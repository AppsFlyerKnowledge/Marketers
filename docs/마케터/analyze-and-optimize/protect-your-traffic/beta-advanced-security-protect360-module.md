---
title: '[베타] Advanced Security Protect360 모듈'
metadata:
  keywords:
    - Beta feature
    - Marketers
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2025-09-17T15:23:22Z'
  edited_at: '2026-10-14T10:28:12Z'
  id: 39145848948625
  locale: ko
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/ko/articles/39145848948625
---
<span class="af-tag af-tag--beta-feature">Beta feature</span>

> **한눈에 보기:** Advanced Security Module로 Android 앱의 프로드 방지를 강화하세요. 이 실시간 솔루션은 설치가 어트리뷰션되기 전에 어트리뷰션 파밍 및 조작된 트래픽을 감지하고 차단합니다. 대량 트래픽을 처리하는 앱과 Protect360 고객, 특히 어필리에이트와 협력하는 기업을 위해 설계되었습니다. 이 모듈은 사용자가 전적으로 직접 설정할 수 있어, 진화하는 프로드 패턴에 맞춰 초기 세팅과 지속적인 운영 관리를 유연하게 조정하고 데이터 무결성을 보호합니다.

<div id="important" />

> 🚧 **중요!**
>
> Advanced Security Protect360 Module 베타 버전은 모든 Protect360 고객에게 제공됩니다. 가입을 원하시면 담당 CSM에게 문의해 주세요.

<div id="what-is-sdk-spoofing" />

## SDK 스푸핑이란 무엇입니까?

SDK 스푸핑은 공격자가 실제 기기에 앱을 설치하거나 실행하지 않고, 앱스플라이어 서버로 가짜 설치 및 앱 내 이벤트 요청을 직접 전송하는 고도화된 프로드 수법입니다. 앱 SDK가 해킹되거나 변조된 것은 아닙니다. 대신 프로드 공격자는 실제 앱이 전송하는 네트워크 요청을 흉내 내어 해당 활동이 정상적인 것처럼 보이게 만듭니다.

광고자에게 SDK 스푸핑은 실제 발생하지 않은 설치 및 참여, 부풀려진 설치 수량, 앱스플라이어와 앱 스토어 데이터 간의 불일치, 그리고 광고비 낭비로 이어질 수 있습니다.

<div id="about-the-advanced-security-module" />

## Advanced Security Module에 대해

**Advanced Security Module**은 Android에서 고도화된 어트리뷰션 스푸핑 기법을 감지하고 차단하도록 설계된 앱스플라이어 Protect360 솔루션의 추가 모듈입니다. 앱 첫 실행 후 어트리뷰션이 수행되기 전 사이의 설치 활동을 평가함으로써, 이 모듈은 의심스러운 트래픽을 식별하고 프로드 설치가 성과 지표에 영향을 미치는 것을 방지합니다.

이 솔루션은 앱 스토어 데이터와 앱스플라이어 어트리뷰션 간의 불일치를 겪고 있는 앱이나 어필리에이트 트래픽을 관리하는 앱에 특히 유용하며, 두 가지 모두 설치 프로드의 대표적인 징후입니다.

**작동 방법**

이 모듈은 앱 첫 실행(SDK에 의해 기록됨) 직후, 그리고 설치가 어트리뷰션되기 전에 작동합니다. Advanced Security Module을 사용하려면 Android SDK v6.15.2 이상 버전을 사용해야 합니다.

<div id="set-the-advanced-security-module" />

## 고급 보안 모듈 설정

Advanced Security Module을 설정하여 인앱 트래픽이 서명된 앱 빌드에서 발생하는지 검증하고, 스푸핑된 트래픽을 감지(및 선택적으로 차단)하세요.

<div id="configure-the-advanced-security-module" />

<Accordion title="Advanced Security Module 설정">

<div id="step-1-open-and-select-an-app" />

