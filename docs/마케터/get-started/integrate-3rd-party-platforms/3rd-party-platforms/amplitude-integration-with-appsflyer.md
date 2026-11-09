---
title: 앱스플라이어와 Amplitude 연동
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Amplitude
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
  created_at: '2016-08-02T05:18:03Z'
  edited_at: '2026-10-14T10:39:14Z'
  id: 211200306
  locale: ko
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ko/articles/211200306
---
> **한눈에 보기:** 앱스플라이어와 Amplitude를 연동하여 사용자 어트리뷰션 데이터 및 이벤트 분석 정보를 공유하고 유저 인게이지먼트, 리텐션 및 수익에 대한 더 풍부한 인사이트를 확보하세요. 사용 사례 및 분석 정보 필요에 따라 **두 개의 연동 버전—V1 또는 V2** 중에서 선택하십시오.

<div id="about-the-integration" />

## 연동에 대하여

Amplitude는 앱스플라이어 연동 파트너로, 제품, 성장 및 마케팅 팀이 모바일 및 웹에서 사용자 행동을 이해하기 위해 활용하는 제품 분석 플랫폼입니다. 이번 연동은 앱스플라이어가 Amplitude에 설치 후 핵심 이벤트 데이터를 전송할 수 있게 하여 포괄적인 사용자 수준 분석을 가능하게 합니다.

두 개의 Amplitude 연동 버전이 있습니다:

* **Amplitude V1:**  
  이 버전은 Amplitude의 어트리뷰션 API를 사용합니다. 앱스플라이어는 연동이 완료된 후 수집된 설치 데이터를 전송합니다. Amplitude는 광고 ID를 식별자로 사용하며, 72시간 이내에 일치하는 사용자 이벤트가 기록되지 않으면 데이터를 삭제합니다. <Anchor target="_blank" href="https://amplitude.com/docs/apis/analytics/attribution">더 알아보기</Anchor>
* **Amplitude V2 :**  
  이 버전은 Amplitude의 HTTP V2 API를 사용합니다. 앱스플라이어는 연동이 완료된 후 설치 및 인앱 이벤트 데이터를 모두 전송합니다. 식별자에 우선 순위가 부여되며(user\_id and device\_id), 일치하지 않을 경우 새로운 사용자를 생성합니다. <Anchor target="_blank" href="https://amplitude.com/docs/apis/analytics/http-v2">더 알아보기</Anchor>

<span id="h_01JSE81SX1FR182N1CZJ5CQP5N"></span>**<span id="integration-methods"></span>연동 버전:**

| 버전 | 사용된 API | 사용된 식별자 | 이벤트 범위 |
| --- | --- | --- | --- |
| **V1** | 어트리뷰션 API | 광고 ID (AdID) | 인스톨만 |
| **V2** | HTTP V2 API | `user_id`, `device_id` (폴백 로직) | 설치 및 인앱 이벤트 |

<div id="important" />

> 🚧 **중요!**
>
> * Amplitude V1 또는 V2 연동 중 하나를 선택하세요. **두 개의 버전을 동시에 사용하지 마세요** 두 버전을 동시에 사용하면 중복 이벤트가 Amplitude로 전송될 수 있습니다.
> * 일부 미디어 소스는 제3자와의 데이터 공유를 제한합니다. 제한된 이벤트에 대한 포스트백은 설정이 되어 있더라도 해당 파트너에게 전송되지 않습니다.

<div id="prerequisites" />

## 선행 조건

**시작하기 전에**

* 계정이 없으면 Amplitude에 연락하여 계정을 생성하세요.
* Amplitude **V1**과 **V2** 중 사용할 버전을 결정하세요.
* 중복을 방지하기 위해 Amplitude SDK와 앱스플라이어에서 동일한 이벤트를 전송하지 않도록 하세요.
* Amplitude V2 연동에 대한 추가 전제 조건을 참조하세요.

<div id="additional-prerequisites-for-the-amplitude-v2-integration" />

