---
title: Атрибуция кросс-промо кампаний для разработчиков
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
  edited_at: '2026-09-02T00:33:32Z'
  id: 4410480466065
  locale: ru
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/ru/articles/4410480466065
---
> **At a glance:** Реализуйте дополнительный код в SDK AppsFlyer, чтобы включить атрибуцию кросс-промо.

<div id="implementing-cross-promotion-attribution-in-the-sdk" />

## Реализация атрибуции перекрестной рекламы в SDK

> 📘 **Note**
>
> **Примечание**
>
> Обычные мобильные рекламные объявления при нажатии открывают URL-адрес. У мобильных объявлений кросс-промо нет ссылки: вместо этого они вызывают метод SDK AppsFlyer ***logAndOpenStore***.

Атрибуция кликов и показов кросс-промо выполняется с помощью двух отдельных вызовов API, как описано ниже. В каждый вызов API также можно передать карту пар «ключ-значение», которая может содержать любые данные для вашего сценария кросс-промо.

Например, с помощью карты параметров можно задать окно атрибуции по клику и другие параметры, такие как идентификаторы объявлений и группы объявлений. Вы также можете пометить кампанию как кампанию с вознаграждением. Подробнее см. в разделе «Параметры атрибуции AppsFlyer».

Список стандартных параметров, которые можно передать в метод API, см. в статье <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters">«Параметры атрибуции AppsFlyer»</Anchor>

При первом запуске продвигаемого приложения все исходные параметры доступны через API данных конверсии SDK для <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data-android">Android</Anchor> или <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data-ios">iOS</Anchor>.

<div id="attribute-cross-promotion-clicks" />

### Атрибуция кликов по кросс-промо

Используйте следующий код, чтобы атрибутировать клик и открыть страницу приложения в магазине приложений. Код создает ссылку атрибуции и добавляет в нее рекламный идентификатор устройства.

<Tabs>
<Tab title="Android iOS">

```java
String campaign = "Cross Promo Campaign";
Map<String, String> parameters = new HashMap();
parameters.put("af_sub1", "val");
parameters.put("custom_param", "val2");
CrossPromotionHelper.logAndOpenStore(this, "com.mygosoftware.android.loginbox", campaign, parameters);
```

</Tab>

<Tab title="adjusted.png">

iOS позволяет использовать компонент StoreKit для открытия App Store, оставаясь в контексте вашего приложения. Следующий фрагмент кода показывает, как открыть класс StoreKit и проверить, что он инициализирован правильно. Подробнее о документации StoreKit можно прочитать <Anchor target="_blank" href="https://developer.apple.com/reference/storekit/skstoreproductviewcontroller">здесь</Anchor>.

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

В Android вызов этого метода должен привести к открытию Play Store и перенаправлению на соответствующее приложение.

</Tab>

<Tab title="Unity - iOS">

```csharp
Dictionary<string,string> parameters = new Dictionary<string,string>();
parameters.Add("af_sub1","val");
parameters.Add("custom_param","val2")
AppsFlyer.attributeAndOpenStore("123456789","test campaign",parameters);
```

В iOS создаётся ссылка атрибуции и возвращается в метод `onOpenStoreLinkGenerated` интерфейса `IAppsFlyerUserInvite`.

</Tab>
</Tabs>

> 📘 **Note**
>
> **Вкладка «Разрешения»**
>
> К сгенерированной ссылке можно добавить любой из этих <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#параметры-ссылки-атрибуции">параметров ссылки атрибуции</Anchor>.

<div id="attribute-cross-promotion-impressions" />

### Атрибуция показов перекрестной рекламы

Для атрибуции показов используйте вызов следующего API. Обязательно используйте предлагаемый идентификатор приложения в том виде, в каком он отображается на дэшборде AppsFlyer.

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

### Атрибуция кросс-промо на ненативных платформах

