---
title: Privacy Manifest
metadata:
  keywords:
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
  created_at: '2024-01-15T10:17:30Z'
  edited_at: '2026-10-14T10:26:08Z'
  id: 21677433322641
  locale: ko
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/ko/articles/21677433322641
---
> **요약:** WWDC23에서 Apple은 새로운 프라이버시 매니페스트를 도입했습니다. 프라이버시 매니페스트를 통해 앱 개발자는 앱의 개인 정보 보호 관행을 보다 정확하게 설명할 수 있습니다. 앱스플라이어가 앱스플라이어 SDK를 위한 프라이버시 매니페스트를 작성하였으며, 상세 내용은 아래를 참고하십시오.

<div id="background" />

## 배경

프라이버시 매니페스트를 통해 앱 개발자는 독립적으로 수집하거나 앱에서 사용하는 써드 파티 SDK와 같은 써드 파티 종속성을 사용해 수집하는 데이터 카테고리 기록을 작성할 수 있습니다. 이 정보는 앱 개발자가 사용자에게 제공하는 영양 라벨을 포함하여 앱의 개인 정보 보호 관행을 정확하게 나타내는 데 도움이 됩니다.

많은 경우에 앱 개발자는 써드 파티 SDK가 수집하는 데이터나 특정 SDK가 데이터를 사용하는 목적을 잘 모릅니다. 프라이버시 매니페스트는 써드 파티 SDK가 이 정보를 앱 개발자에게 쉽게 전달하여 정확한 영양 라벨을 만들 수 있게 도와줍니다.

<div id="what-are-nutrition-labels" />

### 영양 라벨은 무엇인가요?

영양 라벨은 앱의 개인 정보 보호 관행에 대한 정보를 읽기 쉽고 이해하기 쉬운 형식으로 제공합니다. 최종 사용자는 앱이 어떤 데이터를 어떤 목적으로 수집하는지 더 투명하게 알 수 있습니다. 영양 라벨에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/preparing-for-the-app-store-review-nutrition-labels">여기</Anchor>를 참조하세요.

<div id="what-is-in-the-appsflyer-privacy-manifest" />

## 앱스플라이어 프라이버시 매니페스트에 무엇이 들어 있나요?

<div id="important" />

> 🚧 **중요!**
>
> 앱스플라이어 SDK 외에도 귀사의 앱이나 다른 SDK에서 자체 데이터 수집, 필수 이유 API 및 사용 정보를 판단하고 해당 정보를 영양 라벨에 리포트해야 합니다.

앱스플라이어 SDK 6.14.0에는 앱스플라이어 프라이버시 매니페스트가 포함되어 있습니다. 여기에는 다음이 포함됩니다:

