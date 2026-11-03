---
title: Integração do Swrve com AppsFlyer
metadata:
  keywords:
    - Swrve
    - Adobe Analytics
    - 3rd Party
    - SDK
    - Integration
    - integrated partner
    - Advertisers
    - Ad Networks
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
  created_at: '2015-12-24T11:46:00Z'
  edited_at: '2026-08-19T00:11:47Z'
  id: 207040656
  locale: pt
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/pt/articles/207040656
---
> **At a glance:** **Em resumo:** o Swrve, um parceiro integrado da AppsFlyer, é um mecanismo multiplataforma de interação com clientes, que permite aos anunciantes oferecer interações segmentadas, personalizadas e otimizadas aos usuários finais:

* Otimização dinâmica e testes do conteúdo principal do aplicativo
* Campanhas in-app e de notificação push
* E-mail

Junto com a AppsFlyer, o Swrve oferece uma solução completa de ciclo de vida para maximizar o ROI dos gastos com desenvolvimento e aquisição e proporciona experiências excepcionais ao usuário ao longo de toda a jornada no app mobile. Isso inclui personalizar a experiência do usuário com base na fonte de aquisição compartilhada entre as duas plataformas, o que significa que os usuários podem receber conteúdo específico para a sua jornada desde o momento em que abrem o app pela primeira vez.

A integração funciona notificando o Swrve sobre as instalações na API dele usando a API REST. Para isso, você precisará configurar um postback de servidor na sua conta da AppsFlyer para cada um dos seus apps mobile.

> 🚧 **Important**
>
> **Importante!**
>
> <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#restrições-por-fonte-de-mídia">Algumas fontes de mídiarestringem</Anchor> o compartilhamento de dados com terceiros. Portanto, os postbacks de eventos restritos não serão enviados para esse parceiro, independentemente da configuração de envio de postbacks.

## Integrando o Swrve e a AppsFlyer

Configure um postback que permite ao Swrve mensurar o LTV e o comportamento do usuário para diferentes fontes de aquisição:

**Etapa 1**: após inicializar o Swrve, defina o ID do usuário (antes de qualquer chamada ao SDK da AppsFlyer) com o seguinte:

<Tabs>
<Tab title="Para Android">

```java
AppsFlyerLib.setCustomerUserId(SwrveSDK.getUserId());
```

</Tab>

<Tab title="Para iOS">

```objectivec
NSString* swrve_user_id = [[Swrve sharedInstanceWithAppID:appId apiKey:apiKey] userID];
[[AppsFlyerTracker sharedTracker].customerUserID = swrve_user_id];
```

</Tab>

<Tab title="Para o Unity">

```swift
Appsflyer.setCustomerUserID(SwrveComponent. Instance.SDK. UserId);
```

</Tab>
</Tabs>

**Etapa 2**: configure um postback no dashboard da AppsFlyer executando as seguintes ações:

## Configurando o Swrve

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração** selecione **Ativar parceiro**.
4. Na **primeira visita** aqui, você precisará ativar o botão ***Ativar parceiro*** para habilitar a configuração dos parâmetros da aba de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro.  **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo.

A janela de configuração do Swrve utiliza apenas a aba **Integração** .

Para uma descrição detalhada da Janela de configuração de Pprceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

<div id="integration-tab" />

<Accordion title="Aba Integração">

A aba Integração está dividida em diferentes seções, conforme descrito abaixo.

### Ativar parceiro

No **Primeira visita** Aqui, você precisará ativar **Ativar parceiro** para habilitar a configuração dos parâmetros de integração. O botão deve permanecer ativado enquanto você trabalhar com o Medialyzer.Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">a ativação de parceiros</Anchor>.

### Configurações gerais

**ID do Aplicativo e chave de API**

O Swrve se conecta à AppsFlyer por meio de um ID do Aplicativo exclusivo e de uma chave de API. Se você ainda não os tiver, deverá obtê-los com o Swrve para continuar com a integração.

![Swrve_msc_new_3.png](https://files.readme.io/feb1d5f846629d1909727b70b66e4b36138704ebbe4518e2dc03652b9fe5c57a-360001902065.png)

Execute as seguintes etapas, conforme necessário:

* Digite o **APP\_ID**
* Digite a **api\_key**
* Selecione **UE** para clientes da UE
* Selecione **Advanced Data Sharing** para enviar as seguintes informações adicionais à Swrve: cost\_value, channel, keywords, siteID e c (campanha)

### Postbacks padrão

A AppsFlyer pode enviar postbacks automáticos à Swrve após a instalação do usuário. Use esta seção para definir o envio desses postbacks.

![Swrve_msc_new_4.png](https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png)

Selecione **Events attributed to any partner or organic** para enviar postbacks à Swrve para qualquer usuário que faça o download do aplicativo.

Clique em **Salvar**.

Depois de salvar, a AppsFlyer começa a enviar os seguintes dados à Swrve para cada instalação orgânica e instalação não orgânica:

* api\_key
* ID de usuário da Swrve conforme definido no SDK
* Media Source
* Nome da campanha

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Links de atribuição não estão disponíveis para a Swrve.

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

Permissões não estão disponíveis para a Swrve.

</Accordion>

## Relatórios da Swrve com dados da AppsFlyer

Depois de configurar os postbacks do servidor para enviar informações de atribuição da AppsFlyer para a Swrve, você pode visualizar os dados de aquisição na plataforma da Swrve e utilizar toda a gama de funcionalidades de segmentação e testes da Swrve.

A página principal do dashboard do seu aplicativo inclui todas as informações vitais do seu aplicativo em um relance. Nesta página, você pode continuar usando os recursos de testes, segmentação e relatórios selecionando as abas relevantes na barra de navegação principal.

![Gráfico de aquisição no dashboard da Swrve](https://files.readme.io/6a3e4cf709f58b20f2932ab47e6fa9289653504d85a0b6eec2580718e2a4dc7c-49839257162769.png)
![Tabela de dados de aquisição no dashboard da Swrve](https://files.readme.io/561403abefae9e98e24934c96dd25b1ee34ae24cf30695354c4930404e0a7f19-49839257163537.png)

<div data-zendesk-anchors="integrating-swrve-and-appsflyer=integrando-o-swrve-e-a-appsflyer h_01H9HWK5DM1K9P5XXC6S7ENAGV=integrando-o-swrve-e-a-appsflyer setting-up-swrve=configurando-o-swrve h_01H9HWK5DMS8HAK25BF5EXZT51=configurando-o-swrve h_01H9HWK5DN9D0DS46X72EDAW54=integration-tab activate-partner=ativar-parceiro h_01H9HWK5DN375XJVHQCZ8Y3K13=ativar-parceiro general-settings=configura%C3%A7%C3%B5es-gerais h_01H9HWK5DN0XK2E0HXS61GRECE=configura%C3%A7%C3%B5es-gerais default-postbacks=postbacks-padr%C3%A3o h_01H9HWK5DNH6SYY8T9NX09MRYS=postbacks-padr%C3%A3o h_01H9HWK5DNZVQDZ0Q1Z9WSKRSR=attribution-link-tab h_01H9HWK5DNPG89HSB0107TKHED=cost-tab h_01H9HWK5DNARD4K0MPHPXKBPXZ=ad-revenue-tab h_01H9HWK5DNFKAT0J98JWVRPQ1G=permissions-tab swrve-reporting-with-appsflyer-data=relat%C3%B3rios-da-swrve-com-dados-da-appsflyer h_01H9HWK5DN3QB9V593EV566GAQ=relat%C3%B3rios-da-swrve-com-dados-da-appsflyer" />
