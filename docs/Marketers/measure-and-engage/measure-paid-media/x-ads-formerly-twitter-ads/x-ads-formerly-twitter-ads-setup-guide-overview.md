---
title: "X Ads (formerly Twitter Ads) setup guide—overview"
excerpt: "Learn the background of integrating your X Ads account with AppsFlyer, including mobile app promotion, user privacy policies, and SKAdNetwork interoperation."
---
<Cards>
  <Card title="Mobile app promotion on X Ads" href="#mobile-app-promotion-on-x-ads" />
  <Card title="X Ads user privacy" href="#x-ads-user-privacy" />
  <Card title="X Ads and AppsFlyer SKAN interoperation" href="#x-ads-and-appsflyer-skan-interoperation" />
</Cards>

**At a glance:** Learn the background of integrating your X Ads account with AppsFlyer.

![X Ads logo.png](https://files.readme.io/cecae90650321943ad1cb6d22b7f27d3d28b0484f1706cb1be1a19099dfbb20d-20375448207377.png)

## Mobile app promotion on X Ads

X Ads Mobile App Promotion is a method to promote apps on X Ads. It enables advertisers to promote their mobile apps with great App card design driving installs, app engagement, and deep linking. App users can easily install and engage with apps directly from the X Ads timeline.

## X Ads user privacy

X Ads users can control how they share information with advertisers:

- If user settings are set to prevent sharing of their engagement information with advertisers, their X Ads-driven installs and in-app events are omitted from raw data but are still attributed to X Ads.
- Aggregate attribution data reflect correctly in AppsFlyer and is not impacted by the X Ads policy.
- As a result, X Ads aggregate and raw data reports don't correlate.

Beginning July 31, 2021, advertisers who are not in the X Ads Advanced Mobile Measurement (AMM) program will stop receiving all X Ads MACT user-level data.

Through the AMM Program, advertisers may receive more complete user-level data after granting X Ads the right to perform an audit to ensure that X Ads data is being used exclusively for measurement purposes. This is consistent with applicable data protection law and common practices throughout the industry.

**To join the AMM program:** Go to ads.twitter.com/help > **Mobile App, Conversion Tracking & Audience Manager,** and select **Advanced Mobile Measurement Program Agreement Form**.

> 📘 Note
>
> User-level data received prior to joining the AMM program, can't be exported.

For more detailed information, contact your X Ads Account Manager.

## X Ads and AppsFlyer SKAN interoperation

X Ads sends SKAdNetwork postback data via a dedicated API. SKAN data from X Ads will be displayed in the [SKAN dashboard](https://support.appsflyer.com/hc/articles/360011307357-SKAdNetwork-SKAN-dashboard-by-AppsFlyer).

X Ads enriches SKAN postbacks with the following data fields:

- Campaign name
- Campaign ID
- Adset name
- Adset ID