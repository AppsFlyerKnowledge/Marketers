---
title: 앱스플라이어 프리로드 리퍼러 어트리뷰션
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-alina-koifman
    - Marketers
    - Mobile Attribution
  created_at: '2022-03-02T09:54:10Z'
  edited_at: '2026-10-14T10:39:51Z'
  id: 4543811207313
  locale: ko
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/ko/articles/4543811207313
---
> **한눈에 보기:** 요약: 앱스플라이어는 프리로드 리퍼러를 사용하여 인스톨을 프리로드 캠페인에 어트리뷰션하며, 마케터는 OEM(주문자 상표부착 생산자), 이동통신사 및 앱 검색 파트너와 계약을 맺어 공장에서 또는 사용자가 기기를 처음 실행할 때 앱을 미리 로드합니다.

<div id="overview" />

## 개요

프리로드 캠페인에서 OEM(주문자 상표부착 생산자), 이동통신사, 앱 검색 파트너는 사용자가 앱을 사용하기 전에 기기에 앱을 미리 로드합니다. 이 작업은 공장의 OEM 또는 첫 번째 디바이스 활성화 시 제공업체가 수행할 수 있습니다.

광고주는 프리로드 캠페인을 통해 온라인 캠페인을 실행하지 않고도 잠재적으로 많은 잠재 고객에게 다가갈 수 있습니다.

