---
description: Integrate SimpleSpa with Zapier
icon: code
---

# Zapier

Enterprise users can connect SimpleSpa to over 5,000 other applications using Zapier.

## Example Use Cases

* Add new appointments into Google Sheets automatically
* Trigger emails or SMS when a new appointment is booked
* Sync upcoming appointments into a project management system
* Create CRM leads when appointments are confirmed

## Zapier Example Setup

1. Trigger App: Webhooks by Zapier
2. Trigger Event: Retrieve Poll
3. Your configuration should be similar to the following

<figure><img src="../../../.gitbook/assets/Screenshot 2025-04-29 at 2.14.39 AM.png" alt=""><figcaption><p>Zapier with the SimpleSpa Appointments API</p></figcaption></figure>



Let's do another example here to send a Happy Birthday to clients that may have not visited prior to April 30th, 2025 and have no future visits scheduled:

1. Select "Webhooks by Zapier" > "Retrieve Poll"

Populate the fields as shown here, make sure to use your API Key

<figure><img src="../../../.gitbook/assets/Screenshot 2025-04-30 at 1.06.52 PM.png" alt=""><figcaption><p>Webhook setup by Zapier with the SimpleSpa API</p></figcaption></figure>

2. Add "Email by Zapier"

<figure><img src="../../../.gitbook/assets/Screenshot 2025-04-30 at 1.06.19 PM.png" alt=""><figcaption><p>Email by Zapier using the SimpleSpa API</p></figcaption></figure>

Here is a basic HTML template you can use for these campaigns

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Happy Birthday!</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      margin: 0;
      padding: 0;
      background-color: #f4f6f8;
      color: #333;
    }
    .container {
      max-width: 600px;
      margin: 30px auto;
      background: #fff;
      border-radius: 8px;
      overflow: hidden;
      box-shadow: 0 2px 8px rgba(0,0,0,0.05);
    }
    .hero {
      width: 100%;
      height: auto;
      display: block;
    }
    .content {
      padding: 30px;
      text-align: center;
    }
    h1 {
      color: #e91e63;
      margin-bottom: 10px;
    }
    p {
      font-size: 16px;
      line-height: 1.6;
    }
    a.button {
      display: inline-block;
      margin-top: 20px;
      background-color: #00aaff;
      color: white;
      padding: 12px 24px;
      text-decoration: none;
      border-radius: 5px;
      font-weight: bold;
    }
    .footer {
      font-size: 12px;
      color: #999;
      padding: 20px;
      text-align: center;
    }
  </style>
</head>
<body>

  <div class="container">
    <img src="https://my.simplespa.com/img/promos/AE946880-429E-4966-8FD1-68309AF41053.png" alt="Happy Birthday" class="hero">

    <div class="content">
      <h1>Happy Birthday {{294776830__firstname}} 🎉</h1>
      <p>
        Wishing you a wonderful day filled with love, relaxation, and joy.<br>
        The entire team at <strong>California Spa @SimpleSpa</strong> is celebrating you!
      </p>
      <p>
        Don’t forget to treat yourself—book your special appointment today!
      </p>
      <a href="https://californiaspa.simplespa.com" class="button">Book Now</a>
    </div>

    <div class="footer">
      &copy; <?= date('Y') ?> SimpleSpa. All rights reserved.
    </div>
  </div>

</body>
</html>
```

Test the integration out to see that it works, it will send out an email if you have results in your API call

<figure><img src="../../../.gitbook/assets/Screenshot 2025-04-30 at 1.10.41 PM.png" alt=""><figcaption></figcaption></figure>



* Use pagination (page and per\_page) to avoid timeouts on large datasets.
* Use the status filter to target only specific types of appointments (e.g., only Confirmed).
* Appointments are sorted by start time ascending.
* It is recommended to use caching and avoid polling the API more frequently than necessary.
* Rate limits are recommended at no more than 1 request per minute to avoid potential throttling.
