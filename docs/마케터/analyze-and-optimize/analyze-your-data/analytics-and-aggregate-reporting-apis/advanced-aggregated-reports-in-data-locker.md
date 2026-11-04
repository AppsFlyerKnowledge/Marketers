---
title: 데이터 락커의 고급 집계 리포트
metadata:
  keywords:
    - Premium
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
  created_at: '2024-03-06T10:46:12Z'
  edited_at: '2026-10-14T10:29:37Z'
  id: 23127074968721
  locale: ko
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/ko/articles/23127074968721
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **간단히 보기**: 데이터 락커의 고급 집계 보고서에는 최적의 데이터 최신성, 정확성, 세분성 및 무제한 볼륨으로 집계된 데이터가 포함됩니다.

<div id="advanced-aggregated-reports-in-data-locker" />

## 데이터 락커의 고급 집계 리포트

데이터 락커의 고급 집계 보고서:

* 집계된 데이터를 기반으로 내부 BI 시스템을 구축할 수 있는 효율적이고 개인 정보를 보호하는 방법을 제공합니다. 어트리뷰션, 이벤트 및 수익 데이터와 가능한 모든 차원 및 지표를 제공합니다.
* 데이터를 BI 시스템에 로드하여 캠페인 성과 및 최적화 프로세스의 일부로 사용할 수 있습니다.
* 데이터 최신성을 정확하게 유지하세요. 데이터는 <Anchor target="_blank" href="/marketers/ko/docs/about-data-freshness-and-timezone-support#intraday-during-the-day">하루에 여러 번</Anchor> 도착하며 해당 날짜에 사용 가능한 모든 데이터와 함께 보고서의 각 후속 버전으로 업데이트됩니다.
* 미디어 소스 데이터 공유 정책 또는 <Anchor target="_blank" href="/marketers/ko/docs/apply-aggregated-advanced-privacy-framework">개인 정보 보호 정책</Anchor>으로 인해 <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions">제한</Anchor>될 수 있는 원시 데이터를 보강하는 데 도움이 됩니다. 이러한 제한은 캠페인 및 광고 세트와 같은 어트리뷰션 관련 필드에 영향을 미칩니다.

<div id="setup" />

## 설정

고급 집계 보고서를 가져오려면 다음 절차 중 하나를 완료하십시오.

| 현재 데이터 락커를 통해 데이터를 받고 계신가요? | 절차 |
| --- | --- |
| Yes | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)데이터 락커에 리포트를 추가하려면:<ol><li>앱스플라이어의 사이드 메뉴에서 **내보내기 > 데이터 락커**를 선택합니다.</li><li>가져올 리포트를 모두 선택합니다.</li><li>**구성 저장**을 클릭합니다.<br />리포트는 다음 날 사용할 수 있습니다.</li></ol> |
| 아니요 | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)**To set up Data Locker**:<ol><li>최초 데이터 락커(<Anchor target="_blank" href="/marketers/ko/docs/data-locker-for-marketers#set-up-data-locker">광고주</Anchor> \| <Anchor target="_blank" href="/partners/ko/docs/data-locker-for-partners">파트너</Anchor>) 설정을 완료하십시오.</li><li>데이터 락커에 리포트를 추가합니다.<ol><li>앱스플라이어의 사이드 메뉴에서 **내보내기 > 데이터 락커**를 선택합니다.</li><li>가져올 리포트를 모두 선택합니다.</li><li>**구성 저장**을 클릭합니다.<br />리포트는 다음 날 사용할 수 있습니다.</li></ol></li></ol> |

<div id="reports-available" />

## 사용 가능한 리포트

<div id="report-facts" />

### 사실 보고

