---
title: Firebase와 Google Tag Manager를 앱스플라이어와 함께 사용하기—설치 및 이벤트 보내기
metadata:
  keywords:
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T10:31:07Z'
  edited_at: '2026-10-14T10:39:06Z'
  id: 4410481550609
  locale: ko
  section: Firebase and Google Tag Manager
  section_id: 6551267006225
  url: https://support.appsflyer.com/hc/ko/articles/4410481550609
---
> **한눈에 보기:** Firebase SDK를 통해 보고된 이벤트를 앱에서 앱스플라이어로 전송하기 위한 설정 지침입니다.

<div id="configuring-events-in-the-app" />

## 앱에서 이벤트 구성하기

이 섹션에서는 Google Tag Manager(GTM)를 사용하여 앱에서 이벤트를 설정하고 생성하는 방법에 대해 설명합니다.

이벤트가 전송되면 GTM은 이벤트 트리거의 도움을 받아 이 이벤트를 처리하도록 구성된 태그가 있는지 확인합니다. 이벤트 트리거는 특정 이벤트가 전송될 때마다 태그를 실행하도록 설정됩니다. 특정 이벤트가 전송되고 해당 트리거가 있으면 태그가 실행됩니다. 태그가 실행되면 Google Tag Manager가 이벤트의 모든 데이터를 수집합니다. 이러한 데이터에는 앱스플라이어 ID, 이벤트 이름, 이벤트 파라미터가 포함됩니다. 모든 데이터를 수집한 후, Google Tag Manager는 이벤트를 앱스플라이어로 전송합니다.

<div id="creating-event-variables-for-revenue-and-price" />

<Accordion title="매출 및 가격에 대한 이벤트 변수 생성">

<div id="android" />

#### 안드로이드

<Tabs>
<Tab title="Java">

1. MainActivity 클래스에서 앱스플라이어 디바이스 ID를 저장할 변수를 생성합니다.  

   ```java
   public static String appsFlyerID;
   ```
2. MainActivity 클래스로 돌아가서 `onCreate` 메서드 내와 `super.onCreate` 뒤에서 변수에 앱스플라이어 ID를 전달합니다.

   ```java
   appsFlyerID = AppsFlyerLib.getInstance().getAppsFlyerUID(this);
   ```

</Tab>

<Tab title="Kotlin">

1. MainActivity 클래스에서 앱스플라이어 디바이스 ID를 저장할 변수를 생성합니다.  

   ```kotlin
   var appsFlyerID: String? = null
   ```
2. MainActivity 클래스로 돌아가서 `onCreate` 메서드 내와 `super.onCreate` 뒤에서 변수에 앱스플라이어 ID 값을 전달합니다.

   ```kotlin
   override fun onCreate(savedInstanceState: Bundle?) {
    ...
    appsFlyerID = AppsFlyerLib.getInstance().getAppsFlyerUID(this)
   }
   ```

</Tab>
</Tabs>

#### iOS

iOS의 경우 앱 전체에서 파라미터를 사용할 수 있습니다. AppsFlyerTracker 인스턴스를 통해 파라미터를 검색할 수 있습니다.

<Tabs>
<Tab title="Objective C">

1. 앱스플라이어 디바이스 ID -

   ```objectivec
   [AppsFlyerTracker sharedTracker].getAppsFlyerUID
   ```
2. 애플 앱 ID -

   ```objectivec
   [AppsFlyerTracker sharedTracker].appleAppID
   ```

</Tab>

<Tab title="Swift">

1. 앱스플라이어 디바이스 ID -

   ```swift
    AppsFlyerTracker.shared().getAppsFlyerUID()
   ```
2. 애플 앱 ID -

   ```swift
   AppsFlyerTracker.shared().appleAppID
   ```

</Tab>
</Tabs>

</Accordion>

<div id="adding-events-in-the-app" />

<Accordion title="앱에서 이벤트 추가하기">

