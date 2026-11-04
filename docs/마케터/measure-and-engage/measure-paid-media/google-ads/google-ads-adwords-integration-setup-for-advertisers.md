---
title: Google Ads (AdWords)—광고주를 위한 연동 설정
metadata:
  keywords:
    - Integration
    - Google AdWords
    - Configuration
    - google
    - migration
    - Advertisers
    - google ads configuration
    - ads
    - google ads
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2017-05-17T19:16:15Z'
  edited_at: '2026-10-14T10:37:38Z'
  id: 115002504686
  locale: ko
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/ko/articles/115002504686
---
> **한눈에 보기:** Google Ads 계정을 앱스플라이어와 연동하여 모든 캠페인의 어트리뷰션 데이터를 확인할 수 있습니다.

Google Ads 캠페인을 통해 발생하는 설치와 인앱 이벤트를 측정하고 어트리뷰션하기 위해, 앱스플라이어에서 Google Ads 연동을 설정하세요. 앱스플라이어에서 이 연동은 `googleadwords_int`이며 어트리뷰션 결과는 `googleadwords_int` 미디어 소스 아래에 보고됩니다.

<div id="google-ads-attribution-flow-with-advanced-data-sharing" />

## 고급 데이터 공유를 활용한 Google Ads 어트리뷰션 흐름

