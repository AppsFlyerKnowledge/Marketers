---
title: 새로운 Google EU 동의 정책 지원
metadata:
  keywords:
    - Agencies
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
  created_at: '2024-02-07T07:28:17Z'
  edited_at: '2026-10-14T10:33:00Z'
  id: 22310731147153
  locale: ko
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/ko/articles/22310731147153
---
> **한눈에 보기:** 앱스플라이어는 마케터가 디지털 시장법(DMA)을 준수하고 Google에서 광고의 가치를 높일 수 있도록 돕습니다. DMA 준수 및 광고 가치 최적화와 관련된 자주 묻는 질문(FAQ)에 대한 답변을 찾아보세요.

<div id="overview" />

## 개요

Google은 <Anchor target="_blank" href="https://commission.europa.eu/strategy-and-policy/priorities-2019-2024/europe-fit-digital-age/digital-markets-act-ensuring-fair-and-open-digital-markets_en">디지털 시장법</Anchor> (DMA) 시행에 대비하여 <Anchor target="_blank" href="https://www.google.com/about/company/user-consent-policy/?sjid=15416941068016224808-NA">EU 사용자 동의 정책</Anchor>을 업데이트하고 있습니다. Google <Anchor target="_blank" href="https://ads.google.com/lp/appcampaigns/attribution/">앱 어트리뷰션 파트너</Anchor>로서 앱스플라이어는 광고주가 Google에서 광고를 최대한 활용할 수 있도록 지원하는 동시에 정책 변화에 적응하고 있습니다.

<div id="relevant-integrations-and-continued-use-of-google-features" />

## 관련 연동 및 Google 기능의 지속적인 사용

<div id="which-integrations-are-involved" />

<Accordion title="어떤 연동이 관련되어 있나요?">

다음 연동은 Google의 새로운 EU 동의 정책과 관련이 있습니다.

* Google Ads(`googleadwords_int`)
* GMP DV360(`dv360_int`)

이러한 연동에서 앱의 최종 유저가 유럽 경제 지역(EEA) 또는 영국에 거주하는 경우 Google의 새로운 EU 동의 정책의 요구사항을 준수하기 위해 필요한 조치를 취해야 합니다.

<div id="note" />

> 📘 **참고**
>
> [레거시] Google 마케팅 플랫폼 DV360/CM 연동(`doubleclick_int`)은 Google의 새로운 EU 동의 정책에 따라 사용이 중단되며 지원되지 않습니다. 이 연동을 사용하시는 경우 <Anchor target="_blank" href="/marketers/ko/docs/bulletin-google-marketing-platform-gmp-integration-transition">새로운 DV360 연동(dv360\_int)으로 전환</Anchor>하시기를 추천해 드립니다.

</Accordion>

마케터가 측정, 개인 맞춤 광고, 리마케팅과 관련된 Google Ads 및 GMP DV360 기능을 계속 사용하려면 EEA 및 영국의 최종 유저의 개인 데이터 사용에 대한 동의를 얻어야 합니다.


<div id="updating-the-appsflyer-sdk" />

## 앱스플라이어 SDK 업데이트

앱스플라이어 SDK(v6.13.0 이상)는 Google의 요구사항을 충족하기 위해 각 이벤트와 함께 필요한 동의 데이터를 전송할 수 있습니다.

* SDK가 업그레이드되면 DMA 지원을 위한 구현 지침을 여기에서 확인하세요<Anchor target="_blank" href="/marketers/ko/docs/additional-sdk-integration-guide#send-consent-for-dma-compliance">.</Anchor>



<span id="sending-consent-data"></span><span id="how-consent-data-is-sent"></span>마케터가 필요한 동의 데이터를 앱스플라이어에 전송하는 옵션에는 두 가지가 있습니다.

