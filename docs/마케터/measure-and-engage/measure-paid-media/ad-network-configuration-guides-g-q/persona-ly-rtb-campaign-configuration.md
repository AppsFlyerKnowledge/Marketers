---
title: RTB 캠페인 구성 Persona.ly
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
  created_at: '2023-09-20T07:13:43Z'
  edited_at: '2026-10-14T10:36:50Z'
  id: 18699025653265
  locale: ko
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/ko/articles/18699025653265
---
> **한눈에 보기:**

<Image alt="persona.ly_logo.png" src="https://files.readme.io/b0dacbdc4c2e884610a040b5049a1410a88214f8275320163764bcf09f90305b-18699636413969.png" width="234px" />

## Persona.ly RTB 설정

**전제 조건:** 연동 설정 전에 <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations#contact-details">파트너에게 연락</Anchor>하여 계정을 개설하세요.

**연동 활성화 또는 편집 방법:**

1. To activate:연동 활성화 방법: 앱스플라이어의 사이드 메뉴에서협업**>**파트너 마켓플레이스**를 선택합니다.  
   **편집 방법:** 앱스플라이어의 측면 메뉴에서 **협업** > 활성화된 연동을 선택합니다.**
2. 새로운 파트너 연동을 검색하여 선택하세요.
3. **연동 설정**을 클릭하세요. **활성화된 연동** 설정 페이지로 이동합니다.
4. **연동** 탭에서 **파트너 활성화**를 켭니다.  
   **참고: <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">파트너와 작업하는 동안에는 토글이 켜져 있어야 합니다(</Anchor><Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">활성화됨</Anchor>).**
5. 다음 섹션에 설명된 대로 관련 탭을 사용하여 구성을 완료하세요.

Persona.ly RTB와의 연동은 클릭-쓰루 및 뷰-쓰루 어트리뷰션을 지원합니다.  
구성 창에는 다음과 같은 탭이 포함되어 있습니다: 연동, 어트리뷰션 링크, 비용, 광고 수익, 권한. Persona.ly RTB의 경우 사용 가능한 탭은 연동, 어트리뷰션 링크, 비용 및 권한입니다.

> 📘 **참고사항**
>
> * 일부 설정은 iOS와 안드로이드 기기마다 다릅니다.
> * <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner">파트너 연동 설정</Anchor>에 대해 더 알아보세요.

<div id="integration-tab" />

<Accordion title="연동 탭">

**연동** 탭에는 아래 설명된 여러 섹션이 포함되어 있습니다.

#### 파트너 활성화

연동을 구성하려면 먼저 **파트너 활성화** 토글을 <Anchor target="_blank" href="/marketers/ko/docs/amazon-ads-campaign-configuration#파트너-활성화">켜야</Anchor> 합니다. <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation#파트너-연동-활성화">파트너 연동 활성화 및 비활성화</Anchor>에 대해 자세히 알아보세요.

> 📘 **참고사항**
>
> 전체 설치 네트워크인 Persona.ly RTB는 모든 소스에서 앱의 모든 신규 설치에 대한 포스트백을 수신하는 것을 선호합니다. 이렇게 하려면 **오가닉을 포함한 모든 미디어소스를 선택하여 모든** 인스톨 포스트백을 Persona.ly RTB로 전송.

#### 프라이버시 강화 모드

iOS 앱만 해당: 포스트백 및 리포트를 통해 파트너와 공유되는 데이터 제어는 <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions">고급 개인정보 보호( iOS 14.5 이상)</Anchor> **토글 상태**에 따라 달라집니다.

| 프라이버시 강화 모드: 켜기 | 프라이버시 강화 모드: 끄기 |
| --- | --- |
| 포스트백은 파트너에 어트리뷰션된 이벤트에 대해서만 전송됩니다. | 포스트백은 귀사의 설정에 따라 전송됩니다.<ul><li>**오가닉을 포함한 모든 미디어 소스**</li><li>**이 파트너사만**</li></ul> |
| 포스트백은 <Anchor target="_blank" href="/partners/ko/docs/advanced-privacy-guide-postback-macros-for-ad-networks">고급 개인정보 보호 템플릿</Anchor>에 따라 전송됩니다. |  |
| <Anchor target="_blank" href="/marketers/ko/docs/apply-aggregated-advanced-privacy-framework">집약된 익명 데이터</Anchor>는 파트너와 공유되므로 사용자 수준 데이터(디바이스 ID)가 공유되지 않습니다. |  |

#### 트랜잭션 ID

