---
title: 앱스플라이어와 함께 Firebase 및 구글 태그 관리자 사용 - 개요
metadata:
  keywords:
    - GTM
    - Google Tag Manager
    - firebase
    - Advertisers
    - datalayer
    - data layer
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-05-13T19:42:23Z'
  edited_at: '2026-10-14T10:32:08Z'
  id: 210353513
  locale: ko
  section: Firebase and Google Tag Manager
  section_id: 6551267006225
  url: https://support.appsflyer.com/hc/ko/articles/210353513
---
> **한눈에 보기:** 요약: Firebase SDK를 통해 리포트된 이벤트를 Google 태그 관리자를 사용하여 앱스플라이어로 전송하는 방법.

<Image align="center" alt="gtm.png" src="https://files.readme.io/fbb4e0f83baf6f5f7f8dc83e02986ca011f5cb919b9870768da1606798211dcc-360002517245.png" width="289px" />

Google 태그 관리자(GTM) 및 Firebase와의 앱스플라이어 연동을 통해 개발자는 Firebase SDK를 사용하여 Firebase에 인앱이벤트를 보내고 Google 태그 관리자를 사용하여 SDK를 통해 이벤트를 앱스플라이어에 보낼 수 있습니다. 이렇게 하면 동일한 이벤트를 두 번 보내지 않게 됩니다.

GTM을 사용하여 전송된 이벤트는 앱스플라이어 인앱이벤트에서 모델링됩니다. 이벤트 이름, 파라미터 및 구조는 동일합니다. 앱에 이미 GTM이 있는 경우 이를 사용하여 앱스플라이어에 간단히 이벤트를 보낼 수 있습니다.

이 가이드의 단계와 지침을 사용하여 이벤트를 보냅니다. 

<div id="considerations" />

### 고려 사항

* SDK에서 이벤트를 리포트하므로 이로 인해 약간의 혼란이 발생할 수 있습니다.
* SKAdNetwork 전환 가치 업데이트: 이 가이드에 설명된 대로 GTM에서 생성되고 SDK에 리포트된 이벤트로 인해 SDK는 일반 SDK 이벤트와 유사한 방식으로 전환 가치를 업데이트합니다. <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-solution-guide">SKAdNetwork 측정 설정</Anchor>을 켜고 설정하기만 하면 됩니다.

<div id="note" />

> 📘 **참고사항**
>
> * 현재 Google 태그 관리자 연동은 다음 파라미터를 앱스플라이어로 보내는 기능을 지원하지 않습니다.
>   * <Anchor target="_blank" href="/marketers/ko/docs/customer-user-id-field-cuid">고객 유저 ID</Anchor>
>   * `att`
>   * `os`일러두기:
>   * 인앱이벤트 포스트백을 SRN으로 보낼 때 `att`attatt 파라미터가 필요합니다.
>   * Meta 광고에 인앱 이벤트 포스트백을 보낼 때는 and `att`osatt 매개변수가 `os`attos 필요합니다.

<div id="prerequisites" />

### 필수 조건

GTM을 사용하여 앱스플라이어에 이벤트 전송을 시작하려면 먼저 앱에 GTM SDK를 구현해야 합니다. 필요한 것은 다음과 같습니다.

1. [GTM 계정](https://www.google.com/analytics/tag-manager/)이 필요합니다.
2. 앱에 대한 GTM + Firebase 연동 설정이 있어야 합니다( [안드로이드](https://developers.google.com/tag-manager/android) 및 [iOS용](https://developers.google.com/tag-manager/ios/) 지침).
3. 아직 그렇게 하지 않았다면 <Anchor target="_blank" href="/marketers/ko/docs/integrate-the-appsflyer-sdk">앱스플라이어 SDK를 연동하십시오</Anchor>.

모든 것이 준비되면 <Anchor target="_blank" href="/marketers/ko/docs/using-firebase-and-google-tag-manager-with-appsflyer-google-tag-manager-setup">GTM 설정</Anchor>으로 진행합니다.

<div id="see-also" />

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/migrate-from-firebase-dynamic-links-to-appsflyer">Firebase 동적 링크에서 앱스플라이어로 마이그레이션</Anchor>

<div data-zendesk-anchors="considerations=%EA%B3%A0%EB%A0%A4-%EC%82%AC%ED%95%AD h_01HE7SKSCBH47YYFTKBWY3JVSV=%EA%B3%A0%EB%A0%A4-%EC%82%AC%ED%95%AD h_01HE7SKSCBBTTWATRZ87BYRW6G=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD prerequisites=%ED%95%84%EC%88%98-%EC%A1%B0%EA%B1%B4 h_01HE7SKSCB9QHA4WEERVSWMF0P=%ED%95%84%EC%88%98-%EC%A1%B0%EA%B1%B4 h_01HE7SQQG2VJW9179Q77PTZFPH=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
