---
title: "Bulletin: New fields in ad revenue reports"
excerpt: "Learn about the new fields added to AppsFlyer ad revenue reports starting September 19, 2024, and how to configure your Data Locker settings to ingest them."
---
| **What's new?** | Ad revenue reports have new fields. |
| **Effective date** | September 19, 2024 |
| **What you should know** | The following table shows which fields are being added to which reports. See the [raw data field dictionary](https://support.appsflyer.com/hc/articles/208387843) for definitions and details of each field. |

| Report | API field names |
| --- | --- |
| [Legacy ad revenue [single version]](https://support.appsflyer.com/hc/articles/16464765619985#ad-revenue-single-version-report-device-level) | - engagement\_type<br>- custom\_data<br>- customer\_user\_id<br>- ad\_revenue\_ad\_type |
| [Ad revenue [versioned]](https://support.appsflyer.com/hc/articles/16464765619985#ad-revenue-single-version-report-device-level) | - engagement\_type<br>- custom\_data<br>- customer\_user\_id<br>- ad\_revenue\_ad\_type |
| [Ad revenue [SDK impression level]](https://support.appsflyer.com/hc/articles/16464765619985#impression-level-report) | - engagement\_type<br>- custom\_data<br>- customer\_user\_id<br>- ad\_revenue\_ad\_type<br>- ad\_revenue\_custom\_parameters<br>- app\_version<br>- sdk\_version |

| **What you need to do** | - In [AppsFlyer Data Locker settings](/docs/data-locker-for-marketers#set-up-data-locker), select the new fields to be added to your reports.<br>  <br>  **Tip**! If you already receive a field like customer\_user\_id via the default Data Locker settings, in order to populate the fields in ad revenue reports you need to add another new field and save the settings. You can revert the changes after.<br>- Configure your BI systems to ingest and use the new fields. |