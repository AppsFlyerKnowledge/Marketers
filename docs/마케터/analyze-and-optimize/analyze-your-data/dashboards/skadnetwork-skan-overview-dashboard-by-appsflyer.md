---
title: 앱스플라이어에 의한 SKAdNetwork(SKAN) 개요 대시보드
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2020-07-25T21:27:38Z'
  edited_at: '2026-10-14T10:26:05Z'
  id: 360011307357
  locale: ko
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/ko/articles/360011307357
---
> **한눈에 보기:** 요약: SKAN(SKAdNetwork) 대시보드는 초기 사용자 측정 기간 동안 iOS SKAN 포스트백 및 추가 데이터 포인트를 통해 리포트된 캠페인 지표를 표시합니다. null 전환을 고려하는 모델링된 지표도 사용할 수 있습니다. 데이터는 인스톨 또는 포스트백 도착 시간을 사용하여 표시됩니다.

![SKAdHeadling8_us-en.png](https://files.readme.io/72c2eb452741cbd77c5828197f827f238c71c5097b8703528fa180dcafe2364c-360011831017.png)

<div id="dashboard-principles" />

## 대시보드 원칙

대시보드에는 SKAN 캠페인 성과 데이터가 포함되어 있으며 다음 원칙을 준수합니다.

* Apple은 <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork">개인 정보 보호 임계값 메커니즘</Anchor>으로 인해 CV(전환 값)를 항상 채우는 것은 아닙니다. 이들을 null CV라고 합니다. null CV의 경우 인스톨만 기록됩니다.
* 지표는 다음과 같이 계산됩니다.
  * 대시보드의 논오가닉 지표는 앱스플라이어가 받은 SKAN 포스트백 데이터를 사용하여 계산합니다. 재다운로드, 소스 앱 ID 및 충실도 유형 지표와 같은 일부 지표를 사용하려면 <Anchor target="_blank" href="/marketers/ko/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">앱스플라이어에 직접 포스트백 복사본을 보내도록</Anchor> 앱을 구성해야 합니다.
  * 오가닉 지표는 앱스플라이어 어트리뷰션 데이터에서 SKAN 논오가닉 어트리뷰션 데이터를 뺀 값으로 계산됩니다. **참고**: 일러두기 : 오가닉 지표를 항상 사용할 수 있는 것은 아닙니다. [더 알아보기](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#traits-and-limitations).
    * 설치 유형 필드에서 **새 설치**로 필터링해야 합니다.
  * 수익 및 ROAS와 같은 일부 지표는 포스트백에서 파생된 원래 값과 Null CV 비율을 고려하는 [모델링된 값](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv)을 모두 가집니다.
* 에이전시 중심 트래픽은 투명한 에이전시에서 오는 트래픽으로 취급됩니다.
* 데이터 최신성:
  * 일별.
  * 지정된 날짜에 받은 포스트백은 UTC에서 하루의 종료 시점에 처리됩니다. 데이터는 다음날 오전 8:00 UTC까지 이용 가능합니다. 즉, 월요일에 받은 포스트백을 화요일 아침에 대시보드에서 사용할 수 있습니다.
  * <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-solution-guide#timing-from-app-install-until-dashboard-and-reports-update">예상 대시보드 가동 업데이트 시간</Anchor>을 참조하십시오.

<div id="skan-dashboard-view-options" />

## SKAN 대시보드 표시 모드

[인스톨 날짜 또는 포스트백 도착 날짜](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#filter-options)를 이용한 데이터를 표시합니다.

필터 표시줄에서 날짜별 표시 옵션을 선택합니다.

다음 절에서 추가 필터 및 표시 옵션을 설명합니다.

<div id="dashboard-use" />

## 대시보드 사용

<div id="dashboard-settings" />

<Accordion title="대시보드 설정">

대시보드 설정은 앱이 기존 <Anchor target="_blank" href="/marketers/ko/docs/skan-conversion-studio#fixed-modes">고정 모드 전환 측정</Anchor>을 사용하여 전환 이벤트를 선택할 때 사용할 수 있습니다.

**전환 이벤트를 선택하는 방법**:

1. 대시보드의 오른쪽 상단에서 **대시보드 설정**을 클릭합니다.
2. 전환 이벤트를 선택합니다.
3. 적용을 클릭합니다.  
   이 이벤트를 사용하여 전환 지표를 계산합니다.  
   참고! 이 설정은 대시보드의 표시와 관련이 있으며 앱의 CV 설정에는 영향을 주지 않습니다.

</Accordion>

<div id="filter-options" />

<Accordion title="필터 옵션">

표시된 정보를 세분화하려면 필터를 사용하십시오.

| **필터** | **비고** |
| --- | --- |
| 표시 인자 | <ul><li>**인스톨 날짜**: 설치 날짜: 다음과 같이 포스트백 도착 시간에서 파생됩니다.<ul><li>포스트백이 SKAN V4인 경우 설치 날짜 공식은 다음과 같습니다. 설치 날짜 = 포스트백 도착 시간 - [누적 윈도우 길이] - [평균 포스트백 지연].<ul><li>포스트백 1: 설치 날짜 = 포스트백 도착 시간 - 48시간 - 36시간</li><li>포스트백 2: 설치 날짜 = 포스트백 도착 시간 - 168시간 - 84시간</li><li>포스트백 3: 설치 날짜 = 포스트백 도착 시간 - 840시간 - 84시간</li></ul></li><li>설치 날짜 = 포스트백 도착 시간 - 36시간 - [평균 최종 활성 범위].<ul><li>기본값 [평균 최종 활성 범위]는 12시간입니다.</li><li>전환 값이 0인 경우 평균 최종 활성 범위는 0으로 설정됩니다.</li></ul></li></ul></li><li>**포스트백 도착 날짜**:<ul><li>앱스플라이어에서 수신한 포스트백 날짜.</li><li>앱스플라이어 SKAN 대시보드의 지표를 광고 네트워크에서 제공하는 지표와 비교할 때는 일반적으로 광고 네트워크가 포스트백 도착 날짜를 사용하여 데이터를 사용할 수 있도록 한다는 점을 고려하십시오.</li><li>이 옵션을 선택하면 오가닉 지표를 사용할 수 없습니다.</li><li>Google Ads의 경우 도착 날짜 및 인스톨 날짜는 같습니다.</li></ul></li></ul> |
| 날짜 범위 | <ul><li>어트리뷰트 인스톨 날짜. 이 날짜는 포스트백 도착 날짜를 이용하여 파생됩니다.</li><li>인스톨 수가 많은 경우 시간 문제로 인한 부정확성은 중요하지 않습니다.</li><li>인스톨은 재설치를 포함합니다.</li><li>날짜 범위는 90일로 제한됩니다.</li></ul> |
| 미디어 소스 | <ul><li>인스톨에 어트리뷰션한 광고 네트워크</li><li>따라서 익숙하지 않은 미디어소스가 나타날 수 있습니다.</li></ul> |
| 캠페인 | <ul><li>광고 네트워크에서 설정한 캠페인 이름 및 ID</li><li>앱스플라이어는 포스트백 캠페인 ID를 광고 네트워크의 캠페인 ID로 해석합니다.</li><li>지정된 캠페인 ID에 여러 캠페인 이름이 연결되어 있으면 대시보드에 모든 이름이 표시됩니다. 참고! 광고 네트워크는 포스트백별로 캠페인 ID와 이름을 제공합니다. 캠페인 ID와 캠페인 이름은 로데이터와 집계된 SKAN 리포트에서 모두 사용할 수 있습니다.</li></ul> |
| 사이트 ID | <ul><li>앱 광고를 지면에 표시하는 소스 앱.</li><li>가장 성과가 좋은 앱을 분석하기 위해 사용합니다.</li></ul> |
| 지역 | <ul><li>지역 또는 국가</li><li>Geo(지역)는 광고 네트워크에서 제공된 데이터 또는 장치 IP 주소를 사용하여 파생됩니다.</li></ul> |
| 인스톨 유형 | <ul><li>인스톨</li><li>앱스토어가 보고한 앱 재설치</li></ul> |
| 광고세트 | 광고 네트워크가 이 데이터 포인트를 제공하는 경우 사용 가능 |
| Ad | 광고 네트워크가 이 데이터 포인트를 제공하는 경우 사용 가능 |
| 버전 |  |

</Accordion>

<div id="headline-metrics" />

<Accordion title="기본 측정 지표">

| 지표 | 비고 |
| --- | --- |
| 인스톨 | SKAN은 앱 사용자가 앱 인스톨 전 광고에 참여하지 않으면 인스톨을 보고하지 않습니다. 앱스플라이어는 앱스플라이어 어트리뷰트 인스톨(LTV 대시보드)을 사용하여 오가닉 지표를 계산합니다.<ul><li>논오가닉: 논오가닉: 유료 앱 투 앱 캠페인의 컨텍스트에서 미디어소스에 어트리뷰트되고 SKAN에서 리포트한 인스톨입니다.</li><li>앱스플라이어에서 계산한 오가닉은 다음을 포함합니다.<ul><li>SKAN에서 어트리뷰트하지 않았거나 광고 네트워크에서 포스트백을 수신하지 않은 인스톨입니다.</li><li>앱 클립</li><li>재설치인지 확인할 수 있습니다.</li></ul></li></ul> |
| 터치포인트 | 광고 네트워크 리포트 노출 및 클릭 대비 클릭 또는 API. |
| Total revenue | <ul><li>수익 모드가 활성일 때 사용 가능합니다.</li><li>USD 또는 <Anchor target="_blank" href="/marketers/ko/docs/app-settings">앱 설정 페이지</Anchor>에 설정된 앱별 현지 통화로 표시됩니다.</li><li>오가닉 수익과 논오가닉 수익으로 분류</li><li>오가닉 수익은 모든 수익에서 논오가닉 수익을 차감하여 계산합니다.</li><li>동일 조건에서 비교하기 위해, 오가닉과 논오가닉 인스톨의 포스트 인스톨 기간이 같습니다.</li></ul>**참고**: 일러두기 : 오가닉 지표를 항상 사용할 수 있는 것은 아닙니다. [더 알아보기](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#traits-and-limitations). |
| 비용 | <ul><li>광고 네트워크에서 보고한 비용. 비용 데이터는 ROI360/Cost API를 사용하여 앱스플라이어로 리포트됩니다. 비용은 USD 또는 <Anchor target="_blank" href="/marketers/ko/docs/app-settings">앱 설정 페이지</Anchor>에 설정된 앱별 현지 통화로 표시됩니다.</li><li>캠페인 이름이 변경되면 가장 최근에 사용한 캠페인 이름 아래에 비용이 표시됩니다. (캠페인 이름이 여러 개 있는 경우)</li><li>비용 지표는 인스톨 및 재다운로드를 모두 포함하는 필터 인스톨 유형=All(모두)에 대해서만 사용할 수 있습니다.</li></ul> |
| 클릭-인스톨 전환율 | 클릭-인스톨 전환율. |
| 인접 기간 비교 및 트렌드 분석 | 트렌드 값은 두 인접 동일 기간 사이의 특정 지표 값 변화를 %로 표시합니다. 예를 들어 현재 기간이 5월 1&#126;10일 경우 이전 기간은 4월 21일&#126;30일입니다. |

</Accordion>

<div id="charts" />

<Accordion title="차트">

사용 가능한 차트는 선택한 측정 타입에 따라 다릅니다.

<Table>
  <thead>
    <tr>
      <th>
        차트 지표
      </th>
      <th>
        비고
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        UA 트렌드
      </td>
      <td>
        사용 가능한 디멘션:

        * 오가닉
        * 논오가닉

        [<Image alt="SKAdNetwork_Dashboard_AppsFlyer2_us-en.png" src="https://files.readme.io/5c46dc05b4df07f3f60ff6015f115b4bc89106a6eb594f43d777af2100fdf460-360010368477.png" width="201px" />](https://support.appsflyer.com/hc/article_attachments/51857248012689)
      </td>
    </tr>
    <tr>
      <td>
        터치-전환
      </td>
      <td>
        조회 가능한 화면

        * 터치 포인트 디멘션
          * 노출
          * 클릭
        * 클릭-인스톨 전환율

        [<Image alt="SKAdNetwork_Dashboard_AppsFlyer3_us-en.png" src="https://files.readme.io/3e134f9411b356c8879dad8185b1762e6e039ed277da60fa9f67af351d8ab76d-360010368497.png" width="223px" />](https://files.readme.io/3e134f9411b356c8879dad8185b1762e6e039ed277da60fa9f67af351d8ab76d-360010368497.png)
      </td>
    </tr>
    <tr>
      <td>
        광고 계층 요소별로 그룹화된 일당 인스톨
      </td>
      <td>

      </td>
    </tr>
    <tr>
      <td>
        광고 계층 요소별 지표 분류
      </td>
      <td>
        [<Image alt="SKAdNetwork_Dashboard_AppsFlyer5_us-en.png" src="https://files.readme.io/f201592b110b3137329f7ad3c48c53e20639fb664383d76ceba2a347e969f6e4-360010368657.png" width="198px" />](https://files.readme.io/f201592b110b3137329f7ad3c48c53e20639fb664383d76ceba2a347e969f6e4-360010368657.png)
      </td>
    </tr>
    <tr>
      <td>
        주요 이벤트
      </td>
      <td>
        상위 이벤트에는 오가닉 및 논오가닉 사용자가 포함됩니다. 페이지 맨 위에 있는 미디어소스 필터를 사용하여 오가닉 사용자와 논오가닉 사용자를 구분하거나 선택한 미디어소스별로 구분합니다.

        [<Image alt="SKAdNetwork_Dashboard_AppsFlyer6_us-en.png" src="https://files.readme.io/1a569224cec155b54a96433d6b2e36918c9c6f7924629cb09dcfc859358199c3-360010454658.png" width="245px" />](https://files.readme.io/1a569224cec155b54a96433d6b2e36918c9c6f7924629cb09dcfc859358199c3-360010454658.png)
      </td>
    </tr>
    <tr>
      <td>
        상위 국가
      </td>
      <td>
        [<Image alt="mceclip1.png" src="https://files.readme.io/aba8db1a2aa7a90d5fd5c07e184eebd6d09762c5564f87f87f584d91686a59c6-360011169298.png" width="181px" />](https://files.readme.io/aba8db1a2aa7a90d5fd5c07e184eebd6d09762c5564f87f87f584d91686a59c6-360011169298.png)

        참고: 일러두기: 이 차트는 광고주가 아닌 에이전시에서 사용할 수 있습니다/span>
      </td>
    </tr>
    <tr>
      <td>
        포스트백 복사
      </td>
      <td>
        이 차트는 iOS 15 이상의 <Anchor target="_blank" href="/marketers/ko/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">포스트백 복사본</Anchor>을 앱스플라이어로 보내도록 앱을 설정한 후에 사용할 수 있습니다. 차트가 표시되지 않은 경우 다음을 고려하십시오.

        * 앱에서 포스트백을 받지 않거나 아직 받지 못했습니다. 앱 개발자에게 앱스플라이어 엔드포인트가 앱에 설정되었고 업데이트된 앱 버전이 앱 스토어에 있는지 확인하십시오.
        * 선택한 날짜에 대해 포스트백이 수신되지 않았거나(SKAN 인스톨이 없음을 의미) 2022년 1월 1일 이전 날짜를 선택했습니다.

        참고:

        * 대시보드의 다른 모든 지표는 광고 네트워크를 통해 앱스플라이어로 전달된 iOS 포스트백을 사용하거나 SRN에서 직접 제공한 데이터를 사용하여 계산됩니다. 포스트백 복사 지표와 다른 지표가 일치하지 않습니다.
        * 포스트백 복사 차트는 에이전시에 대해 사용할 수 없습니다.

        [<Image alt="PostbackCopy.png" src="https://files.readme.io/0f2d290817650c87b3719ce2cdd107fdf66f62f575d3b4b75fcdd1f8330a04a9-4417816656657.png" width="207px" />](https://files.readme.io/0f2d290817650c87b3719ce2cdd107fdf66f62f575d3b4b75fcdd1f8330a04a9-4417816656657.png)

        | 디멘션 | 비고 |
        | --- | --- |
        | 미디어 소스 | 인스톨에 어트리뷰트한 미디어소스.<br /><br />* 측정 지표<br />  * SKAdNetwork V2.2 이상을 사용한 포스트백과 관련된 지표<br />  * attributed\_touch\_type SKAdNetwork V2.2 이상을 사용한 포스트백과 관련된 지표<br />* 참고: 일러두기: 미디어소스 ID가 표시되면 현재 해당 ID와 연결된 이름이 없습니다. 미디어소스에 앱스플라이어의 SKAdNetwork ID를 업데이트하도록 요청하십시오. |
        | 소스 앱 | 광고 게시자 이름, 즉 사용자가 광고에 인게이지한 앱 이름입니다.<br /><br />* 지표:<br />* 참고:<br />  * Apple이 개인 정보 보호 임계값으로 인해 소스 앱 ID를 보류하면 소스 앱이 *알 수 없음*으로 표시됩니다.<br />  * 앱 이름을 찾을 수 없는 경우 앱 ID가 표시됩니다. |
        | 소스 앱 ID | 광고 게시자 ID, 즉 사용자가 광고에 인게이지한 앱 ID입니다.<br /><br />* 지표: |
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="metrics" />

<Accordion title="측정 지표">

* 사용 가능한 지표 선택. [모델링된 지표](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv)는 null CV 속도를 고려합니다.
* 기준별 1차 및 2차 그룹을 설정하여 성과 지표를 분석합니다.

[![SKAdNetwork_Dashboard_AppsFlyer7_us-en.png](https://files.readme.io/434a848c7a33c052c80101788b066f4bdb90ef36423ea140f85c1cc59ace2ebf-360010368617.png)](https://files.readme.io/434a848c7a33c052c80101788b066f4bdb90ef36423ea140f85c1cc59ace2ebf-360010368617.png)

측정 지표 테이블 사용법

* 이 테이블을 이용해 캠페인 및 미디어 소스의 성과를 비교합니다.
* 기본적으로 인스톨 수에 따라 상위 20개의 미디어소스가 정렬되어 내림차순으로 표시됩니다.
* 정렬 순서를 바꾸려면 순서를 바꿀 헤더 컬럼을 클릭하십시오. 한 번 더 클릭하면 정렬 순서가 반대로 바뀝니다.
* 비용 관련 지표(비용, 노출 및 클릭)는 지정된 캠페인과 1개 이상의 인스톨이 연결된 경우 사용할 수 있습니다. 참고:
  * 0 인스톨을 가진 캠페인은 전혀 표시되지 않습니다.
  * 일부 광고 네트워크는 광고 세트 및 광고 수준에서 비용 관련 지표를 리포트하는 것이 아니라 캠페인 수준에서 인스톨을 리포트합니다. 이 경우 인스톨 지표가 0인 광고 세트 및 광고 비용 관련 지표가 표시됩니다.

테이블 지표:

<table><thead><tr><th>지표</th><th>계산 공식/비고</th></tr></thead><tbody><tr><td>인스톨</td><td><ul><li>총 인스톨</li><li>클릭-쓰루<ul><li>클릭-쓰루 어트리뷰션을 통해 가져온 사용자</li><li>2021년 12월 22일부터 시작하여 기록된 인스톨에 대해 사용 가능합니다.</li></ul></li><li>뷰-쓰루<ul><li>2021년 12월 22일부터 시작하여 기록된 인스톨에 대해 사용 가능합니다.</li><li>SKAdNetwork V2.2 이상을 +를 구현하는 광고 네트워크에 적용됩니다.</li></ul></li></ul>이 데이터는 포스트백의 fidelity_type 필드에서 파생됩니다.</td></tr><tr><td>Null 전환 값 비율</td><td>null 전환 값/인스톨을 가지는 포스트백 \* 100  </td></tr><tr><td>노출</td><td> </td></tr><tr><td>클릭</td><td> </td></tr><tr><td>클릭-인스톨 전환율</td><td>인스톨 수 / 클릭 수 \* 100</td></tr><tr><td>전환 유저</td><td><p>지정된 측정 이벤트를 수행한 고유 앱 사용자 수.</p><ul><li> SKAN 4 모드: 항상 af_skad_revenue(다른 항목을 선택하면 전환된 사용자가 비어 있음)</li><li> SKAN 4 모드: 항상 af_skad_revenue(다른 항목을 선택하면 전환된 사용자가 비어 있음)</li><li> Always af_skad_revenue</li><li>변환 모드 </li><li> <br/><br/> </li></ul></td></tr><tr><td>전환 유저 수 / 인스톨 수</td><td> </td></tr><tr><td>총수익</td><td>null 값의 모델링된 데이터를 포함한 수익입니다. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">더 알아보기</a> </td></tr><tr><td>총 수익(모델링되지 않음)</td><td>전환 가치를 통해 보고된 수익입니다. 모델링된 데이터는 포함되지 않음</td></tr><tr><td>수익 D1-D2</td><td>SKAN 창 1(수정하지 않는 한 1-2일)에 대한 수익으로, null 값의 모델링된 데이터를 포함합니다. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">더 알아보기</a> </td></tr><tr><td>수익 D1-D2(모델링되지 않음)</td><td>SKAN 창 1(수정되지 않는 한 1-2일)에 받은 수익입니다. 모델링된 데이터는 포함되지 않음</td></tr><tr><td>수익 D3-D7</td><td>SKAN 기간 2의 매출 (수정하지 않는 한 3-7일)</td></tr><tr><td>수익 D8-D35</td><td>SKAN 기간 3의 매출 (수정하지 않는 한 8-35일)</td></tr><tr><td>비용</td><td><ul><li>광고 네트워크가 보고한 비용 </li><li>캠페인 이름이 변경되면 가장 최근에 사용한 캠페인 이름 아래에 비용이 표시됩니다. (캠페인 이름이 여러 개 있는 경우)</li></ul></td></tr><tr><td>ARPU</td><td><ul><li>null 값의 모델링된 데이터를 포함한 사용자당 평균 수익입니다. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">더 알아보기</a> </li><li>공식: 수익(모델링됨) / 인스톨</li></ul></td></tr><tr><td>ARPU(모델링되지 않음)</td><td>사용자당 평균 수익, 모델링된 데이터는 포함되지 않음</td></tr><tr><td>ROI (투자수익률)</td><td><ul><li>null 값의 모델링된 데이터를 포함한 투자 수익. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">더 알아보기</a> </li><li>공식: (수익(모델링됨) - 비용) / 비용 \* 100</li></ul></td></tr><tr><td>ROI(모델링되지 않음)</td><td>투자 수익률, 모델링된 데이터는 포함되지 않음</td></tr><tr><td>ROAS</td><td><ul><li>null 값의 모델링된 데이터를 포함한 광고 지출 대비 수익률입니다. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">더 알아보기</a> </li><li>공식: (수익(모델링됨) / 비용 \* 100</li></ul></td></tr><tr><td>ROAS(모델링되지 않음)</td><td>광고 지출 대비 수익률, 모델링된 데이터는 포함되지 않음</td></tr><tr><td>eCPI</td><td> </td></tr><tr><td colspan="2"><strong>인앱 이벤트 메트릭</strong></td></tr><tr><td>인앱 이벤트 이름</td><td> </td></tr><tr><td>eCPA</td><td><ul><li>null 값의 모델링된 데이터를 포함한 작업당 유효 비용입니다. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">더 알아보기</a> </li><li>공식: 수식: 비용/이벤트를 수행하는 고유 사용자(모델링됨)</li></ul></td></tr><tr><td>eCPA (모델링되지 않음)</td><td>효과적인 행동당 비용, 모델링된 데이터는 포함되지 않음</td></tr><tr><td>총 이벤트 수</td><td>null 값의 모델링된 데이터를 포함하여 모든 창에서 발생한 총 이벤트 발생입니다. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">더 알아보기</a> </td></tr><tr><td>총 이벤트 수(모델링되지 않음)</td><td>모든 창에서 발생한 총 이벤트 수(모델링된 데이터는 포함되지 않음)</td></tr><tr><td>이벤트 수 D1-D2\*</td><td>Null 값의 모델링된 데이터를 포함하여 창 1(수정되지 않는 한 1-2일)에 대한 이벤트 발생. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">더 알아보기</a> </td></tr><tr><td>이벤트 카운트 D1-D2(모델링되지 않음)</td><td>창 1에 대한 이벤트 발생(수정되지 않는 한 1-2일), 모델링된 데이터는 포함되지 않음</td></tr><tr><td>이벤트 수 D3-D7</td><td></td></tr><tr><td>이벤트 수 D8-D35</td><td></td></tr></tbody></table>

</Accordion>

<div id="modeled-metrics-and-null-cv" />

<Accordion title="모델링된 지표 및 null CV">

SKAdNetwork(SKAN) 리포트는 다음과 같은 이유로 제한될 수 있습니다.

* SKAN은 6비트로 제한되는 전환 값(CV)에 의존하므로 가능한 값이 64개(0-63) 생성됩니다.
* Apple은 때때로 사용자 프라이버시를 보호하기 위해 실제 CV를 보류(그리고 데이터를 "null"로 반환)합니다.
* 데이터는 측정 기간 내에서만 사용할 수 있으며 전체 유저생애가치(LTV)는 알 수 없습니다.

SKAN 모델링 데이터는 다음을 제공하여 이러한 문제를 해결합니다.

* null 값 대신 모델링된 전환 값.
* 모델링된 수익 및 이벤트 발생.
* 앱 및 캠페인 LTV 성과에 대한 보다 완전한 그림.

사용 가능한 모델링 지표는 다음과 같습니다.

* 수익
* 이벤트 수
* eCPA
* ARPU
* ROI (투자수익률)
* ROAS

모델링된 SKAN 데이터에 대해 자세히 알아보기

</Accordion>

<div id="appsflyer-attribution-vs-skan-attribution" />

<Accordion title="앱스플라이어 어트리뷰션 SKAN 어트리뷰션">

SKAN 지표는 앱스플라이어 어트리뷰션 모델을 이용하여 사용할 수 있는 지표와 다릅니다. 다음 표에는 주요 원인이 기재되어 있습니다.

정의:

* 시간: 기본 활동 기간을 24시간(SKAN 4로 업그레이드한 후 48시간)으로 가정합니다.
* **SDK:** SDK: 앱에 내장된 앱스플라이어 SDK.
* 규칙 <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-attribution-model">앱스플라이어 어트리뷰션 모델</Anchor>

<div id="attribution-framework-differences" />

#### 어트리뷰션 프레임워크 차이

| 개념 | SKAN | 앱스플라이어 |
| --- | --- | --- |
| 지원되는 어트리뷰션 방법 | 클릭-쓰루 및 뷰-쓰루 어트리뷰션을 위한 Apple SKAN. SKAN을 지원하는 SRN과 광고 네트워크의 앱 투 앱 캠페인의 트래픽을 포함합니다. | <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-attribution-model">앱스플라이어 어트리뷰션 모델</Anchor>은 다음과 같은 다중 어트리뷰션 방법과 시나리오를 지원합니다.<ul><li>모바일 웹</li><li>뷰-쓰루(view-through)</li><li>광고 클릭</li><li>앱 클립</li><li>웹 어트리뷰션</li><li>Apple Search Ads</li><li>소유 매체</li><li>SRN 트래픽(동의 사용자)</li><li>기타</li></ul> |
| 1차 데이터 소스 | <ul><li>SKAN 포스트백</li><li>SDK</li></ul> | SDK 및 관련 솔루션.   예시: 서버 간 이벤트 |
| 데이터 최신성 | <Anchor target="_blank" href="/marketers/ko/docs/about-data-freshness-and-timezone-support#skan">SKAN 데이터 최신성.</Anchor> | 사용자가 앱을 실행하고 사용하는 실시간. |
| 시간대 | UTC | 앱별 시간대. |
| 설치 시간 | iOS 포스트백 도착 시간에서 추출. | SDK에서 리포트함. |
| 유저 활동 측정 기간 | 앱이 열린 상태에서 시작되는 고정된 측정 기간 동안의 사용자 활동입니다. | 인스톨 날짜부터 현재까지 LTV 데이터를 포함합니다.<br /><br />코호트를 사용하여 코호트 0일 또는 코호트 1일로 제한된 데이터를 보거나 비교 가능한 측정 기간을 보려면 함께 표시합니다.<br /><br />코호트 0일은 24시간 미만의 활동으로 구성된다는 점을 알아두십시오. 예를 들어, 특정 날짜의 18:00에 설치하는 사용자는 코호트 0일에 6시간의 활동을 가집니다. |
| 인스톨 리포트 담당자 | <ul><li>SKAN SKAN: 논오가닉 인스톨 및 논오가닉 재다운로드로 제한됩니다.</li><li>**SDK**: SDK: 모든 인스톨이 리포트됩니다. 처음 설치하는 것만 지표 목적으로 계산됩니다. 리어트리뷰션 측정은 무시됩니다.</li></ul> | SDK는 규칙을 사용하여 처음 인스톨 및 리타게팅 재인스톨(리어트리뷰션)로 분류된 모든 인스톨을 리포트합니다. |
| 광고 세분성 수준 | 캠페인, 광고 세트, 광고 세트 ID 및 광고 ID. | Full Hierarchy (전체 계층 구조) 전체 계층: 캠페인, 캠페인 ID, 광고 세트, 채널 및 파트너와 같은 추가 파라미터. |
| 재다운로드 대 리인스톨 | 재다운로드는 해당 Apple ID 사용자의 동작과 관련됩니다. 리어트리뷰션과 병렬 처리되지 않습니다. | 리타게팅(리인게이지먼트 리어트리뷰션)은 리타게팅 대시보드를 반영합니다. 재다운로드와 병렬 처리되지 않습니다. |

<div id="metric-differences" />

#### 지표 차이

| 지표 | SKAN | 전통적인 어트리뷰션 |
| --- | --- | --- |
| 논오가닉 인스톨 | 앱스플라이어에서 받은 iOS 포스트백의 개수.<br /><br />알아두기: 앱스플라이어는 앱스플라이어와의 SKAN 연동을 완료하지 않은 광고 네트워크의 포스트백을 얻지 못합니다.<br /><br />이로 인해 논오가닉 인스톨의 수가 줄어들고 오가닉 인스톨이 증가할 수 있습니다. | <ul><li>SDK에서 리포트함.</li><li>미디어소스로 어트리뷰트됩니다.</li><li>규칙을 사용하여 계산합니다.</li></ul> |
| 오가닉 설치 | SDK 인스톨 마이너스 SKAN 인스톨. | <ul><li>SDK에서 리포트함.</li><li>미디어소스로 어트리뷰트되지 않습니다.</li><li>규칙을 사용하여 계산합니다.</li></ul> |
| 수익 | **논오가닉:**<br /><br />**오가닉: 오가닉: SDK 인앱이벤트로 보고된 수익에서 논오가닉 수익을 뺀 값입니다.**  참고:**일러두기 : 오가닉 지표를 항상 사용할 수 있는 것은 아닙니다. [더 알아보기](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#traits-and-limitations).** | <ul><li>SDK와 서버 간 API에 의해 리포트되었습니다.</li></ul> |
| 광고 수익 | <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-solution-guide#recording-ad-revenue">사용 가능</Anchor> | 사용자 수준 광고 수익은 IDFV에 기반하여 어트리뷰트됩니다. |
| ROI/ROAS | 측정 기간 내 수익. | <ul><li>LTV</li><li>UA 및 리타게팅 캠페인 지표.</li></ul> |

</Accordion>

<div id="faq-skan-discrepancies" />

<Accordion title="FAQ—SKAN 차이">

| 이유 | 차이—QA |
| --- | --- |
| A | **질문: 질문: 앱스플라이어 대시보드의 전환 수가 광고 네트워크 대시보드의 전환 수와 다른 이유는 무엇입니까?**<br /><br />**답변**: 답변: 차이의 이유<ul><li>인스톨 대비 포스트백 도착 날짜:<ul><li>앱스플라이어 앱스플라이어: 인스톨 날짜는 iOS 포스트백 도착 시간, 기간의 길이 및 포스트백 지연 시간을 고려한 공식을 사용하여 파생됩니다.</li><li>애드 네트워크 광고 네트워크: 일반적으로 오직 iOS 포스트백 도착 시간을 조정 없이 인스톨 날짜로 사용합니다.</li><li>대시보드의 **포스트백 도착 날짜별 표시** 옵션을 사용하여 이 차이를 제거할 수 있습니다.</li></ul></li><li>포스트백 유효성 검증: 앱스플라이어는 수신된 iOS 포스트백을 확인하고 Apple 서명이 올바른지 확인합니다. 광고 네트워크에서 앱스플라이어가 무시한 잘못된 포스트백을 보낼 수 있습니다.</li><li>**포스트백 누락**: iOS 포스트백은 광고 네트워크에서 앱스플라이어로 전송되어야 합니다. 앱스플라이어는 기기에서 직접 포스트백을 가져오지 않습니다. 포스트백이 누락된 경우 앱스플라이어는 이를 알 수 없습니다.</li></ul> |
| B | **질문**: 질문: **<Anchor target="_blank" href="/marketers/ko/docs/skan-aggregated-performance-report-api">SKAN 성과 API</Anchor> 및 대시보드와 SKAN 집약형 포스트백 API의 차이점이 무엇입니까?**<br /><br />**답변**: 답변: 포스트백 API 날짜 범위는 앱스플라이어가 포스트백을 받은 날짜와 관련이 있습니다. 성과 API 날짜 범위는 이유 A에 설명된 대로 파생된 설치 날짜와 관련이 있습니다. |
| C | **질문: 질문: 모든 광고 네트워크가 지역을 리포트합니까?**<br /><br />**A:** 아니오. |
| D | **질문: 질문: 개요 대시보드와 SKAN 대시보드 사이에 차이가 있는 이유는 무엇입니까?**<br /><br />A. 답변: 불일치 이유에 대한 개요는 이전 섹션을 참조하십시오. |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="특징 및 제약 사항">

| 특징 | 비고 |
| --- | --- |
| 모델링된 이벤트 발생 수 | <ul><li>모델링된 이벤트는 [모델링된 지표 및 null CV](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv)에 설명된 공식을 기반으로 합니다.</li><li>공식은 데이터 행별로 적용됩니다. 이로 인해 주어진 미디어소스에 대해 모델링된 이벤트 수와 해당 캠페인의 모델링된 이벤트 수 합계 간에 불일치가 발생할 수 있습니다.</li></ul> |
| 포스트백 도착 날짜 | 날짜 범위의 최종 날짜는 마지막 인스톨이 기록된 날짜로 제한됩니다. |
| 오가닉 데이터 | <ul><li>SSOT는 SKAN 어트리뷰션 및 앱스플라이어 모델 속성 이벤트를 중복 제거하므로 SSOT를 사용하여 오가닉 데이터를 보는 것을 고려하십시오.</li><li>앱스플라이어 어트리뷰션 데이터(오가닉 및 비오가닉 모두에 대한 신규 인스톨)에서 SKAN 어트리뷰션 데이터(비오가닉 인스톨)를 뺀 값이 음수인 경우, SKAN 대시보드는 오가닉 인스톨 아래에 0을 표시합니다.</li></ul> |
| 과거 데이터 | 2020년 11월 1일 |
| 통화 | USD 또는 <Anchor target="_blank" href="/marketers/ko/docs/app-settings">앱 설정 페이지</Anchor>에 설정된 앱별 현지 통화로 표시됩니다. |
| 시간대 | SKAN에서 리포트한 데이터의 경우, 인스톨 및 이벤트는 UTC를 사용하여 표시되며, Meta 및 Google SKAN 데이터는 예외적으로 시간대가 Meta 및 Google 계정에 각각 구성된 시간대를 기반으로 합니다. |
|  | <ul><li>구글</li><li>메타</li></ul> |

</Accordion>

<div id="see-also" />

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-solution-guide">AppsFlyer SKAN 솔루션 가이드</Anchor>
> * <Anchor target="_blank" href="/marketers/ko/docs/about-att-and-skan">iOS 14 관련 앱스플라이어 업데이트</Anchor>

<div data-zendesk-anchors="dashboard-principles=%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C-%EC%9B%90%EC%B9%99 01H81P8JPZM24J0536GKBPNFMJ=%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C-%EC%9B%90%EC%B9%99 skan-dashboard-view-options=skan-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C-%ED%91%9C%EC%8B%9C-%EB%AA%A8%EB%93%9C 01H81P8JPZC5K0KZR64P084N4W=skan-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C-%ED%91%9C%EC%8B%9C-%EB%AA%A8%EB%93%9C dashboard-use=%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C-%EC%82%AC%EC%9A%A9 01H81P8JPZGSHQVMG27YEJPARH=%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C-%EC%82%AC%EC%9A%A9 01H81P8JPZ93G4EQY343SV2B1Q=dashboard-settings 01H81P8JPZV5F4VCZHR537HREH=filter-options 01H81P8JQ0KRGXWCVT82YW30CS=headline-metrics 01H81P8JQ0ETB0W3SGS56CBCX8=charts 01H81P8JQ0KK1NMRGFR0GBX4EK=metrics 01H81P8JQ0ZKGTRWNW95D015Z7=modeled-metrics-and-null-cv 01H81P8JQ18NGP8Z74D02DMQ7P=appsflyer-attribution-vs-skan-attribution attribution-framework-differences=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%94%84%EB%A0%88%EC%9E%84%EC%9B%8C%ED%81%AC-%EC%B0%A8%EC%9D%B4 01H81P8JQ1VTYX3382WDXDMVT3=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%94%84%EB%A0%88%EC%9E%84%EC%9B%8C%ED%81%AC-%EC%B0%A8%EC%9D%B4 metric-differences=%EC%A7%80%ED%91%9C-%EC%B0%A8%EC%9D%B4 01H81P8JQ1M8M9TSHF0C12Z2QE=%EC%A7%80%ED%91%9C-%EC%B0%A8%EC%9D%B4 faq%E2%80%94skan-discrepancies=faq-skan-discrepancies 01H81P8JQ157YYNX9C527ES4C8=faq-skan-discrepancies 01H81P8JQ1T3DE29Y14VARKASK=traits-and-limitations h_01HE7SWGPWNWG26CEN40VSTA9J=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
