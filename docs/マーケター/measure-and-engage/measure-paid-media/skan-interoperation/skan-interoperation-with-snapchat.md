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
  edited_at: '2026-10-01T00:32:07Z'
  id: 360017604077
  locale: ja
  section: SKAN interoperation
  section_id: 6552115163153
  url: https://support.appsflyer.com/hc/ja/articles/360017604077
---
> **At a glance:** SKAN interoperability enables Snapchat to share SKAN postbacks with AppsFlyer and enables AppsFlyer to share your conversion value measurement mapping with Snapchat.

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

<Table>
  <thead>
    <tr>
      <th>
        Step
      </th>
      <th>
        Action
      </th>
      <th>
        Details
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        1
      </td>
      <td>
        App prerequisites
      </td>
      <td>
        * Adopt the most recent AppsFlyer <Anchor target="_blank" href="/marketers/ja/docs/sdk-integration-overview">SDK</Anchor> into your app.
      </td>
    </tr>
    <tr>
      <td>
        2
      </td>
      <td>
        SKAN settings review
      </td>
      <td>
        Set up and turn on AppsFlyer <Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-solution-guide">SKAN solution.</Anchor>

        **To view SKAN settings**:

        1. In AppsFlyer, go to **Settings** > **SKAN Conversion Studio**.
        2. Click options (⋮), and verify that **SKAN measurement** is on.  

           ![skan-settings.png](https://files.readme.io/5a5b9b8b8a809336055340a14e49dacc16c5c0e95cda62c6dfb2ca9a11618d71-27548444964497.png)
        3. Select your preferred measurement mode.  
           Learn more about <Anchor target="_blank" href="/marketers/ja/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>.
        4. Make a note of the exact event names set. You need them in the next step.
      </td>
    </tr>
    <tr>
      <td>
        3
      </td>
      <td>
        In-app event mapping
      </td>
      <td>
        Review, and if necessary, make changes to your Snapchat in-app event mappings.

        **To view and set in-app event mappings**:

        1. In AppsFlyer, Go to **Settings** > **Active Integrations**.
        2. Search for and select **Snapchat**.
        3. From the **Integration** tab, if **Activate partner** isn't turned on, turn it on.
        4. Verify, and if necessary update, the Snap app ID that displays in AppsFlyer with the app ID that displays in the <Anchor target="_blank" href="https://businesshelp.snapchat.com/s/article/snap-app-id?language=en_US">Snapchat dashboard</Anchor>.
        5. If not on, turn on **In-app events postback**.  

           [<Image alt="mceclip0.png" src="https://files.readme.io/9df3455b102ff280e8b0fae4bfc006fa87f8830d74064eb955fc829d06708165-23458868914577.png" width="432px" />](https://files.readme.io/9df3455b102ff280e8b0fae4bfc006fa87f8830d74064eb955fc829d06708165-23458868914577.png)

           Verify that the in-app events **SDK event names** you set in SKAN measurement are mapped to **Partner event identifiers,** meaning Snapchat event names. You must map the currently-selected SKAN measurement type events or the events in your <Anchor target="_blank" href="/marketers/ja/docs/skan-cv-decode-map-your-cv-to-events">Custom conversion map</Anchor>. **Note**! The default measurement type is revenue.

           #### In-app event mapping guide

        | Measurement type | Mapping requirement |
        | --- | --- |
        | Custom | Map the in-app events you set in Custom to the corresponding Snap events.<br /><br />To report revenue by postback you must set **Send revenue** to **Values & revenue**.<br /><br />![SendValueandRevenue.png](https://files.readme.io/412c60db2b09d80a989b7546a6819aa1b030732e0ce004b323dc09db1015c238-11331054047377.png)<br /><br />*af\_skad\_revenue* is used for overall revenue and mapped to the Snap revenue event.<br /><br />**Note**! It's OK to map more than one event to the Snap revenue event. |
        | Revenue | Map af\_skad\_revenue to PURCHASE |
        | Conversion | Map 1–6 conversion events to the corresponding Snapchat events. |
        | Engagement | Map the engagement event you set to the corresponding Snapchat event. |

        6. Click **Save integration**.
      </td>
    </tr>
    <tr>
      <td>
        4
      </td>
      <td>
        Allow Snapchat to share postbacks with AppsFlyer
      </td>
      <td>
        1. Go to your Snapchat dashboard.
        2. In the **Please share postbacks with this MMP**, select AppsFlyer.

           [<Image alt="SnapchatSelectAppsFlyer.png" src="https://files.readme.io/e142c4bf54019e8587722af4c5cf5aa95ca49a76948f66e3fb584b003aaacdd6-360017154717.png" width="268px" />](https://files.readme.io/e142c4bf54019e8587722af4c5cf5aa95ca49a76948f66e3fb584b003aaacdd6-360017154717.png)
        3. Click **Update**.
      </td>
    </tr>
  </tbody>
</Table>

## Additional information

<div id="discrepancies-guide" />

<Accordion title="Discrepancies guide">

| Discrepancy | Details |
| --- | --- |
| Dashboard filters | **Discrepancy cause**<ul><li>AppsFlyer: The SKAN dashboard contains installs relating to iOS postbacks received.</li><li>Snapchat: By default, the Snapchat dashboard and report includes both SKAN and installs attributed traditionally (IDFA). Filter the Snapchat report to get only SKAN installs.</li></ul>**Solution**<br /><br />Align the Snapchat dashboard filters to display SKAN installs only as indicated in the screenshot that follows.<br /><br />[![SnapchatFilter.png](https://files.readme.io/6e067557aabe899df48454aaf4b7be7f466da55e41b7cd3c68db802e48df7d07-360019782137.png)](https://files.readme.io/6e067557aabe899df48454aaf4b7be7f466da55e41b7cd3c68db802e48df7d07-360019782137.png) |
| Install date differences | **Discrepancy cause**<br /><br />There can be differences between the AppsFlyer and Snapchat install dates as follows:<ul><li>AppsFlyer: Derives the install date using the following formula: Postback arrival time - 24 hours - measurement window (default 24 hours.) So the default adjustment is 48 hours. All times UTC. <Anchor target="_blank" href="/marketers/ja/docs/about-data-freshness-and-timezone-support#skan">SKAN data freshness</Anchor></li><li>Snapchat: Typically uses the iOS postback arrival time as the install date without adjustment.</li></ul>**Solution**<br /><br />Take the above into consideration when comparing results. |

</Accordion>

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/ja/docs/skadnetwork-skan-solution-guide">AppsFlyer SKAN solution guide</Anchor>

<div data-zendesk-anchors="skan-interoperability-appsflyer-snapchat=skan-interoperability-appsflyer---snapchat h_01HDNZ3SP97C331D45AP1F8CM7=skan-interoperability-appsflyer---snapchat h_01HDNZ3SP9FZ3AXCNG185DJQY1=enabling-appsflyer-skan-interoperation-with-snapchat inapp-event-mapping-guide=in-app-event-mapping-guide h_01HDNZ3SPA742313RAJPYSEHWV=in-app-event-mapping-guide h_01HDNZ3SPASN8P9G5YYQGRFC8F=additional-information h_01HDNZ3SPA99XHVBPXVWB5MN86=discrepancies-guide h_01HDNZ1BW5EBP0JCX84MTYPQ6K=see-also" />
