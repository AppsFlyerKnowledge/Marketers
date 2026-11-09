---
title: SKAdNetwork (SKAN) solution guide
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - SKAD
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
    - Ad Networks
  created_at: '2020-07-25T21:19:42Z'
  edited_at: '2026-06-11T08:38:51Z'
  id: 360011420698
  locale: en-us
  section: SKAN solution
  section_id: 6552135379985
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360011420698-SKAdNetwork-SKAN-solution-guide
---
> **At a glance**: Attributing app installs using SKAN.

<Image align="center" alt="5754" src="https://files.readme.io/a970d7b0e8da300ded2138f941bf2e891f32d396c8500292534992a4b4449d71-30757780264337.png" />

<div id="skan" />

## SKAN

SKAdNetwork (SKAN), part of Apple iOS, lets advertisers measure campaign performance while simultaneously preserving user privacy. SKAN operates without IDFA or other advertising ID. SKAN functions without the need for ATT consent.

<div id="tip" />

> 👍 **Tip**
>
> * Starting iOS 15 we recommend that you send <Anchor target="_blank" href="/marketers/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">SKAN postback copies</Anchor> to AppsFlyer. Doing so enables AppsFlyer to verify that Conversion Values in postbacks haven't been manipulated.
> * Want to understand more about the AppsFlyer SKAN solution? Check out this short, informative <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/internal/view/elearning/7810/ios14-and-skadnetwork">course on the AppsFlyer Learning Portal</Anchor>.

**Definitions**

* <Anchor target="_blank" href="/marketers/docs/sdk-integration-overview">SDK</Anchor>: Current version of the AppsFlyer iOS SDK integrated in an app.
* **SKAN measurement window**: Relevant for SKAN 4+. There are 3 time periods (windows) during which user post-install activity is measured:
  * Window 1: 1-2 days
  * Window 2: 3-7 days
  * Window 3: 8-35 days
* **Conversion Value (CV)**: The measure of user quality reported in the postbacks sent by iOS at the end of the SKAN 4 measurement windows or, for SKAN 3 and below, at the end of the Activity Window. The AppsFlyer SDK sets the CVs for you. However, if you want to set the CV use <Anchor target="_blank" href="/marketers/docs/skan-cv-decode-map-your-cv-to-events">Decode</Anchor> to upload your CV mapping file.
  * For SKAN 4+, there are both fine and coarse conversion values.
* **Conversion Studio**: AppsFlyer solution for mapping infrastructure Conversion Values (CV) to events
* **Solution:** SDK, Infrastructure, Conversion Studio, and AppsFlyer platform working together. The AppsFlyer SKAN solution provides advertisers and ad networks with LTV data via dashboard analytics, reports, and postbacks.
* **Activity Window:** Relevant for SKAN 3 and below. Has a set duration, default of 24 hours, starting with the first app open. If you're using SKAN 4+, but user devices or ad networks don't support SKAN 4 yet, the Activity Window is 48 hours.

This article describes the relevant characteristics of the infrastructure and the solution. To set up measurement see <Anchor target="_blank" href="/marketers/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>.

<div id="about-apple-skan" />

<Accordion title="About Apple SKAN">

