---
title: ChatGPT Ads(OpenAI) 연동 설정
metadata:
  keywords:
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2026-07-05T13:42:23Z'
  edited_at: '2026-10-25T11:55:50Z'
  id: 48439655791249
  locale: ko
  section: Measure paid media
  section_id: 6550990672401
  url: https://support.appsflyer.com/hc/ko/articles/48439655791249
---
> **한눈에 보기:** 앱스플라이어 통합 파트너인 ChatGPT Ads는 OpenAI의 광고 플랫폼 입니다. ChatGPT Ads 캠페인을 통해 발생한 모바일 앱 설치, 인앱 이벤트 및 웹사이트 전환을 측정하고 기여도를 분석할 수 있도록 연동 설정하세요.

<div id="about-the-integration-with-chatgpt-ads" />

## ChatGPT Ads 연동 알아보기

앱스플라이어 와 ChatGPT Ads(OpenAI)의 연동 통해 ChatGPT Ads 캠페인으로 발생한 앱 설치, 인앱 이벤트 및 웹사이트 전환을 측정하고 기여를 분석할 수 있습니다. 모바일 앱 과 웹사이트 측정 모두 지원합니다.

* **모바일 앱** - 앱스플라이어 설치 및 재참여를 귀하의 ChatGPT Ads 캠페인 성과로 귀속시키고, 인앱 이벤트 포스트백을 전송합니다.
* **웹사이트** - 앱스플라이어 웹 SDK(Web SDK)를 통해 캡처된 페이지 뷰, 콘텐츠 뷰, 구매 등의 웹 이벤트는 ChatGPT Ads 자바스크립트 픽셀의 추가 방식(또는 대체 방식)으로 ChatGPT Ads의 전환 API(CAPI)에 연동되어 전송됩니다.

웹사이트에서 ChatGPT Ads 픽셀도 함께 실행하는 경우, ChatGPT Ads는 공유된 이벤트 ID를 사용하여 서버 측(CAPI) 이벤트와 픽셀 이벤트 간의 중복을 제거하므로, 전환 수가 부풀려질 걱정 없이 두 가지를 동시에 병행하여 실행할 수 있습니다.

앱스플라이어로 전송하는 이벤트 페이로드에 해당 공통 ID를 `af_customer_event_id`로 포함하세요. 아래 [웹사이트 연동](#웹사이트-연동)을 참조하세요.

<div id="set-up-the-integration" />

## 연동 설정

측정하고자 하는 각 모바일 앱 및 웹사이트에 대해 개별적으로 연동을 설정하십시오. 각각의 앱과 웹사이트에 대해 ChatGPT Ads(OpenAI) Ads Manager 계정에서 발급받은 Pixel ID와 API 키가 필요합니다.

**선행 조건:**

* 연동을 설정하기 전에, 먼저 ChatGPT Ads 계정을 개설하세요.
* 모바일 앱 및 웹사이트 앱이 앱스플라이어에 설정되어 있어야 합니다. <Anchor target="_blank" href="/marketers/ko/docs/adding-an-app-to-appsflyer">더 알아보기</Anchor>

**연동을 설정하려면:**

1. **활성화 방법:** 앱스플라이어 의 사이드 메뉴에서 **Collaborate** > **Partner Integrations** > **Marketplace** 탭을 선택하세요.  
   **편집 방법:** 앱스플라이어 의 사이드 메뉴에서 **Collaborate** > **Partner Integrations** > **Active integrations** 탭을 선택하세요.
2. 연동을 설정하세요.

* [**모바일 앱**](#모바일-앱-연동) - 설치, 재참여 및 인앱 이벤트 ChatGPT Ads 캠페인에 기여(어트리뷰션)합니다.
* [**웹사이트**](#웹사이트-연동) - ChatGPT Ads 픽셀 수집 데이터와의 디듀플리케이션(중복 제거)을 통해, 웹상에서 발생한 전환 이벤트를 ChatGPT Ads의 전환 API(Conversions API)로 연동하여 전송합니다.

<div id="integrate-your-mobile-app" />

## 모바일 앱 연동

모바일 앱에서 ChatGPT Ads의 어트리뷰션 및 인앱 이벤트 포스트백을 설정하려면 다음 단계를 따르십시오.

**모바일 앱을 연동하려면:**

1. 앱스플라이어 의 사이드 메뉴에서 **Collaborate** > **Partner Integrations** > **Marketplace** 탭을 선택하세요.
2. 드롭다운 메뉴에서 모바일 앱 선택하세요.  
   **참고:** 앱이 실행되는 Android 및 iOS 앱과 같은 각 플랫폼에 대해 이 단계를 반복해야 합니다.
3. **ChatGPT Ads(OpenAI)** 를 검색하고 **연동**을 클릭하세요.
4. 아래 설명된 대로 탭의 구성을 완료하십시오.

<div id="integration-tab" />

<Accordion title="연동 탭">

<div id="activate-partner" />

#### 파트너 활성화

**연동을 활성화 하려면:**

**파트너 활성화** 토글을 켭니다.

**중요 사항:** ChatGPT Ads를 이용하는 동안에는 해당 토글이 **항상 켜져 있는 상태**를 유지해야 합니다. 연동을 비활성화하면 귀하의 캠페인에 대한 어트리뷰션 및 포스트백 기능이 중단됩니다.  
<Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">파트너 활성화</Anchor>에 대해 더 알아보세요.

<div id="general-settings" />

#### 일반 설정

다음 자격 증명을 입력하세요.

* **픽셀 ID** - ChatGPT Ads 관리자에서 픽셀이 생성됩니다. Ads Manager 계정의 전환 탭에서 확인하세요.
* **API 키** - Events API 호출을 인증하려면 API 키가 필요합니다. ChatGPT Ads Manager 계정의 '전환(Conversions)' 탭에서 확인하세요.   
  **참고:** 필요한 권한을 확보하려면 CAPI 키가 필요하므로, 광고 관리 API 키가 아닌 전환 API 키를 사용해야 합니다.

<div id="advanced-privacy" />

##### **고급 개인정보 보호**

고급 개인정보 보호(AP) 토글은 IDFA를 제공하지 않은 iOS 사용자(14.5 이상)의 이벤트가 OpenAI로 전송되는 방식을 제어합니다.

* 고급 개인정보 보호 **비활성화**: IDFA를 사용할 수 없는 경우에도 사용 가능한 모든 사용자 식별자(IP, user agent 등)와 함께 이벤트가 전송됩니다.
* 고급 개인정보 보호 **활성화**: `openai_int`에 어트리뷰션된 이벤트만 전송되며, 이러한 포스트백에는 어트리뷰션 데이터만 포함됩니다. 모든 사용자 수준 식별자가 전송 전 포스트백에서 제거되었습니다.

<div id="advanced-matching-data-sharing" />

##### **고급 매칭 데이터 공유**

해당 필드가 앱스플라이어로 전송된 이벤트 정보에 포함되어 있는 경우, 해시된 이메일, 해시된 전화번호, 해시된 이름, 해시된 성과 같은 고급 매칭 필드를 ChatGPT Ads와 공유하려면 활성화하세요. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/advanced-matching-data-sharing">고급 매칭 데이터 공유</Anchor>를 참고하세요.

<div id="default-postbacks" />

#### 기본 포스트백

포스트백은 앱스플라이어가 기여된 이벤트(설치 또는 인앱 액션 등)를 보고하기 위해 ChatGPT Ads에 전송하는 서버 간 알림입니다. 이 섹션에는 포스트백이 표시됩니다. <Anchor target="_blank" href="/marketers/ko/docs/set-up-re-attribution-window">설치 및 재기여 포스트백을 설정하는</Anchor> 방법을 알아보세요.

<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#default-postbacks">기본 포스트백 설정</Anchor>에 대해 더 알아보기.

<div id="in-app-event-settings" />

#### 인앱 이벤트 설정

ChatGPT Ads에 인앱 이벤트 포스트백을 전송할 수 있도록 필요한 자격 증명을 입력하세요.

* Pixel ID
* API 키

자세한 내용은 위의 [일반 설정](#일반-설정)을 참조하세요.

<div id="in-app-event-postbacks" />

#### 인앱 이벤트 포스트백

ChatGPT Ads로 전송할 인앱 이벤트 포스트백을 구성하십시오. <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration">더 알아보기</Anchor>

**인앱 이벤트 포스트백활성화:**

**인앱 이벤트 포스트백** 토글을 켜세요.

**인앱 이벤트 포스트백 윈도우**

설치, 재기여(re-attribution) 또는 재참여(re-engagement) 이후 앱스플라이어가 ChatGPT Ads로 인앱 이벤트 포스트백을 전송하는 기간을 정의합니다. <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration">더 알아보기</Anchor>

**이벤트 매핑**

이벤트가 ChatGPT Ads의 동일한 이벤트와 일치하도록 이벤트 이름을 매핑하세요. <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#이벤트-매핑">더 알아보기</Anchor>

ChatGPT Ads는 아래의 표준 이벤트를 지원하며, 하단에 포함되지 않은 이벤트에 대해서는 **Custom(맞춤)** 폴백을 제공합니다:

| ChatGPT Ads 이벤트 이름 | 사용 상황 |
| --- | --- |
| page\_viewed | 사용자가 중요 페이지에 도달하거나 이를 조회합니다. |
| contents\_viewed | 사용자가 특정 상품, 리스트, 아티클 또는 콘텐츠 단위를 조회합니다. |
| items\_added | 사용자가 장바구니, 번들 또는 선택 항목에 하나 이상의 아이템을 추가합니다. |
| checkout\_started | 사용자가 결제를 시작합니다. |
| order\_created | 구매가 완료되었습니다. |
| registration\_completed | 사용자가 계정 또는 이벤트 등록을 완료합니다. |
| lead\_created | 사용자가 리드 양식을 제출하거나 연락을 요청합니다. |
| appointment\_scheduled | 사용자가 미팅, 데모 또는 상담을 예약합니다. |
| trial\_started | 무료 체험이 시작됩니다. |
| subscription\_created | 유료 구독이 시작됩니다. |
| app\_opened | 모바일 앱을 엽니다. |
| 사용자 지정 | 표준 분류 체계에 포함되지 않는 모든 이벤트입니다. |

**이벤트 복제**

웹사이트에서 ChatGPT Ads Pixel도 함께 실행 중인 경우, 앱스플라이어가 이벤트를 중복 제거할 수 있도록 동일한 이벤트 ID를 앱스플라이어와 ChatGPT Ads 양쪽에 모두 전송하세요:

* 앱스플라이어로 전송하는 이벤트 페이로드에 `af_customer_event_id`를 포함하세요. Web SDK의 경우 eventValue 내에, S2S(서버 간 통신) API의 경우 event\_value 내에 추가해야 합니다.
* 해당하는 Pixel 이벤트에도 동일한 값을 전송하세요.

앱스플라이어는 이 값을 이벤트 ID로 ChatGPT Ads에 전달합니다. 그러면 ChatGPT Ads는 이 값을 바탕으로 앱스플라이어에서 수신한 서버 측 이벤트와 Pixel 이벤트의 중복을 제거하여, 앱스플라이어가 전환을 한 번만 집계하도록 합니다.

`af_customer_event_id`를 전송하지 않으면 앱스플라이어가 이벤트 ID를 자동으로 생성합니다. 이 ID는 Pixel 이벤트와 일치하지 않게 됩니다.

자세한 내용은 '앱스플라이어 Web SDK 연동'을 참조하세요.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="어트리뷰션 링크 탭">

ChatGPT Ads(OpenAI)는 어트리뷰션 링크를 지원합니다.

<div id="choose-your-attribution-type" />

#### 어트리뷰션 유형을 선택하세요

다음 여부를 결정하세요.

1. 사용자를 앱 스토어로 직접 이동시킵니다. 이 경우 캠페인 요구 사항과 타게팅 설정에 따라 최종 URL로 단일 플랫폼 어트리뷰션 링크 또는 <Anchor target="_blank" href="/marketers/ko/docs/onelink-guide">OneLink</Anchor>를 생성해야 합니다.   

   또는
2. 랜딩 페이지를 광고 목적지로 사용한 다음, <Anchor target="_blank" href="/marketers/ko/docs/onelink-smart-script-overview">Smart Script</Anchor> 또는 <Anchor target="_blank" href="/marketers/ko/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banner</Anchor>를 사용하여 사용자를 App Store나 Google Play로 이동시킵니다(어트리뷰션이 가능한 링크를 생성하면서 이동).

<div id="select-parameters" />

#### 파라미터 선택

포함할 어트리뷰션 링크 파라미터를 선택합니다.

* 포함할 어트리뷰션 링크 파라미터(예: **캠페인 이름** 및 **사이트 ID**)를 선택하고 **클릭스루 룩백 윈도우**를 설정합니다(앱스플라이어 권장 기본값은 7일). 앱스플라이어는 ChatGPT Ads 캠페인에 사용할 어트리뷰션 링크를 자동으로 생성합니다.
* 다음 URL 파라미터는 이러한 동적 URL 매크로를 사용하여 ChatGPT에서 자동으로 채울 수 있습니다:
  * `af_partner_account_id={ad_account_id}`
  * `af_c_id={campaign_id}`
  * `af_adset_id={ad_group_id}`
  * `af_ad_id={ad_id}`
  * `clickid={oppref}`
* 이름 필드 매크로는 지원되지 않습니다.

<div id="important" />

> 🚧 **중요**
>
> * 앱스플라이어가 ChatGPT Ads의 클릭 ID를 캡처하여 다시 ChatGPT Ads로 전송할 수 있도록, 광고가 App Store나 Google Play로 직접 연결되는 경우에는 반드시 `clickid={oppref}`를 사용하세요. 광고 목적지가 Smart Script가 적용된 랜딩 페이지인 경우, 유입되는 `oppref` 파라미터를 캡처하여 나가는 아웃바운드 URL의 `clickid`에 매핑해야 합니다.
> * ChatGPT Ads는 해당 파라미터가 **Ad destination URL** 필드가 아닌 **Tracking parameters** 필드에 입력된 경우에만 매크로(예: `{campaign_id}`)를 치환합니다. 쿼리 파라미터(예: `af_c_id={campaign_id}`)를 **Tracking parameters** 필드에 붙여넣고, **Ad destination URL** 필드에는 순수 목적지 URL만 입력하세요.

**참고:** 생성된 링크 에는 다음이 포함됩니다`openai_int`(앱스플라이어 내 ChatGPT Ads 연동 ID).

<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#attribution-link-tab">어트리뷰션 링크</Anchor>에 대해 더 알아보기.

</Accordion>

<div id="cost-tab" />

<Accordion title="비용 탭">

현재 ChatGPT Ads에 대한 비용 API 연동은 지원되지 않습니다.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="광고 수익 탭">

ChatGPT Ads에서 광고 수익 데이터를 가져올 수 없습니다. 캠페인 최적화를 위해 포스트백 또는 UA 시그널을 활용하여 광고 수익 데이터를 공유합니다.

</Accordion>

<div id="permissions-tab" />

<Accordion title="권한 탭">

ChatGPT Ads 팀원들에게 귀하의 데이터에 대한 접근 권한을 부여하려면 **광고 네트워크 권한**을 활성화하세요. 활성화되면 연동 구성, 리텐션 및 코호트 리포트 접근, 또는 집계된 전환 및 수익 데이터 조회 등 부여할 개별 권한을 선택합니다. ChatGPT Ads에 대한 어트리뷰션 기능이 비활성화된 상태이더라도 여전히 권한을 부여할 수 있습니다.

<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#permissions-tab">권한</Anchor>에 대해 더 알아보기.

</Accordion>

<div id="integrate-your-website" />

## 웹사이트 연동

웹사이트에서 ChatGPT Ads로 서버 측 이벤트 전달을 설정하려면 다음 단계를 따르세요.

**웹사이트를 연동하려면:**

1. 앱스플라이어의 사이드 메뉴에서 **Collaborate** > **Partner Integrations** > **Marketplace** 탭을 선택합니다.
2. 드롭다운 메뉴에서 웹사이트 앱을 선택하세요.
3. **ChatGPT Ads(OpenAI)** 를 검색하고 **연동**을 클릭하세요.
4. 아래 설명된 대로 연동 탭에서 구성을 완료하세요.

<div id="integration-tab::2739744d" />

<Accordion title="연동 탭">

<div id="activate-partner-1" />

#### 파트너 활성화

**연동을 활성화 하려면:**

**파트너 활성화** 토글을 켭니다.

**중요 사항:** ChatGPT Ads를 이용하는 동안에는 해당 토글이 **항상 켜져 있는 상태**를 유지해야 합니다. 연동을 비활성화하면 웹사이트의 이벤트 전달 기능이 중단됩니다.  
<Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">파트너 활성화</Anchor>에 대해 더 알아보세요.

<div id="in-app-event-settings-1" />

#### 인앱 이벤트 설정

ChatGPT Ads로 이벤트 포스트백을 전송하려면 다음 자격 증명을 입력하세요.

* **Pixel ID** - ChatGPT Ads 관리자에서 픽셀이 생성됩니다. Ads Manager 계정의 전환 탭에서 확인하세요.
* **API 키** - Events API 호출을 인증하려면 API 키가 필요합니다. ChatGPT Ads Manager 계정의 '전환(Conversions)' 탭에서 확인하세요.

**고급 매칭 데이터 공유:** 해당 필드가 앱스플라이어로 전송된 이벤트 정보에 포함되어 있는 경우, 해시된 이메일, 해시된 전화번호, 해시된 이름, 해시된 성과 같은 고급 매칭 필드를 ChatGPT Ads와 공유하려면 활성화하세요. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/advanced-matching-data-sharing">고급 매칭 데이터 공유</Anchor>를 참조하세요.

<div id="in-app-event-postbacks-1" />

#### 인앱 이벤트 포스트백

ChatGPT Ads로 전송할 이벤트 포스트백을 설정하세요. <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration">더 알아보기</Anchor>

**이벤트 포스트백을 활성화하려면:**

**인앱 이벤트 포스트백** 토글을 켜세요.

**이벤트 매핑**

이벤트가 ChatGPT Ads의 동일한 이벤트와 일치하도록 이벤트 이름을 매핑하세요. ChatGPT Ads가 지원하는 이벤트는 위의 표준 이벤트 표 참조하세요. <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#이벤트-매핑">더 알아보기</Anchor>

</Accordion>

<div id="h_01KWVSPJ9WATTRLNK" />

<Accordion title="어트리뷰션 링크 탭">

ChatGPT Ads(OpenAI)는 웹사이트 연동 시 외부 어트리뷰션 링크를 사용하지 않습니다. 앱스플라이어 웹 SDK는 웹 이벤트를 측정하고 이를 ChatGPT Ads의 전환 API로 직접 포워딩하므로, 링크 기반의 어트리뷰션 설정은 필요하지 않습니다.

</Accordion>

<div id="h_01KWVSPJ9WCOST" />

<Accordion title="비용 탭">

웹사이트 연동의 경우 ChatGPT Ads에 대한 비용 데이터는 지원되지 않습니다.

</Accordion>

<div id="h_01KWVSPJ9WADREV" />

<Accordion title="광고 수익 탭">

웹사이트 연동의 경우 ChatGPT Ads에 대한 광고 수익 데이터는 지원되지 않습니다.

</Accordion>

<div id="h_01KWVSPJ9WPERM" />

<Accordion title="권한 탭">

웹사이트 연동의 경우 ChatGPT Ads에 대한 권한 설정 기능은 지원되지 않습니다.

</Accordion>

<div id="traits-and-limitations" />

## 특징과 제한사항

| 특징 | 설명 |
| --- | --- |
| 지원하는 국가 | ChatGPT Ads Manager를 사용할 수 있는 <Anchor target="_blank" href="https://help.openai.com/en/articles/20001245-ads-manager-availability">국가 목록</Anchor>입니다. |

<div id="see-also" />

> 📄 **참고 자료**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner">파트너 연동</Anchor>

<div data-zendesk-anchors="about-the-integration=chatgpt-ads-%EC%97%B0%EB%8F%99-%EC%95%8C%EC%95%84%EB%B3%B4%EA%B8%B0 h_01KWS8SS8RE2VQ275MFB7CT39J=chatgpt-ads-%EC%97%B0%EB%8F%99-%EC%95%8C%EC%95%84%EB%B3%B4%EA%B8%B0 set-up-the%20integration=%EC%97%B0%EB%8F%99-%EC%84%A4%EC%A0%95 h_01H95QTA3Z5HXW39AHAF8FMFWH=%EC%97%B0%EB%8F%99-%EC%84%A4%EC%A0%95 integrate-your-mobile-app=%EB%AA%A8%EB%B0%94%EC%9D%BC-%EC%95%B1-%EC%97%B0%EB%8F%99 h_01KWVBQG0G85W6QJ8AT2520GTX=%EB%AA%A8%EB%B0%94%EC%9D%BC-%EC%95%B1-%EC%97%B0%EB%8F%99 h_01KWVK5J7FBA81238JD4AD0219=integration-tab activate-partner=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 h_01H95QTA3ZGEM34HY1A7NC8NX7=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 general-settings=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 h_01KWVKHV36H34XCHYBFRHNF8TB=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 h_01M39MMERMEBK470T0NDCVRN2E=%EA%B3%A0%EA%B8%89-%EA%B0%9C%EC%9D%B8%EC%A0%95%EB%B3%B4-%EB%B3%B4%ED%98%B8 h_01M39MP266X5KME19RBVQZRDE6=%EA%B3%A0%EA%B8%89-%EB%A7%A4%EC%B9%AD-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B3%B5%EC%9C%A0 default-postbacks=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01KWVKZJ7AZ8Z4CFM8J0PV071A=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 inapp-event-settings=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95 h_01JTDP2T0BFP5WP03X5EMXVAWA=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95 inapp-event-postbacks=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01KWVMZC74AQSN7BDQP2QQWBT4=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01KWVK5J7FE0ZF74NGXKSASMBV=attribution-link-tab h_01_choose-your-attribution-type=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%9C%A0%ED%98%95%EC%9D%84-%EC%84%A0%ED%83%9D%ED%95%98%EC%84%B8%EC%9A%94 choose-your-attribution-type=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%9C%A0%ED%98%95%EC%9D%84-%EC%84%A0%ED%83%9D%ED%95%98%EC%84%B8%EC%9A%94 h_01_select-parameters=%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0-%EC%84%A0%ED%83%9D select-parameters=%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0-%EC%84%A0%ED%83%9D h_01M254BFC0V68RJ6B903D8XKD3=%EC%A4%91%EC%9A%94 h_01KWVK5J7FK8BAQKEMNA35ABPY=cost-tab h_01KWVK5J7FQRYXQ9FGCWHWY16T=ad-revenue-tab h_01KWVK5J7G3E8NSNDG4CR9FA7N=permissions-tab integrate-your-website=%EC%9B%B9%EC%82%AC%EC%9D%B4%ED%8A%B8-%EC%97%B0%EB%8F%99 h_01KWVSJRYSQEH12C5RH7BN4CC2=%EC%9B%B9%EC%82%AC%EC%9D%B4%ED%8A%B8-%EC%97%B0%EB%8F%99 h_01KWVSPJ9WJERF84ZNGTS7P0HZ=integration-tab::2739744d activate-partner::3c5a91e7=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94-1 h_01KWVSPJ9WBQ2AS5JZPTJZPTRG=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94-1 inapp-event-settings::a3adef08=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95-1 h_01KWVSPJ9WV7ZQZD00ZB7T639X=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95-1 inapp-event-postbacks::c3d06354=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-1 h_01KWVSPJ9WA7Q1M281Q5NBYHV7=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-1 attribution-link-tab::3e2b1646=h_01KWVSPJ9WATTRLNK cost-tab::c486dc3c=h_01KWVSPJ9WCOST ad-revenue-tab::84884d8a=h_01KWVSPJ9WADREV permissions-tab::6f805250=h_01KWVSPJ9WPERM traits-and-limitations=%ED%8A%B9%EC%A7%95%EA%B3%BC-%EC%A0%9C%ED%95%9C%EC%82%AC%ED%95%AD h_01KX3DAS0FBTKGKE7CZJTDTY2X=%ED%8A%B9%EC%A7%95%EA%B3%BC-%EC%A0%9C%ED%95%9C%EC%82%AC%ED%95%AD h_01KWVT1XJ2FKP1CACRV24C1R8E=%EC%B0%B8%EA%B3%A0-%EC%9E%90%EB%A3%8C" />
