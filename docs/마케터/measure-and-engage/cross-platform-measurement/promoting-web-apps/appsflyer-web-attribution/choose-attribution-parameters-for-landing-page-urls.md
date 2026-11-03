---
title: 랜딩 페이지 URL에 사용할 어트리뷰션 파라미터 선택
metadata:
  keywords:
    - Agencies
    - Web Attribution
    - Web Attribution SDK
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
    - Agencies
  created_at: '2026-02-04T16:46:08Z'
  edited_at: '2026-10-22T14:44:12Z'
  id: 43525434385809
  locale: ko
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/ko/articles/43525434385809
---
> **한눈에 보기:** 웹사이트 랜딩 페이지 링크에 일관되고 완전한 URL 파라미터를 사용하여 웹 성과 측정에서 정확한 기여를 유지하는 동시에 최적의 캠페인 세분성을 확보하세요.

## URL 어트리뷰션 파라미터 클래스 안내

앱스플라이어는 랜딩 페이지 URL(사용자가 클릭하는 링크)에서 캠페인 파라미터를 읽어 세션과 이벤트를 올바른 **미디어 소스**, **캠페인**, 그리고 (가능한 경우) **광고 세트** 및 **광고**와 같은 하위 계층에 어트리뷰션합니다.

포함하는 파라미터에 따라 캠페인의 측정 결과가 결정됩니다. 즉, 동일한 랜딩 페이지라도 포함하는 파라미터에 따라 매우 다른 결과가 나올 수 있습니다.

URL 파라미터는 PID와 UTM의 두 가지 클래스 중 하나에 속할 수 있습니다.

* PID 클래스에는 앱스플라이어 URL 파라미터가 포함됩니다.
* UTM 클래스에는 표준 UTM 파라미터가 포함됩니다.

웹 성과 측정이 URL 파라미터를 처리하는 방식에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/about-traffic-source-resolution">트래픽 소스 확인 정보</Anchor>를 참조하세요.

### 지원된 PID 및 UTM 파라미터

웹 성과 측정은 다음 파라미터를 지원합니다.

| # | 파라미터 | 사용처 | 파라미터 클래스 | 대시보드에서 사용가능 여부 | 로우 데이터 필드 |
| --- | --- | --- | --- | --- | --- |
| 1 | `pid` | 미디어 소스 | PID | 네 | `media_source` |
| 2 | `c` | 캠페인 이름 | PID | 네 | `campaign_name` |
| 3 | `af_c_id` | 캠페인 ID | PID | 네 | `campaign_id` |
| 4 | `af_adset` | 광고 세트 이름 | PID | 네 | `adset_name` |
| 5 | `af_adset_id` | 광고 세트 ID | PID | 네 | `adset_id` |
| 6 | `af_ad` | 광고 이름 | PID | 네 | `ad_name` |
| 7 | `af_ad_id` | 광고 ID | PID | 네 | `ad_id` |
| 8 | `utm_source` | 미디어 소스 | UTM | 네 | `media_source` |
| 9 | `utm_medium` | 미디어 유형 | UTM | 아니오 | `media_type` |
| 10 | `utm_campaign` | 캠페인 이름 | UTM | 네 | `campaign_name` |

## 올바른 어트리뷰션 파라미터 선택

앱스플라이어는 특정 우선순위 워터폴을 사용하여 보고 필드(미디어 소스 또는 캠페인 등)별로 URL 파라미터를 독립적으로 평가합니다. 이 방식을 사용하면 동일한 URL에서 **PID 클래스**(앱스플라이어 기본)와 **UTM 클래스**(표준 마케팅)를 모두 활용하여 Google Analytics와 같은 다른 툴과 함께 앱스플라이어 어트리뷰션을 동시에 지원할 수 있습니다.

웹 성과 측정은 각 필드의 우선순위를 개별적으로 점검합니다. 특정 특성에 대해 우선순위가 더 높은 PID 클래스의 파라미터가 없는 경우, 시스템은 해당 필드의 올바른 값을 결정하기 위해 UTM 클래스의 대응하는 파라미터로 자동 전환됩니다.

<div id="scenario-a-url-with-pid-class-only-appsflyer-reporting" />

