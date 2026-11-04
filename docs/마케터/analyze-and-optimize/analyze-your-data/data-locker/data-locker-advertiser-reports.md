---
title: 데이터 락커 광고주 리포트
metadata:
  keywords:
    - Advertisers
    - Premium Feature
    - Marketers
    - Data Locker
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Data Locker
  created_at: '2021-11-11T09:48:51Z'
  edited_at: '2026-10-14T10:40:16Z'
  id: 4410643856657
  locale: ko
  section: Data Locker
  section_id: 6550945728657
  url: https://support.appsflyer.com/hc/ko/articles/4410643856657
---
> **한눈에 보기:** 요약: 데이터 락커를 통해 사용 가능한 집약 데이터 리포트 및 로데이터 리포트들.

<div id="reports-available-via-data-locker-for-advertisers" />

## 광고주용 데이터 락커를 통해 사용 가능한 리포트들

<table><colgroup><col/><col/><col/></colgroup><thead><tr><th>데이터 유형</th><th>리포트 그룹</th><th>데이터 락커 구독 필수</th></tr></thead><tbody><tr><td>로데이터</td><td>사용자 여정 - 로데이터</td><td>예 (2)</td></tr><tr><td>로데이터</td><td>Protect360</td><td>예</td></tr><tr><td>로데이터</td><td>사람 기반 어트리뷰션(PBA) </td><td>아니요 </td></tr><tr><td>로데이터</td><td>증분성</td><td>아니요 </td></tr><tr><td>로데이터</td><td>SKAN</td><td>아니요(1)</td></tr><tr><td>로데이터</td><td>수익</td><td><p>광고 수익 단일 버전 보고서는 데이터 잠금 장치 구독이 필요합니다.</p><p>모든 다른 보고서는 ROI360 고급 패키지 구독이 필요합니다.</p></td></tr><tr><td>로데이터</td><td>CTV, PC, 콘솔 앱</td><td>예</td></tr><tr><td>통합 데이터</td><td>코호트 분석</td><td>아니요(1)</td></tr><tr><td>고급 집계</td><td>코호트 분석</td><td>아니요(1)</td></tr><tr><td>통합 데이터</td><td>광고소재 최적화</td><td><p>아니요(1)</p><p>창의적 최적화 프리미엄 구독 계획이 필요합니다.</p></td></tr><tr><td>통합 데이터</td><td>SSOT</td><td>아니요(1)</td></tr><tr><td colspan="3"><p>(1) 데이커 락커 구독이 없는 경우 <a href="./data-locker-for-marketers#storage-options" target="_blank">사용자가 소유한 스토리지</a>를 제공해야 합니다.</p><p>(2) 크로스 플랫폼 인게이지먼트 제외</p><p>(3) 데이터 잠금 장치 구독 또는 분석 API 제품군과 함께 사용할 수 있습니다.</p></td></tr></tbody></table>

<div id="data-freshness-explanations" />

<Accordion title="데이터 최신성 설명">

다음은 문서 본문에 언급된 데이터 최신성 용어에 대한 설명을 포함합니다.

| 용어 | 세부 정보 |
| --- | --- |
| 1-3시간 | <ul><li>리포트 준비 상태:<ul><li>95%의 리포트가 이벤트 발생 후 1시간 이내에 버킷에서 준비 및 제공됩니다.</li><li>보고서의 99%가 준비되고 이벤트 발생 후 3시간 이내에 버킷에서 사용할 수 있습니다.</li></ul></li></ul> |
| 매일 - 앱 삭제 | <ul><li>앱 삭제 데이터는 매일 준비됩니다.</li><li>보통 UTC 시간으로 10시-12시에 사용 가능합니다.</li><li>대부분 h=2 폴더에 기록됩니다. 즉, h=2 폴더에는 전날에 리포트된 앱 제거 데이터가 포함된다는 뜻입니다. 그러나 데이터는 이후 폴더에 기록될 수 있으므로 가져오기 프로세스에서는 앱 제거 폴더에 있는 모든 폴더의 데이터를 읽어야 합니다. 다시 말하면 h=1–24 및 h=late입니다. 예를 들어, 월요일에 발생한 데이터에 대한 리포트는 화요일 h=2 폴더에 있습니다. 이 데이터는 UTC 기준 화요일 06:00 이후에 사용할 수 있습니다.</li></ul> |
| 매일+1 | 광고 수익 데이터는 1일 후에 사용 가능합니다. 즉, 월요일에 생성된 데이터는 화요일 UTC 시간으로 20:00 이후 월요일 h=23 폴더에서 사용할 수 있다는 뜻입니다. <Anchor target="_blank" href="/marketers/ko/docs/roi360-guide-ad-revenue-attribution#data-freshness">광고 수익 데이터 최신성</Anchor> 참조 |

</Accordion>

<div id="raw-data-reports" />

## 로데이터(Raw data) 보고서

<div id="user-journey" />

<Accordion title="사용자 여정">

리포트 유형에 대한 설명은 <Anchor target="_blank" href="/marketers/ko/docs/raw-data-reporting-overview">사용자 여정 리포트</Anchor>를 참조하십시오.

| 카테고리 | 리포트 유형 (주제) | 데이터 최신성 | 오가닉/논오가닉 | 데이터 락커만의 고유 특징 |
| --- | --- | --- | --- | --- |
| 유저 유입 | 클릭 | 1-3시간 | 해당 없음 | ✓ |
| 리타겟팅 | 클릭 | 1-3시간 | 해당 없음 | ✓ |
| 유저 유입 | 노출 | 1-3시간 | 해당 없음 | ✓ |
| 리타겟팅 | 노출 | 1-3시간 | 해당 없음 | ✓ |
| 유저 유입 | 인스톨 | 1-3시간 | 둘 다 |  |
| 유저 유입 | 인앱 이벤트 | 1-3시간 | 둘 다 |  |
| 유저 유입 | 어트리뷰션된 광고 수익 | 매일+1 | 논오가닉 |  |
| 유저 유입 | 유기적 광고 수익 | 매일+1 | 오가닉 |  |
| 리타겟팅 | 리타겟팅 광고 수익 | 매일+1 | 논오가닉 |  |
| 리타겟팅 | 전환 | 1-3시간 | 논오가닉 |  |
| 리타겟팅 | 인앱 이벤트 | 1-3시간 | 논오가닉 |  |
| 리타겟팅 | 세션 | 1-3시간 | 둘 다 | ✓ |
| 유저 유입 | 세션 | 1-3시간 | 둘 다 | ✓ |
| 유저 유입 | 앱 삭제 | 매일 - 앱 삭제 | 논오가닉 |  |
| 유저 유입 | 오가닉 앱 삭제 | 매일 - 앱 삭제 | 오가닉 |  |
| 재설치 | 재설치 | 1-3시간 | 논오가닉 |  |
| 재설치 | 오가닉 앱 재설치 | 1-3시간 | 오가닉 |  |
| 유저 유입 | 크로스 플랫폼 인게이지먼트 | 시간별 | 둘 다 | ✓ |

</Accordion>

<div id="protect360" />

<Accordion title="Protect360">

<Anchor target="_blank" href="/marketers/ko/docs/protect360-raw-data-reports">Protect360 리포트 소개</Anchor> 참조

| 리포트 유형 (주제) | 데이터 최신성 |
| --- | --- |
| 차단된 인스톨 | 1-3시간 |
| 차단된 인앱 이벤트 | 1-3시간 |
| 차단된 클릭 | 1-3시간 |
| 사후 어트리뷰션 설치 | 일일<br /><br />각 날짜의 리포트에는 전날 리포트된 어트리뷰션 이후 인스톨이 포함됩니다. 예를 들어, 월요일에 발생한 데이터에 대한 리포트는 화요일 리포트에 있습니다. |

</Accordion>

<div id="peoplebased-attribution" />

<Accordion title="유저 중심 어트리뷰션">

**데이터 최신성**

전날(UTC) 종료 후 10-12시간 동안 사용 가능한 일별 데이터입니다. 예를 들어, 월요일에 수신한 데이터는 하루가 끝난 후에 처리되며 월요일 h=23 폴더에서 사용할 수 있습니다. 데이터는 화요일 12:00 UTC까지 이용 가능합니다.

**고려 사항**

* 계정의 모든 PBA 브랜드 번들의 데이터는 항상 앱 필터를 고려하지 않고 제공됩니다.
* 앱별 데이터 분리는 사용할 수 없습니다.

| 리포트 유형 (주제) |
| --- |
| <Anchor target="_blank" href="/marketers/ko/docs/pba-raw-data-reports#website-visits-and-website-events">웹 사이트 방문</Anchor> |
| <Anchor target="_blank" href="/marketers/ko/docs/pba-raw-data-reports#website-visits-and-website-events">웹 사이트 이벤트</Anchor> |
| <Anchor target="_blank" href="/marketers/ko/docs/pba-raw-data-reports#websiteassisted-installs::7e12586d">웹사이트-어시스트 인스톨</Anchor> |
| <Anchor target="_blank" href="/marketers/ko/docs/pba-raw-data-reports#conversion-paths">전환 경로</Anchor> |

</Accordion>

<div id="incrementality" />

<Accordion title="증분성">

<Anchor target="_blank" href="/marketers/ko/docs/incrementality-for-remarketing-overview#available-reports">증분 리포트</Anchor>를 참조하십시오.

</Accordion>

<div id="skan" />

<Accordion title="SKAN">

<Anchor target="_blank" href="/marketers/ko/docs/skan-raw-data-reports">SKAN 로데이터 리포트</Anchor> 소개

**데이터 최신성**

* 데이터는 앱스플라이어에서 포스트백을 수신한 다음 날에 이용하거나 API에서 앱스라이어에 리포트한 데이터를 이용할 수 있습니다.
* 데이터는 앱스플라이어가 데이터를 받은 날짜의 h=23 폴더에 포함됩니다. 예시: 예시: 월요일에 받은 포스트백은 그날이 종료된 후 처리됩니다. 처리가 완료되면 화요일 12:00 UTC까지 데이터가 월요일 h=23 폴더에서 사용 가능합니다.

| 리포트 유형 (주제) |
| --- |
| 포스트백 |
| 포스트백 복사(iOS에서 앱스플라이어로 직접 전송) |
| 인스톨 |
| 재다운로드 |
| 인앱이벤트 |
| SRN 광고 차원 |

</Accordion>

<div id="ad-revenue" />

<Accordion title="수익">

ROI360 수익 ETL 데이터 락커 보고서

<Anchor target="_blank" href="/marketers/ko/docs/roi360-guide-ad-revenue-attribution#ad-revenue-raw-data">광고 수익 로데이터</Anchor> 참조

</Accordion>

<div id="ctv" />

<Accordion title="CTV, PC 및 콘솔 플랫폼 데이터">

<Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-data-via-data-locker">데이터 락커를 통해 CTV, PC 및 콘솔 플랫폼 데이터</Anchor> 확인

</Accordion>

<div id="advanced-raw-data-reports-beta" />

## 고급 원시 데이터 보고서 (베타)

고급 보고서는 구조화되고 검증된 **AI 준비 데이터 세트**를 제공하도록 설계된 새로운 세대의 원시 데이터 보고서를 소개합니다. 이 보고서는 **첫 번째 참여부터 전환 및 설치 후 활동까지의 전체 사용자 여정을 단 3개의 보고서를 사용하여 수집하고 분석할 수 있도록 합니다.**  
타입 필드 **typed fields**, 정제된 필드 이름 **refined field naming**, 및 모든 데이터 세트에 걸쳐 일관된 스키마로 구축된 이 보고서는 명확성, 정확성 및 사용 용이성을 보장합니다. 통합 구조는 데이터 세트 간의 조인을 단순화하고 **ETL 및 다운스트림 처리 복잡성을 줄이며**, 고급 분석을 지원하고 필요에 따라 데이터를 처리할 수 있는 유연성을 제공합니다.

<div id="advanced-reports" />

<Accordion title="원시 참여 보고서">

원시 참여 보고서는 모바일 및 연결된 TV(CTV) 플랫폼에서 사용자 획득 및 리타겟팅 활동 전반에 걸쳐 클릭 및 노출 데이터를 통합합니다. 이 보고서는 광고와의 사용자 상호작용에 대한 통합된 뷰를 제공하여 퍼널 상단 성과에 대한 심층 분석을 가능하게 하고 마케터가 어떤 크리에이티브와 채널이 의미 있는 참여를 유도하는지 식별하는 데 도움을 줍니다. 또한 참여 수준에서 비용 및 도달 범위 최적화를 지원하여 마케팅 노출 및 트래픽 품질 평가를 위한 견고한 기반을 제공합니다.

| 카테고리 | 리포트 유형 (주제) | 데이터 최신성 | 데이터 락커만의 고유 특징 |
| --- | --- | --- | --- |
| 유저 유입(UA) 및 리타겟팅 가이드 | 클릭과 노출 | 1–24시간 | ✅ |

</Accordion>

<div id="conversion-report" />

<Accordion title="전환 보고서">

전환 보고서는 모바일 및 연결된 TV(CTV) 플랫폼 전반에 걸쳐 유기적 및 비유기적 소스를 포함한 모든 앱 설치에 대한 완전한 뷰를 제공합니다. 전환 데이터를 중앙 집중화함으로써 마케터는 단일화된 데이터 세트를 사용하여 포괄적인 성장 분석을 수행할 수 있습니다. 이 보고서를 사용하여 마케팅 성과를 정확하게 측정하고 최적화하십시오.

이 보고서를 사용하여 마케팅 성과를 정확하게 측정하십시오.

| 카테고리 | 리포트 유형 (주제) | 데이터 최신성 | 데이터 락커만의 고유 특징 |
| --- | --- | --- | --- |
| 유저 유입(UA) 및 리타겟팅 가이드 | 전환 | 1–24시간 | ✅ |

<div id="note" />

> 📘 **참고**
>
> 재설치는 이 보고서에 포함되지 않습니다.

</Accordion>

<div id="h_01K9CROSSPLATFORMREPORT" />

<Accordion title="최종 사용자 이벤트 보고서">

최종 사용자 이벤트 보고서는 모바일 및 CTV 플랫폼 전반에 걸쳐 세션, 구매, 등록 및 레벨 완료를 포함한 상세한 인앱 이벤트 데이터를 캡처합니다. 각 이벤트는 전체 귀속 컨텍스트로 풍부해져 사용자 행동, 유지 및 생애 가치를 상세히 분석할 수 있으며, 완전한 귀속 추적 가능성을 보장합니다.

| 카테고리 | 리포트 유형 (주제) | 데이터 최신성 | 데이터 락커만의 고유 특징 |
| --- | --- | --- | --- |
| 유저 유입(UA) 및 리타겟팅 가이드 | 최종 사용자 이벤트 | 1–24시간 | ✅ |

</Accordion>

<div id="aggregated-reports" />

## 종합 리포트

<div id="cohort-analytics" />

<Accordion title="코호트 분석">

**데이터 최신성**

리포트는 선행하는 날의 h=23에서 보통 10:00-12:00 UTC에 사용 가능합니다. 처리가 완료되면 화요일 12:00 UTC까지 데이터가 월요일 h=23 폴더에서 사용 가능합니다.

| 리포트 유형 (주제) |
| --- |
| <Anchor target="_blank" href="/marketers/ko/docs/cohort-analytics-via-data-locker">코호트 통합</Anchor> |
| <Anchor target="_blank" href="/marketers/ko/docs/cohort-analytics-via-data-locker">코호트 사용자 인입</Anchor> |
| <Anchor target="_blank" href="/marketers/ko/docs/cohort-analytics-via-data-locker">코호트 리타게팅</Anchor> |

</Accordion>

<div id="advanced-aggregated-reports" />

<Accordion title="고급 집계 보고서">

