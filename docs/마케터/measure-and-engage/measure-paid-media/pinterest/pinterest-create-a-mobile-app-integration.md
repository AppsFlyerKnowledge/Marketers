---
title: Pinterest 캠페인 구성
metadata:
  keywords:
    - Pinterest
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2016-11-09T12:51:03Z'
  edited_at: '2026-10-14T10:25:54Z'
  id: 216912786
  locale: ko
  section: Pinterest
  section_id: 6551388216337
  url: https://support.appsflyer.com/hc/ko/articles/216912786
---
> **한눈에 보기:** 앱스플라이어 연동 파트너인 Pinterest는 블로거와 브랜드의 트래픽에 가장 많이 기여하는 기업 중 하나입니다. Pinterest는 클릭 기반 및 뷰-쓰루 모바일 어트리뷰션을 모두 제공합니다. 또한 Pinterest는 앱스플라이어로 기록할 수 있는 클릭 기반 리타겟팅도 제공합니다.

<div id="note" />

> 📘 **참고**
>
> * 2021년 6월부터 Pinterest는 더 이상 CPI 캠페인을 진행하지 않습니다. 그 결과, 앱스플라이어는 Pinterest에 설치 포스트백을 전송하지 않습니다.
> * Pinterest 광고 약관에 동의한 후 <Anchor target="_blank" href="https://ads.pinterest.com/terms/app_install/">여기</Anchor>에서 Pinterest 모바일 측정 약관에 동의하세요.
> * Pinterest는 어트리뷰션 파트너에게 사용자 <Anchor target="_blank" href="/marketers/ko/docs/user-level-data-retention#파트너-데이터-리텐션-기간">앱 설치 이후 6개월이 지나면</Anchor>, 사용자 레벨 데이터를 삭제하도록 요구합니다. 즉, 사용자가 앱을 설치한 후 6개월 이후에 수행한 이벤트는 오가닉으로 집계됩니다. 과거 종합 데이터는 동일하게 유지됩니다.
> * <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions#미디어-소스-제한">2023년 9월 4일부터 Pinterest에서는 사용자 개인정보를 보호하고 정보보호법 준수를 보장하기 위해 로데이터 리포트에서 일부 필드의 가용성을 제한할 것을 어트리뷰션 제공업체에 요구합니다.</Anchor>

<div id="set-up-pinterest" />

## Pinterest 설정

**전제 조건:** 연동을 설정하기 전에 <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations#contact-details">파트너에게 연락</Anchor>하여 계정을 개설하세요.

**연동 활성화 또는 편집 방법:**

1. **활성화 방법:** 앱스플라이어에서 측면 메뉴의 **협업** > **파트너 마켓플레이스**를 선택합니다.  
   **편집 방법**: 앱스플라이어의 측면 메뉴에서 **협업** > 활성화된 연동을 선택합니다.
2. **Pinterest**를 검색하여 선택합니다.
3. **연동 설정**을 클릭합니다. 연동 설정 페이지로 이동합니다.
4. **연동** 탭에서 연동할 앱을 선택하고  **파트너 활성화** 을 켭니다.  
   **참고:  파트너와 협력하는 동안 토글은 반드시 켜져 있어야 합니다. <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">(활성화됨)</Anchor> .**
5. 아래 설명된 대로 관련 탭을 사용하여 설정을 완료하십시오.

Pinterest의 구성 창에는 연동, 어트리뷰션 링크, 비용, 권한이라는 4개의 활성 탭이 있습니다. 아래 항목을 클릭하여 탭 설정에 대한 상세 설명을 참조하십시오.

<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">여기</Anchor>를 클릭하여 파트너 설정 창 헤더에 대한 자세한 설명을 확인하십시오.

<div id="integration-tab" />

<Accordion title="연동 탭">

<div id="activate-partner" />

### 파트너 활성화

