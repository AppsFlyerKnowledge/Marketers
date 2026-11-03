---
title: 캠페인을 위한 원링크 생성하기
metadata:
  keywords:
    - Marketers
    - onelink
    - Text-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Text-to-App
  created_at: '2016-05-22T10:03:37Z'
  edited_at: '2026-10-14T10:30:39Z'
  id: 208874366
  locale: ko
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/ko/articles/208874366
---
> **한눈에 보기:** 사용자에게 원하는 경험을 정확하게 제공하는 원링크 링크를 만드세요. 링크를 클릭하는 사용자는 올바른 앱 스토어, 웹 URL 또는 앱으로 정확하게 리디렉션됩니다.

## 원링크 링크 및 경험

<Embed title="YouTube video player" typeOfEmbed="youtube" url="https://www.youtube.com/embed/KZBrxGEjVUE" providerUrl="https://www.youtube.com" />

고객은 다양한 온라인 및 오프라인 터치포인트를 통해 귀사의 브랜드와 상호 작용합니다. 유저가 어디에서 왔는지에 관계없이 클릭에서 앱 인스톨, 딥링킹, 디퍼드 딥링킹에 이르기까지 사용자에게 완벽한 경험을 제공하는 링크를 만들 수 있습니다.

링크를 설정하는 데 필요한 단계는 다음 섹션에 자세히 설명되어 있지만 기본적으로 다음 단계를 거쳐야 합니다.

* 유저 경험 선택
* 일반 설정
* 경험별 설정
* 딥링킹 및 리디렉션 설정
* 추가 파라미터 설정

## 캠페인을 위한 원링크 링크 생성하기

| **담당자**<ul><li>원링크 링크를 생성하여 사용자를 앱 스토어, 웹 URL로 리디렉션하거나, 템플릿이 설정된 후 Android App Links와 iOS Universal Links를 통해 앱의 홈 페이지로 열리도록 하는 작업에는 마케터만 있으면 됩니다.</li><li>링크에 딥링킹 및 디퍼드 딥링킹 기능을 추가하려면 마케터와 안드로이드/iOS 개발자가 모두 필요합니다.</li></ul> |
| --- |
| **전제 조건**<ul><li>앱이 하나 이상 포함된 앱스플라이어 계정입니다.</li><li>링크의 기반이 되는 <Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template">원링크 템플릿</Anchor>입니다.</li><li>어트리뷰션의 경우: 각 모바일 앱에 <Anchor target="_blank" href="/marketers/ko/docs/integrate-the-appsflyer-sdk">앱스플라이어 SDK가 설치되어 있어야 합니다.</Anchor><ul><li>앱에 SDK가 아직 설치되지 않은 경우에도 작동하는 리디렉션 링크를 만들 수는 있지만 대시보드, 딥링크 또는 디퍼드 딥링크에서 설치를 측정할 수는 없습니다.</li></ul></li></ul> |
| **소요 시간**<br /><br />대부분 링크의 경우 30분이 소요되지만, 딥링킹 또는 디퍼드 딥링킹 기능이 필요한 링크의 경우 약 3시간이 소요됩니다. |
| **작업 결과**<ul><li>사용자를 기기에 따라 올바른 앱 스토어, 웹 페이지 또는 앱으로 안내하고 원하는 경험을 정확하게 제공하는 링크입니다.</li></ul> |

**특정 유저 경험으로 연결되는 원링크 링크를 생성하려면:**

