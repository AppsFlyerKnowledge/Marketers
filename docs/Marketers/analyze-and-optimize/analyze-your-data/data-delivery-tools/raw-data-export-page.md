---
title: "Raw data export page"
excerpt: "Download raw data reports in CSV files. Up to 1M rows per download. Limit reports to the data you need by using filters."
x-zendesk:
  id: 360008613838
  url: https://support.appsflyer.com/hc/en-us/articles/360008613838-Raw-data-export-page
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Data delivery tools
  section_id: 6550995484561
  position: 1
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-rona-einat, Marketers, Agencies, Raw Reports, Ad Networks]
  labels: [ad networks, Advertisers, Agencies, Marketers, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2020-05-11T22:25:33Z'
  edited_at: '2026-08-13T16:49:58Z'
---
The following visual displays the first time you go to the **Raw data export** page; the **My reports** page displays if you have reports ready for download or duplication.

[![RawDataSplash.png](https://files.readme.io/febb6a32a3a7b86c5b396cd77ff9e7968057f57ed20fd991d6dbb4899d5eaf07-41225791757969.png)](https://files.readme.io/febb6a32a3a7b86c5b396cd77ff9e7968057f57ed20fd991d6dbb4899d5eaf07-41225791757969.png)

**My reports**

The **My reports** page lists reports previously generated and ready download, duplication, or both. The reports listed were generated during the previous 90 days; their download period is 7 days. After 7 days, if you still need the report, you must generate it again.

For a description of the raw data reports, see [Raw data reporting overview](/docs/raw-data-reporting-overview)

To generate or download reports, see the procedures section of this article.

[![MyReportsRawDataExport.png](https://files.readme.io/1f82e365a7e6cd802ee899666b800be357ea5e99aa6909e75b1fa39a2e4a164e-41225791760145.png)](https://files.readme.io/1f82e365a7e6cd802ee899666b800be357ea5e99aa6909e75b1fa39a2e4a164e-41225791760145.png)

<Accordion title="Raw data export page features and filter options">

The raw data export page provides reports having the features listed in the following table.

<table><thead><tr><th>Feature</th><th>Remarks</th></tr></thead><tbody><tr><td>Report categories </td><td>Differ according to your subscription plan</td></tr><tr><td>Date range</td><td>Raw data reports are filtered by activity dates (event occurrence). You can also add a filter for install dates. See list of filter options in the table that follows.</td></tr><tr><td>Maximum number of rows</td><td>1M rows</td></tr><tr><td>Rate limitation</td><td>A <a href="./report-generation-quotas-rate-limitations">quota mechanism</a> limits the number of reports that can be generated per day.</td></tr><tr><td>Retention/report window</td><td><p>Install-related reports (installs, install postbacks)<strong> 60 </strong>out of the previous 90 days in a single download. </p><p>In-app event-related reports: 31 out of the previous 90 days in a single download.</p></td></tr><tr><td>Filter options</td><td>The filters listed are available for use. In some cases, depending on the filter, filter options are populated. For example, when filtering by Geo the list of available countries is listed.</td></tr><tr><td>Field selection</td><td><p>The most important fields are pre-selected. You can add/clear select fields in the<strong> Report fields</strong> tab. Some fields may not have relevance to a given report. Nevertheless, you can select the field. We do this so that you can have consistent report formats (columns) </p><p>For example, selecting fraud (Protect360) related fields in the user acquisition in-app events report returns blank columns. These fields are populated only in the context of explicit Protect360 reports. </p></td></tr><tr><td>Report (CSV) field order</td><td><p>Columns in reports are arranged according to the field order setting. The column sequence <a href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRGYcMOgC5yy_82yn3DWd3ucLE5KtuTA72eJfvu5KVB9fFH_mYwzM3KpR_inQOnat-KzgVjuuvXa6_g/pub?output=xlsx">listed in a spreadsheet </a>contains separate tabs for the legacy and default options. </p><figure><table><thead><tr><th>Setting</th><th>Field selection allowed</th><th>Remarks</th></tr></thead><tbody><tr><td>Default</td><td>Yes</td><td><ul><li>Selected fields are ordered according to an AppsFlyer template.</li><li>Going forward, the sequence will be preserved. Future fields will be appended to the right of the existing fields.</li></ul></td></tr><tr><td>Alphabetical (A-Z)</td><td>Yes</td><td>Selected fields are ordered alphabetically (ascending).</td></tr><tr><td>Alphabetical (Z-A)</td><td>Yes</td><td>Selected fields are ordered in reverse order alphabetically (descending).</td></tr><tr><td>Legacy</td><td>No</td><td><ul><li>Fields are ordered according to the sequence of columns in reports prepared using the previous version of the export data page.</li><li>Field selection is fixed and can't be changed.</li><li>There is some variation of the reports per field depending on the actual report</li></ul></td></tr></tbody></table></figure></td></tr></tbody></table>

| Filter | Advertiser | Ad network | Agency |
| --- | --- | --- | --- |
| Media source | Yes | No | Yes |
| Activity date range | Yes | Yes | Yes |
| Install date range | Yes | Yes | Yes |
| Agency | Yes | No | No |
| Geo (territory/country) | Yes | Yes | Yes |
| In-app events (available for in-app event reports) | Yes | No | Yes |

</Accordion>

## Procedures

<Accordion title="Create a default report">

You can create a report with the default settings without customizing its fields or filters.

**To create a default report:**

1. In AppsFlyer, from the side menu, select **Export** > **Raw Data Export**
2. Click + **New report**
3. Hover on the type of report you want to generate and click **Create.**
4. Select **Generate now** from the drop-down menu.
5. On the popup window click **Generate now.** Generation can take up to 10 minutes.
   * During report generation, you can continue working, create additional reports, or navigate to other pages.

**The default report filter settings:**

| Filter | Default setting |
| --- | --- |
| Activity dates | The past 7 days |
| Maximum rows per file | 200,000 |
| Media source | All media sources |
| Agency | All Agencies |
| Geo | All geographical areas |

</Accordion>

<Accordion title="Create a custom report">

You can create a custom report by setting its filters and fields.

**To create a custom report:**

1. In AppsFlyer, from the side menu, select **Export** > **Raw Data Export**
2. Click + **New report**
3. Hover on the type of report you want to generate and click **Create.**
4. Select **Customize** from the drop-down menu.
5. Set the report filters
   * **Activity dates:** Select the Activity date range. You can set the specific date or select from the options such as custom, yesterday, last 7 days, and so on.
   * **Maximum rows per file:** [Optional] Set the maximum number of rows a file can include. Select from 100, 200K, 500K, or 1M rows.
   * **Media source:** [Optional] Only the events that were attributed to the selected media sources will be included in the report. You can add a media source to the list by clicking **Add item**.

     > 📘 **Note**
     >
     > Self-reporting network (SRN) web PIDs, such as `metaweb_int`, `googleds_int`, or `tiktokweb_int`, do not appear automatically in the Media source drop-down list. To filter for web SRN postbacks, click **Add item** and enter the web media source PID manually.

   * **Agency:** [Optional] Only the events that were attributed to the selected agencies will be included in the report. You can add an agency to the list by clicking **Add item**.
   * **Geo:** [Optional] Only the events that were attributed to the selected geographical areas will be included in the report.
   * **Report-type specific filter**: Each report type may have its own filter from which you can select a filtering criteria.
6. [Optional]: Reports are populated automatically with the necessary fields. You can add or remove fields as follows:
   1. Go to the **Report fields**tab.The list of selected fields displays. You can't change the selection of mandatory fields.
   2. Select or clear select fields as required.
   3. [Optional] Set **Report (CSV) field Order**to set the sequence of columns.
   4. [Option] Click **Restore defaults**if needed.
7. Click **Create.**
   * The **My reports** page displays. Initially, the status indicates that the report is generating.
   * Generation can take up to 10 minutes.
   * During report generation, you can continue working, create additional reports, or navigate to other pages.

</Accordion>

<div id="download-report" />

<Accordion title="Download report">

**To download a report**:

1. In AppsFlyer, from the sidebar, open **Export** > **Raw Data Export.**
2. Click ![DownloadIcon.png](https://files.readme.io/6c00f4922fc3a835a856d7fdf527aa32d2f50570710c1527b039f43a7acbba79-41225791763217.png) (download), to download the report. Generated reports are available for download for 7 days.

</Accordion>

<Accordion title="Duplicate and edit report settings">

**To duplicate and edit report settings:**

1. In AppsFlyer, from the sidebar, open **Export** > **Raw Data Export.**
2. Click ![Duplicate.png](https://files.readme.io/f745081f1bf0c4f5861e275a29048fe84e8020f8b3bf4ebe4ad6a8d9254ab4b5-41225784681233.png), to duplicate report settings and then edit the settings.
3. Click **Create.** Generated reports are available for 7 days.   
   * The **My reports** page displays. Initially, the status indicates that the report is generating.
   * Generation can take up to 10 minutes.
   * During report generation, you can continue working, create additional reports, or navigate to other pages.

</Accordion>

## Additional information

<Accordion title="Traits and limitations">

| Trait | Remarks |
| --- | --- |
| Ad network access | Yes |
| Agency access | Yes |
| App-specific time zone | Yes |
| App-specific currency | Yes |
| Limitations | Up to 1M records per download |
| Organic data | Available |
| Non-organic data | Available |
| Data freshness | Report dependent |
| Historical data | Previous 90 days |
| Account user access | Users in [roles with required permissions](/docs/user-management) |
| Email delivery | Not supported |
| Install date range | The install date range must be earlier than the activity date range. |
| Raw data postback reports | Postbacks sent to partners due to events attributed to agencies are not included in the Advertiser's Raw Data Postback reports. |

</Accordion>

<Accordion title="Field sequence templates">

The Report field order setting allows you to specify the sequence of columns in reports and in some cases the fields themselves.

| Setting | Field selection allowed | Remarks |
| --- | --- | --- |
| Default | Yes | <ul><li>Selected fields are ordered according to an AppsFlyer template.</li><li>Going forward, the sequence will be preserved. Future fields will be appended to the right of the existing fields.</li></ul> |
| Alphabetical (A-Z) | Yes | Selected fields are ordered alphabetically. |
| Alphabetical (Z-A) | Yes | Selected fields are ordered in reverse order alphabetically |
| Legacy | No | <ul><li>Fields are ordered according to the sequence of columns in reports prepared using the previous version of the export data page.</li><li>Field selection is fixed and can't be changed.</li><li>There is some variation of the reports per field depending on the actual report.</li></ul> |

This [spreadsheet](https://docs.google.com/spreadsheets/d/e/2PACX-1vRGYcMOgC5yy_82yn3DWd3ucLE5KtuTA72eJfvu5KVB9fFH_mYwzM3KpR_inQOnat-KzgVjuuvXa6_g/pub?output=xlsx) contains both a Default and Legacy sheet. Each contains the relevant field order list.

**To change the field order:**

1. In the Report fields tab, select a **Report field order** option.
2. If necessary change the selected fields by selecting or clear selecting the necessary fields.

</Accordion>
