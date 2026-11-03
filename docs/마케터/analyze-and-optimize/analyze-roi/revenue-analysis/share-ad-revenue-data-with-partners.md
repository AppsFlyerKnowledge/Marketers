---
title: UA 파트너와 광고 수익 데이터를 공유하세요.
metadata:
  keywords:
    - Premium
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2024-04-11T11:04:45Z'
  edited_at: '2026-10-14T10:30:00Z'
  id: 24100803679761
  locale: ko
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/ko/articles/24100803679761
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **한눈에 보기:** UA 파트너가 미디에이션 네트워크로부터 광고 수익 정보를 수신하도록 허용하여 UA 캠페인을 최적화할 수 있습니다. **참고**: ROI360 Advanced 구독이 필요합니다.

## UA 파트너와 광고 수익 데이터 공유하기

사용자 획득을 담당하는 애드 네트워크가 미디에이션 네트워크로부터 광고 수익 데이터를 수신하도록 허용할 수 있습니다.  그런 다음 UA 파트너는 정보를 사용하여 UA 캠페인을 최적화할 수 있습니다.

UA 파트너는 다음 중 하나를 통해 광고 수익 데이터를 수신할 수 있습니다.

* 광고 네트워크용 UA 신호
* 광고 네트워크에 대한 광고 수익 포스트백

다음 표에서는 2가지 광고 수익-데이터 공유 솔루션을 비교합니다.

| 광고 수익 데이터 공유 솔루션 | 데이터 최신성 | 사례 | 필수 연동 유형 | 필수 구독 유형 |
| --- | --- | --- | --- | --- |
| UA 신호 | 일일 | 정확하고 완전한 데이터로 D3 및 D7 최적화에 일반적으로 사용됩니다. | <ul><li>광고 노출 레벨 또는 디바이스 레벨</li><li>둘 다 설정된 경우, 디바이스 레벨 데이터가 전송됩니다.</li></ul> | ROI360 고급 기능 |
| 포스트백 | 실시간 | D0 및 D1 최적화에 일반적으로 사용되는 최신 데이터입니다. | 노출 수준 | ROI360 고급 기능 |

## 절차

<div id="ua-signals-for-ad-networks" />

<Accordion title="광고 네트워크용 UA 신호">

UA 신호를 수신할 수 있는 광고 네트워크와 협력할 수 있습니다. 즉, 사용자 획득을 담당하는 광고 네트워크는 광고 수익에 관한 미디에이션 네트워크의 데이터를 수신하고 이를 고객의 UA 캠페인을 최적화하는 데 사용할 수 있습니다.

**UA 신호를 애드 네트워크에 보내려면**:

1. 앱스플라이어의 사이드 메뉴에서 **협업** > **활성화된 연동**을 선택합니다.
2. 연동 파트너를 선택하세요.
3. **연동 탭**으로 이동합니다.
4. **파트너 활성화**가 켜져 있는지 확인합니다. 아닌 경우 데이터를 공유할 수 없습니다.
5. **권한** 탭으로 이동합니다.
6. **애드 네트워크 권한**을 켜세요.
7. 광고 수익 로데이터(UA 신호)에 액세스
8. 전송 **옵션**에서 이 파트너의 광고 수익(**이 파트너만 해당**)에 대한 데이터를 전송할지 아니면 모든 미디어소스의 광고 수익(**오가닉을 포함한 모든 미디어소스**)에 대한 데이터를 전송할지 선택합니다.   **참고**: 오가닉 포함 모든 매체 소스가 선택되면 다른 파트너의 포스트백에는 어트리뷰션 데이터가 포함되지 않습니다.
9. 설정 **저장**을 클릭합니다.
10. 애드 네트워크에 문의하세요.
    1. 권한을 부여받았음을 알리세요.
    2. 그들에게 보고서를 수신하기 위해 <Anchor target="_blank" href="/partners/ko/docs/ad-revenue-signals-for-ua-ad-networks#enable-the-ad-revenue-report">이들의 지침을 따르라고</Anchor> 하십시오.

**UA 광고 네트워크에 UA 신호를 보낼 수 있는 중재 파트너 목록:**

