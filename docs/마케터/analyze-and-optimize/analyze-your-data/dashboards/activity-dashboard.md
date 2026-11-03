---
title: 액티비티 대시보드
metadata:
  keywords:
    - activity report
    - Advertisers
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2016-01-12T15:50:15Z'
  edited_at: '2026-10-14T10:26:44Z'
  id: 207602503
  locale: ko
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/ko/articles/207602503
---
> **한눈에 보기:** 특정 기간 동안의 앱 활동, 참여도 및 인앱 지표를 확인하세요. 현재 날짜 지표가 실시간으로 업데이트됩니다.

![ActivityDB.png](https://files.readme.io/8150eafc018c83ae2b1030702129bda12419dfac60eb8664187c2acd66136df3-4420170646289.png)

## 액티비티 대시보드

* 오가닉 및 논오가닉 트래픽을 포함합니다.
* 날짜 범위는 이벤트 날짜와 관련이 있으며 <Anchor target="_blank" href="/marketers/ko/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTV 기반</Anchor>이 아닙니다.
* 데이터 최신성:
  * **현재 날짜**: <Anchor target="_blank" href="/marketers/ko/docs/about-data-freshness-and-timezone-support#continuous-aka-realtime">지속됨</Anchor>. 예시: DAU, 세션, 수익
  * **평균:** 일별. 예시: MAU, 평균 DAU, 평균 MAU
* 지역(Geo) 필터는 인스톨 시점의 사용자 위치와 관련됩니다.

> 👍 **팁**
>
> 액티비티 대시보드에 대해 자세히 알고 싶으신가요? <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7802/play/18621/the-activity-dashboard">앱스플라이어 학습 포털에서 제공하는 짧고 유익한 강의 코스</Anchor>를 확인해 보세요.

## 대시보드 기능 및 레이아웃

<div id="metric-definitions" />

<Accordion title="지표 정의">

<Table>
  <thead>
    <tr>
      <th>
        지표
      </th>
      <th>
        설명
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="dau"></span>
        DAU
      </td>
      <td>
        * 일일 활성 사용자 수: 하루 동안 앱을 한 번 이상 연 순 사용자 수입니다.
        * DAU는 세션을 기준으로 합니다.
        * <Anchor target="_blank" href="/marketers/ko/docs/unique-users">고유 사용자에 대해 더 알아보기</Anchor>
      </td>
    </tr>
    <tr>
      <td><span id="average-dau"></span>
        평균 DAU
      </td>
      <td>
        선택한 기간 동안의 하루 평균 일일 활성 사용자 수입니다.

        예시: 평균 DAU 계산하기

        > 📄
        >
        > |  | 일요일 | 월요일 | 화요일 |
        > | --- | --- | --- | --- |
        > | <span id="daily-active-unique-users"></span>일일 활성 사용자 수 | 10 | 12 | 8 |
        >
        >
        >
        > **평균 DAU** = (10+12+8)/3= 10.
      </td>
    </tr>
    <tr>
      <td><span id="mau"></span>
        MAU
      </td>
      <td>
        월간 활성 사용자 수

        * **자세히 보기:** 지난 31일 동안 앱을 한 번 이상 연 순 사용자 수(한 번만 계산).
        * **상위 수준:** 한 달 동안 앱을 한 번 이상 연 순 사용자 수(한 번만 계산).
      </td>
    </tr>
    <tr>
      <td><span id="daumau-rate"></span>
        DAU/MAU 비율
      </td>
      <td>
        * 이 지표는 재방문 사용자 비율을 보여줍니다. DAU/MAU 비율이 50%라는 것은 평균 사용자가 지난 31일 중 15일 동안 앱을 실행했음을 의미합니다.
        * DAU/MAU 비율은 사용자 고착도를 측정하는 척도이며 사용자 유지율에 대한 스냅샷을 제공합니다.
      </td>
    </tr>
    <tr>
      <td><span id="revenue"></span>
        수익
      </td>
      <td>
        선택한 기간 동안 발생한 수익입니다. 수익은 인앱 구매(보고된 경우)와 광고 수익으로 구성됩니다.
      </td>
    </tr>
    <tr>
      <td><span id="arpdau"></span>
        ARPDAU
      </td>
      <td>
        일일 활성 사용자당 평균 수익입니다.  
        공식: [[n]일의 매출/[n]일의 DAU]] 합/일수

        > 📄 **예시: ARPDAU 계산**
        >
        > | 일 | 당일 수익($) | DAU | 평균 일일 사용자 수익($) |
        > | --- | --- | --- | --- |
        > | <span id="day-1"></span>1일 차 | 10 | 5 | 2 |
        > | <span id="day-2"></span>2일 차 | 16 | 4 | 4 |
        > | <span id="day-3"></span>3일 차 | 30 | 5 | 6 |
        > |  |  | 합계: | 12 |
        > |  <span id="::4eb0b020"></span>|  | 일수 | 3 |
        > |  <span id="::b35cc38c"></span>|  | **ARPDAU** | 4 |
      </td>
    </tr>
    <tr>
      <td><span id="sessions"></span>
        세션
      </td>
      <td>
        선택한 날짜 범위의 세션(앱에서 보고한 경우)
      </td>
    </tr>
    <tr>
      <td><span id="installs"></span>
        설치
      </td>
      <td>
        지정된 날짜 범위 동안의 설치 횟수
      </td>
    </tr>
    <tr>
      <td><span id="average-ecpi"></span>
        평균 eCPI
      </td>
      <td>
        설치당 평균 비용 참고: 설치는 UA 설치이며 비용은 통합되어 있습니다 (UA 및 리타겟팅).
      </td>
    </tr>
    <tr>
      <td><span id="conversion-rate"></span>
        전환율
      </td>
      <td>
        클릭당 설치 비율. **참고**: 설치는 UA 설치이며 클릭은 통합됩니다 (UA 및 리타겟팅).
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="detailed-tab" />

