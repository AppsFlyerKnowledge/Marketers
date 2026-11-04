---
title: 앱 추적 투명성(ATT, iOS 14+)의 영향과 LAT의 폐지
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Developers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
    - Ad Networks
  created_at: '2020-10-07T17:33:35Z'
  edited_at: '2026-10-14T10:39:54Z'
  id: 360014090597
  locale: ko
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/ko/articles/360014090597
---
> **요약**: iOS 14부터 iOS는 앱 추적 투명성(ATT)을 통해 유저의 개인정보 보호 설정을 판단하며, 광고 측정 제한(LAT)은 더 이상 사용되지 않습니다.

<div id="att-values" />

### ATT 값

* iOS 14부터: Apple의 <Anchor target="_blank" href="https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/">ATTrackingManager</Anchor> (ATT)은 앱 측정 권한 상태 값을 제공합니다.
* 앱스플라이어는 다음 소스로부터 ATT 정보를 수집합니다:
  * 앱에 내장된 앱스플라이어 SDK V6 이상.
  * 광고주의 API를 통해. 예를 들어, S2S API.
* ATT는 로데이터 리포트에서 사용할 수 있습니다. 다음과 같이 명시적으로 요청해야 합니다.
  * Pull API: Pull API 요청에서 additional\_fields 매개변수에 ATT를 추가합니다.
  * 데이터 내보내기 페이지: 리포트 필드 탭에서 ATT를 명시적으로 선택합니다.
  * 데이터 락커: 데이터 락커 구성 페이지에서 ATT를 필드 목록에 명시적으로 추가합니다.
  * Push API: API 액세스 페이지에서 ATT를 필드 목록에 명시적으로 추가합니다.
* 경우에 따라 ATT 값은 앱스플라이어가 정의합니다. 이들은 표에서 접두사 *af*로 표시됩니다.
* IDFA를 사용할 수 없는 경우 0으로 채워집니다.

<div id="att-values-defined-by-apple" />

#### Apple에서 정의한 ATT 값

| ATT 상태 | IDFA 이용 가능 여부 | 행동 |
| --- | --- | --- |
| 미결정 | iOS 14-14.4: 사용 가능<br /><br />iOS 14.5부터: 사용 불가 | ATT 기본값 |
| 제한됨 | 사용 불가 | 이는 iTunes 계정을 기반으로 Apple이 결정하며 사용자 동작과는 관련이 없습니다. 예를 들어, 유저 나이에 따라 조직에서 관리하는 기기입니다. |
| 거부됨 | 사용 불가 | 다음 중 하나라도 해당되면 발생합니다:<ul><li>프롬프트 표시 후 설정</li><li>유저가 *앱 추적 요청 허용*(디바이스 수준의 마스터 스위치)을 껐습니다.</li><li>디바이스에 iOS 14를 설치하기 전에 LAT가 켜져 있었습니다.</li></ul> |
| 허용됨 | 사용 가능 | 유저가 명시적으로 동의했습니다. |

<div id="additional-att-values-defined-by-appsflyer" />

#### 앱스플라이어가 정의한 추가 ATT 값

| ATT 상태 | 참고 | IDFA 이용 가능 여부 |
| --- | --- | --- |
| af\_unknown | 광고주가 신고한 ATT 값이 <Anchor target="_blank" href="https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/">ATTrackingManager</Anchor> 사양에 존재하지 않는 값입니다. | iOS 버전에 따라 다름 |
| af\_authorized | 다음 요인으로 인해 IDFA 사용이 허용됩니다:<ul><li>기기 iOS 버전: iOS 14 이전.</li><li>리포트된 이벤트에 IDFA는 포함되어 있지만 ATT는 포함되어 있지 않습니다. 예를 들어, iOS 14 이전 버전으로 운영되는 디바이스에 SDK V5.X가 포함된 앱이 있습니다.</li></ul> | 사용 가능 |
| af\_unavailable | <ul><li>광고주가 이 이벤트에서 앱 추적 투명성을 보고하지 않았고 IDFA를 사용할 수 없습니다.</li><li>앱스플라이어 SDK 버전 V5.X는 앱 추적 투명성을 받을 수 없고 IDFA도 받지 못했습니다.</li></ul> | 사용 불가 |

<div id="is-lat-in-iosconsiderations-and-how-lat-translates-to-att-in-ios-14" />

### iOS에서 LAT에 대한 고려사항 및 iOS 14에서 LAT를 앱 추적 투명성으로 변환하는 방법

| iOS 버전 | Is LAT 사용 |
| --- | --- |
| iOS 13까지 | <Image alt="IsLatTrue_us-en.png" src="https://files.readme.io/28440075d9c3913a148228a85ede15048d76f24913b48799ec4de3952d8f33e7-360011938457.png" width="221px" /><br /><br />true이면 사용자가 광고 추적 제한을 활성화한 것이며, IDFA를 사용할 수 없습니다. |
| iOS 14부터 | <Anchor target="_blank" href="https://developer.apple.com/documentation/adsupport/asidentifiermanager/1614148-isadvertisingtrackingenabled">Apple은 *LAT를 더 이상 사용하지 않습니다*</Anchor>. *Is LAT*값을 무시하고 대신 ATT를 사용하십시오. |

**iOS14에서 LAT를 ATT로 변환하는 방법**

[altLATtoiOS14.5.pngalt](https://support.appsflyer.com/hc/article_attachments/51858110622353)

<div data-zendesk-anchors="att-values=att-%EA%B0%92 h_01HGX9468F5YF0KSHB3S49CW2Y=att-%EA%B0%92 att-values-defined-by-apple=apple%EC%97%90%EC%84%9C-%EC%A0%95%EC%9D%98%ED%95%9C-att-%EA%B0%92 h_01HGX9468F0TFTMKP1W2J6GEBV=apple%EC%97%90%EC%84%9C-%EC%A0%95%EC%9D%98%ED%95%9C-att-%EA%B0%92 additional-att-values-defined-by-appsflyer=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EA%B0%80-%EC%A0%95%EC%9D%98%ED%95%9C-%EC%B6%94%EA%B0%80-att-%EA%B0%92 h_01HGX96RG9NX9QM2WTX8789DDR=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EA%B0%80-%EC%A0%95%EC%9D%98%ED%95%9C-%EC%B6%94%EA%B0%80-att-%EA%B0%92 is-lat-in-ios%E2%80%94considerations-and-how-lat-translates-to-att-in-ios-14=ios%EC%97%90%EC%84%9C-lat%EC%97%90-%EB%8C%80%ED%95%9C-%EA%B3%A0%EB%A0%A4%EC%82%AC%ED%95%AD-%EB%B0%8F-ios-14%EC%97%90%EC%84%9C-lat%EB%A5%BC-%EC%95%B1-%EC%B6%94%EC%A0%81-%ED%88%AC%EB%AA%85%EC%84%B1%EC%9C%BC%EB%A1%9C-%EB%B3%80%ED%99%98%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 h_01HGX9468F0VTYNXBJRSTNBCMB=ios%EC%97%90%EC%84%9C-lat%EC%97%90-%EB%8C%80%ED%95%9C-%EA%B3%A0%EB%A0%A4%EC%82%AC%ED%95%AD-%EB%B0%8F-ios-14%EC%97%90%EC%84%9C-lat%EB%A5%BC-%EC%95%B1-%EC%B6%94%EC%A0%81-%ED%88%AC%EB%AA%85%EC%84%B1%EC%9C%BC%EB%A1%9C-%EB%B3%80%ED%99%98%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95" />
