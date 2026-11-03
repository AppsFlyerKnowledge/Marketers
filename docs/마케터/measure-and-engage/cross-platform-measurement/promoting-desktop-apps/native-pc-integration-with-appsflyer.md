---
title: 앱스플라이어와 Native PC 연동
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
  created_at: '2023-06-20T05:52:13Z'
  edited_at: '2026-10-14T10:36:23Z'
  id: 16308237781649
  locale: ko
  section: Promoting Desktop apps
  section_id: 15329004312593
  url: https://support.appsflyer.com/hc/ko/articles/16308237781649
---
> **요약:** PC 게임이나 앱을 앱스플라이어와 연동하여 PC 캠페인에 대한 어트리뷰션 및 이벤트 데이터를 받아보세요. Native PC 연동은 PC 앱에 대한 어트리뷰션 및 인앱 이벤트 기록(즉, 사용자 PC에서의 어트리뷰션 및 기록)을 지원합니다.

## Native PC 어트리뷰션 정보

Native PC는 .EXE 또는 .MSI 파일 확장자를 설치하여 Windows 기기에서 실행됩니다.

이는 Microsoft App Store, Windows Phone, UWP에서 설치하여 작동하는 <Anchor target="_blank" href="/marketers/ko/docs/windows-sdk-integration-for-developers">AppsFlyer Windows SDK 2.4.1</Anchor>과는 다릅니다.

PC에서 실행되는 앱은 S2S API 또는 SDK를 통해 앱스플라이어와 연동되어, 어떤 소스 및 캠페인이 앱 오픈 및 인앱 이벤트를 유도하는지에 대한 어트리뷰션 데이터 및 성과를 측정할 수 있습니다. 마케팅 담당자는 이러한 인사이트를 바탕으로 마케팅 활동을 측정하고 최적화합니다. 마케팅 담당자는 이러한 인사이트를 바탕으로 마케팅 활동을 측정하고 최적화합니다.

### 어트리뷰션 흐름의 예

다음 어트리뷰션 흐름을 보면, 광고 인게이지먼트에서 어트리뷰션에 이르기까지 유저 여정에서 가장 중요한 단계가 표시돼 있습니다. 여기에는 앱스플라이어가 권장하는 크로스 플랫폼 랜딩 페이지가 포함됩니다. **주의**: 크로스 플랫폼 랜딩 페이지 사용이 권장되지만 다이렉트 어트리뷰션 링크를 사용할 수도 있습니다.

