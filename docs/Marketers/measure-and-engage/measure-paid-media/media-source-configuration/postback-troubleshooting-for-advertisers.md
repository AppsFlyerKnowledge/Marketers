---
title: Postback troubleshooting for advertisers
metadata:
  keywords:
    - Postback
    - Partner
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2023-04-04T07:09:26Z'
  edited_at: '2026-09-15T11:00:17Z'
  id: 14272573202833
  locale: en-us
  section: Media source configuration
  section_id: 6551067072785
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/14272573202833-Postback-troubleshooting-for-advertisers
---
> **At a glance:** Find the leading causes and solutions to why your partner isn't receiving expected postbacks. Go through each of the topics below and see if they may be the cause.

<div id="check-the-integration-toggles" />

## Check the integration toggles

Various toggles control different parts of the integration. The state of the toggle could be the reason for not receiving postbacks.

<div id="the-activate-partner-toggle-was-turned-off" />

<Accordion title="Activate partner is turned off">

When the <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">**Activate partner**</Anchor> toggle is turned off, conversions aren't attributed and postbacks aren't sent to partners.

<Image align="center" alt="integration_turned_off.png" src="https://files.readme.io/d43b4f465749e343d9523e90e87e43b77a85cdd920f0c0770a94bcb7a585d920-14979273403793.png" />

**To activate the integration:**

1. In AppsFlyer, from the side menu, select **Collaborate** > **c**
2. Click the Manage integration icon of the partner.
3. From the **Integration** tab, turn on the **Activate partner** toggle.

Another case may be if the <Anchor target="_blank" href="/marketers/docs/partner-activation-deactivation">**Activate partner**</Anchor> toggle is currently turned on but during the time of the event, it was turned off. Use the Audit log to check and see if the partner integration was active at the time of the event:

* <span id="1703758710.321359"></span>From the top bar, open the account menu (email address dropdown) >**Security center** > **Audit log**.

</Accordion>

<div id="1703760110.503549" />

<div id="the-inapp-event-postbacks-toggle-was-turned-off" />

<Accordion title="In-app event postbacks is turned off">

The <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration">**In-app event postbacks**</Anchor> toggle is turned off, or it may have been turned off during the time of the event. This means no postbacks are sent.

**To turn on In-app event postbacks:**

1. In AppsFlyer, from the side menu, select **Collaborate** > **Partner Integrations** > **Active Integrations.**
2. Click the Manage integration icon of the partner.
3. From the **Integration** tab, scroll down to the **In-app events postbacks** toggle and turn it on.

   <Image align="center" alt="integration-in_app_event_postbacks_toggle.png" src="https://files.readme.io/20dadaa71b8b54c4512e74a925e66cec9da5e8138bb28a545c5452eef2d38304-14627453566737.png" />

</Accordion>

<div id="check-the-event-configuration" />

## Check the event configuration

The event could be configured in a way that certain postbacks aren't sent.

<div id="the-event-wasnt-configured" />

<Accordion title="The event isn't configured">

Check that the event is included in the list of in-app events that were configured. If it’s not defined, a postback isn't sent.

<Image align="center" alt="list_of_in_app_events.png" src="https://files.readme.io/c2b3a3a87c4a1f39a3fa3acc28c736fd69d8d6d21d4b9ed5d3c84e8df0d3bf39-14979245450641.png" />

1. In AppsFlyer, from the side menu, select **Collaborate** > **Partner Integrations** > **Active Integrations.**
2. Click the Manage integration icon of the partner.
3. From the **Integration** tab scroll down to **In-app event postbacks** and see if the event name appears.

</Accordion>

<div id="the-event-was-configured-incorrectly" />

<Accordion title="The event is configured incorrectly">

Check that the <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#event-mapping">event mapping</Anchor> is correct. Make sure **AppsFlyer event** (the name of the event as received by AppsFlyer from your mobile app or via S2S) matches the **mapped to partner name** (the exact event name used by the partner).

<Image align="center" alt="in_app_event_postback_mapping_2.png" src="https://files.readme.io/b0b4935f2b40e1c81961fbbecd159ca054816be2c58248624eed177ec17f9c20-14979366291857.png" />

</Accordion>

<div id="the-event-was-configured-correctly-but-with-a-condition" />

<Accordion title="The event is configured correctly but with a condition">

If a condition is defined for the event, the postback is sent according to the condition. Check if there's a condition that limits postback sending.

<Image align="center" alt="in_app_event_condition__1_.png" src="https://files.readme.io/0f179d79fdb544f209f901370f7c0103e0fc5dbeda2554268b2a06a272a6b8b9-14979535388433.png" />

</Accordion>

<div id="the-event-was-configured-to-send-postbacks-only-to-the-attributed-partner" />

<Accordion title="The event is configured to send postbacks only to the attributed partner">

Check to see if the in-app event configuration is set to send postbacks to <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#options-for-sending-postbacks">**This partner only** or to **All media sources, including organic**</Anchor>. If it's set to **This partner only**, only the attributed partner gets the postback.

