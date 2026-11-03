---
title: Integração do Oracle Responsys com a AppsFlyer
metadata:
  keywords:
    - Oracle Responsys
    - Advertisers
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
  created_at: '2019-11-20T09:26:13Z'
  edited_at: '2026-08-19T00:34:00Z'
  id: 360003798297
  locale: pt
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/pt/articles/360003798297
---
> **At a glance:** **Visão geral:** Oracle Responsys, uma plataforma de entrega e análise de e-mail, incorpora o OneLink da AppsFlyer no que diz respeito a e-mails. Quando destinatários de um e-mail clicam no link, há um deep link para o seu aplicativo.

![oracle-responsys-af-logo.png](https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png)

ESPs (Email Service Providers ou provedores de serviços de e-mail) podem ser excelentes fontes de tráfego segmentado de usuários.

Um dos desafios dos ESPs é realizar atribuição correta e deep linking. Os ESPs agrupam o URL do deep link com seu próprio domínio de gravação de cliques do ESP. Esse procedimento geralmente interrompe a funcionalidade dos links universais do iOS e dos links de aplicativos do Android.

No entanto, deep linking e gravação de cliques ainda são possíveis com ESPs que suportam links universais e links de aplicativos além de seu domínio de gravação de cliques. Além disso, você pode configurar seu próprio domínio de cliques para atuar como domínio de gravação de cliques.

## Pré-requisitos

* Configure seu aplicativo para que haja compatibilidade do <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">deep link com o OneLink</Anchor>.
* Verifique sua versão do SDK (Android e iOS)

<Tabs>
<Tab title="https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png">

* SDK da AppsFlyer para iOS versão 4.9.0 (ou superior)

</Tab>

<Tab title="Android iOS">

* SDK da AppsFlyer para Android versão 4.9.0 (ou superior)

</Tab>
</Tabs>

## Configurando o domínio de clique do Oracle Responsys

Siga esta seção para configurar seu domínio de clique (domínio de gravação de clique) no Oracle Responsys.

### Etapa 1: configure um domínio de clique no Oracle Responsys

Para configurar um domínio de clique, siga o guia oficial do Oracle Responsys sobre como <Anchor target="_blank" href="https://docs.oracle.com/cloud/latest/marketingcs_gs/OMCEA/LinkTable_Main.htm?cshid=LinkTable_Main">criar domínios de clique</Anchor>. O Oracle Responsys usa tabelas de links para ajudar a registrar cliques para uma campanha específica

**Observe** que, nas tabelas de links, você pode definir **o URL do link do IOS** como igual ao URL do link:

![Oracle-responsys-link-tracking-table.png](https://files.readme.io/c151c58af73cf460ba4275a9159e45c15807f311fa8d8b4b1531b0cdf7e3bc4e-49839256667665.png)

Depois de definir domínios de clique em tabelas de links, o Responsys usa esses domínios para agrupar OneLinks que você inclui em campanhas de e-mail. Dessa forma, o Responsys pode registrar cliques em seu sistema enquanto preserva a funcionalidade do OneLink e do deep link.

### Etapa 2: forneça ao Responsys um AASA (iOS) e um arquivo Asset Links (Android)

<div id="aasa-for-ios" />

<Accordion title="AASA para iOS">

Para que o Responsys seja compatível com links universais do iOS, ele precisa de um arquivo AASA. Veja as instruções a seguir.

Ao configurar o OneLink com Universal Links, você já tem um AASA associado ao OneLink. Para obter o AASA:

1. Vá para a configuração do OneLink e encontre um OneLink configurado com Universal Links.
2. Adicione **/.well-known/apple-app-site-association** ao final do URL do OneLink.
3. Cole o OneLink na barra de endereço do navegador e pressione Enter. Por exemplo: **`<OneLinkSubdomain>`.onelink.me/.well-known/apple-app-site-association**. Ao fazer isso, o arquivo AASA é baixado para o seu computador. Você pode abri-lo usando qualquer editor de texto simples.
4. Envie este arquivo AASA para o Responsys. Para obter mais informações e saber mais sobre o conteúdo deste arquivo, consulte a página 11 do <Anchor target="_blank" href="https://docs.oracle.com/cloud/latest/marketingcs_gs/OMCFB/pdf/ios-universal-links-dev-guide.pdf">guia da Oracle</Anchor>.

</Accordion>

<div id="asset-links-for-android" />

<Accordion title="Asset Links para Android">

Ao configurar o OneLink com App Links, você já tem um arquivo Asset Links associado ao OneLink. Para obter o arquivo Asset Links. Para obter o arquivo Asset Links:

1. Vá para a configuração do OneLink e encontre um OneLink configurado com App Links.
2. Adicione **/.well-known/assetlinks.json** ao final do URL do OneLink.
3. Cole o OneLink na barra de endereço do navegador e pressione Enter. Por exemplo:**`<OneLinkSubdomain>`.onelink.me/.well-known/assetlinks.json**. Ao fazer isso, o arquivo Asset Links é baixado para o seu computador. Você pode abri-lo usando qualquer editor de texto simples.
4. Envie este arquivo Asset Links para o Responsys. Para obter mais informações e saber mais sobre o conteúdo deste arquivo, consulte <Anchor target="_blank" href="https://docs.oracle.com/cloud/latest/marketingcs_gs/OMCFB/android/app-links/">este guia</Anchor>.

</Accordion>

## Configurando seu aplicativo

<div id="step-1-for-android-setting-up-your-app-to-support-app-links" />

<Accordion title="Etapa 1 para Android: configurar seu aplicativo para que ele seja compatível com App Links">

#### Adicionando o domínio de clique à atividade no manifesto do Android

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

#### Configurando o aplicativo para resolver domínios de cliques

O SDK precisa resolver o OneLink por trás do domínio de clique para obter os detalhes da campanha. Os detalhes são retornados no método `onAppOpenAttribution`.

Para resolver domínios de clique:

1. Certifique-se de que sua versão do SDK seja pelo menos 4.9.0.
2. Liste os domínios de clique na API do SDK `setResolveDeepLinkURLs`. Esta API precisa ser chamada antes da inicialização do SDK. Para obter mais informações, consulte a documentação do SDK <Anchor target="_blank" href="/marketers/pt/docs/additional-sdk-integration-guide#resolve-wrapped-deep-link-urls">aqui</Anchor>.  

   ```java
   AppsFlyerLib.getInstance().setResolveDeepLinkURLs("click.example.com");
   ```

   * **Importante!** Se você estiver usando o Movable Ink (MI) em conjunto com a Oracle, será necessário obter o CNAME do MI e os domínios internos do seu gerente de conta do MI e adicioná-los a `setResolveDeepLinkURLs`, além do link de clique para a Oracle. Por exemplo:

     ```java
     AppsFlyerLib.getInstance().setResolveDeepLinkURLs("oracle-click.example.com", "mi.example.com", "example.micpn.com");
     ```

</Accordion>

<div id="step-1-for-ios-setting-up-your-app-to-support-universal-links" />

<Accordion title="Etapa 1 para iOS: configurar seu aplicativo para que ele seja compatível com links universais">

Esta seção é sobre como configurar seu aplicativo para que ele seja compatível com links universais.

#### Associando domínios de clique no Xcode

1. No Xcode, clique no seu projeto.
2. Clique em ***Capacidades***. ![configure-xcode-deeplinking-domain.png](https://files.readme.io/90d0dcc0eba2d7d081ab7d5d4ea697e9257b9107af463fa8c973169f8a2651db-49839256220433.png)
3. Ative ***Domínios Associados***.
4. Clique no sinal + e adicione seu domínio de clique. Por exemplo, applinks:click.example.com.

</Accordion>

### Etapa 2: configurar o aplicativo para resolver domínios de cliques

O SDK precisa resolver o OneLink por trás do domínio de clique para obter os detalhes da campanha. Os detalhes são retornados no método `onAppOpenAttribution`.

Para resolver domínios de clique:

1. Certifique-se de que sua versão do SDK seja pelo menos 4.9.0.
2. Liste os domínios de clique na propriedade do SDK `resolveDeepLinkURLs`. Esta propriedade precisa ser definida antes da inicialização do SDK. Para obter mais informações, consulte a documentação do SDK aqui.  

   <Tabs>
   <Tab title="Objetivo-C">

   ```objectivec
   [AppsFlyerTracker sharedTracker].resolveDeepLinkURLs = @[@"example.com",@"click.example.com"];
   ```

   </Tab>

   <Tab title="Swift">

   ```swift
   AppsFlyerTracker.shared().resolveDeepLinkURLs = ["example.com", "click.example.com"]
   ```

   </Tab>
   </Tabs>

   * **Importante!** Se você estiver usando o Movable Ink (MI) em conjunto com a Oracle, será necessário obter o CNAME do MI e os domínios internos do seu gerente de conta do MI e adicioná-los a `setResolveDeepLinkURLs`, além do link de clique para Oracle. Exemplos de domínio:
     * Domínio Oracle: oracle-click.exemplo.com
     * Domínio MI CNAME: mi.exemplo.com
     * Domínio interno MI: exemplo.micpn.com
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

## Enviando seu primeiro e-mail

1. Crie uma URL do OneLink na página Gerenciamento de links (ou manualmente).
2. Ao criar o URL do OneLink, certifique-se de codificar o URL de todos os valores dos parâmetros.
3. Os seguintes parâmetros são altamente recomendados para uso:
   * pid (fonte de mídia) - Use uma fonte de mídia que signifique esse uso, como E-mail.
   * c (campanha) – O nome da campanha que você deseja medir.
   * af\_dp - O esquema de URI de deep link ao qual você deseja vincular seus usuários.
   * af\_web\_dp - Para onde redirecionar os usuários que clicam no link em um desktop.
   * af\_ios\_url - Para onde redirecionar usuários que não têm o aplicativo e que clicam no link em um dispositivo iOS.
   * af\_android\_url - Para onde redirecionar usuários que não têm o aplicativo e que clicam no link em um dispositivo Android.
4. Coloque o URL do OneLink no e-mail que você cria no Responsys. Exemplo:

   ```http
   <a href="greatapp.onelink.me/abcd/1234567">Download my great app!</a>
   ```

   Nesse estágio, a Responsys agrupa o link acima com o domínio de clique definido nas etapas anteriores. Qualquer clique no domínio de clique redireciona para o link de atribuição do OneLink. Se o aplicativo estiver instalado no dispositivo do usuário, há um deep link entre o domínio do clique e o aplicativo.

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
Além disso, um clique deve aparecer tanto no painel da AppsFlyer, atribuído à fonte de mídia e campanha fornecidas, quanto nos dados do Responsys.

<div data-zendesk-anchors="prerequisites=pr%C3%A9-requisitos h_01HDNSK7GR33AN2M4GP956S1FD=pr%C3%A9-requisitos setting-up-oracle-responsys-click-domain=configurando-o-dom%C3%ADnio-de-clique-do-oracle-responsys h_01HDNSK7GR84QSRTS86GH556WK=configurando-o-dom%C3%ADnio-de-clique-do-oracle-responsys step-1-set-up-a-click-domain-in-oracle-responsys=etapa-1-configure-um-dom%C3%ADnio-de-clique-no-oracle-responsys h_01HDNSK7GRHYJZSMYCMT9RVEBW=etapa-1-configure-um-dom%C3%ADnio-de-clique-no-oracle-responsys step-2-give-responsys-an-aasa-ios-and-an-asset-links-file-android=etapa-2-forne%C3%A7a-ao-responsys-um-aasa-ios-e-um-arquivo-asset-links-android h_01HDNSK7GRW57NNXMN1SWFTTFZ=etapa-2-forne%C3%A7a-ao-responsys-um-aasa-ios-e-um-arquivo-asset-links-android h_01HDNSK7GR77N60SFVBD57S9GQ=aasa-for-ios h_01HDNSK7GR6ADJCPG63ZVP19NJ=asset-links-for-android setting-up-your-app=configurando-seu-aplicativo h_01HDNSK7GRN751HAPPQ3HVRMDG=configurando-seu-aplicativo h_01HDNSK7GRHCK378A8XKMK7ZZF=step-1-for-android-setting-up-your-app-to-support-app-links adding-the-click-domain-to-the-activity-in-the-android-manifest=adicionando-o-dom%C3%ADnio-de-clique-%C3%A0-atividade-no-manifesto-do-android h_01HDNSK7GRQNQGWXAEGHSTHADH=adicionando-o-dom%C3%ADnio-de-clique-%C3%A0-atividade-no-manifesto-do-android setting-up-the-app-to-resolve-click-domains=configurando-o-aplicativo-para-resolver-dom%C3%ADnios-de-cliques h_01HDNSK7GRP9ND0MHC3ZHD7G8H=configurando-o-aplicativo-para-resolver-dom%C3%ADnios-de-cliques h_01HDNSK7GRJ682QYAMPB4PSGRZ=step-1-for-ios-setting-up-your-app-to-support-universal-links associating-click-domains-in-xcode=associando-dom%C3%ADnios-de-clique-no-xcode h_01HDNSK7GSRENM232MQ25EB3J3=associando-dom%C3%ADnios-de-clique-no-xcode step-2-setting-up-the-app-to-resolve-click-domains=etapa-2-configurar-o-aplicativo-para-resolver-dom%C3%ADnios-de-cliques h_01HDNSK7GSP08G2EQSNVR5G45B=etapa-2-configurar-o-aplicativo-para-resolver-dom%C3%ADnios-de-cliques sending-your-first-email=enviando-seu-primeiro-e-mail h_01HDNSK7GSA9VAMTRFCX8SZGSC=enviando-seu-primeiro-e-mail testing-your-links=testando-seus-links h_01HDNSK7GSTAJXAP6KGKE9TD8T=testando-seus-links" />