![User_windows.jpg](https://files.readme.io/33c9138ef2064832a0bd5d08d52c84bea3e70efb674af362a8ef0d3e5d505db1-small-16332549715217.jpg)

1. <span id="marketing-touchpoint"></span>마케팅 터치포인트: 고객은 온라인 또는 오프라인 마케팅 터치포인트를 통해 브랜드와 상호 작용합니다. 이러한 상호작용에는 이메일 및 뉴스레터, 소셜 미디어, 모바일 웹 등이 포함될 수 있습니다.
2. 게임 랜딩 페이지: 게임 랜딩 페이지는 고객을 앱 다운로드 페이지로 안내합니다. 이 단계에서 UTM 및 기타 URL 파라미터를 수집하는 데 중요한 역할을 하며, 고객의 클릭/설치를 오리지널 미디어 소스 또는 온드 미디어 소스로 어트리뷰트합니다.  
   또한, 랜딩 페이지가 유용한 이유는 게임이 지원하는 다양한 플랫폼에 대한 링크를 제공하기 때문입니다. 예를 들어 랜딩 페이지에 Xbox, Microsoft Store 및 Steam 페이지로 안내하는 링크를 포함시킬 수도 있습니다.
3. 앱 페이지: 고객이 다운로드할 수 있도록 앱을 호스팅하는 Native PC 앱 페이지의 URL입니다.
4. 게임 설치: 유저가 게임을 설치하면 어트리뷰션이 트리거되고 인앱 이벤트 및 세션이 기록됩니다.

## 연동 절차

다음 표에는 PC 앱을 앱스플라이어와 연동하는 데 필요한 작업이 나열되어 있습니다.

**참고:** 데이터 락커에서 팀원 추가와 리포트 설정은 필수 사항이 아닙니다.

| 작업 | 액션 | 담당자 |
| --- | --- | --- |
| 앱 설정 | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">앱스플라이어 계정 만들기</Anchor></li><li><Anchor target="_blank" href="/marketers/ko/docs/user-management">적절한 권한이 있는 계정 사용자 추가</Anchor></li><li><Anchor target="_blank" href="/marketers/ko/docs/adding-an-app-to-appsflyer">앱스플라이어에서 PC 앱 추가</Anchor></li></ul> | 마케터 |
| S2S 또는 SDK를 통해) 앱과 앱스플라이어 연동 | 2가지 연동 방법: S2S 및 SDK.<br /><br />S2S 메서드의 경우 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">앱스플라이어 API를 귀하의 앱에 연동할 때,</Anchor> 다음의 이벤트를 앱스플라이어에 리포트하는 명령을 사용합니다.<ul><li>첫 앱 실행</li><li>인앱 이벤트</li><li>세션</li></ul>**참고**:<ul><li>앱 내 이벤트 및 세션 전에 첫 번째 앱 실행을 보고해야 합니다.</li><li>`device_ids` 파라미터의 경우, `custom` 유형을 선택합니다.<ul><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_first-open-app-platform-app-id">첫 앱 실행 시 생성된 `custom` ID는</Anchor> <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_inapp-app-platform-app-id">인앱 이벤트</Anchor> 및 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_session-app-platform-app-id">세션</Anchor> ID와 일치해야 합니다.</li></ul></li><li>API를 사용하여 이벤트를 전송합니다. 개발자에게 어떤 이벤트를 전송할 지 알립니다. API를 설정할 때 앱스플라이어에 전송할 이벤트를 설정하고 매핑했는지 확인합니다.</li><li>온드 미디어 인게이지먼트를 리포트하려면 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">노출 인게이지먼트 API</Anchor>를 연동하세요.</li></ul>SDK 메서드의 경우 세 가지 버전이 있습니다. native <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/nativepc-vanilla">C++</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unreal-nativepc">Unreal</Anchor>그리고 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unity-nativepc">Unity</Anchor>.<br /><br />**참고**:<br /><br />기존 유저 베이스가 존재하여 첫 번째 세션을 설치가 아닌 세션으로 기록하고자 할 경우, 개발자는 `skipFirst=true` 메서드를 사용할 수 있습니다. | 앱 개발자 |
| 크로스 플랫폼 랜딩 페이지 설정 | **권장 사항**: 앱스플라이어 스마트 스크립트를 실행하는 크로스 플랫폼 랜딩 페이지를 통해 웹투앱 어트리뷰션을 수행할 수 있습니다. 캠페인을 통해 Epic 및 Steam과 같은 다른 플랫폼에서도 사용할 수 있는 앱을 홍보하는 경우에 특히 권장됩니다.<br /><br /><Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">크로스 플랫폼 랜딩 페이지에 대해 알아보기</Anchor><br /><br /><Anchor target="_blank" href="/marketers/ko/docs/cross-platform-landing-pages-with-smart-script">크로스 플랫폼 랜딩 페이지 설정 방법 알아보기</Anchor><br /><br />Native PC의 경우 다음 파라미터가 필요합니다.<ul><li>**앱 이름**<br />앱의 이름</li><li>**app\_id**<br />앱의 ID.</li></ul>앱스플라이어에서 사용할 앱 ID가 필요합니다. Native PC 앱에는 특정 앱 ID 규칙이 없으므로, 개발자가 앱에 대해 원하는 앱 ID를 선택하여 생성할 수 있습니다. **권장 사항**: 자신에게는 의미가 있지만 앱에서 사용할 가능성이 없는 ID를 선택하세요. `app-name-is-the-best`를 예로 들 수 있습니다.<ul><li>**media\_source**</li></ul>다음 파라미터는 필수는 아니지만 권장 사항입니다.<ul><li>**campaign**</li><li>**ad**</li><li>**ad\_set**</li></ul> | 마케터(개발자 지원이 필요할 수 있음) |
| 링크 설정 | 크로스 플랫폼 랜딩 페이지를 사용하지 않는 경우, 다이렉트 어트리뷰션 링크를 생성해 광고 뒤에 배치할 수 있습니다.<br /><br /><Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-platform-direct-attribution-links">다이렉트 어트리뷰션 링크 만드는 방법 알아보기</Anchor> | 마케터 |
| 리포트 설정/데이터 보기 | <Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-platform-attribution-concepts#데이터-가용성">대시보드 및 리포트의 데이터 가용성에 대해 알아보기</Anchor> | 마케터/데이터 엔지니어 |


## 특징 및 제약 사항

| 특성 | 비고 |
| --- | --- |
| 리타겟팅 | 현재 지원되지 않음 |
| 비용 데이터 | 비용 데이터는 <Anchor target="_blank" href="/marketers/ko/docs/import-cost-data">Cost Import</Anchor>기능을 통해 이메일을 보내는 방법으로 전송해야 합니다. |

> 📄 **참고 항목**
>
> * <span id="overview"></span><Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-platform-attribution-concepts">CTV, PC 및 콘솔 플랫폼 개요</Anchor>

<div data-zendesk-anchors="about-steam-attribution=native-pc-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%A0%95%EB%B3%B4 01H7Z19FJ5J1CB4ESE55Z32C1C=native-pc-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%A0%95%EB%B3%B4 flow=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%9D%90%EB%A6%84%EC%9D%98-%EC%98%88 01H7Z19FJ5R869054GDRKHTBJ8=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%9D%90%EB%A6%84%EC%9D%98-%EC%98%88 01H7Z19FJ54WZ7XV91Y36EKYQ6=marketing-touchpoint integration-procedures=%EC%97%B0%EB%8F%99-%EC%A0%88%EC%B0%A8 01H7Z19FJ5KKPJ88KAQM49FNVA=%EC%97%B0%EB%8F%99-%EC%A0%88%EC%B0%A8 removing-appsflyer-data-when-uninstalling-the-app=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD traits-and-limitations=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD h_01J3349MAA4J231B6FJ74V3PTB=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD h_01HF9W8YG149TMQE1F57BG0ZS7=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD h_01HE0T79YSNWGB3W4S7WEBW1B5=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
