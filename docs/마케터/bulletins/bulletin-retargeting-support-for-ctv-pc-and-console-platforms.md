---
title: '알림: CTV, PC 및 콘솔 플랫폼을 위한 리타게팅 지원'
metadata:
  keywords:
    - Marketers
    - CTV Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - CTV Attribution
  created_at: '2026-07-07T14:08:17Z'
  edited_at: '2026-10-14T10:27:37Z'
  id: 48515925079313
  locale: ko
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ko/articles/48515925079313
---
| 새로운 소식 | 앱스플라이어에서 확장된(비모바일) 플랫폼인 CTV, PC 및 콘솔 플랫폼을 위한 리타게팅 측정, 리인게이지먼트, 그리고 리어트리뷰션을 이제 지원합니다: CTV, PC 및 콘솔. 이전에는 이러한 플랫폼에서 UA 어트리뷰션만 지원되었습니다.<br /><br />확장된 플랫폼을 위한 리타게팅에는 두 가지 전환 유형이 포함됩니다:<ul><li>**리인게이지먼트**는 기존에 이미 앱을 설치한 사용자를 다시 앱으로 불러오는 캠페인에 성과를 인정합니다.</li><li>**리어트리뷰션**(리타게팅 재설치)은 이탈한 사용자가 앱을 재설치하고 다시 열도록 유도하는 캠페인에 성과를 인정합니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/measure-reinstalls#reattribution">리어트리뷰션 측정</Anchor>을 참조하세요.</li></ul>이는 사용자를 재활성화하고 반복 소비를 유도하며 이탈을 줄이는 캠페인의 성과를 정확하게 인정하기 위해 리인게이지먼트 및 리어트리뷰션이 필수적인 라이프사이클 마케팅 집행 광고주에게 핵심적인 공백을 메워줍니다. 또한 코호트 및 LTV 정확도도 개선됩니다. 이전에는 리타게팅이 지원되지 않아 이후의 앱 활동이 최초 설치 일자에 귀속되었으며, 이로 인해 코호트, 회수 기간, LTV 분석이 왜곡되었습니다. 앱스플라이어가 확장된 플랫폼을 전반적으로 측정하는 방법에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-platform-attribution-concepts">CTV, PC 및 콘솔 플랫폼 어트리뷰션 개념</Anchor>을 참조하세요. |
| --- | --- |
| 시행일 | 2026년 8월 1일 |
| 해야 할 일 | 구성 레이어는 앱, 미디어 소스 또는 연동, 그리고 어트리뷰션 링크의 세 가지가 있습니다.<ol><li><Anchor target="_blank" href="/marketers/ko/docs/app-settings#어트리뷰션-설정">앱 설정</Anchor>에서 **리인게이지먼트 어트리뷰션** 토글을 켜세요. 앱의 마스터 스위치입니다. 이 기능이 꺼져 있으면 해당 앱의 어떤 미디어 소스에서도 리인게이지먼트를 활성화할 수 없습니다.</li><li>리타게팅을 집행하고자 하는 각 파트너 또는 미디어 소스의 **활성 연동** 페이지 내 **연동** 탭에서, 리어트리뷰션 성과를 인정하려면 **재설치 어트리뷰션**을 켜고, 리인게이지먼트 성과를 인정하려면 **리인게이지먼트 어트리뷰션**을 켜세요. 뷰스루 성과까지 측정하고자 한다면 **리인게이지먼트 뷰스루 어트리뷰션** 토글을 켜주시고, 클릭스루 측정만 필요한 경우에는 꺼둠 상태를 유지하세요.</li><li>비-SRN 네트워크의 경우 `af_campaign_type=retargeting`을(를) 어트리뷰션 링크에 추가하세요. 이 파라미터를 자동으로 추가하려면 **활성 연동** 페이지의 **어트리뷰션 링크** 탭에서 **리타게팅 설정 활성화**를 켜세요. 링크 생성 프로세스에 대한 자세한 정보는 <Anchor target="_blank" href="/marketers/ko/docs/retargeting-attribution-guide">리타게팅 어트리뷰션 가이드</Anchor> 및 <Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-platform-direct-attribution-links">CTV, PC, 콘솔 플랫폼 직접 어트리뷰션 링크</Anchor> 항목을 참조하세요. 캠페인에 이 링크를 사용하세요.</li></ol>**<span id="h_01KX0FSH3GN11MG98MZQAVJ5NC"></span>참고**<br />Roku는 현재 이러한 플랫폼에서 사용할 수 있는 유일한 셀프 리포팅 네트워크(SRN)로, 리인게이지먼트만 지원합니다. 리어트리뷰션은 지원되지 않으며, 설정할 어트리뷰션 링크가 없습니다. Roku의 경우 토글이 켜져 있기만 하면 모든 클레임이 리타게팅 대상이 됩니다. |
| 알아두어야 할 사항 | 확장된 플랫폼에서 리타게팅을 측정할 때 다음 사항을 염두에 두세요:<ul><li>**지원되는 플랫폼** 확장된 플랫폼을 위한 리타게팅은 Android, iOS, Windows Phone 또는 웹사이트가 아닌 모든 플랫폼에 적용됩니다. 실제로는 CTV, PC 및 콘솔 앱이 이에 해당합니다.</li><li>**범위:** 이 기능은 비모바일 플랫폼(CTV, PC, 콘솔)에만 적용됩니다. 모바일로 연결되는 크로스 플랫폼 리타게팅은 지원되지 않습니다. 예를 들어, CTV 광고를 통해 모바일 앱 설치를 유도하는 방식은 여전히 지원되지 않습니다. 웹 광고를 통해 PC 앱 설치를 유도하는 방식은 지원됩니다.</li><li>**SRN 제한:** Roku는 현재 이러한 플랫폼에서 이용 가능한 유일한 SRN으로, 재설치나 리어트리뷰션은 지원하지 않고 리인게이지먼트만 지원합니다. 향후 추가될 다른 SRN에는 이 내용이 적용되지 않을 수 있습니다.</li><li>**옵션 창:** 리인게이지먼트 윈도우(기본값 30일)는 앱 내 이벤트가 주로 리인게이지먼트 전환으로 어트리뷰션되는 기간을 결정합니다. 비활성화 윈도우(기본값 7일)는 사용자가 리타게팅 대상이 되기 위해 비활성 상태여야 하는 기간을 결정합니다. 이러한 윈도우 설정은 모바일과 동일하게 작동합니다. 링크 생성 및 가이드는 <Anchor target="_blank" href="/marketers/ko/docs/retargeting-attribution-guide#포함-기간">리타게팅 어트리뷰션 가이드</Anchor> 및 <Anchor target="_blank" href="/marketers/ko/docs/set-retargeting-inactivity-window">비활성화 윈도우 설정</Anchor> 항목을 참조하세요.</li><li>**결과가 표시되는 위치:** 대시보드 화면 및 Data Locker 고급 리포트 기능에만 한정되어 적용됩니다. 기존 Data Locker 내 클래식 리포트 항목에는 신규 리타게팅 로우 데이터 리포트가 포함되지 않습니다. 플랫폼별 대시보드 동작은 개요 대시보드 — 사용자 획득 및 리타겟팅 LTV를 참조하십시오.</li></ul> |