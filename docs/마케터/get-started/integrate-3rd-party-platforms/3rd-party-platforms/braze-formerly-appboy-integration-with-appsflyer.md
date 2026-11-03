---
title: Braze(이전 Appboy)와 앱스플라이어 연동
metadata:
  keywords:
    - Appboy
    - Advertisers
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2017-03-30T08:39:03Z'
  edited_at: '2026-10-14T10:32:13Z'
  id: 115001603343
  locale: ko
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ko/articles/115001603343
---
> **요약:** 앱스플라이어의 연동 파트너인 Braze는 마케팅, 성장 및 인게이지먼트 팀을 위한 라이프사이클 인게이지먼트 플랫폼을 제공합니다. 이 플랫폼을 통해 마케터가 대규모로 고객과 직접 연결하여 깊은 인게이지먼트와 ROI(투자수익률)를 주도할 수 있습니다. 우리 플랫폼의 중심은 고객의 단일 보기를 제공하는 종합적인 사용자 프로필입니다.

<Anchor target="_blank" href="https://www.braze.com/">braze.com</Anchor>에서 더 보기.

> 🚧 **Important!**
>
> <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions#미디어-소스-제한">일부 매체 소스</Anchor>는 제3자와 데이터 공유를 제한합니다. 따라서 포스트백 전송 설정에 관계없이 제한된 이벤트 포스트백은 이 파트너에게 전송되지 않습니다.

## 연동 개요

아래 지침에 따라 Braze와의 연동을 구성하십시오.

최소 요구사항 - 앱스플라이어 SDK:

* <Anchor target="_blank" href="/marketers/ko/docs/sdk-integration-overview">안드로이드</Anchor> (안드로이드 SDK – 버전 2.3.1.18 및 이상)
* <Anchor target="_blank" href="/marketers/ko/docs/sdk-integration-overview">iOS</Anchor>

안드로이드에서 Braze와 연동하려면 Braze <Anchor target="_blank" href="https://www.braze.com/docs/partners/advertising_technologies/attribution/appsflyer/#integration">디바이스 ID</Anchor> (Braze 고유 유저 식별자)가 앱스플라이어 안드로이드 SDK에 포함되어 있어야 합니다. 이 매개변수는 모든 포스트백과 함께 전송되며 각 유저를 식별할 수 있게 합니다. 이를 수행하려면 귀사의 앱 코드에 다음 문자열을 삽입해야 합니다.

> 📘 **Important Note**
>
> 코드 라인이 올바른 위치에 삽입되었는지 확인하십시오 - Braze SDK가 실행된 후 앱스플라이어 SDK 초기화 코드 이전에 삽입해야 합니다 (안드로이드 SDK 연동 가이드의 SDK 초기화 섹션 참조).

<Tabs>
<Tab title="안드로이드">

```java
HashMap<String, Object> customData = new HashMap<String,Object>();
String deviceId =(Braze.getInstance(MyActivity.this).getDeviceId());
customData.put("brazeCustomerId", deviceId);
AppsFlyerLib.getInstance().setAdditionalData(customData);
```

</Tab>

<Tab title="iOS">

<div id="swift" />

#### Swift

완료 핸들러가 있는 API와 새로운 Swift 동시성 지원을 사용하는 API 두 가지가 있습니다. 둘 다 같은 결과를 생성하며 사용할 API는 상황에 따라 다릅니다.

**Swift 완료 핸들러**

```swift
let configuration = Braze.Configuration(
    apiKey: "<BRAZE_API_KEY>",
    endpoint: "<BRAZE_ENDPOINT>")
configuration.useUUIDAsDeviceId = false
let braze = Braze(configuration: configuration)
braze.deviceId {
    brazeDeviceId in
    AppsFlyerLib.shared().customData = [“brazeDeviceId”: brazeDeviceId]
}
```

**Swift await**

```swift
let configuration = Braze.Configuration(
    apiKey: "<BRAZE_API_KEY>",
    endpoint: "<BRAZE_ENDPOINT>")
configuration.useUUIDAsDeviceId = false
let braze = Braze(configuration: configuration)
let brazeDeviceId = await braze.deviceId()
AppsFlyerLib.shared().customData = ["brazeDeviceId": brazeDeviceId]
```

#### Objective-C

```objc
BRZConfiguration *configurations = [[BRZConfiguration alloc] initWithApiKey:@"BRAZE_API_KEY" endpoint:@"BRAZE_END_POINT"];
[configurations setUseUUIDAsDeviceId:NO];
Braze *braze = [[Braze alloc] initWithConfiguration:configurations];
[braze deviceIdWithCompletion:^(NSString * _Nonnull brazeDeviceId) {
    NSLog(@">>[BRZ]: %@", brazeDeviceId);
    [[AppsFlyerLib shared] setAdditionalData:@{
        @"brazeDeviceId": brazeDeviceId
    }];
}];
```

</Tab>

<Tab title="유니티">

```csharp
Appboy.AppboyBinding.getDeviceID()
Dictionary<string, string> customData = new Dictionary<string, string>();
customData.Add("brazeCustomerId", Appboy.AppboyBinding.getDeviceId());
AppsFlyer.setAdditionalData(customData);
```

</Tab>
</Tabs>

## Braze 설정

**전제 조건:** 연동 설정 전에 <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations#contact-details">파트너에게 연락</Anchor>하여 계정을 개설하세요.

**연동 활성화 또는 편집 방법:**

1. To activate:연동 활성화 방법: 앱스플라이어의 사이드 메뉴에서협업<strong>></strong>파트너 마켓플레이스를 선택합니다.  
   <strong>편집 방법:</strong> 앱스플라이어의 사이드 메뉴에서 <strong>협업</strong>> 활성화된 연동을 선택합니다.
