---
description: Integrate SimpleSpa with Integrately
hidden: true
icon: code
---

# Integrately

## Create a new Automation

* Click Create Automation.
* Search for “Webhook” (because you are using your own API).
* Choose “Webhook” as the Trigger (if pulling), or App Action (if sending).

## Use the “Webhook” App

* Select Webhook → Custom Webhook.
* Integrately supports sending requests (outbound) and receiving requests (inbound).
* Because you want to pull appointments, you should send a webhook request to your API.

## Set up the Webhook Request (HTTP Request)

| Field        | What to put                                                                                         |
| ------------ | --------------------------------------------------------------------------------------------------- |
| Method       | POST (or GET if you change your API to accept GET)                                                  |
| Webhook URL  | https://my.simplespa.com/api/appointments.php                                                       |
| Headers      | <p>Add 2 headers:</p><p>Authorization: Bearer YOUR_API_KEY</p><p>Content-Type: application/json</p> |
| Body Type    | Raw (application/json)                                                                              |
| Request Body | JSON like:                                                                                          |

```json
{
  "start": "2025-04-01",
  "end": "2025-04-30",
  "status": 0,
  "page": 1,
  "per_page": 100
}
```

## Test the Webhook

* Press Send Test Request inside Integrately.
* If successful, Integrately will show the JSON response from your API.
* You can now map the fields (appointments) to another app.

## How it fits Integrately

| Scenario              | Example                                       |
| --------------------- | --------------------------------------------- |
| Pull Appointments     | Send API Request to your endpoint             |
| Send to Google Sheets | Map appointment fields to spreadsheet columns |
| Send SMS              | Map client mobile field to Twilio or SMS App  |
| Send Email            | Map appointment details to Email Automation   |

## Summary Steps

1. Create Automation
2. Choose Webhook > Custom Webhook
3. Set Method = POST
4. Set URL = your API
5. Add Authorization and Content-Type Headers
6. Set JSON body
7. Test
8. Connect to next app (Google Sheets, Email, Slack, CRM, etc.)

## Bonus Tip

If you want to schedule it, Integrately lets you “Run Every Hour” or “Every Day” without needing a cron job.
