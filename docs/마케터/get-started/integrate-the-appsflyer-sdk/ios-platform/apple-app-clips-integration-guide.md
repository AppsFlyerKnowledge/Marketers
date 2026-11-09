---
title: Apple App Clip 연동 가이드
metadata:
  keywords:
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2020-10-09T00:42:10Z'
  edited_at: '2026-10-14T10:32:35Z'
  id: 360014262358
  locale: ko
  section: iOS platform
  section_id: 6551263106577
  url: https://support.appsflyer.com/hc/ko/articles/360014262358
---
> **한눈에 보기:** App Clip을 사용하면 iOS 14 이상 버전을 사용하는 유저가 귀하의 앱에 빠르고 손쉽게 접근하고 경험할 수 있습니다. 앱스플라이어는 App Clip 어트리뷰션을 활성화하고 App Clip을 사용할 수 없는 유저(예: Android 유저)를 필요에 따라 리디렉션합니다.

<Image align="center" alt="app_clip_flow_3.png" src="https://files.readme.io/1a5ec7a6b8a061955742d8e79ba78fa0262c0609e1e801decc92300d6c24a774-360012832058.png" />

<div id="app-clip-integration" />

## App Clip 연동

* App Clip은 iOS 14 유저가 전체 앱을 다운로드할 필요 없이 빠르고 편리하게 앱 환경에 액세스할 수 있게 합니다.
* App Clip은 호출(예: QR 코드 또는 NFC 태그)이 있을 시, 설치 및 실행됩니다. **참고**: Safari Smart App Banners 및 Messages의 링크는 지원되지 않습니다.
* 앱스플라이어 SDK는 클릭, 인스톨, 인앱 이벤트, App Clip-투-전체 앱 인스톨의 App Clip 어트리뷰션에 필요합니다.
* 원링크는 SDK와 별개로 필요에 따라 사용자를 리디렉션합니다.
  * 앱을 설치하지 않은 유저:
    * iOS 14 이상에서는 App Clip으로 연결됩니다.
    * iOS 13 이전 버전 또는 Android의 경우 원링크의 설정에 따라 앱 스토어 등으로 리디렉션됩니다.
  * 앱이 설치된 유저들은 원링크에 설정된 유니버설 링크 또는 앱링크에 따라 앱으로 연결됩니다.

<div id="considerations" />

### 고려 사항

* App Clip의 크기는 최대 10MB 입니다. 앱스플라이어 SDK는 1.5MB 정도 입니다.
* 사용할 수 있는 광고 식별자가 없습니다.
* App Clip은 30일 동안 사용하지 않으면 OS에서 자동으로 삭제됩니다.

<div id="example" />

> 📄 **예시**
>
> 마크는 프랜차이즈 카페 브랜드의 마케터입니다. 고객이 줄을 서지 않고 몇 초 만에 편리하게 주문할 수 있도록, 그는 iOS 개발자에게 App Clip을 생성하도록 요청했습니다. 카페를 이용하는 고객들은 <Anchor target="_blank" href="https://developer.apple.com/sign-in-with-apple/">Apple 로그인</Anchor>으로 신원을 확인하고, 커피를 주문하고, <Anchor target="_blank" href="https://developer.apple.com/apple-pay/">Apple Pay</Anchor>로 결제하기만 하면 됩니다. 요청을 받은 개발자는 앱스플라이어 SDK를 추가하고 앱과 App Clip 모두에서 작동하는지 확인합니다.
>
> 마크는 원링크를 만들고 카페에 “줄 서지말고 주문하세요”라는 문구와 함께 QR 코드 게시 합니다.
>
> 고객이 QR 코드를 스캔하면:
>
> * OS 14 이상의 디바이스를 사용할 경우, App Clip이 열린 뒤 —해당 카페 지점이 표시되고 할인 쿠폰이 채워집니다.
> * 전체 앱이 이미 설치되어 있는 경우, 앱에서 커피 주문 페이지가 열립니다.
> * 앱이 없고 iOS 13 이하 또는 Android가 설치된 디바이스의 경우, 카페 앱의 앱 스토어 페이지가 열립니다.
>
> 마크는 앱스플라이어 대시보드와 리포트를 활용하여 App Clip에 얼마나 많은 클릭과 인스톨이 기록됐는지, 그리고 얼마나 많은 유저가 전체 앱을 다운로드하는지 확인합니다.

<div id="metrics-and-reporting" />

## 지표 및 리포팅

App Clip 분석 및 로데이터는 다음 표에 설명된 유저 활동에 따라 플랫폼에서 사용할 수 있습니다.