[![Google ads attribution flow.png](https://files.readme.io/1c49e06e48658a8cb60ae6a9e9a83c0fad751766f3d4ce9c6afdd041fb5e8579-small-38644882427537.png)](https://files.readme.io/1c49e06e48658a8cb60ae6a9e9a83c0fad751766f3d4ce9c6afdd041fb5e8579-small-38644882427537.png)

1. 앱스플라이어는 평소와 같이 설치 이벤트를 Google로 전송합니다. **고급 데이터 공유** 기능이 켜져 있으면, 디바이스 ID 포함 여부와 관계없이 설치 데이터가 전송됩니다. 해당 기능이 꺼져 있으면, **디바이스 ID가 있는 경우에만** 설치 데이터가 전송됩니다.
2. Google은 디바이스 ID가 있는 경우 이를 매칭하는 확정적 방식이나, 디바이스 ID가 없는 경우 확률론적 모델링을 활용한 비확정적 방식으로 설치 기여를 확인합니다.
3. 두 경우 모두에서 Google은 확정적 매칭이나 비확정적 매칭 결과를 바탕으로 앱스플라이어에 어트리뷰션 응답을 전달합니다.
4. 앱스플라이어는 자체 보유한 확률론적 모델링 기술을 통해 Google의 비확정적 매칭 데이터를 다시 한번 검증합니다. 검증된 클레임만 수락됩니다.
5. 검증을 거친 Google의 클레임이 수용되면 최종 어트리뷰션 판단 단계에 진입합니다. 여기서 앱스플라이어는 Google의 성과를 다른 매체(타 SRN, 클릭 기반 네트워크)나 오가닉 유입과 비교하여 최종 기여도를 결정합니다. 설치 데이터는 앱스플라이어의 어트리뷰션 로직과 우선순위 규칙에 따라 최종 승리한 매체에 할당됩니다.
6. 클레임이 수용되고 최종 승리 후보로 선택되면, 해당 설치는 Google에 어트리뷰션됩니다. 로우 데이터 보고서상에서 확정적 클레임은 <Anchor target="_blank" href="/marketers/ko/docs/raw-data-field-dictionary#attribution::cecc12c5">match\_type</Anchor>이 `srn`(으)로, 비확정적 매칭은 매치 타입이 ‘`probabilistic`’(으)로 나타납니다.

<div id="configuring-google-ads-attribution-for-advertisers" />

## 광고주를 위한 Google Ads 어트리뷰션 구성

앱스플라이어로 Google Ads 캠페인 어트리뷰션을 시작하려면 다음 단계를 따르세요.

<div id="h_01HXXXXXPRECONDITIONSTEP1" />

<Accordion title="1단계: ICM 전제 조건 확인">

iOS 기기에서 앱스플라이어를 통한 Google PMOD 설치 클레임 지원을 위한 필수 요구 사항 안내입니다. 아래 항목을 확인하세요. Google의 On-Device Measurement(ODM) 기능을 활성화하는 데 필요한 요구 사항입니다. Android의 경우 별도의 SDK 업데이트가 필요하지 않습니다.

1. [앱스플라이어 iOS SDK](https://dev.appsflyer.com/hc/docs/install-ios-sdk) **v6.17.7 버전 이상**으로 업데이트가 필요하며, 별도의 SDK 구성 변경은 요구되지 않습니다.
2. Google SDK 업데이트 시, 다음 항목 중 하나를 충족해야 합니다.
   * **Google의 Firebase iOS** SDK **v11.14.0 이상 버전.** 자세한 내용은 [Google 문서](https://github.com/firebase/firebase-ios-sdk/releases)를 참조하세요. **또는**
   * **Google ODM 독립형** SDK. 자세한 내용은 [Firebase 문서 참조하세요.](https://support.google.com/google-ads/answer/16384720)
3. 앱 오픈 또는 인앱 이벤트 발생 시마다 <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-knowledge-base-glossary#idfv">IDFV</Anchor>가 앱스플라이어로 전송되는지 확인하세요.
4. 모든 앱 오픈 이벤트 발생 시 IP 주소가 앱스플라이어로 전송되는지 확인하세요. 앱에 IP 마스킹이 설정된 경우, ICM이 제대로 작동하지 않을 수 있습니다.

</Accordion>

<div id="step-1-create-the-google-ads-link-id-mandatory" />

<Accordion title="2단계: Google Ads 링크 ID 생성(필수)">

링크 ID를 생성하려면 계정에 대한 **Google 관리 액세스**가 필요합니다. 아래 단계를 따르거나  <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7365001?hl=en">Google 문서를 참조하세요</Anchor>.

1. Google Ads 관리자 계정에 로그인하세요.
2. 상단 메뉴에서 **도구 및 설정**을 클릭합니다.
3. **설정** 메뉴에서 **데이터 관리자**를 선택하고 **+ 제품 연결**을 클릭합니다.
4. **데이터 소스** 검색창에 "써드 파티 앱 분석"을 입력하고 선택한 후 **계속**을 클릭합니다.
5. **링크 ID 생성**을 클릭하세요.
6. 앱 분석 제공업체로 **앱스플라이어**를 선택합니다.
7. Android 또는 iOS 플랫폼을 선택하세요.
8. 앱을 찾아 선택하세요.
9. **링크 ID 생성**을 클릭하세요.

</Accordion>

<div id="step-2-set-up-google-ads-on-appsflyer-mandatory" />

<Accordion title="3단계: 앱스플라이어에서 Google Ads 설정(필수)">

**(앱스플라이어 계정의 모든 멤버)**

1. 앱스플라이어의 사이드 메뉴에서 **협업**> **파트너 마켓플레이스**를 선택하세요.
2. **Google Ads**를 검색하고 선택하세요.
3. **연동 설정**을 클릭하세요. 연동 설정 페이지로 이동합니다.
4. **연동** 탭에서 **파트너 활성화**를 켜세요.  
   **참고:** 파트너와 작업하는 동안에는 토글이 켜져 있어야(<Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">활성화됨</Anchor>) 합니다<Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">.</Anchor>
5. 이전 단계에서 복사한 **링크 ID**를 붙여넣습니다.
6. <Anchor target="_blank" href="/marketers/ko/docs/support-google-eu-consent-policy#do-i-have-control-over-consent-data-for-nonue-users">**비 EU 사용자**</Anchor>를 켤지 여부를 결정합니다.  
   <Image alt="비 EU 사용자.png" src="https://files.readme.io/fb141c0bd8885facd6574f3e73c5ec8ae8beb596de7fdf3dd8aed9d4e82686dd-22352319155985.png" width="557px" />
7. **고급 데이터 공유를** **활성화(On)** 하거나 **비활성화(Off)** **하세요.** 해당 설정을 활성화하면, 광고 식별값 활용 동의 여부와 관계없이 모든 기기의 디바이스 레벨 데이터가 포스트백 및 이벤트 형태로 Google Ads에 전달됩니다.

   또한, **고급 데이터 공유**가 활성화되면 앱스플라이어는 해당 이벤트들에 대해 어트리뷰션을 수행합니다. 해당 설정을 비활성화할 경우, IDFA 식별이 가능한 기기의 데이터만 전송되고 성과로 인정됩니다.
8. **설치 어트리뷰션** 구성:
   1. <span class="af-ol-a"></span>**설치 클릭-쓰루 룩백 윈도우**를 설정합니다.  
      룩백 윈도우 단위(시간 또는 일)를 선택하고 슬라이더를 원하는 값으로 설정하세요. Google Ads와 일치하도록 룩백 윈도우를 30일로 설정하는 것을 추천합니다.

      > 📘 **참고**
      >
      > Google Ads의 제한으로 인해, <Anchor target="_blank" href="/marketers/ko/docs/about-enriched-engagement-types#engaged_view">참여한 조회수</Anchor>와 <Anchor target="_blank" href="/marketers/ko/docs/about-enriched-engagement-types#engaged_click">참여한 클릭수</Anchor>가 클릭으로 보고됩니다.

   2. [선택 사항] Android 앱의 사전 등록 캠페인을 실행하는 경우 **사전 등록 캠페인 룩백 윈도우**를 설정하세요 (기본값은 90일입니다). 이 슬라이더는 사전 등록 캠페인에 설치를 어트리뷰션하는 룩백 윈도우를 결정합니다.
   3. **설치 뷰-쓰루 어트리뷰션**을 활성화하세요.

      > 📘 **참고**
      >
      > Google Ads 제한으로 iOS에서는 뷰스루 어트리뷰션이 지원되지 않습니다.

   4. 룩백 윈도우 단위(시간 또는 일)를 선택하고 슬라이더를 원하는 값으로 설정하세요. Google Ads와 일치하도록 뷰-쓰루 룩백 윈도우를 1일로 설정하는 것을 추천합니다.  
      **참고:** Google은 iOS 앱 노출에 대한 클레임을 발송하지 않습니다. 설치 뷰-쓰루 어트리뷰션 토글 및 룩백 윈도우 슬라이더는 이제 iOS 앱과 관련이 없습니다.
9. 새로운 통합에 대해 **재설치 귀속** 토글은 기본적으로 켜져 있습니다. 재설치 귀속을 통해 사용자가 재귀속 창 동안 앱을 재설치하는 것을 측정할 수 있습니다.

   재설치 귀속은 설치 귀속 설정의 값을 사용하므로 별도의 회고 창 구성은 필요하지 않습니다. 자세한 정보는 <Anchor target="_blank" href="/marketers/ko/docs/measure-reinstalls">재설치 측정</Anchor>을 참조하십시오.

   <div id="important" />

   > 🚧 **중요!**
   >
   > 재설치 전환 데이터는 Google Ads 대시보드에서 **session\_start**로 표시됩니다. 앱스플라이어에서는 이를 어트리뷰션하고 리어트리뷰션으로 간주합니다.

10. **리인게이지먼트 어트리뷰션**을 구성합니다.
    1. <Anchor target="_blank" href="/marketers/ko/docs/app-settings#reengagement-attribution">앱 설정에서 리타겟팅을 활성화하세요</Anchor>.
    2. Google Ads 연동 설정에서 리인게이지먼트 어트리뷰션을 활성화하세요.
    3. **리인게이지먼트 클릭-쓰루 룩백 윈도우**를 설정합니다. 이는 광고 클릭 이후 앱이 실행되어야 리인게이지먼트로 기록되는 기간입니다. 시간 또는 일 단위로 룩백 윈도우를 선택하고 슬라이더를 원하는 값으로 설정하세요.
    4. **리인게이지먼트 뷰-쓰루 어트리뷰션**을 활성화하세요.  
       **참고:** Google은 iOS 앱 노출에 대한 클레임을 발송하지 않습니다. 설치 뷰-쓰루 어트리뷰션 토글 및 룩백 윈도우 슬라이더는 이제 iOS 앱과 관련이 없습니다.
    5. **리인게이지먼트 뷰-쓰루 룩백 윈도우**를 설정합니다. 이는 광고 노출 이후 앱이 실행되어야 리인게이지먼트로 기록되는 기간입니다. 시간 또는 일 단위로 룩백 윈도우를 선택하고 슬라이더를 원하는 값으로 설정하세요.
    6. **리인게이지먼트 기간**을 설정합니다. 이는 사용자의 인앱 이벤트가 클릭 또는 노출 후에 리타겟팅 미디어 소스에 어트리뷰션되는 기간입니다. 값은 일(1&#126;90), 시간(최대 23시간) 또는 평생 단위로 설정할 수 있습니다. 기본값은 30일입니다.  
       [![](https://files.readme.io/221a5489e91a15f1d9e4db9ab8f7cbff9e47dc1b50b0f7b43323096b26008870-30759261966225.png)](https://files.readme.io/221a5489e91a15f1d9e4db9ab8f7cbff9e47dc1b50b0f7b43323096b26008870-30759261966225.png)
11. <Anchor target="_blank" href="https://support.google.com/google-ads/answer/2402582?hl=en">Google Ads iOS 앱 애셋</Anchor> (이전 명칭: 앱 확장자)이 있는 경우:  
    광고 링크에서 어트리뷰션을 받으려면 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#attribution-link-tab">**어트리뷰션 링크**</Anchor> 탭으로 이동해 앱스플라이어 단일 플랫폼 어트리뷰션 링크를 생성하고 이를 Google Ads 앱 확장 프로그램에 삽입하세요.  
    **참고:** 정적 캠페인 이름(필수)을 반드시 추가하세요.
12. **비용** 탭으로 이동합니다.
13. **비용, 클릭 수 및 노출 데이터 가져오기**를 켭니다.
14. **Google Ads 연결** 버튼을 클릭하고 Google 계정에 로그인하면 앱스플라이어에서 모든 Google Ads 캠페인 비용을 확인할 수 있습니다. <Anchor target="_blank" href="/marketers/ko/docs/google-ads-adwords-cost-and-ad-revenue">자세한 내용은 여기에서 확인하세요</Anchor>.
15. **저장**을 클릭합니다.

<div id="stop" />

> ❗️ **멈추세요!**
>
> * Google Ads에서 설치 및 재참여에 대한 앱스플라이어 어트리뷰션을 보려면 다음 앱스플라이어 이벤트를 가져와야 합니다.
>   * "첫 번째 오픈"(설치용)
>   * "세션 시작"(리인게이지먼트용)
> * 앱스플라이어에서 Google Ads 설치 성과를 확인하려면 반드시 [4단계](#step-4-measure-your-app-conversions-mandatory)를 거쳐야 합니다. 인앱 이벤트를 Google Ads에 매핑해야 하는 경우, [5단계](#step-3-map-your-inapp-events-recommended)를 먼저 진행하세요.

</Accordion>

<div id="step-4-measure-your-app-conversions-mandatory" />

<Accordion title="4단계: 앱 전환 가져오기(필수)">

<div id="important-1" />

> 🚧 **중요!**
>
> Google Ads에 새 전환을 등록하려면 **앱을 실행하고 매핑된 인앱 이벤트를 최소한 한 번 이상 수행**해야 합니다. iOS 앱을 시험하려면 이벤트를 확인하기 위해 IDFA를 수집해야 합니다. 이벤트 전환이 대기열에 추가되는 데 최대 6시간이 걸릴 수 있습니다. 추가되면 가져올 수 있으며, 새로운 전환의 상태가 "최근 전환 없음"에서 "전환 기록 중"으로 변경됩니다.

이 단계에서는 **Google 관리자 액세스**가 계정에 필요합니다 링크 ID 생성을 위해.

<Anchor target="_blank" href="https://support.google.com/google-ads/answer/7382633?sjid=11699141105296914680-EU">Google Ads 도움말 문서</Anchor>에 설명된 단계를 따르세요. 다음 사항에 유의하세요.

* 모든 앱에 대해 **first\_open** 이벤트를 전환 이벤트로 설정하세요(설치 측정을 위해 필수입니다).
* Google을 통한 리인게이지먼트를 측정할 계획이라면, **session\_start** 이벤트를 전환 이벤트로 설정하세요.
* Google에서 측정하려는 각 인앱 이벤트에 대해 이 과정을 반복하세요.

  <div id="note" />

  > 📘 **참고**
  >
  > Google Ads의 파트너 이벤트 식별자가 변경되었거나 CUSTOM으로 표시되어 있고, 해당 이벤트 이름이 앱스플라이어에서 수정된 경우에는 데이터를 다시 가져와야 합니다.

* 프로세스를 완료한 후 **전환** > **요약** 페이지에서 귀사의 써드 파티 전환 이벤트를 확인할 수 있습니다. 리스트에 이벤트가 나타나지 않거나 Google Ads 전환 목록에서 삭제된 경우 다음을 확인하세요.
  1. **모든 전환 작업 보기**를 클릭하세요. **상태** 필터가 나타납니다.
  2. **상태**를 클릭하고 **전체**를 선택하여 비활성화 및 제거된 이벤트를 포함한 모든 이벤트를 볼 수 있습니다.
* "전환에 포함" 설정이 Google Ads의 캠페인 목표에 맞게 조정되었는지 확인하세요. 자세한 내용은 Google 담당자와 상담 또는 <Anchor target="_blank" href="https://support.google.com/google-ads/answer/4677036?hl=en&co=ADWORDS.IsAWNCustomer=false">여기</Anchor>의 Google 문서를 참고하십시오.

축하합니다! 이제 앱스플라이어로 Google Ads 모바일 캠페인을 측정할 수 있습니다!

</Accordion>

<div id="step-3-map-your-inapp-events-recommended" />

<Accordion title="5단계: 인앱 이벤트 매핑(권장)">

**(앱스플라이어 계정에 연결된 모든 구성원)**

[![In-app_event_postbacks_en-us.png](https://files.readme.io/fbeef1b9d6f4462750d849878045d31b4a6614a9f36d20cd9c6f69d91a34f65a-30759221886609.png)](https://files.readme.io/fbeef1b9d6f4462750d849878045d31b4a6614a9f36d20cd9c6f69d91a34f65a-30759221886609.png)

1. **연동** 탭으로 이동하여 **인앱 이벤트 포스트백** 섹션까지 아래로 스크롤합니다.

   <div id="note-1" />

   > 📘 **참고**
   >
   > 앱에 대해 Google Ads 인앱 이벤트 매핑을 **처음으로 활성화하는 경우:**
   >
   > * **af\_app\_opened** 이벤트는 자동으로 정의되어 **session\_start**에 매핑됩니다 (그렇지 않은 경우 수동으로 추가하세요).
   > * **사용자로부터**, 각 이벤트에 대해 **오가닉을 포함한 모든 미디어 소스**를 선택해야 Google Ads에서 이러한 이벤트를 받을 수 있습니다. 연동이 성공적으로 설정된 후에는, 모든 이벤트에 대해 이 선택을 변경할 수 있습니다.

2. **인앱 이벤트 포스트백**을 활성화하세요.
3. **이벤트 추가**를 클릭하여 목록에 SDK 또는 서버-투-서버 이벤트를 추가합니다.
4. 다음 파라미터를 완성하세요.

| 파라미터 이름 | 설명 |
| --- | --- |
| **앱스플라이어 이벤트** | 앱스플라이어가 앱에 연동된 SDK 또는 서버 간 이벤트에서 수신한 이벤트의 이름입니다.<br />**팁**: 찾고 있는 이벤트가 없나요?<ul><li>논오가닉 설치 및 재확인을 통해 디바이스에서 이벤트가 활성화되었는지 확인합니다.</li><li>**앱스플라이어 이벤트**에 입력한 다음 **사용자 지정 생성**을 클릭합니다. <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#커스텀-이벤트">커스텀 이벤트 매핑</Anchor>에 대해 더 알아보세요.</li></ul> |
| **파트너 이벤트에 매핑됨** | Google Ads에서 정의한 각 이벤트의 고유한 이름 또는 ID입니다. 드롭다운 상자에서 가장 적합한 사전 정의된 앱스플라이어 이벤트를 선택하세요. |
| **사용자 유입 소스** | 이벤트 전송 옵션을 선택하세요:<ul><li>**이 파트너만**: 이 이벤트가 Google Ads에 어트리뷰션된 경우에만 포스트백을 보냅니다.</li><li>**오가닉을 포함한 모든 미디어 소스** 파트너 및 오가닉 이벤트에 기여한 이벤트에 대한 포스트백을 보냅니다.</li></ul> |
| **포함** | <ul><li>**데이터 없음(기본값)**: 이벤트 값 없이 이벤트 자체만 전송합니다.</li><li>**값 및 수익**: 수익 값(이벤트에 존재하는 경우)을 **포함한** 모든 이벤트 파라미터를 발송합니다.</li><li>**수익 없는 값**: 수익 값을 **제외한** 모든 파라미터를 전송합니다.</li></ul> |

5. **연동 저장을 클릭합니다.**
6. 연동을 저장한 후 구성 페이지에 머물면서 더 많은 앱을 파트너와 연동할 수 있습니다.
   1. 왼쪽 상단 모서리에서 파트너 이름 아래에 있는 앱 이름을 클릭하여 앱 목록을 엽니다.
   2. 드롭다운 목록에서 다른 앱을 선택합니다.
   3. 선택한 앱에 대해 연동 단계를 반복합니다.

</Accordion>

<div id="tip" />

> 👍 **팁**
>
> Google Ads API 연동에는 Google Ads 리마케팅 기능이 자동으로 포함됩니다. 이 연동을 완료하고 이벤트를 Google Ads에 전송하면 추가 연동 없이 Google Ads에서 리마케팅 오디언스 목록을 생성할 수 있습니다.

<div id="granting-permissions-to-google-ads-team-members" />

## Google Ads 팀원에게 권한 부여

Google Ads에게 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#permissions-tab">귀사의 특정 데이터에 대한 액세스 권한</Anchor>을 부여할 수 있습니다. 귀사의 각 앱에 대한 Google Ads 구성 페이지에서 '권한' 탭을 통해 이 작업을 수행할 수 있습니다.

이러한 권한과 액세스를 받기 위해, 귀사의 Google Ads 담당자는 앱스플라이어의 Google Ads 파트너 계정 팀원이 되어야 합니다.

Google의 개인정보 보호 요구 사항으로 인해 광고주가 명시적으로 요청한 경우에만 새로운 팀원을 앱스플라이어 파트너 계정에 추가할 수 있습니다.

Google Ads 팀원에게 귀사의 앱에 대한 액세스를 부여하려면 다음 절차를 따르세요.

1. 앱스플라이어의 Google 파트너 계정에 귀사의 계정 관리자가 추가되도록 요청하려면 <Anchor target="_blank" href="https://docs.google.com/forms/d/e/1FAIpQLSfJmwEPxy4bXw0mEsKfJ3D5dZmRZgHS3LCiyoEFsZRos0jWIQ/viewform">이 양식</Anchor>을 작성하여 제출하세요.
2. Google Ads에서 귀사의 계정 관리자가 추가되었다는 확인을 기다리세요.
3. **구성** > **활성화된 연동** > **Google Ads** > **권한**으로 이동하여 귀사의 계정 관리자 이메일을 팀원 목록에 추가하세요.
4. 귀사의 Google Ads 계정 관리자에게 부여하고자 하는 권한을 활성화합니다.

<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#permissions-tab">광고 네트워크에 권한 제공하기</Anchor>에 대해 자세히 알아보세요.

<div id="enabling-google-ads-attribution-for-agencies" />

## 에이전시를 위한 Google Ads 어트리뷰션 활성화

앱스플라이어는 Google Ads와 함께 에이전시 구성을 지원합니다. 앱스플라이어가 데이터를 정확하게 어트리뷰션할 수 있도록 광고주와 대행사는 별도의 Google Ads 계정을 가지고 있어야 합니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/google-ads-adwords-integration-setup-for-agencies">Google Ads 통합을 위한 대행사 구성</Anchor>을(를) 참조하세요.

<div id="running-with-multiple-google-ads-accounts" />

## 여러 Google Ads 계정으로 운영

앱스플라이어는 동일한 앱에 대해 여러 Google Ads 계정 사용을 지원합니다. 이 작업은 Google Ads에서 링크 ID를 공유하고 각 Google Ads 계정으로 이벤트를 가져오는 방식으로 수행됩니다.

자세한 내용은 <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7365001">Google Ads 링크 ID 공유에 관한 Google 문서</Anchor>를 참조하세요.

<div id="ios-app-campaigns" />

## iOS 앱 캠페인

**참고**: 이 섹션은 설치를 위한 앱 캠페인에만 적용되며 인게이지먼트를 위한 앱 캠페인에는 적용되지 **않습니다**.

2021년 1월 27일에 <Anchor target="_blank" href="https://blog.google/products/ads-commerce/preparing-developers-and-advertisers-for-policy-updates/">Google이 iOS 14 출시에 맞춰 정책 업데이트</Anchor>를 발표했습니다.

앱 추적 투명성 시행이 시작된 이후 Google iOS 앱은 ATT 프롬프트를 사용하지 않으며, 이에 따라 Google Ads 제품은 ATT에 해당하는 디바이스 식별자(IDFA)를 <Anchor target="_blank" href="https://support.google.com/google-ads/answer/10417364">더 이상 사용하지 않게 되었습니다</Anchor>. 단, ATT 프롬프트를 지원하는 YouTube 앱은 예외입니다.

리포팅 및 캠페인 최적화를 유지하기 위해 Google은 모델링된 전환을 iOS 14+ 트래픽으로 확장했습니다.

모델링된 전환은 디바이스 ID에 의존하지 않으므로 iOS 14.5 출시 이후 Google에서 사용하는 iOS 설치 앱 캠페인 인벤토리 로직은 다음과 같습니다.

* iOS ACI 검색 인벤토리는 디바이스 ID로 어트리뷰션되지 않습니다. 이는 2020년 1월 24일에 발표된 Google의 정책을 따릅니다.
* 광고주와 퍼블리셔 앱 모두에서 사용자 동의를 받아 디바이스 ID를 사용할 수 있는 상태에만, iOS ACI 디스플레이 인벤토리의 성과 측정이 가능합니다.
* 모든 iOS ACI 캠페인은 ICM을 통해 어트리뷰션이 가능합니다. 이는 광고주 앱, 퍼블리셔 앱 또는 두 앱 모두에서 디바이스 ID를 사용할 수 없는 경우에 적용됩니다.
* Google은 현재 iOS에서 클릭만 클레임합니다. 노출에 대해서는 클레임하지 않습니다.

<div id="note-2" />

<div id="using-deferred-deep-linking-in-app-campaigns" />

## 앱 캠페인에서 디퍼드 딥링킹 사용하기

**딥링크란 무엇이며 어떻게 작동하나요?**

잠재적 사용자가 피드를 클릭하면 앱 페이지로 리디렉션됩니다. 사용자가 앱을 설치하고 실행하면 SDK는 디퍼드 딥링킹을 통해 특정 제품 세부 정보(예: 운영화)를 제공합니다. 앱 개발자는 이 데이터를 사용하여 앱 내에서 관련 사용자 경험을 제공합니다.

**Google에서 디퍼드 딥링킹**

<Anchor target="_blank" href="https://support.google.com/google-ads/answer/9959794?hl=en&ref_topic=10011599">앱 캠페인의 Google 피드</Anchor> 또는 <Anchor target="_blank" href="https://support.google.com/google-ads/answer/12373847?">광고 그룹 디퍼드 딥링킹</Anchor>을 활용하면, 신규 모바일 사용자에게 콘텐츠에 특화된 매끄러운 경험을 제공할 수 있습니다. Google에서는 피드 또는 광고 그룹 중 하나에 딥링크를 설정할 수 있으며, 앱스플라이어는 두 경우 모두 디퍼드 딥링크를 지원합니다.

**Google Ads에서 디퍼드 딥링킹을 활성화하는 방법:**

1. 앱스플라이어 SDK에서 <Anchor target="_blank" href="/marketers/ko/docs/conversion-data-payloads-and-scenarios#re-attribution-with-deferred-deep-linking">파라미터를 수신하려면 반드시</Anchor> <Anchor target="_blank" href="/marketers/ko/docs/conversion-data-payloads-and-scenarios#re-attribution-with-deferred-deep-linking">GCD</Anchor>를 사용해야 합니다.
2. Google에서 <Anchor target="_blank" href="https://support.google.com/google-ads/answer/9958973?hl=en&ref_topic=10011599">피드를 설정</Anchor>하거나 <Anchor target="_blank" href="https://support.google.com/google-ads/answer/12373847?">광고 그룹 수준의 디퍼드 딥링킹을 설정</Anchor>하세요.
3. 앱스플라이어에서 **구성** > **활성화된 연동** 으로 이동합니다. **Google Ads (Adwords)** 를 선택하세요.
4. **연동** 탭에서 **Google Ads와의 디퍼드 딥링킹**을 켭니다.
5. **연동 저장을 클릭합니다.**

<div id="populate-the-channel-parameter" />

<div id="google-ads-parameter-mapping" />

## Google Ads 파라미터 매핑

다음 표는 Google Ads와 앱스플라이어 간의 파라미터 매핑을 설명합니다. 광고주는 Google Ads 캠페인에 개인화된 파라미터를 추가할 수 없습니다.

| **네트워크 유형** | **검색** | **디스플레이** | **유튜브** |
| --- | --- | --- | --- |
| 채널 (`af_channel`) | 아래 표에서 [`채널` 파라미터를 채우는 방법](/docs/google-ads-adwords-integration-setup-for-advertisers#google-ads-파라미터-매핑)을 참조하세요. |  |  |
| 캠페인 (`c`) | 예 | 예 | 예 |
| 캠페인 ID (`af_c_id`) | 예 | 예 | 예 |
| 애드셋 (`af_adset`)  <br />`ad_group_name` 매개변수에 의해 채워집니다.  <br />이 매개변수가 null인 경우, AF는 `ad_group_id`로 `af_adset`을(를) 채웁니다. | 예 | 예 | 예 |
| Google `ad_group_id` 매개변수에 의해 채워진 광고 세트 ID (`af_adset_id`) | 예 | 예 | 예 |
| Ad (`af_ad`) | 해당 없음 | 해당 없음 | 해당 없음 |
| Ad ID (`af_ad_id`)  <br />Google의 `creative_id` 매개변수에 의해 채워집니다. | 예 | 예 | 예 |
| Ad 유형 (`af_ad_type`) | 예* | 예* | 예* |
| 사이트 ID (`af_siteid`) | GoogleSearch/  <br />SearchPartners | 해당 없음 | YouTubeVideos/  <br />VideoPartners |
| 키워드 | 해당 없음 | 해당 없음 | 해당 없음 |

`채널` 파라미터를 채우는 방법

Google Ads는 `채널(af_channel)` 파라미터를 발송하지 않습니다. 앱스플라이어는 다음 규칙에 따라 Google Ads에서 받은 캠페인 유형에 대해 이 파라미터를 채우는 방법을 결정합니다.

<table><thead><tr><th colspan="2">캠페인 유형 <strong>및</strong> 네트워크 유형 논리:</th><th rowspan="2"> <kbd>채널</kbd> 파라미터</th><th rowspan="2">예시</th></tr><tr><th>캠페인 유형</th><th>network_type</th></tr></thead><tbody><tr><td> <kbd>ACI</kbd>, <kbd>ACE</kbd>, <kbd>ACPRE</kbd>, <kbd>쇼핑</kbd>, 또는 <kbd>호텔</kbd> </td><td>모든 네트워크 유형</td><td><kbd>캠페인_유형_네트워크_유형</kbd></td><td>채널 = <kbd>ACI_Search</kbd> </td></tr><tr><td><p><strong>제외:</strong></p><p><kbd>ACI</kbd>, <kbd>ACE</kbd>, <kbd>ACPRE</kbd>, <kbd>쇼핑</kbd>, 또는 <kbd>호텔</kbd></p></td><td><kbd>디스플레이</kbd></td><td><kbd>네트워크_하위_유형</kbd></td><td>채널 = <kbd>mGDN</kbd> </td></tr><tr><td><p><strong>제외:</strong></p><p><kbd>ACI</kbd>, <kbd>ACE</kbd>, <kbd>ACPRE</kbd>, <kbd>쇼핑</kbd>, 또는 <kbd>호텔</kbd></p></td><td><p><strong>제외:</strong></p><p><kbd>디스플레이</kbd></p></td><td><kbd>네트워크_유형</kbd></td><td>채널 = <kbd>Search</kbd> </td></tr></tbody></table>

Google 응답에서 사용할 수 있는 광고 유형에 대한 자세한 내용은 <Anchor target="_blank" href="https://developers.google.com/app-conversion-tracking/api/request-response-specs">Google 요청 및 응답 사양</Anchor>을(를) 참조하세요.

<div id="note-3" />

> 📘 **참고**
>
> Google이 확률론적 어트리뷰션을 통해 설치 성과를 어트리뷰트 할 때, Google은 앱스플라이어와 `network_type`을(를) 공유하지 않습니다. 그 결과, 네트워크 유형이 누락되며, 채널 값은 (접미사 없이)`ACI_`(으)로 표시됩니다.

<div id="campaign-type-app-campaigns" />

### 캠페인 유형: 앱 캠페인

<div id="changes-to-campaign-names-by-google-ads" />

#### Google Ads에서의 캠페인 이름 변경

| 2021년 2월 15일까지 | 2021년 2월 23일부터 시작 |
| --- | --- |
| UAC | ACI |
| UACE | ACE |
| UACPre | ACPRE |

**참고:** 캠페인 이름 유형은 클릭 또는 노출 날짜를 기준으로 설정되며, 설치 날짜는 아닙니다.

<div id="engaged-view-parameter-in-raw-data-reports" />

### 로데이터 리포트의 참여 뷰 파라미터

적극적 조회란 사용자가 10초 이상 지속된 비디오 광고에 노출된 경우를 의미합니다. 적극적 조회는 클릭과 동일한 어트리뷰션 우선 순위를 가지고 있습니다.  안드로이드의 경우, 적극적 조회는 로데이터 리포트에서 `Engagement Type` 및 `Sub Param 5` 파라미터 아래에 `engaged_view`로 표시됩니다.   
적극적 조회는 앱스플라이어에서 설정된 클릭 룩백 윈도우 기간 내에 발생한 경우에만 집계되며, 최대 3일까지로 제한됩니다.

<div id="send-complex-in-app-events-to-google-ads" />

<div id="important-2" />

> 🚧 **중요!**
>
> * Google은 SRN(Self Reporting Network)입니다. 이러한 네트워크의 기여 흐름이 작동하는 방식에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/self-reporting-networks-srns">자체 보고 네트워크(SRN)</Anchor>을(를) 참조하세요.
> * 앱스플라이어는 Google에서 제공되는 모든 캠페인 정보를 제시할 수 있습니다. 캠페인 유형(검색, 비디오, 디스플레이) 및 관련 정보는 Google에 의해 결정됩니다. 자세한 내용은 <Anchor target="_blank" href="https://developers.google.com/app-conversion-tracking/api/request-response-specs">Google 요청 및 응답 사양</Anchor>을(를) 참조하세요.

<div id="optimize-google-ads-campaigns-for-conversions-without-device-id" />

## 디바이스 ID 없이 전환을 위해 Google Ads 캠페인을 최적화하세요.

iOS14.5 이상 및 Android 12 이상부터 Google Ads에 여러 식별자가 도입되었습니다. 이러한 식별자는 디바이스 ID 없이 전환을 결정적 어트리뷰션하는 데 사용됩니다.

| 식별자 | 사용 가능 시점 | 소스 | 운영 체제 | 사용 목적 | 데이터 세분화 |
| --- | --- | --- | --- | --- | --- |
| gclid | 2021년 12월 | Google Play 리퍼러 | Android | 설치/재설치 | 사용자 수준 |
| gclid | 2021년 12월 | 딥 링크 URL | Android + iOS | 리인게이지먼트 | 사용자 수준 |
| gbraid | 2021년 3월 | 딥 링크 URL | iOS | 리인게이지먼트 | 종합 |
| odm\_info | 2025년 11월 | 앱스플라이어 SDK / S2S | iOS | 설치/재설치 | 종합 |

Google Ads와 앱스플라이어에서 광고주는 리인게이지먼트, 설치, 리어트리뷰션 활동에 대해 디바이스 ID가 없는 트래픽이라도 캠페인 수준 데이터를 수신할 수 있습니다. 그러나 광고 세트 및 광고 수준 데이터는 Google에 의해 공유되지 않습니다.  
**이러한 파라미터를 수신하기 위해 광고주가 별도의 조치를 취할 필요는 없습니다.**

<div id="data-visibility-by-operating-system" />

### 운영 체제별 데이터 가시성

**Android 앱:**

앱스플라이어와 Google Ads에서 광고주들은 디바이스 ID 없이 설치와 리인게이지먼트 모두에 대해 트래픽의 전체 캠페인 데이터를 받을 수 있습니다.

**iOS 앱:**

Google Ads와 앱스플라이어에서 광고주는 리인게이지먼트에 관한 기기 ID 없이 트래픽에 대한 전체 캠페인 데이터를 받을 수 있습니다.

<div id="advertising-without-the-firebase-sdk" />

## Firebase SDK 없이 광고하기

Firebase SDK가 구현되지 않은 상태에서 Google Ads로 광고할 때는 다음과 같은 제한 사항이 적용됩니다.

| 제한 사항 | 세부 정보 |
| --- | --- |
| tROAS 지원되지 않음 | tROAS(광고 지출 대비 목표 수익) 최적화는 Firebase SDK 수익 이벤트를 사용할 때만 가능합니다. AppsFlyer 수익 이벤트 및 다른 모든 MMP의 수익 이벤트는 이 최적화에 적합하지 않습니다. |
| 청중 제외 지원되지 않음 | 광고주는 캠페인이 Firebase SDK 이벤트를 최적화할 때만 앱 캠페인에서 사용자를 제외할 수 있습니다. |

<div id="google-probabilistic-attribution-icm-traits-and-limitations" />

## Google의 확률론적 어트리뷰션(ICM) 특성과 한계

| 제한 사항 | 세부 정보 |
| --- | --- |
| 어트리뷰션 범위 | **설치 및 리어트리뷰션에 대해서만** 지원되며 리인게이지먼트는 지원하지 **않습니다**. |
| 클레임 데이터 | Google 클레임 포함 항목:<ul><li>**캠페인 이름**</li><li>**캠페인 ID**</li></ul>**광고 세트** 또는 **광고 정보**는 포함되지 않습니다. |
| 채널 필드 | 네트워크 유형 또는 하위 유형 정보는 제공되지 않으며 **채널** 필드에는 부분적인 값 `ACI_`만 포함됩니다.  <br />‘채널’ 로직에 대한 자세한 정보는 [어떻게 `채널` 매개변수를 채우는 방법](/docs/google-ads-adwords-integration-setup-for-advertisers#google-ads-파라미터-매핑)을 참조하세요. |
| iOS ODM 지역 지원 | **EU, UK 및 스위스에서 지원되지 않음** |
| 집계된 고급 개인 정보 보호(AAP) | iOS 앱 설정에서 <Anchor target="_blank" href="/marketers/ko/docs/apply-aggregated-advanced-privacy-framework">AAP</Anchor>(Aggregated Advanced Privacy) 토글이 **ON**으로 설정되어 있으면, 로데이터 리포트 내 Google 어트리뷰션 데이터는 제한 상태로 표시됩니다. Google 비동의 데이터를 보려면 AAP 토글이 **OFF** 상태인지 확인하세요. |
| 어트리뷰션된 터치 시간 | Google 확률론적 어트리뷰션 성과 클레임 시점의 타임스탬프는 15분 간격(00:00, 00:15, 00:30 등)으로 반올림됩니다. |
| IP 차단 | IP 마스킹을 사용하면 ICM 성능에 영향을 줄 수 있습니다. Google은 IP 마스킹이 Google Ads 측정 및 성능에 영향을 줄 수 있으므로 이를 사용 중지할 것을 권장합니다. <Anchor target="_blank" href="/marketers/ko/docs/apply-ip-masking-to-user-data#ip-차단">사용자 데이터에 IP 마스킹 적용</Anchor>을(를) 참조하세요. |
| IDFV | Google은 ICM 성능을 극대화하기 위해 설치, 앱 열기 및 인앱 이벤트와 함께 <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-knowledge-base-glossary#idfv">IDFV</Anchor>(사용 가능한 경우)를 전송할 것을 요구합니다. |

<div id="h_01HDP0SBEE75MAT4A4S9E7Y7FF" />

> 📄 **참고 문서**
>
> * iOS 14 관련 고려 사항은 <Anchor target="_blank" href="/marketers/ko/docs/get-skan-postback-data-from-google-ads">Google Ads SKAdNetwork와 앱스플라이어의 상호운용성</Anchor>을 참조하세요.

<div data-zendesk-anchors="google-icm-attribution-flow-with-advanced-data-sharing=%EA%B3%A0%EA%B8%89-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B3%B5%EC%9C%A0%EB%A5%BC-%ED%99%9C%EC%9A%A9%ED%95%9C-google-ads-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%9D%90%EB%A6%84 h_01K0VKGRK7XXC4GNF6B9X76M4T=%EA%B3%A0%EA%B8%89-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B3%B5%EC%9C%A0%EB%A5%BC-%ED%99%9C%EC%9A%A9%ED%95%9C-google-ads-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%9D%90%EB%A6%84 configuring-google-ads-attribution-for-advertisers=%EA%B4%91%EA%B3%A0%EC%A3%BC%EB%A5%BC-%EC%9C%84%ED%95%9C-google-ads-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EA%B5%AC%EC%84%B1 h_01HACTC1H5MANBCRWYQPNW5CC2=%EA%B4%91%EA%B3%A0%EC%A3%BC%EB%A5%BC-%EC%9C%84%ED%95%9C-google-ads-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EA%B5%AC%EC%84%B1 step-1-verify-prerequisites=h_01HXXXXXPRECONDITIONSTEP1 h_01HACTC1H5XEJEPMZ4C7GP8GG6=step-1-create-the-google-ads-link-id-mandatory h_01HACTC1H5HEP9759J2PCPPZSW=step-2-set-up-google-ads-on-appsflyer-mandatory h_01K9S9C04GHJW1C88R64V742VZ=%EC%B0%B8%EA%B3%A0 h_01K9S93R7E30BCCEYJA4TW2AXV=%EC%B0%B8%EA%B3%A0-1 h_01HACTC1H5R995RXYRFQBFHRF1=%EC%A4%91%EC%9A%94 h_01HACTC1H5EFJKV6AXNSTNFZA4=%EB%A9%88%EC%B6%94%EC%84%B8%EC%9A%94 h_01HACTC1H5GV04KFM29NCCK8J2=step-4-measure-your-app-conversions-mandatory h_01HSX7TJC7PQ0ATM1J86Z4HMYJ=%EC%A4%91%EC%9A%94-1 h_01KA6S8V6CKRATXHZQZ4YN7V9R=%EC%B0%B8%EA%B3%A0-2 h_01HACTC1H50DDS3WCZ9DCHKN0P=step-3-map-your-inapp-events-recommended h_01HACTC1H58WHJDBN2DRQAZKGB=%EC%B0%B8%EA%B3%A0-3 h_01HACTC1H5Z3XXS1MGBS4WYJBV=%ED%8C%81 granting-permissions-to-google-ads-team-members=google-ads-%ED%8C%80%EC%9B%90%EC%97%90%EA%B2%8C-%EA%B6%8C%ED%95%9C-%EB%B6%80%EC%97%AC h_01HACTC1H5PAY95M4H1A6WTSEF=google-ads-%ED%8C%80%EC%9B%90%EC%97%90%EA%B2%8C-%EA%B6%8C%ED%95%9C-%EB%B6%80%EC%97%AC enabling-google-ads-attribution-for-agencies=%EC%97%90%EC%9D%B4%EC%A0%84%EC%8B%9C%EB%A5%BC-%EC%9C%84%ED%95%9C-google-ads-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%99%9C%EC%84%B1%ED%99%94 h_01HACTC1H5QE93EAYYVVDQV2WC=%EC%97%90%EC%9D%B4%EC%A0%84%EC%8B%9C%EB%A5%BC-%EC%9C%84%ED%95%9C-google-ads-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%99%9C%EC%84%B1%ED%99%94 running-with-multiple-google-ads-accounts=%EC%97%AC%EB%9F%AC-google-ads-%EA%B3%84%EC%A0%95%EC%9C%BC%EB%A1%9C-%EC%9A%B4%EC%98%81 h_01HACTC1H5Z8B15RHQ75HVV2RP=%EC%97%AC%EB%9F%AC-google-ads-%EA%B3%84%EC%A0%95%EC%9C%BC%EB%A1%9C-%EC%9A%B4%EC%98%81 ios-app-campaigns=ios-%EC%95%B1-%EC%BA%A0%ED%8E%98%EC%9D%B8 h_01HACTC1H5X567H6A8M3FWCTAN=ios-%EC%95%B1-%EC%BA%A0%ED%8E%98%EC%9D%B8 using-deferred-deep-linking-in-app-campaigns=%EC%95%B1-%EC%BA%A0%ED%8E%98%EC%9D%B8%EC%97%90%EC%84%9C-%EB%94%94%ED%8D%BC%EB%93%9C-%EB%94%A5%EB%A7%81%ED%82%B9-%EC%82%AC%EC%9A%A9%ED%95%98%EA%B8%B0 h_01HACTC1H57HJZNAGDKSQD6MVC=%EC%95%B1-%EC%BA%A0%ED%8E%98%EC%9D%B8%EC%97%90%EC%84%9C-%EB%94%94%ED%8D%BC%EB%93%9C-%EB%94%A5%EB%A7%81%ED%82%B9-%EC%82%AC%EC%9A%A9%ED%95%98%EA%B8%B0 google-ads-parameter-mapping=google-ads-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0-%EB%A7%A4%ED%95%91 h_01HACTC1H6P1A2E160Z6GAGZZS=google-ads-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0-%EB%A7%A4%ED%95%91 how-to-populate-the-channel-parameter=google-ads-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0-%EB%A7%A4%ED%95%91 h_01HACTC1H6TPTDDFSMPQ9YVMDY=google-ads-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0-%EB%A7%A4%ED%95%91 h_01KEYE1W4VJYXYHY4FP1KN3SP9=%EC%B0%B8%EA%B3%A0-4 campaign-type-app-campaigns=%EC%BA%A0%ED%8E%98%EC%9D%B8-%EC%9C%A0%ED%98%95-%EC%95%B1-%EC%BA%A0%ED%8E%98%EC%9D%B8 h_01HACTC1H6CEGD2E3HXHWFWBRB=%EC%BA%A0%ED%8E%98%EC%9D%B8-%EC%9C%A0%ED%98%95-%EC%95%B1-%EC%BA%A0%ED%8E%98%EC%9D%B8 changes-to-campaign-names-by-google-ads=google-ads%EC%97%90%EC%84%9C%EC%9D%98-%EC%BA%A0%ED%8E%98%EC%9D%B8-%EC%9D%B4%EB%A6%84-%EB%B3%80%EA%B2%BD h_01HACTC1H6A028HKVXJ66MCF6M=google-ads%EC%97%90%EC%84%9C%EC%9D%98-%EC%BA%A0%ED%8E%98%EC%9D%B8-%EC%9D%B4%EB%A6%84-%EB%B3%80%EA%B2%BD engaged-view-parameter-in-raw-data-reports=%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%A6%AC%ED%8F%AC%ED%8A%B8%EC%9D%98-%EC%B0%B8%EC%97%AC-%EB%B7%B0-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 h_01HACTC1H6Q6WCTK4Z9RGV6PA4=%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%A6%AC%ED%8F%AC%ED%8A%B8%EC%9D%98-%EC%B0%B8%EC%97%AC-%EB%B7%B0-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0 h_01HACTC1H62HC36C08ZBFZ05XS=%EC%A4%91%EC%9A%94-2 optimize-google-ads-campaigns-for-conversions-without-device-id=%EB%94%94%EB%B0%94%EC%9D%B4%EC%8A%A4-id-%EC%97%86%EC%9D%B4-%EC%A0%84%ED%99%98%EC%9D%84-%EC%9C%84%ED%95%B4-google-ads-%EC%BA%A0%ED%8E%98%EC%9D%B8%EC%9D%84-%EC%B5%9C%EC%A0%81%ED%99%94%ED%95%98%EC%84%B8%EC%9A%94 h_01HACTC1H6EFDVN9N89Y17HDFR=%EB%94%94%EB%B0%94%EC%9D%B4%EC%8A%A4-id-%EC%97%86%EC%9D%B4-%EC%A0%84%ED%99%98%EC%9D%84-%EC%9C%84%ED%95%B4-google-ads-%EC%BA%A0%ED%8E%98%EC%9D%B8%EC%9D%84-%EC%B5%9C%EC%A0%81%ED%99%94%ED%95%98%EC%84%B8%EC%9A%94 data-visibility-by-operating-system=%EC%9A%B4%EC%98%81-%EC%B2%B4%EC%A0%9C%EB%B3%84-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B0%80%EC%8B%9C%EC%84%B1 h_01HACTC1H6WZNMVJK479M5KJYF=%EC%9A%B4%EC%98%81-%EC%B2%B4%EC%A0%9C%EB%B3%84-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B0%80%EC%8B%9C%EC%84%B1 h_01_advertising-without-firebase-sdk=firebase-sdk-%EC%97%86%EC%9D%B4-%EA%B4%91%EA%B3%A0%ED%95%98%EA%B8%B0 advertising-without-the-firebase-sdk=firebase-sdk-%EC%97%86%EC%9D%B4-%EA%B4%91%EA%B3%A0%ED%95%98%EA%B8%B0 google-icm-traits-and-limitations=google%EC%9D%98-%ED%99%95%EB%A5%A0%EB%A1%A0%EC%A0%81-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98icm-%ED%8A%B9%EC%84%B1%EA%B3%BC-%ED%95%9C%EA%B3%84 h_01K0XMCXSS5MKY90DZWJTNVBBS=google%EC%9D%98-%ED%99%95%EB%A5%A0%EB%A1%A0%EC%A0%81-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98icm-%ED%8A%B9%EC%84%B1%EA%B3%BC-%ED%95%9C%EA%B3%84 h_01HDP0SBEE75MAT4A4S9E7Y7FF=%EC%B0%B8%EA%B3%A0-%EB%AC%B8%EC%84%9C" />
