---
title: 앱스플라이어에 앱 추가하기
metadata:
  keywords:
    - Add App
    - adding an app
    - Advertisers
    - could not add app
    - security reasons
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2016-01-20T08:57:00Z'
  edited_at: '2026-10-14T10:36:37Z'
  id: 207377436
  locale: ko
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/ko/articles/207377436
---
> **요약:** 앱스플라이어에 앱을 추가하여 인스톨 및 인앱 이벤트에 대한 어트리뷰션 데이터를 얻고, 다양한 도구를 사용하여 데이터를 분석하는 방법을 알아보세요.

## 개요

아직 대시보드에 앱을 추가하지 않았다면, 앱스플라이어에 로그인 시 앱 온보딩 페이지가 표시됩니다. 앱 온보딩은 앱을 추가하고 어트리뷰션 준비를 마칠 수 있도록 모든 단계를 안내합니다.

### 앱 추가 마법사 시작

플랫폼에서 앱 추가 마법사를 사용할 수 있으며, 안드로이드 및 iOS 앱의 경우, 앱 온보딩 페이지를 통해 앱을 추가할 수도 있습니다.

**앱 온보딩 페이지에서 마법사를 시작하려면:**

* **앱 추가** 단계에서 **앱 추가**를 클릭하고, 앱 추가 지침을 따르세요.

> 📘 **참고**
>
> 온보딩 페이지가 아직 열려 있지 않다면, 상단 메뉴 표시줄에서 이메일 주소 드롭다운으로 **앱 온보딩**을 클릭합니다.

