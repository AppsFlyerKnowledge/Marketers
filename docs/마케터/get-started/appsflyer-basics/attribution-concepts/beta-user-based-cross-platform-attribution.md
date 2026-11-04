---
title: '[베타] 사용자 기반 크로스 플랫폼 어트리뷰션'
metadata:
  keywords:
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - Marketers
    - Cross-Platform Measurement
    - pm-gil-bouchnik
  created_at: '2025-09-16T13:58:09Z'
  edited_at: '2026-10-14T10:28:27Z'
  id: 39104189339793
  locale: ko
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/ko/articles/39104189339793
---
> **한눈에 보기:** 크로스 플랫폼 사용자 기반 어트리뷰션이 무엇인지, 어떻게 작동하는지, 그리고 AppsFlyer에서 설정하는 방법을 알아보세요.

<div id="note" />

<div id="what-is-user-based-attribution" />

## 사용자 기반 어트리뷰션이란?

사용자 기반 어트리뷰션은 <Anchor target="_blank" href="/marketers/ko/docs/customer-user-id-field-cuid">지속적 고객 사용자 ID(CUID)</Anchor>를 기반으로 플랫폼 간 전환 이벤트를 연결하는 크로스 플랫폼 모델입니다. 이 모델은 CUID를 사용하여 모든 활동을 사용자의 첫 번째 전환 이벤트를 유도한 원래의 미디어 소스로 어트리뷰션 합니다.

<div id="a-cross-platform-user-journey-example" />

### 크로스 플랫폼 유저 여정 예시

예를 들어, 사용자가 구글 웹 광고를 클릭하고 가입하여 데스크톱 브라우저에서 구매를 완료합니다. 그런 다음, 동일한 사용자가 인스타그램 모바일 광고를 클릭하고 모바일 앱을 설치하고 또 다른 인앱 구매를 합니다. 일주일 후, 사용자는 브랜드의 CTV 앱을 설치하고, 동일한 CUID를 사용하여 로그인하고, 유료 구독을 시작합니다.

CUID가 플랫폼 전반에 걸쳐 사용자를 일관되게 식별하며, 해당 CUID와 연관된 최초의 논오가닉 런칭 이벤트가 Google 웹 캠페인이었기 때문에, 이후 모든 활동(모바일 앱 구매 및 CTV 구독 포함)은 Google 캠페인에 귀속됩니다.

<div id="user-based-vs-device-based-attribution" />

### 사용자 기반 vs. 기기 기반 어트리뷰션

이 모델은 각 기기를 별개의 사용자로 간주하고 플랫폼 간 사용자 여정을 분할하는 **기기 기반 어트리뷰션**의 주요 한계를 해결합니다. 반면 사용자 중심 어트리뷰션은 지속적 CUID를 활용해 기기 간 이벤트를 연결함으로써 일관된 측정, 정확한 캠페인 기여도 산정, 그리고 전체 제품 라인에 걸친 진정한 고객 생애가치(LTV)를 이해할 수 있습니다.

다음은 기기 중심 어트리뷰션과 유저 중심 어트리뷰션의 차이점을 보여주는 사용자 여정 예시입니다.

