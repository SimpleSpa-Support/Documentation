---
description: >-
  Turn every booking into a professional virtual consultation experience: no
  separate scheduling tools, no confusion for clients, and everything sits right
  with your appointment.
---

# Zoom Meetings

This page explains how to connect Zoom to SimpleSpa, add a Zoom meeting to an appointment, and disconnect Zoom.

## Benefits

* **Instant virtual meeting link** — With one click, you get a secure Zoom link for your appointment, saving you time and manual coordination.
* **Instant virtual meeting creation** — Add a Zoom meeting to any appointment with a single click.
* **Professional client experience** — Clients receive join links automatically (Zoom Pro+), or you can send them the link manually.
* **Unified scheduling flow** — Your meeting link lives _inside_ the appointment, alongside notes and client details.
* **Easy access for both staff and clients** — Join meetings from any device without switching between platforms.
* **Lightweight & secure design** — SimpleSpa never stores Zoom tokens or user data on its servers.

***

## Adding the app (installation)

{% stepper %}
{% step %}
### Install the connector in Zoom

1. Log in to your Zoom account.
2. Visit the SimpleSpa Zoom Connector in the Zoom App Marketplace.
3. Click **Install**.
{% endstep %}

{% step %}
### Approve the permissions

Review the requested permissions (meeting creation + user profile read), then click **Allow**.
{% endstep %}

{% step %}
### Complete the connection in SimpleSpa

1. Open SimpleSpa → **Appointments** → any appointment.
2. Click the camera icon (**Add Meeting**).
3. Choose **Add Zoom Meeting** to complete the connection.
{% endstep %}
{% endstepper %}

Once authorized, your browser session securely stores your Zoom token for meeting creation.

## How the interface works

### Appointment view

When you open an appointment:

* If no Zoom meeting exists, you see a small icon-only button (video-camera icon). Hover over it to see the label _“Add Meeting”_.
* Click that button to start creating the Zoom meeting.

### Meeting creation

* When you click the _Add Meeting_ button, a Zoom meeting is created automatically behind the scenes.
* After it is created, you see a compact meeting widget\* in the appointment view with:
  * A direct client link — click to open or copy.
  * The meeting start time in your local time format (for example, “Tuesday, November 11 2025 6:00 pm”).
  * The meeting topic and Meeting ID in a collapsible **Details** section, if you want more info.

### Notes section

* A special Zoom meeting line is added to the appointment notes automatically:

```
Zoom: [Appointment with {client}] Tuesday, November 11 2025 6:00 pm — {short join link}
```

* This records the meeting link and time as part of the appointment history.

### Loading an existing meeting

* Meetings are stored only in appointment notes.
* SimpleSpa reads the note and displays the details automatically.

Handle meeting updates (date/time changes) in Zoom if needed.

### Removing a meeting

Currently, you remove and update meetings directly in Zoom:

https://zoom.us/meeting#/upcoming

If the meeting is deleted in Zoom, SimpleSpa detects this automatically and cleans up the meeting note.

### Removing the app (Zoom deauthorization)

To disconnect SimpleSpa from Zoom:

1. Log in to your Zoom account.
2. Go to **Zoom App Marketplace → Manage**.
3. Open **Installed Apps**.
4. Select **SimpleSpa**.
5. Click **Uninstall**.

#### What happens after uninstall?

* SimpleSpa immediately loses access (tokens are invalidated).
* No Zoom data is stored on SimpleSpa servers, so no data removal is required.
* Existing notes in appointments stay untouched (they are user-created text).

To use the integration again, simply reconnect from any appointment.

#### What happens next

* All tokens are invalidated immediately.
* SimpleSpa stores no Zoom data, so nothing needs to be removed.
* Notes you created earlier remain unchanged.
* To reconnect, simply click **Add Meeting** again inside an appointment.

### Security & data handling

* No Zoom OAuth tokens are stored on SimpleSpa servers.
* Tokens remain only in the staff member's browser session.
* Tokens expire naturally and are destroyed when you uninstall.
* SimpleSpa does not access or store Zoom user profile data.
* Meeting information is stored only in appointment notes, controlled entirely by you.
* The design intentionally minimizes Zoom data exposure for maximum security.

***

## Quick steps for your staff

1. Open the appointment.
2. Click **Add Meeting** (camera icon) if no meeting exists.
3. Wait a moment — the link appears automatically.
4. Share the client link, or use the copy button to copy the link.
5. If you need to remove or reschedule, click **Remove meeting** and then recreate it if needed.

## Important notes

{% hint style="info" %}
* To make sure email notifications to clients (such as automatic Zoom invite emails) are sent properly, the host account must be on a Pro, Business, Education, or Enterprise plan.
* Simple Free (Basic) accounts do not support meeting registration with automatic email confirmation, so you need to send those notifications to your clients manually.
* The meeting widget is not yet available. Please view the meeting details in the notes.
* Meeting management, such as removals, is done directly on the Zoom platform: [https://zoom.us/meeting#/upcoming](https://zoom.us/meeting#/upcoming)
{% endhint %}

## Related

* [Google Meet](google-meet.md)
* [Appointment Notes](../appointment-notes.md)
