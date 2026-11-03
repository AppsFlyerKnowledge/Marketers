---
title: 광고주를 위한 SKAN CV 스키마 API
metadata:
  keywords:
    - Developers
    - Marketers
    - SKAdNetwork (SKAN)
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2022-08-24T12:59:10Z'
  edited_at: '2026-10-14T10:32:15Z'
  id: 8610329713553
  locale: ko
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/ko/articles/8610329713553
---
> **한눈에 보기:**


<div id="api-basics" />

<Accordion title="API 기본사항">

| 개요 | **참고**: |
| --- | --- |
| 경로 | `https://hq1.appsflyer.com/api/skan-pull-cs-api/v1/conversion-studio-schema/app/` |
| 경로 파라미터 (필수) | : 앱스플라이어 대시보드에서 확인할 수 있는 앱 식별자입니다. |
| HTTP 메서드 | `GET` |
|  | `text/plain` |
| 인증 |  |
| 콜 수 제한 | <ul><li>분당 최대 10번 호출 가능</li></ul> |
|  |  |


```shell
curl --request \
GET 'https://hq1.appsflyer.com/api/skan-pull-cs-api/v1/conversion-studio-schema/app/<app_id>' \
--header 'Authorization: Bearer <V2_AUTH_TOKEN_HERE (700+ characters string)>'
```

</Accordion>

<div id="report-name" />

<Accordion title="리포트 이름">

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="특징 및 제약 사항">

| 특징 | 비고 |
| --- | --- |
| 광고 네트워크 액세스 | 분석 파트너라면 광고주에게 사용 권한을 부여받으라고 요청하세요. |
| 에이전시 액세스 | 사용 불가 |
| 계정 유저 액세스 | 인증 토큰은 대시보드에서 어드민 유저에게 제공됩니다. |

</Accordion>

<div id="http-response-codes-and-troubleshooting" />

<Accordion title="응답 코드 및 문제 해결">

| HTTP | 응답 | 비고 |
| --- | --- | --- |
| 200 | 정상 | 유효한 데이터가 반환되었습니다. |
| 400 | 잘못된 요청 |  |
| 401 | 인증되지 않음 |  |
| 401 | 요청이 너무 많습니다 |  |
| 403 |  | 분석 파트너라면 광고주에게 사용 권한을 부여받으라고 요청하세요. |
| 404 | 찾을 수 없음 |  |

</Accordion>

<div data-zendesk-anchors="h_01HKW1B4XQCZPQBQFADGNTZDC3=api-basics h_01HKW1B4XQ6ZD45YPHKHDHAZX0=report-name h_01HKW1B4XQVFNM33WV73BA5QXG=traits-and-limitations h_01HKW1B4XQY0V30B4BYCRF9HP5=http-response-codes-and-troubleshooting" />
