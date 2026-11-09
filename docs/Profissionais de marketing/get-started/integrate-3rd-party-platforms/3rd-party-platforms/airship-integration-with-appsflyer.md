---
title: Integração do Airship com a AppsFlyer
metadata:
  keywords:
    - Attribution
    - SDK
    - Configure
    - urban airship
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
  created_at: '2015-12-16T11:31:38Z'
  edited_at: '2026-08-19T00:10:35Z'
  id: 207033976
  locale: pt
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/pt/articles/207033976
---
> **Em resumo:** Airship, um parceiro integrado da AppsFlyer, fornece a principal plataforma de engajamento mobile do mundo, ajudando milhares de empresas de todos os portes a estabelecer uma conexão direta e duradoura com seus clientes. Com o Airship, as empresas obtêm controle total sobre sua presença mobile — aplicativos, carteiras e dados em nível de usuário — para oferecer experiências que chamam a atenção e impulsionam ações no mobile ou em qualquer outro ponto de contato com o cliente.

<div id="important" />

> 🚧 **Importante!**
>
> <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#restrições-por-fonte-de-mídia">Algumas fontes de mídia</Anchor> restringem o compartilhamento de dados com terceiros. Portanto, os postbacks de eventos restritos não serão enviados para esse parceiro, independentemente da configuração de envio de postbacks.

<div id="setting-up-airship" />

## Configurando o Airship

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração** selecione **Ativar parceiro**.
4. No **primeiro acesso**, você precisará ativar **Ativar parceiro** para permitir a configuração dos parâmetros da aba de integração. **A opção deve permanecer ativada enquanto você trabalhar com o parceiro**.  
    Saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">ativação de parceiros</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo:

<div id="integration-tab" />

<Accordion title="Aba Integração">

A aba Integração está dividida em diferentes seções, conforme descrito abaixo.

<div id="activate-partner" />

### Ativar parceiro

No **Primeira visita** Aqui, você precisará ativar **Ativar parceiro** para habilitar a configuração dos parâmetros de integração. O botão deve permanecer ativado enquanto você trabalhar com o Medialyzer.Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">a ativação de parceiros</Anchor>.

<div id="general-settings" />

### Configurações gerais

O Airship se conecta à AppsFlyer por meio de uma chave de aplicativo e um token exclusivos. Se você ainda não os tiver, poderá obtê-los no Airship para continuar com a integração ou consultar abaixo as instruções sobre como obtê-los.

<Image align="center" alt="airship-integration-tab.png" src="https://files.readme.io/dc33feec09fe551700586b9778a037fa0f5d610224944aea5a0fe56a6d288043-360017400878.png" />

**Para configurar a integração com o Airship:**

Requisitos mínimos - AppsFlyer SDK:

* Android – versão 2.3.1.18 e acima
* iOS – versão 3.3.3 e acima

Requisitos mínimos - Airship SDK - Versão 13.1.0 e acima.

