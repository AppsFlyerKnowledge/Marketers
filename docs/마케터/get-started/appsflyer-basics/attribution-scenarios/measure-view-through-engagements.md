---
title: 뷰쓰루 어트리뷰션 가이드
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
  created_at: '2016-04-20T07:38:24Z'
  edited_at: '2026-10-14T10:36:44Z'
  id: 210084473
  locale: ko
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/ko/articles/210084473
---
> **한눈에 보기:** 요약: 광고(노출)를 보고 앱을 인스톨한 사용자는 뷰-쓰루 어트리뷰션에 의해 어트리뷰트됩니다.

## 개요

뷰-쓰루 어트리뷰션은 광고를 보았지만 클릭하지 않은 사용자의 인스톨, 리어트리뷰션 및 리인게이지먼트를 측정합니다.

### 뷰쓰루 어트리뷰션 흐름

![Retargeting_-_View-through__1_.png](https://files.readme.io/86d32778a8a0966499a0c5c91c1b2d8aed6d5bb24214b1a32fd484779c105a98-4412917609489.png)

### 용어

* impression 노출: 클릭 또는 기타 사용자 인게이지먼트와 관계없이 사용자에게 광고가 표시됩니다.
* **인스톨**: 인스톨: 이 문서에서 인스톨, 리어트리뷰션 및 리인게이지먼트를 의미합니다.
* 뷰-쓰루 어트리뷰션

### 뷰-쓰루 어트리뷰션 원칙

* <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-attribution-model#device-id-matching">기기 ID 일치</Anchor> 및 <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-attribution-model#probabilistic-modeling">확률 모델링</Anchor> (<Anchor target="_blank" href="/marketers/ko/docs/app-settings#viewthrough-attribution-via-probabilistic-modeling">켜야 함</Anchor>)이 모두 지원됩니다.
* [뷰-쓰루 어트리뷰션 파트너 목록](/docs/measure-view-through-engagements#view-vta-partner-list)에나열된 파트너가 지원합니다.

노출은 다음 원칙에 따라 뷰-쓰루 어트리뷰션의 후보자입니다.

* 뷰-쓰루 룩백 기간(기본 24시간) 내에 노출이 발생했습니다.
* 여러 개의 노출이 있는 경우 가장 최근의 노출이 고려됩니다.
* 클릭이 노출보다 우선합니다. 즉, 클릭-쓰루 룩백 기간에 클릭이 있는 경우 가장 최근의 클릭이 우선합니다. 가장 최근의 노출은 기여자(지원자)로 표시됩니다.

### 뷰-쓰루 룩백 윈도우

* 비 SRN의 경우 뷰-쓰루 어트리뷰션 룩백 기간은 1-24시간입니다. SRN의 경우 룩백 기간이 더 길어질 수 있습니다.
* 기간을 설정하려면:
  * **비 SRN**: 파라미터가 설정되지 않은 경우 기본 24시간 창이 사용됩니다.
  * **SRNs** SRN: 기간은 SRN에 의해 결정됩니다. 앱스플라이어의 SRN과 동일한 값을 설정하는 것이 좋습니다.

### 뷰-쓰루 어트리뷰션 리포트 및 지표

* 집계 데이터: 집약형 데이터:/strong> 광고 네트워크는 API를 통해 또는 노출별로 집약형 노출 데이터를 앱스플라이어에 리포트합니다. 노출수 계산 및 리포트는 각 파트너에 의해 개별적으로 정의됩니다. 주요 연동 파트너별 노출수 및 클릭수 정의를 확인하십시오.
  * 노출 수: 노출수: 지정된 기간 동안 표시된 노출수입니다.
  * 뷰-쓰루 뷰-쓰루: 뷰-쓰루 어트리뷰션을 사용하여 어트리뷰트한 인스톨 수입니다.
* **로데이터**:
  * 뷰-쓰루 어트리뷰션을 통해 어트리뷰트된 사용자의 사용자 수준 데이터(로데이터)를 사용할 수 있으며 클릭으로 어트리뷰트된 사용자와 유사합니다. 그러나 일부 파트너는 이 데이터의 가용성을 제한합니다.
  * 노출 데이터(클릭 데이터와 유사)를 사용할 수 있습니다.
  * attribute\_touch\_type 필드에는 값 *노출*이 포함됩니다.

## 뷰-쓰루 작동

<div id="set-impression-links" />

<Accordion title="노출 링크 설정">

광고 네트워크는 캠페인 및 클릭연결 <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters">어트리뷰션 링크</Anchor>에 포함된 것과 유사한 기타 세부정보로 채워진 앱스플라이어에 노출 링크를 보냅니다.

링크는 실시간으로 전송되므로 인스톨을 따라가면 올바르게 표시됩니다.

링크를 준비할 때 다음 사항을 고려하십시오.

* GET 요청을 사용합니다.
* <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-attribution-model#애드-네트워크에-대한-확률적-모델링-파라미터">확률적 모델링</Anchor> 파라미터를 포함합니다.
* 보안을 강화하기 위해, SHA1을 사용하여 디바이스 ID 값을 해시할 수 있습니다. 파라미터 이름은 반드시 "sha1\_"로 시작하고 그 뒤에 파라미터 이름과 해시된 값(예: sha1\_idfa, sha1\_advertising\_id, sha1\_android\_id 및 sha1\_imei)이 와야합니다.

> 📄
>
>  예시
>
> ```http
> https://impression.appsflyer.com/{app-id}?c={campaign name}&pid={media source}
> &af_viewthrough_lookback=1d&af_prt={agency_name}&af_siteid={site id value}
> &af_sub1={free value}&idfa={idfa value}
> ```

</Accordion>

<div id="set-custom-impression-links" />

<Accordion title="커스텀 노출 링크 설정">

광고주는 웹사이트 배너와 같은 자체 맞춤 미디어 소스와 함께 어트리뷰션 노출 링크를 활용합니다.

광고주가 <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#캠페인을-위한-원링크-링크-생성하기">커스텀 어트리뷰션 링크를 만들면</Anchor> 사용자가 소유한 광고에 참여할 때마다 실행될 수 있는 전체 노출 링크를 얻게 됩니다.

커스텀 노출 링크(원링크를 통해 생성됨)는 모바일 웹사이트 방문자의 뷰-쓰루 어트리뷰션을 수행하는 데에도 사용할 수 있습니다.  <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">커스텀 노출 URL 생성</Anchor>에 대해 자세히 알아보세요.

</Accordion>

<div id="turn-off-viewthroughattribution" />

<Accordion title="뷰-쓰루 어트리뷰션 끄기">

기본적으로 뷰-쓰루 어트리뷰션은 설정되어 있습니다. 앱스플라이어가 유효한 노출 어트리뷰션 링크를 수신하면 해당 노출은 어트리뷰션 흐름에 참여합니다.

뷰-쓰루 어트리뷰션은 기본적으로 활성화되어 있으므로 광고주는 뷰-쓰루 어트리뷰션을 활성화할지 여부에 대해 사전에 네트워크와 계약상 동의하는 것이 중요합니다.

미디어 소스별로 뷰-쓰루 어트리뷰션을 비활성화할 수 있습니다. 그러나 노출이 수신되고 뷰-쓰루 어트리뷰션이 비활성화된 경우:

* 노출 지표는 대시보드에서 사용할 수 있습니다.
* 어트리뷰션 프로세스는 이러한 노출을 무시합니다.

**뷰-쓰루 어트리뷰션을 끄려면:**

1. 앱스플라이어의 측면 메뉴에서 **협업** > **활성화된 연동**을 선택하세요.
2. 통합 파트너를 선택하세요.
3. 연동 탭에서 **뷰-쓰루 어트리뷰션 인스톨**을 끕니다.
4. **연동 저장**을 클릭하세요.

SRN과 관련하여 다음 사항을 참조하세요. SRN과 관련하여: 앱스플라이어에서 뷰-쓰루 어트리뷰션을 끄는 것은 네트워크 측에서 동일하지 않습니다. 불일치를 방지하기 위해 앱스플라이어와 네트워크 모두에서 뷰-쓰루 설정을 정렬해야 합니다.

</Accordion>

<div id="view-vta-partner-list" />

<Accordion title="VTA 파트너 목록 보기">

뷰-쓰루 어트리뷰션을 지원하는 광고 네트워크 파트너 목록은 대시보드를 통해 확인할 수 있습니다.

**목록을 보려면**:

1. 앱스플라이어의 측면 메뉴에서 **협업** > **활성화된 연동**을 선택하세요.
2. 모든 연동을 선택합니다.
3. **파트너 기능** 필터에서, 뷰-쓰루를 선택합니다.    
   파트너 목록이 표시됩니다.

</Accordion>

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 h_01HEMT7T1TB9W7ZBRPQW29SRPF=%EA%B0%9C%EC%9A%94 viewthrough-attribution-flow=%EB%B7%B0%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%9D%90%EB%A6%84 h_01HEMT7T1T6ZK4ZH7DKV3162J1=%EB%B7%B0%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%9D%90%EB%A6%84 terminology=%EC%9A%A9%EC%96%B4 h_01HEMT7T1TY46QXBDS6MBF1DZ5=%EC%9A%A9%EC%96%B4 viewthrough-attribution-principles=%EB%B7%B0-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%9B%90%EC%B9%99 h_01HEMT7T1THD8TVKRRJ168HKY2=%EB%B7%B0-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%9B%90%EC%B9%99 viewthrough-lookback-window=%EB%B7%B0-%EC%93%B0%EB%A3%A8-%EB%A3%A9%EB%B0%B1-%EC%9C%88%EB%8F%84%EC%9A%B0 h_01HEMT7T1TWHN2AB3Q5X36TKKB=%EB%B7%B0-%EC%93%B0%EB%A3%A8-%EB%A3%A9%EB%B0%B1-%EC%9C%88%EB%8F%84%EC%9A%B0 viewthrough-attribution-reporting-and-metrics=%EB%B7%B0-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EB%B0%8F-%EC%A7%80%ED%91%9C h_01HEMT7T1TQNKM5GABA7VY6KR1=%EB%B7%B0-%EC%93%B0%EB%A3%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EB%B0%8F-%EC%A7%80%ED%91%9C viewthrough-operations=%EB%B7%B0-%EC%93%B0%EB%A3%A8-%EC%9E%91%EB%8F%99 h_01HEMT7T1T13JC75ZYY01N8PS6=%EB%B7%B0-%EC%93%B0%EB%A3%A8-%EC%9E%91%EB%8F%99 h_01HEMT7T1TQ3YNQ2Y0CCGPXWDX=set-impression-links h_01HEMT7T1T75MBS64JE837CJ0E=set-custom-impression-links h_01HEMT7T1T253G1CZNS9KVDFCP=turn-off-viewthroughattribution h_01HEMT7T1T5MQHC3F5EHSGMYQF=view-vta-partner-list" />
