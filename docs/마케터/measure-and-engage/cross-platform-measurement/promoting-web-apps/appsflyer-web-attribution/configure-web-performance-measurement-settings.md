---
title: 웹 성과 측정 설정 구성
metadata:
  keywords:
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
  created_at: '2026-02-05T08:47:53Z'
  edited_at: '2026-10-25T13:07:06Z'
  id: 43541863890961
  locale: ko
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/ko/articles/43541863890961
---
> **한눈에 보기:** 웹 어트리뷰션 설정을 구성하여 앱스플라이어가 웹사이트 방문, 전환, 사용자 활동을 마케팅 캠페인에 기여하는 방식을 제어하세요. 설정 항목에는 어트리뷰션 윈도우, 사용자 획득 이벤트, 리인게이지먼트 규칙, 도메인 제외가 포함됩니다.

<div id="overview" />

## 개요

웹 어트리뷰션 설정은 앱스플라이어가 웹사이트 내 사용자 활동을 측정하고 기여도를 산정하는 방식을 정의합니다. 이러한 설정은 다음 항목들을 결정합니다.

* 어떤 이벤트가 사용자 획득으로 인정되나요?
* 이후 발생하는 이벤트를 마케팅 유입 경로에 어트리뷰션하는 기간.
* 사용자를 복귀(리인게이지먼트) 또는 재획득으로 간주하는 시점.
* 어트리뷰션에서 제외할 도메인.

<div id="who-should-configure-these-settings" />

### 해당 설정을 구성해야 하는 담당자

일반적으로 마케팅 팀과 그로스 매니저가 비즈니스 목표에 따라 이러한 설정을 구성합니다. SDK 연동 및 도메인 설정을 위해 기술 팀이 관여할 수 있습니다.

<div id="accessing-web-attribution-settings" />

### 웹 어트리뷰션 설정 접근

웹 앱의 어트리뷰션 설정에 접근하려면:

1. 앱스플라이어에서 **My Apps**로 이동
2. 목록에서 웹 앱 선택
3. **앱 설정** > **어트리뷰션**으로 이동

<div id="quick-reference" />

## 빠른 참조

| 설정 | 기본 | 옵션 | 편집 가능 여부 | 통제 항목 |
| --- | --- | --- | --- | --- |
| 앱 이름 | 사용자 인풋 | 1-100자 | 네 | 앱스플라이어 표시 이름 |
| 전체 URL(기본 도메인) | 사용자 인풋 | 1-500자 | 아니오 | 앱 식별자 및 기본 제외된 도메인 |
| Web SDK ID | 자동 생성 | 1-550자 | 아니오 | 이벤트 콜렉션의 SDK 식별자 |
| 통화 | 사용자 선택 | ISO 코드 | 네 | 매출 및 ROI 리포팅 |
| 시간대 | 사용자 선택 | IANA 존 | 제한됨 | 리포팅 타임스탬프 |
| 사용자 획득 이밴트 | 첫 방문 | 이벤트 이름 | 네 | 사용자가 획득되었다고 판단될 때 |
| 룩백 윈도우(UA) | 30일 | 1시간 - 90일 | 네 | UA 획득 지점 역추적 기간 |
| 리인게이지먼트 윈도우 | 30일 | 1시간 - 90일 | 네 | 리타게팅에 기여도를 인정하는 기간 |
| 비활성 윈도우(리인게이지먼트) | 비활성화 됨 | 0-30일 | 네 | 리타게팅을 위한 최소 비활성 기간 |
| 어트리뷰션 윈도우 | 생애 | 프리셋 옵션 | 네 | 이벤트가 UA로 어트리뷰션되는 기간 |
| 비활성 윈도우(재획득) | 90일 | 1-180일 | 네 | 사용자가 이탈한 것으로 간주되는 시점 |
| 재획득 이벤트 | 방문 | 이벤트 이름 | 네 | 이탈한 사용자를 다시 돌아오게 만드는 요인 |
| 제외된 도메인 | 기본만 | 최대 100 | 네 | 어트리뷰션에서 제외되는 도메인 |

**제약 조건:**  
리인게이지먼트 비활성 윈도우는 재획득 비활성 윈도우보다 **짧거나 같아야** 합니다. 그렇지 않으면 사용자가 리타게팅 대상 자격을 갖추기 전에 재획득될 수 있습니다.

<div id="basic-settings" />

## **기본 설정**

웹 앱 기본 설정:

* 앱 이름
* 전체 URL
* Web SDK ID
* 통화
* 시간대

더 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/adding-an-app-to-appsflyer#web">앱스를라이어에 앱 추가하기</Anchor>를 참고하세요.

<div id="user-acquisition-settings" />

## 사용자 획득 설정

