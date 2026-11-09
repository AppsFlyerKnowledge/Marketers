---
title: 앱스플라이어와 엑솔라(Xsolla) 연동
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2024-03-25T06:20:28Z'
  edited_at: '2026-10-14T10:35:19Z'
  id: 23593013687185
  locale: ko
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ko/articles/23593013687185
---
> **한눈에 보기:** 엑솔라(Xsolla)는 앱스플라이어 연동 파트너로, 전통적인 앱 플랫폼의 외부에서 발생하는 결제 처리를 전문으로 하는 게임 커머스 기술 파트너입니다. 엑솔라와 앱스플라이어의 연동을 통해, 엑솔라는 웹샵(Web Shop)에서 이루어진 구매 및 수익을 자동으로 앱스플라이어에 전송할 수 있으며, 이를 통해 엑솔라 웹샵에서 이루어진 구매를 포함한 게임의 전체 ROAS 및 LTV를 확인할 수 있습니다.

<div id="important" />

> 🚧 **중요!**
>
> <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions#미디어-소스-제한">일부 미디어소스</Anchor>는 써드 파티와의 데이터 공유를 제한합니다. 따라서 포스트백 전송 설정에 관계없이 제한된 이벤트 포스트백은 이 파트너에게 전송되지 않습니다.

<div id="integration-types" />

## 연동 유형

엑솔라와의 연동 방법에는 두 가지가 있습니다.

