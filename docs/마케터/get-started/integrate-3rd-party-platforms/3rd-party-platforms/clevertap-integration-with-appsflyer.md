---
title: CleverTap ESP와 앱스플라이어 연동
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Clevertap
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2018-07-12T06:26:58Z'
  edited_at: '2026-10-14T10:30:57Z'
  id: 360001299165
  locale: ko
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ko/articles/360001299165
---
> **한눈에 보기:**

<Image align="center" alt="clevertap-logo.png" src="https://files.readme.io/ee01a7da1ae0c77758e279c47f2f588d90fdb7f52dce51161fce3891cc5fd498-4405112002833.png" width="193px" />

<div id="note" />

<div id="obtain-clevertap-account-token" />

<div id="important-1" />

<div id="important" />

> 🚧 **중요!**
>
> <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions#미디어-소스-제한">일부 매체 소스</Anchor>는 제3자와 데이터 공유를 제한합니다. 따라서 포스트백 전송 설정에 관계없이 제한된 이벤트 포스트백은 이 파트너에게 전송되지 않습니다.


**<span id="setting-up-clevertap"></span>전제 조건:** 연동 설정 전에 <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations#contact-details">파트너에게 연락</Anchor>하여 계정을 개설하세요.

**연동 활성화 또는 편집 방법:**

1. To activate:연동 활성화 방법: 앱스플라이어의 사이드 메뉴에서협업<strong>></strong>파트너 마켓플레이스를 선택합니다.  
   <strong>편집 방법:</strong> 앱스플라이어의 사이드 메뉴에서 <strong>협업</strong>> 활성화된 연동을 선택합니다.
2. 파트너를 검색하고 선택합니다.
3. **연동 설정**을 클릭하십시오. 연동 설정 페이지로 이동합니다.
4. **연동** 탭에서 연동할 앱을 선택하고 **파트너 활성화**를 켭니다.  
   **참고: 파트너와 협력하는 동안 토글은 반드시 켜져**(활성화)/strong> 있어야 합니다.
5. 아래 설명된 대로 관련 탭을 사용하여 설정을 완료하십시오.

<div id="integration-tab" />

<Accordion title="연동 탭">

연동 탭은 아래와 같이 다양한 섹션으로 나누어져 있습니다.

<div id="activate-partner" />

### 파트너 활성화

<Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation#파트너-연동-활성화">파트너 활성화</Anchor>에 대해 더 알아보십시오.

<div id="general-settings" />

### 일반 설정

<Image align="center" alt="CleverTap_msc_new_2.png" src="https://files.readme.io/dd3f79fdce7dc4d48605f18021e328754d3e78aae98cb5214466c7489fd29fdf-360002305685.png" />


1. <Image align="center" alt="CleverTap_msc_new_4.png" src="https://files.readme.io/2fd248582c3e267b2eaacfc6bf49068bdd4c6811b066c8286f0059e18d8535ae-360002541969.png" />

   <Image align="center" alt="CleverTap_msc_new_5.png" src="https://files.readme.io/795086dfc16cdee369b470e0b598b5089fff6469c77d0ccbf929e230d94191c8-360002537945.png" />

<div id="default-postbacks" />

### 기본 포스트백

앱스플라이어는 유저 인스톨 후 자동 포스트백을 믹스패널로 전송할 수 있습니다. 이 섹션을 사용하여 각 이벤트에 대해 포스트백을 보내는 유저 소스를 정의합니다. <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#default-postbacks">기본 포스트백</Anchor>에 대해 자세히 알아보세요.

<Image align="center" alt="clevertap-default-postbacks_en-us.png" src="https://files.readme.io/58424df9f5e8ba0e30e2390e26e0ecec7fc827baa43f3b812181caa2283dca0a-360014085238.png" />

**앱을 다운로드하는 모든 유저에 대한 포스트백을 믹스패널로 전송하려면** **모든 미디어소스(오가닉 포함)** 를 선택하세요.

<div id="measure-clevertap-owned-media" />

<div id="in-app-events-settings" />

### 인앱 이벤트 설정

<Image align="center" alt="clevertap-in-app-events_en-us.png" src="https://files.readme.io/2ccc8a5a62cd601c45647d72caff0d94af814f78d9e1a8ae1548f973ed4c554f-360014005017.png" />

<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">인앱 이벤트 포스트백</Anchor>에 대해 자세히 알아보세요.

**인앱 이벤트 포스트백 구성 방법:**

2. 인앱 이벤트 포스트백을 설정합니다.
3. SDK 이벤트를 목록에 추가하려면 이벤트 추가를 클릭합니다.
5. 수익 보내기 드롭다운 메뉴에서 필요한 옵션을 선택합니다.
   * **값 없음 및 수익 없음:** 이벤트 값을 제외하고 이벤트만 전송합니다.
   * **값 있음 및 수익 없음:** 매출 값을 제외한 모든 파라미터를 전송합니다.
   * **값 있음 및 수익 있음**: 매출 값(이벤트에 존재하는 경우)을 포함하여 모든 이벤트 파라미터를 전송합니다.
6. 연동 구성을 완료하려면 **연동 저장**을 클릭합니다.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="어트리뷰션 링크 탭">

이 파트너에 대해 어트리뷰션 링크를 사용할 수 없습니다.

</Accordion>

<div id="cost-tab" />

<Accordion title="비용 탭">

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="광고 수익 탭">

</Accordion>

<div id="permissions-tab" />

<Accordion title="권한 탭">

</Accordion>

<div data-zendesk-anchors="h_01H9FK5JT1TM77CAH0JTDCV376=%EC%A4%91%EC%9A%94 h_01H9FK5JT1ATCHY6WAVB6E2YEW=setting-up-clevertap h_01HKW9C39FKN3QN21NKDS6N3BQ=integration-tab activate-partner=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 h_01H9FK5JT12Z1M6WW3GQQF5QVN=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 general-settings=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 h_01H9FK5JT1FMC6JANBP9KBB0V2=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 h_01H9FK5JT1MQKT7KWJ3EVNEA1E=%EC%A4%91%EC%9A%94 obtain-clevertap-account-token=%EC%A4%91%EC%9A%94 h_01H9FK5JT1RVJ1V0CGXSH1XZPM=%EC%A4%91%EC%9A%94 h_01H9FK5JT2QV9CKSZ1N3S4WTGE=%EC%A4%91%EC%9A%94 default-postbacks=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01H9FK5JT2CE0WQ9HAGVGAQA5B=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 inapp-events-settings=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95 h_01H9FK5JT2YS7G5WDD4F5MPYVZ=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95 h_01H9FK5JT2939VDXQCDDG7MZ0R=attribution-link-tab h_01H9FK5JT2AEDDCD11K77WJHBX=cost-tab h_01H9FK5JT2WYWRGZAS1HBYYBSJ=ad-revenue-tab h_01H9FK5JT2FD6WN3Z1RET108JZ=permissions-tab measure-clevertap-owned-media=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95 h_01H9FK5JT2AZTT5936DD88ZZV3=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95" />
