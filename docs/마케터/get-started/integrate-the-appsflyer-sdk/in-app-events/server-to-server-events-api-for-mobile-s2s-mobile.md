---
title: 모바일용 서버-투-서버 이벤트 API (S2S-mobile)
metadata:
  keywords:
    - iOS
    - Android
    - API
    - In-App
    - S2S
    - HTTP API
    - appsflyer_id
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
  created_at: '2014-05-21T17:47:21Z'
  edited_at: '2026-10-14T10:29:20Z'
  id: 207034486
  locale: ko
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ko/articles/207034486
---
> **한눈에 보기:** 앱 외부에서 발생하는 모바일 이벤트를 측정하기 위해 귀사의 서버에서 앱스플라이어로 이벤트를 발송합니다.

<Image align="center" alt="S2S_us-en.png" src="https://files.readme.io/2f228a03ca00df529e42bd033825a0dca595e99a537cadcfd5419754a29b5490-35863179575441.png" />

<div id="server-to-server-events-api-for-mobile" />

## 모바일용 서버-투-서버 이벤트 API

iOS 앱의 경우 iOS 14부터 운영 체제 파라미터를 발송해야 합니다.

앱스플라이어 플랫폼은 앱스플라이어 SDK 및 API에서 발송된 모바일 앱 이벤트를 어트리뷰션하고 기록합니다. S2S API를 사용하면 앱 외부에서 발생하는 이벤트를 리포트할 수 있습니다. 예를 들어, 사용자가 웹 인터페이스를 사용하여 구독을 갱신하는 경우입니다. S2S 이벤트는 기록되면, 대시보드, 로데이터, 분석을 포함한 플랫폼 전반에서 사용 가능합니다. PBA 웹 이벤트의 경우 <Anchor target="_blank" href="/marketers/ko/docs/web-server-to-server-events-api-for-pba-web-s2s">PBA용 웹 S2S</Anchor>를 참조하세요.

앱스플라이어는 S2S 이벤트에 다음을 포함합니다.

* S2S 메시지로 발송된 값
* 일부 앱스플라이어 인스톨 어트리뷰션 값은 인스톨 시간, 미디어 소스를 포함합니다.

API를 통해 이벤트를 발송하려면 개발자에게 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/s2s-events-api3-post">서버 간 이벤트 API 지침</Anchor>을 따르라고 요청하세요.

<div id="populating-parameters" />

## 파라미터 채우기

<div id="difference-between-organic-and-nonorganic" />

<Accordion title="오가닉과 논오가닉의 차이점">

앱스플라이어가 S2S 인앱 이벤트를 처리할 때, 앱스플라이어 ID를 사용하여 어트리뷰션 필드가 채워지고, 이를 통해 인앱 이벤트 이전에 발생한 관련 인스톨 이벤트를 식별합니다.

즉, 앱스플라이어가 논오가닉 S2S 인앱 이벤트와 연관시키는 일부 데이터는 오가닉 S2S 인앱 이벤트와는 연관되지 않습니다.

<div id="h_01_including-user-agent-and-ip-address-in-s2s-events" />

<div id="note" />

> 📄 **예시**
>
> 예를 들어, 논오가닉 및 오가닉 S2S 인앱 이벤트의 로데이터 리포트를 비교해보면, 논오가닉 이벤트에는 오가닉 인앱 이벤트에 없는 데이터가 포함되어 있습니다.
>
> 논오가닉 인앱 이벤트는 미디어 소스, 캠페인, 어트리뷰션된 터치 유형, 어트리뷰션된 터치 시간에 대한 데이터를 포함합니다.
>
> 반면, 오가닉 인앱 이벤트는 오가닉 인스톨을 따릅니다. 오가닉 인스톨은 캠페인, 미디어 소스, 어트리뷰션된 터치 유형, 인스톨 시간과 관련된 데이터가 없습니다.

</Accordion>

<div id="mapping-appsflyer-id-with-customer-user-id-cuid" />

<Accordion title="앱스플라이어 ID와 고객 유저 ID (CUID) 매핑하기">

매개변수를 채우기 위한 값을 얻으려면 백엔드 로직이 필요합니다. 여기서는 앱스플라이어 ID를 얻는 방법을 설명합니다.

* 앱스플라이어 ID는 필수 요소이며 이벤트를 귀속하는 데 사용됩니다.
* 사용자가 모바일 앱을 처음 인스톨 할 때 발생합니다.
* CUID를 앱에 설정하여 귀사의 CUID를 앱스플라이어 ID에 매핑해야 합니다.

