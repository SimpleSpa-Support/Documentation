---
description: >-
  Confirmation and reminder emails end with links that let clients, or their AI
  assistant, book the same service again in one tap.
icon: rotate-right
---

# Rebooking Links in Emails

Appointment confirmation and reminder emails now end with two small links: one to book the same service again, and one to see open times. Clients can rebook in one tap, and AI assistants that read a client's inbox can find the right link when the client asks them to "book my usual again".

## What clients see

At the bottom of the email, just above the SimpleSpa footer, there is one quiet line:

* Confirmations: **Book next visit · See open times**
* Reminders: **Book again · See open times**

Your message itself is not changed, so custom email designs keep their look. The plain-text version of the email includes both links in full.

## Which emails include them

* Appointment confirmation emails, both after a client books online and when sent from SimpleSpa.
* Email reminders.

Staff notifications, text messages and marketing campaigns don't include them.

## What the links do

* **Book again / Book next visit** opens your booking page with the same service already selected. If Staff Selection is on and the staff member offers the service online, they're selected too. For online bookings, the staff member is only included if the client chose them, not when they booked with **Any staff**.
* **See open times** opens the [open times page](../online-booking/ai-assistants-and-direct-booking-links.md#the-open-times-page) for that service for the next 7 days.

## When they're included

The links are only added when all of these are true:

1. The location has a [custom booking URL](../online-booking/your-custom-booking-url.md), which means it takes online bookings.
2. The location uses the [new online booking page](../online-booking/the-online-booking-page.md).
3. The service can be booked online: it's shown online and isn't an add-on.

If any of these is missing, the email is sent exactly as before, without the links.

## Language

The links follow the location's language: English, Greek, Italian, Spanish, French, German or Portuguese. Other languages use English.

## Placing the links inside your message

To show the links inside your own message instead of in the footer, add the `[BOOK_AGAIN]` tag to your confirmation or reminder template in **Settings → Locations → (your location) → Email Notifications**. The tag is replaced with a small block that includes the service name. When the tag is used, the footer line is left out, so the links never appear twice.

{% hint style="info" %}
If the links can't be included for an appointment (for example, the service isn't bookable online), the `[BOOK_AGAIN]` tag is simply removed.
{% endhint %}

## Tracking

The links carry `utm_source=email`, with `utm_medium=confirmation` or `utm_medium=reminder`, so bookings made from them are recorded as coming from an email link. See [Where bookings come from](../online-booking/ai-assistants-and-direct-booking-links.md#where-bookings-come-from).

## Related

* [Email Notifications](email-notifications.md)
* [AI Assistants & Direct Booking Links](../online-booking/ai-assistants-and-direct-booking-links.md)
