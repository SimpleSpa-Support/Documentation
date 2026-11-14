---
description: >-
  Track online bookings in Google Analytics 4 and Google Ads, and send clients
  to your own thank-you page after they book.
icon: chart-line
---

# Conversion Tracking

SimpleSpa can measure your online bookings in **Google Analytics 4** and **Google Ads** without any code. Set it up in one field: the **URL Redirection** (Website Redirect) field under **Settings → Locations → (your location) → Website Tools**.

That field can hold three things, in any order, separated by spaces:

| What                  | Example                              | What it does                                                              |
| --------------------- | ------------------------------------ | ------------------------------------------------------------------------- |
| Thank-you page        | `https://www.yoursite.com/thank-you` | Sends clients to this page after a completed booking.                     |
| Google Analytics 4    | `G-XXXXXXXXXX`                       | Loads GA4 on your booking pages and records each completed booking.       |
| Google Ads conversion | `AW-123456789/AbCdEfGhIjK`           | Loads the Google tag and reports a conversion for each completed booking. |

All three are optional. Use any combination.

{% hint style="info" %}
Fields saved before this update keep working exactly as before. A field holding only a URL, or only a `G-` ID, behaves the same as it always has.
{% endhint %}

## Set it up

{% stepper %}
{% step %}
### Collect your IDs

* **GA4:** in Google Analytics, open **Admin → Data streams**, choose your web stream and copy the **Measurement ID** (starts with `G-`). See [Google Analytics](../../extras/faq/google-analytics.md) for step-by-step help.
* **Google Ads:** in Google Ads, open **Goals → Conversions**, open your booking conversion, choose **Install the tag yourself** and copy the **conversion ID and label** from the event snippet. You need both, joined with a slash: `AW-123456789/AbCdEfGhIjK`.
{% endstep %}

{% step %}
### Enter them in URL Redirection

Go to **Settings → Locations → (your location) → Website Tools** and find **URL Redirection**. Enter your values separated by a space, for example:

```
https://www.yoursite.com/thank-you G-XXXXXXXXXX AW-123456789/AbCdEfGhIjK
```

Copy the conversion label exactly as Google shows it. Labels are case-sensitive.
{% endstep %}

{% step %}
### Save and test

Save, then make a test booking on your booking page (see [Test your setup](conversion-tracking.md#test-your-setup)). Cancel the test appointment afterwards.
{% endstep %}
{% endstepper %}

{% hint style="warning" %}
**Forms at the end of booking.** If you enter a thank-you page URL, clients are redirected right after booking and won't see their intake forms on the confirmation screen. To keep forms, leave the URL out and enter only your tracking IDs. Tracking IDs on their own never redirect.
{% endhint %}

## What gets tracked

Tracking fires **once per booking**, only after the booking is saved (and after payment, when payment is required). A declined or abandoned payment is never counted.

| Destination        | Event                   | Data sent                                                |
| ------------------ | ----------------------- | -------------------------------------------------------- |
| Google Analytics 4 | `sspa_booking_complete` | Booking total, currency, transaction ID, services booked |
| Google Ads         | `conversion`            | Booking total, currency, transaction ID                  |
| Page `dataLayer`   | `sspa_booking_complete` | Same as above, for your own reporting                    |

* **Value** is the full booking total, not the deposit.
* **Transaction ID** looks like `sspa-12345-12346` (built from the appointment IDs). Google uses it to avoid counting the same booking twice.
* No client personal data (name, email, phone) is sent to Google.

{% hint style="info" %}
Entering an Ads ID **without** a label (`AW-123456789`) loads the Google tag on your booking pages (useful for remarketing audiences) but does **not** report a conversion.
{% endhint %}

## Thank-you page parameters

When you set a thank-you page, SimpleSpa adds booking details to the URL so your own site can read them:

| Parameter                                           | Example                     | Meaning                                  |
| --------------------------------------------------- | --------------------------- | ---------------------------------------- |
| `sspa_evt`                                          | `booking_complete`          | Always `booking_complete`                |
| `sspa_tid`                                          | `sspa-12345-12346`          | Transaction ID (same one sent to Google) |
| `sspa_date` / `sspa_time`                           | `2026-11-20` / `14:30`      | Appointment date and start time          |
| `sspa_services` / `sspa_minutes`                    | `2` / `75`                  | Number of services and total minutes     |
| `sspa_svcs`                                         | `Brow Threading,Full Leg`   | Service names                            |
| `sspa_total` / `sspa_subtotal` / `sspa_tax`         | `85` / `85` / `0`           | Amounts                                  |
| `sspa_currency`                                     | `USD`                       | Currency code                            |
| `sspa_taxmode`                                      | `none`, `added`, `included` | How tax was applied                      |
| `sspa_payreq` / `sspa_depositpct` / `sspa_provider` | `1` / `20` / `stripe`       | Payment settings at booking time         |

Any `utm_*` and `gclid` parameters a client arrived with are kept through the booking flow.

{% hint style="warning" %}
**Avoid counting bookings twice.** If your thank-you page also has a Google Ads conversion tag, either remove it or pass `sspa_tid` as its `transaction_id`, so Google can drop the duplicate.
{% endhint %}

## Cross-domain tracking

When you set a thank-you page on your own website, SimpleSpa automatically adds that domain and your booking page domain to Google's cross-domain linker. For attribution to carry across:

* Install the Google tag on your own website too, with the same IDs.
* Add your booking domain (for example `yourbusiness.simplespa.com`) to the linker settings on your website's Google tag.

## Booking page placement

Tracking works on your booking page, your mini-site and the embedded widget. For the most reliable ad attribution, link ad traffic **directly to your booking page** (or to it from a **Book Now** button) rather than embedding the widget in an iframe on another site. Browsers increasingly limit tracking inside embedded frames. See [Linking & Embedding Online Booking](linking-and-embedding-online-booking.md).

## Test your setup

1. Install **Google Tag Assistant** and connect it to your booking page.
2. Make a test booking.
3. In Tag Assistant, check for one `conversion` hit (Google Ads) and/or one `sspa_booking_complete` event (GA4), each with a value, currency and a transaction ID starting with `sspa-`.
4. If you set a thank-you page, confirm you land on it with `sspa_evt=booking_complete` in the address bar.
5. Cancel the test appointment.

{% hint style="info" %}
Google Ads may take a day or two to update a conversion action's status from "Unverified" after the first conversion arrives.
{% endhint %}

## Frequently asked

<details>

<summary>Can I add Google Tag Manager or a Meta (Facebook) Pixel?</summary>

Custom scripts and Google Tag Manager containers can't be added to SimpleSpa booking pages. These pages handle card payments and personal data, so only the tracking listed above is supported. For Meta Pixel or other tools, set a thank-you page on your own website and fire your events there, using the `sspa_*` parameters for value and transaction ID.

</details>

<details>

<summary>I used to have a G- ID in this field. Do I need to change anything?</summary>

No. It keeps working. You can now add a thank-you page URL and/or a Google Ads conversion alongside it.

</details>

<details>

<summary>What if I enter two URLs?</summary>

Only the first URL is used as the thank-you page.

</details>

<details>

<summary>Is Universal Analytics (UA-) still supported?</summary>

No. Google retired Universal Analytics. Use a GA4 Measurement ID (`G-`) instead.

</details>