* Applovin Max
* Google AdMob
* Appodeal
* Chartboost
* Fyber
* Tapdaq
* Topon
* Unity
* Unity LevelPlay 중재(이전의 아이언소스(ironSource))
* Admost
* Tradplusad
* Yandex
* 사용자정의 미디에이션

</Accordion>

<div id="ad-revenue-event-postbacks-for-ad-networks" />

<Accordion title="광고 네트워크의 광고 수익 이벤트 포스트백">

광고 네트워크에 대한 광고 수익 포스트백을 구성할 수 있습니다. 즉, 사용자 획득을 담당하는 광고 네트워크는 광고 수익에 관한 미디에이션 네트워크의 데이터를 수신하고 이를 고객의 UA 캠페인을 최적화하는 데 사용할 수 있습니다.

> 🚧 **중요!**
>
> * 애드 네트워크에 대한 광고 수익 이벤트 포스트백은 SDK를 통한 노출 수준과 SDK를 통한 노출 수준, S2S API를 통한 기기 수준의 광고 수익 연동 <Anchor target="_blank" href="/marketers/ko/docs/roi360-guide-ad-revenue-attribution#integration-types-for-ad-revenue-attribution">유형</Anchor>에서만 작동합니다. 즉, 개발사가 <Anchor target="_blank" href="/marketers/ko/docs/integrate-the-roi360-ad-revenue-sdk-api">앱스플라이어 광고 수익 SDK API</Anchor>를 연동해야 합니다.
> * 특정 파트너에게 광고 수익 포스트백을 보낼 수 있지만, 연동을 시작하기 전에 파트너가 데이터를 어떻게 사용하는지 확인해야 합니다.

광고 수익 이벤트 포스트백을 설정하는 방법:

1. <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations#manage-existing-integrations">마켓플레이스</Anchor> 또는 **콜라보레이트**  >활성  연동 페이지에서 파트너를 검색하고 선택합니다.
2. **연동** 탭에서 아래로 스크롤하여 **인앱이벤트 포스트백**을 켭니다.
3. 앱스플라이어 이벤트 af\_ad\_revenue를 선택합니다. **참고**: 일부 애드 네트워크 연동에는 **모든 이벤트 선택** 옵션이 있습니다. af\_ad\_revenue 이벤트를 제외하므로 이 옵션을 사용하지 마십시오.
4. 다음과 같이 UA 애드 네트워크 이벤트에 연결합니다.

