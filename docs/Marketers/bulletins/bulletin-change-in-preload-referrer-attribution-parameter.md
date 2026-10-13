---
title: "Bulletin: Change in Preload referrer attribution parameter"
table_of_contents: false
x-zendesk:
  id: 20161765461009
  url: https://support.appsflyer.com/hc/en-us/articles/20161765461009-Bulletin-Change-in-Preload-referrer-attribution-parameter
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Bulletins
  section_id: 6551161473041
  position: 29
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-alina-koifman, Marketers, Mobile Attribution]
  labels: [Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2023-11-15T10:47:47Z'
  edited_at: '2023-12-11T10:31:24Z'
---
| | |
| --- | --- |
| **What's new** | The preload referrer attribution parameter of new installs and in-app events and sessions attributed to new installs recorded after the effective date will be reported differently. <br />Below are the changes to the preload referrer attribution parameter:<br />- **attributed\_touch\_type** will be **download** (instead of preload or click\_to\_download)<br />- e **ngagement\_type** will be **preload** (for preload\_rfr match type) or **click\_to\_download** (for af\_referrer match type)<br />In-app events and sessions attributed to installs before the effective date will keep the existing behavior:<br />- **attributed\_touch\_type** will be **preload** or **click\_to\_download**<br />- **engagement\_type** will be **empty** |
| **Effective date** | January 17, 2024 |
| **What this impacts** | - Advertisers and agencies, using [AppsFlyer preload referrer attribution](/docs/set-up-appsflyer-preload-referrer-attribution)<br />- Where is it changing: raw data reports and dashboards |