프리로드 리퍼러 어트리뷰션(3가지 프리로드 <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-attribution-model#preload-campaigns">어트리뷰션 방법</Anchor>중 1개)은 마케터에게 프리로드 캠페인의 성과를 측정할 수 있는 정확한 개인 정보 보호 메커니즘을 제공합니다. 이 방법은 마케터에게 결정론적 어트리뷰션 결과를 제공하는 동시에 디바이스 및 사용자 식별자와 독립적으로 생성된 레퍼러와의 레퍼러 매칭을 통해 어트리뷰션이 수행되므로 사용자 개인 정보가 보호되도록 합니다.

이 솔루션은 다음을 제공합니다.

* 앱 업데이트 및 앱 재다운로드에 대한 투명한 지원.
* 첫 번째 장치 활성화와 첫 번째 앱 실행 사이의 가시성 및 측정 능력을 제공합니다. 이를 통해 특정 파트너가 앱을 미리 로드하여 활성화된 디바이스가 몇 대인지 확인하고, 앱이 처음 실행된 시점을 확인할 수 있습니다.

<div id="partners-supporting-preload-referrer-campaigns" />

## 프리로드 리퍼러 캠페인을 지원하는 파트너

<table><thead><tr><th rowspan="2">파트너</th><th rowspan="2">PID</th><th colspan="2">프리로드 리퍼러 캠페인 옵션 <a href="./set-up-appsflyer-preload-referrer-attribution#프리로드-리퍼러-옵션"><span>자세히 알아보기</span></a> </th></tr><tr><th>프리로드</th><th>클릭하여 다운로드</th></tr></thead><tbody><tr><td><a href="#특징-및-제약-사항">Samsung</a></td><td>samsung_int</td><td><span>✓</span></td><td> </td></tr><tr><td>Digital Turbine On Device</td><td>digitalturbine_int</td><td><span>✓</span></td><td>업데이트 예정</td></tr><tr><td>Unity의 Aura</td><td>aura_int</td><td><span>✓</span></td><td>업데이트 예정</td></tr><tr><td>Appnext</td><td>appnext_int</td><td><span>✓</span></td><td>업데이트 예정</td></tr><tr><td>Glance<br/> </td><td>glance_int</td><td><span>✓</span></td><td><span>✓</span></td></tr></tbody></table>

<div id="preload-referrer-options" />

## 프리로드 리퍼러 옵션

레퍼러는 프리로드 또는 클릭 투 다운로드를 통해 인스톨을 어트리뷰션하는 데 사용할 수 있습니다. 자세한 내용은 다음 표를 참조하십시오.

앱스플라이어는 프리로드 어트리뷰션에 가장 높은 우선순위를 부여합니다. 즉, 사용자가 앱을 처음 열기 전에 다른 캠페인에 참여하는 경우 프리로드 캠페인에 여전히 어트리뷰션이 부여됩니다. 다른 인게이지먼트는 인스톨 어시스트로 간주됩니다. **참고**:

| 리퍼러 옵션 | 설명 | UA는 로데이터 일치 유형을 설치합니다. |
| --- | --- | --- |
| 프리로드 | <ul><li>앱은 공장에서 미리 로드되거나 장치가 처음 활성화될 때 미리 로드됩니다. 디바이스가 처음 활성화될 때, 설치 마법사가 유저에게 앱 다운로드를 요청합니다.</li><li>클릭에 해당하는 프리로드 이벤트는 기기가 처음 켜질 때 앱스플라이어에 리포트됩니다.</li><li>어트리뷰션은 사용자가 앱을 처음 실행할 때 발생합니다.</li><li>프리로드 이벤트는 어트리뷰션 우선순위가 가장 높습니다(동일한 우선순위가 켜져 있지 않은 경우).</li></ul> | `preload_rfr` |
| 클릭하여 다운로드 | <ul><li>앱 인스톨은 장치 수명 주기의 후반부에 푸시 알림, 파트너 대체 저장소 등을 통해 수행됩니다.</li><li>사용자가 광고 또는 푸시 메시지에 참여하면 앱이 앱 스토어로 리디렉션되지 않고 기기에 자동으로 다운로드되고 설치됩니다.</li><li>어트리뷰션은 앱스플라이어 마지막 클릭 윈 규칙을 사용하여 제공됩니다.</li></ul> | `af_referrer` |


<span id="view-preload-attribution-data"></span>인게이지먼트 캠페인 성과 데이터를 다운로드하기 위한 프리로드/클릭은 다음과 같이 사용할 수 있습니다.

* 개요 대시보드  이 수값은 프리로드 파트너(미디어 소스) 및 캠페인 수준에서 집계됩니다.
* **로데이터:** 로데이터: 인게이지먼트는 데이터 락커를 통해서만 사용할 수 있는 클릭 리포트서에서 사용할 수 있습니다. 원래 URL 필드에서 찾을 수 있으며 af\_engagement\_type 파라미터에서 프리로드 또는 클릭 투 다운로드로 식별할 수 있습니다. 인스톨인 경우 이전 섹션의 표를 참조하여 검색 유형이 로데이터에 어떻게 표시되는지 확인합니다.

<div id="set-up-preload-referrer-attribution" />

## 프리로드 리퍼러 어트리뷰션 설정

**선행 조건:**

* 통합 앱스플라이어 <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-android-sdk-release-notes">안드로이드 SDK 6.10.1+</Anchor>.
* 앱스플라이어 프리로드 파트너와의 계약.

**프리로드 리퍼러 어트리뷰션 설정 방법**:

1. 앱스플라이어의 측면 메뉴에서 **협업** > **활성화된 연동**을 선택하세요.
2. 프리로드 파트너를 선택하십시오.
3. **연동** 탭에서 **프리로드 어트리뷰션**을 설정합니다.  
   <Image align="center" alt="" src="https://files.readme.io/d2c08125ca318b4bde60b51668692f21b88e292ca1b3f4fef54b77df779815cb-15585078780433.png" width="538px" />
4. **프리로드 기여 기간**을 설정합니다. 기간: 1-180일.
5. [선택 사항] **Preload equal attribution priority(동일한 어트리뷰션 우선순위 미리 로드)** 를 켭니다.  
   이는 결정론적 클릭에 프리로드 어트리뷰션과 동일한 어트리뷰션 우선순위를 부여하며, 이는 프리로드 리퍼러 인게이지먼트와 인스톨 사이에 결정론적 클릭이 등록되면 클릭이 프리로드 리퍼러로 대체되는 대신 표준 라스트 터치 어트리뷰션 로직에 따라 어트리뷰션을 가져온다는 것을 의미합니다.
6. **연동 저장**을 클릭합니다.
7. 프리로드 파트너에게 캠페인에 기여할 준비가 되었음을 알립니다.



<div id="traits-and-limitations" />

<div id="set-up-samsung-preload-referrer-attribution" />

<div id="samsung-preload-referrer" />

### 특징 및 제약 사항

| 특징 | 비고 |
| --- | --- |
|  | samsung\_int |
| SDK 버전 | v6.16.0 |
| 측정 유형 | `preload_rfr` |
| 개요 대시보드 | 이 수값은 프리로드 파트너(미디어 소스) 및 캠페인 수준에서 집계됩니다. |
| 로데이터(Raw data) 보고서 |  |

<div data-zendesk-anchors="appsflyer-preload-referrer-attribution=%EA%B0%9C%EC%9A%94 h_01HEKAF7K41PH189PSCKBRF070=%EA%B0%9C%EC%9A%94 partners-supporting-preload-referrer-campaigns=%ED%94%84%EB%A6%AC%EB%A1%9C%EB%93%9C-%EB%A6%AC%ED%8D%BC%EB%9F%AC-%EC%BA%A0%ED%8E%98%EC%9D%B8%EC%9D%84-%EC%A7%80%EC%9B%90%ED%95%98%EB%8A%94-%ED%8C%8C%ED%8A%B8%EB%84%88 h_01HEKAF7K5CWX2P9TY8M0MTQAM=%ED%94%84%EB%A6%AC%EB%A1%9C%EB%93%9C-%EB%A6%AC%ED%8D%BC%EB%9F%AC-%EC%BA%A0%ED%8E%98%EC%9D%B8%EC%9D%84-%EC%A7%80%EC%9B%90%ED%95%98%EB%8A%94-%ED%8C%8C%ED%8A%B8%EB%84%88 preload-referrer-options=%ED%94%84%EB%A6%AC%EB%A1%9C%EB%93%9C-%EB%A6%AC%ED%8D%BC%EB%9F%AC-%EC%98%B5%EC%85%98 h_01HEKAF7K4H3HNAMEYM6C58Y29=%ED%94%84%EB%A6%AC%EB%A1%9C%EB%93%9C-%EB%A6%AC%ED%8D%BC%EB%9F%AC-%EC%98%B5%EC%85%98 h_01HEKAF7K4GJDDPHCFTTC75YBS=view-preload-attribution-data set-up-preload-referrer-attribution=%ED%94%84%EB%A6%AC%EB%A1%9C%EB%93%9C-%EB%A6%AC%ED%8D%BC%EB%9F%AC-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%84%A4%EC%A0%95 h_01HEKAF7K41RBRVXC6GF6PCN3Y=%ED%94%84%EB%A6%AC%EB%A1%9C%EB%93%9C-%EB%A6%AC%ED%8D%BC%EB%9F%AC-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%84%A4%EC%A0%95 samsung-preload-referrer=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD set-up-samsung-preload-referrer-attribution=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD traits-and-limitation=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD h_01JCB6K81QRK2NM983SJBYD9M3=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD h_01JDPYAV86PT14C91ZQ2D9XTZ2=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD" />
