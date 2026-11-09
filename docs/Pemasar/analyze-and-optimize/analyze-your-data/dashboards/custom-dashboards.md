---
title: Custom dashboards
metadata:
  keywords:
    - custom dashboard
    - Advertisers
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shani-elkabetz
    - Marketers
    - Marketing Analytics
  created_at: '2016-09-15T11:06:24Z'
  edited_at: '2026-03-18T09:05:20Z'
  id: 212750286
  locale: en-us
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/en-us/articles/212750286-Custom-dashboards
---
> **At a glance:** Build your own customized dashboards inside AppsFlyer. You can easily select, name, and position the data in your own customized reports.

<Image align="center" alt="CustomDashboard_us-en.png" src="https://files.readme.io/6bf2765054a7e7f1e344d15d2ac0c56dbdbd4fe5d0ff285f95bb03066396be0d-360015793598.png" />

## Custom Dashboards

Each custom dashboard consists of one or more widgets containing user acquisition metrics. You configure the widget using the widget wizard to select metrics, presentation format, apps, and so on.

The metrics available are similar to the Overview dashboard user acquisition view metrics. Note! **Don't** compare to Overview unified **nor** retargeting view.

Once a custom dashboard is defined, it's available to all users in the account.

## Dashboard personalization

You can personalize a dashboard by moving and sizing widgets.

| Personalization Option | Description |
| --- | --- |
| Resize widget | Drag the bottom-right corner of a widget to resize it |
| Widget position | Drag and drop a widget to change its location in a dashboard |
| Actions | Hover over a widget in the top-right corner, click actions. The following actions are available per widget:<ul><li>Edit</li><li>Duplicate</li><li>Delete</li><li>Export CSV</li></ul> |

## Procedures

<div id="managing-dashboards" />

<Accordion title="Dashboard actions">

| Action | Description |
| --- | --- |
| Duplicate | Makes a copy of the current dashboard |
| Rename | Change the dashboard name |
| Export PNG | Creates and downloads a PNG file |
| Delete | Remove the dashboard |

</Accordion>

<div id="add-a-custom-dashboard" />

<Accordion title="Add a custom dashboard">

**To add a custom dashboard:**

1. In AppsFlyer, from the side menu, select **Analyze** > **Custom Dashboards**.  
   A dashboard displays.
2. Click + (Add new dashboard).
3. Enter **Your dashboard title**.
4. Click **Add.**
5. Add one or more widgets as described in the section that follows.

</Accordion>

<div id="managing-widgets" />

<Accordion title="Managing widgets">

**To add a widget:**

1. Click Add widget.
2. The widget window displays.

   <Image align="center" alt="WidgetConfigure_us-en.png" src="https://files.readme.io/f04544d8cb8b1d946526c4546565fffb405e5113e09dac65e5a28e218a1170a7-360015793618.png" />
3. Configure the widget. Use the widget settings guide that follows.
4. Add more widgets as required.

**Widget settings guide**