| Characteristic | Description |
| --- | --- |
| Prerequisites | To enable the use of SKAN in the app:<ul><li>Advertiser app (your app) meaning the app being advertised implements the AppsFlyer SDK* to set the CV. Alternatively, you can set the CV using <Anchor target="_blank" href="/marketers/docs/skan-cv-decode-map-your-cv-to-events">Decode mode</Anchor>.</li><li>Publisher apps (app displaying an ad): must <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/configuring_a_source_app">configure a source app</Anchor>.</li><li><Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/registering_an_ad_network">Ad networks must register with Apple</Anchor></li></ul>**\*Note:** Make sure you don't have another SDK that sets conversion values integrated into your app. |
| Supported | <ul><li>The version of SKAdNetwork supported is iOS version dependent:<ul><li>iOS 11-13: V1 (installs only without CV)</li><li>iOS 14-14.5: V2+ (has CV)</li><li>iOS 14.6-16: V3 (has CV)</li><li>iOS 16.1+: V4+ (has CVs for 3 windows, and both fine and coarse values)</li></ul></li><li>App-to-app attribution</li></ul> |
| Limitations | <ul><li>Apple Ads (Search Ads) are supported for SKAN versions 1–3. View-through and SKAN 4 support are pending</li><li>Mobile web not supported</li><li>Until SKAN, 4 campaign ID numbering is <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skstoreproductparameteradnetworkcampaignidentifier">restricted to the range 1-100</Anchor>; means 100 unique values per ad network per app. Ad networks provide AppsFlyer with their campaign ID and name. This reflects in AppsFlyer dashboards and reports.</li><li>From SKAN 4, source identifier is from 1-10,000.</li><li>Organic installs: SKAN doesn't support organic installs.</li><li>Re-engagement.</li></ul> |
| SKAN Attribution principles | <ul><li>SKAN attributes using the following <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_ad_attributions">attribution model</Anchor>:<ul><li>The user, clicks an ad, within 30 days installs (downloads) the app, and thereafter, within 60 days opens the app for the first time.</li><li>The user views an ad, within 24 hours installs (downloads) the app, and thereafter, within 60 days, opens the app for the first time.</li><li>Starting SKAdNetwork V2.2, click-through attribution takes priority over view-through attribution. SKAN version is iOS version dependent.</li><li>iOS sends postbacks to the attributed ad network. Starting iOS 15, advertisers can send a copy of the postback directly to AppsFlyer.</li></ul></li></ul> |
| Crowd anonymity | Apple sends some postbacks with limited data to protect user privacy in the eve. According to Apple, the postback won't include the fine or coarse CVs, nor the source app ID or complete source identifier if doing so contravenes Apple privacy tier limits. <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_postbacks_in_multiple_conversion_windows">Learn more</Anchor> |

</Accordion>

<div id="appsflyer-skan-solution" />

## AppsFlyer SKAN solution

AppsFlyer provides aggregated iOS attribution results using SKAN postbacks from iOS. These postbacks are sent by iOS to ad networks who then forward them to AppsFlyer. The postbacks contain anonymized attribution records enriched with a conversion value (CV) set by the advertiser. The CV is a measure of user quality during an initial post-install window.

The AppsFlyer SKAN solution provides advertisers with:

* SKAN data in dashboards and reports derived by aggregating postbacks from all ad networks enriched with other data points like cost.
* The ability to control, via the AppsFlyer Conversion Studio, what the CV measures without the need to make changes to the app code. The CV can be used to measure revenue, engagements, or conversion events.  
  **Note:** Only the AppsFlyer SDK should have the ability to set conversion values. Make sure you don't have another SDK that sets conversion values integrated into your app.

<div id="principles-and-flow" />

<Accordion title="Principles and flow">

<div id="skan-attribution-flow" />

#### **SKAN attribution flow**

<Image align="center" alt="SKAN_flow_-_Affinity_diagram_2.png" src="https://files.readme.io/bb24c819cc2187e27ec592000ab892f9a4ba8e2ddd55779dd91d9b6f815d6fb8-30757768511121.png" />

1. Advertiser sets SKAN measurement settings in the AppsFlyer Conversion Studio.
2. The user opens the app for the first time.
3. During each window, AppsFlyer sets the CV based on user actions and the defined CV schema.
4. After the window closes, iOS sends the postback to the ad network and a postback copy to AppsFlyer. The postback arrives with some delay:
   * For SKAN 4 measurement window 1: 24-48 hours
   * For SKAN 4 measurement windows 2-3: 24-144 hours
   * For SKAN 3: 24-48 hours after the most recent increase in the CV value.
5. Postback copies sent directly from the iOS device to AppsFlyer are forwarded to the advertiser's defined endpoint. See <Anchor target="_blank" href="/marketers/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">send SKAN postback copies to AppsFlyer.</Anchor>
6. Ad network forwards enriched postback to AppsFlyer or SRN communicates postback data by API.
7. AppsFlyer validates and decodes the CV. Decoded data is recorded and attributed before being made available in AppsFlyer via dashboards, reports, and APIs.

To overcome the functional and structural limitations of the SKAdNetwork infrastructure, the AppsFlyer SKAN solution takes into consideration the characteristics in the table that follows.

