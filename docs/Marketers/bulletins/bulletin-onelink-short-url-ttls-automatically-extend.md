---
title: 'Bulletin: OneLink short URL TTLs automatically extend'
metadata:
  keywords:
    - OneLink
    - User invite
    - OneLink API
    - Developers
    - Marketers
    - bulk upload
    - Link Management
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2022-03-10T11:17:11Z'
  edited_at: '2024-05-14T13:02:59Z'
  id: 4667188714001
  locale: en-us
  section: Bulletins
  section_id: 6551161473041
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/4667188714001-Bulletin-OneLink-short-URL-TTLs-automatically-extend
---
| **What's new** | The default time to live (TTL) for OneLink short URLs created via bulk upload, SDK (user invite), and OneLink API is extended each time the link is clicked:<ul><li>Bulk upload: 365 days</li><li>SDK user invite: 60 days</li><li>OneLink API: 31 days</li></ul> |
| --- | --- |
| **Effective date** | January 14 2024 |
| **Where** | <ul><li>OneLink bulk upload</li><li>User invite links (OneLink URLs created via SDK)</li><li>OneLink API</li></ul> |
| **What's changing** | **Before the change**: OneLink short URLs created via bulk upload, SDK (user invite), and OneLink API had a time to live (TTL). After the TTL expired, the links no longer worked as intended, and did not provide attribution data.<br /><br />**After the change**: OneLink short URLs created via bulk upload, SDK (user invite), and OneLink API still have a TTL. However, each time the link is clicked, the TTL is extended:<ul><li>Bulk upload: 365 days</li><li>SDK user invite: 60 days</li><li>OneLink API: 31 days</li></ul> |
| **What you must know** | <ul><li>The change affects new and pre-existing OneLink short URLs with TTLs.</li><li>For OneLink API:<ul><li>You can change the default TTL by adding the parameter `ttl={value}` and specifying how many days, hours, or minutes. For example `ttl=7d`, `ttl=12h`, or `ttl=10m`.</li></ul></li><li>For OneLink API and bulk upload:<ul><li>If you don't want link TTLs to automatically extend, add the parameter `renew_ttl=false` to your links.<br />**Note**:<ul><li>The parameter `renew_ttl` doesn't display on the actual URL.</li><li>For OneLink API, the value is boolean; either true (default) or false.</li></ul></li></ul></li></ul> |