| UA 애드 네트워크 | af\_ad\_revenue를 매핑할 이벤트 | 스크린샷 |
| --- | --- | --- |
| ironSource | 광고 수익 | [![](https://files.readme.io/f5f6987d04e98536fb5dd6925fd9f95a478ee96fbffe8c1808f333ecca073963-51912485192465.png)](https://files.readme.io/f5f6987d04e98536fb5dd6925fd9f95a478ee96fbffe8c1808f333ecca073963-51912485192465.png) |
| Unity Ads | ad\_revenue |  |
| Moloco | 매핑 필요 없음 |  |
| Mintegral | 매핑 필요 없음 |  |
| Smadex | 매핑 필요 없음 |  |
| Mistplay | 매핑 필요 없음 |  |
| Meta ads | fb\_mobile\_purchase—iOS 앱용  <br />혹은  <br />Adimpression—안드로이드 앱용  <br />자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/meta-ads-in-app-event-mapping#mapping-ad-revenue-data-for-campaign-optimization">여기</Anchor>를 참조하세요. | [<Image alt="revenue-mapping-meta2.jpg" src="https://files.readme.io/9ec143cbcb622dec2aa0081812e41c0c7586b3583f4da7e57d71dffcb2d68a79-29375912802193.jpg" width="230px" />](https://files.readme.io/9ec143cbcb622dec2aa0081812e41c0c7586b3583f4da7e57d71dffcb2d68a79-29375912802193.jpg) |
| TikTok for Business - Advanced SRN | 노출수준 광고수익 |  |
| Unity의 Aura | ad\_revenue |  |
| Digital Turbine | ad\_revenue | [![](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png)](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png) |
| Digital Turbine의 SingleTap | ad\_revenue |  |
| Persona.ly RTB | ad-revenue | [![](https://files.readme.io/bc924575f7cc5f4c7fafe3683ae51dcbf3240b9bc4cf22f9d6916cef7a9877f9-24658308681873.png)](https://files.readme.io/bc924575f7cc5f4c7fafe3683ae51dcbf3240b9bc4cf22f9d6916cef7a9877f9-24658308681873.png) |
| Bigo | ad\_watch | [![](https://files.readme.io/cd3015a60f623ac1d7c563c2b541dfe487006b7babf9b51050f209b70c4a41a4-24658241206929.png)](https://files.readme.io/cd3015a60f623ac1d7c563c2b541dfe487006b7babf9b51050f209b70c4a41a4-24658241206929.png) |
| Appier | 매핑 필요 없음 |  |
| Bidease | 매핑 필요 없음 |  |
| MAF | 매핑 필요 없음 |  |

5. 이벤트에 대해 보내기 옵션을 선택하는 **사용자 from**:
   * 해당 파트너 이 이벤트가 이 파트너에 어트리뷰션된 경우에만 포스트백을 발송합니다. 즉, 유저가 이 파트너에서 온 경우입니다.
   * 오가닉을 포함한 모든 미디어 소스: 모든 파트너에게 할된 이벤트와 오가닉 이벤트에 대해 포스트백을 전송합니다. 즉, 해당 이벤트를 수행한 사용자가 어느 미디어 소스에서 유입되었는지에 관계없이 포함됩니다. **참고**: 오가닉 포함 모든 매체 소스가 선택되면 다른 파트너의 포스트백에는 어트리뷰션 데이터가 포함되지 않습니다.
6. **연동 저장**을 클릭하세요.

**UA 광고 네트워크에 노출 수준 광고 수익 이벤트를 보낼 수 있는 중재 파트너 목록:**

* Applovin Max
* Google AdMob
* Appodeal
* Chartboost
* Fyber
* Tapdaq
* Topon
* Unity
* ironSource
* Admost
* Tradplusad
* Yandex
* 사용자정의 미디에이션

</Accordion>

## 추가 정보

<div id="list-of-ua-ad-networks-that-can-receive-ua-signals-and-postbacks" />

<Accordion title="UA 신호 및 포스트백을 수신할 수 있는 UA 광고 네트워크 목록">

다음 표에는 미디에이션 네트워크로부터 광고 수익 UA 신호와 포스트백을 수신할 수 있는 광고 네트워크가 나열되어 있습니다.

<table><colgroup><col/><col/><col/></colgroup><thead><tr><th rowspan="2">애드 네트워크 파트너:</th><th colspan="2">지원</th></tr><tr><th>UA 신호</th><th>포스트백</th></tr></thead><tbody><tr><td>Aarki</td><td>-</td><td><span>✓</span></td></tr><tr><td>AdAction</td><td><span>✓</span></td><td>-</td></tr><tr><td>Adaction3</td><td>-</td><td><span>✓</span></td></tr><tr><td>Adamobi</td><td><span>✓</span></td><td>-</td></tr><tr><td>Adikteev (Trademob)</td><td><span>✓</span></td><td>-</td></tr><tr><td>Adjoe</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Adonco</td><td><span>✓</span></td><td>-</td></tr><tr><td>Adshow</td><td><span>✓</span></td><td>-</td></tr><tr><td>Almedia GmbH</td><td>-</td><td><span>✓</span></td></tr><tr><td>앱 성장</td><td>-</td><td><span>✓</span></td></tr><tr><td>Appier</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Apprainbow</td><td><span>✓</span></td><td>-</td></tr><tr><td>Unity의 Aura</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Avow OEM</td><td> </td><td><span>✓</span></td></tr><tr><td>ayeT-Studios</td><td>-</td><td><span>✓</span></td></tr><tr><td>Betop</td><td><span>✓</span></td><td>-</td></tr><tr><td>Bidswave</td><td><span>✓</span></td><td>-</td></tr><tr><td>Bidease</td><td>-</td><td><span>✓</span></td></tr><tr><td>Bigo</td><td>-</td><td><span>✓</span></td></tr><tr><td>Brandscale</td><td><span>✓</span></td><td>-</td></tr><tr><td>버즈빌</td><td>-</td><td><span>✓</span></td></tr><tr><td>Chameleostudios</td><td><span>✓</span></td><td>-</td></tr><tr><td>Chartboost</td><td><span>✓</span></td><td>-</td></tr><tr><td>이탈</td><td>-</td><td><span>✓</span></td></tr><tr><td>Datawave</td><td><span>✓</span></td><td>-</td></tr><tr><td>Digital Turbine</td><td>-</td><td><span>✓</span></td></tr><tr><td>DLab</td><td><span>✓</span></td><td>-</td></tr><tr><td>Ecomonline</td><td><span>✓</span></td><td>-</td></tr><tr><td>Etusdigital</td><td><span>✓</span></td><td>-</td></tr><tr><td>Exmox</td><td>-</td><td><span>✓</span></td></tr><tr><td>Fluent</td><td><span>✓</span></td><td>-</td></tr><tr><td>Foregon</td><td><span>✓</span></td><td>-</td></tr><tr><td>GNA Company</td><td><span>✓</span></td><td>-</td></tr><tr><td>Greedygame</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Happimobi</td><td><span>✓</span></td><td>-</td></tr><tr><td>Hybrid</td><td><span>✓</span></td><td>-</td></tr><tr><td>Inflecto</td><td><span>✓</span></td><td>-</td></tr><tr><td>Irismedia</td><td><span>✓</span></td><td>-</td></tr><tr><td>ironSource</td><td>-</td><td><span>✓</span></td></tr><tr><td>카스키크(Kashkick)</td><td>-</td><td><span>✓</span></td></tr><tr><td>쿼이 광고</td><td>-</td><td><span>✓</span></td></tr><tr><td>레이쿠나</td><td>-</td><td><span>✓</span></td></tr><tr><td>Lambadapp</td><td><span>✓</span></td><td>-</td></tr><tr><td>Leadidadmonster</td><td><span>✓</span></td><td>-</td></tr><tr><td>Lifestreet</td><td><span>✓</span></td><td>-</td></tr><tr><td>Liftoff</td><td><span>✓</span></td><td>-</td></tr><tr><td>MAF</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Melodong</td><td><span>✓</span></td><td>-</td></tr><tr><td>Meta ads</td><td><span>-</span></td><td><span>✓</span></td></tr><tr><td>미니클립</td><td>-</td><td><span>✓</span></td></tr><tr><td>Mintegral</td><td>-</td><td><span>✓</span></td></tr><tr><td>Mistplay</td><td><span>-</span></td><td><span>✓</span></td></tr><tr><td>Mobrand</td><td><span>✓</span></td><td>-</td></tr><tr><td>Moloco</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Motive</td><td><span>✓</span></td><td>-</td></tr><tr><td>Mpnd</td><td><span>✓</span></td><td>-</td></tr><tr><td>Msla</td><td><span>✓</span></td><td>-</td></tr><tr><td>Muvmobile</td><td><span>✓</span></td><td>-</td></tr><tr><td>뉴스Break</td><td>-</td><td><span>✓</span></td></tr><tr><td>Nexamob</td><td><span>✓</span></td><td>-</td></tr><tr><td>Nftdroper</td><td><span>✓</span></td><td>-</td></tr><tr><td>Nsofmedia</td><td><span>✓</span></td><td>-</td></tr><tr><td>Performadlive</td><td><span>✓</span></td><td>-</td></tr><tr><td>Persona.ly RTB</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Pitatroas</td><td><span>✓</span></td><td>-</td></tr><tr><td>플레이그랩</td><td>-</td><td><span>✓</span></td></tr><tr><td>Rebornads</td><td><span>✓</span></td><td>-</td></tr><tr><td>RTBhouse</td><td><span>✓</span></td><td>-</td></tr><tr><td>Runfuns</td><td><span>✓</span></td><td>-</td></tr><tr><td>SayGames LTD</td><td>-</td><td><span>✓</span></td></tr><tr><td>Scmobi</td><td><span>✓</span></td><td>-</td></tr><tr><td>Shalltry</td><td><span>✓</span></td><td>-</td></tr><tr><td>Shareit</td><td><span>✓</span></td><td>-</td></tr><tr><td>Digital Turbine의 SingleTap</td><td>-</td><td><span>✓</span></td></tr><tr><td>Smadex</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Surgex</td><td>-</td><td><span>✓</span></td></tr><tr><td>Tapjoy</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Targetmedia</td><td><span>✓</span></td><td>-</td></tr><tr><td>TaurusX</td><td>-</td><td><span>✓</span></td></tr><tr><td>Thepurpleline</td><td><span>✓</span></td><td>-</td></tr><tr><td>TikTok for Business</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Trade Desk</td><td> </td><td><span>✓</span></td></tr><tr><td>Transsion</td><td>-</td><td><span>✓</span></td></tr><tr><td>Truemoney</td><td><span>✓</span></td><td>-</td></tr><tr><td>Tyrads</td><td>-</td><td><span>✓</span></td></tr><tr><td>Unity Ads</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Unity CTV</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Voodoo</td><td>-</td><td><span>✓</span></td></tr><tr><td>벙글</td><td><span>✓</span></td><td>-</td></tr><tr><td>VYBS</td><td>-</td><td><span>✓</span></td></tr><tr><td>Yandex</td><td><span>✓</span></td><td>-</td></tr><tr><td>Yeahmobi</td><td><span>✓</span></td><td>-</td></tr><tr><td>YouAppi</td><td>-</td><td><span>✓</span></td></tr><tr><td>Xiaomi Global</td><td>-</td><td><span>✓</span></td></tr><tr><td>YSO 네트워크</td><td>-</td><td><span>✓</span></td></tr><tr><td>Z2A Digital</td><td><span>✓</span></td><td>-</td></tr><tr><td>Zoyo</td><td><span>✓</span></td><td>-</td></tr></tbody></table>

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="특징 및 제한 사항">

| 특징 | 설명 |
| --- | --- |
| 전환 유형 | <ul><li>UA 신호는 모든 전환 유형에 대한 데이터를 지원합니다. 인스톨, 리어트리뷰션, 리인게이지먼트 및 리인스톨 수</li><li>포스트백은 인스톨에 대한 데이터만 지원합니다.</li></ul> |
| 에이전시 포스트백 권한 | 에이전시는 광고 수익 포스트백을 설정할 수 없습니다. |

</Accordion>

<div data-zendesk-anchors="about-sharing-ad-revenue-data-with-ua-partners=ua-%ED%8C%8C%ED%8A%B8%EB%84%88%EC%99%80-%EA%B4%91%EA%B3%A0-%EC%88%98%EC%9D%B5-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B3%B5%EC%9C%A0%ED%95%98%EA%B8%B0 h_01HV6CW4SAF23TT5XZF1SGPVQH=ua-%ED%8C%8C%ED%8A%B8%EB%84%88%EC%99%80-%EA%B4%91%EA%B3%A0-%EC%88%98%EC%9D%B5-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B3%B5%EC%9C%A0%ED%95%98%EA%B8%B0 procedures=%EC%A0%88%EC%B0%A8 h_01HVEEMGMEWDKAXVNHR8C0AHPQ=%EC%A0%88%EC%B0%A8 01H8V10BKM7MMM63JHGCF2DYMC=ua-signals-for-ad-networks 01H8V10BKMED8J73G22CFVH6GJ=ad-revenue-event-postbacks-for-ad-networks h_01HFAAC1J9KQ6ZNSCRSRKE9GA3=%EC%A4%91%EC%9A%94 additional-information=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01HVE6AREZBPH751WFW70Q7X66=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01HVE6AREZBCAJPVYSF43JWNJZ=list-of-ua-ad-networks-that-can-receive-ua-signals-and-postbacks h_01HTM0KJA8TB44TSV5N2151N4N=traits-and-limitations" />
