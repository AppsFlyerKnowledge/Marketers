---
title: PC 및 콘솔 앱용 메타 웹 통합 설정
metadata:
  keywords:
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2023-09-20T09:54:52Z'
  edited_at: '2026-10-14T10:33:35Z'
  id: 18704273772689
  locale: ko
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/ko/articles/18704273772689
---
> **한눈에 보기:** PC 및 콘솔용 Meta Web 앱을 앱스플라이어와 연동하는 방법과 Meta Web에서 캠페인을 설정하는 방법을 알아보세요.

> 🚧 **중요!**
>
> 이 연동 기능은 Steam, Epic, Native PC와 같은 PC 및 콘솔 앱에서만 사용할 수 있습니다. 모바일 앱의 경우 <Anchor target="_blank" href="/marketers/ko/docs/meta-ads-integration-setup">메타 광고 연동 설정</Anchor> 페이지를 참조하세요.

## 개요

이 글에는 앱스플라이어에서 PC 및 콘솔 앱용 메타 웹을 설정하고 사용하는 방법에 대한 정보와 단계를 제공합니다. 여기에는 다음이 포함됩니다.

* [앱스플라이어에서 파트너 연동 활성화하기](#앱스플라이어-파트너-활성화).
* [앱스플라이어에서 메타 웹 설정하기](#앱스플라이어에서-메타-웹-설정하기).
* [PC 및 콘솔 앱용 메타에서 캠페인 설정하기](/docs/meta-ads-web-integration-setup-for-pc-and-console-apps#pc-및-콘솔-앱용-메타-웹에서-캠페인-설정하기).

### 전제 조건

Meta 웹 연동을 활성화하기 전에 [Meta Business Manager에 비즈니스 계정이](https://www.facebook.com/business/help/1710077379203657?id=180505742745347) 있는지 확인하십시오.

## 앱스플라이어 파트너 활성화

**파트너 연동 활성화 방법:**

1. 앱스플라이어의 사이드 메뉴에서**협업**>**파트너 마켓플레이스**로 이동합니다.
2. **메타 웹**을 검색하여 선택합니다.
3. **연동 설정**을 클릭하세요. **활성화된 연동** 설정 페이지로 이동합니다.
4. **연동** 탭에서 **파트너 활성화**를 켭니다.  
   **참고: <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">파트너와 작업하는 동안에는 토글이 켜져 있어야 합니다(</Anchor><Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">활성화됨</Anchor>).**
5. 다음 섹션에 설명된 대로 관련 탭을 사용하여 구성을 완료합니다.

## 앱스플라이어에서 메타 웹 설정하기

이 단계에서는 메타 웹에 대한 포스트백을 설정할 수 있습니다. 메타 웹(metaweb\_int) 연동은 광고주가 PC 및 콘솔 앱의 데이터를 메타 서버로 직접 전송할 수 있도록 메타 광고에서 제공하는 전환 API 도구를 사용합니다. 이러한 데이터에는 구매, 등록 및 기타 유형의 전환과 같은 사용자 행동이 포함될 수 있으며, 이는 모바일 플랫폼이 아닌(웹사이트 또는 애플리케이션) 환경에서 수행된 것입니다. 그런 다음, 메타 광고에서 이 데이터를 사용하여 광고 타겟팅을 최적화하고 광고 성과를 측정하며, 리타겟팅을 위한 맞춤 오디언스를 구축합니다.

메타 웹과의 통합은 설치 및 인앱 이벤트에 대한 포스트백 전송만 지원합니다.

<div id="integration-tab" />

<Accordion title="연동 탭">

**연동** 탭에는 아래 설명된 여러 섹션이 포함되어 있습니다.

#### 파트너 활성화

연동을 구성하려면 먼저 파트너 활성화 토글을 **켜야** 합니다.

#### 일반 설정

* **픽셀 ID:** 픽셀 ID를 입력합니다. 메타 광고 관리자에서 검색할 수 있습니다.
  1. <Anchor target="_blank" href="https://www.facebook.com/ads/manager">광고 관리자</Anchor> 사이드 메뉴에서 **모든 도구** > **이벤트 관리자**로 이동합니다.   
     **참고:** 오른쪽 상단의 드롭다운에서 올바른 비즈니스를 선택했는지 확인합니다.
  2. **이벤트 관리자** 사이드 메뉴에서 **데이터 소스**를 선택하면, 픽셀 목록이 표시됩니다. 선택한 비즈니스에 대한 픽셀이 없는 경우 동일한 화면에서 픽셀을 생성할 수 있습니다.
  3. 픽셀 이름 아래에 표시된 픽셀 ID를 복사하여 앱스플라이어 연동의 픽셀 ID 필드에 붙여넣습니다.  
     <Image alt="pixel id3.png" src="https://files.readme.io/77969160b04357d056f2eee435a61314b95225f43e03cb31dd21a80dceef0dae-20748699506193.png" width="283px" />
* **액세스 토큰:** 액세스 토큰을 입력합니다. 관련 검색은 다음 [지침](https://developers.facebook.com/docs/marketing-api/conversions-api/get-started#access-token)을 따르세요.
* **메타 광고의 사용자 개인정보 사용 제한(CCPA):** <Anchor target="_blank" href="/marketers/ko/docs/send-opendsr-api-requests">데이터 보호법</Anchor> 준수를 활성화하려면 이 토글을 켭니다.  
  **참고:** CCPA 개인정보 보호 규정을 준수하면 캘리포니아에 거주하는 메타 광고 사용자의 데이터가 제한됩니다.

#### 뷰-쓰루 어트리뷰션 활성화

앱스플라이어는 확률적 모델링(PMOD) 및 <Anchor target="_blank" href="/marketers/ko/docs/meta-ads-create-web-based-campaigns#set-up-smart-script-crossplatform-landing-page">Smart Script</Anchor> 또는 <Anchor target="_blank" href="/marketers/ko/docs/meta-ads-create-web-based-campaigns#set-up-smart-banners-landing-page">Smart Banner</Anchor>가 활성화된 랜딩 페이지를 사용하는 Meta 웹 캠페인에 대해 뷰스루 어트리뷰션을 지원합니다. 이것은 앱스플라이어가 사용자가 광고를 보고 나중에 앱을 설치하는 결과로 발생하는 앱 설치를 귀속할 수 있게 해주며, 직접 클릭 없이도 플랫폼 간에 가능합니다.

사용자가 Meta 웹 광고를 클릭하여 <Anchor target="_blank" href="/marketers/ko/docs/meta-ads-create-web-based-campaigns#set-up-smart-script-crossplatform-landing-page">스마트 스크립트</Anchor> 또는 <Anchor target="_blank" href="/marketers/ko/docs/meta-ads-create-web-based-campaigns#set-up-smart-banners-landing-page">스마트 배너</Anchor>가 활성화된 랜딩 페이지에 도달하면, 앱스플라이어는 다운스트림 앱 설치를 어트리뷰션할 수 있습니다. 사용 가능한 경우, `fbclid`는 귀속 정확성을 높이기 위해 메타에 대한 포스트백에 포함됩니다.

**뷰-쓰루 어트리뷰션 활성화 방법:**

1. 앱스플라이어에서 사이드바에서 **활성 연동** > **메타 웹 광고**를 엽니다.
2. **연동** 탭에서 **인스톨 어트리뷰션** 섹션으로 스크롤합니다.
3. **뷰-쓰루 어트리뷰션 설치**를 켭니다.
4. **[선택 사항]** **크로스 플랫폼 어트리뷰션 우선순위 동등하게 설정**을 켜고 룩백 윈도우를 설정합니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">크로스 플랫폼 노출에 대한 동등 우선 순위 활성화</Anchor>.를 참조하세요.
5. **어트리뷰션 링크** 탭을 클릭합니다.
6. **뷰-쓰루 어트리뷰션** 섹션으로 스크롤하여 **뷰-쓰루 룩백 윈도우**를 설정합니다(최대 24시간).
7. 설정을 적용하려면 **연동 저장**을 클릭하세요.

#### 포스트백 디폴트 설정

설치에 대한 포스트백은 메타 웹으로만 자동으로 전송됩니다. **사용자 선택** 필드에서 다음 중 하나를 선택하십시오:

* **이 파트너 전용**으로, 이 파트너에서 유래한 사용자에 의해 수행된 이벤트에 대해서만 인앱 이벤트 포스트백이 전송되도록 합니다.
* **모든 미디어 소스, 유기적 포함**은 이 파트너, 다른 파트너 또는 유기적 소스에서 유래한 사용자에 의해 수행된 이벤트에 대해 인앱 이벤트 포스트백이 전송되도록 합니다.

#### 인앱 이벤트 포스트백

메타 웹으로 전송되는 인앱 이벤트 포스트백의 매핑을 구성합니다. 이러한 이벤트는 <Anchor target="_blank" href="https://www.facebook.com/business/help/1541268312717919?id=818859032317965">메타 이벤트 관리자</Anchor>에서 확인할 수 있습니다.

1. **인앱 이벤트 포스트백**을 선택합니다.
2. **이벤트 추가**를 클릭하여 목록에 SDK 또는 서버-투-서버 이벤트를 추가하세요. 다음 표는 작성해야 할 필드를 설명합니다.

| 파라미터 이름 | 설명 |
| --- | --- |
| **앱스플라이어 이벤트** | 앱에 통합된 SDK 또는 서버 간 이벤트에서 앱스플라이어가 수신한 이벤트의 이름입니다.<ul><li>**항목 추가**를 클릭하고 이벤트 이름을 입력한 다음 ![check.png](https://files.readme.io/66d595d0ac8a01489ce810bbd3865fca2556342086dc6b20f26fa3d7b7e3afc2-19124971382289.png)를 클릭합니다.</li></ul> |
| **파트너 이벤트에 매핑** | 파트너 측에서 정의한 각 이벤트의 고유한 이름 또는 ID입니다.<ul><li>드롭다운 상자에서 가장 적합한 사전 정의된 파트너 이벤트를 선택하거나 사용자 지정을 선택합니다.</li></ul> |
| **유저 유입 소스** | <ul><li>**이 파트너 전용**으로, 이 파트너에서 유래한 사용자에 의해 수행된 이벤트에 대해서만 인앱 이벤트 포스트백이 전송되도록 합니다.</li><li>**모든 미디어 소스, 유기적 포함**은 이 파트너, 다른 파트너 또는 유기적 소스에서 유래한 사용자에 의해 수행된 이벤트에 대해 인앱 이벤트 포스트백이 전송되도록 합니다.</li></ul> |
| **포함** | **값 및 수익**: 수익 값(이벤트에 존재하는 경우)을 포함한 모든 이벤트 파라미터가 포스트백으로 전송됩니다. |

3. [선택 사항] 이벤트에 대한 <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#조건부-인앱-이벤트-포스트백">조건을 설정</Anchor>하려면 **조건 추가altconditional-iae-postbacks-icon.pngalt아이콘을 클릭하세요.**
4. 필요한 경우 **인앱 이벤트 포스트백 기간**을 설정합니다(<Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#인앱-이벤트-포스트백-기간">인앱 이벤트 포스트백 기간 구성</Anchor>에 대해 자세히 알아보세요).
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
| 크로스 플랫폼 랜딩 페이지 | **권장 사항**: 여러 플랫폼(예: Epic, Steam)에서도 이용 가능한 앱을 캠페인에서 홍보할 때를 위해.<br /><br /><Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">크로스 플랫폼 랜딩 페이지에 대해 알아보기</Anchor><br /><br /><Anchor target="_blank" href="/marketers/ko/docs/cross-platform-landing-pages-with-smart-script">크로스 플랫폼 랜딩 페이지를 설정하는 방법 알아보기</Anchor><ul><li>모든 관련 URL 파라미터(나중에 스마트 스크립트에 의해 캡처됨)가 광고 URL에 추가되었는지 확인합니다.</li><li>스크립트가 수신 URL에서 FBCLID를 가져와 생성된 링크에 추가하는지 확인합니다. 즉, 나가는 FBCLID URL 파라미터 `fbclid`를 들어오는 URL 파라미터 `fbclid`에 매핑합니다. **참고**! 앱스플라이어 로데이터 리포트에 표시하려면, 수신`fbclid`파라미터가 발신 파라미터`af_sub[1-5]`. 중 하나에 매핑되어야 합니다.</li><li>선택 사항: 값을 수동으로 하드코딩하는 대신 메타의 동적 URL 매크로를 사용합니다. <Anchor target="_blank" href="https://www.facebook.com/business/help/2360940870872492">더 알아보기</Anchor></li></ul> | 마케터(개발자 지원이 필요할 수 있음) |
| 다이렉트 어트리뷰션 링크 | 크로스 플랫폼 랜딩 페이지를 사용하지 않는 경우, 하나의 플랫폼에 하나의 앱만 있기 때문에 직접 어트리뷰션 링크를 생성하여 광고 뒤에 배치할 수 있습니다.<br /><br /><Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-platform-direct-attribution-links">직접 어트리뷰션 링크를 만드는 방법 알아보기</Anchor><ul><li>링크에 필수 파라미터가 포함되어 있는지 확인:<ul><li>af\_media\_source</li><li>af\_campaign\_id</li><li>af\_r</li></ul></li></ul>메타 웹 광고 링크에 사용할 템플릿:<br /><br />`https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}?af_media_source=metaweb_int&af_campaign_id={{campaign.id}}&af_campaign={{campaign.name}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}&af_r={encoded landing page and URL params}`<br /><br />스팀으로 연결되는 메타 웹 광고 링크의 샘플 링크: `https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=metaweb_int&af_campaign_id={{campaign.id}}&af_campaign={{campaign.name}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello`<br /><br />**참고**: 템플릿에는 메타에서 지원하는 몇 가지 동적 URL 파라미터가 포함되어 있습니다. 원하는 경우 실제 값으로 수동으로 바꿀 수 있습니다. <Anchor target="_blank" href="https://www.facebook.com/business/help/2360940870872492">Meta 동적 URL 파라미터에 대해 자세히 알아보기</Anchor> | 마케터 |

</Accordion>

<div id="cost-tab" />

<Accordion title="비용 탭">

메타 웹에서는 비용을 사용할 수 없습니다.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="광고 수익 탭">

메타 웹에서는 광고 수익을 사용할 수 없습니다.

</Accordion>

<div id="permissions-tab" />

<Accordion title="권한 탭">

현재 메타 웹에는 권한이 부여되지 않습니다.

</Accordion>

## PC 및 콘솔 앱용 메타 웹에서 캠페인 설정하기

**새 캠페인을 설정할 때 다음 사항이 적용됩니다.**

* 캠페인 목표를 선택합니다. 다음 중 하나를 선택하는 것을 추천합니다.
  * **판매**: 이를 통해 Meta는 특정 이벤트(주요 KPI)에 대해 최적화할 수 있습니다.
  * **트래픽**: 이를 통해 Meta는 광고 클릭에 대해 최적화할 수 있습니다. 다른 KPI가 없거나, KPI 이벤트의 볼륨이 너무 낮은 경우에만 이 옵션을 사용합니다.
  * **사용자 지정**: 캠페인 목표로 사용자 정의 이벤트를 설정하려면. **참고:** 사용자 정의 이벤트가 메타 대시보드의 캠페인 목표로 나타나도록 하려면 먼저 앱스플라이어서 사용자 정의 이벤트를 설정하세요.
* **웹사이트**를 전환 위치로 선택합니다.
* 페이스북 전환 픽셀의 이름을 지정할 때, 앱스플라이어 파트너 마켓플레이스에서 metaweb\_int에 입력한 것과 동일한 픽셀 ID를 입력합니다.
* 광고의 대상으로 웹사이트 URL을 입력할 때는 다음 중 하나의 URL을 입력해야 합니다.
  * 웹 랜딩 페이지(여러 플랫폼에 앱이 있는 경우 권장)
  * 스토어 URL(앱이 단일 플랫폼의 단일 앱 스토어에 있는 경우 권장)

## 웹-앱 귀속 데이터 보기

웹 기반 전환 이벤트는 원래 `metaweb_int` PID 아래에서 Meta에 전송되지만, `Facebook Ads` PID 아래에서 AppsFlyer 대시보드 및 원시 데이터 보고서에 보고됩니다. 이는 기본 전환 이벤트와 전환 보조 이벤트 모두에 적용됩니다.

이 통합 보고 뷰를 통해 웹 및 앱 캠페인 성과를 한 곳에서 분석할 수 있으며, 전체 웹 및 모바일 비용 보고가 포함됩니다.

### 대시보드에서 보기

모든 Meta 웹-앱 귀속은 개요 및 활동 대시보드에서 `Facebook Ads` 아래에 나타납니다. 이는 플랫폼 전반에 걸친 캠페인 결과의 단일 통합 뷰를 제공합니다. 표준 필터 및 분류를 사용하여 Meta 광고 데이터 내에서 앱 및 웹 트래픽을 비교하십시오.

### 원시 데이터 및 API 보고서에서 보기

* **원시 데이터 내보내기 및 API 응답**은 Meta 웹 활동을 위한 `media_source` 필드에 `Facebook Ads` PID를 포함합니다. 웹 캠페인 설정 세부정보를 확인하려면, 웹 캠페인 생성 시 사용된 PID로 `metaweb_int`를 보여주는 `original_url` 필드를 참조하십시오.
* **포스트백 보고서**는 포스트백이 전송된 원래 미디어 소스로 `metaweb_int`를 보여줍니다.

## 특징 및 제약 사항

| 특징 | 설명 |
| --- | --- |
| 클릭 및 노출(일시적 제한) | PC 및 콘솔 앱을 대상으로 하는 캠페인의 클릭 및 노출은 Meta SRN(`Facebook Ads`)에서 일시적으로 사용할 수 없습니다. |

<div data-zendesk-anchors="h_01HE2XD0FSY0QMJSKVC0FHHK5P=%EC%A4%91%EC%9A%94 overview=%EA%B0%9C%EC%9A%94 h_01HK4QHRJG6WTN9P6ZG83XQ6AY=%EA%B0%9C%EC%9A%94 prerequisite=%EC%A0%84%EC%A0%9C-%EC%A1%B0%EA%B1%B4 h_01HFXV8HPGCRGYPEW0NPJ0NR0S=%EC%A0%84%EC%A0%9C-%EC%A1%B0%EA%B1%B4 activate-partner=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 h_01HFXV8HPH3N4DBKKTQE6DK7FK=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 setting-up-metaweb-in-appsflyer=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%97%90%EC%84%9C-%EB%A9%94%ED%83%80-%EC%9B%B9-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 01H88VAJH3VENKYVRQY5RXN63P=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%97%90%EC%84%9C-%EB%A9%94%ED%83%80-%EC%9B%B9-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 01H88VAJH3VZ4GPVE7XXMKTZ2P=integration-tab activate-partner::1ca30957=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 h_01HFXV8HPH6X92YETNAGZ910AV=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 transaction-id=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 h_01HARQDVEDA206D0BBXBC6WEHH=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 enable-viewthrough-attribution=%EB%B7%B0-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%99%9C%EC%84%B1%ED%99%94 h_01ZXVWB1ZYKK4DP38QY1RMEY6M=%EB%B7%B0-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%99%9C%EC%84%B1%ED%99%94 default-postbacks=%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EB%94%94%ED%8F%B4%ED%8A%B8-%EC%84%A4%EC%A0%95 01H88VAJH3WE9Z0971WMBRBJRS=%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EB%94%94%ED%8F%B4%ED%8A%B8-%EC%84%A4%EC%A0%95 inapp-event-postbacks=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 01H88VAJH3AS37MVF75GANWX4B=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 01H88VAJH31GZ4KAY280ZRB8MA=attribution-link-tab 01H88VAJH3RM95V449B6DF8B4D=cost-tab 01H88VAJH3A2Q0CZXQQZMW6YRC=ad-revenue-tab 01H88VAJH30TCC574W2DH7R2A2=permissions-tab setting-up-campaigns-in-meta-web-for-pc-and-console-apps=pc-%EB%B0%8F-%EC%BD%98%EC%86%94-%EC%95%B1%EC%9A%A9-%EB%A9%94%ED%83%80-%EC%9B%B9%EC%97%90%EC%84%9C-%EC%BA%A0%ED%8E%98%EC%9D%B8-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 h_01HK4S03KVAN99YKXTHAKCT420=pc-%EB%B0%8F-%EC%BD%98%EC%86%94-%EC%95%B1%EC%9A%A9-%EB%A9%94%ED%83%80-%EC%9B%B9%EC%97%90%EC%84%9C-%EC%BA%A0%ED%8E%98%EC%9D%B8-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 meta%20view=%EC%9B%B9-%EC%95%B1-%EA%B7%80%EC%86%8D-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B8%B0 view-webtoapp-attribution-data-from-november-2-2025=%EC%9B%B9-%EC%95%B1-%EA%B7%80%EC%86%8D-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B8%B0 h_01K88J8JFNEYBZNR18133NMRP9=%EC%9B%B9-%EC%95%B1-%EA%B7%80%EC%86%8D-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B8%B0 view-in-the-dashboard=%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C%EC%97%90%EC%84%9C-%EB%B3%B4%EA%B8%B0 h_01K88J8JFNMHCVZ0C34E3D7AST=%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C%EC%97%90%EC%84%9C-%EB%B3%B4%EA%B8%B0 view-in-raw-data-and-api-reports=%EC%9B%90%EC%8B%9C-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B0%8F-api-%EB%B3%B4%EA%B3%A0%EC%84%9C%EC%97%90%EC%84%9C-%EB%B3%B4%EA%B8%B0 h_01K88J8JFN8W2572N92466YFZQ=%EC%9B%90%EC%8B%9C-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B0%8F-api-%EB%B3%B4%EA%B3%A0%EC%84%9C%EC%97%90%EC%84%9C-%EB%B3%B4%EA%B8%B0 traits-and-limitations=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD h_01KB503RDVWPSFBAPAPW4CNZXM=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD" />
