---
description: >-
  Browser print settings for receipt printers in Firefox, Chrome, and Safari,
  plus AirPrint notes.
---

# Receipt Printer Setup

This page explains how to set up your browser's print settings so receipts print cleanly on a receipt printer.

When printing with SimpleSpa, remove the headers and footers so your receipts are more compact.

## Mozilla Firefox

1. Open Firefox.
2. Go to **File → Page Setup**.
3. Click the three-line icon in the upper right and select **Print**.
4. On the Print Preview page, select **Page Setup** in the upper left.
5. On the **Format & Options** tab, make sure **Shrink to fit page width** is checked.
6. Select the **Margins & Header/Footer** tab.
7. Set the Top, Right, Left, and Bottom margins to "0.2".
8. Set all Headers & Footers to "--blank--".
9. Click **OK** to save.

## Google Chrome

1. Open Chrome.
2. Select the receipt to print and click the print button or **Print Receipt**.
3. Make sure your receipt printer is selected in **Destination**.
4. Set **Paper size** to the custom roll size, for example 58x297mm / 72mm x Receipt (or 72mm x 2000mm on Mac).
5. Set **Margins** to **Minimum**.
6. Set **Scale** to 100.
7. Under **Options**, uncheck **Headers and footers**.
8. Under **Options**, uncheck **Background graphics**.
9. Click **Print** at the top to test the printout.

## Apple Safari

1. Open Safari.
2. Go to https://my.simplespa.com
3. Click the **Make a Sale** button and make a sale. Once it's completed and saved, click **Print Receipt**.
4. The print prompt opens.
5. Under **Paper Size**, select **Manage Custom Sizes**:
   * Click **+** to create a custom size. Double-click it to rename it, and enter "Receipt".
   * Paper Size Width: 72mm or 2.8 inches
   * Paper Size Height: 100mm or 4 inches
   * Margin Top: 0
   * Margin Left: 0
   * Margin Right: 0
   * Margin Bottom: 0
6. Click **OK**.
7. Make sure **Print backgrounds** and **Print headers and footers** are unchecked.
8. Make sure the new custom size "Receipt" is selected in **Paper Size**.
9. At the top, under **Presets**, select **Save Current Settings as Preset…**:
   * Preset Name: "Receipt"
   * Set the preset to be available for only this printer.
10. Click **Print** to print your first receipt and check that it printed correctly.

## AirPrint

SimpleSpa can print using AirPrint. We have tested various POS printers successfully on iOS. We recommend that you always test a device before purchasing it.

{% hint style="info" %}
To enable AirPrint on a legacy printer, the printer must always be connected to a Mac running as a server. You will also need to install third-party software, such as handyPrint, to enable AirPrint.
{% endhint %}

## Related

* [Thermal Receipt](thermal-receipt.md)
* [Cash drawer / Till](cash-drawer-till.md)
