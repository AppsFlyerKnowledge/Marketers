---
title: Integração da plataforma Braze (antiga Appboy) com o AppsFlyer
metadata:
  keywords:
    - Appboy
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
  created_at: '2017-03-30T08:39:03Z'
  edited_at: '2026-08-19T00:10:49Z'
  id: 115001603343
  locale: pt
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/pt/articles/115001603343
---
> **At a glance:** **Num relance:** A Braze, uma parceira integrada da AppsFlyer, oferece uma plataforma de engajamento do ciclo de vida para equipes de marketing, crescimento e engajamento. A plataforma permite que os profissionais de marketing se conectem com seus clientes de forma mais humana e em escala, gerando engajamento profundo e aumentando o ROI. O ponto central da nossa plataforma é o perfil de usuário holístico que oferece uma visão única e completa do cliente.

Saiba mais em <Anchor target="_blank" href="https://www.braze.com/">braze.com</Anchor>.

> 🚧 **Important**
>
> **Observações importantes**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#restrições-por-fonte-de-mídia">Algumas fontes de mídia</Anchor> restringem o compartilhamento de dados com terceiros. Portanto, os postbacks de eventos restritos não serão enviados para esse parceiro, independentemente da configuração de envio de postbacks.
> * Os postbacks não serão enviados se a fonte for orgânica.

<div id="integration-overview" />

## Visão geral da integração

Siga as instruções abaixo para configurar a integração com a Braze.

Requisitos mínimos - AppsFlyer SDK:

* <Anchor target="_blank" href="/marketers/pt/docs/sdk-integration-overview">Android</Anchor> (Android SDK – versão 2.3.1.18 e superior)
* <Anchor target="_blank" href="/marketers/pt/docs/sdk-integration-overview">/docs/ctv-pc-and-console-platform-attribution-concepts</Anchor>

No Android, a integração com a Braze exige que o <Anchor target="_blank" href="https://www.braze.com/docs/partners/advertising_technologies/attribution/appsflyer/#integration">ID do dispositivo</Anchor> Braze (identificador exclusivo do usuário Braze) seja preenchido no AppsFlyer Android SDK. Esse parâmetro é enviado com cada postback e permite a identificação de cada usuário. Para fazer isso, você deve inserir as seguintes strings no código do seu aplicativo:

> 📘 **Note**
>
> **Importante!**
>
> Certifique-se de que as linhas de código sejam inseridas no lugar correto – depois que o SDK da Braze for iniciado e antes do código de inicialização do SDK da AppsFlyer (consulte a seção Iniciando o SDK em nosso Guia de integração do SDK do Android).

<Tabs>
<Tab title="Android iOS">

```java
HashMap<String, Object> customData = new HashMap<String,Object>(); String deviceId =(Braze.getInstance(MyActivity.this).getDeviceId());
customData.put("brazeCustomerId", deviceId); AppsFlyerLib.getInstance().setAdditionalData(customData);
```

</Tab>

<Tab title="Exemplo">

**Swift**

Há duas APIs do Swift, uma com um manipulador de conclusão e outra usando o novo suporte de simultaneidade do Swift. Ambos produzem o mesmo valor — a escolha de qual usar depende do contexto.

**Manipulador de conclusão rápida**

```swift
https://files.readme.io/b13aba84c394c0b4603e0aad2edd723525dadf204250349620b571bc47b0ba9d-360001907229.png
```

**Aguarde rápido**

```swift
Braze_msc_new_2.png
```

**Objetivo-C**

```objectivec
BRZConfiguration *configurations = [[BRZConfiguration alloc] initWithApiKey:@"BRAZE_API_KEY" endpoint:@"BRAZE_END_POINT"];
[configurations setUseUUIDAsDeviceId:NO]; Braze *braze = [[Braze alloc] initWithConfiguration:configurations];
[braze deviceIdWithCompletion:^(NSString * _Nonnull brazeDeviceId) {
    NSLog(@">>[BRZ]: %@", brazeDeviceId);
    [[AppsFlyerLib shared] setAdditionalData:@{
        @"brazeDeviceId": brazeDeviceId
    }];
}];
```

</Tab>

<Tab title="Unity">

```csharp
AndroidiOSUnity
```

</Tab>
</Tabs>

<div id="setting-up-braze" />

## Configurando a Braze

**Pré-requisito:** Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. **Para ativar:** Na AppsFlyer, no menu lateral, selecione**Colaborar** > **Partner Marketplace**.  
   **Para editar**: Na AppsFlyer, vá para o menu lateral e selecione **Colaborar** > **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração**, selecione o aplicativo e clique em **Ativar parceiro**.
4. Na **primeira visita** aqui, você deve ***ativar o Parceiro*** para permitir a configuração dos parâmetros da guia de integração.Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro.  **Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.**
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Para obter uma descrição detalhada do header da Janela de Configuração de Parceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

