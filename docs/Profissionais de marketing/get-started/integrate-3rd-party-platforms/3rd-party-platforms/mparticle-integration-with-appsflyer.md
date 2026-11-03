---
title: integração do mParticle com AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - mParticle
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2016-04-03T05:31:23Z'
  edited_at: '2026-08-19T00:11:32Z'
  id: 209787323
  locale: pt
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/pt/articles/209787323
---
> **At a glance:** **Em resumo:** o mParticle, um parceiro integrado da AppsFlyer, coleta dados de clientes e os envia para diferentes plataformas de análise, marketing e armazenamento de dados.

> 🚧 **Important**
>
> **Importante!**
>
> <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#restrições-por-fonte-de-mídia">Algumas fontes de mídiarestringem</Anchor> o compartilhamento de dados com terceiros. Portanto, os postbacks de eventos restritos não serão enviados para esse parceiro, independentemente da configuração de envio de postbacks.

## Integrações de eventos

O objetivo deste documento é fornecer a você detalhes sobre como ativar dados de eventos do mParticle para a AppsFlyer.

1. os clientes do mParticle devem integrar o kit da AppsFlyer em seu aplicativo. O SDK do mParticle inicializará o SDK da AppsFlyer e também encaminhará todos os eventos de ciclo de vida necessários para o SDK da AppsFlyer.

2. Consulte os repositórios do GitHub dos SDKs de <Anchor target="_blank" href="https://github.com/mParticle/mParticle-apple-SDK">iOS</Anchor> e <Anchor target="_blank" href="https://github.com/mParticle/mparticle-android-sdk">Android</Anchor> para ver detalhes sobre como configurar o kit da AppsFlyer com o SDK do mParticle no seu aplicativo.

### Configurar a integração de eventos da AppsFlyer

