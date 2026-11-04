---
title: PC 및 콘솔 앱을 위한 Google Ads 웹 연동
metadata:
  keywords:
    - google ads configuration
    - google ads
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2024-01-18T11:04:33Z'
  edited_at: '2026-10-14T10:31:10Z'
  id: 21768823915665
  locale: ko
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/ko/articles/21768823915665
---
> **한눈에 보기:** Google Ads 웹 캠페인을 사용하여 PC 및 콘솔 플랫폼에서 앱을 홍보하고 어트리뷰션을 활성화하세요. 앱스플라이어는 크로스 플랫폼 랜딩 페이지 또는 다이렉트 어트리뷰션 링크를 사용하는 구글 웹 기반 캠페인을 지원합니다.

<div id="note" />

> 📘 **참고**
>
> 이 문서는 PC 또는 콘솔 앱을 홍보하는 웹 캠페인에 중점을 둡니다. 모바일 앱을 홍보하는 웹 캠페인을 만들고 싶다면 <Anchor target="_blank" href="/marketers/ko/docs/google-ads-adwords-create-web-based-campaigns">Google Ads (AdWords) - 웹 기반 캠페인 만들기</Anchor>를 참조하세요.

<div id="overview" />

## 개요

이 문서에는 앱스플라이어와 함께 PC 및 콘솔 앱용 Google Ads 웹을 설정하고 사용하는 방법에 대한 정보와 단계가 포함되어 있습니다. 여기에는 다음이 포함됩니다:

* [앱스플라이어에서 파트너 연동 활성화하기](/docs/google-ads-web-integration-for-pc-and-console-apps#앱스플라이어에서-파트너-활성화).
* [앱스플라이어에서 Google Ads 웹 설정하기](/docs/google-ads-web-integration-for-pc-and-console-apps#setting-up-Googleadsweb-in-appsflyer)
* [Google Ads에서 PC 및 콘솔 앱용 캠페인 설정하기](/docs/google-ads-web-integration-for-pc-and-console-apps#google-ads-웹에서-pc-및-콘솔-앱용-캠페인-설정하기).

<div id="prerequisites" />

### 필수 조건

Google Ads 웹 연동을 활성화하기 전에 다음이 있는지 확인하세요.

* PC 또는 콘솔 앱
* 앱스플라이어 계정
* <Anchor target="_blank" href="https://developers.google.com/identity/protocols/oauth2/scopes">필수 OAuth 범위</Anchor>가 포함된 Google 액세스 토큰입니다. Google 개발자 콘솔에서 액세스 토큰과 관련된 범위를 확인할 수 있습니다.
* <Anchor target="_blank" href="/marketers/ko/docs/user-management">적절한 역할/권한</Anchor> 및 관련 앱에 대한 액세스 권한을 가진 앱스플라이어 사용자

<div id="activate-partner-in-appsflyer" />

## 앱스플라이어에서 파트너 활성화

**파트너 연동 활성화 방법:**

1. 앱스플라이어의 사이드 메뉴에서**협업**>**파트너 마켓플레이스**로 이동합니다.
2. **Google Ads 웹**을 검색하여 선택합니다.
3. **연동 설정**을 클릭하세요. **활성화된 연동** 설정 페이지로 이동합니다.
4. **연동** 탭에서 **파트너 활성화**를 켭니다.  
   **참고: <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">파트너와 작업하는 동안에는 토글이 켜져 있어야 합니다(</Anchor><Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">활성화됨</Anchor>).**
5. 다음 섹션에 설명된 대로 관련 탭을 사용하여 구성을 완료하세요.

<div id="set-up-google-ads-web-in-appsflyer" />

## 앱스플라이어에서 Google Ads 웹 설정하기

설정의 이 부분에서는 Google Ads에 포스트백을 설정할 수도 있습니다. Google Ads 웹(googleads\_int) 연동은 광고주가 **PC 및 콘솔**앱의 데이터를 구글 서버로 직접 전송할 수 있도록 하는 Google Ads 제공 API 도구를 사용합니다. 이러한 데이터에는 비모바일 플랫폼(웹사이트 또는 애플리케이션)에서 실행된 구매, 등록 및 기타 전환 등의 사용자 행동이 포함될 수 있습니다. 그런 다음 Google Ads는 이 데이터를 사용하여 광고 타게팅을 최적화하고, 광고 성과를 측정하고, 리타게팅을 위한 맞춤 타겟을 구축합니다.

Google Ads 웹과의 연동은 설치 및 인앱 이벤트에 대한 포스트백 전송만 지원합니다.

<div id="integration-tab" />

<Accordion title="연동 탭">

**연동** 탭에는 아래 설명된 여러 섹션이 포함되어 있습니다.

<div id="activate-partner" />

#### 파트너 활성화

연동을 구성하려면 먼저 파트너 활성화 토글을 **켜야** 합니다.

<div id="general-settings" />

#### 일반 설정

<div id="note-1" />

> 📘 **참고**
>
> Google에 로그인하고 아래 단계에서 앱스플라이어가 토큰을 가져오도록 허용하면 **누락된 토큰** 오류 메시지가 더 이상 나타나지 않습니다. 로그인 후에도 오류가 지속되면 <Anchor target="_blank" href="/marketers/ko/docs/google-ads-adwords-create-web-based-campaigns#access-token-permissions">토큰에 필요한 권한이 있는지 확인하세요</Anchor>.

1. **첫 번째 오픈 전환 ID**: Google Ads에서 설정한 `First open` 전환 작업의 ID를 입력하세요. ID를 찾으려면:
   1. Google Ads 플랫폼으로 이동하여 **세부정보 탭**을 열고 **첫 번째 오픈** 전환 작업 페이지를 엽니다.
   2. 페이지 URL에서 `ctid=*` 쿼리 매개변수의 값을 복사합니다. 예를 들어, `ctid=123456789`인 경우 `123456789`을 **첫 번째 오픈 전환 작업 ID** 상자에 삽입합니다.
2. **고객 ID**를 입력합니다. Google Ads Manager에서 불러올 수 있습니다.
   1. Google Ads 계정에 로그인합니다.
   2. 오른쪽 상단에서 Google 계정 아이콘을 클릭하고 고객 ID가 표시되는 위치까지 아래로 스크롤합니다.
   3. 앱 캠페인을 운영하는 여러 Google Ads 계정이 있는 경우, 계정 간 전환 추적을 위해 관리자 계정(MCC)의 고객 ID를 사용해야 합니다. **MCC ID**를 **고객 ID** 텍스트 상자와 **MCC 고객 ID** 텍스트 상자(두 상자 모두 동일한 ID) 에 붙여넣으십시오.   
      광고를 실행하기 위해 단일 Google Ads 계정만 사용하는 경우, 계정 ID를 **고객 ID** 텍스트 상자에 붙여넣고 **MCC 고객 ID** 텍스트 상자는 비워 두십시오. <Anchor target="_blank" href="https://support.google.com/google-ads/answer/3061730?sjid=4528491462900554442-NC">MCC 계정 구성에 대한 Google 지침</Anchor>을 참조하세요.
3. 앱스플라이어가 Google Ads에 전환을 업로드할 수 있도록 하려면 **Google로 로그인**을 클릭하세요.
4. Google에서, 고객 ID를 불러온 MCC 계정의 관리자 계정을 선택하세요.
5. **허용**을 클릭합니다.

<div id="enable-view-through-attribution" />

#### 뷰-쓰루 어트리뷰션 활성화

앱스플라이어는 <Anchor target="_blank" href="/marketers/ko/docs/google-ads-adwords-create-web-based-campaigns#원링크-스마트-스크립트로-랜딩-페이지-만들기">스마트 스크립트</Anchor> 또는 <Anchor target="_blank" href="/marketers/ko/docs/google-ads-adwords-create-web-based-campaigns#원링크-스마트-배너로-랜딩-페이지-만들기">스마트 배너</Anchor>가 활성화된 랜딩 페이지를 사용하여 Google 웹 캠페인에 대한 뷰 스루 어트리뷰션을 지원합니다. 이는 사용자가 광고를 직접 클릭하지 않더라도 광고 노출에 의해 촉발된 앱 설치에 대한 확률적 모델링(PMOD) 어트리뷰션 분석을 가능하게 합니다.

사용자가 Google Ads를 보고 <Anchor target="_blank" href="/marketers/ko/docs/google-ads-adwords-create-web-based-campaigns#원링크-스마트-스크립트로-랜딩-페이지-만들기">스마트 스크립트</Anchor> 또는 <Anchor target="_blank" href="/marketers/ko/docs/google-ads-adwords-create-web-based-campaigns#set-up-a-smart-banners-landing-page">스마트 배너</Anchor>가 활성화된 랜딩 페이지에 도착하면, 앱스플라이어는 크로스 플랫폼에서 발생한 앱 인스톨을 원래 웹 노출로 역추적하여 어트리뷰션할 수 있습니다.

사용 가능한 경우, 앱스플라이어는 Google에 대한 포스트백에 `gclid`을 포함합니다.

**뷰-쓰루 어트리뷰션 활성화 방법:**

1. 앱스플라이어의 사이드바에서 **활성 연동** > **Google Ads 웹**를 엽니다.
2. **연동** 탭에서 **인스톨 어트리뷰션** 섹션으로 스크롤합니다.
3. **뷰-쓰루 어트리뷰션 인스톨**을 켭니다.
4. **[선택 사항]** **크로스 플랫폼 어트리뷰션 우선순위 동등하게 설정**을 켜고 룩백 윈도우를 설정합니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">크로스 플랫폼 노출에 대해 동일한 우선순위 활성화하기</Anchor> 항목을 참조하십시오.
5. **어트리뷰션** 탭을 엽니다.
6. **뷰-쓰루 어트리뷰션** 섹션으로 스크롤하여 선호하는 **뷰-쓰루 룩백 윈도우**를 설정합니다(최대 24시간).
7. 변경 사항을 적용하려면 **연동 저장**을 클릭합니다.

<div id="default-postbacks" />

#### 포스트백 디폴트 설정

인스톨에 대한 포스트백은 자동으로 Google Ads Web으로만 전송됩니다.

<div id="in-app-event-postbacks" />

#### 인앱이벤트 포스트백

Google Ads Web으로 전송된 인앱이벤트 포스트백의 매핑을 구성합니다. 이러한 이벤트는 Google Ads 관리자에서 확인할 수 있습니다.

1. **인앱이벤트 포스트백**을 켭니다.
2. **이벤트 추가**를 클릭하여 목록에 SDK 또는 서버-투-서버 이벤트를 추가하세요. 다음 표는 작성해야 할 필드를 설명합니다.

| 파라미터 이름 | 설명 |
| --- | --- |
| **앱스플라이어 이벤트** | 앱에 통합된 SDK 또는 서버 간 이벤트에서 앱스플라이어가 수신한 이벤트의 이름입니다.<ul><li>**항목 추가**를 클릭하고 이벤트 이름을 입력한 다음 ![check.png](https://files.readme.io/66d595d0ac8a01489ce810bbd3865fca2556342086dc6b20f26fa3d7b7e3afc2-19124971382289.png)를 클릭합니다.</li></ul> |
| **파트너 이벤트에 매핑** | 각 이벤트의 전환 작업 ID는 파트너 측에서 정의된 대로입니다.<ol><li><span class="af-ol-a"></span>Google Ads **전환 목표** 페이지에서 생성한 전환 작업을 클릭합니다.</li><li>전환 작업 **세부정보** 페이지에서, URL 매개변수 `ctId=`에서 **전환 작업 ID**를 복사합니다.</li><li>앱스플라이어로 돌아가서 붙여넣습니다. 예를 들어 `ctid=123456789`의 경우, `123456789`를 붙여넣습니다.</li></ol> |
| **사용자용** | **이 파트너만 해당:** **인앱 이벤트 포스트백은** 이 파트너에게 귀속된 이벤트에 대해서만 전송됩니다. 즉, 해당 이벤트를 수행한 사용자가 해당 파트너를 통해 유입된 경우에만 해당됩니다. |
| **포함** | **가치 및 수익:** 수익 값(이벤트에 존재하는 경우)을 포함한 모든 이벤트 파라미터가 포스트백으로 전송됩니다. |

3. [선택 사항] 이벤트에 대한 <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#조건부-인앱-이벤트-포스트백">조건을 설정</Anchor>하려면 **조건 추가altconditional-iae-postbacks-icon.pngalt아이콘을 클릭하세요.**
4. 필요한 경우 **인앱 이벤트 포스트백 기간**을 설정합니다(<Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#인앱-이벤트-포스트백-기간">인앱 이벤트 포스트백 윈도우 구성</Anchor>에 대해 자세히 알아보세요).
5. **연동 저장**을 클릭하세요.
6. [선택 사항] 연동을 저장한 후 구성 페이지에 남아 있는 동안 더 많은 앱을 파트너와 연동할 수 있습니다.
   1. 왼쪽 상단 모서리의 파트너 이름 아래에서 앱 이름을 클릭하면 앱 목록이 열립니다.
   2. 드롭다운 목록에서 다른 앱을 선택합니다.
   3. 선택한 앱에 대해 연동 단계를 반복합니다.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="어트리뷰션 링크 탭">

앱스플라이어 UI에서 어트리뷰션 링크를 생성하는 기능은 현재 제공되지 않습니다. 그러나 SmartScript와 함께 크로스 플랫폼 방문 페이지를 사용하거나 앱에 대한 직접 기여 분석 링크를 만들 수 있습니다(아래 표 참조).

| 옵션 | 작업 | 담당자 |
| --- | --- | --- |
| 크로스 플랫폼 랜딩 페이지 | **권장 사항**: 여러 플랫폼(예: 에픽 게임 스토어와 스팀)에서도 이용 가능한 앱을 캠페인에서 홍보하는 경우<br /><br /><Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">크로스 플랫폼 랜딩 페이지에 대해 알아보기</Anchor><br /><br /><Anchor target="_blank" href="/marketers/ko/docs/cross-platform-landing-pages-with-smart-script">크로스 플랫폼 랜딩 페이지를 설정하는 방법 알아보기</Anchor><ul><li>모든 관련 URL 파라미터(나중에 스마트 스크립트에 의해 캡처됨)가 광고 URL에 추가되었는지 확인합니다.</li><li>스크립트가 수신 URL에서 GCLID를 가져와 생성된 링크에 추가하는지 확인합니다. 즉, 발신 FBCLID URL 파라미터 `gclid`를 수신 URL 파라미터 `gclid`에 매핑합니다. **참고**! `gclid`앱스플라이어 로데이터 리포트에 표시하려면, 수신 `gclid` 파라미터가 발신 파라미터 **중 하나에 매핑되어야 합니다.gclid`gclid`**</li></ul> | 마케터(개발자 지원이 필요할 수 있음) |
| 다이렉트 어트리뷰션 링크 | 하나의 플랫폼에 하나의 앱만 있기 때문에 크로스 플랫폼 랜딩 페이지를 사용하지 않는 경우, 직접 어트리뷰션 링크를 생성하여 광고 뒤에 배치할 수 있습니다.<br /><br /><Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-platform-direct-attribution-links">직접 어트리뷰션 링크를 만드는 방법 알아보기</Anchor><ul><li>다음 파라미터가 링크에 포함되어 있는지 확인합니다.<ul><li>af\_media\_source</li><li>af\_campaign\_id</li><li>af\_r<br />**참고**: <Anchor target="_blank" href="https://support.google.com/google-ads/answer/3095550?hl=en">자동 태깅</Anchor>을 사용하는 경우, Google Ads는 모든 아웃바운드 클릭에 <Anchor target="_blank" href="https://support.google.com/google-ads/answer/9744275?hl=en">Google 클릭 식별자(GCLID)</Anchor>매개변수를 자동으로 추가합니다. Google Ads 계정에서 자동 태깅이 비활성화된 경우 Google Ads 추적 템플릿 URL에 `gclid={gclid}`를 추가합니다.</li></ul></li><li>af\_camapign\_id, af\_adset\_id 및 af\_ad\_id 파라미터의 경우 구글의 [값 추적 파라미터](https://support.google.com/google-ads/answer/6305348)(동적 URL 파라미터) 매크로를 사용할 수 있습니다. 다른 모든 파라미터는 수동으로 설정해야 합니다.</li><li>af\_dp 파라미터를 포함하지 마십시오.</li></ul>**대부분의 플랫폼(Epic, Steam, Xbox, PlayStation 등)에 사용할 템플릿**:<br /><br />`https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}? af_media_source=googleads_int&af_campaign_id={campaignid}&af_campaign=ACTUAL_CAMPAIGN_NAME&af_adset=ACTUAL_ADGROUP_NAME&af_adset_id={adgroupid}&af_ad_id={creative}&af_r={lpurl}`<br /><br />**Steam으로 연결되는 샘플 링크**: `https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=googleads_int&af_campaign_id={campaignid}&af_campaign=campaign1&af_adset=adgroup1&af_adset_id={adgroupid}&af_ad_id={creative}&af_r={lpurl}`<br /><br />**구글 PC 및 Mac 앱에서만 사용할 템플릿**:<br /><br />`https://app.appsflyer.com/{app_id}?af_media_source=googleads_int&af_campaign_id={campaignid}&af_campaign=ACTUAL_CAMPAIGN_NAME&af_adset=ACTUAL_ADGROUP_NAME&af_adset_id={adgroupid}&af_ad_id={creative}&af_r={lpurl}`<br /><br />**구글 PC로 연결되는 샘플 링크**: `https://app.appsflyer.com/123456?af_media_source=googleads_int&af_campaign_id={campaignid}&af_campaign=campaign1&af_adset=adgroup1&af_adset_id={adgroupid}&af_ad_id={creative}&af_r={lpurl}` | 마케터 |

<div id="tip" />

> 👍 **팁**
>
> 캠페인 분석을 단순화하기 위해 캠페인 이름에 캠페인 유형(웹 또는 모바일)을 접두사 또는 접미사로 포함하십시오(예: 캠페인-이름\_web)

</Accordion>

<div id="set-up-campaigns-in-google-ads-web-for-pc-and-console-apps" />

## Google Ads 웹에서 PC 및 콘솔 앱용 캠페인 설정하기

새 캠페인을 설정할 때 사용자를 다음 중 하나로 안내할 수 있습니다.

* 크로스 플랫폼 랜딩 페이지: 캠페인에서 Epic 및 Steam과 같은 여러 플랫폼에서도 사용할 수 있는 앱을 홍보하는 경우에 권장됩니다.
* 단일 스토어: 이는 다이렉트 어트리뷰션 링크를 사용하며 플랫폼 1개에 앱이 1개뿐인 경우에 사용해야 합니다.

사용자를 이러한 옵션 중 하나로 리디렉션하도록 캠페인을 설정하는 방법은 다음 섹션에 자세히 설명되어 있습니다.

**참고**: 캠페인 설정 중에 전환 작업과 목표를 직접 구성할 수 있습니다. 이 작업을 수행하는 방법에 대한 지침은 다음 섹션에도 자세히 설명되어 있습니다.

<div id="campaigns-that-redirect-to-a-crossplatform-landing-page" />

<Accordion title="크로스 플랫폼 랜딩 페이지로 리디렉션되는 캠페인">

**사용자를 크로스 플랫폼 랜딩 페이지로 리디렉션하는 캠페인을 설정하는 방법**:

1. [어트리뷰션 링크 섹션](/docs/google-ads-web-integration-for-pc-and-console-apps#attribution-link-tab)에 설명된 대로 크로스 플랫폼 랜딩 페이지를 설정합니다.
2. Google Ads에 로그인하고 새 캠페인을 만듭니다.
3. 캠페인 목표를 선택합니다.  
   [![](https://files.readme.io/c0d45f4b5ac9221b0d97ba8c8aa4eabbddccf11b9cf959ab0d9776e8766d0414-21939144104337.png)](https://files.readme.io/c0d45f4b5ac9221b0d97ba8c8aa4eabbddccf11b9cf959ab0d9776e8766d0414-21939144104337.png)
   * “앱 프로모션"(모바일 앱 캠페인에만 사용 가능)을 제외한 모든 목표가 적용됩니다.
   * 특정 인앱 이벤트를 기반으로 최적화하려면 “판매” 캠페인 목표를 설정하는 것이 좋습니다.
4. 전환 이벤트를 선택합니다.  
   [![](https://files.readme.io/e63ad3f0db65f9a3b562e7c5aea2d7bad481af73cfaebdfb1f9f4d3d5f0365d1-21939173772177.png)](https://files.readme.io/e63ad3f0db65f9a3b562e7c5aea2d7bad481af73cfaebdfb1f9f4d3d5f0365d1-21939173772177.png)
   * 기본적으로, 사전 정의된 계정 수준의 캠페인 목표가 표시됩니다. 이들 목표를 보관하거나 캠페인과 관련 없는 목표는 삭제할 수 있습니다.
   * 원하는 목표가 보이지 않으면 [전환 작업과 전환 목표를 추가하세요](/docs/google-ads-web-integration-for-pc-and-console-apps#creating-conversion-actions-and-goals).
   * 전환 페이지에서 사전 정의된 목표를 편집할 수도 있습니다.
5. 캠페인 유형을 선택합니다.  
   [![](https://files.readme.io/c320f649f253532425be3c760009e652a8f626a4c10ed2527308df9a7030bb5b-21939144113937.png)](https://files.readme.io/c320f649f253532425be3c760009e652a8f626a4c10ed2527308df9a7030bb5b-21939144113937.png)
   * 제품 카탈로그가 필요하고 인증된 도메인으로 제한되는 “쇼핑”을 제외한 모든 캠페인 유형이 적용됩니다.
6. 크로스 플랫폼 랜딩 페이지 URL을 구글의 최종 URL로 입력합니다.

</Accordion>

<div id="campaigns-that-redirect-to-a-single-app-store" />

<Accordion title="단일 앱 스토어로 리디렉션되는 캠페인">

**유저를 단일 플랫폼 및 앱 스토어로 리디렉션하는 캠페인을 설정하는 방법**:

1. [어트리뷰션 링크 섹션](/docs/google-ads-web-integration-for-pc-and-console-apps#attribution-link-tab)에 설명된 대로 다이렉트 어트리뷰션 링크를 설정합니다.
2. Google Ads에 로그인하고 새 캠페인을 만듭니다.
3. 캠페인 목표를 선택합니다.  
   [![](https://files.readme.io/c0d45f4b5ac9221b0d97ba8c8aa4eabbddccf11b9cf959ab0d9776e8766d0414-21939144104337.png)](https://files.readme.io/c0d45f4b5ac9221b0d97ba8c8aa4eabbddccf11b9cf959ab0d9776e8766d0414-21939144104337.png)
   * “앱 프로모션"(모바일 앱 캠페인에만 사용 가능)을 제외한 모든 목표가 적용됩니다.
   * 특정 인앱 이벤트를 기반으로 최적화하려면 “판매” 캠페인 목표를 설정하는 것이 좋습니다.
4. 전환 이벤트를 선택합니다.  
   [![](https://files.readme.io/e63ad3f0db65f9a3b562e7c5aea2d7bad481af73cfaebdfb1f9f4d3d5f0365d1-21939173772177.png)](https://files.readme.io/e63ad3f0db65f9a3b562e7c5aea2d7bad481af73cfaebdfb1f9f4d3d5f0365d1-21939173772177.png)
   * 기본적으로, 사전 정의된 계정 수준의 캠페인 목표가 표시됩니다. 이들 목표를 보관하거나 캠페인과 관련 없는 목표는 삭제할 수 있습니다.
   * 원하는 목표가 보이지 않으면 [전환 작업과 전환 목표를 추가하세요](/docs/google-ads-web-integration-for-pc-and-console-apps#creating-conversion-actions-and-goals).
   * 전환 페이지에서 사전 정의된 목표를 편집할 수도 있습니다.
5. 캠페인 유형을 선택합니다.  
   [![](https://files.readme.io/c320f649f253532425be3c760009e652a8f626a4c10ed2527308df9a7030bb5b-21939144113937.png)](https://files.readme.io/c320f649f253532425be3c760009e652a8f626a4c10ed2527308df9a7030bb5b-21939144113937.png)
   * 제품 카탈로그가 필요하고 인증된 도메인으로 제한되는 “쇼핑”을 제외한 모든 캠페인 유형이 적용됩니다.
6. 구글의 최종 URL로 사용할 링크를 입력합니다.
   * 이는 유저를 리디렉션하려는 최종 웹 위치여야 합니다. 웹 랜딩 페이지 또는 스토어 URL을 포함한 어떤 웹 URL이든 될 수 있습니다. 예: `https://store.steampowered.com/app/{appid}/{myapp}/`.
   * 최종 URL은 앱스플라이어 URL이 될 수 없습니다. 그러면 캠페인이 거부될 수 있기 때문입니다. 리디렉션이 없는 다이렉트 웹 주소만 사용하십시오.
7. 앱스플라이어 다이렉트 어트리뷰션 링크를 구글의 추적 템플릿 URL로 입력합니다.
   * 병렬 추적이 의도한 대로 작동하려면 구글에서 지정한 대로 구글 추적 템플릿 URL의 `{lpurl}` ValueTrack 파라미터에 최종 URL을 입력해야 합니다.
   * af\_dp 파라미터를 포함하지 마십시오.

</Accordion>

<div id="creating-conversion-actions-and-goals" />

<Accordion title="전환 작업 및 목표를 생성합니다.">

Google Ads에서는 미리 정의된 전환 작업 및 목표 목록에서 선택하거나 직접 만들 수 있습니다.

**중요!** 앱스플라이어가 "첫 번째 열기" 이벤트 포스트백을 보내려면 전환 작업을 생성하고 이름을 "첫 번째 열기"로 지정해야 합니다.

**나만의 Google Ads 전환 작업 및 목표 생성 방법**:

1. Google Ads 계정 개요 페이지의 사이드 메뉴에서 **목표** > **전환** > **요약**을 선택합니다.
2. **+ 새 전환 작업**을 클릭합니다.
3. 전환 작업 데이터 소스로 **오프라인 전환**을 선택하십시오.
4. 전환 유형 목록에서 **가져오기**를 선택한 다음 **API를 사용한 수동 가져오기 또는 업로드** > **클릭으로 인한 전환 추적**을 선택합니다.

   <div id="note-2" />

   > 📘 **참고**
   >
   > **API 또는 업로드를 사용한 수동 가져오기**가 사용 불가능한 경우:
   >
   > 1. <span class="af-ol-a"></span>**CRM, 파일 또는 기타 데이터 소스**을 선택하고 **클릭으로 인한 전환 추적**을 선택합니다.
   > 2. **데이터 소스**에서 **이 단계를 건너뛰고 나중에 데이터 소스소스 설정**을 선택합니다.

5. **계속**을 클릭하세요.  
   양식이 표시됩니다.
6. 양식을 작성하고 **만들기와 계속**을 클릭하여 전환 트래커 생성을 완료하세요.
7. **목표 및 작업 최적화**의 경우 전환 작업을 매핑할 카테고리를 선택합니다.  
   **참고**: Google Ads 캠페인 최적화는 특정 작업별이 아니라 카테고리별로 진행됩니다. 캠페인을 단일 작업에만 최적화하려면 해당 작업만 이 카테고리에 매핑해야 합니다. 예를 들어 캠페인을 '인스톨' 작업에 맞게 최적화하려면 '인스톨' 작업을 자체 카테고리(예: '기타')에 매핑해야 합니다. 그런 다음 캠페인 생성 시 캠페인 목표로 이 카테고리를 선택할 수 있게 됩니다.
8. Google Ads에서 전환 작업 ID를 복사하고 **파트너 이벤트에 매핑됨** 필드에 입력합니다. **전환 작업 ID**는 앱스플라이어 이벤트 이름을 인앱 이벤트 포스트백 설정에서 파트너 이벤트 ID에 매핑할 때, 파트너 이벤트 ID로 사용됩니다. Google Ads에서 전환 작업 ID를 복사하려면 다음을 수행하십시오:
   1. <span class="af-ol-a"></span>Google Ads **전환 목표** 페이지에서 생성한 전환 작업을 클릭합니다.
   2. 전환 작업 **세부정보** 페이지에서, URL 매개변수 `ctId=`에서 **전환 작업 ID**를 복사합니다.
9. **만들기 및 계속**을 클릭합니다.
10. **마침**을 클릭합니다.

</Accordion>

<div id="view-web-to-app-attribution-data-from-november-2-2025" />

## 웹-앱 귀속 데이터를 확인하십시오(2025년 11월 2일부터)

웹 기반 전환 이벤트는 원래 `googleads_int` PID로 Google에 전송되지만, AppsFlyer 대시보드 및 원시 데이터 보고서에서는 `googleadwords_int` PID 아래에 보고됩니다. 이는 기본 전환 이벤트와 전환 보조 이벤트 모두에 적용됩니다.

이 통합 보고 뷰를 통해 웹과 앱 캠페인 성과를 한 곳에서 분석할 수 있으며, 전체 모바일 및 웹 비용 보고를 포함합니다.

<div id="view-in-the-dashboard" />

### 대시보드에서 보기

모든 Google 웹-앱 귀속은 개요 및 활동 대시보드의 `googleadwords_int` 아래에 나타납니다. 이는 플랫폼 전반에 걸쳐 캠페인 결과의 단일 통합 뷰를 제공합니다. 표준 필터와 분류를 사용하여 Google Ads 데이터 내에서 앱과 웹 트래픽을 비교하십시오.

<div id="view-in-raw-data-and-api-reports" />

### 원시 데이터 및 API 보고서에서 보기

* **원시 데이터 내보내기 및 API 응답**은 Google 웹 활동을 위한 `media_source` 필드에 `googleadwords_int` PID를 포함합니다. 웹 캠페인 설정 세부정보를 확인하려면 웹 캠페인 생성 시 사용된 PID로 `googleads_int`를 표시하는 `original_url` 필드를 참조하십시오.
* **포스트백 보고서**는 포스트백이 전송된 원래 미디어 소스로 `googleads_int`를 보여줍니다.

<div id="traits-and-limitations" />

## 특징 및 제약 사항

| 특징 | 설명 |
| --- | --- |
| 클릭 및 노출(임시 제한) | PC 및 콘솔 앱을 대상으로 하는 캠페인의 클릭 및 노출은 Google SRN(`googleadwords_int`)에서 일시적으로 사용할 수 없습니다. |

<div data-zendesk-anchors="h_01JP7SMGEPTQGHRYYCBWECH46X=%EC%B0%B8%EA%B3%A0 overview=%EA%B0%9C%EC%9A%94 h_01HK4QHRJG6WTN9P6ZG83XQ6AY=%EA%B0%9C%EC%9A%94 prerequisites=%ED%95%84%EC%88%98-%EC%A1%B0%EA%B1%B4 h_01HFXV8HPGCRGYPEW0NPJ0NR0S=%ED%95%84%EC%88%98-%EC%A1%B0%EA%B1%B4 activate-partner=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%97%90%EC%84%9C-%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 h_01HFXV8HPH3N4DBKKTQE6DK7FK=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%97%90%EC%84%9C-%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 setting-up-metaweb-in-appsflyer=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%97%90%EC%84%9C-google-ads-%EC%9B%B9-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 01H88VAJH3VENKYVRQY5RXN63P=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%97%90%EC%84%9C-google-ads-%EC%9B%B9-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 01H88VAJH3VZ4GPVE7XXMKTZ2P=integration-tab activate-partner::1ca30957=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 h_01HFXV8HPH6X92YETNAGZ910AV=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 transaction-id=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 h_01HARQDVEDA206D0BBXBC6WEHH=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 h_01JK8XJJWQK5MEJF7GTC5C1707=%EC%B0%B8%EA%B3%A0-1 enable-viewthrough-attribution=%EB%B7%B0-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%99%9C%EC%84%B1%ED%99%94 h_01ZXVWB0GZKWB53KTBWJ51RMBM=%EB%B7%B0-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%99%9C%EC%84%B1%ED%99%94 default-postbacks=%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EB%94%94%ED%8F%B4%ED%8A%B8-%EC%84%A4%EC%A0%95 01H88VAJH3WE9Z0971WMBRBJRS=%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EB%94%94%ED%8F%B4%ED%8A%B8-%EC%84%A4%EC%A0%95 inapp-event-postbacks=%EC%9D%B8%EC%95%B1%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 01H88VAJH3AS37MVF75GANWX4B=%EC%9D%B8%EC%95%B1%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 01H88VAJH31GZ4KAY280ZRB8MA=attribution-link-tab h_01K88M617Q7SVMDEKP5HTKANJM=%ED%8C%81 setting-up-campaigns-in-meta-web-for-pc-and-console-apps=google-ads-%EC%9B%B9%EC%97%90%EC%84%9C-pc-%EB%B0%8F-%EC%BD%98%EC%86%94-%EC%95%B1%EC%9A%A9-%EC%BA%A0%ED%8E%98%EC%9D%B8-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 h_01HK4S03KVAN99YKXTHAKCT420=google-ads-%EC%9B%B9%EC%97%90%EC%84%9C-pc-%EB%B0%8F-%EC%BD%98%EC%86%94-%EC%95%B1%EC%9A%A9-%EC%BA%A0%ED%8E%98%EC%9D%B8-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 h_01HMR6HVJF4QT1EZKYZKRVTWEE=campaigns-that-redirect-to-a-crossplatform-landing-page h_01HMR6HVJFMN1V7VM58ZMQFEXF=campaigns-that-redirect-to-a-single-app-store h_01HMTXEZB3W19TKK8ZR6JK2TPG=creating-conversion-actions-and-goals h_01HV6FR2TFYT11H9EVT9Y9TZ3S=%EC%B0%B8%EA%B3%A0-2 google%20view-web-to-app=%EC%9B%B9-%EC%95%B1-%EA%B7%80%EC%86%8D-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%A5%BC-%ED%99%95%EC%9D%B8%ED%95%98%EC%8B%AD%EC%8B%9C%EC%98%A42025%EB%85%84-11%EC%9B%94-2%EC%9D%BC%EB%B6%80%ED%84%B0 view-webtoapp-attribution-data-from-november-2-2025=%EC%9B%B9-%EC%95%B1-%EA%B7%80%EC%86%8D-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%A5%BC-%ED%99%95%EC%9D%B8%ED%95%98%EC%8B%AD%EC%8B%9C%EC%98%A42025%EB%85%84-11%EC%9B%94-2%EC%9D%BC%EB%B6%80%ED%84%B0 h_01K88H6ETM23EV0PTR8GS13KRN=%EC%9B%B9-%EC%95%B1-%EA%B7%80%EC%86%8D-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%A5%BC-%ED%99%95%EC%9D%B8%ED%95%98%EC%8B%AD%EC%8B%9C%EC%98%A42025%EB%85%84-11%EC%9B%94-2%EC%9D%BC%EB%B6%80%ED%84%B0 view-in-the-dashboard=%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C%EC%97%90%EC%84%9C-%EB%B3%B4%EA%B8%B0 h_01K88H6ETMG7007CJ0ADD8VQH4=%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C%EC%97%90%EC%84%9C-%EB%B3%B4%EA%B8%B0 view-in-raw-data-and-api-reports=%EC%9B%90%EC%8B%9C-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B0%8F-api-%EB%B3%B4%EA%B3%A0%EC%84%9C%EC%97%90%EC%84%9C-%EB%B3%B4%EA%B8%B0 h_01K88H6ETM502Z2XDC63602FGD=%EC%9B%90%EC%8B%9C-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B0%8F-api-%EB%B3%B4%EA%B3%A0%EC%84%9C%EC%97%90%EC%84%9C-%EB%B3%B4%EA%B8%B0 traits-and-limitations=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD h_01KB5085FX7G6Y5E200KVH0ABJ=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD" />
