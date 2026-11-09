---
title: 원링크 문제 해결 및 FAQ
metadata:
  keywords:
    - faq
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2020-10-27T11:26:30Z'
  edited_at: '2026-10-14T10:26:00Z'
  id: 360014821438
  locale: ko
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/ko/articles/360014821438
---
> **한눈에 보기:** 원링크 사용자정의 링크 리디렉선/동작 이슈를 테스트하고 디버깅하는 간단한 해결 방식을 안내해 드립니다.

<div id="onelink-troubleshooting-guide" />

## 원링크 문제 해결 가이드

<div id="onelink-frequently-asked-questions" />

## 원링크 FAQ

<div id="onelink-template-faq" />

### 원링크 템플릿 FAQ

<div id="which-method-should-i-use-for-opening-apps-universal-links-app-links-or-uri-schemes" />

<Accordion title="앱을 열려면 유니버설 링크, 앱 링크 또는 URI 스키마 중 어떤 방법을 사용해야 합니까?">

**Universal Links:** iOS 사용자의 98% 이상에게 필요

**App Links:** 안드로이드 버전 6.0 이상 사용자용 **참고**: 삼성 OS는 안드로이드 앱 링크를 사용하여 앱을 실행할 수 없습니다.

<div id="note" />

> 📘 **참고**
>
> 유니버설 링크와 앱 링크는 모두 클릭한 URL(즉, 원링크 사용자정의 링크 도메인 또는 브랜드 도메인)의 도메인이 열려는 특정 앱과 연결되어 있다는 증거가 필요합니다. 이 도메인 연결은 iOS용 **Apple 앱 사이트 연결 파일(AASA)** 및 안드로이드용 **Assetlinks** 파일을 통해 수행됩니다.
>
> 이런 파일들은 앱스플라이어 또는 웹 사이트의 광고주가 호스팅합니다. 기본 설정으로 원링크 템플릿을 작성하고 유니버설 링크 및 앱 링크를 설정할 때 이러한 파일은 앱스플라이어에서 생성 및 호스트됩니다.

**URI 스킴:** 삼성 기기에서 앱을 여는 열기 위한 기본 방법. 그렇지 않으면 이는 앱을 여는 레거시 및 폴백 방법입니다. 사용 분야:

* 6.0 이전 버전을 사용하는 안드로이드 사용자(안드로이드 사용자의 15% 미만)에게 사용
* 유니버설 링크와 앱 링크가 작동하지 않거나 설정되지 않았기 때문에 유니버설 링크와 앱 링크가 앱을 열지 못할 경우 폴백으로 사용 가능합니다. **참고:** 유니버설 링크에 대해 URI 스킴을 폴백으로 사용하면 iOS 기반 제한 사항이 적용됩니다. <Anchor target="_blank" href="/marketers/ko/docs/uri-scheme-fallback-for-ios">더 알아보기</Anchor>.

<div id="deep-linking" />

#### 딥링킹

유니버설 링크, 앱 링크 및 URI 스킴은 앱을 안전하게 **여는** 방법입니다. 사용자를 앱의 특정 활동 또는 페이지로 딥링크하고 리디렉트하려면 <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">원링크 딥링킹 지시사항</Anchor>을 따르십시오.

</Accordion>

<div id="which-operating-systems-allow-uri-schemes-to-open-the-app" />

<Accordion title="어떤 운영 체제에서 URI 스킴이 앱을 열 수 있습니까?">

| OS | 앱을 열기 위해 URI 스킴이 작동합니까? |
| --- | --- |
| iOS | **예.** 유니버설 링크 장애에 대한 폴백으로 사용합니다.<br /><br />**중요 사항:**<ul><li>URI 스킴을 폴백으로 사용하면 iOS 기반 제한 사항이 적용됩니다.</li><li>Safari를 포함한 많은 브라우저에서 파라미터 `af_force_deeplink=true`을 URL에 추가하여 폴백으로 URL 스킴을 사용할 수 있습니다. <Anchor target="_blank" href="/marketers/ko/docs/uri-scheme-fallback-for-ios">더 알아보기</Anchor>.</li></ul> |
| 안드로이드 | **예.** 삼성 기기, 6.0 이전 버전의 안드로이드 및 이후 안드로이드 버전에서 앱 링크가 실패할 때 폴백으로 사용합니다. |
| Amazon | **아니오** |
| Windows 모바일 | **아니오** |

</Accordion>

<div id="do-i-need-to-update-the-app-after-ios-universal-links-and-android-app-links-setup" />

<Accordion title="iOS 유니버설 링크 및 안드로이드 앱 링크 설정 후 앱을 업데이트해야 합니까?">

**예.** 기존 사용자를 위한 앱을 열기 위해 유니버설 링크 또는 앱 링크를 구현할 때마다 iOS 결합 도메인 또는 AndroidManifest.xml이 업데이트됩니다. 다시 말하면 해당 앱 스토어에 새 버전의 앱을 업로드해야 합니다. **일러두기:** 앱 업데이트의 필요성을 최소화하려면 <Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users">앱</Anchor>과 <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">딥 링크</Anchor>를 동시에 여는 데 필요한 모든 개발 관련 변경을 수행하십시오.

</Accordion>

<div id="can-i-redirect-existing-users-to-a-web-page-instead-of-the-app" />

<Accordion title="기존 사용자를 앱 대신 웹 페이지로 리디렉트할 수 있습니까?">

**예.** 그러나 템플릿을 구성하여 리디렉트하면 모든 사용자(신규 및 기존)에게 영향을 주고 모두에게 랜딩 페이지/웹 URL을 전송합니다. 다시 말하면 신규 사용자를 앱 스토어로 보내지 않습니다.

사용자를 웹 페이지로 보내는 방법은 다음과 같습니다.

1. 템플릿에서 유니버설 링크, 앱 링크 또는 URI 스킴을 설정하지 마십시오.
2. 앱이 랜딩 페이지/웹 URL로 리디렉션하도록 설치되지 않은 경우 리디렉션을 설정하십시오.
   * 랜딩 페이지/웹 URL은 af\_android\_url 및 af\_ios\_url 파라미터에 대한 값으로 추가됩니다.
   * 사용자를 리디렉션하는 모든 URL이 <Anchor target="_blank" href="/marketers/ko/docs/set-up-your-domain-redirect-allowlist">도메인 리디렉션 허용 목록</Anchor>에 추가되었는지 확인하십시오.
   * 그러면 앱이 설치될 때(기존 사용자의 경우)에도 리디렉션이 자동으로 적용됩니다.

**참고**: 기존 사용자를 앱 실행 후에만 모바일 웹 페이지로 리디렉트하려는 경우, 앱 개발자가 해당 동작을 설정해야 합니다.

</Accordion>

<div id="can-i-redirect-tablet-users-to-a-different-app-or-url-then-mobile-app-users" />

<Accordion title="태블릿 사용자를 모바일 앱 사용자와 다른 앱 또는 URL로 리디렉션할 수 있습니까?">

사용자는 다음에 대한 특정 리디렉션을 설정할 수 있습니다.

* 윈도우 폰
* iPad
* 아마존 킨들 파이어.

다른 태블릿은 현재 별도의 리디렉션을 지원하지 않습니다.

</Accordion>

<div id="can-i-assign-an-app-to-multiple-onelink-templates" />

<Accordion title="앱을 여러 원링크 템플릿에 할당할 수 있습니까?">

**예.** 단일 원링크 템플릿을 사용하여 많은 원링크 URL을 만들 수도 있지만, 하나의 앱을 여러 원링크 템플릿에 할당하는 것이 필요한 경우도 있습니다. 예를 들어, 여러 버전의 다른 앱 스토어용 안드로이드 앱이 있는 경우, 안드로이드 버전마다 별도의 OneLink 템플릿이 필요할 수 있지만 동일한 iOS 앱이 모두에 할당됩니다.

**중요 사항**:

iOS 유니버설 링크 및 안드로이드 앱 링크를 사용하여 앱을 여는 템플릿의 경우 **템플릿의 하위 도메인이 서로 다르면** 다음의 각각에 대해 iOS 및 안드로이드 앱을 각각 설정하고 업데이트해야 합니다.

* **iOS: 유니버설 링크** 새로운 원링크 템플릿을 만들고 앱에서 연결된 도메인을 업데이트한 후 새 버전을 앱 스토어에 제출합니다. 새 버전을 업데이트한 iOS 사용자만 새로운 템플릿에서 생성된 원링크 URL을 활성화할 수 있습니다.
* **안드로이드 앱 링크:**
  1. 새로운 원링크 템플릿을 만든 다음 앱 링크 항목의 마지막에서 XML 코드를 복사하고, 딥링크하려는 인텐트 내부의 **AndroidManifest.xml** 파일에서 모든 사전 인텐트 다음에 이를 추가합니다.
  2. 새 버전을 스토어에 배포합니다. 새 버전으로 업데이트한 안드로이드 사용자만 새로운 템플릿에서 생성된 원링크 URL을 활성화할 수 있습니다

</Accordion>

<div id="can-i-delete-a-onelink-template" />

<Accordion title="원링크 템플릿을 삭제해도 됩니까?">

네.

**템플릿 삭제 방법:**

