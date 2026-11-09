---
title: Unity Ads 캠페인 구성
metadata:
  keywords:
    - Unity Ads
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-03-06T10:05:52Z'
  edited_at: '2026-10-14T10:38:06Z'
  id: 208005086
  locale: ko
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/ko/articles/208005086
---
> **한눈에 보기:** 요약: 앱스플라이어 광고 네트워크 연동 파트너인 Unity Ads는 iOS 및 안드로이드용 비디오 광고 네트워크입니다. Unity Ads는 클릭 기반 모바일 어트리뷰션 외에도 비용, 광고 수익 및 뷰-쓰루 어트리뷰션을 제공하며, 이는 앱스플라이어에 기록될 수 있습니다.

Unity Ads로 캠페인을 구성하려면 다음 단계를 따르십시오.

<div id="setting-up-unity-ads" />

## Unity Ads 설정

**전제 조건:** 연동을 설정하기 전에 <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations#contact-details">파트너에게 연락</Anchor>하여 계정을 개설하세요.

**연동 활성화 또는 편집 방법:**

1. **활성화 방법:** 앱스플라이어에서, 측면 메뉴에서 **협업** > **파트너 마켓플레이스**를 선택하세요.  
   **편집 방법**: 앱스플라이어의 측면 메뉴에서 **협업** > **활성화된 연동**을 선택하세요.
2. 파트너를 검색하여 선택하세요.
3. **연동 설정**을 클릭하십시오. 연동 설정 페이지로 이동합니다.
4. **연동** 탭에서 **파트너 활성화**를 선택합니다.  
   **참고:** 파트너와 작업하는 동안에는 토글이 켜져 있어야 합니다(활성화됨/strong>).
5. 아래 설명된 대로 관련 탭을 사용하여 설정을 완료하십시오.

연동, 어트리뷰션 링크, 비용, 광고 수익, 권한. 아래 항목을 클릭하여 탭 설정에 대한 상세 설명을 참조하십시오.

<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">여기</Anchor>를 클릭하여 파트너 설정 창 헤더에 대한 자세한 설명을 확인하십시오.

> 👍 **팁**
>
> * 연동 탭의 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#d-general-settings">일반 설정</Anchor> 단계는 모든 파트너에게 **필수**입니다.
> * 나머지 모든 단계는 설명이거나 **선택** 항목입니다.

<div id="integration-tab" />

<Accordion title="연동 탭">

<div id="activate-partners" />

### 파트너 활성화

처음 방문 시에 **파트너 활성화** 토글을 켜서 연동을 설정해야 합니다. 파트너와 함께 작업하는 동안 토글은 켜져 있는 상태로 남아있어야 합니다.  
파트너 활성화에 대한 자세한 내용을 보려면 <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">여기</Anchor>를 클릭하십시오.

<div id="general-settings" />

### 일반 설정

**Unity에 기기 ID(광고 ID) 전송**

연동 탭의 상단에 Unity Ads는 설치할 때마다 장치 ID를 보내야 한다는 메모가 있는데, 이는 자동으로 수행되므로 사용자가 직접 수행할 필요가 없습니다.

<Image align="center" alt="Unity_msc_new_2.png" src="https://files.readme.io/4291f0b69f8231f6644872f2dfaec84e7c93047e81f653e76ff7266387fa10a9-360002583918.png" />

**Unity Ads 게임 ID**

Unity Ads를 사용하려면 고유 게임 ID를 통해 앱스플라이어와 연결해야 합니다. 자신의 ID를 모르는 경우 Unity Ads에서 직접 다운로드하거나 아래 스크린샷과 같이 게임을 업로드한 후 **앱** > **캠페인**에서 찾을 수 있습니다.

<Image align="center" alt="" src="https://files.readme.io/c3315765f33e957b82c39b638bb8113e207bfe80f242bf2e6dde3dce30287a6f-8109147574673.png" />

Unity Ads 플랫폼은 계정 레벨당 하나의 앱을 하나의 Unity Ads 게임 ID에 매핑합니다(광고주와 에이전시는 동일한 앱에 대해 서로 다른 게임 ID를 갖게 됩니다). Unity Ads 플랫폼의 서로 다른 계정은 서로 다른 게임 ID로 동일한 앱을 실행할 수 없습니다.

**뷰-쓰루 어트리뷰션 활성화**

이 옵션을 켜면 Unity Ads에서 뷰-쓰루 설치를 어트리뷰션할 수 있습니다. 뷰-쓰루 룩백 슬라이더는 어트리뷰션 링크 탭에 있습니다(아래 설명 참조).

<Image align="center" alt="Unity_ads_msc_new_3.png" src="https://files.readme.io/fab459ace7e8f1354d3bbfbca8ddefcd11376b7426a8e361abfab1b42b623880-360001875405.png" />

<div id="default-postbacks" />

### 기본 포스트백

