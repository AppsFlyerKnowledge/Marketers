---
title: 데이터 한도 초과 및 수량 한계 소개
metadata:
  keywords:
    - performance reports
    - Advertisers
    - exceeded
    - reports
    - faq
    - Agencies
    - Exceeded_Events_Limit
    - Exceeded Events Limit
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
  created_at: '2017-10-08T15:20:55Z'
  edited_at: '2026-10-14T10:34:55Z'
  id: 115005099063
  locale: ko
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/ko/articles/115005099063
---
> **한눈에 보기:** 특정 집약 데이터 기준이 *초과*로 표시되는 이유와 수량 한계에 도달하지 않기 위한 방법.

<div id="what-are-exceeded-dimensions" />

## 데이터 한도 초과란 무엇인가요?

앱스플라이어는 귀사의 인스톨 및 이벤트 데이터를 수집하여 집약합니다. 데이터는 각 데이터 기준에서 고유값으로 집약됩니다. 데이터 차원에서 고유값의 개수를 카디널리티(데이트 그룹별 수량)라고 부릅니다. 대부분의 분석 및 집약 리포팅 도구는 차원별로 카디널리티(데이트 그룹별 수량) 한계가 있습니다. 하나의 차원에서 고유값의 수가 수량 한계를 초과하면, 그 초과하는 데이터는 *초과* 그룹으로 분류됩니다. 미디어 소스 차원의 고유값 수가 수량 한계를 초과할 경우, 그 남은 미디어 소스 데이터 **및 그에 기반한 모든 차원의 데이터도** *초과* 그룹으로 분류됩니다.

다음 예시들은 데이터 한계 수량이 귀사의 리포트에 어떤 영향을 미치는지 보여줍니다.

<div id="example" />

> 📄 **예시**
>
> **예제 A: 캠페인 ID의 수량 한계**
>
> 캠페인 ID의 수량 한계는 3000입니다. 어떤 날에 보고된 캠페인 ID 수가 3000개를 넘어가면, 초과하는 캠페인 ID들은 Exceeded\_CampaignID\_Limit 그룹으로 묶입니다.
>
> **예제 B: 이벤트의 수량 제한**
>
> * 이벤트 수량 한계를 3이라고 가정하겠습니다.
> * 어떤 날에 7개의 고유 이벤트가 리포트됩니다: A, B, C, D, E, F, G. 즉, 이벤트 수량은 7입니다.
> * 집약 리포트에서 이벤트 A, B, C는 개별적으로 나열됩니다. 이벤트 D, E, F, G는 Exceeded\_Events\_Limit 그룹에 묶입니다.

초과된 차원과 량 한계는 집약 데이터에 다음과 같은 영향을 미칩니다:

* 개요 대시보드
* 집약 데이터 내보내기 및 Pull API 리포트
* 마스터 API 리포트
* 액티비티 및 커스텀 대시보드에서의 클릭과 노출 데이터
* Protect360 대시보드

로데이터는 카디널리티(데이트 그룹별 수량) 한계의 영향을 받지 않습니다.

귀하의 데이터가 상당 부분 *초과* 그룹에 포함된 경우, 그 데이터는 세분화되지 않습니다. 이는 분석 리포트에서 부정확한 결과로 이어질 수 있습니다. 필요하다면, 카디널리티(데이트 그룹별 수량) 한계 없이 그룹을 만들기 위해 로데이터를 활용하세요.

다음 표에서는 앱 당, 일별로 카디널리티(데이트 그룹별 수량) 한계를 나열합니다.

