---
title: 앱스플라이어 A/B 테스트 가이드
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2019-05-07T09:17:43Z'
  edited_at: '2026-10-14T10:26:57Z'
  id: 360001523657
  locale: ko
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/ko/articles/360001523657
---
> **한눈에 보기:** 앱스플라이어를 사용하여 미디어소스, 캠페인, 크리에이티브, 타겟팅, 광고 배치에 대한 A/B 테스트를 수행할 수 있습니다.

<Image align="center" alt="AB_TESTING.jpg" src="https://files.readme.io/259277a96d044e85cbac39de0f636bad531706e53e2ad5a21475277ea9dbd3a6-360002822018.jpg" />

<div id="what-is-ab-testing" />

## A/B 테스트란?

A/B 테스트는 마케터가 광고 및 캠페인의 다양한 요소를 테스트하는 데 사용하는 방법입니다. 각 광고에는 잠재 사용자의 전환율에 영향을 줄 수 있는 요소(타게팅, 비주얼, 텍스트)가 포함되어 있습니다. 성과가 가장 좋은 광고 요소의 변형을 찾는 것은 모바일 마케팅 활동의 수익에 상당한 영향을 미칠 수 있습니다.

이 문서에서는 **광고주가 앱스플라이어를 사용하여 A/B 테스트를 수행하여 가장 성과가 좋은 광고 요소를 찾는 방법**을 설명합니다.

<div id="how-to-ab-test-mobile-campaigns" />

## 모바일 캠페인에 대한 A/B 테스트 방법

어떤 요소에 대해 A/B 테스트를 수행하려면 동일한 제안을 보여주는 두 소스 사이에서 모바일 트래픽을 50/50으로 분할하세요. 다음으로, 테스트할 요소의 두 가지 변형을 만듭니다. 충분한 트래픽이 통과한 후 기존 버전(대조군)의 결과를 새 버전(변형)과 비교할 수 있습니다.

다음 단계는 앱스플라이어를 사용하여 실행하는 A/B 테스트에 적용됩니다.

**설정**:

1. 테스트할 요소를 선택합니다.  
   이 본문에서는 [크리에이티브](/docs/create-a-b-tests#크리에이티브-ab-테스트-및-타게팅), 광고 배치, 미디어소스, 캠페인의 A/B 테스트에 대해 설명합니다.
2. 두 개의 동일한 캠페인(또는 광고)을 만든 다음 광고 내의 단일 요소에 변화를 줍니다. 예를 들어 행동 유도 버튼 복사가 있습니다.
   * 변형이 **설치 전환율**에 미치는 영향을 테스트하려면 두 캠페인 간에 트래픽을 균등하게 분할하세요.   
     두 소스 모두에 대해 전체 노출 데이터를 사용할 수 있는 경우 설치 수를 노출 수로 나누어 설치 전환율을 계산합니다.
   * 사용자 품질에 대한 변형의 영향을 테스트하려면 **설치 후** 두 캠페인에 서로 다른 양의 트래픽을 보낼 수 있습니다.
3. 통계적 유의성에 도달할 수 있도록 각 캠페인에 충분한 트래픽을 유도해야 하는데, 이는 곧 캠페인당 50회 이상의 설치를 의미합니다. <Anchor target="_blank" href="https://neilpatel.com/ab-testing-calculator/">A/B 테스트 유의성 계산기</Anchor>를 사용합니다.

**분석:**

1. 앱스플라이어의 대시보드와 데이터를 사용하여 두 캠페인 간의 주요 KPI 성과를 비교합니다.
2. 가장 성과가 좋은 변형을 선택하여 라이브 캠페인에 사용합니다.

<div id="ab-testing-creatives-and-targeting" />

## 크리에이티브 A/B 테스트 및 타게팅

크리에이티브에는 카피, 이미지, 색상, 글꼴, 버튼 등 사용자 전환율에 다양한 영향을 미치는 많은 요소가 포함됩니다. 국가, 연령 또는 성별과 같은 타겟팅 파라미터도 전환율에 큰 영향을 미칠 수 있습니다. iOS 15 이상의 경우 최대 35개의 사용자 지정된 제품 페이지가 있을 수도 있습니다. **이러한 요소를 A/B 테스트하면 사용자 전환율 향상에 가장 큰 영향을 미치는 요소를 찾는 데 도움이 될 수 있습니다**.

아래에서는 다음을 사용하여 A/B 테스트를 수행하는 두 가지 방법을 설명합니다.

* 단일 미디어소스
* 여러 미디어소스

| 방법 | 장점 | 단점 |
| --- | --- | --- |
| 단일 미디어소스를 사용한 A/B 테스트 | <ul><li>빠른 설정</li><li>설치 전환율을 테스트하기 쉬움</li></ul> | <ul><li>결과는 특정 미디어소스의 사용자에게만 적용될 수 있음</li><li>테스트하는 데 시간이 더 오래 걸릴 수 있음</li></ul> |
| 여러 미디어소스에 대한 A/B 테스트 | <ul><li>빠른 결과</li><li>결과가 모든 미디어소스의 사용자에게 적용됨</li></ul> | <ul><li>여러 위치에서 어트리뷰션 링크를 업데이트해야 함</li></ul> |

<div id="method-1-ab-testing-with-a-single-media-source" />

<Accordion title="방법 1: 단일 미디어소스를 사용한 A/B 테스트">

**설정**:

1. 트래픽이 충분한 신뢰받는 미디어소스를 선택합니다.
2. 다음 방법 중 하나를 사용하여 앱스플라이어에서 두 개의 캠페인 또는 <Anchor target="_blank" href="/marketers/ko/docs/smart-banners-mobile-web-to-app-for-marketers#3-banner-setup">스마트 배너</Anchor>를 만듭니다.
   * 어트리뷰션 링크에서 "**c**" 파라미터인 이름을 가진 캠페인을 변경합니다.
   * 또는 캠페인 내에서 두 개의 광고 세트("**af\_adset**=")를 만들거나 광고 세트 내에서 단일 광고("**af\_ad=**")를 만들 수 있습니다. **참고**: 스마트 배너에서 동일한 배너 그룹 내에서 <Anchor target="_blank" href="/marketers/ko/docs/smart-banners-mobile-web-to-app-for-marketers#ab-testing-banner-performance">각 배너에 대해 다른 파라미터를 입력하여 A/B 테스트를 수행</Anchor>할 수도 있습니다.
   * iOS 15 이상의 경우, 서로 다른 제품 페이지에 서로 다른 원링크 URL을 전송하여 다양한 사용자 지정 제품 페이지의 효과를 테스트할 수도 있습니다. <Anchor target="_blank" href="/marketers/ko/docs/redirect-users-to-custom-app-store-product-pages">더 알아보기</Anchor>
3. 테스트된 변형을 제외하고 두 캠페인에서 동일한 크리에이티브를 사용합니다.
4. 두 캠페인에 동일한 양의 트래픽을 전송합니다.

**분석:**

* 개요 대시보드 페이지에서 캠페인의 KPI(예: 설치 전환율, ROI, ARPU, 로열 유저 비율)를 비교합니다.

</Accordion>

<div id="method-2-ab-testing-across-multiple-media-sources" />

<Accordion title="방법 2: 여러 미디어소스에 대한 A/B 테스트">

**설정**:

1. 변형 값을 보유할 구독자 파라미터를 선택합니다.  
   예를 들어 2개의 CTA 텍스트 변형을 테스트하려면 af\_sub1="install now" 또는 af\_sub1="please install"을 사용할 수 있습니다. <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#what-are-subscriber-parameters-good-for">여기</Anchor>에서 구독자 파라미터와 크리에이티브 테스트 예시에 대해 자세히 알아보세요.
2. 일치하는 값을 가진 구독자 파라미터를 모든 라이브 어트리뷰션 링크에 추가합니다.
3. 테스트된 변형을 제외한 모든 캠페인에서 동일한 크리에이티브를 사용하는 것이 좋습니다.

**분석:**

1. 설치 또는 인앱 이벤트 로데이터 리포트를 다운로드합니다. 선택한 구독자 파라미터 열을 사용하여 데이터를 필터링하고 정렬합니다.
2. 크리에이티브의 성과를 저장된 2개의 값 중 하나와 비교합니다.

</Accordion>

<div id="ab-testing-ad-placement-on-mobile-web" />

## 모바일 웹에서 광고 배치 A/B 테스트

<Image align="center" alt="ad_placement.png" src="https://files.readme.io/6d64eed1a7a16c6daae9c93429d5bd46625dc4de12728e42b49a91ae69765f24-360002747977.png" />

모바일 웹사이트에서 앱 배너의 위치는 사용자 전환율에 상당한 영향을 미칠 수 있습니다. 대부분의 경우 광고주는 방문자를 모바일 사용자로 전환하기 위해 자체 모바일 웹사이트를 사용합니다.

앱스플라이어 <Anchor target="_blank" href="/marketers/ko/docs/smart-banners-mobile-web-to-app-for-marketers">스마트 배너 기능</Anchor>으로 모바일 웹 배너를 빠르고 쉽게 설정할 수 있습니다. 또한 이 기능을 사용하면 A/B 테스트를 쉽게 실행하여 **웹사이트 방문자를 모바일 사용자로 전환하기 위한 최적의 배치를 결정**할 수 있습니다.

**설정**:

1. 모바일 웹사이트에 <Anchor target="_blank" href="/marketers/ko/docs/smart-banners-mobile-web-to-app-for-marketers">스마트 배너</Anchor>를 구현합니다.
2. 각각의 새 방문자에 대해 페이지 상단 또는 하단에 배너를 표시할지 여부를 결정합니다. 둘 사이에 트래픽을 50/50으로 분할해야 합니다.  
   개발자 팁 - 웹사이트 트래픽을 분할하는 간단한 방법은 방문자 카운터를 사용한 다음, 각각의 신규 방문자에 대해 카운터 값이 홀수(옵션 A)인지 짝수(옵션 B)인지 확인하는 것입니다.
3. 스마트 배너의 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#showbanner">SDK API ShowBanner</Anchor>를 사용하여 결정된 위치에 따라 배너 위치와 어트리뷰션 링크를 설정합니다.  
   예:

   ```javascript
   showBanner({ bannerContainerQuery: "#document.body", additionalParams:{ af_sub5: "top"}})
   ```

**분석:**

1. 설치 또는 인앱 이벤트에 대한 로데이터 리포트를 다운로드하세요. 선택한 구독자 파라미터(예: af\_sub5) 열을 사용하여 데이터를 필터링하고 정렬합니다.
2. 두 광고 배치의 성과, 즉 더 많은 설치 또는 설치 후 이벤트를 받은 배치를 비교해 보세요.

<div id="ab-testing-media-sources" />

## 미디어소스 A/B 테스트

광고주가 앱에 대해 최상 또는 최악의 성과를 내는 미디어소스를 식별하도록 돕는 것이 앱스플라이어를 만든 목적입니다. 하지만 **광고주가 미디어소스를 올바르게 비교하지 못하면 트래픽 품질에 대한 잘못된 결론에 도달할 위험이 있습니다**.

**설정:**

1. 두 미디어소스 모두에 대해 하나의 광고 크리에이티브를 만듭니다.
2. 각 미디어소스에 대해 정확히 동일한 오디언스 타겟팅 파라미터를 사용하여 광고를 정의합니다.
3. 2개의 미디어소스에 서로 다른 양의 트래픽을 보낼 수 있습니다.

**분석:**

1. 테스트 중인 광고가 오직 하나만 두 미디어소스에서 모두에서 실행되는 경우 앱스플라이어의 대시보드와 데이터를 사용하여 두 소스 간의 주요 KPI를 쉽게 비교할 수 있습니다.  
     
   그렇지 않으면 다음과 같이 하세요.
2. 앱스플라이어의 리텐션 리포트, <Anchor target="_blank" href="/marketers/ko/docs/cohort-and-retention-dashboard">코호트 리포트</Anchor>, <Anchor target="_blank" href="/marketers/ko/docs/master-api-user-acquisition-metrics-via-api">마스터 API</Anchor> 또는 <Anchor target="_blank" href="/marketers/ko/docs/pivot-table-user-metrics">피벗 테이블</Anchor>로 이동합니다.
3. 미디어소스별 그룹화 -> 캠페인 -> 광고 세트 -> 광고.
4. KPI를 비교하여 성과가 가장 좋은 미디어소스를 식별합니다.

<div id="example" />

> 📄 **예시**
>
> <Image align="center" alt="" src="https://files.readme.io/bf907e0e67d24764a68579ba6fc42d0d49befbc7ffc7645b91ae1aa8f8b97c12-360002829938.png" />
>
> * 1과 2는 동일한 미디어소스에 있는 서로 다른 광고입니다. 예를 들어 리텐션 4일 차 비율과 같은 단일 KPI를 A/B 테스트 크리에이티브, 타겟팅 또는 광고 배치와 비교합니다.
> * 2와 3은 서로 다른 미디어소스의 광고입니다. 광고의 크리에이티브와 타겟팅이 동일한 경우 단일 KPI를 비교하면 미디어소스에 대한 A/B 테스트를 수행할 수 있습니다.

<div id="using-audiences-split-for-easy-ab-testing-of-media-sources" />

### 미디어소스의 간편한 A/B 테스트를 위해 오디언스 분할 사용

각 미디어소스에 대해 동일한 타겟팅 파라미터를 설정하면 테스트에 네트워크의 타겟팅 기능이 포함됩니다. A/B 테스트를 할 때는 매번 하나의 변형을 테스트하는 것이 가장 좋습니다. 따라서 네트워크 성능의 다른 요소를 A/B 테스트할 때 타겟팅 능력의 차이를 제거하는 것이 좋습니다.

이를 위해서는 오디언스를 무작위로 분할하고 테스트된 각 네트워크에서 동일한 크리에이티브로 두 오디언스를 모두 타겟팅하는 것이 좋습니다. 앱스플라이어는 **다양한 미디어소스 간에 오디언스를 정의, 분할, 자동 분배하는 간편한 방법**을 제공합니다. <Anchor target="_blank" href="/marketers/ko/docs/audiences-guide#오디언스-분할-및-성과-증분-테스트">여기</Anchor>에서 자세한 내용을 읽어보세요.

<div data-zendesk-anchors="what-is-ab-testing=ab-%ED%85%8C%EC%8A%A4%ED%8A%B8%EB%9E%80 h_01HN5CNKKBHV52ENXJXCBV2CES=ab-%ED%85%8C%EC%8A%A4%ED%8A%B8%EB%9E%80 how-to-ab-test-mobile-campaigns=%EB%AA%A8%EB%B0%94%EC%9D%BC-%EC%BA%A0%ED%8E%98%EC%9D%B8%EC%97%90-%EB%8C%80%ED%95%9C-ab-%ED%85%8C%EC%8A%A4%ED%8A%B8-%EB%B0%A9%EB%B2%95 h_01HN5CNKKC02NKW4330QB6E01T=%EB%AA%A8%EB%B0%94%EC%9D%BC-%EC%BA%A0%ED%8E%98%EC%9D%B8%EC%97%90-%EB%8C%80%ED%95%9C-ab-%ED%85%8C%EC%8A%A4%ED%8A%B8-%EB%B0%A9%EB%B2%95 ab-testing-creatives-and-targeting=%ED%81%AC%EB%A6%AC%EC%97%90%EC%9D%B4%ED%8B%B0%EB%B8%8C-ab-%ED%85%8C%EC%8A%A4%ED%8A%B8-%EB%B0%8F-%ED%83%80%EA%B2%8C%ED%8C%85 h_01HN5CNKKCJPZSEEF1RAHC0HXD=%ED%81%AC%EB%A6%AC%EC%97%90%EC%9D%B4%ED%8B%B0%EB%B8%8C-ab-%ED%85%8C%EC%8A%A4%ED%8A%B8-%EB%B0%8F-%ED%83%80%EA%B2%8C%ED%8C%85 h_01HN5CNKKCMVE9YH379RP1S19W=method-1-ab-testing-with-a-single-media-source h_01HN5CNKKC53RTV61K08T9AVRA=method-2-ab-testing-across-multiple-media-sources ab-testing-ad-placement-on-mobile-web=%EB%AA%A8%EB%B0%94%EC%9D%BC-%EC%9B%B9%EC%97%90%EC%84%9C-%EA%B4%91%EA%B3%A0-%EB%B0%B0%EC%B9%98-ab-%ED%85%8C%EC%8A%A4%ED%8A%B8 h_01HN5CNKKCVPSSZZTJ8QGJHY1B=%EB%AA%A8%EB%B0%94%EC%9D%BC-%EC%9B%B9%EC%97%90%EC%84%9C-%EA%B4%91%EA%B3%A0-%EB%B0%B0%EC%B9%98-ab-%ED%85%8C%EC%8A%A4%ED%8A%B8 ab-testing-media-sources=%EB%AF%B8%EB%94%94%EC%96%B4%EC%86%8C%EC%8A%A4-ab-%ED%85%8C%EC%8A%A4%ED%8A%B8 h_01HN5CNKKC03ZAFCQZ0KJ0RHCE=%EB%AF%B8%EB%94%94%EC%96%B4%EC%86%8C%EC%8A%A4-ab-%ED%85%8C%EC%8A%A4%ED%8A%B8 h_01HN5CNKKC4M6YMPHTQCFHFDMD=%EC%98%88%EC%8B%9C using-audiences-split-for-easy-ab-testing-of-media-sources=%EB%AF%B8%EB%94%94%EC%96%B4%EC%86%8C%EC%8A%A4%EC%9D%98-%EA%B0%84%ED%8E%B8%ED%95%9C-ab-%ED%85%8C%EC%8A%A4%ED%8A%B8%EB%A5%BC-%EC%9C%84%ED%95%B4-%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%EB%B6%84%ED%95%A0-%EC%82%AC%EC%9A%A9 h_01HN5CNKKC551X3HQFNKHW1JBY=%EB%AF%B8%EB%94%94%EC%96%B4%EC%86%8C%EC%8A%A4%EC%9D%98-%EA%B0%84%ED%8E%B8%ED%95%9C-ab-%ED%85%8C%EC%8A%A4%ED%8A%B8%EB%A5%BC-%EC%9C%84%ED%95%B4-%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%EB%B6%84%ED%95%A0-%EC%82%AC%EC%9A%A9" />