В настоящее время API атрибуции перекрестной рекламы доступны только для нативных SDK Android и iOS, а также для Unity. Однако **на ненативных платформах тоже можно выполнять атрибуцию кросс-промо так же эффективно.** К ним относятся такие платформы, как Adobe Air, Cordova, Xamarin, React Native, Marmalade и т. д.

**Для этого нужно создать ссылку атрибуции, которая используется, когда пользователь кликает по рекламному объявлению кросс-промо**. Ссылка ОБЯЗАТЕЛЬНО должна содержать имя медиаисточника ***af\_cross\_promotion*** и идентификатор ID сайта исходного приложения.

Формат URL-адреса для кликов по перекрестной рекламе:

```http
https://app.appsflyer.com/{PROMOTED APP ID}?pid=af_cross_promotion&
af_siteid={SOURCE APP NAME}
```

Формат URL-адреса для показов перекрестной рекламы:

```http
https://impression.appsflyer.com/{PROMOTED APP ID}?pid=af_cross_promotion&
af_siteid={SOURCE APP NAME}
```

<div data-zendesk-anchors="implementing-crosspromotion-attribution-in-the-sdk=%D1%80%D0%B5%D0%B0%D0%BB%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D1%8F-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BF%D0%B5%D1%80%D0%B5%D0%BA%D1%80%D0%B5%D1%81%D1%82%D0%BD%D0%BE%D0%B9-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D1%8B-%D0%B2-sdk h_01HBDHCWSEPQFTYPXGZG2Y770S=%D1%80%D0%B5%D0%B0%D0%BB%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D1%8F-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BF%D0%B5%D1%80%D0%B5%D0%BA%D1%80%D0%B5%D1%81%D1%82%D0%BD%D0%BE%D0%B9-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D1%8B-%D0%B2-sdk attribute-crosspromotion-clicks=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BA%D0%BB%D0%B8%D0%BA%D0%BE%D0%B2-%D0%BF%D0%BE-%D0%BA%D1%80%D0%BE%D1%81%D1%81-%D0%BF%D1%80%D0%BE%D0%BC%D0%BE h_01HBDHCWSEB2709HGSKDR78J36=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BA%D0%BB%D0%B8%D0%BA%D0%BE%D0%B2-%D0%BF%D0%BE-%D0%BA%D1%80%D0%BE%D1%81%D1%81-%D0%BF%D1%80%D0%BE%D0%BC%D0%BE attribute-crosspromotion-impressions=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BF%D0%BE%D0%BA%D0%B0%D0%B7%D0%BE%D0%B2-%D0%BF%D0%B5%D1%80%D0%B5%D0%BA%D1%80%D0%B5%D1%81%D1%82%D0%BD%D0%BE%D0%B9-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D1%8B h_01HBDHCWSE5CVWP7AMJ533S7DG=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BF%D0%BE%D0%BA%D0%B0%D0%B7%D0%BE%D0%B2-%D0%BF%D0%B5%D1%80%D0%B5%D0%BA%D1%80%D0%B5%D1%81%D1%82%D0%BD%D0%BE%D0%B9-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D1%8B attribute-crosspromotion-with-nonnative-platforms=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BA%D1%80%D0%BE%D1%81%D1%81-%D0%BF%D1%80%D0%BE%D0%BC%D0%BE-%D0%BD%D0%B0-%D0%BD%D0%B5%D0%BD%D0%B0%D1%82%D0%B8%D0%B2%D0%BD%D1%8B%D1%85-%D0%BF%D0%BB%D0%B0%D1%82%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%85 h_01HBDHCWSEKH16WSW0ANYFFH7A=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BA%D1%80%D0%BE%D1%81%D1%81-%D0%BF%D1%80%D0%BE%D0%BC%D0%BE-%D0%BD%D0%B0-%D0%BD%D0%B5%D0%BD%D0%B0%D1%82%D0%B8%D0%B2%D0%BD%D1%8B%D1%85-%D0%BF%D0%BB%D0%B0%D1%82%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%85" />
