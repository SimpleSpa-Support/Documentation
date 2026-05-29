---
description: >-
  Turn every booking into a professional virtual consultation experience: no
  separate scheduling tools, no confusion for clients, and everything sits right
  with your appointment.
---

# Zoom Meetings

### Benefits

* Instant virtual meeting link — With just one click, you get a secure Zoom link created for your appointment, saving you time and manual coordination.
* Instant virtual meeting creation — Add a Zoom meeting to any appointment with a single click.
* Professional client experience — Clients receive join links automatically (Zoom Pro+) or can be sent the link manually.
* Unified scheduling flow — Your meeting link lives _inside_ the appointment, alongside notes and client details.
* Easy access for both staff and clients — Join meetings from any device without switching between platforms.
* Lightweight & secure design — SimpleSpa never stores Zoom tokens or user data on its servers.

***

## Adding the App (Installation)

1. Log in to your Zoom account.
2. Visit the SimpleSpa Zoom Connector in the Zoom App Marketplace.
3. Click Install.
4. Review the requested permissions (meeting creation + user profile read).
5. Click Allow.
6. Open SimpleSpa → Appointments → any appointment.
7. Click the camera icon (“Add Meeting”)&#x20;
8. Add Zoom Meeting to complete connection.

Once authorized, your browser session securely stores your Zoom token for meeting creation.

### How the interface works

#### 1. Appointment view

When you open an appointment:

* If no Zoom meeting exists, you’ll see a small icon-only button (video-camera icon) labelled _“Add Meeting”_ when you hover over it.
* Clicking that button initiates the Zoom meeting creation process.

#### 2. Meeting creation

* Once you click the _Add Meeting_ button, a Zoom meeting is created automatically behind the scenes.
* After creation, you’ll see a compact meeting widget\* in the appointment view with:
  * A direct Client link — click to open or copy.
  * The meeting start time shown in your local time format (e.g., “Tuesday, November 11 2025 6:00 pm”).
  * The meeting topic and Meeting ID in a collapsible “Details” section if you want more info.

#### 3. Notes section

* Alongside the appointment notes, a special Zoom-meeting line is appended automatically:

```
Zoom: [Appointment with {client}] Tuesday, November 11 2025 6:00 pm — {short join link}
```

* This ensures the meeting link and time are recorded as part of the appointment history.

#### 4. Loading an existing meeting

* Meetings are stored only in appointment notes.
* SimpleSpa reads the note and displays the details automatically.

Meeting updates (date/time changes) should be handled in Zoom if needed.

#### 5. Removing a Meeting

Currently, meeting removal and updates are managed directly through Zoom:

https://zoom.us/meeting#/upcoming

If the meeting is deleted in Zoom, SimpleSpa automatically detects this and cleans the meeting note.

#### 6. Removing the App (Zoom Deauthorization)

To disconnect SimpleSpa from Zoom:

1. Log into your Zoom account
2. Go to Zoom App Marketplace → Manage
3. Open Installed Apps
4. Select SimpleSpa
5. Click Uninstall

#### What happens after uninstall?

* SimpleSpa immediately loses access (tokens invalidated)
* No Zoom data is stored on SimpleSpa servers, so no data removal is required
* Existing notes in appointments remain untouched (they are user-created text)

To use the integration again, simply reconnect from any appointment.

#### What happens next

* All tokens are invalidated immediately
* SimpleSpa stores no Zoom data, so nothing needs to be removed
* Notes you previously created remain unchanged
* To reconnect, simply click “Add Meeting” again inside an appointment

#### 7. Security & Data Handling

* No Zoom OAuth tokens are stored on SimpleSpa servers
* Tokens remain only in the staff browser session
* Tokens expire naturally and are destroyed upon uninstall
* SimpleSpa does not access or store Zoom user profile data
* Meeting information is stored only in appointment notes, controlled entirely by the user
* Design intentionally minimizes Zoom data exposure for maximum security

***

### Quick steps for your user

1. Open the appointment.
2. Click Add Meeting (camera icon) if no meeting exists.
3. Wait a moment — the link appears automatically.
4. Share the client link, or use the copy button or copy the link.
5. If you need to remove or reschedule, click Remove meeting and then optionally recreate.

#### Important Notes

* To ensure email notifications to clients (such as automatic Zoom invite emails) are sent properly, the host account must be on a Pro, Business, Education, or Enterprise plan.&#x20;
* Simple Free (Basic) accounts do not support meeting registration with automatic email confirmation, so you will need to send those notifications to your clients manually.
* Meeting widget is not yet available, please view the meeting details from the notes
* Meeting management i.e. removals are done directly on the Zoom platform [https://zoom.us/meeting#/upcoming](https://zoom.us/meeting#/upcoming)