첫 번째 단계에서는 앱에서 이벤트를 구성합니다. 이벤트는 앱스플라이어 ID, 이벤트 이름, 이벤트 파라미터를 지정하는 경우 Firebase 이벤트 로깅을 사용하여 전송됩니다. 앱스플라이어 ID는 <Anchor target="_blank" href="/marketers/ko/docs/using-firebase-and-google-tag-manager-with-appsflyer-google-tag-manager-setup#google-태그-관리자-설정">설정 단계</Anchor>에서 생성된 변수에서 검색됩니다.

<Anchor target="_blank" href="https://developers.google.com/tag-manager/ios/v5/#log-events-and-variables">Google Tag Manager는 Firebase Analytics</Anchor> 이벤트를 사용하여 태그 이벤트를 트리거합니다. 이벤트가 Firebase로 전송될 때마다 Tag Manager가 이벤트를 인식하여 앱스플라이어에도 전송합니다.

<div id="android-1" />

#### 안드로이드

<Tabs>
<Tab title="Java">

1. 원하는 활동에서 Firebase에 대한 import 문을 추가합니다.  

   ```java
   import com.google.firebase.analytics.FirebaseAnalytics;
   ```
2. 구매 이벤트가 발생할 때마다 실행하도록 다음 코드를 추가합니다.

   ```java
   Bundle bundle = new Bundle();
     // notice "af_id", this is the name of the event parameter 
     // for AppsFlyer ID that we created in the previous step
     bundle.putString("af_id", appsFlyerID);
     bundle.putString("af_revenue", "200");
     bundle.putString("af_price", "250");
     mFirebaseAnalytics.logEvent("af_purchase", bundle);
   ```

</Tab>

<Tab title="Kotlin">

1. 원하는 활동에서 Firebase에 대한 import 문을 추가합니다.  

   ```kotlin
   import com.google.firebase.analytics.FirebaseAnalytics
   ```
2. 구매 이벤트가 발생할 때마다 실행하도록 다음 코드를 추가합니다.

   ```kotlin
   val bundle = Bundle()
     // notice "af_id", this is the name of the event parameter
     // for AppsFlyer ID that we created in the previous step
     bundle.putString("af_id", appsFlyerID)
     bundle.putString("af_revenue", "200")
     bundle.putString("af_price", "250")
     FirebaseAnalytics.getInstance(this).logEvent("af_purchase", bundle)
   ```

</Tab>
</Tabs>

iOS

<Tabs>
<Tab title="Objective-C">

1. 이벤트가 전송되는 보기에서 `@import Firebase`를 추가합니다.
2. 구매 이벤트가 발생할 때마다 실행하도록 다음 코드를 추가합니다.

   ```objectivec
   NSString *id_prefix = @"id";  
   NSString *apple_app_id = [id_prefix stringByAppendingString:[AppsFlyerTracker sharedTracker].appleAppID];  

   [FIRAnalytics logEventWithName:@"af_purchase"
         parameters:@{
          @"apple_app_id": apple_app_id,
          @"af_id": [AppsFlyerTracker sharedTracker].getAppsFlyerUID,
          @"af_revenue": @250,
          @"af_price": @375
       }];
   ```

</Tab>

<Tab title="Swift">

1. 이벤트가 전송되는 보기에서 `import Firebase`를 추가합니다.
2. 구매 이벤트가 발생할 때마다 실행하도록 다음 코드를 추가합니다.

   ```swift
   Analytics.logEvent("af_purchase", parameters: [
          "apple_app_id": "id" + AppsFlyerTracker.shared().appleAppID,
          "af_id": AppsFlyerTracker.shared().getAppsFlyerUID(),
          "af_revenue": 250,
          "af_price": 375
       ]);
   ```

</Tab>
</Tabs>

</Accordion>

<div id="sending-install-events-to-firebase" />

## Firebase로 설치 이벤트 보내기

