---
title: "Bulletin: Change in Preload referrer attribution parameter"
excerpt: "Important update regarding changes to the preload referrer attribution parameter in raw data reports and dashboards starting January 17, 2024."
---
| | |
| --- | --- |
| **What's new** | The preload referrer attribution parameter of new installs and in-app events and sessions attributed to new installs recorded after the effective date will be reported differently. <br />Below are the changes to the preload referrer attribution parameter:<br />- **attributed\_touch\_type** will be **download** (instead of preload or click\_to\_download)<br />- e **ngagement\_type** will be **preload** (for preload\_rfr match type) or **click\_to\_download** (for af\_referrer match type)<br />In-app events and sessions attributed to installs before the effective date will keep the existing behavior:<br />- **attributed\_touch\_type** will be **preload** or **click\_to\_download**<br />- **engagement\_type** will be **empty** |
| **Effective date** | January 17, 2024 |
| **What this impacts** | - Advertisers and agencies, using [AppsFlyer preload referrer attribution](/docs/set-up-appsflyer-preload-referrer-attribution)<br />- Where is it changing: raw data reports and dashboards |