* [데이터 사용](#데이터-사용)
* [필수 이유 API](#required-reason-api)
* [트래킹 도메인](#트래킹-도메인)

<div id="data-usage" />

### 데이터 사용

Apple은 앱 및 SDK 개발자에게 데이터의 카테고리와 앱이나 써드 파티 SDK가 그러한 데이터를 수집하는 이유를 기록하도록 요구합니다.

그런 다음 앱 개발자는 Xcode를 사용하여 수집된 데이터에 대한 정보를 요약하는 프라이버시 리포트를 만들 수 있습니다.

다음은 앱스플라이어 SDK가 수집하며 프라이버시 매니페스트에 포함된 데이터 유형입니다.

<div id="note" />

> 📘 **참고**
>
> 다음은 앱스플라이어 소프트웨어의 기본 설정을 기준으로 합니다. 앱 개발자는 자신의 설정 및 앱스플라이어 SDK 사용 방식에 따라 프라이버시 매니페스트를 조정하는 책임이 있습니다.

| 이름 | NSPrivacyCollectedDataType | NSPrivacyCollectedDataTypeLinked | NSPrivacyCollectedDataTypeTracking | NSPrivacyCollectedDataTypePurposes |
| --- | --- | --- | --- | --- |
| 디바이스 ID (IDFA, IDFV) | NSPrivacyCollectedDataTypeDeviceID | 예 | 예 | NSPrivacyCollectedDataTypePurposeThirdPartyAdvertising |
| 제품 상호작용 (실행) | NSPrivacyCollectedDataTypeProductInteraction | 아니요 | 아니요 | NSPrivacyCollectedDataTypePurposeAnalytics |

<div id="required-reason-apis" />

### Required Reason API

Apple이 사용 이유가 필요한 API 목록을 제공했습니다. 이러한 API를 사용하는 앱과 SDK는 프라이버시 매니페스트의Required ResonAPI섹션에 이를 자세히 설명해야 합니다. 이러한 API는 그 기능과 <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api?language=objc">Apple의 주제 목록</Anchor>에 따라 제공하는 정보에 따라 카테고리로 분류됩니다. 앱스플라이어 SDK 버전 6.14.0 프라이버시 매니페스트에 포함된 API들은 다음과 같습니다.

* <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278393">파일 타임스탬프 API</Anchor>
* <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278401">유저 기본값 API</Anchor>

필수 이유 API의 사용을 명확히 하기 위해, 앱 개발자는 API 카테고리를 선언하고 API를 사용하는 이유를 명시해야 합니다. 아래는 앱스플라이어 API와 그 사용법입니다.

<div id="sdk-version-6140-and-above" />

<Accordion title="SDK 버전 6.14.0 이상">

| API 카테고리 | API 카테고리 유형 | 이유 | 설명 |
| --- | --- | --- | --- |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278393">파일 타임스탬프 API</Anchor> | NSPrivacyAccessedAPICategoryFileTimestamp | C617.1 | SDK는 <Anchor target="_blank" href="https://developer.apple.com/documentation/foundation/nsfilecreationdate?language=objc">NSFileCreationDate</Anchor>와 <Anchor target="_blank" href="https://developer.apple.com/documentation/foundation/nsfilemodificationdate?language=objc">NSFileModificationDate</Anchor> API를 사용해 앱 설치 날짜와 앱 업데이트 날짜를 판단합니다. |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278401">유저 기본값 API</Anchor> | NSPrivacyAccessedAPICategoryUserDefaults | CA92.1 | SDK는 운영에 필요한 데이터를 저장합니다. 예를 들면, 앱이 몇 번 실행되었는지 유지합니다. |

</Accordion>

<div id="sdk-versions-6130-and-earlier" />

<Accordion title="SDK 버전 6.13.x 및 이전">

| API 카테고리 | API 카테고리 유형 | 이유 | 설명 |
| --- | --- | --- | --- |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278393">파일 타임스탬프 API</Anchor> | NSPrivacyAccessedAPICategoryFileTimestamp | C617.1 | SDK는 <Anchor target="_blank" href="https://developer.apple.com/documentation/foundation/nsfilecreationdate?language=objc">NSFileCreationDate</Anchor>와 <Anchor target="_blank" href="https://developer.apple.com/documentation/foundation/nsfilemodificationdate?language=objc">NSFileModificationDate</Anchor> API를 사용해 앱 설치 날짜와 앱 업데이트 날짜를 판단합니다. |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278394">시스템 부팅 시간 API</Anchor> | NSPrivacyAccessedAPICategorySystemBootTime | 35F9.1 | SDK 성과를 측정합니다 (예: 요청을 실행하는 데 소요된 시간). |
| <Anchor target="_blank" href="https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api#4278401">유저 기본값 API</Anchor> | NSPrivacyAccessedAPICategoryUserDefaults | CA92.1 | SDK는 운영에 필요한 데이터를 저장합니다. 예를 들면, 앱이 몇 번 실행되었는지 유지합니다. |

편의상, 위의Required Reasons를 포함한 다음 코드 조각을 복사하여 귀사의 PrivacyInfo.xcprivacy 파일에 붙여넣으실 수 있습니다.

```xml
<key>NSPrivacyAccessedAPITypes</key>
<array>
    <dict>
        <key>NSPrivacyAccessedAPITypeReasons</key>
        <array>
            <string>CA92.1</string>
        </array>
        <key>NSPrivacyAccessedAPIType</key>
        <string>NSPrivacyAccessedAPICategoryUserDefaults</string>
    </dict>
    <dict>
        <key>NSPrivacyAccessedAPITypeReasons</key>
        <array>
            <string>C617.1</string>
        </array>
        <key>NSPrivacyAccessedAPIType</key>
        <string>NSPrivacyAccessedAPICategoryFileTimestamp</string>
    </dict>
    <dict>
        <key>NSPrivacyAccessedAPITypeReasons</key>
        <array>
            <string>35F9.1</string>
        </array>
        <key>NSPrivacyAccessedAPIType</key>
        <string>NSPrivacyAccessedAPICategorySystemBootTime</string>
    </dict>
</array>
```

</Accordion>

<div id="tracking-domains" />

### 트래킹 도메인

앱 또는 써드 파티 SDK에서 사용하는 모든 트래킹 도메인은 프라이버시 매니페스트에 기록되어야 합니다. 사용자가 앱 추적 투명성(ATT, AppTrackingTransparency) 프레임워크를 통해 권한을 부여하지 않으면 iOS 운영 체제가 해당 도메인으로 나가는 모든 트래픽을 차단합니다. 앱스플라이어 SDK는 서버 요청 전에 사용자의 ATT 상태를 확인하고 사용자가 권한을 부여했는지 여부에 따라 요청을 실행합니다.

<div id="faq" />

## 자주 묻는 질문

<div id="do-i-have-to-update-my-appsflyer-sdk" />

<Accordion title="앱스플라이어에 프라이버시 매니페스트를 지원하는 SDK가 있습니까?">

예, 버전 6.14.0부터 SDK가 프라이버시 매니페스트를 완벽하게 지원합니다.

</Accordion>

<div id="do-i-have-to-report-my-own-data-collection" />

<Accordion title="내가 직접 수집한 데이터를 리포트해야 하나요?">

앱스플라이어나 다른 SDK 외에도 귀사의 자체 데이터 수집 및 사용량을 판단하고, 설정 변경 사항을 포함한 해당 정보를 영양 라벨에 리포트해야 합니다. (예: 인앱 이벤트 측정)

</Accordion>

<div data-zendesk-anchors="background=%EB%B0%B0%EA%B2%BD h_01HCY4D9EKHYB5B3YNWRCB53F4=%EB%B0%B0%EA%B2%BD what-are-nutrition-labels=%EC%98%81%EC%96%91-%EB%9D%BC%EB%B2%A8%EC%9D%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80%EC%9A%94 h_01HCY4ZASEAR69RT3YMHMSE4NP=%EC%98%81%EC%96%91-%EB%9D%BC%EB%B2%A8%EC%9D%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80%EC%9A%94 what-to-consider-when-getting-your-app-ready-to-ios17=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%ED%94%84%EB%9D%BC%EC%9D%B4%EB%B2%84%EC%8B%9C-%EB%A7%A4%EB%8B%88%ED%8E%98%EC%8A%A4%ED%8A%B8%EC%97%90-%EB%AC%B4%EC%97%87%EC%9D%B4-%EB%93%A4%EC%96%B4-%EC%9E%88%EB%82%98%EC%9A%94 h_01HCY4D9EKTKB50BSZD7RBMMYB=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%ED%94%84%EB%9D%BC%EC%9D%B4%EB%B2%84%EC%8B%9C-%EB%A7%A4%EB%8B%88%ED%8E%98%EC%8A%A4%ED%8A%B8%EC%97%90-%EB%AC%B4%EC%97%87%EC%9D%B4-%EB%93%A4%EC%96%B4-%EC%9E%88%EB%82%98%EC%9A%94 h_01HQ5C9WGW669HBWSG4WQMJTGP=%EC%A4%91%EC%9A%94 data-usage=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%82%AC%EC%9A%A9 h_01HQ03P71BG159MCE3VQY4GTMH=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%82%AC%EC%9A%A9 h_01HT9QHRQSKDQ8GR17N7X5QB8N=%EC%B0%B8%EA%B3%A0 required-reason-apis=required-reason-api h_01HQ03NV880VHFTXQDE8R6ZRZH=required-reason-api h_01HSZSWW6Y91BTY1GNXMMVJCEQ=sdk-version-6140-and-above h_01HT9QVD9KZVN7RXWP03XCH8JZ=sdk-versions-6130-and-earlier required-reasons-api=%ED%8A%B8%EB%9E%98%ED%82%B9-%EB%8F%84%EB%A9%94%EC%9D%B8 h_01HQ03NV88SJPYKBM66S7X6GP8=%ED%8A%B8%EB%9E%98%ED%82%B9-%EB%8F%84%EB%A9%94%EC%9D%B8 faq=%EC%9E%90%EC%A3%BC-%EB%AC%BB%EB%8A%94-%EC%A7%88%EB%AC%B8 01HQQXSN96D4QTTYHG8CBE8695=%EC%9E%90%EC%A3%BC-%EB%AC%BB%EB%8A%94-%EC%A7%88%EB%AC%B8 h_01HCY5XRA96XAYYGB4XCZ8EXXG=do-i-have-to-update-my-appsflyer-sdk h_01HDDQV25KC9XWF7CJ7QBH4XW2=do-i-have-to-report-my-own-data-collection" />
