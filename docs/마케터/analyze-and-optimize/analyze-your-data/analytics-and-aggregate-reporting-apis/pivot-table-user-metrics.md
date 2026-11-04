---
title: 피벗 테이블—사용자 메트릭
metadata:
  keywords:
    - Pivot
    - Advertisers
    - 透视表
    - Premium
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2017-03-16T13:11:23Z'
  edited_at: '2026-10-14T10:29:57Z'
  id: 115001421846
  locale: ko
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/ko/articles/115001421846
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **간단히 보기**: 다양한 사용자 메트릭 보기—LTV, 활동, Protect360 및 유지율. BI 시스템에서 사용할 수 있도록 결과를 CSV 파일로 다운로드합니다. 피봇은 단일 쿼리로 다중 앱을 지원합니다. 마스터 API 호출을 생성하는 데 사용합니다.

![Full_Funnel.gif](https://files.readme.io/f74b45f8fcaa29cc0941a90d6cca5ef7fb87a8034edb36697d8d595a6be7b3a5-51912582394385.gif)

<div id="about-pivot-reports-page" />

## 피벗 보고서 페이지에 대하여

피봇을 사용하면 유저 인입 지표를 포함하는 커스텀 리포트를 생성할 수 있습니다. 피봇에는 사용자정의된 리포트를 생성하는 기준으로 사용할 수 있는 여러 가지 미리 정의된 리포트가 함께 제공됩니다. 지정된 계정 사용자가 작성한 리포트는 모든 사용자가 사용할 수 있습니다.

사용 가능한 사전 정의된 피봇 리포트는 다음과 같습니다.

* 날짜별 미디어소스
* 전체 구조
* 비용 분석

**참고**: 캠페인 데이터가 피벗에 표시되려면 캠페인에 설치가 있어야 합니다.

<div id="pivot-procedures" />

## 피봇 절차

사용자 인터페이스에서 기존 피봇을 만들고 수정합니다. 이렇게 하려면 다음 절의 절차를 따르십시오.

**피봇을 사용하는 방법**:

* 앱스플라이어의 사이드 메뉴에서 **Analyze** > **Pivot**을 선택합니다.  
  현재 정의된 리포트 목록이 표시됩니다.

<div id="pivot-page-controls-and-options" />

<Accordion title="피봇 페이지—컨트롤 및 옵션">

<Table>
  <thead>
    <tr>
      <th>
        열/옵션
      </th>
      <th>
        설명
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        이름
      </td>
      <td>
        연관된 피봇을 보려면 리포트 이름을 선택하십시오.
      </td>
    </tr>
    <tr>
      <td>
        열 클릭
      </td>
      <td>
        인터페이스에 표시된 일부 열은 열 이름을 클릭하여 정렬할 수 있습니다.
      </td>
    </tr>
    <tr>
      <td>
        마지막 수정
      </td>
      <td>
        리포트 구조가 마지막으로 수정된 시간입니다.
      </td>
    </tr>
    <tr>
      <td>
        수정한 사람
      </td>
      <td>
        피봇을 수정한 사용자의 이름입니다.
      </td>
    </tr>
    <tr>
      <td>
        앱 이름
      </td>
      <td>
        * 앱이 앱 이름을 포함하는 경우
        * 다중 앱이 포함된 경우: 앱 개수
      </td>
    </tr>
    <tr>
      <td>
        작업
      </td>
      <td>
        | 작업 | 비고 |
        | --- | --- |
        | 복제 | 기존 피봇 리포트를 복사합니다. |
        | 피봇 이름 수정 | 리포트 이름을 변경합니다. |
        | 히스토리 로그 보기 | 누가 리포트 구조를 다루었으며, 언제 무엇이 적용되었는지 표시합니다. |
        | 마스터 API 링크 복사 | <Anchor target="_blank" href="/marketers/ko/docs/master-api-user-acquisition-metrics-via-api">마스터 API</Anchor>를 통해 데이터를 끌어올 URL을 생성합니다. 마스터 API를 사용하려면 인증 헤더에서 사용할 <Anchor target="_blank" href="/marketers/ko/docs/managing-appsflyer-tokens">API 토큰</Anchor>(관리자 권한 필요)을 가져와야 합니다. |
        | 삭제 | 선택된 피봇을 삭제합니다. |
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="add-a-pivot-report" />

<Accordion title="피봇 리포트를 추가합니다.">

피봇 리포트를 추가합니다.

1. **피봇 추가**를 클릭합니다.  
   새 피봇 창이 열립니다.
2. 피봇 이름을 입력합니다.
3. **제출**을 클릭하세요.  
   피봇 테이블 추가 창이 열립니다.
4. 앱과 기준 및 지표를 선택합니다. 필터 및 값 표시 설정을 설정합니다.

| 섹션 | 설명 |
| --- | --- |
| 앱 | 피봇에 포함할 1개 이상의 앱을 선택합니다. |
| 디멘션 | [<Image alt="" src="https://files.readme.io/9b0fda106b5de3401a71ceaeb45bac5cc4215b164e263a1422bf6097a9320553-360002246845.png" width="221px" />](https://files.readme.io/9b0fda106b5de3401a71ceaeb45bac5cc4215b164e263a1422bf6097a9320553-360002246845.png)<br /><br />기준을 사용하여 피봇 리포트를 그룹화하고 구조화하며 정렬합니다.<br /><br />**기준을 선택하는 방법**:<ol><li>**기준**을 클릭합니다.</li><li>기준을 선택하고 섹션으로 끌어옵니다. 기준은 피봇에 다음과 같은 영향을 줍니다.<ul><li>5행 행: 행에 배치된 기준은 그룹별 계층을 결정합니다.</li><li>열 열: 열에 배치된 기준은 기준 값에 따라 전체 테이블 결과를 곱합니다.</li></ul></li></ol> |
| KPI | [<Image alt="" src="https://files.readme.io/6b210b1bdc38ee96ef8b73dcacbac3389b914aaef76a680604e41d4becbad807-360000640109.png" width="294px" />](https://files.readme.io/6b210b1bdc38ee96ef8b73dcacbac3389b914aaef76a680604e41d4becbad807-360000640109.png)<br /><br />KPI는 다음 유형에 따라 그룹화됩니다.<ul><li>LTV</li><li><Anchor target="_blank" href="/marketers/ko/docs/activity-dashboard#사양-및-제한-사항">액티비티(Activity)</Anchor></li><li>잔존율 유지일, 유지율. **참고**: 일러두기: 리텐션 섹션에서 아래로 스크롤하여 리텐션 비율 및 Protect360을 선택합니다(Protect360이 활성화된 계정의 경우).</li><li><Anchor target="_blank" href="/marketers/ko/docs/master-api-user-acquisition-metrics-via-api#kpis">지표 소개.</Anchor></li></ul>대부분의 경우 값 섹션에 KPI를 배치합니다. 필요한 경우 KPI를 기준으로 사용할 수 있습니다.<br /><br />KPI를 관련 섹션으로 끌어다 놓습니다. |
| 값 | 각 KPI에 대해 연산자를 선택하여 계산 방법을 설정합니다.<ul><li>합계 (Sum)</li><li>횟수</li><li>최대</li><li>최소</li><li>평가</li><li>평균</li></ul> |
| 필터 | 필터 섹션에 필요한 필터를 배치합니다. 필터 설정 방법을 구성합니다.<ul><li>텍스트</li><li>다중 선택</li></ul> |

</Accordion>

<div id="view-a-pivot-report" />

<Accordion title="피봇 리포트 보기">

[![](https://files.readme.io/cb549ba9b17e75f05d723cdb56335232dd40c419ebfe7ecad08b80a71be46296-360002246865.png)](https://files.readme.io/cb549ba9b17e75f05d723cdb56335232dd40c419ebfe7ecad08b80a71be46296-360002246865.png)

**피봇 리트를 보는 방법**:

* 피봇 페이지에서 표시할 리포트를 선택합니다.
* 리포트 표시 옵션:

| 섹션 | 설명 |
| --- | --- |
| (1) 선택된 기준 | 첫 번째 열에는 보고서를 그룹화해서 조회하려고 선택한 디멘션이 표시됩니다. 기준은 피봇 편집 페이지에서 정해진 순서에 따라 그룹화됩니다. 위의 예시에서, 기본 기준은 앱 이름이며, 그 다음 미디어소스가 표시되며 마지막은 각 인스톨 날짜입니다. |
| (2) 지표 | 나머지 열은 피봇 편집 페이지에서 **값**에 선택한 KPI입니다. 위의 예시에서, 첫 KPI는 노출 수이며, 클릭 수, 인스톨 수 등으로 이어집니다. |
| (3) 필터 | 피봇 편집 페이지에서 설정한 필터가 여기 표시됩니다. 필터링 문자열을 타이핑하거나 드롭 다운 상자에서 여러 항목을 선택할 수 있습니다.<br /><br />[**![](https://files.readme.io/e7f16a6e848b8e9f6942615dd14257b3c0e358cefabbdcfe86c498612fcaae26-115004149786.png)**](https://files.readme.io/e7f16a6e848b8e9f6942615dd14257b3c0e358cefabbdcfe86c498612fcaae26-115004149786.png) |
| (4) 선택한 날짜 | 날짜 선택기를 사용하여 특정 날짜로 검색 범위를 좁힐 수 있습니다. 커스텀 기간을 선택하거나 미리 설정된 날짜 범위 버튼 중 하나를 사용할 수 있습니다. |
| (5) 액션 | [피봇 리포트 목록](/docs/pivot-table-user-metrics#view-a-pivot-report)에서와 동일한 피봇 리포트 별 액션을 수행할 수 있습니다. |

</Accordion>

<div id="traits-and-limitations" />

## 특징 및 제약 사항

<div id="traits-and-limitations::e6883df" />

<Accordion title="특징 및 제약 사항">

| 특징 | 비고 |
| --- | --- |
| 리포트에 대한 광고 네트워크 액세스 | 아니요 |
| 에이전시 액세스 | 아니요 |
| 에이전시 투명성 | 예 |
| 앱별 시간대 | 예<br /><br />예외: 예외: 다음의 모든 경우에, 앱스플라이어는 앱 별 설정된 시간대를 무시하고 기본 시간대 UTC +0을 사용합니다.<ul><li>리포트가 여러 앱을 포함하고 있는데, 이 앱들이 각각 다른 시간대를 가지고 있습니다.</li><li>앱이 모두 동일한 시간대를 사용하고 있지만, 하나 이상의 앱이 리포트 기간 이내에 시간대를 변경했습니다. 리포트 기간을 결정하는 것은 다음과 같습니다.<ul><li>시작날짜 전환 날짜 범위의 첫 번째 날짜.</li><li>종료일. 종료 날짜: 전환일 기간의 마지막 날짜에 표시 기간의 일수를 더하여 계산합니다. 예시: 마지막 날짜: 2007년 1월 보고서 기간: 7일 종료일. 2007년 1월</li></ul></li></ul> |
| 앱별 통화 | 결과는 항상 USD로 반환됩니다. |
| 오가닉 데이터 | 포함 |
| 논오가닉 데이터 | 포함 |
| 데이터 최신성 | 데이터 최신성: 일별. 데이터 최신성은 <Anchor target="_blank" href="/marketers/ko/docs/master-api-user-acquisition-metrics-via-api">마스터 API</Anchor>의 최신성과 동일합니다. |
| 계정 유저 액세스 | 예 |
| 리타겟팅 수익 | 포함 |
| 캠페인 이름 변경 | 피봇이 캠페인 이름 비용을 최근 리포트된 캠페인 이름과 일치시키지 않습니다. 이는 사용된 각 캠페인 이름과 관련된 비용이 발생함을 의미합니다. |
| 리타게팅 데이터 | <ul><li>일반적으로 <Anchor target="_blank" href="/marketers/ko/docs/cohort-and-retention-dashboard">Cohort</Anchor>을 사용하여 리타겟팅 데이터를 봅니다.</li><li>2025년 2월 1일 이후의 트래픽에 대한 활동 KPI는 통합 데이터(UA 및 리타겟팅 포함)를 포함합니다.</li></ul> |
| 비용 데이터 | 앱스플라이어는 주로 비용 API를 통해 비용 데이터를 가져옵니다. 데이터는 연동 파트너가 제공합니다. <Anchor target="_blank" href="/marketers/ko/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">연동 파트너당 기준 목록.</Anchor> |
| 리텐션 비율 | 리텐션 비율을 확인하려면 리포트에 인스톨을 포함하세요. |
| 리포트 당 최대 행 개수 | 200K |
| 과거 데이터 | <ul><li>LTV 데이터 5년</li><li>액티비티 데이터 3년</li></ul> |

</Accordion>

<div data-zendesk-anchors="pivot-reports-page=%ED%94%BC%EB%B2%97-%EB%B3%B4%EA%B3%A0%EC%84%9C-%ED%8E%98%EC%9D%B4%EC%A7%80%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC h_01HJR8389QPFKR9X6V52N7PHMM=%ED%94%BC%EB%B2%97-%EB%B3%B4%EA%B3%A0%EC%84%9C-%ED%8E%98%EC%9D%B4%EC%A7%80%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC pivot-procedures=%ED%94%BC%EB%B4%87-%EC%A0%88%EC%B0%A8 h_01HJR8389QPNRX8Y26VQWN0ZXP=%ED%94%BC%EB%B4%87-%EC%A0%88%EC%B0%A8 pivot-page%E2%80%94controls-and-options=pivot-page-controls-and-options h_01HJR8389QDDWR8ZKCSDZGVAGP=pivot-page-controls-and-options h_01HJR8389R2C1E42JN9NFMS4CJ=add-a-pivot-report h_01HJR8389SQ40HZ8EXQME4807S=view-a-pivot-report traits-and-limitations=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD h_01HJR8389SPJZG6AYGABB17V1N=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD h_01HJR8389S19TVMVR60ZYAJMAA=traits-and-limitations::e6883df" />
