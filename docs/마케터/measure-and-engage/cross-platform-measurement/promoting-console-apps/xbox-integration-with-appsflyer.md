---
title: Xbox와 앱스플라이어의 통합
metadata:
  keywords:
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2023-04-13T08:28:00Z'
  edited_at: '2026-10-14T10:39:21Z'
  id: 14504812967057
  locale: ko
  section: Promoting Console apps
  section_id: 15329052471057
  url: https://support.appsflyer.com/hc/ko/articles/14504812967057
---
> **한눈에 보기:** Xbox 앱을 앱스플라이어와 통합하여 Xbox에서 캠페인에 대한 어트리뷰션 및 이벤트 데이터를 수신하세요.

<div id="about-xbox-attribution" />

## Xbox 어트리뷰션 정보

콘솔 및 CTV 앱용 Xbox OS는 모든 Xbox에서 실행됩니다.

Xbox에서 실행되는 앱은 S2S API를 통해 앱스플라이어와 통합해 앱 열기 및 인앱 이벤트를 유도하는 소스(오가닉)와 캠페인에 대한 어트리뷰션 데이터와 성과 측정값을 수신할 수 있습니다. 마케팅 담당자는 이러한 인사이트를 바탕으로 마케팅 활동을 측정하고 최적화합니다.

Xbox API 통합은 다음을 지원합니다.

* Xbox.
* Xbox 앱의 어트리뷰션 및 이벤트 기록. 사용자의 Xbox 기기에 관한 의미, 어트리뷰션 및 기록.

<div id="integration-procedures" />

## 통합 절차

다음 표에는 Xbox 앱을 앱스플라이어와 통합하는 데 필요한 작업이 나열되어 있습니다.

| 작업 | 액션 | 담당자 |
| --- | --- | --- |
| 앱 설정 | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">앱스플라이어 계정 만들기</Anchor></li><li><Anchor target="_blank" href="/marketers/ko/docs/user-management">적절한 권한이 있는 계정 사용자 추가</Anchor></li><li><Anchor target="_blank" href="/marketers/ko/docs/adding-an-app-to-appsflyer">앱스플라이어에 Xbox 앱 추가</Anchor></li></ul> | 마케터 |
| (S2S를 통해) 앱과 API 통합 | 앱스플라이어에 다음 이벤트를 보고하는 명령으로 앱에 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">앱스플라이어 API를 통합하세요.</Anchor><ul><li>첫 번째 열기</li><li>인앱 이벤트</li><li>세션</li></ul>**참고**:<ul><li>앱 내 이벤트 및 세션 전에 첫 번째 앱 실행을 보고해야 합니다.</li><li>`device_ids` 파라미터의 경우 `custom` 유형을 선택합니다.</li><li>API를 사용하여 이벤트를 전송합니다. 개발자에게 어떤 이벤트를 보낼지 알려주세요. API를 설정할 때, 앱스플라이어로 전송할 이벤트를 설정하고 매핑했는지 확인합니다.</li></ul>온드 미디어 참여를 보고하려면 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">노출 인게이지먼트 API</Anchor>를 통합하세요. | 앱 개발자 |
| 리포트 설정 | <Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-platform-attribution-concepts#데이터-가용성">대시보드 및 리포트의 데이터 가용성에 대해 알아보기</Anchor> | 마케터/데이터 엔지니어 |

<div id="traits-and-limitations" />

<Accordion title="특징 및 제한 사항">

| 특성 | 비고 |
| --- | --- |
| 리타겟팅 | 현재 지원되지 않음 |
| 비용 데이터 | 비용 데이터는 이메일 방식으로 파일 업로드를 사용하여 <Anchor target="_blank" href="/marketers/ko/docs/import-cost-data">비용 가져오기</Anchor>를 통해 전송해야 합니다. |

</Accordion>

<div id="see-also" />

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-platform-attribution-concepts">CTV, PC 및 콘솔 플랫폼 개요</Anchor>

<div data-zendesk-anchors="about-playstation-attribution=xbox-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%A0%95%EB%B3%B4 01H7Z1NEAJMRWKHS4K168V0753=xbox-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%A0%95%EB%B3%B4 integration-procedures=%ED%86%B5%ED%95%A9-%EC%A0%88%EC%B0%A8 01H7Z1NEAJJY4ZRVKY74ACXAAR=%ED%86%B5%ED%95%A9-%EC%A0%88%EC%B0%A8 01H7Z1NEAJRA11P7NG05KRKR8Q=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
