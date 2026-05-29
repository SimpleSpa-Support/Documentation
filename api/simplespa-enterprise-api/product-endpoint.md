---
description: Prouducts API access is read-only
icon: code
cover: >-
  https://images.unsplash.com/photo-1594904351111-a072f80b1a71?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw0fHxjb2RlfGVufDB8fHx8MTc0NTk0MDEyNXww&ixlib=rb-4.0.3&q=85
coverY: 0
---

# Product Endpoint

> Note: API Beta Access, see [API Terms of Use](integrations/api-terms-of-use.md)

***

## Overview

The Services API allows Enterprise accounts to retrieve a list of active products offered at their business location, including product details like name, stock, price, and categorization.

## Endpoint

```
POST https://my.simplespa.com/api/v1/products
```

## Authentication

You must include a valid Authorization header using your SimpleSpa API Key:

```http
Authorization: Bearer YOUR_API_KEY
Content-Type: application/json
```

> Replace YOUR\_API\_KEY with your SimpleSpa Enterprise API Key.

## Request Body

The API expects a JSON body with optional parameters to control pagination and filtering.

Example Request Body

```json
{
  "page": 1,
  "per_page": 100,
  "pos": true
}
```

| Field     | Type    | Required | Description                               |
| --------- | ------- | -------- | ----------------------------------------- |
| page      | integer | No       | Page number to retrieve (default = 1)     |
| per\_page | integer | No       | Number of results per page (maximum 1000) |
| pos       | string  | No       | Filter products with an inventory qty > 0 |

## Example CURL Request

```bash
curl -X POST https://my.simplespa.com/api/v1/services.php \
-H "Authorization: Bearer YOUR_API_KEY" \
-H "Content-Type: application/json" \
-d '{
  "page": 1,
  "per_page": 100
}'
```

## Response Format

The API responds with a JSON object containing the list of services and pagination information.

Example Response

```json
{
  "success": true,
  "products": [
    {
      "product_id": "a4f3e0c0c56d...",
      "name": "Shampoo 250ml",
      "sku": "SHAMP-250",
      "stock": 24,
      "price": 15.0,
      "special_price": 12.0,
      "tax": 24.0,
      "unlimited": false,
      "label": "Hair Care",
      "label_id": "9c13f2...",
      "image_url": "/uploads/products/123.png"
    }
  ],
  "page": 1,
  "per_page": 100,
  "total_results": 245
}
```

## Response Fields

| Field          | Description                               |
| -------------- | ----------------------------------------- |
| success        | Always true if the request was successful |
| products       | List of product records                   |
| product\_id    | Unique hashed ID of the service           |
| name           | Product name                              |
| sku            | SKU number                                |
| stock          | Inventory stock qty                       |
| price          | Regular price for the product             |
| special\_price | Discounted special price (if applicable)  |
| tax            | Tax rate for this product                 |
| unlimited      | If inventory stock is being recorded      |
| label          | Name of the category                      |
| label\_id      | Unique Category ID                        |
| image\_url     | URL which hosts the image                 |
| page           | Current page number                       |
| per\_page      | Number of results per page                |
| total\_results | Total number of services available        |

## Notes

* Pagination: Default per\_page is 100 if not specified. Maximum allowed is 1000.
* Prices:
  * If the service has a special discounted price, both price and special\_price will be shown.
  * If no special price exists, special\_price may be null.
* Rate Limiting: Please ensure reasonable usage to avoid throttling. It is recommended to poll no faster than once per minute.

> ⚠️ IMPORTANT: Never expose your private API key in client-side JavaScript. Always use secure, server-side code to handle sensitive credentials.
