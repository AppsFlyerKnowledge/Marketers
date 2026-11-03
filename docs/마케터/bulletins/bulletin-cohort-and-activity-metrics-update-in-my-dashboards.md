---
title: '업데이트 알림: My Dashboard의 Cohort 지표 업데이트'
metadata:
  keywords:
    - Partners
    - Marketers
    - Marketing Analytics
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maya-kahane
    - Marketers
    - Marketing Analytics
  created_at: '2026-04-19T14:38:57Z'
  edited_at: '2026-10-14T10:27:44Z'
  id: 45887523041425
  locale: ko
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ko/articles/45887523041425
---
| **새로운 기능은 무엇인가요?** | **2026년 7월**부터 **My Dashboards**의 Cohort 및 Activity 지표가 **AI 기반 데이터** 지원을 위해 설계된 업그레이드된 데이터 인프라로 이전됩니다. 이러한 변경 사항은 **2026년 7월부터 8월에** 걸쳐 고객사별로 점진적으로 적용될 예정입니다.<br /><br />이 점진적인 롤아웃의 일환으로, 일부 지표 값, 과거 데이터 가용성 및 세분화 옵션에 변경 사항이 있을 수 있습니다.<br /><br />이번 업데이트를 통해 Activity 데이터에 새로운 뷰 타입과 지표가 도입되며, Cohort 데이터 내 Unique Users 수의 정확도가 향상됩니다. 아울러 Cohort와 Activity 모두에서 과거 데이터 조회 기간 및 세그멘테이션 옵션이 한층 더 확장됩니다. |
| --- | --- |
| **시행일** | 2026년 7월부터 8월까지 점진적으로 출시됩니다. |
| **필요 대상** | **My Dashboards**에서 Cohort 또는 Activity 지표를 사용하는 모든 광고주, 대행사 및 파트너사. |
| **필요한 작업** | 아무 조치도 필요하지 않습니다. 변경 사항이 자동으로 적용됩니다. |
| **알아두어야 할 사항** | **<span id="h_activity-retargeting-and-ua-view-types"></span>이제 Activity 데이터에서 Retargeting 및 UA 뷰 타입을 사용할 수 있습니다.**<br /><br />이제 Activity 데이터를 Retargeting 및 UA를 포함한 뷰 타입별로 필터링하고 분석할 수 있습니다.<ul><li>Retargeting 데이터는 2025년 2월부터 사용할 수 있습니다.</li><li>UA 데이터는 2026년 2월부터 사용할 수 있습니다.</li><li>Retargeting 및 UA 뷰에 당일 데이터는 포함되지 않습니다. 데이터가 1일 지연됩니다.</li></ul>**<span id="h_net-revenue-metrics"></span>이제 Cohort 및 Activity 데이터에서 Net Revenue 지표를 확인할 수 있습니다.**<br /><br />ROI360을 통해 순매출을 측정하거나 인앱 이벤트에 `af_net_revenue` 이벤트 파라미터를 전달하여 측정 중인 고객사는 이제 다음과 같은 항목을 확인할 수 있습니다:<ul><li>Net Revenue</li><li>Net ROAS</li><li>Net ROI</li><li>Net ARPU</li><li>Net Gross Profit</li></ul>이러한 지표는 순수익 데이터를 전송하는 고객에게만 표시됩니다.<br /><br />**<span id="h_ctv-app-support"></span>이제 Cohort 및 Activity 데이터에서 CTV 앱 지원 기능이 제공됩니다.**<br /><br />이제 CTV 앱에서도 Cohort 및 Activity 지표를 확인할 수 있습니다.<br /><br />**<span id="h_new-dimensions"></span>이제 Cohort 및 Activity에 새로운 디멘션이 제공됩니다.**<br /><br />Cohort 및 Activity 모두에서 세그멘테이션 분석을 위해 활용할 수 있는 신규 디멘션이 추가되었습니다:<ul><li>Platform</li><li>Sub 1</li><li>Engagement destination</li></ul>**<span id="h_extended-historical-data"></span>Cohort 과거 데이터 조회 기간 확장**<br /><br />대부분의 Cohort 지표에서 이제 **2024년 5월 6일** 이후의 데이터에 접근할 수 있게 되어, 이전보다 약 6개월 더 확장된 과거 데이터를 확인할 수 있습니다.<br /><br />**2025년 6월 3일**부터 조회가 지원되는 일간 Unique Users 데이터에는 해당되지 않습니다.<br /><br />**<span id="h_unique-users-updated-calculation-method"></span>Cohort 일자별 상세 분석 내 Unique Users 데이터 산출 방식 변경**<br /><br />Day 1, Day 7 등 일별 Cohort 상세 분석 시, 이제 다음 지표들에 업데이트된 계산 방식이 적용됩니다:<ul><li>앱 내 이벤트 Unique Users</li><li>Retention</li><li>Retention Rate</li><li>ARPU</li></ul>**<span id="h_what-changed-and-why"></span>무엇이 왜 바뀌었나요?**<br /><br />사용자 식별 기준이 디바이스 레벨로 변경되었습니다. 여러 번 Re-engagement한 사용자는 각 참여 건별로 중복 집계되지 않고 한번만 카운트됩니다.<br /><br />이를 통해 Re-engagement campaigns를 진행하는 앱에서 기존에 발생하던 데이터 중복 집계 오류가 해결됩니다.<br /><br />앱에서 Re-engagement campaigns를 운영 중인 경우, 일별 Unique User 수가 감소한 것으로 나타날 수 있습니다. 이는 실제 사용자나 성과 감소가 아닌 수정입니다.<br /><br />새로운 방식은 확률론적 카운팅 접근법을 사용하여 통상 1-2% 이내의 매우 미미한 근사 오차 범위가 발생할 수 있습니다. 이는 예상된 결과이며 데이터 오류가 아닙니다.<br /><br />**<span id="h_unique-users-data-availability"></span>데이터 가용성**<ul><li>일별 세부 데이터는 **2025년 6월 3일** 이후부터 조회할 수 있습니다.</li><li>이전의 일별 Unique Users 데이터는 My Dashboards에서 지원되지 않습니다.</li><li>주별 및 월별 세부 데이터 분석에는 영향을 미치지 않습니다. 전체 기록은 계속 사용 가능합니다.</li></ul>**<span id="h_activity-unique-users-and-active-users-historical-availability"></span>Activity 데이터 내 Unique Users 및 Active Users 과거 조회 가능 기간**<br /><br />**2025년 6월 3일** 이전 날짜의 경우, Activity 데이터 내 Unique Users 및 Active Users 지표는 일자별 브레이크다운 형태로만 조회할 수 있습니다.<br /><br />특정 기간 전체의 총합 데이터는 **2025년 6월 3일**부터의 데이터에 한해 조회가 지원됩니다.<br /><br />본 사항은 Unique Users 또는 Active Users 데이터를 기반으로 산출되는 모든 지표에 적용됩니다. 이는 영구적인 제한입니다.<br /><br />**<span id="h_uninstalls-temporarily-unavailable"></span>Cohort 데이터 내 앱 삭제(Uninstall) 지표 일시적 이용 불가**<br /><br />앱 삭제(Uninstall) 지표는 현재 일시적으로 이용하실 수 없습니다. 해당 지표는 1&#126;2분기 내에 다시 제공될 예정입니다.<br /><br />**LTV는 영향을 받지 않습니다.**<br /><br />**<span id="h_ad-revenue-unified-in-utc"></span>모든 대시보드에서 UTC로 통합된 광고 수익**<br /><br />모든 대시보드의 광고 수익 지표는 이제 연동 방식이나 앱 수준의 시간대 설정과 관계없이 일괄 UTC 기준으로 표시됩니다.<br /><br />과거 데이터는 영향을 받지 않습니다.<br /><br />**<span id="h_about-the-transition"></span>전환 관련 정보**<br /><br />이번 마이그레이션의 목적은 Cohort 및 Activity 데이터를 더 현대적이고 확장 가능한 인프라로 이전하는 것입니다. 이를 통해 데이터 신뢰성과 성능을 향상시키고, AI 기반 분석 역량을 확보하며, 앱스플라이어의 집계형 어트리뷰션 데이터 전반에 걸친 향후 제품 개선을 지원하고자 합니다.<br /><br />이전 데이터가 필요한 경우에는 기존 Cohort 및 Retention 대시보드를 계속 이용하실 수 있습니다. 해당 대시보드를 통해 **2025년 6월 3일** 이전의 Cohort Unique Users 데이터를 확인하거나, 지표 재구축 작업이 진행되는 동안 앱 삭제(Uninstall) 데이터를 조회할 수 있습니다. |

<div data-zendesk-anchors="activity-retargeting-and-ua-view-types=h_activity-retargeting-and-ua-view-types net-revenue-metrics=h_net-revenue-metrics ctv-app-support=h_ctv-app-support new-dimensions=h_new-dimensions extended-historical-data=h_extended-historical-data unique-users-updated-calculation-method=h_unique-users-updated-calculation-method what-changed-and-why=h_what-changed-and-why unique-users-data-availability=h_unique-users-data-availability activity-unique-users-and-active-users-historical-availability=h_activity-unique-users-and-active-users-historical-availability uninstalls-temporarily-unavailable=h_uninstalls-temporarily-unavailable ad-revenue-unified-in-utc=h_ad-revenue-unified-in-utc about-the-transition=h_about-the-transition" />
