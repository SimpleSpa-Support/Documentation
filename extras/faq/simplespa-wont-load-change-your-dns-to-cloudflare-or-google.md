---
description: >-
  If SimpleSpa won't load on one network or device, switch your DNS to
  Cloudflare (1.1.1.1) or Google (8.8.8.8) to fix most connection problems.
---

# SimpleSpa won't load: change your DNS to Cloudflare or Google

Sometimes SimpleSpa won't open on one Wi-Fi network or computer, even though the internet works for other sites. The most common cause is the **DNS server** your internet provider assigns. DNS is the internet's phone book: it turns `my.simplespa.com` into an address your device can reach. If your provider's DNS is slow, out of date or blocking, SimpleSpa can fail to load.

Switching to a free public DNS from **Cloudflare** or **Google** fixes this in most cases. It takes about two minutes and you can switch back at any time.

## Signs this will help

* The browser shows **This site can't be reached**, **DNS\_PROBE\_FINISHED\_NXDOMAIN**, **Server not found** or **ERR\_NAME\_NOT\_RESOLVED**.
* SimpleSpa works on your phone's mobile data but not on your business Wi-Fi.
* SimpleSpa works on one computer but not another on the same network.
* Pages load very slowly or only some of the time, while other sites work normally.

{% hint style="info" %}
If **no** websites load at all, the problem is your internet connection itself, not DNS. Restart your modem and router first. While you wait, [Offline Mode](../../daily-operations/appointments/offline-mode.md) lets you view today's schedule.
{% endhint %}

## DNS addresses to use

Pick **one** provider and enter both of its addresses.

| Provider   | Preferred (primary) | Alternate (secondary) | Private DNS hostname (Android) |
| ---------- | ------------------- | --------------------- | ------------------------------ |
| Cloudflare | `1.1.1.1`           | `1.0.0.1`             | `one.one.one.one`              |
| Google     | `8.8.8.8`           | `8.8.4.4`             | `dns.google`                   |

If a screen asks for **IPv6** addresses as well:

* **Cloudflare:** `2606:4700:4700::1111` and `2606:4700:4700::1001`
* **Google:** `2001:4860:4860::8888` and `2001:4860:4860::8844`

## Change your DNS

{% hint style="success" %}
**Fixing the whole salon at once?** Change the DNS on your **router** instead of each device. Log in to your router (usually by typing `192.168.1.1` or `192.168.0.1` in the browser, or through your provider's app), find the **DNS** setting under Internet, WAN or LAN, and enter the addresses above. Every device on the network then uses the new DNS. If you're not sure how, your internet provider or IT person can do this for you.
{% endhint %}

{% tabs %}
{% tab title="Windows 11" %}
1. Open **Start** → **Settings** → **Network & internet**.
2. Select **Wi-Fi** (or **Ethernet** if you use a cable), then select your network or **Hardware properties**.
3. Next to **DNS server assignment**, select **Edit**.
4. Change **Automatic (DHCP)** to **Manual** and turn on **IPv4**.
5. Enter the **Preferred DNS** and **Alternate DNS** from the table above.
6. Select **Save**.
7. Close and reopen your browser, then go to `my.simplespa.com`.
{% endtab %}

{% tab title="Windows 10" %}
1. Open **Control Panel** → **Network and Internet** → **Network and Sharing Center**.
2. Select **Change adapter settings** on the left.
3. Right-click your Wi-Fi or Ethernet connection and choose **Properties**.
4. Select **Internet Protocol Version 4 (TCP/IPv4)**, then **Properties**.
5. Choose **Use the following DNS server addresses** and enter the **Preferred** and **Alternate** addresses from the table above.
6. Select **OK**, then **Close**.
7. Close and reopen your browser, then go to `my.simplespa.com`.
{% endtab %}

{% tab title="Mac" %}
1. Open the **Apple menu** → **System Settings** → **Network**.
2. Select **Wi-Fi** (or **Ethernet**), then **Details…** next to your connected network.
3. Select **DNS** in the sidebar.
4. Under **DNS Servers**, select **+** and add both addresses from the table above. If other addresses are listed, select each one and select **–** to remove it.
5. Select **OK**.
6. Close and reopen your browser, then go to `my.simplespa.com`.
{% endtab %}

{% tab title="iPhone & iPad" %}
1. Open **Settings** → **Wi-Fi**.
2. Tap the **ⓘ** next to your connected network.
3. Scroll down and tap **Configure DNS**.
4. Tap **Manual**.
5. Delete the existing servers (tap the red minus), then tap **Add Server** and add both addresses from the table above.
6. Tap **Save**.

{% hint style="info" %}
This only applies to that Wi-Fi network. Repeat it for each network you use.
{% endhint %}
{% endtab %}

{% tab title="Android" %}
1. Open **Settings** → **Network & internet** (on Samsung: **Connections** → **More connection settings**).
2. Tap **Private DNS**.
3. Choose **Private DNS provider hostname**.
4. Enter `one.one.one.one` for Cloudflare or `dns.google` for Google.
5. Tap **Save**.

This works on Wi-Fi and mobile data. Menu names vary slightly between phone makers.
{% endtab %}

{% tab title="Chrome only" %}
If you can't change your computer's settings (for example, a work-managed computer), you can set the DNS just for Google Chrome:

1. In Chrome, open **⋮** → **Settings** → **Privacy and security** → **Security**.
2. Turn on **Use secure DNS**.
3. Choose **Cloudflare (1.1.1.1)** or **Google (Public DNS)** from the list.
4. Reload SimpleSpa.

This also works in Microsoft Edge under **Settings** → **Privacy, search, and services** → **Use secure DNS**.
{% endtab %}
{% endtabs %}

## Still not loading?

Your computer may have remembered the old, bad address. Clear it:

* **Windows:** open **Command Prompt** and run `ipconfig /flushdns`
* **Mac:** open **Terminal** and run `sudo dscacheutil -flushcache; sudo killall -HUP mDNSResponder` (enter your Mac password when asked)
* **Phone or tablet:** turn Airplane Mode on, wait 10 seconds, then turn it off.

Then restart your browser and try again. You can also try a private/incognito window to rule out browser extensions.

## Check that it worked

Visit [one.one.one.one/help](https://one.one.one.one/help) (Cloudflare) or [dns.google](https://dns.google) (Google). If SimpleSpa now loads normally, you're done.

## Switching back

Repeat the same steps and set DNS back to **Automatic** (Windows, Mac, iPhone) or **Off / Automatic** for Private DNS (Android).

## Contact support

If SimpleSpa still won't load after changing your DNS, contact SimpleSpa support and include:

* The exact error message (a screenshot is best)
* Your device and browser
* Whether it works on mobile data or another network

## Related

* [Browser Support](../../get-started/browser-support.md)
* [Offline Mode](../../daily-operations/appointments/offline-mode.md)
* [What kind of computer do I need?](what-kind-of-computer-do-i-need.md)
