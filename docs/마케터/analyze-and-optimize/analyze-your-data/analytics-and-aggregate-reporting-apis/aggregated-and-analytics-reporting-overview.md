---
title: 집약형 분석 리포트 개요
metadata:
  keywords:
    - Agencies
    - Ad Networks
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
    - Agencies
    - Ad Networks
  created_at: '2020-02-04T09:38:14Z'
  edited_at: '2026-10-14T10:33:29Z'
  id: 360005437257
  locale: ko
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/ko/articles/360005437257
---
> **한눈에 보기:** 요약: 집약형 분석 어트리뷰션 리포트, 도구 및 API 사용에 대한 설명 및 비교.


<span id="aggregated-and-analytics-performance-reporting-tools-and-reports"></span>플랫폼의 집약형 분석 도구는 광고주에게 앱, 캠페인 및 사용자의 성과를 평가할 수 있는 지표를 제공합니다.

도구는 데이터가 표시되는 방식에 따라 다릅니다. 예를 들어, 개요 대시보드는 캠페인(LTV)의 유저 생애 가치 지표를 제공하는 반면, 코호트는 시간에 따른 사용자 인게이지먼트를 분석하는 데 사용됩니다.

본 기사에서 구체적으로 설명한 도구는 플랫폼에서 내보낼 수 있는 데이터와 관련됩니다. 툴 비교표를 참고하면 주요 기능과 각 툴 간의 차이점을 이해하실 수 있습니다.

<div id="toolapi-comparison" />

<Accordion title="리포트 방법 비교">

다음 표에서는 집계 데이터를 가져오기 위한 다양한 리포트 방법 및 대시보드에 대해 설명합니다.

