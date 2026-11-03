---
title: 인앱 이벤트 - 개요
metadata:
  keywords:
    - ios
    - Rich
    - In-App
    - android
    - Advertisers
    - In app events
    - Marketers
    - inapp events
    - attribution
    - inapp
    - inapp events attribution
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2017-11-02T08:12:51Z'
  edited_at: '2026-10-14T10:33:07Z'
  id: 115005544169
  locale: ko
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ko/articles/115005544169
---
> **한눈에 보기:** 매체 소스와 캠페인에 귀속된 인앱 이벤트(로그인, 등록, 인앱 구매 등)를 앱 설치 후 기록합니다.

## 인앱 이벤트를 기록해야 하는 이유

인앱 이벤트는 앱 내에서 무슨 일이 일어나고 있는지 인사이트를 제공하며, 앱 사용자 가치와 **다양한 매체 소스에서 발생하는 트래픽의 품질**을 판단하는 데 이상적인 도구입니다. 인앱 이벤트를 기록하면 ROI (투자수익률)나 LTV (유저생애가치) 같은 KPI를 측정하는 데 도움이 됩니다.

사용자가 등록, 튜토리얼 완료, 장바구니에 상품 추가, 구매 시 인앱 이벤트 데이터를 통해 해당 이벤트의 세부 정보를 기록할 수 있습니다. 모든 앱 설치 후 분석을 위해 인앱 이벤트 구현은 필수입니다.

## 인앱 이벤트에 대하여

인앱 이벤트는 이벤트 이름을 포함하며 필요시 이벤트 파라미터를 포함할 수 있습니다. 인앱 이벤트에 이벤트 파라미터를 추가하면, 그것은 인앱 이벤트라고 불립니다. 이벤트 파라미터는 이벤트 발생에 대한 자세한 컨텍스트와 정보를 제공합니다. 예를 들어, 사용자가 예약을 했다는 정보를 아는 것도 유용하지만, 이벤트 파라미터를 통해 구매 유형, 목적지 및 수익 등의 세부 사항을 알 수 있습니다.

