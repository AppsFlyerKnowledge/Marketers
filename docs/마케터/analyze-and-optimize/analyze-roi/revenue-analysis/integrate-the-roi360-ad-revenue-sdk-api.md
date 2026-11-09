---
title: ROI360 노출 수준 광고 수익 SDK API 통합 가이드
metadata:
  keywords:
    - ROI
    - ad revenue
    - Advertisers
    - Advertiser
    - Developer
    - Developers
    - ad revenue SDK
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2022-01-12T09:09:07Z'
  edited_at: '2026-10-14T10:38:04Z'
  id: 4416353506833
  locale: ko
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/ko/articles/4416353506833
---
> **한눈에 보기:** 앱스플라이어 광고 수익 SDK API는 광고 네트워크와 협력하여 노출 수준의 세부적인 광고 수익을 보고합니다.

<Image align="center" alt="mceclip1__1_.png" src="https://files.readme.io/202ded6950dfbf370bb48738876224936d28ecfae0c0aba09d1c49892b774cb5-31202279100177.png" />

<div id="impression-level-ad-revenue-reporting-by-sdk-api" />

## SDK API를 통한 노출 수준 광고 수익 보고

**광고 수익 보고 옵션**

광고 수익은 API를 통한 집계 수준 세분성 또는 SDK를 통한 노출 수준 세분성으로 앱스플라이어에 보고됩니다. SDK를 통한 노출 수준 데이터:

* 앱스플라이어에서 데이터 최신성을 개선하여 더 빠르게 이용할 수 있습니다.
* SKAN을 지원합니다.
* 앱스플라이어 SDK V6.15+용입니다. 이전 SDK 버전에서는 API 대신 SDK 커넥터가 사용됩니다. 개발자를 위한 링크는 해당 문서에 포함되어 있습니다.

**참고:**

* 광고 수익 노출은 앱스플라이어에서 수집 및 처리되지만 인앱 패키지에는 포함되지 않습니다.

<div id="reporting-ad-revenue-using-the-sdk-api" />

### SDK API를 사용한 광고 수익 보고

**SDK 작동 원칙**

광고 수익 SDK API는 노출 수익 데이터를 앱스플라이어 SDK로 전송합니다. 이러한 노출 이벤트는 앱스플라이어에서 수집 및 처리되며, 광고 수익 이벤트  이 플랫폼에서 생성되고 수익이 원래 UA 소스에 귀속됩니다. 

**데이터 표시**

`af_ad_revenue`이벤트는 광고 수익을 식별하는 데 사용됩니다. 대시보드 및 다른 데이터 전송 도구 등 플랫폼 전반에 걸쳐 이 이벤트가 사용됩니다.

**지원되는 네트워크**

광고 수익 SDK API를 통해 데이터를 보낼 수 있는 지원되는 광고 수익 중재 및 수익화 네트워크 목록은 다음과 같습니다.

* <Anchor target="_blank" href="/marketers/ko/docs/ironsource-campaign-configuration#ad-revenue-tab">Unity LevelPlay 중재</Anchor> (이전의 아이언소스)
* <Anchor target="_blank" href="/marketers/ko/docs/applovin-max-ad-revenue-configuration">Applovin Max</Anchor>
* <Anchor target="_blank" href="/marketers/ko/docs/google-admob-ad-revenue-attribution-configuration">Google AdMob</Anchor>
* <Anchor target="_blank" href="/marketers/ko/docs/fyber-campaign-configuration">Fyber</Anchor>
* <Anchor target="_blank" href="/marketers/ko/docs/appodeal-campaign-configuration">Appodeal</Anchor>
* Admost
* Topon
* Topon Pte.
* Tradplus
* <Anchor target="_blank" href="/marketers/ko/docs/yandex-direct-campaign-configuration">Yandex</Anchor>
* <Anchor target="_blank" href="/marketers/ko/docs/chartboost-campaign-configuration">Chartboost</Anchor>
* customMediation (미디에이션 솔루션이 지원되는 파트너 목록에 없는 경우)
* directMonetizationNetwork (앱이 미디에이션 없이 수익화 네트워크와 직접 통합되는 경우)

**데이터 최신성**

**SDK API는 광고가 표시될 때 수익 데이터를 플랫폼으로 전송합니다. ROI360 프리미엄 고객의 경우, 데이터는 다음과 같이 제공됩니다.**

