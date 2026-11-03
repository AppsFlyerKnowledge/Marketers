---
title: 마케터를 위한 스마트 배너 웹사이트 코드 구현
metadata:
  keywords:
    - OneLink
    - Advertisers
    - Developer
    - Developers
    - Smart Banner
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2022-01-10T11:25:54Z'
  edited_at: '2026-10-14T10:33:32Z'
  id: 4416119954705
  locale: ko
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/ko/articles/4416119954705
---
> **한눈에 보기:** 스마트 배너 코드를 웹사이트에 추가하여 웹사이트 방문자를 모바일 앱으로 전환시키세요.

> 📘 **참고**
>
> 2023년 11월 8일 기준, 앱스플라이어 스마트 배너 웹 SDK v1은 지원이 종료되었습니다. 웹사이트에 스마트 배너를 표시하기 위해 v2로 업그레이드해야 합니다. <Anchor target="_blank" href="/marketers/ko/docs/bulletin-deprecation-of-appsflyer-smart-banner-web-sdk-v1">더 알아보기</Anchor>

## 웹사이트 코드 구현

이 글은 마케터를 위한 웹사이트 내 스마트 배너 코드 구현 방법입니다. 다음 중 한 가지 방법으로 구현할 수 있습니다.

* Google 태그 관리자 (GTM)
* Adobe Launch 태그 관리 플랫폼
* Shopify
* Wix
* Squarespace
* WordPress

웹사이트에 다른 플랫폼을 통해 코드를 추가하거나 수정하고자 할 때(파라미터 추가, 딥링킹, 배너 숨김, PBA를 스마트 배너와 연동하기 등), <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2">개발자를 위한 스마트 배너 웹사이트 코드 구현 방법</Anchor>을 확인하세요.

**사이트에 스마트 배너 코드를 구현하는 방법**:

1. <Anchor target="_blank" href="/marketers/ko/docs/smart-banners-mobile-web-to-app-for-marketers#1-website-workplace-setup">웹사이트 작업 안내서</Anchor>에 따라 스마트 배너 코드를 찾으세요.
2. 아래 플랫폼별 안내에 따라 웹사이트에 코드를 구현하세요.

<div id="google-tag-manager" />

<Accordion title="Google 태그 관리자">

**Google 태그 관리자를 통해 코드 구현하기**:

1. GTM에서 새 태그를 작성합니다.
2. 태그 이름을 지정한 다음 **태그 구성**을 클릭하고, **맞춤 HTML**을 선택하세요.
3. HTML 입력란에 스마트 배너 코드 스니펫을 붙여넣으세요. 스니펫에 있는 YOUR-BANNER-KEY를 실제 배너 키로 교체합니다.
4. **Triggering**을 클릭하고 화면 상단 우측의 플러스(+) 아이콘을 클릭해서 새로운 트리거를 만듭니다.
5. 트리거의 이름을 설정하고, **트리거 구성**에서 **페이지뷰**를 선택하세요.
6. 배너를 모든 페이지에서 표시하려면, **모든 페이지 표시**를 선택합니다. 배너를 특정 페이지에서만 표시하려면,**일부 페이지 표시**를 선택하고 위에서 만든 태그를 트리거하는 조건을 정의합니다. 트리거에 관해 더 알아보고 싶다면, <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/7679319?hl=en&ref_topic=7679108">GTM 문서</Anchor>를 참조하세요.
7. 상단 우측 코너에 있는 **저장** 버튼을 클릭합니다.
8. 태그 구성 화면으로 돌아가십시오. 모두 설정되었는지 점검하고 상단 우측 코너에 있는 **저장**을 클릭합니다.
9. GTM 컨테이너를 발행하세요.

</Accordion>

<div id="adobe-launch-tag-manager" />

<Accordion title="Adobe Launch 태그 관리 플랫폼">

**Adobe 런치 태그 관리 플랫폼에서 코드 구현하기**

<div id="step-1-create-a-property-in-adobe-experience-cloud" />

<Accordion title="1단계: Adobe Experience Cloud에 속성 생성">

**스마트 배너 코드를 포함할 속성(태그) 생성하기**:

1. **Adobe Experience Cloud** > **Launch**로 가십시오.
2. **Adobe Experience Cloud Launch** 아래 **Go to Launch**를 클릭합니다.
3. **New Property**를 클릭합니다.
4. property 이름을 정합니다.
5. **플랫폼** 아래 **웹**을 선택합니다.
6. 귀하의 웹사이트 도메인을 입력합니다.
7. **저장**을 클릭합니다.

