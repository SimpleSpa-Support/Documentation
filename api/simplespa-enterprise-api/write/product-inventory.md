---
icon: gear-code
---

# Product Inventory

Note: API Beta Access, see [API Terms of Use](https://docs.simplespa.net/simplespa-documentation/api/simplespa-enterprise-api/integrations/api-terms-of-use)

***

### Overview

The Product Inventory Write API allows Enterprise accounts to **adjust product stock levels** programmatically using the same logic as the SimpleSpa back office UI.

This endpoint is designed for integrations that need to:

* Sync inventory with external POS systems
* Deduct stock when a sale occurs outside SimpleSpa
* Add stock when new inventory is received
* Record inventory adjustments (e.g., damaged, lost, manual corrections)

Each call creates an inventory transaction record and updates the product’s current quantity for the specific business location.

> 🧾 For reading products and their current stock levels, use the **Products Endpoint**:\
> `POST https://my.simplespa.com/api/v1/products.php`

***

### Endpoint

```http
POST https://my.simplespa.com/api/v1/write/product.php
```

### Authentication

You must include a valid Authorization header using your SimpleSpa API Key:

```http
Authorization: Bearer YOUR_API_KEY
Content-Type: application/json
```

> Replace YOUR\_API\_KEY with your SimpleSpa Enterprise API Key.\
> API Key Mode must be 2 (Write) or 3 (Read + Write) to use this endpoint.

***

### Rate Limiting

This endpoint has a strict rate limit of:

```
10 requests per 60 seconds per API key
```

If exceeded, the API will return a 429 response.

***

### Request Body

| Parameter    | Type    | Required | Description                                                                                                   |
| ------------ | ------- | -------- | ------------------------------------------------------------------------------------------------------------- |
| product\_id  | string  | ✔        | The product ID.                                                                                               |
| qty          | integer | ✔        | Quantity change. Positive to add stock, negative to deduct stock. The final stock cannot go below 0.          |
| unit\_price  | number  | ✔        | Unit cost for this inventory movement (used for reporting and cost tracking).                                 |
| date         | string  | Optional | Inventory transaction date in YYYY-MM-DD format. If omitted, the current date/time is used.                   |
| vendor\_id   | integer | Optional | Existing vendor ID in SimpleSpa. If provided, this vendor will be used.                                       |
| vendor\_name | string  | Optional | Vendor name. If vendor\_id is not provided and vendor\_name is provided, a vendor may be created or matched.  |
| reason       | string  | Optional | Free-text reason or note for this adjustment (e.g., external\_pos\_sale, manual\_adjustment, damaged\_stock). |

> You should provide at least one of vendor\_id or vendor\_name when recording purchases or adjustments tied to a supplier or source.

***

### Example Request – Deduct Stock After External Sale

```bash
curl -X POST https://my.simplespa.com/api/v1/write/product.php \
-H "Authorization: Bearer YOUR_API_KEY" \
-H "Content-Type: application/json" \
-d '{
  "product_id": "a4f3e0c0c56d6ab3e9b0b51e77e9b123",
  "qty": -2,
  "unit_price": 15.50,
  "date": "2025-12-06",
  "vendor_name": "External POS",
  "reason": "external_pos_sale"
}'
```

In this example:

* Stock for the specified product will be reduced by 2 units.
* A new inventory transaction will be recorded using the provided unit\_price.
* If needed, a vendor entry named External POS may be created or reused.

***

### Example Request – Add Stock for New Purchase

```bash
curl -X POST https://my.simplespa.com/api/v1/write/product.php \
-H "Authorization: Bearer YOUR_API_KEY" \
-H "Content-Type: application/json" \
-d '{
  "product_id": "1234",
  "qty": 10,
  "unit_price": 8.00,
  "date": "2025-12-06",
  "vendor_id": 5,
  "reason": "new_shipment_from_supplier"
}'
```

In this example:

* Stock for product ID 1234 will be increased by 10 units.
* Vendor with ID 5 will be used for this inventory transaction.
* Cost and stock levels are updated for reporting and stock tracking.

***

### Example Response

```json
{
  "success": true,
  "product_id": "a4f3e0c0c56d6ab3e9b0b51e77e9b123",
  "product_id_raw": 1234,
  "old_stock": 5,
  "new_stock": 15,
  "qty_delta": 10,
  "reason": "new_shipment_from_supplier"
}
```

***

### Error Responses

Missing or Invalid Authorization

```json
{ "error": "Missing or invalid Authorization header" }
```

#### API Key Not Authorized

```json
{ "error": "This API key is not authorized for inventory write operations (requires mode 2 or 3)." }
```

#### Product Not Found

```json
{ "error": "Product not found for this business/location." }
```

#### Invalid Parameters

```json
{ "error": "product_id is required." }
```

```json
{ "error": "qty must be a non-zero integer." }
```

```json
{ "error": "Resulting stock cannot be negative." }
```

#### Rate Limit Exceeded

```json
{
  "error": "Rate limit exceeded for product inventory writes. Please slow down your requests.",
  "retry_after": 60
}
```

### Notes

* Use the Products Endpoint (/api/v1/products.php) to fetch product lists, labels, and current stock before writing.
* This endpoint is idempotent per call in the sense that each call records a separate inventory movement; it does notoverwrite stock, it adjusts it.
* Inventory writes are per business location. The API key’s lid determines which location’s stock is affected.
* Always store your API key securely on the server side.
* Do not expose your API key to client-side JavaScript, mobile apps, or public environments.

> ⚠️ IMPORTANT: For external POS or e-commerce integrations, ensure you only call this endpoint once per sale or stock event to avoid double-counting inventory changes.
>
> ⚠️ IMPORTANT: Never expose your private API key in client-side JavaScript, mobile apps, or public code repositories. Always perform API calls from secure, server-side code.
