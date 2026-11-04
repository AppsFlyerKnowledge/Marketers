---
title: AppsFlyer attribution model
metadata:
  keywords:
    - Attribution
    - NativeTrack
    - Look-Back
    - Twiiter
    - Multi-Channel
    - Re-Install
    - Facebook
    - media source
    - Advertisers
    - Ad Networks
    - reinstall
    - branch
    - attribution determination
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2015-12-24T10:54:37Z'
  edited_at: '2026-08-12T11:02:01Z'
  id: 207447053
  locale: en-us
  section: Attribution concepts
  section_id: 6551394235409
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/207447053-AppsFlyer-attribution-model
---
> **At a glance:** AppsFlyer determines the media source motivating a user to install or re-engage with an app and attributes the user action to that source using the AppsFlyer attribution model.

[![](https://files.readme.io/20b5c0674ce4b20df7c82398d7a769274dd8467d129adbaad0d40e4f37d39091-31937603228177.png)](https://files.readme.io/20b5c0674ce4b20df7c82398d7a769274dd8467d129adbaad0d40e4f37d39091-31937603228177.png)

<div id="what-is-attribution" />

## What is attribution?

**Attribution** is the act of determining what motivated (caused) a user to install an app or to perform post-install acts like re-engagement and re-attribution. The attribution result is either:

* **A non-organic media source**: The user interacted (usually by way of impression or click) with a media source.
* **Organic**: The user did not interact with a media source. Note! For ease of understanding, we often refer to a user as being *attributed organically*. We know that this is not strictly true, as users installing organically aren't attributed at all.

Attribution is essential to optimizing user acquisition, re-engagement efforts, and results.

<div id="what-is-an-app-install" />

## What is an app install?

The **Attribution Model** is a set of rules, that determine how credit for an event is assigned to touchpoints in conversion paths. Each of the players in the app marketing ecosystem, Google Play, App Store, Apple, CTV, PC, and console platforms, ad networks such as Meta ads and X Ads, and mobile measurement companies, have their own attribution models. Each counts installs and events differently.

What's important is not the difference between the models but rather that the rules are clear and are implemented in a manner that is unbiased. Enabling advertisers to optimize campaigns and compare the quality of user performance.

It is important to understand the models and rules of the players you work with. Most important is to understand the model and nuances of the methods supported by AppsFlyer.

In AppsFlyer, an attributable event occurs when any of the following occur:

* In the context of user acquisition: An **install** is recorded and attributed after the user downloads and launches the app. This means that in AppsFlyer, the **timestamp of an app install is the first launch**. In contrast, ad networks use the engagement time and App stores use the download time.
* In the context of [retargeting](/docs/appsflyer-attribution-model#retargeting-attribution):
  * **Re-engagement**
  * **Re-attribution**

<div id="attribution-methods" />

## Attribution methods

AppsFlyer uses a number of attribution methods, listed in the table that follows:

<table><tbody><tr><td>Method</td><td>Uses device ID</td><td>Technique</td><td>Attributed by</td><td>Android (Google Play and third-party stores)</td><td>iOS</td><td>Universal Windows Platform (UWP)</td><td>CTV, PC, and console platforms (3)</td></tr><tr><td><a href="#install-referrer-android-only">Referrer</a> (1)</td><td>No</td><td>Deterministic</td><td>AppsFlyer</td><td>Yes (2)</td><td>No</td><td>Yes</td><td>No</td></tr><tr><td><a href="#device-id-matching">Device ID matching</a> (1)</td><td>Yes</td><td>Deterministic</td><td>AppsFlyer</td><td>Yes</td><td>Yes</td><td>Yes</td><td>Yes</td></tr><tr><td><a href="#probabilistic-modeling">Probabilistic modeling</a> (1)</td><td>No</td><td>Probabilistic</td><td>AppsFlyer</td><td>Yes</td><td>Yes</td><td>No</td><td>Yes</td></tr><tr><td><a href="#preload-campaigns">Preload</a> (1)</td><td>No</td><td>Deterministic</td><td>AppsFlyer</td><td>Yes</td><td>No</td><td>Yes</td><td>No</td></tr><tr><td><a href="./skadnetwork-skan-solution-guide" target="_blank">SKAdNetwork (SKAN)</a></td><td>No</td><td>Deterministic</td><td>Apple</td><td>No</td><td>Yes</td><td>No</td><td>No</td></tr><tr><td><a href="./apple-ads-integration-setup" target="_blank">Apple Search Ads</a> (1)</td><td>No</td><td>Deterministic</td><td>Apple</td><td>No</td><td>Yes</td><td>No</td><td>No</td></tr><tr><td><a href="#deep-link">Deep link</a> (1)</td><td>No</td><td>Deterministic</td><td>AppsFlyer</td><td>Yes</td><td>Yes</td><td>Yes</td><td>No</td></tr><tr><td colspan="8">(1) Sometimes referred to as the "Classic" attribution method in AppsFlyer dashboards and reports.<br/>(2) Supported by some third-party stores.<br/>(3) See <a href="./ctv-pc-and-console-platform-attribution-concepts#supported-platforms" target="_blank">full list of CTV, PC, and console platforms</a>.</td></tr></tbody></table>

<div id="attribution-method-priorities-attribution-waterfall" />

### Attribution method priorities (Attribution waterfall)

Upon a new install, if there is more than one valid engagement, **AppsFlyer prioritizes clicks over impressions, and deterministic over probabilistic methods**. The attribution methods are utilized according to the priorities shown in the chart.

[<Image alt="watefall.png" src="https://files.readme.io/8110571047a972a247d21d5b34d64c3afd010fd733f625ca1321cff93061e374-37555863998865.png" width="1378px" />](https://files.readme.io/8110571047a972a247d21d5b34d64c3afd010fd733f625ca1321cff93061e374-37555863998865.png)

Find below detailed descriptions of AppsFlyer attribution models.

<div id="install-referrer-android-only" />

<Accordion title="Install referrer (Android only)">

* Android apps downloaded from Google Play and some other app stores are attributed by the install referrer method. The referrer provides the original URL, clicked before redirecting to the Android store. This is the primary method for Android attribution. Currently, Google Play, Huawei app store, Samsung Galaxy Store, and Xiaomi GetApps Store support install referrer attribution. <Anchor target="_blank" href="/marketers/docs/set-up-multi-store-android-attribution#referrer-implementation-thirdparty-android-app-stores">Alternative app store attribution using the referrer.</Anchor>
* <Anchor target="_blank" href="/marketers/docs/meta-ads-integration-setup#Meta_install_referrer_anchor">Meta install referrer:</Anchor> AppsFlyer supports Meta ads attribution for Android apps by receiving ad campaign metadata from a device’s local storage. This data is used for attribution measurement (Meta on-device attribution).

</Accordion>

<div id="device-id-matching" />

<Accordion title="Device ID matching">

A classic attribution method in which the ad network, which has access to the user's device, sends the device ID to AppsFlyer on the click URL, or when notifying AppsFlyer that an impression has been served. This allows AppsFlyer to match the click device ID with the device ID fetched by the AppsFlyer SDK.

Device ID matching is the primary attribution method on iOS, but requires ATT consent.

Available IDs are:

* **iOS devices**: IDFA, IDFV
* **Android devices: having Google Play services:** GAID
* **Android devices without Google Play services:** OAID, Android ID, IMEI, Fire ID

Device IDs can be hashed using SHA1 or MD5 on attribution links.

</Accordion>

<div id="device-id-matching-for-selfreporting-networks" />

<Accordion title="Device ID matching for self-reporting networks">

A classic attribution method in which upon the first app launch, AppsFlyer checks in the app settings if traffic is expected from any of the <Anchor target="_blank" href="/marketers/docs/self-reporting-networks-srns#srns-integrated-with-appsflyer">self-reporting networks</Anchor> (SRNs), like Meta ads, Snapchat, and Google Ads.

AppsFlyer queries the relevant SRNs using the unique device ID of the new install, where the device ID is available, and ATT consent has been granted on iOS. The query uses Mobile Measurement Partners (MMP) APIs as defined by the SRNs. Based on the response, AppsFlyer may attribute the new uses to an SRN.

</Accordion>

<div id="probabilistic-modeling" />

<Accordion title="Probabilistic modeling">

AppsFlyer uses probabilistic modeling as a privacy-preserving statistical method to report on how app developers’ marketing campaigns are performing. It produces aggregate campaign-level performance reports for app developers.

**Implementation characteristics**

* Uses statistics and is not based on unique IDs.
* It estimates how many installs or engagements followed a developer’s own marketing campaigns – ads, website links, emails, QR codes, SMS, or other owned media – for that developer’s own app.
* It uses only the signals necessary to produce an aggregate report.
* The output is a campaign performance report, not an identification of any individual device or user.
* Deterministic attribution methods, i.e., clicks with referrer or ID matching, are given priority if they occur within the lookback window.

</Accordion>

<div id="preload-campaigns" />

<Accordion title="Preload campaigns">

A classic attribution method for preload campaigns, when apps are installed on a user's device by a preload partner, either at the factory or upon device activation. Preload partners can be:

* Original Equipment Manufacturers (OEMs)
* App discovery platforms
* Mobile carriers

There are 3 methods to attribute preload campaigns. All three methods can be used simultaneously; they don't interfere with each other’s mechanisms.

The 3 methods and some of the main specifications are outlined in the table that follows. Click the links to learn more about each preload method.

<table><thead><tr><th>Preload attribution method</th><th>Use case</th><th>Device activation-to-app launch info\*</th><th>Lookback window\*\*</th><th>Match-type in raw data</th></tr></thead><tbody><tr><td><a href="./set-up-appsflyer-preload-referrer-attribution" target="_blank">AppsFlyer referrer</a>\*</td><td><ul><li>Preloaded in factory</li><li>Preloaded upon device activation</li></ul></td><td>Yes</td><td><ul><li>Up to 180 days</li><li>Default is 90 days</li></ul></td><td><ul><li>Preload: preload_rfr</li><li>Click to download: af_referrer</li></ul></td></tr><tr><td><a href="./measure-preload-campaigns-with-google-play-install" target="_blank">Google Play auto-install</a>\*\*</td><td>Preloaded upon device activation (for Google Play apps)</td><td>No</td><td><ul><li>Up to 180 days</li><li>Default is 90 days</li></ul></td><td>preload_pai</td></tr><tr><td><a href="./appsflyer-factory-preinstall-using-manifest-android" target="_blank">Preload in factory via System Property or manifest (Android)</a>\*\*</td><td><ul><li>Preloaded in factory</li><li>Preloaded upon device activation</li></ul></td><td>No</td><td>No limit</td><td>preload_conf</td></tr><tr><td colspan="5"><p>\* The AppsFlyer referrer preload solution provides visibility and measurement capabilities between the first device activation and the first app launch. This lets you see how many devices were activated with the app preloaded on the devices by a specific partner, and then see when the app is launched for the first time.</p><p>For the two other methods, attribution is determined only after the user launches the app for the first time, the number of devices that had the app installed before the first launch isn't available.</p><p>\*\* It can take days or weeks, starting from the first time the user turns on their device until they launch the preloaded app for the first time. Consequently, AppsFlyer gives preload campaigns the highest priority in determining attribution, with longer lookback windows.</p></td></tr></tbody></table>

</Accordion>

<div id="deep-link" />

<Accordion title="Deep link">

A classic attribution method for re-engagements only, when users aren't redirected to an app store to download the app. Therefore, the information in the URL can be directly connected to the click (and subsequent app open). This attribution method is referred to as deep link, since it's the deep link URL that carries the information used to attribute the re-engagement.

</Accordion>

<div id="attribution-methods-per-media-source-and-appsflyer-feature" />

### Attribution methods per media source and AppsFlyer feature

See the sections that follow for a full breakdown of which particular attribution methods are supported, depending on:

* Media source: owned or paid
* AppsFlyer feature used
* User device: Android or iOS

<div id="owned-media" />

<Accordion title="Owned media">

<table><thead><tr><th rowspan="2">Media source</th><th rowspan="2">Feature</th><th colspan="2">Attribution method</th></tr><tr><th>Android</th><th>iOS</th></tr></thead><tbody><tr><td>Owned media: email (including ESPs), SMS, social media posts, influencers/affiliates, print, etc.</td><td><a href="./onelink-guide" target="_blank"><span>OneLink</span></a></td><td><ul><li>Install referrer</li><li>Probabilistic modeling</li></ul></td><td>Probabilistic modeling</td></tr><tr><td rowspan="2">Owned mobile website/landing page with paid or organic incoming traffic</td><td><a href="./smart-banners-mobile-web-to-app-for-marketers" target="_blank">Smart Banners</a></td><td><ul><li>Install referrer</li><li>Probabilistic modeling</li></ul></td><td>Probabilistic modeling</td></tr><tr><td><a href="./onelink-smart-script-overview" target="_blank">OneLink Smart Script</a></td><td><ul><li>Install referrer</li><li>Probabilistic modeling</li></ul></td><td>Probabilistic modeling</td></tr><tr><td rowspan="2">Owned mobile apps</td><td><a href="./user-invite-attribution" target="_blank">User invites/referral</a></td><td><ul><li>Install referrer</li><li>Probabilistic modeling</li></ul></td><td>Probabilistic modeling</td></tr><tr><td><a href="./cross-promotion-attribution-for-marketers" target="_blank">Cross-promotion</a></td><td><ul><li>Install referrer</li><li>Device ID matching</li></ul></td><td>Device ID matching (subject to ATT consent)</td></tr></tbody></table>

</Accordion>

<div id="paid-media" />

<Accordion title="Paid media">

<table><thead><tr><th rowspan="2">Media source</th><th colspan="3">Attribution method</th></tr><tr><th>Android</th><th>iOS</th><th><strong>CTV, PC, and console platforms</strong></th></tr></thead><tbody><tr><td><a href="./self-reporting-networks-srns" target="_blank">SRNs</a></td><td>Device ID matching</td><td><ul><li>Device ID matching (subject to ATT consent)</li><li>SKAdNetwork (iOS 14+)</li></ul></td><td>Device ID matching</td></tr><tr><td><ul><li>Ad networks (non-SRNs) via <a href="./set-up-an-integrated-partner#attribution-link-tab" target="_blank">attribution links for partners</a></li><li><span>CTV, PC, and console platforms</span></li></ul></td><td><ul><li>Install referrer</li><li>Device ID matching</li><li>Probabilistic modeling</li></ul></td><td><ul><li>Device ID matching (subject to ATT consent)</li><li>Probabilistic modeling </li><li>SKAdNetwork (iOS 14+)</li></ul></td><td> </td></tr><tr><td><a href="./appsflyer-factory-preinstall-using-manifest-android" target="_blank">Pre-installed on device</a></td><td>Pre-installs</td><td>--</td><td> </td></tr></tbody></table>

</Accordion>

<div id="user-engagement-attribution-types" />

## User engagement attribution types

Attribution is performed based on click-through and view-through engagements, using AppsFlyer's various campaign measurement methods.

<div id="clickthrough-attribution" />

<Accordion title="Click-through attribution">

Most installs are the result of user clicks on ads, like banners, videos, and interstitials.

Upon the ad click, a click lookback window opens having a default duration of 7 days. Installs occurring within the lookback window period are non-organic and are attributed to the media source. Installs that occur after the duration of the lookback window are considered as organic installs. Often referred to as being organically attributed.

* A seven-day click lookback window is regarded as the industry standard. Set the window duration in accordance with your agreement with the media source.
* Align SRN lookback windows with the duration determined by the SRN.

<table><thead><tr><th rowspan="2"><strong>Attribution type</strong></th><th rowspan="2"><strong>Attribution method</strong></th><th rowspan="2">Range</th><th rowspan="2">Default</th></tr></thead><tbody><tr><td rowspan="2"><p>Click-Through</p><p>(All integrated partners)</p></td><td>Referrer, ID Matching</td><td>1–30 Days</td><td>7 Days</td></tr><tr><td>Probabilistic modeling</td><td>0–24 Hours</td><td><ul><li>Adaptive</li><li>Determined by AppsFlyer</li></ul></td></tr></tbody></table>

<Anchor target="_blank" href="/marketers/docs/set-up-lookback-windows">Learn more about lookback windows</Anchor>

</Accordion>

<div id="viewthrough-attribution" />

<Accordion title="View-through attribution">

Users who view ads but do not click on them can be attributed to the ad network serving the ad.

The lookback window for view-through attribution:

* is shorter than that of click-through attribution
* is configurable.

This is especially helpful for video ad networks that traditionally have low CTRs on their video ads, but also for traditional ad networks serving regular ads.

In cases where both a click and an impression occur, the **click always prevails**, as it's an active engagement.

<table><thead><tr><th><strong>Attribution type</strong></th><th><strong>Attribution method</strong></th><th><strong>Range</strong></th><th><strong>Default</strong><br/> </th></tr></thead><tbody><tr><td rowspan="2"><p>View-through (for <a href="./measure-view-through-engagements#view-vta-partner-list" target="_blank">selected integrated partners</a>)</p></td><td>ID Matching</td><td>0-24 Hours</td><td>1 Day</td></tr><tr><td>Probabilistic modeling</td><td>0-24 Hours</td><td><ul><li>Adaptive</li><li>Determined by AppsFlyer</li></ul></td></tr></tbody></table>

**To enable the view-through attribution:**

* Set the lookback window in the <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#view-through-attribution-lookback-window">configuration window</Anchor>.

<Anchor target="_blank" href="/marketers/docs/measure-view-through-engagements">Learn more about view-through attribution</Anchor>

</Accordion>

<div id="engaged-click-attribution" />

<Accordion title="Engaged click attribution">

Engaged clicks occur when users click an ad and remain in the same context—engaging with the ad—without being redirected to the app store or launching the app. For example, interactions may include staying within a playable ad, interacting with in-ad elements, or continuing to browse content within the ad container. For more information, see: <Anchor target="_blank" href="/marketers/docs/about-enriched-engagement-types">About enhanced engagement types.</Anchor>

* The engaged click lookback window for ID matching attribution is 1–7 days. The default is 2 days.
* The lookback window for probabilistic modeling is 0–24 hours. The default is adaptive.
* Set the window duration in accordance with your agreement with the media source.
* Engaged click is supported by selected integrated partners.
* Engaged clicks share the same attribution priority as click-to-download and click-to-app.

| Attribution type | Attribution method | Range | Default |
| --- | --- | --- | --- |
| Engaged click (for selected integrated partners) | ID Matching | 1–7 Days  <br />1-23 hours | 2 Days |
|  | Probabilistic modeling | 0–24 Hours | <ul><li>Adaptive</li><li>Determined by AppsFlyer</li></ul> |

<Anchor target="_blank" href="/marketers/docs/set-up-lookback-windows">Learn more about lookback windows</Anchor>

</Accordion>

<div id="engaged-view-attribution" />

<Accordion title="Engaged view attribution">

Engaged views occur when users view an ad and take a qualifying action—such as watching a video beyond a certain threshold or interacting with an ad unit—without clicking. These actions signal intent and are used to attribute the install. For more information, see: <Anchor target="_blank" href="/marketers/docs/about-enriched-engagement-types">About enhanced engagement types.</Anchor>

* The engaged view lookback window is 0–24 hours for both deterministic and probabilistic attribution.
* The default lookback window for deterministic attribution is 2 days.
* Engaged view is supported by selected integrated partners.
* Engaged views share the same attribution priority as engaged clicks and click-to-app.

| Attribution type | Attribution method | Range | Default |
| --- | --- | --- | --- |
| Engaged view (for selected integrated partners) | ID Matching | 1–7 Days  <br />1-23 hours | 2 Days |
|  | Probabilistic modeling | 0–24 Hours | <ul><li>Adaptive</li><li>Determined by AppsFlyer</li></ul> |

**To enable engaged view attribution:**

* Set the lookback window in the <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#view-through-attribution-lookback-window">configuration window</Anchor>.

<Anchor target="_blank" href="/marketers/docs/measure-view-through-engagements">Learn more about view-through attribution</Anchor>

</Accordion>

<div id="advanced-attribution-topics" />

## Advanced attribution topics

<div id="in-app-events" />

<Accordion title="In-app events">

AppsFlyer uses the device ID or unique AppsFlyer ID for attributions (an app install, reinstall, or re-attribution) to **attribute in-app events to the media source**. Advertisers can use this information to follow user journeys in their app's raw data. In aggregate day, the device ID/AppsFlyer ID is used to calculate the number of unique users, for example the number of unique users that perform an in-app event.

For more information about event attribution, click <Anchor target="_blank" href="/marketers/docs/in-app-events-overview?query=in%20app%20event#how-does-appsflyer-attribute-events">here</Anchor>.

</Accordion>

<div id="assisted-installs" />

<Accordion title="Assisted installs">

AppsFlyer fully attributes only one media source per install, usually using the last ad click or the last ad impression (if there were no clicks).

Assisted Installs (AKA multi-touch attribution) are installs where the media source/campaign was not the last touchpoint but touched the user before the install and the touch took place within the attribution lookback window.

Assisting networks are shown as contributors to the install in AppsFlyer.

For more information, click <Anchor target="_blank" href="/marketers/docs/measure-assisted-installs">here</Anchor>.

</Accordion>

<div id="reinstalls" />

<Accordion title="Reinstalls">

A reinstall occurs when a user installs the app, uninstalls it, and then reinstalls it. Reinstall attribution is regulated by the <Anchor target="_blank" href="/marketers/docs/set-up-re-attribution-window">re-attribution window</Anchor> as follows:

* If the reinstall occurs after the expiry of the re-attribution window: a new install is recorded.
* If the reinstall occurs during the re-attribution window, one of the following applies:
  * If the user engaged with a retargeting campaign before the reinstall: a <Anchor target="_blank" href="/marketers/docs/retargeting-attribution-guide">retargeting reinstall</Anchor> (AKA re-attribution) is recorded.
  * If the user did not engage with a campaign or engaged with a UA campaign: no install is recorded. Depending on the <Anchor target="_blank" href="/marketers/docs/measure-reinstalls#overview">**Post Reinstall Events Attribution**</Anchor> state, in-app events of these reinstalling users are either attributed to organic or to the original install.

For device testing and multiple installs, <Anchor target="_blank" href="/marketers/docs/registering-test-devices">register</Anchor> the device in AppsFlyer. If you don't register the device only the first install is recorded.

Note that AppsFlyer enables better accuracy for attributing iOS reinstalls without advertiser ID. You can enable this feature on the <Anchor target="_blank" href="/marketers/docs/app-settings#reinstall-detection-using-ondevice-storage-ios-only">App Settings page</Anchor>.

<div id="reinstalling-ios-apps-that-are-backed-up-in-icloud" />

#### Reinstalling iOS apps that are backed up in iCloud

When an application is backed up using iCloud and later restored (on the same device or on another device), AppsFlyer doesn't count it as a new install or reinstall. A user who restores an app from iCloud maintains their AppsFlyer ID and attribution data.

</Accordion>

<div id="retargeting-attribution" />

<Accordion title="Retargeting attribution">

![Retargeting_-_Flow__2_.png](https://files.readme.io/64b8d9f5040daa281ae13f0855749ab4a88a2e7e8616d6ada37975899db92c80-31937591646097.png)

A user who re-installs an app within the <Anchor target="_blank" href="/marketers/docs/set-up-re-attribution-window">re-attribution window</Anchor> (90 days by default) is considered a re-attribution. If this install occurs after engaging with a retargeting campaign, it is recorded as a retargeting reinstall AKA re-attribution and is reported in <Anchor target="_blank" href="/marketers/docs/retargeting-attribution-guide">retargeting</Anchor>.

</Accordion>

<div id="app-updates" />

<Accordion title="App updates">

* When existing users update the app to a subsequent version, this is not treated as a countable attribution event, if the user was previously attributed by AppsFlyer. Note! If you migrate to AppsFlyer from a different MMP existing users on the first app-open, after migration, are attributed to organic.
* Metrics relating to the number of users per app version are available in the <Anchor target="_blank" href="/marketers/docs/sdk-information-version-consent-dashboard">SDK Information dashboard.</Anchor>

</Accordion>

<div data-zendesk-anchors="01H8GG9XPSS8KA9CHPD6ECNR2J=what-is-attribution 01EDRHGMTXK94Y97DPKFAMCJ5B=what-is-an-app-install 01EDRHGMTXCRNVXS9JGHQ1JAQT=attribution-methods attribution-waterfall=attribution-method-priorities-attribution-waterfall h_01JBC8582ABTE00W29PM5Y5X0B=attribution-method-priorities-attribution-waterfall 01H8GG9XPS6P3CXX5AN2KY8WN4=install-referrer-android-only 01H8GG9XPSGVK90FV0K9HZARH7=device-id-matching 01H8GG9XPSV247F3JRCR870JK0=device-id-matching-for-selfreporting-networks 01EDRHGMTXHAKWZK99Q2X86BND=probabilistic-modeling 01H8GG9XPSZ5CPKNSCV7NF1MKW=preload-campaigns h_01K0XWKWQ7TJ2DBT1JZPY5Q4F6=deep-link 01H8GG9XPTXDR41QANF4XVSZMM=attribution-methods-per-media-source-and-appsflyer-feature 01H8GG9XPT65G88DE8548HZREE=owned-media 01H8GG9XPTADWMQ37WBB6P9WVS=paid-media 01EDRHGMTX7851H14R20F9KNAN=user-engagement-attribution-types 01EDRHGMTXJ7WKTWQXFCHTD9AV=clickthrough-attribution 01EDRHGMTXN0Y0ZRVBX7HHW7NN=viewthrough-attribution h_01K0XYZWBVPSXT0T6XGPQT20X8=engaged-view-attribution 01EDRHGMTYYXBSCDPKXCDK1641=advanced-attribution-topics 01EDRHGMTYMH3SVNBTQ28D4F42=in-app-events h_01K0XWKWQ7J20YKEND9A43DRNR=assisted-installs 01EDRHGMTY2CF0B70T3RAGPCJ1=reinstalls 01EDRHGMTYDSNJKQNPNYFXJPAZ=reinstalling-ios-apps-that-are-backed-up-in-icloud 01EDRHGMTYYB9XVM5CBWSPJGMN=retargeting-attribution 01EDRHGMTYTQRMG1W7ZBW4G6W4=app-updates" />
