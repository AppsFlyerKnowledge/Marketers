---
title: 데이터 최신성 및 시간대 지원
metadata:
  keywords:
    - Reports
    - Advertisers
    - Agencies
    - Ad Networks
    - timezone
    - data freshness
    - data
    - Developers
    - Gray
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
    - Ad Networks
  created_at: '2018-02-19T15:57:01Z'
  edited_at: '2026-10-14T10:26:09Z'
  id: 360000310629
  locale: ko
  section: The AppsFlyer platform
  section_id: 6551361489297
  url: https://support.appsflyer.com/hc/ko/articles/360000310629
---
> **한눈에 보기:** 요약: 데이터 최신성은 이벤트 발생과 플랫폼에서 데이터 가용성 사이의 기간입니다.

**시간대**

[![TimeZoneMap.jpg](https://files.readme.io/eddfa3df4d43fed82ba5e867eb1278466d1ba51f9fbc2970f62fa61c6659d340-360005463738.jpg)](https://files.readme.io/eddfa3df4d43fed82ba5e867eb1278466d1ba51f9fbc2970f62fa61c6659d340-360005463738.jpg)

## 데이터 최신성 및 앱 시간대 지원

### 데이터 최신성

앱스플라이어 [플랫폼은 매일 및 실시간과 같은 다양한 유형의 최신 데이터를 활용합니다](/docs/about-data-freshness-and-timezone-support#data-freshness-types) . 데이터를 제공하고 제공하는 데 사용됩니다.  각각 고유한 데이터 최신성 비율이 있습니다.

예시: 예: 이벤트 대시보드의 데이터 최신성 비율:

* 지표 KPI: 실시간
* 평균 KPI: 매일

### 시간대

앱스플라이어 플랫폼에서 하루는 00:01에 시작하여 24:00에 끝납니다. 기본 시간대는 UTC(GMT)입니다. <Anchor target="_blank" href="/marketers/ko/docs/changing-app-time-zone-settings">앱 시간대</Anchor>를 설정하여 기본값을 수정할 수 있습니다.

<Accordion title="날짜 및 시간대 원칙">

UTC 시간은 일정하며 여름/겨울 시간이 따로 없습니다.

반구

* 동부 동부: UTC +/span> 로 지정된 시간대는 UTC **의 동쪽에 위치한 시간대입니다.**
* 서부 서부: UTC로 지정된 시간대 - UTC의 서쪽에 위치한 시간대입니다.

#### 앱별 시간대

앱 시간대를 설정할 수 있습니다. 다시 말해 데이터가 UTC 대신 현지 시간을 사용하여 일로 그룹화될 수 있습니다.

예시:

베이징 베이징: 앱 시간대가 베이징(UTC +8)으로 설정된 경우 하루는 16:01 UTC에 시작하여 다음 날 16:00 UTC에 끝납니다.

로스앤젤레스: 앱 시간대가 로스앤젤레스(UTC -8)로 설정된 경우 하루는 08:01 UTC에 시작하여 다음 날 08:00 UTC에 끝납니다.

#### 시간대 가이드라인

* 앱 시간대를 Google 및 Facebook과 같은 다른 어트리뷰션 서비스 제공업체에 대해 설정한 시간대와 맞추십시오.
* 앱이 두 개 이상인 경우 모든 앱을 동일한 시간대로 설정하는 것이 가장 좋습니다. 앱의 시간대 설정을 보려면 **설정** > **앱 설정으로 이동합니다.**
* 대부분의 리포트 및 데이터 추출 도구는 앱 시간대를 지원합니다. 여기에는 모든 앱이 동일한 앱 시간대로 설정된 경우 다중 앱 리포트가 포함됩니다.

<div id="exception-my-dashboards-cohort-and-activity-metrics" />

<div id="daily-processing" />

#### 일일 처리

일부 리포트 및 풀다운 목록은 하루에 한 번 처리되며 이를 일일 최신성 또는 일일 처리라고 합니다. 다음은 일일 처리 원칙입니다.

* 특정 요일,예를 들어 월요일에 얻어지는 데이터가 *버킷*에 수집됩니다. 앱 시간을 사용하면 하루는 00:01에 시작하여 24:00에 끝납니다.
* 자정 이후 최대 두 시간 동안 수신된 데이터는 해당 날짜의 버킷에 포함됩니다. 화요일 02:00까지 수신된 데이터는 월요일 버킷에 포함됩니다.
* 버킷은 현지 시간 02:00에 닫히고 더 이상 데이터를 추가할 수 없습니다.
* 02:00 이후에 수신한 데이터는 이벤트 날짜와 상관없이 사용 가능한 다음 버킷에 배치됩니다.
* 닫힌 버킷의 일일 처리는 앱별 시간대에 관계없이 UTC 자정 2시간 후에 시작됩니다. 간단하게 하기 위해 UTC 자정에 처리가 시작된다고 명시합니다. 즉, 현지 시간대에 따라 버킷은 처리가 시작되기 전에 UTC 자정까지 기다려야 합니다.

**동반구 및 UTC 시간대**:

![mceclip9b.png](https://files.readme.io/cbea9d910695b39f59b342da6f56fa51df76afc910c4eea60f6dd49fbee2a0d6-8272818122769.png)

* 하루가 끝나는 시간(현지 시간)부터 처리가 시작될 때까지 최대 11시간이 걸릴 수 있습니다. 예를 들어:

  * UTC:
* 리포트 유형에 따라 데이터는 처리 시작 후 8-20시간 동안 사용할 수 있습니다. 예를 들어 베이징 데이터는 현지 시간으로 16:00부터 사용할 수 있습니다. 베를린 데이터는 09:00부터 사용할 수 있습니다.

**서반구:**

![mceclip7a.png](https://files.readme.io/ac5e3046b3f55916bb73732801c7e0bdef714cc45b89b6c4d70bbc2009cd64c8-8272698121489.png)

* 하루가 끝나는 시간부터 처리가 시작될 때까지 최대 23시간이 걸릴 수 있습니다. 예를 들어:
* 리포트 유형에 따라 처리된 데이터는 처리 시작 후 8-20시간 후에 사용할 수 있습니다. 예를 들어 로스앤젤레스 데이터는 이벤트 발행 이틀 후 현지 시간으로 00:01부터 사용할 수 있습니다. 뉴욕 데이터는 이벤트 발생 이틀 후 현지 시간으로 03:01부터 사용할 수 있습니다.
* 예시:
  * 월요일 로스앤젤레스 시간(UTC -8)에 발생한 이벤트 일일 처리는 UTC 화요일 자정에 시작됩니다. 로스앤젤레스 시간으로 화요일 16:01입니다.
  * 8시간 후인 수요일 00:01에 로스앤젤레스 시간에 데이터 처리가 완료됩니다. 실제적으로는 월요일의 데이터는 로스앤젤레스의 광고주가 수요일 아침에 작업을 시작할 때 사용할 수 있습니다.

</Accordion>

<Accordion title="데이터 최신성 유형">

| 평가 | 유효성 | 설명 |
| --- | --- | --- |
| 연속(일명 실시간) | 이벤트 발생 후 15&#126;60분 | 데이터 처리는 연속적입니다. 이 용어는 예를 들어 매일 발생하는 일괄 처리와 구별합니다. 연속 데이터는 다음과 같이 이벤트가 발생한 후 15&#126;60분의 지연으로 업데이트됩니다.<ul><li>어트리뷰션(인스톨, 리어트리뷰션, 리인게이지먼트): 15&#126;30분. 1-60분</li><li>인앱 이벤트: 1-60분</li></ul> |
| 실시간 리포트 | 리포트 요청 후 몇 분 이내 | 데이터는 이벤트가 발생한 후 몇 분 이내에 업데이트됩니다. |
| 일일 | UTC 지대: 이벤트 당일 UTC 자정 이후 8시간<br /><br />서반구: UTC 지대: 이벤트 당일 UTC 자정 이후 8시간<br /><br />서반구: UTC 지대: 이벤트 당일 UTC 자정 이후 8시간 | <ul><li>데이터는 매일 처리</li><li>이 데이터의 가용성은 앱 시간대에 따라 다릅니다.</li><li>앱 시간대를 지원하지 않는 데이터 유형은 UTC 시간을 사용합니다.</li><li>데이터 가용성 시간은 매일 또는 특정 문서에 표시된 대로 다를 수 있습니다.</li></ul> |
| EOD (하루의 끝) | 매일 하루가 끝날 때 앱 시간대 | 력일의 마지막입니다. 다음 날 00:01을 의미합니다. 예시: 예: 월요일에 기록된 데이터는 앱 시간대에 관계없이 화요일 00:01부터 사용 가능합니다. |
| 일중(낮 기간에) | 평균 4시간마다 | <ul><li>데이터는 평균 4시간마다 하루에 6번 수집됩니다.</li><li>ROI360이 없는 고객의 SRN 클릭 및 노출 데이터는 하루 3회 수집됩니다.</li><li>비용 ETL 데이터는 평균 6시간마다 하루에 4번 전송됩니다.</li></ul> |
| 광고 수익 | 연동 유형 및 리포트에 따라 다름 | <Anchor target="_blank" href="/marketers/ko/docs/roi360-guide-ad-revenue-attribution#data-freshness">자세한 내용은 광고 수익 기사를 참조하십시오</Anchor>. |
| PBA 매일 | 데이터는 UTC 종료 후 11-12시간 후에 사용할 수 있습니다. | <ul><li>PBA 대시보드 및 리포트는 UTC 시간대를 사용하여 [매일](/docs/about-data-freshness-and-timezone-support#date-and-timezone-principles) 업데이트됩니다.</li><li>일일 처리에는 전날에 수신된 이벤트가 포함됩니다.</li><li>전환 후 처음 7일 동안 PBA는 전환과 관련된 추가 이벤트를 식별할 수 있습니다. 이는 KPI 및 미디어 소스 어트리뷰션을 소급하여 변경할 수 있습니다.</li><li>7일이 지나면 경로가 고정되고 더 이상 변경이 발생하지 않습니다.</li><li>로데이터 리포트에는 *final\_data* 필드가 포함됩니다. 실제 데이터가 최종 데이터일 때.</li><li><Anchor target="_blank" href="/marketers/ko/docs/using-pba-dashboards#traits-and-limitations">자세한 예시</Anchor></li></ul> |
| SKAN | 대시보드 및 리포트에서 포스트백 도착 시간부터 데이터를 사용할 수 있을 때까지의 <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-solution-guide#timing-from-app-install-until-dashboard-and-reports-update">타이밍에 대해 알아보세요</Anchor>. | 지정된 날짜에 받은 포스트백은 UTC에서 하루의 종료 시점에 처리됩니다. 데이터는 다음날 오전 11:00 UTC까지 이용 가능합니다. 월요일에 받은 iOS 포스트백은 화요일 아침에 리포트와 대시보드에서 사용할 수 있음을 의미합니다. 마찬가지로 파트너에 대한 포스트백은 화요일 아침에 전송됩니다.<br /><br />리포트 및 대시보드의 설치 날짜는 <Anchor target="_blank" href="/marketers/ko/docs/skan-conversion-studio#activity-window">SKAN 변환 스튜디오 기사</Anchor> 에 자세히 설명된 대로 포스트백 도착 시간에서 파생됩니다. |
| 데이터 락커 매일 | 데이터는 UTC 종료 후 8&#126;10시간 후에 사용할 수 있습니다. | <ul><li>데이터는 매일 처리됩니다.</li><li>데이터는 이벤트 날짜의 h=23 폴더에 들어갑니다. 예를 들어 월요일 데이터는 UTC 화요일 08:00–10:00에 월요일의 h=23 폴더에서 사용할 수 있습니다.</li><li>SKAN 데이터는 조금 늦게 도착할 수 있습니다(위의 SKAN 정보 참조).</li></ul> |

</Accordion>

<Accordion title="데이터 최신성 및 시간대 지원">

<table><thead><tr><th>관련 자료  </th><th>제시 방법  </th><th>데이터 최신성 비율<br/> </th><th>앱 시간대를 사용하여 데이터 표시</th></tr></thead><tbody><tr><td>인스톨</td><td>KPI</td><td><p>연속</p><p>참고할 예외:</p><ul><li>Protect360<ul><li></li></ul></li></ul></td><td><span>✓</span></td></tr><tr><td>세션, 클릭, 노출, 로열 유저</td><td>KPI</td><td><ul><li>+ 어트리뷰션 링크 연속</li><li>SRN: 일중</li></ul></td><td><span>✓</span></td></tr><tr><td>수익 인앱이벤트</td><td>KPI</td><td>연속</td><td><span>✓</span></td></tr><tr><td>광고 수익</td><td>KPI</td><td>광고 수익</td><td><span>✓</span></td></tr><tr><td>광고 비용(비용)</td><td>KPI</td><td><ul><li>어트리뷰션 링크: </li><li>API\* 일중</li><li>광고 지출 데이터 업로드 업로드 후 최대 4 시간</li></ul></td><td><span>✓</span></td></tr><tr><td>앱 삭제</td><td>KPI</td><td>일별. 앱스플라이어는 24시간마다 앱 스토어에 핑을 보냅니다. 앱 삭제 이벤트 시간은 앱스플라이어가 자동 푸시 알림을 핑하고 앱이 삭제되었음을 발견한 시간을 나타냅니다. 이것은 실제 앱 삭제 시간이 아닙니다.</td><td><span><strong>x</strong></span></td></tr><tr><td>인터페이스의 인앱이벤트</td><td>풀다운 목록</td><td><p>풀다운 목록에 표시되는 인앱이벤트 이름은 매일 업데이트됩니다.  </p><p>이는 데이터 자체의 데이터 최신성에 영향을 미치지 않습니다.  </p><p><strong>예시</strong> 예: Push API, 대시보드 및 잠재 고객의 풀다운 인앱이벤트 목록.</p></td><td><span>✓</span></td></tr><tr><td>개요 대시보드 </td><td>페이지</td><td>연속</td><td><span>✓</span></td></tr><tr><td>Protect360 대시보드</td><td>페이지 </td><td>일일</td><td> <span>✓ </span>(1)</td></tr><tr><td>SKAN 대시보드</td><td>페이지</td><td>일일</td><td><span><strong>x</strong></span></td></tr><tr><td>활동(Activity) 페이지 </td><td>페이지</td><td><ul><li>KPI 연속</li><li> </li></ul></td><td><p><span>✓</span></p></td></tr><tr><td>이벤트 페이지 </td><td>페이지</td><td>연속</td><td><span>✓</span></td></tr><tr><td>(빈 행)  </td><td> </td><td>(이 행은 의도적으로 비워 두었습니다)</td><td> </td></tr><tr><td>잔존율</td><td>페이지</td><td>리텐션 KPI는 일일 및 주간 단위로 사용할 수 있습니다. 각각의 데이터 최신성은 서로 다릅니다.  <ul><li> 일일</li><li>주별 리텐션 KPI: x  리텐션은 월요일 12:00 UTC에 계산됩니다. 주별 KPI에 대한 앱 시간대 지원이 없으면 무시할 수 있는 차이가 발생합니다.  </li></ul></td><td><p>일별: <span>✓</span></p><p>주별: <span><strong>x</strong></span></p></td></tr><tr><td>코호트</td><td>페이지</td><td>연속</td><td> <span>✓ </span>(2)</td></tr><tr><td>커스텀 대시보드</td><td>페이지</td><td>연속</td><td> <span>✓ </span>(3)</td></tr><tr><td>오디언스</td><td>페이지</td><td><ul><li>업데이트는 24시간마다 파트너에게 푸시됩니다.</li><li>사용자 기반은 매일 업데이트되며 최대 90일 동안 기기 데이터를 보유합니다.</li></ul></td><td><span>✓</span></td></tr><tr><td>SDK 정보 페이지</td><td>페이지</td><td>일일</td><td><span> <strong>x</strong></span></td></tr><tr><td>데이터 내보내기</td><td>페이지</td><td><p>연속</p><p>참고할 예외:</p><ul><li>광고 수익 원시 데이터 일일 </li><li>Protect360:<ul><li>통합 리포트 일일</li><li> 연속</li><li>포스트 어트리뷰션 로데이터: 매일 일일</li></ul></li><li>오가닉 인앱 이벤트 </li></ul></td><td><span>✓</span></td></tr><tr><td>Pull API</td><td>API </td><td>Pull API 데이터 최신성은 내보내기 데이터와 동일합니다.</td><td><p><span>✓</span></p><p><span>기본값 UTC</span></p></td></tr><tr><td>피봇 </td><td>페이지</td><td>일일</td><td><p><span>✓</span></p><p>주별 리텐션 KPI: <strong>x</strong></p></td></tr><tr><td>마스터 API</td><td> API</td><td>일일 </td><td> <span>✓ </span>(3)</td></tr><tr><td>데이터 락커</td><td>API</td><td> </td><td><p><span><strong>x</strong></span></p><p><span><strong>UTC</strong></span></p></td></tr><tr><td>포스트백</td><td>API</td><td>연속</td><td>해당 없음</td></tr><tr><td>Push API</td><td>API</td><td>연속</td><td><p><span>✓</span><br/> </p><p>둘 다</p></td></tr><tr><td>서버 간 인앱이벤트</td><td>API</td><td>연속</td><td>해당 없음</td></tr><tr><td colspan="4"><p>참고:</p><p>(1) 사용자가 권한을 가진 모든 앱은 동일한 앱 시간대를 사용해야 합니다. 그렇지 않으면 표준 시간대가 UTC로 돌아갑니다.</p><p>(2) 시간대가 UTC로 되돌아가는 <a href="./cohort-and-retention-dashboard#traits-and-limitations" target="_blank">코호트 특성 및 제한 사항을</a> 참조하십시오.</p><p>(3) 선택한 모든 앱은 동일한 앱별 시간대를 사용해야 합니다. 그렇지 않으면 표준 시간대가 UTC로 돌아갑니다.</p></td></tr></tbody></table>

</Accordion>
