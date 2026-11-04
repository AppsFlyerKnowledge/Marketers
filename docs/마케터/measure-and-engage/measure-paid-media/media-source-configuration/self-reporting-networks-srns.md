---
title: 셀프 리포팅 네트워크(SRN)
metadata:
  keywords:
    - Facebook
    - Advertisers
    - Agencies
    - Ad Networks
    - srn
    - Self-reporting
    - networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2018-10-22T05:21:45Z'
  edited_at: '2026-10-14T10:31:21Z'
  id: 360001546905
  locale: ko
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/ko/articles/360001546905
---
> **한눈에 보기:** 셀프 리포팅 네트워크(SRN)에 대해 알아보세요. 어트리뷰션, 딥링킹, iOS 관련 사항 및 FAQ를 확인하세요.

<div id="srns-integrated-with-appsflyer" />

## 앱스플라이어와 통합된 SRN

| **SRN** | **로고** |
| --- | --- |
| <Anchor target="_blank" href="/marketers/ko/docs/amazon-ads-campaign-configuration">아마존 광고</Anchor> | <Image alt="amazon-ads-logo.png" src="https://files.readme.io/0a4c9078bd683c51bad40408c894f6e2b7314d7c369bd46ac90c3e622f62f0a7-11927906589329.png" width="134px" /> |
| <Anchor target="_blank" href="/marketers/ko/docs/apple-ads-integration-setup">Apple Search Ads</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/iossearchads.png" width="131px" /> |
| <Anchor target="_blank" href="/marketers/ko/docs/google-ads-adwords-integration-setup-for-advertisers">Google Ads</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/googleadwords.png?v=1" width="47px" /> |
| <Anchor target="_blank" href="/marketers/ko/docs/google-marketing-platform-display-video-360-dv360-integration">Google 마케팅 플랫폼</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/doubleclick.png?v=1" width="45px" /> |
| <Anchor target="_blank" href="/marketers/ko/docs/meta-ads-integration-setup">Meta Ads</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/facebook.png?v=1" width="67px" /> |
| <Anchor target="_blank" href="/marketers/ko/docs/roku-integration-with-appsflyer">Roku</Anchor> | <Image alt="roku.png" src="https://files.readme.io/4909a45e611700e5c2a69f94710226e65e10faf620e3a7939a2c038bea1736ca-33565070184337.png" width="150px" /> |
| <Anchor target="_blank" href="/marketers/ko/docs/snapchat-advanced-srn-integration-setup">스냅챗—고급 SRN</Anchor> | <Image alt="snapchat_logo.png" src="https://files.readme.io/c9b62d55d5c1497011d7411a21dca6f1668308bbe2806ab238b71742c421b182-32259457816209.png" width="41px" /> |
| 텐센트 소셜 광고 | <Image alt="blobid0.jpg" src="https://files.readme.io/6d6e9661c9d81f80ffeedfdf4850a84f3cc183faa49a514d1d3bb116641738da-32259428896017.jpg" width="80px" /> |
| <Anchor target="_blank" href="/marketers/ko/docs/tiktok-for-business-advanced-srn-integration-setup">TikTok for Business—고급 SRN</Anchor> | ![TTFB_logo__4C_horizontal_black.png](https://files.readme.io/caa8c9e02b161eea10740cb79f26d04d3324e87b9cfd929281374d2d7936ef2e-32259428903953.png) |
| <Anchor target="_blank" href="/marketers/ko/docs/x-ads-formerly-twitter-ads-setup-guide-overview">X Ads</Anchor> | <Image alt="X Ads logo.png" src="https://files.readme.io/cecae90650321943ad1cb6d22b7f27d3d28b0484f1706cb1be1a19099dfbb20d-20375448207377.png" width="37px" /> |
| <Anchor target="_blank" href="/marketers/ko/docs/yahoo-integration-setup">야후 (Oath: 광고 플랫폼 \ Yahoo Gemini)</Anchor> | <Image alt="verizonmedia.png" src="https://files.readme.io/36291ff556d07a5dbf2ae8ff693ea33d21dae9e0518a94b251202634a24049cf-32259428916369.png" width="76px" /> |
| <Anchor target="_blank" href="/marketers/ko/docs/yahoo-japan-search-ads-campaign-configuration">Yahoo! 검색 광고</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/yahoojapansearch.png" width="139px" /> |

**참고:** SRN은 <Anchor target="_blank" href="/marketers/ko/docs/user-level-data-retention">유저 수준 데이터 사용 및 리텐션 제한</Anchor>이 있습니다.

<div id="attribution" />

## 어트리뷰션

비 SRN(광고 네트워크)은 이벤트를 앱스플라이어에 리포팅하기 위해 어트리뷰션 링크를 사용하지만, SRN은 앱스플라이어로부터 인스톨 알림을 받을 때 디바이스 ID로 자체 어트리뷰션을 수행합니다. iOS 앱의 경우 <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-solution-guide">SKAN</Anchor> 및 <Anchor target="_blank" href="/marketers/ko/docs/apply-aggregated-advanced-privacy-framework">데이터 집약형 고급 개인 정보 보호 프레임워크</Anchor>를 어트리뷰션에 사용합니다.

앱스플라이어 어트리뷰션은 SRN과 비 SRN 모두에 대해 다음을 기반으로 합니다.

* 마지막 터치와 멀티 터치 방법론.
* 앱스플라이어 표준 어트리뷰션 로직을 사용하여 관련 노출 및 클릭 데이터를 정렬합니다.

<div id="how-does-attribution-work-with-srns" />

### SRN과의 어트리뷰션은 어떻게 작동합니까?

SRN은 새로운 인스톨 및 인앱 이벤트와 같은 이벤트를 다음과 같이 앱스플라이어에 리포팅합니다.

* API를 사용하여 어트리뷰션 및 측정 제공업체와 소통합니다.
* 써드 파티 어트리뷰션 제공자가 인스톨을 감지하면 광고 ID를 사용하여 네트워크에 쿼리를 보냅니다.
* 관련 광고 클릭이나 노출의 세부 정보를 리포트합니다.

앱스플라이어가 어트리뷰션을 수행한 후, 인앱 포스트백은 <Anchor target="_blank" href="/marketers/ko/docs/user-level-data-retention#파트너-데이터-리텐션-기간">파트너 데이터 리텐션 기간</Anchor> 동안 SRN으로 전송됩니다.

<div id="how-does-attribution-work-with-advanced-srns" />

### 고급 SRN의 어트리뷰션은 어떻게 작동합니까?

고급 SRN은 SRN과 동일한 방식으로 어트리뷰션을 수행합니다. 그러나 고급 SRN은 디바이스 ID(IDFA)가 없는 경우에도 <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-knowledge-base-glossary#프라이버시">데이터 집약형 고급 개인정보 보호</Anchor> 프레임워크를 사용해 인게이지먼트를 어트리뷰션할 수 있습니다. 어떤 경우에는 이중 동의를 통해 <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-attribution-model#device-id-matching">ID 매칭</Anchor>을 사용해 어트리뷰션이 수행되며, 일부 고급 SRN의 경우 클릭과 노출에 대한 API 통신을 통해 <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-attribution-model#probabilistic-modeling">확률적 모델링</Anchor>을 사용해 어트리뷰션이 이루어집니다.

<div id="install-attribution" />

### 인스톨 어트리뷰션

잠재적인 앱 사용자들은 앱을 인스톨하기 전에 여러 광고를 보고 상호작용합니다. 일반적으로 어트리뷰션 제공자는 광고주에게 마지막 터치 어트리뷰션을 제공합니다. 이는 실제 인스톨 전에 이루어진 마지막 클릭에 인스톨을 귀속시키는 것입니다.

앱이 처음 실행될 때:

* 앱스플라이어는 다음을 확인합니다.
  * 앱이 SRN으로부터 트래픽을 받을 수 있도록 설정되어 있습니다.
  * 유저는 광고 ID가 있습니다.
* 두 조건이 모두 참일 경우, 앱스플라이어는 광고 ID를 사용해 SRN을 쿼리합니다.
* 앱스플라이어는 SRN의 주장들을 고려해 어트리뷰션을 수행합니다.

<div id="install-attribution-examples" />

#### 인스톨 어트리뷰션 예시

<div id="example-a-assisted-attribution" />

<Accordion title="예시 A: 인스톨 어시스트 어트리뷰션">

![SRN_1.png](https://files.readme.io/8e244c99f54b36a4e88b03bf05bb7ca0da2db5c7c601882ea9f68c191c38981b-32259428920337.png)

**월요일:** 네트워크 A에서 유저의 클릭이 보고됩니다.

**화요일:** 네트워크 B에서 비디오 인게이지먼트가 보고됩니다.

**수요일:** 네트워크 C에서 클릭이 보고되고, 30분 후 인스톨이 이루어집니다.

**앱스플라이어**는 인스톨을 네트워크 C에 귀속시키고, 네트워크 A와 B에 인스톨 어시스트 크레딧을 부여합니다.

앱스플라이어는 광고주에게 인스톨 전의 어트리뷰션이 없는 참여 데이터를 제공합니다. 이를 통해 광고주는 멀티 터치 또는 가중치 적용 어트리뷰션 모델을 사용자 정의할 수 있습니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/measure-assisted-installs">지원 인스톨 설명</Anchor>을 참조하세요.

</Accordion>

<div id="example-b-last-click-attribution" />

<Accordion title="예시 B: 마지막 클릭 어트리뷰션">

![SRN_2.png](https://files.readme.io/6817d8235acfdbbb5324d07ea8a31ace21cf2306e8e099129d9802e3e0d58b0c-32259457863825.png)

**네트워크 D**(SRN)가 네트워크 C보다 몇 분 먼저 클릭을 보고합니다.

**네트워크 C**는 표준 어트리뷰션 연동을 사용합니다.

**앱스플라이어**는 마지막 클릭이 있었던 네트워크 C에 인스톨을 귀속시킵니다.

</Accordion>

<div id="attribution-windows" />

### 어트리뷰션 기간

어트리뷰션 기간에는 룩백과 뷰-쓰루(view-through)가 포함됩니다. 일부 SRN은 노출당 비용(CPM)과 비용당 행동(CPA)을 기준으로 인스톨 비용을 청구하는데, 이는 1&#126;28일 기간 내의 클릭 또는 노출을 기준으로 합니다.

**앱스플라이어**는 광고주가 선호하는 어트리뷰션 방법론과 룩백 기간에 따라 인스톨, 액티비티, 유효 앱 설치당 비용(eCPI), 유효 행동당 비용(eCPA)을 어트리뷰션 합니다.

**광고주**는 SRN 어트리뷰션 룩백 윈도우와 뷰-쓰루 모델에 따라 인스톨 비용을 지불할 수도 있습니다.

* 광고주는 앱스플라이어 써드 파티 범용 어트리뷰션 방법론을 통해 광고 지출을 최적화하고 할당할 수 있기를 기대합니다.
* 이유는? 앱스플라이어가 광고주가 정의한 조건에 따라 실제 eCPI와 eCPA를 보고하기 때문입니다.
* SRN은 종종 자체적으로 지불 조건을 정의하므로 단기적으로 이익을 얻을 수 있습니다. 하지만 광고주는 써드 파티 어트리뷰션 제공업체를 사용하여 이를 바로잡습니다.

<div id="deep-linking-with-srns" />

## SRN을 활용한 딥링킹

링크를 클릭했을 때 귀사의 앱을 열 수 있도록 앱 링크/유니버설 링크/URI 스키마를 설정하기만 하면 됩니다. 그러나 특정 페이지나 액티비티로 딥링크 또는 디퍼드 딥링킹을 수행하기 위해 SRN은 앱스플라이어 딥링킹 메서드를 사용하지 않고 자체 방법을 사용합니다.

그렇다면 어떻게 귀사의 사용자를 딥링크 하고 SRN에서 관련 데이터를 얻을 수 있을까요?

<div id="direct-deep-linking" />

<Accordion title="직접 딥링크">

사용자 디바이스가 딥링킹을 수행할 때, 앱스플라이어의 딥링킹 메서드를 호출하지 않고도 SRN과 직접적인 딥링크가 수행됩니다. 아래 예제에서, 기존 사용자가 광고를 클릭하면 페이스북의 방법을 사용하여 직접 해당 액티비티로 리디렉션되며, 신규 사용자는 앱스플라이어의 전환 데이터를 활용해 동일한 경험을 얻습니다. <Anchor target="_blank" href="/marketers/ko/docs/meta-ads-faq#who-needs-facebooks-sdk">Meta 광고가 원링크를 활용한 딥링킹 방법</Anchor>을 알아보세요.

<div id="example" />

> 📄 **예시**
>
> "greatapp"의 모바일 마케터인 질은 일반 오디언스를 대상으로 하는 Meta 광고에서 딥링킹 캠페인을 실행하기로 결정했습니다. 캠페인은 클릭한 모든 사용자를 "보너스" 액티비티로 리디렉션합니다.
> 모바일 개발자인 잭은 전환 데이터를 얻은 후 다음과 같은 로직을 추가합니다:
>
> 1. 페이스북에서 시작된 것인가요("is\_fb=true")?
> 2. true인 경우, 광고 그룹 매개변수의 값을 가져옵니다.
> 3. 값에 "보너스"라는 단어가 포함되어 있으면 사용자를 "보너스" 액티비티로 발송합니다.

</Accordion>

<div id="deferred-deep-linking" />

<Accordion title="디퍼드 딥링킹">

딥링킹과 달리, 앱스플라이어 GCD API를 사용하면 SRN을 활용한 디퍼드 딥링킹이 가능합니다.  앱스플라이어는 전환 데이터를 수신하여 첫 번째 실행 시 앱에서 사용할 수 있도록 합니다. 전환 데이터를 사용하면, SRN에서 딥링크/리타겟팅 캠페인을 클릭한 후 앱을 설치한 신규 사용자를 앱 실행 시 내부의 특정 위치로 리디렉션할 수 있습니다.

실제 딥링크 값을 사용하여 GCD를 통해 쿼리할 수 있는 `af_dp` 필드를 이용하면, Google Ads, Snapchat, TikTok for Business에서 디퍼드 딥링크가 지원됩니다. TikTok for Business의 경우, 이 값은 `deep_link_value` 필드에서도 액세스할 수 있습니다. 그러나 다른 SRN에서는 일반적인 앱스플라이어 딥링킹 파라미터가 딥 링크 데이터의 일부로 포함되지 않습니다. 앱 내에서 이 데이터를 사용하려면 캠페인, 광고 세트, 단일 광고 이름 등 사용 가능한 파라미터를 기반으로 한 추가 로직을 개발자가 채택해야 합니다.

**참고**: <Anchor target="_blank" href="/marketers/ko/docs/meta-ads-faq#who-needs-facebooks-sdk">Meta Ads</Anchor>의 경우, Google Install Referrer 메커니즘을 사용하는 안드로이드 앱에서는 GCD를 통한 디퍼드 딥링크가 가능합니다. Facebook SDK가 귀하의 앱에 연동된 경우에만 iOS앱에서 사용할 수 있습니다.

</Accordion>

<div id="ios-implications" />

## iOS 관련 사항

대부분의 SRN은 SKAdNetwork를 지원하며, 앱스플라이어와의 필요한 연동을 갖추고 있습니다.

<div id="ios-145-srn-attribution" />

<Accordion title="iOS 14.5 SRN 어트리뷰션">

iOS 14.5부터  광고주와 퍼블리셔 앱에서 앱 추적 투명성(ATT, AppTrackingTransparency) 동의를 받은 경우(<Anchor target="_blank" href="/marketers/ko/docs/appsflyer-knowledge-base-glossary#이중-동의">이중 동의</Anchor>), SKAdNetwork 대시보드에 기록된 SRN 인스톨이 기존 대시보드에도 표시됩니다.

<div id="note" />

> 📘 **참고**
>
> * 기존 대시보드에서는 SRN에 귀속된 인스톨 수가 감소하는 것으로 나타납니다. SRN 성과를 고려할 때 <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">SKAdNetwork 대시보드</Anchor>를 사용하세요. 전반적으로 SRN 인스톨 어트리뷰션은 감소하고, 오가닉 인스톨은 증가할 것으로 예상됩니다. 하지만 고급 SRN의 경우 디바이스 ID가 없어도 참여를 어트리뷰션하기 때문에 영향이 낮습니다.
> * <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">SKAdNetwork 대시보드</Anchor>는 인스톨 후 48&#126;72시간 후에 업데이트됩니다.
> * Apple Search Ads (ASA)로 유입된 인스톨은 SKAdNetwork 대시보드에 반영되지 않습니다.

</Accordion>

<div id="sending-event-postbacks-to-srns" />

<Accordion title="SRN에 이벤트 포스트백 보내기">

이벤트 포스트백을 받는 SRN은 포스트백에 디바이스 ID를 포함하는 것에 의존합니다. 이를 통해 SRN은 보고된 유저 행동을 자체적으로 어트리뷰션할 수 있습니다.  많은 iOS 14 유저는 동의하지 않아 디바이스 ID (IDFA)에 대한 액세스를 허용하지 않습니다. 이 경우, 예상되는 결과는 다음과 같습니다:

* SRN에 전송되는 이벤트 포스트백 수의 감소
* SRN과 모든 이벤트를 기록하는 앱스플라이어 간의 이벤트 포스트백 수에 차이가 발생합니다.

<div id="note-1" />

> 📘 **참고**
>
> * IDFA가 없으면 인스톨, 앱 오픈 또는 인앱 이벤트에 대한 포스트백이 SRN으로 전송되지 않습니다. [그러나 특정 상황에서는 광고 ID가 없어도 앱스플라이어가 SRN에 포스트백을 보냅니다.](/docs/self-reporting-networks-srns#does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid)
> * 클릭 기반 광고 네트워크는 디바이스 ID가 아닌 자체 거래 ID를 사용하기 때문에 이벤트 포스트백 정보를 자체적으로 어트리뷰션하여 영향을 받지 않습니다.

</Accordion>

<div id="faq" />

## 자주 묻는 질문

<div id="how-does-retargeting-work-with-srns" />

<Accordion title="SRN과 리타겟팅은 어떻게 작동하나요?">

SRN이 아닌 네트워크에서의 리타겟팅 클릭은 리타겟팅 어트리뷰션 링크에 `is_retargeting=true` 파라미터가 존재함으로 인해 쉽게 식별할 수 있습니다.  
SRN의 경우에는 이와 같은 명확한 표시가 없습니다. 대신, SRN에서의 재참여 어트리뷰션을 활성화하기 위해 앱스플라이어는 다른 논리를 사용합니다.

* 필수 조건:
  * **앱 설정** 페이지에서 **리타겟팅 활성화**를 켭니다.
  * **활성화된 연동** 페이지에서 SRN을 선택하고 **리타겟팅**을 켭니다.
* 앱스플라이어는 앱이 출시될 때마다 SRN에 디바이스 ID가 최근 캠페인 광고와의 인게이지먼트 여부를 쿼리합니다.
  * SRN이 인게이지먼트 세부 정보로 응답하면 앱스플라이어는 이를 룩백 윈도우 내에 있으며 재참여 최소 시간보다 오래된 것으로 확인합니다.
  * 검증된 인게이지먼트는 재참여로 기록되며 SRN에 속하게 됩니다.

</Accordion>

<div id="what-is-srn-mistargeting" />

<Accordion title="SRN 미스 타겟팅이란 무엇인가요?">

SRN 캠페인은 특정 오디언스를 타겟으로 해야 하지만 항상 그렇지는 않습니다. 유저 유입 캠페인에서는 비사용자, 리타겟팅 캠페인에서는 기존 사용자를 대상으로 합니다.

하나의 SRN을 통해 유저 유입과 리타겟팅 캠페인을 함께 실행하면 사용자가 잘못 타겟팅될 수 있습니다. 결과적으로 의도치 않은 트래픽에 비용이 지불됩니다.

**시나리오:** 앱스플라이어 플랫폼에서 SRN을 유저 유입 캠페인으로 활성화합니다.

* 앱스플라이어는 앱을 실행할 때마다 SRN에 광고 ID(사용자)가 최근에 인게이지먼트를 했는지 확인합니다.
* 만약 그렇다면,
  * SRN은 캠페인 이름으로 응답합니다.
  * 앱스플라이어는 앱이 최초로 실행된 것인지 여부를 판단해 그에 따라 어트리뷰션을 결정합니다.  
    **앱 최초 오픈**: 새로운 인스톨이 캠페인에 어트리뷰션됩니다.  
    **두 번째 이후 실행**: 리타겟팅 이벤트가 캠페인에 귀속됩니다.

**결론:** 유저 유입 캠페인에서 리타겟팅 이벤트를 얻는 것은 낭비입니다.

<div id="is-mistargeting-a-problem" />

#### 잘못된 타겟팅이 문제인가요?

앱스플라이어 데이터 분석가는 특정 달 동안 Meta Ads **유저 유입** 캠페인을 확인했습니다.

* 리타겟팅이 활성화되었습니다.
* 캠페인의 30%에서 타겟 사용자 중 최소 15%가 기존 앱 사용자였습니다.
* 캠페인의 5%에서는 최소 40%가 기존 앱 사용자였습니다.
* **결론: SRN 유저 유입 캠페인에서 타겟 사용자 10명 중 1명은 이미 기존 사용자입니다.**

[alt잘못된 대상 사용자.pngalt](https://support.appsflyer.com/hc/article_attachments/30709726739473)

<div id="solving-the-mistargeting-problem" />

#### 잘못된 타겟팅 문제 해결

**기본 솔루션:** 기존 앱 사용자를 유저 유입 캠페인에 포함하지 마세요.

* SRN은 잠재적인 신규 사용자만을 타겟으로 합니다.
* **동일한 예산으로 새로운 유저 유입 효과를 극대화합니다**.
* 예를 들어 한 달에 한 번 정도 주기적으로(그리고 수동으로) 캠페인을 업데이트합니다.
* 그러나 시기의 차이로 인해 기존 사용자가 앱 인스톨 후 첫 달 동안 유저 유입 캠페인의 타겟이 될 수 있습니다.

앱스플라이어의 프리미엄 기능인 <Anchor target="_blank" href="/marketers/ko/docs/audiences-guide">**오디언스**</Anchor>를 사용하면, 매일 귀사의 다양한 세그먼트를 수십 개의 광고 네트워크에 자동 발송할 수 있습니다.

앱스플라이어 연구에 따르면, 잘못된 타겟팅 문제를 해결하면 귀사의 마케팅 및 유저 유입 활동에 극적인 영향을 미칠 수 있습니다.

</Accordion>

<div id="why-is-the-original-url-field-empty-in-raw-data-reports" />

<Accordion title="로데이터 리포트에서 '원래 URL' 필드가 비어 있는 이유는 무엇인가요?">

클릭은 SRN 환경에서 이루어지지만, 앱스플라이어 어트리뷰션 링크가 없습니다. 따라서 클릭과 관련된 '원래 URL' 데이터를 앱스플라이어에서 확인할 수 없습니다.

</Accordion>

<div id="dashboard-doesnt-show-srn-clicks-and-impressions" />

<Accordion title="대시보드에 SRN 클릭 및 노출이 표시되지 않습니다.">

클릭은 SRN 환경에서 이루어지지만, 앱스플라이어 어트리뷰션 링크가 없습니다. 따라서 일부 SRN은 앱스플라이어에 클릭 및 노출 데이터를 제공하지 않습니다.

<Anchor target="_blank" href="/marketers/ko/docs/meta-ads-integration-setup#cost-clicks-and-impressions">Meta Ads</Anchor>와 <Anchor target="_blank" href="/marketers/ko/docs/google-ads-adwords-cost-and-ad-revenue">Google</Anchor>은 앱스플라이어에 일부 집계 데이터를 제공합니다.

</Accordion>

<div id="can-agencies-configure-srn-campaigns" />

<Accordion title="에이전시가 SRN 캠페인을 구성할 수 있나요?">

네, <Anchor target="_blank" href="/partners/ko/docs/about-agency-accounts#자체-보고-광고-네트워크">여기에서 에이전시의 SRN 구성에 대해 알아보세요</Anchor>.

</Accordion>

<div id="does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid" />

<Accordion title="앱스플라이어가 누락된 광고 ID(IDFA/GAID)에 대해 포스트백을 발송하나요?">

광고 ID가 빈 문자열("")을 포함하거나 '00000000-0000-0000-0000-000000000000'(모두 0인 IDFA) 값을 보일 경우, 앱스플라이어는 다음 시나리오를 제외하고 인스톨, 앱 오픈 또는 인앱 이벤트에 대해 포스트백을 발송하지 않습니다.

* Google Ads: Google Ads와 리마케팅 측정을 위한 연동의 일환으로, 동의하지 않은 iOS 유저가 앱을 열거나 인앱 이벤트를 수행하면 앱스플라이어에서 Google Ads에 `gbraid` 및 이벤트 정보를 (`additional_data_json` 이벤트) 전송합니다.
* Google Ads: 안드로이드에서 디바이스 ID가 없지만 레퍼럴 값에 `gclid`(인스톨)이 포함되어 있거나 리인게이지먼트 이벤트가 `gclid` 매개변수가 있는 딥 링크를 포함한 경우, 앱스플라이어는 Google Ads로 `gclid` 및 이벤트 정보를 전송합니다.
* Meta: 페이스북 쿠키 또는 캠페인 ID(딥 링크 또는 이전 리인게이지먼트) 혹은 AEM 토글이 활성화된 경우.
* 스냅챗 및 TikTok (고급 SRN) - PMOD를 통해 스냅챗 또는 TikTok에 어트리뷰션이 되고 나서 해당 인스톨과 관련된 인앱 이벤트가 도착하면 포스트백을 발송합니다.

**Google Ads** 매개변수: **Google에서 생성한 데이터 집약형 식별자로, 여러 디바이스 그룹을 식별하며 딥 링크에서 참조됩니다.**

**Google 클릭 ID ( 매개변수):** 광고 클릭과 함께 URL에 전달되는 매개변수로, 광고와 관련된 캠페인 및 기타 클릭 속성을 식별합니다. 이 정보는 광고 측정 및 캠페인 어트리뷰션에 사용됩니다.

</Accordion>

<div id="are-clicks-and-impressions-from-srns-available-in-raw-data-reports" />

<Accordion title="SRN에서의 클릭수 및 노출수가 로데이터 리포트에 포함되어 있습니까?">

아니요, SRN의 클릭수 및 노출수는 로데이터 리포트에 포함되지 않습니다. SRN 데이터가 어트리뷰션에 사용되지만, 클릭수 및 노출수에 대한 로데이터는 리포트에 포함되지 않습니다. 이는 TikTok, Snap, Meta 및 Google을 포함한 모든 SRN에 적용됩니다.

</Accordion>

<div data-zendesk-anchors="srns-integrated-with-appsflyer=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%99%80-%ED%86%B5%ED%95%A9%EB%90%9C-srn h_01HFM2MET40AFB84AW5N8GKWF3=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%99%80-%ED%86%B5%ED%95%A9%EB%90%9C-srn attribution=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 h_01HFM2MET4ZNKEZBT3S74N8CMC=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 how-does-attribution-work-with-srns=srn%EA%B3%BC%EC%9D%98-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98%EC%9D%80-%EC%96%B4%EB%96%BB%EA%B2%8C-%EC%9E%91%EB%8F%99%ED%95%A9%EB%8B%88%EA%B9%8C h_01HFM2MET42R6C87XB5RWX9ABJ=srn%EA%B3%BC%EC%9D%98-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98%EC%9D%80-%EC%96%B4%EB%96%BB%EA%B2%8C-%EC%9E%91%EB%8F%99%ED%95%A9%EB%8B%88%EA%B9%8C how-does-attribution-work-with-advanced%E2%80%94srns=%EA%B3%A0%EA%B8%89-srn%EC%9D%98-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98%EC%9D%80-%EC%96%B4%EB%96%BB%EA%B2%8C-%EC%9E%91%EB%8F%99%ED%95%A9%EB%8B%88%EA%B9%8C h_01HFM2MET4Q6WCSANH18VTGBQX=%EA%B3%A0%EA%B8%89-srn%EC%9D%98-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98%EC%9D%80-%EC%96%B4%EB%96%BB%EA%B2%8C-%EC%9E%91%EB%8F%99%ED%95%A9%EB%8B%88%EA%B9%8C install-attribution=%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 h_01HFM2MET4YQGN3GZKTTBRQ4HK=%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 install-attribution-examples=%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%98%88%EC%8B%9C h_01HFM2MET40Y9V8YGA20CCGVNN=%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%98%88%EC%8B%9C h_01HFM2MET47BP3T07NTRVDWSJ3=example-a-assisted-attribution h_01HFM2MET4FY6SRS534NEA25WV=example-b-last-click-attribution attribution-windows=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EA%B8%B0%EA%B0%84 h_01HFM2MET4ZJF290QNE3TPXQMA=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EA%B8%B0%EA%B0%84 deep-linking-with-srns=srn%EC%9D%84-%ED%99%9C%EC%9A%A9%ED%95%9C-%EB%94%A5%EB%A7%81%ED%82%B9 h_01HFM2MET4ZA6WD6HX92JNFW7X=srn%EC%9D%84-%ED%99%9C%EC%9A%A9%ED%95%9C-%EB%94%A5%EB%A7%81%ED%82%B9 h_01HFM2MET4VZX943736W52V0ZJ=direct-deep-linking h_01HFM2MET4HSVHM0Q1C8D5Z279=%EC%98%88%EC%8B%9C h_01HFM2MET4WGVMRJW7NJ7TF8GQ=deferred-deep-linking ios-implications=ios-%EA%B4%80%EB%A0%A8-%EC%82%AC%ED%95%AD h_01HFM2MET4DGERZJ18A7CEFDS9=ios-%EA%B4%80%EB%A0%A8-%EC%82%AC%ED%95%AD h_01HFM2MET4SRX0YRZRMHBY6DKT=ios-145-srn-attribution h_01HFM2MET471M5J2XFE7G2Z6J3=%EC%B0%B8%EA%B3%A0 h_01HFM2MET42KNAMWE9S9BSF4PK=sending-event-postbacks-to-srns h_01HFM2MET4WJ6TMTXM03NFFCAG=%EC%B0%B8%EA%B3%A0-1 faq=%EC%9E%90%EC%A3%BC-%EB%AC%BB%EB%8A%94-%EC%A7%88%EB%AC%B8 h_01HFM2MET49FZ8QHDMA7H92BTE=%EC%9E%90%EC%A3%BC-%EB%AC%BB%EB%8A%94-%EC%A7%88%EB%AC%B8 h_01HFM2MET4VYGPWR98HMAWK4YP=how-does-retargeting-work-with-srns h_01HFM2MET4JGYTW6P1VGYMYGFS=what-is-srn-mistargeting is-mistargeting-a-problem=%EC%9E%98%EB%AA%BB%EB%90%9C-%ED%83%80%EA%B2%9F%ED%8C%85%EC%9D%B4-%EB%AC%B8%EC%A0%9C%EC%9D%B8%EA%B0%80%EC%9A%94 h_01HFM2MET4C1HMWH715XP42ZAQ=%EC%9E%98%EB%AA%BB%EB%90%9C-%ED%83%80%EA%B2%9F%ED%8C%85%EC%9D%B4-%EB%AC%B8%EC%A0%9C%EC%9D%B8%EA%B0%80%EC%9A%94 solving-the-mistargeting-problem=%EC%9E%98%EB%AA%BB%EB%90%9C-%ED%83%80%EA%B2%9F%ED%8C%85-%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0 h_01HFM2MET41CDCP8VNGR39YMCK=%EC%9E%98%EB%AA%BB%EB%90%9C-%ED%83%80%EA%B2%9F%ED%8C%85-%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0 h_01HFM2MET4DETEHT8PACHS6C6B=why-is-the-original-url-field-empty-in-raw-data-reports h_01HFM2MET48Y4ATGB1HNDGSFEP=dashboard-doesnt-show-srn-clicks-and-impressions h_01HFM2MET4JEA8BBGN564CQPYX=can-agencies-configure-srn-campaigns h_01HFM2MET42V7AVV2BPZGDRARV=does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid h_01JMJ79S862T4M96ECZPVRZVJJ=are-clicks-and-impressions-from-srns-available-in-raw-data-reports" />
