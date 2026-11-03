---
title: 앱이 왜 등록대기중(Pending)인가요?
metadata:
  keywords:
    - Google Play
    - App Store
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
  created_at: '2018-10-14T07:22:04Z'
  edited_at: '2026-10-14T10:35:11Z'
  id: 360001533885
  locale: ko
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/ko/articles/360001533885
---
> **한눈에 보기:** 요약: 앱스토어 대시보드에서 앱 스토어에 게시 보류 중인 앱의 상태 확인하십시오.

<Anchor target="_blank" href="/marketers/ko/docs/adding-an-app-to-appsflyer">새로운 앱 추가</Anchor>를 할 경우 앱이 등록 대기중인지 또는 스토어에 배포되어 있는지 여부를 선택하게 됩니다.

앱스플라이어에서 등록대기 중인 앱은 라이브 앱과 똑같이 보입니다. 등록대기 중인 앱들도 대시보드에 접근이 가능하며, 모든 어트리뷰션 측정 또한 가능합니다. 유일한 차이점은 앱의 로고가 실제 앱 로고가 아닌 앱스플라이어 로고로 표시되는 것입니다.

![Pending_App.png](https://files.readme.io/fd280ea8dbcd280aae0a1328d1523f52c51d2f30dc163e7a62deb424ae5bc8ed-360001789338.png)

## 무슨 일일까요?

앱스플라이어는 자동으로 앱의 상태를 하루에 여러 번 확인합니다.

앱스플라이어가 앱 상태를 확인할 때 앱이 스토어에 라이브 되지 않은 경우 앱은 대시보드에 등록대기 중으로 나타납니다. 앱이 마침내 iTunes 또는 Google에 배포되면 앱이 활성 상태로 업데이트되고 앱 로고가 배포된 앱의 고유 로고로 변경됩니다.

대시보드에서 앱의 상태는 데이터 수집 및 측정에 아무런 영향을 미치지 않습니다. 앱이 Google Play 또는 App Store에 배포되어 있고 사용자가 앱을 설치하고 앱과 상호 작용하는 경우 설치 및 인앱 이벤트 데이터는 대시보드에 그대로 표시됩니다.

## 앱 상태 새로고침

앱의 상태가 활성화로 바뀌려면 앱스플라이어가 먼저 스토어에서 앱의 상태를 확인합니다. Google Play 또는 iTunes에 배포되었지만 여전히 대시보드에 등록대기 중인 것으로 표시되면, 관리자는 앱 상태를 직접 수동으로 확인할 수 있습니다.

**선행 조건**:

**앱 상태를 수동으로 업데이트하는 방법:**

2. 등록대기 중인 앱의 옆에서 **상태 새로 고침(Refresh Status)** 을 클릭하십시오.  
   만약 앱의 상태가 변경되지 않았다면, 앱은 여전히 등록대기 중으로 보이게 됩니다. 만약 상태가 변경되었다면, 상태가 라이브로 바뀌고 로고가 업데이트 될 것입니다.  

   ![app-refersh-status.png](https://files.readme.io/d995ea3ee3523a8f0d4854f9ec116efc33c892694d56334c483b7d9fa6da8d64-360001704577.png)

## 스토어 국가

일부 앱은 특정국가의 Google Play 또는 iTunes 스토어에서만 사용할 수 있습니다. 앱스플라이어에서 앱 배포 상태를 확인하기 위해서는, **정확한 국가 정보가 들어가 있는것이 중요합니다.**

### iOS

앱스플라이이어 대시보드에 <Anchor target="_blank" href="/marketers/ko/docs/adding-an-app-to-appsflyer">iOS 앱을 추가할 경우</Anchor> 앱이 배포되어있는 애플 스토어의 국가를 선택할 수 있습니다. 잘못된 국가를 선택하게되면, 앱스플라이어에서 앱의 상태를 정확히 확인할 수 없습니다.

애플 스토어 국가를 바꾸기 위해서는 다음을 확인해주세요:

1. 앱스플라이어의 사이드 메뉴에서  **설정** > 앱 설정을 선택합니다.
2. **앱스토어 국가(App Store Country)** 아래 정확한 국가를 선택해주세요.
3. 하단으로 스크롤한 후 **설정 저장(Save Settings)** 을 눌러 변경된 정보를 저장해주세요.
4. 앱이 여전히 등록대기 중으로 보인다면, [**상태 새로 고침(Refresh Status)** 을 클릭해주세요.](/docs/why-is-my-app-still-pending#앱-상태-새로고침)

### 안드로이드

앱스플라이어 대시보드에 <Anchor target="_blank" href="/marketers/ko/docs/adding-an-app-to-appsflyer">Android 앱을 추가할 경우</Anchor> 구글 플레이 국가를 선택할 수 없으며, 기본값으로 US가 설정됩니다. 만약, 앱이 US 구글 플레이 스토어가 아닌곳에 배포되어있다면, 앱스플라이어에서 앱의 상태를 정확하게 확인할 수 있게 앱이 배포된 정확한 국가로 설정해놓는것이 중요합니다.

구글 플레이 국가를 바꾸기 위해서는 다음을 확인해주세요:

1. 앱스플라이어의 사이드 메뉴에서  **설정** > 앱 설정을 선택합니다.
2. **앱스토어 국가(App Store Country)** 아래 정확한 국가를 선택해주세요.
3. 하단으로 스크롤한 후 **설정 저장(Save Settings)** 을 눌러 변경된 정보를 저장해주세요.
4. 앱이 여전히 등록대기 중으로 보인다면, [**상태 새로 고침(Refresh Status)** 을 클릭해주세요.](/docs/why-is-my-app-still-pending#앱-상태-새로고침)

<div data-zendesk-anchors="whats-happening=%EB%AC%B4%EC%8A%A8-%EC%9D%BC%EC%9D%BC%EA%B9%8C%EC%9A%94 h_01HKW8NT3DWZMYVDYR13BDZDCT=%EB%AC%B4%EC%8A%A8-%EC%9D%BC%EC%9D%BC%EA%B9%8C%EC%9A%94 refreshing-the-app-status=%EC%95%B1-%EC%83%81%ED%83%9C-%EC%83%88%EB%A1%9C%EA%B3%A0%EC%B9%A8 h_01HKW8NT3DY227ASKYX1RC3V5T=%EC%95%B1-%EC%83%81%ED%83%9C-%EC%83%88%EB%A1%9C%EA%B3%A0%EC%B9%A8 store-country=%EC%8A%A4%ED%86%A0%EC%96%B4-%EA%B5%AD%EA%B0%80 h_01HKW8NT3DHSDAG9C9225TDNRE=%EC%8A%A4%ED%86%A0%EC%96%B4-%EA%B5%AD%EA%B0%80 h_01HKW8NT3DMWVGRB0RE3H3BQ36=ios android=%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C h_01HKW8NT3D2V81Z1ZBVQKTYX8T=%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C" />
