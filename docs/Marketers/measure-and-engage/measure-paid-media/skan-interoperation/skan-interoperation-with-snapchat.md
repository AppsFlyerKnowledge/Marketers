---
title: "SKAN interoperation with Snapchat"
excerpt: "Learn how to configure SKAN interoperability between AppsFlyer and Snapchat to share postbacks and conversion value measurement mapping."
---
SKAN interoperability enables Snapchat to share SKAN postbacks with AppsFlyer and enables AppsFlyer to share your conversion value measurement mapping with Snapchat.

## SKAN interoperability: AppsFlyer <-> Snapchat

If you work with multiple ad network partners, the best practice is to configure your SKAN integration in AppsFlyer. By doing so, SKAN performance metrics, enriched with other metrics like cost, are available in the AppsFlyer platform.

**Scope of SKAN interoperability with Snapchat**

The interoperation allows AppsFlyer and Snapchat to share the SKAN conversion value map, enabling both to provide you with performance metrics. If you enable the Snapchat partner integration in AppsFlyer, then AppsFlyer provides Snapchat with events for optimization purposes.

**Snapchat app install ads guidance**

In configuring your Snapchat iOS 14 app install campaigns, consider the following Snapchat guidance:

*Effective February 18, 2021, SKAdNetwork will be available in Snapchat Ads Manager for all advertisers. We recommend that apps configure and begin to test, to ensure no disruption to measurement or scale for app acquisition iOS 14 campaigns on Snapchat. In the future, SKAdNetwork will be a requirement to access App Goal-Based Bidding for iOS Campaigns on Snapchat.*

