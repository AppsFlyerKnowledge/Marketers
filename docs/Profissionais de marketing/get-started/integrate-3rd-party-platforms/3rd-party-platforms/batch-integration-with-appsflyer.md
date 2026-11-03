---
title: Integração da Batch com a AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Batch
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
  created_at: '2019-01-28T10:06:24Z'
  edited_at: '2026-08-19T00:10:46Z'
  id: 360000833437
  locale: pt
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/pt/articles/360000833437
---
> **At a glance:** **Visão geral:** A Batch, parceira integrada da AppsFlyer, é uma plataforma de app analytics, automação de marketing e CRM mobile.

A Batch permite que os anunciantes maximizem o engajamento do usuário, oferecendo ao mesmo tempo uma experiência personalizada ao usuário. A plataforma avançada de engajamento do usuário da Batch permite que você se comunique com os usuários de smartphone de forma mais personalizada, reduza o churn e aumente o ROI do seu aplicativo. A AppsFlyer e a Batch, em conjunto, podem ajudar o anunciante a personalizar ainda mais a experiência e o engajamento do usuário com base na jornada do usuário. Isso significa que o anunciante pode enviar mensagens in-app específicas e notificações push com base em dados de atribuição, como canal de mídia e campanha. Integrar a Batch e a AppsFlyer é fácil e simples.

> 🚧 **Important**
>
> **Importante!**
>
> <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#restrições-por-fonte-de-mídia">Algumas fontes de mídia</Anchor> restringem o compartilhamento de dados com terceiros. Portanto, os postbacks de eventos restritos não serão enviados para esse parceiro, independentemente da configuração de envio de postbacks.

## Integração entre Batch e AppsFlyer

### Definir o ID de usuário do cliente

Para que a Batch consiga corresponder os dados da AppsFlyer aos seus próprios dados, o anunciante deve fornecer o mesmo <Anchor target="_blank" href="/marketers/pt/docs/customer-user-id-field-cuid">Customer User ID</Anchor> a ambas. O Customer User ID é definido no SDK.

É importante inserir um Customer User ID real, e não um valor de espaço reservado. Um Customer User ID real é um ID de usuário que você usa para identificar seus clientes nos seus próprios sistemas.

<Tabs>
<Tab title="Android iOS">

#### Batch

Defina o Customer User ID no SDK da Batch.

```java
Batch. User.editor()
    .setIdentifier("user@example.com")
    .save();
```

#### A AppsFlyer

Defina o ID de usuário do cliente no SDK da AppsFlyer.

```java
AppsFlyerLib.getInstance().setCustomerUserId("user@example.com");
```

</Tab>

<Tab title="Exemplo">

<Tabs>
<Tab title="Objetivo c">

#### Batch

Defina o Customer User ID no SDK da Batch.

```objectivec
BatchUserDataEditor *editor = [BatchUser editor];
[editor setIdentifier:@"user@example.com"];
[editor save];
```

#### A AppsFlyer

Defina o Customer User ID no SDK da AppsFlyer.

```objectivec
[AppsFlyerTracker sharedTracker].customerUserID = @"user@example.com";
```

</Tab>

<Tab title="Swift">

#### Batch

Defina o Customer User ID no SDK da Batch.

```swift
let editor = BatchUser.editor()
editor.setIdentifier("user@example.com")
editor.save()
```

#### A AppsFlyer

Defina o Customer User ID no SDK da AppsFlyer.

```swift
AppsFlyerLib.getInstance().setCustomerUserId("user@example.com");
```

</Tab>
</Tabs>

</Tab>
</Tabs>

### Configurando o Batch

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração** selecione **Ativar parceiro**.
4. Na **primeira visita** aqui, você precisará ativar o botão **Ativar parceiro** para habilitar a configuração dos parâmetros da aba de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro.  **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo.

A configuração da Batch requer apenas a aba **Integração**. As outras quatro abas estão inativas, pois não são necessárias nesta integração.

<div id="integration-tab" />

<Accordion title="Aba Integração">

### Ativar parceiro

No **Primeira visita** Aqui, você precisará ativar **Ativar parceiro** para habilitar a configuração dos parâmetros de integração. O botão deve permanecer ativado enquanto você trabalhar com o Medialyzer.Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">a ativação de parceiros</Anchor>.

