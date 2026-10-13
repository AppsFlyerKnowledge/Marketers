---
title: "Bulletin: Smart Banners support multiple media sources for attribution"
table_of_contents: false
x-zendesk:
  id: 4406100924689
  url: https://support.appsflyer.com/hc/en-us/articles/4406100924689-Bulletin-Smart-Banners-support-multiple-media-sources-for-attribution
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Bulletins
  section_id: 6551161473041
  position: 52
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-asaf-mashiah, Marketers, Smart Banners and Scripts]
  labels: [OneLink, Advertisers, smart banners, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2021-08-24T07:01:05Z'
  edited_at: '2024-01-27T12:04:03Z'
---
| **What's new** | Smart Banner settings allow you to choose multiple media source types for attribution. They are no longer limited to one type of web-to-app URL. |
| --- | --- |
| **Effective date** | August 25, 2021 |
| **Where** | Smart Banners - banner group setup |
| **What** | **Before the change:** One media source type was supported per banner group. Users needed to choose between using incoming attribution link parameters, **OR** incoming links with UTM parameters, **OR** the default attribution parameters (which were also used as a fallback). This meant AppsFlyer looked for either "pid" or “utm\_source” in the incoming URL.<br /><br />**After the change:** Banner groups are not limited to one media source type. They can be configured to support one or more of the above media sources. Meaning, users can choose between incoming attribution link parameters **AND/OR** incoming link UTM parameters **AND/OR** the default attribution parameters. This provides greater flexibility to customize the link behind the banner and provide the best web-to-app experience for the end-user. |
| **What you must know** | * If you have existing Smart Banners and banner groups, your settings remain the same.<br />* For new banner groups, the UI has changed to allow you to choose more than one media source option.<br />* You must have the current [Smart Banners Web SDK](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#smart-banners-only) integrated; this feature is not supported by the old (deprecated) Web SDK.<br /><br />[![](https://files.readme.io/35d3888899ee7d95cb81152ab5a72de5bfcf1df40568b7f2fea00c947658fd42-4406108511633.png)](https://files.readme.io/35d3888899ee7d95cb81152ab5a72de5bfcf1df40568b7f2fea00c947658fd42-4406108511633.png) |