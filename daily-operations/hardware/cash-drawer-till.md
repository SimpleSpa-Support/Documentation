---
description: >-
  Using a printer-connected cash drawer with SimpleSpa, including setup steps
  for Star TSP100/TSP113/TSP143 printers.
---

# Cash drawer / Till

This page explains how a cash drawer works with SimpleSpa and how to set one up with a Star TSP100-series printer.

SimpleSpa works with a cash drawer that connects to your receipt printer and pops open when a receipt is sent to print. Check with your hardware vendor that your cash drawer works this way.

## Set up a cash drawer for Star TSP100 / TSP 113 / TSP143 printers

You can connect a cash drawer to your Star TSP100/TSP113/TSP143 printer and have the printer open the drawer whenever a receipt prints.

{% stepper %}
{% step %}
### Connect the cash drawer to the printer

Plug the connector cable from the cash drawer (the one that looks like a phone line) into the receipt printer.
{% endstep %}

{% step %}
### Connect the printer to your computer

Connect the printer to the computer via USB.
{% endstep %}

{% step %}
### Open the printer properties

Open the **Control Panel** and select **Devices and Printers**. Right-click your Star TSP100/TSP113/TSP143 printer and select **Properties**.
{% endstep %}

{% step %}
### Set the peripheral options

Click the **Device Settings** tab, then:

* Under **Peripheral Unit Type**, select **Cash Drawer**.
* Under **Peripheral Unit 1**, select **Document Top**.
{% endstep %}

{% step %}
### Save and test

Click **OK** to finish. Print a test page from the printer to check that the drawer opens.
{% endstep %}
{% endstepper %}

## Related

* [POS Terminal](https://www.simplespa.com/documentation/hardware/#pos-terminal)
* [Receipt Printer Setup](receipt-printer-setup.md)
* [Cash Reconciliation](../dashboard/cash-reconciliation.md)
