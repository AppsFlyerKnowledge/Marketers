---
title: "AppsFlyer attribution model"
excerpt: "Learn how AppsFlyer determines the media source motivating a user to install or re-engage with an app using its attribution model."
---
At a glance: AppsFlyer determines the media source motivating a user to install or re-engage with an app and attributes the user action to that source using the AppsFlyer attribution model.

## What is attribution?

**Attribution** is the act of determining what motivated (caused) a user to install an app or to perform post-install acts like re-engagement and re-attribution. The attribution result is either:

- **A non-organic media source**: The user interacted (usually by way of impression or click) with a media source.
- **Organic**: The user did not interact with a media source. Note! For ease of understanding, we often refer to a user as being _attributed organically_. We know that this is not strictly true, as users installing organically aren't attributed at all.

Attribution is essential to optimizing user acquisition, re-engagement efforts, and results.

## What is an app install?

The **Attribution Model** is a set of rules, that determine how credit for an event is assigned to touchpoints in conversion paths. Each of the players in the app marketing ecosystem, Google Play, App Store, Apple, CTV, PC, and console platforms, ad networks such as Meta ads and X Ads, and mobile measurement companies, have their own attribution models. Each counts installs and events differently.

What's important is not the difference between the models but rather that the rules are clear and are implemented in a manner that is unbiased. Enabling advertisers to optimize campaigns and compare the quality of user performance.

It is important to understand the models and rules of the players you work with. Most important is to understand the model and nuances of the methods supported by AppsFlyer.

In AppsFlyer, an attributable event occurs when any of the following occur:

- In the context of user acquisition **:** An **install** is recorded and attributed after the user downloads and launches the app. This means that in AppsFlyer, the **timestamp of an app install is the first launch**. In contrast, ad networks use the engagement time and App stores use the download time.
- In the context of [retargeting](https://support.appsflyer.com/hc/articles/207447053#retargeting-attribution):
  - **Re-engagement**
  - **Re-attribution**

## Attribution methods

AppsFlyer uses a number of attribution methods, listed in the table that follows:

| Method | Uses device ID | Technique | Attributed by | Android (Google Play and third-party stores) | iOS | Universal Windows Platform (UWP) | CTV, PC, and console platforms (3) |
| --- | --- | --- | --- | --- | --- | --- | --- |
| [Referrer](/docs/appsflyer-attribution-model#install-referrer-android-only) (1) | No | Deterministic | AppsFlyer | Yes (2) | No | Yes | No |
| [Device ID matching](/docs/appsflyer-attribution-model#device-id-matching) (1) | Yes | Deterministic | AppsFlyer | Yes | Yes | Yes | Yes |
| [Probabilistic modeling](/docs/appsflyer-attribution-model#probabilistic-modeling) (1) | No | Probabilistic | AppsFlyer | Yes | Yes | No | Yes |
| [Preload](/docs/appsflyer-attribution-model#preload-campaigns) (1) | No | Deterministic | AppsFlyer | Yes | No | Yes | No |
| [SKAdNetwork (SKAN)](https://support.appsflyer.com/hc/articles/360011420698) | No | Deterministic | Apple | No | Yes | No | No |
| [Apple Search Ads](https://support.appsflyer.com/hc/articles/213747963) (1) | No | Deterministic | Apple | No | Yes | No | No |
| [Deep link](/docs/appsflyer-attribution-model#deep-link) (1) | No | Deterministic | AppsFlyer | Yes | Yes | Yes | No |

(1) Sometimes referred to as the "Classic" attribution method in AppsFlyer dashboards and reports.  
(2) Supported by some third-party stores.  
(3) See [full list of CTV, PC, and console platforms](https://support.appsflyer.com/hc/articles/4404083608849-Connected-TV-CTV-and-over-the-top-OTT-overview#list-of-supported-ctv-and-gaming-device-types).

### Attribution method priorities (Attribution waterfall)

Upon a new install, if there is more than one valid engagement, **AppsFlyer prioritizes clicks over impressions, and deterministic over probabilistic methods**. The attribution methods are utilized according to the priorities shown in the chart.

<Image src="https://files.readme.io/8110571047a972a247d21d5b34d64c3afd010fd733f625ca1321cff93061e374-37555863998865.png" alt="watefall.png" />

Find below detailed descriptions of AppsFlyer attribution models.

### Install referrer (Android only)

- Android apps downloaded from Google Play and some other app stores are attributed by the install referrer method. The referrer provides the original URL, clicked before redirecting to the Android store. This is the primary method for Android attribution. Currently, Google Play, Huawei app store, Samsung Galaxy Store, and Xiaomi GetApps Store support install referrer attribution. [Alternative app store attribution using the referrer.](https://support.appsflyer.com/hc/articles/207447023#referrer-implementation%E2%80%94thirdparty-android-app-stores)
- [Meta install referrer:](https://support.appsflyer.com/hc/articles/207033826-Meta-ads-integration-setup#Meta_install_referrer_anchor) AppsFlyer supports Meta ads attribution for Android apps by receiving ad campaign metadata from a device’s local storage. This data is used for attribution measurement (Meta on-device attribution).

### Device ID matching

A classic attribution method in which the ad network, which has access to the user's device, sends the device ID to AppsFlyer on the click URL, or when notifying AppsFlyer that an impression has been served. This allows AppsFlyer to match the click device ID with the device ID fetched by the AppsFlyer SDK.

Device ID matching is the primary attribution method on iOS, but requires ATT consent.

Available IDs are:

- **iOS devices**: IDFA, IDFV
- **Android devices: having Google Play services:** GAID
- **Android devices without Google Play services:** OAID, Android ID, IMEI, Fire ID

Device IDs can be hashed using SHA1 or MD5 on attribution links.

### Device ID matching for self-reporting networks

A classic attribution method in which upon the first app launch, AppsFlyer checks in the app settings if traffic is expected from any of the [self-reporting networks](https://support.appsflyer.com/hc/articles/360001546905-Self-Reporting-Networks#srns-integrated-with-appsflyer) (SRNs), like Meta ads, Snapchat, and Google Ads.

AppsFlyer queries the relevant SRNs using the unique device ID of the new install, where the device ID is available, and ATT consent has been granted on iOS. The query uses Mobile Measurement Partners (MMP) APIs as defined by the SRNs. Based on the response, AppsFlyer may attribute the new uses to an SRN.

### Probabilistic modeling

AppsFlyer uses probabilistic modeling as a privacy-preserving statistical method to report on how app developers’ marketing campaigns are performing. It produces aggregate campaign-level performance reports for app developers.

**Implementation characteristics**

- Uses statistics and is not based on unique IDs.
- It estimates how many installs or engagements followed a developer’s own marketing campaigns – ads, website links, emails, QR codes, SMS, or other owned media – for that developer’s own app.
- It uses only the signals necessary to produce an aggregate report.
- The output is a campaign performance report, not an identification of any individual device or user.
- Deterministic attribution methods, i.e., clicks with referrer or ID matching, are given priority if they occur within the lookback window.

### Preload campaigns

A classic attribution method for preload campaigns, when apps are installed on a user's device by a preload partner, either at the factory or upon device activation. Preload partners can be:

- Original Equipment Manufacturers (OEMs)
- App discovery platforms
- Mobile carriers

There are 3 methods to attribute preload campaigns. All three methods can be used simultaneously; they don't interfere with each other’s mechanisms.

The 3 methods and some of the main specifications are outlined in the table that follows. Click the links to learn more about each preload method.

| Preload attribution method | Use case | Device activation-to-app launch info\* | Lookback window\*\* | Match-type in raw data |
| --- | --- | --- | --- | --- |
| [AppsFlyer referrer](https://support.appsflyer.com/hc/articles/4543811207313)\* | - Preloaded in factory<br/>- Preloaded upon device activation | Yes | - Up to 180 days<br/>- Default is 90 days | - Preload: preload\_rfr<br/>- Click to download: af\_referrer |
| [Google Play auto-install](https://support.appsflyer.com/hc/articles/4404557237649)\*\* | Preloaded upon device activation (for Google Play apps) | No | - Up to 180 days<br/>- Default is 90 days | preload\_pai |
| [Preload in factory via System Property or manifest (Android)](https://support.appsflyer.com/hc/articles/207032166)\*\* | - Preloaded in factory<br/>- Preloaded upon device activation | No | No limit | preload\_conf |

\* The AppsFlyer referrer preload solution provides visibility and measurement capabilities between the first device activation and the first app launch. This lets you see how many devices were activated with the app preloaded on the devices by a specific partner, and then see when the app is launched for the first time.  
\*\* For the two other methods, attribution is determined only after the user launches the app for the first time, the number of devices that had the app installed before the first launch isn't available.  
\*\* It can take days or weeks, starting from the first time the user turns on their device until they launch the preloaded app for the first time. Consequently, AppsFlyer gives preload campaigns the highest priority in determining attribution, with longer lookback windows.

### Deep link

A classic attribution method for re-engagements only, when users aren't redirected to an app store to download the app. Therefore, the information in the URL can be directly connected to the click (and subsequent app open). This attribution method is referred to as deep link, since it's the deep link URL that carries the information used to attribute the re-engagement.

### Attribution methods per media source and AppsFlyer feature

See the sections that follow for a full breakdown of which particular attribution methods are supported, depending on:

- Media source: owned or paid
- AppsFlyer feature used
- User device: Android or iOS

#### Owned media

| Media source | Feature | Attribution method | |
| --- | --- | --- | --- |
| | | Android | iOS |
| Owned media: email (including ESPs), SMS, social media posts, influencers/affiliates, print, etc. | [OneLink](https://support.appsflyer.com/hc/articles/115005248543) | - Install referrer<br/>- Probabilistic modeling | Probabilistic modeling |
| Owned mobile website/landing page with paid or organic incoming traffic | [Smart Banners](https://support.appsflyer.com/hc/articles/360000764837) | - Install referrer<br/>- Probabilistic modeling | Probabilistic modeling |
| | [OneLink Smart Script](https://support.appsflyer.com/hc/articles/360000677217) | - Install referrer<br/>- Probabilistic modeling | Probabilistic modeling |
| Owned mobile apps | [User invites/referral](https://support.appsflyer.com/hc/articles/115004480866) | - Install referrer<br/>- Probabilistic modeling | Probabilistic modeling |
| | [Cross-promotion](https://support.appsflyer.com/hc/articles/115004481946) | - Install referrer<br/>- Device ID matching | Device ID matching (subject to ATT consent) |

#### Paid media

| Media source | Attribution method | | |
| --- | --- | --- | --- |
| | Android | iOS | **CTV, PC, and console platforms** |
| [SRNs](https://support.appsflyer.com/hc/articles/360001546905) | Device ID matching | - Device ID matching (subject to ATT consent)<br/>- SKAdNetwork (iOS 14+) | Device ID matching |
| - Ad networks (non-SRNs) via [attribution links for partners](https://support.appsflyer.com/hc/articles/4410395957521#attribution-link-tab)<br/>- CTV, PC, and console platforms | - Install referrer<br/>- Device ID matching<br/>- Probabilistic modeling | - Device ID matching (subject to ATT consent)<br/>- Probabilistic modeling <br/>- SKAdNetwork (iOS 14+) | |
| [Pre-installed on device](https://support.appsflyer.com/hc/articles/207032166) | Pre-installs | -- | |

## User engagement attribution types

Attribution is performed based on click-through and view-through engagements, using AppsFlyer's various campaign measurement methods.

### Click-through attribution

Most installs are the result of user clicks on ads, like banners, videos, and interstitials.

Upon the ad click, a click lookback window opens having a default duration of 7 days. Installs occurring within the lookback window period are non-organic and are attributed to the media source. Installs that occur after the duration of the lookback window are considered as organic installs. Often referred to as being organically attributed.

- A seven-day click lookback window is regarded as the industry standard. Set the window duration in accordance with your agreement with the media source.
- Align SRN lookback windows with the duration determined by the SRN.

| **Attribution type** | **Attribution method** | Range | Default |
| --- | --- | --- | --- |
| Click-Through<br/>(All integrated partners) | Referrer, ID Matching | 1–30 Days | 7 Days |
| Probabilistic modeling | 0–24 Hours | - Adaptive<br/>- Determined by AppsFlyer |

[Learn more about lookback windows](https://support.appsflyer.com/hc/articles/208338403-What-is-AppsFlyer-s-Configurable-Attribution-Lookback-Window-)

### View-through attribution

Users who view ads but do not click on them can be attributed to the ad network serving the ad.

The lookback window for view-through attribution:

- is shorter than that of click-through attribution
- is configurable.

This is especially helpful for video ad networks that traditionally have low CTRs on their video ads, but also for traditional ad networks serving regular ads.

In cases where both a click and an impression occur, the **click always prevails**, as it's an active engagement.

| **Attribution type** | **Attribution method** | **Range** | **Default** |
| --- | --- | --- | --- |
| View-through (for [selected integrated partners](https://support.appsflyer.com/hc/articles/210084473#view-vta-partner-list)) | ID Matching | 0-24 Hours | 1 Day |
| Probabilistic modeling | 0-24 Hours | - Adaptive<br/>- Determined by AppsFlyer |

**To enable the view-through attribution:**

- Set the lookback window in the [configuration window](https://support.appsflyer.com/hc/articles/4410395957521#viewthrough-attribution-lookback-window).

[Learn more about view-through attribution](https://support.appsflyer.com/hc/articles/210084473)

### Engaged click attribution

Engaged clicks occur when users click an ad and remain in the same context—engaging with the ad—without being redirected to the app store or launching the app. For example, interactions may include staying within a playable ad, interacting with in-ad elements, or continuing to browse content within the ad container. For more information, see: [About enhanced engagement types.](/docs/about-enriched-engagement-types)

- The engaged click lookback window for ID matching attribution is 1–7 days. The default is 2 days.
- The lookback window for probabilistic modeling is 0–24 hours. The default is adaptive.
- Set the window duration in accordance with your agreement with the media source.
- Engaged click is supported by selected integrated partners.
- Engaged clicks share the same attribution priority as click-to-download and click-to-app.

| Attribution type | Attribution method | Range | Default |
| --- | --- | --- | --- |
| Engaged click (for selected integrated partners) | ID Matching | 1–7 Days<br/>1-23 hours | 2 Days |
| | Probabilistic modeling | 0–24 Hours | - Adaptive<br/>- Determined by AppsFlyer |

[Learn more about lookback windows](https://support.appsflyer.com/hc/articles/208338403-What-is-AppsFlyer-s-Configurable-Attribution-Lookback-Window-)

### Engaged view attribution

Engaged views occur when users view an ad and take a qualifying action—such as watching a video beyond a certain threshold or interacting with an ad unit—without clicking. These actions signal intent and are used to attribute the install. For more information, see: [About enhanced engagement types.](/docs/about-enriched-engagement-types)

- The engaged view lookback window is 0–24 hours for both deterministic and probabilistic attribution.
- The default lookback window for deterministic attribution is 2 days.
- Engaged view is supported by selected integrated partners.
- Engaged views share the same attribution priority as engaged clicks and click-to-app.

| Attribution type | Attribution method | Range | Default |
| --- | --- | --- | --- |
| Engaged view (for selected integrated partners) | ID Matching | 1–7 Days<br/>1-23 hours | 2 Days |
| | Probabilistic modeling | 0–24 Hours | - Adaptive<br/>- Determined by AppsFlyer |

**To enable engaged view attribution:**

- Set the lookback window in the [configuration window](https://support.appsflyer.com/hc/articles/4410395957521#viewthrough-attribution-lookback-window).

[Learn more about view-through attribution](https://support.appsflyer.com/hc/articles/210084473)

## Advanced attribution topics

### In-app events

AppsFlyer uses the device ID or unique AppsFlyer ID for attributions (an app install, reinstall, or re-attribution) to **attribute in-app events to the media source**. Advertisers can use this information to follow user journeys in their app's raw data. In aggregate day, the device ID/AppsFlyer ID is used to calculate the number of unique users, for example the number of unique users that perform an in-app event.

For more information about event attribution, click [here](https://support.appsflyer.com/hc/articles/115005544169-Rich-in-app-events-Overview?query=in%20app%20event#how-does-appsflyer-attribute-events).

### Assisted installs

AppsFlyer fully attributes only one media source per install, usually using the last ad click or the last ad impression (if there were no clicks).

Assisted Installs (AKA multi-touch attribution) are installs where the media source/campaign was not the last touchpoint but touched the user before the install and the touch took place within the attribution lookback window.

Assisting networks are shown as contributors to the install in AppsFlyer.

For more information, click [here](https://support.appsflyer.com/hc/articles/207040506-How-Are-Assisted-Installs-Calculated-Multi-Touch-Attribution-).

### Reinstalls

A reinstall occurs when a user installs the app, uninstalls it, and then reinstalls it. Reinstall attribution is regulated by the [re-attribution window](https://support.appsflyer.com/hc/articles/115002587066-) as follows:

- If the reinstall occurs after the expiry of the re-attribution window: a new install is recorded.
- If the reinstall occurs during the re-attribution window, one of the following applies:
  - If the user engaged with a retargeting campaign before the reinstall: a [retargeting reinstall](https://support.appsflyer.com/hc/articles/207033786) (AKA re-attribution) is recorded.
  - If the user did not engage with a campaign or engaged with a UA campaign: no install is recorded. Depending on the [**Post Reinstall Events Attribution**](https://support.appsflyer.com/hc/articles/10164066030737#overview) state, in-app events of these reinstalling users are either attributed to organic or to the original install.

For device testing and multiple installs, [register](https://support.appsflyer.com/hc/articles/207031996) the device in AppsFlyer. If you don't register the device only the first install is recorded.

Note that AppsFlyer enables better accuracy for attributing iOS reinstalls without advertiser ID. You can enable this feature on the [App Settings page](https://support.appsflyer.com/hc/articles/211719806-App-settings-#reinstall-detection-using-ondevice-storage-ios-only).

#### Reinstalling iOS apps that are backed up in iCloud

When an application is backed up using iCloud and later restored (on the same device or on another device), AppsFlyer doesn't count it as a new install or reinstall. A user who restores an app from iCloud maintains their AppsFlyer ID and attribution data.

### Retargeting attribution

<Image src="https://files.readme.io/64b8d9f5040daa281ae13f0855749ab4a88a2e7e8616d6ada37975899db92c80-31937591646097.png" alt="Retargeting_-_Flow__2_.png" />

A user who re-installs an app within the [re-attribution window](https://support.appsflyer.com/hc/articles/115002587066-Re-Attribution-Window) (90 days by default) is considered a re-attribution. If this install occurs after engaging with a retargeting campaign, it is recorded as a retargeting reinstall AKA re-attribution and is reported in [retargeting](https://support.appsflyer.com/hc/articles/207033786).

### App updates

- When existing users update the app to a subsequent version, this is not treated as a countable attribution event, if the user was previously attributed by AppsFlyer. Note! If you migrate to AppsFlyer from a different MMP existing users on the first app-open, after migration, are attributed to organic.
- Metrics relating to the number of users per app version are available in the [SDK Information dashboard.](https://support.appsflyer.com/hc/articles/115000805366-SDK-Information-Page)