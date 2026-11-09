---
title: 코호트 및 리텐션 대시보드
metadata:
  keywords:
    - Cohort
    - Cohort Report
    - Advertisers
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2015-12-24T10:20:01Z'
  edited_at: '2026-10-14T10:40:12Z'
  id: 207040496
  locale: ko
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/ko/articles/207040496
---
> **요약: 한눈에 보기: 코호트 및 리텐션 대시보드(간단히 "코호트"라고도 함)는 획득 날짜별로 앱 사용자를 그룹화합니다. 사용자 라이프사이클(LTV) 전반에 걸쳐 성과 분석을 수행합니다. 코호트 대시보드를 이용하여 캠페인별로 성과 지표에 미치는 영향을 비교 분석할 수 있습니다.**

cohort main (2).png

<div id="cohort-and-retention-dashboard" />

## 코호트 및 리텐션 대시보드

관련 문서: <Anchor target="_blank" href="/marketers/ko/docs/aggregated-and-analytics-reporting-overview#cohort-flavors">코호트 개념 사이의 차이</Anchor>

코호트 및 리텐션을 사용하려면 하나 이상의 앱에서 사용자를 선택하고 전환 시간별로 분류합니다. 수익, ROI, 이벤트 전환율과 같은 코호트 분석 지표를 사용할 수 있습니다. 캠페인이나 미디어소스 같은 기준으로 코호트를 나누어 비교합니다. 이렇게 하여 사용자 또는 캠페인의 라이프 사이클에 걸친 패턴이나 성과 변화를 발견할 수 있습니다. <Anchor target="_blank" href="https://www.appsflyer.com/blog/cohort-report-mobile-marketing-kpis/?utm_campaign=Blog%20Subscription%2003-2019&utm_source=hs_email&utm_medium=email&utm_content=76370689&_hsenc=p2ANqtz-8SX49xuEw2WX_Vrlh11_zxlDFvlfMpBzSQm1I-nFhc0WbZDf0ACC-VEi4qmKhesHCsUNdhU50Oinl-urwnGAOZMwwHSTp6UgdChCi7ARayJFUFTus&_hsmi=76370689">코호트 사용 사례</Anchor>를 참조하세요.

<div id="tip" />

> 👍 **팁**
>
> 코호트 보고서에 대해 자세히 알고 싶으십니까? 앱스플라이어 학습 포털에서 짧지만 유익한 <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7804/play/18625/your-users-journey-with-retention-and-cohort-reports">과정</Anchor>을 확인해 보세요.

<div id="using-cohort" />

## 코호트 사용하기

<div id="setting-up-an-analysis" />

<Accordion title="분석 설정하기">

1. 앱스플라이어의 사이드 메뉴에서 > **리텐션** **분석을** 선택합니다.   
   코호트 대시보드가 열립니다. 세분성 및 전환 날짜 기간이 표시됩니다.  
   <Image align="center" alt="mceclip0__1_.png" src="https://files.readme.io/4113fd619422979d6a26004a55c009ebc48eef59d10ddc7c3e5becd2a758e6d4-32127949494417.png" />
