---
title: 광고 수익 어트리뷰션 가이드
metadata:
  keywords:
    - ad revenue
    - ad monetization
    - monetization
    - Advertisers
    - adrevenue
    - Premium
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2016-12-12T10:53:27Z'
  edited_at: '2026-10-14T10:31:12Z'
  id: 217490046
  locale: ko
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/ko/articles/217490046
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **한눈에 보기:** 요약: 광고 수익을 어트리뷰트하여 LTV 성과 뷰를 완성합니다.

[![Attributes_ad_revenue.png](https://files.readme.io/e512531f0363fcda600fbad8ca8e5081d882b5721fb35fc9c449f8774859a5da-small-15734558614033.png)](https://files.readme.io/e512531f0363fcda600fbad8ca8e5081d882b5721fb35fc9c449f8774859a5da-small-15734558614033.png)

## 광고 수익 어트리뷰션

* 광고는 배너, 오퍼월(offer wall), 전면 광고 등으로 앱에 표시되며 광고 수익을 생성합니다.
* 인앱 구매와 결합된 광고 수익 및 구독 수익은 사용자의 전체 LTV 그림을 제공합니다. 사용자 LTV를 미디어 비용에 매칭함으로써, 캠페인 ROI를 결정하고 플랫폼에서 추가적인 분석을 위해 이용 가능합니다.

**어트리뷰트 광고 수익 데이터**:

* 서버 API 또는 앱에 내장된 리포트 SDK(iOS 14 포함)를 통해 중개 및/또는 광고 수익화 네트워크에서 획득합니다.
* 사용자를 원래 가져온 미디어 소스에 어트리뷰션 됩니다. 예를 들어:
  * 사용자는 네트워크 A에서 광고를 보고 앱을 다운로드합니다.
  * 광고는 앱 내부에 표시됩니다.
  * 누가 광고를 게시했든 간에 광고 수익은 네트워크 A(유저 인입 담당)로 어트리뷰트됩니다.
* 리포트 세분성은 수익 창출 네트워크 연동 및 광고 수익 어트리뷰션 유형에 따라 다릅니다.

<div id="integration-types-for-ad-revenue-attribution" />

<Accordion title="광고 수익 어트리뷰션을 위한 연동 유형">

**참고**:

| 광고 수익 어트리뷰션 연동 유형 | 설명 |
| --- | --- |
| S2S API를 통한 [집약형 수준](/docs/roi360-guide-ad-revenue-attribution#aggregate-granularity-using-app-open-or-inapp-events) | <ul><li>앱스플라이어는 지역 별로 구분된 일 별 수익을 수신합니다.</li><li>조치당 실효 수익(effective revenue per action, eRPA)은 광고 수익을 트리거 이벤트 횟수로 나누어 유도됩니다.</li><li>트리거 이벤트는 앱 오픈 또는 앱 내 설정된 특정 인앱 이벤트 중의 하나입니다.</li><li>중개 네트워크를 사용하는 경우에는 중개 네트워크를 통한 광고 수익 연동을 사용하기 전에 중개 네트워크를 통해 중개되는 수익화 파트너에 대한 광고 수익 연동을 비활성화했는지 확인하십시오. 이렇게 하지 않으면 중복 데이터가 발생합니다.</li></ul> |
| S2S API를 통한 [디바이스 수준](/docs/roi360-guide-ad-revenue-attribution#ad-revenue-raw-data) | <ul><li>중개 또는 수익 창출 네트워크는 기기 수준에서 사용자별 수익을 리포트합니다. 모든 네트워크가 디바이스 수준 세분성을 지원하는 것은 아닙니다.</li><li>수익은 사용자를 가져온 미디어 소스에 어트리뷰션 됩니다. 즉, 앱스플라이어 광고 수익 어트리뷰션은 플랫폼에 적용되는 어트리뷰션 규칙(리타게팅 어트리뷰션 규칙 포함)을 고수합니다.</li><li>중개 네트워크를 사용하는 경우에는 중개 네트워크를 통한 광고 수익 연동을 사용하기 전에 중개 네트워크를 통해 중개되는 수익화 파트너에 대한 광고 수익 연동을 비활성화했는지 확인하십시오. 이렇게 하지 않으면 중복 데이터가 발생합니다.</li><li>S2S API를 통한 디바이스 수준은 광고 수익의 100%를 포함하며 광고 수익 통합 유형의 데이터 정확도가 가장 높습니다.</li><li><Anchor target="_blank" href="/marketers/ko/docs/raw-data-reporting-overview">ATT는 로데이터 리포트에서 사용할 수 있습니다. 앱스플라이어는 사용자 단위 데이터의 포스트백을 연동 파트너에게 발송하지 않습니다.</Anchor></li></ul> |
| SDK를 통한 노출 수준 | <ul><li>노출 수준은 앱스플라이어가 데이터를 수신하는 방식을 나타냅니다. 데이터는 다른 세분성 수준(예: 기기 수준)에서 리포트될 수 있습니다.</li><li>중개 또는 수익 창출 네트워크는 노출 수준에서 사용자별 수익을 리포트합니다. 모든 네트워크가 노출 수준 세분성을 지원하는 것은 아닙니다.</li><li>수익은 사용자를 가져온 미디어 소스에 어트리뷰션 됩니다. 즉, 앱스플라이어 광고 수익 어트리뷰션은 플랫폼에 적용되는 어트리뷰션 규칙(리타게팅 어트리뷰션 규칙 포함)을 고수합니다.</li><li>중개 네트워크를 사용하는 경우에는 중개 네트워크를 통한 광고 수익 연동을 사용하기 전에 중개 네트워크를 통해 중개되는 수익화 파트너에 대한 광고 수익 연동을 비활성화했는지 확인하십시오. 이렇게 하지 않으면 중복 데이터가 발생합니다.</li><li>SDK를 통한 노출 수준은 모든 광고 수익 연동 유형 중 최고의 데이터 최신성을 가지고 있습니다.</li><li>SKAN을 지원합니다.</li></ul> |
| 노출 수준(SDK를 통해)과 디바이스 수준(S2S API를 통해) | <ul><li>SDK를 통해 도착하는 노출 수준 데이터가 X일에 어트리뷰트 및 리포트되도록 허용하고, 1일 이후에 API를 통해 도착하는 디바이스 수준 데이터로 전환할 수 있습니다. **참고**: 참고: Android의 경우 알 수 없는 기기에서 SDK를 통해 보고된 데이터(사용 가능한 기기 ID 없음)는 API를 통해 도착하는 데이터로 대체되지 않습니다.</li><li>데이터 최신성을 정확하게 유지합니다. 즉, X+1일 이후의 데이터 정확도와 함께 X일에 대한 데이터 최신성의 이점을 얻을 수 있습니다.</li><li>SKAN을 지원합니다.</li></ul> |

</Accordion>

## 구현하기

다음 절에서는 사용 가능한 광고 수익 어트리뷰션 유형과 구현 및 유지 관리에 필요한 워크플로 및 단계에 대해 설명합니다.

<div id="connect-to-ad-revenue-integrated-partners" />

<Accordion title="광고 수익 연동 파트너에 연결">

**시작하기 전에**:

* 광고 수익 연동 파트너에게 API 인증 정보를 요청하십시오.

**광고 수익 네트워크와 광고 수익 연동을 활성화하는 방법**:

1. 앱스플라이어의 사이드 메뉴에서 설정 > **수익 설정** > 광고 수익을 선택합니다.
2. 광고 수익 연동에서 + 광고 수익 연동 추가를 클릭합니다.
3. 매출 파트너 추가를 선택하고 다음을 클릭합니다. **[![ad revenue 3.6(2).png](https://support.appsflyer.com/hc/article_attachments/23135465810961)](https://support.appsflyer.com/hc/article_attachments/23135465810961)**
4. 받으려는 광고 수익 데이터 유형을 선택합니다. **참고**: 일러두기: 일부 광고 네트워크는 아래에 나열된 모든 옵션을 제공하지는 않습니다.
   * 어트리뷰션 수익. 유저 인입 소스에 기반한 수익을 의미합니다. 어트리뷰트 수익 리포트는 다음 수준일 수 있습니다.
     * S2S API를 통한 [집약형 수준](/docs/roi360-guide-ad-revenue-attribution#aggregate-granularity-using-app-open-or-inapp-events).
       * 광고 수익의 기반이 되는 이벤트를 선택합니다. 예를 들어, af\_app\_opened 이벤트를 선택하면 전체 광고 수익이 모든 앱이 열린 이벤트로 분배되어 앱당 광고 수익을 얻을 수 있습니다.
     * 기기 단위(S2S API를 통해)
       * **참고**: 참고 : 중재 네트워크의 디바이스 수준 광고 수익 API를 활성화하는 경우 중재 네트워크의 광고 수익 통합을 비활성화해야 합니다. 이렇게 하지 않으면 데이터 중복이 발생합니다.
     * SDK를 통한 노출 수준.
       * 앱 개발자에게 앱스플라이어 광고 수익 SDK 커넥터를 통합하도록 지시합니다.
     * 노출 수준(SDK를 통해)과 기기 수준(S2S API를 통해).
       * 앱 개발자에게 앱스플라이어 광고 수익 SDK 커넥터를 통합하도록 지시합니다.
     * **참고**: 중개 네트워크를 사용하는 경우에는 중개 네트워크를 통한 광고 수익 연동을 사용하기 전에 중개 네트워크를 통해 중개되는 수익화 파트너에 대한 광고 수익 연동을 비활성화했는지 확인하십시오. 그렇게 하지 않으면 데이터가 중복되게 됩니다.
5. 연동 파트너가 요구하는 API 인증 정보 또는 로그인 정보를 입력합니다. 이는 SDK 연동과는 관련이 없습니다.
6. 저장을 클릭하세요.
7. 만일 연결 테스트 버튼이 위의 이미지와 같이 표시되는 경우 **연결 테스트**를 클릭합니다.
   * API 키 인증됨이 표시되면, 과정을 성공적으로 완료한 것입니다.
   * 다른 메시지가 표시되면, [광고 수익 API 상태 및 테스트를](/docs/roi360-guide-ad-revenue-attribution#ad-revenue-api-status-and-testing) 참고하여 과정을 반복합니다.
8. 만약 Test Connection 버튼이 없다면, 절차를 완료한 것입니다.
9. [선택 사항] QA를 수행하고 앱스플라이어에 표시되는 광고 매출 데이터를 미디에이션 파트너 및 UA 파트너 대시보드에 표시되는 광고 매출 데이터와 비교합니다. <Anchor target="_blank" href="/marketers/ko/docs/compare-roi360-ad-revenue-data-with-partner-data">더 알아보기</Anchor>
10. [선택 사항] <Anchor target="_blank" href="/marketers/ko/docs/share-ad-revenue-data-with-partners">UA 시그널</Anchor> 및 광고 매출 이벤트 포스트백을 통해 파트너와 광고 매출 데이터를 공유하세요.

**참고**: 참고: 한 연동 유형에서 다른 연동 유형으로 변경하는 경우 변경 사항은 다음 날 오전 12시(UTC)에 적용됩니다.

</Accordion>

<div id="view-edit-and-delete-ad-revenue-integrated-partners" />

<Accordion title="광고 수익 연동 파트너 보기, 편집 및 삭제">

![delete_edit_adi.png](https://support.appsflyer.com/hc/article_attachments/13751607197713)

**광고 매출 네트워크 연동을 보거나, 편집하거나, 삭제하려면**:

1. 앱스플라이어의 사이드 메뉴에서 설정 > 수익설정**** > 광고 수익을 선택하고 앱을 선택합니다.  
   모든 파트너 연동 목록이 제품 및 연동 유형, 연동 상태, 광고 매출 이벤트 이름에 대한 정보와 함께 표시됩니다.
2. 연동 위로 마우스를 가져간 다음 필요에 따라 **편집** 또는 **삭제**를 클릭합니다.

</Accordion>

<div id="deduplicate-cross-referenced" />

<Accordion title="상호 참조된 광고 수익 중복 제거">

이러한 경우 각 중재 플랫폼은 해당 수익이 네트워크 중 하나에서만 중재되는 동안 생성되었는지 여부에 관계없이 연결된 광고 네트워크에서 생성된 모든 광고 수익을 리포트합니다.

**두 중재 플랫폼이 서로 상호 참조할 때 수익 데이터의 부분 중복을 방지하려면**:

2. 1. 앱스플라이어의 사이드 메뉴에서 설정 > **수익 설정** > 광고 수익을 선택합니다.
   2. **일반 설정에서** **두 중재 파트너가 서로 상호 참조할 때 광고 수익 중복 제거**를 클릭합니다. **참고**:
      * 예를 들어 플랫폼 1에 배너 및 전면 광고가 표시되고 플랫폼 2에 AppOpen 및 네이티브 광고가 표시되는 경우입니다.

[![dedup.png](https://support.appsflyer.com/hc/article_attachments/17299804281361)](https://support.appsflyer.com/hc/article_attachments/17299804281361)

</Accordion>

<div id="aggregate-granularity-using-app-open-or-inapp-events" />

<Accordion title="앱 오픈 또는 인앱 이벤트를 사용한 종합 단위 세분성">

광고 수익에 대한 집계 세분성은 다음과 같이 작동합니다.

* 연동 네트워크는 지역별로 일일 총 수익을 리포트합니다.
* 앱스플라이어는 광고 수익을 트리거 이벤트 횟수로 나누어서 eRPA (effective revenue per action)를 유도합니다.
* 앱스플라이어는 각 어트리뷰트 기기에 대한 총 eRPA를 포함하는 \_monetized 이벤트를 생성합니다. 예시, ad\_matched\_monetized.
* eRPA를 사용하면 수익은 미디어 소스에 어트리뷰션됩니다.
* 다음 이벤트 유형 중 하나를 사용할 수 있습니다.
  * **고유한 광고 수익화 인앱 이벤트**는 앱 내 별도 구현이 필요합니다.
  * **af\_app\_open\_event**는 기본으로 사용할 수 있습니다.
* 광고 수익 연동과 병행하여 인앱이벤트에서 광고 수익 금액을 리포트하지 마십시오. 왜냐하면 앱스플라이어는 수익을 광고 수익화 네트워크와 연동하여 수신하고 있기 때문에, 그렇게하면 대시보드에서 광고 수익이 중복될 수 있습니다.

#### 이벤트를 통한 종합 광고 수익

| 이벤트 메서드 | 구현 방법 | 고려 사항 |
| --- | --- | --- |
| 고유 수익화 인앱 이벤트 | <ul><li>인앱 이벤트가 광고 표시 시점에 설정됩니다.</li><li>이를 통해 사용자 액션을 별도 집계하고, 고급 eRPA 계산이 가능합니다.</li></ul> | <ul><li>개발자가 앱 코드에 구현해야합니다.</li><li>대시보드에서 광고 수익을 광고 수익화 네트워크 별로 구분할 수 있습니다.</li></ul> |
| af\_app\_opened 이벤트 | <ul><li>af\_app\_opened 이벤트는 앱스플라이어 SDK에 의해 기본으로 전송됩니다.</li><li>매 사용자 세션에 트리거 됩니다.</li></ul> | <ul><li>별도의 앱 코드 작업이 필요하지 않습니다.</li><li>빠르게 구현할 수 있습니다.</li><li>세션 당 한번의 광고만 게재하는 것이 아닌 이상, eRPA 값이 심각하게 왜곡됩니다.</li><li>광고 수익화 네트워크 별로 구분할 수 없습니다.</li><li>이벤트는 앱을 실행한 모든 사용자에 적용되며, 사용자의 광고 시청 의사에 대한 표시가 없습니다.</li></ul> |

#### 인앱 이벤트 메서드 비교

| 방법 | 장점 | 단점 | 고려 사항 |
| --- | --- | --- | --- |
| 같은 이벤트를 모든 네트워크에 사용합니다. 예, ad\_watched. 이것은 자동으로 ad\_watched\_monetized 이벤트를 생성하여 수익화 세부 사항을 포함합니다. | 구현하는데 가장 간단합니다. | 클릭 횟수나 네트워크 별 광고 수익과 같은 품질 정보가 없습니다. | <ul><li>주요 목표가 광고를 클릭하는 경향이 있는 사용자를 유입시키는 소스/캠페인을 찾는 것이라면 가장 적합합니다.</li><li>수익화 네트워크 성과를 비교하는데 적합하지 않습니다.</li></ul> |
| **(모범 사례)** 각 네트워크는 고유한 광고 시청 이벤트를 할당받습니다. 예시: ad\_watch\_admob,<br /><br /> ad\_watch\_vungle. | 전체적인 가시성과 로데이터 뿐만 아니라 대시보드에서 광고 수익화 네트워크를 비교할 수 있는 기능을 제공합니다. | 광고 수익이 단일 이벤트에서 누적되지 않습니다. 이벤트 갯수는 네트워크 갯수와 동일합니다. | 대시보드에서 광고 수익화 네트워크 간의 비교를 가능하게 합니다. 광고 수익은 네트워크 고유의 인앱이벤트를 사용하는 네트워크별로 구분됩니다. |

</Accordion>

<div id="ad-revenue-api-status-and-testing" />

<Accordion title="광고 수익 API 상태 및 테스트">

* 광고수익 연동의 운영현황은 다음과 같습니다.
  * <Anchor target="_blank" href="/marketers/ko/docs/dashboard-cost-and-ad-revenue-status">비용 및 광고 수익 통합 상태 대시보드</Anchor><Anchor target="_blank" href="/marketers/ko/docs/dashboard-cost-and-ad-revenue-status">: 계정에 있는 하나 이상의 앱에 대해 비용 통합이 활성화된 파트너의 중앙화된 목록입니다.</Anchor>
  * 어떤 파트너는 API 연결을 테스트할 수 있도록 했습니다.
  * API 연결이 작동하는지 확인하려면:
  * **연결 테스트**를 클릭합니다.  
     만약 그렇지 않은 경우, 다음 표의 수정 조치 안내를 따르십시오.

| 상태 | 의미 | 비고/필요한 조치 |
| --- | --- | --- |
| API key verified | <ul><li>연결이 활성되었으며, 데이터를 가져올 수 있습니다.</li><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-freshness-and-timezone-support#ad-revenue">하루에 한 번 데이터를 가져옵니다.</Anchor></li></ul> | 없음 |
| 잘못된 로그인 ID (Invalid Credentials) | 제공된 인증 정보 중 하나 또는 그 이상이 올바르지 않습니다. | 광고 수익 파트너로부터 정확한 인증 정보를 가져옵니다. |
| Missing configuration details | 하나 또는 그 이상의 인증 정보 필드가 완성되지 않았습니다. | 광고 수익 파트너의 대시보드에서 인증 정보를 가져오거나, 파트너에게 연락하여 인증 정보를 요청합니다. |

</Accordion>

## 광고 수익 데이터

광고 수익 데이터는 앱스플라이어 대시보드 및 로데이터 리포트를 통해 제공됩니다.

<div id="ad-revenue-aggregate-data" />

<Accordion title="광고 수익 집계 데이터">

광고 수익은 다양한 소스로부터의 사용자 품질을 시간에 따라 보여줍니다. 사용자가 계속해서 앱을 실행하고 광고에 참여하면, 그들의 LTV가 증가합니다.

**참고**: 일러두기: 다양한 대시보드 및 리포트에서 광고 수익 데이터 간에 불일치가 있을 수 있습니다. [더 알아보기](#is-there-discrepency).

광고 수익 어트리뷰션은 다음에서 사용할 수 있습니다.

* LTV 기반:

  * LTV 보고서
  * 코호트 대시보드 및 리포트
  * 마스터 API
* 액티비티 기반:
  * 대시보드가 액티비티(Activity)
  * 광고 수익 로데이터

#### **개요 대시보드 - 종합 성과 리포트**

[![](https://support.appsflyer.com/hc/article_attachments/360002239229)](https://support.appsflyer.com/hc/article_attachments/360002239229)

개요 대시보드에서:

* 수익을 포함한 값은 LTV입니다. <Anchor target="_blank" href="/marketers/ko/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTV 대 액티비티 데이터</Anchor>를 참고하십시오.
* **수익** 열은 광고 수익과 인앱 구매를 포함하는 모든 수익을 포함합니다.
* 광고 체계(미디어소스, 캠페인, 광고 세트, 지역)를 따라 내려가면서, 리포트에서 **현금화** 이벤트를 봅니다.

**이벤트 대시보드**[![](https://support.appsflyer.com/hc/article_attachments/360002218905)](https://support.appsflyer.com/hc/article_attachments/360002218905)

액티비티 대시보드에서:

* 수익을 포함한 값(value)들은 액티비티 날짜 기반입니다. <Anchor target="_blank" href="/marketers/ko/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTV 대 액티비티 데이터</Anchor>를 참고하십시오.
* **Average Actions per User** 는 사용자가 앱에 게시된 광고에 참여하는 경향을 나타냅니다.

> 📄 **예시**
>
> 세 명의 사용자가 2017년 12월 31일에 앱을 설치합니다. 이들은 다음과 같이 어트리뷰션 되었습니다.
>
> * 유저 A 애드 네트워크 A
> * 유저 B 애드 네트워크 B
> * 유저 C 오가닉
>
> 앱은 5개의 서로 다른 광고 수익화 플랫폼과 연동했습니다. 각 플랫폼은, 다음과 같이 앱스플라이어 SDK에서 이용하는 고유 인앱 이벤트를 사용합니다.
>
> * 메타 Audience Network: fb\_ad\_view
> * Chartboost: chartboost\_ad\_view
> * Admob: admob\_ad\_view
> * Applovin: applovin\_ad\_view
> * IronSource: is\_ad\_view
>
> 인스톨 후 4일이 지나고, 사용자들은 다음과 같이 광고에 노출되었습니다.
>
>
>
> | 사용자 | UA 네트워크 | fb\_  <br />ad\_view | chartboost\_  <br />ad\_view | admob\_  <br />ad\_view | applovin\_  <br />ad\_view | is\_ad\_view | 합계 |
> | --- | --- | --- | --- | --- | --- | --- | --- |
> | A | 애드 네트워크 A<br /><br />2017-12-31 | 2018-01-01<br /><br />$1 | 2018-01-02<br /><br />$1 | 2018-01-03<br /><br />$1 | 2018-01-04<br /><br />$1 |  | $4 |
> | B | 애드 네트워크 B<br /><br />2017-12-31 | 2018-01-02<br /><br />$1 |  | 2018-01-04<br /><br />$1 |  |  | $2 |
> | C | 오가닉<br /><br />2017-12-31 | 2018-01-01<br /><br />$1 |  |  |  | 2018-01-02<br /><br />$1 | $2 |
>
>
>
> 데이터를 봤을 때, 이제 일 별, 사용자 별 (그리고 인앱 이벤트 별)로 수집된 수익을 요약할 수 있습니다.
>
>
>
> | 사용자 | 2018-01-01 | 2018-01-02 | 2018-01-03 | 2018-01-04 | 총 LTV |
> | --- | --- | --- | --- | --- | --- |
> | A | $1 | $1 | $1 | $1 | $4 |
> | B |  | $1 |  | $1 | $2 |
> | C | $1 | $1 |  |  | $2 |
> | 합계 | $2 | $3 | $1 | $2 | $8 |
>
>
>
> **리포트 이해하기:**
>
> 언급한 바와 같이, 광고 수익은 사용자 LTV와 연계되어 있습니다. 그러므로, 대시보드에서 선택한 시간 기간은 인스톨 코호트이며, 현재 날짜, 시간까지의 수익이 총합됩니다. 두 가지 다른 날짜 선택을 한 리포트를 살펴보겠습니다.
>
> 통합 리포트 2017-12-31-2018-01-05
>
>
>
> | 네트워크 | LTV 수익 |
> | --- | --- |
> | 오가닉 | $2 |
> | 애드 네트워크 A | $4 |
> | 애드 네트워크 B | $2 |
> | Network C | $2 |
>
>
>
> 이 경우, 코호트는 2017-12-31 부터 현재 날짜인 2018-01-05 까지 앱을 인스톨한 사용자입니다. 이러한 사용자들에 의해 생성된 모든 수익은 사용자 유입 소스 별로 정렬되어, 사용자 LTV로 표시됩니다.

</Accordion>

<div id="ad-revenue-raw-data" />

<Accordion title="광고 수익 로데이터">

<Image alt="PremiumFeature.jpg" src="https://files.readme.io/674e5d0c9efde9d12008bd705b3ba95f04e133fec3f39d4278612675123d4de4-360007173877.jpg" width="78px" />

광고 수익 로데이터 리포트는 앱스플라이어와 디바이스 수준 또는 노출 수준 연동을 보유한 광고 수익화 네트워크에서 제공한 데이터를 포함하고 있습니다.

**광고 수익 로데이터 원칙**

* 데이터는 사용자 별 고유 노출(impression) 횟수로 집계됩니다. 고유 노출 수는 광고 수익화 네트워크, 광고 단위, 플레이스먼트의 조합에서 유도합니다.
* 노출 수준 로데이터는:
  * 디바이스 수준으로 집계되고 디바이스 수준 리포트에서 사용할 수 있습니다.
  * 데이터 락커의 노출 수준 리포트에서 사용할 수 있습니다.
  * [로데이터 최신성](/docs/roi360-guide-ad-revenue-attribution#data-freshness)은 액티비티 대시보드의 디바이스 수준 광고 수익과 동일합니다.

<table><thead><tr><th>보고서</th><th>내보내기<br/> </th><th>Pull API </th><th>데이터 락커</th></tr></thead><tbody><tr><td>어트리뷰션된 광고 수익 (논오가닉)</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>유기적 광고 수익</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>리타겟팅 광고 수익 </td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>노출 수준 로데이터 </td><td><span>-</span></td><td><span>-</span></td><td><span>✓ </span></td></tr><tr><td colspan="4"><p>\* 디바이스 단위에서 집계된 데이터로 하루에 여러 번 업데이트되는 버전식 리포트도 사용할 수 있습니다. 비버전 데이터 락커 리포트는 매일 제공됩니다.</p></td></tr></tbody></table>

**데이터 특성 및 필드**

광고 수익 리포트의 필드는 다음과 같이 채워집니다.

* 다음 표에 나열된 광고 수익 이벤트 자체적으로. 이러한 필드는 다음과 같이 구분됩니다.
  * 특정 예를 들어, impressions 및 placement. **참고**! 채워진 필드는, 이 섹션의 네트워크에 의한 필드 표에 나오듯이, 광고 수익화 파트너와 다릅니다.
  * 컨텍스트 상황: 다른 로데이터 리포트에서 비슷한 의미를 가지는 필드. 예를 들어, event name, event value, currency.
* 사용자를 유입시킨 미디어 소스로 이벤트를 어트리뷰션한 결과입니다. 즉, 이 필드는 해당 사용자를 유입시킨 전환 이벤트에서 복사된 것입니다. 예를 들어, 미디어 소스 및 캠페인. 이런 필드는 다음의 표에 나열되어 있지 않습니다.

#### 광고 수익에 의해 채워진 필드

| api\_name | 필드 이름 | 필드 유형 | 설명 |
| --- | --- | --- | --- |
| event\_time | 이벤트 시간 | 컨텍스트 | 수익이 어트리뷰션된 날짜 |
| event\_name | 이벤트 이름 | 컨텍스트 | Set to af\_ad\_revenue |
| event\_revenue | Event Revenue Currency | 컨텍스트 | <ul><li>이벤트 수익 통화를 사용한 수익 금액</li><li>0 값은 수익이 없는 광고 노출을 표시</li></ul> |
| 이벤트 수익 통화 | Event Currency | 컨텍스트 | 이벤트 수익 통화 |
| event\_revenue\_XXX | Event Revenue XXX | 컨텍스트 | <ul><li>데이터 락터에서는 항상 USD</li><li>풀(pull) API에서는 pull 할 때의 통화에 따라</li></ul> |
| country | 국가 | 컨텍스트 | 인스톨 전환에서 인스톨한 국가 |
| ad\_unit | 광고 단위 | 특정 | 광고의 유형 |
| 세그먼트 | 세그먼트 | 특정 | Ad placement 이름 |
| monetization\_network | Monetization Network | 특정 | 광고를 전송한 네트워크 |
| 노출 | 노출 | 특정 | 유저가 광고를 본 횟수 |
| mediation\_network | Mediation Network | 특정 |  |

#### 네트워크 별 필드

<table><thead><tr><th>표시 이름</th><th>애드몹</th><th></th><th>AppLovin MAX</th><th>Appodeal</th><th>Fyber</th></tr></thead><tbody><tr><td>광고 단위</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>세그먼트</td><td>-</td><td>(1)</td><td>-</td><td>-</td><td>-</td></tr><tr><td>배치</td><td>-</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Monetization Network</td><td><span>✓</span></td><td><span>✓</span></td><td>-</td><td><span>✓</span></td><td>-</td></tr><tr><td>노출</td><td><span>-</span></td><td>-</td><td><span>✓</span></td><td><span>✓</span></td><td>-</td></tr><tr><td>Mediation Network</td><td><span>-</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td>-</td></tr><tr><td colspan="6">(1) 광고주가 ironSource에서 이를 설정해야합니다.</td></tr></tbody></table>

[광고 수익 로데이터 샘플 보고서](https://docs.google.com/spreadsheets/d/e/2PACX-1vRm_1tevWFdzdj6JgdxYawLBtYAJj-ubDeY4g1QfbdSkd2-Adi18oemPMdd7m7cM2e3fzm7VH0w6lhD/pub?output=xlsx)

</Accordion>

<div id="data-freshness" />

<Accordion title="데이터 최신성">

데이터 최신성은 연동 유형 및 리포트 방법에 따라 다릅니다. 

S2S API 연동의 경우 데이터를 사용할 수 있는 가장 빠른 시기는 다음과 같습니다.

노출 수준 SDK 연동의 경우 데이터를 가장 빨리 사용할 수 있게 되는 시기는 다음과 같습니다.

* 대시보드 및 보고서 최상의 시나리오는 오전 5시(UTC)부터 X일에 시작하여 (데이터 락커를 통해) 4시간마다 하루에 약 6번 업데이트됩니다.
* 노출 수준 로데이터 리포트(데이터 락커를 통해)는 X일 오전 1시(UTC 기준)이며 시간별로 업데이트됩니다.

노출 수준(SDK를 통해)과 디바이스 수준(S2S API를 통해)의 경우 다음과 같이 X일의 데이터 정확도와 X일의 데이터 최신성을 얻을 수 있습니다.

* SDK를 통해 도착하는 노출 수준 데이터의 경우:
  * 대시보드 및 보고서 최상의 시나리오는 오전 5시(UTC)부터 X일에 시작하여 (데이터 락커를 통해) 4시간마다 하루에 약 6번 업데이트됩니다.
  * 노출 수준 로데이터 리포트(데이터 락커를 통해)는 X일 오전 1시(UTC 기준)이며 시간별로 업데이트됩니다.
* S2S API를 통해 도착하는 디바이스 수준 데이터의 경우:

**참고:** 참고:/span> 연동 유형을 변경할 때 과거 날짜의 이전 연동 유형을 통해 수신한 데이터는 새 연동 유형으로 다시 채워지지 않습니다. 예를 들어 X일에 연동 유형이 SDK에서 S2S로 변경된 경우 X+1일부터 데이터를 가져오고 X일 이전 날의 데이터는 가져오지 않습니다.

<div id="ad-revenue-data-locker-reports" />

<Accordion title="광고 수익 데이터 락커 리포트">

| 이름 | 최신성 | 리포트 섹션 |
| --- | --- | --- |
| 일일 광고 수익(디바이스 수준에서 집계) | 특정 날짜(X일)의 광고 수익은 다음 날(X+1일) 오후 8시(UTC)에 리포트됩니다.<br /><br />예를 들어 5월 1일의 광고 수익은 5월 2일에 리포트됩니다. | 이 리포트에는 어트리뷰트, 오가닉 및 리타게팅 AdRevenue 섹션이 포함되어 있습니다. |
| ***버전 지정 일일 광고 수익 리포트***(디바이스 수준에서 집계) | 일일 리포트는 다음과 같이 구성됩니다.<ul><li>수익 창출일(X일) 동안 4시간마다 생성된 당일 버전.</li><li>S2S API 리포트의 데이터를 기반으로 2일, 3일, 7일, 13일에 생성된 전체 버전.</li></ul>다시 말해 일일 리포트의 버전 집합에는 다음 버전이 포함됩니다.<ul><li>X일 00:00 — 04:00.</li></ul><ul><li>x+1일 00:00 — 24:00[S2S]</li><li>x+2일 00:00 — 24:00[S2S]</li><li>x+6일 00:00 — 24:00[S2S]</li><li>x+13일 00:00부터 24:00까지[S2S]</li></ul> | 각 리포트 버전에는 어트리뷰트, 오가닉 및 리타게팅 AdRevenue 섹션이 포함되어 있습니다. |
| 노출 수준 광고 수익 리포트(노출 수준) | 노출 수준 광고 수익 기록은 매시간 별도의 파일에 기록됩니다. |  |

</Accordion>

</Accordion>

## 추가 정보

<div id="migrating-from-aggregate-to-userlevel-granularity" />

<Accordion title="집계에서 디바이스 수준 세분성으로 마이그레이션">

* 마이그레이션은 과거의 광고 수익 데이터에 영향을 주지 않습니다. 이 데이터는 변경되지 않고 남아있습니다.
* 광고 수익 데이터는 하루 한번 UTC 시간대 1400시에 당겨지며(pull), 그 시점에 선택된 세분성 옵션을 사용합니다.
* 디바이스 수준 세분성에서는 인앱이벤트를 정의할 필요가 없습니다(집약 수준 리포트에서처럼). 이러한 이벤트를 계속 보낼 수 있지만 앱스플라이어의 디바이스 수준 세분성 리포트에는 영향을 주지 않습니다.

</Accordion>

<div id="faq" />

<Accordion title="자주 묻는 질문">

| **각 플랫폼에서의 광고 수익 총합을 어떻게 확인할 수 있습니까?**<ul><li>광고 수익 어트리뷰션은 유저 유입(UA) 소스와 연결되어 표시됩니다.</li><li>이는 ROI와 KPI의 LTV 보기를 제공합니다.</li><li>각 광고 수익화 플랫폼에서의 수익 총합을 보려면, [각 네트워크 별로 다른 인앱 이벤트를 사용하고](/docs/roi360-guide-ad-revenue-attribution#aggregate-granularity-using-app-open-or-inapp-events) 다음 절차를 진행하십시오.<ol><li>개요 대시보드에서 **집약형 성과 리포트 표**로 이동합니다.</li><li>**CSV 다운로드**를 클릭하여, 리포트를 다운로드합니다.</li><li>선택한 플랫폼의 수익화된 이벤트 **수익** 열을 총합합니다.<br />![revenue_sum_up.png](https://support.appsflyer.com/hc/article_attachments/360002218885)</li></ol></li></ul> |
| --- |
| **광고 수익이 액티비티 페이지에서 사용 가능합니까?**<br /><br />네. 액티비티 페이지는 인앱 이벤트와 광고 수익을 결합한 매출을 리포트 합니다. **참고:** 참고: 광고 수익 데이터는 이벤트 다음 날에 앱스플라이어로 일 별 전송됩니다. |
<span id="01ECF1PZ39C7CG3R7H9P64QF51"></span>| **연동 탭에서 파트너를 활성화해야합니까?**<br /><br />광고 수익화(광고 수익)만을 위해 파트너와 협업하는 경우, 연동 탭에서 **파트너 활성화**를 사용하도록 설정하지 마십시오. 광고 수익 탭에서 **광고 수익 얻기**만 활성화합니다. |
<span id="01ECF1PZ39KCKY2BC3ZGK3CA0V"></span>| **사용자가 앱스플라이어 SDK를 포함하지 않은 앱 버전을 가지고 있다면, 디바이스 수준 광고 수익이 어떻게 어트리뷰트됩니까?**<br /><br />광고 수익은 오가닉으로 어트리뷰션 됩니다. |
<span id="is-there-discrepency"></span>| **서로 다른 대시보드와 리포트에서 광고 수익 데이터 간에 불일치가 있습니까?**<br /><br />개요 대시보드와 로데이터 리포트, 활동 또는 코호트 대시보드의 광고 수익 데이터 간에 불일치가 있을 수 있습니다. 이유:<ul><li>데이터는 개요 대시보드 앞의 활동 및 코호트 대시보드에 표시되는 경우가 있습니다.</li></ul> |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="특징 및 제약 사항">

| 특징 | 비고 |
| --- | --- |
| 제한 사항 | 광고 수익 이벤트는 다음에서 사용할 수 없습니다.<ul><li>Push API</li><li>리타겟팅 대시보드</li></ul>디바이스 수준 세분성 제한 사항:<ul><li>af\_ad\_revenue 이벤트는 피벗에서의 코호트 및 마스터 API에서 사용할 수 없습니다.</li><li>해당 이벤트는 코호트 애널리틱스에서는 사용 가능합니다.</li><li><Anchor target="_blank" href="/marketers/ko/docs/applovin-max-ad-revenue-configuration#best-practice">메타 광고 **인앱** 비딩 수익을 구현한 경우 수치 차이가 발생할 수 있습니다.</Anchor></li></ul>af\_ad\_revenue 이벤트를 트리거하는 고유 사용자 수는 앱스플라이어 대시보드에서 지원되지 않습니다. |
| 광고 네트워크 액세스 | 코호트 리포트에 액세스할 수 없음 |
| 에이전시 액세스 | 에이전시:<ul><li>광고 수익 설정에 액세스할 수 없습니다.</li><li>그것과 관련된 모든 대시보드와 데이터를 볼 수 있습니다.</li></ul> |
| 에이전시 투명성 | 지원되지 않음 |
| 시간대 | 광고 수익은 앱스플라이어 대시보드에 표시되고 UTC 시간대로만 리포트됩니다. 즉, 데이터가 오후 2시 UTC+2에 리포트되면 앱스플라이어에서 오후 2시 UTC로 표시됩니다.<br /><br />이것은 앱스플라이어가 대부분 UTC로 데이터를 리포트하는 여러 소스 및 파트너로부터 수집된 데이터를 정규화해야 하기 때문입니다. |
| 통화 | 앱스플라이어에서는 다음 사항이 적용됩니다.<ul><li>대시보드는 광고주의 앱 고유 통화를 표시합니다.</li><li>로데이터 리포트는 원래 통화를 표시하며 광고주의 앱 고유 통화로 변환합니다.</li></ul> |
| 데이터 유형 | 오가닉 및 논오가닉 데이터가 모두 지원됩니다. |
| 데이터 최신성 | [광고 수익](/docs/roi360-guide-ad-revenue-attribution#data-freshness) |
| 과거/소급 데이터 | <ul><li>데이터는 연동 당일부터 가져와 사용할 수 있습니다. 즉, 연동일(0일) 이전에는 과거 데이터를 사용할 수 없습니다.</li><li>특정 날짜의 S2S API를 통해 수신된 광고 수익 데이터는 1, 2, 3일에 업데이트됩니다.</li><li>고급 수익 패키지가 있는 경우 데이터는 데이터 락커에서도 업데이트됩니다.</li></ul> |
| 계정 유저 액세스 | 지원됨. |
| SKAN | 노출 수준 광고 수익 SDK 커넥터에서 지원됩니다. |
| 지역/국가 | 코호트 대시보드에서, 지역을 알 수 없는 경우(N/A인 경우), 지리별로 집계될 때 N/A 데이터가 표시되지 않습니다. |
| 인앱 이벤트 포스트백 | <ul><li><Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#포스트백-발송-옵션">더 알아보기</Anchor></li></ul> |
| CTV, PC, 콘솔 앱 | <ul><li>Android 및 iOS 앱만 지원됩니다.</li></ul> |
| 상호 참조된 광고 수익 중복 제거 |  |

</Accordion>

<div id="list-of-ad-revenue-integrated-partners" />

<Accordion title="광고 수익 연동된 파트너 목록">

<table><thead><tr><th rowspan="2">파트너</th><th colspan="3"></th></tr><tr><th></th><th>디바이스 수준</th><th></th></tr></thead><tbody><tr><td>Admost</td><td>-</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><a href="AppLovin" target="_blank">AppLovin</a></td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td><a href="AppLovin" target="_blank">AppLovin Max</a></td><td>-</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><a href="./appodeal-campaign-configuration" target="_blank">Appodeal</a></td><td>-</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td> <a href="./bytedance-ads-china-campaign-configuration" target="_blank">Bytedance Ads - 중국 트래픽</a> </td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td></td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td><a href="Chartboost" target="_blank">Chartboost</a></td><td><span>✓</span></td><td>-</td><td><span>✓</span></td></tr><tr><td></td><td>-</td><td>-</td><td><span>✓</span></td></tr><tr><td>Google Marketing Platform -DV360/CM (DoubleClick)</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td><a href="./meta-ads-integration-setup" target="_blank">Meta Ads</a></td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td><a href="./fyber-campaign-configuration#ad-revenue-tab" target="_blank">Fyber</a></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><a href="./google-admob-ad-revenue-attribution-configuration" target="_blank">Google Admob</a></td><td><span>✓</span></td><td>-</td><td><span>✓</span></td></tr><tr><td>InMobi</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td> </td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Mintegral</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td></td><td>-</td><td><span>✓</span></td><td>-</td></tr><tr><td>Tapjoy</td><td>-</td><td><span>✓</span></td><td>-</td></tr><tr><td>Topon</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Topon Pte.</td><td>-</td><td>-</td><td> <span>✓</span><br/> </td></tr><tr><td>Tradplus</td><td>-</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><a href="./unity-ads-campaign-configuration" target="_blank">Unity Ads</a></td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td></td><td>-</td><td>-</td><td><span>✓</span></td></tr><tr><td></td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td><a href="./vungle-campaign-configuration" target="_blank">벙글</a></td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>Yandex</td><td>-</td><td>-</td><td><span>✓</span></td></tr></tbody></table>

</Accordion>

<div data-zendesk-anchors="ad-revenue-attribution=%EA%B4%91%EA%B3%A0-%EC%88%98%EC%9D%B5-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 01ECF1PZ2XNCHR4QPATTBV0VMV=%EA%B4%91%EA%B3%A0-%EC%88%98%EC%9D%B5-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 01ECF1PZ2Y6ZBAWSNQPEXGJWX3=integration-types-for-ad-revenue-attribution implementation=%EA%B5%AC%ED%98%84%ED%95%98%EA%B8%B0 01ECF1PZ2Y9ERT5C50ZD4CDJET=%EA%B5%AC%ED%98%84%ED%95%98%EA%B8%B0 01ECF1PZ31TBRGG7GW3404Y1HN=connect-to-ad-revenue-integrated-partners 01H8V10BKK6TVY9G1KWC273K0S=deduplicate-cross-referenced aggregate-ad-revenue-using-events=%EC%9D%B4%EB%B2%A4%ED%8A%B8%EB%A5%BC-%ED%86%B5%ED%95%9C-%EC%A2%85%ED%95%A9-%EA%B4%91%EA%B3%A0-%EC%88%98%EC%9D%B5 01H8V10BKK06Z3E823G6GNTPKH=%EC%9D%B4%EB%B2%A4%ED%8A%B8%EB%A5%BC-%ED%86%B5%ED%95%9C-%EC%A2%85%ED%95%A9-%EA%B4%91%EA%B3%A0-%EC%88%98%EC%9D%B5 comparison-of-inapp-event-methods=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%A9%94%EC%84%9C%EB%93%9C-%EB%B9%84%EA%B5%90 01H8V10BKKMG2A704NZC2VFSJM=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%A9%94%EC%84%9C%EB%93%9C-%EB%B9%84%EA%B5%90 01ECF1PZ32Z4C20NADJ2SF3EPC=ad-revenue-api-status-and-testing ad-revenue-data=%EA%B4%91%EA%B3%A0-%EC%88%98%EC%9D%B5-%EB%8D%B0%EC%9D%B4%ED%84%B0 01ECF1PZ3315R242DC78HV60YC=%EA%B4%91%EA%B3%A0-%EC%88%98%EC%9D%B5-%EB%8D%B0%EC%9D%B4%ED%84%B0 01ECF1PZ33EJHN1YY0DMFKWY7N=ad-revenue-aggregate-data overview-dashboard-aggregated-performance-report=%EA%B0%9C%EC%9A%94-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C---%EC%A2%85%ED%95%A9-%EC%84%B1%EA%B3%BC-%EB%A6%AC%ED%8F%AC%ED%8A%B8 01ECF1PZ348365STFGE3136WEJ=%EA%B0%9C%EC%9A%94-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C---%EC%A2%85%ED%95%A9-%EC%84%B1%EA%B3%BC-%EB%A6%AC%ED%8F%AC%ED%8A%B8 01ECF1PZ348P0JCBASS4QBD56W=%EC%98%88%EC%8B%9C 01ECF1PZ36R9W7A0X4WBR95JDS=ad-revenue-raw-data fields-populated-by-ad-revenue=%EA%B4%91%EA%B3%A0-%EC%88%98%EC%9D%B5%EC%97%90-%EC%9D%98%ED%95%B4-%EC%B1%84%EC%9B%8C%EC%A7%84-%ED%95%84%EB%93%9C 01H8V10BKK7BHC31W27G22D23K=%EA%B4%91%EA%B3%A0-%EC%88%98%EC%9D%B5%EC%97%90-%EC%9D%98%ED%95%B4-%EC%B1%84%EC%9B%8C%EC%A7%84-%ED%95%84%EB%93%9C fields-by-network=%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EB%B3%84-%ED%95%84%EB%93%9C 01H8V10BKKW6NERRYCRD6BVZ54=%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EB%B3%84-%ED%95%84%EB%93%9C 01H8V10BKK6N5XJ6GHKC201E3Y=data-freshness 01H8V10BKKG50X5RZR8T2YB092=ad-revenue-data-locker-reports additional-information=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 01H8V10BKMX7H9H04ZBF3HRJVY=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 01H8V10BKMH781GR6GHFSD5N50=migrating-from-aggregate-to-userlevel-granularity 01H8V10BKM75W6YZ59S6FHFY93=faq 01ECF1PZ39PTEPWJDQA4XPBR4R=traits-and-limitations 01ECF1PZ3A2E5GVNC6D6XDC6WW=list-of-ad-revenue-integrated-partners" />