| 개요 | 코호트 버전 보고서에는 모든 캠페인 차원 세분성과 함께 코호트화된 모든 집계 데이터가 포함됩니다. 보고서는 데이터 최신성과 정확성을 최대화하기 위해 몇 시간마다 업데이트됩니다.<br /><br /><Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vT8NQKO287TxXpdTYpIASL55t4muIt9G3lnkEE436FQhNn5_14DfYgf0ztbm1VVZXI4ecPaGktdixS7/pub?output=xlsx">샘플 보고서 다운로드</Anchor> |
| --- | --- |
| 사용 가능한 리포트 | 다음 리포트를 다운로드할 수 있습니다. 보고서 유형은 코호트 대시보드에 자세히 설명되어 있습니다.<ul><li>**사용자 획득:** 리인게이지먼트 윈도우 동안 발생하는 LTV를 포함한 사용자 획득 미디어 소스를 통해 어트리뷰트됩니다.</li><li>**리타게팅:** 발생한 이벤트에 대한 리타게팅 미디어 소스를 통해 어트리뷰트됩니다:<ul><li>리인게이지먼트 기간 동안</li><li>리어트리뷰션의 결과</li></ul></li><li>**통합:** 앱스플라이어의 <Anchor target="_blank" href="/marketers/ko/docs/resolve-retargeting-double-attribution">이중 어트리뷰션</Anchor> 규칙에 따라 최종 터치 미디어 소스에서 데이터를 표시합니다. 즉, 재참여 중에 발생하는 LTV는 사용자 획득 미디어 대신 리타게팅 미디어 소스에 표시됩니다.</li></ul> |
| 리포팅 기간 | 지난 1,095일 동안 전환한 사용자입니다. 즉, 보고서에는 매일 이전 1,095일 동안 전환한 사용자의 이벤트가 포함됩니다. |
| 리포트 구조 | 보고서의 스키마 (측정기준 및 측정항목 포함)는 고정되어 있으며 수정할 수 없습니다. |
| 데이터 최신성 | <ul><li>당일 내 보고서는 몇 시간마다 전송됩니다.</li><li>보고서는 해당 날짜의 데이터에 대한 것입니다. 즉, 4월 18일의 모든 보고서 버전에는 4월 18일의 모든 현재 데이터가 포함됩니다. [더 알아보기](/docs/advanced-aggregated-reports-in-data-locker#보고서-버전-및-데이터-새로-고침)</li></ul> |
| 시간대 | UTC |
| 디렉터리 및 파일 이름 구조 | [더 알아보기](/docs/advanced-aggregated-reports-in-data-locker#리포트-구조) |
| 파트너의 데이터 보존 정책의 영향 | 일부 파트너는 데이터 보존 정책을 시행할 수 있습니다. 이 경우, 보존 기간이 끝난 후 발생한 이벤트는 코호트 보고서에서 오가닉으로 간주됩니다.<br /><br />예시: SRN A의 데이터 보존 정책은 180일입니다. |

<div id="report-structure" />

### 리포트 구조

보고서는 차원과 지표로 구성됩니다.

필드의 형식은 다음과 같습니다.

* **차원**: 문자열입니다. 문자열의 최대 길이는 동적으로, 대부분 광고 계층 구조의 요소를 어떻게 채우느냐에 따라 달라집니다.
* **지표**: 숫자입니다. **참고:** selected\_currency 필드 형식은 문자열입니다.  
  사용할 수 있는 지표는 수익, 이벤트를 수행하는 고유 사용자 및 이벤트 발생 횟수입니다. ROI 및 ROAS와 같은 비용 관련 지표를 계산하려면 수익 및 비용 지표가 모두 있어야 합니다. 수익 지표는 코호트에서 제공되며, 비용 지표는 ROI360 Cost ETL에서 제공됩니다.

<div id="dimensions" />

#### 디멘션

<Table>
  <thead>
    <tr>
      <th>
        필드 이름
      </th>
      <th>
        설명
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        app\_id
      </td>
      <td>

      </td>
    </tr>
    <tr>
      <td>
        media\_source
      </td>
      <td>

      </td>
    </tr>
    <tr>
      <td>
        conversion\_type
      </td>
      <td>
        가능한 값: 설치, install\_unified (통합 보고서에서 설치를 나타냄), 재참여, 재어트리뷰션
      </td>
    </tr>
    <tr>
      <td>
        attributed\_touch\_type
      </td>
      <td>
        가능한 값: 클릭, 노출, 사전 설치, 알 수 없음, TV, null
      </td>
    </tr>
    <tr>
      <td>
        days\_post\_attribution
      </td>
      <td>
        * 전환 날짜 이후 경과된 일수(특정 전환 타임스탬프 아님).
        * 팁! 이를 사용하여 보존 기간 및 KPI 일수를 계산합니다
      </td>
    </tr>
    <tr>
      <td>
        이벤트 날짜
      </td>
      <td>
        * 사용자가 지정된 이벤트를 수행하는 날짜입니다.
        * 형식: yyyy-mm-dd
        * 예시: 사용자가 지정된 인앱 이벤트를 수행한 날짜입니다. 전환의 경우.
        * 참고! event\_name이 af\_conversion인 경우, 이벤트 날짜와 전환 날짜는 동일합니다.
      </td>
    </tr>
    <tr>
      <td>
        conversion\_date
      </td>
      <td>
        * 전환이 발생한 날짜
        * 형식: yyyy-mm-dd
        * 예시: 설치 날짜
      </td>
    </tr>
    <tr>
      <td>
        event\_name
      </td>
      <td>
        이벤트를 식별합니다. 일부 이벤트 이름은 특정 의미를 갖지만, 다른 이벤트 이름은 앱에서 광고주가 설정한 인앱이벤트와 관련됩니다. 

        | event\_name | 사용자가 수행한 작업 |
        | --- | --- |
        | af\_conversion | 사용자가 전환했습니다. conversion\_type을 사용하여 인스톨인지, 리인게이지먼트인지 또는 리어트리뷰션인지를 식별합니다. |
        | af\_세션 | 앱 실행 |
        | 코호트 분석 | 앱 삭제 |
        | 광고주가 인앱이벤트 정의 | 앱에서 인앱이벤트를 실행했습니다. |
      </td>
    </tr>
    <tr>
      <td>
        campaign
      </td>
      <td>
        캠페인 구조

        고려 사항: 캠페인 이름 변경은 지원되지 않습니다. 따라서 지정된 캠페인 ID에 여러 이름을 연결할 수 있습니다.
      </td>
    </tr>
    <tr>
      <td>
        campaign\_id
      </td>
      <td>
        캠페인 구조
      </td>
    </tr>
    <tr>
      <td>
        광고 세트
      </td>
      <td>
        캠페인 구조
      </td>
    </tr>
    <tr>
      <td>
        adset\_id
      </td>
      <td>
        캠페인 구조
      </td>
    </tr>
    <tr>
      <td>
        광고
      </td>
      <td>
        캠페인 구조
      </td>
    </tr>
    <tr>
      <td>
        ad\_id
      </td>
      <td>
        캠페인 구조
      </td>
    </tr>
    <tr>
      <td>
        channe
      </td>
      <td>
        캠페인 구조.

        [2021년 10월 27일 업데이트] 현재 Meta 광고는 Google 설치 리퍼러 메커니즘을 통해 제공된 데이터에서 채널을 비워둡니다.
      </td>
    </tr>
    <tr>
      <td>
        site\_id
      </td>
      <td>
        캠페인 구조
      </td>
    </tr>
    <tr>
      <td>
        is\_primary\_attribution
      </td>
      <td>
        리타게팅 데이터를 식별하고 중복을 제거하는 데 사용합니다.
      </td>
    </tr>
    <tr>
      <td>
        geo
      </td>
      <td>
        사용자 IP 주소로부터 파생된 ISO 국가 코드입니다.
      </td>
    </tr>
    <tr>
      <td>
        agency
      </td>
      <td>
        * 에이전시 투명성 지원.
        * 비투명한 에이전시의 경우, 광고주와 에이전시가 동일한 이름의 캠페인을 진행하면 동일한 캠페인 이름을 가진 행이 여러 개 존재할 수 있습니다. 걱정하지 마세요. 행은 중복되지 않습니다.
      </td>
    </tr>
    <tr>
      <td>
        install\_app\_store
      </td>
      <td>
        Android 앱만 해당: 앱이 다운로드된 Android 스토어입니다. <Anchor target="_blank" href="/marketers/ko/docs/set-up-multi-store-android-attribution">다중 스토어 안드로이드 어트리뷰션</Anchor>을 구현하는 광고주가 채웁니다. 비어 있으면 구글 플레이 스토어를 의미합니다.
      </td>
    </tr>
    <tr>
      <td>
        키워드
      </td>
      <td>
        유저가 온라인 검색 시 사용한 단어들입니다. 애드 네트워크에서 보고된 내용입니다.
      </td>
    </tr>
    <tr>
      <td>
        keyword\_id
      </td>
      <td>
        애드 네트워크에 의해 반환된 키워드 ID입니다.
      </td>
    </tr>
  </tbody>
</Table>

<div id="metrics" />

#### 측정 지표

| 필드 이름 | 설명 | 형식 |
| --- | --- | --- |
| unique\_users | 이벤트를 수행하는 당일 고유 사용자 수입니다. | 숫자 |
| revenue\_usd | <ul><li>수익 금액(USD)입니다. 예를 들어, $100.56은 100.56으로 반영됩니다.</li><li>소수점 이하 2자리까지 가능.</li></ul> | 숫자 |
| event\_count | 이벤트 발생 횟수입니다. | 숫자 |
| selected\_currency | 앱 설정에서 설정한 3자리 통화 코드(USD, EUR). <Anchor target="_blank" href="http://www.xe.com/symbols.php#section1">ISO-4217</Anchor> 형식. 이는 사용자 인터페이스에서 코호트의 수익을 표시하는 데 사용되는 통화와 동일합니다. | 문자열 |
| revenue\_selected\_currency | <ul><li>선택한 통화의 수익 금액입니다. 예를 들어 선택한 통화가 EUR인 경우 €1234.56는 1234.56으로 반영됩니다.</li><li>소수점 이하 2자리까지 가능</li></ul> | 숫자 |
| first\_inapp | <ul><li>전환 후 처음으로 이벤트를 수행하는 사용자 수입니다.</li><li>first\_inapp 지표를 합산하면 이벤트에 대한 누적 고유 사용자 수를 얻을 수 있습니다.</li></ul> | 숫자 |

<div id="directory-and-filename-structure" />

#### 디렉터리 및 파일 이름 구조

보고서 경로는 다음과 같은 폴더 계층으로 구성됩니다.

다음 형식으로: `/t=cohort_unified_versioned/dt=/version=/`

<div id="report-folder-hierarchy" />

#### 보고서 폴더 계층 구조

광고주 버킷의 코호트 버전이 지정된 보고서 폴더 계층 구조의 예는 다음과 같습니다.

```
bucket
|
└── t=cohort_unified_versioned
    |
    ├── dt=2024-05-05
    |   |
    |   └── version=1714890235
    |   |    |
    |   |    ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |    |
    |   |    ├── part-00001-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |    │
    |   |    └── part-00002-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |
    |   |
    |   └── version=1714890286
    |        |
    |        ├── part-00000-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        |
    |        ├── part-00001-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        │
    |        └── part-00002-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |   |
    .   . 
    .   .
```

**범례:**

* **dt**: 보고서에 포함된 이벤트가 발생한 날짜.
* **t:** 보고서 유형.
* **버전**: 버전이 생성되었을 때의 Unix 타임스탬프.

<div id="report-versions-and-data-freshness" />

### 보고서 버전 및 데이터 새로 고침

* 당일 내 보고서는 몇 시간마다 전송됩니다.
* 보고서는 해당 날짜에 현재 사용할 수 있는 모든 데이터에 대한 것입니다. 즉, 4월 18일의 모든 보고서 버전에는 4월 18일 해당 시점까지 사용 가능한 모든 데이터가 포함됩니다.
* **사용 가능한 최신 보고서 버전만 수집합니다.**

| 버전 | 보고서에는 앱스플라이어가 수신한 데이터(UTC 시간)가 포함됩니다. | 적용 사례 | 시간 보고서를 사용할 수 있습니다(UTC 시간). |
| --- | --- | --- | --- |
| 1 | 0일 오전 4시 | 0일차에 대한 부분 데이터 | 0일 오전 8시 |
| 2 | 0일 오전 8시 | 0일차에 대한 부분 데이터 | 0일 오후 1시 |
| 3 | 0일 오후 12시 | 0일차에 대한 부분 데이터 | 0일 오후 6시 |
| 4 | 0일 오후 4시 | 0일차에 대한 부분 데이터 | 0일 오후 9시 |
| 5 | 0일 오후 8시 | 0일차에 대한 부분 데이터 | 0일 오후 11:59 |
| 6 | 0일 오후 11:59 | Day 0의 전체 전환 및 인앱 이벤트 데이터(Day 0 오후 11:59부터 Day 1 AM 2 사이에 앱스플라이어가 수신하는 S2S 이벤트 제외) | 1일차 오전 4시 |
| 7 | 1일차 오전 3시 | 0일차의 전체 전환 및 인앱 이벤트 데이터와 S2S를 통해 전송된 현재 사용 가능한 광고 수익 데이터 | 1일차 오전 8시 |
| 8 | 1일차 오전 11시 | 0일차의 전체 전환 및 인앱 이벤트 데이터와 S2S를 통해 전송된 현재 사용 가능한 광고 수익 데이터 | 1일차 오후 6시 |
| 9 | 1일차 오후 5시 | 0일차의 전체 전환 및 인앱 이벤트 데이터와 S2S를 통해 전송된 현재 사용 가능한 광고 수익 데이터 | 1일 오후 11:59 |
| 10 | 8일차 오전 7시 | 0일차의 전체 전환 및 인앱 이벤트 데이터와 S2S를 통해 전송된 전체 광고 수익 데이터(광고 수익 네트워크 측에서 발생할 수 있는 잠재적 문제를 고려) | 8일차 오후 1시 |


<div id="report-facts-1" />

### 사실 보고

| 개요 | 코호트 시간대 버전 보고서에는 현지화된 시간대에 따라 모든 캠페인 측정기준 세분성과 함께 코호트된 모든 집계 데이터가 포함됩니다. 보고서는 데이터 최신성과 정확성을 최대화하기 위해 몇 시간마다 업데이트됩니다.<br /><br /><Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQk1cZkeJhlx3trW13SjGbD4aWX3LmXZJRDJRApuAJkjB7XAg4nSFUyN0_YoirX-QMHkhFeMHwEmiVj/pub?output=xlsx">샘플 보고서 다운로드</Anchor> |
| --- | --- |
| 사용 가능한 리포트 | 다음 리포트를 다운로드할 수 있습니다. 보고서 유형에 대한 세부 정보는 <Anchor target="_blank" href="/marketers/ko/docs/cohort-and-retention-dashboard#cohort-principles">코호트 대시보드</Anchor>에서 확인할 수 있습니다.<ul><li>**사용자 획득:** 리인게이지먼트 윈도우 동안 발생하는 LTV를 포함한 사용자 획득 미디어 소스를 통해 어트리뷰트됩니다.</li><li>**리타게팅:** 발생한 이벤트에 대한 리타게팅 미디어 소스를 통해 어트리뷰트됩니다:<ul><li>리인게이지먼트 기간 동안</li><li>리어트리뷰션의 결과</li></ul></li><li>**통합:** 앱스플라이어의 <Anchor target="_blank" href="/marketers/ko/docs/resolve-retargeting-double-attribution">이중 어트리뷰션</Anchor> 규칙에 따라 최종 터치 미디어 소스에서 데이터를 표시합니다. 즉, 재참여 중에 발생하는 LTV는 사용자 획득 미디어 대신 리타게팅 미디어 소스에 표시됩니다.</li></ul> |
| 리포팅 기간 | 지난 1,095일 동안 전환한 사용자입니다. 즉, 보고서에는 매일 이전 1,095일 동안 전환한 사용자의 이벤트가 포함됩니다.<br /><br />**참고**: 현지 시간대로 하루가 아직 시작되지 않은 경우 시간대 버전 보고서는 데이터 없이 도착합니다. |
| 리포트 구조 | 보고서의 스키마 (측정기준 및 측정항목 포함)는 고정되어 있으며 수정할 수 없습니다. |
| 데이터 최신성 | <ul><li>당일 내 보고서는 몇 시간마다 전송됩니다.</li><li>보고서는 해당 날짜의 데이터에 대한 것입니다. 즉, 4월 18일의 모든 보고서 버전에는 4월 18일의 모든 현재 데이터가 포함됩니다. [더 알아보기](/docs/advanced-aggregated-reports-in-data-locker#보고서-버전-및-데이터-새로-고침-1)</li></ul> |
| 시간대 | UTC를 제외한 모든 시간대입니다. 즉, 리포트는 앱스플라이어에서 UTC 시간대로 설정된 모든 앱에 대한 데이터를 제외합니다. |
| 디렉터리 및 파일 이름 구조 | [더 알아보기](/docs/advanced-aggregated-reports-in-data-locker#리포트-구조-1) |
| 파트너의 데이터 보존 정책의 영향 | 일부 파트너는 데이터 보존 정책을 시행할 수 있습니다. 이 경우 리텐션 기간 종료 이후에 발생하는 이벤트는 코호트 리포트에서 무시됩니다.<br /><br />예시: SRN A의 데이터 보존 정책은 180일입니다.<br /><br />**참고**: 이벤트는 개요 대시보드에 오가닉으로 표시됩니다. |

<div id="report-structure-1" />

### 리포트 구조

보고서는 차원과 지표로 구성됩니다.

필드의 형식은 다음과 같습니다.

* **차원**: 문자열입니다. 문자열의 최대 길이는 동적으로, 대부분 광고 계층 구조의 요소를 어떻게 채우느냐에 따라 달라집니다.
* **지표**: 숫자입니다. **참고:** selected\_currency 필드 형식은 문자열입니다.  
  사용할 수 있는 지표는 수익, 이벤트를 수행하는 고유 사용자 및 이벤트 발생 횟수입니다. ROI 및 ROAS와 같은 비용 관련 지표를 계산하려면 수익 및 비용 지표가 모두 있어야 합니다. 수익 지표는 코호트에서 제공되며, 비용 지표는 ROI360 Cost ETL에서 제공됩니다.

<div id="dimensions-1" />

#### 디멘션

<Table>
  <thead>
    <tr>
      <th>
        필드 이름
      </th>
      <th>
        설명
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        app\_id
      </td>
      <td>

      </td>
    </tr>
    <tr>
      <td>
        media\_source
      </td>
      <td>

      </td>
    </tr>
    <tr>
      <td>
        conversion\_type
      </td>
      <td>
        가능한 값: 설치, install\_unified (통합 보고서에서 설치를 나타냄), 재참여, 재어트리뷰션
      </td>
    </tr>
    <tr>
      <td>
        attributed\_touch\_type
      </td>
      <td>
        가능한 값: 클릭, 노출, 사전 설치, 알 수 없음, TV, null
      </td>
    </tr>
    <tr>
      <td>
        days\_post\_attribution
      </td>
      <td>
        * 전환 날짜 이후 경과된 일수(특정 전환 타임스탬프 아님).
        * 팁! 이를 사용하여 보존 기간 및 KPI 일수를 계산합니다
      </td>
    </tr>
    <tr>
      <td>
        이벤트 날짜
      </td>
      <td>
        * 사용자가 지정된 이벤트를 수행하는 날짜입니다.
        * 형식: yyyy-mm-dd
        * 예시: 사용자가 지정된 인앱 이벤트를 수행한 날짜입니다. 전환의 경우.
        * 참고! event\_name이 af\_conversion인 경우, 이벤트 날짜와 전환 날짜는 동일합니다.
      </td>
    </tr>
    <tr>
      <td>
        conversion\_date
      </td>
      <td>
        * 전환이 발생한 날짜
        * 형식: yyyy-mm-dd
        * 예시: 설치 날짜
      </td>
    </tr>
    <tr>
      <td>
        event\_name
      </td>
      <td>
        이벤트를 식별합니다. 일부 이벤트 이름은 특정 의미를 갖지만, 다른 이벤트 이름은 앱에서 광고주가 설정한 인앱이벤트와 관련됩니다. 

        | event\_name | 사용자가 수행한 작업 |
        | --- | --- |
        | af\_conversion | 사용자가 전환했습니다. conversion\_type을 사용하여 인스톨인지, 리인게이지먼트인지 또는 리어트리뷰션인지를 식별합니다. |
        | af\_세션 | 앱 실행 |
        | 코호트 분석 | 앱 삭제 |
        | 광고주가 인앱이벤트 정의 | 앱에서 인앱이벤트를 실행했습니다. |
      </td>
    </tr>
    <tr>
      <td>
        event\_timezone
      </td>
      <td>
        시간대:

        * days\_post\_atribution
        * 이벤트 날짜
        * conversion\_date
      </td>
    </tr>
    <tr>
      <td>
        campaign
      </td>
      <td>
        캠페인 구조

        고려 사항: 캠페인 이름 변경은 지원되지 않습니다. 따라서 지정된 캠페인 ID에 여러 이름을 연결할 수 있습니다.
      </td>
    </tr>
    <tr>
      <td>
        campaign\_id
      </td>
      <td>
        캠페인 구조
      </td>
    </tr>
    <tr>
      <td>
        광고 세트
      </td>
      <td>
        캠페인 구조
      </td>
    </tr>
    <tr>
      <td>
        adset\_id
      </td>
      <td>
        캠페인 구조
      </td>
    </tr>
    <tr>
      <td>
        광고
      </td>
      <td>
        캠페인 구조
      </td>
    </tr>
    <tr>
      <td>
        ad\_id
      </td>
      <td>
        캠페인 구조
      </td>
    </tr>
    <tr>
      <td>
        channe
      </td>
      <td>
        캠페인 구조.

        [2021년 10월 27일 업데이트] 현재 Meta 광고는 Google 설치 리퍼러 메커니즘을 통해 제공된 데이터에서 채널을 비워둡니다.
      </td>
    </tr>
    <tr>
      <td>
        site\_id
      </td>
      <td>
        캠페인 구조
      </td>
    </tr>
    <tr>
      <td>
        is\_primary\_attribution
      </td>
      <td>
        리타게팅 데이터를 식별하고 중복을 제거하는 데 사용합니다.
      </td>
    </tr>
    <tr>
      <td>
        geo
      </td>
      <td>
        사용자 IP 주소로부터 파생된 ISO 국가 코드입니다.
      </td>
    </tr>
    <tr>
      <td>
        agency
      </td>
      <td>
        * 에이전시 투명성 지원.
        * 비투명한 에이전시의 경우, 광고주와 에이전시가 동일한 이름의 캠페인을 진행하면 동일한 캠페인 이름을 가진 행이 여러 개 존재할 수 있습니다. 걱정하지 마세요. 행은 중복되지 않습니다.
      </td>
    </tr>
    <tr>
      <td>
        install\_app\_store
      </td>
      <td>
        Android 앱만 해당: 앱이 다운로드된 Android 스토어입니다. <Anchor target="_blank" href="/marketers/ko/docs/set-up-multi-store-android-attribution">다중 스토어 안드로이드 어트리뷰션</Anchor>을 구현하는 광고주가 채웁니다. 비어 있으면 구글 플레이 스토어를 의미합니다.
      </td>
    </tr>
    <tr>
      <td>
        키워드
      </td>
      <td>
        유저가 온라인 검색 시 사용한 단어들입니다. 애드 네트워크에서 보고된 내용입니다.
      </td>
    </tr>
    <tr>
      <td>
        keyword\_id
      </td>
      <td>
        애드 네트워크에 의해 반환된 키워드 ID입니다.
      </td>
    </tr>
  </tbody>
</Table>

<div id="metrics-1" />

#### 측정 지표

| 필드 이름 | 설명 | 형식 |
| --- | --- | --- |
| unique\_users | 이벤트를 수행하는 당일 고유 사용자 수입니다. | 숫자 |
| revenue\_usd | <ul><li>수익 금액(USD)입니다. 예를 들어, $100.56은 100.56으로 반영됩니다.</li><li>소수점 이하 2자리까지 가능.</li></ul> | 숫자 |
| event\_count | 이벤트 발생 횟수입니다. | 숫자 |
| selected\_currency | 앱 설정에서 설정한 3자리 통화 코드(USD, EUR). <Anchor target="_blank" href="http://www.xe.com/symbols.php#section1">ISO-4217</Anchor> 형식. 이는 사용자 인터페이스에서 코호트의 수익을 표시하는 데 사용되는 통화와 동일합니다. | 문자열 |
| revenue\_selected\_currency | <ul><li>선택한 통화의 수익 금액입니다. 예를 들어 선택한 통화가 EUR인 경우 €1234.56는 1234.56으로 반영됩니다.</li><li>소수점 이하 2자리까지 가능</li></ul> | 숫자 |
| first\_inapp | <ul><li>전환 후 처음으로 이벤트를 수행하는 사용자 수입니다.</li><li>first\_inapp 지표를 합산하면 이벤트에 대한 누적 고유 사용자 수를 얻을 수 있습니다.</li></ul> | 숫자 |

<div id="directory-and-filename-structure-1" />

#### 디렉터리 및 파일 이름 구조

보고서 경로는 다음과 같은 폴더 계층으로 구성됩니다.

다음 형식으로: `/t=cohort_unified_timezone_versioned/dt=/version=/`

<div id="report-folder-hierarchy-1" />

#### 보고서 폴더 계층 구조

광고주 버킷의 코호트 시간대 버전이 지정된 보고서 폴더 계층 구조의 예는 다음과 같습니다.

```
bucket
|
└── t=cohort_unified_timezone_versioned
    |
    ├── dt=2024-05-05
    |   |
    |   └── version=1714890235
    |   |    |
    |   |    ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |    |
    |   |    ├── part-00001-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |    │
    |   |    └── part-00002-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |
    |   |
    |   └── version=1714890286
    |        |
    |        ├── part-00000-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        |
    |        ├── part-00001-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        │
    |        └── part-00002-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |   |
    .   . 
    .   .
```

**범례:**

* **dt**: 보고서에 포함된 이벤트가 발생한 날짜.
* **t:** 보고서 유형.
* **버전**: 버전이 생성되었을 때의 Unix 타임스탬프.

<div id="report-versions-and-data-freshness-1" />

### 보고서 버전 및 데이터 새로 고침

* 당일 내 보고서는 몇 시간마다 전송됩니다.
* 보고서는 해당 날짜에 현재 사용할 수 있는 모든 데이터에 대한 것입니다. 즉, 4월 18일의 모든 보고서 버전에는 4월 18일 해당 시점까지 사용 가능한 모든 데이터가 포함됩니다.
* 보고서 사용 사례는 지역과 시간대에 따라 다를 수 있습니다. [더 알아보기](/docs/advanced-aggregated-reports-in-data-locker#timezone-geos)
* **사용 가능한 최신 보고서 버전만 수집합니다.**

| 버전 | 보고서에는 앱스플라이어가 수신한 데이터(UTC 시간)가 포함됩니다. | 적용 사례 | 시간 보고서를 사용할 수 있습니다(UTC 시간). |
| --- | --- | --- | --- |
| 1 | -1일 오전 4시 | 동부 지역 - 0일 부분 데이터 | -1일 오전 8시 |
| 2 | -1일 오전 8시 | 동부 지역 - 0일 부분 데이터 | -1일 오후 1시 |
| 3 | -1일 오후 12시 | 동부 지역 - 0일 부분 데이터 | -1일 오후 6시 |
| 4 | -1일 오후 4시 | 동부 지역 - 0일 부분 데이터 | 1일 오후 9시 |
| 5 | -1일 오후 8시 | 동부 지역 - 0일 부분 데이터 | -1 일 11:59 PM |
| 6 | -1 일 11:59 PM | 동부 및 중부 지역 - 0일에 대한 부분 데이터 | 0일 오전 4시 |
| 7 | 0일 오전 4시 | 모든 지역 - 0일차의 부분 데이터 | 0일 오전 8시 |
| 8 | 0일 오전 8시 | 모든 지역 - 0일차의 부분 데이터 | 0일 오후 1시 |
| 9 | 0일 오후 12시 | 모든 지역 - 0일차의 부분 데이터 | 0일 오후 6시 |
| 10 | 0일 오후 4시 | 모든 지역 - 0일차의 부분 데이터 | 0일 오후 9시 |
| 11 | 0일 오후 8시 | <ul><li>동부 지역 - Day 0의 전체 전환 및 인앱 이벤트 데이터</li><li>중부 및 서부 지역 - 0일에 대한 부분 데이터</li></ul> | 0일 오후 11:59 |
| 12 | 0일 오후 11:59 | 중부 및 서부 지역 - 0일에 대한 부분 데이터 | 1일차 오전 4시 |
| 13 | 1일차 오전 4시 | <ul><li>중앙 지역 - 0일차의 전체 전환 및 인앱 이벤트 데이터</li><li>서부 지역 - 0일차 부분 데이터</li><li>S2S를 통해 전송된 현재 사용 가능한 광고 수익 데이터</li></ul> | 1일차 오전 8시 |
| 14 | 1일차 오전 8시 | 서부 지역 - 0일차의 부분 데이터 및 S2S를 통해 전송된 현재 사용 가능한 광고 수익 데이터 | 1일차 오후 1시 |
| 15 | 1일차 오후 12시 |  | 1일차 오후 6시 |
| 16 | 1일차 오후 12시 |  | 1일차 오후 6시 |
| 17 | 1일차 오후 4시 | 서부 지역 - 0일차의 부분 데이터 및 S2S를 통해 전송된 현재 사용 가능한 광고 수익 데이터 | 1일차 오후 9시 |
| 18 | 1일차 오후 6시 | 서부 지역 - 0일차의 부분 데이터 및 S2S를 통해 전송된 현재 사용 가능한 광고 수익 데이터 | 1일 오후 11:59 |
| 19 | 1일차 오후 8시 | 서부 지역 - 0일차의 전체 전환 및 인앱 이벤트 데이터와 S2S를 통해 전송된 현재 사용 가능한 광고 수익 데이터 | 1일 오후 11:59 |
| 20 | 1일 오후 11:59 | 0일차의 전체 전환 및 인앱 이벤트 데이터와 S2S를 통해 전송된 전체 광고 수익 데이터(광고 수익 네트워크 측에서 발생할 수 있는 잠재적 문제를 고려) | 2일차 오전 4시 |
| 21 | 8일 오전 00:00 | 0일차의 전체 전환 및 인앱 이벤트 데이터와 S2S를 통해 전송된 전체 광고 수익 데이터(광고 수익 네트워크 측에서 발생할 수 있는 잠재적 문제를 고려) | 8일차 오전 6시 |


<div id="additional-information" />

## 추가 정보

<div id="timezone-geos" />

<Accordion title="시간대 지역">

보고서 사용 사례는 지역과 시간대에 따라 다를 수 있습니다. 다음 표를 사용하여 어떤 지역이 어떤 시간대와 일치하는지 파악할 수 있습니다.

| 지역 | 시간대 |
| --- | --- |
| 동부 | UTC+12 - UTC+3 |
| 중부 | UTC+2.5 - UTC-3 |
| 서부 | UTC-3.5 - UTC-12 |

</Accordion>

<div id="bi-developer-considerations" />

<Accordion title="BI 개발사 고려사항">

**리포트의 데이터 범위**

이 리포트에는 사용자 획득, 인스톨 및 리타게팅, 리어트리뷰션, 리인게이지먼트, 관련 인앱이벤트가 포함됩니다.

통합, 사용자 획득 및 리타게팅 보고서를 개별적으로 또는 함께 BI에 로드할 수 있습니다. 함께 로드하고 직접 뷰를 필터링하려는 경우:

* 통합의 경우 is\_primary\_attribution=true 또는 null 필드를 사용합니다.
* 사용자 확보의 경우 conversion\_type=Install을 사용합니다.
* 리타게팅의 경우 conversion\_type=리인게이지먼트 또는 리어트리뷰션을 사용합니다.

데이터 로딩 과정에 통합 뷰를 사용하는 경우 로직을 사용하여 캠페인 유형 간에 데이터를 분할해야 합니다. 다시 말하면 사용자 어트리뷰선(인스톨)과 리타게팅(리인게이지먼트)입니다. 이를 위해, conversion\_type=install, install\_unified, 리인게이지먼트 또는 리어트리뷰션을 사용합니다. <Anchor target="_blank" href="/marketers/ko/docs/resolve-retargeting-double-attribution">리타게팅 이벤트의 이중 어트리뷰션</Anchor>을 참고하십시오.

**필드 수준 고려 사항**

* 사후 어트리뷰션 날짜를 사용하여 리텐션 지표 계산을 쉽게 합니다.
* 캠페인 이름 및 캠페인 ID 차원을 사용하여 고유 사용자 계산: 캠페인 이름 세분성을 무시할 수 있는 경우, 캠페인 ID의 고유 개수를 합산할 수 있으며 지표가 정확합니다.
* 캠페인 계층 구조 필드를 사용하여 데이터를 집계할 수 있습니다.
* USD 단위의 수익은 이벤트 발생일의 환율을 사용하여 계산됩니다.

**일반 고려 사항**

모든 앱의 데이터를 구성할 수 있습니다. 앱당 단일 파일 또는 별도의 파일로 제공할 수 있습니다.

</Accordion>

<div id="use-cases" />

<Accordion title="활용 사례">

다음은 BI 개발자가 데이터 락커를 통해 추출할 수 있는 코호트 데이터의 인기 있고 실용적인 애플리케이션의 예입니다. 각 예제를 SQL 문과 샘플 Excel 시각적 개체로 설명합니다.

<div id="1-calculate-retention" />

#### **1.**

아래 예제에서는 다음을 수행합니다.

* 1일 차와 7일 차의 리텐션과 캠페인 및 광고당 총 인스톨 수를 계산합니다.
* `event_name`을 필터링하여 전환 이벤트당 이벤트 수를 합산합니다.`af_conversion`
* 데이터를 필터링하여 사용자 유입 캠페인을 구체적으로 분석합니다 `conversion_type=install`.

**SQL 문**

```sql
select
    campaign_id, ad_id,
    sum(if(event_name = 'af_conversion', event_count,0)) as installs,
    sum(if(event_name = 'af_session' and days_post_attribution = 1, unique_users,0)) / sum(if(event_name = 'af_conversion', event_count,0)) as retention_day1,
    sum(if(event_name = 'af_session' and days_post_attribution = 7, unique_users,0)) / sum(if(event_name = 'af_conversion', event_count,0)) as retention_day7
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    // If you're querying data from unified reports, edit the line below to: and conversion_type IN ('install', 'install_unified', 'retargeting', 'reattr')
    and conversion_type = 'install'
    and app_id = YOUR_APP
group by 1,2
```

**Excel 예제**

| 캠페인 ID | 광고 ID | 인스톨 | 리텐션 1일차 | 리텐션 7일차 |
| --- | --- | --- | --- | --- |
| 12345678 | 987654 | 100 | 30% | 10% |
| 98765432 | 123456 | 200 | 25% | 15% |
| 07315466 | 613770 | 300 | 20% | 12% |

<div id="2-calculate-arpu-of-multiple-in-app-events" />

#### **2.**

아래 예제에서는 다음을 수행합니다.

* 캠페인당 다중 인앱이벤트의 ARPU를 계산합니다.
* 특히 `conversion_type=re-engagement`과 `conversion_type=re-attribution`를 기준으로 데이터를 필터링하여 리타게팅 캠페인을 구체적으로 분석합니다.
* `event_name`을 필터링하여 전환 이벤트당 이벤트 수를 합산합니다.`af_conversion`
* 이 경우 `af_purchase`과 `af_coins`의 여러 이벤트의 수익을 합산합니다.
* 데이터 처리 부하를 최소화하려면 `days_post_attribution`를 필요한 최소값(이 경우 7)으로 설정합니다.

**SQL 문**

```sql
select
    campaign_id,
    sum(if(days_post_attribution <= 1 and event_name in ('af_purchase', 'af_coins') , revenue_usd, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day1,
    sum(if(days_post_attribution <= 3 and event_name in ('af_purchase', 'af_coins') , revenue_usd, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day3,
    sum(if(days_post_attribution <= 7 and event_name in ('af_purchase', 'af_coins') , revenue_usd, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day7
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    and days_post_attribution <= 7
    // If you're querying data from unified reports, edit the line below to: and conversion_type IN ('install', 'install_unified')
    and conversion_type in ('re-engagement', 're-attribution')
    and app_id = YOUR_APP
group by 1
```

**Excel 예제**

| 캠페인 ID | 전환 유형 | ARPU<br /><br />1일 차 | ARPU<br /><br />3일 차 | ARPU<br /><br />7일 차 |
| --- | --- | --- | --- | --- |
| 12345678 | 리인게이지먼트 | 6.23 | 5.11 | 2.34 |
| 98765432 | 리인게이지먼트 | 3.57 | 1.34 | 4.86 |
| 07315466 | 리어트리뷰션 | 7.41 | 6.79 | 5.29 |

<div id="3-calculate-in-app-event-conversion-rate-for-a-specific-cohort-day" />

#### **3. 특정 코호트일의 인앱 이벤트 전환율 계산**

아래 예제에서는 다음을 수행합니다.

* 여러 측정기준(이 경우 전환일, 지역, 캠페인, 광고, 사이트 ID)에 대한 0일 차 인앱 이벤트 전환율을 계산합니다.
* 통합 데이터를 분석하여 UA와 리타게팅 캠페인 모두에 대한 필터링을 합니다 `is_primary_attribution=true`.
* `event_name`을 필터링하여 전환 이벤트당 이벤트 수를 합산합니다.`af_conversion`
* 데이터 처리 부하를 최소화하려면 `days_post_attribution`를 필요한 최소값(이 경우 7)으로 설정합니다.

**SQL 문**

```sql
select
    conversion_date, geo, campaign_id, ad_id, site_id,
    sum(if(days_post_attribution = 0 and event_name = 'af_complete_tutorial', unique_users, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as day0_af_tutorial_conversion
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    and is_primary_attribution = true
    and app_id = YOUR_APP
group by 1,2,3,4,5
```

**Excel 예제**

| 전환 날짜 | 지역 | 캠페인 ID | 광고 ID | 사이트 ID | 0일 차 af\_complete\_tutorial |
| --- | --- | --- | --- | --- | --- |
| 2022-11-07 | 미국 | 12345678 | 123456 | site\_123 | 45% |
| 2022-11-05 | 영국 | 98765432 | null | 사이트\_654 | 70% |
| 2022-10-31 | 한국 | 07315466 | null | null | 63% |

<div id="4-calculate-daily-installs" />

#### **4.**

아래 예제에서는 다음을 수행합니다.

* 앱 ID, 전환 날짜, 미디어 소스, 이벤트 이름, 전환 유형별로 인스톨 수를 계산합니다.
* UA 인스톨을 표시하도록 `conversion_type`을 `install`로 설정하여 데이터를 필터링합니다 (리타게팅 제외).
* `event_name`을 `af_conversion`로 설정하여 인스톨을 합산합니다.

**SQL 문**

```sql
select
    app_id,
    conversion_date,
    media_source,
    event_name,
    conversion_type,
    sum(events_count) as total
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    // If you're querying data from unified reports, edit the line below to: and conversion_type IN ('install', 'install_unified')
    and conversion_type = 'install'
    and event_name = 'af_conversion'
    and app_id = YOUR_APP
group by 1,2,3,4,5
```

**Excel 예제**

| 앱 ID | 전환 날짜 | 미디어 소스 | 이벤트 이름 | 합계 |
| --- | --- | --- | --- | --- |
| id123456789 | 2022-11-07 | adnet1\_int | af\_conversion | 105 |
| id123456789 | 2022-11-05 | adnet2\_int | af\_conversion | 216 |
| id123456789 | 2022-10-31 | adnet3\_int | af\_conversion | 327 |

<div id="5-calculate-revenue-from-facebook-ads" />

#### **5.**

아래 예제에서는 다음을 수행합니다.

* 전환 날짜 및 앱 ID를 기준으로 Facebook의 3일 차 수익을 계산합니다.
* 페이스북 데이터를 분석할 때 `media_source='Facebook Ads'`에 맞게 데이터를 필터링합니다.
* 데이터 처리 부하를 최소화하려면 `days_post_attribution`을 필요한 최소값(이 경우 3)으로 설정합니다.

**SQL 문**

```sql
select
    conversion_date,
    app_id,
    media_source,
    sum(if(days_post_attribution <= 3, revenue_usd, 0)) as revenue_day3
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2022-06-01' and '2023-05-31'
    and days_post_attribution <= 3
    and media_source = 'Facebook Ads'
    and app_id in (APP_ID1, APP_ID2, ...)
group by 1,2,3
```

**Excel 예제**

| 전환 날짜 | 앱 ID | 미디어 소스 | 수익<br /><br />3일 차 |
| --- | --- | --- | --- |
| 2022-11-07 | id123456789 | adnet1\_int | 400.45 |
| 2022-11-05 | id123456789 | adnet2\_int | 99.23 |
| 2022-10-31 | id123456789 | adnet3\_int | 13.34 |

<div id="6-calculate-arpu-per-asa-keyword-id-for-up-to-365-cohort-days" />

#### **6. 최대 365일의 코호트 일 동안 ASA 키워드 ID당 ARPU 계산**

아래 예제에서는 다음을 수행합니다.

* 코호트 365일까지 키워드 ID별로 Apple Search Ads의 ARPU를 계산합니다.
* `media_source='Apple Search Ads'`에 맞게 데이터를 필터링하여 Apple Search Ads 데이터를 분석합니다.
* `event_name`을 필터링하여 전환 이벤트당 이벤트 수를 합산합니다.`af_conversion`

**SQL 문**

```sql
select
    media_source,
    keyword_id,
    sum(if(days_post_attribution <= 365, revenue_usd,0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day365
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2022-06-01' and '2023-05-31'
    and media_source = 'Apple Search Ads'
    and app_id = YOUR_APP
group by 1
```

**Excel 예제**

| 미디어 소스 | 키워드 ID | ARPU<br /><br />365일 차 |
| --- | --- | --- |
| adnet1\_int | 123456 | 57,019.93 |
| adnet2\_int | 987654 | 64,867.84 |
| adnet3\_int | 666854 | 48,160.02 |

<div id="7-calculate-arpu-days-7-by-attribution-time-per-geo" />

#### **7. 지역별 어트리뷰션 시간에 따른 ARPU 7일 계산**

다음 예제에서는 <Anchor target="_blank" href="/marketers/ko/docs/cohort-and-retention-dashboard#trend-type%E2%80%94kpi-by-attribution-time">어트리뷰션 시간별 KPI</Anchor>를 활용하는 방법을 보여줍니다. 이 예에서는 다음을 수행합니다.

* 지역별 어트리뷰션 날짜별로 ARPU 7일차를 계산합니다.
* 결과는 전환 수를 기준으로 정렬되며 상위 20개 지역이 표시됩니다.
* `conversion_type='install'`하도록 데이터가 필터링되었습니다.
* 첫 번째 열에는 지역이 표시됩니다. 두 번째 열에는 총 전환수가 나옵니다. 그 이후의 열에는 쿼리에 행으로 지정된 각 날짜에 대한 7일차 수익이 나타납니다.

**SQL 문**

```sql
select
    geo,
    sum(if(event_name = 'af_conversion', event_count, 0)) total_conversions,
    sum(if(cohort_day = '2023-07-11' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-11' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_11,
    sum(if(cohort_day = '2023-07-12' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-12' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_12,
    sum(if(cohort_day = '2023-07-13' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-13' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_13,
    sum(if(cohort_day = '2023-07-14' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-14' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_14,
    sum(if(cohort_day = '2023-07-15' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-15' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_15,
    sum(if(cohort_day = '2023-07-16' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-16' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_16
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-07-11' and '2023-07-16'
    and days_post_attribution <= 7
    // If you're querying data from unified reports, edit the line below to: and conversion_type IN ('install', 'install_unified')    
    and conversion_type = 'install'
    and app_id = 'YOUR_APP'
group by 1
order by 2 desc
limit 20
```

**Excel 예제**

| 지역 | 총 전환수 | 2023-07-11 ARPU 7일차 | 2023-07-12 ARPU 7일차 | 2023-07-13 ARPU 7일차 | 2023-07-11 ARPU 7일차 | 2023-07-11 ARPU 7일차 | 2023-07-16 ARPU 7일차 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 한국 | 120,660 | 7,798.89달러 | 6,997.37달러 | 8,258.95달러 | 9,050.21달러 | 10,018.04 | 13,765.73달러 |
| 캐나다 | 35,099 | 64,867.84달러 | 7,050.19달러 | 5,656.33달러 | 9,553.75달러 | 8,632.41달러 | 11,308.06달러 |
| 칠레 | 26,750 | 48,160.02 | 21,249.55달러 | 22,584.57달러 | 24,033.07 | 31,118.91달러 | 41,145.22달러 |

<div id="8-calculate-purchases-day-7-after-conversion" />

#### 24,033.07 전환 후 7일째 되는 날 구매 계산

아래 예제에서는 다음을 수행합니다.

* 전환 후 7일 후에 af\_purchase 이벤트를 수행하는 누적 고유 사용자를 계산합니다(통합 보기에서).
* 이벤트에 대한 전환율, 즉 전환 후 7일 이내에 구매한 전환의 비율을 계산합니다.
* `conversion_type='install'`이 되도록 데이터를 필터링합니다.
* 데이터는 앱, 전환 날짜, 미디어소스, 캠페인, 광고 세트별로 그룹화됩니다.

**SQL 문**

```sql
select
    app_id, conversion_date, media_source, campaign, adset,
    sum(if(event_name = 'af_conversion', event_count,0)) as unified_conversions,
    sum(if(event_name = 'af_purchase', first_inapp, 0)) as af_purchase_day_7_cumulative_unique_users,
    concat(
        cast(
            round(
                sum(if(event_name = 'af_purchase', first_inapp, 0)) /
                sum(if(event_name = 'af_conversion', event_count, 0)) * 100.0
            ,2)
        as varchar),
    '%') as af_purchase_day_7_cumulative_unique_users_conversion_rate
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-12-01' and '2023-12-31'
    and is_primary_attribution = true
    and days_post_attribution <= 7
    and app_id in (APP_ID1, APP_ID2, ...)
group by 1,2,3,4,5
```

**Excel 예제**

| 앱 ID | 전환 날짜 | 미디어 소스 | 캠페인 | 광고세트 | 통합 변환 | D7 af\_purchase 누적 | D7 af\_purchase 전환율 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| id123456789 | 2024-03-05 | adnet1\_int | campaign\_1 | adset\_1 | 100 | 20 | 20% |
| id123456789 | 2024-03-07 | adnet2\_int | campaign\_2 | adset\_2 | 200 | 10 | 5% |
| id123456789 | 2024-03-31 | adnet3\_int | campaign\_3 | adset\_3 | 150 | 15 | 10% |

<div id="9-calculate-dau" />

#### 24,033.07

아래 예제에서는 다음을 수행합니다.

* `event_name = 'af_session'`하도록 데이터가 필터링되었습니다.

**참고**:

**SQL 문**

```sql
select
media_source,campaign_id, ad_id,
sum(case when event_date = '2024-08-06' then unique_users end) as dau_2024_08_06,
sum(case when event_date = '2024-08-07' then unique_users end) as dau_2024_08_07,
sum(case when event_date = '2024-08-08' then unique_users end) as dau_2024_08_08
from YOUR_DATA_LOCKER_REPORT
where event_date between '2024-08-06' and '2024-08-08'
and event_name = 'af_session'
and app_id = YOUR_APP
group by 1,2,3
```

**Excel 예제**

| 미디어 소스 | 캠페인 | Ad |  |  |  |
| --- | --- | --- | --- | --- | --- |
| adnet1\_int | campaign\_1 | adset\_1 | 475,250 | 420,485 | 463,912 |
| adnet2\_int | campaign\_2 | adset\_2 | 380,987 | 355,665 | 401,232 |
| adnet3\_int | campaign\_3 | adset\_3 | 290,042 | 570,322 | 489,787 |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="특징 및 제약 사항">

| 특성 |  |
| --- | --- |
| 비용 데이터 | <ul><li>해당 없음. <Anchor target="_blank" href="/marketers/ko/docs/set-up-and-use-roi360-cost-etl-reports">Cost ETL 사용</Anchor>.</li><li><Anchor target="_blank" href="/marketers/ko/docs/combine-cost-etl-and-cohort-reports-via-data-locker">Cost ETL과 코호트 보고서 병합</Anchor> 참조.</li></ul> |
| 캠페인 이름 변경 | 지원 안 됨. 캠페인 이름이 변경된 경우 그룹화 및 필터링에 캠페인 ID를 사용합니다. |
| 데이터 최신성 | 당일 내 |
| 광고 수익 | 사용 가능 |
| 통화 | 행에 USD와 앱 특정 통화를 모두 사용할 수 있습니다. |
| 시간대 | 앱별 시간대는 시간대 버전 보고서에서 사용할 수 있습니다. |
| 오가닉 데이터 | 사용 가능 |
| 전환 후 일수 (인스톨, 리어트리뷰션, 리인게이지먼트) 데이터를 사용할 수 있습니다. | 1,095일을 사용할 수 있습니다. |
| 에이전시 투명성 | <ul><li>지원됨.</li><li>X 광고 및 메타 광고 데이터는 항상 투명합니다.</li></ul> |
| 앱 분리 | 지원됨. |
| SKAN 데이터 | 포함되지 않음. |
| 데이터 제거 | 제거는 매일 처리됩니다. 따라서 하루 동안의 전체 데이터(부분 데이터 아님)가 포함된 보고서에만 표시됩니다. |
| 재설치 | <ul><li>재설치 후 이벤트가 속성이 없는 오가닉이라고 간주되는 경우:<ul><li>2024년 5월 26일부터 포함됩니다. <Anchor target="_blank" href="/marketers/ko/docs/bulletin-cohort-data-includes-unattributed-sessions-and-events">더 알아보기</Anchor></li><li>설치 시간은 <Anchor target="_blank" href="/marketers/ko/docs/raw-data-field-dictionary#device-info::dfd9504e">device\_download\_time</Anchor> 필드를 기반으로 합니다.</li><li>고유 사용자 및 유지 측정에 포함되지 않습니다.</li></ul></li><li>재설치 후 이벤트가 첫 설치에 속하는 경우 항상 포함됩니다. <Anchor target="_blank" href="/marketers/ko/docs/unique-users">더 알아보기</Anchor></li></ul> |

</Accordion>

<div id="see-also" />

> 📄 **참고 항목**
>
> * Cost ETL 리포트와 고급 집계 코호트 리포트를 결합하는 쿼리
> * <Anchor target="_blank" href="/marketers/ko/docs/cohort-and-retention-dashboard">코호트 대시보드</Anchor>

<div data-zendesk-anchors="advanced-aggregated-reports-in-data-locker=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%9D%BD%EC%BB%A4%EC%9D%98-%EA%B3%A0%EA%B8%89-%EC%A7%91%EA%B3%84-%EB%A6%AC%ED%8F%AC%ED%8A%B8 h_01HWWH83KNSF4BRGTDJ0JD271G=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%9D%BD%EC%BB%A4%EC%9D%98-%EA%B3%A0%EA%B8%89-%EC%A7%91%EA%B3%84-%EB%A6%AC%ED%8F%AC%ED%8A%B8 setup=%EC%84%A4%EC%A0%95 h_01HWWH83KN9CM7ZY43W01AV6TA=%EC%84%A4%EC%A0%95 reports-available=%EC%82%AC%EC%9A%A9-%EA%B0%80%EB%8A%A5%ED%95%9C-%EB%A6%AC%ED%8F%AC%ED%8A%B8 h_01HWWNY76W6RFKX33MXHE4GSBD=%EC%82%AC%EC%9A%A9-%EA%B0%80%EB%8A%A5%ED%95%9C-%EB%A6%AC%ED%8F%AC%ED%8A%B8 report-facts=%EC%82%AC%EC%8B%A4-%EB%B3%B4%EA%B3%A0 h_01HVRBVXS47K91A6KVV33S1BY6=%EC%82%AC%EC%8B%A4-%EB%B3%B4%EA%B3%A0 report-structure=%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EA%B5%AC%EC%A1%B0 h_01HWWH83KNE46SPK1MS99XX64D=%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EA%B5%AC%EC%A1%B0 dimensions=%EB%94%94%EB%A9%98%EC%85%98 01H7WG3CA14PQ2PJ58FX8TE6ZH=%EB%94%94%EB%A9%98%EC%85%98 metrics=%EC%B8%A1%EC%A0%95-%EC%A7%80%ED%91%9C 01H7WG3CA24VQKFVP99S82GCXZ=%EC%B8%A1%EC%A0%95-%EC%A7%80%ED%91%9C directory-and-filename-structure=%EB%94%94%EB%A0%89%ED%84%B0%EB%A6%AC-%EB%B0%8F-%ED%8C%8C%EC%9D%BC-%EC%9D%B4%EB%A6%84-%EA%B5%AC%EC%A1%B0 h_01HVRDKKQA17SMJFFAEDG7A2X2=%EB%94%94%EB%A0%89%ED%84%B0%EB%A6%AC-%EB%B0%8F-%ED%8C%8C%EC%9D%BC-%EC%9D%B4%EB%A6%84-%EA%B5%AC%EC%A1%B0 the-report-folder-hierarchy-in-aws=%EB%B3%B4%EA%B3%A0%EC%84%9C-%ED%8F%B4%EB%8D%94-%EA%B3%84%EC%B8%B5-%EA%B5%AC%EC%A1%B0 h_01HETBAQVVA750VTE1ABSM2M47=%EB%B3%B4%EA%B3%A0%EC%84%9C-%ED%8F%B4%EB%8D%94-%EA%B3%84%EC%B8%B5-%EA%B5%AC%EC%A1%B0 report-versions-and-data-freshness=%EB%B3%B4%EA%B3%A0%EC%84%9C-%EB%B2%84%EC%A0%84-%EB%B0%8F-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%83%88%EB%A1%9C-%EA%B3%A0%EC%B9%A8 h_01HWWH83KN51RR2VJ2F5N8YQ3J=%EB%B3%B4%EA%B3%A0%EC%84%9C-%EB%B2%84%EC%A0%84-%EB%B0%8F-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%83%88%EB%A1%9C-%EA%B3%A0%EC%B9%A8 report-facts::15e071f=%EC%82%AC%EC%8B%A4-%EB%B3%B4%EA%B3%A0-1 h_01HWWH83KNPZETHR2TQS2E4QNT=%EC%82%AC%EC%8B%A4-%EB%B3%B4%EA%B3%A0-1 report-structure::43ffff28=%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EA%B5%AC%EC%A1%B0-1 h_01HWWH83KNG0V2ZMZZ7CTV2GE7=%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EA%B5%AC%EC%A1%B0-1 01HWSX3FA0K39D9M5RQ7J36Q23=%EB%94%94%EB%A9%98%EC%85%98-1 01HWSX3FA035Z8W6EPV4Q6E3JP=%EC%B8%A1%EC%A0%95-%EC%A7%80%ED%91%9C-1 01HWSX3FA189EMBJZ1P21YHC45=%EB%94%94%EB%A0%89%ED%84%B0%EB%A6%AC-%EB%B0%8F-%ED%8C%8C%EC%9D%BC-%EC%9D%B4%EB%A6%84-%EA%B5%AC%EC%A1%B0-1 01HX97NC4F2WCJABSM2NBSBEDN=%EB%B3%B4%EA%B3%A0%EC%84%9C-%ED%8F%B4%EB%8D%94-%EA%B3%84%EC%B8%B5-%EA%B5%AC%EC%A1%B0-1 report-versions-and-data-freshness::e0755e26=%EB%B3%B4%EA%B3%A0%EC%84%9C-%EB%B2%84%EC%A0%84-%EB%B0%8F-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%83%88%EB%A1%9C-%EA%B3%A0%EC%B9%A8-1 h_01HWWH83KPS2ANCQKS2B3V529Z=%EB%B3%B4%EA%B3%A0%EC%84%9C-%EB%B2%84%EC%A0%84-%EB%B0%8F-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%83%88%EB%A1%9C-%EA%B3%A0%EC%B9%A8-1 additional-information=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01HWWH83KPK8535X9EBZVJ9SQK=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01HWWN6GAAD75HPC5GTE40QA37=timezone-geos 01H7WG3CA2C3HV8YT5ZMP9E0QY=bi-developer-considerations 01H7WG3CA2YF03SC6RBMCJYYVX=use-cases 1-Calculate-retention=1 h_01HMTZ0DZWN54HBQ0ZTY0VFNFM=1 2-Calculate-arpu-of-multiple-inapp-events=2 h_01HMTZ0DZWHZ77RYWYAQEJV7X5=2 3-Calculate-inapp-event-conversion-rate-for-a-specific-cohort-day=3-%ED%8A%B9%EC%A0%95-%EC%BD%94%ED%98%B8%ED%8A%B8%EC%9D%BC%EC%9D%98-%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%A0%84%ED%99%98%EC%9C%A8-%EA%B3%84%EC%82%B0 h_01HMTZ0DZW7VA6T6MQY7BY1JZT=3-%ED%8A%B9%EC%A0%95-%EC%BD%94%ED%98%B8%ED%8A%B8%EC%9D%BC%EC%9D%98-%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%A0%84%ED%99%98%EC%9C%A8-%EA%B3%84%EC%82%B0 4-Calculate-daily-installs=4 h_01HMTZ0DZWARZFAQ9R4VF56YN3=4 5-Calculate-revenue-from-facebook-ads=5 h_01HMTZ0DZW74HWW6Z3VDWDMGRF=5 6-Calculate-arpu-per-asa-keyword-id-for-up-to-365-cohort-days=6-%EC%B5%9C%EB%8C%80-365%EC%9D%BC%EC%9D%98-%EC%BD%94%ED%98%B8%ED%8A%B8-%EC%9D%BC-%EB%8F%99%EC%95%88-asa-%ED%82%A4%EC%9B%8C%EB%93%9C-id%EB%8B%B9-arpu-%EA%B3%84%EC%82%B0 h_01HMTZ0DZWSN83V0TEHVM2H5XS=6-%EC%B5%9C%EB%8C%80-365%EC%9D%BC%EC%9D%98-%EC%BD%94%ED%98%B8%ED%8A%B8-%EC%9D%BC-%EB%8F%99%EC%95%88-asa-%ED%82%A4%EC%9B%8C%EB%93%9C-id%EB%8B%B9-arpu-%EA%B3%84%EC%82%B0 Calculate-arpu-days-0-7-by-attribution-time-per-geo=7-%EC%A7%80%EC%97%AD%EB%B3%84-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%8B%9C%EA%B0%84%EC%97%90-%EB%94%B0%EB%A5%B8-arpu-7%EC%9D%BC-%EA%B3%84%EC%82%B0 01H8XYTJVQ1YFBHPWVPP9D7MJ8=7-%EC%A7%80%EC%97%AD%EB%B3%84-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%8B%9C%EA%B0%84%EC%97%90-%EB%94%B0%EB%A5%B8-arpu-7%EC%9D%BC-%EA%B3%84%EC%82%B0 8-calculate-purchases-day-7-after-conversion=2403307-%EC%A0%84%ED%99%98-%ED%9B%84-7%EC%9D%BC%EC%A7%B8-%EB%90%98%EB%8A%94-%EB%82%A0-%EA%B5%AC%EB%A7%A4-%EA%B3%84%EC%82%B0 h_01J7N4VB83T4KZ6G0Q634ASMHV=2403307-%EC%A0%84%ED%99%98-%ED%9B%84-7%EC%9D%BC%EC%A7%B8-%EB%90%98%EB%8A%94-%EB%82%A0-%EA%B5%AC%EB%A7%A4-%EA%B3%84%EC%82%B0 9-calculate-dau=2403307 h_01J55D2FFW0XSH3G6AXRS06RPV=2403307 01H7WG3CA2Y59D2EVMN3YFFY1W=traits-and-limitations h_01HDNZ8A0QH74CGSEG6TKKARJP=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