사용자 획득(UA) 설정은 사용자가 처음 획득된 시점을 앱스플라이어가 식별하는 방식과 해당 획득 성과를 마케팅 소스에 어트리뷰션하는 방식을 결정합니다.

<div id="user-acquisition-event" />

<Accordion title="사용자 획득 이벤트">

사용자 획득을 유발하는 이벤트입니다. 이는 사용자가 진정으로 "획득"되었다고 간주하는 기준을 정의하는 중요한 비즈니스 액션입니다.

<div id="why-customize" />

#### 사용자 지정하는 이유

기본값인 **첫 방문** 은 사용자의 가치를 판단하기에 다소 약한 신호인 경우가 많습니다. 사용자가 실수로 광고를 클릭했거나 즉시 이탈했을 수 있습니다. 이 설정을 맞춤 구성하면 단순한 호기심성 클릭이 아닌 의미 있는 액션을 유도한 마케팅 소스에 고객 생애 가치(LTV)가 어트리뷰션되도록 보장할 수 있습니다.

**기본값:** 첫 방문(사용자가 웹사이트를 처음 방문할 때 획득된 것으로 처리)

<div id="common-alternatives-by-industry" />

#### 산업군 별 일반적인 대안

| **산업군** | **권장 UA 이벤트** |
| --- | --- |
| 은행/금융 | registration 또는 first\_time\_deposit |
| 이커머스 | sign\_up 또는 first\_purchase |
| 음식 배달 | first\_order |
| SaaS/구독 | subscription\_start |
| 게이밍 | sign\_up ortutorial\_complete 또는 first\_purchase |

<div id="how-it-works" />

#### 작동 장법

**첫 방문**으로 설정하면:

* 사용자가 웹사이트를 처음 방문하는 즉시 획득 처리됩니다.
* 어트리뷰션은 첫 방문 시점부터 시작됩니다.

사용자 지정 이벤트로 설정하면(예: sign\_up):

* 사용자는 첫 방문부터 해당 이벤트를 수행할 때까지 **"사전 획득 기간(pre-acquisition period)**"에 진입합니다.
* 사전 획득 기간 동안 발생하는 이벤트는 룩백 윈도우 내의 마지막 논오가닉 접점에 어트리뷰션됩니다(라스트 터치 어트리뷰션).
* 맞춤 UA 이벤트가 발생하면 **User Acquisition 전환**이 생성되고 장기 어트리뷰션이 시작됩니다.

<div id="example-scenario-ua-event--sign_up" />

#### 예시 시나리오(UA 이벤트 = sign\_up):

* **0일 차:** 사용자가 Facebook 광고를 통해 방문 → 사전 획득 기간 시작
* **2일 차:** 사용자가 Google 광고를 통해 방문 → 기여도가 Google로 전환(라스트 터치)
* **3일 차:** 사용자 회원가입 완료 → 사용자 획득 성과가 Google 광고에 어트리뷰션됨

**10일 차:** 사용자 구매 발생 → LTV 측정을 위해 해당 구매가 Google에 어트리뷰션됨

</Accordion>

<div id="lookback-window-user-acquisition" />

<Accordion title="룩백 윈도우(사용자 획득)">

앱스플라이어가 사용자 획득을 유도한 마케팅 접점을 찾기 위해 과거로 소급하여 조회하는 기간입니다.

이 윈도우는 앱스플라이어가 마케팅 접점을 "기억"하는 유효 기간을 제어합니다. 사용자가 광고를 통해 유입되었으나 일정 시간이 지난 후에야 UA 이벤트를 완료한 경우, 해당 광고에 계속 기여도를 부여할지 여부를 이 설정으로 결정합니다.

기본: 30일

범위: 1시간에서 90일

<div id="how-it-works-1" />

#### 작동 방법

사용자가 UA 이벤트(예: sign\_up)를 수행하면, 앱스플라이어는 이 윈도우 기간 내를 역추적하여 가장 최근의 논오가닉 접점을 찾고 해당 마케팅 소스에 획득 성과를 어트리뷰션합니다.

<div id="example-1-30-day-lookback" />

#### 예시 1(30일 룩백):

* **Day 0:** 사용자가 Facebook 광고를 클릭하고 웹사이트를 방문함
* **Day 25:** 사용자가 직접 재방문하여 sign\_up 이벤트를 완료함
* **결과:** 사용자 획득이 Facebook에 어트리뷰션됨 (30일 룩백 윈도우 이내)

<div id="example-2-window-expired" />

#### 예시 2(윈도우 만료)

* **Day 0:** 사용자가 Facebook 광고를 클릭하고 웹사이트를 방문함
* **Day 40:** 사용자가 직접 재방문하여 sign\_up 이벤트를 완료함