* **오전 1시와 이후 매시간마다 업데이트되는 DataLocker 노출 수준 주제,**
* **UTC 오전 5시와 이후 매 4시간마다 업데이트되는 앱스플라이어 활동 및 코호트 보고서.**

<div id="implementing-appsflyer-ad-revenue-sdk-api" />

## 앱스플라이어 광고 수익 SDK API 구현

**앱스플라이어 광고 수익 SDK API를 구현하려면**:

1. <Anchor target="_blank" href="/marketers/ko/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">연결하려는 파트너를 위해 앱스플라이어에서 SDK 수준 광고 수익을 활성화하십시오.</Anchor> **참고**: 이 과정은 각 앱에 대해 개별적으로 진행해야 합니다.
2. 개발자에게 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue">이 설명서</Anchor>를 사용하여 귀사의 앱스플라이어 광고 수익 SDK API를 통합하도록 요청하세요.
3. SKAdNetwork 대시보드에서 광고 수익을 기록하려면 <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-solution-guide#recording-ad-revenue">SKAN 광고 수익 지침</Anchor>을 따르세요.

<div id="traits-and-limitations" />

## 특성 및 한계

| 특징 | 비고 |
| --- | --- |
| 애드몹 | <ul><li>Admob에서 iLTV를 활성화하려면 <Anchor target="_blank" href="https://support.google.com/admob/answer/11322405#getstarted">이 링크</Anchor>를 따르세요.</li><li>안드로이드 및 Unity에서는 Admob iLTV SDK가 노출 수익을 <Anchor target="_blank" href="https://developers.google.com/android/reference/com/google/android/gms/ads/AdValue#public-long-getvaluemicros">마이크로 단위</Anchor>로 보고합니다. 앱스플라이어로 광고 수익 금액을 보내기 전, iLTV 이벤트 핸들러에서 추출한 금액을 100만으로 나눔으로써 앱스플라이어에 정확한 미화 광고 수익이 표시되게 합니다.</li></ul> |
| 광고 수익 가치 | 수익 가치가 10달러(또는 다른 통화의 해당 금액)를 초과하는 노출 이벤트는 SDK API에서 처리되지 않습니다. |
| 채널 | 아마존을 제외한 스토어 외부 앱의 경우 채널 지원이 되지 않습니다. |

<div data-zendesk-anchors="impressionlevel-ad-revenue-reporting-by-sdk-API=sdk-api%EB%A5%BC-%ED%86%B5%ED%95%9C-%EB%85%B8%EC%B6%9C-%EC%88%98%EC%A4%80-%EA%B4%91%EA%B3%A0-%EC%88%98%EC%9D%B5-%EB%B3%B4%EA%B3%A0 01H8HHAQHK6CDK8X2Y6N4GANNC=sdk-api%EB%A5%BC-%ED%86%B5%ED%95%9C-%EB%85%B8%EC%B6%9C-%EC%88%98%EC%A4%80-%EA%B4%91%EA%B3%A0-%EC%88%98%EC%9D%B5-%EB%B3%B4%EA%B3%A0 reporting-ad-revenue-using-the-sdk-API=sdk-api%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%9C-%EA%B4%91%EA%B3%A0-%EC%88%98%EC%9D%B5-%EB%B3%B4%EA%B3%A0 01H8HHAQHKQ3H3R21Z1JYNJ2EE=sdk-api%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%9C-%EA%B4%91%EA%B3%A0-%EC%88%98%EC%9D%B5-%EB%B3%B4%EA%B3%A0 implementing-generic-appsflyer-ad-revenue-sdk-API=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EA%B4%91%EA%B3%A0-%EC%88%98%EC%9D%B5-sdk-api-%EA%B5%AC%ED%98%84 01H8HHAQHKCXKPJJE8EDT1J9CR=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EA%B4%91%EA%B3%A0-%EC%88%98%EC%9D%B5-sdk-api-%EA%B5%AC%ED%98%84 traits-and-limitations=%ED%8A%B9%EC%84%B1-%EB%B0%8F-%ED%95%9C%EA%B3%84 01H8HHAQHMCSVQ2ZAT3G7XJKAN=%ED%8A%B9%EC%84%B1-%EB%B0%8F-%ED%95%9C%EA%B3%84" />
