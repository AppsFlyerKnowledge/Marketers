---
title: 웹 SDK 연동 테스트
metadata:
  keywords:
    - Developers
    - PBA
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2020-09-01T19:09:41Z'
  edited_at: '2026-10-14T10:30:14Z'
  id: 360012729178
  locale: ko
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/ko/articles/360012729178
---
> **한눈에 보기:** 웹 SDK PBA 플러그인 연동 테스트하는 법

## PBA 웹 이벤트 테스트

**테스트 페이지 사용 원칙**

웹 SDK는 PBA로 웹 이벤트를 발송하며, 이는 일일 처리 후 PBA 대시보드 및 로데이터 리포트로 제공됩니다. 효율적인 테스트를 위해, 일일 처리를 대기하지 않고 테스트 이벤트를 전송합니다. 테스트 이벤트는

* 접수 즉시 분석 및 검증됩니다.
* 사용자 인터페이스에서 확인 가능합니다. UI에서는 처리 오류도 확인할 수 있습니다. 처리 오류 발생 시, 정확히 처리될 수 있도록 수정된 이벤트를 재전송합니다.
* 일일 처리 과정에서 다른 이벤트와 같이 처리됩니다. 즉, 수정된 이벤트가 대시보드와 로데이터에 추가됩니다.

#### 웹 SDK 통합 테스트 페이지

