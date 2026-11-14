---
description: >-
  Take a deposit or save a card when clients book online, with Stripe or PayPal,
  for single and multi-service bookings.
---

# Accepting Deposits for Bookings

This page explains how online booking deposits and card capture work.

## Set it up

Go to **Settings → Locations → (your location) → Website Tools**, turn on **require payment** for online bookings and set the deposit as a percentage. Stripe or PayPal must be connected.

## How deposits work

| Deposit setting      | What the client does                  | What you get                                         |
| -------------------- | ------------------------------------- | ---------------------------------------------------- |
| **1% to 99%**        | Pays that share of the booking today. | The deposit, and the rest is due at the appointment. |
| **100%**             | Pays the full booking total.          | The full amount.                                     |
| **0%** (Stripe only) | Saves a card. No charge today.        | A card on file for no-shows or checkout.             |

* The deposit is a percentage of the **total of all services** in the booking, including tax when tax is added on top. Multi-service bookings are supported.
* The client sees the amount due today and the amount remaining before paying.
* With Stripe, the client's card is stored securely, so you won't need to ask for it again at checkout unless they pay another way. See [Cards on File](../../daily-operations/pos/cards-on-file.md).

{% hint style="info" %}
If a deposit is below Stripe's minimum charge, the client's card is saved instead and nothing is charged today.
{% endhint %}

{% hint style="warning" %}
PayPal supports deposits and full payment, but not card capture. With PayPal, a 0% deposit means no payment is required.
{% endhint %}

## Payments are protected

* **Staff are checked before payment.** If every service can't be assigned a staff member at the chosen time, no payment is taken and the client picks another time.
* **Bank verification is safe.** The payment window stays open with a _Please wait, confirming your payment…_ message during 3D Secure or a Link sign-in.
* **Nothing is lost if the page is interrupted.** If the client leaves to approve in their banking app and the page reloads, the booking is finished when they return. If the appointment still couldn't be created, the deposit is recorded and you get an email with the booking details so you can add it or refund.
* **No double charges.** If the chosen time is taken or the connection drops after paying, the client picks a new time and the same payment is reused.

## Apple Pay

SimpleSpa also supports Apple Pay for your business, so your clients can book online even faster and more securely.

## Related

* [Multiple Bookings](multiple-bookings.md)
* [The Online Booking Page](the-online-booking-page.md)
* [Cards on File](../../daily-operations/pos/cards-on-file.md)
* [Balances and Deposits](../../daily-operations/pos/balances-and-deposits.md)
