---
title: "SKAN interoperation with Snapchat"
excerpt: "Learn how to configure SKAN interoperability between AppsFlyer and Snapchat to share postbacks and conversion value measurement mapping."
x-zendesk:
  id: 360017604077
  url: https://support.appsflyer.com/hc/en-us/articles/360017604077-SKAN-interoperation-with-Snapchat
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: SKAN interoperation
  section_id: 6552115163153
  position: 2
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-gil-or, Marketers, SKAdNetwork (SKAN)]
  labels: [Advertisers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2021-02-10T20:20:51Z'
  edited_at: '2024-01-04T10:56:54Z'
---
**At a glance:** SKAN interoperability enables Snapchat to share SKAN postbacks with AppsFlyer and enables AppsFlyer to share your conversion value measurement mapping with Snapchat.

## SKAN interoperability: AppsFlyer &lt;-> Snapchat

If you work with multiple ad network partners, the best practice is to configure your SKAN integration in AppsFlyer. By doing so, SKAN performance metrics, enriched with other metrics like cost, are available in the AppsFlyer platform. 

**Scope of SKAN interoperability with Snapchat**

The interoperation allows AppsFlyer and Snapchat to share the SKAN conversion value map, enabling both to provide you with performance metrics. If you enable the Snapchat partner integration in AppsFlyer, then AppsFlyer provides Snapchat with events for optimization purposes.

**Snapchat app install ads guidance**

In configuring your Snapchat iOS 14 app install campaigns, consider the following Snapchat guidance:

*Effective February 18, 2021, SKAdNetwork will be available in Snapchat Ads Manager for all advertisers. We recommend that apps configure and begin to test, to ensure no disruption to measurement or scale for app acquisition iOS 14 campaigns on Snapchat. In the future, SKAdNetwork will be a requirement to access App Goal-Based Bidding for iOS Campaigns on Snapchat.*

*Please complete your SKAdNetwork integration in your AppsFlyer MMP dashboard, and complete the configuration of your Conversion Value mapping prior to launching SKAdNetwork ad sets within Snapchat Ads Manager. Snapchat’s setup guide for SKAdNetwork can be found [here](https://businesshelp.snapchat.com/s/article/skadnetwork).*

**Implementation requirements**

Consider the following in Snapchat:

* Configure a [Snap App ID](https://businesshelp.snapchat.com/en-US/a/snap-app-id) for each app you advertise on Snapchat.
* Opt-in the Snapchat Ad Sets for SKAN measurement.
* For a given app, you are limited to a maximum of 10 Ad Sets at a time opted into SKAN attribution.

### Enabling AppsFlyer SKAN interoperation with Snapchat

Interoperation is achieved via settings in the AppsFlyer and Snapchat dashboards. No interoperation is required in the app itself. However, you need to adopt the most recent AppsFlyer SDK.

| Step | Action | Details |
| --- | --- | --- |
| 1 | App prerequisites | * Adopt the most recent AppsFlyer [SDK](/docs/sdk-integration-overview) into your app. |
| 2 | SKAN settings review | Set up and turn on AppsFlyer [SKAN solution.](/docs/skadnetwork-skan-solution-guide)  **To view SKAN settings**:   1. In AppsFlyer, go to **Settings** > **SKAN Conversion Studio**. 2. Click options (**⋮**), and verify that **SKAN measurement** is on.  ![skan-settings.png](https://files.readme.io/e4c36e8f5b10a7a4593a8dc776c4c8c43df88577dae8a812303b2d7b3ee37797-4406452401425.png) 3. Select your preferred measurement mode. Learn more about [SKAN Conversion Studio](/docs/skan-conversion-studio). 4. Make a note of the exact event names set. You need them in the next step. |
| 3 | In-app event mapping | Review, and if necessary, make changes to your Snapchat in-app event mappings.  **To view and set in-app event mappings**:   1. In AppsFlyer, Go to **Settings** > **Active Integrations**. 2. Search for and select **Snapchat**. 3. From the **Integration** tab, if **Activate partner** isn't turned on, turn it on. 4. Verify, and if necessary update, the Snap app ID that displays in AppsFlyer with the app ID that displays in the [Snapchat dashboard](https://businesshelp.snapchat.com/s/article/snap-app-id?language=en_US). 5. If not on, turn on **In-app events postback**.  [![mceclip0.png](https://files.readme.io/7dd29ac3be914e9c1b29761d9be525c8945e3ae298274f95f82ede1f548617f6-360017154137.png)](https://files.readme.io/7dd29ac3be914e9c1b29761d9be525c8945e3ae298274f95f82ede1f548617f6-360017154137.png) Verify that the in-app events **SDK event names** you set in SKAN measurement are mapped to **Partner event identifiers,**meaning Snapchat event names. You must map the currently-selected SKAN measurement type events or the events in your [Custom conversion map](/docs/skan-cv-decode-map-your-cv-to-events). **Note**! The default measurement type is revenue.In-app event mapping guide     | Measurement type | Mapping requirement |    | --- | --- |    | Custom | Map the in-app events you set in Custom to the corresponding Snap events.  To report revenue by postback you must set **Send revenue** to **Values & revenue**.  ![SendValueandRevenue.png](https://files.readme.io/412c60db2b09d80a989b7546a6819aa1b030732e0ce004b323dc09db1015c238-11331054047377.png)  *af\_skad\_revenue* is used for overall revenue and mapped to the Snap revenue event*.*  **Note**! It's OK to map more than one event to the Snap revenue event. |    | Revenue | Map af\_skad\_revenue to PURCHASE |    | Conversion | Map 1–6 conversion events to the corresponding Snapchat events. |    | Engagement | Map the engagement event you set to the corresponding Snapchat event. | |
Click Save integration.4Allow Snapchat to share postbacks with AppsFlyerGo to your Snapchat dashboard.In the Please share postbacks with this MMP, select AppsFlyer.[![SnapchatSelectAppsFlyer.png](https://files.readme.io/e142c4bf54019e8587722af4c5cf5aa95ca49a76948f66e3fb584b003aaacdd6-360017154717.png)](https://files.readme.io/e142c4bf54019e8587722af4c5cf5aa95ca49a76948f66e3fb584b003aaacdd6-360017154717.png)Click Update.

## Additional information

### Discrepancies guide

| Discrepancy | Details |
| --- | --- |
| Dashboard filters | **Discrepancy cause**<br /><br />* AppsFlyer: The SKAN dashboard contains installs relating to iOS postbacks received.<br />* Snapchat: By default, the Snapchat dashboard and report includes both SKAN and installs attributed traditionally (IDFA). Filter the Snapchat report to get only SKAN installs.<br /><br />**Solution**<br /><br />Align the Snapchat dashboard filters to display SKAN installs only as indicated in the screenshot that follows.<br /><br />[![SnapchatFilter.png](https://files.readme.io/6e067557aabe899df48454aaf4b7be7f466da55e41b7cd3c68db802e48df7d07-360019782137.png)](https://files.readme.io/6e067557aabe899df48454aaf4b7be7f466da55e41b7cd3c68db802e48df7d07-360019782137.png) |
| Install date differences | **Discrepancy cause**<br /><br />There can be differences between the AppsFlyer and Snapchat install dates as follows:<br /><br />* AppsFlyer: Derives the install date using the following formula: Postback arrival time - 24 hours - measurement window (default 24 hours.) So the default adjustment is 48 hours. All times UTC. [SKAN data freshness](/docs/about-data-freshness-and-timezone-support#skan)<br />* Snapchat: Typically uses the iOS postback arrival time as the install date without adjustment.<br /><br />**Solution**<br /><br />Take the above into consideration when comparing results. |

> 📘 **See also**
>
> * [AppsFlyer SKAN solution guide](/docs/skadnetwork-skan-solution-guide)