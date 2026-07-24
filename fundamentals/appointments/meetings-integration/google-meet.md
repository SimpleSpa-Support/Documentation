---
description: >-
  Create Google Meet links instantly from any appointment, no switching apps, no
  copying calendars, just one click to schedule secure virtual sessions.
---

# Google Meet

### Benefits

Adding Google Meet to your SimpleSpa appointments gives you instant virtual-meeting capability with zero friction:

* Instant meeting links — Create a Google Meet link for any appointment with a single click.
* Seamless workflow — The Meet link automatically appears inside the appointment notes, ensuring it’s always stored with the appointment.
* Cleaner communication — Share the meeting link instantly with clients through your normal SimpleSpa communication tools or your email client.
* Professional, modern scheduling — Clients get a smooth and predictable online meeting experience without juggling multiple platforms.
* Secure by design — Google handles all guest access, permissions, and security. SimpleSpa does not store your Google access tokens on its servers.

***

## How the Interface Works

### 1. Appointment View – Meeting Button

In every appointment, you will notice a small camera icon button (hover title: “Add Meeting”).

Clicking this button opens a simple menu:

* Add Google Meet
* Add Zoom Meeting

Choose Add Google Meet.

***

### 2. Creating a Google Meet Link

After selecting Add Google Meet, SimpleSpa:

1. Checks whether you have already connected Google.
2. If not, opens the Google OAuth window where you select your Google account and grant permission (Calendar access).
3. Automatically creates a Google Calendar event with a Google Meet link.
4. Appends the Meet link into your appointment notes in a clean, timestamped format.

#### What gets stored

A typical meeting entry appears like:

> Google Meet: Tuesday, November 11 2025 6:00 PM — https://meet.google.com/abc-defg-hij

This becomes part of the appointment’s history and can be copied or referenced at any time.

***

### 3. Notes Section Integration

Just like Zoom meetings, Google meetings are stored directly inside appointment notes, ensuring:

* No data duplication
* No backend storage of tokens
* A single source of truth for all appointment-related actions

This also ensures that if staff members rotate or switch devices, the meeting link is always available.

***

### 4. Emailing the Client the Meet Link

When your appointment has a client email on file, SimpleSpa automatically asks Google to send the client a standard Google Calendar invitation. The client receives:

* An email invitation from your Google account (the account you connected)
* The date and time of the appointment, shown in their own time zone
* The Google Meet link, ready to join with one click
* Accept / Decline buttons, just like any Google Calendar invite

There is nothing extra to do — if an email address exists on the appointment, the invitation is sent the moment the meeting is created. The confirmation message will read "Google Meet created — invite emailed to client."

**If the client has no email on file**

The meeting is still created normally, and the Meet link is saved into the appointment notes as usual. You can share it manually using:

* SimpleSpa's existing "Send Email" or messaging tools, or
* Your own email client (Gmail, Outlook, Mail.app)

The meeting link is ready to copy and paste anywhere.

**Good to know**

* The invitation comes directly from Google, sent on behalf of the connected Google account — not from SimpleSpa. Its appearance and wording are Google's standard invite format and cannot be customized.
* Because the invite is a real Google Calendar invitation, any changes the client makes (accepting, declining) appear in your Google Calendar, not in SimpleSpa.
* If you later delete the event in Google Calendar, choose "Send" when Google asks whether to notify guests, so the client receives the cancellation.

***

### 5. Managing or Editing a Google Meeting

Editing or deleting a Google Meet link should be performed directly through your Google Calendar:

1. Open Google Calendar
2. Locate the event
3. Edit time, title, or guest list
4. Or delete the event entirely

SimpleSpa intentionally keeps the integration lightweight and secure, so it does not modify or delete Google Calendar events after creation.

If you delete the event, you should manually remove the Meet link from the appointment notes.

***

### 6. Removing Google Authentication

To disconnect SimpleSpa from Google:

1. Visit https://myaccount.google.com/permissions
2. Locate SimpleSpa under “Third-party apps with account access”
3. Click Remove Access

#### What happens after removal?

* SimpleSpa will no longer be able to create Google Meet links
* Existing appointment notes stay intact (they are user-entered text)
* Clicking Add Google Meeting will simply prompt you to reconnect

***

## Security & Data Handling

*   No Google tokens are stored on SimpleSpa servers.

    Tokens exist only in the staff member’s browser session.
* No Google Calendar data is saved in SimpleSpa’s database.
* Removing the app immediately invalidates all access.
* Appointment notes remain untouched, since they are local to SimpleSpa and created by the user.

This integration is intentionally designed to require minimal permissions, avoid persistent storage, and maintain strict separation between Google data and SimpleSpa data.

***

## Quick Steps for Your Staff

1. Open any appointment
2. Click the camera icon → choose Add Google Meeting
3. Approve Google access on first use
4. Link is generated instantly and saved into the notes
5. Share with your client

It takes 2 seconds, eliminates manual scheduling, and gives your business seamless online-meeting capability.
