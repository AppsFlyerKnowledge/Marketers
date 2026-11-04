---
title: Firebase 동적 링크에서 앱스플라이어로 마이그레이션
metadata:
  keywords:
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2023-06-19T09:27:37Z'
  edited_at: '2026-10-14T10:32:45Z'
  id: 16282289097105
  locale: ko
  section: Marketer onboarding
  section_id: 6550866490129
  url: https://support.appsflyer.com/hc/ko/articles/16282289097105
---
> **한눈에 보기:**



<div id="migrate-from-firebase-to-appsflyer" />

<div id="about-the-migration" />

## Firebase에서 앱스플라이어로 마이그레이션하는 방법

**필수 조건**

* Firebase의 동적 링크
* 앱 개발자

<div id="step-1-create-an-appsflyer-account" />

<Accordion title="3단계: 앱스플라이어 계정 만들기">

* <Anchor target="_blank" href="https://www.appsflyer.com/get-started/">앱스플라이어 계정을 만듭니다</Anchor>.
* <Anchor target="_blank" href="/marketers/ko/docs/user-management">적절한 권한이 있는 계정 사용자 추가</Anchor>

</Accordion>

<div id="step-2-add-your-app" />

<Accordion title="3단계:">

* [선택 사항] 활성 사용자 정의에 맞게 기본 90일 리어트리뷰션 기간을 변경합니다.

추가

</Accordion>

<div id="step-3-create-a-onelink-template" />

<Accordion title="3단계:">

링크 및 최종 사용자 경험을 만들기 위해 템플릿이 필요합니다.

* <Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template#원링크-템플릿-만들기">원링크 템플릿 만들기</Anchor>
  * <Anchor target="_blank" href="/marketers/ko/docs/user-management">마케터는 앱스플라이어 관리자이거나</Anchor> 원링크 템플릿을 추가/수정할 수 있는 권한이 있어야 합니다.

</Accordion>

<div id="step-4-set-up-the-appsflyer-sdk" />

<Accordion title="3단계:">

앱에 연동된 앱스플라이어 SDK는 앱과 앱스플라이어 플랫폼 간의 링크입니다. 이 링크는 다음을 제공합니다.

* 딥링킹 - SDK를 통해 통합 딥링킹(UDL)을 구현할 수 있습니다.
* 어트리뷰션 - SDK는 앱 설치, 앱 열기, 인앱 이벤트 등을 보고합니다.

아래 단계에 따라 앱에 앱스플라이어 SDK를 연동하세요.

<div id="appsflyer-sdk-integration-steps" />

#### 앱스플라이어 SDK 연동 단계

1. 앱에 앱스플라이어 SDK를 연동합니다.  
   <Anchor target="_blank" href="/marketers/ko/docs/sdk-integration-overview">안드로이드</Anchor> 및 iOS SDK 연동에 대해서는 안내서를 참조하십시오.
2. 앱스플라이어 스킴을 사용하여 기록하려는 인앱 이벤트를 매핑합니다.  
   이것은 <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview">SDK</Anchor> 또는 <Anchor target="_blank" href="/marketers/ko/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor>를 통해 수행할 수 있습니다.
3. Firebase의 SDK를 처리합니다.  
   이 작업을 앱스플라이어로만 전환하거나 몇 주 동안 두 SDK를 동시에 실행할 수 있습니다. 아래 표에서 옵션에 대한 분석을 확인하세요.  

| 옵션 | 업데이트된 앱 버전 출시 후   <br />변경되는 사항 | 영향 |
| --- | --- | --- |
| Firebase SDK 삭제(권장) | 앱스플라이어만이 신규 설치 및 업데이트 사용자를 기록합니다.  <br />사용자가 앱을 업데이트할 때까지 Firebase는 사용자가 수행한 이벤트를 계속 표시합니다. | <ul><li>빠른 전환</li><li>이중 어트리뷰션 없음</li><li>Firebase SDK가 아직 남아 있는 앱 버전이 있는지 확인 가능</li></ul> |
| 전환 기간 동안 Firebase SDK 유지 | 앱스플라이어와 Firebase는 신규 설치 및 보고 이벤트의 어트리뷰션을 제공합니다. 추후에 Firebase SDK를 제거하세요. | <ul><li>데이터 유효성 검증 가능. 즉, 앱스플라이어와 Firebase의 데이터를 비교할 수 있음</li><li>이중 어트리뷰션으로 인해 애드 네트워크에 이중 비용 발생</li><li>업무량 증가</li></ul> |