모든 설치 관련 데이터와 함께 설치 이벤트를 Firebase로 보낼 수도 있습니다.

<div id="android-2" />

#### 안드로이드

<Tabs>
<Tab title="Java">

Android에서 설치 이벤트를 Firebase로 전송하려면 `conversionData` 객체를 사용하면 됩니다.

<div id="creating-the-send-event-method" />

#### 이벤트 보내기 메서드 만들기

`onCreate` 메서드 바로 아래 `AFApplication` 클래스에 다음 메서드를 추가합니다.

```java
public void sendInstallToFirebase(Map<String, String> conversionData){
       mFirebaseAnalytics = FirebaseAnalytics.getInstance(this);
       Bundle bundle = new Bundle();
       bundle.putString("install_time", conversionData.get("install_time") == null ? String.valueOf(new Date().getTime()) : conversionData.get("install_time"));
       bundle.putString("click_time", conversionData.get("click_time"));
       bundle.putString("media_source", conversionData.get("media_source") == null ? "organic": conversionData.get("media_source"));
       bundle.putString("campaign", conversionData.get("campaign") == null ? "organic": conversionData.get("campaign"));
       bundle.putString("install_type", conversionData.get("af_status"));
       mFirebaseAnalytics.logEvent("install", bundle);
    }
```

이 메서드는 `conversionData` 객체를 받습니다. 이 메서드는 설치 시간, 미디어소스, 캠페인이 null인지 확인하고 null인 경우 설치 시간을 현재 시간으로, 미디어소스 및 캠페인을 오가닉으로 설정합니다. 그렇지 않으면 `conversionData` 객체에서 데이터를 가져와서 Firebase로 보냅니다.

<div id="sending-the-install-event" />

#### 설치 이벤트 보내기

`onConversionDataSuccess` 메서드에 다음 코드를 추가합니다.

```java
if(conversionData.get("is_first_launch").equals("true")){
       sendInstallToFirebase(conversionData);
    }
```

이 코드는 앱이 처음 실행되는 것인지 확인합니다. 처음 실행되는 것일 경우 `sendInstallToFirebase` 메서드를 호출합니다.

</Tab>

<Tab title="Kotlin">

Android에서 설치 이벤트를 Firebase로 전송하려면 `conversionData` 객체를 사용하면 됩니다.

<div id="creating-the-send-event-method-1" />

#### 이벤트 보내기 메서드 만들기

`onCreate` 메서드 바로 아래 `AFApplication` 클래스에 다음 메서드를 추가합니다.

```kotlin
fun sendInstallToFirebase(conversionData: Map<String, Any>) {
      val bundle = Bundle()
      bundle.putString("install_time", conversionData["install_time"]?.toString() ?: Date().time.toString())
      bundle.putString("click_time", conversionData["click_time"]?.toString())
      bundle.putString("media_source", conversionData["media_source"]?.toString() ?: "organic")
      bundle.putString("campaign", conversionData["campaign"]?.toString() ?: "organic")
      bundle.putString("install_type", conversionData["af_status"]?.toString())
      FirebaseAnalytics.getInstance(this).logEvent("install", bundle)
  }
```

이 메서드는 `conversionData` 객체를 받습니다. 이 메서드는 설치 시간, 미디어소스, 캠페인이 null인지 확인하고 null인 경우 설치 시간을 현재 시간으로, 미디어소스 및 캠페인을 오가닉으로 설정합니다. 그렇지 않으면 `conversionData` 객체에서 데이터를 가져와서 Firebase로 보냅니다.

<div id="sending-the-install-event-1" />

#### 설치 이벤트 보내기

`onConversionDataSuccess` 메서드에 다음 코드를 추가합니다.

```kotlin
if(conversionData?.get("is_first_launch") == true){
      sendInstallToFirebase(conversionData);
  }
```

이 코드는 앱이 처음 실행되는 것인지 확인합니다. 처음 실행되는 것일 경우 `sendInstallToFirebase` 메서드를 호출합니다.

