---
title: 멀티 스토어 안드로이드 어트리뷰션 설정
metadata:
  keywords:
    - Android
    - Google
    - Google Play
    - Add App
    - amazon
    - Advertisers
    - Agencies
    - baidu
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2015-12-24T10:48:17Z'
  edited_at: '2026-10-14T10:39:44Z'
  id: 207447023
  locale: ko
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/ko/articles/207447023
---
> **한눈에 보기:** 요약: 여러 안드로이드 스토어에서 앱을 어트리뷰트하고 단일 앱 대시보드 또는 스토어별 앱 대시보드에서 데이터를 봅니다.

<div id="multi-store-android-attribution" />

## 멀티 스토어 Android 어트리뷰션

앱스플라이어는 앱 스토어와 상관없이 앱을 어트리뷰트합니다. Google Play 스토어 및 Amazon, Opera, GetJar, Baidu 및 Huawei와 같은 타사 안드로이드 앱 스토어를 의미합니다. (일명 아웃 오브 마켓 스토어 또는 대체 안드로이드 앱 스토어.) 여러 스토어를 통해 앱을 마케팅하는 앱 담당자는 모든 스토어의 데이터가 함께 포함된 **단일** **대시보드** 또는 **스토어별 대시보드** 중에서 선택할 수 있습니다.

<div id="note" />

> 📘 **참고**
>
> * 앱스플라이어 안드로이드 어트리뷰션은 GAID 및 <Anchor target="_blank" href="/marketers/ko/docs/android-oaid-implementation-in-the-sdk">OAID</Anchor>를 포함한 모든 디바이스 식별자 유형을 지원합니다.
> * 중국에서 판매되는 앱의 경우 <Anchor target="_blank" href="/marketers/ko/docs/measure-attribution-in-the-chinese-domestic-market">중국 국내 시장에서 안드로이드 앱 어트리뷰트</Anchor>를 참조하십시오.

<Image align="center" alt="DashboardType_us-en-new.jpg" src="https://files.readme.io/10fdd08c4e57f799756f46922b5f8dc45c67f7550f9105e65076652f459c98f7-9545756936593.jpg" />

<div id="single-dashboard-vs-dashboard-per-store" />

### 단일 대시보드 대 스토어 대시보드

* 단일 대시보드 단일 대시보드: Google Play 스토어를 포함한 모든 스토어의 데이터를 결합하는 하나의 대시보드
* 스토어 대시보드 즉, 앱을 제공하는 스토어 수만큼 대시보드가 있습니다.

