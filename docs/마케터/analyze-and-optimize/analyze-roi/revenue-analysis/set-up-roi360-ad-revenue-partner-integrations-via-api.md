---
title: API를 통해 ROI360 광고 수익 파트너 연동 설정
metadata:
  keywords:
    - ad revenue
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
  created_at: '2022-10-16T14:53:47Z'
  edited_at: '2026-10-14T10:27:48Z'
  id: 9901416616465
  locale: ko
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/ko/articles/9901416616465
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **한눈에 보기:** API를 통해 앱스플라이어 계정 또는 개별 앱에 대한 광고 수익 파트너 연동을 구성합니다.

<div id="ad-revenue-partner-integration-api" />

## 광고 수익 파트너 연동 API

광고 수익 파트너 연동 API는 다음과 같은 목적으로 사용됩니다.

* 전체 계정에 대한 앱 수준 광고 수익 파트너 설정을 설정합니다.
* 전체 계정에 대한 현재 광고 수익 파트너 구성 목록을 가져옵니다.

<div id="set-api" />

<Accordion title="API 설정">

API를 통해 광고 수익 파트너 연동을 설정하는 방법:

1. 앱스플라이어 대시보드에서 API v2 토큰을 얻는 방법 API 인증에 필요합니다. **참고**: 이 작업은 계정 관리자가 수행해야 합니다.
2. 다음 표에 설명된 대로 API 요청에 포함할 파라미터를 준비합니다.
3. 개발자에게 파라미터 값을 제공하고 개발 허브에서 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_integrations">연동 설정 API 지침</Anchor>을 따르도록 지시합니다.  
   연동은 다음 날 00:00 UTC에 적용됩니다.

<div id="request-parameters" />

#### 요청 파라미터

| 파라미터 | 설명 |
| --- | --- |
| 연동 | <ul><li>app\_id, network 및 제품을 포함해야 하는 최상위 객체(아래 나열).</li><li>기타 필드에는 인증 정보, event\_name 및 source\_event가 포함될 수 있습니다.</li></ul> |
| app\_id | 연동하려는 앱의 앱 ID입니다. |
| 네트워크 | <ul><li>연동하려는 파트너입니다.</li><li>지원되는 네트워크 목록은 <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vR5BawKBlNhQRmZZ5tvh__HZEvwKOycv2lASR9-_RNpmIRvTr8LCqmHMDUssbpZAfUFJtw2nZYByNpR/pub?output=xlsx">광고 수익 파트너 API 파라미터 표</Anchor>의 네트워크 열을 참조하십시오.</li></ul> |
| 자격 증명 | <ul><li>네트워크 연동에 필요한 1개 이상의 자격 증명.</li><li>자격 증명 목록은 <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vR5BawKBlNhQRmZZ5tvh__HZEvwKOycv2lASR9-_RNpmIRvTr8LCqmHMDUssbpZAfUFJtw2nZYByNpR/pub?output=xlsx">광고 수익 파트너 API 파라미터 표</Anchor>의 크레딧 열을 참조하십시오.</li></ul> |
| event\_name | <ul><li>Default value: af\_ad\_revenue</li><li>커스텀 이벤트 이름[베타]이 될 수도 있습니다.</li><li>활성화가 false로 설정된 경우 event\_name이 필요하지 않습니다.</li></ul> |
| 제품 | <ul><li>파라미터 이름, 활성화 및 해당되는 경우,source\_event를 포함한 연동에서 활성화된 모든 제품 목록(아래 나열).</li><li>네트워크별 지원되는 제품 목록은 <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vR5BawKBlNhQRmZZ5tvh__HZEvwKOycv2lASR9-_RNpmIRvTr8LCqmHMDUssbpZAfUFJtw2nZYByNpR/pub?output=xlsx">광고 수익 파트너 API 파라미터 표</Anchor>의 대량 API 제품 열을 참조하십시오.</li></ul> |
| 이름 | <ul><li>연동 유형의 이름입니다.</li><li>연동 유형 이름 목록은 <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vR5BawKBlNhQRmZZ5tvh__HZEvwKOycv2lASR9-_RNpmIRvTr8LCqmHMDUssbpZAfUFJtw2nZYByNpR/pub?output=xlsx">광고 수익 파트너 API 파라미터 표</Anchor>의 대량 API 제품 열을 참조하십시오.</li></ul> |
| 활성화 완료 | <ul><li>가능한 값:<ul><li>true</li><li>false</li></ul></li><li>앱 수준 연동 유형의 경우 소스 이벤트가 필요합니다.</li><li>값이 false이면,source\_event나 event\_name이 필요하지 않습니다.</li></ul> |
| source\_event | <ul><li>집약 수준 S2S API 파트너 연동에만 해당됩니다.</li><li>앱 수준 연동 유형의 경우 활성화가 true로 설정된 경우 source\_event가 필요합니다.</li></ul> |

</Accordion>

<div id="get-api" />

<Accordion title="API 가져오기">

**API를 통해 광고 수익 파트너 연동 목록을 얻으려면**:

1. 앱스플라이어 대시보드에서 API v2 토큰을 얻는 방법 API 인증에 필요합니다.
2. 개발자에게 개발 허브에서 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_integrations">리스트 연동 API 지침</Anchor>을 따르도록 하십시오.

</Accordion>

<div id="specs-and-limitations" />

### 사양 및 제한 사항

| 사양 | **비고** |
| --- | --- |
| 콜 제한 | 단일 통화에서 최대 1,000건의 연동이 가능합니다. |
| OAuth | OAuth(예: Google 및 Facebook)를 통해 연동된 파트너는 지원되지 않습니다. |

<div data-zendesk-anchors="ad-revenue-partner-integration-api=%EA%B4%91%EA%B3%A0-%EC%88%98%EC%9D%B5-%ED%8C%8C%ED%8A%B8%EB%84%88-%EC%97%B0%EB%8F%99-api h_01HYD2M7E1PH0ARZRF0P17K80J=%EA%B4%91%EA%B3%A0-%EC%88%98%EC%9D%B5-%ED%8C%8C%ED%8A%B8%EB%84%88-%EC%97%B0%EB%8F%99-api h_01HYD2M7E1DX9FAJ0MGN500NZV=set-api request-parameters=%EC%9A%94%EC%B2%AD-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 h_01HYD2M7E1FYY96HNM6DSHXPQ5=%EC%9A%94%EC%B2%AD-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 h_01HYD2M7E19XCCFF1NT40VBWH7=get-api specs-and-limitations=%EC%82%AC%EC%96%91-%EB%B0%8F-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD h_01HYD2M7E1X2PEQ616PWMTWCH7=%EC%82%AC%EC%96%91-%EB%B0%8F-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD" />