**결과:** 사용자 획득이 오가닉(organic)으로 표시됨 (30일 룩백 윈도우 초과)

</Accordion>

<div id="re-engagement-settings" />

## 리인게이지먼트 설정

리인게이지먼트 설정은 이미 획득된 사용자가 리타게팅 캠페인을 통해 웹사이트로 다시 돌아올 때 앱스플라이어가 활동 기여도를 어트리뷰션하는 방식을 제어합니다.

<div id="reengagement-window-item" />

<Accordion title="리인게이지먼트 윈도우">

리인게이지먼트 전환 발생 후 앱스플라이어가 해당 마케팅 접점에 이벤트 기여도를 계속해서 어트리뷰션하는 기간입니다.

이 설정은 리타게팅 캠페인이 사용자의 활동에 대해 성과 기여를 인정받는 기간을 결정합니다. 리타게팅 활동에 기여도를 부여하는 동시에, 장기적인 LTV는 최초 획득 소스로 귀속시키는 균형을 유지합니다.

**기본:** 30일

**범위:** 1시간 - 90일

<div id="how-it-works-2" />

#### 작동 방법

이미 획득된 사용자가 논오가닉 소스(예: 리타게팅 광고)를 통해 재방문하고 리인게이지먼트 기준을 충족하면 **리타게팅 전환**이 생성됩니다. 이 윈도우 기간 내에 발생하는 이벤트는 **이중 어트리뷰션(dual attribution)** 을 적용받습니다.

1. **기본 어트리뷰션** → 리타게팅 캠페인
   * 목적: 리타게팅 캠페인 크레딧
2. **보조 어트리뷰션** → 오리지널 UA 소스
   * 목적: 최초 획득 시점부터 사용자의 전체 생애 가치(LTV)를 측정하는 UA 뷰 지원

<div id="example-within-window" />

#### 예(윈도우 동안):

* **Day 0:** Facebook 광고를 통해 사용자 획득
* **Day 50:** 사용자가 이메일 리타게팅 캠페인을 클릭하고 재방문(리타게팅 전환 생성)
* **Day 60:** 사용자가 100달러 구매 발생 (리타게팅 후 10일 시점)
* **결과 - 이중 어트리뷰션**
  * **기본(리타게팅 뷰):** 이메일 캠페인이 100달러 구매에 대한 기여도를 인정받음
  * **보조(UA 뷰):** 사용자의 LTV 내 100달러가 Facebook 광고 성과로도 함께 추적됨
* **보고서**
  * 통합 뷰: 이메일에 어트리뷰션된 구매로 표시
  * 리타게팅 뷰: 이메일에 어트리뷰션된 구매로 표시
  * UA 뷰: Facebook에 어트리뷰션된 구매로 표시

</Accordion>

<div id="inactivity-window-for-reengagement" />

<Accordion title="리인게이지먼트 비활성 윈도우">

논오가닉 접점이 리인게이지먼트(리타게팅) 전환을 생성하기 위해 충족해야 하는 사용자의 최소 비활성 기간입니다.

사용자가 이미 웹사이트에서 활발히 활동 중인 경우 리타게팅 캠페인에 기여도가 인정되는 것을 방지합니다. 캠페인이 진정으로 비활성 상태인 사용자만을 타게팅하도록 보장함으로써 리타게팅 예산을 최적화합니다.

**기본:** 비활성화

**범위:** 0(비활성화) - 30일

<div id="how-it-works-3" />

#### 작동 방법

**비활성화 시:**

* 이미 획득된 사용자의 모든 논오가닉 접점이 리타게팅 전환을 생성합니다.

**활성화 시(예: 7일)**

* 사용자가 최소 7일 동안 비활성 상태였던 경우에만 리타게팅 전환을 생성합니다.
* 사용자가 최근에 활동한 경우, 해당 방문은 리타게팅 대신 최초 UA 소스에 어트리뷰션됩니다.

**제약 사항**

* 비활성 윈도우(재획득)를 초과할 수 없음

<div id="example-7-day-inactivity-window" />

#### 예(7일 비활성 윈도우):

* **Day 0:** Facebook 광고를 통해 사용자 획득
* **Day 3:** 사용자가 오가닉으로 방문
* **Day 5:** 사용자가 리타게팅 광고를 클릭함 → **리타게팅 전환 미발생** (비활성 기간 2일에 불과)
* **Day 15:** 사용자가 리타게팅 광고를 클릭함 → **리타게팅 전환 생성** (12일 동안 비활성 상태)

</Accordion>

<div id="re-acquisition-settings" />

## 재획득 설정

