---
title: '업데이트 알림: TikTok for Business—고급 SRN'
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2022-07-26T12:27:56Z'
  edited_at: '2026-10-14T10:40:47Z'
  id: 7925111265041
  locale: ko
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ko/articles/7925111265041
---
<div id="note" />

> 📘 **참고사항**
>
> 2023년 1월 30일에 새로운 TikTok for Business —고급 SRN 연동 **tiktokglobal\_int**이 추가되었으며, `레거시 TikTok for Business 연동`**bytedanceglobal\_int**은 단계적으로 중단되어 2024년 3월부터 종료됩니다. 이 전환은 TikTok에서 처리하며 이전 연동을 언제 삭제할지 사용자에게 알려줍니다. **데이터 손실을 방지하려면 전환 단계에서 두 연동을 모두 활성 상태로 유지해야 합니다**.

| <span id="headline"></span>**헤드라인** | 앱스플라이어는 이제 TikTok For Business를 고급 자가 리포팅 네트워크(SRN)로 지원합니다. |
| --- | --- |
| <span id="effective-date"></span>**발효일** | <ul><li>1월 18일 New `tiktokglobal_int`</li><li>2024년 7월 31일</li></ul> |
| <span id="where-is-it-changing"></span>**변경되는 사항** | 연동 파트너의 TikTok For Business 연동 페이지. |
| <span id="required-actions"></span>**필요한 작업** | <ul><li><Anchor target="_blank" href="/marketers/ko/docs/tiktok-for-business-advanced-srn-integration-setup">새 연동을 설정합니다</Anchor>. TikTok For Business의 새로운 PID는 `tiktokglobal_int`입니다.</li><li>TikTok For Business `bytedanceglobal_int`와의 기존 연동이 있는 경우 데이터 손실을 방지하려면 **전환 날짜**까지 삭제하지 마세요(아래 행 참조).</li></ul> |
| <span id="transition-date"></span>**전환 날짜** | 새 통합을 활성화하고 TikTok For Business가 예상대로 작동하는지 테스트하면 기존 `bytedanceglobal_int` 통합에서 새 통합으로 전환하는 정확한 날짜를 알려주기 위해 연락을 드릴 것입니다. 이 작업은 **최대 45일이 소요될 수** 있으며, 이 기간 동안 대시보드 및 보고서에 레거시 통합의 데이터가 계속 표시됩니다.<br /><br />전환 날짜 이후에는 대시보드와 보고서에 새 `tiktokglobal_int` 통합의 데이터가 표시됩니다.<br /><br />**참고:** 메모: 레거시 통합에서 전환되지 않는 새 통합의 경우 데이터가 대시보드 및 보고서에 즉시 표시됩니다. |
| <span id="what-does-this-new-integration-mean"></span>**이 새로운 연동은 무엇을 의미합니까?** | <ul><li>**대시보드 및 리포트**<ul><li>전환 날짜 이후에는 모든 TikTok For Business 신규 전환이 새 PID `tiktokglobal_int`에 어트리뷰트됩니다.</li><li>새 연동을 활성화하기 전에 기록된 클릭 수와 노출 수는 `bytedanceglobal_int`에 어트리뷰트됩니다.</li></ul></li><li><Anchor target="_blank" href="/marketers/ko/docs/tiktok-for-business-advanced-srn-integration-setup#cost-tab-for-cost-clicks-and-impressions">집약된 클릭 수 및 노출 수</Anchor>전환일 이후에는 로데이터 수준 리포트를 통해 클릭 수와 노출 수를 확인할 수 없습니다. TikTok과의 API 연결을 활성화한 후 집약된 데이터가 포함된 리포트에서 사용할 수 있습니다.<br />**참고:**<ul><li>연동을 설정하는 동안 API 연결을 활성화해야 합니다.</li><li>전환 프로세스에는 앱스플라이어 측정 리포팅에 상당한 변화가 필요하므로 클릭 및 노출 데이터를 새로운 연동에 즉시 사용할 수 없습니다.</li></ul></li><li>**비용 데이터**<ul><li>새 <Anchor target="_blank" href="/marketers/ko/docs/tiktok-for-business-advanced-srn-integration-setup#cost-tab-for-cost-clicks-and-impressions">`tiktokglobal_int`</Anchor> 비용 통합과 기존 `bytedanceglobal_int` 비용 <Anchor target="_blank" href="/marketers/ko/docs/tiktok-for-business-advanced-srn-integration-setup#cost-tab-for-cost-clicks-and-impressions">통합</Anchor> 이 동시에 활성화된 경우 **비용 데이터가 두 번 나타날 수 있습니다**. **비용 통합이 하나만 켜져** 있는지 확인하여 이를 방지할 수 있습니다.<br />그러나 새 비용 연동을 활성화하면 전환일 이전 5일 동안의 비용 데이터가 자동으로 수집됩니다. 즉, 새 연동은 이전 5일 동안 중복된 비용 데이터를 표시할 것으로 예상됩니다. **예를 들어**, 이전 비용 연동이 1월 15일에 비활성화되고 새 비용 연동이 같은 날에 활성화된 경우, 1월 15일에만 활성화되었더라도 1월 10일에서 14일 사이에 새 비용 연동에 중복 비용 데이터가 표시됩니다.</li><li>**하나의 비용 통합만 켜져 있는지 확인하는 방법은 다음과 같습니다.**<ol><li>**전환 날짜**에 **레거시 통합** 의 **비용** 탭으로 이동하여 토글을 **끕니다**.</li><li>그런 다음 **새 통합** 의 **비용** 탭으로 이동하여 토글을 **켭니다**.</li></ol></li><li>전환 날짜 이후에는 비용 데이터가 새 PID와 연결됩니다. 레거시 비용 데이터를 보려면 대시보드 필터링 옵션에 이전 PID를 포함합니다.</li><li>전환 기간 동안 인스톨 번호는 며칠 동안 두 연동 간에 분할될 수 있지만 비용 데이터에는 모든 것이 표시됩니다. 이 기간 동안 이 데이터에 의존하는 KPI(예: eCPI 및 ROI)가 정확하지 않을 수 있다는 것을 주목하십시오.<br />cost integration on.png</li></ul></li></ul><ul><li>**SKAN 포스트백**<br />`SKAN 포스트백`전환 날짜 이후에는 모든 SKAN 포스트백이 새로운 연동 tiktokglobal\_int과 연결됩니다.</li><li>**리타겟팅 캠페인**<br />**리타게팅 캠페인새 통합으로 마이그레이션할 때 재참여 토글은 레거시 통합의 상태에 관계없이 기본적으로 꺼져 있습니다. <Anchor target="_blank" href="/marketers/ko/docs/retargeting-attribution-guide">리타게팅 캠페인의</Anchor> 경우** 연속성을 보장하려면 **새 통합에서재참여 토글을** 켜 **야 합니다.**</li></ul> |
| <span id="example-illustrating-the-process"></span>**프로세스를 설명하는 예** | <ul><li>비용 연동을 해제합니다. 두 연동이 모두 켜져 있지만 새 연동은 아직 활성화되지 않았으며 이에 대한 기여도 없습니다.</li><li>데이터를 승인한 후 전환 날짜를 알려줍니다. 이 예제에서는 11일 차가 됩니다.<br />그동안 대시보드와 리포트에는 레거시 연동에 대한 속성만 표시됩니다. 두 연동에서 비용이 켜져 있으면 둘 다 두 배의 비용 데이터를 표시합니다. 이를 방지하려면 새 연동에 대해 비용을 사용하지 않는 것이 좋습니다.</li><li>전환일로부터 약 일주일 동안(모든 이전 클릭이 만료될 때까지) 기여 데이터는 두 연동 간에 분할됩니다.<ul><li>새로운 연동을 위해 TikTok은 데이터를 SRN으로 보냅니다.</li><li>레거시 연동의 경우, 앱스플라이어는 전환일 이전의 이전 클릭을 여전히 어트리뷰션할 수 있습니다.</li></ul></li><li>향후 60일 동안 인앱이벤트에 대한 어트리뷰션이 레거시 연동에 계속 제공될 수 있습니다. 따라서 앱스플라이어가 이러한 이벤트에 대한 포스트백을 계속 보낼 수 있도록 하려면 레거시 연동을 (연동 탭에서) 켜두는 것이 좋습니다.<br />새 연동에 대해 비용 연동이 꺼져 있는 경우 이제 켤 수 있습니다. 이중 비용 데이터가 표시되지 않도록 하려면 레거시 연동에서 비용을 끕니다.</li><li>TikTok은 이제 SRN 역할을 하며 더 이상 인앱 이벤트 포스트백이 필요하지 않습니다.<br />레거시 통합이 꺼져 있더라도 아직 레거시 비용 통합을 해제하지 않은 경우 새 통합에서 중복 비용 데이터가 계속 표시됩니다.</li></ul> |

<div id="see-also" />

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="https://appsflyer.showpad.com/share/XB6r4QA1TN0wN63kqmslA">TikTok과의 새로운 Advanced SRN 통합으로 성공적으로 전환</Anchor>
> * 앱스플라이어의 새로운 기능

<div data-zendesk-anchors="01H8JZVADPFQ4NTHMCB8PSCV6P=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD h_01HDPFFJ6129APQF5DV3TV0SM2=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
