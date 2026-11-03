---
title: 앱스플라이어와 Adobe Analytics의 연동
metadata:
  keywords:
    - GameAnalytics
    - integrated partner
    - Advertisers
    - Ad Networks
    - game
    - game analytics
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
  created_at: '2015-12-24T11:42:56Z'
  edited_at: '2026-10-14T10:33:42Z'
  id: 207447143
  locale: ko
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ko/articles/207447143
---
> **한눈에 보기:**

> 🚧 **중요!**
>
> <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions#미디어-소스-제한">일부 매체 소스</Anchor>는 제3자와 데이터 공유를 제한합니다. 따라서 포스트백 전송 설정에 관계없이 제한된 이벤트 포스트백은 이 파트너에게 전송되지 않습니다.


**<span id="setting-up-gameanalytics"></span>전제 조건:** 연동 설정 전에 <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations#contact-details">파트너에게 연락</Anchor>하여 계정을 개설하세요.

**연동 활성화 또는 편집 방법:**

1. To activate:연동 활성화 방법: 앱스플라이어의 사이드 메뉴에서협업**>**파트너 마켓플레이스**를 선택합니다.  
   **편집 방법:** 앱스플라이어의 사이드 메뉴에서 **협업**> 활성화된 연동을 선택합니다.**
2. 파트너를 검색하고 선택합니다.
3. **연동 설정**을 클릭하십시오. 연동 설정 페이지로 이동합니다.
4. **연동** 탭에서 연동할 앱을 선택하고 **파트너 활성화**를 켭니다.   
   **참고: 파트너와의 작업 동안 토글이 활성화되어 있어야 합니다<Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">(활성화됨)</Anchor>.**
5. 아래 설명된 대로 관련 탭을 사용하여 설정을 완료하십시오.

Google Analytics 설정 윈도우는 *연동* 탭만 사용합니다.

<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">여기</Anchor>를 클릭하여 파트너 설정 창 헤더에 대한 자세한 설명을 확인하십시오.

<div id="integration-tab" />

<Accordion title="연동 탭">

연동 탭은 아래와 같이 다양한 섹션으로 나누어져 있습니다.

### 파트너 활성화

여기서 **첫 번째 방문**에서 연동 탭의 파라미터 설정을 사용 가능하게 하려면 ***파트너 활성화*** 버튼을 켜야 합니다. 파트너와 작업하는 동안에는 토글이 켜져 있어야 합니다.  
파트너 활성화에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">여기</Anchor>를 클릭하십시오.

### 일반 설정

아직 계정 ID가 없다면, 연동을 계속하려면 Google Analytics에서 가져와야 합니다.

![Game_Analytics_msc_new_2.png](https://files.readme.io/0c629a74c16d6d8a861ee3ec344de68516a6224e9d6f5afb4b7d89fe78baa49f-360002199865.png)

### 기본 포스트백

이 섹션을 사용하여 이러한 포스트백 전송을 정의합니다.

![Swrve_msc_new_4.png](https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png)

### 인앱 이벤트 설정

2. 인앱 이벤트 포스트백을 ON으로 토글합니다.
3. SDK에 설정된 모든 이벤트에 대해 보내기 옵션을 선택합니다.  
   - 이 파트너에 어트리뷰션된 유저에게서**만** 발생하는 이벤트에 대해 **이 파트너에 어트리뷰션된 이벤트만**  
   - 전체 유저 기반을 해당 파트너에게 리포트할 수 있도록 하려면 **모든 파트너 또는 오가닉에 어트리뷰션된 이벤트**
4. SDK 이벤트를 목록에 추가하려면 **이벤트 추가**를 클릭합니다.
5. 다음 파라미터를 완성합니다.

| 파라미터 이름 | 설명 |
| --- | --- |
| **SDK 이벤트 이름** | 앱에 연동된 SDK 또는 서버 간(S2S) 이벤트에서 앱스플라이어가 수신한 이벤트의 이름입니다.  <br />**팁** - 원하는 이벤트가 목록에 없으면, 논오가닉으로 인스톨한 기기에서 이벤트를 실행하고 다시 점검해 봅니다. |
| **파트너 이벤트 식별자** |  |
| **수익 전송** | **체크하지 않은 경우** - 앱스플라이어는 리치 인앱 이벤트의 모든 파라미터를 파트너에게 전송합니다. 단, **af\_revenue** 파라미터에 포함된 수익 값은 제외합니다.  <br />**선택한 경우** - 앱스플라이어가 수익 값(이벤트에 존재하는 경우)을 포함하여 모든 파라미터를 전송합니다. |

**저장**을 클릭하세요.

* game\_key
* 미디어 소스
* 캠페인 이름

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="어트리뷰션 링크 탭">

Google Analytics에서는 어트리뷰션 링크를 사용할 수 없습니다.

</Accordion>

<div id="cost-tab" />

<Accordion title="비용 탭">

이 파트너와 연동 시 비용 데이터는 지원되지 않습니다.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="광고 수익 탭">

이 파트너와 연동 시 광고 수익은 지원되지 않습니다.

</Accordion>

<div id="permissions-tab" />

<Accordion title="권한 탭">

Google Analytics에서는 권한을 사용할 수 없습니다.

</Accordion>

<div data-zendesk-anchors="h_01H9FK7ZH27GNEHRZ5KKVH5CHY=%EC%A4%91%EC%9A%94 h_01H9FK7ZH24E9AD7Z0J94NS0JJ=setting-up-gameanalytics h_01H9FK7ZH3VPBE965Z8MCVXSMQ=integration-tab activate-partner=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 h_01H9FK7ZH3D2H5AWW0DMBQP9R3=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 general-settings=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 h_01H9FK7ZH3E32TT8EGAYWPRWBE=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 default-postbacks=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01H9FK7ZH3P0HSQGR2409BFA2F=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 inapp-event-settings=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95 h_01H9FK7ZH366RDSY36QVVWJMJN=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95 h_01H9FK7ZH39J4Q7W5XSFZAEZWH=attribution-link-tab h_01H9FK7ZH37FQ6RN80E90TH4K9=cost-tab h_01H9FK7ZH3GE3G69AA03KJK499=ad-revenue-tab h_01H9FK7ZH3RQJQPAYSZBR208H7=permissions-tab" />
