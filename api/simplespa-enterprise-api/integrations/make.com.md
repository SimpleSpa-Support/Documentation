---
description: Integrate SimpleSpa with Make.com
icon: code
---

# Make.com

## Step-by-Step: Connect SimpleSpa API to Make.com

## Create a new Scenario

* Click “Create a new Scenario”.
* Click the big purple plus (+) to add a module.

## Search for and select “HTTP”

* In the search bar, type “HTTP”.
* Choose HTTP > Make a Request.

## Configure the HTTP Request

Here’s how to fill it:

```json
{
  "birthday_month": 7,
  "page": 1,
  "per_page": 100
}
```

Example API Request: Retrieve Clients with July Birthdays

This API request helps you identify clients with birthdays in July, making it a powerful tool for personalized outreach

<figure><img src="../../../.gitbook/assets/Screenshot 2025-04-30 at 10.36.20 AM.png" alt=""><figcaption></figcaption></figure>

Take this even further and consider adding more variables later on to improve retention, i.e. reaching out to clients that have their upcoming birthday and also haven't visited for while i.e. here is a scenario where the Client has their birthday in July and has not visited prior to 2024-10-30

<figure><img src="../../../.gitbook/assets/Screenshot 2025-04-30 at 10.47.49 AM.png" alt=""><figcaption></figcaption></figure>



## Run Once to Test

* Click Run Once (big button at the bottom).
* Make.com will send the request and show you the response data.

If your API is good, it will say:

* success: true

<figure><img src="../../../.gitbook/assets/Screenshot 2025-04-30 at 10.37.52 AM.png" alt=""><figcaption><p>A successful test API call using Make.com</p></figcaption></figure>

From the Output section, expand Data to review & verify the results&#x20;

## Add More Steps (optional)

Now you can:

* Send the clients to Google Sheets
* Send an email
* Create tasks
* Whatever you want — Make is very flexible.
* Just click the (+) again to add more actions.

## Taking this one step further

Let's do one more step to see how this would work to send an email with a simple Gmail connection

* Select Gmail > Send an Email
* Connect your account
* Populate the following fields
  * To
  * Subject
  * Content

<figure><img src="../../../.gitbook/assets/Screenshot 2025-04-30 at 12.50.50 PM.png" alt=""><figcaption></figcaption></figure>

We have created a simple template for you to edit and paste in the Content section

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
      <h1>Happy Birthday {{1.data.clients[].firstname}} 🎉</h1>
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

Save and then you can "Run Once" to send out the email(s)

<figure><img src="../../../.gitbook/assets/Screenshot 2025-04-30 at 12.53.56 PM.png" alt=""><figcaption><p>This is what the email will look like, you can customize the HTML and set your own look &#x26; feel to it</p></figcaption></figure>

## Important Tips

* Authorization must be exact → Authorization: Bearer YOUR\_API\_KEY
* Body must be valid JSON if you are using POST
*   If you want, you can also switch to GET and pass parameters in URL like:

    https://my.simplespa.com/api/v1/appointments.php?start=2025-04-01\&end=2025-04-30\&page=1\&per\_page=100
* Make will automatically _parse JSON_ for you after the request.
