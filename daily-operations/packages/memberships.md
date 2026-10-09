# Memberships

Memberships are available if your account is connected with Stripe. Once the account is connected to Stripe a new tab will appear in the packages page which will show Memberships. A membership consists of two parts:

* The items which will be credited (packages and discount profile)
* The payment profile

## Creating your first Membership <a href="#first-memberships" id="first-memberships"></a>

* The first step to assign the packages which will be credited (packages are credited upon each successful payment on this membership), optionally a discount can also be added, which applies universally based on the discount profile added (discount profiles are created in the Discounts page)

<figure><img src="https://695085455-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fa9tSKQ7Cexg8YEba5Evb%2Fuploads%2FtdkdthSPhi010KImIamK%2FScreenshot%202024-07-15%20at%202.27.10%E2%80%AFPM.png?alt=media&#x26;token=faf2c7a4-a558-4c2c-89ee-6bbeeef25e36" alt=""><figcaption><p>The Add Membership Prompt after pressing the +Membership button</p></figcaption></figure>

*   The second step is to create a payment profile by selecting the membership again (press the ![](https://695085455-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fa9tSKQ7Cexg8YEba5Evb%2Fuploads%2FsVkYSv2n1ZIDDJCx5qWv%2FPencil%20Button%2002.webp?alt=media\&token=0519b972-51ea-4143-ab13-899b82280f8f) button to edit the package), select the payment profile tab

    * From here the Price (the price that will be paid per frequency x interval period), Frequency (how many intervals will be the payment be charged) and Interval (when should this be charged recurringly)
    * i.e. for a payment profile with a Price: $10 - Frequency: Every 1 - Interval: Month(s) : the membership will be set to charge every 1 month $10.
    * i.e. for a payment profile with a Price: $10 - Frequency: Every 6 - Interval: Month(s) : the membership will be set to charge every 6 months $10.
    * Intervals can be set to Daily, Weekly, Monthly, Yearly
    * Payment Profiles cannot be edited, and a new profile will need to be created
    * Clients that are subscribed to a payment profile/membership will need to be cancelled even if the profile has been deleted

    <figure><img src="https://695085455-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fa9tSKQ7Cexg8YEba5Evb%2Fuploads%2FJ8nR3mhnKJl0CXqMh2SC%2FScreenshot%202024-07-15%20at%202.28.38%E2%80%AFPM.png?alt=media&#x26;token=088ad5c6-5d86-4e8c-b868-055cdb7c0ab4" alt=""><figcaption><p>The Add Payment Profile prompt</p></figcaption></figure>

## Selling a Membership <a href="#viewing-client-memberships" id="viewing-client-memberships"></a>

After you have created a membership, just like any item added in SimpleSpa (services, products, packages, gift certificates) memberships are sold to clients using the POS.

Important: A common mistake is to create a membership with single client information (i.e. Jane Doe Membership) in the memberships page. Memberships should be generic i.e.

* Membership Name: **Monthly 60min Massage**
* Package to use: Monthly 60min Massage with an expiration 1m or 2m so it carries over in case it is not used in the first month
* Service to use: 60min Massage
* Price: this will be the price that this will be sold, this overrides Service price, Package price, only Membership price is used

## Viewing Clients with Memberships <a href="#viewing-client-memberships" id="viewing-client-memberships"></a>

To view clients that have standing memberships, visit the Clients page, and then click on the Clients / Memberships tab which will bring up all clients that have standing memberships, there you can pause and cancel any membership you like.\
Memberships can also be viewed directly in the client profile, and can also be paused/canceled if needed.

<figure><img src="https://695085455-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fa9tSKQ7Cexg8YEba5Evb%2Fuploads%2FklL4P1zKklVIdfLrplX8%2FScreenshot%202024-07-15%20at%202.38.40%E2%80%AFPM.png?alt=media&#x26;token=38dc1ac3-0a27-40e5-8c68-a9a722a4c036" alt=""><figcaption><p>The Clients Memberships tab in the Clients page</p></figcaption></figure>

## Pausing or Cancelling a Membership <a href="#pausing-client-memberships" id="pausing-client-memberships"></a>

To pause or cancel a membership, find the membership that you would to manage in the Clients/Memberships tab and click on the ![](https://695085455-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fa9tSKQ7Cexg8YEba5Evb%2Fuploads%2FSuOokGEqMJCUiScG8lD5%2FPause%20Membership%20Button.webp?alt=media\&token=b750e5d5-72f0-49de-ae95-f1e2c96dd2ca) to pause a membership. Pausing a membership will not charge the client until it has been unpaused and will resume on the scheduled billing cycle. If the billing cycle has passed the following billing cycle will be charged when resumed.\
The ![](https://695085455-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fa9tSKQ7Cexg8YEba5Evb%2Fuploads%2FjYZ1PxPNjNWQKPcYZtQ2%2FCancel%20Membership%20Button.webp?alt=media\&token=da56345d-be4a-4d31-af83-9802b07f10f2) to cancel a membership. Cancelled memberships cannot be restored and will be to be sold again using the POS.

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
