---
title: 'Bulletin: Change in Preload referrer attribution parameter'
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2023-11-15T10:47:47Z'
  edited_at: '2023-12-11T10:31:24Z'
  id: 20161765461009
  locale: en-us
  section: Bulletins
  section_id: 6551161473041
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/20161765461009-Bulletin-Change-in-Preload-referrer-attribution-parameter
---
| **What's new** | The preload referrer attribution parameter of new installs and in-app events and sessions attributed to new installs recorded after the effective date will be reported differently.<br /><br />Below are the changes to the preload referrer attribution parameter:<ul><li>**attributed\_touch\_type** will be **download** (instead of preload or click\_to\_download)<ul><li>e**ngagement\_type** will be **preload** (for preload\_rfr match type) or **click\_to\_download** (for af\_referrer match type)</li></ul></li></ul>In-app events and sessions attributed to installs before the effective date will keep the existing behavior:<ul><li>**attributed\_touch\_type** will be **preload** or **click\_to\_download**<ul><li>**engagement\_type** will be **empty**</li></ul></li></ul> |
| --- | --- |
| **Effective date** | January 17, 2024 |
| **What this impacts** | <ul><li>Advertisers and agencies, using [AppsFlyer preload referrer attribution](/docs/set-up-appsflyer-preload-referrer-attribution)</li><li>Where is it changing: raw data reports and dashboards</li></ul> |