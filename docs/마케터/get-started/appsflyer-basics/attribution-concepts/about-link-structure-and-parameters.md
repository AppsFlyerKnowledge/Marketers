---
title: 링크 구조 및 파라미터 소개
metadata:
  keywords:
    - pid
    - Marketers
    - af_
    - af
    - c
    - af_mp
    - clickid
    - af_siteid
    - af_sub_siteid
    - af_c_id
    - af_adset_id
    - af_ad_type
    - af_viewthrough
    - af_cost_model
    - af_cost_value
    - af_web_dp
    - af_ref
    - af_ip
    - af_os_version
    - deep_link_sub
    - deep_link_value
    - af_og_title
    - af_og_description
    - af_og_image
    - af_prt
    - af_adset
    - af_ad
    - af_ad_id
    - af_channel
    - af_keywords
    - af_cost_currency
    - af_sub
    - af_r
    - af_dp
    - af_force_deeplink
    - is_incentivized
    - af_param_forwarding
    - af_partner_account_id
    - af_ua
    - af_os
    - af_model
    - af_media_type
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2015-12-24T11:50:00Z'
  edited_at: '2026-10-14T10:35:30Z'
  id: 207447163
  locale: ko
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/ko/articles/207447163
---
> **한눈에 보기:**  앱스플라이어 어트리뷰션 링크 구조와 파라미터에 대해 알아보세요.

<div id="overview" />

## 개요

어트리뷰션 링크를 통해 광고주는 광고에 대한 사용자 인게이지먼트에 관한 데이터를 수집할 수 있습니다. 어트리뷰션 링크는 광고 뒤에 배치되어 사용자가 광고에 참여할 때 앱스플라이어에 알립니다. 인게이지먼트는 광고를 클릭하거나 광고 노출을 볼 때 발생할 수 있습니다. 어트리뷰션 URL 사본이 앱스플라이어로 전송됩니다.

어트리뷰션 링크는 **원링크** 또는 **단일 플랫폼 링크**를 사용하여 발생합니다.

