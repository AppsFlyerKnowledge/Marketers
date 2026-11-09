---
title: Integração Mixpanel com a AppsFlyer
metadata:
  keywords:
    - Attribution
    - Mixpanel
    - SDK
    - integrated partner
    - Advertisers
    - Ad Networks
    - facebook mixpabel
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
  created_at: '2015-12-24T11:33:01Z'
  edited_at: '2026-08-19T00:11:26Z'
  id: 207447103
  locale: pt
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/pt/articles/207447103
---
> **Visão geral:** Saiba como compartilhar dados automaticamente da AppsFlyer para o Mixpanel, uma plataforma de análise de produtos.

<Image align="center" alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mixpanel.png" />

A integração entre AppsFlyer e Mixpanel permite importar as informações da campanha de aquisição da AppsFlyer para o Mixpanel.

<div id="important" />

> 🚧 **Importante!**
>
> <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#restrições-por-fonte-de-mídia">Algumas fontes de mídia</Anchor> restringem o compartilhamento de dados com terceiros. Portanto, os postbacks de eventos restritos não serão enviados para esse parceiro, independentemente da configuração de envio de postbacks.

<div id="setting-up-mixpanel" />

## Configurando o Mixpanel

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. **Para ativar:** Na AppsFlyer, no menu lateral, selecione**Colaborar** > **Partner Marketplace**.  
   **Para editar**: Na AppsFlyer, vá para o menu lateral e selecione **Colaborar** > **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Pesquise pelo parceiro (`rokuads_int`) e selecione-o.
