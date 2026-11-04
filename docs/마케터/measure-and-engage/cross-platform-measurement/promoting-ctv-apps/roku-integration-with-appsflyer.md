---
title: Roku-앱스플라이어 연동
metadata:
  keywords:
    - Advertisers
    - CTV
    - Marketers
    - CTV Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - CTV Attribution
  created_at: '2021-07-19T09:00:10Z'
  edited_at: '2026-10-14T10:34:02Z'
  id: 4404257169169
  locale: ko
  section: Promoting CTV apps
  section_id: 15328952633489
  url: https://support.appsflyer.com/hc/ko/articles/4404257169169
---
> **한눈에 보기** Rokuads\_int는 광고주가 Roku Ads와 모바일 또는 Roku CTV 앱을 연동하여 Roku Ads에서 캠페인에 대한 어트리뷰션 및 이벤트 데이터를 받아볼 수 있도록 하는 SRN 연동입니다.

<div id="about-roku-ads-attribution" />

## Roku Ads 어트리뷰션에 대하여

Roku는 커넥티드 TV(CTV)와 모바일 앱 모두에 광고 인벤토리를 보유하고 있는 독특한 애드 네트워크입니다. AppsFlyer와 Roku Ads 간의 SRN 연동은 광고주가 다음을 포함한 여러 사용자 여정을 측정할 수 있도록 합니다:

* CTV-to-CTV: CTV 앱 설치 및 이벤트를 유도하는 CTV 광고
* 모바일-to-모바일: 모바일 앱 설치 및 이벤트를 유도하는 모바일 앱 광고
* CTV-to-모바일 및 모바일-to-CTV: 한 플랫폼에서의 광고 노출이 다른 플랫폼에서의 설치 및 이벤트로 이어질 때

<div id="roku-attribution-flow" />

### Roku 어트리뷰션 흐름

