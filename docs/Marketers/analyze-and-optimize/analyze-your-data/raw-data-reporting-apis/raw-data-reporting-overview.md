---
title: "Raw data reporting overview"
excerpt: "Row-level data (aka raw data) describes events relating to users like installs, in-app events, website visits, Protect360 blocked installs, ad revenue generated, and user-associated postbacks sent to partners. Raw data reports are available via download, API, and Data Locker."
x-zendesk:
  id: 209680773
  url: https://support.appsflyer.com/hc/en-us/articles/209680773-Raw-data-reporting-overview
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Raw data reporting/APIs
  section_id: 6550930711057
  position: 0
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-rona-einat, Marketers, Agencies, Raw Reports]
  labels: [LTV, raw data, uninstalls, AFI, Advertisers, Agencies, Premium Feature, Gray, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2016-03-21T08:32:06Z'
  edited_at: '2026-08-11T08:38:12Z'
---
## Raw data reporting—tools and reports

Raw data reports enable you to analyze user behavior and journeys, reconcile ad network accounts, and enrich your CRM and BI systems. By using raw data, you increase your ability to analyze, optimize, and improve app performance.

Reports are made available via reporting tools. The tools have different characteristics suited to different use cases. For example, to reconcile a given ad network account, download the report as needed via the Export data page. To get user performance data to load into your BI systems, get the data programmatically using Data Locker or Pull API.

> 📘 **Tip**
>
> Want to understand more about your raw data? Check out this short, informative [course on the AppsFlyer Learning Portal](https://elevate.appsflyer.com/learn/course/7806/play/18629/viewing-and-understanding-your-raw-data).

<div id="reporting-tools-characteristics-and-features" />

<Accordion title="Reporting tools—characteristics and features">

Reports are made available using the reporting tools listed in this section.

Considerations:

* The report date range relates to the activity (actual) date the event took place. This is in contrast to aggregated reports where the date range is [LTV-based](/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports).
* Fields descriptions—see the [data field dictionary](/docs/raw-data-field-dictionary).

#### Reporting tools

<table><thead><tr><th>Tool</th><th>Description</th><th>Multiple /single app (1)</th><th>Data freshness capability (2)</th><th>Embed in scripts</th><th>Time zone</th><th>Currency</th></tr></thead><tbody><tr><td><a href="./raw-data-export-page">Raw data export page</a></td><td><ul><li>Download report using the user interface</li><li>Format: CSV file</li></ul></td><td>Single</td><td>Continuously updated</td><td><span><strong>x</strong></span></td><td>App-specific</td><td>App-specific</td></tr><tr><td><a href="./pull-api-raw-data">Pull API\*</a></td><td><ul><li>Download report using API calls.</li><li>Format: CSV files</li></ul></td><td>Single</td><td>Continuously updated</td><td><span><strong>✓</strong></span></td><td><ul><li>Selectable</li><li>Default: UTC</li></ul></td><td><ul><li>Selectable</li><li>Default: USD</li></ul></td></tr><tr><td><a href="./data-locker-for-marketers">Data Locker</a> <span><strong>P</strong></span></td><td><ul><li>Data streamed to a <a href="./data-locker-cloud-service-setup">bucket in the cloud</a></li><li>No volume limitations</li><li>Data availability window: 14 days.</li><li>Format: CSV or  parquet</li></ul></td><td>Multiple</td><td>Continuously updated with a lag of several hours</td><td><span><strong>✓</strong></span></td><td>UTC</td><td>USD </td></tr><tr><td><a href="./push-api-streaming-raw-data">Push API<span></span></a> <span><strong>P</strong></span></td><td><ul><li>User journey data (installs, in-apps, retargeting, SKAN) sent to your servers in real-time.</li><li>Format: JSON or query params</li></ul></td><td>Can use the same endpoint</td><td>Minutes after the event is recorded in AppsFlyer</td><td><span><strong>✓</strong></span></td><td>UTC + app-specific</td><td>USD + app-specific</td></tr><tr><td><a href="./conversion-data-payloads-and-scenarios">SDK Conversion data</a> (3)</td><td><ul><li>Get attribution conversion data within the app.</li><li>Format: JSON</li></ul></td><td>N/A</td><td>SDK conversion data retrieves user attribution data in up to 8 seconds from the first app launch (up to 5 seconds on AppsFlyer servers, plus end-to-end network delay).</td><td><span><strong>✓</strong></span></td><td>UTC</td><td>N/A</td></tr><tr><td colspan="7"><strong>Notes and abbreviations:</strong><br/>(1) Multiple app support<br/>(2) Actual data freshness depends on the report itself, as some reports are Daily.<br/>(3) SDK conversion data retrieves user attribution data in up to 8 seconds from the first app launch (up to 5 seconds on AppsFlyer servers, plus end-to-end network delay), and therefore is the least accurate method.<br/><span><strong>(P) </strong></span><span>Premium feature</span><br/><a href="./report-generation-quotas-rate-limitations">(\*) Report generation quotas apply</a></td></tr></tbody></table>

#### Tool limitations

<table><thead><tr><th>Limitation </th><th>Pull API (\*)</th><th>Push API</th><th>Data Locker</th><th>SDK<br/>Conversion data</th></tr></thead><tbody><tr><td>Data limit</td><td>1M rows per call</td><td>N/A</td><td>N/A</td><td>N/A</td></tr><tr><td>Data selection options</td><td>Select data types. Limited field selection options</td><td>Select data types, fields, and in-apps</td><td>Select data types, fields, and in-apps</td><td>No</td></tr><tr><td>Data availability window</td><td>90 days</td><td>N/A</td><td>14 days </td><td>Lifetime (available in the SDK)</td></tr><tr><td colspan="5"><a href="./report-generation-quotas-rate-limitations">(\*) Report generation quotas apply</a></td></tr></tbody></table>

#### Integration considerations

| Consideration | Pull API | Push API | Data Locker | SDK  <br />Conversion Data |
| --- | --- | --- | --- | --- |
| Server-side development | Optional | Required | Optional | Optional |
| Requires data processing | Optional | Required | Optional | Optional |
| Risk of data loss | No | Yes, if receiving servers are down | No | Small, if there are delays in ad network response |
| Client-server processing costs | None | High | Low | None (unless sending the data to the servers) |
| Client-server maintenance | None | High | Low | None (unless sending the data to the servers) |
| Data format | CSV file | JSON or query params | CSV or parquet | JSON |

</Accordion>

Raw data records occurring in a given context are grouped together in reports. For example, non-organic installs, organic in-app events. For ease of explanation, reports are grouped as follows:

* **User journey:** Use to trace the journey and engagement of a user with the app.  
  For example: click > install > in-app event > uninstall.
* **Feature:** Relate to a given AppsFlyer feature but aren't part of the main user journey. For example, postbacks to ad networks, fraud and Validation Rules reports, and user-level ad revenue reports.

<Accordion title="Report fields">

The [raw data](/docs/raw-data-field-dictionary) field dictionary contains fields relevant to user journey reports and some feature report fields. The principles are as follows:

* **User journey:**
  * Have a common set of fields.
  * Field population depends on the journey context. For example, non-organic reports contain the media source credited with bringing the user. Attribution fields in organic reports aren't populated because there is no media source.
* **Feature**: Have a unique set of fields or contain user journey fields and additional fields relevant to the feature. For example, SKAdNetwork reports have a unique list of fields, whereas postback reports contain the user journey fields and additional fields relating to postback sending to partners.

**Tip**! The best way to become familiar with the reports is to view reports. You can download your reports via the [Export data page](/docs/raw-data-export-page).

For ease of understanding, user journey fields are divided into groups based on context.

#### User journey raw data field groups

| Field group | Relevant to organic users | Example fields |
| --- | --- | --- |
| App | Yes | App ID, app name, app version, SDK version, ATT |
| Attribution | No, except for install time | Install time, attributed touch time, media source, campaign, adset, ad, partner, retargeting conversion type |
| Contributors attribution | No | Contributor partner, match type |
| Device info | Yes | Advertising ID, GAID, OAID, device type, customer user ID |
| Device location | Yes | IP address, city, country |
| Event | Yes | Populated in in-app event reports:<br /><br />Event name, event value, event revenue |

</Accordion>

## User journey reports

![Raw_data_-_User_acquisition_.png](https://files.readme.io/319da2a6a5567d6cfe4a74337279e67e0bdcdb063e62ecacde5eb4293a98a1a2-36317497158033.png)

<Accordion title="User journey basics">

User journey reports contain data collected for events occurring during a user's lifetime. The data is divided into reports according to:

* User source: organic or non-organic
* Journey context:
  * Engagement with ads before app install (impressions and clicks)
  * Acquisition
  * Retargeting

**User acquisition (UA) reports contain:**

* The impressions and clicks occurring before install by any *potential* user engaging with an ad.
* Install event.
* Subsequent in-app events performed by the user.

**Retargeting reports contain:**

* The impressions and clicks occurring when the user is retargeted.
* Conversion events: Either a re-engagement or re-attribution.
* Subsequent in-app events performed as part of the re-engagement. Consider:
  * Retargeting data is always non-organic.
  * Retargeting in-app events are in both the UA and retargeting in-app event reports. See [retargeting double-attribution](/docs/resolve-retargeting-double-attribution) methodology.

    ![Raw_data_-_Retargeting.png](https://files.readme.io/717f6e43ca3b224ead9e3e1c5f9b277d2f21dbc1fe3b4c217ebf4bdbc539bab7-36317470735249.png)

To follow a user journey, combine the reports that relate to the part of the journey that interests you, for example, installs and in-app events. Having done so, sort the report using AppsFlyer ID, event time, and report type. The result is the events of a given user over time, meaning the user journey.

</Accordion>

<div id="user-journey-report-availability" />

<Accordion title="User journey report availability">

* Report availability depends on your subscription plan.
* Reports can include either organic users, non-organic users, or both, as indicated.
* Retention policies apply to historical raw data reports depending on the reporting tool and the origin of the raw data. In general, data is available for the previous 90 days. **Note**! Retention policies don't apply to aggregated data.

#### User journey reports

<table><thead><tr><th>Category</th><th>Unique to Data Locker</th><th>Report topic</th><th>Organic</th><th>Non-organic</th></tr></thead><tbody><tr><td>User acquisition</td><td><span><strong>✓</strong></span></td><td>Clicks</td><td colspan="2">N/A</td></tr><tr><td>Retargeting</td><td><span><strong>✓</strong></span></td><td>Clicks from retargeting campaigns </td><td colspan="2">Retargeting always non-organic</td></tr><tr><td>User acquisition</td><td><span><strong>✓</strong></span></td><td>Impressions</td><td colspan="2">N/A</td></tr><tr><td>Retargeting</td><td><span><strong>✓</strong></span></td><td>Impressions from retargeting campaigns</td><td colspan="2">Retargeting always non-organic</td></tr><tr><td>User acquisition</td><td>-</td><td>Installs </td><td><span><strong>✓</strong></span></td><td><span><strong>✓</strong></span></td></tr><tr><td>User acquisition</td><td>-</td><td>In-app events </td><td><span><strong>✓</strong></span></td><td><span><strong>✓</strong></span></td></tr><tr><td>User acquisition</td><td>-</td><td>Attributed ad revenue</td><td>-</td><td><span><strong>✓</strong></span></td></tr><tr><td>User acquisition</td><td>-</td><td>Organic ad revenue</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>Retargeting</td><td>-</td><td>Retargeting ad revenue</td><td colspan="2">Retargeting always non-organic</td></tr><tr><td>Retargeting</td><td>-</td><td>Retargeting conversions (re-engagements and re-attributions)</td><td colspan="2">Retargeting always non-organic</td></tr><tr><td>Retargeting</td><td>-</td><td>Retargeting in-app events (re-engagements and re-attributions)</td><td colspan="2">Retargeting always non-organic</td></tr><tr><td>Retargeting</td><td><span><strong>✓</strong></span></td><td>Retargeting sessions (re-engagements and re-attributions)</td><td colspan="2">Retargeting always non-organic</td></tr><tr><td>User acquisition</td><td><span><strong>✓</strong></span></td><td>Sessions</td><td><span><strong>✓</strong></span></td><td><span><strong>✓</strong></span></td></tr><tr><td>User acquisition</td><td>-</td><td>Non-organic uninstalls </td><td>-</td><td><span><strong>✓</strong></span></td></tr><tr><td>User acquisition</td><td>-</td><td>Organic uninstalls</td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td>User acquisition</td><td><span><strong>✓</strong></span></td><td>Cross-platform engagements</td><td><span><strong>✓</strong></span></td><td><span><strong>✓</strong></span></td></tr></tbody></table>

</Accordion>

<Accordion title="User journey report descriptions">

#### Clicks and impressions

| Report | Characteristics |
| --- | --- |
| Context | A user engages with a campaign and clicks or views an ad. |
| Characteristics | The reports contain a record of the attribution link and HTTP headers present when a user clicks or [views](/docs/measure-view-through-engagements#set-impression-links) an ad. |
| Use case | <ul><li>Optimize campaigns that don't lead to an app open (install, re-attribution, re-engagement).</li><li>Retarget these users using different campaigns.</li></ul> |
| Example report | [Clicks](https://docs.google.com/spreadsheets/d/e/2PACX-1vRcNRnKgPP5ZRL51o3b9PDhbFv6VFG7xe9xHqCsIC7HwqO2ERLV5dh4bS7pr-WONxpUXvsCc64eTzzN/pub?gid=1036692270&single=true&output=csv) |
| Remarks | SRN data not available. |
| Restricted users | In some cases, due to privacy rules, impression and click data is either restricted (doesn't have user identifiers) or is not available at all. The availability depends on the media source and platform. |

#### Installs and retargeting conversions

<table><thead><tr><th rowspan="2">Report name </th><th rowspan="2"><p>User acquisition: Installs</p></th><th rowspan="2">Retargeting: Conversions</th></tr></thead><tbody><tr><td>Context</td><td><p>When a user opens an app for the first time.</p></td><td><p>After a user engages with a retargeting ad and then opens the app. A retargeting conversion being a re-engagement or re-attribution.</p>See <a href="./retargeting-attribution-guide#retargeting-reports-and-raw-data">Retargeting attribution guide. </a></td></tr><tr><td>Use cases</td><td><ul><li>Generate aggregated reports using fields not available via AppsFlyer analytics tools.</li><li>Combine with other reports for advanced, cross-section analysis.</li><li>Analyze performance across different dimensions such as cities, metropolitan areas, and so on. </li><li>Segment users according to country, city, and language for targeting purposes.</li><li>Obtain user device IDs for retargeting purposes.</li></ul></td><td>Similar to installs.</td></tr><tr><td>Organic vs. non-organic</td><td><ul><li><strong>Non-organic:</strong> The attribution and contributors attribution field groups are populated</li><li><strong>Organic: </strong>The media source field is either blank, null, or organic. Consider this when you load data into your systems. </li></ul></td><td>Not applicable</td></tr><tr><td>Example report</td><td><a href="https://docs.google.com/spreadsheets/d/e/2PACX-1vR2yvNGmZp8ataHBj89CFq856PmDixnyjKK75O8fQcS9TjT8J2jBAnJoTn3350NV-7pCSlaT0oh8ebs/pub?output=csv">Installs</a></td><td>Retargeting conversions report has the same structure as the installs report. Some fields are populated in the context of retargeting. See <a href="./retargeting-attribution-guide#retargeting-reports-and-raw-data">retargeting raw data</a>. </td></tr></tbody></table>

#### In-app events

| Report | Characteristics |
| --- | --- |
| Report context | Chronological list of the actions performed by users after attribution (install, re-attribution, or re-engagement) |
| Characteristics | <ul><li>The report structure and fields are similar to those of install reports.</li><li>Dedicated fields describe the event. These include the event name, value, revenue, and time.</li></ul> |
| Use case | Use the report to:<ul><li>Gain insights by observing the user journey during the user's lifetime</li><li>Combine the install and in-app-event raw data to follow the complete user journey.</li></ul> |
| <span id="event-values"></span>Event values | **Event value field**<br /><br />The event value field contains all the data related to the event in a JSON. You can load this into your BI system for further analysis.<br /><br />**Tip!** You can use [Power Query in Microsoft Excel](https://docs.microsoft.com/en-us/power-query/parse-json-xml) to parse the event parameters from the JSON text strings.<br /><br />```<br />{"af_level":"10","af_user_journey":"3387","arena":"7","char_type":"paladin"}<br />```<br /><br />**Reporting revenue**<br /><br />The revenue and ROI data in AppsFlyer are derived from the af\_revenue sent in events.<br /><br />When the af\_revenue parameter is sent in an in-app-event, AppsFlyer uses this to populate the event revenue field. It is in this field that AppsFlyer uses to update the dashboard and aggregated reports.<br /><br />Note! Use only the af\_revenue parameter with in-app-events that describe **actual revenue generated.** For other events that involve revenue, but are not final, for example, add\_to\_cart, use different parameters like af\_price |
| Example report | [In-app events](https://docs.google.com/spreadsheets/d/e/2PACX-1vQhOF-g3HeqZt3rXx7WZVQnB54p7ALW_IEpnJ9xtAkrcb9XzZwweiNCZzEmuX7q0i1g6yYMxYtuuX1c/pub?output=csv) |
| Remarks | <ul><li>Retargeting in-app events are [doubly recorded](/docs/resolve-retargeting-double-attribution) in both the UA and retargeting in-app event raw data reports.</li><li>In-app events don't include the launch (af\_app\_opened) event. This is available in the [sessions](/docs/measure-sessions) raw data report.</li><li>Geo location: Is derived using the user IP address at the time the event is performed.</li></ul> |

#### Sessions

| Report | Characteristics |
| --- | --- |
| Context | When the user opens the app, a session event is sent to AppsFlyer. The event is recorded if the [minimum time between sessions](/docs/measure-sessions) threshold is exceeded. |
| Characteristics | The report structure is the same as in-app event reports. Sessions (session events) are in a separate report due to the large number of such events. |
| Use case | Understand user engagement with the app. |
| Example report | The sessions report is similar to the in-app events report. Note: In raw data, sessions have the event name *launch*. |

#### Uninstalls

| Report | Characteristics |
| --- | --- |
| Context | Record of users uninstalling the app. |
| Characteristics | <ul><li>This report updates daily and not continuously, as is the case for other user journey reports.</li><li>In the report, the event time represents the time AppsFlyer determines the app was uninstalled, and not the actual uninstall itself. See Uninstall measurement.</li></ul> |
| Fields available | <ul><li>If the user comes from a non-organic media source, media source fields are populated.</li><li>Consider that the uninstall event is generated by AppsFlyer servers after determining that the user uninstalled. Consequently, many fields aren't populated.</li><li>User identifiers available are those recorded at the time of install. The CUID is never available.</li><li>Geo-related fields are populated with the user location at the time of engagement with the media source (click or impression). If the engagement location isn't available then the location associated with the install event is used.</li></ul> |
| Example report | [Uninstalls](https://docs.google.com/spreadsheets/d/e/2PACX-1vRcNRnKgPP5ZRL51o3b9PDhbFv6VFG7xe9xHqCsIC7HwqO2ERLV5dh4bS7pr-WONxpUXvsCc64eTzzN/pub?gid=1558773473&single=true&output=csv) Note! In the example, for clarity, row 2 indicates which fields are populated if relevant data is available. |
| Use cases | <ul><li>Analyze the uninstall event, device, and user characteristics.</li><li>Build an uninstall event audience for retargeting.</li></ul> |

</Accordion>

<Accordion title="User journey report availability per tool">

#### Ad engagement report by tool

<table><thead><tr><th>Report</th><th>Export data</th><th>Pull API</th><th>Data Locker</th><th>Push API</th><th>SDK<br/>Conversion Data</th></tr></thead><tbody><tr><td>Impressions (1)</td><td>-</td><td>-</td><td><span><strong>✓</strong></span></td><td>-</td><td>-</td></tr><tr><td>Clicks (1)</td><td>-</td><td>-</td><td><span><strong>✓</strong></span></td><td>-</td><td>-</td></tr><tr><td colspan="6">(1) Clicks and impressions data is made available by non-SRNs. SRNs don't make this data available.</td></tr></tbody></table>

#### User acquisition reports by tool

| Report | Export data | Pull API | Data Locker | Push API | SDK conversion data |
| --- | --- | --- | --- | --- | --- |
| Installs | **✓** | **✓** | **✓** | **✓** | **✓** |
| Sessions | - | - | **✓** | - | - |
| In-app events | **✓** | **✓** | **✓** | **✓** | - |
| Uninstalls | **✓** | **✓** | **✓** | - | - |

#### Retargeting raw data reports by tool

<table><thead><tr><th>Report</th><th>Export data</th><th>Pull API</th><th>Data Locker</th><th>Push API</th><th>SDK<br/>conversion Data</th></tr></thead><tbody><tr><td>Clicks (1)</td><td>-</td><td>-</td><td><span><strong>✓</strong></span></td><td>-</td><td>-</td></tr><tr><td>Conversions (re-attributions + re-engagements)</td><td><span><strong>✓</strong></span></td><td><span><strong>✓</strong></span></td><td><span><strong>✓</strong></span></td><td><span><strong>✓</strong></span></td><td><span><strong>✓</strong></span></td></tr><tr><td>Impressions (1)</td><td>-</td><td>-</td><td><span><strong>✓</strong></span></td><td>-</td><td>-</td></tr><tr><td>Sessions</td><td>-</td><td>-</td><td><span><strong>✓</strong></span></td><td>-</td><td>-</td></tr><tr><td>In-app events</td><td><span><strong>✓</strong></span></td><td><span><strong>✓</strong></span></td><td><span><strong>✓</strong></span></td><td><span><strong>✓</strong></span></td><td>-</td></tr><tr><td colspan="6">(1) Clicks and impressions data is made available by non-SRNs. SRNs don't make this data available.</td></tr></tbody></table>

</Accordion>

<Accordion title="FAQ">

| Details |
| --- |
| **What is the difference between the timestamps?**<br /><br />The timestamps are common to all the reports. This makes it possible to combine different reports.<br /><br />The following timestamps are relevant:<ul><li>**Attributed touch time**: The time the user engaged with an ad.</li><li>**Install** **time**: The time that the app is launched for the first time.</li><li>**Event time**: The time the event takes place.</li></ul>Consider:<ul><li>In install reports, the install and event times are the same.</li><li>In in-app event reports, the install and event times are different. The difference can show the time that passes between app launch and user engagement with the app.</li></ul> |
| **What is the purpose of the contributor field?**<br /><br />The contributor field lists contributor media sources. Sometimes referred to as [Assisted Installs](/docs/measure-assisted-installs#assisted-installs-reporting). In Protect360, it is also used for [hijacked install attribution correction](/docs/protect360-raw-data-reports#hijacked-installs-attribution-correction). |
| **What is the keywords field—why isn't available in all non-organic installs?**<br /><br />Installs attributed to Google Ads or Apple Ads, can contain the keywords or keyword ID associated with the ad bringing the install. |

</Accordion>

<Accordion title="Install report tips">

**Understanding the user journey**

A user journey is a series of steps that the user performs before achieving a goal like purchasing a product or booking a flight. The idea behind analyzing a user journey is to see what the user does in the app, how active they are, and what value they bring during a given period.

You can identify and highlight user journeys with the help of the AppsFlyer ID. The ID is generated for each app install per device. The ID remains unchanged throughout the user lifecycle (from install to uninstall.) The ID persists if the user resets their device ID.

Since the install and in-app events reports have the same structure, they can be merged into a single report. In the merged report, you can aggregate and filter by AppsFlyer ID and Customer User ID (if available) to analyze user journeys.

> 📘 **Engaged user—strong**
>
> * A user installed the app on August 20 at 09:31.
> * The merged report shows that they made purchases on August 20 at 10:31, August 22 at 15:22, and August 25 at 16:47.
> * From this, we conclude that the user is an engaged user. They made a purchase one hour after launching the app and continued purchasing on the days following the install.
>
> #### Engaged user—weak
>
> * A user installed the app on July 30. The merged report shows that they added an item to their cart on August 15, but there are no subsequent purchase events.
> * You can assume that the user is hesitant to make a purchase and choose to retarget them with the item they added to the cart.
>
> #### Analyzing the user journey for campaign optimization
>
> * The user acquisition (UA) manager of a travel app downloads the install and in-app event reports and merges them.
> * Then, to view user journeys in the app, they filter or aggregate data by AppsFlyer ID.
> * They notice that a given user, identified by their AppsFlyer ID, downloaded the app 12 months ago and booked a flight several days later.
> * Subsequently, the user viewed a few flight deals but didn't make any bookings. Looking further, the UA manager discovers more users with the same pattern and decides to dig even deeper.
> * They find that most of these users came from **Ad A** of **Campaign B** run on **Media source C.** It turns out that this ad and campaign targeted users who wanted to travel to a specific destination.
> * By analyzing the user journey, the UA manager might conclude that the campaign was too narrowly focused and that users weren't sufficiently engaged by the app.

</Accordion>

## Feature reports

Reports relating to additional features available in the platform

* [Ad revenue](/docs/roi360-guide-ad-revenue-attribution#ad-revenue-raw-data)
* [Incrementality](/docs/incrementality-for-remarketing-overview#raw-data-reports)
* [SKAdNetwork](/docs/skan-raw-data-reports)

<div id="postbacks" />

<Accordion title="Postbacks">

Use postback reports, to review copies of data sent to an ad network. For example, use them to investigate discrepancies. These reports are for information purposes, and are not required for integration with ad networks.

* The report contains:
  * Copies of postbacks sent to the attributed media source.
  * [Raw data fields](/docs/raw-data-field-dictionary) and additional fields as detailed in this section.
* The report doesn't contain:
  * SRN installs.
  * In-app events relating to Meta ads, X Ads, and Apple Ads.
  * Unattributed partner postbacks. See [events attributed to any partner or organic](/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration).
  * Organic users. See [about organic installs.](/docs/set-up-an-integrated-partner#default-postbacks)
* Starting in March 2021, fields are populated according to a network's Advanced Privacy setting. Meaning, if Advanced Privacy is on, some fields, like user identifiers aren't included. See [Advanced Privacy postback specification for ad networks.](/docs/advanced-privacy-guide-postback-macros-for-ad-networks#advanced-privacy-postback-specification)
* [Get postback reports by PULL API](https://dev.appsflyer.com/hc/reference/get_app-id-postbacks-v5)

#### Postback reports (available via the Export Data page and Pull API)

| Report topic | Events sent to the attributed media source |
| --- | --- |
| Installs | Non-organic (UA) installs |
| In-app events | Non-organic in-app events |
| Retargeting conversion postbacks | Retargeting (re-engagement and re-attribution) |
| Retargeting in-app events | Retargeting in-app events |

#### Additional fields in postback reports

| Field | Remarks |
| --- | --- |
| Postback URL | Some values, like revenue, may not appear in the appropriate field, but you can still see this data in the **Postback** URL. |
| Postback method |  |
| Postback HTTP response code | 200: Confirms that the postback was received by the ad network |
| Postback error message |  |

</Accordion>

<div id="protect360-fraud-and-validation-rules" />

<Accordion title="Protect360 fraud and validation rules">

* See [Protect360](/docs/protect360-raw-data-reports) and [validation rules](/docs/implement-validation-rules-to-prevent-fraud#outcomes) raw data reports
* Ad networks and agencies need advertiser [permission](/docs/set-up-an-integrated-partner#access-protect360-dashboard-raw-data) to access Protect360 and Validation Rules reports

**To grant an integrated partner permission to access Protect360:**

1. Go to **Collaborate**> **Active Integrations**.
2. Select the integrated partner.
3. In the **Permissions** tab, turn on **Access your Protect360 dashboard & raw data via API**.
4. To give access to the In-app events (CPA) dashboard, turn on **Access aggregate in-app events data**.

</Accordion>

> 📘 **See also**
>
> * [Aggregate reports and analytics](/docs/aggregated-and-analytics-reporting-overview)