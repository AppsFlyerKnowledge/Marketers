---
title: Integração do OneSignal com a AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2020-11-29T08:11:41Z'
  edited_at: '2026-08-19T00:11:34Z'
  id: 360015926437
  locale: pt
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/pt/articles/360015926437
---
> **At a glance:** **Em resumo:** o OneSignal é o provedor líder de mercado de notificações push e mensagens in-app, oferecendo suporte a mais de 1 milhão de desenvolvedores e profissionais de marketing com uma plataforma de engajamento de primeira linha.

<Image align="center" alt="onesignal-logo-stack__3_.png" src="https://files.readme.io/49c50c481c00391f25cf8cc7eb2c35cc166f6a88a10db9120769a7d11affa26a-13013733757841.png" />

O OneSignal entrega 8 bilhões de mensagens todos os dias em todo o mundo. Com tecnologia de arquitetura superior e uma plataforma fácil de usar, o OneSignal entrega mensagens mais rapidamente, com mais eficiência e em maior escala do que qualquer outra solução no mundo. Saiba mais em [onesignal.com](https://onesignal.com/?utm_medium=partner&utm_source=appsflyer)

> 🚧 **Important**
>
> **Importante!**
>
> <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#restrições-por-fonte-de-mídia">Algumas fontes de mídiarestringem</Anchor> o compartilhamento de dados com terceiros. Portanto, os postbacks de eventos restritos não serão enviados para esse parceiro, independentemente da configuração de envio de postbacks.

<div id="setting-up-onesignal" />

## Configurando o OneSignal

A integração com o OneSignal inclui inserir algumas linhas de código no SDK da AppsFlyer no seu aplicativo e, em seguida, ativar a integração na AppsFlyer.

<div id="set-up-the-appsflyer-sdk" />

### Configurar o SDK da AppsFlyer

Ao usar o Android, a integração com o OneSignal exige que o OneSignal Player ID (identificador exclusivo de usuário do OneSignal) seja preenchido no SDK Android da AppsFlyer. Esse parâmetro é enviado com cada postback e permite a identificação de cada usuário.

**Para configurar o SDK iOS da AppsFlyer:**

1. Certifique-se de que a versão do SDK que você usa seja 2.3.1.18 ou superior.
2. Insira as linhas de código a seguir no código do seu aplicativo – [depois que o SDK do OneSignal for iniciado](https://documentation.onesignal.com/docs/android-sdk-setup) e antes do código de inicialização do SDK da AppsFlyer.
   * Para dispositivos Android que usam a versão 3.x.x do OneSignal SDK:

     ```http
     OSPermissionSubscriptionState status = OneSignal.getPermissionSubscriptionState();

               String deviceId = status.getSubscriptionStatus().getUserId();

                 customData.put("onesignalCustomerId", deviceId);
     ```
   * SDK do Unity:

     ```http
     var status = OneSignal. GetPermissionSubscriptionState();

               String deviceId = status.subscriptionStatus.userId;

                 customData.put("onesignalCustomerId", deviceId);
     ```
   * Para dispositivos Android que usam o OneSignal Native SDK versão 4+:

     ```http
     OSDeviceState device = OneSignal.getDeviceState();

               String deviceId = device.getUserId();

                 customData.put("onesignalCustomerId", deviceId);
     ```

**Para configurar o SDK Android da AppsFlyer:**

1. Certifique-se de que a versão do SDK que você usa seja 2.3.1.18 ou superior.
2. Insira as linhas de código a seguir no código do seu aplicativo – [depois que o SDK do OneSignal for iniciado](https://documentation.onesignal.com/docs/android-sdk-setup) e antes do código de inicialização do SDK da AppsFlyer.
   * Para dispositivos iOS que usam a versão 2.x.x do OneSignal SDK:

     <Tabs>
     <Tab title="Swift">

     ```http
     let status: OSPermissionSubscriptionState = OneSignal.getPermissionSubscriptionState()
     if let deviceId = status.subscriptionStatus.userId{
         customData.put("onesignalCustomerId", deviceId);
     ```

     </Tab>

     <Tab title="Objetivo-C">

     ```http
     OSPermissionSubscriptionState* status = [OneSignal getPermissionSubscriptionState]; NSDictionary* CustomDataMap = [[NSDictionary alloc] initWithObjectsAndKeys:status.subscriptionStatus.userId, @"onesignalCustomerId", nil];
     [[AppsFlyerLib shared] setAdditionalData:CustomDataMap];
     ```

     </Tab>
     </Tabs>

   * Para dispositivos iOS que usam o SDK nativo do OneSignal versão 3+:

     <Tabs>
     <Tab title="Swift">

     ```http
     if let deviceState = OneSignal.getDeviceState() {
         let deviceId = deviceState.userId
         customData.put("onesignalCustomerId", deviceId);
     ```

     </Tab>

     <Tab title="Objetivo-C">

     ```http
     OSDeviceState *deviceState = [OneSignal getDeviceState]; NSString *deviceId = deviceState.userId; NSDictionary* CustomDataMap = [[NSDictionary alloc] initWithObjectsAndKeys:deviceId, @"onesignalCustomerId", nil];
     [[AppsFlyerLib shared] setAdditionalData:CustomDataMap];
     ```

     </Tab>
     </Tabs>

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. **Para ativar:** na AppsFlyer, no menu lateral, selecione **Colaborar** > **Partner Marketplace**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Clique em **Configurar a integração**.
4. Na aba **Integração**, selecione o aplicativo e ative a opção **Ativar parceiro**.  
    **Observação:** essa opção deve permanecer habilitada (<Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">ativada</Anchor>) enquanto você trabalhar com o parceiro. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">a ativação de parceiros</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo:

<div id="integration-tab" />

<Accordion title="Aba Integração">

<Image align="center" alt="onesignal-integration-tab.png" src="https://files.readme.io/95ec88041360d492367ed383aa3242bebe1cd5c5abcff8fba64e7888f0a9c052-360017329277.png" />

A aba Integração está dividida em diferentes seções, conforme descrito abaixo.

<div id="activate-partner" />

### Ativar parceiro

Deve permanecer ativado enquanto você trabalhar com o parceiro.  
Saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation#ativar-uma-integração-de-parceiro">ativação de parceiros</Anchor>.

<div id="general-settings" />

### Configurações gerais

#### OneSignal AppID

O ID do seu aplicativo do OneSignal está disponível na plataforma do OneSignal em **Configurações** > **Chaves & IDs**.Para conectar sua conta do OneSignal ao AppsFlyer, insira o ID do seu aplicativo no campo **OneSignal AppID** .

<Image align="center" alt="onesignal-app-id-en_us.png" src="https://files.readme.io/2801bce8ea7ef4be731d8429bd0408f432d4b5600fbd359e989b0013da56b93e-360015238678.png" />

<div id="default-postbacks" />

### Postbacks padrão

<Image align="center" alt="onesignal-default-postbacks_en-us.png" src="https://files.readme.io/07e40365685543a318be8a16c9ea83638634d4a60333338eca0f76d140f84bef-360014377697.png" />

A AppsFlyer pode enviar postbacks automáticos para o OneSignal após instalações de usuário. Use esta seção para definir a fonte dos usuários para a qual os postbacks são enviados para cada evento.  
Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#default-postbacks">postbacks padrão</Anchor>.

**Para enviar postbacks ao OneSignal para qualquer usuário que fizer download do aplicativo**, selecione **Todos os canais de mídia, incluindo orgânicos**.

**Para concluir a configuração da integração,** clique em **Salvar integração**.

Embora todos os eventos sejam enviados pela AppsFlyer, as instalações orgânicas não são contabilizadas pelo OneSignal e, portanto, são ignoradas pela API do OneSignal.

Depois de salvar a configuração, a AppsFlyer envia os seguintes dados ao OneSignal para cada instalação orgânica e não orgânica:

* Canal de mídia
* Campaign name
* ID de dispositivo
* ID do anúncio

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Os links de atribuição não estão disponíveis para o Amplitude.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

Os dados de custo não se aplicam à integração com este parceiro.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A receita de anúncios não se aplica à integração com este parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

As permissões não estão disponíveis para este parceiro.

</Accordion>

<div id="view-user-attribution-data-in-onesignal" />

## Ver dados de atribuição do usuário no OneSignal

Você pode visualizar a atribuição no Editor de Segmentos nas tags do OneSignal, tanto no nível do dispositivo individual quanto ao criar um segmento para usar em uma campanha.

<Image align="center" alt="onesignal-view-attribution_en-us.png" src="https://files.readme.io/ac23c9310cad560f692598127f3e9efb7c2b905efb6fd5de21efabe90bf58eea-360014377737.png" />

<div data-zendesk-anchors="setting-up-onesignal=configurando-o-onesignal h_01H9HWJTEYDEZ8AGVQBHZZTP7K=configurando-o-onesignal set-up-the-appsflyer-sdk=configurar-o-sdk-da-appsflyer h_01H9HWJTEY71PTXR1YSAK709QT=configurar-o-sdk-da-appsflyer h_01H9HWJTEZC62F9JW1KD4Y1CYS=integration-tab activate-partner=ativar-parceiro h_01H9HWJTEZH60AEPE7AB43X4YG=ativar-parceiro general-settings=configura%C3%A7%C3%B5es-gerais h_01H9HWJTEZJAK2PTF4HQP3DQ1X=configura%C3%A7%C3%B5es-gerais h_01H9HWJTEZCNZX17K86H9KCRFN=onesignal-appid default-postbacks=postbacks-padr%C3%A3o h_01H9HWJTEZ91KR3ZA8NX5BVZCF=postbacks-padr%C3%A3o h_01H9HWJTEZZYRBS6PPRBBQAXZ5=attribution-link-tab h_01H9HWJTEZNT0EHJ7G4SFRD8K5=cost-tab h_01H9HWJTEZS7TN4FCAN40QB1NT=ad-revenue-tab h_01H9HWJTEZEY5VKCKDZ1Q7APRG=permissions-tab view-user-attribution-data-in-onesignal=ver-dados-de-atribui%C3%A7%C3%A3o-do-usu%C3%A1rio-no-onesignal h_01H9HWJTEZZTJFTZC1Z2A6F5QM=ver-dados-de-atribui%C3%A7%C3%A3o-do-usu%C3%A1rio-no-onesignal" />
