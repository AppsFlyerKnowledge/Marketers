---
title: "Bulletin: New fields in ad revenue reports"
table_of_contents: false
x-zendesk:
  id: 26907692192273
  url: https://support.appsflyer.com/hc/en-us/articles/26907692192273-Bulletin-New-fields-in-ad-revenue-reports
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Bulletins
  section_id: 6551161473041
  position: 11
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11085
  content_tags: [pm-michael-talapov, Marketers, ROI360]
  labels: [Marketers, Localize]
  promoted: false
  comments_disabled: false
  created_at: '2024-07-22T13:25:32Z'
  edited_at: '2024-09-24T12:01:56Z'
---
| **What's new?** | Ad revenue reports have new fields. |
| --- | --- |
| **Effective date** | September 19, 2024 |
| **What you should know** | The following table shows which fields are being added to which reports. See the [raw data field dictionary](/docs/raw-data-field-dictionary) for definitions and details of each field.<br /><br />\| Report \| API field names \|<br />\| --- \| --- \|<br />\| [Legacy ad revenue [single version]](/docs/revenue-etl-reports#ad-revenue-single-version-report-device-level) \| * engagement\_type * custom\_data * customer\_user\_id * ad\_revenue\_ad\_type \|<br />\| [Ad revenue [versioned]](/docs/revenue-etl-reports#ad-revenue-single-version-report-device-level) \| * engagement\_type * custom\_data * customer\_user\_id * ad\_revenue\_ad\_type \|<br />\| [Ad revenue [SDK impression level]](/docs/revenue-etl-reports#impression-level-report) \| * engagement\_type * custom\_data * customer\_user\_id * ad\_revenue\_ad\_type * ad\_revenue\_custom\_parameters * app\_version * sdk\_version \| |
| Report | API field names |
| [Legacy ad revenue [single version]](/docs/revenue-etl-reports#ad-revenue-single-version-report-device-level) | * engagement\_type<br />* custom\_data<br />* customer\_user\_id<br />* ad\_revenue\_ad\_type |
| [Ad revenue [versioned]](/docs/revenue-etl-reports#ad-revenue-single-version-report-device-level) | * engagement\_type<br />* custom\_data<br />* customer\_user\_id<br />* ad\_revenue\_ad\_type |
| [Ad revenue [SDK impression level]](/docs/revenue-etl-reports#impression-level-report) | * engagement\_type<br />* custom\_data<br />* customer\_user\_id<br />* ad\_revenue\_ad\_type<br />* ad\_revenue\_custom\_parameters<br />* app\_version<br />* sdk\_version |
| **What you need to do** | * In [AppsFlyer Data Locker settings](/docs/data-locker-for-marketers#set-up-data-locker), select the new fields to be added to your reports.  <br />  **Tip**! If you already receive a field like customer\_user\_id via the default Data Locker settings, in order to populate the fields in ad revenue reports you need to add another new field and save the settings. You can revert the changes after.<br />* Configure your BI systems to ingest and use the new fields. |