**첫 번째 방문**에서 연동 탭의 파라미터 설정을 사용 가능하게 하려면 **파트너 활성화** 버튼을 켜야 합니다. 파트너와 작업하는 동안에는 토글이 켜져 있어야 합니다.  
파트너 활성화에 대한 자세한 내용을 보려면 <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">여기</Anchor>를 클릭하십시오.

<div id="general-settings" />

### 일반 설정

다음은 Pinterest의 연동 탭에 대한 일반 설정입니다.

**뷰-쓰루 어트리뷰션 활성화**

Pinterest의 뷰-쓰루 설치를 어트리뷰션하려면 이 옵션을 켭니다. 뷰-쓰루 룩백 슬라이더는 어트리뷰션 링크 탭에 있습니다(아래 설명 참조).

<div id="legacy-set-tag-id" />

<div id="in-app-events-settings" />

<div id="including" />

<div id="to-users-from" />

<div id="partner-event-name" />

<div id="appsflyer-event-name" />

<div id="in-app-event-postbacks" />

### 인앱 이벤트 설정

이 섹션에서는 포스트백을 통해 앱스플라이어 이벤트를 Pinterest와 매핑합니다.

**태그 ID**

Pinterest에 인앱 이벤트 포스트백을 보내려면 태그 ID를 입력해야 합니다. 태그 ID가 없는 경우 Pinterest에서 가져옵니다.

**태그 ID를 가져오고 인앱 이벤트 포스트백을 설정합니다** :

1. Pinterest 비즈니스 계정에서 **광고** > **전환**으로 이동하여 **태그 ID**를 복사합니다.  
   아직 태그가 없는 경우 **태그 만들기**를 클릭하고 생성 프로세스를 완료합니다. 새 태그를 복사합니다.  
   **참고**: 태그 ID는 이벤트 포스트백에만 필요합니다.
2. AppsFlyer의 Pinterest 통합 설정에서 **인앱 이벤트 설정**으로 스크롤하여 Pinterest 태그 ID를 입력합니다.
3. **인앱이벤트 포스트백**을 설정합니다.
4. 인앱이벤트 포스트백 윈도우를 설정합니다.
5. 이벤트에 대한 포스트백 설정 및 매핑을 선택합니다.
6.
   | 파라미터 이름 | 설명 |
   | --- | --- |
   | **AppsFlyer 이벤트 이름** | 앱에 연동된 SDK 또는 서버 간(S2S) 이벤트에서 앱스플라이어가 수신한 이벤트의 이름입니다.  <br />**팁** - 원하는 이벤트가 목록에 없으면, 논오가닉으로 인스톨한 기기에서 이벤트를 실행하고 다시 점검해 봅니다. |
   | **파트너 이벤트 이름** | Pinterest 측에 정의된 각 이벤트의 고유 이름 또는 ID입니다.  <br />Pinterest에서 해당 이벤트 ID를 얻고 텍스트 필드에 설정합니다. |
   | **사용자에게서** | 이 파트너만 해당: Unity Ads로 어트리뷰션된 사용자로부터 발생한 이벤트에만 적용됩니다.  <br />**오가닉을 포함한 모든 미디어소스**: 트레이드 데스크에 리포트할 수 있는 전체 사용자 기반을 가지는 미디어소스를 의미합니다. |
   | **아래 두 곳 역시 포함합니다:** | 이벤트 수익 또는 매개변수 값이 포스트백에서 파트너에게 전송되는지, 아니면 이 데이터가 포함되지 않는지 선택합니다.<br /><br />**체크하지 않은 경우** - af\_revenue 파라미터에 포함된 수익 파라미터를 제외하고, 리치 인앱 이벤트의 모든 파라미터를 파트너에게 전송합니다. 선택한 경우 - 수익 값(이벤트에 존재하는 경우)을 포함하여 모든 파라미터를 전송합니다. |

7. SDK 이벤트를 목록에 추가하려면 **이벤트 추가**를 클릭합니다.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="어트리뷰션 링크 탭">

