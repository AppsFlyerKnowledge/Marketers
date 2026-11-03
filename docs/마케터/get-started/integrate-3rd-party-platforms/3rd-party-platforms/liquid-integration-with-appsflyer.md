---
title: Steam과 앱스플라이어 연동
metadata:
  keywords:
    - Liquid
    - attribution data
    - integrated partner
    - Advertisers
    - Ad Networks
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
  created_at: '2015-12-24T11:36:06Z'
  edited_at: '2026-10-14T10:38:59Z'
  id: 207040626
  locale: ko
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ko/articles/207040626
---
> **한눈에 보기:**

> 🚧 **중요!**
>
> <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions#미디어-소스-제한">일부 미디어소스</Anchor>는 타사와의 데이터 공유를 제한합니다. 따라서 제한된 이벤트에 대한 포스트백은 포스트백을 보내기 위해 구성된 선택에 관계없이 이 파트너에게 전송되지 않습니다.


**<span id="setting-up-liquid"></span>전제 조건:** 연동 설정 전에 <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations#contact-details">파트너에게 연락</Anchor>하여 계정을 개설하세요.

**연동 활성화 또는 편집 방법:**

1. To activate:연동 활성화 방법: 앱스플라이어의 사이드 메뉴에서협업<strong>></strong>파트너 마켓플레이스**를 선택합니다.  
   **편집 방법:** 앱스플라이어의 사이드 메뉴에서 **협업**> 활성화된 연동을 선택합니다.**
2. 파트너를 검색하고 선택합니다.
3. **연동 설정**을 클릭하십시오. 연동 설정 페이지로 이동합니다.
4. **연동** 탭에서 연동할 앱을 선택하고 **파트너 활성화**를 켭니다.   
   **참고: 파트너와의 작업 동안 토글이 활성화되어 있어야 합니다<Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">(활성화됨)</Anchor>.**
5. 아래 설명된 대로 관련 탭을 사용하여 설정을 완료하십시오.

설정 창에서는 연동 탭만 활용합니다.

<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">여기</Anchor>를 클릭하여 파트너 설정 창 헤더에 대한 자세한 설명을 확인하십시오.

<div id="integration-tab" />

<Accordion title="연동 탭">

연동 탭은 아래와 같이 다양한 섹션으로 나누어져 있습니다.

### 파트너 활성화

이곳을 **처음 방문**하면 아래를 토글해야 합니다. ***파트너 활성화*** 버튼을 **켜서** 연동 탭의 파라미터 설정을 활성화합니다. 파트너와 함께 작업하는 동안에는 토글이 **켜져 있어야** 합니다.  
파트너 활성화에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">여기</Anchor>를 클릭하십시오.

### 일반 설정

api\_token


### 기본 포스트백

앱스플라이어는 Braze 사용자 인스톨에 자동 포스트백을 발송할 수 있습니다. 이 섹션을 사용하여 이러한 포스트백 전송을 정의합니다.

![Swrve_msc_new_4.png](https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png)

**저장**을 클릭하세요.

* 미디어 소스
* 캠페인 이름

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="어트리뷰션 링크 탭">

Braze에서는 어트리뷰션 링크를 사용할 수 없습니다.

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

Braze에서는 권한 설정을 사용할 수 없습니다.

</Accordion>

<div data-zendesk-anchors="h_01H9FKBW5QYQGZ7PNEJMHZ6H2R=%EC%A4%91%EC%9A%94 h_01H9FKBW5QMJTARZ6KZ41QT1BN=setting-up-liquid h_01H9FKBW5QM601CMQ6Y2PNJ1HQ=integration-tab activate-partner=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 h_01H9FKBW5RRYW1JTK2S9V4V6SA=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 general-settings=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 h_01H9FKBW5RB52QQKVF5TMFVKKT=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 obtaining-the-api-token=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 default-postbacks=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01H9FKBW5RCGHVJRJEBQW4KNGD=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01H9FKBW5RVYXPEEFDG948P1XV=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01H9FKBW5RNH2BRV8S31DT8SWA=attribution-link-tab h_01H9FKBW5RRQZZC4YQNWGHQTW6=cost-tab h_01H9FKBW5R7TNN5YA5YP36EJ63=ad-revenue-tab h_01H9FKBW5RC55F56K3EMQBJGEK=permissions-tab" />
