---
title: "Overview dashboard—user acquisition and retargeting LTV"
excerpt: "The Overview dashboard gives advertisers a real-time window into the LTV performance of user acquisition and retargeting campaigns."
---
**At a glance:** The Overview dashboard gives advertisers a real-time window into the LTV performance of user acquisition and retargeting campaigns.

## Overview

Use the Overview dashboard to view campaign performance and app health. The dashboard contains user acquisition and retargeting campaign performance data enriched with data points like click, cost, and revenue. Most [metrics](/docs/overview-dashboard-user-acquisition-and-retargeting-ltv#rowlevel-metrics) update continuously in real-time.

![](https://fast.wistia.com/embed/medias/29sf4osshg/swatch)

> 📘 **Note**
>
> #### Tip
>
> * If you don't run retargeting campaigns, use the [UA view](#view-types).
> * If you're familiar with the V1.0 dashboard, you can skip to the [quick-start guide](/docs/overview-dashboard-user-acquisition-and-retargeting-ltv#quickstart-guide) below.
> * Want to understand more about the Overview dashboard? Check out this short, informative [course on the AppsFlyer Learning Portal](https://elevate.appsflyer.com/learn/course/7801/play/18617/the-big-picture-of-your-marketing-data-overview-part-1).


### Terminology

* Attributions—consist of one or more of the following:
  * Install: The installation of an app by a user.
  * Re-attributions: AKA retargeting reinstall.
  * Re-engagements: User engaging with a retargeting campaign.
* Organic: Attribution not attributed to a media source.
* Non-organic: Attribution attributed to a media source.

See the [AppsFlyer Help Glossary](/docs/appsflyer-knowledge-base-glossary) for an in-depth list of all terms.

## Quick-start guide

### Power users

**View types**

The dashboard contains user acquisition and retargeting campaign data. The [View type](/docs/overview-dashboard-user-acquisition-and-retargeting-ltv#view-types) filter is used to filter between **Unified**, **User Acquisition**, and **Retargeting**. The same view types are implemented in the Cohort dashboard—power users are familiar with them.

**Attribution and attribution period**

* An attribution is an install, re-attribution, or re-engagement, based on the view type.
  * **Unified**: Installs, re-attributions, and re-engagements
  * **User acquisition:** Installs
  * **Retargeting:** Re-engagements and re-attributions
* The attribution period (dates) relates to the date a user performed an attribution. For example, in the User Acquisition view, it means the install date. In the Unified view, it means any of the attribution types.   
    
  **Note:** The retargeting view doesn't contain any cost-related metrics. Use the User Acquisition and Unified views to get the cost-related metrics.

**Settings and filters**

You must set a view type and attribution period in the settings and filters panel. The remaining filters are optional. Use the filters for a detailed analysis of your data.

**Widgets**

The dashboard is made up of widgets that include [KPI headline metrics](/docs/overview-dashboard-user-acquisition-and-retargeting-ltv#headline-metrics), [charts](/docs/overview-dashboard-user-acquisition-and-retargeting-ltv#charts), and [tables](/docs/overview-dashboard-user-acquisition-and-retargeting-ltv#table).

**Charts**

* Bar/line over time chart. For example, installs per day.
* Donut/horizontal bar performance comparison. For example, revenue by geo.

In each chart, select a dimension and a metric.

**Tables**

* A [table](/docs/overview-dashboard-user-acquisition-and-retargeting-ltv#table) contains the top 25 or 50 media sources ranked by attributions.
* You can sort a table using the displayed metrics by clicking on the metric. The sort includes ranked media sources only.
* Drill down to view campaign performance at the ad level.
* Group by Source to view organic and non-organic data. Use Source to suppress organic data or to group by organic vs non-organic.
* To select the metrics you want to view in the table, click the settings icon ![gears.png](https://files.readme.io/c0141c4463a598d20c9ff0c042821c6e7ccfea3238ea49d3540d01150fec113c-360013047038.png).
* N/A results: Occur primarily in cost-related metrics. This limitation relates to the granularity of data provided by ad networks. Total values include N/A rows based on the total reported by ad networks.

### For CTV, PC, and console users

The dashboard for CTV, PC, and console apps gives app advertisers LTV insights for non-organic and organic users. Insights are based on subscription, in-app purchases, and ad monetization.

**Settings and filters**

Use the filters for a detailed analysis of your data. [Filters](/docs/overview-dashboard-user-acquisition-and-retargeting-ltv#filter-bar) available include the standard filters.

**Metrics**

All metrics are selectable.

## Dashboard view types and layout

### View types

![](https://fast.wistia.com/embed/medias/31zhcq4hv7/swatch)

Data in the dashboard is presented via view types Unified, User acquisition, and Retargeting as described in the figure that follows.

[![OV.png](https://files.readme.io/6429e4fbc5ba81eefba8635905b89ad43a1966b06fc6dccdd9a2af4bb042ae04-360012858117.png)](https://support.appsflyer.com/hc/article_attachments/360012858117)

These view types contain LTV data as follows:

* **Unified:** display data under the last touch media source bringing the user according to AppsFlyer [double attribution](/docs/resolve-retargeting-double-attribution) rules. Meaning that LTV occurring during re-engagements displays under the retargeting media source and not under the UA media source.
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

To learn how to change default views, see [Dashboard views.](/docs/overview-dashboard-user-acquisition-and-retargeting-ltv#dashboard-views)

The dashboard contains the following functional areas:

A: [Dashboard views](/docs/overview-dashboard-user-acquisition-and-retargeting-ltv#dashboard-views)  
B: [Filter bar](/docs/overview-dashboard-user-acquisition-and-retargeting-ltv#filter-bar)  
C: [KPI headline metrics](/docs/overview-dashboard-user-acquisition-and-retargeting-ltv#headline-metrics)  
D: [Charts](/docs/overview-dashboard-user-acquisition-and-retargeting-ltv#charts)  
E: [Tables](/docs/overview-dashboard-user-acquisition-and-retargeting-ltv#table)

![OverviewV2.png](https://files.readme.io/c513b89b8ae3d041632e73cf8941b3ff7841c925d4db27908970f758b7cdb8b4-4419072259857.png)

## Dashboard features

### Dashboard views

![](https://fast.wistia.com/embed/medias/75tv2r88oc/swatch)

Two predefined layouts, Extended overview, and Lite overview are available. They have the same data and metrics but the number and style of charts they contain differ. Following are some of the layout differences.

#### **My reports layout and comparison**

The images that follow are for illustration purposes. They indicate the number and placement of charts.



| **Layout name**: Lite overview<br /><br />**Charts available:** Two donut/horizontal performance comparison bar charts and one trend over time chart. A compact view highlighting what really matters.<br /><br />![OverviewLayoutLite_us-en.jpg](https://files.readme.io/93fe2c4ea8983d43b93fbfad7bd2ea2a76c22b1a062c2204f817f5c50e78a4fc-360014947378.jpg) |
| --- |
| **Layout name: Extended overview**<br /><br />**Charts available:** Seven donut/horizontal performance comparison charts and three trends over time charts. Providing a deep dive into the metrics.<br /><br />![OverveiwFull_us-en.jpg](https://files.readme.io/1647a10f8dad6014fcbfce88381873a350f3ff3f20c468852b03ab9bfe35b312-360014947398.jpg) |



#### **Dashboard view selector**

**To select a report:**

**![OverviewReportHeader.png](https://files.readme.io/cdd385c00260070734e569b929fbb7f02ad835d09da12c9800d7b43b6bfa1c40-4419080285969.png)**

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

The Overview dashboard can display data in timezone=UTC and currency=USD or in the app-specific timezone and local currency as set on the [app settings page](/docs/app-settings).

**Note**: Localization changes affect only your specific app dashboard; not the dashboard of other account users.

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

Attributions included by [view type](/docs/overview-dashboard-user-acquisition-and-retargeting-ltv#view-types)



| View type | Unified | UA | Retargeting |
| --- | --- | --- | --- |
| Installs | Yes | Yes | - |
| Re-attributions | Yes | - | Yes |
| Re-engagements | Yes | - | Yes |



#### Attribution date range

Dates the attribution occurred.

**Note**: For SKAN, the date range is limited to 90 days.

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
* Geo-related filters available for CTV, PC, and console apps: State, DMA, Ad placement

### Customizing dashboards

#### Saving a dashboard

You can customize your dashboard, select apps, view types, filters, and as described in the sections that follow, widgets, dimensions, and metrics. 

* To save a dashboard, click **Save dashboard** at the top-right of the page.

The report is then saved for your future use. This includes the apps and other filters selected, the widget (KPI, chart and table) selection and placement, and the dimensions and metrics selected. **Note**: The date range isn't saved.

#### Re-arranging the dashboard

The dashboard is made up of widgets that include [KPI headline metrics](/docs/overview-dashboard-user-acquisition-and-retargeting-ltv#headline-metrics), [charts](/docs/overview-dashboard-user-acquisition-and-retargeting-ltv#charts), and [tables](/docs/overview-dashboard-user-acquisition-and-retargeting-ltv#table).

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

* To share a dashboard, click the ![share_icon.png](https://files.readme.io/d2e73ad4a67103eb405a599217e79fe0000939f7e56a92b3c419e523bc013298-14126248130833.png) **Share** icon at the top-right of the page and set the visibility to **Shared**. The dashboard then displays in the "Shared" list of dashboards instead of the "Private" list.
* [Optional ]Copy and share the URL to the dashboard with others. Additionally, your custom dashboard becomes available in the view selector for other users.
* [Optional] Select whether to **Notify all account users about this shared dashboard**.

### KPI headline metrics

KPI headline metrics are provided in the context of the selected view type.

By default, the six most popular KPIs are displayed on the default dashboard view.

Any added KPIs will be added to the bottom of the dashboard and can be moved to anywhere else on the dashboard.

See [Re-arranging the dashboard](/docs/overview-dashboard-user-acquisition-and-retargeting-ltv#rearranging-the-dashboard) for more information.

**Metric component layout**

![HeadlineMetric.png](https://files.readme.io/9a82b47b6eb3619acccce5133cf1eb40f4ed45cb64cece30fea14076f48769f3-4464817083921.png)

A: Metric type  
B: Tooltip  
C: Trend: Change in % compared to the previous adjacent period. Hover over to view the trend period.



| Metric | During the selected period... |
| --- | --- |
| User Acquisition | The number of users installing the app. |
| Retargeting | The number of users engaging with a retargeting campaign who re-attribute or re-engage. |
| Total revenue | Revenue LTV is measured by calculating the total of non-organic installs, organic installs, re-attributions, and re-engagements.<br /><br />Revenue generated by users according to view type:<br /><br />**User acquisition view:**<br /><br />* Revenue is LTV, based on installs in the date range.<br />* Includes retargeting revenue of these users according to [retargeting attribution rules](/docs/resolve-retargeting-double-attribution).<br /><br />**Retargeting**: Revenue generated by users re-attributing and from users re-engaging for the duration of the re-engagement window.<br /><br />**Unified view:**<br /><br />* Based on re-engagements and re-attributions in the date range, according to [retargeting attribution rules.](/docs/resolve-retargeting-double-attribution)<br />  * installs might have happened before the date range. |
| Cost | [Campaign cost](/docs/roi360-cost-aggregation-overview) relating to non-organic installs, re-attributions, and re-engagements. Reported to AppsFlyer by API or by click or impression URLs.<br /><br />**User acquisition view:** Displays cost data of active campaigns (meaning campaigns with at least one install).<br /><br />**Retargeting**: Not available<br /><br />**Unified view:** Displays all cost data of active and inactive campaigns (meaning data from campaigns without any installs). This includes the costs of retargeting campaigns. |
| Non-organic installs | New installs attributed to a non-organic media source, usually following a click or impression engagement. |
| Organic installs | New installs by users who didn't engage with a media source beforehand. |
| Total installs | The total number of new installs, organic and non-organic, during the selected date range. Total installs = non-organic installs + organic installs. |
| eCPI | Formula for eCPI: eCPI = Total available cost / Attributions. Attributions include installs, re-attributions, and re-engagements.<br /><br />To see your eCPI across all sources, select only the sources that share cost data. Campaigns without cost data, but with Installs, impact the accuracy of the eCPI, as installs with zero cost are accounted for. |
| CPC | Cost per click. Formula: Cost / Clicks |
| CPM | Cost per mille (1000 impressions). Formula: (Cost / Impressions) * 1000 |
| CTR | Click-through rate. Formula: Clicks / Impressions |
| Non-organic revenue | Lifetime revenue of users attributed to non-organic installs only. Measured from the install date until today. Revenue from organic users and re-attributed users is not included.  <br />**User acquisition view:** Includes retargeting revenue |
| Organic revenue | Lifetime revenue generated by organic installs, from install date until the present (updates every 15 minutes).<br /><br />**User acquisition view:** Includes retargeting revenue |
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

![](https://fast.wistia.com/embed/medias/b76k41j76b/swatch)

Trend over time and performance comparison charts



| Chart type | Description |
| --- | --- |
| Trend over time | **Stacked bar chart**<br /><br />[![trend 1](https://files.readme.io/c10e00d582110d00d39b527fbd7d4a9de243ab857d7e35604d9746f1c41750f6-17913634971665.png)](https://support.appsflyer.com/hc/article_attachments/17913634971665)<br /><br />**Line chart**<br /><br />[![trend 2](https://files.readme.io/8fded5d754c8963dcd8f824b0468a29efcffc73fc39374de1757b095df90759a-17913634973329.png)](https://support.appsflyer.com/hc/article_attachments/17913634973329)<br /><br />**Display settings**:<br /><br />(A) Dimension and metric   <br />(B) Chart type: Bar or Line, etc.  <br />(C) Dimensions in display: Select as required.   <br />(D) Number of dimensions: Non-organic and organic, top 5 or Show more. In the case of Show more, the top 10 display separately and the remainder are grouped together.<br /><br />**Considerations**:<br /><br />* When comparing charts to each other, make sure the metrics and dimensions are the same.<br />* This dashboard displays LTV data. In the context of this trend over time chart, if you select an in-app event metric, **each date displays the cohort of users who installed the app on that day**, even if the in-app event being measured occurred on a later day.<br />* For most in-app events metrics, the chart display options are either stacked bar or line. For event conversions, event eCPA, and event ratio, only the line chart display is available. |
| Performance comparison donuts | **Set of 3 metric comparison donuts with fixed metrics: Attributions, loyal users, and revenue**<br /><br />![OverviewTopPerformingDonuts_us-en.jpg](https://files.readme.io/8ba3929b772f015c11d284dc1989784914810615664845de1adbbe1bf46939fa-360014852158.jpg)<br /><br />**Display settings**:<br /><br />(A) Dimensions in display: Select dimension |
| Performance comparison selectable format | **Comparisons charts with selectable format (bar/donut) and metrics**<br /><br />![Overview2chart_us-en.jpg](https://files.readme.io/8d995f029cb2ac8a50d89e2596c193519b934a4b7a0cae251bad14efef804cb7-360014865518.jpg)<br /><br />**Display settings**<br /><br />(A) Dimensions and metric  <br />(B) Chart type: Donut, Horizontal bar  <br />(C) Dimensions in display: Select as required |
| In-app events chart selectable event names | **In-app events chart with selectable event names**<br /><br />![](https://support.appsflyer.com/hc/article_attachments/20700520844433)<br /><br />**Display settings**<br /><br />(A) Event name grouping<br /><br />(B) Event filter: Select the events you want to display |



### Tables

![](https://fast.wistia.com/embed/medias/kokhyfoagz/swatch)

The table contains [row-level metrics](/docs/overview-dashboard-user-acquisition-and-retargeting-ltv#rowlevel-metrics) and [event metrics](/docs/overview-dashboard-user-acquisition-and-retargeting-ltv#event-metrics) broken down by [dimensions](/docs/overview-dashboard-user-acquisition-and-retargeting-ltv#dimensions).



<table><thead><tr><th>Option</th><th>Description</th></tr></thead><tbody><tr><td colspan="2"><a href="https://support.appsflyer.com/hc/article_attachments/360014922677"><img alt="OverviewTable.jpg" src="https://files.readme.io/8e250b030248dd0078ee0228ea28bc85e45c2b34cfbfea13fb71a8c464f4e7ce-360014922677.jpg"/> </a></td></tr><tr><td>Ranked attributions principle</td><td><p>The table consists of the top values, ranked by the number of attributions and the primary group by dimension selected.</p><p>For example, if the group by dimension is a media source, and the top 25 are selected: the top 25 media sources ranked by attributions are included in the table.</p><p>This applies to other display options such as the column sort.</p><p>For example, if you sort a column, it sorts only the media sources already contained in the table. This means that media sources not included in the top list won't be displayed. </p><p><strong>Export data</strong></p><p>If you export the table, all media sources are included, meaning the ranked attributions principle is disregarded. </p></td></tr><tr><td>Table controls</td><td><p>(A) Group by:</p><ul><li>Select primary and secondary groups by <a href="/docs/overview-dashboard-user-acquisition-and-retargeting-ltv#dimensions">dimensions</a>.</li><li>Expand using <code>&gt;</code>. Doing so displays the top secondary results of the value expanded.</li><li>Select a row to drill down to the next level of the hierarchy.</li></ul><p>(B) Row-level metrics</p><p>(C) Event metrics</p><p>(D) Export: Click <strong>Export, </strong>to download the table to a CSV file. Export downloads all rows; not just the top.<br/>(E) Column configuration: Row-level and event metrics</p><p>(F) Horizontal scroll bar: Scroll right to view event metrics</p><p>(G) Values having N/A </p><p>(H) Top selector: Select the top 25 or 50 rows using the ranking principle described previously.</p><p><strong>Note:</strong> The number of events that can be added to the table is limited to 20.  More information can be found in <a href="/docs/overview-dashboard-user-acquisition-and-retargeting-ltv#traits-and-limitations">Traits and limitations</a></p></td></tr><tr><td>Metric selection</td><td><p>Metric columns in the table are divided between:</p><ul><li>Summary metrics at the row-level</li><li>In-app event metrics per in-app event.</li></ul><p><strong>To select metrics to display in the table:</strong></p><ul><li>Click <img alt="gears.png" src="https://files.readme.io/c0141c4463a598d20c9ff0c042821c6e7ccfea3238ea49d3540d01150fec113c-360013047038.png"/> (configure).<br/>The list of metrics displays.</li></ul><p><a href="https://support.appsflyer.com/hc/article_attachments/360014907257"><img alt="OverviewMetricsSelection.jpg" src="https://files.readme.io/594665e80e4569cc77bbfa82801cb460ada2eca18c70e223da695053ef26d30a-360014907257.jpg"/></a></p><p><strong>Controls:</strong></p><p>(A) Include all metrics in the table<br/>(B) Remove all metrics from the table<br/>(C) Display the metrics glossary <br/>(D) Set to default</p><p><strong>To add and sequence metrics to the table</strong></p><ul><li>Select metrics to include in the table. Selected metrics display on the right-hand side of the panel.</li><li>To remove a metric, click it.</li><li>To change the sequence of the metrics in the table drag as required.</li></ul><p><strong>To add and sequence in-app event metrics:</strong></p><ol><li>Select an <strong>In-app event</strong><br/>The list of in-app events displays.</li><li>Select one or more metrics.<br/>The metric is added to the list of displayed metrics.</li></ol></td></tr></tbody></table>



### Exporting data

#### EXPORT PNG

**To export a PNG of your dashboard**:

* In the Overview dashboard, click the **Menu icon (⋮)** > **Export to PNG**.

#### EXPORT TABLE

**To export the data from the table in your dashboard:**

1. Select the dimensions and metrics to be included. Learn more
2. Click **Export CSV** at the top-right of the table**.**

## Dimensions and metrics

### Dimensions



| **Dimension** | **Remarks** |
| --- | --- |
| Ad |  |
| Ad ID |  |
| Adset |  |
| Adset ID |  |
| Agency |  |
| Apps |  |
| Attributed touch type | Click or impression. |
| Attribution type | Installs, re-engagements, or re-attributions.<br /><br />Cost-related metrics are usually not available for this dimension. |
| Campaign |  |
| Campaign ID |  |
| Channel | Not available for CTV, PC, and console platforms. |
| Engagement type | * Preload<br />* Click-to-download<br />* Click-to-app<br />* Engaged click<br />* Engaged view<br />* View<br />* Listening<br /><br />[Learn more about the various engagement types](/docs/about-enriched-engagement-types) |
| Geo |  |
| Media source |  |
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



<table><thead><tr><th><strong>Metric</strong></th><th><strong>Group</strong></th><th><strong>Description/formula</strong></th><th><strong>Table</strong></th><th><strong>Performance chart</strong></th><th><strong>Trend over time</strong></th></tr></thead><tbody><tr><td>Attributions</td><td>Count</td><td>Installs, re-attributions, and re-engagements.</td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td>Installs</td><td>Count</td><td>Number of unique users who install the app.</td><td>Y</td><td> </td><td> </td></tr><tr><td>Re-attributions</td><td>Count</td><td>Number of unique users who reinstall the app after interacting with a retargeting campaign.</td><td>Y</td><td> </td><td> </td></tr><tr><td>Re-engagements</td><td>Count</td><td>Number of unique users who open the app after interacting with a retargeting campaign.</td><td>Y</td><td> </td><td> </td></tr><tr><td>Impressions</td><td>Count</td><td>Number of times an ad was viewed.</td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td>Clicks</td><td>Count</td><td>Number of engagements within a media source redirecting the user to the app store to install the app, or to open the app on a specific page.</td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td>Click-throughs</td><td>Count</td><td>Number of attributions occurring after a user clicks on an ad (CTA).</td><td>Y</td><td>N</td><td> </td></tr><tr><td>CTR</td><td>Count</td><td>Click-through rate. Formula: Clicks / Impressions</td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td>Conversion rate (CVR)</td><td>Count</td><td><p>For a given row, CVR is calculated if the row data is valid meaning <code>clicks &gt; installs</code>.</p><p>Formula for CVR: Number of attributions/Number of clicks * 100</p><p><strong>Example CVR calculation</strong></p><figure><table><thead><tr><th>Media source</th><th>Attributions</th><th>Clicks </th><th>CVR</th></tr></thead><tbody><tr><td>A</td><td>100</td><td>NA</td><td>NA</td></tr><tr><td>B</td><td>200</td><td>20</td><td>NA</td></tr><tr><td>C</td><td>300</td><td>600</td><td>50%</td></tr><tr><td>D</td><td>250</td><td>1000</td><td>25%</td></tr></tbody></table></figure><p>In some cases, to improve accuracy, the CVR calculation is performed in 2 steps. For example, to avoid taking into account organic installs.</p><p>Example: To view total CVR at the app level we group by a media source, then remove invalid rows, and finally calculate the metric. </p><p><strong>Example calculation</strong></p><figure><table><thead><tr><th>Media source</th><th>Attributions</th><th>Clicks </th><th>CVR</th></tr></thead><tbody><tr><td><span>A</span></td><td><span>100</span></td><td><span>NA</span></td><td><span>NA</span></td></tr><tr><td><span>B</span></td><td><span>200</span></td><td><span>20</span></td><td><span>NA</span></td></tr><tr><td>C</td><td>300</td><td>600</td><td>50%</td></tr><tr><td>D</td><td>250</td><td>1000</td><td>25%</td></tr></tbody></table></figure><p>Media source A and B are disregarded from the calculation.</p><p>Formula: (300+250)/(600+1000) = 34.3%</p></td><td>Y</td><td>N</td><td>Y</td></tr><tr><td>Loyal users</td><td>Count</td><td>Number of unique users opening the app a minimum number of times or performing a specific action. The default criterion is 3 app opens. (Relevant to UA view.) </td><td>Y</td><td>N</td><td> </td></tr><tr><td>Loyal-users rate</td><td>Count</td><td><p>Rate (%) of loyal users, as a proportion of the users attributing (meaning installing, re-engaging, or re-attributing).</p><p>Formula: Loyal Users/Attributions *100 (Relevant to UA view) </p></td><td>Y</td><td>N</td><td> </td></tr><tr><td>Cost</td><td>Cost</td><td><p>The campaign cost reported to AppsFlyer via click and/or API.</p><ul><li>In general, cost data can be segmented in the advertising hierarchy by media source, geo, site ID, and channel. Some segmented data returns N/A if there is no breakdown information available.</li><li>Limitation: Can't group by attribution type.</li></ul></td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td>Avg eCPI</td><td>Cost</td><td><p>Average Effective Cost per Attribution (Install).</p><p>Formula: Total available cost/Attributions</p></td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td>CPM</td><td>Cost</td><td>Cost per mille (1000 impressions). Formula: (Cost / Impressions) * 1000</td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td>CPC</td><td>Cost</td><td>Cost per click. Formula: Cost / Clicks</td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td>ARPU</td><td>Cost</td><td><p>Average Revenue per User.</p><p>Formula: Revenue/Unique Users</p></td><td>Y</td><td>Y</td><td> </td></tr><tr><td>ROAS</td><td><div><div>Cost</div></div></td><td><div><div>Return On Ad Spend (%).</div><div>Formula: Revenue/Cost * 100</div></div></td><td>Y</td><td>Y</td><td> </td></tr><tr><td>Gross profit</td><td>Cost</td><td><p>Profit after deducting campaign cost.</p><p>Formula: Revenue - Cost</p></td><td>Y</td><td>Y</td><td> </td></tr><tr><td>ROI</td><td>Cost</td><td><p>Return On Investment (%).</p><p>Formula: (Revenue - Cost)/Cost * 100</p></td><td>Y</td><td>Y</td><td> </td></tr><tr><td>Revenue</td><td>Revenue</td><td>Lifetime revenue reported to AppsFlyer.</td><td>Y</td><td>Y</td><td> </td></tr><tr><td>Sessions</td><td>Count</td><td><p>Number of times the app is launched, or other measurement method set by the app developer.</p><p>Limitation: Sessions aren't available for organic users.</p></td><td>Y</td><td> </td><td> </td></tr><tr><td>Uninstalls</td><td>Count</td><td><ul><li>Number of app users installing the app who subsequently uninstall (delete) the app.</li><li>Uninstall measurement must be turned on to obtain this metric.</li><li><strong>Note:</strong> Uninstall metrics are available in the user acquisition view only. </li></ul></td><td>UA view only</td><td> </td><td> </td></tr><tr><td>Uninstall rate</td><td>Count</td><td><p>Rate (%) of users uninstalling the app, as a proportion of the users attributing (meaning installing, re-engaging, or re-attributing).</p><p>Formula: Uninstalls/Attributions *100 (Relevant to User Acquisition)</p></td><td>UA view only </td><td> </td><td> </td></tr><tr><td>View-throughs</td><td>Count</td><td>Number of attributions occurring after a user views an ad (VTA).</td><td>Y</td><td> </td><td> </td></tr><tr><td>Assisted installs</td><td>Count</td><td>Impressions or clicks that contribute to the final install, but aren't the last touch to which the install is attributed. 1 install can have up to 3 assisted installs. <a href="/docs/measure-assisted-installs">Learn more</a></td><td>N</td><td>N</td><td>Y</td></tr></tbody></table>



### Event metrics



| **Layout name**: Lite overview<br /><br />**Charts available:** Two donut/horizontal performance comparison bar charts and one trend over time chart. A compact view highlighting what really matters.<br /><br />![OverviewLayoutLite_us-en.jpg](https://files.readme.io/93fe2c4ea8983d43b93fbfad7bd2ea2a76c22b1a062c2204f817f5c50e78a4fc-360014947378.jpg) |
| --- |
| **Layout name: Extended overview**<br /><br />**Charts available:** Seven donut/horizontal performance comparison charts and three trends over time charts. Providing a deep dive into the metrics.<br /><br />![OverveiwFull_us-en.jpg](https://files.readme.io/1647a10f8dad6014fcbfce88381873a350f3ff3f20c468852b03ab9bfe35b312-360014947398.jpg) |

0

## Additional information

### Traits and limitations



| **Layout name**: Lite overview<br /><br />**Charts available:** Two donut/horizontal performance comparison bar charts and one trend over time chart. A compact view highlighting what really matters.<br /><br />![OverviewLayoutLite_us-en.jpg](https://files.readme.io/93fe2c4ea8983d43b93fbfad7bd2ea2a76c22b1a062c2204f817f5c50e78a4fc-360014947378.jpg) |
| --- |
| **Layout name: Extended overview**<br /><br />**Charts available:** Seven donut/horizontal performance comparison charts and three trends over time charts. Providing a deep dive into the metrics.<br /><br />![OverveiwFull_us-en.jpg](https://files.readme.io/1647a10f8dad6014fcbfce88381873a350f3ff3f20c468852b03ab9bfe35b312-360014947398.jpg) |

1