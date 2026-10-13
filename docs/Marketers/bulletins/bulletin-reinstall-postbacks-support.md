---
title: "Bulletin: Reinstall postbacks support"
excerpt: "AppsFlyer now supports postbacks on app re-installs, allowing you to distinguish them from first-time installs for improved measurement and optimization."
table_of_contents: false
x-zendesk:
  id: 37325372238481
  url: https://support.appsflyer.com/hc/en-us/articles/37325372238481-Bulletin-Reinstall-postbacks-support
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Bulletins
  section_id: 6551161473041
  position: 0
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-ravid-naori, Marketers, Mobile Attribution]
  labels: [Marketers]
  promoted: false
  comments_disabled: false
  created_at: '2025-07-20T08:37:33Z'
  edited_at: '2026-06-28T16:13:43Z'
---
| Section | Details |
| --- | --- |
| **What's new** | Support for **postbacks on app re-installs** is now available. These are now distinguishable from first-time installs. |
| **Effective date** | 01/09/2025 |
| **What you need to know** | Install postbacks now also control reinstall postbacks. Configure them in the **Active Integration** page.<br />- **Supported networks:** Currently available with select partners (for example, Unity Ads). Additional partners will be added soon.<br />  <br />- **Location:** The install postback appears in the **Default Postbacks** section of the **Attribution** tab. For supported networks, it now also controls reinstall postbacks.<br />  <br />- **Configuration:** You can change the  **For users from** dropdown from **This partner only** to **All media sources (including organic)**.<br />  <br />- **Format:** Reinstall events use the same postback format as install events, with the macro `is_reinstall=true` appended.<br />  <br />- **Value:** This enables improved measurement and optimization, particularly for retargeting-focused partners. |
| **What you need to do** | This feature is available only to designated partners. If you are interested in accessing it, contact your PDM. |