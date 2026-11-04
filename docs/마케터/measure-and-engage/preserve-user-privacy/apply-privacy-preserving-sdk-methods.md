---
title: SDK의 개인 정보 보호 방법
metadata:
  keywords:
    - Advertisers
    - coppa
    - opt-out
    - opt out
    - consent management
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2018-08-20T11:14:36Z'
  edited_at: '2026-10-14T10:33:18Z'
  id: 360001422989
  locale: ko
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/ko/articles/360001422989
---
> **한눈에 보기:** 요약: 앱스플라이어 SDK를 통해 사용할 수 있는 하나 이상의 방법으로 사용자의 개인 정보를 보호하십시오.

<div id="note" />

> 📘 **참고사항**
>
> 이 도움말에 제시된 정보는 앱 개발자가 앱 소유자, 광고 네트워크 및 소셜 네트워크와의 사용자 관련 데이터 공유를 제어하는 데 사용할 수 있는 방법에 대한 통찰력을 제공하기 위한 것입니다. **이 문서는 COPPA 또는 GDPR과 같은 개인 정보 보호 규정 또는 특정 개인 정보 보호 규정 준수에 대한 지침을 포함하거나 구성하지 않습니다.**

앱스플라이어 SDK는 앱 소유자에게 사용자 개인 정보를 보호하고 데이터를 제어할 수 있는 여러 가지 방법을 제공합니다. 이 글에서는 이러한 방법을 살펴보고 이러한 방법이 사용자 데이터에 미치는 영향과 어트리뷰션을 허용하면서 사용자 개인 정보를 보호하는 데 사용하는 방법을 평가합니다.

어떤 옵션을 사용할지 고려한 후 개발자 허브의 구현 정보를 개발자와 공유하세요.

각 방법에 대해 논의해 보겠습니다.

<div id="use-start-and-stop-methods" />

## start 및 stop 메서드 사용

SDK는 메서드가 호출된 후 `start`startstart 에만 앱스플라이어에 인스톨 및 인앱 이벤트를 전송합니다. 호출 이전의 start 이벤트는 SDK에서 보고되지 않습니다. 비슷한 방식으로, 메서드를 호출하여 stop 호출이 start 이후에 취소되면 그 이후에는 이벤트가 전송되지 않습니다.

<div id="impact-on-attribution" />

### 어트리뷰션에 미치는 영향

다음과 같은 경우에는 어트리뷰션이 발생하지 **않습니다** .

* `stop`stopstop 이 메서드는 이전 시작을 되돌리기 위해 호출됩니다.

<div id="common-use-cases" />

### 일반적인 사용 사례

| 적용 사례 | 설명 |
| --- | --- |
| 시작 시 옵트인(opt-in) 또는 옵트아웃(opt-out) | 사용자가 첫 번째 실행에서 데이터 공유에 동의한 후 호출 `start`startstart 합니다.  <br />사용자가 데이터 공유에 동의하지 않는 경우start 전혀. |
| 세션 옵트아웃 | 모든 앱 세션에서 동의를 구하고 그에 따라 전화를 걸거나 전화를 걸 `start`startstart 지 않습니다. |
| 일회성 옵트아웃(사용자가 옵트인한 후 옵트아웃하기로 결정한 경우). | SDK가 추가 이벤트를 보내지 못하도록 하려면 호출 `stop`stopstop 합니다. |

<div id="developer-reference" />

### 개발자 참조

start 및 stop 메서드를 사용하는 방법에 대한 개발자 참조 및 설명서는 다음을 참조하세요.

<Tabs>
<Tab title="안드로이드">

