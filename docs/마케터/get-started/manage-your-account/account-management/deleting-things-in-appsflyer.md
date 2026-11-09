---
title: 앱스플라이어에서 항목 삭제
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2018-11-21T16:07:58Z'
  edited_at: '2026-10-14T10:29:49Z'
  id: 360000603117
  locale: ko
  section: Account management
  section_id: 6551191075473
  url: https://support.appsflyer.com/hc/ko/articles/360000603117
---
> **한눈에 보기** 광고주가 앱을 삭제하여 어트리뷰션을 중지하거나, 미디어소스를 삭제하거나, 사용자 관련 데이터를 삭제하는 방법을 알아보세요.

<Image align="center" alt="shutterstock_699498934.jpg" src="https://files.readme.io/db2cd79f6da6de42042707fb2c8bbfe450a6cdc17a93f7a9dc9ea27d04716ef3-34228068995857.jpg" width="363px" />

<div id="delete-user-history" />

## 사용자 기록 삭제

GDPR 또는 CCPA와 같은 일부 개인 정보 보호 규정은 사용자에게 *삭제 권한을 부여합니다*.

**시나리오:** 사용자가 자신과 관련된 데이터를 삭제하도록 요청합니다. GDPR에 따라 30일 이내에 이 작업을 수행해야 합니다.

**필요한 조치:** 필요한 조치: <Anchor target="_blank" href="/marketers/ko/docs/send-opendsr-api-requests">OpenDSR API</Anchor> 를 사용하여 삭제 요청을 보냅니다.

<div id="stop-attributing-installs-to-a-media-source" />

## 미디어소스에 대한 인스톨 어트리뷰션 중지

앱스플라이어는 구성된 미디어소스에 대한 인스톨 및 이벤트 정보를 수집합니다. 미디어소스가 어트리뷰션을 위해 구성된 경우 새 인스톨이 어트리뷰션됩니다.

**시나리오:** 클릭, 노출 또는 인스톨이 없는 미디어소스에서 캠페인 실행을 중단하면 어트리뷰션이 중지됩니다. 그러나 기존 사용자의 인앱 이벤트는 계속 기록되고 어트리뷰션됩니다.

**인스톨을 미디어소스에 어트리뷰트하는 것을 중지하기 위해 필요한 조치:**

* **SKAN(iOS 앱용):**
  1. <Anchor target="_blank" href="/marketers/ko/docs/skan-conversion-studio#disable-skan-measurement">SKAN 측정을 비활성화합니다</Anchor>.
  2. <Anchor target="_blank" href="/marketers/ko/docs/get-skan-postback-data-from-google-ads#turning-off-the-skan-integration">Google Ads</Anchor> 및 <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-interoperation-with-meta-ads#turning-off-the-skan-integration">Meta Ads</Anchor>의 경우 SKAN 데이터 기록을 중지하려면 SKAN 연결도 제거해야 합니다.
* **SRN:** <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation#파트너-연동-비활성화">파트너 통합을 비활성화합니다</Anchor>.
* **비 SRN:**  
  1. <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation#파트너-연동-비활성화">파트너 통합을 비활성화합니다</Anchor>.
  2. 광고의 앱스플라이어 어트리뷰션 링크에서 유입되는 클릭 및 인스톨은 계속 기록되고 어트리뷰션됩니다. 리드에 표시되는 광고에 더 이상 앱스플라이어 어트리뷰션 링크가 포함되지 않는지 확인하십시오.
* **온드 미디어:**
  * 관련 원링크 커스텀 링크 사용을 중단하십시오.

<div id="remove-or-delete-an-app" />

## 앱 제거 혹은 삭제

앱을 일시적으로 삭제할 수 있는 옵션이 있습니다.

<div id="temporarily-removing-an-app" />

#### 앱을 일시적으로 삭제하기

앱을 일시적으로 제거하면 데이터 기록이 중지되고, 대시보드 에 앱이 표시되지 않으며, '내 앱' 페이지에서 회색으로 표시됩니다. 하지만 앱은 계정과 연결된 상태로 유지되므로 복원할 수 있습니다. 앱을 복원하면 앱 설정, 승인된 기관, 토큰과 같은 이전 데이터가 유지됩니다.

<div id="note" />

> 📘 **참고사항**
>
> 앱 삭제는 개별적으로 진행됩니다. 하지만 <Anchor target="_blank" href="/marketers/ko/docs/adding-an-app-to-appsflyer#api를-통해-귀사의-앱을-대량으로-관리하세요">API를 통해 여러 앱을 한꺼번에 삭제할</Anchor> 수 있습니다.

