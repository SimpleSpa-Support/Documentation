---
description: >-
  You now have enough data to create powerful campaigns with the SimpleSpa
  Enterprise API
icon: code
---

# Ideas: Marketing Campaigns with Zapier, Make.com, Integrately

## Example Use Cases

| Automation                             | How                                                                                                                                                                                                                            |
| -------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Send welcome email to new clients      | Use created field — If client is new, send a Mailchimp campaign or Gmail                                                                                                                                                       |
| Send reactivation SMS                  | If last\_visit > 6 months ago, send reminder through Twilio                                                                                                                                                                    |
| Upsell to frequent visitors            | If completed\_visits > 5, invite them to VIP membership via Mailchimp                                                                                                                                                          |
| Remind for next visit                  | Use next\_visit field to schedule WhatsApp/SMS reminders (note that SimpleSpa automatically will send out reminder Email/SMS to clients according to the set reminder period, by default 24h prior to their scheduled booking) |
| Sync clients to CRM                    | Send data to Hubspot, Salesforce, or Airtable                                                                                                                                                                                  |
| Segment marketing by completed\_visits | Tag clients automatically based on visit history                                                                                                                                                                               |

## Zapier / Make.com Template Example:

* Trigger: Webhook → Pull Clients API (per page)
* Filter: Only clients with completed\_visits > 5
* Action: Add to Mailchimp List “VIP Clients”

or

* Trigger: Webhook → Pull Clients API
* Filter: Clients where last\_visit is older than 6 months
* Action: Send SMS “We miss you!”

## Summary

* Clients API is now ready for Zapier, Make, Integrately, Pabbly, and others.
* GET or POST — flexible for any platform.
* New fields allow smarter segmentation and campaigns.
