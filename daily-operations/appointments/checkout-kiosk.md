---
description: >-
  Use a counter iPad as a client-facing screen that shows the cart, collects
  tips and accepts QR code payments.
---

# Checkout Kiosk

The Client Checkout Kiosk turns a counter iPad into a client-facing checkout companion. When a sale is started on the POS, the kiosk automatically displays the client's cart, lets them add a tip, and can accept payment by QR code — without staff ever handing over their device.

***

## Overview

| Feature             | Details                                                                |
| ------------------- | ---------------------------------------------------------------------- |
| **Device**          | Any iPad or tablet running Safari or Chrome                            |
| **Connection**      | Same network as the POS (LAN or Wi-Fi)                                 |
| **Payment methods** | Stripe QR code (card, Afterpay, Klarna, Affirm), terminal, cash, check |
| **Tip collection**  | 15%, 20%, 25%, custom amount, or no tip                                |
| **Requires**        | Stripe payments enabled for the location                               |

***

## How it works

The kiosk and the POS stay in sync through a lightweight server relay (`kiosk_sync`). The POS writes cart state to the server every time the cart changes; the kiosk reads it every 1.5 seconds and updates its display automatically.

```
POS staff adds items → kiosk shows cart
Client selects tip   → POS updates in real time
Staff initiates payment → kiosk shows QR or "Ready to pay" screen
Payment confirmed    → kiosk shows Thank You, resets to idle
```

No pairing, Bluetooth or app install is required on the client's side.

***

## Setup

### 1. Enable the kiosk for your location

The kiosk is enabled per location by your SimpleSpa account manager. Once enabled, a **Kiosk** icon (tablet icon) appears in the top navigation bar of the Dashboard.

### 2. Open the Kiosk Admin panel

Click the **Kiosk** icon in the top navigation bar to open the Kiosk Admin panel.

The panel shows:

* The **Kiosk URL** — the unique link for your counter iPad
* A **QR code** you can scan directly with the iPad camera
* The **IP lock status** — which device is currently locked to this URL
* Admin controls for resetting or regenerating the URL

### 3. Open the URL on your counter iPad

On your counter iPad, open Safari and navigate to the Kiosk URL shown in the admin panel, or scan the QR code displayed there.

{% hint style="success" %}
**Tip:** Add the kiosk to the iPad home screen for a fullscreen, app-like experience. In Safari, tap **Share → Add to Home Screen**.
{% endhint %}

On first load, the kiosk locks itself to the iPad's IP address. After that, visits from any other device on a different IP are silently blocked. This prevents clients from accidentally accessing the kiosk URL from their own phones.

### 4. Run a test transaction

1. Open the POS on the staff device and add a client and service to the cart.
2. The kiosk should automatically transition from the idle screen to the cart screen, showing the client's name and items.
3. The client can select a tip on the kiosk. The tip amount syncs to the POS in real time.
4. Process payment as normal from the POS.

***

## Kiosk screens

### Idle

Displays your business name and logo. Shows when no sale is in progress. The kiosk resets to this screen automatically after each completed checkout.

### Cart

Shows the client's items, subtotal, tax, and total. If the cart contains tippable services, a tip panel appears with three preset percentages (15%, 20%, 25%), a "No tip" option, and an "Other amount" field for a custom tip.

### Processing

Shown when a terminal or cash payment is initiated by staff. Displays a context-appropriate message:

* **Terminal:** "Ready to pay — tap, insert or swipe your card on the reader"
* **Cash/other:** "Your payment is being processed by staff"

### QR payment

Shown when staff start a Stripe QR payment. Displays a QR code that the client scans with their phone camera to pay. Includes a countdown timer and a **Cancel** button.

### Thank you

Shown for 5 seconds after payment is confirmed. Displays the total charged, then resets to idle automatically.

***

## Tip sync

The kiosk tip panel pushes the client's selection back to the POS in real time. Staff can see the tip amount update in the POS tip field as the client makes their choice.

**Rules:**

* If a staff member has manually typed a tip in the POS, the kiosk cannot overwrite it.
* If the tip was set by the kiosk, the client can change their selection freely and the POS will update each time.
* The tip is reset to zero if the client cancels a QR payment, so they can choose again on the next attempt.

{% hint style="info" %}
**Important:** The tip is included in the total amount the POS passes to Stripe. The kiosk does not add the tip a second time — it displays the tip for the client's reference only.
{% endhint %}

***

## Canceling a payment

The client can tap **Cancel** on both the QR screen and the Processing screen. Canceling:

1. Notifies the server immediately to reset the checkout state.
2. Returns the kiosk to the cart screen, showing the client's items.
3. Resets the tip selection to zero.
4. Lets staff retry with a different payment method.

***

## Admin controls

These controls are in the Kiosk Admin panel (tap the Kiosk icon in the top navigation bar). They are intended for owners only.

| Control           | When to use                                                                                                                  |
| ----------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| **Reset IP Lock** | The iPad was replaced, moved to a different network, or the IP changed and the kiosk is now blocked                          |
| **New URL**       | The kiosk URL was accidentally shared or you want to invalidate the old link immediately — the old URL stops working at once |

After you generate a **New URL**, open the new URL again on the counter iPad.

***

## Frequently asked questions

**Can the client pay directly from the kiosk without staff involvement?**\
Not currently. Payment is always initiated from the POS by staff. The kiosk handles tip selection and displays the payment screen, but the charge is triggered from the staff device.

**Does the kiosk work offline?**\
No. The kiosk requires a live connection to the SimpleSpa server to poll for cart updates. It will show the idle screen if the connection is lost.

**Can I use the kiosk on an Android tablet or a desktop browser?**\
Yes. The kiosk URL works in any modern browser. The fullscreen prompt uses the standard browser fullscreen API, which is supported on Android Chrome and desktop browsers. Safari on iPad supports "Add to Home Screen" for the best fullscreen experience.

**Can two locations share one kiosk iPad?**\
No. Each kiosk URL is tied to a single location ID and is IP-locked to the first device that opens it. Each location needs its own iPad and its own URL.

**What happens if staff close the POS mid-sale?**\
When the POS modal is closed without completing a payment, the server is notified and the kiosk returns to the idle screen automatically.

**The kiosk is stuck on a payment screen after a canceled sale. What do I do?**\
This should resolve automatically within 2 seconds as the kiosk polls for updated state. If it persists, tap **Cancel** on the kiosk screen. If the Cancel button is not visible, refreshing the kiosk page in Safari will reset it to idle.

## Related

* [Check-In Kiosk](check-in-kiosk.md)
* [Prompting and Collecting Tips](../pos/common-checkouts-and-tutorial-walkthroughs/prompting-and-collecting-tips.md)
* [Processing Credit Cards](../pos/processing-credit-cards.md)
