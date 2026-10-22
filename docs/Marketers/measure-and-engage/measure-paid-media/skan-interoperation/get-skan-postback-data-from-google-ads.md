---
title: Get SKAN postback data from Google Ads
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
  created_at: '2021-06-28T19:34:39Z'
  edited_at: '2026-09-08T07:01:05Z'
  id: 4403215779857
  locale: en-us
  section: SKAN interoperation
  section_id: 6552115163153
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/4403215779857-Get-SKAN-postback-data-from-Google-Ads
---
> **At a glance:** Enable Google to share the content of your SKAdNewtork (SKAN) app iOS postbacks with AppsFlyer.

## Get SKAN postback data from Google Ads

If you work with multiple ad network partners, the best practice is to set it up in AppsFlyer. By doing so, SKAN performance metrics for all your ad network partners, enriched with other metrics like cost, are available via the AppsFlyer platform.

**Scope of SKAN reporting with Google Ads**

* Google Ads shares aggregated iOS SKAN postbacks they receive with AppsFlyer in the context of iOS app campaigns. These postbacks represent installs from multiple channels such as display, YouTube, and search.
* AppsFlyer decodes the postback and then updates the SKAN dashboard and reports (including the postback raw data report).
* <Anchor target="_blank" href="/marketers/docs/self-reporting-networks-srns#ios-145-srn-attribution">iOS 14.5 implications on SRN reporting</Anchor>

**Considerations**:

On receipt of the iOS postback, Google determines the last click time using ad serving signals. However, AppsFlyer regards the click time as the install time. This can lead to differences between the AppsFlyer and Google dashboards.

Because of Google's click-reporting methodology and its retroactive data update on a daily basis, AppsFlyer pulls the data for the previous 45 days and displays the install under the last click before the install date.  For example, a click on July 1st can be reported to AppsFlyer until  August 15. AppsFlyer displays this install under the click date reported by Google. This impacts <Anchor target="_blank" href="/marketers/docs/skadnetwork-skan-solution-guide#reporting-options">reports</Anchor> as follows:

* Aggregated reports and the dashboard update retroactively.
* <Anchor target="_blank" href="/marketers/docs/skan-raw-data-reports">Raw data reports</Anchor> don't change retroactively. Data (provided via Data Locker) is provided in folders according to the date Google provided the data to AppsFlyer (data arrival date).

## Set up interoperation

To set up interoperation with Google Ads, complete the steps in the following tabs.

<Accordion title="Set up postbacks">

**To set up sending postbacks:**