<table><tbody><tr><th>디멘션</th><th>그룹 이름 초과</th><th>...당 제한 유형</th><th>일일 데이터 수량 제한 </th><th>Protect360의 일일 데이터 수량</th></tr><tr><td>Ad</td><td>광고 한도 초과</td><td>미디어 소스</td><td>1000</td><td>-</td></tr><tr><td>광고 ID</td><td>Exceeded_AdID_Limit</td><td>미디어 소스</td><td>1000</td><td>-</td></tr><tr><td>광고세트</td><td>Exceeded_AdSet_Limit</td><td>미디어 소스</td><td>1000</td><td>-</td></tr><tr><td>광고세트 ID</td><td>Exceeded_AdSetID_Limit</td><td>미디어 소스</td><td>1000</td><td>-</td></tr><tr><td>캠페인</td><td>캠페인 한도 초과</td><td>미디어 소스</td><td>3000</td><td><ul><li>인스톨/인앱 이벤트: 3000</li><li>노출/클릭: 100 </li></ul></td></tr><tr><td>캠페인 ID</td><td>Exceeded_CampaignID_Limit</td><td>미디어 소스</td><td>3000</td><td><ul><li>인스톨/인앱 이벤트: 3000</li><li>노출/클릭: 100 </li></ul></td></tr><tr><td>채널</td><td>Exceeded_Channels_Limit</td><td>미디어 소스</td><td>200억</td><td>200억</td></tr><tr><td>사이트 ID</td><td>Exceeded_SiteID_Limit</td><td>미디어 소스</td><td>1000\*\*</td><td><ul><li> 1000\*\*</li></ul></td></tr><tr><td>이벤트</td><td>Exceeded_Events_Limit</td><td>앱 </td><td>300</td><td>인스톨/인앱 이벤트: 300</td></tr><tr><td>키워드</td><td>키워드 한도 초과</td><td>미디어 소스</td><td>1000</td><td>-</td></tr><tr><td>미디어 소스 이름\*</td><td>Exceeded_MediaSource_Limit</td><td>앱</td><td>1000</td><td><ul><li>인스톨/인앱 이벤트: 1000</li><li>노출/클릭: 100 </li></ul></td></tr><tr><td colspan="5"><p>\* <span>미디어 소스 차원에서 고유 값이 수량 제한을 넘어서는 경우, 초과하는 미디어 소스 데이터<span> 및 </span><strong>그 초과 미디어 소스를 기반으로 하는 모든 차원의 데이터</strong><span>는 </span><em>초과 그룹</em><span>으로 분류됩니다.</span></span></p></td></tr></tbody></table>

<div id="cardinality-limits-per-dimension" />

## 차원별 카디널리티( 제한

<div id="exceeded_adset_limit-and-exceeded_ad_limit" />

<Accordion title="광고 세트 한도 초과 및 광고 한도 초과">

* 미디어 소스 당 최대 1000개의 광고 세트 이름과 1000개의 광고 이름을 보유할 수 있습니다.
  * 특정 날에는 1001번째 광고 세트 정보부터 **광고 세트 한도 초과** 소스로 그룹화됩니다. **광고 한도 초과** 소스에도 같은 원칙이 적용됩니다.

<div id="tip" />

> 👍 **팁**
>
> "나누어 정복" 전략을 다시 활용합니다. 일반적인 광고 세트 이름을 소수로 정하고(최대 50개가 이상적), 모든 이전 광고 세트 이름을 단일 광고로 할당하세요. 앱스플라이어 어트리뷰션 링크에 **af\_sub** 파라미터를 사용하는 것도 가능합니다. 웹사이트 어트리뷰션으로 다음과 같은 일을 할 수 있습니다.
> 1. **광고 세트 한도 초과** 나 **광고 한도 초과**를 방지하세요.
> 2. 중요 광고 세트 및 광고 트래픽을 중심으로 효율적으로 최적화하세요.
> 3. 로데이터에 있는 광고 세트 및 광고 이름을 기준으로 심도 있는 분석을 수행하세요.

</Accordion>

<div id="exceeded_adsetid_limit-and-exceeded_adid_limit" />

<Accordion title="광고 세트 ID 한도 초과 및 광고 ID 한도 초과">

* 미디어 소스 당 최대 1000개의 고유 광고 세트 ID와 1000개의 고유 광고 ID를 사용할 수 있습니다.
  * 특정 날에는 1001번째 광고 세트 ID부터 **광고 세트 ID 한도 초과** 소스로 그룹화됩니다. **광고 ID 한도 초과** 소스에도 같은 원칙이 적용됩니다.

</Accordion>

<div id="exceeded_campaign_limit" />

<Accordion title="캠페인 한도 초과">

