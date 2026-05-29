# Cash Reconciliation

This guide explains how the Reconcile Drawer modal works in SimpleSpa, how expected cash is calculated, and how to interpret the entries.

***

### 📋 Overview

The Cash Drawer Reconciliation feature allows businesses to:

* Open and close their cash drawer
* Track cash amounts at opening and closing
* See how much cash should be on hand based on daily transactions
* Identify cash overages or shortages

***

### 🔄 Drawer Entry Types

Each drawer action is logged as an entry with the following types:

Opening Entry

Closing Entry

### How Expected Cash is Calculated

The system uses the most recent valid opening to determine what the expected cash should be at closing.



Formula:

```
Expected Closing Cash = Opening Amount + Cash Received Today
```

If a closing entry exists after that opening, it will also be displayed for comparison.

***

### 📘 Example Entries



Here’s an example set of entries for a day:

```
[
  { "type": 0, "cash": "100.00", "date": "09:00", "activity_by": "manager" },
  { "type": 1, "cash": "150.00", "date": "15:00", "activity_by": "manager" }
]
```

In this case:

* Opening Cash: $100.00
* Cash Received Today: $50.00
* Expected Closing Cash: $150.00
* Actual Closing Cash: $150.00
* ✅ No difference

***

### 🧾 Modal Breakdown

When the modal opens, you’ll see:

1. Opening Entry — time, amount, notes, and user
2. Closing Entry _(if exists)_ — same details
3. Expected Closing Cash — calculated using today’s transactions
4. Difference — highlights any cash over/short

***

### 🔒 When Is the Drawer Considered Open?

The system considers the drawer _open_ if:

* There is an opening entry
* And no closing entry exists _after_ it

This controls whether the “Close Drawer” tab is enabled.

## Accessing the Reconciliation Modal

<figure><img src="../../.gitbook/assets/Screenshot 2025-06-04 at 4.42.53 PM (1).png" alt=""><figcaption><p>Easily access the reconciliation modal by pressing the cash drawer icon in the Daily Report in the Dashboard</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2025-06-04 at 4.44.03 PM.png" alt=""><figcaption><p>From the prompt you can Open / Close the register with the opening and closing amounts along with any notes</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2025-06-04 at 4.44.08 PM.png" alt=""><figcaption><p>Each entry will be listed above, and if the business has realized any cash revenue this will appear at the bottom showing the total closing amount with the difference</p></figcaption></figure>
