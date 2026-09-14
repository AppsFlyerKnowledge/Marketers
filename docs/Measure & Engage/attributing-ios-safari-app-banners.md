---
title: "Attributing iOS Safari App Banners"
excerpt: "Learn how to implement and attribute iOS Safari App Banners using AppsFlyer measurement links."
---
At a glance: Safari implements an [App Banner](http://developer.apple.com/library/ios/#documentation/AppleApplications/Reference/SafariWebContent/PromotingAppswithAppBanners/PromotingAppswithAppBanners.html) feature providing a standardized way to promote apps in the Apple App Store. **This is not related to the recommended AppsFlyer [Smart Banner](https://support.appsflyer.com/hc/articles/360000764837) solution.**

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