---
title: 로데이터 리포팅 개요
metadata:
  keywords:
    - LTV
    - raw data
    - uninstalls
    - AFI
    - Advertisers
    - Agencies
    - Premium Feature
    - Gray
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Agencies
    - Raw Reports
  created_at: '2016-03-21T08:32:06Z'
  edited_at: '2026-10-14T10:26:27Z'
  id: 209680773
  locale: ko
  section: Raw data reporting/APIs
  section_id: 6550930711057
  url: https://support.appsflyer.com/hc/ko/articles/209680773
---
> **한눈에 보기:** 행 수준 데이터(로데이터라고도 함)는 유저와 관련된 인스톨, 인앱 이벤트, 웹사이트 방문, Protect360에서 차단된 인스톨, 발생한 광고 수익, 파트너에게 전송된 유저 관련 포스트백 등의 이벤트를 설명합니다. 로데이터 리포트는 다운로드, API 및 데이터 락커를 통해 사용할 수 있습니다.

<div id="raw-data-reportingtools-and-reports" />

## 로데이터 리포팅—도구 및 리포트

로데이터 리포트를 통해 유저 행동과 여정을 분석하고, 애드 네트워크 계정을 조정하며, 귀사의 CRM 및 BI 시스템을 강화할 수 있습니다. 로데이터를 사용하면 분석, 최적화, 앱 성과 개선의 가능성을 높일 수 있습니다.

리포트는 리포팅 도구를 통해 제공됩니다. 각 도구는 다양한 사용 사례에 맞는 특성을 지니고 있습니다. 예를 들어, 특정 애드 네트워크 계정을 조정하려면 필요에 따라 데이터 내보내기 페이지를 통해 리포트를 다운로드하세요. 유저 성과 데이터를 BI 시스템에 로드하려면 데이터 락커 또는 Pull API를 사용해 프로그래밍 방식으로 데이터를 가져오세요.

<div id="tip" />

> 👍 **팁**
>
> 로데이터에 대해  더 알고 싶으십니까? <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7806/play/18629/viewing-and-understanding-your-raw-data">앱스플라이어 학습 포털에서 짧지만 유익한 강의 코스</Anchor>를 확인해 보세요.

<div id="reporting-tools-characteristics-and-features" />

<Accordion title="리포팅 도구—특징 및 기능">

이 섹션에 나열된 리포팅 도구를 사용하여 리포트를 사용할 수 있습니다.

고려 사항:

* 리포트 날짜 범위는 이벤트가 발생한 실제 날짜와 관련이 있습니다. 이는 날짜 범위가 <Anchor target="_blank" href="/marketers/ko/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTV(유저생애가치) 기반</Anchor>인 데이터 집약형 리포트와는 대조적입니다.
* 필드 설명—<Anchor target="_blank" href="/marketers/ko/docs/raw-data-field-dictionary">데이터 필드 사전</Anchor>을 참조하세요.

<div id="reporting-tools" />

#### 리포팅 도구

<table><thead><tr><th>도구</th><th>설명</th><th>여러 개/단일 앱(1)</th><th>데이터 최신성 기능(2)</th><th>스크립트에 포함</th><th>시간대</th><th>통화</th></tr></thead><tbody><tr><td><a href="./raw-data-export-page" target="_blank">로데이터 내보내기 페이지</a></td><td><ul><li>유저 인터페이스를 사용하여 리포트를 다운로드하세요.</li><li>형식: CSV 파일</li></ul></td><td>단일</td><td>지속적으로 업데이트됨</td><td><span><strong>x</strong></span></td><td>앱별</td><td>앱별</td></tr><tr><td><a href="./pull-api-raw-data" target="_blank">Pull API\*</a></td><td><ul><li>API 호출을 사용하여 리포트를 다운로드하세요.</li><li>형식: CSV 파일</li></ul></td><td>단일</td><td>지속적으로 업데이트됨</td><td><span>✓</span></td><td><ul><li>선택 가능</li><li>기본값: UTC</li></ul></td><td><ul><li>선택 가능</li><li>기본값: USD</li></ul></td></tr><tr><td> <a href="./data-locker-for-marketers" target="_blank">데이터 락커</a> <span><strong>P</strong></span> </td><td><ul><li> <a href="./data-locker-cloud-service-setup" target="_blank">클라우드에 있는 버킷</a>으로 스트리밍된 데이터 </li><li>볼륨 제한 없음</li><li>데이터 가용성 기간: 14일.</li><li>형식: CSV 또는 파케이</li></ul></td><td>다수</td><td>몇 시간 간격으로 지속 업데이트</td><td><span>✓</span></td><td>UTC</td><td>USD </td></tr><tr><td> <a href="./push-api-streaming-raw-data" target="_blank">Push API<span></span></a> <span><strong>P</strong></span> </td><td><ul><li>유저 여정 데이터(인스톨, 인앱, 리타겟팅, SKAN)를 실시간으로 귀사의 서버로 전송합니다.</li><li>형식: JSON 또는 쿼리 매개변수</li></ul></td><td>같은 종단점을 사용할 수 있습니다</td><td>앱스플라이어에서 이벤트 기록 후 몇 분 이내</td><td><span>✓</span></td><td>UTC + 앱별</td><td>USD + 앱별</td></tr><tr><td> <a href="./conversion-data-payloads-and-scenarios" target="_blank">SDK 전환 데이터</a> (3)</td><td><ul><li>앱 내에서 어트리뷰션 전환 데이터를 얻습니다.</li><li>형식: JSON</li></ul></td><td>N\/A</td><td>앱 최초 실행 후 몇 초 이내</td><td><span>✓</span></td><td>UTC</td><td>N\/A</td></tr><tr><td colspan="7"> <strong>참고 및 약어:</strong><br/>(1) 여러 앱 지원<br/>(2) 데이터 최신성은 리포트 자체에 따라 달라지며, 일부 리포트는 일별로 제공됩니다.<br/>(3) SDK 전환 데이터는 앱 최초 실행 후 몇 초 이내에 사용자 어트리뷰션 데이터를 가져오므로 정확도가 가장 낮습니다.<br/><span><strong>(P)</strong> </span><strong>프리미엄 기능<br/><a href="./report-generation-quotas-rate-limitations" target="_blank">(\*) 리포트 생성 할당량 적용</a> </strong> </td></tr></tbody></table>

