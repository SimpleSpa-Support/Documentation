---
description: Services API access is read-only
icon: code
cover: >-
  https://images.unsplash.com/photo-1594904351111-a072f80b1a71?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw0fHxjb2RlfGVufDB8fHx8MTc0NTk0MDEyNXww&ixlib=rb-4.0.3&q=85
coverY: 0
---

# Service Endpoint

> Note: API Beta Access, see [API Terms of Use](integrations/api-terms-of-use.md)

***

## Overview

The Services API allows Enterprise accounts to retrieve a list of active services offered at their business location, including service details like name, duration, price, and categorization.

## Endpoint

```
POST https://my.simplespa.com/api/v1/services.php
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
  "category_id": 5
}
```

| Field        | Type    | Required | Description                                       |
| ------------ | ------- | -------- | ------------------------------------------------- |
| page         | integer | No       | Page number to retrieve (default = 1)             |
| per\_page    | integer | No       | Number of results per page (maximum 1000)         |
| category\_id | integer | No       | Filter services by a specific category (label) ID |

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
  "services": [
    {
      "service_id": "6",
      "name": "Deep Tissue Massage",
      "duration": 60,
      "price": 120.00,
      "special_price": 100.00,
      "category": "Massage",
      "category_id": "1",
      "required_staff": true,
      "required_resource": false,
      "downtime": 0
    }
  ],
  "page": 1,
  "per_page": 100,
  "total_results": 45
}
```

## Response Fields

| Field              | Description                                                                            |
| ------------------ | -------------------------------------------------------------------------------------- |
| success            | Always true if the request was successful                                              |
| services           | List of service records                                                                |
| service\_id        | Unique hashed ID of the service                                                        |
| name               | Service name                                                                           |
| duration           | Service duration in minutes                                                            |
| price              | Regular price for the service                                                          |
| special\_price     | Discounted special price (if applicable)                                               |
| category           | Category (label) name                                                                  |
| category\_id       | Hashed ID of the category (label)                                                      |
| required\_staff    | Boolean indicating if the service requires a specific staff member                     |
| required\_resource | Boolean indicating if the service requires a specific resource (e.g., room, equipment) |
| downtime           | Downtime minutes (if any) after the service                                            |
| page               | Current page number                                                                    |
| per\_page          | Number of results per page                                                             |
| total\_results     | Total number of services available                                                     |

## Notes

* Pagination: Default per\_page is 100 if not specified. Maximum allowed is 1000.
* Filtering: You can filter services by a specific category using the category\_id parameter.
* Prices:
  * If the service has a special discounted price, both price and special\_price will be shown.
  * If no special price exists, special\_price may be null.
* Rate Limiting: Please ensure reasonable usage to avoid throttling. It is recommended to poll no faster than once per minute.

> ⚠️ IMPORTANT: Never expose your private API key in client-side JavaScript. Always use secure, server-side code to handle sensitive credentials.
