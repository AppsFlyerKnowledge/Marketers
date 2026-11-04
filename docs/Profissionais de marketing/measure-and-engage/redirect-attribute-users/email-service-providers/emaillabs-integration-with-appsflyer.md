---
title: Integração do EmailLabs com AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2022-01-31T14:00:18Z'
  edited_at: '2026-08-19T00:33:52Z'
  id: 4419148952721
  locale: pt
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/pt/articles/4419148952721
---
> **At a glance:** **Visão geral:** o EmailLabs, uma plataforma de entrega e plataforma de analytics de e-mail, incorpora o OneLink da AppsFlyer em e-mails. Quando os destinatários de e-mails clicam no link, eles são direcionados por deep link para o seu Aplicativo.

![emaillabs-af-logo.png](https://files.readme.io/467ee1fbcea8a36dff40172b1dbc97780a7e6cafd958ecb5b520a612c3308231-49839289267857.png)

<div id="introduction" />

## Introdução

ESPs (Email Service Providers ou provedores de serviços de e-mail) podem ser excelentes fontes de tráfego segmentado de usuários.

Um dos desafios ao usar ESPs é registrar cliques e, ao mesmo tempo, preservar a funcionalidade de Deep linking. Os ESPs encapsulam a URL de Deep linking com seu próprio domínio de registro de cliques. Essa ação muitas vezes interrompe os Links Universais do iOS.

No entanto, com ESPs que oferecem suporte a Links Universais além do seu domínio de registro de cliques, ainda é possível realizar o Deep linking e o registro de cliques com sucesso.

<div id="sdk-version-prerequisites" />

## Pré-requisitos de versão do SDK

<Tabs>
<Tab title="Exemplo">

* AppsFlyer iOS SDK versão 6.0.4

</Tab>

<Tab title="Android iOS">

* AppsFlyer Android SDK versão 6.0.0

</Tab>
</Tabs>

<div id="step-1-integration-setup-in-emaillabs" />

## Etapa 1: Configuração da integração no EmailLabs

**Para configurar a integração no EmailLabs:**

1. Configure seu domínio de acordo com <Anchor target="_blank" href="https://docs.emaillabs.io/get_started/getting-started/">este artigo</Anchor>
2. Configure seu domínio de registro de cliques de acordo com <Anchor target="_blank" href="http://docs.emaillabs.io/user-panel/smtp-applications/whitelabel-2/">este artigo</Anchor> e a captura de tela abaixo.  
   ![whitelabel-section-2.png](https://files.readme.io/a5b992868a0abd94b2f24097ead760a98e6529e4f83ecfaf713d681800de4631-49839273475217.png)
3. Ative o rastreamento de links de acordo com <Anchor target="_blank" href="http://docs.emaillabs.io/user-panel/smtp-applications/link-tracking/">este artigo</Anchor> e a captura de tela abaixo.  
   ![link-tracking-section-3.png](https://files.readme.io/3c1d0f13d3fcc2b49754cf4beb653592b9fffc27ad27775cf56986f78f9ea53b-49839289275153.png)
4. Entre em contato com o suporte do EmailLabs em [bok@emaillabs.pl](mailto:bok@emaillabs.pl) e solicite a ativação do SSL.
5. No EmailLabs, acesse **Panel** > **SMTP** **Accounts** > **Settings** > **Deep** **Links** e marque a caixa "Activated". Para aplicativos iOS, insira o <Anchor target="_blank" href="https://developer.apple.com/library/archive/documentation/General/Conceptual/DevPedia-CocoaCore/AppID.html">ID do aplicativo da Apple</Anchor> no respectivo campo.  
   ![deeplinking-section-5.png](https://files.readme.io/15a5b45a58c1a130de6bfe2c3e9e3b379537b4fc549c1c3fcce41ef54b8653e9-49839289277073.png)

<div id="step-2-configuring-your-appsflyer-sdk" />

### Etapa 2: Configure seu SDK AppsFlyer

> 📘 **Note**
>
> **Importante!**
>
> Caso ainda não tenha feito isso, certifique-se de configurar seu aplicativo para que ele seja compatível com <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">deep linking com o OneLink</Anchor>.

Depois de configurar seu domínio de registro de cliques para oferecer suporte a Links Universais conforme descrito anteriormente, você precisa configurar seu Aplicativo para fazer deep link e resolver esse link universal.

1. Associe o domínio de registro de cliques no Xcode:  
   ![configure-xcode-deeplinking-domain.png](https://files.readme.io/90d0dcc0eba2d7d081ab7d5d4ea697e9257b9107af463fa8c973169f8a2651db-49839256220433.png)
2. Forneça o domínio de gravação de cliques para a API do SDK `setResolveDeepLinkURLs`. Esta API precisa ser chamada antes da inicialização do SDK. Para obter mais informações, consulte a documentação do SDK <Anchor target="_blank" href="/marketers/pt/docs/sdk-integration-overview">aqui</Anchor>.  

   ```objectivec
   [[AppsFlyerLib shared] resolveDeepLinkURLs = @[@"example.com",@"click.example.com"];
   ```
3. Quando o aplicativo é invocado devido a um clique no Universal Link, o AppsFlyer SDK resolve o deep link e extrai o OneLink subjacente. Todos os parâmetros de deep link são então propagados para a API onAppOpenAttribution para execução da lógica de deep link.

<div id="step-3-send-emails-with-onelink-through-emaillabs" />

## Etapa 3: Envie e-mails com OneLink através do EmailLabs

1. Crie uma URL do OneLink na página de gerenciamento de links (ou manualmente). Você deve codificar em URL os valores dos parâmetros.
2. [Melhores práticas] Use os seguintes parâmetros:
   * *pid* (canal de mídia): Use um canal de mídia que indique esse uso, como EmailLabs.
   * *c* (campanha): Nome da campanha
   * *af\_dp*: O esquema de URI de deep link para o qual você deseja direcionar seus usuários.
   * *af\_web\_dp:* Para onde redirecionar os usuários que clicam no link no desktop.
   * *af\_ios\_url*: Para onde redirecionar usuários que não têm o aplicativo e que clicam no link em um dispositivo iOS.
   * *af\_android\_url:* Para onde redirecionar usuários que não têm o aplicativo e que clicam no link em um dispositivo Android.
3. Insira a URL do OneLink no e-mail.  
   Exemplo:

   ```html
   <a href="links.example.com" data-msys-sublink="appsflyer">Link para seu Aplicativo!</a>
   ```
4. Se o e-mail fizer parte de uma campanha de retargeting, adicione o parâmetro is\_retargeting=true.  
   Isso indica que o link de atribuição é de uma campanha de retargeting. <Anchor target="_blank" href="/marketers/pt/docs/retargeting-attribution-guide">Saiba mais sobre retargeting</Anchor>.
5. O EmailLabs encapsula o link com o domínio de clique definido para que um clique no domínio de clique redirecione para o link de atribuição do OneLink.

> 📘 **Note**
>
> **Exemplo**
>
> Os parâmetros de URL no exemplo a seguir não estão codificados para facilitar a leitura.
>
> ```http
> https://example.onelink.me/abcd?pid=emaillabs&c=Spring_Newsletter&is_retargeting=true&
> af_dp=testapp://path/to/content&af_web_dp=https://www.example.com/path/to/content&
> af_ios_url=https://www.example.com/path/to/content&af_android_url=https://www.example.com/path/to/content
> ```

<div id="step-4-test-your-links" />

## Etapa 4: Teste seus links

**Para testar a integração:**

1. Configure o EmailLabs.
2. Crie uma URL do OneLink.
3. Insira a URL em um e-mail.
4. Envie um e-mail de teste para você mesmo.

**Resultado esperado:**

* Se você tiver o aplicativo instalado, ele deverá ser aberto e você será direcionado por deep link para a página definida no aplicativo.
* Um clique se reflete em:
  * O dashboard da AppsFlyer, atribuído ao canal de mídia e à campanha.
  * Dados da EmailLabs.

<div data-zendesk-anchors="introduction=introdu%C3%A7%C3%A3o sdk-version-prerequisites=pr%C3%A9-requisitos-de-vers%C3%A3o-do-sdk step-1-integration-setup-in-emaillabs=etapa-1-configura%C3%A7%C3%A3o-da-integra%C3%A7%C3%A3o-no-emaillabs step-2-configuring-your-appsflyer-sdk=etapa-2-configure-seu-sdk-appsflyer step-3-send-emails-with-onelink-through-emaillabs=etapa-3-envie-e-mails-com-onelink-atrav%C3%A9s-do-emaillabs step-4-test-your-links=etapa-4-teste-seus-links" />
