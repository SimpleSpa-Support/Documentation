---
description: >-
  Send a campaign audience to Mailchimp, or download it for Constant Contact,
  Klaviyo, Brevo or any other email tool.
icon: file-export
---

# Exporting Clients to Email Tools

If you already use an email marketing tool, you can send your SimpleSpa clients to it. Both options are inside **New campaign**, at the right of the reach bar on the **To** step.

{% hint style="info" %}
Only active clients who allow marketing email and aren't marked as do-not-contact are exported. The export follows the audience, filters and **Limit** you set in the campaign.
{% endhint %}

{% tabs %}
{% tab title="Mailchimp" %}
{% stepper %}
{% step %}
### Connect

Click **Export to Mailchimp** and paste your Mailchimp API key.

Not sure where to find it? Click **Where do I find my key?**. In Mailchimp, go to **Profile → Extras → API keys → Create A Key**, or use the **Open Mailchimp API keys** button.

Tick **Remember the key on this computer** if you'll export again. You can remove it later with **Forget saved key**.
{% endstep %}

{% step %}
### Choose

* Pick the Mailchimp audience to add clients to.
* Under **Who should we send?**, choose this campaign's audience or everyone who allows marketing email. Each option shows how many clients it includes.
* Check the tag, for example _SimpleSpa - Haven't visited lately_.

Click the export button, for example **Export 298 clients**.
{% endstep %}

{% step %}
### Done

You'll see how many contacts were added, updated and left out, and what to do next in Mailchimp.
{% endstep %}
{% endstepper %}

**What happens in Mailchimp**

* Existing contacts are updated, never duplicated.
* Anyone who unsubscribed in Mailchimp stays unsubscribed.
* Three fields are added to your audience: **Last visit**, **Visits** and **Total spent**.

{% hint style="warning" %}
Unsubscribes in Mailchimp are not sent back to SimpleSpa. If a client asks to stop receiving marketing, update their profile in SimpleSpa too.
{% endhint %}

{% hint style="success" %}
Your API key is never stored on SimpleSpa's servers. If you choose to remember it, it's saved only in your browser on that computer.
{% endhint %}
{% endtab %}

{% tab title="Other email tools" %}
{% stepper %}
{% step %}
### Choose

Click **Download for other email tools** (or, inside the Mailchimp window, **Download a file for another email tool instead**). Choose the audience and tag, then click **Download** with the number of clients.
{% endstep %}

{% step %}
### Import the file

You'll get a file named `simplespa-clients-YYYY-MM-DD.csv` with these columns: Email, First name, Last name, Phone, Birthday, Last visit, Visits, Total spent and Tag. Names with Greek letters or accents open correctly in Excel.

Follow the steps for your tool on the **Done** screen.
{% endstep %}
{% endstepper %}

**Constant Contact**

1. Go to **Contacts → Add contacts → Upload from file**.
2. Choose the file.
3. Match the columns.
4. Add the contacts to a list named after the tag.

Constant Contact will ask you to confirm you have permission to email these contacts.

The **Done** screen also includes short tips for **Klaviyo** and **Brevo**.
{% endtab %}
{% endtabs %}
