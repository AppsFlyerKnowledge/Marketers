---
title: Iterable과 앱스플라이어의 연동
metadata:
  keywords:
    - OneLink
    - Advertisers
    - ESP
    - Developers
    - Iterable
    - Deep Likning
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2019-09-16T13:14:19Z'
  edited_at: '2026-10-14T10:31:53Z'
  id: 360002522337
  locale: ko
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/ko/articles/360002522337
---
> **한눈에 보기:** 원링크 기반 어트리뷰션 링크를 Iterable 시스템과 연동하여 <Anchor target="_blank" href="/marketers/ko/docs/email-service-provider-esp-integration-guide">이메일에서 딥링크를</Anchor> 생성해 보세요. 이 연동에서는 브랜드 클릭 기록 도메인 위에 유니버설 링크에 대한 Iterable의 지원을 활용합니다.

![iterable-af-logo.png](https://files.readme.io/e339ea75a54e53711f3c577c7f82339151af13e6c086cc1435cbb57cf1fae3f0-49839295443089.png)

## 소개

ESP(이메일 서비스 제공업체)는 세분화된 사용자 트래픽을 위한 훌륭한 소스가 될 수 있습니다.

ESP의 문제점 중 하나는 딥링킹 기능을 그대로 유지하면서 클릭 수를 기록하는 것입니다. ESP는 딥링킹 URL을 자체 ESP의 클릭 기록 도메인으로 래핑합니다. 이 절차는 때때로 iOS 유니버설 링크 프로세스를 중단시킵니다.

클릭 기록 도메인 위에 유니버설 링크를 지원하는 Iterable을 사용하면 딥링킹과 클릭 기록을 계속 수행할 수 있습니다.

## 선행 조건

<Tabs>
<Tab title="iOS">

* 앱스플라이어 iOS SDK 버전 4.9.0

</Tab>

<Tab title="Android">

* 앱스플라이어 Android SDK 버전 4.9.0

Iterable은 Android 앱 링크를 지원하지 않습니다. 그러나 <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">URI Scheme 딥링킹은 계속 지원됩니다</Anchor>. Android에서 딥링킹을 지원하기 위해 Iterable 측에서 특별한 조치는 불필요합니다.

</Tab>
</Tabs>

## Iterable 설정

### 1단계: Iterable에서 링크 브랜딩 설정하기

전용 클릭 기록 도메인을 만들고 하위 도메인을 설정합니다(예: [click.example.com](http://click.example.com)). 이는 지정된 도메인을 구매하거나 자체 도메인을 사용하여 수행할 수 있습니다.

Iterable로 클릭 기록 도메인을 설정하는 방법에 대한 자세한 내용은 <Anchor target="_blank" href="https://support.iterable.com/hc/en-us/articles/115002651226-Setting-up-mail-domains">여기</Anchor>를 참조하세요.

### 2단계: Iterable에 SSL 인증서 업로드하기

클릭 기록 도메인에 도메인의 SSL 인증서를 포함해야 합니다. SSL 인증서는 Iterable 계정에 설치되어 있어야 합니다. SSL 인증서 설치에 대한 지침은 <Anchor target="_blank" href="https://support.iterable.com/hc/en-us/articles/115000427446-How-to-Set-up-HTTPS-for-Links-for-Click-Tracking">여기</Anchor>에서 확인할 수 있습니다.

### 2단계: Iterable에 AASA(iOS) 및 에셋 링크 파일(Android)을 제공합니다.

<div id="aasa-for-ios" />

<Accordion title="iOS용 AASA">

Iterable이 iOS 유니버설 링크를 지원하려면 AASA 파일이 필요합니다. 다음 설명을 참조하십시오.

유니버설 링크로 원링크를 설정하면 이미 원링크와 연결된 AASA가 있습니다. AASA를 받으려면:

1. ***원링크 템플릿***으로 이동하여 유니버설 링크로 구성된 원링크를 찾습니다.
2. 원링크 URL 끝에 **/.well-known/apple-app-site-association**을 추가합니다.
3. 브라우저 주소 표시줄에 원링크를 붙여넣고 Enter 키를 누릅니다. 예: **`<OneLinkSubdomain>`.onelink.me/.well-known/apple-app-site-association.** 이렇게 하면 AASA 파일이 컴퓨터에 다운로드됩니다. 간단한 텍스트 편집기를 사용하여 열 수 있습니다.
4. 링크 다시 쓰기 규칙을 정의합니다. 더 자세한 정보는 <Anchor target="_blank" href="https://support.iterable.com/hc/en-us/articles/360035496511">여기</Anchor>를 참고하십시오.
5. 이 AASA 파일을 Iterable로 보냅니다. 자세한 내용과 이 파일의 내용에 대한 자세한 내용은 <Anchor target="_blank" href="https://support.iterable.com/hc/en-us/articles/360035496511-iOS-Universal-Lin">Iterable 가이드</Anchor>를 참조하세요.

</Accordion>

<div id="asset-links-for-android" />

<Accordion title="Android용 자산 링크">

앱 링크로 원링크를 설정할 때, 원링크와 연결된 에셋 링크 파일이 이미 있습니다. 자산 링크 파일을 가져오려면:

1. ***원링크 템플릿***으로 이동하여 앱 링크로 구성된 원링크를 찾습니다.
2. 원링크 URL 끝에 **/.well-known/assetlinks.json**을 추가합니다.
3. 브라우저 주소 표시줄에 원링크를 붙여넣고 Enter 키를 누릅니다. 예:**`<OneLinkSubdomain>`.onelink.me/.well-known/assetlinks.json.** 이렇게 하면 자산 링크 파일이 컴퓨터에 다운로드됩니다. 간단한 텍스트 편집기를 사용하여 열 수 있습니다.
4. 이 애셋 링크 파일을 Iterable로 보냅니다. 자세한 내용과 이 파일의 내용에 대한 자세한 내용은 <Anchor target="_blank" href="https://support.iterable.com/hc/en-us/articles/360035127392">Iterable 가이드</Anchor>를 참조하세요.

</Accordion>

## 앱 설정

앱 및 유니버설 링크를 지원하도록 앱을 설정하려면 다음을 참조하세요.

<div id="step-1-for-android-setting-up-your-app-to-support-app-links" />

<Accordion title="Android에 대한 1단계: 앱 링크를 지원하도록 앱 설정">

#### 1단계: Android 매니페스트의 활동에 클릭 도메인 추가

Android 매니페스트에서 클릭 도메인 호스트와 딥링크하려는 활동의 활동 태그에 접두사를 추가합니다.

```html Markup
<activity android:name=".DeepLinkActivity">
    <intent-filter  android:autoVerify="true">
        <action android:name="android.intent.action.VIEW" />
           <category android:name="android.intent.category.DEFAULT" />
           <category android:name="android.intent.category.BROWSABLE" />
           <data android:scheme="https"
               android:host="click.example.com"
               android:pathPrefix="/campaign" />
     </intent-filter>
</activity>
```

#### 2단계: 클릭 도메인을 확인하도록 앱 설정

SDK는 캠페인 세부 정보를 얻기 위해 클릭 도메인 뒤에 있는 원링크를 확인해야 합니다. 세부 정보는 `onAppOpenAttribution` 메서드를 통해 반환됩니다.

클릭 도메인을 확인하는 방법:

1. SDK 버전이 4.9.0 이상인지 확인합니다.
2. SDK API `setResolveDeepLinkURLs`에 클릭 도메인을 나열합니다. 이 API는 SDK 초기화 전에 호출해야 합니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/additional-sdk-integration-guide#resolve-wrapped-deep-link-urls">여기</Anchor>에서 SDK 설명서를 참조하세요.  

   ```java
   AppsFlyerLib.getInstance().setResolveDeepLinkURLs("click.example.com");
   ```

</Accordion>

<div id="step-1-for-ios-setting-up-your-app-to-support-universal-links" />

<Accordion title="iOS에 대한 1단계: 유니버설 링크를 지원하도록 앱 설정">

이 섹션에서는 유니버설 링크를 지원하도록 앱을 설정하는 방법을 설명합니다.

#### 1단계: Xcode에서 클릭 도메인 연결

1. Xcode에서 프로젝트를 클릭합니다.
2. ***기능***을 클릭합니다.[![configure-xcode-deeplinking-domain.png](https://files.readme.io/90d0dcc0eba2d7d081ab7d5d4ea697e9257b9107af463fa8c973169f8a2651db-49839256220433.png)](https://files.readme.io/90d0dcc0eba2d7d081ab7d5d4ea697e9257b9107af463fa8c973169f8a2651db-49839256220433.png)
3. ***연결된 도메인***을 켭니다.
4. + 기호를 클릭하고 클릭 도메인을 추가합니다. 예를 들면 applinks:click.example.com과 같습니다.

</Accordion>

딥링크를 확인하도록 SDK 구성을 설정하려면 다음을 참조하세요.

<div id="step-2-for-android-resolve-deep-links" />

<Accordion title="Android에 대한 2단계: 딥링크 확인">

SDK는 캠페인 세부 정보를 얻기 위해 클릭 도메인 뒤에 있는 원링크를 확인해야 합니다. 세부 정보는 `onAppOpenAttribution` 메서드를 통해 반환됩니다.

클릭 도메인을 확인하려면:

1. SDK 버전이 4.9.0 이상인지 확인합니다.
2. SDK 속성 `resolveDeepLinkURLs`에 클릭 도메인을 나열합니다. 이 속성은 SDK 초기화 전에 설정해야 합니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/additional-sdk-integration-guide#resolve-wrapped-deep-link-urls">여기</Anchor>에서 SDK 설명서를 참조하세요.  

   ```java
   AppsFlyerLib.getInstance().setResolveDeepLinkURLs("clickdomain.com", "myclickdomain.com", "anotherclickdomain.com");
   ```

</Accordion>

<div id="step-2-for-ios-resolve-deep-links" />

<Accordion title="iOS에 대한 2단계: 딥링크 확인">

SDK는 캠페인 세부 정보를 얻기 위해 클릭 도메인 뒤에 있는 원링크를 확인해야 합니다. 세부 정보는 `onAppOpenAttribution` 메서드를 통해 반환됩니다.

클릭 도메인을 확인하려면:

1. SDK 버전이 4.9.0 이상인지 확인합니다.
2. SDK 속성 `resolveDeepLinkURLs`에 클릭 도메인을 나열합니다. 이 속성은 SDK 초기화 전에 설정해야 합니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/additional-sdk-integration-guide#resolve-wrapped-deep-link-urls">여기</Anchor>에서 SDK 설명서를 참조하세요.  

   <Tabs>
   <Tab title="Objective-C">

   ```objectivec
   [AppsFlyerLib shared].resolveDeepLinkURLs = @[@"example.com",@"click.example.com"];
   ```

   </Tab>

   <Tab title="Swift">

   ```swift
   AppsFlyerLib.shared().resolveDeepLinkURLs = ["example.com", "click.example.com"]
   ```

   </Tab>
   </Tabs>

3. SDK가 클릭 기록 도메인을 확인할 수 있도록 다음 코드를 추가합니다.  

   <Tabs>
   <Tab title="Objective-C">

   AppDelegate.m에 다음 코드를 추가합니다.

   ```objectivec
   - (NSDictionary *)allHTTPHeaderFieldsForResolveDeepLinkURL:(NSURL *)URL {
       if ([URL.host  isEqual: @"click.example.com"]) {
           return [NSDictionary dictionary];
       }
       else {
           return nil;
       }
   }
   ```

   </Tab>

   <Tab title="Swift">

   AppDelgate.swift에 이 코드를 추가합니다.

   ```swift
   func allHTTPHeaderFields(forResolveDeepLinkURL URL: URL!) -> [String : String]! {
       if (URL.host == "click.example.com") {
           /// Change User-Agent
           return [:]
       } else {
           return nil;
       }
   }
   ```

   </Tab>
   </Tabs>

</Accordion>

## 첫 번째 이메일 보내기

1. 링크 관리 페이지에서(또는 수동으로) <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">원링크 URL을 만듭니다</Anchor>.
2. 원링크 URL을 생성할 때 모든 파라미터 값을 URL로 인코딩해야 합니다.
3. 다음 매개 변수를 사용하는 것이 좋습니다.
   * pid(미디어 원본) - 이 사용을 나타내는 미디어 원본(예: 이메일)을 사용합니다.
   * c (campaign) - 측정하려는 캠페인의 이름입니다.
   * af\_dp - 사용자를 딥링크하려는 딥링크 URI 체계입니다.
   * af\_web\_dp - 데스크톱에서 링크를 클릭하는 사용자를 리디렉션하는 위치입니다.
   * af\_ios\_url - iOS 장치에서 링크를 클릭하는 앱이 없는 사용자를 리디렉션하는 위치입니다.
   * af\_android\_url - 앱이 없는 사용자를 리디렉션할 위치: Android 기기에서 링크를 클릭합니다.
4. Iterable에서 생성한 이메일에 원링크 URL을 입력합니다. 예:

   ```http
   <a href="greatapp.onelink.me/abcd/1234567">Download my great app!</a>
   ```

   이 단계에서 Iterable은 위의 링크를 이전 단계에서 설정한 클릭 도메인으로 래핑합니다. 시나리오 : 세 개의 클릭 도메인이 귀하의 원링크 [https://mysubdomain.onelink.me/abCD](https://mysubdomain.onelink.me/abCD)로 리디렉션됩니다. 앱이 사용자의 기기에 설치되어 있는 경우 클릭 도메인은 앱에 딥 링크됩니다.

> 📄 **예시**
>
> URL 매개변수는 가독성을 위해 이 예제에서 URL로 인코딩되지 않습니다.
>
> ```http
> https://greatapp.onelink.me/abcd?pid=Email&c=Spring_Newsletter&is_retargeting=true&
> af_dp=testapp://path/to/content&af_web_dp=https://www.example.com/path/to/content&
> af_ios_url=https://www.example.com/path/to/content&af_android_url=https://www.example.com/path/to/content
> ```

### 링크 테스트

위에서 언급한 모든 필수 단계를 수행하고, 적절한 원링크 URL을 생성하고, 이를 이메일에 넣은 후, 자신에게 테스트 이메일을 보냅니다.

무엇을 기대할 수 있을까요?

앱이 설치되어 있는 경우 앱을 호출해야 합니다. 관련 앱스플라이어 SDK 딥링킹 API가 구현된 경우 관련 콘텐츠에 딥링크되어야 합니다.  
또한 클릭은 제공된 미디어 소스 및 캠페인에 어트리뷰션된 앱스플라이어 대시보드와 Iterable 데이터 모두에 나타나야 합니다.

<div data-zendesk-anchors="introduction=%EC%86%8C%EA%B0%9C h_01HV6PJQRMT8037JMVMMXDPWGN=%EC%86%8C%EA%B0%9C prerequisites=%EC%84%A0%ED%96%89-%EC%A1%B0%EA%B1%B4 h_01HV6PJQRM5N1K6CY0NSSFXT3X=%EC%84%A0%ED%96%89-%EC%A1%B0%EA%B1%B4 setting-up-iterable=iterable-%EC%84%A4%EC%A0%95 h_01HV6PJQRMX18FRB3NMZH6NCH0=iterable-%EC%84%A4%EC%A0%95 step-1-setting-up-link-branding-in-iterable=1%EB%8B%A8%EA%B3%84-iterable%EC%97%90%EC%84%9C-%EB%A7%81%ED%81%AC-%EB%B8%8C%EB%9E%9C%EB%94%A9-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 h_01HV6PJQRMMYV3A5ZSEGTT7993=1%EB%8B%A8%EA%B3%84-iterable%EC%97%90%EC%84%9C-%EB%A7%81%ED%81%AC-%EB%B8%8C%EB%9E%9C%EB%94%A9-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 step-2-uploading-your-ssl-certificate-to-iterable=2%EB%8B%A8%EA%B3%84-iterable%EC%97%90-ssl-%EC%9D%B8%EC%A6%9D%EC%84%9C-%EC%97%85%EB%A1%9C%EB%93%9C%ED%95%98%EA%B8%B0 h_01HV6PJQRMYDDWK9AKGN258TTM=2%EB%8B%A8%EA%B3%84-iterable%EC%97%90-ssl-%EC%9D%B8%EC%A6%9D%EC%84%9C-%EC%97%85%EB%A1%9C%EB%93%9C%ED%95%98%EA%B8%B0 step-2-give-iterable-an-aasa-ios-and-an-asset-links-file-android=2%EB%8B%A8%EA%B3%84-iterable%EC%97%90-aasaios-%EB%B0%8F-%EC%97%90%EC%85%8B-%EB%A7%81%ED%81%AC-%ED%8C%8C%EC%9D%BCandroid%EC%9D%84-%EC%A0%9C%EA%B3%B5%ED%95%A9%EB%8B%88%EB%8B%A4 h_01HV6PJQRMFJ23627KS83D4C6A=2%EB%8B%A8%EA%B3%84-iterable%EC%97%90-aasaios-%EB%B0%8F-%EC%97%90%EC%85%8B-%EB%A7%81%ED%81%AC-%ED%8C%8C%EC%9D%BCandroid%EC%9D%84-%EC%A0%9C%EA%B3%B5%ED%95%A9%EB%8B%88%EB%8B%A4 h_01HV6PJQRMNSYK8N7QEE00KSPE=aasa-for-ios h_01HV6PJQRMSMZCVJ5XRXZ3SWEH=asset-links-for-android setting-up-your-app=%EC%95%B1-%EC%84%A4%EC%A0%95 h_01HV6PJQRMJHDF94JSAT8N8SP9=%EC%95%B1-%EC%84%A4%EC%A0%95 h_01HV6PJQRM5S772CTH219MGY44=step-1-for-android-setting-up-your-app-to-support-app-links step-1-adding-the-click-domain-to-the-activity-in-the-android-manifest=1%EB%8B%A8%EA%B3%84-android-%EB%A7%A4%EB%8B%88%ED%8E%98%EC%8A%A4%ED%8A%B8%EC%9D%98-%ED%99%9C%EB%8F%99%EC%97%90-%ED%81%B4%EB%A6%AD-%EB%8F%84%EB%A9%94%EC%9D%B8-%EC%B6%94%EA%B0%80 h_01HV6PJQRM2V31JAJ52Q3FHQWH=1%EB%8B%A8%EA%B3%84-android-%EB%A7%A4%EB%8B%88%ED%8E%98%EC%8A%A4%ED%8A%B8%EC%9D%98-%ED%99%9C%EB%8F%99%EC%97%90-%ED%81%B4%EB%A6%AD-%EB%8F%84%EB%A9%94%EC%9D%B8-%EC%B6%94%EA%B0%80 step-2%C2%A0setting-up-the-app-to-resolve-click-domains=2%EB%8B%A8%EA%B3%84%ED%81%B4%EB%A6%AD-%EB%8F%84%EB%A9%94%EC%9D%B8%EC%9D%84-%ED%99%95%EC%9D%B8%ED%95%98%EB%8F%84%EB%A1%9D-%EC%95%B1-%EC%84%A4%EC%A0%95 h_01HV6PJQRMCRFM90QSP5SS72SE=2%EB%8B%A8%EA%B3%84%ED%81%B4%EB%A6%AD-%EB%8F%84%EB%A9%94%EC%9D%B8%EC%9D%84-%ED%99%95%EC%9D%B8%ED%95%98%EB%8F%84%EB%A1%9D-%EC%95%B1-%EC%84%A4%EC%A0%95 h_01HV6PJQRMVJB6J6GV41DCYAVQ=step-1-for-ios-setting-up-your-app-to-support-universal-links step-1-associating-click-domains-in-xcode=1%EB%8B%A8%EA%B3%84-xcode%EC%97%90%EC%84%9C-%ED%81%B4%EB%A6%AD-%EB%8F%84%EB%A9%94%EC%9D%B8-%EC%97%B0%EA%B2%B0 h_01HV6PJQRNRW8Y97JWHP0MSXZF=1%EB%8B%A8%EA%B3%84-xcode%EC%97%90%EC%84%9C-%ED%81%B4%EB%A6%AD-%EB%8F%84%EB%A9%94%EC%9D%B8-%EC%97%B0%EA%B2%B0 h_01HV6PJQRNHFH8XGMCEWVGSPA5=step-2-for-android-resolve-deep-links h_01HV6PJQRN4NYPWS2XQQSJAM5R=step-2-for-ios-resolve-deep-links sending-your-first-email=%EC%B2%AB-%EB%B2%88%EC%A7%B8-%EC%9D%B4%EB%A9%94%EC%9D%BC-%EB%B3%B4%EB%82%B4%EA%B8%B0 h_01HV6PJQRN2H29D8HKXHBYE1NB=%EC%B2%AB-%EB%B2%88%EC%A7%B8-%EC%9D%B4%EB%A9%94%EC%9D%BC-%EB%B3%B4%EB%82%B4%EA%B8%B0 h_01HV6PJQRNB327E42Y0ZJM9306=%EC%98%88%EC%8B%9C testing-your-links=%EB%A7%81%ED%81%AC-%ED%85%8C%EC%8A%A4%ED%8A%B8 h_01HV6PJQRNET2J17ZGGZE0K0Q6=%EB%A7%81%ED%81%AC-%ED%85%8C%EC%8A%A4%ED%8A%B8" />
