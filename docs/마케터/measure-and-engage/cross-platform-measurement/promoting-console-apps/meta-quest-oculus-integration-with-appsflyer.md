---
title: 메타 퀘스트 (Oculus)와 앱스플라이어의 통합
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
  created_at: '2022-12-08T10:10:00Z'
  edited_at: '2026-10-14T10:31:54Z'
  id: 11241398279569
  locale: ko
  section: Promoting Console apps
  section_id: 15329052471057
  url: https://support.appsflyer.com/hc/ko/articles/11241398279569
---
> **요약:** 메타 퀘스트 (Oculus) 앱을 앱스플라이어와 통합하여 메타 퀘스트(Oculus)에서 캠페인에 대한 어트리뷰션 및 이벤트 데이터를 수신할 수 있습니다.

<div id="about-meta-quest-oculus-attribution" />

## 메타 퀘스트(Oculus) 어트리뷰션 정보

게임용 메타 퀘스트 (Oculus) OS는 모든 메타 퀘스트(Oculus) 기기에서 실행됩니다.

메타 퀘스트에서 실행되는 앱은 S2S API 또는 SDK를 통해 앱스플라이어와 통합하여 어떤 소스 및 캠페인이 앱 오픈 및 인앱 이벤트를 유도하는지에 대한 어트리뷰션 데이터 및 성과 측정을 받을 수 있습니다. 마케팅 담당자는 이러한 인사이트를 바탕으로 마케팅 활동을 측정하고 최적화합니다.

<div id="integration-procedures" />

## 통합 절차

다음 표에는 메타 퀘스트(Oculus) 앱을 앱스플라이어와 통합하는 데 필요한 작업이 나열되어 있습니다. 

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
        * <Anchor target="_blank" href="/marketers/ko/docs/adding-an-app-to-appsflyer">앱스플라이어에 메타 퀘스트(Oculus) 앱 추가하기</Anchor>
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
        2가지 연동 방법: S2S 및 SDK.

        S2S 방법의 경우, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">앱스플라이어 API를 앱에 통합</Anchor>하고 다음 이벤트를 앱스플라이어에 보고하는 명령을 앱에 통합합니다.

        * 첫 번째 열기
        * 인앱 이벤트
        * 세션

        **참고**:

        * 앱 내 이벤트 및 세션 전에 첫 번째 앱 실행을 보고해야 합니다.
        * `device_ids` 파라미터의 경우, `custom` 유형을 선택합니다.
          * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_first-open-app-platform-app-id">첫 앱 실행 시 생성된 `custom` ID는</Anchor> <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_inapp-app-platform-app-id">인앱 이벤트</Anchor> 및 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_session-app-platform-app-id">세션</Anchor> ID와 일치해야 합니다.
          * API를 사용하여 이벤트를 전송합니다. 개발자에게 어떤 이벤트를 보낼지 알려주세요. API를 설정할 때, 앱스플라이어로 전송할 이벤트를 설정하고 매핑했는지 확인합니다.
          * 온드 미디어 참여를 보고하려면 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">노출 인게이지먼트 API를 통합</Anchor>하세요.

        SDK 방식의 두 가지 버전: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/meta-quest2-unity">Unity</Anchor> 및 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/meta-quest2-unreal">Unreal</Anchor>.

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

        메타 퀘스트의 경우 다음 매개변수가 필요합니다.

        * **플랫폼**: 퀘스트
        * **QUEST\_APP\_ID**: 퀘스트 스토어 앱 ID입니다.  
          퀘스트 2의 경우, 이 번호는 스토어 URL에 있는 번호입니다.

          ```http
          https://www.oculus.com/experiences/quest/XXXXXXXXXXXXXXXX/
          ```

          여기서 **XXXXXXXXXXXXXX는** 고유 앱 ID입니다.
        * **media\_source**

        다음 파라미터는 필수는 아니지만 권장 사항입니다.

        * **campaign**
        * **ad**
        * **ad\_set**
        * **storefront\_redirect\_url**:  **QUEST\_APP\_ID를** 포함한 앱의 Oculus 스토어 첫 화면 전체 URL입니다. 예: `https://www.oculus.com/experiences/quest/XXXXXXXXXXXXXXXX/`
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

<div data-zendesk-anchors="about-meta-quest-attribution=%EB%A9%94%ED%83%80-%ED%80%98%EC%8A%A4%ED%8A%B8oculus-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%A0%95%EB%B3%B4 01H7Z1MK9JHA4C5CB7YME4AJMA=%EB%A9%94%ED%83%80-%ED%80%98%EC%8A%A4%ED%8A%B8oculus-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%A0%95%EB%B3%B4 integration-procedures=%ED%86%B5%ED%95%A9-%EC%A0%88%EC%B0%A8 01H7Z1MK9JNRKAY9VNH5RTF03F=%ED%86%B5%ED%95%A9-%EC%A0%88%EC%B0%A8 01H7Z1MK9KXFY4XVPCDSJPQ26N=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