<Image align="center" alt="Screen_Shot_2022-07-28_at_13.07.25.png" src="https://files.readme.io/a571ddc49e490373b34144e34626a18c6c18908cec3345cd7ac70c49aa855c05-7975491293329.png" />

이 섹션을 사용하여 상기 포스트백을 보낼 수 있는 사용자의 출처를 정의할 수 있습니다.

* **이 파트너만 해당**: Unity Ads로 어트리뷰션된 사용자로부터 발생한 이벤트에만 적용됩니다.
* **오가닉을 포함한 모든 미디어 소스**: Unity Ads에 리포트할 수 있는 전체 사용자 기반을 가지는 미디어 소스를 의미합니다.

<div id="note" />

> 📘 **참고**
>
> 모든 설치 네트워크인 Unity Ads는 모든 소스에서 앱의 모든 신규 설치에 대한 포스트백을 수신하는 것을 선호하며, 모든 설치 포스트백을 Unity Ads로 전송하려면 **오가닉을 포함한 모든 미디어 소스**를 선택할 것을 권장했습니다.

<div id="in-app-events-settings" />

### 인앱 이벤트 설정

포스트백을 통해 앱스플라이어 이벤트를 파트너와 매핑할 수 있습니다. 포스트백 발송이 활성화된 경우, 이는 거부된 인앱 이벤트(Protect360에 의해 차단된 이벤트나 유효성 검증 규칙을 준수하지 않는 것으로 판단된 이벤트)를 포함합니다.

<Image align="center" alt="" src="https://files.readme.io/e0d0af3c57c8452b646dfede7b4899215825ef8455d4e41293088f98ecc026eb-7975565240337.png" />

<div id="important" />

<div id="to-configure-in-app-event-postbacks" />

#### 인앱 이벤트 포스트백 설정 방법