### Configurações gerais

Antes de configurar a integração com o Batch, obtenha sua **Batch Rest API Key** e sua **Batch API Key**. Se tiver dúvidas, [entre em contato com a Batch](mailto:hello@batch.com) para mais informações.  

Depois de obter as duas chaves, insira cada uma no campo correspondente. Em **General Settings**, insira sua **Batch Rest API Key** no campo **BATCH\_REST\_API\_KEY** e sua **Batch API Key** no campo **BATCH\_API\_KEY**.

![batch-general-settings-keys.png](https://files.readme.io/fb165253ec81c0ad4ee9569ef928dc63fb476efe6da8fc7c9120d6619b3124c1-360001692717.png)

### Postbacks padrão

Em **Default Postbacks**, na lista suspensa **Sending Option**, selecione **Events attributed to any partner or organic**.

![batch-default-postbacks.png](https://files.readme.io/e3e84f990d7f05c94fb69195a7e57caeffcd1ca35a5fb0148fc6a81ab9816673-360001778958.png)

Clique em **Salvar** no canto inferior direito da tela.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Links de atribuição não estão disponíveis para o Batch.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

Os dados de custo não são compatíveis com a integração desse parceiro.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A receita de anúncios não é compatível com a integração desse parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Permissões não estão disponíveis para o Batch.

</Accordion>

## Visualizando dados da AppsFlyer no dashboard da Batch

Assim que a AppsFlyer começar a enviar postbacks de instalação para a Batch, você poderá visualizar os dados no dashboard da Batch e começar a personalizar o engajamento do usuário de acordo com os dados de atribuição.

Você pode ver os dados na aba **Userbase** do dashboard da Batch.

![Userbase.png](https://files.readme.io/b0277dc43b81630d5b260273b208a5ab9b62e13c7caca08e8b631d73c8de3b2a-small-360001694717.png)

<div data-zendesk-anchors="integrating-batch-and-appsflyer=integra%C3%A7%C3%A3o-entre-batch-e-appsflyer h_01H9FK389GXG3CDFPNM5ASKJ3N=integra%C3%A7%C3%A3o-entre-batch-e-appsflyer setting-customer-user-id=definir-o-id-de-usu%C3%A1rio-do-cliente h_01H9FK389MPKFN8J74BX1E3MGG=definir-o-id-de-usu%C3%A1rio-do-cliente h_01H9FK389MK1HM1460VAT6X82Y=batch appsflyer=a-appsflyer h_01H9FK389MPGNEX8B3923KYDB3=a-appsflyer batch::28a946d0=batch h_01H9FK389MC4K8PNVPAGC00TBW=batch appsflyer::3f0aa95b=a-appsflyer h_01H9FK389M7V83A66M6T9EV8QT=a-appsflyer batch::24c5c955=batch h_01H9FK389MRV4ARHMHXPAXVXQ9=batch appsflyer::deb78dd1=a-appsflyer h_01H9FK389MT6PD8FW21SYHBPCV=a-appsflyer setting-up-batch-in-appsflyer-dashboard=configurando-o-batch h_01H9FK389MCSR5YDSF4RKFDSDZ=configurando-o-batch h_01H9FK389MG9459909JZBDN77E=integration-tab activate-partner=ativar-parceiro h_01H9FK389M19AVM63DEX5JTTQK=ativar-parceiro general-settings=configura%C3%A7%C3%B5es-gerais h_01H9FK389MN82EKHVGMM9Z6H58=configura%C3%A7%C3%B5es-gerais default-postbacks=postbacks-padr%C3%A3o h_01H9FK389MXA3DS403VXRRK5NX=postbacks-padr%C3%A3o h_01H9FK389MERP4XBF19T28E6DN=attribution-link-tab h_01H9FK389M3E05PVMNA83TBFJZ=cost-tab h_01H9FK389M06FEQ4RZJ04HTH33=ad-revenue-tab h_01H9FK389MB31S8BR8WX178GHX=permissions-tab viewing-appsflyer-data-in-the-batch-dashboard=visualizando-dados-da-appsflyer-no-dashboard-da-batch h_01H9FK389M8BNRFECN0WG23BCD=visualizando-dados-da-appsflyer-no-dashboard-da-batch" />