| Characteristic | Description |
| --- | --- |
| <span id="data-collection"></span>Data collection | <ul><li>For the advertiser, SKAdNetwork postbacks are collected from multiple ad networks.</li><li>Advertisers don't need to integrate individually with each ad network—a complex and tedious task.</li></ul> |
| <span id="data-validation"></span>Data validation | <ul><li>Ensures postbacks are signed by Apple; this reduces the chances of postback manipulation.</li><li>Uses the transaction ID field to validate that postbacks are unique.</li></ul> |
| <span id="data-enrichment"></span>Data enrichment | <ul><li>Enriches SKAdNetwork postback data with other data points to provide complete ROI analysis. For example, campaign name provided by the ad network, and so on.</li><li>Data points include impressions, clicks, cost, and more.</li></ul> |
| <span id="data-delivery"></span>Data delivery | Enriched SKAdNetwork data is available using the following:<ul><li><Anchor target="_blank" href="/marketers/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">SKAdNetwork solution dashboard</Anchor></li><li>[Downloadable reports](/docs/skadnetwork-skan-solution-guide#reporting-options)</li></ul> |
| <span id="seamless-integration"></span>Seamless integration | <ul><li>Full encapsulation enables a near-zero effort by the advertiser via the app settings page.</li><li>No coding is required. The app requires the latest SDK version.</li><li>Includes support for expected changes by Apple in the SKAdNetwork infrastructure.</li></ul> |
| <span id="agility"></span>Agility | Advertisers can change measurement configurations as needed in the dashboard. |

</Accordion>

<div id="conversion-studio" />

<Accordion title="Conversion Studio">

The AppsFlyer <Anchor target="_blank" href="/marketers/docs/skan-conversion-studio">Conversion Studio</Anchor> is at the heart of the SKAN solution. It provides you with maximum flexibility to make every bit of a conversion value count. You determine precisely what measurement data should be encoded within the CV—including what activity and for how long to measure during the post-install period. There are several measurement modes you can use to configure your CV settings.

| Type | Measurement mode | Description | Activity window |
| --- | --- | --- | --- |
| Flexible | SKAN 4.0<br /><br />[Best practice] | Set a combination of revenue, conversion (in-app events), and engagement measurements during 3 configurable measurement windows. | <ul><li>Window 1: 1-2 days</li><li>Window 2: 3-7 days</li><li>Window 3: 8-35 days</li></ul> |
| Flexible | <Anchor target="_blank" href="/marketers/docs/skan-conversion-studio#custom">Custom</Anchor> | Set a combination of revenue, conversion (in-app events), and engagement measurements during a configurable activity window. | 12h-63 days |
| Fixed | Revenue<br /><br />[Default]<br /><br />[Legacy] | Measure revenue using one of the following ranges:<ul><li>$1-$630 in steps of $10</li><li>$1-$63 in steps of $1</li><li>$0.01-$0.63 in steps of $0.01</li></ul> | 24h |
| Fixed | Conversion<br /><br />[Legacy] | Select 1-6 in-app events. | 24h |
| Fixed | Engagement<br /><br />[Legacy] | Number of times a user performs an event | 24h |
| Flexible | <Anchor target="_blank" href="/marketers/docs/skan-cv-decode-map-your-cv-to-events">Decode</Anchor> | <ul><li>Create your own CV to event mapping and set the CV in the app yourself. Use this option if you can't integrate the AppsFlyer SDK into your app. To use Decode, go to **SKAN Conversion Studio,** click options (⋮), select **Upload custom decode mapping file**.</li></ul> | 12-1512h (63 days) |

</Accordion>

<div id="additional-skadnetwork-information" />

## Additional SKAdNetwork information

<div id="reporting-options" />

<Accordion title="Reporting options">

SKAdNetwork reports don't contain user-level identifiers.

| Report name | Type | Enriched by AppsFlyer | Delivery method | Premium feature |
| --- | --- | --- | --- | --- |
| <Anchor target="_blank" href="/marketers/docs/skan-aggregated-performance-report-api">SKAN aggregated performance report.</Anchor><br /><br />Aggregates of install, in-app events, and revenue. The data is similar to that found in the SKAN dashboard. | Aggregated using install or postback arrival date | Yes | API | No |
| <Anchor target="_blank" href="/marketers/docs/skan-aggregated-postback-arrival-date-api">SKAN aggregated postback report</Anchor>.<br /><br />SKAN postbacks aggregated to the most granular level possible. | Postback aggregation using postback arrival date | No | API | No |
| <Anchor target="_blank" href="/marketers/docs/skan-raw-data-reports#raw-data-report-types">SKAN raw-data (row-level) reports via Data Locker</Anchor> (with examples).<br /><br />Reports available:<ul><li>Postbacks sent by iOS with data enrichment provided by ad network partners</li><li>Installs</li><li>Redownloads</li><li>In-app events</li><li>SRN advertising dimensions</li></ul> |  | Yes | Data Locker | Yes. Raw data required. Data Locker subscription isn't required. |
| SKAN data via Push API |  | Yes | Push API | Yes |

</Accordion>

<div id="skadnetwork-solution-implementation-checklist" />

<Accordion title="SKAdNetwork solution implementation checklist">

| No. | Action | Description | Responsibility |
| --- | --- | --- | --- |
| 1 | Prepare | <ul><li>Read <Anchor target="_blank" href="https://www.appsflyer.com/resources/prepare-your-app-ios14/">SKAdNetwork solution guide</Anchor></li><li>Additional reading: <Anchor target="_blank" href="https://www.appsflyer.com/resources/prepare-your-app-ios14/">Prepare your apps for iOS 14</Anchor></li></ul> | Marketer, Developer |
| 2 | Configure | In AppsFlyer, configure the SKAdNetwork solution in the <Anchor target="_blank" href="/marketers/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>. | Marketer |
| 3 | Prepare the app | Migrate the app to AppsFlyer <Anchor target="_blank" href="/marketers/docs/sdk-integration-overview">V6 SDK</Anchor><ul><li>No change to app logic nor to app code is required.</li><li>The AppsFlyer SKAN solution relies on in-app events to set the CV Send in-app events in the usual manner. No SKAN solution-specific testing is required.</li><li>Submit the app to the App Store</li><li>No SKAdNetwork registration or process is required in the app store.</li></ul> | Developer |
| 4 | Partner integrations | Ad network partners must integrate with AppsFlyer using SKAdNetwork integration. Note! AppsFlyer SKAdNetwork simulation contains the data of all your partners irrespective of their current integration status. This won't be the case for the live data reported by SKAdNetwork postbacks.<br /><br />In relation to partners running your campaigns complete the following as required:<br /><br />**Non-SRNs**:<ol><li>Verify that the partner has an AppsFlyer <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#c-transaction-id">SKAdNetwork capability badge</Anchor> and that in the partner UI, SKAdNetwork campaign reporting is enabled.</li><li>Verify that your [in-app event names are mapped](#sending-postbacks-to-integrated-partners) to partner in-app event names.</li></ol>**Meta ads**:<ul><li><Anchor target="_blank" href="/marketers/docs/skadnetwork-skan-interoperation-with-meta-ads">Configure AppsFlyer SKAdNetwork interoperation with Meta ads</Anchor></li></ul> | Marketer |

</Accordion>

<div id="troubleshooting-guide" />

<Accordion title="Troubleshooting guide">

| Symptom | Description |
| --- | --- |
| The dashboard doesn't contain any non-organic installs. | <ol><li>Verify that **SKAdNetwork measurement** is on.<ol><li>Go to **Settings** > **SKAN Conversion Studio.**</li><li>Click options (⋮), examine the SKAN measurement setting.</li></ol></li><li>Verify that your SDK version is 6.2.6+.<ul><li>To do so, go to **Integration** > **SDK Information > Users by SDK version.**</li></ul></li><li>If you use SDK plugins, verify that you implement a version that supports AppsFlyer SKAdNetwork.</li><li>Verify that your ad network partners are integrated with AppsFlyer and that they forward iOS postbacks to AppsFlyer.</li></ol> |
| The dashboard contains non-organic installs but no in-app events at all. | <ol><li>Verify that your SDK version is 6.2.6+.<ul><li>To do so, go to **Integration** > **SDK Information > Users by SDK version.**</li></ul></li><li>If you use SDK plugins, verify that you implement a version that supports AppsFlyer SKAdNetwork.</li><li>Do you send events using S2S? If so, verify that **Record in-app events sent by server-to-server API** is on.<ol><li>Go to **Settings** > **SKAN Conversion Studio.**</li><li>**Click options (⋮), verify that S2S configuration is on.** Note: In Custom and Decode measurement mode, this setting is always on and can't be changed.</li></ol></li></ol> |
| The dashboard contains installs and some in-app events. Some in-app events are missing. | <ol><li>Do you send events using S2S? If so, verify that **Record in-app events sent by server-to-server API** is on.<ol><li>Go to **Settings** > **SKAN Conversion Studio.**</li><li>**Click options (⋮), verify that S2S configuration is on.** Note: In Custom and Decode measurement mode, this setting is always on and can't be changed.</li></ol></li><li>Inspect your <Anchor target="_blank" href="/marketers/docs/skan-raw-data-reports#raw-data-report-types">postback raw data</Anchor> to see if all events are reported.</li></ol> |
| Geo (country) locations are misleading | Geo data is derived as follows:<ul><li>According to the country associated with a campaign and reported to AppsFlyer by the ad network.</li><li>Using the device IP address. Starting iOS 14.6, this address is a proxy address and doesn't truly represent the user geolocation.</li></ul> |

</Accordion>

<div id="timing-from-app-install-until-dashboard-and-reports-update" />

<Accordion title="Timing from app install until dashboard and reports update">

| Key | Element name | Description | Example A | Example B | Example C | Example D | Example E |
| --- | --- | --- | --- | --- | --- | --- | --- |
| A | SKAN 4 measurement window 1 | <ul><li>During the window, the CVs are set by the app</li><li>0-2 days</li><li>Window can be locked before 2 days in Conversion Studio</li></ul> | - | - | 2 days | - | - |
| B | SKAN 4 measurement window 2 | <ul><li>During the window, the CV is set by the app</li><li>3-7 days</li><li>Window can be locked before 7 days in Conversion Studio</li></ul> | - | - | - | 7 days | - |
| C | SKAN 4 measurement window 3 | <ul><li>During the window, the CV is set by the app</li><li>8-35 days</li><li>Window can be locked before 35 days in Conversion Studio</li></ul> | - | - |  | - | 35 days |
| D | SKAN 4 measurement window 1 postback delay | 24-48 hours | - | - | 24-48h | - | - |
| E | SKAN 4 measurement window 2-3 delay | 24-144 hours | - | - | - | 24-144h | 24-144h |
| F | Activity Window<br /><br />(Not relevant for SKAN 4) | <ul><li>During the window, the CV is set by the app.</li><li>The window begins when the app is opened for the first time.</li><li>Duration 12 hours - 63 days.</li></ul> | 24h | 72h | - | - | - |
| G | SKAdNetwork timer<br /><br />(Not relevant for SKAN 4) | <ul><li>Countdown timer: 24 hours</li><li>Each time the CV increases, the timer is reset. This means it starts counting down from 24 hours.</li></ul> | 0-24h | 0-24h | - | - | - |
| H | SKAdNetwork random delay<br /><br />(Not relevant for SKAN 4) | Random postback delay time. The countdown starts at the end of the period defined by F+G. | 0-24h | 0-24h | - | - | - |
| I | AppsFlyer processing | Postbacks received on a given day are processed at the end of the day UTC starting at 00:01 on the following day. The data is available 8 hours later. Meaning processing takes 8-32 hours. Average delay of 20 hours. For example, a postback received on Monday is processed on Tuesday. The dashboard updates by 08:00 UTC. | 8-32h | 8-32h | 8-32h | 8-32h | 8-32h |
| J | Summary | The total time that can elapse | 32 hours-104h | 80-152h | 80-128 hours | 200-344h | 872-1016h |

</Accordion>

<div id="organic-metrics-in-the-context-of-skadnetwork" />

<Accordion title="Organic metrics in the context of SKAdNetwork">

Organic metrics in the SKAdNetwork dashboard are calculated using the following mechanism:

* **Organic revenue** is only available for Revenue in either <Anchor target="_blank" href="/marketers/docs/skan-conversion-studio#fixed-modes">fixed</Anchor> or legacy mode.
* **Organic in-app** events are only available for "Conversion" in <Anchor target="_blank" href="/marketers/docs/skan-conversion-studio#fixed-modes">fixed</Anchor> or legacy modes.
* For the **non-legacy modes** (<Anchor target="_blank" href="/marketers/docs/skan-conversion-studio#skan-4">SKAN4</Anchor>, custom encode, and decode modes) organic data is available only for installs.
* Apple SKAdNetwork sends postbacks relating to users who install after engaging with a media source. This provides the non-organic metrics.
* AppsFlyer attribution dashboards contain metrics of all installs irrespective of source.  See <Anchor target="_blank" href="/marketers/docs/ios-metrics-in-the-overview-dashboard-skan-and-appsflyer-metrics-side-by-side">view AppsFlyer attribution side-by-side with SKAN attribution</Anchor>.
* Using this data, organic metrics are calculated as A-B where:
  * A = Total of all users based on the traditional overview dashboard
  * B = Non-organic users as reported by SKAdNetwork postbacks

**Caveat relating to Apple Ads**: Installs brought by Apple Ads in the traditional dashboard are non-organic. However, in the context of SKAdNetwork, they form part of the organic metric.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Traits and limitations">

| Trait | Remarks |
| --- | --- |
| Ad network access | Ad networks are provided with postbacks |
| Agencies | Not supported. This means that agencies mustn't enable ad networks running SKAdNetwork campaigns. Agency! Ask the advertiser to enable the Ad network don't do it yourself. Agencies can indicate that they brought the user by implementing <Anchor target="_blank" href="/partners/docs/getting-started-agency-onboarding#skadnetwork-agency-campaigns">SKAN agency recognition</Anchor>. |
| Agency transparency | N/A |
| Timezone | UTC |
| Currency | USD |
| Organic data | Based on SDK event data. For example, organic install metrics are calculated as follows: Data of all installs reported by the SDK minus non-organic installs reported by SKAdNetworks. |
| Non-organic data | Based on SKAdNetwork postbacks |
| Data freshness | Daily |
| Historical data | Earliest date, availability of iOS 14 (September 16, 2020) |
| User access | Account users must have the <Anchor target="_blank" href="/marketers/docs/user-management">necessary permissions</Anchor> |
| App clips | App clips are attributed to organic in the SKAdNetwork dashboard. Use the Overview dashboard to view invocation media sources. |

</Accordion>

<div id="skan-integrated-partners" />

## SKAN integrated partners

<div id="recording-ad-revenue" />

<Accordion title="Recording ad revenue">

Attribute ad revenue generated during the SKAdNetwork measurement windows to the campaign bringing the user. Currently, this is limited to advertisers integrated with generic impression-level ad revenue via SDK.

To record ad revenue in your SKAN dashboard:

* Integrate the <Anchor target="_blank" href="/marketers/docs/integrate-the-roi360-ad-revenue-sdk-api">generic impression-level ad revenue SDK</Anchor> into your app.
* If you use a SKAN Conversion Studio fixed mode [legacy], <Anchor target="_blank" href="/marketers/docs/skan-conversion-studio#report-events-by-servertoserver-api">turn on SKAdNetwork server-to-server support</Anchor>.

**Note**: See <Anchor target="_blank" href="/marketers/docs/integrate-the-roi360-ad-revenue-sdk-api">generic SDK connector</Anchor> documentation for information on ad sources available for mediation.

</Accordion>

<div id="sending-postbacks-to-integrated-partners" />

<Accordion title="Sending postbacks to integrated partners">

AppsFlyer sends integrated partners postbacks relating to SKAN attribution (for SKAN 4, postbacks are sent only for window 1).

Take note of the various options and requirements in the table that follows

| Subject | Description |
| --- | --- |
| <span id="transaction-id-sharing"></span>Transaction ID sharing | **Action required**: Check with the integrated partner if they require the <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/verifying_an_install_validation_postback">transaction ID</Anchor> and configure the setting accordingly.<br /><br />AppsFlyer sends the attributed ad network partner postbacks. Meaning the decoded postbacks, not a copy of the SKAdNetwork postback received from iOS. These postbacks contain decoded CV data relating to the install and associated in-app event data of actions performed by the user during the Activity Window.<br /><br />Because the transaction ID can be used to decode your CV, we don't share it without your permission.<br /><br />**Transaction ID sharing**<br /><br />Advertisers <Anchor target="_blank" href="/marketers/docs/set-up-an-integrated-partner#b-advanced-privacy">enable transaction ID sharing</Anchor> as follows: In AppsFlyer, go to **Collaborate** > **Active Integrations** > select a partner > **Integration tab** > **Data sharing**. |
| <span id="inapp-event-mapping-verification"></span>In-app event mapping verification | **<span id="1611499069.009700"></span>Action required**: You must <Anchor target="_blank" href="/marketers/docs/in-app-event-postback-configuration#mapping-methods">map your in-app events</Anchor> to the corresponding partner event names so that the partner records postbacks correctly.<br /><br />For each of the partners running SKAdNetwork campaigns verify that the in-app event is set according to the app measurement type selected.<br /><br />**To verify and change partner in-app event mappings**:<ol><li>In AppsFlyer, Go to **Collaborate** > **Active Integrations**.</li><li>Select the partner.</li><li>Go to the **Integration** tab.</li><li>Verify and, if necessary, make settings changes as follows:<ol><li>Turn on **In-app events postback**.</li><li>Verify that the in-app events, **SDK event names** you set in SKAdNetwork measurement are mapped to **Partner event identifiers**.</li></ol></li><li>Click **Save integration**.</li></ol> |

</Accordion>

<div id="see-also" />

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/docs/about-att-and-skan">Quickstart guide & FAQ to iOS 14, ATT, and SKAN</Anchor>
> * <Anchor target="_blank" href="/marketers/docs/skan-conversion-studio">Set up measurement using SKAN Conversion Studio (SKAdNetwork settings)</Anchor>
> * <Anchor target="_blank" href="/marketers/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">AppsFlyer SKAN dashboard</Anchor>
> * <Anchor target="_blank" href="/marketers/docs/skan-integrated-partners-list">SKAN integrated partners list</Anchor>
> * SKAN partner interoperation requiring set up in AppsFlyer:
>   * <Anchor target="_blank" href="/marketers/docs/skadnetwork-skan-interoperation-with-meta-ads">Meta ads</Anchor>
>   * <Anchor target="_blank" href="/marketers/docs/get-skan-postback-data-from-google-ads">Google Ads</Anchor>
>   * <Anchor target="_blank" href="/marketers/docs/skan-interoperation-with-tiktok-for-business">Tik Tok for Business</Anchor>
>   * <Anchor target="_blank" href="/marketers/docs/skan-interoperation-with-snapchat">Snapchat</Anchor>

<div data-zendesk-anchors="01H7Z06Z03AQY25A3E45Z47A9G=skan 01H7Z06Z03CSKH1ZB9RQP6SHA8=tip 01H7Z06Z03MRE6BCSG1AEXN947=about-apple-skan 01H7Z06Z04G479NAKBEA33SGSZ=appsflyer-skan-solution 01H7Z06Z05CAVK3CR7F5FBKFC5=principles-and-flow 01H7Z06Z05EGK5QBDK6G7BJQJK=skan-attribution-flow 01H7Z06Z053M2H3CJ6SV4VDZPZ=conversion-studio 01H7Z06Z05556NQ35HMR4E2TRY=additional-skadnetwork-information 01H7Z06Z05G0YB56GDG5E196QM=reporting-options 01H7Z06Z05M3BPSBTCMJ3NHK5D=skadnetwork-solution-implementation-checklist 01H7Z06Z05YF4J0MPMJ40EG7BX=troubleshooting-guide 01H7Z06Z0502NW8KFJ7XRZFWJR=timing-from-app-install-until-dashboard-and-reports-update 01H7Z06Z068462E4QTGTSMNS7H=organic-metrics-in-the-context-of-skadnetwork 01H7Z06Z0615QHCY6JZ4MAMTJ8=traits-and-limitations skadnetwork-integrated-partners=skan-integrated-partners 01H7Z06Z06KGT6ESN42XTJSK2F=skan-integrated-partners 01H7Z06Z06NWJQ6W50MCD3P352=recording-ad-revenue 01H7Z06Z06K2ZB949GGTJV6MJP=sending-postbacks-to-integrated-partners h_01HE7TC49KRRX1RVGX1FY7C52T=see-also" />
