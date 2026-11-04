---
title: 개발자용 크로스 프로모션 어트리뷰션
metadata:
  keywords:
    - tracking
    - Cross Promotion
    - cross-promotion
    - Developers
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2021-11-09T09:21:34Z'
  edited_at: '2026-10-14T10:26:59Z'
  id: 4410480466065
  locale: ko
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/ko/articles/4410480466065
---
> **한눈에 보기:**

<div id="note" />

<div id="implementing-cross-promotion-attribution-in-the-sdk" />

## SDK에서 크로스 프로모션 어트리뷰션 구현

> 📘 **참고**
>
> 일반 모바일 광고는 클릭 시 URL을 활성화합니다. 크로스 프로모션 모바일 광고는 링크가 없고 대신, 클릭 시 앱스플라이어 SDK의 ***logAndOpenStore*** 메소드를 활성화합니다.

크로스 프로모션 클릭과 노출은 서로 다른 두 개의 API 호출로 어트리뷰션 합니다. 각 API를 호출할 때 크로스 프로모션 시나리오에 맞는 키 값 맵이 전달될 수 있습니다.

예를 들어, 매개변수 맵을 이용하여 클릭 룩백 윈도우와 ad ID, ad set 같은 매개변수를 설정할 수 있습니다. 캠페인을 보상형 캠페인으로 표시할 수도 있습니다.  앱스플라이어 어트리뷰션 매개변수 에서 확인하세요.

API 메서드에 넘겨주는 표준 매개변수들은  <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters">앱스플라이어 어트리뷰션 매개변수</Anchor>에서 확인하세요.

크로스 프로모션한 앱이 처음 실행되면, 모든 매개변수를 SDK의 conversion data API를 통해 확인할 수 있습니다. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data-android">안드로이드</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data-ios">iOS</Anchor> conversion data API 확인하기


<span id="note-1"></span><span id="attribute-cross-promotion-clicks"></span><span id="attribute-crosspromotion-clicks"></span>다음 코드를 이용하여 클릭을 어트리뷰션하고 앱스토어의 앱 페이지를 실행하십시오. 이 코드는 어트리뷰션 링크를 생성하고 생성된 어트리뷰션 링크에 디바이스 광고 ID를 추가합니다.

<Tabs>
<Tab title="안드로이드">

```java
String campaign = "Cross Promo Campaign"; 
Map<String, String> parameters = new HashMap(); 
parameters.put("af_sub1", "val");
parameters.put("custom_param", "val2"); 
CrossPromotionHelper.logAndOpenStore(this, "com.mygosoftware.android.loginbox", campaign, parameters);
```

</Tab>

<Tab title="iOS">

iOS에서는 Storekit 컴포넌트를 사용하여 해당 앱에 맞는 앱스토어를 열 수 있습니다. 다음 코드는 StoreKit 클래스를 열어 제대로 초기화되었는지 확인하는 방법을 보여줍니다. StoreKit에 대한 상세한 내용은 <Anchor target="_blank" href="https://developer.apple.com/reference/storekit/skstoreproductviewcontroller">이 문서</Anchor>를 읽어보세요.

