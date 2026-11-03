---
title: Cross-promotion attribution for developers
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
  edited_at: '2026-10-26T13:10:48Z'
  id: 4410480466065
  locale: en-us
  section: Owned media attribution
  section_id: 6551214397585
  url: >-
    https://support.appsflyer.com/hc/en-us/articles/4410480466065-Cross-promotion-attribution-for-developers
---
> **At a glance:** Implement additional code in the AppsFlyer SDK to enable cross-promotion attribution.

## Implementing cross-promotion attribution in the SDK

> 📘 **Note**
>
> Regular mobile ads activate a URL when clicked. Cross-promotion mobile ads don't have a link, but instead, they activate the AppsFlyer SDK ***logAndOpenStore*** method.

Attributing cross-promotion clicks and impressions is performed by using two separate API calls as described below. Each API call can also be passed a map of key values, which can be anything that fits your cross-promotion use case.

For example, using the map of parameters you can set the click lookback window and other parameters such as ad IDs, ad sets. You can also mark the campaign as incentivized campaigns. See AppsFlyer attribution parameter for more information.

For a list of standard parameters that you can pass to the API method, see <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters">AppsFlyer attribution parameter.</Anchor>

With the first launch of the promoted app, all the original parameters can be accessed via the SDK's conversion data API, for <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data-android">Android</Anchor> or <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data-ios">iOS</Anchor>.

### Attribute cross-promotion clicks

Use the following code to attribute the click and launch the app store's app page. The code creates an attribution link and adds the device advertising ID to it.

<Tabs>
<Tab title="Android">

```java
String campaign = "Cross Promo Campaign";
Map<String, String> parameters = new HashMap();
parameters.put("af_sub1", "val");
parameters.put("custom_param", "val2");
CrossPromotionHelper.logAndOpenStore(this, "com.mygosoftware.android.loginbox", campaign, parameters);
```

</Tab>

<Tab title="iOS">

iOS allows you to utilize the StoreKit component to open the App Store while remaining in the context of your app. The following code snippet demonstrates how to open the StoreKit class and check that it has been properly initialized. You can read more about the StoreKit documentation <Anchor target="_blank" href="https://developer.apple.com/reference/storekit/skstoreproductviewcontroller">here</Anchor>.

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

<Tab title="Unity - Android">

```csharp
Dictionary<string,string> parameters = new Dictionary<string,string>();
parameters.Add("af_sub1","val");
parameters.Add("custom_param","val2");
AppsFlyer.attributeAndOpenStore("com.mygosoftware.android.loginbox","test campaign",parameters);
```

In Android, the call for this method should result in opening the Play Store and redirecting to the relevant app.

</Tab>

<Tab title="Unity - iOS">

```csharp
Dictionary<string,string> parameters = new Dictionary<string,string>();
parameters.Add("af_sub1","val");
parameters.Add("custom_param","val2")
AppsFlyer.attributeAndOpenStore("123456789","test campaign",parameters);
```

In iOS, an attribution Link is generated and returned to the `onOpenStoreLinkGenerated` method in the `IAppsFlyerUserInvite` interface.

</Tab>
</Tabs>

> 📘 **Note**
>
> You can add any of these <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters#paramètres-du-lien-dattribution">attribution link parameters</Anchor> to the generated link.

### Attribute cross-promotion impressions

To attribute an impression use the following API call. Make sure to use the promoted App ID as it appears within the AppsFlyer dashboard.

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

### Attribute cross-promotion with non-native platforms

Currently, the cross-promotion attribution APIs are available only for native Android and iOS SDKs and for Unity. However, **non-native platforms can perform cross-promotions attribution just as effectively.** These include platforms such as Adobe air, Cordova, Xamarin, React native, Marmalade etc.

**To do this you need to build an attribution Link, which is invoked when the user clicks on the cross-promotion ad**. The link MUST contain the media source name ***af\_cross\_promotion*** and the site ID of the source app.

Clicks cross-promotion URL format:

```http
https://{PREFIX}.app.appsflyersdk.com/{PROMOTED APP ID}?pid=af_cross_promotion&
af_siteid={SOURCE APP NAME}
```

Impressions cross-promotion URL format:

```http
https://impression.appsflyer.com/{PROMOTED APP ID}?pid=af_cross_promotion&
af_siteid={SOURCE APP NAME}
```

<div data-zendesk-anchors="implementing-crosspromotion-attribution-in-the-sdk=implementing-cross-promotion-attribution-in-the-sdk h_01HBDHCWSEPQFTYPXGZG2Y770S=implementing-cross-promotion-attribution-in-the-sdk attribute-crosspromotion-clicks=attribute-cross-promotion-clicks h_01HBDHCWSEB2709HGSKDR78J36=attribute-cross-promotion-clicks attribute-crosspromotion-impressions=attribute-cross-promotion-impressions h_01HBDHCWSE5CVWP7AMJ533S7DG=attribute-cross-promotion-impressions attribute-crosspromotion-with-nonnative-platforms=attribute-cross-promotion-with-non-native-platforms h_01HBDHCWSEKH16WSW0ANYFFH7A=attribute-cross-promotion-with-non-native-platforms" />