![온보딩 페이지.png](https://files.readme.io/8903839c25f12df28e1c4b488699670e2dadca83af9ddfebfc0cf4eacd2ce744-33198275479953.png)

**플랫폼에서 앱 추가 마법사를 시작하려면:**

* 상단 메뉴바에서 **내 앱**을 통해 **+ 앱 추가**를 클릭합니다.
* 앱스플라이어 홈페이지에서 **+ 앱 추가**를 클릭하세요.
* 상단 바에서 계정 메뉴(이메일 주소 드롭다운) >**앱 온보딩**을 열고 **+ 다른 앱 온보딩**을 클릭합니다.

<Image alt="앱 추가(1).png" src="https://files.readme.io/894b7b76c1da76e2308b110266cbffeb579c551033ce302ade182c1d63fd9384-33198275483793.png" width="593px" />

## 앱 추가

[앱 추가 마법사에 들어간 후](#앱-추가-마법사-시작), 다음 단계를 따르세요.

1. [앱 세부정보를 입력하세요](#앱-세부-정보를-입력하세요).
2. [추가 정보를 입력하세요](#추가-정보를-입력하세요웹-앱에는-해당되지-않음).
3. **내 앱 추가**를 클릭하세요.
4. <Anchor target="_blank" href="/marketers/ko/docs/getting-started-onboarding-for-marketers#2단계-sdk--api-연동">SDK 연동</Anchor>에 사용할 개발 키를 복사합니다(나중에 <Anchor target="_blank" href="/marketers/ko/docs/app-settings#일반-앱-설정">앱 설정</Anchor> 페이지에서 다시 얻을 수 있습니다).
5. 더 많은 앱을 추가하려면 **완료** 또는 **+ 다른 앱 추가**를 클릭하세요. 추가적인 앱 추가를 위해 이 과정을 반복하세요.

> 📘 **참고**
>
> * 관리자와 <Anchor target="_blank" href="/marketers/ko/docs/user-management">필요한 권한이 있는 계정 사용자</Anchor>만 앱을 추가할 수 있습니다.
> * 앱 추가 단계를 따르는 동안, 이전에 선택한 옵션에 따라 사용 가능한 옵션이 다를 수 있습니다.

앱을 등록하면 대시보드에 표시됩니다. 인스톨 및 인앱 이벤트를 기록하고 올바른 매체 소스에 할당하려면 다음을 해야 합니다:

* SDK를 연동합니다
* 파트너 마켓플레이스에서 앱을 파트너와 연결하세요

온보딩 프로세스를 완료하기 위한 <Anchor target="_blank" href="/marketers/ko/docs/getting-started-onboarding-for-marketers">모든 단계</Anchor>를 확인하세요.

### 앱 세부 정보를 입력하세요

아래 나열된 대로 앱 플랫폼을 선택하고 필요한 세부 정보를 입력하세요:

<div id="android-androidtv-fire" />

<Accordion title="안드로이드, 안드로이드TV, 파이어">

다음 플랫폼에 대해 이 옵션을 사용하세요:

* 안드로이드 (모바일)
* 안드로이드TV
* 아마존 파이어
* 아마존 파이어 TV
* 킨들

<Table>
  <thead>
    <tr>
      <th>
        구글 플레이 상태
      </th>
      <th>
        사용 시점
      </th>
      <th>
        필요한 세부 정보
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="in-store"></span>
        매장에서
      </td>
      <td>
        귀사의 앱은 현재 구글 플레이 스토어에서 이용 가능합니다.
      </td>
      <td>
        **Google Play URL** (Google Play에서 복사)

        * **예:** https:\/\/play.google.com\/store\/apps\/details?id=com.appsflyer.adNetworkTest **&hl=en&gl=GB**
        * **중요!**
          * 미국 구글 플레이 스토어에 등록된 앱이 **아닌** 경우:
            * URL에는 위의 예와 같이 URL이 등록된 모든 스토어의 국가 코드( **&gl=**)가 포함되어야 합니다. 국가 코드를 포함하지 않으면 앱을 추가하려고 할 때 오류가 발생합니다.
            * 언어 코드는 선택 사항입니다: **&hl=`{language_code}`**
          * 스토어가 미국 구글 플레이 스토어에 등록되어 **있는** 경우 국가 및 언어 코드는 모두 선택 사항입니다.
      </td>
    </tr>
    <tr>
      <td><span id="pending-approval-not-published"></span>
        승인 대기 중\/게시되지 않음
      </td>
      <td>
        앱이 아직 게시되지 않았거나 구글 플레이의 승인 대기 중입니다.
      </td>
      <td>
        **안드로이드 패키지 이름**

        * **예:** com.appsflyer.adNetworkTest
        * **참고:** 일러두기: 패키지 이름은 대소문자를 구분합니다.
        * **형식:**
          * 최소 두 개의 세그먼트(하나 이상의 점)
          * 각 세그먼트는 문자로 시작해야 합니다
          * 모든 문자는 영숫자 또는 밑줄(a-z, A-Z, 0-9 또는 \_)이어야 합니다.
          * 최대 100자까지

        자세한 내용은 <Anchor target="_blank" href="https://developer.android.com/studio/build/application-id">안드로이드 개발자 문서</Anchor>를 참조하십시오.
      </td>
    </tr>
    <tr>
      <td><span id="third-party-store-out-of-store"></span>
        타사 스토어\/스토어 외부
      </td>
      <td>
        앱이 구글 플레이가 아닌 안드로이드 앱 스토어에 있으며/또는 앱 스토어가 아닌 다른 위치에서 다운로드할 수 있습니다.
      </td>
      <td>
        * **안드로이드 패키지 이름** 자세한 요구 사항은 이전 행(승인 보류 중/게시되지 않음)을 참조하십시오.
        * **채널 이름: (선택 사항)** 개별 APK의 AndroidManifest.xml에 설정한 고유한 이름입니다. 예를 들어, Amazon 스토어 APK의 경우 `application` 태그 내에 다음을 추가하십시오. 이름은 대소문자를 구분하며, 앱을 추가할 때 입력한 <Anchor target="_blank" href="/marketers/ko/docs/set-up-multi-store-android-attribution#dashboard-per-store-adding-the-app">채널 이름 필드의 이름과 동일해야 합니다</Anchor>. 더 자세한 정보는 <Anchor target="_blank" href="/marketers/ko/docs/set-up-multi-store-android-attribution#dashboard-per-store-apk-preparation">여기</Anchor>를 참고하십시오.

          ```xml
          <application>
               ...
               <meta-data android:name="CHANNEL" android:value="Amazon"/>
               ...
          </application>
          ```

        * **앱 URL** (타사 앱 스토어 또는 스토어 밖 위치에서 복사)

        > 🚧 **중요!**
        >
        > 앱이 둘 이상의 소스(즉, 구글 플레이, 타사 스토어 또는 스토어 밖 위치의 조합)에서 제공되는 경우 <Anchor target="_blank" href="/marketers/ko/docs/set-up-multi-store-android-attribution">다중 스토어 안드로이드 속성 설정</Anchor> 옵션을 고려하는 것이 중요합니다. 처음부터 제대로 구현하면 필요한 데이터에 필요한 형식으로 액세스할 수 있습니다.
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="ios-tvos-macos" />

<Accordion title="iOS, tvOS, MacOS">

다음 플랫폼에 대해 이 옵션을 사용하세요:

* iOS
* tvOS
* MacOS

| 애플 앱 스토어에서의 상태 | 사용 시점 | 필요한 세부 정보 |
| --- | --- | --- |
| <span id="in-store::f93cfa22"></span>매장에서 | 귀사의 앱은 현재 애플 앱 스토어에서 이용 가능합니다. | **App Store URL**(앱 스토어에서 복사함)<ul><li>**예시:** https:\/\/apps.apple.com\/**us**\/app\/partner-integrations\/id1543229303</li><li>**주석:**<ul><li>URL에 스토어 국가의 2문자 코드(예: 위 URL에서 **US**)가 포함되어 있는지 확인하십시오.</li><li>2019년 6월 14일 이전에 앱 스토어에 추가된 앱은 URL에 itunes.apple.com을 포함할 수 있습니다(apps.apple.com 대신).</li></ul></li></ul> |
| <span id="pending-approvalnot-published"></span>승인 대기 중\/게시되지 않음 | 앱이 아직 게시되지 않았거나 앱스토어에서 승인 대기 중입니다. | 앱이 제출된 앱 스토어의 **국가**<br /><br />앱 스토어에서 할당한 **앱 ID**, 접두사 id 없음<ul><li>**예시:** 1543229303</li><li>**형식:** 9 또는 10자리 숫자, 0-9</li></ul> |

</Accordion>

<div id="windows-xbox" />

<Accordion title="윈도우">

다음 플랫폼에 대해 이 옵션을 사용하세요:

* 윈도우 폰
* 윈도우(데스크톱)

| Microsoft Store 상태 | 사용 시점 | 필요한 세부 정보 |
| --- | --- | --- |
| 매장에서 | 귀사의 앱은 현재 Microsoft Store에서 이용 가능합니다. | **Microsoft Store URL** (Microsoft Store에서 복사)<ul><li>**예:** https:\/\/www.microsoft.com\/en-us\/p\/wordament\/9wzdncrfhwfg</li><li>**참고:** 참고: 위의 URL은 Windows Phone 앱의 예입니다. URL 형식은 Windows 데스크톱 앱에 따라 다릅니다.</li></ul>**앱 ID:** 최대 150자까지 입력 가능합니다. |
| 승인 대기 중\/게시되지 않음 | 앱이 아직 게시되지 않았거나 스토어에서 승인 대기 중입니다. | Microsoft Store에서 할당한 **앱 ID**<ul><li>**최대 길이:** 150자</li><li>**예시:** 9wzdncrfhwfg</li><li>**참고: 앱 ID는 대소문자를 구분합니다.**</li></ul> |

</Accordion>

<div id="web-pba" />

<Accordion title="웹(PBA)">

> 📘 **참고**
>
> 웹 앱은 PBA(유저 중심 어트리뷰션) 기능을 위해 브랜드 번들에 포함할 웹사이트를 정의하는 곳입니다.
>
> * 이 옵션은 PBA를 구독한 고객만 사용할 수 있습니다.
> * 채널, 플랫폼 및 디바이스에 걸친 고객 이동 경로를 통합적으로 파악하기 위해 PBA와 웹 방문 어트리뷰션, 엡 이벤트 및 웹사이트 지원 인스톨에 대해 <Anchor target="_blank" href="/marketers/ko/docs/people-based-attribution-pba-overview">자세히 알아보십시오</Anchor>.

**전체 URL:** 전체 URL: 트래픽을 측정할 웹 사이트의 전체 URL입니다. 이 웹사이트는 <Anchor target="_blank" href="/marketers/ko/docs/onboarding-guide-to-people-based-attribution#2">PBA Web SDK</Anchor>를 구현한(또는 구현하려는) 웹사이트입니다.

[altURL 다이어그램alt](https://files.readme.io/45c6e433af693fd8c293380192a8e60f26c82588195bab61bafbc9839baf5c7b-33198323426961.png)

– 포함

* 스킴
* 서브도메인 [선택사항]
* 도메인 이름
* 최상위 도메인
* path [선택 사항] – 웹 사이트의 특정 디렉토리 또는 페이지 주소

**앱 이름:** 귀사가 선택한 앱 이름입니다.

* 최대 길이: 100자
* XSS 태그는 허용되지 않습니다.

> 🚧 **중요!**
>
> 웹 앱을 만든 후에는 삭제했다가 다시 만들지 않으면 해당 속성(URL 및 앱 이름)을 편집할 수 없습니다. 즉, **웹 앱이 속한 <Anchor target="_blank" href="/marketers/ko/docs/pba-brand-bundles-and-settings#what-happens-if-i-delete-a-bundle">브랜드 번들도 삭제</Anchor>해야 합니다.**

**다음 단계:**

* 새로 만든 웹 앱을 <Anchor target="_blank" href="/marketers/ko/docs/pba-brand-bundles-and-settings">PBA 브랜드 번들</Anchor>에 추가하여 PBA 대시보드에 표시되도록 합니다.
  * 브랜드 번들에 포함하려는 모든 모바일 앱이 번들 생성 전에 계정에 추가되었는지 확인하십시오.
* 측정 데이터 흐름을 가져오려면 <Anchor target="_blank" href="/marketers/ko/docs/pba-web-sdk-integration-guide">PBA 웹 SDK를 웹 앱에서 지정한 웹사이트에 연동</Anchor>하십시오.

</Accordion>

<div id="web" />

<Accordion title="웹">

웹 플랫폼을 사용하여 새로운 웹 앱을 만들고 웹 방문 및 전환을 웹 귀속을 사용하여 측정하십시오.

#### **시작하기 전에**

* 구형 사람 기반 귀속(PBA) 웹 앱은 “**웹 (PBA)”** 로 표시됩니다.
* 구형 PBA 웹 앱에서 마이그레이션하는 경우 기존 PBA 웹 개발 키를 사용할 수 있습니다.

#### **웹 앱 추가**

1. **내 앱** > **앱 추가**로 이동하십시오.
2. **웹사이트**를 선택하십시오.
3. 다음 정보를 입력하십시오:

앱 이름 귀사가 선택한 앱 이름입니다.

* **길이:** 50자.
* **허용된 문자:** 문자(모든 언어), 숫자, 공백(시작 또는 끝에 없음), 및 특수 문자: . - \_ :
* **차단된 문자:** ; \`{ }\` $ &lt; > \` \

**예시:** 내 온라인 상점, 기업 웹사이트 2024, 전자상거래\_생산

**기본 도메인 (전체 URL)**: 귀하의 웹사이트의 기본 도메인입니다. 이는 웹 앱 생성 중에 설정되며 이후에는 변경할 수 없습니다.

* **형식:** 유효한 도메인 이름만 (프로토콜, 경로 또는 포트 없음)
* **길이:** 최소 3자 이상
* 처리중 AppsFlyer가 자동으로
  * http:// 또는 https://를 제거합니다.
  * 후행 슬래시를 제거합니다.
  * 도메인을 소문자로 변환합니다.
* **불변성:** 앱 생성 후에는 편집할 수 없습니다.

**[앱스플라이어] 중요:** 기본 도메인을 변경하려면 웹 앱을 삭제하고 다시 생성해야 하며, 이로 인해 역사적 데이터 연속성이 손실됩니다.

**예시:**

* https://shop.example.com/checkout → shop.example.com로 저장됨 → 앱 ID: website-shop.example.com
* example.com/ → example.com로 저장됨 → 앱 ID: [website-example.com](http://website-example.com)

앱 ID AppsFlyer가 기본 도메인을 기반으로 웹 앱에 대해 생성하는 고유 ID입니다.

* 형식: website-`<primary_domain>`를 사용하여 자동으로 생성됩니다.
* 예: website-shop.example.com

웹 SDK ID 웹 SDK에서 귀속을 위해 사용하는 식별자 (이전에는 web\_dev\_key로 명명됨).

앱 생성 시 두 가지 옵션:

옵션 3 새로 생성(기본값)

* 새로운 웹 SDK ID를 자동으로 생성합니다.
* 형식: website-`{yourdomain.com}`
* 예: website-shop.example.com
* 사용 사례 새로운 웹 귀속 구현

옵션 3 기존 PBA 개발 키 재사용

* 기존 PBA(사람 기반 귀속) 웹 앱 개발 키의 드롭다운에서 선택합니다.
* 웹사이트 코드를 변경하지 않고 원활한 마이그레이션을 가능하게 합니다.
* 사용 사례 구형 PBA에서 새로운 웹 귀속 솔루션으로 마이그레이션 중입니다.

**참고:** PBA 개발 키를 재사용하면 웹사이트 구현을 변경하지 않고 PBA에서 새로운 웹 앱으로 마이그레이션할 수 있습니다.

각 PBA 개발 키는 **하나**의 웹 앱에만 할당될 수 있습니다. PBA 개발 키가 웹 앱에 사용되면 다른 웹 앱에서는 더 이상 사용할 수 없습니다.

* **길이:** 50자.
* **불변성:** 앱 생성 후에는 변경할 수 없습니다.
* **PBA 마이그레이션:** 계정의 PBA 웹 앱에서만 개발 키가 드롭다운에 표시됩니다.

**통화**: 앱 보고에 사용되는 통화입니다.

* 표준 ISO 4217 통화 코드(예: USD, EUR, GBP, ILS)
* 드롭다운에서 선택됨.
* 필수 필드

**시간대**: 앱 보고에 사용되는 시간대입니다.

* IANA 시간대 형식(예: America/New\_York, Europe/London, Asia/Tokyo)
* 드롭다운에서 선택됨.
* 필수 필드

4. **앱 만들기**를 클릭하십시오.

**제한 사항**

* 앱이 생성된 후에는 **기본 도메인을 변경할 수 없습니다**.
* 기본 도메인은 자동으로 **제외된 도메인**에 유형 **기본**으로 추가됩니다.

각 구형 **웹 개발 키는 하나의** 새로운 웹 앱에만 재사용할 수 있습니다.

> 📘 **참고**
>
> 웹 귀속 설정에 대한 전체 정보는 <Anchor target="_blank" href="/marketers/ko/docs/configure-web-performance-measurement-settings">여기를 참조하십시오</Anchor>.

</Accordion>

<div id="roku" />

<Accordion title="로쿠">

**앱 이름: 앱 이름 -** Roku 개발자 대시보드/strong>에서 복사.

* **예시:** 내 Roku 채널
* **형식:**
  * 최대 100자까지
  * XSS 태그는 허용되지 않습니다.

**채널 ID: 채널에 할당된 숫자 ID**

* **형식:**
  * 숫자 (0-9)
  * 최대 길이: 50자
* **어떻게 찾을 수 있나요?**
  * <Anchor target="_blank" href="https://developer.roku.com/developer">Roku 개발자 대시보드</Anchor>에서 앱스플라이어에 추가하는 채널의 이름을 클릭합니다. 채널에 대한 Roku 미리보기 및 게시 페이지가 열립니다.
  * URL 페이지 끝에 있는 숫자가 채널

    ![](https://files.readme.io/89f6513eee03558a9dc8e465fe67953780074477fc0fe20675b721d8116671af-33198275490577.png)

</Accordion>

<div id="amazon-vega-os" />

<Accordion title="Amazon Vega OS">

**앱 이름: 귀사가 선택한 앱 이름입니다.**

앱 ID: 앱의 ID. 역 DNS 표기법을 사용하여 찾음: `<tld>`.`<company_name>`.`<app_name>`  
최소 2개의 세그먼트를 포함해야 합니다. 각 세그먼트는 문자로 시작하고 다음 문자에서 이어져야 합니다: `A-Z` `a-z` `0-9.` `-`  

예: com.company.myapp

자세한 내용은 <Anchor target="_blank" href="https://developer.amazon.com/docs/vega/0.21/manifest-package.html#fields">Amazon Vega OS 문서</Anchor>의 "id" 필드를 참조하십시오.

</Accordion>

<div id="vizio-smartcast" />

<Accordion title="Vizio SmartCast">

**앱 이름: 귀사가 선택한 앱 이름입니다.**

**앱 ID: 앱 ID는 다음과 같이 인식됩니다 `vz`로 시작하고, `A-Z` `a-z` `0-9.` `-`에서 2-20자의 문자가 뒤따릅니다. 앱 ID를 확인해야 하는 경우 Vizio 담당자에게 확인하십시오.**

</Accordion>

<div id="samsung-tizen" />

<Accordion title="삼성 타이젠">

**앱 이름:** 귀사가 선택한 앱 이름입니다.

**앱 ID:** 앱 ID: Samsung에서 앱에 할당한 번들 ID입니다. `G`로 시작하고, 8-15자리 숫자가 뒤따릅니다. 앱 ID를 얻으려면:

1. 삼성 TV 판매 사무소에 로그인하십시오.

   1. 여기에서 <Anchor target="_blank" href="https://developer.samsung.com/tv-seller-office/guides/applications/entering-application-information.html%20">인앱 광고 정보</Anchor> 아래의 가이드를 참조하십시오.
2. 개발자 URL을 입력하십시오.
3. 귀하의 번들 ID는 자동으로 생성되어 표시됩니다. 이것은 앱 스토어 URL에 접근하는 데 사용될 수 있습니다.
4. 앱-ads.txt 검증을 지원하기 위해 광고 태그나 입찰 요청에 귀하의 번들 ID와 앱 스토어 URL을 사용하십시오.
5. 문제가 발생하면 판매 사무소에서 문제 보드 티켓을 열어주십시오.

참고: 고유한 앱 스토어 웹 페이지에 접근하려면 번들 ID를 URL "[https://www.samsung.com/us/appstore/app/](https://www.samsung.com/us/appstore/app/)"에 추가하십시오.

예를 들어, 귀하의 번들 ID가 "G15147002586"인 경우, 귀하의 페이지 URL은 "[https://www.samsung.com/us/appstore/app/G15147002586/](https://www.samsung.com/us/appstore/app/G15147002586/) "입니다. 개발자 URL, 번들 ID 및 앱 스토어 ID는 해당 페이지의 메타데이터에 표시됩니다.

![](https://files.readme.io/ee4b192abab24e064013a4a034bda38fb3ed49497ae333e327e1b78dd05d5349-33198275491729.png)

</Accordion>

<div id="lg-webos" />

<Accordion title="LG WebOS">

**앱 이름:** 귀사가 선택한 앱 이름입니다.

**앱 ID:** LG WebOS 앱 ID.

* **형식:**
  * 최대 길이 50자
  * 번들 형식으로 `A-Z` `a-z._`의 문자입니다. 반드시 문자로 시작해야 합니다.
* **예시:** com.my-company.app

앱 ID를 확인해야 하는 경우 LG WebOS 담당자에게 문의하세요.

</Accordion>

<div id="playstation" />

<Accordion title="플레이스테이션">

**앱 이름:** 귀사가 선택한 앱 이름입니다.

**앱 ID:** 앱 ID: 게임 또는 기타 콘텐츠 개념에 할당된 고유 식별자인 PlayStation 개념 ID, PlayStation 스토어 URL에 5&#126;9자리 숫자로 표시됩니다. 앱의 앱 스토어 URL 끝에서 찾을 수 있습니다.

![playstation_app_id_url.png](https://files.readme.io/df92705244e55e7adc44a88076556609983ec3dff89c03df77e19f0f1a061bbb-33198323434513.png)

</Accordion>

<div id="vidaa" />

<Accordion title="비다">

**앱 이름:** 귀사가 선택한 앱 이름입니다.

**앱 ID:** Vidaa 앱 ID. 최대 150자까지 입력 가능합니다.

</Accordion>

<div id="steam" />

<Accordion title="Steam">

**앱 이름:** 귀사가 선택한 앱 이름입니다.

**앱 ID:** Steam 앱 ID. 이것은 Steam 스토어 URL에 표시되는 5&#126;8자리 숫자입니다.

![steam_store_app_url.png](https://files.readme.io/4976c0323eab0c08b61d4a1a7a75ebf7ea9fcd819176ff574421f0de4d8c614c-33198275497617.png)

</Accordion>

<div id="meta-quest" />

<Accordion title="Meta Quest (Oculus)">

**앱 이름:** 귀사가 선택한 앱 이름입니다.

**앱 ID:** 메타 퀘스트 앱 ID는 앱이 다운로드된 메타 앱 스토어 URL의 끝에 나타나는 것입니다. `A-Z` `A-Z`에서 3-50자의 문자를 포함합니다.

<Image alt="" src="https://files.readme.io/1938b3f89b866ebdd3452367d7410c423ce57372544a801ca3d1b409f3bff541-33198323442449.png" width="397px" />

</Accordion>

<div id="nintendo-switch" />

<Accordion title="닌텐도 스위치">

**앱 이름:** 귀사가 선택한 앱 이름입니다.

**앱 ID:** 닌텐도 스위치 앱 ID는 앱이 다운로드된 스토어의 URL 끝에 나타나는 것입니다. 14자리 숫자로 구성됩니다.

* **예시:** 70010000012345

</Accordion>

<div id="xbox" />

<Accordion title="엑스박스">

**앱 이름:** 귀사가 선택한 앱 이름입니다.

**앱 ID:** 엑스박스 앱 ID는 앱이 다운로드된 엑스박스 스토어 URL의 끝에 나타나는 것입니다. 12자의 문자와 숫자만 포함됩니다 (`A-Z` `a-z0-9`).

![](https://files.readme.io/c33ffcb35d4488b9340cfa8b475097eab7b79bfeaf94e8cf8ce6478dda07d341-33198275505041.png)

**참고:** 앱 ID는 대소문자를 구분합니다.

</Accordion>

<div id="epic-games" />

<Accordion title="에픽 게임즈">

**앱 이름:** 귀사가 선택한 앱 이름입니다.

**앱 ID:** 앱 ID: Epic Games 앱 ID(앱이 다운로드된 스토어에 표시됨) `a-z0-9._-` `A-Z``a-z0-9._-`에서 3-50자의 문자를 포함합니다.

![](https://files.readme.io/81d1f043c8a7ef5e367a62d564f8c6241c6057445363b21286e3f72ad4210cf6-33198275508497.png)

</Accordion>

<div id="native-pc" />

<Accordion title="네이티브 PC">

**앱 이름:** 귀사가 선택한 앱 이름입니다.

**앱 ID:** 네이티브 PC 앱 ID입니다. `a-z0-9._-` `A-Z``a-z0-9._-`에서 3-50자의 문자를 포함합니다.

</Accordion>

### 추가 정보를 입력하세요(웹 앱에는 해당되지 않음):

<Image alt="" src="https://files.readme.io/561aea51bbfaa733721040706cac2b9520e35cfe71027fa34d08ed7890baf00c-33198323448081.png" width="559px" />

#### **통화 선택**

대시보드에 표시될 앱의 데이터 통화를 선택하세요. 수익 및 지출 이벤트는 이벤트 시점의 환율을 사용하여 이 통화로 변환됩니다. <Anchor target="_blank" href="/marketers/ko/docs/app-settings#localization-currency">더 보기</Anchor>: 앱의 통화 설정과 그 영향에 대해

> 🚧 **중요!**
>
> 앱에 사용할 통화를 선택할 때 주의하세요. 비용과 수익이 기록되면 변경이 불가능합니다.

#### **시간대 선택**

여기서 선택한 시간대를 다른 어트리뷰션 파트너(예: Meta Ads 및 Google Ads)에서 설정한 시간대와 맞춥니다. 이를 통해 앱스플라이어 대시보드에 보고된 데이터와 해당 파트너에서 수신한 데이터 간의 일치도를 최대로 높일 수 있습니다.

> 📘 **참고**
>
> * 시간대가 설정되면 잠금 상태가 유지되어 다음 날까지 변경할 수 없습니다.
> * 앱 시간대 설정과 그 영향에 대해 <Anchor target="_blank" href="/marketers/ko/docs/changing-app-time-zone-settings">더 보기</Anchor>.

#### **앱 오디언스 정의**

귀사의 앱이 어린이 또는 혼합 오디언스(어린이와 성인 모두)를 대상으로 하는지 여부를 표시하려면 **예** 또는 **아니요**를 선택하세요.  
**예**를 선택한 경우:

1. 아동 대상 앱의 준수 구현에 대한 <Anchor target="_blank" href="https://www.appsflyer.com/gatedpdfs/KidsAppsComplianceGuide_03_22.pdf">가이드</Anchor>를 열어 읽어보세요.
2. 가이드를 읽었고 명시된 제어를 구현했음을 확인하려면 상자를 선택하세요.

> 📘 **참고**
>
> * 앱을 추가한 후 2주 후에, 아동 대상 앱의 개인정보 보호 설정을 완료했는지 확인하는 알림을 받게 됩니다. 확인 후 확인 메시지를 받게 됩니다. 알림 센터에서 언제든지 확인 메시지에 액세스할 수 있으며, <Anchor target="_blank" href="/marketers/ko/docs/audit-log">감사 로그</Anchor>에서 확인 세부 정보를 볼 수 있습니다.
> * <Anchor target="_blank" href="/marketers/ko/docs/child-directed-apps-faq">아동 대상 앱에 관한 자주 묻는 질문</Anchor>을 참조하세요.

#### API를 통해 귀사의 앱을 대량으로 관리하세요

계정 관리자는 UI의 주요 기능을 지원하는 전용 API를 사용하여 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/app-management-v2-overview">여러 앱을 대량으로 관리</Anchor>할 수 있습니다. 여기에는 앱 추가 및 삭제, 앱 설정 업데이트가 포함됩니다. API는 동일한 오류 검증 메커니즘도 포함하고 있습니다.

> 📘 **참고**
>
> 이 단계에서는 API를 통해 앱을 추가하고 앱 설정을 업데이트하는 것이 모바일 앱에서만 가능합니다. 모든 플랫폼에서 앱을 삭제할 수 있습니다.

### 디버그 또는 테스트 앱을 추가하십시오.

개발자가 **디버그**, **샌드박스** 또는 **테스트 앱**을 생성하는 경우, 해당 앱을 대시보드에 추가해야 합니다. 개발자가 앱으로 테스트를 시작하면, 데이터가 앱의 대시보드에 표시됩니다.

> 📘 **참고**
>
> 앱 스토어에 게시되지 않았고 유효한 앱 스토어 ID가 없는 iOS 앱의 경우, **더미 iOS 앱 스토어 ID**를 사용하여 SDK 테스트를 계속 진행할 수 있습니다. 이것은 실제 앱 스토어 목록이 필요 없이 SDK 통합 및 테스트를 가능하게 합니다.

디버그 앱을 생성하고 대시보드에 추가하는 방법에 대한 개발자 지침은 다음을 참조하십시오:

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/testing-android#creating-an-android-debug-app">안드로이드 지침</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/testing-ios#creating-an-ios-debug-app">iOS 지침</Anchor>

## 보류 중인 앱에 대하여

보류 상태의 앱은 앱스플라이어 SDK를 시험하거나 디버깅할 때 유용할 수 있습니다.

대시보드에서 앱 상태가 보류 중으로 표시되어도 데이터 수집 및 측정에는 영향을 미치지 않습니다. 앱이 앱 스토어에 보류 중이든 출시 중이든, 사용자가 앱을 인스톨 하고 상호작용하면 인스톨 및 인앱 이벤트 데이터는 대시보드에 동일하게 기록됩니다.

귀사의 보류 중인 앱이 공개되면 앱스플라이어가 해당 앱의 상태를 감지하고 자동으로 업데이트하므로, 앱을 다시 추가할 필요가 없습니다. 보류 중인 앱과 관련된 정보 및 상태를 수동으로 새로 고치는 절차에 대해 <Anchor target="_blank" href="/marketers/ko/docs/why-is-my-app-still-pending">더 보기</Anchor>.

## 문제 해결

일반적인 문제에 대한 해결책을 찾아보세요.

<div id="app-wasnt-added" />

<Accordion title="앱이 추가되지 않았습니다">

이 오류가 발생하면 귀사의 CSM에 문의하거나 [hello@appsflyer.com](mailto:hello@appsflyer.com)으로 이메일을 발송하세요.

</Accordion>

<div id="app-not-in-the-store" />

<Accordion title="앱이 앱 스토어에 없습니다">

적절한 앱 이름/ID를 사용하여 스토어 URL을 올바르게 복사했는지 확인하세요.

</Accordion>

<div id="cant-access-marketplace" />

<Accordion title="마켓플레이스에 액세스할 수 없습니다.">

이 오류는 비미국 스토어에서 안드로이드 앱을 추가할 때 가끔 발생합니다. 이 문제를 해결하려면 다음 단계를 따르세요.

1. 위에 설명한 대로 **승인 대기/게시되지 않음** 상태로 앱을 추가합니다.
2. 앱스플라이어 **앱 설정** 페이지로 이동합니다.
3. **앱 스토어 국가**를 올바른 국가로 변경하세요(예: 일본).

</Accordion>

<div id="something-went-wrong" />

<Accordion title="문제가 발생했습니다. 다시 시도해 보세요.">

이 오류가 발생할 수 있는 이유 중 하나는 미국 구글 플레이 스토어에 나열되지 **않은** 앱을 국가 코드 없이 추가하려고 하기 때문입니다. 이 문제를 해결하기 위한 자세한 내용은 [위에서](/docs/adding-an-app-to-appsflyer#in-store) 확인하세요.

</Accordion>

<div id="my-ios-app" />

<Accordion title="내 iOS 앱이 App Store에서 제거되었습니다. 왜 아직도 설치가 보이나요?">

이것은 사용자가 이전에 장치에 존재했던 앱을 운영 체제를 통해 다시 설치할 수 있기 때문에 발생합니다. 앱이 더 이상 App Store에서 제공되지 않더라도, 사용자는 여전히 설치할 수 있으며, 이러한 설치는 AppsFlyer에 기록됩니다.

</Accordion>

## 기타 정보

<div id="product-line" />

<Accordion title="제품 라인">

제품 라인에서 앱을 추가하거나 제거할 수 있습니다. 제품 라인 및 제공하는 내용에 대한 자세한 정보는 <Anchor target="_blank" href="/marketers/ko/docs/product-line-group-apps-for-cross-platform-attribution">여기를 참조하십시오</Anchor>.

</Accordion>

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 01H8Y09SSKZS2RHM35JT16ESKM=%EA%B0%9C%EC%9A%94 entering-the-wizard-for-adding-an-app=%EC%95%B1-%EC%B6%94%EA%B0%80-%EB%A7%88%EB%B2%95%EC%82%AC-%EC%8B%9C%EC%9E%91 01H8Y0K9EHWH05DB5K02ASJG11=%EC%95%B1-%EC%B6%94%EA%B0%80-%EB%A7%88%EB%B2%95%EC%82%AC-%EC%8B%9C%EC%9E%91 01H8F2TENNWXADKVZFHY9SE8JC=%EC%B0%B8%EA%B3%A0 adding-an-app=%EC%95%B1-%EC%B6%94%EA%B0%80 01H8ECFB7V0DCNE0ZKPZ2GCVMP=%EC%95%B1-%EC%B6%94%EA%B0%80 01H81661SR41SQFZZ0AW6K2EDM=%EC%B0%B8%EA%B3%A0-1 enter-app-details=%EC%95%B1-%EC%84%B8%EB%B6%80-%EC%A0%95%EB%B3%B4%EB%A5%BC-%EC%9E%85%EB%A0%A5%ED%95%98%EC%84%B8%EC%9A%94 01H815FE64VZZS9WGJSC8VY74D=%EC%95%B1-%EC%84%B8%EB%B6%80-%EC%A0%95%EB%B3%B4%EB%A5%BC-%EC%9E%85%EB%A0%A5%ED%95%98%EC%84%B8%EC%9A%94 01H815FE64CXEHWTV40NVYQHGJ=android-androidtv-fire 01H815FE641Q6N5JY5846QE59Y=%EC%A4%91%EC%9A%94 01H815FE64X0SPA71TBQ9T4ZVB=ios-tvos-macos 01H815FE64ZZA2N1XQFBRXVF41=windows-xbox 01H815FE64XZKDJW1CX5R1JE1T=web-pba 01H815FE646GWA7KJ83KTGHH05=%EC%B0%B8%EA%B3%A0-2 01H815FE65R1Z06TJR0DNC8PFY=%EC%A4%91%EC%9A%94-1 h_01KGEPG8V7ZZ6V2EYYPES0QM77=web before-you-begin=%EC%8B%9C%EC%9E%91%ED%95%98%EA%B8%B0-%EC%A0%84%EC%97%90 h_01KGPM33BA6AJSX32CTN808AXM=%EC%8B%9C%EC%9E%91%ED%95%98%EA%B8%B0-%EC%A0%84%EC%97%90 to-add-a-web-app=%EC%9B%B9-%EC%95%B1-%EC%B6%94%EA%B0%80 h_01KGPM3GTYJJ0ARD3R1XHVAQ8F=%EC%9B%B9-%EC%95%B1-%EC%B6%94%EA%B0%80 h_01KGPM5TTNSECSWEAQY5VH7DTY=%EC%B0%B8%EA%B3%A0-3 01H815FE65X37H40AN99EZJ940=roku h_01KDJP1G4QZHAKH13M5D3CD793=amazon-vega-os 01H815FE654W6D4FCANR1DET8A=vizio-smartcast 01H815FE65J6T610QQXWJS0CJS=samsung-tizen 01H815FE65CRW81AD1006KHGV4=lg-webos 01H815FE65ESQZ56C8B4HG9P8M=playstation 01H815FE65483DV8MD4STH3QTR=vidaa 01H815FE655PZS1H9YW95X1R53=steam 01H815FE655XP075WYRVVFKD4F=meta-quest 01H815FE65XJEVHNT45SHGWJS4=nintendo-switch 01H815FE6598PD87PNBE7MFEQ8=xbox 01H815FE658WJCB1ZCPGAD4GGS=epic-games 01H815FE652P3HCWY2PEDJJARM=native-pc enter-additional-information-not-applicable-to-web-apps=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4%EB%A5%BC-%EC%9E%85%EB%A0%A5%ED%95%98%EC%84%B8%EC%9A%94%EC%9B%B9-%EC%95%B1%EC%97%90%EB%8A%94-%ED%95%B4%EB%8B%B9%EB%90%98%EC%A7%80-%EC%95%8A%EC%9D%8C 01H815FE65AWE8VKV9FYJ7N8MV=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4%EB%A5%BC-%EC%9E%85%EB%A0%A5%ED%95%98%EC%84%B8%EC%9A%94%EC%9B%B9-%EC%95%B1%EC%97%90%EB%8A%94-%ED%95%B4%EB%8B%B9%EB%90%98%EC%A7%80-%EC%95%8A%EC%9D%8C select-currency=%ED%86%B5%ED%99%94-%EC%84%A0%ED%83%9D h_01HHCFD94K6PGQRED6Z6KXKRQF=%ED%86%B5%ED%99%94-%EC%84%A0%ED%83%9D 01H815FE65X7BCFKH1EEFA91GQ=%EC%A4%91%EC%9A%94-2 select-timezone=%EC%8B%9C%EA%B0%84%EB%8C%80-%EC%84%A0%ED%83%9D h_01HHCFDE25S92GZ9TPGQW4PXHV=%EC%8B%9C%EA%B0%84%EB%8C%80-%EC%84%A0%ED%83%9D h_01HMNSSBP2EFXCVW290MKW1EFV=%EC%B0%B8%EA%B3%A0-4 define-app-audience=%EC%95%B1-%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%EC%A0%95%EC%9D%98 h_01HHCFDRNFDERZZV3TT8BVXMB4=%EC%95%B1-%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%EC%A0%95%EC%9D%98 h_01H9MYF17VNBETQ0HS745EJ85H=%EC%B0%B8%EA%B3%A0-5 manage-your-apps-in-bulk-via-api=api%EB%A5%BC-%ED%86%B5%ED%95%B4-%EA%B7%80%EC%82%AC%EC%9D%98-%EC%95%B1%EC%9D%84-%EB%8C%80%EB%9F%89%EC%9C%BC%EB%A1%9C-%EA%B4%80%EB%A6%AC%ED%95%98%EC%84%B8%EC%9A%94 h_01HR3Z81NXCAZKK26HWCN5VD9D=api%EB%A5%BC-%ED%86%B5%ED%95%B4-%EA%B7%80%EC%82%AC%EC%9D%98-%EC%95%B1%EC%9D%84-%EB%8C%80%EB%9F%89%EC%9C%BC%EB%A1%9C-%EA%B4%80%EB%A6%AC%ED%95%98%EC%84%B8%EC%9A%94 h_01HR3ZJW7YD4B8WV0NW9MX6EVP=%EC%B0%B8%EA%B3%A0-6 add-debug-or-testing-app=%EB%94%94%EB%B2%84%EA%B7%B8-%EB%98%90%EB%8A%94-%ED%85%8C%EC%8A%A4%ED%8A%B8-%EC%95%B1%EC%9D%84-%EC%B6%94%EA%B0%80%ED%95%98%EC%8B%AD%EC%8B%9C%EC%98%A4 h_01K2F8JX66F614HF8D5MWQ26P7=%EB%94%94%EB%B2%84%EA%B7%B8-%EB%98%90%EB%8A%94-%ED%85%8C%EC%8A%A4%ED%8A%B8-%EC%95%B1%EC%9D%84-%EC%B6%94%EA%B0%80%ED%95%98%EC%8B%AD%EC%8B%9C%EC%98%A4 ios-dummy-app-id-note=%EC%B0%B8%EA%B3%A0-7 h_01K2F8JX662XEY0A47DZG6DHWQ=%EC%B0%B8%EA%B3%A0-7 about-pending-apps=%EB%B3%B4%EB%A5%98-%EC%A4%91%EC%9D%B8-%EC%95%B1%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC 01H815FE65MYPABC3DTVEMA8E9=%EB%B3%B4%EB%A5%98-%EC%A4%91%EC%9D%B8-%EC%95%B1%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC troubleshooting=%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0 01H815FE655HS8EA4R00D0VCYD=%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0 01H815FE65V2GYP0Q612512DE0=app-wasnt-added 01H815FE65A0HPTVVCT42QQA6M=app-not-in-the-store 01H815FE65EN3PBSH5BKRGNNXD=cant-access-marketplace 01H815FE65FR4ATDA4CVX2FW9N=something-went-wrong h_01JNK9HB2ZWQ78XK9B33QWHV49=my-ios-app other-information=%EA%B8%B0%ED%83%80-%EC%A0%95%EB%B3%B4 h_01K7KSRWCB1Y89T21JFJR42VAJ=%EA%B8%B0%ED%83%80-%EC%A0%95%EB%B3%B4 h_01K7KSPDSSG8CRCQB5V545Y12Z=product-line" />
