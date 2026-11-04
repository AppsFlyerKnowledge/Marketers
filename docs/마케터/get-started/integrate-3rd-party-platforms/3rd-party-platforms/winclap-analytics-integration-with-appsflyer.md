---
title: 앱스플라이어와 Adobe Analytics의 연동
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
  created_at: '2019-09-04T11:07:12Z'
  edited_at: '2026-10-14T10:30:54Z'
  id: 360002403537
  locale: ko
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ko/articles/360002403537
---
> **한눈에 보기:**

<div id="important" />

> 🚧 **중요!**
>
> <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions#미디어-소스-제한">일부 미디어소스</Anchor>는 타사와의 데이터 공유를 제한합니다. 따라서 제한된 이벤트에 대한 포스트백은 포스트백을 보내기 위해 구성된 선택에 관계없이 이 파트너에게 전송되지 않습니다.


<span id="setting-up-winclap"></span>설정은 **활성 연동** 페이지에서 수행되지만 파트너를 찾으려면 먼저 <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations">마켓플레이스</Anchor>로 이동해야 합니다.

<div id="note" />

> 📘 **참고사항**
>
> 연동을 설정하기 전에 <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations#contact-details">파트너에게 연락하여</Anchor> 계정을 개설해야 합니다.

**연동 활성화 방법:**

1. 앱스플라이어 페이지의 상단 메뉴에서 **마켓플레이스**를 클릭합니다.
2. 파트너를 검색하여 선택하세요.
3. **연동 설정**을 클릭하십시오. 연동 설정 페이지로 이동합니다.
4. **연동** 탭에서 연동할 앱을 선택하고 **파트너 활성화**를 켭니다.   
   **참고: 파트너와의 작업 동안 토글이 활성화되어 있어야 합니다<Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">(활성화됨)</Anchor>.**
5. 아래 설명된 대로 관련 탭을 사용하여 설정을 완료하십시오.

<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">여기</Anchor>를 클릭하여 파트너 설정 창 헤더에 대한 자세한 설명을 확인하십시오.

<div id="integration-tab" />

<Accordion title="연동 탭">

연동 탭은 아래와 같이 다양한 섹션으로 나누어져 있습니다.

<div id="activate-partner" />

### 파트너 활성화

여기서 **첫 번째 방문**에서 연동 탭의 파라미터 설정을 사용 가능하게 하려면 ***파트너 활성화*** 버튼을 켜야 합니다. 파트너와 작업하는 동안에는 토글이 켜져 있어야 합니다.  
파트너 활성화에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/user-level-data-retention">여기</Anchor>를 클릭하십시오.

<div id="default-postbacks" />

### 기본 포스트백

이 섹션을 사용하여 상기 포스트백을 보낼 수 있는 **유저 소스**를 정의할 수 있습니다.

* ***이 파트너는*** *페이스북 광고의 사용자로부터* 수신되는 이벤트에만 해당됩니다.
* <strong>앱을 다운로드하는 모든 유저에 대한 포스트백을 믹스패널로 전송하려면</strong> <em>모든 미디어소스(오가닉 포함)</em>를 선택하세요.

* 캠페인 이름
* 유저 에이전트
* 클릭 시간
* IP
* 국가
* 도시
* 서브 퍼블리셔 ID
* 통신사
* 언어
* 앱 ID
* 앱 버전
* 앱 이름
* 설치 시간

<div id="in-app-events-settings" />

### 인앱 이벤트 설정

2. 필요한 경우 *인앱 이벤트 포스트백 기간*을 설정합니다(**인앱 이벤트 포스트백 기간 구성**에 대해 자세히 알아보세요).
3. SDK 이벤트를 목록에 추가하려면 *이벤트 추가*를 클릭합니다.
4. 다음 파라미터를 완성하세요. 

| 파라미터 이름 | 설명 |
| --- | --- |
| **SDK 이벤트 이름** | 앱에 연동된 SDK 또는 서버 간(S2S) 이벤트로부터 앱스플라이어가 수신한 이벤트 이름입니다.  <br />**팁**: 찾고 있는 이벤트가 없나요? SDK에 이벤트 이름을 입력하고, **사용자정의 생성**을 클릭하여 보통 때처럼 매핑하십시오. <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#커스텀-이벤트">사용자정의 이벤트 매핑</Anchor>에 대해 더 자세히 알아보십시오. |
| **파트너 이벤트 식별자** | Facebook에 정의된 각 이벤트의 고유한 이름 또는 ID입니다. |
| **보내기 옵션** | 이벤트의 전송 옵션을 선택합니다.  <br />이 파트너만 해당: Unity Ads로 어트리뷰션된 사용자로부터 발생한 이벤트에만 적용됩니다.  <br />**오가닉을 포함한 모든 미디어소스**: 트레이드 데스크에 리포트할 수 있는 전체 사용자 기반을 가지는 미디어소스를 의미합니다. |
| **이벤트 데이터 전송** | <ul><li>**No values & no revenue:** 이벤트 값(event value)를 제외하고 이벤트만 전송합니다.</li><li>**Values & no revenue:** 매출 값을 제외한 모든 파라미터를 전송합니다.</li><li>**Values & revenue**: 매출 값(이벤트에 존재하는 경우)을 포함하여 모든 이벤트 파라미터를 전송합니다.</li></ul> |

5. **저장**을 클릭하세요.

* 이벤트 이름
* 이벤트 값
* 이벤트 수익
* Event Currency
* 캠페인 이름
* 유저 에이전트
* 클릭 시간
* IP
* 국가
* 도시
* 서브 퍼블리셔 ID
* 통신사
* 언어
* 앱 ID
* 앱 버전
* 앱 이름
* 설치 시간

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="어트리뷰션 링크 탭">

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

</Accordion>

<div data-zendesk-anchors="h_01H9HWQK6JA2194MPE8PVQJ346=%EC%A4%91%EC%9A%94 h_01H9HWQK6JAQ2GCHHGQ57PJ570=setting-up-winclap h_01H9HWQK6JRZ1KVDJK00PZR7T9=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD h_01H9HWQK6JX9MAD64MQ1HPK4T0=integration-tab activate-partner=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 h_01H9HWQK6JKRB5MDE43RKV3SEH=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 default-postbacks=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01H9HWQK6JP4HQHRFC011KW6XQ=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 inapp-events-settings=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95 h_01H9HWQK6J1MEK67XDMAMKAQKW=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95 h_01H9HWQK6JBH1M2MZQM12R0SAR=attribution-link-tab h_01H9HWQK6JG46BGNRMR8ZM9W2J=cost-tab h_01H9HWQK6J7HHJWKVB55WE1VW9=ad-revenue-tab h_01H9HWQK6J6BD0ER2M9Z7GYGSM=permissions-tab" />