### Amplitude V2 연동을 위한 추가 전제 조건

V2 연동은 다음의 설정이 필요합니다:

* [Amplitude 디바이스 ID](/docs/amplitude-integration-with-appsflyer#amplitude-디바이스-id)
* [고객 사용자 ID](/docs/amplitude-integration-with-appsflyer#고객-사용자-id)
* [Amplitude 세션 ID](/docs/amplitude-integration-with-appsflyer#amplitude-세션-id)

<div id="amplitude-device-id" />

#### Amplitude 디바이스 ID

사용자 수준의 어트리뷰션을 활성화하려면 Amplitude 디바이스 ID를 앱스플라이어 SDK에 전달해야 합니다. 이 값은 각 포스트백과 함께 전송됩니다.

<Tabs>
<Tab title="안드로이드">

```java
AppsFlyerLib.getInstance().setAdditionalData("AmplitudeDeviceId", amplitude.getDeviceId())
```

**언어** Java/Kotlin

관련 문서:  <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference#setadditionaldata">안드로이드 SDK 레퍼런스</Anchor>, <Anchor target="_blank" href="https://amplitude.com/docs/sdks/analytics/android/android-kotlin-sdk#get-device-id">Amplitude</Anchor>

</Tab>

<Tab title="iOS (Objective-C)">

```objc
[[AppsFlyerLib shared] setAdditionalData:@{@"AmplitudeDeviceId": [[Amplitude instance] getDeviceId]}];
```

**언어** Objective-C

**문서:** [iOS SDK 레퍼런스](https://dev.appsflyer.com/hc/docs/ios-sdk-reference#setadditionaldata), <Anchor target="_blank" href="https://amplitude.com/docs/sdks/analytics/ios/ios-sdk#get-device-id">Amplitude</Anchor>

</Tab>

<Tab title="iOS (Swift)">

```swift
AppsFlyerLib.shared().customData = ["AmplitudeDeviceId": Amplitude.instance().getDeviceId()]
```

**언어** Swift

**문서:** [iOS SDK 레퍼런스](https://dev.appsflyer.com/hc/docs/ios-sdk-reference#setadditionaldata), <Anchor target="_blank" href="https://amplitude.com/docs/sdks/analytics/ios/ios-sdk#get-device-id">Amplitude</Anchor>

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> customData = new Dictionary<string, string>();  
customData.Add("AmplitudeDeviceId", Amplitude.getInstance().getDeviceId());  
AppsFlyer.setAdditionalData(customData);
```

**언어** C#

**관련 문서:** [Unity SDK 레퍼런스](https://github.com/AppsFlyerSDK/appsflyer-unity-plugin)

</Tab>

<Tab title="React Native">

```javascript
appsFlyer.setAdditionalData({"AmplitudeDeviceId": amplitude.getDeviceId()},  
(res) => {  
//...  
}  
);
```

**언어** JavaScript

**관련 문서:** [React Native SDK 레퍼런스](https://github.com/AppsFlyerSDK/appsflyer-react-native-plugin)

</Tab>

<Tab title="Cordova">

```javascript
appsFlyer.setAdditionalData({"AmplitudeDeviceId": amplitude.getDeviceId()});
```

**언어** JavaScript

**관련 문서:** 해당 없음

</Tab>

<Tab title="Flutter">

```dart
var data = {"AmplitudeDeviceId": amplitude.getDeviceId()};  
appsFlyerSdk.setAdditionalData(data);
```

**언어** Dart

**관련 문서:** [Flutter SDK 레퍼런스](https://github.com/AppsFlyerSDK/appsflyer-flutter-plugin)

</Tab>
</Tabs>

<div id="customer-user-id" />

#### 고객 사용자 ID

고객 사용자 ID(CUID)를 설정합니다. 이는 일반적으로 사용자 등록 시 앱 소유자가  
생성하고 설정하는 고유의 식별자입니다. <Anchor target="_blank" href="/marketers/ko/docs/customer-user-id-field-cuid?utm_source=chatgpt.com">더 알아보기</Anchor>

<div id="amplitude-session-id" />

#### Amplitude 세션 ID

Amplitude 세션 ID를 설정하고 앱스플라이어에 전달합니다(선택 사항). <Anchor target="_blank" href="https://amplitude.com/docs/data/sources/instrument-track-sessions">더 알아보기</Anchor>

<Tabs>
<Tab title="안드로이드">

```java
AppsFlyerLib.getInstance().setAdditionalData("AmplitudeSessionId", amplitude.getSessionId())
```

**언어** Java/Kotlin

**관련 문서:** [안드로이드 SDK 레퍼런스](https://dev.appsflyer.com/hc/docs/android-sdk-reference#setadditionaldata)

</Tab>

<Tab title="iOS (Objective-C)">

```objc
[[AppsFlyerLib shared] setAdditionalData:@{@"AmplitudeSessionId": [[Amplitude instance] getSessionId]}];
```

**언어** Objective-C

**문서:** [iOS SDK 레퍼런스](https://dev.appsflyer.com/hc/docs/ios-sdk-reference#setadditionaldata)

</Tab>

<Tab title="iOS (Swift)">

```swift
AppsFlyerLib.shared().customData = ["AmplitudeSessionId": Amplitude.instance().getSessionId()]
```

**언어** Swift

**문서:** [iOS SDK 레퍼런스](https://dev.appsflyer.com/hc/docs/ios-sdk-reference#setadditionaldata)

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> customData = new Dictionary<string, string>();  
customData.Add("AmplitudeSessionId", Amplitude.getInstance().getSessionId());  
AppsFlyer.setAdditionalData(customData);
```

**언어** C#

**관련 문서:** [Unity SDK 레퍼런스](https://github.com/AppsFlyerSDK/appsflyer-unity-plugin)

</Tab>

<Tab title="React Native">

```javascript
appsFlyer.setAdditionalData({"AmplitudeSessionId": amplitude.getSessionId()},  
(res) => {  
//...  
}  
);
```

**언어** JavaScript

**관련 문서:** [React Native SDK 레퍼런스](https://github.com/AppsFlyerSDK/appsflyer-react-native-plugin)

</Tab>

<Tab title="Cordova">

```javascript
appsFlyer.setAdditionalData({"AmplitudeSessionId": amplitude.getSessionId()});
```

**언어** JavaScript

**관련 문서:** 해당 없음

</Tab>

<Tab title="Flutter">

```dart
var data = {"AmplitudeSessionId": amplitude.getSessionId()};  
appsFlyerSdk.setAdditionalData(data);
```

**언어** Dart

**관련 문서:** [Flutter SDK 레퍼런스](https://github.com/AppsFlyerSDK/appsflyer-flutter-plugin)

</Tab>
</Tabs>

<div id="set-up-the-integration" />

## 연동 설정

**연동을 설정하려면:**

1. 앱스플라이어에서 **협업**>**파트너 마켓플레이스**로 이동합니다.
2. Amplitude V1 연동을 설정하려면 **Amplitude V1**(기술 파트너)을 선택합니다.  
     
   <Image alt="Amplitude V1 doctored.png" src="https://files.readme.io/71721bb1a48dda061ce2a099522edf9baed39ef2d67edad8ac14277b42cd2d70-36713632837777.png" width="511px" /> 선택  
     
     
   Amplitude V2 연동을 설정하려면 **Amplitude V2** (기술 파트너)을 선택합니다.   
     
   <Image alt="Amplitude V2.png" src="https://files.readme.io/4bbf57727a2b6e16e5205505b459a78f8642f02d1bb1c4e8f72e26b3bd9e1bd3-36713631187857.png" width="503px" /> 선택
3. Amplitude 버전을 선택한 후 **연동 설정**을 클릭합니다.  
     
   <Image align="center" alt="Click set up integration.png" src="https://files.readme.io/c13fef10fb4cf0ea12f44d56f8c3b64936376ce181a1d12c9f096ad6103c29a6-36713632857617.png" />
4. 연동 탭에서
   * 앱을 선택합니다.
   * **파트너 활성화** 토글을 켭니다.  
       
     <Image align="center" alt="파트너 활성화 blurred.png" src="https://files.readme.io/5e0e7ae537cd89b2c561c8561de9ebc160f6d6eb0fedc5c7ba0c761ddb73632a-36713631194641.png" width="521px" />
5. 나머지 탭에서 구성을 완료하십시오:

<div id="integration-tab" />

<Accordion title="연동 탭">

연동 탭은 아래와 같이 다양한 섹션으로 나누어져 있습니다.

<div id="activate-partner" />

### 파트너 활성화

**첫 번째 방문** 시에 **파트너 활성화**를 켜서 연동 탭의 파라미터 설정을 활성화해야 합니다. 파트너와 작업하는 동안에는 토글이 켜져 있어야 합니다.  
<Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">파트너 활성화</Anchor>에 대해 더 알아보십시오.

<div id="general-settings" />

### 일반 설정

<div id="advanced-data-sharing" />

#### 고급 데이터 공유

Amplitude와 추가 설치 정보를 공유하려면 **고급 데이터 공유**를 켭니다. 활성화되면, Amplitude는 설치(인앱 이벤트 제외)에 대해 Amplitude 속성에 매핑된 데이터를 수신하게 됩니다.

| Amplitude 속성 | 앱스플라이어 데이터 포인트 |
| --- | --- |
| sub\_publisher | af\_siteid |
| network\_name | pid |
| adgroup\_name | af\_adset |
| creative\_name | af\_ad\_id |
| installed\_at | install\_timestamp |
| search\_term | af\_keywords |
| channe | af\_channel |
| user\_id | af\_customer\_user\_id |
| af\_sub1 | af\_sub1 |
| af\_sub2 | af\_sub2 |
| af\_sub3 | af\_sub3 |
| af\_sub4 | af\_sub4 |
| af\_sub5 | af\_sub5 |
| app\_version | app\_version |

<div id="amplitude-eu-data-center" />

#### Amplitude EU 데이터 센터

**Amplitude EU 데이터 센터**가 설정되지 않은 경우, 인스톨 포스트백은 미국 데이터 센터로 전송됩니다.  
Amplitude의 EU 데이터 센터로 설치 포스트백을 보내려면 Amplitude EU 데이터 센터를 켜십시오.

#### API Key

Amplitude는 고유한 API 키를 통해 앱스플라이어와 연결됩니다. 아직 키가 없는 경우, 연동을 위해서는 Amplitude에서 키를 가져오거나 아래의 단계를 수행하십시오.

<span id="obtaining-the-api-key-from-amplitude"></span>**Amplitude에서 API 키 가져오기**

**참고**: **일러두기**: Amplitude에서 어드민 또는 관리자 역할이 있는 사용자만 API 키에 액세스할 수 있습니다.

1. Amplitude 계정에 로그인합니다.
2. 페이지 오른쪽 상단에서 설정 > **조직 설정** 아이콘을 클릭합니다.  
   Amplitude
3. 프로젝트를 클릭하고 앱스플라이어로 데이터를 전송할 **프로젝트**를 선택합니다.    
   Amplitude
4. **프로젝트** 탭에서 API 키를 복사합니다.  
   Amplitude
5. 앱스플라이어 대시보드에서 Amplitude 설정을 진행합니다.

<div id="default-postbacks" />

### 기본 포스트백

앱스플라이어는 사용자 인스톨 후 자동 포스트백을 전송할 수 있습니다. 이 섹션에서는 각 이벤트별로 포스트백을 전송할 사용자 소스를 설정합니다. <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#default-postbacks">기본 포스트백</Anchor>에 대해 자세히 알아보세요.

<div id="in-app-event-settings" />

### 인앱 이벤트 설정

* API 키를 입력합니다.
* **Amplitude 데이터 센터**가 설정되지 않은 경우, 인앱이벤트 포스트백은 미국 데이터 센터로 전송됩니다.  
  **Amplitude의 EU 데이터 센터에 인앱이벤트 포스트백을 보내려면 Amplitude 데이터 센터를 켜십시오.**

설정을 저장하면 앱스플라이어는 다음과 같은 데이터를 Amplitude로 전송합니다:

* 디바이스 ID(IDFV/Google 광고 ID)
* 미디어 소스
* 캠페인 이름

iOS 디바이스의 IDFA 전송은 <Anchor target="_blank" href="/marketers/ko/docs/apply-aggregated-advanced-privacy-framework">ATT에 대한 사용자 동의 및 고급 개인정보 보호 정책 설정</Anchor>에 따릅니다.

<div id="in-app-event-postbacks" />

### 인앱 이벤트 포스트백

Amplitude<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">로 인앱 이벤트 포스트백 전송을 구성합니다</Anchor>.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="어트리뷰션 링크 탭">

Amplitude에 대해 어트리뷰션 링크를 사용할 수 없습니다.

</Accordion>

<div id="cost-tab" />

<Accordion title="비용 탭">

이 파트너와의 연동에서 비용 데이터는 지원되지 않습니다.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="광고 수익 탭">

이 파트너와의 연동에서 광고 수익은 지원되지 않습니다.

</Accordion>

<div id="permissions-tab" />

<Accordion title="권한 탭">

Amplitude에 대한 권한이 제공되지 않습니다.

</Accordion>

<div id="viewing-attribution-data-in-the-amplitude-console" />

## Amplitude 콘솔에서 어트리뷰션 데이터 보기

앱스플라이어에서 Amplitude로 전송된 어트리뷰션 데이터는 대시보드에 **[앱스플라이어]** 접두사가 붙어 이벤트와 속성으로 표시됩니다.

<Image align="center" alt="amplitude-properties.png" src="https://files.readme.io/bf52831ea6060172ce251136f47962ffb7f1ec9ffce13b9e35c614c4178e77f1-360009623597.png" />

<div id="important-1" />

> 🚧 **중요!**
>
> 경우에 따라 Amplitude는 앱스플라이어에서 전송된 데이터를 “차단됨"으로 표시합니다. Amplitude에서 앱스플라이어 데이터를 볼 수 없는 경우, 차단된 이벤트로 정의되어 있는지 확인하십시오.![amplitude-blocked-data.png](https://files.readme.io/1d1a327cca509f002110d6908087c0b4f628e8643eee1a96aa7bdb018d96734e-51912986509329.png)

<div id="sending-amplitude-events-to-appsflyer" />

## Amplitude 이벤트를 앱스플라이어로 전송하기

이 연동은 서버-투-서버 API를 통해 Amplitude 이벤트를 앱스플라이어로 전송할 수 있도록 합니다. 자세한 사항은 <Anchor target="_blank" href="https://www.docs.developers.amplitude.com/data/destinations/appsflyer/">Amplitude 관련 문서</Anchor>를 참조하십시오.

<div data-zendesk-anchors="about-the-integration=%EC%97%B0%EB%8F%99%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC h_01JSE81SX1B1RH978Y08W1XXX8=%EC%97%B0%EB%8F%99%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC h_01JSEAMM69J9CD7E32M4NKXRR6=%EC%A4%91%EC%9A%94 set-up-the-integration=%EC%84%A0%ED%96%89-%EC%A1%B0%EA%B1%B4 h_01JSE958V510B9P6VEQTXC55S7=%EC%84%A0%ED%96%89-%EC%A1%B0%EA%B1%B4 additional-prerequisites-for-the-v2-integration=amplitude-v2-%EC%97%B0%EB%8F%99%EC%9D%84-%EC%9C%84%ED%95%9C-%EC%B6%94%EA%B0%80-%EC%A0%84%EC%A0%9C-%EC%A1%B0%EA%B1%B4 h_01JSKEMMEB00PERVQWPYNF5V2E=amplitude-v2-%EC%97%B0%EB%8F%99%EC%9D%84-%EC%9C%84%ED%95%9C-%EC%B6%94%EA%B0%80-%EC%A0%84%EC%A0%9C-%EC%A1%B0%EA%B1%B4 amplitude-device-id=amplitude-%EB%94%94%EB%B0%94%EC%9D%B4%EC%8A%A4-id h_01JSKFH7KPSE5P0CRPVJ3FJ2WN=amplitude-%EB%94%94%EB%B0%94%EC%9D%B4%EC%8A%A4-id customer-user-id=%EA%B3%A0%EA%B0%9D-%EC%82%AC%EC%9A%A9%EC%9E%90-id h_01JSKFK4BFH3PP98XAZ0W8GG11=%EA%B3%A0%EA%B0%9D-%EC%82%AC%EC%9A%A9%EC%9E%90-id amplitude-session-id=amplitude-%EC%84%B8%EC%85%98-id h_01JSKFQXPPJVCW68C4H9B4EJ76=amplitude-%EC%84%B8%EC%85%98-id set-up-the-integration::45aa5acf=%EC%97%B0%EB%8F%99-%EC%84%A4%EC%A0%95 h_01JSKFQAZ8Q76KF1JJKZTAPVBQ=%EC%97%B0%EB%8F%99-%EC%84%A4%EC%A0%95 h_01HNSS4TXFFTZGZRZ6ZTAWNN6N=integration-tab activate-partner=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 01H8KPA9JKDRA680Y0WPZ172EM=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 general-settings=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 01H8KPA9JKF4VCA4S22SYT40WT=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 advanced-data-sharing=%EA%B3%A0%EA%B8%89-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B3%B5%EC%9C%A0 01H8KPA9JKJ2XN1AEPV74QVJYZ=%EA%B3%A0%EA%B8%89-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B3%B5%EC%9C%A0 amplitude-data-center=amplitude-eu-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%84%BC%ED%84%B0 01H8KPA9JKP0T0FDND97VA23EY=amplitude-eu-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%84%BC%ED%84%B0 01H8KPA9JKDYDPDGRXZSH2BAV8=api-key 01H8KPA9JK510YKV47816DT7E7=obtaining-the-api-key-from-amplitude default-postbacks=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 01H8KRBGYQ973CT3H8GHZ8R0BH=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 inapp-event-settings=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95 01H8KPA9JKM4S79160BEYN3B6V=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95 inapp-event-postbacks=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 01H8KSQ76XE9Z191P1RMANF6EQ=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 01H8KPA9JK4D6XX55Q55TBF4QN=attribution-link-tab 01H8KPA9JKK04NNDZA0XTSSWM5=cost-tab 01H8KPA9JK6X04T661D6YBHTVC=ad-revenue-tab 01H8KPA9JKG1VQJJBNFM6Q985X=permissions-tab viewing-attribution-data-in-the-amplitude-console=amplitude-%EC%BD%98%EC%86%94%EC%97%90%EC%84%9C-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B8%B0 01H8KPA9JK75TA0H8T4P65BMSE=amplitude-%EC%BD%98%EC%86%94%EC%97%90%EC%84%9C-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B8%B0 01H8KPA9JK2B4MR26GJZEZJSVT=%EC%A4%91%EC%9A%94-1 sending-amplitude-events-to-appsflyer=amplitude-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EB%A5%BC-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EB%A1%9C-%EC%A0%84%EC%86%A1%ED%95%98%EA%B8%B0 h_01HPYFZDX1WWDWJEBZ4DK706B4=amplitude-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EB%A5%BC-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EB%A1%9C-%EC%A0%84%EC%86%A1%ED%95%98%EA%B8%B0" />
