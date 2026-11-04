---
title: 앱스플라이어 대시보드 및 리포트의 불일치 문제 해결
metadata:
  keywords:
    - dashboard
    - activity
    - Advertisers
    - ltv
    - life time value
    - lifetime value
    - lifetime
    - Agencies
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
  created_at: '2017-11-07T12:42:27Z'
  edited_at: '2026-10-14T10:34:01Z'
  id: 115005600889
  locale: ko
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/ko/articles/115005600889
---
> **한눈에 보기:** 다양한 대시보드 및 리포트의 데이터를 비교할 때 차이와 불일치가 발생하는 이유를 이해합니다. 이러한 차이는 한쪽은 LTV 데이터, 다른 한쪽은 액티비티 데이터를 기준으로 하고 있기 때문에 발생하는 경우가 많습니다. LTV 데이터는 특정 날짜 범위 내에 발생한 인스톨과 관련이 있습니다. 액티비티 데이터는 특정 날짜 범위 내에 발생한 이벤트입니다.

<div id="about-data-differences-and-discrepancies" />

## 데이터 차이 및 불일치에 대한 정보

서로 다른 대시보드와 리포트를 비교할 때 데이터 불일치가 발생하는 주된 이유는, 같은 데이터를 기준으로 비교하지 않았기 때문일 수 있습니다. 다음은 동일한 데이터를 비교 중인지 확인하는 데 유용한 간단한 체크리스트입니다.

* 앱 플랫폼이 동일합니까? (안드로이드, iOS, CTV 등)
* 앱 ID가 동일합니까?
* 대시보드/데이터 필터가 동일합니까?
* 통화가 동일합니까?
* 시간대가 동일합니까?
* <Anchor target="_blank" href="/marketers/ko/docs/about-data-freshness-and-timezone-support">데이터 최신성</Anchor>이 동일합니까?
* 데이터가 <Anchor target="_blank" href="/marketers/ko/docs/aggregated-and-analytics-reporting-overview#toolapi-comparison">집약 데이터</Anchor>입니까, 아니면 <Anchor target="_blank" href="/marketers/ko/docs/raw-data-reporting-overview">로데이터</Anchor>입니까?
* LTV 데이터입니까, 아니면 액티비티 데이터 입니까?

데이터 간 차이가 발생하는 가장 흔한 이유 중 하나는 LTV 대시보드 혹은 리포트를 액티비티 대시보드와 비교하는 데에서 비롯됩니다. LTV와 액티비티에 대해 더 알아보려면 다음 섹션을 참조하십시오.

<div id="ltv-vs-activity" />

## LTV vs 액티비티(Activity)

사용자 이벤트 데이터를 분석하는 데는 두 가지 방법이 있습니다. 이벤트 데이터는 인앱 구매, 등록 및 레벨 완료 등 인스톨 후 사용자가 수행한 작업과 관련됩니다. 앱스플라이어 이벤트 데이터는 유저 유입 날짜 또는 이벤트 날짜별로 그룹화되어 제공됩니다.

* 설치 후 발생하는 이벤트 데이터를 유저 유입일 기준으로 그룹화한 것을 'LTV(유저 생애 가치)'라고 합니다.
* 설치 후 이벤트 데이터가 이벤트 발생일 기준으로 그룹화된 것을 ‘액티비티’라고 합니다.

**참고**: 인스톨는 LTV도 아니고 액티비티도 아닙니다.

광고주들은 두 데이터 모두 활용하지만, 각각 다른 용도로 사용합니다. 따라서, 두 종류의 데이터 모두 사용 가능합니다.

<div id="ltv-data" />

### LTV 데이터

* LTV 데이터는 지정된 기간 동안 앱을 설치하거나 전환한 사용자가 이후에 수행한 모든 이벤트를 의미합니다. 날짜 범위는 해당 기간 동안 설치한 사용자와 그들이 고객으로서 얼마나 가치 있는지를 보여줍니다. 사용자가 지정된 날짜 이전에 앱을 전환/설치한 경우, 지정된 날짜 범위 동안 이벤트가 발생하더라도 LTV 대시보드 및 리포트에 표시되지 않습니다.
* LTV 데이터는 서로 다른 미디어 소스의 **사용자 품질**을 보여주는 툴입니다. 캠페인 최적화는 LTV 데이터에 기반합니다.

<div id="activity-data" />

### 액티비티 데이터

