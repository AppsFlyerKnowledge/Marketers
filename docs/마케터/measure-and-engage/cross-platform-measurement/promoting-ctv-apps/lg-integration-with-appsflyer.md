---
title: LG와 앱스플라이어의 연동
metadata:
  keywords:
    - Advertisers
    - Developers
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
  created_at: '2022-07-03T10:31:42Z'
  edited_at: '2026-10-14T10:38:18Z'
  id: 7341725624081
  locale: ko
  section: Promoting CTV apps
  section_id: 15328952633489
  url: https://support.appsflyer.com/hc/ko/articles/7341725624081
---
> **한눈에 보기:** LG 커넥티드 TV(CTV) 앱을 앱스플라이어와 연동하여 LG 캠페인에 대한 어트리뷰션 및 이벤트 데이터를 수신하세요.

## LG CTV 어트리뷰션 정보

스트리밍용 LG Webos OS는 모든 LG TV에서 실행됩니다.

LG에서 스트리밍하는 CTV 앱은 API를 통해 앱스플라이어와 연동해 앱 열기 및 인앱 이벤트를 유도하는 소스(오가닉 및 논오가닉)와 캠페인에 대한 어트리뷰션 데이터와 성과 측정값을 수신할 수 있습니다. 마케팅 담당자는 이러한 인사이트를 바탕으로 마케팅 활동을 측정하고 최적화합니다.

LG API 연동은 다음을 지원합니다.

* LG 스마트 TV.
* CTV 간 어트리뷰션 및 이벤트 녹화. 사용자의 LG 기기에 대한 의미, 어트리뷰션 및 기록.

## 연동 절차

다음 표에는 LG CTV 앱을 앱스플라이어와 연동하는 데 필요한 작업이 나열되어 있습니다.

| 작업 | 액션 | 담당자 |
| --- | --- | --- |
| 앱 설정 | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">앱스플라이어 계정 만들기</Anchor></li><li><Anchor target="_blank" href="/marketers/ko/docs/user-management">적절한 권한이 있는 계정 사용자 추가</Anchor></li><li><Anchor target="_blank" href="/marketers/ko/docs/adding-an-app-to-appsflyer">앱스플라이어에서 LG CTV 앱 추가</Anchor></li></ul> | 마케터 |
| 앱과 API 연동(S2S 또는 SDK를 통해) | S2S 및 SDK의 두 가지 연동 방법을 S2S 및 SDK.<br /><br />S2S 방법의 경우 앱스플라이어에 다음 이벤트를 보고하는 명령으로 앱에 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">앱스플라이어 API를 연동</Anchor>하세요.<ul><li>첫 번째 열기</li><li>인앱 이벤트</li><li>세션</li></ul>**참고**:<ul><li>인앱 이벤트 및 세션 전에 인스톨을 보고해야 합니다.</li><li>API를 사용하여 이벤트를 보냅니다. 개발자에게 어떤 이벤트를 보낼지 알려주세요. API를 설정할 때, 앱스플라이어로 전송할 이벤트를 설정하고 매핑했는지 확인합니다.</li></ul>온드 미디어 인게이지먼트를 보고하려면 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">노출 인게이지먼트 API</Anchor>를 통합하세요.<br /><br />SDK 방법의 경우 <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-html5-ctv-sdk">LG용 개발자 허브 설명서</Anchor>를 참조하세요. | 앱 개발자 |
| 파트너 연동 | 앱스플라이어에서 삼성을 광고 네트워크 (통합 파트너) 로 추가하세요.<ol><li><Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#a-activate-partner">파트너 활성화</Anchor></li><li>[선택 사항] **<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#e-install-attribution">뷰스루 어트리뷰션</Anchor>을 켭니다.**</li></ol> | 마케터 |
| 링크 설정 | <Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-platform-direct-attribution-links">직접 어트리뷰션 링크를 만드는 방법 알아보기</Anchor> | 마케터 |
| 리포트 설정/데이터 보기 | <Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-platform-attribution-concepts#데이터-가용성">대시보드 및 리포트의 데이터 가용성에 대해 알아보기</Anchor> | 마케터/데이터 엔지니어 |

<div id="traits-and-limitations" />

<Accordion title="특징 및 제약 사항">

| 특성 | 비고 |
| --- | --- |
| 리타겟팅 | 현재 지원되지 않음 |
| 비용 데이터 | 비용 데이터는 이메일로 파일을 업로드하는 방법으로 <Anchor target="_blank" href="/marketers/ko/docs/import-cost-data">비용 가져오기</Anchor>를 통해 전송해야 합니다. |
| 어트리뷰션 |  |

</Accordion>

> 📄 **참고 항목**
>
> * <span id="overview"></span><Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-platform-attribution-concepts">CTV, PC 및 콘솔 플랫폼 개요</Anchor>

<div data-zendesk-anchors="about-lg-ctv-attribution=lg-ctv-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%A0%95%EB%B3%B4 01H7Z17N0YAAGTDPMGZ89F7AVB=lg-ctv-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%A0%95%EB%B3%B4 integration-procedures=%EC%97%B0%EB%8F%99-%EC%A0%88%EC%B0%A8 01H7Z17N0Y8RE5PS15N2JG5NRH=%EC%97%B0%EB%8F%99-%EC%A0%88%EC%B0%A8 01H7Z17N0YCX89SYYJ1AMPM6W4=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