2. 파트너를 검색하고 선택합니다.
3. **연동 설정**을 클릭하십시오. 연동 설정 페이지로 이동합니다.
4. **연동** 탭에서 연동할 앱을 선택하고 **파트너 활성화**를 켭니다.  
   **참고: 파트너와의 작업 동안 토글이 활성화되어 있어야 합니다<Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">(활성화됨)</Anchor>.**
5. 아래 설명된 대로 관련 탭을 사용하여 설정을 완료하십시오.

<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">여기</Anchor>를 클릭하여 파트너 설정 창 헤더에 대한 자세한 설명을 확인하십시오.

<div id="integration-tab" />

<Accordion title="연동 탭">

연동 탭은 아래와 같이 다양한 섹션으로 나누어져 있습니다.

### 파트너 활성화

**처음 방문**시, 연동 탭 파라미터 설정을 활성화하려면 *파트너를 활성화해야 합니다*. 파트너와 작업하는 동안에는 토글이 켜져 있어야 합니다.  
파트너 활성화에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">여기</Anchor>를 클릭하십시오.

### 일반 설정

Braze는 고유한 API 키와 REST 엔드포인트를 통해 앱스플라이어와 연동됩니다.

**Braze의 API 키와 REST 엔드포인트를 가져오는 방법:**

1. 귀사의 Braze 계정에서 **기술** **파트너** 메뉴의 **어트리뷰션**으로 이동합니다.
2. **앱스플라이어**를 선택합니다.  

   ![braze-af-API-key.png](https://files.readme.io/db96e8b5e2363f5250c6c1146a1f7a15e1ed6457fe4543dbe649f8818bb5db78-360017328637.png)
3. **인스톨 어트리뷰션용 데이터 가져오기**에서 'APIKey 생성'을 클릭합니다.
4. 발생된 API 키와 REST 엔드포인트를 복사합니다.
5. 앱스플라이어에서 Braze API 키와 REST 엔드포인트를 입력합니다.  

   ![Braze_msc_new_2.png](https://files.readme.io/b13aba84c394c0b4603e0aad2edd723525dadf204250349620b571bc47b0ba9d-360001907229.png)
6. **저장하고 닫기**를 클릭합니다.

설정을 저장하면, 앱스플라이어는 모든 오가닉 및 논오가닉 인스톨에 대해 다음 데이터를 Braze로 보냅니다:

* Braze Dev\_ID
* 미디어 소스
* 캠페인 이름
* 광고 그룹 이름
* 광고 이름

### 기본 포스트백

앱스플라이어는 Braze 사용자 인스톨에 자동 포스트백을 발송할 수 있습니다. 이 섹션을 사용하여 이러한 포스트백 전송을 정의합니다.

![Swrve_msc_new_4.png](https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png)

앱을 다운로드한 모든 사용자에 대해 Braze로 포스트백을 발송하려면 **모든 파트너 또는 오가닉에 어트리뷰션된 이벤트**를 선택하십시오.

**저장**을 클릭합니다.

> 📘 **Note**
>
> 모든 이벤트는 앱스플라이어에서 전송되지만, 오가닉 인스톨은 Braze에서 집계되지 않기 때문에 Braze API에서 무시됩니다.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="어트리뷰션 링크 탭">

Braze에서는 어트리뷰션 링크를 사용할 수 없습니다.

</Accordion>

<div id="cost-tab" />

<Accordion title="비용 탭">

이 파트너와 연동 시 비용 데이터는 지원되지 않습니다.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="광고 수익 탭">

이 파트너와 연동 시 광고 수익은 지원되지 않습니다.

</Accordion>

<div id="permissions-tab" />

<Accordion title="권한 탭">

Braze에서는 권한 설정을 사용할 수 없습니다.

</Accordion>

## Braze에서 사용자 어트리뷰션 데이터 보기

Braze 대시보드의 인스톨 어트리뷰션 필터를 사용하여 사용자 기반을 어트리뷰션 데이터로 분류할 수 있습니다.

또한, 특정 사용자에 대한 어트리뷰션 데이터는 Braze 대시보드의 각 사용자 프로필에서 확인할 수 있습니다.

<div data-zendesk-anchors="h_01H9FK453A9852FTMBM9T0YP7B=important integration-overview=%EC%97%B0%EB%8F%99-%EA%B0%9C%EC%9A%94 h_01H9FK453A9W5DCPR4X8PR06MZ=%EC%97%B0%EB%8F%99-%EA%B0%9C%EC%9A%94 h_01H9FK453ANSTRYM8V8YXVTS2M=important-note h_01H9FK453AFZA6TS3DYWN2V65T=swift setting-up-braze=braze-%EC%84%A4%EC%A0%95 h_01H9FK453AWXF006KEVKD797QF=braze-%EC%84%A4%EC%A0%95 h_01H9FK453A4RFFH84JHWPV0STH=integration-tab activate-partner=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 h_01H9FK453AVK4YKF41FEP0YRJN=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 general-settings=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 h_01H9FK453AG6AXA7J43X6NGZT1=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 default-postbacks=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01H9FK453ASAKVHT7GV8BG56YS=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01H9FK453ARG95477MA92RA91D=note h_01H9FK453A2W3HWEY0FBM1BZXR=attribution-link-tab h_01H9FK453AQ7MTMDHYNZQRAH7R=cost-tab h_01H9FK453AVQDFQ4K69GFTTTJ5=ad-revenue-tab h_01H9FK453AP7KZDQJCBAPTYCX8=permissions-tab viewing-user-attribution-data-in-braze=braze%EC%97%90%EC%84%9C-%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B8%B0 h_01H9FK453AQXG7NNT2841686MJ=braze%EC%97%90%EC%84%9C-%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B8%B0" />