iOS 앱에 한해, **SKAN 트랜잭션 ID 공유**가 켜져 있으면 앱스플라이어가 SKAdNetwork 포스트백의 트랜잭션 ID를 Reddit과 공유할 수 있습니다.

#### 인스톨 어트리뷰션

Persona.ly RTB의 뷰-쓰루 설치를 어트리뷰션하려면 뷰-쓰루 어트리뷰션 설치를 사용 설정합니다. 뷰-쓰루 룩백 슬라이더는 어트리뷰션 링크 탭에서 사용할 수 있습니다.

#### 기본 포스트백

앱 실행 전에 발생하는 사용자 작업과 관련하여 파트너에게자동 포스트백을 보내기 위한 사용자 소스를 정의합니다.

* **설치**의 경우 다음 중 하나를 선택합니다.
  * 이 파트너사만 이 파트너만 해당: 인스톨이 이 파트너에게 어트리뷰션된 경우, 즉 앱을 설치한 사용자가 RTB에서 온 경우에만 포스트백 Persona.ly 보냅니다.
  * 오가닉을 포함한 모든 미디어 소스

#### 인앱 이벤트 포스트백

포스트백을 통해 전송되는 Persona.ly RTB 이벤트와 인앱이벤트의 매핑을 구성합니다.

1. **인앱 이벤트 포스트백**을 활성화하세요.
2. **이벤트 추가**를 클릭하여 목록에 SDK 또는 서버-투-서버 이벤트를 추가하세요. 다음 표는 작성해야 할 필드를 설명합니다.  

| 파라미터 이름 | 설명 |
| --- | --- |
| **앱스플라이어 이벤트** | 앱스플라이어가 앱에 연동된 SDK 또는 서버 간 이벤트에서 수신한 이벤트의 이름입니다.<br />**팁**: 찾고 있는 이벤트가 없나요?<ul><li>논오가닉 설치된 디바이스에서 이벤트를 활성화하고 다시 확인하세요.</li><li>**앱스플라이어 이벤트**에 입력한 다음 **사용자 지정 생성**을 클릭합니다. <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#커스텀-이벤트">커스텀 이벤트 매핑</Anchor>에 대해 더 알아보세요.</li></ul> |
| **파트너 이벤트에 매핑** | 파트너 측에서 정의한 각 이벤트의 고유한 이름 또는 ID입니다. 가능한 매핑 구성은 다음과 같습니다.<ul><li>**텍스트 필드:** 파트너로부터 해당 이벤트 ID를 받으세요.</li><li>**드롭다운 상자:** 가장 적합한 사전 정의된 앱스플라이어 이벤트를 선택합니다.</li><li>**그대로**: 이름 매핑 없이 이벤트를 있는 그대로 전송합니다.</li></ul> |
| **사용자용** | 이벤트 발송 옵션을 선택하세요:<ul><li>**이 파트너만**: 이 이벤트가 이 파트너에 어트리뷰션되었을 때만 포스트백을 전송합니다.</li><li>**오가닉 미디어 소스를 포함한 모든 미디어 소스**: 모든 파트너와 오가닉 이벤트에 어트리뷰션된 이벤트에 대해 포스트백을 전송합니다.</li></ul> |
| **포함** | <ul><li>**데이터 없음(기본값)**: 이벤트 값이 없는 상태에서 이벤트 자체만 전송합니다.</li><li>**가치와 수익**: 수익 값이 있는 경우 이를 **포함한** 모든 이벤트 파라미터를 전송합니다.</li><li>**수익 없는 값**: 수익 값을 **제외한** 모든 파라미터를 전송합니다.</li></ul> |

