---
title: 탭카트 통합
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
  created_at: '2021-11-24T09:21:54Z'
  edited_at: '2026-10-14T10:32:25Z'
  id: 4411720533905
  locale: ko
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ko/articles/4411720533905
---
> **한눈에 보기:** 탭카트를 사용하여 앱에서 AppsFlyer 기능을 활용하세요.

<div id="introduction" />

## 소개

탭카트를 사용하면 데이터를 AppsFlyer에 쉽게 전송하고 그 기능을 활용할 수 있습니다. 탭카트로 앱을 개발할 때, AppsFlyer SDK는 기본적으로 앱에 구현됩니다. 탭카트를 통해 데이터를 기록한 후, 유기적 및 비유기적 설치를 포함한 데이터가 AppsFlyer에 표시됩니다.

<div id="integrating-tapcart-with-appsflyer" />

## 탭카트와 AppsFlyer 통합

AppsFlyer의 SDK를 사용하면 설치, 제거, 추천, 푸시 알림을 통한 사용자 참여, 딥링크 수행, 사용자 개인정보 보호 시나리오 처리 등을 측정할 수 있습니다.

탭카트와 AppsFlyer를 통합하는 방법을 배우려면 <Anchor target="_blank" href="https://tapcart.com/integrations/appsflyer">이 페이지</Anchor>를 따르세요.

<div id="default-in-app-events-configured-in-the-appsflyer-sdk" />

## AppsFlyer SDK에 구성된 기본 인앱 이벤트

탭카트가 앱에 AppsFlyer SDK를 통합한 후, 사용자가 수행할 때마다 다음 인앱 이벤트가 기록됩니다:

* 등록 완료
* 로그인
* 검색
* 콘텐츠 보기
* 목록 보기
* 위시리스트에 추가
* 장바구니 추가
* 결제
* Purchase
* 구매 완료
* 장바구니에서 제거
* 첫 구매

<div id="enable-deep-linking-with-appsflyer" />

## AppsFlyer로 딥링크 활성화

**AppsFlyer로 딥링크를 활성화하려면, 탭카트에 다음 매개변수를 제공해야 합니다:**

1. 개발 키 SDK를 구성하고 메시지를 암호화하며 사용자, 개발자 또는 API 호출 프로그램을 인증하기 위해 사용하는 인증 토큰이며 고유 ID입니다.  
   동일한 계정의 앱들은 보통 개발 키가 동일합니다. <Anchor target="_blank" href="/marketers/ko/docs/app-settings#sdk-authentication-dev-key">개발 키</Anchor>에 대해 자세히 알아보세요.
2. 원링크 템플릿 ID 이것은 OneLink URL을 생성하는 데 사용되는 OneLink 템플릿의 ID입니다. <Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template#원링크-템플릿-만들기">OneLink 템플릿 만들기</Anchor>에 대해 자세히 알아보세요.  
   **특정 템플릿의 ID를 얻으려면:**  
   1. **앱스플라이어에서** **경험 및 딥링킹** > 원링크 커스텀 링크로 이동 합니다.
   2. **OneLink 템플릿** 메뉴에서 필요한 템플릿을 선택하세요.
   3. 오른쪽에 표시된 ID를 복사하세요.  
       [![OneLink-template-id.png](https://files.readme.io/bb9524b5aecacba00c7f4801f7c854567119c032fa99a6d39122079e3f7956d1-small-4631542470673.png)](https://files.readme.io/bb9524b5aecacba00c7f4801f7c854567119c032fa99a6d39122079e3f7956d1-small-4631542470673.png)
3. **OneLink URL:** 특정 캠페인을 위해 AppsFlyer에서 생성된 특정 OneLink URL입니다. <Anchor target="_blank" href="/marketers/ko/docs/onelink-guide">OneLink 생성 방법</Anchor>에 대해 자세히 알아보세요.

<div data-zendesk-anchors="introduction=%EC%86%8C%EA%B0%9C h_01JQ6D9NCM8K3E6GS12V2CR1CH=%EC%86%8C%EA%B0%9C integrating-tapcart-with-appsflyer=%ED%83%AD%EC%B9%B4%ED%8A%B8%EC%99%80-appsflyer-%ED%86%B5%ED%95%A9 h_01JQ6D9NCM95VJB19G2F7SDRG1=%ED%83%AD%EC%B9%B4%ED%8A%B8%EC%99%80-appsflyer-%ED%86%B5%ED%95%A9 default-inapp-events-configured-in-the-appsflyer-sdk=appsflyer-sdk%EC%97%90-%EA%B5%AC%EC%84%B1%EB%90%9C-%EA%B8%B0%EB%B3%B8-%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8 h_01JQ6D9NCMYBNJ6WJ09R1EHXH4=appsflyer-sdk%EC%97%90-%EA%B5%AC%EC%84%B1%EB%90%9C-%EA%B8%B0%EB%B3%B8-%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8 enable-deep-linking-with-appsflyer=appsflyer%EB%A1%9C-%EB%94%A5%EB%A7%81%ED%81%AC-%ED%99%9C%EC%84%B1%ED%99%94 h_01JQ6D9NCMC97JQ759B44M9TDJ=appsflyer%EB%A1%9C-%EB%94%A5%EB%A7%81%ED%81%AC-%ED%99%9C%EC%84%B1%ED%99%94" />
