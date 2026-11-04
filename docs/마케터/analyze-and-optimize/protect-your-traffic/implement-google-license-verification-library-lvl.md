---
title: Google License Verification Library(LVL) 설정
metadata:
  keywords:
    - Premium
    - Premium Feature
    - Marketers
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2023-07-27T14:45:46Z'
  edited_at: '2026-10-14T10:29:00Z'
  id: 17329535522961
  locale: ko
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/ko/articles/17329535522961
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **한눈에 보기:** Google Play와의 모든 라이선스 관련 커뮤니케이션을 처리하는 Google License Verification Library(LVL)를 추가하여 앱의 무단 사용을 미리 방지하세요.

<div id="overview" />

## 개요

LVL은 귀하의 앱에 추가할 수 있는 라이브러리(Android SDK에서 다운로드 가능)로서 Google Play 라이선스 서비스와의 모든 라이선스 관련 커뮤니케이션을 처리하는 역할을 합니다.

이는 Google Play와 앱스플라이어 대시보드에 표시되는 인스톨 수가 불일치하는 현상을 줄이는 데도 도움이 됩니다.

Google Play 라이선스 서비스는 유저에게 앱 사용 라이선스가 있는지 여부를 확인하는 역할을 합니다. Google Play에서는 유저가 앱 구매자로 기록되면 라이선스가 부여된 것으로 간주합니다. 라이선스는 앱마다 고유하게 부여되며 프로드 방지 강화를 위해 사용될 수 있습니다. <Anchor target="_blank" href="https://developer.android.com/google/play/licensing">더 알아보기</Anchor>

앱스플라이어의 SDK는 고객 측으로부터의 데이터를 수집하고 Protect360은 서버 측 라이선스 유효성을 검사하여, 오가닉 인스톨과 논오가닉 인스톨 확인에 모두 실패한 프로드 인스톨을 차단합니다. Protect360 대시보드 및 리포트에 표시되는 “차단 이유”는 “Bots”입니다.

<div id="note" />

<div id="set-up-lvl" />

## LVL 설정

귀하께서 아래 정보를 앱스플라이어 CSM에 전달하면 하는 수동으로 추가가 되는 수동 프로세스입니다.

**LVL을 추가하려면:**

1.
   ```http
   appsflyerSdkVersion = "YOUR_SDK_VERSION" // e.g., 6.15.2
   ```
2.
   ```http
   dependencies {
       implementation("com.appsflyer:af-android-sdk:$appsflyerSdkVersion")
       implementation("com.appsflyer:lvl:$appsflyerSdkVersion")
   }
   ```
3.
   ```http
   dependencies {
       val appsflyerSdkVersion = "<YOUR_SDK_VERSION>" // e.g., 6.15.2
       implementation("com.appsflyer:af-android-sdk:$appsflyerSdkVersion")
       implementation("com.appsflyer:lvl:$appsflyerSdkVersion")
   }
   ```
4. 앱 라이선스 및 인앱 결제 가져오기:  
   Google Play 개발자 콘솔에서 (앱 선택 -> 개발 도구 -> 서비스 및 API 선택)  

   ```http
   Base64-encoded RSA public key
   ```
5. CSM에 다음 정보를 제공하십시오.

* 공개 키
* app-id
* LVL이 연동된 최소 앱 버전


<div id="test-and-troubleshoot" />

<Accordion title="다음 단계">

귀하의 요청이 접수되면 Protect360 팀은 스테이징 모드에서 LVL 유효성 검사를 구성합니다. 이 단계에서 시스템은 앱스플라이어에 대한 내부 LVL 유효성 결과만 보고합니다. 며칠 후, 앱스플라이어 측에서 데이터를 확인합니다.

**문제가 발견되지 않는 경우:**

* 앱스플라이어가 LVL 유효성을 PRODUCTION 모드로 설정하고 트래픽 차단을 시작합니다.
* Protect360팀이 CSM에 알립니다.

**뭔가 잘못된 경우**(예: 인스톨 이벤트에 LVL 정보가 표시되지 않는 경우):

