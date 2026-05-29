# Email Notifications

With our appointment scheduling software you can have customizable email notifications sent out to your clients and staff for free.

To access the Email Notifications, visit the Settings > Locations > select your location > Email Notifications

<figure><img src="../../.gitbook/assets/Screenshot 2024-07-05 at 8.50.04 AM.png" alt=""><figcaption><p>The Locations tab in the Settings</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2024-07-05 at 8.48.36 AM.png" alt=""><figcaption><p>The Email Notifications Tab</p></figcaption></figure>

From the Email Notifications tab you can set when the reminders will be sent out, the default setting is 24h before the scheduled appointment, it is important to note that if an appointment has been scheduled less than 24h an automated email reminder will not go out to the client

## Customer Email Reminder

This is sent to your client if they have an email set up on their account, at any time you can change your clients preferences and enable or disable these reminders to be sent, you can customize when you want the reminder to be sent out form 24h, 48h, 1 week before the appointment is scheduled

<figure><img src="../../.gitbook/assets/Screenshot 2024-07-05 at 8.47.41 AM.png" alt=""><figcaption><p>The Email Reminder Template - To edit this visit the Settings > Locations > select your location > Email Notifications Tab</p></figcaption></figure>

The Customer Email Reminder also supports the \[CONFIRM] tag which will automatically add a confirm button in the email buttons to allow your clients to confirm or cancel their scheduled appointment

If you need to inform the client of their scheduled appointment there is the ability to manually send an email by visiting the clients appointment and selecting it for the appointment prompt to appear, here select the Send Email button which will send out the [#online-booking-email](email-notifications.md#online-booking-email "mention") to the client

<figure><img src="../../.gitbook/assets/Screenshot 2024-07-05 at 8.55.37 AM.png" alt=""><figcaption><p>The Send Email button found in the appointment prompt, this button will appear if the client has an email on file</p></figcaption></figure>

Replies: SimpleSpa actively supports responses sent from these messages, unlike other platforms that may disregard such communication, potentially resulting in complete loss of correspondence.

## Staff Email Notification

When an appointment is booked your staff will receive an email notification informing them of the new booking

<figure><img src="../../.gitbook/assets/Screenshot 2024-07-05 at 8.52.14 AM.png" alt=""><figcaption><p>The Staff Appointment notification email template</p></figcaption></figure>

## Online Booking Email

Once an appointment has been booked online, besides the ability to add it to their Google, Outlook or Yahoo calendar your customer will receive an email informing them of their booking

<figure><img src="../../.gitbook/assets/Screenshot 2024-07-05 at 8.51.14 AM.png" alt=""><figcaption><p>The Online Booking template</p></figcaption></figure>

## Staff Login

SimpleSpa also sends out an email when you first set your staff to login, allowing them to create their own password for accessing their own appointments on SimpleSpa

<figure><img src="../../.gitbook/assets/Screenshot 2024-07-05 at 8.51.56 AM.png" alt=""><figcaption><p>The welcome email sent to staff when they have been set to login</p></figcaption></figure>

## Post Appointment Thank You Email

When an appointment has been completed or paid for, we will then give you an option in the appointment popup to Send Post Email ![](<../../.gitbook/assets/Send Post Email Button.webp>) this is pre written as a Thank you, but you can write anything you like directly to your client using our rich text editor, an email will be sent out to your clients email address. This feature is available only if your client has an email in their profile.

## Supported Email Tags

* \[CLIENT\_NAME] - this tag will automatically populate the clients name
* \[STAFF\_NAME] - this tag will automatically populate the assigned staff name
* \[SERVICE\_NAME] - this tag will automatically populate the appointment service name
* \[SERVICE\_COST] - this tag will automatically populate the service cost
* \[BUSINESS] - this tag will automatically populate the business name (found in the Settings)
* \[LOCATION] - this tag will automatically populate the business location name (found in the Settings > Locations > selecting the location)
* \[LOCATION\_PHONE] - this tag will automatically populate the location phone (found in the Settings > Locations > selecting the location)
* \[LOCATION\_EMAIL] - this tag will automatically populate the location email (found in the Settings > Locations > selecting the location)&#x20;
* \[PRETTY\_DATE] - this tag will display the date
* \[DATE2] - this tag will display the date in a different format
* \[DATETIME] - this tag will display the date/time
* \[TIME] - this tag will display the time of the appointment
* \[CONFIRM] - this tag will display a confirm button (only supported in the Email reminder template)
* \[DURATION] - this tag will display the duration in minutes of the scheduled appointment
* \[FORMS] - this tag will populate all forms associated with the service for the appointment scheduled

\*Each email type can show the business logo as long as this is set in the Settings, and each message can be customized with a message or formatting that you would prefer