```objectivec
static NSString *const kCrossPromotedAppId = @"123456789";
static NSString *const kCrossPromotedCampaign = @"test campaign";
- (void) crossPromotion {  
  NSDictionary *parameters = @{@"af_sub1": @"val", @"custom_param": @"val2" };
  [AppsFlyerCrossPromotionHelper logAndOpenStore:kCrossPromotedAppId
               campaign:kCrossPromotedCampaign
               parameters:parameters
               openStore:^(NSURLSession *urlSession, NSURL *clickURL)
  {
  NSURLSessionDataTask *dataTask;
  dataTask = [urlSession dataTaskWithURL:clickURL
             completionHandler:^(NSData * _Nullable data,
                       NSURLResponse * _Nullable response,
                       NSError * _Nullable error)
    {
      if (error) {
        NSLog(@"AppsFlyer crossPromotionViewed Connection failed! Error - %@",[error localizedDescription]);
      }
      else
      {
         if (NSClassFromString(@"SKStoreProductViewController") == nil) {
           NSString *iTunesLink = [linkGenerator generateLink];                
             [[UIApplication sharedApplication] openURL:[NSURL URLWithString:iTunesLink] options:@{} completionHandler:^(BOOL success) {
                 NSLog(@"AppsFlyer openAppStoreForAppID completionHandler result %d",success);
               }];
             }
           }
         }];
    [dataTask resume];    
     if (NSClassFromString(@"SKStoreProductViewController") != nil) {
       [self openStoreKit:kCrossPromotedAppId viewController:self];
     }
  }];
}

- (void) openStoreKit:(NSString*) appID
   viewController: (UIViewController*) viewController
{
    SKStoreProductViewController *storeController = [[ SKStoreProductViewController alloc ] init ];  
  NSDictionary *productParameters = @{ SKStoreProductParameterITunesItemIdentifier : appID };
  [ storeController loadProductWithParameters: productParameters completionBlock:^( BOOL result, NSError *error )
  {
    if ( result )
    {
      [viewController presentViewController:storeController animated:YES completion:nil];
    }

  }];
```

</Tab>

<Tab title="유니티 - 안드로이드">

```csharp
Dictionary<string,string> parameters = new Dictionary<string,string>();
parameters.Add("af_sub1","val");
parameters.Add("custom_param","val2");
AppsFlyer.attributeAndOpenStore("com.mygosoftware.android.loginbox","test campaign",parameters);
```

안드로이드에서 이 메서드를 호출하면 플레이 스토어가 열리고 연관 앱으로 리다이렉션합니다.

</Tab>

<Tab title="유니티 - iOS">

```csharp
Dictionary<string,string> parameters = new Dictionary<string,string>();
parameters.Add("af_sub1","val");
parameters.Add("custom_param","val2")
AppsFlyer.attributeAndOpenStore("123456789","test campaign",parameters);
```

</Tab>
</Tabs>

> 📘 **참고**
>
> 이 <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#어트리뷰션-링크-파라미터">어트리뷰션 링크 매개변수</Anchor> 중 아무 매개변수나 생성된 링크에 추가할 수 있습니다.


<span id="attribute-cross-promotion-impressions"></span><span id="attribute-crosspromotion-impressions"></span>크로스 프로모션 노출 어트리뷰션은 다음 API 호출을 사용합니다. 크로스 프로모션 대상 앱 ID가 앱스플라이어 대시보드에 나타납니다. 그러므로 꼭 프로모션할 앱의 ID를 사용하십시오.

<Tabs>
<Tab title="Java">

```java
String appID = "com.app";
String campaign = "Cross Promo Campaign";
Map<String, String> parameters = new HashMap();
parameters.put("af_sub1", "val");
parameters.put("custom_param", "val2");
CrossPromotionHelper.logCrossPromoteImpression(this, appID, campaign, parameters);
```

</Tab>

<Tab title="Kotlin">

```kotlin
val appID = "com.app"
val campaign = "Cross Promo Campaign"
val parameters = HashMap<String, String>()
parameters.put("af_sub1", "val")
parameters.put("custom_param", "val2")
CrossPromotionHelper.logCrossPromoteImpression(
    this,
    appID,
    campaign,
    parameters
)
```

</Tab>

<Tab title="Objective C">

```objectivec
static NSString *const kCrossPromotedAppId = @"123456789";
static NSString *const kCrossPromotedCampaign = @"test campaign";
/*...*/
- (void)viewDidLoad {
  [super viewDidLoad];  
    NSDictionary *kCrossPromotedParameters = @{@"af_sub1": @"val", @"custom_param": @"val2" };
    /* generate impression for cross-promotion */
     [AppsFlyerCrossPromotionHelper logCrossPromoteImpression:kCrossPromotedAppId
                       campaign:kCrossPromotedCampaign parameters:kCrossPromotedParameters];
 }
```

