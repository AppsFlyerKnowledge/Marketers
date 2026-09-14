---
title: "Bulletin: OneLink short URL TTLs automatically extend"
excerpt: "Learn about the automatic extension of default time to live (TTL) for OneLink short URLs created via bulk upload, SDK, and OneLink API upon user clicks."
---
| | |
| --- | --- |
| **What's new** | The default time to live (TTL) for OneLink short URLs created via bulk upload, SDK (user invite), and OneLink API is extended each time the link is clicked:<br>- Bulk upload: 365 days<br>- SDK user invite: 60 days<br>- OneLink API: 31 days |
| **Effective date** | January 14 2024 |
| **Where** | - OneLink bulk upload<br>- User invite links (OneLink URLs created via SDK)<br>- OneLink API |
| **What's changing** | **Before the change**: OneLink short URLs created via bulk upload, SDK (user invite), and OneLink API had a time to live (TTL). After the TTL expired, the links no longer worked as intended, and did not provide attribution data.<br>**After the change**: OneLink short URLs created via bulk upload, SDK (user invite), and OneLink API still have a TTL. However, each time the link is clicked, the TTL is extended:<br>- Bulk upload: 365 days<br>- SDK user invite: 60 days<br>- OneLink API: 31 days |
| **What you must know** | - The change affects new and pre-existing OneLink short URLs with TTLs.<br>- For OneLink API:<br>  - You can change the default TTL by adding the parameter `ttl={value}` and specifying how many days, hours, or minutes. For example `ttl=7d`, `ttl=12h`, or `ttl=10m`.<br>- For OneLink API and bulk upload:<br>  - If you don't want link TTLs to automatically extend, add the parameter `renew_ttl=false` to your links. <br>    <br>    > 📘 Note
    >
    > - The parameter `renew_ttl` doesn't display on the actual URL.
    > - For OneLink API, the value is boolean; either true (default) or false. |