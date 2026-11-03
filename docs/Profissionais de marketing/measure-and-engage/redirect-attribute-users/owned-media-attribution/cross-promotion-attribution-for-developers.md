---
title: Atribuição de promoção entre aplicativos para desenvolvedores
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
  edited_at: '2026-10-27T03:49:34Z'
  id: 4410480466065
  locale: pt
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/pt/articles/4410480466065
---
> **At a glance:** **Em resumo:** Implemente código adicional no SDK da AppsFlyer para habilitar a atribuição de promoção cruzada.

## Implementação da atribuição de promoção entre aplicativos no SDK

> 📘 **Note**
>
> **Importante!**
>
> Anúncios mobile comuns ativam uma URL quando são clicados. Anúncios mobile de promoção entre aplicativos não têm link; em vez disso, ativam o método ***logAndOpenStore*** do SDK da AppsFlyer.

A atribuição de cliques e impressões de promoção entre aplicativos é feita usando duas chamadas de API separadas, conforme descrito abaixo. Também é possível passar para cada chamada de API um mapa de valores-chave, que pode conter qualquer informação adequada ao seu caso de uso de promoção entre aplicativos.

Por exemplo, usando o mapa de parâmetros, você pode definir a janela de lookback de clique e outros parâmetros, como IDs de anúncios e conjuntos de anúncios. Você também pode marcar a campanha como campanha incentivada. Para mais informações, consulte o parâmetro de atribuição da AppsFlyer.

Para ver uma lista de parâmetros padrão que você pode passar ao método da API, consulte <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">Parâmetro de atribuição da AppsFlyer</Anchor>

No primeiro lançamento do aplicativo promovido, todos os parâmetros originais podem ser acessados pela API de dados de conversão do SDK, para <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data-android">Android</Anchor> ou <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data-ios">iOS</Anchor>.

### Atribuir cliques de promoção entre aplicativos

Use o código a seguir para atribuir o clique e abrir a página do aplicativo na loja de aplicativos. O código cria um link de atribuição e adiciona a ele o ID de publicidade do dispositivo.

<Tabs>
<Tab title="Android iOS">

```java
String campaign = "Cross Promo Campaign"; Map<String, String> parameters = new HashMap(); 
parameters.put("af_sub1", "val");
parameters.put("custom_param", "val2"); CrossPromotionHelper.logAndOpenStore(this, "com.mygosoftware.android.loginbox", campaign, parameters);
```

</Tab>

<Tab title="Exemplo">

iOS permite que você utilize o componente StoreKit para abrir a App Store enquanto permanece no contexto do seu aplicativo. O trecho de código a seguir demonstra como abrir a classe StoreKit e verificar se ela foi inicializada corretamente. Saiba mais sobre a documentação do StoreKit <Anchor target="_blank" href="https://developer.apple.com/reference/storekit/skstoreproductviewcontroller">aqui</Anchor>.

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
parameters. Add("af_sub1","val");
parameters. Add("custom_param","val2"); AppsFlyer.attributeAndOpenStore("com.mygosoftware.android.loginbox","test campaign",parameters);
```

No Android, a chamada desse método deve resultar na abertura da Play Store e no redirecionamento para o aplicativo relevante.

</Tab>

<Tab title="Unity - iOS">

```csharp
Dictionary<string,string> parameters = new Dictionary<string,string>();
parameters. Add("af_sub1","val");
parameters. Add("custom_param","val2")
AppsFlyer.attributeAndOpenStore("123456789","test campaign",parameters);
```

No iOS, um link de atribuição é gerado e retornado ao método `onOpenStoreLinkGenerated` na interface `IAppsFlyerUserInvite`.

</Tab>
</Tabs>

> 📘 **Note**
>
> **Importante!**
>
> Você pode adicionar qualquer um destes <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#parâmetros-do-link-de-atribuição">parâmetros de link de atribuição</Anchor> ao link gerado.

### Atribuir impressões de promoção cruzada

Para atribuir uma impressão, use a seguinte chamada de API. Certifique-se de usar o ID do aplicativo promovido da maneira como aparece no painel da AppsFlyer.

<Tabs>
<Tab title="Java">

```java
String appID = "com.app"; String campaign = "Cross Promo Campaign"; Map<String, String> parameters = new HashMap();
parameters.put("af_sub1", "val");
parameters.put("custom_param", "val2"); CrossPromotionHelper.logCrossPromoteImpression(this, appID, campaign, parameters);
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

