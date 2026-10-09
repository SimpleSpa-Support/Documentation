# Check-In Kiosk

The SimpleSpa Check-In Kiosk is a browser-based, touch-friendly page designed to sit on a tablet or shared screen at your front desk. It gives clients two self-service options without requiring staff involvement:

* **Check In** — Clients look up today's appointment by mobile number and tap "I'm here" to notify the front desk.
* **Join Waitlist** — Walk-in clients enter their details, choose a service and preferred provider, and add themselves to the live waitlist.

***

### Setting Up the Kiosk

#### Finding the Kiosk Link & QR Code

Each location has its own unique kiosk URL and QR code. To access them:

1. Go to **Settings → Locations**
2. Click on the location you want to configure
3. Open the **Settings** tab
4. Scroll to the **Check-In** section

From here you can:

* **Copy** the kiosk URL to your clipboard
* **Download** the QR code as a PNG
* **Print** a print-ready version of the QR code

\{% hint style="warning" %\} **Daily token expiry**\
The kiosk link contains a security token that expires at midnight each night. Always generate or display the QR code fresh from the Settings page. Clients who scan an expired QR code will see a "Link unavailable" message. \{% endhint %\}

#### Recommended Setup

Any modern tablet or touchscreen with a browser will work. For best results:

* **Device** — iPad, Android tablet, or Windows touchscreen
* **Browser** — Safari, Chrome, or Edge (latest version)
* **Mounting** — countertop stand or wall-mount at comfortable touch height
* **Kiosk mode** — use Guided Access (iOS) or a kiosk-lock app to prevent clients navigating away
* **Connectivity** — Wi-Fi or wired Ethernet; the kiosk does not require client-side data

#### Opening the Kiosk

1. Open the kiosk URL in the browser on the dedicated tablet
2. The page loads with a live clock, your location name, and two mode tabs
3. Leave the browser open — the page auto-refreshes check-in results and resets the waitlist form after each submission

No staff login is required on the kiosk device. The page is secured by a daily signed token; clients cannot access other locations or admin areas from this page.

***

### Check-In Flow

#### How It Works

1. Client taps the **Check In** tab (active by default)
2. Enters the **mobile number** used when booking
3. Taps **Find appointment**
4. Today's matching appointments appear as cards
5. Client taps **I'm here** on the relevant appointment
6. Confirmation message appears: _"Checked in! A team member will be right with you."_

The appointment status is updated to Checked In in SimpleSpa, and any enabled staff notifications are triggered.

#### Form Requirements

If a client has an outstanding intake form, the **I'm here** button is replaced by a **Complete form** link. The client:

1. Taps the link (opens the form in a new tab)
2. Fills out and submits the form
3. Returns to the kiosk tab

The kiosk checks for completion every 5 seconds and automatically shows the **I'm here** button once all forms are submitted.

#### Error States

| Message                                          | Cause                                        | Action                                         |
| ------------------------------------------------ | -------------------------------------------- | ---------------------------------------------- |
| No appointments found for today.                 | Number not matched, or no appointments today | Client should speak to front desk              |
| This appointment is outside the check-in window. | Appointment is too far in the future or past | Staff can manually check in from the dashboard |
| QR code has expired.                             | Daily token expired past midnight            | Refresh the kiosk URL from Settings            |
| Too many attempts.                               | Rate limit reached                           | Client should speak to front desk              |

***

### Waitlist Flow

#### Step 1 — Client Lookup

The client enters their **mobile number** or **email address** and taps Continue.

* **Found** — A masked confirmation card is shown (e.g. "••• 6789") and the client confirms their identity.
* **Not found** — The client is taken to the Create Profile step to register.

#### Step 2 — Confirm or Register

**Existing client:** The client sees their name and masked contact details. They tap **Yes, that's me** to continue, or **Back** to re-enter their details.

**New client:** A registration form is shown. First name is required; at least one of mobile or email is required. Tapping **Create profile & continue** creates the client record in SimpleSpa and advances to service selection.

#### Step 3 — Service Selection

The client sees a searchable list of active services grouped by category. Tapping a service auto-advances to staff selection.

Only services that are **active** and **available online** are shown. Services hidden for this location via the category hide list are excluded.

\{% hint style="info" %\} **Shared-mode businesses**\
If your business has multiple locations sharing a service catalogue, the service list always shows services for the specific location this kiosk is configured for. Client records are searched across all locations under your business for lookup purposes. \{% endhint %\}

#### Step 4 — Staff Selection

The client sees a grid of available staff filtered to those who perform the selected service category. If no staff match the category, all active staff are shown as a fallback.

The client taps a staff card then taps **Add me to the waitlist**.

#### Confirmation & Auto-Reset

On success the client sees:

* Their queue position (e.g. "#2 of 4 today")
* A summary of the service and provider chosen
* A 20-second countdown after which the kiosk resets automatically for the next client
* A **Start over now** button to reset immediately

The waitlist entry appears instantly in the SimpleSpa Waitlist view for this location.

***

### Troubleshooting

#### "Link unavailable" Error Screen

| Message                                   | Cause                                          | Fix                                                  |
| ----------------------------------------- | ---------------------------------------------- | ---------------------------------------------------- |
| We couldn't find a location in this link. | The location parameter is missing from the URL | Re-copy the URL from Settings → Locations → Check-In |
| This QR code has expired.                 | Daily token is from a previous day             | Reload the kiosk URL from the Settings page          |
| This link may be expired or incorrect.    | Invalid location ID or malformed token         | Re-copy the URL; contact support if it persists      |

#### Services Not Showing on Waitlist

* Confirm the service is marked **active** in Settings → Services
* Confirm **Available online** is enabled on the service
* Confirm the service type is **Standard** (not Package or Add-on)
* Check the service category is not hidden for this location

#### Client Not Found on Lookup

* The client may be registered under a different mobile or email address
* For shared-mode businesses, the search spans all locations — try an alternative contact detail
* If the client is new, the Create Profile step will register them on the spot

#### Check-In Not Updating the Dashboard

* Confirm the kiosk URL is for the correct location
* Check the appointment is scheduled for today
* If forms are pending the **I'm here** button will not appear until they are completed
* Staff can manually update the appointment status from the SimpleSpa dashboard