1. 앱스플라이어에서 원링크 관리 페이지로 이동합니다.
2. 원링크 템플릿을 선택합니다.
3. ellipsis 메뉴에서 '템플릿 편집' 옵션을 클릭합니다.  

   <Image align="center" alt="delete template.png" src="https://files.readme.io/72b68cb979e2360f4e3065f99fbb547a91713a40dcc9adee59028ed2945f794a-31094482204945.png" width="1204px" />
4. "휴지통" 아이콘을 클릭합니다.

**참고:** 삭제된 템플릿에 기반한 기존 원링크 URL이 있는 경우 **사용자는 앱 스토어에도 들어갈 수 없습니다.** 이런 이유로, 템플릿을 사용하는 원링크 URL이 없는지 먼저 확인한 다음 템플릿을 삭제하는 것이 특히 중요합니다. 또는 기존 템플릿의 설정을 삭제하는 대신 변경하여 필요한 결과를 얻을 수 있는지 고려하십시오.

</Accordion>

<div id="can-i-change-the-subdomain-in-a-onelink-template" />

<Accordion title="원링크 템플릿에서 하위 도메인을 변경할 수 있습니까?">

**예, 앱스플라이어에 템플릿을 기반으로 하는 기존 사용자정의 링크가 없는 한 가능합니다.**

앱스플라이어에 원링크 템플릿을 기반으로 한 사용자정의 링크가 이미 있는 경우 하위 도메인을 변경할 수 없습니다. 이 제한은 라이브 링크의 리디렉션/딥링킹 작동 중단을 방지하기 위해 설계되었습니다.

기존 사용자정의 링크가 있는 템플릿에서 하위 도메인을 변경해야 하는 경우 다음 중 하나를 수행할 수 있습니다.

* 새 하위 도메인으로 원링크 템플릿을 새로 만들고, 이 새 템플릿을 이용하여 링크를 생성하십시오.
* 하위 도메인을 변경해야 하는 템플릿에 따라 기존의 모든 사용자정의 링크를 삭제합니다. 템플릿 기반의 모든 연결을 삭제하면 하위 도메인을 편집할 수 있습니다.

</Accordion>

<div id="can-the-domainsubdomain-of-a-onelink-template-be-applied-to-the-template-id-of-another-template" />

<Accordion title="원링크 템플릿의 도메인/하위 도메인을 다른 템플릿의 템플릿 ID에 적용할 수 있습니까?">

**아닙니다.** 특정 템플릿 및 템플릿 ID로 구성된 하위 도메인/도메인을 가져와서 다른 템플릿 ID에 수동으로 연결하면 유니버설 링크 및 앱 링크의 기능이 손상되고 보안 위협이 발생합니다.

**예시:**

* 템플릿 1ABC는 하위 도메인 **bank.onelink.me**로 구성됩니다.
* 템플릿 D123은 하위 도메인 **game.onelink.me**로 구성됩니다.
* **bank.onelink.me/1ABC/shorturl** 링크 는 템플릿 1ABC를 기반으로 생성되며 작동합니다.
* **game.onelink.me/D123/exampleurl** 링크는 템플릿 D123을 기반으로 생성되어 작동합니다.
* **bank.onelink.me/1ABC/shorturl** 링크는 작동하지 않음
* **bank.onelink.me/D123/exampleurl 링크**는 작동하지 않음

</Accordion>

<div id="can-i-use-the-same-subdomain-for-more-than-one-template" />

<Accordion title="두 개 이상의 템플릿에 동일한 하위 도메인을 사용할 수 있습니까?">

**예.** 그러나 하위 도메인을 사용하여 별도의 템플릿을 작성해야 합니다. 템플릿 ID에 하위 도메인을 수동으로 추가하지 마십시오.

</Accordion>

<div id="how-can-i-redirect-desktop-users" />

<Accordion title="데스크톱 사용자를 리디렉션하려면 어떻게 해야 합니까?">

데스크톱 사용자는 예를 들어 이메일 캠페인을 통해 원링크 사용자정의 링크에 참여할 수 있습니다. 그러나 데스크톱 사용자가 이러한 링크를 클릭하면 모바일 사이트, 앱 스토어 또는 앱으로 리디렉션될 수 없습니다. 기본적으로 데스크톱 사용자는 앱 스토어 또는 구글 플레이 스토어의 웹 버전으로 리디렉션됩니다.

**그러면 데스크톱 사용자에게 좋은 사용자 환경을 제공한 뒤, 모바일 사용자로 전환하려면 어떻게 해야 하나요?**

원링크 URL 또는 템플릿에서 데스크톱 사용자(Windows 또는 Mac)를 다른 URL로 리디렉션할 수 있습니다. 이 웹 URL은 `af_web_dp` 파라미터의 링크에 추가됩니다. 사용자를 리디렉션하는 모든 URL이 도메인 <Anchor target="_blank" href="/marketers/ko/docs/set-up-your-domain-redirect-allowlist">리디렉션 허용 목록</Anchor>에 추가되었는지 확인하십시오. 그렇지 않으면 리디렉션이 작동하지 않습니다.

**참고:** 링크에 `af_web_dp`가 포함된 경우, 앱스플라이어는 데스크톱의 클릭을 등록하지 않습니다.

<div id="tip" />

> 👍 **팁**
>
> SMS 또는 이메일을 통해 데스크톱 사용자의 모바일 기기에 원링크 URL을 보내는 전용 웹 양식이 포함된 웹 URL로 데스크톱 사용자 리디렉션을 시도해 보십시오. <Anchor target="_blank" href="/marketers/ko/docs/set-up-smart-script-to-convert-web-visitors#desktop">원링크 스마트 스크립트</Anchor> 솔루션의 일부인 이 옵션에 대해 자세히 알아보십시오.

</Accordion>

<div id="how-can-i-redirect-chrome-os-users" />

<Accordion title="Chrome OS 사용자를 리디렉션하려면 어떻게 해야 합니까?">

Chromebooks 앱은 안드로이드 앱으로 간주됩니다.

Chromebook의 경우, 앱을 다른 웹 URL에 인스톨하지 않고 새 사용자를 리디렉트하려면 다음을 수행합니다.

1. 원링크 템플릿 설정에서 **링크 작동 설정** > **앱이 인스톨되지 않은 경우** > **Android**에서 **다른 URL로 변경**을 클릭하십시오.  
   혹은  
   원링크 링크 설정의 **딥링킹 및 리디렉션** > **리디렉션** > **앱이 설치되지 않은 경우** > **안드로이드**에서 **웹 URL**을 선택하세요.
2. URL을 입력하십시오.  
   링크 설정을 통해 추가되면 `af_android_url` 파라미터의 링크에 URL이 추가됩니다.

</Accordion>

<div id="onelink-link-faq" />

### 원링크 링크 FAQ

<div id="does-onelink-work-without-the-appsflyer-sdk" />

<Accordion title="원링크가 앱스플라이어 SDK 없이 작동합니까?">

**예. 그러나 부분적으로만 작동합니다.**

앱스플라이어 SDK를 연동할 수 없을지라도, 모바일 웹 방문자를 모바일 앱 유저로 빠르게 전환시키는 것이 가능합니다.

앱스플라이어 SDK가 앱에 연동되어 있지 않더라도 기본 사용자 리디렉션과 앱 실행이 작동합니다. 스마트 배너는 SDK를 필요로 하지 않으며, SDK 없이도 정상 작동합니다.

그러나 SDK가 없다는 것은 다음을 의미합니다.

* 초기 앱 실행 이후로는 사용자를 클릭할 때 딥링크가 될 수 없습니다.
* 어트리뷰션 데이터를 기록할 수 없습니다.
* 인앱 이벤트를 기록할 수 없습니다.

</Accordion>

<div id="what-methods-are-available-for-creating-onelink-custom-links" />

<Accordion title="원링크 사용자정의 링크를 만드는 데 사용할 수 있는 방법은 무엇입니까?">

다음 표에서는 원링크 커스텀 링크를 만드는 데 사용할 수 있는 여러 방법을 비교합니다.

| 링크 생성 방법 | 사용자 | 짧은/긴 URL | 프리미엄 기능 | UI에 표시됩니까? | 어트리뷰션 TTL(생존 기간) 최대 및 기본 설정 |
| --- | --- | --- | --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">앱스플라이어 UI</Anchor> | 원링크 템플릿 및 사용자정의 링크 생성 | 둘 다 | -- | ✓ | TTL 없음 |
| <Anchor target="_blank" href="/marketers/ko/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">원링크 API</Anchor> | 수천 개의 링크를 빠르게 생성 | 숏 링크 | ✓ | -- | 31일 |
| 원링크 대량 링크 생성 | CSV에 정의된 파라미터를 사용하여 수천 개의 원링크 숏 URL을 신속하게 생성합니다. | 숏 링크 | -- | -- | 365일 |
| <Anchor target="_blank" href="/marketers/ko/docs/user-invite-attribution">SDK</Anchor> | 앱 추천(리퍼럴) 캠페인 | 숏 링크 | -- | -- | 60일 |
| <Anchor target="_blank" href="/marketers/ko/docs/onelink-smart-script-overview">OneLink Smart Script</Anchor> | 모바일 웹투앱 캠페인 | 롱 링크 | -- | -- | TTL 없음 |
| <Anchor target="_blank" href="/marketers/ko/docs/understand-onelink-short-vs-long-urls">스프레드시트</Anchor> | 고유의 수식을 적용하여 수천 개의 원링크 커스텀 링크 생성 | 롱 링크 | -- | -- | TTL 없음 |

