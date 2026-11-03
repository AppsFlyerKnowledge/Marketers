---
title: Attributing iOS Safari App Banners
metadata:
  keywords:
    - iOS Safari
    - Smart App Banner
    - Advertisers
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2017-01-02T15:08:07Z'
  edited_at: '2026-10-13T01:37:20Z'
  id: 115000171743
  locale: zh-cn
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/zh-cn/articles/115000171743
---
> **At a glance:** Safari implements an <Anchor target="_blank" href="http://developer.apple.com/library/ios/#documentation/AppleApplications/Reference/SafariWebContent/PromotingAppswithAppBanners/PromotingAppswithAppBanners.html">App Banner</Anchor> feature providing a standardized way to promote apps in the Apple App Store. **This is not related to the recommended AppsFlyer <Anchor target="_blank" href="/marketers/zh/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banner</Anchor> solution.**

> 📘 **Note**
>
> We recommend using AppsFlyer Smart Banners to convert website visitors to app users.
>
> AppsFlyer Smart Banners:
>
> * Supports all browsers
> * Are customizable
> * Works on all Android and iOS devices

## iOS App Banner

Using iOS 6.0 and later, you can implement App Banners in Safari to promote apps available in the App Store.

**Example banner in Safari**

<Image alt="AppleBanner_en-us.jpg" src="https://files.readme.io/3682c7d613246e51608356ce773e6924276d43acdf40cdc7b63f5c9132bb71de-51165531547153.jpg" width="278px" />

Before implementing iOS App Banners consider:

* Don't implement both iOS App Banner and AppsFlyer Smart Banners simultaneously. Doing so can result in display issues in your mobile website.
* The App banner solution is iOS-specific, meaning that it does not function on OS X.
* The App banner only works on Safari.

### Setting a web page with an app banner and click attribution link

1. Insert the following in the header element of the web page HTML.  

   ```html Markup
   <meta name="apple-itunes-app" content="app-id=123456789">
   ```
2. Generate an attribution Link for the mobile app you are promoting in the App Banner. The following is an example showing an attribution Link for the mobile app being promoted in the App Banner. You can also use <Anchor target="_blank" href="/marketers/zh/docs/about-link-structure-and-parameters">shortened custom attribution links</Anchor>.   

   ```http
   https://app.appsflyer.com/123456789?pid=ios_smart_banner&c=ios_campaign
   ```
3. Insert the generated attribution link inside an image pixel. Your image pixel with the measurement URL is formatted as illustrated.

   ```html Markup
   <img src="https://app.appsflyer.com/123456789?pid=ios_smart_banner&c=ios_campaign" height="1" width="1" border ="0" />
   ```

   The final HTML page with the image pixel should appear as shown in the following HTML example.

   ```html Markup
   <html>
     <head>
       <meta name="apple-itunes-app" content="app-id=123456789">

     </head>
     <body>
       <p>This is my website</p>
       <img src="https://app.appsflyer.com/123456789?pid=ios_smart_banner&c=ios_campaign" height="1" width="1" border ="0" />
     </body>
   </html>
   ```

**Note!** This code loads and fires a click on both iOS and Android devices. To disable the code on Android devices, add the required logic in your code.