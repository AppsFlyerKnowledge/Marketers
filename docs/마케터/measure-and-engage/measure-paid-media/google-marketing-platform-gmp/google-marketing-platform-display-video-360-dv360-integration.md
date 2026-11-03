---
title: Google 마케팅 플랫폼 - Display & Video 360 (DV360) 연동
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2021-02-02T17:40:13Z'
  edited_at: '2026-10-14T10:36:52Z'
  id: 360017595598
  locale: ko
  section: Google Marketing Platform (GMP)
  section_id: 6551212604305
  url: https://support.appsflyer.com/hc/ko/articles/360017595598
---
> **한눈에 보기:** Google 마케팅 플랫폼 - Display & Video 360 (GMP-DV360)은 앱스플라이어의 자가 리포팅 네트워크(SRN) 파트너로, 광고와 분석을 결합합니다. GMP-DV360 연동(dv360\_int)은 광고와 분석을 통합하여 고객 연계를 강화, 인사이트를 드러내며 마케팅 성과를 향상시킵니다.

> 🚧 **중요!**
>
> <Anchor target="_blank" href="/marketers/ko/docs/bulletin-supporting-the-new-google-eu-consent-policy">새로운 Google EU 동의 정책 지원</Anchor>에 대한 공지를 확인하세요.

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/doubleclick.png" width="121px" />

## 개요

GMP-DV360 연동은 전환 측정을 위해 링크 ID를 활용합니다. 다음을 활용하여 GMP-DV360&lt;4>과 직접 혹은 대행사를 통해, 아니면 둘 다를 통해 협력할 수 있습니다:

* [광고주를 위한 DV360](#광고주를-위한-gmp-dv360설정): 일회성 과정 - 필수
* [대행사를 위한 DV360](#대행사용-gmp-dv360-설정하기): 대행사별로 선택 사항

> 📘 **참고**
>
> * GMP-DV360 연동은 Legacy GMP DV360/CM (doubleclick\_int) 연동을 대체하기 위해 설계되었으며, 이는 2024년 2분기까지 서비스가 중단될 예정입니다.
> * API 사용을 위해서는 GMP-DV360 계정 담당자에게 문의하십시오.

아래 표는 GMP 연동 솔루션에 대해 설명합니다:

| GMP 솔루션 | 설명 | 연동을 위해 필요한 조치 |
| --- | --- | --- |
| DV360 시리즈 | DV360을 앱스플라이어와 연동해 dv360\_int 어트리뷰션을 측정하십시오 | [광고주 연동 완료](#광고주를-위한-gmp-dv360설정) |
| CM360 & DV360 | CM360을 통해 DV360 트래픽을 구입하고, 앱스플라이어에서는 dvc360\_int 어트리뷰션으로 측정합니다. | [광고주 연동 완료](#광고주를-위한-gmp-dv360설정) |
| CM360 및 비-DV360 타사 미디어 소스 | 타사 미디어 소스로부터 트래픽을 구입하고, 이 트래픽에서 발생하는 모바일 앱 전환을 CM360에서 측정합니다. | <Anchor target="_blank" href="/marketers/ko/docs/gmp-use-case-of-traffic-measurement-from-3rd-parties-in-cmp360">CM360을 사용한 타사 트래픽 측정</Anchor> |

### 앱스플라이어와 GMP - DV360 간 데이터 공유

**앱스플라이어로부터 제공되는 데이터:** 앱스플라이어는 전환과 인앱 이벤트와 관련된 포스트백을 GMP-DV360에 전송합니다.

**앱스플라이어에 제공될 데이터:** GMP-DV360에서 전환을 주장하면, 해당 미디어 소스 파라미터를 앱스플라이어에 제공합니다. 해당 파라미터들은 분석 및 로데이터 리포트에 사용됩니다. 아래 표는 GMP-DV360과 앱스플라이어 간의 매핑 파라미터를 나타냅니다.

| GMP | 앱스플라이어 |
| --- | --- |
| 상호작용 형태 | attributed\_touch\_type |
| 타임 스탬프 | attributed\_touch\_time |
| line\_item\_id | campaign\_id |
| line\_item\_name | campaign\_name |
| creative\_id | ad\_id |
| product\_type | af\_channel |
| external\_customer\_id | network\_account\_id |
| site\_id | af\_siteid |

## 광고주를 위한 GMP-DV360설정

**필수 조건**

연동을 설정하기 전에 다음 사항들을 확인해주세요:

* <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations#contact-details">해당 파트너에게 연락하여</Anchor>&lt;2> 계정을 개설합니다.
* <Anchor target="_blank" href="https://support.google.com/displayvideo/answer/10956727">GMP-DV360 링크 ID를 받으세요.</Anchor>

**연동 활성화 또는 편집 방법:**

1. **활성화하기:** 앱스플라이어의 측면 메뉴에서 **협업**> **파트너 마켓플레이스**를 선택하세요.  
   **편집하기**: 앱스플라이어의 사이드 메뉴에서 **콜라보레이트** > **활성 연동을** 선택합니다.
2. **Google 마케팅 플랫폼 - Display & Video 360 (DV360)** 를 검색하여 선택하세요.
3. **연동 설정**을 클릭합니다. 연동 설정 페이지로 이동합니다.
4. **연동** 탭에서 연동할 앱을 선택하고 **파트너 활성화**를 켭니다.  
   **참고:** 파트너와 협력하는 동안 토글은 반드시 켜져<Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">(활성화)</Anchor> 있어야 합니다.
5. 아래 설명된 대로 관련 탭을 사용하여 설정을 완료하십시오.

<div id="integration-tab" />

<Accordion title="연동 탭">

앱스플라이어가 GMP-DV360을 쿼리할 때, 그들은 응답에 나열된 파라미터를 제공합니다. 이 파라미터들은 아래에 자세히 나열된 표대로 앱스플라이어 파라미터 및 로데이터와 매핑됩니다.

| GMP - 이전 파라미터 | GMP-DV360 파라미터 | 앱스플라이어 파라미터 | URL 파라미터 |
| --- | --- | --- | --- |
| 게재위치 ID | 항목 이름 | 캠페인 이름 | C |
| 게재위치 ID | 항목 ID | 캠페인 ID | af\_c\_id |
| 사이트 ID | 사이트 ID | 사이트 ID | af\_siteid |
| 광고소재 ID | 광고소재 ID | 광고 ID | af\_ad\_id |

<span id="activate-partner::e4f2f638"></span>**연동** 탭에는 아래 설명과 같이 여러 섹션이 있습니다.

#### 파트너 활성화

연동을 구성하려면 먼저 **파트너 활성화** 토글을 켜야 합니다. 파트너 연동을 <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation#파트너-연동-활성화">활성화 및 비활성화하는 방법</Anchor>에 대해 더 알아보세요.

#### 일반 설정

**링크 ID:** 사전 준비 과정에서 언급된 링크 ID를 입력해 주세요.

**EU 외 사용자:** <Anchor target="_blank" href="/marketers/ko/docs/support-google-eu-consent-policy#do-i-have-control-over-consent-data-for-nonue-users">**EU 외 사용자**</Anchor>를 활성화할지 결정해주세요.

<Image alt="non eu usrs.png" src="https://files.readme.io/fb141c0bd8885facd6574f3e73c5ec8ae8beb596de7fdf3dd8aed9d4e82686dd-22352319155985.png" width="536px" />

#### 인스톨 어트리뷰션

광고를 본 또는 클릭한 사용자의 신규 설치(첫 실행 포함)를 어트리뷰션하기 위한 다양한 어트리뷰션 기간을 설정하세요. 이는 클릭 또는 조회로부터 설치까지의 최대 시간을 나타냅니다. Google Marketing Platform - Display & Video 360 (DV360)에 측정되기 위해서는 설치가 룩백 윈도우 내에 있어야만 합니다.

1. 설치 클릭-쓰루 룩백 윈도우를 1-23시간 또는 1-30일 중에서 설정하세요.
2. [선택 가능] 설치 뷰-쓰루 어트리뷰션을 활성화하고 룩백 윈도우를 1-23시간 또는 1-30일로 설정하세요.

#### 리인게이지먼트 어트리뷰션

광고를 본 또는 클릭한 기존 사용자들의 재인게이지먼트를 어트리뷰션하기 위해 다양한 어트리뷰션 기간을 설정하세요. 룩백 윈도우 내에 있는 재인게이지먼트만이 GMP-DV360에 측정됨을 유의하세요.

1. 재인게이지먼트 클릭-쓰루 룩백 윈도우를 1-23시간 또는 1-30일로 설정하세요.
2. [선택 가능] 재인게이지먼트 뷰-쓰루 어트리뷰션을 활성화하고 룩백 윈도우를 1-23시간 또는 1-7일로 설정하세요.

<Anchor target="_blank" href="/marketers/ko/docs/retargeting-attribution-guide#reengagement-rules-and-windows">리인게이지먼트 규칙 및 기간</Anchor>에 대해 자세히 알아보세요.

#### 리인게이지먼트 기간

인앱 이벤트가 주로 리인게이지먼트 전환으로 측정되는 시간 기간을 설정합니다. <Anchor target="_blank" href="/marketers/ko/docs/retargeting-attribution-guide#setup-reengagement-window">더 알아보기</Anchor>.

* **리인게이지먼트 기간**을 1-23시간, 1-90일, 또는 **생애** 중에서 설정하세요.

#### 리타겟팅 대상으로 활성 유저 무시

앱을 실행한 사용자들의 리인게이지먼트 및 리-어트리뷰션을 <Anchor target="_blank" href="/marketers/ko/docs/set-retargeting-inactivity-window#비활성-기간">무시할</Anchor> 시간대를 정하세요. 이는 지정된 시간대 동안의 사용자 활동이 앱스플라이어에 기록되지 않는다는 것을 의미합니다.

> 📘 **참고**
>
> 지정된 시간 동안 **활동하지 않았던** 사용자들의 재인게이지먼트 및 리-어트리뷰션 전환은 **기록됩니다**.

1. 리타겟팅을 위해 **활동 중인 사용자 무시** 기능을 활성화하세요.
2. 비활성 기간을 설정하세요.

#### 인앱 이벤트 포스트백

GMP-DV360 이벤트로부터 포스트백을 통해 발송되는 인앱 이벤트를 매핑하도록 설정:

1. **인앱 이벤트 포스트백**을 켭니다.
2. **이벤트 추가**를 클릭하여 목록에 SDK 또는 서버-투-서버 이벤트를 추가하세요. 다음 표는 작성해야 할 필드를 설명합니다.  

| 파라미터 이름 | 설명 |
| --- | --- |
| **앱스플라이어 이벤트** | 앱스플라이어가 앱에 연동된 SDK 또는 서버 간 이벤트에서 수신한 이벤트의 이름입니다.<br />**팁**: 찾고 있는 이벤트가 없나요?<ul><li>논오가닉 설치된 디바이스에서 이벤트를 활성화하고 다시 확인하세요.</li><li>**앱스플라이어 이벤트**에 입력한 다음 **사용자 지정 생성**을 클릭합니다. <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#커스텀-이벤트">커스텀 이벤트 매핑</Anchor>에 대해 더 알아보세요.</li></ul> |
| **파트너 이벤트에 매핑** | 파트너 측에서 정의한 각 이벤트의 고유한 이름 또는 ID입니다. 가능한 매핑 구성은 다음과 같습니다.<ul><li>**드롭다운 상자:** 가장 적합한 사전 정의된 앱스플라이어 이벤트를 선택합니다.</li><li>**커스텀**</li></ul>**참고:** |
| **사용자용** | 이벤트의 전송 옵션을 선택합니다.<ul><li>**이 파트너만**(기본값): 이 이벤트가 GMP-DV360에 어트리뷰션되었을 때만 포스트백을 전송합니다.</li><li>**오가닉을 포함한 모든 미디어 소스:** 어트리뷰션된 모든 파트너 이벤트 및 오가닉 이벤트에 대해서도 포스트백을 보냅니다.</li></ul> |
| **포함** | <ul><li>**값 없음 & 수익 없음** (기본 설정): 이벤트 값 없이 이벤트 자체만 발송합니다.</li><li>**값 있음 & 수익 없음**: 수익 값을 **제외한** 모든 파라미터를 전송합니다.</li><li>**값 있음 & 수익 있음**: 수익 값이 있는 경우 이를 **포함**한 모든 이벤트 파라미터를 발송합니다.</li></ul> |

3. [선택 사항] 이벤트에 대한 <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#조건부-인앱-이벤트-포스트백">조건을 설정</Anchor>하려면 **조건 추가altconditional-iae-postbacks-icon.pngalt아이콘을 클릭하세요.**
4. **연동 저장**을 클릭하세요.
5. [선택 가능] 연동을 저장하고 설정 페이지에 있으면서 GMP-DV360와 더 많은 앱을 연동할 수 있습니다:
   1. 왼쪽 상단 모서리의 파트너 이름 아래에서 앱 이름을 클릭하여 앱 목록을 엽니다.
   2. 드롭다운 목록에서 다른 앱을 선택합니다.
   3. 선택한 앱에 대해 연동 단계를 반복합니다.

> 📘 **참고**
>
> iOS 앱의 경우에만: 포스트백 및 <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions">리포트</Anchor>를 통해 파트너와 공유된 데이터에 대한 제어 권한은 **고급 개인정보 보호(iOS 14.5 이상)** [토글 상태](#advanced-privacy)에 따라 달라집니다.

#### U 매개변수 매핑

앱스플라이어는 u 파라미터로 알려진 추가 파라미터 전송을 지원하며, u26까지 제한됩니다. U 파라미터는 앱스플라이어에서 미리 정의되어 있으며 변경이 불가능합니다. 다음 사항을 참고해 주세요:

* 파라미터들이 사전에 정의되어 있어 추가적인 커스텀 U 파라미터 설정이 불가능합니다.
* 특정 U 파라미터에 대한 데이터가 없는 경우, 앱스플라이어는 해당 파라미터를 전송하지 않습니다. 예를 들어, 통신사 데이터가 없으면 앱스플라이어는 U5를 전송하지 않습니다.

| U 파라미터 | 이름 | 예시 값 |
| --- | --- | --- |
| u1= | AF 장치 ID | 1540995037437-2811776739500410055 |
| u2= | 고객 사용자 ID | eaf8a5f2.1836.4686 |
| u3= | **안드로이드**:  <br />광고 식별자  <br />**iOS**: idfa | 9d9d03ab-f211-4e17-994e-d0afdf23ac01 |
| u4= | wifi | true |
| u5= | carrier | Jio%204G |
| u6= | 국가 코드 | 인도 |
| u7= | Region | HR |
| u8= | city | 구르가온 |
| u9= | 기기 유형 | 모토로라::모토 G (4) |
| u10= | OS 버전 | 7 |
| u11= | SDK 버전 | v4.8.18 |
| u12= | 앱 버전 | 3.31.1 |
| u13= | 설치 타임스탬프 | 1540995041 |
| u14= | 클릭 시간 | 1546441586 |
| u15= | 노출 시간 | 1546441586 |
| u16= | 캠페인 이름* | Appinstall\_campaign |
| u17= | 캠페인 ID | 12345ABC |
| u18= | 애드셋 이름* | Appinstall\_adset |
| u19= | 광고세트 ID | 12345ABC |
| u20= | 광고 이름* | Appinstall\_ad |
| u21= | 광고 아이디 | 1234567ABCDE |
| u22= | 사이트 ID | site\_id\_123456 |
| u23= | 이벤트 시점 | 2019-01-04 12:56:35.707 |
| u24= | event name | af\_purchase |
| u25= | 이벤트 값 | `{"af_price":459,"af_content_id":"77147","af_revenue":4.59,"af_currency":"EUR"}` |
| u26= | currency | EUR |

* GMP-DV360에서 이 파라미터 이름의 응답을 받지 못하면 앱스플라이어는 해당 필드를 대응하는 ID로 채웁니다. 예를 들면, Adset 이름은 `12345ABC`이라는 Adset ID로 표시됩니다.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="어트리뷰션 링크 탭">

**DV360과 함께 앱스플라이어 어트리뷰션 링크를 노출 및 클릭 기록에만 사용할 수 있습니다**. 이러한 링크는 저작자 표시에 사용되지 않으며 그 안에 포함된 추가 정보는 어떤 목적으로도 구문 분석되거나 사용되지 않습니다.

앱스플라이어에서 DV360의 클릭 수를 측정할 수 있으려면 DV360 대시보드에 앱스플라이어 어트리뷰션 URL을 추가해야 합니다. 이 경우 앱스플라이어가 올바른 캠페인에 대한 클릭 데이터를 검색하고 추가할 수 있도록 어트리뷰션 URL의 캠페인 이름이 **GMP의 배치 ID** 와 동일 한지 확인하십시오(가능한 경우).

앱스플라이어에서 **클릭 수를** 계산하려면 다음 링크를 사용하십시오.  

```http
https://app.appsflyer.com/ADD-APP-ID?pid=dv360_int&af_siteid=${UNIVERSAL_SITE_ID}
&af_ad_id=${CREATIVE_ID}&c=${PLACEMENT_ID}&af_c_id=${PLACEMENT_ID}
```

앱스플라이어에서 **노출수를** 계산하려면 다음 링크를 사용하십시오.

```http
https://impression.appsflyer.com/ADD-APP-ID?pid=dv360_int&af_siteid=%24{UNIVERSAL_SITE_ID}
&af_ad_id=${CREATIVE_ID}&c=${PLACEMENT_ID}&af_c_id=${PLACEMENT_ID}
```

</Accordion>

<div id="cost-tab-for-cost-clicks-and-impressions" />

<Accordion title="비용 탭(비용, 클릭 수, 노출 수)">

이 연동에서는 비용 데이터를 지원하지 않습니다.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="광고 수익 탭">

이 연동에서 광고 수익을 지원하지 않습니다.

</Accordion>

## 대행사용 GMP-DV360 설정하기

대행사는 귀사를 대신해 GMP-DV360을 사용하여 캠페인을 운영할 수 있습니다.

#### 에이전시 설정

| 절차 실행자 | 절차 |
| --- | --- |
| 광고주 | <ol><li>광고주의 GMP-DV360 연동이 완료되었는지 확인하세요.</li><li>앱스플라이어의 측면 메뉴에서 **협업** > **활성화된 연동**을 선택하세요.</li><li>대행사를 선택합니다.</li><li>**권한** 탭으로 이동하여 **에이전시 권한**을 켭니다.</li><li>**[옵션]** 연동 **탭에서 인앱 이벤트 포스트백&lt;3>을 켭니다. 이렇게 하면 대행사가 포스트백을 켜거나 끌 수 있게 됩니다.**</li></ol> |
| 에이전시 | <ol><li>앱스플라이어의 측면 메뉴에서 **협업** > **활성화된 연동**을 선택하세요.</li><li>**Google 마케팅 플랫폼 - Display & Video 360 (DV360)&lt;2>을 선택하세요..**</li><li>**연동 탭**으로 이동합니다.</li><li>활성화 파트너가 **켜짐** 상태인지 확인하세요. **그렇지 않을 경우, 광고주가 [광고주 GMP-DV360 연동&lt;4>을 완료해야 합니다.](#광고주를-위한-gmp-dv360설정)**</li><li>룩백 기간 및 인앱 이벤트 매핑과 같은 나머지 설정들이 정확한지 확인하세요. 필요하다면, 광고주에게 수정을 요청하세요.</li><li>하나 이상의 **DBM 광고주 ID**를 입력하세요. ID는 귀하의 <Anchor target="_blank" href="https://support.google.com/displayvideo/answer/11415707?hl=en">GMP 대시보드</Anchor>에서 확인할 수 있습니다.</li><li>**저장**을 클릭합니다.</li></ol> |

## GMP-DV360 차이점

차이점의 가능한 원인과 최소화 방법을 확인하세요:

| 원인 | 설명 | 앱스플라이어 팁 |
| --- | --- | --- |
| 뷰스루 어트리뷰션 창 | GMP-DV360 어트리뷰션 기간에서 뷰-쓰루(view-through)는 14일인 반면, 앱스플라이어의 기본 기간은 1일입니다. |  |
| 매핑이 잘못되었습니다 | 앱스플라이어와 GMP-DV360 간 매핑이 올바르지 않습니다 | <ul><li>링크 ID를 확인하십시오</li><li>인앱 이벤트 매핑이 정확한지 확인하십시오</li></ul> |

<div data-zendesk-anchors="h_01HMEH8VW3PYCZ6GC4T5BYBS3V=%EC%A4%91%EC%9A%94 overview=%EA%B0%9C%EC%9A%94 01H8E4ZJNRMXY183TQCPW15ZQB=%EA%B0%9C%EC%9A%94 01H8DYEV7JPV80T3YAJQQHBA6C=%EC%B0%B8%EA%B3%A0 data-sharing-between-appsflyer-and-gmp=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%99%80-gmp---dv360-%EA%B0%84-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B3%B5%EC%9C%A0 h_01HQ0QJJRMYP3E6B5FVA0V6861=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%99%80-gmp---dv360-%EA%B0%84-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B3%B5%EC%9C%A0 advertiser-gmp-integration=%EA%B4%91%EA%B3%A0%EC%A3%BC%EB%A5%BC-%EC%9C%84%ED%95%9C-gmp-dv360%EC%84%A4%EC%A0%95 01H8DYEV7KYNB2FJG7N1CTEE86=%EA%B4%91%EA%B3%A0%EC%A3%BC%EB%A5%BC-%EC%9C%84%ED%95%9C-gmp-dv360%EC%84%A4%EC%A0%95 h_01HPYMRJ1WVVKCHKKEA6WD0XZP=integration-tab 01H8VVCC8G0KR4AA2HD9S8QBKD=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 general-settings=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 01H8VVCC8GSDPSNN0AJPVZPR8P=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 install-attribution=%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 01H8VVCC8GK8VFPBEPAMVHCAWM=%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 reengagement-attribution=%EB%A6%AC%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 01H8VVCC8HHG5290PYF0BT29QA=%EB%A6%AC%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 reengagement-window=%EB%A6%AC%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8-%EA%B8%B0%EA%B0%84 h_01HQ06JCJZD6AMFR2B6GTMSM9S=%EB%A6%AC%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8-%EA%B8%B0%EA%B0%84 ignore-active-users-for-retargeting=%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%EB%8C%80%EC%83%81%EC%9C%BC%EB%A1%9C-%ED%99%9C%EC%84%B1-%EC%9C%A0%EC%A0%80-%EB%AC%B4%EC%8B%9C h_01HNWSTJZPFQVQ5C8M0JA1J0T5=%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%EB%8C%80%EC%83%81%EC%9C%BC%EB%A1%9C-%ED%99%9C%EC%84%B1-%EC%9C%A0%EC%A0%80-%EB%AC%B4%EC%8B%9C h_01HMXNJVHK9C3FT8E04RE0TH99=%EC%B0%B8%EA%B3%A0-1 inapp-event-postbacks=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 01H8VVCC8HHZRFQ2T1X478YZMP=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 01H8VVCC8HDMTY1P2SG31HD61K=%EC%B0%B8%EA%B3%A0-2 parameter-mapping=u-%EB%A7%A4%EA%B0%9C%EB%B3%80%EC%88%98-%EB%A7%A4%ED%95%91 h_01HBBJQZSTT1HFENXNACMHFC18=u-%EB%A7%A4%EA%B0%9C%EB%B3%80%EC%88%98-%EB%A7%A4%ED%95%91 01H8VVCC8H53ZRMDBNK1436NAX=attribution-link-tab h_01HBBJQZSW45X3SM92H4FS94HM=%EC%A4%91%EC%9A%94 01H8VVCC8H74GDVCNAXT0741MG=cost-tab-for-cost-clicks-and-impressions 01H8VVCC8H90ANM70QAHKTQQ1S=ad-revenue-tab setting-up-gmp-dv360-for-agencies=%EB%8C%80%ED%96%89%EC%82%AC%EC%9A%A9-gmp-dv360-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 01H8VVCC8HVNNQ9PJS4ZQCVDNS=%EB%8C%80%ED%96%89%EC%82%AC%EC%9A%A9-gmp-dv360-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 agency-setup=%EC%97%90%EC%9D%B4%EC%A0%84%EC%8B%9C-%EC%84%A4%EC%A0%95 01H8DYEV7MNFFY9ESFF2S3ETEB=%EC%97%90%EC%9D%B4%EC%A0%84%EC%8B%9C-%EC%84%A4%EC%A0%95 gmp-discrepancies=gmp-dv360-%EC%B0%A8%EC%9D%B4%EC%A0%90 01H8DYEV7MTPJMY12AVHX45YFF=gmp-dv360-%EC%B0%A8%EC%9D%B4%EC%A0%90" />