</Accordion>

<div id="can-onelink-custom-links-open-the-app-from-a-browser" />

<Accordion title="원링크 사용자정의 링크가 브라우저에서 앱을 열 수 있습니까?">

**예,** 그러나 유니버설 링크 및 앱 링크는 클릭(예를 들어, 웹 페이지 또는 이메일의 링크 클릭)할 때만 작동합니다. **링크를 브라우저 주소창에 붙여넣고서는 앱을 열 수 없습니다.** 링크를 브라우저 URL 상자에 붙여넣지 않고 URL을 클릭하여 테스트합니다.

</Accordion>

<div id="why-doesnt-the-onelink-url-open-the-app-or-deep-link-existing-users" />

<Accordion title="원링크 URL이 앱을 열거나 기존 사용자를 딥링크하지 못하는 이유는 무엇입니까?">

좋은 의도에도 불구하고, 일부 경우에 있어서, 원링크 URL은 의도된 딥링킹을 수행하지 않을 수 있습니다. 이런 상황이 발생하면 사용자가 앱 내의 특정 액티비티에 딥링크되는 대신, 앱 스토어 또는 심지어 오류 페이지로 리디렉션됩니다.

그 이유는 다음과 같은 여러 가지가 있을 수 있습니다.

* **호스트 애플리케이션:** 어트리뷰션 링크가 공유된 앱 (예: WhatsApp, Gmail, WeChat)은 클릭된 링크를 활성화하기 위해, 자체 개발한 내부 브라우저와 같이 서로 다른 메서드를 사용합니다. 이들 중 일부는 모든 어트리뷰션 링크를 차단하는 것으로 알려져 있습니다.
* **브라우저:** 일부 브라우저 및 OS 플랫폼에서는 링크가 다르게 동작합니다. 예를 들어 특정 브라우저에서는 링크 붙여넣기가 작동하지 않습니다. 링크를 실제로 클릭해야 합니다.
* **OS 업데이트:** 새로운 OS 업데이트(iOS와 안드로이드 모두)로 인해 예상치 못하게 발생한 버그가 딥링킹을 방해할 수 있습니다.
* **기기:** 다양한 스마트폰, 태블릿, 노트북, 그리고 다른 버전의 iOS, 안드로이드, Windows 모바일 및 기타 운영 체제는 각각 어트리뷰션 링크 처리가 서로 매우 다를 수 있습니다.
* **구성 오류:** 딥링킹 값에 <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#traits-and-limitations">특수문자</Anchor>를 사용하면 링크가 끊어집니다.

사용자 환경을 개선하기 위한 두 가지 솔루션은 폴백 URL과 강제 딥링킹입니다.

<div id="fallback-urls" />

#### 폴백 URL

어떤 이유로든 앱 열기 또는 딥링킹이 실패할 경우 폴백 URL은 사용자를 지정된 웹 페이지로 보냅니다. **주의!** 또한 앱을 설치하지 않은 사용자를 올바른 앱 스토어 대신 폴백 URL로 보냅니다. 따라서 앱을 이미 설치한 사용자를 리타겟팅하는 경우에만 이 옵션을 사용하십시오.

폴백 URL을 구현하려면 원링크 템플릿 또는 사용자정의 링크 설정에서 앱이 설치되지 않은 경우의 링크 동작을 설정하여 다른 URL로 리디렉션하십시오.

<Image align="center" alt="different_url.png" src="https://files.readme.io/6e15b343cb778a0ab4e76c1be4a6bf3cd21ad675f9a64c521a61a4756a580a01-30192900484625.png" />

이 설정을 사용하면 `af_ios_url` 및 `af_android_url`이 폴백의 대상 파라미터로 추가되므로 iOS 사용자는 `af_ios_url`에서 지정한 페이지로, 안드로이드 사용자는 `af_android_url`에서 지정한 페이지로 리디렉션됩니다.

<div id="tip-1" />

> 📄 **예시**
>
> 예를 들어 다음과 같은 원링크 URL을 고려하십시오.
>
> ```http
> https://go.onelink.ly/qwerty?pid=source&af_dp=greatapp%3A%2F%2F&af_ios_url=www.yoursite.com/ios-bonus
> &af_android_url=www.yoursite.com/android-bonus
> ```
>
> 이 링크를 클릭하는 iOS 및 안드로이드 사용자 모두 앱에 딥링크되어 있어야 합니다. 그러나 딥링킹이 실패하면, 다음과 같이 리디렉션됩니다.
>
> * iOS: www.yoursite.com/ios-bonus
> * 안드로이드: www.yoursite.com/android-bonus

<div id="note-1" />

> 📘 **참고**
>
> 리디렉션이 발생하면 원링크 URL 파라미터는 `af_ios_url` 또는 `af_android_url`로 지정된 대상 페이지로 전달됩니다. 이 동작을 방지하려면 `af_param_forwarding=false` 파라미터를 원링크에 추가합니다.

<div id="forced-deep-linking" />

#### 강제 딥링킹

강제 딥링킹을 사용하면 URI 스킴을 폴백으로 사용하여 앱을 열고 사용자를 딥링킹할 수 있습니다.

이 솔루션은 앱을 설치해둔 사용자에게 적합합니다. 그러나 iOS의 경우 URI 스킴을 사용하여 앱을 여는 데는 제한이 있으며 URI 스킴에 지정된 활동에 강제로 딥링킹하려면 원링크 URL에 `af_force_deeplink=true`를 추가해야 할 수 있습니다(`af_dp` 파라미터). 더 자세한 정보는 <Anchor target="_blank" href="/marketers/ko/docs/uri-scheme-fallback-for-ios">iOS의 URI 스키마 폴백</Anchor>을 참조하십시오.

</Accordion>

<div id="why-does-my-onelink-url-open-a-blank-page-in-chrome" />

<Accordion title="내 원링크 URL이 Chrome에서 빈 페이지를 여는 이유는 무엇입니까?">

`target` 어트리뷰트가 포함된 HTML  태그를 사용하지 않는지 확인하십시오. 원링크 URL이  태그 안에 `target="_blank"` 어트리뷰트로 있으면 Chrome(iOS와 안드로이드 모두에서)에서 빈 페이지가 열리고 사용자는 앱 스토어 또는 Google Play로 리디렉션되지 않습니다.

</Accordion>

<div id="can-i-use-onelink-for-redirection-on-brave" />

<Accordion title="리디렉션용 원링크를 Brave에서 사용할 수 있습니까?">

예. 그러나 안드로이드에서는 사용자가 Brave 브라우저에서 원링크 링크를 클릭하면 디퍼드 딥링크가 작동하지 않습니다. iOS에서는 사용자가 클릭한 후 빈 화면이 표시되고 디퍼드 딥링크는 빈 화면에서 스크롤 또는 탭과 같은 작업을 수행하는 경우에만 작동합니다.

</Accordion>

<div id="do-onelink-custom-links-take-longer-to-load-than-other-links" />

<Accordion title="원링크 사용자정의 링크가 다른 링크보다 로드하는 데 시간이 오래 걸립니까?">

**아니요.** 원링크 사용자정의 링크는 제대로 작동하고 필요에 따라 사용자를 리디렉션하는 데 여분의 처리 또는 로드 시간을 추가하지 않습니다. 다른 앱스플라이어 링크만큼 빠릅니다.

</Accordion>

<div id="how-can-i-record-the-cost-per-install-when-using-onelink" />

<Accordion title="원링크를 사용할 때 설치당 비용을 기록하려면 어떻게 해야 합니까?">

**설치당 비용 사용**(**고급 파라미터**에서)을 설정하면 링크에서 오는 각 설치에 구체적 CPI 값을 적용할 수 있습니다.

비용 통화 단위를 선택한 다음 CPI를 나타내는 **숫자 값**(소수점 이후 최대 4자리)을 선택합니다. 그러면 링크에 af\_cost\_currency 및 af\_cost\_value 파라미터가 추가됩니다.

<div id="tip-2" />

> 📄 **예시**
>
> 문자메시지 캠페인의 비용은 문자 1,000건당 $20입니다(CPM). 경험에 의하면 이러한 캠페인은 5% 전환율을 기록하며, 이에 따라 계산된 CPI는 $0.40입니다. 인스톨당 비용을 0.40 USD로 설정하면 이 문자메시지 캠페인의 최종 ROI를 측정할 수 있습니다.

더 자세한 정보는 <Anchor target="_blank" href="/marketers/ko/docs/roi360-cost-aggregation-overview">비용 및 ROI 측정</Anchor>를 참조하십시오.

</Accordion>

<div id="how-can-i-prevent-parameter-forwarding-on-redirections" />

<Accordion title="리디렉션에 대한 파라미터 전달을 방지하려면 어떻게 해야 합니까?">

`af_r`, `af_ios_url`, `af_android_url`, `af_web_dp`는 어트리뷰션 링크 또는 원링크의 파라미터를 리디렉션된 페이지로 전달합니다. 이 동작을 방지하려면 어트리뷰션 링크에 `af_param_forwarding=false`를 추가하십시오.

</Accordion>

<div id="how-can-i-remove-appsflyer-pid-and-c-parameters-when-forwarding-while-keeping-all-other-parameters-on-redirection-urls" />

