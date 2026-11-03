---
title: 세금 API를 사용하여 순수익 측정값을 편집하십시오.
metadata:
  keywords:
    - Revenue
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
  created_at: '2024-11-28T13:57:14Z'
  edited_at: '2026-10-14T10:40:44Z'
  id: 30468586765841
  locale: ko
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/ko/articles/30468586765841
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

## 순수익 및 세금 측정에 대한 정보

True Revenue는 앱스플라이어 인앱 구매 및 구독 매출 솔루션을 제공하기 위해 구축된 비즈니스 로직 계층입니다. 들어오는 각 트랜잭션의 순수익 가치를 실시간으로 자동 계산하여 리포트에 포함합니다.

**세금은 기본 세율 구성을 사용하여 ROI360으로 측정된 모든 거래에 대해 기본적으로 신고됩니다.**

**전용 세금 API를 사용하여** 구성을 편집할 수 있습니다.

순수익에 대해 자세히 알아보세요.

## 세금 API를 사용하여 세금 비율을 편집하십시오.

**시작하기 전**: ROI360 인앱 구매 및 구독 수익 측정 설정의 1-2단계를 완료해야 합니다.

tax API를 사용하여 세금 구성을 편집하려면 다음 단계를 따르세요.

1. 개발자에게 다음 항목을 제공합니다.
   * 권한 부여 키로 사용할 API V2 토큰.
   * 다음 표에 설명된 대로 계산할 세금에 대한 정보를 포함하는 파라미터 및 값.
2. 개발자에게 세금 API 안내 에 따라 세율 규칙을 만들도록 알려주십시오. **참고**: 참고: API는 게시 요청의 본문에 JSON 파일을 허용합니다. 이 JSON 파일에서 모든 지원되는 국가와 그들의 기본 세율이 표시됩니다. 개발자는 이를 수정하거나 API에서 그대로 사용할 수 있습니다.

#### API에서 사용할 파라미터 및 값

| 파라미터 | 필수 | 비고 | 값 기록(개발자가 사용할 수 있음) |
| --- | --- | --- | --- |
| tax\_name | 예 | <ul><li>특정 세금 유형을 설명하는 고객 청구서에 표시되는 이름입니다.</li><li>예시: Sales, VAT, GST</li></ul> |  |
| tax\_rate | 예 | <ul><li>값은 0보다 커야 합니다.</li><li>징수할 세율을 나타내는 소수점 이하 4자리까지의 숫자입니다.</li><li>예: 7.25</li></ul> |  |
| tax\_exclusive | 아니요 | <ul><li>boolean 파라미터로, true나 false 중 하나입니다.</li><li>false는 세금이 전체 수익에 포함됨을 의미합니다.</li><li>true는 세금이 전체 언급된 수익에 추가됨을 의미합니다. 예를 들어, 미국 또는 캐나다에서는 가격표에 판매세가 포함되어 있지 않습니다.</li><li>기본 값은 false 입니다.</li></ul> |  |
| country | 아니요 | <ul><li>세금이 적용되는두 글자 ISO 국가 코드입니다.</li><li>예: CA</li><li>참고: 영국의 코드는 GB가 아닌 UK로 구현되었습니다.</li></ul> |  |
| 하위 분할 | 아니요 | <ul><li>일부 국가에는 추가적인 주\/구역이 있을 수 있습니다.</li><li><Anchor target="_blank" href="https://service.unece.org/trade/locode/2022-2%20SubdivisionCodes.htm">ISO 3166-2 하위 분할 코드에 따라 처리됩니다.</Anchor></li><li>국가 코드와 하위 분할 코드를 포함해야 합니다.</li><li>예: US-CA</li></ul> |  |
| postal\_code | 아니요 | <ul><li>문자 및/또는 숫자 문자열</li><li>예: L4J8E3</li></ul> |  |
| deduction\_order | 아니요 | <ul><li>열거형 , 0, 1 또는 2:<ul><li>0은 매장 수수료가 총 수익에서 먼저 공제되고 나머지 금액에서 세금이 공제됨을 의미합니다.</li><li>0은 매장 수수료가 총 수익에서 먼저 공제되고 나머지 금액에서 세금이 공제됨을 의미합니다.</li><li>2는 세금과 매장 수수료가 모두 총 수익에서 공제됨을 의미합니다.</li></ul></li></ul> |  |

<div data-zendesk-anchors="about-true-revenue-and-tax-measurements=%EC%88%9C%EC%88%98%EC%9D%B5-%EB%B0%8F-%EC%84%B8%EA%B8%88-%EC%B8%A1%EC%A0%95%EC%97%90-%EB%8C%80%ED%95%9C-%EC%A0%95%EB%B3%B4 h_01JDSGVGFB2AAZMZ87628WTAED=%EC%88%9C%EC%88%98%EC%9D%B5-%EB%B0%8F-%EC%84%B8%EA%B8%88-%EC%B8%A1%EC%A0%95%EC%97%90-%EB%8C%80%ED%95%9C-%EC%A0%95%EB%B3%B4 edit-tax-rates-using-the-tax-api=%EC%84%B8%EA%B8%88-api%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%98%EC%97%AC-%EC%84%B8%EA%B8%88-%EB%B9%84%EC%9C%A8%EC%9D%84-%ED%8E%B8%EC%A7%91%ED%95%98%EC%8B%AD%EC%8B%9C%EC%98%A4 h_01JDSGYR29TPPA9BPKJJRWNWKB=%EC%84%B8%EA%B8%88-api%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%98%EC%97%AC-%EC%84%B8%EA%B8%88-%EB%B9%84%EC%9C%A8%EC%9D%84-%ED%8E%B8%EC%A7%91%ED%95%98%EC%8B%AD%EC%8B%9C%EC%98%A4 parameters-and-values-to-use-in-the-api=api%EC%97%90%EC%84%9C-%EC%82%AC%EC%9A%A9%ED%95%A0-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0-%EB%B0%8F-%EA%B0%92 01H8VJJP1D8AZFRPEX7GYRH9CX=api%EC%97%90%EC%84%9C-%EC%82%AC%EC%9A%A9%ED%95%A0-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0-%EB%B0%8F-%EA%B0%92" />
