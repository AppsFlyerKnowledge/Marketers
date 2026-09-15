---
title: "Overview dashboard—user acquisition and retargeting LTV"
excerpt: "The Overview dashboard gives advertisers a real-time window into the LTV performance of user acquisition and retargeting campaigns."
---
## Overview

Use the Overview dashboard to view campaign performance and app health. The dashboard contains user acquisition and retargeting campaign performance data enriched with data points like click, cost, and revenue. Most metrics update continuously in real-time.

![Dashboard Overview](https://files.readme.io/9ccd6af4db08b95040c283183b68337c6d528c46266ae98c6e47d53ec35289c9-d1e63ada853e249536b82099e8c70124.webp)

> 👍 Tip
>
> * If you don't run retargeting campaigns, use the [UA view](/docs/overview-dashboard-user-acquisition-and-retargeting-ltv#view-types).
> * If you're familiar with the V1.0 dashboard, you can skip to the [quick-start guide](https://support.appsflyer.com/hc/articles/360014697157#quickstart-guide) below.
> * Want to understand more about the Overview dashboard? Check out this short, informative [course on the AppsFlyer Learning Portal](https://elevate.appsflyer.com/learn/course/7801/play/18617/the-big-picture-of-your-marketing-data-overview-part-1).

### Terminology

* **Attributions**—consist of one or more of the following:
  * **Install**: The installation of an app by a user.
  * **Re-attributions**: AKA retargeting reinstall.
  * **Re-engagements**: User engaging with a retargeting campaign.
* **Organic**: Attribution not attributed to a media source.
* **Non-organic**: Attribution attributed to a media source.

See the [AppsFlyer Help Glossary](https://support.appsflyer.com/hc/articles/360000732237) for an in-depth list of all terms.

## Quick-start guide

### Power users

**View types**

The dashboard contains user acquisition and retargeting campaign data. The View type filter is used to filter between **Unified**, **User Acquisition**, and **Retargeting**. The same view types are implemented in the Cohort dashboard—power users are familiar with them.

**Attribution and attribution period**

* An attribution is an install, re-attribution, or re-engagement, based on the view type.
  * **Unified**: Installs, re-attributions, and re-engagements
  * **User acquisition:** Installs
  * **Retargeting:** Re-engagements and re-attributions
* The attribution period (dates) relates to the date a user performed an attribution. For example, in the User Acquisition view, it means the install date. In the Unified view, it means any of the attribution types.

> 📘 Note
>
> The retargeting view doesn't contain any cost-related metrics. Use the User Acquisition and Unified views to get the cost-related metrics.

**Settings and filters**

You must set a view type and attribution period in the settings and filters panel. The remaining filters are optional. Use the filters for a detailed analysis of your data.

**Widgets**

The dashboard is made up of widgets that include KPI headline metrics, charts, and tables.

**Charts**

* Bar/line over time chart. For example, installs per day.
* Donut/horizontal bar performance comparison. For example, revenue by geo.

In each chart, select a dimension and a metric.

**Tables**

* A table contains the top 25 or 50 media sources ranked by attributions.
* You can sort a table using the displayed metrics by clicking on the metric. The sort includes ranked media sources only.
* Drill down to view campaign performance at the ad level.
* Group by Source to view organic and non-organic data. Use Source to suppress organic data or to group by organic vs non-organic.
* To select the metrics you want to view in the table, click the settings icon ![gears.png](https://files.readme.io/c0141c4463a598d20c9ff0c042821c6e7ccfea3238ea49d3540d01150fec113c-360013047038.png).
* **N/A results**: Occur primarily in cost-related metrics. This limitation relates to the granularity of data provided by ad networks. Total values include N/A rows based on the total reported by ad networks.

### For CTV, PC, and console users

The dashboard for CTV, PC, and console apps gives app advertisers LTV insights for non-organic and organic users. Insights are based on subscription, in-app purchases, and ad monetization.

**Settings and filters**

Use the filters for a detailed analysis of your data. Filters available include the standard filters.

**Metrics**

All metrics are selectable.

## Dashboard view types and layout

### View types

![Dashboard View Types](https://files.readme.io/8f404774fd79fca19f176249377fa55a271f95ddc90a926828073817ea9413d0-d12ed3989ff54f684546224d777c343e.webp)

Data in the dashboard is presented via view types Unified, User acquisition, and Retargeting as described in the figure that follows.

![OV.png](https://files.readme.io/6429e4fbc5ba81eefba8635905b89ad43a1966b06fc6dccdd9a2af4bb042ae04-360012858117.png)

These view types contain LTV data as follows:

* **Unified:** display data under the last touch media source bringing the user according to AppsFlyer double attribution rules. Meaning that LTV occurring during re-engagements displays under the retargeting media source and not under the UA media source.
  * Shows all event data: new installs (organic and non-organic), re-engagements, re-attributions.
  * Re-engagements and re-attributions events are attributed to the retargeting media source and their parallel user acquisition events are deduped.
* **User acquisition:** attributed to a user acquisition media source including LTV occurring during re-engagement windows.
  * Includes new installs (organic and non-organic), and re-engagements (attributed to the original install media source).
* **Retargeting:** attributed to a retargeting media source for events occurring:
  * During a re-engagement window.
  * As a result of re-attributions.

### Layout

The dashboard opens using your currently selected default dashboard view.

By default, two predefined views, Extended overview, and Lite overview are available.

To learn how to change default views, see Dashboard views.

The dashboard contains the following functional areas:

* **A**: Dashboard views
* **B**: Filter bar
* **C**: KPI headline metrics
* **D**: Charts
* **E**: Tables

![OverviewV2.png](https://files.readme.io/c513b89b8ae3d041632e73cf8941b3ff7841c925d4db27908970f758b7cdb8b4-4419072259857.png)

## Dashboard features

### Dashboard views

![Dashboard Views](https://files.readme.io/a3085d8625e12d2fb7f662babe772aac762fa40568864051ed9803cf99ec9e21-b728a3a8cbb2eee538d0b3cd8f50ccd9.webp)

Two predefined layouts, Extended overview, and Lite overview are available. They have the same data and metrics but the number and style of charts they contain differ. Following are some of the layout differences.

#### **My reports layout and comparison**

| Layout Name | Details & Preview |
| --- | --- |
| **Lite overview** | **Charts available:** Two donut/horizontal performance comparison bar charts and one trend over time chart. A compact view highlighting what really matters.<br />![OverviewLayoutLite_us-en.jpg](https://files.readme.io/93fe2c4ea8983d43b93fbfad7bd2ea2a76c22b1a062c2204f817f5c50e78a4fc-360014947378.jpg) |
| **Extended overview** | **Charts available:** Seven donut/horizontal performance comparison charts and three trends over time charts. Providing a deep dive into the metrics.<br />![OverveiwFull_us-en.jpg](https://files.readme.io/1647a10f8dad6014fcbfce88381873a350f3ff3f20c468852b03ab9bfe35b312-360014947398.jpg) |

#### **Dashboard view selector**

**To select a report:**

![OverviewReportHeader.png](https://files.readme.io/cdd385c00260070734e569b929fbb7f02ad835d09da12c9800d7b43b6bfa1c40-4419080285969.png)

1. Click ▼ (My reports).
2. Select a dashboard: The dashboard displays using the report settings and current data.

**Icons on the dashboard view dropdown**

![MyReports.jpg](https://files.readme.io/e4d70b2acde417c28f8bd9788987496295dcf91f977a03c1b406f6c9158488ce-360014917077.jpg)

* **Delete**: Delete a report.
* **Favorite**: Set as the report that displays when you first open the dashboard.
* **Edit**: Change the current report settings.
* **Save current view**: The report is saved for your future use.
* Dashboards having the AppsFlyer logo are foundation dashboards and can't be changed.
* The dashboard with the blue star is the current default dashboard.

#### **Unsaved changes**

![UnsavedChanges.jpg](https://files.readme.io/da2d6b6d0b20c75c6cae98b247fa32fed84c4d18dcc0aa670ecdfb072163c39f-8711408071057.jpg)

* You are notified that your dashboard has been changed and not saved by the orange dot.
* To save the changes, click **Save dashboard** at the top-right of the page.

#### Localization—timezone and currency

The Overview dashboard can display data in timezone=UTC and currency=USD or in the app-specific timezone and local currency as set on the app settings page.

> 📘 Note
>
> Localization changes affect only your specific app dashboard; not the dashboard of other account users.

**To select/change the settings for timezone and currency**:

1. In the Overview dashboard, next to the timezone and currency display, click **Edit**.

![localize_tz_and_currency.png](https://files.readme.io/77fc90d3450cef5d3da9779ccab3da1eb485d5bf604df56463f625cf1c6dccb4-14632349655953.png)
2. For **Timezone**, select either UTC+0 or the app-specific timezone.
3. For **Currency**, select either USD or the app-specific currency.
4. Click **Apply**.

### Filter bar

Select the apps, view type, attribution date range, and display filters.

#### Apps

You can select up to 10 apps to view in the dashboard.

Dimensions and metrics for the selected apps are available in the combined dashboard. However, data for the fields are empty or marked as "none" when unavailable. For example, if you have an Android, iOS, and Roku app selected, DMA data is available only for the Roku app, and store product page data is available only for the iOS app.

#### View type

Attributions included by view type:

| View type | Unified | UA | Retargeting |
| --- | --- | --- | --- |
| Installs | Yes | Yes | - |
| Re-attributions | Yes | - | Yes |
| Re-engagements | Yes | - | Yes |

#### Attribution date range

Dates the attribution occurred.

> 📘 Note
>
> For SKAN, the date range is limited to 90 days.

#### Filters

Default filters available:

* Media source
* Campaign
* Geo

Click **+** to add one or more of the following filters:

* Ad
* Adset
* Agency (not available for CTV, PC, and console platforms)
* Source: Organic or non-organic
* Geo-related filters available for CTV, PC, and console apps: State, DMA, Ad placement

### Customizing dashboards

#### Saving a dashboard

You can customize your dashboard, select apps, view types, filters, and as described in the sections that follow, widgets, dimensions, and metrics.

* To save a dashboard, click **Save dashboard** at the top-right of the page.

The report is then saved for your future use. This includes the apps and other filters selected, the widget (KPI, chart and table) selection and placement, and the dimensions and metrics selected. **Note**: The date range isn't saved.

#### Re-arranging the dashboard

The dashboard is made up of widgets that include KPI headline metrics, charts, and tables.

Customize your dashboard by resizing and moving your widgets for a personalized view of your data:

* To move a widget, hover over the top and then drag and drop it.
* To resize a widget, expand the widget to the desired size from the bottom-right corner.
* To save the changes, click **Save dashboard** at the top-right of the page.

#### Adding more widgets

* To add a new widget click **Add Widget.**
  * You can choose the type of widget from the dropdown options.
* To save the changes, click **Save dashboard** at the top-right of the page.

#### Changing or removing widgets

* To remove a widget, click on the widgets menu then select the **Delete** button.
* To change chart widgets, click on the widgets menu and select the desired chart type.
* To save the changes, click **Save dashboard** at the top-right of the page.

#### Sharing a dashboard

After saving a custom dashboard, you can share it with others.

* To share a dashboard, click the ![share_icon.png](https://files.readme.io/d2e73ad4a67103eb405a599217e79fe0000939f7e56a92b3c419e523bc013298-14126248130833.png)**Share** icon at the top-right of the page and set the visibility to **Shared**. The dashboard then displays in the "Shared" list of dashboards instead of the "Private" list.
* [Optional] Copy and share the URL to the dashboard with others. Additionally, your custom dashboard becomes available in the view selector for other users.
* [Optional] Select whether to **Notify all account users about this shared dashboard**.

### KPI headline metrics

KPI headline metrics are provided in the context of the selected view type.

By default, the six most popular KPIs are displayed on the default dashboard view.

Any added KPIs will be added to the bottom of the dashboard and can be moved to anywhere else on the dashboard.

See Re-arranging the dashboard for more information.

**Metric component layout**

![HeadlineMetric.png](https://files.readme.io/9a82b47b6eb3619acccce5133cf1eb40f4ed45cb64cece30fea14076f48769f3-4464817083921.png)

* **A**: Metric type
* **B**: Tooltip
* **C**: Trend: Change in % compared to the previous adjacent period. Hover over to view the trend period.

| Metric | During the selected period... |
| --- | --- |
| User Acquisition | The number of users installing the app. |
| Retargeting | The number of users engaging with a retargeting campaign who re-attribute or re-engage. |
| Total revenue | Revenue LTV is measured by calculating the total of non-organic installs, organic installs, re-attributions, and re-engagements.<br />Revenue generated by users according to view type:<br />**User acquisition view:**<br />- Revenue is LTV, based on installs in the date range.<br />- Includes retargeting revenue of these users according to [retargeting attribution rules](https://support.appsflyer.com/hc/articles/360016371077).<br />**Retargeting**: Revenue generated by users re-attributing and from users re-engaging for the duration of the re-engagement window.<br />**Unified view:**<br />- Based on re-engagements and re-attributions in the date range, according to [retargeting attribution rules.](https://support.appsflyer.com/hc/articles/360016371077)<br />- installs might have happened before the date range. |
| Cost | [Campaign cost](https://support.appsflyer.com/hc/articles/207040526-Cost-aggregation-overview) relating to non-organic installs, re-attributions, and re-engagements. Reported to AppsFlyer by API or by click or impression URLs.<br />**User acquisition view:** Displays cost data of active campaigns (meaning campaigns with at least one install).<br />**Retargeting**: Not available<br />**Unified view:** Displays all cost data of active and inactive campaigns (meaning data from campaigns without any installs). This includes the costs of retargeting campaigns. |
| Non-organic installs | New installs attributed to a non-organic media source, usually following a click or impression engagement. |
| Organic installs | New installs by users who didn't engage with a media source beforehand. |
| Total installs | The total number of new installs, organic and non-organic, during the selected date range. Total installs = non-organic installs + organic installs. |
| eCPI | Formula for eCPI: eCPI = Total available cost / Attributions. Attributions include installs, re-attributions, and re-engagements.<br />To see your eCPI across all sources, select only the sources that share cost data. Campaigns without cost data, but with Installs, impact the accuracy of the eCPI, as installs with zero cost are accounted for. |
| CPC | Cost per click. Formula: Cost / Clicks |
| CPM | Cost per mille (1000 impressions). Formula: (Cost / Impressions) * 1000 |
| CTR | Click-through rate. Formula: Clicks / Impressions |
| Non-organic revenue | Lifetime revenue of users attributed to non-organic installs only. Measured from the install date until today. Revenue from organic users and re-attributed users is not included.<br />**User acquisition view:** Includes retargeting revenue |
| Organic revenue | Lifetime revenue generated by organic installs, from install date until the present (updates every 15 minutes).<br />**User acquisition view:** Includes retargeting revenue |
| Clicks | The number of engagements within a media source redirecting the user to the app store or to a specific page in the app. |
| Impressions | The number of ad views. |
| Re-engagements | Users who have the app installed and then open it after engaging with a retargeting campaign. |
| Re-attributions | Users who reinstall the app after engaging with a retargeting campaign. |
| Total retargeting | Total retargeting = re-attributions + re-engagements. Measures how many previously acquired users opened the app after engaging with a retargeting campaign. |
| Re-attributions revenue | Lifetime revenue generated by re-attributions, attributed to retargeting media sources. |
| Re-engagements revenue | Lifetime revenue generated by re-engaged users during the [re-engagement window](/docs/retargeting-attribution-guide#example-flow-implementing-the-rules). |
| Total touchpoints | Number of clicks and impressions |
| SKAN installs | Number of installs attributed via SKAN |
| SKAN revenue | Total revenue attributed via SKAN conversion values |

### Charts

![Charts Overview](https://files.readme.io/dd7eefef70c1d60483edad6b673731e0efab1dfa0dce67c64e3e3ac771070213-f7ec32eb6ca3785daefa9e1e00e1e093.webp)

Trend over time and performance comparison charts:

| Chart type | Description |
| --- | --- |
| **Trend over time** | **Stacked bar chart**<br />![trend 1](https://files.readme.io/c10e00d582110d00d39b527fbd7d4a9de243ab857d7e35604d9746f1c41750f6-17913634971665.png)<br />**Line chart**<br />![trend 2](https://files.readme.io/8fded5d754c8963dcd8f824b0468a29efcffc73fc39374de1757b095df90759a-17913634973329.png)<br />**Display settings**:<br />(A) Dimension and metric<br />(B) Chart type: Bar or Line, etc.<br />(C) Dimensions in display: Select as required.<br />(D) Number of dimensions: Non-organic and organic, top 5 or Show more. In the case of Show more, the top 10 display separately and the remainder are grouped together.<br />**Considerations**:<br />- When comparing charts to each other, make sure the metrics and dimensions are the same.<br />- This dashboard displays LTV data. In the context of this trend over time chart, if you select an in-app event metric, **each date displays the cohort of users who installed the app on that day**, even if the in-app event being measured occurred on a later day.<br />- For most in-app events metrics, the chart display options are either stacked bar or line. For event conversions, event eCPA, and event ratio, only the line chart display is available. |
| **Performance comparison donuts** | **Set of 3 metric comparison donuts with fixed metrics: Attributions, loyal users, and revenue**<br />![OverviewTopPerformingDonuts_us-en.jpg](https://files.readme.io/8ba3929b772f015c11d284dc1989784914810615664845de1adbbe1bf46939fa-360014852158.jpg)<br />**Display settings**:<br />(A) Dimensions in display: Select dimension |
| **Performance comparison selectable format** | **Comparisons charts with selectable format (bar/donut) and metrics**<br />![Overview2chart_us-en.jpg](https://files.readme.io/8d995f029cb2ac8a50d89e2596c193519b934a4b7a0cae251bad14efef804cb7-360014865518.jpg)<br />**Display settings**<br />(A) Dimensions and metric<br />(B) Chart type: Donut, Horizontal bar<br />(C) Dimensions in display: Select as required |
| **In-app events chart selectable event names** | **In-app events chart with selectable event names**<br />**Display settings**<br />(A) Event name grouping<br />(B) Event filter: Select the events you want to display |

### Tables

![Tables Overview](https://files.readme.io/301574c38c8abe4688cdb6ba87256dc6a0cee88e246bd200bbcf3646d6eac3a2-8fb749493be435e6de395de717dee5e0.webp)

The table contains row-level metrics and event metrics broken down by dimensions.

| Option | Description |
| --- | --- |
| ![OverviewTable.jpg](https://files.readme.io/8e250b030248dd0078ee0228ea28bc85e45c2b34cfbfea13fb71a8c464f4e7ce-360014922677.jpg) | |
| **Ranked attributions principle** | The table consists of the top values, ranked by the number of attributions and the primary group by dimension selected.<br />For example, if the group by dimension is a media source, and the top 25 are selected: the top 25 media sources ranked by attributions are included in the table.<br />This applies to other display options such as the column sort.<br />For example, if you sort a column, it sorts only the media sources already contained in the table. This means that media sources not included in the top list won't be displayed.<br />**Export data**<br />If you export the table, all media sources are included, meaning the ranked attributions principle is disregarded. |
| **Table controls** | (A) Group by:<br />- Select primary and secondary groups by dimensions.<br />- Expand using `>`. Doing so displays the top secondary results of the value expanded.<br />- Select a row to drill down to the next level of the hierarchy.<br />(B) Row-level metrics<br />(C) Event metrics<br />(D) Export: Click **Export,** to download the table to a CSV file. Export downloads all rows; not just the top.<br />(E) Column configuration: Row-level and event metrics<br />(F) Horizontal scroll bar: Scroll right to view event metrics<br />(G) Values having N/A<br />(H) Top selector: Select the top 25 or 50 rows using the ranking principle described previously.<br />**Note:** The number of events that can be added to the table is limited to 20. More information can be found in Traits and limitations |
| **Metric selection** | Metric columns in the table are divided between:<br />- Summary metrics at the row-level<br />- In-app event metrics per in-app event.<br />**To select metrics to display in the table:**<br />- Click ![gears.png](https://files.readme.io/c0141c4463a598d20c9ff0c042821c6e7ccfea3238ea49d3540d01150fec113c-360013047038.png) (configure).<br />The list of metrics displays.<br />![OverviewMetricsSelection.jpg](https://files.readme.io/594665e80e4569cc77bbfa82801cb460ada2eca18c70e223da695053ef26d30a-360014907257.jpg)<br />**Controls:**<br />(A) Include all metrics in the table<br />(B) Remove all metrics from the table<br />(C) Display the metrics glossary<br />(D) Set to default<br />**To add and sequence metrics to the table**<br />- Select metrics to include in the table. Selected metrics display on the right-hand side of the panel.<br />- To remove a metric, click it.<br />- To change the sequence of the metrics in the table drag as required.<br />**To add and sequence in-app event metrics:**<br />1. Select an **In-app event**<br />The list of in-app events displays.<br />2. Select one or more metrics.<br />The metric is added to the list of displayed metrics. |

### Exporting data

#### EXPORT PNG

**To export a PNG of your dashboard**:

* In the Overview dashboard, click the **Menu icon (⋮)** > **Export to PNG**.

#### EXPORT TABLE

**To export the data from the table in your dashboard:**

1. Select the dimensions and metrics to be included. [Learn more](https://support.appsflyer.com/hc/articles/WIP%20MERGE%20this%20draft%20into%20the%20Exporting%20data%20section%20of%20the%20Overview%20dashboard%20KB:%20https://support.appsflyer.com/hc/en-us/articles/20146967587473)
2. Click **Export CSV** at the top-right of the table.

## Dimensions and metrics

### Dimensions

| **Dimension** | **Remarks** |
| --- | --- |
| Ad | |
| Ad ID | |
| Adset | |
| Adset ID | |
| Agency | |
| Apps | |
| Attributed touch type | Click or impression. |
| Attribution type | Installs, re-engagements, or re-attributions.<br />Cost-related metrics are usually not available for this dimension. |
| Campaign | |
| Campaign ID | |
| Channel | Not available for CTV, PC, and console platforms. |
| Engagement type | - Preload<br />- Click-to-download<br />- Click-to-app<br />- Engaged click<br />- Engaged view<br />- View<br />- Listening<br />[Learn more about the various engagement types](https://support.appsflyer.com/hc/articles/21837486015889) |
| Geo | |
| Media source | |
| Source | Organic or non-organic. |
| Event name | The name of the in-app event to show in a chart. |
| Install app store | Populated in the context of multi-store Android attribution. If you don't see the dimension, ask your CSM to enable the SFDC feature for you. |
| Store product page | iOS apps only. |

### Row-level metrics

* When a grouping contains a dimension having both organic and non-organic data, metrics not applicable to organic will reflect as N/A. An example of this is geo.
* Some groups by dimensions can't be fully segmented (broken down) and N/A displays. This occurs due to the granularity and dimensions of the data provided by ad networks.
* Cost-related metrics:
  * Total cost includes the total cost reported by the network for a given metric including the N/A rows.
  * Aren't available in the retargeting view. They are available in the User Acquisition and Unified views.
    * The Unified view, has both User Acquisition and retargeting costs.

#### Metric availability by display method

| **Metric** | **Group** | **Description/formula** | **Table** | **Performance chart** | **Trend over time** |
| --- | --- | --- | --- | --- | --- |
| Attributions | Count | Installs, re-attributions, and re-engagements. | Y | Y | Y |
| Installs | Count | Number of unique users who install the app. | Y | | |
| Re-attributions | Count | Number of unique users who reinstall the app after interacting with a retargeting campaign. | Y | | |
| Re-engagements | Count | Number of unique users who open the app after interacting with a retargeting campaign. | Y | | |
| Impressions | Count | Number of times an ad was viewed. | Y | Y | Y |
| Clicks | Count | Number of engagements within a media source redirecting the user to the app store to install the app, or to open the app on a specific page. | Y | Y | Y |
| Click-throughs | Count | Number of attributions occurring after a user clicks on an ad (CTA). | Y | N | |
| CTR | Count | Click-through rate. Formula: Clicks / Impressions | Y | Y | Y |
| Conversion rate (CVR) | Count | For a given row, CVR is calculated if the row data is valid meaning `clicks > installs`. <br /><br />Formula for CVR: Number of attributions/Number of clicks * 100 <br /><br />**Example CVR calculation**<br />- Media source A: 100 Attributions, NA Clicks -> NA CVR<br />- Media source B: 200 Attributions, 20 Clicks -> NA CVR<br />- Media source C: 300 Attributions, 600 Clicks -> 50% CVR<br />- Media source D: 250 Attributions, 1000 Clicks -> 25% CVR<br /><br />In some cases, to improve accuracy, the CVR calculation is performed in 2 steps. For example, to avoid taking into account organic installs.<br /><br />Example: To view total CVR at the app level we group by a media source, then remove invalid rows, and finally calculate the metric.<br /><br />**Example calculation**<br />Media source A and B are disregarded from the calculation.<br />Formula: (300+250)/(600+1000) = 34.3% | Y | N | Y |
| Loyal users | Count | Number of unique users opening the app a minimum number of times or performing a specific action. The default criterion is 3 app opens. (Relevant to UA view.) | Y | N | |
| Loyal-users rate | Count | Rate (%) of loyal users, as a proportion of the users attributing (meaning installing, re-engaging, or re-attributing).<br />Formula: Loyal Users/Attributions *100 (Relevant to UA view) | Y | N | |
| Cost | Cost | The campaign cost reported to AppsFlyer via click and/or API.<br />- In general, cost data can be segmented in the advertising hierarchy by media source, geo, site ID, and channel. Some segmented data returns N/A if there is no breakdown information available.<br />- Limitation: Can't group by attribution type. | Y | Y | Y |
| Avg eCPI | Cost | Average Effective Cost per Attribution (Install).<br />Formula: Total available cost/Attributions | Y | Y | Y |
| CPM | Cost | Cost per mille (1000 impressions). Formula: (Cost / Impressions) * 1000 | Y | Y | Y |
| CPC | Cost | Cost per click. Formula: Cost / Clicks | Y | Y | Y |
| ARPU | Cost | Average Revenue per User.<br />Formula: Revenue/Unique Users | Y | Y | |
| ROAS | Cost | Return On Ad Spend (%).<br />Formula: Revenue/Cost * 100 | Y | Y | |
| Gross profit | Cost | Profit after deducting campaign cost.<br />Formula: Revenue - Cost | Y | Y | |
| ROI | Cost | Return On Investment (%).<br />Formula: (Revenue - Cost)/Cost * 100 | Y | Y | |
| Revenue | Revenue | Lifetime revenue reported to AppsFlyer. | Y | Y | |
| Sessions | Count | Number of times the app is launched, or other measurement method set by the app developer.<br />Limitation: Sessions aren't available for organic users. | Y | | |
| Uninstalls | Count | - Number of app users installing the app who subsequently uninstall (delete) the app.<br />- Uninstall measurement must be turned on to obtain this metric.<br />- **Note:** Uninstall metrics are available in the user acquisition view only. | UA view only | | |
| Uninstall rate | Count | Rate (%) of users uninstalling the app, as a proportion of the users attributing (meaning installing, re-engaging, or re-attributing).<br />Formula: Uninstalls/Attributions *100 (Relevant to User Acquisition) | UA view only | | |
| View-throughs | Count | Number of attributions occurring after a user views an ad (VTA). | Y | | |
| Assisted installs | Count | Impressions or clicks that contribute to the final install, but aren't the last touch to which the install is attributed. 1 install can have up to 3 assisted installs. [Learn more](https://support.appsflyer.com/hc/articles/207040506) | N | N | Y |

### Event metrics

| **Event metric** | **Description** | Table | Per-formance chart |
| --- | --- | --- | --- |
| Event conversion | Rate (%) of unique users performing the event, as a proportion of the users attributing (meaning installing, re-engaging, or re-attributing).<br />Formula: Unique users performing the event/Attributions *100 | Y | Y |
| (Event) Unique users | Number of unique users (attributions) performing an event. | Y | Y |
| Event occurrences | Number of times an event was performed. | Y | Y |
| Event revenue | Revenue generated by an event. | Y | Y |
| Event eCPA | Effective Cost Per Action (event).<br />Formula: Cost/Unique users performing the event | Y | Y |
| Event ratio | Rate (%) of users performing an event, as a proportion of the users attributing (meaning installing, re-engaging, or re-attributing).<br />Formula: Events/Attributions *100. | Y | Y |

## Additional information

### Traits and limitations

| Trait | Details |
| --- | --- |
| Attribution date range | - For SKAN, the date range is limited to 90 days.<br />- If your computer is set to a timezone where it's a specific day, and the app timezone in AppsFlyer is for a timezone where it's still the previous day, "Today" isn't an option in the date range picker. For example, if, according to your computer settings, it's Monday, but according to your app timezone in AppsFlyer, it's still Sunday. |
| Widgets | - A maximum of 28 widgets (including KPI headline metrics, charts, and tables) can be added to one dashboard.<br />- Maximum 5 tables per dashboard. |
| Ad network access | Yes. However:<br />- SKAN metrics aren't available.<br />- Viewing in-app event data requires advertiser permission. |
| Agency access | Yes. However, SKAN metrics are not available. |
| Agency transparency | Yes |
| App-specific timezone | Supported.<br />**Note**:<br />- For CTV, PC, and console platforms, app-specific timezone support started April 20, 2024. To view data from before, switch the timezone to UTC.<br />- When multiple apps are selected, and they have different app-specific timezones, data displays in UTC. |
| App-specific currency | Supported. Exceptions:<br />- When multiple apps are selected, and they have different app-specific currencies. |
| Campaign name changes | Ad spend data displays using the most recent campaign name reported. **Note:** This is for the display of aggregate data; not the raw data itself. |
| CTV, PC, and console platforms | - CTV, PC, and console platform dimensions are not available for mobile apps.<br />- Same platform-to-same-platform impressions are available. Cross-platform impressions aren't available. They're available in the Cross-platform engagements report via Data Locker. |
| Organic data | Yes |
| Non-organic data | Yes |
| Data freshness | - App attributions and in-app events: [Continuous](https://support.appsflyer.com/hc/articles/360000310629-Data-freshness-and-time-zone-support#continuous-aka-realtime)<br />- Cost: 6 times a day on average 4 times a day. Data is final after the 7th day.<br />- Ad revenue: Lag of ~48 hours |
| Historical data | Overview and LTV metrics support up to 5 years of historical data, and up to 3 years for Date range. |
| In-app events | - The number of events can be added or displayed in the table is limited to 20.<br />- For each event, all metrics (count, ratio, unique users, conversion, revenue, CPA and SKAN event occurrences) can be added and displayed. |
| Uninstall numbers | Uninstall numbers can only be seen in the User Acquisition view. If you are in the Unified view, it will show as N/A. |
| View-through attribution | - User Acquisition view: Available<br />- Unified and Retargeting views: Requires at least one of the following grouping dimensions:<br />- Media source<br />- Campaign<br />- Adset<br />- Ad |
| Multiple apps | - Up to 15 apps can be selected. However, if more than 5 apps are selected, only the following dimensions are available to group by and filter:<br />- Attribution type<br />- Media source<br />- Campaign<br />- Geo<br />- Agency<br />- Channel<br />- Source<br />- SKAN installs, revenue, and event metrics aren't available when multiple apps are selected.<br />- SSOT isn't available when multiple apps are selected |
| Assisted installs | - From August 1, 2024, assisted installs are available in any timezone.<br />- For data July 31, 2024 and earlier, assisted installs are only available when viewing data in UTC timezone. |
| Geo | Aggregation by geo is based on the geo where the install occurred. |