데이터 락커의 고급 집계 보고서에는 최적의 데이터 최신성, 정확성, 세분성 및 무제한 볼륨으로 집계된 데이터가 포함됩니다. <Anchor target="_blank" href="/marketers/ko/docs/advanced-aggregated-reports-in-data-locker">더 알아보기</Anchor>

</Accordion>

<div id="creative-optimization-etl" />

<Accordion title="광고소재 최적화">

크리에이티브 최적화 ETL 보고서는 데이터 분석가에게 크리에이티브 성과 분석에 필요한 모든 정보를 제공합니다. 모든 핵심성과지표(KPI), 상위 및 하위 퍼널 KPI, 기여 분석 데이터, 광고 소재 자산 데이터를 포함한 전체 자산 수준 성과 보고가 제공됩니다. <Anchor target="_blank" href="/marketers/ko/docs/creative-optimization-etl-reporting">더 알아보기</Anchor>

</Accordion>

<div data-zendesk-anchors="reports-available-via-data-locker-for-advertisers=%EA%B4%91%EA%B3%A0%EC%A3%BC%EC%9A%A9-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%9D%BD%EC%BB%A4%EB%A5%BC-%ED%86%B5%ED%95%B4-%EC%82%AC%EC%9A%A9-%EA%B0%80%EB%8A%A5%ED%95%9C-%EB%A6%AC%ED%8F%AC%ED%8A%B8%EB%93%A4 01H7WFZN6P1S49NYX8Q0W55P0B=%EA%B4%91%EA%B3%A0%EC%A3%BC%EC%9A%A9-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%9D%BD%EC%BB%A4%EB%A5%BC-%ED%86%B5%ED%95%B4-%EC%82%AC%EC%9A%A9-%EA%B0%80%EB%8A%A5%ED%95%9C-%EB%A6%AC%ED%8F%AC%ED%8A%B8%EB%93%A4 01H7WFZN6PQWASTMXM9V72QZER=data-freshness-explanations raw-data-reports=%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0raw-data-%EB%B3%B4%EA%B3%A0%EC%84%9C 01H7WFZN6P94YW1V79NT3HV5G4=%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0raw-data-%EB%B3%B4%EA%B3%A0%EC%84%9C 01H7WFZN6PD75S557PDB5PSFFR=user-journey 01H7WFZN6QY2GV69N464EE196M=protect360 01H7WFZN6QW72FDBTMW2ZD7NZQ=peoplebased-attribution 01H7WFZN6QZ1B7BS6E59RVAF30=incrementality 01H7WFZN6Q0P99DCFA7MZQTVSX=skan 01H7WFZN6Q717F9Z1HG38JVBG3=ad-revenue 01H7WFZN6QMJGSAJR00MHYJB6Z=ctv Unified%20raw-data-reports=%EA%B3%A0%EA%B8%89-%EC%9B%90%EC%8B%9C-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B3%A0%EC%84%9C-%EB%B2%A0%ED%83%80 h_01JX9T0PGE93JNJ3S4NDP0C2YW=%EA%B3%A0%EA%B8%89-%EC%9B%90%EC%8B%9C-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B3%A0%EC%84%9C-%EB%B2%A0%ED%83%80 h_01K85EE8DA4E8D4SVHYV2PE42E=conversion-report h_01K85EE8DAWY52B7RJQ33MJ59B=%EC%B0%B8%EA%B3%A0 cross-platform-end-user-events-report=h_01K9CROSSPLATFORMREPORT aggregated-reports=%EC%A2%85%ED%95%A9-%EB%A6%AC%ED%8F%AC%ED%8A%B8 01H7WFZN6Q90AT8N0VY5PKQ407=%EC%A2%85%ED%95%A9-%EB%A6%AC%ED%8F%AC%ED%8A%B8 01H7WFZN6QNKXTRM7G6VFANSZ7=cohort-analytics h_01J0K1MEKEEAQBXF1YRZTG8V0X=advanced-aggregated-reports h_01J0TQ88VNSFZJ27T3E2P3MVE6=creative-optimization-etl" />
