---
icon: gear-code
---

# Appointment Status

> Note: API Beta Access, see [API Terms of Use](https://docs.simplespa.net/simplespa-documentation/api/simplespa-enterprise-api/integrations/api-terms-of-use)

***

### Overview

The Appointment Status Update API allows approved Enterprise accounts to update the status of an existing appointment using the appointment **ID**.

This endpoint is designed for integrations that need to:

* Confirm appointments
* Cancel appointments
* Sync appointment status updates from external systems
* Automate workflows triggered by appointment changes

Status changes update the internal appointment tables and create corresponding status update records used for notifications and audit logs.

### Endpoint

```http
POST https://my.simplespa.com/api/v1/write/appointments-status.php
```

### Authentication

You must include a valid Authorization header using your SimpleSpa API Key:

```http
Authorization: Bearer YOUR_API_KEY
Content-Type: application/json
```

> Replace YOUR\_API\_KEY with your SimpleSpa Enterprise API Key.\
> API Key Mode must be 2 (Write) or 3 (Read + Write) to use this endpoint.

### Request Body

| Parameter       | Type    | Required | Description                                                                                                |
| --------------- | ------- | -------- | ---------------------------------------------------------------------------------------------------------- |
| appointment\_id | string  | Required | The appointment ID.                                                                                        |
| status          | integer | Required | The new appointment status code (see Status Codes table below).                                            |
| reason          | string  | Optional | Optional text describing why the status is being changed (used for logging/audit purposes, not displayed). |

### Example Request

```bash
curl -X POST https://my.simplespa.com/api/v1/write/appointment-status.php \
-H "Authorization: Bearer YOUR_API_KEY" \
-H "Content-Type: application/json" \
-d '{
  "appointment_id": "e3b0c44298fc1c149afbf4c8996fb924",
  "status": 20,
  "reason": "client_confirmed_via_external_system"
}'
```

### Example Response

```json
{
  "success": true,
  "appointment_id": "e3b0c44298fc1c149afbf4c8996fb924",
  "appointment_id_raw": 12345,
  "old_status": 10,
  "new_status": 20,
  "reason": "client_confirmed_via_external_system"
}
```

**Example 1 — Mark Appointment as Confirmed**

```bash
curl -X POST https://my.simplespa.com/api/v1/write/appointment-status.php \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "appointment_id": "e3b0c44298fc1c149afbf4c8996fb924",
    "status": 20,
    "reason": "client_confirmed_via_external_system"
  }'
```

**Example 2 — Cancel Appointment**

```bash
curl -X POST https://my.simplespa.com/api/v1/write/appointment-status.php \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "appointment_id": "e3b0c44298fc1c149afbf4c8996fb924",
    "status": 15,
    "reason": "cancelled_by_client"
  }'
```

### Status Codes

These status codes align with the main Appointment Endpoint:

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

### Notes

* This endpoint only updates status for an existing appointment. It does not create appointments or change times, staff, or services.
* Rate Limiting: This endpoint is strictly rate limited. Excessive updates may result in HTTP 429 responses. We recommend keeping status updates to no more than 10 requests per minute per API key.
* Pagination is not applicable for this endpoint (single appointment update per call).<br>

> ⚠️ IMPORTANT: Never expose your private API key in client-side JavaScript, mobile apps, or public code repositories. Always perform API calls from secure, server-side code.
