---
title: PBA에서 웹 성과 측정으로 마이그레이션
metadata:
  keywords:
    - Developers
    - Marketers
    - Web Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
  created_at: '2026-07-26T11:53:06Z'
  edited_at: '2026-10-14T10:27:37Z'
  id: 49156441281425
  locale: ko
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/ko/articles/49156441281425
---
> **한눈에 보기:** PBA(People-Based Attribution)가 앱스플라이어의 업그레이드된 웹 측정 솔루션인 웹 성과 측정(Web Performance Measurement)으로 대체됩니다. 본 문서에서는 변경 사항, 마이그레이션 단계, 리포트 및 서버 사이드 연동을 위한 전체 필드 매핑 정보를 안내합니다.

<div id="why-were-upgrading-your-web-measurement" />

## 웹 측정을 업그레이드하는 이유

웹 측정이 그 어느 때보다 중요해졌습니다. 웹사이트는 많은 사용자 전환을 발생시키는 공간이자 모바일 앱으로 향하는 여정이 시작되는 지점입니다. 웹사이트는 단순한 랜딩 페이지가 아닙니다. 퀴즈 플로우, 개인화된 온보딩, 페이월, 웹스토어로 이루어진 완전한 유입 파이프라인으로, 보다 적은 비용으로 구매 의도가 높은 사용자를 확보하게 되는 경우가 많습니다.

앱스플라이어는 웹 측정 수준을 모바일과 동일한 표준으로 끌어올리고 있습니다. 기존 웹 제품인 PBA는 앱스플라이어의 핵심 어트리뷰션 엔진 및 통합 데이터 모델을 기반으로 구축된 웹 성과 측정으로 대체됩니다. 웹 성과 측정은 현재 PBA가 제공하는 모든 기능을 지원하며 다음 기능을 추가로 제공합니다.

* **One source of truth**를 바탕으로 비용 집계, 최적화 포스트백, 크리에이티브 최적화까지 웹과 모바일 앱 측정을 한곳에서 통합 관리합니다.
* **더 나은 예산 책정**과 비즈니스 로직에 맞춘 유연한 어트리뷰션을 제공하여 실제 성과를 내는 캠페인에 더욱 집중할 수 있도록 지원합니다.
* **향상된 ROAS**, 광고사로 전달되는 다각화된 최적화 포스트백, 더 많은 전환을 측정하는 완벽한 서버 사이드 설정을 제공하여 광고사 네트워크가 더 우수한 시그널을 바탕으로 캠페인을 최적화할 수 있도록 지원합니다.
* **진정한 크로스 플랫폼 ROI**, 웹, 앱 및 모든 플랫폼에 걸친 모든 사용자 여정을 측정합니다.
* **간편한 통합 리포팅**, 단 하나의 대시보드와 단일 데이터 리포트 세트로 모든 플랫폼의 성과를 매시간 업데이트하여 제공합니다.

> 📘 **참고**
>
> 최소 노력으로 전환을 손쉽게 진행할 수 있습니다. 웹사이트의 코드 변경 없이 기존 Web SDK를 그대로 유지할 수 있습니다.

> 🚧 **중요!**
>
> 수치상 약간의 차이가 발생할 수 있습니다. 웹 성과 측정의 기여 로직은 더욱 고도화되고 유연해졌기 때문에, 기존 PBA의 수치와 완전히 일치하지는 않습니다.

<div id="web-performance-measurement-vs-pba" />

## 웹 성능 측정 vs. PBA

<table><thead><tr><th>기능</th><th>설명</th><th>PBA</th><th>웹 성과 측정</th></tr></thead><tbody><tr><td colspan="4"><strong>Data</strong></td></tr><tr><td>데이터 최신성</td><td>리포팅에 데이터가 반영되기까지 얼마나 걸리나요?</td><td>✗ 일일</td><td>✓ 시간별 보고서, 약 2시간의 데이터 새로고침</td></tr><tr><td>데이터 모델</td><td>모바일 어트리뷰션 데이터와의 스키마 정렬</td><td>✗ 모바일과 다른 점</td><td>✓ 모바일 데이터와 얼라인되어 쉽게 결합하고 분석 가능</td></tr><tr><td colspan="4"><strong>리포팅</strong></td></tr><tr><td>액티비티 대시보드</td><td>이벤트 시간 기반 대시보드</td><td>✓ 지원됨</td><td>✓ 지원됨</td></tr><tr><td>코호트 대시보드</td><td>시간 경과에 따른 유입 코호트별 성과 분석</td><td>✗ 지원되지 않음</td><td>✓ 지원됨</td></tr><tr><td>Data Locker 로우 데이터</td><td>Data Locker 내보내기를 통한 로우 어트리뷰션 데이터 액세스</td><td>✓ 지원됨</td><td>✓ 지원됨</td></tr><tr><td>광고 수준 세분성</td><td>캠페인부터 소재 레벨까지의 리포트 세부 내역</td><td>✗ 대시보드 전용, 로우 데이터 제외</td><td>✓ 대시보드와 로우 데이터 모두에서 전체 캠페인 세분화</td></tr><tr><td>크로스 플랫폼 LTV</td><td>웹 및 모바일 사용자 여정을 LTV로 통합 산출</td><td>✗ 지원되지 않음</td><td>✓ 지원됨</td></tr><tr><td colspan="4"><strong>비용 및 신호</strong></td></tr><tr><td>웹 비용</td><td>웹 캠페인 광고 지출에 대한 인제스트 및 리포트</td><td>✗ 지원되지 않음</td><td>✓ 지원됨</td></tr><tr><td>포스트백 최적화</td><td>최적화 신호를 광고 네트워크로 다시 전송</td><td>✗ 지원되지 않음</td><td>✓ 지원됨</td></tr><tr><td colspan="4"><strong>구현</strong></td></tr><tr><td>Web SDK(픽셀)</td><td>웹 방문 및 이벤트 측정을 위한 클라이언트측 SDK</td><td>✓ 지원됨</td><td>✓ 동일한 SDK, 코드 변경 필요 없음</td></tr><tr><td>S2S 지원</td><td>방문 및 이벤트에 대한 전체 서버 측 측정</td><td>✗ 이벤트 전용</td><td>✓ 이벤트 및 방문 전체 서버 측 구현 지원</td></tr><tr><td colspan="4"><strong>어트리뷰션 엔진</strong></td></tr><tr><td>어트리뷰션 기간</td><td>룩백, 어트리뷰션, 리인게이지먼트 및 비활성 기간 구성</td><td>✗ 룩백 윈도우만 클릭</td><td>✓ 5개 기간 구성(전체 제어)</td></tr><tr><td>커스텀 UA 이벤트</td><td>첫 방문 이의 사용자 획득으로 간주되는 이벤트 정의</td><td>✗ 첫 방문만 가능</td><td>✓ 모든 커스텀 이벤트(예: 가입, 구매)</td></tr><tr><td>UA vs. 리타겟팅</td><td>신규 유입 및 리인게이지먼트 시 별도의 크레딧</td><td>✗ UA 컨셉 없음, 라스트 터치로 인한 이벤트</td><td>✓ 전용 UA 및 리타겟팅 뷰(이중 어트리뷰션 크레딧 포함)</td></tr></tbody></table>

