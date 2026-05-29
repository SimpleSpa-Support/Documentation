# Google Analytics

## Is Google Analytics supported in the SimpleSpa online booking?

Yes, you can easily add your Google Analyitcs Measurement ID in the Settings > Locations > selecting your location > Website Tools - and in the Website Redirect please enter only the Measurement ID

### Google Analytics 4 (GA4)

Most accounts today use GA4. Follow these steps:

1. Log in to [Google Analytics](https://analytics.google.com/).
2. Click the Admin (⚙️) icon at the bottom-left.
3. Under the Property column, select your website property.
4. Click Data Streams.
5. Select your Web data stream.
6. In the top-right corner, you’ll see your Measurement ID.

It looks like this:

```
G-XXXXXXXXXX
```

## Universal Analytics (Legacy UA)

Google has phased out Universal Analytics, but if you still have an older property, your ID will look like UA-12345678-1.

To find it:

1. Go to Admin in Google Analytics.
2. Under the Property column, select your UA property (it starts with “UA”).
3. Click Property Settings.
4. The Tracking ID will be displayed at the top.

Example:

```
UA-12345678-1
```

### Which One Do I Need?

* ✅ If you see a GA4 ID (G-XXXXXXXXXX), that’s what you should use.
* ⚠️ If you only have a UA ID (UA-XXXXXX-X), you can still use it, but we recommend upgrading to GA4 for continued support.

***

👉 Once you have your ID, either add it as per the instructions above or send it to our team and we’ll connect it to your SimpleSpa booking page. Note that either Google Analytics tracking or a URL Redirect will work, and not both

