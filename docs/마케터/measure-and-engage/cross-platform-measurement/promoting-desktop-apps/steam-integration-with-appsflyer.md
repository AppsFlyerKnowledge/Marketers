---
title: Steam과 앱스플라이어 연동
metadata:
  keywords:
    - CTV
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2022-12-08T10:02:09Z'
  edited_at: '2026-10-14T10:30:20Z'
  id: 11241130508433
  locale: ko
  section: Promoting Desktop apps
  section_id: 15329004312593
  url: https://support.appsflyer.com/hc/ko/articles/11241130508433
---
> **요약:** Steam 게임/앱을 앱스플라이어와 연동하여 Steam 캠페인에 대한 어트리뷰션 및 이벤트 데이터를 측정하세요. Steam 연동은 유저의 Steam 디바이스에 있는 Steam 앱에 대한 어트리뷰션 및 인앱 이벤트 기록을 지원합니다. Steam 연동은 유저의 Steam 디바이스에 있는 Steam 앱에 대한 어트리뷰션 및 인앱 이벤트 기록을 지원합니다.

<div id="about-steam-attribution" />

## Steam 어트리뷰션

Steam은 Windows 및 Mac 디바이스, Steam Deck 및 기타 Steam OS 디바이스에서 실행됩니다.

Steam에서 실행되는 앱은 S2S API 또는 SDK를 통해 앱스플라이어와 연동되어, 어떤 소스 및 캠페인이 앱 오픈 및 인앱 이벤트를 유도하는지에 대한 어트리뷰션 데이터 및 성과를 측정할 수 있습니다. 마케팅 담당자는 이러한 인사이트를 바탕으로 마케팅 활동을 측정하고 최적화합니다. 마케팅 담당자는 이러한 인사이트를 바탕으로 마케팅 활동을 측정하고 최적화합니다.

<div id="example-attribution-flow" />

### 어트리뷰션 흐름의 예

다음 어트리뷰션 흐름을 보면, 광고 인게이지먼트에서 어트리뷰션에 이르기까지 유저 여정에서 가장 중요한 단계가 표시돼 있습니다. 여기에는 앱스플라이어가 권장하는 크로스 플랫폼 랜딩 페이지가 포함됩니다. **참고**: 크로스 플랫폼 랜딩 페이지 사용이 권장되지만 다이렉트 어트리뷰션 링크를 사용할 수도 있습니다

<Image align="center" alt="Steam_user_journey.jpg" src="https://files.readme.io/4979821043af1ed3e662b55c84df10a17a863e79084d050c478fa31767ed8eaa-51473918246929.jpg" />

1. 마케팅 터치포인트: 고객은 온라인 또는 오프라인 마케팅 터치포인트를 통해 브랜드와 상호 작용합니다. 이러한 상호작용에는 이메일 및 뉴스레터, 소셜 미디어, 모바일 웹 등이 포함될 수 있습니다.
2. 게임 랜딩 페이지: 게임 랜딩 페이지는 고객을 Steam 게임 페이지로 안내합니다. 이 단계에서 UTM 및 기타 URL 파라미터를 수집하는 데 중요한 역할을 하며, 고객의 클릭/설치를 오리지널 미디어 소스 또는 온드 미디어 소스로 어트리뷰트합니다.   
   또한, 랜딩 페이지가 유용한 이유는 게임이 지원하는 다양한 플랫폼에 대한 링크를 제공하기 때문입니다. 예를 들어 랜딩 페이지에 Xbox, Microsoft Store 및 Steam 페이지로 안내하는 링크를 포함시킬 수 있습니다.  
   <Image align="center" alt="awesome_game.png" src="https://files.readme.io/37cabff10a2e0a721b4d2901e7df47f53a7dedff25bdac80b97003b60eaef430-51473918248465.png" />
3. <span id="marketing-touchpoint"></span>Steam 앱 페이지: 고객이 다운로드할 수 있는 Steam 앱을 호스팅하는 Steam 스토어 페이지입니다.
4. 게임 설치: 유저가 게임을 설치하면 어트리뷰션이 트리거되고 인앱 이벤트 및 세션이 기록됩니다.

<div id="integration-procedures" />

## 연동 절차

다음 표에는 Steam 앱을 앱스플라이어와 연동하는 데 필요한 작업이 나열되어 있습니다.