<Tab title="Objetivo c">

```objectivec
static NSString *const kCrossPromotedAppId = @"123456789";
static NSString *const kCrossPromotedCampaign = @"test campaign";
/*...*/
- (void)viewDidLoad {
  [super viewDidLoad];  
    NSDictionary *kCrossPromotedParameters = @{@"af_sub1": @"val", @"custom_param": @"val2" };
    /* gerar impressão para cross-promotion */
     [AppsFlyerCrossPromotionHelper logCrossPromoteImpression:kCrossPromotedAppId
                       campaign:kCrossPromotedCampaign parameters:kCrossPromotedParameters];
 }
```

</Tab>

<Tab title="Swift">

```swift
Atribuir cliques de promoção entre aplicativos
```

</Tab>

<Tab title="Unity">

```csharp
AppsFlyer.recordCrossPromoteImpression(string promotedAppID, string campaign);
```

</Tab>
</Tabs>

### Atribuir promoção cruzada com plataformas não nativas

Atualmente, as APIs de atribuição de promoção cruzada estão disponíveis apenas para os SDKs nativos de Android e iOS e para Unity. No entanto, **plataformas não nativas podem realizar a atribuição de promoção cruzada com a mesma eficácia.** Elas incluem plataformas como Adobe Air, Cordova, Xamarin, React Native, Marmalade etc.

**Para fazer isso, você precisa criar um link de atribuição, que é acionado quando o usuário clica no anúncio de promoção cruzada**. O link DEVE conter o nome do canal de mídia ***af\_cross\_promotion*** e o ID do site do aplicativo de origem.

Formato da URL de cliques de promoção cruzada:

```http
https://{PREFIX}.app.appsflyersdk.com/{PROMOTED APP ID}?pid=af_cross_promotion&
af_siteid={SOURCE APP NAME}
```

Formato da URL de impressões de promoção cruzada:

```http
https://impression.appsflyer.com/{PROMOTED APP ID}?pid=af_cross_promotion&
af_siteid={SOURCE APP NAME}
```

<div data-zendesk-anchors="implementing-crosspromotion-attribution-in-the-sdk=implementa%C3%A7%C3%A3o-da-atribui%C3%A7%C3%A3o-de-promo%C3%A7%C3%A3o-entre-aplicativos-no-sdk h_01HBDHCWSEPQFTYPXGZG2Y770S=implementa%C3%A7%C3%A3o-da-atribui%C3%A7%C3%A3o-de-promo%C3%A7%C3%A3o-entre-aplicativos-no-sdk attribute-crosspromotion-clicks=atribuir-cliques-de-promo%C3%A7%C3%A3o-entre-aplicativos h_01HBDHCWSEB2709HGSKDR78J36=atribuir-cliques-de-promo%C3%A7%C3%A3o-entre-aplicativos attribute-crosspromotion-impressions=atribuir-impress%C3%B5es-de-promo%C3%A7%C3%A3o-cruzada h_01HBDHCWSE5CVWP7AMJ533S7DG=atribuir-impress%C3%B5es-de-promo%C3%A7%C3%A3o-cruzada attribute-crosspromotion-with-nonnative-platforms=atribuir-promo%C3%A7%C3%A3o-cruzada-com-plataformas-n%C3%A3o-nativas h_01HBDHCWSEKH16WSW0ANYFFH7A=atribuir-promo%C3%A7%C3%A3o-cruzada-com-plataformas-n%C3%A3o-nativas" />
