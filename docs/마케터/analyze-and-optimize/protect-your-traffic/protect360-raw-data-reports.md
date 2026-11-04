---
title: Protect360 로데이터 리포트
metadata:
  keywords:
    - Advertisers
    - Protect360
    - protect
    - protect 360
    - '360'
    - Raw Data
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2020-11-09T13:03:45Z'
  edited_at: '2026-10-14T10:25:51Z'
  id: 360015179337
  locale: ko
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/ko/articles/360015179337
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **한눈에 보기:** 로데이터 리포트는 Protect360 엔진이 차단한 인스톨 및 인앱 이벤트와 수동으로 추가한 유효성 검증 규칙을 설명합니다.

<div id="about-protect360-raw-data-reports" />

## Protect360 로데이터 리포트에 대하여

로데이터 리포트:

* 다음 데이터 표시:
  * Protect360 엔진이 프로드로 식별한 클릭, 인스톨 및 인앱 이벤트
  * 유효성 검증 규칙을 통해 식별된 인스톨 및 인앱 이벤트
* 각 클릭, 인스톨 또는 인앱 이벤트에 대한 차단 사유를 포함합니다.
* 광고주가 애드 네트워크 계정을 조정하거나 최적화하며, 사후 어트리뷰션 프로드에 대한 어트리뷰션 대시보드를 조정하는 데 사용됩니다.
* 앱스플라이어 데이터 집약형 고급 프라이버시(AAP)가 적용되는 경우, 일부 필드가 제한되거나 사용할 수 없습니다.
* 리포트 유형과 다운로드, API, 데이터 락커(S3 버킷)에 따른 가용성에 대해 다음 섹션에서 설명합니다.
* 역사적인 로데이터 리포트 리텐션은 리포팅 도구와 로데이터 출처에 따라 최대 90일까지 보관됩니다.

<div id="note" />

> 📘 **참고**
>
> 프라이버시와 관련된 로데이터 제한으로 인해 로데이터 리포트는 비어 있는 값이 포함된 필드를 보여줄 수 있습니다. 그 예가 기여자 필드입니다.

<div id="report-types" />

<Accordion title="리포트 유형">

<div id="protect360-raw-data-report-types" />

#### Protect360 로데이터 리포트 유형

| 리포트 | 설명 |
| --- | --- |
| <span id="installs"></span>인스톨 | 리포트에는 다음이 포함됩니다.<ul><li>**가짜 인스톨**: Protect360 엔진이 프로드로 식별한 인스톨입니다. 이것은 Protect360 대시보드 및 로데이터를 제외한 모든 앱스플라이어 대시보드 또는 로데이터에는 표시되지 않습니다.</li><li>**하이재킹된 인스톨**: 실제 유저 인스톨이지만, 어트리뷰션이 도용된 경우이고, Protect360이 [어트리뷰션을 수정합니다](/docs/protect360-raw-data-reports#하이재킹된-인스톨-어트리뷰션-수정).</li><li>**유효성 검증 규칙**: 인스톨이나 어트리뷰션이 차단된 사례(Protect360이 [어트리뷰션을 수정합니다](/docs/protect360-raw-data-reports#하이재킹된-인스톨-어트리뷰션-수정)).</li></ul> |
| <span id="postattribution-installs"></span>사후 어트리뷰션 인스톨 | 리포트에는 미디어 소스에 귀속된 installs로 추정되지만 나중에 프로드로 판명된 것이 포함됩니다. [Protect360](/docs/protect360-raw-data-reports#하이재킹된-인스톨-어트리뷰션-수정)[이 어트리뷰션을 수정합니다.](/docs/protect360-raw-data-reports#하이재킹된-인스톨-어트리뷰션-수정) |
| <span id="blocked-inapp-events"></span>차단된 인앱 이벤트 | 리포트는 다음의 인앱 이벤트를 포함합니다.<ul><li>**가짜 인스톨**: 인앱 이벤트가 차단되었습니다.</li><li>**인앱 이벤트**: 원래 인스톨과 관계없이 사기로 식별되었습니다.</li><li>**유효성 검증 규칙**:<ul><li>인스톨이나 어트리뷰션을 차단한 규칙에서 발생한 IAE입니다.</li><li>인앱 이벤트를 차단한 규칙으로 인해 발생한 IAE입니다.</li></ul></li></ul> |
| <span id="postattribution-inapp-events"></span>사후 어트리뷰션 인앱 이벤트 | 리포트에는 인앱 이벤트가 포함됩니다.<ul><li>사후 어트리뷰션으로 식별되었습니다.</li><li>미디어 소스에 어트리뷰션된 인스톨이었지만 나중에 사기로 판명된 경우</li></ul> |
| <span id="clicks"></span>클릭 | 리포트에는 차단된 클릭과 차단 사유가 포함됩니다. |
| <span id="blocked-install-postbacks"></span>차단된 인스톨 포스트백 | 리포트에는 차단된 인스톨을 가져오는 미디어 소스로 전송된 거부 포스트백의 복사본이 포함됩니다. |

</Accordion>

<div id="postattribution-reports" />

<Accordion title="사후 어트리뷰션 리포트">

* 사후 어트리뷰션 로데이터 프로드 리포트는 차단된 프로드 리포트와 동일한 구조를 갖습니다.
* 현재 월(인스톨 일 기준) 사후 어트리뷰션 리포트는 다음 달 7일(감지일)까지 계속 업데이트됩니다.
* 사후 어트리뷰션 로데이터 리포트는 광고주에게만 제공됩니다. 기관에서는 <Anchor target="_blank" href="/partners/ko/docs/protect360-for-integrated-partners">권한</Anchor>을 활성화해 에 액세스해야 합니다.
* 리포트에는 Protect360에서 식별한 사후 어트리뷰션 프로드 이벤트가 포함되며, 모든 미디어 소스가 단일 리포트로 제공됩니다. **참고**: 선택한 날짜 범위에 대해 사후 어트리뷰션 프로드 이벤트가 식별되지 않으면, 리포트는 비어 있습니다.
* 사후 어트리뷰션 로데이터 프로드 리포트는 다음과 같이 제공됩니다:

  * 대시보드 사용자 인터페이스: 한 달 동안 하나의 미디어 소스로 제한됩니다.
  * Pull API: 모든 미디어 소스를 포함합니다. (제한 사항: 앱 소유자에게만 제공됨.)

<div id="using-post-attribution-reports" />

#### **사후 어트리뷰션 리포트 사용하기**

* 원하는 인스톨\/IAE와 감지 날짜 범위 조합을 선택하세요.
* Protect360은 인스톨이 있는 달 동안 그리고 다음 달 7일까지 사후 어트리뷰션 감지를 수행한다는 점을 고려하세요. 예를 들어 11월에 인스톨이 이루어진 경우 Protect360은 12월 7일까지 프로드를 확인합니다.
* 이 Pull API를 사용하는 가장 좋은 방법은 다음과 같습니다:
  * 매일 리포트를 받는다고 가정해 봅시다.
  * 인스톨 날짜 범위를 현재 날짜에서 60일 이전으로 설정합니다.
  * 감지 시작/종료 범위를 현재 날짜의 전날로 설정합니다.  
    이는 어제 감지된 사후 어트리뷰션 프로드 목록을 받게 된다는 뜻입니다. 며칠 동안 리포트를 가져오지 못했다면 감지 날짜 범위를 조정하고 리포트를 가져오세요.

<div id="example" />

> 📄 **예시**
>
> **예시 A**: 12월 동안(인스톨 날짜) example\_media에 15개의 인스톨이 어트리뷰션되었습니다. 1월 3일(탐지 날짜)에 Protect360이 example\_media를 사기꾼으로 식별했습니다. 결과적으로, example\_media에 어트리뷰션된 15개의 인스톨은 앱 소유자가 추가 조치를 취할 수 있도록 사후 어트리뷰션 프로드 리포트에 사기로 나열됩니다.
>
> **예시 B**: 12월 동안 example\_media에 15개의 인스톨이 어트리뷰션되었습니다. 1월 9일에 Protect360이 example\_media를 사기꾼으로 식별했습니다. 이 경우, 사기꾼이 1월 7일 월 마감 후에 식별되었기 때문에 Protect360은 아무런 조치를 취하지 않습니다.

</Accordion>

<div id="raw-data-availability-by-tool-type" />

<Accordion title="도구 유형별 로데이터 가용성">

<div id="protect360-raw-data-availability-by-tool-type" />

#### 도구 유형별 Protect360 로데이터 가용성

<table><thead><tr><th>리포트</th><th>데이터 최신성</th><th>Pull API</th><th>데이터 내보내기 페이지</th><th>데이터 락커</th></tr></thead><tbody><tr><td>인스톨</td><td>실시간</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>차단된 인앱 이벤트</td><td>실시간</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>클릭</td><td>실시간</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>차단된 인스톨 포스트백</td><td>실시간</td><td>-</td><td><span>✓</span></td><td>-</td></tr><tr><td>사후 어트리뷰션 인스톨</td><td><p>매일 10:00 UTC</p></td><td><p><span>✓</span></p></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>사후 어트리뷰션 인앱 이벤트</td><td><p>매일 10:00 UTC</p></td><td><span>✓</span></td><td><span>✓</span></td><td>-</td></tr></tbody><tfoot><tr><td colspan="5"><p>\* 데이터 락커를 통한 리포트의 제한 사항:</p><ul><li>에이전시 투명성 지원되지 않음. 즉, 에이전시 주도 트래픽에는 인스톨을 보낸 미디어 소스의 이름을 포함하지 않습니다. </li><li>이 리포트는 다른 데이터 락커 리포트와 대비하여 고유한 필드 집합을 가지고 있습니다. 이 목록은 변경할 수 없습니다. </li><li>리타겟팅 데이터는 인스톨 리포트에서는 사용할 수 없고, 사후 어트리뷰션 인스톨 리포트에서는만 사용할 수 있습니다. </li></ul></td></tr></tfoot></table>

</Accordion>

<div id="getting-raw-data-reports" />

## 로데이터 리포트 받기

로데이터 리포트는 다운로드, Pull API 및 데이터 락커(S3 버킷)를 통해 이용할 수 있습니다. 또한 <Anchor target="_blank" href="/partners/ko/docs/protect360-for-integrated-partners">파트너에게 리포트에 대한 액세스를 제공</Anchor>할 수 있습니다.

<div id="download" />

<Accordion title="다운로드">

**다운로드 방법:**

1. Protect360 대시보드에서 **로데이터 리포트** > **차단** 또는 **사후 어트리뷰션**으로 이동하세요.
   * 사후 어트리뷰션 리포트의 경우 미디어 소스와 월을 선택하세요.
2. **Protect360 및 유효성 검증 규칙** 리포트를 다운로드하려면 선택하세요.

**또는**

1. 앱스플라이어 대시보드에서 **데이터 내보내기**로 이동하세요.
2. **Protect360 및 유효성 검증 규칙** 리포트를 다운로드하려면 선택하세요.

**참고**: 데이터 내보내기 페이지에서 다운로드한 리포트에는 모든 미디어 소스가 포함되어 있습니다.

</Accordion>

<div id="pull-api" />

<Accordion title="Pull API">

**Pull API로 사용 가능한 로데이터 리포트를 다운로드하려면:**

**시작하기 전:**

Pull API 토큰이 필요합니다. 어드민 <Anchor target="_blank" href="/marketers/ko/docs/managing-appsflyer-tokens">유저</Anchor>로부터 토큰을 받으세요.

1. **리포트 > API 액세스로 이동하세요.** <Anchor target="_blank" href="/marketers/ko/docs/pull-api-raw-data">Pull API</Anchor> 페이지가 열립니다.
2. Protect360 프로드 리포트 섹션에서 필요한 Pull API 호출을 선택하세요.
3. 필요에 따라 파라미터를 입력하세요. 다음 표에 파라미터가 나열됩니다.
4. 리포트를 가져오세요.

<div id="pull-api-raw-data-report-parameters" />

#### Pull API 로데이터 리포트 파라미터

| 파라미터 | 설명 | 형식 | 필수 |
| --- | --- | --- | --- |
| app\_id | 앱스플라이어에 표시되는 앱 ID | 문자열 | 예 |
| api\_token | 대시보드에서 키를 찾아보세요. **리포트** > **API 액세스로 이동하세요.** 오직 어드민 유저만 API 토큰을 가져올 수 있습니다. | 문자열 | 예 |
| 시작 | 날짜 범위 시작:<ul><li>인스톨의 경우에는 인스톨 날짜입니다.</li><li>인앱 이벤트의 경우에는 이벤트 날짜입니다.</li></ul> | YYYY-MM-DD | 예 |
| 끝 | 날짜 범위 끝:<ul><li>인스톨의 경우에는 인스톨 날짜입니다.</li><li>인앱 이벤트의 경우에는 이벤트 날짜입니다.</li></ul> | YYYY-MM-DD | 예 |
| event\_name | [사후 어트리뷰션 인앱 이벤트 프로드에 대한 선택사항]<br /><br />인앱 이벤트로 이벤트를 필터하세요. 특정 이벤트에 리포트를 제한합니다.  하나 이상의 이벤트를 포함할 수 있습니다.<br /><br />사용 예: `&event_name=af_purchase,af_login` | 문자열 | 아니오 |
| 추가 필드=rejected\_reason\_value | [사후 어트리뷰션 인앱 이벤트 프로드에 대한 선택사항]<br /><br />**<Anchor target="_blank" href="/marketers/ko/docs/raw-data-field-dictionary#protect360">rejected\_reason\_value</Anchor>** 는 하이재킹된 인스톨/인앱 이벤트에 대한 <Anchor target="_blank" href="/marketers/ko/docs/raw-data-field-dictionary#protect360">유효한 기여 미디어 소스를 보여줍니다. 기여자[**[1-3]**](/docs/raw-data-field-dictionary#attribution::2a6fd501) 또는 **오가닉**으로 채워집니다.</Anchor> | 문자열 | 아니오 |
| 시작 감지 | [사후 어트리뷰션 인스톨에 대한 선택사항]<br /><br />프로드 감지 날짜 범위의 시작입니다. (기본값은 시작입니다.) (사후 어트리뷰션 인스톨 프로드에 사용됨.) | YYYY-MM-DD | 아니오 |
| 감지 종료 | [사후 어트리뷰션 인스톨에 대한 선택사항]<br /><br />프로드 감지 날짜 범위의 끝입니다. (기본값은 끝입니다.) | YYYY-MM-DD | 아니오 |

</Accordion>

<div id="data-locker" />

<Accordion title="데이터 락커">

데이터 락커가 로데이터를 AWS S3 버킷에 기록합니다.

<Anchor target="_blank" href="/marketers/ko/docs/data-locker-advertiser-reports#protect360">사용 가능한 Protect360 리포트 목록을 확인하세요</Anchor>.

<Anchor target="_blank" href="/marketers/ko/docs/data-locker-for-marketers#aws-cli">데이터 락커 설정 지침을 확인하세요</Anchor>.

</Accordion>

<div id="protect360-report-structure" />

## Protect360 리포트 구조

Protect360 리포트는 유저 유입 리포트 필드와 동일한 일반 구조를 갖고 있습니다.

일반적인 <Anchor target="_blank" href="/marketers/ko/docs/raw-data-field-dictionary">로데이터 리포트 필드</Anchor> 외에도 Protect360 리포트에는 리타겟팅 및 차단 이유 필드도 포함되어 있습니다. 예를 들면 다음과 같습니다:

<div id="blocked-reasons" />

### 차단된 이유

<div id="click-level-blocked-reasons" />

<Accordion title="클릭 수준 차단 이유">

클릭 수준에서는 클릭이 차단되고 어트리뷰션 프로세스에서 무시됩니다.

| 차단된 이유 | 설명 |
| --- | --- |
| ip\_blacklist (아이피 블랙리스트) | 동적으로 생성된 목록(<Anchor target="_blank" href="/marketers/ko/docs/protect360-anti-fraud-guide#ip-denylists">세부사항</Anchor>)에 기반함 |
| 유효하지 않은 지문 | S2S 클릭만: 소스에서 잘못된 파라미터 전송(확률적 매칭의 경우) |
| 클릭 제한 | 해당 애드 네트워크에서 매우 높은 비율의 클릭 프로드가 감지되었습니다. <Anchor target="_blank" href="/partners/ko/docs/protect360-for-integrated-partners#노출-및-클릭-제한">더 보기</Anchor> |
| 클릭 서명 | 클릭에 대한 서명이 검증되지 않았습니다. <Anchor target="_blank" href="/partners/ko/docs/click-signing-for-ad-networks">더 보기</Anchor> |
| 입력 검증 | 잘못된 미디어 소스 이름 |

</Accordion>

<div id="install-level-blocked-reasons" />

<Accordion title="인스톨 수준 차단 이유">

인스톨 수준에서는 인스톨 시점에 충분한 정보를 식별하여 다음 중 하나를 판단합니다:

* 가짜 인스톨, 즉 앱을 인스톨하는 유저가 실제 사람이 아님을 뜻합니다. 이 경우, 어트리뷰션은 완전히 차단됩니다.
* 어트리뷰션 하이재킹은 실제 사용자가 참여했지만, 인게이지먼트가 위조된 경우입니다. 이 경우, 사기적인 인게이지먼트는 차단되고 어트리뷰션은 첫 번째 유효 기여 애드 네트워크에 다시 할당됩니다.

다음 표에는 인스톨 수준에서 차단된 이유가 나열되어 있습니다:

<div id="install-level-fake-install-block-sub-reasons" />

#### 인스톨 수준: 가짜 인스톨 차단 하위 이유

| 차단된 이유 | 차단된 하위 이유 | 설명 |
| --- | --- | --- |
| 봇 | 가짜 장치 매개변수 | 앱 설치 과정에서 디바이스 관련 파라미터에서 비인간적 동작이 감지됨 |
| 봇 | 가짜 설치 파라미터 | 앱 설치 과정에서 설치 관련 파라미터에서 비인간적 동작이 감지됨 |
| 봇 | 베이지안 네트워크 | 베이지안 네트워크를 통한 사기 패턴 식별 |
| 인스톨 스토어 검증 | - | Apple 애플 앱 스토어 <Anchor target="_blank" href="/marketers/ko/docs/implement-apple-app-store-itunes-install-validation">인스톨 영수증 검증</Anchor> 실패 |
| 검증 봇 | 잘못된 디바이스 파라미터 | 특정 디바이스 필드 기대의 불일치 - 고객이 정의함 |
| 검증 봇 | 유효성 검증 규칙 | 수동으로 정의된 유효성 검증 규칙에 따라 차단된 인스톨 규칙 |
| 봇 | ai\_layer | AI 모델이 방대한 양의 데이터 포인트를 분석하여 사기 디바이스 및 인스톨 활동을 식별하는 탐지 능력을 향상시킵니다. |

<div id="install-level-attribution-hijacking-block-sub-reasons" />

#### 인스톨 수준: 어트리뷰션 하이재킹 차단 하위 이유

| 차단된 이유 | 차단된 하위 이유 | 설명 |
| --- | --- | --- |
| ctit\_anomalies | 짧은\_ctit | CTIT가 짧아 인스톨 차단됨: Protect360 정의 |
| 인스톨 하이재킹 | 리퍼러 하이재킹 | GooglePlay API와 앱스플라이어 SDK 파라미터에 기반한 하이재킹 시도 차단 |
| 인스톨 하이재킹 | 통합 일시 차단됨 | 파트너(pid)의 프로드 비율이 매우 높고 모든 트래픽에서 심각한 이상 현상이 발생하여 인스톨 차단됨 |
| 유효성 검증 하이재킹 | 짧은\_ctit | CTIT가 짧아 인스톨 차단됨: 고객 정의 |
| 유효성 검증 하이재킹 | 빈\_사이트\_ID | 사이트 ID가 비어 있어 인스톨 차단됨. 규칙 구현은 단계적으로 진행됩니다 |
| 유효성 검증 하이재킹 | 유효성 검증 규칙 | 수동으로 정의된 유효성 검증 규칙에 기반하여 차단된 어트리뷰션 규칙 |

</Accordion>

<div id="cluster-level-blocked-reasons" />

<Accordion title="클러스터 수준 차단 이유">

프로드 패턴이 감지되면, 해당 프로드 소스는 거부 목록에 추가됩니다. 이 거부된 소스에서의 인스톨은 다음 중 하나의 이유로 차단됩니다:

* 가짜 인스톨, 즉 앱을 인스톨하는 유저가 실제 사람이 아님을 뜻합니다. 이 경우, 어트리뷰션은 완전히 차단됩니다.
* 어트리뷰션 하이재킹은 실제 사용자가 참여했지만, 인게이지먼트가 위조된 경우입니다. 이 경우, 사기성 인게이지먼트는 차단되고, 어트리뷰션은 첫 번째 유효 기여 광고 네트워크에 재할당됩니다.

다음 표에는 클러스터 수준에서 차단된 이유들이 나열되어 있습니다:

<div id="cluster-level-fake-install-block-reasons" />

#### 클러스터 수준: 가짜 인스톨 차단 이유

| 차단된 이유 | 차단된 하위 이유 | 설명 |
| --- | --- | --- |
| 봇 | 타임스탬프 이상 | 디바이스에서 수집된 어트리뷰션 흐름 클릭 시간 및 기타 타임스탬프 관련 이상 |
| 봇, 사이트 블랙리스트 | 디바이스 에뮬레이터 | 가상 환경에서 작동하는 자동 스크립트에 의해 발생한 대규모 인스톨 |
| 사이트 블랙리스트 | 디바이스 팜 | 높은 비율의 알려지지 않은(신규) 디바이스 |
| 행동적 이상 | 행동적 이상 | 일반적인 앱 유저 행동 패턴과 비교하여 인앱에서 의심스러운 행동 |

<div id="cluster-level-attribution-hijacking-block-reasons" />

#### 클러스터 수준: 어트리뷰션 하이재킹 차단 이유

| 차단된 이유 | 차단된 하위 이유 | 설명 |
| --- | --- | --- |
| ctit\_anomalies, 인스톨 하이재킹 | ctit\_anomalies | 앱 표준에 따른 비정상적인 CTIT 패턴 |
| 클릭 플러드 | 클릭 플러드 | 긴 CTIT 분포에서 비정상적으로 높은 클릭 수량 |
| 인스톨 하이재킹 | 클릭 클러스터 | 디바이스 단위 맬웨어에 의해 발생한 클릭 |

</Accordion>

<div id="inapp-level-blocked-reasons" />

<Accordion title="인앱 수준 차단 이유">

인앱 이벤트는 다음과 같은 이유로 차단될 수 있습니다:

* 최초 인스톨이 가짜로 확인되었습니다.
* 유효성 검증 규칙에 따라.
* 우리 알고리즘이 프로드를 감지했기 때문입니다.

다음 표에는 인앱 수준에서 차단된 이유가 나열되어 있습니다.

<div id="in-app-level-block-reasons" />

#### 인앱 수준 차단 이유

| 차단된 이유 | 차단된 하위 이유 | 설명 |
| --- | --- | --- |
| 인스톨에서 상속됨 | 인스톨에서 상속됨 | 초기 인스톨이 [인스톨](/docs/protect360-raw-data-reports#install-level-blocked-reasons) 또는 [거부된](/docs/protect360-raw-data-reports#cluster-level-blocked-reasons) 수준 이유에 따라 가짜로 식별되었습니다. |
| inapps\_bots | 가짜 장치 매개변수 | 앱스플라이어 알고리즘이 프로드를 감지합니다 |
| 인앱 스토어 검증 | - | 인앱 구매의 <Anchor target="_blank" href="/marketers/ko/docs/legacy-receipt-validation-for-in-app-purchases">영수증 검증</Anchor>이 실패했습니다. |
| validation\_inapps | 유효성 검증 규칙 | 수동으로 정의된 유효성 검증 규칙 기반 |

</Accordion>

<div id="retargeting" />

### 리타겟팅

Protect360 로데이터에는 리타겟팅 캠페인에서 발생한 사기성 인스톨 및 세션(각각 리어트리뷰션 및 리인게이지먼트라고 함)이 포함되어 있습니다. 데이터는 <Anchor target="_blank" href="/marketers/ko/docs/raw-data-field-dictionary#event">이벤트 이름</Anchor> 및 <Anchor target="_blank" href="/marketers/ko/docs/raw-data-field-dictionary#attribution::e9c68f6c">리타겟팅 전환 유형</Anchor> 필드를 사용하여 표시됩니다. 이는 다음과 같이 표시됩니다:

* 인스톨(이벤트 이름에는 적용되지만 리타겟팅 전환 유형에는 포함되지 않음)
* 리어트리뷰션
* 리인게이지먼트
* 재설치

Protect360 리타겟팅 로데이터는 다음과 같이 실시간 차단 및 사후 어트리뷰션에 식별된 프로드를 위해 사용할 수 있습니다.

<table><thead><tr><th>리포트 </th><th>데이터 내보내기</th><th>Pull API</th><th>데이터 락커</th></tr></thead><tbody><tr><td>인스톨</td><td><span>✓\*</span></td><td><span>✓\*</span></td><td>-</td></tr><tr><td>사후 어트리뷰션 인스톨</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td colspan="4"> <span>\* 리인게이지먼트 데이터는 사용할 수 없습니다</span><span><span><br/></span> </span> </td></tr></tbody></table>

<div id="hijacked-installs-attribution-correction" />

### 하이재킹된 인스톨 어트리뷰션 수정

하이재킹된 인스톨의 경우, 앱스플라이어가 사기 네트워크에 대한 어트리뷰션을 차단하고 최종 합법적 기여자 소스에 대해 처리합니다.

하이재킹된 인스톨의 경우  사용하여 <Anchor target="_blank" href="/marketers/ko/docs/raw-data-field-dictionary#protect360">rejected\_reason\_value</Anchor> 필드를 유효한 기여자(미디어 소스), 즉 원래 어트리뷰션을 받아야 했던 기여자를 식별합니다.

* **rejected\_reason\_value**은 <Anchor target="_blank" href="/marketers/ko/docs/raw-data-field-dictionary#attribution::2a6fd501">**기여자[1-3]**</Anchor> 또는 **오가닉** **값을 포함합니다.** 기여자[1-3] **및** 미디어 소스\/파트너 **필드를 확인하여 기여자 세부 사항을 보고 조정하세요.**
* 귀사의 리포트에 기여자 필드가 표시되지 않으면 **데이터 내보내기** 페이지에서 추가할 수 있습니다.

**참고**: 하이재킹된 인스톨이 실시간으로 차단되면 올바른 어트리뷰션이 앱스플라이어 대시보드 및 보고서에 표시됩니다(Protect360에만 국한되지 않음). 하이재킹된 인스톨이 어트리뷰션 이후에 식별되었을 경우, 올바른 어트리뷰션은 Protect360 로데이터에만 표시됩니다.

<div id="traits-and-limitations" />

<Accordion title="특성 및 제한 사항">

| 특성 | 비고 |
| --- | --- |
| 인앱 리포트 | 인앱 리포트에는 기여자 필드가 포함되지 않습니다. 기여자 필드는 인스톨 리포트에서만 사용할 수 있습니다. |
| 빈 값 | 프라이버시와 관련된 로데이터 제한으로 인해 로데이터 리포트는 비어 있는 값이 포함된 필드를 보여줄 수 있습니다. 그 예가 기여자 필드입니다. |

</Accordion>

<div data-zendesk-anchors="about-protect360-raw-data-reports=protect360-%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%A6%AC%ED%8F%AC%ED%8A%B8%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC h_01HE7S55TCE60A34T6RCNTCQK8=protect360-%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%A6%AC%ED%8F%AC%ED%8A%B8%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC h_01J91EP40Q69KXXF2SR66AM2FQ=%EC%B0%B8%EA%B3%A0 h_01HE7S55TC4G31R9EANMKCZ7V5=report-types protect360-rawdata-report-types=protect360-%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EC%9C%A0%ED%98%95 h_01HE7S55TCKQYTXPV6J54SHM0D=protect360-%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EC%9C%A0%ED%98%95 h_01HE7S55TC4F5S243BSGN74RDK=postattribution-reports using-postattribution-reports=%EC%82%AC%ED%9B%84-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EC%82%AC%EC%9A%A9%ED%95%98%EA%B8%B0 h_01HE7S55TC7KCF75KFXHCE3K2K=%EC%82%AC%ED%9B%84-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EC%82%AC%EC%9A%A9%ED%95%98%EA%B8%B0 h_01HE7S55TCR8BKZ0PQ5B14X3X4=%EC%98%88%EC%8B%9C h_01HE7S55TC95YC1BJJ0ZERCQ14=raw-data-availability-by-tool-type protect360-rawdata-availability-by-tool-type=%EB%8F%84%EA%B5%AC-%EC%9C%A0%ED%98%95%EB%B3%84-protect360-%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B0%80%EC%9A%A9%EC%84%B1 h_01HE7S55TCH4CES29C5J3QXQK4=%EB%8F%84%EA%B5%AC-%EC%9C%A0%ED%98%95%EB%B3%84-protect360-%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B0%80%EC%9A%A9%EC%84%B1 getting-raw-data-reports=%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EB%B0%9B%EA%B8%B0 h_01HE7S55TC3MRT6E9QV0J0X6FC=%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EB%B0%9B%EA%B8%B0 h_01HE7S55TCBVFQ1DH06G53BNEN=download h_01HE7S55TCMT81J4SWBFQFYV2C=pull-api pull-api-raw-data-report-parameters=pull-api-%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%A6%AC%ED%8F%AC%ED%8A%B8-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 h_01HE7S55TCRRD95D0QPCXBRF8T=pull-api-%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%A6%AC%ED%8F%AC%ED%8A%B8-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 h_01HE7S55TCMAY86J1HKYB0APZ6=data-locker protect360-report-structure=protect360-%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EA%B5%AC%EC%A1%B0 h_01HE7S55TCS91ZC9V3K0VDSVXK=protect360-%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EA%B5%AC%EC%A1%B0 blocked-reasons=%EC%B0%A8%EB%8B%A8%EB%90%9C-%EC%9D%B4%EC%9C%A0 h_01HE7S55TC1ZEDD5ABD21FCPY2=%EC%B0%A8%EB%8B%A8%EB%90%9C-%EC%9D%B4%EC%9C%A0 h_01HE7S55TDMDSVQCVSV5YS3CZN=click-level-blocked-reasons h_01HE7S55TD754T07FWHFK5P71K=install-level-blocked-reasons install-level-fake-install-block-reasons=%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%88%98%EC%A4%80-%EA%B0%80%EC%A7%9C-%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%B0%A8%EB%8B%A8-%ED%95%98%EC%9C%84-%EC%9D%B4%EC%9C%A0 h_01HE7S55TDHTE5P47N1CCREGZX=%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%88%98%EC%A4%80-%EA%B0%80%EC%A7%9C-%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%B0%A8%EB%8B%A8-%ED%95%98%EC%9C%84-%EC%9D%B4%EC%9C%A0 install-level-attribution-hijacking-block-reasons=%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%88%98%EC%A4%80-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%95%98%EC%9D%B4%EC%9E%AC%ED%82%B9-%EC%B0%A8%EB%8B%A8-%ED%95%98%EC%9C%84-%EC%9D%B4%EC%9C%A0 h_01HE7S55TDFA6WGAHE80ECV8CA=%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%88%98%EC%A4%80-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%95%98%EC%9D%B4%EC%9E%AC%ED%82%B9-%EC%B0%A8%EB%8B%A8-%ED%95%98%EC%9C%84-%EC%9D%B4%EC%9C%A0 h_01HE7S55TDCHG0CVJA3JRSAW3G=cluster-level-blocked-reasons cluster-level-fake-install-block-reasons=%ED%81%B4%EB%9F%AC%EC%8A%A4%ED%84%B0-%EC%88%98%EC%A4%80-%EA%B0%80%EC%A7%9C-%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%B0%A8%EB%8B%A8-%EC%9D%B4%EC%9C%A0 h_01HE7S55TDBES0BY0FF3WKSSVG=%ED%81%B4%EB%9F%AC%EC%8A%A4%ED%84%B0-%EC%88%98%EC%A4%80-%EA%B0%80%EC%A7%9C-%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%B0%A8%EB%8B%A8-%EC%9D%B4%EC%9C%A0 cluster-level-attribution-hijacking-block-reasons=%ED%81%B4%EB%9F%AC%EC%8A%A4%ED%84%B0-%EC%88%98%EC%A4%80-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%95%98%EC%9D%B4%EC%9E%AC%ED%82%B9-%EC%B0%A8%EB%8B%A8-%EC%9D%B4%EC%9C%A0 h_01HE7S55TD3M45TH4PY2W805W7=%ED%81%B4%EB%9F%AC%EC%8A%A4%ED%84%B0-%EC%88%98%EC%A4%80-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%95%98%EC%9D%B4%EC%9E%AC%ED%82%B9-%EC%B0%A8%EB%8B%A8-%EC%9D%B4%EC%9C%A0 h_01HE7S55TDGB05PEZX8KS3J3QJ=inapp-level-blocked-reasons inapp-level-block-reasons=%EC%9D%B8%EC%95%B1-%EC%88%98%EC%A4%80-%EC%B0%A8%EB%8B%A8-%EC%9D%B4%EC%9C%A0 h_01HE7S55TD661EHCV50S9BW5MS=%EC%9D%B8%EC%95%B1-%EC%88%98%EC%A4%80-%EC%B0%A8%EB%8B%A8-%EC%9D%B4%EC%9C%A0 retargeting=%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85 h_01HE7S55TDSYDC8BWZ8D8DF9JE=%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85 hijacked-installs-attribution-correction=%ED%95%98%EC%9D%B4%EC%9E%AC%ED%82%B9%EB%90%9C-%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%88%98%EC%A0%95 h_01HE7S55TD8SDCQJCCYQC0MNES=%ED%95%98%EC%9D%B4%EC%9E%AC%ED%82%B9%EB%90%9C-%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%88%98%EC%A0%95 h_01J91E55BXQ4E01A9R3EB33WYF=traits-and-limitations" />
