---
title: ディベロッパー向けクロスプロモーション計測
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
  edited_at: '2026-10-14T09:27:47Z'
  id: 4410480466065
  locale: ja
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/ja/articles/4410480466065
---
> **概要：** 概要：AppsFlyer SDKに追加コードを実装してクロスプロモーション計測を有効にしましょう。

## SDKにクロスプロモーション計測を実装

> 📘 **注**
>
> 通常のモバイル広告では、クリックされるとURLがアクティベートされます。クロスプロモーションのモバイル広告ではリンクが存在しませんが、代わりにAppsFlyer SDKの ***logAndOpenStore*** メソッドでアクティベートされます。

クロスプロモーションのクリックとインプレッションの計測は、次の2つの異なるAPIコールを使用して実行されます。各APIコールは、クロスプロモーションのユースケースに適用するどんなキーと値のMapに引き渡すことも可能です。

例えば、パラメーターのマップを使用して、クリックルックバック期間や広告ID、広告セットなど、その他のパラメーターを設定できます。キャンペーンをインセンティブキャンペーンとしてマークすることもできます。詳細については、AppsFlyerの計測パラメーターを参照してください。

APIメソッドに引き渡すことができる標準パラメーターの一覧については、 <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters">AppsFlyerの計測パラメーター</Anchor>を参照してください。

広告対象のアプリが初回起動すると、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data-android">Android</Anchor> または <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data-ios">iOS</Anchor> のいずれも、SDKのコンバージョンデータAPIを介して全ての計測リンク上のパラメーターにアクセスできます。

### クロスプロモーションのクリック計測

次のコードを使用して、クリックとアプリのアプリストアページの起動を計測します。このコードは、計測リンクを作成し、デバイスの広告IDを追加します。

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

iOSでは、StoreKit コンポーネントを使用して、アプリのコンテキストを維持しながら、App Storeを開くことができます。次のコードスニペットは、StoreKitクラスを開き、正常に初期化されたことを確認する方法をしています。StoreKitのドキュメントについて詳細は、<Anchor target="_blank" href="https://developer.apple.com/reference/storekit/skstoreproductviewcontroller">こちら</Anchor>をご覧ください。

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

Androidでは、このメソッドの呼び出すことで、Play Storeを開き、該当するアプリにリダイレクトされます。

</Tab>

<Tab title="Unity - iOS">

```csharp
Dictionary<string,string> parameters = new Dictionary<string,string>();
parameters.Add("af_sub1","val");
parameters.Add("custom_param","val2")
AppsFlyer.attributeAndOpenStore("123456789","test campaign",parameters);
```

</Tab>
</Tabs>

> 📘 **注**
>
> <Anchor target="_blank" href="/marketers/ja/docs/about-link-structure-and-parameters#計測リンクのパラメータ">生成されたリンクには、</Anchor>これらの計測リンクパラメーターのいずれも追加することができます。

### クロスプロモーションのインプレッション計測

インプレッションを計測するには、次のAPIコールを使用します。AppsFlyerの管理画面上に表示されているAppIDを使用してください。

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

### ネイティブ以外のプラットフォームでクロスプロモーションを計測

現在、クロスプロモーション計測 APIは、ネイティブのAndroid および iOS SDKと、Unityのみでご利用いただけます。ただし、**非ネイティブプラットフォームも、同様に効果的にクロスプロモーションを計測できます**。これらのプラットフォームには、Adobe air、Cordova、Xamarin、React native、Marmaladeなどが含まれます。

**そのためには、ユーザーがクロスプロモーション広告をクリックした際に呼び出される計測リンクを構築する必要があります**。このリンクには、メディアソース名である ***af\_cross\_promotion*** と、広告が掲載されるアプリのサイトIDを含める必要があります。

クリック用のクロスプロモーションURL形式：

```http
https://app.appsflyer.com/{PROMOTED APP ID}?pid=af_cross_promotion&
af_siteid={SOURCE APP NAME}
```

インプレッション用のクロスプロモーションURL形式：

```http
https://impression.appsflyer.com/{PROMOTED APP ID}?pid=af_cross_promotion&
af_siteid={SOURCE APP NAME}
```

<div data-zendesk-anchors="implementing-crosspromotion-attribution-in-the-sdk=sdk%E3%81%AB%E3%82%AF%E3%83%AD%E3%82%B9%E3%83%97%E3%83%AD%E3%83%A2%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E8%A8%88%E6%B8%AC%E3%82%92%E5%AE%9F%E8%A3%85 h_01HBDHCWSEPQFTYPXGZG2Y770S=sdk%E3%81%AB%E3%82%AF%E3%83%AD%E3%82%B9%E3%83%97%E3%83%AD%E3%83%A2%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E8%A8%88%E6%B8%AC%E3%82%92%E5%AE%9F%E8%A3%85 h_01HBDHCWSEFSZKDEJYVABG4SMC=%E6%B3%A8 attribute-crosspromotion-clicks=%E3%82%AF%E3%83%AD%E3%82%B9%E3%83%97%E3%83%AD%E3%83%A2%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E8%A8%88%E6%B8%AC h_01HBDHCWSEB2709HGSKDR78J36=%E3%82%AF%E3%83%AD%E3%82%B9%E3%83%97%E3%83%AD%E3%83%A2%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E3%82%AF%E3%83%AA%E3%83%83%E3%82%AF%E8%A8%88%E6%B8%AC h_01HBDHCWSESWH645GDT4N9VCVP=%E6%B3%A8-1 attribute-crosspromotion-impressions=%E3%82%AF%E3%83%AD%E3%82%B9%E3%83%97%E3%83%AD%E3%83%A2%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E3%82%A4%E3%83%B3%E3%83%97%E3%83%AC%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3%E8%A8%88%E6%B8%AC h_01HBDHCWSE5CVWP7AMJ533S7DG=%E3%82%AF%E3%83%AD%E3%82%B9%E3%83%97%E3%83%AD%E3%83%A2%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%81%AE%E3%82%A4%E3%83%B3%E3%83%97%E3%83%AC%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3%E8%A8%88%E6%B8%AC attribute-crosspromotion-with-nonnative-platforms=%E3%83%8D%E3%82%A4%E3%83%86%E3%82%A3%E3%83%96%E4%BB%A5%E5%A4%96%E3%81%AE%E3%83%97%E3%83%A9%E3%83%83%E3%83%88%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0%E3%81%A7%E3%82%AF%E3%83%AD%E3%82%B9%E3%83%97%E3%83%AD%E3%83%A2%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%82%92%E8%A8%88%E6%B8%AC h_01HBDHCWSEKH16WSW0ANYFFH7A=%E3%83%8D%E3%82%A4%E3%83%86%E3%82%A3%E3%83%96%E4%BB%A5%E5%A4%96%E3%81%AE%E3%83%97%E3%83%A9%E3%83%83%E3%83%88%E3%83%95%E3%82%A9%E3%83%BC%E3%83%A0%E3%81%A7%E3%82%AF%E3%83%AD%E3%82%B9%E3%83%97%E3%83%AD%E3%83%A2%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E3%82%92%E8%A8%88%E6%B8%AC" />
