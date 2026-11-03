---
title: 수신 파트너 연결—Amplitude
metadata:
  keywords:
    - Audiences
    - Premium
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2022-02-23T14:27:13Z'
  edited_at: '2026-10-14T10:31:43Z'
  id: 4470658876817
  locale: ko
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/ko/articles/4470658876817
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **요약:** 귀사의 Amplitude에서 코호트를 가져온 오디언스로 앱스플라이어에 동기화하여 귀사의 1당사자 데이터를 활용하세요.

## Amplitude 연동에 대하여

**앱스플라이어 오디언스-Amplitude 연동**을 통해 Amplitude 계정에서 정의한 코호트를 앱스플라이어의 <Anchor target="_blank" href="/marketers/ko/docs/audiences-import-audience-segments-from-internal-systems">가져온 오디언스</Anchor>로 직접 동기화할 수 있습니다. 앱스플라이어는 이러한 오디언스를 파트너와 연결·유지하고, 연결된 캠페인 지표를 검토하며, 귀사의 Amplitude 및 앱스플라이어 데이터를 연결하여 시너지 효과를 발휘할 수 있는 중앙 집중형 위치로 활용할 수 있습니다.

Amplitude 코호트는 앱스플라이어와 한 번에 동기화하거나, 매일 또는 매시간 업데이트하는 예약된 동기화를 통해 동기화할 수 있습니다.

## 연동 설정

Amplitude 플랫폼 내에서 오디언스-Amplitude 연동을 설정하세요.

### 앱스플라이어 데이터 목적지 정의

**Amplitude에서 다음 단계를 따라 앱스플라이어 데이터 목적지를 정의하세요.** **앱스플라이어 오디언스를 가져오는 각 앱에 대해 별도의 데이터 목적지를 정의해야 합니다.**

1. Amplitude의 **데이터 목적지** 섹션에서 **앱스플라이어** 타일을 선택하세요.
2. **코호트 목적지**에서 **앱스플라이어**를 선택하세요.
3. **앱스플라이어에 연결** 대화 상자에 다음 정보를 입력합니다.

   **중요!** Amplitude 계정에 이전에 생성된 앱스플라이어 데이터 목적지가 있는 경우, 대화 상자는 모든 기존 목적지를 보여주는 스크롤 가능한 목록으로 표시됩니다. 새로운 목적지를 생성하려면 이 목록의 끝으로 스크롤하여 **다른 목적지 추가**를 클릭하세요.

   