</Accordion>

<div id="step-2-add-smart-banners-code-to-the-adobe-launch-property" />

<Accordion title="2단계: Adobe 런치 속성에 스마트 배너 코드를 추가하세요">

**태그에 스마트 배너 코드를 추가하기 위해서는**:

1. **My web property** 페이지에서 **규칙** 탭을 선택합니다.
2. 규칙의 이름을 지정한다. 권장 사항: **앱스플라이어 스마트 배너**.
3. **'만약'** 절에서, **이벤트** 아래 **+추가** 버튼을 클릭하세요.
   * **이벤트 유형**에서 **코어 - DOM 준비**를 선택하십시오.
   * **변경 유지**를 클릭합니다.
4. **'그런 다음'** 절에서, **액션** 아래 **+추가** 버튼을 클릭하세요.
   * **조치 유형** > **사용자정의 코드**를 클릭하십시오.
   * **JavaScript** > **Open Editor**를 클릭하고 스마트 배너 SDK 스니펫을 **&lt;script> 태그 없이** 붙입니다.
   * **변경 유지**를 클릭하여 코드 편집기를 닫습니다.
5. **저장**을 클릭합니다.

</Accordion>

<div id="step-3-add-the-adobe-launch-tag-to-your-website" />

<Accordion title="3단계: 웹사이트에 Adobe 런치 태그를 추가하기">

**스마트 배너 코드를 로드하기 위해 웹사이트에 Adobe 런치 태그를 추가하려면**:

1. **My web property** 페이지에서 **환경** 탭을 선택합니다.
2. 퍼블리시할 환경(개발 환경 혹은 실 운영 환경)이 있는 행을 찾으십시오.
   * **설치** 섹션에서, 일반적으로 운영 환경인 해당 행의 박스 아이콘을 클릭하세요.
   * **Adobe Launch** 환경을 퍼블리시하는 방법에 대한 섹션을 참조하십시오.
3. **웹 설치 지침** 대화상자에서:
   * 스크립트 코드 스니펫을 복사합니다.
   * 대화 상자를 닫습니다.
4. 코드 스니펫을 귀하의 웹사이트 &lt;head> 태그에 붙여넣습니다.

</Accordion>

<div id="step-4-publish-the-adobe-launch-environment" />

<Accordion title="4단계: Adobe Launch 환경 게시">

**Adobe 런치 태그를 활성화하기 위해 환경을 게시하려면**:

1. **My web property** 페이지에서 **퍼블리싱** 탭을 선택합니다.
2. **Development** 섹션에서 **새 라이브러리 추가**를 클릭합니다.
   1. 라이브러리를 명명하고 환경을 선택하세요.
   2. **리소스 변경** 영역에서 **리소스 추가** 버튼을 클릭하세요.
   3. **규칙** > **스마트 배너 로드** > **최신** > **새 개정 버전 선택 및 작성**을 클릭합니다.
   4. **저장**을 클릭합니다.
3. **Development** 섹션 아래에서:
   1. 새로 생성된 라이브러리 옆에 조치 메뉴(점 3개)를 클릭해서 **Build for Development**를 선택합니다.
   2. 다시 조치 메뉴를 클릭하고 **승인을 위한 제출**을 선택합니다.
4. **제출됨** 섹션 아래에서:
   1. 조치 메뉴를 클릭하고 **Build for Staging**을 선택합니다.
   2. 조치 메뉴를 클릭하고 **퍼블리싱 승인**을 선택합니다.
5. <strong>승인됨</strong> 섹션에서 액션 메뉴를 열고 빌드 및 프로덕션에 배포를 선택해주세요.  
   이제 프로세스가 완료되었습니다.

</Accordion>

웹사이트가 모바일에 로딩될 때, 배너의 활성화된 광고 소재가 노출됩니다. 배너를 특정 페이지나 특정 유저 액션에 따라서만 노출시키려면, <Anchor target="_blank" href="https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/rules.html">Adobe Launch 규칙</Anchor>을 참조하십시오.

</Accordion>

<div id="shopify" />

<Accordion title="Shopify">

**Shopify 내 웹사이트에 코드 구현하기**:

1. Shopify 대시보드에서 **판매 채널** > **온라인 스토어** > **테마**로 들어가세요.  
   현재 사용 중인 테마가 보여집니다.