각 사용자가 어떤 이벤트를 수행했는지 더 쉽게 파악할 수 있도록 다음과 같은 흐름을 구현하세요:

* 사용자가 앱을 인스톨 할 때 <Anchor target="_blank" href="/marketers/ko/docs/customer-user-id-field-cuid">고객 유저 ID</Anchor>를 설정하세요.
* 앱스플라이어 로데이터 리포트에는 CUID와 앱스플라이어 ID가 포함됩니다. 이를 얻으려면 데이터 전달 도구 중 하나나 앱스플라이어 Push API를 사용하세요.
* 로데이터 리포트를 사용하여 CUID와 앱스플라이어 ID를 매칭시키세요.
* 앱스플라이어 ID는 귀하의 앱에 통합된 SDK에서 사용할 수 있습니다 (안드로이드/iOS).
* 내부 시스템에서 앱스플라이어 ID를 고객 유저 ID에 매핑하세요 (향후 사용을 위해 중요).

앱스플라이어 ID를 귀사의 CUID와 매핑하면 사용자를 수행한 이벤트와 매칭할 수 있습니다. 그런 다음 이벤트 값, 이벤트 통화, 이벤트 시간 등 다른 값을 얻어서 서버-투-서버 인앱 이벤트를 발송할 수 있습니다.

</Accordion>

<div id="fetching-the-appsflyer-id" />

<Accordion title="앱스플라이어 ID 가져오기">

`appsflyer_id`은 서버-투-서버 이벤트 메시지의 필수 매개변수입니다. 앱스플라이어는 이 매개변수를 사용하여 이벤트를 원래 디바이스와 어트리뷰션된 미디어 소스에 귀속시킵니다. 다음 방법 중 하나를 사용하여 ID를 얻을 수 있습니다:

* 모바일 디바이스에서 앱스플라이어 SDK API를 호출하여:

  <Tabs>
  <Tab title="안드로이드 네이티브">

  <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#getappsflyeruid">getAppsFlyerUID</Anchor>

  </Tab>

  <Tab title="iOS 네이티브">

  <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#getappsflyeruid">getAppsFlyerUID</Anchor>

  </Tab>

  <Tab title="유니티">

  <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#getappsflyerid">getAppsFlyerId</Anchor>

  </Tab>

  <Tab title="리액트 네이티브">

  <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#getappsflyeruid">getAppsFlyerUID</Anchor>

  </Tab>
  </Tabs>

* 앱스플라이어 플랫폼에서 다음 중 하나를 사용하여: <Anchor target="_blank" href="/marketers/ko/docs/pull-api-raw-data?query=pull">Pull API,</Anchor> <Anchor target="_blank" href="/marketers/ko/docs/push-api-streaming-raw-data">Push API,</Anchor> <Anchor target="_blank" href="/marketers/ko/docs/raw-data-reporting-overview">로데이터 내보내기 설치</Anchor>

</Accordion>

<div id="time-stamping-s2s-events" />

<Accordion title="타임스탬프 S2S 이벤트">

