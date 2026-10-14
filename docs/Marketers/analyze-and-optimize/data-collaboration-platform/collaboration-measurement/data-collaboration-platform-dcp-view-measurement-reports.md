---
title: "Data Collaboration Platform (DCP) - View measurement reports"
excerpt: "Customize your measurement reports by setting report fields, aggregation levels, schedules, and cloud connections."
x-zendesk:
  id: 34060852331153
  url: https://support.appsflyer.com/hc/en-us/articles/34060852331153-Data-Collaboration-Platform-DCP-View-measurement-reports
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Collaboration measurement
  section_id: 38034865098641
  position: 6
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-yael-sharabi, Marketers, Data Clean Room]
  labels: [Marketers]
  promoted: false
  comments_disabled: false
  created_at: '2025-04-03T14:39:29Z'
  edited_at: '2025-04-07T10:16:21Z'
---
Data Collaboration Platform (DCP) measurement reports provide top-level metrics such as clicks, impressions, and ROAS per campaign. They may also include additional metrics and dimensions based on granted access.

Reports are sent directly to your connected cloud storage or data warehouse. You can receive reports in either a predefined format or customize them to include the specific metrics and dimensions you need.

<div id="what-are-dimensions-and-metrics" />

<Accordion title="What are dimensions and metrics?">

The collaboration measurement report is an aggregated report that summarizes data by grouping and combining individual records. It provides high-level insights rather than raw, user-level data.

Report fields are divided into two types: *dimensions* and *metrics*. Each can be further divided into *basic fields* and *calculated fields*.

### Dimensions

A dimension is a grouping category that aggregates event-level data into report records. For example, if the media source is selected as the report dimension, each row will contain aggregated data for all events attributed to that media source. The number of rows equals the number of media sources.

Adding more dimensions increases the grouping granularity. For instance, selecting Event date, Media source, and Campaign results in one row per unique combination of those fields.

### Metrics

A metric is numerical data grouped based on the selected dimensions.

For example, if Revenue is selected as the metric and Media source is the only dimension, the report displays total revenue per media source.

When multiple dimensions are selected, such as Event date, Media source, and Campaign, the revenue is grouped by the combination of those fields.

When selecting a metric, choose its aggregation function. For example, for the revenue metric, you would select the **SUM** function.

### What are basic and calculated fields?

Dimensions and metrics can be either basic fields or calculated fields.

* **Basic fields:** Basic fields contain raw data from sources or in-app events.
* **Calculated fields:** Calculated fields use basic fields to compute values using defined functions.

</Accordion>

## Create a predefined report

To generate a predefined report, follow these steps:

1. In AppsFlyer, from the side menu, go to **Collaborate** > **Data Clean Room**.
2. On the **Data Collaboration Platform** page, select the relevant collaboration.
3. On the collaboration page, click **Create report.**
4. In the dialog that appears, click **Approve report.** The report is sent to your connected cloud service using a predefined name and schedule.

## Create a custom report

To create a custom report, follow these steps:

<div id="1-open-the-new-report-page" />

<Accordion title="1. Open the New report page">