#### **1단계: 앱을 열고 선택합니다**

1. 앱스플라이어에서 **설정 > Protect360 > Advanced Security Module**으로 이동합니다.
2. **시작하기** 또는 **빌드 추가**를 클릭합니다.
3. Advanced Security Module 솔루션을 구현하려는 앱을 선택합니다.
4. **다음**을 클릭합니다.

<div id="step-2-add-certificate" />

#### **2단계: 인증서 추가**

1. 다음 추가:
   1. 인증서 이름
   2. 인증서 값
2. **다음**을 클릭합니다.

참고: 앱을 서명하는 데 사용되는 모든 [인증서 해시](https://dev.appsflyer.com/hc/docs/android-security-plugin#generating-a-sha256-fingerprint)를 개발자에게 물어보세요. Security Module은 이러한 인증서를 사용해 트래픽이 사용자의 앱에서 발생하는지 검증하므로, 관련된 모든 해시를 포함해야 합니다.

<div id="step-3-excluded-app-versions-from-detection" />

#### **3단계: 탐지에서 제외된 앱 버전**

* Advanced Security 탐지에서 제외할 앱 버전을 추가하세요. 일반적으로 다음과 같습니다:
  * Advanced Security Module이 연동되기 전에 출시된 버전.
  * 모듈을 포함하지 않는 테스트 또는 기존 빌드.

<div id="step-4-build-activation" />

#### **4단계: 빌드 활성화**

1. **빌드 활성화** 를 클릭합니다.
2. 빌드가 완료될 때까지 빌드 상태가 **진행 중**으로 표시됩니다. 10-15분 정도 걸릴 수 있습니다.
3. 완료되면 빌드에서 **코드 복사** 버튼을 클릭하여 코드를 복사한 후, 앱 SDK에 연동할 수 있도록 개발자에게 전달하세요.

<div id="note" />

> 📘 **참고**
>
> 빌드 후 탐지 모드는 기본적으로 **태그됨**으로 설정됩니다. 이 모드에서는 앱스플라이어가 의심스러운 트래픽을 플래그로 표시하지만 차단하지는 않습니다. 보안 버전이 라이브된 후, 스푸핑된 트래픽을 차단하려면 **연동 완료** 모드로 전환하세요. 태그됨 및 연동 완료 모드에 대한 자세한 정보는 <Anchor target="_blank" href="/marketers/ko/docs/beta-fraud-protection-studio#fps-모드">FPS 모드</Anchor>를 참조하세요.

</Accordion>

<div id="maintaining-and-updating-the-configuration" />

<Accordion title="구성 유지 및 업데이트">

프로드 기법은 시간이 지남에 따라 변하며, 악의적인 공격자는 탐지 로직을 리버스 엔지니어링하려 시도할 수 있습니다. 정기적인 유지보수를 통해 지속적인 효과를 보장할 수 있습니다.

<div id="when-to-update-the-configuration" />

#### **설정 업데이트 시점**

다음과 같은 현상이 감지되면 설정을 업데이트하세요.

* 탐지를 통과하는 의심스러운 설치 또는 이벤트 발생 시
* 트래픽 패턴의 변화
* 새로운 앱 버전 또는 인증서 변경
* 기존 보호의 효율성 감소

<div id="what-you-can-update" />

#### **업데이트 가능한 항목**

다음 항목:

* 앱 인증서 추가 또는 업데이트
* 제외된 앱 버전 수정
* 보안 모듈을 재구성 및 재배포
* 배포 상태에 따라 탐지 모드 조정

<div id="best-practices" />

#### **모범 사례**

* 정기적인 Advanced Security Insights 검토
* 앱 출시 전 개발자와 조정
* 서명 변경 직후 즉시 인증서 업데이트
* 새롭게 등장하는 프로드 수법보다 한발 앞서 나가기 위해 정기적으로 설정 재평가

</Accordion>

<div id="data-visibility" />

## **데이터 가시성**

Advanced Security Module의 탐지 결과는 두 곳에서 확인하실 수 있습니다.

* Protect360 대시보드
* 프로드 방지 스튜디오

<div id="protect360-dashboard" />

<Accordion title="Protect360 대시보드">

Advanced Security Module 탐지 내역은 **어트리뷰션 스푸핑** 섹션에서 찾을 수 있습니다.

데이터는 2개의 KPI와 하나의 그래프로 나누어 표시됩니다.

**KPI**

* **태그된 어트리뷰션 스푸핑**: 태그됨 모드에서 Advanced Security Module에 의해 감지된 설치 후보 수입니다.
* **연동 완료 어트리뷰션 스푸핑**: 연동 완료 모드에서 Advanced Security Module에 의해 감지되어 차단된 설치 후보 수입니다.

**그래프**

* **어트리뷰션 스푸핑 추세**: 시간 경과에 따른 Advanced Security Module 탐지 현황 반영입니다. 이 그래프는 앱 수준에서의 스푸핑 탐지에 대한 전반적인 상태를 반영합니다.

<Image alt="" src="https://files.readme.io/2f9e63d283850d3b1150dfcefff3c3cd47383cb58c4194dbbec3296da807fcb9-39145854862353.png" width="624px" />

</Accordion>

<div id="fraud-protection-studio-fps" />

<Accordion title="프로드 방지 스튜디오(FPS)">

Advanced Security Module은 Fraud Protection Studio 페이지에서 확인하실 수 있습니다.

<div id="how-to-access" />

#### 액세스 방법

고급 보안 모듈에 액세스하려면:

1. 앱스플라이어에 로그인합니다.
2. 왼쪽 메뉴에서 설정 > Protect360 > 프로드 방지 스튜디오로 이동합니다.
3. 페이지 상단의 앱 드롭다운을 사용하여 설정할 앱을 선택합니다.
4. 왼쪽 메뉴에서 Advanced Security Module 카드를 선택합니다.

<div id="the-advanced-security-module-page" />

#### 고급 보안 모듈 페이지

<Image alt="" src="https://files.readme.io/a94b0c810f719846ae2882cac2ff1dbe4e32f815ee4e023e65e563199f4e3345-39145848945681.png" width="624px" />

Advanced Security Module 페이지는 세 가지 섹션으로 분할됩니다.

<div id="detection-status" />

##### 탐지 상태

* 탐지 모드를 표시합니다. 두 옵션은 구현되고 태그됩니다. 기본적으로, **태그됨**으로 설정됩니다.

참고: 감지 상태를 변경하려면 CSM에 문의하세요.

<div id="top-app-versions-by-detection-status" />

##### 감지 상태별 상위 앱 버전

* 이 차트는 설치 수량을 기준으로 상위 5개 앱 버전을 보여줍니다.
  * 각 앱 버전은 다음과 같이 분할됩니다.
    * **태그되지 않음** - Advanced Security Module에 의해 감지되지 않은 설치 후보 수입니다.
    * **태그됨** - 태그됨 모드에서 Advanced Security Module에 의해 감지된 설치 후보 수입니다.
    * **차단됨** - 연동 완료 모드에서 Advanced Security Module에 의해 감지된 설치 후보 수입니다. 차단된 모든 설치 후보는 이후 프로세스로 진행되지 않습니다.

<div id="insights" />

##### 인사이트

인사이트는 차트의 세부 내역을 이해하는 데 도움이 됩니다. 세 가지 유형의 인사이트는 다음과 같습니다.

* **모든 트래픽 차단됨** -100% 차단된 앱 버전은 해당 버전이 제외 리스트에 추가되지 않았음을 의미할 수 있습니다. 해당 CSM과 함께 앱 버전 제외 리스트를 확인하고 관련 앱 버전을 추가하는 것을 고려해 보세요.
* **모든 트래픽 태그됨** - 100% 태그 지정된 앱 버전은 제외 리스트에 추가되지 않았을 수 있습니다. 해당 CSM과 함께 앱 버전 제외 리스트를 확인하고 관련 앱 버전을 추가하는 것을 고려해 보세요.
* **높은 태그 지정 탐지율** - 하나 이상의 앱 버전에서 태그됨 모드의 Advanced Security Module 탐지 비율이 20%를 초과하여 나타나고 있습니다. 최상의 결과를 얻으려면 담당 CSM에게 문의하여 연동 완료 탐지 모드로 전환하는 것을 강력히 권장합니다.

</Accordion>

<div id="faq" />

<Accordion title="FAQ">

<div id="what-is-advanced-security" />

#### Advanced Security란 무엇입니까?

Advanced Security는 앱을 설치하거나 사용하지 않은 실제 사용자가 없음에도 가짜 설치나 이벤트가 보고되는 부정 행위 유형인 어트리뷰션 스푸핑을 방지하는 데 도움을 주는 앱스플라이어 Android SDK의 추가 보호 레이어입니다.

<div id="what-problem-does-advanced-security-solve" />

#### Advanced Security는 어떤 문제를 해결할 수 있나요?

Advanced Security는 앱 스토어나 백엔드 시스템에는 존재하지 않지만 앱스플라이어에 나타나는, 스푸핑으로 인한 가짜 설치 및 앱 내 활동을 방지하는 데 도움을 줍니다. 이는 부풀려진 설치 수, 데이터 불일치, 낭비되는 광고비를 줄여줍니다.

<div id="what-is-attribution-spoofing" />

#### 어트리뷰션 스푸핑이 무엇인가요?

어트리뷰션 스푸핑은 공격자가 가짜 설치나 앱 내 이벤트 데이터를 생성하여 사용자 앱에서 발생한 것처럼 위장한 후 앱스플라이어로 전송하는 사기 기법입니다. 실제 앱 설치나 사용자 활동은 전혀 발생하지 않습니다.

<div id="how-does-advanced-security-prevent-attribution-spoofing" />

#### Advanced Security는 어트리뷰션 스푸핑을 어떻게 방지하나요?

Advanced Security는 각 요청에 고유한 검증 서명을 추가하여 설치 및 앱 내 이벤트 데이터가 앱의 SDK에서 실제로 생성되었는지 검증합니다. 앱스플라이어는 이 서명을 확인하여 데이터의 진위 여부를 판별하고 스푸핑이나 조작이 발생하지 않았음을 입증합니다.

<div id="does-advanced-security-affect-the-app-or-user-experience" />

#### Advanced Security가 앱이나 사용자 경험에 영향을 미치나요?

아닙니다. Advanced Security는 백그라운드에서 실행되며 사용자가 앱을 설치하거나 사용하는 방식에 영향을 주지 않습니다. 모든 추가 처리 과정은 비하인드에서 이루어지므로 사용자가 인지할 수 없습니다.

<div id="who-should-use-advanced-security" />

#### 누가 Advanced Security를 사용해야 하나요?

Advanced Security는 non-SRN이나 애프리이에트 네트워크와 활발하게 협력하는 앱, 앱스토어 설치 수와 앱스플라이어 데이터 간의 원인을 알 수 없는 격차를 겪는 앱, 또는 표준적인 방식으로는 감지하기 어려운 고도화된 사기가 의심되는 앱에 가장 유용합니다.

<div id="is-advanced-security-available-for-all-platforms" />

#### Advanced Security는 모든 플랫폼에서 사용할 수 있나요?

아닙니다. Advanced Security는 현재 Android 앱에서만 사용 가능하며, Protect360 프리미엄 고객에게 제공됩니다. 또한 모든 앱스플라이어 플러그인과 호환됩니다.

<div id="how-do-i-know-advanced-security-is-working" />

#### Advanced Security가 제대로 작동하는지 어떻게 확인하나요?

탐지 결과는 Protect360 대시보드 및 Fraud Protection Studio에서 확인할 수 있으며, 태그 처리되거나 차단된 스푸핑 트래픽을 추적하고 시간에 따른 추이를 검토할 수 있습니다.

</Accordion>

<div data-zendesk-anchors="h_01K5EBZV8BY54H332WTWEMYVSA=%EC%A4%91%EC%9A%94 what-is-sdk-spoofing=sdk-%EC%8A%A4%ED%91%B8%ED%95%91%EC%9D%B4%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9E%85%EB%8B%88%EA%B9%8C h_01KH8MPFJBSN67PSQXX25NG6ZZ=sdk-%EC%8A%A4%ED%91%B8%ED%95%91%EC%9D%B4%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9E%85%EB%8B%88%EA%B9%8C about-the-advanced-security-module=advanced-security-module%EC%97%90-%EB%8C%80%ED%95%B4 h_01K5C4BCNRE8JWQ9DA20DJ3A07=advanced-security-module%EC%97%90-%EB%8C%80%ED%95%B4 set-the-advanced-security-module=%EA%B3%A0%EA%B8%89-%EB%B3%B4%EC%95%88-%EB%AA%A8%EB%93%88-%EC%84%A4%EC%A0%95 h_01KHK6M3CTY4YSCRTSMS707S5Z=%EA%B3%A0%EA%B8%89-%EB%B3%B4%EC%95%88-%EB%AA%A8%EB%93%88-%EC%84%A4%EC%A0%95 h_01KH8MQXD943CTH2XB4HTH890S=configure-the-advanced-security-module step-1-open-and-select-an-app=1%EB%8B%A8%EA%B3%84-%EC%95%B1%EC%9D%84-%EC%97%B4%EA%B3%A0-%EC%84%A0%ED%83%9D%ED%95%A9%EB%8B%88%EB%8B%A4 h_01KH8XDACWA2C46MEEGFMM6J8M=1%EB%8B%A8%EA%B3%84-%EC%95%B1%EC%9D%84-%EC%97%B4%EA%B3%A0-%EC%84%A0%ED%83%9D%ED%95%A9%EB%8B%88%EB%8B%A4 step-2-add-certificate=2%EB%8B%A8%EA%B3%84-%EC%9D%B8%EC%A6%9D%EC%84%9C-%EC%B6%94%EA%B0%80 h_01KH8XDACYBFZJWHZZCD0JSNGJ=2%EB%8B%A8%EA%B3%84-%EC%9D%B8%EC%A6%9D%EC%84%9C-%EC%B6%94%EA%B0%80 step-3-excluded-app-versions-from-detection=3%EB%8B%A8%EA%B3%84-%ED%83%90%EC%A7%80%EC%97%90%EC%84%9C-%EC%A0%9C%EC%99%B8%EB%90%9C-%EC%95%B1-%EB%B2%84%EC%A0%84 h_01KH8XDAD08E1JJVVSV9GY4RAB=3%EB%8B%A8%EA%B3%84-%ED%83%90%EC%A7%80%EC%97%90%EC%84%9C-%EC%A0%9C%EC%99%B8%EB%90%9C-%EC%95%B1-%EB%B2%84%EC%A0%84 step-4-build-activation=4%EB%8B%A8%EA%B3%84-%EB%B9%8C%EB%93%9C-%ED%99%9C%EC%84%B1%ED%99%94 h_01KH8XDAD122D7PWP2367YVNP2=4%EB%8B%A8%EA%B3%84-%EB%B9%8C%EB%93%9C-%ED%99%9C%EC%84%B1%ED%99%94 h_01KH8XJXN717M3GDJNPPMWDBHY=%EC%B0%B8%EA%B3%A0 h_01KH9HBT6Y803N7ABMSWHZCKE9=maintaining-and-updating-the-configuration when-to-update-the-configuration=%EC%84%A4%EC%A0%95-%EC%97%85%EB%8D%B0%EC%9D%B4%ED%8A%B8-%EC%8B%9C%EC%A0%90 h_01KH8XDAD3M4RARMK7DS7RA08X=%EC%84%A4%EC%A0%95-%EC%97%85%EB%8D%B0%EC%9D%B4%ED%8A%B8-%EC%8B%9C%EC%A0%90 what-you-can-update=%EC%97%85%EB%8D%B0%EC%9D%B4%ED%8A%B8-%EA%B0%80%EB%8A%A5%ED%95%9C-%ED%95%AD%EB%AA%A9 h_01KH8XDAD46P524Z2H8BBZRAR1=%EC%97%85%EB%8D%B0%EC%9D%B4%ED%8A%B8-%EA%B0%80%EB%8A%A5%ED%95%9C-%ED%95%AD%EB%AA%A9 best-practices=%EB%AA%A8%EB%B2%94-%EC%82%AC%EB%A1%80 h_01KH8XDAD5PVKNPW37PMG3NKHH=%EB%AA%A8%EB%B2%94-%EC%82%AC%EB%A1%80 data-visibility=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B0%80%EC%8B%9C%EC%84%B1 h_01K5C4BCNTBVDQX8DGTGEAN01T=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B0%80%EC%8B%9C%EC%84%B1 h_01KH9H6RPBTNTPNMW68VSSN582=protect360-dashboard h_01KH9H6RPBAY53PNH00FX9596D=fraud-protection-studio-fps how-to-access=%EC%95%A1%EC%84%B8%EC%8A%A4-%EB%B0%A9%EB%B2%95 h_01K5C4BCNZBS424A4PMS7AR8XG=%EC%95%A1%EC%84%B8%EC%8A%A4-%EB%B0%A9%EB%B2%95 the-advanced-security-module-page=%EA%B3%A0%EA%B8%89-%EB%B3%B4%EC%95%88-%EB%AA%A8%EB%93%88-%ED%8E%98%EC%9D%B4%EC%A7%80 h_01K5C4BCP14ARR3JMDPMRWZPTT=%EA%B3%A0%EA%B8%89-%EB%B3%B4%EC%95%88-%EB%AA%A8%EB%93%88-%ED%8E%98%EC%9D%B4%EC%A7%80 h_01K5C4BVN5CQVP8HJG1MBV72AW=%ED%83%90%EC%A7%80-%EC%83%81%ED%83%9C h_01K5C4BVN69SK4TBNWPFPWYXPN=%EA%B0%90%EC%A7%80-%EC%83%81%ED%83%9C%EB%B3%84-%EC%83%81%EC%9C%84-%EC%95%B1-%EB%B2%84%EC%A0%84 h_01K5C4BVN6XA4SNP4TK9SSRHS9=%EC%9D%B8%EC%82%AC%EC%9D%B4%ED%8A%B8 h_01KH9JJ5Y7QA631VTKXVGFXBYJ=faq what-is-advanced-security=advanced-security%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9E%85%EB%8B%88%EA%B9%8C h_01KH9HERVW7QE2JXCGBBC206VW=advanced-security%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9E%85%EB%8B%88%EA%B9%8C what-problem-does-advanced-security-solve=advanced-security%EB%8A%94-%EC%96%B4%EB%96%A4-%EB%AC%B8%EC%A0%9C%EB%A5%BC-%ED%95%B4%EA%B2%B0%ED%95%A0-%EC%88%98-%EC%9E%88%EB%82%98%EC%9A%94 h_01KH9HERVX8V537KQBSMAR31T8=advanced-security%EB%8A%94-%EC%96%B4%EB%96%A4-%EB%AC%B8%EC%A0%9C%EB%A5%BC-%ED%95%B4%EA%B2%B0%ED%95%A0-%EC%88%98-%EC%9E%88%EB%82%98%EC%9A%94 what-is-attribution-spoofing=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%8A%A4%ED%91%B8%ED%95%91%EC%9D%B4-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80%EC%9A%94 h_01KH9HERVY5G1J5KQV9ZKTHGXX=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%8A%A4%ED%91%B8%ED%95%91%EC%9D%B4-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80%EC%9A%94 how-does-advanced-security-prevent-attribution-spoofing=advanced-security%EB%8A%94-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%8A%A4%ED%91%B8%ED%95%91%EC%9D%84-%EC%96%B4%EB%96%BB%EA%B2%8C-%EB%B0%A9%EC%A7%80%ED%95%98%EB%82%98%EC%9A%94 h_01KH9HERVZAT11WNX99R2EQCPB=advanced-security%EB%8A%94-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%8A%A4%ED%91%B8%ED%95%91%EC%9D%84-%EC%96%B4%EB%96%BB%EA%B2%8C-%EB%B0%A9%EC%A7%80%ED%95%98%EB%82%98%EC%9A%94 does-advanced-security-affect-the-app-or-user-experience=advanced-security%EA%B0%80-%EC%95%B1%EC%9D%B4%EB%82%98-%EC%82%AC%EC%9A%A9%EC%9E%90-%EA%B2%BD%ED%97%98%EC%97%90-%EC%98%81%ED%96%A5%EC%9D%84-%EB%AF%B8%EC%B9%98%EB%82%98%EC%9A%94 h_01KH9HERW0XFEGCKGJZA6C44HY=advanced-security%EA%B0%80-%EC%95%B1%EC%9D%B4%EB%82%98-%EC%82%AC%EC%9A%A9%EC%9E%90-%EA%B2%BD%ED%97%98%EC%97%90-%EC%98%81%ED%96%A5%EC%9D%84-%EB%AF%B8%EC%B9%98%EB%82%98%EC%9A%94 who-should-use-advanced-security=%EB%88%84%EA%B0%80-advanced-security%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%B4%EC%95%BC-%ED%95%98%EB%82%98%EC%9A%94 h_01KH9HERW00N9M05DSF8998JE0=%EB%88%84%EA%B0%80-advanced-security%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%B4%EC%95%BC-%ED%95%98%EB%82%98%EC%9A%94 is-advanced-security-available-for-all-platforms=advanced-security%EB%8A%94-%EB%AA%A8%EB%93%A0-%ED%94%8C%EB%9E%AB%ED%8F%BC%EC%97%90%EC%84%9C-%EC%82%AC%EC%9A%A9%ED%95%A0-%EC%88%98-%EC%9E%88%EB%82%98%EC%9A%94 h_01KH9HERW13WYZYBAGA9XXKW1B=advanced-security%EB%8A%94-%EB%AA%A8%EB%93%A0-%ED%94%8C%EB%9E%AB%ED%8F%BC%EC%97%90%EC%84%9C-%EC%82%AC%EC%9A%A9%ED%95%A0-%EC%88%98-%EC%9E%88%EB%82%98%EC%9A%94 how-do-i-know-advanced-security-is-working=advanced-security%EA%B0%80-%EC%A0%9C%EB%8C%80%EB%A1%9C-%EC%9E%91%EB%8F%99%ED%95%98%EB%8A%94%EC%A7%80-%EC%96%B4%EB%96%BB%EA%B2%8C-%ED%99%95%EC%9D%B8%ED%95%98%EB%82%98%EC%9A%94 h_01KH9HERW2CQ76W33ERFTP0FS9=advanced-security%EA%B0%80-%EC%A0%9C%EB%8C%80%EB%A1%9C-%EC%9E%91%EB%8F%99%ED%95%98%EB%8A%94%EC%A7%80-%EC%96%B4%EB%96%BB%EA%B2%8C-%ED%99%95%EC%9D%B8%ED%95%98%EB%82%98%EC%9A%94" />
