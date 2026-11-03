---
title: 앱스플라이어와 Vizio 통합
metadata:
  keywords:
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
  created_at: '2022-03-27T15:48:04Z'
  edited_at: '2026-10-14T10:32:27Z'
  id: 5045234293777
  locale: ko
  section: Promoting CTV apps
  section_id: 15328952633489
  url: https://support.appsflyer.com/hc/ko/articles/5045234293777
---
> **요약:** 비지오 커넥티드 TV(CTV) 앱(채널)을 앱스플라이어와 통합하여 비지오에서 캠페인에 대한 어트리뷰션 및 이벤트 데이터를 수신할 수 있습니다.

## Vizio CTV 어트리뷰션 정보

스트리밍용 Vizio SmartCast OS는 모든 Vizio TV에서 실행됩니다.

비지오에서 스트리밍되는 CTV 앱은 API를 통해 앱스플라이어와 통합하여 어떤 소스(비오가닉 또는 오가닉)와 유료 캠페인이 앱 오픈 및 인앱 이벤트를 유도하는지에 대한 어트리뷰션 데이터 및 성과 측정을 받을 수 있습니다. 마케팅 담당자는 이러한 인사이트를 바탕으로 마케팅 활동을 측정하고 최적화합니다.

Vizio API 통합 다음을 지원합니다.

* Vizio 스마트 TV.
* CTV-to-TV 어트리뷰션 및 이벤트 녹화. 사용자의 Vizio 기기에서 발생하는 첫 번째 앱 열기 (설치에 해당) 및 이벤트의 의미, 어트리뷰션 및 기록.

### Vizio 어트리뷰션 흐름

![CTV_attribution_flow_-_Vizio__1_.png](https://files.readme.io/f4ab4b6c9e045fe00b537814fa9f10746b525a5512e5805e62eb0c2e4c9a8615-6318406872337.png)

## 통합 절차

다음 표에는 Vizio CTV 앱을 앱스플라이어와 통합하는 데 필요한 작업이 나열되어 있습니다.

| 작업 | 액션 | 담당자 |
| --- | --- | --- |
| 앱 설정 | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">앱스플라이어 계정 만들기</Anchor></li><li><Anchor target="_blank" href="/marketers/ko/docs/user-management">적절한 권한이 있는 계정 사용자 추가</Anchor></li><li><Anchor target="_blank" href="/marketers/ko/docs/adding-an-app-to-appsflyer">앱스플라이어에 비지오 CTV 앱 추가하기</Anchor></li></ul> | 마케터 |
| 앱과 API 통합(S2S를 통한) | 다음 이벤트를 앱스플라이어에 보고하는 명령을 사용하여 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">앱스플라이어 CTV API</Anchor>를 CTV 앱에 통합하세요.<ul><li>첫 번째 열기</li><li>인앱 이벤트</li><li>세션</li></ul>**참고**:<ul><li>인앱 이벤트 및 세션 전에 인스톨을 보고해야 합니다.</li><li>API를 사용하여 이벤트를 보냅니다. 개발자에게 어떤 이벤트를 보낼지 알려주세요. API를 설정할 때, 앱스플라이어로 전송할 이벤트를 설정하고 매핑했는지 확인합니다.</li></ul>온드 미디어 참여를 보고하려면 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">노출 인게이지먼트 API</Anchor>를 통합하세요. | 앱 개발자 |
| 파트너 연동 | 앱스플라이어에서 Vizio를 광고 네트워크(통합 파트너)로 추가하세요.<ol><li><Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#a-activate-partner">파트너 활성화</Anchor></li><li>[선택 사항] **<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#e-install-attribution">뷰스루 어트리뷰션</Anchor>을 켭니다.**</li></ol> | 마케터 |
| 링크 설정 | <Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-platform-direct-attribution-links">다이렉트 어트리뷰션 링크 만드는 방법 알아보기</Anchor> | 마케터 |
| 리포트 설정/데이터 보기 | <Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-platform-attribution-concepts#데이터-가용성">대시보드 및 리포트의 데이터 가용성에 대해 알아보기</Anchor> | 마케터/데이터 엔지니어 |

<div id="traits-and-limitations" />

<Accordion title="특징 및 제한 사항">

| 특성 | 비고 |
| --- | --- |
| 리타겟팅 | 현재 지원되지 않음 |
| 뷰-쓰루 어트리뷰션 | 기본값은 24시간입니다. |
| 비용 데이터 | 비용 데이터는 이메일 방식으로 파일 업로드를 사용하여 <Anchor target="_blank" href="/marketers/ko/docs/import-cost-data">비용 가져오기</Anchor>를 통해 전송해야 합니다. |

</Accordion>

> 📄 **참고 항목**
>
> * <span id="overview"></span><Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-platform-attribution-concepts">CTV, PC 및 콘솔 플랫폼 개요</Anchor>

<div data-zendesk-anchors="about-vizio-ctv-attribution=vizio-ctv-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%A0%95%EB%B3%B4 01H7Z16QWWCPR309JDKV7H0469=vizio-ctv-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%A0%95%EB%B3%B4 vizio-attribution-flow=vizio-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%9D%90%EB%A6%84 01H7Z16QWW3GJEAGV0F3JHTKE1=vizio-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%9D%90%EB%A6%84 integration-procedures=%ED%86%B5%ED%95%A9-%EC%A0%88%EC%B0%A8 01H7Z16QWW1WX5F947WPH9HBQX=%ED%86%B5%ED%95%A9-%EC%A0%88%EC%B0%A8 01H7Z16QWX24K8QCEJVBX1SQEA=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
