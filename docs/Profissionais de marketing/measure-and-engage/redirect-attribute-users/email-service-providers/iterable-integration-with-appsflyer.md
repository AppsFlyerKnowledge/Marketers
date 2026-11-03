---
title: Integração do Iterable com a AppsFlyer
metadata:
  keywords:
    - OneLink
    - Advertisers
    - ESP
    - Developers
    - Iterable
    - Deep Likning
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2019-09-16T13:14:19Z'
  edited_at: '2026-08-19T00:33:54Z'
  id: 360002522337
  locale: pt
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/pt/articles/360002522337
---
> **At a glance:** **Visão geral:** Integre links de atribuição baseados no OneLink com o sistema Iterable para <Anchor target="_blank" href="/marketers/pt/docs/email-service-provider-esp-integration-guide">criar deep link de e-mails</Anchor>. A integração usa o suporte do Iterable para links universais além de domínios de gravação de cliques de marca.

![iterable-af-logo.png](https://files.readme.io/e339ea75a54e53711f3c577c7f82339151af13e6c086cc1435cbb57cf1fae3f0-49839295443089.png)

## Introdução

ESPs (Email Service Providers ou provedores de serviços de e-mail) podem ser excelentes fontes de tráfego segmentado de usuários.

Um dos problemas com ESPs é registrar cliques enquanto mantém a funcionalidade de deep linking intacta. Os ESPs agrupam os URLs do deep link com seu próprio domínio de gravação de cliques do ESP. Este procedimento às vezes interrompe o processo de Links Universais do iOS.

Com o Iterable, que é compatível com Links Universais além do seu domínio de gravação de cliques, é possível ainda executar deep linking e gravação de cliques.

## Pré-requisitos

<Tabs>
<Tab title="https://files.readme.io/e339ea75a54e53711f3c577c7f82339151af13e6c086cc1435cbb57cf1fae3f0-49839295443089.png">

* AppsFlyer iOS SDK versão 4.9.0

</Tab>

<Tab title="Android iOS">

* AppsFlyer Android SDK versão 4.9.0

O Iterable não é compatível com Links de aplicativo do Android O Iterable não é compatível com Links de aplicativo do Android O Iterable não é compatível com Links de aplicativo do Android No entanto, <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">o deep linking do esquema URI ainda é compatível</Anchor>. Nenhuma ação especial é necessária no Iterable ter compatibilidade com deep links no Android.

</Tab>
</Tabs>

## Configurando o Iterable

### Etapa 1: Configurando a marca de link no Iterable

Crie um domínio de gravação de cliques dedicado e defina um subdomínio (por exemplo, [click.exemplo.com](http://click.example.com))). Isso pode ser feito comprando um domínio designado ou usando seu próprio domínio.

Para obter mais informações sobre como definir um domínio de gravação de cliques com o Iterable, clique <Anchor target="_blank" href="https://support.iterable.com/hc/en-us/articles/115002651226-Setting-up-mail-domains">aqui</Anchor>.

### Etapa 2: Fazendo upload do seu certificado SSL para Iterable

Seu domínio de gravação de cliques deve incluir o certificado SSL do seu domínio. O certificado SSL deve ser instalado na sua conta do Iterable. Instruções sobre como instalar seus certificados SSL podem ser encontradas<Anchor target="_blank" href="https://support.iterable.com/hc/en-us/articles/115000427446-How-to-Set-up-HTTPS-for-Links-for-Click-Tracking">aqui</Anchor>.

### Etapa 2: Dê ao Iterable um arquivo AASA (iOS) e um arquivo Asset Links (Android)

<div id="aasa-for-ios" />

<Accordion title="AASA para iOS">

Para que o Iterable seja compatível com links universais do iOS, ele precisa de um arquivo AASA. Veja as instruções a seguir.

Ao configurar o OneLink com Universal Links, você já tem um AASA associado ao OneLink. Para obter o AASA:

1. Vá para ***Templates do OneLink*** e encontre um OneLink configurado com Universal Links.
2. Adicione **/.well-known/apple-app-site-association** ao final do URL do OneLink.
3. Cole o OneLink na barra de endereço do navegador e pressione Enter. Por exemplo: **`<OneLinkSubdomain>`.onelink.me/.well-known/apple-app-site-association**. Ao fazer isso, o arquivo AASA é baixado para o seu computador. Você pode abri-lo usando qualquer editor de texto simples.
4. Defina regras de reescrita de links. Clique <Anchor target="_blank" href="https://support.iterable.com/hc/en-us/articles/360035496511">aqui</Anchor> para mais informações.
5. Envie este arquivo AASA para o Iterable. Para obter mais informações e saber mais sobre o conteúdo deste arquivo, consulte <Anchor target="_blank" href="https://support.iterable.com/hc/en-us/articles/360035496511-iOS-Universal-Lin">o guia do Iterable</Anchor>.

</Accordion>

<div id="asset-links-for-android" />

<Accordion title="Asset Links para Android">

Ao configurar o OneLink com App Links, você já tem um arquivo Asset Links associado ao OneLink. Para obter o arquivo Asset Links:

1. Acesse ***os templates do OneLink*** e encontre um OneLink configurado com App Links.
2. Adicione **/.well-known/assetlinks.json** ao final do URL do OneLink.
3. Cole o OneLink na barra de endereço do navegador e pressione Enter. Por exemplo:**`<OneLinkSubdomain>`.onelink.me/.well-known/assetlinks.json**. Ao fazer isso, o arquivo Asset Links é baixado para o seu computador. Você pode abri-lo usando qualquer editor de texto simples.
4. Envie este arquivo do Asset Links para o Iterable. Para obter mais informações e saber mais sobre o conteúdo deste arquivo, consulte <Anchor target="_blank" href="https://support.iterable.com/hc/en-us/articles/360035127392">o guia do Iterable</Anchor>.

</Accordion>

## Configurando seu aplicativo

Veja o seguinte para configurar seus aplicativos para que eles sejam compatíveis com App Links e Universal links.

<div id="step-1-for-android-setting-up-your-app-to-support-app-links" />

<Accordion title="Etapa 1 para Android: Configurando seu aplicativo para que ele seja compatível com App Links">

#### Etapa 1: Adicionando o domínio de clique à atividade no manifesto do Android

No manifesto do Android, adicione o host do domínio de clique e qualquer prefixo na tag de atividade da atividade à qual você deseja conectar um deep link.

```html Markup
<activity android:name=". DeepLinkActivity">
    <intent-filter  android:autoVerify="true">
        <action android:name="android.intent.action.VIEW" />
           <category android:name="android.intent.category.DEFAULT" />
           <category android:name="android.intent.category.BROWSABLE" />
           <data android:scheme="https"
               android:host="click.example.com"
               android:pathPrefix="/campaign" />
     </intent-filter>
</activity>
```

#### Etapa 2: Configurando o aplicativo para resolver domínios de cliques

O SDK precisa resolver o OneLink por trás do domínio de clique para obter os detalhes da campanha. Os detalhes são retornados no método `onAppOpenAttribution`.

Para resolver domínios de clique:

1. Certifique-se de que sua versão do SDK seja pelo menos 4.9.0.
2. Listar os domínios de clique na API do SDK `setResolveDeepLinkURLs`. Esta API precisa ser chamada antes da inicialização do SDK. Para mais informações, consulte a documentação do SDK <Anchor target="_blank" href="/marketers/pt/docs/additional-sdk-integration-guide#resolve-wrapped-deep-link-urls">aqui</Anchor>.  

   ```java
   AppsFlyerLib.getInstance().setResolveDeepLinkURLs("click.example.com");
   ```

</Accordion>

<div id="step-1-for-ios-setting-up-your-app-to-support-universal-links" />

<Accordion title="Etapa 1 para iOS: Configurando seu aplicativo para que ele seja compatível com o Universal Links">

Esta seção é sobre como configurar seu aplicativo para que ele seja compatível com Universal Links.

#### Etapa 1: Associando domínios de clique no Xcode

1. No Xcode, clique no seu projeto.
2. Clique em ***Recursos***. ![configure-xcode-deeplinking-domain.png](https://files.readme.io/90d0dcc0eba2d7d081ab7d5d4ea697e9257b9107af463fa8c973169f8a2651db-49839256220433.png)
3. Ative ***Domínios Associados***.
4. Clique no sinal + e adicione seu domínio de clique. Por exemplo, applinks:click.example.com.

</Accordion>

Veja o seguinte para configurar o SDK para resolver deep links.

<div id="step-2-for-android-resolve-deep-links" />

<Accordion title="Etapa 2 para Android: resolver deep links">

O SDK precisa resolver o OneLink por trás do domínio de clique para obter os detalhes da campanha. Os detalhes são retornados no método `onAppOpenAttribution`.

Para resolver domínios de clique:

1. Certifique-se de que sua versão do SDK seja pelo menos 4.9.0.
2. Liste os domínios de clique na propriedade do SDK `resolveDeepLinkURLs`. Esta propriedade precisa ser definida antes da inicialização do SDK. Para mais informações, consulte a documentação do SDK <Anchor target="_blank" href="/marketers/pt/docs/additional-sdk-integration-guide#resolve-wrapped-deep-link-urls">aqui</Anchor>.  

   ```java
   AppsFlyerLib.getInstance().setResolveDeepLinkURLs("clickdomain.com", "myclickdomain.com", "anotherclickdomain.com");
   ```

</Accordion>

<div id="step-2-for-ios-resolve-deep-links" />

<Accordion title="Etapa 2 para iOS: resolver deep links">

O SDK precisa resolver o OneLink por trás do domínio de clique para obter os detalhes da campanha. Os detalhes são retornados no método `onAppOpenAttribution`.

Para resolver domínios de clique:

1. Certifique-se de que sua versão do SDK seja pelo menos 4.9.0.
2. Liste os domínios de clique na propriedade do SDK `resolveDeepLinkURLs`. Esta propriedade precisa ser definida antes da inicialização do SDK. Para mais informações, consulte a documentação do SDK <Anchor target="_blank" href="/marketers/pt/docs/additional-sdk-integration-guide#resolve-wrapped-deep-link-urls">aqui</Anchor>.  

   <Tabs>
   <Tab title="Objetivo-C">

   ```objectivec
   [AppsFlyerLib shared].resolveDeepLinkURLs = @[@"example.com",@"click.example.com"];
   ```

   </Tab>

   <Tab title="Swift">

   ```swift
   AppsFlyerLib.shared().resolveDeepLinkURLs = ["example.com", "click.example.com"]
   ```

   </Tab>
   </Tabs>

3. Adicione o seguinte código para que o SDK possa resolver o domínio de gravação de cliques:  

   <Tabs>
   <Tab title="Objetivo-C">

   Adicione este código em AppDelegate.m

   ```objectivec
   - (NSDictionary *)allHTTPHeaderFieldsForResolveDeepLinkURL:(NSURL *)URL {
       if ([URL.host  isEqual: @"click.example.com"]) {
           return [NSDictionary dictionary];
       }
       else {
           return nil;
       }
   }
   ```

   </Tab>

   <Tab title="Swift">

   Adicione este código em AppDelgate.swift

   ```swift
   func allHTTPHeaderFields(forResolveDeepLinkURL URL: URL!) -> [String : String]! -> [String : String]! {
       if (URL.host == "click.example.com") {
           /// Alterar o User-Agent
           return [:]
       } else {
           return nil;
       }
   }
   ```

   </Tab>
   </Tabs>

</Accordion>

## Enviando seu primeiro e-mail

1. Crie uma URL do OneLink na página Gerenciamento de links (ou manualmente).
2. Ao criar o URL do OneLink, certifique-se de codificar o URL de todos os valores dos parâmetros.
3. Os seguintes parâmetros são altamente recomendados para uso:
   * pid (fonte de mídia) - Use uma fonte de mídia que signifique esse uso, como E-mail.
   * c (campanha) – O nome da campanha que você deseja medir.
   * af\_dp - O esquema de URI de deep link ao qual você deseja vincular seus usuários.
   * af\_web\_dp - Para onde redirecionar os usuários que clicam no link no desktop.
   * af\_ios\_url - Para onde redirecionar usuários que não têm o aplicativo e que clicam no link em um dispositivo iOS.
   * af\_android\_url - Para onde redirecionar usuários que não têm o aplicativo que clicam no link em um dispositivo Android.
4. Coloque o URL do OneLink no e-mail que você cria no Iterable. Exemplo:

   ```http
   <a href="greatapp.onelink.me/abcd/1234567">Download my great app!</a>
   ```

   Nesse estágio, o Iterable agrupa o link acima com o domínio de clique definido nas etapas anteriores. Qualquer clique no domínio de clique redireciona para o link de atribuição do OneLink. Se o aplicativo estiver instalado no dispositivo do usuário, há um deep link entre o domínio do clique e o aplicativo.

> 📘 **Note**
>
> **Exemplo**
>
> Os parâmetros de URL não são codificados em URL neste exemplo, apenas por uma questão de legibilidade:
>
> ```http
> https://greatapp.onelink.me/abcd?pid=Email&c=Spring_Newsletter&is_retargeting=true&
> af_dp=testapp://path/to/content&af_web_dp=https://www.example.com/path/to/content&
> af_ios_url=https://www.example.com/path/to/content&af_android_url=https://www.example.com/path/to/content
> ```

### Testando seus links

Depois de seguir todas as etapas necessárias mencionadas acima, criar o URL OneLink apropriado e colocá-lo em um e-mail, envie um e-mail de teste para si mesmo.

O que você deve esperar?

Se você tiver o aplicativo instalado, ele deverá ser chamado. Se as APIs de deep linking relevantes do SDK da AppsFlyer forem implementadas, deve haver um deep link para o conteúdo relevante.  
Além disso, um clique deve aparecer tanto no painel da AppsFlyer, atribuído à fonte de mídia e campanha fornecidas, quanto nos dados do Iterable.

<div data-zendesk-anchors="introduction=introdu%C3%A7%C3%A3o h_01HV6PJQRMT8037JMVMMXDPWGN=introdu%C3%A7%C3%A3o prerequisites=pr%C3%A9-requisitos h_01HV6PJQRM5N1K6CY0NSSFXT3X=pr%C3%A9-requisitos setting-up-iterable=configurando-o-iterable h_01HV6PJQRMX18FRB3NMZH6NCH0=configurando-o-iterable step-1-setting-up-link-branding-in-iterable=etapa-1-configurando-a-marca-de-link-no-iterable h_01HV6PJQRMMYV3A5ZSEGTT7993=etapa-1-configurando-a-marca-de-link-no-iterable step-2-uploading-your-ssl-certificate-to-iterable=etapa-2-fazendo-upload-do-seu-certificado-ssl-para-iterable h_01HV6PJQRMYDDWK9AKGN258TTM=etapa-2-fazendo-upload-do-seu-certificado-ssl-para-iterable step-2-give-iterable-an-aasa-ios-and-an-asset-links-file-android=etapa-2-d%C3%AA-ao-iterable-um-arquivo-aasa-ios-e-um-arquivo-asset-links-android h_01HV6PJQRMFJ23627KS83D4C6A=etapa-2-d%C3%AA-ao-iterable-um-arquivo-aasa-ios-e-um-arquivo-asset-links-android h_01HV6PJQRMNSYK8N7QEE00KSPE=aasa-for-ios h_01HV6PJQRMSMZCVJ5XRXZ3SWEH=asset-links-for-android setting-up-your-app=configurando-seu-aplicativo h_01HV6PJQRMJHDF94JSAT8N8SP9=configurando-seu-aplicativo h_01HV6PJQRM5S772CTH219MGY44=step-1-for-android-setting-up-your-app-to-support-app-links step-1-adding-the-click-domain-to-the-activity-in-the-android-manifest=etapa-1-adicionando-o-dom%C3%ADnio-de-clique-%C3%A0-atividade-no-manifesto-do-android h_01HV6PJQRM2V31JAJ52Q3FHQWH=etapa-1-adicionando-o-dom%C3%ADnio-de-clique-%C3%A0-atividade-no-manifesto-do-android step-2%20setting-up-the-app-to-resolve-click-domains=etapa-2configurando-o-aplicativo-para-resolver-dom%C3%ADnios-de-cliques h_01HV6PJQRMCRFM90QSP5SS72SE=etapa-2configurando-o-aplicativo-para-resolver-dom%C3%ADnios-de-cliques h_01HV6PJQRMVJB6J6GV41DCYAVQ=step-1-for-ios-setting-up-your-app-to-support-universal-links step-1-associating-click-domains-in-xcode=etapa-1-associando-dom%C3%ADnios-de-clique-no-xcode h_01HV6PJQRNRW8Y97JWHP0MSXZF=etapa-1-associando-dom%C3%ADnios-de-clique-no-xcode h_01HV6PJQRNHFH8XGMCEWVGSPA5=step-2-for-android-resolve-deep-links h_01HV6PJQRN4NYPWS2XQQSJAM5R=step-2-for-ios-resolve-deep-links sending-your-first-email=enviando-seu-primeiro-e-mail h_01HV6PJQRN2H29D8HKXHBYE1NB=enviando-seu-primeiro-e-mail testing-your-links=testando-seus-links h_01HV6PJQRNET2J17ZGGZE0K0Q6=testando-seus-links" />
