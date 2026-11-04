---
title: 로데이터 필드 사전
metadata:
  keywords:
    - raw reports
    - facebook rawdata
    - facebook raw data
    - Developers
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Raw Reports
  created_at: '2016-03-10T14:37:44Z'
  edited_at: '2026-10-14T10:30:12Z'
  id: 208387843
  locale: ko
  section: Raw data reporting/APIs
  section_id: 6550930711057
  url: https://support.appsflyer.com/hc/ko/articles/208387843
---
> **한눈에 보기:** 데이터 필드 사전(로데이터 명세서)은 필드 내용을 설명합니다. 필드의 의미, 형식, 이용 가능 시기를 이해하는 데 도움이 됩니다.

<div id="overview" />

## 개요

로데이터 필드 사전표는 다양한 앱스플라이어 리포트에서 사용 가능한 로데이터 필드를 나열합니다. AppsFlyer에 추가 로데이터 필드가 추가되어 있기 때문에 표는 지속적으로 업데이트되고 있습니다.

사전 표의 열은 다음과 같습니다.

* **필드 그룹:** 필드 사용에 따른 논리적 그룹화. **참고**! 광고 수익 그룹의 필드는 로데이터 리포트에 별도의 열로 표시되거나 **이벤트 값**의 일부로 표시됩니다.
* **이름:**
  * 데이터 락커 및 Push API 보고서에 표시되는 필드 이름입니다.
  * [n] 표기법은 같은 필드의 여러 인스턴스가 있음을 의미하며, 이들의 차이는 해당 인스턴스 번호입니다. 예를 들어, Sub Param [n]은 Sub Param 1, Sub Param 2, ..., Sub Param 5를 의미합니다. n 값의 범위는 (n=1-5)로 표시됩니다.
* **필드 이름**:
  * 내보내기 페이지와 Pull API를 통해 제공된 보고서에 사용되는 필드 이름입니다.
  * [n] 표기법은 같은 필드의 여러 인스턴스가 있음을 의미하며, 이들의 차이는 해당 인스턴스 번호입니다. 예를 들어, Sub Param [n]은 Sub Param 1, Sub Param 2, ..., Sub Param 5를 의미합니다. n 값의 범위는 (n=1-5)로 표시됩니다.
