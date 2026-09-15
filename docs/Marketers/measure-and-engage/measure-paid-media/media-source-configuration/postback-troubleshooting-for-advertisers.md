---
title: "Postback troubleshooting for advertisers"
excerpt: "Find the leading causes and solutions to why your partner isn't receiving expected postbacks."
---
**At a glance:** Find the leading causes and solutions to why your partner isn't receiving expected postbacks. Go through each of the topics below and see if they may be the cause.

## Check the integration toggles

Various toggles control different parts of the integration. The state of the toggle could be the reason for not receiving postbacks.

### Activate partner is turned off

When the [**Activate partner**](/docs/partner-activation-deactivation) toggle is turned off, conversions aren't attributed and postbacks aren't sent to partners.

<Image src="https://files.readme.io/d43b4f465749e343d9523e90e87e43b77a85cdd920f0c0770a94bcb7a585d920-14979273403793.png" alt="integration_turned_off.png" />

**To activate the integration:**

1. In AppsFlyer, from the side menu, select **Collaborate** \> **Active Integrations.**
2. Click the Manage integration icon of the partner.
3. From the **Integration** tab, turn on the **Activate partner** toggle.

Another case may be if the [**Activate partner**](/docs/partner-activation-deactivation) toggle is currently turned on but during the time of the event, it was turned off. Use the Audit log to check and see if the partner integration was active at the time of the event:

- From the top bar, open the account menu (email address dropdown) > **Security center** > **Audit log**.

### In-app event postbacks is turned off

