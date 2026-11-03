---
title: '업데이트 알림:'
metadata:
  keywords:
    - Agencies
    - Developers
    - Marketers
    - Platform essentials
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
  created_at: '2023-01-23T15:35:25Z'
  edited_at: '2026-10-14T10:34:44Z'
  id: 12399683708305
  locale: ko
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ko/articles/12399683708305
---
| **새로운 소식** | API 사용에 대한 보다 안전하고 신뢰할 수 있는 환경을 제공하기 위해 API URL에 포함된 API V1 토큰은 더 이상 사용되지 않고, 대신에 전달자 권한 부여를 위해 헤더에서 전달되는 JWT 기반 토큰인 API V2 토큰이 사용됩니다.<br /><br />API V1 토큰 및 이를 사용하는 API는 2023년 9월 18일부터 더 이상 사용할 수 없습니다. |
| --- | --- |
| **시행일** | 2023년 9월 18일 |
| **필수 조건** | 관리자만 앱스플라이어 대시보드에서 <Anchor target="_blank" href="/marketers/ko/docs/managing-appsflyer-tokens#토큰-검색">API V2 토큰을 검색</Anchor>할 수 있습니다. |
| **누가 API 토큰을 업데이트해야 하나요?** | 여전히 API 토큰 V1을 사용하는 광고주와 에이전시 모두 토큰을 업데이트해야 합니다. |
| **API V1 토큰을 찾는 방법** | <Anchor target="_blank" href="/marketers/ko/docs/audit-log">감사 로그</Anchor>를 사용하여 아직 사용 중인 API V1 토큰을 필터링합니다. 그런 다음 데이터를 CSV 파일로 다운로드할 수 있습니다.<ol><li>감사 로그 대시보드로 이동합니다.</li><li>검색 창에 "API Token V1"을 입력합니다.</li><li>**서비스** 필터에서 **API 호출**만 선택하고 결과를 필터링합니다.</li><li>페이지 오른쪽 상단에서 다운로드 아이콘을 클릭합니다.<br />CSV 파일이 다운로드되고 앱 ID, 사용된 서비스, API 호출 URL이 포함됩니다.</li></ol> |
| **필요한 조치** | **API V2 토큰에 대해 다음 API를 업데이트하세요.**<ol><li><Anchor target="_blank" href="https://hq1.appsflyer.com/account/api-tokens">API 토큰 페이지</Anchor>로 이동.n하세요bsp</li><li>API 토큰 V2.0에서 **클립보드에 복사** 아이콘을 클릭합니다.</li><li>다음 각 API에 대해 각 작업을 수행합니다.<ul><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/master_api_get">Master API V2</Anchor></li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-11">Aggregate Pull API V2</Anchor></li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-5">Raw Data Pull API V2</Anchor></li></ul><ol><li>API V1 URL을 위 설명서의 URL로 바꿉니다.</li><li>복사한 토큰을 전달자 인증 헤더에 붙여넣습니다.<br />![token_v2_bearer.png](https://files.readme.io/edab36cc4a091da5b8e08d6b9a446f03e364398dbec2984a83212320a8bac5f0-15407883767313.png)</li><li>`'Authorization': 'Bearer %AuthTokenV2%'`</li></ol></li></ol> |
| **API 토큰 정보** | **API 토큰에 대해 자세히 알아보세요.**<ul><li>API 토큰 관리<ul><li>마스터 API</li><li>Aggregate Pull API</li><li><Anchor target="_blank" href="/marketers/ko/docs/pull-api-raw-data">로데이터</Anchor></li><li><Anchor target="_blank" href="/marketers/ko/docs/send-opendsr-api-requests#gdpr-요청-형식">OpenDSR API</Anchor></li></ul></li></ul> |