**[![](https://files.readme.io/6b96713b7a7ef6dc781fdd6d8b61507788bf79b452cfe2a3aa6fd80d7be71e0b-115016680246.png)](https://files.readme.io/6b96713b7a7ef6dc781fdd6d8b61507788bf79b452cfe2a3aa6fd80d7be71e0b-115016680246.png)**

* 하루에 최대 3000개의 고유 캠페인 이름을 사용할 수 있습니다.
  * 어떤 날에는 3001번째 캠페인 정보부터 **캠페인 한도 초과** 소스로 그룹화됩니다.

<div id="tip-1" />

> 👍 **팁**
>
> 소수의 일반적인 캠페인 이름을 정의하고(최대 300개 권장), 모든 이전 캠페인 이름을 광고 세트로 할당하세요. **af\_adset**는 앱스플라이어 어트리뷰션 링크 파라미터입니다. 웹사이트 어트리뷰션으로 다음과 같은 일을 할 수 있습니다.
> 1. **Exceeded\_Campaign\_Limit.이(가) 나타나지 않도록 방지합니다.** 2. 주요 광고 세트 트래픽을 기준으로 효과적으로 최적화하세요.
> 3. 로데이터에 담긴 캠페인 및 광고 세트 이름을 분석하여 심층적인 분석을 진행하세요.

</Accordion>

<div id="exceeded_campaignid_limit" />

<Accordion title="Exceeded_CampaignID_Limit">

* 하루 최대 3000개의 고유 캠페인 ID를 사용할 수 있습니다.
  * 하루 동안 3001번째 캠페인 ID부터 시작하는 모든 캠페인 정보는 **Exceeded\_CampaignID\_Limit** 소스에 속하게 됩니다.

</Accordion>

<div id="exceeded_channels_limit" />

<Accordion title="Exceeded_Channels_Limit">

* 하루에 미디어 소스마다 최대 20개의 고유 채널 이름을 사용할 수 있습니다. Protect360의 경우, 한도는 1000입니다.
  * 하루 동안 21번째 채널부터의 모든 채널 정보는 **Exceeded\_Channel\_Limit** 소스로 귀속됩니다.

</Accordion>

<div id="exceeded_events_limit" />

<Accordion title="Exceeded_Events_Limit">

* 하루에 최대 300개의 고유 이벤트 이름을 사용할 수 있습니다.
  * 하루 동안 301번째 이벤트부터의 모든 이벤트 정보는 **Exceeded\_Events\_Limit**라는 이름의 이벤트로 귀속됩니다.

<div id="tip-2" />

> 👍 **팁**
>
> **Exceeded\_Events\_Limit**을 보지 않기 위해 고려해볼 수 있는 것:
>
> * <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview">리치 인앱 이벤트</Anchor> 사용하기. 다양한 이벤트에 대해 리포팅하는 대신 몇 가지 일반적인 이벤트 이름을 정의하세요(이상적으로 20개 이내). 이벤트간 차이점을 나타내기 위해 동적 이벤트 값을 이용하세요. 이 방법은 값 파라미터에 따라 최적화하고, <Anchor target="_blank" href="/marketers/ko/docs/raw-data-reporting-overview">인앱 이벤트 로데이터 리포트.</Anchor>를 통해 이벤트 값들에 기반해 분석을 할 수 있게 합니다.
> * 앱스플라이어 플랫폼에서 필요하지 않은 인앱 이벤트를 제거하기 위한 <Anchor target="_blank" href="/marketers/ko/docs/implement-validation-rules-to-prevent-fraud">유효성 검증 규칙</Anchor>을 사용하세요.

<div id="example-1" />

> 📄 **예**
>
> 예를 들어, 귀하의 앱 com.greatapp은 판매하는 양말의 색상별로 구매 인앱 이벤트를 보냅니다, 예를 들면 buy\_red\_socks, buy\_blue\_socks, buy\_white\_socks 등과 같은. 다양한 이벤트의 확장을 방지하기 위해, 색상을 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview">이벤트 파라미터</Anchor>로 포함시킨 단일 이벤트 buy\_socks로 모든 것을 단순화하세요.

</Accordion>

<div id="exceeded_keywords_limit" />

<Accordion title="키워드 한도 초과">

* 하루에 미디어 소스별로 최대 1000개의 고유 키워드를 활용할 수 있습니다.
  * 하루 동안 1001번째 키워드 이상의 모든 키워드 정보는 **Exceeded\_Keywords\_Limit** 소스에 그룹화됩니다.

</Accordion>

<div id="exceeded_mediasource_limit" />

<Accordion title="Exceeded_MediaSource_Limit">

* 하루에 사용할 수 있는 미디어 소스별 고유 이름은 최대 1000개입니다.
  * 어느 날, 1001번째 이상의 미디어 소스 이름으로부터 얻은 캠페인 정보는 **Exceeded\_MediasSource\_Limit**소스로 묶여 처리됩니다.

</Accordion>

<div id="exceeded_siteid_limit" />

<Accordion title="Exceeded_SiteID_Limit">

* * 하루 동안, 미디어 소스별로 1001번째 사이트 ID부터의 정보는 **Exceeded\_SiteID\_Limit이라는 이름의 단일 사이트 ID로 분류됩니다.** 따라서, 만약 사이트 ID **Exceeded\_SiteID\_Limit**을 보게 된다면, 문제가 된 미디어 소스에 너무 많은 사이트 ID가 사용되어서 사이트 ID별로 트래픽을 최적화하는 것이 정확도와 효율성이 떨어진다는 의미입니다.

<div id="tip-3" />

> 👍 **팁**
>
> "분할 정복"을 실천하세요. 집계 데이터가 왜곡될 수 있는 미디어 소스 당 수천 개의 사이트 ID를 사용하는 대신, **af\_sub\_siteid**라고 불리는 두 번째 파라미터를 귀하의 어트리뷰션 링크에 사용해 보세요. 적은 수의 일반적인 사이트 ID(최적의 경우 최대 50개)를 정의하고, 그 아래에 이전의 모든 사이트 ID를 서브 사이트 ID로 분류하세요. 웹사이트 어트리뷰션으로 다음과 같은 일을 할 수 있습니다.
> 1. **Exceeded\_SiteID\_Limit을 보기 금지**
> 2. 중요한 사이트 ID 트래픽을 바탕으로 효과적으로 최적화하세요
> 3. 로데이터에 포함된 사이트 ID 및 서브 사이트 ID를 기반으로 심층 분석을 수행하세요

<div id="note" />

> 📘 **참고**
>
> 리텐션 리포트에서 Exceeded\_SiteID\_Limit는 표시되지 않지만 모든 사이트 ID가 표시되는 것은 아닙니다. 사이트 ID가 무작위로 표시되긴 하지만, 한도를 초과했을 때 모든 것을 표시할 수 있는 UI의 제한점이 있습니다. 이 문제를 해결하기 위해 마스터 API를 통해 리텐션 데이터를 가져오세요.

</Accordion>

<div id="how-to-avoid-getting-exceeded-sources" />

## 초과된 소스를 피하는 방법은 무엇일까요?

<div id="the-long-term-solution" />

### 장기적인 해결방안

대다수 광고주는 보통 수동으로 3000개의 캠페인을 정의하지 않기 때문에 **초과** 소스를 겪지 않을 것입니다.

만약 **초과** 소스를 겪게 된다면, 하나 이상의 미디어 소스가 캠페인, 사이트 ID, 광고 세트 또는 광고의 이름에 동적 값을 사용하고 있을 가능성이 큽니다. 앱 코드 내의 동적 인앱 이벤트로 인해 **Exceeded\_Events\_Limit** 소스 데이터가 나타날 수 있습니다.

<div id="tip-4" />

> 👍 **팁**
>
> 소스를 방지하기 위해 인앱 이벤트, 캠페인, 사이트 ID, 광고 세트 및 광고의 명칭에 정적 값만을 사용하세요.
>
> 또한 언급된 **초과** 소스에 대한 구체적인 조언을 확인하세요.

<div id="the-short-term-solution" />

### 단기적인 해결책

장기적인 해결책을 전부 시행하는 데는 며칠에서 몇 주가 소요될 수 있습니다.

하지만 지금 바로 당신의 데이터를 확인하고 싶다면 어떻게 해야 할까요?

설명한 바와 같이, 하루 동안 N+1 번째 클릭(또는 이벤트) 소스를 앱스플라이어가 수신할 때 **초과** 소스가 발생합니다. "**초과**" 소스의 데이터와 결합될 가능성이 있는 주목할만한 매체 소스를 사용하는 경우, 그런 매체들이 하루 중 늦은 시간에 도착할 수 있습니다. 보이는 **초과** 소스의 영향을 줄일 수 있는 간단한 방법이 있습니다:

<div id="tip-5" />

> 👍 **팁**
>
> 오늘의 데이터는 잠시 잊고 어제 및 그 이전 데이터만을 봅니다. 매일매일 데이터 집계 과정에서 전날 데이터를 재계산하고, **초과** 소스에 가장 작은(늦지 않은 소스가 아닌) 소스들만을 소급해 할당합니다. 이러한 방식은 클릭 과잉에 의해 발생할 수 있는 왜곡을 최소화할 수 있도록 도와줍니다!

<div data-zendesk-anchors="what-are-exceeded-dimensions=%EB%8D%B0%EC%9D%B4%ED%84%B0-%ED%95%9C%EB%8F%84-%EC%B4%88%EA%B3%BC%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80%EC%9A%94 h_01J1VY82KFVMRW99RK0SXWSEZ4=%EB%8D%B0%EC%9D%B4%ED%84%B0-%ED%95%9C%EB%8F%84-%EC%B4%88%EA%B3%BC%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80%EC%9A%94 h_01J1VY82KFXYA0XCA1XFVTJ2DZ=%EC%98%88%EC%8B%9C cardinality-limits-per-dimension=%EC%B0%A8%EC%9B%90%EB%B3%84-%EC%B9%B4%EB%94%94%EB%84%90%EB%A6%AC%ED%8B%B0-%EC%A0%9C%ED%95%9C h_01J1VY82KF5WP6PJQ1MKYPP7YY=%EC%B0%A8%EC%9B%90%EB%B3%84-%EC%B9%B4%EB%94%94%EB%84%90%EB%A6%AC%ED%8B%B0-%EC%A0%9C%ED%95%9C h_01J1VY82KF9XQ08EQ2BH89B6QK=exceeded_adset_limit-and-exceeded_ad_limit h_01J1VY82KFM4VAD4FG5CEKTQK6=%ED%8C%81 h_01J1VY82KFWMF6DN3XNFSWBFHH=exceeded_adsetid_limit-and-exceeded_adid_limit h_01J1VY82KFF7AWBCB54KRPJNS4=exceeded_campaign_limit h_01J1VY82KFBPK2PAHSSMCER6TW=%ED%8C%81-1 h_01J1VY82KF4TFVTGQ31RCE3QK7=exceeded_campaignid_limit h_01J1VY82KFXPX63XKKKTZ9AWN1=exceeded_channels_limit h_01J1VY82KFRDRVNEAG6S72Q1T4=exceeded_events_limit h_01J1VY82KFYXAXTJ613VAN1PXX=%ED%8C%81-2 h_01J1VY82KF48N1M8DZ89XQBJTD=%EC%98%88 h_01J1VY82KFAFK03F3SDJBA5ZNX=exceeded_keywords_limit h_01J1VY82KFV85460FCZB77EY1A=exceeded_mediasource_limit h_01J1VY82KFQG2ZGF91F80X2AAK=exceeded_siteid_limit h_01J1VY82KFMD2DJWDYXF8528CY=%ED%8C%81-3 h_01J1VY82KFQRVCAW82ZSNJ96G7=%EC%B0%B8%EA%B3%A0 how-to-avoid-getting-exceeded-sources=%EC%B4%88%EA%B3%BC%EB%90%9C-%EC%86%8C%EC%8A%A4%EB%A5%BC-%ED%94%BC%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95%EC%9D%80-%EB%AC%B4%EC%97%87%EC%9D%BC%EA%B9%8C%EC%9A%94 h_01J1VY82KFE9E2DNRNPBRQSW22=%EC%B4%88%EA%B3%BC%EB%90%9C-%EC%86%8C%EC%8A%A4%EB%A5%BC-%ED%94%BC%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95%EC%9D%80-%EB%AC%B4%EC%97%87%EC%9D%BC%EA%B9%8C%EC%9A%94 the-long-term-solution=%EC%9E%A5%EA%B8%B0%EC%A0%81%EC%9D%B8-%ED%95%B4%EA%B2%B0%EB%B0%A9%EC%95%88 h_01J1VY82KFDBASKPRK2GJ16FDZ=%EC%9E%A5%EA%B8%B0%EC%A0%81%EC%9D%B8-%ED%95%B4%EA%B2%B0%EB%B0%A9%EC%95%88 h_01J1VY82KFSWQ2Y4WSSASYDFWR=%ED%8C%81-4 the-short-term-solution=%EB%8B%A8%EA%B8%B0%EC%A0%81%EC%9D%B8-%ED%95%B4%EA%B2%B0%EC%B1%85 h_01J1VY82KFR7Z8422MYFK71ET8=%EB%8B%A8%EA%B8%B0%EC%A0%81%EC%9D%B8-%ED%95%B4%EA%B2%B0%EC%B1%85 h_01J1VY82KF83SADWJCESRNSJCJ=%ED%8C%81-5" />
