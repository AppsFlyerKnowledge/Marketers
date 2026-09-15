---
title: "Protect360 dashboard"
excerpt: "The Protect360 dashboard provides insights about fraudulent traffic and installs blocked due to the application of validation rules."
---
**At a glance:** The Protect360 dashboard provides insights about fraudulent traffic and installs blocked due to the application of validation rules.

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

### Filters and groupings

**Filter and groupings window**

[![p360_filters_2.png](https://files.readme.io/9fd2afbbfc1bdf671ae0427d75c1020085b36da724e40dcfe57da27943e15b0c-4408431325969.png)](https://support.appsflyer.com/hc/article_attachments/4408431325969)

The following filtering and grouping options are available:

* Basic filters:
  * App name
  * Source type: Non-organic and/or organic
  * Media source
  * Geo
  * Date range ([see time zone support](/docs/about-data-freshness-and-timezone-support#protect360-dashboard))
  * Attribution type: Installs, re-attributions, and/or re-engagements
  * [Payable events](/docs/protect360-dashboard#payable-events) (available in the In-app events dashboard)
* Expanded filters - click on the blue arrow, to the right of the date picker:
  * Agencies
  * Campaigns
  * Channels
* Grouping options - choose different dimensions to group the fraud data by to get the specific insights you need:
  * **Application:** Compare the total amount of fraud per each of your apps.
  * **Media Source**(default): Compare the identified fraud from each of the media sources used by your apps
  * **Media Source + Campaign**: Compare the identified fraud from all your campaigns across all media sources used by your apps
  * **Media Source + Site ID**: Compare the identified fraud from all publishers (site IDs) across all media sources used by your apps
  * **Media Source + Site ID + Campaign**: Compare the identified fraud from all publishers (site IDs) across all media sources used by your apps, associated with the relevant campaign names
  * **Media source + Geo**: (available in the In-app events dashboard): compare the identified fraud from each of the media sources used by your apps associated with the relevant countries
  * **Media source + Attribution type**: Compare the identified fraud from each of your media sources, associated with the selected attribution type (installs, re-attributions, and/or re-engagements)
  * **Geo**: compare the identified fraud from all countries

## Installs dashboard

The installs dashboard displays LTV-based data, meaning data relating to installs, re-attributions, and re-engagements that occurred during your selected date range.

Dashboard features are described in the sections that follow.

### Installs—headline metrics

The headline metrics enable you to see:

* **Identified fraudulent attributions** - Total number of fraudulent installs
* **Blocked in-app events** - Number of fraudulent (in-app) events
* **Total of tagged attributions** - Total of tagged attributions
* **Total of tagged in-app events** - Total of tagged in-app events
* **Identified compromised installs** - Number of installs detected with inauthentic engagements
* **Average engagement per install** - Average number of  engagements associated with the install

For each KPI, there is a percentage value. This value shows how the presented KPI is in relation to the parallel date range before it. For example, this week compared to last week, or any days selected in the date range compared to the same number of days that came before: if it shows an X% increase in estimated savings, it means the previous parallel date range had X% fewer fraudulent installs, re-attributions, and re-engagements.

**Identified fraudulent attributions**

[![](https://support.appsflyer.com/hc/article_attachments/4408437121297)](https://support.appsflyer.com/hc/article_attachments/4408437121297)

Total identified fraud metrics display the amounts of:

* Fraudulent installs, re-attributions, and re-engagements blocked in real-time for all the various fraud-blocking reasons.
* Installs, re-attributions, and re-engagements identified as fraud post-attribution.

**Blocked in-app events**

[![](https://support.appsflyer.com/hc/article_attachments/4403139249809)](https://support.appsflyer.com/hc/article_attachments/4403139249809)

Blocked in-app events metrics display the amount of in-app events blocked by AppsFlyer. The events may have been blocked due to belonging to blocked installs, or due to being marked as suspicious post-attribution events.

**Total of tagged attributions**

[![](https://support.appsflyer.com/hc/article_attachments/32184720638097)](https://support.appsflyer.com/hc/article_attachments/32184720638097)

Tagged attributions metrics display the number of installs that were recognized as fraud but have been marked by the user as tagged and not blocked. this does not include in-app events.

**Total of tagged in-app events**

[![](https://support.appsflyer.com/hc/article_attachments/32637238112145)](https://support.appsflyer.com/hc/article_attachments/32184720638097)

Tagged in-app events metrics display the number of installs that were recognized as fraud but have been marked by the user as tagged and not blocked.

**Identified compromised installs**

![](https://support.appsflyer.com/hc/article_attachments/41459847283729)

Installs where the device was detected by AppsFlyer attribution logic as being flooded with inauthentic engagements.

**Average engagement per install**

![](https://support.appsflyer.com/hc/article_attachments/41459862819857)

 Average engagement per install shows the average number of engagements associated with the install.

### Installs—charts

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
* [Blocked sub-reason](/docs/protect360-raw-data-reports#install-level-fake-install-block-reasons)
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

### Installs—table

#### Identified fraud breakdown

The **Identified fraud breakdown** table displays the following data:

* Fraud blocked in real-time
* Fraud identified and marked post-attribution
* Other indications of fraud per media source

The table is presented in a general overview format, as shown in the image that follows.

[![p360_main_table.png](https://files.readme.io/15885268068f2b57e9b22b7028a824951690e737a47cb154cd38d1ddf79937b8-4408431449745.png)](https://support.appsflyer.com/hc/article_attachments/4408431449745)

The dynamic table structure:

* Lets you click the table settings button to add or remove columns to the table.  
  If you make any changes to the table, make sure to click the **Save** button afterward.
* Is per user, so every account user with access to Protect360 can personally customize their own table structure. See [more table options](/docs/protect360-dashboard#additional-table-options).

[![edit_table.jpg](https://files.readme.io/fcde2bc6970c29902dd7585ee92c2bc38edf1d5c56e65de4e3f10df784108e5c-360011641617.jpg)](https://support.appsflyer.com/hc/article_attachments/360011641617)

#### Content of the identified fraud breakdown table



| Table Column | Description |
| --- | --- |
| Groupings | * [Default] The table and dashboard are grouped by Media source.<br />* When selecting a specific media source, the grouping is automatically by both Media source and Site ID.<br />* Optional groupings include Campaign, GEO, Channel, Agency, Agency + Media Source, and combinations thereof.<br />* If you select a grouping with dimensions that only apply to non-organic traffic, the table displays N/A for the organic media source. |
| **Attributions** | **Headline breakdown of blocked and post-attribution fraudulent installs.** |
| Total (A) | * Total installs = Regular (non-fraudulent) installs + blocked installs<br />* Regular installs are available per media source (non-organic) in the Overview dashboard. |
| Blocked (B) | * Total number of blocked installs.<br />* [Default] The table is sorted in descending order using this KPI. |
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

## In-app events dashboard

The in-app events dashboard displays activity-based data, meaning data relating to in-app events that occurred during your selected date range, including events from installs that happened before the date range.

Dashboard features are described in the sections that follow.

### In-app events—headline metrics

[![](https://support.appsflyer.com/hc/article_attachments/360012501757)](https://support.appsflyer.com/hc/article_attachments/360012501757)

The headline metrics enable you to see:

* Estimated savings
  * Only available if [**Payable events**](/docs/protect360-dashboard#payable-events) is enabled.
  * Based on the payable events you have configured.
* Total number of identified fraudulent IAEs

### In-app events—charts

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

### In-app events—table

The **In-app event fraud breakdown** table displays the following data:

* Fraud blocked in real-time
* Fraud identified and marked post-attribution
* Other indications of fraud per media source

The table is presented in a general overview format, as shown in the image that follows.

[![IAE_fraud_table.jpg](https://files.readme.io/dd57a2508911b3e26268ad8cc4508d5402fa091ac95a77900c7f257486c99aeb-360012839758.jpg)](https://support.appsflyer.com/hc/article_attachments/360012839758)

The dynamic table structure:

* Lets you click the table settings button to add or remove columns to the table.  
  If you make any changes to the table, make sure to click the **Save** button afterward.
* Is per user, so every account user with access to Protect360 can personally customize their own table structure. See [more table options](/docs/protect360-dashboard#installs%E2%80%94table).

[![iae_table_structure.jpg](https://files.readme.io/5b2933e2b254d8fa268e30a72ae53691da391e365d781d55bcdb6cfeb1f40a6a-360012839778.jpg)](https://support.appsflyer.com/hc/article_attachments/360012839778)

#### Content of the in-app event fraud breakdown table



| Table Column | Description |
| --- | --- |
| Groupings | * [Default] The table and dashboard are grouped by Media source.<br />* When selecting a specific media source, the grouping is automatically by both Media source and Site ID.<br />* Optional groupings include Campaign, GEO, Channel, Agency, Agency + Media Source, and combinations thereof. |
| **In-app events** | **Headline breakdown of blocked and post-attribution fraudulent IAEs.** |
| Total IAE (A) | * Total IAE = Regular (non-fraudulent) IAEs + blocked IAEs + IAEs identified as fraud post-attribution.<br />* Regular IAEs are available per media source (non-organic) in the Overview dashboard. |
| Total fraudulent IAE (B) | * Total number of blocked IAEs + IAEs identified as fraud post-attribution.<br />* [Default] The table is sorted in descending order using this KPI. |
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

### Payable events

Payable events are IAEs that have a cost. Once enabled and configured, the In-app activity dashboard only displays data related to payable events.

**To enable Payable events in the In-app activity dashboard**:

* In the **Filter by** section of the In-app activities dashboard, enable Payable events.  
  [![](https://support.appsflyer.com/hc/article_attachments/360012576718)](https://support.appsflyer.com/hc/article_attachments/360012576718)

**To configure payable events**:

1. In the In-app activities dashboard, click **Configure payable events**.

   [![](https://support.appsflyer.com/hc/article_attachments/360012505217)](https://support.appsflyer.com/hc/article_attachments/360012505217)

   The Configure payable events popup displays.

   [![](https://support.appsflyer.com/hc/article_attachments/360012580938)](https://support.appsflyer.com/hc/article_attachments/360012580938)
2. [Optional] If you configuring a new payable event, click **Add new**.
3. Based on which payable IAEs you want to display in the dashboard, select the following from the drop-down menus:
   * Apps
   * In-app events
   * Media sources
   * Campaigns
4. Enter the CPA of the IAE.
5. Click **Save.**
6. Click **Close.**

## Traits and limitations



| Trait | Remarks |
| --- | --- |
| Retargeting | * The installs (CPI) dashboard can display the attributed touch-type breakdown between installs, re-attributions, and re-engagements.<br />* The in-app event (CPA) dashboard displays fraudulent events from UA installs, but not from retargeting. **Note**: Fraudulent events from re-attributions that are identified in real-time, can be viewed in raw data reports. |
| Historical data | Data is available from the start of the Protect360 subscription |
| Data freshness | Updated daily.<br /><br />* Installs (CPI) at 16:00 UTC<br />* In-app events (CPA) at 21:00 UTC |
| Media source not available | If a media source is not available in the filter it can be due to all of its traffic being blocked.<br /><br />In order to filter based on the media source, you can use its link from the identified fraud breakdown table |



> 📘 **See also**
>
> * [Protect360 Overview](/docs/protect360-anti-fraud-guide)
> * [Raw data reports](/docs/protect360-raw-data-reports)