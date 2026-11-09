---
title: iOS 사파리 앱 배너 어트리뷰션
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
  edited_at: '2026-10-14T10:39:42Z'
  id: 115000171743
  locale: ko
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/ko/articles/115000171743
---
> **한눈에 보기:** 요약: iOS가 사파리 브라우저로 지원하는 <Anchor target="_blank" href="http://developer.apple.com/library/ios/#documentation/AppleApplications/Reference/SafariWebContent/PromotingAppswithAppBanners/PromotingAppswithAppBanners.html">스마트 앱 배너</Anchor> 기능은  애플 앱스토어에서 앱을 홍보하는 표준 방식입니다.

<div id="note" />

> 📘 **참고사항**
>
> 앱스플라이어 스마트 배너를 사용하여 웹사이트 방문자를 앱 사용자로 전환하는 것이 좋습니다.
>
> 앱스플라이어 스마트 배너:
>
> * 모든 브라우저 지원
> * 커스터마이즈 가능
> * 모든 안드로이드 및 iOS 기기에서 작동

<div id="ios-app-banner" />

## iOS 앱 배너

iOS 6.0 이상에서 사파리로 앱 배너를 구현하여 앱스토어에서 앱을 홍보할 수 있습니다.

**iOS 사파리 스마트 앱 배너 예시**

<Image align="center" alt="AppleBanner_en-us.jpg" src="https://files.readme.io/6c65f5424eb1019726726927e1f908ccc9903a2a4bbec1de5a5bb680d7a991aa-51858172981393.jpg" width="278px" />

iOS 앱 배너를 구현하기 전에 다음을 고려하십시오.

* iOS 앱 배너와 앱스플라이어 스마트 배너를 동시에 구현하지 마십시오. 동시에 구현하면 모바일 웹 사이트에 디스플레이 문제가 발생할 수 있습니다.
* 배너 솔루션은 iOS에 최적화되어 있고, OS X에서 작동하지 않습니다.
* 앱 배너는 사파리에서만 작동합니다.

<div id="setting-a-web-page-with-an-app-banner-and-click-attribution-link" />

### 웹페이지에 앱 배너와 클릭 어트리뷰션 링크 설정하기

1. 웹페이지 HTML 헤더 부분에 다음을 삽입합니다.   

   ```html Markup
   <meta name="apple-itunes-app" content="app-id=123456789">
   ```
2. 앱 배너로 프로모션할 모바일 앱 어트리뷰션 링크를 생성합니다. 다음은 앱 배너로 소개될 모바일 앱의 어트리뷰션 링크 예시입니다. <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters">단축된 어트리뷰션 커스텀 링크</Anchor>를 사용하실 수도 있습니다.    

   ```http
   https://app.appsflyer.com/123456789?pid=ios_smart_banner&c=ios_campaign
   ```
3. 생성된 어트리뷰션 링크를 이미지 픽셀 안에 삽입하십시오. 측정 URL이 삽입된 이미지 픽셀이 아래와 같이 형식이 지정됩니다.

   ```html Markup
   <img src="https://app.appsflyer.com/123456789?pid=ios_smart_banner&c=ios_campaign" height="1" width="1" border ="0" />
   ```

   이미지 픽셀을 포함한 최종 HTML 페이지가 아래 HTML 예시와 같이 나타납니다.

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

**참고! 이 코드는 iOS 및 안드로이드 디바이스 모두에서 클릭을 로드하고 실행합니다. 안드로이드 디바이스에서 코드를 사용 안 함으로 설정하려면 코드에 필수 로직을 추가하십시오.**

<div data-zendesk-anchors="ios-app-banner=ios-%EC%95%B1-%EB%B0%B0%EB%84%88 setting-a-web-page-with-an-app-banner-and-click-attribution-link=%EC%9B%B9%ED%8E%98%EC%9D%B4%EC%A7%80%EC%97%90-%EC%95%B1-%EB%B0%B0%EB%84%88%EC%99%80-%ED%81%B4%EB%A6%AD-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0" />
