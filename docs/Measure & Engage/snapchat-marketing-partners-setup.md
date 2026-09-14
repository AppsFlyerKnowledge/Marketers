---
title: "Snapchat marketing partners setup"
excerpt: "Learn how to integrate with Snapchat marketing partners to measure your campaigns and configure postbacks in AppsFlyer."
---
At a glance: Integrate with Snapchat marketing partners to measure campaigns you run with them. When configured, AppsFlyer sends postbacks to the configured Snapchat marketing partner.

## Setting up a Snapchat Marketing Partner

Follow the steps below to configure your campaigns with any one of Snapchat Marketing Partners.

* Activate [Snapchat attribution](https://support.appsflyer.com/hc/articles/211011983).
* In the Snapchat **Business Manager** dashboard, copy the **Snap Account ID** highlighted below in green.

![snapchat-dashboard.png](https://files.readme.io/4d943f14633d51b7c43408616e8e771c45c8555400efb1e6c74eb5fbfd696084-4417687661841.png)

Once you have activated Snapchat and obtained the Snap Account ID, configure the Marketing Partner:

1. In AppsFlyer, from the side menu, select **Collaboration** > **Active Integrations.**
2. In the search box, enter the name of the specific partner, or 'Snapchat' to see the full list of Snapchat marketing partners.
3. Click the logo of the required partner to open the configuration window.
4. Enable **Activate partner**.
5. Paste the **Snap account ID** obtained from the Snapchat dashboard (with the hyphens) in the **Snap Account ID** field.
6. Click **Save**.

### Default postbacks

AppsFlyer can send automatic install and re-engagement postbacks to partners. Use this section to define the **source of the users** that allow sending these postbacks. In some cases the source of users is predefined and cannot be changed:

![remerge2.png](https://files.readme.io/115d04a76ff27deb4bc470c91f6fead6894886c7f4b983c39ecf42d54d09d12b-4417687705617.png)

Select **Only events attributed to this partner** for events coming only from users attributed to this partner.

Select **Events attributed to any partner or organic** to have your entire user base available to be reported to this partner.

### In-app events

1. To send in-app event postbacks to the Snapchat marketing partner you're configuring, toggle the In-App Events Postback to **ON**.
2. Individually add the in-app events (SDK events) you want to send to the partner and [map them as required.](https://support.appsflyer.com/hc/articles/208439256-In-App-Events-Postback-Configuration#event-mapping)

> ❗️ Important!
>
> Disabling attribution for Snapchat prevents sending postbacks to Snapchat Marketing Partners.

### See also

<Cards>
  <Card title="Snapchat and AppsFlyer SKAdNetwork interoperation" href="https://support.appsflyer.com/hc/articles/360017604077">
    Learn about the interoperation between Snapchat and AppsFlyer for SKAdNetwork.
  </Card>
</Cards>