<div id="tool-limitations" />

#### 도구 한계

<table><thead><tr><th>제한 사항 </th><th>Pull API (\*)</th><th>Push API</th><th>데이터 락커</th><th>SDK<br/>전환 데이터</th></tr></thead><tbody><tr><td>데이터 한계</td><td>호출당 100만 행</td><td>N\/A</td><td>N/A</td><td>N\/A</td></tr><tr><td>데이터 선택 옵션</td><td>데이터 유형을 선택하세요. 제한된 필드 선택 옵션</td><td>데이터 유형, 필드 및 인앱 항목 선택</td><td>데이터 유형, 필드 및 인앱 항목 선택</td><td>아니오</td></tr><tr><td>데이터 가용성 기간</td><td>90일</td><td>N\/A</td><td>14일 </td><td>수명( SDK에서 사용 가능)</td></tr><tr><td colspan="5"><a href="./report-generation-quotas-rate-limitations" target="_blank">(\*) 리포트 생성 할당량 적용</a></td></tr></tbody></table>

<div id="integration-considerations" />

#### 연동 고려 사항

| 고려 사항 | Pull API | Push API | 데이터 락커 | SDK  <br />전환 데이터 |
| --- | --- | --- | --- | --- |
| 서버 측 개발 | 선택 사항 | 필수 | 선택 사항 | 선택 사항 |
| 데이터 처리 필요 | 선택 사항 | 필수 | 선택 사항 | 선택 사항 |
| 데이터 손실 위험 | 아니오 | 예, 수신 서버가 다운된 경우 | 아니오 | 애드 네트워크 응답에 지연이 있을 경우 작음 |
| 클라이언트-서버 처리 비용 | 없음 | 높음 | 낮음 | 없음(데이터를 서버로 보내는 경우 제외) |
| 클라이언트-서버 유지보수 | 없음 | 높음 | 낮음 | 없음(데이터를 서버로 보내는 경우 제외) |
| 데이터 형식 | CSV 파일 | JSON 또는 쿼리 매개변수 | CSV 또는 파케이 | JSON |

</Accordion>

주어진 맥락에서 발생하는 로데이터 기록은 리포트에서 그룹화됩니다. 예를 들어, 논오가닉 인스톨, 오가닉 인앱 이벤트. 설명을 쉽게 하기 위해 리포트는 다음과 같이 그룹화되었습니다.

* **유저 여정:** 앱과의 유저 여정과 인게이지먼트를 추적하여 사용합니다.  
  예: 클릭 > 인스톨 > 인앱 이벤트 > 앱 삭제.
* **특징:** 앱스플라이어 특정 기능과 관련이 있지만 주요 유저 여정의 일부는 아닙니다. 예를 들어, 광고 네트워크에 대한 포스트백, 프로드 및 유효성 검증 규칙 리포트, 사용자 수준 광고 수익 리포트 등이 있습니다.

<div id="report-fields" />

<Accordion title="리포트 필드">

<Anchor target="_blank" href="/marketers/ko/docs/raw-data-field-dictionary">로데이터</Anchor> 필드 사전에는 유저 여정 리포트와 관련된 필드와 일부 기능 리포트 필드가 포함되어 있습니다. 원칙은 다음과 같습니다.

* **유저 여정:**
  * 공통된 필드 집합을 갖습니다.
  * 필드의 수는 여정 맥락에 따라 달라집니다. 예를 들어, 논오가닉 리포트에는 사용자를 유치한 것으로 인정된 미디어 소스가 포함됩니다. 오가닉 리포트의 어트리뷰션 필드는 미디어 소스가 없기 때문에 채워지지 않았습니다.
* **특징**: 고유한 필드 집합을 갖거나 유저 여정 필드와 해당 기능과 관련된 추가 필드를 포함합니다. 예를 들어, SKAdNetwork 리포트에는 고유한 필드 목록이 있는 반면, 포스트백 리포트에는 유저 여정 필드와 파트너에게 포스트백 보내기와 관련된 추가 필드가 포함됩니다.

**팁**! 리포트에 익숙해지는 가장 좋은 방법은 리포트를 직접 보는 것입니다. 귀사의 리포트를 <Anchor target="_blank" href="/marketers/ko/docs/raw-data-export-page">데이터 내보내기 페이지</Anchor>를 통해 다운로드할 수 있습니다.

이해의 편의를 위해, 유저 여정 필드는 맥락에 따라 그룹으로 나뉩니다.

<div id="user-journey-raw-data-field-groups" />

#### 유저 여정 로데이터 필드 그룹

| 필드 그룹 | 오가닉 사용자와 관련됨 | 예시 필드 |
| --- | --- | --- |
| 앱 | 예 | 앱 ID, 앱 이름, 앱 버전, SDK 버전, 앱 추적 투명성(ATT) |
| 어트리뷰션 | 아니요, 인스톨 시간을 제외하고 | 인스톨 시간, 어트리뷰트된 터치 시간, 미디어소스, 캠페인, 광고 세트, 광고, 파트너, 리타게팅 전환 유형 |
| 기여자 어트리뷰션 | 아니오 | 기여자 파트너, 측정 유형 |
| 디바이스 정보 | 예 | 광고 ID, GAID, OAID, 디바이스 유형, 고객 사용자 ID |
| 디바이스 위치 | 예 | IP 주소, 도시, 국가 |
| 이벤트 | 예 | 인앱 이벤트 리포트에 입력됨:<br /><br />이벤트 이름, 이벤트 가치, 이벤트 수익 |

</Accordion>

<div id="user-journey-reports" />

## 유저 여정 리포트

<Image align="center" alt="로데이터_-_유저_획득_.png" src="https://files.readme.io/319da2a6a5567d6cfe4a74337279e67e0bdcdb063e62ecacde5eb4293a98a1a2-36317497158033.png" />

<div id="user-journey-basics" />

<Accordion title="유저 여정 기본 사항">

유저 여정 리포트에는 사용자의 수명 동안 발생한 이벤트에 대해 수집된 데이터가 포함됩니다. 데이터는 다음 기준에 따라 리포트로 나뉩니다:

* 유저 소스: 오가닉 또는 논오가닉
* 여정 컨텍스트:
  * 앱 설치 전 광고 인게이지먼트(노출 및 클릭)
  * 유입
  * 리타겟팅

**유저 인입(UA) 리포트**에는 다음이 포함됩니다.

* *잠재적* 유저가 광고와 인게이지먼트 하여 인스톨 전에 발생하는 노출 및 클릭.
* 인스톨 이벤트.
* 유저가 수행한 후속 인앱 이벤트.

**리타겟팅 리포트 포함하다:**

* 사용자가 리타겟팅될 때 발생하는 노출 및 클릭.
* 전환 이벤트: 리인게이지먼트 또는 리어트리뷰션.
* 리인게이지먼트의 일부로 수행된 후속 인앱 이벤트. 유의사항:
  * 리타겟팅 데이터는 항상 논오가닉입니다.
  * 리타겟팅 인앱 이벤트는 UA 및 리타겟팅 인앱 이벤트 리포트에 포함됩니다. <Anchor target="_blank" href="/marketers/ko/docs/resolve-retargeting-double-attribution">리타겟팅 이중 어트리뷰션</Anchor> 방법론을 확인하세요.

    <Image align="center" alt="로데이터_-_리타겟팅.png" src="https://files.readme.io/717f6e43ca3b224ead9e3e1c5f9b277d2f21dbc1fe3b4c217ebf4bdbc539bab7-36317470735249.png" />

유저 여정을 따르려면 관심 있는 여정 부분과 관련된 리포트를 결합하세요. 예를 들어, 인스톨과 인앱 이벤트. 이후, 앱스플라이어 ID, 이벤트 시간, 리포트 유형으로 정렬합니다. 결과는 특정 유저의 시간에 따른 이벤트, 즉 유저 여정입니다.

</Accordion>

<div id="user-journey-report-availability" />

<Accordion title="유저 여정 리포트 가용성">

* 리포트의 이용 가능성은 귀사의 구독 플랜에 따라 다릅니다.
* 리포트에는 오가닉 유저, 논오가닉 유저, 또는 둘 다 포함될 수 있습니다.
* 리텐션 정책은 리포팅 도구와 로데이터의 출처에 따라 과거 로데이터 리포트에 적용됩니다. 일반적으로, 이전 90일 동안의 데이터가 제공됩니다. **참고**! 데이터 집약형 데이터에는 리텐션 정책이 적용되지 않습니다.

<div id="user-journey-reports-1" />

#### 유저 여정 리포트

<table><thead><tr><th>카테고리</th><th>데이터 락커만의 고유 특징</th><th>리포트 주제</th><th>오가닉</th><th>논오가닉</th></tr></thead><tbody><tr><td>유저 유입</td><td><span>✓</span></td><td>클릭</td><td colspan="2">N\/A</td></tr><tr><td>리타겟팅</td><td><span>✓</span></td><td>리타겟팅 캠페인에서의 클릭 </td><td colspan="2">리타겟팅은 항상 논오가닉</td></tr><tr><td>유저 유입</td><td><span>✓</span></td><td>노출</td><td colspan="2">N\/A</td></tr><tr><td>리타겟팅</td><td><span>✓</span></td><td>리타겟팅 캠페인에서의 노출</td><td colspan="2">리타겟팅은 항상 논오가닉</td></tr><tr><td>유저 유입</td><td>-</td><td>인스톨 </td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>유저 유입</td><td>-</td><td>인앱 이벤트 </td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>유저 유입</td><td>-</td><td>어트리뷰션된 광고 수익</td><td>-</td><td><span>✓</span></td></tr><tr><td>유저 유입</td><td>-</td><td>오가닉 광고 수익</td><td><span>✓</span></td><td>-</td></tr><tr><td>리타겟팅</td><td>-</td><td>리타겟팅 광고 수익</td><td colspan="2">리타겟팅은 항상 논오가닉</td></tr><tr><td>리타겟팅</td><td>-</td><td>리타겟팅 전환 (리인게이지먼트 및 리어트리뷰션)</td><td colspan="2">리타겟팅은 항상 논오가닉</td></tr><tr><td>리타겟팅</td><td>-</td><td>리타겟팅 인앱 이벤트 (리인게이지먼트 및 리어트리뷰션)</td><td colspan="2">리타겟팅은 항상 논오가닉</td></tr><tr><td>리타겟팅</td><td><span>✓</span></td><td>리타겟팅 세션 (리인게이지먼트 및 리어트리뷰션)</td><td colspan="2">리타겟팅은 항상 논오가닉</td></tr><tr><td>유저 유입</td><td><span>✓</span></td><td>세션</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>유저 유입</td><td>-</td><td>논오가닉 앱 삭제 </td><td>-</td><td><span>✓</span></td></tr><tr><td>유저 유입</td><td>-</td><td>오가닉 앱 삭제</td><td><span>✓</span></td><td>-</td></tr><tr><td>유저 유입</td><td><span>✓</span></td><td>크로스 플랫폼 인게이지먼트</td><td><span>✓</span></td><td><span>✓</span></td></tr></tbody></table>

</Accordion>

<div id="user-journey-report-descriptions" />

<Accordion title="유저 여정 리포트 설명">

<div id="clicks-and-impressions" />

#### 클릭과 노출

| 리포트 | 특성 |
| --- | --- |
| 컨텍스트 | 유저는 캠페인에 참가하여 광고를 클릭하거나 봅니다. |
| 특성 | 보고서에는 유저가 광고를 클릭하거나 <Anchor target="_blank" href="/marketers/ko/docs/measure-view-through-engagements#set-impression-links">볼</Anchor> 때 나타나는 어트리뷰션 링크와 HTTP 헤더 기록이 포함됩니다. |
| 사례 | <ul><li>앱 오픈으로 이어지지 않는 캠페인(인스톨, 리어트리뷰션, 리인게이지먼트)을 최적화하세요.</li><li>다양한 캠페인을 활용하여 이런 유저를 리타겟팅하세요.</li></ul> |
| 리포트 예시 | <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRcNRnKgPP5ZRL51o3b9PDhbFv6VFG7xe9xHqCsIC7HwqO2ERLV5dh4bS7pr-WONxpUXvsCc64eTzzN/pub?gid=1036692270&single=true&output=csv">클릭</Anchor> |
| 비고 | SRN 데이터를 사용할 수 없습니다. |
| 제한된 사용자 | 어떤 경우에는 개인정보 보호 규칙으로 인해 노출 및 클릭 데이터가 제한되거나(유저 식별자 없음) 전혀 사용할 수 없는 경우도 있습니다. 이용 가능 여부는 미디어 소스 및 플랫폼에 따라 다릅니다. |

<div id="installs-and-retargeting-conversions" />

#### 인스톨 및 리타겟팅 전환

<table><thead><tr><th rowspan="2">리포트 이름 </th><th rowspan="2"><p>유저 유입: 인스톨</p></th><th rowspan="2">리타겟팅: 전환</th></tr></thead><tbody><tr><td>컨텍스트</td><td><p>유저가 처음으로 앱을 열 때.</p></td><td><p>유저가 리타겟팅 광고에 참여한 후 앱을 엽니다. 리타겟팅 전환은 리인게이지먼트 또는 리어트리뷰션을 의미합니다.</p><a href="./retargeting-attribution-guide#retargeting-reports-and-raw-data" target="_blank">리타겟팅 어트리뷰션 가이드</a>를 참조하세요. </td></tr><tr><td>활용 사례</td><td><ul><li>앱스플라이어 분석 도구를 통해 사용할 수 없는 필드를 이용하여 데이터 집약형 리포트를 생성합니다.</li><li>다른 리포트와 결합하여 심층적인 횡단면 분석을 실시할 수 있습니다.</li><li>도시, 광역도시 등 다양한 측면에서 성과를 분석합니다. </li><li>타겟팅 목적으로 국가, 도시, 언어별로 유저를 세분화합니다.</li><li>리타겟팅 목적으로 유저 디바이스 ID를 얻습니다.</li></ul></td><td>인스톨과 유사합니다.</td></tr><tr><td>오가닉 vs. 논오가닉</td><td><ul><li> <strong>논오가닉:</strong> 어트리뷰션 및 기여자 어트리뷰션 필드 그룹이 채워집니다.</li><li> <strong>오가닉:</strong> 미디어 소스 필드는 비어 있거나 null이거나 오가닉입니다. 데이터를 시스템에 로드할 때 이 점을 고려하세요. </li></ul></td><td>적용 불가</td></tr><tr><td>리포트 예시</td><td><a href="https://docs.google.com/spreadsheets/d/e/2PACX-1vR2yvNGmZp8ataHBj89CFq856PmDixnyjKK75O8fQcS9TjT8J2jBAnJoTn3350NV-7pCSlaT0oh8ebs/pub?output=csv" target="_blank">인스톨</a></td><td>리타겟팅 전환 리포트는 인스톨 리포트와 동일한 구조를 가지고 있습니다. 일부 필드는 리타겟팅 맥락에서 채워집니다. <a href="./retargeting-attribution-guide#retargeting-reports-and-raw-data" target="_blank">리타겟팅 로데이터</a>를 참조하세요. </td></tr></tbody></table>

<div id="in-app-events" />

#### 인앱 이벤트

<Table>
  <thead>
    <tr>
      <th>
        리포트
      </th>
      <th>
        특성
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="report-context"></span>
        리포트 컨텍스트
      </td>
      <td>
        어트리뷰션 후(인스톨, 리어트리뷰션 또는 리인게이지먼트) 유저가 수행한 작업의 연대순 목록
      </td>
    </tr>
    <tr>
      <td><span id="characteristics"></span>
        특성
      </td>
      <td>
        * 리포트 구조와 필드는 인스톨 리포트와 유사합니다.
        * 전용 필드는 이벤트를 설명합니다. 여기에는 이벤트 이름, 값, 수익, 시간이 포함됩니다.
      </td>
    </tr>
    <tr>
      <td><span id="use-case"></span>
        사례
      </td>
      <td>
        리포트를 사용하여 다음을 수행할 수 있습니다.

        * 사용자의 생애 동안 유저 여정을 관찰하여 데이터 인사이트를 얻으세요.
        * 인스톨 및 인앱이벤트 로데이터를 결합하여 전체 사용자 여정을 따르십시오.
      </td>
    </tr>
    <tr>
      <td><span id="event-values"></span>
        이벤트 값
      </td>
      <td>
        **이벤트 값 필드**

        이벤트 값 필드에는 JSON 형식의 이벤트와 관련된 모든 데이터가 포함되어 있습니다. 추가 분석을 위해 이를 귀사의 BI 시스템에 로드할 수 있습니다.

        **팁! <Anchor target="_blank" href="https://docs.microsoft.com/en-us/power-query/parse-json-xml">Microsoft Excel의</Anchor> <Anchor target="_blank" href="https://docs.microsoft.com/en-us/power-query/parse-json-xml">Power Query</Anchor>를 사용하여 JSON 텍스트 문자열에서 이벤트 파라미터를 구문 분석할 수 있습니다.**

        ```json
        {"af_level":"10","af_user_journey":"3387","arena":"7","char_type":"paladin"}
        ```

        **수익 리포팅**

        앱스플라이어의 수익 및 ROI (투자수익률) 데이터는 인앱 이벤트로 전송된 af\_revenue에서 파생됩니다.

        af\_revenue 파라미터가 인앱 이벤트로 전송되면, 앱스플라이어는 이를 사용하여 이벤트 수익 필드를 채웁니다. 이 필드에서 앱스플라이어는 대시보드와 데이터 집약형 리포트를 업데이트합니다.

        주의! **실제 수익이 발생한 것을 설명하는 인앱 이벤트와 함께 af\_revenue 파라미터만 사용하세요.** 수익과 관련되지만 최종이 아닌 다른 이벤트(예: add\_to\_cart)의 경우, af\_price와 같은 다른 파라미터를 사용합니다.
      </td>
    </tr>
    <tr>
      <td><span id="example-report"></span>
        리포트 예시
      </td>
      <td>
        <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQhOF-g3HeqZt3rXx7WZVQnB54p7ALW_IEpnJ9xtAkrcb9XzZwweiNCZzEmuX7q0i1g6yYMxYtuuX1c/pub?output=csv">인앱 이벤트</Anchor>
      </td>
    </tr>
    <tr>
      <td><span id="remarks"></span>
        비고
      </td>
      <td>
        * 리타게팅 인앱이벤트는 UA 및 리타게팅 인앱이벤트 로데이터 리포트에 모두 <Anchor target="_blank" href="/marketers/ko/docs/resolve-retargeting-double-attribution">이중으로 기록됩니다</Anchor>.
        * 인앱이벤트는 시작 이벤트(af\_app\_opened)를 포함하지 않습니다. 이는 <Anchor target="_blank" href="/marketers/ko/docs/measure-sessions">세션</Anchor> 로데이터 리포트에서 확인할 수 있습니다.
        * 지역 위치: 이벤트 발생 시점의 유저 IP 주소를 사용하여 파생됩니다.
      </td>
    </tr>
  </tbody>
</Table>

<div id="sessions" />

#### 세션

| 리포트 | 특성 |
| --- | --- |
| 컨텍스트 | 유저가 앱을 열면, 세션 이벤트가 앱스플라이어로 전송됩니다. 세션 간 <Anchor target="_blank" href="/marketers/ko/docs/measure-sessions">최소 시간</Anchor> 임계값을 초과하면 이벤트가 기록됩니다. |
| 특성 | 리포트 구조는 인앱 이벤트 리포트와 동일합니다. 세션(세션 이벤트)은 해당 이벤트의 수가 많기 때문에 별도의 리포트에 나와 있습니다. |
| 사례 | 앱 유저 인게이지먼트를 이해합니다. |
| 리포트 예시 | 세션 리포트는 인앱 이벤트 리포트와 유사합니다. 참고: 로데이터에서 세션의 이벤트 이름은 *launch*입니다. |

<div id="uninstalls" />

#### 앱 삭제

| 리포트 | 특성 |
| --- | --- |
| 컨텍스트 | 사용자가 앱을 삭제한 기록. |
| 특성 | <ul><li>이 리포트는 다른 유저 여정 리포트들과 달리, 지속적이지 않고 매일 갱신됩니다.</li><li>리포트에서 이벤트 시간은 앱스플라이어가 앱이 삭제되었다고 판단하는 시간을 나타내며, 실제 삭제 시간을 나타내지 않습니다. 앱 삭제 측정을 참조하세요.</li></ul> |
| 사용 가능한 필드 | <ul><li>사용자가 논오가닉 미디어 소스에서 온 경우, 미디어 소스 필드가 채워집니다.</li><li>앱 삭제 이벤트는 사용자가 앱을 삭제한 것을 확인한 후 앱스플라이어 서버에 의해 발생합니다. 결과적으로 많은 필드가 채워지지 않을 수 있습니다.</li><li>사용 가능한 유저 식별자는 인스톨 시점에 기록된 식별자입니다. CUID는 사용할 수 없습니다.</li><li>지역 관련 필드는 미디어 소스와 인게이지먼트 당시(클릭 또는 노출)의 사용자 위치로 채워집니다. 인게이지먼트 위치를 알 수 없을 경우, 인스톨 이벤트와 관련된 위치가 사용됩니다.</li></ul> |
| 리포트 예시 | <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRcNRnKgPP5ZRL51o3b9PDhbFv6VFG7xe9xHqCsIC7HwqO2ERLV5dh4bS7pr-WONxpUXvsCc64eTzzN/pub?gid=1558773473&single=true&output=csv">앱 삭제</Anchor> 참고! 예시에서는 명확성을 위해, 관련 데이터가 있을 경우 어떤 필드가 채워지는지를 행 2가 나타냅니다. |
| 활용 사례 | <ul><li>앱 삭제 이벤트, 디바이스, 사용자 특성을 분석합니다.</li><li>리타겟팅을 위한 앱 삭제 이벤트 오디언스를 구축합니다.</li></ul> |

</Accordion>

<div id="user-journey-report-availability-per-tool" />

<Accordion title="도구별 유저 여정 리포트 가용성">

<div id="ad-engagement-report-by-tool" />

#### 도구별 광고 인게이지먼트 리포트

<table><thead><tr><th>리포트</th><th>데이터 내보내기</th><th>Pull API</th><th>데이터 락커</th><th>Push API</th><th>SDK<br/>전환 데이터</th></tr></thead><tbody><tr><td>노출 (1)</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>클릭 (1)</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td colspan="6">(1) 클릭 및 노출 데이터는 비-SRN에 의해 제공됩니다. SRN은 이 데이터를 제공하지 않습니다.</td></tr></tbody></table>

<div id="user-acquisition-reports-by-tool" />

#### 도구별 유저 유입 리포트

| 리포트 | 데이터 내보내기 | Pull API | 데이터 락커 | Push API | SDK 전환 데이터 |
| --- | --- | --- | --- | --- | --- |
| 인스톨 | ✓ | ✓ | ✓ | ✓ | ✓ |
| 세션 | - | - | ✓ | - | - |
| 인앱 이벤트 | ✓ | ✓ | ✓ | ✓ | - |
| 앱 삭제 | ✓ | ✓ | ✓ | - | - |

<div id="retargeting-raw-data-reports-by-tool" />

#### 도구별 리타겟팅 로데이터 리포트

<table><thead><tr><th>리포트</th><th>데이터 내보내기</th><th>Pull API</th><th>데이터 락커</th><th>Push API</th><th>SDK<br/>전환 데이터</th></tr></thead><tbody><tr><td>클릭 (1)</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>전환 (재귀속 + 재참여)</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>노출 (1)</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>세션</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>인앱 이벤트</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td>-</td></tr><tr><td colspan="6">(1) 클릭 및 노출 데이터는 비-SRN에 의해 제공됩니다. SRN은 이 데이터를 제공하지 않습니다.</td></tr></tbody></table>

</Accordion>

<div id="faq" />

<Accordion title="자주 묻는 질문">

| 세부 정보 |
| --- |
| **타임스탬프의 차이는 무엇인가요?**<br /><br />타임스탬프는 모든 리포트에 공통적으로 적용됩니다. 이를 통해 다양한 리포트를 결합할 수 있습니다.<br /><br />다음 타임스탬프가 중요합니다.<ul><li>**귀속된 터치 시간**: 유저가 광고에 인게이지먼트한 시간입니다.</li><li>**인스톨** **시간**: 앱이 처음으로 실행된 시간입니다.</li><li>**이벤트 시간**: 이벤트가 발생한 시간입니다.</li></ul>유의사항:<ul><li>인스톨 리포트에서는 인스톨과 이벤트 시간이 동일합니다.</li><li>인앱 이벤트 리포트에서는 인스톨과 이벤트 시간이 다릅니다. 이 차이는 앱 실행 후 유저가 앱과 인게이지먼트까지 걸리는 시간을 보여줍니다.</li></ul> |
| **기여자 필드의 목적은 무엇입니까?**<br /><br />기여자 필드에는 기여한 매체 소스가 나열됩니다. 때때로 <Anchor target="_blank" href="/marketers/ko/docs/measure-assisted-installs#인스톨-어시스트-리포트">인스톨 어시스트</Anchor>라고도 합니다. Protect360에서는 <Anchor target="_blank" href="/marketers/ko/docs/protect360-raw-data-reports#하이재킹된-인스톨-어트리뷰션-수정">하이재킹된 인스톨 어트리뷰션 수정</Anchor>에도 사용됩니다. |
| **키워드 필드란 무엇입니까? 모든 논오가닉 인스톨에서 사용할 수 없는 이유는 무엇입니까?**<br /><br />Google Ads 또는 Apple Search Ads에 어트리뷰트된 인스톨은 인스톨을 가져오는 광고와 연관된 키워드 또는 키워드 ID를 포함할 수 있습니다. |

</Accordion>

<div id="install-report-tips" />

<Accordion title="인스톨 리포트 팁">

**유저 여정 이해하기**

유저 여정은 유저가 제품 구매나 항공편 예약과 같은 목표를 달성하기 전에 거치는 단계입니다. 유저 여정을 분석하는 목적은 유저가 앱에서 무엇을 하는지, 얼마나 활동적인지, 특정 기간 동안 어떤 가치를 제공하는지 파악하기 위함입니다.

앱스플라이어 ID를 사용하여 유저 여정을 식별하고 강조할 수 있습니다. ID는 디바이스별로 각 앱 인스톨 시 생성됩니다. ID는 유저의 라이프사이클(인스톨부터 앱 삭제까지) 동안 변하지 않습니다. 유저가 디바이스 ID를 재설정해도 ID는 그대로 유지됩니다.

인스톨과 인앱 이벤트 리포트는 구조가 동일하여 하나의 리포트로 통합할 수 있습니다. 병합된 리포트에서 앱스플라이어 ID와 고객 유저 ID(사용 가능한 경우)를 기준으로 데이터를 집계하고 필터링하여 유저 여정을 분석할 수 있습니다.

> 📄 **예시**
>
> #### <span id="engaged-userstrong"></span>참여 유저 - 강력함
>
> * 한 유저가 8월 20일 09:31에 앱을 설치했습니다.
> * 통합된 리포트에 따르면, 이 유저는 8월 20일 10:31, 8월 22일 15:22, 8월 25일 16:47에 구매를 했습니다.
> * 이를 통해 해당 유저가 적극적으로 참여하는 유저임을 알 수 있습니다. 앱 실행 한 지 1시간 만에 구매를 시작했으며, 설치 후 며칠 동안 계속해서 구매를 이어갔습니다.
>
> #### <span id="engaged-userweak"></span>참여 유저 - 약함
>
> * 한 유저가 7월 30일에 앱을 설치했습니다. 병합된 리포트에 따르면, 8월 15일에 장바구니에 상품을 추가했지만 그 이후 구매 이벤트가 없습니다.
> * 이 유저가 구매를 주저하는 것으로 가정하고, 장바구니에 담긴 상품으로 리타겟팅을 시도해 볼 수 있습니다.
>
> #### <span id="analyzing-the-user-journey-for-campaign-optimization"></span>캠페인 최적화를 위한 유저 여정 분석
>
> * 여행 앱의 UA 매니저가 인스톨 및 인앱 이벤트 리포트를 다운로드하여 병합합니다.
> * 그런 다음 앱에서의 유저 여정을 보려면 앱스플라이어 ID로 데이터를 필터링하거나 집계합니다.
> * 그들은 앱스플라이어 ID로 식별된 특정 유저가 12개월 전에 앱을 다운로드하고 며칠 후에 항공편을 예약했다는 것을 발견했습니다.
> * 그 후, 해당 유저는 여러 항공편 상품을 살펴봤지만 예약을 하지 않았습니다. 더 자세히 조사하면서 UA 매니저는 동일한 패턴을 보이는 유저들을 더 많이 발견하고 심도 있게 분석하기로 결정합니다.
> * 그들은 이들 유저 대부분이 **광고 A**의 **캠페인 B**에서 **미디어 소스 C**에서 유입된 것을 발견했습니다. 이 광고와 캠페인은 특정 목적지로 여행을 가고 싶어 하는 유저를 타겟팅했습니다.
> * UA 매니저가 유저 여정을 분석하면 캠페인이 지나치게 협소하게 집중되어 사용자들이 앱에 충분히 참여하지 않았다는 결론에 이를 수 있습니다.

</Accordion>

<div id="feature-reports" />

## 기능 리포트

플랫폼에서 제공되는 추가 기능에 관한 리포트

* <Anchor target="_blank" href="/marketers/ko/docs/roi360-guide-ad-revenue-attribution#ad-revenue-raw-data">광고 수익</Anchor>
* <Anchor target="_blank" href="/marketers/ko/docs/incrementality-for-remarketing-overview#raw-data-reports">증분성</Anchor>
* <Anchor target="_blank" href="/marketers/ko/docs/skan-raw-data-reports">SKAdNetwork</Anchor>

<div id="postbacks" />

<Accordion title="포스트백">

애드 네트워크에 전송된 데이터 사본을 검토하기 위해 포스트백 리포트를 사용하세요. 예를 들어, 이를 사용하여 불일치 문제를 조사하세요. 이 리포트는 정보 제공 용도로 사용되며, 애드 네트워크와의 연동에는 필요하지 않습니다.

* 리포트에 포함된 내용:
  * 귀속된 미디어 소스로 전송된 포스트백의 사본입니다.
  * <Anchor target="_blank" href="/marketers/ko/docs/raw-data-field-dictionary">로데이터 필드</Anchor> 및 이 섹션에 설명된 추가 필드.
* 리포트에 포함되지 않는 내용:
  * SRN 인스톨.
  * 메타 광고, X 광고 및 Apple Search 광고와 관련된 인앱이벤트.
  * 속성 없는 파트너 포스트백. 파트너 또는 오가닉에 기인한 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">이벤트를 참조하세요</Anchor>.
  * 오가닉 사용자. 오가닉 인스톨에 관한 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#default-postbacks">정보를 참조하세요</Anchor>.
* 2021년 3월부터 필드는 네트워크의 고급 개인정보 설정에 따라 채워집니다. 고급 개인정보가 활성화되어 있으면 사용자 식별자와 같은 특정 필드는 제외됩니다. <Anchor target="_blank" href="/partners/ko/docs/advanced-privacy-guide-postback-macros-for-ad-networks#advanced-privacy-postback-specification">광고 네트워트에 대한 고급 개인정보 보호 포스트백 사양</Anchor>을 참조하십시오.
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_app-id-postbacks-v5">푸시 API로 포스트백 보고서 가져오기</Anchor>

<div id="postback-reports-available-via-the-export-data-page-and-pull-api" />

#### 포스트백 리포트(데이터 내보내기 페이지 및 Pull API 통해 제공)

| 리포트 주제 | 귀속된 미디어 소스로 전송된 이벤트 |
| --- | --- |
| 인스톨 | 논오가닉(UA) 인스톨 |
| 인앱 이벤트 | 논오가닉 인앱 이벤트 |
| 리타겟팅 전환 포스트백 | 리타겟팅(리인게이지먼트 및 리어트리뷰션) |
| 리타게팅 인앱 이벤트 | 리타게팅 인앱 이벤트 |

<div id="additional-fields-in-postback-reports" />

#### 포스트백 리포트의 추가 필드

| 필드 | 비고 |
| --- | --- |
| 포스트백 URL | 수익과 같은 일부 값이 해당 필드에 나타나지 않을 수 있지만, **포스트백** URL에서 이 데이터를 여전히 확인할 수 있습니다. |
| 포스트백 방법 |  |
| 포스트백 HTTP 응답 코드 | 200: 애드 네트워크에서 포스트백을 수신했음을 확인합니다. |
| 포스트백 오류 메시지 |  |

</Accordion>

<div id="protect360-fraud-and-validation-rules" />

<Accordion title="Protect360 프로드 및 유효성 검증 규칙">

* <Anchor target="_blank" href="/marketers/ko/docs/protect360-raw-data-reports">Protect360</Anchor> 및 <Anchor target="_blank" href="/marketers/ko/docs/implement-validation-rules-to-prevent-fraud#outcomes">유효성 검증 규칙</Anchor> 로데이터 리포트를 참조하십시오.
* 애드 네트워크 및 대행사가 Protect360 및 유효성 검증 보고서에 액세스하려면 광고주의 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#access-protect360-dashboard-raw-data">권한이 필요합니다.</Anchor>

**Protect360 액세스 권한을 통합 파트너에게 부여하려면:**

1. **협업** > **활성화된 연동**으로 이동합니다.
2. 통합 파트너를 선택하세요.
3. **권한** 탭에서 **Protect360 대시보드 및 로데이터를 API로 액세스** 옵션을 켭니다.
4. 인앱 이벤트(CPA) 대시보드에 액세스하려면 **집계된 인앱 이벤트 데이터 액세스**를 켜세요.

</Accordion>

<div id="see-also" />

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/aggregated-and-analytics-reporting-overview">집계 보고서 및 분석 도구</Anchor>