<Image align="center" alt="in_app_event_sending_options.png" src="https://files.readme.io/3fd96860a0a8842dd183a29e9f9dd947b5c9082e2069c0aa74bd8eb781302908-14979359951761.png" />

</Accordion>

<div id="the-event-occurred-outside-of-the-configuration-window" />

<Accordion title="The event occurred outside of the configuration window">

Postbacks are sent according to the <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#in-app-event-postback-window">postback window</Anchor> setting. Postbacks for events after this period aren't sent to the partner, although the events are still recorded in AppsFlyer.

<Image align="center" alt="in_app_event_postback_window.png" src="https://files.readme.io/21cae7825d557c1ee89c890ec64c922cb36e31be882850a26bfdc4e5595773f0-14661845664401.png" />

Note that for <Anchor target="_blank" href="/marketers/docs/self-reporting-networks-srns">SRNs</Anchor>, in-app event postbacks are sent for the duration of the <Anchor target="_blank" href="/marketers/docs/user-level-data-retention#partner-data-retention-periods">partner data retention period</Anchor>.

</Accordion>

<div id="privacy-restrictions" />

## Privacy restrictions

In the following cases, AppsFlyer doesn't send postbacks due to privacy restrictions.

<div id="the-partner-didnt-set-up-advanced-privacy" />

<Accordion title="The partner doesn't support Advanced Privacy or didn't set it up (iOS)">

For iOS, when <Anchor target="_blank" href="/marketers/docs/apply-aggregated-advanced-privacy-framework#partner-advanced-privacy-switch">Advanced Privacy</Anchor> is turned on but the partner didn't configure Advanced Privacy on their side or they don't support Advanced Privacy, they won't receive <Anchor target="_blank" href="/partners/docs/advanced-privacy-guide-postback-macros-for-ad-networks#types-of-templates-for-sending-postbacks">Advanced Privacy aggregated postbacks</Anchor>.

<Image align="center" alt="partner_not_supporting_ap_postbacks.png" src="https://files.readme.io/1d8784e8994eba5c403ac706673490b91b7b34ed4d5dbea8c3fe58f227d382c5-15140294126353.png" />

</Accordion>

<div id="media-source-restrictions-on-thirdparty-platforms" />

<Accordion title="Media source restrictions on third-party platforms">

<Anchor target="_blank" href="/marketers/docs/discrepancies-between-appsflyer-and-third-party-platforms#postback-restrictions-on-third-party-platforms">Some media sources</Anchor> restrict sharing data with third parties. AppsFlyer doesn't enable the sharing of user-level data acquired through these media sources with any third-party platforms or services. All installs from such media sources are therefore sent as organic. Note that Meta ads doesn't enable the sharing of any data with third-party platforms.

</Accordion>

<div id="the-sdk-was-set-not-to-share-information-with-the-partner" />

<Accordion title="The SDK was set not to share information with the partner">

A sharing filter has been implemented in the SDK to prevent the partner from receiving information. This filter may be activated either by a user's explicit opt-out request or at any other point during the app's lifecycle.

For more information see: <Anchor target="_blank" href="/marketers/docs/apply-privacy-preserving-sdk-methods#prevent-sharing-data-with-networks">Prevent data sharing with third parties</Anchor> and <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setsharingfilterforpartners">setSharingFilterForPartners</Anchor>.

</Accordion>

<div id="miscellaneous" />

## Miscellaneous

<div id="the-postback-was-sent-but-doesnt-show-on-the-partners-platform" />

<Accordion title="The postback was sent but doesn't show on the partner's platform">

In some cases, although AppsFlyer sends postbacks to a partner, they aren't showing it on the partner's side. Is such cases, contact the partner.

**To see if the postback was sent from AppsFlyer:**

1. In AppsFlyer, from the side menu, select **Reports** > **Raw Data Export.**
2. View the relevant report under **Postbacks** (Installs, In-app events, Retargeting conversions, In-app events retargeting).

<Image align="center" alt="postback_reports.JPG" src="https://files.readme.io/21f7ead0f04cf8b67735476348245c5849b638701946236cf649adfa69699df6-14981466637457.png" />

</Accordion>

<div id="the-event-didnt-occur" />

<Accordion title="The event didn't occur or wasn't sent to AppsFlyer">

All events that occurred can be found on the <Anchor target="_blank" href="/marketers/docs/activity-dashboard">**Activity** dashboard</Anchor> and in <Anchor target="_blank" href="/marketers/docs/raw-data-reporting-overview?query=raw%20data%20reports">Raw data reports</Anchor>. An event not showing there means it didn’t occur or it wasn't sent to AppsFlyer.

It could be the event wasn't defined in the SDK. In this case, you won't see it on the platform. Check the SDK configuration.  <Anchor target="_blank" href="/marketers/docs/basic-sdk-integration-guide#recording-in-app-events">defined in the SDK</Anchor>.

