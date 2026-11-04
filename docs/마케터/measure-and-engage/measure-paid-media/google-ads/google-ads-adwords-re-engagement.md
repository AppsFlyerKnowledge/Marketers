---
title: Google Ads (AdWords)—리인게이지먼트
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2022-01-20T09:55:51Z'
  edited_at: '2026-10-14T10:38:38Z'
  id: 4417296925073
  locale: ko
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/ko/articles/4417296925073
---
> **한눈에 보기:** Google Ads 리타겟팅 캠페인 측정

<div id="google-ads-retargeting-campaigns" />

## Google Ads 리타겟팅 캠페인

앱스플라이어를 통해 **Google Ads 앱 리인게이지먼트 캠페인** 결과를 측정할 수 있습니다.  
앱스플라이어에서는 이러한 캠페인을 <Anchor target="_blank" href="/marketers/ko/docs/retargeting-attribution-guide">리타겟팅</Anchor> 캠페인이라고 부릅니다. 앱스플라이어는 리타겟팅 캠페인에 대한 비용, 클릭 및 노출 데이터 가져오기를 지원합니다. 이 연동을 통해 Google Ads에서의 광고 지출을 확인하고 측정한 다음, Google Ads 캠페인의 eCPI 및 ROI를 계산할 수 있습니다.

리타겟팅 캠페인은 과거에 앱을 설치한 사용자를 타깃합니다.

* 앱을 여전히 보유하고 있는 사용자에 의한 리타겟팅 인게이지먼트는 **리인게이지먼트(Re-engagement)** 라고 합니다. 이때 사용자는 딥링킹됩니다.
* 앱을 보유하고 있지 않은 사용자에 의한 리타겟팅 인게이지먼트는 **리인스톨(Re-install)** 또는 **리어트리뷰션(Re-attribution)** 이라고 합니다.

자세한 내용은 <Anchor target="_blank" href="https://support.google.com/google-ads/answer/9234180">Google Ads 앱 리인게이지먼트 캠페인 지원 문서</Anchor>를 참고하십시오.

<div id="setting-up-google-ads-app-campaigns-for-engagement" />

## 인게이지먼트를 위한 Google Ads 앱 캠페인 생성하기

시작하기 전에 기존 링크 ID를 통해 인게이지먼트 캠페인이 정확히 측정되도록 <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7365001?hl=en">다른 Google Ads 계정과 링크를 공유하는 방법에 대한 Google의 지침</Anchor>을 검토하십시오.

인게이지먼트를 위한 Google Ads 앱 캠페인을 측정하려면, 다음 세 단계를 따르십시오:

<div id="enabling-retargeting-in-app-settings" />

<Accordion title="앱 설정에서 리타겟팅 활성화">

미디어 소스에서 리타겟팅 캠페인을 활성화하려면, 앱 수준에서 이를 활성화해야 합니다. 이것이 앱의 첫 번째 리타겟팅 캠페인이라면, 다음을 진행하십시오.

1. 앱스플라이어의 사이드 메뉴에서 **설정** > **앱 설정**을 선택합니다.
2. 아래로 끝까지 스크롤합니다.
3. **리인게이지먼트 어트리뷰션**을 켭니다.

</Accordion>

<div id="enable-google-ads-retargeting-in-appsflyer" />

<Accordion title="앱스플라이어에서 Google Ads 리타겟팅 활성화">

* 앱스플라이어에서 Google Ads를 설정하려면 <Anchor target="_blank" href="/marketers/ko/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">여기 링크의 안내</Anchor> 5번 항목을 진행하십시오.

</Accordion>

<div id="importing-session-start-conversions-in-google-ads" />

<Accordion title="Google Ads에서 세션 시작(session start) 전환 가져오기">

**Google Ads에서** 리인게이지먼트 캠페인의 전환을 기록하려면, Google Ads에서 session\_start 이벤트를 가져와야합니다.

앱스플라이어에서 Google Ads 리타겟팅을 활성화한 후 최소 한 명의 사용자가 앱을 실행하면 이 이벤트가 Google Ads에 표시됩니다. 확실히 하기 위해, 리타겟팅을 활성화한 후 직접 앱을 실행해 보세요.

Google Ads에서 전환을 가져오는 방법을 알아보려면 <Anchor target="_blank" href="/marketers/ko/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">여기</Anchor>를 참조하십시오.

<div id="note" />

> 📘 **참고**
>
> 다른 이벤트와 달리, session\_start 이벤트는 앱스플라이어에서 Google Ads로 가져오지 않아도 Google Ads API에서 자동으로 인식하고 어트리뷰션을 할 수 있습니다.
> 그러나 이 경우에도, 해당 전환은 앱스플라이어에서 어트리뷰션 될 수 있습니다. 이로 인해 **Google Ads와 앱스플라이어 상의 데이터 사이 상당한 차이가 발생할 수 있습니다.** 또한, 이는 **Google Ads가 캠페인 사용자 타겟팅을 최적화하는 것을 방지합니다.**

</Accordion>

<div id="setting-up-deep-linking-for-app-campaigns-for-engagement" />

<Accordion title="앱 캠페인 인게이지먼트를 위한 딥링킹 설정">

인게이지먼트를 위한 Google 앱 캠페인은 <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6310747?hl=en&ref_topic=3121770">리인게이지먼트(re-engagement) 캠페인에서 딥링크 사용을</Anchor> 필히 요구합니다. 도메인 불일치로 인해 타사 딥링킹 솔루션은 사용할 수 없습니다. 여기에는 앱스플라이어의 원링크가 포함됩니다. <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6046977?hl=en">자체 개발한 앱 링크, 유니버설 링크 또는 커스텀 URI scheme</Anchor>을 사용하십시오.