2. **액션** > **코드 편집**으로 이동해주세요.  
   해당 테마의 코드 편집 페이지가 열립니다.
3. 레이아웃 폴더에서 **`{\}` 테마** 파일을 찾아 클릭하세요.  
   웹페이지의 코드가 나타납니다.
4. 코드 내에서 **&lt;head>** 바로 아래에 귀하의 스마트 배너 코드를 붙여넣으세요.

</Accordion>

<div id="wix" />

<Accordion title="Wix">

**Wix로 만든 웹사이트에 코드 구현하기**:

1. Wix 대시보드에서 **설정**을 선택하세요.
2. 설정의 고급 메뉴에서 **커스텀 코드**를 클릭하세요.
3. **+ 커스텀 코드 추가**를 진행하세요.
4. **여기에 코드 조각을 붙여넣으세요** 입력란에 스마트 배너의 코드를 붙여넣으세요.
5. 코드의 명칭을 이름란에 입력해주세요. **추천**: 앱스플라이어 스마트 배너
6. **페이지에 코드 추가**에서 배너가 표시될 위치를 선택하세요. 다음 중 하나입니다.
   * 모든 페이지에 적용
   * 특정 페이지만 선택
7. **Apply(적용)** 을 클릭합니다.  
   커스텀 코드 페이지에서 이제 새로운 코드가 나타나야 합니다. **Head** 섹션에 코드가 올바르게 배치되었는지 확인하세요.

</Accordion>

<div id="squarespace" />

<Accordion title="Squarespace">

**Squarespace로 만든 웹사이트에 코드 구현하기**:

1. Squarespace 대시보드에서 **웹사이트**를 선택하세요.
2. **설정**을 클릭하세요.
3. **고급**을 진행하세요.
4. **코드 삽입**을 클릭하세요.
5. 헤더 섹션에 스마트 배너의 코드를 붙여넣으세요.
6. **저장** 버튼을 눌러주세요.

</Accordion>

<div id="wordpress" />

<Accordion title="WordPress">

**WordPress로 만든 웹사이트에 코드 구현하기**:

1. WordPress 대시보드에서 **외양** > **테마 편집기**를 찾아 클릭하세요.  
   테마 편집 페이지가 열리면 귀하의 웹사이트 CSS 코드가 표시됩니다.
2. **테마 파일** 아래에서 **테마 헤더(header.php)** 를 선택하세요.
3. 보이는 코드 내에서 **&lt;head>** 바로 아래에 스마트 배너 코드를 적용하세요.
4. **파일 업데이트** 버튼을 클릭해 변경사항을 저장하세요.

</Accordion>

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/pba-web-sdk-integration-guide#installation-and-integration">스마트 배너와 PBA 통합</Anchor>

<div data-zendesk-anchors="h_01HBT97B1ZGKKTD0TN2J2W56ZQ=%EC%B0%B8%EA%B3%A0 website-code-implementation=%EC%9B%B9%EC%82%AC%EC%9D%B4%ED%8A%B8-%EC%BD%94%EB%93%9C-%EA%B5%AC%ED%98%84 h_01HBT97B1Z0F4B8E9GQWJEE6BH=%EC%9B%B9%EC%82%AC%EC%9D%B4%ED%8A%B8-%EC%BD%94%EB%93%9C-%EA%B5%AC%ED%98%84 h_01HBT97B1ZKW36W9F0XQKM323P=google-tag-manager h_01HBT97B1ZX6VM1YER2HXTYQJ2=adobe-launch-tag-manager h_01HBT97B1ZPP0AKB5E31W36VC2=step-1-create-a-property-in-adobe-experience-cloud h_01HBT97B1ZK4T23MF4D6VGP4B8=step-2-add-smart-banners-code-to-the-adobe-launch-property h_01HBT97B1Z0W9VJ5FCW4605RDC=step-3-add-the-adobe-launch-tag-to-your-website h_01HBT97B1Z1W33DTT6NR4PQHQ0=step-4-publish-the-adobe-launch-environment h_01HBT97B1Z0NTYJKB2YFMX62P9=shopify h_01HBT97B1ZYVJ6PW7F811V5TAX=wix h_01HBT97B1ZS0FDM60M1GA04PRT=squarespace h_01HBT97B1ZKYB7XPGFG00PB2BT=wordpress h_01HE7SG3MJ4WTPMTXF0DA0M07D=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
