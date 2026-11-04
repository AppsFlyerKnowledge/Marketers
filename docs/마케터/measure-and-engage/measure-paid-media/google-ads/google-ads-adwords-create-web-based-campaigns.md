---
title: 'Google Ads (AdWords): 웹 기반 캠페인 만들기'
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
  created_at: '2024-05-16T09:12:15Z'
  edited_at: '2026-10-14T10:37:35Z'
  id: 25096718837137
  locale: ko
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/ko/articles/25096718837137
---
> **한눈에 보기:** Google Ads에서 웹에서 앱으로의 전환에 기여하는 웹 캠페인을 만듭니다.

> 📘 **참고**
>
> 이 문서는 모바일 앱을 홍보하는 웹 캠페인에 중점을 둡니다. PC 또는 콘솔 앱을 홍보하는 캠페인을 만들고 싶다면 <Anchor target="_blank" href="/marketers/ko/docs/google-ads-web-integration-for-pc-and-console-apps">Google Ads Web—PC 및 콘솔 앱 연동</Anchor>을 참조하세요.

<div id="overview" />

## 개요

앱스플라이어는 웹 기반 캠페인에 대해 Google Ads(`googleads_int`)와의 연동을 지원하고 Google Offline Conversion API(OCI)를 통해 캠페인의 어트리뷰션 및 전환 데이터를 리포트합니다.

이 문서에서는 앱스플라이어와 Google Ads에서 Google Ads와 상호 작용하는 웹 사용자를 대상으로 모바일 웹 캠페인을 설정하는 방법을 알아봅니다.

캠페인은 사용자가 광고를 클릭하고 랜딩 페이지로 리디렉션될 때 시작되는 사용자 여정을 기반으로 합니다. 이 페이지에는 어트리뷰션 링크를 생성하는 앱스플라이어 스마트 스크립트 또는 스마트 배너가 포함됩니다.

사용자가 이러한 링크를 클릭하면 앱을 다운로드하고 설치할 수 있는 앱 스토어로 이동하게 됩니다. 설치 및 후속 인앱 이벤트는 앱스플라이어에 기록되고 OCI를 통해 Google Ads에 보고됩니다.

구글은 이 데이터를 사용하여 광고 타겟팅을 최적화하고, 성과를 측정하고, 사용자 지정 오디언스를 구축합니다.

<div id="prerequisite" />

### 전제 조건

웹 캠페인용 Google Ads 연동을 활성화하기 전에 다음 사항을 확인하세요.

* 모바일 앱
* 앱스플라이어 계정
* <Anchor target="_blank" href="/marketers/ko/docs/user-management">적절한 역할 또는 권한</Anchor>과 관련 앱에 대한 액세스 권한을 가진 앱스플라이어 사용자

<div id="create-a-google-ads-web-campaign" />

### Google Ads 웹 캠페인을 만드는 방법

이 문서에는 앱스플라이어를 사용하여 모바일, PC 및 콘솔 앱용 Google Ads에서 웹 캠페인을 설정하는 방법에 대한 정보와 단계가 포함되어 있습니다. 이 설정에는 Google Ads와 앱스플라이어 간의 연동을 정의하고 캠페인 어트리뷰션 링크를 설정하는 작업이 포함됩니다.

