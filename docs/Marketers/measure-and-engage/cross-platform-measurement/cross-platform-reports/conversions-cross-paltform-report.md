---
title: Conversions cross-platform report
excerpt: "The Conversions cross-platform report shows the complete user journey behind each cross-platform conversion, including the full assisting engagement chain and revenue context."
x-zendesk:
  id: 50451304393617
  url: https://support.appsflyer.com/hc/en-us/articles/50451304393617-Conversions-cross-platform-report
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Cross platform reports
  section_id: 50467263168657
  position: 0
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [Marketers, Data Locker, Cross-Platform Measurement]
  labels: []
  promoted: false
  comments_disabled: true
  created_at: '2026-09-02T07:11:54Z'
  edited_at: '2026-09-16T13:31:34Z'
---
## About the report

The Conversions cross-platform report is a raw data report that provides user-level conversion records, linked across platforms using your [Customer User ID (CUID)](https://dev.appsflyer.com/hc/docs/set-customer-user-id). This lets you analyze the complete user journey that led to a conversion, not only the last touchpoint.

For more information about the user-based attribution flow and configuration, see [User-based cross-platform attribution](/docs/beta-user-based-cross-platform-attribution).

## Report fields

To learn which fields are contained in the report, download a [report sample](https://docs.google.com/spreadsheets/d/e/2PACX-1vRTFg6HXtHNYwegAjMysjybPbRk4IO8uflwvbGvR_xb11BcCrCWQ7i3xZD_Y2iiYSsx_MjTPN0E_Bmk/pub?gid=670907846&single=true&output=csv).

The report sample includes all the report fields and their values. For the definitions of the fields, see [the field dictionary](/docs/raw-data-field-dictionary).

The report contains three groups of fields:

- **Cross-platform conversion fields:** media source, campaign, ad, geo, device, CUID, conversion type, revenue, cross-platform conversion timestamp, and related identifiers.
- **Assist fields (1, 2, and 3):** for each of the three assist positions, the corresponding media source, campaign, ad set, ad, agency, channel, engagement type and subtype, site ID, and event time. These fields use the `<field>__assist_1`, `<field>__assist_2`, and `<field>__assist_3` naming convention.
- **Enrichment fields:** support user-level lifetime value (LTV) and event-level analysis. For example, join these fields with a user's conversion records to build a per-user LTV view across platforms.

## Report data freshness

The report runs a batch every 4 hours. Each batch run processes events that entered the database during the previous 4-hour window. For example, the 8:00 AM batch run processes events that entered the database between 3:00 AM and 7:00 AM.

The batch process allocates events to their corresponding hourly versions. For example, events that entered the database between 3:00 and 4:00 AM appear in the 3:00 AM version.

There is typically a short delay between an event's actual occurrence and its entry into the database. The report uses the database entry time to keep hourly grouping accurate and consistent.

### Example: The 8 AM batch run

| Date | Report version | Available at | Includes events happening between | Includes events entering the database between |
| --- | --- | --- | --- | --- |
| 2025-10-01 | 3:00 | 9:00 | 2:00-4:00 | 3:00-4:00 |
| 2025-10-01 | 4:00 | 9:00 | 3:00-5:00 | 4:00-5:00 |
| 2025-10-01 | 5:00 | 9:00 | 4:00-6:00 | 5:00-6:00 |
| 2025-10-01 | 6:00 | 9:00 | 5:00-7:00 | 6:00-7:00 |

> 📘 Good to know
>
> - The batch does not process events from the last hour before the run, to leave enough time to enrich events with their related CUID. In the example above, the 8:00 AM batch processes events that entered the database between 3:00 and 7:00. Events that entered the database between 7:00 and 8:00 are not processed in that run.
> - The report becomes available an hour after the batch run, because an internal process updates the batch during that hour. In the example above, the 8:00 AM batch is available at 9:00 AM.

## Subscribe to the report

To subscribe to the report:

1. In AppsFlyer, from the side menu, select **Export** \> **Data Locker**.
2. In the **Data Locker content** pane, scroll down to the **Advanced reports** section.
3. Select **Conversions cross-platform**.

## Access the report data in your cloud bucket

The path to the report consists of the following folder hierarchy:

```plaintext
<bucket-name>/<DataLocker connection name>/t=conversions_user_level_cross_platform/dt=<yyyy-mm-dd>/h=<hour>/
```

## Business intelligence (BI) developer considerations

Keep the following in mind when connecting your database or dashboard to this report:

- Each report's hourly version contains unique conversion records. Make sure you pull all reports hourly or daily.
- Assist fields (`__assist_1`, `__assist_2`, `__assist_3`) reflect the assisting engagements behind each conversion, based on the underlying conversion data. Use them to reconstruct the touchpoint sequence that led to each conversion.
- The report provides revenue in three currencies: `revenue_usd` (normalized), `revenue_value_original` (the currency of the reporting event, see `revenue_currency_original`), and `revenue_value_customer` (your preferred currency, see `currency_customer`). Use whichever matches your reporting needs.
- This report does not include cost fields (cost, clicks, impressions). Extract them from the [cost ETL report](/docs/set-up-and-use-roi360-cost-etl-reports) instead.
- The report provides all app data in a single file. Use the App ID field to segregate data per app, or set Data Locker to segregate by app. We recommend using the [unified segregation type](/docs/data-locker-for-marketers#app-segregation).