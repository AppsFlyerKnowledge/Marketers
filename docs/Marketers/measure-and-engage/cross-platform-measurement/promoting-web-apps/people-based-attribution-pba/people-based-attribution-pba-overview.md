---
title: "People-Based Attribution (PBA)—Overview"
excerpt: "People-Based Attribution (PBA) provides a unified view of customer journeys across channels, platforms, and devices."
x-zendesk:
  id: 360002274017
  url: https://support.appsflyer.com/hc/en-us/articles/360002274017-People-Based-Attribution-PBA-Overview
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  position: 0
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-gil-or, Marketers, Cross-Platform Measurement]
  labels: [People Based Analysis, People Based Attribution, People Based Attribution SDK, Developers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2019-08-19T11:53:56Z'
  edited_at: '2024-02-22T07:54:54Z'
---
![PBANoSilos_us-en.gif](https://files.readme.io/1ac3614eb1b9d4c01bffbe904f1a060d1facd681ff32c274b12f0a15612a2e4a-360009359798.gif)

## PBA principles

* PBA consolidates website and mobile app data to provide a holistic view of campaign performance across a brand’s digital properties. Advertisers use PBA to understand customer journeys in terms of people, instead of devices.
* PBA data—on the PBA dashboards and in raw data reports—is used for marketing analyses and campaign optimization.
* Data consisting of website visits and user events is acquired using [SDKs and/or APIs.](/docs/pba-web-sdk-integration-guide)
* For each visit to the website: the media source responsible for bringing the visit is determined. Any resulting event (conversion) is [attributed](/docs/pba-media-source-attribution-rules) to the media source causing the visit.

### PBA analytics dashboards and raw data

* PBA data is presented via analytics dashboards and reports:
  * Website Attribution
  * Web-Assisted Installs
  * Raw data reports
* Data in the dashboards [filtered and grouped](/docs/using-pba-dashboards) using dimensions like mobile platform, media channel, and media type, This enables you to drill down and dissect the data.

### [Website Attribution](/docs/pba-website-attribution-dashboard)

[![WebsiteAttributionTable_us-en.jpg](https://files.readme.io/327a4830ca20ba9067bb9f7a5e5264908fd918ada9462261befcef2f48fd0fd0-360013135398.jpg)](https://files.readme.io/327a4830ca20ba9067bb9f7a5e5264908fd918ada9462261befcef2f48fd0fd0-360013135398.jpg)

Analyze web traffic sources and marketing campaigns driving user visits and conversions on your website. Uncover performance differences down to the ad level. Supports all AppsFlyer query params in the link without the need to redirect users to AppsFlyer servers.

### [Web-Assisted Installs](/docs/pba-web-assisted-installs)

[![AppsFlyer-Web-to-App_us.en.gif](https://files.readme.io/4a278b57379c999d80fd7f1dfea750049f56c03ed32051f9af92577b2a51742a-360009705058.gif)](https://files.readme.io/4a278b57379c999d80fd7f1dfea750049f56c03ed32051f9af92577b2a51742a-360009705058.gif)

Use Web-Assisted Installs to examine the impact and results of your web marketing efforts on driving mobile app installs.

* Gain insights as to how different media types (paid, owned, earned), media channels (direct, social media, organic search), and media sources interact and contribute to your overall user acquisition efforts.
* Attribute organic installs driven by your web efforts.
* Examine the interaction between the web efforts and non-organic installs.

### [Raw data](/docs/pba-raw-data-reports)

Raw data reports are available via Data Locker. They offer in-depth insights and includes the media source attributed/responsible for bringing the user to the website.

* **Web visits:** visits to the website
* **Web events**: actions performed on the website like subscribe or purchase
* **Web-Assisted Installs** journeys are provided in full.
* BI tools are used to analyze the data for additional insights.
* [Learn more about PBA raw data](/docs/pba-raw-data-reports).

> 📘 **See also**
>
> * [Onboarding guide to PBA](/docs/onboarding-guide-to-people-based-attribution)