<Accordion title="Aba de integração">

A aba Integração está dividida em diferentes seções, conforme descrito abaixo.

<div id="activate-partner" />

### Ativar parceiro

Na sua **primeira visita** aqui, você deve ***ativar o parceiro***para habilitar a configuração dos parâmetros da guia de integração. Essa opção deve permanecer ativada enquanto você trabalhar com o parceiro.  
Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.

<div id="general-settings" />

### Configurações gerais

A Braze se conecta ao AppsFlyer por meio de uma chave de API exclusiva e um endpoint REST.

**Para obter a chave de API e o endpoint REST da Braze:**

1. Na sua conta Braze, em **Parceiros** **de Tecnologia** , acesse **Atribuição**.
2. Selecione **AppsFlyer**.  ![Selecione AppsFlyer como parceiro de tecnologia no Braze](https://files.readme.io/db96e8b5e2363f5250c6c1146a1f7a15e1ed6457fe4543dbe649f8818bb5db78-360017328637.png)
3. Em **Importação de dados para atribuição de instalação**, clique em Gerar chave de API.
4. braze-af-API-key.png
5. No AppsFlyer, insira a chave da API da Braze e o endpoint REST.  ![](https://files.readme.io/d9ee5206a8bf3c092c5297c361cf38b2c77717fbb9638b282032e4fc4c31091e-360001907289.png)
6. Clique em **Save and Close**.

Depois de salvar a configuração, o AppsFlyer envia os seguintes dados à Braze em cada instalação orgânica e não orgânica:

* Braze Dev\_ID
* Canal de mídia
* Nome da campanha
* adgroup\_name
* Nome do anúncio

<div id="default-postbacks" />

### Postbacks padrão

O AppsFlyer pode enviar postbacks automáticos para instalações de usuários da Braze. Use esta seção para definir o envio desses postbacks.

 <Image align="center" alt="Seção de postbacks padrão" src="https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png" />

Selecione **Eventos atribuídos a qualquer parceiro ou orgânico** para enviar postbacks à Braze para qualquer usuário que baixar o aplicativo.

Clique em **Salvar.**

> 📘 **Note**
>
> **Atenção**
>
> Embora todos os eventos sejam enviados pelo AppsFlyer, as instalações orgânicas não são contadas pela Braze e, portanto, são ignoradas pela API da Braze.

</Accordion>

<Accordion title="Aba do link de atribuição">

Links de atribuição não estão disponíveis para Braze.

</Accordion>

<Accordion title="Custo">

Os dados de custo não são compatíveis com a integração desse parceiro.

</Accordion>

<Accordion title="Aba receita de anúncios">

A receita de anúncios não é compatível com a integração desse parceiro.

</Accordion>

<Accordion title="Aba permissões">

Permissões não estão disponíveis para a Braze.

</Accordion>

<div id="viewing-user-attribution-data-in-braze" />

## Visualizando dados de atribuição do usuário na Braze

Sua base de usuários pode ser segmentada por dados de atribuição no painel da Braze usando os filtros Instalar Atribuição.

 <Image align="center" alt="Filtros de atribuição de instalação no dashboard da Braze" src="https://files.readme.io/7289491d4d301eb38618298536ac5b895a610024bf162c733409d3f50b10b8f4-360001908045.png" />

Além disso, os dados de atribuição de um usuário específico estão disponíveis no perfil de cada usuário no painel da Braze.

 <Image align="center" alt="Dados de atribuição em um perfil de usuário no Braze" src="https://files.readme.io/d9ee5206a8bf3c092c5297c361cf38b2c77717fbb9638b282032e4fc4c31091e-360001907289.png" />

<div data-zendesk-anchors="integration-overview=vis%C3%A3o-geral-da-integra%C3%A7%C3%A3o h_01H9FK453A9W5DCPR4X8PR06MZ=vis%C3%A3o-geral-da-integra%C3%A7%C3%A3o setting-up-braze=configurando-a-braze h_01H9FK453AWXF006KEVKD797QF=configurando-a-braze activate-partner=ativar-parceiro h_01H9FK453AVK4YKF41FEP0YRJN=ativar-parceiro general-settings=configura%C3%A7%C3%B5es-gerais h_01H9FK453AG6AXA7J43X6NGZT1=configura%C3%A7%C3%B5es-gerais default-postbacks=postbacks-padr%C3%A3o h_01H9FK453ASAKVHT7GV8BG56YS=postbacks-padr%C3%A3o viewing-user-attribution-data-in-braze=visualizando-dados-de-atribui%C3%A7%C3%A3o-do-usu%C3%A1rio-na-braze h_01H9FK453AQXG7NNT2841686MJ=visualizando-dados-de-atribui%C3%A7%C3%A3o-do-usu%C3%A1rio-na-braze" />
