---
description: Fields and Settings available per Product
---

# Product Fields and Settings

This page describes the fields and settings you can customize for each product.

## Name

The product name that you and your clients refer to.

## Category

The category this product belongs to. Click it to select a different category from the dropdown.

## SKU/Barcode

Enter the barcode or SKU for this product.

## Description

This is the retail price for the product.

## Retail

The retail price for the product.

## Special

If the product has a special price, set it here. The Online Booking page and the POS will show that this is a special-priced item.

## Tax Rate

Each product can have its own tax rate. Tax is calculated based on your location's tax type (Sales Tax or VAT), found in **Settings → Locations → (your location) → Payments & Tax Rates → Tax Type**.

## Enable Commissions

Turn this on to allocate commissions to your staff for this product.

{% hint style="info" %}
Commissions are only recorded for transactions made after you turn this setting on. If commissions were turned off for a period, no commissions are recorded for that period, and none are recorded until you turn the setting back on.
{% endhint %}

## Show Online

Turn this on to make the product available online, or off to hide it online. Products are available online only if your account is connected with Stripe.

## Inventory

Choose whether inventory is recorded (on) or not recorded (off). When you make a sale in the POS, the units sold are deducted from your existing inventory.

{% hint style="warning" %}
When inventory reaches 0, the product shows a warning that no inventory remains. If you bypass the warning and complete the sale, no further inventory is deducted. Inventory stays at 0 and does not go negative.
{% endhint %}

## Inventory Purchases

If **Inventory** is on, you can see the inventory purchases for a product. Open the product's edit prompt and go to the **Inventory Purchases** tab. These are transactions made within your business to add or remove inventory. They are not retail sales made in the POS.

<figure><img src="https://695085455-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fa9tSKQ7Cexg8YEba5Evb%2Fuploads%2F5mQyRRItx93ZwGwrAyhu%2FScreenshot%202024-07-13%20at%205.39.29%E2%80%AFPM.png?alt=media&#x26;token=d9eeda78-ce7f-4701-b05e-6f93890f1fe0" alt=""><figcaption></figcaption></figure>

## Related

* [Managing Products](managing-products.md)
* [Assign Tax Rate to all Products](assign-a-tax-rate-to-all-products.md)
* [Inventory](inventory.md)
