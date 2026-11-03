---
title: 마스터 API—API를 통한 유저 인입 지표
metadata:
  keywords:
    - Master API
    - Customizable
    - Aggregated Data
    - Advertisers
    - Developers
    - Premium
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2016-09-27T15:10:38Z'
  edited_at: '2026-10-14T10:40:37Z'
  id: 213223166
  locale: ko
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/ko/articles/213223166
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **한눈에 보기:** 선택한 LTV, 액티비티, 리텐션, 코호트, 및 Protect360 캠페인 성과 KPI를 API별로 CSV 또는 JSON 형식으로 가져옵니다. 1개 이상의 앱을 선택합니다.

## 마스터 API—API를 통한 유저 인입 지표

마스터 API:

* 선택한 LTV, 액티비티, 리텐션, 코호트 및 Protect360 캠페인 성과 KPI를 가져올 수 있습니다. 사용 가능한 KPI는 개요, 액티비티, 리텐션, 코호트, 및 Protect360 대시보드에 있는 KPI와 동등한 KPI입니다.
* 매일 계산됩니다. 업데이트된 데이터는 앱 별 시간대에 따라, 24-48시간 내에 사용 가능합니다.
* 앱스플라이어 <Anchor target="_blank" href="/marketers/ko/docs/pivot-table-user-metrics">피벗 테이블</Anchor>의 기반이 되는 인프라 구조입니다.

마스터 API를 사용하려면 보려는 데이터를 정의합니다( <Anchor target="_blank" href="/marketers/ko/docs/pull-api-aggregate-data">Pull API</Anchor>구현과 유사). 결과는 CSV 또는 JSON 파일로 반환됩니다.

**마스터 API 사용 방법**:

1. ![](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) alt<Anchor target="_blank" href="/marketers/ko/docs/managing-appsflyer-tokens">AppsFlyerAdmin\_us-en.png</Anchor> API 토큰을 받으세요. 관리자가 토큰을 가져와야 합니다.
2. 인증 헤더에 사용할 API 토큰을 귀사의 개발자에게 제공하세요.
3. 다음 절에 설명한 데 따라 개발자에게 API 호출을 할 때 입력할 파라미터를 제공합니다. 파라미터는 리포트의 중점 사항, 구성 방법을 결정하고 리포팅 기간을 제공합니다.
4. 개발자에게 개발자 허브에서 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-9">마스터 API 지침</Anchor>을 따르도록 하십시오.
5.
   <div id="api-parameters" />

   <Accordion title="API 파라미터">

   | 파라미터 | 값 | 필수 |
   | --- | --- | --- |
   | app\_id | * 앱스플라이어에서 확인되는 앱 식별자입니다.<br />* 앱스플라이어에서 찾은대로 정확하게 앱 ID를 입력하십시오.<br />* iOS 앱은 접두사 **id**를 붙입니다.<br />* **모든 앱 ID**를 사용하여 모든 앱 쿼리 | 예 |
   | 부터 | LTV 어트리뷰션 날짜 기간의 하한입니다.<br /><br />* 형식: yyyy-mm-dd 형식의 문자열<br />* 예: `from: 2020-01-02` | 예 |
   | 부터까지 | LTV 어트리뷰션 날짜 기간의 상한입니다.<br /><br />* 기간 범위 내의 일 수: 1-31 일 7일<br />* 형식: yyyy-mm-dd | 예 |
   | [그룹화](/docs/master-api-user-acquisition-metrics-via-api#groupings) | 조회 기준(Group by) 파라미터이며, 쉼표(,)로 구분됩니다. 사용 가능한 목록을 보려면 조회 기준(groupings) 표를 참고하십시오.<br /><br />예: `groupings=pid,geo` | 예 |
   | [KPI](/docs/master-api-user-acquisition-metrics-via-api#kpis) | 포함할 KPI 목록. 각각은 쉼표로 구분됩니다. KPI 목록을 보려면 아래의 KPI 표를 참고하십시오.<br /><br />예: `kpis=installs,clicks, impressions,sessions,retention_day_7` | 예 |
   | [필터](/docs/master-api-user-acquisition-metrics-via-api#filters-optional) | 하나 또는 그 이상의 필터 옵션을 사용하여 데이터를 필터링할 수 있습니다. | 아니요 |
   | [통화](/docs/master-api-user-acquisition-metrics-via-api#localization) | 데이터를 앱 별 통화를 사용해 리턴하려면, currency=preferred 를 설정합니다. | 아니요 |
   | [시간대](/docs/master-api-user-acquisition-metrics-via-api#localization) | 데이터를 앱 고유 시간대를 사용해 리턴하려면, timezone=preferred를 설정합니다.   [현지화 규칙](/docs/master-api-user-acquisition-metrics-via-api#localization) 참조 | 아니요 |
   | 형식 |  | 아니요 |

   </Accordion>

   <div id="groupings" />

   <Accordion title="그룹화">

   이러한 디멘션은 정보를 쉽고 정확하게 조사할 수 있도록, 데이터를 그룹 별로 수집하는 데 사용됩니다. 이 필드의 설명은 <Anchor target="_blank" href="/marketers/ko/docs/raw-data-field-dictionary">여기</Anchor>에서 확인할 수 있습니다.

   <table><thead><tr><th>그룹별로<br/>API 이름</th><th>조회 기준(Group by) 표시 이름</th><th>LTV KPI</th><th>리텐션 KPI</th><th>액티비티 KPI</th><th>Protect360</th><th>코호트</th></tr></thead><tbody><tr><td>app_id</td><td>앱 ID</td><td>예</td><td>예</td><td>예</td><td>예</td><td>예</td></tr><tr><td>pid</td><td>미디어 소스</td><td>예</td><td>예</td><td>예</td><td>예</td><td>예</td></tr><tr><td>af_prt</td><td>에이전시</td><td>예</td><td>예</td><td>예</td><td>예</td><td>아니요</td></tr><tr><td>c</td><td>캠페인</td><td>예</td><td>예</td><td>예</td><td>예</td><td>예</td></tr><tr><td>af_adset</td><td>광고세트</td><td>예</td><td>예</td><td>예</td><td>아니오</td><td>아니요</td></tr><tr><td>af_ad</td><td>Ad</td><td>예</td><td>예</td><td>예</td><td>아니오</td><td>아니요</td></tr><tr><td>af_채널</td><td>채널</td><td>예</td><td>예</td><td>예</td><td>예</td><td>아니요</td></tr><tr><td>af_siteid</td><td>퍼블리셔 ID</td><td>예</td><td>예</td><td>예</td><td>예</td><td>예</td></tr><tr><td>af_키워드</td><td>키워드</td><td>예</td><td>예</td><td>예</td><td>아니오</td><td>아니요</td></tr><tr><td>1차 어트리뷰션</td><td>1차 어트리뷰션 여부</td><td>예</td><td>아니오</td><td>Yes</td><td>예</td><td>아니요</td></tr><tr><td>af_c_id</td><td>캠페인 ID</td><td>예</td><td>아니오</td><td>Yes</td><td>예</td><td>아니요</td></tr><tr><td>af_adset_id</td><td>광고세트 ID</td><td>예</td><td>아니오</td><td>예</td><td>아니오</td><td>아니요</td></tr><tr><td>af_ad_id</td><td>광고 ID</td><td>예</td><td>아니오</td><td>예</td><td>아니오</td><td>아니요</td></tr><tr><td>설치 시간</td><td>설치 시간</td><td>예</td><td>예</td><td>예\*</td><td>예</td><td>예</td></tr><tr><td>attributed_touch_type</td><td>Touch Type</td><td>예</td><td>예</td><td>예</td><td>예</td><td>아니요</td></tr><tr><td>geo</td><td>지역</td><td>예</td><td>예</td><td>예</td><td>예</td><td>예</td></tr><tr><td colspan="7">\* 활동 KPI 컨텍스트에서 인스톨 시간은 이벤트 시간으로 간주됩니다.  </td></tr></tbody></table>

   </Accordion>

   <div id="kpis" />

   <Accordion title="KPI">

   KPI는 앱에 대한 인사이트를 얻기 위해 사용되는 지표입니다.

   <div id="ltv" />

   <Accordion title="LTV">

   라이프타임 값(LTV) - 인스톨 날짜로 그룹화되어 오늘까지 집계된 종합 이벤트

   | KPI API 이름 | 설명 |
   | --- | --- |
   | 노출 | 선택한 기간 동안 노출 수 |
   | 클릭 | 선택한 기간 동안 클릭 수 |
   | 설치 | 선택한 기간 동안 인스톨 수 |
   | cr | 전환율 |
   | 세션(Sessions) | 선택한 기간 동안 앱을 설치한 사용자가 수행한 세션 수 |
   | loyal\_users | 선택한 기간 동안 앱을 설치한 사용자 중 충성 고객 수 |
   | loyal\_users\_rate | Loyal Users/Installs |
   | 비용 | 선택한 기간 동안의 총 비용 *제한 사항 참조 |
   | 수익 | 선택한 기간 동안 앱을 설치한 사용자가 현재까지 누적으로 발생시킨 수익 |
   | ROI | 특정 기간에 대한 투자 대비 수익률. Return on Investment |
   | arpu\_ltv | 선택한 기간 동안 앱을 설치한 사용자의 사용자 별 평균 수익. Average revenue per user |
   | average\_ecpi | 특정 기간에 동안의 인스톨 당 효과 비용(eCPI, Effective Cost per Installation). 비용과 인스톨 수가 API 호출에 포함된 경우에만 사용 가능합니다. |
   | 앱 삭제 | 선택한 기간 동안 앱을 설치한 사용자 중 앱을 삭제한 사용자 |
   | uninstalls\_rate | 앱 삭제 비율 |
   | event\_counter\_[event\_name] | 이벤트가 발생한 횟수 |
   | unique\_users\_[event\_name] | 이벤트를 수행한 고유 유저 수 |
   | sales\_in\_usd\_[event\_name] | 리포트된 이벤트의 일부로서 리포트된 수익 |

   </Accordion>

   <div id="retention" />

   <Accordion title="잔존율">

   리텐션은 앱에 얼마만큼의 유저가 활동하고 있는지에 대해 보여줍니다.

   **참고:**

   * 최대 리텐션 기간은 인스톨 후 day 30이며, 여기서 앱 인스톨 날짜는 day 0입니다. 즉, [x] 값은 30을 초과할 수 없습니다.
   * retention\_day\_1을 요청하면 해당 날짜의 데이터가 사용 가능하기 전에 해당 날짜에 대한 지표는 이전 날짜에 인스톨한 사용자와 관련된 것입니다. 예를 들어 1월 2일에는 1월 1일에 인스톨을 수행한 사용자에 대해 retention\_day\_1을 요청합니다. 지표가 아직 사용 가능하지 않으므로 리턴하는 지표는 12월 31일에 인스톨한 사용자와 관련됩니다.

   | KPI | 설명 |
   | --- | --- |
   | retention\_day\_[x] | Day X에 보유한 사용자 수 |
   | retention\_rate\_day\_[x] | 인스톨 사용자 중 Day X에 보유한 사용자 수 비율 |

   </Accordion>

   <div id="activity" />

   <Accordion title="액티비티(Activity)">

   선택된 기간의 앱 액티비티 **참고**:

   | KPI | 설명 |
   | --- | --- |
   | activity\_average\_dau | 선택한 기간 동안 평균 일일 실 사용 유저 수 (DAU, Daily Active User) |
   | activity\_average\_mau | 선택한 기간 동안 평균 월간 실 사용 유저 수 (MAU, Monthly Active User). 하나의 MAU 일은 이전 30일 동안의 고유 사용자(unique user)를 표시. |
   | activity\_average\_dau\_mau\_rate | 평균 DAU/MAU 비율 |
   | activity\_average\_arpdau | 일별 실 사용 유저 당 평균 매출 - 모든 고유 사용자의 특정 일자 평균 매출 |
   | activity\_sessions | 선택한 기간 동안 발생한 세션 수 |
   | activity\_revenue | 선택한 기간 동안 리포트된 매출 |
   | activity\_event\_counter\_[event\_name] | 선택한 기간 동안 사용자가 생성한 이벤트 수 |
   | activity\_sales\_in\_usd\_[event\_name] | 선택한 기간 동안 리포트된 이벤트의 일부로서 리포트된 매출 |
   | activity\_average\_unique\_users\_[event\_name] | 선택된 기간 동안 지정된 이벤트를 수행한 평균 고유 사용자 |

   </Accordion>

   <div id="cohort" />

   <Accordion title="코호트">

   앱스플라이어의 코호트는 광고주에게 서로 다른 시간 기간에 걸쳐 여러 코호트에 대해 다양한 척도를 보고 비교할 수 있는 기능을 제공합니다.

   **참고:**

   * 사용자 당 매출은 9/100000=0.00009 입니다. 표시되는 값은 0 입니다.
   * 코호트 일수 코호트 일수: 최대 코호트 일수는 인스톨 후 90일이며, 여기서 day 0은 앱 설치일입니다. 코호트 일수 값 [x] 범위는 1-90 사이여야 합니다.   참고: cohort\_day\_0는 코호트 대시보드에서 지원되더라도 마스터 API에서는 지원되지 않습니다.
   * Master API V2

   **세션**

   | KPI | 설명 |
   | --- | --- |
   | cohort\_day\_[x]\_total\_sessions\_per\_user | Cohort Day x - day x 까지 유저 당 누적 세션 (day x 포함) |
   | cohort\_day\_[x]\_sessions\_per\_user | Cohort Day x - 코호트에서 오직 day x의 세션 |
   | cohort\_[x]\_days\_total\_sessions\_per\_user | 특정하는 KPI인 Cohort\_day\_1\_total\_sessions\_per\_user를 URL에서 Cohort\_day\_x\_total\_sessions\_per\_user로 바꿉니다. |

   **수익**

   | KPI | 설명 |
   | --- | --- |
   | cohort\_day\_[x]\_total\_revenue\_per\_user | Cohort Day x - day x 까지 유저 당 누적 매출 (day x 포함) |
   | cohort\_day\_[x]\_revenue\_per\_user | Cohort Day x - 코호트에서 오직 day x에 수신한 ARPU |
   | cohort\_[x]\_days\_total\_revenue\_per\_user | 특정하는 KPI인 Cohort\_day\_1\_total\_revenue\_per\_user를 Cohort\_day\_x\_total\_revenue\_per\_user로 바꿉니다. |
   | cohort\_day\_[x]\_total\_event\_[eventname]\_revenue\_per\_user | 코호트 Day x 특정 인앱 이벤트에 따른 사용자당 누적 수익 |
   | cohort\_day\_[x]\_event\_[eventname]\_revenue\_per\_user | 코호트 Day x 특정 인앱 이벤트에 따른 사용자당 수익 |

   **이벤트**

   | KPI | 설명 |
   | --- | --- |
   | cohort\_day\_[x]\_total\_event\_[eventname]\_per\_user | Cohort Day x - day x 까지 유저 당 누적 이벤트 (day x 포함) |
   | cohort\_day\_[x]\_event\_[eventname]\_per\_user | Cohort Day x - 코호트에서 오직 day x에 수신한 이벤트 |
   | cohort\_[x]\_days\_total\_event\_[eventname]\_per\_user | 특정하는 KPI 이벤트를 Cohort\_day\_x\_total\_events\_per\_user로 바꿉니다. |

   </Accordion>

   <div id="protect360" />

   <Accordion title="Protect360">

   **Protect360 KPI**

   | 설명 | KPI |
   | --- | --- |
   | **인스톨** |  |
   | 합계 | protect360\_total\_installs |
   | 차단 수 | blocked\_installs |
   | 차단율 % | blocked\_installs\_rate |
   | 포스트 어트리뷰션 | post\_attribution\_installs |
   | 포스트 어트리뷰션 % | post\_attribution\_installs\_rate |
   | 총 프로드 인스톨 | total\_fraudulent\_installs |
   | 프로드 인스톨 % | fraudulent\_installs\_rate |
   | **가짜 설치** |  |
   | 실시간 차단 | real\_time\_fake\_installs |
   | 포스트 어트리뷰션 프로드 | post\_attribution\_fake\_installs |
   | **하이재킹된 인스톨** |  |
   | 실시간 차단 | real\_time\_hijacked\_installs |
   | 포스트 어트리뷰션 프로드 | post\_attribution\_installs\_hijacked\_installs |
   | **유효성 검증 규칙** |  |
   | 차단된 인스톨 | validation\_rules\_blocked\_installs |
   | 차단된 어트리뷰션 | validation\_rules\_blocked\_attribution |
   | **허위 인스톨 차단 상세** |  |
   | 차단된 사이트 ID 블랙리스트 | blocked\_installs\_siteid\_blacklist |
   | 포스트 어트리뷰션 사이트 ID 블랙리스트 | post\_attribution\_installs\_siteid\_blacklist |
   | 차단된 봇 | blocked\_installs\_bots |
   | 포스트 어트리뷰션 봇 | post\_attribution\_installs\_bots |
   | 차단된 행동 이상 현상 | blocked\_installs\_behavioral\_anomalies |
   | 포스트 어트리뷰션 이상 행동(behavioral anomalies) | post\_attribution\_installs\_behavioral\_anomalies |
   | 차단된 인스톨 유효성 검증 | blocked\_installs\_install\_validation |
   | **하이재킹 인스톨 차단 상세** |  |
   | 차단된 인스톨 하이재킹 | blocked\_installs\_install\_hijacking |
   | 포스트 어트리뷰션 인스톨 하이재킹 | post\_attribution\_installs\_installs\_hijacking |
   | 차단된 CTIT 이상 현상 | blocked\_installs\_ctit\_anomalies |
   | 포스트 어트리뷰션 CTIT 이상현상 | post\_attribution\_installs\_ctit\_anomalies |
   | 차단된 클릭 플러딩 | blocked\_installs\_click\_flood |
   | 포스트 어트리뷰션 클릭 플러딩 | post\_attribution\_installs\_click\_flood |
   | **클릭** |  |
   | 합계 | protect360\_total\_clicks |
   | 차단 수 | blocked\_clicks |
   | % | blocked\_clicks\_rate |
   | **인앱 이벤트** |  |
   | 합계 | protect360\_total\_in\_apps |
   | 차단 수 | blocked\_in-app-events |
   | % | blocked\_in-app-events\_rate |
   | 디바이스 팜 지표 - 뉴 디바이스 |  |
   | 인스톨 | install\_fraud\_new\_devices\_total |
   | 설치 % | install\_fraud\_new\_devices\_total\_installs\_rate |
   | 충성 유저 % | install\_fraud\_new\_devices\_total\_loyal\_user\_rate |
   | **디바이스 팜 지표 - LAT 디바이스** |  |
   | 인스톨 | install\_fraud\_lat\_devices\_total |
   | 설치 % | install\_fraud\_lat\_devices\_total\_installs\_rate |
   | 충성 유저 % | install\_fraud\_lat\_devices\_total\_loyal\_user\_rate |
   | **클릭 플러딩 지표** |  |
   | 전환율 | conversion\_rate |
   | **클릭 도배 지표 - CTIT** |  |
   | 60분 이상 | click\_flood\_over\_1\_hour\_rate |
   | 5시간 이상 | click\_flood\_over\_5\_hours\_rate |

   </Accordion>

   #### 계산된 KPI

   앞서 설명한 KPI에 더하여, 마스터 API 리포트에 계산된 KPI를 추가할 수 있습니다. 이렇게 하면 마스터 API 리포트에 자체 계산된 리포트를 포함시킬 수 있습니다.

   계산된 KPI 수식을 위해, 몇 개 든지의 기본 KPI 개체를 삽입할 수 있습니다. 각 계산 KPI 개체에는 키와 값이 포함됩니다. 키는 KPI에 지정한 이름이고 값은 KPI 수식입니다.

   표준 산술 연산자가 지원됩니다: 더하기(+)는 인코딩 되어 %2b, 빼기(-), 곱하기(*), 나누기(/)는 %2f 로 인코딩 됩니다.

   계산된 KPI 필드 키는 **반드시** "calculated\_kpi\_"로 시작하여 유효한 스트링으로 이어져야 합니다. 예, "calculated\_kpi\_purchaserate"

   > 📄 **예시**
   >
   > 첫 3 일의 리텐션 모음
   >
   > ```http
   > kpis=installs,loyal_users_rate&calculated_kpi_3days_retention=
   > retention_day_1%2Bretention_day_2%2Bretention_day_3
   > ```
   >
   > 광고 노출 당 평균 수익
   >
   > ```http
   > kpis=installs&calculated_kpi_rev_per_impression=revenue%2Fimpression
   > ```
   >
   > 코호트 day 7의 ROI
   >
   > ```http
   > kpis=installs,roi,arpu_ltv,cost,revenue&calculated_kpi_roi_day_7=
   > (cohort_day_7_total_revenue_per_user-average_ecpi)%2Faverage_ecpi
   > ```

   </Accordion>

   <div id="filters-optional" />

   <Accordion title="필터 (선택적)">

   | 파라미터 | 설명 | 예시 | 필수적? |
   | --- | --- | --- | --- |
   | pid | * 특정 미디어 소스가 표시된 행을 선택하는데 사용됩니다.<br />* 쉼표(,)로 구분된 다중 선택이 지원됩니다. | pid=organic,applovin\_int | 아니요 |
   | c | * 캠페인 이름으로 필터링하는 데 사용됩니다.<br />* 쉼표(,)로 구분된 다중 선택이 지원됩니다. | c=my\_sample\_campaign | 아니요 |
   | af\_prt | * 에이전시 이름으로 필터링하는 데 사용됩니다.<br />* 쉼표(,)로 구분된 다중 선택이 지원됩니다. | af\_prt=moburst | 아니요 |
   | af\_채널 | * 채널 이름으로 필터링하는 데 사용됩니다.<br />* 쉼표(,)로 구분된 다중 선택이 지원됩니다. | af\_channel=Instagram | 아니요 |
   | af\_siteid | * 퍼블리셔 ID를 기준으로 필터링하는 데 사용됩니다.<br />* 쉼표(,)로 구분된 다중 선택이 지원됩니다. | af\_siteid=12345678 | 아니요 |
   | geo | * 국가별로 필터링하는 데 사용됩니다.<br />* 쉼표(,)로 구분된 다중 선택이 지원됩니다. | geo=US,DE | 아니요 |

   </Accordion>

   <div id="localization" />

   <Accordion title="현지화">

   로컬 통화 및 앱 별 시간대는 <Anchor target="_blank" href="/marketers/ko/docs/app-settings">앱 설정 페이지</Anchor>에 설정되어 있습니다. 마스터 API 데이터는 시스템 기본 통화 및 시간대를 사용하거나 앱 별 설정된 시간대와 통화를 사용하여 데이터를 추출할 수 있습니다.

   다음 사항이 적용됩니다.

   * 앱 별 시간대/통화를 사용하는 것은 모든 앱이 동일한 시간대/통화를 설정한 경우에만 지원됩니다. 그렇지 않으면, UTC 시간대와 USD 가 사용됩니다. 시간대와 통화는 별도로 분리되어 있습니다. 즉, 모든 앱의 통화 설정은 동일한데 시간대는 그렇지 않다면, 앱 별 통화는 사용할 수 있지만, 앱 별 시간대는 사용할 수 없습니다.
   * 대시보드에서 선호하는 시간대가 요청한 시간 기간 이내에 변경되었다면, 생성하는 리포트는 가장 최근의 시간대 변경 이후의 값만 포함합니다.

   다음 파라미터를 사용하여 앱 별 설정을 선택하십시오. **참고**: 참고: 만약 preferred 파라미터를 사용하지 않는 경우, 기본 설정인 USD 통화와 UTC 시간대를 갖게 됩니다.

   | 파라미터 | 설명 | 예시 | 필수적? |
   | --- | --- | --- | --- |
   | 통화 | 앱 별 설정한 통화에 따른 금전적 값. | currency=preferred | 아니요 |
   | 시간대 | 앱 별 설정한 시간대에 따라 시간대 사용. | timezone=preferred | 아니요 |

   </Accordion>

## 추가 정보

<div id="limitations" />

<Accordion title="특성 및 한계">

| 특징 | 비고 |
| --- | --- |
| 비용 데이터 | <ul><li>광고 세트, 광고, 지역, 채널 및 사이트 ID를 의미하는 다른 비용 차원의 가용성은 <Anchor target="_blank" href="/marketers/ko/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">ad network dependant</Anchor>입니다.</li><li>eCPI를 얻는 방법: 비용 데이터가 가능한 상황에서, 호출에 인스톨과 비용을 모두 포함하십시오.</li><li>일반적으로 앱스플라이어 링크를 사용하고 링크에 cost 파라미터가 있는 온드 미디어를 포함한 모든 소스는 요청된 차원에 관계없이 비용 데이터를 완벽하게 지원합니다. 자체 API를 가진 SRN(self-reporting network)는 일반적으로 가능한 디멘션 중 오직 일부 디멘션의 비용 데이터만 지원합니다. 예를 들어 <Anchor target="_blank" href="/marketers/ko/docs/meta-ads-faq#what-are-the-limitations-of-facebook-cost-data-in-master-api">Meta 광고</Anchor> 는 동일한 통화에서 지역 및 채널별 그룹화를 지원하지 않습니다. 둘 중 하나를 기준으로 개별적으로 그룹화할 수 있습니다.</li><li>비용 데이터는 있지만 최근 인스톨 데이터가 없는 캠페인(약 7일)은 마스터 API에서 사용할 수 없습니다.</li></ul> |
| 그룹화 | 특정 그룹화는 오직 LTV KPI, 액티비티 또는 리텐션 KPI에 대해서만 사용할 수 있습니다. 특정 KPI를 위한 데이터가 가능하지 않을 때는 API가 N/A을 반환합니다. 예를 들어, af\_channel로 그룹화한 retention\_rate\_day\_7d 요청은 N/A를 반환합니다. |
| 리포트 당 최대 행 개수 | 200K |
| 이벤트 이름 | 마스터 API는 현재 슬래시 `/`// 를 포함하는 이벤트 이름을 지원하지 않습니다. 이 제한사항을 해결하려면 이벤트 이름에 /를 사용하지 마십시오. |
| 처리 시간 | 두 개 이상의 앱을 선택하면 처리 시간이 늘어나고 응답 시간이 길어질 수 있습니다. |
| 날짜 범위 | 시간 세분성은 매일입니다. |
| 대행사 | 마스터 API를 사용할 수 없음 |
| 애드 네트워크 | 마스터 API를 사용할 수 없음 |
| 과거 데이터 | <ul><li>LTV 데이터 5년</li><li>2년</li><li>액티비티 데이터 3년</li></ul> |
| 리타겟팅 | <ul><li>지원되지 않습니다.</li></ul> |

</Accordion>

<div data-zendesk-anchors="master-api%E2%80%94user-acquisition-metrics-via-api=%EB%A7%88%EC%8A%A4%ED%84%B0-apiapi%EB%A5%BC-%ED%86%B5%ED%95%9C-%EC%9C%A0%EC%A0%80-%EC%9D%B8%EC%9E%85-%EC%A7%80%ED%91%9C h_01JJVMXKACJ2V4YZFGYXVB8FQF=%EB%A7%88%EC%8A%A4%ED%84%B0-apiapi%EB%A5%BC-%ED%86%B5%ED%95%9C-%EC%9C%A0%EC%A0%80-%EC%9D%B8%EC%9E%85-%EC%A7%80%ED%91%9C h_01JJVMXKACZDXPQG4271HFYWCE=api-parameters h_01JJVMXKAEXMKQQRT0RT6N8P74=groupings h_01JJVMXKAEHM0871GBQHZENRXA=kpis h_01JK2ZEH32Y92Y553540XDYZFA=ltv h_01JK2ZEH32A08EEDZEWFSX3ZFS=retention h_01JK2ZEH3219694E4PFPZ8ZXZF=activity h_01JK2ZEH32NCWZWKTDS0J6DFS2=cohort h_01JK2ZEH32Q7B6RCQYXNHM8KGK=protect360 calculated-kpis=%EA%B3%84%EC%82%B0%EB%90%9C-kpi h_01JJVMXKAFW1TEE35GK9B20TRP=%EA%B3%84%EC%82%B0%EB%90%9C-kpi h_01JJVMXKAFZDPNXKAZCBQ27DBD=%EC%98%88%EC%8B%9C h_01JJVMXKAFWA4D47MH7VSXKN14=filters-optional h_01JJVMXKAFSBXJ9EJJ16BF8H7Q=localization additional-information=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01JJVMXKAFFW2G3N7188DHYCB8=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01JJVMXKAF25YX092NE9DV9862=limitations" />