1. **game\_id**입력합니다. game\_id 올바르고 인스톨 어트리뷰션에 사용된 것과 동일한지 확인합니다.
2. **인앱 이벤트 포스트백**을 활성화하세요.
3. 필요한 경우 **인앱 이벤트 포스트백 기간**을 설정합니다(<Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#인앱-이벤트-포스트백-기간">인앱 이벤트 포스트백 기간 구성</Anchor>에 대해 자세히 알아보세요).
4. **이벤트 추가**를 클릭하여 목록에 SDK 또는 서버 간 이벤트를 추가합니다.
5. 다음 파라미터를 완성하세요.

| 파라미터 이름 | 설명 |
| --- | --- |
| **앱스플라이어 이벤트**, | 앱스플라이어가 앱에 연동된 SDK 또는 서버 간 이벤트에서 수신한 이벤트의 이름입니다.<br />**팁**: 찾고 있는 이벤트가 없나요?<ul><li>논오가닉 인스톨 및 재확인을 통해 디바이스에서 이벤트가 활성화되었는지 확인합니다.</li><li>**앱스플라이어 이벤트**에 입력한 다음 **사용자 지정 생성**을 클릭합니다. 커스텀 이벤트 매핑에 대해 더 알아보세요.</li></ul> |
| **파트너 이벤트에 매핑** | 파트너 측에서 정의한 각 이벤트의 고유한 이름 또는 ID입니다. 가능한 매핑 구성은 다음과 같습니다.<ul><li>**텍스트 필드:** 파트너로부터 해당 이벤트 ID를 받으세요.</li><li>**드롭다운 상자:** 가장 적합한 사전 정의된 앱스플라이어 이벤트를 선택합니다.</li><li>**그대로**: 이름 매핑 없이 이벤트를 있는 그대로 전송합니다.</li></ul> |
| **사용자용** | 이벤트의 전송 옵션을 선택합니다.<ul><li>**이 파트너만**: 이 이벤트가 이 파트너에게 귀속된 경우에만 포스트백을 발송합니다.</li><li>**오가닉을 포함한 모든 미디어소스**: 오가닉 이벤트를 포함하여 모든 파트너로 어트리뷰션된 이벤트의 포스트백을 전송합니다.</li></ul> |
| **포함** | <ul><li>**데이터 없음(기본값)**: 이벤트 값 없이 이벤트 자체만 보냅니다.</li><li>**값 및 수익**: 매출 값(이벤트에 존재하는 경우)을 **포함하여** 모든 이벤트 파라미터를 전송합니다.</li><li>**수익이 없는 값**: 수익 값을 **제외한** 모든 파라미터를 전송합니다.</li></ul> |

<div id="note-1" />

> 📘 **참고**
>
> <Anchor target="_blank" href="/marketers/ko/docs/roi360-guide-ad-revenue-attribution#ad-revenue-event-postbacks-for-ad-networks">광고 수익 포스트백</Anchor>을 Unity Ads로 보내 광고 수익 데이터를 사용하여 캠페인을 최적화할 수 있습니다.
>
> * **<strong>이벤트 이름:</strong> af\_ad\_revenue**<strong>이벤트 이름:</strong> af\_ad\_revenue
> * **<strong>매핑 대상:</strong> ad\_revenue**<strong>매핑 대상:</strong> ad\_revenue

<div id="attribution-link-tab" />

<Accordion title="어트리뷰션 링크 탭">

UA 및 리타겟팅 캠페인 모두에 대한 특정 캠페인, 광고 세트 또는 단일 광고를 어트리뷰션하기 위해 어트리뷰션 링크를 생성하고 저장한 후 파트너에게 보냅니다. 단일 플랫폼 링크 또는 원링크를 사용할 수 있습니다.  
<Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters">어트리뷰션 링크 구조 및 파라미터에 대해 자세히 알아보십시오</Anchor>.

**어트리뷰션 링크를 생성하려면** <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#attribution-link-tab">다음 지침</Anchor>을 따르십시오.

**참고:**

* 안드로이드 앱의 타겟 잠재 고객에 어린이가 포함된 경우 Unity는 어린이를 0으로 처리한 광고 ID를 전송합니다.
* Unity Ads에서 클릭 및 뷰를 정의하는 방법에 대해 자세히 알아보십시오.

</Accordion>

<div id="cost-tab" />

<Accordion title="비용 탭">

앱스플라이어는 비용 API로 트위터 비용 정보를 가져옵니다. 지원되는 기준, 지표 및 기능에 대한 세부 정보를 얻으려면 애드 네트워크 비용 연동 표를 참조하세요.

**참고:**

* 비용 데이터를 사용하려면 ROI360 구독이 필요합니다.
* 에이전시 비용은 클릭당 비용 또는 API를 통해 지원되지 않습니다. 광고주는 광고 지출 처리를 통해 대행사 비용 데이터를 보낼 수 있습니다.

**비용 API를 활성화하려면**:

* <Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#비용-api-활성화">이 연동 지침</Anchor>을 따르세요.  
  **참고**: 그렇지 않으면 비용 데이터를 가져오는 데 영향을 받습니다.

비용 <Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">API</Anchor>상태와 앱스플라이어가 비용(및 광고 수익) 연동 상태 대시보드 또는 개별 광고 네트워크 대시보드에서 일치하는 비용 데이터를 마지막으로 가져온 시간을 확인합니다.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="광고 수익 탭">

이 섹션은 사용자에게 파트너의 광고를 표시하는 퍼블리셔에게만 해당됩니다. 퍼블리셔에 해당되는 경우는 다른 소스에서 획득한 사용자의 인게이지먼트를 측정하여 가장 수익성이 높은 소스를 찾을 수 있습니다.

**광고 수익 API 설정 방법**:

* <Anchor target="_blank" href="/marketers/ko/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">이 연동 지침</Anchor>을 따르세요.

</Accordion>

<div id="permissions-tab" />

<Accordion title="권한 탭">

이 탭에서 특정 작업을 수행하도록 Unity Ads에 권한을 부여할 수 있습니다. Unity Ads에 대한 어트리뷰션이 비활성화되어 있어도 권한 탭이 활성화되며 Unity Ads 권한을 부여할 수 있습니다.  
<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#permissions-tab">부여할 수 있는 권한</Anchor>에 대해 더 알아보세요.

</Accordion>

</Accordion>

<div data-zendesk-anchors="setting-up-unity-ads=unity-ads-%EC%84%A4%EC%A0%95 h_01HAPVZ510GTJRY1NXE0T3SMR6=unity-ads-%EC%84%A4%EC%A0%95 h_01HAPVZ5109NKD8GHD36EDN810=%ED%8C%81 h_01HAPVZ510KPB0HQS9X6R4BCWT=integration-tab activate-partners=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 h_01HAPVZ510BGQ4KZ3S6ZP0QRE8=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 general-settings=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 h_01HAPVZ510EZ3HKJQVPMKHV5FH=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 default-postbacks=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01HAPVZ511MRQXKPC78HR61X9P=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01HAPVZ511CCXS93Y714STGQ67=%EC%B0%B8%EA%B3%A0 inapp-events-settings=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95 h_01HAPVZ511CJ6JP49HYG9T6RPF=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95 to-configure-inapp-event-postbacks=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EC%84%A4%EC%A0%95-%EB%B0%A9%EB%B2%95 h_01HAPVZ511RMEVNASSTJNXKCJG=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EC%84%A4%EC%A0%95-%EB%B0%A9%EB%B2%95 h_01HAPVZ511AV30DEKMZ0YB5ZBD=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EC%84%A4%EC%A0%95-%EB%B0%A9%EB%B2%95 h_01HAPVZ511PC45Q5FEXQMZ4MFC=%EC%B0%B8%EA%B3%A0-1 h_01HAPVZ5110QVYGGCGQDHRJEQM=attribution-link-tab h_01HAPVZ511DSKFAKKNWTKV9522=cost-tab h_01HAPVZ5111WPRRMPF6GZJTRJS=ad-revenue-tab h_01HAPVZ511RBNY3HHSHJHJDPWG=permissions-tab" />
