---
title: Oracle Responsys와 앱스플라이어의 연동
metadata:
  keywords:
    - Oracle Responsys
    - Advertisers
    - Developers
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2019-11-20T09:26:13Z'
  edited_at: '2026-10-14T10:38:03Z'
  id: 360003798297
  locale: ko
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/ko/articles/360003798297
---
> **한눈에 보기:** 요약: 이메일 전송 및 분석 플랫폼인 Oracle Responsys는 이메일에 앱스플라이어 원링크를 내장하고 있습니다. 링크를 클릭하는 이메일 수신자는 앱에 딥 링크됩니다.

<Image align="center" alt="oracle-responsys-af-logo.png" src="https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png" />

ESP(이메일 서비스 제공업체)는 세분화된 사용자 트래픽을 위한 훌륭한 소스가 될 수 있습니다.

ESP의 과제 중 하나는 올바른 어트리뷰션과 딥링킹을 수행하는 것입니다. ESP는 딥링킹 URL을 자신의 ESP의 클릭 기록 도메인으로 래핑합니다. 이 절차는 종종 iOS 유니버설 링크 및 Android 앱 링크의 기능을 중단합니다.

그러나 딥링킹과 클릭 기록은 클릭 기록 도메인 위에 유니버셜 링크와 앱링크를 지원하는 ESP를 통해 여전히 가능합니다. 또한 클릭 기록 도메인 역할을 하도록 고유한 클릭 도메인을 설정할 수 있습니다.

<div id="prerequisites" />

## 필수 조건

* <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">원링크로 딥링킹</Anchor>을 지원하도록 앱을 설정합니다.
* SDK 버전 확인(Android 및 iOS 모두)

<Tabs>
<Tab title="iOS">

* 앱스플라이어 iOS SDK 버전 4.9.0 (또는 그 이상)

</Tab>

<Tab title="Android">

* 앱스플라이어 안드로이드 SDK 버전 4.9.0 (또는 그 이상)

</Tab>
</Tabs>

<div id="setting-up-oracle-responsys-click-domain" />

## Oracle Responsys 클릭 도메인 설정

이 절에 따라 Oracle Responsys에서 클릭 도메인(클릭 기록 도메인)을 설정합니다.

<div id="step-1-set-up-a-click-domain-in-oracle-responsys" />

### 1단계: 1단계: Oracle Responsys에서 클릭 도메인 설정

클릭 도메인을 설정하려면 <Anchor target="_blank" href="https://docs.oracle.com/cloud/latest/marketingcs_gs/OMCEA/LinkTable_Main.htm?cshid=LinkTable_Main">클릭 도메인을 생성하는</Anchor> 방법에 대한 Oracle Responsys 공식 가이드를 따르십시오. Oracle Responsys는 링크 테이블을 사용하여 특정 캠페인에 대한 클릭을 기록합니다

**링크** 테이블에서 IOS 링크 URL을 **링크 URL** 과 동일하게 정의할 수 있습니다.

<Image align="center" alt="Oracle-responsys-link-tracking-table.png" src="https://files.readme.io/c151c58af73cf460ba4275a9159e45c15807f311fa8d8b4b1531b0cdf7e3bc4e-49839256667665.png" />

링크 테이블에서 클릭 도메인을 설정하면 Responsys는 이러한 도메인을 사용하여 이메일 캠페인에 포함된 OneLink를 래핑합니다. 이러한 방식으로 Responsys는 원링크 및 딥링킹 기능을 유지하면서 시스템에서 클릭을 기록할 수 있습니다.

<div id="step-2-give-responsys-an-aasa-ios-and-an-asset-links-file-android" />

### 2단계: 2단계: Responsys에 AASA(iOS) 및 자산 링크 파일(Android) 제공

<div id="aasa-for-ios" />

<Accordion title="iOS용 AASA">

Responsys가 iOS 유니버셜 링크를 지원하려면 AASA 파일이 필요합니다. 다음 설명을 참조하십시오.

유니버설 링크로 원링크를 설정하면 이미 원링크와 연결된 AASA가 있습니다. AASA를 받으려면:

1. 원링크 구성으로 이동하여 유니버설 링크로 구성된 원링크를 찾습니다.
2. 원링크 URL 끝에 **/.well-known/apple-app-site-association**을 추가합니다.
3. 브라우저 주소 표시줄에 원링크를 붙여넣고 Enter 키를 누릅니다. 예: **`<OneLinkSubdomain>`.onelink.me/.well-known/apple-app-site-association.** 이렇게 하면 AASA 파일이 컴퓨터에 다운로드됩니다. 간단한 텍스트 편집기를 사용하여 열 수 있습니다.
4. 이 AASA 파일을 Responsys로 보냅니다. 자세한 내용과 이 파일의 내용에 대한 자세한 내용은 <Anchor target="_blank" href="https://docs.oracle.com/cloud/latest/marketingcs_gs/OMCFB/pdf/ios-universal-links-dev-guide.pdf">Oracle 가이드</Anchor>의 11페이지를 참조하십시오.

</Accordion>

<div id="asset-links-for-android" />

<Accordion title="Android용 자산 링크">

앱 링크로 원링크를 설정할 때, 원링크와 연결된 에셋 링크 파일이 이미 있습니다. 자산 링크 파일을 가져옵니다. 자산 링크 파일을 가져오려면:

1. 원링크 구성으로 이동하여 앱 링크로 구성된 원링크를 찾습니다.
2. 원링크 URL 끝에 **/.well-known/assetlinks.json**을 추가합니다.
3. 브라우저 주소 표시줄에 원링크를 붙여넣고 Enter 키를 누릅니다. 예:**`<OneLinkSubdomain>`.onelink.me/.well-known/assetlinks.json.** 이렇게 하면 자산 링크 파일이 컴퓨터에 다운로드됩니다. 간단한 텍스트 편집기를 사용하여 열 수 있습니다.
4. 이 자산 링크 파일을 Responsys로 보냅니다. 자세한 내용과 이 파일의 내용에 대한 자세한 내용은 <Anchor target="_blank" href="https://docs.oracle.com/cloud/latest/marketingcs_gs/OMCFB/android/app-links/">이 가이드</Anchor>를 참조하세요.

</Accordion>

<div id="setting-up-your-app" />

## 앱 설정

<div id="step-1-for-android-setting-up-your-app-to-support-app-links" />

<Accordion title="Android에 대한 1단계: 앱 링크를 지원하도록 앱 설정">

<div id="adding-the-click-domain-to-the-activity-in-the-android-manifest" />

#### Android 매니페스트의 활동에 클릭 도메인 추가

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

<div id="setting-up-the-app-to-resolve-click-domains" />

#### 클릭 도메인을 확인하도록 앱 설정

SDK는 캠페인 세부 정보를 얻기 위해 클릭 도메인 뒤에 있는 원링크를 확인해야 합니다. 세부 정보는 `onAppOpenAttribution` 메서드를 통해 반환됩니다.

클릭 도메인을 확인하는 방법:

1. SDK 버전이 4.9.0 이상인지 확인합니다.
2. SDK API `setResolveDeepLinkURLs`에 클릭 도메인을 나열합니다. 이 API는 SDK 초기화 전에 호출해야 합니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/additional-sdk-integration-guide#resolve-wrapped-deep-link-urls">여기</Anchor>에서 SDK 설명서를 참조하세요.  

   ```java
   AppsFlyerLib.getInstance().setResolveDeepLinkURLs("click.example.com");
   ```

   * **중요!** Salesforce와 함께 MI(Movable Ink)를 사용하는 경우 MI 계정 관리자로부터 MI CNAME 및 내부 도메인을 가져와 Salesforce에 대한 클릭 링크 외에도 에 추가해야 합니다. 예를 들어:

     ```java
     AppsFlyerLib.getInstance().setResolveDeepLinkURLs("oracle-click.example.com", "mi.example.com", "example.micpn.com");
     ```

</Accordion>

<div id="step-1-for-ios-setting-up-your-app-to-support-universal-links" />

<Accordion title="iOS에 대한 1단계: 유니버설 링크를 지원하도록 앱 설정">

이 섹션에서는 유니버설 링크를 지원하도록 앱을 설정하는 방법을 설명합니다.

