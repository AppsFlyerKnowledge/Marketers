---
title: "Self-serve integration management for ad networks"
excerpt: "Learn how to set up and manage your attribution links, default postbacks, and Advanced Privacy or SKAN postbacks directly from the AppsFlyer dashboard."
---
**At a glance**: Set up and manage your integration from the AppsFlyer dashboard.

## Prerequisites:

- You have to have login credentials (username and password) for AppsFlyer before you can manage attribution links and postbacks. To [create a partner](https://support.appsflyer.com/hc/articles/360001300998) account, ask an AppsFlyer customer (advertiser) to [invite you](https://support.appsflyer.com/hc/articles/4410395957521#invite-new-partners-to-appsflyer).
- Management of attribution links and default postbacks is available only to partners who joined after February 1, 2022.
- Verify that your servers are ready to receive postbacks by complying with the following:
  - Allowlist AppsFlyer server [IP addresses](https://support.appsflyer.com/hc/articles/207447093-AppsFlyer-IPs-for-Whitelisting) in your firewalls and security systems to ensure communication with your endpoints
  - TLS versions: TLS 1.1, TLS 1.2+ with the [ciphers listed.](https://support.appsflyer.com/hc/articles/360001288945#outgoing-messages-appsflyer-as-client)
  - Ports: 80, 443

> 📘 Admin access required
>
> Only Admin users can access and manage this section.

## Accessing Integration management

1. Log into your AppsFlyer partner account.
2. Click the top-right drop-down menu > **Postback Management**.

## Attribution link

The attribution link is the most important part of your integration. Attribution links are used to notify AppsFlyer about user engagement with an ad. Attribution links are placed behind ads, so that when a user clicks on an ad they are clicking on an attribution link.

Completion of attribution link configuration is mandatory

**To configure attribution link:**

1. In the **Attribution link** tab, add the parameters to be included in your attribution link:
   - **Parameter name**: AppsFlyer parameter screen name.
   - **Your macro**: add the macro that populates the parameters with values.
   - **Include**: check the box to include the parameter in the link

> 🚧 Important!
>
> - Add campaign and ad-related parameters to provide more robust data about campaign performance.
> - **Site ID** is a mandatory parameter
> - Advertisers use this link as a basis for the integration of a specific app and can add additional parameters to it.
> - App ID, Lookback window duration, and your Partner ID are added to the link automatically and you don't need to add them to this template.

2. **[Optional]** Add custom parameters that are not provided by AppsFlyer.
3. Use the link preview to verify that everything is correct.
4. Click **Save**.

[More about attribution links and available parameters](https://support.appsflyer.com/hc/articles/207447163).

In the case of any issues, reach out using the [partner assistant widget](https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif).

## Default postback

Postbacks are URLs containing macros populated by AppsFlyer and sent to your servers in real-time after each conversion (either on your network, or other networks too — depending on your configuration).

**To configure the default postback:**

1. Enter the **endpoint addresses.** These are the endpoints to which postbacks are sent. Enter the relevant URLs for installs, in-app events, or both. To be able to activate the integration, at least the install postback URL is required.
2. Add parameters to the postback:
   - **Parameter name**: AppsFlyer parameter screen name.
   - **Your receiving parameter**: the respective receiving parameter on your side.
   - **Parameter value** (available for some parameters): choose the value format. For example, for boolean values, choose whether to receive them as "true"/"false", or 1/0.
   - **Install**: check the box to include the parameter in the install postback.
   - **In-app event**: check the box to include the parameter in the in-app event postback.

[Full list of postback macros](https://support.appsflyer.com/hc/articles/207273946)

> 🚧 Important!
>
> - To be able to distinguish between postbacks for legitimate events and rejected postbacks, configure the [rejected postback macros](/docs/postback-macros-for-ad-networks#macros%E2%80%94installs-inapp-events-and-rejected-events).
> - To enable rejected install/in-app event postbacks, append the following parameters to your default postback template:
>   - `is-rejected`
>   - `blocked-reason`
>   - `blocked-sub-reason`
>   - `blocked-reason-value`
>
>   **Note:** If the Advanced Privacy postback is enabled, append the parameters above to the Advanced Privacy template as well.

3. **[Optional] Custom parameters:** Configure your own parameters to include in the postback.
4. Use the postback template preview to verify that everything is correct.
5. Click **Save**.

[More postback info and examples.](/docs/in-app-event-postback-configuration)

In the case of any issues, use the [partner assistant widget](https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif).

## Advanced Privacy and SKAN postbacks

Advanced Privacy and SKAN postbacks can be configured only after the attribution link and default postback are created.

**To manage the postbacks:**

1. Select a postback type:
   - [Advanced privacy](https://support.appsflyer.com/hc/articles/360011316197) postback.
   - [SKAdNetwork](https://support.appsflyer.com/hc/articles/360011502657) postback.
2. Activate the builder.
3. **[For SKAdNetwork postback configuration only]** Enter your SKAdNetwork ID. This field is mandatory and the configuration can't be saved without a valid ID.
4. Enter the **endpoint addresses.** These are the endpoints to which postbacks are sent. Enter the relevant URLs for installs, in-app events, or both.
5. Add postback parameters:
   - **Parameter name**: AppsFlyer parameter screen name.
   - **Your receiving parameter**: The respective receiving parameter on your side.
   - **Parameter value** (available for some parameters): Choose the value format. For example, for boolean values, choose whether to receive them as "true"/"false", or 1/0.
   - **Install**: Check the box to include the parameter in the install postback.
   - **In-app event**: Check the box to include the parameter in the in-app event postback.

List of [SKAdNetwork postback macros](https://support.appsflyer.com/hc/articles/360011502657#receive-data-from-appsflyer)

List of [Advanced Privacy postback macros](https://support.appsflyer.com/hc/articles/360011316197#advanced-privacy-postback-specification)

> 🚧 Important!
>
> - To enable rejected install/in-app event postbacks, append the following parameters to your default postback template:
>   - `is-rejected`
>   - `blocked-reason`
>   - `blocked-sub-reason`
>   - `blocked-reason-value`
> - To enable rejected postbacks for Advance Privacy you must first append the parameters above to the [Default postback](https://support.appsflyer.com/hc/articles/360018512658#default-postback)
> - When the parameters above are added to both the Default postback and the Advanced Privacy postback (if enabled), rejected install/in-app event postbacks are enabled.

6. **[Optional] Custom parameters:** Configure your own parameters to include in the postback.
7. Use the postback template preview to verify that everything is correct.
8. Click **Save**.

Note, that when you save the postback, the changes take place immediately.

In the case of any issues, contact us using the [partner assistant widget](https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif).