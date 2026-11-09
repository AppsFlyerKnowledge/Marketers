---
title: 마케터를 위한 SDK 연동 테스트
metadata:
  keywords:
    - Testing
    - SDK
    - Advertisers
    - Debug
    - Debugging
    - redirects test
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2018-11-12T14:15:08Z'
  edited_at: '2026-10-14T10:33:57Z'
  id: 360001559405
  locale: ko
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/ko/articles/360001559405
---
> **한눈에 보기:** 요약: 안드로이드 또는 iOS 앱과 앱스플라이어 연동을 테스트합니다.

<div id="overview" />

## 개요

SDK 연동이 완료되면 SDK가 앱스플라이어 서버와 성공적으로 연결되어 있는지 확인할 수 있습니다. 마케터는 두 가지 테스트 방법 중에서 하나를 선택할 수 있습니다.

* **SDK 연동 테스트**페이지를 사용하여 다음 항목에 대한 테스트를 수행할 수 있습니다.
  * <Image alt="" src="https://files.readme.io/16b90e430d7beea0eaa1530130d094d590c0a202f6c6ad298a88aac9508fee7a-31828933593745.png" width="30px" />앱 테스트 중 발생한 [이벤트를 실시간으로 모니터링](#view-live-events)
  * [논오가닉 인스톨 테스트](#test-nonorganic-installs)
  * [딥링크(리타겟팅) 테스트](#test-deep-links-retargeting)
* [어트리뷰션 링크를 사용한 테스트](#어트리뷰션-링크를-사용한-테스트)

개발자는 개발 환경에서 연동 테스트를 수행할 수 있습니다. 자세한 내용은 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integration-testing">Dev Hub의 연동 테스트 문서</Anchor>를 확인하세요.

CTV 앱도 테스트 가능합니다. 자세한 내용은 [CTV 테스트](#ctv-테스트) 문서를 확인하세요.

<div id="note" />

<div id="testing-using-the-sdk-integration-tests-page" />

## SDK 연동 테스트 페이지를 사용한 테스트

**SDK 연동 테스트** 페이지를 통해 앱에서 발생하는 실시간 라이브 이벤트, 인스톨 및 인앱 이벤트를 확인할 수 있습니다. 뿐만 아니라 논오가닉 설치, 인앱 이벤트, 딥링킹(리타겟팅)을 테스트하고, 프로젝트 중 생길 수 있는 연동 문제를 확인하는 것도 가능합니다. 기존의 인앱 이벤트 테스트 툴은 라이브 이벤트 뷰어로 대체됩니다.

**iOS에만 해당되는 사항**: SDK 연동 테스트 페이지는 ATT를 구현하는 iOS 앱에만 적용됩니다. [여기](https://dev.appsflyer.com/hc/docs/testing-ios#apps-that-dont-implement-att)에 설명된 절차에 따라 비 ATT 앱을 테스트할 수 있습니다.

<div id="prepare-a-test-device" />

### **테스트 장치 준비**

1. 앱이 설치되지 않은 디바이스(안드로이드 또는 iOS)를 준비합니다. 필요한 경우 디바이스에서 앱을 삭제합니다.
2. <Anchor target="_blank" href="/marketers/ko/docs/registering-test-devices">준비한 디바이스를 테스트 장치로 등록합니다.</Anchor>

<div id="perform-the-integration-tests" />

<div id="note-1" />

### 연동 테스트 수행하기

**SDK 통합 테스트** 페이지에서 다음과 같은 세 가지 테스트를 실행할 수 있습니다.

<div id="view-live-events" />

<Accordion title="라이브 이벤트 보기">

라이브 이벤트 뷰어는 인스톨 이벤트 및 기타 인앱 이벤트와 같이 SDK에서 앱스플라이어로 전송된 실시간 데이터를 보여주는 테스트 툴입니다. 각 이벤트에 대해 이벤트 로그 및 세부 정보를 볼 수 있습니다.

**라이브 이벤트 뷰어에서 이벤트를 보려면:**

1. 앱스플라이어의 사이드 메뉴에서 **설정** > **SDK 연동 테스트**를 선택합니다.

   <Image align="center" alt="" src="https://files.readme.io/c4f39fb2ddf1de510d9a03e292b05fab444600a8584c0a23e7b3e613c7077799-31828925846033.png" />
2. **라이브 이벤트** 클릭

   <Image align="center" alt="" src="https://files.readme.io/6ec1edba14e51bb27babf80d2d6f4873dbaa5113752217b4fb13399f7a1c61f1-31828925849489.png" />
3. **앱** 목록에서 테스트할 앱을 선택합니다.
4. **테스트 기기** 목록에서, 앱 테스트에 사용할 디바이스를 선택합니다. 테스트 장치가 없는 경우, **테스트 장치 추가** 링크를 클릭하여 등록할 수 있습니다.
5. **계속하기**를 클릭하여 앱 이벤트 기록을 시작합니다.
6. 앱을 실행하고 상호 작용하여 세션 및 인앱 이벤트를 생성합니다.

   <Image align="center" alt="" src="https://files.readme.io/72b8822197dc626c1b28a9f8d43bb3c1a91f99e600ae0d8d1f74829bc62dcce6-31828933607313.png" />
7. 이벤트 항목을 클릭하면 오른쪽 패널에서 이벤트 세부 정보를 볼 수 있습니다.
8. 이벤트 기록을 중지하려면 **중지**를 클릭하세요. 다시 계속하려면 **시작**을 클릭하세요.

</Accordion>

<div id="test-nonorganic-installs" />

<Accordion title="논오가닉 인스톨 테스트">

**논오가닉 인스톨을 테스트하려면:**

1. 앱스플라이어의 사이드 메뉴에서 **설정** > **SDK 연동 테스트**를 선택합니다.

   <Image align="center" alt="" src="https://files.readme.io/c4f39fb2ddf1de510d9a03e292b05fab444600a8584c0a23e7b3e613c7077799-31828925846033.png" />
2. **논오가닉 인스톨** 테스트를 클릭합니다.

   <Image align="center" alt="" src="https://files.readme.io/34440ab6d328e2d519f759f3c2a1b17dbcbee55af32b47bdbd52bb9f537c6735-31828933612177.png" />
3. **앱** 목록에서 테스트할 앱을 선택합니다.
4. **테스트 기기** 목록에서, 앱 테스트에 사용할 디바이스를 선택합니다. 테스트 장치가 없는 경우, **테스트 장치 추가** 링크를 클릭하여 등록할 수 있습니다.
5. 테스트된 앱이 테스트 장치에 설치되어 있으면 제거합니다.
6. **“테스트한 디바이스에서 앱을 삭제했습니다”** 선택란에 체크합니다.
7. **계속**을 클릭하고 각 마법사 단계를 따릅니다.

**앱이 논오가닉 인스톨을 기록하지 않는 경우, 다음과 같은 이유 때문일 수 있습니다.**

* IDFA를 사용할 수 있지만 테스트 장치가 <Anchor target="_blank" href="/marketers/ko/docs/registering-test-devices#ios-테스트-디바이스-등록">테스트 장치 페이지에서 IDFA 식별자로 등록되지 않았습니다</Anchor>.
* 테스트 장치에 테스트 앱 외에 2개 이상의 앱이 설치되어 있지만 테스트 장치가 <Anchor target="_blank" href="/marketers/ko/docs/registering-test-devices#ios-테스트-디바이스-등록">테스트 장치 페이지의 IDFV에 등록되지 않았습니다</Anchor>.
* 오가닉 인스톨이 기록되었습니다.
* SDK를 포함하지 않는 앱 버전에서 테스트가 수행되었습니다.

연동 오류가 나타나는 경우, 개발자에게 문의하십시오.

</Accordion>

<div id="test-deep-links-retargeting" />

<Accordion title="딥링크(리타겟팅) 테스트">

**시작하기 전에:**

* 테스트 앱을 3번 이상 실행합니다.
* 딥링킹(리타겟팅)을 테스트하려면 원링크가 앱에 정의되어 있어야 합니다. 자세한 정보는 <Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template">원링크 설정 가이드</Anchor>를 참조하십시오.
* <Anchor target="_blank" href="/marketers/ko/docs/app-settings#reengagement-attribution">리타겟팅</Anchor>이 켜져 있는지 확인하십시오.

**딥링크를 테스트하려면:**

1. 앱스플라이어의 사이드 메뉴에서 **설정** > **SDK 연동 테스트**를 선택합니다.

   <Image align="center" alt="Keyboard Maestro Engine 2024-10-06 10.00.47.png" src="https://files.readme.io/c4f39fb2ddf1de510d9a03e292b05fab444600a8584c0a23e7b3e613c7077799-31828925846033.png" width="2895px" />
2. **리타겟팅**을 클릭합니다.

   <Image align="center" alt="" src="https://files.readme.io/7c5eb6870e8d4c25a817f6c2895163b699e0a4972a6cc675b94396c386288d72-31828925858961.png" />
3. **앱** 목록에서 테스트할 앱을 선택합니다.
4. **테스트 기기** 목록에서, 앱 테스트에 사용할 디바이스를 선택합니다. 테스트 장치가 없는 경우, **테스트 장치 추가** 링크를 클릭하여 등록할 수 있습니다.
5. **계속**을 클릭하고 각 마법사 단계를 따릅니다.

</Accordion>

<div id="note-3" />

<div id="note-2" />

<div id="testing-using-attribution-links" />

## 어트리뷰션 링크를 사용한 테스트

다음 섹션에서는 어트리뷰션 링크로 인스톨을 테스트하기 위해 거쳐야 하는 절차에 대해 설명합니다. 앱이 배포 전 즉, Google Play Store 또는 Apple 앱 스토어에 배포되지 않은 경우에도 이러한 테스트를 수행할 수 있습니다.

<div id="test-install-attribution" />

<Accordion title="인스톨 어트리뷰션 테스트">

인스톨 테스트를 통해 앱스플라이어 SDK가 인스톨을 다양한 미디어 소스에 올바르게 어트리뷰트하고 있는지 확인할 수 있습니다.

**인스톨 어트리뷰션 테스트 방법:**

1. 다음 링크(안드로이드 또는 iOS)를 복사하고 아래와 같이 수정합니다.

   1. **app\_id** 값: 앱스플라이어에 앱 ID를 추가합니다.
   2. **pid** 파라미터: 인스톨이 어트리뷰트될 미디어 소스의 이름을 지정합니다.
   3. **c** 파라미터: 캠페인의 이름을 지정합니다.
   4. 써드 파티 안드로이드 스토어의 앱을 테스트하는 경우, 어트리뷰션 링크에 <Anchor target="_blank" href="/marketers/ko/docs/set-up-multi-store-android-attribution#single-dashboard-attribution-links">af\_r parameter</Anchor>를 추가합니다.
   5. GAID, IDFA 또는 IDFV를 귀하의 디바이스 식별자로 변경합니다.

   <Tabs>
   <Tab title="안드로이드">

   ```http
   https://app.appsflyer.com/<app_id>?pid=Test&c=Test&advertising_id=<GAID>
   ```

   </Tab>

   <Tab title="iOS">

   IDFA

   ```http
   https://app.appsflyer.com/<app_id>?pid=Test&c=Test&idfa=<IDFA>
   ```

   IDFV

   ```http
   https://app.appsflyer.com/<app_id>?pid=Test&c=Test&idfv=<IDFV>
   ```

   </Tab>
   </Tabs>

   다음은 특정 값을 가진 어트리뷰션 링크의 예입니다.

   <Tabs>
   <Tab title="안드로이드">

   ```

   ```

   ```http
   https://app.appsflyer.com/com.my.app?pid=Test&c=Test&advertising_id=12345f9*-eba*-421*-876*-7654ac67876*
   ```

   </Tab>

   <Tab title="iOS">

   ```

   ```

   ```http
   https://app.appsflyer.com/id123456789?pid=Test&c=Test&idfa=1A2B****-9128-4***-123*-04E***654321
   ```

   </Tab>
   </Tabs>

   > 📘 **참고**
   >
   > <Anchor target="_blank" href="/marketers/ko/docs/registering-test-devices">테스트 장치 등록</Anchor>을 하지 않고 iOS 앱을 테스트하는 경우, Fraud 360에 의해 테스트 클릭이 프로드로 표시될 수 있습니다.
   >
   > 해당 이벤트가 프로드로 감지되는 것을 방지하려면, 링크에 다음 쿼리 파라미터를 추가하세요. `pid=”ios_testing”`

2. 업데이트된 링크를 복사하여 테스트 장치로 보낸 다음 링크를 클릭합니다.

   > 📘 **참고**
   >
   > iOS에서는 iMessenger 또는 이메일을 사용하여 링크를 디바이스로 보냅니다. iOS Notes 앱에 링크를 붙여넣기 하지 마시고, 링크를 클릭하세요. 링크를 붙여넣기하는 경우, 링크가 끊어질 수 있습니다.

3. 다음 중 하나를 수행합니다.

   * 앱이 배포되어 있다면, 설치를 진행하십시오.
   * 앱이 아직 배포 전인 경우, 다음 메시지가 표시됩니다. "*The app you are looking for is not available in the market yet.*"이라는 메시지가 뜬다면 정상입니다. 앱이 배포되지 않았기 때문에 어트리뷰션 링크가 앱 스토어로 연결되지 않습니다. 그러나 어트리뷰션 링크는 어트리뷰션 목적으로 여전히 유효하며 다음과 같이 앱을 설치해야 합니다.
     * **안드로이드의 경우:** APK 파일(또는 개발자용 Android Studio)로 설치
     * **iOS의 경우:** TestFlight(또는 개발자용 Xcode)로 설치

   **테스트**라고 불리는 미디어 소스 아래에 테스트 캠페인에 어트리뷰트된 인스톨이 표시됩니다. 해당 인스톨이 앱의 대시보드에 표시될 때까지 30여 분 정도 시간이 소요됩니다.

   <Image align="center" alt="Test_Install_Attribution_Link" src="https://files.readme.io/1771da27f7b8c5334d68c3d7c8361e91e0e35a3a08abf60e3d711f83de9ad22d-31828925861265.png" />

<div id="tip" />

> 👍 **팁**
>
> 다음은 테스트 결과를 확인할 수 있는 다른 대체 방법들에 대해 설명합니다.
>
> * 로데이터 리포트에 접근 권한이 있다면, <Anchor target="_blank" href="/marketers/ko/docs/raw-data-reporting-overview">인스톨 로데이터 리포트</Anchor>를 다운로드하십시오. 리포트를 다운로드하는 데 몇 분 정도 소요될 수 있습니다. **리포트 다운로드 방법:**
>   1. 앱스플라이어의 사이드 메뉴에서 **리포트** > **로데이터 내보내기**를 선택합니다.
>   2. **유저 유입(논오가닉)** 목록에서 **인스톨**을 클릭한 후 리포트를 다운로드하십시오.
> * 디버그 로그에 액세스가 가능하다면, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/gcd-get-data">전환 데이터 API</Anchor>를 사용하여 특정 인스톨에 대한 어트리뷰션 결과를 불러올 수 있습니다.

</Accordion>

<div id="test-inapp-events-attribution" />

<Accordion title="인앱 이벤트 어트리뷰션 테스트">

인앱 이벤트를 테스트하면 이벤트와 관련된 수익이 표시되며, 인앱 이벤트가 인스톨을 생성하는 미디어 소스에 어트리뷰트되는지 확인할 수 있습니다.

**인앱 이벤트의 어트리뷰션 테스트 방법:**

1. 앱을 실행하고 인앱 이벤트를 생성하세요.
2. 앱의 액티비티 대시보드를 열고 이벤트가 생성되어 있는지 확인하세요.  
   이벤트, 수익 (관련 있는 경우), 관련 미디어 소스를 확인할 수 있습니다. 해당 이벤트가 대시보드에 표시될 때까지 60&#126;70분 정도 소요됩니다.

**팁!** 이벤트가 올바르게 어트리뷰트되었는지 확인하려면 <Anchor target="_blank" href="/marketers/ko/docs/raw-data-reporting-overview">인앱 이벤트 로데이터 리포트</Anchor> 다운로드를 권장드립니다. 리포트를 다운로드하는 데 몇 분 정도 소요될 수 있습니다.

**리포트 다운로드 방법:**

1. 앱스플라이어의 사이드 메뉴에서 **Report** > **Raw Data Export** 를 선택합니다.
2. **로데이터 리포트** 섹션에서 인앱 이벤트 로데이터 리포트를 다운로드합니다.

</Accordion>

<div id="test-onelink" />

<Accordion title="원링크 테스트">

원링크를 사용하면 안드로이드와 iOS 모두에 단일 어트리뷰션 링크를 설정할 수 있습니다. 원링크는 사용자의 디바이스를 인식하여 관련 앱스토어로 리디렉션합니다.

또한 원링크를 통해 딥링킹이 가능합니다. 딥링킹을 통해, 맞춤형 콘텐츠를 제공함과 동시에 구체적인 앱 활동 내에서 앱을 오픈할 수 있습니다.

자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#testing">원링크 URL 테스트</Anchor>에 대한 가이드를 참조하십시오.

</Accordion>

<div id="note-4" />

<div id="testing-retargeting-using-attribution-links" />

## 어트리뷰션 링크를 사용한 리타겟팅 테스트

다음은 리타겟팅 어트리뷰션을 테스트하기 위해 따라야 하는 절차에 대해서 설명합니다.

<div id="about-retargeting-tests" />

<Accordion title="리타케팅 테스트 정보">

리타겟팅 어트리뷰션은 유저가 리타겟팅 어트리뷰션 링크를 클릭하여 리타겟팅 캠페인에 참여할 때 발생합니다. 이로 인해 리어트리뷰션 또는 리인게이지먼트 이벤트가 발생합니다. 자세한 정보는 <Anchor target="_blank" href="/marketers/ko/docs/retargeting-attribution-guide">리타겟팅 어트리뷰션 가이드</Anchor>를 참조하십시오.

리타겟팅 테스트에는 다음이 포함됩니다.

* [**리어트리뷰션의 경우:**](/docs/testing-the-sdk-integration-for-marketers#test-reattribution) 앱을 제거하고 다시 설치합니다. 그런 다음, 대시보드에서 인스톨이 기록되었는지 여부를 확인합니다.
* [**리인게이지먼트의 경우:**](/docs/testing-the-sdk-integration-for-marketers#test-reengagement) 리타겟팅 어트리뷰션 링크 또는 딥링크를 클릭했을 때, 리인게이지먼트가 올바른 미디어 소스에 어트리뷰트되는지를 확인합니다.

</Accordion>

<div id="prerequisites-to-run-retargeting-tests" />

<Accordion title="리타겟팅 테스트 실행의 전제 조건">

리타겟팅 테스트 실행 전에 다음 설정이 필요합니다.

* 테스트하려는 앱에 대해 리타겟팅이 활성화되어야 합니다.
* 앱 전용 링크를 생성하거나 원링크 커스텀 링크를 검색합니다. 해당 링크에는 리타겟팅 파라미터가 포함되어야 합니다.

**리타겟팅 테스트 설정 방법:**

1. 앱 설정에서 리타겟팅을 활성화합니다.

   앱 대시보드에서 **앱 설정**을 클릭하고 **리타겟팅 어트리뷰션 활성화**를 켭니다.

   <Image align="center" alt="Set_Reattribution_window" src="https://files.readme.io/1fe0c8c4add90c75237b0c5c97b6ff26d8f08ff95bd952912ef746fdec2e9f3d-31828933628561.png" />
2. 다음 중 하나를 수행합니다.
   * 앱 전용 어트리뷰션 링크를 생성합니다. 해당 링크에는 리타겟팅 파라미터와 `is_retargeting=true`, 광고 ID가 반드시 포함되어야 합니다. GAID, IDFA 또는 IDFV를 보려면, <Anchor target="_blank" href="/marketers/ko/docs/registering-test-devices">테스트 장치 등록하기</Anchor> 지침을 따르세요.    
     다음은 어트리뷰션 분석 링크에 안드로이드 전용 파라미터가 디바이스 식별자(GAID)로 포함되어 있는 예입니다. IDFA 또는 IDFV와 같은 다른 디바이스 식별자 파라미터를 추가하는 방법에 대해서는 <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#ios-전용-파라미터">어트리뷰션 링크 구조 및 파라미터</Anchor>를 참조하십시오.

     ```

     ```

     ```http
     https://app.appsflyer.com/<app_id>?pid=Test&c=Test&is_retargeting=true&advertising_id=<GAID>
     ```
   * <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#캠페인을-위한-원링크-링크-생성하기">원링크 템플릿</Anchor>에서 <Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template#원링크-템플릿-만들기">커스텀 링크의 긴URL</Anchor>을 가져옵니다. <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">리타겟팅 캠페인</Anchor>이 활성화되어 있는지 확인하세요. 아래 이미지를 통해 커스텀 긴 URL의 예시를 확인하세요. ![Testing_LongLink_en-us.png](https://files.readme.io/19c706b0cc11b83a5cb08d51b3418654c6fa1e597ee7ff9e631db21c33c00b82-31828933632401.png)

이제 리어트리뷰션 및 리인게이지먼트 테스트를 진행할 수 있습니다.

</Accordion>

<div id="test-reattribution" />

<Accordion title="리어트리뷰션 테스트">

**시작하기 전에:**

* 리타겟팅 테스트 설정에 대한 [지침](/docs/testing-the-sdk-integration-for-marketers#prerequisites-to-run-retargeting-tests)을 따르십시오.
* **등록되지 않은** 테스트 장치를 사용해야 합니다.

**리어트리뷰션 테스트 방법:**

1. 디바이스에서 앱을 삭제합니다. 앱을 방금 설치했다면 몇 분 정도 기다려 주세요.
2. 미리 생성한 [어트리뷰션 링크](/docs/testing-the-sdk-integration-for-marketers#prerequisites-to-run-retargeting-tests) (원링크 템플릿을 활용한 앱 전용 어트리뷰션 링크 또는 커스텀 롱 링크)를 복사하여 테스트 장치로 보낸 다음 링크를 클릭합니다.

   > 📘 **참고**
   >
   > iOS에서는 iMessenger 또는 이메일을 사용하여 링크를 디바이스로 보냅니다. iOS Notes 앱에 링크를 붙여넣기 하지 마시고, 링크를 클릭하세요. 붙여넣기 하는 경우, 링크가 끊어질 수 있습니다.

3. 다음 중 하나를 수행합니다.
   * 앱이 배포되어 있다면, 설치를 진행하십시오.
   * 앱이 아직 배포 전인 경우, 다음의 설치 방법을 따르십시오.
     * **안드로이드의 경우**: Android Studio 또는 APK 파일로 설치합니다.
     * **iOS의 경우:** TestFlight를 통해 설치합니다.
4. 앱의 대시보드를 열고 **유형 보기** 박스에서 **리타겟팅**을 선택합니다.
5. **어트리뷰션 유형** 박스에서 **리어트리뷰션**을 선택합니다.

   미디어소스 및 캠페인에 기여된 인스톨을 확인할 수 있습니다. 리타겟팅된 인스톨이 대시보드에 표시될 때까지 30여 분 정도 시간이 소요될 수 있습니다.

   <Image align="center" alt="Testing_SDK_Reattribution" src="https://files.readme.io/c5c59709b199262cbefd5cd70ee9fe0db2c788612a8ae6b598c7b2188b696345-small-31828925870609.png" />

<div id="tip-1" />

> 👍 **팁**
>
> 다음은 테스트 결과를 확인할 수 있는 다른 대체 방법들에 대해 설명합니다.
>
> * 로데이터 리포트에 액세스할 수 있는 경우, <Anchor target="_blank" href="/marketers/ko/docs/raw-data-reporting-overview">로데이터 전환 리포트</Anchor>를 다운로드하십시오. 리포트를 다운로드하는 데 몇 분 정도 소요될 수 있습니다. **리포트 다운로드 방법:**
>   1. 앱스플라이어의 사이드 메뉴에서 **리포트** > **로데이터 내보내기**를 선택합니다.
>   2. **리타겟팅** 목록에서 **전환(리인게이지먼트 및 리어트리뷰션)** 을 클릭하여 리포트를 다운로드하십시오.
> * 디버그 로그에 접근 권한이 있다면, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_app-id-2">SDK 연동 테스트 API</Anchor>를 사용하여 특정 인스톨에 대한 어트리뷰션 결과를 가져올 수 있습니다.

</Accordion>

<div id="test-reengagement" />

<Accordion title="리인게이지먼트 테스트">

**시작하기 전에:**

* 리타겟팅 테스트 설정에 대한 [지침](/docs/testing-the-sdk-integration-for-marketers#prerequisites-to-run-retargeting-tests)을 따르십시오.
* 테스트를 위해 전환 사이의 최소 시간을 **없음**으로 설정합니다. 이를 통해 테스트 중에 모든 리인게이지먼트 전환을 기록하고 어트리뷰트할 수 있습니다.
* 앱이 테스트 장치에 설치되어 있고, 몇 차례 실행된 적이 있는지 확인하십시오. 앱을 방금 설치했다면 몇 분 정도 기다려 주세요.

**리인게이지먼트(direct deep linking) 테스트 방법:**

앱이 <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">딥링킹</Anchor>을 지원하도록 구성되었는지 확인한 후, <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#testing">다음 절차</Anchor>를 따라 테스트하세요.

**리인게이지먼트(indirect deep linking) 테스트 방법:**

1. 미리 생성한 [어트리뷰션 링크](/docs/testing-the-sdk-integration-for-marketers#prerequisites-to-run-retargeting-tests) (원링크 템플릿을 활용한 앱 전용 어트리뷰션 링크 또는 커스텀 롱 링크)를 복사합니다.
2. 테스트 장치에 대한 링크를 보낸 다음 링크를 클릭합니다.
3. 앱을 열기 위해서는 다음 중 하나를 수행합니다.

   * 앱 스토어에서 **열기**를 클릭합니다.
   * 디바이스에서 앱을 실행합니다.

   대시보드에서 미디어소스 및 캠페인에 어트리뷰트된 리인게이지먼트가 표시됩니다. 리인게이지먼트가 나타날 때까지 최대 30분 정도 기다리십시오.

   <Image align="center" alt="Testing_SDK_Re-engagement" src="https://files.readme.io/5b64b671c8071f871d9835e8df4d89c18d06c85fe996f7227b6ddf429552fccd-small-31828933643153.png" />

**팁!** 리인게이지먼트가 올바른 미디어 소스에 어트리뷰트되는지 확인하려면 전환 로데이터 리포트를 다운로드하는 방법도 있습니다. 리포트를 다운로드하는 데 몇 분 소요될 수 있습니다.

**리포트 다운로드 방법:**

1. 앱스플라이어의 사이드 메뉴에서 **리포트** > **로데이터 내보내기**를 선택합니다.
2. **리타겟팅** 섹션에서 **전환(리인게이지먼트 및 리어트리뷰션)** 리포트를 다운로드합니다.

</Accordion>

<div id="testing-organic-installs" />

## 오가닉 인스톨 테스트

먼저 오가닉 인스톨 테스트부터 시작할 것을 권장합니다.

**오가닉 인스톨 테스트 방법:**

1. 등록된 테스트 장치에 앱을 설치하십시오.
2. 앱을 실행합니다.

앱의 대시보드에 신규 오가닉 인스톨이 표시됩니다. 인스톨이 표시될 때까지 최대 30분 정도 기다리십시오.

<Image align="center" alt="" src="https://files.readme.io/49c242957324516ba93d6c5ebfa338ec19b05820bcf619d8c39d6f7e4ada9bae-31828925882001.png" />

<div id="traits-and-limitations" />

<div id="note-5" />

<div id="testing-ctv" />

## CTV 테스트

특별 테스트 사례는 다음과 같습니다.

* **안드로이드 TV:** SDK는 안드로이드 기반 스마트 TV와 호환됩니다. 마케터 또는 팀원은 이 도움말 문서의 절차에 따라 TV 앱을 테스트할 수 있습니다.
* **Apple TV (tvOS):** SDK는 Apple TV(tvOS)와 호환됩니다. 마케터 또는 팀원은 이 도움말 문서의 절차에 따라 TV 앱을 테스트할 수 있습니다.
* **배포되지 않은 tvOS 앱:** 마케터와 개발자가 협력해야 합니다. (<Anchor target="_blank" href="/marketers/ko/docs/testing-tvos-integration-before-publishing">배포 전 tvOS 연동 테스트</Anchor> 참조)
* **Amazon Fire TV:** 마케터는 앱스플라이어 대시보드에서 안드로이드 SDK 테스트 방법을 사용하여 [연동을 테스트](/docs/testing-the-sdk-integration-for-marketers#testing-from-the-dashboard)할 수 있습니다. (<Anchor target="_blank" href="/marketers/ko/docs/setting-up-amazon-fire-tv-ad-attribution">Amazon Fire 어트리뷰션</Anchor>에 대해 자세히 알아보기)
* **PBA 웹 이벤트:** 마케터와 개발자가 협력해야 합니다. (<Anchor target="_blank" href="/marketers/ko/docs/test-pba-web-sdk-integration">PBA 웹 SDK 연동 테스트</Anchor> 참조)

> 📄 **참조 항목**
>
> * 애드 네트워크 연동 테스트 <Anchor target="_blank" href="/partners/ko/docs/getting-started-onboarding-guide-for-ad-networks">애드 네트워크 연동 테스트</Anchor>

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 01H88X11QS2VYFXJGC95TXC6PN=%EA%B0%9C%EC%9A%94 testing-using-the-sdk-integration-tests-page=sdk-%EC%97%B0%EB%8F%99-%ED%85%8C%EC%8A%A4%ED%8A%B8-%ED%8E%98%EC%9D%B4%EC%A7%80%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%9C-%ED%85%8C%EC%8A%A4%ED%8A%B8 h_01HYX9R159XMZKMH1MBMBH9K9J=sdk-%EC%97%B0%EB%8F%99-%ED%85%8C%EC%8A%A4%ED%8A%B8-%ED%8E%98%EC%9D%B4%EC%A7%80%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%9C-%ED%85%8C%EC%8A%A4%ED%8A%B8 prepare-a-test-device=%ED%85%8C%EC%8A%A4%ED%8A%B8-%EC%9E%A5%EC%B9%98-%EC%A4%80%EB%B9%84 h_01J9GTS4S2RXJAMYGG6XJ5HFRZ=%ED%85%8C%EC%8A%A4%ED%8A%B8-%EC%9E%A5%EC%B9%98-%EC%A4%80%EB%B9%84 perform-the-integration-tests=%EC%97%B0%EB%8F%99-%ED%85%8C%EC%8A%A4%ED%8A%B8-%EC%88%98%ED%96%89%ED%95%98%EA%B8%B0 h_01J9GTW7RAGZXE7GK5BWGBA7N5=%EC%97%B0%EB%8F%99-%ED%85%8C%EC%8A%A4%ED%8A%B8-%EC%88%98%ED%96%89%ED%95%98%EA%B8%B0 h_01HYX9R15983XCT54TJ0VDE8DE=view-live-events h_01HYX9R15931HJEA06SY3K47W5=test-nonorganic-installs h_01HYX9R159DDNJW53AWTWT4C2Z=test-deep-links-retargeting testing-using-attribution-links=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%9C-%ED%85%8C%EC%8A%A4%ED%8A%B8 01H88X11QT0WDRW5GZDCR7MZ3D=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%9C-%ED%85%8C%EC%8A%A4%ED%8A%B8 01H88X11QT6YVB3TQ6JEM4G92G=test-install-attribution h_01HMDX7JMR8RMDMGS49K3DVJGG=%EC%B0%B8%EA%B3%A0 01H88X11QTG2NZ3VGMQXJR7368=%EC%B0%B8%EA%B3%A0-2 01H88X11QT5TY25HRTX4RD06C7=%ED%8C%81 01H88X11QTRBQQ11C8SAK7DCTC=test-inapp-events-attribution 01H88X11QTJE6HNPDHBMKQMDCP=test-onelink testing-retargeting-using-attribution-links=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%9C-%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%ED%85%8C%EC%8A%A4%ED%8A%B8 01H88X11QTQ94BAJGEE1V11F6X=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A7%81%ED%81%AC%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%9C-%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%ED%85%8C%EC%8A%A4%ED%8A%B8 01H88X11QT4DR3WA6RGB8HDZB3=about-retargeting-tests 01H88X11QTR3AGQHN674ZYEYF7=prerequisites-to-run-retargeting-tests 01H88X11QVFQ6552C272ST108D=test-reattribution 01H88X11QVYBPJPYSPZH2HS308=%EC%B0%B8%EA%B3%A0-2 01H88X11QV5YVR7HCFTGD9BEFJ=%ED%8C%81-1 01H88X11QVKAG3JWRQ6KXESTQA=test-reengagement testing-organic-installs=%EC%98%A4%EA%B0%80%EB%8B%89-%EC%9D%B8%EC%8A%A4%ED%86%A8-%ED%85%8C%EC%8A%A4%ED%8A%B8 h_01HYX9R1594DD9BEZ6PMV9PJM8=%EC%98%A4%EA%B0%80%EB%8B%89-%EC%9D%B8%EC%8A%A4%ED%86%A8-%ED%85%8C%EC%8A%A4%ED%8A%B8 Testing%20CTV=ctv-%ED%85%8C%EC%8A%A4%ED%8A%B8 01H88X11QT72F71N49G65BAEAE=ctv-%ED%85%8C%EC%8A%A4%ED%8A%B8 h_01H9FHRVKE88CXGH8G7E26ZXT2=%EC%B0%B8%EC%A1%B0-%ED%95%AD%EB%AA%A9" />