* 액티비티 데이터는 지정된 날짜 범위 동안 사용자가 수행한 작업을 보여줍니다. 즉, 지정된 날짜 범위 동안 활성 앱 사용자가 수행한 이벤트를 의미합니다. 사용자가 설정한 날짜 범위를 벗어나 앱을 설치/전환했는지 여부는 영향을 주지 않습니다.
* 액티비티 데이터는 시간별 이벤트의 내역을 보여주기 때문에 특정 기간 동안 미디어소스의 전체 성과를 측정하는 데 유용합니다. 예를 들어, 액티비티 데이터를 사용하여 특정한 달 동안 모든 앱 사용자가 수행한 구매 이벤트 수를 확인합니다.
* 액티비티 데이터를 활용해 이번 달 사용자 행동을 지난달과 비교합니다.

<div id="the-train-analogy" />

> 📄 **기차 방법론(Train Analogy)**
>
> LTV와 액티비티 데이터의 차이를 이해하는 데 있어, 여기서 설명하는 비유가 도움이 될 수 있습니다.
>
> **액티비티:** 지나가는 기차를 보고 있다고 상상해 보십시오. 기차가 지나가는 동안, 우리는 차 안의 승객들이 그 순간에 취하는 행동만 볼 수 있습니다. 이를 액티비티 데이터라고 합니다.
>
> <Image alt="activity_data.jpg" src="https://files.readme.io/70a37d5dc16f0817d137f9011be9af5360bd7c4d2469a8abf9430fe69b2671c3-360002436957.jpg" width="400px" />
>
> **LTV**: 이제 귀하가 관찰자로서 기차를 탄다고 상상해 보십시오. 그 기차는 여러 차량 칸으로 나뉘어져 있습니다.
>
> * 귀하는 출발 플랫폼에서 다른 승객들과 함께 차에 탑승합니다. 이것이 인스톨입니다.
> * 귀하는 주행 중에 차 안의 승객이 수행하는 모든 행동을 관찰할 수 있습니다. 승객들이 기차에서 내릴 때까지 승객들의 행동을 관찰하는 상황은 앱 삭제에 비유할 수 있습니다.
> * 다른 열차칸에 탑승한 승객의 행동은 그들이 귀하보다 이전 또는 이후에 탑승한 승객이기 때문에 볼 수 없습니다. 이는 LTV에 해당합니다.
>
> <Image alt="ltv_data.jpg" src="https://files.readme.io/78925644f263b6d5ea5630a09e0b2155d153ce2c4b3060be5c8d7cb9ba0ce4e6-360002436977.jpg" width="400px" />

<div id="appsflyer-dashboards-and-reportsltv-or-activity" />

### 앱스플라이어 대시보드 및 리포트—LTV 또는 액티비티?

대시보드를 통해 마케터는 논오가닉 트래픽을 최적화할 수 있습니다. 대부분의 대시보드는 LTV 기반으로 하며, 마케터는 일반적으로 LTV 기준으로 성과를 측정합니다. 모든 집약 데이터 리포트는 LTV 기반이며, 모든 로데이터 리포트는 액티비티 데이터를 기반으로 합니다.

다음 표는 어떤 대시보드와 리포트가 LTV에 해당하고, 어떤 것이 액티비티에 해당하는지 보여줍니다.

| 데이터 소스 | 데이터 유형 |
| --- | --- |
| 개요 대시보드 | LTV |
| My Dashboards | LTV |
| SKAN 개요 | LTV |
| Protect360 인스톨 | LTV |
| Protect360 인앱 이벤트 | 액티비티 |
| 액티비티 대시보드 | 액티비티 |
| 이벤트 대시보드 | LTV |
| 리텐션 | LTV |
| 코호트 | LTV |
| 집약 데이터 성과 리포트 | LTV |
| 로데이터(Raw data) 리포트 | 액티비티 |
| 리타겟팅 리포트 | LTV |
| Protect360 프로드 방지 리포트 | 액티비티 |
| 마스터 API—캠페인 성과 KPI | 둘 다 |
| 피벗 테이블 | 둘 다 |

<div id="compare-data-between-different-dashboards-and-reports" />

## 다양한 대시보드와 리포트 간의 데이터 비교

다음 섹션에서는 서로 다른 대시보드 및 리포트 간의 데이터를 비교하는 방법과, 데이터의 차이 또는 불일치 원인을 파악하고 해결하는 방법을 안내합니다.

<div id="compare-ltv-and-activity-data-in-appsflyer" />

<Accordion title="앱스플라이어에서 LTV 데이터와 액티비티 데이터 비교">

앱스플라이어 데이터를 비교할 때, 특히 LTV 데이터와 액티비티 데이터를 비교할 때 고려해야 할 두 가지 차이점이 있습니다:

1. 액티비티 데이터는 선택한 기간 **이전에 발생한 인스톨**로부터 생성된 이벤트를 포함합니다.
2. LTV 데이터에는 선택한 날짜 범위 **이후에 발생한 이벤트**도 포함됩니다.

