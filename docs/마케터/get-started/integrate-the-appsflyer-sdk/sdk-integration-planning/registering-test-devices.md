---
title: 테스트 디바이스 등록
metadata:
  keywords:
    - whitelisting
    - Testing
    - device
    - Advertisers
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2015-03-10T08:19:35Z'
  edited_at: '2026-10-14T10:38:30Z'
  id: 207031996
  locale: ko
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/ko/articles/207031996
---
> **한눈에 보기:** 어트리뷰션 테스트을 할 때, 테스트 디바이스를 등록하여 각 인스톨이 새로운 인스톨로 기록되도록 하세요. 등록된 테스트 디바이스는 인스톨이 재설치로 기록되는 것을 방지합니다.

## 테스트 디바이스를 등록해야 하는 이유

어트리뷰션 테스트를 할 때, 리어트리뷰션 윈도우는 인스톨 어트리뷰션을 90일 동안 하나로 제한합니다. 따라서 동일한 디바이스를 반복적으로 사용하여 인스톨 어트리뷰션을 테스트하면, 아무것도 기록되지 않습니다. 테스트 디바이스로 등록하면, 등록된 디바이스에서 반복 인스톨이 재설치로 기록되는 것을 방지할 수 있습니다.

## 테스트 디바이스를 등록하는 방법

테스트 디바이스를 등록할 때에는 디바이스의 운영 체제(안드로이드, iOS 또는 Windows)를 선택하고 디바이스 식별자를 추가합니다.

다음 방법 중 하나를 사용하여 등록할 수 있습니다.

