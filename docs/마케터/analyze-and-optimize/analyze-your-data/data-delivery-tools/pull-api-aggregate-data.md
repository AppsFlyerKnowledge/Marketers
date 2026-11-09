---
title: Pull API 집약형 데이터
metadata:
  keywords:
    - Performance
    - raw data
    - Pull API
    - Reports
    - API
    - Parameters
    - API Policy
    - Advertisers
    - facebook rawdata
    - facebook raw data
    - Developers
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Raw Reports
  created_at: '2013-04-24T15:08:25Z'
  edited_at: '2026-10-14T10:40:04Z'
  id: 207034346
  locale: ko
  section: Data delivery tools
  section_id: 6550995484561
  url: https://support.appsflyer.com/hc/ko/articles/207034346
---
> **한눈에 보기:** 요약: 이 Pull API를 사용하여 CSV 파일에서 앱스플라이어 집약형 리포트를 가져옵니다.

<Image align="center" alt="PullAPIAverage_us-en.png" src="https://files.readme.io/fb9be34d49394086b37e71d2553d6f926829928a3e1f6cd2ec3e95943ecaa503-360008811078.png" />

<div id="looking-for-pull-api-raw-data" />

> 👍 **Pull API 로데이터를 찾고 계신가요?**
>
> <Anchor target="_blank" href="/marketers/ko/docs/pull-api-raw-data">여기</Anchor>에서 자세히 알아보세요.

<div id="pull-api-aggregate-data" />

## Pull API 집약형 데이터

* Pull API를 사용하면 유저 인입(UA) 및 리타게팅을 위한 집약형 데이터 리포트를 CSV 파일로 가져올 수 있습니다.
* <Anchor target="_blank" href="/marketers/ko/docs/about-data-freshness-and-timezone-support#data-freshness-rates-and-timezone-support">데이터 최신성</Anchor>은 데이터 내보내기 페이지 및 개요 대시보드 페이지에서 동일한 리포트와 같습니다. 비용 데이터를 제공하는 파트너에 따라 몇 시간의 지연으로 비용이 업데이트될 수 있습니다.
* 사용 가능한 옵션으로 필터링:
* Pull API의 추가 기능은 다음과 같습니다.
  * 어트리뷰션 터치 유형 추가
  * 시간대 선택

<div id="aggregate-performance-reports-available-via-pull-api" />

#### Pull API를 통해 사용 가능한 집약형 성과 리포트

<table><tbody><tr><th>카테고리</th><th> UA</th><th>리타게팅\*</th></tr><tr><td>파트너 (미디어 소스)</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><p>파트너 - 날짜별</p></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><p>일일</p></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><p>지역</p></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><p>지역별 날짜별 리포트</p></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td colspan="3"></td></tr></tbody></table>

<div id="using-pull-api-aggregate-data" />

<Accordion title="Pull API 집약형 데이터 사용">

**Pull API 집약형 데이터 사용 방법**:

1. ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) API 토큰을 받으세요. 관리자가 토큰을 받아야 합니다.
2. 인증 헤더에 사용할 API 토큰을 귀사의 개발자에게 제공하세요.
3. 다음 절에 설명한 데 따라 개발자에게 API 호출을 할 때 입력할 [파라미터](/docs/pull-api-aggregate-data#parameters)를 제공합니다. 파라미터는 리포트의 중점 사항, 구성 방법을 결정하고 리포팅 기간을 제공합니다.
4. 개발자에게 개발자 허브의 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-11">Pull API 집약형 데이터 지침</Anchor>을 따르도록 합니다.

</Accordion>

<div id="parameters" />

<Accordion title="파라미터">

| 파라미터 | 설명 |
| --- | --- |
| app\_id | 애플리케이션 ID |
| 부터 | <ul><li>날짜 범위는 과  파라미터로 구성되어 있습니다.</li><li>형식</li><li>예: 2010-01-01</li></ul> |
| 부터까지 | 종료일. `from` `from`에 관해서는 |
| media\_source | 특정 미디어 소스로 제한 (필터)하는데 사용합니다.<ul><li>예시:`media_source=facebook`</li></ul> |
| attribution\_touch\_type | 이 파라미터를 다음 예시처럼 설정하여 [뷰-쓰루 어트리뷰션 (view-through attribution, VTA)](/docs/pull-api-aggregate-data) KPI를 확인합니다.<br /><br />예: `attribution_touch_type=impression`<br /><br />클릭 수, 노출 수 및 비용 API와 같은 일부 VTA KPI에는 해당하는 값이 없고, 대신 N/A 값이 표시됩니다. |
| 통화 | 수익과 비용의 통화.<br /><br />Pull API 종합 리포트는 항상 앱 별 통화를 사용합니다. |
| 재귀 | 리타게팅 전환 데이터 얻기.<ul><li>[기본값] false인 경우, 사용자 유입 데이터(UA) 캠페인이 반환됩니다.</li><li>참인 경우 리타게팅 전환이 반환됩니다.</li><li>**예시**:</li></ul> |
| 시간대 | [기본값] UTC를 사용하여 데이터가 반환됩니다.<ul><li>템플릿 URI는 timezone 파라미터가 앱 별로 설정된 시간대값으로 설정되어 채워집니다.</li><li>[기본값] 파라미터가 전송되지 않으면, UTC를 기반으로 데이터가 반환됩니다.</li></ul>시간대 선택 관련 참고 사항<ul><li>Joda-Time 시간대 형식은 서머 타임(daylight saving time)을 반영합니다.</li><li>선택한 시간대로 데이터를 가져오는 것은 앱 설정에서 시간대를 설정한 날짜 다음부터만 사용할 수 있습니다. 시간대 설정 변경 이전의 데이터는 UTC 시간대를 사용합니다.</li></ul> |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="특징 및 제약 사항">

| 특성 | 설명 |
| --- | --- |
| API 토큰 유형 요구됨 | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)<Anchor target="_blank" href="/marketers/ko/docs/managing-appsflyer-tokens">V2.0 토큰</Anchor> |
| 광고 네트워크 액세스 | N |
| 에이전시 액세스 | Y |
| 에이전시 투명성 | Y |
| 앱별 통화 | Y |
| 앱별 시간대 | Y |
| 비용 | 비용 데이터는 UA 캠페인용입니다. 캠페인(인스톨이 없는 캠페인)을 리타게팅하거나 비활성화하기 위한 것이 아닙니다. |
| 데이터 최신성 | <Anchor target="_blank" href="/marketers/ko/docs/about-data-freshness-and-timezone-support#continuous-aka-realtime">연속</Anchor> |
| 과거 데이터 | 5년 |
| 논오가닉 데이터 | Y |
| 오가닉 데이터 | Y |
| 콜 제한 | <Anchor target="_blank" href="/marketers/ko/docs/report-generation-quotas-rate-limitations">제한 사항</Anchor> |
| 사이즈 제한 | <ul><li>API 호출은 최대 20만 행을 반환합니다.<ul><li>리포트에 정확히 20만 개의 행이 있는 경우, 초과되어 누락된 행이 있다고 가정하십시오.</li><li>시간을 포함한 from/to 파라미터를 사용하여 API 호출을 여러번 발송하십시오.</li></ul></li></ul> |
| 캠페인 이름 변경 | Pull API 리포트는 캠페인 이름 변경 기능을 지원하지 않습니다. |

</Accordion>

<div id="see-also" />

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/aggregated-and-analytics-reporting-overview">집약형 리포트 설명 및 예시</Anchor>
> * <Anchor target="_blank" href="/marketers/ko/docs/aggregated-and-analytics-reporting-overview">집약형 데이터를 위한 올바른 데이터 전달 도구 선택</Anchor>

<div data-zendesk-anchors="h_01HE0YP82966QHRAEW979ABCTP=pull-api-%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%A5%BC-%EC%B0%BE%EA%B3%A0-%EA%B3%84%EC%8B%A0%EA%B0%80%EC%9A%94 pull-api-aggregate-data=pull-api-%EC%A7%91%EC%95%BD%ED%98%95-%EB%8D%B0%EC%9D%B4%ED%84%B0 h_01HE0YP829WD5TDFHTPYAV30QN=pull-api-%EC%A7%91%EC%95%BD%ED%98%95-%EB%8D%B0%EC%9D%B4%ED%84%B0 aggregate-performance-reports-available-via-pull-api=pull-api%EB%A5%BC-%ED%86%B5%ED%95%B4-%EC%82%AC%EC%9A%A9-%EA%B0%80%EB%8A%A5%ED%95%9C-%EC%A7%91%EC%95%BD%ED%98%95-%EC%84%B1%EA%B3%BC-%EB%A6%AC%ED%8F%AC%ED%8A%B8 h_01HE0YP829EQ7N6CST352X917H=pull-api%EB%A5%BC-%ED%86%B5%ED%95%B4-%EC%82%AC%EC%9A%A9-%EA%B0%80%EB%8A%A5%ED%95%9C-%EC%A7%91%EC%95%BD%ED%98%95-%EC%84%B1%EA%B3%BC-%EB%A6%AC%ED%8F%AC%ED%8A%B8 h_01HE0YP82954F1ACVR2K4AFD5W=using-pull-api-aggregate-data h_01HE0YP8292131Q2561A4E1GYZ=parameters h_01HE0YP829ZPJAPHPDR9H4HMRT=traits-and-limitations h_01HE0Y2KTXS06WHN57MQ91AD09=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