| 유저 행동 | 앱스플라이어 이벤트 | 개요 대시보드 및 분석 툴 | 로데이터 |
| --- | --- | --- | --- |
| 호출 (예: QR 코드) | 이벤트 없음 | 이벤트 없음 | 이벤트 없음 |
| 앱 카드를 클릭하고 App Clip 열림 | 클릭 및 인스톨이 호출 소스에 어트리뷰트됨 | <ul><li>클릭</li><li>인스톨</li></ul> | <Anchor target="_blank" href="/marketers/ko/docs/raw-data-field-dictionary#app::5a1697f1">app\_type=app\_clip</Anchor> |
| App Clip 사용 | <ul><li>[선택사항] 개발자가 인앱 이벤트를 전송</li><li>첫 번째 App Clip 실행 후 후속 오픈은 세션으로 계산됨</li></ul> | <ul><li>인앱 이벤트</li><li>세션</li></ul> | <ul><li>개발자가 보낸 인앱 이벤트</li><li><Anchor target="_blank" href="/marketers/ko/docs/raw-data-field-dictionary#app::5a1697f1">app\_type=app\_clip</Anchor></li></ul> |
| 전체 앱 다운로드 및 실행 | 인앱 이벤트 | 인앱 이벤트 이름= af\_app\_clip\_to\_full\_app | <ul><li>인앱 이벤트 이름= af\_app\_clip\_to\_full\_app</li><li><Anchor target="_blank" href="/marketers/ko/docs/raw-data-field-dictionary#app::5a1697f1">app\_type=full\_app</Anchor></li></ul> |
| 전체 앱을 지속적으로 사용 | [선택사항] 개발자가 인앱 이벤트를 전송 | 인앱 이벤트 | <ul><li>개발자가 보낸 인앱 이벤트</li><li><Anchor target="_blank" href="/marketers/ko/docs/raw-data-field-dictionary#app::5a1697f1">app\_type=full\_app</Anchor></li></ul> |

**코호트 대시보드**

<Anchor target="_blank" href="/marketers/ko/docs/cohort-and-retention-dashboard#trend-type%E2%80%94user-lifetime-performance">코호트 대시보드</Anchor>에서 App Clip 성과를 확인할 수 있습니다. 이 단계에서 다음을 수행할 수 있습니다:

* App Clip에서 전체 앱 인스톨까지 유저가 소요하는 시간을 확인할 수 있습니다.
* 인앱 전환 지표를 사용하여 다양한 캠페인의 성과를 비교할 수 있습니다.

<div id="app-clip-implementation" />

## App Clip 구현

App Clip을 개발하고 연동하기 위해 마케터와 iOS 개발자가 수행해야 하는 작업에 대해서는 아래를 참고해 주시기 바랍니다.

<div id="scope-of-work" />

#### 작업 범위

| **담당자**<ul><li>**마케터**:<ul><li>원링크 템플릿에서 Apple App Clip을 구성합니다.</li><li>원링크 링크를 Apple App Store Connect 포털에 삽입합니다.</li><li>앱스플라이어 대시보드 및 리포트에서 지표를 볼 수 있습니다.</li></ul></li><li>**iOS 개발자**:<ul><li>App Clip을 생성합니다.</li><li>앱스플라이어 SDK를 App Clip에 연동시킵니다.</li></ul></li></ul> |
| --- |
| **필수 조건**<ul><li>하나 이상의 앱과 연결된 앱스플라이어 계정</li><li>유니버설 링크가 포함된 원링크 템플릿과 전체 앱 유저를 디렉션하도록 설정된 원링크.<br />**권장 사항**: 여기서 사용되는 템플릿과 링크는 전체 앱이 없는 유저를 App Clip으로 보냅니다. 따라서 전체 앱이 없는 유저를 App Clip 대신 앱스토어로 보내려는 경우에는 별도의 템플릿과 커스텀 링크를 사용하는 것이 좋습니다.</li></ul> |

<div id="develop-app-clip" />

<Accordion title="App Clip 개발">

개발자가 앱용 App Clip을 생성하는 방법에 대한 전체 가이드는 <Anchor target="_blank" href="https://developer.apple.com/app-clips/">개발자용 Apple App Clip 가이드</Anchor>를 참조하십시오.

App Clip의 사용법과 전체 앱과의 연동을 보여주는 간단한 샘플 앱을 보려면, <Anchor target="_blank" href="https://www.appsflyer.com/resources/others/apple-app-clips/">앱스플라이어 App Clip 가이드</Anchor>를 참조하십시오.

</Accordion>

<div id="integrate-sdk" />

<Accordion title="SDK 연동">

* 클릭, 인스톨, 인앱 이벤트, App Clip-투-전체 앱 설치의 앱스플라이어 어트리뷰션을 위해서는 SDK가 필요합니다.
* 원링크는 SDK 연동과는 별개로 유저를 리디렉션합니다.

