---
description: >-
  Run group classes with online booking, payments or card capture, roster
  management, walk-ins and a Dashboard card.
---

# Classes

SimpleSpa Classes lets you run group sessions — fitness classes, yoga, workshops, group treatments — with online booking, payments, roster management, and dashboard visibility built in.

This page covers the latest additions to the Classes module:

* Online class booking with payments (pay in full or card capture)
* Payment status on the class roster
* Card-on-file badges for attendees
* Walk-in bookings for classes
* Client profile links from the roster
* The Classes card on the Dashboard

***

## Online class booking with payments

Clients booking a class through your online booking portal can now be asked to pay — or to securely save a card — before their seat is confirmed.

### How it works

Class bookings follow a simple **full-or-capture** model. Based on your location's online payment settings, one of three things happens at booking time:

| Payment setting                               | What the client experiences                                                                                            |
| --------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| **Payment required, 100%**                    | The client pays the full class price online before the booking is confirmed.                                           |
| **Payment required, less than 100% (Stripe)** | The client's card is securely saved (no charge today). You can charge it later per your cancellation / no-show policy. |
| **Payment not required**                      | The client reserves a seat with no payment step.                                                                       |

{% hint style="info" %}
**Why no deposits for classes?** Partial deposits on class bookings leave a balance to collect at the front desk for every attendee, every session. To keep check-in fast, classes support only **full payment** or **card capture** — never a partial deposit.
{% endhint %}

### Payment providers

* **Stripe** supports both full payment and card capture (card saved securely with Stripe — card numbers never touch your server).
* **PayPal** supports full payment only. If your location is configured for card capture but only PayPal is connected, class bookings fall back to a free reservation.

### When a booking can't be completed

Payment is always collected **before** the seat is booked. If the booking is then rejected (for example, the last seat was taken while the client was paying), any payment is automatically voided or refunded — the client is never charged for a seat they didn't get.

***

## Class roster: payment status & cards on file

The class roster in your back office (**Appointments → Classes**) now shows you at a glance who has paid, who has a card on file, and who still needs to settle up.

### Payment status chips

Each attendee row displays a payment chip based on how they booked:

* **Paid** — the seat was paid in full online (shows the amount).
* **Card captured** — no charge was made, but a card is securely saved and can be charged per your policy.
* No chip — the seat was reserved without payment (book-and-pay-at-desk).

### Card badge

When an attendee has a card on file, a compact badge appears under their phone number in the roster showing the card brand, last four digits, and expiry (for example, `Visa ***4242 · 12/27`). This works for cards saved during class booking as well as cards already on the client's profile.

### Client profile links

Attendee names in the roster link directly to the client's profile, so you can jump from a class roster to a client's history, cards, and notes in one click. Walk-in entries do not link to a profile.

***

## Walk-in bookings for classes

You can add a walk-in to any class session without creating a client record for them.

* From the class roster, choose **Add walk-in**. No name or contact details are required.
* The seat is registered under the shared walk-in record and displays as **WALKIN** on the roster.
* Walk-ins work the same way here as everywhere else in SimpleSpa (appointments, POS): one shared walk-in record per location, no per-visit names.

{% hint style="warning" %}
Walk-in seats have no payment attached and no client profile. If the person becomes a regular, create a proper client record and book them by name next time.
{% endhint %}

***

## Dashboard: Classes card

The Dashboard now includes a **Classes** card for the selected day.

* The card appears automatically when the day you're viewing has class sessions **with at least one attendee**. Days with no class activity keep the dashboard uncluttered — no empty card is shown.
* Each session shows the class name, time, instructor, and seat counts (booked / capacity).
* Tap a session to expand its roster inline, including each attendee's payment status.
* The card refreshes automatically along with the rest of the dashboard when bookings change — no manual reload needed.

{% hint style="info" %}
The Classes card only appears for locations that have class-type services configured. If you don't use classes, your dashboard is unchanged.
{% endhint %}

***

## Setup checklist

To take payments for class bookings online:

1. **Connect a payment provider** — Stripe (recommended for full flexibility) or PayPal, under your location's payment settings.
2. **Set your online payment mode** for the location:
   * Require payment at **100%** to charge the full class price at booking.
   * Require payment at **less than 100%** (with Stripe) to capture the card only, with no charge today.
   * Leave payment off to allow free seat reservations.
3. That's it — the online booking portal, roster, and dashboard pick up the configuration automatically.

{% hint style="warning" %}
Card capture requires **Stripe**. PayPal cannot save cards for later charging; PayPal-only locations support full payment or free reservation.
{% endhint %}

## Related

* [Accepting Deposits for Bookings](../../reports-and-marketing/online-booking/accepting-deposits-for-bookings.md)
* [Cards on File](../pos/cards-on-file.md)
