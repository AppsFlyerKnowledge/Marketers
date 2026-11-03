---
title: Awin 캠페인 구성
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
  created_at: '2023-09-13T11:50:38Z'
  edited_at: '2026-10-14T10:32:12Z'
  id: 18532554968849
  locale: ko
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/ko/articles/18532554968849
---
> **한눈에 보기:** Awin (affiliatewindow\_int)는 광고주가 UA 및 리타겟팅 캠페인을 실행할 수 있도록 하는 통합 파트너입니다. Awin의 마케팅 플랫폼은 상인(광고주)과 제휴사(퍼블리셔)를 연결하는 데 도움을 줍니다.

![awin icon.png](https://files.readme.io/2a7f22084586fec820c0bfab7f3a256259c43d37f14d6fed8e8db3d2e9905947-18533392495377.png)

## 파트너 활성화

**전제 조건:** 연동을 설정하기 전에 <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations#contact-details">파트너에게 연락</Anchor>하여 계정을 개설하세요.

**연동 활성화 또는 편집 방법:**

1. **활성화 방법:** 앱스플라이어에서의 사이드 메뉴에서 **협업** > **파트너 마켓플레이스**를 선택하세요.  
   **편집 방법:** 앱스플라이어의 사이드 메뉴에서 **협업**> **활성화된 연동**을 선택합니다.
2. 파트너를 검색하고 선택합니다.
3. **연동 설정**을 클릭합니다. 연동 설정 페이지로 이동합니다.
4. **연동** 탭에서 연동할 앱을 선택하고 **파트너 활성화**를 켭니다.  
   **참고:** 파트너와 협력하는 동안 토글은 반드시 켜져<Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">(활성화)</Anchor> 있어야 합니다.
5. 아래 설명된 대로 관련 탭을 사용하여 설정을 완료하십시오.

## Awin 설정

Awin과의 통합은 클릭스루 어트리뷰션을 지원합니다.

구성 창에는 다음과 같은 탭이 포함되어 있습니다: 연동, 어트리뷰션 링크, 비용, 광고 수익, 권한. Avow GmbH의 경우 사용 가능한 탭은 통합, 저작자 표시 링크 및 권한입니다.

> 📘 **참고사항**
>
> * 일부 설정은 iOS와 안드로이드 기기마다 다릅니다.
> * <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner">파트너 연동 설정</Anchor>에 대해 더 알아보세요.

### 전제 조건

연동을 설정하기 전에 <Anchor target="_blank" href="https://help.awin.com/docs/appsflyer">Awin 문서에</Anchor>지정된 대로 SDK에서 필요한 "커미션 그룹" 매개변수를 구현해야 합니다.

<div id="integration-tab" />

<Accordion title="연동 탭">

**연동** 탭에는 아래 설명된 여러 섹션이 포함되어 있습니다.

#### 파트너 활성화

연동을 구성하려면 먼저 **파트너 활성화** 토글을 <Anchor target="_blank" href="/marketers/ko/docs/amazon-ads-campaign-configuration#파트너-활성화">켜야</Anchor> 합니다. 파트너를 활성화 및 비활성화하는 방법에 대해 알아보세요. 추가 정보는 <Anchor target="_blank" href="https://developer.awin.com/docs/appsflyer">Awin 통합 페이지</Anchor>를 참조할 수 있습니다.

#### 프라이버시 강화 모드

iOS 앱의 경우: 포스트백 및 <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions">리포트</Anchor>를 통해 파트너와 공유된 데이터에 대한 제어 권한은 **고급 개인정보 보호(iOS 14.5 이상)** 토글 상태에 따라 달라집니다.

| 프라이버시 강화 모드: 켜기 | 프라이버시 강화 모드: 끄기 |
| --- | --- |
| 포스트백은 파트너에 어트리뷰션된 이벤트에 대해서만 전송됩니다. | 포스트백은 귀사의 설정에 따라 전송됩니다.<ul><li>**오가닉을 포함한 모든 미디어 소스**</li><li>**이 파트너사만**</li></ul> |
| 포스트백은 <Anchor target="_blank" href="/partners/ko/docs/advanced-privacy-guide-postback-macros-for-ad-networks">고급 개인정보 보호 템플릿</Anchor>에 따라 전송됩니다. |  |
| <Anchor target="_blank" href="/marketers/ko/docs/apply-aggregated-advanced-privacy-framework">집계된 익명 데이터</Anchor>만 파트너와 공유되며, 유저 수준 데이터(디바이스 ID)는 공유되지 않습니다. |  |

#### 일반 설정

**Awin 광고주 ID**

Awin 판매자 ID를 추가합니다.

> 📘 **참고**
>
> 여러 상인 ID가 있는 경우, 주요 ID를 연결하십시오.

#### 기본 포스트백

인스톨 포스트백은 이 파트너에게만 전송됩니다.

#### 인앱 이벤트 설정

**Awin 광고주 ID**

Awin 판매자 ID를 추가합니다.

#### 인앱 이벤트 포스트백

포스트백을 통해 전송된 Awin 이벤트와 인앱 이벤트 매핑을 구성합니다.

1. **인앱 이벤트 포스트백**을 활성화하세요.
2. **이벤트 추가**를 클릭하여 목록에 SDK 또는 서버-투-서버 이벤트를 추가하세요. 다음 표는 작성해야 할 필드를 설명합니다.

| 파라미터 이름 | 설명 |
| --- | --- |
| **앱스플라이어 이벤트** | 앱스플라이어가 앱에 연동된 SDK 또는 서버 간 이벤트에서 수신한 이벤트의 이름입니다.<br />**팁**: 찾고 있는 이벤트가 없나요?<ul><li>논오가닉 설치된 디바이스에서 이벤트를 활성화하고 다시 확인하세요.</li><li>**앱스플라이어 이벤트**에 입력한 다음 **사용자 지정 생성**을 클릭합니다. <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#커스텀-이벤트">커스텀 이벤트 매핑</Anchor>에 대해 더 알아보세요.</li></ul> |
| **파트너 이벤트에 매핑** | 파트너 측에서 정의한 각 이벤트의 고유한 이름 또는 ID입니다. 가능한 매핑 구성은 다음과 같습니다.<ul><li>**텍스트 필드:** 파트너로부터 해당 이벤트 ID를 받으세요.</li><li>**드롭다운 상자:** 가장 적합한 사전 정의된 앱스플라이어 이벤트를 선택합니다.</li><li>**그대로**: 이름 매핑 없이 이벤트를 있는 그대로 전송합니다.</li></ul> |
| **사용자용** | **이 파트너만 해당:** 이 파트너만 해당: 인앱 이벤트 포스트백 은 이벤트가 이 파트너에게 어트리뷰션된 경우, 즉 이벤트를 수행한 사용자가 이 파트너로부터 온 경우에만종료할 수 있습니다. |
| **포함** | <ul><li>**데이터 없음(기본값)**: 이벤트 값 없이 이벤트 자체만 전송합니다.</li><li>**가치와 수익**: 수익 값(이벤트에 존재하는 경우)을 **포함한** 모든 이벤트 파라미터를 발송합니다.</li><li>**수익 없는 값**: 수익 값을 **제외한** 모든 파라미터를 발송합니다.</li></ul> |

3. [선택 사항] 이벤트에 대한 <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#조건부-인앱-이벤트-포스트백">조건을 설정</Anchor>하려면 **조건 추가altconditional-iae-postbacks-icon.pngalt아이콘을 클릭하세요.**
4. 필요한 경우 **인앱 이벤트 포스트백 기간**을 설정합니다(<Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#인앱-이벤트-포스트백-기간">인앱 이벤트 포스트백 기간 구성</Anchor>에 대해 자세히 알아보세요).
5. **연동 저장**을 클릭하세요.
6. [선택 사항] 연동을 저장한 후 구성 페이지에 남아 있는 동안 파트너와 더 많은 귀사의 앱을 연동할 수 있습니다.
   1. 왼쪽 상단 모서리에서 파트너 이름 아래에 있는 앱 이름을 클릭하여 앱 목록을 엽니다.
   2. 드롭다운 목록에서 다른 앱을 선택합니다.
   3. 선택한 앱에 대해 <Anchor target="_blank" href="/marketers/ko/docs/amazon-ads-campaign-configuration#integration-tab">연동 단계</Anchor>를 반복합니다.

> 📘 **참고사항**
>
> iOS 앱의 경우: 포스트백 및 <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions">리포트</Anchor>를 통해 파트너와 공유된 데이터에 대한 제어 권한은 **고급 개인정보 보호(iOS 14.5 이상)** <Anchor target="_blank" href="/marketers/ko/docs/tiktok-for-business-advanced-srn-integration-setup#advanced-privacy">토글 상태</Anchor>에 따라 달라집니다.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="어트리뷰션 링크 탭">

UA 및 리타게팅 캠페인 모두에 대한 특정 캠페인, 광고 세트 또는 단일 광고를 제공하기 위해 어트리뷰션 링크를 생성하고 저장한 후 파트너에게 보냅니다. 단일 플랫폼 링크 또는 <Anchor target="_blank" href="/marketers/ko/docs/onelink-guide">원링크</Anchor>를 사용할 수 있습니다. <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters">어트리뷰션 링크 구조 및 파라미터에 대해 더 알아보세요</Anchor>. 어트리뷰션 링크를 생성하려면 다음 지침을 따르십시오.

</Accordion>

<div id="cost-tab" />

<Accordion title="비용 탭">

Awin에 대한 비용 데이터는 사용할 수 없습니다.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="광고 수익 탭">

Awin의 경우 광고 수익을 사용할 수 없습니다.

</Accordion>

<div id="permissions-tab" />

<Accordion title="권한 탭">

Awin이 데이터에 액세스하고 다양한 작업을 수행할 수 있도록 부여할 권한을 선택합니다.

> 📘 **참고사항**
>
> * 권한 토글이 켜진 상태에서 연동이 <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">비활성화</Anchor>되면 권한이 계속 부여됩니다.
> * <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#permissions-tab">권한 부여</Anchor>에 대해 자세히 알아보십시오.

</Accordion>

## OneLink를 사용한 딥링킹(Deep Linking) 및 디퍼드 딥링킹(Deferred Deep Linking)

AWIN은 고객에게 분석 데이터를 제공할 수 있도록 플랫폼에서 사용되는 모든 링크를 래핑합니다. 즉, 사용자를 최종 목적지로 보내기 전에 링크가 AWIN 사이트로 리디렉션됩니다. <Anchor target="_blank" href="https://www.appsflyer.com/blog/mobile-marketing/universal-links-app-links/#:~:text=%231%3A%20Link%20wrapping%20and%20Universal%20Links">링크 래핑에 대해 자세히 알아보세요</Anchor>.  
플랫폼으로서의 AWIN은 URI 스킴을 지원하지만 딥링킹의 iOS 유니버설 링크 및 Android 앱 링크 메서드 처리를 **지원하지 않습니다** . 이는 AWIN 내에서 사용되는 모든 링크에 적용됩니다.

AWIN을 통해 원링크로 딥링킹하는 방법:

* <Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users">URI 스킴으로 원링크 URL 설정</Anchor>

> 📘 **참고사항**
>
> iOS 앱의 경우, 딥 링크 <Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users">URI 스킴</Anchor>을 활성화하기 위해 OneLink URL에서 `af_force_deeplink=true` 매개변수를 사용하십시오.

<div data-zendesk-anchors="activate-partner=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 01H88VAJH3B5ESK12D3ATMMVZ8=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 setting-up-amazon-dsp-integration=awin-%EC%84%A4%EC%A0%95 01H88VAJH3VENKYVRQY5RXN63P=awin-%EC%84%A4%EC%A0%95 01H88VAJH3BYZSXQGGZZJQ9N0C=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD prerequisite=%EC%A0%84%EC%A0%9C-%EC%A1%B0%EA%B1%B4 h_01HFPEEW4FXS9AFQTTEF2ZBDZW=%EC%A0%84%EC%A0%9C-%EC%A1%B0%EA%B1%B4 01H88VAJH3VZ4GPVE7XXMKTZ2P=integration-tab activate-partner::b746d215=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94-1 01H88VAJH34GP7FK1KTJGRDPM7=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94-1 advanced-privacy=%ED%94%84%EB%9D%BC%EC%9D%B4%EB%B2%84%EC%8B%9C-%EA%B0%95%ED%99%94-%EB%AA%A8%EB%93%9C 01H88VAJH3G5FAR7RRNDEPNGME=%ED%94%84%EB%9D%BC%EC%9D%B4%EB%B2%84%EC%8B%9C-%EA%B0%95%ED%99%94-%EB%AA%A8%EB%93%9C general-settings=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 01H88VAJH3F2FJK5YP3M2V7RWD=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 h_01K4VVB00RYB0XRANWQ29M6P36=%EC%B0%B8%EA%B3%A0 default-postbacks=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 01H88VAJH3WE9Z0971WMBRBJRS=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 inapp-event-settings=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95 h_01HA77JYAR06HA5FZGSRQJATHF=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95 inapp-event-postbacks=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 01H88VAJH3AS37MVF75GANWX4B=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 01H88VAJH36MYZ9W1YPWA92Z1Z=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD-1 01H88VAJH31GZ4KAY280ZRB8MA=attribution-link-tab 01H88VAJH3RM95V449B6DF8B4D=cost-tab 01H88VAJH3A2Q0CZXQQZMW6YRC=ad-revenue-tab 01H88VAJH30TCC574W2DH7R2A2=permissions-tab 01H88VAJH3XYP81GTFBWDBXECP=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD-2 deep-linking-and-deferred-deep-linking-using-onelink=onelink%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%9C-%EB%94%A5%EB%A7%81%ED%82%B9deep-linking-%EB%B0%8F-%EB%94%94%ED%8D%BC%EB%93%9C-%EB%94%A5%EB%A7%81%ED%82%B9deferred-deep-linking h_01HA77Q9RWZ3FRE5KEN854ZZ78=onelink%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%9C-%EB%94%A5%EB%A7%81%ED%82%B9deep-linking-%EB%B0%8F-%EB%94%94%ED%8D%BC%EB%93%9C-%EB%94%A5%EB%A7%81%ED%82%B9deferred-deep-linking h_01HA78QWQVXEWHPEQE6XWBB64M=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD-3" />