**SDK를 설치하고 전체 앱 SDK를 구성하려면**:

iOS 개발자에게 다음 링크를 보내고 관련 가이드를 따르도록 안내하시기 바랍니다:

* <Anchor target="_blank" href="https://dev.appsflyer.com/docs/app-clip-sdk-integration">App Clip에 SDK 연동</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/docs/app-clip-to-full-app-install">App Clip-투-전체 앱 인스톨 어트리뷰션 구성</Anchor>
* [선택 사항] 전체 앱에 대해 아직 인앱 이벤트를 측정하고 있지 않거나 App Clip에 다른 인앱 이벤트를 사용하려는 경우, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events">인앱 이벤트를 설정하십시오.</Anchor>

</Accordion>

<div id="configure-onelink" />

<Accordion title="원링크 설정">

**선행 조건:**

* iOS 유니버설 링크가 설정된 전체 앱용 <Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template#원링크-템플릿-만들기">원링크 템플릿</Anchor>
* <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#캠페인을-위한-원링크-링크-생성하기">원링크 링크</Anchor>
* **권장 사항**: 여기서 사용되는 템플릿과 링크는 전체 앱이 없는 유저를 App Clip으로 보냅니다. 따라서 이러한 유저를 App Clip 대신 앱스토어로 보내려는 경우에는 별도의 템플릿과 사용자 지정 링크를 사용하는 것이 좋습니다.

**App Clip용 원링크 템플릿을 구성하려면**:

1. **앱스플라이어 대시보드에서** 인게이지 **> 원링크 관리로 이동합니다.**
2. 유저를 전체 앱으로 디렉션하는 데 사용되는 **원링크 템플릿을** 선택하세요.
3. 원링크 템플릿에 유니버설 링크가 구성되어 있는지 확인하세요. (유니버설 링크를 추가하려면 <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">여기</Anchor>를 참조하세요.)
4. **저장**을 클릭하세요.  
   App Clip을 지원하도록 AASA 파일이 업데이트됩니다.
5. **앱스플라이어 대시보드에서** 인게이지 **> 원링크 관리로 이동합니다.**
6. 1&#126;4단계에서 구성한 템플릿을 기반으로 유저를 App Clip으로 안내하는 데 사용하는 **원링크 커스텀 링크**를 선택합니다.
7. 미디어 소스(pid)를 지정했는지 확인하세요.  
   미디어 소스는 URL (예: **pid=chartboost\_int**)에 지정되거나 링크 내에 포함되어야 합니다.

**앱스플라이어 원링크에서 App Clip이 활성화되었는지 확인하려면:**

1. URL을 생성하여 연결된 파일을 가져오세요. URL은 원링크 템플릿에서 가져온 도메인을 추가하여 생성됩니다. `/.well-known/apple-app-site-association`
   예: `coffee.onelink.me/.well-known/apple-app-site-association`.
2. 연결된 파일의 URL로 이동합니다.  
   apple-app-site-association 파일이 자동으로 다운로드됩니다.
3. 텍스트 편집기(예: 메모장)를 사용하여 apple-app-site-association 파일을 엽니다.
4. 파일에 “**appclips**”라는 단어가 포함되어 있고 번들 ID가 “**.Clip**”으로 끝나는지 확인하십시오. 예시:  

   ```java
   "appclips": {
       "apps": [
         "ABCD1234.id.your.app.Clip",
         ...
       ]
   ...
   }
   ```

   위의 사항이 모두 확인됐다면, 앱스플라이어에서 App Clip을 성공적으로 설정했다는 뜻이며, 동일한 서브 도메인이 설정된 모든 원링크 템플릿 App Clip이 구현된 것입니다.

</Accordion>

<div id="configure-app-store-connect" />

<Accordion title="App Store Connect 설정">

**선행 조건**: [App Clip을 위한 원링크 템플릿 구성](/docs/apple-app-clips-integration-guide#configure-onelink) 완료

**원링크와 연동되도록 App Clip을 구성하려면**:

1. App Store Connect 내 귀하의 앱 페이지에서 **Build** > **Domain Status**로 이동합니다.
2. 원링크 도메인이 **Build Domains**에 표시되고 **Cache Status**와 **Debug Status**가 모두 “검증”되었는지 확인하십시오.
3. **앱스플라이어 대시보드에서** 인게이지 **> 원링크 관리로 이동합니다.**
4. 사용하려는 링크의 **조치** 아이콘 위에 마우스를 놓고 **URL 가져오기**를 클릭합니다.
5. 짧은 URL을 기록합니다. (또는 긴 URL의 prefix를 기록합니다.)
6. App Store Connect의 앱 페이지에서 **App Clip** > **Edit Advanced Experiences** > **+Add** > **Next**로 이동합니다.
7. **App Clip Experience URL**에 5단계에서 기록한 원링크 사용자 지정 URL을 붙여넣습니다.  
   **참고**: 기본 맞춤 URL 뒤에 쿼리 파라미터를 추가할 수 있지만 경로를 변경할 수는 없습니다.
8. **다음**을 클릭합니다.  
   이제 App Clip이 원링크와 함께 작동하도록 구성되었습니다. App Store Connect 설정에 관한 추가 지침은 <Anchor target="_blank" href="https://developer.apple.com/documentation/app_clips/configuring_your_app_clip_s_launch_experience">Apple Developer</Anchor>에서 확인할 수 있습니다.

</Accordion>

<div id="testing" />

<Accordion title="테스트">

**선행 조건**: 전체 앱이 설치되지 않은 iOS 14 버전의 <Anchor target="_blank" href="/marketers/ko/docs/registering-test-devices">등록된 테스트 디바이스</Anchor>

**원링크/App Clip 연동을 테스트하려면:**

1. **앱스플라이어 대시보드에서** 인게이지 **> 원링크 관리로 이동합니다.**
2. 테스트하고자 하는 링크의 **액션** 아이콘을 클릭하고 **URL 가져오기**를 클릭합니다.
3. 디바이스로 QR 코드를 스캔합니다.  
   App Clip 카드가 디바이스에 표시되면, 원 링크/App Clip 연동이 제대로 설정되었음을 나타냅니다.

</Accordion>

<div id="traits-and-limitations" />

## 특징 및 제약 사항

<div id="traits-and-limitations::26141033" />

<Accordion title="특징 및 제약 사항">

| 특징/제한 사항 | 설명 |
| --- | --- |
| 호출 메서드 | <ul><li>Safari Smart App Banners 및 Messages의 링크는 지원되지 않습니다.</li></ul> |
| SKAdNetwork | SKAdNetwork 기능은 사용할 수 없습니다. 따라서 App Clip 인스톨은 SKAdNetwork 대시보드에서 오가닉으로 표시됩니다. |
| 원링크 | 원링크 커스텀 링크당 하나의 advanced App Clip experience만 허용됩니다. 즉, App Store Connect에서 원링크로의 경로를 더 추가할 수 없습니다. |
| Protect360 | Protect360은 App Clip을 지원하지 않습니다. |

</Accordion>

<div id="see-also" />

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="https://www.appsflyer.com/resources/guides/ios-14-app-clips/">앱스플라이어의 Apple App Clip용 어트리뷰션 솔루션</Anchor>

<div data-zendesk-anchors="app-clip-integration=app-clip-%EC%97%B0%EB%8F%99 h_01HDNZQTCBXY0Y3QYCBNVH7EAW=app-clip-%EC%97%B0%EB%8F%99 considerations=%EA%B3%A0%EB%A0%A4-%EC%82%AC%ED%95%AD h_01HDNZQTCBPJWY6H2M452QH644=%EA%B3%A0%EB%A0%A4-%EC%82%AC%ED%95%AD h_01HDNZQTCB7NB682YTSMNCJSDP=%EC%98%88%EC%8B%9C metrics-and-reporting=%EC%A7%80%ED%91%9C-%EB%B0%8F-%EB%A6%AC%ED%8F%AC%ED%8C%85 h_01HDNZQTCBNG3TYRAA7GVPF39P=%EC%A7%80%ED%91%9C-%EB%B0%8F-%EB%A6%AC%ED%8F%AC%ED%8C%85 app-clip-implementation=app-clip-%EA%B5%AC%ED%98%84 h_01HDNZQTCBJK7SB96G8A4DHR34=app-clip-%EA%B5%AC%ED%98%84 scope-of-work=%EC%9E%91%EC%97%85-%EB%B2%94%EC%9C%84 h_01HDNZQTCB1AKW9QFRRM9VVN4D=%EC%9E%91%EC%97%85-%EB%B2%94%EC%9C%84 h_01HDNZQTCBN04J3GA8H64V70YY=develop-app-clip h_01HDNZQTCBHHENFYJK7MFJTZ14=integrate-sdk h_01HDNZQTCBN9QV4MZAAWMV164Y=configure-onelink h_01HDNZQTCC6F8TTM2FRQK6DB2E=configure-app-store-connect h_01HDNZQTCCN2BX9NZ4027ZCEFB=testing traits-and-limitations=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD h_01HDNZQTCCMW2YNK1G34EBM7DM=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD h_01HDNZQTCCV0S78NRK00PK4S0J=traits-and-limitations::26141033 h_01HDNZS83EKJNZGG1QEVS9RMCA=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
