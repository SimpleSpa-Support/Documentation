---
description: Clients API access is read-only
icon: code
cover: >-
  https://images.unsplash.com/photo-1516259762381-22954d7d3ad2?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwxfHxjb2RlfGVufDB8fHx8MTc0NTk0MDEyNXww&ixlib=rb-4.0.3&q=85
coverY: 0
---

# Client Endpoint

> Note: API Beta Access, see [API Terms of Use](integrations/api-terms-of-use.md)

## Overview

The Clients API endpoint allows you to fetch client records from your SimpleSpa account, with powerful filtering options.

> **Enterprise Feature:** This API access is only available to Enterprise accounts.

You can **search**, **filter by dates**, and **filter by number of completed visits**, allowing highly targeted client lists for marketing campaigns, automations, and integrations.

Compatible with:

* Zapier
* Make.com (Integromat)
* Integrately
* Direct API access (CURL, Postman)

## Endpoint

```
POST https://my.simplespa.com/api/v1/clients.php
```

## Authentication

You must include a valid Authorization header using your SimpleSpa API Key:

```http
Authorization: Bearer YOUR_API_KEY
Content-Type: application/json
```

> Replace YOUR\_API\_KEY with your SimpleSpa Enterprise API Key.

## Request Method

* **POST** with JSON body
* or **GET** with URL parameters (Zapier/Make.com friendly)

## Request Parameters

| Parameter              | Type                | Description                                       |
| ---------------------- | ------------------- | ------------------------------------------------- |
| `page`                 | integer             | Page number (default `1`)                         |
| `per_page`             | integer             | Results per page (max `1000`)                     |
| `search`               | string              | Search by first name, last name, email, or mobile |
| `created_before`       | date (`YYYY-MM-DD`) | Clients created before this date                  |
| `created_after`        | date (`YYYY-MM-DD`) | Clients created after this date                   |
| `first_visit_before`   | date (`YYYY-MM-DD`) | First visit before this date                      |
| `first_visit_after`    | date (`YYYY-MM-DD`) | First visit after this date                       |
| `last_visit_before`    | date (`YYYY-MM-DD`) | Last visit before this date                       |
| `last_visit_after`     | date (`YYYY-MM-DD`) | Last visit after this date                        |
| `min_completed_visits` | integer             | Clients with at least X visits                    |
| `max_completed_visits` | integer             | Clients with no more than X visits                |
| `birthday_month`       | integer (1-12)      | Clients with a birthday in this month             |
| `birthday_day`         | integer (1-31)      | Clients born on this day of month                 |
| `min_points`           | integer             | Minimum points to search                          |

***

## Example CURL Request

```bash
curl -X POST https://my.simplespa.com/api/v1/clients.php \
-H "Authorization: Bearer YOUR_API_KEY" \
-H "Content-Type: application/json" \
-d '{
  "page": 1,
  "per_page": 100,
  "created_before": "2022-01-01",
  "completed_visits_min": 5
}'
```

### Example GET Request (Zapier/Make.com Friendly)

```http
https://my.simplespa.com/api/v1/clients.php?page=1&per_page=100&created_before=2022-01-01&completed_visits_min=5
```

## Response Format

The API responds with a JSON object containing the results and pagination information.

## Example Response

```json
{
  "success": true,
  "clients": [
    {
      "client_id": "1",
      "firstname": "John",
      "lastname": "Doe",
      "email": "john@example.com",
      "mobile": "1234567890",
      "created": "2021-05-15",
      "first_visit": "2021-06-01",
      "last_visit": "2022-12-15",
      "next_visit": "2023-01-10",
      "completed_visits": 12,
      "points": 100
    },
    ...
  ],
  "page": 1,
  "per_page": 100,
  "total_results": 350
}
```

### Example: Birthday Search

Get all clients born in **July**:

```bash
curl -X GET "https://my.simplespa.com/api/v1/clients.php?birthday_month=7" \
-H "Authorization: Bearer YOUR_API_KEY"
```

Get all clients born on **July 15**:

```bash
curl -X GET "https://my.simplespa.com/api/v1/clients.php?birthday_month=7&birthday_day=15" \
-H "Authorization: Bearer YOUR_API_KEY"
```

## Response Format

```json
{
  "success": true,
  "clients": [
    {
      "client_id": "e4bc12f93b...",
      "firstname": "John",
      "lastname": "Doe",
      "email": "john@example.com",
      "mobile": "1234567890",
      "dob_year": "1990",
      "dob_month": "7",
      "dob_day": "15",
      "created": "2020-01-15 10:00:00",
      "first_visit": "2020-02-01 09:00:00",
      "last_visit": "2024-04-28 13:30:00",
      "completed_visits": 18,
      "points": 100
    }
  ],
  "page": 1,
  "per_page": 50,
  "total_results": 1
}
```

## Other Examples

### We Miss You Campaign

* Haven’t visited since April 30, 2024
* And don’t have a future appointment
* Returns the first 100 results (use page: 2 to paginate)

POST

```bash
curl -X POST https://my.simplespa.com/api/v1/clients.php \
-H "Authorization: Bearer YOUR_API_KEY" \
-H "Content-Type: application/json" \
-d '{
  "last_visit_before": "2024-04-30",
  "no_future_visits": true,
  "page": 1,
  "per_page": 100
}'
```

GET&#x20;

```bash
https://my.simplespa.com/api/v1/clients.php?last_visit_before=2025-04-30&no_future_visits=true&page=1&per_page=100
```

## Response Fields

| Field             | Description                      |
| ----------------- | -------------------------------- |
| client\_id        | Unique ID                        |
| firstname         | Client’s first name              |
| lastname          | Client’s last name               |
| email             | Client’s email address           |
| mobile            | Client’s mobile number           |
| dob\_year         | Client's birthday year           |
| dob\_month        | Client's birthday month          |
| dob\_day          | Client's birthday day            |
| created           | When client record was created   |
| first\_visit      | First appointment date           |
| last\_visit       | Last appointment date            |
| next\_visit       | Next booked appointment          |
| completed\_visits | Number of completed appointments |
| points            | Loyalty Points accumulated       |

## Ideas for Marketing or Automation

* Build **Birthday Campaigns** (clients with upcoming birthdays)
* Send **Loyalty Rewards** (clients with `completed_visits >= 10`)
* **Remind inactive clients** (e.g., "last\_visit\_before": "2023-01-01")
* **Create birthday campaigns** (extend API with birthday field if needed)
* **Target VIP clients** who spend more frequently
* Target Clients with the most accumulated loyalty points
* **Export segmented client lists** to Mailchimp or any email platform
* **Trigger SMS** via Twilio for last-minute promos

## Notes

* Important:  for polling-based setup, all new records will be fetched together, which could lead to duplication unless filtered appropriately, please keep a record of those that have been contacted if you are using this for notifications
* `dob_year`, `dob_month`, and `dob_day` are separate fields.
* Search Behavior: The search field performs a partial match across first name, last name, email, and mobile phone.
* Dates must be in `YYYY-MM-DD` format.
* Pagination: Default per\_page is 100 if not specified. Maximum allowed is 1000 per page.
* Rate Limiting: Please ensure reasonable usage to avoid throttling. It is recommended to poll no faster than once per minute.

> ⚠️ IMPORTANT: Never expose your private API key in client-side JavaScript. Always use secure, server-side code to handle sensitive credentials.