| Step | Action | Details |
| --- | --- | --- |
| 1 | SKAN settings review | Verify that AppsFlyer <Anchor target="_blank" href="/marketers/docs/skadnetwork-skan-solution-guide">SKAN solution</Anchor> is set up and is on. Doing so allows the AppsFlyer SDK to call SKAN APIs and set the conversion value.<br /><br />**To review SKAN settings**:<ol><li>In AppsFlyer, go to **Settings** > **SKAN Conversion Studio**.</li><li>Click options (⋮), and verify that **SKAN measurement** is on.<br />![skan-settings.png](https://files.readme.io/5602fded7e030177bb921ff83ff1e6dad7a230a87825e112314935a4c3dd83dd-4406452045457.png)</li><li>Select your preferred measurement mode.<br />Learn more about <Anchor target="_blank" href="/marketers/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>.</li><li>Make a note of the exact event names set. You'll need them in the next step. **Note**! Names are case-sensitive.</li></ol> |
| 2 | In-app event mapping in AppsFlyer | **To view and set in-app event mapping**:<ol><li>In AppsFlyer, go to **Collaborate** > **Active integrations**.</li><li>Select **Google Ads**.</li><li>From the **Integration** tab, verify that **Activate Partner** is on. If not, you must first complete the <Anchor target="_blank" href="/marketers/docs/google-ads-adwords-integration-setup-for-advertisers">integration with Google Ads</Anchor>.</li><li>In the **In-app events postbacks section**:<ol><li>If not on, turn on **In-app events postbacks**.</li><li>The best practice is to map the events related to the currently selected measurement type. Note! In the case of revenue measurement, map af\_skad\_revenue to the appropriate Google revenue event</li></ol></li><li>Scroll down to the bottom of the page.</li><li>Click **Save integration**.</li></ol> |

</Accordion>

<Accordion title="Allow Google Ads to share SKAN data with AppsFlyer">

In order to see SKAN installs attributed to Google Ads in the AppsFlyer SKAN dashboard, you must allow Google Ads to share SKAN data with AppsFlyer.

**To grant Google Ads permission to share SKAN data with AppsFlyer:**

1. The procedure that follows must be performed by the advertiser. In the case of an agency, both the agency and advertiser have to enable SKAN measurement.
2. In AppsFlyer, go to **Collaborate** > **Active integrations**.
3. Search for and select **Google Ads**.
4. Go to the **SKAN** tab. <Image alt="mceclip0.png" src="https://files.readme.io/ba8d881ca8430bfdcf67a37e862ad3e31a9af522f2f877d3fba30bc2e13006a6-4404428381457.png" width="309px" />
5. If the **temporarily unavailable message displays**, most times it means an ad blocker is active. If so, disable the ad blocker and reload the page. If this is not the case, contact AppsFlyer support.  ![mceclip1.png](https://files.readme.io/e86b868f71e11ad347ff7557a793090d9d6adb8fe4df4f9010c8d770b373ac6a-4404428420497.png)
6. Click **Connect** **Google Ads**.
   * You must log in to Google Ads using an Administrator user role on the account.
   * If the Google account is associated with multiple apps, log in once, and all apps are authorized. In other words, there is no need to authorize on a per-app basis.
   * AppsFlyer pulls data for all the AppsFlyer iOS apps that your Google account is associated with, irrespective of the app's activate partner setting.
7. Follow the instructions in the user interface.
8. In some cases, you might be prompted to give AppsFlyer permission to **Manage your AdWords campaigns.** If so, you must enable the permission. Don't worry, we won't make changes to your campaign settings. [![GoogleManageAdWords.png](https://files.readme.io/bf327f152f937cdbea0b71cca72cc989aa83de6cef83677fca1f687b71aa8606-4405185007121.png)](https://files.readme.io/bf327f152f937cdbea0b71cca72cc989aa83de6cef83677fca1f687b71aa8606-4405185007121.png)
9. Verify that the account status, **waiting for sync** displays.  
   This message persists until we get data from Google Ads (maximum 24 hours.)
10. Wait until after 02:00 UTC of the next day, then verify that the status changes to **active.**  
    Data in the SKAN dashboard updates daily by 08:00 UTC. **Note**! As described in the considerations section, Google can update data 45 days retroactively.
11. Read about [measurement differences](/docs/get-skan-postback-data-from-google-ads#measurement-and-timing-differences-between-appsflyer-and-google-ads).

</Accordion>

## Additional information

<Accordion title="Turning off the SKAN integration">

When turning off your Google Ads integration, it's not enough to turn off the **Activate partner** toggle, you must separately remove the SKAN connections to stop SKAN data recording.

**To turn off the SKAN integration:**

1. In AppsFlyer, go to **Collaborate** > **Active integrations**.
2. Search for and select Google Ads.
3. Go to the **SKAN** tab.
4. Click the delete icon for the account you want to remove.

</Accordion>

<Accordion title="Measurement and timing differences between AppsFlyer and Google Ads">

| Item | Details |
| --- | --- |
| Earliest data availability | Data is available starting on the date that you enable the integration according to the UTC time. Because Google uses the click time, installs from before the starting date can display retroactively. |
| Install date | Google sets the install time to the estimated last click time before the install. It is Google that determines the click time using ad serving signals.<br /><br />The following should be considered when comparing media sources and the dashboard in AppsFlyer:<ul><li>AppsFlyer doesn't consider the app time zone or the Google Ads ad account time zone.</li><li>Google can report installs retroactively for 45 days after the install date.</li><li>In the case of other media sources, we derive the install time using the postback arrival time.</li></ul> |
| Installs | From Google Ads API V10+, AppsFlyer only displays installs from postbacks with the did\_win=TRUE. As a result, the installs number in AppsFlyer may be lower than in the Google Ads dashboard. |

</Accordion>

<Accordion title="Troubleshooting and FAQ">

| Item | Details |
| --- | --- |
| Sending events to Google Ads | **Q**: Does it make sense to send additional event postbacks to Google Ads for events not selected in the conversion value measurement option?<br /><br />**A**: For consenting users, send the full range of events to maximize Google Ads' ability to optimize. |
| Map multiple events to the same Google Ads event | **Q**: Can I map multiple in-app events to one Google Ads event?<br /><br />**A**: If multiple events are mapped to one Google Ads standard event, Google Ads can't differentiate between the events. So, Google Ads will optimize toward the one event they recognize. |
| Campaign types supported | **Q:** What types of Google Ads campaigns are supported?<br /><br />**A**: Web-to-app and App-to-app iOS campaigns including search, video, and so on. |
| No data to pull | **Q:** Why does the connection status display "No data to pull: Check your Google data-sharing permissions"?<br /><br />**A**: Either there is no SKAN data yet or you need to log into Google Ads using an Administrator user role on the account. |

</Accordion>

<Accordion title="Specifications and limitations">

| Spec | Description |
| --- | --- |
| Engaged views | Engaged views are counted as clicks and postbacks are sent for them as they are for any click-through attribution. |
| Data freshness | <ul><li>We collect SKAN data from Google Ads daily starting 01:00 UTC.</li><li>Dashboards and aggregate data update 7 hours later.</li><li>Google occasionally experiences delays in its SKAN pipeline, so data might arrive later than usual and single source of truth (SSOT) data might also be affected.<ul><li>Once Google delivers the delayed data, it is updated retroactively.</li></ul></li></ul> |
| Reports available | Google Ads data is available in the SKAN dashboard, aggregate, and raw data reports. See<Anchor target="_blank" href="/marketers/docs/skadnetwork-skan-solution-guide#reporting-options"> SKAN reporting options.</Anchor> |
| Agencies | If the agency has an Administrator user role in the advertiser's Google Ads account, then they can perform the procedure in this article and enable Google SKAN interoperation on behalf of the advertiser. Advertisers don't need to log in to their Google Ads as well. The agency login is indicated in the advertiser's account. |

</Accordion>

<Accordion title="Not seeing SKAN installs from Google Ads?">

Use this checklist to confirm your setup is correct and data can flow into the AppsFlyer SKAN dashboard.

**Quick fix checklist**

1. Check integration status.
   * Confirm the Google Ads integration is active in AppsFlyer.
   * In the **SKAN** tab, verify the status shows **Active**. If it shows **Temporarily unavailable**, disable any ad blockers and reload the page.
2. Authorize the Google Ads connection, if not already connected.
   * Click **Connect Google Ads**.
   * Log in using a Google Ads Administrator account, and allow AppsFlyer to manage AdWords campaigns if prompted.
3. Wait for sync.
   * After you log in, the status shows **Waiting for sync**.
   * Once AppsFlyer starts receiving SKAN data from Google, the status changes to **Active** — this can take up to 24 hours.
   * After that, SKAN dashboard data updates daily by 08:00 UTC.

**Still not working?**

If you've completed the steps above and installs still aren't showing, check the following:

* If the status shows "No data to pull: Check your Google data-sharing permissions," Google hasn't shared SKAN data yet, or you need to log into Google Ads using an Administrator user role.
* Make sure you're running SKAN-specific campaigns in Google Ads and are logged in with an Administrator account.
* Check install counts directly in Google Ads:

  1. In Google Ads, go to **Campaigns**.
  2. Click the **Reports** icon > **Goals and conversions** > **SKAdNetwork conversions**.
  3. If you see "Error loading report — This report is incompatible with the current view filters," click **Clear view filters**.
  4. Use the column search (magnifying glass icon) to find and add SKAN-specific columns, such as **SKAdNetwork conv. value segment**.

  If there are no installs in Google, there won't be any in AppsFlyer. Check with your Google representative to understand why there are no installs.

**Good to know**

* SKAN data is collected from Google Ads daily starting at 01:00 UTC. Google's data can occasionally take up to two extra days to arrive.
* Only Web-to-app and App-to-app iOS campaigns are supported for SKAN measurement.

</Accordion>

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/docs/skadnetwork-skan-solution-guide">AppsFlyer SKAN Solution guide</Anchor>

<div data-zendesk-anchors="h_01HCHYGCVJA3C8WJS8JH7BG0CD=get-skan-postback-data-from-google-ads h_01HCHYGCVJY5KT4J6RQS0BJ90G=set-up-interoperation h_01HCHYGCVJTS53PCGK21BEZB2T=additional-information h_01HE7RMSECNDW9VD9XY6H01H55=see-also" />