두 데이터를 올바르게 비교하려면, 차이를 제거하거나 보정해야 합니다. 이를 잘 활용하여 LTV에서 액티비티로 또는 그 반대 방향으로의 데이터 비교가 가능합니다. **참고**: 각 소스별 리포트 생성 시간에 따라 작은 차이가 발생할 수 있습니다.

<div id="to-retrieve-ltv-data-out-of-raw-activity-data" />

#### 액티비티 로데이터에서 LTV 데이터를 추출하려면:

1. 앱스플라이어의 사이드 메뉴에서 **리포트** > **로데이터 내보내기를 선택합니다.**
2. 기간을 선택할 때 **오늘을 마지막날(current day as the last day)** 로 선택합니다 (이를 통해 2번째 차이점에 대한 문제 해결)
3. 인앱 이벤트 로리포트를 다운로드합니다.
4. **설치 시간(Install Time)** 칼럼에 필터를 걸어 선택한 기간 이전에 포함되는 날짜를 제거합니다. (이를 통해 1번째 차이점에 대한 문제 해결)

<div id="to-retrieve-activity-data-out-of-ltv-data" />

#### LTV 데이터에서 액티비티 데이터를 추출하려면:

1. **앱스플라이어에서 지정된 날짜 범위 내에 설치 데이터를 전송하기 시작한 미디어 소스를 선택하세요.** (이를 통해 1번째 차이점에 대한 문제 해결)  
   이를 통해 선택한 날짜 이전의 인스톨에서 발생한 인앱 이벤트들을 포함하지 않도록 설정할 수 있습니다.
2. 기간을 선택할 때 **오늘을 마지막날(current day as the last day)로 설정합니다.** (이를 통해 2번째 차이점에 대한 문제 해결)  
   이를 통해 선택한 날짜 이후에 발생하는 인앱 이벤트들을 포함하지 않게 할 수 있습니다.

</Accordion>

<div id="compare-different-appsflyer-aggregated-data-dashboards-and-reports" />

<Accordion title="다양한 앱스플라이어 집약 데이터 대시보드 및 리포트 비교">

다양한 앱스플라이어 집약 데이터 대시보드 및 리포트 간의 데이터를 비교할 때 LTV와 액티비티 데이터간 불일치의 원인일 수 있습니다.

데이터를 지역(Geo) 기준으로 집계할 경우, 차이가 발생하는 또 다른 이유는 앱스플라이어 대시보드에서는 '설치가 발생한 국가'를 기준으로 집계되는 반면, 원시 데이터 리포트에서는 '이벤트가 발생한 국가'를 기준으로 집계되기 때문일 수 있습니다.

그러나 다른 이유가 있을 수도 있음을 고려하십시오. <Anchor target="_blank" href="/marketers/ko/docs/aggregated-and-analytics-reporting-overview#toolapi-comparison">자세한 정보는 집약 리포팅 방법 비교를 참조하십시오</Anchor>

</Accordion>

<div id="compare-appsflyer-data-with-external-data" />

<Accordion title="앱스플라이어 데이터와 외부 데이터 비교">

Google 및 Apple을 포함한 대부분의 데이터 소스는 LTV 데이터가 아닌 액티비티 데이터를 표시합니다. 따라서 외부 소스의 데이터를 앱스플라이어 데이터와 비교하려면 일반적으로 로데이터 리포트에서 사용 가능한 앱스플라이어 액티비티 데이터를 사용합니다.

Meta Ads는 설치 후 28일 동안의 일부 LTV 데이터만 제공하므로, 이 점을 고려해야 합니다.

앱스플라이어 데이터와 외부 데이터 간의 차이가 발생하는 데에는 다른 원인들도 있을 수 있습니다. 다음 자료를 참조하십시오.

* <Anchor target="_blank" href="/marketers/ko/docs/google-analytics-integration-discrepancies">Google 애널리틱스 불일치</Anchor>
* <Anchor target="_blank" href="/marketers/ko/docs/meta-ads-discrepancies">Meta Ads 불일치</Anchor>
* <Anchor target="_blank" href="/marketers/ko/docs/snapchat-integration-discrepancies">Snapchat 불일치</Anchor>
* <Anchor target="_blank" href="/marketers/ko/docs/google-ads-adwords-faq-and-discrepancies">Google Ads 불일치</Anchor>
* <Anchor target="_blank" href="/marketers/ko/docs/x-ads-formerly-twitter-ads-faq-and-discrepancies">X Ads 불일치</Anchor>
* <Anchor target="_blank" href="/marketers/ko/docs/attribution-discrepancies-between-tiktok-for-business-and-appsflyer">TikTok 불일치</Anchor>
* <Anchor target="_blank" href="/marketers/ko/docs/resolve-appsflyer-app-stores-discrepancies">앱 스토어 불일치</Anchor>
* <Anchor target="_blank" href="/marketers/ko/docs/discrepancies-between-appsflyer-and-third-party-platforms">써드파티 플랫폼 불일치</Anchor>