<table><thead><tr><th> </th><th>단일 대시보드<br/>[모범 사례]</th><th> 스토어별 대시보드</th></tr></thead><tbody><tr><td><span id="android-package-name"></span>안드로이드 패키지 이름</td><td colspan="2">선택한 옵션에 관계없이 동일한(동일한) 패키지 이름을 사용하십시오.  </td></tr><tr><td><span id="channel-name"></span>채널명</td><td>설정할 결과 없음</td><td><ul><li> <span>안드로이드 아웃 어브 마켓 APK</span> 옵션을 사용하여 앱스플라이어 대시보드에 앱을 추가할 때 채널을 설정하십시오.</li><li><span>채널은 스토어를 식별합니다. </span></li><li>안드로이드 패키지 이름과 채널의 조합은 각 앱스플라이어 대시보드를 고유하게 식별합니다.  </li><li>예시: 예: Android 패키지 이름은 com.abc.def이고 채널은 xyzdevicestore입니다. 고유한 대시보드 식별자는 com.abc.def-xyz_device_store입니다.  </li><li>APK에 채널 설정이 있지만 이 설정이 있는 앱이 없는 경우 트래픽은 Google Play 스토어인 빈 채널 설정이 있는 앱인 기본 앱에 어트리뷰트합니다.  </li></ul></td></tr><tr><td><span id="populating-the-install_app_store-field"></span>install_app_store 필드 채우기</td><td><ul><li>다운로드를 통해 앱을 제공하는 스토어를 고유하게 식별합니다.</li><li>Google Play 스토어의 경우 공백입니다.  </li><li>스토어 이름은 <a href="./set-up-multi-store-android-attribution#single-dashboard-apk-preparation">manifest/APK</a>에 설정됩니다.</li></ul></td><td>해당 없음</td></tr><tr><td><span id="onelink-template"></span><a href="./create-a-onelink-template#원링크-템플릿-만들기" target="_blank">원링크 템플릿</a></td><td>원링크로 작업할 때 이 방법을 권장합니다.  </td><td>해당 없음 </td></tr><tr><td><span id="measurementattribution-links"></span>측정/어트리뷰션 링크  </td><td><ul><li>링크는 스토어에 상관없이 동일합니다.</li><li>올바른 저장소로 리디렉션하려면 <a href="./set-up-multi-store-android-attribution#single-dashboard-attribution-links">af_r</a>을 사용하여 리디렉션 URL을 설정하십시오.</li></ul></td><td><ul><li>각 스토어마다 고유한 링크가 필요합니다.</li><li> <strong>활성 연동</strong> 페이지를 사용하여 이들을 생성합니다.</li><li>앱 ID는 안드로이드 패키지 이름에 추가된 채널 이름입니다. 예: com.abc.def-def_store.<br/>따라서 어트리뷰션 링크가 다릅니다.</li></ul></td></tr><tr><td><span id="reporting-options-available-having-install_app_store-field"></span>install_app_store 필드가 있는 리포트 옵션 사용 가능</td><td>  </td><td>해당 없음 </td></tr><tr><td><span id="considerations"></span>고려 사항</td><td><ul><li>어트리뷰션 정확도  </li><li><span>오가닉 인스톨은 하나의 대시보드 아래 모든 스토어의 APK 오가닉 인스톨을 반영합니다.</span></li><li><span>스토어별로 세분화된 리포트 옵션은 현재 개요, 코호트 및 로데이터로 제한됩니다.</span></li></ul></td><td><ul><li>어트리뷰션 정확도 </li><li> <span>앱스플라이어</span>의 별도 앱 대시보드에서 스토어(채널)별 오가닉 및 논오가닉 인스톨 및 인앱이벤트 데이터를 봅니다.</li><li><span>코호트를 사용하여 모든 스토어에 대해 결합된 리포트를 함께 표시</span></li><li>협력하는 파트너가 <strong>모든</strong> 대시보드에서 <a href="./partner-activation-deactivation" target="_blank">활성</a> 상태(<strong>파트너 활성화</strong>가 켜져 있음)인지 확인합니다. 이는 불일치를 방지하기 위한 것입니다(데이터를 SRN과 비교할 때 더 일반적임). </li></ul></td></tr></tbody></table>

<div id="set-up-tasks" />

## 설정 작업

다음 워크플로는 원하는 옵션을 설정하는 데 필요한 활동을 기재합니다. 작업은 마케터와 개발자로 나뉩니다.

스토어별 대시보드 옵션의 경우 각 스토어에 대해 태스크를 반복하십시오.

<div id="before-you-begin" />

### **시작하기 전에**

* 채널 및 install\_app\_store 파라미터의 이름 지정 규칙을 결정하십시오.
* 채널 및 스토어를 매핑하려면 다음 명명 표를 사용하십시오.
* 이 테이블은 개발자가 APK를 준비하는 데 사용합니다.

<table><thead><tr><th>파라미터</th><th>지침</th><th>단일 대시보드<br/>[모범 사례]</th><th>스토어별 대시보드</th></tr></thead><tbody><tr><td>안드로이드 패키지 이름</td><td>모든 대시보드 옵션에 대해 동일한 패키지 이름</td><td colspan="2">앱이 이미 Google Play 스토어에 있는 경우 기존 패키지 이름을 사용합니다. 예: comb.abc.def</td></tr><tr><td>채널명</td><td>각 스토어에 대한 고유한 가치.</td><td>설정되지 않음. 공백으로 남겨 둡니다.  </td><td><p>스토어마다 고유합니다. 스토어용으로 준비한 개별 APK와 앱스플라이어에서 앱 추가 시 값을 설정하십시오.  </p><p>Google Play 스토어 APK용 채널을 설정하지 마십시오.  </p></td></tr><tr><td>인스톨 앱 스토어 AF_STORE</td><td>스토어를 식별하는 고유한 값</td><td>스토어마다 고유합니다. 매니페스트를 통해 APK에서 설정합니다. 각 스토어에는 자체 APK가 있습니다. </td><td> 설정되지 않음.</td></tr></tbody></table>