<Accordion title="상세 탭">

상세 분석 탭은 기본 측정 지표, 액티비티 트렌드, 액티비티 요약으로 나뉩니다. 

<table><tbody><tr><td colspan="2"><h4><strong><span id="headline-metrics"></span>기본 측정 지표</strong></h4></td></tr><tr><td> </td><td><img alt="ActivityHeadLines_us-en__1_.png" src="https://files.readme.io/a4f1a5316eeacf0f635bbeadf52d490dd0276bb8a1fe9c0e32db7008d11d044b-360012584838.png"/></td></tr><tr><td> </td><td> <strong>평균 활성 사용자 수</strong><ul><li>평균 DAU: 지정된 시간 범위의 일일 평균 활성 사용자 수입니다.</li><li>평균 MAU: 지정된 시간 범위의 월 평균 활성 사용자 수입니다. 이 값은 선택한 범위 내 날짜의 이동 평균으로 계산되며, 각 날짜는 31일을 거슬러 올라갑니다. 참고: 예를 들어, 3월의 MAU 값을 확인하려면 날짜 범위를 다음 달의 첫째 날(예: 4월 1일)로 설정한 후 평균 MAU 값을 확인합니다.</li></ul></td></tr><tr><td> </td><td> <strong>총 설치 수:</strong> 오가닉 인스톨과 논오가닉 인스톨로 나눈 설치 수</td></tr><tr><td> </td><td> <strong>총 세션</strong>: 세션 수를 오가닉 및 논오가닉 사용자별로 구분한 값</td></tr><tr><td> </td><td> <strong>총수익</strong>: 수익을 오가닉 및 비오가닉 사용자별로 어트리뷰트된 매출로 구분한 값</td></tr><tr><td colspan="2"><h4> <br/><strong><span id="activity-trends"></span>액티비티 트렌드</strong><br/> </h4></td></tr><tr><td> </td><td><p> <strong>비교 가능한 추세선</strong></p><p><img alt="TrendLinWithComp_us-en.png" src="https://files.readme.io/b9edb3e409dc13bc72aebdccdc499fa2dcd9abf4549fb0170bf0cdc7036eee15-360012507997.png"/></p><ul><li>트렌드 차트는 KPI 또는 인앱이벤트 관련 측정을 표시합니다.</li><li> <strong>이전</strong> 기간(일, 주, 월, 분기, 연도)과 <strong>비교</strong>를 활성화하여 비교 추세선(선택 사항)을 추가할 수 있습니다. </li><li>예를 들어 '월'을 선택하면 차트에서 특정 날짜에 대해 전월의 같은 날과 비교한다는 의미입니다. </li></ul><p>사용 가능한 KPI는 다음과 같습니다.</p><ul><li><span>DAU</span></li><li><span>MAU</span></li><li><span>수익</span></li><li><span>ARPDAU</span></li><li><span>세션</span></li><li><span>DAU/MAU 비율</span></li></ul><p><span>사용 가능한 인앱 이벤트 대책은 다음과 같습니다.</span></p><ul><li><span>횟수</span></li><li><span>고유 사용자</span></li><li><span>수익</span></li></ul></td></tr><tr><td colspan="2"><h4> <br/><strong><span id="activity-summary-table"></span>액티비티 요약 표</strong> </h4></td></tr><tr><td> </td><td><p>액티비티 요약 표에서는</p><ul><li>노출 수, 클릭 수 및 설치 수 등과 관련된 데이터와 함께 최대 50개의 미디어소스를 표시합니다. (모든 데이터를 가져오려면 <a href="./master-api-user-acquisition-metrics-via-api" target="_blank">마스터 API</a> 또는 <a href="./pivot-table-user-metrics" target="_blank">피벗</a>을 사용하세요.) </li><li>세션 수에 따라 정렬됩니다. </li><li>캠페인 수준까지 드릴다운할 수 있는 기능을 제공합니다(이 수준 이상은 드릴다운 불가).</li><li>신규 사용자 수와 기존 사용자 수(DAU에서 설치 수를 뺀 수)를 확인할 수 있는 좋은 방법입니다.</li></ul><p><span>요약 표를 사용하는 방법:</span></p><ul><li><span>필터링 기준 및 그룹화 기준 필드를 사용하여 표시되는 데이터를 구체화합니다.</span></li><li><span>표 열은 열 머리글을 클릭하여 정렬할 수 있습니다.</span></li><li> <strong>인앱 이벤트</strong> 별로 필터링하여 특정 인앱 이벤트로 표시를 제한합니다.</li><li>다양한 보기 유형으로 전환합니다.<ul><li> <strong>요약:</strong> 선택한 모든 인앱 이벤트의 합계</li><li> <strong>인앱</strong> <strong>이벤트</strong> 인앱 이벤트별로 분류</li></ul></li></ul></td></tr></tbody></table>

