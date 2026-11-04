---
title: 로데이터 리포트에서 확인할 수 있습니다.
metadata:
  keywords:
    - Data Locker
    - People Based Attribution
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2019-07-01T07:53:57Z'
  edited_at: '2026-10-14T10:34:28Z'
  id: 360001917778
  locale: ko
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/ko/articles/360001917778
---
> **간단히 보기**: 로데이터 리포트는 데이터 락커를 통해 제공됩니다

<div id="pba-raw-data-reports" />

## 로데이터 리포트에서 확인할 수 있습니다.

<div id="report-descriptions" />

### 리포트 설명

로데이터 리포트 관련 주제

| 로데이터 리포트 관련 주제 | 설명 |
| --- | --- |
| <span id="website-visits"></span>[웹 사이트 방문](#website-visits-and-website-events) |  |
| <span id="website-events"></span><Anchor target="_blank" href="/marketers/ko/docs/pba-website-attribution-dashboard">웹 사이트 이벤트</Anchor> | <ul><li>이벤트는 최근 30일 이내의 마지막 비직접 웹 방문에 어트리뷰션 됩니다.</li></ul> |



* <span id="sample-reports"></span><span id="raw-data-report-fields"></span><span id="rawdata-report-fields"></span>웹 사이트 이벤트 <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTAWrfTDOJmY04jkFNd0OJ3TcQgPiybcMkdQF7XLmIt33HV09GFYy7KwsmWN3Z8TT2JhStf3uQHfH2E/pub?gid=1096347999&single=true&output=csv">CSV</Anchor>
* 웹 사이트 방문 [CSV](https://docs.google.com/spreadsheets/d/e/2PACX-1vTAWrfTDOJmY04jkFNd0OJ3TcQgPiybcMkdQF7XLmIt33HV09GFYy7KwsmWN3Z8TT2JhStf3uQHfH2E/pub?gid=432734495&single=true&output=csv)


| <span id="field-list-website-visits-and-website-events-report"></span><span id="website-visits-events"></span>필드 이름 | 설명 | 형식 | 예시 |
| --- | --- | --- | --- |
| advertising\_id | 광고 ID(GAID) | 문자열 | 7fzzz3fa-8bad-46c9-bb03-fffffffffffffffffffffffff |
| af\_web\_id |  | 문자열 | 68972980-58f9-4ca6-8743-c0d633364b6d |
| amazon\_aid | 아마존 파이어 TV 광고 ID | 문자열 | df07c7dc-cea7-4a89-b328-810ff5acb15d |
| android\_id |  | 문자열 | 68999980-58f9-4ca6-8743-c0d633364b6d |
| app\_id |  | 문자열 | id123456789 |
| app\_name |  | 문자열 | 내 앱 |
| app\_version |  | 문자열 | 6.32 |
| appsflyer\_id |  | 문자열 | 1594825729709-5655157112349378588 |
| attributed\_touch\_time |  |  | 24,033.07 |
| attributed\_touch\_type |  | 문자열 | 웹 방문 |
| bundle\_id |  | 문자열 | 048db9bf-97r7-4m2f-919b-607b7kk806d0 |
| campaign |  | 문자열 |  |
| campaign\_id |  | 문자열 | 12343425 |
| 도시 |  | 문자열 |  |
| country\_code |  | 문자열 | 미국 |
| 고객\_유저\_ID |  | 문자열 | 5a8771ecbb986ABC |
| device\_type |  | 문자열 | 데스크톱 |
| dma |  | 문자열 | 501 |
| event\_name |  | 문자열 | purchase |
| event\_revenue |  | 문자열 | 199.99 |
| 이벤트 수익 통화 |  | 문자열 | USD, ZAR, EUR |
| 이벤트 수익 USD | USD로 전환된 수익 | 문자열 | 57.46 |
| event\_source |  | 문자열 | web SDK, S2S |
| event\_time |  |  | 24,033.07 |
| event\_type | 다음 작업을 수행하십시오. | 문자열 | 전환 이벤트 |
| event\_url | 이벤트가 발생한 웹페이지의 URL (웹사이트 방문 시의 원래 URL과 동일) | 문자열 | http://www.brandpit.com/checkout |
| event\_value | 웹 사이트 이벤트 웹 사이트 방문 항상 null | JSON | `{"sku": "ABC123", “color": "blue", "unit_price":3.99,"currency": "USD"}` |
| idfa |  | 문자열 | A56B9887-FEBA-458C-BEFC-C891F9DF7681 |
| idfv |  | 문자열 | EBC2F523-B1E5-4484-A4C8-ADC32DC7C23D |
| imei | 기기 식별자 | 문자열 | 3532211234 |
| 설치 시간 |  |  | 24,033.07 |
| ip |  | 문자열 | 24.7.104.115 |
| 언어 |  | 문자열 | 한국어 |
| media\_channel |  | 문자열 | Ad |
| media\_source |  | 문자열 | googleadwords\_int |
| media\_type |  | 문자열 | 페이드 미디어 |
| oaid |  | 문자열 | df07c7dc-cea7-4a89-b328-810ff5acb15d |
| original\_url |  | 문자열 | https://www.brandpitt.com/signin?utm_source=Googleg&utm_term=shoes&utm_campaign=cool&c=summer&af_siteid=publisher&af_sub1=helloworld |
| 플랫폼 |  | 문자열 | macOS |
| postal\_code |  | 문자열 | 10977 |
| query\_params | 리디렉션 URL의 쿼리 파라미터(? 이후) | JSON |  |
| 리퍼러 |  | 문자열 | https://www.google.com/ |
| 지역 |  | 문자열 | NA |
| state |  | 문자열 |  |


| 날짜 | 보고서 | 변경 |
| --- | --- | --- |
| 24,033.07 | 웹 사이트 이벤트<br /><br />웹 사이트 방문 |  |
| 24,033.07 | 웹 투 앱 | <ul><li>mobile\_campaign\_id</li><li>web\_campaign\_id</li></ul> |


<div id="use-cases-for-pba-and-mobile" />

<div id="procedures" />

### 절차

1. 앱스플라이어의 사이드 메뉴에서 **보고서** > **데이터 락커**를 선택합니다.
3. **구성 저장을 클릭합니다.**


**해결 방안:**



**시작하기 전**:

1. ![Duck_us-en.jpg](https://files.readme.io/b8e93ad9423605b3247531d276b9c2d45abd4ea044dde29ee177f4d71b738e9d-360008254377.jpg)

**시작하기 전:**

2. 참고:    

   ```
   ~q "SELECT * from part*.gz" -d , -H -z -O >pbadata.csv
   ```

<div data-zendesk-anchors="pba-raw-data-reports=%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%A6%AC%ED%8F%AC%ED%8A%B8%EC%97%90%EC%84%9C-%ED%99%95%EC%9D%B8%ED%95%A0-%EC%88%98-%EC%9E%88%EC%8A%B5%EB%8B%88%EB%8B%A4 h_01HKW341NVTCP4FY5G4TC94MZY=%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%A6%AC%ED%8F%AC%ED%8A%B8%EC%97%90%EC%84%9C-%ED%99%95%EC%9D%B8%ED%95%A0-%EC%88%98-%EC%9E%88%EC%8A%B5%EB%8B%88%EB%8B%A4 report-descriptions=%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EC%84%A4%EB%AA%85 h_01HKW341NVC83ZC3HCH86QBJYG=%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EC%84%A4%EB%AA%85 sample-reports=rawdata-report-fields h_01HKW341NVNYM1AGFC8GHV7VR2=rawdata-report-fields h_01HKW341NVX51NQFAA79BD7MF3=rawdata-report-fields field-list-website-visits-and-website-events-report=website-visits-events h_01J53BGNDSQCCFV1VQA8EV50GR=website-visits-events procedures=%EC%A0%88%EC%B0%A8 h_01HKW341NWXQ19ZB5QXZK84VMQ=%EC%A0%88%EC%B0%A8 use-cases-for-pba-and-mobile=%EC%A0%88%EC%B0%A8 h_01HKW341NXTXX4FJ2ZZQFZ2V85=%EC%A0%88%EC%B0%A8" />
