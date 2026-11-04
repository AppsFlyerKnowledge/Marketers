---
title: >-
  Uso do Firebase e do Google Tag Manager com a AppsFlyer - envio de instalações
  e eventos
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
  edited_at: '2026-08-18T00:12:51Z'
  id: 4410481550609
  locale: pt
  section: Firebase and Google Tag Manager
  section_id: 6551267006225
  url: https://support.appsflyer.com/hc/pt/articles/4410481550609
---
> **Num relance:** Instruções para configurar o envio de eventos relatados via Firebase SDK para a AppsFlyer em seu app.

<div id="configuring-events-in-the-app" />

## Configurar eventos no app

Esta seção aborda a forma de configurar e criar eventos na aplicação com o Google Tag Manager (GTM).

Quando o evento é enviado, o GTM verifica se existe uma etiqueta configurada para processar o evento com a ajuda do acionador de eventos. O acionador de eventos é definido para disparar a etiqueta sempre que um evento específico for enviado. Se um evento específico for enviado e tiver um acionador correspondente, a etiqueta é ativada. Quando a etiqueta é ativada, o Google Tag Manager recolhe todos os dados do evento. Esses dados incluem o ID da AppsFlyer, o nome do evento e os parâmetros do evento. Depois de recolher todos os dados, o Google Tag Manager envia o evento para a AppsFlyer.

<div id="creating-event-variables-for-revenue-and-price" />

<Accordion title="Criação de variáveis de evento para receita e preço">

<div id="ios" />

<div id="android" />

#### com o Android

<Tabs>
<Tab title="Java">

1. Na classe MainActivity, crie uma variável para guardar o ID do dispositivo da AppsFlyer:  

   ```java
   public static String appsFlyerID;
   ```
2. De volta à classe MainActivity, no método `onCreate` e depois de `super.onCreate`, passe o ID da AppsFlyer para a variável:

   ```java
   appsFlyerID = AppsFlyerLib.getInstance().getAppsFlyerUID(this);
   ```

</Tab>

<Tab title="Kotlin">

1. Na classe MainActivity, crie uma variável para guardar o ID do dispositivo da AppsFlyer:  

   ```kotlin
   var appsFlyerID: String? = nulo
   ```
2. De volta à classe MainActivity, no método `onCreate` e após `super.onCreate`, passe o valor de ID da AppsFlyer para a variável:

   ```kotlin
   override fun onCreate(savedInstanceState: Bundle?) {
    ... {
    ...
    appsFlyerID = AppsFlyerLib.getInstance().getAppsFlyerUID(this)
   }
   ```

</Tab>
</Tabs>

#### /docs/ctv-pc-and-console-platform-attribution-concepts

Para iOS, os parâmetros estão disponíveis em toda o app. Pode recuperá-los através da instância do AppsFlyerTracker.

<Tabs>
<Tab title="Objective C">

1. appsflyer\_device\_id

   ```objectivec
   [AppsFlyerTracker sharedTracker].getAppsFlyerUID
   ```
2. ID do app da Apple -

   ```objectivec
   [AppsFlyerTracker sharedTracker].appleAppID
   ```

</Tab>

<Tab title="Swift">

1. appsflyer\_device\_id

   ```swift
    AppsFlyerTracker.shared().getAppsFlyerUID()
   ```
2. ID do app da Apple -

   ```swift
   AppsFlyerTracker.shared().appleAppID
   ```

</Tab>
</Tabs>

</Accordion>

<div id="adding-events-in-the-app" />

<Accordion title="Adicionar eventos na aplicação">

O primeiro passo é configurar o evento na aplicação. O evento é enviado usando o Firebase Event Logging. No evento, você especifica o ID da AppsFlyer, o nome do evento e os parâmetros do evento. O ID da AppsFlyer é recuperado da variável que é criada na <Anchor target="_blank" href="/marketers/pt/docs/using-firebase-and-google-tag-manager-with-appsflyer-google-tag-manager-setup#configuração-do-google-tag-manager">etapa de configuração</Anchor>.