3. [선택 사항] **조건 추가**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" /> 아이콘을 클릭하여 이벤트에 대한 <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#조건부-인앱-이벤트-포스트백">조건을 설정</Anchor>합니다.
4. 필요한 경우 **인앱 이벤트 포스트백 창**을 설정합니다(<Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#인앱-이벤트-포스트백-기간">인앱 이벤트 포스트백 창 구성</Anchor>에 대한 자세한 내용 참조).
5. **연동 저장**을 클릭하세요.
6. [선택 사항] 연동을 저장한 후 구성 페이지에 남아 있는 동안 파트너와 더 많은 귀사의 앱을 연동할 수 있습니다.
   1. 왼쪽 상단 모서리에서 파트너 이름 아래에 있는 앱 이름을 클릭하여 앱 목록을 엽니다.
   2. 드롭다운 목록에서 다른 앱을 선택합니다.
   3. 선택한 앱에 대해 <Anchor target="_blank" href="/marketers/ko/docs/amazon-ads-campaign-configuration#integration-tab">연동 단계</Anchor>를 반복합니다.

> 📘 **참고사항**
>
> iOS 앱의 경우: 포스트백 및 <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions">리포트</Anchor>를 통해 파트너와 공유되는 데이터 제어는 **고급 개인정보 보호( iOS 14.5 이상)** <Anchor target="_blank" href="/marketers/ko/docs/tiktok-for-business-advanced-srn-integration-setup#advanced-privacy">토글 상태</Anchor>에 따라 달라집니다.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="어트리뷰션 링크 탭">

UA 및 리타겟팅 캠페인 모두에 대한 특정 캠페인, 광고 세트 또는 단일 광고를 어트리뷰션하기 위해 어트리뷰션 링크를 생성하고 저장한 후 파트너에게 보냅니다. 단일 플랫폼 링크 또는 원링크를 사용할 수 있습니다. 어트리뷰션 링크 구조 및 파라미터에 대해 더 알아보기. 어트리뷰션 링크를 생성하려면 다음 지침을 따르십시오.

</Accordion>

<div id="cost-tab" />

<Accordion title="비용 탭">

앱스플라이어는 비용 API로 트위터 비용 정보를 가져옵니다. 지원되는 기준, 지표 및 기능에 대한 세부 정보를 얻으려면 <Anchor target="_blank" href="/marketers/ko/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">애드 네트워크 비용 연동 표</Anchor>를 참조하세요. 주의: 비용 데이터를 사용하려면 ROI360 구독이 필요합니다.

**비용 API를 활성화하는 방법**:

* <Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#비용-api-활성화">이 연동 지침</Anchor>을 따르세요.

비용 <Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">API</Anchor>상태와 앱스플라이어가 비용(및 광고 수익) 연동 상태 대시보드 또는 개별 광고 네트워크 대시보드에서 일치하는 비용 데이터를 마지막으로 가져온 시간을 확인합니다.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="광고 수익 탭">

광고 수익은 Persona.ly RTB에 사용할 수 없습니다.

</Accordion>

<div id="permissions-tab" />

<Accordion title="권한 탭">

RTB Persona.ly 데이터에 액세스하고 다양한 작업을 수행할 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#permissions-tab">수 있도록 부여할 권한을</Anchor> 선택합니다.

> 📘 **참고사항**
>
> 권한 토글이 계속 켜져 있는 동안 연동이 <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">비활성화</Anchor>되어도 권한은 계속 부여됩니다.

</Accordion>

<div data-zendesk-anchors="setting-up-amazon-dsp-integration=personaly-rtb-%EC%84%A4%EC%A0%95 01H88VAJH3VENKYVRQY5RXN63P=personaly-rtb-%EC%84%A4%EC%A0%95 01H88VAJH3BYZSXQGGZZJQ9N0C=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD 01H88VAJH3VZ4GPVE7XXMKTZ2P=integration-tab activate-partner::b746d215=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 01H88VAJH34GP7FK1KTJGRDPM7=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 h_01HBB9EEMJ55BQDJ1ZEJT136ZF=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD-1 advanced-privacy=%ED%94%84%EB%9D%BC%EC%9D%B4%EB%B2%84%EC%8B%9C-%EA%B0%95%ED%99%94-%EB%AA%A8%EB%93%9C 01H88VAJH3G5FAR7RRNDEPNGME=%ED%94%84%EB%9D%BC%EC%9D%B4%EB%B2%84%EC%8B%9C-%EA%B0%95%ED%99%94-%EB%AA%A8%EB%93%9C transaction-id=%ED%8A%B8%EB%9E%9C%EC%9E%AD%EC%85%98-id h_01HARQDVEDA206D0BBXBC6WEHH=%ED%8A%B8%EB%9E%9C%EC%9E%AD%EC%85%98-id install-attribution=%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 h_01HA6PNN6RJYTNXRAS3M9EA4M4=%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 default-postbacks=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 01H88VAJH3WE9Z0971WMBRBJRS=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 inapp-event-postbacks=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 01H88VAJH3AS37MVF75GANWX4B=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 01H88VAJH36MYZ9W1YPWA92Z1Z=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD-2 01H88VAJH31GZ4KAY280ZRB8MA=attribution-link-tab 01H88VAJH3RM95V449B6DF8B4D=cost-tab 01H88VAJH3A2Q0CZXQQZMW6YRC=ad-revenue-tab 01H88VAJH30TCC574W2DH7R2A2=permissions-tab 01H88VAJH3XYP81GTFBWDBXECP=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD-3" />