<Accordion title="리디렉션 URL에 다른 모든 파라미터를 유지하면서 포워딩 시 앱스플라이어 PID 및 C 파라미터를 제거하려면 어떻게 해야 하나요?">

경우에 따라 URL에 여러 PID가 있을 수 있습니다. 앱스플라이어가 리디렉션 URL에 PID 및 C 파라미터를 추가하고 클라이언트가 자체 PID 파라미터를 추가할 수도 있기 때문에 이런 것이 발생합니다. 예를 들어 클라이언트 웹 사이트 URL에서 '제품 ID'는 'pid'일 수 있습니다.

일반적으로 어트리뷰션 링크에 `af_param_forwarding=false`를 추가하면 모든 파라미터가 제거됩니다.

그러나 데스크톱에서 링크를 클릭하면 클라이언트가 필수 CRM 파라미터를 유지하기를 원할 수 있습니다. 앱스플라이어 PID 및 C 파라미터만 제거하고 다른 모든 파라미터는 유지하려면 `af_base_params_forward=false`를 어트리뷰션 링크에 추가하십시오.

</Accordion>

<div id="are-singleplatform-custom-links-still-available" />

<Accordion title="단일 플랫폼 커스텀 링크를 계속 사용할 수 있습니까?">

이제 원링크가 온드 미디어(owned media)에 사용하는 커스텀 어트리뷰션 링크를 생성하는 유일한 방식입니다.

과거에는 앱 소유주가 원링크 없이(특정 앱 중심) 단일 플랫폼 커스텀 링크를 사용했습니다. 단일 플랫폼 커스텀 링크 방식은 더 이상 운영되지 않으며 이제 새 커스텀 링크는 원링크 템플릿을 이용해서만 만들 수 있습니다.

그러나 이전에 만든 단일 플랫폼 사용자정의 링크는 기존과 같이 작동합니다. 원링크 사용자정의 링크 페이지의 오른쪽 상단 모서리에 있는 **레거시 단일 플랫폼 링크 보기**를 클릭하여 레거시 링크를 보고 편집할 수도 있습니다.

</Accordion>

<div id="can-i-change-the-short-url-id-after-saving-a-link" />

<Accordion title="링크를 저장한 후 짧은 URL ID를 변경할 수 있습니까?">

**아니요,** 짧은 URL ID는 링크가 생성됨과 동시에 설정할 수 있습니다.

</Accordion>

<div id="can-i-wrap-and-shorten-onelink-custom-links" />

<Accordion title="원링크 사용자정의 링크를 래핑 및 단축할 수 있습니까?">

**외부 링크 단축기 또는 원링크 사용자정의 링크를 래핑하면 유니버설 링크 및 앱 링크의 앱 열기 기능이 중단됩니다.**

유니버설 링크 또는 앱 링크를 활성화하려면 OS가 앱과 연결된 URL의 도메인을 인식해야 하지만, 어떤 유형의 외부 래핑, 단축 또는 사용자 대상 링크로의 리디렉션에 의해 불가능합니다. 여기에는 bit.ly, 비-앱스플라이어 브랜드 링크 또는 클릭 기록이 활성화된 ESP(이메일 서비스 제공업체) 사용이 포함됩니다.

**리디렉션이 정상적으로 작동할 수 있도록 링크를 래핑하거나 단축하는 법:**

* 원링크 사용자정의 링크를 생성할 때 (bit.ly와 같은 외부 단축기 대신) 앱스플라이어에서 생성된 짧은 URL을 사용합니다.   
   **팁**! 링크에 짧은 브랜드 도메인을 만들어 URL을 더 짧게 만드세요. 앱스플라이어 UI에서 링크를 생성하는 경우 URL ID를 최대한 짧게 편집할 수 있습니다. 예: https://brand.com/a1b2/a(brand.com이 사용자의 브랜드 도메인인 경우 **a1b2**는 항상 4문자인 템플릿 ID이고 **a**는 한 문자로 편집되는 URL ID입니다.    
   장점:
  * 이 방법은 원링크 템플릿에 설정된 원링크 하위 도메인(subdomain)을 이용하므로 잘 동작합니다.
  * 어트리뷰션 링크가 배포된 이후이거나 링크 운영 중에도, 딥링킹 설정을 포함한 파라미터를 변경할 수 있습니다.
  * 링크에 대한 모바일 디바이스에서의 모든 클릭이 앱스플라이어 대시보드에 집계되므로, 다른 서비스를 확인할 필요가 없습니다.
  * 단축 URL의 마지막 부분을 사용자 정의하여 <Anchor target="_blank" href="/marketers/ko/docs/brand-onelink-with-your-domain">브랜드 도메인</Anchor>으로 만들 수 있습니다.