<Anchor target="_blank" href="https://developers.google.com/tag-manager/ios/v5/#log-events-and-variables">O Google Tag Manager utiliza</Anchor> os eventos <Anchor target="_blank" href="https://developers.google.com/tag-manager/ios/v5/#log-events-and-variables">do Firebase Analytics</Anchor> para acionar eventos de tag. Sempre que um evento é enviado para o Firebase, o Tag Manager reconhece o evento e envia-o também para a AppsFlyer.

<div id="android-1" />

#### com o Android

<Tabs>
<Tab title="Java">

1. Na atividade desejada, adicione a declaração de importação para o Firebase:  

   ```java
   import com.google.firebase.analytics. FirebaseAnalytics;
   ```
2. Adicione o seguinte código para ser executado sempre que ocorrer um evento de compra:

   ```java
   Bundle bundle = new Bundle();
     // observe "af_id", este é o nome do parâmetro do evento 
     // do ID da AppsFlyer que criamos na etapa anterior
     bundle.putString("af_id", appsFlyerID);
     bundle.putString("af_revenue", "200");
     bundle.putString("af_price", "250");
     mFirebaseAnalytics.logEvent("af_purchase", bundle);
   ```

</Tab>

<Tab title="Kotlin">

1. Na atividade desejada, adicione a declaração de importação para o Firebase:  

   ```java
   import com.google.firebase.analytics. FirebaseAnalytics
   ```
2. Adicione o seguinte código para ser executado sempre que ocorrer um evento de compra:

   ```kotlin
   val bundle = Bundle()
     // observe "af_id", este é o nome do parâmetro do evento
     // do ID da AppsFlyer que criamos na etapa anterior
     bundle.putString("af_id", appsFlyerID)
     bundle.putString("af_revenue", "200")
     bundle.putString("af_price", "250")
     FirebaseAnalytics.getInstance(this).logEvent("af_purchase", bundle)
   ```

</Tab>
</Tabs>

/docs/ctv-pc-and-console-platform-attribution-concepts

<Tabs>
<Tab title="Objective-C">

1. Na visualização para a qual o evento é enviado, adicione `@import Firebase`
2. Adicione o seguinte código para ser executado sempre que ocorrer um evento de compra:

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

1. Na visualização para a qual o evento é enviado, adicione `import Firebase`
2. Adicione o seguinte código para ser executado sempre que ocorrer um evento de compra:

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

## Enviando eventos de instalação para o Firebase

Você também pode enviar eventos de instalação para o Firebase com todos os dados relacionados à instalação.

<div id="android-2" />

#### com o Android

<Tabs>
<Tab title="Java">

Para enviar eventos de instalação para o Firebase no Android, pode utilizar o objeto `conversionData`.

<div id="creating-the-send-event-method" />

#### Criar o método de envio de eventos

Adicione o seguinte método na classe `AFApplication` logo abaixo do método `onCreate`:

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

Esse método aceita um objeto `conversionData`. O método verifica se a hora de instalação, a fonte de mídia e a campanha são nulas e, em caso afirmativo, define a hora de instalação como a hora atual e a fonte de mídia e a campanha como orgânicas. Caso contrário, obtém os dados do objeto `conversionData` e envia-os para o Firebase.

<div id="sending-the-install-event" />

#### Envio do evento de instalação

Adicione o seguinte código no método `onConversionDataSuccess`:

```java
if(conversionData.get("is_first_launch").equals("true")){
       sendInstallToFirebase(conversionData);
    }
```

Este código verifica se esta é a primeira vez que a aplicação é lançada. Em caso afirmativo, chama o método `sendInstallToFirebase`.

</Tab>

<Tab title="Kotlin">

Para enviar eventos de instalação para o Firebase no Android, pode utilizar o objeto `conversionData`.

<div id="creating-the-send-event-method-1" />

#### Criar o método de envio de eventos

Adicione o seguinte método na classe `AFApplication` logo abaixo do método `onCreate`:

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

Esse método aceita um objeto `conversionData`. O método verifica se a hora de instalação, a fonte de mídia e a campanha são nulas e, em caso afirmativo, define a hora de instalação como a hora atual e a fonte de mídia e a campanha como orgânicas. Caso contrário, obtém os dados do objeto `conversionData` e envia-os para o Firebase.