1. No dashboard do mParticle ([https://app.mparticle.com](https://app.mparticle.com)), selecione seu aplicativo (também chamado de Workspace)

2. Clique em **Directory** na navegação à esquerda

3. Clique no bloco da AppsFlyer para exibir os detalhes da integração, que fornecem informações sobre a integração, como categorias, plataformas disponíveis, versões mínimas do SDK do mParticle (se houver), tipos de dados, IDs de usuário, IDs de dispositivo, eventos disponíveis e configurações disponíveis.

![Tile da AppsFlyer no Diretório da mParticle](https://files.readme.io/afa886e48f2cddde39007275a72ce03c4a6c4182408bb2ad4c8c183b1591b47d-115015666683.png)

4. Clique em **Add AppsFlyer to Setup**.

A janela **Add to Setup** é aberta:

![Janela Adicionar à Configuração da mParticle](https://files.readme.io/1eccc4ea365d41d4228eb07f4df88641458244b303ac8805932bf42ef4df5a74-115015476946.png)

5. Selecione o tipo de integração de evento de saída e clique em **Add to Setup** para abrir a tela de configuração de eventos, onde você poderá continuar o processo de configuração.

![Tela de Configuração do Evento da mParticle](https://files.readme.io/9a4720fef99a21a67fd017f4485e73765ebcb7aeb126f5342cc911aff4a345d2-115015476966.png)

6. Insira as configurações da AppsFlyer e clique em **Save**:

* Nome da configuração
* Usar as mesmas configurações para Desenvolvimento e Produção
* Dev Key
* A configuração que você acabou de criar é exibida no grupo padrão da AppsFlyer

![Configuração da AppsFlyer exibida no Grupo padrão da AppsFlyer](https://files.readme.io/4d82533f311b93373152f046e92fe46c5e515cb8f5084bb89e81bfcae608172c-115015666803.png)

A próxima etapa é estabelecer uma conexão entre suas plataformas de entrada e a configuração de evento de saída da AppsFlyer.

7. Clique em **Connections**.

8. Selecione a entrada (iOS neste exemplo) e depois clique em **Connect Output**.

9. Selecione o bloco da AppsFlyer e, em seguida, selecione a configuração da AppsFlyer criada acima.

10. Insira as configurações de conexão da AppsFlyer:  
Apple App ID (insira apenas o número, sem o prefixo ID. Por exemplo, se o ID do seu aplicativo for **id123456789**, insira **123456789**)

![Tela de configurações de conexão da AppsFlyer](https://files.readme.io/2fb4c7480c5813bf7d893318de5c4a8edfe3649293bf51c8dae422be65db726e-115015477066.png)

11. Clique em **Adicionar conexão**.

O AppsFlyer agora é exibido como uma Saída conectada. Outras opções, como Mapeamentos personalizados, podem estar disponíveis. Consulte a <Anchor target="_blank" href="https://docs.mparticle.com/guides/getting-started/connect-an-event-output#outputs">documentação da mParticle</Anchor> para mais informações.

![AppsFlyer exibida como uma saída conectada](https://files.readme.io/53ea474eeb94c551677dd7a4ce190d6ed5972d65eafacd773b61d4ebd954fe2c-115015667883.png)

## Integrações de feed

Esta seção ajuda você a entender como conectar um feed de dados do AppsFlyer à mParticle.

Informações gerais sobre a integração do AppsFlyer estão disponíveis em [https://docs.mparticle.com/integrations/appsflyer/feed/](https://docs.mparticle.com/integrations/appsflyer/feed/).

1. No Dashboard da mParticle (<Anchor target="_blank" href="https://app.mparticle.com">https://app.mparticle.com</Anchor>), selecione seu Aplicativo (também chamado de workspace)

2. Clique em **Directory** na navegação à esquerda

3. Clique no bloco do AppsFlyer para exibir os detalhes da integração, que fornecem informações sobre a integração.

![Tile da AppsFlyer no Diretório da mParticle](https://files.readme.io/53ea474eeb94c551677dd7a4ce190d6ed5972d65eafacd773b61d4ebd954fe2c-115015667883.png)
![Detalhes da integração da AppsFlyer na mParticle](https://files.readme.io/afa886e48f2cddde39007275a72ce03c4a6c4182408bb2ad4c8c183b1591b47d-115015666683.png)

4. Clique em **Adicionar AppsFlyer à configuração**.

5. Selecione o tipo de integração do feed de entrada e clique em **Adicionar à configuração**.

Agora você será direcionado para a tela de Setup, onde poderá continuar o processo de configuração.

6. Insira as configurações do AppsFlyer e clique em **Criar**:

* Nome da configuração
* Atuar como aplicativo

![Configurações de configuração do feed da AppsFlyer](https://files.readme.io/b27aff8223a98b0bf4bd73b6a7a04dc73bc245fa062ac9dd47ed6f4bbeece3f2-115015668703.png)

7. Conclua a configuração no dashboard do AppsFlyer usando as informações de autenticação fornecidas.

![Configuração de autenticação do dashboard da AppsFlyer](https://files.readme.io/3c751a38c3891f73485375d75eacde3e07f86969a7d44cd33bf29ace6bfa1875-115015478566.png)

## Deep linking diferido

O AppsFlyer permite que você acesse os dados de atribuição do usuário em tempo real, diretamente no nível do SDK. Ele possibilita que você personalize as páginas de destino que um usuário vê quando o aplicativo abre pela primeira vez após uma nova instalação do aplicativo. Isso normalmente é chamado de vinculação profunda "adiada".

Para mais detalhes sobre deferred deep linking, clique <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">aqui</Anchor>.

Os dados de conversão da AppsFlyer contêm um parâmetro chamado `is_First_Launch`. O valor de `is_First_Launch` é 'true' somente na primeira inicialização e 'false' em todas as inicializações seguintes. Você pode usar esse parâmetro para determinar, em cada inicialização, se o Aplicativo deve fazer Deferred deep linking para o usuário ou não.

```
af_dp → $deeplink_path
```

> 📘 **Note**
>
> **Exemplo**
>
> ```
> $deeplink_path=product/Banana-Pet-Costume/dd67268672b345e491656c871af8aa29
> ```
>
> `af_dp` inclui o esquema de URI codificado e o caminho
>
> `af_dp` →
>
> `%20jet%3A%2F%2Fproduct%2FBanana-Pet-Costume%2Fdd67268672b345e491656c871af8aa29`

<Tabs>
<Tab title="com o Android">

Para Android: faça isso com Shared Preferences: <Anchor target="_blank" href="https://developer.android.com/reference/android/content/SharedPreferences.html">aqui.</Anchor>

```java
AttributionListener myListener = new AttributionListener() {
  @Override
  public void onResult(@NonNull AttributionResult attributionResult) {
   if (attributionResult.getServiceProviderId() == MParticle. ServiceProviders.APPSFLYER) {
    JSONObject attributionParams = attributionResult.getParameters();
    if (attributionParams != null && attributionParams.has(AppsFlyerKit.INSTALL_CONVERSION_RESULT)) {
     Log.d("Resultado da conversão", attributionParams.toString());
    } else if (attributionParams != null && attributionParams.has(AppsFlyerKit.APP_OPEN_ATTRIBUTION_RESULT)) {
     Log.d("Resultado de abertura do Aplicativo", attributionParams.toString());
    }
   }
  }

  @Override
  public void onError(@NonNull AttributionError attributionError) {
   Log.d("Erro de dados de atribuição", attributionError.toString());
  }
 };

 MParticleOptions options = MParticleOptions.builder(this)
  .credentials("replaceWithAPIKey", "replace-withAPISecret")
  .attributionListener(myListener)
  .build();

 MParticle.start(options);
```

</Tab>

<Tab title="/docs/ctv-pc-and-console-platform-attribution-concepts">

Para iOS: faça isso em UserDefaults: <Anchor target="_blank" href="https://developer.apple.com/documentation/foundation/userdefaults">aqui</Anchor>

```objectivec
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
 MParticleOptions *options = [MParticleOptions optionsWithKey:@"<>" secret:@"<>"];
 options.onAttributionComplete = ^void (MPAttributionResult *_Nullable attributionResult, NSError * _Nullable error) {
  if (error) {
   NSLog(@"A recuperação de atribuição para kitCode=%@ falhou com o erro=%@", error.userInfo[mParticleKitInstanceKey], error);
   return;
  }
  NSLog(@"A recuperação de atribuição para kitCode=%@ foi concluída com linkInfo: %@", attributionResult.kitCode, attributionResult.linkInfo);
 }
 [[MParticle sharedInstance] startWithOptions:options];
 return YES;
}
```

</Tab>
</Tabs>

### Casos de uso de AppsFlyer/mparticle

| Caso de uso | Plataforma | Método do SDK da AppsFlyer | Método do Kit mParticle-AF |
| --- | --- | --- | --- |
| https://files.readme.io/1eccc4ea365d41d4228eb07f4df88641458244b303ac8805932bf42ef4df5a74-115015476946.png | /docs/ctv-pc-and-console-platform-attribution-concepts | onConversionDataSuccess | checkForDeferredDeepLinkWithCompletionHandler |
| links universais | /docs/ctv-pc-and-console-platform-attribution-concepts | continueUserActivity | continueUserActivity |
| Abertura do app | Exemplo | onAppOpenAttribution | checkForDeferredDeepLinkWithCompletionHandler |
| Deep linking diferido | com o Android | onConversionDataSuccess | checkForDeepLink |
| Links do Aplicativo Android | com o Android |  | continueUserActivity |
| Abertura do app | Android / iOS | onAppOpenAttribution | checkForDeepLink |

### Como lidar com sinalizadores do usuário

A AppsFlyer também permite que você exiba conteúdo personalizado ou envie usuários existentes para locais específicos no aplicativo APÓS a primeira abertura. Quando usuários existentes entram no Aplicativo por Deep linking, o Aplicativo é aberto pelo método `onOpenAttribution`, que retorna os dados da URL de referência.

```swift
 if let conversionData = params?[MPKitAppsFlyerConversionResultKey] as? [AnyHashable: Any], !alreadyLoggedAppsflyerConversionData {
   logAppsflyerConversionData(conversionData: conversionData)
   alreadyLoggedAppsflyerConversionData = true
   if let onelinkURL = (conversionData["af_dp"] as? String).flatMap(URL.init) {
    UIApplication.appDelegate._linkController.handle(onelinkURL, source: .appsflyer)
   }
  } else if let appOpenData = params?[MPKitAppsFlyerAppOpenResultKey] as? [AnyHashable: Any] {
   logAppsflyerAppOpenData(appOpenData: appOpenData as? [String: Any])
  }
```

A AppsFlyer usa ***UserDefaults*** no iOS e ***Shared Preferences*** no Android para indicar se o usuário está abrindo o aplicativo pela primeira vez e deve ser redirecionado para a página apropriada, ou se o aplicativo já foi aberto e o usuário já foi direcionado para essa página. Para isso, o valor `alreadyLoggedAppsflyerConversionData` é lido e gravado em UserDefaults/ Shared Preferences, para que o valor ***af\_dp*** não seja considerado na primeira inicialização.

Para mais detalhes sobre como fornecer conteúdo personalizado em deep linking, <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">clique aqui</Anchor>.

## Como ativar a mensuração de desinstalação da AppsFlyer no mParticle

A mensuração de desinstalação da AppsFlyer não é ativada automaticamente com o kit SDK mParticle-AppsFlyer. Para mensurar desinstalações de aplicativos, chame os métodos da AppsFlyer diretamente seguindo a documentação de mensuração de desinstalação da AppsFlyer.

**Para implementar a mensuração de desinstalação no iOS ou no Android:**

* Chame os métodos da AppsFlyer diretamente seguindo nossa documentação de mensuração de desinstalação

<div data-zendesk-anchors="event-integrations=integra%C3%A7%C3%B5es-de-eventos h_01H9HWJRM2612MBM2Y7C5YZ2YY=integra%C3%A7%C3%B5es-de-eventos configure-the-appsflyer-event-integration=configurar-a-integra%C3%A7%C3%A3o-de-eventos-da-appsflyer h_01H9HWJRM2BJATV1QHS382J0ZN=configurar-a-integra%C3%A7%C3%A3o-de-eventos-da-appsflyer feed-integrations=integra%C3%A7%C3%B5es-de-feed h_01H9HWJRM2YV3CEH7J7EMA8E3Y=integra%C3%A7%C3%B5es-de-feed deferred-deep-linking=deep-linking-diferido h_01H9HWJRM2SZYRXFTSZPM1JHCJ=deep-linking-diferido appsflyermparticle-use-cases=casos-de-uso-de-appsflyermparticle h_01H9HWJRM2HCB4YF2BP9RPK2RP=casos-de-uso-de-appsflyermparticle handling-user-flags=como-lidar-com-sinalizadores-do-usu%C3%A1rio h_01H9HWJRM3HAGGWHF4YTQTTS2X=como-lidar-com-sinalizadores-do-usu%C3%A1rio known-mparticle-integration-limitation=como-ativar-a-mensura%C3%A7%C3%A3o-de-desinstala%C3%A7%C3%A3o-da-appsflyer-no-mparticle h_01H9HWJRM321PSNQ480R96BN12=como-ativar-a-mensura%C3%A7%C3%A3o-de-desinstala%C3%A7%C3%A3o-da-appsflyer-no-mparticle" />
