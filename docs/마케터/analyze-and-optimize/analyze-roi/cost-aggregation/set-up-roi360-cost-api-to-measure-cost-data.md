---
title: 비용 통합 연결
metadata:
  keywords:
    - ROI
    - cost
    - Advertisers
    - Agencies
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - Agencies
    - ROI360
  created_at: '2020-05-19T12:50:13Z'
  edited_at: '2026-10-14T10:35:12Z'
  id: 360008850257
  locale: ko
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/ko/articles/360008850257
---
> **요약:** 특정 앱의 비용을 활성화하세요.

<div id="overview" />

## 개요

Cost API를 사용하여 집계된 마케팅 비용 데이터(비용 관련 LTV 성과 지표 포함)를 가져옵니다. 데이터는 정확하고, 소급 적용되며 자동화되어 있습니다.

앱 수준에서 API를 통해 비용 통합을 활성화하는 경우, 모든 앱에 대해 모든 광고 네트워크(파트너)를 개별적으로 통합해야 합니다.

## 비용 API 활성화

> 📘 **참고**
>
> 광고주가 대행사를 통해 캠페인을 실행하는 경우, 광고주가 아닌 대행사가 관련 파트너와 연동해야 합니다. 그렇지 않으면 광고주와 대행사가 동일한 앱에 대해 동일한 자격 증명을 사용하여 파트너와 연동하면 비용 데이터가 중복됩니다.

**비용 API를 활성화하려면:**

1. 앱스플라이어의 사이드 메뉴에서 **협업** > **활성 연동**을 선택하고 파트너를 선택합니다.
2. **연동 관리**를 클릭합니다.
3. 통합된 파트너의 **비용** 탭을 엽니다.
4. **비용 데이터 가져오기** 토글을 활성화합니다. 파트너에 연결하기 위한 요구 사항이 표시됩니다.
5. 파트너와의 통합을 구성하고 인증합니다. 통합 방법은 파트너에 따라 다릅니다. [자세히 알아보기](/docs/set-up-roi360-cost-api-to-measure-cost-data#connection-methods)
6. 파트너의 비용 구성에 **사이트 ID 매핑**이 있는 경우 드롭다운에서 원하는 사이트 ID 구성을 선택하세요. [자세히 알아보기](/docs/set-up-roi360-cost-api-to-measure-cost-data#site-id-mapping)
7. **비용 저장**을 클릭합니다.
8. **연결 테스트**를 클릭합니다.  
   * API가 활성 상태입니다. 앱스플라이어는 하루 6번, 평균 4시간마다 한 번씩 파트너로부터 데이터를 수집합니다.
   * [비용 데이터 동기화 상태 및 메시지](/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status)

## 추가 정보

<div id="connection-methods" />

<Accordion title="통합 방법">

비용 통합을 활성화하는 데 사용되는 방법은 앱스플라이어와의 파트너 통합 모드에 따라 다릅니다. 다음 중 하나일 수 있습니다.

* 로그인: **로그인**을 클릭하여 파트너 로그인 창을 엽니다. 그런 다음 파트너의 로그인 프롬프트를 따릅니다.
* 자격 증명: 파트너별 매개 변수 값을 입력하십시오. 예를 들어: **API 키**.
* 없음: 2단계의 지시에 따라 **비용 데이터 가져오기** 토글을 켜는 것 외에는 연결 구성이 필요하지 않습니다.

특정 파트너가 사용하는 방법을 확인하려면 <Anchor target="_blank" href="/marketers/ko/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">광고 네트워크 비용 통합 표</Anchor>의 **통합 방법** 열을 참조하세요.

</Accordion>

<div id="map-apps-to-site-ids" />

<div id="site-id-mapping" />

<Accordion title="사이트 ID 매핑">

비용 데이터를 보고할 때, <Anchor target="_blank" href="/marketers/ko/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">일부 파트너 통합</Anchor>을 사용하면 사이트 ID 필드가 채워지는 방식을 선택할 수 있습니다. 이는앱스플라이어 사이트 ID 매크로가 어트리뷰션 링크에 있기 때문에, 앱스플라이어 사이트 ID 매크로와 일치하는 사이트 ID를 설정할 수 있다는 의미입니다.

* 기본적으로 사이트 ID 매핑은 어트리뷰션 링크의 앱스플라이어 매크로와 정렬됩니다.
* 사용하는 어트리뷰션 링크에 사이트 ID 매핑 옵션과 다른 매크로가 있으면, 사이트 ID 데이터가 올바르게 채워지지 않습니다.

**사이트 ID 구성 방법을 선택하려면:**

1. 통합된 파트너의 **비용** 탭에서 **사이트 ID 매핑**으로 이동하여 드롭다운 메뉴에서 구성을 선택합니다.
2. **비용 저장**을 클릭하세요.  
   변경 사항은 다음 날(UTC)부터 적용됩니다. 예를 들어, 사이트 ID 매핑이 월요일에 발생하면 화요일 UTC의 데이터에 반영됩니다.

</Accordion>

<div id="deleting-connected-accounts-in-the-cost-tab" />

<Accordion title="통합 계정 삭제">

일부 통합 파트너와의 연결은 앱스플라이어 내에서 파트너에 로그인하여 계정에 연결함으로써 이루어집니다. 필요에 따라 통합을 삭제할 수 있습니다. 한번 삭제되면, 앱스플라이어는 해당 계정에서 더 이상 비용 데이터를 가져올 수 없습니다. 통합을 삭제해도 이전 데이터에는 영향이 없습니다.

**통합 계정을 삭제하려면:**

1. 앱스플라이어의 사이드 메뉴에서 **협업** > **활성 통합**으로 이동합니다.
2. 통합된 파트너를 선택합니다, 예를 들어 Meta 광고.
3. **연동 관리**를 클릭합니다.
4. **비용** 탭으로 이동합니다.  
   연결된 계정 목록이 표시됩니다.
5. 액션 항목에서, 계정 위로 마우스 오버합니다.  
   **연결 삭제** 옵션이 표시됩니다.
6. **연결 삭제**를 클릭합니다.  
   확인 메시지가 표시됩니다. [altOauthDelete\_en-us.pngalt](https://support.appsflyer.com/hc/article_attachments/360008572837)
7. **삭제**를 클릭합니다.  
   계정 연결이 삭제되었습니다.  
   이전에 연결되었던 계정의 비용 데이터 수집이 즉시 종료됩니다. 과거 데이터에는 영향이 없습니다.

</Accordion>

<div id="disabling-cost-api" />

<Accordion title="비용 API 비활성화">

**비용 API를 비활성화하려면:**

1. **활성 통합**으로 이동하여 파트너를 선택하세요.
2. **비용** 탭으로 이동합니다.
3. **비용 데이터 가져오기**를 비활성화합니다.
4. **비용 저장**을 클릭하세요.

**참고**: 광고주가 에이전시와의 관계를 종료하고 앱 수준에서 에이전시 권한을 비활성화한 경우, 에이전시에서 앱의 비용을 구성한 경우 비용 데이터는 계속 수집됩니다. 이 데이터 수집을 중단하려면 광고주가 에이전시에 앱스플라이어에서 비용 통합을 비활성화하도록 요청해야 합니다.

</Accordion>

<div id="cost-api-status" />

<Accordion title="비용 API 상태">

비용 통합의 운영 상태는 다음과 같습니다:

* <Anchor target="_blank" href="/marketers/ko/docs/dashboard-cost-and-ad-revenue-status">비용 및 광고 수익 통합 상태 대시보드</Anchor><Anchor target="_blank" href="/marketers/ko/docs/dashboard-cost-and-ad-revenue-status">: 계정에 있는 하나 이상의 앱에 대해 비용 통합이 활성화된 파트너의 중앙화된 목록입니다.</Anchor>
* [통합 파트너:](/docs/set-up-roi360-cost-api-to-measure-cost-data#통합-파트너-비용-api-상태) 개별 앱의 컨텍스트에서 사용할 수 있는 상태입니다.

#### **통합 파트너 비용 API 상태**

파트너 통합 페이지의 비용 탭은 API를 통해 비용 데이터를 가져오는 것을 지원하는 광고 네트워크와 관련이 있으며, 다음과 같은 정보를 표시합니다:

* 비용 통합의 상태입니다.
* 앱스플라이어가 마지막으로 일치 비용 데이터를 성공적으로 가져온 시간.

**개별 파트너 비용 통합 상태를 보려면**:

1. 앱스플라이어의 사이드 메뉴에서 **협업** > **활성 통합**으로 이동합니다.
2. 파트너를 선택하세요.
3. **비용** 탭으로 이동합니다.  
   상태 및 마지막 동기화 시간이 표시됩니다.

| 상태 | 비고/필요한 조치 |
| --- | --- |
| 활성 (Active) | 연동이 활성화되고 광고 네트워크에 성공적으로 연결되었습니다. |
| 파트너 API가 일치하는 비용 데이터를 반환하지 않습니다. | 연결에 성공했지만 API가 앱스플라이어 캠페인 어트리뷰션 데이터와 일치하는 비용 데이터를 반환하지 않았습니다.<br /><br />이는 다음과 같은 이유로 발생합니다.<ul><li>캠페인 ID가 제공되지 않아 비용을 캠페인과 맞출 수 없습니다.</li><li>앱스플라이어를 통해 파트너에 로그인할 때 다른 파트너 광고 계정을 연결했습니다(예: 다른 Meta 광고 계정). 올바른 파트너 광고 계정을 연결했는지 확인하세요.</li><li>파트너 비용 연동의 자격 증명 필드 중 하나가 잘못되었습니다. 예를 들어 번들 ID입니다. 연동 자격 증명을 검토하고 수정하세요.</li></ul> |
| 파트너 API가 응답하지 않습니다. | <ul><li>연동 파트너의 서버가 앱스플라이어에 응답하지 않습니다.</li><li>6시간 동안 기다립니다. 상태 메시지가 지속되면 앱스플라이어 지원팀에 문의하십시오.</li></ul> |
| 잘못된 로그인 ID (Invalid Credentials) | <ul><li>앱스플라이어는 자격 증명이 유효하지 않기 때문에 API를 통해 데이터를 가져올 수 없습니다.</li><li>올바른 자격 증명을 사용하여 다시 연결합니다.</li></ul> |
| 리포팅된 API에 액세스하려면 광고 네트워크 계정 관리자로 이동하세요. | 파트너 계정 관리자와 협력하여 파트너 시스템에서 비용 연동을 사용하도록 설정합니다. |
| 파트너 API가 데이터를 반환하지 않습니다. 연동을 검토하세요. | 이는 다음과 같은 이유로 발생합니다.<ul><li>캠페인이 일시중지되었으며 데이터가 없습니다.</li><li>앱스플라이어를 통해 파트너에 로그인할 때 다른 파트너 광고 계정을 연결했습니다(예: 다른 Meta 광고 계정). 올바른 파트너 광고 계정을 연결했는지 확인하세요.</li><li>파트너 비용 연동의 자격 증명 필드 중 하나가 잘못되었습니다. 예를 들어 번들 ID입니다. 연동 자격 증명을 검토하고 수정하세요.</li></ul> |
| 파트너 시스템에서 비용을 받기 위해 계정이 활성화되지 않았습니다. | 파트너에게 연락하세요. |

</Accordion>

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 h_01HF4JW8MW5TBJBCNAHEMKSDW0=%EA%B0%9C%EC%9A%94 enable-cost-api=%EB%B9%84%EC%9A%A9-api-%ED%99%9C%EC%84%B1%ED%99%94 h_01HF4K7Z1BX9E6A7V158GANEVT=%EB%B9%84%EC%9A%A9-api-%ED%99%9C%EC%84%B1%ED%99%94 h_01HE0T3TGQ42ZTWSDF3MAM524K=%EC%B0%B8%EA%B3%A0 additional-information=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01HF4KF4ZP76QTVV3GTAPG2KK9=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01HF4KG17S6RRWV89GMHGRDT56=connection-methods h_01HF4QRXFZDE9BNGRR60FC3X4Q=site-id-mapping h_01HE0T3TGQ82E9R26NHGEE96WV=deleting-connected-accounts-in-the-cost-tab h_01HF4KG17STFQNXAP5RV24EDFE=disabling-cost-api h_01HE0T3TGQF2ADT3H071QDCJD3=cost-api-status integrated-partner-cost-api-status=%ED%86%B5%ED%95%A9-%ED%8C%8C%ED%8A%B8%EB%84%88-%EB%B9%84%EC%9A%A9-api-%EC%83%81%ED%83%9C h_01HE0T3TGQ5RE1CFMXYDD1W49C=%ED%86%B5%ED%95%A9-%ED%8C%8C%ED%8A%B8%EB%84%88-%EB%B9%84%EC%9A%A9-api-%EC%83%81%ED%83%9C" />