<div id="sending-the-install-event-1" />

#### Envio do evento de instalação

Adicione o seguinte código no método `onConversionDataSuccess`:

```kotlin
if(conversionData?.get("is_first_launch") == true){
      sendInstallToFirebase(conversionData);
  }
```

Este código verifica se esta é a primeira vez que a aplicação é lançada. Em caso afirmativo, chama o método `sendInstallToFirebase`.

**Nota:** A partir do SDK V5, `onConversionDataSuccess` é o nome do método para obter dados de conversão. Se você estiver usando uma versão do SDK abaixo de 5.0.0, o nome do método será onConversionDataReceived. Recomendamos que você atualize para o SDK 5.0.0. Clique <Anchor target="_blank" href="/marketers/pt/docs/links-to-appsflyer-sdk-release-notes">aqui</Anchor> para saber mais.

</Tab>
</Tabs>

#### /docs/ctv-pc-and-console-platform-attribution-concepts

<Tabs>
<Tab title="Objective-C">

<div id="creating-the-send-event-method-2" />

#### Criar o método de envio de eventos

Em AppDelegate.m, adicione o seguinte método no final do ficheiro:

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

Este método recebe o objeto `installData` e verifica se a instalação é orgânica ou não. Se for orgânico, define a hora de instalação para a hora atual e a fonte de multimídia, a campanha e o tipo de instalação para orgânico.

Se a instalação for não orgânica, o método obtém os dados de instalação não orgânica relevantes.

Uma vez definidos os parâmetros, o método envia o evento de instalação para o Firebase.

<div id="sending-the-install-event-2" />

<div id="ios-1" />

#### Envio do evento de instalação

Em AppDelegate.m, no método `didFinishLaunchingWithOptions`, adicione `[FIRApp configure]`

Em AppDelegate.m, no método `onConversionDataSuccess`, adicione o seguinte código no final do método:

```objectivec
if([installData objectForKey:@"is_first_launch"]){
      [self sendInstallToFirebase: installData];
    }
```

O fragmento de código acima verifica se esta é a primeira vez que a aplicação é lançada. Se for, chama o método `sendInstallToFirebase`.

</Tab>

<Tab title="Swift">

Em AppDelegate.swift, adicione o seguinte método no final do ficheiro:

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

**Nota:** A partir do SDK V5, `onConversionDataSuccess` é o nome do método para obter dados de conversão. Se você estiver usando uma versão do SDK abaixo de 5.0.0, o nome do método será onConversionDataReceived. Recomendamos que você atualize para o SDK 5.0.0. Clique <Anchor target="_blank" href="/marketers/pt/docs/links-to-appsflyer-sdk-release-notes">aqui</Anchor> para saber mais.

Este método aceita o objeto `installData` e verifica se a instalação é orgânica ou não. Se for orgânico, define a hora de instalação para a hora atual e a fonte de multimídia, a campanha e o tipo de instalação para orgânico.

Se a instalação for não orgânica, o método obtém os dados de instalação não orgânica relevantes.

Uma vez definidos os parâmetros, o método envia o evento de instalação para o Firebase.

<div id="sending-the-install-event-3" />

#### Envio do evento de instalação

Em AppDelegate.swift, no método `didFinishLaunchingWithOptions`, adicione `FirebaseApp.configure();`

Em AppDelegate.swift, no método `onConversionDataSuccess`, adicione o seguinte código no final do método:

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

**Nota:** A partir do SDK V5, `onConversionDataSuccess` é o nome do método para obter dados de conversão. Se você estiver usando uma versão do SDK abaixo de 5.0.0, o nome do método será **onConversionDataReceived**. Recomendamos que você atualize para o SDK 5.0.0. Clique <Anchor target="_blank" href="/marketers/pt/docs/links-to-appsflyer-sdk-release-notes">aqui</Anchor> para saber mais.

O fragmento de código acima verifica se esta é a primeira vez que a aplicação é lançada. Se for, chama o método `sendInstallToFirebase`.

</Tab>
</Tabs>