| 필드 | 설명 |
| --- | --- |
| 이름 | 목적지의 이름을 입력하세요.<br /><br />단일 Amplitude 프로젝트에서 두 개 이상의 앱스플라이어 목적지를 생성하려면(예: 프로젝트에 여러 앱이 있는 경우) 나중에 쉽게 식별할 수 있는 이름을 만드세요. |
| 앱스플라이어 API 토큰 V2.0 | **앱스플라이어 API 토큰을 가져오려면 앱스플라이어에서 다음 단계를 따르세요:**<ol><li>상단 메뉴 바에서 사용자 메뉴(오른쪽 위 모서리에 있는 이메일 주소 드롭다운)를 액세스하세요.</li><li>**보안 센터**를 선택하세요.</li><li>**앱스플라이어 API 토큰** 섹션에서 **귀사의 앱스플라이어 API 토큰 관리**를 클릭하세요.</li><li>**V2.0** 토큰을 복사합니다.</li></ol> |
| 앱스플라이어 앱 ID | 앱스플라이어 대시보드에 나오는 대로 이 목적지의 앱 ID를 입력하세요:<br /><br />![amplitude_app_id_from_appsflyer_dashboard.png](https://files.readme.io/2e7da9a20f0c4b59e58f51823dd9753ecc36b77e84622821cb3cb65e4f7b2743-33375708378385.png) |
| 플랫폼 | 앱 플랫폼을 선택하세요 (iOS 또는 안드로이드). |
| 식별자 | Amplitude 유저 속성을 왼쪽에서 선택한 후, 오른쪽에서 매핑할 앱스플라이어 키를 선택하여 귀사의 Amplitude 데이터를 앱스플라이어 데이터와 연결하도록 앱스플라이어에 지시하세요. 선택한 앱스플라이어 키는 다음 중 하나여야 합니다.<ul><li>**iOS 오디언스의 경우:** iOS 광고주 ID, Amplitude 유저 ID 또는 앱스플라이어 고객 유저 ID</li><li>**안드로이드 오디언스의 경우:** Google 광고주 ID, Amplitude 유저 ID 또는 앱스플라이어 고객 유저 ID</li></ul> |

4. **저장**을 클릭하여 새로운 앱스플라이어 목적지를 저장하세요.

### Amplitude 코호트를 앱스플라이어 대상에 동기화하기

**다음으로, Amplitude 코호트를 앱스플라이어 목적지에 동기화하려면 다음 단계를 따르세요:**

1. Amplitude 플랫폼의 **코호트** 섹션에서 앱스플라이어 오디언스를 만들려는 코호트를 선택합니다. (또는 새로운 코호트를 만들 수도 있습니다.)
2. 링크를 따라가세요: **코호트 세부 정보를 보려면 클릭하세요.**
3. **코호트 정의** 페이지에서 **동기화 대상…** 버튼을 클릭하세요.
4. 앱스플라이어 타일을 선택한 다음 **다음**을 클릭하세요.

   **대상 및 주기 정의** 대화 상자가 열립니다.

   [altamplitude\_define\_destination\_and\_cadence\_dialog.pngalt](https://support.appsflyer.com/hc/article_attachments/30283235273873)
5. **동기화할 API 대상 선택** 목록에서 해당 앱스플라이어 대상의 이름을 선택합니다.
6. 이 코호트를 앱스플라이어에 한 번만 동기화할지 또는 예약된 동기화로 동기화할지 선택하세요. (예약된 동기화의 경우 매일 또는 매시간 업데이트할지 선택합니다.)
7. **동기화** 버튼을 클릭하여 동기화를 시작하세요.

첫 번째 동기화가 성공적으로 완료되면 이 코호트를 위한 새 오디언스가 오디언스 대시보드의 오디언스 탭에 표시됩니다.

기본적으로 새 오디언스의 이름은 동기화된 Amplitude 코호트의 이름 뒤에 영숫자 식별자가 붙은 형태입니다. 원하면 오디언스 대시보드에서 오디언스 이름을 편집할 수 있습니다.

[altamplitude\_imported\_audience.pngalt](https://support.appsflyer.com/hc/article_attachments/30283235275025)

<div data-zendesk-anchors="overview=amplitude-%EC%97%B0%EB%8F%99%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC h_01HNZP6HDVC5RBMKTCZY81HG4M=amplitude-%EC%97%B0%EB%8F%99%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC setting-up-the-integration=%EC%97%B0%EB%8F%99-%EC%84%A4%EC%A0%95 h_01HNZP6HDVZH6Q1KGJE7FXSPMT=%EC%97%B0%EB%8F%99-%EC%84%A4%EC%A0%95 define-appsflyer-data-destinations=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%AA%A9%EC%A0%81%EC%A7%80-%EC%A0%95%EC%9D%98 h_01HNZP6HDVV3GSEPARCY1VABX8=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%AA%A9%EC%A0%81%EC%A7%80-%EC%A0%95%EC%9D%98 sync-amplitude-cohorts-to-appsflyer-destinations=amplitude-%EC%BD%94%ED%98%B8%ED%8A%B8%EB%A5%BC-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EB%8C%80%EC%83%81%EC%97%90-%EB%8F%99%EA%B8%B0%ED%99%94%ED%95%98%EA%B8%B0 h_01HNZP6HDV6EFPCM5FE5XBAS78=amplitude-%EC%BD%94%ED%98%B8%ED%8A%B8%EB%A5%BC-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EB%8C%80%EC%83%81%EC%97%90-%EB%8F%99%EA%B8%B0%ED%99%94%ED%95%98%EA%B8%B0" />
