---
title: Guia básico para integração do SDK
metadata:
  keywords:
    - sdk
    - iOS
    - Android
    - Integration
    - Advertisers
    - appuid
    - anonymous
    - kakao
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2013-08-22T16:09:08Z'
  edited_at: '2026-08-18T00:15:49Z'
  id: 207032066
  locale: pt
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/pt/articles/207032066
---
> **At a glance:** **Visão geral:** trabalhe com o desenvolvedor do seu app mobile ou de CTV para integrar e instalar o SDK em aplicativos Android ou iOS. Depois que as tarefas básicas de integração forem concluídas, seu aplicativo estará pronto para atribuição de instalação e métricas de eventos in-app.

<div id="implementing-the-dev-key-in-your-app" />

## **Implementação da dev key em seu app**

A AppsFlyer usa a dev key para identificar a sua conta. A dev key é obrigatória, pois ela permite que o SDK envie e recupere com segurança dados da sua conta. O seu desenvolvedor deve instalar e integrar o SDK, inserindo a dev key.

<div id="retrieve-the-dev-key" />

#### Recuperar a dev key

Antes que seu desenvolvedor possa instalar e integrar o SDK, você deve recuperar a sua dev key.

1. Na AppsFlyer, no menu lateral, selecione **Configurações**> **Configurações do aplicativo**.
2. Copie sua chave do desenvolvedor e envie-a para o desenvolvedor mobile.

   <Image align="center" alt="" src="https://files.readme.io/5078fdabbcce4d3977f3d32351b61bacbc8af406a68911f2c6b4cdca458712a5-30603573703057.png" />

<div id="provide-the-dev-key-to-your-developer" />

#### Forneça a Dev Key ao seu desenvolvedor

Forneça a Dev Key, o App ID e o API v2 token da AppsFlyer ao seu desenvolvedor com as seguintes instruções:

* Use o <Anchor target="_blank" href="https://dj.dev.appsflyer.com/?utm_source=kb&amp;utm_medium=kb-basic-sdk-integration">assistente de integração do SDK</Anchor> para instalação e integração automatizadas do SDK.
* Siga as instruções passo a passo para <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/sdk-installation">instalar</Anchor> e <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/sdk-integration">integrar</Anchor> o SDK.

<div id="where-to-start-the-sdk" />

## **Onde iniciar o SDK?**

Ao planejar a integração do SDK da AppsFlyer, a primeira decisão que você deve tomar é onde iniciar o SDK no fluxo de inicialização do seu app.

O princípio básico é que o SDK deve começar a enviar dados assim que possível, após a abertura do app. **Isso garante que o SDK capture o evento de instalação e todos os outros eventos in-app que ocorram na sessão.**

No entanto, para cumprir regulamentações de preservação de privacidade, como GDPR e CCPA, muitas vezes é necessário adiar o envio de dados para a AppsFlyer até que os usuários concordem em compartilhar suas informações.

<Tabs>
<Tab title="Iniciando o SDK no Android native">

<div id="starting-the-sdk-in-android-native" />

### O passo a passo da implementação do SDK para deferred deep linking.

<div id="select-in-what-class-to-start-the-sdk" />

#### SELECIONE EM QUAL CLASSE INICIAR O SDK

Selecione se deseja iniciar o SDK na classe  `Application` global ou na classe `Activity`:

* **Iniciar o SDK na classe** `Application` **global**: geralmente, inicializar o SDK na classe/subclasse `Application` global é uma prática recomendada, pois a classe `Application` é carregada e inicializada antes que qualquer interface do aplicativo seja exibida. Isso garante que o SDK possa ser iniciado a qualquer cenário, incluindo deep linking.
* **Inicie o SDK em uma classe** `Activity` **(início adiado)** para permitir que os usuários aceitem o compartilhamento de dados. Isso ocorre porque a obtenção do consentimento do usuário requer uma interface de usuário (IU) renderizada em uma classe `Activity`.

<div id="android-developer-instructions" />

#### INSTRUÇÕES PARA DESENVOLVEDORES ANDROID

* Informe o desenvolvedor sobre o seguinte:
  * Em que classe - `Application` ou `Activity` - iniciar o SDK?
  * Qual cenário de opt-in/opt-out usar?