* [앱스플라이어의 My Device ID 앱을 다운로드하고 인스톨 합니다:](#register-a-device-using-the-appsflyer-device-id-app-admin-only) 테스트 디바이스에 앱을 설치하면 자동으로 디바이스가 등록되고 디바이스 ID 세부 정보를 앱스플라이어 계정에 공유할 수 있습니다. 해당 디바이스는 자동으로 **테스트 디바이스** 페이지에 표시됩니다.

  > 📘 **참고**
  >
  > iOS 14+ 테스트 디바이스에서는, 앱에 앱 추적 투명성(ATT)이 구현되어 있고 동의한 유저로서 테스트을 실행하고 싶은 경우에만 이 등록 방법을 사용할 수 있습니다. 이 경우가 아니라면 수동 방법을 사용하세요.

* [테스트 디바이스를 수동으로 추가:](#register-a-device-manually) 모든 계정 사용자는 **테스트 디바이스** 페이지에 디바이스 식별자를 추가하여 직접 디바이스를 등록할 수 있습니다.

다음 사항을 염두에 두세요.

* 등록된 테스트 디바이스는 해당 계정에 속한 모든 앱에서 사용 가능합니다.
* 광고 네트워크는 광고주에게 디바이스 추가를 요청해야 하며, 대행사는 자체 디바이스를 추가할 수 있습니다.

<div id="supported-device-identifiers" />

<Accordion title="지원되는 디바이스 식별자">

디바이스 식별자에는 다음이 포함됩니다:

* **안드로이드:** AID(GAID 또는 OAID), IMEI, 안드로이드 ID

  > 📘 **참고**
  >
  > 테스트 디바이스를 등록할 때, 귀사의 앱이 이러한 식별자를 수집하고 사용하는 경우에만 IMEI 또는 안드로이드 ID 디바이스 식별자를 추가해야 합니다.

* **iOS:** IDFA, IDFV
* **윈도우 폰:** Windows 광고 ID

</Accordion>

## 테스트 디바이스 등록 관리

<div id="register-a-device-using-the-appsflyer-device-id-app-admin-only" />

<Accordion title="앱스플라이어 디바이스 ID 앱으로 디바이스를 등록하기">

**앱스플라이어 디바이스 ID 앱을 다운로드하려면:**

1. QR 코드(구글 플레이 스토어) 또는 제공된 링크 중 하나로 앱을 다운로드하고 설치하세요.

   <div id="android" />

   <Accordion title="안드로이드">

   [<Image alt="" src="https://files.readme.io/b794c8176cd4884bd1b66372353770485403ca841787e1c0fa3e2759f9c945a0-51912959808273.png" width="233px" />](https://files.readme.io/b794c8176cd4884bd1b66372353770485403ca841787e1c0fa3e2759f9c945a0-51912959808273.png)

   **링크:** [Google Play](https://play.google.com/store/apps/details?id=com.appsflyer.android.deviceid&hl=en) 및 [비공식 스토어](https://apkpure.com/my-device-id-by-appsflyer/com.appsflyer.android.deviceid)

   </Accordion>

   <div id="ios" />

   <Accordion title="iOS">

   [<Image alt="" src="https://files.readme.io/ad4981f255d185e8fea7be468e66e49c6180d27efe3e24bad7d7c7caf1a0c34f-51912933340561.png" width="233px" />](https://files.readme.io/ad4981f255d185e8fea7be468e66e49c6180d27efe3e24bad7d7c7caf1a0c34f-51912933340561.png)

   </Accordion>

   <div id="windows" />

   <Accordion title="윈도우">

   p [<Image alt="" src="https://files.readme.io/6e60bf0e69c0055c5946d111a0a5a2a04dddb268ba777b52097ab0650327d280-31773660950673.png" width="233px" />](https://files.readme.io/6e60bf0e69c0055c5946d111a0a5a2a04dddb268ba777b52097ab0650327d280-31773660950673.png)

   </Accordion>

2. iOS 14.5 이상의 디바이스에서 IDFA 수집을 허용하려면 앱 추적 투명성(ATT) 프롬프트가 표시될 때 **허용**을 탭하세요.[![](https://files.readme.io/3be1b8f24bf558d022c45913b393cf8c8011639354d8b11d9c591e58024f1c8d-31773660957329.png)](https://files.readme.io/3be1b8f24bf558d022c45913b393cf8c8011639354d8b11d9c591e58024f1c8d-31773660957329.png)
3. 안드로이드/iOS/Windows 화면에서 **등록**을 탭하여 디바이스를 등록하세요.

   <div id="android::db8cc168" />

   <Accordion title="안드로이드">

   [![](https://files.readme.io/b6deed582cc87925576b893fb8f021e4aa254c15a99ec532fd456e146769a125-31773630607889.png)](https://files.readme.io/b6deed582cc87925576b893fb8f021e4aa254c15a99ec532fd456e146769a125-31773630607889.png)

   </Accordion>

   <div id="ios::80f176b3" />

   <Accordion title="iOS">

   [![](https://files.readme.io/f06f609433b8ce483e5281cc2a0d062ab71a150318d7892879f3defb706f5429-31773660968081.png)](https://files.readme.io/f06f609433b8ce483e5281cc2a0d062ab71a150318d7892879f3defb706f5429-31773660968081.png)

   </Accordion>

   <div id="windows::6c6af14b" />

   <Accordion title="윈도우">

   [![](https://files.readme.io/6bbfb8680a3f6ea507a7d011d3140fbcc11173f4ef091f7c5f7c3cc863598ab8-31773660972817.jpg)](https://files.readme.io/6bbfb8680a3f6ea507a7d011d3140fbcc11173f4ef091f7c5f7c3cc863598ab8-31773660972817.jpg)

   </Accordion>

4. 앱스플라이어 로그인 자격 증명을 입력하세요. 이제 디바이스가 등록되었습니다.
5. **공유** 세부 정보를 탭하여 디바이스 ID 정보를 공유하세요.

</Accordion>

<div id="register-a-device-manually" />

<Accordion title="수동으로 디바이스를 등록하기">

계정 사용자들이 수동으로 디바이스를 등록할 수 있습니다.

1. 앱스플라이어의 사이드 메뉴에서 **설정** -> **테스트 디바이스**를 선택하세요.
2. **테스트 디바이스**를 선택하세요.
3. **+ 디바이스 추가**를 클릭하세요.
4. 다음을 완료하세요.
   * **이름(영문만 사용):** 디바이스의 고유한 식별 이름을 입력하세요.
   * **운영체제:** 운영체제를 선택하세요.
   * **디바이스 ID 유형:** 디바이스 식별자를 선택하세요.
   * **디바이스 ID:** 운영 체제에 따라 디바이스 ID를 제공하세요.

     <div id="ios::41efa11e" />

     <Accordion title="iOS">

     IDFA 또는 IDFV 식별자를 얻는 방법:

     * **IDFA:** IDFA를 얻으려면 테스트 디바이스에 앱스플라이어 디바이스 ID 앱을 설치하세요. 자세한 내용은 다음을 참조하세요. 위의 앱스플라이어 디바이스 ID 앱(관리자 전용)을 사용하여 [디바이스 추가](#register-a-device-manually)를 실행하세요.
     * **IDFV:** IDFV를 얻으려면 개발자에게 테스트 디바이스에 IDFV 테스트 도구 앱을 설치하도록 요청하세요. 도구 앱이 설치되고 실행되면 IDFV가 표시됩니다. **참고:** 테스트 도구는 개발자가 X-Code에서 예비 단계를 수행한 후에만 설치할 수 있습니다.

     IDFA 또는 IDFV를 언제 사용해야 하는지 알아보려면 [iOS 테스트 디바이스 등록](#ios-테스트-디바이스-등록)을 참조하세요.

     </Accordion>

     <div id="android::7db075c7" />

     <Accordion title="안드로이드">

     앱스플라이어 디바이스 ID 앱을 사용하거나 코드를 디바이스에 입력하여 식별자를 얻으세요.

     | 식별자 | 검색 방법 | 구글 플레이 | 기타 |
     | --- | --- | --- | --- |
     | AID (GAID 또는 OAID) | [앱스플라이어 디바이스 ID 앱](https://play.google.com/store/apps/details?id=com.appsflyer.android.deviceid)을 사용하세요. | 필수 |  |
     | IMEI | *#06#* | 적용 불가 | 개발자가 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectimei">setCollectImei</Anchor>를 사용하여 ID를 수집했는지 확인하세요. |
     | 안드로이드 ID | *#*#8255#*#* (최신 디바이스에서는 작동하지 않을 수 있음) | 적용 불가 | 개발자가 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectandroidid">setCollectAndroidID</Anchor>를 사용하여 ID를 수집했는지 확인하세요. |

     </Accordion>

5. **저장**을 클릭하세요. 등록된 디바이스 목록에 표시됩니다. **참고**: 디바이스가 등록된 디바이스 목록에 즉시 표시되지만, 시스템에 등록되어 제대로 작동하려면 몇 분이 걸릴 수 있습니다.

> 📘 **참고**
>
> 테스트 디바이스에 두 개 이상의 식별자를 추가하려는 경우가 있습니다. 예를 들어, 동일한 디바이스에서 IDFA와 IDFV를 모두 원할 때가 있습니다.
>
> **추가 식별자를 추가하려면:**
>
> 1. **디바이스 추가**를 클릭합니다.
> 2. 테스트 디바이스에 동일한 이름을 사용하고 두 번째 식별자를 추가합니다.
> 3. **저장**을 클릭하세요.

</Accordion>

<div id="unregister-a-device" />

<Accordion title="디바이스 등록 해제">

계정당 최대 200개의 디바이스를 등록할 수 있습니다.

**목록에서 디바이스 삭제하기:**

1. 앱스플라이어에서 오른쪽 상단의 귀사의 이메일 주소를 클릭하세요.
2. **테스트 디바이스**를 선택하세요.
3. 디바이스를 제거하려면 삭제 아이콘을 클릭하세요.

</Accordion>

## iOS 테스트 디바이스 등록

아래의 순서도는 iOS 테스트 디바이스 등록 시 고려할 수 있는 다양한 진행 절차를 설명합니다.

iOS 테스트 디바이스 등록 시 다음 옵션 중 하나를 선택하세요.

<div id="register-your-testing-device-with-idfa" />

<Accordion title="IDFA로 테스트 디바이스 등록">

#### **IDFA를 사용하여 테스트 디바이스를 등록하는 경우는 언제인가요?**

앱에 앱 추적 투명성(ATT)이 구현되어 있고 동의한 유저의 자격으로 측정을 실행하려는 경우 IDFA로 등록할 수 있습니다. 테스트한 앱을 처음 실행할 때, 앱 추적 투명성 프롬프트에서 **허용**을 클릭해야 합니다.

#### **IDFA를 사용하여 테스트 디바이스를 등록하는 방법**

IDFA에 등록하려면 앱스플라이어 디바이스 ID 앱을 사용하여 디바이스를 등록하세요.

</Accordion>

<div id="register-your-testing-device-with-idfv" />

<Accordion title="IDFV를 사용하여 테스트 디바이스를 등록하기">

#### **테스트 디바이스 등록에 IDFV를 사용하는 경우는 언제인가요?**

IDFA에 접근할 수 없을 때 IDFV가 유일한 선택입니다. 다음과 같은 경우 **IDFV를 사용해야 합니다**:

* **앱 추적 투명성이 구현되었지만** 동의하지 않은 유저로서 테스트을 실행하려고 할 때. 앱을 처음 실행할 때, 앱 추적 투명성 프롬프트에서 **허용 안 함**을 클릭하세요.
* **앱 추적 투명성이 전혀 구현되지 않았을 때**

#### **IDFV로 귀사의 디바이스를 등록하는 방법**

1. IDFV로 테스트 디바이스를 등록하기 전에, 개발자가 귀사의 테스트 디바이스에 IDFV 테스트 도구 앱을 설치해야 합니다. 개발자 지침은 귀사의 개발자에게 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-the-idfv-test-tool-app">이 문서</Anchor>를 참조하라고 하세요.
2. 개발자가 IDFV 테스트 도구 앱을 설치한 후 이를 실행하여 표시된 IDFV를 복사합니다.
3. IDFV를 사용하여 [테스트 디바이스를 수동으로 등록합니다](#register-a-device-manually).

> 📘 **참고**
>
> **IDFV 테스트 도구 앱을 설치해야 하는 이유는 무엇인가요?**
>
> * IDFV 테스트 도구는 테스트 디바이스 등록에 필요한 IDFV를 추출하는 데 사용됩니다.
> * 테스트 디바이스에 개발자 계정이 소유한 다른 앱이 설치되지 않은 경우. 이 경우 iOS는 앱을 다시 설치할 때마다 새로운 벤더 ID를 할당합니다. 테스트 시 여러 번 앱을 다시 설치하는 경우가 많기 때문에, 각 설치 시 iOS는 IDFV를 재설정합니다. **이 유틸리티 앱은 벤더에 속한 앱처럼 동작함으로써, 테스트 디바이스에서 앱을 재설치할 때마다 iOS가 새로운 IDFV를 생성하지 않도록 합니다.**

</Accordion>

<div id="dont-register-a-testing-device" />

<Accordion title="등록되지 않은 디바이스로 테스트하기">

IDFA나 IDFV로 테스트 디바이스를 등록할 수 없는 경우에만 이 옵션을 사용하세요. 이 경우 확률적 모델링이 어트리뷰션에 사용됩니다. 각 인스톨은 테스트 디바이스에서 새로운 인스톨로 기록됩니다. 다음 조건 중 하나 이상이 충족될 경우, 이 방법은 동일 디바이스에서 반복적인 테스트 설치를 등록하는 데 도움이 될 수 있습니다.

* 앱스플라이어 iOS SDK가 v6.8.0 이하입니다.
* 해당 앱에서 재설치 감지가 비활성화되었습니다(라이브 앱에는 권장되지 않음).
* 테스트 어트리뷰션 링크에 `is_retargeting="true"`이 포함되어 있습니다. 이 경우, 인스톨은 리어트리뷰션으로 기록되며, 리타겟팅 대시보드와 리타겟팅 로데이터 리포트에서 확인할 수 있습니다.
* iOS 전용: Protect360이 클릭을 프로드로 표시하는 것을 방지하려면 테스트 어트리뷰션 링크에 쿼리 파라미터 `pid="ios_testing"`을 추가하세요.

</Accordion>

<div data-zendesk-anchors="why-register-a-testing-device=%ED%85%8C%EC%8A%A4%ED%8A%B8-%EB%94%94%EB%B0%94%EC%9D%B4%EC%8A%A4%EB%A5%BC-%EB%93%B1%EB%A1%9D%ED%95%B4%EC%95%BC-%ED%95%98%EB%8A%94-%EC%9D%B4%EC%9C%A0 01H7W9EA7RQDB69QS339XFHAFZ=%ED%85%8C%EC%8A%A4%ED%8A%B8-%EB%94%94%EB%B0%94%EC%9D%B4%EC%8A%A4%EB%A5%BC-%EB%93%B1%EB%A1%9D%ED%95%B4%EC%95%BC-%ED%95%98%EB%8A%94-%EC%9D%B4%EC%9C%A0 methods-for-registering-a-testing-device=%ED%85%8C%EC%8A%A4%ED%8A%B8-%EB%94%94%EB%B0%94%EC%9D%B4%EC%8A%A4%EB%A5%BC-%EB%93%B1%EB%A1%9D%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 01H7W9EA7RRRJBFSXW3KY53R9K=%ED%85%8C%EC%8A%A4%ED%8A%B8-%EB%94%94%EB%B0%94%EC%9D%B4%EC%8A%A4%EB%A5%BC-%EB%93%B1%EB%A1%9D%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 01H7W9EA7RTTQ1FHZZ6GBGV0WP=%EC%B0%B8%EA%B3%A0 01H7W9EA7RWWNACKSEETMCP90W=supported-device-identifiers 01H7W9EA7R9A8KCNRD0BTPPQTH=%EC%B0%B8%EA%B3%A0-1 managing-testingdevice-registration=%ED%85%8C%EC%8A%A4%ED%8A%B8-%EB%94%94%EB%B0%94%EC%9D%B4%EC%8A%A4-%EB%93%B1%EB%A1%9D-%EA%B4%80%EB%A6%AC 01H7W9EA7R7SJVVQCST3WA6YBM=%ED%85%8C%EC%8A%A4%ED%8A%B8-%EB%94%94%EB%B0%94%EC%9D%B4%EC%8A%A4-%EB%93%B1%EB%A1%9D-%EA%B4%80%EB%A6%AC h_01H6V7FQFF10E4C82ZQ97PEEZA=register-a-device-using-the-appsflyer-device-id-app-admin-only 01JHJKN5Z3562N4W2H543XPC7E=android 01JHJKN5Z54T180C7G462C26Z4=ios 01JHJKN5Z51FABEGCFVTK0MPYR=windows 01JHJKTNRHHSZSC44WDWA9J2PD=android::db8cc168 01JHJKTNRJJBBA6WAC44PD33V7=ios::80f176b3 01JHJKTNRK9DY99SZ759ZGRP23=windows::6c6af14b h_01H6V7GM8KKXF8VS5ZRA4NV592=register-a-device-manually 01JHJKDZK8084GMZ9QAZPHVBHQ=ios::41efa11e 01JHJKDZK9MTNXANVEHCM18EBM=android::7db075c7 01H7W9EA7R190M9DH7GPY1VJ77=%EC%B0%B8%EA%B3%A0-2 01H7W9EA7R0KGH3YXZ9SMAFESZ=unregister-a-device registering-an-ios-testing-device=ios-%ED%85%8C%EC%8A%A4%ED%8A%B8-%EB%94%94%EB%B0%94%EC%9D%B4%EC%8A%A4-%EB%93%B1%EB%A1%9D h_01H6S2AKDH181MBDFGPBP1BQPV=ios-%ED%85%8C%EC%8A%A4%ED%8A%B8-%EB%94%94%EB%B0%94%EC%9D%B4%EC%8A%A4-%EB%93%B1%EB%A1%9D 01H7W9EA7SPA47GR1X0S9WZKDH=register-your-testing-device-with-idfa when-to-use-idfa-for-testing-device-registration=idfa%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%98%EC%97%AC-%ED%85%8C%EC%8A%A4%ED%8A%B8-%EB%94%94%EB%B0%94%EC%9D%B4%EC%8A%A4%EB%A5%BC-%EB%93%B1%EB%A1%9D%ED%95%98%EB%8A%94-%EA%B2%BD%EC%9A%B0%EB%8A%94-%EC%96%B8%EC%A0%9C%EC%9D%B8%EA%B0%80%EC%9A%94 01H7W9EA7SRD5V5134H2BRZ2AF=idfa%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%98%EC%97%AC-%ED%85%8C%EC%8A%A4%ED%8A%B8-%EB%94%94%EB%B0%94%EC%9D%B4%EC%8A%A4%EB%A5%BC-%EB%93%B1%EB%A1%9D%ED%95%98%EB%8A%94-%EA%B2%BD%EC%9A%B0%EB%8A%94-%EC%96%B8%EC%A0%9C%EC%9D%B8%EA%B0%80%EC%9A%94 how-to-register-your-testing-device-with-an-idfa=idfa%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%98%EC%97%AC-%ED%85%8C%EC%8A%A4%ED%8A%B8-%EB%94%94%EB%B0%94%EC%9D%B4%EC%8A%A4%EB%A5%BC-%EB%93%B1%EB%A1%9D%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 01H7W9EA7SBBCAP3Y24FFCCGJW=idfa%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%98%EC%97%AC-%ED%85%8C%EC%8A%A4%ED%8A%B8-%EB%94%94%EB%B0%94%EC%9D%B4%EC%8A%A4%EB%A5%BC-%EB%93%B1%EB%A1%9D%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 01H7W9EA7SNZ3ER02MBV8VJGH3=register-your-testing-device-with-idfv when-to-use-idfv-for-testing-device-registration=%ED%85%8C%EC%8A%A4%ED%8A%B8-%EB%94%94%EB%B0%94%EC%9D%B4%EC%8A%A4-%EB%93%B1%EB%A1%9D%EC%97%90-idfv%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%98%EB%8A%94-%EA%B2%BD%EC%9A%B0%EB%8A%94-%EC%96%B8%EC%A0%9C%EC%9D%B8%EA%B0%80%EC%9A%94 01H7W9EA7S3103TSHSH4XHTP1R=%ED%85%8C%EC%8A%A4%ED%8A%B8-%EB%94%94%EB%B0%94%EC%9D%B4%EC%8A%A4-%EB%93%B1%EB%A1%9D%EC%97%90-idfv%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%98%EB%8A%94-%EA%B2%BD%EC%9A%B0%EB%8A%94-%EC%96%B8%EC%A0%9C%EC%9D%B8%EA%B0%80%EC%9A%94 how-to-register-your-device-with-idfv=idfv%EB%A1%9C-%EA%B7%80%EC%82%AC%EC%9D%98-%EB%94%94%EB%B0%94%EC%9D%B4%EC%8A%A4%EB%A5%BC-%EB%93%B1%EB%A1%9D%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 01H7W9EA7SGTDQCRVJKKRH0EVT=idfv%EB%A1%9C-%EA%B7%80%EC%82%AC%EC%9D%98-%EB%94%94%EB%B0%94%EC%9D%B4%EC%8A%A4%EB%A5%BC-%EB%93%B1%EB%A1%9D%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 01H7W9EA7SHVSDPJN8P2WBSFN1=%EC%B0%B8%EA%B3%A0-3 01H7W9EA7S3KJ89AN9ZBMHFGRR=dont-register-a-testing-device" />