<div id="tasks" />

### 작업

| 단계 | 책임 | 단일 대시보드 | 스토어별 대시보드 |
| --- | --- | --- | --- |
| 1 | 개발자 | [APK 준비](/docs/set-up-multi-store-android-attribution#single-dashboard-apk-preparation) | [APK 준비](/docs/set-up-multi-store-android-attribution#dashboard-per-store-apk-preparation) |
| 2 | 마케터 | 조치가 필요하지 않습니다. 앱이 이미 앱스플라이어에서 활성화되어 있다고 가정합니다. | 앱스플라이어에 [앱을 추가](/docs/set-up-multi-store-android-attribution#dashboard-per-store-adding-the-app)합니다. |
| 3 | 마케터 | [어트리뷰션 링크 준비](/docs/set-up-multi-store-android-attribution#single-dashboard-attribution-links) | 채널 이름과 결합된 앱 ID로 어트리뷰션 링크를 준비합니다. |
| 4 | 개발자 및 마케터 | [테스트](/docs/set-up-multi-store-android-attribution#testing-both-dashboard-options) | [테스트](/docs/set-up-multi-store-android-attribution#testing-both-dashboard-options) |

<div id="note-1" />

<div id="procedures" />

## 절차

<div id="single-dashboard-apk-preparation" />

<Accordion title="단일 대시보드 - APK 준비">

안드로이드 패키지 이름은 어트리뷰션 데이터를 포함할 대시보드를 결정합니다. 단일 대시보드 방식에서는 모든 스토어가 동일한 안드로이드 패키지 이름을 갖습니다.  여기에는 채널 파라미터의 개념이 없습니다.

다운로드 스토어의 식별은 이 섹션에 설명된 대로 SDK에 설정된 AF\_STORE 매개 변수를 통해 이루어집니다.   AF\_STORE 파라미터는 대소문자를 구분하지 않습니다. 예를 들어, ABC, abc, Abc.

**APK를 준비하려면:**

1. 앱 빌드의 복사본을 만듭니다. **참고**: 참고: 안드로이드 패키지 이름을 변경하지 마십시오.
2. 개별 스토어를 식별하려면 다음 방법 중 하나를 사용하십시오.
   * AndroidManfest.xml의 `<application>` 태그 내에 다음을 추가하여 스토어를 식별합니다. AF\_STORE 파라미터를 앱 스토어 이름으로 설정합니다.

     ```xml
     <application>
        ...
        <meta-data android:name="AF_STORE" android:value="EnterStoreNameHere"/>
        ...
     </application>
     ```

     **--또는--**
   * API 메서드 API 방식: 대체 앱 스토어마다 별도의 APK를 준비합니다. setOutOfStore API를 호출하여 AF\_STORE 값을 설정하십시오. 각 스토어에 대해 고유한 값을 설정하십시오.  

     ```java
     AppsFlyerLib.getInstance().setOutOfStore("EnterStoreNameHere")
     ```

여기에서 설정한 값은 앱스플라이어 로데이터 install\_app\_store 필드에 나타납니다. 이 필드는 다음에서 사용할 수 있습니다.

* 개요 대시보드
* 코호트 대시보드
* <Anchor target="_blank" href="/marketers/ko/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">로데이터 리포트</Anchor> (로데이터 리포트는 앱스플라이어 프리미엄 기능입니다)

</Accordion>

<div id="single-dashboard-attribution-links" />

<Accordion title="단일 대시보드 - 어트리뷰션 링크">

1. 이렇게 하면 어트리뷰션 링크에 af\_r 매크로가 채워져 사용자를 올바른 앱 스토어 방문 페이지로 리디렉션합니다. 예를 들어:   
   **참고:** <Anchor target="_blank" href="/marketers/ko/docs/app-settings#outofstore-app-url">더 알아보기</Anchor>
2. 스토어 랜딩 페이지 URL로 af\_r 매크로를 채우십시오.
3. 추가 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#어트리뷰션-링크-파라미터">어트리뷰션 링크 파라미터</Anchor>를 설정합니다.
4. 스토어 외 미디어 소스는 **어트리뷰션을 위해 ID 일치를 사용**하고 앱스플라이어 <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-attribution-model#probabilistic-modeling">확률 모델링</Anchor>은 대체 방법으로 사용됩니다.
5. 링크 URL에 하나 이상의 사용자 ID 자리 표시자를 추가합니다.
   * `android_id`
   * `advertising_id`
   * `oaid`
6. 어트리뷰션 링크를 복사하여 광고 네트워크 파트너에게 제공합니다.

</Accordion>

<div id="dashboard-per-store-apk-preparation" />

<Accordion title="스토어별 대시보드 - APK 준비">

매니페스트에 설정된 채널 파라미터와 결합된 안드로이드 패키지 이름은 어트리뷰션 데이터를 포함할 스토어 대시보드를 결정합니다.

**각 스토어에 대해 별도의 APK/매니페스트를 준비하려면:**

* AndroidManfest.xml의 `<application>` 태그 내에 다음을 추가하여 스토어를 식별합니다. 채널 파라미터를 앱 스토어 이름으로 설정합니다.

  ```xml
  <application>
       ...
       <meta-data android:name="CHANNEL" android:value="EnterStoreNameHere"/>
       ...
  </application>
  ```

  **참고: 메모: 매개 변수는 대소문자를 구분합니다.  참고: 채널 이름에는 대문자 또는 소문자(a-z 또는 A-Z)만 사용해야 합니다. 하이픈(-)이나 밑줄(\_) 등 다른 문자는 사용할 수 없습니다.**

</Accordion>

<div id="dashboard-per-store-adding-the-app" />

<Accordion title="스토어별 대시보드 - 앱 추가">

APK/매니페스트에 설정된 안드로이드 패키지 이름과 채널의 조합으로 식별되는 대시보드(앱)를 추가합니다. 예시: 예: 안드로이드 패키지 이름은 com.myapp이고 채널 이름은 abcstore이고 고유한 대시보드 이름은 com.myapp—abcstore입니다.

**앱스플라이어에서 스토어별로 대시보드를 추가하려면**:

1. 앱스플라이어의 사이드 메뉴에서 **설정** > **내 앱**을 선택하고 **앱 추가**를 클릭합니다.
2. **안드로이드 > 타사 스토어**를 선택합니다.
3. 완료:
   * **안드로이드 패키지 이름**
   * 채널명 채널 이름: 패키지명이 동일한 대시보드를 구분하기 위한 고유식별자(스토어 이름)입니다. 스토어용으로 준비된 APK에서 동일한 값을 사용하고 있는지 확인하십시오.  
     **참고:** 참고: 채널 이름에는 대문자 또는 소문자(a-z 또는 A-Z)만 사용해야 합니다. 하이픈(-)이나 밑줄(\_) 등 다른 문자는 사용할 수 없습니다.
   * **앱 URL:**
     * 어트리뷰션 링크에서 af\_r 매크로를 채우는 기본 URL 다운로드 주소를 포함합니다. APK가 호스팅되는 URL 또는 방문 페이지 URL을 입력하십시오.
     * 어트리뷰션 링크를 생성할 때 이를 변경할 수 있습니다.
4. **다음**을 클릭합니다.
5. 인터페이스의 지침에 따라 앱 추가를 완료하십시오.

</Accordion>

<div id="testing-both-dashboard-options" />

<Accordion title="테스트 - 두 대시보드 옵션">

<div id="non-organic-installs" />

#### **논오가닉 인스톨**

**논오가닉 인스톨을 테스트하려면:**

1. 앱을 인스톨하지 않은 안드로이드 기기를 사용하거나 기기를 <Anchor target="_blank" href="/marketers/ko/docs/registering-test-devices">등록하십시오</Anchor> .
2. <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">OneLink 링크</Anchor>를 사용하여 테스트 어트리뷰션 링크를 생성하십시오. 테스트를 미디어 소스 이름으로 사용하십시오("&pid=test").
3. 클릭 URL에 GAID, OAID 또는 안드로이드 ID인 광고 ID를 추가합니다.

   ```http
   https://app.appsflyer.com/com.greatapp?pid=test
   &af_r=https://www.destinationurl.com&advertising_id=b5a3-78d9b5-0f12345-xxxx
   ```

   이메일을 통해 자신에 대한 어트리뷰션 링크를 보내고 그것을 클릭하십시오. **리디렉션한 후에는 스토어에서 설치하지 않습니다**. 대신에, 업데이트된 베타 버전 앱을 앱스플라이어의 트래킹 SDK 임베디드와 함께 설치하고 실행합니다.

| 단일 대시보드 | 스토어별 대시보드 |
| --- | --- |
| <ol><li>데이터 내보내기 페이지에서 앱의 인스톨 로데이터 리포트를 확인합니다.</li><li>테스트 미디어 소스와 함께 하나의 인스톨 전환이 표시되어야 합니다. **앱 스토어 설치** 라는 열 아래에 manifest.xml 파일에 표시되는 스토어 이름이 표시되어야 합니다.</li></ol> | <ol><li>필요한 스토어별 앱 대시보드로 이동합니다.</li><li>데이터 내보내기 페이지나 앱의 개요 페이지에서 앱의 인스톨 로데이터 리포트를 확인합니다.</li><li>인스톨 전환 하나가 "test" 미디어 소스로 되어 있는 것을 볼 수 있습니다.</li></ol> |

<div id="organic-installs" />

#### **오가닉 설치**

**오가닉 인스톨을 테스트하려면:**

1. 앱이 인스톨되지 않았거나 <Anchor target="_blank" href="/marketers/ko/docs/registering-test-devices">등록된</Anchor> 안드로이드 기기를 사용합니다.
2. 업데이트된 베타 버전 앱을 앱스플라이어의 트래킹 SDK 임베디드와 함께 설치하고 실행합니다.
3. 결과 확인:

<div id="expected-results" />

#### 예상 결과

| 단일 대시보드 | 스토어별 대시보드 |
| --- | --- |
| 새로운 오가닉 인스톨에 대한 개요 페이지를 확인하십시오("오가닉" 미디어 소스 아래). 현재 단일 앱 방식으로는 오가닉 인스톨의 출처에 대한 표시가 없습니다. | <ol><li>테스트한 스토어로 지정된 앱의 대시보드와 개요 페이지로 이동합니다.</li><li>인스톨 전환 하나가 "오가닉" 미디어 소스 아래에 있는 것을 볼 수 있습니다.</li></ol> |

</Accordion>

<div id="3rd-party-raw-data" />

<div id="additional-features" />

## 추가 기능

<div id="driving-users-to-the-amazon-app-store-from-facebook" />

<Accordion title="사용자를 페이스북에서 아마존 앱 스토어로 유도">

1. 메타 앱 설정의 안드로이드 **섹션**에서 앱에 대한 URL 링크를 구성합니다 .
2. 메타에 앱 관리자로 로그인하고 <Anchor target="_blank" href="https://developers.facebook.com/apps/">[https://developers.facebook.com/apps/](https://developers.facebook.com/apps/)로 이동하여</Anchor> , 앱을 선택합니다.
3. 설정으로 이동하여 안드로이드 설정을 찾거나, 아직 안드로이드를 구성하지 않았으면 플랫폼을 추가합니다.
4. 앱 특정의 Amazon 앱 스토어 URL과 같은 필수 세부 항목을 입력합니다.  

   <Image align="center" alt="outofstore_1.png" src="https://files.readme.io/1e8c365176ac9e0e55360a8a5db1dd549518e477f3fba43206491bcf9a3023da-115010742229.png" />
5. 앱스플라이어 대시보드의 활성 연동 아래에서 메타 광고를 선택하고 앱스플라이어로 메타 스토어 내 모바일 앱 인스톨 광고를 기록할 때 사용한 것과 동일한 페이스북 앱 ID를 입력합니다.

</Accordion>

<div id="getting-the-data-appsflyer-reports" />

<Accordion title="데이터 가져오기 - 추가 앱스플라이어 리포트">

개요 대시보드 외에도 앱스플라이어에서 다음과 같은 리포팅 방법을 사용할 수 있습니다.

* 코호트:
  * 단일 리포트에서 여러 대시보드(앱) 결합
  * install\_app\_store별로 분류하여 각 대시보드의 성능을 봅니다.
* Pull API(단일 앱 방식)
* 커스텀 대시보드(여러 앱 방식)

</Accordion>

<div id="referrer-implementation-thirdparty-android-app-stores" />

<Accordion title="리퍼러 구현 - 타사 안드로이드 앱 스토어">

앱스플라이어와 리퍼러 어트리뷰션 통합이 있는 타사 안드로이드 스토어

| 타사 앱 스토어 | 시작: | SDK 버전 |
| --- | --- | --- |
| <span id="huawei-app-store"></span>Huawei 앱 스토어 | 2020년 7월 | 6.14.0 + |
| <span id="samsung-galaxy-store"></span>삼성 갤럭시 스토어 | 2020년 12월 | 6.1.1 + |
| <span id="xiaomi-getapps-store"></span>Xiaomi GetApps 스토어 | 2022년 9월 | 6.9.0 + |

</Accordion>

타사 스토어 리퍼러에 의한 어트리뷰션은 다음과 같이 로데이터 리포트에 반영됩니다.

* 검색 유형: 어트리뷰트된 타사 스토어의 이름입니다. 예를 들어:
* 기여자 기여자: 사용자가 앱을 인스톨하기 전에 여러 앱 스토어에 인게이지했다면 앱스플라이어는 이러한 인게이지먼트를 기여자로 간주합니다. 인스톨은 라스트 클릭 인게이지먼트에 부여됩니다. 예시:
  * 사용자가 Google에서 제공하는 광고를 클릭하면 Play 스토어로 리디렉션됩니다.  사용자가 앱을 다운로드하지 않습니다.
  * 사용자가 다른 광고를 클릭하면 Samsung Galaxy 스토어로 리디렉션됩니다. 사용자가 앱을 다운로드하고 인스톨합니다.
  * 어트리뷰션은 사용자를 Samsung Galaxy 스토어로 리디렉션하도록 하는 광고 네트워크에 부여됩니다. Google은 기여자로 인정됩니다.


<div id="troubleshooting" />

## 문제 해결

<div id="installs-attributed-to-the-default-app" />

### 기본 앱으로 인한 인스톨 수

기본 앱이 없으면 해당 앱에 대한 데이터가 기록되지 않습니다.

<div id="traits-and-limitations" />

## 특징 및 제약 사항

| 특징 | 비고 |
| --- | --- |
| 여러 앱 스토어로 원링크 리디렉션 | 앱 패키지 이름이 모든 앱 스토어에 대해 동일하고 단일 대시보드 옵션을 구현하는 경우 <Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template#원링크-템플릿-만들기">원링크 템플릿</Anchor>에 여러 앱 스토어를 설정할 수 있습니다. |
| 애플 앱 스토어 설치 | 이 파라미터는 에이전시 또는 애드 네트워크에서는 사용할 수 없습니다. |
|  |  |
| 광고 수익 |  |

<div data-zendesk-anchors="multistore-android-attribution=%EB%A9%80%ED%8B%B0-%EC%8A%A4%ED%86%A0%EC%96%B4-android-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 h_01HJ369QB8PDKG7QQRV840KRAY=%EB%A9%80%ED%8B%B0-%EC%8A%A4%ED%86%A0%EC%96%B4-android-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 h_01HJ369QB876GZKQCGJZQDXDRF=%EC%B0%B8%EA%B3%A0 single-dashboard-vs-dashboard-per-store=%EB%8B%A8%EC%9D%BC-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C-%EB%8C%80-%EC%8A%A4%ED%86%A0%EC%96%B4-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C h_01HJ369QB8SRN61ABBZ51TKFX2=%EB%8B%A8%EC%9D%BC-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C-%EB%8C%80-%EC%8A%A4%ED%86%A0%EC%96%B4-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C reporting-options-available-having%C2%A0install_app_store-field=reporting-options-available-having-install_app_store-field setup-tasks=%EC%84%A4%EC%A0%95-%EC%9E%91%EC%97%85 h_01HJ369QB8NPE8FAHR42D2YN0K=%EC%84%A4%EC%A0%95-%EC%9E%91%EC%97%85 before-you-begin=%EC%8B%9C%EC%9E%91%ED%95%98%EA%B8%B0-%EC%A0%84%EC%97%90 h_01JD2DEXW74MFE44FM3S0JCK5Q=%EC%8B%9C%EC%9E%91%ED%95%98%EA%B8%B0-%EC%A0%84%EC%97%90 tasks=%EC%9E%91%EC%97%85 h_01JD2DFF2K0APZ98JV1X09ZB33=%EC%9E%91%EC%97%85 procedures=%EC%A0%88%EC%B0%A8 h_01HJ369QB990HH38TRQESQVFWN=%EC%A0%88%EC%B0%A8 single-dashboard%E2%80%94apk-preparation=single-dashboard-apk-preparation h_01HJ369QB9V3W9R3EB6SJSNBED=single-dashboard-apk-preparation single-dashboard%E2%80%94attribution-links=single-dashboard-attribution-links h_01HJ369QB9H3J6E892X4V15AYJ=single-dashboard-attribution-links dashboard-per-store%E2%80%94apk-preparation=dashboard-per-store-apk-preparation h_01HJ369QB9SP4DHZM5JB0RKEWG=dashboard-per-store-apk-preparation dashboard-per-store%E2%80%94adding-the-app=dashboard-per-store-adding-the-app h_01HJ369QB9X58DVBTWVWD0GCAV=dashboard-per-store-adding-the-app testing%E2%80%94both-dashboard-options=testing-both-dashboard-options h_01HJ369QB97FN9BJKD9WRW99YG=testing-both-dashboard-options nonorganic-installs=%EB%85%BC%EC%98%A4%EA%B0%80%EB%8B%89-%EC%9D%B8%EC%8A%A4%ED%86%A8 h_01HJ369QB93A3ZZFAF0JAEXFRR=%EB%85%BC%EC%98%A4%EA%B0%80%EB%8B%89-%EC%9D%B8%EC%8A%A4%ED%86%A8 organic-installs=%EC%98%A4%EA%B0%80%EB%8B%89-%EC%84%A4%EC%B9%98 h_01HJ369QB9SA05Y8VES8DD1FY4=%EC%98%A4%EA%B0%80%EB%8B%89-%EC%84%A4%EC%B9%98 expected-results=%EC%98%88%EC%83%81-%EA%B2%B0%EA%B3%BC h_01HJ369QBAJADS4SMSDPKK9RHW=%EC%98%88%EC%83%81-%EA%B2%B0%EA%B3%BC additional-features=%EC%B6%94%EA%B0%80-%EA%B8%B0%EB%8A%A5 h_01HJ369QBAQ49ACSG3VEGSH7D4=%EC%B6%94%EA%B0%80-%EA%B8%B0%EB%8A%A5 h_01HJ369QBA1XVMZD4G019T2S9W=driving-users-to-the-amazon-app-store-from-facebook h_01HJ369QBA2WDAZNNPRRWA3MRT=getting-the-data-appsflyer-reports referrer-implementation%E2%80%94thirdparty-android-app-stores=referrer-implementation-thirdparty-android-app-stores h_01HJ369QBA4D0SG9MQE6MXB0DH=referrer-implementation-thirdparty-android-app-stores troubleshooting=%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0 01JBKV47A5YJXKYHWA7H8NQAAF=%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0 installs-attributed-to-the-default-app=%EA%B8%B0%EB%B3%B8-%EC%95%B1%EC%9C%BC%EB%A1%9C-%EC%9D%B8%ED%95%9C-%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%88%98 h_01HJ369QBANRCTCFKTGK8BTQEC=%EA%B8%B0%EB%B3%B8-%EC%95%B1%EC%9C%BC%EB%A1%9C-%EC%9D%B8%ED%95%9C-%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%88%98 traits-and-limitations=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD h_01HJ369QBAJA87QJNTYNWYX82N=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD" />
