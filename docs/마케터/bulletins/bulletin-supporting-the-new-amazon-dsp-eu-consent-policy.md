---
title: '업데이트 알림: 새로운 Amazon DSP EU 동의 정책 지원'
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2026-04-12T09:11:36Z'
  edited_at: '2026-10-14T10:27:14Z'
  id: 45664244736529
  locale: ko
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ko/articles/45664244736529
---
| 섹션 | 세부 정보 |
| --- | --- |
| **새로운 소식** | Amazon Ads는 디지털 시장법(DMA) 시행의 일환으로 EU 동의 정책을 업데이트하고 있습니다. 앱스플라이어는 Amazon의 정책 요구 사항을 지원하는 동시에 광고주가 Amazon Ads 마케팅 채널의 가치를 극대화할 수 있도록 필요한 변경을 진행하고 있습니다. |
| **시행일** | 2025년 6월 4일 |
| **주요 변경 사항:** | 관련 통합 및 대상 `amazondsp_int` SRN 연동을 통해 Amazon Ads와 연동된 앱을 사용하고 EU(영국 및 스위스 포함)에서 광고 활동을 하는 모든 광고주.<br /><br />**필요한 작업** EU, 영국 또는 스위스 사용자의 모든 이벤트(앱 오픈 또는 인앱 이벤트)에 대해 앱스플라이어에 유효한 DMA 동의 신호를 전달했는지 확인합니다.<br /><br />동의 신호는 다음 중 하나일 수 있습니다.<ol><li>**수동 동의:** 필요한 필드만이 수동 동의 어레이의 일부인 `ad_user_data_enabled`입니다. Google의 DMA 동의에 필요한 다른 필드는 Amazon과 관련이 없습니다.</li><li>**TCF 동의:** CMP에서 생성한 전체 TCF 동의 정보를 전송하고 동의한 공급업체 목록에 Amazon Ads 공급업체 ID(`793`)를 포함해야 합니다.</li><li>**GPP 동의 문자열:** Amazon은 GPP 동의 문자열을 지원하지만 현재 앱스플라이어에서 지원하지는 않습니다.</li></ol>**<span id="h_01KP0FAZ70YDRQ71TDRYFEG120"></span>참고 항목**<ul><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/send-consent-for-dma-compliance">앱스플라이어 SDK를 통해 DMA 동의를 보내는 방법</Anchor></li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/s2s-events-api3-post">앱스플라이어 S2S를 통해 DMA 동의를 보내는 방법</Anchor>(`consent_data` 검색)</li></ul> |