</Accordion>

<div data-zendesk-anchors="ltv-vs-activity=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%B0%A8%EC%9D%B4-%EB%B0%8F-%EB%B6%88%EC%9D%BC%EC%B9%98%EC%97%90-%EB%8C%80%ED%95%9C-%EC%A0%95%EB%B3%B4 h_01HKA0R42YZMAM5Y20B7T2JCDZ=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%B0%A8%EC%9D%B4-%EB%B0%8F-%EB%B6%88%EC%9D%BC%EC%B9%98%EC%97%90-%EB%8C%80%ED%95%9C-%EC%A0%95%EB%B3%B4 h_01J5WGZ13WPMNSB1NA0SMA77WJ=ltv-vs-%EC%95%A1%ED%8B%B0%EB%B9%84%ED%8B%B0activity ltv-data=ltv-%EB%8D%B0%EC%9D%B4%ED%84%B0 h_01HKA0R42YQ2CJS67MDQSJHKEW=ltv-%EB%8D%B0%EC%9D%B4%ED%84%B0 activity-data=%EC%95%A1%ED%8B%B0%EB%B9%84%ED%8B%B0-%EB%8D%B0%EC%9D%B4%ED%84%B0 h_01HKA0R42Y987PJRM70M7DFJ98=%EC%95%A1%ED%8B%B0%EB%B9%84%ED%8B%B0-%EB%8D%B0%EC%9D%B4%ED%84%B0 h_01J5WGZ13W5W8NJ1CRZQPHY939=%EA%B8%B0%EC%B0%A8-%EB%B0%A9%EB%B2%95%EB%A1%A0train-analogy appsflyer-dashboards%E2%80%94ltv-or-activity=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C-%EB%B0%8F-%EB%A6%AC%ED%8F%AC%ED%8A%B8ltv-%EB%98%90%EB%8A%94-%EC%95%A1%ED%8B%B0%EB%B9%84%ED%8B%B0 h_01HKA0R42Y558BQ45Y9MFZHZM0=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C-%EB%B0%8F-%EB%A6%AC%ED%8F%AC%ED%8A%B8ltv-%EB%98%90%EB%8A%94-%EC%95%A1%ED%8B%B0%EB%B9%84%ED%8B%B0 compare-data-between-different-dashboards-and-reports=%EB%8B%A4%EC%96%91%ED%95%9C-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C%EC%99%80-%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EA%B0%84%EC%9D%98-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B9%84%EA%B5%90 h_01J5WKA06A7XYFN07V60VQ4FY5=%EB%8B%A4%EC%96%91%ED%95%9C-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C%EC%99%80-%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EA%B0%84%EC%9D%98-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B9%84%EA%B5%90 h_01J5WHVQSNEA2WK83RBRDM1GT3=compare-ltv-and-activity-data-in-appsflyer retrieving-ltv-data-out-of-raw-activity-data=%EC%95%A1%ED%8B%B0%EB%B9%84%ED%8B%B0-%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0%EC%97%90%EC%84%9C-ltv-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%A5%BC-%EC%B6%94%EC%B6%9C%ED%95%98%EB%A0%A4%EB%A9%B4 h_01HKA0R42Z3ZSMEM7T5F0V3VM7=%EC%95%A1%ED%8B%B0%EB%B9%84%ED%8B%B0-%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0%EC%97%90%EC%84%9C-ltv-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%A5%BC-%EC%B6%94%EC%B6%9C%ED%95%98%EB%A0%A4%EB%A9%B4 retrieving-activity-data-out-of-ltv-data=ltv-%EB%8D%B0%EC%9D%B4%ED%84%B0%EC%97%90%EC%84%9C-%EC%95%A1%ED%8B%B0%EB%B9%84%ED%8B%B0-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%A5%BC-%EC%B6%94%EC%B6%9C%ED%95%98%EB%A0%A4%EB%A9%B4 h_01HKA0R42ZHFM4RHG78GE51XK3=ltv-%EB%8D%B0%EC%9D%B4%ED%84%B0%EC%97%90%EC%84%9C-%EC%95%A1%ED%8B%B0%EB%B9%84%ED%8B%B0-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%A5%BC-%EC%B6%94%EC%B6%9C%ED%95%98%EB%A0%A4%EB%A9%B4 h_01J5WK0AEN2N6J4P06CC3DMWPJ=compare-different-appsflyer-aggregated-data-dashboards-and-reports h_01J5WHVQSNZW66CQ4VGQGAKZB1=compare-appsflyer-data-with-external-data" />
