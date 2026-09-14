---
title: "Set up AppsFlyer preload referrer attribution"
excerpt: "Learn how to set up and measure preload referrer campaigns with OEMs, mobile carriers, and app discovery partners using AppsFlyer."
---
At a glance: AppsFlyer uses preload referrer to attribute installs to preload campaigns, where marketers contract with Original Equipment Manufacturers (OEMs), mobile carriers, and app discovery partners to preload their app at the factory or at the time the device is first turned on by the user.

## Overview

In preload campaigns, Original Device Manufacturers (OEMs), mobile carriers, and app discovery partners preload apps on devices before they reach the user. This can be done by the OEM at the factory or by providers upon first device activation.

Preload campaigns allow advertisers to reach a potentially large audience without running online campaigns.

Preload referrer attribution (1 of 3 [preload attribution methods](https://support.appsflyer.com/hc/articles/207447053#preload-campaigns)) gives marketers an accurate and privacy-preserving mechanism to measure the performance of preload campaigns. This method provides marketers with deterministic attribution results and simultaneously ensures that user privacy is preserved since attribution is performed via referrer matching with a referrer generated independently of the device and user identifiers.

The solution provides:

- Transparent support for app updates and app redownloads.
- Visibility and measurement capabilities between the first device activation and the first app launch. This lets you see how many devices were activated with the app preloaded on the devices by a specific partner, and then see when the app is launched for the first time.

## Partners supporting preload referrer campaigns

The information in this article is relevant for advertisers that are integrated with the partners specified in the following table:

| Partner | PID | Preload | Click to download |
| --- | --- | --- | --- |
| [Samsung](/docs/set-up-appsflyer-preload-referrer-attribution#samsung-preload-referrer) | samsung\_int | **✓** |  |
| Digital Turbine On Device | digitalturbine\_int | **✓** | Coming soon |
| Aura from Unity | aura\_int | **✓** | Coming soon |
| Appnext | appnext\_int | **✓** | Coming soon |
| Glance | glance\_int | **✓** | **✓** |

## Preload referrer options

Referrers can be used to attribute installs by preload or by click-to-download. See the table that follows for more details.

AppsFlyer gives the highest priority to preload attribution. This means that if a user engages with other campaigns before opening the app for the first time, the preload campaign is still awarded the attribution. Other engagements are regarded as assisted installs. 

> 📘 Note
>
> You can enable equal priority for preload engagements. This gives deterministic clicks the same attribution priority as preload engagements for the entire preload lookback window, so attribution to the preload campaign can be superseded by another ad engagement.

| Referrer option | Description | UA installs raw data match type |
| --- | --- | --- |
| Preload | - The app is preloaded at the factory or is preloaded the first time the device is activated. Alternatively, a wizard prompts users to download the app when the device is first activated.<br>- A preload event, equivalent to a click, is reported to AppsFlyer when the device is turned on for the first time.<br>- Attribution occurs when the user opens the app for the first time.<br>- The preload event has the highest attribution priority (unless equal attribution priority is turned on). | `preload_rfr` |
| Click to download | - App installation takes place later in the device lifecycle, via push notifications, partner alternative stores, etc.<br>- When the user engages with an ad or with a push message, the app is automatically downloaded and installed on the device without redirecting to an app store.<br>- Attribution is awarded using the AppsFlyer last-click win rules. | `af_referrer` |

## View preload attribution data

Preload/click to download engagement campaign performance data is available as follows:

- **Overview dashboard:** Engagements count as clicks in aggregate reports and dashboards. They are aggregated at the preload partner (media source) and campaign levels.
- **Raw data:** Engagements are available in the clicks reports available only via Data Locker. They're found in the original URL field and can be identified in the af\_engagement\_type parameter as either preload or click\_to\_download. For installs, see the table in the previous section to see how the match type displays in raw data.

## Set up preload referrer attribution

**Prerequisites:**

- Integrate AppsFlyer [Android SDK 6.10.1+](/docs/appsflyer-android-sdk-release-notes).
- Contract with an AppsFlyer preload partner.

**To set up preload referrer attribution**:

1. In AppsFlyer, from the side menu, select **Collaborate** \> **Active Integrations**.
2. Select the preload partner.
3. In the **Integration** tab, turn on **Preload attribution**.
4. Set the **Preload lookback window** duration. Range: 1-180 days.
5. [Optional] Turn on **Preload equal attribution priority**.

This gives deterministic clicks the same attribution priority as preload attribution, meaning that if a deterministic click is registered between the preload referrer engagement and install, the click gets the attribution under the standard last-touch attribution logic, instead of being superseded by the preload referrer.
6. Click **Save Integration**.
7. Let the preload partner know that you are ready to attribute their campaigns.

## Samsung preload referrer

Samsung’s preload referrer integration with AppsFlyer provides you with detailed visibility from the initial app download, to first launch allowing for a clearer understanding of user behavior.

### Set up Samsung preload referrer attribution

To set up Samsung preload referrer attribution, see the [general instructions for preload referrers](/docs/set-up-appsflyer-preload-referrer-attribution#set-up-preload-referrer-attribution).

### Traits and limitations

The traits specific to Samsung preload referrer are as follows:

| Trait | Remarks |
| --- | --- |
| Integration name | samsung\_int |
| SDK version | v6.16.0 |
| Match type | `preload_rfr` |
| Overview dashboard | Engagements count as clicks in aggregate reports and dashboards. They are aggregated at the preload partner (media source) and campaign levels. |
| Raw data reports | - Engagements are available in the clicks reports only via Data Locker.&nbsp;<br>- In the install reports, the preload events are NOT found in the original URL due to Samsung’s privacy restrictions.&nbsp;<br>- They can be identified in the `af_engagement_type` parameter as `preload`. |