4. 작업 범위에 있는 다른 모든 작업이 완료된 후, 앱스플라이어 SDK를 사용하여 앱 버전을 시장에 업데이트합니다. 신규 사용자는 앱스플라이어에 의해 어트리뷰션됩니다.   
   **참고**:
   * iOS, 구글 플레이, 그리고 모든 관련 안드로이드 아웃스토어 마켓에 사용할 앱을 업데이트해야 합니다.
   * 안드로이드 앱이 비공식 APK 사이트에 존재할 수도 있습니다(웹에서 앱의 패키지 이름을 검색하여 확인). APK 사이트는 최신 버전으로 업데이트할 때까지 다소 시간이 걸리므로, 앱스플라이어 SDK가 없는 구 버전을 인스톨하는 오가닉 유저가 유입될 수 있습니다.
   * 앱스토어에서 앱 업데이트가 완전히 반영되기까지 며칠이 걸릴 수도 있습니다. 이 기간 동안에 앱을 설치한 사용자에게는 이전 버전이 계속 제공될 수 있습니다.

</Accordion>

<div id="step-5-understand-parameter-mapping" />

<Accordion title="3단계:">

Firebase 동적 링크 파라미터가 앱스플라이어의 해당 파라미터에 어떻게 매핑되는지 이해합니다.

해당 파라미터를 올바르게 매핑하고 이해하면 링크에서 동일한 결과를 얻을 수 있습니다.

아래 표에는 Firebase의 모든 파라미터와 해당 앱스플라이어 파라미터가 나열되어 있습니다.

이 표를 앱스플라이어로 마이그레이션할 때 현재 사용하는 모든 파라미터에 대한 참조로 사용하세요.

<div id="note" />

> 📘 **참고**
>
> Firebase 파라미터가 목록에 없다면, 링크에 파라미터를 넣을 필요 없이 앱스플라이어가 원링크 템플릿 설정에서 이를 처리하기 때문입니다.

<table><thead><tr><th>그룹화</th><th>Firebase</th><th>앱스플라이어</th><th>설명</th></tr></thead><tbody><tr><td>모바일 파라미터</td><td>link</td><td><ul><li>af_dp</li><li>딥 링크 값</li></ul></td><td><ul><li> <strong>af_dp - iOS 및 안드로이드 앱을 실행하기 위한 대체 방법으로 사용되는 URI 스킴입니다.</strong> </li><li> <strong>deep_link_value</strong>- 사용자가 연결될 특정 인앱 콘텐츠의 값 이름입니다.</li></ul></td></tr><tr><td> <br/>안드로이드 파라미터</td><td>afl</td><td>af_android_url</td><td></td></tr><tr><td rowspan="2">iOS 파라미터<br/><br/> </td><td>ifl</td><td>af_ios_url</td><td></td></tr><tr><td>efr</td><td>af_force_deeplink</td><td>af_dp URI 스킴을 사용하여 iOS 앱을 강제로 열 때 사용됩니다. 이 기능이 없으면 앱이 URI 스킴을 사용하여 열 수 없습니다.</td></tr><tr><td>기티 플랫폼 URL</td><td>ofl</td><td>af_web_dp</td><td></td></tr><tr><td rowspan="3"> <br/>소셜 태그<br/><br/> </td><td>st</td><td>af_og_title</td><td>소셜미디어에서 공유된 콘텐츠의 제목을 사용자 지정하는 데 사용됩니다.</td></tr><tr><td>sd</td><td>af_og_description</td><td>소셜미디어에서 공유 콘텐츠의 설명을 사용자 지정하는 데 사용됩니다.</td></tr><tr><td>si</td><td>af_og_image</td><td>소셜미디어에서 공유 콘텐츠의 이미지를 사용자 지정하는 데 사용됩니다.</td></tr><tr><td rowspan="5"><p>분석 파라미터 <br/><br/><br/><br/> </p></td><td>utm_source</td><td>pid</td><td>미디어 소스</td></tr><tr><td>utm_medium</td><td>af_채널</td><td>광고가 게재되는 미디어소스 채널을 식별합니다.</td></tr><tr><td>utm_campaign</td><td>c</td><td>캠페인 이름</td></tr><tr><td>utm_term</td><td>af_키워드</td><td>텍스트 타겟 캠페인을 위한 키워드 목록</td></tr><tr><td>utm_content</td><td>af_adset</td><td>캠페인과 관련된 광고 모음</td></tr></tbody></table>

</Accordion>

<div id="step-6-create-onelink-links-with-mapped-parameters" />

<Accordion title="3단계:">

매핑된 파라미터를 사용하여 원링크 템플릿에 원링크 링크를 생성할 수 있습니다.

다음 표를 참조하여 사용 목적에 가장 적합한 방법을 결정하세요.

