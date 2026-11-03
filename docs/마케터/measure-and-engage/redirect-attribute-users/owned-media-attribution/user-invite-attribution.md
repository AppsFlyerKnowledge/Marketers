---
title: 사용자 초대 어트리뷰션
metadata:
  keywords:
    - OneLink
    - Advertisers
    - User invite
    - Developers
    - Marketers
    - Text-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Text-to-App
  created_at: '2017-08-30T12:13:45Z'
  edited_at: '2026-10-14T10:37:28Z'
  id: 115004480866
  locale: ko
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/ko/articles/115004480866
---
> **한눈에 보기:** 기존 사용자가 다른 사용자에게 앱을 사용하도록 초대할 때 새 인스톨을 어트리뷰트하고 기록합니다.

[![Invite_Attribution_new.png](https://files.readme.io/ee6793f57e16e7b051d1651108d7408482dff15501d9d786b5ca250e71d54ed4-360002880777.png)](https://files.readme.io/ee6793f57e16e7b051d1651108d7408482dff15501d9d786b5ca250e71d54ed4-360002880777.png)

## 사용자 초대 어트리뷰션 소개

사용자 초대란 기존 앱 사용자가 다른 사용자(예: 친구)를 앱을 다운로드하거나 열 수 있는 링크를 공유함을 의미합니다.

사용자 초대 어트리뷰션이란, 새로운 앱 설치나 인게이지먼트 활동을 추천을 보낸 사용자에게 어트리뷰트하는 것을 의미합니다.

사용자 초대 어트리뷰션을 통해 다음을 수행할 수 있습니다.

* 유저 초대 비용 및 ROI를 분석합니다. 사용자 초대 기능은 광고 수익을 창출할 수 있는 앱의 광고 공간을 차지하게 됩니다. 이때 사용자 초대가 다른 광고 대안보다 더 나은 투자 수익률(ROI)을 제공하는지 확인할 수 있습니다.
* 다른 사람에게 가장 많이 추천하는 사용자에 대한 정보를 기록합니다. 앱에 다른 사용자를 초대하는 사용자는 가치와 참여도가 높은 사용자이며, 이러한 사용자에 대한 정보는 리타겟팅하거나 인센티브를 제공하는 데 사용할 수 있습니다.

또한 링크로부터의 데이터를 사용하여 다음 기능을 수행할 수 있습니다.

* 새 사용자의 경험을 맞춤화합니다. 예를 들어, 앱을 특정 콘텐츠로 열거나 일반적인 메시지를 보내는 대신, 다음과 같은 개인 맞춤형 환영 메시지를 보낼 수 있습니다. “안녕하세요 John님, 친구 Maria님이 게임 대결을 요청했어요. 지금 플레이하세요!"
* 다른 사용자를 추천인으로 입력하는 사용자에게 보상을 제공합니다. [더 알아보기](/docs/user-invite-attribution#reward-referrers-for-user-invite-installs)

사용자들이 다른 사람과 공유하는 초대 링크는 실제로 앱에 연동된 앱스플라이어 SDK에 의해 생성된 원링크 커스텀 링크(숏 URL)입니다. 원링크 설정을 통해 초대를 받은 사용자가 올바른 위치로 리디렉션되도록 할 수 있습니다. 즉, 올바른 앱 스토어로 이동하거나, 앱 내로 진입하거나, 앱의 특정 페이지로 딥링크/디퍼드 딥링크 될 수 있습니다. <Anchor target="_blank" href="/marketers/ko/docs/onelink-guide">원링크에 대해 더 알아보기</Anchor>

### 플로우

전체 플로우는 다음과 같이 작동합니다.

1. 사용자 A가 앱 내에서 탭하여 앱을 친구와 공유합니다. (사용자 A는 앱을 설치했으며 로그인했습니다.)
2. 탭하면 사용자 A를 식별하는 파라미터가 포함된 링크가 생성됩니다.
3. 사용자 A는 이메일/WhatsApp/SMS 등을 통해 사용자 B에게 링크를 보냅니다.
4. 사용자 B가 다음과 같은 경우:
   * 앱이 설치되어 있으며 앱이 열립니다. 사용자 B는 앱의 특정 페이지에 딥링킹되거나 보상을 받을 수 있습니다.
   * 설치된 앱이 없으면 올바른 앱 스토어로 전송됩니다. 사용자 B는 최초 앱 실행 후 또는 사용자 A가 보상을 받은 이후 앱 내 특정 페이지와의 디퍼드 딥링킹이 가능합니다.
   * 인앱 이벤트를 수행하며 사용자 A에게 보상을 제공할 수 있습니다.

## 데이터 보기

사용자 초대 데이터는 앱스플라이어 대시보드 및 리포트를 통해 사용할 수 있습니다. 앱스플라이어 대시보드에서 다음과 같이 사용자 초대 어트리뷰션을 필터링할 수 있습니다.

* **미디어 소스:** 앱 초대
* **채널** 마케터의 결정에 따라
* **캠페인**: 마케터의 결정에 따라

리포트에서 미디어 소스 (`pid` 파라미터)는 SDK에서 기본값 `af_app_invites`로 전송됩니다.

## 절차

**사용자 초대 링크를 생성하는 방법**:

1. <Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template#원링크-템플릿-만들기">원링크 템플릿</Anchor>을 생성합니다.
2. 채널과 캠페인 파라미터 값을 결정합니다. [파라미터](/docs/user-invite-attribution#parameters)를 참조하세요.
3. 링크에 대해 어떤 활용 사례를 적용할지 결정합니다. 일반적인 활용 사례는 다음과 같습니다.
   * 새 사용자를 앱의 특정 페이지로 딥링킹합니다.
   * 어떤 사용자가 추천을 했는지 기록합니다.
   * 새 사용자를 보상합니다.
4. 링크의 활용 목적에 맞춰 어떤 파라미터를 사용할지 Android 및 iOS 개발자와 함께 논의하세요. 사용 가능한 [파라미터](/docs/user-invite-attribution#parameters)를 참조하십시오.
5. 개발자에게 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/getting-started-1">딥링크를 구현</Anchor>을 요청합니다. (코드 내에서 원하는 파라미터 동작을 사용)
6. 다음 플랫폼에 사용자 초대 기능을 구현하도록 개발자에게 요청합니다.

   <Tabs>
   <Tab title="안드로이드">

   개발자 허브에서 [안드로이드 사용자 초대](https://dev.appsflyer.com/hc/docs/dl_android_user_invite)를 참조하세요.

   </Tab>

   <Tab title="iOS">

   개발자 허브에서 [iOS 사용자 초대](https://dev.appsflyer.com/hc/docs/dl_ios_user_invite)를 참조하세요.

   </Tab>

   <Tab title="Unity">

   개발자 허브에서 [사용자 초대](https://dev.appsflyer.com/hc/docs/userinvite)를 참조하세요.

   </Tab>
   </Tabs>

<div id="parameters" />

<Accordion title="파라미터">

#### SDK에 구현하기 위해 개발자에게 제공된 파라미터/값

<table><thead><tr><th>파라미터/값</th><th>비고</th><th>개발자가 구현해야 할 값/활용 사례를 기록합니다.</th></tr></thead><tbody><tr><td>원링크 템플릿 ID</td><td>모든 사용자 초대 링크의 기반이 될 기본 설정이 있는 원링크 템플릿의 ID입니다. 예시: H5hv</td><td> </td></tr><tr><td>채널</td><td>채널 이름. 이를 통해 앱스플라이어 UI에서 채널별로 어트리뷰션을 정렬하고 볼 수 있습니다.</td><td> </td></tr><tr><td>캠페인</td><td>캠페인 이름. 이를 통해 앱스플라이어 UI에서 캠페인별로 어트리뷰션을 정렬하고 볼 수 있습니다.</td><td> </td></tr><tr><td> <span>is_retargeting=true</span><br/> </td><td>캠페인이 기존 사용자를 리타겟팅하려는 경우 추가됩니다.</td><td> </td></tr><tr><td>deep_link_value</td><td>초대된 사용자의 디바이스에서 특정 경험을 제공하기 위해 사용할 파라미터입니다. 일반적으로 사용자가 연결될 특정 페이지 이름을 지정하는 데 사용됩니다. 예를 들어, 앱에서 과일을 판매하는 경우 사용자를 사과 페이지로 딥링킹할 수 있습니다.</td><td> </td></tr><tr><td>deep_link_sub1</td><td rowspan="10">초대된 사용자의 디바이스에서 특정 경험을 제공하기 위해 사용할 파라미터입니다. deep_link_value는 일반적으로 사용자를 특정 페이지로 보내는 데 사용되지만, 이 파라미터는 원하는 다른 기능에도 활용할 수 있습니다. 예를 들어, 보상 또는 할인을 추가하거나 초대를 한 사용자를 기록하는 데에도 사용됩니다. </td><td> </td></tr><tr><td>deep_link_sub2</td><td> </td></tr><tr><td>deep_link_sub3</td><td> </td></tr><tr><td>deep_link_sub4</td><td> </td></tr><tr><td>deep_link_sub5</td><td> </td></tr><tr><td>deep_link_sub6</td><td> </td></tr><tr><td>deep_link_sub7</td><td> </td></tr><tr><td>deep_link_sub8</td><td> </td></tr><tr><td>deep_link_sub9</td><td> </td></tr><tr><td>deep_link_sub10</td><td> </td></tr><tr><td>[선택 사항] pid</td><td><p>기본적으로 생성하는 링크에는 값이 <code>af_app_invites</code>인 미디어 소스(<code>pid</code> 파라미터)가 포함됩니다. </p><p>값을 변경하려면, 원하는 값을 가진 <code>pid</code>라는 커스텀 파라미터를 개발자가 추가해야 합니다. <strong>참고</strong>: 안드로이드의 경우 SDK V6.4.2+에서만 작동합니다.</p></td><td> </td></tr><tr><td>브랜드 이름</td><td>브랜드 도메인 이름입니다. 이를 통해 앱스플라이어 UI에서 브랜드 도메인별로 어트리뷰션을 정렬하고 볼 수 있습니다.</td><td> </td></tr></tbody></table>

</Accordion>

<div id="example" />

<Accordion title="예시">

마케터인 마크는 과일을 판매하는 앱을 운영하고 있습니다. 마크는 사용자를 특정 과일 페이지로 딥링크시키고, 정해진 수량의 과일을 구매할 수 있는 옵션이 포함된 링크를 만들고자 합니다.

이 링크는 사용자 초대를 통해 전송될 수 있어야 하며, 추천을 통해 새로운 앱 인스톨과 과일 구매가 발생할 때마다 추천인에게 보상이 주어져야 합니다.

이 모든 기능이 제대로 작동하도록 하기 위해, 마크는 사용자 초대 링크를 구현할 때 사용할 파라미터와 값의 목록을 개발자에게 다음과 같이 전달했습니다.

| 파라미터 | 값 | 비고 |
| --- | --- | --- |
| deep\_link\_value | fruit\_name | 앱스플라이어 UDL 메서드를 사용하는 딥링킹의 경우. |
| deep\_link\_sub1 | promo\_code | 앱스플라이어 UDL 메서드를 사용하는 딥링킹의 경우. |
| deep\_link\_sub2 | referrer\_id | SDK를 통한 링크 생성의 경우. |
| param\_1 | referrer\_id | 각 구매를 기록하는 인앱이벤트의 경우. |
| 채널 | mobile\_share | 어트리뷰션의 경우, 그리고 앱스플라이어의 데이터를 보려는 경우. |
| 캠페인 | summer\_sale | 어트리뷰션의 경우, 그리고 앱스플라이어의 데이터를 보려는 경우. |

</Accordion>

## 추가 정보

<div id="record-user-invites-as-inapp-events" />

<Accordion title="사용자 초대를 인앱 이벤트로 기록">

사용자가 초대를 보낸 후 인앱 이벤트를 기록하면, 다른 사용자를 추천한 사용자를 식별할 수 있을 뿐만 아니라 이 추천자를 유입시킨 미디어 소스도 파악할 수 있습니다.

**사용자 초대 인앱 이벤트를 기록하는 방법**:

* <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-event-structure#invite-af_invite">af\_invite 이벤트</Anchor>를 전송합니다. 개발자는 앱스플라이어 개발자 허브 지침에 따라 이를 구현해야 합니다.

**참고**: 이벤트와 연결할 파라미터를 더 추가할 수 있습니다. 이벤트에 추가 컨텍스트를 제공하고 데이터를 풍부하게 할 파라미터를 선택하세요. <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#인앱-이벤트-설정">더 알아보기</Anchor>

</Accordion>

<div id="reward-referrers-for-user-invite-installs" />

<Accordion title="사용자 초대 인스톨에 대한 리워드 리퍼러">

**사용자 초대가 앱 인스톨로 이어졌을 때 추천인에게 보상을 제공하려면**:

1. 리퍼러 ID의 값이 [deep\_link\_sub1-10 파라미터](/docs/user-invite-attribution#parameters) 중 하나에 해당하는지 확인합니다.
2. 개발자에게 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/getting-started-1">딥링크를 구현</Anchor>을 요청합니다. (코드 내에서 원하는 파라미터 동작을 사용)
3. 백엔드 개발자에게 앱 개발자와 협력하여 앱스플라이어 리포트에서 추천인 ID를 확인하고, 해당 추천인에게 보상이 지급되도록 처리해 달라고 요청하세요.

예시:

1. 사용자 A가 사용자 B를 앱을 설치하도록 초대합니다.
2. 사용자 B가 앱을 실행하면 앱은 사용자 A의 리퍼러 ID를 얻게 됩니다.
3. 백엔드에서 앱스플라이어 리포트의 리퍼러 ID를 검색합니다.
4. 백엔드에서 사용자 A의 리퍼러 ID를 보상 대상자 목록에 추가합니다.
5. 사용자 A가 앱을 실행할 때, 해당 사용자의 추천인 ID가 보상 대상 사용자 목록에 있는지 확인하고, 목록에 있다면 보상을 지급합니다.

</Accordion>

<div id="reward-referrers-for-referred-user-actions" />

<Accordion title="추천된 사용자의 작업 수행에 따른 리퍼러 보상">

**특정 인앱 이벤트를 발생시킨 사용자 초대에 대해 리퍼러에게 보상을 제공하는 방법**:

1. 보상하려는 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#인앱-이벤트-설정">인앱 이벤트를 생성</Anchor>합니다.
2. 이벤트에 추천인 ID를 값으로 가지는 파라미터(예: param\_1)를 추가하도록 개발자에게 요청합니다. **참고**: 앱 인스톨 시, 선택한 [파라미터](/docs/user-invite-attribution#parameters) (deep\_link\_sub1&#126;10)를 사용해 추천인 ID가 최초로 기록됩니다.
3. 백엔드 개발자에게 앱 개발자와 협력하여 앱스플라이어 리포트에서 추천인 ID를 확인하고, 해당 추천인에게 보상이 지급되도록 처리해 달라고 요청하세요.

예시:

1. 사용자 A가 앱에서 작업을 수행하도록 사용자 B를 초대합니다.
2. 사용자 B가 작업을 수행하면 사용자 A의 리퍼러 ID가 포함된 인앱이벤트가 기록됩니다.
3. 백엔드에서 앱스플라이어 리포트의 리퍼러 ID를 검색합니다.
4. 백엔드에서 사용자 A의 리퍼러 ID를 보상 대상자 목록에 추가합니다.
5. 사용자 A가 앱을 실행할 때, 해당 사용자의 추천인 ID가 보상 대상 사용자 목록에 있는지 확인하고, 목록에 있다면 보상을 지급합니다.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="특징 및 제약 사항">

| 특징 | 설명 |
| --- | --- |
| SDK Version | 앱스플라이어 SDK 버전 4.8.0 이상과 Unity SDK 버전 4.17.0 이상이 있어야 합니다. |
| <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">소셜 미디어 앱 랜딩 페이지</Anchor> | 사용자 초대로 생성된 링크는 소셜 미디어 앱의 랜딩 페이지를 구현할 수 없습니다. |
| 유효기간(TTL, Time to Live) | SDK 앱 추천을 통해 작성된 원링크 숏 URL에 대한 기본 TTL은 60일입니다. 링크를 클릭할 때마다 60일씩 늘어납니다. |
| 과금 체계 | 모든 계정 플랜에 무료 |
| iOS 14+ | 사용자 초대 어트리뷰션은 IDFA를 사용하지 않으므로 iOS 14는 IDFA에 어떠한 영향도 미치지 않습니다. |
| URL ID | URL ID(또는 숏링크 ID)를 편집하여 캠페인 프로모션을 강조할 수 있습니다. 예시: https://myapp.onelink.me/abc123/apples.URL ID는 50자를 초과하지 않아야 하며 문자와 숫자를 조합할 수 있습니다. 기본값은 8자입니다.<br /><br />**참고**: 현재 ID가 사용되고 있지 않은 경우에만 URL ID를 편집할 수 있습니다. |

</Accordion>

<div data-zendesk-anchors="about-user-invite-attribution=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%B4%88%EB%8C%80-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%86%8C%EA%B0%9C h_01H98E1CZ2AG8AW2H77SPPHFGR=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%B4%88%EB%8C%80-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%86%8C%EA%B0%9C flow=%ED%94%8C%EB%A1%9C%EC%9A%B0 h_01H98E1CZ234MRBWDEYGZFCDRE=%ED%94%8C%EB%A1%9C%EC%9A%B0 viewing-data=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B8%B0 h_01H98E1CZ23FEAS8JJC7FFTFXD=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B8%B0 procedures=%EC%A0%88%EC%B0%A8 h_01H98E1CZ2VBCG0RREERW8FNJE=%EC%A0%88%EC%B0%A8 h_01H98E1CZ2WE6DJW717C6AJWXD=parameters parametersvalues-provided-to-the-developer-to-implement-in-the-sdk=sdk%EC%97%90-%EA%B5%AC%ED%98%84%ED%95%98%EA%B8%B0-%EC%9C%84%ED%95%B4-%EA%B0%9C%EB%B0%9C%EC%9E%90%EC%97%90%EA%B2%8C-%EC%A0%9C%EA%B3%B5%EB%90%9C-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0%EA%B0%92 h_01H98E1CZ2CANBK1T55DD103JB=sdk%EC%97%90-%EA%B5%AC%ED%98%84%ED%95%98%EA%B8%B0-%EC%9C%84%ED%95%B4-%EA%B0%9C%EB%B0%9C%EC%9E%90%EC%97%90%EA%B2%8C-%EC%A0%9C%EA%B3%B5%EB%90%9C-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0%EA%B0%92 h_01H98E1CZ2NXCCYEV12JC6EMFG=example additional-information=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01H98E1CZ28T2SJ3YNY8TNCAZY=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01H98E1CZ2172W6845K099F814=record-user-invites-as-inapp-events h_01H98E1CZ316WWYK55XTN4C8JE=reward-referrers-for-user-invite-installs h_01H98E1CZ330FXG06A4MVQ56PW=reward-referrers-for-referred-user-actions h_01H98E1CZ3SPASZDF5CCY3T3B3=traits-and-limitations" />