* Envie ao seu desenvolvedor o link de referência a seguir:
  * [Como executar deferred start](https://dev.appsflyer.com/hc/docs/integrate-android-sdk#starting-the-android-sdk)

</Tab>

<Tab title="Android nativo iOS nativo Unity React nativo">

<div id="starting-the-sdk-in-ios" />

<div id="starting-the-sdk-in-ios-native" />

### Iniciar o SDK em iOS Native

<div id="delay-the-sdk-start-in-ios" />

#### ATRASAR O INÍCIO DO SDK NO IOS

Ao planejar o momento de início do SDK, é importante considerar se deve-se atrasar `start` até que o usuário dê seu consentimento.

O SDK oferece o método `waitForATTUserAuthorization`, que permite **configurar quanto tempo o SDK deve aguardar pelo consentimento do usuário antes de enviar dados aos servidores da AppsFlyer**.

Para mais informações sobre o fluxo de dados desse método e sua interação com o framework ATT no iOS, veja [Como configurar o suporte para App Tracking Transparency (ATT)](/docs/basic-sdk-integration-guide#visão-geral-da-função-waitforattuserauthorization).

<div id="ios-developer-instructions" />

#### INSTRUÇÕES PARA DESENVOLVEDORES IOS

Compartilhe com seu desenvolvedor as seguintes informações:

* Qual é o tempo limite, em segundos, antes do envio de dados à AppsFlyer?
* Links para desenvolvedores:
  * Guia de [Como iniciar o SDK do iOS](https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#starting-the-ios-sdk) para desenvolvedores e referências sobre como iniciar o SDK.
  * [Configurar suporte para App Tracking Transparency (ATT)](/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support) para informações sobre o fluxo de dados do método [e como ele interage com o framework ATT do iOS.](/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support)
  * Guia de [Como habilitar o suporte App Tracking Transparency (ATT)](https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#enabling-app-tracking-transparency-att-support) para desenvolvedores e referências para `waitForATTUserAuthorization`

</Tab>

<Tab title="Unity">

<div id="starting-the-sdk-in-Unity" />

<div id="starting-the-sdk-in-unity" />

### O passo a passo da implementação do SDK para deep linking unificado.

Envie ao seu desenvolvedor <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/basicintegration#manual-integration">este artigo do Dev Hub</Anchor> sobre como iniciar o SDK.

</Tab>

<Tab title="CONTEXTO">

<div id="starting-the-sdk-in-react" />

<div id="starting-the-sdk-in-react-native" />

### http://dev.appsflyer.com/hc/docs/in-app-events-sdk

Envie ao seu desenvolvedor <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#startsdk">este artigo do Dev Hub</Anchor> sobre como iniciar o SDK.

</Tab>
</Tabs>

<div id="select-your-privacy-preserving-strategy" />

## Defina a sua estratégia de proteção à privacidade

Defina **como você pretende garantir a privacidade dos usuários.** Por exemplo, escolha entre interromper o SDK na instalação, impedir o compartilhamento de dados com terceiros, anonimizar os dados do usuário ou desabilitar identificadores específicos.

Para mais informações sobre os diferentes métodos de proteção à privacidade disponíveis, consulte <Anchor target="_blank" href="/marketers/pt/docs/apply-privacy-preserving-sdk-methods">Métodos de proteção à privacidade no SDK</Anchor>.

<div id="attribution" />

## **Atribuição**

O SDK coleta <Anchor target="_blank" href="/marketers/pt/docs/about-device-identifiers">identificadores</Anchor> com o objetivo de garantir a atribuição. Para garantir que as instalações sejam registradas e atribuídas corretamente, analise e siga as diretrizes abaixo.

**Todas as plataformas**

<Accordion title="Identificador exclusivo para instalações">

Um AppsFlyer ID é criado automaticamente para cada nova instalação de um aplicativo. Nenhuma ação é necessária por parte do profissional de marketing.

Você pode usar esse identificador para realizar as seguintes ações:

* Enviar <Anchor target="_blank" href="/marketers/pt/docs/server-to-server-events-api-for-mobile-s2s-mobile">eventos in-app de servidor para servidor</Anchor>.
* Combine o ID da AppsFlyer com os registros do usuário em seus sistemas de back-end.
* Baixe o <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview">relatório de dados brutos de eventos in-app</Anchor> e use o **appsflyer\_id** para analisar o comportamento e as jornadas do usuário.

</Accordion>

<Accordion title="Integre identificadores exclusivos de seu sistema de BI com a AppsFlyer">

Definir seu próprio CUID no SDK da AppsFlyer permite que você cruze seu ID exclusivo com o AppsFlyer ID e outros identificadores. O CUID está disponível nos relatórios de <Anchor target="_blank" href="/marketers/pt/docs/raw-data-field-dictionary">dados brutos</Anchor> da AppsFlyer. Também é possível usá-lo em APIs de postback para referência cruzada com seus IDs internos.

Para saber mais sobre o CUID, consulte <Anchor target="_blank" href="/marketers/pt/docs/customer-user-id-field-cuid">este artigo.</Anchor>

</Accordion>

**Apenas para Android**

As seções a seguir descrevem considerações de atribuição para a Google Play Store ou lojas de aplicativos de terceiros.

<Accordion title="Atribuir aplicativos publicados no Google Play">

#### GOOGLE PLAY INSTALL REFERRER

A [API Google Play Install Referrer](https://developer.android.com/google/play/installreferrer) melhora a precisão da <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model#métodos-de-atribuição">atribuição</Anchor>, oferece proteção contra fraudes de instalação e permite a recuperação segura de dados de referral do Google Play (como, por exemplo, a versão do app no momento em que foi instalado pela primeira vez).

Recomendamos que forneça ao seu desenvolvedor as [instruções para adicionar a Google Play Install Referrer API](https://developer.android.com/google/play/installreferrer/library).

#### GAID

A partir do SDK V4.8.0, a AppsFlyer passou a coletar automaticamente esse identificador de dispositivo.

</Accordion>

<Accordion title="Atribuir apps em lojas externas">

Com a AppsFlyer, você pode <Anchor target="_blank" href="/marketers/pt/docs/set-up-multi-store-android-attribution">atribuir instalações provenientes de lojas de aplicativos de terceiros</Anchor>, como Amazon, Opera, GetJar, Baidu e Huawei. Isso permite que você promova seus aplicativos e alcance públicos maiores em mercados onde a Google Play Store não está disponível.

A AppsFlyer é compatível com a atribuição no contexto de lojas de aplicativos de terceiros da seguinte forma:

* **IMEI ou Android ID:** O SDK não coleta automaticamente o IMEI ou Android ID. Entretanto, se houver necessidade de coletar esses identificadores (por exemplo, para <Anchor target="_blank" href="/marketers/pt/docs/measure-attribution-in-the-chinese-domestic-market#atribuição-de-aplicativos-android-no-mercado-doméstico-chinês">apps no mercado chinês</Anchor>) seu desenvolvedor poderá implementar um dos seguintes tipos de coleta:
  * Coleta manual: o aplicativo envia o IMEI ou Android ID para o SDK usando a API `setImeiData` ou `setAndroidIdData` (veja a referência da função nas abas abaixo). O SDK envia os dados para os servidores da AppsFlyer.

    <Tabs>
    <Tab title="Iniciando o SDK no Android native">

    Consulte a referência do Android SDK para:

    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setimeidata">`setImeiData`</Anchor>
    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setandroididdata">`setAndroidIdData`</Anchor>

    </Tab>

    <Tab title="Unity">

    Consulte a referência do Unity SDK para:

    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setimeidata">`setImeiData`</Anchor>
    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setandroididdata">`setAndroidIdData`</Anchor>

    </Tab>
    </Tabs>

  * Opt-in da coleta de device ID: força o SDK a coletar o IMEI ou ID do Android usando setCollectIMEI e setCollectAndroidID (consulte a referência da função nas abas abaixo).

    <Tabs>
    <Tab title="Iniciando o SDK no Android native">

    Consulte a referência do Android SDK para:

    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectimei">`setCollectIMEI`</Anchor>
    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectandroidid">`setCollectAndroidID`</Anchor>

    </Tab>

    <Tab title="Unity">

    Consulte a referência do Unity SDK para:

    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setcollectimei">`setCollectIMEI`</Anchor>
    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setcollectandroidid">`setCollectAndroidID`</Anchor>

    </Tab>

    <Tab title="iOS native UnityReact Native">

    Consulte a referência do React Native para:

    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#setcollectimei">`setCollectIMEI`</Anchor>
    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#setcollectandroidid">`setCollectAndroidID`</Anchor>

    </Tab>
    </Tabs>

* **OAID:** OAID: atribui instalações de lojas de aplicativos externas no Android. Para mais informações, veja o <Anchor target="_blank" href="/marketers/pt/docs/android-oaid-implementation-in-the-sdk">guia de implementação do OAID</Anchor>.
* **Install referrers:** o SDK é compatível com a recuperação de dados de referral da Samsung Gallery e da Huawei AppGallery.

</Accordion>

**Exclusivo para iOS**

As seções a seguir incluem informações importantes sobre o suporte para dispositivos iOS 14+.

<Accordion title="Configurando o suporte da App Tracking Transparency (ATT)">

**CONTEXTO**

A partir do iOS 14.5, a coleta do IDFA requer o consentimento do usuário. Na prática, isto significa que o acesso ao IDFA é regulado pela estrutura [**App Tracking Transparency**](https://developer.apple.com/documentation/apptrackingtransparency) (ATT). Em dispositivos iOS 14+, o SDK usa o framework da ATT para obter acesso ao IDFA do dispositivo. Para uma introdução à ATT, veja o artigo <Anchor target="_blank" href="/marketers/pt/docs/about-att-and-skan#att-principles">princípios da ATT</Anchor>.

<Tabs>
<Tab title="Android nativo iOS nativo Unity React nativo">

Consulte o Dev Hub para <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#enabling-app-tracking-transparency-att-support">instruções para desenvolvedores sobre como implementar a ATT</Anchor>.

</Tab>

<Tab title="Unity">

Consulte o Dev Hub para <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/basicintegration#collect-idfa-with-attrackingmanager">instruções para desenvolvedores sobre como implementar a ATT</Anchor>.

</Tab>
</Tabs>

Quando a atribuição ocorre usando IDFA, é importante que o IDFA seja enviado na **primeira inicialização.** Por esse motivo, o SDK fornece o método `waitForATTUserAuthorization`.

<div id="waitforattuserauthorization-overview" />

#### Visão geral da função waitForATTUserAuthorization

> 🚧 **Important**
>
> Não chame `waitForATTUserAuthorization` se você não pretende invocar o prompt da ATT.

`waitForATTUserAuthorization` permite que você configure por quanto tempo o SDK deve adiar e esperar pelo status da ATT antes de enviar dados aos servidores da AppsFlyer.

<Image align="center" alt="" src="https://files.readme.io/a41e66c5aa23d2c673aba5b06589dcc24d34175e90900a8232343272ecca427c-30603573710993.png" />

Quando um usuário inicia o aplicativo, o status da ATT é **notDetermined.** Durante o tempo de espera do `waitForATTUserAuthorization`, o SDK coloca na fila o evento de abertura e os eventos in-app consecutivos na memória, assim como acontece quando [eventos offline são registrados](https://dev.appsflyer.com/hc/docs/in-app-events-sdk#offline-in-app-events):

* Se o usuário **consentir** com a solicitação da ATT (coleta de IDFA):
  * O SDK adiciona o IDFA a eventos em cache.
  * O SDK inicia e envia eventos armazenados em cache com IDFA (sem esperar que o tempo limite termine).
* Se o usuário **recusar** a notificação da ATT: O SDK inicia e envia eventos armazenados em cache sem IDFA (sem esperar que o tempo limite termine).
* Se o tempo limite terminar e o status da ATT permanecer como **notDetermined:** o SDK inicia e envia eventos em cache sem IDFA.

**Considerações**

* Chamar [`requestTrackingAuthorization`](https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/3547037-requesttrackingauthorization) sem definir `waitForATTUserAuthorization` resultará no envio de aberturas e eventos sem IDFA para dispositivos com iOS 14+.
* Se o usuário mover o aplicativo para o background durante o timeout:
  * O temporizador pausa até que o aplicativo volte para o primeiro plano.
  * Os eventos são armazenados em cache na memória.
* Se o usuário fechar o aplicativo, ele será eliminado durante o tempo limite:
  * O temporizador é reiniciado na próxima abertura do aplicativo.
  * Os eventos armazenados em cache são perdidos.

</Accordion>

<Accordion title="Personalizar o diálogo de consentimento da ATT">

Você pode personalizar o prompt da ATT. Uma mensagem que indique claramente o propósito da solicitação pode ajudar a aumentar as taxas de adesão dos usuários.

Considere o seguinte ao criar sua mensagem:

* Use a linguagem que melhor explique aos usuários por que o aplicativo está pedindo o consentimento.
* Informe aos usuários sobre como os dados serão usados. [Saiba mais sobre privacidade do usuário e uso de dados.](https://developer.apple.com/app-store/user-privacy-and-data-use/)

Assim que sua mensagem for concluída, forneça ao desenvolvedor o texto e as instruções de implementação.

<Tabs>
<Tab title="Android nativo iOS nativo Unity React nativo">

Consulte o Dev Hub para <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#customizing-the-att-consent-dialog">obter instruções do desenvolvedor sobre como personalizar a caixa de diálogo de consentimento da ATT</Anchor>.

</Tab>

<Tab title="Unity">

Consulte o Dev Hub para [obter instruções do desenvolvedor sobre como personalizar a caixa de diálogo de consentimento da ATT](https://dev.appsflyer.com/hc/docs/basicintegration#collect-idfa-with-attrackingmanager).

</Tab>
</Tabs>

</Accordion>

<Accordion title="Suporte para atribuição da SKAN">

> 📘 **Note**
>
> Para oferecer suporte completo à atribuição da SKAN, atualize para o iOS SDK V6.2.3+.

SKAN é uma classe usada pelo iOS para validar instalações de aplicativos impulsionadas por anunciantes. O processo de validação da instalação do app envolve o app de origem e o app anunciado.

Um aplicativo de origem é um aplicativo que participa de campanhas publicitárias exibindo anúncios de uma ad network. Configurar seu aplicativo para exibir anúncios não está dentro do escopo do SDK da AppsFlyer. Para configurar, siga as [instruções da Apple](https://developer.apple.com/documentation/storekit/skadnetwork/configuring_a_source_app).

Para o aplicativo anunciado (o aplicativo com o SDK da AppsFlyer), a <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide">solução para SKAN</Anchor> da AppsFlyer usa SKAN para fornecer o postback de atribuição enquanto a AppsFlyer coleta, traduz e agrega os dados, mantendo a privacidade do usuário. Quando o aplicativo é iniciado pela primeira vez, a plataforma AppsFlyer usa a configuração definida pelo profissional de marketing para instruir o SDK sobre como definir o valor de conversão SKAN.

Para usar a solução SKAN:

* O profissional de marketing deve configurar a mensuração da SKAN na AppsFlyer. O desenvolvedor não precisa realizar nenhuma ação.
* O SDK da AppsFlyer chama automaticamente as APIs necessárias da SKAN.
* Certifique-se de desativar as chamadas SKAN em outros SDKs caso dependa da AppsFlyer para atribuição SKAN.
* Não há nenhuma outra ação ou processo de registro exigido pelo desenvolvedor ou pelo profissional de marketing na App Store.

Para desativar a atribuição da SKAN, instrua o desenvolvedor a desativá-la no SDK.

<Tabs>
<Tab title="Android nativo iOS nativo Unity React nativo">

Para desativar a atribuição SKAN, use <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disableskadnetwork">`disableSKAdNetwork`</Anchor>

</Tab>

<Tab title="Unity">

Para desativar a atribuição SKAN, use <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#disableskadnetwork">`disableSKAdNetwork`</Anchor>

</Tab>

<Tab title="Android native UnityReact Native">

Para desativar a atribuição SKAN, use <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#disableskad">`disableSKAd`</Anchor>

</Tab>
</Tabs>

</Accordion>

<div id="recording-in-app-events" />

## **Registro de eventos in-app**

Eventos in-app (IAE) oferecem insights sobre o que está acontecendo em seu aplicativo. O registro de eventos in-app ajuda a mensurar KPIs como ROI (retorno sobre o investimento) e LTV (Lifetime Value). Recomendamos que você separe um momento para definir os eventos que deseja gravar.

Depois de definir os eventos in-app que você deseja mensurar, envie os nomes e parâmetros dos eventos para o desenvolvedor, incluindo um link para:

* O [assistente de instalação do SDK](https://dj.dev.appsflyer.com/?utm_source=kb&amp;utm_medium=kb-basic-sdk-integration) que oferece uma explicação específica para eventos in-app.
* As instruções passo a passo de implementação de eventos in-app no SDK.

Para aprender a configurar eventos in-app e enviá-los ao seu desenvolvedor, veja nosso <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview">guia de eventos in-app avançados</Anchor>.

**Todas as plataformas**

<Accordion title="Registrar receita">

É possível enviar receita com qualquer evento in-app. Certifique-se de usar o parâmetro **af\_revenue** para incluir a receita. É o único parâmetro de evento que a AppsFlyer conta como receita real no dashboard e nos relatórios de dados brutos. <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#revenue-events">Saiba mais</Anchor>.

<Tabs>
<Tab title="Iniciando o SDK no Android native">

Para instruções sobre como configurar eventos de receita, veja [aqui](https://dev.appsflyer.com/hc/docs/in-app-events-android#logging-revenue).

</Tab>

<Tab title="Android nativo iOS nativo Unity React nativo">

Para instruções sobre como configurar eventos de receita, veja [aqui](https://dev.appsflyer.com/hc/docs/in-app-events-ios#logging-revenue).

</Tab>

<Tab title="Unity">

* Para instruções para desenvolvedores sobre eventos in-app em geral, veja [aqui](https://dev.appsflyer.com/hc/docs/inappevents#send-event).
* Para instruções específicas sobre receita no iOS e Android, consulte as abas Android e iOS.

</Tab>
</Tabs>

</Accordion>

<Accordion title="Validar compras dentro do aplicativo">

O SDK da AppsFlyer oferece verificação do servidor para compras in-app. A validação da compra in-app envia automaticamente um evento de compra in-app à AppsFlyer. O envio manual desse evento cria relatórios de eventos duplicados.

</Accordion>

<Accordion title="Verticais da indústria">

Veja nossa <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#recommended-events-by-business-vertical">lista de eventos in-app recomendados por vertical</Anchor>, por exemplo, viagens, jogos ou eCommerce.

</Accordion>

<div id="deep-linking-with-onelink" />

## **Deep linking com o OneLink**

OneLink é a solução da AppsFlyer para atribuição multiplataforma, **redirecionamento e deep linking**.

**Todas as plataformas**

<Accordion title="Detecção e redirecionamento de dispositivos">

Para usuários sem o aplicativo instalado, o OneLink detecta o tipo de dispositivo e o redireciona para o destino correto (por exemplo, Google Play, Apple App Store, loja de aplicativos de terceiros ou página da web). Isso se baseia nas configurações do template do OneLink. <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template">Saiba mais</Anchor>

</Accordion>

<Accordion title="Deep linking">

Para usuários com o aplicativo instalado, o OneLink abre o aplicativo. Além de abrir o aplicativo, você também pode fazer um deep link com usuários para uma atividade ou página específica dentro do aplicativo. Isso exige que seu desenvolvedor implemente Unified Deep Linking (UDL) usando:

* O [assistente de instalação do SDK](https://dj.dev.appsflyer.com/?utm_source=kb&amp;utm_medium=kb-basic-sdk-integration) que oferece uma explicação detalhada para a implementação de deep linking, ou
* https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl

**Observação**:

* O UDL requer o SDK V6.1+.
* Os clientes que já usam o OneLink para deep linking podem estar usando o [método legado](https://dev.appsflyer.com/hc/docs/dl_work_flow#legacy-use-only-gcd-api-for-deep-linking) em vez do UDL.

Consulte nosso guia sobre como configurar <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">deep linking e deferred deep linking</Anchor>.

</Accordion>

<Accordion title="Deep linking diferido">

Para usuários sem o aplicativo instalado, o OneLink detecta o tipo de dispositivo e os redireciona para o destino correto: Google Play, Apple App Store, lojas externas ou página na web. Depois que o usuário iniciar o aplicativo, você poderá usar deferred deep linking para redirecioná-los para uma atividade ou página específica dentro do aplicativo.

Isso exige que seu desenvolvedor implemente deferred deep linking usando:

* O [assistente de instalação do SDK](https://dj.dev.appsflyer.com/?utm_source=kb&amp;utm_medium=kb-basic-sdk-integration) que oferece uma explicação detalhada para a implementação de deep linking, ou
* https://dev.appsflyer.com/hc/docs/dl_work_flow#recommended-implement-extended-deferred-deep-linking

**Observação**:

* O UDL requer o SDK V6.1+.
* Os clientes que já usam o OneLink para deferred deep linking podem estar usando o [método legado](https://dev.appsflyer.com/hc/docs/dl_work_flow#legacy-use-only-gcd-api-for-deep-linking) em vez do UDL.

Consulte nosso guia sobre como configurar <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">deep links e deferred deep linking</Anchor>.

</Accordion>

<div id="accessing-attribution-and-deep-linking-data" />

## **Acessando dados de atribuição e deep linking**

A tabela a seguir descreve os métodos disponíveis para a recuperação de dados de atribuição e deep linking:

| Método | Quem está envolvido? | Retorno dos resultados | Método de obtenção | Dados de atribuição | Dados de deep linking | Disponibilidade |
| --- | --- | --- | --- | --- | --- | --- |
| <Anchor target="_blank" href="/marketers/pt/docs/push-api-streaming-raw-data">**API de push**</Anchor> | • Profissional de marketing • Desenvolvedor de back-end | Normalmente em minutos | Back-end | S | Não | Premium |
| <Anchor target="_blank" href="/marketers/pt/docs/pull-api-raw-data">**Extrair API**</Anchor> | • Profissional de marketing • Desenvolvedor de back-end | • Periódico (não em tempo real). • Você pode agendar downloads de relatórios de dados brutos. | Back-end | S | S | Premium para relatórios de dados brutos |
| <Anchor target="_blank" href="/marketers/pt/docs/data-locker-for-marketers">**Relatório do Data Locker**</Anchor> | • Profissional de marketing • Desenvolvedor de back-end | Os relatórios por hora estão disponíveis dentro de 1 a 3 horas | Armazenamento na nuvem disponível através das seguintes opções: • Bucket da AppsFlyer na AWS • Armazenamento próprio (AWS ou GCS) | S | S | Premium |
| <Anchor target="_blank" href="/marketers/pt/docs/conversion-data-payloads-and-scenarios#visão-geral">**Obtenção de dados de conversão (GCD)**</Anchor> | • Profissional de marketing • Desenvolvedor mobile <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#legacy-use-only-gcd-api-for-deep-linking">Consulte a documentação para desenvolvedor</Anchor> | Até 5 segundos | SDK | S | S | Todas as contas |
| <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template">**Unified Deep Linking (UDL)**</Anchor> | • Profissional de marketing • Desenvolvedor mobile <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl">Consulte a documentação para desenvolvedor</Anchor> | Até 1 segundo | SDK | Não | S | Todas as contas |

Observe o seguinte para usuários que não deram o consentimento no iOS 14.5+:

* Ao usar UDL para mídias pagas e próprias, os dados de deep linking estão disponíveis.
* Ao usar o GCD para mídias pagas, os dados são limitados e não incluem detalhes de atribuição e deep linking.

> 👍 **Tip**
>
> Recomendamos o seguinte:
>
> * Use a Push API para recuperar dados de atribuição e enviá-los para seus servidores para processamento posterior. Esse método aguarda que os dados se tornem disponíveis e, portanto, é muito preciso e próximo do tempo real. O GCD fornece dados em tempo real, mas pode apresentar imprecisões quando as decisões finais de atribuição são efetuadas após mais de cinco segundos.
> * Use a Pull API para complementar periodicamente (por exemplo, diariamente) dados de atribuição em tempo real e para compensar quaisquer erros de comunicação que possam ocorrer.

<div id="testing-your-sdk-integration" />

## **Testar a integração do SDK**

Assim que a integração do SDK for concluída, você poderá acessar o painel da AppsFlyer e, na página Testes de integração do SDK, testar instalações orgânicas e não orgânicas, eventos in-app e deep linking (retargeting). Isso garante que as instalações e os eventos in-app sejam registrados e atribuídos corretamente.

Para cenários e instruções de teste, consulte <Anchor target="_blank" href="/marketers/pt/docs/testing-the-sdk-integration-for-marketers">Teste de integração do SDK</Anchor>.

**Atenção:** ao realizar testes de atribuição, <Anchor target="_blank" href="/marketers/pt/docs/registering-test-devices">registre um dispositivo de teste</Anchor> (Android ou iOS) para garantir que cada instalação seja registrada como uma nova instalação. Um dispositivo de teste registrado impede que as instalações sejam registradas como reinstalações.

> 📘 **Note**
>
> **Veja também**
>
> * Visão geral das plataformas CTV, PC e console

<div data-zendesk-anchors="retrieving-the-dev-key=implementa%C3%A7%C3%A3o-da-dev-key-em-seu-app h_01HAWCK9K4QBRE74JAS8Q7MEXW=implementa%C3%A7%C3%A3o-da-dev-key-em-seu-app retrieve-the-dev-key=recuperar-a-dev-key h_01HHHKTARNPQTBXQ6CQGEHMJRG=recuperar-a-dev-key embed-the-dev-key=forne%C3%A7a-a-dev-key-ao-seu-desenvolvedor h_01HHHKXMBGV6EM0CCW842RQQZ6=forne%C3%A7a-a-dev-key-ao-seu-desenvolvedor where-to-start-the-sdk=onde-iniciar-o-sdk h_01HAWCK9K4MBS0F0HE6QE1W1AN=onde-iniciar-o-sdk starting-the-sdk-in-android=o-passo-a-passo-da-implementa%C3%A7%C3%A3o-do-sdk-para-deferred-deep-linking h_01HAWCK9K45HCJEDRW761WHKES=o-passo-a-passo-da-implementa%C3%A7%C3%A3o-do-sdk-para-deferred-deep-linking select-in-what-class-to-start-the-sdk=selecione-em-qual-classe-iniciar-o-sdk h_01HAWCK9K428SDFBFCCSZ15X9J=selecione-em-qual-classe-iniciar-o-sdk android-developer-instructions=instru%C3%A7%C3%B5es-para-desenvolvedores-android h_01HAWCK9K4XR1HZHP7Y15Q2Q4N=instru%C3%A7%C3%B5es-para-desenvolvedores-android h_01HAWCK9K4693729EX1WYFR6XT=starting-the-sdk-in-ios h_01HAWCK9K4QSBP874RX2ZRA7EB=delay-the-sdk-start-in-ios h_01HAWCK9K4VHDFB9CYHC144BZN=ios-developer-instructions h_01JQ73M8DWMVQ98V1DQMPT0316=starting-the-sdk-in-Unity h_01JQ73M8DW350GBH9P52W4516V=starting-the-sdk-in-react select-the-optoutin-scenario::ae4c6e25=defina-a-sua-estrat%C3%A9gia-de-prote%C3%A7%C3%A3o-%C3%A0-privacidade h_01HAWCK9K4EXBA2F0BPVBXFAMG=defina-a-sua-estrat%C3%A9gia-de-prote%C3%A7%C3%A3o-%C3%A0-privacidade attribution=atribui%C3%A7%C3%A3o h_01HAWCK9K41T5GGWDB3ABYGRHW=atribui%C3%A7%C3%A3o h_01HAWCK9K4V91MPQHXDZBD0HKR=google-play-install-referrer h_01HAWCK9K4YD8CYQDB2YRA8W1F=gaid waitforattuserauthorization-overview=vis%C3%A3o-geral-da-fun%C3%A7%C3%A3o-waitforattuserauthorization h_01HAWCK9K5JHDWS8KTBTTGSS9G=vis%C3%A3o-geral-da-fun%C3%A7%C3%A3o-waitforattuserauthorization recording-inapp-events=registro-de-eventos-in-app h_01HAWCK9K5ZZYQR8KPCWANZEA5=registro-de-eventos-in-app deep-linking-with-onelink=deep-linking-com-o-onelink h_01HAWCK9K5PK9RE7WZQVCY97KC=deep-linking-com-o-onelink accessing-attribution-and-deep-linking-data=acessando-dados-de-atribui%C3%A7%C3%A3o-e-deep-linking h_01HAWCK9K5ACPZ2WKBTVR3VVTD=acessando-dados-de-atribui%C3%A7%C3%A3o-e-deep-linking testing-your-sdk-integration=testar-a-integra%C3%A7%C3%A3o-do-sdk h_01HAWCK9K6JQ33T32RYKYH20P1=testar-a-integra%C3%A7%C3%A3o-do-sdk" />
