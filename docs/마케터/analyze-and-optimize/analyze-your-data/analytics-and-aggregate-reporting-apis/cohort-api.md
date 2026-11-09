---
title: 코호트 API
metadata:
  keywords:
    - API
    - Advertisers
    - Partners
    - Developer
    - Premium
    - Gray
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2020-01-14T07:04:32Z'
  edited_at: '2026-10-14T10:37:04Z'
  id: 360004799057
  locale: ko
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/ko/articles/360004799057
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **한눈에 보기:** 코호트 API는 광고주가 프로그래밍을 통해 코호트 데이터를 얻을 수 있도록 지원합니다. API를 사용하여 코호트 데이터를 BI 및 마케팅 자동화 시스템에 연동합니다.

<div id="cohort-api" />

## 코호트 API

코호트 API는 앱스플라이어 플랫폼에서 코호트 캠페인 성과 데이터를 가져오는 데 사용됩니다. <Anchor target="_blank" href="/marketers/ko/docs/cohort-and-retention-dashboard">코호트 대시보드</Anchor>와 기능적으로 동일합니다.

코호트 및 리텐션을 사용하려면, 확인하고자 하는 데이터를 정의하세요. 앱에서 사용자를 선택하고 전환 시간에 따라 세분화합니다. 수익, ROI, 이벤트 전환율과 같은 코호트 분석 지표를 사용할 수 있습니다. 캠페인이나 미디어소스 같은 기준으로 코호트를 나누어 비교합니다. 결과는 CSV 또는 JSON 파일로 반환됩니다.  이렇게 하여 사용자 또는 캠페인의 라이프 사이클에 걸친 패턴이나 성과 변화를 발견할 수 있습니다.

<Anchor target="_blank" href="https://www.appsflyer.com/blog/cohort-report-mobile-marketing-kpis/?utm_campaign=Blog%20Subscription%2003-2019&utm_source=hs_email&utm_medium=email&utm_content=76370689&_hsenc=p2ANqtz-8SX49xuEw2WX_Vrlh11_zxlDFvlfMpBzSQm1I-nFhc0WbZDf0ACC-VEi4qmKhesHCsUNdhU50Oinl-urwnGAOZMwwHSTp6UgdChCi7ARayJFUFTus&_hsmi=76370689">코호트 사용 사례</Anchor>를 참조하세요.

**Cohort API를 사용하려면**:

1. ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)<Anchor target="_blank" href="/marketers/ko/docs/managing-appsflyer-tokens">API 토큰</Anchor>을 받으세요. 관리자가 토큰을 가져와야 합니다.
2. 인증 헤더에 사용할 API 토큰을 귀사의 개발자에게 제공하세요.
3. 다음 섹션에서 설명된 대로, API 호출 시 개발자가 입력해야 할 [파라미터](#filtering-and-grouping-parameters)를 제공하세요. 여기서 파라미터는 리포트의 초점, 구성 방식 및 보고 기간을 결정합니다.
4. 개발자에게 개발자 허브에서 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_app-id">코호트 API 지침</Anchor>을 따르도록 안내하십시오.

<div id="filtering-and-grouping-parameters" />

<Accordion title="코호트 API 파라미터">

다음 파라미터를 사용하여 필요한 데이터를 가져옵니다.

| 파라미터 이름 | 설명 | 필수 여부 |
| --- | --- | --- |
| <span id="bearer"></span>bearer | API 인증 헤더에 사용되는 API 토큰. | 예 |
| <span id="cohort-_type"></span>cohort \_type | 코호트 어트리뷰션(전환) 유형은 다음 중 하나입니다: `user_acquisition`, `retargeting`, `unified`<ul><li>Unified는 유저 유입(UA) 및 리타게팅 캠페인의 성과를 결합합니다.</li><li>이벤트가 리타게팅 및 UA 캠페인 모두에 어트리뷰트된 경우, 반환되는 KPI에는 리타게팅 이벤트만 포함됩니다.(즉, is\_primary=true)</li><li>형식: 문자열</li><li>예시: `"cohort_type": "user_acquisition"`</li></ul> | 예 |
| <span id="min_cohort_size"></span>min\_cohort\_size | 최소 코호트 사이즈는 사용자 수가 적은 코호트를 제외하여 반환되는 기록 수를 줄이는 데 사용됩니다. 이것은 “사용자(users)” KPI가 지정된 값과 같거나 그보다 크다는 것을 의미합니다.<ul><li>형식: Integer</li><li>허용되는 최소값: 1. 0(영)을 전송하지 마세요.</li><li>기본값: 1</li><li>예시: `"min_cohort_size": 50`</li></ul> | 아니오 |
| <span id="from"></span>from | LTV 어트리뷰션 날짜 범위의 하한값을 나타냅니다. 지원되는 가장 이른 날짜는 현재 날짜 기준 720일 전입니다.<ul><li>형식: yyyy-mm-dd 형식의 스트링(문자열)</li><li>예시: `"from": "2020-01-02"`</li></ul> | 예 |
| <span id="to"></span>to | LTV 어트리뷰션 날짜 범위의 상한값을 나타냅니다.<ul><li>범위 내의 일 수: 1-31일</li><li>하루 동안: `from` 과 `to`의 값은 동일합니다.</li><li>형식: yyyy-mm-dd</li><li>예시: `"from": "2020-01-01", "to": 2020-01-31`은 31일입니다.</li></ul> | 예 |
| <span id="granularity"></span>granularity | 이전 72시간 동안의 시간별 세분화를 위해, 날짜 뿐 아니라 시간까지 포함하도록 `"granularity": "hour"`를 설정하고 `from` 과 `to` 범위를 설정합니다.<ul><li>형식: yyyy-mm-dd hh:mm:ss</li><li>예시:</li></ul>`"granularity": "hour", "from": "2021-12-01 14:00:00", "to": "2021-12-03 11:00:00",` | 아니오 |
| <span id="partial_data"></span>partial\_data | 데이터 왜곡 및 오해를 방지하기 위해 코호트는 완료된 날의 데이터를 반환합니다. 그러나, 부분 날짜의 데이터가 유용할 수 있습니다.<br /><br />쿼리에 대한 완료 코호트 일수는 오늘 날짜와 *to* 날짜 간의 차이로 계산됩니다.<ul><li>[기본값] false일 경우, 전체 일 수가 반환됩니다.</li><li>true인 경우, 불완전한 데이터가 있는 날을 포함하여 최대 180일의 코호트 일수가 반환됩니다.</li><li>형식: Boolean</li><li>플랫폼 UI 버전: false</li></ul>**예시**: 5월 10일을 기준으로, 4월 1일부터 30일까지 전환한 사용자의 완료 코호트 일수는 10일입니다.<ul><li>false [기본값]인 경우, 코호트 0-9일을 반환합니다. 이는 마지막 전환 날짜와 오늘 사이의 일 수(10)입니다.</li><li>true이면 코호트 1-40일이 반환됩니다. 11-40일에는 부분 데이터가 포함되며 반환되지 않습니다. 예를 들어, 4월 20일 이후로는 20일만 경과했으며, 이와 같은 방식으로 계산됩니다.</li></ul>**참고**: 부분 데이터는 집약 유형이 누적인 경우에만 허용됩니다. | 아니오 |
| <span id="filters"></span>필터 | 반환된 데이터 및 기간(일)을 필터링합니다.  [필터 기준 목록](/docs/cohort-api#list-of-group-by-and-filter-by-dimensions)에서 필터를 선택합니다.<ul><li>형식: 중첩된 JSON의 문자열(strings). 값은 배열(array)에 있어야 합니다.</li><li>**특정 지역에 대한 제한 예시:** `"filters": {"geo": ["US"]}`는 미국에 어트리뷰트된 사용자만 포함합니다.</li><li>**예시 기간 (코호트) 일수**: `period` 필터는 측정값이 반환되는 날짜를 설정합니다. 가능한 값은 0-180입니다.</li><li>기본값: 기간 필터를 설정하지 않으면 0-30, 60, 90 및 180이 반환됩니다.  [마침표가 있는 필터의 예](/docs/cohort-api#using-period-filters)</li></ul> | 아니오 |
| <span id="groupings"></span>그룹화 | <ul><li>그룹화 파라미터를 사용하여 추가 열을 포함하고 리포트의 세분화 수준을 줄일 수 있습니다.</li><li>[그룹화 기준 목록](/docs/cohort-api#list-of-group-by-and-filter-by-dimensions)에서 1-7개의 그룹화를 선택합니다.</li><li>형식: Strings in an array (배열의 문자열)</li><li>예시: `"groupings": ["af_ad", "c", "af_c_id", "af_prt"]`</li></ul> | 예 |
| <span id="kpis"></span>KPI | KPIs는 앱의 동작에 대한 인사이트를 얻기 위해 사용하는 지표입니다. [KPI를 선택하고 형식을 설정하는 방법에 대해 알아보세요.](/docs/cohort-api#selecting-and-formatting-kpis) | 예 |
| <span id="preferred_currency"></span>preferred\_currency | 반환되는 KPI의 형식을 설정하는 파라미터 입니다. [KPI 형식을 설정하는 방법에 대해 알아보세요.](/docs/cohort-api#kpi-기능-형식-설정하기) | 아니오 |
| <span id="preferred_timezone"></span>preferred\_timezone | 반환되는 KPI의 형식을 설정하는 파라미터 입니다. [KPI 형식을 설정하는 방법에 대해 알아보세요.](/docs/cohort-api#kpi-기능-형식-설정하기) | 아니오 |
| <span id="aggregation_type"></span>aggregation\_type | 반환되는 KPI의 형식을 설정하는 파라미터 입니다. [KPI 형식을 설정하는 방법에 대해 알아보세요.](/docs/cohort-api#kpi-기능-형식-설정하기) | 예 |
| <span id="per_user"></span>per\_user | 반환되는 KPI의 형식을 설정하는 파라미터 입니다. [KPI 형식을 설정하는 방법에 대해 알아보세요.](/docs/cohort-api#kpi-기능-형식-설정하기) | 아니오 |

</Accordion>

<div id="selecting-and-formatting-kpis" />

<Accordion title="KPI 선택 및 서식 지정">

* 이 표에는 사용 가능한 KPI 및 관련 기능이 나열되어 있습니다. KPI를 호출하면 모든 함수가 반환됩니다.
* 다음 KPI는 항상 반환됩니다: user, ecpi 및 cost
* 호출당 하나의 추가 KPI를 선택합니다.
* 요청된 각 KPI에 대해 모든 함수가 반환됩니다.
* 형식: Strings in an array (배열의 문자열)
  * 예시 A: `"kpis": ["sessions"]`
  * 예시 B: `"kpis": ["event_name"]`

<table><thead><tr><th> </th><th> </th><th colspan="5">함수 (Functions)</th></tr><tr><th rowspan="2">기본값/선택 사항  </th><th rowspan="2">KPI(데이터 기준 이름) </th><th>횟수(Count)</th><th>전환율 (CVR)</th><th>비율</th><th>합계 (Sum)</th><th>고유 사용자</th></tr><tr><th>숫자</th><th>백분율</th><th>백분율</th><th>숫자</th><th>숫자</th></tr></thead><tbody><tr><td>항상</td><td>users</td><td><span>Y</span></td><td>-</td><td>-</td><td>-</td><td>-</td></tr><tr><td>항상</td><td>ecpi</td><td>-</td><td>-</td><td>-</td><td><span>Y</span></td><td>-</td></tr><tr><td>항상</td><td>cost</td><td>-</td><td>-</td><td>-</td><td><span>Y</span></td><td>-</td></tr><tr><td>선택 사항</td><td> <code>"event_name"</code>(4) </td><td><span>Y</span></td><td><span>Y</span></td><td>-</td><td><span>Y (3)</span></td><td><span>Y</span></td></tr><tr><td>선택 사항</td><td>revenue</td><td><span>Y</span></td><td>-</td><td>-</td><td><span>Y</span></td><td>-</td></tr><tr><td>선택 사항</td><td>roas</td><td>-</td><td>-</td><td><span>Y</span></td><td>-</td><td>-</td></tr><tr><td>선택 사항</td><td>roi</td><td>-</td><td>-</td><td><span>Y</span></td><td>-</td><td>-</td></tr><tr><td>선택 사항</td><td>sessions</td><td><span>Y</span></td><td>-</td><td><span>Y</span></td><td>-</td><td><span>Y (1)</span></td></tr><tr><td>선택 사항</td><td>uninstalls (2)</td><td><span>Y</span></td><td>-</td><td><span>Y</span></td><td>-</td><td>-</td></tr><tr><td colspan="7"><p>(1) 고유 세션 수는 <em>aggregation_type=on_day</em> 일 때 반환됩니다.</p><p>(2) cohort_type=unified일 경우 사용할 수 없습니다.  </p><p>(3) 합계(Sum)는 이벤트에서 발생한 총 수익을 의미합니다. 리포트에서 해당 부분은 <code>sum_event_name"</code>으로 표시됩니다. </p><p>(4) 주의! 이벤트 이름은 대소문자를 구분합니다.</p></td></tr></tbody></table>

<div id="formatting-kpi-functions" />

#### KPI 기능 형식 설정하기

다음 파라미터로 반환되는 KPI의 형식을 설정합니다.

| 파라미터 | 값 | 필수 여부 |
| --- | --- | --- |
| preferred\_currency | KPI 수익 통화<ul><li>true일 경우, 수익은 플랫폼에 설정된 <Anchor target="_blank" href="/marketers/ko/docs/app-settings#localization-currency">앱별 통화</Anchor>를 사용하여 반환됩니다.</li><li>[기본값] false인 경우 결과는 USD로 반환됩니다.</li><li>형식: Boolean</li><li>플랫폼 UI 버전: true</li></ul> | 아니오 |
| preferred\_timezone | **데이터 범위의 시간대**<ul><li>true일 경우, 플랫폼에 설정된 <Anchor target="_blank" href="/marketers/ko/docs/app-settings#localization-time-zone">앱별 표준 시간대</Anchor>를 기준으로 시간이 표시됩니다.</li><li>[기본값] false일 경우, UTC 표준 시간대로 시간이 표시됩니다.</li><li>형식: Boolean</li><li>플랫폼 UI 버전: true</li></ul> | 아니오 |
| aggregation\_type | <ul><li>`cumulative`</li><li>`on_day`</li></ul>`"aggregation_type": "cumulative"`<br /><br />`Format: String` | 예 |
| per\_user | KPI 함수를 앱 사용자 수로 나눕니다. 관련된 KPI에만 적용됩니다.<ul><li>true인 경우, KPI 값을 코호트의 사용자 수로 나눕니다.</li><li>false인 경우, KPI 값을 사용자 수로 나누지 않습니다.</li><li>형식: Boolean</li><li>true인 경우의 예: 총 수익은 1000달러, 앱 사용자 수는 500명, 반환되는 값은 2달러입니다.</li></ul> | 아니오 |

</Accordion>

<div id="list-of-group-by-and-filter-by-dimensions" />

<Accordion title="그룹화 및 데이터 기준 필터">

<table><thead><tr><th>데이터 기준 이름 </th><th>데이터 기준 API 값</th><th>그룹화</th><th>필터</th></tr></thead><tbody><tr><td>Ad</td><td>af_ad</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Ad ID</td><td>af_ad_id</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Campaign</td><td>c</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Campaign ID</td><td>af_c_id</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Channel</td><td>af_channel</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Media Source</td><td>pid</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Sub Param 1</td><td>af_sub1</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Keywords</td><td>af_keywords</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Agency</td><td>af_prt</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>Conversion Type (1) </td><td>cohort_type</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>사이트 ID</td><td>site_id</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>수익 유형 (2)</td><td>revenue_type</td><td><span>x </span></td><td><span>Y</span></td></tr><tr><td>Attributed Touch Type (3)</td><td>attributed_touch_type</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>광고 세트</td><td>af_adset</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>광고 세트 ID</td><td>af_adset_id</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>국가</td><td>geo</td><td><span>Y</span></td><td><span>Y</span></td></tr><tr><td>날짜(인스톨/리어트리뷰션/선택한 cohort_type 컨텍스트에서 리인게이지먼트 날짜) </td><td>date</td><td><span>Y</span></td><td><span>x </span></td></tr><tr><td>기간</td><td><p>period</p><p><a href="./cohort-api#using-period-filters">자세한 설명</a></p></td><td><span>x</span></td><td><span>Y</span></td></tr><tr><td colspan="4"><p>참고: </p><p>데이터 기준 옵션:</p><p>(1) 전환 유형: <code>user_acquisition</code>, <code>retargeting</code> (<code>re-engagement</code> 및 <code>re-attribution</code>), <code>unified</code></p><ul><li>내보낼 때:<ul><li> <code>re-engagement</code>은 <code>retargeting</code>로 표시됨 </li><li> <code>re-attribution</code>은 <code>reattr</code>로 표시됨 </li></ul></li></ul><p>(2) 수익 유형: <code>regular</code>, <code>ad_monetization</code><span></span></p><p>(3) 어트리뷰트된 터치 유형: <code>click</code>, <code>impression</code>, <code>TV</code>, <code>pre-installed</code></p></td></tr></tbody></table>

</Accordion>

<div id="additional-information" />

## 추가 정보

<div id="using-period-filters" />

<Accordion title="기간 필터 사용">

기간은 어트리뷰션 이후의 날을 의미하며, 여기서 기간 0은 어트리뷰션 일입니다. 예를 들어, 사용자가 1월 1일에 앱을 설치했습니다. 여기서 1월 1일은 어트리뷰션 일입니다. 기간 0에 구매한 경우 1월 1일에 구매했음을 의미합니다. 기간 3에 구매한 경우 1월 4일에 구매했음을 의미합니다. 같은 맥락에서, 1월 11일에 설치하는 사용자는 이 기간이 0입니다. 1월 14일에 이루어진 구매는 기간 3으로 표시됩니다.

리포트 날짜 범위가 1월 1일부터 1월 11일까지인 경우, 이 기간 동안 어트리뷰트(설치)한 사용자가 리포트에 포함됩니다. 다른 데이터는 포함되지 않습니다.

* 기간의 값은 다음 0-180 중 하나 이상일 수 있습니다. 예시: 0, 1, 2, 30, 180
* 기간을 지정하지 않으면 0, 1, 2 등의 기본값에서 30, 60, 90 및 180이 반환됩니다.

<div id="example-period-filter" />

> 📄 **기간 필터의 예시**
>
> * 이 예시에는 JSON 쿼리 파라미터, 로데이터 및 결과 CSV 파일이 포함되어 있습니다.
> * 쿼리는 0, 1 및 2 *기간을 필터링하고*, 여기서 선택한 KPI는 *수익*입니다.
> * 쿼리는 집약 유형을 “누적”으로 지정합니다. 당일 데이터를 원할 경우, "on\_day"로 변경하면 됩니다.
> * 그 결과, 반환되는 데이터에는 다음이 포함됩니다.
>   * 항상 반환되는 유저, 비용 및 eCPI의 측정값
>   * 각 기간(즉, 기간 0, 1, 2)에 대한 합(sum)과 횟수(count)로 구성된 수익 측정값
>
> **쿼리**
>
> ```json
> {
>     "cohort_type": "user_acquisition",
>     "min_cohort_size": 1,
>     "preferred_timezone": false,
>     "from": "2019-12-01",
>     "to": "2020-01-01",
>     "filters": {
>         "period": [
>             0,
>             1,
>             2
>         ]
>     },
>     "aggregation_type": "cumulative",
>     "per_user": false,
>     "groupings": [
>         "pid"
>     ],
>     "kpis": [
>         "revenue"
>     ]
> }
> ```
>
> **로데이터**
>
> **![mceclip1.png](https://files.readme.io/846aade481d3b5fa72536817533bc3edad721f1ce6015edcb48bd500461342b9-32131110606865.png)**
>
> **결과**
>
> <Image align="center" alt="mceclip0.png" src="https://files.readme.io/c284e5133e4e811b9416c850e399ddefb3c5bfcfcf879f469556b7a6bc0062c6-32131110607249.png" />

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="특징 및 제약 사항">

| 특징 | 비고 |
| --- | --- |
| 애드 네트워크 액세스 | 아니요 |
| 에이전시 액세스 | 아니오 |
| 에이전시 투명성 | 지원되지 않습니다. 에이전시 주도의 트래픽의 미디어 소스는 항상 원래의 미디어 소스가 아닌 에이전시입니다. |
| 특정 앱 시간대 | 예 |
| 앱별 통화 | 예 |
| 사이즈 제한 | 없음 |
| 속도 제한 | <ul><li>API 호출 속도 제한: 1분에 60건, 계정당 하루 50,000건</li><li>쿼리는 최대 30,000개의 행을 반환합니다.</li></ul> |
| 오가닉 데이터 | 사용 가능 |
| 논오가닉 데이터 | 사용 가능 |
| 비용 데이터 제한 | <ul><li>비용 데이터는 최소 1회 이상의 인스톨이 기록된 캠페인에만 적용됩니다.</li><li>앱스플라이어는 코호트 리포트나 코호트 API에 있는 대문자를 포함한 키워드에 대한 비용 데이터를 제공하지 않습니다.</li><li>일부 그룹화 조합에 비용은 포함될 수 없습니다. 예를 들어 Meta ads에는 지역 그룹이나 채널 그룹 중 하나만 포함될 수 있습니다. 그룹화의 정확한 조합은 애드 네트워크에 따라 달라질 수 있습니다.</li></ul> |
| 데이터 최신성 | 데이터 새로 고침은 다음과 같이 [partial\_data](/docs/cohort-api#partial_data)에 따라 달라집니다.<ul><li>[기본값] false인 경우 <Anchor target="_blank" href="/marketers/ko/docs/about-data-freshness-and-timezone-support#daily">매일</Anchor> 새로 고침</li><li>true일 경우, <Anchor target="_blank" href="/marketers/ko/docs/about-data-freshness-and-timezone-support#continuous-aka-realtime">연속(실시간)</Anchor> 새로 고침</li><li>비용 및 제거 지표는 모든 환경에서 매일 업데이트됩니다.</li></ul> |
| 과거 데이터 | 일일 코호트: 2년 |
| 계정 유저 액세스 | 권한 부여 토큰은 대시보드에서 관리자 유저가 사용할 수 있습니다 |
| 광고 수익 | af\_ad\_revenue 이벤트의 경우, 집약 유형이 다음과 같을 때 고유 사용자 지표가 제공되지 않습니다.<ul><li>누적.</li><li>“On day”는 2022년 10월 5일부터 2023년 2월 16일 사이의 날짜입니다.</li></ul> |
| 주간 및 월간 그룹화 | 주간 및 월간 데이터 기준 그룹화는 코호트 API에서 사용할 수 없습니다. 코호트 대시보드를 사용합니다. |
| 코호트 API 기간 | <ul><li>전환 기간을 0(0시간 또는 0일)이라고 합니다. 전환 후 다음 기간을 1(1시간 또는 1일) 등으로 지칭합니다.</li><li>앱스플라이어에서 코호트 기간은 특정 인스톨 타임스탬프를 고려하지 않습니다. 오히려 코호트 시간은 가장 가까운 시간으로 내림하고 코호트 일수는 달력상의 날짜를 기준으로 합니다. 이로 인해 앱스플라이어 코호트 데이터를 다른 네트워크의 코호트 데이터와 비교할 때 불일치가 발생할 수 있습니다. 다른 네트워크에서는 모든 코호트 기간이 특정 인스톨 타임스탬프를 기준으로 결정됩니다. (즉, 한 시간은 인스톨 타임스탬프 후 60분, 1일은 인스톨 타임스탬프 후 24시간 동안의 기간을 의미합니다.)</li></ul> |
| 날짜 | <ul><li>날짜 또는 기간은 유저 생애 가치(<Anchor target="_blank" href="/marketers/ko/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTV</Anchor>) 날짜를 의미하며, 이는 활동 자체의 날짜가 아니라 사용자가 어트리뷰트(전환)된 날짜를 의미합니다.</li><li>지원되는 가장 이른 날짜: 현재 날짜로부터 730일 전. 즉, 2년 전.</li><li>최대 쿼리 범위: 60일</li></ul> |
| 재설치 | <ul><li>재설치 후 이벤트가 속성이 없는 오가닉이라고 간주되는 경우:<ul><li>2024년 5월 26일부터 포함됩니다. <Anchor target="_blank" href="/marketers/ko/docs/bulletin-cohort-data-includes-unattributed-sessions-and-events">더 알아보기</Anchor></li><li>설치 시간은 <Anchor target="_blank" href="/marketers/ko/docs/raw-data-field-dictionary#device-info::dfd9504e">device\_download\_time</Anchor> 필드를 기반으로 합니다.</li><li>고유 사용자 및 유지 측정에 포함되지 않습니다.</li></ul></li><li>재설치 후 이벤트가 첫 설치에 속하는 경우 항상 포함됩니다. <Anchor target="_blank" href="/marketers/ko/docs/unique-users">더 알아보기</Anchor></li></ul> |
| 파트너를 위한 코호트 API | 마케팅 파트너를 위한 코호트 API에 대한 접근은 2024년 9월 15일부터 사용 중단됩니다. 마케팅 파트너는 고객 데이터에 지속적으로 접근할 수 있도록 <Anchor target="_blank" href="/partners/ko/docs/data-locker-reports-for-api-partners">데이터 락커를 활성화</Anchor>하는 것을 권장합니다. |

</Accordion>

<div data-zendesk-anchors="cohort-reporting-api=%EC%BD%94%ED%98%B8%ED%8A%B8-api 01H7WFZR41YAQX4MFPBMJD1MBP=%EC%BD%94%ED%98%B8%ED%8A%B8-api 01H7WFZR42H3CA0CSB4E3XED3H=filtering-and-grouping-parameters 01H7WFZR42XV4JY46GY11KT3CF=selecting-and-formatting-kpis presentation-of-kpi-functions=kpi-%EA%B8%B0%EB%8A%A5-%ED%98%95%EC%8B%9D-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 01H7WFZR43HFF65TSWG1AN0JTB=kpi-%EA%B8%B0%EB%8A%A5-%ED%98%95%EC%8B%9D-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 01H7WFZR43BJ8E6KVHSGV4CDDP=list-of-group-by-and-filter-by-dimensions additional-information=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01HMY09W324E54VPZWPJVS2KB8=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 01H7WFZR440NTXWWQ2T4P2ANWK=using-period-filters 01H7WFZR44RCXA56CXSCEZ0KXH=%EA%B8%B0%EA%B0%84-%ED%95%84%ED%84%B0%EC%9D%98-%EC%98%88%EC%8B%9C 01H7WFZR45VC96KYW1W9A8PBFT=traits-and-limitations" />