딥링크에 파라미터를 별도로 추가할 필요가 없습니다. (is\_retargeting=true 및 pid=adwords는 필요하지 않음)

</Accordion>

<div id="dynamic-remarketing-and-shopping-campaigns" />

## 동적 리마케팅(Dynamic remarketing) 및 쇼핑 캠페인

앱스플라이어에서는 앱 및 쇼핑 캠페인에 대한 동적 리마케팅을 지원합니다. 앱스플라이어 플랫폼은 이를 다른 리인게이지먼트 캠페인과 동일하게 취급합니다.

* 앱을 위한 동적 리마케팅에 대해 알아보려면 <Anchor target="_blank" href="https://support.google.com/adwords/answer/7538938">여기를</Anchor> 클릭하십시오.
* 쇼핑 캠페인에 대해 알아보려면 <Anchor target="_blank" href="https://support.google.com/google-ads/answer/2454022?hl=en">여기를</Anchor> 클릭하십시오.
* Google Ads 인게이지먼트에 대해 더 자세히 알아보려면 <Anchor target="_blank" href="https://support.google.com/google-ads/answer/9234180">여기를</Anchor> 클릭하십시오.

<div id="support-for-non-app-campaigns-demand-gen-and-sem" />

### 앱 외 캠페인(Demand Gen 및 SEM)에 대한 지원

AppsFlyer는 Google의 비앱 캠페인에 대한 재참여 측정만 지원합니다. 포함된 내용:

* Demand Gen 캠페인
* 검색 엔진 마케팅(Search Engine Marketing, SEM) 캠페인

이 캠페인은 **기본 설정**만으로 앱스플라이어와 바로 연동되며 다음을 요하지 않습니다:

* 병렬 추적
* 스마트 스크립트 구현

**제한 사항:**

* Demand Gen 또는 SEM 캠페인으로부터 발생한 **인스톨**은 어떤 플랫폼에서도 어트리뷰션되지 않습니다.

**옵트 아웃:** Google은 현재 앱 외 캠페인 측정에 대한 옵트인 및 옵트 아웃을 지원하지 않습니다(틱톡이나 메타와 같은 플랫폼과 구분됨).

<div id="see-also" />

> 📄 **참고 항목**
>
> * iOS 14 관련 고려 사항은 <Anchor target="_blank" href="/marketers/ko/docs/get-skan-postback-data-from-google-ads">앱스플라이어와 Google Ads SKAdNetwork 상호 운용성</Anchor>을 참조하세요.

<div data-zendesk-anchors="google-ads-retargeting-campaigns=google-ads-%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%EC%BA%A0%ED%8E%98%EC%9D%B8 h_01HDP34BWZFG09ABN5NQB6EY32=google-ads-%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%EC%BA%A0%ED%8E%98%EC%9D%B8 setting-up-google-ads-app-campaigns-for-engagement=%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8%EB%A5%BC-%EC%9C%84%ED%95%9C-google-ads-%EC%95%B1-%EC%BA%A0%ED%8E%98%EC%9D%B8-%EC%83%9D%EC%84%B1%ED%95%98%EA%B8%B0 h_01HDP34BWZXXNZDE0SR4MXBC9V=%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8%EB%A5%BC-%EC%9C%84%ED%95%9C-google-ads-%EC%95%B1-%EC%BA%A0%ED%8E%98%EC%9D%B8-%EC%83%9D%EC%84%B1%ED%95%98%EA%B8%B0 h_01HDP34BWZNHY08NDX6YSE9CXR=enabling-retargeting-in-app-settings h_01HDP34BWZNNNT4HRMXJB2X3S2=enable-google-ads-retargeting-in-appsflyer h_01HDP34BWZ8MGJKEZFC77VYWNG=importing-session-start-conversions-in-google-ads h_01HDP34BWZHWVKKNB7CEHY73R0=%EC%B0%B8%EA%B3%A0 h_01HDP34BWZ64XG2G0PTH6XCCMG=setting-up-deep-linking-for-app-campaigns-for-engagement dynamic-remarketing-and-shopping-campaigns=%EB%8F%99%EC%A0%81-%EB%A6%AC%EB%A7%88%EC%BC%80%ED%8C%85dynamic-remarketing-%EB%B0%8F-%EC%87%BC%ED%95%91-%EC%BA%A0%ED%8E%98%EC%9D%B8 h_01HDP34BWZ990SD3B1C5DZRESK=%EB%8F%99%EC%A0%81-%EB%A6%AC%EB%A7%88%EC%BC%80%ED%8C%85dynamic-remarketing-%EB%B0%8F-%EC%87%BC%ED%95%91-%EC%BA%A0%ED%8E%98%EC%9D%B8 h_google-non-app-campaign-support=%EC%95%B1-%EC%99%B8-%EC%BA%A0%ED%8E%98%EC%9D%B8demand-gen-%EB%B0%8F-sem%EC%97%90-%EB%8C%80%ED%95%9C-%EC%A7%80%EC%9B%90 support-for-nonapp-campaigns-demand-gen-and-sem=%EC%95%B1-%EC%99%B8-%EC%BA%A0%ED%8E%98%EC%9D%B8demand-gen-%EB%B0%8F-sem%EC%97%90-%EB%8C%80%ED%95%9C-%EC%A7%80%EC%9B%90 h_01HDP2XBSEJVQ5G0MD0V5R05CM=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
