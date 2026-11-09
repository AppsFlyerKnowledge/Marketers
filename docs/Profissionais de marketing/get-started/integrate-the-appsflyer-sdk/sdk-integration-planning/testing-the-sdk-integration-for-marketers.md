---
title: Testando a integração do SDK para profissionais de marketing
metadata:
  keywords:
    - Testing
    - SDK
    - Advertisers
    - Debug
    - Debugging
    - redirects test
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2018-11-12T14:15:08Z'
  edited_at: '2026-08-19T00:15:17Z'
  id: 360001559405
  locale: pt
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/pt/articles/360001559405
---
> **At a glance:** **Em resumo:** Teste a integração do seu aplicativo Android ou iOS com a AppsFlyer.

<div id="overview" />

## Visão Geral

Após a conclusão da integração do SDK, você pode verificar se o SDK está se comunicando com sucesso com os servidores da AppsFlyer. Os profissionais de marketing podem escolher entre dois métodos de teste:

* Usando o **Teste de integração do SDK** que permite:
  * <Image alt="" src="https://files.readme.io/16b90e430d7beea0eaa1530130d094d590c0a202f6c6ad298a88aac9508fee7a-31828933593745.png" width="30px" /> [A visualização de eventos em tempo real](#view-live-events) conforme eles ocorrem no seu aplicativo de teste.
  * [Teste de instalação não orgânica](#h_01HYX9R15931HJEA06SY3K47W5)
  * [Teste de deep links (retargeting)](#h_01HYX9R159DDNJW53AWTWT4C2Z)
* [Usando links de atribuição.](#testar-usando-links-de-atribuição)

Os desenvolvedores podem realizar testes de integração em seu ambiente de desenvolvimento. Veja os <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integration-testing">artigos de teste de integração do Dev Hub</Anchor>.

Os aplicativos de CTV também podem ser testados - para mais informações, acesse [testes de CTV](#testando-ctv).

<div id="testing-using-the-sdk-integration-tests-page" />

## Testes usando a página de testes de integração do SDK

Use a página **testes de Integração do SDK** para visualizar eventos em tempo real, como instalações, receita de anúncios e eventos in-app, à medida que eles ocorrem em seu aplicativo. Você também pode testar instalações não orgânicas, eventos in-app e deep linking (retargeting), além de identificar problemas de integração em seu projeto. O visualizador de eventos ao vivo substitui a ferramenta legada de testes de eventos in-app.

> 📘 **Note**
>
> Android iOS
>
> * **Somente iOS**: a página de teste de integração do SDK é aplicável apenas para aplicativos iOS que implementam a ATT. Você pode testar aplicativos sem a ATT usando o procedimento especificado aqui.
> * **Android:** Embora o ID do dispositivo (GAID) geralmente seja coletado automaticamente, recomendamos verificar se o SDK o coleta.

<div id="prepare-a-test-device" />

### **Prepare um dispositivo de teste**

1. Prepare um dispositivo (Android ou iOS) que não tenha o aplicativo instalado. Se necessário, desinstale o aplicativo do dispositivo.
2. <Anchor target="_blank" href="/marketers/pt/docs/registering-test-devices">Registre o dispositivo como um dispositivo de teste.</Anchor>

<div id="perform-the-integration-tests" />

### Execute os testes de integração

Os **testes de integração do SDK** fornecem os três testes a seguir:

<Accordion title="Ver eventos ao vivo">

O Live Event Viewer é uma ferramenta de teste que mostra dados em tempo real enviados do SDK para a AppsFlyer, como eventos de instalação e outros eventos in-app. Para cada evento capturado, você pode ver o log de eventos e os detalhes.

> 📘 **Note**
>
> O Live Events Viewer também oferece suporte a eventos in-app e sessões criados em um dispositivo de teste, enviados ao seu servidor e ingeridos no AppsFlyer por meio da API S2S. Verifique se os eventos S2S incluem o identificador do dispositivo (IDFA para iOS, GAID para Android) do dispositivo de teste registrado.

**Para exibir eventos no Visualizador de Eventos ao Vivo:**

1. Na AppsFlyer, no menu lateral, selecione **configurações** > **Testes de Integração do SDK**.

   <Image align="center" alt="" src="https://files.readme.io/c4f39fb2ddf1de510d9a03e292b05fab444600a8584c0a23e7b3e613c7077799-31828925846033.png" />
2. Clique em **Eventos ao vivo.**

   <Image align="center" alt="" src="https://files.readme.io/6ec1edba14e51bb27babf80d2d6f4873dbaa5113752217b4fb13399f7a1c61f1-31828925849489.png" />
3. Na lista de **Aplicativos** , selecione o app que você deseja testar.
4. Na lista de **Dispositivos de teste** , selecione o dispositivo que você quer usar para testar seu aplicativo. Se você não tiver um dispositivo de teste, poderá registrar um clicando no link **Adicionar um dispositivo de teste**.
5. Clique em **Continuar** para começar a registrar os eventos do seu aplicativo.
6. Inicie o aplicativo e interaja com ele para gerar sessões e eventos in-app.

   <Image align="center" alt="" src="https://files.readme.io/72b8822197dc626c1b28a9f8d43bb3c1a91f99e600ae0d8d1f74829bc62dcce6-31828933607313.png" />
7. Clique em um item de evento para exibir os detalhes do evento no painel direito.
8. Se você quiser parar de gravar os eventos, clique em **Parar**. Clique em **Começar** novamente quando você quiser continuar.

</Accordion>

<Accordion title="Testar instalações não orgânicas:">

**Para testar instalações não orgânicas:**

1. Na AppsFlyer, no menu lateral, selecione **configurações** > **Testes de Integração do SDK**.

   <Image align="center" alt="" src="https://files.readme.io/c4f39fb2ddf1de510d9a03e292b05fab444600a8584c0a23e7b3e613c7077799-31828925846033.png" />
2. Clique em testar **Instalações não orgânicas**.

   <Image align="center" alt="" src="https://files.readme.io/34440ab6d328e2d519f759f3c2a1b17dbcbee55af32b47bdbd52bb9f537c6735-31828933612177.png" />
3. Na lista de **Aplicativos** , selecione o app que você deseja testar.
4. Na lista de **Dispositivos de teste** , selecione o dispositivo que você quer usar para testar seu aplicativo. Se você não tiver um dispositivo de teste, poderá registrar um clicando no link **Adicionar um dispositivo de teste**.
5. Se o aplicativo testado estiver instalado no seu dispositivo de teste, desinstale-o.
6. Selecione **Removi o aplicativo do dispositivo testado**.
7. Clique em **Continuar** e siga as etapas do assistente.

**Se o aplicativo não registrar uma instalação não-orgânica, os possíveis motivos podem ser:**

* O IDFA está disponível, mas o dispositivo de teste não foi <Anchor target="_blank" href="/marketers/pt/docs/registering-test-devices#registrar-um-dispositivo-de-teste-ios">registrado com esse identificador na página de Dispositivos de teste</Anchor>.
* Você tem mais de 1 dos seus aplicativos, além do aplicativo de teste, instalado no dispositivo de teste, mas o dispositivo de teste não foi <Anchor target="_blank" href="/marketers/pt/docs/registering-test-devices#registrar-um-dispositivo-de-teste-ios">registrado com o IDFV na página de Dispositivos de teste</Anchor>.
* Uma instalação orgânica foi gravada.
* O teste foi realizado em uma versão do aplicativo que não inclui o SDK.

Para erros de integração, entre em contato com o desenvolvedor.

</Accordion>

<Accordion title="Teste de deep links (retargeting)">

**Antes de começar:**

* Inicie o aplicativo de teste pelo menos 3 vezes.
* Para testar o deep linking (retargeting), o OneLink deve ser definido para o seu aplicativo. Para mais informações, consulte o <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template">guia de configuração do OneLink</Anchor>.
* Verifique se o <Anchor target="_blank" href="/marketers/pt/docs/app-settings#reengagement-attribution">retargeting</Anchor> está ativado.

**Para testar deep links:**

1. Na AppsFlyer, no menu lateral, selecione **configurações** > **Testes de Integração do SDK**.

   <Image align="center" alt="Keyboard Maestro Engine 2024-10-06 10.00.47.png" src="https://files.readme.io/c4f39fb2ddf1de510d9a03e292b05fab444600a8584c0a23e7b3e613c7077799-31828925846033.png" width="2895px" />
2. Clique em **retargeting**.

   <Image align="center" alt="" src="https://files.readme.io/7c5eb6870e8d4c25a817f6c2895163b699e0a4972a6cc675b94396c386288d72-31828925858961.png" />
3. Na lista de **Aplicativos** , selecione o app que você deseja testar.
4. Na lista de **Dispositivos de teste** , selecione o dispositivo que você quer usar para testar seu aplicativo. Se você não tiver um dispositivo de teste, poderá registrar um clicando no link **Adicionar um dispositivo de teste**.
5. Clique em **Continuar** e siga as etapas do assistente.

</Accordion>

<div id="testing-using-attribution-links" />

## Testar usando links de atribuição

A seção a seguir descreve os procedimentos que você deve seguir para testar instalações com links de atribuição. Você pode executar esses testes mesmo se o aplicativo ainda estiver pendente (ou seja, não listado na Google Play Store ou na Apple App Store).

<Accordion title="Testar atribuição de instalação">

Testar instalações permite que você verifique se o SDK da AppsFlyer está atribuindo instalações corretamente a vários canais de mídia.

**Para testar a atribuição de instalação:**

1. Copie o link a seguir (Android ou iOS) e faça as seguintes alterações:

   1. Valor **app\_id**: adicione o seu app ID na AppsFlyer.
   2. Parâmetro **pid**: especifique o nome do canal de mídia ao qual a instalação é atribuída.
   3. Parâmetro **c**: especifique o nome da campanha.
   4. Se você estiver testando um aplicativo disponível em uma loja externa do Android: adicione o <Anchor target="_blank" href="/marketers/pt/docs/set-up-multi-store-android-attribution#single-dashboard-attribution-links">parâmetro af\_r</Anchor> ao link de atribuição.
   5. Substitua o GAID, o IDFA ou o IDFV pelo identificador de dispositivo específico.

   <Tabs>
   <Tab title="com o Android">

   ```
   https://app.appsflyer.com/<app_id>?pid=Test&c=Test&advertising_id=<GAID>
   ```

   </Tab>

   <Tab title="/docs/ctv-pc-and-console-platform-attribution-concepts">

   IDFA

   ```
   https://app.appsflyer.com/<app_id>?pid=Test&c=Test&idfa=<IDFA>
   ```

   IDFV

   ```
   https://app.appsflyer.com/<app_id>?pid=Test&c=Test&idfv=<IDFV>
   ```

   </Tab>
   </Tabs>

   Abaixo estão exemplos de links de atribuição com valores específicos:

   <Tabs>
   <Tab title="com o Android">

   ```

   ```

   ```
   https://app.appsflyer.com/com.my.app?pid=Test&c=Test&advertising_id=12345f9*-eba*-421*-876*-7654ac67876*
   ```

   </Tab>

   <Tab title="/docs/ctv-pc-and-console-platform-attribution-concepts">

   ```

   ```

   ```
   https://app.appsflyer.com/id123456789?pid=Test&c=Test&idfa=1A2B****-9128-4***-123*-04E***654321
   ```

   </Tab>
   </Tabs>

> 📘 **Note**
>
> Se você estiver testando um aplicativo iOS sem <Anchor target="_blank" href="/marketers/pt/docs/registering-test-devices">registrar um dispositivo de teste,</Anchor> seu clique de teste poderá ser sinalizado como fraudulento pelo P360.
>
> Para evitar que esse evento seja detectado como fraude, adicione o seguinte parâmetro de consulta ao seu link: `pid=ios_testing`

1. Copie o link atualizado, envie-o para o dispositivo de teste e clique no link.

> 📘 **Note**
>
> No iOS, use o iMessage ou o e-mail para enviar o link para o dispositivo. Não cole o link no aplicativo iOS Notes e clique no link. Essa ação pode fazer com que o link quebre.

1. Siga um dos procedimentos abaixo:

   * Se o aplicativo estiver ativo, realize a instalação.
   * Se o aplicativo estiver pendente, a seguinte mensagem será exibida: "*O aplicativo que você está procurando ainda não está disponível no mercado."*Este é o resultado esperado."Esse é o resultado esperado. Como o aplicativo não está ativo, o link de atribuição não leva a nenhuma loja de aplicativos. No entanto, o link de atribuição ainda é válido para fins de atribuição e você deve instalar o aplicativo da seguinte maneira:
     * **Para Android** A partir de um arquivo APK (ou Android Studio para desenvolvedores)
     * **Para iOS:** Do TestFlight (ou Xcode para desenvolvedores)

   Você verá uma instalação atribuída à campanha de teste no canal de mídia chamado **Test**. Aguarde até 30 minutos para que a instalação apareça no dashboard do aplicativo.

   <Image align="center" alt="Test_Install_Attribution_Link" src="https://files.readme.io/1771da27f7b8c5334d68c3d7c8361e91e0e35a3a08abf60e3d711f83de9ad22d-31828925861265.png" />

> 👍 **Tip**
>
> Veja abaixo formas alternativas de verificar os resultados do teste:
>
> * Se você tiver acesso aos relatórios de dados brutos, baixe o <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview">Relatório de dados brutos de instalações</Anchor>. Esse relatório leva vários minutos para ser baixado. **Para fazer o download do relatório:**
>   1. **Na AppsFlyer, no menu lateral, selecione** **relatório** > exportação de dados brutos.
>   2. Na lista **Aquisição de usuários (não orgânicos)**, clique em **Instalações** e faça o download do relatório.
> * Se você tiver acesso aos debug, você pode usar a <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/gcd-get-data">Get conversion data API</Anchor> para recuperar os resultados de atribuição para uma instalação específica.

</Accordion>

<Accordion title="Testar atribuição de eventos in-app">

O teste de eventos in-app permite verificar se a receita associada a um evento é exibida e se os eventos in-app são atribuídos ao canal de mídia que gera a instalação.

**Para testar a atribuição de eventos in-app:**

1. Abra o aplicativo e, em seguida, gere alguns eventos in-app.
2. Abra o dashboard de atividades e verifique se os eventos estão lá.  
   Você verá os eventos, a receita (se a receita estiver associada a eles) e o canal de mídia ao qual eles estão associados. Aguarde entre 60 a 70 minutos para que os eventos apareçam no dashboard.

**Dica!** Considere fazer o download do <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview">relatório de dados brutos de eventos in-app</Anchor> para verificar se os eventos foram atribuídos corretamente. Esse relatório leva vários minutos para ser baixado.

**Para fazer o download do relatório:**

1. **Na AppsFlyer, no menu lateral, selecione** **relatório** > exportação de dados brutos.
2. Na seção **Relatórios de dados brutos**, faça o download do relatório de dados brutos de eventos in-app.

</Accordion>

<Accordion title="Testar o OneLink">

O OneLink permite que você configure um único link de atribuição tanto para o iOS quanto para o Android. O OneLink reconhece o dispositivo do usuário e o redireciona para a loja de aplicativos relevante.

Além do mais, o OneLink habilita o deep linking. O deep linking permite que você abra o aplicativo em um destino específico do app enquanto fornece conteúdos personalizados.

Para mais informações, consulte nosso guia de <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#testing">teste de URLs do OneLink</Anchor>.

</Accordion>

<div id="testing-retargeting-using-attribution-links" />

## Testando o retargeting usando links de atribuição

As seções a seguir descrevem os procedimentos que você deve seguir para testar a atribuição de retargeting.

<Accordion title="Sobre testes de retargeting">

A atribuição de retargeting ocorre quando um usuário engaja com uma campanha de retargeting clicando em um link de atribuição de retargeting. Isso resulta em um evento de reatribuição ou reengajamento. Para mais informações, consulte o <Anchor target="_blank" href="/marketers/pt/docs/retargeting-attribution-guide">Guia de atribuição de retargeting</Anchor>.

Os testes de retargeting incluem:

* [**Para reatribuição:**](/docs/testing-the-sdk-integration-for-marketers#test-reattribution) Desinstalação e reinstalação do aplicativo. Depois, verifique no dashboard se uma instalação foi registrada.
* Para reengajamento: Clique em um link de atribuição de retargeting ou em um deep link e verifique se um reengajamento foi atribuído ao canal de mídia correto.

</Accordion>

<Accordion title="Pré-requisitos para executar testes de retargeting">

Antes de executar testes de retargeting, a seguinte configuração é necessária:

* O retargeting deve estar ativado para o aplicativo que você está testando.
* Crie um link específico do aplicativo ou recupere um link personalizado do OneLink. Esses links devem incluir o parâmetro de retargeting.

**Para configurar testes de retargeting:**

1. Habilitar o retargeting nas configurações do aplicativo

   No dashboard do aplicativo, clique em **Configurações do aplicativo** e habilite a opção **Ativar atribuição de retargeting**.

   <Image align="center" alt="Set_Reattribution_window" src="https://files.readme.io/1fe0c8c4add90c75237b0c5c97b6ff26d8f08ff95bd952912ef746fdec2e9f3d-31828933628561.png" />
2. Siga um dos procedimentos abaixo:
   * Crie um link de atribuição específico do aplicativo. Certifique-se de incluir o parâmetro de redirecionamento, `is_retargeting=true`e o ID de publicidade. Para visualizar o GAID, IDFA ou IDFV, siga as instruções <Anchor target="_blank" href="/marketers/pt/docs/registering-test-devices">Registrando um dispositivo de teste</Anchor>.    
     Veja a seguir um exemplo de um link de atribuição que inclui um parâmetro específico do Android como o identificador de dispositivo (GAID). Para mais informações sobre como adicionar outros parâmetros de identificador de dispositivo, como IDFA ou IDFV, consulte <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#parâmetros-específicos-do-ios">Estrutura e parâmetros do link de atribuição</Anchor>.

     ```
     https://app.appsflyer.com/<app_id>?pid=Test&c=Test&is_retargeting=true&advertising_id=<GAID>
     ```
   * Recupere a <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#crie-um-link-do-onelink">URL longa do link personalizado</Anchor> de um <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template#como-criar-templates-do-onelink">template do OneLink</Anchor>. Certifique-se de ativar a <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">campanha de retargeting</Anchor>. A imagem a seguir mostra um exemplo de uma URL longa personalizada: ![Testing_LongLink_en-us.png](https://files.readme.io/19c706b0cc11b83a5cb08d51b3418654c6fa1e597ee7ff9e631db21c33c00b82-31828933632401.png)

Agora você pode prosseguir e testar a reatribuição e o reengajamento.

</Accordion>

<Accordion title="Testar o reengajamento">

**Antes de começar:**

* Siga as [instruções](/docs/testing-the-sdk-integration-for-marketers#prerequisites-to-run-retargeting-tests) para configurar testes de retargeting.
* Certifique-se de que seu dispositivo de teste **não** está registrado.

**Para testar a reatribuição:**

1. Desinstale o aplicativo do dispositivo. Se você acabou de instalar o aplicativo, aguarde alguns minutos.
2. Copie o [link de atribuição](/docs/testing-the-sdk-integration-for-marketers#prerequisites-to-run-retargeting-tests) criado anteriormente, o link de atribuição específico do aplicativo ou o link longo personalizado do template do OneLink, envie-o para o dispositivo de teste e clique no link.

> 📘 **Note**
>
> No iOS, use o iMessage ou o e-mail para enviar o link para o dispositivo. Não cole o link no aplicativo iOS Notes e clique no link. Essa ação pode fazer com que o link quebre.

1. Siga um dos procedimentos abaixo:
   * Se o aplicativo estiver ativo, realize a instalação.
   * Se o aplicativo estiver pendente, instale-o da seguinte forma:
     * Para Android Instale a partir do Android Studio ou de um arquivo APK.
     * **Para iOS:** Instale a partir do TestFlight.
2. Abra o dashboard do aplicativo e, em **Tipo de visualização**, selecione **Retargeting**.
3. Em **Tipo de atribuição**, selecione **Reatribuições**.

   Você deve ver a instalação atribuída ao canal de mídia e à campanha. Aguarde até 30 minutos para que a instalação de retargeting apareça no dashboard.

   <Image align="center" alt="Testing_SDK_Reattribution" src="https://files.readme.io/c5c59709b199262cbefd5cd70ee9fe0db2c788612a8ae6b598c7b2188b696345-small-31828925870609.png" />

> 👍 **Tip**
>
> Veja abaixo formas alternativas de verificar os resultados do teste:
>
> * Se você tiver acesso aos relatórios de dados brutos, faça o download do <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview">relatório de dados brutos de conversões</Anchor>. Esse relatório leva vários minutos para ser baixado. **Para fazer o download do relatório:**
>   1. Na AppsFlyer, no menu lateral, selecione relatório > exportar dados brutos.
>   2. Na lista **Retargeting**, clique em **Conversões (reengajamentos e reatribuições)** e, depois, faça o download do relatório.
> * Se você tiver acesso aos logs de depuração, poderá usar a <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_app-id-2">SDK integration test API</Anchor> para recuperar os resultados da atribuição de uma instalação específica.

</Accordion>

<Accordion title="Testar reatribuição">

**Antes de começar:**

* Siga as [instruções](/docs/testing-the-sdk-integration-for-marketers#prerequisites-to-run-retargeting-tests) para configurar testes de retargeting.
* Para fins de teste, defina o tempo mínimo entre as conversões para **Nenhum**. Isso permite que todas as conversões de reengajamento sejam registradas e atribuídas durante o teste. ![Testing_Reattribution_window](https://files.readme.io/ec8c7c923093dbed0e99aa5ef57d0239217ead5a9db41f42fe4af8a70eb04551-4406211661841.png)
* Certifique-se de que o aplicativo esteja instalado no seu dispositivo de teste e tenha sido inicializado várias vezes. Se você acabou de instalar o aplicativo, aguarde alguns minutos.

**Para testar o reengajamento (deep linking indireto):**

Certifique-se de que seu app esteja configurado para <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">deep linking</Anchor> e, em seguida, siga <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#testing">esse procedimento</Anchor> de teste.

**Para testar o reengajamento (deep linking direto):**

1. Copie o [link de atribuição](/docs/testing-the-sdk-integration-for-marketers#prerequisites-to-run-retargeting-tests) que você criou anteriormente, seja o link de atribuição específico do aplicativo ou o link longo personalizado do template do OneLink.
2. Envie o link para o dispositivo de teste e clique no link.
3. Para abrir o aplicativo, siga um desses procedimentos:

   * Na loja de aplicativos, clique em **Abrir**.
   * Inicialize o aplicativo do seu dispositivo.

   No dashboard, você deve ver um reengajamento atribuído ao canal de mídia e à campanha. Espere até 30 minutos para que o reengajamento apareça.

   <Image align="center" alt="Testing_SDK_Re-engagement" src="https://files.readme.io/5b64b671c8071f871d9835e8df4d89c18d06c85fe996f7227b6ddf429552fccd-small-31828933643153.png" />

**Dica!** Considere fazer o download do relatório de dados brutos de conversões para verificar se o reengajamento foi atribuído ao canal de mídia correto. Esse relatório leva vários minutos para ser baixado.

**Para fazer o download do relatório:**

1. **Na AppsFlyer, no menu lateral, selecione** **relatório** > exportação de dados brutos.
2. Na seção **Retargeting**, faça o download do relatório **Conversões (reengajamentos e reatribuições)**.

</Accordion>

<div id="testing-organic-installs" />

## Testar instalações orgânicas

Recomendamos que você comece testando uma instalação orgânica.

**Para testar uma instalação orgânica:**

1. Instale o aplicativo em um <Anchor target="_blank" href="/marketers/pt/docs/registering-test-devices">dispositivo de teste registrado.</Anchor>
2. Inicie o aplicativo.

O dashboard do aplicativo exibe uma nova instalação orgânica. Aguarde até 30 minutos para que a instalação apareça.

<Image align="center" alt="" src="https://files.readme.io/49c242957324516ba93d6c5ebfa338ec19b05820bcf619d8c39d6f7e4ada9bae-31828925882001.png" />

<div id="testing-ctv" />

## Testando CTV

Casos de teste especiais incluem:

* **Android TV:** o SDK é compatível com Smart TVs baseadas em Android. Um profissional de marketing ou qualquer membro da equipe pode testar esses aplicativos de TV seguindo os procedimentos desse artigo.
* **Apple TV (tvOS):** O SDK é compatível com Apple TVs (tvOS). Um profissional de marketing ou qualquer membro da equipe pode testar esses aplicativos de TV seguindo os procedimentos desse artigo.
* **Aplicativos tvOS não publicados:** é preciso que um profissional de marketing e um desenvolvedor trabalhem juntos (consulte <Anchor target="_blank" href="/marketers/pt/docs/testing-tvos-integration-before-publishing">Testando a integração do tvOS antes de publicar</Anchor>).
* **Amazon Fire TV:** um profissional de marketing pode [testar a integração](/docs/testing-the-sdk-integration-for-marketers#testing-from-the-dashboard) usando o método de teste do Android SDK no dashboard da AppsFlyer. (Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/setting-up-amazon-fire-tv-ad-attribution">a atribuição do Amazon Fire TV</Anchor>).
* **Eventos web PBA:** é preciso que um profissional de marketing e um desenvolvedor trabalhem juntos (consulte <Anchor target="_blank" href="/marketers/pt/docs/test-pba-web-sdk-integration">Testando a integração de SDK de PBA na web</Anchor>).

> 📘 **Note**
>
> Veja também
>
> * Teste de integração de ad networks <Anchor target="_blank" href="/partners/pt/docs/getting-started-onboarding-guide-for-ad-networks">Teste de integração de ad networks</Anchor>

<div id="traits-and-limitations" />

## Especificações e limitações

| Caraterística | Observação: |
| --- | --- |
| /docs/testing-the-sdk-integration-for-marketers#test-reengagement | Ao usar um dispositivo de teste registrado, remova o parâmetro `af_inactivity_window` do link de teste. Caso contrário, a instalação poderá ser atribuída incorretamente como *Orgânica* em vez de ser atribuída ao link de teste. |

<div data-zendesk-anchors="overview=vis%C3%A3o-geral 01H88X11QS2VYFXJGC95TXC6PN=vis%C3%A3o-geral testing-using-the-sdk-integration-tests-page=testes-usando-a-p%C3%A1gina-de-testes-de-integra%C3%A7%C3%A3o-do-sdk h_01HYX9R159XMZKMH1MBMBH9K9J=testes-usando-a-p%C3%A1gina-de-testes-de-integra%C3%A7%C3%A3o-do-sdk prepare-a-test-device=prepare-um-dispositivo-de-teste h_01J9GTS4S2RXJAMYGG6XJ5HFRZ=prepare-um-dispositivo-de-teste perform-the-integration-tests=execute-os-testes-de-integra%C3%A7%C3%A3o h_01J9GTW7RAGZXE7GK5BWGBA7N5=execute-os-testes-de-integra%C3%A7%C3%A3o testing-using-attribution-links=testar-usando-links-de-atribui%C3%A7%C3%A3o 01H88X11QT0WDRW5GZDCR7MZ3D=testar-usando-links-de-atribui%C3%A7%C3%A3o testing-retargeting-using-attribution-links=testando-o-retargeting-usando-links-de-atribui%C3%A7%C3%A3o 01H88X11QTQ94BAJGEE1V11F6X=testando-o-retargeting-usando-links-de-atribui%C3%A7%C3%A3o testing-organic-installs=testar-instala%C3%A7%C3%B5es-org%C3%A2nicas h_01HYX9R1594DD9BEZ6PMV9PJM8=testar-instala%C3%A7%C3%B5es-org%C3%A2nicas Testing%20CTV=testando-ctv 01H88X11QT72F71N49G65BAEAE=testando-ctv traits-and-limitations=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es h_01J6S6HS0H0M6GQ81WGZ3XT0P9=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es" />
