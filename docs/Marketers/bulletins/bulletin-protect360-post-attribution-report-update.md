---
title: 'Bulletin: Protect360 post-attribution report update'
metadata:
  keywords:
    - Pull API
    - Advertisers
    - Protect360
    - Raw Data
    - Marketers
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2020-11-25T11:39:55Z'
  edited_at: '2023-10-26T17:09:11Z'
  id: 360015900018
  locale: en-us
  section: Bulletins
  section_id: 6551161473041
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/360015900018-Bulletin-Protect360-post-attribution-report-update
---
| **What's new** | Protect360 post-attribution reports display the valid contributor (media source) for hijacked installs and in-app events. Meaning, the contributor that should have originally received attribution. |
| --- | --- |
| **Effective Date** | November 23, 2020 |
| **Where** | Protect360 post-attribution raw data reports via:<ul><li>Export data (download) raw data reports</li><li>Pull API raw data reports</li></ul> |
| **What** | <ul><li>Until now, post-attribution reports did not display the valid contributor media source. The **contributor[1-3]** and **organic** fields displayed contributing media sources, but do not let you know which of them warranted attribution.</li><li>Starting from November 23, 2020, the **rejected\_reason\_value** field value displays either **contributor[1-3]** or **organic**.<ul><li>In Data Locker, this is the **validation\_reason\_value**.</li></ul></li><li>Advertisers can check the **contributor[1-3]** fields to see what the attributed media source should be and use this information for reconciliation.<ul><li>If the contributor fields are not displayed in your report, they are available to be added from the **Export data** page.</li></ul></li></ul> |

> 📘 **See also**
>
> * [Post-attribution reports](/docs/protect360-raw-data-reports#postattribution-reports)
> * [Pull API reports](/docs/protect360-raw-data-reports#pull-api)
> * [Rejected\_reason\_value](/docs/raw-data-field-dictionary#protect360::440536f1)
> * [Contributor[1-3]](/docs/raw-data-field-dictionary#attribution::f1c497c7)
> * What's new in AppsFlyer

<div data-zendesk-anchors="h_01HDPEGXJSMW6Q9DXA89AZ20T6=see-also" />
