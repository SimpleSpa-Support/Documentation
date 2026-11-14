---
description: >-
  How clients book several services in one online booking, one after the other
  or two at the same time with different staff.
---

# Multiple Bookings

Clients can add several services to one online booking. This page explains how those services are scheduled.

## One after the other (default)

By default, services are booked back to back: the second service starts when the first one ends (including any downtime you've set on the service), and so on.

* If the client picks a **different staff member for each service**, only times that work for every chosen staff member, back to back, are offered.
* If the client chooses **Any staff** for services from different categories, only times where a qualified staff member is free for **each** service, at the time that service takes place, are offered.
* Before any deposit is taken, SimpleSpa checks that every service can be assigned a staff member. If not, no payment is taken and the client picks another time.

## Two services at the same time (beta)

With parallel booking turned on for a location, a client who books two services (for example a manicure and a pedicure) is booked into both at the **same start time with two different staff members**.

| Situation                                   | How it's booked                                                                                                    |
| ------------------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| Two services                                | Both start together, each with a different staff member. Only times when two different staff are free are shown.   |
| Three or more services                      | The first two start together. The rest follow one after the other, starting when the longer of the first two ends. |
| Client picks the same staff member for both | Booked one after the other instead.                                                                                |
| A service that needs two staff (couples)    | The whole booking is one after the other. No more than two staff are booked at the same time.                      |

The cart and the confirmation step tell the client whether services run **at the same time** or **one after another**, with the exact time range once a time is picked. Calendar invites (Google Calendar and .ics) show the correct end time.

{% hint style="info" %}
Parallel booking is off by default. Contact support to turn it on for your location.
{% endhint %}

## Deposits

Deposits work for multi-service bookings and are calculated on the total of all services. See [Accepting Deposits for Bookings](accepting-deposits-for-bookings.md).

## Related

* [The Online Booking Page](the-online-booking-page.md)
* [Accepting Deposits for Bookings](accepting-deposits-for-bookings.md)
* [Does SimpleSpa support parallel bookings?](../../extras/faq/does-simplespa-support-parallel-bookings.md)
* [Fields and Service Settings](../../daily-operations/services/fields-and-service-settings.md)
