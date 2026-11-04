---
title: 앱스플라이어와 Vidaa 연동
metadata:
  keywords:
    - CTV
    - Marketers
    - CTV Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - CTV Attribution
  created_at: '2022-11-06T08:13:09Z'
  edited_at: '2026-10-14T10:33:37Z'
  id: 10400222972433
  locale: ko
  section: Promoting CTV apps
  section_id: 15328952633489
  url: https://support.appsflyer.com/hc/ko/articles/10400222972433
---
> **요약:** Vidaa 커넥티드 TV(CTV) 앱을 앱스플라이어와 연동하여 Vidaa 캠페인에 대한 어트리뷰션 및 이벤트 데이터를 수신할 수 있습니다.

<div id="about-vidaa-ctv-attribution" />

## Vidaa CTV 어트리뷰션 정보

스트리밍용 Vidaa OS는 모든 Vidaa TV에서 실행됩니다.

Vidaa에서 스트리밍하는 CTV 앱은 API를 통해 앱스플라이어와 연동해 앱 열기 및 인앱 이벤트를 유도하는 소스(오가닉)와 캠페인에 대한 어트리뷰션 데이터와 성과 측정값을 수신할 수 있습니다. 마케터는 이러한 인사이트를 바탕으로 마케팅 활동을 측정하고 최적화합니다.

Vidaa API 연동은 다음을 지원합니다.

* Vidaa 스마트 TV.
* CTV-투-CTV 어트리뷰션 및 이벤트 기록. 즉, 사용자의 Vidaa 기기에 대한 어트리뷰션 및 기록.

<div id="integration-procedures" />

## 연동 절차

다음 표에는 Vidaa CTV 앱을 앱스플라이어와 연동하는 데 필요한 작업이 나열되어 있습니다. 진행 상황을 기록하려면 이 <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vSFsuk9liZ_z34w3kHMyOFzASh5PBDtdn_HxgMqxAYY0wEt5RxCdrXeyLvteC5Cp-x-6ESwO5YbJ0n-/pub?output=xlsx">스프레드시트</Anchor>를 다운로드하세요.

| 작업 | 액션 | 담당자 |
| --- | --- | --- |
| 앱 설정 | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">앱스플라이어 계정 만들기</Anchor></li><li><Anchor target="_blank" href="/marketers/ko/docs/user-management">적절한 권한이 있는 계정 사용자 추가</Anchor></li><li><Anchor target="_blank" href="/marketers/ko/docs/adding-an-app-to-appsflyer">앱스플라이어에 Vidaa CTV 앱 추가</Anchor></li></ul> | 마케터 |
| 앱과 API 통합(S2S를 통한) | 다음 이벤트를 앱스플라이어에 보고하는 명령을 사용하여 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">앱스플라이어 CTV API</Anchor>를 CTV 앱에 통합하세요.<ul><li>첫 번째 열기</li><li>인앱 이벤트</li><li>세션</li></ul>**참고**:<ul><li>인앱 이벤트 및 세션 전에 인스톨을 보고해야 합니다.</li><li>API를 사용하여 이벤트를 보냅니다. 개발자에게 어떤 이벤트를 보낼지 알려주세요. API를 설정할 때, 앱스플라이어로 전송할 이벤트를 설정하고 매핑했는지 확인합니다.</li><li>`device_ids` 파라미터의 경우 `custom` 유형을 선택합니다.</li></ul>온드 미디어 인게이지먼트를 보고하려면 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">노출 인게이지먼트 API</Anchor>를 연동하세요. | 앱 개발자 |
| 링크 설정 | <Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-platform-direct-attribution-links">직접 어트리뷰션 링크를 만드는 방법 알아보기</Anchor> | 마케터 |
| 리포트 설정/데이터 보기 | <Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-platform-attribution-concepts#데이터-가용성">대시보드 및 리포트의 데이터 가용성에 대해 알아보기</Anchor> | 마케터/데이터 엔지니어 |

<div id="traits-and-limitations" />

<Accordion title="특징 및 제한 사항">

| 특성 | 비고 |
| --- | --- |
| 논오가닉 소스 | 업데이트 예정 |
| 리타겟팅 | 현재 지원되지 않음 |
| 비용 데이터 | 비용 데이터는 이메일 방식으로 파일 업로드를 사용하여 <Anchor target="_blank" href="/marketers/ko/docs/import-cost-data">비용 가져오기</Anchor>를 통해 전송해야 합니다. |

</Accordion>

<div id="see-also" />

> 📄 **참고 항목**
>
> * <span id="overview"></span><Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-platform-attribution-concepts">CTV, PC 및 콘솔 플랫폼 개요</Anchor>

<div data-zendesk-anchors="about-vidaa-ctv-attribution=vidaa-ctv-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%A0%95%EB%B3%B4 01H7Z180QRR77E1GBQ0P0RHVN5=vidaa-ctv-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%A0%95%EB%B3%B4 integration-procedures=%EC%97%B0%EB%8F%99-%EC%A0%88%EC%B0%A8 01H7Z180QR6HT4R3N9DYSM8WB9=%EC%97%B0%EB%8F%99-%EC%A0%88%EC%B0%A8 01H7Z180QR0QQ0HK3N5N1G4ENZ=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