* [기술 파트너 연동](#기술-파트너-연동-설정): 이 연동을 통해 엑솔라의 웹샵 구매 및 수익을 모바일 인앱 이벤트로 전송할 수 있으며 이는 즉, 앱 스토어 내 구매에만 국한되지 않고, 웹샵 수익까지 포함한 보다 확장된 수익 데이터를 바탕으로 모바일 앱 캠페인의 ROAS와 LTV를 향상시킬 수 있습니다.
* [PBA 웹 SDK 연동](#pba-웹-sdk-통합-설정하기): 이 연동을 통해 엑솔라는 웹샵에서 발생한 구매 및 수익을 웹 이벤트로 전송할 수 있으며, 이를 통해 앱스플라이어는 게임 유저를 웹샵으로 직접 유도하는 웹 캠페인의 성과를 측정할 수 있습니다.

**선행 조건:**

* 연동을 설정하기 전에 <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations#contact-details">파트너에게 연락</Anchor>하여 계정을 개설하세요.
* 연동이 제대로 작동하도록 하려면 고객 사용자 ID(CUID)를 앱스플라이어와 공유하고, 엑솔라와 공유된 사용자 ID가 일치하는지 확인해야 합니다. 이 과정을 통해 사용자가 엑솔라의 웹샵에 원활히 로그인할 수 있으며, 사용자 데이터가 앱스플라이어에 정확하게 전송됩니다.

<div id="setting-up-the-tech-partner-integration" />

## 기술 파트너 연동 설정

**연동 활성화 또는 편집 방법:**

1. **활성화 방법:** 앱스플라이어에서, 측면 메뉴에서 **협업** > **파트너 마켓플레이스**를 선택하세요.  
   **편집 방법**: 앱스플라이어의 사이드 메뉴에서 **협업** > **활성화된 연동**을 선택하세요.
2. 파트너를 검색하여 선택합니다.
3. **연동 설정**을 클릭하십시오. 연동 설정 페이지로 이동합니다.
4. **연동** 탭에서 연동할 앱을 선택하고 **파트너 활성화**를 켭니다.  
   **참고:** 파트너와 작업하는 동안 토글이 켜져<Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">(활성화됨)</Anchor> 있어야 합니다.
5. 아래 설명된 대로 관련 탭을 사용하여 설정을 완료하십시오.

설정 창에서는 **연동** 탭만 활용합니다.

파트너 설정 창 헤더에 대한 자세한 설명은 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">여기</Anchor>를 클릭하십시오.

<div id="integration-tab" />

<Accordion title="연동 탭">

<div id="activate-partner" />

#### 파트너 활성화

연동 탭에 처음으로 들어간 경우, **파트너 활성화** 토글을 켜서 연동을 설정해야 합니다. 엑솔라와 작업하는 동안, 토글이 켜져 있어야 합니다. <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">파트너 활성화</Anchor>에 대해 더 알아보십시오.

<div id="advanced-privacy" />

#### 고급 개인정보 보호

iOS 앱의 경우, <Anchor target="_blank" href="/marketers/ko/docs/apply-aggregated-advanced-privacy-framework">고급 개인정보 보호</Anchor> 토글이 나타납니다. 이 기능을 켜면 파트너와의 사용자 식별자 공유가 제한됩니다. 앱 설정에서 <Anchor target="_blank" href="/marketers/ko/docs/apply-aggregated-advanced-privacy-framework">집약형 프라이버시 강화(Aggregated Advanced Privacy )</Anchor> 토글을 켜면, **Advanced Privacy(iOS 14.5+ 이상의 경우)** 가 기본적으로 켜지고 잠깁니다.

<div id="default-postbacks" />

#### 기본 포스트백

앱스플라이어는 사용자 설치 후 기본 포스트백을 엑솔라에 전송합니다. 이 섹션을 통해 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#default-postbacks">다음과 같은 포스트백을 정의할 수 있습니다</Anchor>.

* **끄기:** 인스톨 포스트백은 엑솔라에 전송되지 않습니다.  
  **참고:** 엑솔라의 앱스플라이어와의 연동은 설치 포스트백을 전송할 필요가 없습니다. 따라서, 해당 포스트백을 꺼두는 것을 권장드립니다.
* **오가닉을 포함한 모든 미디어 소스:** 인스톨 포스트백은 파트너에 어트리뷰트된 이벤트와 오가닉 이벤트 모두에 대해 전송됩니다.

<Image align="center" alt="default_postbacks.png" src="https://files.readme.io/d78c2e8335e80c3a1b18b57ba3b2974ffd5622a3728c85b6ecd89569b48e905b-14963640623505.png" />

<div id="in-app-event-postbacks" />

#### 인앱 이벤트 포스트백

이 섹션에서는 포스트백을 통해 앱스플라이어 이벤트를 파트너와 매핑할 수 있습니다.

<Image align="center" alt="xsolla-af-login-3.jpg" src="https://files.readme.io/6b694389980e67023a506e0fc8c302f0512d12681e44d3d3a414c511d6dd83e4-26908967996177.jpg" />

1. **인앱 이벤트 포스트백**을 활성화하세요.
2. **이벤트 추가**를 클릭하여 목록에 SDK 또는 서버-투-서버 이벤트를 추가합니다.
3. 다음 파라미터를 완성하세요.

| 파라미터 이름 | 설명 |
| --- | --- |
| **AppsFlyer event** | 앱에 연동된 SDK 또는 서버 간 이벤트를 통해 앱스플라이어에서 수신하는 이벤트의 이름입니다.<br /><br />**참고:**<ul><li>엑솔라의 경우, 위 스크린샷에 표시된 대로 모바일 앱에 대한 사용자 로그인을 나타내는 `af_login` 이벤트 또는 기타 이벤트를 추가해야 합니다.</li><li>엑솔라는 너무 자주 발생하는 이벤트를 전송하지 않고, CUID(예: af\_app\_opened)를 포함하지 않도록 권장하고 있습니다. 연동 기능이 정상적으로 작동하지 않을 수 있기 때문입니다.</li></ul> |
| **mapped to partner event** | 엑솔라에 전송할 해당 이벤트 이름을 입력하세요. 엑솔라의 명명 규칙은 유연하며 이 필드에서 어떤 이름이든 사용할 수 있습니다. |
| **for users from** | 모든 파트너에게 기여된 이벤트 및 오가닉 이벤트에 대한 포스트백을 전송하려면, **오가닉을 포함한 모든 미디어 소스**를 선택하세요. |
| **포함** | <ul><li>**값 없음 및 수익 없음**: 파라미터 없이 이벤트 자체만 발송합니다 (값이나 수익).</li><li>**값 있음 및 수익 없음**: 수익 값을 **제외한** 모든 파라미터를 전송합니다.</li><li>**값 있음 & 수익 있음**: 이벤트에 수익 값이 포함되어 있다면, 수익 값을 **포함**한 모든 이벤트 파라미터를 전송해 주세요.</li></ul>참고: 엑솔라와 앱스플라이어의 연동에서는 값 또는 수익 데이터를 전송할 필요가 없습니다. 따라서 선택된 모든 옵션이 적용 가능합니다. |

4. **연동 저장**을 클릭합니다.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="어트리뷰션 링크 탭">

엑솔라에 대한 어트리뷰션 링크는 제공되지 않습니다.

</Accordion>

<div id="cost-tab" />

<Accordion title="비용 탭">

비용 데이터는 엑솔라와의 연동에서 지원되지 않습니다.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="광고 수익 탭">

광고 수익 데이터는 엑솔라와의 연동에서 지원되지 않습니다.

</Accordion>

<div id="permissions-tab" />

<Accordion title="권한 탭">

Xsolla에 대한 권한이 없습니다.

</Accordion>

<div id="setting-up-the-pba-web-sdk-integration" />

## PBA 웹 SDK 통합 설정하기

이 연동을 통해, PBA 대시보드 내에서 앱 성과 분석에 활용할 수 있는 LTV 데이터와 인사이트를 얻을 수 있습니다.

**연동을 설정하려면:**

1. **앱스플라이어에서 할일:** <Anchor target="_blank" href="/marketers/ko/docs/adding-an-app-to-appsflyer?query=adding%20an%20app">Xsolla 앱을 추가하세요</Anchor>. 플랫폼으로 <Anchor target="_blank" href="/marketers/ko/docs/adding-an-app-to-appsflyer#web-pba">Web (PBA)</Anchor>를 선택하고 다음 세부정보를 입력하세요:
   * 웹 앱 URL로 웹 샵 도메인을 사용하세요. 예를 들어, 웹 샵 도메인이 [www.webshop.com](http://www.webshop.com,)인 경우, 이를 웹 앱 URL로 사용하세요.
   * 앱 이름으로 원하는 앱 이름을 입력하세요. (아무 값이나 가능)
2. **앱스플라이어에서 할일:** <Anchor target="_blank" href="/marketers/ko/docs/pba-brand-bundles-and-settings#add-brand-bundle">엑솔라 번들을 추가</Anchor>할 때 다음 세부사항을 확인하세요:
   1. 1. 번들 이름으로 원하는 번들 이름을 입력하세요. (아무 값이나 가능)
      2. 이전 단계에서 생성한 웹 앱을 번들의 웹 앱으로 선택하세요.
3. **엑솔라에서 할 일:** 앱스플라이어를 엑솔라 퍼블리셔 계정과 연결하세요:
   1. <Anchor target="_blank" href="https://publisher.xsolla.com/">퍼블리셔 계정</Anchor>에서 프로젝트를 엽니다.
   2. 귀하의 사이트를 선택하고 **Configure를 클릭하세요.**
   3. **Site settings** 탭에서 **Apps** 섹션으로 이동하세요.
   4. **AppsFlyer** 블록에서, **Connect**를 클릭하세요.  
      <Image align="center" alt="xsolla-connect.jpg" src="https://files.readme.io/e29b2444769092cc6ea8e6b0fe0cf7753b65c6d5eef5770b920d5604f922d6c0-28569784464913.jpg" />
   5. **AppsFlyer Dev Key** 필드에 앱스플라이어 웹 개발 키를 입력하세요. [앱스플라이어에서 웹 개발 키를 찾는 방법](/docs/xsolla-integration-with-appsflyer#앱스플라이어에서-웹-개발-키-찾기)은 아래에서 확인하세요.
   6. **Connect**를 클릭하세요.

<div id="finding-the-web-dev-key-in-appsflyer" />

#### 앱스플라이어에서 웹 개발 키 찾기

1. **나의 앱** 페이지에서, **View brand bundles**를 클릭합니다.
2. 엑소랄 번들 행에서 복사 아이콘을 클릭합니다.

<Image align="center" alt="xsolla-brand-bundle2.jpg" src="https://files.readme.io/9cb6a9e872e482f7e426aea7e615afb1f91017c569e7cd67286cdb946d9d2445-26923253273361.jpg" />

<div id="identifying-xsollas-events-in-appsflyer" />

## 앱스플라이어에서 엑솔라의 이벤트 식별하기

<div id="tech-partner-s2s-integration" />

### 기술 파트너(S2S) 연동:

엑솔라는 앱스플라이어에 2개의 인앱 이벤트를 보냅니다:

* xsolla-billing-payment - 구매한 항목
* xsolla-billing-refund - 구매 환불한 황목

두 이벤트 모두 모바일 앱 인앱 이벤트의 일부입니다.

<div id="web-sdk-integration" />

### 웹 SDK 연동:

엑솔라는 특정 광고주 활동에 맞게 사용자 정의된 여러 웹 이벤트를 앱스플라이어에 보냅니다. 가장 중요한 항목은 'PURCHASE'라는 이름이며, 수익 정보를 포함하고 있습니다.  
엑솔라의 웹 이벤트는 PBA의 웹 어트리뷰션 및 “웹 이벤트” 데이터 락커 로리포트에 표시됩니다.

<div id="traits-and-limitations" />

<Accordion title="특징 및 제약 사항">

PC / 콘솔 지원 - 이 단계에서 엑솔라와 앱스플라이어의 연동은 PC / 콘솔 앱을 지원하지 않습니다.

</Accordion>

<div id="see-also" />

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="https://developers.xsolla.com/solutions/web-shop/analytics/appsflyer/">엑솔라 문서</Anchor>

<div data-zendesk-anchors="h_01HST42K52VQDWCWGP7TQVFB2X=%EC%A4%91%EC%9A%94 integration-types=%EC%97%B0%EB%8F%99-%EC%9C%A0%ED%98%95 h_01J3DB8MCNQKKKCV1M39KN7Q0H=%EC%97%B0%EB%8F%99-%EC%9C%A0%ED%98%95 setting-up-xsolla=%EA%B8%B0%EC%88%A0-%ED%8C%8C%ED%8A%B8%EB%84%88-%EC%97%B0%EB%8F%99-%EC%84%A4%EC%A0%95 h_01HST42K52JKQ70F7Y5PHDZAZ5=%EA%B8%B0%EC%88%A0-%ED%8C%8C%ED%8A%B8%EB%84%88-%EC%97%B0%EB%8F%99-%EC%84%A4%EC%A0%95 h_01HST42K52YZMTE3C2TBTK865M=integration-tab activate-partner=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 h_01HST42K52RCTSGRNRCJ1C70NP=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 advanced-privacy=%EA%B3%A0%EA%B8%89-%EA%B0%9C%EC%9D%B8%EC%A0%95%EB%B3%B4-%EB%B3%B4%ED%98%B8 h_01HST42K52BBJ6JS5KM0WCN6CF=%EA%B3%A0%EA%B8%89-%EA%B0%9C%EC%9D%B8%EC%A0%95%EB%B3%B4-%EB%B3%B4%ED%98%B8 default-postbacks=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01HST47F5BXWV5W8BNHS9M2MTN=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 inapp-event-postbacks=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01H9FKEAV3GG6X17X3NCCSWJAS=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01HST42K53GSMD91ACXY9DMP7S=attribution-link-tab h_01HST42K53D0PPXTM7MHBQ8P04=cost-tab h_01HST42K53YS8N6G2V0279F5GA=ad-revenue-tab h_01H9FKEAV3ZNKMZSG76B61H2AS=permissions-tab setting-up-the-pba-web-sdk-integration=pba-%EC%9B%B9-sdk-%ED%86%B5%ED%95%A9-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 h_01J3DEZZHDPSRZRXDV6FD4HY6Q=pba-%EC%9B%B9-sdk-%ED%86%B5%ED%95%A9-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 finding-the-web-dev-key-in-appsflyer=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%97%90%EC%84%9C-%EC%9B%B9-%EA%B0%9C%EB%B0%9C-%ED%82%A4-%EC%B0%BE%EA%B8%B0 h_01J3F247QEAFGRW7CEP941KZE9=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%97%90%EC%84%9C-%EC%9B%B9-%EA%B0%9C%EB%B0%9C-%ED%82%A4-%EC%B0%BE%EA%B8%B0 identifying-xsollas-events-in-appsflyer=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%97%90%EC%84%9C-%EC%97%91%EC%86%94%EB%9D%BC%EC%9D%98-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%8B%9D%EB%B3%84%ED%95%98%EA%B8%B0 h_01JMHXRGB60RVZ399FNHS18ZHZ=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%97%90%EC%84%9C-%EC%97%91%EC%86%94%EB%9D%BC%EC%9D%98-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%8B%9D%EB%B3%84%ED%95%98%EA%B8%B0 tech-partner-s2s-integration=%EA%B8%B0%EC%88%A0-%ED%8C%8C%ED%8A%B8%EB%84%88s2s-%EC%97%B0%EB%8F%99 h_01JMHXS5MZ7B781WNNVYMDGGFY=%EA%B8%B0%EC%88%A0-%ED%8C%8C%ED%8A%B8%EB%84%88s2s-%EC%97%B0%EB%8F%99 web-sdk-integration=%EC%9B%B9-sdk-%EC%97%B0%EB%8F%99 h_01JMHXX7VBPPS7GQ0VBGWRPT7X=%EC%9B%B9-sdk-%EC%97%B0%EB%8F%99 h_01JN0HXSEJV9JPAXGSBM7B3X7X=traits-and-limitations h_01J1C78W0MP8KXFB4251FKWJBX=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
