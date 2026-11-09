---
title: X Ads (formerly Twitter Ads) setup guide—overview
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T09:31:36Z'
  edited_at: '2023-11-23T12:16:22Z'
  id: 4410464316049
  locale: en-us
  section: X Ads (formerly Twitter Ads)
  section_id: 6551370375569
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/4410464316049-X-Ads-formerly-Twitter-Ads-setup-guide-overview
---
> **At a glance:** Learn the background of integrating your X Ads account with AppsFlyer.

<Image align="center" alt="X Ads logo.png" src="https://files.readme.io/cecae90650321943ad1cb6d22b7f27d3d28b0484f1706cb1be1a19099dfbb20d-20375448207377.png" width="167px" />

<div id="mobile-app-promotion-on-x-ads" />

## Mobile app promotion on X Ads

X Ads Mobile App Promotion is a method to promote apps on X Ads. It enables advertisers to promote their mobile apps with great App card design driving installs, app engagement, and deep linking. App users can easily install and engage with apps directly from the X Ads timeline.

<div id="x-ads-user-privacy" />

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

<div id="x-ads-and-appsflyer-skan-interoperation" />

## X Ads and AppsFlyer SKAN interoperation

X Ads sends SKAdNetwork postback data via a dedicated API. SKAN data from X Ads will be displayed in the <Anchor target="_blank" href="/marketers/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">SKAN dashboard</Anchor>.

X Ads enriches SKAN postbacks with the following data fields:

* Campaign name
* Campaign ID
* Adset name
* Adset ID

<div data-zendesk-anchors="mobile-app-promotion-on-twitter=mobile-app-promotion-on-x-ads h_01H9QR6TH7M0H5YMXRWVVAYRK9=mobile-app-promotion-on-x-ads twitter-user-privacy=x-ads-user-privacy h_01H9QR6TH74R50K00H7FYN61KC=x-ads-user-privacy twitter-ads-and-appsflyer-skan-interoperation=x-ads-and-appsflyer-skan-interoperation h_01H9QR6TH74PKBGM5RC4M118GE=x-ads-and-appsflyer-skan-interoperation" />
