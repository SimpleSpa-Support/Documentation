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
3. Your configuration should be similar to the following:

<figure><img src="https://695085455-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fa9tSKQ7Cexg8YEba5Evb%2Fuploads%2FJwtZGcn1aDoAgGNkPBqm%2FScreenshot%202025-04-29%20at%202.14.39%E2%80%AFAM.png?alt=media&#x26;token=e9d3fe32-6077-45cd-94a1-44d184758e9b" alt=""><figcaption><p>Zapier with the SimpleSpa Appointments API</p></figcaption></figure>

Here is another example that sends a Happy Birthday email to clients who have not visited since April 30th, 2025 and have no future visits scheduled:

1. Select "Webhooks by Zapier" > "Retrieve Poll"

Populate the fields as shown here. Make sure to use your API key.

<figure><img src="https://695085455-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fa9tSKQ7Cexg8YEba5Evb%2Fuploads%2FGF7vjHrtAr6iQJEbddW3%2FScreenshot%202025-04-30%20at%201.06.52%E2%80%AFPM.png?alt=media&#x26;token=53b55afb-0609-4e1f-81e7-cc1c244806bf" alt=""><figcaption><p>Webhook setup by Zapier with the SimpleSpa API</p></figcaption></figure>

2. Add "Email by Zapier"

<figure><img src="https://695085455-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fa9tSKQ7Cexg8YEba5Evb%2Fuploads%2FmmkEq80pzQNNtoGSro9q%2FScreenshot%202025-04-30%20at%201.06.19%E2%80%AFPM.png?alt=media&#x26;token=fe2037e0-a2ea-4cd0-ad5c-dd32fc8535bd" alt=""><figcaption><p>Email by Zapier using the SimpleSpa API</p></figcaption></figure>

Here is a basic HTML template you can use for these campaigns:

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

Test the integration to make sure it works. It will send out an email if your API call returns results.

<figure><img src="https://695085455-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fa9tSKQ7Cexg8YEba5Evb%2Fuploads%2Fh5Ux6yyifumU198bwv64%2FScreenshot%202025-04-30%20at%201.10.41%E2%80%AFPM.png?alt=media&#x26;token=9eb23f6e-cb04-4998-a061-7e3687264cf8" alt=""><figcaption></figcaption></figure>

## Tips

* Use pagination (page and per\_page) to avoid timeouts on large datasets.
* Use the status filter to target only specific types of appointments (e.g., only Confirmed).
* Appointments are sorted by start time ascending.
* It is recommended to use caching and avoid polling the API more frequently than necessary.
* Rate limits are recommended at no more than 1 request per minute to avoid potential throttling.
