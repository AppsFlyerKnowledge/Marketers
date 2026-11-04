---
title: iOS Safari App Bannersのアトリビューション
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
  edited_at: '2026-10-14T09:38:30Z'
  id: 115000171743
  locale: ja
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/ja/articles/115000171743
---
> **概要：** 概要： Safariには、Apple App Storeのアプリをプロモーションする <Anchor target="_blank" href="http://developer.apple.com/library/ios/#documentation/AppleApplications/Reference/SafariWebContent/PromotingAppswithAppBanners/PromotingAppswithAppBanners.html">Smart App Banner</Anchor> 機能が提供されています。

<div id="note" />

> 📘 **注意**
>
> ウェブサイトの訪問者をアプリユーザーに変換するために、AppsFlyerのスマートバナーの使用をお勧めします。
>
> AppsFlyerのスマートバナー：
>
> * 全てのブラウザに対応しています
> * カスタマイズ可能です
> * 全てのAndroid・iOSデバイスで機能します

<div id="ios-app-banner" />

## iOSアプリバナー

iOS 6.0以降、SafariにSmart App Bannersを実装して、App Storeで配信されているアプリをプロモーションすることができます。

**Safariのバナー例**

<Image alt="AppleBanner_en-us.jpg" src="https://files.readme.io/a45e35278a22e7c272e9af8b5caa2b134fed70f29bb5fbcf1605ed1662d9eddf-51444659311121.jpg" width="278px" />

iOSアプリバナーを実装する前に、次の点を考慮してください。

* iOSアプリバナーとAppsFlyerのスマートバナーの両方を同時に実装しないでください。モバイルWebサイトの表示に問題が発生する可能性があります。
* Smart Appバナーソリューションは、iOSに特化しているため、OS Xでは機能しません。
* アプリバナーはSafariでのみ機能します

<div id="setting-a-web-page-with-an-app-banner-and-click-attribution-link" />

### スマートアプリのバナーとクリック計測リンクの設定

1. WebページのHTMLのheader要素に次のように挿入します。  

   ```html Markup
   <meta name="apple-itunes-app" content="app-id=123456789">
   ```
2. スマートアプリバナーでプロモーションしているモバイルアプリの計測リンクを生成します。以下は、スマートアプリバナーの計測リンクを示す例です。<Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">OneLinkショートリンクURL</Anchor> を使用することもできます。   

   ```http
   https://app.appsflyer.com/123456789?pid=ios_smart_banner&c=ios_campaign
   ```
3. 生成した計測リンクを画像ピクセル内に挿入します。計測用URLを持つ画像ピクセルは、図のような形式になっています。

   ```html Markup
   <img src="https://app.appsflyer.com/123456789?pid=ios_smart_banner&c=ios_campaign" height="1" width="1" border ="0" />
   ```

   最終的に画像ピクセルを含むHTMLページは、以下のHTML例のように表示されるはずです。

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

**注！ このコードは、iOSデバイスとAndroidデバイスの両方で、クリックをロードし、トリガーします。Android端末で無効にするには、コードに必要なロジックを追加してください。**

<div data-zendesk-anchors="ios-app-banner=ios%E3%82%A2%E3%83%97%E3%83%AA%E3%83%90%E3%83%8A%E3%83%BC setting-a-web-page-with-an-app-banner-and-click-attribution-link=%E3%82%B9%E3%83%9E%E3%83%BC%E3%83%88%E3%82%A2%E3%83%97%E3%83%AA%E3%81%AE%E3%83%90%E3%83%8A%E3%83%BC%E3%81%A8%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E8%A8%88%E6%B8%AC%E3%83%AA%E3%83%B3%E3%82%AF%E3%81%AE%E8%A8%AD%E5%AE%9A" />
