---
title: 앱스플라이어와 믹스패널 연동
metadata:
  keywords:
    - Attribution
    - Mixpanel
    - SDK
    - integrated partner
    - Advertisers
    - Ad Networks
    - facebook mixpabel
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2015-12-24T11:33:01Z'
  edited_at: '2026-10-14T10:36:33Z'
  id: 207447103
  locale: ko
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ko/articles/207447103
---
> **한눈에 보기:** 앱스플라이어에서 제품 애널리틱스 플랫폼인 믹스패널로 데이터를 자동으로 공유하는 방법을 알아보세요.

<Image align="center" alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mixpanel.png" />

앱스플라이어와 믹스패널의 연동을 통해 앱스플라이어에서 믹스패널로 유입 캠페인 정보를 가져올 수 있습니다.

<div id="important" />

> 🚧 **중요!**
>
> <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions#미디어-소스-제한">일부 미디어소스</Anchor>는 타사와의 데이터 공유를 제한합니다. 따라서 제한된 이벤트에 대한 포스트백은 포스트백을 보내기 위해 구성된 선택에 관계없이 이 파트너에게 전송되지 않습니다.

<div id="setting-up-mixpanel" />

## 믹스패널 설정

**선행 조건:** 연동 설정 전에 <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations#contact-details">파트너에게 연락</Anchor>하여 계정을 개설하세요.

**연동 활성화 또는 편집 방법:**

1. To activate:연동 활성화 방법: 앱스플라이어의 사이드 메뉴에서협업<strong>></strong>파트너 마켓플레이스를 선택합니다.  
   <strong>편집 방법:</strong> 앱스플라이어의 사이드 메뉴에서 <strong>협업</strong>> 활성화된 연동을 선택합니다.
2. 파트너를 검색하고 선택합니다.
3. **연동 설정**을 클릭하십시오. 연동 설정 페이지로 이동합니다.
4. **연동** 탭에서 연동할 앱을 선택하고 **파트너 활성화**를 켭니다.  
   **참고: 파트너와의 작업 동안 토글이 활성화되어 있어야 합니다<Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">(활성화됨)</Anchor>.**
5. 아래 설명된 대로 관련 탭을 사용하여 설정을 완료합니다.

<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">파트너 구성 창 헤더</Anchor>에 대해 자세히 알아보세요.

<div id="integration-tab" />

<Accordion title="연동 탭">

연동 탭은 아래 설명과 같이 여러 섹션으로 나누어져 있습니다.

<div id="general-settings" />

### 일반 설정

<Image align="center" alt="mixpanel-general-settings.png" src="https://files.readme.io/df1b95eb3926aa7e10db338f156a87b88aabda6b97a4d28db2953e9e48a114e6-360017400598.png" width="542px" />