[alt타임스탬핑 로직 다이어그램alt](https://support.appsflyer.com/hc/article_attachments/30446139690129)

S2S 이벤트가 앱스플라이어에 대량으로 도달하면 `eventTime` 속성 값과 도착 시간에 맞추어 타임스탬프가 찍힙니다. `eventTime` 속성은 인앱 이벤트의 발생 시간을 나타냅니다.

도착 시, 이벤트는 다음과 같이 타임스탬프가 지정됩니다:

* 이벤트 기록에 `eventTime` 매개변수가 포함되어 있지 않으면, 이벤트 시간은 HTTP 메시지 도착 시간으로 설정됩니다.
* 02:00 UTC 이전에 도착한 이벤트는 `eventTime` 값으로 타임스탬프가 찍힙니다. 즉, 이벤트에 `eventTime`이 타임스탬프 찍히려면 그날이나 다음 날 02:00 UTC까지 보고되어야 합니다.
* 전날 또는 그 이전에 발생하고 02:00 UTC 이후에 도착한 이벤트는 도착 시간(즉, API 호출 시간)으로 타임스탬프가 찍힙니다.
* 미래 `eventTime` 값으로 도착하는 이벤트(eventTime > 도착 시간):
  * 보고된 `eventTime`과 도착 시간이 같은 날짜이면, 이벤트는 `eventTime` 값으로 타임스탬프가 찍힙니다.
  * 보고된 `eventTime`이 다음 날짜이면, 이벤트는 도착 시간으로 타임스탬프를 찍습니다.
* `eventTime` 값이 잘못된 이벤트는 HTTP 메시지 도착 시간으로 타임스탬프가 찍힙니다.

**예시**

* `eventTime` = 월요일 21:00으로 이벤트가 전송되었습니다.

| 앱스플라이어에 도착했습니다 | 앱스플라이어 타임스탬프 | 비고 |
| --- | --- | --- |
| 화요일 01:00 | 월요일 21:00 | 업무 종료 전에 도착했습니다. 시간은 `eventTime` 값으로 설정됩니다. |
| 수요일 09:00 | 수요일 09:00 | 업무 종료 후 도착했습니다. 시간은 도착 시간으로 설정됩니다. |

</Accordion>

<div id="sending-negative-revenue" />

<Accordion title="음수 수익 전송">

수익 값이 음수인 이벤트도 전송 가능합니다. 예를 들어, 구매가 취소된 경우입니다. `af_revenue` 매개변수는 이를 기록하기 위해 음수 값을 가질 수 있습니다.

`af_quantity`을 채울 때 귀사의 시스템 로직에 따라 음수 값으로 채울 수 있습니다. 앱스플라이어는 `af_quantity`을 사용하지 않습니다.

</Accordion>

<div id="note-1" />

> 📘 **참고**
>
> <Anchor target="_blank" href="/marketers/ko/docs/incrementality-for-remarketing-overview">증분성</Anchor>으로 측정되기 위해, S2S 이벤트는 페이로드에 광고 ID를 포함해야 합니다 (iOS의 IDFA, Android의 GAID).

<div id="increasing-the-volume-of-data-transactions" />

## 데이터 거래량 증가

점진적 확장을 사용하는 경우, 앱스플라이어는 자동 확장 솔루션을 통해 초당 거래량(TPS)을 대량으로 지원할 수 있습니다. 예를 들어:

* 초당 10,000건의 거래(TPS)로 시작해서 1분 간격으로 점진적으로 확장합니다.
  * 00:00:00 - 10천 TPS 발송 (기준선)
  * 00:01:00 - 12천 TPS로 증가
  * 00:02:00 - 14천 TPS로 증가
  * 00:03:00 - 16천 TPS로 증가
  * 00:04:00 - 18천 TPS로 증가
  * …
* 오류가 발생할 때 사용할 재시도 메커니즘을 구현하십시오.

<div id="troubleshooting" />

## 문제 해결

<div id="events-arent-displaying-in-the-dashboard" />

<Accordion title="대시보드에 이벤트가 표시되지 않습니다.">

* 엔드포인트: 사용된 엔드포인트가 올바른지 확인하세요.
* 페이로드에 필수 파라미터가 포함되어 있는지 확인하세요. [여기](/docs/server-to-server-events-api-for-mobile-s2s-mobile#mapping-appsflyer-id-with-customer-user-id-cuid)를 참조하세요.
* 이벤트를 발생시키는 앱스플라이어 ID가 실제 appsflyer\_id이며 실제 앱 설치와 관련이 있는지 확인하세요. [여기](/docs/server-to-server-events-api-for-mobile-s2s-mobile#fetching-the-appsflyer-id)를 참조하세요.
* S2S 이벤트는 하나의 S2S 요청에서 멀티이벤트를 지원하지 않습니다. 각 이벤트는 별도의 이벤트로 발송해야 합니다.
  * 응답 시간을 단축하기 위해 비동기 메서드로 이벤트를 발송할 수 있습니다.
* 개요 대시보드에서 날짜 범위는 이벤트 날짜가 아닌 인스톨 날짜(LTV(유저생애가치))와 관련이 있습니다.
  * 올바른 날짜 범위를 선택했는지 확인하세요.
  * 대시보드의 날짜 범위가 이벤트 날짜가 아닌 디바이스의 인스톨 날짜(appsflyer\_id)에 맞게 설정되었는지 확인하세요.
* 이벤트 로데이터 리포트: 날짜 범위는 인스톨 날짜가 아닌 이벤트 날짜와 관련이 있습니다.

</Accordion>

<div id="events-dont-contain-revenue" />

<Accordion title="이벤트에는 수익이 포함되지 않습니다.">

S2S 이벤트를 발송했지만 수익이 기록되지 않는 경우, 발송한 JSON이 문자열화되었는지 확인하세요. 가장 중요한 부분은 JSON의 이벤트 값 파라미터입니다. 다음 예와 같이 문자열로 변환해야 합니다.

```json
"{\"af_revenue\":\"6\" ,\"af_content_type\":\"wallets\"}"
```

문자열화되지 않으면 이벤트 값이 올바르게 처리되지 않고 수익이 기록되지 않습니다.

수익 값은 어떤 형식으로도 변환되지 않아야 합니다. 소수점을 포함할 수 있습니다. 통화 기호나 코드, `,` 구분 기호를 포함하지 마십시오. 수익은 `-`로 접두사를 붙일 수 있습니다.

* 유효한 값의 예는 다음과 같습니다: `123`, `-123.45`, `123.456`
* 잘못된 값의 예: `1,234.56`, `1,234`

</Accordion>

<div id="not-all-fields-are-populated-in-s2s-events" />

<Accordion title="S2S 이벤트에서는 모든 필드가 채워지지 않을 수 있습니다.">

S2S 이벤트의 원시 데이터 필드는 S2S 호출에서 전송된 값으로만 채워집니다. 다음 필드는 S2S API로 보고할 수 없으며, 따라서 로데이터 리포트의 S2S 이벤트에서는 채워지지 않습니다:

* WIFI
* 오퍼레이터
* 언어
* 디바이스 모델
* 디바이스 카테고리
* 앱 버전: `app_version_name`을 사용할 수 있습니다
* 앱 이름

</Accordion>

<div id="S2S_in-app_events_are_wrongly_attributed_as_organic" />

<Accordion title="S2S 인앱 이벤트가 잘못 오가닉으로 지정됩니다">

S2S 이벤트, 예를 들면 로그인 이벤트,는 앱이 설치되고 SDK가 시작될 때 앱스플라이어로 전송될 수 있습니다. 그러나 이러한 S2S 인앱 이벤트가 앱스플라이어가 인스톨 이벤트를 처리 완료하기 전에 도착하면, 일반적으로 20&#126;30초 이상 필요하면, 속성이 지정되지 않은 오가닉 이벤트로 표시될 수 있습니다.

인스톨 직후 발생하는 S2S 인앱 이벤트를 서버에 리포팅하기 전에 잠시 지연시키는 것을 권장합니다.

</Accordion>

<div data-zendesk-anchors="servertoserver-events-api-for-mobile=%EB%AA%A8%EB%B0%94%EC%9D%BC%EC%9A%A9-%EC%84%9C%EB%B2%84-%ED%88%AC-%EC%84%9C%EB%B2%84-%EC%9D%B4%EB%B2%A4%ED%8A%B8-api h_01H9Q8KBYGXAA8H4AKKXP8T8DY=%EB%AA%A8%EB%B0%94%EC%9D%BC%EC%9A%A9-%EC%84%9C%EB%B2%84-%ED%88%AC-%EC%84%9C%EB%B2%84-%EC%9D%B4%EB%B2%A4%ED%8A%B8-api populating-parameters=%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0-%EC%B1%84%EC%9A%B0%EA%B8%B0 h_01H9Q8KBYGHY1SDSMSFZRT2JXZ=%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0-%EC%B1%84%EC%9A%B0%EA%B8%B0 h_01H9Q8KBYG6W4TERWHARZZZASZ=difference-between-organic-and-nonorganic h_01H9Q8KBYG0JCCGTEJW3GXZMF1=%EC%98%88%EC%8B%9C h_01H9Q8KBYG6EBKPS5Y2KC1QT7G=mapping-appsflyer-id-with-customer-user-id-cuid h_01H9Q8KBYGR26VMQR9Y0CK85F6=fetching-the-appsflyer-id h_01H9Q8KBYG8ASB1WB9X4XM3CYZ=time-stamping-s2s-events h_01H9Q8KBYG63SZWNM4GWSJG605=sending-negative-revenue h_01JWV0HR3P78NFBHWY1KM97M98=%EC%B0%B8%EA%B3%A0 increasing-the-volume-of-data-transactions=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B1%B0%EB%9E%98%EB%9F%89-%EC%A6%9D%EA%B0%80 h_01HX77GDZ1CCWN48CN616P860D=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B1%B0%EB%9E%98%EB%9F%89-%EC%A6%9D%EA%B0%80 troubleshooting=%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0 h_01H9Q8KBYGYR9Y7DPCNWSB4QY0=%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0 h_01H9Q8KBYGYHCWAPPNMG9WB8QN=events-arent-displaying-in-the-dashboard h_01H9Q8KBYGDC68637RH4DE2FZX=events-dont-contain-revenue h_01H9Q8KBYGDQKZF90EJAXRTMF3=not-all-fields-are-populated-in-s2s-events h_01JWV0CS5BFBXDT333794BHFER=S2S_in-app_events_are_wrongly_attributed_as_organic" />