1. In AppsFlyer, from the side menu, go to **Collaborate** > **Data Clean Room**.
2. On the **Data Collaboration Platform** page, select the relevant collaboration.
3. On the measurement dashboard, click ![](https://files.readme.io/ed483d2c2b845f1274b3cf84887ea15e0b0384a5f1cf3a5148b1fb8458cd6ec9-34061156892177.png) **C![]() reate report.**
4. In the dialog that appears click ![](https://files.readme.io/317ded6d0dbe6b0acfee8d3b8c7898dbab1c9b7ae621802fa867f2a6069f5d79-34061156893457.png) **Customize**.
5. On the **New report** page, perform the listed steps.

</Accordion>

<div id="2-set-the-report-type" />

<Accordion title="2. Set the report type">

Under the **Report type** step, select ![](https://files.readme.io/c94890451d831a5a3f1f12b6f42c1c86de1453c175c40cc450e915f6f1f128ad-34061156898449.png)  **Commerce media measurement,** then, click **Next.**

</Accordion>

<div id="3-set-the-report-scope" />

<Accordion title="3. Set the report scope">

Under the **Filters and data sources** step:

1. In the **Report name** box, enter a name for the report.
   * This can be any name that will help you identify the report in the DCR platform.
   * **Important!** Ensure that the report name is different from all other reports in your account or you will not be able to [save the report](/docs/data-clean-room-creating-attribution-data-reports#set-the-report-destination-and-save-the-report).
   * Report name requirements:
     * Length: 2-80 characters
     * Valid characters:
       * letters **(A-Z, a-z)**
       * numbers **(0-9)**, *cannot be the first character of a name*
       * a hyphen **(-)**, *cannot be the first character of a name*
     * Invalid characters:
       * spaces
       * all other symbols or special characters
2. In the **Collaboration name** box, select the relevant collaboration.
3. In the **Timeframe** slider, set the report’s span in days (1-180). Only attributed conversion events occurring within the selected span will appear in the report. The span is calculated backward from the report’s day.
4. Click **Next**.

</Accordion>

<div id="4-set-the-report-dimensions-and-metrics" />

<Accordion title="4. Set the report dimensions and metrics">

If you want to customize the report you can select your report [dimensions and metrics](#what-are-dimensions-and-metrics). For a comprehensive list of the report fields see [the report scheme](#report-scheme) in this article.

To set the report dimensions and metrics, follow these steps:

1. Under the **Structure** step, from the **Dimension from sources** list, select the fields you want to be included in the report.
2. If you want to create a [calculated field](#what-are-basic-and-calculated-fields) click **+ Calculated field** and see [Create calculated field](#create-calculated-field) in this article.
3. You can include the field in the report as a dimension or as a metric.
   * To include the field in the report as a dimension, click **Set as dimension**.
   * To include the field in the report as a metric, click **Set as metric**.
4. If you set the field as a metric, select its aggregation function:
   * **Sum:** The metric value is the sum of event-level values aggregated in the report record. For example, the revenue metric is the sum of  `sku_revenue` all events grouped in the record.
   * **Count:** The metric value is the count of event-level values aggregated in the report record. For example, the conversions metric is the count of all the conversions included in the grouped record.
   * **Count distinct**: The metric value is the number of unique values for a given field across the events grouped in the report record. For example, If the selected metric is count-distinct of `sku` and a grouped record includes 10 events containing 4 different SKUs, the metric value will be **4**.
5. To change the display name of the field, hover over the field and click **Edit display name.**

<Accordion title="">

#### Create calculated field

Calculated fields contain values calculated from basic values using a specified function.

To create or edit a calculated field perform the following:

1. To create or edit a calculated field perform one of the following
   * **Create**: Click **+ Calculated field.**
   * **Edit**: Hover over the calculated field and click the action menu → Edit calculated field.
2. In the **Edit** or **New calculated field** dialog perform the following:
   1. In the **Field** box enter the name of the field.
   2. In the **Set function** list, choose the function used to calculate the new value.
3. Set the function according to the table below:

| **Function** | **Description** | **Example Calculation** | **Example Description** |
| --- | --- | --- | --- |
| `ADD` | Sum of two numbers | `Clicks + Impressions` | Total interactions (clicks + ad impressions). |
| `ARRAY SIZE` | Transforms JSON string array to its size | `ARRAY_SIZE(Products_Clicked)` | Number of products a user clicked in a campaign (from JSON). |
| `CASE WHEN` | Returns a value when the first condition is met, or ELSE | `CASE WHEN Conversions > 0 THEN 'Successful' ELSE 'Failed' END` | Classifies campaign performance based on conversions. |
| `CONCAT` | Concatenation of two strings | `CONCAT(Campaign_Name, ' - ', Region)` | Combines campaign name with the region for reporting. |
| `CONST` | Returns its parameter | `CONST('Marketing Budget Cap: $5000')` | Returns a constant value for budget reference. |
| `DATETIME DIFF` | Period in selected units between `start` and `end` | `DATETIME_DIFF(End_Date, Start_Date, 'day')` | Calculates the campaign duration in days. |
| `MAX` | Maximum of two numbers | `MAX(Click_Through_Rate, Conversion_Rate)` | Finds the higher value between CTR and conversion rate. |
| `MIN` | Minimum of two numbers | `MIN(Budget_Remaining, Daily_Spend_Limit)` | Ensures spending does not exceed daily budget. |
| `MULTIPLY` | Multiplying two numbers | `Conversions * Avg_Order_Value` | Calculates total revenue from conversions. |
| `REGEX EXTRACT` | Extracts the first group by regex | `REGEX_EXTRACT(Ad_Text, 'PromoCode: (\\w+)')` | Extracts promo code from ad text using regex. |
| `SUBSTRING` | Substring of a string from index `start` to `end` | `SUBSTRING(Campaign_ID, 0, 5)` | Extracts the first 5 characters of the campaign ID. |
| `SUBTRACT` | Subtraction of two numbers | `Budget_Allocated - Budget_Spent` | Calculates the remaining budget for the campaign. |

</Accordion>

</Accordion>

<div id="5-manage-dimension-priority" />

<Accordion title="5. Manage dimension priority">

Dimension groups with very few user-level events may conflict with data privacy regulations.

To resolve this, **DCR merges small groups** with larger groups by eliminating the dimensions with the highest specificity.

By default, dimensions are removed in reverse order of their position in the **Report dimensions** list. However, you can adjust the default order and apply a different regrouping priority to preserve the dimensions most important to you. To learn more see a [Regrouping example](/docs/data-clean-room-creating-attribution-data-reports#preserving-privacy-while-grouping-by-dimension-regrouping).

**To change the dimension priority:**

1. Under the **Manage dimension priority** step, click **Manage dimension priority.**
2. Drag the dimension to rearrange the order.
   * The dimension labeled as the **Highest priority** (at the top of the list) means it will be the last to be eliminated if regrouping is required.
3. [Optional] To apply regrouping to custom source dimensions:
   1. Click **Use advanced options to refine regrouping**
   2. Select custom source dimensions to which you'd like to apply regrouping.
   3. The selected dimensions are added to the **Manage dimension priority** list.
      * By default, these dimensions are added to the bottom of the list as the **Lowest priority** for regrouping. However, you can reorder them just like attribution data dimensions, as described above.
4. Click **Next** to save your changes.
   * The **Report dimensions** list on the main screen remains in its original order, but the revised order has been saved. (Click again on the **Manage dimension priority** button to review or edit your selection.)

</Accordion>

<div id="6-set-the-report-schedule-and-destination" />

<Accordion title="6. Set the report schedule and destination">

DCP delivers reports to your selected cloud services using [AppsFlyer Data Locker](/docs/data-locker-for-marketers). Therefore, specifying the report destination involves selecting or creating a Data Locker connection.

**To set the report schedule and destination:**

1. In the **Settings** step, under the **Schedule** section, select the report schedule (daily, weekly, or monthly).
2. Depending on the selected interval, select the hour, day in a week, or month of the report.
3. Under the **Destination** section, select from the list of Data Locker connections available in your AppsFlyer account.
   * If there are no connections defined in your account:
     * A new tab will open in your browser (showing the AppsFlyer Data Locker page)
     * A **New connection** dialog will open. Follow [these instructions](/docs/data-clean-room-working-with-connections#complete-the-connection-1) to create the connection.
   * If you have existing connections but want to use a new one, click **+ New connection in Data Locker**:
     * A new tab will open in your browser (showing the AppsFlyer Data Locker page)
     * A **New connection** dialog will open. Follow [these instructions](/docs/data-clean-room-working-with-connections#complete-the-connection-1) to create the connection.
     * After creating the connection, return to the DCP tab in your browser and select the newly created connection from the list of Data Locker connections.
4. To receive report status notifications via API, turn on **Report status notifications,** and in the API endpoint box, enter your API URL.
5. Click **Save** to save the report.
6. The new report is now displayed in the **Reports** tab.

</Accordion>

## Report scheme

The report is comprised of the following dimensions and metrics categorized as calculated fields and attribution fields:

<div id="calculated-fields" />

<Accordion title="Calculated fields">

| **Field** | **Description** |
| --- | --- |
| `clicks` | Total number of clicks on the ad. |
| `ctr` | Click-through rate (clicks divided by impressions). |
| `event_date` | Date the event occurred. |
| `impressions` | Number of times the ad was displayed. |
| `total_revenue` | Total revenue generated across all events. |
|  |  |

</Accordion>

<div id="attribution-fields" />

<Accordion title="Attribution fields">

| **Field** | **Description** |
| --- | --- |
| `ad_id` | Unique identifier for the ad. |
| `ad_name` | Name of the ad. |
| `ad_type` | Type of ad (e.g., banner, video). |
| `adset_id` | Unique identifier for the ad set. |
| `adset_name` | Name of the ad set. |
| `advertising_id` | User-resettable device ID (e.g., GAID). |
| `android_id` | Permanent Android device ID. |
| `app_id` | Unique identifier for the app. |
| `app_name` | Name of the app. |
| `app_version` | Version of the app. |
| `appsflyer_id` | Unique ID assigned by AppsFlyer. |
| `campaign_id` | Unique identifier for the campaign. |
| `campaign_name` | Name of the campaign. |
| `channel` | Media source channel (e.g., YouTube). |
| `city` | User’s city based on IP location. |
| `country_code` | ISO 3166-1 alpha-2 country code (e.g., US, GB). |
| `cuid` | Unique customer/user identifier. |
| `device_category` | Device type (e.g., phone, tablet). |
| `event_name` | Name of the event (e.g., install, purchase). |
| `event_revenue` | Revenue generated from the event. |
| `idfa` | User-resettable iOS advertising ID. |
| `idfv` | Vendor ID assigned by iOS. |
| `platform` | The platform (iOS, Android, etc.). |
| `region` | User’s region based on IP location. |
| `sku_revenue` | Revenue associated with a specific SKU. |
| `state` | User’s state based on IP location. |

</Accordion>

<div id="scheme-fields" />

<Accordion title="Scheme fields">

| **Field** | **Description** | **Onsite Availability** | **Offsite availability** |
| --- | --- | --- | --- |
| conversions | Number or conversions | TRUE | FALSE |
| Count\_AFID | Total number of unique users | TRUE | TRUE |

</Accordion>

<div data-zendesk-anchors="h_01JQY1FA02JN6VR67HJ5118SFF=what-are-dimensions-and-metrics h_01JR5NBE6NQ22QCFZG9XRVGM45=dimensions h_01JR5NC59TQ45QPWP7JG6BQKXX=metrics h_01JQY33FZ2H59YZVVXBN9J61RE=what-are-basic-and-calculated-fields h_01JQY1FA03AXH588Z5C9HCJHMS=create-a-predefined-report h_01JQY1FA038V0V1PKBF1CC0B5J=create-a-custom-report h_01JQY1FA035K7VWX4BDC796SVT=1-open-the-new-report-page h_01JQY1FA03Z0W8N8PFVGEC3HRM=2-set-the-report-type h_01JQY1FA03CWP0GSJY46CEJRJY=3-set-the-report-scope h_01JQY1FA03WA8NNB4RT1VBK0F5=4-set-the-report-dimensions-and-metrics h_01JQY1FA03PA40NCTZXHWGQ86C=create-calculated-field h_01JQY1FA03TMN4N7V3F83EK4EY=5-manage-dimension-priority h_01JQY1FA03PRSGHSKNTKNV4NH3=6-set-the-report-schedule-and-destination h_01JQY1FA03S41J7TR5HAF6G8PW=report-scheme h_01JQY1FA0494AK29M0R7ZRJ4DT=calculated-fields h_01JQY1FA0486WK4GHV5G3TZ77V=attribution-fields h_01JQY1FA04DTN2C6A541J25RZJ=scheme-fields" />