**참고:** SDK V5부터 `onConversionDataSuccess`는 전환 데이터를 가져오는 메서드의 이름입니다. SDK 버전 5.0.0보다 낮은 버전을 사용하는 경우 메서드 이름은 `onInstallConversionDataLoaded`입니다. SDK 5.0.0 이상으로 업그레이드 하는 것을 추천드립니다. 자세히 알아보려면 <Anchor target="_blank" href="/marketers/ko/docs/links-to-appsflyer-sdk-release-notes">여기</Anchor>를 클릭하세요.

</Tab>
</Tabs>

#### iOS

<Tabs>
<Tab title="Objective-C">

<div id="creating-the-send-event-method-2" />

#### 이벤트 보내기 메서드 만들기

AppDelegate.m에서 파일 끝에 다음 메서드를 추가합니다.

```objectivec
- (void)sendInstallToFirebase:(NSDictionary *)installData{
      NSDateFormatter *dateFormatter = [[NSDateFormatter alloc] init];
      [dateFormatter setDateFormat:@"dd/MM/yyyy HH:mm:ss"];
      NSDate *date = [NSDate date];
      NSString *newDate = [dateFormatter stringFromDate:date];

      if([[installData objectForKey: @"af_status"] isEqual: @"Organic"]){
        [FIRAnalytics logEventWithName:@"install"
         parameters:@{
          @"install_time": newDate,
          @"media_source": @"organic",
          @"campaign": @"organic"

        }];
      }
      else {
        [FIRAnalytics logEventWithName:@"install"
          parameters:@{
          @"install_time": [installData objectForKey: @"install_time"],
          @"click_time": [installData objectForKey: @"click_time"],
          @"install_type": [installData objectForKey: @"af_status"],
          @"media_source": [installData objectForKey: @"media_source"],
          @"campaign": [installData objectForKey: @"campaign"]
        }];
      }
    }
```

이 메서드는 `installData` 객체를 수신하고 설치가 오가닉인지 여부를 확인합니다. 오가닉인 경우 설치 시간을 현재 시간으로 설정하고 미디어소스, 캠페인 및 설치 유형을 오가닉으로 설정합니다.

설치가 논오가닉인 경우 메서드는 관련 논오가닉 설치 데이터를 가져옵니다.

파라미터가 설정되면 메서드는 설치 이벤트를 Firebase로 전송합니다.

<div id="sending-the-install-event-2" />

#### 설치 이벤트 보내기

AppDelegate.m의 메서드 `didFinishLaunchingWithOptions`에서 `[FIRApp configure]`를 추가합니다.

AppDelegate.m의 `onConversionDataSuccess` 메서드에서 메서드 끝에 다음 코드를 추가합니다.

```objectivec
if([installData objectForKey:@"is_first_launch"]){
      [self sendInstallToFirebase: installData];
    }
```

위의 코드 스니펫은 앱이 처음 실행되는 것인지 확인합니다. 처음 실행되는 것인 경우 `sendInstallToFirebase` 메서드를 호출합니다.

</Tab>

<Tab title="Swift">

AppDelegate.swift에서 파일 끝에 다음 메서드를 추가합니다.

```swift
func sendInstallToFirebase(_ installData: [AnyHashable : Any]!){

        let date = Date()
        let dateFormatter = DateFormatter()
        dateFormatter.dateFormat = "dd/MM/yyyy hh:mm:ss"
        let _newDate: String = dateFormatter.string(from: date)

        if(installData["af_status"] as? String == "Organic"){
          Analytics.logEvent("install", parameters: [
            "install_time": _newDate,
            "media_source": "organic",
            "campaign": "organic"
          ]);
        } else {
          Analytics.logEvent("install", parameters: [
            "install_time": installData["install_time"],
            "click_time": installData["click_time"],
            "media_source": installData["media_source"],
            "campaign": installData["campaign"],
            "install_type": installData["af_status"]
          ]);
        }

      }
```

