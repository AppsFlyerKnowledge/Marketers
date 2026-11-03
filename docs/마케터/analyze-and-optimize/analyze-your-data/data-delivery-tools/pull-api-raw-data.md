---
title: Pull API 로데이터
metadata:
  keywords:
    - Premium
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Raw Reports
  created_at: '2020-04-14T18:24:00Z'
  edited_at: '2026-10-14T10:32:02Z'
  id: 360007530258
  locale: ko
  section: Data delivery tools
  section_id: 6550995484561
  url: https://support.appsflyer.com/hc/ko/articles/360007530258
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **개요:** 이 API를 사용하여 CSV 파일 형식으로 원시 데이터 보고서를 받을 수 있습니다.

[altPullAPIRaw\_us-en.pngalt](https://support.appsflyer.com/hc/article_attachments/30996075641233)

## Pull API 로데이터

* Pull API를 사용하면 CSV 파일 형식으로 원시 데이터 보고서를 받을 수 있습니다. <Anchor target="_blank" href="/marketers/ko/docs/raw-data-reporting-overview">원시 데이터 보고서에 대해 자세히 알아보기</Anchor>
* 사용 가능한 옵션으로 필터링: 미디어 소스, 날짜 범위, 인앱 이벤트 이름, 지역.
* Pull API의 추가 기능은 다음과 같습니다.
  * 통화 선택
  * 시간대 선택

#### Pull API를 통해 사용할 수 있는 로데이터 리포트

<table><tbody><tr><th><span>보고서</span></th><th><span>설명</span></th><th><span>새로고침 빈도</span></th></tr><tr><td colspan="3"><strong>원시 데이터 보고서 (비유기적)</strong></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-installs-report-v5" target="_blank">설치</a></td><td><span>비유기적 설치를 기록합니다. 사용자가 앱을 처음 열 때 레코드가 생성됩니다.<br/></span></td><td><span>실시간</span></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-in-app-events-report-v5" target="_blank">인앱 이벤트</a></td><td><span>사용자가 수행한 이벤트를 기록합니다.<br/></span></td><td><span>실시간</span></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-uninstall-events-report-v5" target="_blank">삭제</a></td><td><span>사용자가 앱을 삭제한 경우를 기록합니다.<br/></span></td><td><span>일일</span></td></tr><tr><td><span><a href="https://dev.appsflyer.com/hc/reference/get_app-id-reinstalls-v5" target="_blank">재설치</a><br/></span></td><td><span>앱을 삭제한 후 UA 미디어 소스와 상호작용하고, 리어트리뷰션 기간 동안 앱을 다시 설치한 사용자를 기록합니다.</span></td><td><span>실시간</span></td></tr><tr><td colspan="3"> <span><strong>원시 데이터 보고서 (유기적)</strong></span><br/> </td></tr><tr><td><span><a href="https://dev.appsflyer.com/hc/reference/get_app-id-organic-installs-report-v5" target="_blank">유기적 설치</a><br/></span></td><td><span>사용자가 처음으로 앱을 열었을 때 기록합니다.<br/></span></td><td><span>연속</span></td></tr><tr><td><span><a href="https://dev.appsflyer.com/hc/reference/get_app-id-organic-in-app-events-report-v5" target="_blank">유기적 인앱 이벤트</a><br/></span></td><td><span>사용자가 수행한 이벤트에 대한 세부 정보를 기록합니다.<br/></span></td><td><span>연속</span></td></tr><tr><td><span><a href="https://dev.appsflyer.com/hc/reference/get_app-id-organic-uninstall-events-report-v5" target="_blank">유기적 삭제</a><br/></span></td><td><span>사용자가 앱을 삭제한 경우를 기록합니다.<br/></span></td><td><span>일일</span></td></tr><tr><td><span><a href="https://dev.appsflyer.com/hc/reference/get_app-id-reinstalls-organic-v5" target="_blank">유기적 재설치</a><br/></span></td><td><span>리타겟팅 미디어 소스로부터 발생한 광고 수익을 기록합니다.<br/></span></td><td><span>일일<br/></span></td></tr><tr><td colspan="3"><span><strong>리타게팅</strong></span></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-installs-retarget-v5">전환</a></td><td>리타겟팅 캠페인 참여 후 사용자가 앱을 실행한 기록입니다.</td><td>실시간</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-in-app-events-retarget-v5">인앱 이벤트</a></td><td>리인게이지먼트 기간 동안 사용자가 수행한 인앱 이벤트입니다.</td><td>실시간</td></tr><tr><td colspan="3"> <span><strong>광고 수익 원시 데이터</strong></span><br/> </td></tr><tr><td> <a href="https://dev.appsflyer.com/hc/reference/get_app-id-ad-revenue-raw-v5" target="_blank">어트리뷰션된 광고 수익</a><a href="https://dev.appsflyer.com/hc/reference/get_app-id-ad-revenue-raw-v5"><br/> </a> </td><td>미디어 소스로 어트리뷰트한 사용자의 광고 수익을 기록합니다.</td><td>일일</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-ad-revenue-organic-raw-v5" target="_blank">유기적 광고 수익</a></td><td>미디어 소스에 어트리뷰트되지 않은 사용자의 광고 수익을 기록합니다.</td><td>일일</td></tr><tr><td colspan="3"><span><strong>Protect360 부정행위 방지</strong></span></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-blocked-installs-report-v5" target="_blank">설치</a></td><td>사기로 식별되어 미디어 소스에 어트리뷰트되지 않은 인스톨을 기록합니다.</td><td><span>실시간</span></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-detection-v5" target="_blank">사후 어트리뷰션 설치</a></td><td>부정 설치로 기록된 인앱 이벤트이므로 어트리뷰트되지 않습니다.</td><td>실시간</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-blocked-in-app-events-report-v5" target="_blank">인앱 이벤트</a></td><td>Protect360에서 사기로 식별된 인앱이벤트를 기록합니다.</td><td>일일</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-fraud-post-inapps-v5" target="_blank">사후 어트리뷰션 인앱 이벤트</a></td><td>인스톨 자체와 상관없이 미디어 소스에 어트리뷰트되거나 사기로 판단된 후 사기로 식별된 인스톨에 대한 인앱이벤트를 기록합니다.</td><td>일일</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-blocked-clicks-report-v5" target="_blank">클릭</a></td><td>Protect360에 의해 차단된 사용자가 수행한 클릭을 기록합니다.</td><td>일일</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-blocked-install-postbacks-v5" target="_blank">차단된 설치 포스트백</a></td><td>인스톨이 차단된 미디어 소스로 전송된 포스트백 사본을 기록합니다.</td><td>실시간</td></tr><tr><td colspan="3"><strong>포스트백</strong></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-postbacks-v5" target="_blank">설치 포스트백</a></td><td>사용자가 앱을 처음 열 때 생성된 인스톨 이벤트를 기록합니다.</td><td>일일</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-in-app-events-postbacks-v5" target="_blank">인앱 이벤트 포스트백</a></td><td>미디어 소스로 전송된 인앱이벤트 포스트백을 기록합니다.</td><td>일일</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-retarget-in-app-events-postbacks-v5" target="_blank">리타게팅 인앱 이벤트 포스트백</a></td><td>리인게이지먼트 기간 동안 사용자가 수행한 인앱 이벤트를 기록합니다.</td><td>실시간</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-retarget-install-postbacks-v5" target="_blank">리타겟팅 전환 포스트백</a></td><td>리인게이지먼트 기간 동안 사용자가 수행한 인앱 이벤트를 기록합니다.</td><td>실시간</td></tr></tbody></table>

<div id="using-pull-api-raw-data" />

<Accordion title="Pull API 로데이터 사용하기">

**Pull API 원시 데이터 사용법**:

1. ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) API 토큰을 받으세요. 관리자가 토큰을 받아야 합니다.
2. 인증 헤더에 사용할 API 토큰을 귀사의 개발자에게 제공하세요.
3. 다음 절에 설명한 데 따라 개발자에게 API 호출을 할 때 입력할 파라미터를 제공합니다. 파라미터는 리포트의 중점 사항, 구성 방법을 결정하고 리포팅 기간을 제공합니다.
4. 개발자에게 개발자 허브에서 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-5">Pull API 원시 데이터 지침</Anchor>을 따르라고 알려주세요.

#### 파라미터

| 파라미터 | 설명 |
| --- | --- |
| 부터 | <ul><li>날짜 범위는 과  파라미터로 구성되어 있습니다. 날짜는 활동 날짜와 관련이 있습니다.</li><li>형식: , , 또는  **참고**: 공간은 여기에 표시된 대로 인코딩되어야 합니다`from=2020-04-01%2001:00:00` - 보통 브라우저는 공간을 인코딩합니다.</li><li>예: 2010-01-01 또는 2010-01-01 20:15 (로데이터 보고서에 사용 가능한 시간 및 분 파라미터).</li></ul> |
| 부터까지 | 종료일. `from``from`에 관해서는 |
| media\_source | `media_source`: 특정 미디어 소스로 호출을 제한(필터링)합니다.<br /><br />및  파라미터를 다음과 같이 설정합니다.<ul><li>Meta 광고의 경우 category 및 media source를 *facebook*으로 설정합니다.</li><li>X 광고의 경우 category 및 media source를 *twitter*로 설정합니다.</li><li>기타 모든 미디어 소스의 경우 category를 *standard*로, media source를 미디어 소스의 이름으로 설정합니다.</li></ul><ul><li>예시</li></ul> |
| maximum\_rows | 단일 API 호출에 의해 반환되는 최대 행 수입니다.<ul><li>[기본값] 값이 전송되지 않으면 최대 20만 행</li><li>200000: 최대 20만 행이 반환됩니다.</li><li>1000000: 최대 1백만 행이 반환됩니다.</li><li>예시:  최대 1백만 행을 허용합니다.</li></ul> |
| 이벤트 이름 | 지정된 이벤트로 인앱 이벤트를 필터링합니다. 여러 이벤트를 선택하려면 쉼표로 구분된 목록을 사용하십시오.<br /><br />**예시**: |
| 재귀 | 리타게팅 어트리뷰션 데이터를 설정합니다.<ul><li>[기본값] false인 경우, 사용자 유입 데이터(UA) 캠페인이 반환됩니다.</li><li>true인 경우, 리타게팅 어트리뷰션 데이터가 반환됩니다.</li><li>**예시**:</li></ul> |
| 추가 필드 | 기본 필드 이외에 더욱 다양한 필드를 얻으려면<br /><br />**예시**: |
| 통화 | 수익 및 비용의 통화<ul><li>[기본값] 매개변수를 전송하지 않으면 USD로 데이터가 반환됩니다. 즉, 아무 조치를 취하지 않으면 결과는 USD로 반환됩니다.</li><li>전송하면 <Anchor target="_blank" href="/marketers/ko/docs/app-settings#localization-time-zone">앱별</Anchor> 통화가 반영됩니다. <Anchor target="_blank" href="/marketers/ko/docs/app-settings#localization-time-zone">앱 설정에서 지정한 통화를 의미합니다.</Anchor></li></ul>**예시**: 앱별 통화가 EUR이면 `currency=preferred`을 전송해 EUR로 반환됩니다. |
| 시간대 | [기본값] UTC를 사용하여 데이터가 반환됩니다.<ul><li><Anchor target="_blank" href="/marketers/ko/docs/app-settings#localization-time-zone">앱별</Anchor> 시간대의 데이터로 표시하려면, 본 섹션에 나오는 <Anchor target="_blank" href="/marketers/ko/docs/app-settings#localization-time-zone">을 호출에 추가하세요.</Anchor></li></ul><ul><li>`timezone=[Numerical value]`</li><li>예: 시간대가 UTC+10:00일 경우 **참고를 사용하세요. ,** , `:`는 인코딩이 필요합니다. 예: +10:00는 `%2B10%3A00`(으)로 인코딩됩니다.</li></ul> |
| 지리적 위치 | 국가 코드를 기준으로 데이터를 필터링합니다.<br /><br />제약: API 호출마다 하나의 국가 코드 필터만 적용 가능합니다.<br /><br />예시: |
| 설치 시간 시작 | <ul><li>날짜 범위는 과  파라미터로 구성되어 있습니다. 날짜는 활동 날짜와 관련이 있습니다.</li><li>형식:</li><li>예: 2010-01-01</li></ul> |
| 설치 시간 종료 | 종료일. 에 관해서는 |
| 에이전시 | 특정 에이전시에 한해서만 필터링합니다. |

</Accordion>

<div id="protect360-fields" />

<Accordion title="Protect360 필드">

<Anchor target="_blank" href="/marketers/ko/docs/protect360-raw-data-reports#postattribution-reports">Protect360 로데이터 가이드 참조</Anchor>

</Accordion>

<div id="time-frame-fields" />

<Accordion title="시간 기간 필드">

API 결과가 최대값을 초과하면, 시간과 분을 기준으로 보고서를 나눕니다. 다음 사항을 적용하세요:

* **시작**／**종료:** **yyyy-mm-dd hh:mm**
* **에서:** 
  * 날짜만 = 선택한 날짜의 시작 시각(00:00)부터
  * 날짜 및 시간 = 00:00부터 포함하여
* 파라미터 **종료:** 
  * 날짜만 = 선택한 날짜의 종료 시각(24:00)까지
  * 날짜 및 시간 = 표시된 시간까지, 그러나 이 시간을 포함하지 않음

**예:** 앱 소유자는 모든 소스에서 하루 130만 건 설치를 달성합니다. 1M 행 제한을 극복하기 위해 앱 소유자는 하루를 두 개의 12시간 URI 호출로 나눕니다. 하단 표에서 옵션을 확인하세요.

<table><tbody><tr><th>API 호출</th><th>시작 </th><th>종료 </th></tr><tr><td><strong>첫 번째 API 호출</strong> </td><td><p><span><strong>시작</strong>=yyyy-mm-dd</span></p><p><span><strong>예시:</strong></span></p><ul><li><span><strong>시작</strong>=</span></li><li><span>이 날짜의 하루 시작 시각인 00:00에 시작됩니다.</span></li></ul></td><td><p><span><strong>종료</strong>=yyy</span><span>y-mm-dd 12:00</span></p><p><strong>예시:</strong> </p><ul><li><span><strong>종료</strong> =</span></li><li> <span>12:00이 아닌 11:59:59까지 계속됩니다.</span><span> </span> </li></ul></td></tr><tr><td><p><strong>옵션 A: <strong><strong>두 번째 API 호출</strong></strong></strong> </p><p><span><strong>예시:</strong></span><span> </span></p><p><span><kbd><kbd></kbd></kbd></span></p><ul><li><span>2019년 12월 29일 정오부터 시작됩니다.</span></li><li><span>2019년 12월 29일 자정까지 종료됩니다.</span></li></ul></td><td> <p><span><strong>시작</strong>=yyyy-mm-dd 12:00</span></p><p><strong>예시:</strong> </p><ul><li> <strong>시작</strong>=<span></span> </li><li><span>12:00부터 시작하여 포함됩니다.</span></li></ul></td><td><p><span> </span></p><p><span><strong>시작</strong>=yyy</span><span>y-mm-dd </span></p><p><span><strong>예시:</strong> </span></p><ul><li><span><strong>종료</strong> =</span></li><li><span>자정에 종료됩니다.</span></li></ul><p><span> </span></p></td></tr><tr><td><strong>옵션 B: 두 번째 API 호출</strong></td><td><p><span><strong>시작</strong>=yyyy-mm-dd 12:00</span></p><p><strong>예시:</strong> </p><ul><li> <strong>시작</strong>=<span></span> </li><li><span>12:00부터 시작하여 포함됩니다.</span></li></ul></td><td><p><span><strong>시작</strong>=yyyy-mm-dd+1 00:00</span>까지</p><p><span><strong>+1</strong> = 다음 날 00:00</span></p><p><strong>예시:</strong> </p><ul><li><span><strong>종료=</strong></span></li><li>12월 30일이 되기 전에 종료됨을 의미합니다.</li></ul></td></tr><tr><td colspan="3"><p><span><strong>참고:</strong> 결과가 동일하므로 옵션 A 또는 B를 사용하세요. </span></p></td></tr></tbody></table>

</Accordion>

<div id="additional-fields" />

<Accordion title="추가 필드">

추가 리포트 필드는 기본 필드 목록에 추가되지 않으므로 새 필드가 기존 가져오기 및 수집 프로세스에 영향을 주지 않습니다. `additional_fields` 매개변수를 사용해 기본이 아닌 필드를 얻습니다.

* 필드는 한 번만 기재합니다.
* <Anchor target="_blank" href="/marketers/ko/docs/raw-data-field-dictionary">가능한 필드 목록</Anchor>을 참고하세요.
* 예시:

</Accordion>

<div id="default-fields" />

<Accordion title="기본 필드">

| 기본 Pull API 필드 |
| --- |
| 속성 터치 유형 |
| Attributed Touch Time |
| 설치 시간 |
| Event Time |
| 이벤트 이름 |
| 이벤트 값 |
| 이벤트 수익 |
| Event Revenue Currency |
| 이벤트 수익 USD |
| Event Source |
| Is Receipt Validated |
| 파트너 |
| 미디어 소스 |
| 채널 |
| 키워드 |
| 캠페인 |
| 캠페인 ID |
| 광고세트 |
| 광고세트 ID |
| Ad |
| 광고 ID |
| 광고 타입 |
| 사이트 ID |
| 하위 사이트 ID |
| Sub Param 1 |
| 부 매개변수 2 |
| Sub Param 3 |
| Sub Param 4 |
| 부 매개변수 5 |
| 비용 모델 |
| 비용 값 |
| 비용 통화 |
| 기여자 1 파트너 |
| Contributor 1 Media Source |
| Contributor 1 Campaign |
| Contributor 1 Touch Type |
| Contributor 1 Touch Time |
| Contributor 2 Partner |
| 기여자 2 미디어 소스 |
| Contributor 2 Campaign |
| Contributor 2 Touch Type |
| 기여자 2 터치 시간 |
| 기여자 3 파트너 |
| Contributor 3 Media Source |
| Contributor 3 Campaign |
| Contributor 3 Touch Type |
| Contributor 3 Touch Time |
| 지역 |
| 국가 코드 |
| 주 |
| 도시 |
| Postal Code |
| DMA |
| IP |
| WIFI |
| 운영자 |
| 통신사 |
| 언어 |
| 앱스플라이어 ID |
| 광고 ID |
| IDFA |
| 안드로이드 ID |
| Customer User ID |
| IMEI |
| IDFV |
| 플랫폼 |
| 장치 유형 |
| OS 버전 |
| App Version |
| SDK 버전 |
| 앱 ID |
| 앱 이름 |
| 번들 ID |
| 리타겟팅 여부 |
| 리타겟팅 전환 유형 |
| Attribution Lookback |
| 재참여 기간 |
| Is Primary Attribution |
| 사용자 에이전트 |
| HTTP 리퍼러 |
| 원래 URL |

</Accordion>

## 추가 정보

<div id="traits-and-limitations" />

<Accordion title="특성 및 한계">

| 특성 | 설명 |
| --- | --- |
| API 토큰 유형 요구됨 | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)<Anchor target="_blank" href="/marketers/ko/docs/managing-appsflyer-tokens">V2.0 토큰</Anchor> |
| 광고 네트워크 액세스 | 아니요 |
| 에이전시 액세스 | 예 |
| 에이전시 투명성 | 네. 그러나 에이전시 필터와 미디어 소스 필터를 동시에 사용할 경우, 미디어 소스 필터는 투명하지 않은 에이전시에는 효과가 없습니다. 이는 투명하지 않은 에이전시의 경우, 필터링된 미디어 소스 데이터뿐만 아니라 모든 데이터가 포함됨을 의미합니다. |
| 앱별 통화 | 예 |
| 앱별 시간대 | 예 |
| 데이터 최신성 | <ul><li>개요 대시보드에 있는 데이터의 가용성과 동등합니다.</li><li>몇 시간 지연을 가지고 업데이트된 리포트:<ul><li>오가닉 인앱 이벤트</li></ul></li><li>보고서는 매일 업데이트됩니다:<ul><li>앱 삭제</li><li>사후 어트리뷰션 인앱 이벤트</li><li>광고 수익</li></ul></li></ul> |
| 과거 데이터 | 네.  <Anchor target="_blank" href="/marketers/ko/docs/user-level-data-retention">보존</Anchor> 및 <Anchor target="_blank" href="/marketers/ko/docs/report-generation-quotas-rate-limitations">요금 제한</Anchor> 정책에 따라. |
| 논오가닉 데이터 | 예 |
| 오가닉 데이터 | 예 |
| 콜 수 제한 | <Anchor target="_blank" href="/marketers/ko/docs/report-generation-quotas-rate-limitations">raw data</Anchor>를 위한 API 제한 사항. |
| 사이즈 제한 | <ul><li>API 호출은 최대 20만/1백만 행을 반환합니다.</li><li>리포트에 정확히 20만/1백만 개의 행이 있는 경우, 초과되어 누락된 행이 있다고 가정하십시오.</li><li>최대 행 수를 선택하려면 maximum\_rows 파라미터를 사용하십시오.</li><li>시간을 포함한 from/to 파라미터를 사용하여 API 호출을 여러번 발송하십시오.</li></ul> |
| 설치 날짜 시작 및 종료 | 설치 날짜 범위는 활동 날짜 범위보다 이전이어야 합니다. |

</Accordion>

<div id="troubleshooting" />

<Accordion title="문제 해결">

| 증상/메시지 | 해결 방안 |
| --- | --- |
| 리포트에 선택한 시간 범위에 따라 예상된 데이터가 포함되어 있지 않거나 원본 데이터 리포트와 집계 데이터 리포트 간에 불일치가 있습니다. | `timezone`매개변수를 설정했는지 확인하십시오. 설정하지 않으면 앱 시간대가 아닌 UTC로 데이터가 전송됩니다. |

</Accordion>

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">적절한 데이터 전달 도구\/리포팅 API 선택하기</Anchor>

<div data-zendesk-anchors="pull-api-raw-data=pull-api-%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0 h_01HE7S6WDVJD2XFW498P8FPY7W=pull-api-%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0 aggregate-performance-reports-available-via-pull-api=pull-api%EB%A5%BC-%ED%86%B5%ED%95%B4-%EC%82%AC%EC%9A%A9%ED%95%A0-%EC%88%98-%EC%9E%88%EB%8A%94-%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%A6%AC%ED%8F%AC%ED%8A%B8 h_01HE7S6WDV59VTP6Z4X790QDRD=pull-api%EB%A5%BC-%ED%86%B5%ED%95%B4-%EC%82%AC%EC%9A%A9%ED%95%A0-%EC%88%98-%EC%9E%88%EB%8A%94-%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%A6%AC%ED%8F%AC%ED%8A%B8 h_01HE7S6WDVYJ5MAK04VWB4MF6A=using-pull-api-raw-data parameters=%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 h_01HE7S6WDVF8T4719HWDJH8JN1=%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 h_01HE7S6WDVGSS0F116ZB6QVG1N=protect360-fields h_01HE7S6WDVP47A3Q8J7NPH54T5=time-frame-fields h_01HE7S6WDWZ8FR6GRJ40B4CJAV=additional-fields h_01HE7S6WDWMXYF0RHYPF058A9K=default-fields additional-information=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01HE7S6WDW9V8XC3CJ0F96EHN0=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01HE7S6WDWV87YVJMN76STX7A1=traits-and-limitations h_01HE7S6WDWMZPPTR41VHJQ8MWC=troubleshooting h_01HE7S8S8QCSKRA62A2HVK2MYJ=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