* * * **EU 데이터 레지던시**: 앱스플라이어는 기본적으로 데이터를 믹스패널의 미국 서버로 전송합니다. 대신 믹스패널의 EU 서버로 데이터를 보내려면 이 토글을 켜세요.  
      **\*토큰**: 믹스패널은 고유 토큰을 통해 앱스플라이어와 연결합니다. 아직 확인하지 않은 경우, 믹스패널에서 가져와서 연동을 계속해야 합니다.

      **믹스패널에서 토큰을 받는 방법:**

      1. [https://mixpanel.com/login/](https://mixpanel.com/login/)에서 믹스패널 계정에 로그인합니다.
      2. **믹스패널**에서 **분석** 대시보드로 이동하여 톱니바퀴 아이콘을 클릭합니다.

         <Image align="center" alt="mixpanel-token-1.png" src="https://files.readme.io/f1fbc76fff621e12a7d91fed5ba49eb20f2b049de65c70b0ab32cadd997287d2-small-360014578477.png" />
      3. 프로젝트의 액세스 키 섹션에서 토큰을 복사하여 앱스플라이어 믹스패널 연동 탭의 **토큰** 필드에 붙여넣습니다.

         <Image align="center" alt="mixpanel-token-2.png" src="https://files.readme.io/e8e633ec87d963244652a53b9b21c495b0a850e234621a44d93b3034c640bff7-360014578757.png" />
    * **광고주 ID 보내기**:
      * 앱스플라이어 customer\_user\_id 파라미터를 사용하는 경우, 인스톨 시마다 이 파라미터가 믹스패널로 전송됩니다(**광고주 ID 보내기**는 비활성화 상태로 둠).
      * 앱스플라이어 customer\_user\_id를 사용하지 않는 경우 **광고주 ID 보내기**를 활성화합니다. 디바이스 ID는 믹스패널에 customer\_user\_id(믹스패널의 unique\_id)로 전송됩니다.  
        <Anchor target="_blank" href="/marketers/ko/docs/sdk-integration-overview">안드로이드</Anchor> 및 <Anchor target="_blank" href="/marketers/ko/docs/sdk-integration-overview">iOS</Anchor>용 앱스플라이어 SDK 연동 가이드에 대해 자세히 알아보세요.
    * **이벤트:** 인스톨 데이터를 믹스패널 이벤트 엔드포인트로 보내려면 켜세요.
    * **피플:** 인스톨 데이터를 믹스패널 피플 엔드포인트로 보내려면 이 옵션을 켜세요.  

      <div id="note" />

      > 📘 **참고**
      >
      > 인스톨 포스트백을 믹스패널로 보내려면 **이벤트** 또는 **피플**이라는 두 가지 엔드포인트 중 하나 이상이 켜져 있어야 합니다.

    * **고급 데이터 공유:** 추가 정보인 c(campaign), network(pid), impression\_based(is-impression)를 믹스패널에 전송하려면 이 옵션을 활성화하세요.

<div id="default-postbacks" />

### 기본 포스트백

앱스플라이어는 사용자 설치 및 리인게이지먼트 후 믹스패널에 자동 포스트백을 보낼 수 있습니다. 리인게이지먼트는 이미 앱을 설치한 사용자가 캠페인을 통해 클릭한 후 앱을 열었을 때 발생합니다. <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#default-postbacks">기본 포스트백</Anchor>에 대해 자세히 알아보세요.

<Image align="center" alt="" src="https://files.readme.io/6cf4f0e1b73c634c5fbe8f79e654ff3a3cd318bdca51d5e6b17933c307eb769d-36693858465809.png" />

<div id="in-app-events-settings" />

### 인앱 이벤트 설정

<Image align="center" alt="mixpanel-in-app-events-settings.png" src="https://files.readme.io/db5e4e6d5bbe084a94b90425d49345511c214ddc39380a2b8419659ad752cdb2-360014576637.png" />

이 섹션에서는 포스트백을 통해 앱스플라이어 이벤트를 믹스패널과 매핑합니다.

<div id="note-1" />

> 📘 **참고**
>
> 믹스패널은 자체 SDK를 사용하여 인앱 이벤트를 캡처합니다. 이들 이벤트가 캡처하지 않고 믹스패널로 전송할 수 있는 유일한 이벤트는 af\_uninstall입니다.

<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">인앱 이벤트 포스트백</Anchor>에 대해 자세히 알아보세요.

**인앱 이벤트 포스트백 구성 방법:**

1. 믹스패널 토큰을 입력합니다.
2. 인앱 이벤트 포스트백을 활성화합니다.
3. **앱 삭제의 광고주 ID를 보내려면** **광고주 ID 보내기**를 활성화합니다.
4. **앱 삭제를 위한 추가 정보를 보내려면** **고급 데이터 공유**를 활성화합니다.
5. SDK 이벤트를 목록에 추가하려면 **이벤트 추가**를 클릭합니다.
6. 드롭다운 메뉴에서 **af\_uninstall**을 선택합니다.
7. 드롭다운 메뉴에서 해당 **파트너 이벤트 식별자**를 선택합니다.
8. 수익 보내기 드롭다운 메뉴에서 필요한 옵션을 선택합니다.  
   * **값 없음 및 수익 없음:** 이벤트 값을 제외하고 이벤트 자체만 전송합니다.
   * **값 및 수익 없음:** 수익 값을 제외한 모든 파라미터를 전송합니다.
   * **값 및 수익**: 수익 값(이벤트에 존재하는 경우)을 포함하여 모든 이벤트 파라미터를 전송합니다.
9. 연동 구성을 완료하려면 **연동 저장**을 클릭합니다.

통합을 저장하면 앱스플라이어가 모든 오가닉 및 논오가닉 인스톨에 대해 다음 데이터를 믹스패널로 보냅니다.

* 믹스패널 토큰 파라미터
* Customer\_user\_id 또는 디바이스 ID(IDFA / 구글 광고 ID)
* 미디어 소스
* 캠페인 이름

**참고**: CUID는 앱 삭제 포스트백에서 전송되지 않습니다.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="어트리뷰션 링크 탭">

이 파트너에 대해 어트리뷰션 링크를 사용할 수 없습니다.

</Accordion>

<div id="cost-tab" />

<Accordion title="비용 탭">

이 파트너와 연동 시 비용 데이터는 지원되지 않습니다.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="광고 수익 탭">

이 파트너와 연동 시 광고 수익은 지원되지 않습니다.

</Accordion>

<div id="permissions-tab" />

<Accordion title="권한 탭">

이 파트너에 대한 권한은 사용할 수 없습니다.

</Accordion>

<div id="integrating-with-mixpanel-when-using-a-login-mechanism" />

## 로그인 메커니즘을 사용할 때 믹스패널과 연동하기

다음은 연동 단계의 예를 보여줍니다.

1. 유저가 앱을 실행했습니다(열었습니다).
2. 믹스패널 SDK는 임의의 고유 ID **(distinct\_id)** 를 생성합니다.
3. 믹스패널 고유 ID를 가져와서 앱스플라이어 SDK 함수 **setCustomerUserId**를 사용하여 고객 유저 ID로 설정합니다.
4. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#start">**시작**</Anchor>을 전송합니다. AppsFlyer는 이 API로 인스톨, 세션, 업데이트를 감지할 수 있습니다.
5. 앱 인스톨이 어트리뷰션되면 고객 유저 ID와 함께 **인스톨** 이벤트가 믹스패널로 전송되며, 여기에는 믹스패널 고유 ID가 포함됩니다.
6. 유저가 등록하거나 로그인하면 유저 식별자(예: 이메일 또는 고객 ID)와 함께 믹스패널 identify() 명령이 호출됩니다. 이렇게 하면 초기 임의의 고유 ID가 등록된 유저 ID에 매핑됩니다.  

   <Tabs>
   <Tab title="Android">

   믹스패널 안드로이드 - <Anchor target="_blank" href="https://developer.mixpanel.com/docs/android#section-combining-anonymous-and-identifiable-user-data">익명 및 식별 가능한 유저 데이터 결합</Anchor>

   ```java
   MixpanelAPI mixpanel = MixpanelAPI.getInstance(context, MIXPANEL_TOKEN);
   mixpanel.identify("user@example.com");

   // Mixpanel v6.2.0 and below should use the following API:
   mixpanel.getPeople().identify(“user@example.com”);
   ```

   </Tab>

   <Tab title="Objective C">

   믹스패널 iOS Objective C - <Anchor target="_blank" href="https://developer.mixpanel.com/docs/ios#section-combining-anonymous-and-identifiable-user-data">익명 및 식별 가능한 유저 데이터 결합</Anchor>

   ```objectivec
   [mixpanel identify:@“user@example.com”];
   ```

   </Tab>

   <Tab title="Swift">

   믹스패널 iOS Swift - [익명 및 식별 가능한 유저 데이터 결합](https://developer.mixpanel.com/docs/swift#section-combining-anonymous-and-identifiable-user-data)

   ```swift
   mixpanel.identify(“user@example.com”);
   ```

   </Tab>

   <Tab title="Unity">

   믹스패널 Unity - [익명 및 식별 가능한 유저 데이터 결합](https://developer.mixpanel.com/docs/unity#section-combining-anonymous-user-data-with-identifiable-user-data)

   ```csharp
   // set customer user id or device id
   Mixpanel.Identify(“user@example.com”);
   ```

   </Tab>
   </Tabs>

7. 믹스패널은 앱스플라이어로부터 유저 ID의 별칭(예: 이메일 주소)과 함께 customer\_user\_id를 수신합니다.

<div id="note-2" />

> 📘 **참고**
>
> 애플리케이션 내에서 등록 프로세스를 사용하지 않는 경우 위에 설명된 대로 1&#126;3단계를 구현합니다.

<div id="viewing-appsflyer-data-in-mixpanel" />

## 믹스패널에서 앱스플라이어 데이터 보기

아래 스크린샷은 인스톨부터 가치 이벤트까지의 전환을 미디어소스별로 세분화한 퍼널 리포트입니다. 또한 각 미디어소스에 대해 전환에 걸리는 시간도 확인할 수 있습니다.

<Image align="center" alt="" src="https://files.readme.io/fdffbe0a2f29c8a8b02b600966583cdeb4917bb48f0502e9b00ef39daa2fa835-9646475113361.png" />

<Image align="center" alt="" src="https://files.readme.io/043a96a00e46a3daaef2b9fa4d58d252391ca2bb14307437f28c447d96ae97d6-9646475229841.png" />

<div data-zendesk-anchors="h_01H9FKEWTEN4F8FM5C9A9ES6HN=%EC%A4%91%EC%9A%94 setting-up-mixpanel=%EB%AF%B9%EC%8A%A4%ED%8C%A8%EB%84%90-%EC%84%A4%EC%A0%95 h_01H9FKEWTEGMEVH3SK739DD719=%EB%AF%B9%EC%8A%A4%ED%8C%A8%EB%84%90-%EC%84%A4%EC%A0%95 h_01H9FKEWTE90WR75PMNN93JAXE=integration-tab general-settings=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 h_01H9FKEWTEMT7VGTTFWFMJHYA8=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 h_01H9FKEWTEV3RWKMWZN0EXFFNP=%EC%B0%B8%EA%B3%A0 default-postbacks=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01H9FKEWTER31RXAH216TRXQPM=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 inapp-events-settings=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95 h_01H9FKEWTERRVKPQFF1B8QQERE=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%A4%EC%A0%95 h_01H9FKEWTEEMMQ0KKRZXRJRE25=%EC%B0%B8%EA%B3%A0-1 h_01H9FKEWTEEQ0GHF87V20TX9W0=attribution-link-tab h_01H9FKEWTEJ61197SN3R6JXYCP=cost-tab h_01H9FKEWTEA7GN2HHK3QD62A3A=ad-revenue-tab h_01H9FKEWTET4QD1RE0HJZM64D4=permissions-tab integrating-with-mixpanel-when-using-a-login-mechanism=%EB%A1%9C%EA%B7%B8%EC%9D%B8-%EB%A9%94%EC%BB%A4%EB%8B%88%EC%A6%98%EC%9D%84-%EC%82%AC%EC%9A%A9%ED%95%A0-%EB%95%8C-%EB%AF%B9%EC%8A%A4%ED%8C%A8%EB%84%90%EA%B3%BC-%EC%97%B0%EB%8F%99%ED%95%98%EA%B8%B0 h_01H9FKEWTE9DEANTXKPD286GD2=%EB%A1%9C%EA%B7%B8%EC%9D%B8-%EB%A9%94%EC%BB%A4%EB%8B%88%EC%A6%98%EC%9D%84-%EC%82%AC%EC%9A%A9%ED%95%A0-%EB%95%8C-%EB%AF%B9%EC%8A%A4%ED%8C%A8%EB%84%90%EA%B3%BC-%EC%97%B0%EB%8F%99%ED%95%98%EA%B8%B0 h_01H9FKEWTFZ107Y999WEMB3409=%EC%B0%B8%EA%B3%A0-2 viewing-appsflyer-data-in-mixpanel=%EB%AF%B9%EC%8A%A4%ED%8C%A8%EB%84%90%EC%97%90%EC%84%9C-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B8%B0 h_01H9FKEWTF9PFNVHTZGDKBX75Y=%EB%AF%B9%EC%8A%A4%ED%8C%A8%EB%84%90%EC%97%90%EC%84%9C-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B8%B0" />
