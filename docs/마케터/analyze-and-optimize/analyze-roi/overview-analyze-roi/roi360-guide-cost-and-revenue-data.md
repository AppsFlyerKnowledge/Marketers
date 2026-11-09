---
title: ROI360—비용 및 수익 데이터
metadata:
  keywords:
    - cost
    - Advertisers
    - Premium
    - Marketers
    - revenue
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2022-11-10T13:52:03Z'
  edited_at: '2026-10-14T10:40:32Z'
  id: 10515748254609
  locale: ko
  section: Overview
  section_id: 15173289016593
  url: https://support.appsflyer.com/hc/ko/articles/10515748254609
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **한눈에 보기**: 비용 및 수익 데이터를 가져와 총 ROI와 ROAS를 파악할 수 있습니다.

<Image align="center" alt="M_emptyState.png" src="https://files.readme.io/5eec5be77bf0b72afdd95b1957642cc67ba509000bc756ac68d87da5e96ed08e-11832563913489.png" />

<div id="overview" />

## 개요

ROI360은 가장 정확한 데이터를 최대한 빨리 제공하는 고유한 비용 및 수익 리포트 도구 모음입니다.

비용과 수익 인사이트를 결합하면 광고 투자수익(ROAS)과 투자수익(ROI)을 완벽하게 파악할 수 있습니다.

<div id="cost-tools" />

### 비용 도구

이전에 Xpend로 알려진 ROI360 비용 도구는 비용 데이터를 집계하고 리포트하는 기능을 수행합니다. 비용 도구 및 기능의 전체 제품군은 다음 표에 요약되어 있습니다. 링크를 클릭하여 각 기능에 대해 자세히 알아보십시오.

<table><thead><tr><th>도구</th><th>설명</th></tr></thead><tbody><tr><td><a href="./roi360-cost-aggregation-overview" target="_blank">어트리뷰트된 비용</a></td><td><p><span>어트리뷰션, 클릭, 노출과 연결된 비용 데이터는 사용 가능한 가장 세부적인 수준입니다.</span></p><p><span>여기에는 80개 이상의 API 통합에 대한 액세스가 포함되어 글로벌 또는 로컬 광고 네트워크에 쉽게 연결할 수 있습니다.</span></p></td></tr><tr><td><a href="./import-cost-data" target="_blank">파일 가져오기</a></td><td><p><span>비용 가져오기로 API를 통해 수신되지 않은 비용 데이터를 기록합니다.</span></p></td></tr><tr><td><a href="./incorporate-agency-fees-into-campaign-costs" target="_blank">에이전시 수수료</a></td><td><p><span>에이전시 수수료 계산은 비용에 포함됩니다.</span></p></td></tr><tr><td><a href="./set-up-and-use-roi360-cost-etl-reports" target="_blank">비용 ETL\*</a></td><td><span>매일 4회 업데이트되는 캠페인 비용 데이터를 광고주 BI 시스템에 로드할 준비가 된 AWS S3 또는 GCS 버킷으로 전송합니다.</span></td></tr><tr><td colspan="2"><span>\* ROI360 고급 패키지와 함께 사용 가능</span></td></tr></tbody></table>

**참고**: 그러나 이 방법은 CPI 비용 모델에만 적용되며 CPA, CPC 및 CPM과 같은 다른 모델에는 적용되지 않습니다.

<div id="revenue-tools" />

### 수익 도구

ROI360 수익 도구는 인앱 구매, 구독, 광고 수익을 고려하여 수익 데이터를 집계하고 보고합니다. 세금 및 앱 스토어 수수료도 수익 지표에 포함됩니다. 수익 도구 및 기능의 전체 제품군은 다음 표에 요약되어 있습니다. 링크를 클릭하여 각 기능에 대해 자세히 알아보십시오.

<table><thead><tr><th>도구</th><th>설명</th></tr></thead><tbody><tr><td>인앱 구매</td><td><p><span>환불 또는 취소와 같은 후속 트랜잭션에 대한 데이터를 포함하여 검증된 인앱 구매에 대한 자동 리포트입니다.</span></p></td></tr><tr><td>구독 수익</td><td><p><span>변경사항, 취소 및 가족 공유를 포함한 가입에 대한 자동 리포트입니다.</span></p></td></tr><tr><td><a href="./roi360-guide-ad-revenue-attribution" target="_blank">광고 수익</a></td><td><p>API 또는 SDK를 통해 연결하는 20개 이상의 광고 매출 파트너에 액세스하여 뛰어난 정확성과 데이터 최신성을 제공합니다.</p></td></tr><tr><td> <a href="./revenue-etl-reports" target="_blank">수익 ETL</a>\*</td><td><span>광고주 BI 시스템에 로드할 준비가 된 AWS S3 또는 GCS 버킷에 수익 데이터를 제공합니다.</span></td></tr><tr><td colspan="2"><span>\* ROI360 고급 패키지와 함께 사용 가능</span></td></tr></tbody></table>

**참고**: ROI360에 포함되지 않은 몇 가지 기본적인 수익 측정 도구도 있습니다. ROI360에 포함된 도구와 달리 이러한 도구는 개발자가 상당한 양을 설정해야 합니다.

* <Anchor target="_blank" href="/marketers/ko/docs/legacy-receipt-validation-for-in-app-purchases">인앱 구매 영수증 유효성 검증</Anchor>
* 구독 수익 측정
* <Anchor target="_blank" href="/marketers/ko/docs/roi360-revenue-attribution-overview">맞춤형 인앱이벤트를 통한 수익 기록</Anchor>

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 h_01HKHGX9JJQQCKF9SDZRSCM1XJ=%EA%B0%9C%EC%9A%94 cost-tools=%EB%B9%84%EC%9A%A9-%EB%8F%84%EA%B5%AC h_01HKHGX9JJRWDP9PMYP9CFA7MQ=%EB%B9%84%EC%9A%A9-%EB%8F%84%EA%B5%AC revenue-tools=%EC%88%98%EC%9D%B5-%EB%8F%84%EA%B5%AC h_01HKHGX9JJFQ9ZM6J3B2D5G6C5=%EC%88%98%EC%9D%B5-%EB%8F%84%EA%B5%AC" />
