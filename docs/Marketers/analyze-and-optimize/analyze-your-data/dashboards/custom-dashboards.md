---
title: "Custom dashboards"
excerpt: "Build your own customized dashboards inside AppsFlyer. You can easily select, name, and position the data in your own customized reports."
x-zendesk:
  id: 212750286
  url: https://support.appsflyer.com/hc/en-us/articles/212750286-Custom-dashboards
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Dashboards
  section_id: 6550925337873
  position: 14
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11085
  content_tags: [pm-shani-elkabetz, Marketers, Marketing Analytics]
  labels: [custom dashboard, Advertisers, Marketers, Localize]
  promoted: false
  comments_disabled: true
  created_at: '2016-09-15T11:06:24Z'
  edited_at: '2026-03-18T09:05:20Z'
---
![CustomDashboard_us-en.png](https://files.readme.io/6bf2765054a7e7f1e344d15d2ac0c56dbdbd4fe5d0ff285f95bb03066396be0d-360015793598.png)

## Custom Dashboards

Each custom dashboard consists of one or more widgets containing user acquisition metrics. You configure the widget using the widget wizard to select metrics, presentation format, apps, and so on.

The metrics available are similar to the Overview dashboard user acquisition view metrics. 

> 🚧 Important
>
> **Don't** compare to Overview unified **nor** retargeting view.

Once a custom dashboard is defined, it's available to all users in the account.

## Dashboard personalization

You can personalize a dashboard by moving and sizing widgets.

| Personalization Option | Description |
| --- | --- |
| Resize widget | Drag the bottom-right corner of a widget to resize it |
| Widget position | Drag and drop a widget to change its location in a dashboard |
| Actions | Hover over a widget in the top-right corner, click actions. The following actions are available per widget:<br />- Edit<br />- Duplicate<br />- Delete <br />- Export CSV |

## Procedures

### Dashboard actions

| Action | Description |
| --- | --- |
| Duplicate | Makes a copy of the current dashboard |
| Rename | Change the dashboard name |
| Export PNG | Creates and downloads a PNG file |
| Delete | Remove the dashboard |

### Add a custom dashboard

**To add a custom dashboard:**

1. In AppsFlyer, from the side menu, select **Analyze** > **Custom Dashboards**.

A dashboard displays.
2. Click **+**(Add new dashboard).
3. Enter **Your dashboard title**.
4. Click **Add.**
5. Add one or more widgets as described in the section that follows.

### Managing widgets

**To add a widget:**

1. Click Add widget.
2. The widget window displays.

![WidgetConfigure_us-en.png](https://files.readme.io/f04544d8cb8b1d946526c4546565fffb405e5113e09dac65e5a28e218a1170a7-360015793618.png)

3. Configure the widget. Use the widget settings guide that follows.
4. Add more widgets as required.

**Widget settings guide**

| Setting | Description |
| --- | --- |
| Widget type | ![WidgetType_us-en.png](https://files.readme.io/00174da67c1b5046033655aad2f0af815d5abb3229cdc7c2f225f689c8adc7d8-360015793638.png)<br />Select a widget type:<br />- Pie chart<br />- Bar chart<br />- Line chart<br />- Data table<br />- Geo map<br />- Metric<br />- Funnel chart |
| Description | Enter a widget description |
| Apps | Select 1–more or all apps to include in the widget data. Note if you select all it means the top-100 apps in your account. |
| KPIs | - Select KPIs to display in the widget<br />- Data table and bar chart are sorted according to the first KPI selected |
| Group by | Select group by |
| Show top | Enter the number of values to display. |
| Pre-Covid | If selected, show data of a pre-COVID-19 date range of November 1-30, 2019. |
| Filters | Use filters to limit data in the widget:<br />- **Countries (geo)**<br />- **Media sources**<br />- **Campaigns**<br />- **Channels**<br />Select **Exclude organic** to explicitly exclude data not attributed to a media source. |

### Export widget data

![Widget_table.png](https://files.readme.io/b04e80e16d0d34946e6783103fc6fbbdf89b390842db27226b4fdba6c1f7e506-360015717057.png)

**To download widget data to a CSV file**:

1. Make sure the widget contains a title and data.
2. Select **Actions** in a widget.
3. Select **Export CSV**.

The file downloads.

Dates in CSV files have the format dd/mm/yyyy. You can [convert them to a different format](https://answers.microsoft.com/en-us/msoffice/forum/msoffice_excel-mso_winother-mso_2010/how-to-convert-ddmmyyyy-to-mmddyyyy/41119ed6-4057-4598-a44c-1ebfdf301a43), like mm/dd/yyyy in Excel.

## Traits and limitations

### Traits and limitations

| Trait | Remarks |
| --- | --- |
| Ad network access to report | No |
| Agencies | Not supported |
| Agency transparency | Yes |
| App-specific timezone | If all apps housed in the account have the same timezone setting, data displays using the app-specific timezone. If this is not the case: data displays in UTC. |
| App-specific currency | If all apps housed in the account have the same currency setting, data displays in app-specific currency. If this is not the case, data displays in USD. |
| Cost data | Only available if there is at least 1 recorded install. [Learn more](/docs/roi360-cost-aggregation-overview#cost-data-availability-and-reports) |
| Organic data | Available |
| Non-organic data | Available |
| eCPA | - In Custom dashboards, the eCPA formula is: Total spend / Number of actions = eCPA<br />- This differs from other dashboards, including Overview, where the formula is: Total spend / **unique users** who performed an action = eCPA |
| Data freshness | [Real-time](/docs/about-data-freshness-and-timezone-support#continuous-aka-realtime). Equivalent to the Overview Dashboard |
| Account user access | Yes |
| Limitations | - Full page export to PDF option is not available.<br />- Export to PNG is not supported in the following browsers: Edge, Firefox 69 (Max).<br />- Searching for a specific campaign is limited to cases where there are less than 100 campaigns. If necessary, narrow the time period and search again. <br />- KPI availability: User acquisition LTV KPIs are available. Retargeting, retention, activity, and Protect360 KPIs aren't available. Note! Don't compare Custom dashboard metrics to Overview unified or retargeting view metrics. <br />- Campaign name changes aren't supported. |
| Timezones | - If all apps in the account have the same timezone name, data is displayed using the app timezone. If not, UTC will be used. |
| Historical data | LTV data is available for up to 25 months (2 years + 1 month). |