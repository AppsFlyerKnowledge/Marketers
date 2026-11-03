---
title: X Ads(이전의 Twitter Ads) 연동 설정
metadata:
  keywords:
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
  created_at: '2021-11-09T09:33:40Z'
  edited_at: '2026-10-14T10:28:57Z'
  id: 4410472471825
  locale: ko
  section: X Ads (formerly Twitter Ads)
  section_id: 6551370375569
  url: https://support.appsflyer.com/hc/ko/articles/4410472471825
---
> **한눈에 보기:** X Ads 계정을 앱스플라이어와 연동하여 X Ads 캠페인의 어트리뷰션 데이터를 표시합니다.

## 개요

X Ads는 고급 SRN(Self-Reporting Network)으로, 앱스플라이어가 광고 ID가 없는 사용자를 포함한 모든 사용자의 전환 이벤트를 기여 감정할 수 있도록 지원합니다.

### 앱스플라이어 내 X-Ads 어트리뷰션 플로우

**X Ads에 대한 앱스플라이어 어트리뷰션 플로우는 다음과 같습니다.**

1. 앱스플라이어는 서버 간(S2S) 연동을 통해 X Ads로부터 모든 인게이지먼트 데이터를 수신하며, 해당 인게이지먼트를 다음과 같이 어트리뷰션합니다.
   * 설치 이벤트와 인게이지먼트 모두에 모바일 광고 ID(MAID)가 포함된 경우, 앱스플라이어는 확정적 ID 매칭을 수행합니다.
   * 설치 또는 인게이지먼트 중 하나라도 MAID가 누락된 경우, 앱스플라이어는 어트리뷰션을 위해 확률적 모델링(PMOD)을 적용합니다.
