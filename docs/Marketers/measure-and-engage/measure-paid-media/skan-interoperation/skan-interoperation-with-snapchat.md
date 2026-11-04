---
title: SKAN interoperation with Snapchat
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-02-10T20:20:51Z'
  edited_at: '2024-01-04T10:56:54Z'
  id: 360017604077
  locale: en-us
  section: SKAN interoperation
  section_id: 6552115163153
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360017604077-SKAN-interoperation-with-Snapchat
---
> **At a glance:** SKAN interoperability enables Snapchat to share SKAN postbacks with AppsFlyer and enables AppsFlyer to share your conversion value measurement mapping with Snapchat.

<div id="skan-interoperability-appsflyer---snapchat" />

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

<div id="enabling-appsflyer-skan-interoperation-with-snapchat" />

### Enabling AppsFlyer SKAN interoperation with Snapchat

Interoperation is achieved via settings in the AppsFlyer and Snapchat dashboards. No interoperation is required in the app itself. However, you need to adopt the most recent AppsFlyer SDK.

<table><thead><tr><th>Step</th><th>Action</th><th>Details </th></tr></thead><tbody><tr><td><p>1</p></td><td>App prerequisites</td><td><ul><li>Adopt the most recent AppsFlyer <a href="./sdk-integration-overview" target="_blank">SDK</a> into your app.</li></ul></td></tr><tr><td><p>2</p></td><td>SKAN settings review </td><td><p>Set up and turn on AppsFlyer <a href="./skadnetwork-skan-solution-guide" target="_blank">SKAN solution.</a></p><p><strong>To view SKAN settings</strong>:</p><ol><li>In AppsFlyer, go to <strong>Settings</strong> &gt; <strong>SKAN Conversion Studio</strong>.</li><li><span>Click options (</span><span>⋮</span><span>), and verify</span> that <span><span><strong>SKAN measurement</strong> is on.<br/></span></span><p><img alt="skan-settings.png" src="https://files.readme.io/e4c36e8f5b10a7a4593a8dc776c4c8c43df88577dae8a812303b2d7b3ee37797-4406452401425.png"/></p></li><li>Select your preferred measurement mode.<br/>Learn more about <a href="./skan-conversion-studio" target="_blank">SKAN Conversion Studio</a>.</li><li>Make a note of the exact event names set. You need them in the next step.</li></ol></td></tr><tr><td><p>3</p></td><td>In-app event mapping</td><td><p>Review, and if necessary, make changes to your Snapchat in-app event mappings. </p><p><strong>To view and set in-app event mappings</strong>:</p><ol><li>In AppsFlyer, Go to <strong>Settings</strong> &gt; <strong>Active Integrations</strong>.</li><li>Search for and select <strong>Snapchat</strong>.</li><li>From the <strong>Integration</strong> tab, if <strong>Activate partner</strong> isn't turned on, turn it on. </li><li>Verify, and if necessary update, the Snap app ID that displays in AppsFlyer with the app ID that displays in the <a href="https://businesshelp.snapchat.com/s/article/snap-app-id?language=en_US" target="_blank">Snapchat dashboard</a>.</li><li>If not on, turn on <strong>In-app events postback</strong>.<br/><p><a href="https://files.readme.io/7dd29ac3be914e9c1b29761d9be525c8945e3ae298274f95f82ede1f548617f6-360017154137.png"><img alt="mceclip0.png" src="https://files.readme.io/7dd29ac3be914e9c1b29761d9be525c8945e3ae298274f95f82ede1f548617f6-360017154137.png"/></a></p>Verify that the in-app events <strong>SDK event names</strong> you set in SKAN measurement are mapped to <strong>Partner event identifiers,</strong> meaning Snapchat event names. You must map the currently-selected SKAN measurement type events or the events in your <a href="./skan-cv-decode-map-your-cv-to-events" target="_blank">Custom conversion map</a>. <strong>Note</strong>! The default measurement type is revenue. <h4 id="in-app-event-mapping-guide"><span id="inapp-event-mapping-guide"></span>In-app event mapping guide</h4><table><tbody><tr><th>Measurement type</th><th>Mapping requirement</th></tr><tr><td>Custom</td><td><p>Map the in-app events you set in Custom to the corresponding Snap events.</p><p>To report revenue by postback you must set <span></span><strong>Send revenue</strong> <span></span>to <span></span><strong>Values &amp; revenue</strong>.</p><p><img alt="SendValueandRevenue.png" src="https://files.readme.io/412c60db2b09d80a989b7546a6819aa1b030732e0ce004b323dc09db1015c238-11331054047377.png"/></p><p><em>af_skad_revenue <span></span></em>is used for overall revenue and mapped to the Snap revenue event.</p><p><strong>Note</strong>! It's OK to map more than one event to <span></span>the Snap revenue event.</p></td></tr><tr><td>Revenue</td><td><p>Map af_skad_revenue to PURCHASE</p></td></tr><tr><td>Conversion</td><td>Map 1–6 conversion events to the corresponding Snapchat events.</td></tr><tr><td>Engagement</td><td>Map the engagement event you set to the corresponding Snapchat event.</td></tr></tbody></table></li><li>Click <strong>Save integration</strong>.</li></ol></td></tr><tr><td><p>4</p></td><td>Allow Snapchat to share postbacks with AppsFlyer</td><td><ol><li><span>Go to your Snapchat dashboard.</span></li><li><span>In the <strong>Please share postbacks with this MMP</strong>, select AppsFlyer.</span><p><a href="https://files.readme.io/e142c4bf54019e8587722af4c5cf5aa95ca49a76948f66e3fb584b003aaacdd6-360017154717.png"><img alt="SnapchatSelectAppsFlyer.png" src="https://files.readme.io/e142c4bf54019e8587722af4c5cf5aa95ca49a76948f66e3fb584b003aaacdd6-360017154717.png"/></a></p></li><li>Click <strong>Update</strong>.</li></ol></td></tr></tbody></table>

