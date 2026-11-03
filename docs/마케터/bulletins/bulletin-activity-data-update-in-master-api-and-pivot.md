---
title: '업데이트 알림: Master API 및 Pivot 액티비티 데이터 업데이트'
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2026-08-17T07:26:26Z'
  edited_at: '2026-10-14T10:27:25Z'
  id: 49896622875537
  locale: ko
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ko/articles/49896622875537
---
| 섹션 | 세부 정보 |
| --- | --- |
| 새로운 소식 | Master API와 Pivot이 마이 대시보드, 앱스플라이어 MCP, AI Assistant 및 에이전트에 이미 적용 중인 동일한 액티비티 데이터를 사용하도록 전환됩니다. 이에 따라 어디서 확인하든 액티비티 지표가 완벽하게 일치하게 됩니다.<br /><br />액티비티 데이터의 필터링 및 그룹화에 사용되는 일부 하위 값들이 변경됩니다. 자세한 내용은 아래를 참조해 주세요.<br /><br />대부분의 고객은 별도의 조치를 취할 필요가 없습니다. |
| 시행일 | 2026년 9월 14일 |
| 영향을 받는 대상 | <ul><li>액티비티 지표를 분석하는 모든 Master API 및 Pivot 고객: `activity_average_dau`, `activity_average_dau_mau_rate`, `activity_average_arpdau`, `activity_sessions`, `activity_revenue`, `activity_event_counter_[event_name]`, `activity_sales_in_usd_[event_name]`, `activity_average_unique_users_[event_name]`.</li></ul>참고: `activity_average_mau`은(는) 영향을 받지 않습니다.<ul><li>코호트, LTV, 리텐션 및 기타 데이터 유형은 변경되지 않습니다. 동일한 리포트에서 액티비티를 해당 항목들과 함께 조회할 경우, 다른 데이터 유형에 동일한 변경 사항이 적용되기 전까지 일부 값(특히 미디어 소스 / `pid`)이 일치하지 않을 수 있습니다.</li></ul> |
| 필요한 작업 | 이 변경 사항은 자동으로 적용되며, 대부분의 고객은 별도의 조치를 취하실 필요가 없습니다.<br /><br />아래에 나열된 값으로 액티비티 보고서를 필터링하거나 그룹화하는 경우, 2026년 9월 14일 이후 해당 필터 항목을 확인해 주세요. 기존 값을 사용할 경우 다른 결과가 조회되거나 결과가 나오지 않을 수 있습니다. |
| 알아두어야 할 사항 | 다음 변경 사항을 참고해 주세요.<br /><br />* **업데이트 이후 지표 값에 미세한 차이가 발생할 수 있습니다.** 액티비티 데이터가 새로운 데이터 파이프라인으로 이관됨에 따라 지표 값에 미세한 변동이 발생할 수 있습니다. 순 사용자(Unique Users), DAU 및 관련 지표의 경우 최대 3%까지 차이가 발생할 수 있습니다. 이는 데이터 오류가 아니라 파이프라인 변경의 일환으로 예상되는 현상입니다.<br />* **"Pre-install" 및 "preload"는 이제 `attributed_touch_type` 그룹화 시 "download"로 통합됩니다**. Master API의 `attributed_touch_type` 항목을 "pre-install" 또는 "preload"로 필터링하거나 그룹화할 경우 더 이상 별도의 결과가 조회되지 않습니다. 해당 트래픽은 이제 "download" 아래에 표시됩니다.<br />* **Null 값은 빈 문자열로 대체됩니다.** 여기에는 유기적/비 미디어 소스(Master API의 `pid`, Pivot의 미디어 소스)가 포함되며, 이제 빈 문자열로 표시됩니다.<br />* **두 가지 미디어 소스 이름이 변경됩니다:** `facebook`은(는) `Facebook Ads`이(가) 되고, `twitter` 및 `twitter_int`은(는) `Twitter`이(가) 됩니다. 다른 모든 미디어 소스 이름은 변경되지 않습니다.<br />* **특정 문자는 밑줄로 대체됩니다.** 제어 문자와 `;`, `{`, `}`, `$`, `<`, `>`, `'`, `\` 문자는 모두 언더스코어(\_)로 대체됩니다.<br />* **새로운 필드 제한이 적용됩니다.**<br />  * `ad_id` (250)<br />  * `ad_name` (256)<br />  * `event_name` (100)<br />  * `app_version` (64)<br />  * `agency` (32)<br />  * `keywords` (90)<br />  * `install_app_store` (50)<br />  * `os_version` (20)<br /><br />이번 이관을 통해 액티비티 데이터가 한층 더 현대적이고 확장 가능한 인프라로 이동하며, 이를 통해 안정성과 성능이 향상되고 향후 제품 개선까지 더욱 강력하게 지원하게 됩니다. |