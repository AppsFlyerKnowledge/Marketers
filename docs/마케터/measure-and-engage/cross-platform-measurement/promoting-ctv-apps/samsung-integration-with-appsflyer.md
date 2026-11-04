---
title: 삼성과 앱스플라이어 통합
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
  created_at: '2022-05-03T09:19:48Z'
  edited_at: '2026-10-14T10:31:00Z'
  id: 5860544738065
  locale: ko
  section: Promoting CTV apps
  section_id: 15328952633489
  url: https://support.appsflyer.com/hc/ko/articles/5860544738065
---
> **요약:** 삼성 커넥티드 TV (CTV) 앱을 앱스플라이어와 통합하여 삼성 캠페인의 어트리뷰션 및 이벤트 데이터를 수신할 수 있습니다.

<div id="about-samsung-ctv-attribution" />

## 삼성 CTV 어트리뷰션에 대하여

스트리밍용 삼성 Tizen OS는 모든 삼성 TV에서 실행됩니다.

삼성에서 스트리밍하는 CTV 앱은 API를 통해 앱스플라이어와 통합하여 앱 오픈 및 인앱 이벤트를 주도하는 소스 (오가닉 및 논오가닉) 및 캠페인에 대한 어트리뷰션 데이터 및 성과 측정치를 수신할 수 있습니다. 마케팅 담당자는 이러한 인사이트를 바탕으로 마케팅 활동을 측정하고 최적화합니다.

삼성 API 통합은 다음을 지원합니다.

* 삼성 스마트 TV.
* CTV에서 CTV로의 어트리뷰션 및 이벤트 레코딩. 사용자의 삼성 디바이스에서의 의미, 어트리뷰션 및 기록.

<div id="samsung-attribution-flow" />

### 삼성 어트리뷰션 플로우

![CTV_attribution_flow_-_Samsung__1_.png](https://files.readme.io/a1031878e8aced81da5762d06ae0163770cd73b9a7c91224ea7665aa142d2ce8-7215151128209.png)

<div id="h_01M349521V96NRS5CJKXZKMA6P" />

<div id="integration-procedures" />

## 통합 절차

다음 표에는 삼성 CTV 앱을 앱스플라이어와 통합하는 데 필요한 작업이 나열되어 있습니다.

| 작업 | 작업 | 담당자 |
| --- | --- | --- |
| 앱 설정 | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">앱스플라이어 계정 만들기</Anchor></li><li><Anchor target="_blank" href="/marketers/ko/docs/user-management">적절한 권한을 가진 계정 사용자 추가</Anchor></li><li><Anchor target="_blank" href="/marketers/ko/docs/adding-an-app-to-appsflyer">앱스플라이어에 삼성 CTV 앱 추가</Anchor></li></ul> | 마케터 |
| 앱과 API 연동(S2S 또는 SDK를 통해) | S2S 및 SDK의 두 가지 연동 방법을 S2S 및 SDK.<br /><br />S2S 메서드의 경우 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/pc-console-ctv-api-overview">앱스플라이어 API를 귀하의 앱에 연동할 때, 다음의 이벤트를 앱스플라이어에 리포트하는 명령을 사용합니다.</Anchor><ul><li>첫 오픈</li><li>인앱이벤트</li><li>세션 수</li></ul>**참고**:<ul><li>인스톨은 인앱 이벤트와 세션 전에 리포트해야 합니다.</li><li>API를 사용하여 이벤트를 보냅니다. 개발자에게 어떤 이벤트를 전송할 지 알립니다. API를 설정할 때 앱스플라이어에 전송할 이벤트를 설정하고 매핑했는지 확인합니다.</li></ul>온드 미디어 인게이지먼트를 리포트하려면 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">노출 인게이지먼트 API</Anchor>를 연동하세요.<br /><br /><Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-html5-ctv-sdk">SDK 방법에 대해서는 삼성 문서의 개발자 허브를 참조하십시오.</Anchor> | 앱 개발자 |
| 파트너 연동 | 앱스플라이어에서 삼성을 광고 네트워크 (통합 파트너) 로 추가하세요.<ol><li><Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#a-activate-partner">파트너 활성화</Anchor></li><li>[선택 사항] <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#e-install-attribution">**뷰스루 어트리뷰션**을 켭니다.</Anchor></li></ol> | 마케터 |
| 링크 설정 | <Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-platform-direct-attribution-links">다이렉트 어트리뷰션 링크 만드는 방법 알아보기</Anchor> | 마케터 |
| 리포트 설정/데이터 보기 | <Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-platform-attribution-concepts#데이터-가용성">대시보드 및 리포트의 데이터 가용성에 대해 알아보기</Anchor> | 마케터/데이터 엔지니어 |

<div id="traits-and-limitations" />

<Accordion title="특징 및 제한 사항">

| 특징 | 비고 |
| --- | --- |
| 리타겟팅 | 현재 지원되지 않음 |
| 비용 데이터 | <Anchor target="_blank" href="/marketers/ko/docs/import-cost-data">비용 데이터는 이메일로 파일을 업로드하는 방법으로</Anchor> 비용 가져오기를 통해 전송해야 합니다. |
| 지원 지역 |  |

</Accordion>

> 📄 **참고 항목**
>
> <Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-platform-attribution-concepts">CTV, PC 및 콘솔 플랫폼 개요</Anchor>

<div data-zendesk-anchors="about-samsung-ctv-attribution=%EC%82%BC%EC%84%B1-ctv-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC 01H7Z17A1QPJQH9R5MRBVTMG37=%EC%82%BC%EC%84%B1-ctv-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC samsung-attribution-flow=%EC%82%BC%EC%84%B1-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%94%8C%EB%A1%9C%EC%9A%B0 01H7Z17A1Q03CEJT848FRFHDPQ=%EC%82%BC%EC%84%B1-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%94%8C%EB%A1%9C%EC%9A%B0 integration-procedures=%ED%86%B5%ED%95%A9-%EC%A0%88%EC%B0%A8 01H7Z17A1QQN4FYJXZFS5FP2NY=%ED%86%B5%ED%95%A9-%EC%A0%88%EC%B0%A8 01H7Z17A1QVW58B2FZE7SDJHHJ=traits-and-limitations h_01HE7RG1GE2E37NN4WT1XYG9YX=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