UA 및 리타겟팅 캠페인 모두에 대한 특정 캠페인, 광고 세트 또는 단일 광고를 어트리뷰션하기 위해 어트리뷰션 링크를 생성하고 저장한 후 파트너에게 보냅니다. 단일 플랫폼 링크 또는 원링크를 사용할 수 있습니다.  
<Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters">어트리뷰션 링크 구조 및 파라미터에 대해 더 알아보기</Anchor>.

**어트리뷰션 링크를 생성하려면** <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#attribution-link-tab">다음 지침</Anchor>을 따르십시오.

<div id="attribution-link-for-retargeting-campaign" />

#### 리타겟팅 캠페인을 위한 어트리뷰션 링크

Pinterest는 리타겟팅 캠페인을 위해 OS별 어트리뷰션 링크를 사용할 것을 권장합니다. **단일 플랫폼 링크 사용** 옵션을 선택하고 필요한 파라미터를 리타겟팅 어트리뷰션 링크에 추가합니다.

<div id="deep-link-url" />

#### 딥링크 URL

<div id="note-1" />

> 📘 **참고**
>
> 핀 내의 딥링킹은 Pinterest에서 앱을 허용 목록에 추가하는 경우에만 올바르게 작동합니다.
> 딥링킹에 대한 허용 목록에 추가하려면 Pinterest 담당자에게 문의하거나 이메일([apps@pinterest.com](mailto:apps@pinterest.com))을 보내주세요.

링크가 사용자를 앱 내부의 특정 액티비티로 딥링킹하려는 경우, 이 필드를 사용합니다.

</Accordion>

<div id="cost-tab" />

<Accordion title="비용 탭">

Pinterest의 비용을 설정한 후에는 실행 중인 캠페인, 광고 세트 또는 단일 광고의 이름을 변경하거나 캠페인 이름 파라미터와 함께 동적 매크로를 사용하면 심각한 불일치가 발생하거나 비용 데이터가 누락될 수 있으므로 이러한 작업을 수행하지 마세요.

<div id="enabling-and-testing-pinterest-integration" />

### Pinterest 연동 활성화 및 테스트

앱스플라이어는 비용 API로 트위터 비용 정보를 가져옵니다. 지원되는 기준, 지표 및 기능에 대한 세부 정보를 얻으려면 <Anchor target="_blank" href="/marketers/ko/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">애드 네트워크 비용 연동 표</Anchor>를 참조하세요. 주의: 비용 데이터를 사용하려면 ROI360 구독이 필요합니다.

**비용 API를 활성화하는 방법**:

* <Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#비용-api-활성화">이 연동 지침</Anchor>을 따르세요.

<div id="cost-data-sync-status" />

### 비용 데이터 동기화 상태

<Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">비용 API 상태</Anchor>와 앱스플라이어가 비용(및 광고 수익) 연동 상태 대시보드 또는 개별 광고 네트워크 대시보드에서 일치하는 비용 데이터를 가져온 마지막 시간을 확인합니다.

<div id="stop-pinterest-cost-sync" />

### Pinterest 비용 동기화 중지

**연결된 계정을 삭제하려면:**

* <Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#deleting-connected-accounts-in-the-cost-tab">작업 열에서 계정 위로 마우스를 올리고 *연결 삭제*를 클릭합니다.</Anchor> 삭제되면 앱스플라이어가 비용 수신을 중지합니다. 연결을 삭제해도 기록 데이터에는 영향을 주지 않습니다.

<div id="ad-revenue-tab" />

<Accordion title="광고 수익 탭">

이 파트너는 광고 수익 데이터를 지원하지 않습니다.

</Accordion>

<div id="permissions-tab" />

<Accordion title="권한 탭">

이 탭에서는 Pinterest에 부여할 권한을 선택할 수 있습니다. Pinterest 어트리뷰션이 비활성화되어 있더라도 권한 탭은 활성 상태이므로, Pinterest에 권한을 부여할 수 있습니다.