**참고:** SDK V5부터 `onConversionDataSuccess`는 전환 데이터를 가져오는 메서드의 이름입니다. SDK 버전 5.0.0보다 낮은 버전을 사용하는 경우 메서드 이름은 `onConversionDataReceived`입니다. SDK 5.0.0 이상으로 업그레이드 하는 것을 추천드립니다. 자세히 알아보려면 <Anchor target="_blank" href="/marketers/ko/docs/links-to-appsflyer-sdk-release-notes">여기</Anchor>를 클릭하세요.

이 메서드는 `installData` 객체를 받고 설치가 오가닉인지 여부를 확인합니다. 오가닉인 경우 설치 시간을 현재 시간으로 설정하고 미디어소스, 캠페인 및 설치 유형을 오가닉으로 설정합니다.

설치가 논오가닉인 경우 메서드는 관련 논오가닉 설치 데이터를 가져옵니다.

파라미터가 설정되면 메서드는 설치 이벤트를 Firebase로 전송합니다.

<div id="sending-the-install-event-3" />

#### 설치 이벤트 보내기

AppDelegate.swift의 메서드 `didFinishLaunchingWithOptions`에서 `FirebaseApp.configure();`를 추가합니다.

AppDelegate.swift의 `onConversionDataSuccess` 메서드에서 메서드 끝에 다음 코드를 추가합니다.

```swift
if let is_first_launch = data["is_first_launch"] , let launch_code = is_first_launch as? Int {
      if(launch_code == 1){
        print("First Launch")
        sendInstallToFirebase(installData)
      } else {
        print("Not First Launch")
      }
    }
```

**참고:** SDK V5부터 `onConversionDataSuccess`는 전환 데이터를 가져오는 메서드의 이름입니다. SDK 버전 5.0.0보다 낮은 버전을 사용하는 경우 메서드 이름은 `onConversionDataReceived`입니다. SDK 5.0.0 이상으로 업그레이드 하는 것을 추천드립니다. 자세히 알아보려면 <Anchor target="_blank" href="/marketers/ko/docs/links-to-appsflyer-sdk-release-notes">여기</Anchor>를 클릭하세요.

위의 코드 스니펫은 앱이 처음 실행되는 것인지 확인합니다. 처음 실행되는 것인 경우 `sendInstallToFirebase` 메서드를 호출합니다.

</Tab>
</Tabs>

<div id="warning" />

> ❗️ **경고**
>
> 일부 미디어소스는 타사 플랫폼 및 서비스와의 데이터 공유를 허용하지 않습니다. 타사 플랫폼 및 서비스와의 데이터 공유에 제한을 설정한 Meta 광고, Twitter, Snap, Pinterest 등의 파트너와 협력하는 경우 해당 파트너의 **가이드라인을 따르고 이러한 제한이 적용되는 데이터를 모두 삭제해야** 합니다.
>
> * <Anchor target="_blank" href="https://www.facebook.com/privacy/policy/">Meta 광고 데이터 정책</Anchor>
> * <Anchor target="_blank" href="https://business.twitter.com/en/help/ads-policies/introduction-to-twitter-ads/twitter-ads-policies.html">Twitter 데이터 정책</Anchor>
> * <Anchor target="_blank" href="https://www.snap.com/en-US/privacy/privacy-policy/">Snapchat 데이터 정책</Anchor>
> * <Anchor target="_blank" href="https://policy.pinterest.com/en/privacy-policy">Pinterest 데이터 정책</Anchor>