| Firebase | 앱스플라이어 | 다음과 같은 경우에 사용 | 참고 |
| --- | --- | --- | --- |
| Firebase 콘솔 | <Anchor target="_blank" href="/marketers/ko/docs/onelink-guide">원링크 관리 페이지</Anchor> | 원링크 링크를 하나씩 만들고 싶을 때, 이 방식으로 원링크의 전체 기능과 가능성을 활용할 수 있음 |  |
| 동적 링크 빌더 API | <Anchor target="_blank" href="/marketers/ko/docs/user-invite-attribution">SDK</Anchor> | 사용자 초대 및 추천 등의 용도로 인앱 프로그래밍 방식으로 생성된 링크를 생성하려는 경우 | <ul><li>iOS 또는 안드로이드 개발자 필요</li></ul> |
| Firebase REST API | <Anchor target="_blank" href="/marketers/ko/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">원링크 API로 대규모 캠페인을 위한 링크 생성하기</Anchor> | 모바일 앱 외부에서 프로그래밍 방식으로 링크를 생성하려는 경우 | <ul><li>개발자 필요</li><li>무료 플랜에서 사용 불가</li></ul> |
| 수동 링크 구축 | <Anchor target="_blank" href="/marketers/ko/docs/understand-onelink-short-vs-long-urls">긴 링크</Anchor> | 쿼리 파라미터를 사용하여 링크를 수동으로 구성하려고 함. 짧은 링크가 필요하지 않은 경우 사용 버튼 또는 배너 뒤에 링크가 있는 경우 등 |  |
|  | <Anchor target="_blank" href="/marketers/ko/docs/perform-onelink-bulk-actions-via-csv">대량 링크</Anchor> | 모든 Firebase 동적 링크를 앱스플라이어로 일괄 마이그레이션하고 싶은 경우<br /><br />오류 없이 모든 링크를 빠르게 이동하려면 이 방법을 권장 | <ul><li>[해당 Firebase 파라미터에 따라 링크 파라미터 키와 값을 매핑하는 사전 단계 필요](/docs/migrate-from-firebase-dynamic-links-to-appsflyer#map-parameters)</li><li>무료 플랜에서는 사용 불가</li></ul> |
|  | <Anchor target="_blank" href="/marketers/ko/docs/smart-banners-mobile-web-to-app-for-marketers">스마트 배너</Anchor> |  |  |
|  | <Anchor target="_blank" href="/marketers/ko/docs/set-up-smart-script-to-convert-web-visitors">스마트 스크립트</Anchor> | 웹투앱 경험을 위해 웹 페이지에서 긴 링크를 동적으로 구성하려는 경우 |  |

</Accordion>

<div id="see-also" />

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/brand-onelink-with-your-domain">브랜드 도메인</Anchor>
> * <Anchor target="_blank" href="/marketers/ko/docs/using-firebase-and-google-tag-manager-with-appsflyer-overview">앱스플라이어와 함께 Firebase 및 구글 태그 관리자 사용 - 개요</Anchor>

<div data-zendesk-anchors="overview=firebase%EC%97%90%EC%84%9C-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EB%A1%9C-%EB%A7%88%EC%9D%B4%EA%B7%B8%EB%A0%88%EC%9D%B4%EC%85%98%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 how-to-migrate-from-firebase-to-appsflyer=firebase%EC%97%90%EC%84%9C-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EB%A1%9C-%EB%A7%88%EC%9D%B4%EA%B7%B8%EB%A0%88%EC%9D%B4%EC%85%98%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 h_01J7ZPPQ340PNQ70FZAQY4GBZ1=firebase%EC%97%90%EC%84%9C-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EB%A1%9C-%EB%A7%88%EC%9D%B4%EA%B7%B8%EB%A0%88%EC%9D%B4%EC%85%98%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 01H8K961JHRXNQHBVN930XW70Q=firebase%EC%97%90%EC%84%9C-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EB%A1%9C-%EB%A7%88%EC%9D%B4%EA%B7%B8%EB%A0%88%EC%9D%B4%EC%85%98%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 01H8K961JHCK0Z4GTTHCAKF98E=firebase%EC%97%90%EC%84%9C-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EB%A1%9C-%EB%A7%88%EC%9D%B4%EA%B7%B8%EB%A0%88%EC%9D%B4%EC%85%98%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 h_01J5QWWGWGDBEF8RY3DZ5XAN3G=step-1-create-an-appsflyer-account h_01J5QWWGWGN17673GYFZWPNKQR=step-2-add-your-app h_01J5QWWGWGKJPRCG9N93B8KBYW=step-3-create-a-onelink-template h_01J5QWWGWGCQFHBQ9EC0QTPF4S=step-4-set-up-the-appsflyer-sdk appsflyer-sdk-integration-steps=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-sdk-%EC%97%B0%EB%8F%99-%EB%8B%A8%EA%B3%84 h_01J5QXST2K890DV7QS6S9K3A01=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-sdk-%EC%97%B0%EB%8F%99-%EB%8B%A8%EA%B3%84 h_01J5QWWGWGPRF5DRMMQ14BJCFA=step-5-understand-parameter-mapping 01H8K961JHBXVKXM0XQYY605EQ=%EC%B0%B8%EA%B3%A0 h_01J5QWWGWG3ST19WDRZXN8FK8Q=step-6-create-onelink-links-with-mapped-parameters h_01HE7SZPKKQETH260G45V0D0HN=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