<Accordion title="시나리오 A. PID 클래스만 사용한 URL (앱스플라이어 리포팅)">

앱스플라이어 리포팅이 주목적인 경우 PID 클래스를 사용하세요.

#### 예시

```http
www.website.com?pid=facebook_int&c={{campaign.name}}&af_c_id={{campaign.id}}
```

**결과**: 앱스플라이어는 `pid`를 사용하여 미디어 소스를 확인하고 `c`를 사용하여 캠페인을 식별합니다.

</Accordion>

<div id="scenario-b-url-with-utm-class-only-fallback" />

<Accordion title="시나리오 B. UTM 클래스만 사용한 URL(폴백)">

`pid`가 누락된 경우, 앱스플라이어는 UTM 클래스로 전환됩니다.

#### 예시

```http
 www.website.com?utm_source=facebook&utm_medium=paidsocial&utm_campaign={{campaign.name}}
```

**결과**: 앱스플라이어는 `utm_source`를 사용하여 미디어 소스를 확인하고 `utm_campaign`을 사용하여 캠페인을 식별합니다.

</Accordion>

<div id="scenario-c-url-with-both-pid-and-utm-classes" />

<Accordion title="시나리오 C. PID 클래스와 UTM 클래스를 모두 사용한 URL">

앱스플라이어를 사용하면 동일한 URL 내에 서로 다른 클래스(예: PID 및 UTM)의 파라미터를 포함할 수 있습니다. 이는 Google Analytics나 자체 측정 시스템과 같은 다른 분석 툴과 함께 앱스플라이어 어트리뷰션을 함께 지원해야 할 때 유용합니다.

앱스플라이어는 미디어 소스 및 캠페인과 같은 어트리뷰션 필드를 독립적으로 처리합니다. 각 특정 필드에 대해 시스템은 특정 우선순위 워터폴을 따라 기록할 값을 결정합니다. 일반적으로 해당 특정 필드에 대해 **PID 클래스**가 **UTM 클래스**보다 우선 적용됩니다.

#### 예시 1: 중복되는 파라미터

```http
www.website.com?pid=facebook_ads&c=summer_sale&utm_source=facebook&utm_campaign=seasonal_promo
```

* **미디어 소스:** 앱스플라이어가 `pid`와 `utm_source`를 모두 감지합니다. 이 필드의 우선순위 워터폴에 따라 `facebook_ads`를 기록합니다.
* **캠페인:** 앱스플라이어가 `c`와 `utm_campaign`을 모두 감지합니다. 이 필드의 우선순위 워터폴에 따라 `summer_sale`을 기록합니다.
* **결과:** 앱스플라이어는 우선순위가 더 높은 PID 클래스 값을 사용하고, 외부 도구는 여전히 UTM 값을 읽을 수 있습니다.

#### 예시 2: 혼합된 파라미터 클래스

```http
www.website.com?utm_source=facebook&c=summer_sale
```

* **미디어 소스:** 앱스플라이어가 `utm_source`를 감지합니다. PID 클래스에 해당하는 파라미터(`pid`)가 없으므로, UTM 클래스의 `facebook`을 기록합니다.
* **캠페인:** 앱스플라이어가 `c`를 감지합니다. UTM 클래스에 해당하는 파라미터(`utm_campaign`)가 없으므로, PID 클래스의 `summer_sale`을 기록합니다.
* **결과:** 각 필드가 독립적으로 처리되므로 앱스플라이어는 두 클래스의 값을 모두 사용하여 이벤트를 성공적으로 어트리뷰션합니다.

</Accordion>

## 기타 모범 사례

<div id="keep-parameter-values-in-a-consistent-case" />

<Accordion title="파라미터 값을 일관된 대소문자로 유지하세요">

파라미터 값은 **대소문자를 구별**합니다. 예를 들어, `utm_source=channel1`과 `utm_source=CHANNEL1`은 **서로 다른 미디어 소스**로 처리됩니다.

권장 사항: 대소문자 표기 규칙(주로 소문자 사용)을 정의하고 모든 URL에 일관되게 적용하세요.

</Accordion>

