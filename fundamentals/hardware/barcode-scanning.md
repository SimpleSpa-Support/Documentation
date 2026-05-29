# Barcode Scanning

## Barcode Scanning (Point of Sale)

SimpleSpa’s Point of Sale includes built-in barcode scanning for fast product lookup. Use the Scan button in the search bar to connect your device's camera.

The scanner uses the device’s native camera (phone, tablet, or laptop) and does not require any special hardware to get started.

This makes it easy to scan retail products, gift cards, or internal labels directly from the POS.

***

### How Barcode Scanning Works

* The POS activates your device’s camera when you tap the barcode scan icon
* Point the camera at the barcode or QR code
* Once detected, the code is automatically entered and used for product search
* The scanner closes automatically after a successful scan

No pairing, drivers, or configuration required.

***

### Supported Devices

Barcode scanning works on:

* iOS devices (iPhone / iPad)
* Android phones and tablets
* Laptops and desktops with a camera
* USB handheld barcode scanners that emulate keyboard input

For best results, we recommend:

* A rear (back-facing) camera on mobile devices
* Good lighting and a clearly printed barcode

***

### Smart Camera Selection (Mac & Desktop)

On desktop and laptop computers, SimpleSpa automatically chooses the best available camera for scanning:

* If a built-in or connected camera is available, it will be used
* If no usable camera is detected on a Mac or desktop, you can scan using your phone instead
* Simply open the POS on your phone and scan the barcode using the phone’s camera

This makes barcode scanning seamless even on desktop setups without a dedicated camera.

> 💡 Many merchants run the POS on a Mac or desktop computer and use a phone as a quick, handheld scanner — no extra hardware required.

***

#### Recommended Workflow (Desktop + Phone)

1. Run the POS on your Mac or desktop
2. Keep a phone nearby (iOS or Android)
3. When scanning is needed, open the POS on the phone
4. Scan the product barcode using the phone’s camera
5. Continue checkout on the main POS screen

This setup works especially well at busy counters and front desks.

***

### Supported Barcode & QR Code Formats

SimpleSpa supports the most common retail and inventory barcode standards:

#### 2D Codes

*   QR Code

    Used for digital gift cards, vouchers, and mobile-based codes

#### 1D Barcodes

* UPC-A – Standard retail barcode (US & Canada)
* UPC-E – Compact UPC used on small retail items
* EAN-13 – International retail barcode
* EAN-8 – Shortened EAN for small packages
* Code 128 – High-density barcode for products and inventory
* Code 39 – Common for internal labels and membership cards
* ITF / ITF-14 – Used for cartons and case packaging

\
Most retail products sold in salons, spas, and clinics are supported out of the box.

***

### Product Lookup with Barcodes

When a barcode is scanned in the POS:

1. The scanned value is read by the camera
2. SimpleSpa searches for a matching product barcode
3. If found, the product is added or highlighted in the POS
4. If no match is found, you can manually create or update the product with that barcode

This allows fast checkout and accurate inventory tracking.

***

### Camera & Privacy Notes

* Camera access is only used while scanning
* No images or video are stored
* Scanning runs entirely in the browser using modern HTML5 standards

***

### Troubleshooting

Barcode won’t scan?

* Make sure the barcode is not damaged or blurry
* Improve lighting conditions
* Hold the camera steady and centered
* Try a different angle or distance

No camera detected?

* Ensure camera permissions are allowed in your browser
* Try a different browser (Chrome or Safari recommended)
* On desktops, verify a camera is connected

***

### Technical Notes (For Advanced Users)

* Scanning is powered by the HTML5 QR Code library
* The system prefers the environment (rear) camera when available
* Barcode detection uses native browser capabilities when supported for better accuracy

No additional plugins or na~~t~~ive apps are required.
