---
title: End-user events cross-platform report in Data Locker
metadata:
  keywords:
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Cross-Platform Measurement
  created_at: '2025-10-07T10:37:56Z'
  edited_at: '2026-09-03T09:06:58Z'
  id: 39748676204817
  locale: en-us
  section: Cross platform reports
  section_id: 50467263168657
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/39748676204817-End-user-events-cross-platform-report-in-Data-Locker
---
> **At a glance:** The Cross-platform end-user events report measures complete user journeys, conversions, and LTV across platforms and devices

The Cross-platform end-user events report is a raw data report that provides event-level logs of sessions and in-app events for each user, linked across platforms using your Customer User ID (CUID). Each event includes the cross-platform attribution result, enabling you to analyze complete user journeys.

For more information about the user-based attribution flow and configuration, see <Anchor target="_blank" href="/marketers/fr/docs/beta-user-based-cross-platform-attribution">User-based cross-platform attribution</Anchor>.

## Report fields

To learn which fields are contained in the report, [download a report sample](https://docs.google.com/spreadsheets/d/e/2PACX-1vRhOl-tyaJvgPd9rxGkGMNrgzHPpr7ZsMMnONOHkzdObor158gJPt7XwCBkreM4ka4OkGIyDmqCp_hh/pub?output=csv).

The report sample includes all the report fields and their values. For the definitions of the fields, see <Anchor target="_blank" href="/marketers/fr/docs/raw-data-field-dictionary">the field dictionary</Anchor>.

## Report data freshness

* The report runs a batch every 4 hours.
* Each batch run processes events that entered the database during the previous 4-hour window.
  * Example: The 8:00 AM batch run processes events that were entered into the database between 3:00 AM and 7:00 AM.

* Events are allocated to their corresponding hourly buckets.
  * Example: Events that entered the database between 3:00 and 4:00 AM will appear in the 3:00 AM bucket.

> 🚧 **Important!**
>
> There is typically a short delay between an event's actual happening and its entry into the database. The report uses the database entry time to ensure accurate and consistent hourly grouping.

### Example of the 8:00 AM batch run

| Date | Report version | Report available at | The report includes events happening between | The report include events that entered the database between |
| --- | --- | --- | --- | --- |
| 2025-10-01 | 3:00 | 9:00 | 2:00-4:00 | 3:00-4:00 |
| 2025-10-01 | 4:00 | 9:00 | 3:00-5:00 | 4:00-5:00 |
| 2025-10-01 | 5:00 | 9:00 | 4:00-6:00 | 5:00-6:00 |
| 2025-10-01 | 6:00 | 9:00 | 5:00-7:00 | 6:00-7:00 |

Notes for the above example:

* Events of the last hour before the run are not processed to allow enough time to enrich events with their related CUID. In the above example, the 8:00 AM batch process events that entered the database between 3:00 and 7:00. Events that entered the database between 7:00 and 8:00 are not processed.
* The report is only available an hour after the batch run because an internal process updates the batch during that hour. In the above example, the 8:00 AM batch is available at 9:00 AM.

## How to subscribe to the report?

1. In AppsFlyer, from the side menu, select **Export** > **Data Locker**.
2. In the **Data Locker content** pane, scroll down to the **Advanced reports** section.
3. Select **End-user events cross-platform.**

## How to access the report data in your cloud bucket?

The path to the report consists of the following folder hierarchy:

```
<bucket-name>/<DataLocker connection name>/t=end_user_events_user_level_cross_platform/dt=<dt=yyyy-mm-dd>/h=<hour>/
```

### DL Report folder hierarchy

[![](https://files.readme.io/c10bd982197388cbe412d491829ae896bffbcb13921f008ba1508dc46b173032-39751330744209.png)](https://files.readme.io/c10bd982197388cbe412d491829ae896bffbcb13921f008ba1508dc46b173032-39751330744209.png)

## BI Developer considerations

* Each report hourly bucket contains unique end-user events. Make sure you pull all reports on an hourly or daily basis.
* Ad revenue events are not included yet.
* All app data is provided in a single file. Use the App ID field to segregate data per app, or set Data Locker to segregate by app. It is recommended to use the unified segregation type.
* Pre-attribution data such as cost, clicks, and impressions, should be extracted from the cost ETL report.

### Query examples

The following are examples of some popular, practical applications of the data that BI developers can extract via Data Locker. Each example is illustrated by an SQL statement

<div id="calculating-total-user-acquisitions" />

<Accordion title="Calculating total User Acquisitions">

Count the number of new unique users per media source and campaign.

```sql
SELECT DATE (event_time__conversion) AS install_date
	,CASE 
		WHEN media_source IS NULL
			OR media_source = ''
			OR media_source = 'null'
			THEN 'organic'
		ELSE media_source
		END AS media_source
	,campaign_name
	,count(DISTINCT customer_user_id) AS user_acquisition
	,
FROM end_user_events_user_level_cross_platform
WHERE product_line_name = 'YOUR_PRODUCT_LINE_NAME'
GROUP BY install_date
	,media_source
	,campaign_name
```

</Accordion>

<div id="calculating-total-platform-activations" />

<Accordion title="Calculating total platform activations">

Sum the number of total new platforms, groups, media sources, and campaigns brought per user.

```sql
SELECT DATE (event_time__conversion) AS install_date
	,CASE 
		WHEN media_source IS NULL
			OR media_source = ''
			OR media_source = 'null'
			THEN 'organic'
		ELSE media_source
		END AS media_source
	,campaign_name
	,count(DISTINCT CASE 
			WHEN platform_group = 'PC'
				THEN customer_user_id
			ELSE NULL
			END) + count(DISTINCT CASE 
			WHEN platform_group = 'CONSOLE'
				THEN customer_user_id
			ELSE NULL
			END) + count(DISTINCT CASE 
			WHEN platform_group = 'CTV'
				THEN customer_user_id
			ELSE NULL
			END) + count(DISTINCT CASE 
			WHEN platform_group = 'MOBILE'
				THEN customer_user_id
			ELSE NULL
			END) + count(DISTINCT CASE 
			WHEN platform_group = 'Web'
				THEN customer_user_id
			ELSE NULL
			END) + count(DISTINCT CASE 
			WHEN platform_group = 'Other'
				THEN customer_user_id
			ELSE NULL
			END) AS total_activations
FROM end_user_events_user_level_cross_platform
WHERE product_line_name = 'YOUR_PRODUCT_LINE_NAME'
GROUP BY install_date
	,media_source
	,campaign_name
```

</Accordion>

<div id="calculating-total-revenue" />

<Accordion title="Calculating total revenue">

Sum the total revenue per media source and campaign.

```sql
SELECT DATE (event_time__conversion) AS install_date
	,CASE 
		WHEN media_source IS NULL
			OR media_source = ''
			OR media_source = 'null'
			THEN 'organic'
		ELSE media_source
		END AS media_source
	,campaign_name
	,SUM(revenue_value_customer) AS total_revenue
FROM end_user_events_user_level_cross_platform
WHERE product_line_name = ’YOUR_PRODUCT_LINE_NAME’
GROUP BY install_date
	,media_source
	,campaign_name;
```

</Accordion>

<div data-zendesk-anchors="the-report-fields=report-fields h_01K6Z40KG9H1AC81H77XXEGK1B=report-fields h_01K6Z40KG9PTRAFGXB3XJH5TJ7=report-data-freshness h_01K6Z40KG9QPSMXT13N50TE7KE=important h_01K6Z40KG9JTHGJG7YJNH9TTDT=example-of-the-800-am-batch-run h_01K6Z40KG9J1XWV99Z9M7AG0BY=how-to-subscribe-to-the-report how-to-access-the-report-in-your-bucket=how-to-access-the-report-data-in-your-cloud-bucket h_01K6Z40KG9CDQ43ASM5T80AK65=how-to-access-the-report-data-in-your-cloud-bucket h_01K6Z40KG9NSVWTRSHR71Q7PM6=dl-report-folder-hierarchy h_01K6Z7QHDT4Q2D4JFGC28W8MND=bi-developer-considerations h_01K6Z40KG9E2F30Q9P5GFA9TWT=query-examples h_01K6Z40KG9Y4MWKY6HX8A5NPXA=calculating-total-user-acquisitions h_01K6Z40KG9J9VKC3JH6XNNDA52=calculating-total-platform-activations h_01K6Z40KG9SE8068HG75H59E8Q=calculating-total-revenue" />