재획득 설정은 비활성 사용자가 "이탈"된 것으로 간주되는 시점과 이들을 재획득 사용자로 다시 유입시키는 방식을 정의합니다.

<div id="inactivity-window-reacquisition" />

<Accordion title="비활성 윈도우(재획득)">

사용자가 "이탈" 상태로 표시되기까지 필요한 완전한 비활성 기간입니다. 이탈한 사용자는 다시 재획득될 수 있으며, 이때 새로운 UA 전환이 생성됩니다.

이 설정은 비즈니스의 이탈 임계치를 정의합니다. 사용자가 "이탈"된 것으로 간주되어 재획득 대상 자격을 얻는 시점을 결정함으로써, 윈백 캠페인이 이탈 사용자를 복귀시킨 성과 기여도를 인정받을 수 있도록 합니다.

**기본:** 90일

**범위:** 1일에서 180일

<div id="how-it-works-4" />

#### 작동 방법

**사용자가 이탈 상태로 표시되는 경우:**

* 신규 이벤트에 대해 해당 사용자가 더 이상 기존 최초 UA 소스에 어트리뷰션되지 않음
* 사용자가 "사전 획득" 상태로 진입함(재획득 대기 상태)
* 최초 획득 시점의 어트리뷰션 윈도우가 더 이상 적용되지 않음

**이탈 사용자가 복귀할 때:**

* 사용자가 재획득 이벤트를 수행하는 경우 → 새로운 UA 전환 생성
* 윈백 캠페인이 새로운 획득 소스로서 기여도를 인정받음
* 리포트 관점에서 사용자가 완전히 새로운 신규 획득으로 처리됨

<div id="example-90-day-window" />

#### 예(90일 윈도우)

* **Day 0:** Google 광고를 통해 사용자 획득
* **Day 50:** 마지막 활동
* **Day 140:** 사용자 이탈 처리 (90일 동안 비활성)
* **Day 145:** 사용자가 이메일 윈백 캠페인을 클릭함

**Day 146:** 사용자가 재획득 이벤트 수행 → 이메일 캠페인에 어트리뷰션된 **새로운 UA 전환** 생성

</Accordion>

<div id="reacquisition-event" />

<Accordion title="재획득 이벤트">

이탈한 사용자의 재획득을 트리거하는 이벤트입니다. 이탈한 사용자만 재획득될 수 있습니다.

많은 사용자 획득 이벤트는 두 번 발생할 수 없는 일회성 액션(예: sign\_up, first\_purchase)입니다. 이 설정을 통해 이탈한 사용자가 돌아왔음을 나타내는 반복 가능한 이벤트를 정의할 수 있습니다.

**기본값:** visit (이탈 사용자가 복귀하여 첫 방문하는 즉시 **재획득 처리됨**)

**자주 사용되는 대체 이벤트:** sign\_in 또는 purchase

<div id="how-it-works-5" />

#### 작동 방법

**맞춤 이벤트(예:** **sign\_in)로 설정된 경우:**

* 이탈한 사용자가 재획득되려면 해당 특정 이벤트를 반드시 수행해야 합니다.
* 재획득이 발생하기 전까지 사용자가 여러 번 방문할 수 있습니다.
* "진정한" 재획득에 대한 더욱 엄격한 정의입니다.

<div id="example-re-acquisition-event--sign_in" />

#### 예시(재획득 이벤트 = sign\_in):

* 사용자가 90일 동안 비활성 상태로 유지된 후 이탈 처리됨
* 사용자가 이메일 윈백 캠페인을 클릭하고 방문함 → 아직 재획득되지 않음
* 하루 뒤 사용자가 로그인함 → 재획득 전환이 생성되어 이메일 캠페인에 어트리뷰션됨

</Accordion>

<div id="attribution-window" />

## 어트리뷰션 윈도우

<div id="time-period" />

<Accordion title="기간">

사용자 획득 이후 앱스플라이어가 해당 전환에 이벤트를 어트리뷰션하는 최대 기간입니다.

**기본:** 영구

**선택 가능한 옵션:** None, 1일, 7일, 30일, 60일, 90일, 180일, 365일, Forever (데이터 보관 주기에 따라 제한됨)

</Accordion>

<div id="excluded-domains" />

## 제외 도메인

어트리뷰션에서 제외할 도메인입니다. 사용자가 지정된 도메인과 웹사이트 사이를 이동할 때 앱스플라이어가 방문이나 이벤트를 어트리뷰션하는 것을 방지합니다.

**목적**

1. **자체 어트리뷰션 방지:** 자체 소유 도메인 제외
2. **서드파티 플로우 제외:** 결제 대행사(PG), 인증 서비스 제공업체 도메인 제외

<div id="domain-types" />

<Accordion title="도메인 유형">