</Tab>

<Tab title="Swift">

```swift
var appID = "com.app"
var campaign = "Cross Promo Campaign"
var parameters = [String : String]()
parameters["af_sub1"] = "val"
parameters["custom_param"] = "val2"
AppsFlyerCrossPromotionHelper.logCrossPromoteImpression(appID, campaign: campaign, parameters: parameters)
```

</Tab>

<Tab title="Unity">

```csharp
AppsFlyer.recordCrossPromoteImpression(string promotedAppID, string campaign);
```

</Tab>
</Tabs>

<div id="attribute-cross-promotion-with-non-native-platforms" />

### 안드로이드, iOS, 유니티 외 Non-native 플랫폼에서 크로스 프로모션 어트리뷰션하기

현재, 크로스 프로모션 어트리뷰션 API는 네이티브 안드로이드와 iOS SDK, 유니티에서만 가능합니다. 그러나 **Non-native 플랫폼에서도 크로스 프로모션을 효율적으로 어트리뷰션할 수 있습니다.** 이런 Non-native 플랫폼에는 Adobe air, Cordova, Xamarin, React native, Marmalade 등이 있습니다.

**이런 플랫폼으로 만든 앱을 어트리뷰션하기 위해서는 사용자가 크로스 프로모션 광고를 클릭할 때 호출되는 어트리뷰션 링크를 만들어야 합니다**. 어트리뷰션 링크는 반드시 미디어 소스 이름: ***af\_cross\_promotion***, 소스 앱의 사이트 ID를 포함해야 합니다.

크로스 프로모션 클릭 URL 포맷

```http
https://app.appsflyer.com/{PROMOTED APP ID}?pid=af_cross_promotion&
af_siteid={SOURCE APP NAME}
```

크로스 프로모션 노출 URL 포맷

```http
https://impression.appsflyer.com/{PROMOTED APP ID}?pid=af_cross_promotion&
af_siteid={SOURCE APP NAME}
```

<div data-zendesk-anchors="implementing-crosspromotion-attribution-in-the-sdk=sdk%EC%97%90%EC%84%9C-%ED%81%AC%EB%A1%9C%EC%8A%A4-%ED%94%84%EB%A1%9C%EB%AA%A8%EC%85%98-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EA%B5%AC%ED%98%84 h_01HBDHCWSEPQFTYPXGZG2Y770S=sdk%EC%97%90%EC%84%9C-%ED%81%AC%EB%A1%9C%EC%8A%A4-%ED%94%84%EB%A1%9C%EB%AA%A8%EC%85%98-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EA%B5%AC%ED%98%84 h_01HBDHCWSEFSZKDEJYVABG4SMC=%EC%B0%B8%EA%B3%A0 h_01HBDHCWSEB2709HGSKDR78J36=attribute-crosspromotion-clicks h_01HBDHCWSESWH645GDT4N9VCVP=%EC%B0%B8%EA%B3%A0-1 h_01HBDHCWSE5CVWP7AMJ533S7DG=attribute-crosspromotion-impressions attribute-crosspromotion-with-nonnative-platforms=%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-ios-%EC%9C%A0%EB%8B%88%ED%8B%B0-%EC%99%B8-non-native-%ED%94%8C%EB%9E%AB%ED%8F%BC%EC%97%90%EC%84%9C-%ED%81%AC%EB%A1%9C%EC%8A%A4-%ED%94%84%EB%A1%9C%EB%AA%A8%EC%85%98-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98%ED%95%98%EA%B8%B0 h_01HBDHCWSEKH16WSW0ANYFFH7A=%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-ios-%EC%9C%A0%EB%8B%88%ED%8B%B0-%EC%99%B8-non-native-%ED%94%8C%EB%9E%AB%ED%8F%BC%EC%97%90%EC%84%9C-%ED%81%AC%EB%A1%9C%EC%8A%A4-%ED%94%84%EB%A1%9C%EB%AA%A8%EC%85%98-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98%ED%95%98%EA%B8%B0" />