<div id="associating-click-domains-in-xcode" />

#### Xcode에서 클릭 도메인 연결

1. Xcode에서 프로젝트를 클릭합니다.
2. ***기능***을 클릭합니다.[![configure-xcode-deeplinking-domain.png](https://files.readme.io/90d0dcc0eba2d7d081ab7d5d4ea697e9257b9107af463fa8c973169f8a2651db-49839256220433.png)](https://files.readme.io/90d0dcc0eba2d7d081ab7d5d4ea697e9257b9107af463fa8c973169f8a2651db-49839256220433.png)
3. ***연결된 도메인***을 켭니다.
4. + 기호를 클릭하고 클릭 도메인을 추가합니다. 예를 들면 applinks:click.example.com과 같습니다.

</Accordion>

<div id="step-2-setting-up-the-app-to-resolve-click-domains" />

### 2단계: 클릭 도메인을 확인하도록 앱 설정

SDK는 캠페인 세부 정보를 얻기 위해 클릭 도메인 뒤에 있는 원링크를 확인해야 합니다. 세부 정보는 `onAppOpenAttribution` 메서드를 통해 반환됩니다.

클릭 도메인을 확인하려면:

1. SDK 버전이 4.9.0 이상인지 확인합니다.
2. SDK 속성 `resolveDeepLinkURLs`에 클릭 도메인을 나열합니다. 이 속성은 SDK 초기화 전에 설정해야 합니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/additional-sdk-integration-guide#resolve-wrapped-deep-link-urls">여기</Anchor>에서 SDK 설명서를 참조하세요.  

   <Tabs>
   <Tab title="Objective-C">

   ```objectivec
   [AppsFlyerTracker sharedTracker].resolveDeepLinkURLs = @[@"example.com",@"click.example.com"];
   ```

   </Tab>

   <Tab title="Swift">

   ```swift
   AppsFlyerTracker.shared().resolveDeepLinkURLs = ["example.com", "click.example.com"]
   ```

   </Tab>
   </Tabs>

   * **중요!** Salesforce와 함께 MI(Movable Ink)를 사용하는 경우 MI 계정 관리자로부터 MI CNAME 및 내부 도메인을 가져와 Salesforce에 대한 클릭 링크 외에도 에 추가해야 합니다. 도메인 예시:
     * Oracle 도메인: oracle-click.example.com
     * MI CNAME 도메인: mi.example.com
     * MI 내부 도메인: example.micpn.com
3. SDK가 클릭 기록 도메인을 확인할 수 있도록 다음 코드를 추가합니다.  

   <Tabs>
   <Tab title="Objective-C">

   AppDelegate.m에 다음 코드를 추가하세요.

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

<div id="sending-your-first-email" />

## 첫 번째 이메일 보내기

1. 링크 관리 페이지에서(또는 수동으로) 원링크 URL을 생성합니다.
2. 원링크 URL을 생성할 때 모든 파라미터 값을 URL로 인코딩해야 합니다.
3. 다음 매개 변수를 사용하는 것이 좋습니다.
   * pid(미디어 원본) - 이 사용을 나타내는 미디어 원본(예: 이메일)을 사용합니다.
   * c (campaign) - 측정하려는 캠페인의 이름입니다.
   * af\_dp - 사용자를 딥링크하려는 딥링크 URI 체계입니다.
   * af\_web\_dp - 데스크톱에서 링크를 클릭하는 사용자를 리디렉션하는 위치입니다.
   * af\_ios\_url - iOS 장치에서 링크를 클릭하는 앱이 없는 사용자를 리디렉션하는 위치입니다.
   * af\_android\_url - 앱이 없는 사용자를 리디렉션할 위치: Android 기기에서 링크를 클릭합니다.
4. Responsys에서 생성한 이메일에 원링크 URL을 입력합니다. 예시:

   ```http
   <a href="greatapp.onelink.me/abcd/1234567">Download my great app!</a>
   ```

   이 단계에서 Responsys는 위의 링크를 이전 단계에서 설정한 클릭 도메인으로 래핑합니다. 시나리오 : 세 개의 클릭 도메인이 귀하의 원링크 [https://mysubdomain.onelink.me/abCD](https://mysubdomain.onelink.me/abCD)로 리디렉션됩니다. 앱이 사용자의 기기에 설치되어 있는 경우 클릭 도메인은 앱에 딥 링크됩니다.

<div id="note" />

> 📄 **예시**
>
> URL 매개변수는 가독성을 위해 이 예제에서 URL로 인코딩되지 않습니다.
>
> ```http
> https://greatapp.onelink.me/abcd?pid=Email&c=Spring_Newsletter&is_retargeting=true&
> af_dp=testapp://path/to/content&af_web_dp=https://www.example.com/path/to/content&
> af_ios_url=https://www.example.com/path/to/content&af_android_url=https://www.example.com/path/to/content
> ```

<div id="testing-your-links" />

### 링크 테스트

위에서 언급한 모든 필수 단계를 수행하고, 적절한 원링크 URL을 생성하고, 이를 이메일에 넣은 후, 자신에게 테스트 이메일을 보냅니다.

무엇을 기대할 수 있을까요?

앱이 설치되어 있는 경우 앱을 호출해야 합니다. 관련 앱스플라이어 SDK 딥링킹 API가 구현된 경우 관련 콘텐츠에 딥링크되어야 합니다.  
또한 클릭은 제공된 미디어 소스 및 캠페인에 어트리뷰션된 앱스플라이어 대시보드와 Responsys 데이터 모두에 나타나야 합니다.

<div data-zendesk-anchors="prerequisites=%ED%95%84%EC%88%98-%EC%A1%B0%EA%B1%B4 h_01HDNSK7GR33AN2M4GP956S1FD=%ED%95%84%EC%88%98-%EC%A1%B0%EA%B1%B4 setting-up-oracle-responsys-click-domain=oracle-responsys-%ED%81%B4%EB%A6%AD-%EB%8F%84%EB%A9%94%EC%9D%B8-%EC%84%A4%EC%A0%95 h_01HDNSK7GR84QSRTS86GH556WK=oracle-responsys-%ED%81%B4%EB%A6%AD-%EB%8F%84%EB%A9%94%EC%9D%B8-%EC%84%A4%EC%A0%95 step-1-set-up-a-click-domain-in-oracle-responsys=1%EB%8B%A8%EA%B3%84-1%EB%8B%A8%EA%B3%84-oracle-responsys%EC%97%90%EC%84%9C-%ED%81%B4%EB%A6%AD-%EB%8F%84%EB%A9%94%EC%9D%B8-%EC%84%A4%EC%A0%95 h_01HDNSK7GRHYJZSMYCMT9RVEBW=1%EB%8B%A8%EA%B3%84-1%EB%8B%A8%EA%B3%84-oracle-responsys%EC%97%90%EC%84%9C-%ED%81%B4%EB%A6%AD-%EB%8F%84%EB%A9%94%EC%9D%B8-%EC%84%A4%EC%A0%95 step-2-give-responsys-an-aasa-ios-and-an-asset-links-file-android=2%EB%8B%A8%EA%B3%84-2%EB%8B%A8%EA%B3%84-responsys%EC%97%90-aasaios-%EB%B0%8F-%EC%9E%90%EC%82%B0-%EB%A7%81%ED%81%AC-%ED%8C%8C%EC%9D%BCandroid-%EC%A0%9C%EA%B3%B5 h_01HDNSK7GRW57NNXMN1SWFTTFZ=2%EB%8B%A8%EA%B3%84-2%EB%8B%A8%EA%B3%84-responsys%EC%97%90-aasaios-%EB%B0%8F-%EC%9E%90%EC%82%B0-%EB%A7%81%ED%81%AC-%ED%8C%8C%EC%9D%BCandroid-%EC%A0%9C%EA%B3%B5 h_01HDNSK7GR77N60SFVBD57S9GQ=aasa-for-ios h_01HDNSK7GR6ADJCPG63ZVP19NJ=asset-links-for-android setting-up-your-app=%EC%95%B1-%EC%84%A4%EC%A0%95 h_01HDNSK7GRN751HAPPQ3HVRMDG=%EC%95%B1-%EC%84%A4%EC%A0%95 h_01HDNSK7GRHCK378A8XKMK7ZZF=step-1-for-android-setting-up-your-app-to-support-app-links adding-the-click-domain-to-the-activity-in-the-android-manifest=android-%EB%A7%A4%EB%8B%88%ED%8E%98%EC%8A%A4%ED%8A%B8%EC%9D%98-%ED%99%9C%EB%8F%99%EC%97%90-%ED%81%B4%EB%A6%AD-%EB%8F%84%EB%A9%94%EC%9D%B8-%EC%B6%94%EA%B0%80 h_01HDNSK7GRQNQGWXAEGHSTHADH=android-%EB%A7%A4%EB%8B%88%ED%8E%98%EC%8A%A4%ED%8A%B8%EC%9D%98-%ED%99%9C%EB%8F%99%EC%97%90-%ED%81%B4%EB%A6%AD-%EB%8F%84%EB%A9%94%EC%9D%B8-%EC%B6%94%EA%B0%80 setting-up-the-app-to-resolve-click-domains=%ED%81%B4%EB%A6%AD-%EB%8F%84%EB%A9%94%EC%9D%B8%EC%9D%84-%ED%99%95%EC%9D%B8%ED%95%98%EB%8F%84%EB%A1%9D-%EC%95%B1-%EC%84%A4%EC%A0%95 h_01HDNSK7GRP9ND0MHC3ZHD7G8H=%ED%81%B4%EB%A6%AD-%EB%8F%84%EB%A9%94%EC%9D%B8%EC%9D%84-%ED%99%95%EC%9D%B8%ED%95%98%EB%8F%84%EB%A1%9D-%EC%95%B1-%EC%84%A4%EC%A0%95 h_01HDNSK7GRJ682QYAMPB4PSGRZ=step-1-for-ios-setting-up-your-app-to-support-universal-links associating-click-domains-in-xcode=xcode%EC%97%90%EC%84%9C-%ED%81%B4%EB%A6%AD-%EB%8F%84%EB%A9%94%EC%9D%B8-%EC%97%B0%EA%B2%B0 h_01HDNSK7GSRENM232MQ25EB3J3=xcode%EC%97%90%EC%84%9C-%ED%81%B4%EB%A6%AD-%EB%8F%84%EB%A9%94%EC%9D%B8-%EC%97%B0%EA%B2%B0 step-2-setting-up-the-app-to-resolve-click-domains=2%EB%8B%A8%EA%B3%84-%ED%81%B4%EB%A6%AD-%EB%8F%84%EB%A9%94%EC%9D%B8%EC%9D%84-%ED%99%95%EC%9D%B8%ED%95%98%EB%8F%84%EB%A1%9D-%EC%95%B1-%EC%84%A4%EC%A0%95 h_01HDNSK7GSP08G2EQSNVR5G45B=2%EB%8B%A8%EA%B3%84-%ED%81%B4%EB%A6%AD-%EB%8F%84%EB%A9%94%EC%9D%B8%EC%9D%84-%ED%99%95%EC%9D%B8%ED%95%98%EB%8F%84%EB%A1%9D-%EC%95%B1-%EC%84%A4%EC%A0%95 sending-your-first-email=%EC%B2%AB-%EB%B2%88%EC%A7%B8-%EC%9D%B4%EB%A9%94%EC%9D%BC-%EB%B3%B4%EB%82%B4%EA%B8%B0 h_01HDNSK7GSA9VAMTRFCX8SZGSC=%EC%B2%AB-%EB%B2%88%EC%A7%B8-%EC%9D%B4%EB%A9%94%EC%9D%BC-%EB%B3%B4%EB%82%B4%EA%B8%B0 h_01HDNSK7GS8HP7BAA8BYBVBABD=%EC%98%88%EC%8B%9C testing-your-links=%EB%A7%81%ED%81%AC-%ED%85%8C%EC%8A%A4%ED%8A%B8 h_01HDNSK7GSTAJXAP6KGKE9TD8T=%EB%A7%81%ED%81%AC-%ED%85%8C%EC%8A%A4%ED%8A%B8" />
