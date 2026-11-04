---
title: 원링크 템플릿 만들기
metadata:
  keywords:
    - template
    - Marketers
    - Link Management
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Link Management
  created_at: '2014-11-03T12:35:49Z'
  edited_at: '2026-10-14T10:39:33Z'
  id: 207032246
  locale: ko
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/ko/articles/207032246
---
> **한눈에 보기:** 다양한 마케팅 캠페인을 위해 생성하는 모든 원링크 링크에 대한 리디렉션 논리의 기초를 형성하는 템플릿을 생성합니다. 링크 및 최종 사용자 경험을 생성하려면 템플릿이 필요합니다.

<div id="onelink-templates" />

## 원링크 템플릿

<Embed title="원링크 템플릿 만들기" typeOfEmbed="youtube" url="https://www.youtube.com/embed/d4AtCJ9122Q" providerUrl="https://www.youtube.com" />

원링크 템플릿:

* 최종 사용자가 클릭할 수 있는 링크가 아니라 많은 사용자 지정 링크를 생성하기 위한 기초입니다. 일반적으로 앱당 하나의 템플릿만 있으면(테스트 제외) 모든 다른 광고 캠페인에 대해 원하는 만큼의 링크를 생성할 수 있습니다.
* 사용자를 사용자 디바이스 OS와 기존 앱 설치 상태 여부에 따라 어디로 리디렉션할지 정합니다.
* 다양한 마케팅 캠페인에 사용하기 위해 생성하는 모든 원링크의 핵심에 있는 라우팅 로직을 나타냅니다. 여기에는 다음에 대한 리디렉션 설정이 포함됩니다.
  * **앱을 설치하지 않은 신규 사용자**: 올바른 앱 스토어 또는 웹 URL로 연결합니다.
  * **앱이 이미 설치된 기존 사용자**: 안드로이드 앱 링크, iOS 유니버설 링크 또는 URI 스키마를 통해 앱을 엽니다. 여기에는 설정을 위한 일부 개발자 작업이 포함됩니다.
  * **참고**: 웹 사이트 또는 앱 스토어의 리디렉션 설정을 링크 수준에서 재정의할 수 있습니다.

<div id="create-a-onelink-template" />

## 원링크 템플릿 만들기

| 담당자 | 필수 조건 | 소요 시간 | 작업 결과 |
| --- | --- | --- | --- |
| <ul><li>앱을 설치하지 않은 신규 사용자를 위한 리디렉션 로직(예: 올바른 앱 스토어 또는 웹 페이지로)을 설정하려면 마케터만 필요합니다.</li><li>이미 앱을 인스톨한 기존 앱 사용자를 위한 리디렉션 로직을 추가하려면(예: 앱 열기) 마케터와 안드로이드/iOS 개발자가 모두 필요합니다.</li></ul> | <ul><li>앱이 하나 이상 포함된 앱스플라이어 계정입니다.</li><li>마케터는 앱스플라이어 어드민 사용자거나 원링크 템플릿을 추가/편집하기 위한 관리 권한이 있어야 합니다.</li></ul> | 안드로이드/iOS 개발자가 협업하여 약 1.5시간이 필요합니다. | 사용자를 올바른 앱 스토어, 웹 페이지 또는 기기를 기반으로 하는 앱으로 보내는 링크를 생성할 수 있는 템플릿이 생성됩니다. |

<div id="create-a-onelink-template-with-redirection-logic-for-new-app-users" />

<Accordion title="신규 앱 사용자를 위한 리디렉션 로직이 있는 원링크 템플릿 만들기">

**원링크 템플릿 작성하기:**

