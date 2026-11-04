---
title: Mensure as desinstalações
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-alina-koifman
    - Marketers
    - Mobile Attribution
  created_at: '2021-10-14T08:03:47Z'
  edited_at: '2026-08-19T00:09:51Z'
  id: 4408933557137
  locale: pt
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/pt/articles/4408933557137
---
> **At a glance:** **Resumo:** mensure a taxa de desinstalação do seu aplicativo e identifique quais canais (fontes de mídia, campanhas, criativos e localizações) atraem usuários de alto valor.

<div id="overview" />

## Visão geral

Para entender o valor dos usuários do seu aplicativo, você deve analisar tanto as taxas de instalação quanto de desinstalação. A métrica de desinstalação pode ajudar você a mensurar a performance do seu aplicativo, além de mostrar quando e por que os usuários abandonam seu app.

<div id="how-does-it-work" />

### Como funciona?

1. A AppsFlyer envia uma solicitação de API diária para o Firebase Cloud Messaging (FCM) e o Apple Push Notification Services (APNS).
2. Em seguida, o FCM e o APNS enviam uma notificação push silenciosa para verificar se um aplicativo ainda está instalado em um determinado dispositivo.
3. Uma desinstalação é registrada se a resposta indicar que o aplicativo foi desinstalado (FCM e APNS) ou se não houver qualquer atividade do usuário nos últimos 270 dias (somente FCM).
4. A AppsFlyer atribui a desinstalação à fonte de mídia que inicialmente atraiu o usuário.

> 📘 **Note**
>
> **Nota**
>
> As métricas de desinstalação estão disponíveis no dashboard unificado e na visão de aquisição de usuários.

<div id="how-to-use-uninstall-data" />

## Como usar os dados de desinstalação

Veja alguns exemplos do que você pode descobrir ao mensurar desinstalações e como usar esses dados para otimizar campanhas e aumentar o engajamento do usuários.

<div id="compare-the-quality-of-sources" />

<Accordion title="Comparar a qualidade dos canais">

Ao comparar a qualidade dos usuários adquiridos através de diferentes canais (fontes de mídia, campanhas, criativos e localizações), você pode identificar quais são os canais com as menores taxas de desinstalação e realocar seu orçamento.

