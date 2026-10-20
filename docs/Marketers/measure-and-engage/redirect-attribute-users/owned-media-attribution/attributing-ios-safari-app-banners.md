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
  edited_at: '2023-07-24T11:58:04Z'
  id: 115000171743
  locale: en-us
  section: Owned media attribution
  section_id: 6551214397585
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/115000171743-Attributing-iOS-Safari-App-Banners
---
**At a glance:** Safari implements an [App Banner](http://developer.apple.com/library/ios/#documentation/AppleApplications/Reference/SafariWebContent/PromotingAppswithAppBanners/PromotingAppswithAppBanners.html) feature providing a standardized way to promote apps in the Apple App Store. **This is not related to the recommended AppsFlyer  [Smart Banner](/docs/smart-banners-mobile-web-to-app-for-marketers) solution.**

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

![AppleBanner_en-us.jpg](https://files.readme.io/dde65134ca3450b407c7b2b5ff7f757422c7fcb3982430df66f1f793b8d0580a-360007210818.jpg)

Before implementing iOS App Banners consider:

* Don't implement both iOS App Banner and AppsFlyer Smart Banners simultaneously. Doing so can result in display issues in your mobile website.
* The App banner solution is iOS-specific, meaning that it does not function on OS X.
* The App banner only works on Safari.

### Setting a web page with an app banner and click attribution link

1. Insert the following in the header element of the web page HTML.  

   ```html
   <meta name="apple-itunes-app" content="app-id=123456789">
   ```
2. Generate an attribution Link for the mobile app you are promoting in the App Banner. The following is an example showing an attribution Link for the mobile app being promoted in the App Banner. You can also use [shortened custom attribution links](/docs/about-link-structure-and-parameters).   

   ```
   https://app.appsflyer.com/123456789?pid=ios_smart_banner&c=ios_campaign
   ```
3. Insert the generated attribution link inside an image pixel. Your image pixel with the measurement URL is formatted as illustrated.

   ```html
   <img src="https://app.appsflyer.com/123456789?pid=ios_smart_banner&c=ios_campaign" height="1" width="1" border ="0" />
   ```

   The final HTML page with the image pixel should appear as shown in the following HTML example.

   ```html
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