---
title: (Data Clean Room - 연결 작업 참조).
metadata:
  keywords:
    - Premium
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-inbar-agassi
    - Marketers
    - Data Clean Room
  created_at: '2023-03-20T13:18:17Z'
  edited_at: '2026-10-14T10:31:38Z'
  id: 13886278812817
  locale: ko
  section: Data Clean Room
  section_id: 4591191779217
  url: https://support.appsflyer.com/hc/ko/articles/13886278812817
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **한눈에 보기:**

## 개요


1. [![dcr_manage_connections_button.png](https://files.readme.io/773e9568a1e9e642f127806fa3b80932699e0db6cc6a124d5a09898577ade645-13909932760593.png)](https://files.readme.io/773e9568a1e9e642f127806fa3b80932699e0db6cc6a124d5a09898577ade645-13909932760593.png)

1. * <span id="creating-inbound-connections"></span>계정에 정의된 연결이 없는 경우 **새 연결** 대화 상자가 열리고 연결을 만들라는 메시지가 표시됩니다.


<Image alt="dcr_create_inbound_connection.png" src="https://files.readme.io/b30606026761528f4a0d3efcc1a3207e8b9c99ca8202f76b2d698a86efaa21ee-13913809617297.png" width="457px" />

<div id="bigquery-inbound" />

<Accordion title="빅쿼리">

* <Image alt="BQ_project_ID.png" src="https://files.readme.io/de295dfc0224ff90f041b1aeaf2996828ec1920a715ba668b46a2f50489fd15b-13910856739857.png" width="457px" />

</Accordion>

<div id="snowflake-inbound" />

<Accordion title="Snowflake">

![ui-snowsight-account-identifier.png](https://files.readme.io/9995c3fd523548de93bafc7c575203e7d38be3b6be2a5e876d7a0a8495ca04c9-24698313004433.png)

</Accordion>


<span id="creating-outbound-connections"></span>DCR은 <Anchor target="_blank" href="/marketers/ko/docs/data-locker-for-marketers">앱스플라이어 데이터 락커</Anchor>를 사용하여 선택한 클라우드 서비스에 리포트를 제공합니다.

> 📘 **참고사항**
>
> DCR 리포트를 수신하는 데 데이터 락커에 대한 프리미엄 구독이 필요하지 않습니다. 데이터 락커를 통해 다른 앱스플라이어 리포트를 수신하려면 CSM에 문의하거나 [hello@appsflyer.com](mailto:hello@appsflyer.com)로 이메일을 보내주십시오.

1. * 계정에 정의된 연결이 없는 경우:
     * 브라우저에서 새 탭이 열립니다(앱스플라이어 데이터 락커 페이지 표시).
     * **새로운 연결** 대화 상자가 열립니다.
   * 기존 연결이 있지만 새로운 연결을 사용하려면 ![dcr_new_connection_data_locker_button.png](https://files.readme.io/9850a4b8ea4f40f6320903c545c51add7b90207538a27c83a3b02a41197ba567-14995870859281.png) 버튼을 클릭하세요.
     * 브라우저에서 새 탭이 열립니다(앱스플라이어 데이터 락커 페이지 표시).
     * **새로운 연결** 대화 상자가 열립니다.
3. 연결을 만든 후 브라우저의 DCR 탭으로 돌아가서 데이터 락커 연결 목록에서 새로 만든 연결을 선택합니다.


[![dcr_dl_new_connection_dialog.png](https://files.readme.io/fe77a008f036e15f6e192a7a2dc660efd54c92fb3bcceb0be9625420f66893e3-13928181611025.png)](https://files.readme.io/fe77a008f036e15f6e192a7a2dc660efd54c92fb3bcceb0be9625420f66893e3-13928181611025.png)

<div id="bigquery-outbound" />

<Accordion title="빅쿼리">

2. * <Image alt="BQ_project_ID_dataset_name.png" src="https://files.readme.io/c784b0369c51a6e123279fdc5b2fa1fba255ae371d436e9247cb5e4685387983-13928683779089.png" width="457px" />

</Accordion>

<div id="snowflake-outbound" />

<Accordion title="Snowflake">

**참고:** 참고: Snowflake **계정 관리자**가 다음 절차를 수행해야 합니다.

2. * **중요!**   

     <Image alt="snowflake_account_locator.png" src="https://files.readme.io/23495b3209129f48ed1ca3442a1e96fac791d46df6f87050ac036893a050e427-13930022354961.png" width="536px" />

2. 사용자 역할을 **계정 관리자**로 전환합니다.
3. 왼쪽 패널에서 비공개 공유를 선택합니다.

</Accordion>

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 h_01HKA1AS2QGDTPW85WA07K35M0=%EA%B0%9C%EC%9A%94 h_01HKA1AS2QRRBJAYNKSWWZXE3N=creating-inbound-connections complete-the-connection-inbound=%EA%B0%9C%EC%9A%94 h_01HKA1AS2Q06F07RDD8W384RE2=%EA%B0%9C%EC%9A%94 h_01HKA1AS2QXP5H2HBJ911F3TPZ=bigquery-inbound h_01HKA1AS2QCPC6515FZ45E8Q67=snowflake-inbound h_01HKA1AS2QAV9DJWZQ2703TS0Z=creating-outbound-connections h_01HKA1AS2Q76NP9FY7S4H0QP4D=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD complete-the-connection-outbound=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD h_01HKA1AS2RKTWNY2ZR7VYAJC90=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD h_01HKA1AS2R7RFWKM2W89QSEH3V=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD h_01HKA1AS2RJXZPCBKE7ST0SA63=bigquery-outbound h_01HKA1AS2R7TV495V39N35CWAR=snowflake-outbound" />
