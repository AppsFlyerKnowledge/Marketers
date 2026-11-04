---
title: Atribución de promoción cruzada para desarrolladores
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
  edited_at: '2026-10-27T03:49:32Z'
  id: 4410480466065
  locale: es
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/es/articles/4410480466065
---
> **At a glance:** Implementa código adicional en el SDK de AppsFlyer para habilitar la atribución de promoción cruzada.

<div id="implementing-cross-promotion-attribution-in-the-sdk" />

## Implementar la atribución de promoción cruzada en el SDK

> 📘 **Note**
>
> **Nota:**
>
> Los anuncios móviles normales activan una URL cuando se hace clic en ellos. Los anuncios móviles de promoción cruzada no tienen un enlace; en su lugar, activan el método ***logAndOpenStore*** del SDK de AppsFlyer.

La atribución de clics e impresiones de promoción cruzada se realiza mediante dos llamadas independientes a la API, como se describe a continuación. En cada llamada a la API también puedes pasar un mapa de valores de clave que puede contener cualquier dato que se ajuste a tu caso de uso de promoción cruzada.

Por ejemplo, con el mapa de parámetros puedes configurar la ventana de lookback de clic y otros parámetros, como los ID de anuncios y los conjuntos de anuncios. También puedes marcar la campaña como incentivada. Consulta el parámetro de atribución de AppsFlyer para obtener más información.

Para ver una lista de parámetros estándar que puedes pasar al método de la API, consulta <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">el parámetro de atribución de AppsFlyer.</Anchor>

Cuando se inicia por primera vez la aplicación promocionada, puedes acceder a todos los parámetros originales a través de la API de datos de conversión del SDK para <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data-android">Android</Anchor> o <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data-ios">iOS</Anchor>.

<div id="attribute-cross-promotion-clicks" />

### Atribuir clics de promoción cruzada

Usa el siguiente código para atribuir el clic y abrir la página de la aplicación en la tienda de aplicaciones. El código crea un enlace de atribución y le añade el ID de publicidad del dispositivo.

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

<Tab title="apps de iOS,">

iOS te permite utilizar el componente StoreKit para abrir la App Store sin salir del contexto de tu aplicación. El siguiente fragmento de código muestra cómo abrir la clase StoreKit y comprobar que se ha inicializado correctamente. Puedes leer más sobre la documentación de StoreKit <Anchor target="_blank" href="https://developer.apple.com/reference/storekit/skstoreproductviewcontroller">aquí</Anchor>.

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

En Android, la llamada a este método debería abrir Play Store y redirigir a la aplicación correspondiente.

</Tab>

<Tab title="Unity - iOS">

```csharp
Dictionary<string,string> parameters = new Dictionary<string,string>();
parameters.Add("af_sub1","val");
parameters.Add("custom_param","val2")
AppsFlyer.attributeAndOpenStore("123456789","test campaign",parameters);
```

En iOS, se genera un enlace de atribución y se devuelve al método `onOpenStoreLinkGenerated` en la interfaz `IAppsFlyerUserInvite`.

</Tab>
</Tabs>

> 📘 **Note**
>
> **Nota**
>
> Puedes añadir cualquiera de estos <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#parámetros-del-enlace-de-atribución">parámetros de enlace de atribución</Anchor> al enlace generado.

<div id="attribute-cross-promotion-impressions" />

### Atribuir impresiones de promoción cruzada

Para atribuir una impresión, usa la siguiente llamada a la API. Asegúrate de usar el ID de aplicación promocionado tal y como aparece en el panel de control de AppsFlyer.

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
    /* generar impresión para la promoción cruzada */
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

### Atribución de promoción cruzada con plataformas no nativas

Actualmente, las API de atribución de promoción cruzada solo están disponibles para los SDK nativos de Android e iOS y para Unity. Sin embargo, **las plataformas no nativas pueden realizar la atribución de promoción cruzada con la misma eficacia.** Entre ellas se incluyen plataformas como Adobe air, Cordova, Xamarin, React native, Marmalade, etc.

**Para ello, debes crear un enlace de atribución, que se activa cuando el usuario hace clic en el anuncio de promoción cruzada**. El enlace DEBE contener el nombre de la fuente de medios ***af\_cross\_promotion*** y el ID del sitio de la aplicación de origen.

Formato de URL de clics de promoción cruzada:

```http
https://{PREFIX}.app.appsflyersdk.com/{PROMOTED APP ID}?pid=af_cross_promotion&
af_siteid={SOURCE APP NAME}
```

Formato de URL de impresiones de promoción cruzada:

```http
https://impression.appsflyer.com/{PROMOTED APP ID}?pid=af_cross_promotion&
af_siteid={SOURCE APP NAME}
```

<div data-zendesk-anchors="implementing-crosspromotion-attribution-in-the-sdk=implementar-la-atribuci%C3%B3n-de-promoci%C3%B3n-cruzada-en-el-sdk h_01HBDHCWSEPQFTYPXGZG2Y770S=implementar-la-atribuci%C3%B3n-de-promoci%C3%B3n-cruzada-en-el-sdk attribute-crosspromotion-clicks=atribuir-clics-de-promoci%C3%B3n-cruzada h_01HBDHCWSEB2709HGSKDR78J36=atribuir-clics-de-promoci%C3%B3n-cruzada attribute-crosspromotion-impressions=atribuir-impresiones-de-promoci%C3%B3n-cruzada h_01HBDHCWSE5CVWP7AMJ533S7DG=atribuir-impresiones-de-promoci%C3%B3n-cruzada attribute-crosspromotion-with-nonnative-platforms=atribuci%C3%B3n-de-promoci%C3%B3n-cruzada-con-plataformas-no-nativas h_01HBDHCWSEKH16WSW0ANYFFH7A=atribuci%C3%B3n-de-promoci%C3%B3n-cruzada-con-plataformas-no-nativas" />
