---
title: 데이터 락커를 통한 코호트 분석
metadata:
  keywords:
    - Advertisers
    - Premium Feature
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2021-10-14T08:46:00Z'
  edited_at: '2026-10-14T10:29:16Z'
  id: 4408945472529
  locale: ko
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/ko/articles/4408945472529
---
> **간단히 보기**: 데이터 락커의 코호트 분석에는 광고 계층 구조에 속한 모든 요소의 집약 데이터를 포함합니다. 보고서에는 지난 365일 동안 어트리뷰트된 사용자의 데이터가 포함됩니다. 이 보고서는 로데이터 또는 코호트 API를 구독하거나 둘 다 가진 광고주에게 제공됩니다. 즉, 이 리포트에는 데이터 락커 가입이 필요하지 않습니다.

<div id="cohort-analytics-in-data-locker" />

## 데이터 락커에서 코호트 분석

어떤 경우에는 미디어 소스 데이터 공유 정책이나 <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions">회사 개인정보 보호 정책으로 인해 앱스플라이어에서 어트리뷰션 로데이터가</Anchor> <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions">제한</Anchor>될 수 있습니다. 이 제한에는 캠페인, 광고세트 등 모든 어트리뷰션 관련 필드가 포함됩니다. 코호트 보고서는 로데이터의 대안으로 사용할 수 있는 집약 데이터를 제공합니다.

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQ8q_4xv83wHkl4fs6jndEffRu-RHsPobBRfxDG-bUNXb0pOnvJH4QT0nXKdWvi3JPtVUBegTFbxIEe/pub?output=xlsx">예시 보고서 다운로드</Anchor>

<div id="enable-data-locker" />

<Accordion title="데이터 락커 활성화">

리포트는 데이터 락커, Cohort API 및 로데이터 등록자가 사용할 수 있습니다. <Anchor target="_blank" href="/marketers/ko/docs/data-locker-for-marketers">데이터 락커</Anchor>에서 보고서를 활성화하려면 다음 절차 중 하나를 완료하세요.

| 현재 데이터 락커를 통해 데이터를 받고 계신가요? | 절차 |
| --- | --- |
| 예 | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) 코호트 보고서를 데이터 락커에 추가 하시려면:<ol><li>앱스플라이어의 사이드 메뉴에서 **보고서 > 데이터 락커**를 선택합니다.</li><li>**코호트 분석** 섹션의 모든 보고서를 선택하세요.</li><li>**구성 저장**을 클릭합니다.<br />보고서는 다음 날 10:00 UTC에 이용 가능합니다.</li></ol> |
| 아니요 | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) **데이터 락커 설정 방법**:<ol><li>데이터 락커( <Anchor target="_blank" href="/marketers/ko/docs/data-locker-for-marketers#set-up-data-locker">광고주</Anchor> \| <Anchor target="_blank" href="/partners/ko/docs/data-locker-for-partners">파트너</Anchor> ) 설정을 처음 완료하세요.</li><li>코호트 리포트를 데이터 락커에 추가:<ol><li>앱스플라이어의 사이드 메뉴에서 **보고서 > 데이터 락커**를 선택합니다.</li><li>**코호트 분석** 섹션의 모든 보고서를 선택하세요.</li><li>**구성 저장**을 클릭합니다.<br />보고서는 다음 날 10:00 UTC에 이용 가능합니다.</li></ol></li></ol> |

</Accordion>

데이터를 BI 시스템에 로드하여 캠페인 성과와 최적화 프로세스의 일부로 사용할 수 있습니다.

**사용 가능한 지표**

사용 가능한 지표는 수익, 이벤트를 수행하는 고유 사용자 및 이벤트 발생 횟수입니다. ROI 및 ROAS와 같은 비용 관련 지표를 계산하려면 수익 및 비용 지표가 모두 있어야 합니다. 수익 지표는 코호트에서 제공되며, 비용 지표는 <Anchor target="_blank" href="/marketers/ko/docs/set-up-and-use-roi360-cost-etl-reports">ROI360 Cost ETL</Anchor>에서 제공됩니다.

<div id="facts" />

<Accordion title="코호트 분석 팩트">

