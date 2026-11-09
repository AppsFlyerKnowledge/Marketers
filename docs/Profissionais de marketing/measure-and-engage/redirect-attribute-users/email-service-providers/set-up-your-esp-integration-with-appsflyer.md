---
title: '[Beta fechado - acesso especial] Configure sua integração ESP com a AppsFlyer'
metadata:
  keywords:
    - Premium
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2024-07-24T14:10:54Z'
  edited_at: '2026-08-19T00:34:05Z'
  id: 26967438815377
  locale: pt
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/pt/articles/26967438815377
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Resumo:** Configure uma integração ESP com a AppsFlyer para ativar fluxos de deep linking seguros e sem interrupções em suas campanhas de e-mail, melhorando o engajamento do usuário e as taxas de conversão.

## <Image alt="ESP final main KB image.png" src="https://files.readme.io/f14a193bb8d303adb93c01b33dcafba9053359fd92a187378cd324544a94dc88-27434531852049.png" width="613px" />

<div id="about-the-appsflyer-esp-integration" />

## Sobre a integração de ESP com a AppsFlyer

Profissionais de marketing costumam usar provedores de serviços de e-mail (ESPs) para enviar campanhas de e-mail em grande escala. Embora esse devesse ser um processo simples, que oferece jornadas previsíveis, muitas vezes não é o caso. Os problemas surgem como resultado da forma como o ESP lida com seus analytics, adotando um processo que costuma quebrar deep links e afetar negativamente a experiência do usuário mobile. Como resultado, os usuários são levados para sites mobile em vez de acessar o aplicativo, reduzindo a probabilidade de conversão.

Alguns ESPs são compatíveis com a nossa solução de integração, que permite que a AppsFlyer atue como intermediária entre o servidor ESP e seu nome de domínio. Seu papel como proxy permite o fornecimento de arquivos de associação (AASA / asset links), o que facilita o deep linking. Além disso, a solução da AppsFlyer envia dados de mensuração de volta ao ESP, permitindo que você acompanhe seus analytics de e-mail de forma eficaz.

Ao configurar a integração ESP com a AppsFlyer, você oferece experiências de deep linking rápidas e seguras em suas campanhas de e-mail, impulsionando o engajamento de usuários mobile e suas taxas de conversão.

A solução de integração ESP da AppsFlyer é um recurso premium. Se quiser saber mais sobre isso ou começar, entre em contato conosco pelo [hello@appsflyer.com](mailto:hello@appsflyer.com).

<div id="set-up-the-integration" />

## Configurar a integração

<span id="h_01J3JHFXRP57VS9D22FEWS2JZW"></span>Saiba como configurar sua integração ESP com a AppsFlyer.

<div id="prerequisites" />

### Pré-requisitos

Antes de começar a configuração, você deve ter uma conta com um ESP compatível*. Além disso, os itens abaixo são necessários:

* Um novo **domínio de rastreamento de cliques** (descrito no [passo 1](#step-1-create-a-onelink-template-for-your-email-campaign)).))
* Um **endpoint do ESP**: o endpoint é fornecido pelo ESP para que você possa encaminhar cliques para seus servidores. Exemplo de estrutura de um endpoint de ESP: esp.endpoint.com.
* **Requisitos específicos da integração ESP:**
  * **Emarsys** - peça ao seu customer success manager (CSM) da Emarsys para ativar o redirecionamento de HTTP.
  * **Blueshift** - peça ao seu customer success manager (CSM) do Blueshift para  
    mudar o código de resposta HTTP de cliques para 302.

**Para configurar a integração, siga esses passos:**

<div id="step-1-create-a-onelink-template-for-your-email-campaign" />

<Accordion title="1. Passo 1: crie um domínio de rastreamento de cliques em sua plataforma ESP (TI / administrador do sistema)">

O click-tracking domain (CTD) é o componente de domínio da URL que aparece nas mensagens de e-mail.   
Ele consiste em um subdomínio e um domínio principal, como email.suamarca.com. Diferentes ESPs podem se referir a isso como branding de link, domínio de rastreamento, domínio de clique, reescrita de link, rastreamento de cliques ou white labeling. Etapa 1:

**Você deve criar um novo CTD**, mesmo que você já esteja usando um existente. Assim, você garante que não haja impacto no tráfego das suas campanhas de e-mail atuais.

<div id="notes" />

> 📘 **Observações**
>
> * O certificado SSL será gerenciado pela AppsFlyer (no passo 3).
> * Nesse estágio, os links de e-mail provavelmente não estão seguros, o que significa que o prefixo da URL será HTTP em vez de HTTPS. Isso será resolvido no [passo 5.](#h_01JMYDQGPF3B9GNH0RY27JW3E4)).

</Accordion>

<div id="h_01JMYD02VRGT8353RDBARRPJ2M" />

<Accordion title="3. Selecione o template do OneLink que você deseja usar para campanhas de e-mail e em seguida clique em próximo .">

Crie um <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template#como-criar-templates-do-onelink">template do OneLink</Anchor> e configure Universal Links/App Links para a opção "**quando o aplicativo está instalado**". Esse template será usado para criar links do OneLink para suas campanhas de e-mail.

*Se você já tiver um template do OneLink com Universal Links/App Links já configurados, você pode usá-lo.

</Accordion>

<div id="step-3-set-your-esp-integration-in-appsflyer" />

<Accordion title="3. Passo 3: configure sua integração de ESP na AppsFlyer">

Agora é hora de configurar sua integração de ESP na AppsFlyer. Atenção: essa etapa e a seguinte ([passo 4: configure seu aplicativo](#step-2-configure-your-app-developer-task)") podem ser feitas ao mesmo tempo. Configure seu aplicativo") pode ser configurado ao mesmo tempo.

**Para configurar sua integração de ESP na AppsFlyer:**

1. Na **AppsFlyer**, no menu lateral, selecione **engajamento** > **integração ESP**.

<Image align="center" alt="From Engage click ESP integration.png" src="https://files.readme.io/7b731446ce6158d5033020b63be5f386105e7899a8c1b291aa3cb13662a59ee5-27063684942481.png" width="196px" />

2. Selecione seu ESP.

<Image align="center" alt="select ESP.png" src="https://files.readme.io/526fed3aaf1e6fdbf2404243619159984e298752fdf5913fd3a65cc5a2ed9e1d-27086632495761.png" width="482px" />

3. **Encaminhar o tráfego do link para a AppsFlyer:**

<Image align="center" alt="select OneLink template.png" src="https://files.readme.io/4f96b999740be8596a424ce9108a8f702bda2a7ed025ec1869c553393432d87d-27086632499729.png" />

4. Certifique-se de que você possui uma conta ativa com o ESP selecionado.

Dados necessários do seu ESP:

* Domínio de rastreamento de cliques, criado no passo 1.
* Endpoint do ESP

Clique em **próximo**.

5. Insira seu domínio de rastreamento de cliques e endpoint do ESP, em seguida clique em **validar conexão**. Essa ação avalia se o domínio de rastreamento de cliques aponta para o endpoint que você inseriu.

<Image align="center" alt="enter your ctd and esp endpoint.png" src="https://files.readme.io/d068b7de020bed7ba979b25e0fe866c40a118b00bbfde06a36a4c097485ac885-27086632503441.png" />

Quando terminar, clique em **próximo**.

6. Use a <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl">Unified DeepLinking API</Anchor> para obter os parâmetros e tratar os dados de deep linking.

a. a. a. **Copie e envie as instruções pré-fabricadas e personalizadas na AppsFlyer para a pessoa responsável por TI ou pelo domínio.** Ela terá que redirecionar o tráfego da sua campanha de e-mail dos servidores de ESP para os servidores da AppsFlyer, atualizando seus registros DNS CNAME com o novo domínio fornecido pela AppsFlyer.

Como resultado, toda vez que um usuário clicar em um link, o clique será redirecionado para a AppsFlyer, que por sua vez o redirecionará para o endpoint do ESP.

<Image align="center" alt="click to Af to ESP image.png" src="https://files.readme.io/8a53fa7e8e2574246ea6b1344cfec0ac2d8f319bb181f6956ecb6db5b05cd0c5-26982377140369.png" width="374px" />

b. Após copiar e enviar as instruções, clique em **concluir**.

Sua integração ESP foi criada.

**Observe que:**

* O status de integração do ESP fica pendente e só começará a funcionar depois que o registro CNAME ser mapeado.
* Pode demorar até 24 horas após o mapeamento para que uma nova integração comece a funcionar e se torne ativa.

</Accordion>

<div id="step-2-configure-your-app-developer-task" />

<Accordion title="4. Passo 4: configure seu aplicativo (desenvolvedor)">

Peça ao seu desenvolvedor para fazer as seguintes configurações em seu aplicativo:

* [Configure seu aplicativo para garantir o suporte a domínios associados](#configure-seu-aplicativo-para-garantir-o-suporte-a-domínios-associados)
* [Configure seu aplicativo para garantir o suporte a deep linking](#configure-seu-aplicativo-para-garantir-o-suporte-para-deep-linking)
* [Configure seu aplicativo para processar Weblinks e Application Links](#configure-seu-aplicativo-para-processar-weblinks-e-application-links)

<div id="configure-your-app-to-support-associated-domains" />

#### **Configure seu aplicativo para garantir o suporte a domínios associados**

A AppsFlyer hospeda arquivos de associação para o seu aplicativo, permitindo o funcionamento de <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-knowledge-base-glossary#links-universais">Universal Links (iOS)</Anchor> e/ou <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-knowledge-base-glossary#link-de-aplicativo-android-en-android-app-link">App Links (Android)</Anchor>.

**Para configurar seu aplicativo para acessar os arquivos:**

**Para iOS**  
**Pré-requisito:** SDK <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-ios-sdk-release-notes">v6.12.3</Anchor>  
Configure seu aplicativo para permitir o Universal Linking a partir da mensagem de e-mail.  
Saiba mais sobre como configurar <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#procedures-for-ios-universal-links">Universal links</Anchor>.  
**Atenção:** O domínio de clique deve estar adicionado aos domínios associados já definidos.

**Para Android**  
**Pré-requisito:** SDK <Anchor target="_blank" href="https://mvnrepository.com/artifact/com.appsflyer/af-android-sdk">v6.12.5</Anchor>  
Configure seu aplicativo para permitir o Android App Linking a partir da mensagem de e-mail. Saiba mais sobre como configurar <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-knowledge-base-glossary#links-universais">App Links</Anchor> do Android.  
**Atenção:** O domínio de clique deve ser adicionado aos domínios atuais já definidos no Android Manifest.


<div id="configure-your-app-to-support-deep-linking" />

#### **Configure seu aplicativo para garantir o suporte para deep linking**

Quando um usuário clicar em um App Link ou Universal Link, o app deve abrir.

**Para permitir que o aplicativo extraia o OneLink por trás do click recording domain e garantir o funcionamento do deep linking:**

1. Forneça o click recording domain para a SDK API resolveDeepLinkURLs. Essa API deve ser chamada antes da inicialização do SDK.

* Para iOS, siga essas <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_esp_2_setup">instruções</Anchor>.
* Para Android, siga essas <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_esp_2_setup#flow-description">instruções</Anchor>.

2. Use a <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl">Unified DeepLinking API</Anchor> para obter os parâmetros do deep link e processar os dados de deep linking.


<div id="configure-your-app-to-handle-weblinks-and-application-links" />

#### **Configure seu aplicativo para processar Weblinks e Application Links**

O código fornecido regula a funcionalidade de links encurtados de uma campanha de e-mail. Mais especificamente, ele regula dois tipos: Weblinks que abrem o site + links que abrem o aplicativo através de um Universal Link ou App Link.  
Para mais informações para desenvolvedores, consulte os guias abaixo:

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_esp_2_setup">iOS Deep Linking ESP 2.0</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_esp_2_setup">Android Deep Linking ESP 2.0</Anchor>

</Accordion>

<div id="h_01JMYDQGPF3B9GNH0RY27JW3E4" />

<Accordion title="5. Passo 5: Certifique-se de que o rastreamento de cliques SSL esteja ativado na sua plataforma de ESP.">

Faça um teste de e-mail para verificar o status do link.   
Se os links CTD forem identificados como HTTP, entre em contato com a equipe do ESP para ativar o rastreamento de cliques SSL.   
Isso garantirá que todos os links HTTP sejam automaticamente convertidos para HTTPS.

Ao entrar em contato com seu ESP, você pode usar a mensagem de exemplo abaixo:

Oi [nome],  
Vocês poderia habilitar o rastreamento de cliques SSL para CTD XXX? Atualmente, ele está configurado para HTTP em vez de HTTPS.   
Agradeço a sua ajuda com essa atualização.

</Accordion>

<div id="step-4-customize-the-onelink-link-for-your-email-campaign" />

<Accordion title="Passo 6: Passo 6: Passo 6: personalize o link do OneLink para sua campanha de e-mail na AppsFlyer">

**Para criar e personalizar o link do OneLink para a sua campanha:**

1. Na AppsFlyer, crie um link "email-to-app" na página de gerenciamento do OneLink (ou crie um link manualmente) dentro do template criado anteriormente. Você usará esse link em sua campanha de e-mail para atribuir e redirecionar os usuários de acordo com suas especificações. Aprenda a criar um <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#crie-um-link-do-onelink">link do OneLink</Anchor>.

<Image align="center" alt="email-to-app.png" src="https://files.readme.io/4e30986e039ed4cc13b9963ef3d1bb7b933061176bed812dced45a7240023d54-27082280943761.png" width="652px" />

**Recomendado:** use o mesmo nome tanto na campanha de e-mail do ESP quanto nos links do OneLink usados nessa campanha.

</Accordion>

<div id="step-5-test-the-link" />

<Accordion title="Passo 7: Passo 7: Passo 7: teste a integração na sua plataforma ESP">

**Para testar a integração com o link do OneLink criado:**

Insira a URL do OneLink em um e-mail de teste e o envie para si mesmo usando o editor de e-mail do ESP.

* Do seu dispositivo mobile, abra o e-mail e clique no link. Se você tiver o aplicativo instalado, ele será aberto e você será direcionado para o conteúdo relevante. Além disso, um clique "mobile" deve ser exibido no dashboard da AppsFlyer, atribuído à fonte de mídia e campanha fornecidas, assim como no dashboard de analytics do seu ESP.
* Clique em um link da web e verifique se ele redireciona para o destino correto.

Se o teste for bem-sucedido, tudo está pronto.

</Accordion>

<div id="step-6-use-the-link-in-your-email-campaigns-then-measure-the-results-use-the-link-confidently-in-your-email-campaigns" />

<Accordion title="Passo 8: Passo 8: Passo 8: use o link em suas campanhas de e-mail">

Bom trabalho! Agora você está pronto para usar links em suas campanhas de e-mail. Depois, você pode visualizar os resultados da campanha em seus dashboards do ESP e da AppsFlyer.

</Accordion>

*ESPs compatíveis com essa integração incluem: Blueshift, Braze, CleverTap, Customer.io, Emarsys, Expert Sender, Klaviyo, MailExpress, MailGun, Moengage, RDStation, Reteno, Sailthru, Sendgrid, Sparkpost e mais. Veja a <Anchor target="_blank" href="/marketers/pt/docs/email-service-provider-esp-integration-guide">lista completa aqui</Anchor>.

<div id="faq" />

## Perguntas frequentes

<div id="do-i-need-to-create-an-ssl-certificate-at-any-point" />

<Accordion title="Preciso criar um certificado SSL em algum momento?">

Não, a AppsFlyer cria o certificado SSL para você.

</Accordion>

<div id="if-i-have-the-appsflyer-esp-integration-and-sdk-implemented-for-basic-onelink-deep-linking-do-i-need-to-add-both-the-onelink-domain-and-the-esp-click-tracking-domain-to-ios-associated-domains" />

<Accordion title="Se eu tiver a integração ESP da AppsFlyer e o SDK implementados para deep linking básico do OneLink, preciso adicionar tanto o domínio do OneLink quanto o domínio de rastreamento de clique do ESP aos Associated Domains do iOS?">

* sim, sim, Ao configurar links universais/App Links do ESP e do OneLink para deep linking, você deve registrar os dois domínios no entitlement Associated Domains do seu aplicativo:
  * **O domínio do OneLink** – necessário para deep linking padrão com a AppsFlyer.
  * **O domínio de rastreamento de clique do ESP** – necessário para garantir que os links de e-mail com tecnologia do seu ESP (por exemplo, Braze, Emarsys) sejam reconhecidos e recebam deep linking corretamente.
* **Quem hospeda o arquivo AASA para o domínio de rastreamento de clique?**  
  Nessa configuração, a AppsFlyer hospeda o arquivo AASA para o domínio de rastreamento de clique usado nos links de e-mail do ESP. Você só precisa adicionar esse domínio aos associated domains do seu aplicativo, e não precisa gerenciar a hospedagem do AASA por conta própria.

</Accordion>

<div data-zendesk-anchors="overview=sobre-a-integra%C3%A7%C3%A3o-de-esp-com-a-appsflyer h_01J6RXTXCS7WC0P5X4J96T8JAP=sobre-a-integra%C3%A7%C3%A3o-de-esp-com-a-appsflyer h_01J3JHJCCASM6E5QYJB5VHQ8HK=sobre-a-integra%C3%A7%C3%A3o-de-esp-com-a-appsflyer set-up-your-esp-integration-with-appsflyer=configurar-a-integra%C3%A7%C3%A3o h_01J3JHFRGA6BTMWSK7EEEVGS6T=configurar-a-integra%C3%A7%C3%A3o prerequisites=pr%C3%A9-requisitos h_01J3JJ74GYF5AJT9R2P2CXDXE1=pr%C3%A9-requisitos h_01J3W0Z161XE7BKMMR62SEEZN7=step-1-create-a-onelink-template-for-your-email-campaign h_01JMYJG3CTGE9Y3SBFAECV326G=observa%C3%A7%C3%B5es h_01J3W0Z161T0D075HPE3Y8H3J4=step-3-set-your-esp-integration-in-appsflyer h_01J3W0Z1613XPYM75GH65R793W=step-2-configure-your-app-developer-task configure-your-app-to-support-associated-domains=configure-seu-aplicativo-para-garantir-o-suporte-a-dom%C3%ADnios-associados h_01J3W8XR5QS227XNCD453RWYZ9=configure-seu-aplicativo-para-garantir-o-suporte-a-dom%C3%ADnios-associados configure-your-app-to-support-deep-linking=configure-seu-aplicativo-para-garantir-o-suporte-para-deep-linking h_01J3WS4QWMRT8KSW6J3QHXM9TQ=configure-seu-aplicativo-para-garantir-o-suporte-para-deep-linking h_01J3W8Y7FMSWPG7MFF6FMSXFM3=configure-seu-aplicativo-para-garantir-o-suporte-para-deep-linking ::250c928e=configure-seu-aplicativo-para-processar-weblinks-e-application-links configure-your-app-to-handle-weblinks-and-application-links=configure-seu-aplicativo-para-processar-weblinks-e-application-links h_01J3WS4QWMSKZ33APWFR8CG5TZ=configure-seu-aplicativo-para-processar-weblinks-e-application-links h_01J3W8ZMHSXQGJPQEVR62Q28X9=configure-seu-aplicativo-para-processar-weblinks-e-application-links h_01J3W0Z1616GFFYCS7WPTNCCHT=step-4-customize-the-onelink-link-for-your-email-campaign h_01J3W0Z161M9NDXAN0KZFA9J4G=step-5-test-the-link h_01J3W0Z161RAYTKH3V9VBAADBM=step-6-use-the-link-in-your-email-campaigns-then-measure-the-results-use-the-link-confidently-in-your-email-campaigns faq=perguntas-frequentes h_01K3R6V0K31816PVY95X5WZC4C=perguntas-frequentes h_01K3R6THWT2MCCJHPSXPBAVT8Y=do-i-need-to-create-an-ssl-certificate-at-any-point h_01K3R6THWTG8G8PWPZ2ZRA1CSA=if-i-have-the-appsflyer-esp-integration-and-sdk-implemented-for-basic-onelink-deep-linking-do-i-need-to-add-both-the-onelink-domain-and-the-esp-click-tracking-domain-to-ios-associated-domains" />
