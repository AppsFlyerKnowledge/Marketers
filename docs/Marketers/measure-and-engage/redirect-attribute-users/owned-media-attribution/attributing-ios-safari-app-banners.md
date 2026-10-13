---
title: "Attributing iOS Safari App Banners"
x-zendesk:
  id: 115000171743
  url: https://support.appsflyer.com/hc/en-us/articles/115000171743-Attributing-iOS-Safari-App-Banners
  locale: en-us
  category: Marketers
  category_id: 6550444307985
  section: Owned media attribution
  section_id: 6551214397585
  position: 5
  owner: Ilana Wolf
  owner_email: ilana.wolf@appsflyer.com
  visibility: Everyone / Public (no restriction)
  user_segment_id: null
  permission_group_id: 11065
  content_tags: [pm-asaf-mashiah, Marketers, Smart Banners and Scripts]
  labels: [iOS Safari, Smart App Banner, Advertisers, Marketers]
  promoted: false
  comments_disabled: true
  created_at: '2017-01-02T15:08:07Z'
  edited_at: '2023-07-24T11:58:04Z'
---
At a glance: Safari implements an [App Banner](http://developer.apple.com/library/ios/#documentation/AppleApplications/Reference/SafariWebContent/PromotingAppswithAppBanners/PromotingAppswithAppBanners.html) feature providing a standardized way to promote apps in the Apple App Store. **This is not related to the recommended AppsFlyer [Smart Banner](/docs/smart-banners-mobile-web-to-app-for-marketers) solution.**

> 👍 Recommended alternative
>
> We recommend using AppsFlyer Smart Banners to convert website visitors to app users.
>
> AppsFlyer Smart Banners:
> - Supports all browsers
> - Are customizable
> - Works on all Android and iOS devices

## iOS App Banner

Using iOS 6.0 and later, you can implement App Banners in Safari to promote apps available in the App Store.

**Example banner in Safari**

![AppleBanner_en-us.jpg](https://files.readme.io/dde65134ca3450b407c7b2b5ff7f757422c7fcb3982430df66f1f793b8d0580a-360007210818.jpg)

Before implementing iOS App Banners consider:

- Don't implement both iOS App Banner and AppsFlyer Smart Banners simultaneously. Doing so can result in display issues in your mobile website.
- The App banner solution is iOS-specific, meaning that it does not function on OS X.
- The App banner only works on Safari.

### Setting a web page with an app banner and click attribution link

1. Insert the following in the header element of the web page HTML.

```markup
<meta name=