* <Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users">URI 스킴</Anchor>을 폴백으로 사용하여 유니버설 링크 및 앱 링크가 실패할 때 앱을 열고 다음 파라미터를 링크에 추가합니다. `af_force_deeplink=true`.
* [ESP 작업](/docs/onelink-troubleshooting-and-faq#can-i-use-onelink-custom-links-in-emails) 옵션을 참조하십시오.

</Accordion>

<div id="can-i-use-onelink-custom-links-in-emails" />

<Accordion title="이메일에 원링크 사용자정의 링크를 사용할 수 있습니까?">

**예,** 그러나 ESP(이메일 서비스 제공업체)와 함께 작업할 때는 특별히 고려해야할 사항이 있습니다. 수행한 클릭 횟수를 계산하기 위해 ESP는 이메일 안에 있는 모든 링크를 래핑합니다. 이 경우 URL을 클릭하는 사용자에 대한 앱 열기/딥링킹 흐름이 중단됩니다.

이를 방지하려면 다음 옵션 솔루션 중 하나를 사용하십시오.

* ESP 설정에서 클릭 기록을 비활성화합니다.  
   **(팁: 이것이 일반적으로 가장 쉬운 솔루션입니다.)**
* 어트리뷰션 링크에 `af_dp` 플래그를 추가하여 `af_esp=true` 파라미터에 지정된 URI 스킴으로 앱을 강제로 엽니다. 이 솔루션은 앱을 설치해둔 사용자에게 적합합니다.
* 앱스플라이어 솔루션을 지원하는 ESP를 사용하여 앱을 열고 유니버설 링크와 딥링킹합니다. <Anchor target="_blank" href="/marketers/ko/docs/email-service-provider-esp-integration-guide">더 알아보세요</Anchor>.

</Accordion>

<div id="how-do-users-get-redirected-to-their-regional-app-store" />

<Accordion title="사용자가 어떻게 지역 앱 스토어로 리디렉션됩니까?">

원링크는 사용자의 IP 주소를 기반으로 올바른 지역 앱 스토어로 사용자를 리디렉션합니다.

</Accordion>

<div id="why-isnt-my-onelink-url-redirecting-users-to-the-specified-domain" />

<Accordion title="왜 저의 원링크 URL이 사용자를 지정된 도메인으로 리디렉션하지 않습니까?">

앱스플라이어에서 리디렉션 허용 목록을 활성화했는지 확인하십시오. 활성화된 경우 원하는 웹 URL 도메인 또는 서브도메인을 기재해야 합니다. <Anchor target="_blank" href="/marketers/ko/docs/set-up-your-domain-redirect-allowlist">리디렉션 허용 목록에 대해 자세히 알아보기</Anchor>

</Accordion>

<div id="why-do-i-get-the-app-you-are-looking-for-is-unavailable-error" />

<Accordion title="'찾고 있는 앱을 사용할 수 없습니다.' 오류가 발생하는 이유는 무엇입니까?">

다음과 같은 이유로 Google Play로 리디렉션되는 대신 '찾고 있는 앱을 사용할 수 없습니다.' 오류가 발생할 수 있습니다.

* 앱이 현재 Google Play에서 '보류 중' 상태입니다. 위에 언급된 오류 메시지를 방지하려면 Google Play 대신 웹 URL을 가리키도록 링크의 리디렉션을 설정하세요. 앱이 승인되면 리디렉션을 다시 Google Play로 다시 변경할 수 있습니다. 이러한 구성 변경은 <Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template#create-a-onelink-template-with-redirection-logic-for-new-app-users">링크의 템플릿 페이지</Anchor>에서 수행됩니다.
* 앱이 타사 스토어를 통해서만 제공되는 경우, 앱스플라이어에서 잘못된 Google Play 상태가 할당되어 문제가 발생할 수 있습니다. 이 문제를 해결하려면 내 앱 설정 페이지에서 <Anchor target="_blank" href="/marketers/ko/docs/set-up-multi-store-android-attribution#dashboard-per-store-adding-the-app">Google Play 상태를 스토어 ‘외부에 게시됨’으로 설정해야 합니다</Anchor>.

</Accordion>

<div id="why-is-my-monelinkme-shortlink-not-working" />

<Accordion title="m.onelink.me 숏링크가 왜 작동하지 않습니까?">

2024년 6월부터 기존의 숏링크 버전 **m.onelink.me**은 더 이상 사용되지 않습니다. 해당 서브 도메인을 사용하는 링크는 더 이상 정상적으로 리디렉션되지 않아, 사용자 흐름에 차질이 생길 수 있습니다.

</Accordion>

<div id="can-i-manually-switch-between-the-branded-domain-and-its-onelink-subdomain-in-an-existing-link" />

<Accordion title="기존 링크에서 브랜드 도메인과 원링크 서브 도메인 사이를 수동으로 전환할 수 있나요?">

예 - 브랜드 도메인과 원링크 하위 도메인이 제대로 매핑된 경우에는 가능합니다. 다음을 참조하세요. <Anchor target="_blank" href="/marketers/ko/docs/brand-onelink-with-your-domain#set-up-a-branded-domain-in-appsflyer">앱스플라이어에서 브랜드 도메인 설정</Anchor>

**예**:  
 원링크 하위 도메인: **demo.onelink.me**  
 템플릿 ID: **A1r4**  
 [**demo.onelink.me**](http://demo.onelink.me) 하위 도메인에 매핑된 브랜드 도메인은 다음과 같습니다.

* **app.simulatorapp.com**
* **click.simulatorapp.com**

원링크 UI에서 다음 브랜드 링크를 생성했습니다.  
 **app.simulatorapp.com/A1r4/simulationlink**  
 위의 브랜드 링크를 다른 브랜드 도메인 링크 또는 원링크 하위 도메인 링크로 교체할 수 있습니다.   
 다음 링크는 기능적으로 동일하며 모든 곳에서 동일 하게 작동합니다.

* app.simulatorapp.com/A1r4/simulationlink
* demo.onelink.me/A1r4/simulationlink
* click.simulatorapp.com/A1r4/simulationlink

</Accordion>

<div id="onelink-parameter-faq" />

### 원링크 파라미터 FAQ

<div id="what-parameters-are-mandatory-for-onelink-custom-links" />

<Accordion title="원링크 사용자정의 링크에 필수적인 파라미터는 무엇입니까?">

미디어 소스(**pid**) 파라미터만 필수입니다.

</Accordion>

<div id="can-parameters-be-appended-to-the-short-url" />

<Accordion title="파라미터를 짧은 URL에 추가할 수 있습니까?">

**예,** 모든 파라미터를 짧은 URL에 추가할 수 있습니다.

**중요!** 짧은 URL에 첨부된 파라미터는 링크 내부의 파라미터를 재정의하지 않습니다.

<div id="tip-3" />

> 📄 **예시**
>
> * 다음 출력 형식으로 원링크 커스텀 링크를 만듭니다.
>   * **긴 URL:** https://onelink-sim.onelink.me/Il2C?pid=training&c=peaches
>   * **짧은 URL:** https://onelink-sim.onelink.me/Il2C/70e6d165
> * 다음 파라미터를 짧은 URL에 추가합니다. https://onelink-sim.onelink.me/Il2C/70e6d165?c=bananas&af_adset=fruits
> * 짧은 URL에 추가된 **af\_adset=fruits** 파라미터는 어트리뷰션에 효과적입니다. 그러나 긴 URL에 이미 **c** 파라미터가 있으므로 **c=bananas** 파라미터는 **유효하지 않습니다**.

</Accordion>

<div id="what-custom-media-source-names-can-i-use" />

<Accordion title="사용할 수 있는 사용자정의 미디어 소스 이름은 무엇인가요?">

온드 미디어의 경우, 연동 파트너가 사용하지 않는 값이라면 커스텀 미디어 소스 이름(PID 값)은 자유롭게 설정할 수 있습니다. 충돌을 방지하려면 커스텀 미디어소스에 \_int 접미사를 사용하지 마십시오. 그러나 어트리뷰션 데이터 무결성에 영향을 줄 수 있으므로 커스텀 미디어소스 이름으로 *오가닉*을 사용하지 않는 것이 좋습니다.

페이드 미디어(paid media)에 원링크를 사용하는 경우:

* 연동 파트너 예약 **PID** 값( **\_int**으로 끝나는 값)을 원링크 커스텀 링크의 미디어소스 값으로 사용합니다. *googleadwords* 또는 *facebook*과 같은 SRN 미디어소스를 사용자 지정 미디어소스 이름으로 사용하지 마세요. 이는 어트리뷰션 데이터 무결성에 영향을 미칠 수 있습니다.
* 파트너가 앱스플라이어와 연동되어 있고 원링크 템플릿에 설정된 모든 앱에 대해 활성 상태( **파트너 활성화** 토글이 켜져 있음)되어 있는지 확인하십시오.

</Accordion>

<div id="what-attribution-parameters-can-be-added-to-a-onelink" />

<Accordion title="원링크에 추가할 수 있는 어트리뷰션 파라미터는 무엇입니까?">

많은 어트리뷰션 파라미터를 추가하면 드릴 다운 분석을 할 수 있습니다.

| **어트리뷰션 파라미터** | **설명** | **파라미터 링크 이름** |
| --- | --- | --- |
| **캠페인** | 캠페인 이름을 설정하여 온드 미디어 소스에서 다양한 캠페인 비교 | C |
| **광고세트** | 광고 세트 이름을 설정하여 온드 미디어 소스의 특정 캠페인 내 서로 다른 광고 세트 비교 | af\_adset |
| **광고 이름** | 온드 미디어 소스의 특정 광고 세트나 캠페인의 서로 다른 광고 소재를 비교할 수 있는 파라미터 | af\_ad |
| **채널** | 온드 미디어에 대해 둘 이상의 배포 채널을 비교하려면 채널 이름을 설정하십시오.<br /><br />예시: SMS 메시지를 두 SMS 서비스 제공업체 간에 분할하는 경우 채널 파라미터를 사용하여 제공업체를 지정합니다. 나중에 두 제공업체의 전환율을 비교할 수 있습니다. | af\_channel |
| **서브 파라미터** | 사용 가능한 5개의 가입자 파라미터 중 하나를 사용하여 분석에 유용한 값을 삽입합니다.<br /><br />**참고:** 이러한 파라미터는 구문 분석되어 로데이터 리포트에 표시되므로 데이터 집계 또는 필터링을 수행하는 데 유용합니다. | af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5 |
| **커스텀 파라미터** | 구독자 파라미터와 마찬가지로 파라미터 이름과 값을 가진 필드를 지정할 수 있습니다. 그리고 모든 이름이 해당됩니다.<br /><br />구독자 파라미터와 달리 사용자정의 파라미터는 로데이터에서 구문 분석되지 않으며 **원래 URL** 열에서만 로데이터 리포트에 나타납니다. | 커스텀 파라미터  <br />(사용자가 지정한 대로) |

자세한 정보는 <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters">앱스플라이어 어트리뷰션 링크 구조와 파라미터</Anchor>를 참조하십시오.

</Accordion>

<div id="are-custom-parameters-added-to-onelink-custom-links-available-in-raw-data" />

<Accordion title="원링크 사용자정의 링크에 추가된 사용자정의 파라미터를 로데이터에서 사용할 수 있습니까?">

**예.** 사용자정의 파라미터는 로데이터의 **원래 URL** 열로 전달되며 이것을 여기서 확인할 수 있습니다. 로데이터에는 자체 열이 없습니다.

구문 분석 데이터의 경우 가입자 파라미터를 사용합니다. `af_sub1-5`각 파라미터는 로데이터 리포트에 별도의 열이 있습니다.

</Accordion>

<div id="are-parameter-names-case-sensitive" />

<Accordion title="파라미터 이름은 대소문자를 구분합니까?">

**예.** 파라미터 및 값에 소문자만 사용하도록 하십시오. 파라미터 이름 및 값의 대소문자 구분 문자 또는 대소문자의 불일치로 인해 대시보드와 로데이터에 오류 또는 데이터 불일치가 발생할 수 있습니다.

</Accordion>

<div id="integrated-partner-faq" />

### 연동 파트너 FAQ

<div id="can-i-use-onelink-in-social-apps-unpaid" />

<Accordion title="소셜 앱(무료)에서 원링크를 사용할 수 있습니까?">

이러한 게시물에 노출되는 잠재적 사용자는 자신의 기기에 따라 사전에 타게팅될 수 없으므로 소셜 앱의 무료 게시물에 원링크를 사용하는 것이 좋습니다.

유감스럽게도 일부 소셜 앱에 의해 설정된 iOS 유니버설 링크 한계 및 제한사항은 기본 기기 인식, 리디렉션 및 속성, 딥링킹에 대한 원링크의 사용을 복잡하게 만듭니다. 경우에 따라 사용자를 리디렉션하거나 딥링크하기 위해 소셜 앱 랜딩 페이지 또는 URI 스킴을 설정해야 할 수 있습니다.

다음 표는 현재 유명한 소셜 앱에서 원링크로 할 수 있는 것들을 요약해서 보여줍니다.

<table><thead><tr><th>소셜 앱</th><th>앱을 설치하지 않은 안드로이드 사용자</th><th>안드로이드 딥링킹</th><th>앱을 설치하지 않은 iOS 사용자</th><th>iOS 딥링킹</th></tr></thead><tbody><tr><td> <strong>Facebook</strong> (부스티드 포스트 포함)</td><td><span>✓\*\*†† </span></td><td><span>✓\*\*††</span></td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>Facebook 메신저</strong></td><td><span>✓\*\*†† </span></td><td> <span>✓\*\*</span> </td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>스냅챗</strong></td><td><span>✓†† </span></td><td> <span>✓\*</span> </td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>인스타그램</strong></td><td><span>✓†† </span></td><td><span>✓††</span></td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>LinkedIn</strong></td><td><span>✓</span></td><td><span>✓\*\*</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td><strong>Reddit</strong></td><td>-</td><td>-</td><td>-</td><td>-</td></tr><tr><td><strong>Slack</strong></td><td><span>✓</span></td><td> <span>✓\*</span> </td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>X(이전의 트위터)</strong></td><td><span>✓</span></td><td> <span>✓\*</span> </td><td><span>✓</span></td><td> <span>✓\*</span> </td></tr><tr><td><strong>WeChat</strong></td><td><span>✓† </span></td><td><span>✓† </span></td><td><span>✓\*</span></td><td><span>✓\*† </span></td></tr><tr><td><strong>WhatsApp</strong></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td colspan="5"><p>\* <a href="./onelink-troubleshooting-and-faq#which-operating-systems-allow-uri-schemes-to-open-the-app">URI 스킴</a> 또는 <a href="./create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page" target="_blank">소셜 앱 랜딩 페이지</a> 설정인 경우. <strong>참고</strong>: Facebook과 Facebook Messenger의 경우 URI 스킴과 소셜 앱 랜딩 페이지가 모두 설정되어 있으면 소셜 앱 랜딩 페이지가 표시되지 않습니다.</p><p>\*\* URI 스킴이 있어야 합니다.</p><p><span>† </span> 외부 브라우저에서 링크를 열라는 메시지가 표시될 수 있습니다.</p><p><span>††</span>안드로이드 소셜 앱 WebView 딥링킹 리디렉션 제한. 세부 정보는 <a href="./create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#android-social-apps-webview-deep-linking-redirection" target="_blank"><span>여기</span></a>에서 확인하세요<span>.</span></p></td></tr></tbody></table>

</Accordion>

<div id="can-i-use-onelink-with-ad-networks-paid" />

<Accordion title="원링크를 애드 네트워크(유료)와 함께 사용할 수 있습니까?">

**예,** 그러나 원링크는 주로 광고 네트워크가 아닌 온드 미디어와 함께 사용된다는 점을 명심해야 합니다. 광고 네트워크는 일반적으로 앱(사용자의 플랫폼, 기기 ID 등을 알고 있다는 의미)에 광고를 하므로 앱 및 플랫폼별 어트리뷰션 링크로 충분하므로 원링크를 사용할 필요가 없습니다. 하지만 애드 네트워크가 사용자 플랫폼을 미리 알지 못하는 경우(예를 들어, 이메일 또는 SMS 캠페인을 직접 실행할 경우)에는 원링크가 솔루션이 될 수 있습니다.

<div id="important" />

> 🚧 **중요!**
>
> 원링크를 애드 네트워크에서 사용할 때는 원링크의 긴 URL을 사용해야 합니다.

**연동된 애드 네트워크에 원링크 설정하기**

* <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#attribution-link-tab">광고 네트워크 어트리뷰션 링크 지침</Anchor>을 따르고 메시지가 표시되면 **원링크 사용**을 선택합니다.

안드로이드 및 iOS에 대한 모든 파라미터가 올바르게 추가되었으면, 원링크 커스텀 링크를 누르고 사용자를 올바른 플랫폼으로 리디렉션하면 사용자가 설치한 후 필요한 파라미터가 포스트백 내의 네트워크로 전송됩니다.

<div id="tip-4" />

> 📄 **예시**
>
> ```http
> https://greatapp.onelink.me/3287867539?pid=network_int&c=email&
> idfa{$IDFA}&gaid={$GAID}&clickid=$SITEID&
> af_sub1=[pixel_code]&af_sub2=[creative]
> ```
>
> 애드 네트워크는 앱 사용자의 디바이스 OS에 따라 IDFA나 GAID 파라미터를 사용하고 다른 파라미터는 무시합니다.

</Accordion>

<div id="how-can-i-solve-the-ios-applaunching-issue-from-social-media-apps" />

<Accordion title="소셜 미디어 앱에서 iOS 앱 실행 문제를 해결하려면 어떻게 해야 합니까?">

Facebook 및 기타 다른 소셜미디어 앱에서 iOS 유니버설 링크로 앱을 여는 것이 차단될 수 있습니다. <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">소셜 앱 랜딩 페이지</Anchor>는 이러한 앱 실행 문제에 권장되는 솔루션입니다.

소셜 앱 랜딩 페이지를 사용하지 않으려면 URI 스킴을 폴백 방법으로 사용할 수 있습니다. 그러나 다음을 알아두십시오.

* URI 스킴을 폴백으로 사용하면 iOS 기반 제한 사항이 적용됩니다.
* Safari를 포함한 많은 브라우저에서 파라미터 `af_force_deeplink=true`을 URL에 추가하여 폴백으로 URL 스킴을 사용할 수 있습니다. <Anchor target="_blank" href="/marketers/ko/docs/uri-scheme-fallback-for-ios">더 알아보기</Anchor>.

</Accordion>

<div id="can-i-use-onelink-on-instagram" />

<Accordion title="인스타그램에서 원링크를 사용할 수 있습니까?">

**예,** 그러나 다음 제한 사항에 유의하십시오.

* 인스타그램이 페이지 포스트에서 텍스트를 렌더링하는 방식으로 인해 포스트 캡션에는 클릭할 수 있는 링크를 삽입할 수 없습니다.
* 앱 열기와 안드로이드 앱과의 딥링킹은 특별한 고려사항 없이 지원됩니다. 하지만 인스타그램은 앱 열기와 iOS 앱과의 딥링킹을 지원하지 않습니다. 이를 해결하기 위해서는, 다음 두 가지 방법 중 하나를 진행할 수 있습니다.
  * **권장:** <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">소셜 앱 랜딩 페이지</Anchor>를 설정하십시오. Clustered Poster와 ShowAndTell 템플릿이 가장 효과가 좋습니다. 소셜 랜딩 페이지 외에도 원링크 템플릿에서 URI 체계를 설정하는 것이 좋습니다.
  * 인스타그램에 원링크를 사용할 때 URI 스킴과 [강제 딥링킹](/docs/onelink-troubleshooting-and-faq#강제-딥링킹)을 사용합니다. 인스타그램에 `af_force_deeplink=true`와 함께 원링크를 사용할 때 다음 사항에 유의하십시오.  

| 앱을 설치했습니까? | 클릭이 af\_force\_deeplink=true를 가지고 있습니까? | 완료 후 |
| --- | --- | --- |
| 아니오 | 예 | 클릭이 앱스토어를 엽니다. |
| 아니오 | 아니오 | 클릭이 앱스토어를 엽니다. |
| 예 | 예 | 클릭이 앱을 오픈합니다. |
| 예 | 아니오 | 클릭이 앱스토어를 엽니다. |

</Accordion>

<div id="can-i-use-onelink-for-redirection-on-wechat" />

<Accordion title="리디렉션용 원링크를 WeChat에서 사용할 수 있습니까?">

WeChat은 안드로이드 및 iOS 딥링크를 재정의하여 사용자를 웹페이지로 이동시킵니다. 이 웹페이지에서 사용자는 **옵션** 버튼을 반드시 클릭하고 브라우저에서 열기를 선택해야 합니다. 결과적으로 사용자 경험이 불편해지고 전환율이 떨어질 수 있게 됩니다.

이것을 극복하기 위해 원링크는 WeChat에서의 클릭을 인식하면, 사용자가 옵션 버튼을 클릭하고 **브라우저로 열기**를 클릭하도록 지시하는 전용 랜딩 페이지를 로딩합니다. 그러면 원링크 템플릿 설정에 정의된 리디렉션 URL이 열립니다.

<Image align="center" alt="WeChat_a.jpg" src="https://files.readme.io/49c03a10d458f6ce71fd6448e922294682ac9239775534c6264c29151ec1ea6d-30192900489105.jpg" />

만약 사용자의 위챗 언어가 중국어로 설정되었다면, 원링크는 현지화된 버전의 랜딩 페이지를 생성합니다.

<Image align="center" alt="WeChat_b.jpg" src="https://files.readme.io/502ef821a122459ab991f2a507c720f25fcac7129eb647a01290e8cabfa7a34e-30192887085841.jpg" />

</Accordion>

<div id="why-are-android-users-with-the-app-installed-being-redirected-to-a-web-url-and-not-into-the-app-when-they-click-a-link-on-facebook-webview" />

<Accordion title="Facebook 웹뷰에서 링크를 클릭할 때 앱을 설치한 안드로이드 사용자가 웹 URL로 리디렉션되고 앱으로 리디렉션되지 않는 이유는 무엇입니까?">

일반적으로 앱을 열고 Facebook 광고에서 딥링킹하는 것이 가능합니다. 단, 다음 조건이 적용되는 경우 Facebook은 원링크 URL에서 기존 앱 사용자를 대상으로 앱을 열 수 없습니다. 대신, 앱 사용자를 포함한 모든 사용자는 원링크 템플릿에 정의된 URL이나 **af\_android\_url**, **af\_r**, 또는 **af\_custom\_android\_url** 파라미터 중 하나의 값으로 전송됩니다.

* 사용자에게 안드로이드 모바일 디바이스가 있습니다.
* 링크는 Facebook 앱에서 클릭됩니다.
* 링크는 Facebook 웹뷰에서 열리는 HTML 페이지(사이트 또는 소셜 앱 랜딩 페이지)로 연결됩니다.
* HTML 페이지에는 **af\_dp** 파라미터(URI 구성표가 있음) 및 OneLink 템플릿 또는 파라미터(**af\_android\_url**, **af\_r** 또는 **af\_custom\_android\_url** 중 하나)의 URL 리디렉션 설정이 있는 링크가 포함되어 있습니다.

</Accordion>

<div id="testing-faq" />

### 테스트 FAQ

<div id="how-can-i-ab-test-the-social-app-landing-page" />

<Accordion title="소셜 앱 랜딩 페이지 A/B 테스트를 어떻게 합니까?">

<Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">소셜 앱 랜딩 페이지</Anchor>는 소셜 네트워크에 원링크를 적용하여 유저에게 원활한 앱 실행 경험을 제공합니다. 유저 경험에 한 단계를 추가해서 전환율이 줄어들까봐 우려하실 수 있습니다. 그러나 랜딩 페이지가 없으면 사용자 여정이 끊기기 쉬워 전환율이 매우 낮습니다.

랜딩 페이지가 필요한지에 대한 확신이 안서면, 테스트를 해보시겠습니까?

소셜 미디어 앱에서 사용자정의 링크를, 소셜 앱 랜딩 페이지가 있는 경우와 없는 경우로 <Anchor target="_blank" href="/marketers/ko/docs/create-a-b-tests">A/B 테스트</Anchor>를 하세요.

**소셜 앱 랜딩 페이지 A/B 테스트하기**

1. 소셜 미디어 앱에 사용할 <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">원링크 링크</Anchor> (Link1)을 만듭니다. 이 링크에 대해서는 소셜 앱 랜딩 페이지를 설정하지 마십시오.
2. **af\_adset** 어트리뷰션 파라미터를 추가합니다.
3. 값을 "no lp"로 하는 **af\_ad** 어트리뷰션 파라미터를 추가합니다.
4. Link1을 소셜 미디어 앱이 아닌 곳에서 테스트하여 앱을 정상적으로 여는지 확인합니다.
5. Link1을 복사하여 Link2라고 이름 붙입니다.
6. **af\_ad** 어트리뷰션 파라미터 값을 "using lp"로 변경합니다.
7. Link2에 대해서만 <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">소셜 앱 랜딩 페이지를 만듭니다</Anchor>.
8. **동일한** 소셜 미디어 앱에서 Link1과 Link2로 각각 하나씩 두 포스트를 게재합니다.  
   각 링크의 클릭 수는 신경쓰지 마십시오. 중요한 KPI는 최종 전환율입니다.
9. **트래픽이 충분히 발생하면 A/B 테스트 결과를 확인하십시오.**
   1. 앱스플라이어 개요 대시보드에서 스크롤 다운하여 **집약형 성과 리포트** 표를 확인하십시오.
   2. Link1과 Link2는 미디어 소스, 캠페인, 애드셋 이름이 모두 같습니다. 특정 애드셋을 분석합니다.
   3. Link1이나 Link2를 클릭한 사용자의 전환율(및 기타 KPI)을 비교합니다.

</Accordion>

<div id="how-can-i-bypass-the-app-selection-dialog" />

<Accordion title="앱 선택 대화 상자를 우회하려면 어떻게 해야 합니까?">

원링크를 테스트할 때 앱 선택 대화상자가 나타나면 <Anchor target="_blank" href="https://developer.android.com/studio/publish/app-signing">디버그 앱</Anchor>이더라도 <Anchor target="_blank" href="https://developer.android.com/studio/publish/app-signing#debug-mode">앱에 로그인</Anchor>하세요. 앱에 로그인할 때 사용하는 인증서는 앱 링크에 대한 원링크를 구성할 때 <Anchor target="_blank" href="https://dev.appsflyer.com/docs/initial-setup-for-deep-linking-and-deferred-deep-linking#generating-a-sha256-fingerprint">SHA256 핑거프린트를 생성</Anchor>하는 데 사용하는 것과 동일한 인증서입니다.

</Accordion>

<div id="deep-linking-faq" />

### 딥링킹 FAQ

<div id="what-deep-linking-methods-should-be-implemented" />

<Accordion title="어떤 딥링킹 메서드를 구현해야 합니까?">

개발사는 딥링킹을 위한 UDL(통합 딥링킹) 방법을 구현해야 합니다. <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">딥링킹에 대한 당사의 전체 지침</Anchor>을 참조하십시오.

iOS 유니버설 링크와 안드로이드 앱 링크는 **앱을 실행시키는 메서드이며 실제로 사용자를 (앱 내 특정 콘텐츠로 보내는) 딥링킹하지 않습니다.** URI 스킴 메서드는 (**af\_dp** 사용자정의 링크 파라미터를 통해) 앱과 딥링킹 사용자를 실행할 수 있지만, 이는 앱 실행을 위한 설정에만 사용되어야 합니다. 유니버설 링크 및 앱 링크의 주요 용도는 6.0 이전 버전의 안드로이드 OS를 사용하는 앱 실행 사용자를 위한 폴백 방식입니다.

위 방법 중 하나로 앱이 실행되면, 앱스플라이어 SDK는 사용자정의 어트리뷰션 링크에 명시된 **deep\_link\_value**를 제공합니다. 이 값은 개발사가 구현한 UDL 방법을 통해 전달되어야 합니다.

</Accordion>

<div id="can-a-uri-scheme-af_dp-parameter-be-used-for-deep-linking" />

<Accordion title="URI 스킴(af_dp 파라미터)을 딥링킹에 사용할 수 있습니까?">

**네,** 그러나 권장하지 않습니다. 이론적으로는 딥링킹을 위해 **deep\_link\_value**를 사용해야 하며, 딥링킹 없이 (**af\_dp** 파라미터를 통해) 앱을 실행하려면 폴백 메서드로 URI 스킴을 사용합니다. 하지만 이미 **URI 경로의 일부로 연결된 추가 파라미터를 사용하여 딥링크로 설정된 URI 스킴이 있는 경우(예를 들어 greatapp://param1/param2) 기존 설정 또는 코드를 변경할 필요가 없으므로 URI 스킴이 계속 작동합니다.**

**사용자정의 파라미터를 추가할 때는 사용자정의 링크 설정 페이지에서 설정하는 것이 가장 좋습니다**.

</Accordion>

### iOS 14 FAQ

<div id="does-onelink-deep-linking-work-for-ios-14" />

<Accordion title="원링크 딥링킹이 iOS 14에서 작동하나요?">

애드 네트워크 캠페인 및 UDL 메서드를 사용하는 온드 미디어에서 딥링크된 iOS 14 사용자는 사용자 경험에 영향을 받지 않습니다. 레거시 메서드가 딥 링킹을 방해할 수 있습니다.

어트리뷰션/리포트를 위해 앱스플라이어는 가능한 경우 IDFA 또는 IDFV를 사용합니다. IDFA 또는 IDFV가 없는 경우 확률적 모델링을 사용할 수 있습니다. iOS 14.5이부터 확률적 모델링은 온드 미디어, 크로스 프로모션, 사용자의 동의를 받은 웹-투-앱 전환 측정에만 적용됩니다.

</Accordion>

<div id="does-onelink-deferred-deep-linking-work-for-ios-14" />

<Accordion title="원링크 디퍼드 딥링킹이 iOS 14에서 작동하나요?">

애드 네트워크 캠페인 및 UDL 메서드를 사용하는 온드 미디어에서 디퍼드 딥링크된 iOS 14 사용자는 사용자 경험에 영향을 받지 않습니다. 레거시 메서드가 디퍼드 딥 링킹을 방해할 수 있습니다.

어트리뷰션/리포트를 위해 앱스플라이어는 가능한 경우 IDFA 또는 IDFV를 사용합니다. IDFA 또는 IDFV가 없는 경우 확률적 모델링을 사용할 수 있습니다. iOS 14.5이부터 확률적 모델링은 온드 미디어, 크로스 프로모션, 사용자의 동의를 받은 웹-투-앱 전환 측정에만 적용됩니다. 애드 네트워크와 온드 미디어에서 디퍼드 딥링킹을 구현하려면, 앱스플라이어 iOS SDK V6.1.0 이상을 설치하여 ATT 동의를 얻고 (필요한 경우) 전체적인 영향을 완화하며 빠른 응답 시간을 활용하기를 권고드립니다.

</Accordion>

<div data-zendesk-anchors="onelink-troubleshooting-guide=%EC%9B%90%EB%A7%81%ED%81%AC-%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0-%EA%B0%80%EC%9D%B4%EB%93%9C 01H7WPYJV9CQ1J6J3PFCEQFGB0=%EC%9B%90%EB%A7%81%ED%81%AC-%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0-%EA%B0%80%EC%9D%B4%EB%93%9C onelink-frequently-asked-questions=%EC%9B%90%EB%A7%81%ED%81%AC-faq 01H7WPYJV9H52P659N8JPRX2TY=%EC%9B%90%EB%A7%81%ED%81%AC-faq onelink-template-faq=%EC%9B%90%EB%A7%81%ED%81%AC-%ED%85%9C%ED%94%8C%EB%A6%BF-faq 01H7WPYJV9TJRKHFZ77DFMKDDG=%EC%9B%90%EB%A7%81%ED%81%AC-%ED%85%9C%ED%94%8C%EB%A6%BF-faq which-method-should-i-use-for-opening-apps%E2%80%94universal-links-app-links-or-uri-schemes=which-method-should-i-use-for-opening-apps-universal-links-app-links-or-uri-schemes 01H7WPYJV9JQG66S3K7TRHMFHA=which-method-should-i-use-for-opening-apps-universal-links-app-links-or-uri-schemes 01H7WPYJV9TV402AGAAGYARATW=%EC%B0%B8%EA%B3%A0 deep-linking=%EB%94%A5%EB%A7%81%ED%82%B9 01H7WPYJV9JSQ5FV73YCE3H5AF=%EB%94%A5%EB%A7%81%ED%82%B9 01H7WPYJV9CMQAQZ56P5P2MDBV=which-operating-systems-allow-uri-schemes-to-open-the-app 01H7WPYJV975A2YS61MQM1WX4W=do-i-need-to-update-the-app-after-ios-universal-links-and-android-app-links-setup 01H7WPYJV9GPXDP0KSQEPZXJCH=can-i-redirect-existing-users-to-a-web-page-instead-of-the-app 01H7WPYJV9A266QMK2J1K2AQXR=can-i-redirect-tablet-users-to-a-different-app-or-url-then-mobile-app-users 01H7WPYJV9DCVNRR3NNF7JMR0D=can-i-assign-an-app-to-multiple-onelink-templates 01H7WPYJV90RVHSAWA2YHBNNHA=can-i-delete-a-onelink-template 01H7WPYJV9RPNG3Z94630B789K=can-i-change-the-subdomain-in-a-onelink-template 01H7WPYJV9C0H3ZH6F6F3E43WH=can-the-domainsubdomain-of-a-onelink-template-be-applied-to-the-template-id-of-another-template 01H7WPYJV9246X8821B943N9AD=can-i-use-the-same-subdomain-for-more-than-one-template 01H7WPYJVAFBS0Y56NWN8M979B=how-can-i-redirect-desktop-users 01H7WPYJVA6PWA88VD8V0B3M74=%ED%8C%81 01H7WPYJVAB57R0VQAS7C0D9NK=how-can-i-redirect-chrome-os-users onelink-link-faq=%EC%9B%90%EB%A7%81%ED%81%AC-%EB%A7%81%ED%81%AC-faq 01H7WPYJVAPNYAQ1SH4FBX4Z9F=%EC%9B%90%EB%A7%81%ED%81%AC-%EB%A7%81%ED%81%AC-faq 01H7WPYJVAEQQDSJ298M8JV361=does-onelink-work-without-the-appsflyer-sdk 01H7WPYJVA8XASRX9X3QVAWYS9=what-methods-are-available-for-creating-onelink-custom-links 01H7WPYJVATBVVMEPNAVBW9ZFZ=can-onelink-custom-links-open-the-app-from-a-browser 01H7WPYJVAWJ9BFYBXM6DJ3V22=why-doesnt-the-onelink-url-open-the-app-or-deep-link-existing-users fallback-urls=%ED%8F%B4%EB%B0%B1-url 01H7WPYJVACCGVJD1Z7ZPVG2SQ=%ED%8F%B4%EB%B0%B1-url 01H7WPYJVAHXE4M12X94T9C7A5=%EC%98%88%EC%8B%9C 01H7WPYJVAEMX54GZAX166FPS7=%EC%B0%B8%EA%B3%A0-1 forced-deep-linking=%EA%B0%95%EC%A0%9C-%EB%94%A5%EB%A7%81%ED%82%B9 01H7WPYJVA1W3HYYJJFQM01136=%EA%B0%95%EC%A0%9C-%EB%94%A5%EB%A7%81%ED%82%B9 01H7WPYJVAWSD03E141SZEN2J9=why-does-my-onelink-url-open-a-blank-page-in-chrome 01H7WPYJVAV93G4EGDH2A91XMP=can-i-use-onelink-for-redirection-on-brave 01H7WPYJVAJQ6FKWDK8MNZAZT3=do-onelink-custom-links-take-longer-to-load-than-other-links 01H7WPYJVAX7P2YCBV1K1DCGEJ=how-can-i-record-the-cost-per-install-when-using-onelink 01H7WPYJVAEFX5306YA4GA45FW=%EC%98%88%EC%8B%9C-1 01H7WPYJVAQZJQYX3H5V8YTC27=how-can-i-prevent-parameter-forwarding-on-redirections 01H7WPYJVAYVK3A77Q35H1ENKF=how-can-i-remove-appsflyer-pid-and-c-parameters-when-forwarding-while-keeping-all-other-parameters-on-redirection-urls 01H7WPYJVA89118V5Y2DSM67Y4=are-singleplatform-custom-links-still-available 01H7WPYJVANDKXGFKYXZ6CKHSF=can-i-change-the-short-url-id-after-saving-a-link 01H7WPYJVAC2WXXY43WEYKVPYP=can-i-wrap-and-shorten-onelink-custom-links 01H7WPYJVANTMSMGZ6VP36DTV1=can-i-use-onelink-custom-links-in-emails 01H7WPYJVAE0TSRPPTD21X9Q4V=how-do-users-get-redirected-to-their-regional-app-store 01H7WPYJVA4W7YFMQD4HEE313P=why-isnt-my-onelink-url-redirecting-users-to-the-specified-domain h_01JJRP42HGK2YAQ902ADS178GD=why-do-i-get-the-app-you-are-looking-for-is-unavailable-error h_01HZKZRQW63QBJEB7HPDPAZMG1=why-is-my-monelinkme-shortlink-not-working h_01HAKSWWMSHVW9KFWA34XGXWN2=can-i-manually-switch-between-the-branded-domain-and-its-onelink-subdomain-in-an-existing-link onelink-parameter-faq=%EC%9B%90%EB%A7%81%ED%81%AC-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0-faq 01H7WPYJVAGRVWHRVMZVQG1ZVE=%EC%9B%90%EB%A7%81%ED%81%AC-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0-faq 01H7WPYJVBCS3JZ98FYMAPY2YT=what-parameters-are-mandatory-for-onelink-custom-links 01H7WPYJVBCD7GG37JZTF919YQ=can-parameters-be-appended-to-the-short-url 01H7WPYJVB15Q3YAVJ8M7EQ1FW=%EC%98%88%EC%8B%9C-2 01H7WPYJVBNTKJM3F72ZEZG32Z=what-custom-media-source-names-can-i-use 01H7WPYJVB25VGB37D3DZ2J786=what-attribution-parameters-can-be-added-to-a-onelink 01H7WPYJVBSQBR8E9NY0GJ3APT=are-custom-parameters-added-to-onelink-custom-links-available-in-raw-data 01H7WPYJVB3CCB838A7N6K932G=are-parameter-names-case-sensitive integrated-partner-faq=%EC%97%B0%EB%8F%99-%ED%8C%8C%ED%8A%B8%EB%84%88-faq 01H7WPYJVB8ZZSKFT1V01EN6QF=%EC%97%B0%EB%8F%99-%ED%8C%8C%ED%8A%B8%EB%84%88-faq 01H7WPYJVBCQNPTEZPM8KFE6YX=can-i-use-onelink-in-social-apps-unpaid 01H7WPYJVBTBQKK50JR179S7MW=can-i-use-onelink-with-ad-networks-paid 01H7WPYJVBJ0DX0MZPGXYF76EP=%EC%A4%91%EC%9A%94 01H7WPYJVBB9KJRZQTFZDG7NDK=%EC%98%88%EC%8B%9C-3 01H7WPYJVB60DFMHN8PCVFC5S9=how-can-i-solve-the-ios-applaunching-issue-from-social-media-apps 01H7WPYJVB94NGD94MW4HYDB5S=can-i-use-onelink-on-instagram 01H7WPYJVBT5PJHVAFD1TY6CDY=can-i-use-onelink-for-redirection-on-wechat 01H7WPYJVB05C8BXKRG0WGBJ8P=why-are-android-users-with-the-app-installed-being-redirected-to-a-web-url-and-not-into-the-app-when-they-click-a-link-on-facebook-webview testing-faq=%ED%85%8C%EC%8A%A4%ED%8A%B8-faq 01H7WPYJVC1PJJDA0GGT1DVVCF=%ED%85%8C%EC%8A%A4%ED%8A%B8-faq 01H7WPYJVCQ89S3R4X1111TRGZ=how-can-i-ab-test-the-social-app-landing-page 01H7WPYJVC20TXWKRB89XFTK1N=how-can-i-bypass-the-app-selection-dialog deep-linking-faq=%EB%94%A5%EB%A7%81%ED%82%B9-faq 01H7WPYJVCTM39HKCG9JN03BN6=%EB%94%A5%EB%A7%81%ED%82%B9-faq 01H7WPYJVCZMRN53QG5JNSB8MP=what-deep-linking-methods-should-be-implemented 01H7WPYJVC6BXRJGTJBY6KG8JX=can-a-uri-scheme-af_dp-parameter-be-used-for-deep-linking 01H7WPYJVCVCVWHJW4RH85KC40=ios-14-faq 01H7WPYJVCFANQQ9T27M2YGGBD=does-onelink-deep-linking-work-for-ios-14 01H7WPYJVCBC9YMBQ6TV1B2SBV=does-onelink-deferred-deep-linking-work-for-ios-14" />