<div id="migrate-to-web-performance-measurement" />

## 마이그레이션 단계

아래 표는 마이그레이션을 다섯 단계로 나눕니다. 웹 앱 생성은 모든 사용자에게 적용되며, 나머지 항목은 S2S API나 Data Locker 리포트 등 현재 사용 중인 PBA 기능에 따라 달라집니다.

| 액션 | 관련 대상 | 관련 내용 |
| --- | --- | --- |
| 앱 만들기 | 모두 | <Anchor target="_blank" href="/marketers/ko/docs/adding-an-app-to-appsflyer#web">신규 웹 앱 생성</Anchor> 시 기존 웹 Dev Key를 **Web SDK ID** 필드에서 선택하세요. 이렇게 하면 코드 변경 없이 현재 웹 사이트 코드가 그대로 작동합니다. 그런 다음 새 앱에서 어트리뷰션 설정을 구성합니다. |
| 새 S2S API로 마이그레이션 | PBA S2S API 사용 | <Anchor target="_blank" href="/marketers/ko/docs/server-to-server-s2s-api-for-web-performance-measurement">새 S2S API</Anchor>를 설정합니다. 서버 사이드만으로 완벽히 구동할 수 있도록 방문과 이벤트 측정을 모두 지원합니다. 아래 [S2S API 마이그레이션 부록을](#부록-pba-웹-s2s에서-새로운-s2s-api로-마이그레이션) 참조하십시오. |
| 새 Data Locker 보고서로 이동 | PBA Data Locker 보고서 사용 | UI에서 <Anchor target="_blank" href="/marketers/ko/docs/export-web-performance-measurement-report-data-from-data-locker">신규 웹 리포트</Anchor>를 활성화하고 BI/ETL의 데이터 소스를 업데이트된 데이터로 변경하세요. 새로운 리포트는 모바일 앱, 웹사이트, CTV, PC를 포함한 모든 플랫폼에 걸쳐 단일화된 공통 스키마를 따릅니다. 아래 [로우 데이터 필드 매핑 부록을](#부록-로우-데이터-보고서-변경-사항) 참조하십시오. |
| 어트리뷰션 파라미터 리뷰 | 추천 | PBA는 자체 <Anchor target="_blank" href="/marketers/ko/docs/pba-media-source-attribution-rules">미디어 소스 어트리뷰션 규칙을</Anchor> 적용했습니다. 웹 성과 측정은 <Anchor target="_blank" href="/marketers/ko/docs/about-traffic-source-resolution">향상된 트래픽 소스 해상도를</Anchor> 사용하여 분석을 더욱 선명하게 합니다. 차이점을 검토하여 보고서에 어떤 값을 기대해야 하는지 알아보세요. 아래의 [트래픽 소스 해상도 비교 부록을](#부록-트래픽-소스-해상도-pba-vs-웹-성과-측정) 참조하세요. |
| 앱을 프로덕트 라인으로 그룹화 | 선택 사항 | 프로덕트 라인을 생성하고 웹 앱을 모바일 앱과 그룹화하여 <Anchor target="_blank" href="/marketers/ko/docs/beta-user-based-cross-platform-attribution">크로스 플랫폼 사용자 LTV 리포팅</Anchor>(PBA Brand Bundle과 유사) 기능을 활성화하세요. |

> 📘 **참고**
>
> 수치상 약간의 차이가 발생할 수 있습니다. 웹 성과 측정의 기여 로직은 더욱 고도화되고 유연해졌기 때문에, 기존 PBA의 수치와 완전히 일치하지는 않습니다. <Anchor target="_blank" href="/marketers/ko/docs/about-traffic-source-resolution#1단계-방문-기록">세션 기록 로직</Anchor> 자체는 변경되지 않으며, 시장 표준대로 30분간의 액티비티 동안 세션이 유지됩니다.

<div id="capabilities-being-discontinued" />

## 지원 중단되는 기능

| 기능 | 변경된 내용 | 세부 정보 |
| --- | --- | --- |
| 전환 경로 | 이미 사용 중지됨 | — |
| 웹 어시스트 설치(이후 발생한 모바일 설치에 기여한 웹 캠페인에 크레딧 부여) | 전용 “웹 어시스트 설치” 보기가 없습니다. | 웹투앱 사용자 여정은 스마트 스크립트 및 스마트 배너를 통해 측정됩니다. 크로스 플랫폼 리포트는 동일하진 않지만 유사한 형태의 분석을 제공합니다. PBA와 마찬가지로 CUID를 기반으로 합니다.<ul><li>기존에 자연 유입으로 리포팅되었으나 설치에 기여한 웹 캠페인들이 이제는 비자연 유입 신규 사용자 획득으로 표시됩니다. 이는 단순 어시스트가 아니며, 해당 웹 캠페인이 신규 사용자 획득의 직접적인 출처입니다.</li><li>비자연 유입 설치에 기여한 웹 캠페인의 경우, 웹 캠페인은 신규 사용자 획득으로 처리되고 모바일 설치는 크로스 플랫폼 리타겟팅으로 처리됩니다.</li></ul> |
| 소급 재계산 | 기본 30분의 지연 시간 이후에는 과거 데이터 소급 계산이 적용되지 않습니다. | 30분의 지연 시간 이후 어트리뷰션이 최종 확정되며, 이 시간 동안 사용자가 본인을 식별할 수 있는 유예 시간이 제공됩니다. |
| 로우 데이터 필드 | 모바일 관련 필드는 웹에서 더 이상 지원되지 않습니다. 일부 필드명이 변경되고 일부 값이 변경됩니다. | 아래 [로우 데이터 필드 매핑 부록을](#부록-로우-데이터-보고서-변경-사항) 참조하십시오. |
| 후기 S2S 이벤트 | 해당 이벤트가 발생한 UTC 기준 일자가 종료된 후 30분을 초과하여 수신된 이벤트도 수용은 되지만, 해당 이벤트의 발생 시간은 앱스플라이어가 수신한 시간으로 대체됩니다. | 이벤트를 일별로 일괄 업로드하기보다는 이벤트 발생 후 가급적 30분 이내에 실시간으로 전송하는 것을 권장합니다. 정확한 어트리뷰션은 이벤트가 발생한 시점과 최대한 가까운 때에 수신되는 것에 달려 있습니다. 이는 웹 환경의 동작 방식을 기존 모바일 동작 방식과 동일하게 맞추어 줍니다. |

<div id="raw-data-field-mapping" />

## 부록: 로우 데이터 보고서 변경 사항

PBA 로 데이터 리포트(웹사이트 방문 및 웹사이트 이벤트)의 모든 필드를 신규 End User Events 리포트에 1:1로 매핑합니다. 소스: <Anchor target="_blank" href="/marketers/ko/docs/pba-raw-data-reports">PBA 로우 데이터 리포트</Anchor>.

범위: PBA 웹사이트 방문 및 웹사이트 이벤트 리포트.

* **변경되지 않은** 동일한 필드 이름 및 데이터.
* **이름 변경**, 동일한 데이터, 새 열 이름.
* **재정의**, 동일하거나 유사한 이름이지만 데이터 또는 값 형식 변경(재사용 전에 주의 필요).
* **사용 중단**, 보고서에는 이에 상응하는 내용 없음.

| 필드 이름 | 설명 | 상태 | 새 필드/노트 |
| --- | --- | --- | --- |
| `advertising_id` | 광고 ID(GAID) | 사용 중단 | PBA 내에서 교차 플랫폼으로 스티칭된 모바일/디바이스 광고 ID입니다. 크로스 플랫폼 LTV 및 사용자 여정 리포트는 CUID를 기반으로 하며 이 필드를 사용하지 않습니다. |
| `af_web_id` | 웹 SDK에서 전송된 쿠키 ID | 이름 변경됨 | `appsflyer_id_value`, 동일한 웹 쿠키. |
| `amazon_aid` | Amazon Fire TV 광고 ID | 사용 중단 | 모바일/기기 ID, 웹과는 관련 없음. |
| `android_id` | Android 디바이스 ID | 사용 중단 | 모바일/기기 ID, 웹과 관련 없음. |
| `app_id` | 가장 최근에 설치된 앱 ID | 사용 중단 | 모바일 크로스 플랫폼 필드. 신규 리포트의 웹 앱 식별자는 `unified_app_id` ("website-`{domain}`")로, 기존과는 다른 개념입니다. |
| `app_name` | 가장 최근 앱 이름 | 변경되지 않음 | `app_name`. |
| `app_version` | 최신 앱 버전 | 사용 중단 | 모바일 크로스 플랫폼 필드, 웹과 관련 없음. |
| `appsflyer_id` | 앱스플라이어(설치) ID | 사용 중단 | 모바일 설치 ID 신규 `appsflyer_id_value`은(는) 별도의 고유 식별자인 웹 쿠키(`af_web_id`)입니다. |
| `attributed_touch_time` | (어트리뷰션된) 웹 방문 타임스탬프 | 이름 변경됨 | `event_time__attribution`, 어트리뷰션된 터치 (인게이지먼트) 시간. |
| `attributed_touch_type` | 터치포인트 유형, 항상 “웹 방문” | 사용 중단 | PBA의 상수값. Visit-Vs-Event가 이제 `end_user_event_type` (SESSION / IN\_APP) 에 있습니다. |
| `bundle_id` | PBA 번들 ID | 사용 중단 | 크로스 플랫폼 리포트에서 프로덕트 라인 그룹화(웹 + 모바일 앱)로 대체됩니다. |
| `campaign` | 웹사이트 방문 건으로 어트리뷰션됨 | 이름 변경됨 | `campaign_name`. |
| `campaign_id` | 웹사이트 방문 건으로 어트리뷰션됨 | 변경되지 않음 | `campaign_id`. |
| `city` | IP 주소를 사용하여 분석 및 결정됨 | 변경되지 않음 | `city`. |
| `country_code` | IP 주소를 사용하여 해결됨 | 변경되지 않음 | `country_code`. |
| `customer_user_id` | 고객 사용자 식별자(CUID) | 변경되지 않음 | `customer_user_id`. |
| `device_type` | 디바이스 유형 | 이름 변경됨 | `device_category`, 값이 다릅니다 (“데스크톱” vs. "MOBILE\_PHONE" / "TV"). |
| `dma` | IP 주소를 사용하여 해결됨 | 변경되지 않음 | `dma`. |
| `event_name` | 방문: 항상 “웹사이트 방문”. 이벤트: 이벤트 이름 전송됨 | 재정의 | 방문 시 비어 있음(PBA에는 "website visit"으로 기록됨). 이벤트는 변경되지 않았습니다. |
| `event_revenue` | 구매 통화 기준 이벤트 매출 금액 | 이름 변경됨 | `revenue_value_original`. |
| `event_revenue_currency` | `event_revenue`의 3자리 통화 코드 | 이름 변경됨 | `revenue_currency_original`. |
| `event_revenue_usd` | USD로 전환된 `event_revenue` 수익 | 이름 변경됨 | `revenue_usd`. |
| `event_source` | 웹 SDK 또는 서버 간 | 변경되지 않음 | `event_source`. |
| `event_time` | 방문: 방문 시간. 이벤트: 이벤트 시간 | 변경되지 않음 | `event_time`. |
| `event_type` | 표준 이벤트/전환 이벤트/웹 사이트 방문 | 재정의 | 전환 이벤트 표시가 더 이상 존재하지 않습니다. Visit-vs-event가 `end_user_event_type` (SESSION / IN\_APP) 에 있습니다. |
| `event_url` | 이벤트가 발생한 웹페이지의 URL(방문 시 Original URL과 동일) | 변경되지 않음 | `event_url`, 이제 URL 쿼리 파라미터(UTM 등)를 확인하고 읽는 주 영역이기도 합니다. |
| `event_value` | 이벤트: JSON과 같은 이벤트 세부 정보 방문: null | 변경되지 않음 | `event_value`. |
| `idfa` | 광고 식별자 | 사용 중단 | 모바일/기기 ID, 웹과 관련 없음. |
| `idfv` | 광고 식별자 | 사용 중단 | 모바일/기기 ID, 웹과 관련 없음. |
| `imei` | 기기 식별자 | 사용 중단 | 모바일/기기 ID, 웹과 관련 없음. |
| `install_time` | 최근 앱 설치 시간 | 사용 중단 | 모바일 크로스 플랫폼 필드. 웹 사용자 획득(전환) 시간은 `event_time__conversion`, 별도의 개념입니다. |
| `ip` | 방문자 IP 주소 | 이름 변경됨 | `ip_address_value`, 동일한 값 그리고 해싱 방식을 위한 `ip_address_type` |
| `language` | 사용자 에이전트가 보고함(예: '영어') | 재정의 | `language`, 값 형식이 ISO 639-1 및 국가 코드로 변경됩니다. |
| `media_channel` | 웹사이트 방문 건으로 어트리뷰션됨(“Ad”) | 사용 중단 | 필요한 경우 `sub_param_1-5`에 의해 커버할 수 있습니다. |
| `media_source` | 웹사이트 방문 건으로 어트리뷰션됨 | 변경되지 않음 | `media_source`. |
| `media_type` | 웹사이트 방문 건으로 어트리뷰션됨(“Paid”) | 사용 중단 | 웹용으로는 비어 있습니다. 이제 오가닉과 유료 간의 차이가 `is_organic` 불리언으로 바뀝니다. |
| `oaid` | 광고 식별자 | 사용 중단 | 모바일/기기 ID, 웹과 관련 없음. |
| `original_url` | 어트리뷰션된 방문에서 사용자를 리디렉션한 URL | 이름 변경됨 | `event_url`(으)로 통합됩니다 (방문 시 원래 `event_url`은(는) 원래 URL과 같음). 독립형 컬럼은 이제 없습니다. |
| `platform` | 플랫폼 (“macOS", "Windows”) | 재정의 | 플랫폼은 항상 "WEBSITE"입니다. OS가 `os_version` /`user_agent`(으)로 이동했습니다. |
| `postal_code` | IP 주소를 사용하여 해결됨 | 변경되지 않음 | `postal_code`. |
| `query_params` | 리다이렉트 URL의 쿼리 파라미터(JSON 형태) | 사용 중단 | 로우 쿼리 스트링은 `event_url`에 위치하며, 파싱된 JSON 컬럼은 제거되었습니다. |
| `referrer` | 어트리뷰션된 웹사이트 방문의 HTTP 리퍼러 | 이름 변경됨 | `http_referrer`. |
| `region` | IP 주소를 사용하여 분석 및 결정됨 ("NA") | 이름 변경됨 | `continent`, 대륙 코드 (예: “NA”) |
| `state` | IP 주소를 사용하여 해결됨 | 변경되지 않음 | `state`. |

<div id="readytouse-codingagent-prompt-for-data-locker-etl-migration" />

<Accordion title="Data Locker ETL 마이그레이션을 위한 즉시 사용 가능한 코딩 에이전트 프롬프트">

이러한 전환을 더 쉽게 진행하실 수 있도록, AI 코딩 에이전트(Claude Code, Cursor 등)에 바로 사용할 수 있는 프롬프트를 준비했습니다. 에이전트에게 기존 ETL 코드에 대한 접근 권한을 부여하고 아래 프롬프트를 붙여넣으세요. 이 프롬프트에는 전체 필드 매핑 및 모든 동작 차이점이 포함되어 있습니다. 에이전트가 기존 파이프라인을 학습한 후 새로운 리포트에 맞게 다시 구현하도록 가이드합니다.

```
You are migrating an ETL pipeline from AppsFlyer's legacy PBA Data Locker raw-data reports (Website visits + Website events) to AppsFlyer's Web Performance Measurement Data Locker report (End User Events). Everything you need is in this prompt: the structural changes, the complete field-by-field mapping, and the validation steps. Do not guess anything beyond what is written here; if something is ambiguous, ask me.

## Step 1: Learn the current pipeline

Before writing any code, explore the existing codebase and produce an inventory:
1. Which PBA reports we consume (Website visits, Website events, or both) and where they are ingested.
2. Every PBA field we read, and where each is used downstream (transforms, joins, dashboards, alerts, exports).
3. The load cadence and scheduling assumptions (PBA delivered daily).
4. Any logic that separates or joins visit rows and event rows.
5. Any filters, groupings, or hardcoded values keyed on PBA field values (e.g. media_source names, channel labels, event_type, platform values).

Present this inventory to me and wait for my confirmation before proceeding.

## Step 2: Ask me these questions

1. Is the new End User Events report already enabled in Data Locker (enabled from the AppsFlyer UI)? If not, I need to enable it first.
2. What is our new web app's Unified App ID? Format: "website-{domain}" (e.g. website-www.example.com). If I don't know it, I'll get it from the AppsFlyer dashboard before we continue.
3. Do we want a parallel-run period (old and new pipelines side by side, comparing outputs) or a direct cutover? Recommend parallel-run.
4. Should the new pipeline also consume the Conversions report (unique attribution instances, no duplicate rows) or the cross-platform End User Events report (CUID-deduplicated, web+mobile user-level)? Default scope is the platform-level End User Events report, the direct successor of the PBA reports.

## Structural changes to design around

1. **One report instead of two.** PBA split visits and events into two reports. The new End User Events report holds both: visits are rows with end_user_event_type = 'SESSION', events are rows with end_user_event_type = 'IN_APP'. Only IN_APP rows carry a valid event_name; on SESSION rows event_name is empty (PBA wrote "website visit" there).
2. **One schema across platforms.** The report is shared by website, mobile, CTV, and PC. Always filter platform = 'WEBSITE' to isolate web data.
3. **Dual attribution credit, deduplicate.** The same action can appear twice: a primary-credit row and a secondary-credit row (original UA source, for UA-view LTV). Filter is_primary_attribution = true by default to avoid double-counting. Drop the filter only for dedicated UA-view vs retargeting-view analysis using conversion_type.
4. **Hourly instead of daily.** The new report delivers hourly with approximately 2 hours of data freshness. Redesign incremental loads around hourly batches instead of a daily drop.
5. **Organic vs paid.** PBA's media_type ("Paid") is gone. Use the is_organic boolean; never infer organic/paid from media_source.
6. **User counting.** Count and join users with COALESCE(customer_user_id, appsflyer_id_value), the stable customer user ID first, the cookie-based ID as fallback.
7. **Empty values.** STRING fields are '', NUMERIC fields are NULL.

## Field-by-field mapping (PBA → End User Events)

Status legend: Unchanged = same name and data. Renamed = same data, new column. Redefined = data or value format changes (handle with care). Deprecated = no equivalent.

| PBA field | Status | New field / handling |
|---|---|---|
| advertising_id | Deprecated | Mobile/device ID. Cross-platform reports are CUID-based; drop it. |
| af_web_id | Renamed | appsflyer_id_value, same web cookie. |
| amazon_aid | Deprecated | Mobile/device ID, not relevant for web. |
| android_id | Deprecated | Mobile/device ID, not relevant for web. |
| app_id | Deprecated | Mobile cross-platform field. The new web app identifier is unified_app_id ("website-{domain}"), a different concept, not a rename. |
| app_name | Unchanged | app_name. |
| app_version | Deprecated | Mobile cross-platform field. |
| appsflyer_id | Deprecated | Mobile install ID. Note: the new appsflyer_id_value is the web cookie (PBA's af_web_id), NOT this field. |
| attributed_touch_time | Renamed | event_time__attribution. |
| attributed_touch_type | Deprecated | Was a constant. Visit-vs-event now lives in end_user_event_type. |
| bundle_id | Deprecated | Replaced by the Product Line grouping in the cross-platform report. |
| campaign | Renamed | campaign_name. |
| campaign_id | Unchanged | campaign_id. |
| city | Unchanged | city. |
| country_code | Unchanged | country_code. |
| customer_user_id | Unchanged | customer_user_id. |
| device_type | Renamed + values change | device_category, values differ (e.g. "Desktop" → "MOBILE_PHONE" / "TV" style values). Update any value-keyed logic. |
| dma | Unchanged | dma. |
| event_name | Redefined | Events: unchanged. Visits: now empty (PBA wrote "website visit"). Use end_user_event_type = 'SESSION' to identify visits. |
| event_revenue | Renamed | revenue_value_original. |
| event_revenue_currency | Renamed | revenue_currency_original. |
| event_revenue_usd | Renamed | revenue_usd. |
| event_source | Unchanged | event_source. |
| event_time | Unchanged | event_time. |
| event_type | Redefined | "Conversion event" marking no longer exists. Visit-vs-event lives in end_user_event_type (SESSION / IN_APP). |
| event_url | Unchanged | event_url, now also the primary place URL query params (UTMs, etc.) are read from. |
| event_value | Unchanged | event_value. |
| idfa / idfv / imei / oaid | Deprecated | Mobile/device IDs, not relevant for web. |
| install_time | Deprecated | Mobile field. The web user-acquisition time is event_time__conversion, a separate concept. |
| ip | Renamed | ip_address_value (plus ip_address_type for the hashing method). |
| language | Redefined | language, format changes to ISO 639-1 + country code (was e.g. "English"). |
| media_channel | Deprecated | Can be covered by sub_param_1-5 if needed. |
| media_source | Unchanged | media_source (but see value renames below). |
| media_type | Deprecated | Use the is_organic boolean instead. |
| original_url | Renamed | Consolidated into event_url (on visits, event_url equals the original URL). Standalone column gone. |
| platform | Redefined | platform is always "WEBSITE". The OS moved to os_version / user_agent. |
| postal_code | Unchanged | postal_code. |
| query_params | Deprecated | The raw query string lives in event_url; the parsed-JSON column is gone. Re-implement parsing from event_url if needed. |
| referrer | Renamed | http_referrer. |
| region | Renamed | continent, continent code (e.g. "NA"). |
| state | Unchanged | state. |

## Attributed-value changes (update filters and groupings)

The attribution engine resolves traffic sources differently, so some VALUES change even where field names don't:
- media_source renames: doubleclick_int → dv360_int (Google display/video via UTM); "X Ads" → "Twitter" (Twitter via UTM). More PID values now remap to display names (e.g. iossearchads_int → Apple Search Ads, metweb_int → Facebook Ads, tiktokweb_int → tiktokglobal_int, snapweb_int → snapchat_int).
- Channel labels change format: Direct / Organic search / Social media / Email / Ad / Referral / Other become DIRECT / ORGANIC_SEARCH / SOCIAL_MEDIA / EMAIL / AD / REFERRAL / OTHER.
- Click-ID coverage expanded (more networks resolve from click IDs); dclid alone no longer resolves; fbclid is not used.

Scan the codebase for any filter, CASE, join key, or dashboard grouping keyed on these old values and update them.

## Step 3: Build

1. Propose the new ETL design (ingestion, schema, incremental hourly logic, the mandatory filters from "Structural changes").
2. After my approval, implement it, reusing our existing conventions and infrastructure.
3. For every Deprecated field the inventory found in downstream use, list the consumer and propose a resolution (drop, replace with the suggested alternative, or flag to the business owner).

## Step 4: Validate

1. Run both pipelines on the same day range and compare: visits (SESSION rows) vs PBA website visits, events (IN_APP rows) vs PBA website events, and revenue totals.
2. Expect differences, not equality: the new attribution logic is more advanced, so attributed dimensions (media_source, campaign) will not match PBA exactly. Session counting logic is unchanged (30 minutes of activity), so visit volumes should be in the same ballpark.
3. Verify the is_primary_attribution filter is applied everywhere; its absence shows up as inflated event counts.
4. Produce a short migration report: what was mapped, what was dropped, what changed in values, and any open items for the business owner.
```

</Accordion>

<div id="pba-web-s2s-to-new-s2s-api-migration" />

## 부록: PBA 웹-S2S에서 새로운 S2S API로 마이그레이션

PBA Web <Anchor target="_blank" href="/marketers/ko/docs/web-server-to-server-events-api-for-pba-web-s2s">서버 간 이벤트 API(Web-S2S)</Anchor>를 통해 이벤트를 전송 중이신 경우, <Anchor target="_blank" href="/marketers/ko/docs/server-to-server-s2s-api-for-web-performance-measurement">신규 S2S API</Anchor>로 전환하세요. 신규 API는 방문과 이벤트를 모두 지원하므로 웹사이트를 완전한 서버 사이드 방식으로 운영할 수 있습니다. 기존 PBA의 S2S는 이벤트만 수신했습니다.

<div id="endpoints-and-authentication" />

<Accordion title="엔드포인트 및 인증">

|  | PBA Web-S2S | 새로운 S2S API |
| --- | --- | --- |
| 기본 URL | `https://webs2s.appsflyer.com` | `https://events.appsflyer.com` |
| 이벤트 콜 | `POST /v1/{bundleId}/event` | `POST /v2.0/s2s/inapps/app/web/{appId}` |
| 방문 콜 | 제공되지 않음(방문 건은 웹 SDK를 통해서만 수집됨) | `POST /v2.0/s2s/visits/app/web/{appId}` |
| ID 콜 | `POST /v1/{bundleId}/setcuid`(CUID를 웹 사용자와 연결하기 위한 별도 호출) | 없음, 식별자 정보는 모든 이벤트/방문 시 `user_id` 객체 내에 인라인으로 전송됨 |
| 앱 식별자 | `bundleId` 경로 내의 (브랜드 번들 ID) | `appId` = 경로에 있는 웹 `unified_app_id` ("website-`{domain}`") |
| 인증 | `webDevKey` 매 호출 시 JSON 본문 내부 | S2S API 키가 포함된 Authorization 헤더 |
| 콘텐츠 유형 | `application/json` | `application/json` |
| 성공 응답 | 200 OK | 202 수락 |

</Accordion>

<div id="payload-field-mapping" />

<Accordion title="페이로드 필드 매핑">

| PBA 웹-S2S 필드 | 새로운 S2S 필드 | 참고 |
| --- | --- | --- |
| `customerUserId` | `user_id.customer_user_id` | 이제 `user_id` 오브젝트에 중첩됩니다. |
| `afUserId` | `user_id.appsflyer_id` | 이제 `user_id` 오브젝트에 중첩됩니다. `customer_user_id` 또는 `appsflyer_id` 중 최소 하나를 전송해야 하며, 사용자가 식별된 경우에는 두 항목을 모두 전송하세요. |
| `webDevKey` | — | 본문에서 제거되었습니다. 인증 방식이 Authorization 헤더로 이동되었으며, 앱은 경로 내의 `appId` 항목으로 식별됩니다. |
| `eventType`(상시 EVENT) | — | 삭제됨. 엔드포인트(/inapps 또는 /visits)에 따라 유형이 결정됩니다. |
| `eventName` | `event_name` | 1&#126;64자, `@ = + -` 문자는 포함할 수 없습니다. |
| `timestamp`(유닉스 ms, 13자리 숫자) | `timestamp`(유닉스 ms) | 같은 형식. 매 호출 시 권장되며, 생략할 경우 앱스플라이어 수신 시간을 사용합니다. |
| `eventValue` | `event_value` | 자유 형식, `custom_parameters` 하위 오브젝트를 지원합니다. |
| `eventRevenue` | `event_revenue` | 이제 선택 사항입니다(대시보드에는 PBA가 필요함). |
| `eventRevenueCurrency` | `event_revenue_currency` | 이제 선택 사항입니다(대시보드에는 PBA가 필요함). |
| `referrer` | `http_referrer` | 이름 변경됨 |
| `userAgent` | `user_agent` | 이름 변경됨 |
| `ip` | `ip` | 변경되지 않음. |
| — | `event_url` | 신규 방문 건에는 필수, 이벤트 건에는 선택 사항. |
| — | `customer_dedup_id` | 신규 다른 소스(예: 웹 SDK)에서 들어오는 동일한 이벤트와의 중복을 제거합니다. |
| — | `email_hashed`, `phone_number_hashed`, `phone_number_e164_hashed`, `first_name_hashed`, `last_name_hashed` | 신규 식별자 보강을 위해 정규화된 값의 SHA256(64자 소문자 16진수) 형태로 전송합니다. |

</Accordion>

<div id="s2s-api-notes" />

<Accordion title="S2S API 노트">

* **방문은 이제 서버 측에서 이루어집니다.** 기존 PBA S2S는 이벤트만 수신 가능했으며, 방문 데이터는 웹 SDK를 통해서만 전송되어야 했습니다. 새로운 /visits 엔드포인트를 사용하면 웹사이트를 완전한 서버 사이드 방식으로 운영할 수 있습니다.
* **더 이상 setcuid 호출을 사용하지 않습니다.** PBA는 Web SDK가 필수였기 때문에, CUID를 웹 사용자와 연결하려면 별도의 호출이 필요했습니다. 새로운 API는 모든 요청에 식별자 정보를 직접 포함하여 전달하므로 해당 단계가 삭제되었습니다.
* **지연 데이터 윈도우입니다.** 이벤트를 일일 단위로 한 번에 모아서 전송하기보다, 이벤트 발생 후 가급적 30분 이내의 실시간으로 이벤트와 방문 건을 전송하세요. 이벤트가 발생한 UTC 일자의 종료 시점으로부터 30분이 지나 도착한 데이터도 수신은 가능하지만, 이벤트 발생 시간이 AppsFlyer가 수신한 시간으로 대체됩니다.

</Accordion>

<div id="s2s-service-migration-readytouse-codingagent-prompt" />

<Accordion title="S2S 서비스 마이그레이션: 바로 사용할 수 있는 코딩 에이전트 프롬프트">

PBA 서버간 API를 통해 이벤트를 리포트하는 경우 AI 코딩 에이전트(Claude Code, Cursor 등)에 바로 사용할 수 있는 프롬프트를 준비했습니다. 앱스플라이어로 이벤트를 전송하는 서비스에 대한 접근 권한을 에이전트에 부여한 후 아래 프롬프트를 붙여넣으세요. 전체 엔드포인트 및 페이로드 매핑 정보가 포함되어 있습니다. 에이전트가 현재 구현 방식을 파악하고 최신 방식으로 업데이트할 수 있도록 안내합니다.

```
You are migrating a server-side integration from AppsFlyer's legacy PBA Web S2S events API (webs2s.appsflyer.com) to AppsFlyer's new S2S API for Web Performance Measurement (events.appsflyer.com). Everything you need is in this prompt: endpoints, authentication, the complete payload mapping, and the behavior changes. Do not guess anything beyond what is written here; if something is ambiguous, ask me.

## Step 0: Ask me these questions before touching code

1. Should we modify the existing service in place, or create a new service/module alongside it (allowing a parallel-run and clean cutover)? Recommend a new module alongside.
2. Do I know our new web app's Unified App ID? Format: "website-{domain}" (e.g. website-www.example.com). It replaces PBA's bundle ID in the URL path. If I don't know it, I'll get it from the AppsFlyer dashboard before we continue.
3. Do I have the new S2S API key? Authentication moved from the webDevKey in the request body to an Authorization header carrying this key. If I don't have it, I'll retrieve it from the AppsFlyer dashboard.
4. Do we want to send events only (like PBA), or adopt the new visits endpoint too? The new API supports server-side visits, so the website can run fully server-side; PBA accepted events only.
5. Is the AppsFlyer Web SDK still running on our site? (Determines whether visits come from the SDK and whether we need event deduplication between SDK and S2S.)

## Step 1: Learn the current service

Explore the codebase and produce an inventory:
1. Every call site to webs2s.appsflyer.com, the /event calls and any /setcuid calls.
2. The fields populated on each call (customerUserId, afUserId, eventName, eventValue, eventRevenue, timestamp, referrer, userAgent, ip, etc.) and where their values come from.
3. Error handling and monitoring keyed on the 200 OK response.
4. Retry, batching, and queueing behavior.

Present this inventory to me and wait for my confirmation before proceeding.

## What changed: endpoints and authentication

|  | PBA Web-S2S (old) | New S2S API |
|---|---|---|
| Base URL | https://webs2s.appsflyer.com | https://events.appsflyer.com |
| Event call | POST /v1/{bundleId}/event | POST /v2.0/s2s/inapps/app/web/{appId} |
| Visit call | Not available | POST /v2.0/s2s/visits/app/web/{appId} |
| Identity call | POST /v1/{bundleId}/setcuid | None, identity is inline in the user_id object on every call |
| App identifier in path | bundleId (brand bundle ID) | appId = the web Unified App ID ("website-{domain}") |
| Authentication | webDevKey in the JSON body | Authorization header with the S2S API key |
| Content type | application/json | application/json (415 if missing) |
| Success response | 200 OK | 202 Accepted |

## Payload field mapping

| PBA field | New field | Note |
|---|---|---|
| customerUserId | user_id.customer_user_id | Nested in the user_id object. |
| afUserId | user_id.appsflyer_id | Nested in the user_id object. Send at least one of customer_user_id or appsflyer_id; send both whenever the user is identified. |
| webDevKey | (removed) | Auth moved to the Authorization header; the app is identified by appId in the path. |
| eventType (always "EVENT") | (removed) | The endpoint (/inapps vs /visits) determines the type. |
| eventName | event_name | 1-64 chars; cannot contain @ = + - characters. |
| timestamp (Unix ms) | timestamp (Unix ms) | Same format. Recommended on every call; if omitted, AppsFlyer uses receive time. |
| eventValue | event_value | Free-form; supports a custom_parameters sub-object. |
| eventRevenue | event_revenue | Now optional (PBA required it for dashboards). |
| eventRevenueCurrency | event_revenue_currency | Now optional (PBA required it for dashboards). |
| referrer | http_referrer | Renamed. |
| userAgent | user_agent | Renamed. |
| ip | ip | Unchanged. |
| (new) | event_url | Required on visits; optional on events. |
| (new) | customer_dedup_id | Deduplicates against the same event arriving from another source (e.g. the Web SDK). |
| (new) | email_hashed, phone_number_hashed, phone_number_e164_hashed, first_name_hashed, last_name_hashed | SHA256 (64-char lowercase hex) of normalized values, for identity enrichment. |

## Behavior changes and gotchas

1. **appId is the Unified App ID, not the "Web SDK ID".** The AppsFlyer app settings page shows a "Web SDK ID" UUID (the former Web Dev Key, kept for SDK continuity). The S2S path must carry the Unified App ID ("website-{domain}"), never that UUID. A 401 "app not found" usually means a wrong appId in the path or a missing/invalid Authorization header.
2. **Success is 202, not 200.** Update health checks, retries, and alerting accordingly.
3. **Don't validate against the old endpoint.** The legacy endpoint may still return 200, but that response is not proof that data reached Web Performance Measurement. Always verify events actually appear in the new web app's data.
4. **Drop the setcuid flow entirely.** Identity travels inline in the user_id object on every event and visit.
5. **Visits before events.** The system expects a visit before any event from a user; events for a user with no prior visit are classified as organic. Visits come from the Web SDK, or, new, from the /visits endpoint.
6. **Send in real time; don't batch.** Send every event and visit as it happens, preferably within 30 minutes of the event occurring. Data that arrives later than 30 minutes after the end of the UTC day in which the event occurred is still accepted, but its event time is replaced with the receive time, which distorts attribution. Always send a timestamp. Note that the approximately 30-minute attribution delay you may read about is a separate, server-side hold on AppsFlyer's side, nothing for us to implement.
7. **Full server-side option (if we adopt visits).** With no Web SDK, our server owns the web user identifier: generate a stable ID for first-time visitors, persist it as a server-set first-party HTTP cookie (Set-Cookie header, not JavaScript; JS cookies are capped at approximately 7 days on Safari), reuse it on every request, and send it as user_id.appsflyer_id. The visit payload must include event_url (and should include ip, user_agent, http_referrer for attribution quality).
8. **SDK + S2S together.** If both send the same event, populate customer_dedup_id so AppsFlyer keeps one copy.

## Step 2: Build

1. Propose the design: new client/module, config (base URL, appId, API key storage in our secrets manager, never hardcoded), payload builders for events (and visits, if in scope), and the response/retry handling for 202.
2. After my approval, implement it following our existing conventions.
3. Map every field from the inventory through the payload mapping above; flag any field we currently send that has no new equivalent.

## Step 3: Validate

1. Send a test event (and visit, if in scope) and confirm a 202 response.
2. Verify the test data appears in the new web app in AppsFlyer (dashboard or Data Locker); this is the real success signal, not the HTTP response.
3. Confirm event names comply with the new constraints (1-64 chars, no @ = + -).
4. If running in parallel with the old service, compare event volumes between old and new for a few days before cutover, then decommission the old calls including setcuid.
```

</Accordion>

<div id="traffic-source-resolution-pba-vs-web-performance-measurement" />

## 부록: 트래픽 소스 해상도, PBA vs. 웹 성과 측정

미디어 소스, 채널 또는 캠페인 값이 기존 PBA 보고서 내용과 다른 경우 원인은 다음과 같습니다. 두 방식 모두 동일한 기본 메커니즘을 사용합니다. 웹 방문 시 URL 파라미터와 리퍼러 정보를 기반으로 우선순위 목록을 순차적으로 확인하여 가장 먼저 일치하는 미디어 소스를 판별합니다. 하지만 몇 가지 규칙이 변경되었으며, 이러한 변경 사항으로 인해 리포트에서 확인되는 값이 달라집니다. 소스: <Anchor target="_blank" href="/marketers/ko/docs/pba-media-source-attribution-rules">PBA 미디어 소스 어트리뷰션 규칙</Anchor> 및 <Anchor target="_blank" href="/marketers/ko/docs/about-traffic-source-resolution">트래픽 소스 식별</Anchor>

<div id="media-source-values-renamed" />

<Accordion title="미디어 소스 값 이름 변경됨">

| 트리거 | PBA 값 | 신규 값 |
| --- | --- | --- |
| Google 디스플레이/비디오(utm\_source=Google + utm\_medium= cpm / display/banner/video/listing) | `doubleclick_int` | `dv360_int` |
| UTM을 통한 트위터(twitter + cpc) | X Ads | Twitter |

웹 성과 측정 기능은 더 많은 PID 값을 표시 이름으로 매핑합니다. 예를 들어 `iossearchads_int`은(는) Apple Search Ads(으)로, `metweb_int`은(는) Facebook Ads(으)로, `twitterweb_int`은(는) Twitter(으)로 `tiktokweb_int`은(는) `tiktokglobal_int`(으)로, `snapweb_int`은(는) `snapchat_int`(으)로 변환됩니다. 기존 원시 값을 기준으로 작성된 리포트는 변경된 새로운 값을 반영해야 합니다.

</Accordion>

<div id="click-id-coverage-expanded-and-dclid-dropped" />

<Accordion title="클릭 ID 수집 범위가 확대되었으며, dclid 지원은 중단되었습니다.">

PBA는 세 가지 클릭 ID를 식별했습니다: `gclid`은(는) `googleadwords_int`(으)로, `dclid`은(는) `doubleclick_int`(으)로, `msclkid`은(는) `bingsearch_int`(으)로 매핑합니다.

웹 성과 측정은 훨씬 더 많은 항목을 식별합니다. `gclid`/`wbraid`/`gbraid`은(는) `googleadwords_int`(으)로, `msclkid`은(는) `bingsearch_int`(으)로, `twclid`은(는) Twitter로, `vmcid`은(는) `yahoogemini_int`(으)로, `sccid`은(는) `snapchat_int`(으)로, `li_fat_id`은(는) `linkedin_int`(으)로, `ttclid`은(는) `tiktokglobal_int`(으)로, `tbclid`은(는) `taboola_int`(으)로, `ob_click_id`/`dicbo`(은)는 `outbrain_int`(으)로, `yclid`은(는) `yandex_int`(으)로, `rdt_cid`은(는) `reddit_int`(으)로 매핑합니다.

> ❗️ **경고**
>
> 두 가지 동작 변경 사항: `dclid`은(는) 더 이상 단독으로 트래픽 소스 식별에 사용되지 않으며(PBA에서는 이를 `doubleclick_int`(으)로 식별했음), `fbclid`은(는) 명시적으로 사용되지 않습니다.

</Accordion>

<div id="utm-custom-rules-expanded" />

<Accordion title="UTM 맞춤 규칙 확장">

웹 성과 측정에서는 맞춤 `utm_source` + `utm_medium` 매핑 범위가 더 넓어졌습니다. 기존 PBA의 제한적인 단일 매체 규칙을 넘어 더 다양한 매체 동의어(paid, paid\_search, paid-search 등)를 포함하며 TikTok, Snapchat, Pinterest에 대한 지원이 추가되었습니다. 맞춤 규칙이 일치하지 않는 경우, 두 방식 모두 기존의 원시 `utm_source` 값을 기본값으로 사용합니다.

</Accordion>

<div id="channel" />

<Accordion title="채널">

채널 **값**의 형식도 변경됩니다. 기존 PBA의 Direct / Organic search / Social media / Email / Ad / Referral / Other 형태에서 대문자 및 언더바 기반의 DIRECT / ORGANIC\_SEARCH / SOCIAL\_MEDIA / EMAIL / AD / REFERRAL / OTHER 형식으로 바뀝니다. 기존 라벨을 기준으로 설정된 필터 및 그룹화 조건은 업데이트가 필요합니다.

</Accordion>

<div data-zendesk-anchors="why-were-upgrading-your-web-measurement=%EC%9B%B9-%EC%B8%A1%EC%A0%95%EC%9D%84-%EC%97%85%EA%B7%B8%EB%A0%88%EC%9D%B4%EB%93%9C%ED%95%98%EB%8A%94-%EC%9D%B4%EC%9C%A0 h_01KYM7JM37WVTV7XHEHVTPKWM9=%EC%9B%B9-%EC%B8%A1%EC%A0%95%EC%9D%84-%EC%97%85%EA%B7%B8%EB%A0%88%EC%9D%B4%EB%93%9C%ED%95%98%EB%8A%94-%EC%9D%B4%EC%9C%A0 h_01KYM7JM375VPAAVQEN43F2X73=%EC%B0%B8%EA%B3%A0 h_01KYM7JM37WTAX6JTQFZJ189TK=%EC%A4%91%EC%9A%94 web-performance-measurement-vs-pba=%EC%9B%B9-%EC%84%B1%EB%8A%A5-%EC%B8%A1%EC%A0%95-vs-pba h_01KYM7JM3711FXC132MSC3B4A8=%EC%9B%B9-%EC%84%B1%EB%8A%A5-%EC%B8%A1%EC%A0%95-vs-pba migration-steps=%EB%A7%88%EC%9D%B4%EA%B7%B8%EB%A0%88%EC%9D%B4%EC%85%98-%EB%8B%A8%EA%B3%84 h_01KYM7JM37HG8YAX02XMSKBTPP=%EB%A7%88%EC%9D%B4%EA%B7%B8%EB%A0%88%EC%9D%B4%EC%85%98-%EB%8B%A8%EA%B3%84 h_01KYM7JM37ZHHDBR961W2XGWPN=%EC%B0%B8%EA%B3%A0-1 capabilities-being-discontinued=%EC%A7%80%EC%9B%90-%EC%A4%91%EB%8B%A8%EB%90%98%EB%8A%94-%EA%B8%B0%EB%8A%A5 h_01KYM7JM37JJ25D3RFE2V7BM4D=%EC%A7%80%EC%9B%90-%EC%A4%91%EB%8B%A8%EB%90%98%EB%8A%94-%EA%B8%B0%EB%8A%A5 appendix-raw-data-reports-changes=%EB%B6%80%EB%A1%9D-%EB%A1%9C%EC%9A%B0-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B3%A0%EC%84%9C-%EB%B3%80%EA%B2%BD-%EC%82%AC%ED%95%AD h_01KYM7JM37Z7Z21FJ2G83T2WPG=%EB%B6%80%EB%A1%9D-%EB%A1%9C%EC%9A%B0-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B3%A0%EC%84%9C-%EB%B3%80%EA%B2%BD-%EC%82%AC%ED%95%AD h_01KYM7JM38PDKMST3E5CWN3NC1=readytouse-codingagent-prompt-for-data-locker-etl-migration appendix-pba-web-s2s-to-new-s2s-api-migration=%EB%B6%80%EB%A1%9D-pba-%EC%9B%B9-s2s%EC%97%90%EC%84%9C-%EC%83%88%EB%A1%9C%EC%9A%B4-s2s-api%EB%A1%9C-%EB%A7%88%EC%9D%B4%EA%B7%B8%EB%A0%88%EC%9D%B4%EC%85%98 h_01KYM7JM38K9C01XDZY99KZVTX=%EB%B6%80%EB%A1%9D-pba-%EC%9B%B9-s2s%EC%97%90%EC%84%9C-%EC%83%88%EB%A1%9C%EC%9A%B4-s2s-api%EB%A1%9C-%EB%A7%88%EC%9D%B4%EA%B7%B8%EB%A0%88%EC%9D%B4%EC%85%98 h_01KYM7JM38NY2VQKWGV884M79N=endpoints-and-authentication h_01KYM7JM38RBC9SCJ3YESYP68H=payload-field-mapping h_01KYM7JM38H9EJZDF9441XBRHQ=s2s-api-notes h_01KYM7JM38RS0DZ13ZW228S9EB=s2s-service-migration-readytouse-codingagent-prompt appendix-traffic-source-resolution-pba-vs-web-performance-measurement=%EB%B6%80%EB%A1%9D-%ED%8A%B8%EB%9E%98%ED%94%BD-%EC%86%8C%EC%8A%A4-%ED%95%B4%EC%83%81%EB%8F%84-pba-vs-%EC%9B%B9-%EC%84%B1%EA%B3%BC-%EC%B8%A1%EC%A0%95 h_01KYM7JM387R5YEYJK9CD0AQJ0=%EB%B6%80%EB%A1%9D-%ED%8A%B8%EB%9E%98%ED%94%BD-%EC%86%8C%EC%8A%A4-%ED%95%B4%EC%83%81%EB%8F%84-pba-vs-%EC%9B%B9-%EC%84%B1%EA%B3%BC-%EC%B8%A1%EC%A0%95 h_01KYM7JM388C143S76GH58DEZB=media-source-values-renamed h_01KYM7JM380B4S13JDW9FWHMWT=click-id-coverage-expanded-and-dclid-dropped h_01KYM7JM3889HC2VTC1QN9JAZG=%EA%B2%BD%EA%B3%A0 h_01KYM7JM38CNVZ43EFK0HMJ3VY=utm-custom-rules-expanded h_01KYM7JM38E9P4MS4Q6TNZ1TH1=channel" />