<div id="warning" />

> ❗️ **Aviso**
>
> Algumas fontes de mídia não permitem que os seus dados sejam compartilhados com plataformas e serviços de terceiros. Se você estiver trabalhando com parceiros, como Facebook, Twitter, Snap, Pinterest etc., que têm restrições definidas no compartilhamento de seus dados com plataformas e serviços de terceiros, certifique-se **de seguir suas diretrizes e remover quaisquer dados que estiverem sob essas restrições**.
>
> * <Anchor target="_blank" href="https://www.facebook.com/privacy/policy/">Política de dados dos meta-anúncios</Anchor>
> * <Anchor target="_blank" href="https://business.twitter.com/en/help/ads-policies/introduction-to-twitter-ads/twitter-ads-policies.html">Política de dados do Twitter</Anchor>
> * <Anchor target="_blank" href="https://www.snap.com/en-US/privacy/privacy-policy/">Política de dados do Snapchat</Anchor>
> * <Anchor target="_blank" href="https://policy.pinterest.com/en/privacy-policy">Política de dados do Pinterest</Anchor>

<div data-zendesk-anchors="configuring-events-in-the-app=configurar-eventos-no-app 01H8H2MH93M1SB9HEQNHDDJZP0=configurar-eventos-no-app 01H8H2MH93D36ZH7788XCMHHV6=creating-event-variables-for-revenue-and-price android=com-o-android 01H8H2MH93RNWN6N6EWE5T26V1=com-o-android ios=com-o-android 01H8H2MH93CZ5TACG3MWJ8YRFK=com-o-android 01H8H2MH9340PQCCKB85BQZQEG=adding-events-in-the-app android::eb294e42=com-o-android-1 01H8H2MH9357Z5M1DBK4Z9N22P=com-o-android-1 sending-install-events-to-firebase=enviando-eventos-de-instala%C3%A7%C3%A3o-para-o-firebase 01H8H2MH930VDZH5YSWEPTS8BN=enviando-eventos-de-instala%C3%A7%C3%A3o-para-o-firebase android::319436d3=com-o-android-2 01H8H2MH938Y980A9KA9BPP44Y=com-o-android-2 creating-the-send-event-method=criar-o-m%C3%A9todo-de-envio-de-eventos 01H8H2MH932WYSS6Z5NZJ3195X=criar-o-m%C3%A9todo-de-envio-de-eventos sending-the-install-event=envio-do-evento-de-instala%C3%A7%C3%A3o 01H8H2MH93H0WKMV5DAN713EY0=envio-do-evento-de-instala%C3%A7%C3%A3o creating-the-send-event-method::64b5a305=criar-o-m%C3%A9todo-de-envio-de-eventos 01H8H2MH93VYXGMM5H6ZQWCFZY=criar-o-m%C3%A9todo-de-envio-de-eventos sending-the-install-event::aeb9cdb7=envio-do-evento-de-instala%C3%A7%C3%A3o 01H8H2MH93VTPZNF51R05QPK7C=envio-do-evento-de-instala%C3%A7%C3%A3o ios::95ad6e27=envio-do-evento-de-instala%C3%A7%C3%A3o-2 01H8H2MH93AQE7PKVW4QKD2ARN=envio-do-evento-de-instala%C3%A7%C3%A3o-2 creating-the-send-event-method::346138b1=criar-o-m%C3%A9todo-de-envio-de-eventos-2 01H8H2MH93NGBRHBDQTX4DKNTY=criar-o-m%C3%A9todo-de-envio-de-eventos-2 sending-the-install-event::aca3c0e3=envio-do-evento-de-instala%C3%A7%C3%A3o-2 01H8H2MH93SWYFF2KTC1HJ06FF=envio-do-evento-de-instala%C3%A7%C3%A3o-2 sending-the-install-event::b6997ad3=envio-do-evento-de-instala%C3%A7%C3%A3o-2 01H8H2MH93Y5J8QH0YBKPQSV5N=envio-do-evento-de-instala%C3%A7%C3%A3o-2 01H8H2MH93JQBAR6ZTW77HHFQR=aviso" />
