---
title: 웹 성과 측정 - 개요
metadata:
  keywords:
    - Agencies
    - Web Attribution
    - Web Attribution SDK
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
    - Agencies
  created_at: '2026-02-04T15:07:53Z'
  edited_at: '2026-10-22T14:24:47Z'
  id: 43521734577809
  locale: ko
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/ko/articles/43521734577809
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **한눈에 보기:** 웹 성과 측정을 통해 어떤 미디어 소스와 캠페인이 웹사이트로 사용자를 유입시키는지 확인하고, 이러한 방문이 시간이 지남에 따라 하위 액션에 어떠한 영향을 미치는지 측정할 수 있습니다. 이를 통해 최초 방문부터 생애 가치 측정에 이르기까지 신규 사용자 획득(최초 방문자)과 리인게이지먼트 모두를 지원하며, 사용자의 상호작용을 엔드투엔드로 캡처하고 어트리뷰션할 수 있습니다.

<div id="about-web-performance-measurement" />

## 웹 성과 측정에 대하여

웹 어트리뷰션은 어떤 미디어 소스와 캠페인이 사용자의 웹사이트 방문을 유도하고 이후의 액션에 영향을 미치는지 확인하는 프로세스입니다.

웹 방문은 브라우징 활동인 동시에 방문 직전에 발생한 광고 참여를 의미합니다. 클릭과 설치를 매칭해야 하는 모바일 어트리뷰션과 달리, 웹 방문은 랜딩 URL과 헤더에 마케팅 소스 데이터를 포함하고 있어 최초 매칭이 즉각적으로 이루어집니다.

이 아티클의 목적은 최초 웹사이트 방문부터 생애 가치 측정에 이르기까지 사용자 상호작용이 어떻게 수집되고 식별되며 측정되는지 설명하면서, 엔드투엔드 웹 성과 측정 프로세스의 개요를 전달하는 것입니다. 이 프로세스를 통해 엔진은 신규 방문자를 식별하고 어트리뷰션하는 신규 사용자 획득뿐만 아니라, 재방문 사용자를 타겟팅하는 캠페인의 성과를 측정하기 위한 리타겟팅 또는 리인게이지먼트까지 모두 지원할 수 있습니다.

<div id="if-you-use-people-based-attribution-pba" />

#### People-Based Attribution(PBA)을 사용하는 경우

현재 <Anchor target="_blank" href="/marketers/ko/docs/people-based-attribution-pba">People-Based Attribution(PBA)</Anchor>을 사용 중인 경우, 더 세분화된 어트리뷰션과 추가적인 시그널을 활용할 수 있는 웹 성과 측정으로 전환하는 것을 고려해 보세요.

<div id="the-web-performance-measurement-flow" />

### 웹 성과 측정 플로우

웹 성과 측정 플로우는 단순 사이트 방문 데이터를 실행 가능한 마케팅 인사이트로 변환하는 체계적인 단계별 프로세스를 따릅니다.

