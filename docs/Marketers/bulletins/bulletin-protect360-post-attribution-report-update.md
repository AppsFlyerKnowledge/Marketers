---
title: "Bulletin: Protect360 post-attribution report update"
excerpt: "Protect360 post-attribution reports now display the valid contributor (media source) for hijacked installs and in-app events to assist with reconciliation."
table_of_contents: false
x-zendesk:
  id: 360015900018
  url: https://support.appsflyer.com/hc/en-us/articles/360015900018-Bulletin-Protect360-post-attribution-report-update
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Bulletins
  section_id: 6551161473041
  position: 59
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-roy-yanai, Marketers, Protect360]
  labels: [Pull API, Advertisers, Protect360, Raw Data, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2020-11-25T11:39:55Z'
  edited_at: '2023-10-26T17:09:11Z'
---
| **What's new** | Protect360 post-attribution reports display the valid contributor (media source) for hijacked installs and in-app events. Meaning, the contributor that should have originally received attribution. |
| --- | --- |
| **Effective Date** | November 23, 2020 |
| **Where** | Protect360 post-attribution raw data reports via:<br /><br />* Export data (download) raw data reports<br />* Pull API raw data reports |
| **What** | * Until now, post-attribution reports did not display the valid contributor media source. The **contributor[1-3]** and **organic** fields displayed contributing media sources, but do not let you know which of them warranted attribution.<br />* Starting from November 23, 2020, the **rejected\_reason\_value** field value displays either **contributor[1-3]** or **organic**.<br />  * In Data Locker, this is the **validation\_reason\_value**.<br />* Advertisers can check the **contributor[1-3]** fields to see what the attributed media source should be and use this information for reconciliation.<br />  * If the contributor fields are not displayed in your report, they are available to be added from the **Export data** page. |


> 📘 **See also**
>
> * [Post-attribution reports](/docs/protect360-raw-data-reports#postattribution-reports)
> * [Pull API reports](/docs/protect360-raw-data-reports#pull-api)
> * [Rejected\_reason\_value](/docs/raw-data-field-dictionary#protect360::440536f1)
> * [Contributor[1-3]](/docs/raw-data-field-dictionary#attribution::f1c497c7)
> * What's new in AppsFlyer