If you think the event occurred, check below how to see if it appears in the Activity dashboard or create a Raw data report and look for it there.

**To view the Activity dashboard:**

* In AppsFlyer, from the side menu, select **Analyze** > **Activity** and select the partner and date range.

**To create a raw data report:**

1. In AppsFlyer, from the side menu, select **Reports** > **Raw Data Export**.
2. Click **Create report**.
3. Select the relevant report.
4. Select the date range and any of the necessary fields, and click **Create**.
5. Download the report and look for the event there.

</Accordion>

<div id="differences-in-time-zones" />

<Accordion title="Differences in timezones">

There may be discrepancies in receiving postbacks due to a difference in time zones between the AppsFlyer platform and the partner's platform. AppsFlyer dashboards and reports display according to the selected timezone.

**To see the app timezone in AppsFlyer:**

1. In AppsFlyer, from the side menu, select **Settings** > **App settings**.
2. View the app timezone under **Localization**.

</Accordion>

<div id="srns-missing-advertising-ids-idfagaid" />

<Accordion title="SRNs missing advertising IDs (IDFA/GAID)">

There are a number of <Anchor target="_blank" href="/marketers/docs/self-reporting-networks-srns#does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid">specific cases for SRNs</Anchor> in which AppsFlyer doesn't send postbacks for installs, app opens or in-app events.

</Accordion>

<div id="media-source-restrictions-on-thirdparty-platforms::40092c14" />

<Accordion title="Media source restrictions on third-party platforms">

<Anchor target="_blank" href="/marketers/docs/discrepancies-between-appsflyer-and-third-party-platforms#postback-restrictions-on-third-party-platforms">Some media sources</Anchor> restrict sharing data with third parties. AppsFlyer can't share user-level data acquired through these media sources with any third-party platforms or services. All installs from such media sources are therefore sent as organic. Note that Meta ads doesn't share any data with third-party platforms.

</Accordion>

<div id="advanced-privacy-postbacks" />

<Accordion title="Advanced Privacy postbacks">

When Advanced Privacy (AP) is turned on, user-level data for non-consenting users running iOS 14.5+ is not available via postbacks. Postbacks are sent according to the <Anchor target="_blank" href="/partners/docs/advanced-privacy-guide-postback-macros-for-ad-networks#types-of-templates-for-sending-postbacks">Advanced Privacy template</Anchor>.

</Accordion>

<div id="see-also" />

> 📄 **See also**
>
> <Anchor target="_blank" href="/partners/docs/postback-troubleshooting-for-ad-networks">Postback troubleshooting for ad networks</Anchor>

<div data-zendesk-anchors="activation-toggles=check-the-integration-toggles h_01H9FT385FY1QJC6M2YVMZF2NC=check-the-integration-toggles h_01H9FT385FJ0W62NB6FBB6ASKP=the-activate-partner-toggle-was-turned-off h_01H9FT385FKK7VQ293HH9RANBP=the-inapp-event-postbacks-toggle-was-turned-off event-configuration-issues=check-the-event-configuration h_01H9FT385FW71JV2KKZ22TP6TN=check-the-event-configuration h_01H9FT385FHFX4PNRQVRXX8A5X=the-event-wasnt-configured h_01H9FT385FE4GCP9D5XCNZ1FAR=the-event-was-configured-incorrectly h_01H9FT385FTT97PJ9NN09K0X9F=the-event-was-configured-correctly-but-with-a-condition h_01H9FT385FDEC21CAZ7V9BBT7M=the-event-was-configured-to-send-postbacks-only-to-the-attributed-partner h_01H9FT385G8HSVJWWGKSRKT381=the-event-occurred-outside-of-the-configuration-window h_01H9FT385G84E2A1J64VWG8H4Z=privacy-restrictions h_01H9FT385G3ECF0PXCE6S2GD5A=the-partner-didnt-set-up-advanced-privacy h_01H9FT385G9YMX9BAEYY0XQR4C=media-source-restrictions-on-thirdparty-platforms h_01HG0YAHWJ565C7BAXAXT75ACB=the-sdk-was-set-not-to-share-information-with-the-partner h_01H9FT385GSWRPKEHKJ4HXCX01=miscellaneous h_01H9FT385GTSH1K93WNCARY2BA=the-postback-was-sent-but-doesnt-show-on-the-partners-platform h_01H9FT385G5HK6N2JEE8C6S245=the-event-didnt-occur h_01H9FT385GPVT9WAC6ZTPK6D10=differences-in-time-zones h_01H9FT385G8RXJD25KAQJ28TF6=srns-missing-advertising-ids-idfagaid h_01H9FT385GAYCY615W7M88XJT3=media-source-restrictions-on-thirdparty-platforms::40092c14 h_01JK86ZFXJGPVYJCAAVAY6F4YD=advanced-privacy-postbacks h_01HE7R6G699RG30ZSSQF02AK5Y=see-also" />
