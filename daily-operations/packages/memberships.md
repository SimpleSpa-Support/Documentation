---
description: >-
  Create recurring memberships with packages, discounts and a payment profile,
  and manage client memberships.
---

# Memberships

This page explains how to create, sell and manage recurring memberships.

Memberships are available if your account is connected with Stripe. Once your account is connected, a **Memberships** tab appears on the **Packages** page. A membership has two parts:

* The items that are credited (packages and a discount profile)
* The payment profile

## Creating your first Membership <a href="#first-memberships" id="first-memberships"></a>

{% stepper %}
{% step %}
### Add the packages and discount

Assign the packages to credit. Packages are credited each time a payment on this membership succeeds. You can also add a discount, which applies universally based on the discount profile you choose. Discount profiles are created on the **Discounts** page.

<figure><img src="https://695085455-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fa9tSKQ7Cexg8YEba5Evb%2Fuploads%2FtdkdthSPhi010KImIamK%2FScreenshot%202024-07-15%20at%202.27.10%E2%80%AFPM.png?alt=media&#x26;token=faf2c7a4-a558-4c2c-89ee-6bbeeef25e36" alt=""><figcaption><p>The Add Membership prompt after pressing the +Membership button</p></figcaption></figure>
{% endstep %}

{% step %}
### Create the payment profile

Select the membership again (press the ![](https://695085455-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fa9tSKQ7Cexg8YEba5Evb%2Fuploads%2FsVkYSv2n1ZIDDJCx5qWv%2FPencil%20Button%2002.webp?alt=media\&token=0519b972-51ea-4143-ab13-899b82280f8f) button to edit the package), then select the **Payment Profile** tab. Set:

* **Price**: the amount charged each billing period (frequency × interval).
* **Frequency**: how many intervals pass between charges.
* **Interval**: the unit for recurring charges. You can choose Daily, Weekly, Monthly or Yearly.

Examples:

* Price: $10, Frequency: Every 1, Interval: Month(s). The membership charges $10 every 1 month.
* Price: $10, Frequency: Every 6, Interval: Month(s). The membership charges $10 every 6 months.

{% hint style="warning" %}
- Payment profiles can't be edited. To change one, create a new profile.
- Clients subscribed to a payment profile/membership must still be cancelled, even if the profile has been deleted.
{% endhint %}

<figure><img src="https://695085455-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fa9tSKQ7Cexg8YEba5Evb%2Fuploads%2FJ8nR3mhnKJl0CXqMh2SC%2FScreenshot%202024-07-15%20at%202.28.38%E2%80%AFPM.png?alt=media&#x26;token=088ad5c6-5d86-4e8c-b868-055cdb7c0ab4" alt=""><figcaption><p>The Add Payment Profile prompt</p></figcaption></figure>
{% endstep %}
{% endstepper %}

## Selling a Membership <a href="#viewing-client-memberships" id="viewing-client-memberships"></a>

Once you have created a membership, you sell it to clients in the POS, just like any other item in SimpleSpa (services, products, packages, gift certificates).

{% hint style="warning" %}
A common mistake is creating a membership for a single client (for example, "Jane Doe Membership") on the Memberships page. Memberships should be generic, for example:

* **Membership Name:** Monthly 60min Massage
* **Package to use:** Monthly 60min Massage, with an expiration of 1m or 2m so unused credits carry over if not used in the first month
* **Service to use:** 60min Massage
* **Price:** the price the membership is sold for. This overrides the service price and package price; only the membership price is used.
{% endhint %}

## Viewing Clients with Memberships <a href="#viewing-client-memberships" id="viewing-client-memberships"></a>

To see clients with standing memberships, go to the **Clients** page and click the **Clients / Memberships** tab. It lists all clients with standing memberships, and you can pause or cancel any membership there.

You can also view memberships directly in the client profile, and pause or cancel them there if needed.

<figure><img src="https://695085455-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fa9tSKQ7Cexg8YEba5Evb%2Fuploads%2FklL4P1zKklVIdfLrplX8%2FScreenshot%202024-07-15%20at%202.38.40%E2%80%AFPM.png?alt=media&#x26;token=38dc1ac3-0a27-40e5-8c68-a9a722a4c036" alt=""><figcaption><p>The Clients Memberships tab in the Clients page</p></figcaption></figure>

## Pausing or Cancelling a Membership <a href="#pausing-client-memberships" id="pausing-client-memberships"></a>

Find the membership you want to manage in the **Clients / Memberships** tab.

* **Pause:** click the ![](https://695085455-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fa9tSKQ7Cexg8YEba5Evb%2Fuploads%2FSuOokGEqMJCUiScG8lD5%2FPause%20Membership%20Button.webp?alt=media\&token=b750e5d5-72f0-49de-ae95-f1e2c96dd2ca) button. The client is not charged while the membership is paused. When you unpause it, billing resumes on the scheduled billing cycle. If a billing date passed while paused, the next billing cycle is charged when it resumes.
* **Cancel:** click the ![](https://695085455-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fa9tSKQ7Cexg8YEba5Evb%2Fuploads%2FjYZ1PxPNjNWQKPcYZtQ2%2FCancel%20Membership%20Button.webp?alt=media\&token=da56345d-be4a-4d31-af83-9802b07f10f2) button. Cancelled memberships can't be restored and must be sold again in the POS.

## Membership Status in the Client Profile

Each membership in the client profile shows a status and a plain-language billing line, for example when the next payment is due.

| Status               | Meaning                                                     |
| -------------------- | ----------------------------------------------------------- |
| **Active**           | Billing normally.                                           |
| **Paused**           | Billing is paused until you resume it.                      |
| **Ends \[date]**     | Set to end on that date.                                    |
| **Payment failed**   | The last payment didn't go through. Check the card on file. |
| **Trial**            | In a free trial period.                                     |
| **Cancelled**        | No longer active.                                           |
| **Setup incomplete** | Setup wasn't finished, so billing hasn't started.           |

Use **Pause billing** or **Cancel membership** on the membership card.

{% hint style="warning" %}
**Cancel membership** takes effect immediately and can't be undone. To stop billing for a while, use **Pause billing** instead.
{% endhint %}

On the **Clients / Memberships** tab you can filter memberships by status, expand a row to see its payment history from your card processor, and cancel several memberships at once.