* 앱스플라이어에서 LVL 유효성 모드를 STAGING 상태로 설정할 것입니다.
* CSM팀에서 귀하께 연락을 드리고 앱 구현 문제를 해결을 지원합니다.

</Accordion>

<div id="setup-process" />

<Accordion title="테스트 및 문제 해결">

앱을 디버깅할 때 아래 예와 같이 앱스플라이어로 전송되는 페이로드에 대한 LVL 정보를 볼 수 있어야 합니다.

```json
"lvl":{
      "ttr":,<ttr>,
      "signature":"<signature>",
      "signedData":"<signedData>"
   }
```

설치 메시지에 LVL 정보가 없는 경우 지원/SDK 팀과 상의하십시오.

</Accordion>

<div id="faq" />

## 자주 묻는 질문

<div id="what-if-an-app-is-installed-from-a-store-other-than-google-play" />

<Accordion title="Google Play가 아닌 다른 스토어에서 앱을 설치하면 어떻게 되나요?">

LVL 유효성 검사는 Google Play 이외의 스토어에서 들어오는 인스톨을 확인하거나 차단하지 않습니다.

</Accordion>

<div id="how-much-time-does-it-take-to-get-lvl-set-up" />

<Accordion title="LVL을 설정하는 데 시간이 얼마나 걸리나요?">

정보를 가져온 뒤 LVL을 설정하고 데이터를 확인하는 데 영업일 기준으로 수 일이 소요될 수 있습니다. [설정 프로세스](/docs/implement-google-license-verification-library-lvl#setup-process)에 대한 세부정보를 확인하세요.

</Accordion>

<div id="does-lvl-affect-app-functionality" />

<Accordion title="LVL이 앱 기능에 영향을 미치나요?">

아니요, 앱 기능은 영향을 받지 않습니다.

</Accordion>

<div id="what-is-the-difference-between-lvl-and-gpreferrer" />

<Accordion title="LVL과 GP 리퍼러의 차이점은 무엇입니까?">

LVL을 사용한 라이센스 유효성 검사는 GP-리퍼러 검증 알고리즘과 다릅니다. LVL은 앱 자체의 라이센스를 검증하는 반면, GP-리퍼러는 Google Play 스토어에서 설치된 패키지의 리퍼러 URL을 사용하여 인스톨의 리디렉션 소스를 가져오는 데 사용됩니다. (리퍼러 클릭이 발생한 시간, 설치가 시작된 시간, 앱 버전 등) 즉, LVL은 유저에게 앱 사용 권한이 있는지 확인하는 데 사용되는 반면 GP-리퍼러는 인스톨 세부 정보가 위조되지 않았는지 확인하는 데 사용됩니다.

</Accordion>

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 01H7YJ35YKDHJ2MDZSSYKMDCJ4=%EA%B0%9C%EC%9A%94 set-up-lvl=lvl-%EC%84%A4%EC%A0%95 01H7YJ35YKDW0CB9TWRBKFBCDJ=lvl-%EC%84%A4%EC%A0%95 01JGK7NK10ZDD6CM6Y4631FB4Q=lvl-%EC%84%A4%EC%A0%95 01H7YJ35YKX1CVYMRZ1W8NRH7Y=test-and-troubleshoot 01H7YJ35YKMCN2E2BDWA5DD5M3=setup-process faq=%EC%9E%90%EC%A3%BC-%EB%AC%BB%EB%8A%94-%EC%A7%88%EB%AC%B8 01H7YJ35YMR8PBTTSHD77WZ4AE=%EC%9E%90%EC%A3%BC-%EB%AC%BB%EB%8A%94-%EC%A7%88%EB%AC%B8 01H7YJ35YMRZ8KRSVND1JT6JGH=what-if-an-app-is-installed-from-a-store-other-than-google-play 01H7YJ35YM11J0EG0B8PBMSPAC=how-much-time-does-it-take-to-get-lvl-set-up 01H7YJ35YMH0NM73Y1R90JDMEA=does-lvl-affect-app-functionality 01H7YJ35YM6RHCA6QP3MK0Y9J0=what-is-the-difference-between-lvl-and-gpreferrer" />