[start를 사용하여 설치 이벤트만 공유합니다.](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-android#use-start-to-share-only-the-install-event)

</Tab>

<Tab title="iOS">

[start를 사용하여 설치 이벤트만 공유합니다.](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-ios#use-start-to-share-only-the-install-event)

</Tab>
</Tabs>

<div id="prevent-sharing-data-with-networks" />

## 네트워크와 데이터 공유 금지

광고 네트워크 또는 자체 보고 네트워크(SRN)와 통합할 때 해당 파트너와 사용자 수준 정보를 공유하거나 공유하지 않도록 선택할 수 있습니다.

이 방법을 사용하면 앱스플라이어는 포스트백, API, 로데이터 리포트 등을 포함한 모든 수단을 통해 제외된 파트너와의 사용자 데이터 공유를 비활성화합니다.

<div id="impact-on-attribution-1" />

### 어트리뷰션에 미치는 영향

* 제외된 광고 네트워크 **(비 SRN)** 의 설치는 앱스플라이어에 어트리뷰션되지만, **광고 네트워크** 에는 어떤 형태나 방식으로도 통지되지 않습니다.
* **제외된** **SRN** 의 인스톨은 어트리뷰션되지 않으며 해당 데이터는 연동 파트너와 공유되지 않습니다.

  <div id="note-1" />

  > 📘 **참고사항**
  >
  > 앱스플라이어는 데이터 가져오기에서 제외된 SRN에 대한 인게이지먼트 데이터를 어트리뷰션할 수 없습니다.


<div id="developer-reference-1" />

### 개발자 참조

제3자와의 데이터 공유를 방지하는 방법에 대한 개발자 참조 및 문서는 다음을 참조하세요.

<Tabs>
<Tab title="안드로이드">

[제3자와의 데이터 공유 방지](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-android#prevent-sharing-data-with-third-parties)

</Tab>

<Tab title="iOS">

[제3자와의 데이터 공유 방지](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-ios#prevent-sharing-data-with-third-parties)

</Tab>
</Tabs>

<div id="anonymize-user-information" />

## 사용자 정보 익명화

이 방법을 사용하여 앱스플라이어에 모든 사용자 식별 정보를 제거하도록 지시하도록 SDK를 `anonymizeUser`anonymizeUseranonymizeUser 구성할 수 있습니다. 이 경우 SDK는 앱스플라이어로 인스톨 및 인앱 이벤트를 전송하며, 앱스플라이어에서 모든 식별 정보가 삭제되거나 해시됩니다.

다음 이미지는 익명화(삭제 및 해싱) 후 원시 데이터의 예제 행을 보여줍니다.

[altalt](https://support.appsflyer.com/hc/article_attachments/51858190977297)

<div id="impact-on-attribution-2" />

### 어트리뷰션에 미치는 영향

모든 인앱이벤트는 대시보드에 따라 오가닉으로 계산되거나 완전히 무시됩니다.

<div id="note-2" />

> 👍 **팁**
>
> 인스톨 이벤트를 어트리뷰션하려면 SDK가 `anonymizeUser`anonymizeUseranonymizeUser 앱스플라이어에 인스톨 이벤트를 전송했는지 확인한 후에만 함수를 호출하십시오. 이 흐름은 설치 후 발생하는 모든 인앱 이벤트가 식별자 없이 전송되도록 보장하며, 결과적으로 어트리뷰션되지 않습니다.

<div id="developer-reference-2" />

### 개발자 참조

사용자 정보를 익명화하는 방법에 대한 개발자 참조 및 문서는 다음을 참조하세요.

<Tabs>
<Tab title="안드로이드">

[사용자 정보 익명화](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-android#anonymize-user-information)

</Tab>

<Tab title="iOS">

[사용자 정보 익명화](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-ios#anonymize-user-information)

</Tab>
</Tabs>

<div id="remove-specific-device-identifiers" />

## 특정 기기 식별자 삭제

SDK가 특정 기기 식별자를 수집하여 앱스플라이어로 전송하는 것을 방지할 수 있습니다. 이 `anonymizeUser`사용자 anonymizeUser 방법을 사용하는 것과 달리 특정 식별자를 사용하지 않도록 설정하면 유지하려는 식별자를 결정할 수 있습니다.

SDK API에는 식별자를 사용 중지하는 다음 메서드가 포함되어 있습니다.

<div id="android-identifiers" />

### Android 식별자

| 방법 |  |
| --- | --- |
| `setdisableadvertisingIdentifiers` | GAID - Google Advertising ID (구글 광고 ID)  <br />OAID(Open Anonymous Device Identifier)  <br />Amazon 광고 ID |
| [`setcollectoaid`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectoaid) | OAID(Open Anonymous Device Identifier) |

<div id="ios-identifiers" />

### iOS 식별자

| 방법 | 식별자 사용 안 함 |
| --- | --- |
| `disableAdvertisingIdentifier` | IDFA(iOS 13 이하) |
| `disableIDFVCollection` | IDFV |

<div id="developer-reference-3" />

### 개발자 참조

특정 장치 식별자를 제거하는 방법에 대한 개발자 참조 및 설명서는 다음을 참조하세요.

<Tabs>
<Tab title="안드로이드">

[ID 비활성화](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-android#disable-ids)

</Tab>

<Tab title="iOS">

[ID 비활성화](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-ios#disable-ids)

</Tab>
</Tabs>

<div id="note-3" />

> 📘 **앱스플라이어 개인정보 보호에 대해 궁금한 점이 있으신가요?**
>
> 귀하와 앱스플라이어 간의 개인정보 보호 관계는 [데이터 처리에 관한 앱스플라이어 성명서](https://www.appsflyer.com/legal/processing-customer-data/)의 적용을 받습니다. 본 방침과 관련하여 질문이 있거나 당사의 데이터 보호 책임자에게 문의하려면 [dpo@appsflyer.com](mailto:dpo@appsflyer.com) 로 이메일을 보내주십시오.

<div data-zendesk-anchors="h_01HKD1N2C8G348DPPG41HMC15J=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD use-start-and-stop-methods=start-%EB%B0%8F-stop-%EB%A9%94%EC%84%9C%EB%93%9C-%EC%82%AC%EC%9A%A9 h_01HKD1N2C8V0SP1NG8W2EJPRQZ=start-%EB%B0%8F-stop-%EB%A9%94%EC%84%9C%EB%93%9C-%EC%82%AC%EC%9A%A9 impact-on-attribution=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98%EC%97%90-%EB%AF%B8%EC%B9%98%EB%8A%94-%EC%98%81%ED%96%A5 h_01HKD1N2C80QAJSNE83SD45DJA=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98%EC%97%90-%EB%AF%B8%EC%B9%98%EB%8A%94-%EC%98%81%ED%96%A5 common-use-cases=%EC%9D%BC%EB%B0%98%EC%A0%81%EC%9D%B8-%EC%82%AC%EC%9A%A9-%EC%82%AC%EB%A1%80 h_01HKD1N2C8YHWYARRAGX1TD6DM=%EC%9D%BC%EB%B0%98%EC%A0%81%EC%9D%B8-%EC%82%AC%EC%9A%A9-%EC%82%AC%EB%A1%80 developer-reference=%EA%B0%9C%EB%B0%9C%EC%9E%90-%EC%B0%B8%EC%A1%B0 h_01HKM6VNJFCW77F2268XXDF65Q=%EA%B0%9C%EB%B0%9C%EC%9E%90-%EC%B0%B8%EC%A1%B0 prevent-sharing-data-with-networks=%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC%EC%99%80-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B3%B5%EC%9C%A0-%EA%B8%88%EC%A7%80 h_01HKD1N2C8ASV10XWY33R972MC=%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC%EC%99%80-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B3%B5%EC%9C%A0-%EA%B8%88%EC%A7%80 impact-on-attribution::aa0a9f9e=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98%EC%97%90-%EB%AF%B8%EC%B9%98%EB%8A%94-%EC%98%81%ED%96%A5-1 h_01HKD1N2C8RA34M4TSWYCW3A9F=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98%EC%97%90-%EB%AF%B8%EC%B9%98%EB%8A%94-%EC%98%81%ED%96%A5-1 h_01HKD1N2C809Y9HE99WGXZYE39=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD-1 developer-reference::f2007ab7=%EA%B0%9C%EB%B0%9C%EC%9E%90-%EC%B0%B8%EC%A1%B0-1 h_01HKM6VNJFP8C7KCFSV1046H0B=%EA%B0%9C%EB%B0%9C%EC%9E%90-%EC%B0%B8%EC%A1%B0-1 anonymize-user-information=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A0%95%EB%B3%B4-%EC%9D%B5%EB%AA%85%ED%99%94 h_01HKD1N2C8CWSWK0VSXZ39MQ3D=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A0%95%EB%B3%B4-%EC%9D%B5%EB%AA%85%ED%99%94 impact-on-attribution::601baa93=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98%EC%97%90-%EB%AF%B8%EC%B9%98%EB%8A%94-%EC%98%81%ED%96%A5-2 h_01HKD1N2C8BFVCKD3BQS4HE75P=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98%EC%97%90-%EB%AF%B8%EC%B9%98%EB%8A%94-%EC%98%81%ED%96%A5-2 h_01HKD1N2C80WW9JVBBFS5QDY7T=%ED%8C%81 developer-reference::e4cacf1f=%EA%B0%9C%EB%B0%9C%EC%9E%90-%EC%B0%B8%EC%A1%B0-2 h_01HKM6VNJF7XPZ9ME61JG4KM9Z=%EA%B0%9C%EB%B0%9C%EC%9E%90-%EC%B0%B8%EC%A1%B0-2 remove-specific-device-identifiers=%ED%8A%B9%EC%A0%95-%EA%B8%B0%EA%B8%B0-%EC%8B%9D%EB%B3%84%EC%9E%90-%EC%82%AD%EC%A0%9C h_01HKD1N2C8S3Y73AZ9J7JFDKQE=%ED%8A%B9%EC%A0%95-%EA%B8%B0%EA%B8%B0-%EC%8B%9D%EB%B3%84%EC%9E%90-%EC%82%AD%EC%A0%9C android-identifiers=android-%EC%8B%9D%EB%B3%84%EC%9E%90 h_01HKD1N2C8HZ61XHMBC0JNTK7S=android-%EC%8B%9D%EB%B3%84%EC%9E%90 ios-identifiers=ios-%EC%8B%9D%EB%B3%84%EC%9E%90 h_01HKD1N2C8AHK4EYANG6N6ST06=ios-%EC%8B%9D%EB%B3%84%EC%9E%90 developer-reference::4e0971d1=%EA%B0%9C%EB%B0%9C%EC%9E%90-%EC%B0%B8%EC%A1%B0-3 h_01HKM6VNJFV0YJWV8KT23VTKKH=%EA%B0%9C%EB%B0%9C%EC%9E%90-%EC%B0%B8%EC%A1%B0-3 h_01HKD1N2C8ZZX549W0KP3V16YQ=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EA%B0%9C%EC%9D%B8%EC%A0%95%EB%B3%B4-%EB%B3%B4%ED%98%B8%EC%97%90-%EB%8C%80%ED%95%B4-%EA%B6%81%EA%B8%88%ED%95%9C-%EC%A0%90%EC%9D%B4-%EC%9E%88%EC%9C%BC%EC%8B%A0%EA%B0%80%EC%9A%94" />