2. [코호트 분석 기간 세분성](/docs/cohort-and-retention-dashboard#cohort-periods)을 선택합니다.
   * Hours
   * 시간(일)
   * 주
   * 월
3. 어트리뷰션 기간(유저 인입 또는 리타게팅 인게이지먼트)을 선택합니다. 최신 일자와 관련된 데이터는 차트와 테이블에서 대시(-)로 표시되는 [부분 데이터](/docs/cohort-and-retention-dashboard#partial-data)로 나타날 수 있습니다.
4. **Edit Cohort**(코호트 편집)을 클릭합니다.  
   코호트 설정창이 열립니다.  
   <Image align="center" alt="CohortSetup.jpg" src="https://files.readme.io/f09cc190770d16a2ddf60e1f210f458114ac43d4c19fc5507fb50b0d1d2f5c77-32127949495825.jpg" width="365px" />
5. 다음을 완료하세요.
   * * **User acquisition**
     * **리타겟팅**
     * 통합 통합: 사용자 어트리뷰션과 리타게팅 어트리뷰션의 인앱이벤트를 포함합니다. **참고**: 일러두기: 리타게팅 이벤트가 유저 인입 (UA) 이벤트보다 우선됩니다. 즉, 리포트는 is\_primary\_attribution=true를 포함하는 이벤트를 포함합니다.
   * [추세 유형](/docs/cohort-and-retention-dashboard#trend-types):
     * **User lifetime performance**.
     * **KPI by attribution time**.
   * 1개 이상의 앱을 선택합니다. **모두** 계정의 상위 100개 앱을 의미합니다. **참고**: 일러두기: 에이전시는 오직 하나의 앱만 선택할 수 있습니다.
   * 조회 기준  미디어 소스
   * 최소 코호트 크기 중요하지 않은 (너무 작은) 코호트들로 리포트가 어수선해지는 것을 방지합니다.
   * 선택 필드:
     * 기본 설정된 필터는 없습니다.
6. **변경 적용**을 클릭합니다.
7. 코호트 분석을 수행할 지표(KPI)를 선택합니다. 인앱이벤트의 경우 인앱이벤트와 지표를 선택합니다.
8. 데이터를 보려는 코호트 분석 기간을 선택합니다. 변환 후 몇 시간, 며칠, 몇 주 또는 몇 달을 의미합니다. 선택할 수 있는 코호트 기간의 수는 선택한 추세 유형에 따라 다릅니다.
9. **부분 데이터**를 포함할지 아니면 전체 데이터(이미 종료된 코호트 기간의 **데이터** )만 표시할지 선택합니다. 부분 데이터와 전체 데이터에 대해 자세히 알아보세요.
10. **누적** 또는 요일(시간/**일** /주/월) 데이터를 표시할지 여부를 선택합니다.
    * "누적".
    * on\_day 요일: 해당 날짜에 대한 지표 값입니다. 즉, 코호트 3은 코호트 기간 3의 메트릭만 보여줍니다. 이전 기간에 일어난 일은 계산하지 않습니다.
11. **히트 맵**을 표시할지 여부를 선택합니다.
12. 데이터를 표 또는 차트로 볼지 여부를 선택합니다. 테이블을 선택하면 25, 50, 100 또는 200 중에서 표시할 데이터 행 수를 선택할 수 있습니다.
13. [선택사항] [저장된 코호트 리포트 관리](/docs/cohort-and-retention-dashboard#using-my-reports-save-and-select-reports).

</Accordion>

<div id="using-my-reports-save-and-select-reports" />

<Accordion title="'내 리포트' 기능—리포트 저장 및 선택">

* 내 리포트(My reports)는 나중에 사용할 수 있도록 현재 대시보드 설정을 저장할 수 있는 기능입니다.
* 저장된 보고서를 선택하여 최신 코호트 데이터를 조회하십시오.
* 하나 이상의 리포트를 저장할 수 있습니다.
* 그 리포트를 만든 사람만이 내 리포트(My reports)에 접속할 수 있습니다.

| 기능 | 설명 |
| --- | --- |
| 내 리포트 | MyReports.png<br /><br />사용 가능한 최신 데이터를 표시하려면 리포트를 선택하십시오. |
| 변경 사항 저장 | 리포트를 저장합니다. 참고: 일러두기: 현재 선택한 리포트로 덮었습니다. |
|  | <ul><li>**새로 저장**<ul><li>다른 리포트 이름을 사용하여 리포트 저장</li><li>[선택사항] 이 보고서를 기본 보고서로 설정</li></ul></li><li>피봇 이름 수정</li><li>코호트 대시보드를 열 때, 처음 나타나는 리포트입니다.</li><li>**삭제**</li></ul> |

</Accordion>

<div id="export-the-cohort-to-a-csv-file" />

<Accordion title="CSV 파일로 코호트 내보내기">

* 코호트 리포트는 CSV 파일로 내보낼 수 있습니다.
* [partial이라는 접미사(suffix)가 있는 열 이름은 UI의 차트와 테이블에서 대시(-)로 표시됩니다.](/docs/cohort-and-retention-dashboard#partial-data)

**코호트 리포트를 CSV 파일로 내보내려면:**

* CSV 파일의 코호트 리포트가 다운로드 됩니다.

</Accordion>

<div id="cohort-concepts" />

## 코호트 개념

<div id="cohort-periods" />

<Accordion title="코호트 기간">

변환 기간을 0(시간 0, 0일, 0주 또는 0개월)이라고 합니다. 변환 후 다음 기간을 1(시간 1, 1일, 1주 또는 1개월) 등이라고 합니다.

사용 가능한 기간 수는 선택한 기간 단위에 따라 다릅니다.

* 시간 단위의 경우 최대 변환 후 시간은 72시간입니다.
* 일 단위의 경우 최대 변환 후 일수는 180일입니다.
* 주 단위의 경우 최대 변환 후 주 수는 156주입니다
* 월 단위의 경우 최대 변환 후 개월 수는 36개월입니다

**참고**: 앱스플라이어에서 코호트 기간은 특정 인스톨 타임스탬프를 고려하지 않습니다. 대신 코호트 시간은 가장 가까운 시간으로 반올림되며 코호트 일, 주 및 월은 달력 일, 주 또는 월을 기준으로 합니다. 이로 인해 앱스플라이어 코호트 데이터를 다른 네트워크의 코호트 데이터와 비교할 때 불일치가 발생할 수 있으며, 여기서 모든 코호트 기간은 특정 설치 타임스탬프에 의해 결정됩니다(즉, 한 시간은 설치 타임스탬프 후 60분, 하루는 설치 타임스탬프 후 24시간 설치 후 기간입니다).

</Accordion>

<div id="view-types" />

<Accordion title="보기 유형">

3가지 코호트 보기 유형이 있습니다.

* **통합**:
  * 유저 유입과 리타겟팅 캠페인 통합 성과 (비용 및 수입 포함)
  * 어떤 이벤트가 두가지 전환 유형 모두에 해당되는 경우, 리타겟팅 이벤트만 포함됩니다. 즉 리포트는 실제 마지막 터치 미디어소스를 사용하여 생성됩니다. 로데이터에 익숙하다면 이것은 <Anchor target="_blank" href="/marketers/ko/docs/raw-data-reporting-overview">is\_primary\_contribution=true</Anchor>인 이벤트를 의미합니다.
* **유저 유입:** 사용자 획득: 설치의 성능 데이터(<Anchor target="_blank" href="/marketers/ko/docs/measure-reinstalls#attributed-to-the-first-install">특별하게 활성화되지 않은 경우</Anchor> 재설치 제외)
* **리타게팅** 리타게팅:  리어트리뷰션이나 리인게이지먼트의 성과 데이터

<Image align="center" alt="OV.png" src="https://files.readme.io/738bf91c1a12671b32b088993c43d4103498907a8bbe15821ddc53a0b071b876-32127949500305.png" />

</Accordion>

<div id="trend-types" />

<Accordion title="추세 유형">

2가지 코호트 추세 유형이 있습니다.

* **사용자 창출 가치**
* **어트리뷰션 날짜별 KPI**

<div id="user-lifetime-performance" />

#### **사용자 창출 가치**

* 표의 각 열 또는 차트의 포인트는 다른 코호트 기간(시간/일/주/월)을 나타냅니다. 이렇게 하면 전환 기간부터 시작하여 전환 후 사용자 실적을 비교할 수 있습니다.
* 데이터를 가져올 코호트 기간을 각 세부 수준 옵션(시간/일/주/월)에 대해 최대값까지 선택할 수 있습니다.

<div id="kpi-by-attribution-time" />

#### **어트리뷰션 날짜별 KPI**

* 표의 각 열 또는 차트의 포인트는 선택한 날짜 범위의 기간에 대한 코호트 기간(시간/일/주/월)을 나타냅니다. 이를 통해, 시간 경과에 따른 캠페인 성과를 평가하고 전환 시점 관련 상대적인 캠페인 KPI를 볼 수 있습니다.
* 데이터를 얻기 위해 선택할 수 있는 최대 코호트 기간 수는 5개입니다.

<div id="example-user-lifetime-performance-trend-vs-kpi-by-attribution-time-trend" />

#### 예시:

이 예시에서는, 동일한 로데이터를 사용하여 두가지 코호트 트렌드 유형을 만들었습니다. 로데이터 표는 서로 다른 사용자 A, B, C, D와 관련된 어트리뷰션 이벤트를 표시합니다. 이 사용자들은 광고에 참여하고 앱을 설치했으며, 후속 전환으로 하나 이상의 구매를 했습니다. 코호트 day 0은 인스톨 날짜입니다.

<Image align="center" alt="CohortExample_en-us.jpg" src="https://files.readme.io/7542605e2bb3972dc90fb12c9d6a328ff52ec65f0694a79752380d548e72e286-32127949500817.jpg" />

</Accordion>

<div id="partial-data" />

<Accordion title="부분 데이터 vs. 전체 데이터">

전환 데이터 기간의 어떤 날에 전환일 이후 경과된 일수가 코호트 일보다 적은 경우, 코호트 일은 부분 데이터를 포함합니다. 부분 데이터는 코호트 일 > 현재 일 - 전환 일인 날에 발생합니다.

부분/전체 데이터 컨트롤을 사용하여 데이터 표시 모드를 선택합니다.

* [기본값] **부분:**
  * 어트리뷰션 데이터는 수익을 포함하여 실시간으로 지속적으로 업데이트됩니다.
  * 비용 데이터는 평균 4시간마다 한 번씩, 하루 6번 업데이트됩니다.
  * 부분 데이터(테이블 및 차트에서 대시로 표시)가 포함됩니다.
* **완료:** 일일: 데이터가 매일 업데이트되며 자정 후 몇 분 뒤 조회 가능합니다. 부분 날짜의 데이터는 표시되지 않습니다.

</Accordion>

<div id="list-of-dimensions-for-grouping-and-filtering" />

<Accordion title="조회 및 필터링 기준이 되는 디멘션">

| 디멘션 | 설명 | 그룹별로 | 필터링 기준 |
| --- | --- | --- | --- |
| <span id="ad"></span>Ad |  | ✓ | ✓ |
| <span id="ad-id"></span>광고 ID |  | ✓ | ✓ |
| <span id="adset"></span>광고세트 |  | ✓ | ✓ |
| <span id="adset-id"></span>광고세트 ID |  | ✓ | ✓ |
| <span id="agency"></span>에이전시 |  | ✓ | ✓ |
| <span id="apps"></span>앱 | 리포트가 다수의 앱을 포함한 경우 유용합니다. | ✓ | **x** |
| <span id="attributed-touchtype"></span>Attributed touch-type | 값: 값: Click, impression, 또는 N/A (organic) | ✓ | ✓ |
| <span id="campaign"></span>캠페인 |  | ✓ | ✓ |
| <span id="campaign-id"></span>캠페인 ID |  | ✓ | ✓ |
| <span id="channel"></span>채널 |  | ✓ | ✓ |
| <span id="conversion-type"></span>전환 유형 | 코호트 유형에 종속적.<ul><li>유저 유입: 인스톨</li><li>**리타겟팅**: 리인게이지먼트 및 리어트리뷰션</li></ul> | ✓ | ✓ |
| <span id="country-geo"></span>지역 | 사용자 IP 주소 기반 | ✓ | ✓ |
| <span id="time-in-the-case-of-daily-granularity-is-the-date-hourly-granularity-is-the-hour-of-the-day-weekly-granularity-is-the-week-of-the-year-monthly-granularity-is-the-month-of-the-year"></span>시간. 다음의 경우:<ul><li>일별 세분성은 날짜입니다.</li><li>시간별 세분성은 하루 중 시간입니다.</li><li>주별 세분성은 해당 연도의 주입니다.</li><li>월별 세분성은 해당 연도의 월입니다.</li></ul> | 코호트 유형에 종속적.<ul><li>**리타겟팅**: Retargeting(라타게팅): 리인게이지먼트 이후에 앱이 처음으로 실행된 시간입니다.</li></ul> | ✓ | **x** |
| <span id="install-app-store"></span>애플 앱 스토어 설치 | 안드로이드 <Anchor target="_blank" href="/marketers/ko/docs/set-up-multi-store-android-attribution">멀티 스토어 어트리뷰션</Anchor>을 구현하는 앱에 대한 관련성입니다. 이 기준을 활성화하려면 CSM에 문의하십시오. | ✓ | ✓ |
| <span id="keywords"></span>키워드 | 연동 파트너가 제공한 검색 키워드. | ✓ | ✓ |
| <span id="media-source"></span>미디어 소스 |  | ✓ | ✓ |
| <span id="revenue-type"></span>수익 유형 |  | **x** | ✓ |
| <span id="site-id"></span>사이트 ID |  | ✓ | ✓ |
| <span id="sub-param-1"></span>Sub Param 1 |  | ✓ | ✓ |

</Accordion>

<div id="metrics-available" />

<Accordion title="사용 가능 지표">

| 지표 | 설명 |
| --- | --- |
| 인스톨 | 선택한 시간 범위 동안의 설치 수 |
| 리타게팅 전환 | 선택한 시간 범위 동안의 리타게팅 전환(리어트리뷰션 및 리인게이지먼트) 수 |
| 어트리뷰션 | 선택한 시간 범위 동안의 설치, 리인게이지먼트 및 리어트리뷰션 수 |
| 비용 | <ul><li>클릭 및 API를 통해 앱스플라이어에 보고된 캠페인 비용</li><li>다음과 같은 경우에는 사용할 수 없습니다.<ul><li>뷰 유형은 리타게팅입니다.</li><li>세분성은 시간입니다.</li></ul></li></ul> |
| 평균 eCPI |  |
| 수익 | 앱스플라이어에 보고된 수익(설정에 따라 누적 또는 당일) |
| 수익 카운트 | 수익 이벤트가 발생한 횟수(설정에 따라 누적 또는 일) |
| ARPU | 유저 당 평균 수익. 수익\자 고유 사용자 |
| 평균 수익 카운트 | 앱스플라이어에 보고된 평균 수익 이벤트 수(설정에 따라 누적 또는 당일) |
| 세션 수(누적) | 앱이 실행되거나, 디바이스 포그라운드로 이동하거나, 개발자가 설정한 기타 측정값의 누적 횟수 |
| 평균 세션(누적) | 사용자가 앱을 실행하거나, 기기 포그라운드로 가져오거나, 개발자가 설정한 기타 측정값의 평균 횟수(누적) |
|  | 앱이 실행되거나, 디바이스 포그라운드로 이동하거나, 개발자가 설정한 기타 측정값이 발생한 날짜의 횟수 |
| 평균 세션(당일) | 사용자당 앱이 실행되거나, 기기 포그라운드로 이동하거나, 개발자가 설정한 기타 측정 횟수(당일) |
| 잔존율 | 리텐션 비율 유지율: 당일 앱을 연 순 사용자 수/전환수 * 100 |
| ROI (투자수익률) | <ul><li>ROI (투자수익률)(%). (수익 - 비용)\/비용 * 100</li><li>다음과 같은 경우에는 사용할 수 없습니다.<ul><li>뷰 유형은 리타게팅입니다.</li><li>세분성은 시간입니다.</li></ul></li></ul> |
| ROAS | <ul><li>광고 지출 수익률(%). 수익\/비용 * 100</li><li>다음과 같은 경우에는 사용할 수 없습니다.<ul><li>뷰 유형은 리타게팅입니다.</li><li>세분성은 시간입니다.</li></ul></li></ul> |
| 앱 삭제 횟수 | <ul><li>앱을 설치하고 나중에 앱을 제거하는 앱 사용자 수(사용자 획득에만 해당됨).</li><li>다음과 같은 경우에는 사용할 수 없습니다.<ul><li>보기 유형이 리타게팅 또는 통합입니다.</li><li>세분성은 시간입니다.</li></ul></li></ul> |
| 평균 앱 삭제 횟수 | <ul><li>앱을 설치하고 나중에 앱을 제거하는 앱 사용자 수(사용자 획득에만 해당됨).</li><li>다음과 같은 경우에는 사용할 수 없습니다.<ul><li>보기 유형이 리타게팅 또는 통합입니다.</li><li>세분성은 시간입니다.</li></ul></li></ul> |
| IAE 수 | 인앱이벤트가 수행된 횟수(누적 또는 당일, 설정에 따라 다름) |
| 평균 IAE 수 | 인앱 이벤트가 수행된 평균 횟수(설정에 따라 누적 또는 일) |
| IAE 수익 | 인앱이벤트에서 생성된 수익(누적 또는 당일, 설정에 따라 다름) |
| 평균 IAE 수익 | 인앱이벤트에서 발생한 평균 수익(누적 또는 당일, 설정에 따라 다름) |
| IAE 고유 사용자 수 | 인앱이벤트를 수행하는 순 사용자 수(누적 또는 당일, 설정에 따라 다름) |
| IAE 전환(누적) | 인앱 이벤트 전환 (In-app event conversion) |
| IAE 전환(당일) | 인앱 이벤트 전환 (In-app event conversion) |
| eCPA | 액션당 유효 비용(이벤트). |

</Accordion>

<div id="additional-information" />

## 추가 정보

<div id="cohort-for-agencies" />

<Accordion title="에이전시를 위한 코호트">

* 코호트를 사용하려면, 광고주가 에이전시 권한을 부여해야합니다.
  * 에이전시에게 권한을 부여하려면, 광고주는 다음을 진행합니다.
    1. 앱스플라이어의 측면 메뉴에서 **협업** > **활성화된 연동**을 선택하세요.
    2. 에이전시를 선택합니다.
    3. 권한 탭으로 이동하여, **Allow access to your retention and cohort reports(리텐션 및 코호트 리포트 액세스 허용)** 를 활성화합니다.
* 에이전시는 에이전시에서 생성된 트래픽 데이터에만 액세스할 수 있습니다. 오가닉 트래픽 또는 다른 곳에서 생성된 논오가닉 트래픽과 관련된 데이터는 볼 수 없습니다.

</Accordion>

<div id="use-cases" />

<Accordion title="활용 사례">

<div id="revenue-sum-by-geo" />

#### 지역별 수익 합계

차트 차트: 사용자 1인당 누적 수익

Screenshot 2023-10-23 at 9.59.01.png

표

cohort use case 3.png

<div id="in-app-event-conversion" />

#### 인앱 이벤트 전환 (In-app event conversion)

광고주는 인앱이벤트 af\_purchase를 정의합니다. 코호트 테이블에는 코호트에서 구매한 앱 사용자의 비율이 표시됩니다. 예를 들어, 10일째 되는 날에는 Facebook 광고 미디어소스에 기여한 코호트 사용자의 36.27%가 구매를 수행했음을 알 수 있습니다[.](https://support.appsflyer.com/hc/article_attachments/51857267497873)

cohort use case 3.png

</Accordion>

<div id="faq" />

<Accordion title="자주 묻는 질문">

| 질문 | 답변 |
| --- | --- |
| Apple Search Ads <Anchor target="_blank" href="/marketers/ko/docs/apple-ads-integration-setup#analyze-keyword-cost">키워드 비용 및 ROI</Anchor>를 볼 수 있습니까? | 예, 가능합니다.  <br />Apple Search Ads는 앱스플라이어에 캠페인/광고 세트/광고로 쪼갠 일별 키워드 각각의 비용을 제공합니다. **참고: 메모: 지역별 분석은 사용할 수 없습니다.** |
| 어떤 미디어소스의 경우, 왜 동일한 캠페인 이름이 두 번 이상 표시됩니까? | <ul><li>만약 서로 다른 캠페인 ID를 가진 캠페인들에게 동일한 캠페인 이름을 사용하는 경우, 이름이 두 번 이상 표시됩니다.</li><li>캠페인 ID 별로 고유한 이름을 지정하십시오.</li><li>캠페인 이름을 변경하는 경우, 데이터는 가장 나중에 사용된 이름으로 정렬됩니다.</li></ul> |
| 오가닉 유저를 볼 수 있나요? | 오가닉 유저는 기본적으로 코호트 리포트에 포함됩니다.<br /><br />**코호트 리포트를 오가닉 유저에만 제한하려면 다음을 수행하십시오.**<ol><li>**코호트 대시 보드** 에서 **코호트 편집** 버튼을 클릭합니다.</li><li>**변경 적용**을 클릭합니다.</li></ol> |
| 삭제된 인스톨의 데이터를 볼 수 있습니까? | 데이터 리텐션 정책으로 인해 삭제된 SRN의 인스톨 또는 GDPR에서 삭제된 인스톨과 같은 삭제된 인스톨은 코호트 대시보드에서 볼 수 없습니다.<br /><br />더 자세한 정보는 <Anchor target="_blank" href="/marketers/ko/docs/user-level-data-retention#파트너-데이터-리텐션-기간">여기</Anchor>를 클릭하여 볼 수 있습니다. |
| 일일 보기 데이터를 주간 또는 월간 보기 데이터와 비교할 수 있나요? | 코호트 LTV가 정렬되지 않으므로 일일 세분성에서 주간 또는 월별 세분성과 데이터를 비교하는 것은 쉽지 않습니다. |
|  |  |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="특징 및 제약 사항">

| 특징 | 비고 |
| --- | --- |
| 코호트에 대한 애드 네트워크 액세스 | 사용 불가 |
| 에이전시 액세스 | 사용 가능<ul><li>하나의 앱으로 제한됩니다.</li><li>하이브리드 계정은 코호트를 사용할 수 없습니다.</li><li>앱 별로 액세스 권한이 필요합니다.</li><li>여러 앱을 선택할 수 없습니다.</li><li>유기적 데이터에 대한 액세스는 불가능합니다.</li></ul> |
| 에이전시 투명성 | 2021년 1월 10일부터 사용 가능 |
| 앱별 시간대 | <ul><li>사용 가능</li><li>예외: 다음의 모든 경우에, 앱스플라이어는 앱 별 설정된 시간대를 무시하고 기본 시간대를 UTC +0 으로 사용합니다.<ul><li>코호트 리포트가 여러 앱을 포함하고 있는데, 이 앱들이 각각 다른 시간대를 가지고 있습니다.</li><li>앱이 모두 동일한 시간대를 사용하고 있지만, 하나 이상의 앱이 리포트 기간 이내에 시간대를 변경했습니다. 리포트 기간을 결정하는 것은 다음과 같습니다.<ul><li>시작날짜</li><li>종료일. 종료 날짜: 전환일 기간의 마지막 날짜에 표시 기간의 일수를 더하여 계산합니다. 예시: 2007년 1월 7일 종료일. 2007년 1월</li></ul></li><li>주간 및 월간 데이터는 UTC 시간대로 표시됩니다.</li></ul></li></ul> |
| 비용 | <ul><li>코호트에서 비용 데이터는 관련 어트리뷰션(설치, 리인게이지먼트 또는 리어트리뷰션)이 있는 경우에만 포함됩니다. 다시 말해 캠페인이 클릭과 노출을 기반으로 비용을 발생시키지만 어트리뷰션이 없는 경우 비용은 코호트 리포트에 포함되지 않습니다. 이 원칙은 모든 수준의 광고 계층에 적용됩니다.</li><li>앱스플라이어는 코호트 리포트 또는 코호트 API에서 대문자가 포함된 키워드에 대한 비용 데이터를 보고하지 않습니다.</li></ul> |
| 앱별 통화 | <ul><li>사용 가능</li><li>그렇지 않은 경우 USD가 사용됩니다.</li></ul> |
| CSV 파일 다운로드 | <ul><li>최대 10,000행입니다.</li><li>사용자 전체 기간 실적 리포트에만 사용할 수 있습니다. KPI by attribution time(어트리뷰션 시간별 KPI) 트렌드는 사용할 수 없습니다.</li><li>CSV 내보내기는 분당 10개, 사용자당 하루 100개로 제한됩니다.</li></ul> |
| 차트 | 차트는 해당 코호트에서 앱 사용자 수에 의한 순위에서 상위 5 내 10을 표시합니다. 이는 표시된 기준과 무관합니다. |
| 표 | 테이블에는 최대 200개의 행이 표시됩니다. 인스톨, 리타게팅 전환 또는 어트리뷰션(코호트 뷰 유형에 따라 다름), 비용, 평균 eCPI(유효 설치당 비용)는 선택한 지표에 관계없이 항상 표시됩니다. |
| 재설치 | <ul><li>재설치 후 이벤트가 속성이 없는 오가닉이라고 간주되는 경우:<ul><li>2024년 5월 26일부터 포함됩니다. <Anchor target="_blank" href="/marketers/ko/docs/bulletin-cohort-data-includes-unattributed-sessions-and-events">더 알아보기</Anchor></li><li>설치 시간은 <Anchor target="_blank" href="/marketers/ko/docs/raw-data-field-dictionary#device-info::dfd9504e">device\_download\_time</Anchor> 필드를 기반으로 합니다.</li><li>고유 사용자 및 유지 측정에 포함되지 않습니다.</li></ul></li><li>재설치 후 이벤트가 첫 설치에 속하는 경우 항상 포함됩니다. <Anchor target="_blank" href="/marketers/ko/docs/unique-users">더 알아보기</Anchor></li></ul> |
| 데이터 쿼리 | 분당 20개의 데이터 쿼리와 사용자당 하루 500개의 데이터 쿼리로 제한됩니다. 기간, 그룹화, KPI 등을 변경하는 것은 새 쿼리로 간주됩니다. |
| 오가닉 데이터 | 포함 |
| 논오가닉 데이터 | 포함 |
| 데이터 최신성 | <ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-freshness-and-timezone-support#eod">실시간</Anchor></li><li>예외:<ul><li>일일 코호트:<ul><li>비용, 광고 수익, 앱 삭제 지표는 매일 업데이트됩니다.</li><li>제거는 UTC 시계를 사용하여 하루에 한 번 계산됩니다.</li></ul></li><li>주간 및 월간 코호트:<ul><li>실시간 데이터를 사용할 수 없습니다. 데이터는 완료된 후에만 표시됩니다(IE 주말 또는 월말).<br />그러나 일부 데이터가 완료(설치 후 시간)되고 다른 데이터는 아직 시작되지 않은 등 일부 설치 데이터가 완료된 데이터는 표시됩니다.</li></ul></li></ul></li></ul> |
| 과거 데이터 | <ul><li>일일 코호트: 2년</li><li>3년</li></ul> |
| 지역 | <ul><li>사용 가능</li><li>지역을 알 수 없는 경우(N/A) 지역별로 그룹화할 때 광고 수익 데이터가 표시되지 않습니다.</li></ul> |
| 세션 집계 | 리타게팅 뷰에서 제0일의 세션 수가 사용자 수보다 적을 수 있습니다.<br />이런 일이 발생할 수 있는 몇 가지 이유가 있습니다. 가장 일반적인 이유는 다음과 같습니다.<ul><li>리인게이지먼트 세션은 리인게이지먼트가 기록되기 전에 이미 어트리뷰트되었습니다. 이 경우 리타겟팅 세션에 어트리뷰트되지 않습니다.</li><li>**세션 간 최소 시간**과 같은 다른 설정으로 필터링. 이 경우 리인게이지먼트가 기록됩니다. 그러나 세션이 필터링되어 기록되지 않습니다.</li></ul> |
| 리타게팅 및 통합 데이터 | 2021년 9월 1일 이후의 날짜만 월간 세션 날짜로 선택할 수 있습니다. |
| 광고 수익 | <ul><li>시간별 세분성으로 코호트를 볼 때는 사용할 수 없습니다.</li><li>코호트 및 개요 대시보드에 표시되는 광고 수익 금액 간에 불일치가 있을 수 있습니다. 이는 네트워크가 UTC로 수익을 보고하고 앱의 시간대 설정이 다른 경우에 발생합니다.</li><li>af\_ad\_revenue 이벤트의 경우 집계 유형이 다음과 같은 경우 고유 사용자 지표를 사용할 수 없습니다.<ul><li>"누적".</li><li>"당일"은 2022년 10월 5일부터 2023년 2월 16일 사이의 날짜입니다.</li></ul></li></ul> |
| 주 및 월 세분성 | <ul><li>주 및 월 세분성은 코호트 대시보드에서만 사용할 수 있습니다.</li><li>**고유 사용자** 및 **전환율** 측정항목은 데이터에 2022년 11월 이전의 인스톨 수가 포함된 경우 사용할 수 없습니다.</li><li>과거 데이터는 2021년 이후에만 사용할 수 있습니다.</li><li>제한됩니다.</li></ul> |
| 코호트 기간 | <ul><li>변환 기간을 0(시간 0, 0일, 0주 또는 0개월)이라고 합니다. 변환 후 다음 기간을 1(시간 1, 1일, 1주 또는 1개월) 등이라고 합니다.</li><li>앱스플라이어에서 코호트 기간은 특정 인스톨 타임스탬프를 고려하지 않습니다. 대신 코호트 시간은 가장 가까운 시간으로 반올림되며 코호트 일, 주 및 월은 달력 일, 주 또는 월을 기준으로 합니다. 이로 인해 앱스플라이어 코호트 데이터를 다른 네트워크의 코호트 데이터와 비교할 때 불일치가 발생할 수 있으며, 여기서 모든 코호트 기간은 특정 설치 타임스탬프에 의해 결정됩니다(즉, 한 시간은 설치 타임스탬프 후 60분, 하루는 설치 타임스탬프 후 24시간 설치 후 기간입니다).</li></ul> |
| 인앱 이벤트 이름 | 권장 사항: |
| 필터 |  |
| 부분 데이터 |  |
| 이벤트 |  |

</Accordion>

<div data-zendesk-anchors="cohort-dashboard=%EC%BD%94%ED%98%B8%ED%8A%B8-%EB%B0%8F-%EB%A6%AC%ED%85%90%EC%85%98-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C 01H7T5AGP75A36TVWSM7H81E8P=%EC%BD%94%ED%98%B8%ED%8A%B8-%EB%B0%8F-%EB%A6%AC%ED%85%90%EC%85%98-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C 01H7T5AGP7SGPZNK8VTDYBTY2B=%ED%8C%81 using-cohort=%EC%BD%94%ED%98%B8%ED%8A%B8-%EC%82%AC%EC%9A%A9%ED%95%98%EA%B8%B0 01H7T5AGP7XDKN85TR0J4V8TP3=%EC%BD%94%ED%98%B8%ED%8A%B8-%EC%82%AC%EC%9A%A9%ED%95%98%EA%B8%B0 01H7T5AGP7FDZNVM9PDBQJPMA0=setting-up-an-analysis using-my-reports%E2%80%94save-and-select-reports=using-my-reports-save-and-select-reports 01H7T5AGP8KRZ9207DCYGRGGC0=using-my-reports-save-and-select-reports 01H7T5AGP84HVD2BQ9Z8S13D5K=export-the-cohort-to-a-csv-file cohort-concepts=%EC%BD%94%ED%98%B8%ED%8A%B8-%EA%B0%9C%EB%85%90 01H8K817ZPJTRBP1KK90FVV57T=%EC%BD%94%ED%98%B8%ED%8A%B8-%EA%B0%9C%EB%85%90 01H8K817ZPZTG476KZ83F6Z460=cohort-periods h_01JJH967X8P2NF3AFBSNMBD7B4=view-types 01H8K817ZPBVTGT5R18XGQHYT2=trend-types user-lifetime-performance=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%B0%BD%EC%B6%9C-%EA%B0%80%EC%B9%98 01H8VNMYN0149T418BXM8RGBN9=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%B0%BD%EC%B6%9C-%EA%B0%80%EC%B9%98 kpi-by-attribution-time=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%82%A0%EC%A7%9C%EB%B3%84-kpi 01H8VNRGMWS8SSDM5KX08EDAS2=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%82%A0%EC%A7%9C%EB%B3%84-kpi example-user-lifetime-performance-trend-vs-kpi-by-attribution-time-trend=%EC%98%88%EC%8B%9C 01H8K98XE9T23QGB440GHRB8E8=%EC%98%88%EC%8B%9C 01H7T5AGP8PN12P2C4RGGQ0R95=partial-data 01H7T5AGP8XNG1CW2FPJSEEJ45=list-of-dimensions-for-grouping-and-filtering time-in-the-case-of%0A%20%20%0A%20%20daily-granularity-is-the-date%0A%20%20hourly-granularity-is-the-hour-of-the-day%0A%20%20weekly-granularity-is-the-week-of-the-year%0A%20%20monthly-granularity-is-the-month-of-the-year=time-in-the-case-of-daily-granularity-is-the-date-hourly-granularity-is-the-hour-of-the-day-weekly-granularity-is-the-week-of-the-year-monthly-granularity-is-the-month-of-the-year 01H7T5AGP708H7JGTS1RJ07H27=metrics-available information=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 01H7T5AGP8J9AQ1BREYZ0JWWZ4=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 01H7T5AGP83FRX1H9WVMS485MT=cohort-for-agencies 01H7T5AGP8JF0EAX8WEFNSEKM9=use-cases revenue-sum-by-country=%EC%A7%80%EC%97%AD%EB%B3%84-%EC%88%98%EC%9D%B5-%ED%95%A9%EA%B3%84 01H7T5AGP8R6913GPXWM6DGASF=%EC%A7%80%EC%97%AD%EB%B3%84-%EC%88%98%EC%9D%B5-%ED%95%A9%EA%B3%84 inapp-event-conversion=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%A0%84%ED%99%98-in-app-event-conversion 01H7T5AGP80W5J1VEZ40MHGPPF=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%A0%84%ED%99%98-in-app-event-conversion 01H7T5AGP85T7H25863GXJCVCW=faq 01H7T5AGP90NADB7YXTFEMTSAX=traits-and-limitations" />