<div id="primary-required-automatic" />

#### 기본(필수, 자동)

* 기본 웹사이트 도메인(앱 생성 시 설정됨)
* 자동으로 추가되며 삭제할 수 없습니다.
* 웹 앱당 정확히 1개의 기본 도메인
* **서브도메인 자동 제외:** 기본 도메인(Primary domain)은 모든 하위 서브도메인을 자동으로 제외합니다.
  * 예시: example.com은 shop.example.com, blog.example.com 등을 자동으로 제외합니다.
* **제외 효과:** 자체 어트리뷰션 방지

<div id="internal-optional" />

#### 내부(선택 사항)

* 기본 도메인에 포함되지 않는 브랜드의 기타 다른 도메인
* 최대 99개의 추가 도메인 등록 가능
* 예시: example.co.uk, example.in과 같은 서로 다른 최상위 도메인
* **제외 효과:** 자체 어트리뷰션 방지

<div id="external-optional" />

#### 외부(선택 사항)

외부 도메인 제외 유형에는 두 가지가 있습니다.

<div id="external-listed-by-you" />

#### 외부(사용자 지정 목록)

* 웹사이트에서 직접 사용되지만 브랜드의 일부는 아닌 도메인
* 여기에는 결제 대행사(PG), 결제 처리 사이트, 인증 서비스 제공업체 등이 포함됩니다.
* 최대 99개의 추가 도메인 등록 가능
* 예시: auth0.com, okta.com, facebook.com, google.com
* **제외 효과:** 방문이 무시됨

<div id="external-listed-by-appsflyer" />

#### 외부(앱스플라이어 목록)

* 앱스플라이어에서 자동으로 제외하는 도메인:

  **결제 서비스 제공업체**

  * PayPal(결제 체크아웃)
  * Stripe(결제 체크아웃)
  * Adyen(결제 체크아웃)
  * Klarna(결제 체크아웃)
  * Braintree(결제 체크아웃)
  * Square(결제 체크아웃)
  * Paddle(결제 체크아웃)
  * Mollie(결제 체크아웃)
  * Alipay(결제 체크아웃)
  * Razorpay(결제 체크아웃)
  * Paytm(결제 체크아웃)
  * PayU(결제 체크아웃)
  * Mercado Pago(결제 체크아웃)
  * Yandex Pay(결제 체크아웃)
  * Naver Pay(결제 체크아웃)

  **OAuth 및 SSO sign-in**

  * Google Sign-In(Google 계정 로그인)
  * Apple ID(Apple 계정 로그인)
  * Microsoft(Microsoft 365 / Entra 계정 로그인)
  * Microsoft Live(Outlook/Live 계정 로그인)
  * Facebook Login(Facebook 로그인 도메인만)
  * Yandex Login(Yandex 계정 로그인)
  * 카카오 로그인(카카오 계정 로그인)
  * 네이버 로그인(네이버 계정 로그인)
  * LINE 로그인(LINE 계정 로그인)
  * Weixin Login(WeChat OAuth 로그인)
  * VK Login(VK 계정 로그인)
  * 다음 로그인(Daum 계정 로그인)
* 자동 도메인 목록은 편집될 수 없음
* **제외 효과:** 방문이 무시됨

</Accordion>

<div id="adding-excluded-domains" />

<Accordion title="제외 도메인 추가하기">

**제외 도메인을 추가하려면:**

1. 웹 앱 설정 → 어트리뷰션으로 이동합니다.
2. 제외된 도메인 섹션으로 이동합니다.
3. **도매인 추가** 클릭를 클릭합니다.
4. 도메인 이름을 입력합니다(예: custom-gateway.com).
5. 도메인 유형을 선택합니다: Internal(내부) 또는 External(외부)
6. **저장**을 클릭합니다.

**중요한 참고사항:**