* **소스**: 필드 콘텐츠의 원래 소스 위치입니다.
  * **링크**: 어트리뷰션 링크(<Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters">앱스플라이어 어트리뷰션 링크 구조와 파라미터</Anchor> 참조) 또는 해당되는 경우 SRN의 API에서 수집됩니다.
  * **SDK**: 앱 내 SDK를 통해 수집됩니다.
  * **AF**: 앱스플라이어에서 발생한.
  * 그리고 더 많은 내용.
* **설명**
  * 일부 필드는 이벤트의 상황에 따라 의미가 달라질 수 있습니다. 예를 들어 UA 또는 리타겟팅 캠페인의 결과일 수 있습니다.
* **형식:** 필드 유형 및 길이.
  * <span id="wYXz"></span>**문자열**: 문자열의 최대 길이. 길이가 1024자를 초과하거나 필드 길이 제한을 초과하지 않는 것이 좋습니다. 이 제한은 <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#어트리뷰션-링크-파라미터ua-및-리타겟팅">여기</Anchor>에서 확인할 수 있습니다.
  * 날짜 시간
    * `yyyy-mm-dd hh:mm:ss` 형식의 문자열입니다. 예를 들어, `2019-09-17 00:09:25` 데이터 표시에 사용되는 표준 시간대는 다음과 같이 데이터 전달 도구에 따라 달라집니다.
      * 데이터 내보내기 페이지: 앱에서 선택한 시간대.
      * 푸시 API: 시간 필드에는 앱별 시간대를 의미하는 *selected\_time\_zone* 옵션이 있고, 그렇지 않으면 UTC입니다.
      * 마스터 API: 기본값은 앱에서 선택할 수 있는 시간대입니다.
      * 데이터 락커: UTC
    * CSV 파일의 날짜 필드는 yyyy-mm-dd 형식을 갖습니다. Excel에서 CSV 파일을 열면 날짜 필드는 컴퓨터의 날짜 및 시간 설정을 사용하여 형식이 지정됩니다. [Excel](https://support.office.com/en-us/article/format-a-date-the-way-you-want-8e10019e-d5d8-47a1-ba95-db95123d273e#ID0EAACAAA=Windows)에서 표시 형식을 변경할 수 있습니다. 서식이 지정되지 않은 값을 보려면 편집기를 사용하여 파일을 엽니다.
    * 푸시 API:
      * UTC 타임스탬프 필드의 경우: 형식 `yyyy-mm-dd hh:mm:ss.sss`. 예를 들어, `2019-09-17 00:09:25.123`
      * 선택한 시간대의 타임스탬프 필드: 형식 `yyyy-mm-dd hh:mm:ss.sss±th:tm`. 예를 들어 `2019-01-20 04:51:16.000+0000`
  * **열거형 n 문자**: 열거형 필드는 특정 값만 포함할 수 있습니다. 예를 들어, 비용 통화에는 3개의 문자가 있으며 지정된 대로 통화 코드만 포함할 수 있습니다.
  * **열거형 5 문자 부울: `FALSE` 필드의 값은 `FALSE` 또는 `FALSE` 중 하나일 수 있습니다.**

<div id="event-2" />

<div id="attribution::860c6c0d-2" />

<div id="device-info::63466612" />

<div id="device-info::5aed5231" />

<div id="field-dictionary" />

<div id="tip" />

> 👍 **팁**
>
> * 표를 정렬하려면 열 이름을 클릭하세요.
> * 또한 <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRDdd2FKVQ0eISEwGVYyTeF4JD0rlOLnrepz8Nf1R3Kc6o7AESDwXQLOuSB41xN6wIuhmIFlb5b9Gvp/pub?output=xlsx">표</Anchor> 를 다운로드할 수 있습니다.
> * 다운로드된 CSV에는 위에서 언급한 필드 외에도 추가 필드가 포함되어 있습니다.
>   * **주요 앱스플라이어 리포트 스키마의 일부**:
>     * 대부분의 앱스플라이어 리포트는 동일한 스키마로 작성되며 동일한 필드를 포함합니다.
>     * 일부 필드는 리포트와 데이터가 광고 네트워크, 광고주, 디바이스 플랫폼 등에서 수집되는지 여부에 따라 null 또는 빈 값으로 채워질 수 있습니다.
>     * 귀사의 BI 시스템을 구성할 때, 리포트가 항상 null이나 빈 값으로 반환하더라도 모든 주요 앱스플라이어 스키마 필드를 설정하는 것이 좋습니다. 이를 통해 데이터가 사용 가능해지면 쉽게 수집할 수 있습니다.
>     * 필드가 앱스플라이어 리포트 스키마의 일부가 아닌 경우, 특정 리포트에서만 포함됩니다. 예를 들어 SKAN 리포트가 있습니다.
>   * **리포트 전달 방법**: 해당 필드가 Push API, 데이터 내보내기/Pull API 또는 데이터 락커로 제공되는지를 나타냅니다. **참고**: 필드가 앱스플라이어 리포트 스키마의 일부라 하더라도 특정 방법으로 전달되는 리포트에는 포함되지 않을 수 있습니다. 예를 들어, 배치 필드는 앱스플라이어 기본 스키마에 포함되어 있지만, 데이터 락커, Pull API 또는 데이터 내보내기 페이지를 통해서만 표시되며, Push API를 통해서는 제공되지 않습니다.

| 필드 그룹 | 이름 | 필드 이름 | 소스 | 설명 | 형식 |
| --- | --- | --- | --- | --- | --- |
| <span id="attribution::xde448d77"></span>어트리뷰션 | ad\_id | 광고 ID | 링크 | 특정 광고에 할당된 고유 식별자<ul><li>[af\_ad\_id와 동일](#attribution::de448d77)입니다.</li><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="attribution::b19119e4"></span>어트리뷰션 | {"ad_id__assist_[n]"} (n=1-3) |  | AF | 첫 번째 보조 어트리뷰션에서 오는 특정 광고에 할당된 고유 식별자입니다.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="xattribution"></span>어트리뷰션 | ad\_name | 광고 이름 | 링크 | 광고에 할당된 설명적인 레이블<ul><li>[af\_ad와](#attribution) 동일.</li><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="attribution::ce2d519c"></span>어트리뷰션 | {"ad_name__assist_[n]"} (n=1-3) |  | AF | 첫 번째 보조 어트리뷰션에서 오는 광고에 할당된 설명 레이블입니다.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="skan"></span>SKAN | ad\_network\_ad\_id | 광고 ID | 애드 네트워크 | 광고 ID | 문자열 |
| <span id="skan::2fb2335a"></span>SKAN | 애드 네트워크 광고 이름 | 광고 이름 | 애드 네트워크 | 광고 이름 | 문자열 |
| <span id="skan::5dca70a1"></span>SKAN | ad\_network\_adset\_id | 광고 세트 ID | 애드 네트워크 | 광고 세트 ID | 문자열 |
| <span id="skan::d952fce5"></span>SKAN | 애드 네트워크 광고 세트 이름 | 광고 세트 이름 | 애드 네트워크 | 광고 세트 이름 | 문자열 |
| <span id="skan::6f93cee6"></span>SKAN | ad\_network\_campaign\_id | 캠페인 ID | 애드 네트워크 | 애드 네트워크가 앱스플라이어에 보고한 캠페인 ID | 문자열 |
| <span id="skan::ccaf995e"></span>SKAN | ad\_network\_campaign\_name | 캠페인 | 애드 네트워크 | 애드 네트워크가 앱스플라이어에 보고한 캠페인 이름 | 문자열 |
| <span id="skan::5fe116d5"></span>SKAN | 애드 네트워크 채널 | Channel | 애드 네트워크 | 필드가 보고서에 추가되지만 반드시 채워지지는 않습니다. | 문자열 |
| <span id="skan::5125d426"></span>SKAN | 애드 네트워크 크리에이티브 | 크리에이티브 | 애드 네트워크 | <ul><li>값은 애드 네트워크에서 수신한 데이터 보강에 기반합니다.</li><li>SKAN 3의 경우 값은 null입니다.</li></ul> | 문자열 |
| <span id="skan::5a2fa279"></span>SKAN | 애드 네트워크 이름 | 애드 네트워크 이름 | 애드 네트워크 | 애드 네트워크가 앱스플라이어에 보고한 애드 네트워크 이름입니다.<ul><li>이 필드가 비어 있으면 애드 네트워크가 해당 정보를 제공하지 않았거나 제공할 수 없습니다.</li><li>skad\_ad\_network\_id를 사용하여 애드 네트워크 이름을 확인할 수 있습니다. 이를 위해 <Anchor target="_blank" href="/marketers/ko/docs/skan-integrated-partners-list#apple-skadnetwork-ids-of-ad-networks">이 표</Anchor>를 사용하세요.</li></ul> | 문자열 |
| <span id="skan::39724216"></span>SKAN | ad\_network\_source\_app\_id | 광고 네트워크 소스 앱 ID | 애드 네트워크 | 애드 네트워크가 보고한 퍼블리셔 앱 ID입니다. 비용 조정 시 사용되며 애드 네트워크에 의해 보고됩니다. 퍼블리셔 앱은 이 데이터의 기반을 제공합니다. | 문자열 |
| <span id="skan::11414be7"></span>SKAN | ad\_network\_timestamp | 애드 네트워크 타임스탬프 | 애드 네트워크 | <ul><li>애드 네트워크가 포스트백을 수신한 시간입니다.</li><li>Google Ads의 경우 이 필드는 채워지지 않습니다.</li></ul> | 타임스탬프 |
| <span id="device-info::e7dfb109"></span>디바이스 정보 | ad\_personalization\_enabled | ad\_personalization\_enabled | SDK | 사용자가 Google이 개인 맞춤형 광고를 위해 사용자 수준 데이터를 사용하는 것을 허용하는 데 동의했는지(true) 또는 동의하지 않았는지(false)를 나타냅니다. | Boolean |
| <span id="attribution::7ea87d9e"></span>어트리뷰션 | ad\_placement | 광고 배치 | 링크 | CTV 광고 배치에 포함됨 | 문자열 |
| <span id="ad-revenue::a77b252f"></span>광고 수익 | 광고 유형(ad\_revenue\_ad\_type) | 광고 수익 광고 유형 | 광고 수익 SDK | 표시된 광고의 유형 | 문자열 |
| <span id="ad-revenue::e2b62d09"></span>광고 수익 | ad\_revenue\_custom\_parameters | 광고 수익 커스텀 파라미터 | 광고 수익 SDK | 앱에 표시되는 광고에 대해 광고주가 광고 수익 SDK를 통해 제공한 커스텀 파라미터. | 문자열 |
| <span id="attribution::x5954755967"></span>어트리뷰션 | ad\_type | 광고 유형 | 링크 | 광고 유형은 인게이지먼트 유도한 광고의 유형을 정의합니다.<ul><li>[af\_ad\_type](#attribution::59547559)과 동일.</li><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="ad-revenue"></span>광고 수익 | ad\_unit | 광고 단위 | 광고 수익 API | A/B 테스트 수행 시 광고 수익 광고 세그먼트 이름 | 문자열 |
| <span id="device-info::ce4bb08e"></span>디바이스 정보 | ad\_user\_data\_enabled | ad\_user\_data\_enabled | SDK | 사용자가 Google이 측정 및 개인화된 광고를 위해 사용자 수준 데이터를 사용하는 것에 동의했는지 여부를 나타냅니다 (true), 아니면 그렇지 않음 (false) | Boolean |
| <span id="attribution::x9b2f9ab6"></span>어트리뷰션 | adset\_id | Adset ID | 링크 | 캠페인 내 광고 세트를 식별하는 고유 식별자입니다.<ul><li>[af\_adset\_id와 동일](#attribution::9b2f9ab6)입니다.</li><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="attribution::9964905a"></span>어트리뷰션 | {"adset_id__assist_[n]"} (n=1-3) |  | AF | 첫 번째 보조 어트리뷰션에서 오는 캠페인 내 광고 세트에 대한 고유 식별자입니다.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="attribution::x5209dd66"></span>어트리뷰션 | adset\_name | 광고 세트 이름 | 링크 | 캠페인 내 광고 그룹<ul><li>[af\_adset에](#attribution::5209dd66) 동일합니다.</li><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="attribution::f348c026"></span>어트리뷰션 | {"adset_name__assist_[n]"} (n=1-3) |  | AF | 첫 번째 보조 어트리뷰션에서 오는 캠페인 내 광고의 그룹입니다.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="device-info-advertising-id"></span>디바이스 정보 | advertising\_id | 안드로이드 디바이스용 광고 ID | SDK | <ul><li>사용자가 재설정할 수 있는 디바이스 ID, 일명 GAID.</li><li>CTV의 경우, 이는 CTV ID입니다(예: RIDA 또는 VIDA).</li></ul> | 문자열 |
| <span id="attribution::929faa8"></span>어트리뷰션 | advertising\_id\_type | 광고 ID 유형 | 링크 | <ul><li>사용자가 재설정할 수 있는 장치에 대한 고유 식별자 유형입니다.</li><li>advertising\_id\_value 필드에 제공된 광고 ID의 유형을 지정합니다. 일반적인 유형에는 IDFA(iOS) 및 GAID(Android)가 포함됩니다.</li></ul> | 문자열 |
| <span id="attribution::be9cb893"></span>어트리뷰션 | advertising\_id\_value | 광고 ID 값 | 링크 | 사용자가 재설정할 수 있는 장치의 고유 식별 가치 .<ul><li>[advertising\_id](#device-info-advertising-id), [idfa](#device-info::e0372922), [oaid와](#device-info::4afa15f) 동일.</li><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="attribution"></span>어트리뷰션 | af\_ad | Ad | 링크 | 광고 이름 | 문자열 |
| <span id="attribution::de448d77"></span>어트리뷰션 | af\_ad\_id | 광고 ID | 링크 | 광고 ID | 문자열/정수 |
| <span id="attribution::59547559"></span>어트리뷰션 | af\_ad\_type | 광고 유형 | 링크 | <ul><li>예: 배너, 푸터</li></ul> | 문자열 |
| <span id="attribution::5209dd66"></span>어트리뷰션 | af\_adset | Adset | 링크 | 광고 세트 이름은 하나 이상의 광고가 포함된 그룹을 식별합니다. | 문자열 |
| <span id="attribution::9b2f9ab6"></span>어트리뷰션 | af\_adset\_id | 광고 세트 ID | 링크 | 광고 세트 ID, 하나 이상의 광고가 포함된 그룹을 식별합니다. | 문자열 |
| <span id="skan::1e316e1d"></span>SKAN | af\_attribution\_flag | AF 어트리뷰션 플래그 | AF | <ul><li><Anchor target="_blank" href="/marketers/ko/docs/skan-modeled-data#null-conversion-values">SSOT (Single Source of Truth) 메커니즘</Anchor>이 활성화된 경우: true인 경우, 인스톨이 앱스플라이어와 SKAN 둘 다에 의해 어트리뷰트됨. false인 경우, 인스톨이 앱스플라이어에 의해 어트리뷰트되지 않음. skad\_conversion\_value가 null인 경우, 플래그는 true 또는 false입니다(모델링 기준).</li></ul> | Boolean |
| <span id="attribution::acbd5bea"></span>어트리뷰션 | af\_attribution\_lookback | 어트리뷰션 룩백 윈도우 | 링크 | <ul><li>특정 광고에 인스톨이 측정될 수 있는 최대 기간입니다.</li><li>UA: 클릭 어트리뷰션의 경우, af\_click\_lookback 어트리뷰션 링크 매개변수를 설정합니다.</li><li>리타겟팅: 앱 설정에서 <Anchor target="_blank" href="/marketers/ko/docs/set-up-re-attribution-window#setting-the-re-attribution-window">리타겟팅 클릭-쓰루 룩백</Anchor>를 설정합니다.</li></ul> | 문자 |
| <span id="attribution::reqloopback"></span>어트리뷰션 | requested\_lookback\_window |  | AF | 참여 URL에 지정된 원시 비구문 값입니다. 클릭 또는 노출이 전환에 귀속될 수 있는 기간을 결정할 때 사용됩니다.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="attribution::75430560"></span>어트리뷰션 | af\_c\_id | 캠페인 ID | 링크 | 캠페인 ID | 문자열 |
| <span id="iap::a1f84da0"></span>인앱결제 (IAP) | af\_cancelation\_date\_ms |  | AppsFlyer 구매 검증 | 취소 날짜 |  |
| <span id="attribution::1d1e08b5"></span>어트리뷰션 | af\_채널 | Channel | 링크 | 미디어 소스 채널 예시: Google의 YouTube, Meta Ads의 인스타그램 | 동적 열거형 문자열 |
| <span id="attribution::8c179e3b"></span>어트리뷰션 | af\_cost\_currency | 비용 화폐 단위 | 링크 | <Anchor target="_blank" href="http://www.xe.com/symbols.php#section1">ISO-4217을 준수하는 3자리 통화 코드(USD, EUR)</Anchor> 기본값은 USD입니다. | 문자열 |
| <span id="attribution::8733a05b"></span>어트리뷰션 | af\_cost\_model | 비용 모델 | 링크 | 어트리뷰션 링크에 보고된 비용 모델입니다. CPC/CPI/CPM/기타. 현재 모든 비용은 이 값과 관계없이 CPI에 따라 계산됩니다. | 문자열 |
| <span id="attribution::5647f309"></span>어트리뷰션 | af\_cost\_value | 비용 값 | 링크 | 비용 통화의 금액입니다. 소수점 이하 4자리까지 허용됩니다. 예시: 320.5095 | 문자열 |
| <span id="subscription"></span>구독 | af\_cuids | CUID | AppsFlyer 구매 검증 | <ul><li>ARS의 컨텍스트에서는 이 매개변수에 모든 CUID가 포함된 배열이 들어 있습니다.</li><li>CUID 배열은 디바이스 ID와 상관없이 표시됩니다. 따라서 동일한 CUID가 여러 디바이스 ID에 표시될 수 있습니다.</li></ul> |  |
| <span id="iapsubscription"></span>IAP 구독 | af\_discount\_id | 할인 ID | AppsFlyer 구매 검증 | 초기 구매 시 유저에게 제시된 제안 ID입니다. 할인 코드가 있는 경우에만 ID가 채워집니다. |  |
| <span id="subscription::83d8905f"></span>구독 | af\_discount\_type | 할인 유형 | AppsFlyer 구매 검증 | 유저가 사용한 할인 유형입니다. 가능한 값:<ul><li>iOS:<ul><li>소개</li><li>구독</li></ul></li><li>안드로이드:<ul><li>소개 가격</li><li>일회용 코드</li><li>vanity\_code</li></ul></li></ul> |  |
| <span id="attribution::4c444ee7"></span>어트리뷰션 | af\_engagement\_destination | 인게이지먼트 목적지 | AF | 광고에서 연결된 목적지 카테고리(예: **웹** 랜딩 페이지, **모바일** 앱(딥링크 또는 앱 스토어) 또는 **CTV**, **PC** 또는 **Console**와 같은 다른 목적지 유형)를 나타냅니다. | 문자열 |
| <span id="iapsubscription::6b5c7f1f"></span>IAP 구독 | af\_환경 | 환경 | AppsFlyer 구매 검증 | 데이터를 수신하는 환경으로, 운영 또는 샌드박스 중 하나입니다. |  |
| <span id="subscription::9d10090e"></span>구독 | af\_expires\_date\_ms | 구독 만료 날짜 |  | 현재 구독 청구 주기의 만료 날짜 |  |
| <span id="attribution::9dd48973"></span>어트리뷰션 | af\_키워드 | 키워드 | 링크 | 유저가 온라인 검색 시 사용한 단어들입니다. 애드 네트워크에서 보고된 내용입니다. | 문자열 |
| <span id="iapsubscription::ebbabfd3"></span>IAP 구독 | af\_net\_revenue | 순 이익 | True Revenue API | 모든 요인을 고려하여 계산된 순수익입니다. af\_net\_revenue\_factors를 참조하십시오. |  |
| <span id="iapsubscription::d4d47a47"></span>IAP 구독 | af\_net\_revenue\_country | 순수익 국가 | True Revenue API | 세금이 적용되는 두 글자의 ISO 국가 코드입니다.<ul><li>예시: GB</li></ul> |  |
| <span id="iapsubscription::398dcab"></span>IAP 구독 | af\_net\_revenue\_factors | 순수익 요인 | True Revenue API | 리포트된 af\_net\_revenue 금액을 생성하는 모든 요인 이유를 나타내는 배열입니다.<ul><li>예시 값: store\_commission</li></ul> |  |
| <span id="iapsubscription::45acb981"></span>IAP 구독 | af\_net\_revenue\_postal\_code | 순수익 우편 번호 | True Revenue API | 문자 및\/또는 숫자 문자열<ul><li>예시: L4J8E3</li></ul> |  |
| <span id="iapsubscription::e1bc387a"></span>IAP 구독 | af\_net\_revenue\_subdivision | 순수익 세분화 | True Revenue API | 일부 국가에는 추가적인 주\/구역이 있을 수 있습니다. 이는 ISO 3166-2 구역 코드에 따라 처리됩니다.<ul><li>국가 코드와 구역 코드가 포함됩니다.</li><li>예시: US-CA</li></ul> |  |
| <span id="iapsubscription::9767b912"></span>IAP 구독 | af\_net\_revenue\_tax\_exclusive | 세금 제외 순수익 | True Revenue API | <ul><li>boolean 매개변수로, true나 false 중 하나입니다.</li><li>false는 세금이 전체 수익에 포함됨을 의미합니다.</li><li>true는 세금이 전체 언급된 수익에 추가됨을 의미합니다. 예를 들어, 미국 또는 캐나다에서는 가격표에 판매세가 포함되어 있지 않습니다.</li></ul> |  |
| <span id="iapsubscription::60f8530"></span>IAP 구독 | af\_net\_revenue\_tax\_name | 순수익 세금명 | True Revenue API | 특정 세금 유형을 설명하는 고객 청구서에 표시되는 이름입니다.<ul><li>예시: 매출, VAT, GST</li></ul> |  |
| <span id="iapsubscription::e9ec3c4c"></span>IAP 구독 | af\_net\_revenue\_tax\_rate | 순 수익 세율 | True Revenue API | 4자리 소수점까지의 세율을 나타냅니다.<ul><li>예시: 7.25</li></ul> |  |
| <span id="iapsubscription::ddec7a40"></span>IAP 구독 | af\_offer\_id | 제공 ID | AppsFlyer 구매 검증 | 거래에 적용된 오퍼 ID(해당할 경우, 예: 할인 또는 프로모션 오퍼). | 문자열 |
| <span id="iapsubscription::6a1d1d2a"></span>IAP 구독 | af\_original\_transaction\_id | 기존 거래 ID | AppsFlyer 구매 검증 | <ul><li>원래 거래 ID</li><li>iOS 전용</li></ul> |  |
| <span id="subscription::b4ee3dae"></span>구독 | af\_기간\_유형 | 구독 기간 유형 | AppsFlyer 구매 검증 | <ul><li>구독 또는 체험 기간 유형.</li></ul>가능한 값:<ul><li>시험, 소개, 정상</li></ul> |  |
| <span id="iapsubscription::bb6f0cb2"></span>IAP 구독 | af\_product\_id | 제품 ID | AppsFlyer 구매 검증 | 구독 제품 ID |  |
| <span id="attribution::9067a60e"></span>어트리뷰션 | af\_prt | 파트너 | 링크 | 기관 식별자 SKAN의 경우 채워지지 않을 수 있음 | 문자열 |
| <span id="iapsubscription::a48bb9e9"></span>IAP 구독 | af\_purchase\_date\_ms | 구매 날짜 | AppsFlyer 구매 검증 | 신고된 제품 ID 인앱 이벤트에 대한 구매 날짜 |  |
| <span id="iapsubscription::a56bb9e9"></span>인앱결제 (IAP) | af\_purchase\_option\_id | 구매 옵션 ID | AppsFlyer 구매 검증 | 거래와 연결된 구매 옵션 ID. | 문자열 |
| <span id="iapsubscription::a49872e9"></span>인앱결제 (IAP) | af\_purchase\_option\_type | 구매 옵션 유형 | AppsFlyer 구매 검증 | 거래의 구매 옵션 유형. 가능한 값(안드로이드): 구매, 임대. | 문자열 |
| <span id="iap"></span>인앱결제 (IAP) | af\_구매\_상태 | 구매 상태 | AppsFlyer 구매 검증 | 가능한 값:<ul><li>구매됨</li><li>취소됨</li><li>보류 중</li></ul> |  |
| <span id="iapsubscription::4d962f68"></span>IAP 구독 | af\_purchase\_token | 구매 토큰 | AppsFlyer 구매 검증 | <ul><li>거래에 대한 구매 토큰</li><li>안드로이드 전용</li></ul> |  |
| <span id="iapsubscription::b0119997"></span>IAP 구독 | af\_이유 | 이유 | AppsFlyer 구매 검증 | 취소나 이탈 관련 이벤트에서 사용자가 이탈하거나 취소한 이유입니다. 가능한 값:<ul><li>iOS:<ul><li>취소\_의도</li><li>청구\_문제</li><li>가격 인상 거부</li><li>제품\_사용 불가</li></ul></li><li>안드로이드:<ul><li>이 서비스를 충분히 사용하지 않음</li><li>기술적인 문제</li><li>비용 관련 이유</li><li>더 나은 앱을 찾았습니다</li><li>기타</li></ul></li><li>구독 재개 이벤트에서 유저가 구독을 재개한 이유입니다. 가능한 값: 안드로이드: 중지 및 재개됨<br />자동 갱신 비활성화 및 활성화</li><li>환불 관련 이벤트에서는 유저가 환불을 받은 이유를 제공합니다. 가능한 값: iOS: 1: 귀사의 앱에 문제가 있음<br />0: 다른 이유</li></ul> |  |
| <span id="attribution::15cc3657"></span>어트리뷰션 | af\_재참여\_창 | 리인게이지먼트 기간 | 링크 | 리타겟팅: 이벤트가 리타겟팅 캠페인에 어트리뷰션되는 기간<ul><li>참고: 리타겟팅 캠페인에서는 이 필드가 채워지지 않습니다.</li></ul> | 문자열 |
| <span id="iapsubscription::d5fc1fe4"></span>IAP 구독 | af\_refunded\_transaction\_ids | 환불 거래 ID | AppsFlyer 구매 검증 | <ul><li>환불된 모든 거래 ID의 목록</li><li>iOS 전용</li></ul> |  |
| <span id="attribution::e9b53459"></span>어트리뷰션 | af\_siteid | Site ID | 링크 | 퍼블리셔 ID | 문자열 |
| <span id="iapsubscription::22a14b24"></span>IAP 구독 | af\_store | 스토어 | AppsFlyer 구매 검증 | 구독 상품이 구매된 앱 스토어 |  |
| <span id="attribution::eaeca85c"></span>어트리뷰션 | af\_sub[n] (n=1-5) | 하위 파라미터 [n] | 링크 | 광고주가 어트리뷰션 링크에 입력한 파라미터 | 문자열 |
| <span id="attribution::9fdff16d"></span>어트리뷰션 | af\_sub\_siteid | 하위 사이트 ID | 링크 | 서브 퍼블리셔 ID | 문자열 |
| <span id="subscription::6f140cd3"></span>구독 | af\_subscription\_ownership\_type | 구독 소유 유형 | AppsFlyer 구매 검증 | FAMILY\_SHARED는 유저가 가족 공유를 통해 액세스할 수 있음을 의미합니다. PURCHASED는 결제 유저가 구매했음을 의미합니다. |  |
| <span id="iapsubscription::4571d5da"></span>IAP 구독 | af\_트랜잭션\_아이디 | 트랜잭션 ID | AppsFlyer 구매 검증 | <ul><li>트랜잭션의 ID</li><li>iOS 전용</li></ul> |  |
| <span id="attribution::x9067a60e"></span>어트리뷰션 | 에이전시 | 대행사 | 링크 | 에이전시 식별자<ul><li>[af\_prt와](#attribution::9067a60e) 동일.</li><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="attribution::ba8e1da9"></span>어트리뷰션 | {"agency__assist_[n]"} (n=1-3) |  | AF | 첫 번째 보조 어트리뷰션에서 오는 에이전시 식별자<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="device-info::a9ae30bc"></span>디바이스 정보 | amazon\_aid | 아마존 파이어 ID | SDK | Amazon 디바이스에서 사용자가 재설정할 수 있는 광고 ID. | 문자열 |
| <span id="device-info::3a055021"></span>디바이스 정보 | android\_id | 안드로이드 ID | SDK | 영구 디바이스 ID | 문자열 |
| <span id="attribution::fbb2666c"></span>어트리뷰션 | app\_group\_id | 앱 그룹 ID | AF | 크로스 플랫폼 어트리뷰션을 위한 관련 OneLink 템플릿에 속하는 연결된 앱 | 문자열 |
| <span id="app"></span>앱 | app\_id | 앱 ID | SDK | 앱스플라이어의 고유한 앱 식별자. 예시:<ul><li>iOS: id123456789</li><li>안드로이드: com.appsflyer.referrersender</li></ul> | 문자열 |
| <span id="app::38720e5d"></span>앱 | app\_name | 앱 이름 | SDK | 해당 애플리케이션의 공식 명칭은 공개 앱 스토어 및 HQ1에 표시되는 이름입니다. 이 가치 은 사용자에게 표시되는 값이며 내부 또는 번들 식별자와 다를 수 있습니다. 표시 및 리포팅 에 사용됩니다.<ul><li>광고주가 설정</li></ul> | 문자열 |
| <span id="attribution::b4bcbe76"></span>어트리뷰션 | app\_store\_id | 앱 스토어 ID | AF | 앱스토어에 표시되는 앱 ID | 문자열 |
| <span id="app::5a1697f1"></span>앱 | app\_type | 앱 유형 | 앱 클립 | 값:<ul><li>app\_clip, full\_app</li></ul> | 문자열 |
| <span id="app::f992fbe9"></span>앱 | app\_version | 앱 버전 | SDK | 고객의 SDK 또는 Appsflyer S2S API를 통해 보고된 고객 앱의 버전입니다.<ul><li>광고주가 설정</li></ul> | 문자 |
| <span id="app::avc00001"></span>앱 | app\_version\_\_conversion | 변환 시 앱 버전 | SDK | 변환 시 고객의 SDK 또는 AF S2S API를 통해 보고된 고객 앱의 버전입니다.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="device-info::98b3ecc7"></span>디바이스 정보 | appsflyer\_id | 앱스플라이어 ID | SDK | <ul><li>앱이 디바이스에 설치될 때 SDK에 의해 생성된 고유 ID입니다. ID는 LTV(유저생애가치) 흐름에서 인앱 이벤트를 어트리뷰트하고, 전환 데이터를 가져오며, 인앱 이벤트를 제휴하는 데 사용됩니다.</li><li>앱을 삭제하고 다시 설치하면 새로운 ID가 발생한합니다. iCloud 백업에서 앱을 복원하는 것은 설치로 간주되지 않습니다.</li><li>CTV의 경우, 이 필드는 광고주가 관리하는 디바이스 ID인 custom\_device\_id로 채워집니다.</li></ul> | 문자열 |
| <span id="device-info"></span>디바이스 정보 | appsflyer\_id\_type | Appsflyer ID 유형 | SDK | appsflyer\_id\_value의 출처를 식별합니다. 예를 들어 모바일 SDK 또는 웹 SDK와 같습니다.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="device-info::b482a05"></span>디바이스 정보 | appsflyer\_id\_value | Appsflyer ID 값 | SDK | 모바일 앱 설치 또는 웹 세션과 같은 단일 컨텍스트를 나타내는 데 사용되는 플랫폼 범위 식별자입니다.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="device-info::dd85d811"></span>디바이스 정보 | att | 앱 추적 투명성(ATT, AppTrackingTransparency) | SDK | <ul><li>앱 추적 투명성(ATT, att\_status)은 iOS 14+에서 사용할 수 있으며 다음 중 하나의 값으로 채워집니다. <Anchor target="_blank" href="https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/">ATTrackingManager</Anchor>가 반환한 값으로, S2S가 전송하고, 앱스플라이어가 결정했습니다.</li><li>앱 추적 투명성(ATT) <Anchor target="_blank" href="/marketers/ko/docs/att-implications-ios-14-and-deprecation-of-lat">값</Anchor>는 다음 중 하나입니다: not\_determined, restricted, denied, authorized, af\_unknown, af\_authorized, af\_unavailable.</li></ul> | 문자열 |
| <span id="attribution::46498f6f"></span>어트리뷰션 | attributed\_touch\_time | 어트리뷰션된 터치 시간 | AF | <ul><li>UA: 측정된 터치 시간입니다.</li><li>리타겟팅: 측정된 인게이지먼트 시간입니다.</li></ul> | 날짜 시간 |
| <span id="attribution::65deebe6"></span>어트리뷰션 | attributed\_touch\_type | 어트리뷰션된 터치 유형 | AF | 인게이지먼트를 분류합니다. 인게이지먼트가 인스톨과 매치된 후 앱스플라이어에 의해 설정됩니다.<ul><li>UA: 가능한 값: 클릭, 다운로드, 노출, 사전 인스톨</li><li>리타겟팅: 클릭, 노출</li></ul> | 열거형 |
| <span id="protect360"></span>Protect360 | blocked\_reason | 차단된 이유 | AF | Protect360: 인스톨이 차단된 이유. 예: install\_hijacking, 봇 | 문자열 |
| <span id="protect360::e47c57b1"></span>Protect360 | 차단 이유 규칙 | 차단된 이유 규칙(폐지됨) | AF | 폐지됨 | 문자열 |
| <span id="protect360::ecb2f1e5"></span>Protect360 | 차단 이유 값 | 차단된 이유 값 | AF | Protect360: 차단에 대한 추가 정보. 예시: 사이트 ID, 유효성 검증 규칙 이름 | 문자열 |
| <span id="protect360::e5842829"></span>Protect360 | 차단된 하위 이유 | 차단된 하위 이유 | AF | Protect360: 인스톨이 차단된 특정 하위 이유. 예시: 이유: install\_hijacking. 하위 이유: 레퍼러 하이재킹, CTIT\_anomalies, 유효성 검증 규칙 | 문자열 |
| <span id="app::d66d86c7"></span>앱 | bundle\_id | 번들 ID | SDK | <Anchor target="_blank" href="https://developer.apple.com/documentation/appstoreconnectapi/bundle_ids">iOS: iOS에서 단일 앱 또는 앱 그룹을 일치시키기 위한 식별(Apple 개발자 번들 ID</Anchor> 참조)<ul><li>안드로이드: 앱 ID</li><li>참고: 이 필드는 앱스플라이어 PBA와 관련이 없습니다.</li></ul> | 문자열 |
| <span id="attribution::274e74d5"></span>어트리뷰션 | 캠페인 | 캠페인 | 링크 | 캠페인 이름 | 문자열 |
| <span id="attribution::x75430560"></span>어트리뷰션 | campaign\_id | campaign\_id | 링크 | 특정 광고 캠페인 식별하는 고유 식별자<ul><li>[af\_c\_id와 동일](#attribution::75430560).</li><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="attribution::f8b1a2e"></span>어트리뷰션 | {"campaign_id__assist_[n]"} (n=1-3) |  | AF | 첫 번째 보조 어트리뷰션에서 오는 특정 광고 캠페인에 대한 고유 식별자<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="attribution::x274e74d5"></span>어트리뷰션 | campaign\_name | 캠페인 이름 | 링크 | 광고 캠페인 에 부여되는 설명적인 명칭<ul><li>[캠페인](#attribution::274e74d5)과 동일</li><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="attribution::64d77c36"></span>어트리뷰션 | {"campaign_name__assist_[n]"} (n=1-3) |  | AF | 첫 번째 보조 어트리뷰션에서 오는 광고 캠페인에 할당된 설명적 레이블<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="attribution::1ce994b8"></span>어트리뷰션 | 캠페인 유형 | 캠페인 유형 | AF | 유저를 데려오는 소스:<ul><li>앱스플라이어 캠페인의 목적을 분류한 내용</li><li>UA</li><li>오가닉</li><li>리타겟팅</li><li>알 수 없음 (1)</li></ul>(1) 특정 미디어 소스에 기인하지 않는 인앱 이벤트/세션 또는 개인정보 보호정책이나 GDPR 요청으로 인한 데이터 삭제 | 문자열 |
| <span id="attribution::d8d5132b"></span>어트리뷰션 | 캠페인 유형 | 캠페인 유형 |  | 캠페인이 신규 사용자 확보, 리타게팅 또는 다른 유형인지 지정합니다. | 문자열 |
| <span id="attribution::76ae00fe"></span>어트리뷰션 | campaign\_type\_\_assist\_3 |  | AF | 세 번째 보조 어트리뷰션에서 오는 캠페인의 의도에 대한 앱스플라이어 분류<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="device-info::5ba059c9"></span>디바이스 정보 | 캐리어 | 통신사 | SDK | 안드로이드에서 <Anchor target="_blank" href="https://developer.android.com/reference/android/telephony/TelephonyManager#getSimCarrierIdName()">getSimCarrierIdName()</Anchor>을 사용하여 제공한 통신사 이름 <Anchor target="_blank" href="https://android.googlesource.com/platform/packages/providers/TelephonyProvider/+/master/assets/carrier_list.textpb">캐리어 매핑</Anchor>도 참조하세요. | 문자열 |
| <span id="attribution::x1d1e08b5"></span>어트리뷰션 | channe | Channel | 링크 | 미디어 소스 채널<ul><li>[af\_channel](#attribution::1d1e08b5)과 동일.</li><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="attribution::760ee8ed"></span>어트리뷰션 | {"channel__assist_[n]"} (n=1-3) |  | AF | 첫 번째 보조 어트리뷰션에서 오는 미디어 소스 채널<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="device-location"></span>디바이스 위치 | 도시 | 도시 | AF | 기기가 위치한 도시. 일반적으로 도시 이름이 포함되지만, 때로는 지구나 자치구처럼 더 정확할 수 있습니다 | 문자열 |
| <span id="device-location::ctc00001"></span>기기 위치 | 도시 전환 | 변환 시 도시 | AF | 변환 시 장치 위치의 도시입니다.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="attribution::cit00001"></span>어트리뷰션 | click\_id\_type | 클릭 ID 유형 | 링크 | 네트워크 클릭-ID 유형입니다. 클릭 ID는 광고 클릭 URL에 추가된 고유한 영숫자 식별자로, 특정 광고, 캠페인 또는 키워드가 클릭을 생성했는지 추적하여 정확한 귀속을 가능하게 합니다.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="attribution::civ00001"></span>어트리뷰션 | click\_id\_value | 클릭 ID 값 | 링크 | 신호 전송 및 파트너 API를 통해 전체 캠페인 계층 구조를 해결하는 데 사용되는 랜딩 URL의 실제 클릭-ID 값입니다.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="device-location::11aea02f"></span>기기 위치 | 대륙 | 대륙 | AF | 대륙 이름의 두 글자 약어<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="attribution::f1c497c7"></span>어트리뷰션 | contributor[n]\_af\_prt(n=1-3) | Contributor[n] 파트너 | AF | 에이전시 또는 PMD - 항상 소문자로 변환 | 문자열 |
| <span id="attribution::860c6c0d"></span>어트리뷰션 | contributor[n]\_campaign(n=1-3) | 기여자[n] 캠페인 | AF | 기여자 캠페인 | 문자열 |
| 어트리뷰션 | 기여자[n]\_인게이지먼트\_유형(n=1-3) | 기여자[n] 인게이지먼트 유형 | AF | 가능한 값:<ul><li>사전 로드, 다운로드 클릭, 앱 클릭, 참여 클릭, 참여 보기, 보기, 청취, 클릭 유형 미지정, 노출 유형 미지정</li></ul> | 열거형 |
| <span id="attribution::daff87fa"></span>어트리뷰션 | contributor[n]\_match\_type(n=1-3) | Contributor[n] 검색 광고 유형 | AF | 가능한 값은 측정 유형과 동일합니다 | 문자열 |
| <span id="attribution::78fcf7ca"></span>어트리뷰션 | contributor[n]\_media\_source(n=1-3) | 기여자[n] 미디어 소스 | AF | 기여자 미디어 소스 | 문자열 |
| <span id="attribution::d7d270cf"></span>어트리뷰션 | contributor[n]\_touch\_time(n=1-3) | 기여자[n] 터치 시간 | AF | 기여자 터치 시간 | 날짜 시간 |
| <span id="attribution::43d06f64"></span>어트리뷰션 | contributor[n]\_touch\_type(n=1-3) | Contributor[n] 터치 유형 | AF | 가능한 값:<ul><li>클릭/노출</li></ul> | 열거형 |
| <span id="attribution::afacec40"></span>어트리뷰션 | contributor\_[n]\_engagement\_type | 기여자[n] 인게이지먼트 유형 | AF | 기여자 참여 유형 | 열거형 |
| <span id="attribution::942d31ab"></span>어트리뷰션 | conversion\_name | 전환 이름 | AF | 사용자 활동으로 인해 AppsFlyer 시스템에서 생성된 전환의 이름. 이 필드는 conversion\_type과 관련이 있습니다.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="attribution::40c20c30"></span>어트리뷰션 | 전환 유형 | 전환 유형 | AF | 전환 유형:<ul><li>사용자 행동으로 인해 AppsFlyer 시스템에 기록된 전환 유형, conversion\_name과 관련이 있습니다.</li><li>인스톨</li><li>재설치 (1)</li><li>리인게이지먼트</li><li>알 수 없음 (2)</li></ul>[(1) conversion\_type이 재설치이고, campaign\_type이 리타겟팅인 경우, 리타겟팅 전환 유형은 리어트리뷰션과 동일합니다](#attribution::40c20c30)<br /><br />(2) 어떤 미디어 소스에도 어트리뷰션되지 않은 인앱 이벤트/세션. | 문자열 |
| <span id="attribution::x8c179e3b"></span>어트리뷰션 | cost\_currency | 비용 화폐 단위 | 링크 | 비용의 통화 -- [cost\_value를](#attribution::x5647f309) 참조하세요<ul><li>[af\_cost\_currency와 동일](#attribution::8c179e3b)</li></ul> | 문자열 |
| <span id="attribution::x8733a05b"></span>어트리뷰션 | cost\_model | 비용 모델 | 링크 | 광고 가격 모델(예: CPC, CPM)<ul><li>[af\_cost\_model와 동일](#attribution::8733a05b)</li></ul> | 문자열 |
| <span id="attribution::x5647f309"></span>어트리뷰션 | cost\_value | 비용 값 | 링크 | 캠페인 관련 비용 - [cost\_model](#attribution::x8733a05b) 및 [cost\_currency](#attribution::x8c179e3b) 참조<ul><li>[af\_cost\_value와 동일](#attribution::5647f309)</li></ul> | 돈 |
| <span id="device-location::4a3ca194"></span>디바이스 위치 | country\_code | 국가 코드 | AF | <ul><li><Anchor target="_blank" href="https://www.iso.org/iso-3166-country-codes.html">ISO 3166 (alpha-2)</Anchor>를 사용하는 국가 코드입니다. 예시: 미국, 중국</li><li>영국의 코드는 GB가 아닌 UK로 구현되었습니다.</li></ul> | 열거형 |
| <span id="device-location::ccc00001"></span>기기 위치 | country\_code\_\_conversion | 변환 시 국가 코드 | AF | 변환 시 ISO 3166(알파-2)를 사용하는 국가 코드입니다.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="monetary"></span>금전적 | currency\_customer | 통화 고객 | 해당 없음 | 고객의 선호 통화 — 수익\_값\_고객 참조<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="monetary::rco00001"></span>금전적 | revenue\_currency\_original | 수익 통화 원본 | SDK | 이벤트에서 보고된 원래 수익의 통화입니다. 수익 가치 원본<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="attribution::36c62977"></span>어트리뷰션 | 커스텀 데이터 | 커스텀 데이터 | SDK | 광고주가 SDK나 S2S에서 설정한 데이터로, 대부분 타사 연동 및 오디언스에 사용됩니다. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata">안드로이드</Anchor> 및 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata">iOS</Anchor>를 참조하세요. | 문자열 \| 객체 |
| <span id="attribution::dc3d05d"></span>어트리뷰션 | custom\_dimension | 사용자정의 기준 | SDK | 앱스플라이어의 향후 사용을 위해 예약됨 | 문자열 |
| <span id="device-info::40b02bb7"></span>디바이스 정보 | customer\_user\_id | 고객 사용자 ID | SDK | 고객 사용자 ID(CUID)는 고유한 사용자 식별자입니다. 일반적으로 앱 소유자가 유저를 등록할 때 발생한 설정합니다. 앱 소유자는 CUID를 통해 다양한 디바이스에서 사용자 여정을 추적할 수 있습니다.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 \| 정수 |
| <span id="device-info::8be2aaee"></span>디바이스 정보 | customer\_user\_id | 고객 사용자 ID | SDK | 앱 소유자가 설정한 고유한 앱 유저 ID입니다. | 문자열 \| 정수 |
| <span id="device-info::ed856308"></span>디바이스 정보 | deeplink\_url | 딥링크 URL | SDK | 유저가 딥링크되는 앱 내부 액티비티의 경로입니다. 딥링킹과 디퍼드 딥링킹에 사용하세요.  <br />어트리뷰션 링크의 af\_dp 값이 포함되어 있습니다. | 문자열 |
| <span id="protect360::8cb25250"></span>Protect360 | detection\_date | 감지 날짜 | AF | 어트리뷰션 프로드가 탐지된 날짜입니다. | 문자열 |
| <span id="protect360::detstate"></span>Protect360 | protect\_detection\_state | 보호 감지 상태 | AF | <ul><li>Protect360이 참여, 전환 또는 최종 사용자 이벤트와 같은 이벤트에 할당한 사기 탐지 결과를 나타냅니다.</li><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="device-info::1fd8f0c4"></span>디바이스 정보 | device\_category | 기기 범주 | 보고된 유저 에이전트 | <ul><li>기기 종류 (예: 휴대폰, TV)</li><li>사용된 기기 유형: 태블릿, 휴대폰, 데스크톱, TV, 셋톱박스, 게임 콘솔, 미디어 플레이어, unknown\_device\_category. 'unknown\_device\_category' 가치 앱스플라이어 기기의 사용자 에이전트를 감지할 수 없을 때 생성됩니다. 앱스플라이어가 디바이스의 특성을 파악하려 시도했으나 알려진 범주로 분류하지 못했음을 나타냅니다.</li></ul> | 문자열 |
| <span id="device-info::dfd9504e"></span>디바이스 정보 | device\_download\_time | 기기 다운로드 시간 | SDK | 디바이스의 <Anchor target="_blank" href="https://developer.android.com/reference/android/content/pm/PackageInfo#firstInstallTime">안드로이드</Anchor>\/<Anchor target="_blank" href="https://developer.apple.com/documentation/foundation/nsfilecreationdate?language=occ">iOS</Anchor> 시계를 사용하고 UTC로 변환된 앱 다운로드 완료 시간입니다. 값은 항상 UTC 시간으로 표시됩니다.  <br />형식: yyyy-mm-dd hh:mm:ss.sss | 날짜 시간 |
| <span id="device-info::4a5568db"></span>디바이스 정보 | device\_id\_type | 기기 ID 유형 | SDK | CTV 플랫폼 ID 유형으로 CTV에 사용됩니다. 예를 들어, Roku의 RIDA입니다. | 열거형 |
| <span id="device-info::716c46bf"></span>디바이스 정보 | device\_model | 디바이스 모델 | SDK | 디바이스의 상업용 모델 이름입니다. 예: xiaomi::Redmi 또는 iPhone 7 | 문자열 |
| <span id="device-info::2be6278"></span>디바이스 정보 | device\_type | 디바이스 유형 | SDK | 디바이스의 상업용 모델 이름입니다.<ul><li>[2022년 2월 2일부터 이 필드는 더 이상 사용되지 않습니다.]</li><li>이 필드 대신 디바이스 모델을 사용하세요.</li><li>예시:<ul><li>디바이스 모델: xiaomi::Redmi Note 8</li><li>디바이스 유형: xiaomi-Redmi Note 8</li><li>디바이스 모델: iPhone 7</li><li>디바이스 유형: iPhone 7</li></ul></li></ul> | 문자열 |
| <span id="skan::d5ea0b47"></span>SKAN | did\_win |  | iOS | 캠페인이 인스톨에 <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes">기여했거나 어트리뷰션된</Anchor> 경우를 구별하는 데 사용됩니다.<ul><li>진실이라면, 캠페인은 인스톨을 가져온 것으로 간주됩니다.</li><li>false인 경우, 캠페인이 인스톨에 기여한 것으로 인식되지만 SKAN 대시보드나 보고서에는 포함되지 않습니다.</li><li>null인 경우, iOS가 <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes">기존 iOS 또는 SKAdNetwork 버전</Anchor> 때문에 필드를 채우지 않았습니다.</li></ul> | Boolean |
| <span id="device-location::e6a26925"></span>디바이스 위치 | dma | DMA | AF | 지정 시장 지역 또는 지리적 영역. <Anchor target="_blank" href="https://www.nielsen.com/us/en/solutions/nielsen-global-connect/">Nielsen 회사</Anchor>에 의해 정의됨. <Anchor target="_blank" href="/marketers/ko/docs/determine-user-location">유저 위치 확인</Anchor>. | 문자열 |
| <span id="device-location::dmac0001"></span>기기 위치 | dma\_\_conversion | 전환 시 DMA | AF | 전환 시 지정된 시장 영역.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="lifetime-value-events"></span>LTV 이벤트 | end\_user\_event\_type | 엔드 유저 이벤트 타입 | 해당 없음 | 최종 사용자 이벤트 유형을 식별합니다. 값에는 사용자 행동에 의해 트리거된 인앱 이벤트에 대한 IN\_APP와 앱 실행에 대한 SESSION이 포함됩니다.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 열거형 |
| <span id="attribution::8aab1f4d"></span>어트리뷰션 | engagement\_destination | 인게이지먼트 목적지 | AF | 광고가 연결되는 목적지의 플랫폼 그룹입니다. 예를 들어 웹 랜딩 페이지(WEBSITE) 또는 딥 링크 나 앱 스토어 통한 모바일 앱 (MOBILE) 등이 있습니다. 목적지를 알 수 없거나 지정하지 않은 경우 비워둘 수 있습니다. |  |
| <span id="attribution::engcat"></span>어트리뷰션 | engagement\_category | 참여 카테고리 | AF | 사용자가 광고와 상호작용한 방식을 설명하는 상위 수준의 그룹화입니다.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="attribution::isintegrated"></span>어트리뷰션 | is\_integrated | 통합되어 있습니다 | AF | 미디어 소스 통합되어 있습니까?<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | Boolean |
| <span id="attribution::8cea583a"></span>어트리뷰션 | engagement\_subtype | 참여 하위 유형 | AF | 사용자가 광고와 상호작용한 구체적인 방식, engagement\_type보다 더 세밀함<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="attribution::f7713604"></span>어트리뷰션 | {"engagement_subtype__assist_[n]"} (n=1-3) |  | AF | 사용자가 광고와 상호작용한 구체적인 방식, engagement\_type보다 더 세밀함<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="event"></span>어트리뷰션 | engagement\_type | 인게이지먼트 유형 | AF | <ul><li>사용자가 광고와 상호작용한 방식을 설명하는 상위 수준의 그룹화</li></ul>가능한 값:<ul><li>사전 로드, 다운로드 클릭, 앱 클릭, 참여 클릭, 참여 보기, 보기, 청취, 클릭 유형 미지정, 노출 유형 미지정</li></ul> | 문자열 |
| <span id="attribution::18bbe871"></span>어트리뷰션 | {"engagement_type__assist_[n]"} (n=1-3) |  | AF | 첫 번째 보조 어트리뷰션에서 오는 광고와 상호작용한 사용자의 고수준 그룹화 설명<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="event::13df6252"></span>이벤트 | event\_name | 이벤트 이름 | AF\/SDK | <ul><li>앱에서 전송한 어트리뷰션 이벤트 유형 또는 인앱 이벤트 이름 어트리뷰션 이벤트 유형의 예시: 인스톨 , 리인게이지먼트 등.</li><li>데이터 락커에서 리타겟팅 리포트의 문맥에서, 이벤트 이름은 다음과 같이 설정됩니다: 리타겟팅은 리인게이지먼트를 의미하고, 인스톨 은 리어트리뷰션 을 의미합니다. SKAN 리포트에서는 인앱 이벤트 이름이 앱스플라이어에서 구성된 대로 설정됩니다.</li><li>SKAN SRN 리포트에서는 이는 Meta Ads에서 구성된 인앱 이벤트 이름입니다.</li></ul> | 문자열 |
| <span id="event::2f7f426"></span>이벤트 | event\_revenue | 이벤트 수익 | SDK | <ul><li>이벤트 수익 통화를 사용한 수익의 가치.</li><li>$-1,000,000에서 $+1,000,000 범위를 벗어나는 금액은 로데이터 리포트에는 표시되지만, 집계 리포트에는 나타나지 않습니다.</li></ul> | 문자열 |
| <span id="skan::eb2c0d57"></span>SKAN | event\_revenue | 이벤트 수익 | AF | 공식: [특정 이벤트의 USD 값 합계] \/ [특정 날짜에 발생한 이벤트 수] | Float |
| <span id="event::78cfad98"></span>이벤트 | 이벤트 수익 통화 | 이벤트 수익 통화 | SDK | SDK에 보고된 이벤트 수익 통화 코드입니다. | 문자열 |
| <span id="event::f6999087"></span>이벤트 | event\_revenue\_usd* | 이벤트 수익 USD | AF | <ul><li>수익 금액입니다. 통화는 사용하는 보고 도구에 따라 달라집니다.</li><li>선호 또는 선택된 통화는 앱 설정에서 지정된 앱 전용 통화를 의미합니다.</li><li>데이터 락커: 항상 USD</li><li>내보내기 페이지: 선택된 통화</li><li>Pull API 선택 가능: USD 또는 &currency=preferred를 사용하여 선택.</li><li>Push API: 항상 USD와 선택한 통화 필드를 모두 포함합니다.</li></ul> | 문자열 \| 십진수 |
| <span id="event::6b26cc93"></span>이벤트 | event\_revenue\_xxx | 이벤트 수익 선택 통화 |  | <ul><li>수익 금액입니다. 통화는 사용하는 보고 도구에 따라 달라집니다.</li><li>선호 또는 선택된 통화는 앱 설정에서 지정된 앱 전용 통화를 의미합니다.</li><li>데이터 락커: 항상 USD</li><li>내보내기 페이지: 선택된 통화</li><li>Pull API 선택 가능: USD 또는 &currency=preferred를 사용하여 선택.</li><li>Push API: 항상 USD와 선택한 통화 필드를 모두 포함합니다.</li></ul> | 문자열 |
| <span id="attribution::eb80c5ea"></span>어트리뷰션 | event\_source | 이벤트 소스 | AF | 가능한 값은 참여 유형에 따라 다릅니다:<ul><li>클릭<ul><li>`s2s` (링크에서 redirect=false일 때)</li><li>그렇지 않으면 다음과 같이 하세요.</li></ul></li><li>노출 수<ul><li>`s2s` `af_ua` 또는 `af_ip`이 있을 때,</li><li>그렇지 않으면 다음과 같이 하세요.</li></ul></li><li>크로스 플랫폼 노출<ul><li>값 없음</li></ul></li></ul> | 열거형 |
| 이벤트 | event\_time | 이벤트 시점 | 포스트백 | 이벤트 시간은 가장 가까운 시간으로 내려서 반올림됨 | 날짜 시간 |
| <span id="event::b3d24688"></span>이벤트 | event\_time | 이벤트 시점 | SDK | <ul><li>이벤트 발생 시간</li><li>이벤트가 발생한 시간</li></ul> | 날짜 시간 |
| <span id="event::isfirstevent"></span>이벤트 | is\_first\_event |  | AF | <ul><li>사용자가 전환 후 처음으로 관련 인앱 이벤트를 수행했음을 나타냅니다. 이를 시간 경과에 따른 지표로 축적하면 특정 인앱 이벤트 수행한 고유 사용자 수를 측정할 수 있습니다.</li><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | Boolean |
| <span id="event::isattributed"></span>이벤트 | is\_attributed |  | AF | <ul><li>최종 사용자 이벤트가 어트리뷰션 기록에 연결되었는지 여부를 나타냄. 해당 이벤트 가 출처 기록(오가닉 또는 논오가닉)과 연결된 경우 참입니다. 귀속 기록을 사용할 수 없는 경우(예: GDPR로 인해 삭제되었거나, 만료되었거나, 기타 이유로 사용할 수 없는 경우)에는 false입니다. 이러한 이벤트는 오가닉 이벤트로 간주됩니다.</li><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | Boolean |
| <span id="event::devevttime"></span>이벤트 | device\_event\_time | 장치 이벤트 시간 | AF | 기기 측 이벤트 타임스탬프(`af_timestamp`)는 이벤트 생성되어 SDK 캐시에 추가된 시점을 기록합니다. 앱스플라이어 SDK는 유닉스 에포크 이후 경과된 시간을 밀리초 단위로 전송합니다. 안드로이드 에서는 `System.currentTimeMillis()`를 사용하여 생성되고, iOS 에서는 이에 상응하는 시스템 API 사용하여 생성됩니다. 해당 가치 서버 측에서 정규화되어 GMT 타임스탬프로 저장됩니다. 참고: 이는 클라이언트 측 시간이며 장치 시계가 잘못되었거나 의도적으로 변경되었을 수 있으므로 완전히 신뢰받는 없습니다.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 타임스탬프 |
| <span id="event::origevttime"></span>이벤트 | original\_event\_time | 원래 이벤트 시간 | AF | 차단 로직이 적용되기 전 이벤트 발생의 원래 시간입니다. 매우 늦은 시간에 발생하는 이벤트에 관련됨<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 타임스탬프 |
| <span id="event::556034db"></span>이벤트 | {"event_time__assist_[n]"} (n=1-3) |  | AF | 두 번째 어트리뷰션에서 오는 이벤트 발생 시간<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 타임스탬프 |
| <span id="event::55b76d8f"></span>이벤트 | event\_time\_\_attribution |  | AF | 어트리뷰션 (인게이지먼트) 이벤트에서 오는 이벤트 발생 시간<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 타임스탬프 |
| <span id="time"></span>시간 | event\_time\_\_conversion |  | 해당 없음 | 이벤트 타임스탬프(전환, 기여도, 세션 또는 인앱 이벤트). *참고*: [event\_time\_\_conversion](#time) 은 컨텍스트 별칭입니다.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 날짜 및 시간 |
| <span id="event::94d6064c"></span>이벤트 | event\_type | 이벤트 유형 | AF\/SDK | 어트리뷰션 이벤트 유형입니다. 어트리뷰션 이벤트 유형의 예시: 인스톨 , 리인게이지먼트 등. | 문자열 |
| <span id="pba-event"></span>PBA 이벤트 | event\_url | 이벤트 URL | 웹 SDK | 이벤트가 발생한 웹페이지의 URL (웹사이트 방문 시의 원래 URL과 동일) | 문자열 |
| <span id="skan::ed9e6b7a"></span>SKAN | event\_uuid |  | AF | 파트너가 중복된 포스트백을 식별할 수 있도록 하는 고유한 임의 식별자 | 문자열 |
| <span id="event::819be544"></span>이벤트 | event\_value | 이벤트 값 | SDK | 앱스플라이어 SDK에서 일반적으로 전송되는 이벤트 콘텐츠 JSON 형식으로 저장됩니다. 가치 JSON으로 파싱될 수 없는 경우, `__unparseable__` 키를 사용하여 해당 값을 감싸줍니다. 가치 이 3000자를 초과하면 3000자로 잘리고, JSON에 `is_truncated = true`가 추가됩니다. | 문자열 |
| <span id="event::evtorder"></span>이벤트 | event\_order | 이벤트 순서 | AF | 앱스플라이어 SDK 에서 사용하는 형식으로, 이벤트 생성된 시점에 기기에 기록된 이벤트 주문 카운터입니다. SDK 이름: iaecounter. 이 카운터는 인앱 이벤트 발생할 때마다 지속적으로 증가하며, 앱을 다시 설치하면 초기화됩니다. 해당 가치 SDK에서 문자열 형태로 전송됩니다. [앱스플라이어] 중요: 이 필드는 기기에서 생성되며 사기꾼에 의해 수정될 수 있습니다.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 롱 링크 |
| <span id="skan::b328108"></span>SKAN | event\_value | 이벤트 값 | S2S | <ul><li>기본값: null</li><li>커스텀 디코드나 <Anchor target="_blank" href="/marketers/ko/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor> 이벤트 발송을 구현하는 앱에서 설정한 문자열을 포함합니다.</li><li>광고주는 이를 자신의 시스템에서 사용합니다. 앱스플라이어는 이를 활용하지 않습니다.</li></ul> | 문자열(JSON) |
| <span id="skan::15ab0ab2"></span>SKAN | fidelity\_type | 충실도 유형 |  | <ul><li><Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_ad_attributions">어트리뷰션에 영향을 미치는 광고 표현 방법을 구분합니다</Anchor>. 다음과 같이 0과 1의 값으로 표시됩니다.<ul><li>시청 기반 광고 (0)</li><li>StoreKit 광고 (1)</li><li>SKAN 버전이 2.2 이전인 경우 필드 값을 무시하세요.</li></ul></li></ul> | 정수 |
| <span id="protect360::e2ef1cd4"></span>Protect360 | fraud\_reason | 프로드 사유 | AF | Protect360: 차단된 이유를 확인하세요. | 문자열 |
| <span id="protect360::f3bc9fc2"></span>Protect360 | fraud\_sub\_reason | 사기 하위 이유 | AF | Protect360: 차단된 하위 이유를 확인하세요. | 문자열 |
| <span id="device-info::e7bb2cb9"></span>디바이스 정보 | gdpr\_applies | gdpr\_applies | SDK | 사용자가 DMA 관할권에 해당하는지(true) 여부 또는 그렇지 않은지(false) 여부를 나타냅니다. | Boolean |
| <span id="attribution::169162d3"></span>어트리뷰션 | {"gp_broadcast_"} referrer | Google Play 브로드캐스트 리퍼러 | Google Play 스토어 | Google Play 브로드캐스트 리퍼러 | 문자열 |
| <span id="attribution::2ad3d84b"></span>어트리뷰션 | gp\_click\_time | Google Play 클릭 시간 | Google Play 필드 | 광고 클릭 후 Google Play에서 앱 페이지가 로드되는 시간입니다.<ul><li>시간 소스: Google API</li><li>안드로이드 SDK 버전 4.8.5부터 사용 가능</li><li>예시: install\_time을 gp\_click\_time과 비교하세요. 이는 사용자가 앱을 열 때까지 다운로드된 후 시간이 얼마나 소요되는지를 알려줍니다.</li></ul> | 타임스탬프 |
| <span id="attribution::d8bdd9fe"></span>어트리뷰션 | gp\_install\_begin | Google Play 인스톨 시작 시간 | Google Play 스토어 | 설치가 시작되는 시간<ul><li>시간 소스: Google API</li><li>안드로이드 SDK 버전 4.8.5부터 사용 가능</li></ul> | 타임스탬프 |
| <span id="attribution::67a30c47"></span>어트리뷰션 | gp\_referrer | Google Play 리퍼러 | Google Play 스토어 | 설치된 패키지의 URL입니다.<ul><li>안드로이드 SDK 버전 4.8.5부터 사용 가능</li></ul> | 문자열 |
| <span id="attribution::fe9e4cb0"></span>어트리뷰션 | hardware\_id\_type | 하드웨어 ID 유형 |  | 사용자가 재설정할 수 없는 장치에 대한 고유 식별자 유형입니다. | 문자열 |
| <span id="attribution::6bcef26e"></span>어트리뷰션 | hardware\_id\_value | 하드웨어 ID 값 |  | 사용자가 재설정할 수 없는 고유한 기기 수준 식별자(예: Android ID, IMEI). 해당 값은 hardware\_id\_type 필드에 지정된 유형에 해당합니다.<ul><li>android\_id 및 imei 와 동일합니다.</li><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="attribution::2191a08e"></span>어트리뷰션 | http\_referrer | HTTP 리퍼러 | AF | 고객 웹사이트 바로 앞에 위치하고 고객 웹사이트로 연결되는 웹페이지의 URL . 이는 방문 URL 에 특정 기여도 파라미터 (PID, UTM 또는 클릭 ID)가 없는 경우 기여도 대체 수단으로 사용됩니다. | 문자열 |
| <span id="device-info::e0372922"></span>디바이스 정보 | idfa | IDFA | SDK | iOS 디바이스에서 유저가 재설정할 수 있는 광고 ID입니다. IDFA가 사용 불가능한 경우 일반적으로 0으로 표시됩니다. | 문자 |
| <span id="device-info::8471310d"></span>디바이스 정보 | idfv | IDFV | SDK | iOS가 제공하는 공급업체 ID | 문자 |
| <span id="device-info::d4bf0a30"></span>디바이스 정보 | imei | IMEI | SDK | 영구 디바이스 ID | 문자 |
| <span id="ad-revenue::5406d519"></span>광고 수익 | 노출 | 노출 | 광고 수익 API | 유저가 광고를 본 횟수 | 문자열 |
| <span id="attribution::instappdl"></span>어트리뷰션 | 애플 앱 스토어 설치 | 애플 앱 스토어 설치 | AF | 앱이 설치된 앱 스토어 (예: 구글 구글 플레이, Samsung Galaxy Store, Xiaomi Marketplace, Huawei AppGallery). 이 필드는 안드로이드 에만 해당되며 앱 개발자가 입력합니다. 자세한 내용은 기술 자료(KB) - <Anchor target="_blank" href="/marketers/ko/docs/set-up-multi-store-android-attribution#single-dashboard-apk-preparation">멀티스토어 안드로이드 어트리뷰션 설정</Anchor> 에서 확인하세요.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="skan::913c6896"></span>SKAN | 설치 날짜 | 설치 날짜 | iOS | 앱스플라이어가 포스트백 도착 시간을 기준으로 추정한 날짜입니다. | 시간 문자열 |
| <span id="attribution::15b5bb86"></span>어트리뷰션 | 설치 시간 | 설치 시간 | 포스트백 | <ul><li>UA: 인스톨 후 앱 최초 오픈.</li><li>리타겟팅: 리인게이지먼트/리어트리뷰션 후 앱 최초 오픈</li></ul> | 날짜 시간 |
| <span id="skan::84c4214f"></span>SKAN | install\_type | 인스톨 유형 | iOS | New 인스톨 | 문자열 |
| <span id="skan::576274f5"></span>SKAN | 간격 | 간격 | AF | 유저 활동 측정 기간 간격. | 정수 |
| <span id="device-location::f8003308"></span>디바이스 위치 | ip | IP | AF | <Anchor target="_blank" href="/marketers/ko/docs/determine-user-location">IP 주소</Anchor>는 IPV4 또는 IPV6일 수 있습니다. 앱스플라이어는 이 주소를 사용해 유저 위치를 판단합니다. 필요에 따라 광고주는 보고서 및 포스트백에서 <Anchor target="_blank" href="/marketers/ko/docs/apply-ip-masking-to-user-data">IP 주소를 숨길 수</Anchor> 있습니다. | 문자열 |
| <span id="attribution::869dd814"></span>어트리뷰션 | ip\_address\_type | IP 주소 유형 |  | ip\_address\_value 필드에 제공된 IP 주소의 형식을 지정합니다(예: IPv4, IPv6).<ul><li>IP 마스킹이 활성화되면 유형은 "MD5\_HASH"가 됩니다. 중국 PIPL 솔루션의 경우 유형은 "SHA256\_PIPL\_HASH"가 됩니다.</li></ul> | 문자열 |
| <span id="device-location::xf8003308"></span>어트리뷰션 | ip\_address\_value | IP 주소 값 | AF | 장치의 IPv4 또는 IPv6 주소 가치 . MD5 또는 SHA256 해시로 계산할 수 있습니다.<ul><li>IP와 동일합니다.</li><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="device-info::e79f7a7b"></span>디바이스 정보 | is\_lat | 광고 추적 제한 | SDK | 광고 제한 추적 (LAT):<ul><li>iOS: iOS 14부터 Apple은 LAT를 더 이상 지원하지 않습니다. 앱 추적 투명성을 사용하여 유저의 개인 정보 보호 상태를 판단합니다. 이 사례에서 is\_lat을 무시하십시오.<br />iOS 14 이전에서는 true이면 IDFA를 사용할 수 없으며 0으로 설정됩니다.</li><li><Anchor target="_blank" href="https://developers.google.com/android/reference/com/google/android/gms/ads/identifier/AdvertisingIdClient.Info#public-constructor-summary">안드로이드</Anchor>: true인 경우, 유저는 관심 기반 광고를 거부합니다. GAID는 데이터를 수집하지 않으며 대신 0을 표시합니다.</li></ul> | 열거형 boolean |
| <span id="protect360::d8a27dfc"></span>Protect360 | 오가닉 여부 | 오가닉 여부 | AF | 인앱 이벤트가 오가닉 인스톨과 연관 되어 있는지 여부를 나타냅니다. | 문자열 |
| <span id="attribution::8aef34c8"></span>어트리뷰션 | is\_primary\_attribution | 기본 어트리뷰션 | AF | UA: True  <br />  <br />리타겟팅: 리인게이지먼트 기간 동안 원래 미디어 소스(리인게이지먼트 이전)와 리인게이지먼트 미디어 소스 둘 다에 어트리뷰션을 부여합니다. 인게이지먼트 창 내에 있는 이벤트. 원래 미디어 소스는 FALSE가 됩니다 (1차 어트리뷰션 아님). 리인게이지먼트 미디어 소스는 TRUE로 설정됩니다. <Anchor target="_blank" href="/marketers/ko/docs/resolve-retargeting-double-attribution">더 많은 정보</Anchor> | 열거형 boolean |
| <span id="event::isa00001"></span>이벤트 | is\_attributed | (is\_attributed) | AF | <ul><li>최종 사용자 이벤트가 어트리뷰션 기록에 연결되었는지 여부를 나타냄. 어트리뷰션 기록에 연결되었을 때 참 (유기적 또는 비유기적). 귀속 기록이 없을 때는 거짓입니다(예: GDPR로 삭제되었거나, 만료되었거나, 기타 이유로 사용할 수 없음); 이러한 이벤트는 유기적으로 간주됩니다.</li><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | Boolean |
| <span id="event::ife00001"></span>이벤트 | is\_first\_event | 첫 번째 이벤트입니다. | AF | <ul><li>사용자가 전환 후 처음으로 관련 인앱 이벤트를 수행했음을 나타냅니다. 이것을 지표로 축적하면 특정 인앱 이벤트를 수행한 고유 사용자 수를 측정할 수 있습니다.</li><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | Boolean |
| <span id="event::3177f2dd"></span>이벤트 | is\_receipt\_validated | 영수증 확인 상태 | AF | SDK에 구현된 경우 TRUE/FALSE/NULL, 그렇지 않으면 비어 있음 | 열거형 boolean |
| <span id="attribution::e433456e"></span>어트리뷰션 | 리타겟팅 여부 | 리타겟팅 여부 | 링크 | <ul><li><Anchor target="_blank" href="/marketers/ko/docs/protect360-raw-data-reports#차단된-이유">UA: false</Anchor></li><li><Anchor target="_blank" href="/marketers/ko/docs/protect360-raw-data-reports#차단된-이유">리타겟팅</Anchor>: 리타겟팅 전환 및 이벤트에 대해 True입니다.</li></ul> | 열거형 boolean |
<span id="d-Y"></span>| <span id="protect360::1e7f166b"></span>Protect360 | <span id="K-gt-FI"></span>is\_tagged |  | <span id="Ao"></span>앱스플라이어 | <span id="YPo"></span>탐지가 태그 되었는지 여부를 표시합니다. | 문자열 |
| <span id="attribution::1fb276b0"></span>어트리뷰션 | 키워드\_ID | 키워드 ID | 링크 | 애드 네트워크에 의해 반환된 키워드 ID입니다. af\_keyword의 ID입니다. | 문자열 |
| <span id="attribution::dc04765b"></span>어트리뷰션 | keyword\_match\_type | 키워드 측정 유형 | AF | <ul><li>키워드 측정 유형은 Google AdWords만 제공합니다.</li><li>2021년 2월 15일부터 Apple Search Ads와 관련하여 이 필드는 더 이상 채워지지 않습니다.</li></ul> | 문자열 |
| <span id="attribution::x9dd48973"></span>어트리뷰션 | 키워드 | 키워드 | 링크 | 유저가 온라인 검색 시 사용한 단어들입니다.<ul><li>[af\_keywords와](#attribution::9dd48973) 동일.</li><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="attribution::80f36786"></span>어트리뷰션 | keywords\_id |  | 링크 | 애드 네트워크에서 키워드의 식별자로 반환된 ID입니다.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="device-info::5d72ff40"></span>디바이스 정보 | 언어 | 언어 | SDK | 기기에서 보고하는 언어(로케일)와 기기 운영체제에서 설정한 언어(IETF BCP 47 언어 태그). 일반적으로 ll-DD의 형식을 따릅니다. 여기서 ll은 언어를, DD는 방언을 나타냅니다. 예를 들어 en-ZA는 남아프리카에서 사용되는 영어를 의미합니다. | 문자열 |
| <span id="attribution::cecc12c5"></span>어트리뷰션 | match\_type | 일치 유형 | AF | <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-attribution-model#어트리뷰션-메서드">어트리뷰션 메서드 유형</Anchor>. 가능한 값에는 다음이 포함됩니다:<ul><li>SRN</li><li>ID 매칭</li><li>확률적</li><li>딥링크</li><li>사전 설치</li><li>gp\_referrer(구글 플레이 참조자 문자열)</li><li>fb\_referrer, ig\_referrer (Meta 인스톨 리퍼러)</li><li><Anchor target="_blank" href="/marketers/ko/docs/set-up-multi-store-android-attribution#referrer-implementation-thirdparty-android-app-stores">써드 파티 안드로이드 앱 스토어 리퍼러</Anchor></li></ul> | 문자열 |
| <span id="skan::ae39e2c4"></span>SKAN | 최대 이벤트 카운터 | 최대 이벤트 수 | AF | 유저가 인앱 이벤트를 수행하는 횟수를 판단하려면 다음 공식을 사용하세요: [반올림((min\_event\_counter + max\_event\_counter) \/ 2)]. 주의! 가장 가까운 정수로 반올림해야 합니다.  <br />예시:  <br />A. min = 0, max = 1이면 평균은 0.5; 반올림하면 1이 됩니다.  <br />B. min = 5, max = 10이면 평균은 7.5; 반올림하면 8이 됩니다. | 정수 |
| <span id="skan::11f44c7e"></span>SKAN | max\_revenue | 최대 수익 | AF | 수익은 항상 [skad\_revenue](#skan::d831aefd) 필드에 제공됩니다. SKAN 4 또는 사용자정의 모드를 사용하는 경우 이벤트와 연관되고 skad\_revenue를 계산하는 데 사용되는 버킷 범위는 min\_revenue 및 max\_revenue로 설명됩니다. | 실수 |
| <span id="skan::61d427e9"></span>SKAN | 앱 설치 후 최대 시간 | 앱 설치 후 최대 시간 | AF | <ul><li>커스텀 전환에서: 앱스플라이어는 포스트백 도착 시간 - 36시간 - 평균(min\_time\_post\_install + max\_time\_post\_install)으로 인스톨 시간을 계산합니다. 그러나, CV=0이면 평균(min\_time\_post\_install + max\_time\_post\_install)은 0으로 간주됩니다.</li><li>디코드 전환에서: min\_time\_post\_install은 max\_time\_post\_install에 설정된 시간보다 1시간 적으며, 이는 귀사의 디코드 전환 매핑에서 설정한 hours\_from\_install과 동일합니다.</li></ul> | 정수 |
| <span id="skan::8c407dd5"></span>SKAN | measurement\_window | SKAN 측정 기간 | AF | 유저 활동 측정 기간 기본값은 24시간입니다. | 정수 |
| <span id="pba-attribution"></span>PBA 어트리뷰션 | media\_channel | 미디어 채널 | 웹 SDK | 웹사이트 방문에 어트리뷰션된 미디어 채널 | 문자열 |
| <span id="attribution::83b91456"></span>어트리뷰션 | media\_source | 미디어 소스 | 링크 | <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions#미디어-소스-제한">이벤트에 어트리뷰션되거나 제한된 미디어 소스</Anchor> | 문자열 |
| <span id="attribution::41d00e54"></span>어트리뷰션 | {"media_source__assist_[n]"} (n=1-3) |  | AF | 첫 번째 보조 어트리뷰션에서 오는 이벤트에 귀속된 미디어 소스<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="attribution::929e716c"></span>어트리뷰션 | media\_type | 매체 유형 | AF | 다음과 같이 링크를 전달하는 광고 배치:<ul><li>앱: 링크는 앱을 통해 사용할 수 있습니다.</li><li>웹: 링크는 모바일 웹사이트에서 제공됩니다.</li></ul> | 문자열 |
| <span id="ad-revenue::63a5ea9a"></span>광고 수익 | mediation\_network | 중재 네트워크 | 광고 수익 API | 광고 수익 미디에이션 네트워크가 이벤트를 앱스플라이어에 리포팅함 | 문자열 |
| <span id="skan::f2af60ce"></span>SKAN | min\_event\_counter | 최소 이벤트 수 | AF | 유저가 이벤트를 수행하는 횟수를 계산하는 데 사용됩니다. 유저가 인앱 이벤트를 수행하는 횟수를 판단하려면 다음 공식을 사용하세요: [반올림((min\_event\_counter + max\_event\_counter) \/ 2)]. 주의! 가장 가까운 정수로 반올림해야 합니다.  <br />예시:  <br />A. min = 0, max = 1이면 평균은 0.5; 반올림하면 1이 됩니다.  <br />B. min = 5, max = 10이면 평균은 7.5; 반올림하면 8이 됩니다. | 정수 |
| <span id="skan::224372e8"></span>SKAN | min\_revenue | 최소 수익 | AF | 수익은 항상 [skad\_revenue](#skan::d831aefd) 필드에 제공됩니다. SKAN 4 또는 사용자정의 모드를 사용하는 경우 이벤트와 연관되고 skad\_revenue를 계산하는 데 사용되는 버킷 범위는 min\_revenue 및 max\_revenue로 설명됩니다. | 실수 |
| <span id="skan::2c7e94a3"></span>SKAN | min\_time\_post\_install | 앱 설치 후 최소 시간 | AF | <ul><li>커스텀 전환에서: 앱스플라이어는 포스트백 도착 시간 - 36시간 - 평균(min\_time\_post\_install + max\_time\_post\_install)으로 인스톨 시간을 계산합니다. 그러나, CV=0이면 평균(min\_time\_post\_install + max\_time\_post\_install)은 0으로 간주됩니다.</li><li>디코드 전환에서: min\_time\_post\_install은 max\_time\_post\_install에 설정된 시간보다 1시간 적으며, 이는 귀사의 디코드 전환 매핑에서 설정한 hours\_from\_install과 동일합니다.</li></ul> | 정수 |
| <span id="ad-revenue::90d3bcb3"></span>광고 수익 | monetization\_network | 수익화 네트워크 | 광고 수익 API | 광고를 전달하는 광고 수익 네트워크 | 문자열 |
| <span id="attribution::7160d53a"></span>어트리뷰션 | network\_account\_id | 네트워크 계정 ID | 링크 | 애드 네트워크의 광고주 계정 ID | 문자열 \| 정수 |
| <span id="device-info::4afa15f"></span>디바이스 정보 | oaid | <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-knowledge-base-glossary#o">OAID</Anchor> | SDK | 일부 안드로이드 디바이스에서 유저가 재설정할 수 있는 ID로, 주로 GAID의 대안으로 사용됩니다. | 문자 |
| <span id="device-info::44749108"></span>디바이스 정보 | operator | 연산자 | SDK | <Anchor target="_blank" href="https://developer.android.com/reference/android/telephony/TelephonyManager#getNetworkOperatorName()">SIM MCCMNC로부터 파생된 모바일 운영자 이름입니다. 사용자가 안드로이드 getNetworkOperatorName()을 사용하여 네트워크에 등록된 경우 사용 가능합니다.</Anchor> | 문자열 |
| <span id="attribution::2e20e418"></span>어트리뷰션 | original\_url | 원래 URL | 링크 | <ul><li>UA: 사용된 클릭\/노출 URL 링크가 브랜드 링크인 경우: 필드는 브랜드 링크로 채워집니다.</li><li>리타겟팅: 다음 중 하나가 포함됨: 리타겟팅 링크, 딥링킹 데이터, SRN은 비어 있음.</li></ul> | 문자열(URL) |
| <span id="attribution::rlw00001"></span>어트리뷰션 | requested\_lookback\_window | 요청된 룩백 윈도우 | 링크 | 참여 URL에 지정된 원시 비구문 값입니다. 클릭 또는 노출이 전환에 귀속될 수 있는 기간을 결정할 때 사용됩니다.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="device-info::c9430692"></span>디바이스 정보 | os\_버전 | OS 버전 | SDK | 기기에 설치된 운영체제 버전 | 문자열 |
| <span id="device-info::ovc00001"></span>디바이스 정보 | os\_version\_\_conversion | 전환 시의 OS 버전 | AF | 전환 시 장치의 운영 체제 버전입니다.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="ad-revenue::88ea46f4"></span>광고 수익 | placement | 배치 | 광고 수익 API | 앱 내 광고가 표시되는 위치 | 문자열 |
| <span id="device-info::858b3f6a"></span>디바이스 정보 | 플랫폼 | 플랫폼 | SDK | 애플리케이션이 실행되는 운영 체제 또는 생태계 | 열거형 |
| <span id="app::1f608704"></span>앱 | platform\_group | 플랫폼 그룹 | AF | 여러 플랫폼 가치를 더 넓은 범주로 클러스터링하여 의미 있는 리포팅을 가능하게 하는 비즈니스 수준의 그룹입니다. 이것은 팀이 모바일 앱, 웹, CTV 앱 등과 같은 그룹으로 나누어 성과를 분석할 수 있게 하여 이벤트가 발생한 플랫폼의 카테고리를 반영합니다.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="device-info::3d0f4698"></span>디바이스 정보 | platform\_user\_id\_type |  | SDK | 플랫폼에서 생성된 사용자에 대한 고유 식별자 유형입니다.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="device-info::bbda346b"></span>디바이스 정보 | platform\_user\_id\_value |  | SDK | 플랫폼에서 생성된 사용자에 대한 고유 식별자 값입니다.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="device-location::9d71ef7e"></span>디바이스 위치 | postal\_code | 우편번호 | AF | 기기 위치의 우편번호(ZIP 코드) | 문자열 |
| <span id="product-line"></span>제품 라인 | product\_line\_id | 제품 라인 ID | 해당 없음 | AppsFlyer에서 제품 라인 엔티티에 대한 고유 식별자입니다. 통합된 크로스 플랫폼 측정을 위해 플랫폼 전반에 걸쳐 유사한 앱을 그룹화합니다.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="product-line::d5e0225b"></span>제품 라인 | product\_line\_name | 제품 라인 이름 | 해당 없음 | 플랫폼 전반에 걸쳐 유사한 앱을 그룹화하는 제품 라인 엔티의 이름.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="pba"></span>PBA | query\_params | 쿼리 파라미터 | 링크 | 리디렉션 URL의 쿼리 파라미터(? 이후)  <br />예: <Anchor target="_blank" href="https://www.brandpitt.com/signin?utm_source=Google&utm_term=shoes&utm_campaign=cool&c=summer&af_siteid=publisher&af_sub1=helloworld&af_keyword=shoes">https:\/\/www.brandpitt.com\/signin?utm\_source=Google</Anchor>  <br /><Anchor target="_blank" href="https://www.brandpitt.com/signin?utm_source=Google&utm_term=shoes&utm_campaign=cool&c=summer&af_siteid=publisher&af_sub1=helloworld&af_keyword=shoes">&utm\_term=신발</Anchor>  <br /><Anchor target="_blank" href="https://www.brandpitt.com/signin?utm_source=Google&utm_term=shoes&utm_campaign=cool&c=summer&af_siteid=publisher&af_sub1=helloworld&af_keyword=shoes">&utm\_campaign=멋진</Anchor>  <br /><Anchor target="_blank" href="https://www.brandpitt.com/signin?utm_source=Google&utm_term=shoes&utm_campaign=cool&c=summer&af_siteid=publisher&af_sub1=helloworld&af_keyword=shoes">&c=여름</Anchor>  <br /><Anchor target="_blank" href="https://www.brandpitt.com/signin?utm_source=Google&utm_term=shoes&utm_campaign=cool&c=summer&af_siteid=publisher&af_sub1=helloworld&af_keyword=shoes">&af\_siteid=퍼블리셔</Anchor>  <br /><Anchor target="_blank" href="https://www.brandpitt.com/signin?utm_source=Google&utm_term=shoes&utm_campaign=cool&c=summer&af_siteid=publisher&af_sub1=helloworld&af_keyword=shoes">&af\_sub1=helloworld</Anchor>  <br /><Anchor target="_blank" href="https://www.brandpitt.com/signin?utm_source=Google&utm_term=shoes&utm_campaign=cool&c=summer&af_siteid=publisher&af_sub1=helloworld&af_keyword=shoes">&af\_keyword=신발</Anchor><br /><br />URL에 쿼리 파라미터가 없으면 값은 null | 문자열 |
| <span id="device-info::195c85df"></span>디바이스 정보 | raw\_consent\_data | 원시 동의 데이터 | SDK | 광고주로부터 앱스플라이어로 전송된 모든 동의 로데이터 DMA 데이터를 JSON 객체로 반환합니다. | 문자열 \| 객체 |
| <span id="device-location::1720981c"></span>디바이스 위치 | 지역 | 지역 | AF | SDK가 보고한 디바이스 IP 주소 사용 SKAN의 경우, 국가 코드에 따라 결정됩니다. | 문자열 |
| <span id="protect360::d685b64e"></span>Protect360 | 거부된 이유 | 거부된 이유 | AF | Protect360: 지원 중단 계획됨. 현재 차단된 이유를 포함합니다. | 문자열 |
| <span id="protect360::440536f1"></span>Protect360 | rejected\_reason\_value | 거부된 이유 값 | AF | <ul><li>Protect360: 사후 어트리뷰션 하이재킹된 인스톨/인앱 이벤트의 유효한 기여자(미디어 소스)를 표시합니다. 기여자[1-3] 또는 오가닉으로 채워집니다.</li><li>데이터 락커에서는 validation\_reason\_value로 표시됩니다.</li></ul> | 문자열 |
| <span id="attribution::eecda2a2"></span>어트리뷰션 | 리타겟팅\_전환\_유형 | 리타겟팅 전환 유형 | AF | <ul><li>UA: 재인스톨</li><li>리타겟팅: 리인게이지먼트 및 리어트리뷰션</li></ul> | 열거형 |
| <span id="monetary::cf660373"></span>금전적 | revenue\_usd | revenue\_usd | 해당 없음 | 미국 달러로 변환된 이벤트 수익입니다.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 숫자 |
| <span id="monetary::1248941c"></span>금전적 | revenue\_value\_customer | 수익 가치 고객 | 해당 없음 | 이벤트 수익이 고객이 선호하는 통화로 변환됨 — currency\_customer 참조<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 숫자 |
| <span id="monetary::nrvcust"></span>금전적 | net\_revenue\_value\_customer | 수익 가치 고객 | AF | 이벤트 (예: 구매 또는 구독)의 수익 고객이 선호하는 통화로 환산한 금액입니다. 자세한 내용은 [currency\_customer를](#monetary) 참조하세요. 이는 총액(이벤트 수익 가치\_고객)에서 앱 스토어/ 플랫폼 수수료 및 해당 세금(부가가치세/상품서비스세, 판매세)을 뺀 금액과 같습니다.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | decimal |
| <span id="monetary::nrusd"></span>금전적 | net\_revenue\_usd | 순수익 USD | AF | 해당 이벤트 (예: 구매 또는 구독)의 수익 미국 달러로 환산한 금액입니다. 이는 총액( [이벤트 수익 USD](#event::f6999087) )에서 앱스토어/ 플랫폼 수수료 및 해당 세금(부가가치세/상품서비스세, 판매세)을 뺀 금액과 같습니다.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | decimal |
| <span id="monetary::rvo00001"></span>금전적 | revenue\_value\_original | 수익 가치 원본 | SDK | 이벤트에서 보고된 원래 수익 값으로, 원래 통화로 표시됩니다. 수익 통화 원본<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 숫자 |
| <span id="app::89931c41"></span>앱 | sdk\_version | SDK Version | SDK | 앱스플라이어 SDK 버전 | 문자열 |
| <span id="ad-revenue::ae2875be"></span>광고 수익 | 세그먼트 | Segment | 광고 수익 API | 광고 수익 세그먼트 이름 | 문자열 |
| <span id="attribution::xe9b53459"></span>어트리뷰션 | site\_id | 사이트 ID | 링크 | <ul><li>퍼블리셔 ID를 나타냅니다. 미디어 소스 다양한 게시자를 통해 광고를 실행하다 할 수 있으며, 각 게시자는 서로 다른 사이트 ID 로 식별됩니다.</li><li>[af\_siteid](#attribution::e9b53459)와 동일.</li><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="attribution::b09cbd8f"></span>어트리뷰션 | {"site_id__assist_[n]"} (n=1-3) |  | AF | <ul><li>첫 번째 어시스트 어트리뷰션에서 들어온 퍼블리셔 ID를 나타냅니다.</li><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="skan::70c7a914"></span>SKAN | skad\_ad\_network\_id | 애드 네트워크 ID | iOS | 포스트백이 전송된 애드 네트워크의 ID | 문자열 |
| <span id="skan::85b51b68"></span>SKAN | skad\_ambiguous\_event | 모호한 이벤트 | AF | true인 경우, 광고주가 대시보드에서 SKAN 설정을 변경한 후 첫 72시간 동안 iOS 포스트백 수신됨.  <br />SKAN에서 다양한 타이머 사용으로 인해, 앱스플라이어가 이벤트를 정확히 매핑할 수 없음. | Boolean |
| <span id="skan::89c88e44"></span>SKAN | skad\_app\_id | 앱 ID | iOS | 앱 ID | 문자열 |
| <span id="skan::95b0801d"></span>SKAN | skad\_attribution\_signature | 어트리뷰션 서명 | iOS | SKAN 포스트백에 애드 네트워크가 추가한 서명 | 문자열 |
| <span id="skan::9c8a097a"></span>SKAN | skad\_campaign\_id | 캠페인 ID | iOS | 광고를 게시하는 데 사용되는 캠페인 ID 범위 0-100 | 정수 \| 문자열 |
| <span id="skan::275a8850"></span>SKAN | skad\_coarse\_conversion\_value | 대략적인 전환 값 | iOS | <ul><li>값은 낮음, 중간, 높음 중 하나일 수 있습니다</li><li>SKAN 3의 경우 값은 null입니다.</li></ul> | 문자열 |
| <span id="skan::41d3b405"></span>SKAN | skad\_전환\_가치 | 전환 값 | iOS | iOS 에서 보고된 전환 값입니다. 범위 0-63.<ul><li>null인 경우, iOS에서 필드를 채우지 않았습니다.</li></ul> | 정수 |
| <span id="skan::accd42a5"></span>SKAN | skad\_did\_win | 이겼습니다 | iOS | 캠페인이 인스톨에 <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes">기여했거나 어트리뷰션된</Anchor> 경우를 구별하는 데 사용됩니다.<ul><li>진실이라면, 캠페인은 인스톨을 가져온 것으로 간주됩니다.</li><li>false인 경우, 캠페인이 인스톨에 기여한 것으로 인식되지만 SKAN 대시보드나 보고서에는 포함되지 않습니다.</li><li>null인 경우, iOS가 <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes">기존 iOS 또는 SKAdNetwork 버전</Anchor> 때문에 필드를 채우지 않았습니다.</li></ul> | Boolean |
| <span id="skan::3b4ad54f"></span>SKAN | skad 신뢰도 유형 | 충실도 유형 | iOS | <ul><li>어트리뷰션에 영향을 미치는 <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_ad_attributions">광고 표현 방법을 구분합니다</Anchor>. 다음과 같이 0과 1의 값으로 표시됩니다.<ul><li>시청 기반 광고 (0)</li><li>StoreKit 광고 (1)</li><li>SKAN 버전이 2.2 이전인 경우 필드 값을 무시하세요. 필드가 보고서에 추가되지만 반드시 채워지지는 않습니다.</li></ul></li></ul> | 정수 |
| <span id="skan::a36c9f3c"></span>SKAN | skad\_mode | SKAN 모드 | AF | iOS 포스트백을 디코딩하는 데 사용되는 전환 측정 모드입니다. 옵션:<ul><li>커스텀 디코딩</li><li>수익</li><li>이벤트</li><li>skan4</li><li>커스텀 인코딩</li><li>인게이지먼트</li></ul> | 문자열 |
| <span id="skan::546f8b91"></span>SKAN | skad\_포스트백\_서열\_인덱스 | 포스트백 시퀀스 인덱스 | iOS | <ul><li>값은 SKAN 기간, 즉 0, 1 또는 2를 나타냅니다.</li><li>SKAN 3의 경우 값은 0</li></ul> | 정수 |
| <span id="skan::8e4acd4"></span>SKAN | skad\_redownload | 재다운로드 | iOS | 사실이라면, 앱이 재다운로드되었습니다. | Boolean |
| <span id="skan::d831aefd"></span>SKAN | skad\_수익 | 수익 | iOS | 이벤트 수익 금액 (USD) | Float |
| <span id="skan::6d2ea88c"></span>SKAN | skad\_source\_app\_id | 소스 앱 ID | iOS | <ul><li>사이트 ID - 광고를 게시하는 앱입니다.</li><li>필드 인구는 개인정보 임계값에 따라 달라집니다.</li></ul> | 문자열 |
| <span id="skan::3dbc953"></span>SKAN | skad\_source\_domain | 소스 도메인 | iOS | <ul><li>값은 어트리뷰션이 가능한 웹 광고의 소스를 나타냅니다.</li><li>SKAN 3의 경우 값은 null입니다.</li></ul> | 문자열 |
| <span id="skan::19de61ba"></span>SKAN | skad\_source\_identifier | 소스 식별자 | iOS | <ul><li>값은 최대 4자리까지 가능합니다.</li><li>SKAN 3의 경우 값은 null입니다.</li></ul> | 문자열 |
| <span id="skan::b186321d"></span>SKAN | skad\_transaction\_id | SKAN 트랜잭션 ID | iOS | Apple에서 제공한 포스트백 ID | 문자열 |
| <span id="skan::3f316453"></span>SKAN | skad\_version | SKAN 버전 | iOS | SKAN 버전 | 문자열 |
| <span id="skan::3cd1002"></span>SKAN | source\_app\_id |  | AF | 사이트 ID. 광고를 게재하는 앱입니다. 이 필드는 skad\_source\_app\_id와 동일합니다. | 문자열 |
| <span id="device-location::6ae9b695"></span>디바이스 위치 | state | 주 | AF | 기기 위치의 주 또는 도 | 문자열 |
| <span id="device-location::stc00001"></span>기기 위치 | state\_\_conversion | 변환 시 상태 | AF | 변환 시 장치 위치의 주 또는 지방.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="iapsubscription::bd419a23"></span>IAP 구독 | store\_commission | 스토어 수수료 | True Revenue API | 구매한 제품에서 스토어가 얻는 수수료의 계산된 비율입니다.<ul><li>소수로 표시됩니다.</li><li>예시: 30</li></ul> |  |
| <span id="attribution::4c11e393"></span>어트리뷰션 | store\_product\_page | 스토어 제품 페이지 | AF | 사용자가 리디렉션된 안드로이드 또는 Apple 애플 앱 스토어(iOS 15+)의 커스텀 제품 페이지입니다. | 문자열 |
| <span id="attribution::b75cae23"></span>어트리뷰션 | store\_product\_page\_id |  | 링크 | 사용자가 리디렉션된 안드로이드 또는 애플 앱 스토어(iOS 15+) 내 맞춤 제품 페이지의 ID.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="device-info::2dc09e38"></span>디바이스 정보 | store\_reinstall | 스토어 리인스톨 | SDK | Apple 애플 앱 스토어는 Apple Search Ads에 의해 유치된 유저가 재설치인지 Apple 유저 ID로 판별합니다.<ul><li>New 유저: false</li><li>기존 유저에 의한 재설치: true</li></ul> | 부울 \| 문자열 |
| <span id="attribution::ef045054"></span>어트리뷰션 | {"sub_param_[n]"} (n=1-5) |  | 링크 | 어트리뷰션에 사용되는 추가 트래킹 파라미터<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="attribution::subp4"></span>어트리뷰션 | sub\_param\_4 |  | AF | 어트리뷰션에 사용되는 추가 트래킹 파라미터<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="attribution::subp5"></span>어트리뷰션 | sub\_param\_5 |  | AF | 어트리뷰션에 사용되는 추가 트래킹 파라미터<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="attribution::x9fdff16d"></span>어트리뷰션 | sub\_site\_id | (하위 사이트 ID): | 링크 | 하위 퍼블리셔 에게 할당된 식별자<ul><li>[af\_sub\_siteid](#attribution::9fdff16d)와 동일.</li><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="protect360::3b89b7c1"></span>Protect360 | tagged\_additional\_data |  | AF | 태그가 지정된 유형별 관련 데이터로 채워지는 동적 필드. 예를 들어, 태그가 "신규 출시"인 경우 관련 릴리즈 패키지의 패키지 번호를 반영합니다. | 문자열 |
| <span id="protect360::d46f7957"></span>Protect360 | tagged\_type |  | AF | 탐지를 표시한 태그 유형을 나타냅니다. 태그 유형 예시는 다음과 같습니다. 새 릴리즈, 앱 평점 등. | 문자열 |
| <span id="protect360::c64c1afb"></span>Protect360 | tagged\_validation\_reason\_value |  | AF | 탐지 모드가 구현된 경우, 실시간으로 어트리뷰션을 수신할 수 있는 적법한 기여자를 나타냅니다. | 문자열 |
| <span id="skan::c7910cfb"></span>SKAN | 타임스탬프 | 타임스탬프 | 애드 네트워크 | 앱스플라이어가 포스트백을 수신한 시간  <br />Google Ads 및 Meta Ads의 경우, 이는 앱스플라이어가 각각 Google과 Meta Ads API로부터 데이터를 받는 시간입니다. | 타임스탬프 |
| <span id="time::tzc00001"></span>시간 | timezone\_customer | 시간대 고객 | AF | 앱 소유자가 선호하는 시간대, IANA 형식 (예: Europe/Paris, America/Sao\_Paulo)으로 표시됩니다.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="time::tzcc0001"></span>시간 | timezone\_customer\_\_conversion | 변환 시 (고객) 시간대 | AF | 변환 시 앱 소유자가 선호하는 IANA 형식의 시간대(예: Europe/Paris, America/Sao\_Paulo).<ul><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="attribution::a543f19e"></span>어트리뷰션 | total\_candidates | 총 후보 | AF | 전환 시점에 지정된 기기에 대해 평가된 총 인게이지먼트(클릭, 노출 및 기타 인게이지먼트 유형) 수를 나타냅니다. | 문자열 |
| <span id="xapp"></span>어트리뷰션 | unified\_app\_id | 통합 앱 ID | SDK | 앱스플라이어의 고유한 앱 식별자. raw [app\_id는](#app) 플랫폼 내에서 앱을 식별하는 식별자입니다. [unified\_app\_id는](#xapp) 플랫폼 간 충돌을 방지하기 위해 플랫폼 전체에서 앱 ID를 표준화합니다. 구성 규칙: - 모바일 플랫폼(안드로이드, iOS)의 경우, [unified\_app\_id](#xapp) 는 원본 [app\_id](#app) 와 같습니다. - 기타 모든 플랫폼(웹, CTV 등)의 경우, [unified\_app\_id](#xapp) 는 원본 [app\_id](#app) 앞에 플랫폼 과 하이픈(-)을 붙인 형태입니다. 예: "&lt; 플랫폼>-&lt; [앱\_id](#app) >".<ul><li>[app\_id와](#app) 동일.</li><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="device-info::a74b0cd"></span>디바이스 정보 | user\_agent | 사용자 에이전트 | 링크 | 요청을 보내는 브라우저, 운영 체제, 장치 유형 및 애플리케이션 버전을 식별하는 문자열입니다. | 문자열 |
| <span id="attribution::32f28e6f"></span>어트리뷰션 | vendor\_id\_type | 벤더 ID 유형 |  | 기기+앱 공급업체를 위한 고유 식별자 유형입니다. | 문자열 |
| <span id="device-info::x8471310d"></span>어트리뷰션 | vendor\_id\_value | 벤더 ID 가치 | SDK | 기기+앱 공급업체에 대한 고유 식별자 가치 .<ul><li>[idfv와](#device-info::8471310d) 동일</li><li><Anchor target="_blank" href="/marketers/ko/docs/about-data-locker-advanced-reports">고급 보고서</Anchor>에서만 사용 가능합니다.</li></ul> | 문자열 |
| <span id="pba-event::c1d28dd1"></span>PBA 이벤트 | web\_event\_type | Web Event Type | 웹 SDK | 웹 이벤트 유형 ( 방문, 이벤트 등) | 문자열 |
| <span id="device-info::fdb1b524"></span>디바이스 정보 | wifi | WIFI | SDK | TRUE 또는 FALSE로 설정 | 열거형 boolean |

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 h_01JYP22DSGHFMRW5JXDWH6YZZQ=%EA%B0%9C%EC%9A%94 01H8BNKT33XGHES55AZXCY1H03=%ED%8C%81 d%3FY%3D=d-Y K%26gt%3BFI=K-gt-FI Ao%3B%7C=Ao YPo%5B=YPo" />
