---
title: Protect360 dashboard
metadata:
  keywords:
    - dashboard
    - Advertisers
    - Protect360
    - protect 360
    - '360'
    - P360
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2020-08-11T09:58:07Z'
  edited_at: '2026-05-07T00:01:09Z'
  id: 360011793077
  locale: en-us
  section: Protect your traffic
  section_id: 6551015912465
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360011793077-Protect360-dashboard
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **At a glance:** The Protect360 dashboard provides insights about fraudulent traffic and installs blocked due to the application of validation rules.

## About Protect360 dashboard

The Protect360 dashboard:

* Displays aggregate fraud data at the account level.
* Has two dashboard views:
  * Installs (CPI)
  * In-app events (CPA)
* Organizes fraud based on categories, including:
  * Fake versus hijacked installs
  * Fraud blocked in real-time versus fraud identified post-attribution
  * Fraud from UA versus retargeting campaigns
* Allows you to drill down to further examine fraud events by using the filtering and grouping options.

To view the Protect360 dashboard, in AppsFlyer, go to **Optimize** > **Protect360.**

<div id="filters-and-groupings" />

<Accordion title="Filters and groupings">

**Filter and groupings window**

[![p360_filters_2.png](https://files.readme.io/9fd2afbbfc1bdf671ae0427d75c1020085b36da724e40dcfe57da27943e15b0c-4408431325969.png)](https://files.readme.io/9fd2afbbfc1bdf671ae0427d75c1020085b36da724e40dcfe57da27943e15b0c-4408431325969.png)

The following filtering and grouping options are available:

* Basic filters:
  * App name
  * Source type: Non-organic and/or organic
  * Media source
  * Geo
  * Date range (<Anchor target="_blank" href="/marketers/docs/about-data-freshness-and-timezone-support#protect360-dashboard">see time zone support</Anchor>)
  * Attribution type: Installs, re-attributions, and/or re-engagements
  * [Payable events](/docs/protect360-dashboard#payable-events) (available in the In-app events dashboard)
* Expanded filters - click on the blue arrow, to the right of the date picker:
  * Agencies
  * Campaigns
  * Channels
* Grouping options - choose different dimensions to group the fraud data by to get the specific insights you need:
  * **Application:** Compare the total amount of fraud per each of your apps.
  * **Media Source** (default): Compare the identified fraud from each of the media sources used by your apps
  * **Media Source + Campaign**: Compare the identified fraud from all your campaigns across all media sources used by your apps
  * **Media Source + Site ID**: Compare the identified fraud from all publishers (site IDs) across all media sources used by your apps
  * **Media Source + Site ID + Campaign**: Compare the identified fraud from all publishers (site IDs) across all media sources used by your apps, associated with the relevant campaign names
  * **Media source + Geo**: (available in the In-app events dashboard): compare the identified fraud from each of the media sources used by your apps associated with the relevant countries
  * **Media source + Attribution type**: Compare the identified fraud from each of your media sources, associated with the selected attribution type (installs, re-attributions, and/or re-engagements)
  * **Geo**: compare the identified fraud from all countries

</Accordion>

## Installs dashboard

The installs dashboard displays LTV-based data, meaning data relating to installs, re-attributions, and re-engagements that occurred during your selected date range.

Dashboard features are described in the sections that follow.

<div id="installs-headline-metrics" />

<Accordion title="Installs—headline metrics">

The headline metrics enable you to see:

* **Identified fraudulent attributions** - Total number of fraudulent installs
* **Blocked in-app events** - Number of fraudulent (in-app) events
* **Total of tagged attributions** - Total of tagged attributions
* **Total of tagged in-app events** - Total of tagged in-app events
* **Identified compromised installs** - Number of installs detected with inauthentic engagements
* **Average engagement per install** - Average number of  engagements associated with the install

For each KPI, there is a percentage value. This value shows how the presented KPI is in relation to the parallel date range before it. For example, this week compared to last week, or any days selected in the date range compared to the same number of days that came before: if it shows an X% increase in estimated savings, it means the previous parallel date range had X% fewer fraudulent installs, re-attributions, and re-engagements.

**Identified fraudulent attributions**

[![](https://files.readme.io/262403803bd074e4742f63d7998d4642e3b17781e178ed3bc24b35dd958ca262-4408437121297.png)](https://files.readme.io/262403803bd074e4742f63d7998d4642e3b17781e178ed3bc24b35dd958ca262-4408437121297.png)

Total identified fraud metrics display the amounts of:

* Fraudulent installs, re-attributions, and re-engagements blocked in real-time for all the various fraud-blocking reasons.
* Installs, re-attributions, and re-engagements identified as fraud post-attribution.

**Blocked in-app events**

[![](https://files.readme.io/ed6692be83cae6a6bee556e5c763d6313c0d32cb577a9587caac41c54b51b378-4403139249809.png)](https://files.readme.io/ed6692be83cae6a6bee556e5c763d6313c0d32cb577a9587caac41c54b51b378-4403139249809.png)

Blocked in-app events metrics display the amount of in-app events blocked by AppsFlyer. The events may have been blocked due to belonging to blocked installs, or due to being marked as suspicious post-attribution events.

**Total of tagged attributions**

[![](https://files.readme.io/49e705c39b88c243af92c88e33d1939d1ec54b6a83e94724bdef702c9442a6a6-32184720638097.png)](https://files.readme.io/49e705c39b88c243af92c88e33d1939d1ec54b6a83e94724bdef702c9442a6a6-32184720638097.png)

Tagged attributions metrics display the number of installs that were recognized as fraud but have been marked by the user as tagged and not blocked. this does not include in-app events.

**Total of tagged in-app events**

[![](https://files.readme.io/79650837a722efdc3bea39664f0d5eb774ac6acbfb15e5f64d9a56f7c03b21fe-32637238112145.png)](https://files.readme.io/49e705c39b88c243af92c88e33d1939d1ec54b6a83e94724bdef702c9442a6a6-32184720638097.png)

Tagged in-app events metrics display the number of installs that were recognized as fraud but have been marked by the user as tagged and not blocked.

**Identified compromised installs**

<Image alt="" src="https://files.readme.io/60fdba97e9eb920e26ac2667431b760a7dee62b53396196403d68326bff6c3cc-41459847283729.png" width="624px" />

Installs where the device was detected by AppsFlyer attribution logic as being flooded with inauthentic engagements.

**Average engagement per install**

<Image alt="" src="https://files.readme.io/edb695ad30e16e403d953fd0fad274d5733ca4e2dc411baad7bbe4179cfcd0b0-41459862819857.png" width="624px" />

 Average engagement per install shows the average number of engagements associated with the install.

</Accordion>

<div id="installs-charts" />

<Accordion title="Installs—charts">

#### Identified fraud trend chart

The identified fraud trend chart displays the number of fraudulent installs, re-attributions, and re-engagements per day, broken down by either:

* **Detection type**: Installs blocked in real-time and installs identified as fraud post-attribution.
* **Attribution type**: Installs, re-attributions, and re-engagements.
* **Source type**: Non-organic and organic.
* **Detection status**: Comparing Tagged, Untagged, and Blocked data.
* **Compromised rate**: Total attributions flagged as compromised out of total attributions.

The display can be either a line graph or a bar chart.

#### Hijacked installs attribution correction chart

The hijacked installs attribution correction chart displays media sources that attempted to take credit for installs, re-attributions, and re-engagements, as well as the last valid contributor sources.

You can:

* Filter by hijacked attributions identified in real-time, post-attribution, or attributions identified via validation rules.
* Set to which valid sources attribution is corrected or from which hijacked sources attribution was corrected.
* Change the chart view to a table format, and download the data as a CSV.

**Note:**

* This chart is only accessible to advertisers. Agencies and ad networks do not have access.
* When the hijackings are blocked in real-time, the correct attributions display in AppsFlyer dashboards and reports (not just Protect360). When hijackings are identified post-attribution, the correct attributions are displayed only in Protect360 raw data.
* This chart can display correction **to** organic, but not **from** organic.

#### Identified fraud chart

The identified fraud chart displays the types of fraud you experience, by percentage. Fraud breakdown can be by:

* Block reason
* <Anchor target="_blank" href="/marketers/docs/protect360-raw-data-reports#install-level-fake-install-block-sub-reasons">Blocked sub-reason</Anchor>
* Tag type
* Tag reason
* Tag sub reason
* Media source
* Campaign
* Geo
* App

#### Affiliate Attribution Model

AppsFlyer’s new **Affiliate Attribution Model** solves the click-flooding problem head-on. At the core is a dedicated attribution algorithm that actively detects flooded devices and validates engagement using authentication methods and real-time AI behavioral analysis. The result is attribution that is unbiased, resilient to fraud, and grounded in real user intent.

* **Compromised rate:** total attributions flagged as compromised out of total attributions
* **Candidate's reflection:**
  * Candidates per compromised - average number of candidates from total attributions **flagged** as compromised
  * Candidates per non-compromised - average number of candidates from total attributions **not** **flagged** as compromised
* Those metrics are also reflected in the trend chart over time:
  * Compromised total install
  * Candidates per compromised
  * Candidates per non-compromised

Compromised installs are installs where the device was detected by AppsFlyer attribution logic as being flooded with inauthentic engagements. This indicates the device was under heavy flooding manipulation, specifically referring to instances where installs are manipulated

</Accordion>

<div id="installs-table" />

<Accordion title="Installs—table">

#### Identified fraud breakdown

The **Identified fraud breakdown** table displays the following data:

* Fraud blocked in real-time
* Fraud identified and marked post-attribution
* Other indications of fraud per media source

The table is presented in a general overview format, as shown in the image that follows.

[![p360_main_table.png](https://files.readme.io/15885268068f2b57e9b22b7028a824951690e737a47cb154cd38d1ddf79937b8-4408431449745.png)](https://files.readme.io/15885268068f2b57e9b22b7028a824951690e737a47cb154cd38d1ddf79937b8-4408431449745.png)

The dynamic table structure:

* Lets you click the table settings button to add or remove columns to the table.  
  If you make any changes to the table, make sure to click the **Save** button afterward.
* Is per user, so every account user with access to Protect360 can personally customize their own table structure. See [more table options](/docs/protect360-dashboard#additional-table-options).

[![edit_table.jpg](https://files.readme.io/fcde2bc6970c29902dd7585ee92c2bc38edf1d5c56e65de4e3f10df784108e5c-360011641617.jpg)](https://files.readme.io/fcde2bc6970c29902dd7585ee92c2bc38edf1d5c56e65de4e3f10df784108e5c-360011641617.jpg)

#### Content of the identified fraud breakdown table

| Table Column | Description |
| --- | --- |
| Groupings | <ul><li>[Default] The table and dashboard are grouped by Media source.</li><li>When selecting a specific media source, the grouping is automatically by both Media source and Site ID.</li><li>Optional groupings include Campaign, GEO, Channel, Agency, Agency + Media Source, and combinations thereof.</li><li>If you select a grouping with dimensions that only apply to non-organic traffic, the table displays N/A for the organic media source.</li></ul> |
| **Attributions** | **Headline breakdown of blocked and post-attribution fraudulent installs.** |
| Total (A) | <ul><li>Total installs = Regular (non-fraudulent) installs + blocked installs</li><li>Regular installs are available per media source (non-organic) in the Overview dashboard.</li></ul> |
| Blocked (B) | <ul><li>Total number of blocked installs.</li><li>[Default] The table is sorted in descending order using this KPI.</li></ul> |
| Blocked % (B/A) | Blocked installs / Total installs |
| Post-attribution (C) | Installs identified as fraud post-attribution. |
| Post-attribution % (C/A) | Post-attribution installs / Total number of installs |
| Total fraudulent installs (D) | Fraudulent installs, blocked in real-time or identified as fraudulent post-attribution. |
| Fraudulent installs % (D/A) | Fraudulent installs / Total number of installs |
| **Fraud attribution type breakdown** | **The attribution types of the fraudulent installs, broken down into installs, re-attributions, and re-engagements.** |
| Installs | Fraud originated from a UA campaign. |
| Re-attributions | Fraud originated from a retargeting campaign that led to an install. |
| Re-engagements | Fraud originated from a retargeting campaign that led to a re-engagement. |
| **Fake** | **Fraudulent installs or re-attributions simulating real user activity - divided by real-time blocks and post-attribution.** |
| Real-time block | Fake installs blocked in real-time. |
| Post-attribution fraud | Fake installs identified as fraud post-attribution. |
| **Hijacked** | **Fraudulent last clicks stealing attribution of real user installs - divided by real-time blocks and post-attribution.** |
| Real-time block | Hijacked installs blocked in real-time. |
| Post-attribution fraud | Hijacked installs identified as fraud post-attribution. |
| **Validation rules** | **Installs meeting validation rules conditions.** |
| Blocked installs | Installs blocked by validation rules. |
| Blocked attribution | Attribution changes of installs due to validation rules. |
| **Fake installs block breakdown** | **Breakdown of blocked and post-attribution fraudulent fake installs usually performed programmatically.** |
| Blocked site ID denylist | Installs blocked due to Protect360 denylisting the SiteID. |
| Post-attribution site ID denylist | Installs marked as fraud due to Protect360 post-attribution denylisting of the SiteID. |
| Blocked bots | Blocked installation attempts made by automatic bots. |
| Post-attribution bots | Installs marked as fraud due to identified automatic bots activities post-attribution |
| Blocked behavioral anomalies | Installs blocked due to behavioral anomalies, meaning, abnormal session and in-app event performance of users. |
| Post-attribution behavioral anomalies | Installs marked as fraud due to behavioral anomalies post-attribution. |
| Blocked install validation | Total installs blocked due to negative store validation. |
| **Hijacked installs block breakdown** | **Breakdown of fraudulent last clicks aimed to steal attribution of real user app installs.** |
| Blocked install hijacking | Blocked install hijacking of the source. |
| Post-attribution install hijacking | Install hijacking marked as fraud in post-attribution. |
| Blocked CTIT anomalies | Installs blocked due to CTIT anomalies. |
| Post-attribution CTIT anomalies | CTIT anomalies marked as fraud in post-attribution. |
| Blocked click flooding | Installs blocked due to click flooding (fraud attempts to send large numbers of clicks hoping to deliver the last clicks prior to random installs.) |
| Post-attribution click flooding | Click flooding installs marked as fraud in post-attribution. |
| **Clicks** | **Clicks from the source**<br /><br />**Note:** All attribution types must be selected in the filter bar in order for click data to display in the table (otherwise it will display as N/A). Be sure to adjust your filter selections accordingly. |
| Total (E) | Total number of legitimate and fraudulent clicks received from the source |
| Blocked | Clicks blocked due to fraud |
| **Impressions** | **Impressions from the source**<br /><br />**Note:** All attribution types must be selected in the filter bar in order for impressions data to display in the table (otherwise it will display as N/A). Be sure to adjust your filter selections accordingly. |
| Total | Total number of legitimate and fraudulent impressions received from the source |
| Blocked | Impressions blocked due to fraud |
| **In-App Events** | **In-app events from the source**<br /><br />**Note:** This includes in-app events from installs; not re-attributions or re-engagements. |
| Total (G) | Total in-app events |
| Blocked (H) | Blocked in-app events |
| % (H/G) | Blocked in-app events / total in-app events |
| **Device farm indicators** | **Indicators of fraudulent device farm activity, using Device ID Reset and Limited Ad Tracking (LAT) fraud.**<br /><br />**Note:** This includes installs and re-attributions; not re-enagements. |
| Installs (I) | Installs having a new device ID not known to AppsFlyer. |
| Installs % (I/A) | New device installs / Total number of installs |
| Loyal user % | General KPI indicating if users are real or fake. |
| **Click flooding indicators** | **Indications of click flooding fraud based on abnormal conversion or assist rates, or CTIT time.** |
| Conversion rate (%) | Low percentage compared with the general app conversion rate indicates click flooding fraud.<br /><br />**Note**: All attribution types must be selected in the filter bar in order for conversion rate data to display in the table (otherwise it will show as N/A). Be sure to adjust your filter selections accordingly. |
| Assists % | High percentage compared with other media sources (in the Assists widget on the overview page) indicates click flooding fraud. |
| CTIT > Over 60 minutes | Installs, re-attributions, and re-engagements where the time between the click and first app launch is more than 60 minutes. The calculation only includes installs whose CTIT is under 25 hours (and not all installs). Typically, around 30% of first app launches occur more than 60 minutes after download. |
| CTIT > Over 5 hours | Installs, re-attributions, and re-engagements where the time between the click and first app launch is more than 5 hours. The calculation only includes installs whose CTIT is under 25 hours (and not all installs). Typically, around 20% of first app launches occur more than 5 hours after download. |

#### Additional table options

* Click **Export CSV** to download the table to your desktop in CSV format
* Click the gear icon to:
  * Change the order of table columns
  * Add or remove the columns described above
  * Add or remove any of your app's **recently blocked in-app events**. For each added in-app event the following columns are displayed:

| Table Column | Description |
| --- | --- |
| Events Counter (Total) | Number of the specific event's blocked occurrences |
| Unique Users | Number of unique users getting the specific event blocked |

Note that uncommon rates of either of these KPIs don't necessarily indicate fraud, as many events get blocked due to fraudulent post-attribution installs.

The in-app event data in the CPI dashboard is LTV-based, meaning it is all the in-app events associated with installs that occurred during the specified date range.

</Accordion>

## In-app events dashboard

The in-app events dashboard displays activity-based data, meaning data relating to in-app events that occurred during your selected date range, including events from installs that happened before the date range.

Dashboard features are described in the sections that follow.

<div id="inapp-events-headline-metrics" />

<Accordion title="In-app events—headline metrics">

[![](https://files.readme.io/ea33b3ddafc4265eb74b2e1070a77a6afbad429a1aeb20cd1579127f7e8ee605-360012501757.jpg)](https://files.readme.io/ea33b3ddafc4265eb74b2e1070a77a6afbad429a1aeb20cd1579127f7e8ee605-360012501757.jpg)

The headline metrics enable you to see:

* Estimated savings
  * Only available if [**Payable events**](/docs/protect360-dashboard#payable-events) is enabled.
  * Based on the payable events you have configured.
* Total number of identified fraudulent IAEs

</Accordion>

<div id="inapp-events-charts" />

<Accordion title="In-app events—charts">

#### **Fraud trend over time chart**

The fraud trend over time chart displays the number of events per day, broken down into:

* **Real-time**: Fraudulent in-app events blocked in real-time
* **Post-attribution**: Fraudulent events identified post-attribution
* **Non-fraud**

#### **Top IAE fraud by media source chart**

The top in-app event fraud by media source list contains: 

* The 5 media sources with the highest number of fraudulent in-app events in descending order.
* A bar chart for each media source bar that displays the following in-app event types as a percentage of total in-app events:
  * **Real-time**: Fraudulent in-app events blocked in real-time
  * **Post-attribution**: Fraudulent events identified post-attribution
  * **Non-fraud**

</Accordion>

<div id="inapp-events-table" />

<Accordion title="In-app events—table">

The **In-app event fraud breakdown** table displays the following data:

* Fraud blocked in real-time
* Fraud identified and marked post-attribution
* Other indications of fraud per media source

The table is presented in a general overview format, as shown in the image that follows.

[![IAE_fraud_table.jpg](https://files.readme.io/dd57a2508911b3e26268ad8cc4508d5402fa091ac95a77900c7f257486c99aeb-360012839758.jpg)](https://files.readme.io/dd57a2508911b3e26268ad8cc4508d5402fa091ac95a77900c7f257486c99aeb-360012839758.jpg)

The dynamic table structure:

* Lets you click the table settings button to add or remove columns to the table.  
  If you make any changes to the table, make sure to click the **Save** button afterward.
* Is per user, so every account user with access to Protect360 can personally customize their own table structure. See [more table options](/docs/protect360-dashboard#installs-table).

[![iae_table_structure.jpg](https://files.readme.io/5b2933e2b254d8fa268e30a72ae53691da391e365d781d55bcdb6cfeb1f40a6a-360012839778.jpg)](https://files.readme.io/5b2933e2b254d8fa268e30a72ae53691da391e365d781d55bcdb6cfeb1f40a6a-360012839778.jpg)

#### Content of the in-app event fraud breakdown table

| Table Column | Description |
| --- | --- |
| Groupings | <ul><li>[Default] The table and dashboard are grouped by Media source.</li><li>When selecting a specific media source, the grouping is automatically by both Media source and Site ID.</li><li>Optional groupings include Campaign, GEO, Channel, Agency, Agency + Media Source, and combinations thereof.</li></ul> |
| **In-app events** | **Headline breakdown of blocked and post-attribution fraudulent IAEs.** |
| Total IAE (A) | <ul><li>Total IAE = Regular (non-fraudulent) IAEs + blocked IAEs + IAEs identified as fraud post-attribution.</li><li>Regular IAEs are available per media source (non-organic) in the Overview dashboard.</li></ul> |
| Total fraudulent IAE (B) | <ul><li>Total number of blocked IAEs + IAEs identified as fraud post-attribution.</li><li>[Default] The table is sorted in descending order using this KPI.</li></ul> |
| Fraudulent events % (B/A) | Fraudulent IAEs/Total IAEs |
| **Fake IAE real-time blocks** | **Fraudulent IAEs blocked in real-time.** |
| Fake IAE | Fake IAE identified as fraud and blocked in real-time. |
| Fake installs | The original install was identified as fraud and blocked in real-time. |
| Post-attribution fake installs | The original install was identified as fraud post-attribution, before the IAE. |
| **Saved from hijacking in real-time** | **IAEs with the original install hijacked by a fraudulent source, that AppsFlyer correctly attributes to the last non-fraudulent source.** |
| Corrected to organic | Hijacked installs with the last non-fraudulent source being organic. |
| Corrected to non-organic source | Hijacked installs with the last non-fraudulent source being a non-organic media source. |
| **Post-attribution IAE fraud** | **In-app events identified as fraud post-attribution.** |
| Fake installs | IAE occurred before the install was identified as fraud post-attribution. |
| Hijacked installs | IAE occurred before the install was identified as hijacked, and cannot be correctly attributed post-attribution. |
| **Validation rules** | **IAEs blocked due to meeting validation rules conditions.** |
| Blocked installs | IAEs of installs blocked by validation rules. |
| Blocked IAE | IAEs blocked by validation rules. |
| Corrected to organic | Hijacked installs with the last non-fraudulent source being organic. |
| Corrected to non-organic source | Hijacked installs with the last non-fraudulent source being a non-organic media source. |

#### Additional table options

* Click **Export CSV** to download the table to your desktop in CSV format
* Click the gear icon to:
  * Change the order of table columns
  * Add or remove the columns described above

The amount of events shown is activity-based, and not LTV based, meaning it's the exact number of event blocks during the specified date range.

</Accordion>

<div id="payable-events" />

<Accordion title="Payable events">

Payable events are IAEs that have a cost. Once enabled and configured, the In-app activity dashboard only displays data related to payable events.

**To enable Payable events in the In-app activity dashboard**:

* In the **Filter by** section of the In-app activities dashboard, enable Payable events.  
  [![](https://files.readme.io/8162f6f4f6dcef50fbe0fd998b7a95d20deeb658dd53bafc216b75df050c734c-360012576718.jpg)](https://files.readme.io/8162f6f4f6dcef50fbe0fd998b7a95d20deeb658dd53bafc216b75df050c734c-360012576718.jpg)

**To configure payable events**:

1. In the In-app activities dashboard, click **Configure payable events**.

   [![](https://files.readme.io/00b1f4506f0c7ec8e1e1b90c16cc2232d2862b231b2673d2decc7a90b6c6b6af-360012505217.jpg)](https://files.readme.io/00b1f4506f0c7ec8e1e1b90c16cc2232d2862b231b2673d2decc7a90b6c6b6af-360012505217.jpg)

   The Configure payable events popup displays.

   [![](https://files.readme.io/4643b9d0e0042ca5860d21ec3eb3ff7e4178f92f1f4215db56adda10be41c452-360012580938.jpg)](https://files.readme.io/4643b9d0e0042ca5860d21ec3eb3ff7e4178f92f1f4215db56adda10be41c452-360012580938.jpg)
2. [Optional] If you configuring a new payable event, click **Add new**.
3. Based on which payable IAEs you want to display in the dashboard, select the following from the drop-down menus:
   * Apps
   * In-app events
   * Media sources
   * Campaigns
4. Enter the CPA of the IAE.
5. Click **Save.**
6. Click **Close.**

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Traits and limitations">

| Trait | Remarks |
| --- | --- |
| Retargeting | <ul><li>The installs (CPI) dashboard can display the attributed touch-type breakdown between installs, re-attributions, and re-engagements.</li><li>The in-app event (CPA) dashboard displays fraudulent events from UA installs, but not from retargeting. **Note**: Fraudulent events from re-attributions that are identified in real-time, can be viewed in raw data reports.</li></ul> |
| Historical data | Data is available from the start of the Protect360 subscription |
| Data freshness | Updated daily.<ul><li>Installs (CPI) at 16:00 UTC</li><li>In-app events (CPA) at 21:00 UTC</li></ul> |
| Media source not available | If a media source is not available in the filter it can be due to all of its traffic being blocked.<br /><br />In order to filter based on the media source, you can use its link from the identified fraud breakdown table |

</Accordion>

> 📄 **See also**
>
> * <Anchor target="_blank" href="/marketers/docs/protect360-anti-fraud-guide">Protect360 Overview</Anchor>
> * <Anchor target="_blank" href="/marketers/docs/protect360-raw-data-reports">Raw data reports</Anchor>

<div data-zendesk-anchors="01H8H9GQ17C4PBHCAMXE879BX7=about-protect360-dashboard 01H8H9GQ173SQ8P29C4DETJRTD=filters-and-groupings 01H8H9GQ173H3QH1Y5KZ26XMCW=installs-dashboard installs%E2%80%94headline-metrics=installs-headline-metrics 01H8H9GQ17FJKWE3M2YSZFTQCS=installs-headline-metrics installs%E2%80%94charts=installs-charts 01H8H9GQ18VHMK7FFV3RY409VB=installs-charts 01H8H9GQ18JDSZ2H8BKZVWGBPV=identified-fraud-trend-chart 01H8H9GQ18VXBPQRN55WHM3GG0=hijacked-installs-attribution-correction-chart 01H8H9GQ18FW87TXQZCYERHNDE=identified-fraud-chart h_01KQY7ARA2Z1WJ1V84X5GH832C=affiliate-attribution-model installs%E2%80%94table=installs-table 01H8H9GQ18FYXJA7TXQ4RNQGX2=installs-table 01H8H9GQ18540JJ8X833E6WF44=identified-fraud-breakdown 01H8H9GQ18DMPD7YTPTN2XJMSH=content-of-the-identified-fraud-breakdown-table 01H8H9GQ18PZ8ABG3D51M7J91R=additional-table-options inapp-events-dashboard=in-app-events-dashboard 01H8H9GQ19CQZV00XA62MGVJ86=in-app-events-dashboard inapp-events%E2%80%94headline-metrics=inapp-events-headline-metrics 01H8H9GQ19B95MDK2WEHVNEFS5=inapp-events-headline-metrics inapp-events%E2%80%94charts=inapp-events-charts 01H8H9GQ19XEJ0HNY2Y8BMX7A5=inapp-events-charts 01H8H9GQ1969AB4KK4ENP8AVQJ=fraud-trend-over-time-chart 01H8H9GQ19Z078PK1HR7VEZHXG=top-iae-fraud-by-media-source-chart inapp-events%E2%80%94table=inapp-events-table 01H8H9GQ19PTNWGJV6YDWR7SH6=inapp-events-table content-of-the-inapp-event-fraud-breakdown-table=content-of-the-in-app-event-fraud-breakdown-table 01H8H9GQ19773CS8TGS2QXBRG5=content-of-the-in-app-event-fraud-breakdown-table additional-table-options::44e54bfa=additional-table-options-1 01H8H9GQ192WA6XFNW7CKGBQ03=additional-table-options-1 01H8H9GQ1AVAVQ31ZZA1K024RF=payable-events 01H8H9GQ1BJX0K01NX8VCC0690=traits-and-limitations h_01HE7S2JKX3VMRCF6913S4MCAR=see-also" />
