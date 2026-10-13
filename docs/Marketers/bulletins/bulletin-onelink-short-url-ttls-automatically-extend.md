---
title: "Bulletin: OneLink short URL TTLs automatically extend"
excerpt: "Learn about the automatic extension of default time to live (TTL) for OneLink short URLs created via bulk upload, SDK, and OneLink API upon user clicks."
table_of_contents: false
x-zendesk:
  id: 4667188714001
  url: https://support.appsflyer.com/hc/en-us/articles/4667188714001-Bulletin-OneLink-short-URL-TTLs-automatically-extend
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Bulletins
  section_id: 6551161473041
  position: 48
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-asaf-mashiah, Marketers, Link Management]
  labels: [OneLink, User invite, OneLink API, Developers, Marketers, bulk upload, Loc Published]
  promoted: false
  comments_disabled: true
  created_at: '2022-03-10T11:17:11Z'
  edited_at: '2024-05-14T13:02:59Z'
---
| | |
| --- | --- |
| **What's new** | The default time to live (TTL) for OneLink short URLs created via bulk upload, SDK (user invite), and OneLink API is extended each time the link is clicked:<br />- Bulk upload: 365 days<br />- SDK user invite: 60 days<br />- OneLink API: 31 days |
| **Effective date** | January 14 2024 |
| **Where** | - OneLink bulk upload<br />- User invite links (OneLink URLs created via SDK)<br />- OneLink API |
| **What's changing** | **Before the change**: OneLink short URLs created via bulk upload, SDK (user invite), and OneLink API had a time to live (TTL). After the TTL expired, the links no longer worked as intended, and did not provide attribution data.<br />**After the change**: OneLink short URLs created via bulk upload, SDK (user invite), and OneLink API still have a TTL. However, each time the link is clicked, the TTL is extended:<br />- Bulk upload: 365 days<br />- SDK user invite: 60 days<br />- OneLink API: 31 days |
| **What you must know** | - The change affects new and pre-existing OneLink short URLs with TTLs.<br />- For OneLink API:<br />  - You can change the default TTL by adding the parameter `ttl={value}` and specifying how many days, hours, or minutes. For example `ttl=7d`, `ttl=12h`, or `ttl=10m`.<br />- For OneLink API and bulk upload:<br />  - If you don't want link TTLs to automatically extend, add the parameter `renew_ttl=false` to your links. <br />    <br />    > 📘 Note
    >
    > - The parameter `renew_ttl` doesn't display on the actual URL.
    > - For OneLink API, the value is boolean; either true (default) or false. |