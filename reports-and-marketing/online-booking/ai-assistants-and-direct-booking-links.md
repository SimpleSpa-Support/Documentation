---
description: >-
  How ChatGPT, Claude and other AI assistants read your online booking page, the
  open times page, and links that open booking with a service, staff member,
  date or time already chosen.
icon: robot
---

# AI Assistants & Direct Booking Links

More and more clients ask an AI assistant, such as ChatGPT or Claude, to find a service and book it for them. Your online booking page is built so these assistants can read your services and open times, and send the client to your page with the right service already chosen.

{% hint style="info" %}
These features work for locations that have a [custom booking URL](your-custom-booking-url.md) and use the [new online booking page](the-online-booking-page.md). Contact support if you're not sure which booking page your location uses.
{% endhint %}

## What assistants can read

When an assistant opens your booking page, it can read:

* Your business name, address, phone number, opening hours and upcoming holidays.
* Your services, grouped by category, with their duration.
* Your prices, only if **Show Prices** is on for the location.
* Your staff and the services each one offers, only if **Staff Selection** is on.
* A link to book each service, and a link to see its open times.

Client information is never included. Changes you make to services, prices, staff or hours appear within about 10 minutes.

### How it works

Your booking page now includes a plain-text version of this information, plus a standard description of your business (schema.org structured data) that search engines and assistants understand. Your clients still see the normal booking page; the text version is hidden from them.

{% hint style="success" %}
**Assistants don't book on their own.** An assistant gives the client a link to your booking page. The client confirms the time and enters their details on your page, so your deposits, cards on file, booking window and terms all apply as usual.
{% endhint %}

## The open times page

Each location also has a simple page that lists the open times for a service. Assistants read it to answer questions such as "when can I get a facial tomorrow?":

```
https://yourname.simplespa.com/availability.php?svc=123&date=tomorrow
```

| Setting | What it does                                                                    |
| ------- | ------------------------------------------------------------------------------- |
| `svc`   | The service ID. Required.                                                       |
| `date`  | `today`, `tomorrow` or a date such as `2026-12-05`.                             |
| `days`  | How many days to list, from 1 to 7.                                             |
| `staff` | A staff member's ID, to show only their times. Used when Staff Selection is on. |

* Open times follow the same rules as your booking page: opening hours, holidays, staff schedules, existing appointments, your booking buffer and how far ahead clients can book.
* Times are grouped into morning, afternoon and evening, and each time links to your booking page with that time already chosen.
* Times are refreshed every couple of minutes. The final check happens when the client books, so a time that was just taken can't be double booked.
* People who open this page in a browser are taken straight to your booking page with the service selected.
* The page is not listed in search engines.

## Direct booking links

You can open your booking page with a service, staff member, date or time already chosen by adding these to the end of your booking URL:

| Setting | What it does                                                                        | Example            |
| ------- | ----------------------------------------------------------------------------------- | ------------------ |
| `svc`   | Adds one or more services to the booking (up to 5, separated by commas).            | `?svc=123`         |
| `staff` | Selects a staff member. Used when Staff Selection is on and they offer the service. | `&staff=45`        |
| `date`  | Opens the calendar on that date.                                                    | `&date=2026-12-05` |
| `time`  | Selects that time on the date, if it's still free (24-hour clock).                  | `&time=14:30`      |

For example:

```
https://yourname.simplespa.com/?svc=123&staff=45&date=2026-12-05&time=14:30
```

* A date in the past, or beyond how far ahead clients can book, moves to the nearest day the client can book.
* If the time has been taken, the client sees a short message and picks another time.
* The client can still change anything before confirming.

Use these links anywhere you promote a single service: your Instagram bio, your Google Business Profile, a newsletter or a button on your website. Contact support if you need the ID of a service or staff member.

## Where bookings come from

Links from AI assistants and from SimpleSpa emails carry a source tag, such as `utm_source=chatgpt.com` or `utm_source=email`. For bookings made on the new online booking page, SimpleSpa records where each booking came from, for example ChatGPT, Claude, an email link, Google, social media or a direct visit.

You can tag links you share yourself in the same way, for example `?utm_source=instagram`.

## Helping assistants recommend you

* Give services clear names and descriptions: what the service is, who it's for and what's included.
* Turn on **Show Prices** if you're comfortable sharing them. Assistants are often asked about prices.
* Link to your booking URL from your website, Google Business Profile, Bing Places and social profiles, so assistants can find it.
* Keep your opening hours and holidays up to date.

## Related

* [Rebooking Links in Emails](../notifications/rebooking-links-in-emails.md)
* [Your Custom Booking URL](your-custom-booking-url.md)
* [Linking & Embedding Online Booking](linking-and-embedding-online-booking.md)
* [Conversion Tracking](conversion-tracking.md)
