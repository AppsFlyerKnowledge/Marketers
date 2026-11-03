---
title: 오디언스—추가 식별자 API
metadata:
  keywords:
    - Advertisers
    - Developers
    - Premium Feature
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2021-11-22T14:05:51Z'
  edited_at: '2026-10-14T10:40:48Z'
  id: 4411552670993
  locale: ko
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/ko/articles/4411552670993
---
> **한눈에 보기:** 오디언스 추가 식별자 API를 사용하여 귀사의 내부 시스템(BI 및 CRM 등)에서 앱스플라이어 오디언스로 사용자 식별자를 대량 업로드하여, 이들 식별자를 통해 관련 파트너와의 오디언스 통신을 더욱 확대할 수 있습니다.

## API 개요

오디언스 추가 식별자 API를 사용하면 귀사의 내부 시스템에서 다음과 같은 사용자 식별자를 앱스플라이어 오디언스에 추가할 수 있습니다:

* 최대 2개의 해싱된 이메일 주소
* 해싱된 전화번호
* 해싱된 E164 전화번호

귀사의 오디언스 파트너에게 이러한 식별자를 발송하도록 선택할 수 있습니다(<Anchor target="_blank" href="/marketers/ko/docs/audiences-user-identifier-policy">귀사의 계정 수준 사용자 식별자 정책</Anchor>에 따라), 이를 통해 목표 오디언스를 보다 정확하게 식별할 수 있습니다. 모든 광고 파트너가 모든 식별자를 지원하는 것은 아닙니다.

### 이 API는 언제 사용해야 하나요?

이 API는 대량의 식별자 데이터를 업로드해야 할 때 사용하도록 설계되었습니다. 일반적으로 이는 시간 경과에 따라 수집된 데이터를 의미합니다 (예: 지난 12개월 동안 앱을 사용한 모든 사용자로부터 수집된 해싱된 이메일). 특정 디바이스의 식별자를 실시간으로 개별 업데이트하려면 앱스플라이어 SDK 또는 S2S-모바일 API에서 <Anchor target="_blank" href="/marketers/ko/docs/audiences-configure-additional-identifiers-for-partner-audience-creation">추가 식별자를 구성</Anchor>하세요.

> 🚧 **중요!**
>
> 모든 추가 식별자 값은 **SHA256 해싱으로** 암호화되어야 합니다. 암호화되지 않은 식별자는 처리되지 않습니다.
>
> **타이밍:** 식별자의 정확한 매칭을 보장하기 위해, 오디언스 추가 식별자 API는 **주요 식별자가 앱스플라이어 SDK를 통해 보고된 다음 날**부터 사용할 수 있습니다 (UTC 기준). 예를 들어, 2022년 1월 3일(UTC)에 보고된 주요 식별자는 이 API를 통해 2022년 1월 4일(UTC) 또는 그 이후에 업데이트될 수 있습니다.

## 작업