* [앱스플라이어에서 Google Ads 연동 설정](#앱스플라이어에서-google-ads-연동-생성) (필수)
* [Google Ads에서 Google Ads 연동 설정](#google-ads에서-웹-캠페인-만들기) (필수)

Google Ads와 앱스플라이어 연동을 통해 1단계에서 어트리뷰션 링크를 설정한 후, 2단계에서는 랜딩 페이지를 만드는 데 중점을 둡니다. 여기서 원링크 스마트 스크립트 또는 스마트 배너는 어트리뷰션 링크를 사용하여 행동 유도 버튼을 생성하고 사용자를 앱 스토어로 이끕니다.

* [원링크 스마트 스크립트로 랜딩 페이지 만들기](#원링크-스마트-스크립트로-랜딩-페이지-만들기) (선택 사항)
* [원링크 스마트 배너로 랜딩 페이지 만들기](#원링크-스마트-배너로-랜딩-페이지-만들기) (선택 사항)

<div id="note-1" />

<div id="create-a-google-ads-integration-in-appsflyer" />

## 앱스플라이어에서 Google Ads 연동 생성

먼저 웹 캠페인을 위해 Google Ads와의 연동을 활성화하고 앱스플라이어가 OCI에 보내는 포스트백을 설정합니다.

<div id="a-activate-the-google-ads-for-web-campaigns-integration" />

<Accordion title="1. 웹 캠페인 연동을 위해 Google Ads 활성화">

1. 앱스플라이어의 사이드 메뉴에서**협업**>**파트너 마켓플레이스**로 이동합니다.
2. **Google Ads 웹**을 검색하여 선택합니다.
3. **연동 설정**을 클릭합니다. **활성 연동** 설정 페이지로 이동합니다.
4. **연동** 탭에서 **파트너 활성화**를 선택합니다. **참고:** 파트너와 작업하는 동안에는 토글이 켜져 있어야(**활성화됨**) 합니다.
5. **고급 개인 정보 보호**(iOS 앱 연동을 설정하는 경우)를 끕니다.

   > 📘 **참고**
   >
   > Google에 로그인하고 아래 단계에서 앱스플라이어가 토큰을 가져오도록 허용하면 **누락된 토큰** 오류 메시지가 더 이상 나타나지 않습니다. 로그인 후에도 오류가 지속되면 [토큰에 필요한 권한이 있는지 확인하세요](#access-token-permissions).

6. **첫 번째 열린 전환 ID**에 Google Ads에서 설정한 `First open` 전환 동작의 ID를 입력합니다. ID를 찾으려면 Google Ads로 이동하여 **처음 열린** 전환 동작 페이지의 **세부 정보 탭**을 엽니다. 그런 다음 페이지 URL에서 `ctid=*` 쿼리 매개변수의 값을 복사합니다. 예를 들어, `ctid=123456789`인 경우 `123456789`을 **첫 번째 오픈 전환 작업 ID** 상자에 삽입하세요.

   [![](https://files.readme.io/0bbe655051204d8902b82f2f8d8b12f183ef40f9e84c542972db767707d75a9d-26324053660177.png)](https://files.readme.io/0bbe655051204d8902b82f2f8d8b12f183ef40f9e84c542972db767707d75a9d-26324053660177.png)

   <div id="note-2" />

   <div id="tip" />

   > 👍 **팁**
   >
   > Google Ads에서 '처음 열기' 동작을 여전히 설정해야 하는 경우 동작이 완전히 설정될 때까지 자리표시자 값을 임시로 입력할 수 있습니다.

7. **고객 ID**를 입력합니다. Google Ads Manager에서 불러올 수 있습니다.
   1. <span class="af-ol-a"></span>Google Ads 계정에 로그인합니다.
   2. 오른쪽 상단에서 Google 계정 아이콘을 클릭하고 고객 ID가 표시되는 위치까지 아래로 스크롤합니다.
   3. 여러 Google Ads 계정에서 앱 캠페인을 실행 중인 경우 교차 계정 전환 추적을 위해 관리자(MCC)의 고객 ID를 사용해야 합니다. [MCC 계정 구성에 대한 Google 지침](https://support.google.com/google-ads/answer/3061730?sjid=4528491462900554442-NC)을 참조하세요.
8. 앱스플라이어가 Google Ads에 전환을 업로드할 수 있도록 하려면 **Google로 로그인합니다**.
9. Google에서, 고객 ID를 불러온 MCC 계정의 관리자 계정을 선택하세요.
10. **허용**을 클릭합니다.

</Accordion>

<div id="d-enable-view-through-attribution-for-meta-web" />

<Accordion title="2. 뷰-쓰루 어트리뷰션 활성화">

앱스플라이어는 [스마트 스크립트](#set-up-a-smart-script-crossplatform-landing-page) 또는 [스마트 배너](#set-up-a-smart-banners-landing-page)가 활성화된 랜딩 페이지를 사용하여 Google 웹 캠페인에 대한 뷰-쓰루 어트리뷰션을 지원합니다. 이는 사용자가 광고를 직접 클릭하지 않더라도 광고 노출에 의해 촉발된 앱 설치에 대한 확률적 모델링(PMOD) 어트리뷰션 분석을 가능하게 합니다.

사용자가 Google Ads를 보고 [스마트 스크립트](#set-up-a-smart-script-crossplatform-landing-page) 또는 [스마트 배너](#set-up-a-smart-banners-landing-page)가 활성화된 랜딩 페이지에 도착하면, 앱스플라이어는 크로스 플랫폼에서 발생한 앱 인스톨을 원래 웹 노출로 역추적하여 어트리뷰션할 수 있습니다.

사용 가능한 경우, 앱스플라이어는 Google에 대한 포스트백에 `gclid`을 포함합니다.

**뷰-쓰루 어트리뷰션 활성화 방법:**

1. 앱스플라이어에서 사이드바에서 **활성 연동** > **Google Ads Web**을 엽니다.
2. **연동** 탭에서 **인스톨 어트리뷰션** 섹션으로 스크롤합니다.
3. **뷰-쓰루 어트리뷰션 인스톨**을 켭니다.
4. **[선택 사항]** **크로스 플랫폼 어트리뷰션 우선순위 동등하게 설정**을 켜고 룩백 윈도우를 설정합니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">크로스 플랫폼 노출에 대해 동일한 우선순위 활성화하기</Anchor> 항목을 참조하십시오.
5. **어트리뷰션** 탭을 엽니다.
6. **뷰-쓰루 어트리뷰션** 섹션으로 스크롤하여 선호하는 **뷰-쓰루 룩백 윈도우**를 설정합니다(최대 24시간).
7. 변경 사항을 적용하려면 **연동 저장**을 클릭합니다.

</Accordion>

<div id="b-set-inapp-event-postbacks" />

<Accordion title="3. 인앱 이벤트 포스트백 설정">

현재 설치 이벤트만이 OCI API를 통해 Google Ads for Web으로 기본 포스트백을 자동으로 유발하는 유일한 이벤트입니다. 다른 이벤트 유형의 경우, 앱스플라이어 이벤트를 Google Ads 전환 동작 ID('전환 동작'은 Google Ads에서 어트리뷰션 이벤트를 지칭하는 용어임)에 매핑하여 사용자 지정 포스트백을 생성할 수 있습니다. AF 이벤트에 매핑해야 하는 Google Ads Web 이벤트에 대해 알아보려면 Google Ads 관리자에게 문의하세요.

1. **인앱 이벤트 포스트백**을 켭니다.
2. 필요한 경우 인앱 이벤트 포스트백 윈도우를 설정합니다(인앱 이벤트 포스트백 윈도우 구성에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#인앱-이벤트-포스트백-기간">이 글</Anchor>을 참고하세요).
3. **이벤트 추가**를 클릭하여 목록에 SDK 또는 서버-to-서버 이벤트를 추가합니다.
4. **앱스플라이어 이벤트** 열의 드롭다운 상자에서 이벤트 이름을 선택합니다. 앱스플라이어는 앱에 연동된 SDK 또는 서버-to-서버 이벤트로부터 이벤트 이름을 수신합니다.
5. **파트너 이벤트에 매핑됨** 열에서 앱스플라이어 이벤트를 해당 Google 전환 동작 ID에 매핑해야 합니다. 그 작업을 수행하기 전에 Google Ads에서 필요한 Google 전환 작업을 설정해야 합니다. Google Ads에서 전환 동작을 설정하는 방법을 알아보려면 [사용자 지정 전환 동작 생성](#b-create-custom-conversion-actions)을 참조하세요.

   **Google Ads에서 전환 작업 ID를 찾으려면:**

   1. <span class="af-ol-a"></span>Google Ads로 이동합니다.
   2. 매핑하려는 전환 작업의 페이지를 엽니다.
   3. 세부정보 탭을 엽니다.
   4. 페이지 URL에서 `ctid=*` 쿼리 매개변수의 값을 복사합니다.
   5. 앱스플라이어로 돌아가기
   6. 이를 **파트너 이벤트에 매핑됨** 열에 붙여넣습니다. 예를 들어, `ctid=123456789`인 경우 `123456789`을 붙여넣습니다.
6. **사용자 대상** 열에서 **이 파트너만**을 선택합니다.
7. **포함** 열에서 Revenue 값(이벤트에 있는 경우)을 포함한 모든 이벤트 파라미터를 포스트백으로 전송할지 여부를 선택합니다.
8. [선택 사항] **조건 추가** 아이콘을 클릭하여 이벤트에 대한 <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#조건부-인앱-이벤트-포스트백">조건을 설정</Anchor>합니다.
9. **연동 저장**을 클릭합니다.
10. [선택 사항] 연동을 저장한 후 구성 페이지에 남아 있는 동안 더 많은 앱을 파트너와 통합할 수 있습니다.
    1. <span class="af-ol-a"></span>왼쪽 상단에서 파트너 이름 아래의 앱 이름을 클릭하여 앱 목록을 엽니다.
    2. 드롭다운 목록에서 다른 앱을 선택합니다.
    3. 선택한 앱에 대해 연동 단계를 반복합니다.

</Accordion>

<div id="c-configure-the-onelink-template" />

<Accordion title="4. OneLink 템플릿 구성하기">

Google Ads 캠페인에 대한 원링크 어트리뷰션 링크를 생성하기 전에 템플릿을 설정해야 합니다. 그런 다음 템플릿을 기반으로 원링크 어트리뷰션 URL을 생성하여 Google 추적 템플릿 URL로 사용할 수 있습니다.

> 📘 **참고**
>
> 아래 지침은 스마트 스크립트를 사용하여 구글 웹 캠페인용 원링크 템플릿을 만드는 방법에 중점을 둡니다. 원링크 템플릿 설정 방법에 대한 종합 가이드는 <Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template#원링크-템플릿-만들기">원링크 템플릿</Anchor> 문서의 <Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template#원링크-템플릿-만들기">원링크 템플릿을 만드는 방법</Anchor> 섹션을 참조하세요.

1. **새 템플릿** 또는 **템플릿 편집** 페이지의 **리디렉션** 섹션에서 다음 설정을 구성합니다:
   * **앱이 설치되지 않은 경우** > **다음으로 리디렉션**: 선호하는 옵션을 선택합니다. 여기서 설정한 리디렉션 값은 Google 추적 템플릿에 배치한 리디렉션 매개변수(<Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_android_url">`af_android_url`</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_ios_url">`af_ios_url`</Anchor>)의 `{lpurl}`값에 의해 재정의됩니다; [여기](#추적-템플릿-url-설정)를 참조하세요.
   * **앱이 설치된 경우**: 구글은 최종 URL로의 리디렉션 외에는 어떤 리디렉션도 허용하지 않으므로 앱을 시작할 때 유니버설 링크, URI 스킴 또는 모든 링크를 설정하지 **않도록** 하세요.
   * **데스크톱 웹페이지에서 링크를 클릭한 경우** > **다음으로 리디렉션**: 선호하는 옵션을 선택합니다. 여기에서 설정하는 리디렉션 값은 구글 추적 템플릿에 입력하는 리디렉션 파라미터(<Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_web_dp">`af_web_dp`</Anchor>)의 `{lpurl}`값으로 재정의됩니다. [여기](#추적-템플릿-url-설정)를 참조하세요.
2. **템플릿 만들기**를 클릭합니다.

</Accordion>

<div id="create-a-web-campaign-in-google-ads" />

## Google Ads에서 웹 캠페인 만들기

Google Ads에서 다음 단계를 수행합니다.

<div id="a-set-the-campaign-type-objective-and-goals" />

<Accordion title="1. 캠페인 유형, 목적, 목표 설정">

Google Ads에서는 여기에서 선택한 캠페인 유형의 목적과 목표를 사용하여 올바른 입찰 전략을 정하고 캠페인 성과를 최적화합니다.

1. Google Ads에 로그인하여 캠페인을 만듭니다.
2. 캠페인 목표를 선택합니다.

   [![](https://files.readme.io/90063f7fe5a363ed498271148c4165969cc63c708a73ab25363d2263a79b0828-26324053661201.png)](https://files.readme.io/90063f7fe5a363ed498271148c4165969cc63c708a73ab25363d2263a79b0828-26324053661201.png)

   * “앱 프로모션"(모바일 앱 캠페인에만 사용 가능)을 제외한 모든 목표가 적용됩니다.
   * 특정 인앱 이벤트를 기반으로 최적화하려면 “판매” 캠페인 목표를 설정하는 것이 좋습니다.
3. 전환 이벤트를 선택합니다.

   [![](https://files.readme.io/5ca0a0425af24d5926dc0a7a3529632e22bd140423e87c026ff1527e7a0341b3-26324096257169.png)](https://files.readme.io/5ca0a0425af24d5926dc0a7a3529632e22bd140423e87c026ff1527e7a0341b3-26324096257169.png)

   * 기본적으로, 사전 정의된 계정 수준의 캠페인 목표가 표시됩니다. 이들 목표를 보관하거나 캠페인과 관련 없는 목표는 삭제할 수 있습니다.
   * Google이 최적화하기를 원하는 목표가 보이지 않으면

     <Anchor target="_blank" href="/marketers/ko/docs/google-ads-web-integration-for-pc-and-console-apps#creating-conversion-actions-and-goals">사용자 정의 전환 작업 및 목표를 만듭니다.</Anchor>
   * 전환 페이지에서 사전 정의된 목표를 편집할 수도 있습니다.
4. 캠페인 유형을 선택합니다.

   [![](https://files.readme.io/14daea1c1edf92854e21d0a4c5d34372a4e062d68a4613967bb4f40d0d1e720f-26324053659281.png)](https://files.readme.io/14daea1c1edf92854e21d0a4c5d34372a4e062d68a4613967bb4f40d0d1e720f-26324053659281.png)

   * 제품 카탈로그가 필요하고 인증된 도메인으로 제한되는 ‘쇼핑’을 제외한 모든 캠페인 유형을 적용할 수 있습니다.

</Accordion>

<div id="b-create-custom-conversion-actions" />

<Accordion title="2. 사용자 지정 전환 동작 만들기">

다음으로, [앱스플라이어에서 설정한 인앱 이벤트](#b-set-inapp-event-postbacks) 각각에 대해 Google Ads에서 해당 전환 동작을 만들어야 합니다. 전환 동작 생성을 완료한 후 새로 생성된 동작의 ID를 복사하여 앱스플라이어 인앱 이벤트에 매핑해야 합니다.

사용자 지정 Google Ads 전환 동작과 목표를 만드는 방법은 다음과 같습니다.

1. Google Ads 계정 개요 페이지의 사이드 메뉴에서 **목표 > 전환 > 요약**을 선택합니다.
2. **+ 새 전환 작업**을 클릭합니다.
3. 전환 유형 목록에서 **가져오기**를 선택하고 다음 중 하나를 선택합니다.

   * **API 또는 업로드를 사용한 수동 가져오기 > 클릭을 통한 전환 추적**

   또는

   * **CRM, 파일 또는 기타 데이터 소스 > 클릭으로 인한 전환 추적**을 선택하고 데이터 소스에서 **‘이 단계를 건너뛰고 나중에 데이터 소스 설정’** 을 선택합니다.
4. **계속**을 클릭하세요.
5. **전환 목표**에서 전환 동작 카테고리를 선택합니다.
6. **전환 이름 입력**에 전환 동작의 이름을 입력합니다.

   <div id="warning" />

   > 🚧 **중요!**
   >
   > GBRAID/WBRAID(GCLID 외 추가로)와 함께 오프라인 전환 API를 사용하려면 전환 작업의 **Count** 필드가 **‘매번’** (기본값)으로 설정되어 있고 **‘한 번’** 으로 설정되어 있지 않은지 확인하십시오.

7. **전환 이름**을 입력한 다음 **추가**를 클릭합니다. **참고**: 캠페인을 단일 동작에만 최적화하려는 경우 해당 동작만 이 카테고리에 포함하세요. 예를 들어, **첫 번째 열기** 전환 동작에 맞춰 캠페인을 최적화하려면 해당 캠페인이 해당 카테고리에서 유일한 캠페인이어야 합니다. 그러면 캠페인 생성 시 성과 최적화를 위한 전환 목표로 이 카테고리를 선택할 수 있습니다.
8. **저장 후 계속**을 클릭한 다음 데이터 소스를 설정하지 않고 **완료**를 클릭합니다. 새로운 전환 작업은 처음에 "비활성"으로 표시될 수 있지만, 실제 데이터가 전송되면 "활성"으로 변경됩니다.
9. 새 전환 동작을 앱스플라이어 포스트백 이벤트에 매핑하려면 새 전환 동작 ID를 검색하세요. 전환 목표 **요약 페이지**에서 생성한 전환 동작을 클릭하고 전환 동작 페이지 URL에서 `ctid=*` 쿼리 파라미터의 값을 복사합니다.

   [![](https://files.readme.io/0bbe655051204d8902b82f2f8d8b12f183ef40f9e84c542972db767707d75a9d-26324053660177.png)](https://files.readme.io/0bbe655051204d8902b82f2f8d8b12f183ef40f9e84c542972db767707d75a9d-26324053660177.png)
10. 앱스플라이어에서 구글에서 최적화하도록 하려는 포스트백 이벤트의 **파트너에 매핑됨 이벤트** 열에 `ctid` 값을 붙여넣습니다. [인앱 이벤트 포스트백을 설정합니다](#b-set-inapp-event-postbacks).

</Accordion>

<div id="c-set-the-campaign-urls" />

<Accordion title="3. 캠페인 URL 설정">

Google Web Ads 캠페인은 각 인게이지먼트에 대해 최종 URL과 추적 템플릿 URL이라는 두 URL을 활용합니다. 이러한 URL은 광고를 클릭하면 동시에 활성화되는데, 구글에서는 이 기능을 병렬 추적이라고 합니다. 병렬 추적에 대한 자세한 내용은 <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7544674?hl=en">구글 문서</Anchor>에서 확인할 수 있습니다.

<div id="warning-2" />

<div id="warning-1" />

<div id="set-the-final-url" />

#### 최종 URL을 설정하는 방법은 다음과 같습니다.

구글에서는 <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6080568?sjid=9660882197247124000-EU">최종 URL</Anchor>을 "사용자가 광고를 클릭하면 연결되는 웹사이트에서 웹페이지의 URL 주소"로 정의합니다. ‘랜딩 페이지'라고도 합니다.

**최종 URL을 설정하는 방법은 다음과 같습니다.**

1. Google Ads에서 **캠페인** > **광고** 페이지를 엽니다.
2. 광고 행에서 수정 아이콘을 클릭합니다.

   [![](https://files.readme.io/e6b834a0e105324c5b9e4105a5ce7e1f47fa7c00fcf2aee29b6b0e96763150f1-26324098055057.png)](https://files.readme.io/e6b834a0e105324c5b9e4105a5ce7e1f47fa7c00fcf2aee29b6b0e96763150f1-26324098055057.png)
3. **최종 URL**에 웹 랜딩 페이지의 URL을 입력합니다.

   > 🚧 **중요!**
   >
   > 최종 URL은 앱스플라이어 URL(원링크 또는 단일 플랫폼 어트리뷰션 URL)이 될 수 없습니다. 그럴 경우 캠페인이 거부될 수 있습니다. 웹페이지 URL, Google Play 스토어 URL 또는 앱 스토어 URL과 같이 리디렉션이 없는 직접 웹 주소만 사용하세요.


   최종 URL은 사용자를 리디렉션할 최종 웹 위치여야 합니다. 다음 중 하나일 수 있습니다.

   * 사용자가 구글 플레이, 앱 스토어 또는 기타 앱 스토어에서 앱을 다운로드하려면 CTA 버튼을 클릭하라는 메시지가 표시되는 페이지를 가리키는 **랜딩 페이지 URL**. 랜딩 페이지에는 CTA 버튼 URL을 자동으로 생성하는 스마트 스크립트 또는 스마트 배너가 포함됩니다. [스마트 스크립트](#원링크-스마트-스크립트로-랜딩-페이지-만들기)나 [스마트 배너를 사용하여 랜딩 페이지를 만드는 방법](#원링크-스마트-배너로-랜딩-페이지-만들기)을 알아보세요.

     최종 URL에 AF 어트리뷰션 파라미터를 추가하고 Google ValueTrack 파라미터에 매핑할 수 있습니다(예: `af_c_id={campaignid}`). 구글 광고를 클릭하고 랜딩 페이지가 로드되면 스마트 스크립트 또는 스마트 배너가 파라미터를 랜딩 페이지의 발신 URL에 복사할 수 있습니다. 사용 가능한 ValueTrack 파라미터에 대해 알아보려면 [Google 문서](https://support.google.com/google-ads/answer/6305348?sjid=9660882197247124000-EU#zippy=%2Cfinal-url-tracking-template-or-custom-parameter)를 참조하세요.

     예를 들어,

     ```http HTTPS
     https://example.com?product=1234&af_c_id={campaignid}
     ```
   * **스토어 URL**(예: 앱 스토어 또는 구글 플레이)

     > 🚧 **중요!**
     >
     > 스토어 URL을 최종 URL로 사용한다고 가정해 보겠습니다. 앱스플라이어에 어트리뷰션 및 사용자 지정 파라미터 정보를 전송하는 유일한 방법은 AF 파라미터를 삽입하고 추적 템플릿 URL에 매핑하는 것입니다.


     ```http HTTPS
     https://play.google.com/store/apps/details?id=.com.app.id&hl=en&gl=US&referrer={gclid}&gclid={gclid}&campaignid={campaignid}
     ```
   * 사용자가 스토어로 리디렉션되지 않고 앱을 직접 다운로드하도록 하려는 경우 **앱 APK 파일에 대한 직접 다운로드 링크**.

<div id="tip-1" />

<div id="warning-3" />

<div id="set-the-tracking-template-url" />

#### 추적 템플릿 URL 설정

Google Ads는 기본적으로 병렬 추적을 사용하므로 추적 템플릿 URL(이 경우 앱스플라이어 어트리뷰션 링크)이 백그라운드에서 로드되고 클릭이 앱스플라이어에 등록됩니다. 추적 템플릿 URL 사용은 필수 사항이 아닙니다. 특히 스마트 배너나 스마트 스크립트를 사용할 때는 더욱 그렇습니다. 자세한 내용은 본 문서의 ['스마트 스크립트 또는 스마트 배너와 함께 추적 템플릿 URL 사용하기'](#스마트-스크립트-또는-스마트-배너와-함께-추적-템플릿-url-사용)를 참조하십시오.

1. Google Ads에서 **캠페인** > **캠페인** 페이지를 엽니다. 캠페인 행에서 설정 아이콘을 클릭합니다.

   [![](https://files.readme.io/ec6503cfb3ff185448f13897240e0eadd7f10fc3678ffa85b4d52d2393b01ca4-26324098054033.png)](https://files.readme.io/ec6503cfb3ff185448f13897240e0eadd7f10fc3678ffa85b4d52d2393b01ca4-26324098054033.png)
2. **설정** > **추가 설정** > **캠페인 URL 옵션**을 선택합니다.

   [![](https://files.readme.io/4959b4129749ff282ee3818c3b5724ac2ed3b1d033d06f8557329cafa812720f-26324053658641.png)](https://files.readme.io/4959b4129749ff282ee3818c3b5724ac2ed3b1d033d06f8557329cafa812720f-26324053658641.png)
3. **추적 템플릿**에서 다음(BaseURL + 리디렉션 파라미터)을 사용합니다.

   * **기본 URL**: 광고 클릭 대상에 따라 기본 URL을 설정합니다.
     * 광고 클릭 대상이 구글 플레이 또는 앱 스토어인 경우 **단일 플랫폼 어트리뷰션 링크**(아래 예 참조).
     * 광고 클릭 대상이 웹 페이지인 경우 **원링크 어트리뷰션 링크**(아래 예 참조).
   * **PID 파라미터:** 필수 <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#pid">`pid`</Anchor>`=googleads_int` 파라미터를 추가합니다.
   * **사이트 ID 파라미터:** 필수 <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_siteid">`af_siteid`</Anchor> 파라미터를 추가합니다. 어떤 값이든 파라미터에 수동으로 할당할 수 있습니다.
   * **캠페인 이름 파라미터:** 필수 <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#c">c</Anchor> 파라미터를 추가하고 그 값을 수동으로 할당합니다(이 파라미터에 대한 ValueTrack 파라미터는 없습니다).
   * 강제 투명 매개변수: 필수 **`af_force_transparent=true`** 파라미터를 추가합니다. 이 매개변수는 리디렉션 동작의 보안을 강화하도록 설계되어 Google의 요구 사항을 준수합니다. 필수 매개변수를 추가하지 않으면 Google이 광고를 승인하지 않을 수 있습니다.
   * **OneLink 어트리뷰션 링크의 리디렉션 파라미터:** 병렬 추적이 의도한 대로 작동하려면 AF 리디렉션 매개변수를 다음 조합 중 하나로 설정하십시오:
     * 매개변수 `af_android_url`, `af_ios_url`, `af_web_dp`는`{lpurl}` Google ValueTrack 매개변수로 설정해야 합니다. **중요:** 모든 시나리오에서 어트리뷰션 속성 링크 작동을 보장하려면 세 가지가 모두 채워져야 합니다.  
       **또는**
     * `af_r` 매개변수는`{lpurl}` Google ValueTrack 파라미터로 설정해야 합니다.
   * **단일 플랫폼 어트리뷰션 링크용 리디렉션 매개변수:** 병렬 추적이 의도한 대로 작동하려면 `{lpurl}` Google ValueTrack 매개변수로 설정하십시오.

     <div id="note-3" />

     <div id="warning-4" />

     > 🚧 **중요!**
     >
     > Google 요구 사항을 준수하려면 `{lpurl}` 값이 유효한 리디렉션 URL인지 확인하십시오:
     >
     > * HTTPS 프로토콜을 사용합니다.
     > * 인코딩되어야 합니다.
     > * URL 도메인이 <Anchor target="_blank" href="/marketers/ko/docs/set-up-your-domain-redirect-allowlist">리디렉션 허용 목록에</Anchor> 포함되어야 합니다.

   * **Google ValueTrack 파라미터에 매핑된 앱스플라이어 어트리뷰션 파라미터**(예: <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_c_id">`af_c_id`</Anchor>`={campaignid}`) 사용 가능한 ValueTrack 파라미터에 대해 알아보려면 [Google 문서](https://support.google.com/google-ads/answer/6305348?sjid=9660882197247124000-EU#zippy=%2Cfinal-url-tracking-template-or-custom-parameter)를 참조하세요.
   * <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_dp">`af_dp`</Anchor> 파라미터를 포함하지 마세요.
   * 리디렉션 매개변수 `{lpurl}`의 값을 변경하는 매개변수를 포함하지 마십시오. 여기에는 `af_base_params_forward`과 `af_param_forwarding`가 포함됩니다.

   > 📘 **참고**
   >
   > 추적 템플릿 URL에 대한 추가 제한 사항은 이 문서의 [특성 및 제한 사항](#특징-및-제약-사항) 섹션을 참조하십시오.


<div id="google-tracking-template-url-examples" />

#### Google 추적 템플릿 URL 예시

구글 추적 템플릿 URL의 **원링크** 예:

```http
https://subdomain.onelink.me/aAB1?pid=googleads_int&af_force_transparent=true&af_android_url={lpurl}&af_ios_url={lpurl}&af_web_dp={lpurl}&c=summer_sale24&af_siteid=123456&af_c_id={campaignid}&af_adset=sum24A&af_adset_id={adgroupid}&af_sub1={gclid}&af_sub2={gbraid}
```

구글 추적 템플릿 URL의 **단일 플랫폼 링크** 예:

```http
https://app.appsflyer.com/id1510557250?pid=googleads_int&af_force_transparent=true&c=examplecamp&af_siteid=123456&af_adset=exampleadset&af_adset_id={adgroupid}&af_c_id={campaignid}&af_ad_id={creative}&af_click_lookback=7d&af_r={lpurl}
```

<div id="using-the-tracking-template-url-with-smart-script-or-smart-banners" />

#### 스마트 스크립트 또는 스마트 배너와 함께 추적 템플릿 URL 사용

광고가 스마트 스크립트 또는 스마트 배너를 사용하는 랜딩 페이지로 리디렉션될 경우, 추적 템플릿 URL에 앱스플라이어 어트리뷰션 링크로 입력할 필요가 없습니다. 이는 사용자가 랜딩 페이지 CTA 버튼을 클릭할 때 이러한 도구가 앱스플라이어에 등록되는 어트리뷰션 링크를 자동으로 생성하기 때문입니다. 그러나 추적 템플릿 URL 필드를 비워 두는 것에 대해 고려해야 할 사항이 있습니다.

* 추적 템플릿 URL에 어트리뷰션 링크를 **채우지 않을** 경우 사용자가 광고는 클릭하지만 랜딩 페이지 CTA 버튼을 클릭하지 않을 때 발생하는 설치를 빠뜨릴 위험이 있습니다. 사용자가 룩백 윈도우 내에 앱 스토어로 직접 이동하여 앱을 다운로드할 경우, 후속 설치는 어트리뷰션 가능한 것으로 간주되지 않습니다.
* 추적 템플릿 URL에 어트리뷰션 링크를 **채우고** 사용자가 광고를 클릭한 후 랜딩 페이지의 CTA 버튼을 클릭하면, 한 번이 아닌 두 번의 클릭으로 기록되어 전환율 데이터에 영향을 미칠 수 있습니다.

</Accordion>

<div id="note-4" />

<div id="create-a-landing-page-with-onelink-smart-script" />

## 원링크 스마트 스크립트로 랜딩 페이지 만들기

**사용자 여정:** 사용자가 구글 광고를 클릭하면 모바일 웹사이트로 연결됩니다. 사용자가 앱을 다운로드하게끔 하는 CTA 버튼이 있는 페이지로 연결됩니다. 버튼을 클릭하면 사용자가 스토어로 리디렉션됩니다.

<div id="endtoend-data-flow" />

<Accordion title="엔드투엔드 데이터 흐름">

W2A 스마트 스크립트 사용 사례는 다음 단계로 구성됩니다.

[![](https://files.readme.io/95b5a593eba3bc0bafb629bb8a27d83c077d5815a79897c004f8f085fa8e953b-25646834953105.png)](https://files.readme.io/95b5a593eba3bc0bafb629bb8a27d83c077d5815a79897c004f8f085fa8e953b-25646834953105.png)

1. 사용자가 Google 광고를 클릭하면 Google은 최종 URL에 다음을 자동으로 추가합니다:
   * Android 기기용 및 iOS 기기에서 동의한 사용자를 위한 `gclid` 매개변수.
   * iOS 기기 비동의 사용자를 위한 `gbraid`, `wbraid`.
   * 광고 Google 추적 템플릿 URL에 설정된 모든 쿼리 매개변수 (리디렉션 매개변수 제외).
2. 최종 URL은 사용자를 랜딩 페이지로 리디렉션합니다.
3. 동시에, 자동으로 추가되는 `gclid`, `gbraid`, `wbraid`, `pid=googleads_int` 파라미터를 포함하는 광고 Google Tracking 템플릿 URL이 백그라운드에서 실행되며, 클릭이 앱스플라이어에 등록됩니다.
4. 랜딩 페이지가 로드되면 스마트 스크립트는 앱스플라이어에 노출 이벤트를 발생시키며, 여기에는 수신 URL 파라미터가 포함됩니다. 이 노출은 랜딩 페이지에 대한 뷰-쓰루 어트리뷰션을 가능하게 합니다. 노출 및 뷰-쓰루 어트리뷰션에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">여기</Anchor>를 참조하세요.
5. 스마트 스크립트는 `gclid`, `gbraid`, `wbraid` 파라미터를 포함한 수신 URL 파라미터를 기반으로, 해당 페이지의 CTA 버튼에 대한 발신 URL을 생성합니다. 버튼은 다음으로 이어질 수 있습니다.
   * 구글 플레이 및 앱 스토어(원링크 어트리뷰션 링크 사용).
   * 여러 플랫폼 스토어(예: CTV, Epic, Steam). 이 사용 사례에서 스마트 스크립트트는 각 플랫폼에 대해 발신 단일 플랫폼 어트리뷰션 링크를 생성하여 지정된 플랫폼의 스토어로 연결됩니다.
   * 사용자의 기기에 APK 파일을 다운로드합니다.
6. 사용자가 CTA 버튼을 클릭하면 클릭이 실행되고 앱스플라이어에 등록됩니다.
7. 사용자가 스토어로 리디렉션되고 앱을 다운로드합니다.
8. 사용자가 앱을 열면 인스톨 이벤트가 앱스플라이어에 등록됩니다.
9. 앱스플라이어는 확률적 모델링을 기반으로 설치를 귀속하거나, [설치 리퍼러](https://www.appsflyer.com/glossary/install-referrer/)가 존재할 경우 결정론적으로 귀속합니다.
10. `gclid` 또는 `gbraid`, `wbraid` 및 추가적인 이벤트 파라미터를 포함하는 포스트백은 OCI API를 통해 생성되고 Google Ads로 전송됩니다. Google Ads는 특정 클릭을 식별하기 위해 `gclid` 또는 `gbraid` 및 `wbraid` 매개변수를 사용하며, 다른 매개변수들은 캠페인 최적화에 도움을 줍니다.

</Accordion>

<div id="set-up-a-smart-script-landing-page" />

<Accordion title="스마트 스크립트 랜딩 페이지 설정">

스마트 스크립트를 설정하기 위해 구글 웹 캠페인은 다음을 수행합니다.

1. 스마트 스크립트를 만듭니다.

   > 📘 **참고**
   >
   > 아래의 지침은 스마트 스크립트로 구글 웹 캠페인을 설정하는 데 필요한 단계에 초점을 맞춥니다. 스마트 스크립트 캠페인을 설정하는 방법에 대한 포괄적인 가이드는 <Anchor target="_blank" href="/marketers/ko/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">원링크 스마트 스크립트 V2 설정</Anchor> 문서의 <Anchor target="_blank" href="/marketers/ko/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">원링크 스마트 스크립트를 만드는 방법</Anchor> <Anchor target="_blank" href="/marketers/ko/docs/set-up-smart-script-to-convert-web-visitors#how-to-create-a-onelink-smart-script">섹션을 참조할 수 있습니다.</Anchor>

2. 모든 관련 URL 파라미터(나중에 스마트 스크립트에 의해 캡처됨)가 수신 URL에 추가되었는지 확인합니다. 수신 URL에 추가된 파라미터를 검토하려면 Google Ads를 열고 최종 URL 또는 추적 템플릿 URL 생성의 일부로 설정된 URL 파라미터를 확인합니다. [캠페인 URL 설정](#c-set-the-campaign-urls)을 참조하세요.
3. 캠페인에 필요한 인바운드 URL 매개변수를 사용자가 CTA 버튼을 클릭할 때 AppsFlyer로 전송될 아웃바운드 URL 매개변수에 매핑하십시오:
   * **PID**: 스마트 스크립트가 수신 URL에서 `pid=googleads_int`parameter 값을 가져와 발신 URL의 해당 매개변수에 매핑하는지 확인하세요.
   * **GCLID**: `gclid`매개변수는 Google Ads에 인앱 이벤트 포스트백을 성공적으로 전송하는 데 필수적입니다. 발신 URL GCLID 매개변수 매핑은 스마트 스크립트 버전에 따라 다릅니다:
     * 버전 2.8.1 이상: 이 `gclid` 매개 변수는 수신 URL에 있는 경우 발신 URL 매개 변수로 자동으로 전달되므로 수동 매핑이 필요하지 않습니다.
     * 버전 2.8.0 이하: `gclid` 매개변수는 **스마트 스크립트** 페이지의 **URL 매개변수 매핑 섹션**에서 수동으로 매핑해야 합니다:
       1. **Mapping for**에서 **커스텀 파라미터**를 선택하세요.
       2. **발신 URL 매개변수** 및 **수신 URL 매개변수**에 **gclid**를 입력합니다.
   * GBRAID 및 WBRAID: iOS 기기 사용자가 동의하지 않은 경우, Google Ads로 인앱 이벤트 포스트백을 성공적으로 전송하기 위해서는 `gbraid`, `wbraid` 파라미터가 필수입니다. 발신 URL에서 `gbraid`, `wbraid` 매개변수의 매핑은 Smart Script 버전에 따라 다릅니다:

     * 버전 2.9.0 이상: `wbraid`, `gbraid` 파라미터는 수신 URL에 존재하는 경우, 발신 URL 파라미터로 자동 전달되어 수동 매핑이 필요하지 않습니다.
     * 버전 2.8.1 이하: `wbraid`, `gbraid`매개변수는 **Smart Script** 페이지의 **URL 매개변수 매핑 섹션**에서 수동으로 매핑해야 합니다.
       1. **Mapping for**에서 **커스텀 파라미터**를 선택하세요.
       2. **발신 URL 매개변수** 및 **수신 URL 매개변수**에 **wbraid**를 입력합니다.
       3. 위 단계를 반복하여 매개변수에 대해 수행합니다.

     <div id="note-5" />

     > 📘 **참고**
     >
     > 앱스플라이어 로데이터 보고서에 표시하려면 수신 `gclid`, `gbraid`, `wbraid` 매개변수가 각각 전용 발신 `af_sub[1-5]` 매개변수에 매핑되어야 합니다 (발신 URL `gclid` , `gbraid`, `wbraid`파라미터 외 추가로).


</Accordion>

<div id="set-up-a-smart-script-crossplatform-landing-page" />

<Accordion title="스마트 스크립트 크로스 플랫폼 랜딩 페이지 설정">

크로스 플랫폼이 아닌 랜딩 페이지의 경우, 마케터는 일반적으로 앱스플라이어 스마트 스크립트 페이지를 통해 스마트 스크립트를 자동 생성할 책임이 있습니다. 그러나 크로스 플랫폼 랜딩 페이지의 경우 개발자는 마케터가 보낸 파라미터를 기반으로 스크립트를 만듭니다.

스마트 스크립트를 설정하기 위해 구글 웹 캠페인은 다음을 수행합니다.

1. 크로스 플랫폼 어트리뷰션을 위해 원링크 템플릿을 활성화합니다. <Anchor target="_blank" href="/marketers/ko/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-1-create-or-edit-a%C2%A0onelink-template%C2%A0for-crossplatform-attribution">여기</Anchor>를 확인해 보세요.
2. 모든 관련 URL 파라미터가 수신 URL에 추가되었는지 확인합니다. 수신 URL에 추가된 파라미터를 검토하려면 Google Ads를 열고 최종 URL 또는 추적 템플릿 URL 생성의 일부로 설정된 URL 파라미터를 확인합니다. [캠페인 URL 설정](#c-set-the-campaign-urls)을 참조하세요.
3. 각 수신 파라미터에 대해 매핑할 대상이 되는 발신 파라미터를 결정합니다. 예를 들어, 수신 URL의 `af_site_id`는 발신 URL의 `af_site_id`에 매핑됩니다.
4. 비워 둘 수 없는 필수 발신 파라미터의 기본값을 결정합니다.
5. 개발자에게 다음 정보를 보냅니다.
   * 수신-발신 파라미터 매핑입니다. 개발자는 수신-발신 파라미터 매핑을 기반으로 발신 직접 URL을 생성하는 스크립트를 만듭니다.
   * 파라미터의 기본값입니다. 스크립트는 해당하는 수신 URL 파라미터 값이 없을 때마다 발신 URL 파라미터를 기본값으로 채웁니다.
   * 원링크 어트리뷰션 링크를 사용하는 경우, 개발자에게 도메인과 템플릿 ID를 전송하세요. 개발자는 이를 사용하여 발신 원링크 URL을 생성합니다. 예: `your_brand.onelink.me/A1b2` 또는 브랜드 도메인의 예: `click.yourbrand.com/A1b2`
   * 개발자에게 다음 Dev Hub 링크를 보냅니다.
     * 모바일 플랫폼이 아닌 곳으로 직접 나가는 URL을 만드는 방법에 대한 [지침과 코드 예시](https://dev.appsflyer.com/hc/docs/create-direct-click-url)입니다.
     * 크로스 플랫폼 랜딩 페이지를 만드는 방법에 대한 [데모와 지침](https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/)입니다.
   * 수신 URL에 있는 경우 `gclid` 파라미터는 발신 URL 파라미터로 자동으로 전달되므로 수동 매핑이 필요하지 않습니다(스마트 스크립트 버전 2.8.1부터). 개발자에겐 여전히 `gclid`를 `af_sub` 파라미터 중 하나에 매핑하여 로데이터 리포트에서 사용할 수 있는 옵션이 있습니다. Google Ads GCLID를 참조하세요.

</Accordion>

<div id="view-in-raw-data-and-api-reports" />

<div id="view-in-the-dashboard" />

<div id="view-web-to-app-attribution-data" />

<div id="note-6" />

<div id="create-a-landing-page-with-onelink-smart-banners" />

## 원링크 스마트 배너로 랜딩 페이지 만들기

**사용자 여정:** 사용자가 구글 광고를 클릭하면 모바일 웹사이트로 연결됩니다. 페이지에 도착하면 앱 스토어에서 앱을 다운로드할 수 있는 CTA와 함께 스마트 배너가 표시됩니다.

<div id="endtoend-data-flow::3c418973" />

<Accordion title="엔드투엔드 데이터 흐름">

1. 사용자가 Google 광고를 클릭하면 Google은 최종 URL에 다음을 자동으로 추가합니다:
   * Android 기기용 및 iOS 기기에서 동의한 사용자를 위한 `gclid` 매개변수.
   * iOS 기기 비동의 사용자를 위한 `gbraid`, `wbraid`.
   * 광고 Google 추적 템플릿 URL에 설정된 모든 쿼리 매개변수 (리디렉션 매개변수 제외).
2. 동시에 광고 뒤에 있는 Google 추적 템플릿 URL(자동 추가된 `gclid`매개변수와 `pid=googleads_int`매개변수를 포함)이 백그라운드에서 실행되며, 클릭이 AppsFlyer에 등록됩니다.
3. 랜딩 페이지가 로드되면 스마트 배너는 앱스플라이어에 <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">노출</Anchor> 이벤트를 발생시키며, 여기에는 수신 URL 파라미터가 포함됩니다. 이 노출은 랜딩 페이지에 대한 뷰-쓰루 어트리뷰션을 가능하게 합니다. 노출 및 뷰-쓰루 어트리뷰션에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">여기</Anchor>를 참조하세요.
4. 스마트 배너는 `gclid` 파라미터를 포함한 수신 파라미터를 기반으로, 해당 배너의 CTA 버튼에 대한 발신 URL을 생성합니다. 스마트 배너는 원링크 기반 링크만 생성할 수 있습니다.
5. 사용자가 스마트 배너 CTA 버튼을 클릭하면 클릭이 실행되고 앱스플라이어에 등록됩니다.
6. 사용자가 스토어로 리디렉션되고 앱을 다운로드합니다.
7. 사용자가 앱을 열면 인스톨 이벤트가 앱스플라이어에 등록됩니다.
8. 앱스플라이어는 [설치 참조자](https://www.appsflyer.com/glossary/install-referrer/)가 있는 경우 확률적 모델링을 기반으로 설치를 귀속시키거나 결정적으로 귀속시킵니다.
9. `gclid` 및 다른 이벤트 파라미터가 포함된 포스트백이 생성되어 OCI API를 통해 Google Ads로 전송됩니다. 구글은 `gclid` 파라미터를 사용하여 특정 클릭을 식별하고, 다른 파라미터는 캠페인을 최적화하는 데 도움이 됩니다.

</Accordion>

<div id="set-up-a-smart-banners-landing-page" />

<Accordion title="스마트 배너 랜딩 페이지 설정">

> 📘 **참고**
>
> 아래의 지침은 스마트 배너로 구글 웹 캠페인을 설정하는 데 필요한 단계에 초점을 맞춥니다. 스마트 배너 캠페인을 설정하는 방법에 대한 포괄적인 가이드는 <Anchor target="_blank" href="/marketers/ko/docs/smart-banners-mobile-web-to-app-for-marketers">스마트 배너 - 모바일 웹-앱(마케터용)</Anchor> 문서의 <Anchor target="_blank" href="/marketers/ko/docs/smart-banners-mobile-web-to-app-for-marketers#설정">설정 섹션</Anchor>을 참조하세요.

스마트 배너 구글 웹 캠페인을 설정하려면 다음을 수행하세요.

1. 스마트 배너를 만드세요. 지침은 <Anchor target="_blank" href="/marketers/ko/docs/smart-banners-mobile-web-to-app-for-marketers">스마트 배너 - 모바일 웹-앱(마케터용)</Anchor> 문서의 <Anchor target="_blank" href="/marketers/ko/docs/smart-banners-mobile-web-to-app-for-marketers#설정">설정 섹션</Anchor>을 참조하세요.
2. 수신 URL에 다음이 포함되어 있는지 확인하십시오:
   * `pid=googleads_int`은 수신 URL에서 사용할 수 있습니다.
   * `gclid` 파라미터는 수신 URL에서 사용할 수 있습니다. Smart Banners는 `gclid` 매개변수를 발신 배너 URL로 자동 전달합니다. `gclid` 매개변수는 Google OCI에 인앱 포스트백을 성공적으로 전달하는 데 필요합니다.
   * 동의하지 않은 iOS 기기 사용자에게 포스트백을 전송할 때, 수신 URL에서 `gbraid`, `wbraid` 파라미터를 사용할 수 있습니다. Smart Banners는 이러한 매개변수를 발신 배너 URL로 자동 전달합니다. 이 경우, `gbraid` 매개변수와 `wbraid`매개변수는 `gclid`매개변수가 없는 상황에서 Google이 집계된 이벤트 데이터를 얻을 수 있도록 합니다.
   * 모든 관련 URL 파라미터가 수신 URL에 추가되었는지 확인합니다. 수신 URL에 추가된 파라미터를 검토하려면 Google Ads를 열고 최종 URL 또는 추적 템플릿 URL 생성의 일부로 설정된 URL 파라미터를 확인합니다. [캠페인 URL 설정](#c-set-the-campaign-urls)을 참조하세요.
3. (선택 사항) the **동적 어트리뷰션 매개변수** 섹션의 배너 그룹 설정 페이지에서 첫 번째 체크박스를 선택합니다. 이 설정은 수신 링크의 모든 매개변수가 Smart Banner의 링크에 추가되도록 보장합니다.

</Accordion>

<div id="troubleshooting-in-app-events-postbacks" />

## 인앱 이벤트 포스트백 문제 해결

인앱 이벤트 데이터가 Google Ads 또는 Google Analytics에 표시되지 않거나 누락된 토큰 오류가 발생하는 경우, 지원팀에 연락하기 전에 다음 설정이 올바른지 확인하십시오:

<div id="access-token-permissions" />

<Accordion title="토큰 권한 설정">

Google Ads에서 액세스 토큰이 오프라인 전환을 업로드하는 데 필요한 권한을 가지고 있는지 확인하십시오:

1. Google 개발자 콘솔로 이동하십시오.
2. `uploadClickConversions`에 다음 OAuth 범위가 포함되어 있는지 확인하십시오: [`https://www.googleapis.com/auth/adwords`](https://www.googleapis.com/auth/adwords)
3. 앱스플라이어의 연동 탭에서 **Google로 로그인** 클릭.
4. MCC 계정의 관리자 계정을 선택하십시오.
5. **허용**을 클릭합니다.

</Accordion>

<div id="mcc-customer-id" />

<Accordion title="MCC 고객 ID">

앱을 위한 캠페인을 실행하는 여러 Google Ads 계정이 있는 경우, MCC 계정의 고객 ID를 사용해야 합니다. [MCC 계정 구성에 대한 Google 지침](https://support.google.com/google-ads/answer/3061730?sjid=4528491462900554442-NC)을 참조하세요.

</Accordion>

<div id="conversion-action-id" />

<Accordion title="전환 작업 ID">

포스트백 인앱 이벤트가 올바른 전환 작업 ID에 매핑되어 있는지 확인하십시오. Google Ads에서 전환 작업 ID를 찾으려면 [여기](#to-find-the-conversion-action-id-in-google-ads)를 참조하세요.

</Accordion>

<div id="h_01JK60PD859H8TG4BCD7BXQ63K" />

<Accordion title="GCLID, GBRAID, WBRAID 매개변수">

스마트 스크립트 또는 스마트 배너의 외부 URL에는 Google OCI로 정상적으로 포스트백되어 Google Ads에 등록되도록 하기 위해 `gclid`, `wbraid`, 또는 `gbraid` 중 하나가 반드시 포함되어야 합니다.

</Accordion>

<div id="agency-managed-campaigns" />

<div id="traits-and-limitations" />

## 특징 및 제약 사항

| 특징 | 비고 |
| --- | --- |
| <span id="dashboard"></span>대시보드 | iOS의 Google 웹 기반 캠페인에 대한 귀속 데이터는 앱스플라이어 Classic 대시보드에서 조회 및 분석됩니다. 대부분의 경우, SKAN 대시보드는 웹-앱 캠페인과 관련이 없습니다. |
| <span id="reengagement-attribution"></span>리인게이지먼트 어트리뷰션 | 사용자는 동일한 캠페인에 의해 유도되더라도 `googleads_int`에 귀속된 설치 및 `googleadwords_int`에 귀속된 재참여를 관찰할 수 있습니다. 이 행동은 예상된 것이며 기술적 문제로 이어지지 않습니다.   <br />  <br />일반적으로 `googleadwords_int` SRN 연동이 활성화되어 있을 때 발생하여 동일한 Google Ads 웹-to-앱 캠페인에서 재참여를 주장할 수 있습니다. |
| <span id="cost-data"></span>비용 데이터 | Google Ads 웹 네트워크의 비용 데이터 (`pid=googleads_int`)는 자동으로 검색되지 않습니다. 대신, <Anchor target="_blank" href="/marketers/ko/docs/import-cost-data#절차">두 가지 지원되는 방법 중 하나: 이메일 기반 파일 업로드 또는 앱스플라이어 UI를 통한 수동 업로드</Anchor>를 사용하여 수동으로 가져와야 합니다. 이것은 ROI360 구독자를 포함한 모든 사용자에게 적용됩니다. |
| <span id="tracking-template-urls"></span>추적 템플릿 URL | 추적 템플릿 URL은 아래의 제한 사항을 준수해야 합니다. 이를 준수하지 않으면 링크가 끊어집니다.<ul><li>링크에는 중복 매개변수가 포함되어서는 안 됩니다.</li><li>링크에는 다음과 같은 유효하지 않은 매개변수가 포함되어서는 안 됩니다:<ul><li>값이 없는 매개변수, 손상된 매개변수 또는 구문 분석할 수 없는 매개변수. 여기에는 `key=` 또는 `key`와 같은 값이 없는 매개변수가 포함됩니다. 예: `pid=googleads_int&key&c=campaign` or `pid=googleads_int&key=&c=campaign`</li><li>ValueTrack 매개변수 중 하나에 누락된 값이 있는 경우, 예를 들어, `{placement}`. 누락된 값을 방지하려면 Google Ads에서 추적 템플릿을 올바르게 정의하여 Google Ads가 해당 값을 채우도록 하십시오.</li></ul></li><li>Google Ads 캠페인 설정에서 **캠페인 URL 옵션** 아래의 매개변수에 값을 입력한 경우, 해당 값은 추적 템플릿의 매개변수 값과 반드시 일치해야 합니다. 일치하지 않는 경우, 정책 업데이트 준수를 위해 추적 템플릿에서 해당 항목을 제거해 주십시오.</li></ul> |
| <span id="unexpected-srn-attribution"></span>예상치 못한 SRN 어트리뷰션 | 경우에 따라 Google Ads 웹 기반 캠페인에서의 설치는 웹 기반 캠페인에서도 SRN(자체 보고 네트워크)을 통해 `googleadwords_int`에 귀속될 수 있습니다. 이것은 Google이 설치를 주장할 때 발생합니다. Google이 해당 주장을 할 때, 앱스플라이어는 인스톨에 따라 어트리뷰션합니다. 이러한 결과는 예상되는 것이며, Google이 웹 캠페인 설치 기여도 분석 지원을 확대함에 따라 더욱 흔해질 수 있습니다. |
| <span id="plan-availability"></span>플랜 가용성 | `googleads_int` 연동은 Growth 및 Enterprise 플랜에서만 사용할 수 있습니다. 제로 및 웰컴 플랜의 고객은 이 연동을 사용할 수 없습니다. |

<div data-zendesk-anchors="h_01JP7SMGEPTQGHRYYCBWECH46X=%EC%B0%B8%EA%B3%A0 overview=%EA%B0%9C%EC%9A%94 h_01J1MPPMW38A7EG2W8TJ8F6YQ3=%EA%B0%9C%EC%9A%94 prerequisite=%EC%A0%84%EC%A0%9C-%EC%A1%B0%EA%B1%B4 h_01J1MPPMW3GWQKZVG2HAQA9H46=%EC%A0%84%EC%A0%9C-%EC%A1%B0%EA%B1%B4 how-to-create-a-google-ad-web-campaign=google-ads-%EC%9B%B9-%EC%BA%A0%ED%8E%98%EC%9D%B8%EC%9D%84-%EB%A7%8C%EB%93%9C%EB%8A%94-%EB%B0%A9%EB%B2%95 h_01J1MPPMW3ZYSPQHT4D2YAJ038=google-ads-%EC%9B%B9-%EC%BA%A0%ED%8E%98%EC%9D%B8%EC%9D%84-%EB%A7%8C%EB%93%9C%EB%8A%94-%EB%B0%A9%EB%B2%95 create-a-google-ad-for-web-integration-in-appsflyer=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%97%90%EC%84%9C-google-ads-%EC%97%B0%EB%8F%99-%EC%83%9D%EC%84%B1 h_01J1MPPMW3WTD63M686BHZNKDX=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%97%90%EC%84%9C-google-ads-%EC%97%B0%EB%8F%99-%EC%83%9D%EC%84%B1 h_01J1MPPMW3G9B1G116B18CRYJB=a-activate-the-google-ads-for-web-campaigns-integration h_01JK8XJJWQK5MEJF7GTC5C1707=%EC%B0%B8%EA%B3%A0-1 h_01J1MPPMW3CF8RDRGB4WTQCTG8=%ED%8C%81 h_01ZXVWB0GZKWB53KTBWJ51RMBM=d-enable-view-through-attribution-for-meta-web h_01J1MPPMW34GG0EPDWYXA7383C=b-set-inapp-event-postbacks h_01J1MPPMW47SPEX51DHC4F6HQC=c-configure-the-onelink-template h_01J1MPPMW4X400GFKR871FV1M5=%EC%B0%B8%EA%B3%A0-2 create-a-web-campaign-in-google-ads=google-ads%EC%97%90%EC%84%9C-%EC%9B%B9-%EC%BA%A0%ED%8E%98%EC%9D%B8-%EB%A7%8C%EB%93%A4%EA%B8%B0 h_01J1MPPMW4AQNQEKBN1VSPM4X7=google-ads%EC%97%90%EC%84%9C-%EC%9B%B9-%EC%BA%A0%ED%8E%98%EC%9D%B8-%EB%A7%8C%EB%93%A4%EA%B8%B0 h_01J1MPPMW4HPJR91DREYNQKJJB=a-set-the-campaign-type-objective-and-goals h_01J1MPPMW4KMSXAR903P534X65=b-create-custom-conversion-actions h_01K456EGHVQTV0W51EE80ZR36X=%EC%A4%91%EC%9A%94 h_01J1MPPMW44NGXN55SFD16Z4HE=c-set-the-campaign-urls set-the-final-url=%EC%B5%9C%EC%A2%85-url%EC%9D%84-%EC%84%A4%EC%A0%95%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95%EC%9D%80-%EB%8B%A4%EC%9D%8C%EA%B3%BC-%EA%B0%99%EC%8A%B5%EB%8B%88%EB%8B%A4 h_01J1MPPMW48F7X2NYEA735BG51=%EC%B5%9C%EC%A2%85-url%EC%9D%84-%EC%84%A4%EC%A0%95%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95%EC%9D%80-%EB%8B%A4%EC%9D%8C%EA%B3%BC-%EA%B0%99%EC%8A%B5%EB%8B%88%EB%8B%A4 h_01J1MPPMW4KCR8P0GW3WDC55YQ=%EC%A4%91%EC%9A%94-1 h_01J1MPPMW442TTX15YKK07TC91=%EC%A4%91%EC%9A%94-2 set-the-tracking-template-url=%EC%B6%94%EC%A0%81-%ED%85%9C%ED%94%8C%EB%A6%BF-url-%EC%84%A4%EC%A0%95 h_01J1MPPMW44596CZVKF9MGDTMP=%EC%B6%94%EC%A0%81-%ED%85%9C%ED%94%8C%EB%A6%BF-url-%EC%84%A4%EC%A0%95 01JCJGVWN4ZMXFERA7Q3Q1M4KR=%EC%A4%91%EC%9A%94-3 h_01JQ958K4JNMY2DSRDKASPYZJ4=%EC%B0%B8%EA%B3%A0-3 google-tracking-template-url-examples=google-%EC%B6%94%EC%A0%81-%ED%85%9C%ED%94%8C%EB%A6%BF-url-%EC%98%88%EC%8B%9C 01JCZQR9RJAZF4SJVVKYZNJNPY=google-%EC%B6%94%EC%A0%81-%ED%85%9C%ED%94%8C%EB%A6%BF-url-%EC%98%88%EC%8B%9C using-the-tracking-template-url-with-smart-script-or-smart-banners=%EC%8A%A4%EB%A7%88%ED%8A%B8-%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8-%EB%98%90%EB%8A%94-%EC%8A%A4%EB%A7%88%ED%8A%B8-%EB%B0%B0%EB%84%88%EC%99%80-%ED%95%A8%EA%BB%98-%EC%B6%94%EC%A0%81-%ED%85%9C%ED%94%8C%EB%A6%BF-url-%EC%82%AC%EC%9A%A9 01JCZQR9RMAW9YP3T3679JAX45=%EC%8A%A4%EB%A7%88%ED%8A%B8-%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8-%EB%98%90%EB%8A%94-%EC%8A%A4%EB%A7%88%ED%8A%B8-%EB%B0%B0%EB%84%88%EC%99%80-%ED%95%A8%EA%BB%98-%EC%B6%94%EC%A0%81-%ED%85%9C%ED%94%8C%EB%A6%BF-url-%EC%82%AC%EC%9A%A9 create-a-landing-page-with-onelink-smart-script=%EC%9B%90%EB%A7%81%ED%81%AC-%EC%8A%A4%EB%A7%88%ED%8A%B8-%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8%EB%A1%9C-%EB%9E%9C%EB%94%A9-%ED%8E%98%EC%9D%B4%EC%A7%80-%EB%A7%8C%EB%93%A4%EA%B8%B0 h_01J1MPPMW4P7Q18JN7JS9ZXR23=%EC%9B%90%EB%A7%81%ED%81%AC-%EC%8A%A4%EB%A7%88%ED%8A%B8-%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8%EB%A1%9C-%EB%9E%9C%EB%94%A9-%ED%8E%98%EC%9D%B4%EC%A7%80-%EB%A7%8C%EB%93%A4%EA%B8%B0 h_01J1MPPMW40PZCXWBYKV8VVB62=endtoend-data-flow h_01J1MPPMW4R1Q7PPZAF566Z5A3=set-up-a-smart-script-landing-page h_01J1MPPMW4WF7PRJ1WSDEH1172=%EC%B0%B8%EA%B3%A0-4 h_01HZKNS17K2W4XJB0BH87RZYTJ=%EC%B0%B8%EA%B3%A0-5 h_01J1MPPMW4X9PRB1JECYB154SH=set-up-a-smart-script-crossplatform-landing-page create-a-landing-page-with-onelink-smart-banners=%EC%9B%90%EB%A7%81%ED%81%AC-%EC%8A%A4%EB%A7%88%ED%8A%B8-%EB%B0%B0%EB%84%88%EB%A1%9C-%EB%9E%9C%EB%94%A9-%ED%8E%98%EC%9D%B4%EC%A7%80-%EB%A7%8C%EB%93%A4%EA%B8%B0 h_01J1MPPMW4CW8JMJK26PTEY74W=%EC%9B%90%EB%A7%81%ED%81%AC-%EC%8A%A4%EB%A7%88%ED%8A%B8-%EB%B0%B0%EB%84%88%EB%A1%9C-%EB%9E%9C%EB%94%A9-%ED%8E%98%EC%9D%B4%EC%A7%80-%EB%A7%8C%EB%93%A4%EA%B8%B0 h_01J1MPPMW5W8XBVT9X2YJBWSXX=endtoend-data-flow::3c418973 h_01J1MPPMW5E82SW0ZEZCDXC98W=set-up-a-smart-banners-landing-page h_01J1MPPMW5N8YV40E7XPEKT8EJ=%EC%B0%B8%EA%B3%A0-6 troubleshooting-inapp-events-postbacks=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0 h_01J52V5G2DSF9PW9Z5GJHAD376=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0 h_01J52V5G2DJZB1R1TK0GR49J0R=access-token-permissions h_01J52V5G2EJ7GDP7ZTCZGWDW4C=mcc-customer-id h_01J52V5G2E2EAY611JKRSPWZG4=conversion-action-id traits-and-limitations=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD 01JDW5XHD92VFJ93671YP4JMFQ=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD" />
