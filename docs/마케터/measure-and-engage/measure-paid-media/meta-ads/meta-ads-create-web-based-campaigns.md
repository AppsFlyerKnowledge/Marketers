---
title: Meta 광고용 웹 기반 캠페인 생성
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2024-06-04T16:08:28Z'
  edited_at: '2026-10-14T10:29:02Z'
  id: 25646834966033
  locale: ko
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/ko/articles/25646834966033
---
> **요약:** Meta 광고 웹 캠페인을 사용하여 Meta 광고의 웹-to-앱 전환 측정

## 개요

앱스플라이어는 사용자 유입 웹 기반 캠페인을 위해 Meta 광고 (`metaweb_int`)와의 연동을 지원하며, 이로써 Meta의 Conversion API(CAPI)를 통해 직접 어트리뷰션 및 전환 데이터를 보고할 수 있습니다. 그런 다음 Meta는 해당 데이터를 활용하여 광고 타겟팅을 최적화하고, 성과를 측정하며, 오디언스를 커스텀하여 구축할 수 있습니다.

> 📘 **참고**
>
> 현재 Meta 웹과의 연동은 CAPI로의 리인게이지먼트 포스트백 전송을 지원하지 않습니다.

### 필수 조건

Meta 광고 연동을 활성화하기 전에 [Meta Business Manager에 비즈니스 계정이](https://www.facebook.com/business/help/1710077379203657?id=180505742745347) 있는지 확인하십시오.

### Meta 웹 광고 캠페인을 만드는 방법

이 문서에는 앱스플라이어를 사용하여 모바일, PC 및 콘솔 앱용 Meta 광고에서 웹 캠페인을 설정하는 방법에 대한 정보와 단계가 포함되어 있습니다. 설정에는 Meta 광고와 앱스플라이어의 연동 정의, 두 플랫폼 모두에서 캠페인 설정, 원링크 스마트 스크립트 또는 원링크 스마트 배너를 사용하는 랜딩 페이지 생성 등이 포함됩니다.  
설정 프로세스에는 다음과 같은 필수 단계가 포함됩니다.

* [앱스플라이어에서 Meta 웹 광고 연동 설정](#앱스플라이어에서-meta-웹-광고-연동-설정) (필수)
* [Meta 광고에서 앱스플라이어 연동 설정하기](#meta-광고에서-앱스플라이어-연동-설정하기) (필수)

그리고 선택적 단계는 다음과 같습니다.

* [OneLink Smart Script로 랜딩 페이지 만들기](#원링크-스마트-스크립트로-랜딩-페이지-만들기) (선택 사항)
* [OneLink Smart Banners로 랜딩 페이지 만들기](#원링크-스마트-배너로-랜딩-페이지-만들기) (선택 사항)

## 앱스플라이어에서 Meta 웹 광고 연동 설정

먼저 Meta 광고 연동을 활성화하고 앱스플라이어가 CAPI에 보내는 포스트백을 설정합니다.

<div id="a-activate-the-meta-ads-integration" />

<Accordion title="1. Meta 웹 광고 통합 활성화하기">

Meta 웹 광고 통합을 활성화하려면 다음 단계를 따르세요.

1. 앱스플라이어의 사이드 메뉴에서**협업**>**파트너 마켓플레이스**로 이동합니다.
2. **Meta 웹**을 검색하여 선택합니다.
3. **연동 설정**을 클릭합니다. **활성 연동** 설정 페이지로 이동합니다.
4. **연동** 탭에서 **파트너 활성화**를 선택합니다. **참고:** 파트너와 함께 작업하는 동안에는 토글이 켜져 있어야(<Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">활성화</Anchor>) 합니다.
5. **고급 개인 정보 보호** (iOS 앱 통합을 설정하는다 경우)를 끕니다.
6. **픽셀 ID** 필드를 입력합니다. Meta 광고 관리자에서 픽셀 ID를 검색할 수 있습니다.
   1. [광고 관리자](https://www.facebook.com/ads/manager) 사이드 메뉴에서 **모든 도구** > **이벤트 관리자**로 이동합니다. **참고:** 오른쪽 상단의 드롭다운에서 올바른 비즈니스를 선택했는지 확인합니다.
   2. **이벤트 관리자** 사이드 메뉴에서 **데이터 소스**를 선택하면, 픽셀 목록이 표시됩니다. 선택한 비즈니스에 대한 픽셀이 없는 경우 동일한 화면에서 픽셀을 생성할 수 있습니다.
   3. 픽셀 이름 아래에 표시되는 픽셀 ID를 복사합니다.  
      그리고 다음에 붙여 넣습니다.  
      앱스 플라이어 **픽셀 ID** 필드.
7. **액세스 토큰** 필드를 입력합니다. 액세스 토큰을 검색하려면 다음 [지침](https://developers.facebook.com/docs/marketing-api/conversions-api/get-started#access-token)을 따르십시오.
8. **Meta 광고의 사용자 개인 정보 사용 제한(CCPA)** 을 켜면 <Anchor target="_blank" href="/marketers/ko/docs/send-opendsr-api-requests">데이터 보호법</Anchor> 준수할 수 있습니다. **참고:** CCPA 개인정보 보호 규정을 준수함으로써, 캘리포니아에 거주하는 Meta 광고 사용자로부터 수집되는 데이터가 제한됩니다.

</Accordion>

<div id="d-enable-view-through-attribution-for-meta-web" />

<Accordion title="2. 뷰-쓰루 어트리뷰션 활성화">

앱스플라이어는 [스마트 스크립트](#set-up-smart-script-crossplatform-landing-page) 또는 [스마트 배너](#set-up-smart-banners-landing-page)가 활성화된 랜딩 페이지를 사용하여 Meta 웹 캠페인의 뷰-쓰루 어트리뷰션을 지원합니다. 이는 사용자가 광고를 직접 클릭하지 않더라도 광고 노출에 의해 촉발된 앱 설치에 대한 확률적 모델링(PMOD) 어트리뷰션 분석을 가능하게 합니다.

사용자가 Meta 웹 광고를 클릭하여 [스마트 스크립트](#set-up-smart-script-crossplatform-landing-page) 또는 [스마트 배너](#set-up-smart-banners-landing-page)가 활성화된 랜딩 페이지에 도달하면, 앱스플라이어는 다운스트림 앱 설치를 어트리뷰션할 수 있습니다. 가능한 경우, Meta로의 포스트백에 해당 `fbclid`이 포함되어 어트리뷰션 정확도를 향상시킵니다.

**Meta 웹 뷰-쓰루 어트리뷰션을 활성화 하려면:**

1. 앱스플라이어 홈 사이드바에서 **활성 연동** > **Meta 웹 광고를** 엽니다.
2. **연동** 탭에서 **인스톨 어트리뷰션** 섹션으로 스크롤합니다.
3. **뷰-쓰루 어트리뷰션 설치**를 켭니다.
4. **[선택 사항]** **크로스 플랫폼 어트리뷰션 우선순위 동등하게 설정**을 켜고 룩백 윈도우를 설정합니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">크로스 플랫폼 노출에 대해 동일한 우선순위 활성화하기</Anchor> 항목을 참조하십시오.
5. **어트리뷰션 링크** 탭을 클릭합니다.
6. **뷰-쓰루 어트리뷰션** 섹션으로 스크롤하여 **뷰-쓰루 룩백 윈도우**를 설정합니다(최대 24시간).
7. 설정을 적용하려면 **연동 저장** 을 클릭합니다.

</Accordion>

<div id="b-set-inapp-event-postbacks" />

<Accordion title="3. 인앱이벤트 포스트백 설정">

설치는 현재 Meta 광고에 대한 자동 기본 포스트백을 트리거하는 유일한 이벤트입니다. 다른 이벤트 유형의 경우, 앱스플라이어 이벤트를 Meta 광고 이벤트에 매핑하여 사용자 정의 포스트백을 생성할 수 있으며, 이는 [Meta 이벤트 관리자](https://www.facebook.com/business/help/1541268312717919?id=818859032317965)에서 볼 수 있습니다.  
인앱 이벤트 포스트백을 설정하려면 다음을 수행합니다.

1. **인앱 이벤트 포스트백**을 켭니다.
2. 필요한 경우 인앱 이벤트 포스트백 창을 설정합니다(인앱 이벤트 포스트백 창 구성에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#인앱-이벤트-포스트백-기간">이 글</Anchor>을 참고하세요).
3. **이벤트 추가**을 클릭하여 목록에 이벤트를 추가합니다.
4. **앱스플라이어 이벤트** 열의 드롭다운 상자에서 이벤트 이름을 선택합니다. 앱에 통합된 SDK 또는 서버 간 이벤트에서 앱스플라이어가 수신한 이벤트의 이름입니다.
5. **파트너 이벤트에 매핑됨** 열에서 드롭다운 상자에서 가장 적합한 사전 정의된 파트너 이벤트를 선택하거나 CUSTOM을 선택합니다.
6. **for users from:** 열에서 이벤트에 대해 전송 옵션을 선택합니다.
   * **이 파트너에게만 전송**: 이벤트가 Meta Ads에 어트리뷰션된 경우에만 포스트백을 전송합니다.
   * **오가닉을 포함한 모든 미디어 소스**: 파트너 및 오가닉 이벤트에 어트리뷰트된 이벤트에 대한 포스트백을 전송합니다.
7. **포함** 열에서 이벤트가 수익 값과 함께 전송될지 여부를 선택합니다. <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#포스트백에-포함할-데이터">포스트백에 포함할 데이터</Anchor> 참조

   > 📘 **참고**
   >
   > 구매 이벤트를 설정하는 경우, **포함** 열을 **값 및 수익**으로 설정합니다. 다른 옵션을 선택하면 포스트백이 실패하게 됩니다.

8. [선택 사항] **조건 추가** 아이콘을 클릭하여 이벤트에 대한 <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#조건부-인앱-이벤트-포스트백">조건을 설정</Anchor>합니다.
9. **연동 저장**을 클릭합니다.
10. [선택 사항] 연동을 저장한 후 설정 페이지에 남아 있는 동안 더 많은 앱을 파트너와 연동할 수 있습니다.
    1. 왼쪽 상단에서 파트너 이름 아래의 앱 이름을 클릭하여 앱 목록을 엽니다.
    2. 드롭다운 목록에서 다른 앱을 선택합니다.
    3. 선택한 앱에 대해 연동 단계를 반복합니다.

</Accordion>

## Meta 광고에서 앱스플라이어 연동 설정하기

Meta 광고 관리자에서 다음 단계를 수행합니다.

<div id="a-set-the-campaign-type-objective-and-goals" />

<Accordion title="1. 캠페인 유형, 목표, 목표를 설정합니다">

1. Meta 광고에 로그인하고 캠페인을 만듭니다.
2. **캠페인 목표**에서 다음 중 하나를 선택합니다: [![](https://files.readme.io/a0cdd42ddf3bc69106de5137e5c842468178bd1dcd76805ea77ead750ba1e9bb-25646834955921.png)](https://files.readme.io/a0cdd42ddf3bc69106de5137e5c842468178bd1dcd76805ea77ead750ba1e9bb-25646834955921.png)
   * **매출**: 이를 통해 Meta는 특정 이벤트(주요 KPI)에 대해 최적화할 수 있습니다.
   * **트래픽**: 이를 통해 Meta는 광고 클릭에 대해 최적화할 수 있습니다. 다른 KPI가 없거나, KPI 이벤트의 볼륨이 너무 낮은 경우에만 이 옵션을 사용합니다.
3. [선택 사항] 위의 옵션에 사용자 지정 목표를 추가하려면 다음을 수행합니다.
   1. Meta 광고에서 캠페인 목표로 설정하려는 맞춤 이벤트를 선택하고 Meta 광고에서 전환 행동으로 표시합니다.
   2. 앱스플라이어 **Meta 웹 연동** 페이지 **인앱 이벤트 포스트백**탭에서 앱스플라이어 이벤트를 사용자 지정 파트너 이벤트에 매핑하고(**파트너 이벤트에 매핑** 열), Meta 광고의 전환 액션과 동일한 이름으로 지정합니다.

      > 📘 **참고**
      >
      > Meta 캠페인 목표에 대한 자세한 내용은 [Meta 문서](https://www.facebook.com/business/help/175683976191028)를 참고하세요.

4. **전환 위치**에서 **웹 사이트**를 선택합니다.
5. **픽셀**에서 앱스플라이어 파트너 마켓플레이스에 `metaweb_int`에 입력한 것과 동일한 픽셀 ID를 입력합니다. Meta 픽셀에 대해 자세히 알아보려면 [Meta 문서](https://www.facebook.com/business/help/742478679120153)를 참조하세요(로그인 필요).
6. **다음**을 클릭합니다.

</Accordion>

<div id="b-set-destination-url" />

<Accordion title="2. 도착 URL 설정">

1. **목적지 아래의 웹사이트 URL필드에서, 광고의 목적지 역할을 하는 URL을 입력하세요. URL은 다음 중 하나여야 합니다.**

   [![](https://files.readme.io/aec9109f2f3000f669799093460e70198de1934e483314b6cd7f95d8209f361d-25646834955537.png)](https://files.readme.io/aec9109f2f3000f669799093460e70198de1934e483314b6cd7f95d8209f361d-25646834955537.png)

   * **웹 랜딩 페이지:** 다음과 같은 경우 랜딩 페이지를 사용하는 것이 좋습니다.

     * 앱이 여러 플랫폼에 존재합니다.
     * 랜딩 페이지를 사용하여 광고된 제품에 대한 자세한 정보를 제공하려고 합니다.
     * 랜딩 페이지를 사용하여 더 많은 데이터를 수집하려고 합니다.

     이러한 모든 사용 사례에 대해 [스마트 스크립트가 있는 랜딩 페이지](#원링크-스마트-스크립트로-랜딩-페이지-만들기) 또는 [스마트 배너](#원링크-스마트-배너로-랜딩-페이지-만들기)를 만듭니다.
   * **AF 어트리뷰션 링크:** AF 어트리뷰션 링크(원링크, 싱글 플랫폼 또는 크로스 플랫폼)를 사용하는 것은 사용자가 랜딩 페이지를 먼저 방문하지 않고 앱을 다운로드할 수 있도록 스토어로 직접 리디렉션되도록 하려는 경우에 권장됩니다.

     > 🚧 **중요!**
     >
     > 경우에 따라 AF 어트리뷰션 링크를 사용하면 오류가 발생할 수 있습니다. 이 경우 Meta 담당자에게 해결 방법을 요청하거나 웹 랜딩 페이지를 도착 URL로 사용하세요.

2. **URL 매개변수 만들기**를 클릭하여 URL(랜딩 페이지 URL 또는 AF 어트리뷰션 링크)에 URL 매개변수를 추가합니다.
3. 아래의 **사용자 지정 매개 변수**에서 **매개 변수 추가**를 클릭합니다.

   [![4.png](https://files.readme.io/bbce415e16d3442f8959bf7a0c23825035d7d4740d5bf3570306c3684c8764d4-25722672143633.png)](https://files.readme.io/bbce415e16d3442f8959bf7a0c23825035d7d4740d5bf3570306c3684c8764d4-25722672143633.png)
4. 앱스플라이어 매개변수를 Meta 값에 매핑합니다.

   * 도착 URL이 **랜딩 페이지, OneLink 어트리뷰션 링크 또는 단일 플랫폼 어트리뷰션 링크**인 경우, 다음 AF 매개변수를 Meta 매개변수에 매핑합니다.  

| AF 매개변수 | 매핑된 Meta 값 |
| --- | --- |
| <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#pid">`pid`</Anchor> | `metaweb_int` |
| <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#c">`c`</Anchor> | `{{campaign.name}}` |
| <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_siteid">`af_siteid`</Anchor> | `{{site_source_name}}` |
| <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_c_id">`af_c_id`</Anchor> | `{{campaign.id}}` |
| <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_adset">`af_adset`</Anchor> | `{{adset.name}}` |
| <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | `{{adset.id}}` |
| <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_ad">`af_ad`</Anchor> | `{{ad.name}}` |
| <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_ad_id">`af_ad_id`</Anchor> | `{{ad.id}}` |

     결과 URL의 예는 다음과 같습니다.

     ```http
     https://app.appsflyer.com/{app_id}?pid=metaweb_int&c={{campaign.name}}&af_siteid={{site_source_name}}&af_c_id={{campaign.id}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}&af_r={https://Add-your-store-url.com}
     ```

     * 앱의 APK가 Google Play 스토어에서 호스팅되지 않는 경우 <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_r">`af_r`</Anchor> 매개 변수를 추가하고 해당 스토어 URL (e.g, `https://Add-your-store-url.com`)을 매핑합니다.
   * 도착 URL이 **PC 또는 콘솔 스토어**인 경우, 아래 표의 지침에 따라 링크를 만듭니다. 자세한 내용은 다음을 참조하세요. <Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-platform-direct-attribution-links">CTV, PC 및 콘솔 플랫폼 다이렉트 어트리뷰션 링크</Anchor>

<table><thead><tr><th colspan="2">어트리뷰션 링크 구조</th></tr></thead><tbody><tr><td>기본 URL</td><td>engagement.appsflyer.com/v1.0/c2s/click/app/</td></tr><tr><td>필수 경로 파라미터</td><td><ul><li>플랫폼<br/>예: steam</li><li>app_id<br/>예: 123456</li></ul></td></tr><tr><td>필수 쿼리 파라미터</td><td><ul><li>af_media_source</li><li>af_campaign_id</li><li>af_r</li></ul></td></tr><tr><td>기타 파라미터</td><td><a href="./ctv-pc-and-console-platform-direct-attribution-links#파라미터" target="_blank">전체 보기</a></td></tr><tr><td>URL 구조</td><td><code>https://engagements.appsflyer.com/v1.0/c2s/click/app/`{platform}/{app_id}?af_media_source={media_source}&amp;af_campaign_id={campaign_id}&amp;af_r={app_store_url}`</code></td></tr></tbody></table>

     다음 앱스플라이어 매개변수를 Meta 매개변수에 매핑합니다.

| AF 매개변수 | 매핑된 Meta 값 |
| --- | --- |
| `af_media_source` | `metaweb_int` |
| `af_campaign` | `{{campaign.name}}` |
| <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_siteid">`af_siteid`</Anchor> | `{{site_source_name}}` |
| <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_c_id">`af_campaign_id`</Anchor> | `{{campaign.id}}` |
| <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_adset">`af_adset`</Anchor> | `{{adset.name}}` |
| <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | `{{adset.id}}` |
| <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_ad">`af_ad`</Anchor> | `{{ad.name}}` |
| <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_ad_id">`af_ad_id`</Anchor> | `{{ad.id}}` |

     크로스 플랫폼 URL의 예는 다음과 같습니다.

     ```http
     https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=metaweb_int&af_campaign_id={{campaign.id}}&af_campaign={{campaign.name}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello
     ```

   > 📘 **참고**
   >
   > Meta는 광고가 클릭될 때, `fbclid={{fbclid}}`을 도착 URL로 자동으로 추가합니다.


   > 👍 **팁**
   >
   > 캠페인 분석을 간소화하기 위해 캠페인 이름에는 캠페인 유형(웹 또는 모바일)을 접두사 또는 접미사로 포함합니다. (예: campaign-name\_web)


> 📘 **참고**
>
> AF 링크 매개변수에 대한 포괄적인 안내는 <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#어트리뷰션-링크-파라미터">어트리뷰션 링크 매개변수</Anchor>를 참조하십시오.

</Accordion>

<div id="c-select-tracked-events" />

<Accordion title="3. 추적된 이벤트 선택">

추적 섹션을 사용하여 광고가 유도하는 전환 이벤트를 선택합니다(이벤트 설정은 [이벤트 관리자](https://www.facebook.com/business/help/898185560232180?id=1205376682832142)를 통해 수행됩니다)

[![](https://files.readme.io/75b6136fdf3fd9790e39aeec735ccd2e1ff0b8a5f302c85f0ed3b05926fcc435-25646834958481.png)](https://files.readme.io/75b6136fdf3fd9790e39aeec735ccd2e1ff0b8a5f302c85f0ed3b05926fcc435-25646834958481.png)

> 🚧 **중요!**
>
> 를 선택하지 않도록 주의하세요. 그렇지 않으면 Meta가 SRN API를 사용하여 해당 전환을 청구하며, 이로 인해 리포팅 및 최적화가 잘못 정렬될 수 있습니다.

</Accordion>

## 원링크 스마트 스크립트로 랜딩 페이지 만들기

**유저 여정:** 사용자가 Meta 광고를 클릭하면 모바일 웹사이트로 이동합니다. 사용자는 하나 이상의 플랫폼에서 앱을 다운로드하도록 촉구하는 CTA 버튼이 있는 페이지를 방문합니다. 버튼을 클릭하면 사용자가 스토어로 리디렉션됩니다.

<div id="end-to-end-data-flow" />

<Accordion title="엔드투엔드 데이터 흐름">

[![](https://files.readme.io/95b5a593eba3bc0bafb629bb8a27d83c077d5815a79897c004f8f085fa8e953b-25646834953105.png)](https://files.readme.io/95b5a593eba3bc0bafb629bb8a27d83c077d5815a79897c004f8f085fa8e953b-25646834953105.png)

1. Meta 광고 URL에는 `pid=metaweb_int` 매개 변수가 포함됩니다. 사용자가 광고를 클릭하면 `fbclid` 매개변수는 클릭한 URL에 자동으로 추가됩니다.
2. 사용자는 스마트 스크립트가 포함된 랜딩 페이지인 URL 대상으로 리디렉션됩니다.
3. 랜딩 페이지가 로드되면 스마트 스크립트는 수신 URL 매개변수가 포함된 임프레션을 앱스플라이어에 실행합니다. 노출은 웹 랜딩 페이지에서 조회 후 기여를 허용합니다. 노출 및 조회 후 기여에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">여기</Anchor> 참조하십시오.
4. 스마트 스크립트는 `fbclid` 매개변수를 포함한 수신 URL 매개변수를 기반으로, 해당 페이지의 CTA 버튼에 대한 발신 URL을 생성합니다. 버튼은 다음과 같이 이어질 수 있습니다.
   * Google Play 및 App Store(원링크 어트리뷰션 링크 사용).
   * 여러 플랫폼 스토어(예: CTV, Epic 및 Steam). 이 사용 사례에서 스마트 스크립트트는 각 플랫폼에 대해 단일 플랫폼 어트리뷰션 링크를 생성하여 지정된 플랫폼의 스토어로 연결됩니다.
   * 사용자의 기기에 APK 파일을 다운로드합니다.
5. 사용자가 CTA 버튼을 클릭하면 클릭이 실행되고 앱스플라이어에 등록됩니다.
6. 사용자가 스토어로 리디렉션되고 앱을 다운로드합니다.
7. 사용자가 앱을 열면 인스톨 이벤트가 앱스플라이어에 등록됩니다.
8. 앱스플라이어는 [설치 참조자](https://www.appsflyer.com/glossary/install-referrer/)가 있는 경우 확률적 모델링을 기반으로 설치를 귀속시키거나 결정적으로 귀속시킵니다.
9. `fbclid` 매개변수와 기타 이벤트 매개변수를 포함하는 포스트백이 생성되어 CAPI API를 통해 Meta로 전송됩니다. Meta는 `fbclid` 매개변수를 사용하여 특정 클릭을 식별하고, 다른 매개변수는 캠페인을 최적화하는 데 도움이 됩니다.

</Accordion>

<div id="set-up-smart-script-landing-page" />

<Accordion title="스마트 스크립트 랜딩 페이지 설정">

스마트 스크립트를 설정하려면 Meta 광고 캠페인을 수행하세요.

1. 캠페인의 원링크 어트리뷰션 링크에 대한 템플릿을 설정합니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template#원링크-템플릿-만들기">원링크 템플릿을 만드는 방법</Anchor>을 참조하세요.
2. 스마트 스크립트를 만듭니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">원링크 스마트 스크립트 생성 방법</Anchor>을 참조하세요.

   > 📘 **참고**
   >
   > 아래 지침은 스마트 스크립트로 Meta 광고 캠페인을 설정하는 데 필요한 구체적인 단계를 중점적으로 설명합니다. 스마트 스크립트 캠페인을 설정하는 방법에 대한 포괄적인 가이드는 <Anchor target="_blank" href="/marketers/ko/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">OneLink Smart Script V2 설정</Anchor> 문서의 <Anchor target="_blank" href="/marketers/ko/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">OneLink Smart Script를 만드는 방법</Anchor> <Anchor target="_blank" href="/marketers/ko/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">섹션을 참조하세요.</Anchor>

3. 모든 관련 URL 매개변수가 수신 URL에 추가되었는지 확인합니다. 수신 URL에 추가된 매개변수를 검토하려면 Meta 광고 관리자를 열고 도착 URL을 만들 때 설정된 URL 매개변수를 확인하세요. 자세한 내용은 다음을 참조하세요. [도착 URL 설정](/docs/meta-ads-create-web-based-campaigns#b-set-destination-url).
4. 사용자가 CTA 버튼을 클릭할 때 앱스플라이어로 전송될 아웃바운드 URL 매개변수에 메타 광고 캠페인에 필요한 인바운드 URL 매개변수를 매핑하십시오:
   * **PID**: 스마트 스크립트가 `pid=metaweb_int` 의 파라미터 값을 수신 URL에서 가져와 발신 URL의 파라미터에 매핑하도록 합니다.
   * **FBCLID**: 이 `fbclid` 파라미터는 Meta에 인앱 이벤트 포스트백을 성공적으로 전송하는 데 필수입니다. 발신 URL FBCLID 파라미터 매핑은 스마트 스크립트 버전에 따라 달라집니다.

     * 버전 2.8.1 이상: 이 `fbclid` 매개 변수는 수신 URL에 존재할 경우, 발신 URL 매개 변수로 자동으로 전달되므로 수동 매핑이 필요하지 않습니다.
     * 버전 2.8.0 이하: `fbclid` 파라미터는 **스마트 스크립트** 페이지의 **URL 파라미터 매핑** 섹션에서 수동으로 매핑되어야 합니다.
       1. **Mapping for**에서 **사용자정의 파라미터**을 선택합니다.
       2. **발신 URL 파라미터** 와 **수신 URL 파라미터** 에 **fbclid 를** 입력합니다.

     > 📘 **참고**
     >
     > 앱스플라이어 로데이터 보고서에 표시하려면 들어오는 `fbclid`매개변수도 나가는 `fbclid`매개변수와 함께 나가는 매개변수 `af_sub[1-5]`중 하나에 매핑되어야 합니다. `fbclid`자세한 내용은 fbclid`fbclid`페이스북 FBCLIDfbclid`af_sub[1-5]`을 참고하세요.af\_sub[1-5]


</Accordion>

<div id="set-up-smart-script-crossplatform-landing-page" />

<Accordion title="스마트 스크립트 크로스 플랫폼 랜딩 페이지 설정">

스마트 스크립트를 설정하려면 크로스 플랫폼 랜딩 페이지에 대한 Meta 광고 캠페인을 수행하세요.

1. 캠페인의 원링크 어트리뷰션 링크에 대한 템플릿을 설정합니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template#원링크-템플릿-만들기">원링크 템플릿을 만드는 방법</Anchor>을 참조하세요.
   * 크로스 플랫폼 어트리뷰션을 위해 OneLink 템플릿을 활성화하려면 <Anchor target="_blank" href="/marketers/ko/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-1-create-or-edit-a%C2%A0onelink-template%C2%A0for-crossplatform-attribution">여기</Anchor>를 참조하세요.
2. 모든 관련 URL 매개변수가 수신 URL에 추가되었는지 확인합니다. 수신 URL에 추가된 매개변수를 검토하려면 Meta 광고 관리자를 열고 도착 URL을 만들 때 설정한 URL 매개변수를 검토하세요. 자세한 내용은 [도착 URL 설정](#b-set-destination-url)을 참고하세요.
3. 각 들어오는 매개 변수에 대해 매핑될 나가는 매개 변수를 결정합니다. 예를 들어, 들어오는 URL의 `af_site_id`은 나가는 URL의 `af_site_id`에 매핑됩니다.
4. 비워 둘 수 없는 필수 발신 매개변수의 기본값을 결정합니다.
5. 개발자에게 다음 정보를 보냅니다.
   * 수신-발신 매개변수 매핑입니다. 개발자는 수신-발신 매개변수 매핑을 기반으로 발신 직접 URL을 생성하는 스크립트를 만듭니다.
   * 매개 변수 기본값입니다. 스크립트는 해당하는 들어오는 URL 매개 변수 값이 없을 때마다 나가는 URL 매개 변수를 기본값으로 채웁니다.
   * 원링크 어트리뷰션 링크를 사용하는 경우, 도메인과 템플릿 ID를 개발자에게 전송하십시오. 개발자는 이를 사용하여 나가는 원링크 URL을 생성합니다. 예를 들어: `yourbrand.onelink.me/A1b2` 또는 브랜드 도메인의 예: `click.yourbrand.com/A1b2`
   * 개발자에게 다음 Dev Hub 링크를 보냅니다.
     * 모바일 플랫폼이 아닌 곳으로 직접 나가는 URL을 만드는 방법에 대한 [지침과 코드 예시](https://dev.appsflyer.com/hc/docs/create-direct-click-url)입니다.
     * 크로스 플랫폼 랜딩 페이지를 만드는 방법에 대한 [데모와 지침](https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/)입니다.
   * 개발자에게 발신 URL에 수신 `fbclid`매개변수를 포함하라고 상기시켜주세요.

     > 📘 **참고**
     >
     > 앱스플라이어 로데이터 보고서에 표시하려면 들어오는 `fbclid`매개변수도 나가는 `fbclid`매개변수와 함께 나가는 매개변수 `af_sub[1-5]`중 하나에 매핑되어야 합니다.


</Accordion>

## 원링크 스마트 배너로 랜딩 페이지 만들기

**유저 여정:** 사용자가 Meta 광고를 클릭하면 모바일 웹사이트로 이동합니다. 페이지에 도착하면 스마트 배너가 CTA와 함께 표시되어 앱 스토어에서 앱을 다운로드할 수 있습니다.

<div id="end-to-end-data-flow::4f887e1c" />

<Accordion title="엔드투엔드 데이터 흐름">

1. Meta 광고 URL에는 `pid=metaweb_int` 매개 변수가 포함됩니다. 사용자가 광고를 클릭하면 `fbclid` 매개변수는 클릭한 URL에 자동으로 추가됩니다.
2. 사용자는 스마트 배너가 포함된 랜딩 페이지인 URL 대상으로 리디렉션됩니다.
3. 랜딩 페이지가 로드되면 스마트 배너는 앱스플라이어에 <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">노출</Anchor> 이벤트를 발생시키며, 여기에는 수신 URL 매개변수가 포함됩니다. 이 노출은 랜딩 페이지에 대한 뷰-쓰루 어트리뷰션을 가능하게 합니다. 노출 및 뷰-쓰루 어트리뷰션에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">여기</Anchor>를 참조하세요.
4. 스마트 배너는 배너의 CTA 버튼에 대한 발신 URL을 생성합니다. 발신 URL은 매개변수를 포함한 수신 URL `fbclid`매개변수를 기반으로 합니다. 스마트 배너는 원링크 기반 링크만 생성할 수 있습니다.
5. 사용자가 스마트 배너 CTA 버튼을 클릭하면 클릭이 실행되고 앱스플라이어에 등록됩니다.
6. 사용자가 스토어로 리디렉션되고 앱을 다운로드합니다.
7. 사용자가 앱을 열면 인스톨 이벤트가 앱스플라이어에 등록됩니다.
8. 앱스플라이어는 설치 참조자가 사용 가능한 경우 확률적 모델링을 기반으로 설치를 귀속시키거나 결정적으로 귀속시킵니다.
9. `fbclid` 매개변수와 기타 이벤트 매개변수를 포함하는 포스트백이 생성되어 CAPI API를 통해 Meta로 전송됩니다. Meta는 `fbclid` 매개변수를 사용하여 특정 클릭을 식별하고, 다른 매개변수는 캠페인을 최적화하는 데 도움이 됩니다.

</Accordion>

<div id="set-up-smart-banners-landing-page" />

<Accordion title="스마트 배너 랜딩 페이지 설정">

스마트 배너를 설정하려면 Meta 광고 캠페인을 수행해야 합니다.

1. 캠페인의 원링크 어트리뷰션 링크에 대한 템플릿을 설정합니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template#원링크-템플릿-만들기">원링크 템플릿을 만드는 방법</Anchor>을 참조하세요.
2. 스마트 배너를 만드세요.

   > 📘 **참고**
   >
   > 아래 지침은 스마트 배너로 Meta 광고 캠페인을 설정하는 데 필요한 특정 단계를 중점적으로 설명합니다. 스마트 배너 캠페인을 설정하는 방법에 대한 포괄적인 가이드는 <Anchor target="_blank" href="/marketers/ko/docs/smart-banners-mobile-web-to-app-for-marketers">스마트 배너 - 모바일 웹-앱(마케터용)</Anchor> 문서의 <Anchor target="_blank" href="/marketers/ko/docs/smart-banners-mobile-web-to-app-for-marketers#설정">설정 섹션</Anchor>을 참조하세요.

3. Meta 광고 캠페인에 대한 스마트 배너 매개변수를 설정합니다.
   * 모든 관련 URL 파라미터가 수신 URL에 추가되었는지 확인합니다. 가장 중요한 것은 `pid=metaweb_int` 그리고 `fbclid`가 수신 URL에 포함되어 스마트 배너가 이를 수집할 수 있도록 해야 한다는 것입니다. 이 두 매개변수는 어트리뷰션과 Meta 광고에 포스트백을 전송하는 데 필요합니다. 수신 URL에 추가된 매개변수를 검토하려면 Meta 광고 관리자를 열고 도착 URL을 만들 때 설정한 URL 매개변수를 검토하세요. [도착 URL 설정](#b-set-destination-url).

</Accordion>

## 웹 투 앱 어트리뷰션 데이터 보기

웹 기반 전환 이벤트는 원래의 `metaweb_int` PID로 메타에 전송되지만, 앱스플라이어 대시보드와 로데이터 리포트에서 `Facebook Ads` PID로 보고됩니다. 이는 운영 컨버전 이벤트와 컨버전 지원 이벤트에 모두 적용됩니다.

이 통합 리포팅 뷰에서는 전체 웹 및 모바일 비용 리포팅을 포함하여 한 곳에서 웹 및 앱 캠페인 성과를 모두 분석할 수 있습니다.

### 대시보드에서 보기

모든 메타 웹투앱 어트리뷰션은 개요 및 액티비티 대시보드의 `Facebook Ads` 아래에 표시됩니다. 이를 통해 플랫폼 전반에 걸친 캠페인 성과에 대한 통합된 단일 시야를 제공합니다. 표준 필터와 분석 기준을 사용하여 Meta Ads 데이터에서 앱 및 웹 트래픽을 비교할 수 있습니다.

### 로데이터 및 API 리포트에서 보기

* **로데이터 내보내기 및 API 응답**은 구글 웹 액티비티의 `media_source` 필드에 있는 `Facebook Ads` PID를 포함합니다. 웹 캠페인 설정 세부 정보를 확인하려면 웹 캠페인을 생성할 때 사용된 PID로 `metaweb_int`을 표시하는 `original_url` 필드를 참조하십시오.
* **포스트백 리포트**는 포스트백이 전송된 원래의 미디어 소스로 `metaweb_int`를 표시합니다.

## 자주 묻는 질문

<div id="why-am-i-seeing" />

<Accordion title="Meta Web(metaweb_int) 대신 Meta Ads(facebook_int)로 어트리뷰션된 인스톨과 인앱 이벤트가 표시되는 이유는 무엇인가요?">

Meta 광고에서 [추적된 이벤트를 설정](#c-select-tracked-events)했을 때 웹 이벤트 대신 앱 이벤트로 설정했습니다. 웹 이벤트로 설정해야 합니다.

</Accordion>

## 특성과 제한 사항

| 특징 | 비고 |
| --- | --- |
| 비용, 클릭수 및 노출 데이터 | 메타 광고 웹(`metaweb_int`)의 비용, 클릭 및 노출 데이터는 메타 광고 연동(`Facebook Ads`)을 통해 지원됩니다.<ul><li>데이터를 얻으려면 광고 네트워크 계정을 메인 PID(`Facebook Ads`)에 연결해야 합니다.<ul><li>ROI360 구독자: **비용 설정** 페이지에서</li><li>ROI360 비구독자: **활성 연동** 페이지(**비용 연동** 탭)에서</li></ul></li><li>메타 광고 웹 캠페인의 비용, 클릭 및 노출 데이터를 보려면 어트리뷰션 링크에 캠페인 ID(<Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_c_id">af\_c\_id</Anchor>)가 포함되어 있는지 확인하십시오.</li><li>어트리뷰션 링크는 가장 세밀한 수준에서 어트리뷰션과 관련된 비용, 클릭 및 노출 데이터를 보려면 전체 캠페인 구조를 포함해야 합니다.</li></ul> |

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 h_01HZKNS17JYFQ3F5TKNE5Q5TJ4=%EA%B0%9C%EC%9A%94 h_01J8CYG29BETYPZ03A1X54M3ZF=%EC%B0%B8%EA%B3%A0 prerequisite=%ED%95%84%EC%88%98-%EC%A1%B0%EA%B1%B4 h_01HZKNS17JTCXE4JMZ64NEVPS6=%ED%95%84%EC%88%98-%EC%A1%B0%EA%B1%B4 how-to-create-a-meta-ads-campaign=meta-%EC%9B%B9-%EA%B4%91%EA%B3%A0-%EC%BA%A0%ED%8E%98%EC%9D%B8%EC%9D%84-%EB%A7%8C%EB%93%9C%EB%8A%94-%EB%B0%A9%EB%B2%95 h_01HZKNS17JERCAKZHK43ZQWARJ=meta-%EC%9B%B9-%EA%B4%91%EA%B3%A0-%EC%BA%A0%ED%8E%98%EC%9D%B8%EC%9D%84-%EB%A7%8C%EB%93%9C%EB%8A%94-%EB%B0%A9%EB%B2%95 set-up-meta-ads-integration-in-appsflyer=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%97%90%EC%84%9C-meta-%EC%9B%B9-%EA%B4%91%EA%B3%A0-%EC%97%B0%EB%8F%99-%EC%84%A4%EC%A0%95 h_01HZKNS17J284R2MAN42WV7F0S=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%97%90%EC%84%9C-meta-%EC%9B%B9-%EA%B4%91%EA%B3%A0-%EC%97%B0%EB%8F%99-%EC%84%A4%EC%A0%95 h_01HZKNS17JGQBENY2X8S5PHFVH=a-activate-the-meta-ads-integration h_01ZXVWB1ZYKK4DP38QY1RMEY6M=d-enable-view-through-attribution-for-meta-web h_01HZKNS17JH2ZJKATV1AP6JDWP=b-set-inapp-event-postbacks 01JJ4MGS84WXEVG4FWQ0YQ7GN6=%EC%B0%B8%EA%B3%A0-1 set-up-appsflyer-integration-in-meta-ads=meta-%EA%B4%91%EA%B3%A0%EC%97%90%EC%84%9C-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EC%97%B0%EB%8F%99-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 h_01HZKNS17JJWX7N9W6BN05B57C=meta-%EA%B4%91%EA%B3%A0%EC%97%90%EC%84%9C-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EC%97%B0%EB%8F%99-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 h_01HZKNS17JTVX8N5CKTKVGH0QB=a-set-the-campaign-type-objective-and-goals h_01HZKNS17JHHS7GYPBT441ND7A=%EC%B0%B8%EA%B3%A0-2 h_01HZKNS17KT8TRD2TGDBRGKBZ3=b-set-destination-url h_01HZKNS17KCNKS4YY4JHMQRM1Z=%EC%A4%91%EC%9A%94 h_01J2V9WF300WDY0PWV68TDR9TT=%EC%B0%B8%EA%B3%A0-3 h_01K88MSNRX9QFQ49FN2MXPMADX=%ED%8C%81 01J2V903C36X5K6VRPGQQGWFMW=%EC%B0%B8%EA%B3%A0-4 h_01HZKNS17K07CENP8GG7MQRKHK=c-select-tracked-events h_01HZKNS17KARAENYPMVJSM1ARQ=%EC%A4%91%EC%9A%94-1 create-landing-page-with-onelink-smart-script=%EC%9B%90%EB%A7%81%ED%81%AC-%EC%8A%A4%EB%A7%88%ED%8A%B8-%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8%EB%A1%9C-%EB%9E%9C%EB%94%A9-%ED%8E%98%EC%9D%B4%EC%A7%80-%EB%A7%8C%EB%93%A4%EA%B8%B0 h_01HZKNS17KPJMP74HQKWY022T2=%EC%9B%90%EB%A7%81%ED%81%AC-%EC%8A%A4%EB%A7%88%ED%8A%B8-%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8%EB%A1%9C-%EB%9E%9C%EB%94%A9-%ED%8E%98%EC%9D%B4%EC%A7%80-%EB%A7%8C%EB%93%A4%EA%B8%B0 h_01HZKNS17K5PRRXSD2JMJ54NTN=end-to-end-data-flow h_01HZKNS17KA8VAK5TDFG1NV9YN=set-up-smart-script-landing-page h_01HZKNS17K6DPA6E9CTM5F3X1A=%EC%B0%B8%EA%B3%A0-5 h_01HZKNS17K2W4XJB0BH87RZYTJ=%EC%B0%B8%EA%B3%A0-7 h_01HZKNS17K5RRAFFTNA6QT7AKJ=set-up-smart-script-crossplatform-landing-page h_01HZKNS17K03S4B3ZRQ62TRFRE=%EC%B0%B8%EA%B3%A0-7 create-landing-page-with-onelink-smart-banners=%EC%9B%90%EB%A7%81%ED%81%AC-%EC%8A%A4%EB%A7%88%ED%8A%B8-%EB%B0%B0%EB%84%88%EB%A1%9C-%EB%9E%9C%EB%94%A9-%ED%8E%98%EC%9D%B4%EC%A7%80-%EB%A7%8C%EB%93%A4%EA%B8%B0 h_01HZKNS17KH8NQ68RPZGMEAQTV=%EC%9B%90%EB%A7%81%ED%81%AC-%EC%8A%A4%EB%A7%88%ED%8A%B8-%EB%B0%B0%EB%84%88%EB%A1%9C-%EB%9E%9C%EB%94%A9-%ED%8E%98%EC%9D%B4%EC%A7%80-%EB%A7%8C%EB%93%A4%EA%B8%B0 h_01HZKNS17K4Y7WSM14EEJ2G5NC=end-to-end-data-flow::4f887e1c h_01HZKNS17KZ3YKS5R52SRKR9P2=set-up-smart-banners-landing-page h_01HZKNS17K3W3GPV6TM5RQS1WP=%EC%B0%B8%EA%B3%A0-8 meta%20view=%EC%9B%B9-%ED%88%AC-%EC%95%B1-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B8%B0 view-webtoapp-attribution-data-from-november-2-2025=%EC%9B%B9-%ED%88%AC-%EC%95%B1-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B8%B0 h_01K88J8JFNEYBZNR18133NMRP9=%EC%9B%B9-%ED%88%AC-%EC%95%B1-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B8%B0 view-in-the-dashboard=%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C%EC%97%90%EC%84%9C-%EB%B3%B4%EA%B8%B0 h_01K88J8JFNMHCVZ0C34E3D7AST=%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C%EC%97%90%EC%84%9C-%EB%B3%B4%EA%B8%B0 view-in-raw-data-and-api-reports=%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B0%8F-api-%EB%A6%AC%ED%8F%AC%ED%8A%B8%EC%97%90%EC%84%9C-%EB%B3%B4%EA%B8%B0 h_01K88J8JFN8W2572N92466YFZQ=%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B0%8F-api-%EB%A6%AC%ED%8F%AC%ED%8A%B8%EC%97%90%EC%84%9C-%EB%B3%B4%EA%B8%B0 frequently-asked-questions-faq=%EC%9E%90%EC%A3%BC-%EB%AC%BB%EB%8A%94-%EC%A7%88%EB%AC%B8 01JCJ9GGDT8GGPRF2YBNSJZ579=%EC%9E%90%EC%A3%BC-%EB%AC%BB%EB%8A%94-%EC%A7%88%EB%AC%B8 01JCJ9GGDVNFW6YBJTC0CKVKGM=why-am-i-seeing traits-and-limitations=%ED%8A%B9%EC%84%B1%EA%B3%BC-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD 01JEZXJNF1C932KGAEFS4P5D51=%ED%8A%B9%EC%84%B1%EA%B3%BC-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD" />