</Accordion>

<div id="highlevel-tab-previous-twelvemonths" />

<Accordion title="상위 수준 탭: 지난 12개월">

![ActivityHiLevel.png](https://files.readme.io/42636f5b13dca3a2209ea295c02e784175dfc92a2523c861220b87baed859541-4420194466065.png)

이 탭에는 앱 활동 실적에 대한 12개월간의 기록 개요가 포함되어 있으며, 다음과 같은 차트가 제공됩니다. 

* 활성 사용자 및 수익
* 월별 총이익: 매출, 비용, 총이익

</Accordion>

## 사양 및 제한 사항

| 사양 | 비고 |
| --- | --- |
| 데이터 최신성 | <ul><li>**지표:** 실시간. 다음 이미지를 참조하세요.</li><li>**평균 지표**: 일별. 다음 이미지를 참조하세요. **참고**: 불완전한 날짜의 데이터로 평균이 왜곡되는 것을 방지하기 위해 평균 지표는 실시간으로 계산되지 않습니다. 날짜 범위에 현재 날짜가 포함된 경우 다음과 같은 일이 발생합니다.<ul><li>날짜 범위가 현재 날짜에만 해당하는 경우: 평균 결과는 표시되지 않습니다.</li><li>날짜 범위가 현재 날짜가 포함된 기간인 경우: 현재 날짜의 데이터를 포함하지 않고 평균을 계산합니다.</li></ul></li><li>**광고 수익:** <Anchor target="_blank" href="/marketers/ko/docs/roi360-guide-ad-revenue-attribution#data-freshness">시차를 두고 기록되며</Anchor> 다음 날짜에 보고됩니다.<ul><li>집계 수준 데이터: 1일 차(데이터를 가져온 날) 미만입니다.</li><li>사용자 수준 데이터: 0일 차(광고가 게재된 날) 미만입니다.</li></ul></li></ul>[![Whats_realtime.png](https://files.readme.io/39969fe7395e1b22910aed5d6ca61f6b5603171650f0d0ce88218a2491c02cc5-4407209143953.png)](https://files.readme.io/39969fe7395e1b22910aed5d6ca61f6b5603171650f0d0ce88218a2491c02cc5-4407209143953.png) |
| 앱 삭제 | 지원되지 않음 |
| 리타겟팅 | 2025년 2월 1일 기준으로 모든 액티비티 지표는 통합 데이터(UA 및 리타겟팅 포함)입니다. 2025년 2월 1일 이전 데이터의 경우, 다음 지표는 UA 트래픽 데이터만 포함합니다.<ul><li>총 세션</li><li>DAU</li><li>MAU</li><li>DAU/MAU</li><li>ARPDAU</li><li>비용</li><li>클릭</li><li>노출</li><li>전환율</li><li>eCPI</li></ul>통합된 보기만 사용 가능하며, 사용자는 UA 또는 리타겟팅으로 전환할 수 없습니다. |
| ARPDAU | 액티비티 대시보드의 ARPDAU와 피벗 간에 차이가 있을 수 있습니다. |
| 기록 데이터 | <ul><li>3년</li><li>상위 수준 탭: 1년</li></ul> |
| 표시 범위 | <ul><li>최대 2개월. 기간을 더 길게 지정하면 범위가 2개월로 줄어들고 메시지가 표시됩니다.</li></ul> |
| 지역별로 그룹화 | <ul><li>지리(Geo)별 집약은 앱이 설치된 지리적 위치를 기준으로 이루어집니다.</li><li>최대 62개의 지역을 표시합니다. (상위 액티비티 세션 순서로 정렬)</li></ul> |
| 캠페인별 그룹화 | 이 그룹화는 특정 미디어소스를 선택한 후에만 사용할 수 있습니다. |
| 데이터 기준 값 | 미디어 소스, 캠페인 이름 및 애셋 이름과 같은 데이터 기준 값은 대소문자를 구분합니다. 예를 들어, 이는 "Facebook"과 "facebook"이 결과를 필터링할 때 별개의 값으로 취급된다는 것을 의미합니다. 대소문자를 구분하지 않고 결과를 보려면 <Anchor target="_blank" href="/marketers/ko/docs/pivot-table-user-metrics">피벗 테이블</Anchor>을 사용하세요. |
| 에이전시 | 에이전시는 액티비티 대시보드에 접근할 수 없습니다. <Anchor target="_blank" href="/marketers/ko/docs/manage-data-access-permissions">더 알아보기</Anchor> |

<div data-zendesk-anchors="activity-dashboard=%EC%95%A1%ED%8B%B0%EB%B9%84%ED%8B%B0-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C h_01HHYHP1HE8G5VA6GSAVTQDDDN=%EC%95%A1%ED%8B%B0%EB%B9%84%ED%8B%B0-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C h_01HHYHP1HEJHKQKCNC5R26ZE3J=%ED%8C%81 dashboard-features-and-layout=%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C-%EA%B8%B0%EB%8A%A5-%EB%B0%8F-%EB%A0%88%EC%9D%B4%EC%95%84%EC%9B%83 h_01HHYHP1HEBTACW6Q3MJ3QJJ95=%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C-%EA%B8%B0%EB%8A%A5-%EB%B0%8F-%EB%A0%88%EC%9D%B4%EC%95%84%EC%9B%83 h_01HHYHP1HESQBPYJWK81ZHQDVH=metric-definitions h_01HHYHP1HFZBRTWB8MJ1F6XKZS=%EC%98%88%EC%8B%9C-arpdau-%EA%B3%84%EC%82%B0 h_01HHYHP1HFF92WQMQAFKWWNDJK=detailed-tab h_01HHYHP1HFNDXC2E55Q7PDE9WY=headline-metrics h_01HHYHP1HFZR9JN2H0RNAG1QTK=activity-trends h_01HHYHP1HFV8AZ2FYKJ300488A=activity-summary-table h_01HHYHP1HF6FCXPS2SHTH0RBXC=highlevel-tab-previous-twelvemonths specifications-and-limitations=%EC%82%AC%EC%96%91-%EB%B0%8F-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD h_01HHYHP1HFNJF4JJZY4CSVZ3GY=%EC%82%AC%EC%96%91-%EB%B0%8F-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD" />
