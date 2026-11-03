---
title: 스마트 배너—모바일 웹-투-앱 (마케터 용)
metadata:
  keywords:
    - Landing Page
    - Advertisers
    - Web Attribution
    - Developers
    - Smart Banner
    - sb
    - Marketers
    - Banner
    - Banners
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2019-01-14T12:33:07Z'
  edited_at: '2026-10-14T10:30:04Z'
  id: 360000764837
  locale: ko
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/ko/articles/360000764837
---
> **한눈에 보기:** 스마트 배너를 통해 웹 사이트 방문객을 모바일 앱 유저로 전환하세요.

[![](https://files.readme.io/2e76dd3d337d7cb8e34af01b34f3a466fa724566058d260f56796bf6eae4b3ff-34734678772881.jpg)](https://files.readme.io/2e76dd3d337d7cb8e34af01b34f3a466fa724566058d260f56796bf6eae4b3ff-34734678772881.jpg)

> 📘 **참고**
>
> 2023년 11월 8일 기준, 앱스플라이어 스마트 배너 웹 SDK v1은 지원이 종료되었습니다. 웹사이트에 스마트 배너를 표시하기 위해 v2로 업그레이드해야 합니다. <Anchor target="_blank" href="/marketers/ko/docs/bulletin-deprecation-of-appsflyer-smart-banner-web-sdk-v1">더 알아보기.</Anchor>

## 스마트 배너

스마트 배너:

* **귀하의 브랜드 모바일 웹사이트에 배너를 설치하여** 구매 의도가 높은 유저의 전환율을 높일 수 있습니다.
* 모바일 웹사이트 방문자의 앱 인스톨 품질을 측정합니다.
* SRN을 포함한 모든 미디어 소스에 대해 정확한 웹 캠페인-투-앱 모바일 어트리뷰션을 지원합니다.
* 스마트 배너는 <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-attribution-model#유저-인게이지먼트-어트리뷰션-유형">뷰스루 어트리뷰션, 클릭스루 어트리뷰션</Anchor> 및 노출 수를 계산하여 속성을 지정할 수 있습니다.
  * **클릭 수:** 유저가 스마트 배너를 클릭하고 설치를 진행합니다.
  * **노출 수:** 배너가 로드되면(유저에게 배너가 보일 때) 앱스플라이어에 노출 이벤트를 전송합니다.

흐름은 다음과 같습니다:

1. 유저가 광고를 클릭하면 광고주의 모바일 웹사이트로 이동합니다.
2. 광고주의 모바일 웹사이트에 스마트 배너가 [표시](/docs/smart-banners-mobile-web-to-app-for-marketers#banner-group-display-logic)됩니다.
3. 유저가 스마트 배너를 클릭하면:
   * **앱이 설치되어 있지 않은 경우**, 앱을 설치할 수 있는 앱 스토어로 이동합니다.
   * **앱이 설치되어 있는 경우**, 유니버설 링크, 앱 링크 및/또는 URI 링크가 구성되고 앱이 바로 실행됩니다.
4. 유저가 프로모션과 관련된 인앱 콘텐츠에 도달합니다.
5. 유저는 원본 광고를 게재한 미디어 소스에 어트리뷰션됩니다.

**담당자**

* 웹사이트 개발자는 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#installation">웹사이트의 HTML에 코드 스니펫만 입력</Anchor>하면 됩니다.
* 그 외 다른 작업은 모두 마케팅 담당자가 할 수 있습니다.

---

**필수 조건**

* 최소 한 개 이상의 앱이 등록된 앱스플라이어 계정
* 스마트 배너를 통해 광고할 앱이 포함된 <Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template">OneLink 템플릿</Anchor>은, 유저의 디바이스에 따라 모바일 웹 방문자를 올바른 앱 스토어 페이지로 유도하는 데 필요합니다.

---

**소요 시간**

약 20분

---

**결과**

* 웹사이트 방문자가 CTA 버튼을 클릭하면 디바이스에 따라 올바른 앱 스토어 또는 웹 페이지로 이동합니다.
* 모바일 앱 유저가 CTA 버튼을 클릭하면 딥링크를 통해 앱으로 연결될 수 있습니다.
* 유저는 클릭/설치를 통해 원본 미디어 소스 또는 소유한 미디어 소스로 어트리뷰션됩니다.
* 배너 실적은 실적 페이지와 카드에서 확인할 수 있습니다.

---

---

> 📄 **예시**
>
> 마크는 성공적인 음식 배달 서비스 ‘Feed Me’에서 일하는 마케터입니다.
>
> 그는 Feed Me의 모바일 웹사이트 방문자를 앱 유저로 전환하려고 합니다.
>
> 이를 위해 마크는 자신의 시각 자료와 텍스트를 사용하여 스마트 배너를 활용합니다.
>
> 스마트 배너는 OneLink로 구동됩니다. 모바일 웹사이트 방문자가 CTA 버튼을 클릭하면 앱을 쉽게 설치할 수 있는 **적절한 앱 스토어 또는 랜딩 페이지로 자동 연결**됩니다. 그리고 기존 모바일 유저가 CTA 버튼을 클릭하면 앱이 실행됩니다.
>
> 그런 다음 앱스플라이어는 **클릭/설치를 마크가 정의한 미디어소스 및 캠페인에 어트리뷰션**합니다.

> 🚧 **중요!**
>
> 앱스플라이어 스마트 배너 또는 iOS 사파리 스마트 앱 배너 중 하나를 사용하되, 둘 다 사용할 수는 없습니다. 두 가지를 모두 사용하면 모바일 웹사이트에 표시 문제가 발생하고 어트리뷰션 불일치가 발생할 수 있습니다.

## 설정

스마트 배너를 설정하려면 다음 절차를 완료하세요.

* 스마트 배너를 통해 모바일 사이트에서 유저를 디바이스에 따라 올바른 앱 스토어 또는 앱 페이지로 안내합니다.
* OneLink를 사용하여 클릭/인스톨을 귀하의 온드 미디어 소스에 어트리뷰션합니다.

<div id="1-website-workplace-setup" />

<Accordion title="1. 웹사이트 작업 공간 설정">

#### 모바일 사이트에 스마트 배너 최초 게재 준비하기

1. 앱스플라이어의 사이드 메뉴에서 **인게이지먼트** > **웹-투-앱** > **스마트 배너** > **스마트 배너로 이동**을 선택합니다.
2. **시작하기**를 클릭합니다. 설정 마법사가 필요한 단계(다음)를 안내합니다. 추가 웹 사이트 작업 공간을 설정하려면 아래를 참조하세요.
3. 웹사이트 작업 공간 이름을 입력합니다.
4. **생성**을 클릭합니다. 웹 사이트 작업 공간이 열립니다.
5. 배너 **코드 스니펫**을 복사합니다.
6. 웹사이트에 코드 스니펫을 구현하세요. 이 작업은 웹사이트당 한 번만 수행할 수 있습니다.
   * Google 태그 관리자, Adobe 태그 관리자, Shopify, Wix, Squarespace 또는 WordPress를 통해 웹 사이트에 코드를 추가하려면 <Anchor target="_blank" href="/marketers/ko/docs/smart-banners-website-code-implementation-for-marketers">마케터를 위한 스마트 배너 웹 사이트 코드 구현</Anchor>을 참조하세요.
   * 다른 플랫폼을 통해 코드를 추가하거나 필요에 따라 코드를 변경하려면(매개변수 추가, 딥 링크, 배너 숨기기 또는 PBA와 스마트 배너 통합 포함) <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2">개발자를 위한 스마트 배너 웹 사이트 코드 구현을</Anchor> 참조하세요.
7. [선택 사항] **웹 키를** 복사합니다. (이 키는 코드 조각의 일부로 이미 존재합니다.)
8. **계속**을 클릭합니다.

#### 웹사이트 워크플레이스 최초 생성하기

1. 앱스플라이어의 사이드 메뉴에서 **인게이지먼트** > **웹-투-앱** > **스마트 배너** > **스튜디오**를 선택합니다.
2. 옵션 메뉴를 클릭합니다.
3. **새 웹사이트 작업 공간**을 선택합니다.
4. 웹사이트 작업 공간 이름을 입력합니다.
5. **생성**을 클릭합니다. 웹 사이트 작업 공간이 열립니다.
6. 배너 **코드 스니펫**을 복사합니다.
7. 웹사이트에 코드 스니펫을 구현하세요. 이 작업은 웹사이트당 한 번만 수행할 수 있습니다.
   * Google 태그 관리자, Adobe 태그 관리자, Shopify, Wix, Squarespace 또는 WordPress를 통해 웹 사이트에 코드를 추가하려면 <Anchor target="_blank" href="/marketers/ko/docs/smart-banners-website-code-implementation-for-marketers">마케터를 위한 스마트 배너 웹 사이트 코드 구현</Anchor>을 참조하세요.
   * 다른 플랫폼을 통해 코드를 추가하거나 필요에 따라 코드를 변경하려면(매개변수 추가, 딥 링크, 배너 숨기기 또는 PBA와 스마트 배너 통합 포함) <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2">개발자를 위한 스마트 배너 웹 사이트 코드 구현을</Anchor> 참조하세요.
8. [선택 사항] **웹 키를** 복사합니다. (이 키는 코드 조각의 일부로 이미 존재합니다.)
9. **계속**을 클릭합니다.

</Accordion>

<div id="2-banner-group-setup" />

<Accordion title="2. 배너 그룹 설정">

배너 그룹에는 하나 이상의 배너가 포함됩니다. 여기서는 다음을 수행할 수 있습니다.

* 배너 그룹이 사용하는 OneLink 템플릿을 선택합니다. 여기에는 웹사이트 방문자를 리디렉션할 모바일 앱이 포함되어 있습니다.
* 특정 딥링킹 스킴을 설정합니다.
* 배너 그룹의 모든 배너에 사용되는 타겟팅 규칙, 일정, 동작 및 어트리뷰션 세부 정보를 정의합니다.
* 방문자가 특정 페이지에 도달했을 때 배너 그룹의 배너가 표시되도록 페이지를 설정합니다.

**배너 그룹을 설정하거나 복제하는 방법:**

1. 앱스플라이어의 사이드 메뉴에서 **인게이지먼트** > **웹투앱** > **스마트 배너**를 선택합니다.
2. **배너 그룹 최초 설정 방법**
   1. 왼쪽에서 **배너 그룹 추가**를 클릭합니다.
   2. 5단계 이후의 절차를 따르세요.
3. **배너 그룹을 추가로 설정하는 방법**
   1. **스튜디오** 탭으로 이동합니다.
   2. **+ 새로 만들기**를 클릭합니다.
   3. 5단계부터 절차를 따르세요.
4. **배너 그룹을 복제하려면**
   1. 삭제 아이콘 옆에 있는 **복제** 아이콘을 클릭합니다.
5. 고유한 **배너 그룹 이름**을 입력합니다. 배너 그룹 이름은 배너의 공통적인 주제(예: 광고하는 앱)를 반영해야 합니다.
6. 배너 그룹에 사용할 OneLink 템플릿을 선택합니다.
7. [선택 사항] 유니버설 링크 및 안드로이드 앱 링크 유저를 위한 대체 수단으로 배너 그룹에 대한 **URI 스킴**을 설정합니다. 기본적으로 OneLink 템플릿에서 값을 가져오기 때문에 이 값은 거의 필요하지 않습니다. 템플릿에 있는 값과 다른 값이 필요한 경우에만 배너 그룹에 대해 이 값을 설정합니다.
8. <span id="attributed-sources"></span>이 배너 그룹을 통해 유입되는 신규 인스톨에 대해 기여할 기본 및 폴백(대체) **어트리뷰션 소스(Attributed source)** 를 설정하십시오.   
    **클릭 ID 전달에 관한 참고사항:** FBCLID, GCLID, WBRAID, 및 GBRAID가 입력 URL에 포함되어 있는 경우, 자동으로 출력 URL로 전달됩니다. Google 클릭 ID의 경우, “keyword” 파라미터도 함께 발견되면, 해당 키워드 값을 af\_keywords의 값으로 출력 URL에 포함시킵니다.  

   다음 표를 사용하여 커스텀 링크에 가장 적합한 옵션을 선택하세요.

<div id="param-table" />

| 옵션 | 선택 시기 | 코멘트 |
| --- | --- | --- |
| **UTM 파라미터 사용** | 논오가닉 방문자가 UTM 파라미터가 있는 소스를 통해 모바일 웹사이트로 가장 많이 유입되는 시점을 선택합니다. | ◦ 미디어 소스 이름 (pid) = UTM\_Source   <br />◦ 캠페인 (c) = UTM\_campaign  <br />◦ UTM\_source 또는 UTM\_campaign이 누락된 경우 정적 이름이 대신 사용됩니다. |
| **유입되는 어트리뷰션 링크 파라미터 사용** | 논오가닉 방문자가 앱스플라이어 어트리뷰션 링크를 사용하는 클릭 애드 네트워크 통해 모바일 웹사이트로 가장 많이 유입되는 시점을 선택합니다. | ◦ 유입되는 앱스플라이어 어트리뷰션 링크에서 사용 가능한 모든 파라미터가 스마트 배너 링크에 추가됩니다.<br /><br />◦ 유입되는 앱스플라이어 어트리뷰션 링크와 스마트 배너에 파라미터가 존재하는 경우, 유입되는 파라미터가 최종 커스텀 링크에 우선적으로 적용됩니다. |
| **다른 어트리뷰션 파라미터 추가** | 원하는 경우 웹사이트 관련 어트리뷰션 데이터를 추가할 수 있습니다. 이를 통해 모든 설치에 대한 세분화된 분석이 가능합니다. | 예를 들어, 이커머스 사이트에서 모든 제품 카테고리 유형에 대해 af\_adset 값(예: "af\_adset=fruit")에 따라 다른 동일한 유저 지정 링크를 생성합니다. |
| **기본 어트리뷰션 파라미터 사용** | ◦ 선택 시기: ▪ 대부분의 모바일 웹사이트 방문자가 오가닉 방문자입니다. ▪ 논오가닉 방문자는 클릭 광고 네트워크나 UTM 파라미터가 있는 소스를 통해 웹사이트로 유입되지 않습니다. ◦유저는 파라미터 값을 사용자 지정할 수 있습니다. | **중요:** 미디어 소스, 캠페인 또는 채널 이름을 사용할 수 없는 경우 기본 스마트 배너 어트리뷰션 파라미터가 사용자 지정 링크에 대체로 사용되므로, UTM 또는 인커밍 어트리뷰션 링크 파라미터를 선택하는 것이 가장 좋습니다. |

9. [권장] 기본 어트리뷰션 파라미터 **채널 이름**을 설정하여 스마트 배너에서 발생하는 모든 설치를 지정된 채널로 어트리뷰션합니다. 이렇게 함으로써 여러 미디어 소스의 정보가 같은 채널에서 집계되어 **코호트 리포트**, **개요 대시보드**, **리텐션 리포트** 등의 형태로 나타납니다.
10. <span id="2-banner-group-setup-step10"></span>[선택 사항] 배너 그룹을 사용하여 유저가 배너를 클릭했을 때 집계된 리인게이지먼트를 기록하려면 **리타겟팅**을 설정하세요. 리타겟팅에 대해 자세히 알아보려면 리타게팅 어트리뷰션 가이드를 참조하십시오.

    > 🚧 **중요**
    >
    > 리타겟팅이 작동되려면 다음을 수행해야 합니다:
    >
    > * <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#앱에-대한-리타겟팅-활성화">앱 리타겟팅 활성화</Anchor>


    OneLink 기반 리타겟팅이 아닌 배너 링크(UA)를 클릭하는 기존 유저도 앱을 실행하고 동일한 사용자 경험을 갖게 됩니다. 하지만 리인게이지먼트는 일반 세션으로 기록되기 때문에 온드 미디어 캠페인의 성공 여부를 측정하는 것은 불가능합니다.
11. [선택 사항] **리타겟팅을 위해 활성 유저 무시**를 활성화시키고, 비활성 시간을 설정합니다. 이렇게 하면 스마트 배너 그룹 링크에 af\_inactivity\_window=[일수] 매개변수가 추가되고, 해당 기간 동안의 활성 유저는 리타겟팅에서 제외됩니다.
12. 리인게이지먼트 기간을 설정하여 유저의 인앱 이벤트가 리타겟팅 미디어 소스에 어트리뷰션되는 리인게이지먼트 이후의 기간을 결정합니다.
    * 값은 일(1&#126;90), 시간(최대 23시간) 또는 수명 단위로 설정할 수 있습니다.
    * 리인게이지먼트 기간은 af\_reengagement\_window 파라미터 링크에 추가됩니다.
13. <span id="dismissal-behaviour"></span>[선택 사항] **동작 해제**, 즉 유저가 그룹 내 한 배너를 해지한 후 동일한 배너가 유저에게 다시 표시될 때까지 허용되는 최소 시간을 설정합니다. 다음 중 하나를 선택하세요.
    * 시간별: 1시간, 1일 또는 1주일.
    * 다음 세션: 유저가 배너를 닫은 후 다른 탭이나 창에서 진행되는 세션을 의미합니다.
    * 다시 표시 안 함: 배너가 다시 표시되지 않습니다. **참고**:
      * 유저가 브라우저 캐시를 지우거나 비공개 브라우징 모드에서 사이트를 보는 경우 해제 동작 설정이 손실됩니다.
      * 동작 해제는 유저가 해제하는 배너에 적용되며, 배너 그룹의 다른 배너는 계속 표시할 수 있습니다.
14. [선택 사항] **주파수 제한**을 설정합니다.  빈도 제한은 배너 그룹의 각 배너가 고유한 유저에게 표시되는 횟수를 결정합니다. **제한 없음** (배너가 항상 표시되는 경우) 또는 **배너 표시 제한**을 선택할 수 있습니다.

    예를 들어 배너 그룹이 3개의 배너로 구성되어 있고 빈도 제한이 1개로 설정되어 있는 경우, 그룹의 각 배너는 유저당 한 번씩 표시됩니다. 이 시나리오에서 유저는 세 번 방문하면 그룹 내에서 세 개의 배너를 모두 보게 됩니다. 그러나 네 번째 방문부터는 더 이상 그룹에서 배너를 표시하지 않습니다. 횟수 제한을 2개로 설정하면 그룹의 각 배너는 유저당 두 번 표시되므로 그룹의 제한 횟수에 도달하려면 총 6번 방문해야 합니다.
15. [선택 사항] 배너를 표시할 **운영 체제**를 설정합니다.
    * 모든 모바일 운영 체제.
    * 안드로이드 또는 iOS.
16. [선택 사항] 배너 그룹 활성화 **예약**: 즉시 시작(기본값) 또는 시간 제한 캠페인을 설정합니다.
17. [선택 사항] 배너 그룹이 활성화되는 **위치**를 설정합니다.
    1. 모든 유저에게 이 배너 그룹을 표시하려면 **전 세계**를 선택합니다. 필요한 경우 다른 지역, 국가 또는 주에서 오는 방문자를 제외합니다.
    2. 하나 이상의 특정 위치에서 이 배너 그룹을 유저에게 표시하려면 **특정 위치** 선택 옵션을 선택합니다.
18. [선택 사항] **페이지에 표시**, 즉 배너 그룹을 방문자에게 표시할 수 있는 페이지를 설정합니다.
    * [기본 설정] 웹사이트의 **모든 페이지에 표시**합니다.  **참고**: 모든 페이지에 대한 폴백(fallback)으로 최소 하나 이상의 배너 그룹을 정의하는 것을 권장합니다.
    * **특정 페이지에 표시**: 배너를 표시하기 위해 페이지 또는 URL에 포함하거나 포함하지 말아야 할 내용을 지정합니다.
      * 둘 중 하나를 선택하실 수 있습니다.
        * **특정 페이지**: 배너를 표시할 페이지의 호스트 및/또는 경로를 지정합니다. 입력한 모든 쿼리는 무시됩니다. 예시: http://www.example.com/path?query
        * **URL 경로 및 쿼리**: 배너 표시 여부를 결정하는 경로 및/또는 검색어를 입력합니다. 예: path?query.  **참고**: [http://www.example.com/path?query](http://www.example.com/path?query)와 같은 전체 URL을 입력하지 마세요. 경로 및/또는 쿼리만 입력합니다.
      * ‘및/또는’을 사용하여 조건을 15개까지 추가할 수 있습니다.
      * 조건 간에 충돌이 있는 경우 배너가 표시되지 않습니다.
19. **배너 그룹 생성**을 클릭합니다.
20. [선택 사항] 배너 그룹을 다시 수정하려면 **타게팅 및 동작** 위에 커서를 가져가 **편집**을 클릭합니다.

> 📄 **예시**
>
> 마크는 'Feed Me’라는 음식 배달 서비스의 마케터입니다. 그는 앱에서 자두 판매를 위한 캠페인을 만들기로 결정합니다. 마크는 캠페인에 SMS뿐만 아니라 광고 네트워크와 구글을 사용하기로 결정했습니다.
>
> 캠페인애 대비하여 마크는 다음을 수행합니다.
>
> * 유입되는 링크 어트리뷰션 파라미터와 UTM 파라미터를 모두 사용하도록 선택합니다(수신 링크 또는 UTM 캠페인에서 발생하지 않은 클릭의 경우 기본 파라미터를 폴백으로 사용).
> * Feed Me 모바일 사이트의 자두 판매 페이지로 유저를 유도하기 위해 캠페인에서 사용할 고유 어트리뷰션 링크를 광고 네트워크에 제공합니다. 링크에는 자두 판매 페이지로 연결되는 URL과 함께 리디렉션 URL(af\_r) 매개변수가 포함되어 있습니다: `http://feedme.com/plums_link`.
> * "plums\_utm"이 포함된 모바일 웹 페이지를 방문하는 유저를 위한 Google Ads 캠페인을 준비합니다.
> * SMS의 경우, 캠페인 링크에 사용할 고유한 어트리뷰션 파라미터를 추가하여 유저를 피드미 모바일 사이트의 자두 세일 페이지로 유도합니다. 링크에는 자두 판매 페이지의 URL과 함께 pid 매개 변수가 포함되어 있습니다: `http://feedme.com/plums_link?pid=sms&c=plums`.
>
> 캠페인이 실행됩니다.
>
> 유저:
>
> * 자두 판매에 대한 광고를 보고 Feed Me 모바일 사이트를 클릭합니다.
> * Google Ads 클릭 및 기타 모든 클릭은 유입 링크 랜딩 페이지에 도착하고, 페이지별로 일치하는 스마트 배너가 활성화됩니다.
> * 모바일 사이트에서 스마트 배너를 찾아 클릭합니다.
> * Feed Me 앱으로 이동하여 다운로드하고 설치합니다.
> * 앱 실행 시 자두 세일로 바로 연결됩니다.
> * Feed Me 모바일 사이트로 유도한 올바른 미디어 소스에 기인합니다.

#### 타게팅 및 행동

타겟팅 및 행동 패널에는 해당 배너 그룹에 대해 구성한 설정이 표시됩니다. 이러한 설정을 수정하려면 수정 아이콘을 클릭합니다.

</Accordion>

<div id="3-banner-setup" />

<Accordion title="3. 배너 설정">

**배너 그룹에서 배너를 작성하는 방법:**

1. **새 배너**를 클릭하고 **배너 편집** 페이지로 들어갑니다.
2. 배너의 **이름**을 설정합니다.
3. **디자인 크리에이티브**를 생성합니다.
   1. **디자인 크리에이티브**를 클릭하여 배너의 광고 소재를 설정합니다.

      배너 템플릿을 선택할 수 있는 창이 열립니다.

      [![](https://files.readme.io/72baea2c6323742beb17761fdf8dc69048ada303db89855db8a60644ead3ad7f-34734678773649.png)](https://files.readme.io/72baea2c6323742beb17761fdf8dc69048ada303db89855db8a60644ead3ad7f-34734678773649.png)
   2. **크리에이티브 템플릿** 위로 마우스를 가져간 다음, **만들기를** 클릭하여 **크리에이티브** 설정 페이지로 들어갑니다.
   3. 스마트 배너 광고 소재의 모든 요소를 사용자 지정하는데, 이름으로 요소를 선택하거나 미리보기 이미지에서 클릭하면 됩니다. **참고:** 모든 템플릿에서 모든 요소를 사용할 수 있는 것은 아닙니다.
      * 제목
      * 설명
      * 평가
      * 종료 버튼
      * 행동 요청
      * 앱 로고
      * 배경
      * 배너 위치
      * 배너 패딩 (배너 크기 조정)
      * 장치 투명성
      * 이미지의 경우 jpeg, jpg, png 파일 형식 중 하나를 사용합니다.  **참고**: webp 형식은 지원되지 않습니다.   이미지 권장 사항은 다음과 같습니다. 

| 템플릿 유형 | 이미지 파일 최대 크기 | 이미지 비율 | 이미지 높이 | 이미지 너비 |
| --- | --- | --- | --- | --- |
| 최소 | 300 KB | 3:1 (너비 x 높이) | 70 픽셀 | 기기에 맞게 조정 |
| 표준 | 300 KB | 3:1 (너비 x 높이) | 70 픽셀 | 기기에 맞게 조정 |
| 향상 | 300 KB | 9:4 (너비 x 높이) | 110 픽셀 | 기기에 맞게 조정 |
| 다중 선택 | 300 KB | 9:4 (너비 x 높이) | 110 픽셀 | 기기에 맞게 조정 |
| 프로모션 | 300 KB | 4:5 (너비 x 높이) | 300 픽셀 | 기기에 맞게 조정 |
| 다중 선택 오버레이 | 300 KB | 9:4 (너비 x 높이) | 110 픽셀 | 기기에 맞게 조정 |
| 전면 광고 | 700 KB | 9:16 (너비 x 높이) | 기기에 맞게 조정 | 기기에 맞게 조정 |

   4. **검토**를 클릭하여 배너 광고 소재의 모양을 검토하고 다른 기기에서 해당 모양을 테스트합니다. **참고**: 배너는 활성 캠페인에서 미리보기 이미지와 약간 다르게 표시될 수 있습니다.
   5. 변경이 필요한 경우 **편집기로 돌아가기를** 클릭합니다.
   6. **완료**를 클릭하여 배너 설정 페이지로 돌아갑니다.
4. [선택 사항] 사용자 지정 어트리뷰션 파라미터를 추가합니다. 예: `ad_adset` 및 `af_ad` **참고**: `pid`, `c`, `channel` 매개 변수는 배너 그룹 수준에 속하므로 배너 수준에서는 추가할 수 없습니다.
5. 새 크리에이티브를 완성하고 저장하면 배너의 상태가 활성화됩니다. **상태** 토글을 사용하여 **활성 상태** 및 **일시 정지** 상태를 전환합니다.
6. **모두 저장**을 클릭하여 작업을 저장하거나 **모두 저장 후 닫기**를 클릭하여 작업을 저장하고 배너 설정 페이지를 닫습니다.

> 📄 **예시**
>
> 팁과 요령은 <Anchor target="_blank" href="https://drive.google.com/file/d/1mr6g3uNwlLw6UQ_WgtQZprJMhauw7Xi3/view?usp=sharing">스마트 배너 치트 시트</Anchor>를 참조하세요.

</Accordion>

<div id="4-testing" />

<Accordion title="4. 테스트">

크리에이티브가 준비되면 라이브로 설정하고 유저를 위해 활성화하기 **전에** 테스트해 볼 차례입니다.

**스마트 배너 크리에이티브 테스트 방법:**

**전제 조건:** 스마트 배너 코드 스니펫이 웹사이트에 통합되어 있는지 확인하세요.

1. **크리에이티브 테스트** 페이지에서 스마트 배너 SDK가 통합된 웹 페이지의 링크를 입력합니다 ([개발자용 스마트 배너](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2) 참조).
2. **생성**을 클릭합니다.
3. 생성된 링크를 복사하여 테스트 기기로 보내거나 테스트 기기로 QR 코드를 스캔합니다. **링크 또는 QR은 웹 페이지로 리디렉션되어 크리에이티브가 포함된 배너를 표시해야 합니다.**
4. 크리에이티브 **편집을** 클릭하여 크리에이티브 구성으로 돌아가거나 **완료**를 클릭하여 크리에이티브를 저장합니다.

</Accordion>

## 배너 성과 보기

성과 페이지에서 모든 배너의 성과를 확인하고 비교할 수 있습니다.

개별 성과 카드에서 특정 배너의 실적을 빠르게 확인할 수 있습니다.

배너 성과 데이터에는 다음이 포함됩니다.

* 노출 수
* 클릭 수
* 설치 수
* 리인게이지먼트
* 리어트리뷰션
* 클릭률(CTR). 공식: 클릭 수/노출 수 * 100
* 전환율(CVR). 공식: 어트리뷰션 수 / 클릭 수 * 100

**참고**:

* 데이터는 UTC 표준 시간대를 기준으로 합니다.
* 데이터 최신성은 <Anchor target="_blank" href="/marketers/ko/docs/about-data-freshness-and-timezone-support#continuous-aka-realtime">지속적으로</Anchor> 유지됩니다.
* 표시되는 데이터는 배너 및 OneLink 템플릿 별로 표시됩니다. 즉, 배너와 OneLink 템플릿이 둘 이상의 앱(예: Android 앱과 iOS 앱 모두)에 대해 구성된 경우 표시되는 실적 데이터는 둘 이상의 앱에 대한 것입니다.
* 뷰스루 어트리뷰션과 클릭 어트리뷰션이 모두 집계되기 때문에 CVR은 예상보다 높을 수 있으며, 때로는 100%를 초과하기도 합니다.

<div id="performance-page" />

<Accordion title="성과 페이지">

성과 페이지에서는 모든 스마트 배너의 지난 90일까지의 실적 데이터를 확인하고 비교할 수 있습니다.

**성과 페이지 보는 방법**:

1. 앱스플라이어의 사이드 메뉴에서 **인게이지먼트** > **웹투앱** > **스마트 배너** > **퍼포먼스를** 선택합니다.
2. 성과를 확인할 날짜 범위를 선택합니다. 기본 날짜 범위는 최근 7일입니다.
3. [선택 사항] **현재 활성 배너만 표시**를 선택합니다. 이 기능을 선택할 경우, 일시 중지되었거나 현재 활성화되어 있지 않은 배너의 데이터는 선택한 날짜 범위 동안 활성화되어 있더라도 표시되지 않습니다. 선택한 날짜 범위에 대한 성과 데이터가 표시됩니다.

</Accordion>

<div id="performance-cards" />

<Accordion title="성과 카드">

특정 배너에 대한 지난 7일간의 실적 데이터를 확인할 수 있습니다.

**배너 성과 확인 방법**:

1. 앱스플라이어의 사이드 메뉴에서 **인게이지먼트** > **웹투앱** > **스마트 배너** > **스튜디오를** 선택합니다.
2. 성과를 보려는 웹사이트 작업 공간 및 배너 그룹을 선택합니다.
3. 배너 그룹에 있는 배너 위로 마우스를 가져갑니다. 지난 한 주 동안의 실적 데이터가 표시됩니다.

</Accordion>

## 추가 정보

<div id="banner-group-display-logic" />

<Accordion title="배너 그룹 표시 논리">

앱스플라이어는 스마트 배너를 표시할지 여부를 결정할 때 다음 사항을 고려합니다.

* 배너 그룹에 대해 설정된 규칙(해제 동작, 빈도 제한, 위치, 페이지에 표시 등)이 있나요?
* 최종 유저가 규칙 조건을 충족하고 배너를 표시할 자격이 있나요?

두 질문에 모두 '예'로 답하면, 즉 규칙이 있고 유저가 배너를 볼 자격이 있는 경우, 앱스플라이어는 다음 표에 설명된 대로 표시할 배너를 선택합니다.

| 배너 그룹 설정 | 표시되는 배너 | 예시 |
| --- | --- | --- |
| 단일 배너 그룹 | 앱스플라이어는 모든 배너 그룹에 있는 모든 활성 배너를 모든 적격 유저에게 균등하게 분할하여 표시합니다. | •예시 1: 활성 배너가 1개 있습니다. 이는 모든 유저에게 표시됩니다.<br /><br />•예시 2: 배너가 2개 있습니다. 50%의 사용자는 배너 1을 보고 나머지 50%는 배너 2를 봅니다.<br /><br />•예시 3: 배너가 3개가 있으며, 적격 사용자의 1/3이 각 배너를 볼 수 있습니다.<br /><br />•예시 4: 활성 배너가 없습니다. 아무것도 표시되지 않습니다. |
| 동일한 규칙을 가진 여러 배너 그룹 | 앱스플라이어는 모든 배너 그룹에 있는 모든 활성 배너를 모든 적격 유저에게 균등하게 분할하여 표시합니다. | 배너 그룹은 2개(A, B)이며, 각각 3개의 배너가 있습니다(총 6개의 배너). 적격 사용자의 1/6이 각 배너를 확인합니다. |
| 여러 규칙이 있는 다중 배너 그룹 | 앱스플라이어는 *가장 구체적으로 설명하고 유저와 일치하는 규칙이 있는 배너 그룹에서* 모든 활성 배너의 표시를 균등하게 분할합니다. 배너 그룹이 서로 다른 방식으로 동일하게 특정하면 모든 배너 그룹의 배너가 표시됩니다. | •예시 1: 배너 그룹 A는 전 세계에, 배너 그룹 B는 일본에 표시되도록 설정되어 있습니다. 배너 그룹 B는 더 구체적이므로 해당 그룹의 배너만 일본 내 사용자에게 표시됩니다. 그룹에 활성 배너가 없는 경우 아무것도 표시되지 않습니다.<br /><br />•예시 2: 배너 그룹 A는 전 세계에 표시되도록 설정하고 배너 그룹 B는 우크라이나를 제외한 모든 곳에 표시되도록 설정합니다. 배너 그룹 B는 더 구체적이므로 해당 그룹의 배너만 전 세계 사용자(우크라이나 사용자 제외)에게 표시됩니다. 배너 그룹 B에 활성 배너가 없는 경우 아무것도 표시되지 않습니다. 우크라이나에 배너 그룹 A가 표시됩니다.<br /><br />•예시 3: 배너 그룹 A와 B 두 가지가 있으며, 배너 그룹 A는 일본에서, 배너 그룹 B는 4월에 공개될 예정입니다. 두 배너 그룹은 똑같이 구체적이지만 방식은 다릅니다. 따라서 일본에서는 4월에 두 배너 그룹의 배너가 모두 표시되며, 어느 배너 그룹도 다른 배너 그룹보다 우선순위가 없습니다. |

</Accordion>

<div id="ab-testing-banner-performance" />

<Accordion title="배너 성능 A/B 테스트">

실적 대시보드에서 배너의 실적을 비교하여 배너를 A/B 테스트할 수 있습니다. 추가 어트리뷰션 관련 데이터는 `af_adset`, `af_ad` 또는 기타 어트리뷰션 파라미터( `pid`, `c`, `channel` 제외)를 각 배너 크리에이티브 또는 배너 그룹에 고유 값으로 추가하는 것을 권장합니다. 앱스플라이어 대시보드 및 보고서에서 데이터를 볼 때 이러한 매개변수를 사용하여 각 배너 그룹의 성과를 비교할 수 있습니다.

</Accordion>

## 자주 묻는 질문(FAQ)

<div id="why-does-my-banner-not-display" />

<Accordion title="내 배너가 표시되지 않는 이유는 무엇인가요?">

이유는 배너 그룹에 설정된 빈도 제한 때문입니다. 빈도 제한은 고유 사용자에게 배너가 표시되는 횟수를 결정합니다. 예를 들어 빈도 제한이 3회로 설정되어 있고 사용자가 사이트를 네 번 방문하면, 처음 세 번 방문 시에는 배너가 표시되지만 네 번째 이후에는 배너가 표시되지 않습니다. 빈도 제한을 비활성화할 수 있습니다. 빈도 제한 값을 선택하거나 빈도 제한을 비활성화합니다.

</Accordion>

<div id="can-i-use-my-own-font-for-my-banner" />

<Accordion title="배너에 내 글꼴을 사용할 수 있나요?">

예. [개발자 허브의 지침에](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#control-smart-banner-font) 따라 웹사이트에서 배너에 사용할 글꼴을 직접 설정할 수 있습니다.

* 웹사이트 개발자가 구현해야 합니다.
* 이 글꼴은 웹사이트의 모든 배너와 배너 내부의 모든 텍스트 요소에 적용됩니다.
* 글꼴은 크리에이티브 편집기에서 볼 수 없습니다.
* 구현한 후 [크리에이티브 배너를 테스트](/docs/smart-banners-mobile-web-to-app-for-marketers#4-testing)합니다.
* 글꼴이 올바르게 표시되지 않으면 [크리에이티브 편집기에서](/docs/smart-banners-mobile-web-to-app-for-marketers#3-banner-setup) 배너를 다시 저장하세요.

</Accordion>

<div id="can-i-add-parameters-to-the-url-of-my-smart-banners" />

<Accordion title="스마트 배너의 URL에 매개 변수를 추가할 수 있나요?">

예, 스마트 스크립트에서 다음 두 함수를 호출하면 됩니다.

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#showbanner">showBanner</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#updateparams">updateParams</Anchor>

</Accordion>

<div id="do-smart-banners-support-deep-linking" />

<Accordion title="스마트 배너가 딥링킹을 지원합나요?">

예. 다음 방법 중 하나로 <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">deep\_link\_value 매개 변수를</Anchor> 추가합니다.

* 앱스플라이어 UI에서 [배너 설정](/docs/smart-banners-mobile-web-to-app-for-marketers#3-banner-setup)하는 동안 정적 사용자 지정 어트리뷰션 파라미터를 추가합니다.
* 배너를 표시하기 전에 URL에 매개변수를 추가하려면 [showBanner](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#showbanner%20target=) 함수에서 additionalParams를 사용합니다.
* 배너가 표시된 후 URL에 매개변수를 추가하려면 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#updateparams">updateParams</Anchor> 함수를 사용합니다.

개발자가 deep\_link\_value의 원하는 동작을 구현하는지 확인하세요.

</Accordion>

<div id="can-smart-banners-show-different-content-based-on-whether-or-not-users-have-the-app-installed" />

<Accordion title="스마트 배너는 사용자가 앱을 설치했는지 여부에 따라 다른 콘텐츠를 표시할 수 있나요?">

아니오. 사용자가 앱을 설치했는지 여부를 모르는 경우에는 두 가지 모두에 적용 가능한 클릭 유도 문안을 만드는 것이 좋습니다. 예: "앱으로 이동" 또는 "앱 열기."

</Accordion>

<div id="do-original-incoming-url-parameters-remain-available-for-the-smart-banner-url-when-users-navigate-away-from-and-then-return-to-the-banners-landing-page" />

<Accordion title="사용자가 배너의 랜딩 페이지에서 다른 곳으로 이동했다가 다시 돌아올 때 스마트 배너 URL에 원래의 인커밍 URL 파라미터를 계속 사용할 수 있나요?">

예. 원본 수신 URL에 utm\_source 또는 pid 매개변수가 포함된 경우 원본 URL은 브라우징 세션 기간 동안 저장되고 해당 매개변수는 발신 배너 URL에 적용됩니다.

</Accordion>

<div id="can-i-set-my-banners-to-display-on-my-mobile-site-but-not-on-my-wrapperhybrid-app" />

<Accordion title="모바일 사이트에는 배너가 표시되지만 래퍼/하이브리드 앱에는 표시되지 않도록 설정할 수 있나요?">

예. 그러기 위해서 래퍼/하이브리드 앱에서 스마트 배너를 구현하고 웹 브라우저가 아닌 앱에서 배너 페이지를 로드할 때 배너를 앱에 표시하는 [showBanner](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#showbanner%20target=) 함수를 사용하지 마십시오. 대신, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#hidebanner">hideBanner</Anchor> 함수를 사용합니다.

</Accordion>

<div id="do-smart-banners-support-web-accessibility" />

<Accordion title="스마트 배너는 웹 접근성을 지원하나요?">

당사는 장애인을 포함한 모든 사용자가 스마트 배너에 완전히 액세스하고 참여할 수 있도록 최선을 다하고 있습니다.

따라서 당사는 스마트 배너 요소에 관련 HTML 속성을 제공하여 스마트 배너가 웹 접근성과 호환되도록 노력하고 있으며 WCAG 2.1 표준 모범 사례를 따르고 있습니다.

그러나 이러한 스마트 배너의 사용 목적에 맞는 접근성 요구 사항을 결정하는 것은 전적으로 귀하의 책임입니다. 귀사가 사용하는 스마트 배너가 관련 웹 접근성 요구 사항에 따라 모든 사용자가 계속 액세스할 수 있도록 할 책임은 전적으로 회원님에게 있습니다.

스마트 배너에 대한 다양한 변경 사항은 관련 접근성 요구 사항과의 호환성에 영향을 미칠 수 있습니다(예: 내부 배너 요소의 색상 및 크기 편집).

</Accordion>

<div id="if-a-smart-banner-is-deleted-from-a-banner-group-will-the-data-associated-with-that-banner-group-also-be-removed" />

<Accordion title="스마트 배너가 배너 그룹에서 삭제되면 해당 배너 그룹과 관련된 데이터도 삭제됩니까?">

아니요. 스마트 배너가 삭제되더라도 귀속 데이터는 삭제되지 않습니다.

</Accordion>

## 문제 해결 & 특성 및 제한 사항

| 특징 | 비고 |
| --- | --- |
| 배너 표시 분할 | 앱스플라이어는 사용자에게 활성 배너를 균등하게 분할하여 표시합니다. 특정 배너를 더 많이 또는 적게 표시할지 여부를 선택할 수는 없습니다. 예를 들어, 그룹에 배너가 2개 있는 경우 각각 50%의 사용자에게 표시됩니다. 70%-30% 분할로 변경할 수 없습니다. |
| 사용자 지정 파라미터 | •사용자 지정 파라미터에는 다음 특수 문자가 허용되지 않습니다: ;, *, !, @, #, ?, $, ^, :, &, ~, \`, =, +, ', >, &lt;, / • 이러한 특수 문자 중 하나를 사용하여 매개변수를 정의하는 경우 해당 매개변수는 저장되지 않습니다. |
| 이름 변경 | 배너 그룹 이름과 배너 이름은 변경할 수 있습니다. 성과 데이터는 이에 영향을 받지 않으며 넘어갑니다. |
| 버튼 클릭/닫기 수 | 배너를 클릭했지만 닫은 사용자 수를 측정하는 기능은 지원되지 않습니다. |
| 특정 페이지 | 특정 페이지에 배너를 표시하도록 배너 그룹을 설정하면 입력한 호스트/경로에만 배너 규칙이 적용됩니다. 완벽하게 일치하지 않는 경우 (예: 사이트 페이지에 규칙 설정에 포함되지 않은 추가 문자열이 있는 경우) 규칙이 적용되지 않습니다. |
| 태블릿 | • 스마트 배너는 모바일 장치용으로 설계되었으며 해상도가 대형 화면이 있는 태블릿에 최적화되지 않을 수 있습니다. 태블릿의 브라우저는 모바일 기기로 인식되지 않을 수 있습니다. |
| 배너는 빈 영역 옆에 표시됩니다 | 이 동작이 발생하면 다음 기준을 사용하여 원인을 평가합니다.<ul><li>SDK 코드 스니펫이 웹 페이지에서 두 번 이상 구현되지 않았는지 확인합니다.</li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#showbanner">`showBanner`</Anchor> 함수가 여러 번 적용되지 않았는지 확인합니다.</li></ul> |

<div data-zendesk-anchors="h_01HB5W700P3GP7JS4PFDF65EWT=%EC%B0%B8%EA%B3%A0 smart-banners=%EC%8A%A4%EB%A7%88%ED%8A%B8-%EB%B0%B0%EB%84%88 h_01HB5W700PWY5G45BYNWPKAC52=%EC%8A%A4%EB%A7%88%ED%8A%B8-%EB%B0%B0%EB%84%88 h_01HB5W700QQMYSEFBBXVJ97M0M=%EC%98%88%EC%8B%9C h_01HB5W700QGWTWDXBNB2GAPQ3B=%EC%A4%91%EC%9A%94 setup=%EC%84%A4%EC%A0%95 h_01HB5W700QVNYJT48VAP9Y7HQS=%EC%84%A4%EC%A0%95 h_01HB5W700Q7G5E98V0DBN9P5VZ=1-website-workplace-setup prepare-your-mobile-site-to-display-smart-banners-for-the-first-time=%EB%AA%A8%EB%B0%94%EC%9D%BC-%EC%82%AC%EC%9D%B4%ED%8A%B8%EC%97%90-%EC%8A%A4%EB%A7%88%ED%8A%B8-%EB%B0%B0%EB%84%88-%EC%B5%9C%EC%B4%88-%EA%B2%8C%EC%9E%AC-%EC%A4%80%EB%B9%84%ED%95%98%EA%B8%B0 h_01HB5W700QE7MDBSN5GH4E7ABR=%EB%AA%A8%EB%B0%94%EC%9D%BC-%EC%82%AC%EC%9D%B4%ED%8A%B8%EC%97%90-%EC%8A%A4%EB%A7%88%ED%8A%B8-%EB%B0%B0%EB%84%88-%EC%B5%9C%EC%B4%88-%EA%B2%8C%EC%9E%AC-%EC%A4%80%EB%B9%84%ED%95%98%EA%B8%B0 to-create-website-workplaces-after-the-first-time=%EC%9B%B9%EC%82%AC%EC%9D%B4%ED%8A%B8-%EC%9B%8C%ED%81%AC%ED%94%8C%EB%A0%88%EC%9D%B4%EC%8A%A4-%EC%B5%9C%EC%B4%88-%EC%83%9D%EC%84%B1%ED%95%98%EA%B8%B0 h_01HB5W700Q57WXKFSWXNF22QZ1=%EC%9B%B9%EC%82%AC%EC%9D%B4%ED%8A%B8-%EC%9B%8C%ED%81%AC%ED%94%8C%EB%A0%88%EC%9D%B4%EC%8A%A4-%EC%B5%9C%EC%B4%88-%EC%83%9D%EC%84%B1%ED%95%98%EA%B8%B0 h_01HB5W700QY1FH2SYX6DM4HDEQ=2-banner-group-setup h_01HDH1BQSXCQV9QCJGZ4VNXGPQ=%EC%A4%91%EC%9A%94-1 h_01HB5W700QYJ9NR5F4VT59NG2Q=%EC%98%88%EC%8B%9C-1 targeting-behavior=%ED%83%80%EA%B2%8C%ED%8C%85-%EB%B0%8F-%ED%96%89%EB%8F%99 h_01HB5W700QYC48YTJY9B8JT0XM=%ED%83%80%EA%B2%8C%ED%8C%85-%EB%B0%8F-%ED%96%89%EB%8F%99 h_01HB5W700QG54YYQFHGA2J41RY=3-banner-setup h_01HB5W700QD0WKNAP5X6T9E6DQ=%EC%98%88%EC%8B%9C-2 h_01HB5W700QX5J59BBK1AV7VFV6=4-testing view-banner-performance=%EB%B0%B0%EB%84%88-%EC%84%B1%EA%B3%BC-%EB%B3%B4%EA%B8%B0 h_01HB5W700Q6WHMVFNSVM2E9JXN=%EB%B0%B0%EB%84%88-%EC%84%B1%EA%B3%BC-%EB%B3%B4%EA%B8%B0 h_01HB5W700QEP46WV78KEYD1RT1=performance-page h_01HB5W700QZ705H5EE0PFHB1KY=performance-cards additional-information=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01HB5W700Q9XD8MGEK0B3ZZJS3=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01HB5W700QHW078W3RRCB81AWM=banner-group-display-logic h_01HB5W700QNYT482FR0FRHP2DC=ab-testing-banner-performance faq=%EC%9E%90%EC%A3%BC-%EB%AC%BB%EB%8A%94-%EC%A7%88%EB%AC%B8faq h_01HB5W700Q90F1KMASF94EZWEM=%EC%9E%90%EC%A3%BC-%EB%AC%BB%EB%8A%94-%EC%A7%88%EB%AC%B8faq h_01HB5W700Q1ZP3RAR94T41SXK2=why-does-my-banner-not-display h_01HB5W700QKBVFQHH9D8WD36R2=can-i-use-my-own-font-for-my-banner h_01HB5W700R2AJC2C1PRT5PTH8G=can-i-add-parameters-to-the-url-of-my-smart-banners h_01HB5W700RAVG10QZDBPXWT14G=do-smart-banners-support-deep-linking h_01HB5W700R12DSA6HF4HVWGW9P=can-smart-banners-show-different-content-based-on-whether-or-not-users-have-the-app-installed h_01HB5W700RT122T2M6NXFPSXDV=do-original-incoming-url-parameters-remain-available-for-the-smart-banner-url-when-users-navigate-away-from-and-then-return-to-the-banners-landing-page h_01HB5W700RH40FGHWVJ9J31R9F=can-i-set-my-banners-to-display-on-my-mobile-site-but-not-on-my-wrapperhybrid-app h_01HB5W700R11SHAKV5W21MXCX8=do-smart-banners-support-web-accessibility h_01JSVH17EH97S8B7EBCD4QHS1Q=if-a-smart-banner-is-deleted-from-a-banner-group-will-the-data-associated-with-that-banner-group-also-be-removed traits-and-limitations=%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0--%ED%8A%B9%EC%84%B1-%EB%B0%8F-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD h_01HB5W700RXHC22QGXDX4GG1AR=%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0--%ED%8A%B9%EC%84%B1-%EB%B0%8F-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD" />
