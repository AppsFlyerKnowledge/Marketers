---
title: 계정 간 앱 전송하기
metadata:
  keywords:
    - Account
    - Advertisers
    - Agencies
    - moving apps
    - move app
    - app transfer
    - transferring apps
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
  created_at: '2018-07-24T07:56:37Z'
  edited_at: '2026-10-14T10:38:42Z'
  id: 360001336005
  locale: ko
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/ko/articles/360001336005
---
> **한눈에 보기:** 본 문서에서 설명한 단계에 따라 앱스플라이어 계정 간에 앱을 이전합니다(발신자 및 수신자 계정의 관리자용).

![5638-Transfering-an-app-NEW1.gif](https://files.readme.io/f4288a79bbd96e8cf828cf0ca9ae9ef994400f702cd66108d2861e3a405c4d79-360010967257.gif)

## 계정 간 앱 전송

앱스플라이어 계정 간에 앱을 이전하려면 송수신 앱 소유자(앱스플라이어 계정 관리자)가 필요한 전송 필수 조건을 완료하고 전송에 동의해야 합니다.

### 필수 조건

* 발신자와 수신자의 계정(관리자)의 이메일이 모두 있는지 확인합니다.
* 두 계정 모두 활성 상태여야 합니다. 정지된 계정은 앱을 보내거나 받을 수 없습니다.
* 두 계정 모두 미지급 인보이스가 없어야 합니다.
* <Anchor target="_blank" href="/marketers/ko/docs/account-management-plans-payments-and-billing#appsflyer-plans">더 알아보기</Anchor>

### 앱 전송 과정

아래에 앱 이전 프로세스의 개요를 보여줍니다.

1. 발신자는 앱스플라이어에 선택한 앱을 전송하고 수신자의 관리자 이메일 주소를 입력하도록 요청합니다.
2. 수신자는 알림을 받고 앱을 수신하는 데 동의합니다.
3. 발신자와 수신자 관리자 모두 보류 중인 전송에 대한 알림(이메일 및 **나의 앱** 페이지)을 받습니다.   
   **참고:** 전송이 보류 중인 상태에서 관리자는 앱 전송 요청을 삭제(전송 취소)할 수 있습니다.
4. 앱스플라이어는 앱을 전송합니다. 전제조건이 완료되지 않은 경우, 앱스플라이어는 완료를 보장하기 위해 관련 당사자에게 연락합니다.

<div id="app-transfer-scope" />

<Accordion title="앱 전송 범위">

다음 표에서는 전송되는 앱 기능 및 설정에 대해 자세히 설명합니다. 전송하기 전에 발신자가 특정 설정 및 구성 정보를 삭제할 수 있다는 것에 유의하십시오.

<table><thead><tr><th>항목</th><th>이전 완료/<br/>이전되지 않음</th><th>세부 사항/결정 고려사항</th></tr></thead><tbody><tr><td>앱 설정 </td><td>이전 완료</td><td> <strong>결정권:</strong> 발신자는 전송 전에 FireBase/GCM 서버 키를 삭제할 수 있습니다. </td></tr><tr><td rowspan="2">연동된 파트너</td><td>이전 완료</td><td><p>연동, 비용 및 수익 설정(비용 및 수익 데이터 포함)</p><p><strong>결정권:</strong> 수신자에게 이전할 연동 파트너가 없는 경우, 전송자는 해당 파트너를 비활성화하고 설정 및 자격 증명(비용 및 광고 수익 설정 포함)을 삭제해야 합니다.</p></td></tr><tr><td>이전되지 않음</td><td><p>광고 네트워크 및 에이전시 권한</p><p>Twitter 설정 및 신용 정보</p></td></tr><tr><td>링크 관리</td><td>이전되지 않음</td><td>원링크 템플릿과 링크는 자동으로 전송되지 않지만 CSM이 전송할 수 있습니다. <strong>결정권:</strong> <ul><li>템플릿과 링크를 전송하려면 CSM에 문의하거나 <a href="mailto:hello@appsflyer.com">hello@appsflyer.com</a> 에 메시지를 보냅니다.</li><li>발신자는 전송하기 전에 오래된 링크를 삭제할 수 있습니다.</li></ul></td></tr><tr><td>Push API</td><td>이전 완료</td><td> <strong>결정권:</strong><ul><li>수신자가 전송되는 Push API 설정(엔드포인트)을 필요로 하지 않는 경우 발신자는 해당 설정을 삭제해야 합니다. 그렇지 않으면 데이터가 발신자 정의 엔드포인트로 계속 전달됩니다.</li><li>그 대신, 수신자는 발신자가 사용자-수준 데이터를 수신하지 않도록 보장하기 위해 수신에 대한 설정을 변경할 수 있습니다.  </li></ul></td></tr><tr><td>스마트 배너</td><td>이전되지 않음</td><td><p>배너, 배너 그룹, 광고 소재, 웹사이트는 이전되지 않습니다.  </p></td></tr><tr><td>스마트 스크립트</td><td>이전되지 않음</td><td>앱스플라이어 UI 내에서 생성된 스마트 스크립트는 새 계정에서 사용할 수 없습니다. </td></tr><tr><td>대행사</td><td>이전되지 않음</td><td>에이전시는 앱에 액세스할 수 없게 됩니다.</td></tr><tr><td>오디언스</td><td>이전되지 않음</td><td>잠재 고객들은 삭제됩니다.</td></tr><tr><td>비용 가져오기</td><td>해당 없음</td><td>수신자는 과거 비용 가져오기 파일에 액세스할 수 없습니다. 이는 비용 기록에 영향을 주지 않습니다.  </td></tr><tr><td>데이터 락커</td><td>이전되지 않음</td><td>앱이 데이터 보관함 구성에서 제거되고, 발신자 계정의 앱 데이터 수신이 중지됩니다. </td></tr><tr><td>과거 데이터</td><td>이전 완료</td><td> </td></tr><tr><td>PBA 브랜드 번들</td><td>이전되지 않음</td><td><p>관련 앱이 이전되면 발신자는 번들을 더는 사용할 수 없습니다. 수신자는 PBA 데이터에 액세스할 수 없습니다.</p><p>즉, 클라이언트가 새 계정에서 PBA를 계속 사용해야 하는 경우 앱 이전이 완료되기 전에 웹 번들을 삭제해야 하며, 그렇지 않으면 새 계정에서 동일한 웹 번들을 만들 수 없습니다.</p></td></tr><tr><td>프로텍트 360 데이터</td><td>이전 완료</td><td> </td></tr><tr><td>로데이터 및 통합 데이터</td><td>이전 완료</td><td> </td></tr><tr><td>SDK 개발 키</td><td>이전 완료</td><td> </td></tr><tr><td>유효성 검증 규칙</td><td>이전 완료</td><td> </td></tr></tbody></table>

</Accordion>

## 전송 절차

하나 이상의 앱을 다른 앱스플라이어 계정으로 전송하도록 요청하려면 프로세스를 시작하고 사용자 인터페이스에서 마법사를 안내에 따르십시오.

<div id="sender" />

<Accordion title="발신자">

**전송 요청 제출 방법**:

1. 수신자의 관리자에게 문의하십시오.
   1. [앱 이전 범위](/docs/transferring-apps-between-accounts#app-transfer-scope)를 검토하고 동의하십시오. 양쪽 모두 이전되는 항목과 이전되지 않는 항목을 이해하고 적절히 준비했는지 확인하세요.
   2. 수신자가 사용자에게 앱스플라이어에서 사용하는 관리자의 이메일 주소를 제공하도록 요청합니다.
2. **다음 중 하나를 수행하세요.**  
   * 하나의 앱을 전송하려면: **상단 메뉴 모음 > 나의 앱 > 앱 작업 메뉴 열기(...) > 앱 전송을 선택합니다.**
   * 2개 이상의 앱을 전송하려면:**상단 메뉴 모음 >** /strong>**나의 앱** > 앱 작업 메뉴 열기(...) > **앱 전송**을 선택합니다.
3. 전송할 앱 또는 앱들을 선택합니다.
4. **다음**을 클릭합니다.
5. 수신자의 관리자 이메일을 입력합니다.
6. **다음**을 클릭합니다.
7. 사용 약관을 읽어보고 서명합니다.
   * 사용자와 수신자는 요청이 성공적으로 제출되었다는 알림 메시지를 (이메일을 통해) 받게 됩니다.
   * 요청을 앱스플라이어에서 처리해야 하는 경우, 팝업으로 알림을 받게 됩니다.
   * 앱은 **나의 앱** 페이지에 `<수신자 이메일>`에 대한 전송 보류 중으로 표시됩니다. 이 단계에서도 요청을 삭제할 수 있습니다.[![App_transfer_sender_side.JPG](https://files.readme.io/5e4762461afd7953657b91074054bd79a63ad5bf8a06d084ee4c655ac60088aa-360010128998.jpg)](https://files.readme.io/5e4762461afd7953657b91074054bd79a63ad5bf8a06d084ee4c655ac60088aa-360010128998.jpg)

</Accordion>

<div id="receiver" />

<Accordion title="수신자">

1. [앱 이전 범위](/docs/transferring-apps-between-accounts#app-transfer-scope)를 검토하고 동의하려면 발신자 관리자에게 문의하십시오. 양쪽 모두 이전되는 항목과 이전되지 않는 항목을 이해하고 적절히 준비했는지 확인하세요.
2. 발신자가 전송 요청을 시작했음을 알리는 이메일 알림을 받게 됩니다.
3. **나의 앱** 페이지에서 **요청 검토**를 클릭합니다. 요청에는 하나 이상의 앱이 포함될 수 있습니다.  
   [![App_transfer_receiver_side.JPG](https://files.readme.io/696264fdbc5d2a05c314deabc3ce6410fc211c421b96b7518e4a8c4958b30553-360010129018.jpg)](https://files.readme.io/696264fdbc5d2a05c314deabc3ce6410fc211c421b96b7518e4a8c4958b30553-360010129018.jpg)
4. 각 요청을 검토하고 승인하거나 거부합니다.
5. 읽어보고 허용되는 경우 사용 약관에 서명하십시오.
6. 사용자 및 발신자는 요청이 승인되었음을 이메일로 받게 됩니다.
7. 이전된 앱은 **나의 앱** 페이지에 표시됩니다.

<div id="delete-transfer-request" />

<Accordion title="전송 요청 삭제">

전송이 완료되기 전에 발신자 또는 수신자의 관리자가 앱 전송 프로세스를 삭제(취소)할 수 있습니다.

**앱 이전 요청 삭제 방법:**

* **발신자 관리자**: 상단 메뉴 모음 > **나의 앱** > **[이메일]로 전송 대기 중** 섹션에서 > **요청 삭제**를 클릭합니다.  
  발신자 및 수신자의 관리자에게 알림(이메일)이 발송됩니다.
* **수신자 관리자**:
* 상단 메뉴 모음 > **나의 앱** > **전송 보류 중인 앱** 섹션 > 거부를 클릭합니다.  
  발신자 및 수신자의 관리자에게 알림(이메일)이 발송됩니다.

</Accordion>

</Accordion>

<div data-zendesk-anchors="app-transfer-between-accounts=%EA%B3%84%EC%A0%95-%EA%B0%84-%EC%95%B1-%EC%A0%84%EC%86%A1 h_01HJR1G7Q71H5DAH1G9QFSYK35=%EA%B3%84%EC%A0%95-%EA%B0%84-%EC%95%B1-%EC%A0%84%EC%86%A1 prerequisites=%ED%95%84%EC%88%98-%EC%A1%B0%EA%B1%B4 h_01HJR1G7Q7T1Q768MTTR3Y542X=%ED%95%84%EC%88%98-%EC%A1%B0%EA%B1%B4 app-transfer-process=%EC%95%B1-%EC%A0%84%EC%86%A1-%EA%B3%BC%EC%A0%95 h_01HJR1G7Q7EDJZ4E1T17GWYGTP=%EC%95%B1-%EC%A0%84%EC%86%A1-%EA%B3%BC%EC%A0%95 h_01HJR1G7Q7AWF07RG2J4Q3V2KN=app-transfer-scope transfer-procedures=%EC%A0%84%EC%86%A1-%EC%A0%88%EC%B0%A8 h_01HJR1G7Q7JB0XD3NGT0MWYJZ5=%EC%A0%84%EC%86%A1-%EC%A0%88%EC%B0%A8 h_01HJR1G7Q7ERYXGB83D475AEPN=sender h_01EDBXVWAB5VBWT3XFK21KPV6W=receiver h_01HJR1G7Q8NEF5P5N95C6CGSF9=delete-transfer-request" />