<div data-zendesk-anchors="configuring-events-in-the-app=%EC%95%B1%EC%97%90%EC%84%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EA%B5%AC%EC%84%B1%ED%95%98%EA%B8%B0 01H8H2MH93M1SB9HEQNHDDJZP0=%EC%95%B1%EC%97%90%EC%84%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EA%B5%AC%EC%84%B1%ED%95%98%EA%B8%B0 01H8H2MH93D36ZH7788XCMHHV6=creating-event-variables-for-revenue-and-price android=%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C 01H8H2MH93RNWN6N6EWE5T26V1=%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C 01H8H2MH93CZ5TACG3MWJ8YRFK=ios 01H8H2MH9340PQCCKB85BQZQEG=adding-events-in-the-app android::eb294e42=%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-1 01H8H2MH9357Z5M1DBK4Z9N22P=%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-1 sending-install-events-to-firebase=firebase%EB%A1%9C-%EC%84%A4%EC%B9%98-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%B3%B4%EB%82%B4%EA%B8%B0 01H8H2MH930VDZH5YSWEPTS8BN=firebase%EB%A1%9C-%EC%84%A4%EC%B9%98-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%B3%B4%EB%82%B4%EA%B8%B0 android::319436d3=%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-2 01H8H2MH938Y980A9KA9BPP44Y=%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-2 creating-the-send-event-method=%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%B3%B4%EB%82%B4%EA%B8%B0-%EB%A9%94%EC%84%9C%EB%93%9C-%EB%A7%8C%EB%93%A4%EA%B8%B0 01H8H2MH932WYSS6Z5NZJ3195X=%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%B3%B4%EB%82%B4%EA%B8%B0-%EB%A9%94%EC%84%9C%EB%93%9C-%EB%A7%8C%EB%93%A4%EA%B8%B0 sending-the-install-event=%EC%84%A4%EC%B9%98-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%B3%B4%EB%82%B4%EA%B8%B0 01H8H2MH93H0WKMV5DAN713EY0=%EC%84%A4%EC%B9%98-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%B3%B4%EB%82%B4%EA%B8%B0 creating-the-send-event-method::64b5a305=%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%B3%B4%EB%82%B4%EA%B8%B0-%EB%A9%94%EC%84%9C%EB%93%9C-%EB%A7%8C%EB%93%A4%EA%B8%B0 01H8H2MH93VYXGMM5H6ZQWCFZY=%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%B3%B4%EB%82%B4%EA%B8%B0-%EB%A9%94%EC%84%9C%EB%93%9C-%EB%A7%8C%EB%93%A4%EA%B8%B0 sending-the-install-event::aeb9cdb7=%EC%84%A4%EC%B9%98-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%B3%B4%EB%82%B4%EA%B8%B0 01H8H2MH93VTPZNF51R05QPK7C=%EC%84%A4%EC%B9%98-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%B3%B4%EB%82%B4%EA%B8%B0 ios::95ad6e27=ios-1 01H8H2MH93AQE7PKVW4QKD2ARN=ios-1 creating-the-send-event-method::346138b1=%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%B3%B4%EB%82%B4%EA%B8%B0-%EB%A9%94%EC%84%9C%EB%93%9C-%EB%A7%8C%EB%93%A4%EA%B8%B0-2 01H8H2MH93NGBRHBDQTX4DKNTY=%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%B3%B4%EB%82%B4%EA%B8%B0-%EB%A9%94%EC%84%9C%EB%93%9C-%EB%A7%8C%EB%93%A4%EA%B8%B0-2 sending-the-install-event::aca3c0e3=%EC%84%A4%EC%B9%98-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%B3%B4%EB%82%B4%EA%B8%B0-2 01H8H2MH93SWYFF2KTC1HJ06FF=%EC%84%A4%EC%B9%98-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%B3%B4%EB%82%B4%EA%B8%B0-2 sending-the-install-event::b6997ad3=%EC%84%A4%EC%B9%98-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%B3%B4%EB%82%B4%EA%B8%B0-2 01H8H2MH93Y5J8QH0YBKPQSV5N=%EC%84%A4%EC%B9%98-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%B3%B4%EB%82%B4%EA%B8%B0-2 01H8H2MH93JQBAR6ZTW77HHFQR=%EA%B2%BD%EA%B3%A0" />
