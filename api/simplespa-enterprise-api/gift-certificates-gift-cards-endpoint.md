---
description: Gift cards API access is read-only
icon: code
---

# Gift Certificates/Gift Cards Endpoint

> Note: API Beta Access, see [API Terms of Use](https://docs.simplespa.net/simplespa-documentation/api/simplespa-enterprise-api/integrations/api-terms-of-use)

***

### Overview

The Gift Cards API allows Enterprise accounts to retrieve and query gift cards issued through SimpleSpa.

You can:

* Retrieve paginated gift card records
* Search for a specific gift card by code
* Return only cards with a remaining balance
* Exclude expired cards
* Retrieve associated template metadata (name, value)

All gift card and template IDs are returned as hashed IDs, consistent with SimpleSpa’s API design.

***

### Endpoint

```http
POST https://my.simplespa.com/api/v1/giftcards.php
```

***

### Authentication

Requests must include your SimpleSpa Enterprise API Key:

```bash
Authorization: Bearer YOUR_API_KEY
Content-Type: application/json
```

> Replace YOUR\_API\_KEY with your actual API key.

***

### Request Body

| Parameter        | Type    | Required | Description                                                 |
| ---------------- | ------- | -------- | ----------------------------------------------------------- |
| page             | integer | Optional | Page number (default: 1).                                   |
| per\_page        | integer | Optional | Items per page (default: 50, max: 100).                     |
| code             | string  | Optional | Filter by exact gift card code.                             |
| with\_balance    | boolean | Optional | true = return only cards with balance > 0.                  |
| exclude\_expired | boolean | Optional | true = exclude gift cards whose expiration date has passed. |

***

### Example Request

```bash
curl -X POST https://my.simplespa.com/api/v1/giftcards.php \
-H "Authorization: Bearer YOUR_API_KEY" \
-H "Content-Type: application/json" \
-d '{
  "page": 1,
  "per_page": 50,
  "with_balance": true,
  "exclude_expired": true
}'
```

***

### Example Response

```bash
{
  "success": true,
  "gift_cards": [
    {
      "giftcard_id": "2f8b6e1d9cdf41a3e91c5281d913e412",
      "code": "GC-12345",
      "initial_balance": 100,
      "balance": 55,
      "created_at": "2025-01-15 14:22:10",
      "expires_at": "2026-01-15",
      "is_expired": false,
      "template_id": "a0d42dbecf809422c57b04b09458fb1b",
      "template_name": "Holiday Special",
      "template_value": 100
    }
  ],
  "page": 1,
  "per_page": 50,
  "total_results": 27
}
```

***

### Gift Card Fields

| Field            | Type    | Description                                        |
| ---------------- | ------- | -------------------------------------------------- |
| giftcard\_id     | string  | ID of the gift card                                |
| code             | string  | The visible code printed or emailed to the client. |
| initial\_balance | float   | Original purchased value.                          |
| balance          | float   | Current remaining value.                           |
| created\_at      | string  | Timestamp of creation.                             |
| expires\_at      | string  | Expiration date (or null / 0000-00-00 if none).    |
| is\_expired      | boolean | Whether the card is expired as of today.           |
| template\_id     | string  | reference ID.                                      |
| template\_name   | string  | The display name of the template.                  |
| template\_value  | float   | Suggested value of that template.                  |

***

### Filtering Examples

#### 1. Get all active (non-expired) gift cards with balance remaining

```bash
-d '{
  "with_balance": true,
  "exclude_expired": true
}'
```

#### 2. Search for a specific gift card by code

```bash
-d '{
  "code": "GC-12345"
}'
```

#### 3. Combine filters + pagination

```bash
-d '{
  "page": 2,
  "per_page": 25,
  "with_balance": true
}'
```

***

### Pagination

| Parameter      | Description                  |
| -------------- | ---------------------------- |
| page           | Starting at 1                |
| per\_page      | Max 100                      |
| total\_results | Total items matching filters |

### Rate Limiting

The Gift Cards API is limited to:

* 60 requests per minute per API key
* Exceeding this limit returns: 429 Rate limit exceeded

***

### Notes

* All IDs use SimpleSpa’s hashed ID system for security.
* Expiration logic treats NULL and 0000-00-00 as “no expiration.”
* The endpoint supports both JSON POST and URL-based GET (if no JSON body is provided).
* Codes are searchable with exact match only.
* Expired cards are determined server-side based on the current date.

***

### Example Error Response

```json
{
  "error": "Missing or invalid Authorization header"
}
```

> ⚠️ IMPORTANT: Never expose your private API key in client-side JavaScript. Always use secure, server-side code to handle sensitive credentials.