* [S2S API 또는 **SDK를 통해 직접 전송**:](#앱스플라이어-sdk-업데이트) 마케터는 SDK를 사용하여 동의 데이터를 앱스플라이어에 직접 전송할 수 있습니다. Android 또는 iOS 앱에 적용할 수 있습니다.
* **TCF 문자열을 통해 전송:** 현재 CMP(동의 관리 플랫폼)를 사용 중이거나 사용할 계획인 마케터는 표준 IAB TCF 문자열(TCF V2.2)을 통해 데이터 필드를 전송할 수 있습니다. 동의한 공급업체 목록에 Google 공급업체 ID(755)를 포함해야 합니다.

그런 다음 앱스플라이어는 고객이 동의 신호를 Google에 전송할 수 있도록 합니다. 그러나 앱스플라이어가 최종 유저 동의를 수집, 변경 또는 제어하지 않는다는 점에 유의해야 합니다. Google과 협력하는 마케터는 필요한 동의 필드를 수집할 책임이 있습니다.


최종 유저 동의 값은 관련 앱스플라이어 연동(`googleadwords_int` 및 `dv360_int`)을 위해 다음 필드를 사용하여 Google로 전송됩니다.

| 앱스플라이어 필드 | Google 필드(1) | 값 | 필드 설명 |
| --- | --- | --- | --- |
| <span id="gdpr_applies"></span>gdpr\_applies | eea | true/false(2) |  |
| <span id="ad_personalization"></span>ad\_personalization\_enabled | ad\_personalization | true\/false | 유저가 개인 광고를 위해 자신의 데이터를 Google에 사용하는 것에 동의했는지 여부 |
| <span id="ad_user_data"></span>ad\_user\_data\_enabled | ad\_user\_data | true\/false | 유저가 자신의 유저 데이터를 Google에 발송하는 데 동의했는지 여부 |

1. (1) <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/13802165?hl=en">각 필드에 대한 Google의 정의</Anchor>를 참조하세요.



<div id="do-i-have-control-over-consent-data-for-nonue-users" />

<div id="sending-consent-datafaq" />

<div id="sending-consent-data-faq" />

<Accordion title="Google에 동의 데이터를 전송하지 않는 옵션이 있나요?">

앱스플라이어는 광고주가 자신의 최종 유저를 GDPR 및 DMA 요구사항의 적용을 받지 않는 최종 유저(예: EU 또는 영국 이외 국가 거주자)라고 생각하는 경우, 동의 데이터를 Google에 전송하지 않도록 할 수 있습니다. 이 작업은 관련 연동 페이지에서 토글을 활성화하여 수행됩니다.

<div id="important" />

> 🚧 **중요!**
>
> 이 옵션을 사용하기 전에 마케터는 법무 및 개인 정보 보호 팀의 승인을 받아 정책에 부합하는지 확인하는 것이 좋습니다. 참조 정의는 Google의 <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/13802165?hl=en">동의 모드 문서</Anchor>를 참조하세요.

**Google과 동의 데이터를 공유하지 않으려면 다음 안내를 따르세요.**

1. 앱스플라이어의 사이드 메뉴에서 **협업** > **활성화된 연동**을 선택합니다.

<Image alt="비 EU 사용자.png" src="https://files.readme.io/fb141c0bd8885facd6574f3e73c5ec8ae8beb596de7fdf3dd8aed9d4e82686dd-22352319155985.png" width="595px" />

</Accordion>

|  |  | 설명 |
| --- | --- | --- |
| `gdpr_applies=1/0` | `eea=1/0` |  |
| `ad_user_data` | `ad_user_data=1` |  |
| `ad_user_data` | `ad_user_data=0` |  |
| `ad_personalization` | `ad_personalization=1` `ad_personalization=0` |  |


네.



<div id="preparing-for-the-upcoming-changes" />

<div id="what-i-can-do-on-my-side" />

<div id="how-can-i-prepare-for-the-upcoming-changes" />

<Accordion title="다음 준비 단계를 수행합니다.">


<span id="address-user-consent-in-the-european-economic-area-eea"></span><span id="address-user-consent-in-the-european-economic-area-eea-and-in-the-uk"></span>회사의 법률 고문과 협력합니다. 유럽 사용자 동의 정책이 Google과 같은 파트너와 공유하는 데이터에 미치는 영향에 대한 인사이트를 제공할 수 있습니다. 필요한 경우 '개인정보 설정' 또는 '개인정보 보호 선택'과 같은 개인정보 보호 프롬프트를 구현하여 앱 유저로부터 마케팅 및 광고 관련 유저 동의 신호를 수집합니다.

<div id="verify-cmp-compliance-and-tcf-2223-support" />

#### CMP 규정 준수 및 TCF 2.2 지원 확인

동의 관리 플랫폼(CMP)이 가장 업데이트된 투명성 및 동의 프레임워크(TCF) 버전인 TCF 2.2를 지원하는지 확인합니다. 또한 TCF는 새로운 Google EU 동의 요구사항에 대해 잘 알고 있어야 하며 TCF를 통해 이를 지원하는 방법에 대해 조언해 줄 수 있습니다.

<div id="implement-the-newest-sdkserver-to-server-s2s-apis" />

#### 최신 SDK/서버 간(S2S) API 구현

SDK 또는 S2S API 호출을 사용하여 새 동의 필드를 전송하려면 다음 옵션을 고려합니다.

* **SDK 사용:**

  * <Anchor target="_blank" href="/marketers/ko/docs/additional-sdk-integration-guide#send-consent-for-dma-compliance">동의 데이터 전송</Anchor> 방법을 선택합니다
* **<Anchor target="_blank" href="/marketers/ko/docs/server-to-server-events-api-for-mobile-s2s-mobile?">S2S</Anchor> API 호출 사용:**
  * 앱스플라이어에 인앱 이벤트를 전송하기 전에 각 이벤트에 대한 `consent_data` 오브젝트를 포함하도록 API 호출을 업데이트합니다. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/s2s-events-api3-post">이 작업을 수행하는 방법</Anchor>을 참조하세요.

<div id="transition-from-the-legacy-gmp-integration-doubleclick" />

#### 레거시 GMP 연동(DoubleClick)에서 전환

레거시 앱스플라이어 GMP 연동(doubleclick\_int)을 계속 사용 중인 경우, 2024년 1분기 이내에 최신 버전(dv360\_int)으로의 전환을 완료하도록 계획합니다. 레거시 연동은 **EU 동의와 호환되지 않으며** 곧 더 이상 사용할 수 없게 됩니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/bulletin-google-marketing-platform-gmp-integration-transition">여기</Anchor>를 참조하세요.

</Accordion>


<span id="impact-on-advertising-activityfaq"></span><span id="impact-on-my-advertising-activity"></span>Google에서 광고 목적으로 데이터를 사용하는 데 동의하지 않는 EU 및 영국의 유저는 Google Ads 및 DV360의 어트리뷰션에 관한 요청을 받지 않습니다. 즉, 앱스플라이어는 해당 유저를 어트리뷰션할 수 없습니다.


<div id="how-will-the-upcoming-change-affect-my-audiences" />

<Accordion title="예정된 변화는 오디언스(Audiences)에 어떤 영향을 미치나요?">

이 변화는 오디언스에 표시되고 Google의 리마케팅 캠페인에 노출되는 EEA 및 영국 유저 수에 영향을 미칠 수 있습니다. EEA 및 영국에 거주하는 유저는 Google과 정보를 공유하기 전에 동의해야 합니다. 동의하지 않는 유저는 Google 측 오디언스에서 제외되며 캠페인에 노출되지 않습니다. 이로 인해 유저의 동의를 얻는 방법과 비즈니스 및 광고 활동의 결과에 관한 질문이 제기됩니다. <Anchor target="_blank" href="/marketers/ko/docs/audiences-user-identifier-policy#eu-digital-markets-act">오디언스의 변화에 대해 더 알아보기</Anchor>.

</Accordion>


<span id="further-information-and-contact-details"></span>추가 질문이나 불확실한 부분이 있는 경우 다음 연락처로 문의할 수 있습니다.

* Google의 요구사항 또는 이러한 업데이트가 Google 데이터에 미칠 수 있는 영향에 대해서는 <Anchor target="_blank" href="https://www.google.com/about/company/user-consent-policy-help/">Google의 도움말</Anchor>을 참조하거나 Google 담당자에게 직접 문의하시기 바랍니다.
* 앱스플라이어의 EU 최종 유저 동의 필드 지원에 관한 질문은 앱스플라이어 CSM 또는 [hello@appsflyer.com](mailto:hello@appsflyer.com)으로 문의하세요.
* 참조 정의는 Google의 <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/13802165?hl=en">동의 모드 문서</Anchor>를 참조하세요.

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 h_01HP195KV35FD6X67WTMXJWWSZ=%EA%B0%9C%EC%9A%94 relevant-integrations-and-continued-use-of-google-features=%EA%B4%80%EB%A0%A8-%EC%97%B0%EB%8F%99-%EB%B0%8F-google-%EA%B8%B0%EB%8A%A5%EC%9D%98-%EC%A7%80%EC%86%8D%EC%A0%81%EC%9D%B8-%EC%82%AC%EC%9A%A9 h_01HP1M37V1CYW5T5E4K1ES3NQA=%EA%B4%80%EB%A0%A8-%EC%97%B0%EB%8F%99-%EB%B0%8F-google-%EA%B8%B0%EB%8A%A5%EC%9D%98-%EC%A7%80%EC%86%8D%EC%A0%81%EC%9D%B8-%EC%82%AC%EC%9A%A9 01HP1KN2H7NTS2V1S2PGF0C41N=which-integrations-are-involved h_01HP2HRPJR72Z0R5VEG5N36CN2=%EC%B0%B8%EA%B3%A0 updating-the-appsflyer-sdk=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-sdk-%EC%97%85%EB%8D%B0%EC%9D%B4%ED%8A%B8 h_01HP1Z2G2M56DDQS9T47GMCFHJ=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-sdk-%EC%97%85%EB%8D%B0%EC%9D%B4%ED%8A%B8 h_01HP1KPSMCH3EG373BWVQZM4ZT=how-consent-data-is-sent sending-consent-data%E2%80%94faq=sending-consent-data-faq h_01HR1X08VZ5MEAV01E9X54KAQS=sending-consent-data-faq h_01HP1JJ2AYZ57G0GMR8QRDTEZ7=do-i-have-control-over-consent-data-for-nonue-users h_01HP2MRPFA2ECJGAZ93NQHVD2J=%EC%A4%91%EC%9A%94 01HR1XYXRDVEW6H9Q3WP17E2N3=what-i-can-do-on-my-side h_01HP1JJ2AYFHRRDYZS8YFYE6WP=how-can-i-prepare-for-the-upcoming-changes h_01HPGNBQCTJFVZR99BY6E5J2JF=address-user-consent-in-the-european-economic-area-eea-and-in-the-uk verify-cmp-compliance-and-tcf-22-support=cmp-%EA%B7%9C%EC%A0%95-%EC%A4%80%EC%88%98-%EB%B0%8F-tcf-22-%EC%A7%80%EC%9B%90-%ED%99%95%EC%9D%B8 h_01HPGNC0HAMA7Z0B4DNV2QSFYG=cmp-%EA%B7%9C%EC%A0%95-%EC%A4%80%EC%88%98-%EB%B0%8F-tcf-22-%EC%A7%80%EC%9B%90-%ED%99%95%EC%9D%B8 implement-the-newest-sdkservertoserver-s2s-apis=%EC%B5%9C%EC%8B%A0-sdk%EC%84%9C%EB%B2%84-%EA%B0%84s2s-api-%EA%B5%AC%ED%98%84 h_01HPGNCAG3M9XPHDTP03WHQQ9F=%EC%B5%9C%EC%8B%A0-sdk%EC%84%9C%EB%B2%84-%EA%B0%84s2s-api-%EA%B5%AC%ED%98%84 transition-from-the-legacy-gmp-integration-doubleclick=%EB%A0%88%EA%B1%B0%EC%8B%9C-gmp-%EC%97%B0%EB%8F%99doubleclick%EC%97%90%EC%84%9C-%EC%A0%84%ED%99%98 h_01HPGNCHP6SSFCVZ3P4AG0N1FB=%EB%A0%88%EA%B1%B0%EC%8B%9C-gmp-%EC%97%B0%EB%8F%99doubleclick%EC%97%90%EC%84%9C-%EC%A0%84%ED%99%98 h_01HP1PKNZN32TQYHGJNNM3JFVZ=impact-on-my-advertising-activity h_01HP4K2ZJW11BFSKNPRH7FA092=how-will-the-upcoming-change-affect-my-audiences h_01HQ2VJES04CYF4J8YBB4GQS73=further-information-and-contact-details" />
