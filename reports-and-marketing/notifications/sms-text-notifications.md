---
description: >-
  Customizable SMS/text notifications for clients and staff, supported tags,
  replies, Sender ID and dedicated numbers.
---

# SMS/Text Notifications

This page explains the SMS/text notifications SimpleSpa sends to your clients and staff, and how to customize them.

SimpleSpa offers the most comprehensive SMS notifications in the industry, and you can customize each text message to meet your needs. By default, automated SMS/text reminders are sent 24h before a scheduled appointment.

If an appointment is scheduled less than 24h in advance, you can either:

1. Change the appointment status to confirmed (from the appointment prompt), so the confirmation goes out to the client.
2. If the client has an email on file, click **Send Email** in the appointment prompt to send an email with the appointment details.

## Client SMS/Text Appointment Reminder

Your clients receive an automated SMS reminder a day before their appointment.

* To let clients confirm or cancel their appointment, use the `[CONFIRM]` tag.
* To accept confirmations only, use the `[CNFRM]` tag.

<figure><img src="https://695085455-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fa9tSKQ7Cexg8YEba5Evb%2Fuploads%2Fwp4VKQ4CNiWYdNiAFPRZ%2FScreenshot%202024-07-05%20at%209.09.29%E2%80%AFAM.png?alt=media&#x26;token=7a1ca213-1a7a-45c5-87a1-7b6c6f4944ef" alt=""><figcaption><p>The Client Reminder template (sent at a default time of 24h before the scheduled appointment)</p></figcaption></figure>

## Client SMS/Text Appointment Confirmation

When you set your client's appointment as confirmed, your client receives an appointment notification. You can set this manually:

* by changing the appointment status when a client has confirmed, or
* when booking within SimpleSpa, by toggling the appointment as confirmed at the end of the booking process in the appointment wizard.

<figure><img src="https://695085455-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fa9tSKQ7Cexg8YEba5Evb%2Fuploads%2FYQNT39wIhq8cs6CCnOT8%2FScreenshot%202024-07-05%20at%209.09.45%E2%80%AFAM.png?alt=media&#x26;token=9e1cc27c-af90-4d89-80e0-d0707030f612" alt=""><figcaption><p>The Client Confirmation template (sent when the appointment has been confirmed)</p></figcaption></figure>

## Client Thank You SMS/Text

After a successful transaction in the POS, your clients receive an automated SMS with a thank you message. The client needs a valid mobile number on their profile. You can also include the receipt using the `[RECEIPT]` tag.

<figure><img src="https://695085455-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fa9tSKQ7Cexg8YEba5Evb%2Fuploads%2FkTOveBrZM2J9GqlcK3CQ%2FScreenshot%202024-07-05%20at%209.10.07%E2%80%AFAM.png?alt=media&#x26;token=6e1543b2-5b73-49b9-9a39-806421480378" alt=""><figcaption><p>The Client Thank You template</p></figcaption></figure>

## Staff SMS/Text Appointment Notification

When an appointment is created, your staff are notified so they know they have been scheduled.

<figure><img src="https://695085455-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fa9tSKQ7Cexg8YEba5Evb%2Fuploads%2F0VoYvNLIetGROHr1Zsg5%2FScreenshot%202024-07-05%20at%209.11.11%E2%80%AFAM.png?alt=media&#x26;token=8d93793f-c377-4d17-aeb9-a19b76d03474" alt=""><figcaption><p>The Staff Notification template</p></figcaption></figure>

## Staff SMS/Text Appointment Cancellation Notification

When an appointment is canceled, your staff are notified of the cancellation.

<figure><img src="https://695085455-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fa9tSKQ7Cexg8YEba5Evb%2Fuploads%2F33tZvfj9zH5Fo5T61Zrs%2FScreenshot%202024-07-05%20at%209.13.12%E2%80%AFAM.png?alt=media&#x26;token=cccc361d-d782-4d25-9c42-cf18a3d4bf28" alt=""><figcaption><p>The Staff Cancelled template</p></figcaption></figure>

## Daily Staff Digest

The digest sends your staff a message 2 hours before their shift, listing their appointments for the day, with an attachment of their upcoming appointments.

<figure><img src="https://695085455-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fa9tSKQ7Cexg8YEba5Evb%2Fuploads%2FXGp5kL5TgwFfjRJJGRZ2%2FScreenshot%202024-07-05%20at%209.13.00%E2%80%AFAM.png?alt=media&#x26;token=1ce5bbc9-ff40-4623-9024-b4ba4586a191" alt=""><figcaption><p>The Daily Agenda toggle section</p></figcaption></figure>

## Supported SMS Tags

| Tag             | What it shows                                                             |
| --------------- | ------------------------------------------------------------------------- |
| `[CLIENT_NAME]` | The client name                                                           |
| `[STAFF_NAME]`  | The assigned staff name                                                   |
| `[BUSINESS]`    | The business name                                                         |
| `[LOCATION]`    | The location name                                                         |
| `[DATE]`        | Date only                                                                 |
| `[TIME]`        | Time only                                                                 |
| `[DATETIME]`    | Date and time                                                             |
| `[CONFIRM]`     | A link that lets the client confirm or cancel their scheduled appointment |
| `[CNFRM]`       | A link that lets the client confirm only                                  |
| `[RECEIPT]`     | A receipt link, if the client was checked out using the POS               |

## Support for Client Replies

If your clients reply to a SimpleSpa notification text/SMS, the reply shows up in your SimpleSpa account when you view all the sent messages for the day. A dedicated button on each message lets you quickly view the related appointment. On the SimpleSpa dashboard, replies show up as "growl"-style notification alerts.

{% hint style="info" %}
This functionality may be limited in some locales or if you have a custom Sender ID.
{% endhint %}

SimpleSpa does not provide two-way communication with your clients. It sends only transactional messages about appointments to your clients, and receives your clients' replies to those notifications.

You can reply to a client manually if you are on a mobile device, or a device connected to a messaging app. Click the client's mobile number link in the appointment popup to open a supported messaging app and send a message to that number.

## Support for Client Return Calls

Calls to the number that sent the text notification are answered by an automated IVR. Clients with existing appointments hear a greeting with their next scheduled appointment date, time, service and staff member. They can then confirm their appointment directly over the phone.

{% hint style="info" %}
This functionality may be limited in some locales or if you have a custom Sender ID.
{% endhint %}

SimpleSpa sends SMS notifications with a 5 minute delay to avoid accidental appointment changes. To subscribe to our SMS/Text Message Plans, please [click here](https://www.simplespa.com/sms).

## Sender ID

In some countries, SimpleSpa supports a custom Sender ID. A Sender ID is a name, typically your business name, shown in place of the phone number the text message is sent from. It may be limited to 9-11 characters.

Some countries require a Sender ID to be registered with local regulators before any SMS can be sent. To register a custom Sender ID, contact our support team. We'll check availability and quote you the monthly maintenance fee for the service.

## Dedicated Number

In certain regions, SimpleSpa supports a dedicated number for sending your messages. If you're interested, contact our support team. They'll check availability and quote you the monthly maintenance fee.

## Related

* [SMS Replies and Confirmations](sms-replies-and-confirmations.md)
* [Email Notifications](email-notifications.md)
* [Appointment Status](../../daily-operations/appointments/appointment-status.md)