4. Na aba **Integração**, selecione o aplicativo e clique em **Ativar parceiro**.  
    **Atenção:** **o toggle deve permanecer ligado ([ativado](#)) enquanto você trabalhar com o parceiro. [Saiba mais sobre a ativação de parceiros](#).**
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Para obter uma descrição detalhada do cabeçalho da janela de configuração do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

<div id="integration-tab" />

<Accordion title="Aba de integração">

A aba Integração está dividida em diferentes seções, conforme descrito abaixo.

<div id="general-settings" />

### Configurações gerais

<Image align="center" alt="mixpanel-general-settings.png" src="https://files.readme.io/df1b95eb3926aa7e10db338f156a87b88aabda6b97a4d28db2953e9e48a114e6-360017400598.png" width="542px" />

* **Residência de dados da UE**: A AppsFlyer envia dados para os servidores do Mixpanel nos EUA como padrão. Para enviar dados para os servidores da UE do Mixpanel, ative essa opção.  
  **\*token**: O Mixpanel se conecta à AppsFlyer por meio de um token exclusivo. Se você ainda não o tem, você deve solicitá-lo ao Mixpanel para continuar com a integração.

  **Para obter o Token do Mixpanel:**

  1. Faça login na sua conta Mixpanel em: https://mixpanel.com/login/
  2. No **Mixpanel**, vá para o painel **Análise** e clique no ícone de engrenagem.

     <Image align="center" alt="mixpanel-token-1.png" src="https://files.readme.io/f1fbc76fff621e12a7d91fed5ba49eb20f2b049de65c70b0ab32cadd997287d2-small-360014578477.png" />
  3. Copie seu token da seção Chaves de acesso do seu projeto e cole-o no campo de **token** na aba de integração do Mixpanel do AppsFlyer.

     <Image align="center" alt="mixpanel-token-2.png" src="https://files.readme.io/e8e633ec87d963244652a53b9b21c495b0a850e234621a44d93b3034c640bff7-360014578757.png" />
* **Enviar ID do anunciante**:
  * Se você estiver usando o parâmetro AppsFlyer customer\_user\_id, ele será enviado para o Mixpanel a cada instalação (Deixe **Enviar ID do anunciante** desativado).
  * Se você não estiver usando o AppsFlyer customer\_user\_id - ative **Enviar ID do anunciante.** O ID do dispositivo é enviado para o Mixpanel como o customer\_user\_id (unique\_id no Mixpanel).  
    Saiba mais sobre o guia de integração do SDK da AppsFlyer para <Anchor target="_blank" href="/marketers/pt/docs/sdk-integration-overview">Android</Anchor> e <Anchor target="_blank" href="/marketers/pt/docs/sdk-integration-overview">iOS</Anchor>.
* **Eventos:** Ative para enviar dados de instalação para o ponto final do Mixpanel Events.
* Pessoas: Ative isso para enviar dados de instalação para o ponto final do Mixpanel People.

  <div id="note" />

  > 📘 **Observação**
  >
  > Para que os postbacks de instalação sejam enviados ao Mixpanel, pelo menos um dos dois pontos finais, **Events** ou **People**, deve estar ativado.

* **Compartilhamento avançado de dados:** Habilite isso para enviar informações adicionais ao Mixpanel: c (campaign), network (pid), impression\_based (is-impression).

<div id="default-postbacks" />

### Postbacks padrão

A AppsFlyer pode enviar postbacks automáticos para o MixPanel após instalações de usuários. Use essa seção para definir a fonte de usuários para a qual os postbacks são enviados. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#default-postbacks">postbacks padrão</Anchor>.

<Image align="center" alt="" src="https://files.readme.io/6cf4f0e1b73c634c5fbe8f79e654ff3a3cd318bdca51d5e6b17933c307eb769d-36693858465809.png" />

<div id="in-app-events-settings" />

### Configurações de eventos in-app

<Image align="center" alt="mixpanel-in-app-events-settings.png" src="https://files.readme.io/db5e4e6d5bbe084a94b90425d49345511c214ddc39380a2b8419659ad752cdb2-360014576637.png" />

Nesta seção, você mapeia eventos da AppsFlyer com o Mixpanel através de postbacks.

<div id="note-1" />

> 📘 **Observação**
>
> O Mixpanel captura eventos in-app usando seu próprio SDK. O único evento que pode ser enviado para o Mixpanel que não é capturado por eles é af\_uninstall.

Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">postbacks de eventos in-app</Anchor>.

**Para configurar postbacks de eventos in-app:**

1. Insira o token Mixpanel.
2. Ative postback de evento in-app.
3. **Para enviar o ID do anunciante da desinstalação**, ative **Enviar ID do anunciante**.
4. **Para enviar informações adicionais para a desinstalação**, habilite o **Compartilhamento Avançado de Dados**.
5. Clique em **Adicionar evento** para adicionar um evento SDK à lista.
6. Selecione **af\_uninstall** no menu suspenso.
7. Selecione o **Identificador de Evento de Parceiro** correspondente no menu suspenso.
8. Selecione a opção necessária no menu suspenso Enviar receita:
   * **Sem valores e sem receita:** envia apenas o evento em si sem o valor do evento.
   * **Com valores e sem receita:** envia todos os parâmetros excluindo o valor da receita.
   * **Valores e receita**: envia todos os parâmetros do evento, inclusive o valor da receita (se existir no evento).
9. Para concluir a configuração de integração, clique em **Salvar integração**.

Depois de salvar a integração, a AppsFlyer envia os seguintes dados para o Mixpanel para cada instalação orgânica e não orgânica:

* Parâmetro de token Mixpanel
* Customer\_user\_id ou ID do dispositivo (IDFA / Google Advertising ID)
* Fonte de mídia
* Nome da campanha

**Observação:** O CUID não é enviado em postbacks de desinstalação.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Aba do link de atribuição">

Os links de atribuição não estão disponíveis para o Amplitude.

</Accordion>

<div id="cost-tab" />

<Accordion title="Custo">

Os dados de custo não são compatíveis com a integração desse parceiro.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Aba receita de anúncios">

A receita de anúncios não é compatível com a integração desse parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

As permissões não estão disponíveis para este parceiro.

</Accordion>

<div id="integrating-with-mixpanel-when-using-a-login-mechanism" />

## Integração com o Mixpanel ao usar um mecanismo de login

Veja a seguir um exemplo das etapas de integração:

1. O aplicativo foi iniciado (aberto) pelo usuário.
2. O SDK do Mixpanel gera um ID distinto aleatório (**distinct\_id**).
3. Obtenha o ID distinto do Mixpanel e defina-o como o ID do usuário do cliente, usando a função do SDK do Appsflyer **setCustomerUserId**.
4. Envie<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#start">**Start**</Anchor>. Essa API permite que a AppsFlyer detecte instalações, sessões e atualizações.
5. Depois que a instalação do aplicativo é atribuída, um evento **instalação** é enviado ao Mixpanel com a ID de usuário do cliente, que inclui a ID distinta do Mixpanel.
6. Quando o usuário se registra ou faz login, o comando Mixpanel identify() é chamado com o identificador do usuário (por exemplo, e-mail ou ID do cliente). Isso mapeará o ID aleatório inicial distinto para o ID de usuário registrado.

   <Tabs>
   <Tab title="Android">

   Mixpanel Android - <Anchor target="_blank" href="https://developer.mixpanel.com/docs/android#section-combining-anonymous-and-identifiable-user-data">Combinando dados anônimos e identificáveis do usuário</Anchor>

   ```java
   MixpanelAPI mixpanel = MixpanelAPI.getInstance(context, MIXPANEL_TOKEN);
   mixpanel.identify("user@example.com");

   // Mixpanel v6.2.0 and below should use the following API:
   mixpanel.getPeople().identify(“user@example.com”);
   ```

   </Tab>

   <Tab title="Objective C">

   Mixpanel iOS Objective C - <Anchor target="_blank" href="https://developer.mixpanel.com/docs/ios#section-combining-anonymous-and-identifiable-user-data">Combinando dados anônimos e identificáveis do usuário</Anchor>

   ```objectivec
   [mixpanel identify:@“user@example.com”];
   ```

   </Tab>

   <Tab title="Swift">

   Mixpanel iOS Swift - [Combinando dados anônimos e identificáveis do usuário](https://developer.mixpanel.com/docs/swift#section-combining-anonymous-and-identifiable-user-data)

   ```swift
   mixpanel.identify(“user@example.com”);
   ```

   </Tab>

   <Tab title="Unity">

   Mixpanel Unity - [Combinando dados anônimos e identificáveis do usuário](https://developer.mixpanel.com/docs/unity#section-combining-anonymous-user-data-with-identifiable-user-data)

   ```csharp
   // set customer user id or device id
   Mixpanel. Identify(“user@example.com”);
   ```

   </Tab>
   </Tabs>

7. O Mixpanel recebe o customer\_user\_id do AppsFlyer com o alias do ID do usuário (por exemplo, endereço de e-mail).

<div id="note-2" />

> 📘 **Observação**
>
> Se você não estiver usando nenhum processo de registro dentro de seu aplicativo, implemente as etapas 1 a 3 conforme descrito acima.

<div id="viewing-appsflyer-data-in-mixpanel" />

## Exibindo dados da AppsFlyer no Mixpanel

As capturas de tela abaixo são um relatório de funil para ver a conversão da instalação por meio do valor do evento, dividido pela fonte de mídia. Além disso, o tempo para converter para cada fonte de mídia pode ser visto.

<Image align="center" alt="" src="https://files.readme.io/fdffbe0a2f29c8a8b02b600966583cdeb4917bb48f0502e9b00ef39daa2fa835-9646475113361.png" />

<Image align="center" alt="" src="https://files.readme.io/043a96a00e46a3daaef2b9fa4d58d252391ca2bb14307437f28c447d96ae97d6-9646475229841.png" />

<div data-zendesk-anchors="h_01H9FKEWTEN4F8FM5C9A9ES6HN=importante setting-up-mixpanel=configurando-o-mixpanel h_01H9FKEWTEGMEVH3SK739DD719=configurando-o-mixpanel h_01H9FKEWTE90WR75PMNN93JAXE=integration-tab general-settings=configura%C3%A7%C3%B5es-gerais h_01H9FKEWTEMT7VGTTFWFMJHYA8=configura%C3%A7%C3%B5es-gerais h_01H9FKEWTEV3RWKMWZN0EXFFNP=observa%C3%A7%C3%A3o default-postbacks=postbacks-padr%C3%A3o h_01H9FKEWTER31RXAH216TRXQPM=postbacks-padr%C3%A3o inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01H9FKEWTERRVKPQFF1B8QQERE=configura%C3%A7%C3%B5es-de-eventos-in-app h_01H9FKEWTEEMMQ0KKRZXRJRE25=observa%C3%A7%C3%A3o-1 h_01H9FKEWTEEQ0GHF87V20TX9W0=attribution-link-tab h_01H9FKEWTEJ61197SN3R6JXYCP=cost-tab h_01H9FKEWTEA7GN2HHK3QD62A3A=ad-revenue-tab h_01H9FKEWTET4QD1RE0HJZM64D4=permissions-tab integrating-with-mixpanel-when-using-a-login-mechanism=integra%C3%A7%C3%A3o-com-o-mixpanel-ao-usar-um-mecanismo-de-login h_01H9FKEWTE9DEANTXKPD286GD2=integra%C3%A7%C3%A3o-com-o-mixpanel-ao-usar-um-mecanismo-de-login h_01H9FKEWTFZ107Y999WEMB3409=observa%C3%A7%C3%A3o-2 viewing-appsflyer-data-in-mixpanel=exibindo-dados-da-appsflyer-no-mixpanel h_01H9FKEWTF9PFNVHTZGDKBX75Y=exibindo-dados-da-appsflyer-no-mixpanel" />
