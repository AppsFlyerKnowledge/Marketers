---
title: Snapchat용 웹 기반 캠페인 생성
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
  created_at: '2025-11-27T14:39:44Z'
  edited_at: '2026-10-14T10:28:02Z'
  id: 41365000854161
  locale: ko
  section: Snap (Snapchat)
  section_id: 6551316540945
  url: https://support.appsflyer.com/hc/ko/articles/41365000854161
---
> **한눈에 보기:** Snapchat 광고의 웹 캠페인을 사용하여 Snapchat 광고의 웹-앱 전환을 기여합니다.

## 개요

앱스플라이어는 사용자 유입 웹 기반 캠페인을 위해 Meta 광고 (`snapweb_int`)와의 연동을 지원하며, 이로써 Meta의 Conversion API(CAPI)를 통해 직접 어트리뷰션 및 전환 데이터를 보고할 수 있습니다. 그런 다음 Meta는 해당 데이터를 활용하여 광고 타겟팅을 최적화하고, 성과를 측정하며, 오디언스를 커스텀하여 구축할 수 있습니다.

> 🚧 **중요!**
>
> 현재 Meta 웹과의 연동은 CAPI로의 리인게이지먼트 포스트백 전송을 지원하지 않습니다.

### 필수 조건

Snapchat 웹 통합을 활성화하기 전에 에 비즈니스 계정이 있는지 확인하십시오.

### Snapchat 광고 웹 캠페인을 만드는 방법

이 문서에는 앱스플라이어를 사용하여 모바일, PC 및 콘솔 앱용 Meta 광고에서 웹 캠페인을 설정하는 방법에 대한 정보와 단계가 포함되어 있습니다. 설정에는 Meta 광고와 앱스플라이어의 연동 정의, 두 플랫폼 모두에서 캠페인 설정, 원링크 스마트 스크립트 또는 원링크 스마트 배너를 사용하는 랜딩 페이지 생성 등이 포함됩니다.

설정 프로세스에는 다음과 같은 필수 단계가 포함됩니다.