| Setting | Description |
| --- | --- |
| Widget type | ![WidgetType_us-en.png](https://files.readme.io/00174da67c1b5046033655aad2f0af815d5abb3229cdc7c2f225f689c8adc7d8-360015793638.png)<br /><br />Select a widget type:<ul><li>Pie chart</li><li>Bar chart</li><li>Line chart</li><li>Data table</li><li>Geo map</li><li>Metric</li><li>Funnel chart</li></ul> |
| Description | Enter a widget description |
| Apps | Select 1–more or all apps to include in the widget data. Note if you select all it means the top-100 apps in your account. |
| KPIs | <ul><li>Select KPIs to display in the widget</li><li>Data table and bar chart are sorted according to the first KPI selected</li></ul> |
| Group by | Select group by |
| Show top | Enter the number of values to display. |
| Pre-Covid | If selected, show data of a pre-COVID-19 date range of November 1-30, 2019. |
| Filters | Use filters to limit data in the widget:<ul><li>**Countries (geo)**</li><li>**Media sources**</li><li>**Campaigns**</li><li>**Channels**</li></ul>Select **Exclude organic** to explicitly exclude data not attributed to a media source. |

</Accordion>

<div id="export-widget-data" />

<Accordion title="Export widget data">

<Image align="center" alt="Widget_table.png" src="https://files.readme.io/b04e80e16d0d34946e6783103fc6fbbdf89b390842db27226b4fdba6c1f7e506-360015717057.png" />

**To download widget data to a CSV file**:

1. Make sure the widget contains a title and data.
2. Select **Actions** in a widget.
3. Select **Export CSV**.  
   The file downloads.  
   Dates in CSV files have the format dd/mm/yyyy. You can <Anchor target="_blank" href="https://answers.microsoft.com/en-us/msoffice/forum/msoffice_excel-mso_winother-mso_2010/how-to-convert-ddmmyyyy-to-mmddyyyy/41119ed6-4057-4598-a44c-1ebfdf301a43">convert them to a different format</Anchor>, like mm/dd/yyyy in Excel.

</Accordion>

## Traits and limitations

<div id="traits-and-limitations::6693dfa7" />

<Accordion title="Traits and limitations">

| Trait | Remarks |
| --- | --- |
| Ad network access to report | No |
| Agencies | Not supported |
| Agency transparency | Yes |
| App-specific timezone | If all apps housed in the account have the same timezone setting, data displays using the app-specific timezone. If this is not the case: data displays in UTC. |
| App-specific currency | If all apps housed in the account have the same currency setting, data displays in app-specific currency. If this is not the case, data displays in USD. |
| Cost data | Only available if there is at least 1 recorded install. <Anchor target="_blank" href="/marketers/id/docs/roi360-cost-aggregation-overview#cost-data-availability-and-reports">Learn more</Anchor> |
| Organic data | Available |
| Non-organic data | Available |
| eCPA | <ul><li>In Custom dashboards, the eCPA formula is: Total spend / Number of actions = eCPA</li><li>This differs from other dashboards, including Overview, where the formula is: Total spend / **unique users** who performed an action = eCPA</li></ul> |
| Data freshness | <Anchor target="_blank" href="/marketers/id/docs/about-data-freshness-and-timezone-support#continuous-aka-realtime">Real-time</Anchor>. Equivalent to the Overview Dashboard |
| Account user access | Yes |
| Limitations | <ul><li>Full page export to PDF option is not available.</li><li>Export to PNG is not supported in the following browsers: Edge, Firefox 69 (Max).</li><li>Searching for a specific campaign is limited to cases where there are less than 100 campaigns. If necessary, narrow the time period and search again.</li><li>KPI availability: User acquisition LTV KPIs are available. Retargeting, retention, activity, and Protect360 KPIs aren't available. Note! Don't compare Custom dashboard metrics to Overview unified or retargeting view metrics.</li><li>Campaign name changes aren't supported.</li></ul> |
| Timezones | <ul><li>If all apps in the account have the same timezone name, data is displayed using the app timezone. If not, UTC will be used.</li></ul> |
| Historical data | LTV data is available for up to 25 months (2 years + 1 month). |

</Accordion>

<div data-zendesk-anchors="h_01HKW1YXVNE5R4XA2T089WP4SV=custom-dashboards h_01HKW1YXVN36YFAQNHXBDS8Z50=dashboard-personalization h_01HKW1YXVNK44TB98N3S1N0B8N=procedures h_01HKW1YXVNX1J1BFHW2KMS0XEV=managing-dashboards h_01HKW1YXVNRFR7F3G3G870NPP0=add-a-custom-dashboard h_01HKW1YXVNRS55CTY4461NGEM1=managing-widgets h_01HKW1YXVN94CWPFFGWM6SYBAD=export-widget-data h_01HKW1YXVNSNAT7FGWH7BGBKH1=traits-and-limitations h_01HKW1YXVNTWXPZKD79MTPH556=traits-and-limitations::6693dfa7" />