[<Image alt="user-journey.png" src="https://files.readme.io/892efd3cdcaa15848baefdd50e65dcdc9448d423e4b6787c067dcbdd5c801dd0-39104359761169.png" width="2048px" />](https://files.readme.io/892efd3cdcaa15848baefdd50e65dcdc9448d423e4b6787c067dcbdd5c801dd0-39104359761169.png)

유저가 웹에서 메타 광고를 클릭하고 광고주의 웹사이트로 리디렉션되어 가입하고 계정을 만듭니다. 나중에 같은 사용자가 광고주의 iOS 앱을 설치하고 로그인하여 $50 구매를 합니다. 며칠 후, 유저는 유튜브 광고를 보고, 광고주의 PC 앱을 설치하고, 다시 로그인하여 $100 구매를 합니다.

기기 기반 어트리뷰션은 Meta Ads에 0달러를, 사용자 기반 어트리뷰션은 150달러를 각각 기여합니다. 아래 표는 이 여정이 각 모델별로 어떻게 어트리뷰션되는지 보여줍니다.

| 구매 인앱 이벤트 | **기기 중심 어트리뷰션** | **사용자 중심 어트리뷰션(CUID)** |
| --- | --- | --- |
| **iOS 앱 구매** ($50) | 어트리뷰션된 **오가닉** (기기에서 이전에 광고 클릭이 수행되지 않음) | **Meta**에 어트리뷰션됨 (초기 웹 광고에서) |
| **PC 앱 구매** ($100) | **YouTube**에 어트리뷰션됨 (최근 기기 수준 상호 작용 기반) | **Meta**에 어트리뷰션됨 (CUID를 통해 식별된 동일 유저) |
| **총 구매액** (150달러) | **오가닉 50달러**, **유튜브 100달러**(캠페인별로 분할) | Meta(단일 통합 소스)에 어트리뷰션된 총 **150달러** |

<div id="what-makes-an-event-a-candidate-for-cross-platform-attribution" />

### 이벤트를 크로스 플랫폼 어트리뷰션 후보로 만드는 요인은 무엇일까요?

이벤트는 **다음 조건**을 모두 충족할 경우 **크로스 플랫폼 어트리뷰션의 대상**이 됩니다:

* **CUID가 존재합니다:** 이벤트는 유효한 <Anchor target="_blank" href="/marketers/ko/docs/customer-user-id-field-cuid">Customer User ID(CUID)</Anchor>를 포함해야 합니다. 광고주가 제공하는 고정 식별자(예: 로그인 ID 또는 해시 처리된 이메일)로 디바이스와 플랫폼 전반에 걸쳐 사용자를 고유하게 식별할 수 있습니다.
  * 이벤트에 CUID가 누락되었지만 동일한 `appsflyer_id`을 공유하는 경우, AppsFlyer는 짧은 처리 시간 내에 CUID를 보충할 수 있습니다. 보충된 CUID는 CUID가 포함된 첫 번째 이벤트가 도착하기 최대 4시간 전까지 소급 적용됩니다. 자세한 내용은 아래의 [CUID enrichment 처리 창](#cuid-보강-처리-기간)을 참조하십시오.
  * CUID 없이 도착하고 CUID 보강 프로세스를 통해 보강할 수 없는 이벤트도 크로스 플랫폼 어트리뷰션에 포함됩니다. 이런 경우, 어트리뷰션은 기기 수준(클래식) 어트리뷰션 방법을 사용하여 결정됩니다.
* **제품군에 속합니다:** 이벤트를 생성하는 앱은 반드시 **제품 라인**에 속해야 합니다. 제품 라인이란 동일한 브랜드 아래에서 속성 범위가 지정되고 일괄적으로 구성된 관련 앱(예: iOS, Android, CTV)의 집합을 의미합니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/product-line-group-apps-for-cross-platform-attribution#about-product-line">크로스 플랫폼 어트리뷰션을 위한 앱 그룹화</Anchor> 항목을 참조하십시오.
* **비활성 복원 윈도우 내에서:** 이벤트는 설정 가능한 기간(예: 7&#126;390일)으로 정의된 **비활성 기간(inactivity window)** 내에 포함되어야 합니다. 이 기간 동안 CUID는 여전히 활성으로 간주되며, 지정된 제품 라인 내에서 어트리뷰션 대상이 됩니다. 이 윈도우 내에 CUID가 보이지 않으면 이전 어트리뷰션 매핑이 무시됩니다.
* **기기 수준 어트리뷰션 필드가 있습니다:** 이벤트는 이미 AppsFlyer의 전통적인 기기 기반 어트리뷰션 모델에서 파생된 유효한 **기기 수준 어트리뷰션 파라미터**(예: 미디어 소스, 캠페인 ID)를 포함해야 합니다.

<div id="note-1" />

<div id="how-is-the-attribution-source-determined" />

### 어트리뷰션 소스는 어떻게 결정되나요?

이 모델은 지정된 사용자(CUID)에 대한 모든 이벤트를 사용자의 첫 번째 전환을 유도한 **오리지널 미디어소스**에 어트리뷰트합니다.

어트리뷰션된 원래 미디어소스는 다음과 같은 로직을 사용하여 결정됩니다.

* 제품 라인 내 CUID가 포함된 각 인앱 이벤트에 대해, AppsFlyer는 해당 CUID의 **가장 초기**런치 이벤트(즉, 유효한 미디어 소스가 있는 런치 이벤트)를 식별합니다.
* 전통적인 기기 중심 어트리뷰션에 의해 해당 실행 이벤트에 어트리뷰트된 미디어 소스는 해당 인앱 이벤트의 어트리뷰션 소스로 간주됩니다.
* 이 미디어소스는 해당 CUID 및 제품군과 연관된 모든 후속 이벤트에 대해 **사용자 유입 크로스 플랫폼 어트리뷰션 소스**로 사용됩니다.
* 앱 내 이벤트에 CUID가 누락된 경우, AppsFlyer는 1&#126;4시간의 [보강 처리 기간](#cuid-보강-처리-기간) 동안 이를 보충하려고 시도합니다.
* CUID가 없는 이벤트가 정의된 CUID [보강 기간](#cuid-보강-처리-기간) 이외에 도착하는 경우 여전히 크로스 플랫폼 어트리뷰션에 포함됩니다. 이러한 이벤트는 기기 수준(클래식) 어트리뷰션 방법을 사용하여 어트리뷰션됩니다.

> 📘 **참고**
>
> AppsFlyer는 동일한 제품군 **내에서** 동일한 CUID를 매칭합니다. 앱스플라이어는 다른 제품군이나 다른 고객을 대상으로 CUID를 매칭, 추정 또는 공유하지 않습니다. 이는 엄격한 개인정보 보호 우선 접근 방식을 보장하며, 각 고객의 데이터를 분리된 독립적인 상태로 유지합니다.

<div id="tip" />

<div id="the-cuid-enrichment-processing-window" />

#### CUID 보강 처리 기간

CUID 보충 처리 창은 AppsFlyer가 새로 도착한 인앱 이벤트를 처리하여 누락된 고객 사용자 ID(CUID)를 보충하는 기간(1&#126;4시간)입니다. 이는 CUID 없이 일부 인앱 이벤트가 도착하는 경우에도 크로스 플랫폼 어트리뷰션을 가능하게 합니다.

**CUID enrichment(보강)은 어떻게 이루어지나요**

* AppsFlyer는 1&#126;4시간마다 프로세싱 작업을 수행합니다.
* CUID 없이 이벤트가 도착했지만 다른 이벤트와 동일한 `appsflyer_id`을 공유한 경우 AppsFlyer는 누락된 CUID를 추후 보충합니다.
* 이 스티칭은 처리 기간 동안 수신된 이벤트에만 적용됩니다.

**CUID 보강 예시**

* **8:01**: *첫 번째 앱 오픈* 이벤트는 `appsflyer_id = XYZ`로 기록됩니다.
* **9:00**: *가입* 이벤트는 `cuid = 123` 및 `appsflyer_id = XYZ`로 기록됩니다.
* **12:00**: 4시간의 처리 기간이 종료됩니다. 앱스플라이어는 소급적으로 `cuid = 123`을 *첫 번째 앱 오픈* 이벤트와 연결합니다.
* **12:30**: *구매* 이벤트는 `appsflyer_id = XYZ`에 기록되지만 CUID는 없습니다. 이벤트가 창이 닫힌 후에 도착하기 때문에 AppsFlyer는 `cuid = 123`에 스티칭하지 않습니다.

**CUID 보강 제한 사항**

* CUID가 없는 이벤트가 **1&#126;4시간 처리 시간대를 벗어난 경우,** 클래식 AppsFlyer 어트리뷰션 방식을 사용하여 어트리뷰션 처리되며 크로스 플랫폼 어트리뷰션 방법 결과에 추가됩니다.
* CUID 스티칭은 처리 기간 이후로 **소급 적용되지 않습니다.**

> 👍 **팁**
>
> 크로스 플랫폼 매칭을 극대화하려면 전송되는 모든 인앱 이벤트에 항상 CUID를 포함해야 합니다.

<div id="set-up-cross-platform-attribution" />

## 크로스 플랫폼 어트리뷰션 설정

크로스 플랫폼 어트리뷰션을 설정하려면 AppsFlyer에서 몇 가지 설정을 적용하고 앱 코드에 특정 SDK 기능을 구현해야 합니다.

* **앱스플라이어에서** 앱을 제품 라인에 할당하고, 크로스 플랫폼 어트리뷰션을 선택하고, 비활성화 복구 기간을 지정합니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/product-line-group-apps-for-cross-platform-attribution#how-to-set-up-a-product-line">제품 라인 설정</Anchor>을 참조하십시오.
* 앱스플라이어 SDK를 CUID와 함께 이벤트를 보내도록 **앱에서** 설정합니다. 개발사 지침은 [고객 사용자 ID 설정](https://dev.appsflyer.com/hc/docs/set-customer-user-id) 항목을 참조하십시오.

<div id="different-attribution-date" />

<div id="different-attribution-logic" />

<div id="frequently-asked-questions-faqs" />

<div id="view-cross-platform-attribution-results" />

## 크로스 플랫폼 어트리뷰션 결과 보기

* 크로스 플랫폼 어트리뷰션 결과를 보려면 <Anchor target="_blank" href="/marketers/ko/docs/end-user-events-cross-platform-report-in-data-locker">데이터 락커 엔드 유저 이벤트 크로스 플랫폼 리포트</Anchor>를 참조하십시오.
* (예정) 마이 대시보드에서 사용할 수 있는 새로운 어트리뷰션 방법

.

<div data-zendesk-anchors="what-is-userbased-attribution=%EC%82%AC%EC%9A%A9%EC%9E%90-%EA%B8%B0%EB%B0%98-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98%EC%9D%B4%EB%9E%80 h_01K59D3JXN9P5ZN40WX957CHKC=%EC%82%AC%EC%9A%A9%EC%9E%90-%EA%B8%B0%EB%B0%98-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98%EC%9D%B4%EB%9E%80 a-crossplatform-user-journey-example=%ED%81%AC%EB%A1%9C%EC%8A%A4-%ED%94%8C%EB%9E%AB%ED%8F%BC-%EC%9C%A0%EC%A0%80-%EC%97%AC%EC%A0%95-%EC%98%88%EC%8B%9C h_01K59D3JXN4WJ3HN0AXN58N877=%ED%81%AC%EB%A1%9C%EC%8A%A4-%ED%94%8C%EB%9E%AB%ED%8F%BC-%EC%9C%A0%EC%A0%80-%EC%97%AC%EC%A0%95-%EC%98%88%EC%8B%9C userbased-vs-devicebased-attribution=%EC%82%AC%EC%9A%A9%EC%9E%90-%EA%B8%B0%EB%B0%98-vs-%EA%B8%B0%EA%B8%B0-%EA%B8%B0%EB%B0%98-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 h_01K59D3JXN3EXS90N2AX7DXV3B=%EC%82%AC%EC%9A%A9%EC%9E%90-%EA%B8%B0%EB%B0%98-vs-%EA%B8%B0%EA%B8%B0-%EA%B8%B0%EB%B0%98-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 what-makes-an-event-a-candidate-for-crossplatform-attribution=%EC%9D%B4%EB%B2%A4%ED%8A%B8%EB%A5%BC-%ED%81%AC%EB%A1%9C%EC%8A%A4-%ED%94%8C%EB%9E%AB%ED%8F%BC-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%9B%84%EB%B3%B4%EB%A1%9C-%EB%A7%8C%EB%93%9C%EB%8A%94-%EC%9A%94%EC%9D%B8%EC%9D%80-%EB%AC%B4%EC%97%87%EC%9D%BC%EA%B9%8C%EC%9A%94 h_01K59D3JXNNYZHYFAPRH50E4Z4=%EC%9D%B4%EB%B2%A4%ED%8A%B8%EB%A5%BC-%ED%81%AC%EB%A1%9C%EC%8A%A4-%ED%94%8C%EB%9E%AB%ED%8F%BC-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%9B%84%EB%B3%B4%EB%A1%9C-%EB%A7%8C%EB%93%9C%EB%8A%94-%EC%9A%94%EC%9D%B8%EC%9D%80-%EB%AC%B4%EC%97%87%EC%9D%BC%EA%B9%8C%EC%9A%94 how-is-the-attribution-source-determined=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%86%8C%EC%8A%A4%EB%8A%94-%EC%96%B4%EB%96%BB%EA%B2%8C-%EA%B2%B0%EC%A0%95%EB%90%98%EB%82%98%EC%9A%94 h_01K59D3JXNGNZYAYPG13SZ98V1=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%86%8C%EC%8A%A4%EB%8A%94-%EC%96%B4%EB%96%BB%EA%B2%8C-%EA%B2%B0%EC%A0%95%EB%90%98%EB%82%98%EC%9A%94 h_01K59D3JXNG9KDQ11QPNK3Z0EW=%EC%B0%B8%EA%B3%A0 the-cuid-enrichment-processing-window=cuid-%EB%B3%B4%EA%B0%95-%EC%B2%98%EB%A6%AC-%EA%B8%B0%EA%B0%84 h_01K59D3JXN5CYVB6F84DTRBZS9=cuid-%EB%B3%B4%EA%B0%95-%EC%B2%98%EB%A6%AC-%EA%B8%B0%EA%B0%84 h_01K6ZF1RRQ47HAFZNP4RK083W9=%ED%8C%81 set-up-crossplatform-attribution=%ED%81%AC%EB%A1%9C%EC%8A%A4-%ED%94%8C%EB%9E%AB%ED%8F%BC-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%84%A4%EC%A0%95 h_01K59D3JXNH84WMZ6PQ4BVF44B=%ED%81%AC%EB%A1%9C%EC%8A%A4-%ED%94%8C%EB%9E%AB%ED%8F%BC-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%84%A4%EC%A0%95 view-crossplatform-attribution-results=%ED%81%AC%EB%A1%9C%EC%8A%A4-%ED%94%8C%EB%9E%AB%ED%8F%BC-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EA%B2%B0%EA%B3%BC-%EB%B3%B4%EA%B8%B0 h_01K59D3JXNGGG4AKEXM9Q9KA6A=%ED%81%AC%EB%A1%9C%EC%8A%A4-%ED%94%8C%EB%9E%AB%ED%8F%BC-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EA%B2%B0%EA%B3%BC-%EB%B3%B4%EA%B8%B0" />