1. A integração com o Airship exige que o channelid (identificador exclusivo do usuário do Airship) seja preenchido no SDK da AppsFlyer.

   * [Mais informações sobre o Channel ID para iOS](https://docs.airship.com/platform/ios/segmentation/#airship-channel-ids).
   * [Mais informações sobre o Channel ID para Android](https://docs.airship.com/platform/android/segmentation/#airship-channel-ids).

   Esse parâmetro é enviado com cada postback e permite a identificação de cada usuário. Para fazer isso, você deve inserir as seguintes strings no código do seu aplicativo:

   <div id="important-note" />

   > 📘 **Observação importante**
   >
   > Verifique se as linhas de código foram inseridas no local correto – após a inicialização do SDK do Airship e antes que o método start seja chamado no iOS ou Android.


   <Tabs>
   <Tab title="Android">

   Para mais detalhes sobre o  `setAdditionalData` method, clique <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata">aqui</Anchor>.

   ```java
   HashMap<String, Object> customData = new HashMap<String,Object>(); String channelId = UAirship.shared().getChannel().getId();
   customData.put("channelid", channelId); AppsFlyerLib.getInstance().setAdditionalData(customData);
   ```

   </Tab>

   <Tab title="iOS">

   Para mais detalhes sobre o  `setAdditionalData` method, clique <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#customdata">aqui</Anchor>.

   ```objectivec
   let channelID = UAirship.channel().identifier
   print("My Application Channel ID: \(channelID)")
   ```

   </Tab>
   </Tabs>

2. Obtenha a App Key no Airship:
   1. Faça login na sua conta do Airship em: [go.airship.com](http://go.urbanairship.com/)
   2. No menu à esquerda, acesse **Settings >** **APIs &** **Integrations** e clique em **Airship API**.

      <Image align="center" alt="airship-appkey-en_us.png" src="https://files.readme.io/c33611035d8dcadb73e41a3787690726608bddde55edbc38f34990c03948985d-360017666917.png" />
   3. Copie a chave do Aplicativo.
   4. No AppsFlyer, cole a chave do Aplicativo no campo App Key.
3. Obtenha o Token do Airship:
   1. Faça login na sua conta Airship em: [go.airship.com](http://go.urbanairship.com/)
   2. No menu à esquerda, vá para **Settings >** **APIs &** **Integrations** e clique em **Tokens**.

      <Image align="center" alt="airship-token-creation-1.png" src="https://files.readme.io/b0c22d9844dbc93f7dd158a75916eca98404474a65be0c1528f83e6e4ac7b210-360017480697.png" />
   3. Clique em **criar token**.

      <Image align="center" alt="airship-token-creation-2.png" src="https://files.readme.io/656f6f5a6eebe3ccd1a786f6abec62739633e4150722fec41bc1fbdea78f8275-360017549138.png" />
   4. Insira o nome do token e selecione a função.
   5. Clique em **Criar token**.
   6. No AppsFlyer, cole o Token no campo **Token Authentication**.

<div id="default-postbacks" />

### Postbacks padrão

A AppsFlyer pode enviar postbacks automáticos ao Airship após as instalações e os reengajamentos do usuário. Use esta seção para definir a **origem dos usuários** que permitem o envio desses postbacks.

<Image align="center" alt="urban_airship_msc_new_3.png" src="https://files.readme.io/394dd47ff26742092f3012e333f137d706f41bc85cd6875013d792ce7f36b01d-360001900305.png" />

Selecione **Events attributed to any partner or organic** para enviar postbacks ao Airship para qualquer usuário que fizer o download do aplicativo.

Depois de salvar a configuração, a AppsFlyer envia os seguintes dados ao Airship para cada instalação orgânica e não orgânica:

* Device ID (IDFA / Google Advertising ID)
* Media Source
* Campaign name

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Links de atribuição não estão disponíveis para o Airship.

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

As permissões não estão disponíveis para o Airship.

</Accordion>

<div id="set-up-and-manage-the-attribution-data-in-airship-console" />

## Configure e gerencie os dados de atribuição no console do Airship

No Airship, atributos são pares de chave-valor que você associa às suas audiências para ajudar a direcioná-las melhor com mensagens. Use atributos para direcionar audiências com mais especificidade do que com tags.

Configure seus dados de atribuição do AppsFlyer no Airship [adicionando atributos individuais ao seu projeto](https://docs.airship.com/partners/appsflyer/#setting-attributes-for-integration).

<div data-zendesk-anchors="h_01H9FJYKH3V1TZ4GYEKKG46F2S=importante setting-up-airship=configurando-o-airship h_01H9FJYKH3SWMNC8CRPPDQMCGQ=configurando-o-airship h_01H9FJYKH4KQMK2N5BTTFTY076=integration-tab activate-partner=ativar-parceiro h_01H9FJYKH4NTCNVKBW9XSENFTP=ativar-parceiro general-settings=configura%C3%A7%C3%B5es-gerais h_01H9FJYKH4MMRE57BNEBD0P5NT=configura%C3%A7%C3%B5es-gerais h_01H9FJYKH4H93Q5S41HK7S4RD6=observa%C3%A7%C3%A3o-importante default-postbacks=postbacks-padr%C3%A3o h_01H9FJYKH44F4YQSEPKTGN7EYK=postbacks-padr%C3%A3o h_01H9FJYKH44S8F34YJ97TE32PM=attribution-link-tab h_01H9FJYKH47DYTR8T197CEXH0Z=cost-tab h_01H9FJYKH46AC5X7F6GAD9MQJG=ad-revenue-tab h_01H9FJYKH4N4T5JTGWHQC0A18Z=permissions-tab set-up-and-manage-the-attribution-data-in-airship-console=configure-e-gerencie-os-dados-de-atribui%C3%A7%C3%A3o-no-console-do-airship h_01H9FJYKH4Q09JSBJ25RRE02Y3=configure-e-gerencie-os-dados-de-atribui%C3%A7%C3%A3o-no-console-do-airship" />
