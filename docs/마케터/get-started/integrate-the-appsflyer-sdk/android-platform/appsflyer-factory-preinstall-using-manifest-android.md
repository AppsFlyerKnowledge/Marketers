---
title: 매니페스트를 사용한 앱스플라이어 공장 사전 설치(안드로이드)
metadata:
  keywords:
    - Android
    - Pre-Install
    - Attribution
    - Metrics
    - Advertisers
    - Agencies
    - af_pre_install_name
    - Developers
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
  created_at: '2014-10-13T11:14:04Z'
  edited_at: '2026-10-14T10:39:49Z'
  id: 207032166
  locale: ko
  section: Android platform
  section_id: 6551190827921
  url: https://support.appsflyer.com/hc/ko/articles/207032166
---
> **요약:** 공장 출하 전에 디바이스에 추가된 앱에 대해 앱 인스톨을 디바이스 제조업체로 어트리뷰션합니다. **참고**: <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-attribution-model#preload-campaigns">다른 모든 프리로드 어트리뷰션 방법</Anchor>을 참조하십시오.

![pre-install-intro-breakdown.png](https://files.readme.io/cb21162bd0fa0850cdfd7d380841ca47eda40173f5a05b95dab87bf602583d25-51857559113617.png)

<div id="introduction" />

## 소개

<div id="what-is-a-pre-install-campaign" />

### 사전 설치 캠페인이란 무엇입니까?

사전 설치 캠페인을 통해 온라인 캠페인을 운영하지 않고도 광범위한 오디언스에 도달할 수 있습니다.

사전 설치 캠페인에서 앱 소유자는 디바이스 제조업체에 **공장 출하 전 디바이스에 앱을 사전 설치**하도록 요청할 수 있습니다.

사전 설치 캠페인은 앱 소유자를 대신하여 다양한 제조업체와 협력하는 제3 당사자 매체 소스와의 협업일 수도 있습니다.

> 🚧 **Important!**
>
> 앱스플라이어는 앱이 처음으로 실행되었을 때 인스톨수를 집계합니다. 따라서 표시되는 사전 인스톨 수는 앱을 사전 인스톨한 디바이스의 수가 아니라 앱을 실행한 사용자 수입니다.

<div id="benefits-of-recording-installs-from-pre-install-campaigns" />

### 사전 설치 캠페인으로 인한 인스톨 기록의 이점

어트리뷰션된 사전 인스톨 캠페인을 통해 측정할 수 있는 항목:

* 사전 설치된 앱을 실행한 사용자 수
* 각 제조업체가 제공하는 앱 사용자 수
* 각 사용자의 LTV(유저생애가치)를 판단하여 어떤 제조업체가 고부가가치 사용자를 유입시키는지 파악

<div id="how-can-i-measure-pre-install-campaigns" />

### 사전 설치 캠페인은 어떻게 측정합니까?

사전 인스톨 캠페인을 측정하는 방법에는 네 가지가 있습니다. 자세한 내용은 본 문서의 [설정 섹션](/docs/appsflyer-factory-preinstall-using-manifest-android#설정)을 참조하세요.

<div id="viewing-pre-install-data" />

### 사전 설치 데이터 보기

사전 설치는 다른 인스톨 이벤트와 마찬가지로 앱스플라이어 대시보드에 어트리뷰트된 미디어 소스 아래에 표시됩니다. 그러나 캠페인 이름은 항상 **사전 설치**입니다.

> 📘 **Note**
>
> [SDK API 메서드](/docs/appsflyer-factory-preinstall-using-manifest-android#sdk-api-method)를 사용하여 사전 설치에 대해 다른 캠페인 이름을 지정할 수 있습니다.

> 📘 **Note**
>
> 2022년 5월 24일부터:
>
> * 공장 사전 설치 캠페인의 Match\_type은 로데이터 리포트에 `preload_conf`으로 표시됩니다.
> * 앱스플라이어는 프리로드를 유도한 애드 네트워크와 첫 번째 앱 실행에 기여한 광고 네트워크를 대시보드에표시합니다. <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-attribution-model#preload-campaigns">프리로드 캠페인</Anchor>에 대해 자세히 알아보십시오.

<div id="setup" />

## 설정

사전 설치 캠페인을 측정하려면 다음 방법 중 하나를 선택하십시오.

| 메서드 이름 | 다중 APK가 필요합니까? | 사전 설치 어트리뷰션을 보장합니까? | 미디어 소스나 제조업체의 조치가 필요합니까? |
| --- | --- | --- | --- |
| 시스템 속성 | No | Yes | Yes |
| SDK API | Yes | 아니오 | No |
| 매니페스트 파일의 이름 | Yes | 아니오 | No |
| 경로 | No | No | Yes |

<div id="system-properties-method-recommended" />

<Accordion title="시스템 속성 메서드(권장)">

SDK 버전 `V4.0+`을 사용하십시오.

이 메서드는 가장 강력하므로 권장되지만, 모든 후속 앱 인스톨에 대해 사전 설치 미디어 소스가 항상 어트리뷰션된다는 점을 고려하십시오. 이것은 신규설치든 재설치든 관계없이 적용됩니다.

시스템 속성 방법을 사용하려면 개발자와 제조업체 모두의 조치가 필요합니다.

<div id="developer" />

#### 개발자

제조업체나 미디어 소스에 APK를 제공해야 합니다. 기본 APK가 제공됩니다. 이 메서드에는 별도의 APK가 필요하지 않습니다.

`pre_install.appsflyer`라는 파일을 만드십시오. 파일에 키-값 쌍을 추가하십시오:

`=`

예를 들어:

`com.appsflyer.sampleapp=huawei`

**추가 사전 설치 파라미터를 지정하는 방법:**

**pre\_install.appsflyer** 파일에 추가 파라미터를 JSON 형식으로 전달하십시오. 예를 들어:

```json
com.appsflyer.sampleapp={"pid":"huawei", "c":"special_campaign","af_adset":"some_adset"}
```

> 🚧 **Important!**
>
> 이 옵션을 사용할 때 다음 동작에 유의하십시오:
>
> * 원시 데이터에서는 채널을 '사전 설치'로 설정합니다.
> * JSON에 `pid` 파라미터가 없으면 미디어 소스는 원시 데이터에서 'None'으로 표시됩니다.
> * JSON 설정에서 `c` 파라미터가 없으면 캠페인 이름은 '사전 설치'로 설정됩니다.
> * JSON 형식이 잘못된 경우, 전달된 문자열은 미디어 소스 이름으로 간주됩니다.

pre\_install.appsflyer 파일이 있으면 APK와 함께 미디어 소스나 제조업체에 제공하십시오.

<div id="manufacturer" />

#### 제조업체

제조업체는 ***pre\_install.appsflyer*** 파일을 선택한 경로에 배치합니다. **pre\_install.appsflyer** 파일 권한을 744로 설정하십시오.

그런 다음 제조업체는 시스템 속성 파일을 편집하여 ***pre\_install.appsflyer*** 파일을 가리키도록 합니다. 이를 위해 제조업체는 시스템 속성에 키-값 쌍을 추가해야 합니다.

> 📘 **Note**
>
> 이 단계에서는 루트 권한이 필요합니다. 사전 설치 구성을 테스트할 때도 루트 권한이 필요합니다. 자세한 내용은 [테스트 섹션](/docs/appsflyer-factory-preinstall-using-manifest-android#사전-인스톨-설정-테스트)을 참조하십시오.

**안드로이드 시스템 속성에 키-값 쌍 추가:**

```bash
adb shell su
setprop ro.appsflyer.preinstall.path /data/pre_install.appsflyer
```

또 다른 메서드로는 안드로이드 파일 시스템에서 시스템 속성 파일을 검색하여 편집한 후 다시 푸시하는 방법이 있습니다.

```bash
adb root
adb remount
adb pull /system/build.prop
echo ro.appsflyer.preinstall.path=/data/pre_install.appsflyer >> build.prop
adb push build.prop /system/build.prop
adb shell chmod 744 /system/build.prop
adb reboot
```

<div id="advantages" />

#### 장점

미디어 소스나 제조사마다 다른 APK를 유지할 필요가 없습니다. 구글 플레이에서 앱을 변경하거나 경로를 추가할 필요가 없습니다. 제조업체는 커스텀 경로를 사용할 수 있으며, 서로 다른 기기에서 운영되는 여러 사전 설치된 앱 사이에 종속성이 없습니다.

이 메서드는 사전 설치 캠페인 및 미디어 소스로 어트리뷰션을 보장합니다. 유저가 앱을 실행하기 전에 업데이트하더라도, 혹은 광고를 클릭한 후 인스톨하더라도 사전 설치는 여전히 사전 설치 미디어 소스나 제조업체로 어트리뷰션됩니다.

<div id="disadvantages" />

#### 단점

일부 책임이 미디어 소스나 제조업체로 이전됩니다. 개발자는 제조업체나 미디어 소스가 필요한 단계를 수행하는지 반드시 확인해야 합니다. 또한, 이 메서드는 앱 개발자가 시험하기에 조금 더 어려울 수 있습니다.

</Accordion>

<div id="sdk-api-method" />

<Accordion title="SDK API 메서드">

SDK API 메서드는 사전 인스톨이 어트리뷰트되는 제조업체나 미디어 소스 이름을 지정할 수 있는 기본 방법을 제공합니다.

이 메서드를 사용하려면 SDK를 초기화하기 전에 AFApplication 클래스에 다음 메서드 호출을 추가합니다.

`setPreinstallAttribution(String mediaSource, String campaign, String siteId)`

<div id="when-working-with-a-media-source" />

#### 미디어 소스와 협업할 때

```java
AppsFlyerLib.getInstance().setPreinstallAttribution("MEDIA_SOURCE_NAME", "CAMPAIGN_NAME", "123");
AppsFlyerLib.getInstance().init(AF_DEV_KEY , conversionListener , getApplicationContext());
```

<div id="when-working-with-a-manufacturer" />

#### 제조사와 협업할 때

```java
AppsFlyerLib.getInstance().setPreinstallAttribution(android.os.Build.MANUFACTURER, "CAMPAIGN_NAME", "123");
AppsFlyerLib.getInstance().init(AF_DEV_KEY , conversionListener , getApplicationContext());
```

> 📘 **Note**
>
> * 미디어 소스 파라미터는 필수입니다.
> * `android.os.Build.MANUFACTURER` 속성은 운영 체제에 설정된 대로 제조업체 이름을 유지합니다. 이 속성을 사용한다고 해서 해당 제조업체의 모든 디바이스에서 동일한 형식으로 제조업체 이름을 얻을 수 있는 것은 아닙니다. 이 속성에 예상대로 제조업체 이름이 있는지 확인하세요.
> * `campaign` 및 `siteId` 파라미터는 선택사항이지만 `setPreinstallAttribution` 메서드에서는 필수입니다. `campaign`와 `siteId`를 지정하지 않으려면 둘 다 null을 전달하세요.

<div id="advantages-1" />

#### 장점

SDK API 메서드를 사용하면 프로그래밍 방식으로 제조업체 이름을 검색할 수 있습니다. 제조업체에 관계없이 SDK 메서드는 디바이스에서 직접 이름을 가져옵니다. 즉, 협업하는 모든 제조업체에 대해 하나의 APK를 유지할 수 있습니다.

`setPreinstallAttribution` 메서드를 사용하여 캠페인 이름을 지정할 수 있습니다. 모든 제조업체나 미디어 소스를 "사전 인스톨" 캠페인 아래에 두는 대신, 각 제조업체나 미디어 소스를 다른 캠페인으로 분리할 수 있습니다.

<div id="disadvantages-1" />

#### 단점

제조업체와 직접 협업하는 경우 제조업체용과 구글 플레이용 두 가지 버전의 APK를 유지해야 합니다. 어떤 경우든 하나 이상의 APK가 필요합니다.

대신 제조업체와 통신하는 여러 미디어 소스와 작업하는 경우, 각 미디어 소스를 위해 별도의 APK를 유지해야 합니다.

경우에 따라 인스톨이 사전 인스톨 미디어 소스로 측정되지 않을 수 있습니다:

* 새 디바이스를 가진 사용자가 사전 설치된 앱을 먼저 실행하지 않고 구글 플레이에서 직접 업데이트하면, 인스톨이 오가닉으로 간주됩니다.
* 새 디바이스를 가진 사용자가 광고를 클릭한 후 구글 플레이에서 앱을 업데이트하면, 인스톨은 광고를 제공한 미디어 소스로 측정됩니다.

> 👍 **Tip**
>
> 앱에서 논리를 구현하여 위 시나리오가 발생하더라도 인스톨이 사전 인스톨로 계산되도록 할 수 있습니다. 플레이 스토어 APK와 사전 설치용 APK 모두 해당 로직을 포함해야 합니다.
>
> **예시:**
>
> * 앱이 특정 제조업체 및 모델의 디바이스에 사전 설치되어 있다고 가정합니다. 이 디바이스들은 특정 통신사와 함께 운영됩니다.
> * 앱이 실행될 때 이러한 조건들을 확인할 수 있습니다. 이러한 조건이 충족되면, 인스톨은 사전 인스톨로 기록됩니다. 플레이 스토어 APK에도 로직이 포함되어 있어, 사용자가 앱을 실행하기 전에 앱을 업데이트하더라도 인스톨은 사전 인스톨로 기록됩니다.

</Accordion>

<div id="name-in-manifest-file-method" />

<Accordion title="매니페스트 파일 메서드의 이름">

매니페스트 메서드를 사용하려면 앱의 매니페스트 파일에 메타데이터 태그를 추가해야 합니다. 협업하는 모든 미디어 소스 또는 제조업체에 대해 이 단계를 반복해야 합니다.

애플리케이션 태그를 닫기 전에 메타데이터 태그를 추가합니다.

```html Markup
...
    <meta-data android:name="AF_PRE_INSTALL_NAME" android:value="market_name"/>
  </application>
</manifest>
```

앱이 처음 실행되면, 앱스플라이어 SDK가 매니페스트 파일에서 이 메타데이터 태그를 감지하고, 이에 따라 인스톨을 어트리뷰션합니다.

<div id="advantages-2" />

#### 장점

매니페스트 메서드는 사전 설치 캠페인을 어트리뷰션하기 위한 쉬운 메서드로 간주됩니다. 매니페스트에 추가할 태그는 하나뿐입니다. 게다가, 미디어 소스나 제조사는 캠페인 측정을 위해 별도로 할 필요는 없습니다.

<div id="disadvantages-2" />

#### 단점

메타데이터 태그는 미디어 소스 또는 제조업체 이름을 지정하므로, 미디어 소스 또는 제조업체별로 서로 다른 APK 세트를 유지해야 합니다.

경우에 따라 인스톨이 사전 인스톨 미디어 소스로 측정되지 않을 수 있습니다:

* 새 디바이스를 가진 사용자가 사전 설치된 앱을 먼저 실행하지 않고 구글 플레이에서 직접 업데이트하면, 인스톨이 오가닉으로 간주됩니다.
* 새 디바이스를 가진 사용자가 광고를 클릭한 후 구글 플레이에서 앱을 설치하면, 해당 설치는 광고를 제공하는 미디어 소스에 어트리뷰션됩니다.

</Accordion>

<div id="pathway-method" />

<Accordion title="경로 메서드">

> 📘 **Note**
>
> SDK 버전 4.5.0 이상에서 지원됩니다.

이 메서드를 사용하려면 개발자와 제조업체 모두 몇 가지 작업을 수행해야 합니다.

<div id="developer-1" />

#### 개발자

경로 메서드를 사용하면, 미디어 소스 또는 제조업체의 이름이 포함된 파일의 경로를 지정할 수 있습니다. 다음 세 단계를 완료해야 합니다.

1. 키-값 쌍을 포함하는 파일을 생성합니다. 파일의 이름은 ***pre\_install.appsflyer***여야 합니다. 파일에서 다음 형식으로 키-값 쌍을 지정합니다: `<PACKAGE_NAME>`=`<MEDIA_SOURCE>`. 예를 들어, `com.appsflyer.sampleapp=my_media_source`.  

   <div id="passing-additional-pre-install-parameters" />

   #### 추가 사전 설치 파라미터 전달

   JSON을 사용하여 파일에 추가 사전 설치 파라미터를 지정할 수 있습니다. 예를 들어, **pre\_install.appsflyer** 파일에 다음 키-값 쌍을 추가할 수 있습니다.

   ```json
   com.appsflyer.sampleapp={"pid":"huawei", "c":"special_campaign","af_adset":"some_adset"}
   ```

   > 🚧 **Important!**
   >
   > 이 옵션을 사용할 때 다음 동작에 유의해야 합니다.
   >
   > 1. "Pre-install"을 af\_channel로 설정합니다.
   > 2. pid가 JSON에 없으면, 미디어 소스는 "없음"으로 표시됩니다.
   > 3. JSON 설정에서 c가 없으면 캠페인 이름은 "Pre-install"로 설정됩니다.
   > 4. JSON 형식이 잘못된 경우, 전달된 문자열은 미디어 소스 이름으로 간주됩니다.


   pre\_install.appsflyer 파일이 있으면 APK와 함께 미디어 소스나 제조업체에 제공하십시오.
2. 미디어 소스 또는 제조업체와 파일을 저장할 경로에 대해 협의하십시오. 권장 경로는"/data/local/tmp/pre\_install.appsflyer"입니다.
3. 경로가 합의되면 매니페스트 파일에 지정하십시오. 다음 코드 조각을 닫는 애플리케이션 태그 앞에 배치하십시오.  

   ```html Markup
   <meta-data android:name="AF_PRE_INSTALL_PATH" 
         android:value="/data/local/temp/pre_install.appsflyer" />
   ```

<div id="manufacturer-1" />

#### 제조업체

제조업체는 합의된 경로에 파일을 넣어야 합니다. pre\_install.appsflyer 파일 권한은 744로 설정해야 합니다.

앱이 실행되면 SDK는 매니페스트 파일을 확인하고 지정된 경로에서 파일을 찾습니다. 파일을 찾으면, 지정된 미디어 소스에 따라 인스톨을 측정합니다.

<div id="advantages-3" />

#### 장점

앱스플라이어는 두 가지 기본 경로에서 **pre\_install.appsflyer** 파일을 찾습니다.

```bash
/data/local/tmp/pre_install.appsflyer
OR 
/etc/pre_install.appsflyer
```

일부 제조업체에서는 파일을 기본 경로가 아닌 곳에 저장합니다. 이러한 경우 매니페스트 파일에 기본이 아닌 경로를 지정할 수 있습니다.

> 🚧 **Important!**
>
> 기본이 아닌 경로는 SDK 버전 4.8 이상이 필요합니다.
>
> 기본이 아닌 경로가 허용되지만 대신 [시스템 속성 메서드](/docs/appsflyer-factory-preinstall-using-manifest-android#system-properties-method-recommended)를 구현하는 것이 좋습니다.

<div id="disadvantages-3" />

#### 단점

매체 소스 또는 제조업체에 따라 별도의 ***pre\_install.appsflyer*** 파일을 유지해야 합니다.

제조업체가 ***pre\_install.appsflyer*** 파일을 기본이 아닌 경로에 저장할 수 있습니다. 이 경우 기본이 아닌 각 경로에 대해 별도의 APKS를 유지해야 합니다.

**기본이 아닌 경로**를 사용하면 사전 인스톨 미디어 소스로 측정되지 않을 수 있습니다:

* 새 디바이스를 가진 사용자가 사전 설치된 앱을 먼저 실행하지 않고 구글 플레이에서 직접 업데이트하면, 인스톨이 오가닉으로 간주됩니다.
* 새 디바이스를 가진 사용자가 광고를 클릭한 후 구글 플레이에서 앱을 설치하면, 해당 설치는 광고를 제공하는 미디어 소스에 어트리뷰션됩니다.

</Accordion>

<div id="testing-pre-install-configuration" />

## 사전 인스톨 설정 테스트

이 섹션에서는 사전 인스톨 구성을 시험하고 확인하는 방법을 설명합니다.

> 🚧 **Important!**
>
> 테스트를 시작하기 전에 테스트에 사용하는 <Anchor target="_blank" href="/marketers/ko/docs/registering-test-devices">디바이스를 허용 목록에 추가</Anchor>했는지 확인하십시오.
> 또한, AFApplication 클래스에서 디버그 로그가 true로 설정되어 있는지 확인하십시오.
>
> ```java
> AppsFlyerLib.getInstance().setDebugLog(true);
> ```

<div id="verifying-the-configuration-in-the-app" />

<Accordion title="앱에서 설정 확인">

> 👍 **Tip**
>
> 캐싱 문제를 방지하고 최상의 결과를 얻으려면 프로젝트를 빌드하기 전에 정리하는 것이 좋습니다. 안드로이드 스튜디오의 상황에 맞는 메뉴에서 ***Build***를 클릭하고 ***Clean Project***를 선택합니다.

안드로이드 스튜디오에서 앱을 빌드하여 시험 디바이스에 인스톨합니다. 애플리케이션이 시작되면 안드로이드 스튜디오에서 Logcat을 열고 "AppsFlyer"로 필터링합니다. 어트리뷰션된 인스톨이 모든 세부사항과 함께 표시될 것입니다. 아래 스크린샷을 참고하세요.

![pre_install_logcat.png](https://files.readme.io/260ce97a8f4a5e494e16de1ea31b68190fe8c72351fe6267b85d4add2e01163e-51857544690065.png)

![pre_install_logcat_2.png](https://files.readme.io/a1f0091ec7adc31247433b690c93530ad709bfd93e00831fb8043133dbad4ee1-51857559114257.png)

</Accordion>

<div id="verifying-the-configuration-in-the-appsflyer-dashboard" />

<Accordion title="앱스플라이어 대시보드에서 설정 확인">

설정이 성공하면, 제조사나 미디어 소스에 어트리뷰션된 논오가닉 인스톨이 대시보드에 나타납니다. 인스톨 이벤트는 “사전 설치” 캠페인 아래에도 나열됩니다.

앱스플라이어 계정으로 이동하여 귀사의 테스트하려는 앱의 대시보드를 엽니다. 아래 단계를 따르세요.

1. 개요 페이지에서 미디어 소스로 필터링하고 미디어 소스를 선택하세요.  

   ![choose_media_source.png](https://files.readme.io/e35689cfc07cd634c0e533f314d48da3f0f2e2a49cf9ca71397a3ed4815a187c-51857544690577.png)
2. ***캠페인별 분석*** 그래프에서 'my 미디어 소스'로 측정된 인스톨이 사전 설치 캠페인에서 비롯된 것을 확인할 수 있습니다.  

    [![](https://files.readme.io/3e60def526507a2429137762c87ee39149c9a37ff463ce6d3945adc1c4d056bc-360002653405.png)](https://files.readme.io/3e60def526507a2429137762c87ee39149c9a37ff463ce6d3945adc1c4d056bc-360002653405.png)  
   또한 *집약형 성과 리포트를 확인하여 설치가 올바르게 어트리뷰션되었는지 확인할 수 있습니다*. 리포트에서 미디어 소스와 캠페인을 볼 수 있습니다. 아래 스크린샷에서 '내 미디어 소스'가 미디어 소스이고 캠페인이 사전 설치인 경우를 참고하세요.  

    [![](https://files.readme.io/495ed305a2379b4d22bc6f2b920bf4213c49b7bcba069e45b8a5a03f53502ac5-51857544690833.png)](https://files.readme.io/495ed305a2379b4d22bc6f2b920bf4213c49b7bcba069e45b8a5a03f53502ac5-51857544690833.png)
3. 사전 설치 캠페인에 협업하는 모든 제조업체나 미디어 소스에 대해 이 과정을 반복하세요.

</Accordion>

<div id="special-cases" />

## 특별한 경우

<div id="multiple-preinstall-apps-on-the-same-device" />

<Accordion title="동일한 디바이스에 여러 사전 설치 앱이 있는 경우">

여러 앱을 동일한 디바이스에 설치한 경우, 다음 네 가지 방법을 각각 사용하여 어트리뷰션을 측정할 수 있습니다:

* 매니페스트 메서드 - 각 앱의 Manifest.xml에서 미디어 소스 또는 제조업체를 지정합니다.
* SDK API 메서드 - 각 앱의 경우SDK API 메서드에서 사전 설치를 위한 미디어 소스 또는 제조업체를 지정합니다.
* 시스템 속성 또는 경로 메서드 - ***pre\_install.appsflyer*** 파일에서 앱과 해당 미디어 소스를 지정할 수 있습니다. 각 앱 정보는 파일의 새로운 줄에 추가해야 합니다. 예를 들어:

  ```bash
  com.appsflyer.tester=market_name
  com.newapp.newapp=market_name
  com.game.king=market_name
  ```

</Accordion>

<div id="sending-install-postbacks" />

<Accordion title="인스톨 포스트백 전송">

협업하는 미디어 소스 또는 제조업체가 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#your-integrated-partners">앱스플라이어 파트너</Anchor>인 경우, 인스톨에 대한 포스트백을 활성화할 수 있습니다.

이를 위해 미디어 소스 이름이 앱스플라이어에서 구성된 미디어 소스 pid와 동일한지 확인하세요.

예를 들어, market\_name와 협업하는 경우, 그 pid는 market\_name\_int입니다. <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#클릭-쓰루-어트리뷰션">통합된 파트너의 어트리뷰션 링크</Anchor>를 확인하여 pid를 볼 수 있습니다.

</Accordion>

<div id="agencies" />

<Accordion title="에이전시">

현재 에이전시는 사전 인스톨로 측정될 수 없습니다.

af\_prt(에이전시 이름 매개변수)가 사전 설치 데이터의 일부이고 사용자가 사전 설치된 앱을 실행한 경우:

* 유저는 에이전시가 사용하는 미디어 소스에 어트리뷰션됩니다(pid=).
* 클라이언트는 전체 유저 수준 데이터에 액세스할 수 있습니다.
* 유저는 에이전시에 어트리뷰션되지 않았습니다.
* 에이전시는 유저 수준 데이터에 액세스할 수 없습니다.

</Accordion>

<div data-zendesk-anchors="introduction=%EC%86%8C%EA%B0%9C h_01J421581P06FTM7B3XG2GYB2P=%EC%86%8C%EA%B0%9C what-is-a-preinstall-campaign=%EC%82%AC%EC%A0%84-%EC%84%A4%EC%B9%98-%EC%BA%A0%ED%8E%98%EC%9D%B8%EC%9D%B4%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9E%85%EB%8B%88%EA%B9%8C h_01J421581P6GYK60D5JQ9PK93N=%EC%82%AC%EC%A0%84-%EC%84%A4%EC%B9%98-%EC%BA%A0%ED%8E%98%EC%9D%B8%EC%9D%B4%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9E%85%EB%8B%88%EA%B9%8C h_01J421581PBQQ5AS3S4JPX52CF=important benefits-of-recording-installs-from-preinstall-campaigns=%EC%82%AC%EC%A0%84-%EC%84%A4%EC%B9%98-%EC%BA%A0%ED%8E%98%EC%9D%B8%EC%9C%BC%EB%A1%9C-%EC%9D%B8%ED%95%9C-%EC%9D%B8%EC%8A%A4%ED%86%A8-%EA%B8%B0%EB%A1%9D%EC%9D%98-%EC%9D%B4%EC%A0%90 h_01J421581P5MS4X9BHSJ3TTWBF=%EC%82%AC%EC%A0%84-%EC%84%A4%EC%B9%98-%EC%BA%A0%ED%8E%98%EC%9D%B8%EC%9C%BC%EB%A1%9C-%EC%9D%B8%ED%95%9C-%EC%9D%B8%EC%8A%A4%ED%86%A8-%EA%B8%B0%EB%A1%9D%EC%9D%98-%EC%9D%B4%EC%A0%90 how-can-i-measure-preinstall-campaigns=%EC%82%AC%EC%A0%84-%EC%84%A4%EC%B9%98-%EC%BA%A0%ED%8E%98%EC%9D%B8%EC%9D%80-%EC%96%B4%EB%96%BB%EA%B2%8C-%EC%B8%A1%EC%A0%95%ED%95%A9%EB%8B%88%EA%B9%8C h_01J421581PEZZW2R244ZX9HX0R=%EC%82%AC%EC%A0%84-%EC%84%A4%EC%B9%98-%EC%BA%A0%ED%8E%98%EC%9D%B8%EC%9D%80-%EC%96%B4%EB%96%BB%EA%B2%8C-%EC%B8%A1%EC%A0%95%ED%95%A9%EB%8B%88%EA%B9%8C viewing-preinstall-data=%EC%82%AC%EC%A0%84-%EC%84%A4%EC%B9%98-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B8%B0 h_01J421581PS1CEPK3NN7AZ0ZDE=%EC%82%AC%EC%A0%84-%EC%84%A4%EC%B9%98-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B8%B0 h_01J421581PDE1CEXRS6BYTDV35=note h_01J421581PKQTX47GC62K4AB9A=note-1 setup=%EC%84%A4%EC%A0%95 h_01J421581P28NEVB44R3XTPY75=%EC%84%A4%EC%A0%95 h_01J421581QNSQ7W3VYFDVZ1423=system-properties-method-recommended developer=%EA%B0%9C%EB%B0%9C%EC%9E%90 h_01J421581Q8ZAPZS12PEG4VW3N=%EA%B0%9C%EB%B0%9C%EC%9E%90 h_01J421581QYRNXCP16GY8CJTKT=important-1 manufacturer=%EC%A0%9C%EC%A1%B0%EC%97%85%EC%B2%B4 h_01J421581QF6Y6MY28N5MR5BTM=%EC%A0%9C%EC%A1%B0%EC%97%85%EC%B2%B4 h_01J421581QBFMVT3KPCPPFRX42=note-2 advantages=%EC%9E%A5%EC%A0%90 h_01J421581QEPAC0WZK93HH3QYP=%EC%9E%A5%EC%A0%90 disadvantages=%EB%8B%A8%EC%A0%90 h_01J421581QCG3HARVZVECMHQ1K=%EB%8B%A8%EC%A0%90 h_01J421581QQ3VJSSQ06DKZQ0BQ=sdk-api-method when-working-with-a-media-source=%EB%AF%B8%EB%94%94%EC%96%B4-%EC%86%8C%EC%8A%A4%EC%99%80-%ED%98%91%EC%97%85%ED%95%A0-%EB%95%8C h_01J421581Q6F1AD0SYXEEJB8FB=%EB%AF%B8%EB%94%94%EC%96%B4-%EC%86%8C%EC%8A%A4%EC%99%80-%ED%98%91%EC%97%85%ED%95%A0-%EB%95%8C when-working-with-a-manufacturer=%EC%A0%9C%EC%A1%B0%EC%82%AC%EC%99%80-%ED%98%91%EC%97%85%ED%95%A0-%EB%95%8C h_01J421581Q3YSNH7KXQXET7FD4=%EC%A0%9C%EC%A1%B0%EC%82%AC%EC%99%80-%ED%98%91%EC%97%85%ED%95%A0-%EB%95%8C h_01J421581QRYRWY2WJKCBHQBFG=note-3 advantages::d999b734=%EC%9E%A5%EC%A0%90-1 h_01J421581QWHP73CA7P13WAQ7Q=%EC%9E%A5%EC%A0%90-1 disadvantages::92772f7d=%EB%8B%A8%EC%A0%90-1 h_01J421581QRRFBJWZB5Z6M08BE=%EB%8B%A8%EC%A0%90-1 h_01J421581QF11R7ZXAXRP2YQYR=tip h_01J421581QJ2J54HJFTXF3G5S0=name-in-manifest-file-method advantages::3f0b06fb=%EC%9E%A5%EC%A0%90-2 h_01J421581Q8WFYYFQJ45KPWZWP=%EC%9E%A5%EC%A0%90-2 disadvantages::919cb3e3=%EB%8B%A8%EC%A0%90-2 h_01J421581QYC02EKB5P0FN5G3F=%EB%8B%A8%EC%A0%90-2 h_01J421581QNFT2E2P3A6MR3BB5=pathway-method h_01J421581QF43JW6A0B48SK9AE=note-4 developer::7c51f631=%EA%B0%9C%EB%B0%9C%EC%9E%90-1 h_01J421581QB4TH9DMA2ANHG7RD=%EA%B0%9C%EB%B0%9C%EC%9E%90-1 passing-additional-preinstall-parameters=%EC%B6%94%EA%B0%80-%EC%82%AC%EC%A0%84-%EC%84%A4%EC%B9%98-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0-%EC%A0%84%EB%8B%AC h_01J421581Q45AEN4GEM5ZKPYRN=%EC%B6%94%EA%B0%80-%EC%82%AC%EC%A0%84-%EC%84%A4%EC%B9%98-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0-%EC%A0%84%EB%8B%AC h_01J421581Q3MMTKPP3E8SZD13F=important-2 manufacturer::56d9649d=%EC%A0%9C%EC%A1%B0%EC%97%85%EC%B2%B4-1 h_01J421581Q16AVHRCTHME67VHQ=%EC%A0%9C%EC%A1%B0%EC%97%85%EC%B2%B4-1 advantages::1fb76031=%EC%9E%A5%EC%A0%90-3 h_01J421581QTRY13FVNQRMG0H2B=%EC%9E%A5%EC%A0%90-3 h_01J421581Q0P5VQJHQ9X3VRW8N=important-3 disadvantages::c9cae863=%EB%8B%A8%EC%A0%90-3 h_01J421581QSNNCHPC2VSF48FT3=%EB%8B%A8%EC%A0%90-3 testing-preinstall-configuration=%EC%82%AC%EC%A0%84-%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%84%A4%EC%A0%95-%ED%85%8C%EC%8A%A4%ED%8A%B8 h_01J421581QYHRHF119J4YBZD23=%EC%82%AC%EC%A0%84-%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%84%A4%EC%A0%95-%ED%85%8C%EC%8A%A4%ED%8A%B8 h_01J421581QW0XKZ635A194W80J=important-4 h_01J421581QPXQDFX5G11B7GSNA=verifying-the-configuration-in-the-app h_01J421581QSZPZVZ6GGQST5FWS=tip-1 h_01J421581Q7PGHJ2HBX1ZDNJS6=verifying-the-configuration-in-the-appsflyer-dashboard special-cases=%ED%8A%B9%EB%B3%84%ED%95%9C-%EA%B2%BD%EC%9A%B0 h_01J421581Q624TH08PX24B1P3X=%ED%8A%B9%EB%B3%84%ED%95%9C-%EA%B2%BD%EC%9A%B0 h_01J421581QQHB8624SS6FSSA6D=multiple-preinstall-apps-on-the-same-device h_01J421581Q86AB5GTM91ARYJ23=sending-install-postbacks h_01J421581RD2WQ6SPES729GJEP=agencies" />
