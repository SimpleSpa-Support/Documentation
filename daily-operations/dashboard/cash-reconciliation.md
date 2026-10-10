---
description: >-
  How the Reconcile Drawer modal works, how expected cash is calculated, and how
  to read drawer entries.
---

# Cash Reconciliation

This guide explains how the **Reconcile Drawer** modal works in SimpleSpa, how expected cash is calculated, and how to read the entries.

***

## 📋 Overview

Cash drawer reconciliation lets you:

* Open and close your cash drawer
* Track cash amounts at opening and closing
* See how much cash should be on hand based on the day's transactions
* Identify cash overages or shortages

***

## 🔄 Drawer entry types

Each drawer action is logged as an entry. There are two entry types:

* **Opening Entry**
* **Closing Entry**

## How expected cash is calculated

SimpleSpa uses the most recent valid opening entry to work out how much cash you should have at closing.

Formula:

```
Expected Closing Cash = Opening Amount + Cash Received Today
```

If a closing entry exists after that opening, it is also displayed for comparison.

***

## 📘 Example entries

Here’s an example set of entries for one day:

```
[
  { "type": 0, "cash": "100.00", "date": "09:00", "activity_by": "manager" },
  { "type": 1, "cash": "150.00", "date": "15:00", "activity_by": "manager" }
]
```

In this example:

* Opening Cash: $100.00
* Cash Received Today: $50.00
* Expected Closing Cash: $150.00
* Actual Closing Cash: $150.00
* ✅ No difference

***

## 🧾 What the modal shows

When the modal opens, you’ll see:

1. **Opening Entry** — time, amount, notes, and user
2. **Closing Entry** _(if one exists)_ — the same details
3. **Expected Closing Cash** — calculated from today’s transactions
4. **Difference** — highlights any cash over or short

***

## 🔒 When is the drawer considered open?

SimpleSpa considers the drawer _open_ if:

* There is an opening entry, and
* No closing entry exists _after_ it

This controls whether the **Close Drawer** tab is enabled.

## Accessing the Reconciliation Modal

<figure><img src="https://695085455-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fa9tSKQ7Cexg8YEba5Evb%2Fuploads%2FT08pPFmKSBjYo0kJfGOW%2FScreenshot%202025-06-04%20at%204.42.53%E2%80%AFPM.png?alt=media&#x26;token=d83dd6fc-a31f-43be-9011-6990097d9a2d" alt=""><figcaption><p>Open the reconciliation modal by clicking the cash drawer icon in the Daily Report on the Dashboard</p></figcaption></figure>

<figure><img src="https://695085455-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fa9tSKQ7Cexg8YEba5Evb%2Fuploads%2FOf5vT5R4hBh0gnrO4ka1%2FScreenshot%202025-06-04%20at%204.44.03%E2%80%AFPM.png?alt=media&#x26;token=cc244d70-eb07-4ecc-b499-4625e6bcf673" alt=""><figcaption><p>From the prompt you can open or close the register with the opening and closing amounts, along with any notes</p></figcaption></figure>

<figure><img src="https://695085455-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2Fa9tSKQ7Cexg8YEba5Evb%2Fuploads%2FYJcnr1rw0kcFZVHaPvh0%2FScreenshot%202025-06-04%20at%204.44.08%E2%80%AFPM.png?alt=media&#x26;token=a31c57be-7ea9-41fa-afc5-ece67867438a" alt=""><figcaption><p>Each entry is listed above. If the business has any cash revenue, it appears at the bottom with the total closing amount and the difference.</p></figcaption></figure>

## Related

* [Viewing Transactions](viewing-transactions.md)
* [Cash drawer / Till](../hardware/cash-drawer-till.md)