The [**In-app event postbacks**](https://support.appsflyer.com/hc/articles/208439256-In-app-events-postback-configuration) toggle is turned off, or it may have been turned off during the time of the event. This means no postbacks are sent.

**To turn on In-app event postbacks:**

1. In AppsFlyer, from the side menu, select **Collaborate** \> **Active Integrations.**
2. Click the Manage integration icon of the partner.
3. From the **Integration** tab, scroll down to the **In-app events postbacks** toggle and turn it on.

<Image src="https://files.readme.io/20dadaa71b8b54c4512e74a925e66cec9da5e8138bb28a545c5452eef2d38304-14627453566737.png" alt="integration-in_app_event_postbacks_toggle.png" />

## Check the event configuration

The event could be configured in a way that certain postbacks aren't sent.

### The event isn't configured

Check that the event is included in the list of in-app events that were configured. If it’s not defined, a postback isn't sent.

<Image src="https://files.readme.io/c2b3a3a87c4a1f39a3fa3acc28c736fd69d8d6d21d4b9ed5d3c84e8df0d3bf39-14979245450641.png" alt="list_of_in_app_events.png" />

1. In AppsFlyer, from the side menu, select **Collaborate** \> **Active Integrations.**
2. Click the Manage integration icon of the partner.
3. From the **Integration** tab scroll down to **In-app event postbacks** and see if the event name appears.

### The event is configured incorrectly

Check that the [event mapping](/docs/in-app-event-postback-configuration#event-mapping) is correct. Make sure **AppsFlyer event** (the name of the event as received by AppsFlyer from your mobile app or via S2S) matches the **mapped to partner name** (the exact event name used by the partner).

<Image src="https://files.readme.io/b0b4935f2b40e1c81961fbbecd159ca054816be2c58248624eed177ec17f9c20-14979366291857.png" alt="in_app_event_postback_mapping_2.png" />

### The event is configured correctly but with a condition

If a condition is defined for the event, the postback is sent according to the condition. Check if there's a condition that limits postback sending.

<Image src="https://files.readme.io/0f179d79fdb544f209f901370f7c0103e0fc5dbeda2554268b2a06a272a6b8b9-14979535388433.png" alt="in_app_event_condition__1_.png" />

### The event is configured to send postbacks only to the attributed partner

Check to see if the in-app event configuration is set to send postbacks to [**This partner only** or to **All media sources, including organic**](/docs/in-app-event-postback-configuration#options-for-sending-postbacks). If it's set to **This partner only**, only the attributed partner gets the postback.

<Image src="https://files.readme.io/3fd96860a0a8842dd183a29e9f9dd947b5c9082e2069c0aa74bd8eb781302908-14979359951761.png" alt="in_app_event_sending_options.png" />

### The event occurred outside of the configuration window

Postbacks are sent according to the [postback window](/docs/in-app-event-postback-configuration#inapp-event-postback-window) setting. Postbacks for events after this period aren't sent to the partner, although the events are still recorded in AppsFlyer.

<Image src="https://files.readme.io/21cae7825d557c1ee89c890ec64c922cb36e31be882850a26bfdc4e5595773f0-14661845664401.png" alt="in_app_event_postback_window.png" />

> 📘 Note
>
> For [SRNs](https://support.appsflyer.com/hc/articles/360001546905), in-app event postbacks are sent for the duration of the [partner data retention period](https://support.appsflyer.com/hc/articles/360006091197-User-level-data-retention-and-sharing-limitations-of-partners#partner-data-retention-periods).

## Privacy restrictions

In the following cases, AppsFlyer doesn't send postbacks due to privacy restrictions.

### The partner doesn't support Advanced Privacy or didn't set it up (iOS)

For iOS, when [Advanced Privacy](https://support.appsflyer.com/hc/articles/360018515798-Aggregated-Advanced-Privacy-framework#partner-advanced-privacy-switch) is turned on but the partner didn't configure Advanced Privacy on their side or they don't support Advanced Privacy, they won't receive [Advanced Privacy aggregated postbacks](https://support.appsflyer.com/hc/articles/360011316197#types-of-templates-for-sending-postbacks).

<Image src="https://files.readme.io/1d8784e8994eba5c403ac706673490b91b7b34ed4d5dbea8c3fe58f227d382c5-15140294126353.png" alt="partner_not_supporting_ap_postbacks.png" />

### Media source restrictions on third-party platforms

[Some media sources](https://support.appsflyer.com/hc/articles/19384888063249#postback-restrictions) restrict sharing data with third parties. AppsFlyer doesn't enable the sharing of user-level data acquired through these media sources with any third-party platforms or services. All installs from such media sources are therefore sent as organic. Note that Meta ads doesn't enable the sharing of any data with third-party platforms.

### The SDK was set not to share information with the partner

A sharing filter has been implemented in the SDK to prevent the partner from receiving information. This filter may be activated either by a user's explicit opt-out request or at any other point during the app's lifecycle.

For more information see: [Prevent data sharing with third parties](https://support.appsflyer.com/hc/articles/360001422989#prevent-sharing-data-with-networks) and [setSharingFilterForPartners](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setsharingfilterforpartners).

## Miscellaneous

### The postback was sent but doesn't show on the partner's platform

In some cases, although AppsFlyer sends postbacks to a partner, they aren't showing it on the partner's side. Is such cases, contact the partner.

**To see if the postback was sent from AppsFlyer:**

1. In AppsFlyer, from the side menu, select **Reports** \> **Raw Data Export.**
2. View the relevant report under **Postbacks** (Installs, In-app events, Retargeting conversions, In-app events retargeting).

<Image src="https://files.readme.io/21f7ead0f04cf8b67735476348245c5849b638701946236cf649adfa69699df6-14981466637457.png" alt="postback_reports.JPG" />

### The event didn't occur or wasn't sent to AppsFlyer

All events that occurred can be found on the [**Activity** dashboard](/docs/activity-dashboard) and in [Raw data reports](/docs/raw-data-reporting-overview). An event not showing there means it didn’t occur or it wasn't sent to AppsFlyer.

It could be the event wasn't defined in the SDK. In this case, you won't see it on the platform. Check the SDK configuration. [defined in the SDK](/docs/basic-sdk-integration-guide#recording-inapp-events).

If you think the event occurred, check below how to see if it appears in the Activity dashboard or create a Raw data report and look for it there.

**To view the Activity dashboard:**

- In AppsFlyer, from the side menu, select **Analyze** > **Activity** and select the partner and date range.

**To create a raw data report:**

1. In AppsFlyer, from the side menu, select **Reports** > **Raw Data Export**.
2. Click **Create report**.
3. Select the relevant report.
4. Select the date range and any of the necessary fields, and click **Create**.
5. Download the report and look for the event there.

### Differences in timezones

There may be discrepancies in receiving postbacks due to a difference in time zones between the AppsFlyer platform and the partner's platform. AppsFlyer dashboards and reports display according to the selected timezone.

**To see the app timezone in AppsFlyer:**

1. In AppsFlyer, from the side menu, select **Settings** \> **App settings**.
2. View the app timezone under **Localization**.

### SRNs missing advertising IDs (IDFA/GAID)

There are a number of [specific cases for SRNs](https://support.appsflyer.com/hc/articles/360001546905-Self-reporting-networks-SRNs-#does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid) in which AppsFlyer doesn't send postbacks for installs, app opens or in-app events.

### Media source restrictions on third-party platforms

[Some media sources](https://support.appsflyer.com/hc/articles/19384888063249#postback-restrictions) restrict sharing data with third parties. AppsFlyer can't share user-level data acquired through these media sources with any third-party platforms or services. All installs from such media sources are therefore sent as organic. Note that Meta ads doesn't share any data with third-party platforms.

### Advanced Privacy postbacks

When Advanced Privacy (AP) is turned on, user-level data for non-consenting users running iOS 14.5+ is not available via postbacks. Postbacks are sent according to the [Advanced Privacy template](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#types-of-templates-for-sending-postbacks).

#### See also

<Cards>
  <Card title="Postback troubleshooting for ad networks" href="https://support.appsflyer.com/hc/articles/7466104144145">
    Troubleshooting postbacks from the ad network perspective.
  </Card>
</Cards>