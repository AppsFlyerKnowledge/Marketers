---
title: Adobe Launch SDK 확장 프로그램
metadata:
  keywords:
    - SDK
    - Adobe
    - Advertisers
    - AppsFlyer SDK
    - Adobe Experience Platform
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
  created_at: '2019-02-13T08:03:45Z'
  edited_at: '2026-10-14T10:29:45Z'
  id: 360000939097
  locale: ko
  section: Other platforms
  section_id: 6551244207121
  url: https://support.appsflyer.com/hc/ko/articles/360000939097
---
> **한눈에 보기:** 앱스플라이어 Adobe Launch SDK 확장 프로그램의 단일 구현으로 Adobe Launch SDK와 앱스플라이어 SDK로 데이터를 전송할 수 있습니다.

<div id="overview" />

## 개요

Adobe Launch SDK는 Adobe Experience Platform의 필수적인 부분입니다. Adobe Experience Platform은 기업이 여러 앱과 플랫폼에서 데이터를 수집, 연동 및 분석할 수 있도록 지원합니다. 이를 통해 비즈니스 소유자와 개발자는 고객 행동을 더 잘 이해하여 경험과 콘텐츠 전달을 최적화할 수 있습니다. 앱이 Adobe Launch SDK와 앱스플라이어 SDK를 모두 구현하는 경우, **앱스플라이어 Adobe Launch SDK 확장 프로그램**을 한 번만 구현하여 두 가지 모두에 데이터를 전송할 수 있습니다. 개발 프로세스의 전반적인 복잡성을 줄이고 더 깔끔하고 유지 관리하기 쉬운 코드베이스를 만들 수 있습니다.

<div id="note" />

> 📘 **참고**
>
> Adobe Launch 확장 프로그램을 사용하는 경우 표준 <Anchor target="_blank" href="/marketers/ko/docs/adobe-analytics-integration-with-appsflyer">Adobe Analytics 연동</Anchor>이 필요하지 않습니다.

<div id="prerequisites" />

## 선행 조건

앱스플라이어 Adobe SDK 확장 프로그램을 연동하기 전에 몇 가지 사항이 필요합니다.

<div id="get-your-appsflyer-dev-key" />

<Accordion title="3.1 앱스플라이어 dev key 가져오기">

<Image alt="dev_key.png" src="https://files.readme.io/bf25b5d583f3eaab57c230b68764f08c49806a50401955a511993d8a847e7d42-360006050318.png" width="357px" />

1. 앱 대시보드에서 왼쪽 메뉴의 ***구성***에서 ***앱 설정***을 클릭합니다.
2. ***SDK 설치*** 아래에서 ***개발자 키***를 복사합니다.

</Accordion>

<div id="get-your-app-id" />

<Accordion title="앱 ID 받기">

* 안드로이드 - 앱 ID는 패키지 이름입니다(예: example.com.app).
* iOS - 앱 ID는 *id* 접두사가 없는 앱의 iTunes ID입니다(예: 123456748).

</Accordion>

<div id="step-1-configuring-adobe-launch" />

## 1단계: Adobe Launch 구성

여기의 지침에 따라 Adobe Launch를 구성합니다.

<div id="11-creating-a-new-property-in-adobe-launch" />

<Accordion title="1.1 Adobe Launch에서 새 속성 만들기">