![travel.png](https://files.readme.io/0ebe64e7aa3ccc40ef014c55ee3a91edf678e21b2d00a7f8be1298d6b494e925-30858351609617.png)

> 👍 **팁**
>
> 인앱 이벤트에 대해 더 알고 싶으신가요? 앱스플라이어 학습 포털에서 짧고 유익한 <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7774/play/18613/in-app-events-and-integrated-partners-part-1">코스를 확인해 보세요</Anchor>.

### 사전 정의된 사용자정의 이벤트

인앱 이벤트를 발송하려면 귀사의 앱에서 해당 코드의 구현이 필요합니다. 이벤트 이름과 파라미터는 다음과 같이 분류됩니다.

* **사전 정의된**: 이는 다양한 앱에서 일반적으로 사용되는 이벤트 이름 및 파라미터입니다. 다음과 같은 이유로 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#사전-정의된-이벤트-이름">사전 정의된 이벤트 이름</Anchor> 및 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#미리-정의된-event-parameter">이벤트 파라미터</Anchor>를 최대한 활용하는 것이 좋습니다.
  * 사전 정의된 네이밍 방식을 활용하면 파트너사로의 이벤트 매핑을 매끄럽게 처리할 수 있습니다.
  * 앱스플라이어가 이벤트나 이벤트 파라미터의 이름을 변경하더라도 귀사의 구현은 이전 버전과 호환됩니다.
* **커스텀:** 이는 귀사의 앱에서 발생하는 특정 사용자 시나리오에 대해 정의한 이벤트 이름과 파라미터입니다. 어떤 커스텀 이벤트 이름이나 파라미터 이름을 사용할 수 있지만, 커스텀 이벤트는 귀사의 개발자가 유지 보수해야 함을 명심하세요. [팁](/docs/in-app-events-overview#tips) 및 [제한 사항](/docs/in-app-events-overview#limitations)을 참조하세요.

## 인앱 이벤트 수익

이번 섹션에서는 앱스플라이어에 수익 이벤트를 보내는 방법과 이벤트가 포함하는 파라미터 매핑 방법을 알려드립니다. ROI360을 구독하시면 가장 정확하고 최신의 비용 및 수익 데이터(인앱 구매, 구독, 광고 수익 데이터 포함)를 받아보실 수 있으니 참고하시기 바랍니다. <Anchor target="_blank" href="/marketers/ko/docs/roi360-guide-cost-and-revenue-data">ROI360</Anchor>에 대해 자세히 알아보세요.

<div id="actual-revenue" />

<Accordion title="이벤트 수익">

`af_revenue` 이는 수익 리포팅 위한 기본 매개변수입니다. 송금된 수익`af_revenue` 앱스플라이어 제품 전반의 모든 수익 지표(대시보드, LTV, 코호트, ROAS, ROI)에 데이터를 제공하며, 파트너에게 전송되는 포스트백에도 포함됩니다. 항상 귀사의 비즈니스 로직에서 실제 수익 창출을 나타내는 인앱 이벤트와 함께 사용하세요.

앱 스토어 수수료 및 세금 공제 후 등 자체 로직을 적용하여 수익 리포트 하려면 추가로 제출할 수 있습니다.`af_net_revenue` . 이것은 추가 사항입니다.`af_revenue` 대체품이 아닙니다. 아래 [수익](#h_NETREVENUE0001) 참조하십시오.

* <Anchor target="_blank" href="/marketers/ko/docs/basic-sdk-integration-guide#record-revenue">SDK에서 수익 기록하기</Anchor>
* Unity에서 수익 기록하기

사용자가 구매를 취소하거나 환불을 처리하는 경우, 마이너스(-) 매출로 기록할 수도 있습니다. 마이너스 매출을 기록하려면, `af_revenue`에 전달하는 매출 값 앞에 마이너스 부호(-)를 추가하기만 하면 됩니다.

또한 거래 취소나 환불 등의 이벤트를 기록할 때에 **af\_revenue**가 마이너스 수익 값을 가질 수 있습니다.

수익 값에는 숫자(필요한 경우 소수점 포함)만 포함되어야 합니다.

* 다른 문자를 포함하거나 수익 가치의 형식을 다른 방식으로 지정하지 **마십시오** . 즉, 쉼표, 통화 기호 f(또는 예: $), 특수 문자 또는 텍스트가 없어야 합니다.
* 앱스플라이어 **최대 소수점 5자리까지 정확한** 수익 가치 제공합니다.
* 이 값의 범위는 달러 기준 또는 이에 상응하는 기존 통화 금액으로 -1,000,000에서 1,000,000 사이여야 합니다. 이 범위를 벗어난 값은 로데이터 리포트에 포함되지만 집약형 리포트에는 포함되지 않습니다.
* 예시: 1234.56
* 수익을 문자열로 보낼 때 따옴표 안의 값은 유효해야 합니다. 예를 들어: "1234.56".

**참고**:

* SDK에서 발송된 정확한 수익을 앱스플라이어가 표시합니다. 앱스플라이어로 전송되기 전에 SDK 단계에서 개발자가 포함하지 않는 한, VAT나 앱 스토어 커미션과 같은 기타 다른 계산은 포함되지 않습니다. 이러한 공제 후의 수익 리포트 하려면 추가로 제출해 주십시오.`af_net_revenue` ( [수익](/docs/in-app-events-overview#h_NETREVENUE0001) 참조).

**af\_currency는 af\_revenue(또는 af\_price)에 표기된 통화를 나타냅니다. 이벤트의 파라미터에서 af\_currency가 누락된 경우, 앱스플라이어는 기본값인 "USD"로 이를 전송합니다.**

**af\_price**는 ("장바구니 담기" 이벤트와 같이) 매출로 합산되지 않는 금전적 파라미터로 사용할 수 있습니다. 이 파라미터는 개별 항목의 가격을 의미합니다. 총 구매 금액은 af\_revenue 파라미터에 표시됩니다.

</Accordion>

<div id="h_NETREVENUE0001" />

<Accordion title="순 이익">

그만큼`af_net_revenue` 이 매개변수는 앱 스토어 수수료, 세금 공제, 총 마진 또는 서비스 수수료 차감 후 수익 과 같이 수익 금액에 자체 로직을 적용하려는 경우 수익 리포트 추가적인 선택적 방법을 제공합니다.

**af\_net\_revenue does not replace af\_revenue.** 계속 보내주세요`af_revenue` 평소처럼 추가하세요`af_net_revenue` 순 리포팅 원할 때 함께 사용하세요.

* 통화는 다음과 같습니다.`af_currency` (기본값 USD), 다음과 유사함`af_revenue` .
* SDK 에 미리 정의된 상수가 없으므로`af_net_revenue` 해당 키를 사용하여 사용자 커스텀 매개변수로 전송해야 합니다.`af_net_revenue` .
* 수익 <Anchor target="_blank" href="/marketers/ko/docs/my-dashboards#metrics">내 대시보드</Anchor> 의 순매출 지표( 수익, 순 ROI, 순ROAS, 순 ARPU 및 순총이익)를 뒷받침합니다.

> 📘 **참고**
>
> <Anchor target="_blank" href="/marketers/ko/docs/about-roi360-store-revenue">ROI360 앱 내 수익</Anchor> 사용하는 경우`af_net_revenue` 인앱 구매 및 구독 이벤트의 경우 자동으로 채워지므로 별도로 전송할 필요가 없습니다.`af_net_revenue` 해당 행사들을 위해서요. 수익 총 수익 에서 앱 스토어 수수료와 세금을 뺀 금액입니다.

</Accordion>

<div id="revenue-currency" />

<Accordion title="수익 통화">

앱스플라이어에서 통화 설정 및 통화 변환을 처리하는 방법을 이해하는 것이 중요합니다.

앱스플라이어는 통화 변환을 사용하여 앱 설정 통화와 인앱이벤트 통화 간의 차액을 처리합니다.

![revenue_normalization_flow.png](https://files.readme.io/f890d34168f92202c94da4bfa548bd0f471c98dec9c8d4282b2549f5878e9321-46334674326033.png)

위의 다이어그램은 다음의 과정을 보여줍니다:

1. 인앱 이벤트가 발송됩니다. 각 이벤트마다 서로 다른 통화가 사용됩니다.
2. 앱스플라이어는 모든 통화를 USD로 전환합니다.
3. 앱스플라이어가 수익 데이터를 처리합니다.
4. 대시보드의 수익 데이터는 앱 설정 통화로 표시됩니다
5. 앱스플라이어는 로데이터 리포트의 수익 데이터를 이벤트 통화 및 앱 설정 통화 모두로 채웁니다

앱스플라이어는 <Anchor target="_blank" href="https://openexchangerates.org/">공개 환율</Anchor>을 사용하여 통화를 변환합니다. 환율은 매 시간 업데이트됩니다. 앱스플라이어는 통화 변환을 수행할 때마다 마지막 시간의 업데이트 환율을 사용합니다.

#### 통화 전환

> 📄 **예시**
>
> 귀사의 앱 설정에서 통화를 GBP로 설정합니다. 프랑스의 사용자가 앱을 사용하여 제품을 구매합니다. 가격은 EUR(€)로 표시됩니다. 앱스플라이어에 보내는 인앱이벤트는 다음과 같습니다.
>
> ```java
> Map<String, Object> eventValue = new HashMap<String, Object>();
> eventValue.put(AFInAppEventParameterName.REVENUE,200);
> eventValue.put(AFInAppEventParameterName.CONTENT_TYPE,"category_a");
> eventValue.put(AFInAppEventParameterName.CONTENT_ID,"1234567");
> eventValue.put(AFInAppEventParameterName.CURRENCY,"EUR");
> AppsFlyerLib.getInstance().trackEvent(getApplicationContext() , AFInAppEventType.PURCHASE , eventValue);
> ```
>
> 이 경우 앱스플라이어는 수익을 먼저 EUR에서 USD로 변환한 다음 GBP로 변환합니다. 환율이 €1 = $1.13이라고 가정해 보겠습니다. 그러면 €200는 $226.85가 됩니다. 다음으로 앱스플랄이어는 USD에서 GBP로 변환합니다. 환율이 $1 = £0.78이라고 가정해 보겠습니다. 그러면 $226.85는 £176.92가 됩니다.

#### 통화 표시

<Anchor target="_blank" href="/marketers/ko/docs/app-settings#localization-currency">통화는 앱 설정에서 설정됩니다</Anchor>. 앱 설정에서 설정한 통화가 대시보드에 표시되는 통화입니다. 인앱이벤트를 보내는 통화에 관계없이 대시보드의 수익은 항상 앱 설정에서 설정한 통화로 표시됩니다.

> 📄 **예시**
>
> 앱 설정에 설정된 통화와 다른 통화로, 또는 통화가 전혀 없는 인앱이벤트를 보낸다고 가정해 보겠습니다. 이 예에서는 앱 설정의 통화가 **GBP**로 설정되어 있습니다.
>
> 앱스플라이어에 인앱 이벤트를 3개 발송합니다.
>
> 1. 이벤트 A의 수익은 **234**이고 통화는 **GBP**입니다.
> 2. 이벤트 B의 수익은 **171**이고 통화는 **EUR**입니다.
> 3. 이벤트 C의 수익은 **171**이고 지정된 **통화는 없습니다**.
>
> #### 대시보드의 수익 데이터
>
> 대시보드에 표시되는 수익은 인앱이벤트 통화에서 USD로 변환된 다음 앱 설정 통화로 변**환된 값**입니다.
>
> 이벤트에 통화가 지정되지 않은 경우 **앱스플라이어는 기본적으로 USD를 사용합니다**. 대시보드에는 이벤트 및 수익이 다음과 같이 표시됩니다.
>
>
>
> | 인앱 이벤트 | 고유 사용자 | 동작 수 | 수익 |
> | --- | --- | --- | --- |
> | A | 1 | 1 | 234파운드 |
> | B | 1 | 1 | 149.4파운드 - EUR에서 USD로, 그다음 GBP로 변환됐습니다. |
> | C | 1 | 1 | £132.9 - 지정된 통화가 없으므로 기본값은 USD입니다. USD에서 GBP로 직접 변환됩니다. |
>
>
>
> #### 로우 데이터 리포트의 수익 데이터
>
> 앱 설정에서 통화를 **GBP**로 설정했지만 인앱이벤트를 다른 통화로 보내는 경우 로데이터 리포트에는 수익이 앱 설정 통화와 인앱이벤트 통화 모두로 표시됩니다.
>
> 앱 설정에서 통화를 **GBP**로 설정했지만 통화 없이 인앱이벤트를 전송하는 경우 로데이터 리포트에 수익이 앱 설정 통화와 USD로 모두 표시됩니다.
>
> 인앱이벤트 로데이터 리포트에는 이벤트 및 수익이 다음과 같이 표시됩니다.
>
>
>
> | 이벤트 | 이벤트 수익 | 이벤트 수익 통화 | 이벤트 수익 GBP |
> | --- | --- | --- | --- |
> | A | 234 | GBP | 234 |
> | B | 171 | EUR로 책정됩니다. | 149.4 - EUR에서 USD로 변환한 후 GBP로 변환됨. |
> | C | 171 | USD | 통화가 지정되지 않아 기본적으로 USD로 설정된 132.9 USD에서 GBP로 직접 변환됩니다. |

</Accordion>

## 이벤트 발송

앱스플라이어에 인앱 이벤트를 발송하는 방법은 여러 가지가 있습니다.

* <Anchor target="_blank" href="/marketers/ko/docs/sdk-integration-overview">**앱스플라이어 SDK:**</Anchor> 이것이 이벤트를 발송하는 가장 일반적인 방법입니다. SDK 수준에서 앱스플라이어 인앱 이벤트 API를 사용하여 앱 내의 사용자 동작을 기록하는 인앱 이벤트를 발송할 수 있습니다.
* <Anchor target="_blank" href="/marketers/ko/docs/server-to-server-events-api-for-mobile-s2s-mobile">**서버-투-서버 API:**</Anchor> 서버-투-서버 API를 사용하여 모바일 앱 외부에서 발생하는 이벤트를 앱스플라이어로 직접 발송합니다. 예를 들어, 웹과 모바일 인터페이스를 모두 사용하는 유저가 있는 경우 두 소스의 이벤트를 기록하여 앱스플라이어에서 동일한 유저로 연결할 수 있습니다. 인앱 이벤트일 수도 있고, 웹사이트 이벤트, 콜센터 이벤트 또는 귀사의 매장에서의 구매와 같은 다른 이벤트일 수도 있습니다.
* <Anchor target="_blank" href="/marketers/ko/docs/purchase-and-subscription-validation-overview">**영수증 검증**</Anchor>: 이는 결제 플랫폼(예: Apple, Google)이 인앱 구매가 보고된 대로 이루어졌는지 확인하는 보안 메커니즘입니다. 구매 유효성 검증은 사기성 수익 이벤트를 방지하는 주요 도구입니다. 이를 통해 실제 수익을 확인할 수 있으며, 미완료된 인앱 구매를 걸러냅니다.
* <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-for-hybrid-apps">**하이브리드 앱:**</Anchor> 이러한 앱은 기본적 뷰와 HTML 콘텐츠를 결합하며 인앱 이벤트를 기록할 수 있습니다. 하지만 SDK는 네이티브 측에서만 이벤트를 발송할 수 있으므로 개발자는 모든 이벤트 데이터를 네이티브 코드로 전달해야 합니다.

## 인앱 이벤트 설정

인앱 이벤트를 설정하기 위해서는 마케터와 개발자가 다음과 같이 협력해야 합니다.

| 단계 | 역할 | 작업 | 세부 정보 |
| --- | --- | --- | --- |
| 1 | 마케터 | 측정하고자 하는 인앱 이벤트를 판단하다. 귀사의 개발자에게 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#사전-정의된-이벤트-이름">이벤트 이름</Anchor>과 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#미리-정의된-event-parameter">이벤트 파라미터</Anchor>를 [정의](/docs/in-app-events-overview#defining-an-inapp-event)하고 전달하세요. | 사용자 품질을 측정하기 위한 KPI로 사용할 수 있는 3&#126;5개의 이벤트(예: 구매, 등록, 공유)부터 시작하는 것이 좋습니다. 이벤트 파라미터는 선택 사항이며, 모든 이벤트 이름과 함께 사용할 수 있습니다.<br /><br />일반적인 인앱 이벤트에 대해서는 [비즈니스 업종별, 앱 카테고리별 추천 이벤트](/docs/in-app-events-overview#recommended-events-by-business-vertical)를 참조하세요. |
| 2 | 개발자 | 해당 사항에서는 귀사의 앱에 코드를 구현하세요. | 개발자 문서는 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk">여기</Anchor>에서 확인할 수 있습니다. |
| 3 [선택사항] | 마케터 | 개발자와 협력하여 <Anchor target="_blank" href="/marketers/ko/docs/customer-user-id-field-cuid">고객 유저 ID 필드(CUID)</Anchor>를 설정하세요. | 이 필드는 CUID를 키로 사용하여 앱스플라이어 어트리뷰션 데이터와 귀사의 다른 데이터를 교차 참조하여 인앱 이벤트 데이터를 풍부하게 만듭니다. |
| 4 [선택사항] | 마케터 | 대시보드에서 관련 파트너에 <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#이벤트-매핑">이벤트를 매핑</Anchor>하세요. | 이는 연동하는 파트너에 따라 지속적인 작업입니다. |

<div id="defining-an-inapp-event" />

<Accordion title="인앱 이벤트 정의">

측정할 인앱 이벤트를 판단한 후, <Anchor target="_blank" href="https://evgen.appsflyer.com/">인앱 이벤트 생성기</Anchor>를 사용하여 다음과 같이 이벤트와 파라미터를 정의하세요:

1. 기록하려는 시나리오에 가장 적합한 이벤트 이름을 선택하세요.
2. 이벤트와 연관시킬 이벤트 파라미터를 선택하세요. 이벤트에 추가 정보를 제공하고 데이터를 풍부하게 할 파라미터를 선택하세요.
3. 인앱 이벤트 생성기에서 완료된 파일을 다운로드하여 개발자와 공유하세요.

> 📄 **예시**
>
> 이커머스 앱의 마케터는 사용자들이 보는 콘텐츠 유형을 기록하여 어떤 카테고리가 가장 인기 있는지 더 잘 이해하고, 제품 조회와 판매를 연결하려고 합니다.
>
> 다음 표는 마케터가 개발자에게 전달하는 이벤트 구조의 예를 보여줍니다.
>
>
>
> <table><thead><tr><th>이벤트 이름</th><th>이벤트 파라미터</th><th>파라미터 값</th><th>이벤트는 언제 시작되나요?</th></tr></thead><tbody><tr><td rowspan="3">af_content_view</td><td>af_가격</td><td>제품 가격</td><td rowspan="3"><span>유저가 특정 제품 세부 정보 페이지를 볼 때</span></td></tr><tr><td><span>af_content_type</span></td><td><span>제품 카테고리 이름(예: 신발)</span></td></tr><tr><td><span>af_content_id</span></td><td><span>제품 ID(예: SKU)</span></td></tr></tbody></table>

</Accordion>

<div id="recommended-events-by-business-vertical" />

<Accordion title="업종별, 앱 카테고리별 추천 이벤트">

다음 표는 업종별, 앱 카테고리별로 기록하기를 제안하는 일반적인 인앱 이벤트의 예와 흐름을 포함한 문서 링크를 제공합니다.

| 업종별, 앱 카테고리별 | 문서 제목 |
| --- | --- |
| <Image alt="InApp_Events_games.png" src="https://files.readme.io/ee2d46ddf11a6a6cacc95399ffd778d6613ecdd905d237cd971073e095cada5b-20659444711953.png" width="38px" /> | <Anchor target="_blank" href="/marketers/ko/docs/recommended-gaming-app-events">추천 게임 앱 이벤트</Anchor> |
| <Image alt="InApp_Events_ecommerce.png" src="https://files.readme.io/c6497d250c22c7de5c13f01278ac72d8b3117bc60712ba3fe40ad24efcdc4947-360019350097.png" width="37px" /> | <Anchor target="_blank" href="/marketers/ko/docs/recommended-ecommerce-app-events">추천 이커머스 앱 이벤트</Anchor> |
| <Image alt="InApp_Events_streaming.png" src="https://files.readme.io/27f2f38b0ce7d242580c60edeff730079a3801f98ff0d7cb8a605380ed11071f-20659453813905.png" width="39px" /> | <Anchor target="_blank" href="/marketers/ko/docs/recommended-entertainment-app-events">추천 엔터테인먼트 앱 이벤트</Anchor> |
| <Image alt="banking.png" src="https://files.readme.io/260638f807a43f42c6ff99bb72b8d4113b2df09436b9322a820888ad3f8a01ae-20659476893969.png" width="36px" /> | <Anchor target="_blank" href="/marketers/ko/docs/recommended-finance-and-banking-app-events">추천 금융 및 뱅킹 앱 이벤트</Anchor> |
| <Image alt="InApp_Events_lending.png" src="https://files.readme.io/e3465ee913a65a215f1c224db20d4f1fd61fd0bf488b798073c94b4e8387d252-20659507679889.png" width="36px" /> | <Anchor target="_blank" href="/marketers/ko/docs/recommended-p2p-lending-app-events">추천 P2P 대출 앱 이벤트</Anchor> |
| <Image alt="education.png" src="https://files.readme.io/fb036c8f3b0cb4cc06a5284c26089bbb361273ab628bc5b740692bc49e7a2c40-20659493109393.png" width="37px" /> | <Anchor target="_blank" href="/marketers/ko/docs/recommended-online-education-app-events">추천 온라인 교육 앱 이벤트</Anchor> |
| <Image alt="InApp_Events_ride.png" src="https://files.readme.io/3901cfcc0cc821cc9c93edbe806bc2d570698be366b76b3710cb60e9aa190d91-20659532208401.png" width="37px" /> | <Anchor target="_blank" href="/marketers/ko/docs/recommended-ride-hailing-app-events">추천 승차 호출 앱 이벤트</Anchor> |
| <Image alt="InApp_Events_flight.png" src="https://files.readme.io/7a09c4a641dd5e797bffc41a6e66b20efe5660721f37abac3dd12ac83688b37b-20659533911697.png" width="38px" /> | <Anchor target="_blank" href="/marketers/ko/docs/recommended-flight-booking-app-events">추천 항공편 예약 앱 이벤트</Anchor> |
| <Image alt="InApp_Events_hotel.png" src="https://files.readme.io/ffc23cc65b6b6cfe99c12e988cca3df6667058b7e3a672db3639472a17602546-20659548553745.png" width="37px" /> | <Anchor target="_blank" href="/marketers/ko/docs/recommended-hotel-booking-app-events">추천 호텔 예약 앱 이벤트</Anchor> |
| <Image alt="5669_Healthcare_icon_3.png" src="https://files.readme.io/bb4bb46d842d1f2d08da548724e7d69910b0a050302fcdbd1500a8ebef325516-20659200427281.png" width="37px" /> | <Anchor target="_blank" href="/marketers/ko/docs/recommended-healthcare-app-events">추천 헬스케어 앱 이벤트</Anchor> |
| <Image alt="telecommunications_icon.png" src="https://files.readme.io/42f1aac3b825957d9d0584d83480c441b9d53665cc6cf1a6b8cd1803bb9b6121-20659194885393.png" width="39px" /> | <Anchor target="_blank" href="/marketers/ko/docs/recommended-telecommunication-app-events">추천 통신 앱 이벤트</Anchor> |
| <Image alt="InApp_Events_eWallet.png" src="https://files.readme.io/4d2ed4994bbe8e8eca7009b8ec8f5dbf22a626421a7a1efb213ddb4a12c7b487-4402543191825.png" width="39px" /> | <Anchor target="_blank" href="/marketers/ko/docs/recommended-ewallet-app-events">추천 eWallet 앱 이벤트</Anchor> |
| <Image alt="soccer_ball.png" src="https://files.readme.io/2c5150b2c50ec166878cd976154dc81c0dc8a1e710fa8869aa582b535313b464-4413968925585.png" width="39px" /> | <Anchor target="_blank" href="/marketers/ko/docs/recommended-sports-betting-events">추천 스포츠 베팅 이벤트</Anchor> |

</Accordion>

<div id="view-inapp-event-data" />

<Accordion title="인앱 이벤트 데이터 보기">

인앱 이벤트는 유저의 생애동안 인스톨한 미디어 소스에 속합니다. 이벤트 데이터는 <Anchor target="_blank" href="/marketers/ko/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">유저 생애 가치 (LTV) 또는 액티비티 데이터</Anchor>로 표시됩니다.

다음 장소에서 귀사의 인앱 이벤트 데이터를 확인할 수 있습니다.

* 대시보드 개요 페이지: 실시간 유저 생애 가치 (LTV) 유저 유입 (UA) 성과가 표시됩니다. **참고**: 여기에는 인앱 이벤트를 통해 보고된 오가닉 및 논오가닉 사용자 간에 나뉜 수익과 <Anchor target="_blank" href="/marketers/ko/docs/resolve-retargeting-double-attribution">이중 어트리뷰션</Anchor>이 적용된 리타겟팅 수익이 포함됩니다.
* 이벤트 페이지: 매체 소스 전반의 LTV 인앱 이벤트 성과를 보여줍니다.
* <Anchor target="_blank" href="/marketers/ko/docs/activity-dashboard">활동 페이지:</Anchor> 선택한 기간 동안의 인앱 액티비티를 보여줍니다.
* <Anchor target="_blank" href="/marketers/ko/docs/raw-data-reporting-overview">로데이터 인앱 이벤트 리포트:</Anchor> 유저 전체의 활동을 연대순으로 나열한 목록입니다. 이 리포트에는 예시로 이벤트 파라미터 값이 포함됩니다.

  ```json
  {
    "af_level":"10",
    "af_score":"3387",
    "arena":"7",
    "char_type":"paladin"
  }
  ```

  로데이터 리포팅은 프리미엄 기능입니다.

> 📘 **참고**
>
> 인앱 이벤트 파라미터 값은 <Anchor target="_blank" href="/marketers/ko/docs/raw-data-reporting-overview#인앱-이벤트">로데이터 인앱 이벤트 리포트</Anchor>에서만 확인 가능합니다. 개요, 이벤트, 액티비티 대시보드 및 통합 데이터 리포트에서는 확인이 어렵습니다.

</Accordion>

<div id="tips" />

<Accordion title="팁">

앱에서 이벤트 이름과 파라미터를 정의할 때 다음 사항에 유의하세요.

* 로데이터 리포팅의 데이터 일관성을 위해 모든 플랫폼에서 동일한 인앱 이벤트 이름과 구조를 정의하고 사용하실 것을 권장합니다.
* 다양한 소스에서 오는 사용자 품질을 쉽게 비교할 수 있도록 최소한의 이벤트만 사용하세요.
* **사용자 정보 보호를 보장하는 것이 중요합니다.** **인앱 이벤트 값을 직접 식별할 수 있는 제한된 데이터로 채우지 마세요.** **예를 들어, 이메일 주소, 이름, 주민등록번호, 또는 일부 지역의 우편번호입니다. 제한된 데이터에 대한 자세한 정보는** <Anchor target="_blank" href="https://www.appsflyer.com/legal/services-privacy-policy/">**서비스 개인정보 보호정책**</Anchor>**을 참조하세요.**
* 앱스플라이어는 <Anchor target="_blank" href="https://www.appsflyer.com/services-privacy-policy/#engagementinformation">참여</Anchor> 시 기기의 IP 주소를 포함합니다. 일부 관할권이나 사용 시나리오에서는 IP 주소가 PII로 간주될 수 있습니다. 광범위한 지리적 위치(도시, 지구 수준)를 알아내기 위하여 IP 주소를 사용하며, 특정 주소는 사용하지 않습니다. 필요한 경우, <Anchor target="_blank" href="/marketers/ko/docs/apply-ip-masking-to-user-data">IP 주소를 마스킹</Anchor>하여 로데이터 리포트에 나타나지 않도록 선택할 수 있습니다.
* 인앱 이벤트는 앱스플라이어의 유일한 수익 데이터 소스입니다. 각 이벤트에 특정 수익 값을 첨부하고 이를 귀사의 앱 대시보드에서 볼 수 있습니다. [수익화 파라미터](/docs/in-app-events-overview#revenue-events)에 대해 더 알아보세요. [![revenue_data.png](https://files.readme.io/9ada01568583ef5eb7d39ca09b2ae9dd68afb9415859574f35c477cf46d6272c-46334666577425.png)](/docs/in-app-events-overview#revenue-events)

</Accordion>

<div id="limitations" />

<Accordion title="제한 사항">

앱에서 이벤트 이름과 파라미터를 정의할 때 다음 사항에 유의하세요.

* 인앱 이벤트 이름에 소문자 영숫자(a-z 및 0-9)만을 사용하는 것이 권장됩니다. 이벤트 이름은 대소문자를 구분합니다. 즉, af\_purchase와 af\_PURCHASE는 로데이터에서 두 개의 다른 이벤트로 인식됩니다. 단, 통합 리포트와 대시보드(예: 개요 또는 이벤트)에서는 소문자만 허용되므로 동일한 이벤트로 표시됩니다.
* 하루 최대 300개의 고유 이벤트를 추적할 수 있습니다. <Anchor target="_blank" href="/marketers/ko/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_events_limit">더 보기</Anchor>
* 고유 사용자는 앱을 인스톨 후 처음 100개 이벤트에서만 계산됩니다.
* 이벤트 이름은 다음 문자열로 시작할 수 없습니다 : " = + -
* 이벤트 값에는 인코딩된 URL이나 <Anchor target="_blank" href="https://www.w3schools.com/tags/ref_urlencode.ASP">ASCII</Anchor>로 인코딩된 경우를 제외하고는 + 문자가 포함되어서는 안 됩니다.
* 이벤트 이름에는 빈 공간을 포함할 수 없습니다. 이벤트 이름 앞이나 뒤에 밑줄(낮은 대시)을 사용할 수 있습니다.
* 로데이터 리포트에서 값이 잘리는 것을 방지하려면 이벤트 값이 2,000자를 넘지 않아야 합니다. 그러나 SDK에서 발생한 이벤트라면 HTTP 요청으로 전송 시 페이로드가 잘리지 않도록 1,000자 이하로 유지하는 것이 좋습니다.
* 이벤트 값으로 참조 URL을 포함하는 경우 <Anchor target="_blank" href="https://www.w3schools.com/tags/ref_urlencode.ASP">URL 인코딩</Anchor>을 해야 합니다.
* Meta Ads에는 이벤트 이름과 파라미터에 대한 일부 제한이 있습니다. 제한 사항에 대한 내용은 <Anchor target="_blank" href="https://developers.facebook.com/docs/app-events/faq#limits">여기</Anchor>에서 읽어보세요.

</Accordion>

## 자주 묻는 질문

다음 섹션에는 인앱 이벤트에 대한 다양한 FAQ가 포함되어 있습니다.

<div id="how-do-i-use-the-revenue-parameter" />

<Accordion title="수익 파라미터는 어떻게 사용하나요?">

어떤 파라미터 이름과 이벤트와 함께 수익 값을 발송할 수 있습니다. 그러나 앱스플라이어 로데이터와 데이터 집약형 데이터에 수익 (포함 [음수 수익](/docs/in-app-events-overview#revenue-events) )을 등록하기 위해서는 반드시 ***af\_revenue*** 파라미터를 사용해야 합니다. 항상 귀사의 비즈니스 로직에서 실제 수익 창출을 나타내는 인앱 이벤트와 함께 사용하세요.

**af\_currency**는 **af\_revenue**(또는 **af\_price**)에 명시된 통화를 나타냅니다. 이벤트 파라미터에 **af\_currency**가 없을 경우 앱스플라이어는 이를 기본값인 "USD"와 함께 발송합니다. ***af\_revenue*** 파라미터에 대한 자세한 정보는 [수익 어트리뷰션 가이드](/docs/in-app-events-overview#revenue-events)를 참조하세요.

수수료 및 세금을 공제한 후, 자체적인 계산 방식을 적용하여 수익 리포트 하고 싶으시다면, 다음 양식을 보내주세요.`af_net_revenue` 커스텀 매개변수와 함께`af_revenue` .`af_net_revenue` 대체하지 않습니다`af_revenue` . 자세한 내용은 [수익](#h_NETREVENUE0001) 참조하십시오.

</Accordion>

<div id="how-does-appsflyer-attribute-events" />

<Accordion title="앱스플라이어가 이벤트를 어떻게 어트리뷰션하나요?">

인앱 이벤트는 앱 설치의 원래 미디어 소스에 어트리뷰션됩니다.

앱을 인스톨할 때 (첫 번째 앱 실행), 앱스플라이어는 다양한 <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-attribution-model#어트리뷰션-메서드">어트리뷰션 방법</Anchor>을 사용하여 인스톨의 어트리뷰션을 판단합니다. 동시에 앱스플라이어 SDK가 어트리뷰션 세부 정보와 연결된 새로운 고유한 <Anchor target="_blank" href="/marketers/ko/docs/about-device-identifiers#appsflyer-id">앱스플라이어 ID</Anchor>를 생성합니다.

앱 내 같은 디바이스에서 발생하는 모든 후속 인앱 이벤트에는 이 ID가 있습니다. 이를 통해 앱스플라이어는 이벤트를 원래 미디어 소스에 어트리뷰션할 수 있습니다. 광고주는 이를 사용하여 앱 내 유저 여정을 추적할 수 있습니다.

최근 리타겟팅된 사용자의 이벤트에는 <Anchor target="_blank" href="/marketers/ko/docs/resolve-retargeting-double-attribution">이중 어트리뷰션</Anchor>이 있을 수 있습니다.

앱스플라이어는 다음과 같은 경우 인스톨 이벤트를 **오가닉**으로 어트리뷰션합니다.

* 매체 소스의 약관에 [사용자 수준 데이터 삭제](/docs/in-app-events-overview#how-long-does-appsflyer-retain-userlevel-data-and-what-are-the-deletion-obligations)가 명시되어 있을 때
* 사용자가 디바이스에 저장된 앱 데이터를 삭제하면 새로운 앱스플라이어 ID가 생성됩니다.

</Accordion>

<div id="are-events-recorded-if-a-device-is-offline" />

<Accordion title="디바이스가 오프라인일 때도 이벤트가 기록되나요?">

사용자가 인터넷 연결이 없는 상태에서 이벤트를 시작하면 앱스플라이어는 여전히 이를 기록할 수 있습니다. 작동 방식은 다음과 같습니다:

1. SDK는 이벤트를 앱스플라이어 서버로 전송하고 성공적인 응답을 기다립니다.
2. SDK가 성공적인 응답을 받지 못하면 이벤트는 캐시에 저장됩니다.
3. 다음에 성공적인 응답이 오면 저장된 이벤트가 다시 서버로 전송됩니다.
4. 캐시에 여러 이벤트가 있을 경우, 이벤트는 순차적으로 서버로 전송됩니다.

> 📘 **참고**
>
> SDK 캐시는 최대 40개의 이벤트를 저장할 수 있으므로, 오프라인 상태에서 발생하는 이벤트 중 처음 40개만 저장됩니다. 이후에 이어지는 모든 내용은 다음 성공적인 응답 전까지 무시됩니다.
>
> 로우 데이터에 표시되는 이벤트 시간은 디바이스가 다시 온라인 상태가 된 후 앱스플라이어로 이벤트가 전송된 시간입니다. 이는 이벤트가 실제로 발생한 시간을 나타내는 것은 아닙니다.

</Accordion>

<div id="what-are-complex-inapp-events-and-how-do-i-set-them-up" />

<Accordion title="복잡한 인앱 이벤트란 무엇이며 어떻게 설정하나요?">

복합 인앱 이벤트를 사용하면 단 한 번의 API 호출로 여러 개의 항목을 전송할 수 있습니다. 이는 연관성이 높은 여러 사용자의 행동을 하나로 묶고자 할 때 유용하며, 예를 들어 단일 세션에서 여러 개의 상품을 장바구니에 담는 행위 등이 이에 해당합니다.

복합 인앱 이벤트를 구성하려면 `af_content`을(를) JSON 배열로 사용하세요. 배열의 각 객체에는 `id` 및 `quantity`이(가) 포함되어야 합니다. `af_content_list`은(는) 선택 사항이며 생략할 수 있습니다.

> 📄 **예시**
>
> ```json
> {
>   "af_revenue": 4.99,
>   "af_currency": "USD",
>   "af_order_id": "12345",
>   "af_content": "[{"id":"ID1","quantity":"1"},{"id":"ID2","quantity":"1"},{"id":"ID3","quantity":"2"}]"
> }
> ```

> 🚧 **중요!**
>
> `af_content` 문자열이 1,000자를 초과하면 앱스플라이어는 `fb_content` 매개변수 없이 Meta로 이벤트를 보낼 수 있습니다. 이 경우 `af_content_list`도 없으면 Meta는 제품 식별 데이터를 수신하지 못합니다. 많은 항목이 포함된 이벤트의 경우 `af_content`을(를) 1,000자 미만으로 유지하세요.

Meta로 복합 인앱 이벤트를 전송하는 방법에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/meta-ads-in-app-event-mapping#send-complex-in-app-events-to-meta-ads">Meta ads로 복합 인앱 이벤트 전송하기</Anchor> 가이드를 참조하세요.

**참고:** 앱스플라이어 <Anchor target="_blank" href="/marketers/ko/docs/audiences-guide#limitations">오디언스(Audiences)</Anchor>의 경우, 이벤트 속성값으로 배열은 허용되지 않으며 오직 숫자와 문자열 형태만 사용할 수 있습니다.

</Accordion>

<div id="can-i-add-multiple-items-to-a-single-transaction" />

<Accordion title="하나의 거래에 여러 품목을 추가할 수 있나요?">

하나의 거래에 여러 항목을 추가할 수 있습니다. 이벤트 파라미터당 단일 값을 사용하는 대신, 쉼표로 구분하여 거래를 설명하는 항목의 배열을 사용할 수 있습니다. 형식은 JSON 문자열이어야 합니다.

> 📄 **예시**
>
> 같은 거래에서 스미스 씨는 미국 온라인 매장에서 동일한 셔츠 두 개, 신발 한 켤레, 모자 하나를 구매했습니다. 포스트백에서 여러 항목이 배열 형태로 전달되므로, 각 항목이 나열되는 순서는 반드시 동일해야 합니다.
>
> ```json
> "{"af_content_id": ["123","988","399"], "af_quantity": ["2","1","1"], "af_price": ["25","50","10"], "af_revenue": "110", "af_currency": "USD"}"
> ```
>
> 여러 항목이 <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration">포스트백</Anchor>의 배열로 전송됩니다. 현재 Meta Ads와 X Ads는 배열 파라미터를 올바르게 구문 분석할 수 없습니다. 이 문제에 대처하기 위해, 앱스플라이어는 배열로 전송하는 대신 항목 수(af\_quantity)를 합산하여 알려줍니다. 예를 들어, Meta Ads는 **af\_quantity=4**를 받습니다.
>
> **<span id="h_01HDBZW9XFJ68WSM3066NVRATS"></span>참고 사항**
>
> * 앱스플라이어 <Anchor target="_blank" href="/marketers/ko/docs/audiences-guide#limitations">오디언스(Audiences)</Anchor>의 경우, 이벤트 속성값으로 배열은 허용되지 않으며 오직 숫자와 문자열 형태만 사용할 수 있습니다.
> * 다음 인앱 이벤트와 함께 여러 항목을 사용할 수 있습니다:
>   af\_add\_to\_cart, af\_add\_to\_wishlist, af\_tutorial\_completion, af\_initiated\_checkout, af\_purchase, af\_rate, af\_spent\_credits, af\_content\_view, af\_travel\_booking, af\_update



</Accordion>

<div id="how-does-appsflyer-handle-event-deduplication" />

<Accordion title="앱스플라이어는 이벤트 중복을 어떻게 처리하나요?">

인앱 이벤트 중복 제거 메커니즘이 있습니다. 모든 인앱 이벤트를 확인하여 10초 안에 동일한 appsflyer\_id에서 발생한 인앱 이벤트가 있는지 확인합니다. 이러한 이벤트가 발견되면, 중복을 제거합니다.

두 이벤트의 다음 필드가 동일한 경우, 두 이벤트는 동일한 것으로 간주됩니다.

* 이벤트 이름
* 이벤트 값
* 앱 ID
* 앱스플라이어 ID

> 📘 **참고**
>
> 중복 제거는 SDK에서 발송되는 인앱 이벤트에만 적용됩니다.
>
> S2S 인앱 이벤트는 중복 제거되지 않습니다.

</Accordion>

<div id="how-long-does-appsflyer-retain-userlevel-data-and-what-are-the-deletion-obligations" />

<Accordion title="앱스플라이어는 사용자 데이터를 얼마 동안 보관하며 삭제 의무가 있나요?">

앱스플라이어는 연동 유형 및 파트너 요구 사항에 따라 유저의 로데이터를 보관합니다. 통합 데이터는 최대 5년간 보존됩니다.

데이터 보관 기간은 미디어 소스와 전달 방법(예: 데이터 락커 또는 풀 API)에 따라 달라질 수 있으며, 법적, 계약적 또는 파트너 의무 사항에 따라 달라질 수 있습니다.

삭제 이후에는 삭제된 사용자와 관련된 이벤트가 오가닉으로 표시됩니다. 기존 집계 데이터는 변경되지 않습니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/user-level-data-retention#데이터-리텐션-및-삭제-의무">데이터 보관 및 삭제 의무</Anchor>를 참조하세요.

</Accordion>

<div id="do-i-need-to-add-the-os-operating-system-parameter-to-my-events" />

<Accordion title="이벤트에 OS(운영 체제) 매개변수를 추가해야 하나요?">

* 안드로이드 SDK와 iOS SDK는 자동으로 OS(운영 체제) 매개변수를 추가합니다.
* <Anchor target="_blank" href="/marketers/ko/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S API</Anchor>의 경우 2021년 7월 1일부터 iOS 앱에 대해 OS(운영 체제) 매개변수를 발송해야 합니다. 이 매개변수를 발송하지 않으면, 데이터는 iOS 14.5 사용자로부터 온 것으로 간주되어 <Anchor target="_blank" href="/marketers/ko/docs/apply-aggregated-advanced-privacy-framework">로데이터 제공 방법</Anchor>에 영향을 미칩니다.

</Accordion>

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration">인앱 이벤트 포스트백 구성</Anchor>

<div data-zendesk-anchors="why-record-inapp-events=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EB%A5%BC-%EA%B8%B0%EB%A1%9D%ED%95%B4%EC%95%BC-%ED%95%98%EB%8A%94-%EC%9D%B4%EC%9C%A0 h_01HDBZW9XEBTY13MG4AN93RNCD=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EB%A5%BC-%EA%B8%B0%EB%A1%9D%ED%95%B4%EC%95%BC-%ED%95%98%EB%8A%94-%EC%9D%B4%EC%9C%A0 about-inapp-events=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC h_01HDBZW9XEBDSDA9T5X5B6KGTG=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC h_01HDBZW9XE3Z40JE9576C4XSF4=%ED%8C%81 predefind-and-custom-events=%EC%82%AC%EC%A0%84-%EC%A0%95%EC%9D%98%EB%90%9C-%EC%82%AC%EC%9A%A9%EC%9E%90%EC%A0%95%EC%9D%98-%EC%9D%B4%EB%B2%A4%ED%8A%B8 01J9XGXGC7R9B19MMX4CQV7DAY=%EC%82%AC%EC%A0%84-%EC%A0%95%EC%9D%98%EB%90%9C-%EC%82%AC%EC%9A%A9%EC%9E%90%EC%A0%95%EC%9D%98-%EC%9D%B4%EB%B2%A4%ED%8A%B8 revenue-in-inapp-events=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%88%98%EC%9D%B5 01J9XGXGC990R3AG0R0XT9E5Y7=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%88%98%EC%9D%B5 h_01HDBZW9XEZWDDHFATKY6KDN25=actual-revenue net-revenue=h_NETREVENUE0001 h_NETREVENUE0002=%EC%B0%B8%EA%B3%A0 h_01JJS31E3D7NCFC9F7QGTT02K1=revenue-currency currency-conversion=%ED%86%B5%ED%99%94-%EC%A0%84%ED%99%98 h_01HDBZW9XEMGA5RAW0DBBPV3FQ=%ED%86%B5%ED%99%94-%EC%A0%84%ED%99%98 h_01HDBZW9XERK3VN1GS8GHM911W=%EC%98%88%EC%8B%9C currency-display=%ED%86%B5%ED%99%94-%ED%91%9C%EC%8B%9C h_01HDBZW9XE85YC3JHG58YYAB8F=%ED%86%B5%ED%99%94-%ED%91%9C%EC%8B%9C h_01HDBZW9XEQNG1RDH7A8H002ZD=%EC%98%88%EC%8B%9C-1 revenue-data-in-the-dashboard=%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C%EC%9D%98-%EC%88%98%EC%9D%B5-%EB%8D%B0%EC%9D%B4%ED%84%B0 h_01HDBZW9XEVWB9045N0YEVWE6Z=%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C%EC%9D%98-%EC%88%98%EC%9D%B5-%EB%8D%B0%EC%9D%B4%ED%84%B0 revenue-data-in-raw-data-reports=%EB%A1%9C%EC%9A%B0-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%A6%AC%ED%8F%AC%ED%8A%B8%EC%9D%98-%EC%88%98%EC%9D%B5-%EB%8D%B0%EC%9D%B4%ED%84%B0 h_01HDBZW9XEGYFD3W9FT1N3ZGQW=%EB%A1%9C%EC%9A%B0-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%A6%AC%ED%8F%AC%ED%8A%B8%EC%9D%98-%EC%88%98%EC%9D%B5-%EB%8D%B0%EC%9D%B4%ED%84%B0 sending-events=%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%B0%9C%EC%86%A1 h_01HDBZW9XFESG6MP9QF1XCJKE6=%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%B0%9C%EC%86%A1 setting-up-inapp-events=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95 h_01HDBZW9XF13AGRCN2HJ18RHS2=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95 h_01HDBZW9XF6X9H4WCFWC28W1CD=defining-an-inapp-event h_01HDBZW9XFN2B8AC18VW99G8Z6=%EC%98%88%EC%8B%9C-2 h_01HDBZW9XFM33BYF90EJPQ35V9=recommended-events-by-business-vertical h_01HDBZW9XF6G2R6Y6S5GFNDM6W=view-inapp-event-data 01JEWW8YB6A91VT8Z4PM9NCV00=%EC%B0%B8%EA%B3%A0-1 h_01HDBZW9XF1Q1NB1YS8Q0HKA6K=tips h_01HDBZW9XFFNWCJ18NETEM2287=limitations faq=%EC%9E%90%EC%A3%BC-%EB%AC%BB%EB%8A%94-%EC%A7%88%EB%AC%B8 h_01HDBZW9XF5H24H2HCJKKHCRTE=%EC%9E%90%EC%A3%BC-%EB%AC%BB%EB%8A%94-%EC%A7%88%EB%AC%B8 h_01HDBZW9XF5ZNGVEMND08137PR=how-do-i-use-the-revenue-parameter h_01HDBZW9XFZ144ND2FXW2AMGRW=how-does-appsflyer-attribute-events h_01HDBZW9XFDBFY580P939ZP0D4=are-events-recorded-if-a-device-is-offline h_01HDBZW9XFCDMKNWJ75AWHC2Y0=%EC%B0%B8%EA%B3%A0-2 h_01HDBZW9XF8Q57JZPD8J2Y25SB=what-are-complex-inapp-events-and-how-do-i-set-them-up h_01KSMX2ECGTDXQP3G9PZW1PFQD=%EC%98%88%EC%8B%9C-3 h_01KSMX2ECGNMX39RD2F6ZHQEK4=%EC%A4%91%EC%9A%94 h_01HDBZW9XFRAFSXJE5N5ZPRW2R=can-i-add-multiple-items-to-a-single-transaction h_01HDBZW9XFB9TAT8W4CGNP1892=%EC%98%88%EC%8B%9C-4 h_01HDBZW9XFGMG5B5FG2785ERAM=how-does-appsflyer-handle-event-deduplication h_01HDBZW9XFWKN7W90PSVMX73FS=%EC%B0%B8%EA%B3%A0-3 h_01HDBZW9XFFXXBYY14A3QGENSF=how-long-does-appsflyer-retain-userlevel-data-and-what-are-the-deletion-obligations h_01HDBZW9XFH80JK748PAPG09B5=do-i-need-to-add-the-os-operating-system-parameter-to-my-events h_01HDNZ708FN0N286R5HDQGMNGZ=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
