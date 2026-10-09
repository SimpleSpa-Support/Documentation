# SMS/Text Notifications

SimpleSpa offers the most comprehensive SMS notifications in the industry, with each text message being customizable to meet your needs, by default automated SMS/Text reminders are sent out 24h prior to a scheduled appointment. If an appointment has been scheduled less than 24h hours, then you can either:

1. Change the status of the appointment to confirmed (from the appointment prompt) so the confirmation can go out to the client
2. If the client has an email on file, use the Send Email button in the appointment prompt to send out an email with the appointment details

## Client SMS/Text Appointment Reminder

Your clients receive an automated SMS reminder a day before their appointment, if you would like to allow your clients to confirm or cancel their appointment you can use the \[CONFIRM] tag, to only accept confirmations you can use the \[CNFRM] tag

<figure><img src="../../.gitbook/assets/Screenshot 2024-07-05 at 9.09.29 AM.png" alt=""><figcaption><p>The Client Reminder template (sent at a default time of 24h prior to the scheduled appointment)</p></figcaption></figure>

## Client SMS/Text Appointment Confirmation

Once you set your clients appointment as confirmed your client will receive an appointment notification, this can be manually set by changing the appointment status, when a client has confirmed or if booking within SimpleSpa to toggle the appointment as confirmed during the end of the booking process when using the appointent wizard

<figure><img src="../../.gitbook/assets/Screenshot 2024-07-05 at 9.09.45 AM.png" alt=""><figcaption><p>The Client Confirmation template (sent when appointment has been confirmed)</p></figcaption></figure>

## Client Thank You SMS/Text

Your clients will receive an automated SMS with a thank you message, upon a successful transaction with the POS (client will need to have a valid mobile number on their profile). The receipt can also included using the \[RECEIPT] tag

<figure><img src="../../.gitbook/assets/Screenshot 2024-07-05 at 9.10.07 AM.png" alt=""><figcaption><p>The Client Thank You template</p></figcaption></figure>

## Staff SMS/Text Appointment Notification

Once an appointment has been created your staff will get notified to know when they have been scheduled

<figure><img src="../../.gitbook/assets/Screenshot 2024-07-05 at 9.11.11 AM.png" alt=""><figcaption><p>The Staff Notification template</p></figcaption></figure>

## Staff SMS/Text Appointment Cancellation Notification

If an appointment is cancelled your staff will be notified of the cancellation

<figure><img src="../../.gitbook/assets/Screenshot 2024-07-05 at 9.13.12 AM.png" alt=""><figcaption><p>The Staff Cancelled template</p></figcaption></figure>

## Daily Staff Digest

This digest sends out a message to your staff 2 hours prior to their shift, with a message telling them their appointments for the day, and an attachment of their upcoming appointments

<figure><img src="../../.gitbook/assets/Screenshot 2024-07-05 at 9.13.00 AM.png" alt=""><figcaption><p>The Daily Agenda toggle section</p></figcaption></figure>

## Supported SMS Tags

* \[CLIENT\_NAME] - the client name will be automatically populated
* \[STAFF\_NAME] - the assigned staff name will be populated
* \[BUSINESS] - the business name will be populated
* \[LOCATION] - the location name will be populated
* \[DATE] - date only will be populated
* \[TIME] - time only will be populated
* \[DATETIME] - date time will be populated
* \[CONFIRM] - displays a link allowing a client to confirm or cancel their scheduled appointment
* \[CNFRM] - displays a link allowing a client to confirm only
* \[RECEIPT] - if the client was checked out using the POS then a receipt link will be populated

## Support for Client Replies

If your clients reply to a SimpleSpa notification Text/SMS, that reply will show up in your SimpleSpa account when you view all the sent messages for the day and we allow you to quickly view the respective appointment with a dedicated button for that message, when navigating to the SimpleSpa dashboard replies will show up as "growl" like notification alerts \*this functionality may be limited in some locales or if you have a custom Sender ID

SimpleSpa does not provide two way communication with your clients, only transactional messages regarding appointment information towards your clients and a reply from your clients to that notification. You can manually reply to a client if you are on a mobile device or a device which is connected to a messaging app, by clicking on the hyperlink of the mobile number your client has on file in the appointment popup. This will open a supported messaging app to send a message manually to the selected clients number

## Support for Client Return Calls

Calls made towards the number that sent the text notification will be answered by an automated IVR; clients with existing appointments will be greeted with a message and prompted with their next scheduled appointment date, time, service and staff member, they will have the option to Confirm their appointment directly over the phone _\*this functionality may be limited in some locales or if you have a custom Sender ID_

SimpleSpa sends SMS notifications with a 5 minute delay, to avoid accidental appointment changes - to subscribe to our SMS/Text Message Plans please [click here](https://www.simplespa.com/sms)

## Sender ID

In some countries SimpleSpa supports a custom Sender ID, a Sender ID is typically a name used to replace a phone number where the text message is sent from. Typically this is the business name and may be limited to 9-11 characters. Please note that some countries require a sender id be registered with local regulators for any SMS to be sent out, to register a custom Sender ID you will need to reach out to our support team and we will check availability and quote you the monthly maintenance fee for the service

## Dedicated Number

In certain regions of the world SimpleSpa supports a dedicated number where your messages are sent from, if you are interested in this feature please reach out to our support team so they can check availability and quote you for the monthly maintenance fee