<Table>
  <tbody>
    <tr>
      <td>
        <span id="page-main-view"></span>**페이지 주 화면**

        [<Image alt="TestScreen_us-en.jpg" src="https://files.readme.io/345bb7bfffcb7756c0a61d05daadd8a355df5a7b7a07adaeeef203a64adc79bf-360011199758.jpg" width="338px" />](https://files.readme.io/345bb7bfffcb7756c0a61d05daadd8a355df5a7b7a07adaeeef203a64adc79bf-360011199758.jpg)

        * 최신 이벤트가 먼저 나타납니다.
        * **이벤트 캐시**:
          * 최대 100개 이벤트 저장
          * 새 이벤트 자리를 만들기 위해 오래된 이벤트는 삭제됩니다
          * 캐시된 이벤트는 24시간 후 삭제됩니다
        * **페이지 조작 버튼**:
          * **새로고침 빈도 표시기**: 해당 페이지는 5초마다 자동으로 새로고침됩니다.
          * **모두 제거**: 캐시에서 이벤트를 영구히 제거합니다. **주의!** 캐시는 동일한 웹 개발 키를 공유하는 웹사이트에 공통적으로 적용됩니다. 이에 따라, 다른 개발자가 테스트 페이지를 사용 중이라면 그들에게도 동시에 지워집니다.
          * **멈춤/시작**: 자동 새로고침을 멈춥니다. 시작 버튼을 누를 때까지 새 이벤트가 표시되지 않습니다.

        **이벤트 테이블 열**

        | 필드 | 설명 |
        | --- | --- |
        | 시간 (UTC) | Event Time |
        | 이벤트 유형 | 이벤트 유형은 다음과 같습니다:<br /><br />* 귀하가 보낸 이벤트:<br />  * `EVENT`<br />  * `setCustomerUserId`<br />  * `pageLoad`: 귀하의 웹사이트에서 페이지가 로드/새로 고침될 때마다 웹 SDK로부터 전송됩니다 |
        | 이벤트 내용 | PBA로 기록된 이벤트 페이로드입니다. |
        | 코멘트 | * **유효(Valid)**: PBA가 이벤트를 수신 및 기록했습니다. 추가적인 조치가 필요하지 않습니다.<br />* **유효하지 않음**: 수정 조치가 필요한 오류 목록. 오류 메시지 형태는 다음과 같습니다.   <br />  이벤트 필드 이름: 오류 설명<br />* 오류 메시지에 마우스를 올리면 다음과 같은 세부 정보를 확인할 수 있습니다.   <br /><br />  ![PBAWebSDKTestingErrorMessagesPopup_en-us.png](https://files.readme.io/0e050e60dbf9f1289880b5d58c4885d4be66392265986eaf4b2f76876697e429-360011317358.png) |
      </td>
    </tr>
    <tr>
      <td>
        **세부 내용 보기**[![mceclip0.png](https://files.readme.io/893f2654c8a3d4f9e8bce43728c65723d9fe1583825b2ae8c2276afc33612511-360011199738.png)](https://files.readme.io/893f2654c8a3d4f9e8bce43728c65723d9fe1583825b2ae8c2276afc33612511-360011199738.png)

        이벤트 열을 클릭하여 처리된 이후의 내용을 확인합니다. 추가 정보는 <Anchor target="_blank" href="/marketers/ko/docs/pba-web-sdk-integration-guide#web-sdk-event-parameters">웹 SDK 이벤트 파라미터</Anchor>를 참조하세요
      </td>
    </tr>
  </tbody>
</Table>

## 절차

다음 절차를 완료하세요.

<div id="enable-test-mode" />

<Accordion title="테스트 모드 활성화">

**선행 조건**

테스트를 시작하기 전에, <Anchor target="_blank" href="/marketers/ko/docs/pba-web-sdk-integration-guide#installation-and-integration">웹 SDK가 귀사의 웹사이트나 테스트 웹사이트에 구현되어야</Anchor> 합니다.

**브라우저 제한 사항**

특정 브라우저에서 테스트 모드가 활성화되면, 탭에 상관없이 해당 브라우저는 지정된 웹사이트에만 접속할 수 있고 다른 웹사이트는 접속할 수 없습니다. 같은 컴퓨터에서 다른 웹사이트에 접속하기 위해 Chrome 대신 Safari와 같은 다른 브라우저를 사용하세요.

**테스트 모드를 활성화하는 방법:**

1. **SDK가 제대로 로드되었는지 확인:**
   1. 앱스플라이어에서 상단 메뉴를 선택하고 **내 앱** > **브랜드** **번들 보기**를 선택합니다.
   2. 필요한 **웹 SDK 연동 테스트를 선택하세요.** 연동 페이지가 열립니다. 웹 개발자 키(dev key)가 표시됩니다.  

      [![pba_web_sdk_integration_test_web_dev_key_en-us.png](https://files.readme.io/48c37f28d833c0b864fee0a3f417bbd946a385f329ed0e906e20596aeef79b71-360011130257.png)](https://files.readme.io/48c37f28d833c0b864fee0a3f417bbd946a385f329ed0e906e20596aeef79b71-360011130257.png)
   3. 새 브라우저 탭에서 웹 SDK가 설치된 귀사의 웹사이트로 이동하세요.
   4. 마우스 오른쪽 버튼을 클릭하여 '검사'를 선택하고 브라우저 개발자 도구를 열어주세요.
   5. **Console** 탭으로 가세요.
   6. 콘솔에 다음 명령어를 입력하세요:  

      ```javascript
      window.AF_SDK.initPluginsConfig.pba.webAppId
      ```

      webAppID가 나타납니다.

      [![testing_pba_integration_webappid_check_en-us.png](https://files.readme.io/030f867d82d122f2f493d20f65793ded7739ebb32d92ee15e0668aceded02a58-360011059197.png)](https://files.readme.io/030f867d82d122f2f493d20f65793ded7739ebb32d92ee15e0668aceded02a58-360011059197.png)
   7. **웹 SDK 연동 테스트** 페이지에서 보여지는 웹 개발자 키와 웹앱ID가 일치하는지 확인해 주세요.
2. **테스트 모드 활성화**:
   1. 웹사이트 브라우저 탭에서 **Console** 탭으로 이동하세요.
   2. 다음 명령어를 입력하세요:

      ```javascript
      window.AF_SDK.PLUGINS.PBA.turnOnDevMode()
      ```

      이 함수는 `undefined`을 반환합니다.

      [![testing_pba_integration_turnondevmode.png](https://files.readme.io/b26f180876556e90bce8512f310ca3acff97b7ca040b0dcf98362d9076c81e5b-360011059137.png)](https://files.readme.io/b26f180876556e90bce8512f310ca3acff97b7ca040b0dcf98362d9076c81e5b-360011059137.png)
3. **테스트 모드 활성화 여부 확인:**
   * **Console** 탭에서 다음 명령어를 입력하세요:  

     ```javascript
     window.AF_SDK.PLUGINS.PBA.isDevModeOn()
     ```

     반환값은 `true`입니다. 이는 테스트 모드가 활성화되었음을 의미합니다.   
     [![PBATestingWebSDKIntegrationIsDevModeOn_en-us.png](https://files.readme.io/4b5d8f3c3ef31148c9f3cd4021d83404810382fd654defa86d733c0377ffd968-360011482797.png)](https://files.readme.io/4b5d8f3c3ef31148c9f3cd4021d83404810382fd654defa86d733c0377ffd968-360011482797.png)

</Accordion>

<div id="send-test-events" />

<Accordion title="테스트 이벤트 전송">

* 테스트 모드에서 전송된 이벤트는 테스트 통합 페이지에서 확인할 수 있습니다.
* 주의! 테스트 이벤트는 처리된 후 PBA 보고서에 반영됩니다. 보고서가 왜곡되지 않도록 `eventRevenue`을(를) 낮은 값으로 설정해 주세요. 값을 전송하지 않으면 PBA가 자동으로 0으로 처리합니다.

설명된 유형별로 예시 이벤트를 전송해 보세요.

| 단계 | 작업<br /><br />(명령 입력) | 웹 SDK 테스트 통합 페이지<br /><br />(예정된 결과) |
| --- | --- | --- |
| 1 | 브라우저에서 새 탭을 열고 귀사 웹사이트의 아무 페이지나 방문하세요. | 웹사이트를 열거나 새로고침할 때마다 PBA가 `'pageLoad'` 이벤트를 기록합니다:<br /><br />[![PBATestingWebSDKPageLoadEvent_en-us.png](https://files.readme.io/25ae1b2efbfea897caeb5da94d683b3465c9068245acbedb976959cb8fd3cc77-360011369638.png)](https://files.readme.io/25ae1b2efbfea897caeb5da94d683b3465c9068245acbedb976959cb8fd3cc77-360011369638.png) |
| 2 | 귀사의 웹사이트에 사용자로 로그인하거나 등록해서 <Anchor target="_blank" href="/marketers/ko/docs/pba-web-sdk-integration-guide#setting-customer-user-id-after-signup">setCustomerUserId 이벤트를 발생시키세요&lt;1>.</Anchor> | [![mceclip3.png](https://files.readme.io/7fb5276c5d24b1c6128aaee60684e9f2941e1686eeef4dcf4df4a91c86c9ebb6-360011199558.png)](https://files.readme.io/7fb5276c5d24b1c6128aaee60684e9f2941e1686eeef4dcf4df4a91c86c9ebb6-360011199558.png) |
| 3 | <Anchor target="_blank" href="/marketers/ko/docs/pba-web-sdk-integration-guide#recording-event-scenarios">웹 이벤트를 전송해</Anchor> PBA 처리 상태를 확인해 보세요.<br /><br />**참고:**<br /><br />별도로 설정하지 않은 경우, `eventRevenue`와 `eventRevenueCurrency`는 기본값으로 설정됩니다:<ul><li>`eventRevenueCurrency: "USD"`</li><li>`eventRevenue: 0`</li></ul>[![PBAWebSDKTestEventEVENT_en-us.png](https://files.readme.io/208c42edaa132b69279a5a99232763e2e9da1be950dd3dec3b5636d650e540c8-360011317918.png)](https://files.readme.io/208c42edaa132b69279a5a99232763e2e9da1be950dd3dec3b5636d650e540c8-360011317918.png)<br /><br />더 자세한 정보는 <Anchor target="_blank" href="/marketers/ko/docs/pba-web-sdk-integration-guide#web-sdk-event-parameters">웹 SDK 이벤트 파라미터</Anchor>를 참조하세요. | [![mceclip5.png](https://files.readme.io/51f3c824c253bc825d22c672393adc002c365a2084d71ce6183e412b76e9d3eb-360011199578.png)](https://files.readme.io/51f3c824c253bc825d22c672393adc002c365a2084d71ce6183e412b76e9d3eb-360011199578.png) |

</Accordion>

## 문제 해결

<div id="events-do-not-display-in-the-test-page" />

<Accordion title="테스트 페이지에 이벤트가 나타나지 않습니다">

1. 브라우저 개발자 도구에서 **Network** 탭으로 이동해 주세요.
2. 필터 칸에 "websdk."를 입력해 주세요.
3. HTTP 응답 코드를 기준으로 아래와 같은 조치를 취하세요:
   * 200: 앱스플라이어 기술 지원팀으로 연락해 주세요.
   * 400: " " 안에 모든 파라미터가 들어 있는지 확인해 보세요.

</Accordion>

<div data-zendesk-anchors="test-pba-web-events=pba-%EC%9B%B9-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%85%8C%EC%8A%A4%ED%8A%B8 h_01HKW32BE04AKHFMY853211C1A=pba-%EC%9B%B9-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%85%8C%EC%8A%A4%ED%8A%B8 web-sdk-integration-test-page=%EC%9B%B9-sdk-%ED%86%B5%ED%95%A9-%ED%85%8C%EC%8A%A4%ED%8A%B8-%ED%8E%98%EC%9D%B4%EC%A7%80 h_01HKW32BE0Z2ZKTBHSCSWVT04N=%EC%9B%B9-sdk-%ED%86%B5%ED%95%A9-%ED%85%8C%EC%8A%A4%ED%8A%B8-%ED%8E%98%EC%9D%B4%EC%A7%80 procedures=%EC%A0%88%EC%B0%A8 h_01HKW32BE0VA0X9ZX4Z26EY6CZ=%EC%A0%88%EC%B0%A8 h_01HKW32BE08Z9CCMBPK4Z0854C=enable-test-mode h_01HKW32BE0E4A1W221FKY97EZB=send-test-events troubleshooting=%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0 h_01HKW32BE1HFV0NM64QMASBCCT=%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0 h_01HKW32BE1QHV0W6ZDYHG94RQA=events-do-not-display-in-the-test-page" />