2. 앱스플라이어는 설치가 X Ads에 어트리뷰션되었는지 여부와 관계없이, 연동을 통해 모든 설치 포스트백을 X Ads로 전송합니다.
3. 사용자가 앱 추적 투명성(ATT) 동의를 거부하고 고도화된 개인정보 보호(AP)가 활성화된 경우, X Ads로 전송되는 포스트백 내 일부 필드가 제한됩니다. 제한된 필드는 다음과 같습니다.

   * X Ads 참여 ID
   * 해시된 장치 ID
   * IP 주소
   * 사용자 에이전트

   [![_- visual selection.png](https://files.readme.io/8c17755d275e732f88cf93e8e7e33df891911dd640d2dbfc2637313a9d59d43e-small-36433399199249.png)](https://files.readme.io/8c17755d275e732f88cf93e8e7e33df891911dd640d2dbfc2637313a9d59d43e-small-36433399199249.png)

## X Ads 계정을 앱스플라이어에 연동하기

> 📘 **참고**
>
> 시작하기 전에 X Ads 계정에 <Anchor target="_blank" href="https://business.X%20Ads.com/en/help/account-setup/billing-basics.html">결제 수단이 등록</Anchor>되어 있는지 확인하세요. 그렇지 않으면 앱스플라이어에서 파트너 연동을 활성화할 수 없습니다.

1. <Anchor target="_blank" href="https://business.x.com/en/advertising">X Ads.</Anchor>에서 X Ads 계정에 로그인하세요.  
   광고 페이지로 자동 이동되지 않는 경우, 좌측 상단의 광고 버튼을 클릭하세요.
2. **심플(신규)** 또는**어드밴스드** 캠페인 중 하나를 선택하라는 안내가 나오면 **어드밴스드**를 선택하세요.
3. **캠페인 목표** 아래에서 **앱 설치** 또는 **앱 리엔게이지먼트**를 선택한 후 **다음**을 클릭하세요.

   ![X-Ads-campaign-objective.png](https://files.readme.io/44e5aca3895fc5aefa22f91542b9c23f9798b246ac8086e97a3994244fc2c5a8-36433415100561.png)
4. 앱을 선택한 후 **모바일 측정 파트너** 링크를 클릭하세요.
5. **전환 추적** 페이지에서 **앱스플라이어로로 이동**을 눌러주시기 바랍니다.

   ![X-Ads-mmp-selection.png](https://files.readme.io/718bc93d2fcf606a8c165aed70364659ba23b74891b22775c5522ee9e4c7901a-36433422307345.png)
6. X Ads를 떠나 앱스플라이어 웹사이트로 이동한다는 안내 알림이 표시됩니다. **앱스플라이어로 이동**을 클릭하고 대시보드에 로그인합니다.
7. 앱스플라이어의 사이드 메뉴에서 **협업** > **활성화된 연동**을 선택합니다.
8. **X Ads**를 검색하여 선택합니다.
9. **연동** 탭에서 모바일 앱 전환 기록(MACT)에 대한 X Ads 이용약관에 동의한 후 **연동 저장**을 클릭하세요.
10. **파트너 활성화**를 켜고 **X Ads로 로그인**을 클릭하세요.
11. **앱 승인**을 클릭하여 앱스플라이어가 X Ads 계정을 사용할 수 있도록 승인합니다.
12. **파트너 활성화**를 다시 켜서 **연동** 탭 설정을 표시하고 어트리뷰션을 활성화 하세요.  
    **참고:** 토글은 파트너와 함께 작업하는 동안 켜져(활성화) 있어야 합니다. <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">파트너 활성화</Anchor>에 대해 더 알아보세요.
13. X Ads 계정을 선택하여 활성화한 다음 **저장 및 닫기**를 클릭합니다.

## X Ads 어트리뷰션 설정

파트너 설정 페이지의 상단 메뉴에 대한 자세한 설명은 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner">여기</Anchor>를 클릭하십시오.

<div id="integration-tab" />

<Accordion title="연동 탭">

**연동 탭**은 아래 설명된 것처럼 여러 섹션으로 나누어져 있습니다. 설정을 사용 가능하게 하려면 첫 번째 방문에서 <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">파트너가 활성화되어야 합니다</Anchor>.

### 연결 광고 계정

어트리뷰션을 활성화할 계정을 선택합니다.

![X-Ads_msc_new_4.png](https://files.readme.io/8b8ecdfd79bc87d4a65766ce67e48a06524d825e04d5e642eb5e9741069a2f6c-36433422308241.png)

**참고:** 앱스플라이어에서 최대 200개의 광고 계정을 연결할 수 있습니다. 이 한도에 도달하는 것을 방지하고 모든 활성 계정에 대해 연속적인 어트리뷰션을 보장하려면, 더 이상 사용하지 않는 광고 계정을 삭제하는 것을 권장합니다.

### 고급 개인정보 보호

iOS 앱 전용: **고급 개인정보 보호(AP)** 토글을 사용하면 포스트백을 통해 X Ads와 공유되는 사용자 데이터의 수준을 제어할 수 있습니다. 이 설정은 iOS 14.5+ 개인 정보 요구 사항을 준수합니다.  
AP 토글이 켜져 있을 때:

* 포스트백은 <Anchor target="_blank" href="/partners/ko/docs/advanced-privacy-guide-postback-macros-for-ad-networks">고급 개인정보 보호 템플릿</Anchor>을 따릅니다.
* 오직 <Anchor target="_blank" href="/marketers/ko/docs/apply-aggregated-advanced-privacy-framework">집계되고 익명화된 데이터</Anchor>만 공유됩니다. 장치 수준 식별자는 포함되지 않습니다.

> 📘 **참고**
>
> * X Ads 연동을 활성화할 때 고급 개인정보 보호 토글은 기본적으로 켜져(On) 있습니다.
> * X Ads에 따르면, 고급 개인 정보 보호 **켜짐**을 유지하면 캠페인 이벤트의 **보고 누락**이 발생하고 X Ads에서 성능 최적화가 제한될 수 있습니다.

### 클릭-쓰루 어트리뷰션

슬라이더를 사용하여 **클릭에서 설치까지 최대 시간**을 설정하십시오. 기여 인정 기간 내에 이루어진 설치(최초 실행) 건에 한해서만 X Ads로 어트리뷰션될 수 있습니다.

이 값을 1&#126;23시간 또는 1&#126;30일로 맞춤 설정할 수 있습니다. X Ads와 일치하도록, 클릭-쓰루 기여 기간을 14일로 설정하는 것을 추천합니다.

![X-Ads_msc_new_6.png](https://files.readme.io/359f6145751f45d38c151572f1ba0c525d232d16ffaee6b68453da0bc1826a69-36433422308369.png)

### 뷰-쓰루 어트리뷰션 룩백 윈도우

이 슬라이더를 사용하여 **노출에서 설치까지의 최대 시간**을 설정할 수 있습니다. 광고 노출 후 다른 관련 광고 클릭이 없었던 경우, 해당 룩백 윈도우 이내에 발생한 설치(첫 실행)만 X Ads로 어트리뷰션됩니다.

이 값을 1-23시간 또는 1-7일로 사용자 정의할 수 있습니다. X Ads와 일치하도록, 인스톨 노출 룩백 윈도우를 1일로 설정하는 것을 추천합니다.

![X-Ads_msc_new_7.png](https://files.readme.io/15c9d815b05c03dfdf8578ed5af297c411991ab74accc5539fc1dbca178c3336-36433422308497.png)

### 설정 재설치

재설치 어트리뷰션을 활성화하려면 **재설치 어트리뷰션** 토글을 켭니다.

재설치 어트리뷰션에 대한 룩백 윈도우는 설정을 따로 진행할 필요가 없습니다. 해당 값은 설치 어트리뷰션 설정값을 그대로 가져옵니다.

### 리인게이지먼트 설정

X Ads의 리타겟팅 캠페인의 경우, 앱스플라이어는 리엔게이지먼트 측정만 지원합니다. 이는 참여 시점에 이미 앱이 설치되어 있는 사용자가 리타겟팅 캠페인에 참여한 건을 의미합니다.

> 🚧 **중요!**
>
> 앱 설정 페이지에서 앱의 리타겟팅이 활성화되어 있는지 확인하세요. 더 자세한 내용을 보려면 <Anchor target="_blank" href="/marketers/ko/docs/app-settings#reengagement-attribution">여기</Anchor>를 클릭하세요.

X Ads 리타겟팅 어트리뷰션은 리인게이지먼트 전환만 포함합니다.

**리인게이지먼트 어트리뷰션** 토글을 켜서 X Ads에 대한 리인게이지먼트 어트리뷰션을 시작합니다.

#### 리인게이지먼트 클릭-쓰루 룩백 윈도우

**리인게이지먼트 클릭-쓰루 룩백 윈도우**를 설정합니다. (광고가 클릭된 후, 리타게팅된 사용자가 해당 광고에 어트리뷰션될 수 있는 최대 기간) 그 값은 시간(최대 23시간) 또는 일(1&#126;30일)로 설정할 수 있습니다.

![X-Ads-reengagement-activate.png](https://files.readme.io/318deeab0432870035a163a7b8a5b8c03be7d683bfc369104c8577674fde0036-36433422309905.png)

#### 리인게이지먼트 뷰-쓰루 룩백 윈도우

리타게팅 광고의 노출 어트리뷰션을 시작하려면, **리인게이지먼트 뷰-쓰루 어트리뷰션**을 활성화합니다.

그리고, **리인게이지먼트 뷰-쓰루 룩백 윈도우**를 설정합니다. (광고가 노출된 후, 리타게팅된 사용자가 해당 광고에 어트리뷰션될 수 있는 최대 기간) 그 값은 시간(최대 23시간) 또는 일(1&#126;7일)로 설정할 수 있습니다.

![X-Ads-reengagement-view-through.png](https://files.readme.io/4faf93b6d8a8e45043eb9440d8f56a70eba2da51f3a572ea6cd698e072f033c6-36433415112849.png)

#### 리인게이지먼트 윈도우

**리인게이지먼트 윈도우**(사용자의 인앱 이벤트가 리타겟팅 미디어 소스로 어트리뷰션되는 기간)를 설정합니다. 값은 '일(1-90)', '시간(최대 23)', 또는 '라이프타임'으로 설정할 수 있습니다.

<Image alt="X-Ads-reengagement-window.png" src="https://files.readme.io/5bc42bd967929a88fd38f8bdd9cc36046a6f0381d1883ab1f26f5c680185a74c-36433415113105.png" width="628px" />

#### 리타게팅 시 활성 사용자 제외

지정된 기간 내 활성 사용자에 대한 리타겟팅 전환이 기록되지 않도록 비활성 기간을 설정합니다. <Anchor target="_blank" href="/marketers/ko/docs/set-retargeting-inactivity-window">리타겟팅 비활성 기간</Anchor>에 대해 자세히 알아보세요.

### 인앱이벤트 포스트백 설정

이 섹션에서는 포스트백을 통해 앱스플라이어 이벤트를 파트너와 매핑할 수 있습니다.

[![In-app_event_postbacks_en-us.png](https://files.readme.io/d89725172c53c309b5b58227ce53812e12f9cd4ee7611a6c375970b395122b15-36433415113361.png)](https://files.readme.io/d89725172c53c309b5b58227ce53812e12f9cd4ee7611a6c375970b395122b15-36433415113361.png)

**인앱 이벤트 포스트백 설정 방법:**

1. **파트너 ID**를 설정합니다(필요한 경우).
2. **인앱 이벤트 포스트백**을 설정합니다.
3. **이벤트 추가**를 클릭하여 목록에 SDK 또는 서버 간 이벤트를 추가합니다.
4. 아래 표에 따라 필수 파라미터를 작성합니다.  

| 파라미터 | 설명 |
| --- | --- |
| **앱스플라이어 이벤트** | 이벤트의 이름은 앱스플라이어가 귀하의 앱에 연동된 SDK로부터 수신했거나 서버-투-서버 이벤트로부터 수신하여 나타나는 이름입니다.<br />**팁**: 찾고 있는 이벤트가 없나요?<ul><li>논오가닉 인스톨과 재점검으로 디바이스에 이벤트가 활성화되었는지 확인합니다.</li><li>**앱스플라이어 이벤트**에 입력한 다음 **커스텀 생성**을 클릭합니다. <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#커스텀-이벤트">커스텀 이벤트 매핑</Anchor>에 대해 더 알아보세요.</li></ul> |
| **파트너 이벤트에 매핑** | 파트너 측에서 정의한 각 이벤트의 고유한 이름 또는 ID입니다. 드롭다운 상자에서 가장 적합한 사전 정의된 앱스플라이어 이벤트를 선택하세요. |
| **사용자 유입** | 이벤트의 전송 옵션을 선택합니다.<br /><br /><br /><br />**<span id="h_01HDJVBAEZATGM580CNC7BCVTN"></span>참고**<br />X Ads에서 에이전시 어트리뷰트 포스트백을 수신하려면 **오가닉을 포함한 모든 미디어 소스**를 선택해야 합니다. 그렇지 않으면 X Ads는 이러한 포스트백을 수신하지 않습니다.<ul><li>**이 파트너만**: 이 이벤트가 이 파트너에게 귀속된 경우에만 포스트백을 발송합니다.</li><li>**오가닉을 포함한 모든 미디어 소스**: 파트너 및 오가닉 이벤트에 어트리뷰트된 이벤트에 대한 포스트백을 전송합니다.</li></ul> |
| **포함** | <ul><li>**데이터 없음(기본값)**: 이벤트 값 없이 이벤트 자체만 보냅니다.</li><li>**값 및 수익**: 매출 값(이벤트에 존재하는 경우)을 **포함하여** 모든 이벤트 파라미터를 전송합니다.</li><li>**수익이 없는 값**: 수익 값을 **제외한** 모든 파라미터를 전송합니다.</li></ul> |

5. [선택 사항] <Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" />를 클릭하여 특정 인앱 이벤트를 파트너에게 발송하기 위한 조건을 설정하세요.  
   <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#조건부-인앱-이벤트-포스트백">조건적인 인앱 이벤트 포스트백</Anchor>에 대해 알아보세요.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="어트리뷰션 링크 탭">

X Ads는 어트리뷰션을 위해 어트리뷰션 링크를 사용하지 않습니다.

> 📘 **참고**
>
> Meta 광고, Apple Search Ads, Google Ads, X Ads 등과 같은 모든 <Anchor target="_blank" href="/marketers/ko/docs/self-reporting-networks-srns">SRN(self-reporting networks)</Anchor>의 경우 외부 어트리뷰션 링크를 사용하지 않으므로 이 탭이 작동하지 않습니다.

</Accordion>

<div id="cost-tab" />

<Accordion title="비용 탭">

비용 연동은 다음의 집약형 데이터를 제공합니다.

* 캠페인, 광고 세트, 광고, 채널 및 지역/국가에 대한 비용 데이터입니다. 지원되는 디멘션, 메트릭 및 기능에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">애드 네트워크 비용 연동 표</Anchor>를 참조하세요.  
  **참고:** 비용 데이터를 사용하려면 <Anchor target="_blank" href="/marketers/ko/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor> 구독이 필요합니다.
* 클릭 수에 대한 데이터, 노출 횟수, 보강된 데이터(키워드, 캠페인 이름, 광고 세트).

**비용 API를 활성화 하려면**:

* <Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#비용-api-활성화">이 연동 지침</Anchor>을 따르세요.

<Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">비용 API 상태</Anchor>와 앱스플라이어가 마지막으로 일치하는 비용 데이터를 가져온 시간은 비용(및 광고 수익) 연동 상태 대시보드 또는 각 애드 네트워크별 대시보드에서 확인할 수 있습니다.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="광고 수익 탭">

X Ads의 경우 광고 수익을 사용할 수 없습니다.

</Accordion>

<div id="permissions-tab" />

<Accordion title="권한 탭">

이 탭에서는 X Ads에 애드 네트워크, 에이전시 또는 양쪽 모두로 활동하는지에 따라 부여할 권한을 선택할 수 있습니다. X Ads에 대한 어트리뷰션이 비활성화되어 있더라도 권한 탭은 활성화되어 있으며 X Ads에 제어 권한을 부여할 수 있습니다.

이러한 토글을 사용하면 앱에 대한 설정 권한을 광고 네트워크에 부여할 수 있습니다.

### 애드 네트워크 권한

* **파트너 연동 설정 허용** - 파트너가 연동 탭을 설정할 수 있도록 허용(인앱이벤트 포스트백 제외)
* **인앱이벤트 포스트백 설정 허용** - 파트너가 연동 탭에서 자사와 인앱이벤트 포스트백을 매핑할 수 있도록 허용
* **리텐션 리포트 액세스 허용** - 파트너가 유입시킨 유저의 리텐션 데이터만 해당
* **종합 로열 유저 데이터 접근 허용** - 파트너 자사만의 로열 유저에만 해당
* **통합 인앱이벤트 데이터 액세스 허용**- 파트너가 유입시킨 유저의 인앱이벤트 데이터만 해당
* **종합 수익 데이터 접근 허용** - 파트너 자사에 어트리뷰션되는 수익 데이터만 해당
* **Protect360 대시보드 액세스 허용** - 파트너 자사의 Protect360 데이터에만 해당되며, 이 기능을 사용하고 있는 광고주만 부여 가능

<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#permissions-tab">광고 네트워크 권한</Anchor> 부여에 대해 자세히 알아보세요.

### 에이전시 권한

<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#에이전시-권한">에이전시 권한 부여</Anchor>에 대해 알아보세요.

</Accordion>

## X-Ads 기능

<div id="mobile-app-promotion-on-x-ads" />

<Accordion title="X Ads의 모바일 앱 프로모션">

X Ads 모바일 앱 프로모션은 트위터에 앱을 프로모션하는 방식입니다. 앱 광고주가 트위터의 앱 카드 디자인을 이용하여 설치, 앱 참여 및 딥링킹을 유도할 수 있습니다. 앱 유저는 X Ads 타임라인에서 바로 앱을 설치하고 쉽게 사용할 수 있습니다.

</Accordion>

<div id="webtoapp-measuring-app-activity-for-nonapp-campaigns-android-only" />

<Accordion title="웹-to-앱 비앱 캠페인에 대한 앱 활동 측정(안드로이드 전용)">

앱스플라이어와 X Ads의 연동을 통해 Android 환경의 **비앱 캠페인**에서도 설치, 리엔게이지먼트, 인앱 이벤트를 포함한 앱 활동을 측정할 수 있습니다.

예를 들어, 광고 목적지가 **웹 랜딩 페이지**인 경우에도 앱 설치 및 기타 설치 후 활동을 측정할 수 있어 웹에서 앱(W2A) 사용자 여정을 측정할 수 있습니다.

X 비앱 캠페인에서 앱 활동을 측정하고 사용자 행동에 대한 유용한 인사이트를 얻으려면, X Ads Manager에서 다음 단계를 진행하세요.

1. X Ads 관리자에서 캠페인 생성 양식으로 이동합니다.
2. **게재** 섹션에서 **앱 전환** 측정을 활성화하여 캠페인을 통해 발생하는 설치 및 인앱 전환을 추적할 수 있도록 설정하세요. 자세한 내용은 <Anchor target="_blank" href="https://business.x.com/en/help/campaign-setup/create-an-app-installs-campaign/mobile-app-measurement-and-attribution">X Ads 설명서</Anchor> (*"Measuring app conversions on non-app objectives" 섹션*)를 참조하세요.

> 🚧 **중요!**
>
> 이 기능은 현재 **Android에서만 지원됩니다**.

</Accordion>

<div id="twitter-ads-and-appsflyer-skan-interoperation" />

<Accordion title="X Ads 및 앱스플라이어 SKAN 상호 운용성">

X Ads는 SKAdNetwork 포스트백 데이터를 전용 API를 통해 전송합니다. X Ads의 SKAN 데이터가 <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">SKAN 대시보드</Anchor>에 표시됩니다.

X Ads는 다음과 같은 데이터 필드를 사용하여 SKAN 포스트백을 풍부하게 합니다.

* 캠페인 이름
* 캠페인 ID
* 광고세트 이름
* 광고세트 ID

</Accordion>

<div id="twitter-user-privacy" />

<Accordion title="X Ads 사용자 개인정보 보호">

X Ads 광고주와 사용자는 광고주 및 비즈니스 파트너와 정보를 공유하는 방식을 직접 제어할 수 있습니다.

* **2021년 7월 31일**부터 X Ads AMM(Advanced Mobile Measurement) 프로그램에 **등록하지 않은** 광고주는 X Ads MACT 사용자 수준(User-level) 데이터를 더 이상 수신할 수 없습니다. 결과적으로, **모든 X Ads 데이터는 앱스플라이어의 로우 데이터 도구에서 제한**됩니다. <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions#x-ads-formerly-twitter">X Ads 데이터 제한에 대해 자세히 알아보세요.</Anchor>
* 광고주가 AMM 프로그램에 참여 중이고 사용자가 개인정보 처리방침 고지에 동의한 경우, **로우 데이터 제한이 적용되지 않습니다**.
* AMM 참여 여부와 관계없이, 사용자가 EU 지역에 거주하며 비즈니스 파트너와의 데이터 공유에 동의한 경우 **로우 데이터 제한이 적용되지 않습니다**.
* 사용자가 EU 지역에 거주하며 비즈니스 파트너와의 데이터 공유에 동의하지 **않은** 경우, **로우 데이터 제한이 적용됩니다**.
* 집계된 어트리뷰션 데이터는 앱스플라이어에 정상적으로 반영되며, X Ads 정책의 영향을 받지 않습니다.

AMM 프로그램을 통해 광고주는 X Ads에 감사를 수행할 수 있는 권한을 부여함으로써 더욱 완전한 사용자 수준 데이터를 제공받을 수 있습니다. 이 감사는 관련 업계 표준 및 데이터 보호 법률에 따라 X Ads 데이터가 오직 측정 목적으로만 사용되는지 확인하기 위한 것입니다.

<Anchor target="_blank" href="https://business.x.com/en/help/campaign-setup/create-an-app-installs-campaign/mobile-app-measurement-and-attribution">FAQ 섹션에서 AMM 프로그램에 대해 더 알아보세요.</Anchor> 자세한 안내는 X Ads 계정 관리자에게 문의하세요.

</Accordion>

## 고급 SRN 매개변수 이름

X Ads용 Advanced SRN 연동의 아래 항목들은 앱스플라이어 대시보드, 집계 리포트 및 이벤트 수준 로우 데이터 전체에서 기존 항목을 **대체**합니다.

| **앱스플라이어의**  <br />**데이터 열** | **기존 SRN** | 고급 SRN |
| --- | --- | --- |
| **PID** | Twitter | Twitter |
| **캠페인 이름** | 캠페인 이름 | 캠페인 이름 |
| **캠페인 ID** | 캠페인 ID  <br />(base36: 다른 X의 대시보드, 예: 21I3V9) | 캠페인 ID  <br />(base10: X의 대시보드와 동일, 예: 123456789) |
| **애드세트 이름** | 항목 ID  <br />(base36: 다른 X의 대시보드, 예: 21I3V9) | 항목 이름 |
| **광고세트 ID** | 항목 ID  <br />(base36: 다른 X의 대시보드, 예: 21I3V9) | 항목 ID  <br />(base10: X의 대시보드와 동일, 예: 123456789) |
| **광고 이름** | Tweet ID | 광고 이름  <br />(사용 가능한 경우) |
| **광고 ID** | Tweet ID | Tweet ID |
| **Match Type** | SRN (영문) | id\_matching / probabilistic |

## 특징 및 제한 사항

| 특징 | 비고 |
| --- | --- |
| 프리롤 어트리뷰션이 지원되지 않음 | X Ads는 프리롤 캠페인에 대한 MMP 어트리뷰션을 지원하지 않습니다. |
| 광고 이름 "제목 없음" | 광고 이름은 X (이전 Twitter) Ads 데이터 모델에서 필수 필드가 아니므로 누락될 수 있습니다. 광고 이름이 X Ads Manager에 정의되지 않은 경우, 앱스플라이어는 이를 **'제목 없음.** '으로 표시합니다. |
| 비용 | X 광고의 경우 SKAN 전용 캠페인(SKAN 설치만 있고 '일반' 설치가 없는 캠페인)에 대한 비용 데이터는 대행사에서 사용할 수 없습니다. 비용 설정은 광고주가 해야 합니다. 그리고 데이터는 광고주만 볼 수 있습니다. |

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 h_01JV7CGQNZNEM3P98K6KSYKB0D=%EA%B0%9C%EC%9A%94 xads-attribution-flow-in-appsflyer=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EB%82%B4-x-ads-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%94%8C%EB%A1%9C%EC%9A%B0 h_01JZG83EKX39SF8355EW62C462=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EB%82%B4-x-ads-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%94%8C%EB%A1%9C%EC%9A%B0 connecting-your-X-Ads-ads-account-to-appsflyer=x-ads-%EA%B3%84%EC%A0%95%EC%9D%84-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%97%90-%EC%97%B0%EB%8F%99%ED%95%98%EA%B8%B0 h_01HDJVCRYQESA17XZ83GS81YZ3=x-ads-%EA%B3%84%EC%A0%95%EC%9D%84-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%97%90-%EC%97%B0%EB%8F%99%ED%95%98%EA%B8%B0 h_01JV7D6AWYQ981HY6C130B021B=%EC%B0%B8%EA%B3%A0 X-Ads-ads-attribution-setup=x-ads-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%84%A4%EC%A0%95 h_01HDJVBAEZ5W3JH1BN7WXJ08P6=x-ads-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%84%A4%EC%A0%95 h_01HDJVBAEZSFKRXAKQJP58N550=integration-tab ad-account-connected=%EC%97%B0%EA%B2%B0-%EA%B4%91%EA%B3%A0-%EA%B3%84%EC%A0%95 h_01HDJVBAEZD89BSGHQTPR84HSC=%EC%97%B0%EA%B2%B0-%EA%B4%91%EA%B3%A0-%EA%B3%84%EC%A0%95 xads_advanced_privacy_toggle=%EA%B3%A0%EA%B8%89-%EA%B0%9C%EC%9D%B8%EC%A0%95%EB%B3%B4-%EB%B3%B4%ED%98%B8 advanced-privacy=%EA%B3%A0%EA%B8%89-%EA%B0%9C%EC%9D%B8%EC%A0%95%EB%B3%B4-%EB%B3%B4%ED%98%B8 h_01JV7HVQJ2GTP74G6JYB300E71=%EC%B0%B8%EA%B3%A0-1 clickthrough-attribution=%ED%81%B4%EB%A6%AD-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 h_01HDJVBAEZFJWQ6FD4Q4GSPD76=%ED%81%B4%EB%A6%AD-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 viewthrough-attribution-lookback-window=%EB%B7%B0-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A3%A9%EB%B0%B1-%EC%9C%88%EB%8F%84%EC%9A%B0 h_01HDJVBAEZ2H91WBHNSMRQYQ7H=%EB%B7%B0-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A3%A9%EB%B0%B1-%EC%9C%88%EB%8F%84%EC%9A%B0 reinstall-settings=%EC%84%A4%EC%A0%95-%EC%9E%AC%EC%84%A4%EC%B9%98 h_01HDJVBAF0XRWRZJQSS4STH7YN=%EC%84%A4%EC%A0%95-%EC%9E%AC%EC%84%A4%EC%B9%98 reengagement-settings=%EB%A6%AC%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8-%EC%84%A4%EC%A0%95 h_01HDJVBAEZZR1W06YH4XJSBKHV=%EB%A6%AC%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8-%EC%84%A4%EC%A0%95 h_01JV9YQ7ZHRDD2NA5ENQXJQ31V=%EC%A4%91%EC%9A%94 reengagement-clickthrough-lookback-window=%EB%A6%AC%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8-%ED%81%B4%EB%A6%AD-%EC%93%B0%EB%A3%A8-%EB%A3%A9%EB%B0%B1-%EC%9C%88%EB%8F%84%EC%9A%B0 h_01HDJVBAEZ59ERYD2WQQYK6T37=%EB%A6%AC%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8-%ED%81%B4%EB%A6%AD-%EC%93%B0%EB%A3%A8-%EB%A3%A9%EB%B0%B1-%EC%9C%88%EB%8F%84%EC%9A%B0 reengagement-viewthrough-lookback-window=%EB%A6%AC%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8-%EB%B7%B0-%EC%93%B0%EB%A3%A8-%EB%A3%A9%EB%B0%B1-%EC%9C%88%EB%8F%84%EC%9A%B0 h_01HDJVBAEZSCK7430NJ8AMQYVY=%EB%A6%AC%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8-%EB%B7%B0-%EC%93%B0%EB%A3%A8-%EB%A3%A9%EB%B0%B1-%EC%9C%88%EB%8F%84%EC%9A%B0 reengagement-window=%EB%A6%AC%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8-%EC%9C%88%EB%8F%84%EC%9A%B0 h_01HDJVBAEZCMWY5X47FEEFXTBX=%EB%A6%AC%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8-%EC%9C%88%EB%8F%84%EC%9A%B0 ignore-active-users=%EB%A6%AC%ED%83%80%EA%B2%8C%ED%8C%85-%EC%8B%9C-%ED%99%9C%EC%84%B1-%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A0%9C%EC%99%B8 h_01JVC3PWDR9KHEFBQF5NWHCQJN=%EB%A6%AC%ED%83%80%EA%B2%8C%ED%8C%85-%EC%8B%9C-%ED%99%9C%EC%84%B1-%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A0%9C%EC%99%B8 inapp-event-postback-settings=%EC%9D%B8%EC%95%B1%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EC%84%A4%EC%A0%95 h_01HDJVBAEZ5ZM9RDXPWTJPPYVA=%EC%9D%B8%EC%95%B1%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EC%84%A4%EC%A0%95 h_01HDJVBAEZR1Q2SVE9MEQ9EXKP=attribution-link-tab h_01HDJVBAEZ7R7BKFAZYXXBGS5Y=%EC%B0%B8%EA%B3%A0-2 h_01HDJVBAEZYSWN59VNXTDEWX93=cost-tab 01H88VAJH3A2Q0CZXQQZMW6YRC=ad-revenue-tab h_01HDJVBAF0KEVSWJ0EW54AEAWV=permissions-tab ad-network-permissions=%EC%95%A0%EB%93%9C-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EA%B6%8C%ED%95%9C h_01HDJVBAF0BMSCKF6J9NJ019YJ=%EC%95%A0%EB%93%9C-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EA%B6%8C%ED%95%9C agency-permissions=%EC%97%90%EC%9D%B4%EC%A0%84%EC%8B%9C-%EA%B6%8C%ED%95%9C h_01HDJVBAF0W3ZE7J93CRE8EBRP=%EC%97%90%EC%9D%B4%EC%A0%84%EC%8B%9C-%EA%B6%8C%ED%95%9C x-ad-features=x-ads-%EA%B8%B0%EB%8A%A5 h_01JZWQA6DXRZ17SRVT4HM2MQSH=x-ads-%EA%B8%B0%EB%8A%A5 h_01JZWQA6DX3BRNG8B5CJGA57AM=mobile-app-promotion-on-x-ads h_01JZWQA6DX7W9102P5S6KWJ1WB=webtoapp-measuring-app-activity-for-nonapp-campaigns-android-only h_01JZWQA6DX8AX5XG3W4A6XB53S=%EC%A4%91%EC%9A%94-1 h_01H9QR6TH74PKBGM5RC4M118GE=twitter-ads-and-appsflyer-skan-interoperation h_01H9QR6TH74R50K00H7FYN61KC=twitter-user-privacy x-ads-data-differences=%EA%B3%A0%EA%B8%89-srn-%EB%A7%A4%EA%B0%9C%EB%B3%80%EC%88%98-%EC%9D%B4%EB%A6%84 advanced-srn-parameter-names=%EA%B3%A0%EA%B8%89-srn-%EB%A7%A4%EA%B0%9C%EB%B3%80%EC%88%98-%EC%9D%B4%EB%A6%84 traits-and-limitations=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD h_01JYGPBHHNQARG3GRMQJA95JKD=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD" />
