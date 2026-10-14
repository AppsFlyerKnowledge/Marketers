---
title: 'Bulletin: New fields in ad revenue reports'
metadata:
  keywords:
    - Marketers
    - ROI360
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2024-07-22T13:25:32Z'
  edited_at: '2024-09-24T12:01:56Z'
  id: 26907692192273
  locale: en-us
  section: Bulletins
  section_id: 6551161473041
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/26907692192273-Bulletin-New-fields-in-ad-revenue-reports
---
| **What's new?** | Ad revenue reports have new fields. |
| --- | --- |
| **Effective date** | September 19, 2024 |
| **What you should know** | The following table shows which fields are being added to which reports. See the [raw data field dictionary](/docs/raw-data-field-dictionary) for definitions and details of each field.<table><thead><tr><th>Report</th><th>API field names</th></tr></thead><tbody><tr><td>[Legacy ad revenue [single version]](/docs/revenue-etl-reports#ad-revenue-single-version-report-device-level)</td><td>\* engagement\_type \* custom\_data \* customer\_user\_id \* ad\_revenue\_ad\_type</td></tr><tr><td>[Ad revenue [versioned]](/docs/revenue-etl-reports#ad-revenue-single-version-report-device-level)</td><td>\* engagement\_type \* custom\_data \* customer\_user\_id \* ad\_revenue\_ad\_type</td></tr><tr><td>[Ad revenue [SDK impression level]](/docs/revenue-etl-reports#impression-level-report)</td><td>\* engagement\_type \* custom\_data \* customer\_user\_id \* ad\_revenue\_ad\_type \* ad\_revenue\_custom\_parameters \* app\_version \* sdk\_version</td></tr></tbody></table> |
| Report | API field names |
| [Legacy ad revenue [single version]](/docs/revenue-etl-reports#ad-revenue-single-version-report-device-level) | <ul><li>engagement\_type</li><li>custom\_data</li><li>customer\_user\_id</li><li>ad\_revenue\_ad\_type</li></ul> |
| [Ad revenue [versioned]](/docs/revenue-etl-reports#ad-revenue-single-version-report-device-level) | <ul><li>engagement\_type</li><li>custom\_data</li><li>customer\_user\_id</li><li>ad\_revenue\_ad\_type</li></ul> |
| [Ad revenue [SDK impression level]](/docs/revenue-etl-reports#impression-level-report) | <ul><li>engagement\_type</li><li>custom\_data</li><li>customer\_user\_id</li><li>ad\_revenue\_ad\_type</li><li>ad\_revenue\_custom\_parameters</li><li>app\_version</li><li>sdk\_version</li></ul> |
| **What you need to do** | <ul><li>In [AppsFlyer Data Locker settings](/docs/data-locker-for-marketers#set-up-data-locker), select the new fields to be added to your reports.<br />**Tip**! If you already receive a field like customer\_user\_id via the default Data Locker settings, in order to populate the fields in ad revenue reports you need to add another new field and save the settings. You can revert the changes after.</li><li>Configure your BI systems to ingest and use the new fields.</li></ul> |