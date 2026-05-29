---
description: Staff API access is read-only
icon: code
cover: >-
  https://images.unsplash.com/photo-1515879218367-8466d910aaa4?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHw4fHxjb2RlfGVufDB8fHx8MTc0NTk0MDEyNXww&ixlib=rb-4.0.3&q=85
coverY: 0
---

# Staff Endpoint

> Note: API Beta Access, see [API Terms of Use](integrations/api-terms-of-use.md)

***

## Overview

The Staff API allows Enterprise accounts to retrieve a list of active staff offered at their business location, including service details like name, contact information, and general staff work hours.

## Authentication

You must include a valid Authorization header using your SimpleSpa API Key:

```http
Authorization: Bearer YOUR_API_KEY
Content-Type: application/json
```

> Replace YOUR\_API\_KEY with your SimpleSpa Enterprise API Key.

## Appointments API

## Endpoint

```http
POST https://my.simplespa.com/api/v1/staff.php
```

## Authentication

You must include a valid Authorization header using your SimpleSpa API Key:

| Header Name   | Header Value          |
| ------------- | --------------------- |
| Authorization | Bearer YOUR\_API\_KEY |
| Content-Type  | application/json      |

> Replace YOUR\_API\_KEY with your SimpleSpa Enterprise API Key.

## Request Body

The API expects a JSON body with optional parameters to control pagination and filtering.

## Example Request Body

```json
{
  "page": 1,
  "per_page": 100
}
```

| Field     | Type    | Required | Description                               |
| --------- | ------- | -------- | ----------------------------------------- |
| page      | integer | No       | Page number to retrieve (default = 1)     |
| per\_page | integer | No       | Number of results per page (maximum 1000) |

## Example CURL Request

```bash
curl -X POST https://my.simplespa.com/api/v1/staff.php \
-H "Authorization: Bearer YOUR_API_KEY" \
-H "Content-Type: application/json" \
-d '{
  "page": 1,
  "per_page": 100
}'
```

## Response Format

The API responds with a JSON object containing the list of staff members and pagination information.

Example Response

```json
{
  "success": true,
  "staff": [
    {
      "staff_id": "1",
      "first_name": "Jane",
      "last_name": "Doe",
      "email": "john@example.com",
      "phone": "+15551234567",
      "gender": "Male",
      "color_code": "#FF5733",
      "labels": ["Massage", "Therapy"],
      "label_ids": ["1", "2"],
      "working_hours": [
        { "day": 1, "start_time": "09:00", "end_time": "17:00" },
        { "day": 3, "start_time": "10:00", "end_time": "18:00" }
      ],
      "staff_image_url": "https://my.simplespa.com/uploads/staff/12345.jpg",
      "deleted": false
    }
  ],
  "page": 1,
  "per_page": 100,
  "total_results": 20
}
```

## Response Fields

| Field             | Description                                                 |
| ----------------- | ----------------------------------------------------------- |
| success           | Always true if the request was successful                   |
| staff             | List of staff records                                       |
| staff\_id         | Unique ID of the staff member                               |
| first\_name       | Staff member’s first name                                   |
| last\_name        | Staff member’s last name                                    |
| email             | Staff member’s email address                                |
| phone             | Staff member’s phone number                                 |
| gender            | Gender of the staff member (if provided)                    |
| color\_code       | Assigned color code for calendar views                      |
| labels            | Skills or categories associated with the staff              |
| label\_ids        | IDs of the labels (category)                                |
| working\_hours    | Weekly working hours array (day: 0 = Monday, 6 = Sunday)    |
| staff\_image\_url | Public URL of the staff member’s avatar image (if uploaded) |
| deleted           | If true, this staff is currently inactive/deleted           |
| page              | Current page number                                         |
| per\_page         | Number of results per page                                  |
| total\_results    | Total number of staff available                             |

## Notes

*   Working Hours:

    Only the first time range per day is returned. Days without hours are skipped.
*   Pagination:

    Default per\_page is 100 if not specified. Maximum allowed is 1000.
*   Filtering Inactive Staff:

    Only staff with active = 1 are returned (deleted staff are flagged with "deleted": true).
*   Rate Limiting:

    It is recommended to query no faster than once per minute

> ⚠️ IMPORTANT: Never expose your private API key in client-side JavaScript. Always use secure, server-side code to handle sensitive credentials.