> 📘 **Note**
>
> **Exemplo**
>
> Você é um profissional de marketing responsável pelos apps de jogos da PlayIt Gaming International. A empresa acabou de lançar um novo aplicativo e você está executando campanhas em duas fontes de mídia diferentes (Fonte A e Fonte B).
>
> Ao conferir o dashboard, você repara que embora a Fonte A tenha o maior número de instalações (10.390), ela também tem a maior taxa de desinstalação (30%).
>
> Por outro lado, a Fonte B tem 5.949 instalações e a menor taxa de desinstalação (12%).
>
>  ![Taxas de desinstalação.png](https://files.readme.io/36fb732bfe3a63729b1aa0913f2fe3f24df6a7c86adde9f5c2b95424d840dec4-33839423253137.png)
>
> Com base nessas informações, você poderia realocar a maior parte do seu orçamento para a Fonte B e tentar atrair usuários mais engajados.

</Accordion>

<div id="share-uninstall-data-with-ad-networks-for-optimization" />

<Accordion title="Compartilhar dados de desinstalação com ad networks para otimização">

Enviar postbacks de eventos de desinstalação para as ad networks com as quais você trabalha é essencial para otimizar as campanhas de aquisição de usuários. Você pode enviar o evento de desinstalação ao [mapear af\_uninstall para sua ad network](/docs/measure-uninstalls#mapeando-o-evento-de-desinstalação). Assim que o mapeamento estiver completo, um evento será enviado sempre que um usuário desinstalar o aplicativo. As ad networks podem usar essa informação para identificar usuários menos engajados e se concentrar em atrair a atenção dos usuários mais engajados.

> 📘 **Note**
>
> **Caraterística**
>
> Você é um profissional de marketing responsável pelos apps de jogos da PlayIt Gaming International. A Fonte A é uma ad network com a qual você está colaborando no lançamento do seu novo aplicativo Android. Na campanha anterior com a Fonte A, 1.000 novos usuários instalaram seu aplicativo e, posteriormente, 300 desinstalaram. Para a nova campanha, você quer que a Fonte A receba dados de desinstalação. Isso permitirá que a Fonte A resolva rapidamente os desafios de desinstalação.
>
> Com base nas informações da campanha anterior, a Fonte A cria uma lista de exclusão para a campanha, removendo tipos específicos de usuários dos anúncios apresentados na sua nova campanha:
>
> * Usuários que já demonstraram ter um valor menor para seus aplicativos.
> * Usuários que desinstalam frequentemente seus aplicativos.
>
> Isso permite que a Fonte A otimize a segmentação de audiências para garantir que o orçamento da sua campanha não seja desperdiçado com usuários que não precisam ver determinados anúncios.

</Accordion>

<div id="exclude-uninstalls-from-retargeting-campaigns" />

<Accordion title="Excluir desinstalações de campanhas de retargeting">

Em alguns casos, para garantir o compliance com as leis como GDPR e CCPA, talvez seja necessário excluir os usuários que desinstalaram seu aplicativo das campanhas de retargeting. As informações de desinstalação permitem criar listas de exclusão e aplicar medidas de privacidade para proteger os dados e a privacidade dos seus clientes.

Veja os métodos para excluir usuários:

* <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview#user-journey-report-availability">Relatórios de dados brutos:</Anchor> um método manual, no qual você recupera uma lista de usuários desinstalados do relatório de **desinstalações** e cria uma lista de exclusão.
* <Anchor target="_blank" href="/marketers/pt/docs/audiences-guide">Audiences da AppsFlyer:</Anchor> um método automático, no qual você define uma audiência com base em critérios específicos (por exemplo, usuários que **não** desinstalaram seu app). Os usuários que não atendem aos critérios são excluídos da audiência.

> 📘 **Note**
>
> **Exemplo**
>
> Você é um profissional de marketing responsável pelos apps de jogos da PlayIt Gaming International. Você está executando uma campanha de retargeting para um dos seus aplicativos Android e decide usar o Audiences para definir uma audiência de retargeting. Os critérios para sua audiência são:
>
> * Usuários que não desinstalaram o aplicativo.
> * Usuários que não abriram o aplicativo nos últimos 30 dias.
>
> Isso permite criar uma audiência de retargeting mais precisa. Quando sua campanha de retargeting é executada, os anúncios são exibidos apenas para os usuários definidos na sua audiência de retargeting.

</Accordion>

<div id="setting-up-uninstall-measurement" />

## Configurando a mensuração de desinstalações

O processo para configurar a métrica de desinstalação requer a colaboração entre o profissional de marketing e o desenvolvedor. As instruções de implementação variam conforme o sistema operacional do seu aplicativo.

O fluxo de trabalho entre o profissional de marketing e o desenvolvedor funciona assim:

<Tabs>
<Tab title="Android iOS">

| Função | Proprietário |
| --- | --- |
| [Conectar o Firebase Cloud Messaging (FCM) à AppsFlyer](/docs/measure-uninstalls#conectar-o-firebase-cloud-messaging-à-appsflyer-android) | Marketer |
| [Configurar a mensuração de desinstalações na AppsFlyer](/docs/measure-uninstalls#configurar-a-mensuração-de-desinstalações-na-appsflyer) | Marketer |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/uninstall-measurement">Integrar com o SDK</Anchor> | Desenvolvedor Android |
| [Testar a mensuração de desinstalações](/docs/measure-uninstalls#testando-a-mensuração-de-desinstalações) | Marketer |
| [Opcional] [Mapear o evento de desinstalação](/docs/measure-uninstalls#mapeando-o-evento-de-desinstalação) para os parceiros relevantes no dashboard | Marketer |

</Tab>

<Tab title="Exemplo">

| Função | Proprietário |
| --- | --- |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/uninstall-measurement-ios#creating-a-p12-certificate">Gerar certificação P12</Anchor> | Desenvolvedor iOS |
| [Configurar a mensuração de desinstalações na AppsFlyer](/docs/measure-uninstalls#configurar-a-mensuração-de-desinstalações-na-appsflyer) | Marketer |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/uninstall-measurement">Integrar com o SDK</Anchor> | Desenvolvedor iOS |
| [Testar a mensuração de desinstalações](/docs/measure-uninstalls#testando-a-mensuração-de-desinstalações) | Marketer |
| [Opcional] [Mapear o evento de desinstalação](/docs/measure-uninstalls#mapeando-o-evento-de-desinstalação) para os parceiros relevantes no dashboard | Marketer |

</Tab>
</Tabs>

<div id="implementation-procedures" />

## Processos de implementação

A implementação exige que o desenvolvedor mobile integre um mecanismo que responda às notificações push no seu aplicativo. As instruções de implementação variam de acordo com o sistema operacional.

<div id="connect-firebase-cloud-messaging-to-appsflyer-android" />

### Conectar o Firebase Cloud Messaging à AppsFlyer (Android)

A mensuração de desinstalações no Android está disponível ao configurar a mensuração de desinstalações na AppsFlyer e integrar o Firebase Cloud Messaging (FCM) ao seu aplicativo.

<div id="http-v1" />

<Accordion title="HTTP V1">

Para configurar o FCM HTTP V1 para desinstalações:

1. Para obter o ID do projeto:
   1. Acesse o <Anchor target="_blank" href="https://console.firebase.google.com/">console do FCM.</Anchor>
   2. Selecione um projeto.
   3. Acesse a **visão geral do projeto** e selecione **Project settings**.

       ![UninstallFirebase.png](https://files.readme.io/15e74e10daa2f1f1d872f0c8fea274c9819c52c4655baa903728257dd6337e80-33839423254289.png)
   4. Copie o ID do projeto. Você precisará disso em uma etapa posterior do processo.
2. Para ativar a FCM API:
   1. Vá para a aba **Cloud Messaging**.
   2. Certifique-se de que a **Firebase Cloud Messaging API (V1)** esteja **ativada**.
3. **Para atribuir a AppsFlyer à função de desinstalação:**
   1. Acesse a aba **Service accounts**.
   2. Clique em **Manage service account permissions**.   
      Uma nova aba do navegador será aberta no Google Cloud Platform.
   3. No menu lateral, selecione **Roles**.
   4. Clique em **+Create role**.
   5. Preencha da seguinte forma:
      * Título: Escreva **Desinstalações da AppsFlyer**.
      * ID: Insira `af_uninstalls`.
      * Etapa de lançamento da função: Selecione **General availability**.
   6. Clique em **Add permissions**.
   7. Em <Image alt="adjusted.png" src="https://files.readme.io/c9fc0c6358ff89e1004ac1ab348a4b286d58c8a5cbe024aeb5c637136f3a67ac-33839382508049.png" width="20px" /> **Filter**, selecione a permissão **cloudmessaging.messages.create**.

       ![Filtro de permissão do Cloud Messaging](https://files.readme.io/255f5cf42ba1b07cae905ec0acbe6459303c3bd5b03f2d36e1ac3f9606fbb229-33839382512145.png)
   8. Clique em **Add** e depois em **Create**.
4. **Para atribuir a AppsFlyer à função de desinstalação do FCM:**
   1. No menu lateral, selecione **IAM**.
   2. Abra a aba **PERMISSIONS** -> **VIEW BY PRINCIPALS**.
   3. Clique em **Grant Access**.
   4. Em **Add Principals** -> **New principals**, insira **af-uninstalls-tracking@af-uninstalls-tracking.iam.gserviceaccount.com**.
   5. Em **Assign roles** -> **Role**, selecione a função personalizada que você criou (**Desinstalações da AppsFlyer**).
   6. Clique em **Save**.   
      A conta de serviço da AppsFlyer recebeu a função de desinstalações.

      > 📘 **Note**
      >
      > **Nota**
      >
      > A AppsFlyer utiliza notificações push silenciosas apenas para mensurar desinstalações ou identificar usuários inativos.


</Accordion>

<div id="legacy-http" />

<Accordion title="[Descontinuado] HTTP legado">

> 🚧 **Important**
>
> **Importante!**
>
> A API HTTP antiga foi descontinuada pelo Firebase em 20 de junho de 2023 e foi removida em 21 de junho de 2024. Se você ainda estiver usando a API antiga, recomendamos que mude para a [API HTTP V1](/docs/measure-uninstalls#http-v1). <Anchor target="_blank" href="https://firebase.google.com/docs/cloud-messaging/http-server-ref">Saiba mais</Anchor>

A mensuração de desinstalações com o Firebase Messaging é compatível com o Android SDK V4.7.0+.

**Para obter a chave do servidor do Firebase:**

1. Crie um projeto de aplicativo Android no Firebase (se ainda não fez isso) ou migre seu projeto do **Google Developer Console** (siga as instruções disponíveis). Para mais informações, veja <Anchor target="_blank" href="https://firebase.google.com/docs/cloud-messaging/android/client">Firebase</Anchor>.
2. Abra o <Anchor target="_blank" href="https://console.firebase.google.com">Console do Firebase</Anchor>.
3. No Console do Firebase, explore as configurações do projeto (clique no ícone de engrenagem ao lado de “Project Overview” no painel à esquerda da página).

    ![firebase_cloud_messaging_server_key.png](https://files.readme.io/4e31c02a1bea013c823b0148ba1704d4492f66d04e23f0e13e00a9c0c22d286c-33839382513041.png)
4. No aba “Cloud Messaging”, você verá duas chaves de servidor.
5. Copie a **chave do servidor**.

</Accordion>

<div id="configure-uninstall-measurement-in-appsflyer" />

### Configurar a mensuração de desinstalações na AppsFlyer

<Tabs>
<Tab title="Android / iOS">

**Pré-requisito:** O desenvolvedor Android deve concluir as <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/uninstall-measurement">instruções de integração</Anchor>.

Para configurar a mensuração de desinstalações na AppsFlyer:

1. Na AppsFlyer, no menu lateral, selecione **Settings** > **App Settings**.
2. Se necessário, ative a **mensuração de desinstalações**.
3. Selecione **HTTP V1 e insira o ID do projeto**.

    ![DesinstalarHTTPV1.png](https://files.readme.io/80d13e47ea7ae1585d2ecc0e2f7210572e47dba936557c8e96314e49b0d738d8-33839423258641.png)
4. Clique em **Test connection**.  
   Você verá uma mensagem de confirmação.

   > 📘 **Note**
   >
   > **Observação**
   >
   > Se você receber a mensagem de erro **Project ID is invalid or access permissions are missing**, depois de testar sua conexão, verifique suas configurações de conexão no FCM. Para mais informações, consulte [Conectar o Firebase Cloud Messaging à AppsFlyer (Android)](#conectar-o-firebase-cloud-messaging-à-appsflyer-android) neste artigo.  
   > Certifique-se de que as permissões e o ID do projeto estejam definidos corretamente.

5. Clique em **Save settings**.

</Tab>

<Tab title="/docs/ctv-pc-and-console-platform-attribution-concepts">

**Pré-requisito**: o desenvolvedor iOS deve concluir as <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/uninstall-measurement">instruções de integração</Anchor>.

**Para configurar a mensuração de desinstalações na AppsFlyer:**

1. Solicite o arquivo P12 ao seu desenvolvedor.
2. Na AppsFlyer, no menu lateral, selecione **Settings** > **App Settings**.
3. Role para baixo até à seção de desinstalação.
4. Ative a **mensuração de desinstalação**.

    ![Desinstalar_iOS_p2.png](https://files.readme.io/3f9de3ebe6099886fa9bc210bd6e491ba91e8ff2c890c980f66c4d48398a597c-33839423260561.png)
5. Clique no ícone de upload e selecione o arquivo P12.
6. [Opcional] Se a certificação P12 estiver protegida, insira a senha.
7. Clique em **Validate** para enviar a certificação à AppsFlyer.
8. Clique em **Save Settings**.

</Tab>
</Tabs>

<div id="testing-uninstall-measurement" />

## Testando a mensuração de desinstalações

Assim que os processos de implementação estiverem concluídos, você pode instalar e desinstalar o aplicativo para verificar se as desinstalações são registradas corretamente. As desinstalações e suas respectivas taxas são apresentadas no dashboard de visão geral.

<Tabs>
<Tab title="Importante!">

Faça esse teste em aplicativos que estejam:

* Na Google Play Store
* Pendentes (não listados na Google Play Store)
* Disponíveis através de download direto
* Em lojas de aplicativos alternativas

Ao testar aplicativos Android, lembre-se:

* A mensuração de desinstalações é processada <Anchor target="_blank" href="/marketers/pt/docs/about-data-freshness-and-timezone-support#uninstalls">diariamente</Anchor>. Um evento de desinstalação é registrado no prazo de 24 horas. No entanto, se o aplicativo for reinstalado nesse período, o evento não será contabilizado.
* **Os eventos de desinstalação demoram até 48 horas para aparecer** nos <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview">relatórios de dados brutos</Anchor> e no dashboard da AppsFlyer (Relatório de performance agregada).

</Tab>

<Tab title="https://files.readme.io/4e31c02a1bea013c823b0148ba1704d4492f66d04e23f0e13e00a9c0c22d286c-33839382513041.png">

Ao testar aplicativos iOS, lembre-se:

* As desinstalações não aparecem imediatamente no dashboard da AppsFlyer. Devido ao Apple Push Notification Service, o tempo mínimo para que as desinstalações apareçam no dashboard é de 9 dias. A AppsFlyer atualiza e agrega métricas de desinstalação a cada 24 horas.

  > 📘 **Note**
  >
  > **Exemplo**
  >
  > * Dia 1: Um usuário instala seu aplicativo.
  > * Dia 4: Um usuário desinstala seu aplicativo.
  > * Dia 12: O APNS informa a remoção do aplicativo 8 dias após a desinstalação.
  > * Dia 13: Os dados da desinstalação aparecem no dashboard da AppsFlyer e nos dados brutos.

* Se você estiver testando uma versão do aplicativo, certifique-se de usar o ambiente de sandbox. Veja as instruções do desenvolvedor para o [processo de desinstalação no sandbox](https://dev.appsflyer.com/hc/docs/uninstall-measurement-ios#testing-uninstall-measurement).

</Tab>
</Tabs>

<div id="mapping-the-uninstall-event" />

## Mapeando o evento de desinstalação

 ![Uninstall_event_postback.png](https://files.readme.io/9c3c7f3fd330720d4f6f41fdf509c5af00d042291c1350ab83a1951464ac8e8f-33839423261713.png) 

Para compartilhar dados de desinstalação com uma ad network, é necessário mapear o <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">evento af\_uninstall</Anchor> para um parceiro. Ao contrário dos postbacks para eventos in-app tradicionais, o evento de desinstalação não é enviado em tempo real. O horário do evento informado representa o momento em que a AppsFlyer identificou que o aplicativo foi desinstalado, e não a própria desinstalação.

Lembre-se:

* A AppsFlyer só pode enviar o postback se o evento realmente ocorrer e for registrado por ela.
* Caso você não veja as desinstalações no dashboard de visão geral ou no relatório de dados brutos, isso significa que os postbacks de desinstalação não foram enviados para o parceiro, mesmo que o evento **af\_uninstall** tenha sido mapeado.

<div id="limitations" />

#### Limitações

* Eventos de desinstalação não são incluídos nos relatórios de postback de eventos in-app.
* Todos os parceiros aceitam o evento **af\_uninstall**. Se você deseja mapeá-lo para um parceiro, mas o evento não estiver disponível, entre em contato com seu parceiro ou mande um e-mail para hello@appsflyer.com.

<div id="turning-off-uninstall-measurement" />

## Desativando a mensuração de desinstalações

<Tabs>
<Tab title="Android iOS">

Se uma chave de servidor do Firebase/GCM for disponibilizada, a mensuração de desinstalações do aplicativo é ativada por padrão. Os proprietários dos aplicativos podem desativar essa funcionalidade através do dashboard.

</Tab>

<Tab title="Android iOS">

Se uma certificação P12 for disponibilizada e validada, a mensuração de desinstalações do aplicativo é ativada por padrão. Os proprietários dos aplicativos podem desativar essa funcionalidade através do dashboard.

</Tab>
</Tabs>

**Observação:** Para que uma desinstalação seja informada, a opção de **Enable uninstall measurement** deve estar habilitada no momento em que o aplicativo é instalado. As instalações que ocorrem quando a opção **Enable uninstall measurement** está desabilitada não são informadas.

<div id="to-turn-off-uninstall-measurement" />

#### **Para desativar a mensuração de desinstalação**:

1. Na AppsFlyer, no menu lateral, selecione **Settings** > **App Settings**.
2. Acesse **Attribution** > **Uninstall measurement** e desative **Enable uninstall measurement**.

<div id="traits-and-limitations" />

<Accordion title="Características e limitações">

| Caraterística | Observações |
| --- | --- |
| CLIQUE | O CUID não é enviado em postbacks de desinstalação. |

</Accordion>

<div data-zendesk-anchors="overview=vis%C3%A3o-geral h_01HB8CXQ4824V2WEPYGK8YS4DC=vis%C3%A3o-geral how-does-it-work=como-funciona h_01HB8CXQ48JEJECC1HR79DXCRK=como-funciona how-to-use-uninstall-data=como-usar-os-dados-de-desinstala%C3%A7%C3%A3o h_01HB8CXQ48E2SRN95MH4E2H7ZH=como-usar-os-dados-de-desinstala%C3%A7%C3%A3o h_01HB8CXQ48HX9RH50G45FZMZTK=compare-the-quality-of-sources h_01HB8CXQ488E22GPCEBE69VQ3M=share-uninstall-data-with-ad-networks-for-optimization h_01HB8CXQ48JTET73GH0QQBX5HF=exclude-uninstalls-from-retargeting-campaigns setting-up-uninstall-measurement=configurando-a-mensura%C3%A7%C3%A3o-de-desinstala%C3%A7%C3%B5es h_01HB8CXQ4810HTB45FAS5ZVRHF=configurando-a-mensura%C3%A7%C3%A3o-de-desinstala%C3%A7%C3%B5es implementation-procedures=processos-de-implementa%C3%A7%C3%A3o h_01HB8CXQ489HRF72VRZ4G532GX=processos-de-implementa%C3%A7%C3%A3o connect-firebase-cloud-messaging-to-appsflyer-android=conectar-o-firebase-cloud-messaging-%C3%A0-appsflyer-android h_01HB8CXQ48ZD5Y0RKTG1W51TKW=conectar-o-firebase-cloud-messaging-%C3%A0-appsflyer-android h_01HB8CXQ4865MNVG0VERSNSE3F=http-v1 h_01HB8CXQ48H079WQ6Q6G0XSQC7=legacy-http configure-uninstall-measurement-in-appsflyer=configurar-a-mensura%C3%A7%C3%A3o-de-desinstala%C3%A7%C3%B5es-na-appsflyer h_01HB8CXQ48CVA9B8B78W0H357C=configurar-a-mensura%C3%A7%C3%A3o-de-desinstala%C3%A7%C3%B5es-na-appsflyer testing-uninstall-measurement=testando-a-mensura%C3%A7%C3%A3o-de-desinstala%C3%A7%C3%B5es h_01HB8CXQ48SW2TT5Z85XD3XWT6=testando-a-mensura%C3%A7%C3%A3o-de-desinstala%C3%A7%C3%B5es mapping-the-uninstall-event=mapeando-o-evento-de-desinstala%C3%A7%C3%A3o h_01HB8CXQ499ABX9ZGDFB1VAE8W=mapeando-o-evento-de-desinstala%C3%A7%C3%A3o limitations=limita%C3%A7%C3%B5es h_01HB8CXQ49F2ARQTEV8Q032P9V=limita%C3%A7%C3%B5es turning-off-uninstall-measurement=desativando-a-mensura%C3%A7%C3%A3o-de-desinstala%C3%A7%C3%B5es h_01HB8CXQ49Y5NCG7GK93HXHYMD=desativando-a-mensura%C3%A7%C3%A3o-de-desinstala%C3%A7%C3%B5es to-turn-off-uninstall-measurement=para-desativar-a-mensura%C3%A7%C3%A3o-de-desinstala%C3%A7%C3%A3o h_01HB8CXQ49WXZS4M6CK5XG1BCX=para-desativar-a-mensura%C3%A7%C3%A3o-de-desinstala%C3%A7%C3%A3o h_01HB8CXQ4916CJ9NDZWGWQHKSA=traits-and-limitations" />