* [식별자 추가\/수정](/docs/upload-additional-identifiers-to-audiences-via-api#addmodify-identifiers-put)
* [식별자 제거](/docs/upload-additional-identifiers-to-audiences-via-api#remove-identifiers-delete)

## 인증

요청에는 귀사의 계정 <Anchor target="_blank" href="/marketers/ko/docs/managing-appsflyer-tokens">앱스플라이어 V2.0 API 토큰이 포함된 HTTP 헤더가 포함되어야 합니다. 이 토큰을 앱스플라이어 대시보드에서 받으려면 귀사의 계정 관리자에게 문의하세요.</Anchor>

## API 사양 및 샘플 코드

<div id="addmodify-identifiers-put" />

<Accordion title="식별자 추가/수정(PUT)">

<span id="01ECF4ZD0T03JBV8DDH25MM01W"></span>**API 요청 URL**

```json
https://hq1.appsflyer.com/api/audience-bulk-api/v1/additional-identifiers/app/{app-id}
```

| 매개변수 | 설명 | 필수 |
| --- | --- | --- |
| `{앱아이디}` | 식별자가 수집된 앱의 앱 ID (앱스플라이어 대시보드에 표시되는 대로) | 예 |

<span id="01ECF4ZD0TWPH3DXV2YKN7G9B0"></span>**API 요청 본문**

```json
{
  "key_type": "<key_type>",
  "action": "add",
  "data": [
    {
      "key_value": "<key_value>",
      "identifiers": {
        "hashed_emails": [
          "<hashed_email_value>",
          "<hashed_email_value>"
        ],
        "phone_number_sha256": "<phone_number_sha256_value>",
        "phone_number_e164_sha256": "<phone_number_e164_sha256_value>"
      }
    },
    {
      "key_value": "<key_value>",
      "identifiers": {
        "hashed_emails": [
          "<hashed_email_value>",
          "<hashed_email_value>"
        ],
        "phone_number_sha256": "<phone_number_sha256_value>",
        "phone_number_e164_sha256": "<phone_number_e164_sha256_value>"
      }
    }
  ]
}
```

| 매개변수 | 설명 | 필수 |
| --- | --- | --- |
| `{키_유형}` | 각 데이터 행에서 유저를 나타내는 고유 값으로 사용되는 식별자입니다.<br /><br />여기에서 지정된 값은 요청의 모든 행에 적용됩니다.<br /><br />가능한 값:<ul><li>idfa</li><li>gaid</li><li>idfv</li><li>고객\_유저\_ID</li><li>imei</li><li>oaid</li></ul> | 예 |
| `{행동}` | "add" | 아니요<br /><br />기본값: 추가 |
| `{키_값}` | 지정된 key\_type에 대한 유효한 식별자 값 | 예 |
| \{식별자\} | 추가할 식별자의 이름과 값을 포함하는 객체:<ul><li>\{해시된\_이메일\}</li><li>\{전화번호\_sha256\}</li><li>\{전화번호\_e164\_sha256\}</li></ul> | 예<ul><li>이 3개 식별자 중 최소 1개의 값을 포함해야 합니다.</li></ul> |
| `{해시된_이메일}` | 최대 2개의 해시된 이메일 주소 배열<br /><br />형식:<ul><li>소문자</li><li>공백이 없음</li><li>SHA256 해시됨</li></ul>해싱 전 예시 값: name@domain.com | 아니요 |
| `{전화번호_sha256}` | 전화번호 (아래 참고)<br /><br />형식:<ul><li>기호, 문자 또는 선행 0 없음</li><li>국가 코드 포함</li><li>SHA256 해시됨</li></ul>해싱 전 예시 값:<br /><br />442070313000 | 아니요 |
| `{전화번호_e164_sha256}` | E164 형식의 전화번호 (아래 참고)<br /><br />형식<ul><li>E164 전화번호</li><li>SHA256 해시됨</li></ul>해싱 전 예시 값:<br /><br />+442070313000 | 아니요 |

> 📘 **참고**
>
> 광고 파트너마다 지원하는 전화번호 형식이 다릅니다. 따라서 전화번호를 추가할 경우, 두 식별자(*phone\_number\_sha256* 및 *phone\_number\_e164\_sha256.*)를 모두 보내는 것을 추천합니다.

**제한 사항**

다음 제한 사항은 **식별자 추가/수정** 요청에 적용됩니다.

* 기존 값(있는 경우)은 요청에서 전송된 값으로 덮어씁니다.
* `{data}` 개체는 요청당 최대 4,000개의 행(키\_값)을 포함할 수 있습니다.

**식별자를 추가하기 위한 샘플 요청**

```json
HTTP PUT
body:
{
  "key_type": "idfv",
  "action": "add",
  "data": [
    {
      "key_value": "CDDA802e-AAAA-BBBB-CCCC-DDDDDDDDDDDD",
      "identifiers": {
        "hashed_emails": [
          "34d31be18022626de6b311d6a76e791176d2691b6eef406f524d8f56364c187a",
          "d8c2aec999baad2464e521873ee4465caaf7ff6db8c8b4a25b09ca07694e4dee"
        ],
        "phone_number_sha256": "6c91c4c640f6ef0162833260db4f13dec0df2b683092f4dba7e874bef1acea37",
        "phone_number_e164_sha256": "f3d7e96c73fb0de1b66acfce541d7af758fbd4f3fa3af0ea4e10110000d3625e"
      }
    }
  ]
}
```

</Accordion>

<div id="remove-identifiers-delete" />

<Accordion title="식별자 제거(PUT)">

**API 요청 URL**

```json
https://hq1.appsflyer.com/api/audience-bulk-api/v1/additional-identifiers/app/{app-id}
```

| 매개변수 | 설명 | 필수 |
| --- | --- | --- |
| `{앱아이디}` | 식별자가 수집된 앱의 앱 ID (앱스플라이어 대시보드에 표시되는 대로) | 예 |

**API 요청 본문**

```json
{
  "key_type": "<key_type>",
  "action": "remove",
  "data": [
    {
      "key_value": ",<key_value>",
      "identifiers": [
        "hashed_emails",
        "phone_number_sha256",
        "phone_number_e164_sha256"
      ]
    },
    {
      "key_value": ",<key_value>",
      "identifiers": [
        "hashed_emails",
        "phone_number_sha256",
        "phone_number_e164_sha256"
      ]
    }
  ]
}
```

| 매개변수 | 설명 | 필수 |
| --- | --- | --- |
| `{키_유형}` | 각 데이터 행에서 유저를 나타내는 고유 값으로 사용되는 식별자입니다.<br /><br />여기에서 지정된 값은 요청의 모든 행에 적용됩니다.<br /><br />가능한 값:<ul><li>idfa</li><li>gaid</li><li>idfv</li><li>고객\_유저\_ID</li><li>imei</li><li>oaid</li></ul> | 예 |
| `{키_값}` | 지정된 key\_type에 대한 유효한 식별자 값 | 예 |
| `{행동}` | 제거 | 아니요<br /><br />기본값: 추가 |
| \{식별자\} | 값을 삭제해야 하는 식별자의 이름을 포함하는 배열:<ul><li>\{해시된\_이메일\}</li><li>\{전화번호\_sha256\}</li><li>\{전화번호\_e164\_sha256\}</li></ul> | 예<ul><li>이 3가지 식별자 중 최소 1개를 포함해야 합니다.</li></ul> |

**제한 사항**

`{data}` 개체는 요청당 최대 4,000개의 행(키\_값)을 포함할 수 있습니다.

**식별자를 제거하기 위한 샘플 요청**

```json
HTTP PUT
body:
{
  "key_type": "gaid",
  "action": "remove",
  "data": [
    {
      "key_value": "cdda802e-aaaa-bbbb-cccc-dddddddddddd",
      "identifiers": [
        "hashed_emails",
        "phone_number_sha256",
        "phone_number_e164_sha256"
      ]
    }
  ]
}
```

</Accordion>

<div id="responses" />

<Accordion title="응답">

| 코드 | 메시지 | 설명 |
| --- | --- | --- |
| 202 | 처리 승인됨 | 요청은 다음 처리 기간 동안 적용됩니다. |
| 400 | 요청 본문에는 유효한 key\_type이 포함되어야 합니다. | 지원되는 키 유형은 다음과 같습니다.<ul><li>idfa</li><li>gaid</li><li>idfv</li><li>고객\_유저\_ID</li><li>imei</li><li>oaid</li></ul> |
| 400 | 요청에는 최소 1개의 요소를 가진 '데이터'가 필요합니다. | 데이터 목록은 비워 둘 수 없습니다. |
| 400 | 요청 '데이터'는 단일 요청에서 4000의 크기를 넘지 않아야 합니다. | 데이터 목록에는 최대 4,000개의 행이 포함될 수 있습니다. |
| 400 | 요청 데이터에 유효하지 않은 '데이터' 요소가 너무 많습니다. | 수정할 데이터 중 10% 이상이 사양에 따라 유효하지 않습니다. |
| 404 | 앱스플라이어 - 페이지를 찾을 수 없음 | 다음을 확인하세요:<ul><li>API 요청 URL에 명시된 `{app-id}`가 올바른지 확인합니다.</li><li>HTTP 헤더에 올바른 <Anchor target="_blank" href="/marketers/ko/docs/managing-appsflyer-tokens">앱스플라이어 V2.0 API 토큰</Anchor>이 포함되어 있는지 확인합니다. 귀사의 계정 관리자는 앱스플라이어 대시보드에서 이 토큰을 얻을 수 있습니다.</li></ul> |

**응답 예시**

```json
{
"message": "Accepted for processing",
"received": 1000,"invalid": 2,
"trace-id": "698ed323-c787-45b5-b792-463c67c94064"
}
```

```json
{
"error": "Request body must have a valid key_type",
"trace-id": "18a5f685-ea4d-4ca9-beab-a542a3786d12"
}
```

```json
{
"error": "Request must have 'data' with at least 1 element",
"trace-id": "c155a7fa-b573-4efe-9bfb-5ae7de40e7fd"
}
```

```json
{
"error": "Request 'data' should not exceeds the size of 4000 in a single request”,
"trace-id": "b325a7fa-b573-4efe-9bfb-5ae7de40e72c"
}
```

```json
{
"error": "Request data has too many invalid 'data' elements",
"valid": 2,
"invalid": 30,
"trace-id": "33551c1d-5682-405e-a959-c8729ca74735"
}
```

</Accordion>

<div id="rate-limitations" />

<Accordion title="콜 수 제한">

* 초당 5건의 요청
* 분당 350건의 요청

</Accordion>

<div data-zendesk-anchors="api-overview=api-%EA%B0%9C%EC%9A%94 h_01HNZP1Y2MQ8W25SNP2XVNZ7WW=api-%EA%B0%9C%EC%9A%94 when-should-i-use-this-api=%EC%9D%B4-api%EB%8A%94-%EC%96%B8%EC%A0%9C-%EC%82%AC%EC%9A%A9%ED%95%B4%EC%95%BC-%ED%95%98%EB%82%98%EC%9A%94 h_01HNZP1Y2MJY56TMN6QH4BVRPA=%EC%9D%B4-api%EB%8A%94-%EC%96%B8%EC%A0%9C-%EC%82%AC%EC%9A%A9%ED%95%B4%EC%95%BC-%ED%95%98%EB%82%98%EC%9A%94 h_01HNZP1Y2MX414NJ49BCVW7KZC=%EC%A4%91%EC%9A%94 methods=%EC%9E%91%EC%97%85 h_01HNZP1Y2MS5V43XS008GG4S32=%EC%9E%91%EC%97%85 authentication=%EC%9D%B8%EC%A6%9D h_01HNZP1Y2MH2Y4P8ZT4SVM5GM2=%EC%9D%B8%EC%A6%9D api-specifications-and-sample-code=api-%EC%82%AC%EC%96%91-%EB%B0%8F-%EC%83%98%ED%94%8C-%EC%BD%94%EB%93%9C h_01HNZP1Y2MR0GCCA1916RMB6GJ=api-%EC%82%AC%EC%96%91-%EB%B0%8F-%EC%83%98%ED%94%8C-%EC%BD%94%EB%93%9C h_01HNZP1Y2M1N548KSMA6MQ601W=addmodify-identifiers-put h_01HNZP1Y2P2VVV4WT88D82QXJ4=%EC%B0%B8%EA%B3%A0 h_01HNZP1Y2Q0FAQQE3MTZ8B3FFS=remove-identifiers-delete h_01HNZP1Y2QK2J8ERP1SQTYB20C=responses h_01HNZP1Y2Q1WZCN2TCEAS6HB2X=rate-limitations" />