[<Image alt="54525 inline.jpg" src="https://files.readme.io/5634ed65702e1d4c90250a7f7b4448c225d5f769936b2a120ddbac1a76752c09-39534517801617.jpg" width="895px" />](https://support.appsflyer.com/hc/article_attachments/39554303369489)

<div id="setting-up-roku-ads-integration-for-advertisers" />

## 광고주를 위한 Roku Ads 연동 설정

**전제 조건:** 연동 설정 전에 [파트너에게 연락](#)하여 계정을 개설하세요.

**연동 활성화 또는 연동 편집 방법:**

1. 활성화 방법: 앱스플라이어에서의 사이드 메뉴에서 **협업** > **파트너 마켓플레이스**를 선택하세요.  
   편집 방법: **협업**> **활성 연동**으로 이동합니다.
2. 파트너(`rokuads_int`)를 검색하고 선택합니다.
3. **연동 설정**을 클릭하세요. **활성** 연동 설정 페이지로 이동합니다.
4. **연동** 탭에서 **파트너 활성화**를 켭니다.  
   **참고:** **파트너와 작업하는 동안에는 토글이 켜져 있어야 합니다([활성화됨](#)). 파트너 활성화에 대해 더 알아보십시오.**
5. 아래 설명된 대로 관련 탭을 사용하여 설정을 완료하십시오.

**참고:** iOS, Android 및 Roku 앱 설정 간에는 몇 가지 차이가 있습니다.

<div id="integration-tab" />

<Accordion title="연동 탭">

<div id="general-settings" />

#### 일반 설정

* **이벤트 그룹 ID:** Roku Ads 관리자가 부여한 이벤트 그룹 ID를 입력하여 앱을 AppsFlyer에 연결합니다. 자세한 내용은 <Anchor target="_blank" href="https://help.ads.roku.com/en/articles/11885912-setting-up-an-integration-with-appsflyer-a-mobile-measurement-partner-mmp">Roku 광고 관련 문서</Anchor>를 참조하십시오.
* **고급 데이터 공유:**  ON으로 설정하면 Roku는 모든 장치에 대해 IP 주소가 포함된 포스트백 및 이벤트 데이터를 수신합니다. 여기에는 광고 ID(IDFA)를 제공하지 않은 장치도 포함됩니다. 고급 공유를 OFF로 유지하면 해당 파트너는 IDFA가 존재하는 기기에 대해서만 포스트백 및 이벤트 데이터를 수신하게 됩니다.
* **제한된 데이터 사용:** ON으로 설정하면 Roku Ads가 특정 미국 주에서 주어진 이벤트에 한하여 개인 정보 사용을 제한하게 됩니다. 자세한 내용은 <Anchor target="_blank" href="https://help.ads.roku.com/en/articles/8766138-limited-data-use">Roku 광고 관련 문서</Anchor>를 참조하십시오.

<div id="install-attribution" />

#### 인스톨 어트리뷰션

광고를 본 유저, 클릭했거나 인게이지한 유저의 새 인스톨을 측정하기 위해 어트리뷰션 윈도우를 각각 다르게 설정하세요. **참고:** 재설치(디바이스의 초기 설정이 아닌 모든 인스톨)에 대한 어트리뷰션은 지원되지 않습니다.

* **인스톨 클릭-쓰루 룩백 윈도우**를 1&#126;23시간 또는 1&#126;14일로 설정하세요. **참고:** Roku Ads는 이를 14일로 설정할 것을 권장합니다.
* [선택사항] **인스톨 뷰-쓰루 어트리뷰션**을 활성화하고 **인스톨 뷰-쓰루 룩백 윈도우**를 1-23시간 혹은 1-14일로 설정합니다. **참고:** Roku Ads는 14일을 권장합니다.

<div id="re-engagement-attribution" />

#### 리인게이지먼트 어트리뷰션

* **리인게이지먼트 클릭-쓰루 룩백 윈도우**를 1&#126;23시간 또는 1&#126;14일로 설정합니다. **참고:** Roku Ads는 14일을 권장합니다.
* [선택 사항] **리인게이지먼트 뷰-쓰루 어트리뷰션**을 켜고 **리인게이지먼트 뷰-쓰루 룩백 윈도우**를 1–23시간 또는 1–14일로 설정합니다. **참고:** Roku Ads는 14일을 권장합니다.
* **리인게이지먼트 윈도우**를 1&#126;23시간, 1&#126;90일 또는 **평생**으로 설정하세요.

[리인게이지먼트 규칙 및 윈도우](#)에 대해 자세히 알아보세요.

<div id="ignore-active-users-for-retargeting" />

#### 리타깃팅 시 활성 유저 무시

지정된 기간 내에 앱을 실행한 유저의 리인게이지먼트를 무시하도록 윈도우 시간을 설정합니다. 이는 해당 기간 동안의 활동이 귀속되지 않음을 의미합니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/set-retargeting-inactivity-window#비활성-기간">비활동 기간</Anchor>을 참조하십시오.

1. **리타깃팅을 위해 활성 유저 무시**를 켭니다.
2. **비활성 기간**을 설정합니다.

<div id="cross-platform-attribution" />

#### 크로스 플랫폼 어트리뷰션

이 연동에 한해 크로스 플랫폼 어트리뷰션이 디폴트로 활성화되어 있습니다.

* **크로스 플랫폼 룩백 윈도우**를 1–23시간 또는 1–3일로 설정합니다.
* [선택 사항] **크로스 플랫폼 간 동등한 우선순위** 설정이 활성화되면 Roku가 리포팅하는 크로스 플랫폼 노출이 다른 네트워크의 클릭과 동일한 우선순위를 갖게 됩니다. 활성화된 경우 **크로스 플랫폼 동등 우선 순위 윈도우**를 1–6시간으로 설정합니다 (기본값: 3시간).

<div id="in-app-events-postbacks" />

#### 인앱 이벤트 포스트백

AppsFlyer의 인앱 이벤트를 Roku Ads 이벤트에 매핑하여, 포스트백을 통해 전송하세요.

1. **인앱 이벤트 포스트백**을 활성화하세요.
2. **이벤트 추가**를 클릭하여 목록에 SDK 또는 서버-to-서버 이벤트를 추가하세요. 다음 표에는 작성해야 할 필드에 대한 설명이 나와있습니다.

| 파라미터 이름 | 설명 |
| --- | --- |
| **앱스플라이어 이벤트** | 앱에 연동된 SDK 또는 서버 간 이벤트로부터 앱스플라이어에서 수신한 이벤트의 이름입니다. |
| **파트너 이벤트**에 매핑됨: | Roku의 미리 정의된 이벤트 목록에서 선택합니다. AppsFlyer 이벤트에서 Roku Ads 이벤트로의 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#사전-정의된-이벤트-이름">권장되는 매핑</Anchor>을 참조하십시오.  <br />**참고:** Roku는 사용자 정의 이벤트 전송을 지원하지 않습니다. |
| **유저 유입 소스** | <ul><li>**해당 파트너만**(기본값): 이 이벤트가 이 파트너에게 어트리뷰션된 경우에만 포스트백을 보냅니다.<br />혹은</li><li>**오가닉을 포함한 모든 미디어 소스:** 파트너에 어트리뷰션 된 이벤트 (오가닉 이벤트 포함)에 대해 포스트백을 전송합니다.</li></ul> |
| **포함** | <ul><li>**값 없음 & 수익 없음** (기본 설정): 이벤트 값 없이 이벤트 자체만 전송합니다.</li><li>**값 있음 & 수익 없음**: 수익 값을 **제외한** 모든 파라미터를 전송합니다.</li><li>**값 있음 & 수익 있음**: 수익 값(이벤트에 존재할 경우)을 포함한 모든 이벤트 파라미터를 전송합니다.</li></ul> |

* [선택 사항] **조건 추가** 아이콘을 클릭하여 이벤트에 대한 조건을 설정합니다.
* **연동 저장**을 클릭하세요.
* [선택 사항] 더 많은 앱을 통합하려면:
  1. 왼쪽 상단 모서리에서 파트너 이름 아래에 있는 앱 이름을 클릭하여 앱 목록을 엽니다.
  2. 목록에서 다른 앱을 선택합니다.
  3. 선택한 앱에 대해 설정을 반복합니다.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="어트리뷰션 링크 탭">

어트리뷰션 링크는 SRN 또는 고급 SRN과 관련이 없습니다.

</Accordion>

<div id="cost-tab" />

<Accordion title="비용 탭(비용, 클릭 수, 노출 수)">

현재 단계에서는 Roku Ads에 대한 비용 연동 기능이 제공되지 않습니다.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="광고 수익 탭">

Roku Ads에 대한 광고 수익 기능이 제공되지 않습니다.

</Accordion>

<div id="permissions-tab" />

<Accordion title="권한 탭">

이 탭에서는 Roku Ads에 어떤 권한을 부여할지 선택할 수 있습니다—애드 네트워크, 에이전시 혹은 두 역할을 모두 수행하더라도 부여할 권한을 선택할 수 있습니다. Roku Ads에 대한 어트리뷰션이 비활성화되어도 권한 탭은 활성 상태로 유지되며 여전히 액세스를 부여할 수 있습니다.

Roku Ads에 대한 권한을 활성화한 후, 팀 구성원을 추가하고 선택한 권한에 따라 액세스를 부여할 수 있습니다. **참고:** 권한은 AppsFlyer에서 광고 네트워크 팀 구성원 계정을 가지고 있는 Roku Ads 직원에게만 부여될 수 있습니다.

**애드 네트워크 팀 구성원에게 권한을 부여하려면 다음 단계를 따르세요:**

1. **팀 구성원 추가**를 클릭합니다.
2. 애드 네트워크 팀원의 이메일을 입력합니다.
3. **추가**를 클릭합니다.

<div id="important" />

> 🚧 **중요!**
>
> * Roku Ads에 연동을 설정하고 인앱 이벤트 포스트백을 변경할 수 있는 권한을 부여하면, 모든 미디어소스의 오가닉 및 논오가닉 트래픽을 포함한 모든 어트리뷰션 이벤트에 접근할 수 있도록 허용하게 됩니다.
> * 사용자(광고주)가 현재 구성을 설정했더라도 Roku OneView에서 변경한 사항이 현재 구성보다 우선 적용됩니다.

<div id="types-of-permissions-advertisers-can-grant-to-roku-ads" />

#### 광고주가 Roku Ads에 부여할 수 있는 권한의 유형

| 권한 | 부여된 기능 |
| --- | --- |
| 연동 설정 | 파트너가 연동 탭을 설정하도록 허용하세요(인앱 이벤트 포스트백 제외). |
| 인앱 이벤트 포스트백 구성 | 파트너가 인앱 이벤트 포스트백을 설정할 수 있도록 허용합니다.<br /><br />**주의!** "연동 구성"과 결합되어 모든 미디어 소스의 오가닉 및 논오가닉 트래픽을 포함한 모든 어트리뷰션 이벤트에 대한 접근 권한을 부여합니다. |
| 리텐션 리포트 액세스 | 파트너의 자체 리텐션 데이터에만 접근을 허용합니다. |
| 집계된 충성 사용자 데이터에 액세스 | 파트너가 충성도 높은 사용자 지표에 접근할 수 있도록 허용합니다. |
| 집약형 전환 데이터에 액세스 | 인스톨, 리인게이지먼트, 리인스톨 및 리어트리뷰션에 대한 지표에 접근할 수 있도록 허용합니다. 예시로 <Anchor target="_blank" href="/partners/ko/docs/aggregated-campaign-performance-report-for-ad-networks">집계 캠페인 성과 보고서</Anchor>가 있습니다. |
| 집약형 인앱 이벤트 데이터 접근 | 파트너에게 포스트백 매핑에 구성된 이벤트뿐만 아니라 Protect360 데이터를 포함한 모든 인앱 이벤트 데이터에 대한 접근 권한을 부여하십시오.  <br />여기에는 광고 수익화 데이터에 대한 접근 권한도 포함되며, 해당 데이터에는 다른 미디어 소스의 이벤트가 포함될 수 있습니다. |
| 유효성 검증 규칙 보기 | 파트너가 검증 규칙 세부 정보를 볼 수 있도록 허용합니다. |
| 집약형 수익 데이터 접근 | UA 최적화를 위한 광고 수익 데이터에 접근할 수 있도록 허용합니다. |
| 비용 가져오기 사용 | 파트너가 비용 데이터를 Cost Import를 사용하여 업로드할 수 있도록 허용합니다. |
| Protect360 대시보드 및 로데이터에 접근 | <ul><li>로데이터 접근은 귀하의 구독 상품에 Protect360, 검증 규칙 또는 로데이터가 포함된 경우에만 가능합니다.</li><li>ProtectLITE를 포함한 Protect360 대시보드에 대한 접근을 부여합니다.</li><li>**참고:** ProtectLITE는 대시보드 접근을 포함하지만 로데이터 접근을 제공하지 않습니다.</li></ul> |

</Accordion>

<div id="setting-up-roku-ads-integration-for-agencies" />

## 에이전시를 위한 Roku Ads 연동 설정

광고주를 대신하여 일하는 에이전시는 Roku Ads 연동을 켜고 캠페인에 대한 어트리뷰션을 시작할 수 있습니다. 그러나 이 연동은 에이전시에 대한 몇 가지 제한 사항이 있습니다.

<div id="agency-limitations" />

### 에이전시 제한 사항

* 에이전시는 함께 일하는 광고주가 먼저 Roku Ads를 활성화한 후에야 Roku Ads 연동에 액세스할 수 있습니다.
* 에이전시의 연동 페이지에 표시되는 어트리뷰션 매개변수는 광고주의 설정을 그대로 상속받아보기 전용 모드로 나타납니다.

**에이전시를 위한 Roku Ads를 설정하려면:**

1. AppsFlyer에서 사이드바에서 <Image alt="collaborate.png" src="https://files.readme.io/70400e32ef967b981aabd47faf97880368585fdf52ad29c0d4c2d4c31751e6a3-37844129188753.png" width="2%" /> **협업** > **파트너 마켓플레이스**를 엽니다.
2. **Roku Ads (rokuads\_int)** 를 선택합니다.
3. 귀하의 에이전시 **Roku Ads 계정 ID**를 입력합니다. 이를 통해 에이전시 트래픽을 확인하고 광고주 트래픽과 구별할 수 있습니다.
4. **연동 저장**을 클릭합니다.

<div id="warning" />

> ❗️ **경고**
>
> Roku Ads 계정 ID는 광고주와 에이전시 사이에 공유되어서는 안 됩니다. 공유된 경우 모든 광고주의 인스톨이 에이전시의 대시보드에 자동으로 어트리뷰션됩니다.

<div data-zendesk-anchors="overview=roku-ads-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC roku-attribution-flow=roku-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%9D%90%EB%A6%84 01H7Z13QPBTKZ9BVCMGASYEM0R=roku-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%9D%90%EB%A6%84 setting-up-roku-ads=%EA%B4%91%EA%B3%A0%EC%A3%BC%EB%A5%BC-%EC%9C%84%ED%95%9C-roku-ads-%EC%97%B0%EB%8F%99-%EC%84%A4%EC%A0%95 general-settings=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 h_01K0P7PHA89T432XNW0C4BZ4VH=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 install-attribution=%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 h_01K0P7PHA8X7E7MC7JNVG86JAV=%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 reengagement-attribution=%EB%A6%AC%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 h_01K0P7PHA8GR0SYPNKSP4D90AF=%EB%A6%AC%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 ignore-active-users-for-retargeting=%EB%A6%AC%ED%83%80%EA%B9%83%ED%8C%85-%EC%8B%9C-%ED%99%9C%EC%84%B1-%EC%9C%A0%EC%A0%80-%EB%AC%B4%EC%8B%9C h_01K0P7PHA85619R1SM4SR49TQ3=%EB%A6%AC%ED%83%80%EA%B9%83%ED%8C%85-%EC%8B%9C-%ED%99%9C%EC%84%B1-%EC%9C%A0%EC%A0%80-%EB%AC%B4%EC%8B%9C crossplatform-attribution=%ED%81%AC%EB%A1%9C%EC%8A%A4-%ED%94%8C%EB%9E%AB%ED%8F%BC-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 h_01K0P7PHA80KKG06719ZWE8JB0=%ED%81%AC%EB%A1%9C%EC%8A%A4-%ED%94%8C%EB%9E%AB%ED%8F%BC-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 inapp-events-postbacks=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01K0P7PHA89Y8W70NTF40S6PC4=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 cost-tab-for-cost-clicks-and-impressions=cost-tab h_01K0P7PHA840N225ABCSGTTCAN=%EC%A4%91%EC%9A%94 types-of-permissions-advertisers-can-grant-to-roku-ads=%EA%B4%91%EA%B3%A0%EC%A3%BC%EA%B0%80-roku-ads%EC%97%90-%EB%B6%80%EC%97%AC%ED%95%A0-%EC%88%98-%EC%9E%88%EB%8A%94-%EA%B6%8C%ED%95%9C%EC%9D%98-%EC%9C%A0%ED%98%95 h_01K0P7PHA8D7WQR02129YADZZP=%EA%B4%91%EA%B3%A0%EC%A3%BC%EA%B0%80-roku-ads%EC%97%90-%EB%B6%80%EC%97%AC%ED%95%A0-%EC%88%98-%EC%9E%88%EB%8A%94-%EA%B6%8C%ED%95%9C%EC%9D%98-%EC%9C%A0%ED%98%95 setting-up-agencies=%EC%97%90%EC%9D%B4%EC%A0%84%EC%8B%9C%EB%A5%BC-%EC%9C%84%ED%95%9C-roku-ads-%EC%97%B0%EB%8F%99-%EC%84%A4%EC%A0%95 setting-up-roku-ads-integration-for-agencies=%EC%97%90%EC%9D%B4%EC%A0%84%EC%8B%9C%EB%A5%BC-%EC%9C%84%ED%95%9C-roku-ads-%EC%97%B0%EB%8F%99-%EC%84%A4%EC%A0%95 agency-limitations=%EC%97%90%EC%9D%B4%EC%A0%84%EC%8B%9C-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD h_01K0P7PHA8MSV6Q13P9ATAX8SJ=%EC%97%90%EC%9D%B4%EC%A0%84%EC%8B%9C-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD h_01K0P7PHA8KXP5H9WXJ1J2VFR2=%EA%B2%BD%EA%B3%A0" />