*Please complete your SKAdNetwork integration in your AppsFlyer MMP dashboard, and complete the configuration of your Conversion Value mapping prior to launching SKAdNetwork ad sets within Snapchat Ads Manager. Snapchat’s setup guide for SKAdNetwork can be found [here](https://businesshelp.snapchat.com/s/article/skadnetwork).*

**Implementation requirements**

Consider the following in Snapchat:

- Configure a [Snap App ID](https://businesshelp.snapchat.com/en-US/a/snap-app-id) for each app you advertise on Snapchat.
- Opt-in the Snapchat Ad Sets for SKAN measurement.
- For a given app, you are limited to a maximum of 10 Ad Sets at a time opted into SKAN attribution.

### Enabling AppsFlyer SKAN interoperation with Snapchat

Interoperation is achieved via settings in the AppsFlyer and Snapchat dashboards. No interoperation is required in the app itself. However, you need to adopt the most recent AppsFlyer SDK.

| Step | Action | Details |
| --- | --- | --- |
| 1 | App prerequisites | - Adopt the most recent AppsFlyer [SDK](https://support.appsflyer.com/hc/articles/207032126) into your app. |
| 2 | SKAN settings review | Set up and turn on AppsFlyer [SKAN solution.](https://support.appsflyer.com/hc/articles/360011420698)<br>**To view SKAN settings**:<br>1. In AppsFlyer, go to **Settings** \> **SKAN Conversion Studio**.<br>2. Click options ( **⋮**), and verify that **SKAN measurement** is on.<br>   <br>   <br>   <Image src="https://files.readme.io/e4c36e8f5b10a7a4593a8dc776c4c8c43df88577dae8a812303b2d7b3ee37797-4406452401425.png" alt="skan-settings.png" /><br>   <br>3. Select your preferred measurement mode.<br>   <br>   Learn more about [SKAN Conversion Studio](https://support.appsflyer.com/hc/articles/4403727223185).<br>4. Make a note of the exact event names set. You need them in the next step. |
| 3 | In-app event mapping | Review, and if necessary, make changes to your Snapchat in-app event mappings.<br><br>**To view and set in-app event mappings**:<br><br>1. In AppsFlyer, Go to **Settings** \> **Active Integrations**.<br>2. Search for and select **Snapchat**.<br>3. From the **Integration** tab, if **Activate partner** isn't turned on, turn it on.<br>4. Verify, and if necessary update, the Snap app ID that displays in AppsFlyer with the app ID that displays in the [Snapchat dashboard](https://businesshelp.snapchat.com/s/article/snap-app-id?language=en_US).<br>5. If not on, turn on **In-app events postback**.<br><br><Image src="https://files.readme.io/7dd29ac3be914e9c1b29761d9be525c8945e3ae298274f95f82ede1f548617f6-360017154137.png" alt="mceclip0.png" /><br><br>Verify that the in-app events **SDK event names** you set in SKAN measurement are mapped to **Partner event identifiers,** meaning Snapchat event names. You must map the currently-selected SKAN measurement type events or the events in your [Custom conversion map](https://support.appsflyer.com/hc/articles/360014696297-Custom-conversion-value-decode-for-SKAdNetwork). **Note**! The default measurement type is revenue.<br><br>#### In-app event mapping guide<br><br>| Measurement type | Mapping requirement |<br>| --- | --- |<br>| Custom | Map the in-app events you set in Custom to the corresponding Snap events.<br>To report revenue by postback you must set **Send revenue** to **Values & revenue**.<br><Image src="https://files.readme.io/412c60db2b09d80a989b7546a6819aa1b030732e0ce004b323dc09db1015c238-11331054047377.png" alt="SendValueandRevenue.png" /><br>_af\_skad\_revenue_ is used for overall revenue and mapped to the Snap revenue event _._<br>**Note**! It's OK to map more than one event to the Snap revenue event. |<br>| Revenue | Map af\_skad\_revenue to PURCHASE |<br>| Conversion | Map 1–6 conversion events to the corresponding Snapchat events. |<br>| Engagement | Map the engagement event you set to the corresponding Snapchat event. |<br><br>6. Click **Save integration**. |
| 4 | Allow Snapchat to share postbacks with AppsFlyer | 1. Go to your Snapchat dashboard.<br>2. In the **Please share postbacks with this MMP**, select AppsFlyer.<br>   <Image src="https://files.readme.io/e142c4bf54019e8587722af4c5cf5aa95ca49a76948f66e3fb584b003aaacdd6-360017154717.png" alt="SnapchatSelectAppsFlyer.png" /><br>   <br>3. Click **Update**. |

## Additional information

### Discrepancies guide

| Discrepancy | Details |
| --- | --- |
| Dashboard filters | **Discrepancy cause**<br>- AppsFlyer: The SKAN dashboard contains installs relating to iOS postbacks received.<br>- Snapchat: By default, the Snapchat dashboard and report includes both SKAN and installs attributed traditionally (IDFA). Filter the Snapchat report to get only SKAN installs. <br>**Solution**<br>Align the Snapchat dashboard filters to display SKAN installs only as indicated in the screenshot that follows.<br><Image src="https://files.readme.io/6e067557aabe899df48454aaf4b7be7f466da55e41b7cd3c68db802e48df7d07-360019782137.png" alt="SnapchatFilter.png" /> |
| Install date differences | **Discrepancy cause**<br>There can be differences between the AppsFlyer and Snapchat install dates as follows:<br>- AppsFlyer: Derives the install date using the following formula: Postback arrival time - 24 hours - measurement window (default 24 hours.) So the default adjustment is 48 hours. All times UTC. [SKAN data freshness](https://support.appsflyer.com/hc/articles/360000310629-Data-freshness-and-time-zone-support#skan)<br>- Snapchat: Typically uses the iOS postback arrival time as the install date without adjustment.<br>**Solution**<br>Take the above into consideration when comparing results. |

### Related resources

<Cards>
  <Card title="AppsFlyer SKAN solution guide" href="https://support.appsflyer.com/hc/articles/360011420698">
    Learn how to set up and configure the AppsFlyer SKAdNetwork solution.
  </Card>
</Cards>