1. 앱스플라이어의 사이드 메뉴에서 **참여** > **원링크 관리**를 선택합니다.  
   원링크는 앱스플라이어 계정 수준 기능으로, 모든 앱에 대한 원링크 템플릿과 해당 사용자 지정 커스텀 링크를 만들 수 있습니다.  
   [![](https://files.readme.io/c5aacf61d1d1dc75ac7f0b9b6f681bb00e6521f6436fad3d2f073a42d4b0153f-4406696125713.png)](https://files.readme.io/c5aacf61d1d1dc75ac7f0b9b6f681bb00e6521f6436fad3d2f073a42d4b0153f-4406696125713.png) **참고**: 생성된 템플릿이 없는 경우, 온보딩 마법사가 열립니다. 마법사의 지침을 따르고 나머지 절차는 무시하십시오.
2. 메뉴 아이콘 > **원링크 템플릿 추가**를 클릭합니다.  
   원링크 템플릿 설정 페이지가 열립니다.  
   [![OneLink_template_page_en-us.png](https://files.readme.io/d773d60cd2febcf6a8389e9586e8ca23a1515fc853e4d42d0db98661cacb387a-360009665478.png)](https://files.readme.io/d773d60cd2febcf6a8389e9586e8ca23a1515fc853e4d42d0db98661cacb387a-360009665478.png)
3. **원링크 템플릿 이름** 입력란에 이름을 입력합니다.

   <div id="note" />

   > 📘 **참고**
   >
   > * 훌륭한 원링크 템플릿 이름에는 **앱 이름**(예: feed\_me)이나 원링크가 나타내는 사용 사례 또는 경험(예: pre\_launch\_landing\_page)이 포함됩니다.
   > * 이름에는 캠페인이나 채널 이름, 미디어소스(실제 최종 사용자 링크가 아니라 많은 링크를 만들기 위한 기본 템플릿) 또는 플랫폼 이름(안드로이드, iOS. 여러 플랫폼이 보통 원링크 템플릿을 사용하는 이유)이 포함되지 않아야 합니다.
   > * 이 템플릿 이름은 내부에서만 사용됩니다. 따라서 마케팅 어트리뷰션 데이터에 영향을 미치지 않으며 사용자에게 표시되지 않습니다.

4. **하위 도메인** 입력란에 <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-knowledge-base-glossary#하위-도메인">하위 도메인</Anchor> 이름을 입력합니다.
   * 브랜드에 맞는 하위 도메인을 선택하세요. 예를 들어, 웹 사이트가 [www.abcd.com](https://www.abcd.com)이면 하위 도메인으로 abcd를 선택합니다.
   * 사용자는 이 서브 도메인을 링크 URL의 일부로 보게 됩니다. 예시: `https://abcd.onelink.me/RPsv/37e5cd36`.
   * 이 템플릿을 바탕으로 사용자 지정 커스텀 링크가 생성된 후에는 서브 도메인을 변경할 수 없습니다.
   * 영문 소문자, 숫자, 하이픈(-)만 사용할 수 있습니다.
   * 또한 원링크는 완전한 브랜드 도메인을 지원하므로 캠페인 성과를 개선하고 브랜드 노출을 높일 수 있습니다.  <Anchor target="_blank" href="/marketers/ko/docs/brand-onelink-with-your-domain">더 알아보기</Anchor>
5. 안드로이드 앱, iOS 앱 또는 둘 다를 선택합니다.
6. (선택 사항) 추가 파라미터 이용한 링크 도용을 방지하려면 보안 단축 링크 기능을 켜세요. **보안 단축 링크를 활성화하려면 다음 단계를 따르세요.**

   **보안 단축 링크** 에서 **'추가 파라미터 사용하여 클릭에 속성을 부여하지 않음'** 을 켜세요.

   이것이 여러분에게 의미하는 바는 다음과 같습니다. 이 기능이 활성화되면, 누군가가 이 템플릿으로 생성된 단축 링크에 매개변수를 추가하더라도 해당 클릭 집계되지 않습니다. 사용자는 템플릿의 리디렉션 설정에 따라 리디렉션되며, 출처 표기만 변경됩니다.

   > 📄 **예시**
   >
   > | 링크 | 완료 후 |
   > | --- | --- |
   > | `[subdomain].onelink.me/[template_id]/[shortlink_id]` | 평소와 같이 출처가 명시되어 있습니다. |
   > | `[subdomain].onelink.me/[template_id]/[shortlink_id]?param=value` | 매개변수가 추가되어 클릭 이 기록되지 않습니다. |


   > 📘 **참고**
   >
   > * 이 설정은 템플릿 수준 에서 적용됩니다. 개별 링크에 대해 이 기능을 켜거나 끌 수 있는 방법은 없습니다.
   > * 이 기능이 출시 전에 생성된 템플릿의 경우 해당 설정은 비활성화되어 있습니다. 원하시면 켜세요. 출시 이후에 생성된 템플릿의 경우 기본적으로 활성화되어 있으며, 원하지 않으면 비활성화할 수 있습니다.

7. **앱이 설치되지 않은 경우,** 사용자를 리디렉션할 위치를 설정합니다.  
   * 안드로이드 앱과 iOS 앱을 선택한 경우, 템플릿은 기본적으로 신규 앱 사용자를 올바른 앱 스토어로 보내도록 설정됩니다.
   * 안드로이드나 iOS 중 하나의 앱만 선택한 경우, 템플릿은 모든 사용자(iOS와 안드로이드, 신규 및 기존 사용자)를 정의된 단일 대상으로 보내도록 구성됩니다.
   * 구글 플레이에 없는 안드로이드 앱을 선택하는 경우, 안드로이드 사용자를 리디렉션하는 URL을 입력해야 합니다.
   * [선택 사항] 구글 플레이 이외의 다른 스토어에서 앱을 다운로드할 수 있는 경우, **타사 앱 스토어로 리디렉션**합니다. 다른 스토어에 등록된 앱의 패키지 이름이 원링크 템플릿에서 선택한 안드로이드 앱의 패키지 이름과 동일한지 확인하세요.
   * [선택 사항] **다른 URL로 변경**: 경우에 따라 신규 사용자를 앱 스토어로 직접 보내는 대신, 모바일 웹 환경으로 유도하는 것이 더 적절할 수 있습니다. (또는 앱이 스토어에 등록되어 있지 않을 수도 있습니다.) 변경을 위해 URL 입력란에 새로운 URL을 입력합니다. **참고**: 타사 리디렉션과 다른 URL을 모두 설정한 경우 기본 리디렉션은 타사 앱 스토어로 설정됩니다.
   * [선택 사항] **비공개 릴레이를 사용하는 사용자를 위해 앱 클립을 표시**하도록 설정합니다.(iOS 14 이상에서 사용 가능) <Anchor target="_blank" href="/marketers/ko/docs/apple-app-clips-integration-guide">앱 클립에 대해 자세히 알아보세요</Anchor>.
8. **앱이 설치된 경우,** 위 과정은 생략됩니다. 이에 대해서는 [다음 절차](/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users)에서 설명합니다.
9. [선택 사항] **데스크톱에서 링크를 클릭한 경우**, 링크 목적지를 변경하십시오.  
   * 특히 이메일이나 소셜 미디어를 통해 링크가 전송되면, 데스크톱 컴퓨터에서 링크를 클릭하는 경우가 있습니다. 링크에 데스크톱 트래픽이 많이 발생할 것으로 예상되는 경우, 해당 사용자를 올바른 앱 스토어 대신 랜딩 페이지나 기본 웹사이트 홈페이지 또는 휴대폰에서 SMS 링크를 요청할 수 있는 페이지로 유도하는 것이 좋습니다.
   * 기본 설정으로 데스크톱 사용자는 템플릿에 설정된 앱에 따라 웹 버전의 앱 스토어나 구글 플레이 스토어로 리디렉션됩니다.
     * 기본 스토어 옵션을 변경하려면 "데스크톱 웹 URL(Desk web URL)"을 선택하고 관련 웹 스토어 URL을 추가하십시오. 리디렉션 허용 목록에 스토어 도메인을 추가해야 합니다.
10. [선택 사항] **다른 플랫폼에서 앱 선택**   
    다음 전용 앱 버전을 사용하는 경우:
    * **윈도우즈 휴대폰**: 토글을 켜고 앱을 선택하거나 **다른 URL로 변경**을 선택합니다.
    * **아이패드**: 토글을 켜고 아이패드 앱을 선택합니다.
    * **아마존 킨들 파이어**: 토글을 켜고 아마존 스토어 ASIN 또는 앱 페이지 URL을 추가합니다.
11. **원링크 템플릿 저장**(편집한 템플릿의 경우 원링크 템플릿 업데이트)을 클릭합니다.   
    이제 원링크 템플릿이 생성되었으며 다양한 클릭 가능한 링크를 만드는 데 사용할 수 있습니다(<Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">링크 및 경험</Anchor> 참조).

</Accordion>

<div id="add-redirection-logic-for-existing-app-users" />

<Accordion title="기존 앱 사용자를 위한 리디렉션 로직 추가">

기존 앱 사용자는 일반적으로 앱 스토어나 웹 페이지가 아닌, 앱 내부로 직접 이동되는 것을 선호합니다. 클릭 후 앱을 직접 여는 데 사용할 수 있는 기술은 다음 세 가지입니다.

* **iOS** **유니버설 링크**: iOS 9 이상에서 작동하며, 앱을 열 때 원활하고 안전한 사용자 경험을 제공합니다.
* **안드로이드 앱 링크**: Android 6 이상에서 작동하며 앱을 열 때 원활하고 안전한 환경을 제공합니다. **참고**: 삼성 인터넷 브라우저는 안드로이드 앱 링크를 사용하여 앱을 열 수 없습니다.
* **URI 스킴**:  
  * 대체 방법:
    * 안드로이드: URI 스킴은 안드로이드 앱 링크가 제대로 작동하지 않거나 설정되어 있지 않아 앱을 열지 못할 경우를 대비한 효과적인 예비 수단입니다.
    * iOS: 유니버설 링크가 작동하지 않거나 설정되지 않아 앱을 열지 못하는 경우에 대비한 제한된 대체 기능입니다. <Anchor target="_blank" href="/marketers/ko/docs/uri-scheme-fallback-for-ios">더 알아보기</Anchor>
  * 삼성 디바이스에서 앱을 여는 기본 방법입니다.
  * 앱이 설치되었을 경우, 접속할 때 이 주소에서 앱을 엽니다. 웹사이트 링크와 비슷하지만 웹사이트 대신 앱을 열 수 있습니다.
  * iOS와 안드로이드에서 동일해야 합니다.

최상의 사용자 환경, 보안 및 디바이스 적용 범위를 위해 가능한 한 많은 기술을 사용하도록 설정하는 것이 좋습니다. 모든 링크 기술을 활성화하면 원링크가 각 사용자에게 가장 적합한 방법을 자동으로 적용합니다.

**기존 앱 사용자에 대한 리디렉션 로직을 원링크 템플릿에 추가하는 방법:**

1. 앱스플라이어의 사이드 메뉴에서 **참여** > **원링크 관리**를 선택합니다.
2. 편집할 원링크 템플릿을 선택합니다.
3. 메뉴 아이콘(⋮)을 클릭한 후 **Edit OneLink Template(원링크 템플릿 편집)** 을 클릭합니다.
4. 아래로 스크롤하여 **When app is installed(앱이 설치된 경우)** 로 이동합니다. [![](https://files.readme.io/c0e8e5364f0b184f33d72e33f28df131d5a8bb6c377dc74f0ec190bcc6e63e75-18363965490833.png)](https://files.readme.io/c0e8e5364f0b184f33d72e33f28df131d5a8bb6c377dc74f0ec190bcc6e63e75-18363965490833.png)
5. 다음 지침에 따라 iOS, 안드로이드 및 대체 옵션을 설정합니다.

   <Tabs>
   <Tab title="iOS 유니버설 링크">

   유니버설 링크는 일반 웹 링크(예: https://yourbrand.onelink.me 또는 https://www.yourbrand.com)의 형식을 사용하므로 하위 도메인을 설정해야 합니다([이전 가이드](/docs/create-a-onelink-template#원링크-템플릿-만들기) 참고). 원링크는 완전 <Anchor target="_blank" href="/marketers/ko/docs/brand-onelink-with-your-domain">브랜드 도메인</Anchor>도 지원하지만 이 가이드를 완료하기 위해 반드시 필요한 것은 아닙니다.

   **유니버설 링크로 앱 실행하기**:

   1. iOS 개발자에게 문의:
      * 이 원링크 템플릿의 하위 도메인을 iOS 개발자에게 제공합니다.
      * iOS 개발자에게 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#procedures-for-ios-universal-links">이 가이드</Anchor>에 따라 작업할 것을 요청합니다.
      * 개발자는 팀 ID(Apple 앱 ID 접두사(예: PF23MIWNTW)라고도 함)를 제공합니다.
      * 앱이 아직 게시되지 않은 경우 개발자는 번들 식별자(예: com.myapp.something)도 제공해야 합니다.  
        [![](https://files.readme.io/c469a6c99515b0d76d075b0036ea118af16cd11b2ef134a63499acf0467895a0-18363965493521.png)](https://files.readme.io/c469a6c99515b0d76d075b0036ea118af16cd11b2ef134a63499acf0467895a0-18363965493521.png)
   2. 원링크 템플릿 페이지에서 **Change to launch the app using Universal Links(유니버설 링크를 이용한 앱 오픈으로 변경)** 를 클릭하세요.
   3. 새 창에서 **Launch the app using Universal Links(유니버설 링크를 사용하여 앱 실행)** 을 선택합니다.
   4. **팀 ID(Team ID)** 입력란에 개발자가 제공한 팀 ID를 입력합니다.
   5. 앱이 게시되지 않은 경우 **번들 식별자**도 입력합니다.
   6. **변경 사항 저장**을 클릭합니다.

   </Tab>

   <Tab title="안드로이드 앱 링크">

   앱 링크는 일반 웹 링크 형식(예: https://yourbrand.onelink.me 또는 https://www.yourbrand.com)을 사용하므로 하위 도메인을 설정해야 합니다([이전 가이드](/docs/create-a-onelink-template#원링크-템플릿-만들기) 참조). 원링크는 완전 <Anchor target="_blank" href="/marketers/ko/docs/brand-onelink-with-your-domain">브랜드 도메인</Anchor>도 지원하지만 이 가이드를 완료하기 위해 반드시 필요한 것은 아닙니다.

   **시작하기 전**:

   이 원링크 템플릿에 선택한 하위 도메인을 기록합니다.

   **안드로이드 앱 링크로 앱 실행하기**:

   1. 안드로이드 개발자에게 문의:   
      안드로이도 개발자에게 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#generating-a-sha256-fingerprint">다음 지침</Anchor>에 따라 SHA256 핑거프린트 생성을 요청합니다.  
      개발자가 마케터에게 생성된 SHA256 핑거프린트를 제공합니다. 예:`DC:65:43:67:F3:BD:02:52:AC:B4:50:F1:74:54: 23:49:4D:49:6C:E6:DF:56:BD:CB:53:06:11:5B:C9:4E:5D:0C`
   2. 원링크 템플릿 페이지에서 **Change to launch the app using Universal Links(유니버설 링크를 이용한 앱 오픈으로 변경)** 를 클릭하세요.
   3. 새 창에서 **앱 링크를 사용하여 앱 실행**을 선택합니다.
   4. **SHA256 fingerprint** 입력란에 개발자가 제공한 SHA256 fingerprint를 입력합니다.  
      자동 생성된 인텐트 필터 코드가 나타납니다.
   5. 안드로이드 개발자에게 문의:   
      자동으로 생성된 인텐트 필터 코드를 제공합니다.  
      <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#adding-app-link-intent-filter-to-main-activity">이 가이드</Anchor>를 따라 작업을 완료하도록 요청하고 확인합니다.

   </Tab>

   <Tab title="URI 스킴">

   URI 스킴은 iOS와 안드로이드 사용자 모두에 적용되는 대체 옵션이므로 양쪽 모두 동일하게 설정해야 합니다.

   **안드로이드 및 iOS URI 대체 옵션 설정하기:**

   1. iOS와 안드로이드 개발자에게 문의하여 URI 스킴을 정합니다. 예: `feedmeapp://`

      <div id="h_01H9Q4E7VR4CAK0PJY269GQ9XJ" />

      > 👍 **팁**
      >
      > * 앱 스킴 이름은 Apple과 Google 모두에서 중복되어도 허용됩니다. **브랜드 고유의 스킴 이름을 선택하여** 여러 애플리케이션에서 스킴이 충돌하지 않도록 하세요. 스킴 이름으로는 일반적으로 앱의 번들 ID를 사용하는 것이 권장됩니다. 예시: **com.company.app**
      > * 원링크를 iOS와 안드로이드에서 모두 사용하려면, **양쪽 플랫폼에서 같은 스킴을 정의하는 것**이 중요합니다. 다음은 <Anchor target="_blank" href="https://help.contrast.co/hc/en-us/articles/200865293-URL-Scheme-Intro-for-App-Developers">iOS</Anchor> 및 <Anchor target="_blank" href="https://developer.android.com/training/app-links/deep-linking.html">안드로이드에</Anchor> 대한 지침입니다.
      > * URI 스킴은 http나 https로 시작해서는 안 됩니다.

   2. iOS 개발자에게 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#procedures-for-uri-scheme">이 지침</Anchor>에 따라 URI 스킴을 구현하도록 요청합니다.  
      **그리고**  
      안드로이드 개발자에게 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#procedures-for-uri-scheme">다음 지침에 따라</Anchor> 앱에서 URI 스킴을 구현하도록 요청합니다.
   3. 완료 후, 개발자는 구현된 URI 스킴의 값을 확인합니다. `exampleapp://`, `exampleapp://home` 또는 `exampleapp://main` 등과 같습니다.
   4. 원링크 템플릿 페이지에서 **URI 스킴 추가**를 클릭하여 앱을 실행합니다.
   5. 팝업창에서 **URI 스킴을 사용하여 앱 실행**을 선택합니다.
   6. URI 스킴 값을 입력합니다.
   7. **변경 사항 저장**을 클릭합니다.
   8. URI 스킴 테스트(이 작업은 회원님 또는 개발자가 수행 가능):
      1. 앱이 설치된 iOS 및 Android 기기에서 <Anchor target="_blank" href="https://halgatewood.com/deeplink/">무료 공개 테스트 도구</Anchor>로 이동합니다.
      2. 이 도구에서 생성한 링크를 탭합니다.  
         URI 스킴이 옳은 경우, 앱이 열립니다.

   </Tab>
   </Tabs>

6. **원링크 템플릿 업데이트**를 클릭합니다.

<div id="note-1" />

> 📘 **참고**
>
> * 원링크 템플릿을 저장하거나 업데이트하면, 앱스플라이어는 앱 도메인을 확인하기 위해 AASA 및/또는 디지털 자산 링크 JSON 파일을 자동으로 생성하고 이를 호스팅합니다. 이 작업은 유니버설 링크와 앱 링크가 제대로 작동하는 데 매우 중요합니다.
> * 원링크 템플릿 업데이트가 적용되려면 최대 1시간이 소요될 수 있습니다.

</Accordion>

<div id="customize-qr-codes" />

<Accordion title="QR 코드 사용자 지정">

![OnelinkQRFinal__1_.gif](https://files.readme.io/6eb996db8c8bcdb8ac46380151fc54c8ef5b686999aaaef3d1a951d627eadc70-11902870808081.gif)

원링크를 통해 생성된 QR 코드는 다음과 같이 사용자 지정할 수 있습니다.

* 로고를 QR 코드에 추가하기
* QR 코드의 색상 변경하기

**참고**: QR 코드 사용자 지정은 개별 링크 수준이 아닌 템플릿 수준에서 이루어집니다. 따라서 사용자 지정은 편집된 템플릿을 기반으로 하는 모든 QR 코드에 영향을 미칩니다.

**QR 코드를 사용자 지정하는 방법**:

1. 앱스플라이어의 사이드 메뉴에서 **참여** > **원링크 커스텀 링크**를 선택합니다.
2. 편집하고자 하는 템플릿의 **액션** 아이콘에 마우스를 가져가 **QR 코드 사용자 지정**을 클릭합니다.  
   QR 코드 편집기가 열립니다.
3. 로고가 호스팅되는 URL을 입력합니다. 예: https://yourbrand.com/logo.png.  
   로고 요구사항:

   * PNG 또는 JPG 형식
   * 투명한 배경의 정사각형 또는 원형
   * 최소 크기 400 x 400 픽셀
   * 인쇄를 위해 최대 이미지 해상도 사용
4. QR 코드 색상을 설정합니다.
5. **저장** 을 클릭합니다.

</Accordion>

## 특징 및 제약 사항

<div id="key-traits-and-limitations" />

<div id="traits-and-limitations" />

<Accordion title="특징 및 제한 사항">

| 특징 | 비고 |
| --- | --- |
| 에이전시 | 에이전시는 원링크 템플릿과 링크를 생성할 수 없습니다. |
| 원링크 템플릿 추가/편집 | 계정 사용자가 원링크 템플릿을 추가 또는 편집하려면 <Anchor target="_blank" href="/marketers/ko/docs/user-management">권한</Anchor>이 필요합니다. |
| 원링크 템플릿 | 계정당 최대 600개의 원링크 템플릿이 제공됩니다. |
| 데스크톱 | 데스크톱 사용자를 다른 URL로 리디렉션하도록 원링크 URL 또는 템플릿을 설정하면, 매개변수 `af_web_dp`의 링크에 웹 URL이 추가됩니다. 링크에 `af_web_dp`가 포함된 경우, 앱스플라이어는 데스크톱의 클릭을 등록하지 않습니다. |
| 타사 앱 스토어로 리디렉션 | 앱 패키지 이름이 모든 앱 스토어에서 동일한 경우에만 원링크 템플릿에 여러 앱 스토어를 설정할 수 있습니다. 타사 안드로이드 앱 스토어로의 원링크 리디렉션에 대해 자세히 알아보려면 <Anchor target="_blank" href="/marketers/ko/docs/bulletin-onelink-redirection-to-third-party-android-app-stores?query=3rd%20party%20store">여기</Anchor>를 참조하세요.<br /><br />**참고**:<ul><li>Huawei 및 기타 써드 파티 스토어는 경우에 따라 다른 패키지 이름을 요구하는 경우가 있습니다. 이러한 경우 여러 앱 스토어에서 동일한 원링크 템플릿을 사용할 수 없습니다.</li><li>일부 샤오미 기기에는 GetApps 스토어가 탑재되어 있으며, 이 스토어는 구글 플레이와 동일한 URI 스킴을 사용합니다. 이는 앱이 샤오미의 GetApps 스토어에 등록되어 있지 않은 경우에도, 사용자를 구글 플레이가 아닌 GetApps로 리디렉션할 수 있음을 의미합니다.</li><li>패키지 이름은 같지만 채널이 다른 경우 리디렉션은 작동하지만 어트리뷰션은 작동하지 않습니다.</li><li>타사 앱 스토어 어트리뷰션 및 데이터에 대해 <Anchor target="_blank" href="/marketers/ko/docs/set-up-multi-store-android-attribution">자세히 알아보세요</Anchor>.</li></ul> |
| 템플릿 업데이트 | <ul><li>원링크 템플릿의 구성을 변경하면 적용하는 데 최대 1시간이 소요됩니다.</li><li>연결된 앱이 계정에서 삭제된 경우 원링크 템플릿을 편집할 수 없습니다. 이 경우 다음과 같은 조치를 취할 수 있습니다:<ul><li>새 템플릿을 생성하세요.</li><li>삭제된 앱을 복원하려면 담당 앱스플라이어 고객 성공 매니저(CSM)에 연락하거나 hello@appsflyer.com으로 문의해 주세요.</li></ul></li></ul> |
| URI 스킴 | <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#chrome-browser-on-ios">여기</Anchor>를 참조하세요. |

</Accordion>

원링크 템플릿에 대해 궁금한 점이 있으신가요? <Anchor target="_blank" href="/marketers/ko/docs/onelink-troubleshooting-and-faq#원링크-템플릿-faq">자주 묻는 질문(FAQ)</Anchor>을 확인하세요!

<div id="next-step" />

## 다음 단계

지침에 따라 템플릿을 기반으로 <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">원링크 링크를 생성하세요</Anchor>.

<div data-zendesk-anchors="onelink-templates=%EC%9B%90%EB%A7%81%ED%81%AC-%ED%85%9C%ED%94%8C%EB%A6%BF h_01H9Q4E7VQ0GKZ9HFF88190TYN=%EC%9B%90%EB%A7%81%ED%81%AC-%ED%85%9C%ED%94%8C%EB%A6%BF procedures=%EC%9B%90%EB%A7%81%ED%81%AC-%ED%85%9C%ED%94%8C%EB%A6%BF-%EB%A7%8C%EB%93%A4%EA%B8%B0 h_01H9Q4E7VQYGZ1MH5SS3ZYZF1K=%EC%9B%90%EB%A7%81%ED%81%AC-%ED%85%9C%ED%94%8C%EB%A6%BF-%EB%A7%8C%EB%93%A4%EA%B8%B0 h_01H9Q4E7VQ648CQ1VJTB1TC571=create-a-onelink-template-with-redirection-logic-for-new-app-users h_01H9Q4E7VQ15AAR1VXNKWR1XGT=%EC%B0%B8%EA%B3%A0 h_01KYMEP248AG3T4M0MPD6YW5P1=%EC%98%88%EC%8B%9C h_01KYMEP248VHE2TDCD3KXNSV4F=%EC%B0%B8%EA%B3%A0-1 h_01H9Q4E7VQ4NEWYAD6AMR9YKGY=add-redirection-logic-for-existing-app-users h_01H9Q4E7VR8164HR6MD0EAV2SN=%EC%B0%B8%EA%B3%A0-2 h_01H9Q4E7VR0F4B7CTF08YTG715=customize-qr-codes traits-and-limitations::f2d46c64=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD h_01KZX7Q3V7PNRJKKC6PDMABVKQ=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD h_01H9Q4E7VR2B50EQE31DDG8GNZ=traits-and-limitations next-step=%EB%8B%A4%EC%9D%8C-%EB%8B%A8%EA%B3%84 h_01H9Q4E7VRJK31P9CSGJFCKQQF=%EB%8B%A4%EC%9D%8C-%EB%8B%A8%EA%B3%84" />