|  | 원링크 (멀티 플랫폼 링크) | 단일 플랫폼 링크 |
| --- | --- | --- |
| 설명 및 사용 시기 | 다음과 같은 경우에 사용:<ul><li>모든 플랫폼을 아우르는 단일 링크가 필요합니다.</li><li>딥링킹 기능이 필요할 때</li><li>Android 앱 링크나 iOS 유니버설 링크를 사용하여 앱을 열려고 할 때</li></ul><Anchor target="_blank" href="/marketers/ko/docs/onelink-guide">원링크에 대해 더 알아보기</Anchor> | 다음과 같은 경우에 사용:<ul><li>단일 플랫폼만 사용할 때. 예를 들어, Android만 사용하고 iOS는 사용하지 않을 때.</li><li>앱을 열기 위해 URI 스킴만 사용할 때.</li></ul><Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#attribution-link-tab">통합 파트너 설정 방법에 대해 알아보기</Anchor> |
| 선행 조건 | <Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template">원링크 템플릿</Anchor> | 없음 |
| 포함할 정보 | <ul><li>[미디어 소스](/docs/about-link-structure-and-parameters#partner-id-pid-parameter)</li><li>[캠페인](#c)</li><li>[사이트 ID \/ 하위 사이트 ID](/docs/about-link-structure-and-parameters#site-id-parameter)</li></ul> | <ul><li>[미디어 소스](/docs/about-link-structure-and-parameters#partner-id-pid-parameter)</li><li>[캠페인](#c)</li><li>[사이트 ID \/ 하위 사이트 ID](/docs/about-link-structure-and-parameters#site-id-parameter)</li></ul> |
| 기본 URL | `{subdomain}`.onelink.me | app.appsflyer.com |
| 고유 식별자 | 템플릿 ID | app\_id |
| URL 구조 | `https://{subdomain}.onelink.me/`<br />`{templateid}?pid={media_source}`<br />`&af_siteid={ApplicationID}`<br />`&c={CampaignName}` | `https://app.appsflyer.com/{app_id}?pid={media_source}&af_siteid={ApplicationID}&c={CampaignName}` |
| 예시 | `https://yourbrand.onelink.me/aAB1?pid=greatnetwork_int`<br />`&c=GreatCampaign&af_siteid=A1b1` | `https://app.appsflyer.com/com.greatapp?pid=greatnetwork_int&`<br />`c=GreatCampaign&af_siteid=A1b1` |

<div id="important" />

> 🚧 **중요!**
>
> 앱스플라이어는 클릭 및 노출과 같은 인게이지먼트 트래픽 수신 시, HTTPS 프로토콜만을 지원합니다.

<div id="attribution-link-parameters" />

## 어트리뷰션 링크 파라미터

* 나열된 파라미터는 어트리뷰션 링크에서 사용할 수 있습니다.
* 값 **필드 유형** 열은 매개변수 값의 문자 제한입니다. 매개변수 값의 길이 제한에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/raw-data-field-dictionary">여기</Anchor>에서 확인하세요.

<div id="attribution-link-parametersua-and-retargeting" />

### 어트리뷰션 링크 파라미터—UA 및 리타겟팅

다음 표는 [`.csv` 파일로 다운로드](https://docs.google.com/spreadsheets/d/e/2PACX-1vTZQnoDdFo2NxBuWXBs5gGgvkGU2pr_hn58H9Dtf5uHBAHv4Io89Wd44rRtL24pRsOXHthnBitaOyfp/pub?gid=0&single=true&output=csv)할 수 있습니다.

<div id="attribution-parameters" />

| 파라미터 | 로데이터에서의 표시 이름 | 설명 | 필드 유형 및 길이 |
| --- | --- | --- | --- |
| <span id="pid"></span>pid | 미디어 소스 | 앱스플라이어 통합 파트너를 고유하게 식별합니다. 수정하지 마세요. [자세한 내용](/docs/about-link-structure-and-parameters#partner-id-pid-parameter). | <span id="PID"></span>문자열 150 |
| <span id="c"></span>c | 캠페인 | 광고주 또는 퍼블리셔가 제공합니다. [캠페인 이름에 대한 제한](/docs/about-link-structure-and-parameters#what-limits-are-there-on-campaign-names)을 참조하세요. | <span id="Campaign"></span>문자열 100 |
| <span id="af_prt"></span>af\_prt | 파트너 | <ul><li>에이전시 계정 이름을 통해 설치를 에이전시에 귀속시킬 수 있습니다.</li><li>**주의**: **에이전시 권한**이 활성화되었는지 확인하기 전에는 이 매개변수를 사용하지 마세요.</li></ul> | 문자열 50 |
| <span id="af_mp"></span>af\_mp | 해당 없음 | <ul><li>설치 시 퍼블리셔 마케팅 파트너에게 포스트백을 보낼 수 있도록 설정합니다.</li><li>**참고**: 현재 이 매개변수는 핀터레스트 마케팅 파트너에게만 적용됩니다.</li></ul> |  |
| <span id="clickid"></span>clickid | 해당 없음 | 애드 네트워크 고유 클릭 식별자 |  |
| <span id="af_siteid"></span>af\_siteid | 사이트 ID | <ul><li>광고를 게재하는 퍼블리셔를 식별하는 고유 ID입니다. [더 보기](/docs/about-link-structure-and-parameters#site-id-parameter)</li></ul> | <span id="Site_id"></span>문자열 24 |
| <span id="af_sub_siteid"></span>af\_sub\_siteid | 하위 사이트 ID | <ul><li>광고 서브 네트워크\/퍼블리셔 ID입니다.</li><li>주요 퍼블리셔(사이트 ID) 외에 하위 퍼블리셔가 있거나 앱 내 광고 유형\/배치(배너, 전면 광고, 비디오 등)와 같은 추가 정보를 포함하려면 af\_sub\_siteid를 사용하세요. 예: af\_sub\_siteid =ABCD\_4567</li></ul> | 문자열 50 |
| <span id="af_c_id"></span>af\_c\_id | 캠페인 ID | 광고주\/퍼블리셔가 제공합니다. | 문자열 24 |
| <span id="af_adset"></span>af\_adset | 광고세트 | <ul><li>광고주\/퍼블리셔가 제공합니다.</li><li>광고세트는 캠페인과 광고 사이의 중간 데이터 계층 구조 수준입니다. [더 보기](/docs/about-link-structure-and-parameters#데이터의-세분화-수준)</li></ul> | 문자열 100 |
| <span id="af_adset_id"></span>af\_adset\_id | 광고세트 ID | 광고주\/퍼블리셔가 제공합니다. | 문자열 24 |
| <span id="af_ad"></span>af\_ad | 광고 | 광고주\/퍼블리셔가 제공한 광고 이름([더 보기](/docs/about-link-structure-and-parameters#데이터의-세분화-수준)) | 문자열 100 |
| <span id="af_ad_id"></span>af\_ad\_id | 광고 ID | 광고주\/퍼블리셔가 제공합니다. | 문자열 24 |
| <span id="af_ad_type"></span>af\_ad\_type | 광고 유형 | 다음 명명 규칙을 사용하세요.<ul><li>**네이티브**: 미디어 소스의 콘텐츠와 일치하도록 설계된 유료 매체입니다. 이 매체는 귀사의 추천 비디오 피드에 자연스럽게 나타나는 콘텐츠의 시각적 디자인과 기능에 맞게 설계되었습니다.</li><li>**배너**: 웹 페이지나 앱 인터페이스의 다양한 위치에 나타나는 작은 직사각형 형태의 디스플레이 광고입니다.</li><li>**전면 광고**: 호스트 앱의 전체 인터페이스를 덮는 전체 화면 광고입니다. 이 광고는 콘텐츠 사이에 배치되도록 설계되어 앱의 흐름에서 활동 사이 또는 게임 수준 사이, 또는 일시 정지 중에 전환 지점에서 일반적으로 표시됩니다.</li><li>**rewarded\_video**:  인앱 보상을 대가로 게임에서 여분의 생명을 얻기 위해 비디오를 시청하거나, 문서에 액세스하거나, 공항에서 Wi-Fi에 접속하는 등의 광고를 사용자가 완전히 시청할 수 있습니다. 이러한 '보상형' 광고는 사용자를 (유저를 앱에) 참여시키며, 앱 전반의 경험을 향상시킵니다.</li><li>**오디오**: 온라인 팟캐스트나 음악 스트리밍 플랫폼에서 제공되는 오디오 형식의 광고입니다.</li><li>**오퍼월**: 개발자가 앱을 수익화하기 위해 사용하는 인앱 광고 단위입니다. 앱 내에서 작은 상점처럼 작동하며, 사용자가 인앱 보상을 위해 여러 '제안'을 완료할 수 있습니다.</li></ul> | 문자열 24 |
| <span id="af_ad_format"></span>af\_ad\_format | 광고 형식 | 다음 명명 규칙을 사용하세요.<ul><li>**텍스트**: 일반적으로 짧은 텍스트 조각으로 나타나는 텍스트 기반 광고입니다. 사용자의 관심을 끌고 웹사이트나 랜딩 페이지로 클릭-쓰루를 유도하기 위해 제목, 설명, 링크 또는 행동 촉구가 포함될 수 있습니다.</li><li>**이미지**: 그래픽이나 사진을 사용하여 제품, 서비스 또는 브랜드를 보여주는 시각적 광고입니다. 일반적으로 매력적인 이미지와 간결한 텍스트가 포함될 수 있으며, 행동 촉구도 포함될 수 있습니다.</li><li>**비디오**: 마케팅 메시지를 전달하기 위해 시청각 콘텐츠를 사용하는 디지털 광고입니다. 길이는 다양할 수 있으며 온라인 비디오 콘텐츠 내에서 프리롤, 미드롤, 포스트롤로 나타날 수 있습니다. 또한 다양한 플랫폼에서 독립형 비디오로 나타날 수도 있습니다.</li><li>**플레이어블**:  사용자에게 게임이나 앱의 축소판을 체험해 볼 수 있는 대화형 광고로, 다운로드나 구매 전에 (유저를 앱에) 참여시킬 수 있습니다. 사용자는 실제 게임 플레이나 앱 기능을 직접 체험할 수 있습니다.</li><li>**대화형**:  사용자 상호작용이나 참여를 장려하는 매력적이고 역동적인 광고입니다. 사용자의 관심을 끌고 활발한 참여를 유도하기 위해 퀴즈, 설문조사 또는 기타 대화형 요소를 포함할 수 있습니다.</li><li>**dynamic\_product**: 사용자 행동, 선호도 또는 검색 기록에 따라 제품 정보를 동적으로 채우는 개인화된 광고 형식입니다. 이 형식을 통해 광고주는 각 개인에게 적합하고 맞춤형의 제품 광고를 보여줄 수 있습니다.</li><li>**회전목마**: 하나의 광고에 여러 슬라이드 또는 카드로 구성된 광고 형식입니다. 각 카드에는 서로 다른 이미지, 제목, 설명을 포함할 수 있어 광고주는 하나의 광고에서 여러 제품이나 기능을 선보일 수 있습니다.</li></ul> |  |
| <span id="af_click_lookback"></span>af\_click\_lookback | 어트리뷰션 룩백 윈도우 | <ul><li>클릭 어트리뷰션을 위한 룩백 윈도우. 이 윈도우의 지속 시간은 광고/링크를 보여주는 소스가 새 사용자로 측정될 수 있는 최대 CTIT (클릭에서 설치까지의 시간)입니다.</li><li>룩백 클릭 어트리뷰션 기간에 대한 설정 가능한 일수입니다. 사용 가능한 파라미터 값: 1일&#126;30일(일) 또는 1시간&#126;23시간(시간). 기본값은 7일입니다.</li><li>룩백 윈도우는 <Anchor target="_blank" href="/marketers/ko/docs/set-up-lookback-windows#룩백-윈도우-설정하기">OneLinks 및 SRN</Anchor>에 맞게 사용자 정의할 수 있습니다.</li></ul>**참고**: 클릭 URL에만 영향을 주며 노출 URL에는 영향을 주지 않습니다. | 최대 3자 |
| <span id="af_viewthrough_lookback"></span>af\_viewthrough\_lookback | 해당 없음 | <ul><li>룩백 뷰-쓰루 어트리뷰션 기간에 대한 설정 가능한 시간입니다. 사용 가능한 파라미터 값: 1시간&#126;24시간(시간). 기본값은 24시간입니다.</li><li>룩백 윈도우는 <Anchor target="_blank" href="/marketers/ko/docs/set-up-lookback-windows#룩백-윈도우-설정하기">SRN</Anchor>에 맞게 사용자 정의할 수 있습니다.</li></ul>**참고**: 노출 URL에만 영향을 주고 클릭 URL에는 영향이 없습니다. | 최대 3자 |
| <span id="af_channel"></span>af\_channel | 채널 | 광고가 배포되는 미디어 소스 채널 (예: UAC\_Search, UAC\_Display, 인스타그램, Meta Audience Network 등) | Dynamic Enum. 문자열 20자 |
| <span id="af_engagement_destination"></span>af\_engagement\_destination | 인게이지먼트 목적지 | 광고에서 연결된 목적지 카테고리(예: **웹** 랜딩 페이지, **모바일** 앱(딥링크 또는 앱 스토어) 또는 **CTV**, **PC** 또는 **Console**와 같은 다른 목적지 유형)를 나타냅니다. | 문자열 50 |
| <span id="af_keywords"></span>af\_keywords | 키워드 | 텍스트 타겟 캠페인을 위한 키워드 목록 | 문자열 100 |
| <span id="af_cost_model"></span>af\_cost\_model | 비용 모델 | <ul><li>비용 모델, CPI (기본값)는 현재 클릭당 비용 리포팅 시 지원되는 유일한 모델로, <Anchor target="_blank" href="/marketers/ko/docs/roi360-cost-aggregation-overview#cost-data-availability-and-reports">앱스플라이어 데이터 집약형 리포트의 비용 값</Anchor>을 채웁니다.</li><li>가능한 경우 <Anchor target="_blank" href="/marketers/ko/docs/roi360-cost-aggregation-overview#cost-aggregation-methods">API</Anchor>로 비용을 리포트합니다. 링크 및 API에서 모두 비용이 보고되는 경우, API가 우선합니다.</li></ul> | 문자열 20자 |
| <span id="af_cost_currency"></span>af\_cost\_currency | 비용 통화 | <ul><li>3자리 통화 코드는 <Anchor target="_blank" href="/marketers/ko/docs/roi360-cost-aggregation-overview#cost-aggregation-methods">ISO-4217</Anchor>을 준수합니다. 예: USD, ZAR, EUR</li><li>[기본값]: USD</li></ul> | 열거형 3자 |
| <span id="af_cost_value"></span>af\_cost\_value | 비용 값 | <ul><li>비용 통화를 사용한 비용 값입니다.</li><li>소수점 이하 4자리까지 가능합니다.</li><li>숫자만 입력하세요(소수점이 필요하면 사용하세요). 예: "56", "2.85"</li></ul> | 문자열 20자 |
| <span id="af_sub-n-n15-example-af_sub1"></span>af\_sub[n]<br /><br />(n=1-5) 예: af\_sub1 | 하위 파라미터 [n] | 광고주가 정의한 선택적 커스텀 파라미터입니다. 이 파라미터 사용에 대한 자세한 내용은 [특성 및 제한 사항](/docs/about-link-structure-and-parameters#특성-및-제한-사항) 섹션을 확인하세요. | 문자열 100 |
| <span id="af_r"></span>af\_r | 해당 없음 | **모든 플랫폼**(Android, iOS 및 데스크톱)에서 지정된 URL로 사용자를 리디렉션하는 데 사용됩니다.<br /><br />멀티 플랫폼 링크(원링크)에서 이 파라미터는:<ul><li>템플릿 수준의 리디렉션 설정을 무시합니다.</li><li>다음 링크 수준 파라미터로 무시됩니다.</li></ul>**참고:** 추가 리디렉션 파라미터 [특성 및 제한 사항](/docs/about-link-structure-and-parameters#special-characters)을 참조하십시오. |  |
| <span id="af_web_dp"></span>af\_web\_dp | 해당 없음 | 데스크톱(예: Windows 또는 Mac) 사용자를 원링크 템플릿에 설정된 것과 다른 웹 페이지로 리디렉션하는 URL입니다. 이 기능을 사용하여 다른 플랫폼(예: Google Analytics 또는 Omniture)에서 데스크톱 사용자의 어트리뷰션 데이터를 유지할 수 있습니다.<br /><br />**참고:** 추가 리디렉션 파라미터 [특성 및 제한 사항](/docs/about-link-structure-and-parameters#special-characters)을 참조하십시오. |  |
| <span id="af_dp"></span>af\_dp | 해당 없음 | 앱을 시작하는 URI 스킴 대체 값으로, Universal Link 또는 Android 앱 링크 메서드가 실패할 경우 및 Android 6.0 미만의 사용자를 위해 사용됩니다. <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">기본 경로</Anchor>, 즉 기본 액티비티만을 가리켜야 합니다.<br /><br />**참고:** 이 파라미터에 대해서 웹 URL 값을 사용하는 경우 (권장하지 않음) 리디렉션 파라미터의 [특성 및 제한 사항](/docs/about-link-structure-and-parameters#special-characters)을 검토하십시오. |  |
| <span id="af_force_deeplink"></span>af\_force\_deeplink | 해당 없음 | af\_dp 값에 지정된 액티비티에 <Anchor target="_blank" href="/marketers/ko/docs/onelink-troubleshooting-and-faq">강제 딥링크</Anchor>를 적용합니다. |  |
| <span id="af_ref"></span>af\_ref | 해당 없음 | S2S 클릭을 사용하는 광고 네트워크는 다음 매개변수를 사용하여 고유한 참조자 값을 발송할 수 있습니다. &af\_ref=**ReferrerValue**<br /><br />af\_ref 값은 **필수적으로** 다음과 같이 구성된 고유한 값으로 구성되어야 합니다:<br /><br />**네트워크 이름\_각 클릭에 대한 고유 클릭 값**<br /><br />예: af\_ref=networkname\_123456789ABCDEF<br /><br />네트워크 이름은 어떤 유효한 문자열도 가능합니다. networkname\_int이거나 네트워크 이름일 수 있습니다.<br /><br />앱스플라이어는 Android 디바이스의 어트리뷰션에 이 파라미터를 사용할 수 있습니다. 앱스플라이어는 iOS 또는 Windows 디바이스의 어트리뷰션에 이 파라미터를 사용하지 않습니다. |  |
| <span id="is_incentivized"></span>is\_incentivized | 해당 없음 | 부울: true/false<br /><br />보상형 또는 비보상형 캠페인 |  |
| <span id="af_param_forwarding"></span>af\_param\_forwarding | 해당 없음 | <ul><li>false로 설정하면, 어트리뷰션 링크에 있는 파라미터가 리디렉션된 페이지로 전달되지 않습니다.</li><li>리디렉션된 페이지에서 URL을 더 깔끔하게 보이게 하거나 어트리뷰션 링크 파라미터가 쿼리 파라미터 처리 문제로 인해 문제가 생길 수 있는 경우 이 옵션을 사용하세요.</li></ul> |  |
| <span id="af_base_params_forward"></span>af\_base\_params\_forward | 해당 없음 | <ul><li>false로 설정하면, 어트리뷰션 링크에 있는 앱스플라이어 PID 및 C 파라미터가 리디렉션된 페이지로 전달되지 않습니다.</li><li>URL이 데스크톱에서 클릭될 경우, 필수적인 CRM 파라미터는 유지하면서 앱스플라이어 PID와 C 파라미터는 제거하고 싶을 때 이 옵션을 사용하세요. 이렇게 하면 URL에 중복된 PID가 생기는 것을 방지할 수 있습니다.</li></ul> |  |
| <span id="af_partner_account_id"></span>af\_partner\_account\_id | 네트워크 계정 ID | 파트너와 광고주의 계정 ID | 문자열 100 |
| <span id="af_redirect"></span>redirect | 해당 없음 | `&redirect=false`인 경우, 이 파라미터는 앱스플라이어가 S2S 클릭임을 알고, 파트너가 클릭한 사용자를 리디렉션 해야 한다는 것을 알려줍니다. |  |
| <span id="af_ua"></span>af\_ua | 사용자-에이전트 | 클릭과 노출을 <Anchor target="_blank" href="/partners/ko/docs/redirecting-users-to-the-app-store">서버 간(S2S)</Anchor>으로 발송하는 애드 네트워크에 적합합니다.<br /><br />**중요:** 클라이언트-서버(C2S) 링크에서 `af_ua`을 사용하지 마십시오. C2S 링크에서 `af_ua`을 사용하면 속성에 영향을 미칠 수 있습니다.<br /><br />사용자 에이전트 문자열은 다음과 같이 전송됩니다.<ol><li>URL 파라미터(URL로 인코딩됨)</li><li>HTTP 요청 헤더(인코딩되지 않음)</li></ol>사용자 에이전트는 **URL 파라미터와 HTTP 헤더에서 동일해야 합니다**.<br /><br />**Android에서는** 사용자 에이전트가 클라이언트 힌트로 인해 축소될 수 있습니다. 하지만 그와 관계없이 보내야 합니다.<ul><li>**전체 사용자 에이전트의 예:** `Mozilla/5.0 (Linux; Android 12; Pixel 5) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/95.0.4638.16 Mobile Safari/537.36`</li><li>**축소된 사용자 에이전트의 예:** `Mozilla/5.0 (Linux; Android 10; K) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/95.0.0.0 Mobile Safari/537.36`</li></ul>**iOS에서는** iOS 26부터 버전이 첨부됩니다.<br />여기:<ul><li>**첨부된 부분 예시:** `Version/26.0.1 Mobile/15E148 Safari/604.1`</li><li>**전체 사용자 에이전트 예시:**<br />`Mozilla/5.0 (iPhone; CPU iPhone OS 16_4_1 like Mac OS X) AppleWebKit/8615.1.26.10.24 (KHTML, like Gecko) Mobile/20E252 Version/26.0.1 Mobile/15E148 Safari/604.1`</li></ul> |  |
| <span id="af_ip"></span>af\_ip | IP | 클릭과 노출을 <Anchor target="_blank" href="/partners/ko/docs/redirecting-users-to-the-app-store">서버 간</Anchor>으로 발송하는 애드 네트워크에 적합합니다.<br /><br />**중요:** 클라이언트-서버(C2S) 링크에서 `af_ip`을 사용하지 마십시오. C2S 링크에서 `af_ip`을 사용하면 속성에 영향을 미칠 수 있습니다.<br /><br />**디바이스 IP 주소**<br /><br />**권장 사항**: 가능한 경우 디바이스 IP를 `af_ip` 파라미터에 입력하세요.<br /><br />**다음 옵션**: 가능하다면 앱스플라이어는 X-Forwarded-For의 IP를 사용합니다. |  |
| <span id="deprecated--af_os"></span>[사용 중단됨] af\_os | OS 버전 | [iOS 전용] 디바이스의 운영 체제 버전입니다.<br /><br />이 매개변수는 사용이 중단되었지만 앱스플라이어에서 여전히 지원됩니다. 권장 사항: af\_os\_version 매개변수를 대신 사용하세요. |  |
| <span id="af_os_version"></span>af\_os\_version | OS 버전 | <ul><li>클릭과 노출을 <Anchor target="_blank" href="/partners/ko/docs/redirecting-users-to-the-app-store">서버 간</Anchor>으로 발송하는 애드 네트워크에 적합합니다.</li><li>디바이스의 운영 체제 버전입니다.<ul><li>Android:<ul><li>예시: 12</li><li>사용자 에이전트가 축소된 경우(데스크톱 또는 Android에서 운영되는 브라우저와 Chrome 110+ 엔진 사용으로 인해), 애드 네트워크는 <Anchor target="_blank" href="https://web.dev/migrate-to-ua-ch/">클라이언트 힌트 API</Anchor>를 사용하여 이 값을 얻어야 합니다.</li><li>축소되지 `(\d+(?:\.\d+)*);(?:\s..-..;)?\s(.+?(?=\)\|\s\w*\/))`않은 사용자 에이전트의 경우 다음 정규식을 사용하여 사용자 에이전트 문자열에서 Android OS 버전을 추출합니다. .</li></ul></li><li>iOS:<ul><li>예시: 16.2</li></ul></li></ul></li></ul> |  |
| <span id="af_model"></span>af\_model | 디바이스 모델 | <ul><li>클릭과 노출을 <Anchor target="_blank" href="/partners/ko/docs/redirecting-users-to-the-app-store">서버 간</Anchor>으로 발송하는 애드 네트워크에 적합합니다.</li><li>디바이스 모델<ul><li>Android:<ul><li>예시: 픽셀 5</li><li>사용자 에이전트가 축소된 경우(데스크톱 또는 Android에서 운영되는 브라우저와 Chrome 110+ 엔진 사용으로 인해), 애드 네트워크는 <Anchor target="_blank" href="https://web.dev/migrate-to-ua-ch/">클라이언트 힌트 API</Anchor>를 사용하여 이 값을 얻어야 합니다.</li><li>**축소되지 않은** 사용자 에이전트의 경우 다음 정규식을 사용하여 사용자 에이전트 문자열에서 Android 모델을 추출합니다. `(\d+(?:\.\d+)*);(?:\s..-..;)?\s(.+?(?=\)\|\s\w*\/))`.</li></ul></li><li>iOS:<ul><li>`iphone` 또는 `ipad` (모두 소문자)</li><li>정확한 어트리뷰션을 위해 기기 모델 ID를 포함하세요. 예: `iphone15,1` 또는 `ipad14,2`</li></ul></li></ul></li></ul> |  |
| <span id="af_media_type"></span>af\_media\_type | 매체 유형 | 링크가 포함된 광고 배치는 다음과 같습니다:<ul><li>앱: 링크는 앱을 통해 사용할 수 있습니다.</li><li>웹: 링크는 모바일 웹사이트에서 제공됩니다.</li></ul> |  |
| <span id="deep_link_sub110"></span>deep\_link\_sub1-10 | 해당 없음 | 추가적인 딥 링크 값입니다. 개발자는 코드에서 이 값들의 원하는 동작을 구현합니다. |  |
| <span id="deep_link_value"></span>deep\_link\_value | 해당 없음 | 사용자가 이동할 특정 인앱 콘텐츠의 이름입니다. 개발자는 코드에서 deep\_link\_value의 원하는 동작을 구현합니다. |  |
| <span id="af_og_title"></span>af\_og\_title | 해당 없음 | 링크가 소셜미디어에 게시되면, 오픈그래프(OG) 제목이 미리 보기 제목을 생성합니다. | 문자열 40 |
| <span id="af_og_description"></span>af\_og\_description | 해당 없음 | 링크가 소셜미디어에 게시되면, 오픈그래프(OG) 설명이 설명의 미리 보기를 생성합니다. | 문자열 300 |
| <span id="af_og_image"></span>af\_og\_image | 해당 없음 | 링크가 소셜미디어에 게시되면, 오픈그래프(OG) 이미지가 이미지 미리 보기를 생성합니다. |  |

<div id="attribution-link-parametersretargeting-only" />

### 어트리뷰션 링크 파라미터 - 리타겟팅 전용

| 파라미터 | 로데이터에서의 표시 이름 | 설명 | 필드 유형과 너비 |
| --- | --- | --- | --- |
| <span id="is_retargeting"></span>is\_retargeting | 리타겟팅 (캠페인) | 모든 리타겟팅 캠페인의 클릭 URL에는 `&is_retargeting=true`(이)가 포함되어야 합니다.  <br />매개변수가 포함되지 않았거나 값이 "false"인 경우, 캠페인은 일반 사용자 유입 캠페인으로 간주됩니다. | 열거형 5 문자 |
| <span id="af_reengagement_window"></span>af\_reengagement\_window | 리인게이지먼트 기간 | 이 파라미터를 어트리뷰션 링크에 추가하여 <Anchor target="_blank" href="/marketers/ko/docs/retargeting-attribution-guide#reengagement-rules-and-windows">리인게이지먼트 어트리뷰션 기간</Anchor>을 변경합니다.<br /><br />가능한 기간 범위 옵션은 다음과 같습니다.<ul><li>일: 1-90 또는 시간 1-36</li><li>수명: 즉, 리인게이지먼트 기간은 무제한입니다. 예:`&af_reengagement_window=lifetime`</li></ul>기본값: 30일<br /><br />예: `&af_reengagement_window=30d`은(는) 리인게이지먼트 기간을 30일로 설정합니다. | 해당 없음 |

<div id="viewability-parameters" />

### 조회 가능성 파라미터

광고 유형에 따라 인게이지먼트 사양을 자세히 설명하는 관련 조회 가능성 파라미터를 발송할 수도 있습니다.

| 파라미터 | 값 형식 | 설명 |
| --- | --- | --- |
| <span id="af_video_total_length"></span>af\_video\_total\_length | 초 | 비디오의 총 가능한 길이 |
| <span id="af_video_played_length"></span>af\_video\_played\_length | 초 | 비디오가 얼마나 재생되었는지 |
| <span id="af_playable_played_length"></span>af\_playable\_played\_length | 초 | 플레이 가능한 요소가 완전히 로드된 후 재생된 시간 |
| <span id="af_ad_time_viewed"></span>af\_ad\_time\_viewed | 초 | 광고 단위가 화면에 표시된 시간 |
| <span id="af_ad_displayed_percent"></span>af\_ad\_displayed\_percent | % | 디바이스 화면에 표시된 광고 단위의 최대 비율 |
| <span id="af_audio_total_length"></span>af\_audio\_total\_length | 초 | 오디오의 총 가능한 길이 |
| <span id="af_audio_played_length"></span>af\_audio\_played\_length | 초 | 오디오가 얼마나 재생되었는지 |

<div id="android-specific-parameters" />

### Android 특정 파라미터

| 파라미터 | 로데이터에서의 표시 이름 | 설명 | 필드 유형 |
| --- | --- | --- | --- |
| <span id="advertising_id"></span>advertising\_id | 광고 ID | Google Advertising ID - 애드 네트워크 지원 필요합니다. | 최대 40자 |
| <span id="sha1_advertising_id"></span>sha1\_advertising\_id | 해당 없음 | SHA1로 해시된 Google Advertising ID - 애드 네트워크 지원 필요합니다. |  |
| <span id="md5_advertising_id"></span>md5\_advertising\_id | 해당 없음 | MD5로 해시된 Google Advertising ID - 애드 네트워크 지원 필요합니다. | 설치 및 재귀속으로만 지원됨 |
| <span id="android_id"></span>android\_id | Android ID | 디바이스 Android\_id - 애드 네트워크 지원 필요합니다. | 최대 20자 |
| <span id="sha1_android_id"></span>sha1\_android\_id | 해당 없음 | SHA1로 해시된 디바이스 Android\_id - 애드 네트워크 지원 필요합니다. |  |
| <span id="md5_android_id"></span>md5\_android\_id | 해당 없음 | MD5로 해시된 디바이스 Android\_id - 애드 네트워크 지원 필요합니다. | 설치 및 재귀속으로만 지원됨 |
| <span id="imei"></span>imei | IMEI | 디바이스 IMEI ID |  |
| <span id="sha1_imei"></span>sha1\_imei | 해당 없음 | SHA1로 해시된 디바이스 IMEI ID - 애드 네트워크 지원 필요합니다. |  |
| <span id="md5_imei"></span>md5\_imei | 해당 없음 | MD5로 해시된 디바이스 IMEI ID - 애드 네트워크 지원 필요합니다. |  |
| <span id="oaid"></span>oaid | OAID | 오픈 익명의 디바이스 식별자 | Android SDK 버전 4.10.3부터 사용 가능 |
| <span id="sha1_oaid"></span>sha1\_oaid | 해당 없음 | SHA1로 해시된 오픈 익명의 디바이스 식별자 - 애드 네트워크 지원 필요합니다. | Android SDK 버전 4.10.3부터 사용 가능 |
| <span id="md5_oaid"></span>md5\_oaid | 해당 없음 | MD5로 해시된 익명의 디바이스 식별자 - 애드 네트워크 지원이 필요합니다. | Android SDK 버전 4.10.3부터 사용 가능 |
| <span id="af_android_url"></span>af\_android\_url | 해당 없음 | Android 사용자를 Google Play의 앱 페이지가 아닌 다른 URL로 리디렉션합니다. <Anchor target="_blank" href="/marketers/ko/docs/set-up-multi-store-android-attribution#단일-대시보드-대-스토어-대시보드">써드 파티 앱 스토어</Anchor>에 사용하세요.<br /><br />**참고:** 추가 리디렉션 파라미터 [특성 및 제한 사항](/docs/about-link-structure-and-parameters#special-characters)을 참조하십시오. |  |
| <span id="sha1_el"></span>sha1\_el | 해당 없음 | 데스크탑에서 모바일 어트리뷰션을 위해 사용됨 - 이메일을 SHA1로 해시함. 애드 네트워크 지원이 필요합니다. |  |
| <span id="fire_advertising_id"></span>fire\_advertising\_id | 해당 없음 | Amazon Fire 광고 ID |  |
| <span id="af_android_store_csl"></span>af\_android\_store\_csl | store\_product\_page | Google 콘솔에서의 커스텀 스토어 리스트 | 문자열 |

<div id="ios-specific-parameters" />

### iOS 전용 파라미터

| 파라미터 | 표시 이름 | 설명 |
| --- | --- | --- |
| <span id="idfa"></span>idfa | IDFA | 대문자를 사용하세요. 애드 네트워크 지원이 필요합니다.<br /><br />필드 유형: 최대 40자 |
| <span id="idfv"></span>idfv | IDFV | 대문자를 사용하세요. |
| <span id="af_ios_url"></span>af\_ios\_url |  | 이 설정을 통해 iOS (iPhone 또는 iPad) 사용자를 iTunes의 앱 페이지가 아닌 다른 URL로 리디렉션하는 랜딩 페이지 리디렉션에 사용할 수 있습니다.<br /><br />**참고:** 추가 리디렉션 파라미터 [특성 및 제한 사항](/docs/about-link-structure-and-parameters#special-characters)을 참조하십시오. |
| <span id="af_ios_store_cpp"></span>af\_ios\_store\_cpp | store\_product\_page | 커스텀 제품 페이지 ID (ppid)<br /><br />**참고:** 로데이터와 데이터 집약형 리포팅에서는 af\_ios\_store\_cpp (커스텀 제품 페이지 ID) 파라미터 값이 클릭에 대해서만 기록되고 노출에 대해서는 기록되지 않습니다. |
| <span id="af_ios_fallback--deprecated"></span>af\_ios\_fallback [사용 중단] | 해당 없음 | **사용 중단**: 사용자는 <Anchor target="_blank" href="/marketers/ko/docs/uri-scheme-fallback-for-ios">iOS URI 체계 흐름</Anchor>을 기반으로 리디렉션됩니다. |
| <span id="sha1_idfa"></span>sha1\_idfa | 해당 없음 | IDFA를 SHA1로 해시함. 애드 네트워크 지원이 필요합니다. |
| <span id="sha1_idfv"></span>sha1\_idfv | 해당 없음 | SHA1로 해시된 IDFV |
| <span id="mac"></span>mac | 해당 없음 | 디바이스의 MAC 주소. 애드 네트워크 지원이 필요합니다. |
| <span id="md5_idfa"></span>md5\_idfa | 해당 없음 | MD5로 해시된 IDFA |
| <span id="md5_idfv"></span>md5\_idfv | 해당 없음 | MD5로 해시된 IDFV |
| <span id="sha1_mac"></span>sha1\_mac | 해당 없음 | SHA1로 해시된 디바이스의 MAC 주소. 애드 네트워크 지원이 필요합니다. |

<div id="example" />

> 📄 **예시**
>
> ```http
> https://app.appsflyer.com/{app_id}/?pid=airpush_int&c=RedBanner&
> 	  af_siteid={publisher_id}&af_sub1=1.5&af_sub2=USD&af_sub3=burst_campaign
> ```

모든 파라미터는 <Anchor target="_blank" href="/marketers/ko/docs/raw-data-reporting-overview">설치 리포트</Anchor>와 <Anchor target="_blank" href="/marketers/ko/docs/analytics-and-aggregate-reporting-apis">분석, 리포트 및 API</Anchor>에서 이용할 수 있습니다.

<div id="custom-parameters" />

### 사용자 지정 파라미터

기본 Android 전용 및 iOS 전용 파라미터 외에도 커스텀 파라미터를 지정할 수 있습니다. 이러한 커스텀 파라미터는 어트리뷰션 링크에 따라 설치로 이어지는 사용자 경험 및 콘텐츠를 커스터마이즈하는 데 유용할 수 있습니다.

`parameter=value` 형식으로 어트리뷰션 링크에 커스텀 파라미터를 추가할 수 있습니다. 예를 들어:

```http
https://app.appsflyer.com/com.greatapp?pid=networkx_int&c=winter&af_adset=coats&af_ad=cashmere&my_custom_param=my_custom_value
```

커스텀 파라미터에 대해 알아야 할 두 가지 중요한 사항:

* 커스텀 파라미터는 로데이터에 나타나지 않습니다.
* 커스텀 파라미터는 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data">전환 데이터 SDK API</Anchor>에서 검색할 수 있습니다.

<div id="partner-id-pid-parameter" />

<Accordion title="파트너 ID (PID) 파라미터">

사용 가능한 모든 어트리뷰션 링크 파라미터 중에서 PID는 필수입니다. PID는 앱스플라이어가 할당한 미디어 소스의 고유 식별자입니다.

각 <Anchor target="_blank" href="http://appsflyer.com/partners">파트너사</Anchor> 에는 *\_int* 접미사로 끝나는 고유한 PID 값이 부여됩니다. <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">OneLink 링크</Anchor> 를 사용할 때는 연동 파트너사가 선점한 값이 아니라면 원하시는 어떤 값으로든 PID를 설정하실 수 있습니다.

<div id="note" />

> 📘 **참고**
>
> 앱스플라이어는 이메일이나 SMS 같은 커스텀 미디어 소스에서 예약된 <Anchor target="_blank" href="/marketers/ko/docs/self-reporting-networks-srns#앱스플라이어와-통합된-srn">SRN</Anchor> 이름을 PID 값으로 사용하는 어트리뷰션 링크를 차단합니다. 이 제한은 ASRN에는 **적용되지 않습니다**.

중요한 연동 파트너 전용 PID의 대표적인 예로는 organic, googleadwords\_int(Google AdWords), facebook\_int(Meta ads), twitter\_int(X Ads) 등이 있습니다. 이메일, SMS, mail pigeons와 같은 비연동 소스의 경우 원하는 어떤 이름이든 사용할 수 있습니다.

<div id="avoid-common-pid-issues" />

#### 일반적인 PID 문제를 방지하세요:

* **귀사의 어트리뷰션 링크에 항상 PID를 포함하세요.** 어트리뷰션 링크에 PID가 없으면 사용자는 자동으로 "None" 미디어 소스로 어트리뷰션되며, 최초 설치 소스 정보는 유실됩니다.
* **각 연동 소스의** 설치가 정확하게 어트리뷰션되려면 지정된 PID만 사용해야 합니다.
* **커스텀 소스의 경우 비통합 파트너 PID를 사용하세요.** 이메일, SMS 또는 Facebook의 비대가성 바이럴 게시물과 같은 모든 커스텀 미디어 소스에는 owned\_email, sms\_push 등 연동 파트너의 이름 과 중복되지 않는 다른 비연동 PID 값을 사용하세요.
* **법적 문자만 사용하세요.** 어트리뷰션 링크의 PID 파라미터에 /&lt;>*&?\ 중 하나라도 포함되어 있는 경우
  * 해당 클릭 또는 설치는 대시보드상에서 ***af\_invalid\_param*** 항목으로 표시됩니다.
  * 어트리뷰션 링크는 귀속되지 않습니다.
  * 클릭 시 딥링킹 기능이 작동하지 않습니다.

<div id="tip" />

> 👍 **팁**
>
> PID 값에는 공백을 사용하지 않거나, 어트리뷰션 링크를 사용하기 전에 반드시 URL 인코딩을 진행하세요.

</Accordion>

<div id="site-id-parameter" />

<Accordion title="사이트 ID 파라미터">

사이트 ID는 광고를 게재하는 퍼블리셔의 고유 식별자입니다. 즉, 광고를 표시하는 웹사이트나 앱입니다. 애드 네트워크는 각 퍼블리셔마다 고유한 사이트 ID를 할당합니다.

이 ID는 어트리뷰션 링크를 통해 앱스플라이어로 전달되는 `af_siteid` 파라미터에 포함되며, 다양한 대시보드, 리포팅 옵션, 포스트백을 통해 확인하실 수 있습니다.

사이트 ID는 다음과 같은 이유 로 어트리뷰션 링크를 통해 앱스플라이어에 전달되어야 합니다.

* 퍼블리셔에 대한 명확성과 투명성을 제공합니다
* 앱스플라이어가 프로드 퍼블리셔 및 기타 프로드 트래픽 클러스터를 식별하고 차단하는 데 사용됩니다.

사이트 ID 파라미터에는 광고를 게재하는 퍼블리셔의 ID만 포함됩니다.

앱 내 배너, 전면 광고, 비디오 등 광고 유형이나 지면(위치), 또는 둘 다에 대한 추가 정보를 포함하려면 서브 사이트 ID 파라미터를 사용하세요.

<div id="example-1" />

> 📄 **예시**
>
> 다음 어트리뷰션 링크에는 다음이 포함됩니다.
>
> * `af_siteid` (사이트 ID): 퍼블리셔 ID
> * `af_sub_siteid` (하위 사이트 ID): 추가 ID 정보 (이 경우, 어필리에이트 소스 및 광고 유형 지면)
>
> `https://app.appsflyer.com/com.yourapp?pid=mediaName_int&clickid={clickid}&advertising_id={gaid}&af_siteid=1234&af_sub_siteid=ABCD_4567`
>
> 예시 링크:
>
> * 1234 = 퍼블리셔 ID
> * ABCD = 퍼블리셔와 협력하는 어필리에이트 소스(서브 퍼블리셔)
> * 4567 = 배너, 전면 광고, 동영상 등 앱 내 광고 유형 지면

<div id="faq-why-does-traffic-result-in-many-blocked-installs" />

#### **자주 묻는 질문: 트래픽으로 차단된 설치가 많은 이유는 무엇입니까?**

차단된 설치는 다음과 같은 이유로 발생할 수 있습니다.

* **누락된 사이트 ID:** 클릭 URL 내 `af_siteid` 파라미터가 비어 있습니다.Site ID가 비어 있는 상태로 전송된 참여(Engagement)는 기술적 문제이거나 프로드 감지 시스템을 회피하려는 의도적인 시도임을 의미합니다.
* **여러 사이트 ID:** 동일한 퍼블리셔가 서로 다른 사이트 ID를 사용하여 여러 클릭 URL로 전송됩니다. 이는 실제 퍼블리셔의 활동을 은폐하는 프로드 행위로 간주되며, 클릭 플러딩(click flooding)과 연관되어 있는 경우가 많습니다.
* **잘못된 사이트 ID 형식:** 잘못된 형식을 전송할 경우 다른 프로드 징후와 결합되어 특정 퍼블리셔뿐만 아니라 더 높은 상위 클러스터 수준까지 차단될 수 있으며, 이는 파트너사의 전체 트래픽량에 영향을 미칠 수 있습니다.

설치가 차단되는 것을 방지하려면 예시에 나온 것처럼 퍼블리셔당 단 하나의 사이트 ID 파라미터만 전송하도록 하세요.

</Accordion>

<div id="levels-of-data-granularity" />

## 데이터의 세분화 수준

최대 4개의 URL 파라미터를 사용하여 귀사의 광고 성과를 깊이 분석할 수 있습니다.

모든 활성 어트리뷰션 링크에 4개의 파라미터를 전부 사용하면 다음과 같은 이점이 있습니다.

* 모든 사용자 설치와 이벤트를 특정 광고와 어트리뷰션합니다.
* 데이터 집약형 보고서에서 광고 세트별, 캠페인별, 미디어 소스별로 귀사의 모든 광고 성과를 분석하고 비교하여 모든 수준에서 최적화할 수 있습니다.
* 로데이터 리포트와 <Anchor target="_blank" href="/marketers/ko/docs/pivot-table-user-metrics">피벗 표</Anchor>에서 모든 미디어 소스에 걸쳐 귀사의 모든 광고를 비교합니다.

파라미터는 다음과 같습니다.

* `Media source (pid=)`
* `campaign name (c=)`
* `Ad set (af_adset=)`
* `Ad name (af_ad=)`

<div id="example-2" />

> 📄 **예시**
>
> 다음 어트리뷰션 링크는 통합된 "네트워크" 미디어 소스에서 운영되는 "겨울" 캠페인의 "코트" 광고 세트 내 "캐시미어" 광고를 기록하기 위해 4단계의 세분성을 사용합니다.
>
> ```http
> https://app.appsflyer.com/com.greatapp?pid=networkx_int&c=winter&
> af_adset=coats&af_ad=cashmere
> ```

<div id="frequently-asked-questions" />

## 자주 묻는 질문

<div id="should-i-use-lower-or-upper-case-letters-for-parameters" />

<Accordion title="파라미터에 소문자나 대문자를 사용해야 하나요?">

둘 중 하나를 사용할 수 있지만 항상 일관성을 유지해야 합니다. 대문자 또는 소문자로 커스텀 파라미터를 설정했다면 항상 그 파라미터 형식을 사용해야 합니다.

예를 들어, pid=MyMediaSource로 설정했다면, 항상 이것을 사용하세요. 한 어트리뷰션 링크에서 pid=MyMediaSource를 사용하고 다른 링크에서는 pid=mymediasource를 사용하면 데이터 불일치가 발생할 수 있습니다. 이는 어트리뷰션 링크에 설정한 다른 모든 파라미터에도 동일하게 적용됩니다.

</Accordion>

<div id="is-the-appsflyer-attribution-link-dynamic-or-static" />

<Accordion title="앱스플라이어 어트리뷰션 링크가 동적인가요 아니면 정적인가요?">

어트리뷰션 링크는 동적이거나 정적일 수 있습니다.  
링크가 동적인지 정적인지 어떻게 알 수 있나요?  
**어트리뷰션 링크에 파라미터**가 포함되어 있으면, 이는 미리 정의된 긴 어트리뷰션 링크이며 **정적**입니다.  
<strong>커스텀 어트리뷰션 링크에 사용되는 짧은 URL</strong>(예: )은 동적입니다.  
즉, 통합 파트너에 대한 어트리뷰션 링크나 자체 매체에 대한 긴 URL을 사용하기 시작하면, 앱스플라이어 대시보드에서 어트리뷰션 링크 값을 변경해도 해당 링크와 상호 작용하는 리드에는 변화가 없습니다. 변경을 적용하려면 새로운 긴 URL을 앞으로 사용해야 합니다.  
반면에, 자체 매체의 짧은 URL은 파라미터를 직접 포함하지 않습니다. 리드가 앱스플라이어 짧은 URL로 상호작용하면, 리드는 앱스플라이어로 리디렉션되고 현재 설정된 파라미터가 동적으로 적용됩니다.

</Accordion>

<div id="what-is-this-play-store-error-message" />

<Accordion title="Play 스토어 오류 메시지가 무엇인가요?">

어트리뷰션 링크를 따라간 후 Play 스토어에서 다음과 같은 오류 메시지가 나타나는 경우:

![TL_error_message.png](https://files.readme.io/03e509d3cbe68aa0621bb0f43ab113c25a8427e70826c5af5258f1fc9e3f3d36-360000002485.png)

이는 어트리뷰션 링크에 # 문자가 포함되어 있기 때문입니다. 예를 들어:

```http
https://app.appsflyer.com/com.travelco?pid=globalwide_int&clickid=#reqid#
```

일반적으로 이러한 문자는 매크로이기 때문에 링크에 있으며, 동적으로 값으로 대체되므로 큰 문제가 아니며 메시지를 무시할 수 있습니다.

</Accordion>

<div id="what-are-subscriber-parameters-good-for" />

<Accordion title="구독자 파라미터는 무엇이 좋은가요?">

구독자 파라미터, 즉 af\_sub1, af\_sub2, ..., af\_sub\_5는 유용한 KPI를 기록하는 데 사용할 수 있습니다. 이러한 파라미터는 분석되어 로데이터 리포트에 표시되므로 데이터 집계나 필터링을 수행하는 데 매우 유용합니다.

<div id="example-3" />

> 📄 **예시**
>
> 우박 차량 호출 앱인 Luber에는 파란색, 노란색, 빨간색의 3가지 색상 템플릿이 있는 크리에이티브가 있습니다. Luber의 모바일 마케터인 Linda는 어떤 색상 템플릿이 더 많은 설치를 가져오는지 시험하고 싶어합니다. 이를 위해 그녀는 모든 비(非) SRN 매체 소스의 모든 파란색 광고의 어트리뷰션 링크에 `&af_sub3=blue`을 추가합니다. 노란색과 빨간색 광고에도 동일한 작업이 수행됩니다. 이러한 정보를 분석하여 로데이터 리포트에 표시되면 Linda는 다양한 색상의 광고의 성공 여부를 분석하고 가장 전환율이 높은 광고를 선택할 수 있습니다.

</Accordion>

<div id="what-limits-are-there-on-campaign-names" />

<Accordion title="캠페인 이름에 어떤 제한이 있나요?">

* 어트리뷰션 링크 URL에 있는 캠페인 이름의 최대 길이는 100자로 제한됩니다. 초과 시 캠페인 이름이 `c_name_exceeded_max_length`로 변경됩니다.
* 캠페인 이름은 공백으로 시작하거나 끝나서는 안 됩니다. 이는 대시보드와 리포트에서 불일치를 일으킬 수 있습니다.

</Accordion>

<div id="traits-and-limitations" />

## 특성 및 제한 사항

| 특성 | 비고 |
| --- | --- |
| <span id="special-characters"></span>특수문자 | 다음 특수문자는 파라미터 키 및 값에 사용할 수 없습니다 (redirect 및 af\_dp 파라미터 제외): ;, *, !, @, #, ?, $, ^, :, &, ~, \`, =, +, ’, >, &lt;, /, \{, \}, %, ), ( |
| <span id="redirection-parameters"></span>리디렉션 파라미터 | <ul><li>리디렉션 URL 도메인이 <Anchor target="_blank" href="/marketers/ko/docs/set-up-your-domain-redirect-allowlist">리디렉션 허용 목록</Anchor>에 추가되었는지 확인하십시오.</li><li>리디렉션 값은 <Anchor target="_blank" href="https://datatracker.ietf.org/doc/html/rfc1738">RFC 1738 표준</Anchor>에 따라 유효한 전체 웹 URL(https://[domain][optional-path])이어야 합니다.</li><li>리디렉션 URL에서는 <Anchor target="_blank" href="https://en.wikipedia.org/wiki/URI_fragment">URI 프래그먼트 식별자</Anchor>(예: #webpagesection처럼 사용자를 문서 내 특정 섹션으로 스크롤시키는 기능)는 **지원되지 않습니다**.</li></ul> |
| <span id="url-characteravailable"></span>URL 문자 제한 | 총 URL 길이는 2000자를 초과할 수 없습니다. |
| <span id="agencies"></span>Android 소셜 앱 WebView 딥링킹 리디렉션 | 제한 세부사항은 <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#android-social-apps-webview-deep-linking-redirection">여기</Anchor>에서 확인하세요. |
| <span id="deep-linking-is-not-supported-in-the-android-naver-blog-app"></span>Android 네이버 블로그 앱에서는 딥링킹이 지원되지 않습니다. | Android 네이버 블로그 앱에서는 딥링킹이 지원되지 않습니다. 사용자는 링크에 설정된 대로 Google Play Store나 웹으로 리디렉션됩니다. |
| <span id="a-popup-appears-when-clicking-on-a-uri-scheme-link-from-chrome-browser-on-ios"></span>iOS에서 Chrome 브라우저에서 URI 스킴 링크를 클릭하면 팝업이 표시됩니다. | Chrome iOS의 변경으로 인해 iOS의 Chrome에서 사용자가 URI 스킴 링크를 클릭할 때마다 앱 열기 확인 또는 애플 앱 스토어로 리디렉션할지 묻는 팝업이 표시됩니다. |
| <span id="uri-scheme-validity-requirements"></span>URI 스킴 유효성 요구 사항 | <Anchor target="_blank" href="https://www.rfc-editor.org/rfc/rfc3986#section-3.1">RFC 3986</Anchor>을 준수하는 유효한 URI 스킴을 사용하는 것이 좋습니다. 위의 조건을 준수하지 않는 스킴은 앱을 열지 못할 수 있으며 웹뷰 또는 다른 웹 환경에서 클릭 시 오류가 발생할 수 있습니다. |
| <span id="telegram-webview-attribution"></span>Telegram WebView 어트리뷰션 | 제한 세부사항은 <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#telegram-webview">여기</Anchor>에서 확인하세요. |

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 01H8GN1XXC5T2ENFHBK0G4WQ1P=%EA%B0%9C%EC%9A%94 01JENAANV4KTRF882JMEM5N91A=%EC%A4%91%EC%9A%94 attribution-link-parameters=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 01H8GN1XXDX1XMQ1GJTHCP425D=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 attribution-link-parameters%E2%80%94ua-and-retargeting=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0ua-%EB%B0%8F-%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85 01H8GN1XXDEWPB2MPP3KJVPRJV=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0ua-%EB%B0%8F-%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85 af_sub%5Bn%5D%C2%A0%0An15-example-af_sub1=af_sub-n-n15-example-af_sub1 %5Bdeprecated%5D-af_os=deprecated--af_os attribution-link-parameters%E2%80%94retargeting-only=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0---%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%EC%A0%84%EC%9A%A9 01H8GN1XXD9X7CWZJN43PSS94R=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0---%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%EC%A0%84%EC%9A%A9 viewability-parameters=%EC%A1%B0%ED%9A%8C-%EA%B0%80%EB%8A%A5%EC%84%B1-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 01H8GN1XXETQEYT39F05ZYX4E2=%EC%A1%B0%ED%9A%8C-%EA%B0%80%EB%8A%A5%EC%84%B1-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 androidspecific-parameters=android-%ED%8A%B9%EC%A0%95-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 01H8GN1XXEE9RGSB1H72H025Z4=android-%ED%8A%B9%EC%A0%95-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 iosspecific-parameters=ios-%EC%A0%84%EC%9A%A9-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 01H8GN1XXESJ9VE3W8CYKRFFYX=ios-%EC%A0%84%EC%9A%A9-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 af_ios_fallback-%5Bdeprecated%5D=af_ios_fallback--deprecated 01H8GN1XXEFRSQSERTB6ARC773=%EC%98%88%EC%8B%9C custom-parameters=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 01H8GN1XXEB58JN4SV9HX1ZV6S=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 01H8GN1XXE8EXMMKDZMJ2WNNH5=partner-id-pid-parameter h_01JRX48BX8W9V9XWPB1DSG4H8Y=%EC%B0%B8%EA%B3%A0 avoid-common-pid-issues=%EC%9D%BC%EB%B0%98%EC%A0%81%EC%9D%B8-pid-%EB%AC%B8%EC%A0%9C%EB%A5%BC-%EB%B0%A9%EC%A7%80%ED%95%98%EC%84%B8%EC%9A%94 01H8GN1XXEXTGC4M8AMJ256Q9G=%EC%9D%BC%EB%B0%98%EC%A0%81%EC%9D%B8-pid-%EB%AC%B8%EC%A0%9C%EB%A5%BC-%EB%B0%A9%EC%A7%80%ED%95%98%EC%84%B8%EC%9A%94 01H8GN1XXEGNVX9GM5JYBMBGCF=%ED%8C%81 01H8GN1XXEVG65YP782CM37RES=site-id-parameter 01H8GN1XXED2MVSNRXN11KZ955=%EC%98%88%EC%8B%9C-1 faq-why-does-traffic-result-in-many-blocked-installs=%EC%9E%90%EC%A3%BC-%EB%AC%BB%EB%8A%94-%EC%A7%88%EB%AC%B8-%ED%8A%B8%EB%9E%98%ED%94%BD%EC%9C%BC%EB%A1%9C-%EC%B0%A8%EB%8B%A8%EB%90%9C-%EC%84%A4%EC%B9%98%EA%B0%80-%EB%A7%8E%EC%9D%80-%EC%9D%B4%EC%9C%A0%EB%8A%94-%EB%AC%B4%EC%97%87%EC%9E%85%EB%8B%88%EA%B9%8C 01H8GN1XXEK0G9TDW8WHWM17HK=%EC%9E%90%EC%A3%BC-%EB%AC%BB%EB%8A%94-%EC%A7%88%EB%AC%B8-%ED%8A%B8%EB%9E%98%ED%94%BD%EC%9C%BC%EB%A1%9C-%EC%B0%A8%EB%8B%A8%EB%90%9C-%EC%84%A4%EC%B9%98%EA%B0%80-%EB%A7%8E%EC%9D%80-%EC%9D%B4%EC%9C%A0%EB%8A%94-%EB%AC%B4%EC%97%87%EC%9E%85%EB%8B%88%EA%B9%8C levels-of-data-granularity=%EB%8D%B0%EC%9D%B4%ED%84%B0%EC%9D%98-%EC%84%B8%EB%B6%84%ED%99%94-%EC%88%98%EC%A4%80 01H8GN1XXE4RF9J0APAAKD1WEG=%EB%8D%B0%EC%9D%B4%ED%84%B0%EC%9D%98-%EC%84%B8%EB%B6%84%ED%99%94-%EC%88%98%EC%A4%80 01H8GN1XXEHPFKX7V0RRW2MH2G=%EC%98%88%EC%8B%9C-2 frequently-asked-questions=%EC%9E%90%EC%A3%BC-%EB%AC%BB%EB%8A%94-%EC%A7%88%EB%AC%B8 h_01HN0JW166VHR33T8VVVY47F9P=%EC%9E%90%EC%A3%BC-%EB%AC%BB%EB%8A%94-%EC%A7%88%EB%AC%B8 01H8GN1XXEND9X8YVRQE1YFA5W=should-i-use-lower-or-upper-case-letters-for-parameters 01H8GN1XXER749PH4Z14A7AJ0F=is-the-appsflyer-attribution-link-dynamic-or-static 01H8GN1XXEPQTY0XNW6EZSA9ZN=what-is-this-play-store-error-message 01H8GN1XXFYAFYFX9MNBP6D35B=what-are-subscriber-parameters-good-for 01H8GN1XXFEFA498J22GRF5F8G=%EC%98%88%EC%8B%9C-3 01H8GN1XXFS1DFS3HAHVTVG93A=what-limits-are-there-on-campaign-names traits-and-limitations=%ED%8A%B9%EC%84%B1-%EB%B0%8F-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD h_01HN0JW166WH76A5SM293PGKX6=%ED%8A%B9%EC%84%B1-%EB%B0%8F-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD" />
