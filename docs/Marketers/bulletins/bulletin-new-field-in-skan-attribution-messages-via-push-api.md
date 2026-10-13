---
title: "Bulletin: New field in SKAN attribution messages via Push API"
excerpt: "AppsFlyer has introduced new fields, including the af_attribution flag, measurement_window, and interval, to SKAN attribution messages via the Push API."
table_of_contents: false
x-zendesk:
  id: 5203225179153
  url: https://support.appsflyer.com/hc/en-us/articles/5203225179153-Bulletin-New-field-in-SKAN-attribution-messages-via-Push-API
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Bulletins
  section_id: 6551161473041
  position: 51
  owner: Elliot Lachman
  owner_email: elliot.lachman@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-gil-or, Marketers, SKAdNetwork (SKAN)]
  labels: [Developers, SKAD, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2022-04-03T09:15:05Z'
  edited_at: '2023-11-26T12:49:36Z'
---
| | |
| --- | --- |
| **Bulletin date** | April 3, 2022 |
| **What's new**<br />**![Information_icon.png](https://files.readme.io/620ca798aec80f80ef2c05e25c4eefc25ec289d29ad752534dc42a5dd7f0b6cf-20445076224657.png)** | New fields available in [SKAN attribution messages](/docs/push-api-streaming-raw-data#skan-attribution-messages) via Push API:<br />- **af\_attribution flag:** When the Single Source of Truth (SSOT) mechanism is on: If **true**, the install was attributed by both AppsFlyer and SKAN. If **false**, the install wasn't attributed by AppsFlyer. If **null**, the Conversion Value is null.<br />- **measurement\_window**<br />- **interval**<br />See [all fields available](/docs/skan-raw-data-reports#fields-available-in-decoded-event-reports) in decoded event reports. |