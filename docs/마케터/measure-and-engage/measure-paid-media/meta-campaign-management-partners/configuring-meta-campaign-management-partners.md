---
title: Meta 캠페인 관리 파트너 구성하기
metadata:
  keywords:
    - Facebook
    - FMP
    - Advertisers
    - Partners
    - facebook marketing partner
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2018-03-18T12:43:51Z'
  edited_at: '2026-10-14T10:34:36Z'
  id: 360000562569
  locale: ko
  section: Meta campaign management partners
  section_id: 6551188365457
  url: https://support.appsflyer.com/hc/ko/articles/360000562569
---
> **한눈에 보기:** Kenshoo, Bidalgo, Smartly 등의 Meta 캠페인 관리 파트너(구 Facebook Marketing Partner(FMP))를 사용하여 Meta 광고 캠페인을 최적화하세요. 구성되면 앱스플라이어가 캠페인에 포스트백을 보냅니다.

## Meta 캠페인 관리 파트너 구성

**전제 조건:**  연동 설정 전에 반드시  <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations#contact-details">파트너에게 연락하여</Anchor> 계정을 개설하세요.

**연동 활성화 또는 편집 방법:**

1. To activate:연동 활성화 방법: 앱스플라이어의 사이드 메뉴에서협업<strong>></strong>파트너 마켓플레이스를 선택합니다.  
   <strong>편집 방법:</strong> 앱스플라이어의 사이드 메뉴에서 <strong>협업</strong>> 활성화된 연동을 선택합니다.
2. 파트너를 검색하고 선택합니다.
3. **연동 설정**을 클릭합니다. 연동 설정 페이지로 이동합니다.
4. **연동** 탭에서 연동할 앱을 선택하고  **파트너 활성화** 을 켭니다.  
   **참고:** 토글은 파트너와 함께 작업하는 동안 켜져 있어야<Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">(활성화되어야)</Anchor> 합니다.
5. 아래 설명된 대로 관련 탭을 사용하여 설정을 완료하십시오.

## 인앱 이벤트 포스트백 설정

**선행 조건**:

파트너가 포스트백을 받으려면 캠페인 이름 앞에 Meta 캠페인 관리 파트너 이름을 접두사로 **붙여야 합니다**. 예를 들어 Meta 캠페인 관리 파트너 이름이 *Mcmpexample*이고 세그먼트가 *Young\_Segment*인 경우 캠페인 이름을 *mcmpexample\_Young\_Segment*로 설정합니다.  
**참고:** Meta 캠페인 관리 파트너의 이름은 **대/소문자를 구분합니다.**

**인앱 이벤트 포스트백 설정 방법**:

[![in-app_event_mapping.png](https://files.readme.io/ced254c1aa0ad454c1876cfc0bc85de20d275824efb34c9665ca144dabffaa2a-14050539243793.png)](https://files.readme.io/ced254c1aa0ad454c1876cfc0bc85de20d275824efb34c9665ca144dabffaa2a-14050539243793.png)

1. **인앱 이벤트 포스트백**을 켭니다.
2. <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#매핑-방법">매핑 방법</Anchor>에 따라 필수 파라미터를 작성합니다.  
   

| 파라미터 이름 | 설명 |
| --- | --- |
| <span id="appsflyer-event"></span>**앱스플라이어 이벤트** | 앱스플라이어가 앱에 연동된 SDK 또는 서버 간 이벤트에서 수신한 이벤트의 이름입니다.<br />**팁**: 찾고 있는 이벤트가 없나요?<ul><li>논오가닉 인스톨된 디바이스에서 이벤트를 활성화하고 다시 확인하세요.</li><li>**앱스플라이어 이벤트**에 입력한 다음 **사용자 지정 생성**을 클릭합니다. <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#커스텀-이벤트">커스텀 이벤트 매핑</Anchor>에 대해 더 알아보세요.</li></ul> |
| <span id="mapped-to-partner-event"></span>**파트너 이벤트에 매핑** | 파트너 측에서 정의한 각 이벤트의 고유한 이름 또는 ID입니다. <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#매핑-방법">가능한 매핑 구성</Anchor>은 다음과 같습니다.<ul><li>**텍스트 필드:** 파트너로부터 해당 이벤트 ID를 받으세요.</li><li>**드롭다운 상자:** 가장 적합한 사전 정의된 파트너 이벤트를 선택하세요.</li><li>**있는 그대로**: 이벤트 이름을 매핑하지 않고 이벤트를 그대로 보냅니다.</li></ul> |
| <span id="for-users-from"></span>**유저에 대한** | 이벤트 발송 옵션을 선택하세요:<ul><li>**이 파트너만**: 이 이벤트가 이 파트너에 어트리뷰션된 경우에만 포스트백을 발송합니다. 즉, 유저가 이 파트너에서 온 경우입니다.</li><li>**오가닉 미디어 소스를 포함한 모든 미디어 소스**: 모든 파트너 및 오가닉 이벤트에 어트리뷰션된 이벤트에 대해 포스트백을 발송합니다. 즉, 유저가 어떤 미디어 소스에서 온 경우입니다.</li></ul> |
| <span id="including"></span>**포함하여** | 파트너와 포스트백에서 공유할 <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#포스트백에-포함할-데이터">이벤트 데이터를</Anchor> 선택하세요.<ul><li>**값 없음 및 수익 없음**: 파라미터 없이 이벤트 자체만 발송합니다 (값이나 수익).</li><li>**값 있음 및 수익 없음**: 수익 값을 **제외한** 모든 파라미터를 전송합니다.</li><li>**값 있음 & 수익 있음**: 수익 값(이벤트에 존재하는 경우)을 **포함한** 모든 이벤트 파라미터를 전송합니다.</li></ul> |

3. [선택 사항] 파트너에게 특정 인앱 이벤트를 전송하기 위한 <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#조건부-인앱-이벤트-포스트백">조건을 설정</Anchor>하려면 ![conditional-iae-postbacks-icon.png](https://files.readme.io/5345c5ebe95b3f1a0d0858b88ce29f9965178ce750df86c04cb131a93d006a5e-14050481317393.png)를 클릭합니다.
4. [선택 사항] **이벤트 추가**를 클릭하여 목록에 다른 SDK 또는 서버 간 이벤트를 추가합니다.
5. **연동 저장**을 클릭합니다.

> 📘 **중요 사항**
>
> * Meta 광고에 대한 어트리뷰션을 비활성화하면 Meta 캠페인 관리 파트너에게 포스트백을 보낼 수 없습니다.
> * Meta 캠페인 관리 파트너와의 인앱 이벤트 매핑 또는 매핑 부족은 광고주의 계정에서 직접 Meta 광고로 인앱 이벤트를 전송하는 데 영향을 미치지 않습니다.
> * 인앱 이벤트 매핑에는 Meta 캠페인 관리 파트너에 따라 다른 설정 파라미터가 필요할 수 있습니다.
> * Meta 광고 및 X 광고 캠페인 이름은 앱스플라이어 플랫폼에 정의된 Meta 캠페인 관리 파트너 계정 이름으로 시작하고 그 뒤에 밑줄 "\_"이 와야 합니다. 캠페인의 이름이 언급한 대로 지정되지 않은 경우 광고주에게는 표시되지만 Meta 캠페인 관리 파트너에게는 표시되지 않습니다. Meta 캠페인 관리 파트너 이름은 **대/소문자를 구분합니다**.

<div data-zendesk-anchors="configuring-facebook-marketing-partners=meta-%EC%BA%A0%ED%8E%98%EC%9D%B8-%EA%B4%80%EB%A6%AC-%ED%8C%8C%ED%8A%B8%EB%84%88-%EA%B5%AC%EC%84%B1 h_01HGFQCBT217ZV0R6E2YHTV88N=meta-%EC%BA%A0%ED%8E%98%EC%9D%B8-%EA%B4%80%EB%A6%AC-%ED%8C%8C%ED%8A%B8%EB%84%88-%EA%B5%AC%EC%84%B1 inapp-event-postback-setup=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EC%84%A4%EC%A0%95 h_01HGFQCBT3R7HH8M5SQJK1EPSP=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EC%84%A4%EC%A0%95 h_01HGFQCBT3HGZVFHCC1S04MVQW=%EC%A4%91%EC%9A%94-%EC%82%AC%ED%95%AD" />
