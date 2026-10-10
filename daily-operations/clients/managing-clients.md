---
description: >-
  Add and edit clients, save a credit card on file, and merge duplicate client
  profiles.
---

# Managing Clients

This page shows you how to add and edit clients, save a credit card on file, and merge duplicate client profiles.

## Adding Clients

To add a client, click the **+Client** button on the **Clients** page. This opens the **Add Client** prompt.

<figure><img src="https://695085455-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fa9tSKQ7Cexg8YEba5Evb%2Fuploads%2FwfiWHulaT1pkkI4a6Ryr%2FScreenshot%202024-07-10%20at%2011.53.38%E2%80%AFPM.png?alt=media&#x26;token=b21a3e98-10c9-4ab5-af4c-3321e17d0fbc" alt=""><figcaption><p>The Add Client button on the Clients page</p></figcaption></figure>

<figure><img src="https://695085455-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fa9tSKQ7Cexg8YEba5Evb%2Fuploads%2Ft6zpChfQcPBWwL7bmKx3%2FScreenshot%202024-07-10%20at%2011.54.34%E2%80%AFPM.png?alt=media&#x26;token=de2f7c80-948e-4f8b-93e5-1f559d4c6af2" alt=""><figcaption><p>The Add Client prompt</p></figcaption></figure>

The **Add Client** prompt has many input fields. Use the **Check Duplicate** button to quickly check whether a client with the information you entered already exists.

## Editing Clients

To edit a client, click the pencil button on the right side of that client's row in the client table.

<figure><img src="https://695085455-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fa9tSKQ7Cexg8YEba5Evb%2Fuploads%2FjuZV54nxgWLzS5aSypGn%2FScreenshot%202024-07-10%20at%2011.57.18%E2%80%AFPM.png?alt=media&#x26;token=3c726755-47e8-45ff-9d21-11a262e831ef" alt=""><figcaption><p>The Edit Client button</p></figcaption></figure>

<figure><img src="https://695085455-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fa9tSKQ7Cexg8YEba5Evb%2Fuploads%2FqKkNhZ7pOksmsUm7oMhS%2FScreenshot%202024-07-11%20at%2012.03.20%E2%80%AFAM.png?alt=media&#x26;token=0d1baa8d-1244-49b4-bf4a-38dd40cc3170" alt=""><figcaption><p>The Edit Client prompt and the available fields</p></figcaption></figure>

## Adding a Credit Card

To save a credit card on file, your account must first be connected to Stripe.

{% stepper %}
{% step %}
### Open your payment settings

Go to **Settings → Locations → (your location) → Payments & Tax Rates**.
{% endstep %}

{% step %}
### Connect with Stripe

Scroll to the bottom of the tab and connect with Stripe. Once connected, you can capture credit cards in SimpleSpa using your Stripe account.
{% endstep %}

{% step %}
### Add the card from the client

Edit the client and add the card in the **Add Credit Card** prompt.

<figure><img src="https://695085455-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fa9tSKQ7Cexg8YEba5Evb%2Fuploads%2FXsw9EjaRAL0Vn35i5T87%2FScreenshot%202024-07-11%20at%2012.16.21%E2%80%AFAM.png?alt=media&#x26;token=4c3d4b69-8334-40af-9cc9-ac6fa9484049" alt=""><figcaption><p>The Add Credit Card prompt in Edit Client</p></figcaption></figure>

<figure><img src="https://695085455-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fa9tSKQ7Cexg8YEba5Evb%2Fuploads%2FUpGt8yIlv8TqORYE42r5%2FScreenshot%202024-07-11%20at%2012.16.34%E2%80%AFAM.png?alt=media&#x26;token=9ca2d962-4837-401d-b206-f2167b5a2094" alt=""><figcaption><p>A captured card and the available options in the Edit Client tab</p></figcaption></figure>
{% endstep %}
{% endstepper %}

## Merging

Client merging is run automatically by a job every 24 hours. You submit the merge from the **Clients** page, and the job completes it.

{% stepper %}
{% step %}
### Open the Clients page

Go to the **Clients** page.
{% endstep %}

{% step %}
### Click Merge

In the list controls, click the **Merge** button.

<figure><img src="https://695085455-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fa9tSKQ7Cexg8YEba5Evb%2Fuploads%2Foiw1PboqEowWBZQnjFhz%2FScreenshot%202024-07-10%20at%203.21.23%E2%80%AFPM.png?alt=media&#x26;token=0c92912e-e5b3-446f-aef3-1174607cd863" alt=""><figcaption><p>The Merge button on the Clients page</p></figcaption></figure>
{% endstep %}

{% step %}
### Follow the instructions

Follow the instructions that appear so the client profiles merge successfully.

<figure><img src="https://695085455-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fa9tSKQ7Cexg8YEba5Evb%2Fuploads%2FtqdEu6VtIDBg1TNw9ufU%2FScreenshot%202024-07-10%20at%203.21.45%E2%80%AFPM.png?alt=media&#x26;token=47f4b23a-a790-4b78-8581-01c85006e142" alt=""><figcaption><p>The Merge prompt with instructions on how to merge</p></figcaption></figure>
{% endstep %}
{% endstepper %}

To merge, the client profiles must match on:

1. First name and last name
2. Mobile number

{% hint style="info" %}
The older profile becomes the primary profile. If both profiles have notes, we recommend copying those notes over to both profiles.
{% endhint %}

## Related

* [Cards on File](../pos/cards-on-file.md)
* [Processing Credit Cards](../pos/processing-credit-cards.md)