* [AppsFlyer에서 Snapchat Ads 웹 통합 설정](#appsflyer에서-snapchat-광고-웹-통합-설정) (필수)
* [Snapchat 광고에서 AppsFlyer 통합 설정](#snapchat-광고에서-appsflyer-통합-설정) (필수)

그리고 선택적 단계는 다음과 같습니다.

* [원링크 스마트 스크립트로 랜딩 페이지 만들기](#원링크-스마트-스크립트로-랜딩-페이지-만들기) (선택 사항)
* [원링크 스마트 배너로 랜딩 페이지 만들기](#원링크-스마트-배너로-랜딩-페이지-만들기) (선택 사항)

## AppsFlyer에서 Snapchat 광고 웹 통합 설정

Snapchat 광고 웹 통합을 활성화하는 것부터 시작합니다. 그런 다음 AppsFlyer가 이벤트 API로 보내는 포스트백을 구성합니다.

<div id="1-activate-the-snapchat-ads-web-integration" />

<Accordion title="1. Snapchat 광고 웹 통합 활성화">

Snapchat 광고 웹 통합을 활성화하려면:

1. 앱스플라이어에서의 사이드 메뉴에서 **협업** > **파트너 마켓플레이스**를 선택하세요.
2. 검색: **Snapchat 웹** 그리고 선택하십시오.
3. **연동 설정**을 클릭합니다. 활성 연동 설정 페이지로 이동합니다.
4. **연동** 탭에서 **파트너 활성화**를 선택합니다. 파트너와 작업하는 동안에는 토글이 켜져 있어야 합니다(활성화됨).
5. **고급 개인 정보 보호**(iOS 앱 연동을 설정하는 경우)를 끕니다.
6. **픽셀 ID:** 픽셀 ID를 입력합니다. Snapchat 광고 관리자에서 자세한 지침에 따라 생성하거나 검색할 수 있습니다. [Snapchat 광고 공식 문서](https://businesshelp.snapchat.com/s/article/pixel-website-install?language=en_US)
7. **액세스 토큰:** 액세스 토큰을 입력합니다. 이를 생성하거나 검색하려면 다음을 따르십시오. [Snapchat 광고 공식 문서의 지침](https://developers.snap.com/api/marketing-api/Conversions-API/GetStarted)

</Accordion>

<div id="2-enable-viewthrough-attribution" />

<Accordion title="2. 뷰-쓰루 어트리뷰션 활성화">

AppsFlyer는 Snapchat 웹 캠페인에 대해 뷰-스루 어트리뷰션을 지원합니다( [스마트 스크립트](#원링크-스마트-스크립트로-랜딩-페이지-만들기) 또는 [스마트 배너](#set-up-smart-banners-landing-page)-enabled 방문 페이지. 이를 통해 사용자가 광고를 클릭하지 않더라도 광고 노출로 인해 발생한 앱 설치에 대한 확률적 모델링(PMOD) 분석이 가능합니다.

사용 가능한 경우, `ScCid`는 귀속 정확성을 높이기 위해 메타에 대한 포스트백에 포함됩니다.

**Snapchat 웹 보기 기반 분석을 활성화하려면:**

1. 앱스플라이어에서 사이드바에서 **활성 연동** > **Google Ads Web**을 엽니다.
2. **연동** 탭에서 **인스톨 어트리뷰션** 섹션으로 스크롤합니다.
3. **뷰-쓰루 어트리뷰션 설치**를 켭니다.
4. **[선택 사항]** **크로스 플랫폼 어트리뷰션 우선순위 동등하게 설정**을 켜고 룩백 윈도우를 설정합니다. 자세한 내용은 크로스 플랫폼 노출에 대한 동등 우선 순위 활성화.를 참조하세요.
5. **어트리뷰션 링크** 탭을 클릭합니다.
6. **뷰-쓰루 어트리뷰션** 섹션으로 스크롤하여 **뷰-쓰루 룩백 윈도우**를 설정합니다(최대 24시간).
7. 설정을 적용하려면 **연동 저장**을 클릭하세요.

</Accordion>

<div id="3-set-inapp-event-postbacks" />

<Accordion title="3. 인앱 이벤트 포스트백 설정">

설치는 현재 Meta 광고에 대한 자동 기본 포스트백을 트리거하는 유일한 이벤트입니다. 기타 모든 이벤트 유형의 경우 AppsFlyer 이벤트를 Snapchat 광고 이벤트에 매핑하여 사용자 지정 포스트백을 만들 수 있습니다. 이러한 포스트백은 Snapchat 광고 관리자에서 확인할 수 있습니다.

인앱 이벤트 포스트백을 설정하려면 다음을 수행합니다.

1. **인앱 이벤트 포스트백**을 켭니다.
2. 필요한 경우 앱 내 이벤트 포스트백 창을 설정합니다(앱 내 이벤트 포스트백 창 구성에 대한 자세한 내용은 다음을 참조하십시오. <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#인앱-이벤트-포스트백-기간">앱 내 이벤트 포스트백 구성</Anchor>).
3. **이벤트 추가**을 클릭하여 목록에 이벤트를 추가합니다.
4. **앱스플라이어 이벤트** 열의 드롭다운 상자에서 이벤트 이름을 선택합니다. 앱에 통합된 SDK 또는 서버 간 이벤트에서 앱스플라이어가 수신한 이벤트의 이름입니다.
5. In the **파트너 이벤트에 매핑됨** 열, 목록에서 가장 적합한 사전 정의된 파트너 이벤트를 선택합니다.
6. **사용자 출처** 열에서 **‘이 파트너만’** 을 선택하면, 해당 파트너로부터 유입된 사용자가 수행한 이벤트에 대해서만 인앱 이벤트 포스트백이 전송되도록 보장됩니다.
7. In the **포함하여** 열에서 수익 값이 포함된 이벤트를 보낼지 여부를 선택합니다. 포스트백에 포함할 데이터 참조

   > 📘 **참고**
   >
   > * 구매 이벤트를 설정하는 경우, **포함** 열을 **값 및 수익**으로 설정합니다. 다른 옵션을 선택하면 포스트백이 실패합니다.
   > * 현재 구매 이벤트만 수익을 포함하도록 설정할 수 있습니다.

8. [선택 사항] **조건 추가** 아이콘을 클릭하여 이벤트에 대한 <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#조건부-인앱-이벤트-포스트백">조건을 설정</Anchor>합니다.
9. **연동 저장**을 클릭합니다.
10. [선택 사항] 통합을 저장하고 구성 페이지에 남아 있는 동안 파트너와 함께 추가 앱을 통합할 수 있습니다:
    1. 왼쪽 상단에서 파트너 이름 아래의 앱 이름을 클릭하여 앱 목록을 엽니다.
    2. 목록에서 다른 앱을 선택합니다.
    3. 선택한 앱에 대해 위의 단계를 반복합니다.

</Accordion>

## Snapchat 광고에서 AppsFlyer 통합 설정

Snapchat 광고 관리자에서 다음 단계를 수행합니다.

<div id="1-set-the-campaign-type-objective-and-goals" />

<Accordion title="1. 캠페인 유형, 목적, 목표 설정">

AppsFlyer에서 보낸 사전 정의된 INAPP 이벤트 중 캠페인 목표로 사용할 이벤트를 선택하거나 모바일 앱 설치를 최적화하려면 "PAGE\_VIEW"를 선택할 수 있습니다.

> ❗️ **경고**
>
> `{u}다음을 선택하지 않도록 주의하십시오{u}` **앱 이벤트;** 그렇지 않으면 Snapchat이 SRN API를 사용하여 해당 전환을 청구하게 되며, 이는 보고 및 최적화에서 불일치를 초래할 수 있습니다.

</Accordion>

<div id="2-set-destination-url" />

<Accordion title="2. 도착 URL 설정">

1. **목적지 아래의 웹사이트 URL필드에서, 광고의 목적지 역할을 하는 URL을 입력하세요. URL은 다음 중 하나여야 합니다.
   * **웹 랜딩 페이지:** 다음과 같은 경우 랜딩 페이지를 사용하는 것이 좋습니다.

     * 앱이 여러 플랫폼에 존재합니다.
     * 랜딩 페이지를 사용하여 광고된 제품에 대한 자세한 정보를 제공하려고 합니다.
     * 랜딩 페이지를 사용하여 더 많은 데이터를 수집하려고 합니다.

     이러한 모든 사용 사례에 대해 [스마트 스크립트가 있는 랜딩 페이지](#원링크-스마트-스크립트로-랜딩-페이지-만들기) 또는 [스마트 배너](#원링크-스마트-배너로-랜딩-페이지-만들기)를 만듭니다.
   * **AF 어트리뷰션 링크:** AF 어트리뷰션 링크(원링크, 싱글 플랫폼 또는 크로스 플랫폼)를 사용하는 것은 사용자가 랜딩 페이지를 먼저 방문하지 않고 앱을 다운로드할 수 있도록 스토어로 직접 리디렉션되도록 하려는 경우에 권장됩니다.**
2. **URL 매개변수 만들기**를 클릭하여 URL(랜딩 페이지 URL 또는 AF 어트리뷰션 링크)에 URL 매개변수를 추가합니다.
3. 아래의 **사용자 지정 매개 변수**에서 **매개 변수 추가**를 클릭합니다.

   Screenshot 2023-10-23 at 9.59.01.png
4. AppsFlyer 매개 변수를 Snapchat 값에 매핑합니다.
   * 도착 URL이 **랜딩 페이지, OneLink 어트리뷰션 링크 또는 단일 플랫폼 어트리뷰션 링크**인 경우, 다음 AF 매개변수를 Meta 매개변수에 매핑합니다.

| AF 매개변수 | 매핑된 Snapchat 값 |
| --- | --- |
| <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#pid">`pid`</Anchor> | `snapweb_int` |
| <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#c">`c`</Anchor> | `{{campaign.name}}`* |
| <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_c_id">`af_c_id`</Anchor> | `{{campaign.id}}`* |
| <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_adset">`af_adset`</Anchor> | `{{adSet.name }}`* |
| <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | `{{adSet.id}}`* |
| <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_ad">`af_ad`</Anchor> | `{{creative.name }}` |
| <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_ad_id">`af_ad_id`</Anchor> | `{{ad.id}}`* |
| <Anchor target="_blank" href="/marketers/ko/docs/raw-data-field-dictionary#attribution::1d1e08b5">`af_channel`</Anchor> | `{{site_source_name}}` |

     결과 URL의 예는 다음과 같습니다.

     ```
     https://app.appsflyer.com/{app_id}?pid=snapweb_int&c=__campaign_name__&af_c_id=__campaign_id__&af_adset=__aid_name__&af_adset_id=__aid__&af_ad=__cid_name__&af_ad_id=__cid__&af_r={https://Add-your-store-url.com}
     ```

     * 앱의 APK가 Google Play 스토어에서 호스팅되지 않는 경우 <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_r">`af_r`</Anchor> 매개 변수를 추가하고 해당 스토어 URL (e.g, `https://Add-your-store-url.com`)을 매핑합니다.

* 도착 URL이 **PC 또는 콘솔 스토어**인 경우, 아래 표의 지침에 따라 링크를 만듭니다. 자세한 내용은 다음을 참조하세요. <Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-platform-direct-attribution-links">CTV, PC 및 콘솔 플랫폼 다이렉트 어트리뷰션 링크</Anchor>

| 어트리뷰션 링크 구조 |  |
| --- | --- |
| 기본 URL | engagement.appsflyer.com/v1.0/c2s/click/app/ |
| 필수 경로 파라미터 | ▪ platformExample: steam  <br />▪ app\_idExample: 123456 |
| 필수 쿼리 파라미터 | ▪ af\_media\_source  <br />▪ af\_campaign\_id  <br />▪ af\_r |
| 기타 파라미터 | <Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-platform-direct-attribution-links#파라미터">전체 보기</Anchor> |
| URL 구조 | `https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}?af_media_source={media_source}&af_campaign_id={campaign_id}&af_r={app_store_url}` |

  다음 앱스플라이어 매개변수를 Meta 매개변수에 매핑합니다.

| AF 매개변수 | 매핑된 Snapchat 값 |
| --- | --- |
| `af_media_source` | `snapweb_int` |
| `af_campaign` * | `{{campaign.name}}`* |
| <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_c_id">`af_campaign_id`</Anchor> | `{{campaign.id}}`* |
| <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_adset">`af_adset`</Anchor> | `{{adSet.name }}`* |
| <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | `{{adSet.id}}`* |
| <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_ad">`af_ad`</Anchor> | `{{creative.name }}` |
| <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_ad_id">`af_ad_id`</Anchor> | `{{ad.id}}`* |
| <Anchor target="_blank" href="/marketers/ko/docs/raw-data-field-dictionary#attribution::1d1e08b5">`af_channel`</Anchor> | `{{site_source_name}}` |

  * 캠페인 분석을 단순화하려면 캠페인 이름에 접두사 또는 접미사로 캠페인 유형(웹 또는 모바일)을 포함하세요(예: 캠페인 이름\_웹).

  크로스 플랫폼 URL의 예는 다음과 같습니다.

  ```
  https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=snapweb_int&af_campaign_id={{campaign.id}}&af_campaign={{campaign.name}}&af_adset={{adSet.name}}&af_adset_id={{adSet.id}}&af_ad={{creative.name}}&af_ad_id={{ad.id}}&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello
  ```

  > 📘 **참고**
  >
  > Meta는 광고가 클릭될 때, `ScCid={{ScCid}}`을 도착 URL로 자동으로 추가합니다.


  > 📄
  >
  > AF 링크 매개변수에 대한 포괄적인 안내는 <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#어트리뷰션-링크-파라미터">어트리뷰션 링크 매개변수</Anchor>를 참조하십시오.


</Accordion>

## 원링크 스마트 스크립트로 랜딩 페이지 만들기

**유저 여정:** 사용자가 Meta 광고를 클릭하면 모바일 웹사이트로 이동합니다. 사용자는 하나 이상의 플랫폼에서 앱을 다운로드하도록 촉구하는 CTA 버튼이 있는 페이지를 방문합니다. 버튼을 클릭하면 사용자가 스토어로 리디렉션됩니다.

<div id="endtoend-data-flow" />

<Accordion title="엔드투엔드 데이터 흐름">

[![](https://files.readme.io/95b5a593eba3bc0bafb629bb8a27d83c077d5815a79897c004f8f085fa8e953b-25646834953105.png)](https://files.readme.io/95b5a593eba3bc0bafb629bb8a27d83c077d5815a79897c004f8f085fa8e953b-25646834953105.png)

1. Snapchat 광고 URL은 다음을 포함합니다: `pid=snapweb_int` 매개 변수. 사용자가 광고를 클릭하면 매개변수는 클릭한 URL에 자동으로 추가됩니다.
2. 사용자는 스마트 스크립트가 포함된 랜딩 페이지인 URL 대상으로 리디렉션됩니다.
3. 랜딩 페이지가 로드되면 스마트 스크립트는 수신 URL 매개변수가 포함된 임프레션을 앱스플라이어에 실행합니다. 노출은 웹 랜딩 페이지에서 조회 후 기여를 허용합니다. 노출 및 뷰-쓰루 어트리뷰션에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">여기</Anchor>를 참조하세요.
4. 스마트 스크립트는 `ScCid` 매개변수를 포함한 수신 URL 매개변수를 기반으로, 해당 페이지의 CTA 버튼에 대한 발신 URL을 생성합니다. 버튼은 다음으로 이어질 수 있습니다.
   * Google Play 및 App Store(원링크 어트리뷰션 링크 사용).
   * 여러 플랫폼 스토어(예: CTV, Epic 및 Steam). 이 사용 사례에서 스마트 스크립트트는 각 플랫폼에 대해 단일 플랫폼 어트리뷰션 링크를 생성하여 지정된 플랫폼의 스토어로 연결됩니다.
   * 사용자의 기기에 APK 파일을 다운로드합니다.
5. 사용자가 CTA 버튼을 클릭하면 클릭이 실행되고 앱스플라이어에 등록됩니다.
6. 사용자가 스토어로 리디렉션되고 앱을 다운로드합니다.
7. 사용자가 앱을 열면 인스톨 이벤트가 앱스플라이어에 등록됩니다.
8. 앱스플라이어는 확률적 모델링을 기반으로 설치를 귀속하거나, [설치 리퍼러](https://www.appsflyer.com/glossary/install-referrer/)가 존재할 경우 결정론적으로 귀속합니다.
9. 포스트백을 포함하는 내용 `ScCid` 매개 변수 및 기타 이벤트 매개 변수는 생성되어 이벤트 API를 통해 Snapchat으로 전송됩니다. Meta는 매개변수를 사용하여 특정 클릭을 식별하고, 다른 매개변수는 캠페인을 최적화하는 데 도움이 됩니다.

</Accordion>

<div id="set-up-a-smart-script-landing-page" />

<Accordion title="스마트 스크립트 랜딩 페이지 설정">

스마트 스크립트를 설정하려면 Meta 광고 캠페인을 수행하세요.

1. 캠페인의 원링크 어트리뷰션 링크에 대한 템플릿을 설정합니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template#원링크-템플릿-만들기">원링크 템플릿을 만드는 방법</Anchor>을 참조하세요.
2. 스마트 스크립트를 만듭니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">원링크 스마트 스크립트 생성 방법</Anchor>을 참조하세요.

   > 📘 **참고**
   >
   > 아래 지침은 Smart Script을 사용하여 Snapchat 광고 캠페인을 설정하는 데 필요한 구체적인 단계를 설명합니다. 스마트 스크립트 캠페인을 설정하는 방법에 대한 포괄적인 가이드는 <Anchor target="_blank" href="/marketers/ko/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">OneLink Smart Script V2 설정</Anchor> 문서의 <Anchor target="_blank" href="/marketers/ko/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">OneLink Smart Script를 만드는 방법</Anchor> <Anchor target="_blank" href="/marketers/ko/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">섹션을 참조하세요.</Anchor>

3. 모든 관련 URL 파라미터가 수신 URL에 추가되었는지 확인합니다. 들어오는 URL에 추가된 매개 변수를 검토하려면 Snapchat 광고 관리자를 열고 대상 URL을 만들 때 설정한 URL 매개 변수를 확인하세요. 자세한 내용은 [도착 URL 설정](#2-set-destination-url)을 참고하세요.
4. Snapchat 광고 캠페인에 필요한 들어오는 URL 매개 변수를 나가는 URL 매개 변수에 매핑합니다. 사용자가 CTA 버튼을 클릭할 때 다음 매개 변수가 AppsFlyer로 전송됩니다.
   * **PID**: 스마트 스크립트가 수신 URL에서 `pid=snapweb_int`parameter 값을 가져와 발신 URL의 해당 매개변수에 매핑하는지 확인하세요.
   * **ScCid**: The `ScCid` 매개 변수는 Snapchat으로 인앱 이벤트 피드백을 성공적으로 전송하는 데 필요합니다. 매개변수는 `ScCid`스마트 스크립트ScCid 페이지의 URL 매개변수 매핑 섹션에서 수동으로 매핑해야 합니다:

     1. **Mapping for**에서 **커스텀 파라미터**를 선택하세요.
     2. `{i:In {b:the} {u:Korean}:} **{b}발신 URL 매개변수{/b}`** 그리고 the **들어오는 URL 매개 변수,** 입력하십시오 **ScCid**.

     > 📘 **참고**
     >
     > AppsFlyer 원시 데이터 보고서에 표시하려면 들어오는 데이터도 매핑해야 합니다. `ScCid` 매개 변수, 발신과 별도로 `ScCid` 매개 변수, 발신 중 하나로 `af_sub[1–5]` 매개 변수.


</Accordion>

<div id="set-up-a-smart-script-crossplatform-landing-page" />

<Accordion title="스마트 스크립트 크로스 플랫폼 랜딩 페이지 설정">

스마트 스크립트를 설정하려면 크로스 플랫폼 랜딩 페이지에 대한 Meta 광고 캠페인을 수행하세요.

1. 캠페인의 원링크 어트리뷰션 링크에 대한 템플릿을 설정합니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template#원링크-템플릿-만들기">원링크 템플릿을 만드는 방법</Anchor>을 참조하세요.
   * 크로스 플랫폼 어트리뷰션을 위해 OneLink 템플릿을 활성화하려면 여기를 참조하세요. 자세한 내용은 다음을 참조하십시오. <Anchor target="_blank" href="/marketers/ko/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-1-create-or-edit-a%C2%A0onelink-template%C2%A0for-crossplatform-attribution">크로스 플랫폼 어트리뷰션용 OneLink 템플릿 만들기</Anchor>.
2. 모든 관련 URL 파라미터가 수신 URL에 추가되었는지 확인합니다. 수신 URL에 추가된 매개변수를 검토하려면 Meta 광고 관리자를 열고 도착 URL을 만들 때 설정한 URL 매개변수를 검토하세요. 자세한 내용은 [도착 URL 설정](#2-set-destination-url)을 참고하세요.
3. 각 입력 매개 변수에 대해 매핑될 출력 매개 변수를 결정합니다. 예를 들어, 입력 매개 변수 `af_site_id``af_site_id` 들어오는 URL의 매개 변수는 다음과 매핑됩니다.  `af_site_id``af_site_id`이(가) 포함된 URL이 전송됩니다.
4. 비워 둘 수 없는 필수 발신 파라미터의 기본값을 결정합니다.
5. 개발자에게 다음 정보를 보냅니다.
   * 수신-발신 파라미터 매핑입니다. 개발자는 수신-발신 파라미터 매핑을 기반으로 발신 직접 URL을 생성하는 스크립트를 만듭니다.
   * 파라미터의 기본값입니다. 스크립트는 해당하는 들어오는 URL 매개 변수 값이 없을 때마다 나가는 URL 매개 변수를 기본값으로 채웁니다.
   * 원링크 어트리뷰션 링크를 사용하는 경우, 도메인과 템플릿 ID를 개발자에게 전송하십시오. 개발자는 이를 사용하여 나가는 원링크 URL을 생성합니다. 예를 들어: `yourbrand.onelink.me/A1b2` 또는 브랜드 도메인의 예: `click.yourbrand.com/A1b2`
   * 개발자에게 다음 Dev Hub 링크를 보냅니다.
     * 모바일 플랫폼이 아닌 곳으로 직접 나가는 URL을 만드는 방법에 대한 [지침과 코드 예시](https://dev.appsflyer.com/hc/docs/create-direct-click-url)입니다.
     * 크로스 플랫폼 랜딩 페이지를 만드는 방법에 대한 [데모와 지침](https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/)입니다.

* 개발자에게 발신 URL에 수신 `ScCid`매개변수를 포함하라고 상기시켜주세요.

  > 📘 **참고**
  >
  > 앱스플라이어 로데이터 보고서에 표시하려면 들어오는 `ScCid`매개변수도 나가는 `ScCid`매개변수와 함께 나가는 매개변수 `af_sub[1-5]`중 하나에 매핑되어야 합니다.


</Accordion>

## 원링크 스마트 배너로 랜딩 페이지 만들기

**유저 여정:** 사용자가 Meta 광고를 클릭하면 모바일 웹사이트로 이동합니다. 페이지에 도착하면 스마트 배너가 CTA와 함께 표시되어 앱 스토어에서 앱을 다운로드할 수 있습니다.

<div id="endtoend-data-flow::b905b9a5" />

<Accordion title="엔드투엔드 데이터 흐름">

1. Snapchat 광고 URL은 다음을 포함합니다: `pid=snapweb_int` 매개 변수. 사용자가 광고를 클릭하면 매개변수는 클릭한 URL에 자동으로 추가됩니다.
2. 사용자는 스마트 배너가 포함된 랜딩 페이지인 URL 대상으로 리디렉션됩니다.
3. 랜딩 페이지가 로드되면 스마트 배너는 앱스플라이어에 <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">노출</Anchor> 이벤트를 발생시키며, 여기에는 수신 URL 매개변수가 포함됩니다. 이 노출은 랜딩 페이지에 대한 뷰-쓰루 어트리뷰션을 가능하게 합니다. 인상 및 조회 전송 속성에 대해 자세히 알아보려면 다음을 참조하십시오. <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">맞춤형 인상 URL 만들기</Anchor>.
4. 스마트 배너는 배너의 CTA 버튼에 대한 발신 URL을 생성합니다. 발신 URL은 매개변수를 포함한 수신 URL `ScCid`매개변수를 기반으로 합니다. 스마트 배너는 원링크 기반 링크만 생성할 수 있습니다.
5. 사용자가 스마트 배너 CTA 버튼을 클릭하면 클릭이 실행되고 앱스플라이어에 등록됩니다.
6. 사용자가 스토어로 리디렉션되고 앱을 다운로드합니다.
7. 사용자가 앱을 열면 인스톨 이벤트가 앱스플라이어에 등록됩니다.
8. 앱스플라이어는 설치 참조자가 사용 가능한 경우 확률적 모델링을 기반으로 설치를 귀속시키거나 결정적으로 귀속시킵니다.
9. 포스트백을 포함하는 내용 `ScCid` 매개 변수 및 기타 이벤트 매개 변수는 생성되어 이벤트 API를 통해 Snapchat으로 전송됩니다. Meta는 매개변수를 사용하여 특정 클릭을 식별하고, 다른 매개변수는 캠페인을 최적화하는 데 도움이 됩니다.

</Accordion>

<div id="set-up-a-smart-banners-landing-page" />

<Accordion title="스마트 배너 랜딩 페이지 설정">

스마트 배너를 설정하려면 Meta 광고 캠페인을 수행해야 합니다.

1. 캠페인의 원링크 어트리뷰션 링크에 대한 템플릿을 설정합니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template#원링크-템플릿-만들기">원링크 템플릿을 만드는 방법</Anchor>을 참조하세요.
2. 스마트 배너를 만드세요.

   > 📘 **참고**
   >
   > 아래 지침은 스마트 배너를 사용하여 Snapchat 광고 캠페인을 설정하는 데 필요한 구체적인 단계를 설명합니다. 스마트 배너 캠페인을 설정하는 방법에 대한 포괄적인 가이드는 <Anchor target="_blank" href="/marketers/ko/docs/smart-banners-mobile-web-to-app-for-marketers">스마트 배너 - 모바일 웹-앱(마케터용)</Anchor> 문서의 <Anchor target="_blank" href="/marketers/ko/docs/smart-banners-mobile-web-to-app-for-marketers#설정">설정 섹션</Anchor>을 참조하세요.

3. Snapchat 광고 캠페인에 대한 스마트 배너 매개 변수 설정:

   * 모든 관련 URL 파라미터가 수신 URL에 추가되었는지 확인합니다.
   * 들어오는 URL에 추가된 매개 변수를 검토하려면 Snapchat 광고 관리자를 열고 URL 매개 변수를 검토하십시오. [대상 URL 생성](#2-set-destination-url).

   > 📘 **참고**
   >
   > 가장 중요한 것은 `pid=snapweb_int` 그리고 `ScCid`가 수신 URL에 포함되어 스마트 배너가 이를 수집할 수 있도록 해야 한다는 것입니다. 이 두 매개변수는 어트리뷰션과 Meta 광고에 포스트백을 전송하는 데 필요합니다.


</Accordion>

## **웹 대 애플리케이션 어트리뷰션 데이터 보기**

웹 기반 전환 이벤트는 원래대로 Snapchat으로 전송되지만 `snapweb_int` PID는 AppsFlyer 대시보드 및 원시 데이터 보고서에서 보고됩니다. `snapchat_int` PID. 이는 기본 전환 이벤트와 전환 지원 이벤트 모두에 적용됩니다.

이 통합 보고서 보기를 통해 모바일 및 웹 비용 보고를 포함하여 웹 및 앱 캠페인 성과를 한 곳에서 분석할 수 있습니다.

### **대시보드에서 보기**

모든 Snapchat 웹앱 출처는 아래에 표시됩니다. `snapchat_int` 개요 및 활동 대시보드에서. 이는 플랫폼 전반에 걸친 캠페인 결과를 단일 통합된 보기로 제공합니다. Snapchat 데이터 내에서 앱 및 웹 트래픽을 비교하려면 표준 필터와 구분을 사용합니다.

### **원시 데이터 및 API 보고서에서 보기**

* **원시 데이터 내보내기 및 API 응답** 포함하십시오. `snapchat_int` PID in the `media_source` Google 웹 활동 필드. 웹 캠페인 설정 세부 정보를 확인하려면 다음을 참조하십시오. `original_url` 표시되는 필드 `snapchat_int` 웹 캠페인 생성 시 사용된 PID처럼.
* **포스트백 보고서**  **`snapweb_int` 포스트백이 전송된 원본 미디어 소스로 표시됩니다.**

## 특성과 제한 사항

| 특징 | 비고 |
| --- | --- |
| 비용 데이터 | Meta 광고(`snapweb_int`) 웹 기반 캠페인의 비용 데이터는 자동으로 가져와지지 않습니다. 대신, 두 가지 지원되는 방법 중 하나: 이메일 기반 파일 업로드 또는 앱스플라이어 UI를 통한 수동 업로드를 사용하여 수동으로 가져와야 합니다. 이것은 ROI360 구독자를 포함한 모든 사용자에게 적용됩니다. |
| 클릭 및 노출(임시 제한) | 웹 캠페인의 클릭수 및 노출수는 Snapchat SRN에서 일시적으로 사용할 수 없습니다.`snapchat_int`). |

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 h_01KB2W28THC55F0AJ0KZJPQ6S5=%EA%B0%9C%EC%9A%94 h_01KB2W28THSST3148Y5Y07PJ7S=%EC%A4%91%EC%9A%94 prerequisites=%ED%95%84%EC%88%98-%EC%A1%B0%EA%B1%B4 h_01KB2W28THW7E6TRVTTHJZ9BP4=%ED%95%84%EC%88%98-%EC%A1%B0%EA%B1%B4 how-to-create-a-snapchat-ads-web-campaign=snapchat-%EA%B4%91%EA%B3%A0-%EC%9B%B9-%EC%BA%A0%ED%8E%98%EC%9D%B8%EC%9D%84-%EB%A7%8C%EB%93%9C%EB%8A%94-%EB%B0%A9%EB%B2%95 h_01KB2W28THTST7HWTJA9TTGPGG=snapchat-%EA%B4%91%EA%B3%A0-%EC%9B%B9-%EC%BA%A0%ED%8E%98%EC%9D%B8%EC%9D%84-%EB%A7%8C%EB%93%9C%EB%8A%94-%EB%B0%A9%EB%B2%95 set-up-snapchat-ads-web-integration-in-appsflyer=appsflyer%EC%97%90%EC%84%9C-snapchat-%EA%B4%91%EA%B3%A0-%EC%9B%B9-%ED%86%B5%ED%95%A9-%EC%84%A4%EC%A0%95 h_01KB2W28THQJF8K4AWTRXNA3RX=appsflyer%EC%97%90%EC%84%9C-snapchat-%EA%B4%91%EA%B3%A0-%EC%9B%B9-%ED%86%B5%ED%95%A9-%EC%84%A4%EC%A0%95 h_01KB2W28TH6NZCGCJAN8K3WFGA=1-activate-the-snapchat-ads-web-integration h_01KB2W28TJ6XY7WKR4VC5XS7DS=2-enable-viewthrough-attribution h_01KB2W28TJGRKP3C50ZPQAWAS9=3-set-inapp-event-postbacks h_01KB2W28TJ14KC606KE82Q7BB7=%EC%B0%B8%EA%B3%A0 set-up-appsflyer-integration-in-snapchat-ads=snapchat-%EA%B4%91%EA%B3%A0%EC%97%90%EC%84%9C-appsflyer-%ED%86%B5%ED%95%A9-%EC%84%A4%EC%A0%95 h_01KB2W28TJVZ1BX94SZYH1K5EM=snapchat-%EA%B4%91%EA%B3%A0%EC%97%90%EC%84%9C-appsflyer-%ED%86%B5%ED%95%A9-%EC%84%A4%EC%A0%95 h_01KB2W28TJ2R95JK7C1PQE644C=1-set-the-campaign-type-objective-and-goals h_01KB2W28TJ4BK88DVYJG4XYE0S=%EA%B2%BD%EA%B3%A0 h_01KB2W28TJB1V382HD09M9Y0C3=2-set-destination-url h_01KB2W28TJT7QZ2P7AZ5X61ZXV=%EC%B0%B8%EA%B3%A0-1 create-a-landing-page-with-onelink-smart-script=%EC%9B%90%EB%A7%81%ED%81%AC-%EC%8A%A4%EB%A7%88%ED%8A%B8-%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8%EB%A1%9C-%EB%9E%9C%EB%94%A9-%ED%8E%98%EC%9D%B4%EC%A7%80-%EB%A7%8C%EB%93%A4%EA%B8%B0 h_01KB2W28TJQA1TBXXQ7MA1F0CB=%EC%9B%90%EB%A7%81%ED%81%AC-%EC%8A%A4%EB%A7%88%ED%8A%B8-%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8%EB%A1%9C-%EB%9E%9C%EB%94%A9-%ED%8E%98%EC%9D%B4%EC%A7%80-%EB%A7%8C%EB%93%A4%EA%B8%B0 h_01KB2W28TJ4J426HD3ZFHXAV4J=endtoend-data-flow h_01KB2W28TJR8S029FJ3Y81MG8Y=set-up-a-smart-script-landing-page h_01KB2W28TJBYHKYNQRMJ4ZGWYD=%EC%B0%B8%EA%B3%A0-2 h_01KB2W28TJZMQEDSNVWRZCNXYD=%EC%B0%B8%EA%B3%A0-3 h_01KB2W28TJT0TEFB97RXEGDVRM=set-up-a-smart-script-crossplatform-landing-page h_01KB2W28TJ6XWR7GW4SQQAKZH9=%EC%B0%B8%EA%B3%A0-4 create-a-landing-page-with-onelink-smart-banners=%EC%9B%90%EB%A7%81%ED%81%AC-%EC%8A%A4%EB%A7%88%ED%8A%B8-%EB%B0%B0%EB%84%88%EB%A1%9C-%EB%9E%9C%EB%94%A9-%ED%8E%98%EC%9D%B4%EC%A7%80-%EB%A7%8C%EB%93%A4%EA%B8%B0 h_01KB2W28TJM0X7K5Z7M2120MT9=%EC%9B%90%EB%A7%81%ED%81%AC-%EC%8A%A4%EB%A7%88%ED%8A%B8-%EB%B0%B0%EB%84%88%EB%A1%9C-%EB%9E%9C%EB%94%A9-%ED%8E%98%EC%9D%B4%EC%A7%80-%EB%A7%8C%EB%93%A4%EA%B8%B0 h_01KB2W28TKJZBNFR335SXKY6FC=endtoend-data-flow::b905b9a5 h_01KB2W28TKKA9NTQEC7ZA9E6EA=set-up-a-smart-banners-landing-page h_01KB2W28TKW8B6H4W0R9YJM3ZE=%EC%B0%B8%EA%B3%A0-5 h_01KB2W28TKRH3NC73J2JHNSMWD=%EC%B0%B8%EA%B3%A0-6 view-webtoapp-attribution-data=%EC%9B%B9-%EB%8C%80-%EC%95%A0%ED%94%8C%EB%A6%AC%EC%BC%80%EC%9D%B4%EC%85%98-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B8%B0 h_01KB2W28TKDAV34JGYJKF2VT43=%EC%9B%B9-%EB%8C%80-%EC%95%A0%ED%94%8C%EB%A6%AC%EC%BC%80%EC%9D%B4%EC%85%98-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B8%B0 view-in-the-dashboard=%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C%EC%97%90%EC%84%9C-%EB%B3%B4%EA%B8%B0 h_01KB2W28TKNWYXJX189EP2HPN2=%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C%EC%97%90%EC%84%9C-%EB%B3%B4%EA%B8%B0 view-in-raw-data-and-api-reports=%EC%9B%90%EC%8B%9C-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B0%8F-api-%EB%B3%B4%EA%B3%A0%EC%84%9C%EC%97%90%EC%84%9C-%EB%B3%B4%EA%B8%B0 h_01KB2W28TKJ1MAMM00KY3M3S2W=%EC%9B%90%EC%8B%9C-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B0%8F-api-%EB%B3%B4%EA%B3%A0%EC%84%9C%EC%97%90%EC%84%9C-%EB%B3%B4%EA%B8%B0 traits-and-limitations=%ED%8A%B9%EC%84%B1%EA%B3%BC-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD h_01KB2W28TKFY74YBXHD91QP9V0=%ED%8A%B9%EC%84%B1%EA%B3%BC-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD" />
