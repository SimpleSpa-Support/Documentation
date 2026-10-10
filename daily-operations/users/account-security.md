---
description: >-
  Change your password and protect your account with 2-step sign-in using a text
  message or an authenticator app.
icon: shield-halved
---

# Account Security

Every user, whatever their role, can manage their own sign-in security from **Account Security**.

## Open Account Security

Click your name in the top right corner and choose **Account Security**.

## Change your password

On **Account Security**, enter your new password twice and save.

Admins and managers can also set a password for another user. See [User Password](user-password.md).

## Turn on 2-step sign-in

With 2-step sign-in, you enter a code after your password, so someone who learns your password still can't sign in. You can receive the code by text message or from an authenticator app.

{% tabs %}
{% tab title="Authenticator app" %}
{% stepper %}
{% step %}
### Install an authenticator app

Install an app such as Google Authenticator, Microsoft Authenticator or 1Password on your phone.
{% endstep %}

{% step %}
### Start setup

On **Account Security**, choose to set up an authenticator app. A QR code appears.
{% endstep %}

{% step %}
### Scan the QR code

In your authenticator app, add a new account and scan the QR code.
{% endstep %}

{% step %}
### Confirm with a code

Enter the 6-digit code shown in the app to finish setup.
{% endstep %}
{% endstepper %}
{% endtab %}

{% tab title="Text message" %}
{% stepper %}
{% step %}
### Check your mobile number

Make sure your mobile number on your user profile is correct.
{% endstep %}

{% step %}
### Turn on text message codes

On **Account Security**, choose to receive sign-in codes by text message and save.
{% endstep %}
{% endstepper %}
{% endtab %}
{% endtabs %}

## Signing in with 2-step

{% stepper %}
{% step %}
### Enter your email and password

Sign in as usual.
{% endstep %}

{% step %}
### Enter your code

Enter the code from your authenticator app or the text message you received.
{% endstep %}
{% endstepper %}

{% hint style="warning" %}
After 5 incorrect codes you'll be signed out and see **Too many incorrect codes. Please sign in again.** Start again from your email and password.
{% endhint %}

## Signing in with Google or Apple

Users can also sign in with their Google or Apple account. On the **Users** page, an icon next to each user shows when Google or Apple sign-in is connected. See [Manage Users](managing-users.md).

{% hint style="info" %}
Lost your phone or can't get a code? Ask an admin on your account or contact SimpleSpa support to reset your 2-step sign-in.
{% endhint %}