* 제외 설정은 **1시간 이내**에 적용됩니다.
* 변경 사항은 **향후 데이터에만 적용**됩니다(과거 데이터에는 영향을 주지 않음).
* 일반적인 결제 대행사 및 OAuth/SSO 로그인 도메인은 자동으로 제외됩니다. [외부(앱스플라이어 목록)](#외부앱스플라이어-목록) 아래에서 전체 목록을 확인할 수 있습니다(수동으로 추가할 필요 없음).

</Accordion>

<div id="requirements-and-validation" />

<Accordion title="요구 사항 및 유효성 검사">

<div id="domain-format" />

#### 도메인 형식

* 도메인 이름만(프로토콜, 경로 및 포트 제외)
* 도메인당 최대 500자
* 프로토콜(https://)은 자동으로 제거되며 소문자로 변환됩니다.

<div id="examples" />

#### 예:

* example.com ✅
* shop.example.com ✅ (example.com이 기본 도메인인 경우에는 불필요)
* https://example.com → example.com ✅ (프로토콜 제거됨)
* example.com/path ❌ (경로 허용 안됨)
* example.com:8080 ❌ (경로 허용 안됨)

<div id="limits" />

#### 제한:

* 총 최대 100개 도메인 (기본 도메인 1개 포함)

</Accordion>

<div id="migrating-from-people-based-attribution-pba" />

## People-Based Attribution(PBA)에서의 마이그레이션 가이드

<div id="key-differences" />

<Accordion title="주요 차이점">

| **Aspect** | **PBA(레거시)** | **새 웹 성과 측정** |
| --- | --- | --- |
| **구성 수준** | 브랜드 번들 수준 | 웹 앱 수준 |
| **사용자 지정 UA 이벤트** | 사용 불가 | 완전 사용자 지정 가능 |
| **시간 윈도우** | 제한된 컨트롤 | 전체 컨트롤(1시간 - 생애) |

</Accordion>

<div id="migration-steps" />

<Accordion title="마이그레이션 단계">

1. 새 웹 앱 만들기
   1. 마이 앱 → 앱 추가 → 웹사이트 선택으로 이동
2. 웹 SDK ID 선택   
   웹사이트의 코드 수정을 방지하기 위해 기존 PBA dev key 재사용(권장)
3. 설정 구성   
   PBA 설정을 새로운 웹 어트리뷰션 설정에 매핑
4. 제외된 도메인 추가   
   PBA(Brand Bundle) 제외 도메인을 새로운 웹 어트리뷰션 설정에 매핑

**참고:** 각 PBA dev key는 하나의 새로운 웹 앱에만 할당할 수 있습니다.

</Accordion>

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 h_01KGPFHN8MKTPX5VYDEV30M9A7=%EA%B0%9C%EC%9A%94 who-should-configure-these-settings=%ED%95%B4%EB%8B%B9-%EC%84%A4%EC%A0%95%EC%9D%84-%EA%B5%AC%EC%84%B1%ED%95%B4%EC%95%BC-%ED%95%98%EB%8A%94-%EB%8B%B4%EB%8B%B9%EC%9E%90 h_01KGPFK1RNA7ZTJRACJ6M97EAB=%ED%95%B4%EB%8B%B9-%EC%84%A4%EC%A0%95%EC%9D%84-%EA%B5%AC%EC%84%B1%ED%95%B4%EC%95%BC-%ED%95%98%EB%8A%94-%EB%8B%B4%EB%8B%B9%EC%9E%90 accessing-web-attribution-settings=%EC%9B%B9-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%84%A4%EC%A0%95-%EC%A0%91%EA%B7%BC h_01KGPFM0DJDMVDXZC2B6G6DVX5=%EC%9B%B9-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%84%A4%EC%A0%95-%EC%A0%91%EA%B7%BC quick-reference=%EB%B9%A0%EB%A5%B8-%EC%B0%B8%EC%A1%B0 h_01KGPFT1W65R724WCNDPBHY3F6=%EB%B9%A0%EB%A5%B8-%EC%B0%B8%EC%A1%B0 basic-settings=%EA%B8%B0%EB%B3%B8-%EC%84%A4%EC%A0%95 h_01KGPGJG092S1TEDB1T9JNBASE=%EA%B8%B0%EB%B3%B8-%EC%84%A4%EC%A0%95 user-acquisition-settings=%EC%82%AC%EC%9A%A9%EC%9E%90-%ED%9A%8D%EB%93%9D-%EC%84%A4%EC%A0%95 h_01KGPGE592EK59XXVKTTFDGX16=%EC%82%AC%EC%9A%A9%EC%9E%90-%ED%9A%8D%EB%93%9D-%EC%84%A4%EC%A0%95 h_01KGPGRTEFA0PJ3DB7MR4W85EB=user-acquisition-event why-customize=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95%ED%95%98%EB%8A%94-%EC%9D%B4%EC%9C%A0 h_01KGPHMJWF6Z1VV0KH301TYAS5=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95%ED%95%98%EB%8A%94-%EC%9D%B4%EC%9C%A0 common-alternatives-by-industry=%EC%82%B0%EC%97%85%EA%B5%B0-%EB%B3%84-%EC%9D%BC%EB%B0%98%EC%A0%81%EC%9D%B8-%EB%8C%80%EC%95%88 h_01KGPHMSEDGJ2E6NSB1ZCR5CCW=%EC%82%B0%EC%97%85%EA%B5%B0-%EB%B3%84-%EC%9D%BC%EB%B0%98%EC%A0%81%EC%9D%B8-%EB%8C%80%EC%95%88 how-it-works=%EC%9E%91%EB%8F%99-%EC%9E%A5%EB%B2%95 h_01KGPHN5M5GBBMPBYRMYHB9F0E=%EC%9E%91%EB%8F%99-%EC%9E%A5%EB%B2%95 example-scenario-ua-event-sign_up=%EC%98%88%EC%8B%9C-%EC%8B%9C%EB%82%98%EB%A6%AC%EC%98%A4ua-%EC%9D%B4%EB%B2%A4%ED%8A%B8--sign_up h_01KGPHQES3SF5AKBNYD8CY3RG8=%EC%98%88%EC%8B%9C-%EC%8B%9C%EB%82%98%EB%A6%AC%EC%98%A4ua-%EC%9D%B4%EB%B2%A4%ED%8A%B8--sign_up h_01KGPGRTEFYRAZD7Z9NYDKV907=lookback-window-user-acquisition how-it-works::69b3417c=%EC%9E%91%EB%8F%99-%EB%B0%A9%EB%B2%95 h_01KGPHX2JNAWZ8VJZ25CRWP1ER=%EC%9E%91%EB%8F%99-%EB%B0%A9%EB%B2%95 example-1-30day-lookback=%EC%98%88%EC%8B%9C-130%EC%9D%BC-%EB%A3%A9%EB%B0%B1 h_01KGPHX8JMG7FMRS1MYFYS6JRV=%EC%98%88%EC%8B%9C-130%EC%9D%BC-%EB%A3%A9%EB%B0%B1 example-2-window-expired=%EC%98%88%EC%8B%9C-2%EC%9C%88%EB%8F%84%EC%9A%B0-%EB%A7%8C%EB%A3%8C h_01KGPHXT83JHJ6J0APVN7NRJ3E=%EC%98%88%EC%8B%9C-2%EC%9C%88%EB%8F%84%EC%9A%B0-%EB%A7%8C%EB%A3%8C reengagement-settings=%EB%A6%AC%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8-%EC%84%A4%EC%A0%95 h_01KGPJ1ZMXXJJNCBB52CHY95Z2=%EB%A6%AC%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8-%EC%84%A4%EC%A0%95 reengagement-window%C2%A0item=reengagement-window-item h_01KGPJ58N3712E1NZ4E6JVGAY2=reengagement-window-item how-it-works::dafb60ec=%EC%9E%91%EB%8F%99-%EB%B0%A9%EB%B2%95-1 h_01KGPJFG3X578XCP5X353RRVR1=%EC%9E%91%EB%8F%99-%EB%B0%A9%EB%B2%95-1 example-within-window=%EC%98%88%EC%9C%88%EB%8F%84%EC%9A%B0-%EB%8F%99%EC%95%88 h_01KGPJG6WSYX2R0VVQYXXWZSMA=%EC%98%88%EC%9C%88%EB%8F%84%EC%9A%B0-%EB%8F%99%EC%95%88 h_01KGPJ58N3QH9RKXTVZXCZ1WGW=inactivity-window-for-reengagement how-it-works::4a4cf0f=%EC%9E%91%EB%8F%99-%EB%B0%A9%EB%B2%95-2 h_01KGPJK3H2JF7PV1ATQB3TE9AX=%EC%9E%91%EB%8F%99-%EB%B0%A9%EB%B2%95-2 example-7day-inactivity-window=%EC%98%887%EC%9D%BC-%EB%B9%84%ED%99%9C%EC%84%B1-%EC%9C%88%EB%8F%84%EC%9A%B0 h_01KGPJKDMY4FRAJSMHE19GGJCA=%EC%98%887%EC%9D%BC-%EB%B9%84%ED%99%9C%EC%84%B1-%EC%9C%88%EB%8F%84%EC%9A%B0 reacquisition-settings=%EC%9E%AC%ED%9A%8D%EB%93%9D-%EC%84%A4%EC%A0%95 h_01KGPJMJDX83SBA77A7BSRZ87V=%EC%9E%AC%ED%9A%8D%EB%93%9D-%EC%84%A4%EC%A0%95 h_01KGPJPC0QXYFD6Q09XF7T3XA9=inactivity-window-reacquisition how-it-works::9c91010b=%EC%9E%91%EB%8F%99-%EB%B0%A9%EB%B2%95-3 h_01KGPJV8EJR94H1P7GZXMP8HSR=%EC%9E%91%EB%8F%99-%EB%B0%A9%EB%B2%95-3 example-90day-window=%EC%98%8890%EC%9D%BC-%EC%9C%88%EB%8F%84%EC%9A%B0 h_01KGPJVHCNBZHD9ZXW288CGG9H=%EC%98%8890%EC%9D%BC-%EC%9C%88%EB%8F%84%EC%9A%B0 h_01KGPJPC0QY2726Z583AQ7G5W2=reacquisition-event how-it-works::587eebec=%EC%9E%91%EB%8F%99-%EB%B0%A9%EB%B2%95-4 h_01KGPJY5PA9907PXBRC2QHNJ6T=%EC%9E%91%EB%8F%99-%EB%B0%A9%EB%B2%95-4 example-reacquisition-event-sign_in=%EC%98%88%EC%8B%9C%EC%9E%AC%ED%9A%8D%EB%93%9D-%EC%9D%B4%EB%B2%A4%ED%8A%B8--sign_in h_01KGPJYWG31QJ1G5A09QC00AMY=%EC%98%88%EC%8B%9C%EC%9E%AC%ED%9A%8D%EB%93%9D-%EC%9D%B4%EB%B2%A4%ED%8A%B8--sign_in attribution-window=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%9C%88%EB%8F%84%EC%9A%B0 h_01KGPK8H7P5AT59S0GQ9ZK0F01=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%9C%88%EB%8F%84%EC%9A%B0 h_01KGPK1CSV5XGKHX3XVS37QFKS=time-period excluded-domains=%EC%A0%9C%EC%99%B8-%EB%8F%84%EB%A9%94%EC%9D%B8 h_01KGPKA56KQRJKRS54HBR50NJN=%EC%A0%9C%EC%99%B8-%EB%8F%84%EB%A9%94%EC%9D%B8 h_01KGPKCY1EBCMYDDYS6SZEK1ZR=domain-types primary-required-automatic=%EA%B8%B0%EB%B3%B8%ED%95%84%EC%88%98-%EC%9E%90%EB%8F%99 h_01KGPKJQ7M82KW5VE9ESYNNFEQ=%EA%B8%B0%EB%B3%B8%ED%95%84%EC%88%98-%EC%9E%90%EB%8F%99 internal-optional=%EB%82%B4%EB%B6%80%EC%84%A0%ED%83%9D-%EC%82%AC%ED%95%AD h_01KGPKJV9B2BHDR64JD24VHH1X=%EB%82%B4%EB%B6%80%EC%84%A0%ED%83%9D-%EC%82%AC%ED%95%AD external-optional=%EC%99%B8%EB%B6%80%EC%84%A0%ED%83%9D-%EC%82%AC%ED%95%AD h_01KGPKJZQYZESHHH3D0NA2WC9F=%EC%99%B8%EB%B6%80%EC%84%A0%ED%83%9D-%EC%82%AC%ED%95%AD external-listed-by-you=%EC%99%B8%EB%B6%80%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95-%EB%AA%A9%EB%A1%9D h_01KGPKK4THXQ88AXT58GZ2MHHE=%EC%99%B8%EB%B6%80%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95-%EB%AA%A9%EB%A1%9D external-listed-by-appsflyer=%EC%99%B8%EB%B6%80%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EB%AA%A9%EB%A1%9D h_01KGPKK96ZAZSKVPBX60FC888X=%EC%99%B8%EB%B6%80%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EB%AA%A9%EB%A1%9D h_01KGPKCY1ETKF1NQ2BP6Z3JH4T=adding-excluded-domains h_01KGPKCY1EE01631ZEYGC6FEJH=requirements-and-validation domain-format=%EB%8F%84%EB%A9%94%EC%9D%B8-%ED%98%95%EC%8B%9D h_01KGPKKXRA59A4RDY4QE1M0Q66=%EB%8F%84%EB%A9%94%EC%9D%B8-%ED%98%95%EC%8B%9D examples=%EC%98%88 h_01KGPKM213203KA8CEBHZ9KJP3=%EC%98%88 limits=%EC%A0%9C%ED%95%9C h_01KGPKM8AMQ5BA88ZCSTRJ2JV7=%EC%A0%9C%ED%95%9C migrating-from-peoplebased-attribution-pba=people-based-attributionpba%EC%97%90%EC%84%9C%EC%9D%98-%EB%A7%88%EC%9D%B4%EA%B7%B8%EB%A0%88%EC%9D%B4%EC%85%98-%EA%B0%80%EC%9D%B4%EB%93%9C h_01KGPKPGSF3VSBTQJR6JN80BF4=people-based-attributionpba%EC%97%90%EC%84%9C%EC%9D%98-%EB%A7%88%EC%9D%B4%EA%B7%B8%EB%A0%88%EC%9D%B4%EC%85%98-%EA%B0%80%EC%9D%B4%EB%93%9C h_01KGPKQPWC1GYYGYYD6PCDWX29=key-differences h_01KGPKQPWD00B08Z76ZYGRP4AT=migration-steps" />