| 사용 가능한 리포트 | 다음 리포트를 다운로드할 수 있습니다. 보고서 유형에 대한 세부 정보는 <Anchor target="_blank" href="/marketers/ko/docs/cohort-and-retention-dashboard#cohort-principles">코호트 대시보드</Anchor>에서 확인할 수 있습니다.<ul><li>**사용자 획득:** 리인게이지먼트 윈도우 동안 발생하는 LTV를 포함한 사용자 획득 미디어 소스를 통해 어트리뷰트됩니다.</li><li>**리타게팅:** 발생한 이벤트에 대한 리타게팅 미디어 소스를 통해 어트리뷰트됩니다:<ul><li>리인게이지먼트 기간 동안</li><li>리어트리뷰션의 결과</li></ul></li><li>**통합:** 앱스플라이어의 <Anchor target="_blank" href="/marketers/ko/docs/resolve-retargeting-double-attribution">이중 어트리뷰션</Anchor> 규칙에 따라 최종 터치 미디어 소스에서 데이터를 표시합니다. 즉, 재참여 중에 발생하는 LTV는 사용자 획득 미디어 대신 리타게팅 미디어 소스에 표시됩니다.</li></ul> |
| --- | --- |
| 리포팅 기간 | 지난 365일 동안 전환하는 사용자. 즉, 매일 보고서는 이전 365일 동안 전환한 사용자의 이벤트를 포함합니다. |
| 리포트 구조 | 보고서의 스키마(차원과 지표 포함)는 고정되어 있으며 수정할 수 없습니다. [보고서 구조](/docs/cohort-analytics-via-data-locker#report-structure)를 참조하세요. |
| 보고서 전달 | [데이터 락커에서 코호트 보고서 활성화](/docs/cohort-analytics-via-data-locker#enable-data-locker)를 참조하세요. |
| 데이터 최신성 | <ul><li>일별.</li><li>지표는 자정(UTC)에 사용 가능한 데이터를 사용하여 계산합니다. 다시 말하면, 하루가 끝날 때입니다.</li><li>리포트는 데이터 락커의 날짜-시간(dt) 폴더에서 10:00 UTC까지 사용할 수 있습니다. 예를 들어, 월요일의 데이터는 화요일 아침 10:00 UTC에 월요일 폴더에서 이용할 수 있습니다.</li></ul> |
| 파트너의 데이터 보존 정책의 영향 | 일부 파트너는 데이터 보존 정책을 시행할 수 있습니다. 이 경우, 보존 기간이 끝난 후 발생한 이벤트는 코호트 보고서에서 오가닉으로 간주됩니다.<br /><br />예시: SRN A의 데이터 보존 정책은 180일입니다. 180일까지의 유저 이벤트는 SRN A에 어트리뷰트됩니다. 180일 이후에 발생하는 이벤트는 오가닉으로 간주됩니다. |

</Accordion>

<div id="report-structure" />

<Accordion title="리포트 구조">

보고서는 차원과 지표로 구성됩니다.

필드의 형식은 다음과 같습니다.

* **차원**: 문자열입니다. 문자열의 최대 길이는 동적으로, 대부분 광고 계층 구조의 요소를 어떻게 채우느냐에 따라 달라집니다.
* **지표**: 숫자입니다. **참고:** selected\_currency 필드 형식은 문자열입니다.

<div id="dimensions" />

#### 디멘션

<Table>
  <thead>
    <tr>
      <th>
        필드 이름
      </th>
      <th>
        설명
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        app\_id
      </td>
      <td>
        --
      </td>
    </tr>
    <tr>
      <td>
        media\_source
      </td>
      <td>
        --
      </td>
    </tr>
    <tr>
      <td>
        conversion\_type
      </td>
      <td>
        가능한 값: 설치, install\_unified (통합 보고서에서 설치를 나타냄), 재참여, 재어트리뷰션
      </td>
    </tr>
    <tr>
      <td>
        attributed\_touch\_type
      </td>
      <td>
        가능한 값: 클릭, 노출, 사전 설치, 알 수 없음, TV, null
      </td>
    </tr>
    <tr>
      <td>
        days\_post\_attribution
      </td>
      <td>
        * 전환 날짜 이후 경과된 일수(특정 전환 타임스탬프 아님).
        * 팁! 이를 사용하여 보존 기간 및 KPI 일수를 계산합니다
      </td>
    </tr>
    <tr>
      <td>
        이벤트 날짜
      </td>
      <td>
        * 사용자가 지정된 이벤트를 수행하는 날짜입니다.
        * 형식: yyyy-mm-dd
        * 예시: 사용자가 지정된 인앱 이벤트를 수행한 날짜입니다. 전환의 경우.
        * 참고! event\_name이 af\_conversion인 경우, 이벤트 날짜와 전환 날짜는 동일합니다.
      </td>
    </tr>
    <tr>
      <td>
        conversion\_date
      </td>
      <td>
        * 전환이 발생한 날짜
        * 형식: yyyy-mm-dd
        * 예시: 설치 날짜
      </td>
    </tr>
    <tr>
      <td>
        event\_name
      </td>
      <td>
        이벤트를 식별합니다. 일부 이벤트 이름은 특정 의미를 갖지만, 다른 이벤트 이름은 앱에서 광고주가 설정한 인앱이벤트와 관련됩니다. 

        | event\_name | 사용자가 수행한 작업 |
        | --- | --- |
        | af\_conversion | 사용자가 전환했습니다. conversion\_type을 사용하여 인스톨인지, 리인게이지먼트인지 또는 리어트리뷰션인지를 식별합니다. |
        | af\_세션 | 앱 실행 |
        | 코호트 분석 | 앱 삭제 |
        | 광고주가 인앱이벤트 정의 | 앱에서 인앱이벤트를 실행했습니다. |
      </td>
    </tr>
    <tr>
      <td>
        campaign
      </td>
      <td>
        캠페인 구조

        고려 사항: 캠페인 이름 변경은 지원되지 않습니다. 따라서 지정된 캠페인 ID에 여러 이름을 연결할 수 있습니다.
      </td>
    </tr>
    <tr>
      <td>
        campaign\_id
      </td>
      <td>
        캠페인 구조
      </td>
    </tr>
    <tr>
      <td>
        광고 세트
      </td>
      <td>
        캠페인 구조
      </td>
    </tr>
    <tr>
      <td>
        adset\_id
      </td>
      <td>
        캠페인 구조
      </td>
    </tr>
    <tr>
      <td>
        광고
      </td>
      <td>
        캠페인 구조
      </td>
    </tr>
    <tr>
      <td>
        ad\_id
      </td>
      <td>
        캠페인 구조
      </td>
    </tr>
    <tr>
      <td>
        channe
      </td>
      <td>
        캠페인 구조.

        [2021년 10월 27일 업데이트] 현재 Meta 광고는 Google 설치 리퍼러 메커니즘을 통해 제공된 데이터에서 채널을 비워둡니다.
      </td>
    </tr>
    <tr>
      <td>
        site\_id
      </td>
      <td>
        캠페인 구조
      </td>
    </tr>
    <tr>
      <td>
        is\_primary\_attribution
      </td>
      <td>
        리타게팅 데이터를 식별하고 중복을 제거하는 데 사용합니다.
      </td>
    </tr>
    <tr>
      <td>
        geo
      </td>
      <td>
        사용자 IP 주소로부터 파생된 ISO 국가 코드입니다.
      </td>
    </tr>
    <tr>
      <td>
        agency
      </td>
      <td>
        * 에이전시 투명성 지원.
        * 비투명한 에이전시의 경우, 광고주와 에이전시가 동일한 이름의 캠페인을 진행하면 동일한 캠페인 이름을 가진 행이 여러 개 존재할 수 있습니다. 걱정하지 마세요. 행은 중복되지 않습니다.
      </td>
    </tr>
    <tr>
      <td>
        install\_app\_store
      </td>
      <td>
        Android 앱만 해당: 앱이 다운로드된 Android 스토어입니다. <Anchor target="_blank" href="/marketers/ko/docs/set-up-multi-store-android-attribution">다중 스토어 안드로이드 어트리뷰션</Anchor>을 구현하는 광고주가 채웁니다. 비어 있으면 구글 플레이 스토어를 의미합니다.
      </td>
    </tr>
    <tr>
      <td>
        키워드
      </td>
      <td>
        유저가 온라인 검색 시 사용한 단어들입니다. 애드 네트워크에서 보고된 내용입니다.
      </td>
    </tr>
    <tr>
      <td>
        keyword\_id
      </td>
      <td>
        [2022년 4월 27일부터 사용 가능한 필드] 광고 네트워크에서 반환된 키워드 ID.
      </td>
    </tr>
  </tbody>
</Table>

<div id="metrics" />

#### 측정 지표

| 필드 이름 | 설명 | 형식 |
| --- | --- | --- |
| unique\_users | 이벤트를 수행하는 당일 고유 사용자 수입니다. | 숫자 |
| revenue\_usd | <ul><li>수익 금액(USD)입니다. 예를 들어, $100.56은 100.56으로 반영됩니다.</li><li>소수점 이하 2자리까지 가능.</li></ul> | 숫자 |
| event\_count | 이벤트 발생 횟수입니다. | 숫자 |
| selected\_currency | 앱 설정에서 설정한 3자리 통화 코드(USD, EUR). <Anchor target="_blank" href="http://www.xe.com/symbols.php#section1">ISO-4217</Anchor> 형식. 이는 사용자 인터페이스에서 코호트의 수익을 표시하는 데 사용되는 통화와 동일합니다. | 문자열 |
| revenue\_selected\_currency | <ul><li>선택한 통화의 수익 금액입니다. 예를 들어 선택한 통화가 EUR인 경우 €1234.56는 1234.56으로 반영됩니다.</li><li>소수점 이하 2자리까지 가능</li></ul> | 숫자 |

</Accordion>

<div id="bi-developer-considerations" />

<Accordion title="BI 개발사 고려사항">

**리포트의 데이터 범위**

이 리포트에는 사용자 획득, 인스톨 및 리타게팅, 리어트리뷰션, 리인게이지먼트, 관련 인앱이벤트가 포함됩니다.

통합, 사용자 획득 및 리타게팅 보고서를 개별적으로 또는 함께 BI에 로드할 수 있습니다. 함께 로드하고 직접 뷰를 필터링하려는 경우:

* 통합의 경우 is\_primary\_attribution=true 또는 null 필드를 사용합니다.
* 사용자 확보의 경우 conversion\_type=Install을 사용합니다.
* 리타게팅의 경우 conversion\_type=리인게이지먼트 또는 리어트리뷰션을 사용합니다.

데이터 로딩 과정에 통합 뷰를 사용하는 경우 로직을 사용하여 캠페인 유형 간에 데이터를 분할해야 합니다. 다시 말하면 사용자 어트리뷰선(인스톨)과 리타게팅(리인게이지먼트)입니다. 이를 위해, conversion\_type=install, install\_unified, 리인게이지먼트 또는 리어트리뷰션을 사용합니다. <Anchor target="_blank" href="/marketers/ko/docs/resolve-retargeting-double-attribution">리타게팅 이벤트의 이중 어트리뷰션</Anchor>을 참고하십시오.

**필드 수준 고려 사항**

* 사후 어트리뷰션 날짜를 사용하여 리텐션 지표 계산을 쉽게 합니다.
* 캠페인 이름 및 캠페인 ID 차원을 사용하여 고유 사용자 계산: 캠페인 이름 세분성을 무시할 수 있는 경우, 캠페인 ID의 고유 개수를 합산할 수 있으며 지표가 정확합니다.
* 캠페인 계층 구조 필드를 사용하여 데이터를 집계할 수 있습니다.
* 매출은 USD로 표시되며 이벤트 당일의 환율로 계산됩니다.
* 광고 수익 이벤트는 가능한 경우 포함되지만, 업데이트는 최대 3일 지연될 수 있습니다.

**일반 고려 사항**

모든 앱의 데이터는 단일 파일로 제공됩니다. 앱 ID 필드를 사용하여 앱별로 데이터를 분리하거나 데이터 락커를 앱별로 분리하도록 설정합니다.

</Accordion>

<div id="use-cases" />

<Accordion title="활용 사례">

다음은 BI 개발자가 데이터 락커를 통해 추출할 수 있는 코호트 데이터의 인기 있고 실용적인 애플리케이션의 예입니다. 각 예제를 SQL 문과 샘플 Excel 시각적 개체로 설명합니다.

<div id="1-calculating-retention" />

#### **1. 리텐션 계산**

아래 예제에서는 다음을 수행합니다.

* 1일 차와 7일 차의 리텐션과 캠페인 및 광고당 총 인스톨 수를 계산합니다.
* `event_name`을 필터링하여 전환 이벤트당 이벤트 수를 합산합니다.`af_conversion`
* 데이터를 필터링하여 사용자 유입 캠페인을 구체적으로 분석합니다 `conversion_type=install`.

**SQL 문**

```sql
select
    campaign_id, ad_id,
    sum(if(event_name = 'af_conversion', event_count,0)) as installs,
    sum(if(event_name = 'af_session' and days_post_attribution = 1, unique_users,0)) / sum(if(event_name = 'af_conversion', event_count,0)) as retention_day1,
    sum(if(event_name = 'af_session' and days_post_attribution = 7, unique_users,0)) / sum(if(event_name = 'af_conversion', event_count,0)) as retention_day7
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    // If you're querying data from unified reports, edit the line below to: and conversion_type IN ('install', 'install_unified')    
    and conversion_type = 'install'
    and app_id = YOUR_APP
group by 1,2
```

**Excel 예제**

| 캠페인 ID | 광고 ID | 인스톨 | 리텐션 1일차 | 리텐션 7일차 |
| --- | --- | --- | --- | --- |
| 12345678 | 987654 | 100 | 30% | 10% |
| 98765432 | 123456 | 200 | 25% | 15% |
| 07315466 | 613770 | 300 | 20% | 12% |

<div id="2-calculating-arpu-of-multiple-in-app-events" />

#### **2. 여러 인앱 이벤트의 ARPU 계산**

아래 예제에서는 다음을 수행합니다.

* 캠페인당 다중 인앱이벤트의 ARPU를 계산합니다.
* 특히 `conversion_type=re-engagement`과 `conversion_type=re-attribution`를 기준으로 데이터를 필터링하여 리타게팅 캠페인을 구체적으로 분석합니다.
* `event_name`을 필터링하여 전환 이벤트당 이벤트 수를 합산합니다.`af_conversion`
* 이 경우 `af_purchase`과 `af_coins`의 여러 이벤트의 수익을 합산합니다.
* 데이터 처리 부하를 최소화하려면 `days_post_attribution`를 필요한 최소값(이 경우 7)으로 설정합니다.

**SQL 문**

```sql
select
    campaign_id,
    sum(if(days_post_attribution <= 1 and event_name in ('af_purchase', 'af_coins') , revenue_usd, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day1,
    sum(if(days_post_attribution <= 3 and event_name in ('af_purchase', 'af_coins') , revenue_usd, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day3,
    sum(if(days_post_attribution <= 7 and event_name in ('af_purchase', 'af_coins') , revenue_usd, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day7
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    and days_post_attribution <= 7
    and conversion_type in ('re-engagement', 're-attribution')
    and app_id = YOUR_APP
group by 1
```

**Excel 예제**

| 캠페인 ID | 전환 유형 | ARPU<br /><br />1일 차 | ARPU<br /><br />3일 차 | ARPU<br /><br />7일 차 |
| --- | --- | --- | --- | --- |
| 12345678 | 리인게이지먼트 | 6.23 | 5.11 | 2.34 |
| 98765432 | 리인게이지먼트 | 3.57 | 1.34 | 4.86 |
| 07315466 | 리어트리뷰션 | 7.41 | 6.79 | 5.29 |

<div id="3-calculating-in-app-event-conversion-rate-for-a-specific-cohort-day" />

#### **3. 특정 코호트일의 인앱 이벤트 전환율 계산**

아래 예제에서는 다음을 수행합니다.

* 여러 측정기준(이 경우 전환일, 지역, 캠페인, 광고, 사이트 ID)에 대한 0일 차 인앱 이벤트 전환율을 계산합니다.
* 통합 데이터를 분석하여 UA와 리타게팅 캠페인 모두에 대한 필터링을 합니다 `is_primary_attribution=true`.
* `event_name`을 필터링하여 전환 이벤트당 이벤트 수를 합산합니다.`af_conversion`
* 데이터 처리 부하를 최소화하려면 `days_post_attribution`를 필요한 최소값(이 경우 7)으로 설정합니다.

**SQL 문**

```sql
select
    conversion_date, geo, campaign_id, ad_id, site_id,
    sum(if(days_post_attribution = 0 and event_name = 'af_complete_tutorial', unique_users, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as day0_af_tutorial_conversion
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    and is_primary_attribution = true
    and app_id = YOUR_APP
group by 1,2,3,4,5
```

**Excel 예제**

| 전환 날짜 | 지역 | 캠페인 ID | 광고 ID | 사이트 ID | 0일 차 af\_complete\_tutorial |
| --- | --- | --- | --- | --- | --- |
| 2022-11-07 | 미국 | 12345678 | 123456 | site\_123 | 45% |
| 2022-11-05 | 영국 | 98765432 | null | 사이트\_654 | 70% |
| 2022-10-31 | 한국 | 07315466 | null | null | 63% |

<div id="4-calculating-daily-installs" />

#### **4. 일일 인스톨 계산**

아래 예제에서는 다음을 수행합니다.

* 앱 ID, 전환 날짜, 미디어 소스, 이벤트 이름, 전환 유형별로 인스톨 수를 계산합니다.
* UA 인스톨을 표시하도록 `conversion_type`을 `install`로 설정하여 데이터를 필터링합니다 (리타게팅 제외).
* `event_name`을 `af_conversion`로 설정하여 인스톨을 합산합니다.

**SQL 문**

```sql
select
    app_id,
    conversion_date,
    media_source,
    event_name,
    conversion_type,
    sum(events_count) as total
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    // If you're querying data from unified reports, edit the line below to: and conversion_type IN ('install', 'install_unified')
    and conversion_type = 'install'
    and event_name = 'af_conversion'
    and app_id = YOUR_APP
group by 1,2,3,4,5
```

**Excel 예제**

| 앱 ID | 전환 날짜 | 미디어 소스 | 이벤트 이름 | 합계 |
| --- | --- | --- | --- | --- |
| id123456789 | 2022-11-07 | adnet1\_int | af\_conversion | 105 |
| id123456789 | 2022-11-05 | adnet2\_int | af\_conversion | 216 |
| id123456789 | 2022-10-31 | adnet3\_int | af\_conversion | 327 |

<div id="5-calculating-revenue-from-facebook-ads" />

#### **5. 페이스북 광고 수익 계산**

아래 예제에서는 다음을 수행합니다.

* 전환 날짜 및 앱 ID를 기준으로 Facebook의 3일 차 수익을 계산합니다.
* 페이스북 데이터를 분석할 때 `media_source='Facebook Ads'`에 맞게 데이터를 필터링합니다.
* 데이터 처리 부하를 최소화하려면 `days_post_attribution`을 필요한 최소값(이 경우 3)으로 설정합니다.

**SQL 문**

```sql
select
    conversion_date,
    app_id,
    media_source,
    sum(if(days_post_attribution <= 3, revenue_usd, 0)) as revenue_day3
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2022-06-01' and '2023-05-31'
    and days_post_attribution <= 3
    and media_source = 'Facebook Ads'
    and app_id in (APP_ID1, APP_ID2, ...)
group by 1,2,3
```

**Excel 예제**

| 전환 날짜 | 앱 ID | 미디어 소스 | 수익<br /><br />3일 차 |
| --- | --- | --- | --- |
| 2022-11-07 | id123456789 | adnet1\_int | 400.45 |
| 2022-11-05 | id123456789 | adnet2\_int | 99.23 |
| 2022-10-31 | id123456789 | adnet3\_int | 13.34 |

<div id="6-calculating-arpu-per-asa-keyword-id-for-up-to-365-cohort-days" />

#### **6. 최대 365일의 코호트 일 동안 ASA 키워드 ID당 ARPU 계산**

아래 예제에서는 다음을 수행합니다.

* 코호트 365일까지 키워드 ID별로 Apple Search Ads의 ARPU를 계산합니다.
* `media_source='Apple Search Ads'`에 맞게 데이터를 필터링하여 Apple Search Ads 데이터를 분석합니다.
* `event_name`을 필터링하여 전환 이벤트당 이벤트 수를 합산합니다.`af_conversion`

**SQL 문**

```sql
select
    media_source,
    keyword_id,
    sum(if(days_post_attribution <= 365, revenue_usd,0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day365
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2022-06-01' and '2023-05-31'
    and media_source = 'Apple Search Ads'
    and app_id = YOUR_APP
group by 1
```

**Excel 예제**

| 미디어 소스 | 키워드 ID | ARPU<br /><br />365일 차 |
| --- | --- | --- |
| adnet1\_int | 123456 | 57,019.93 |
| adnet2\_int | 987654 | 64,867.84 |
| adnet3\_int | 666854 | 48,160.02 |

<div id="7-calculating-arpu-days-7-by-attribution-time-per-geo" />

#### **7. 지역별 어트리뷰션 시간에 따른 ARPU 7일 계산**

다음 예제에서는 <Anchor target="_blank" href="/marketers/ko/docs/cohort-and-retention-dashboard#trend-type%E2%80%94kpi-by-attribution-time">어트리뷰션 시간별 KPI</Anchor>를 활용하는 방법을 보여줍니다. 이 예에서는 다음을 수행합니다.

* 지역별 어트리뷰션 날짜별로 ARPU 7일차를 계산합니다.
* 결과는 전환 수를 기준으로 정렬되며 상위 20개 지역이 표시됩니다.
* `conversion_type='install'`하도록 데이터가 필터링되었습니다.
* 첫 번째 열에는 지역이 표시됩니다. 두 번째 열에는 총 전환수가 나옵니다. 그 이후의 열에는 쿼리에 행으로 지정된 각 날짜에 대한 7일차 수익이 나타납니다.

**SQL 문**

```sql
select
    geo,
    sum(if(event_name = 'af_conversion', event_count, 0)) total_conversions,
    sum(if(cohort_day = '2023-07-11' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-11' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_11,
    sum(if(cohort_day = '2023-07-12' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-12' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_12,
    sum(if(cohort_day = '2023-07-13' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-13' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_13,
    sum(if(cohort_day = '2023-07-14' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-14' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_14,
    sum(if(cohort_day = '2023-07-15' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-15' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_15,
    sum(if(cohort_day = '2023-07-16' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-16' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_16
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-07-11' and '2023-07-16'
    and days_post_attribution <= 7
    // If you're querying data from unified reports, edit the line below to: and conversion_type IN ('install', 'install_unified')
    and conversion_type = 'install'
    and app_id = 'YOUR_APP'
group by 1
order by 2 desc
limit 20
```

**Excel 예제**

| 지역 | 총 전환수 | 2023-07-11 ARPU 7일차 | 2023-07-12 ARPU 7일차 | 2023-07-13 ARPU 7일차 | 2023-07-11 ARPU 7일차 | 2023-07-11 ARPU 7일차 | 2023-07-16 ARPU 7일차 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 한국 | 120,660 | 7,798.89달러 | 6,997.37달러 | 8,258.95달러 | 9,050.21달러 | 10,018.04 | 13,765.73달러 |
| 캐나다 | 35,099 | 64,867.84달러 | 7,050.19달러 | 5,656.33달러 | 9,553.75달러 | 8,632.41달러 | 11,308.06달러 |
| 칠레 | 26,750 | 48,160.02 | 21,249.55달러 | 22,584.57달러 | 24,033.07 | 31,118.91달러 | 41,145.22달러 |

</Accordion>

<div id="additional-information" />

## 추가 정보

<div id="traits-and-limitations" />

<Accordion title="특성 및 한계">

| 특성 |  |
| --- | --- |
| 비용 데이터 | <ul><li>해당 없음. <Anchor target="_blank" href="/marketers/ko/docs/set-up-and-use-roi360-cost-etl-reports">Cost ETL 사용</Anchor>.</li><li><Anchor target="_blank" href="/marketers/ko/docs/combine-cost-etl-and-cohort-reports-via-data-locker">Cost ETL과 코호트 보고서 병합</Anchor> 참조.</li></ul> |
| 캠페인 이름 변경 | 지원되지 않습니다. |
| 데이터 최신성 | 일일 UTC. 보고서는 보고 당일의 데이터 락커에 다음날 UTC 10:00에 있습니다. |
| 광고 수익 | <ul><li>사용 가능</li><li>af\_ad\_revenue 이벤트의 경우, 2022년 10월 5일부터 2023년 2월 16일까지의 날짜에는 고유 사용자 지표를 사용할 수 없습니다.</li></ul> |
| 통화 | 행에 USD와 앱 특정 통화를 모두 사용할 수 있습니다. |
| 시간대 | <ul><li>UTC</li><li>앱별 시간대는 <Anchor target="_blank" href="/marketers/ko/docs/advanced-aggregated-reports-in-data-locker">고급 집계 코호트 시간대 버전 보고서</Anchor>에서 확인할 수 있습니다.</li></ul> |
| 오가닉 데이터 | 사용 가능 |
| 전환 후 날짜(인스톨, 리어트리뷰션, 리인게이지먼트) | <ul><li>365일 설치 후 데이터를 사용할 수 있습니다.</li><li><Anchor target="_blank" href="/marketers/ko/docs/advanced-aggregated-reports-in-data-locker">고급 집계 보고서</Anchor>로 1,095일치 데이터를 볼 수 있습니다.</li></ul> |
| 에이전시 투명성 | <ul><li>지원됨.</li><li>X 광고 및 메타 광고 데이터는 항상 투명합니다.</li></ul> |
| 앱 분리 | 지원됨. |
| SKAN 데이터 | 포함되지 않음. 다시 말하면 iOS 포스트백에서 제공한 데이터. |
| 재설치 | <ul><li>재설치 후 이벤트가 속성이 없는 오가닉이라고 간주되는 경우:<ul><li>2024년 5월 26일부터 포함됩니다. <Anchor target="_blank" href="/marketers/ko/docs/bulletin-cohort-data-includes-unattributed-sessions-and-events">더 알아보기</Anchor></li><li>설치 시간은 <Anchor target="_blank" href="/marketers/ko/docs/raw-data-field-dictionary#device-info::dfd9504e">device\_download\_time</Anchor> 필드를 기반으로 합니다.</li><li>고유 사용자 및 유지 측정에 포함되지 않습니다.</li></ul></li><li>재설치 후 이벤트가 첫 설치에 속하는 경우 항상 포함됩니다. <Anchor target="_blank" href="/marketers/ko/docs/unique-users">더 알아보기</Anchor></li></ul> |

</Accordion>

<div id="see-also" />

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/combine-cost-etl-and-cohort-reports-via-data-locker">Cost ETL과 코호트 보고서 병합</Anchor>
> * <Anchor target="_blank" href="/marketers/ko/docs/cohort-and-retention-dashboard">코호트 대시보드</Anchor>

<div data-zendesk-anchors="cohort-analytics-in-data-locker=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%9D%BD%EC%BB%A4%EC%97%90%EC%84%9C-%EC%BD%94%ED%98%B8%ED%8A%B8-%EB%B6%84%EC%84%9D 01H7WG3CA1DDAN79D1PBPE0RJ3=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%9D%BD%EC%BB%A4%EC%97%90%EC%84%9C-%EC%BD%94%ED%98%B8%ED%8A%B8-%EB%B6%84%EC%84%9D 01H7WG3CA1ZMNTGZ5B8FNXNC4A=enable-data-locker 01H7WG3CA179D6VCWYPCJ1G49M=facts 01H7WG3CA1R3PZCKSGWC90E7RC=report-structure dimensions=%EB%94%94%EB%A9%98%EC%85%98 01H7WG3CA14PQ2PJ58FX8TE6ZH=%EB%94%94%EB%A9%98%EC%85%98 metrics=%EC%B8%A1%EC%A0%95-%EC%A7%80%ED%91%9C 01H7WG3CA24VQKFVP99S82GCXZ=%EC%B8%A1%EC%A0%95-%EC%A7%80%ED%91%9C 01H7WG3CA2C3HV8YT5ZMP9E0QY=bi-developer-considerations 01H7WG3CA2YF03SC6RBMCJYYVX=use-cases 1-calculating-retention=1-%EB%A6%AC%ED%85%90%EC%85%98-%EA%B3%84%EC%82%B0 h_01HMTZ0DZWN54HBQ0ZTY0VFNFM=1-%EB%A6%AC%ED%85%90%EC%85%98-%EA%B3%84%EC%82%B0 2-calculating-arpu-of-multiple-inapp-events=2-%EC%97%AC%EB%9F%AC-%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%9D%98-arpu-%EA%B3%84%EC%82%B0 h_01HMTZ0DZWHZ77RYWYAQEJV7X5=2-%EC%97%AC%EB%9F%AC-%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%9D%98-arpu-%EA%B3%84%EC%82%B0 3-calculating-inapp-event-conversion-rate-for-a-specific-cohort-day=3-%ED%8A%B9%EC%A0%95-%EC%BD%94%ED%98%B8%ED%8A%B8%EC%9D%BC%EC%9D%98-%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%A0%84%ED%99%98%EC%9C%A8-%EA%B3%84%EC%82%B0 h_01HMTZ0DZW7VA6T6MQY7BY1JZT=3-%ED%8A%B9%EC%A0%95-%EC%BD%94%ED%98%B8%ED%8A%B8%EC%9D%BC%EC%9D%98-%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%A0%84%ED%99%98%EC%9C%A8-%EA%B3%84%EC%82%B0 4-calculating-daily-installs=4-%EC%9D%BC%EC%9D%BC-%EC%9D%B8%EC%8A%A4%ED%86%A8-%EA%B3%84%EC%82%B0 h_01HMTZ0DZWARZFAQ9R4VF56YN3=4-%EC%9D%BC%EC%9D%BC-%EC%9D%B8%EC%8A%A4%ED%86%A8-%EA%B3%84%EC%82%B0 5-calculating-revenue-from-facebook-ads=5-%ED%8E%98%EC%9D%B4%EC%8A%A4%EB%B6%81-%EA%B4%91%EA%B3%A0-%EC%88%98%EC%9D%B5-%EA%B3%84%EC%82%B0 h_01HMTZ0DZW74HWW6Z3VDWDMGRF=5-%ED%8E%98%EC%9D%B4%EC%8A%A4%EB%B6%81-%EA%B4%91%EA%B3%A0-%EC%88%98%EC%9D%B5-%EA%B3%84%EC%82%B0 6-calculating-arpu-per-asa-keyword-id-for-up-to-365-cohort-days=6-%EC%B5%9C%EB%8C%80-365%EC%9D%BC%EC%9D%98-%EC%BD%94%ED%98%B8%ED%8A%B8-%EC%9D%BC-%EB%8F%99%EC%95%88-asa-%ED%82%A4%EC%9B%8C%EB%93%9C-id%EB%8B%B9-arpu-%EA%B3%84%EC%82%B0 h_01HMTZ0DZWSN83V0TEHVM2H5XS=6-%EC%B5%9C%EB%8C%80-365%EC%9D%BC%EC%9D%98-%EC%BD%94%ED%98%B8%ED%8A%B8-%EC%9D%BC-%EB%8F%99%EC%95%88-asa-%ED%82%A4%EC%9B%8C%EB%93%9C-id%EB%8B%B9-arpu-%EA%B3%84%EC%82%B0 calculating-arpu-days-0-7-by-attribution-time-per-geo=7-%EC%A7%80%EC%97%AD%EB%B3%84-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%8B%9C%EA%B0%84%EC%97%90-%EB%94%B0%EB%A5%B8-arpu-7%EC%9D%BC-%EA%B3%84%EC%82%B0 01H8XYTJVQ1YFBHPWVPP9D7MJ8=7-%EC%A7%80%EC%97%AD%EB%B3%84-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%8B%9C%EA%B0%84%EC%97%90-%EB%94%B0%EB%A5%B8-arpu-7%EC%9D%BC-%EA%B3%84%EC%82%B0 additional-information=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 01H7WG3CA255TG9HW150RW1QTX=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 01H7WG3CA2Y59D2EVMN3YFFY1W=traits-and-limitations h_01HDNZ8A0QH74CGSEG6TKKARJP=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