<div id="additional-information" />

## Additional information

<div id="discrepancies-guide" />

<Accordion title="Discrepancies guide">

| Discrepancy | Details |
| --- | --- |
| Dashboard filters | **Discrepancy cause**<ul><li>AppsFlyer: The SKAN dashboard contains installs relating to iOS postbacks received.</li><li>Snapchat: By default, the Snapchat dashboard and report includes both SKAN and installs attributed traditionally (IDFA). Filter the Snapchat report to get only SKAN installs.</li></ul>**Solution**<br /><br />Align the Snapchat dashboard filters to display SKAN installs only as indicated in the screenshot that follows.<br /><br />[![SnapchatFilter.png](https://files.readme.io/6e067557aabe899df48454aaf4b7be7f466da55e41b7cd3c68db802e48df7d07-360019782137.png)](https://files.readme.io/6e067557aabe899df48454aaf4b7be7f466da55e41b7cd3c68db802e48df7d07-360019782137.png) |
| Install date differences | **Discrepancy cause**<br /><br />There can be differences between the AppsFlyer and Snapchat install dates as follows:<ul><li>AppsFlyer: Derives the install date using the following formula: Postback arrival time - 24 hours - measurement window (default 24 hours.) So the default adjustment is 48 hours. All times UTC. <Anchor target="_blank" href="/marketers/docs/about-data-freshness-and-timezone-support#skan">SKAN data freshness</Anchor></li><li>Snapchat: Typically uses the iOS postback arrival time as the install date without adjustment.</li></ul>**Solution**<br /><br />Take the above into consideration when comparing results. |

</Accordion>

<div id="see-also" />

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/docs/skadnetwork-skan-solution-guide">AppsFlyer SKAN solution guide</Anchor>

<div data-zendesk-anchors="skan-interoperability-appsflyer-snapchat=skan-interoperability-appsflyer---snapchat h_01HDNZ3SP97C331D45AP1F8CM7=skan-interoperability-appsflyer---snapchat h_01HDNZ3SP9FZ3AXCNG185DJQY1=enabling-appsflyer-skan-interoperation-with-snapchat h_01HDNZ3SPA742313RAJPYSEHWV=inapp-event-mapping-guide h_01HDNZ3SPASN8P9G5YYQGRFC8F=additional-information h_01HDNZ3SPA99XHVBPXVWB5MN86=discrepancies-guide h_01HDNZ1BW5EBP0JCX84MTYPQ6K=see-also" />
