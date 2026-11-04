---
title: 앱스플라이어와 Adobe Analytics의 연동
metadata:
  keywords:
    - Adobe Analytics
    - Integration
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2017-07-05T07:20:10Z'
  edited_at: '2026-10-14T10:31:59Z'
  id: 115003326706
  locale: ko
  section: Adobe
  section_id: 6551419728657
  url: https://support.appsflyer.com/hc/ko/articles/115003326706
---
> **한눈에 보기:** [Adobe Analytics](http://www.adobe.com/marketing-cloud/web-analytics.html) (구 Omniture)는 써드 파티 소스에 통합할 수 있는 예측 및 실시간 분석 도구 세트입니다. Marketing Reports and Analytics(SiteCatalyst), Ad hoc analysis(Adobe Discover), Insight 애플리케이션을 포함하여 고객과의 상호작용 데이터를 통찰력으로 변환해 비즈니스 활동에 대한 종합적인 시야를 제공합니다.

<div id="overview" />

## 개요

이 연동은 Adobe와 앱스플라이어 사이에 데이터를 양방향으로 흐를 수 있게 구성되어 있습니다. 성공적인 연동을 위해서는 귀사의 앱 내에 코드를 구현해야 합니다. 연동이 성공적으로 완성되기 위해서는 앱스플라이어와 Adobe 양쪽의 요구 조건을 모두 충족해야 합니다.

<div id="setting-up-adobe-analytics-integration" />

## Adobe Analytics 연동 준비하기

Adobe Analytics Report Suite를 활용해 전체 캠페인 성과 분석과 세그먼트 생성을 하고 계시다면, Adobe Analytics와 앱스플라이어의 연동을 통해 앱스플라이어에서 Adobe로 어트리뷰션 데이터가 자동으로 전송되도록 할 수 있습니다.

<div id="prerequisites" />

### 선행 조건:

* Adobe Experience Platform 모바일 SDK 문서 설정하기
* <Anchor target="_blank" href="https://marketing.adobe.com/resources/help/en_US/mcvid/">Marketing Cloud Visitor ID</Anchor> 혹은 Experience Cloud ID 서비스
* 이 연동만을 위해 리포트 스위트마다 사용할 수 있는 세 개의 eVars

<div id="step-1-share-adobe-experience-cloud-id-ecid-marketing-cloud-id-or-visitor-id-with-appsflyer" />

### 1단계: Adobe Experience Cloud ID(ECID, Marketing Cloud ID 또는 Visitor ID)를 앱스플라이어와 공유해주세요.

Adobe Experience Cloud ID를 추출 및 공유하는 방법:

1. <Anchor target="_blank" href="https://developer.adobe.com/client-sdks/documentation/mobile-core/identity/api-reference/#getexperiencecloudid">Adobe SDK가 초기화된 직후 Adobe SDK 방식을 이용해 앱을 업데이트하고 Marketing Cloud Visitor ID를 추출하세요.</Anchor>
2. Adobe Marketing Cloud Visitor ID를 설정하기 위한 앱스플라이어 SDK 메소드 중 하나를 사용하세요:

<div id="setadditionaldata" />

<Accordion title="setAdditionalData">

<Tabs>
<Tab title="안드로이드">

[setAdditionalData 메서드](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata)에 대해 자세히 알아보십시오.

```java
HashMap<String, Object> customData = new HashMap<String,Object>();
customData .put("marketingCloudID", "ADOBE_VISITOR_ID");
AppsFlyerLib.setAdditionalData(customData);
```

</Tab>

<Tab title="iOS">

[setAdditionalData 메서드](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#customdata)에 대해 자세히 알아보십시오.

Objective C

```objectivec
[[AppsFlyerTracker sharedTracker] setAdditionalData:@{
  @"marketingCloudID" : "ADOBE_VISITOR_ID"
}];
```

Swift

```swift
let CustomDataMap: [AnyHashable: Any] = [
  "marketingCloudID" : "ADOBE_VISITOR_ID"
]
AppsFlyerTracker.shared().customData = CustomDataMap
```

</Tab>

<Tab title="Unity">

[setAdditionalData 메서드](https://dev.appsflyer.com/hc/docs/api#setadditionaldata)에 대해 자세히 알아보십시오.

```csharp
Dictionary<string, string> CustomDataMap = new Dictionary<string, string>();
CustomDataMap.Add("marketingCloudID", "ADOBE_VISITOR_ID");
AppsFlyer.setAdditionalData(CustomDataMap);
```

</Tab>
</Tabs>

</Accordion>

<div id="setcustomeruserid" />

<Accordion title="setCustomerUserId">

<Tabs>
<Tab title="안드로이드">

<Anchor target="_blank" href="/marketers/ko/docs/basic-sdk-integration-guide#integrate-unique-identifiers-from-your-bi-system-with-appsflyer">setCustomerUserId</Anchor> <Anchor target="_blank" href="/marketers/ko/docs/basic-sdk-integration-guide#integrate-unique-identifiers-from-your-bi-system-with-appsflyer">방법</Anchor>에 관해 더 알아보세요.

```java
AppsFlyerLib.getInstance().setCustomerUserId("ADOBE_VISITOR_ID");
```

</Tab>

<Tab title="iOS">

<Anchor target="_blank" href="/marketers/ko/docs/basic-sdk-integration-guide#integrate-unique-identifiers-from-your-bi-system-with-appsflyer">setCustomerUserId 메소드</Anchor>에 대해서 자세히 알아보세요.

Objective C

```objectivec
NSString *customerUserID = [AppsFlyerLib shared].customerUserID;
```

Swift

```swift
let customerUserID = AppsFlyerLib.shared().customerUserIDp
```

</Tab>
</Tabs>

</Accordion>

<div id="step-2-configure-adobe-analytics-in-appsflyer" />

### 2단계: 앱스플라이어에서 Adobe Analytics 설정하기

**선행 조건:** 연동을 시작하기 전에, [Adobe Marketing Cloud Visitor ID를 앱스플라이어 SDK에 전달하세요.](/docs/adobe-analytics-integration-with-appsflyer#1단계-adobe-experience-cloud-idecid-marketing-cloud-id-또는-visitor-id를-앱스플라이어와-공유해주세요)

**연동 활성화 또는 편집 방법:**

1. **활성화 방법:** 앱스플라이어에서 측면 메뉴의 **협업** > **파트너 마켓플레이스**를 선택합니다.  
   **편집 방법**: 앱스플라이어의 사이드 메뉴에서 **협업** > 활성 연동을 선택합니다.
2. **Adobe Analytics**를 찾아서 선택하세요.
3. **연동 설정**을 클릭합니다. 연동 설정 페이지로 이동합니다.
4. **연동** 탭에서 연동할 앱을 선택하고  **파트너 활성화** 을 켭니다.  
   **참고:** 적용 시 슬라이더가 켜져 있어야 합니다(활성화)&lt;6> 파트너와 협업하는 동안.
5. **Adobe Analytics SDK**에서, **ADBMobileConfig.XML** 파일의 일부인 **Report\_Suite\_ID**(파랗게 강조)와 **Adobe\_Analytic\_server\_URL**(녹색으로 강조)를 복사하여 앱스플라이어에서 Adobe Analytics 연동 페이지의 해당 필드에 붙여넣으세요.  

   ![](https://files.readme.io/fb46a40178b88dc8f8fb0f9bcce5aa289fc27c2dbf52d1e67783c7b764729f0f-360001063605.png)
6. 저장하기 **연동 설정**.

저장 후, 앱스플라이어는 오가닉 및 논오가닉 인스톨 모두에 대해 Adobe Analytics로 다음과 같은 데이터를 전송합니다.

* Adobe ID (MCVID)
* Report Suite ID & Server URL
* Customer Device ID
* 미디어 소스
* 캠페인 이름

<div id="note" />

> 📘 **참고**
>
> Meta 광고와 X 광고의 이용 약관에 따라, 앱스플라이어는 사용자 개별 데이터를 제삼자에게 공유할 수 없습니다. 즉, Meta 광고 및 X 광고로부터의 인스톨이 오가닉으로 처리됩니다.

<div id="step-3-map-data-to-evars-in-adobe-analytics" />

### 3단계: Adobe Analytics에서 eVars로 데이터 매핑

Adobe Analytics 데이터 커넥터가 지원 중단됨에 따라, 컨텍스트 변수를 eVars로 매핑하기 위한 처리 규칙의 활용이 필요합니다.

[처리 규칙 사용 방법](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/t-processing-rules.html?lang=en)에 관해 자세히 알아보세요.

앱스플라이어 컨텍스트 데이터 변수가 아래와 같이 매핑됩니다:

* MobileAdCampaign(컨텍스트 데이터)
* MobileAdNetwork(컨텍스트 데이터)
* 모바일 광고 제공자(컨텍스트 데이터)

처리 규칙을 통해 앱스플라이어 컨텍스트 데이터 변수의 매핑에 문제가 있다면, 추가적인 지원을 위해 Adobe 계정 팀에 문의해 주세요.

<div id="step-4-optional-set-up-your-marketing-channel" />

### 4단계 [선택 사항]: 마케팅 채널 설정

해당 플랫폼에서 마케팅 채널을 어떻게 설정하는지는 <Anchor target="_blank" href="https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/marketing-channels/c-channels.html">Adobe Analytics 문서</Anchor>를 확인하세요. 식별 규칙을 설정할 때 다음 필드들을 선택하세요:

1. "Adobe의 웹 비콘에 의해 설정된 전환 변수 값": **앱스플라이어** 및 **존재** 선택.
2. "채널을 다음과 같이 식별": **모바일 앱 어트리뷰션** 선택.
3. "채널 값 설정": **앱스플라이어 캠페인** 선택.

<div id="domain-and-security-details" />

## 도메인 및 보안 관련 상세 정보

아래에 도메인 및 보안 문제의 상세 정보를 제공합니다:

1. ANALYTIC\_SERVER\_DOMAIN은 앱의 설정 파일에서 서버 변수로 확인할 수 있습니다. 어트리뷰션 분석을 위한 도메인은 자유롭게 선택 가능합니다. 일반적으로는 Adobe Analytics 수집 서비스의 표준 도메인인 sc.omtrdc.net을 사용합니다. 이는 ADBMobile.config 파일의 애널리틱스(서버) 설정 내에서 확인할 수 있습니다.
2. URL의 프로토콜(HTTP/HTTPS)은 ANALYTIC 서버 도메인이 보안 처리되었는지 여부에 따라 결정됩니다. 올바른 프로토콜 사용이 중요합니다. 설정이 보안 처리되었는지 확인하려면, ADBMobile.config 파일에서 애널리틱스(SSL) 설정이 **true**로 설정되어 있는지를 확인하세요. 연결 상태가 안전하면 HTTPS를, 그렇지 않다면 HTTP를 사용하세요.
3. 리포트 스위트 ID는 앱의 구성 파일에서 **rsids** 변수를 통해 찾을 수 있습니다. 리포트 스위트의 이름은 원하는 대로 지정하실 수 있습니다.
4. 귀사의 구성 파일에서 **offlineEnabled** 설정이 true인 경우에만 ts=`{timestamp}`가 사용됩니다. **offlineEnabled**이 False로 설정되어 있거나 리포트 스위트가 **시간대 기록** 기능을 지원하지 않을 경우, URL에서 해당 파라미터를 제거하세요.

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 h_01HA4ZWDM1MEW2VDFXYMAJ2QE2=%EA%B0%9C%EC%9A%94 setting-up-adobe-analytics-integration=adobe-analytics-%EC%97%B0%EB%8F%99-%EC%A4%80%EB%B9%84%ED%95%98%EA%B8%B0 h_01HA4ZWDM11RJ6GRJ7W8QMFACT=adobe-analytics-%EC%97%B0%EB%8F%99-%EC%A4%80%EB%B9%84%ED%95%98%EA%B8%B0 prerequisite=%EC%84%A0%ED%96%89-%EC%A1%B0%EA%B1%B4 h_01HA4ZWDM1YK58Q56Y0S8PC1E2=%EC%84%A0%ED%96%89-%EC%A1%B0%EA%B1%B4 step-1-share-adobe-experience-cloud-id-ecid-marketing-cloud-id-or-visitor-id-with-appsflyer=1%EB%8B%A8%EA%B3%84-adobe-experience-cloud-idecid-marketing-cloud-id-%EB%98%90%EB%8A%94-visitor-id%EB%A5%BC-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%99%80-%EA%B3%B5%EC%9C%A0%ED%95%B4%EC%A3%BC%EC%84%B8%EC%9A%94 h_01HA4ZWDM1J65D32PVXY0ZD9YV=1%EB%8B%A8%EA%B3%84-adobe-experience-cloud-idecid-marketing-cloud-id-%EB%98%90%EB%8A%94-visitor-id%EB%A5%BC-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%99%80-%EA%B3%B5%EC%9C%A0%ED%95%B4%EC%A3%BC%EC%84%B8%EC%9A%94 h_01HA4ZWDM1RDRDGZ3X7WC0ACV1=setadditionaldata h_01HA4ZWDM1CAXZH7ZNJ0Z37EE1=setcustomeruserid step-2-configure-adobe-analytics-in-appsflyer=2%EB%8B%A8%EA%B3%84-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%97%90%EC%84%9C-adobe-analytics-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 h_01HA4ZWDM26AVEQKC4CXF18D22=2%EB%8B%A8%EA%B3%84-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%97%90%EC%84%9C-adobe-analytics-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 h_01HA4ZWDM23A6BFXDV2JH4NR2J=%EC%B0%B8%EA%B3%A0 step-3-map-data-to-evars-in-adobe-analytics=3%EB%8B%A8%EA%B3%84-adobe-analytics%EC%97%90%EC%84%9C-evars%EB%A1%9C-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%A7%A4%ED%95%91 h_01HA4ZWDM27S52KY36GS1QPKJ5=3%EB%8B%A8%EA%B3%84-adobe-analytics%EC%97%90%EC%84%9C-evars%EB%A1%9C-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%A7%A4%ED%95%91 step-4-%5Boptional%5D-set-up-your-marketing-channel=4%EB%8B%A8%EA%B3%84-%EC%84%A0%ED%83%9D-%EC%82%AC%ED%95%AD-%EB%A7%88%EC%BC%80%ED%8C%85-%EC%B1%84%EB%84%90-%EC%84%A4%EC%A0%95 h_01HA4ZX6FG6RM5JNDKQP6GVAD1=4%EB%8B%A8%EA%B3%84-%EC%84%A0%ED%83%9D-%EC%82%AC%ED%95%AD-%EB%A7%88%EC%BC%80%ED%8C%85-%EC%B1%84%EB%84%90-%EC%84%A4%EC%A0%95 domain-and-security-details=%EB%8F%84%EB%A9%94%EC%9D%B8-%EB%B0%8F-%EB%B3%B4%EC%95%88-%EA%B4%80%EB%A0%A8-%EC%83%81%EC%84%B8-%EC%A0%95%EB%B3%B4 h_01HA4ZWDM2NNFVPP1XYWKPS89A=%EB%8F%84%EB%A9%94%EC%9D%B8-%EB%B0%8F-%EB%B3%B4%EC%95%88-%EA%B4%80%EB%A0%A8-%EC%83%81%EC%84%B8-%EC%A0%95%EB%B3%B4" />
