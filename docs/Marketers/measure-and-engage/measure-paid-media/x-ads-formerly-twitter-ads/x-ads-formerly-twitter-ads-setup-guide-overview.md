---
title: "X Ads (formerly Twitter Ads) setup guide—overview"
excerpt: "Learn the background of integrating your X Ads account with AppsFlyer."
x-zendesk:
  id: 4410464316049
  url: https://support.appsflyer.com/hc/en-us/articles/4410464316049-X-Ads-formerly-Twitter-Ads-setup-guide-overview
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: X Ads (formerly Twitter Ads)
  section_id: 6551370375569
  position: 0
  owner: Dori Frost
  owner_email: dori.frost@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-shay-maoz, Marketers, Mobile Attribution]
  labels: [Advertisers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2021-11-09T09:31:36Z'
  edited_at: '2023-11-23T12:16:22Z'
---
![X Ads logo.png](https://files.readme.io/cecae90650321943ad1cb6d22b7f27d3d28b0484f1706cb1be1a19099dfbb20d-20375448207377.png)

## Mobile app promotion on X Ads

X Ads Mobile App Promotion is a method to promote apps on X Ads. It enables advertisers to promote their mobile apps with great App card design driving installs, app engagement, and deep linking. App users can easily install and engage with apps directly from the X Ads timeline.

## X Ads user privacy

X Ads users can control how they share information with advertisers:

* If user settings are set to prevent sharing of their engagement information with advertisers, their X Ads-driven installs and in-app events are omitted from raw data but are still attributed to X Ads.
* Aggregate attribution data reflect correctly in AppsFlyer and is not impacted by the X Ads policy.
* As a result, X Ads aggregate and raw data reports don't correlate.

Beginning July 31, 2021, advertisers who are not in the X Ads Advanced Mobile Measurement (AMM) program will stop receiving all X Ads MACT user-level data.

Through the AMM Program, advertisers may receive more complete user-level data after granting X Ads the right to perform an audit to ensure that X Ads data is being used exclusively for measurement purposes. This is consistent with applicable data protection law and common practices throughout the industry.  
**To join the AMM program:** Go to ads.twitter.com/help > **Mobile App, Conversion Tracking & Audience Manager,** and select **Advanced Mobile Measurement Program Agreement Form**.

Note that user-level data received prior to joining the AMM program, can't be exported.

For more detailed information, contact your X Ads Account Manager.

## X Ads and AppsFlyer SKAN interoperation

X Ads sends SKAdNetwork postback data via a dedicated API. SKAN data from X Ads will be displayed in the [SKAN dashboard](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer).

X Ads enriches SKAN postbacks with the following data fields:

* Campaign name
* Campaign ID
* Adset name
* Adset ID