<div data-zendesk-anchors="raw-data-reporting%E2%80%94tools-and-reports=%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%A6%AC%ED%8F%AC%ED%8C%85%EB%8F%84%EA%B5%AC-%EB%B0%8F-%EB%A6%AC%ED%8F%AC%ED%8A%B8 h_01HE7SRDXQ9TR0CRB2JC9XCQE2=%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%A6%AC%ED%8F%AC%ED%8C%85%EB%8F%84%EA%B5%AC-%EB%B0%8F-%EB%A6%AC%ED%8F%AC%ED%8A%B8 h_01HE7SRDXQQJFMV9EJKPY34D00=%ED%8C%81 reporting-tools%E2%80%94characteristics-and-features=reporting-tools-characteristics-and-features h_01HE7SRDXQFJGMY05K1SV4TF63=reporting-tools-characteristics-and-features reporting-tools=%EB%A6%AC%ED%8F%AC%ED%8C%85-%EB%8F%84%EA%B5%AC h_01HE7SRDXQ647XRQ8QVMPGH43B=%EB%A6%AC%ED%8F%AC%ED%8C%85-%EB%8F%84%EA%B5%AC tool-limitations=%EB%8F%84%EA%B5%AC-%ED%95%9C%EA%B3%84 h_01HE7SRDXQWQAKR0G6CNKC5AMT=%EB%8F%84%EA%B5%AC-%ED%95%9C%EA%B3%84 integration-considerations=%EC%97%B0%EB%8F%99-%EA%B3%A0%EB%A0%A4-%EC%82%AC%ED%95%AD h_01HE7SRDXQN3HSMGAPBAX9S3MB=%EC%97%B0%EB%8F%99-%EA%B3%A0%EB%A0%A4-%EC%82%AC%ED%95%AD h_01HE7SRDXQRPD8MHC8M5916HTQ=report-fields user-journey-raw-data-field-groups=%EC%9C%A0%EC%A0%80-%EC%97%AC%EC%A0%95-%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%ED%95%84%EB%93%9C-%EA%B7%B8%EB%A3%B9 h_01HE7SRDXQMGQEG1QWGWEESQER=%EC%9C%A0%EC%A0%80-%EC%97%AC%EC%A0%95-%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%ED%95%84%EB%93%9C-%EA%B7%B8%EB%A3%B9 user-journey-reports=%EC%9C%A0%EC%A0%80-%EC%97%AC%EC%A0%95-%EB%A6%AC%ED%8F%AC%ED%8A%B8 h_01HE7SRDXQZ50WMKCMYHZM7D92=%EC%9C%A0%EC%A0%80-%EC%97%AC%EC%A0%95-%EB%A6%AC%ED%8F%AC%ED%8A%B8 h_01HE7SRDXQFN0P9QK8SKAZKVKP=user-journey-basics h_01HE7SRDXRS2B12Z67MYMH0QN9=user-journey-report-availability user-journey-reports::d286e1f5=%EC%9C%A0%EC%A0%80-%EC%97%AC%EC%A0%95-%EB%A6%AC%ED%8F%AC%ED%8A%B8-1 h_01HE7SRDXR7YQGWN4FNDXMNMX8=%EC%9C%A0%EC%A0%80-%EC%97%AC%EC%A0%95-%EB%A6%AC%ED%8F%AC%ED%8A%B8-1 h_01HE7SRDXRK6G27SDFK3CGDCRC=user-journey-report-descriptions clicks-and-impressions=%ED%81%B4%EB%A6%AD%EA%B3%BC-%EB%85%B8%EC%B6%9C h_01HE7SRDXRC9YKZ0P9ED0218SJ=%ED%81%B4%EB%A6%AD%EA%B3%BC-%EB%85%B8%EC%B6%9C installs-and-retargeting-conversions=%EC%9D%B8%EC%8A%A4%ED%86%A8-%EB%B0%8F-%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%EC%A0%84%ED%99%98 h_01HE7SRDXRN60XE5BSDQY28N71=%EC%9D%B8%EC%8A%A4%ED%86%A8-%EB%B0%8F-%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%EC%A0%84%ED%99%98 inapp-events=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8 h_01HE7SRDXR3ZT39EDNW4MVZZTX=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8 sessions=%EC%84%B8%EC%85%98 h_01HE7SRDXRY05XQCMZE6YPXGWQ=%EC%84%B8%EC%85%98 uninstalls=%EC%95%B1-%EC%82%AD%EC%A0%9C h_01HE7SRDXRA7ESDD4ME51WWBPR=%EC%95%B1-%EC%82%AD%EC%A0%9C h_01HE7SRDXRZYNFGK4CNP4VPAE0=user-journey-report-availability-per-tool ad-engagement-report-by-tool=%EB%8F%84%EA%B5%AC%EB%B3%84-%EA%B4%91%EA%B3%A0-%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8-%EB%A6%AC%ED%8F%AC%ED%8A%B8 h_01HE7SRDXR171M74HMQBZJ2E8R=%EB%8F%84%EA%B5%AC%EB%B3%84-%EA%B4%91%EA%B3%A0-%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8-%EB%A6%AC%ED%8F%AC%ED%8A%B8 user-acquisition-reports-by-tool=%EB%8F%84%EA%B5%AC%EB%B3%84-%EC%9C%A0%EC%A0%80-%EC%9C%A0%EC%9E%85-%EB%A6%AC%ED%8F%AC%ED%8A%B8 h_01HE7SRDXRMGEP5QB452ZKQ8X7=%EB%8F%84%EA%B5%AC%EB%B3%84-%EC%9C%A0%EC%A0%80-%EC%9C%A0%EC%9E%85-%EB%A6%AC%ED%8F%AC%ED%8A%B8 retargeting-raw-data-reports-by-tool=%EB%8F%84%EA%B5%AC%EB%B3%84-%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%A6%AC%ED%8F%AC%ED%8A%B8 h_01HE7SRDXRXR4J3HTMYW2P233Y=%EB%8F%84%EA%B5%AC%EB%B3%84-%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%A6%AC%ED%8F%AC%ED%8A%B8 h_01HE7SRDXRWW3JKNESSN2QA4DV=faq h_01HE7SRDXR61K28JGA8944D6HV=install-report-tips h_01HE7SRDXRKFR2WYGNF317CTRX=%EC%98%88%EC%8B%9C engaged-user%E2%80%94strong=%EC%B0%B8%EC%97%AC-%EC%9C%A0%EC%A0%80---%EA%B0%95%EB%A0%A5%ED%95%A8 h_01HE7SRDXRW0CWHGQV75VF66DC=%EC%B0%B8%EC%97%AC-%EC%9C%A0%EC%A0%80---%EA%B0%95%EB%A0%A5%ED%95%A8 engaged-user%E2%80%94weak=%EC%B0%B8%EC%97%AC-%EC%9C%A0%EC%A0%80---%EC%95%BD%ED%95%A8 h_01HE7SRDXRNMDZEJQ32665T14F=%EC%B0%B8%EC%97%AC-%EC%9C%A0%EC%A0%80---%EC%95%BD%ED%95%A8 analyzing-the-user-journey-for-campaign-optimization=%EC%BA%A0%ED%8E%98%EC%9D%B8-%EC%B5%9C%EC%A0%81%ED%99%94%EB%A5%BC-%EC%9C%84%ED%95%9C-%EC%9C%A0%EC%A0%80-%EC%97%AC%EC%A0%95-%EB%B6%84%EC%84%9D h_01HE7SRDXRRET0YN4Q8WYMENSR=%EC%BA%A0%ED%8E%98%EC%9D%B8-%EC%B5%9C%EC%A0%81%ED%99%94%EB%A5%BC-%EC%9C%84%ED%95%9C-%EC%9C%A0%EC%A0%80-%EC%97%AC%EC%A0%95-%EB%B6%84%EC%84%9D feature-reports=%EA%B8%B0%EB%8A%A5-%EB%A6%AC%ED%8F%AC%ED%8A%B8 h_01HE7SRDXSVAHKBYQK0C71K6AR=%EA%B8%B0%EB%8A%A5-%EB%A6%AC%ED%8F%AC%ED%8A%B8 h_01HE7SRDXSFWMVY61NBYFQ4XSM=postbacks postback-reports-available-via-the-export-data-page-and-pull-api=%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EB%A6%AC%ED%8F%AC%ED%8A%B8%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%82%B4%EB%B3%B4%EB%82%B4%EA%B8%B0-%ED%8E%98%EC%9D%B4%EC%A7%80-%EB%B0%8F-pull-api-%ED%86%B5%ED%95%B4-%EC%A0%9C%EA%B3%B5 h_01HE7SRDXS6T4M4CRQN0ZTJETR=%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EB%A6%AC%ED%8F%AC%ED%8A%B8%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%82%B4%EB%B3%B4%EB%82%B4%EA%B8%B0-%ED%8E%98%EC%9D%B4%EC%A7%80-%EB%B0%8F-pull-api-%ED%86%B5%ED%95%B4-%EC%A0%9C%EA%B3%B5 additional-fields-in-postback-reports=%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EB%A6%AC%ED%8F%AC%ED%8A%B8%EC%9D%98-%EC%B6%94%EA%B0%80-%ED%95%84%EB%93%9C h_01HE7SRDXSYBDG0H2QEYBFWSRH=%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EB%A6%AC%ED%8F%AC%ED%8A%B8%EC%9D%98-%EC%B6%94%EA%B0%80-%ED%95%84%EB%93%9C h_01HE7SRDXS8K4MB76WVBCBHASQ=protect360-fraud-and-validation-rules h_01HE7ST20N8ZBFNY2QXW5G44A1=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
