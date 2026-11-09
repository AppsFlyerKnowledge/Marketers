---
title: Roku와 앱스플라이어 연동
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
  created_at: '2023-04-03T07:18:07Z'
  edited_at: '2026-10-14T10:32:40Z'
  id: 14241298075921
  locale: ko
  section: Promoting Desktop apps
  section_id: 15329004312593
  url: https://support.appsflyer.com/hc/ko/articles/14241298075921
---
> **요약:  Native PC 연동은 PC 앱에 대한 어트리뷰션 및 인앱 이벤트 기록(즉, 사용자 PC에서의 어트리뷰션 및 기록)을 지원합니다.**


<span id="about-epic-game-attribution"></span><span id="about-steam-attribution"></span>마케팅 담당자는 이러한 인사이트를 바탕으로 마케팅 활동을 측정하고 최적화합니다.

<div id="example-attribution-flow" />

### 어트리뷰션 흐름의 예

다음 어트리뷰션 흐름을 보면, 광고 인게이지먼트에서 어트리뷰션에 이르기까지 유저 여정에서 가장 중요한 단계가 표시돼 있습니다. 여기에는 앱스플라이어가 권장하는 크로스 플랫폼 랜딩 페이지가 포함됩니다. 주의: 크로스 플랫폼 랜딩 페이지 사용이 권장되지만 다이렉트 어트리뷰션 링크를 사용할 수도 있습니다.

<Image align="center" alt="Epic_journey.jpg" src="https://files.readme.io/c5807442cff142ceb4aa3c4d55628e75b37627a011ca531fa390e46ccc3e23b8-small-14241275857553.jpg" />

1. 마케팅 터치포인트: 고객은 온라인 또는 오프라인 마케팅 터치포인트를 통해 브랜드와 상호 작용합니다. 이러한 상호작용에는 이메일 및 뉴스레터, 소셜 미디어, 모바일 웹 등이 포함될 수 있습니다.
2. 게임 랜딩 페이지: 게임 랜딩 페이지는 고객을 Steam 게임 페이지로 안내합니다. 이 단계에서 UTM 및 기타 URL 파라미터를 수집하는 데 중요한 역할을 하며, 고객의 클릭/설치를 오리지널 미디어 소스 또는 온드 미디어 소스로 어트리뷰트합니다.  
   또한, 랜딩 페이지가 유용한 이유는 게임이 지원하는 다양한 플랫폼에 대한 링크를 제공하기 때문입니다. 예를 들어 랜딩 페이지에 Xbox, Microsoft Store 및 Steam 페이지로 안내하는 링크를 포함시킬 수도 있습니다.
4. 게임 설치: 유저가 게임을 설치하면 어트리뷰션이 트리거되고 인앱 이벤트 및 세션이 기록됩니다.

<div id="integration-procedures" />

## 연동 절차

다음 표에는 PC 앱을 앱스플라이어와 연동하는 데 필요한 작업이 나열되어 있습니다.

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
      </td>
      <td>
        마케터
      </td>
    </tr>
    <tr>
      <td>

      </td>
      <td>
        2가지 연동 방법:

        앱스플라이어에 다음 이벤트를 보고하는 명령으로 앱에 <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-epic-sample">앱스플라이어 API를 통합하세요.</Anchor>

        * 첫 앱 실행
        * 인앱 이벤트
        * 세션

        **참고**:

        * 앱 내 이벤트 및 세션 전에 첫 앱 실행을 보고해야 합니다.
        * `device_ids` 파라미터의 경우, `custom` 유형을 선택합니다.
        * API를 사용하여 이벤트를 전송합니다. 개발자에게 어떤 이벤트를 전송할 지 알립니다.
        * 온드 미디어 인게이지먼트를 리포트하려면 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">노출 인게이지먼트 API</Anchor>를 연동하세요.

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
        **권장 사항**: 앱스플라이어 스마트 스크립트를 실행하는 크로스 플랫폼 랜딩 페이지를 통해 웹투앱 어트리뷰션을 수행할 수 있습니다. 캠페인을 통해 Epic 및 Steam과 같은 다른 플랫폼에서도 사용할 수 있는 앱을 홍보하는 경우에 특히 권장됩니다.

        <Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">크로스 플랫폼 랜딩 페이지에 대해 알아보기</Anchor>

        <Anchor target="_blank" href="/marketers/ko/docs/cross-platform-landing-pages-with-smart-script">크로스 플랫폼 랜딩 페이지 설정 방법 알아보기</Anchor>

        **참고**:

        Steam의 경우 다음 파라미터가 필요합니다.

        * **플랫폼**  
          epic
        * **app\_id**  

          예를 들어,

          ```http
          https://store.epicgames.com/en-us/p/YOUR-GAME-ID
          ```
        * **media\_source**

        다음 파라미터는 필수는 아니지만 권장 사항입니다.

        * **campaign**
        * **ad**
        * **ad\_set**
        * **storefront\_redirect\_url**  

          예를 들어, `https://store.epicgames.com/en-us/p/12345678/`
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
> * <Anchor target="_blank" href="/marketers/ko/docs/ctv-pc-and-console-platform-attribution-concepts">CTV, PC 및 콘솔 플랫폼 개요</Anchor>

<div data-zendesk-anchors="01H7Z1F3SE03BXJD0WAJV8RE7Q=about-steam-attribution flow=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%9D%90%EB%A6%84%EC%9D%98-%EC%98%88 01H7Z1F3SETVXQKRQ71YAJACY3=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%9D%90%EB%A6%84%EC%9D%98-%EC%98%88 integration-procedures=%EC%97%B0%EB%8F%99-%EC%A0%88%EC%B0%A8 01H7Z1F3SF4J2WJ2Y6QG3VGGVK=%EC%97%B0%EB%8F%99-%EC%A0%88%EC%B0%A8 removing-appsflyer-data-when-uninstalling-the-app=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD traits-and-limitations=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD h_01J3349MAA4J231B6FJ74V3PTB=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD h_01HF9WA5FJ6P4C357ZE231GMR0=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD h_01HE7T4JX3RX3SZW2VPW5ZZY7E=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