<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#permissions-tab">Pinterest에 부여할 수 있는 권한</Anchor>에 대해 더 알아보세요.

</Accordion>

</Accordion>

<div id="troubleshooting" />

## 문제 해결

비용 탭 오류 메시지: *일치하는 데이터가 없음*은 앱스플라이어에 연결한 Pinterest 계정이 올바른 Pinterest 계정이 아님을 의미합니다. 앱과 일치하는 데이터를 찾을 수 없습니다. 다른 자격 증명으로 Pinterest에 로그인해야 합니다.

<div data-zendesk-anchors="h_01H95QTA3ZZ9GJW9EN1VZ01TH2=%EC%B0%B8%EA%B3%A0 set-up-pinterest=pinterest-%EC%84%A4%EC%A0%95 h_01H95QTA3Z5HXW39AHAF8FMFWH=pinterest-%EC%84%A4%EC%A0%95 h_01H95QTA3ZNQWBRA86E6TRQ46Y=integration-tab activate-partner=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 h_01H95QTA3ZGEM34HY1A7NC8NX7=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 general-settings=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 h_01H95QTA3Z0NW9V51D8J7MHEX0=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 inapp-events-settings=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95 h_01H95QTA3ZWSF0JYZ9D4HEB4A4=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95 h_01H95QTA3ZT7PVGAJW5AKPC186=attribution-link-tab attribution-link-for-retargeting-campaigns=%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%EC%BA%A0%ED%8E%98%EC%9D%B8%EC%9D%84-%EC%9C%84%ED%95%9C-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC h_01H95QTA3ZPQZ422AB2JBZAS07=%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%EC%BA%A0%ED%8E%98%EC%9D%B8%EC%9D%84-%EC%9C%84%ED%95%9C-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC deep-link-url=%EB%94%A5%EB%A7%81%ED%81%AC-url h_01H95QTA3ZT23CYTCE2V3728MD=%EB%94%A5%EB%A7%81%ED%81%AC-url h_01H95QTA3ZYHQED2T5B2FA5PV8=%EC%B0%B8%EA%B3%A0-1 h_01H95QTA3Z3XJDM5YRXFK7DA0E=cost-tab enabling-and-testing-pinterest-integration=pinterest-%EC%97%B0%EB%8F%99-%ED%99%9C%EC%84%B1%ED%99%94-%EB%B0%8F-%ED%85%8C%EC%8A%A4%ED%8A%B8 h_01H95QTA3ZZ56R8EZBJY1ESX5W=pinterest-%EC%97%B0%EB%8F%99-%ED%99%9C%EC%84%B1%ED%99%94-%EB%B0%8F-%ED%85%8C%EC%8A%A4%ED%8A%B8 cost-data-sync-status=%EB%B9%84%EC%9A%A9-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%8F%99%EA%B8%B0%ED%99%94-%EC%83%81%ED%83%9C h_01H95QTA3ZST8WS3TAR79H06FM=%EB%B9%84%EC%9A%A9-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%8F%99%EA%B8%B0%ED%99%94-%EC%83%81%ED%83%9C stop-pinterest-cost-sync=pinterest-%EB%B9%84%EC%9A%A9-%EB%8F%99%EA%B8%B0%ED%99%94-%EC%A4%91%EC%A7%80 h_01H95QTA3ZFCJ82E3YDMP7S716=pinterest-%EB%B9%84%EC%9A%A9-%EB%8F%99%EA%B8%B0%ED%99%94-%EC%A4%91%EC%A7%80 h_01H95QTA3ZM2REWR2A5DHK1DSA=ad-revenue-tab h_01H95QTA3ZM4WPHV3MB00WZXSB=permissions-tab troubleshooting=%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0 h_01H95QTA3ZP20DSJQGY4QQX0Z7=%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0" />