[표를 CSV 파일로 다운로드하여](https://docs.google.com/spreadsheets/d/e/2PACX-1vSICicxcvD0996RT59fTLDJvdGUKxqPqr47f5SMD8BmsbZtrWIoxRxJEo7tAXTBBmnIbiH097VtK6L9/pub?output=xlsx) 다양한 리포트 방법을 비교 및 대조하는 데 도움이 되는 다양한 사양과 제한 사항을 설명하는 추가 필드를 확인할 수 있습니다.

다운로드 가능한 CSV 파일의 추가 사양 필드는 다음과 같습니다.

* 데이터 최신성 데이터 최신성:이벤트 발생과 리포트 방법을 통해 데이터를 사용할 수 있게 되는 시간 사이의 기간입니다.
* LTV/<Anchor target="_blank" href="/marketers/ko/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">활동</Anchor>
* <Anchor target="_blank" href="/marketers/ko/docs/retargeting-attribution-guide">리타겟팅</Anchor>: 리타게팅: 리타게팅(리인게이지먼트 및 리어트리뷰션) 데이터를 표시할지 여부를 설정합니다.
* 에이전시 투명성 사 에이전시명성: 마케터가 에이전시에서 파생된 트래픽에 대한 원본 미디어 소스의 ID를 볼 수 있는지 여부를 설정합니다.
* <Anchor target="_blank" href="/marketers/ko/docs/about-data-freshness-and-timezone-support#date-and-timezone-principles">시간대</Anchor>: 시간대: 데이터를 표시하는 데 사용되는 시간대(UTC 또는 앱에서 선택한)입니다.
* 캠페인 이름 변경

| 리포트 메서드 | 설명 |
| --- | --- |
| 개요 대시보드 | 선택된 날짜 범위 중 인스톨, 리인게이지 또는 리어트리뷰트하는 사용자의 유저 생애 가치(LTV). |
| <Anchor target="_blank" href="/marketers/ko/docs/master-api-user-acquisition-metrics-via-api">마스터 API</Anchor>  <br />프리미엄 기능 | 선택한 LTV, 액티비티, 리텐션, 코호트, 및 Protect360 캠페인 성과 KPI를 API별로 CSV 또는 JSON 형식으로 가져옵니다. |
| <Anchor target="_blank" href="/marketers/ko/docs/pull-api-aggregate-data">Pull API 통합 리포트</Anchor> | CSV 파일을 설치하거나, 리인게이지하거나, 리어트리뷰트하는 유저 평생 가치(LTV)입니다. UA와 리타게팅 데이터는 별개입니다. 통합 옵션이 없습니다. |
| <Anchor target="_blank" href="/marketers/ko/docs/aggregated-data-export-page">데이터 내보내기 페이지 - 집약형 리포트</Anchor> | CSV 파일을 설치하거나, 리인게이지하거나, 리어트리뷰트하는 유저 평생 가치(LTV)입니다. UA와 리타게팅 데이터는 별개입니다. 통합 옵션이 없습니다. |
| <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">SKAN</Anchor>  <br />개요 | 초기 사용자 측정 기간 동안 iOS SKAN 포스트백 및 추가 데이터 포인트를 통해 리포트된 지표입니다. |
| <Anchor target="_blank" href="/marketers/ko/docs/skan-aggregated-performance-report-api">SKAN</Anchor>  <br /><Anchor target="_blank" href="/marketers/ko/docs/skan-aggregated-performance-report-api">SKAN (스카이칸)</Anchor>집약 데이터 API | 초기 사용자 측정 기간 동안 iOS SKAN 포스트백 및 추가 데이터 포인트를 통해 리포트된 지표입니다. |
| <Anchor target="_blank" href="/marketers/ko/docs/protect360-dashboard">Protect360 대시보드</Anchor> | 사기성 트래픽과 관련된 지표 및 인사이트.  <br />인스톨에 대한 LTV 기반 데이터, 인앱 이벤트에 대한 활동 기반 데이터. |
| <Anchor target="_blank" href="/marketers/ko/docs/activity-dashboard">액티비티 대시보드</Anchor> | 선택한 날짜 범위의 앱 활동, 인게이지먼트 및 인앱 지표입니다. |
| 이벤트 대시보드 | 선택한 기간 동안 앱을 설치한 사용자의 LTV 데이터를 기반으로 한 미디어 소스 전반의 인앱 이벤트 실적 지표입니다. |
| 리텐션 대시보드 | 설치 후 각 날짜에 대한 고유한 사용자 참여(세션) 메트릭입니다. |
| <Anchor target="_blank" href="/marketers/ko/docs/cohort-and-retention-dashboard">코호트 대시보드</Anchor> | 설치 후 매일 다양한 코호트 LTV 유저 지표. |
| <Anchor target="_blank" href="/marketers/ko/docs/cohort-api">코호트 API</Anchor>  <br />프리미엄 기능 | 설치 후 매일 다양한 코호트 LTV 유저 지표. |
| 프리미엄 기능 | 설치 후 매일 다양한 코호트 LTV 유저 지표. |
| 프리미엄 기능 | LTV. |
| <Anchor target="_blank" href="/marketers/ko/docs/custom-dashboards">커스텀 대시보드</Anchor> | LTV 사용자 획득 지표가 포함된 맞춤형 대시보드. |
| 피벗 리포트  <br />프리미엄 기능 | 대시보드 또는 CSV를 통해 선택한 LTV, 활동, 리텐션 및 Protect360 캠페인 성과 KPI. |
| <Anchor target="_blank" href="/marketers/ko/docs/set-up-and-use-roi360-cost-etl-reports">Cost ETL</Anchor> | 미디어 원본당 사용할 수 있는 최상의 세분성을 가진 캠페인 비용 데이터입니다. |
| 사용량 리포트 | 앱스플라이어의 모든 사용량 기반 기능의 조합으로, 청구 주기 기간 동안 계약 의무에 영향을 미칩니다. |
|  |  |

</Accordion>

다음 표에 차이점을 기재했습니다.

| 특성 | 데이터 락커에서 코호트 분석 | 데이터 락커의 고급 집계 리포트 | 코호트 대시보드 | 코호트 API |
| --- | --- | --- | --- | --- |
| 다중 또는 단일 앱 | 다중 앱 데이터는 단일 파일로 앱마다 그룹화되거나 앱당 별개의 파일로 분리됩니다. | 다중 앱 데이터는 단일 파일로 앱마다 그룹화되거나 앱당 별개의 파일로 분리됩니다. | 다중 앱 성과가 결합되거나 앱 옵션별로 그룹화됩니다. | 단일 |
| 그룹화 | 전체 캠페인 계층 및 이벤트 이름. | 전체 캠페인 계층 및 이벤트 이름. | 4개 그룹 | 7개 그룹 |
| 사용 가능 지표 | 모든 지표 | 모든 지표 | 뷰당 선택 가능한 지표 1개 및 고정 지표 4개 | 콜당 선택 가능한 지표 1개 및 고정 지표 4개 |
| 사용 가능한 일별 포스트 어트리뷰션(코호트 일) | 365 | 1095 | 180 | 180 |
| 데이터 내보내기 제한 | 전체 데이터 세트를 사용할 수 있습니다. | 전체 데이터 세트를 사용할 수 있습니다. | 수동 다운로드 및 설정 | 속도 및 응답 크기 제한 |
| 사용자정의 가능 요청 | 아니요 | No | Yes | 예 |


### 유저 여정 리포트

설명한 리포트들은 데이터 다운로드 페이지 또는 Pull API 종합 리포트 항목에서 사용할 수 있습니다.

* * UA 및 프로텍트360 리포트는 인스톨 날짜
  * 리타겟팅 리포트는 리어트리뷰션 또는 리인게이지먼트 날짜

<div id="ua-ltv-aggregate-data-reports-containing-nonorganic-and-organic-users" />

<Accordion title="논오가닉 및 오가닉 유저를 포함하는 UA LTV 종합 데이터 리포트">

<table><thead><tr><th>리포트 이름</th><th>조회 기준</th></tr></thead><tbody><tr><td>파트너 - 미디어소스별</td><td>에이전시, 미디어 소스, 캠페인</td></tr><tr><td>파트너 - 날짜별</td><td>날짜, 에이전시, 미디어 소스, 캠페인</td></tr><tr><td>일별 액티비티</td><td>날짜, 에이전시, 미디어 소스, 캠페인</td></tr><tr><td>지역</td><td>국가, 에이전시, 미디어 소스, 캠페인</td></tr><tr><td>지역 - 날짜별</td><td>날짜, 국가, 에이전시, 미디어 소스, 캠페인</td></tr><tr><td>뷰-쓰루 어트리뷰션 (VTA) KPI</td><td><a href="./pull-api-aggregate-data" target="_blank">VTA 리포트는 풀 API에서 가능</a></td></tr><tr><td colspan="2"> <strong>참고</strong>:  </td></tr></tbody></table>

CSV 파일의 날짜 필드는 yyyy-mm-dd 형식입니다. 엑셀에서 CSV 파일을 열면, 컴퓨터의 날짜 및 시간 설정을 사용하여 날짜 필드의 형식이 지정됩니다. <Anchor target="_blank" href="https://support.office.com/en-us/article/format-a-date-the-way-you-want-8e10019e-d5d8-47a1-ba95-db95123d273e#ID0EAACAAA=Windows">엑셀에서</Anchor> 적절한 날짜 표시를 선택하십시오.

#### 종합 리포트 예시

[스프레드 시트 형식의 리포트 예시](https://docs.google.com/spreadsheets/d/e/2PACX-1vQmzRons779Dk5QWVoPsOF8E7yJLwNPB1IF87shZr6rcMJLjszlSNIbAMVcdeQLysr8Bc4QAby5QB4u/pub?output=xlsx)

#### UA 종합 리포트 필드

<table><colgroup><col/><col/><col/><col/><col/><col/><col/></colgroup><thead><tr><th rowspan="2">필드</th><th rowspan="2">설명</th><th colspan="5"><strong>리포트 이름</strong></th></tr><tr><th><strong>파트너 (미디어 소스)</strong></th><th><strong>날짜 별 파트너</strong></th><th><strong>일일</strong></th><th><strong>지역</strong></th><th><strong>지역 - 날짜별</strong></th></tr></thead><tbody><tr><td>국가</td><td>인스톨 국가</td><td> </td><td> </td><td> </td><td>✓</td><td> ✓</td></tr><tr><td>날짜</td><td>어트리뷰션 날짜</td><td> </td><td>✓</td><td> </td><td> </td><td>✓</td></tr><tr><td>Agency/PMD (af_prt)</td><td>에이전시/파트너 이름</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Media Source (pid)</td><td>유저를 유입시킨 미디어 소스 (pid=미디어 소스)</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>캠페인</td><td><p>캠페인 이름</p><p>(c= 캠페인 이름)</p></td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>캠페인 ID</td><td>메타 캠페인 ID  </td><td>메타 광고 전용</td><td>메타 광고 전용</td><td>메타 광고 전용</td><td>메타 광고 전용</td><td>메타 광고 전용</td></tr><tr><td>Adgroup ID</td><td>메타 광고그룹 ID 또는 광고 ID</td><td>메타 광고 전용</td><td>메타 광고 전용</td><td>메타 광고 전용</td><td>메타 광고 전용</td><td>메타 광고 전용</td></tr><tr><td>Adgroup Name</td><td>메타 광고그룹</td><td>메타 광고 전용</td><td>메타 광고 전용</td><td>메타 광고 전용</td><td>메타 광고 전용</td><td>메타 광고 전용</td></tr><tr><td>광고세트 ID</td><td>메타 광고 세트 ID</td><td>메타 광고 전용</td><td>메타 광고 전용</td><td>메타 광고 전용</td><td>메타 광고 전용</td><td>메타 광고 전용</td></tr><tr><td>Adset name</td><td>메타 광고 세트 이름</td><td>메타 광고 전용</td><td>메타 광고 전용</td><td>메타 광고 전용</td><td>메타 광고 전용</td><td>메타 광고 전용</td></tr><tr><td>ARPU</td><td>사용자당 평균 수익</td><td>✓</td><td>✓</td><td> </td><td>✓</td><td>✓</td></tr><tr><td>평균 eCPI</td><td>평균 eCPI</td><td> </td><td>✓</td><td> </td><td> </td><td> </td></tr><tr><td>클릭</td><td>클릭 수</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>전환율</td><td>앱 설치 수/클릭 수</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>CTR</td><td>광고 클릭률</td><td> </td><td>✓</td><td>✓</td><td> </td><td> </td></tr><tr><td></td><td>이벤트를 수행한 고유 유저 수</td><td>✓</td><td>✓</td><td> </td><td>✓</td><td>✓</td></tr><tr><td></td><td>이벤트 횟수</td><td>✓</td><td>✓</td><td> </td><td>✓</td><td>✓</td></tr><tr><td></td><td>XXX 통화로 이벤트 매출 (XXX는 앱 별 선택된 통화)</td><td>✓</td><td>✓</td><td> </td><td>✓</td><td>✓</td></tr><tr><td>노출</td><td>노출 수</td><td>✓</td><td>✓</td><td> </td><td>✓</td><td>✓</td></tr><tr><td>인스톨</td><td>설치 수</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>로열 유저</td><td>[기본 설정] 앱을 3번 이상 오픈한 유저</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Loyal Users/Installs</td><td>로열 유저 비율</td><td>✓</td><td>✓</td><td> </td><td> </td><td> </td></tr><tr><td>ROI (투자수익률)</td><td>투자 자본 수익률 (Return on investment)</td><td>✓</td><td>✓</td><td> </td><td> </td><td> </td></tr><tr><td>세션</td><td><ul><li>논오가닉 앱 오픈 횟수</li><li>오가닉 및 논오가닉 세션은 코호트 애널리틱스에서 확인 가능</li></ul></td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Total Cost</td><td>-</td><td>✓</td><td>✓</td><td> </td><td> </td><td> </td></tr><tr><td>총수익</td><td>미디어 소스 및 캠페인에서 생성된 총 수익</td><td>✓</td><td>✓</td><td> </td><td>✓</td><td>✓</td></tr><tr><td colspan="7"> <strong>참고:</strong>  참고: '메타 광고만'을 표시하는 열은 메타 광고를 유일한 미디어 소스로 선택할 때 포함됩니다.</td></tr></tbody></table>

</Accordion>

리타게팅 리포트는 <Anchor target="_blank" href="/marketers/ko/docs/retargeting-attribution-guide#retargeting-reports-and-raw-data">리타게팅 캠페인</Anchor>에 참여했고, 리인게이지먼트 또는 리어트리뷰션을 수행한 사용자로 이루어져 있습니다.

리타게팅 리포트에서 오가닉과 논오가닉 사용자 간 차이가 없습니다.

Pull API를 통해 리포트를 리타게팅하려면 성과 리포트 URI에 *&reattr=true* 파라미터를 추가하십시오.

#### 종합 LTV 리타겟팅 리포트

| 리포트 이름 | 조회 기준 |
| --- | --- |
| 파트너 - 미디어소스별 | 에이전시, 미디어 소스, 캠페인 |
| 파트너 - 날짜별 | 날짜, 에이전시, 미디어 소스, 캠페인 |
| 날짜 별 액티비티 | 날짜, 에이전시, 미디어 소스, 캠페인 |
| 국가 | 국가, 에이전시, 미디어 소스, 캠페인 |
| 국가 별, 날짜 별 | 날짜, 국가, 에이전시, 미디어 소스, 캠페인 |

#### 종합 LTV 리타겟팅 리포트

| 필드 | 설명 | 파트너 | 일일 | 파트너 - 날짜별 | 지역 - 날짜별 | 지역 |
| --- | --- | --- | --- | --- | --- | --- |
| 날짜 | 전환 날짜 | - | - | ✓ | ✓ | - |
| 국가 |  | - | ✓ |  | ✓ | ✓ |
| Agency/PMD (af\_prt) | 에이전시/파트너 이름 | ✓ | ✓ | ✓ | ✓ | ✓ |
| Media Source (pid) |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| 캠페인 (c) |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| 클릭 |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| 전환 |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Conversion type (전환 타입) | Re-attribution 또는 re-engagement | ✓ | ✓ | ✓ | ✓ | ✓ |
| 전환율 | 전환 수/클릭 수 | ✓ | ✓ | ✓ | ✓ | ✓ |
| 세션 |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| 로열 유저 |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Loyal Users/Installs |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Total Cost |  | - | - | - | - | - |
| 평균 eCPI |  | - | - | - | - | - |
| Total revenue |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| ROI (투자수익률) |  | - | - | - | - | - |
| ARPU |  | ✓ | ✓ | ✓ | - | ✓ |


## 기능 리포트

<div id="skadnetwork" />

<Accordion title="SKAdNetwork">

<Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-solution-guide#reporting-options">SKAdNetwork 집약형 리포트</Anchor>

</Accordion>

<div id="protect360-blocked-fraud" />

<Accordion title="프로텍트360— 프로드 차단">

![](https://theme.zdassets.com/theme_assets/245528/ffbbc473bb0e74b9fb636ed735f69e9af6a25a18.png)

차단된 집약형 사기 리포트는 <Anchor target="_blank" href="/marketers/ko/docs/protect360-anti-fraud-guide">Protect360</Anchor>에 의해 차단된 이벤트의 상세 내역을 제공합니다.

리포트는 Pull API에서 가능합니다. 이런 리포트는 데이터 내보내기 페이지에서는 사용할 수 없습니다.

날짜 기간은 인스톨 날짜 기준입니다.

#### Pull API를 통해 사용 가능한 집약형 Protect360 리포트

| 리포트 이름 |
| --- |
| 파트너 - 미디어소스별 |
| 파트너 - 날짜별 |
| 지역 |
| 지역 - 날짜별 |
| 파트너 캠페인 리포트 |

**제약: 제한 사항: 차단 이유** Bots /strong>은, 그 이유가 **앱 버전** 이나 **고객 사용자 id 누락**인 경우에도 표시될 수 있습니다.

</Accordion>

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/configuring-meta-campaign-management-partners">Meta 캠페인 관리 파트너 구성</Anchor>
> * <Anchor target="_blank" href="/marketers/ko/docs/raw-data-reporting-overview">로데이터 리포팅 개요</Anchor>

<div data-zendesk-anchors="aggregated-and-analytics-performance-reporting%E2%80%94tools-and-reports=aggregated-and-analytics-performance-reporting-tools-and-reports 01EWA9VQ2HH93525BMK6WN0P6S=aggregated-and-analytics-performance-reporting-tools-and-reports 01ED4D7W8B53Q81G7PXQH8ADE2=toolapi-comparison user-journey-reports=%EC%9C%A0%EC%A0%80-%EC%97%AC%EC%A0%95-%EB%A6%AC%ED%8F%AC%ED%8A%B8 01ED4D7W8CVAQ9V2GCEX1G6KD7=%EC%9C%A0%EC%A0%80-%EC%97%AC%EC%A0%95-%EB%A6%AC%ED%8F%AC%ED%8A%B8 h_01HDNYFR9KBMWAFXDNNJN8VA2X=ua-ltv-aggregate-data-reports-containing-nonorganic-and-organic-users examples-of-aggregate-reports=%EC%A2%85%ED%95%A9-%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EC%98%88%EC%8B%9C 01ED4D7W8C3ZNBYR3CMHJF3QSE=%EC%A2%85%ED%95%A9-%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EC%98%88%EC%8B%9C fields-in-ua-aggregate-reports=ua-%EC%A2%85%ED%95%A9-%EB%A6%AC%ED%8F%AC%ED%8A%B8-%ED%95%84%EB%93%9C h_01HDNYFR9KTQ7ZF35C7E7M7AF1=ua-%EC%A2%85%ED%95%A9-%EB%A6%AC%ED%8F%AC%ED%8A%B8-%ED%95%84%EB%93%9C aggregate-ltv-retargeting-reports=%EC%A2%85%ED%95%A9-ltv-%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%EB%A6%AC%ED%8F%AC%ED%8A%B8 h_01HDNYFR9MSJWCP3JA4M1WXN1H=%EC%A2%85%ED%95%A9-ltv-%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%EB%A6%AC%ED%8F%AC%ED%8A%B8 aggregate-ltv-retargeting-reports::b2093953=%EC%A2%85%ED%95%A9-ltv-%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%EB%A6%AC%ED%8F%AC%ED%8A%B8-1 h_01HDNYFR9MSK9VQQ0Q889Z55TN=%EC%A2%85%ED%95%A9-ltv-%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%EB%A6%AC%ED%8F%AC%ED%8A%B8-1 feature-reports=%EA%B8%B0%EB%8A%A5-%EB%A6%AC%ED%8F%AC%ED%8A%B8 h_01HDNYFR9MYXVZ5BA9FDZ6D82M=%EA%B8%B0%EB%8A%A5-%EB%A6%AC%ED%8F%AC%ED%8A%B8 01ED4D7W8CBH7Q8D31VX5313WP=skadnetwork protect360%E2%80%94blocked-fraud=protect360-blocked-fraud h_01HDNYFR9MJNKGR7XFCACVP6KT=protect360-blocked-fraud aggregate-protect360-reports-available-via-pull-api=pull-api%EB%A5%BC-%ED%86%B5%ED%95%B4-%EC%82%AC%EC%9A%A9-%EA%B0%80%EB%8A%A5%ED%95%9C-%EC%A7%91%EC%95%BD%ED%98%95-protect360-%EB%A6%AC%ED%8F%AC%ED%8A%B8 h_01HDNYFR9MSZ9K8F283J0WBHCZ=pull-api%EB%A5%BC-%ED%86%B5%ED%95%B4-%EC%82%AC%EC%9A%A9-%EA%B0%80%EB%8A%A5%ED%95%9C-%EC%A7%91%EC%95%BD%ED%98%95-protect360-%EB%A6%AC%ED%8F%AC%ED%8A%B8 h_01HDNYYJXVY9XHX87K06NXYQNS=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
