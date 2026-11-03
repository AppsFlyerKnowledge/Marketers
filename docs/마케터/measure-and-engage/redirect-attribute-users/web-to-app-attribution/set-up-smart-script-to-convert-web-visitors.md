---
title: 웹 방문자를 앱 유저로 전환하기 위한 Smart Script 설정
metadata:
  keywords:
    - OneLink
    - Advertisers
    - Developers
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2021-12-13T09:57:23Z'
  edited_at: '2026-10-26T14:50:43Z'
  id: 4413588932241
  locale: ko
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/ko/articles/4413588932241
---
> **한눈에 보기:** OneLink Smart Script를 설정하여 모든 소스에서 온 모바일 웹 사이트 방문자를 모바일 앱 사용자로 전환하고 어트리뷰트합니다.

![7901_Smart_Script_flow_1920x1080_2__1_.png](https://files.readme.io/5181971c27e89974a86afeb83f48eb5c127b64765334bc3b5644ed47adb974e8-30193884510225.png)

## 설정

OneLink Smart Script는 두 가지 버전이 있습니다.

**OneLink Smart Script V2(권장)**: OneLink Smart Script를 처음 설정하는 경우 이 버전을 사용하는 것이 좋습니다. 개발자 지원 없이 앱스플라이어 UI에서 생성할 수 있습니다. 개발자가 필요하다 하더라도 작업이 어렵지 않습니다. 또한 Google 태그 관리자를 사용하여 설정할 수도 있습니다. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_script_v2">개발자 지침 참조</Anchor>

<Anchor target="_blank" href="/marketers/ko/docs/legacy-onelink-smart-script-v1-setup">**OneLink Smart Script V1(레거시)**</Anchor>: Onelink Smart Script를 이미 설정한 경우 이 버전의 설명서를 사용하여 스크립트를 유지 관리하고 편집하세요. **노트**: 필수 사항은 아니지만 OneLink Smart Script를 사용하여 <Anchor target="_blank" href="https://www.appsflyer.com/glossary/view-through-attribution/">뷰-쓰루 어트리뷰션</Anchor>을 제대로 얻으려면 V2로 마이그레이션하는 것이 좋습니다.

### OneLink Smart Script 설정

Smart Script를 설정하려면 다음 중 하나를 수행하세요.

* 웹사이트에 스크립트를 내장합니다.
* Google 태그 매니저를 사용합니다.

#### 작업 범위

**관련 담당자**

* **광고주**:
  * 수신 URL을 처리하는 스크립트의 [인수](/docs/set-up-smart-script-to-convert-web-visitors#arguments)를 기반으로 발신 URL에 포함할 내용을 결정합니다. 이는 수신 URL을 조작하거나 특정 값을 강제 적용하여 송신 URL에 추가되는 어트리뷰션 및 딥링킹 데이터를 결정합니다.
  * 앱스플라이어 UI에서 Smart Script를 생성합니다.
  * 모바일 웹 사이트로 연결되는 모든 캠페인에 스크립트가 작동하는 파라미터를 포함한 수신 URL이 있는지 확인합니다.
  * <Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-onelink-smart-script/examples/test_page.html">Smart Script를 테스트합니다</Anchor>.
* **웹 개발자**:
  * 스크립트가 작동하려는 모바일 사이트/페이지에서 실행되는지 확인합니다.
  * 예를 들어 웹 사이트의 CTA 아래에 링크로 배치하기 위해 결과 값을 필요에 따라 사용합니다.
  * 스크립트를 사용하여 QR 코드를 생성하는 데 필요할 수 있습니다.
  * 스크립트에 고급 인수를 수동으로 추가하는 데 필요할 수 있습니다.

**선행 조건**

* 최소 한 개 이상의 앱이 등록된 앱스플라이어 계정
* [OneLinkURL 파라미터](/docs/set-up-smart-script-to-convert-web-visitors#arguments) 값으로 사용될 <Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template#원링크-템플릿-만들기">OneLink 템플릿</Anchor>

<div id="how-to-create-a-onelink-smart-script" />

<Accordion title="OneLink Smart Script 만들기">

**OneLink Smart Script를 만드려면:**

1. 앱스플라이어 사이드 메뉴에서 **참여** > **웹-to-앱** > **Smart Script**로 이동합니다.
2. ***신규 사용자***
   1. ***시작하기** 버튼을 클릭합니다.*
   2. *4단계 이후부터 수행합니다.*
3. 페이지 맨 위에 있는 **+ 새 Smart Script 버튼**을 클릭합니다.
4. 화면상의 지침에 따라 Smart Script 이름을 지정하세요.
5. 스크립트의 기반이 될 OneLink 템플릿을 선택하세요. 템플릿에는 기본 리디렉션 설정이 포함되어 있습니다.
6. 발신 URL에 포함되어야 하는 파라미터를 매핑합니다. 이러한 파라미터는 수신 URL 파라미터에 기반합니다. **참고**: 미디어 소스(pid) 파라미터는 필수입니다.
   1. 매핑할 발신 파라미터/디멘션을 선택합니다.  
      변경할 수 없는 앱스플라이어 파라미터 이름인 경우도 있지만 어떤 경우에는 사용자의 파라미터 이름을 입력해야 합니다.
   2. 다음 중 하나를 기반으로 발신 파라미터의 값을 결정하고 구성합니다.
      * 수신 URL 파라미터: 발신 URL 파라미터로 대체할 하나 이상의 가능한 수신 URL 파라미터를 나열합니다. 수신 URL 파라미터의 값은 발신 URL 파라미터의 값이 됩니다.
        * 예: any\_param\_name, utm\_param\_name. 수신 URL에 utm\_param\_name이 있는 경우 값이 선택한 발신 URL 파라미터의 값으로 사용됩니다.
        * Smart Script는 파라미터 목록을 왼쪽에서 오른쪽으로 검색하고 첫 번째 일치 항목을 발신 파라미터 URL에 매핑합니다.
        * 개발자는 이 파라미터 목록을 키로 참조합니다.
      * 기본값: 수신 URL 파라미터를 찾을 수 없거나 수신 URL 파라미터를 나열하지 않은 경우 발신 파라미터 값에 대해 원하는 기본값을 입력합니다.
        * 예: 발신 파라미터의 경우 수신 URL 파라미터가 any\_paramname, utm\_paramname을 나열하는 경우 목록에 파라미터가 모두 없으면 기본값이 발신 파라미터 값으로 사용됩니다.
      * 값 재정의: 대체할 발신 URL 값과 함께 수신 URL에서 값을 하나 이상 구성합니다.
        * 예: 캠페인 파라미터의 경우 수신 URL의 값이 campaign\_name이면 발신 URL의 값을 new\_campaign\_name으로 변경할 수 있습니다.
   3. [선택 사항] **+ 새 파라미터**를 클릭하여 추가 파라미터를 매핑합니다. 사용할 수 있는 모든 [추가 인수](/docs/set-up-smart-script-to-convert-web-visitors#arguments) (파라미터 구성)를 참조하십시오.
7. [선택 사항] URL 파라미터 매핑 섹션에서 확인되지 않은 자연 검색 트래픽의 미디어 소스를 자동으로 설정하려면, **웹** **리퍼러 매핑** 섹션 하위의 **오가닉 검색 설치 미디어 소스**를 활성화하세요. [더 알아보기](#seo-referrer-mapping)
8. 웹사이트에서 Smart Script를 구현하는 방법을 선택하세요.
   * **웹사이트에 스크립트를 내장합니다.**
   * **Google Tag Manager를 사용합니다.**
9. **검사**를 클릭하여 <Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-onelink-smart-script/examples/test_page.html">Smart Script 검사 페이지</Anchor>에서 스크립트를 테스트합니다. 올바른 발신 URL이 생성되었는지 확인합니다.
10. 클릭
    1. **저장** 하여 변경 내용을 저장합니다.
    2. **저장 및 생성** 을 클릭하여 스크립트를 저장 및 생성합니다.
       1. **스크립트 다운로드**를 클릭합니다.
11. 웹사이트에 스크립트를 포함하도록 선택한 경우: 웹 개발자에게 스크립트를 보내 구현하고 생성된 발신 URL로 수행할 작업을 알려줍니다. 예를 들어 모바일 사이트의 CTA 버튼 아래에 배치하거나 데스크톱 사이트에 QR 코드를 제시합니다. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script-v2web-to-app-url-generator#embed-the-script-in-your-website">개발자 가이드</Anchor>
12. Google 태그 관리자를 사용하도록 선택한 경우:
    1. Google 태그 관리자에서 새 태그를 만들고 태그 이름을 지정하고 **태그 설정**을 클릭하고 **사용자 지정 HTML**을 선택합니다.
    2. HTML 상자에 생성된 Smart Script 코드를 붙여넣습니다.
    3. **트리거**를 클릭하고 새 트리거를 만들고 이름을 지정한 다음 **트리거 설정**(예: 모든 페이지 보기)을 선택합니다. <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/7679319?hl=en&ref_topic=7679108">자세한 내용은 GTM 문서를 참조하십시오</Anchor>
    4. **저장**을 클릭합니다.
    5. 웹 개발자에게 생성된 발신 URL로 수행할 작업을 알려주세요. 예를 들어 모바일 사이트의 CTA 버튼 아래에 배치하거나 데스크톱 사이트에 QR 코드를 제시합니다. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script-v2web-to-app-url-generator#use-google-tag-manager">개발자 가이드</Anchor>
13. 저장된 스크립트는 [드롭다운 메뉴](/docs/set-up-smart-script-to-convert-web-visitors#how-to-edit-or-delete-a-script)에서볼 수 있습니다.

> 🚧 **중요!**
>
> 스크립트를 업데이트 할 때마다 다시 구현해야합니다.

</Accordion>

<div id="how-to-edit-or-delete-a-script" />

<Accordion title="스크립트를 편집 및 삭제">

**스크립트를 편집하거나 삭제하는 방법**

1. <Image alt="Down_arrow.jpg" src="https://files.readme.io/a82023665721be681f985548857c4c329f626435780bb1bff7a3821b32b69078-42045468433041.jpg" width="28px" />Smart Script 이름 옆에 있는  
    드롭다운 화살표를 클릭합니다.여기에서 저장된 모든 스크립트를 볼 수 있습니다.  

   <Image alt="Script_steps.jpg" src="https://files.readme.io/824c042dc23acaa14b360ce8cd792cfc2e85ee3c9c95e3fa694f96badfeb1fc2-42045468432657.jpg" width="1732px" />
2. 편집하려는 스크립트 옆에 있는 펜 아이콘을 클릭합니다.
   1. [OneLink Smart Script를 만드는 방법](/docs/set-up-smart-script-to-convert-web-visitors#onelink-smart-script-설정)을 따르세요.
3. 휴지통 아이콘을 클릭하여 Smart Script를 삭제합니다.

> 🚧 **중요!**
>
> 스크립트를 업데이트 할 때마다 다시 구현해야합니다.

</Accordion>

<div id="how-to-duplicate-a-script" />

<Accordion title="스크립트를 복제">

**스크립트를 복제하려면:**

1. 복제하려는 Smart Script로 이동하세요.
2. 상단 배너의 복제 버튼 <Image alt="SmartScript_duplicate.jpg" src="https://files.readme.io/ec05ea217331b588dc7033984287d46b61a37e41510546b67a0046ea281e0979-42045454920721.jpg" width="21px" />을 클릭합니다.
3. [OneLink Smart Script만드는 방법](/docs/set-up-smart-script-to-convert-web-visitors#onelink-smart-script-설정)을 따르세요.

</Accordion>

<div id="argument-structure" />

<Accordion title="인수 구조">

OneLink Smart Script는 인수를 사용하여 수신 URL의 파라미터와 스크립트에 정의된 인수를 기반으로 송신 URL을 생성합니다. afParameters 인수는 어트리뷰션과 딥링크에 사용되는 여러 하위 인수(파라미터)로 구성된 구조를 가집니다. 각 인수는 이어지는 표에 기술된 바와 같이 키, 오버라이드 값, 기본값을 포함하는 구조(개발자들 사이에서는 구성 객체로 불림)로 이루어져 있습니다.

| 인수 | 설명 | 예시 |
| --- | --- | --- |
| 수신 URL 파라미터(개발자가 키로 참조) | <ul><li>문자열 목록</li><li>스크립트가 찾는 수신 URL에서 가능한 파라미터(등) 목록이며, 이 값은 송신 URL에 값으로 배치됩니다.</li><li>스크립트는 왼쪽에서 오른쪽으로 검색하며 첫 일치 항목에서 검색을 중단합니다.</li></ul> | <ul><li>예: ['in\_channel', 'utm\_channel']</li><li>스크립트의 채널 파라미터의 경우 스크립트는 수신 링크에서 in\_channel을 검색하고 이 값을 채널 값으로 사용합니다.</li></ul> |
| 기본값 | <ul><li>문자열</li><li>"폴백" 값이 무엇이길 원하는지 설명하세요.</li><li>키 목록에서 파라미터를 찾을 수 없는 경우 송신 URL에 defaultValue 값이 사용됩니다.</li><li>비어 있는 키 목록을 전달하여 기본값을 강제 실행할 수 있습니다.</li></ul> | 예: ['web\_video']<br /><br />스크립트의 채널 파라미터의 경우 in\_channel 파라미터를 찾을 수 없으면 web\_video가 채널 값으로 사용됩니다. |
| 재정의 값 | <ul><li>사전 \{string: string\}</li><li>발신 링크에서 변경하려는 값의 경우 바꾸려는 값과 함께 수신 URL의 값을 나열합니다.</li><li>이 스크립트는 수신 URL의 파라미터 값을 사용자가 정의한 값으로 바꿉니다.</li></ul> | 예: \{'video': 'video\_new'\}<br /><br />스크립트의 채널 파라미터의 경우, 수신 값이 비디오일 때마다 스크립트는 발신 링크에서 video\_new로 변경합니다. |

</Accordion>

<div id="arguments" />

<Accordion title="인수(파라미터 및 값)">

OneLink Smart Script는 인수를 사용하여 수신 URL의 파라미터와 스크립트에 정의된 인수를 기반으로 발신 URL을 생성합니다.

#### Smart Script를 구현하기 위한 인수(파라미터 및 값)

<table><thead><tr><th colspan="2">인수</th><th>참고</th><th>응답 기록(사용자 또는 사용자의 개발자가 사용)</th></tr></thead><tbody><tr><td colspan="2">OneLink URL(필수)</td><td><ul><li>OneLink 템플릿 도메인 + 템플릿 ID를 제공합니다. <strong>노트:</strong> OneLink 사용자정의 링크 URL이 아닙니다!</li><li>예: <strong>yourbrand.onelink.me/A1b2</strong> </li><li>브랜드 도메인 예: <strong>click.yourbrand.com/A1b2</strong> </li></ul></td><td> </td></tr><tr><td rowspan="9"><p>afParameters</p><p>(필수)</p></td><td><p>mediaSource</p><p>(필수)</p></td><td><ul><li>미디어 소스의 설정 개체.</li><li>예:<ul><li>키: ['incoming_mediasource’' 'utm_source']</li><li>기본값: ['any_source']</li><li>재정의 값: `{twitter: 'twitter_int', orig_src: 'new_src'}</li></ul></li></ul></td><td><p>키:</p><p>기본값:</p><p>재정의 값:</p></td></tr><tr><td>campaign</td><td><ul><li>캠페인의 설정 개체.</li><li>예:<ul><li>키: ['incoming_campaign', 'utm_campaign']</li><li>기본값: ['any_campaign_name']</li><li>재정의 값: {campaign_name: 'new_campaign_name'}</li></ul></li></ul></td><td><p>키:</p><p>기본값:</p><p>재정의 값:</p></td></tr><tr><td>channel</td><td><ul><li>채널의 설정 개체.</li><li>예:<ul><li>키: ['incoming_channel', 'utm_channel']</li><li>기본값: ['any_video']</li><li>재정의 값: {video: 'new_video'}</li></ul></li></ul></td><td><p>키:</p><p>기본값:</p><p>재정의 값:</p></td></tr><tr><td>ad</td><td><ul><li>광고의 설정 개체.</li><li>예:<ul><li>키: ['incoming_ad', 'utm_ad']</li><li>기본값: ['any_ad_name']</li><li>재정의 값: {ad_name: 'new_ad_name'}</li></ul></li></ul></td><td><p>키:</p><p>기본값:</p><p>재정의 값:</p></td></tr><tr><td>adSet</td><td><ul><li>광고 세트의 설정 개체.</li><li>예:<ul><li>키: ['incoming_adset', 'utm_adset']</li><li>기본값: ['any_ad_name']</li><li>재정의 값: {adset_name: 'new_adset_name'}</li></ul></li></ul></td><td><p>키:</p><p>기본값:</p><p>재정의 값:</p></td></tr><tr><td>deepLinkValue</td><td><ul><li> <strong>deep_link_value</strong>의 설정 개체.</li><li>예:<ul><li>키: ['product_id', 'page_name']</li><li>기본값: 'new_offers_page'</li><li>재정의 값: {twenty_percent_off: 'thirty_percent_off'}</li></ul></li></ul></td><td><p>키:</p><p>기본값:</p><p>재정의 값:</p></td></tr><tr><td>afSub1-5</td><td> <strong>af_sub[1-5]</strong>의 설정 개체.</td><td><p>키:</p><p>기본값:</p><p>재정의 값:</p></td></tr><tr><td>googleClickIdKey</td><td> <a href="https://support.google.com/google-ads/answer/9744275?hl=en" target="_blank">GCLID</a>를 전달하는 파라미터를 호출할 내용을 설명하세요.<br/><strong>노트</strong>! <span>앱스플라이어 로우 데이터 리포트에 표시하려면 파라미터가 <strong>af_sub[1-5]</strong> 중 하나여야 합니다.</span> </td><td> </td></tr><tr><td> <span>기타(사용자정의) 쿼리 파라미터</span><br/> </td><td><ul><li>어트리뷰션 또는 딥링크를 위해 발신 OneLink URL에 포함할 기타 파라미터를 해당 설정 개체와 함께 나열합니다.</li><li>사용자정의 파라미터의 이름은 개발자에 의해 설정 개체에 paramKey로 나열됩니다.<span></span> </li><li>예:<ul><li>paramKey: 'deep_link_sub1'</li><li>키: ['page_id']</li><li>기본값: 'page1'</li><li>재정의 값: {page12: 'new_page12'}`</li></ul></li></ul></td><td><p>파라미터 키:</p><p>키:</p><p>기본값:</p><p>재정의 값:</p></td></tr></tbody></table>

</Accordion>

<div id="advanced-arguments" />

<Accordion title="고급 인수">

다음 표에서는 기술적 이해도가 높은 마케터나 개발자가 Smart Script에 구현할 수 있는 인수들을 설명합니다.

#### Smart Script에서 구현을 위한 고급 인수(파라미터 및 값)

<table><thead><tr><th colspan="2">인수</th><th>참고</th><th>응답 기록(사용자 또는 사용자의 개발자가 사용)</th></tr></thead><tbody><tr><td colspan="2"> <br/>referrerSkipList</td><td><ul><li>특정 클릭(예: Twitter 또는 Facebook)의 HTTP 리퍼러에서 발견될 경우 Smart Script가 <code>null</code>을 반환하도록 만드는 문자열 목록. 이는 클릭수가 이미 보고된 X 광고 및 Meta 광고와 같은 SRN에 유용할 수 있습니다.</li><li>이 인수를 구현하면 스크립트가 OneLink URL을 생성하지 않습니다.</li></ul></td><td> </td></tr><tr><td colspan="2">urlSkipList</td><td><ul><li>특정 클릭(예: af_r)에 대한 URL의 문자열 목록으로, 발견될 경우 Smart Script가 <code>null</code>을 반환하게 됩니다. 이 기능은 af_r을 포함된 앱스플라이어 어트리뷰션 링크를 사용하여 사용자를 모바일 웹사이트로 리디렉션할 때 최초 클릭했던 데이터가 손실되지 않도록 하려는 경우에 유용할 수 있습니다.</li><li>이 인수를 구현하면 스크립트가 OneLink URL을 생성하지 않습니다.</li></ul></td><td> </td></tr><tr><td colspan="2">SEO</td><td><ul><li>활성화되어 있고 <strong>URL 파라미터 매핑</strong> 섹션에서 미디어 소스가 확인되지 않은 경우, 웹 리퍼러 URL을 기반으로 사용자가 검색 엔진을 통해 유입되었는지 확인한 뒤 그에 맞춰 미디어 소스를 설정합니다. (버전 2.10.3부터 사용 가능)</li></ul></td><td> </td></tr></tbody></table>

</Accordion>

## 활용 사례

다음 섹션에서는 일반적인 캠페인/미디어 소스 시나리오에서 Smart Script 사용 사례를 제공합니다.

<div id="utm-parameters" />

<Accordion title="UTM 파라미터">

**UTM 파라미터에 대한 스크립트를 설정하는 방법**:

1. 수신 URL(예: **utm\_source** 및 **utm\_campaign**)에 UTM 파라미터 목록을 작성하고 이를 발신 URL의 파라미터(예: **media\_source** 및 **campaign**)와 매치시키세요.
2. 웹 개발자에게 이 [인수 목록](/docs/set-up-smart-script-to-convert-web-visitors#arguments)에 제공하세요.

**결과**: 수신 파라미터의 값(**utm\_source** 및 **utm\_campaign**)은 발신 링크의 (**media\_source** 및 **campaign**) 파라미터 값을 채우는 데 사용됩니다.

</Accordion>

<div id="google-ads-gclid" />

<Accordion title="Google Ads GCLID">

Google Ads 캠페인의 일반적인 설치 어트리뷰션 프로세스(GCLID 파라미터를 사용)에서는 광고를 클릭한 사용자가 앱스토어 페이지 URL로 리디렉션되어야 합니다.

이 경우, Google Ads에서 리드를 웹/랜딩 페이지로 리디렉션하므로, 스크립트가 Google Ads 설치 캠페인 URL에서 GCLID 파라미터를 가져와 출력 URL에 넣습니다. Smart Script 버전 2.9.0부터는 GCLID, WBRAID, GBRAID 파라미터(사용 가능할 경우)가 Smart Script에 의해 생성된 목적지 페이지의 URL에 “그대로” 자동 추가됩니다.

또한, 클릭 ID를 다른 발신 파라미터 (**af\_sub[1-5]**)에 매핑하여 앱스플라이어 로우 데이터 보고서에서 사용할 수 있습니다.

**참고!**

* 이것은 설치 캠페인에 적용됩니다. 리인게이지먼트 캠페인을 의미하는 비 ACI 검색 캠페인의 경우 Smart Script트 출력에도 불구하고 Google이 미디어 소스로 어트리뷰션될 수 있습니다.
* GCLID를 찾은 경우, 스크립트는 들어오는 파라미터 키워드를 찾습니다. 찾은 경우 발신 URL에 키워드 값을 af\_keywords의 값으로 삽입합니다.

**전제 조건**: Google 대시보드에서, <Anchor target="_blank" href="https://support.google.com/analytics/answer/1033981?hl=en">자동 태깅을 활성화합니다</Anchor>.   
자동 태깅이 활성화된 상태에서, URL은 *GCLID* 파라미터를 포함합니다.

**Google Ads GCLID에 대한 스크립트를 설정하는 방법**:

1. 발신 URL에서 GCLID를 포함할 파라미터를 선택합니다.  
   모범 사례: 데이터가 앱스플라이어 로우 데이터 리포트에 표시되도록 **af\_sub[1-5]** 를 선택합니다.
2. [인수 목록](/docs/set-up-smart-script-to-convert-web-visitors#arguments)을 웹 개발자에게 제공하세요. 그 결과, 발신 URL에서 GCLID는 **af\_sub[1-5]** 파라미터의 값으로 반영됩니다.

**Google Ads에 이러한 설치에 대해 알리려면:**

**권장 사항:** <Anchor target="_blank" href="/marketers/ko/docs/google-ads-adwords-create-web-based-campaigns">Google 웹 연동</Anchor>을 설정하세요. 이 연동은 설치에 대한 자동 포스트백을 지원합니다.

**연동이 없다면:**

1. 각 설치에 대해 CSV 또는 푸시 API를 통해 실시간으로 파라미터 **af\_sub[1-5]** 에서 GCLID 데이터를 가져옵니다.
2. <Anchor target="_blank" href="https://support.google.com/adwords/answer/7014069">수동으로</Anchor> 또는 <Anchor target="_blank" href="https://developers.google.com/google-ads/api/docs/start">Google Ads API</Anchor>를 통해 GCLID 데이터를 Google에 업로드합니다.

> 📘 **참고**
>
> GCLID 솔루션은 Google이 공식적으로 지원하거나 권고하지 않습니다. Google이 GCLID 파라미터 지원을 중단할 경우, 해당 변경 사항을 지원하도록 스크립트를 수정할 예정입니다. 문서 상단의 **팔로우** 버튼을 클릭해 이 문서를 팔로우하면, 문서나 첨부된 스크립트에 업데이트가 있을 때 알림을 받을 수 있습니다.

</Accordion>

<div id="facebook-click-id" />

<Accordion title="Facebook FBCLID">

Meta 광고는 FBCLID라는 클릭 ID를 전달합니다. Smart Script 버전 2.8.1부터는 사용 가능한 경우 FBCLID가 Smart Script에서 생성된 발신 URL로 원본 그대로 자동 전달됩니다. 클릭 ID를 다른 발신 파라미터에 매핑하여 앱스플라이어 로우 데이터 리포트에서 확인할 수도 있습니다.

**FBCLID를 다른 파라미터에 매핑하도록 스크립트를 설정하려면:**

1. 발신 URL에서 FBCLID를 포함할 파라미터를 선택합니다. 모범 사례: 데이터가 앱스플라이어 로우 데이터 리포트에 표시되도록 **af\_sub[1-5]** 를 선택합니다.
2. [인수 목록](/docs/set-up-smart-script-to-convert-web-visitors#arguments)을 웹 개발자에게 제공하세요. 그 결과, 발신 URL에서 FBCLID는 **af\_sub[1-5]** 파라미터의 값으로 반영됩니다.

</Accordion>

<div id="tiktok-ttclid-x-twclid-and-snapsccid" />

<Accordion title="TikTok(ttclid), X(twclid), 및 Snap(ScCid)">

TikTok, X(구 Twitter) 및 Snap 광고 캠페인의 설치 어트리뷰션은 광고 클릭 시 추가되는 네트워크별 클릭 ID 파라미터에 의존하며, 이를 통해 설치 및 설치 후 이벤트를 해당 광고와 매칭합니다.

트래픽이 웹 페이지 또는 랜딩 페이지로 먼저 리디렉션될 때, 올바른 어트리뷰션을 보장하기 위해 클릭 ID가 보존 및 전달되어야 합니다. 이 경우 Smart Script는 수신된 클릭 ID 파라미터를 캡처하여 생성된 발신 URL에 추가합니다.

클릭 ID는 설치 시점에 캡처되며, 이후 해당 설치와 관련된 향후 이벤트에 사용됩니다.

Smart Script 버전 2.10.0부터는 사용 가능한 경우 다음 클릭 ID 파라미터가 Smart Script에서 생성된 발신 URL로 원본 그대로 자동 전달됩니다:

* TikTok: ttclid
* X(구 Twitter): twclid
* Snap: ScCid

이러한 클릭 ID를 af\_sub1-af\_sub5와 같은 다른 발신 파라미터에 매핑하여 앱스플라이어 로우 데이터 리포트에서 사용할 수 있도록 설정할 수도 있습니다.

다음 관련 웹 연동 문서를 확인하세요.

* <Anchor target="_blank" href="/marketers/ko/docs/tiktok-for-business-create-web-based-campaigns">TikTok</Anchor>
* <Anchor target="_blank" href="/marketers/ko/docs/snapchat-create-web-based-campaigns">Snap</Anchor>

</Accordion>

<div id="srns-owned-media-and-other-media-source-links" />

<Accordion title="SRN, 온드 미디어 및 기타 미디어 소스 링크">

Snapchat 또는 X Ads와 같은 <Anchor target="_blank" href="/marketers/ko/docs/self-reporting-networks-srns#앱스플라이어와-통합된-srn">SRN</Anchor>은 Google Ads 또는 Meta Ads와 같은 크로스 플랫폼과 다르게 작동합니다. 이러한 SRN의 캠페인은 사용자를 웹/랜딩 페이지로 유도하며, 파생된 모바일 사용자와 무관하게 클릭 리드에 따라 비용이 청구됩니다.

이러한 SRN의 경우 스크립트 설정은 온드 미디어 또는 사용할 수 있는 다른 미디어 소스의 링크에 대한 설정과 동일합니다.

**스크립트 설정 방법**:

1. 수신 링크에 있는 미디어 소스 및 캠페인 파라미터 이름의 목록을 작성하세요.
2. [인수 목록](/docs/set-up-smart-script-to-convert-web-visitors#arguments)을 웹 개발자에게 제공합니다.  
   SRN/미디어 소스 유형은 수신 URL의 미디어 소스 값이어야 하며 스크립트는 이 값을 찾아 웹/랜딩 페이지의 다운로드 버튼 뒤에 있는 발신 OneLink URL에서 **media\_source** 값으로 사용합니다. 발신 **media\_source**를 변경하려면 웹 개발자에게 제공하는 [인수 목록](/docs/set-up-smart-script-to-convert-web-visitors#arguments)에서 수신 media\_source 값과 재정의 media\_source 값을 제공하세요.

**결과**: 이러한 SRN/미디어 소스의 경우 미디어 소스의 값과 수신 링크의 캠페인 파라미터는 발신 링크의 **media\_source** 및 **campaign** 파라미터의 값을 채우는 데 사용됩니다.

> 📄 **예시**
>
> **수신 URL**: https://hotel.me/incoming_mediasource=twitter&incoming_campaign=big_social
>
> **발신 URL**: https://hotel.onelink.me/Ac4G?pid=twitter&c=big_social

</Accordion>

<div id="appsflyer-attribution-links" />

<Accordion title="앱스플라이어 어트리뷰션 링크">

앱스플라이어 어트리뷰션 링크는 미디어 소스가 클릭 광고 네트워크일 때 사용할 수 있습니다. 앱스플라이어에서 이러한 링크를 설정할 때 웹 캠페인-to-앱 어트리뷰션을 위해 원하는 URL 경로가 포함된 **리디렉션 URL 경로(af\_r)** 파라미터를 모바일 웹사이트에 추가할 수 있습니다. 스크립트가 발신 OneLink URL을 생성하지 않도록 할 수 있으며, 그러면 최초 클릭에 의한 데이터의 일부가 손실될 수 있습니다.

**조치:** **urlSkipList** 인수를 사용하여 **af\_r** 파라미터를 나열합니다.

**결과**: Smart Script가 수신 링크에서 **af\_r** 파라미터를 찾으면 Smart Script는 발신 URL을 생성하지 않으며 개발자는 발신 URL로 배치할 링크를 결정하고 구현해야 합니다.

> 📄 **예시**
>
> **수신 URL**: https://app.appsflyer.com/id123456789?pid=click_ad_network_int&c=orlando&af_r=hotel.me
>
> **발신 URL**: 발신 URL은 없습니다.

</Accordion>

<div id="web-referrer-mapping" />

<Accordion title="웹 리퍼러 매핑">

웹 리퍼러 매핑을 사용하면 사용자가 웹사이트에 도달한 페이지(예: 오가닉 검색 결과)를 학습할 수 있으므로 Smart Script 웹-to-앱 흐름에서 발생하는 설치 및 리인게이지먼트를 분석하기 위해 원하는 대로 데이터를 보강할 수 있습니다.

랜딩 페이지 또는 웹사이트 HTTP 헤더 [`리퍼러`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referer) 필드에서 이 정보를 수집하도록 Smart Script를 설정할 수 있습니다. 이 필드에는 사용자가 웹페이지로 연결되는 링크를 클릭한 페이지의 기본 URL이 포함됩니다.

**웹 리퍼러를 수집하도록 스크립트를 설정하려면**

1. **Smart Script** 페이지 열기
2. **웹 리퍼러 매핑** 영역 섹션에서 웹 리퍼러 값에 대한 발신 URL 파라미터 키를 선택합니다.
   * af\_channel - 파라미터는 대시보드 및 로우 데이터에서 사용할 수 있습니다.
   * af\_sub1-5 - 파라미터는 **af\_sub1-5** 열 아래의 로우 데이터와 **original URL** 열에서 사용할 수 있습니다.
   * 사용자 지정 파라미터 - 파라미터 이름과 값으로 구성됩니다. 파라미터는 **원래 URL 열의** 로데이터로 표시됩니다.

Universial Links 및 App Links를 사용한 리인게이지먼트에 대한 오가닉 검색 어트리뷰션에 대해 알아보려면 <Anchor target="_blank" href="/marketers/ko/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">여기</Anchor>를 참조하세요.

</Accordion>

<div id="seo-referrer-mapping" />

<Accordion title="SEO 리퍼러 매핑">

**URL 파라미터 매핑** 섹션에서 아직 해결되지 않은 경우, 오가닉 검색 트래픽에 대한 미디어 소스를 자동으로 설정하도록 **오가닉 검색 설치 미디어 소스**를 켤 수 있습니다.

* 사용자의 웹 리퍼러가 지원되는 검색 엔진(예: google.com 또는 bing.com)과 일치하는 경우, Media Source는 일치하는 채널(예: google\_organic\_seo)로 설정됩니다.
* 일치하는 항목이 없는 경우, URL 파라미터 매핑에 설정된 **기본 값**이 사용됩니다.

</Accordion>

<div id="desktop" />

<Accordion title="데스크톱">

이 문서에 나오는 사용 사례 대부분은 모바일 기기를 사용하는 사용자입니다. 따라서 모바일 웹 사이트에서 앱 스토어로 안내되면 즉시 앱을 다운로드할 수 있습니다.

그러나 데스크톱 사용자 기기(데스크톱 또는 노트북)는 모바일 앱 다운로드와 호환되지 않으므로 앱 스토어로 즉시 전송되지 않습니다.

**데스크톱 사용자용 스크립트 설정 방법**:

* <Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template#원링크-템플릿-만들기">OneLink 템플릿</Anchor>에서 **데스크톱에서 링크가 클릭 되었을 때**에 대한 목적지 URL을 설정하세요. URL은 전용 웹/랜딩 페이지로 리디렉션되어야 합니다. 랜딩 페이지에는 사용자가 세부 정보를 입력하면 앱 다운로드 링크가 포함된 SMS나 이메일을 받을 수 있는 웹 폼이 포함될 수 있습니다. 웹 폼을 생성하고 스크립트에 해당 웹 폼의 URL을 제공하는 것은 사용자 선택사항입니다.

**결과**: 이 스크립트는 사용자가 사용하는 기기 또는 플랫폼을 감지합니다. 데스크톱인 경우 스크립트는 사용자를 전용 웹/랜딩 페이지로 리디렉션하는 나가는 원링크 URL을 생성합니다.

<Anchor target="_blank" href="/marketers/ko/docs/qr-to-app-conversion">데스크톱-to-앱 전환</Anchor>을 참조하세요.

</Accordion>

<div id="qr-codes" />

<Accordion title="QR 코드">

Smart Script는 링크가 있는 버튼 대신 웹 페이지에 QR 코드를 표시합니다. 

**QR 코드를 표시하는 방법:**

1. Smart Script를 설정할 때 Smart Script 2.6+를 사용해야 합니다.
2. 개발자에게 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script-v2web-to-app-url-generator#create-a-qr-code-with-the-smart-script-result">해당 가이드</Anchor>를 따라 Smart Script 결과로 QR 코드를 생성하도록 안내하세요.
3. [모범 사례] 개발자에게 다음을 전달합니다.
   * QR 코드 센터에 앱 로고를 추가하고 색상을 사용자 지정하여<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_script_v2#create-a-qr-code-with-the-smart-script-result">QR 코드를 사용자 지정합니다.</Anchor>
   * 사용자가 데스크톱에 있을 때는 QR 코드를 표시하고, 사용자가 모바일에 있을 때는 링크가 포함된 버튼을 표시하세요.

**결과**: 스크립트는 URL이 연결된 버튼 대신 QR 코드를 표시합니다.

> 📄 **예시**
>
> **수신 URL**:
>
> https://hotel.me/qr_code.html?incmp=gogo&inmedia=email
>
> **발신 URL**:
>
> https://hotel.onelink.me/LtRd/?af_js_web=true&af_ss_ver=2_1_0&pid=email&c=gogo
>
> **발신 QR 코드**:
>
> <Image alt="" src="https://files.readme.io/2f06149c901d8a97c2a544b8196e9afecbe3b3748ed8419a39c2dc5e3afa61ba-42045454923153.png" width="48.07%" />

</Accordion>

<div id="impressions" />

<Accordion title="노출">

OneLink Smart Script를 사용하여 웹사이트의 노출수를 계산할 수 있습니다. 그러려면 개발자가 모든 노출 함수를 콜 해야 합니다. 설치는 <Anchor target="_blank" href="/marketers/ko/docs/measure-view-through-engagements">뷰 쓰루 어트리뷰션</Anchor>을 통해 노출을 어트리뷰션합니다.

**참고**:

* 노출 수 집계는 클릭 수를 집계하는 일반적인 Smart Script 생성 URL 외에 추가로 수행됩니다. Smart Script를 사용하여 클릭수, 노출수 또는 둘 다를 계산할 수 있습니다.
* Smart Script를 통한 뷰 쓰루 어트리뷰션은 데스크톱이 아닌 모바일 기기에서만 작동합니다.

**노출에 대한 신규 설치 어트리뷰션(뷰-쓰루 어트리뷰션):**

1. Smart Script를 설정할 때 Smart Script 2.3 이상을 사용해야 합니다.
2. 개발자에게 Smart Script에서 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script-v2web-to-app-url-generator#fire-an-impression">노출 함수를 호출</Anchor>할 것을 요청합니다.
3. <Anchor target="_blank" href="/marketers/ko/docs/measure-view-through-engagements">뷰-쓰루 어트리뷰션이 켜져 있는지</Anchor> 확인하하세요.

> 🚧 **중요!**
>
> 2023년 2월 1일(Chrome 110 정식 버전 출시)부터 Google은 <Anchor target="_blank" href="https://developer.chrome.com/en/docs/privacy-sandbox/user-agent/">User-Agent 데이터를 축소</Anchor>하기 위한 몇 가지 변경 사항을 적용했습니다. OneLink Smart Script를 사용하여 <Anchor target="_blank" href="https://www.appsflyer.com/glossary/view-through-attribution/">뷰 쓰루 어트리뷰션</Anchor>을 올바르게 측정하려면 OneLink Smart Script 버전 2.3 이상을 사용해야 합니다.

</Accordion>

## 추가 정보

<div id="faq" />

<Accordion title="FAQ">

#### **사용자가 웹사이트 내 다른 페이지로 이동하는 경우에도 OneLink 링크 생성을 위한 수신 URL이 작동하나요?**

예. 수신 URL 파라미터는 브라우징 세션 기간 동안 저장되며 Smart Script로 생성된 원링크 링크의 발신 파라미터에 적용됩니다. 구현에 대한 자세한 내용은 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_script_v2#preserve-incoming-url-parameters-across-pages">개발자 허브를 참조하세요</Anchor>.

#### **Google Tag Manager를 통해 Smart Script를 구현할 때 오류가 발생하는 이유는 무엇인가요?**

앱스플라이어에서 Smart Script를 생성하고 이를 Google Tag Manager(GTM)에 삽입하려고 할 때 "JavaScript가 너무 깁니다"라는 오류가 표시되는 경우가 있습니다. 이 경우 GTM 태그를 삭제하고 새 태그를 만드십시오.

#### **나열되지 않은 파라미터를 추가할 수 있나요?**

예. OneLink Smart Script 페이지에서 +**새 파라미터 추가**를 클릭하여 추가 파라미터를 매핑합니다.

* 새 파라미터는 드롭다운에 나열되지 않은 사용자 지정 파라미터 또는 앱스플라이어 예약 파라미터일 수 있습니다.
  * 사용할 수 있는 모든 추가 인수 (파라미터 구성)를 참조하세요.
* 드롭다운에서 사용자 지정 옵션을 사용하고 파라미터를 **발신 URL 파라미터** 필드에 추가하세요.

예를 들어 is\_retargeting을 파라미터로 추가하려면 **매핑 대상** 필드에서 사용자 지정 파라미터를 선택한 다음 **발신 URL 파라미터** 필드에 is\_retargeting 파라미터를 선택합니다.

![Smart_Script_Custom.jpg](https://files.readme.io/5a09d18b01ece93bbb47667b676039c98742ebc3b88c5235ad92c7e44d5316b9-small-42045454926609.jpg)

#### **Adset 및 기타 파라미터가 드롭다운에 표시되지 않습니다.**

새 파라미터를 만들거나 추가할 때 브라우저에 있는 모든 광고 차단기를 끄는 것이 좋습니다. 때때로 광고 차단기는 '광고'라는 단어가 포함된 옵션을 제거합니다.

#### **Smart Script는 어떤 브라우저에서 작동하나요?**

Smart Script는 Javascript를 사용하므로 모든 브라우저에서 작동합니다.

</Accordion>

<div id="specs-and-limitations" />

<Accordion title="사양 및 제한 사항">

| **사양** | **참고** |
| --- | --- |
| URI 스킴 | 기존 사용자가 앱을 열 수 있도록 OneLink 템플릿에 URI 스킴이 설정되어 있더라도, Smart Script를 사용하여 생성된 링크의 경우 개발자가 URI 스킴이 포함된 af\_dp 파라미터를 URL에 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script-v2web-to-app-url-generator#set-additional-custom-parameters">사용자 지정 파라미터</Anchor>로 직접 추가해야 합니다. |
| **수신 URL에서**| Smart Script에서 쿼리 파라미터 앞에 해시('#') 기호('?' 기호로 표시)가 포함된 수신 URL을 처리할 때 문제가 발생합니다. 이러한 경우 Smart Script는 기본값으로 되돌아갑니다. |

</Accordion>

<div data-zendesk-anchors="setup=%EC%84%A4%EC%A0%95 h_01H95PGMNWR12KQ2P0KT8BBGEC=%EC%84%A4%EC%A0%95 set-up-onelink-smart-script=onelink-smart-script-%EC%84%A4%EC%A0%95 h_01H95PGMNW6N63XQ1EQSQSHHB2=onelink-smart-script-%EC%84%A4%EC%A0%95 scope-of-work=%EC%9E%91%EC%97%85-%EB%B2%94%EC%9C%84 h_01H95PGMNWPBRHSZBPMKNJ2PS6=%EC%9E%91%EC%97%85-%EB%B2%94%EC%9C%84 h_01H95PGMNWWYRRNVNTK31XYRN3=how-to-create-a-onelink-smart-script h_01H95PGMNW5HA4FWBFW7AR89AV=%EC%A4%91%EC%9A%94 h_01H95PGMNXZAES8DPJ1B4E1QV8=how-to-edit-or-delete-a-script h_01H95PGMNX5ZT7DPV2WBG0CTKB=%EC%A4%91%EC%9A%94-1 h_01H95PGMNXNT9C07B0YTS1KK82=how-to-duplicate-a-script h_01H95PGMNXWJ9V5JW9JEAHF81S=argument-structure h_01H95PGMNXR2HTV1EF07QVQB6W=arguments arguments-parameters-and-values-to-implement-the-smart-script::d4f6bf94=smart-script%EB%A5%BC-%EA%B5%AC%ED%98%84%ED%95%98%EA%B8%B0-%EC%9C%84%ED%95%9C-%EC%9D%B8%EC%88%98%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0-%EB%B0%8F-%EA%B0%92 h_01H95PGMNXPMCM73XT3GTDVAXJ=smart-script%EB%A5%BC-%EA%B5%AC%ED%98%84%ED%95%98%EA%B8%B0-%EC%9C%84%ED%95%9C-%EC%9D%B8%EC%88%98%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0-%EB%B0%8F-%EA%B0%92 h_01H95PGMNX4B8W84DHJR9T4CR2=advanced-arguments arguments-parameters-and-values-to-implement-the-smart-script=smart-script%EC%97%90%EC%84%9C-%EA%B5%AC%ED%98%84%EC%9D%84-%EC%9C%84%ED%95%9C-%EA%B3%A0%EA%B8%89-%EC%9D%B8%EC%88%98%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0-%EB%B0%8F-%EA%B0%92 h_01H95PGMNXCAHTTJATG75Y3TRN=smart-script%EC%97%90%EC%84%9C-%EA%B5%AC%ED%98%84%EC%9D%84-%EC%9C%84%ED%95%9C-%EA%B3%A0%EA%B8%89-%EC%9D%B8%EC%88%98%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0-%EB%B0%8F-%EA%B0%92 use-cases=%ED%99%9C%EC%9A%A9-%EC%82%AC%EB%A1%80 h_01H95PGMNXBPFFNE44YGGECBPR=%ED%99%9C%EC%9A%A9-%EC%82%AC%EB%A1%80 h_01H95PGMNX3W95JW47YQGSEYQ6=utm-parameters h_01H95PGMNXGZZEMZ6PMAB4XFQQ=google-ads-gclid h_01H95PGMNXZT08G8RTMMG6BQCJ=%EC%B0%B8%EA%B3%A0 h_01H95PGMNXHJXGB2QXH0YTB6Z0=facebook-click-id h_01KD5EZQFF23MYGXGJF1CF6VPT=tiktok-ttclid-x-twclid-and-snapsccid h_01H95PGMNXBKXFG9M169WG89TK=srns-owned-media-and-other-media-source-links h_01H95PGMNXZPB6CT3ZKJ2KMQ1J=%EC%98%88%EC%8B%9C h_01H95PGMNX8Q0BASSESVD06MXE=appsflyer-attribution-links h_01H95PGMNX741EJGPF9G2DS67N=%EC%98%88%EC%8B%9C-1 h_01HAS199KS0C0V3G41WGXTK4PF=web-referrer-mapping h_01M1BK4M22YAQ6YX4RZXRKZF7C=seo-referrer-mapping h_01H95PGMNY0P2354ZFVC92TMVC=desktop h_01H95PGMNYDSFP6GJDWC9AE0J2=qr-codes h_01H95PGMNYGJ9BJ86YCP7FYH6G=%EC%98%88%EC%8B%9C-2 h_01H95PGMNYZBGZWNFESDTE9GY9=impressions h_01H95PGMNYX1FDT1KK9PQAMX5N=%EC%A4%91%EC%9A%94-2 additional-information=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01H95PGMNYB6A8VKEAH8Z8TDPE=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01H95PGMNYKQ8TNM3KKK9EXANV=faq will-the-incoming-url-for-onelink-link-generation-work-if-the-user-browses-to-a-different-page-on-the-website=%EC%82%AC%EC%9A%A9%EC%9E%90%EA%B0%80-%EC%9B%B9%EC%82%AC%EC%9D%B4%ED%8A%B8-%EB%82%B4-%EB%8B%A4%EB%A5%B8-%ED%8E%98%EC%9D%B4%EC%A7%80%EB%A1%9C-%EC%9D%B4%EB%8F%99%ED%95%98%EB%8A%94-%EA%B2%BD%EC%9A%B0%EC%97%90%EB%8F%84-onelink-%EB%A7%81%ED%81%AC-%EC%83%9D%EC%84%B1%EC%9D%84-%EC%9C%84%ED%95%9C-%EC%88%98%EC%8B%A0-url%EC%9D%B4-%EC%9E%91%EB%8F%99%ED%95%98%EB%82%98%EC%9A%94 h_01H95PGMNYM5X2K9J0WZW6PZ8A=%EC%82%AC%EC%9A%A9%EC%9E%90%EA%B0%80-%EC%9B%B9%EC%82%AC%EC%9D%B4%ED%8A%B8-%EB%82%B4-%EB%8B%A4%EB%A5%B8-%ED%8E%98%EC%9D%B4%EC%A7%80%EB%A1%9C-%EC%9D%B4%EB%8F%99%ED%95%98%EB%8A%94-%EA%B2%BD%EC%9A%B0%EC%97%90%EB%8F%84-onelink-%EB%A7%81%ED%81%AC-%EC%83%9D%EC%84%B1%EC%9D%84-%EC%9C%84%ED%95%9C-%EC%88%98%EC%8B%A0-url%EC%9D%B4-%EC%9E%91%EB%8F%99%ED%95%98%EB%82%98%EC%9A%94 why-do-i-get-an-error-when-implemeting-smart-script-via-google-tag-manager=google-tag-manager%EB%A5%BC-%ED%86%B5%ED%95%B4-smart-script%EB%A5%BC-%EA%B5%AC%ED%98%84%ED%95%A0-%EB%95%8C-%EC%98%A4%EB%A5%98%EA%B0%80-%EB%B0%9C%EC%83%9D%ED%95%98%EB%8A%94-%EC%9D%B4%EC%9C%A0%EB%8A%94-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80%EC%9A%94 h_01H95PGMNYSQX6BJCN56D4XZZF=google-tag-manager%EB%A5%BC-%ED%86%B5%ED%95%B4-smart-script%EB%A5%BC-%EA%B5%AC%ED%98%84%ED%95%A0-%EB%95%8C-%EC%98%A4%EB%A5%98%EA%B0%80-%EB%B0%9C%EC%83%9D%ED%95%98%EB%8A%94-%EC%9D%B4%EC%9C%A0%EB%8A%94-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80%EC%9A%94 can-i-add-parameters-that-are-not-listed=%EB%82%98%EC%97%B4%EB%90%98%EC%A7%80-%EC%95%8A%EC%9D%80-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0%EB%A5%BC-%EC%B6%94%EA%B0%80%ED%95%A0-%EC%88%98-%EC%9E%88%EB%82%98%EC%9A%94 h_01H95PGMNY2AVJ0CYDAM62Q9PA=%EB%82%98%EC%97%B4%EB%90%98%EC%A7%80-%EC%95%8A%EC%9D%80-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0%EB%A5%BC-%EC%B6%94%EA%B0%80%ED%95%A0-%EC%88%98-%EC%9E%88%EB%82%98%EC%9A%94 adset-and-other-parameters-are-not-showing-in-the-dropdown=adset-%EB%B0%8F-%EA%B8%B0%ED%83%80-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0%EA%B0%80-%EB%93%9C%EB%A1%AD%EB%8B%A4%EC%9A%B4%EC%97%90-%ED%91%9C%EC%8B%9C%EB%90%98%EC%A7%80-%EC%95%8A%EC%8A%B5%EB%8B%88%EB%8B%A4 h_01H95PGMNY97BY6BCPPMYHBF0Q=adset-%EB%B0%8F-%EA%B8%B0%ED%83%80-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0%EA%B0%80-%EB%93%9C%EB%A1%AD%EB%8B%A4%EC%9A%B4%EC%97%90-%ED%91%9C%EC%8B%9C%EB%90%98%EC%A7%80-%EC%95%8A%EC%8A%B5%EB%8B%88%EB%8B%A4 what-browsers-does-smart-script-work-on=smart-script%EB%8A%94-%EC%96%B4%EB%96%A4-%EB%B8%8C%EB%9D%BC%EC%9A%B0%EC%A0%80%EC%97%90%EC%84%9C-%EC%9E%91%EB%8F%99%ED%95%98%EB%82%98%EC%9A%94 h_01H95PGMNY5AV0DTX51X0DJMTK=smart-script%EB%8A%94-%EC%96%B4%EB%96%A4-%EB%B8%8C%EB%9D%BC%EC%9A%B0%EC%A0%80%EC%97%90%EC%84%9C-%EC%9E%91%EB%8F%99%ED%95%98%EB%82%98%EC%9A%94 h_01H95PGMNY4W9X51KV6GM4BSPG=specs-and-limitations" />
