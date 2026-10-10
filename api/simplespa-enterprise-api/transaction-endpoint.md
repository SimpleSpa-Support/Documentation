---
description: Transactions API access is read-only
icon: code
cover: >-
  https://images.unsplash.com/photo-1584949091598-c31daaaa4aa9?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw5fHxjb2RlfGVufDB8fHx8MTc0NTk0MDEyNXww&ixlib=rb-4.0.3&q=85
coverY: 0
---

# Transaction Endpoint

> Note: API Beta Access, see [API Terms of Use](integrations/api-terms-of-use.md)

***

## Overview

The Transactions API allows Enterprise accounts to retrieve a paginated list of their transactions for a selected time period, including the receipt number, date/time, client, item name, price, tax, discount, qty, type (e.g., Service, Product), and user.

## Endpoint

```http
POST https://my.simplespa.com/api/v1/transactions.php
```

## Authentication

You must include a valid Authorization header using your SimpleSpa API Key:

```http
Authorization: Bearer YOUR_API_KEY
Content-Type: application/json
```

> Replace YOUR\_API\_KEY with your SimpleSpa Enterprise API Key.

## Request Body

| Field      | Type    | Required | Description                                                                       |
| ---------- | ------- | -------- | --------------------------------------------------------------------------------- |
| start      | string  | Yes      | Start date in YYYY-MM-DD format                                                   |
| end        | string  | Yes      | End date in YYYY-MM-DD format                                                     |
| client\_id | string  | No       | Client ID found from the SimpleSpa client profile or from the Client Endpoint API |
| page       | integer | No       | Page number (default: 1)                                                          |
| per\_page  | integer | No       | Results per page (default: 1000 maximum)                                          |

## Example Request

```bash
curl -X POST https://my.simplespa.com/api/v1/transactions.php \
-H "Authorization: Bearer YOUR_API_KEY" \
-H "Content-Type: application/json" \
-d '{
  "start": "2025-06-01",
  "end": "2025-06-30",
  "page": 1,
  "per_page": 10
}'
```

## Example Response

```json
{
  "success": true,
  "start": "2025-06-01",
  "end": "2025-06-30",
  "total_results": 2,
  "transactions": [
    {
      "receipt_id": "R-9582",
      "timestamp": "2025-06-05 14:22:11",
      "client": "John Doe",
      "description": "Swedish Massage",
      "amount": 85.00,
      "tax": 6.80,
      "discount": 10.00,
      "qty": 1,
      "type": "Service",
      "user": "user@simplespa.com"
    },
    {
      "receipt_id": "R-9583",
      "timestamp": "2025-06-05 14:34:08",
      "client": "WALKIN",
      "description": "Lavender Body Oil",
      "amount": 24.00,
      "tax": 1.92,
      "discount": 0.00,
      "qty": 1,
      "type": "Product",
      "user": "user@simplespa.com"
    }
  ]
}
```

## Notes

* Important: For a polling-based setup, all new records are fetched together, which could lead to duplicates unless you filter them appropriately. Please keep a record of the clients you have contacted if you use this for notifications.
* Limitation: The start/end date range can be up to 92 days.
* Pagination: Default per\_page is 100 if not specified. Maximum allowed is 1000 per page.
* Rate Limiting: Please ensure reasonable usage to avoid throttling. It is recommended to poll no faster than once per minute.

> ⚠️ IMPORTANT: Never expose your private API key in client-side JavaScript. Always use secure, server-side code to handle sensitive credentials.