<div id="use-question-marks-only-once" />

<Accordion title="물음표 한 번만 사용">

규칙:

* URL의 쿼리 파라미터 앞에는 **단 하나**의 물음표(`?` )만 사용하세요.
* URL에 추가적인 물음표를 사용하지 마세요.

올바른 방법:

* `www.website.com?parameters`

틀린 방법:

* `www.website.com??parameters`
* `www.website.com?parameter1?parameter2`

</Accordion>

<div id="don-t-use-anchor-signs" />

<Accordion title="앵커 기호(#)를 사용하지 마세요">

URL에 앵커 기호(`#`)를 사용하지 마세요.

이유: `#` 뒤에 오는 파라미터는 로드되지 않을 수 있으며 웹 SDK에 의해 기록되지 않을 수 있습니다.

</Accordion>

<div data-zendesk-anchors="about-website-attribution-urls=url-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0-%ED%81%B4%EB%9E%98%EC%8A%A4-%EC%95%88%EB%82%B4 h_01KGMRXNWGXQ3CH5XGSREV6Z3R=url-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0-%ED%81%B4%EB%9E%98%EC%8A%A4-%EC%95%88%EB%82%B4 supported-pid-and-utm-parameters=%EC%A7%80%EC%9B%90%EB%90%9C-pid-%EB%B0%8F-utm-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 h_01KGMRXNWG88REW1CVJ4XMYFHQ=%EC%A7%80%EC%9B%90%EB%90%9C-pid-%EB%B0%8F-utm-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 choose-the-right-attribution-parameters=%EC%98%AC%EB%B0%94%EB%A5%B8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0-%EC%84%A0%ED%83%9D h_01KGMRXNWGP1SFBWE3KG6VRZ9V=%EC%98%AC%EB%B0%94%EB%A5%B8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0-%EC%84%A0%ED%83%9D h_01KGMRXNWGT9MS799QH9EP29XR=scenario-a-url-with-pid-class-only-appsflyer-reporting example=%EC%98%88%EC%8B%9C h_01KGMS1RMN3F1D0Q7HDZMGG19E=%EC%98%88%EC%8B%9C h_01KGMRXNWG0T3YCK0RPKX4B3BT=scenario-b-url-with-utm-class-only-fallback example::4f5c28b5=%EC%98%88%EC%8B%9C-1 h_01KGMS215ARDSY6NFQ8VEF6C2Y=%EC%98%88%EC%8B%9C-1 h_01KGMRXNWGZH2ZBP9XR8C8TNFN=scenario-c-url-with-both-pid-and-utm-classes example-1-overlapping-parameters=%EC%98%88%EC%8B%9C-1-%EC%A4%91%EB%B3%B5%EB%90%98%EB%8A%94-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 h_01KGMS10B1QCRJ5N28FBNEEKR2=%EC%98%88%EC%8B%9C-1-%EC%A4%91%EB%B3%B5%EB%90%98%EB%8A%94-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 example-2-mixed-parameter-classes=%EC%98%88%EC%8B%9C-2-%ED%98%BC%ED%95%A9%EB%90%9C-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0-%ED%81%B4%EB%9E%98%EC%8A%A4 h_01KGMS17B500RPGHSKJ1AJSYH8=%EC%98%88%EC%8B%9C-2-%ED%98%BC%ED%95%A9%EB%90%9C-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0-%ED%81%B4%EB%9E%98%EC%8A%A4 other-best-practices=%EA%B8%B0%ED%83%80-%EB%AA%A8%EB%B2%94-%EC%82%AC%EB%A1%80 h_01KGMRXNWGVJY55M83FVMKBP1X=%EA%B8%B0%ED%83%80-%EB%AA%A8%EB%B2%94-%EC%82%AC%EB%A1%80 h_01KGMRXNWG9S03GGBDXPN34DDM=keep-parameter-values-in-a-consistent-case h_01KGMRXNWGEF9D0ZH5M81RP0PH=use-question-marks-only-once don%E2%80%99t-use-anchor-signs-=don-t-use-anchor-signs h_01KGMRXNWGX6HA0R9X3VC2WFXV=don-t-use-anchor-signs" />