**앱을 삭제하는 방법:**

1. 상단 표시줄에서 **나의 앱**을 클릭합니다.
2. 앱 작업 메뉴를 선택합니다.
3. **제거를** ***클릭*** 한 다음 확인하세요.  
   앱이 삭제되고 더 이상 앱 목록에 표시되지 않습니다.

**삭제된 앱을 복원하려면 다음 단계를 따르세요.**

* 고객 성공 관리자(CSM)에게 연락하거나 [hello@appsflyer.com](mailto:hello@appsFlyer.com) 으로 이메일 보내 절차를 시작하세요. 고객 성공 관리자(CSM)가 앱을 복원하면 계정에 다시 추가할 수 있습니다.

<div id="transfer-apps-between-accounts" />

## 계정 간 앱 전송

자세한 내용은 가이드를 참조하십시오. <Anchor target="_blank" href="/marketers/ko/docs/transferring-apps-between-accounts">계정 간 앱 전송하기</Anchor>.

<div id="delete-your-account-or-downgrade-your-subscription-plan" />

## 계정 삭제 또는 구독 플랜 다운그레이드

CSM에 문의하거나 [hello@appsflyer.com](mailto:hello@appsFlyer.com)으로 이메일을 보내세요..

<div data-zendesk-anchors="delete-user-history=%EC%82%AC%EC%9A%A9%EC%9E%90-%EA%B8%B0%EB%A1%9D-%EC%82%AD%EC%A0%9C h_01HNZ7TNZM4P5APM2B1WQ4X7S5=%EC%82%AC%EC%9A%A9%EC%9E%90-%EA%B8%B0%EB%A1%9D-%EC%82%AD%EC%A0%9C stop-attributing-installs-to-a-media-source=%EB%AF%B8%EB%94%94%EC%96%B4%EC%86%8C%EC%8A%A4%EC%97%90-%EB%8C%80%ED%95%9C-%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%A4%91%EC%A7%80 h_01HNZ7VPA16065PGCSZDMQZ3ZC=%EB%AF%B8%EB%94%94%EC%96%B4%EC%86%8C%EC%8A%A4%EC%97%90-%EB%8C%80%ED%95%9C-%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%A4%91%EC%A7%80 delete-an-app=%EC%95%B1-%EC%A0%9C%EA%B1%B0-%ED%98%B9%EC%9D%80-%EC%82%AD%EC%A0%9C h_01HNZ7XKEFRNEWGQZ58T7H0KDH=%EC%95%B1-%EC%A0%9C%EA%B1%B0-%ED%98%B9%EC%9D%80-%EC%82%AD%EC%A0%9C removing-an-app=%EC%95%B1%EC%9D%84-%EC%9D%BC%EC%8B%9C%EC%A0%81%EC%9C%BC%EB%A1%9C-%EC%82%AD%EC%A0%9C%ED%95%98%EA%B8%B0 h_01J52J31FDKSPNWSD5J2V5BYTW=%EC%95%B1%EC%9D%84-%EC%9D%BC%EC%8B%9C%EC%A0%81%EC%9C%BC%EB%A1%9C-%EC%82%AD%EC%A0%9C%ED%95%98%EA%B8%B0 h_01HYJ5EPX4B1G1SAF6XGZ7ADWZ=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD transfer-apps-between-accounts=%EA%B3%84%EC%A0%95-%EA%B0%84-%EC%95%B1-%EC%A0%84%EC%86%A1 h_01HNZ7ZW7ZKDSD2TTEX55PYB91=%EA%B3%84%EC%A0%95-%EA%B0%84-%EC%95%B1-%EC%A0%84%EC%86%A1 delete-your-account-or-downgrade-your-subscription-plan=%EA%B3%84%EC%A0%95-%EC%82%AD%EC%A0%9C-%EB%98%90%EB%8A%94-%EA%B5%AC%EB%8F%85-%ED%94%8C%EB%9E%9C-%EB%8B%A4%EC%9A%B4%EA%B7%B8%EB%A0%88%EC%9D%B4%EB%93%9C h_01HNZ81GQ8Z6R8DV8Z6SAXYRB9=%EA%B3%84%EC%A0%95-%EC%82%AD%EC%A0%9C-%EB%98%90%EB%8A%94-%EA%B5%AC%EB%8F%85-%ED%94%8C%EB%9E%9C-%EB%8B%A4%EC%9A%B4%EA%B7%B8%EB%A0%88%EC%9D%B4%EB%93%9C" />
