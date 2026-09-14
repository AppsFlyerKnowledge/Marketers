---
title: "Bulletin: Smart Banners support multiple media sources for attribution"
excerpt: "Smart Banner settings now allow you to choose multiple media source types for attribution, providing greater flexibility for web-to-app URLs."
---
| | |
| --- | --- |
| **What's new** | Smart Banner settings allow you to choose multiple media source types for attribution. They are no longer limited to one type of web-to-app URL. |
| **Effective date** | August 25, 2021 |
| **Where** | Smart Banners - banner group setup |
| **What** | **Before the change:** One media source type was supported per banner group. Users needed to choose between using incoming attribution link parameters, **OR** incoming links with UTM parameters, **OR** the default attribution parameters (which were also used as a fallback). This meant AppsFlyer looked for either "pid" or “utm\_source” in the incoming URL.<br>**After the change:** Banner groups are not limited to one media source type. They can be configured to support one or more of the above media sources. Meaning, users can choose between incoming attribution link parameters **AND/OR** incoming link UTM parameters **AND/OR** the default attribution parameters. This provides greater flexibility to customize the link behind the banner and provide the best web-to-app experience for the end-user. |
| **What you must know** | - If you have existing Smart Banners and banner groups, your settings remain the same. <br>- For new banner groups, the UI has changed to allow you to choose more than one media source option.<br>- You must have the current [Smart Banners Web SDK](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#smart-banners-only) integrated; this feature is not supported by the old (deprecated) Web SDK. |