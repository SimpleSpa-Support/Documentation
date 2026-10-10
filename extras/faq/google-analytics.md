---
description: >-
  Add your Google Analytics Measurement ID to track visits to your SimpleSpa
  online booking page.
---

# Google Analytics

This page shows how to add Google Analytics to your SimpleSpa online booking page and how to find your ID.

## Is Google Analytics supported in the SimpleSpa online booking?

Yes. Add your Google Analytics Measurement ID under **Settings → Locations → (your location) → Website Tools**. In the **Website Redirect** field, enter only the Measurement ID.

{% hint style="warning" %}
Either Google Analytics tracking or a URL redirect will work, but not both.
{% endhint %}

## Find your Measurement ID

### Google Analytics 4 (GA4)

Most accounts today use GA4.

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

### Universal Analytics (Legacy UA)

Google has phased out Universal Analytics, but if you still have an older property, your ID will look like UA-12345678-1.

To find it:

1. Go to **Admin** in Google Analytics.
2. Under the **Property** column, select your UA property (it starts with “UA”).
3. Click **Property Settings**.
4. The Tracking ID is displayed at the top.

Example:

```
UA-12345678-1
```

## Which one do I need?

* ✅ If you see a GA4 ID (G-XXXXXXXXXX), use that.
* ⚠️ If you only have a UA ID (UA-XXXXXX-X), you can still use it, but we recommend upgrading to GA4 for continued support.

***

👉 Once you have your ID, either add it as described above or send it to our team and we’ll connect it to your SimpleSpa booking page.

## Related

* [Linking and embedding online booking](../../reports-and-marketing/online-booking/linking-and-embedding-online-booking.md)
* [Your custom booking URL](../../reports-and-marketing/online-booking/your-custom-booking-url.md)