1. 앱스플라이어의 사이드 메뉴에서 **인게이지** > **원링크 관리**를 선택합니다.
2. **원링크 템플릿**을 선택하여 커스텀 링크를 추가합니다.
3. **링크 추가**를 클릭합니다.
4. 사용자를 위해 만들고자 하는 [경험](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#experiences)을 선택합니다.
5. 미디어 소스를 선택하거나 커스텀 미디어 소스를 입력합니다. 이때 선택/입력한 미디어 소스의 데이터가 앱스플라이어에 표시됩니다 미디어소스는 링크에 `pid` 파라미터 값으로 포함됩니다.
6. **다음**을 클릭합니다.
7. [일반 설정](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings)을 완료합니다.
8. **다음**을 클릭합니다.
9. [선택 사항] 생성 중인 유저 환경과 관련된 절차를 완료합니다.

| 경험 | 절차 옵션 |
| --- | --- |
| <ul><li>소셜-투-앱</li><li>텍스트-투-앱</li><li>리퍼럴-투-앱</li><li>커스텀 링크</li></ul> | <ul><li>[소셜미디어 미리 보기](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-media-preview-og-tags)</li><li>[소셜 앱 랜딩 페이지](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page)</li></ul> |
| 이메일-투-앱 | ESP를 사용하는 경우 <Anchor target="_blank" href="/marketers/ko/docs/email-service-provider-esp-integration-guide">ESP 연동 지침</Anchor>을 따르십시오. |
| 앱-투-앱 | <Anchor target="_blank" href="/marketers/ko/docs/cross-promotion-attribution-for-marketers">크로스 프로모션</Anchor>을 통해 여러 앱에서 작동하는 다이나믹 링크를 만들 수 있습니다. |
| 리퍼럴-투-앱 | <ul><li>[소셜미디어 미리 보기](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-media-preview-og-tags)</li><li>[소셜 앱 랜딩 페이지](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page)</li><li><Anchor target="_blank" href="/marketers/ko/docs/user-invite-attribution">사용자 초대 연동</Anchor>을 통해 앱의 SDK로 리퍼럴-투-앱 링크를 동적으로 생성할 수 있습니다.</li></ul> |

10. **다음**을 클릭합니다.
11. [선택사항] **딥링킹 및 리디렉션**에서 [딥링킹/디퍼드 딥링킹 설정](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking)을 완료합니다. 이 링크가 딥 링크용이 아닌 경우 이 섹션을 건너뛰십시오.
12. [선택 사항] **딥링킹 및 리디렉션**에서 [리디렉션 설정](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#redirection)을 변경합니다. 원링크 템플릿의 리디렉션 설정이 올바른 경우 이 섹션을 건너뛰십시오.
13. **다음**을 클릭합니다.
14. **추가 파라미터**에서 [미리 정의된 파라미터 또는 커스텀 파라미터를 링크에 추가](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#additional-parameters)하여 보다 세분화된 분석을 수행합니다. <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters">어트리뷰션 파라미터에 대해 자세히 알아보기</Anchor>
15. **링크 생성**을 클릭합니다.
16. <Anchor target="_blank" href="/marketers/ko/docs/set-up-your-domain-redirect-allowlist">도메인 리디렉션 허용 목록</Anchor>이 사용자를 리디렉션하려는 모든 도메인으로 업데이트됐는지 확인합니다.

<div id="experiences" />

<Accordion title="유저 경험">

다음 유저 경험에 대한 링크를 만들 수 있습니다.

* **소셜-투-앱**: 소셜미디어에서 사용자의 참여를 유도하고, 소셜미디어 게시물에서 앱으로 안내합니다.
* **앱-투-앱**: 다른 앱에 표시되는 광고를 통해 유저를 귀하의 앱으로 유도합니다.
* **QR-투-앱**: QR 코드를 사용하여 오프라인 고객 경험의 주요 지점에서 사용자가 QR 코드를 스캔하도록 유도하고, 이를 통해 앱 인스톨으로 연결합니다. 데스크톱 사이트나 TV 및 CTV 광고에 QR 코드를 삽입하여 사용자를 앱으로 연결할 수도 있습니다.
* **이메일-투-앱**: 이메일 서비스 제공업체(ESP)를 사용하여 이메일을 통해 사용자의 참여를 유도하고 사용자를 받은 편지함에서 앱으로 유도합니다.
* **텍스트-투-앱**: SMS 및 메시징 캠페인에 대한 링크를 생성하고, 문자 메시지를 통해 사용자의 참여를 유도합니다.
* **리퍼럴-투-앱**: 사용자 또는 인플루언서가 다른 사용자를 앱으로 초대하거나, 특정 인앱 콘텐츠(예: 기사)를 공유할 수 있도록 사용자 초대 링크를 생성합니다.
* **커스텀 링크**: 위에서 언급한 고객 경험에 해당되지 않는 사용자 여정의 경우, 원링크 커스텀 링크를 만들 수 있습니다. 그러면 데스크톱 혹은 모바일, 온-오프라인이든, 온드 미디어, 페이드 미디어 등 사용자가 어디에서 왔는지에 관계없이 적절한 곳으로 쉽게 안내할 수 있습니다.

</Accordion>

<div id="general-settings" />

<Accordion title="일반 설정">

일반 설정은 모든 경험에 적용되는 원링크 링크 생성 프로세스입니다.

**일반 설정을 완료하는 방법**:

1. [선택 사항] 미디어소스 이름을 변경합니다.
2. [선택사항] 캠페인 이름을 변경합니다.
3. [선택 사항] 이 링크를 사용하여 기존 유저를 타겟팅하려는 경우 **리타겟팅**을 켭니다.

   이를 통해 커스텀 링크를 클릭한 사용자가 수행한 리인게이지먼트를 확인할 수 있습니다.

   리타겟팅이 아닌 캠페인(UA) 링크를 클릭한 기존 사용자도 앱이 열리고 동일한 사용자 경험이 제공됩니다. 하지만 리인게이지먼트는 일반 세션으로 기록되기 때문에 온드(owned) 미디어 캠페인의 성공 여부를 측정하는 것은 불가능합니다.

   **중요**! 리타겟팅이 작동하려면 앱에 대한 리타겟팅도 활성화해야 합니다.
4. [선택 사항] **리타겟팅을 위해 활성 사용자 무시**를 켜고 비활성 창을 선택합니다.  
   이렇게 하면 af\_inactivity\_window=[number of days] 파라미터가 링크에 추가되고 해당 기간 동안 활성 상태인 모든 사용자는 리타겟팅을 위해 무시됩니다.
5. 리인게이지먼트 윈도우를 설정하여 리인게이지먼트 후 리타겟팅 미디어 소스가 사용자의 인앱 이벤트에 기여되는 기간을 결정합니다.
   * 값은 일(1&#126;90), 시간(최대 23시간) 또는 수명 단위로 설정할 수 있습니다.
   * 리인게이지먼트 기간은 af\_reengagement\_window 파라미터의 링크에 추가됩니다.
6. [선택 사항] **링크 브랜딩** 하위 섹션에서:
   * 브랜드를 반영할 수 있도록 다른 도메인을 선택하세요. <Anchor target="_blank" href="/marketers/ko/docs/brand-onelink-with-your-domain">더 알아보기</Anchor>
   * <span id="url-id"></span>캠페인 오퍼를 강조 표시하려면 URL ID를 편집합니다. URL ID는 최대 50자여야 하며 문자와 숫자의 조합일 수 있습니다. 기본 세팅은 8자 입니다.

#### 앱에 대한 리타겟팅 활성화

이 앱에 대해 리타겟팅이 설정되지 않았다면, 먼저 앱 리타겟팅을 설정해야 합니다. <Anchor target="_blank" href="/marketers/ko/docs/app-settings#어트리뷰션-설정">더 알아보기</Anchor>

**앱 수준에서 리타겟팅 설정하기**

1. 앱스플라이어의 사이드 메뉴에서 **설정** > **앱 설정**을 선택합니다.
2. **어트리뷰션** 섹션에서 **리인게이지먼트 어트리뷰션**을 활성화합니다.
3. **설정 저장**을 클릭합니다.

</Accordion>

<div id="social-media-preview-og-tags" />

<Accordion title="소셜미디어 미리보기 - OG 태그">

링크를 공유할 때, 오픈 그래프(OG) 태그는 제목, 설명 및 이미지를 포함한 미리 보기를 생성하는 데 사용됩니다.

이러한 OG 태그는 리디렉션하는 웹 URL 또는 앱 스토어에서 자동으로 가져올 수 있습니다. 그러나 이 미리 보기 생성 방법이 실패할 때도 있습니다. 따라서 원링크 UI를 사용하거나 원링크 UI에 생성되지 않은 링크의 경우 링크에 OG 태그 파라미터를 추가하여 원링크에서 소셜 미디어 미리 보기를 설정하는 것이 좋습니다.

소셜 미디어 미리 보기 기능은 다음 플랫폼에서 지원됩니다.

* 페이스북: 게시물 및 DM
* X(구 트위터): 게시물 및 DM
* iMessage
* WhatsApp
* LinkedIn: 게시물 및 DM
* Line
* Telegram
* Slack
* Signal
* 카카오톡
* Discord
* Reddit

**원링크 UI에서 소셜 미디어 미리 보기를 만드는 방법:**

1. 원링크 사용자정의 링크 편집기에서 **소셜 미디어 공유** 섹션으로 이동합니다.
2. **소셜미디어 미리 보기** 섹션에서 다음을 입력합니다.
   * 제목
   * 설명
   * 이미지 URL

**링크에 OG 태그 파라미터를 추가**(원링크 UI에서 생성되지 않은 경우):

* 다음 필수 파라미터를 추가합니다.
  * af\_og\_title(최대 40자)
  * af\_og\_description(최대 300자)
  * af\_og\_image

**참고:**

* OG 태그 파라미터를 앱스플라이어 UI 외부의 링크에 추가할 수 있습니다.
* X(이전의 트위터)에 대해 별도의 OG 태그를 추가하면 일반 앱스플라이어 미리보기가 덮어쓰여집니다.

</Accordion>

<div id="social-app-landing-page" />

<Accordion title="소셜 앱 랜딩 페이지">

> 🚧 **중요!**
>
> 이제 iOS Universal Links가 Meta ads에서 지원됩니다.
>
> * Meta는 이제 <Anchor target="_blank" href="/marketers/ko/docs/meta-ads-faq#are-ios-universal-links-and-android-app-links-supported-in-meta-ads">Universal Links를 지원</Anchor>하므로, Universal Links를 지원하는 메타 유료(paid) 광고에는 더 이상 소셜 앱 랜딩 페이지가 필요하지 않습니다.
> * 온드(owned) 게시물(비유료 광고)에는 소셜 앱 랜딩 페이지가 필요합니다.

소셜 미디어 앱은 Universal Links를 사용하는 기존 사용자들의 자연스러운 앱 경험을 방해할 수 있습니다. 이는 다음 방법으로 해결할 수 있습니다.

* [**권장**] 소셜미디어 앱 랜딩 페이지를 만듭니다.  
  소셜 미디어 앱 랜딩 페이지를 만들 때는 URI 스킴이 설정되어 있는지 확인하는 것을 권장합니다.
* [대안] `af_force_deeplink=true` 파라미터를 사용하여 <Anchor target="_blank" href="/marketers/ko/docs/onelink-troubleshooting-and-faq#강제-딥링킹">앱을 강제로 열도록</Anchor> 합니다.  
  **참고**: 이 파라미터는 카카오톡, 네이버, 네이버 블로그, 크롬, 웨이보, X(구 트위터)에서 자동으로 활성화됩니다.

소셜 앱 랜딩 페이지를 통해 소셜 미디어 앱 광고를 클릭한 사용자가 앱스플라이어 생성 랜딩 페이지로 리다이렉트됩니다. 사용자는 이 랜딩 페이지에서 딥링킹이 되거나 앱 설치를 계속할 수 있습니다.

앱스플라이어는 다양한 소셜 앱 랜딩 페이지 템플릿을 제공합니다. 템플릿 구성 요소 위치는 고정되어 있지만, 배경 이미지 또는 색상, 제목, 텍스트, 이미지, 버튼, 태그 등을 포함하여 구성 요소 자체는 사용자 지정할 수 있습니다.

소셜 앱 랜딩 페이지는 다음 소셜미디어 앱에서 사용할 수 있습니다.

* 인스타그램
* 페이스북/페이스북 메신저(**참고**: 페이스북과 페이스북 메신저의 경우 URI 스킴과 소셜 앱 랜딩 페이지가 모두 설정되어 있으면 소셜 앱 랜딩 페이지가 표시되지 않습니다.)
* LinkedIn
* iOS용 Pinterest
* Snapchat
* X(구 트위터)
* WeChat

**사용자 경험**

사용자가 랜딩 페이지에 있는 CTA 버튼을 클릭하면,

* **앱이 이미 설치된 경우**: 앱이 실행됩니다.
* **앱이 설치되지 않은 경우**: 사용자는 관련 앱 스토어로 이동합니다. 설치 시 사용자 딥링킹을 연기할 수 있습니다([딥링킹 및 디퍼드 딥링킹](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking)에서 설명).

> 📘 **참고**
>
> 소셜 앱 랜딩 페이지는 원링크 짧은 URL만 지원합니다.

#### **소셜 앱 랜딩 페이지를 사용하는 방법:**

1. 다음 섹션에 설명된 대로 랜딩 페이지를 설정합니다.
2. 생성된 원링크 **짧은** URL을 기록합니다.  
   소셜 앱 랜딩 페이지는 긴 원링크 URL에서 작동하지 않습니다.
3. 소셜 앱에 원링크 짧은 URL을 게시합니다.

어트리뷰션은 어트리뷰션 설정에 따라 결정됩니다.

#### **소셜 앱 랜딩 페이지 설정하기:**

1. 커스텀 링크 설정에서 **소셜-투-앱** 섹션으로 이동합니다.
2. **소셜 앱 랜딩 페이지** 섹션에서 **소셜 앱 랜딩 페이지 생성**을 클릭합니다.  
   랜딩 페이지 템플릿을 선택할 수 있는 창이 열립니다.  
   [![](https://files.readme.io/82a65bf446c4e6ae8803eaf048cc95ebe9c312f574fb8eda2764c123f0a50ee6-30151216576657.jpg)](https://files.readme.io/82a65bf446c4e6ae8803eaf048cc95ebe9c312f574fb8eda2764c123f0a50ee6-30151216576657.jpg)
3. 랜딩 페이지 템플릿을 선택하려면, 선택한 템플릿 위로 마우스를 가져간 다음 **만들기**를 클릭합니다. **팁**: 템플릿의 🛈 아이콘 위로 마우스를 가져가면, 어떤 경우에 템플릿을 사용해야 하는지 확인할 수 있습니다. 인스타그램용 템플릿은 Clustered Poster와 ShowAndTell을 추천합니다.
4. 랜딩 페이지 크리에이티브의 모든 요소를 맞춤화할 수 있습니다. 맞춤화를 위해 크리에이티브 요소 이름을 선택하거나 미리보기 이미지에서 해당 요소를 클릭합니다.    
   **팁**: 크리에이티브 템플릿을 교체할 경우를 대비하여 텍스트를 저장합니다.
5. 모든 템플릿 이미지를 나만의 이미지로 바꿉니다.  
   1. 확장자를 포함한 이미지 URL을 입력합니다. (예: `https://example.com/image.png`)
   2. 사용 가능한 파일 유형: jpeg, jpg, png.    
      **참고**: webp 형식은 지원되지 않습니다.
   3. 이미지에 대한 권장 사항은 다음과 같습니다.  

| 템플릿 이미지 유형 | 최대 이미지 파일 크기 | 이미지 비율 |
| --- | --- | --- |
| 컬렉션 | 300 KB | 16:9 (가로) |
| <ul><li>Trapeze</li><li>Carousel</li><li>ShowAndTell</li></ul> | 300 KB | 1:1 |
| <ul><li>Flyer</li><li>Poster</li><li>Blurry poster</li><li>Clustered poster</li></ul> | 300 KB | 9:16 (세로) |

   4. 이미지 중 하나 이상이 정확한 URL이 아닌 경우 오류가 표시되며 크리에이티브를 검토할 수 없습니다.  
      [![](https://files.readme.io/63223efc74994143111d5a5ef6b2d5fa7b84ac4f1033f8713d96cc293ba47588-30151216583697.png)](https://files.readme.io/63223efc74994143111d5a5ef6b2d5fa7b84ac4f1033f8713d96cc293ba47588-30151216583697.png)
6. 랜딩 페이지 크리에이티브를 검토하려면 **검토**를 클릭합니다.  
   변경이 필요한 경우 **편집기로 돌아가기**를 클릭합니다.  
   [![](https://files.readme.io/90b52321a6f7061a77624ec4486d6e2628c38c49ea0de734cf1c1fd0bc888cee-30151216593169.png)](https://files.readme.io/90b52321a6f7061a77624ec4486d6e2628c38c49ea0de734cf1c1fd0bc888cee-30151216593169.png)
7. 랜딩 페이지를 저장하려면 **완료**를 클릭합니다.  
   **중요**: 신규/업데이트된 랜딩 페이지 크리에이티브는 커스텀 링크를 생성/업데이트한 후에만 적용됩니다.
8. [선택 사항] 랜딩 페이지를 편집하려면 **소셜 앱 랜딩 페이지 편집**을 클릭합니다.

</Accordion>

<div id="deep-linking-and-deferred-deep-linking" />

<Accordion title="딥링킹 및 디퍼드 딥링킹">

딥링킹이란 기존 앱 사용자를 리타겟팅하여 앱 스토어나 앱 홈 페이지로 먼저 연결하지 않고 앱 내의 특정 경험(예: 특정 페이지)으로 바로 보내는 것을 의미합니다. 리타겟팅 어트리뷰션을 사용하면 해당 사용자가 어트리뷰트됩니다.

디퍼드 딥링킹은 신규 사용자에게 기존 사용자와 유사한 딥링킹 경험을 제공한다는 의미입니다. 하지만 유저 플로우는 먼저 새로운 사용자들이 앱 스토어로 이동하고, 앱을 다운로드하고 실행한 후에 특정 경험이나 페이지로 이동하는 방식입니다.

**참고**: 딥링킹 및 디퍼드 딥링킹을 설정하려면 안드로이드 및 iOS 개발자가 필요합니다.

**사용자를 앱의 특정 경험으로 안내하도록 딥링킹 및 디퍼드 딥링킹을 설정하려면:**

1. iOS와 안드로이드 개발자에게 문의하여, 링크에 설정할**deep\_link\_value** 를 계획합니다.
   * **deep\_link\_value**는 사용자가 안내될 특정 인앱 콘텐츠의 값 이름입니다. 개발자는 코드에서 **deep\_link\_value**의 원하는 동작을 구현합니다.
   * 개발자들은 코드에서 원하는 동작을 구현합니다. 가이드를 공유하여 기술 플로우를 이해하고 예시를 확인합니다.
     * 앱 유무에 관계없이 신규 또는 기존 사용자를 대상으로 [딥링킹 및 디퍼드 딥링킹](https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl)을 지원합니다.  
       **UDL에 대한 고려 사항:**
       * SDK V6.1 이상이 필요합니다.
       * 클릭 룩백 윈도우는 최대 15분까지 가능합니다.
     * **참고**: 이미 딥링킹에 원링크를 사용하고 있는 고객은 UDL 대신 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_gcd_legacy">안드로이드</Anchor> 및 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_gcd_legacy">iOS</Anchor> 레거시 메소드를 사용할 수 있습니다.  

       > 👍 **팁**
       >
       > **deep\_link\_value**는 제품 SKU, 소셜미디어 게시물 ID, URL 경로 또는 기타 값을 기반으로 할 수 있습니다.
       >
       > 개발자와 협력하여 장기적으로 **deep\_link\_value**및 기타 파라미터나 값에 대한 최적의 시스템을 마련하는 것이 중요합니다. 이렇게 하면 추가 앱 업데이트를 최소화할 수 있습니다. **매번 앱 코드를 변경할 필요 없이** 앱 내에서 다양한 콘텐츠로 연결되는 다양한 딥링크를 생성하려면 개발자와 동적 값 사용에 대해 논의하세요.
       >
       > 예를 들어, 과일 종류의 **deep\_link\_value**가 선택되었고, 개발자가 그 값을 동적으로 설정했습니다. 이렇게 하면 개발팀의 추가 작업 없이도 마케터가 모든 과일을 입력할 수 있습니다.
       >
       > `https://onelink-sample-app.onelink.me/H5hv?pid=Email&c=fruit_of_the_month``&deep_link_value=apples``...`
       >
       > `https://onelink-sample-app.onelink.me/H5hv?pid=Email&c=fruit_of_the_month``&deep_link_value=bananas``...`
       >
       > `https://onelink-sample-app.onelink.me/H5hv?pid=Email&c=fruit_of_the_month``&deep_link_value=peaches``...`

2. 개발자가 앱이 선택한 파라미터 및 값에 따라 작동하는 것을 확인하면, 링크 설정 페이지의 **딥링킹 및 리디렉션** 섹션에서, 개발자와 결정한 대로 **딥 링크 값**을 입력합니다.
3. [선택 사항] 딥링킹에 하나 이상의 인앱 경험이 필요한 경우(예: 사용자를 상품으로 연결하고 별도로 할인을 제공하려는 경우) 딥링크 데이터 페이로드에 (파라미터 deep\_link\_sub1을 사용하는) **추가 딥링크 값**을 추가할 수 있습니다. **추가 파라미터** 섹션에서 딥링크 파라미터(deep\_link\_sub2-10)를 추가할 수 있습니다.
   1. iOS 및 안드로이드 개발자에게 연락하여 값을 계획합니다.
   2. 개발자들은 코드에서 원하는 동작을 구현합니다. 원링크 가이드를 개발자와 공유하여 기술 플로우를 이해하고 예시를 확인하세요.

      <Tabs>
      <Tab title="안드로이드">

      <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_overview">안드로이드 개발자 지침</Anchor>

      </Tab>

      <Tab title="iOSUnity">

      <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_overview">iOS 개발자 지침</Anchor>

      </Tab>
      </Tabs>

   3. **추가 파라미터** 섹션에서 개발자와의 협의 및 결정 사항에 따라 필요한대로 커스텀 파라미터 **deep\_link\_sub2-10**와 값을 추가합니다.

> 📘 **참고**
>
> 개발자가 파라미터와 동적 값을 구현하면, 마케터는 원링크 API를 사용하여 커스텀 링크를 수천 개 자동 생성할 수 있습니다. <Anchor target="_blank" href="/marketers/ko/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">더 알아보기</Anchor>

</Accordion>

<div id="redirection" />

<Accordion title="리디렉션">

**신규 사용자를 앱 스토어 대신 랜딩 페이지로 보내려면 다음 단계를 따르세요.**

1. 링크 설정 페이지의 **딥링킹 및 리디렉션** 섹션에서, “앱이 설치되지 않은 경우” 선택 사항에서 사용자를 다른 URL로 보내도록 선택합니다.  
   안드로이드 및 iOS 커스텀 URL은 신규 사용자를 지정한 랜딩 페이지로 리디렉션합니다.   
   **주의!** 원링크 템플릿에 사용자 지정 URL에 대한 설정 값이 이미 있는 경우 이러한 사용자 지정 링크 URL이 해당 값을 재정의합니다.
2. 신규 사용자를 <Anchor target="_blank" href="/marketers/ko/docs/redirect-users-to-custom-app-store-product-pages">커스텀 스토어 제품 페이지</Anchor>로 보낼 수도 있습니다.

</Accordion>

<div id="additional-parameters" />

<Accordion title="추가 파라미터">

링크에 캠페인, 광고 세트 이름, 광고 이름, 채널, 사용자 지정 파라미터 또는 1&#126;5개의 <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#what-are-subscriber-parameters-good-for">구독자 파라미터</Anchor>와 같은 추가 파라미터를 추가할 수 있습니다. 어트리뷰션 파라미터를 여러 가지로 설정하면, 마케팅 성과를 더욱 상세하게 분석할 수 있습니다. <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters">추가 어트리뷰션 파라미터</Anchor>에 대해 자세히 알아보세요.

추가 딥링킹 파라미터(deep\_link\_sub2-10)를 추가할 수도 있습니다.

**파라미터를 추가하려면**:

1. 링크 설정의 **추가 파라미터** 섹션에서 **파라미터 추가**를 클릭합니다.
2. 추가할 파라미터를 선택하거나 커스텀 파라미터를 입력합니다.

</Accordion>

<div id="testing" />

<Accordion title="테스트">

링크가 다음 사용자를 리디렉션 하는지 테스트할 수 있습니다.

* 앱이 설치되지 않은 신규 사용자
* 앱이 설치된 기존 사용자

#### 앱이 설치되지 않은 신규 사용자

**선행 조건**: 앱이 설치되지 않은, <Anchor target="_blank" href="/marketers/ko/docs/registering-test-devices">등록된 테스트 디바이스</Anchor>

**링크를 테스트하는 방법**:

1. 앱스플라이어의 사이드 메뉴에서 **참여** > **원링크 관리**를 선택합니다.
2. 테스트하고자 하는 링크의 **액션** 아이콘을 클릭하고 **URL 가져오기**를 클릭합니다.
3. 휴대폰으로 숏링크 URL이나 롱링크 URL을 보냅니다. 다음 둘 중 하나를 수행하세요.
   * 휴대폰 카메라 또는 QR 스캐너 앱으로 QR 코드를 스캔합니다.
   * 이메일 또는 WhatsApp으로 링크를 보내고, 휴대폰에서 엽니다.  
     **참고:** iOS 노트에 붙여넣거나 모바일 브라우저에 직접 붙여넣지 마세요. 모바일 OS가 의도적으로 앱을 열지 않을 수 있습니다.
4. 모바일 기기에서 링크를 클릭합니다.  
   플랫폼에 따라 앱 스토어 또는 랜딩 페이지로 이동합니다.  
   **참고**: 모바일 디바이스에서 실제 클릭이 필요합니다. 자바스크립트 또는 301/302 리디렉션이 Universal Links 및 안드로이드 App Links를 트리거할 수 없습니다. 스크립트로 클릭을 만드는 경우, 일부 브라우저에서는 기본 리디렉션도 되지 않습니다.
5. 앱을 다운로드하고 실행합니다.
   * 앱이 실행되고 홈 화면에서 열립니다.
   * 디퍼드 딥링킹을 구현한 경우, 앱은 링크 파라미터에서 지정한 콘텐츠로 열립니다.
6. 앱스플라이어 **대시보드 개요**에서 신규 인스톨을 찾습니다.  
   미디어소스(예: 테스트) 및 URL에 입력한 캠페인 이름에서 새 클릭 및 인스톨을 찾습니다.

링크가 예상대로 작동하지 않습니까? <Anchor target="_blank" href="/marketers/ko/docs/onelink-troubleshooting-and-faq">원링크 FAQ 및 문제 해결 가이드</Anchor>에서 해결 방법을 확인하세요.

#### 앱이 설치된 기존 사용자

**선행 조건**: 앱이 설치된 안드로이드 및/또는 iOS 기기. 개발자들이 변경한 (Universal Links, App Links, 및/또는 URI 스킴을 구현한) 앱의 소스와 버전이 맞는지 확인하세요.

**링크를 테스트 하려면:**

1. 앱스플라이어의 사이드 메뉴에서 **인게이지** > **원링크 관리**를 선택합니다.
2. 선택된 **원링크 템플릿** 클릭합니다.
3. 목록에서 커스텀 링크를 선택합니다.
4. 테스트하고자 하는 링크의 **액션** 아이콘을 클릭하고 **URL 가져오기**를 클릭합니다.
5. 휴대폰으로 숏링크 URL이나 롱링크 URL을 보냅니다. 다음 둘 중 하나를 수행하세요.
   * 휴대폰 카메라 또는 QR 스캐너 앱으로 QR 코드를 스캔합니다.
   * 이메일 또는 WhatsApp으로 링크를 보내고, 휴대폰에서 엽니다.  
     **참고:** iOS 노트에 붙여넣거나 모바일 브라우저에 직접 붙여넣지 마세요. 모바일 OS가 의도적으로 앱을 열지 않을 수 있습니다.
6. 모바일 기기에서 링크를 클릭합니다.
   * 앱이 실행되고 홈 화면에서 열립니다.
   * 딥링킹을 구현한 경우 앱은 링크 파라미터에서 지정한 콘텐츠로 열립니다.
7. 앱스플라이어로 **개요** 대시보드로 이동합니다. (**보기 유형: 리타겟팅**)  
   링크의 미디어소스(예: test)와 URL에 입력한 캠페인 이름 아래에서 새로운 클릭/리인게이지먼트(앱 열기)를 찾으십시오.

링크가 예상대로 작동하지 않습니까? <Anchor target="_blank" href="/marketers/ko/docs/onelink-troubleshooting-and-faq">원링크 FAQ 및 문제 해결 가이드</Anchor>에서 해결 방법을 확인하세요.

</Accordion>

## 추가 절차

<div id="create-a-custom-impression-url" />

<Accordion title="커스텀 노출 URL 만들기">

커스텀 노출 링크를 통해 다음을 수행할 수 있습니다.

* 표시하는 광고의 <Anchor target="_blank" href="/marketers/ko/docs/about-conversion-rates#마케팅-퍼널-단계-및-전환율-1">노출 대비 클릭 전환율</Anchor>을 측정합니다.
* 노출에 대한 어트리뷰션을 받습니다.

**전제 조건:** 작동되는 원링크 긴 URL. 짧은 URL은 지원되지 않습니다.

**직무별 작업:**

마케터 및 웹 개발자

**노출 수 측정을 위한 노출 URL을 생성하는 방법:**

1. 앱스플라이어의 사이드 메뉴에서 **참여** > **원링크 관리**를 선택합니다.
2. 테스트하려는 링크의 옵션 메뉴 위로 마우스를 가져간 다음, **URL 가져오기**를 클릭합니다.
3. 편집할 원링크 긴 URL을 복사합니다.  
   예시:  `https://subdomain.onelink.me/j7rN?pid=email&c=Spring`
4. 서브 도메인(또는 브랜드 도메인을 사용하는 경우 전체 브랜드 도메인)을 '노출 수'로 바꿉니다.  예시:  `https://impressions.onelink.me/j7rN?pid=email&c=Spring`
5. 노출 URL을 복사하여 개발자에게 보냅니다.
6. 웹 개발자에게 웹사이트 로직에 노출 URL을 구현하도록 요청하세요.

웹사이트 페이지에서 노출 수를 집계하는데 사용될 수 있지만, **신규 인스톨 기여가 할당되지 않는** 노출 URL를 만들었습니다.  뷰-쓰루 어트리뷰션의 경우 다음 단계를 따르세요.

**어트리뷰션에 노출 URL을 사용하려면:**

1. 전 단계에서 설명한 대로 노출 URL을 준비합니다.
2. <Anchor target="_blank" href="/marketers/ko/docs/measure-view-through-engagements">뷰-쓰루 어트리뷰션이 켜져 있는지</Anchor> 확인하세요.
3. [선택 사항] 기본 1일 뷰-쓰루 <Anchor target="_blank" href="/marketers/ko/docs/set-up-lookback-windows">룩백 기간</Anchor> 값을 변경하려면 `af_viewthrough_lookback` 파라미터에 새 값을 추가합니다. 예시: `af_viewthrough_lookback=1d`.
4. 노출 URL을 복사하여 개발자에게 보냅니다.
5. 웹 개발자에게 웹사이트 로직에 노출 URL을 구현하도록 요청합니다.

전체 노출 URL 예시:

```http
https://impressions.onelink.me/j7rN?pid=email&c=Spring&af_viewthrough_lookback=1d
```

</Accordion>

<div id="deep-linking-post-event" />

<Accordion title="딥링킹 포스트 이벤트">

이벤트 이후에만 사용자를 특정 활동이나 페이지로 딥링킹해야 하는 경우가 있습니다. 예시:

* 로그인
* 초기 화면
* 이용 약관 동의
* 기타

**이벤트 후 사용자를 딥링킹하려면**:

개발자에게 [안드로이드](https://dev.appsflyer.com/hc/docs/dl_android_dl_post_event) 및 [iOS](https://dev.appsflyer.com/hc/docs/dl_ios_dl_post_event)용 포스트 이벤트 유저 딥링킹에 대한 가이드를 따르도록 요청합니다.

</Accordion>

<div id="deferred-deep-linking-with-ios-private-relay" />

<Accordion title="iOS 비공개 릴레이를 사용한 디퍼드 딥링킹">

iOS 15 출시와 함께 Apple은 iCloud+ 사용자에게 <Anchor target="_blank" href="https://www.macworld.com/article/348965/icloud-plus-private-relay-safari-vpn-ip-address-encryption-privacy.html">비공개 릴레이</Anchor> 기능을 제공하여 웹 브라우징 트래픽을 암호화하고, 정확한 위치, IP 주소 및 브라우징 트래픽의 내용을 숨길 수 있는 옵션을 제공합니다. 사용자가 비공개 릴레이를 선택하면 어트리뷰션 및 디퍼드 딥링킹이 방해될 수도 있습니다. 즉, 앱이 없는 신규 사용자가 앱 스토어로 이동하여 앱을 설치 및 실행하면 비공개 릴레이를 통해 앱의 특정 페이지로 전송되는 것을 방지할 수 있습니다.

디퍼드 딥링킹(DDL)이 예상대로 계속 작동하도록 하려면 다음 앱스플라이어 솔루션 중 하나를 구현해야 합니다.

* **[권장] 앱 클립 기반 솔루션**: 사용자 어트리뷰션 데이터를 제공하는 앱 클립을 생성하여 DDL을 통해 달성하고자 하는 것과 유사한 맞춤형 앱 클립 경험으로 사용자를 안내합니다. 앱 클립에는 사용자를 앱 클립에서 전체 앱으로 안내하는 플로우도 포함시킬 수 있습니다.
* **클립보드 기반 솔루션**: URL에서 디퍼드 딥링킹 데이터를 복사하고 사용자를 앱으로 올바르게 리디렉션하는 웹 랜딩 페이지를 생성합니다. **참고**: 이 솔루션은 어트리뷰션에 도움이 되지 않습니다.

<div id="app-clipbased-solution" />

<Accordion title="앱 클립 기반 솔루션">

이 솔루션은 원링크 짧은 URL과 iOS에서 사용할 수 있는 앱 클립 기술을 결합하여 전체 앱을 설치할 필요 없이 사용자를 제품의 특정 플로우로 보낼 수 있습니다. 원링크 짧은 URL은 사용자 어트리뷰션 데이터를 제공하며, DDL을 통해 달성하고자 하는 것과 유사한 맞춤형 앱 클립 경험으로 사용자를 안내합니다. 앱 클립에는 사용자를 앱 클립에서 전체 앱으로 안내하는 플로우도 포함할 수 있습니다. **참고**: 사용자가 앱 클립 기반 솔루션에서 전체 앱을 재설치하면, 앱스플라이어에 오가닉 인스톨로 보고될 수 있습니다. 

#### **플로우**

앱 클립 기반 DDL 솔루션의 플로우는 다음과 같습니다.

1. 광고주가 앱 클립을 생성하고 비공개 릴레이가 켜져 있는 사용자를 위해 원링크 템플릿에 추가합니다.
2. 사용자가 원링크 URL을 누릅니다.
3. 앱스플라이어 웹 핸들러는 다음과 같은 사항을 확인합니다.
   * iOS 15 이상 버전의 기기를 사용 중
   * Safari 브라우저
   * 사용자가 비공개 릴레이 기능 설정
4. 앱스플라이어에서 위 사항을 확인하면 사용자에게 **앱 클립 재생** 또는 **Safari에서 보기**를 클릭하도록 프롬프트가 표시됩니다.
   * 사용자가 **앱 클립 재생**을 클릭하면 앱 클립 카드가 사용자에게 표시됩니다.
   * 사용자가 Safari에서 보기를 클릭하면 랜딩 페이지가 열리고 앱 클립을 열라는 메시지가 표시됩니다.
5. 사용자가 앱 클립을 엽니다.
6. 앱 클립이 열리고 앱 마케터와 개발자가 결정한 경험을 사용자에게 제공합니다.
7. 앱 클립에 사용자를 전체 앱으로 안내하는 흐름이 포함된 경우, 사용자는 전체 앱을 다운로드할 수 있도록 앱 스토어로 이동합니다. 앱이 실행되면 개발자가 정의한 사용자 경험이 제공됩니다.

**전제 조건:** 앱스플라이어 SDK V6.4.0 이상

**앱 클립 기반 DDL 솔루션을 설정하려면**:

1. 개발자에게 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_private_relay#app-clip-based-solution">앱 클립 기반 솔루션 개발 허브 지침</Anchor>을 따르도록 요청하고, 원하는 사용자 경험을 제공하는 앱 클립을 만듭니다. 여기에는 앱 클립에서 전체 앱으로 사용자를 안내하는 플로우도 포함됩니다.
2. [Universal Links](https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#procedures-for-ios-universal-links) 및 [디퍼드 딥링킹](/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking)이 포함된 <Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template">원링크 템플릿</Anchor>을 만들거나 편집합니다.
3. 원링크 템플릿에서 **사용자에게 개인 릴레이가 있는 경우 앱 클립 표시**를 설정하십시오. 앱 클립이 없는 경우 이 기능을 켜지 마세요.  
   **참고**: Universal Links가 있는 원링크 템플릿을 변경할 때 앱 클립 기능을 추가(또는 제거)하는 등의 작업을 수행하면 AASA 파일이 업데이트되는 데 몇 시간이 걸릴 수 있습니다. 따라서 템플릿을 기반으로 만든 링크에는 업데이트된 기능이 바로 적용되지 않을 수 있습니다.
4. 원링크 템플릿을 기반으로 커스텀 링크를 만듭니다.
5. App Store Connect에서 **앱 클립 경험** 섹션으로 이동하여 **앱 URL**로 스크롤한 후 원링크 템플릿 URL(도메인+템플릿 ID)을 입력하십시오. 예: `yourbrand.onelink.me/GrbZ`) 또는 특정 원링크 사용자 지정 링크의 짧은 URL입니다.  
   **참고**: 원링크 커스텀 링크를 입력하면, 앱 클립 기반 솔루션은 해당 특정 링크를 탭하는 사용자에게만 작동하며 원링크 템플릿을 기반으로 생성된 다른 링크는 작동하지 않습니다.

</Accordion>

<div id="clipboardbased-solution" />

<Accordion title="클립보드 기반 솔루션">

#### **플로우**

클립보드 기반 DDL 솔루션의 플로우는 다음과 같습니다.

1. 광고주가 파라미터 `af_cp_lp=true`를 포함하는 디퍼드 딥링크를 생성합니다.
2. 사용자가 디퍼드 딥링크를 탭합니다.
3. 앱스플라이어가 다음 사항을 확인합니다.
   * iOS 15 이상 버전의 기기를 사용 중
   * Safari 브라우저
   * 사용자가 비공개 릴레이 기능 설정
   * 링크에 파라미터 `af_cp_lp=true` 포함
4. 앱스플라이어가 상기 사항을 확인하면, 앱 아이콘, 이미지 및 CTA를 포함하는 웹 랜딩 페이지가 App Store에서 애플리케이션을 가져오기 위해 로드됩니다. 또한 사용자에게 앱의 특정 페이지로 이동하는 최상의 사용자 경험을 보장하기 위해 URL이 복사된다는 프로세스를 설명하는 메시지가 표시됩니다.  
   ![ios_15_ip_masking__1_.png](https://files.readme.io/c130314c98ebd42f50feaafd752c0cea954f42c5bfd99a6dbd94daf9e48c2ff4-30151216595345.png)
5. 사용자가 **앱 가져오기**를 누릅니다.
6. 사용자가 앱 스토어로 가서 앱을 설치합니다. 그런 다음, 앱 첫 실행 시 특정 앱 페이지로 이동합니다.

#### **요구 사항**

랜딩 페이지 DDL 솔루션 복사/붙여넣기에는 다음이 필요합니다.

* Safari에서 웹을 검색할 사용자.
* 디퍼드 딥 링크에 `af_cp_lp=true` 파라미터 포함.
* 앱스플라이어 iOS SDK V6 이상.
* iOS 앱 개발자가 클립보드의 URL에 디퍼드 딥링크 데이터를 붙여넣는 코드를 구현할 수 있습니다. 이는 앱스플라이어 SDK의 일부가 아닙니다.
* 엔드 유저가 확인란을 선택한 상태로 유지합니다. (기본값) 이 옵션을 선택하지 않으면 URL이 복사되지 않고 디퍼드 딥링킹이 작동하지 않습니다.

#### **설정**

**클립보드 기반 DDL 솔루션을 설정하는 방법**:

1. 아래 사항을 iOS 개발자에게 요청합니다. 
   1. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_private_relay#clipboard-based-solution">dev hub 지침</Anchor>을 따라 앱스플라이어 SDK에 필요한 코드를 연동합니다.
   2. 클립보드에서 URL에 디퍼드된 딥링크 데이터를 붙여넣는 코드를 구현합니다. 이는 앱스플라이어 SDK의 일부가 아닙니다.
2. 링크에 `af_cp_lp=true` 파라미터를 추가합니다.   
   앱스플라이어 원링크 커스텀 링크 UI에서 커스텀 파라미터를 추가하거나, 링크에 파라미터를 추가하기만 하면 됩니다.

</Accordion>

</Accordion>

## 추가 정보

<div id="examples" />

<Accordion title="예시">

**기본 예시**

마크는 'Feed Me'라는 성공한 식품 배달 서비스의 마케터입니다. 마크는 사용자 기반 전화번호를 타겟팅하여 Feed Me의 새로운 모바일 iOS 및 안드로이드 앱을 다운로드를 유도하고 자합니다. 또한 SMS 캠페인도 계획되어 있습니다. 하지만 마크는 어떤 사용자가 안드로이드 또는 iOS 디바이스를 가지고 있는지 알지 못합니다. 또한 앱을 설치했는지 여부도 알 수 없습니다.

이를 해결하기 위해 마크는 원링크에서 제공하는 짧은 URL이 포함된 SMS를 사용자에게 보냅니다. 사용자가 SMS를 수신하고 링크를 클릭합니다.

* 아직 앱이 없는 경우 앱을 쉽게 설치할 수 있는 적절한 앱 스토어 또는 랜딩 페이지로 자동 연결됩니다.
* 이미 앱이 설치되어 있으면 앱이 자동으로 열립니다.

신규 인스톨과 리인게이지먼트는 SMS 캠페인으로 어트리뷰션되며, 마크는 앱스플라이어에서 SMS 캠페인의 성공 여부를 확인할 수 있습니다. 

**딥링킹 예시**

위의 예시에서 마케터의 SMS는 사용자가 앱을 다운로드하고 실행하도록 유도하는 데 어느 정도 성공했습니다. 하지만 링크를 클릭하고 앱을 실행한 사용자 중 주문으로 전환한 사용자는 많지 않았습니다.

따라서 마크는 앱 구매 시 복숭아, 사과 또는 아보카도 한 봉지를 무료로 제공하여 전환율을 높이기로 결정합니다. 이를 위해 마크는 기존 사용자를 위한 원활한 딥링킹 환경을 구축합니다. 사용자들에게 이 세 가지 건강 과일의 이점을 강조하는 자세한 이메일을 보냅니다. 

이메일에 언급된 각 과일에 대해 마크는 모바일 개발자의 도움을 받아 다음과 같이 구성한 원링크 기반의 딥링크 값이 포함된 링크를 포함시킵니다.

이를 해결하기 위해 마크는 원링크에서 제공하는 짧은 URL이 포함된 SMS를 사용자에게 보냅니다. 사용자가 SMS를 수신하고 링크를 클릭합니다.

* 이미 앱이 설치되어 있는 경우, 관련 과일 페이지로 바로 이동합니다.
* 아직 앱이 없는 경우, 디바이스에 따라 적절한 앱 스토어 또는 랜딩 페이지로 이동합니다. 그리고 앱을 다운로드하고 열면 바로 과일 페이지로 이동합니다.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="특징 및 제한 사항">

| 특징 | 설명 |
| --- | --- |
| <span id="onelink-characters"></span>원링크 문자 | <ul><li>총 URL 길이는 2000자를 초과할 수 없습니다.</li><li>링크 이름 및 미디어소스: 150자를 초과할 수 없습니다.</li><li>짧은 URL ID는 50자를 초과할 수 없습니다.</li><li>추가 리디렉션 파라미터 <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#special-characters">특성 및 제한 사항</Anchor>을 참조하십시오.</li></ul> |
| <span id="maximum-links"></span>최대 링크 수 | 앱스플라이어에서 생성할 수 있는 원링크 링크의 최대 수는 계정당 120,000개입니다. |
| <span id="posting-onelink-urls-in-web-pages"></span>웹 페이지에 원링크 URL 게시하기 | HTML href 태그에 `target="_blank"` 를 사용해도 Google Play 또는 App Store로 리디렉션되지 않습니다. 원링크 URL이 **target="\_blank”** 속성이 있는 html **a** 태그 안에 배치되면, 안드로이드 및 iOS의 Chrome에서 빈 페이지가 열립니다. 이는 원링크 기능에 영향을 줍니다. **a** 태그에 타겟 어트리뷰트가 있는지 여부를 확인하십시오. |
| <span id="agencies"></span>에이전시 | 에이전시는 원링크 템플릿이나 링크를 사용할 수 없습니다. 커스텀/온드 미디어 원본에만 사용할 수 있습니다. |
| <span id="ad-networks"></span>애드 네트워크 | 에이전시는 원링크 템플릿이나 링크를 사용할 수 없습니다. 커스텀/온드 미디어 원본에만 사용할 수 있습니다. |
| <span id="social-media-preview-image"></span>소셜 미디어 미리보기 이미지 | <ul><li>이미지 유형이 소셜미디어 플랫폼에서 지원되지 않는 경우 표시되지 않습니다.</li><li>WhatsApp의 경우 이미지는 300KB를 초과할 수 없습니다.</li></ul> |
| <span id="desktop"></span>데스크톱 | 데스크톱 사용자를 다른 URL로 리디렉션하도록 원링크 URL 또는 템플릿을 설정하면, 매개변수 `af_web_dp`의 링크에 웹 URL이 추가됩니다. 링크에 `af_web_dp`가 포함된 경우, 앱스플라이어는 데스크톱의 클릭을 등록하지 않습니다. |
| <span id="af_enc_data"></span>af\_enc\_data | 노출 URL에서는 지원되지 않습니다. |
| <span id="android-social-apps-webview-deep-linking-redirection"></span>안드로이드 소셜 앱 WebView | 최근 여러 안드로이드 소셜 앱의 변경으로 인해, 내부 브라우저 뷰(WebView)에서 일부 딥링크 및 스토어 리디렉션 흐름이 작동하지 않게 되었습니다.<br /><br />**안드로이드 앱 링크**:<br /><br />현재 Facebook 인앱 브라우저 내에서 클릭할 때 안드로이드 앱 링크는 지원되지 않습니다. 이 흐름에서 URI 스킴을 사용하는 링크는 기존과 동일하게 작동합니다.<br /><br />**리디렉션 저장**<br /><br />변경 사항을 수용하고 딥링킹 및 리디렉션을 다시 활성화하기 위해 다음 안드로이드 소셜 앱에 추가적인 사용자 상호작용을 도입해야 했습니다.<ul><li>Facebook 버전 v420 이상</li><li>인스타그램</li><li>Facebook 메신저</li><li>Snapchat</li></ul>새로운 사용자 플로우에서는 위에 언급된 앱의 사용자들이 Google Play 스토어 및 기타 써드 파티 스토어로 리디렉션되기 위해 추가 랜딩 페이지 버튼을 클릭해야 합니다.<br /><br />이 버튼은 자동으로 추가되며, 아무런 조치가 필요하지 않습니다.<br /><br />**참고:**<ul><li>Facebook 버전 420 이하에서는 추가적인 사용자 상호작용 없이 기존과 동일하게 작동합니다.</li><li>Facebook 게시물의 Facebook 앱 링크(URI 스킴 사용)는 추가적인 사용자 상호작용 없이 기존과 동일하게 작동합니다.</li><li>Instagram 채팅에서의 Facebook App Links는 추가적인 사용자 상호작용 없이 기존과 동일하게 작동합니다.</li><li>딥링킹 플로우에서 앱이 설치되지 않은 경우, 오류 팝업 메시지가 표시되는 제한 사항이 있습니다. 이 메시지는 플로우에 영향을 주지 않으며 사용자는 여전히 스토어로 리디렉션됩니다.</li></ul> |
| <span id="onelink-link-previews-sometimes-fail-to-display-correctly-on-facebook-and-linkedin"></span>원링크 링크 미리보기 | **설명**  <br />원링크 링크 미리보기가 Facebook 및 LinkedIn에서 올바르게 표시되지 않는 경우가 있습니다. 대상 웹사이트가 미리보기 요청의 `AppsFlyerBot-Previewer/1.0` 사용자 에이전트 문자열을 로봇(또는 크롤러)에서 보낸 것으로 인식하지 못할 때 문제가 발생합니다. 이러한 경우, 웹사이트는 적절한 OG 태그가 지정된 미리보기 콘텐츠로 응답하지 않습니다.<br /><br />**해결 방안**  <br />웹사이트의 robot.txt 파일을 업데이트하여 `AppsFlyerBot-Previewer/1.0`사용자 에이전트 헤더 문자열이 포함된 페이지를 로봇에서 온 것으로 처리하도록 랜딩 페이지를 구성할 수 있습니다. |
| <span id="deep-linking-is-not-supported-on-android-naver-blog-app"></span>안드로이드 네이버 블로그 앱 | 안드로이드 네이버 블로그 앱에서는 딥링킹이 지원되지 않습니다. 사용자는 링크에 정의된 대로 구글 플레이 또는 웹 리디렉션으로 이동합니다. |
| <span id="chrome-browser-on-ios"></span>iOS의 크롬 브라우저 | Chrome iOS의 변경 사항으로 인해 사용자가 iOS의 Chrome에서 URI 스킴 링크를 클릭할 때마다 앱 열기 또는 앱 스토어 리디렉션을 확인하라는 팝업이 표시됩니다. |
| <span id="telegram-webview"></span>텔레그램 WebView | 텔레그램 WebView(텔레그램 브라우저)에서 유저 인게이지먼트에 대한 확률적 모델링 어트리뷰션은 작동하지 않습니다. WebView가 인게이지먼트 요청에 디바이스 모델과 OS 버전을 포함하지 않기 때문입니다. |

</Accordion>

<div data-zendesk-anchors="onelink-links-and-experiences=%EC%9B%90%EB%A7%81%ED%81%AC-%EB%A7%81%ED%81%AC-%EB%B0%8F-%EA%B2%BD%ED%97%98 h_01H8Y6DDT4M8XGAEJJVTHKHPKV=%EC%9B%90%EB%A7%81%ED%81%AC-%EB%A7%81%ED%81%AC-%EB%B0%8F-%EA%B2%BD%ED%97%98 create-a-onelink-link=%EC%BA%A0%ED%8E%98%EC%9D%B8%EC%9D%84-%EC%9C%84%ED%95%9C-%EC%9B%90%EB%A7%81%ED%81%AC-%EB%A7%81%ED%81%AC-%EC%83%9D%EC%84%B1%ED%95%98%EA%B8%B0 h_01H8Y6DDT41C6JYKXET0NDRB1G=%EC%BA%A0%ED%8E%98%EC%9D%B8%EC%9D%84-%EC%9C%84%ED%95%9C-%EC%9B%90%EB%A7%81%ED%81%AC-%EB%A7%81%ED%81%AC-%EC%83%9D%EC%84%B1%ED%95%98%EA%B8%B0 h_01H8Y6DDT4C543RS2BXAGS487M=experiences h_01H8Y6DDT4WZ5FKZYBX2H08MFD=general-settings enable-retargeting-for-the-app=%EC%95%B1%EC%97%90-%EB%8C%80%ED%95%9C-%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%ED%99%9C%EC%84%B1%ED%99%94 h_01H8Y6DDT4R7785X5DRES66BKJ=%EC%95%B1%EC%97%90-%EB%8C%80%ED%95%9C-%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%ED%99%9C%EC%84%B1%ED%99%94 h_01H8Y6DDT4JT9H0R13ZNGHJ79S=social-media-preview-og-tags h_01H8Y6DDT4PHY2F5E3GK582P51=social-app-landing-page h_01H8Y6DDT463F5569B28DD17SV=%EC%A4%91%EC%9A%94 h_01H8Y6DDT4MMD1AW6D1PNGNX5X=%EC%B0%B8%EA%B3%A0 to-use-the-social-app-landing-page=%EC%86%8C%EC%85%9C-%EC%95%B1-%EB%9E%9C%EB%94%A9-%ED%8E%98%EC%9D%B4%EC%A7%80%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 h_01H8Y6DDT4JB4RT438MAGNNX2S=%EC%86%8C%EC%85%9C-%EC%95%B1-%EB%9E%9C%EB%94%A9-%ED%8E%98%EC%9D%B4%EC%A7%80%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 to-set-up-the-social-apps-landing-page=%EC%86%8C%EC%85%9C-%EC%95%B1-%EB%9E%9C%EB%94%A9-%ED%8E%98%EC%9D%B4%EC%A7%80-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 h_01H8Y6DDT4G34S3RV3ZH64XT19=%EC%86%8C%EC%85%9C-%EC%95%B1-%EB%9E%9C%EB%94%A9-%ED%8E%98%EC%9D%B4%EC%A7%80-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 h_01H8Y6DDT5XNJVYW2Y8F6JWPK2=deep-linking-and-deferred-deep-linking h_01H8Y6DDT5JR3B3DMR87JCBZ69=%ED%8C%81 h_01H8Y6DDT5KSBE00WWDGQ5R1AQ=%EC%B0%B8%EA%B3%A0-1 h_01H8Y6DDT58FC3HMSRZBMGZZRJ=redirection h_01H8Y6DDT5AAQ3BZD8QB9H19QB=additional-parameters h_01H8Y6DDT5B6M7CETQRD9NKX8R=testing new-users-without-your-app-installed=%EC%95%B1%EC%9D%B4-%EC%84%A4%EC%B9%98%EB%90%98%EC%A7%80-%EC%95%8A%EC%9D%80-%EC%8B%A0%EA%B7%9C-%EC%82%AC%EC%9A%A9%EC%9E%90 h_01H8Y6DDT50DH5TGVVPJPJC4MG=%EC%95%B1%EC%9D%B4-%EC%84%A4%EC%B9%98%EB%90%98%EC%A7%80-%EC%95%8A%EC%9D%80-%EC%8B%A0%EA%B7%9C-%EC%82%AC%EC%9A%A9%EC%9E%90 existing-users-with-your-app-installed=%EC%95%B1%EC%9D%B4-%EC%84%A4%EC%B9%98%EB%90%9C-%EA%B8%B0%EC%A1%B4-%EC%82%AC%EC%9A%A9%EC%9E%90 h_01H8Y6DDT5KDEWS40XPYGYC8HK=%EC%95%B1%EC%9D%B4-%EC%84%A4%EC%B9%98%EB%90%9C-%EA%B8%B0%EC%A1%B4-%EC%82%AC%EC%9A%A9%EC%9E%90 additional-procedures=%EC%B6%94%EA%B0%80-%EC%A0%88%EC%B0%A8 h_01H8Y6DDT5YR8JA5YMZFPMCC2X=%EC%B6%94%EA%B0%80-%EC%A0%88%EC%B0%A8 h_01H8Y6DDT58EFS8S46D1AVP3T1=create-a-custom-impression-url h_01H8Y6DDT5S4NEJMNJR4K3QMNH=deep-linking-post-event h_01H8Y6DDT58Y6CS27M2W3MHYAD=deferred-deep-linking-with-ios-private-relay h_01H8Y6DDT5A7J07KNNRWCXCBH2=app-clipbased-solution flow=%ED%94%8C%EB%A1%9C%EC%9A%B0 h_01H8Y6DDT5VDKAR89B8N6D7YMB=%ED%94%8C%EB%A1%9C%EC%9A%B0 h_01H8Y6DDT62H71A8DPG00A3ZTN=clipboardbased-solution flow::21baf6ac=%ED%94%8C%EB%A1%9C%EC%9A%B0-1 h_01H8Y6DDT638T7C9HQHZ1CJ726=%ED%94%8C%EB%A1%9C%EC%9A%B0-1 requirements=%EC%9A%94%EA%B5%AC-%EC%82%AC%ED%95%AD h_01H8Y6DDT6JGP33AWFQV6Z8FF0=%EC%9A%94%EA%B5%AC-%EC%82%AC%ED%95%AD setup=%EC%84%A4%EC%A0%95 h_01H8Y6DDT61ENGJFZ1XS28GS1T=%EC%84%A4%EC%A0%95 additional-information=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01H8Y6DDT679SGBTSM669F9FHV=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01H8Y6DDT6TX4WTP2HYRF11DZ3=examples h_01H8Y6DDT6TQYRS81BMHARB62S=traits-and-limitations" />
