---
description: Appointments API access is read-only
icon: code
cover: >-
  https://images.unsplash.com/photo-1584949091598-c31daaaa4aa9?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw5fHxjb2RlfGVufDB8fHx8MTc0NTk0MDEyNXww&ixlib=rb-4.0.3&q=85
coverY: 0
---

# Appointment Endpoint

> Note: API Beta Access, see [API Terms of Use](integrations/api-terms-of-use.md)

***

## Overview

The Appointments API allows Enterprise accounts to retrieve a paginated list of their appointments for a selected time period, including creation date/time, appointment start-end date/time, client, staff and service details.

## Endpoint

```http
POST https://my.simplespa.com/api/v1/appointments.php
```



## Authentication

You must include a valid Authorization header using your SimpleSpa API Key:

```http
Authorization: Bearer YOUR_API_KEY
Content-Type: application/json
```

> Replace YOUR\_API\_KEY with your SimpleSpa Enterprise API Key.

## Request Body

| Parameter       | Type                | Required    | Description                                                                                                                   |
| --------------- | ------------------- | ----------- | ----------------------------------------------------------------------------------------------------------------------------- |
| start           | string (YYYY-MM-DD) | Conditional | Beginning of the service date window (e.g., 2025-10-01). Required if created\_after / created\_before are not used.           |
| end             | string (YYYY-MM-DD) | Conditional | End of the service date window (e.g., 2025-10-31). Required if created\_after / created\_before are not used.                 |
| created\_after  | string (ISO 8601)   | Conditional | Fetch appointments created on or after this date/time (e.g., 2025-10-01T00:00:00Z). When provided, start and end are ignored. |
| created\_before | string (ISO 8601)   | Optional    | Fetch appointments created before this date/time (optional when using created\_after).                                        |
| client\_id      | string              | Conditional | The client ID from the client profile in SimpleSpa or from the Client Endpoint API                                            |
| service\_id     | string              | Conditional | ID from API endpoints                                                                                                         |
| staff\_id       | string              | Conditional | ID from the API endpoints                                                                                                     |
| status          | integer             | Optional    | Filter by appointment status (see table below).                                                                               |
| page            | integer             | Optional    | Page number for pagination (default: 1).                                                                                      |
| per\_page       | integer             | Optional    | Number of results per page (default: 100, max: 1000).                                                                         |

## Example Request

```bash
curl -X POST https://my.simplespa.com/api/v1/appointments.php \
-H "Authorization: Bearer YOUR_API_KEY" \
-H "Content-Type: application/json" \
-d '{
  "start": "2025-04-01",
  "end": "2025-04-30",
  "status": 20,
  "page": 1,
  "per_page": 10
}'
```

## Example Response

```json
{
  "success": true,
  "appointments": [
    {
      "appointment_id": "1",
      "created_at": "2025-04-25 12:34:56",
      "start": "2025-04-30 09:00:00",
      "end": "2025-04-30 10:00:00",
      "status": 20,
      "status_label": "Confirmed",
      "client": {
        "client_id": "1",
        "first_name": "John",
        "last_name": "Doe",
        "mobile": "555-1234",
        "email": "john@example.com"
      },
      "service": {
        "service_id": "3",
        "service_name": "Deep Tissue Massage"
      },
      "staff": {
        "staff_id": "5",
        "staff_name": "Jane Therapist"
      }
    }
  ],
  "page": 1,
  "per_page": 10,
  "total_results": 50
}
```

#### 🔍 Example 1 — Fetch by Appointment Status & Date

```bash
curl -X POST https://my.simplespa.com/api/v1/appointments.php \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "start": "2025-10-01",
    "end": "2025-10-31",
    "status": 20,
    "page": 1,
    "per_page": 100
  }'
```

#### 🔍 Example 2 — Fetch by Creation Time

```bash
curl -X POST https://my.simplespa.com/api/v1/appointments.php \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "created_after": "2025-10-01T00:00:00Z",
    "page": 1,
    "per_page": 100
  }'
```

## Status Codes

| Code | Description        |
| ---- | ------------------ |
| 0    | New                |
| 5    | Rebooked           |
| 7    | Request            |
| 10   | Online             |
| 12   | Payment Due        |
| 15   | Canceled           |
| 17   | No-Show            |
| 20   | Confirmed          |
| 22   | Confirmed (No SMS) |
| 25   | Arrived            |
| 30   | Paid               |
| 40   | Completed          |

## Notes

* Important:  for polling-based setup, all new records will be fetched together, which could lead to duplication unless filtered appropriately, please keep a record of those that have been contacted if you are using this for notifications
* Limitation: Start/End date can range up to 92 days
* Pagination: Default per\_page is 100 if not specified. Maximum allowed is 1000 per page.
* Rate Limiting: Please ensure reasonable usage to avoid throttling. It is recommended to poll no faster than once per minute.

> ⚠️ IMPORTANT: Never expose your private API key in client-side JavaScript. Always use secure, server-side code to handle sensitive credentials.