1. [데이터 수집](#1-data-collection): 해당 시스템은 웹 SDK(Pixel) 및 서버 대 서버(S2S) API 중 하나를 활용해 사용자의 반응 및 활동 데이터를 캡처합니다.
2. [방문 기록](#2-visit-recording)[:](/docs/web-performance-measurement-overview#2-visit-recording) 트래픽 소스를 아직 모르는 상태이더라도 사용자의 웹사이트 접속을 캡처하고 방문 이벤트를 기록합니다.
3. [미디어 소스 식별](#3-media-source-resolution): 정의된 우선순위에 따라 URL 파라미터를 파싱하여 미디어 소스를 규명합니다.
4. [30분 식별 지연](#4-the-30minute-identity-delay): 사용자 로그인을 통한 식별을 진행할 수 있도록 어트리뷰션 판정을 30분 동안 지연합니다.
5. [스티칭 및 신원 식별](#5-stitching-and-identity-resolution): 진행 중인 세션을 영구적인 고객 사용자 ID(CUID)나 브라우저 쿠키와 매칭하여 결합합니다.
6. [신규 사용자 획득 이벤트](#6-user-acquisition-ua-event): 신규 사용자 획득 룩백 윈도우 내에서 획득을 정의하는 이벤트(예: `first_visit` 또는 커스텀 획득 이벤트)를 기록합니다.
7. [획득 전 기간](#7-preacquisition-period): 최초 방문과 UA 이벤트 사이에 발생하는 중간 이벤트를 어트리뷰션합니다.
8. [리인게이지먼트 및 재획득](#8-reengagement-and-reacquisition): 비활성화 윈도우를 기준으로 재방문 사용자를 어트리뷰션하고, 해당 재방문이 리인게이지먼트인지 또는 재획득인지를 판정합니다.
9. [LTV 측정](#9-ltv-measurement): 어트리뷰션 윈도우 기준에 따라 지속적인 이벤트와 매출을 어트리뷰션하여 사용자의 생애 가치를 측정합니다.

<div id="the-web-performance-measurement-process---step-by-step" />

## 단계별 웹 성과 측정 프로세스

다음 섹션에서는 각 단계를 자세히 설명합니다.

<div id="1-data-collection" />

<Accordion title="1. 데이터 콜렉션">

사용자가 랜딩 페이지에 도달하면, 앱스플라이어는 연동된 리스너를 통해 해당 상호작용을 캡처해야 합니다.

* **Web SDK(Pixel)**: <Anchor target="_blank" href="/marketers/ko/docs/integrate-appsflyer-web-sdk">웹사이트 내 직접 설치 또는 Google Tag Manager(GTM)를 거쳐 배치</Anchor>되는 클라이언트 측 코드 스니펫입니다.
* **서버 대 서버(S2S) API**: 브라우저의 트래킹 방지 정책 및 애드블록을 차단 없이 통과하도록 돕는 강력한 서버 측 연동 솔루션으로, 수집된 정보가 앱스플라이어로 전송되기 전 데이터를 더욱 풍부하게 가공 및 보강할 수 있게 해줍니다. S2S 연동은 고객 서버에서 직접 진행하거나 Google Tag Manager 서버 사이드를 통해 수행할 수 있습니다.

</Accordion>

<div id="2-visit-recording" />

<Accordion title="2. 방문 기록">

세션 데이터가 수집된 후, 시스템은 최초 방문 기록을 생성할지 여부를 결정합니다. 이 기록은 실제 미디어 소스 식별 및 어트리뷰션이 이루어지기 전에 순수 사용자 활동을 수집하는 전처리 레이어 역할을 합니다. 모든 세션이 방문으로 기록되는 것은 아닙니다.

앱스플라이어는 새로운 세션 내에서 또는 식별 가능한 소스 파라미터를 가지고 사이트에 접속할 때 방문을 기록하며, 제외된 도메인으로부터의 방문은 무시합니다. 이러한 방문 기록 규칙은 세션이 중복 집계되는 것을 방지합니다.

자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/about-traffic-source-resolution#1단계-방문-기록">방문 기록</Anchor>을 참조하세요.

</Accordion>

<div id="3-media-source-resolution" />

<Accordion title="3. 미디어 소스 식별">

데이터가 수집되고 방문이 기록된 후, 엔진은 정의된 우선순위에 따라 이를 평가합니다. 이 워터폴은 앱스플라이어 전용 파라미터와 업계 표준 파라미터를 모두 지원하므로, 고객은 **마이그레이션 과정에서 기존 어트리뷰션 링크를 변경할 필요가 없습니다**. 워터폴에서 가장 먼저 일치하는 신호를 사용하여 방문 출처를 결정합니다.

* **PID**: 시스템은 먼저 앱스플라이어 전용 파라미터가 있는지 확인합니다.
* **UTM 파라미터**: PID가 존재하지 않는 경우 `utm_source`와 같은 표준 태그를 탐색합니다.
* **클릭 ID**: 이후 Google Click ID(`gclid`) 또는 TikTok Click ID(`ttclid`)와 같은 네트워크 고유 ID를 검색합니다.
* **리퍼러**: 최후의 대체 수단으로, 사용자가 도착하기 직전에 머물렀던 URL을 식별합니다.

자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/about-traffic-source-resolution#2단계-미디어-소스-리졸루션">미디어 소스 식별</Anchor>을 참조하세요.

</Accordion>

<div id="4-the-30minute-identity-delay" />

<Accordion title="4. 30분 식별 지연">

대부분의 사용자가 방문 후 30분 이내에 로그인하므로, 앱스플라이어는 의도적으로 동일한 시간 동안 어트리뷰션 결정을 유예합니다. 이 유예 시간을 통해 시스템이 CUID를 수집하고 쿠키가 만료된 재방문 사용자를 최초 소스에 정확히 연결할 수 있어 "오가닉"으로 잘못 분류되는 것을 방지합니다.

</Accordion>

<div id="5-stitching-and-identity-resolution" />

<Accordion title="5. 스티칭 및 식별자 통합">

소스가 식별되고 30분 유예 시간이 완료되면, 시스템은 사용자의 파편화된 세션을 단일 여정으로 "스티칭"하는 단계로 이동합니다.

* **CUID 스티칭**: CUID(예: 해시 처리된 이메일)가 수집되면, 엔진은 해당 세션을 사용자의 크로스 디바이스 히스토리에 연결합니다.
* **쿠키 폴백**: CUID를 사용할 수 없는 경우 시스템은 브라우저 쿠키로 대체하지만, 이는 안정성이 떨어지고 기기별로 제한됩니다.

</Accordion>

<div id="6-user-acquisition-ua-event" />

<Accordion title="6. 사용자 획득 이벤트">

사용자 식별자 통합이 완료되면, 엔진은 해당 사용자를 획득으로 정의하는 특정 작업을 탐색합니다. 업계 표준은 `first_visit`이지만, 이는 사용자가 실수로 광고를 클릭하거나 즉시 이탈할 수 있어 약한 신호인 경우가 많습니다. 회원가입이나 구매와 같은 사용자 지정 획득 이벤트를 설정하면, 단순한 호기심성 클릭이 아닌 의미 있는 활동을 유도한 마케팅 소스에 장기 가치(LTV)가 귀속되도록 할 수 있습니다.

사용자 획득 이벤트가 발생하면, 어트리뷰션 엔진은 **신규 획득 룩백 윈도우** 기간만큼 소급 검색하여 기여할 비오가닉 방문을 탐색합니다. 이 설정은 사용자의 방문부터 UA 이벤트 완료까지 허용되는 최대 시간을 정의합니다(기본값: 30일). 이 룩백 기간 내에 비오가닉 접점이 발견되지 않으면, 해당 UA 이벤트는 오가닉으로 간주되어 어트리뷰션이 인정되지 않습니다. 웹 앱을 앱스플라이어에 추가할 때 사용자 지정 이벤트 룩백 윈도우 기간을 설정할 수 있습니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/configure-web-performance-measurement-settings#lookback-window-user-acquisition">룩백 윈도우(사용자 획득)</Anchor>을 참조하세요.

비즈니스 모델에 따라 다양한 이벤트가 사용자 획득 트리거로 정의될 수 있습니다. 예를 들어 다음과 같습니다.

* **가입 완료 이벤트(예: 뱅킹 앱)** 획득 이벤트는 가입 절차가 성공적으로 완료되었을 때만 트리거됩니다.
* **첫 주문 완료 이벤트(예: 배달 앱)** 상품을 둘러보거나 장바구니에 담는 행동은 포함되지 않으며, 결제가 성공적으로 처리된 후에만 이벤트가 발생합니다.
* **구독 활성화 이벤트(예: 스트리밍 또는 SaaS 앱)** 획득 이벤트는 무료 체험 시작이나 앱 설치 시점이 아닌, 구독이 확정되었을 때 기록됩니다.

사용자 획득 이벤트 설정에 대한 자세한 정보는 <Anchor target="_blank" href="/marketers/ko/docs/configure-web-performance-measurement-settings#사용자-획득-설정">사용자 획득 설정</Anchor>을 참조하세요.

</Accordion>

<div id="7-preacquisition-period" />

<Accordion title="7. 획득 전 기간">

시스템이 사용자의 식별자를 통합한 후 신규 획득이 이루어지기 전까지, 유연한 여정 내에는 '획득 전 기간'이라고 불리는 간극이 존재할 수 있습니다. 이 설정은 기본값인 `first_visit`대신 사용자 지정 획득(UA) 이벤트를 정의한 경우에만 적용됩니다. 이 기간 동안 사용자는 회원가입이나 첫 구매 등 공식적으로 신규 획득이 인정되는 이벤트를 완료하기 전에, 장바구니에 상품 담기, 상품 탐색, 콘텐츠 참여 등 의미 있는 활동을 수행할 수 있습니다.

앱스플라이어는 이러한 획득 전 이벤트를 수집하여 마케팅 소스에 귀속시키고, 리포트에서 획득 전 이벤트로 표시합니다. 획득 전 어트리뷰션과 획득 후 어트리뷰션의 핵심적인 차이점은 어트리뷰션 윈도우에 있습니다. 획득 전 기간 동안 어트리뷰션 윈도우는 더 짧으며 UA 이벤트 룩백 윈도우와 일치합니다. 이러한 이벤트들은 사용자를 획득 상태로 정의하는 UA 이벤트보다 먼저 발생하기 때문입니다. 사용자 지정 UA 이벤트가 트리거되고 사용자가 획득된 후에는 어트리뷰션 윈도우가 확장되어 생애 가치(LTV)를 측정하며, 사용자를 획득한 마케팅 소스에 장기적인 성과를 부여합니다.

</Accordion>

<div id="8-reengagement-and-reacquisition" />

<Accordion title="8. 리인게이지먼트 및 재획득">

사용자가 한 번 획득되면, 나중에 사이트에 다시 방문할 수 있습니다. 리인게이지먼트(재방문) 어트리뷰션은 기존 사용자가 광고를 클릭하여 사이트를 다시 방문할 때 트리거됩니다.

*리인게이지먼트*가 기존 사용자에 초점을 맞추는 반면, 사용자가 장기간 활동하지 않은 경우에는 재방문이 *재획득*으로 분류될 수도 있습니다. 재획득 대상이 되려면 사용자는 먼저 이탈 상태로 간주되는 데 필요한 비활동 기간을 정의하는 **비활동 윈도우**(기본값: 90일)를 지나야 합니다. 이 윈도우 기간이 지난 후 사용자가 돌아오면, 엔진은 일반적인 재방문 대신 새로운 사용자 획득 이벤트를 기록합니다.

자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/configure-web-performance-measurement-settings#리인게이지먼트-설정">리인게이지먼트 설정</Anchor> 및 <Anchor target="_blank" href="/marketers/ko/docs/configure-web-performance-measurement-settings#재획득-설정">재획득 설정</Anchor>을 참조하세요.

</Accordion>

<div id="9-ltv-measurement" />

<Accordion title="9. LTV 측정">

사용자가 최초 획득 캠페인을 통해 유입되었든 후속 리타겟팅 성과로 유입되었든, 최종 목표는 시간 경과에 따른 사용자의 총 가치를 측정하는 것입니다. 사용자가 특정 소스로 성과가 인정되면, 시스템은 사용자의 지속적인 활동을 측정하여 생애 가치(LTV)를 계산합니다.

이 측정은 기본적으로 "Forever"로 설정된 **어트리뷰션 윈도우**에 의해 제어됩니다. 이를 통해 재구매나 구독 갱신과 같은 모든 후속 활동이 사용자를 사이트로 유도한 최초의 마케팅 소스로 정확히 기여 반영됩니다. 이러한 장기 데이터를 수집함으로써 단순한 전환 건수 측정을 넘어 캠페인의 실제 광고비 대비 수익률(ROAS)을 정확히 파악할 수 있습니다.

**어트리뷰션 윈도우** 설정에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/configure-web-performance-measurement-settings#어트리뷰션-윈도우">어트리뷰션 윈도우</Anchor>를 참조하세요.

</Accordion>

<div data-zendesk-anchors="about-web-attribution=%EC%9B%B9-%EC%84%B1%EA%B3%BC-%EC%B8%A1%EC%A0%95%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC h_01KGMK4P46QE2HQHADD25TPCQF=%EC%9B%B9-%EC%84%B1%EA%B3%BC-%EC%B8%A1%EC%A0%95%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC if-you-use-peoplebased-attribution-pba=people-based-attributionpba%EC%9D%84-%EC%82%AC%EC%9A%A9%ED%95%98%EB%8A%94-%EA%B2%BD%EC%9A%B0 h_01KH0P7BB9KF19S8XRH49DKMZA=people-based-attributionpba%EC%9D%84-%EC%82%AC%EC%9A%A9%ED%95%98%EB%8A%94-%EA%B2%BD%EC%9A%B0 the-appsflyer-web-attribution-flow=%EC%9B%B9-%EC%84%B1%EA%B3%BC-%EC%B8%A1%EC%A0%95-%ED%94%8C%EB%A1%9C%EC%9A%B0 h_01KGMK4P4614EEQ28V5FV32CY5=%EC%9B%B9-%EC%84%B1%EA%B3%BC-%EC%B8%A1%EC%A0%95-%ED%94%8C%EB%A1%9C%EC%9A%B0 the-appsflyer-web-attribution-process-step-by-step=%EB%8B%A8%EA%B3%84%EB%B3%84-%EC%9B%B9-%EC%84%B1%EA%B3%BC-%EC%B8%A1%EC%A0%95-%ED%94%84%EB%A1%9C%EC%84%B8%EC%8A%A4 h_01KGMK4P46HTB82K2PH9V0E33B=%EB%8B%A8%EA%B3%84%EB%B3%84-%EC%9B%B9-%EC%84%B1%EA%B3%BC-%EC%B8%A1%EC%A0%95-%ED%94%84%EB%A1%9C%EC%84%B8%EC%8A%A4 h_01KGMK4P46VJ0NF1FKFRS8V6J2=1-data-collection h_01KGMK4P46GWBP56NJM2ENARTR=2-visit-recording h_01KGMK4P46ZKS856R5C5KEQDBK=3-media-source-resolution h_01KGMK4P465777YN9MQ1JYZ7HT=4-the-30minute-identity-delay h_01KGMK4P46GFBZTMHDVW2MD3K1=5-stitching-and-identity-resolution h_01KGMK4P46MBT49ECD7RFHDY3X=6-user-acquisition-ua-event h_01KGMK4P46XYPVFV67F000EM6C=7-preacquisition-period h_01KGMK4P472B4TFGVR4VBH4REH=8-reengagement-and-reacquisition h_01KGMK4P47E9TPX0S26TTPW4CB=9-ltv-measurement" />
