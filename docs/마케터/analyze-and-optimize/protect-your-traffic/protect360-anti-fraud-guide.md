---
title: Protect360 프로드 방지 가이드
metadata:
  keywords:
    - Advertisers
    - Protect360
    - protect
    - protect 360
    - '360'
    - p360
    - p 360
    - 360protect
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2016-12-06T07:47:17Z'
  edited_at: '2026-10-14T10:36:19Z'
  id: 218254203
  locale: ko
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/ko/articles/218254203
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **한눈에 보기:** **요약:** 어트리뷰션 프로드는 마케팅 예산을 소모하고 마케팅 성과 데이터를 왜곡시키며 캠페인 손실로 이어질 수 있습니다. **Protect360은 앱 소유자에게 실시간 사기 방지 및 포스트 어트리뷰션 감지 기능을 제공합니다.**

![p360intro2.jpg](https://files.readme.io/c8476382eeff62164ca93b9bf2f3c4cdbe0609d4160047eac36a44d5f333ffdb-360014803578.jpg)

<div id="protect360-overview" />

## Protect360 개요

* 어트리뷰션 프로드에 대항하여 보호합니다. 이는 프로드를 탐지하고 프로드 어트리뷰션을 차단하는 동적인 툴로 구성됩니다.
* 이미 알려진 방법 뿐만 아니라 새로운 형태의 클릭/인스톨 프로드, 봇 및 이상 행동에 대응하기 위해, 앱스플라이어의 큰 규모, 머신 러닝 그리고 행동 분석을 사용합니다.
* 디바이스, 퍼블리셔 및 미디어 소스 단위에서 마케팅 담당자를 보호합니다.
* 실시간 프로드 차단 및 포스트 어트리뷰션 프로드 식별을 위해 단계별로 접근합니다.
* 앱 사용자 경험에 영향을 주지 않습니다. 실제 사용자가 사기 시도를 한 경우 앱 인스톨이 정상적으로 완료되며, 어트리뷰션 기록만 영향을 받습니다.

<div id="realtime-blocking" />

<Accordion title="실시간 차단">

* 실시간으로, 어트리뷰션 전에 설치가 사기성 미디어 소스에서 발생한 것으로 식별되어 어트리뷰션에서 차단됩니다.
* 동일한 사용자의 후속 인앱이벤트가 차단됩니다.
* 차단된 인스톨 및 인앱이벤트는 Protect360 대시보드와 차단된 사기 리포트에 보고됩니다.
  * 차단된 인스톨 및 인앱이벤트: 어트리뷰트되지 않았기 때문에 앱스플라이어 어트리뷰션 및 대시보드에 포함되지 않습니다.
* 차단된 인스톨 포스트백은 차단 사유와 함께 미디어 소스로 전송되어 최적화를 가능하게 합니다.

<Anchor target="_blank" href="/marketers/ko/docs/protect360-raw-data-reports">차단된 이벤트 관련 정보</Anchor>

</Accordion>

<div id="postattribution-detection" />

<Accordion title="포스트 어트리뷰션 탐지">

* 어트리뷰션 후 확인된 사기를 포스트 어트리뷰션 사기라고 합니다. 포스트 어트리뷰션 프로드는 인스톨 당일 및 인스톨 후 최대 7일(총 8일)까지 확인할 수 있습니다.
* 어트리뷰트되면 인스톨은 삭제할 수 없습니다. 이러한 이유로, 포스트 어트리뷰션 사기는 실시간 사기와 다르게 처리됩니다.
* 돌이켜보면 인스톨 프로드 및 인앱이벤트는 실제 프로드로 간주하여, 요금을 청구해서는 안 됩니다.

광고 네트워크 또는 사이트 ID와 같은 소스가 사기성인 것으로 확인되는 경우:

* 해당 소스의 향후 클릭은 차단됩니다.
* 지난 인스톨:
  * 달력 기준으로 이번 달의 시작부터 현재까지 집계된 인스톨은 포스트 어트리뷰션 사기로 라벨이 붙지만, **데이터에서 삭제되지는 않습니다**. 2020년 1월 기준으로, 광고주 청구서는 이러한 인스톨의 어트리뷰션 비용을 크레딧으로 받습니다.
  * 현재 월이 시작되기 이전은 변경되지 않습니다.
* 발생한 인앱 이벤트:

  * **인스톨 전**: 프로드로 라벨링
  * **인스톨 후:** 프로드로 라벨링

  참고: 프로드로 식별된 사용자 유입(UA) 재설치에 대해, Protect360은 해당 설치를 오가닉 소스로 재할당해 어트리뷰션을 바로잡습니다. 결과적으로 이러한 재설치에서 발생하는 후속 인앱 이벤트는 오가닉 소스로 귀속되며 오가닉 인앱 이벤트 보고서에 나타납니다.

포스트 어트리뷰션 프로드 예시:

* 일반적인 인스톨 이후 인앱 이벤트에서 사기성 신호가 발생함
* 새로운 형태의 프로드가 발견됨
* 이상 탐지 알고리즘이 퍼블리셔의 인스톨에 대해 충분한 통계적 데이터를 수집한 후에만 사기성으로 판명되는 인스톨

</Accordion>

<div id="common-fraud-issues-and-solutions" />

<Accordion title="일반 프로드 문제 및 솔루션">

앱스플라이어가 프로드를 식별할 때, 해당 프로드의 **어트리뷰션** **이벤트**는 차단됩니다. 이는 사기꾼의 이익과 동기를 제거합니다. **참고**: 앱 설치 자체는 진행되며 차단되지 않습니다. 이는 앱 유저가 앱을 사용할 수 있고, 광고주를 위해 매출을 생성할 수 있음을 의미합니다.

차단된 사기 클릭, 인스톨 및 인앱이벤트는 <Anchor target="_blank" href="/marketers/ko/docs/protect360-raw-data-reports">Protect360 사기 로데이터 리포트</Anchor>에서 찾을 수 있습니다.

다음 표에서는 프로드 유형과 Protect360이 이러한 프로드를 처리하는 방법에 대해 설명합니다.

| 프로드 유형 | 설명 | 앱스플라이어 솔루션 |
| --- | --- | --- |
| <span id="device-id-reset-fraud"></span>**기기 ID 리셋 프로드** | 많은 수의 인스톨을 생성하도록 동일한 물리적 기기에 있는 사기꾼에 의해 기기 ID가 지속적으로 재설정됩니다. | AppsFlyer는 비정상적인 신규 기기 비율을 식별하고, 이에 따라 해당 기기를 제공하는 소스를 차단 목록에 추가합니다. |
| <span id="install-hijacking"></span>**프로드 하이재킹** | 사기꾼이 모바일 기기에 심어둔 악성코드를 통해 앱 다운로드가 일어날때마다 클릭을 앱스플라이어에 전송하여 인스톨에 대한 크레딧을 요구합니다. | 매우 빠른 CTIT(<Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/click-to-install-time-ctit/">클릭에서 설치까지 소요 시간</Anchor>)을 기록한 클릭을 차단하며, Google Play 서버 측 API를 기반으로 합니다. |
| <span id="click-hijacking"></span><Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/click-hijacking/">**클릭 하이재킹**</Anchor> | 악성 코드는 인스톨 어트리뷰션 링크 클릭을 식별하여 클릭이 어트리뷰트되면 그 즉시 크레딧을 얻기 위해 다른 클릭을 전송합니다. | 동일한 앱에 대해 동일한 기기에서 클릭이 일어난 후 매우 빠르게 발생한 어트리뷰트 클릭을 차단합니다. |
| <span id="click-flooding"></span><Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/click-flooding/">**클릭 플루딩**</Anchor> | 인스톨 전 라스트 클릭을 얻기 위한 목적으로 다수의 사기성 클릭을 전송하는 모바일 프로드. | 전환율이 낮고 CTIT가 긴 사이트 ID에서 발생한 어트리뷰트 클릭을 차단합니다. |
| <span id="behavioral-anomalies"></span>**행동 이상 현상** | 일관적이지 않고 비정상적인 포스트 인스톨 활동을 생성하는 형태의 모바일 프로드. | 당사가 갖는 독자적인 데이터 규모 덕분에 앱, 지역, 미디어소스 및 퍼블리셔와 같은 여러 레벨에서 행동 인게이지먼트 패턴을 측정하고 이해할 수 있습니다. 비인간적인 행동 패턴은 거의 실시간으로 식별되어 소스에서 차단됩니다. |
| <span id="ip-denylists"></span>**IP 차단 목록** | 사기꾼들은 일반적으로 <Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/click-farms/">클릭 팜</Anchor>에서 활동하며, 이들은 장기간 동일한 IP 주소를 사용하는 것으로 식별될 수 있습니다. | <ul><li>사기 행위가 의심되는 IP 주소는 서드파티 글로벌 공급업체인 <Anchor target="_blank" href="http://www.digitalelement.com/">Digital Element</Anchor>로부터 수신된 최신 데이터를 기반으로 매일 차단 목록에서 제외됩니다.</li><li>의심 IP 차단 기능은 모든 앱에 대해 사용할 수 있습니다.</li></ul> |
| <span id="sdk-authentication"></span>**SDK 인증** | 사기꾼은 가짜 SDK 메시지를 전송하여 가치있는 사용자 행동을 시뮬레이션합니다. | <ul><li>앱스플라이어 자체 개발 해싱 프로토콜을 사용하여 SDK와 웹서비스 간 메시지를 암호화하여 사기꾼이 메시지를 모방할 수 없도록 합니다.</li><li>SDK 인증 보안 장치는 모든 앱에 대해 사용할 수 있습니다.</li></ul> |
| <span id="store-validations"></span>**스토어 유효성 검증** | 사기꾼들은 가짜 SDK 메시지를 보내 설치나 인앱 구매를 모방하여 높은 CPA 수수료를 청구합니다. <Anchor target="_blank" href="/marketers/ko/docs/implement-apple-app-store-itunes-install-validation">애플 스토어 검증</Anchor>. | iTunes 및 Google Play에서 발생한 모든 설치 또는 인앱 구매에 대해 <Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/install-validation/">설치 검증</Anchor> 및 인앱 구매 검증을 활성화하여 사기 행위의 귀속을 방지합니다. |

**참고**: 상기 언급된 정확한 시간 값은 고객 보호를 위해 공개하지 않습니다.

추가 차단 사유는 <Anchor target="_blank" href="/marketers/ko/docs/protect360-raw-data-reports">로데이터 문서</Anchor>를 참조하십시오.

</Accordion>

아래 표에는 다양한 유형의 사기 인스톨 및 인앱이벤트와 Protect360 엔진이 실시간으로 이를 차단하거나 포스트-어트리뷰션을 탐지할 때 발생하는 일이 요약되어 있습니다.

<table><thead><tr><th>프로드 유형</th><th>감지 시간</th><th>인스톨 시 발생하는 사항</th><th>인앱이벤트에 발생하는 사항</th></tr></thead><tbody><tr><td rowspan="2"><span>가짜 인스톨</span></td><td><span>실시간</span></td><td><span>실시간으로 차단됨</span></td><td><span>실시간으로 차단됨</span></td></tr><tr><td><span>포스트 어트리뷰션</span></td><td><span>Post-attribution 인스톨 리포트에 표시됨</span></td><td><ul><li><span>사기 행위가 감지되기 전에 발생한 인앱이벤트는 포스트 어트리뷰션 인앱이벤트 리포트에 표시됩니다.</span></li><li><span>감지 후: 실시간으로 차단됨</span></li></ul></td></tr><tr><td rowspan="2"><span>인스톨 어트리뷰션 하이재킹</span></td><td><span>실시간</span></td><td><ul><li><span>실시간으로 차단됨</span></li><li><span>어트리뷰션이 유효한 마지막 소스로 수정되었습니다.</span></li></ul></td><td><ul><li><span>원시 보고서에는 표시되지 않으며 대시보드에서만 볼 수 있습니다.</span></li><li><span>인스톨과 동일한 유효한 소스로 어트리뷰트됩니다.</span></li></ul></td></tr><tr><td><span>포스트 어트리뷰션</span></td><td><span>Post-attribution 인스톨 리포트에 표시됨</span></td><td><ul><li><span>사기 행위가 감지되기 전에 발생한 인앱이벤트는 포스트 어트리뷰션 인앱이벤트 리포트에 표시됩니다.</span></li><li><p>사기 탐지 후: 포스트 어트리뷰션 인앱이벤트 리포트에 인스톨 후 최대 30일까지 표시됩니다.\*</p><p>\*인앱 이벤트는 설치 후 30일 동안 마지막으로 유효한 미디어 소스로 수정됩니다. 30일 후에 발생하는 이벤트는 수정되지 않습니다.</p></li></ul></td></tr><tr><td rowspan="2"><span>사기성 인앱이벤트</span></td><td><span>실시간</span></td><td>-</td><td><span>실시간으로 차단됨</span></td></tr><tr><td><span>포스트 어트리뷰션</span></td><td>-</td><td><span>포스트 어트리뷰션 인앱이벤트 리포트에 표시됨</span></td></tr></tbody></table>

Protect360 사기 감지 및 결과

<div id="using-protect360" />

## Protect360 사용

<div id="dashboard" />

<Accordion title="대시보드">

<Anchor target="_blank" href="/marketers/ko/docs/protect360-dashboard">Protect360 대시보드</Anchor>는 집계된 사기 데이터를 표시하며 사기성 트래픽과 관련된 인사이트를 제공합니다.

대시보드 뷰:

인스톨 프로드 설치에 대한 <Anchor target="_blank" href="/marketers/ko/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTV 기반</Anchor> 인사이트, 실시간 차단 및 사후 어트리뷰션 분석을 통한 식별. 필터와 그룹화 옵션을 사용하여 드릴다운하면서, 사기 이벤트를 더 깊게 검사할 수 있습니다.

**인앱 이벤트**: 실시간으로 차단되거나 어트리뷰션 후에 식별된 사기성 인앱 이벤트에 대한 <Anchor target="_blank" href="/marketers/ko/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">활동 기반</Anchor> 인사이트 필터와 그룹화 옵션을 사용하여 드릴다운하면서, 사기 이벤트를 더 깊게 검사할 수 있습니다.

</Accordion>

<div id="raw-data" />

<Accordion title="로데이터">

사기에 대한 <Anchor target="_blank" href="/marketers/ko/docs/protect360-raw-data-reports">로데이터</Anchor>는 Pull API, Export Data 및 <Anchor target="_blank" href="/marketers/ko/docs/data-locker-for-marketers">Data Locker(프리미엄 기능)</Anchor>를 통해 사용할 수 있습니다.

로데이터 리포트는 다음과 같이 구분됩니다.

* 차단된 보고서: 어트리뷰션이 차단되어 어떤 미디어 소스에도 전혀 어트리뷰션되지 않은 사용자의 설치, 클릭 및 인앱 이벤트.
* 포스트 어트리뷰션 리포트:
  * 미디어 소스로 어트리뷰션된 인스톨이지만, 이후에 프로드로 밝혀짐.
  * 인앱 이벤트:
    * 미디어 소스에 어트리뷰션된 이후에 프로드로 식별된 인스톨의 인앱 이벤트.
    * 인스톨과 상관없이, 그 자체적으로 프로드로 판단된 인앱 이벤트.

* 광고주는 이런 리포트를 사용하여, 애드 네트워크 계정을 조정하고, 최적화하며, 포스트 어트리뷰션 사기 관련 어트리뷰션 대시보드를 조정합니다.

</Accordion>

<div id="validation-rules" />

<Accordion title="유효성 검증 규칙">

<Anchor target="_blank" href="/marketers/ko/docs/implement-validation-rules-to-prevent-fraud">유효성 검증 규칙</Anchor>을 사용하면 앱 소유자가 특정 인스톨을 차단하거나, 어트리뷰션을 차단하거나(그리고 인스톨이 가장 최근의 유효한 미디어소스에 기인하는지 확인) 인앱이벤트를 차단하는 조건을 설정할 수 있습니다.

</Accordion>

<div id="fraud-reconciliation-with-ad-networks" />

<Accordion title="애드 네트워크와의 프로드 조정">

Protect360을 사용하면 광고주들은 광고 네트워크가 사기 행위로 기록하지 않았을 수 있는 사기성 인스톨 및 앱 내 이벤트와 관련된 로데이터를 얻을 수 있습니다.

광고 네트워크가 의심스러운 소스에서 트래픽을 보낸 것을 발견한 경우 광고 네트워크에 알리고 의심스러운 소스에서 보낸 트래픽 전송을 중지하도록 요청합니다. **어트리뷰트된 터치 시간**이라는 로데이터 인스톨 리포트 열을 사용하여 중지 요청 후 소스에서 더 이상 인스톨이 수신되지 않는지 확인합니다.

또한 Protect360 데이터를 사용하여 광고 네트워크와 조정하고 의심스러운 소스의 과거 트래픽에 대해 전체 또는 부분적으로 환불받을 수 있습니다.

**프로텍트360을 사용하여 CPI 기반 캠페인을 조정하려면:**

* 매월 초에 프로드가 발생한 애드 네트워크의 계정 담당자에게 연락하십시오.
* [차단된 인스톨 및](/docs/protect360-anti-fraud-guide#postattribution-detection) 포스트 어트리뷰션 인스톨 리포트에서 관련 사기성 인스톨 로데이터를 수집합니다.
* 조정과 트래픽 최적화를 위해 네트워크로 프로드 로데이터를 공유합니다.
* 포스트 어트리뷰션 프로드 인스톨을 제외하고 유효한 인스톨만 포함한 로데이터 리포트를 생성하는 것도 가능합니다. 이를 위해서는, 월간 ***Attributed UA 인스톨*** 리포트를 다운로드 받고 ***포스트 어트리뷰션 인스톨*** 리포트의 모든 항목을 제외해야 합니다.

**프로텍트360을 사용하여 CPA/CPE 기반 캠페인을 조정하려면:**

* 매월 초에 프로드가 발생한 애드 네트워크의 계정 담당자에게 연락하십시오.
* [차단된 인앱이벤트 및](/docs/protect360-anti-fraud-guide#postattribution-detection) 포스트 어트리뷰션 인앱이벤트에서 관련 사기 인앱이벤트 로데이터를 수집합니다.
* 조정과 트래픽 최적화를 위해 네트워크로 프로드 로데이터를 공유합니다.
* 포스트 어트리뷰션 프로드 이벤트를 제외하고 유효한 인앱 이벤트만 포함한 로데이터 리포트를 생성하는 것도 가능합니다. 이를 위해서는, 월간 ***Attributed UA 인앱 이벤트*** 리포트를 다운로드 받고 ***포스트 어트리뷰션 인앱 이벤트*** 리포트의 모든 항목을 제외해야 합니다.

</Accordion>

<div id="traits-and-limitations" />

## 특징 및 제약 사항

<div id="traits-and-limitations::a07033c3" />

<Accordion title="특징 및 제약 사항">

| 특징 | 비고 |
| --- | --- |
| 광고주 액세스 | 모든 계정 사용자. |
| 광고 네트워크 액세스 | <ul><li><Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#애드-네트워크-권한">Protect360 대시보드 및 로데이터에 액세스하려면</Anchor> 광고주 권한이 필요합니다.</li><li>광고주는 광고 네트워크를 연동 파트너로 가져야 합니다.</li></ul> |
| 에이전시 액세스 | <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#애드-네트워크-권한">Protect360 대시보드 및 로데이터에 액세스하려면</Anchor> 광고주 권한이 필요합니다. |
| 에이전시 투명성 | 투명한 에이전시: 특정 미디어 소스를 볼 수 있습니다.<br /><br />비투명 에이전시: 특정 미디어 소스를 볼 수 없습니다. |
| 앱별 시간대 | <ul><li>모든 앱이 동일한 시간대로 설정된 경우 대시보드에서는 앱별 시간대가 사용됩니다.</li><li>앱이 동일한 시간대로 설정되지 않은 경우 대시보드는 기본적으로 UTC로 설정됩니다.</li></ul> |
| 데이터 최신성 | <ul><li>프로텍트360 대시보드 <Anchor target="_blank" href="/marketers/ko/docs/about-data-freshness-and-timezone-support#eod">일일</Anchor> 업데이트<br />가장 최근의 업데이트 시간이 대시보드 화면의 날짜 범위 필터 아래에 표시됩니다.</li><li>리포트:<ul><li>차단된 인스톨 및 인앱이벤트: 지속적로 거의 실시간 업데이트됩니다.</li><li>포스트 어트리뷰션: UTC 사용하여 <Anchor target="_blank" href="/marketers/ko/docs/about-data-freshness-and-timezone-support#eod">매일</Anchor></li></ul></li></ul> |
| 리인스톨 | 리인스톨에 대한 사기 데이터는 로데이터에서만 가능합니다. 따라서 대시보드의 전체 숫자와 로데이터 리포트 간에 불일치가 있을 수 있습니다. |
| 리타겟팅 | <ul><li>사기로 식별된 인스톨인 경우 인스톨, 리어트리뷰션, 리인게이지먼트 간의 어트리뷰션된 터치 유형 분석 결과가 표시됩니다.</li><li>인앱이벤트인 경우:<ul><li>인앱이벤트(CPA) 대시보드에 UA 인스톨로 인한 사기 이벤트가 표시되지만 리타게팅으로 인한 사기성 이벤트는 표시되지 않습니다.</li><li>실시간으로 식별된 리어트리뷰션의 사기 이벤트는 로데이터 리포트에서 확인할 수 있습니다. 리인게이지먼트를 통한 사기 이벤트는 식별할 수 없습니다.</li><li>리타게팅으로 인한 사기성 이벤트는 포스트 어트리뷰션을 식별할 수 없습니다.</li></ul></li></ul> |
| 제한 사항 | <ul><li>표는 최대 20,000행으로 제한됩니다.</li><li>더 큰 데이터 세트를 쿼리하면, 일부 미디어소스가 제외될 수 있습니다. 제한을 해결하려면, 다음을 권장합니다.<ul><li>더 작은 데이터 세트를 쿼리 - 더 작은 날짜 범위, 특정 앱 및 특정 미디어 소스</li><li><Anchor target="_blank" href="/marketers/ko/docs/protect360-raw-data-reports">Protect360</Anchor> 로데이터 리포트 내보내기</li><li><Anchor target="_blank" href="/marketers/ko/docs/pull-api-aggregate-data">Pull API를 통한</Anchor> Protect360 집계 고급 탐지 리포트 내보내기</li></ul></li></ul> |

특징 및 제약 사항

</Accordion>

<div id="faq-and-tips" />

## FAQ 및 팁

<div id="faq" />

<Accordion title="자주 묻는 질문">

| **프로텍트360은 커스텀 어트리뷰션 링크에서 발생한 프로드에 대해 작동합니까?**<br /><br />확실히요! 당연합니다! Protect360은 애드 네트워크 뿐만 아니라, 커스텀 어트리뷰션 링크에서 발생한 프로드도 탐지하고 차단합니다. 이것은 인플루언서, 이메일 및 문자 메시지 캠페인, 웹 사이트 배너와 랜딩 페이지, 소셜미디어의 바이럴 포스트, 푸시 알림 또는 QR 코드에 이르기까지 온드 미디어 캠페인을 운영하는 경우에도 광고주가 보호됨을 의미합니다. |
| --- |
| **Protect360 V2를 V1과 비교했을 때 새로운 점은 무엇입니까?**<ol><li>P360 V2.0에는 3가지 주요 변경 사항이 있습니다:<br />포스트 어트리뷰션 프로드 - 차단된 설치를 표시하는 곳에서는 포스트 어트리뷰션 프로드 설치도 함께 표시합니다. 포스트 어트리뷰션은 로데이터 리포트에서도 이용 가능합니다.</li><li>이상 현상 인사이트 - "이상 현상 인사이트" 섹션이 새로 추가되었으며, 광고주는 시각화 도구를 통해 이상 현상을 분석할 수 있습니다. 기존의 "고급 탐지" 탭의 차트 2개는 이것으로 대체됩니다.</li><li>모든 프러드 데이터 중앙 집중화 - "고급 탐지" 탭이 삭제되고 탭 하나로 모든 정보를 보여줍니다.</li></ol> |
| **왜 데이터 내보내기 페이지에서 포스트 어트리뷰션 로데이터를 이용할 수 없나요?**<br /><br />보다 원활한 비용 조정 과정을 위해 포스트 어트리뷰션 리포트는 미디어소스별 계정 레벨로 제공합니다. **데이터 내려받기** 페이지는 단일 앱 레벨이지만, 이전 버전과 호환성을 위해 앱 레벨에서 차단된 프로드 데이터를 계속 유지합니다. |
| **포스트 어트리뷰션 데이터는 소급하여 업데이트하나요?**<ul><li>**설치**- 개요 페이지 및 Protect360 대시보드 외부의 모든 보고서에 설치된 데이터는 소급 적용되지 않습니다.</li><li>**인앱 이벤트** - 포스트 어트리뷰션 보호 단계가 인스톨을 허위로 식별하고 나면, 이 인스톨에서 들어온 후속 인앱 이벤트는 차단됩니다. 이전의 인앱 이벤트는 소급해서 업데이트 되지 않습니다.</li></ul> |
| **이상현상 감지력에서 특정/다른 네트워크를 선택할 때 데이터가 다르게 보이는 이유는 무엇입니까?**<br /><br />CTIT(Click To Install Time, 클릭에서 앱 설치까지 소요시간) 이상을 살펴보고 AF\_Baseline을 벤치마크로 선택하면 네트워크 A의 이상이 나타날 수 있습니다. 그런 다음 예를 들어 네트워크 A를 벤치마크로 선택하면 네트워크 A가 아닌 다른 네트워크의 이상이 표시됩니다.<br /><br />이는 실제로 예상할 수 있는 결과입니다. 신뢰할 수 있는 앱스플라이어 기준선을 사용하면 CTIT 비율이 비정상인 네트워크가 표시됩니다. 이상 네트워크를 기준으로 사용할 경우 해당 설치는 더 이상 이상으로 포함되지 않지만, 다른 네트워크의 설치는 이와 관련하여 이상인 것으로 간주될 수 있습니다. |
| **비정상적인 오가닉 트래픽이 실제로 프로드 입니까?**<br /><br />오가닉 트래픽에서의 비정상적인 상승이 실제로 프로드일 가능성도 있습니다. 일반적으로, 앱스플라이어 상 실제로 프로드라고 믿을 만한 이유가 있는 오가닉 트래픽을 봤다면, 다음 세 가지 경우 중의 하나가 될 수 있습니다:<ul><li>**실패한 어트리뷰션 프로드:** 사기꾼의 클릭이 기여도 측정을 받지 못했습니다. 예를 들어, 클릭 플러딩이 발생했지만 마지막 클릭이 클릭 조회 기간을 초과해 발생한 경우입니다.</li><li>**비어트리뷰션 프로드: 이는 어트리뷰션과 무관한 유형의 프로드입니다. 예를 들어, 전략 게임에서 아이템을 부정하게 수집하는 행위를 의미합니다.**</li><li>**SDK 연동 문제: 인앱 이벤트가 올바르게 전송되는지 확인하십시오. 즉, 플로에서 적절한 시점에 전송되고 올바른 이벤트 매개변수 값을 포함하는지 확인하십시오.**</li></ul> |

자주 묻는 질문

</Accordion>

<div id="benchmarks-and-tips" />

<Accordion title="벤치마크 및 팁">

| **새 기기 프로드 감지**<br /><br />사기꾼들은 iOS의 IDFA  및 Android의 GAID와 같은 기기의 주요 ID를 자주 재설정함으로써 자신의 기기를 위장할 수 있습니다.<br /><br />다행히 앱스플라이어는 전 세계적으로 모바일 기기의 98% 이상을 식별합니다.<br /><br />그러므로 새 기기를 의도적으로 타게팅 하지 않는 이상 새 기기 비율이 굉장히 높게 형성되는 경우, 클릭 공장에 의한 프로드 가능성이 높습니다.<br /><br />**새 기기 탐지:**<ol><li>*Protect360에서* **식별된 프로드 분류표**로 이동하세요.</li><li>오른쪽으로 스크롤하여 디바이스 팜 지표 - 새 디바이스 열을 확인하세요.</li><li>**인스톨 %** 열 이름을 클릭하여 새 기기 비율 기준으로 표를 내림차순으로 정렬하세요.</li><li>신규 디바이스 사기 표시자:</li></ol><ul><li>새 기기 비율이 높은 소스. **참고**: 설치 수가 증가함에 따라, 낮은 비율도 사기로 간주될 수 있습니다(전체 규모가 크기 때문).<ul><li>소스 로열티 사용자 비율을 전체 로열티 사용자 비율과 비교할 때 상대적으로 낮은 비율은 사기를 나타내는 강력한 지표입니다.</li></ul></li></ul>**참고**: 사전 설치된 앱의 캠페인은 일반적으로 신규 기기 비율이 매우 높습니다. 이는 사용자가 새 기기를 활성화할 때 가장 먼저 실행하는 앱 중 하나일 수 있기 때문입니다. 따라서 사전 설치된 앱의 경우 새로운 기기 비율이 높지만 프로드일 가능성은 낮습니다. |
| --- |
| **광고 추적 제한(LAT) 프로드 감지**<br /><br />광고 추적 제한(LAT) 사용자는 선택적으로 광고주에게 기기 ID, IDFA 또는 GAID 노출을 옵트아웃할 수 있습니다. 대략적으로 iOS 사용자 15%와 Android 사용자 10%가 이렇게 선택합니다.<br /><br />새 기기 랭킹과 유사한 광고 추적 제한(LAT) 사용자는 합법적일 수 있습니다. 하지만, 이들 중 높은 비율이 사기성 활동일 수 있습니다.<br /><br />**광고 추적 제한(LAT) 탐지:**<ol><li>*Protect360에서* **식별된 프로드 분류표**로 이동하세요.</li><li>오른쪽으로 스크롤하여 장치 팜 지표 - LAT 장치 열까지 이동하십시오.</li><li>**인스톨 %** 열 이름을 클릭하여 광고 추적 제한(LAT) 기기 비율 기준으로 표를 내림차순으로 정렬하십시오.</li><li>LAT 기기 사기 표시자:</li></ol><ul><li>**LAT** 기기 비율이 높은 소스. **참고**: 설치 수가 증가함에 따라, 낮은 비율도 사기로 간주될 수 있습니다(전체 규모가 크기 때문).</li><li>소스 로열티 사용자 비율을 전체 로열티 사용자 비율과 비교할 때 상대적으로 낮은 비율은 사기를 나타내는 강력한 지표입니다.</li></ul> |
| <strong>클릭 도배 프로드 탐지</strong><ol><li>사기꾼들은 클릭 플러딩을 이용해 실제 기기 ID로 수백만 건의 클릭을 전송하며, 이를 통해 실제 사용자의 최종 클릭으로 등록되기를 노립니다. 이러한 유형의 프로드 소스는 전환율이 매우 낮지만, 실제 사용자이므로 고품질 사용자입니다.</li></ol><strong>클릭 플러딩 탐지:</strong><ol><li><em>Protect360에서</em> <strong>식별된 프로드 분류표</strong>로 이동하세요.</li><li>오른쪽으로 스크롤하여 클릭 플러딩 지표 열을 확인하세요.</li><li>변환율 열 이름을 클릭하면 변환율 순으로 테이블을 오름차순 정렬합니다.</li><li>클릭 도배 프로드 벤치마크:</li></ol><ul><li>정상 <strong><em>전환율</em></strong>은 0.5%에서 35% 사이입니다.<br />전환율이 비정상적으로 낮거나 <strong>앱의 평균 전환율의 25% 이하</strong>인 의심스러운 소스. 이 KPI는 대시보드 개요 페이지의 종합 성과 리포트 표에서 확인할 수 있습니다.</li><li>경계선상에 있는 소스의 경우 <strong><em>어시스트 %</em></strong>을 평균 어시스트 비율과 비교하세요. 대시보드 개요 페이지의 어시스트 위젯에서 일반적인 어시스트 비율을 확인할 수 있습니다. 앱의 평균 어시스트 비율보다 50% 높은 어시스트 비율을 보이는 소스는 의심스러운 것으로 간주됩니다.<br />앱이 사용하는 소스가 많을수록 컨트리뷰션 비율이 높아집니다.</li></ul> |
| **CTIT 지표가 포함된 클릭 도배 탐지**<br /><br />**또 다른 클릭 플러딩 징후는** CTIT가 고르게 분포될 때입니다.<br />일반적으로 약 70%의 인스톨이 광고 인게이지먼트 후 1시간 이내에 일어납니다.<br />클릭 도배 시 가짜 인게이지먼트와 실제 인스톨 사이에 연관성이 없습니다. 이는 1시간 이상의 CTIT를 가진 사기 설치 사례가 30%를 훨씬 초과하는 결과를 초래합니다.<br /><br />**클릭 플러딩 CTIT 징후 탐지:**<ol><li>*Protect360에서* **식별된 프로드 분류표**로 이동하세요.</li><li>오른쪽으로 스크롤하여 클릭 플러딩 지표 - CTIT 열을 확인하세요.</li><li>클릭 도배 CTIT 벤치마크:</li></ol><ul><li>보통 *60분 이상의 값은 30% 정도여야 합니다*. 이 지표가 50% 이상인 소스는 의심하세요.</li><li>보통  *5시간 이상의 값은 20% 정도여야 합니다*. 이 지표가 40% 이상인 소스는 의심하세요.</li></ul>**<Anchor target="_blank" href="/marketers/ko/docs/protect360-dashboard#anomalies-dashboard">이상 징후 인사이트</Anchor>** 페이지를 사용하여 의심스러운 CTIT를 가진 소스를 조사하세요. |

벤치마크 및 팁

</Accordion>

<div id="advanced-antifraud-tips" />

<Accordion title="고급 프러드 방지 팁">

| **설치 수**<br /><br />체크된 소스당 인스톨 수를 이용한 필터링은 매우 큰 사기 소스를 탐지하는 데 중요합니다. 또한, 인스톨 수가 적을수록 수학적으로 중요하지 않을 수 있습니다. 참고:<br /><br />**참고**: 인스톨이 30회 또는 50회 미만인 소스는 결론을 도출해야할 만큼 그렇게 중요하지 않습니다. 데이터 범위나 다른 검색 조건을 추가로 사용하여 더 중요한 결과를 얻어보세요. |
| --- |
| **로열 유저 정의 변경**<br /><br />기본적으로 로열 유저는 앱을 3번 이상 실행한 사용자로 정의합니다. 이는 사용자 참여도를 측정하는 중요한 핵심 성과 지표(KPI)이지만, 안타깝게도 많은 사기꾼들이 이를 알고 충성도 높은 사용자의 비율이 높은 것처럼 위장하여 의심을 피하는 데 이용합니다. 보다 명확하고 정교한 로열 유저 정의를 생성한 후 이를 선택하여 사기를 피하세요.<br /><br />가입, 튜토리얼 완료, 구매, 다수의 세션과 같은 앱 사용자 퀄리티 KPI를 분석하세요. 앱 코드 내에서 사용자가 모든 KPI 목록을 수행할 경우 새로운 ‘충성도 높은 사용자’ 인앱 이벤트를 전송합니다.<br /><br />첫 번째 논오가닉 충성도 높은 사용자 이벤트가 전송된 후, 앱 설정으로 이동하여 해당 이벤트를 선택하여 앱의 충성도 높은 사용자를 표시하십시오. 일반적인 로열 유저 비율이 약간 떨어질 것으로 예상되며 사기성 소스는 해당 비율이 급격하게 하락할 수 있습니다. |

고급 프러드 방지 팁

</Accordion>

<div id="tip" />

> 👍 **팁**
>
> 프로드 방지에 대해 더 알고 싶으신가요? <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7809/play/18635/mobile-app-fraud-and-protect360">앱스플라이어 학습 포털에서 짧지만 유익한 강의 코스</Anchor>를 확인해 보세요.

<div id="see-also" />

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/protect360-raw-data-reports">로데이터</Anchor>
> * <Anchor target="_blank" href="https://www.appsflyer.com/resources/others/marketers-guide-mobile-ad-fraud/">마케터를 위한 모바일 광고 사기 입문 가이드</Anchor>

<div data-zendesk-anchors="protect360-overview=protect360-%EA%B0%9C%EC%9A%94 h_01HE7RSPPQ4T5J3W038EZRCTCE=protect360-%EA%B0%9C%EC%9A%94 h_01HE7RSPPQ5BH7HBK0R8SY1T16=realtime-blocking h_01HE7RSPPRW4CQ3GB9ZEYAA6YN=postattribution-detection h_01HE7RSPPRYMQKJH46JET2ZZ0T=common-fraud-issues-and-solutions using-protect360=protect360-%EC%82%AC%EC%9A%A9 h_01HE7RSPPR8Y8J1VJJXXDCAZE6=protect360-%EC%82%AC%EC%9A%A9 h_01HE7RSPPR04G3SCSYHSWJKQDG=dashboard h_01HE7RSPPRS6PSTZCR5RT4A5ND=raw-data h_01HE7RSPPR8C9MHRAGJXYD2VVZ=validation-rules h_01HE7RSPPR1PQ2R6NJPRQGS1K1=fraud-reconciliation-with-ad-networks traits-and-limitations=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD h_01HE7RSPPRV797PS12NFQHX1X5=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD h_01HE7RSPPRWRKR1Y25PZV2RMVV=traits-and-limitations::a07033c3 faq-and-tips=faq-%EB%B0%8F-%ED%8C%81 h_01HE7RSPPSV2TT8SMK8JZXFKMC=faq-%EB%B0%8F-%ED%8C%81 h_01HE7RSPPS01J796008HDS1CRW=faq h_01HE7RSPPS018W98JWZGED54W8=benchmarks-and-tips h_01HE7RSPPSEDZWRH929DBSWEWM=advanced-antifraud-tips h_01HE7RSPPSY161MSQVQW7M767F=%ED%8C%81 h_01HE7RX6167Q5QP5JNZDSXCCK5=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