<Table>
  <thead>
    <tr>
      <th>
        작업
      </th>
      <th>
        액션
      </th>
      <th>
        담당자
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        앱 설정
      </td>
      <td>
        * <Anchor target="_blank" href="https://www.appsflyer.com/get-started/">앱스플라이어 계정 만들기</Anchor>
        * <Anchor target="_blank" href="/marketers/ko/docs/user-management">적절한 권한이 있는 계정 사용자 추가</Anchor>
        * <Anchor target="_blank" href="/marketers/ko/docs/adding-an-app-to-appsflyer">앱스플라이어에 Steam 앱 추가</Anchor>
      </td>
      <td>
        마케터
      </td>
    </tr>
    <tr>
      <td>
        S2S 또는 SDK를 통해) 앱과 앱스플라이어 연동
      </td>
      <td>
        2가지 연동 방법: S2S 및 SDK.

        S2S 메서드의 경우 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/pc-console-ctv-api-overview">앱스플라이어 API를 귀하의 앱에 연동할 때,</Anchor> 다음의 이벤트를 앱스플라이어에 리포트하는 명령을 사용합니다.

        * 첫 앱 실행
        * 인앱 이벤트
        * 세션

        **참고**:

        * 앱 내 이벤트 및 세션 전에 첫 앱 실행을 보고해야 합니다.
        * `platform` 파라미터의 경우, `steam` 유형을 선택합니다.
        * `device_ids` 파라미터의 경우, `custom` 유형을 선택합니다.
        * API를 사용하여 이벤트를 전송합니다. 개발자에게 어떤 이벤트를 전송할 지 알립니다. API를 설정할 때 앱스플라이어에 전송할 이벤트를 설정하고 매핑했는지 확인합니다.
        * 온드 미디어 인게이지먼트를 리포트하려면 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">노출 인게이지먼트 API</Anchor>를 연동하세요.

        SDK 메서드의 경우 세 가지 버전이 있습니다. native <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/steam-vanilla">C++</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unreal-steam">Unreal</Anchor>그리고 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unity-steam">Unity</Anchor>.

        **참고**:

        기존 유저 베이스가 존재하여 첫 번째 세션을 설치가 아닌 세션으로 기록하고자 할 경우, 개발자는 `skipFirst=true` 메서드를 사용할 수 있습니다.
      </td>
      <td>
        앱 개발자
      </td>
    </tr>
    <tr>
      <td>
        크로스 플랫폼 랜딩 페이지 설정
      </td>
      <td>
        **권장 사항**: 앱스플라이어 스마트 스크립트를 실행하는 크로스 플랫폼 랜딩 페이지를 통해 웹투앱 어트리뷰션을 수행할 수 있습니다. 캠페인을 통해 Epic 및 Native PC와 같은 다른 플랫폼에서도 사용할 수 있는 앱을 홍보하는 경우에 특히 권장됩니다.

        <Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">크로스 플랫폼 랜딩 페이지에 대해 알아보기</Anchor>

        <Anchor target="_blank" href="/marketers/ko/docs/cross-platform-landing-pages-with-smart-script">크로스 플랫폼 랜딩 페이지 설정 방법 알아보기</Anchor>

        **참고**:

        Steam의 경우 다음 파라미터가 필요합니다.

        * **platform**: steam
        * **steam\_app\_id**: 앱 페이지의 ID입니다.  

          URL 표시줄에서 복사하거나 <Anchor target="_blank" href="https://steamdb.info/">https://steamdb.info/</Anchor>에서 귀하의 게임을 검색하면 고유 아이디를 찾을 수 있습니다. 예를 들어,

          ```http
          https://store.steampowered.com/app/12345678/
          ```

          위 URL에서는 **12345678**이 고유한 앱 ID를 나타냅니다.
        * **media\_source**

        다음 파라미터는 필수는 아니지만 권장 사항입니다.

        * **campaign**
        * **ad**
        * **ad\_set**
        * **storefront\_redirect\_url**: storefront\_redirect\_url: 귀하의 앱을 다운로드 받을 수 있는 Steam 스토어 페이지의 전체 URL(**steam\_app\_id** 포함) 예시: `https://store.steampowered.com/app/12345678/`
      </td>
      <td>
        마케터(개발자 지원이 필요할 수 있음)
      </td>
    </tr>
    <tr>
      <td>
        링크 설정
      </td>
      <td>
        크로스 플랫폼 랜딩 페이지를 사용하지 않는 경우, 다이렉트 어트리뷰션 링크를 생성해 광고 뒤에 배치할 수 있습니다.

        <Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-platform-direct-attribution-links">다이렉트 어트리뷰션 링크 만드는 방법 알아보기</Anchor>
      </td>
      <td>
        마케터
      </td>
    </tr>
    <tr>
      <td>
        리포트 설정/데이터 보기
      </td>
      <td>
        <Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-platform-attribution-concepts#데이터-가용성">대시보드 및 리포트의 데이터 가용성에 대해 알아보기</Anchor>
      </td>
      <td>
        마케터/데이터 엔지니어
      </td>
    </tr>
  </tbody>
</Table>


<div id="traits-and-limitations" />

<div id="removing-appsflyer-data-when-uninstalling-the-app" />

## 특징 및 제약 사항

| 특성 | 비고 |
| --- | --- |
| 리타겟팅 | 현재 지원되지 않음 |
| 비용 데이터 | 비용 데이터는 <Anchor target="_blank" href="/marketers/ko/docs/import-cost-data">Cost Import</Anchor>기능을 통해 이메일을 보내는 방법으로 전송해야 합니다. |

<div id="see-also" />

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-platform-attribution-concepts">CTV, PC, 콘솔 플랫폼 어트리뷰션</Anchor>

<div data-zendesk-anchors="about-steam-attribution=steam-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 01H7Z1DJRW1KPJQ4CZ6T85ASRK=steam-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 flow=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%9D%90%EB%A6%84%EC%9D%98-%EC%98%88 01H7Z1DJRWHB8TQC15WW4FVSHG=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%9D%90%EB%A6%84%EC%9D%98-%EC%98%88 integration-procedures=%EC%97%B0%EB%8F%99-%EC%A0%88%EC%B0%A8 01H7Z1DJRWX54DN2SNS21GPGXB=%EC%97%B0%EB%8F%99-%EC%A0%88%EC%B0%A8 removing-appsflyer-data-when-uninstalling-the-app=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD traits-and-limitations=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD h_01J3349MAA4J231B6FJ74V3PTB=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD h_01HDEHMH0HF201TH4XDW691STH=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD h_01HDP1K6FDDEED5P2WNESST7GE=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
