---
description: >-
  Add your Google Analytics Measurement ID to track visits and bookings on your
  SimpleSpa online booking page.
---

# Google Analytics

This page shows how to add Google Analytics to your SimpleSpa online booking page and how to find your ID.

## Is Google Analytics supported in the SimpleSpa online booking?

Yes. Add your Google Analytics Measurement ID under **Settings → Locations → (your location) → Website Tools**, in the **URL Redirection** (Website Redirect) field.

The same field can also hold a thank-you page URL and a Google Ads conversion, separated by spaces, for example:

```
https://www.yoursite.com/thank-you G-XXXXXXXXXX
```

Each completed booking is recorded in GA4 as an `sspa_booking_complete` event with its value. See [Conversion Tracking](../../reports-and-marketing/online-booking/conversion-tracking.md) for the full setup, including Google Ads.

## Find your Measurement ID

### Google Analytics 4 (GA4)

{% stepper %}
{% step %}
### Log in

Log in to [Google Analytics](https://analytics.google.com/).
{% endstep %}

{% step %}
### Open Admin

Click the **Admin** (⚙️) icon at the bottom left.
{% endstep %}

{% step %}
### Select your property

Under the **Property** column, select your website property.
{% endstep %}

{% step %}
### Open your data stream

Click **Data Streams**, then select your **Web** data stream.
{% endstep %}

{% step %}
### Copy the Measurement ID

Your Measurement ID appears in the top-right corner.
{% endstep %}
{% endstepper %}

It looks like this:

```
G-XXXXXXXXXX
```

{% hint style="warning" %}
**Universal Analytics (UA-) is no longer supported.** Google retired Universal Analytics, so IDs that look like `UA-12345678-1` are ignored. Use your GA4 Measurement ID (`G-`) instead.
{% endhint %}

***

👉 Once you have your ID, either add it as described above or send it to our team and we'll connect it to your SimpleSpa booking page.

## Related

* [Conversion Tracking](../../reports-and-marketing/online-booking/conversion-tracking.md)
* [Linking and embedding online booking](../../reports-and-marketing/online-booking/linking-and-embedding-online-booking.md)
* [Your custom booking URL](../../reports-and-marketing/online-booking/your-custom-booking-url.md)