[![](https://files.readme.io/d03e61047c536785e7601d4f0efbd9b6488bd41c92efdd6e0d1021b42a5bec3a-small-360005983477.png)](https://files.readme.io/d03e61047c536785e7601d4f0efbd9b6488bd41c92efdd6e0d1021b42a5bec3a-small-360005983477.png)

1. Adobe Experience Cloud에 로그인합니다.
2. ***Launch***를 선택합니다.
3. ***실행으로 이동***을 클릭합니다.
4. ***새로운 속성***을 클릭합니다.
5. 속성의 이름을 지정하고 ***모바일***을 선택합니다.
6. ***저장***을 클릭합니다.

</Accordion>

<div id="12-installing-required-adobe-launch-extensions" />

<Accordion title="1.2 필요한 Adobe Launch 확장 프로그램 설치하기">

Adobe Launch에서 다음 확장 프로그램을 설치합니다.

[![adboe_extensions.png](https://files.readme.io/bf0c0652c3807d4da0819a62b600ac875af1f8764387a36cc3f256a58e1ea852-360005983597.png)](https://files.readme.io/bf0c0652c3807d4da0819a62b600ac875af1f8764387a36cc3f256a58e1ea852-360005983597.png)

* Adobe Analytics - SDK에서 기록된 데이터를 Adobe Analytics 모듈에 연결합니다.
* 앱스플라이어 SDK 확장 프로그램 - Adobe Launch SDK를 사용하여 데이터와 이벤트를 어도비와 앱스플라이어로 모두 전송합니다.
* Adobe Profile - SDK가 클라이언트 측 프로필에 데이터를 저장할 수 있습니다.
* Adobe Mobile Core - 모바일 SDK를 구성할 수 있으며 기본 수명 주기 이벤트 및 조건에 대한 액세스를 제공합니다.

<div id="installing-adobe-analytics-extension" />

#### Adobe Analytics 확장 프로그램 설치

1. Adobe Analytics에 로그인합니다.
2. <Anchor target="_blank" href="https://docs.adobe.com/help/en/analytics/admin/admin-console/create-report-suite.html">보고서 모음을 만듭니다</Anchor>.
3. Adobe Launch에 다시 로그인합니다.
4. 속성 목록에서 이전에 생성한 속성을 클릭합니다.
5. ***확장 프로그램***을 클릭합니다.
6. ***Adobe Analytics***를 검색하고 설치합니다.
7. ***보고서 세트***에서 2단계에서 만든 보고서 세트를 지정합니다.
8. ***저장***을 클릭합니다.

<div id="installing-appsflyer-sdk-extension" />

#### 앱스플라이어 SDK 확장 프로그램 설치

1. ***확장 프로그램***을 다시 선택합니다.
2. ***앱스플라이어 SDK 확장 프로그램***을 검색하고 설치합니다.
3. ***앱스플라이어 iOS 앱 ID***에서 선행 조건 단계에서 얻은 iOS 앱 ID를 지정합니다.
4. ***앱스플라이어 개발자 키***에서 선행 조건 단계에서 받은 개발자 키를 지정합니다.
5. ***어트리뷰션 데이터를 Adobe Analytics로 전송***을 활성화합니다. <Anchor target="_blank" href="/marketers/ko/docs/user-level-data-retention">타사 분석 플랫폼과 사용자 수준 데이터를 공유하는 데에는 몇 가지 제한 사항</Anchor>이 있습니다.
6. ***저장***을 클릭합니다.

<div id="install-profile-and-mobile-core-extension" />

#### Profile 및 Mobile Core 확장 프로그램 설치

1. ***확장 프로그램***을 다시 선택합니다.
2. ***Profile***을 검색하고 설치합니다.
3. ***Mobile Core***를 검색하고 설치합니다.
   * Mobile Core를 설치할 때는 확장 프로그램을 그대로 저장하기만 하면 됩니다. ***Experience Cloud 서버***를 지정할 필요가 없습니다.

</Accordion>

<div id="step-2-implementing-appsflyer-adobe-sdk-extension" />

## 2단계: 앱스플라이어 Adobe SDK 확장 프로그램 구현하기

이 섹션의 지침에 따라 앱에 Adobe SDK 확장 프로그램을 구현합니다.

<div id="21-adding-the-sdk-to-the-app" />

<Accordion title="2.1 앱에 SDK 추가하기">

[![adobe_sdk.png](https://files.readme.io/076e6cc5911a0a515e5510a8da233bcefcb4144c92cf49190416b593fcdecc8f-small-360006050518.png)](https://files.readme.io/076e6cc5911a0a515e5510a8da233bcefcb4144c92cf49190416b593fcdecc8f-small-360006050518.png)

1. Adobe 자산 내에서 ***환경***을 선택합니다.
2. SDK를 배포할 환경을 선택합니다.
3. 오른쪽에서 상자 아이콘을 클릭합니다.
4. 열리는 창에서 코드 스니펫을 복사하고 지침을 따릅니다. Adobe를 구성하는 마케터라면 이 코드 스니펫을 앱 개발자에게 보내십시오.

</Accordion>

<div id="22-publishing-the-environment" />

<Accordion title="2.2 환경 게시하기">

SDK 구현을 완료하려면 환경을 라이브러리에 게시해야 합니다.

[![adobe_publishing.png](https://files.readme.io/4e9ad08fce291ef59e7a3567726c678754ae3a3c96de75f4ae27cd80a84945d1-small-360006050558.png)](https://files.readme.io/4e9ad08fce291ef59e7a3567726c678754ae3a3c96de75f4ae27cd80a84945d1-small-360006050558.png)

1. Adobe 속성에서 ***게시***를 선택합니다.
2. ***새 라이브러리 추가***를 클릭합니다.
3. 이름을 지정하고 환경에서 ***개발***을 선택합니다.
4. ***개발을 위한 저장 및 빌드***를 클릭합니다.
5. 빌드가 완료되면 ***개발***에서 라이브러리 옆에 있는 점 세 개 아이콘을 클릭하고 ***승인을 위해 제출***을 선택합니다.
6. ***제출됨***에서 라이브러리 옆의 점 세 개 아이콘을 클릭하고 ***스테이징용 빌드***를 선택합니다.
7. 빌드가 완료되면 라이브러리 옆에 있는 점 세 개 아이콘을 클릭하고 ***게시 승인***을 선택합니다.
8. ***승인***에서 라이브러리 옆의 점 세 개 아이콘을 클릭하고 ***빌드 및 프로덕션에 게시***를 선택합니다.

</Accordion>

<div id="23-adding-android-install-referrer-to-your-app" />

<Accordion title="2.3 앱에 안드로이드 설치 리퍼러 추가하기">

안드로이드 인스톨 리퍼러는 어트리뷰션 정확도를 높이고 인스톨 사기 등을 방지합니다. 이는 앱스플라이어 안드로이드 SDK 4.8.6 버전 이상에서 지원됩니다.

<div id="note-1" />

> 📘 **참고**
>
> 구글은 [BroadcastReceiver](https://android-developers.googleblog.com/2019/11/still-using-installbroadcast-switch-to.html)를 2020년 3월부터 사용하지 않습니다.
>
> * 이 변경은 앱에 영향을 주지 않습니다.
> * 스토어 외부의 어트리뷰션을 위해 BroadcastReceiver가 여전히 필요할 수 있습니다. 정확한 확인을 위해, 앱이 등록된 스토어에 확인해보십시오.
> * 인스톨 리퍼러 구현은 이제 필수입니다.

앱에 인스톨 리퍼러를 추가하는 방법은 두 가지가 있습니다.

* Gradle 사용하기(권장)
* 수동으로 인스톨 리퍼러 추가하기

<Tabs>
<Tab title="Gradle을 이용하여 인스톨 리퍼러 추가하기">

안드로이드 인스톨 리퍼러를 종속 항목으로 추가하십시오. 최신 버전은 <Anchor target="_blank" href="https://mvnrepository.com/artifact/com.android.installreferrer/installreferrer/1.0">여기</Anchor>에서 찾을 수 있습니다.

1.
   ```java
   dependencies {
   //make sure to use the latest SDK version: https://mvnrepository.com/artifact/com.appsflyer/af-android-sdk
   	implementation 'com.appsflyer:af-android-sdk:5.+'
   	implementation 'com.android.installreferrer:installreferrer:1.1'
   }
   ```
2. 프로젝트를 동기화하여 종속성을 검색하려면 다음 스크린샷을 참조하세요.  

   [![android_af_sdk_sync_gradle.png](https://files.readme.io/f8835cf76d51d7ddeb51206707d95b7214e398c5960299893118ad57ccffe890-22939234622609.png)](https://files.readme.io/f8835cf76d51d7ddeb51206707d95b7214e398c5960299893118ad57ccffe890-22939234622609.png)

ProGuard를 사용 중인데 구글의 새로운 리퍼러 API를 사용하려면 다음의 ProGuard 규칙을 설정하세요. `-dontwarn com.android.installreferrer`

</Tab>

<Tab title="수동으로 인스톨 리퍼러 추가하기">

1. <Anchor target="_blank" href="https://mvnrepository.com/artifact/com.android.installreferrer/installreferrer/1.0">인스톨 리퍼러 aar 다운로드하기</Anchor>
2. <Anchor target="_blank" href="https://stackoverflow.com/questions/16682847/how-to-manually-include-external-aar-package-using-new-gradle-android-build-syst">프로젝트에 추가하기</Anchor>
3. 매니페스트에 다음 권한을 추가함: `com.google.android.finsky.permission.BIND_GET_INSTALL_REFERRER_SERVICE`

</Tab>
</Tabs>

</Accordion>

<div id="24-setting-required-permissions" />

<Accordion title="2.4 필요한 권한 설정">

권한을 추가하면 <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-attribution-model#probabilistic-modeling">확률적 모델링 어트리뷰션</Anchor>의 매칭 확률을 더욱 높일 수 있습니다. 또한 SDK에서 Wifi 및 통신사 네트워크 데이터와 같은 더 많은 데이터를 전송할 수 있게 합니다. 이런 데이터를 <Anchor target="_blank" href="/marketers/ko/docs/raw-data-reporting-overview">로데이터 리포트</Anchor>에서 확인하고 캠페인 분석 및 최적화에 사용할 수 있습니다.

<div id="add-required-permissions" />

#### 필요한 권한 추가하기

1. AndroidManifest.xml에 다음 권한을 추가합니다.  

   ```html Markup
   <uses-permission android:name="android.permission.INTERNET" />
   <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
   <uses-permission android:name="android.permission.ACCESS_WIFI_STATE" />
   <!-- Optional : -->
   <uses-permission android:name="android.permission.READ_PHONE_STATE" />
   ```

</Accordion>

<div id="using-the-adobe-sdk-extension" />

## Adobe SDK 확장 프로그램 사용

이제 Adobe SDK 확장 프로그램을 사용하여 어도비와 앱스플라이어로 데이터를 전송할 수 있습니다.

<div id="note-2" />

> 📘 **참고**
>
> 현재 Adobe Launch SDK 확장 프로그램은 전환 데이터 가져오기 및 이벤트 전송만 지원합니다. 그러나 앱에 Adobe Launch SDK 확장 프로그램을 추가하면 앱스플라이어 SDK도 추가됩니다. 따라서 현재 Adobe SDK 확장 프로그램에 없는 모든 기능은 앱스플라이어 SDK를 사용하여 구현할 수 있습니다.

<div id="sending-events" />

<Accordion title="이벤트 전송">

인앱 이벤트는 앱에서 어떤 일이 일어나는지 인사이트를 제공합니다. 시간을 들여 기록할 이벤트를 정의하는 것이 좋습니다. 인앱 이벤트를 기록하면 ROI(Return on Investment)나 LTV(Lifetime Value)와 같은 KPI를 측정할 수 있습니다.

Adobe Launch SDK 확장 프로그램을 사용하면 인앱 이벤트 데이터를 어도비와 앱스플라이어 모두에 전송할 수 있습니다. 그런 다음 Adobe Analytics를 사용하여 사용자 행동을 분석하고, 앱스플라이어를 사용하여 ROI 및 LTV를 분석할 수 있습니다.

<Tabs>
<Tab title="안드로이드">

```java
final Map<String,String> eventMap = new HashMap<>();  
eventMap.put("currency", "USD");  
eventMap.put("revenue", "200");  
eventMap.put("freehand", "param");

MobileCore.trackAction("af_purchase", eventMap);
```

</Tab>

<Tab title="iOS">

```java
[ACPCore trackAction:@"af_purchase data:@{@"revenue":@"200",@"currency":@"USD"];
```

</Tab>
</Tabs>

위 코드에 지정된 대로 이벤트를 전송하면 앱스플라이어 대시보드에 af\_purchase라는 이벤트가 생성되고 수익은 200달러가 됩니다. 이 이벤트는 Adobe Analytics에도 전송되어 표시됩니다.

이벤트와 함께 전송되는 모든 <Anchor target="_blank" href="https://dev.appsflyer.com/docs/direct-deep-linking-1">전환 데이터</Anchor> 앞에는 ***appsflyer***가 접두사로 붙습니다. 예시는 다음 표를 참조하세요.

| 접두사가 붙은 전환 데이터 변수 |
| --- |
| appsflyer.af\_click\_lookback |
| appsflyer.install\_time |
| appsflyer.cost\_cents\_USD |
| appsflyer.media\_source |
| appsflyer.af\_adset |
| appsflyer.click\_time |
| appsflyer.orig\_cost |
| appsflyer.campaign |

</Accordion>

<div id="getting-data-for-deep-linking-and-deferred-deep-linking" />

<Accordion title="딥링킹 및 디퍼드 딥링킹을 위한 데이터 가져오기">

딥링킹과 디퍼드 딥링킹을 통해 사용자 경험을 개선할 수 있습니다. 특정 활동에서 앱을 열고 캠페인 데이터에 따라 콘텐츠를 맞춤 설정할 수 있습니다.

딥링킹에서 데이터를 가져오려면 확장 프로그램 콜백을 구현하세요.

<Tabs>
<Tab title="안드로이드">

전역 애플리케이션 클래스에서 다음 코드를 구현합니다.

```java
AppsFlyerAdobeExtension.registerAppsFlyerExtensionCallbacks(new AppsFlyerExtensionCallbacksListener() {
		@Override
		public void onCallbackReceived(Map<String, String> callback) {
			Log.d(AppsFlyerLibCore.LOG_TAG, callback.toString());
			if(callback.get("callback_type").equals("onConversionDataReceived")){
				// conversion data returned 
				if(callback.get("is_first_launch").equals("true")){
					String af_status = callback.get("af_status");
					if(af_status.equals("Non-organic")){
						Log.d(AppsFlyerLibCore.LOG_TAG, "this is first launch and a non organic install!");
					}
				}
			} else if(callback.get("callback_type").equals("onAppOpenAttribution")){
				// direct deeplink - redirect user
				Log.d(AppsFlyerLibCore.LOG_TAG, callback.toString());
			}
		}
		@Override
		public void onCallbackError(String errorMessage) {
			Log.d("TAG", errorMessage);
		}
	});
```

</Tab>

<Tab title="iOS">

AppDelegate.m에서 다음 코드를 구현합니다.

```objectivec
[AppsFlyerAdobeExtension registerCallbacks:^(NSDictionary *dictionary) {
        NSLog(@"[AppsFlyerAdobeExtension] Received callback: %@", dictionary);
        if([[dictionary objectForKey:@"callback_type"] isEqualToString:@"onConversionDataReceived"]){
            if([[dictionary objectForKey:@"is_first_launch"] boolValue] == YES){
                NSString* af_status = [dictionary objectForKey:@"af_status"];
                if([af_status isEqualToString:@"Non-organic"]){
                    NSLog(@"this is first launch and a non organic install!");
                }
            }
        } else if([[dictionary objectForKey:@"callback_type"] isEqualToString:@"onAppOpenAttribution"]) {
            NSLog(@"onAppOpenAttribution Received");
        }
     }];
    [AppsFlyerAdobeExtension callbacksErrorHandler:^(NSError *error) {
          NSLog(@"[AppsFlyerAdobeExtension] Error recieving callback: %@" , error);
    }];
```

</Tab>
</Tabs>

</Accordion>

<div id="connecting-appsflyer-conversion-data" />

## 앱스플라이어 전환 데이터 연결

전환 데이터는 이벤트와 함께 Adobe 플랫폼으로 전송됩니다. 이러한 변수를 사용하면 리포팅 차원, 메트릭 또는 필터에 로직과 규칙을 적용할 수 있습니다.

1. [![](https://files.readme.io/d56f170695893dbbde00c50c838ce8a5c2cfe418a17692f372e208d458ed2d6c-31205379096465.png)](https://files.readme.io/d56f170695893dbbde00c50c838ce8a5c2cfe418a17692f372e208d458ed2d6c-31205379096465.png)

앱스플라이어 컨텍스트 변수를 매핑하는 방법은 다음 표를 참조하세요.

| **맵에 사용할 권장 이름** | **전환 데이터** |
| --- | --- |
| 앱스플라이어어 룩백 윈도우 | appsflyer.af\_click\_lookback |
| 앱스플라이어 설치 시간 | appsflyer.install\_time |
| 앱스플라이어 비용 미국 센트 | appsflyer.cost\_cents\_USD |
| 앱스플라이어 MediaSource | appsflyer.media\_source |
| 앱스플라이어 애드셋 | appsflyer.af\_adset |
| 앱스플라이어 클릭 시간 | appsflyer.click\_time |
| 앱스플라이어 오리지널 비용 | appsflyer.orig\_cost |
| 앱스플라이어 캠페인 | appsflyer.campaign |

<div id="using-appsflyer-mapped-conversion-data-for-analytics-and-analysis" />

### 앱스플라이어 매핑된 전환 데이터를 분석 및 분석에 활용하기

SDK에서 가져온 모든 데이터는 앱에 연결된 Adobe Analytics 보고서 세트에서 사용할 수 있습니다.

생성된 Adobe Analytics 보고서 및 대시보드에서 데이터와 관련 차원 및 지표를 사용할 수 있습니다. 이 데이터는 어트리뷰션 및 인앱 이벤트 분석을 위해 앱스플라이어 대시보드에서도 사용할 수 있습니다.

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 h_01HQQN1Y7MP7B0GXJFP5330G80=%EA%B0%9C%EC%9A%94 h_01HQQNCMYNN0YH7S8Q5F2EWFG5=%EC%B0%B8%EA%B3%A0 prerequisites=%EC%84%A0%ED%96%89-%EC%A1%B0%EA%B1%B4 h_01HQQN1JWAQZZ9S3YV7VXTMRWM=%EC%84%A0%ED%96%89-%EC%A1%B0%EA%B1%B4 h_01HQQN1JWA4JYET26CB11JGY46=get-your-appsflyer-dev-key h_01HQQN1JWAHYQBRY43EWANQ57Z=get-your-app-id step-1-configuring-adobe-launch=1%EB%8B%A8%EA%B3%84-adobe-launch-%EA%B5%AC%EC%84%B1 h_01HQQN1JWAAR873B679QGA9NSX=1%EB%8B%A8%EA%B3%84-adobe-launch-%EA%B5%AC%EC%84%B1 h_01HQQN1JWAE1T7SP3DHTFB55TK=11-creating-a-new-property-in-adobe-launch h_01HQQN1JWA8FDWMNZ4Y17AWYKW=12-installing-required-adobe-launch-extensions installing-adobe-analytics-extension=adobe-analytics-%ED%99%95%EC%9E%A5-%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%A8-%EC%84%A4%EC%B9%98 h_01HQQN1JWAMB8607K8V2F3YKHE=adobe-analytics-%ED%99%95%EC%9E%A5-%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%A8-%EC%84%A4%EC%B9%98 installing-appsflyer-sdk-extension=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-sdk-%ED%99%95%EC%9E%A5-%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%A8-%EC%84%A4%EC%B9%98 h_01HQQN1JWAYHP9243MTFZ4B2EF=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-sdk-%ED%99%95%EC%9E%A5-%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%A8-%EC%84%A4%EC%B9%98 install-profile-and-mobile-core-extension=profile-%EB%B0%8F-mobile-core-%ED%99%95%EC%9E%A5-%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%A8-%EC%84%A4%EC%B9%98 h_01HQQN1JWA1TEBQY1NH3YP2HQB=profile-%EB%B0%8F-mobile-core-%ED%99%95%EC%9E%A5-%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%A8-%EC%84%A4%EC%B9%98 step-2-implementing-appsflyer-adobe-sdk-extension=2%EB%8B%A8%EA%B3%84-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-adobe-sdk-%ED%99%95%EC%9E%A5-%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%A8-%EA%B5%AC%ED%98%84%ED%95%98%EA%B8%B0 h_01HQQN1JWB3B24RHP9QMNPJK8J=2%EB%8B%A8%EA%B3%84-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-adobe-sdk-%ED%99%95%EC%9E%A5-%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%A8-%EA%B5%AC%ED%98%84%ED%95%98%EA%B8%B0 h_01HQQN1JWBMP4ARMH2VPX35TGH=21-adding-the-sdk-to-the-app h_01HQQN1JWBV3144WY92PAX6PW2=22-publishing-the-environment h_01HQQN1JWBRRCTGA6Q9RDC41KN=23-adding-android-install-referrer-to-your-app h_01HQQN1JWB40T4K3ZJB6AE42WQ=%EC%B0%B8%EA%B3%A0-1 h_01HQQN1JWB19NTCNTWX9QRP8AC=24-setting-required-permissions add-required-permissions=%ED%95%84%EC%9A%94%ED%95%9C-%EA%B6%8C%ED%95%9C-%EC%B6%94%EA%B0%80%ED%95%98%EA%B8%B0 h_01HQQN1JWBVVVGRRXGX9ZJTBT8=%ED%95%84%EC%9A%94%ED%95%9C-%EA%B6%8C%ED%95%9C-%EC%B6%94%EA%B0%80%ED%95%98%EA%B8%B0 using-the-adobe-sdk-extension=adobe-sdk-%ED%99%95%EC%9E%A5-%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%A8-%EC%82%AC%EC%9A%A9 h_01HQQN1JWBFD2CZ4PMCBRM3JN8=adobe-sdk-%ED%99%95%EC%9E%A5-%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%A8-%EC%82%AC%EC%9A%A9 h_01HQQN1JWBSBVFVB911WH54Q32=%EC%B0%B8%EA%B3%A0-2 h_01HQQN1JWBVZDAVAZD4NXMBG4S=sending-events h_01HQQN1JWBXG0JCE9RKA659H6V=getting-data-for-deep-linking-and-deferred-deep-linking connecting-appsflyer-conversion-data=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EC%A0%84%ED%99%98-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%97%B0%EA%B2%B0 h_01HQQN1JWBMBXGQFKGWHE058VT=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EC%A0%84%ED%99%98-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%97%B0%EA%B2%B0 using-appsflyer-mapped-conversion-data-for-analytics-and-analysis=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EB%A7%A4%ED%95%91%EB%90%9C-%EC%A0%84%ED%99%98-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%A5%BC-%EB%B6%84%EC%84%9D-%EB%B0%8F-%EB%B6%84%EC%84%9D%EC%97%90-%ED%99%9C%EC%9A%A9%ED%95%98%EA%B8%B0 h_01HQQN1JWB0WBD6HZXQN6STJY9=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EB%A7%A4%ED%95%91%EB%90%9C-%EC%A0%84%ED%99%98-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%A5%BC-%EB%B6%84%EC%84%9D-%EB%B0%8F-%EB%B6%84%EC%84%9D%EC%97%90-%ED%99%9C%EC%9A%A9%ED%95%98%EA%B8%B0" />
