# Memberships

Memberships are available if your account is connected with Stripe. Once the account is connected to Stripe a new tab will appear in the packages page which will show Memberships. A membership consists of two parts:

* The items which will be credited (packages and discount profile)
* The payment profile

## Creating your first Membership <a href="#first-memberships" id="first-memberships"></a>

* The first step to assign the packages which will be credited (packages are credited upon each successful payment on this membership), optionally a discount can also be added, which applies universally based on the discount profile added (discount profiles are created in the Discounts page)

<figure><img src="../../.gitbook/assets/Screenshot 2024-07-15 at 2.27.10 PM.png" alt=""><figcaption><p>The Add Membership Prompt after pressing the +Membership button</p></figcaption></figure>

*   The second step is to create a payment profile by selecting the membership again (press the ![](<../../.gitbook/assets/Pencil Button 02.webp>) button to edit the package), select the payment profile tab

    * From here the Price (the price that will be paid per frequency x interval period), Frequency (how many intervals will be the payment be charged) and Interval (when should this be charged recurringly)
    * i.e. for a payment profile with a Price: $10 - Frequency: Every 1 - Interval: Month(s) : the membership will be set to charge every 1 month $10.
    * i.e. for a payment profile with a Price: $10 - Frequency: Every 6 - Interval: Month(s) : the membership will be set to charge every 6 months $10.
    * Intervals can be set to Daily, Weekly, Monthly, Yearly
    * Payment Profiles cannot be edited, and a new profile will need to be created
    * Clients that are subscribed to a payment profile/membership will need to be cancelled even if the profile has been deleted

    <figure><img src="../../.gitbook/assets/Screenshot 2024-07-15 at 2.28.38 PM.png" alt=""><figcaption><p>The Add Payment Profile prompt</p></figcaption></figure>

## Selling a Membership <a href="#viewing-client-memberships" id="viewing-client-memberships"></a>

After you have created a membership, just like any item added in SimpleSpa (services, products, packages, gift certificates) memberships are sold to clients using the POS.&#x20;

Important: A common mistake is to create a membership with single client information (i.e. Jane Doe Membership) in the memberships page. Memberships should be generic i.e.

* Membership Name: **Monthly 60min Massage**
* Package to use: Monthly 60min Massage with an expiration 1m or 2m so it carries over in case it is not used in the first month
* Service to use: 60min Massage
* Price: this will be the price that this will be sold, this overrides Service price,  Package price, only Membership price is used

## Viewing Clients with Memberships <a href="#viewing-client-memberships" id="viewing-client-memberships"></a>

To view clients that have standing memberships, visit the Clients page, and then click on the Clients / Memberships tab which will bring up all clients that have standing memberships, there you can pause and cancel any membership you like.\
Memberships can also be viewed directly in the client profile, and can also be paused/canceled if needed.

<figure><img src="../../.gitbook/assets/Screenshot 2024-07-15 at 2.38.40 PM.png" alt=""><figcaption><p>The Clients Memberships tab in the Clients page</p></figcaption></figure>

## Pausing or Cancelling a Membership <a href="#pausing-client-memberships" id="pausing-client-memberships"></a>

To pause or cancel a membership, find the membership that you would to manage in the Clients/Memberships tab and click on the ![](<../../.gitbook/assets/Pause Membership Button.webp>) to pause a membership. Pausing a membership will not charge the client until it has been unpaused and will resume on the scheduled billing cycle. If the billing cycle has passed the following billing cycle will be charged when resumed.\
The ![](<../../.gitbook/assets/Cancel Membership Button.webp>) to cancel a membership. Cancelled memberships cannot be restored and will be to be sold again using the POS.
