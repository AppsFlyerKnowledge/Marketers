---
title: Google Ads (AdWords) – Configuração da integração para anunciantes
metadata:
  keywords:
    - Integration
    - Google AdWords
    - Configuration
    - google
    - migration
    - Advertisers
    - google ads configuration
    - ads
    - google ads
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2017-05-17T19:16:15Z'
  edited_at: '2026-11-02T01:14:23Z'
  id: 115002504686
  locale: pt
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/pt/articles/115002504686
---
> **At a glance:** Integre a sua conta Google Ads com a AppsFlyer para visualizar dados de atribuição de todas as suas campanhas.

Configure a integração do Google Ads na AppsFlyer para mensurar e atribuir instalações e eventos in-app das suas campanhas. Na AppsFlyer, essa integração é chamada de `googleadwords_int` e os resultados de atribuição são registrados sob a fonte de mídia `googleadwords_int`.

<div id="google-ads-attribution-flow-with-advanced-data-sharing" />

## Fluxo de atribuição do Google Ads com compartilhamento avançado de dados

![Google ads attribution flow.png](https://files.readme.io/1c49e06e48658a8cb60ae6a9e9a83c0fad751766f3d4ce9c6afdd041fb5e8579-small-38644882427537.png)

1. A AppsFlyer envia eventos de instalação para o Google, como de costume. Se a opção **Compartilhamento avançado de dados** estiver ATIVADA, as instalações são enviadas com ou sem um Device ID. Quando estiver DESATIVADA, as instalações são enviadas **apenas quando o Device ID está disponível**.
2. O Google tenta reivindicar a instalação, seja por meio de um método determinístico (ID matching, usando o Device ID quando disponível) ou uma não determinístico (quando o Device ID não está disponível), ou seja, utilizando modelagem probabilística.
3. Em ambos os casos, o Google responde à AppsFlyer com uma reivindicação, seja determinística ou não determinística.
4. A AppsFlyer valida a reivindicação usando a própria modelagem probabilística. Apenas reivindicações validadas são aceitas.
5. Após a validação, a reivindicação do Google (se aceita) entra na etapa de decisão de atribuição, em que a AppsFlyer a compara com outros possíveis candidatos à atribuição (por exemplo, outras SRNs, networks baseadas em cliques, orgânico). A instalação é atribuída à fonte vencedora com base na lógica de atribuição e nas regras de prioridade da AppsFlyer.
6. Se a reivindicação for aceita e selecionada como a candidata vencedora, a instalação é atribuída ao Google. Nos relatórios de dados brutos, as reivindicações determinísticas mostram <Anchor target="_blank" href="/marketers/pt/docs/raw-data-field-dictionary#attribution::cecc12c5">match\_type</Anchor> de `srn`, enquanto reivindicações não determinísticas mostram um tipo de correspondência “`probabilistic`”.

<div id="configuring-google-ads-attribution-for-advertisers" />

## Configuração da atribuição do Google Ads para anunciantes

Para começar a atribuir campanhas do Google Ads com a AppsFlyer, siga estes passos:

<Accordion title="Passo 1: Verifique os pré-requisitos do ICM">

Certifique-se de que os requisitos abaixo sejam atendidos para oferecer suporte às reivindicações de instalação do Google PMOD no iOS via AppsFlyer. Esse passo é necessário para ativar a mensuração on-device (ODM) do Google. Para Android, nenhuma atualização de SDK é necessária.

1. [Atualize o SDK da AppsFlyer para iOS](https://dev.appsflyer.com/hc/docs/install-ios-sdk) para a **versão 6.17.9 ou superior** (nenhuma configuração adicional é necessária).
2. Para atualizar o SDK do Google:
   * Atualize o SDK do **Firebase para iOS** para a **versão 11.14.0 ou superior.** Para mais informações, consulte [a documentação do Google](https://github.com/firebase/firebase-ios-sdk/releases). **OU**
   * Atualize o **SDK do Google ODM.** Para mais informações, consulte [a documentação do Firebase](https://support.google.com/google-ads/answer/16384720).
3. Certifique-se de que <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-knowledge-base-glossary#idfv">o IDFV</Anchor> seja enviado à AppsFlyer a cada abertura de aplicativo ou evento in-app.
4. Certifique-se de que o endereço IP seja enviado à AppsFlyer com cada evento de abertura de aplicativo. Quando o mascaramento de IP está configurado para o aplicativo, o ICM pode não funcionar.

</Accordion>

<Accordion title="Passo 2: Crie o Google Ads Link ID (obrigatório)">

Para criar um link ID, é necessário **acesso de administrador** à conta do Google. Siga os passos abaixo ou a <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7365001?hl=en">documentação do Google</Anchor>.

1. Faça o login na sua conta de administrador do Google Ads.
2. No menu superior, clique em **Ferramentas e Definições**.
3. No menu **Configuração**, selecione **Gestor de Dados** e clique em **+ Conectar Produto**.
4. Na barra de pesquisa **Fontes de Dados**, escreva "App analytics third-party", selecione-o e clique em **Continuar**.
5. Clique em **Criar link ID**.
6. Escolha **AppsFlyer** como o seu fornecedor de app analytics.
7. Selecione a plataforma, Android ou iOS.
8. Procure o seu app e selecione-o.
9. Clique em **Criar link ID**.

</Accordion>

<Accordion title="Passo 3: Configure o Google Ads na AppsFlyer (obrigatório)">

**(Qualquer membro da conta AppsFlyer)**

1. Na AppsFlyer, no menu lateral, selecione a aba **Colaborar** > **Integrações de parceiros > Marketplace** .
2. Procure por **Google Ads**.
3. Clique em I**ntegrate**. Você será direcionado para a página de configuração da integração.
4. Na aba **Integração**, clique em Ativar parceiro.  
   **Atenção:** O toggle deve permanecer ligado (<Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">ativado</Anchor>) enquanto você trabalhar com o parceiro.
5. Cole o **link ID** que você copiou no passo anterior.
6. Decida se você deseja ou não ativar a opção <Anchor target="_blank" href="/marketers/pt/docs/support-google-eu-consent-policy#do-i-have-control-over-consent-data-for-nonue-users">**Usuários fora da UE**</Anchor>.

   <Image alt="non eu usrs.png" src="https://files.readme.io/fb141c0bd8885facd6574f3e73c5ec8ae8beb596de7fdf3dd8aed9d4e82686dd-22352319155985.png" width="557px" />
7. Ative ou desative o **compartilhamento avançado de dados**. Quando ativado, o Google Ads recebe postbacks e eventos com identificadores a nível de dispositivo para todos os dispositivos, incluindo aqueles que não disponibilizaram o advertising ID (IDFA ou Google advertising ID).

   Além disso, quando o **compartilhamento avançado de dados** está ativado, a AppsFlyer atribui esses eventos. Quando desativado, apenas postbacks e eventos de dispositivos com IDFA são enviados e atribuídos.
8. Configurando a **atribuição de instalação**:
   1. Defina a **Janela lookback de click-through**.  
      Selecione as unidades da janela de lookback (horas ou dias) e defina a barra deslizante para o valor desejado. Recomendamos a definição da janela de lookback para 30 dias para corresponder ao período do Google Ads.
   2. [Opcional] se você executar campanhas de pré-registro para aplicativos Android, defina a **janela de lookback de campanha de pré-registro** (o padrão é 90 dias). Esse cursor determina a janela de lookback para a atribuição de instalações a campanhas de pré-registro.
   3. Ative a **atribuição de view-through de instalação**.
   4. Selecione as unidades da janela de lookback (horas ou dias) e defina a barra deslizante para o valor desejado. Recomendamos definir a janela de lookback de view-through para 1 dia para alinhar com o Google Ads.  
      **Atenção:** O Google não envia notificações de impressões para aplicações iOS. O toggle de atribuição de view-through de instalação e o slider da janela de lookback não são mais relevantes para aplicativos do iOS.

      ![](https://files.readme.io/a6f05b9f92abf6dfdbaafc248c0381bfe063086daa10727dc088d484c1b38f0b-30759221879825.png)
9. A opção **atribuição de reinstalação** é ativada por padrão para novas integrações. A atribuição de reinstalação permite que você mensure usuários que reinstalam seu aplicativo na janela de reatribuição.

   Não é necessária uma configuração separada da janela de lookback, porque a reinstalação de atribuição utiliza os valores das suas configurações de atribuição de instalação. Para mais informações, leia este artigo sobre a <Anchor target="_blank" href="/marketers/pt/docs/measure-reinstalls">mensuração de reinstalações</Anchor>.

   <div id="important" />

   > 🚧 **Importante!**
   >
   > Os dados de conversão de reinstalação são **apresentados como session\_start** no painel do Google Ads. Na AppsFlyer, isso é atribuído e visto como uma reatribuição.

10. Configure a **atribuição de reengajamento**:
    1. <Anchor target="_blank" href="/marketers/pt/docs/app-settings#reengagement-attribution">Habilite o retargeting nas configurações do aplicativo</Anchor>.
    2. Ative a atribuição de reengajamento nas configurações de integração do Google Ads.
    3. Configure a **janela de lookback de reengajamento por click-through**, que é o período de tempo que se inicia com o clique no anúncio, durante o qual o aplicativo deve ser iniciado para que o clique seja registrado como um reengajamento. Selecione uma janela de lookback em horas ou dias e configure a barra deslizante para o valor desejado.
    4. Habilite a **atribuição de reengajamento para view-through**.  
       **Atenção:** O Google não envia notificações de impressões para aplicações iOS. O toggle de atribuição de view-through de reengajamento e o slider da janela de lookback não são mais relevantes para aplicativos do iOS.
    5. Defina a **janela de lookback de reengajamento para view-through**, que é o período de tempo que se inicia com a impressão do anúncio, durante a qual o aplicativo deve ser iniciado para que a impressão seja registrada como um reengajamento. Selecione uma janela de lookback em horas ou dias e configure a barra deslizante para o valor desejado.
    6. Defina a **janela de reengajamento**. Esse é o período em que os eventos in-app do usuário são atribuídos à fonte de mídia de retargeting após um clique ou uma impressão. Você pode definir o valor em dias (1 a 90), horas (até 23) ou até mesmo vitalício. O padrão é 30 dias.

       ![](https://files.readme.io/221a5489e91a15f1d9e4db9ab8f7cbff9e47dc1b50b0f7b43323096b26008870-30759261966225.png)
11. Se você tiver um <Anchor target="_blank" href="https://support.google.com/google-ads/answer/2402582?hl=en">asset de aplicativo iOS do Google Ads</Anchor> (anteriormente conhecido como extensão de aplicativo):  
    Para obter atribuições a partir do link do anúncio, vá para a aba <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">**Link de atribuição**</Anchor> , crie um link de atribuição de plataforma única na AppsFlyer e insira-o no asset do app do Google Ads.  
    **Atenção:** Certifique-se de adicionar um nome de campanha estático (obrigatório).

    ![](https://files.readme.io/6b7513829fb3abbaab75942e3612760f39f6ae6502064eac1f31b0783a63e95b-30759221884561.png)
12. Acesse a aba **Custo**.
13. Ative **Obter dados de custos, cliques e impressões**.
14. Clique no botão **Conectar Google Ads** e faça login na sua conta Google para obter todos os custos da sua campanha do Google Ads na AppsFlyer. <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-cost-and-ad-revenue">Mais detalhes aqui</Anchor>.
15. Clique em **Salvar**.

<div id="stop" />

> ❗️ **Atenção!**
>
> * Se você precisar mapear seus eventos in-app para o Google Ads, primeiro siga a [etapa 5](#h_01HACTC1H50DDS3WCZ9DCHKN0P).

</Accordion>

<Accordion title="Passo 4: Verifique as conversões do seu aplicativo (recomendado)">

<div id="important-1" />

> 🚧 **Importante!**
>
> Para que o Google Ads registre as suas novas conversões, você deve **iniciar o seu app e realizar os eventos mapeados** pelo menos uma vez. Para testar aplicativos iOS, você deve coletar o IDFA para ver o evento. Pode demorar até seis horas para que as conversões do evento sejam adicionadas à fila. Depois que forem adicionadas, as novas conversões mudam do status “No recent conversion” para “recording conversion”.

Essa etapa requer **o administrador da conta do Google** para criar um link ID.

Quando a AppsFlyer envia dados de conversão para qualquer evento que ainda não esteja configurado na sua conta do Google Ads, incluindo `first_open`, `session_start` e seus eventos in-app, o Google Ads o adiciona automaticamente à lista de conversões. Para mais informações, consulte <Anchor target="_blank" href="https://support.google.com/google-ads/answer/17086025?hl=en">Sobre ações de conversão de aplicativo ativadas automaticamente</Anchor>.

**Para verificar as conversões do seu aplicativo:**

1. No Google Ads, acesse a página **Conversions** > **Summary**.
2. Verifique se o evento `first_open` aparece na lista de eventos de conversão de terceiros para todos os seus aplicativos. Esse evento é necessário para a mensuração de instalação.
3. Se você pretende mensurar reengajamentos com o Google, verifique se o evento `session_start` também aparece na lista.
4. Verifique se cada evento in-app que você quer mensurar com o Google aparece na lista.

**Se um evento estiver ausente, oculto ou removido, importe-o manualmente:**

1. Na página **Conversions** > **Summary**, clique em **View all conversion actions**. O filtro **Status** é apresentado.
2. Clique em **Status** e selecione Todos para visualizar todos os eventos, incluindo os desativados e removidos.
3. Se o evento ainda não aparecer, importe-o seguindo as etapas descritas na <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7382633?sjid=11699141105296914680-EU">documentação de ajuda do Google Ads</Anchor>.

> 📘 **Atenção**
>
> Se o identificador do evento do parceiro no Google Ads tiver sido alterado ou estiver rotulado como PERSONALIZADO, enquanto o nome do evento correspondente tiver sido modificado na AppsFlyer, você terá de importar novamente os dados.

Certifique-se de que a configuração "incluir nas conversões" está alinhada com os objetivos da sua campanha no Google Ads. Para mais informações, fale com seu representante do Google ou veja <Anchor target="_blank" href="https://support.google.com/google-ads/answer/4677036?hl=en&co=ADWORDS.IsAWNCustomer=false">a documentação do Google sobre as configurações de conversão</Anchor>.

Parabéns! Agora você está mensurando campanhas mobile do Google Ads com a AppsFlyer!

</Accordion>

<Accordion title="Passo 5: Mapeie seus eventos in-app (recomendado)">

**(Qualquer membro associado à conta da AppsFlyer)**

![Os postbacks seguem o](https://files.readme.io/fbeef1b9d6f4462750d849878045d31b4a6614a9f36d20cd9c6f69d91a34f65a-30759221886609.png)

1. Vá até a aba **Integração** e desça até a seção **Postbacks de eventos in-app**.

   <div id="note-1" />

   > 📘 **Importante!**
   >
   > Ao ativar o mapeamento de eventos in-app do Google Ads para um aplicativo **pela primeira vez:**
   >
   > * O evento **af\_app\_open** é automaticamente definido e mapeado para **session\_start** (se não, acrescente-o manualmente).
   > * Em **para usuários de**, você deve selecionar **Todas as fontes de mídia, incluindo orgânicas** para cada evento para permitir que o Google Ads receba estes eventos. Após a integração ter sido definida com sucesso, você poderá alterar esta seleção para qualquer evento.

2. Ative **Postbacks de eventos in-app.**
3. Clique em **Adicionar evento** para adicionar um SDK ou evento servidor para servidor à lista.
4. Preencha os seguintes parâmetros:

| Nome do parâmetro | Descrição |
| --- | --- |
| **Evento AppsFlyer** | O nome do evento, conforme recebido do SDK integrado no aplicativo ou de eventos de servidor para servidor.<br />**Dica**: não encontrou o evento que está procurando?<ul><li>Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente.</li><li>Digite-o em **Evento da AppsFlyer**, depois clique em **Criar personalizado**. Leia mais sobre o <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#eventos-personalizados">mapeamento de eventos personalizados</Anchor>.</li></ul> |
| **mapeado para evento do parceiro** | O nome ou ID exclusivo de cada evento, conforme definido no Google Ads Selecione o evento AppsFlyer predefinido mais adequado. Selecione o evento AppsFlyer predefinido mais adequado. |
| **para usuários de** | Selecione a opção de envio para o evento:<ul><li>**Apenas este parceiro**: Envie postbacks apenas quando o evento for atribuído ao Google Ads.</li><li>**Todas as fontes de mídia, inclusive orgânicas** Envie postbacks para eventos atribuídos a qualquer parceiro, incluindo eventos orgânicos.</li></ul> |
| **incluindo** | <ul><li>**Sem dados (padrão)**: Envie somente o evento em si, sem o valor do evento.</li><li>**Valores e receitas**: Envie todos os parâmetros do evento, **incluindo** o valor da receita (se existir no evento).</li><li>**Valores sem receita**: Envie todos os parâmetros **exceto** o valor de receita.</li></ul> |

5. Clique em **Salvar integração.**
6. Após salvar a integração, enquanto permanece na página de configuração, você pode integrar mais aplicativos com o parceiro.
   1. No canto superior esquerdo, abaixo do nome do parceiro, clique no nome do aplicativo para abrir a lista de apps.
   2. Selecione um aplicativo diferente a partir da lista suspensa.
   3. Repita as etapas de integração para o aplicativo selecionado.

</Accordion>

<div id="tip" />

> 👍 **Observação**
>
> A integração de API do Google Ads inclui automaticamente o recurso de remarketing do Google Ads. Ao concluir esta integração e enviar eventos para o Google Ads, poderá criar listas de públicos-alvo para remarketing, sem necessidade de integrações adicionais.

<div id="granting-permissions-to-google-ads-team-members" />

## Como conceder permissões aos membros da equipe do Google Ads

Você pode conceder <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões ao Google Ads para acessar determinados dados em sua conta.</Anchor> Você pode fazer isso na sua página de configuração do Google Ads na aba Permissão para cada um de seus aplicativos.

Para obter essas permissões e acessar seu aplicativo, seu representante do Google Ads deve ser um membro da equipe da conta de parceiro do Google Ads na AppsFlyer.

Devido aos seus requisitos de privacidade, o Google pode adicionar novos membros de equipe à sua conta de parceiro da AppsFlyer somente quando solicitado explicitamente por um anunciante.

Para conceder a um membro da equipe do Google Ads acesso ao seu aplicativo, faça o seguinte:

1. Preencha e envie <Anchor target="_blank" href="https://docs.google.com/forms/d/e/1FAIpQLSfJmwEPxy4bXw0mEsKfJ3D5dZmRZgHS3LCiyoEFsZRos0jWIQ/viewform">este formulário</Anchor> para solicitar que seu gerente de conta seja adicionado à conta de parceiro do Google na AppsFlyer.
2. Aguarde a confirmação do Google Ads de que seu gerente de conta do GA foi adicionado.
3. Acesse **Configuração** > **Integrações ativas** > **Google Ads** > **Permissões** e adicione o e-mail do gerente de sua conta à lista de membros da equipe.
4. Ative as permissões que você deseja conceder ao gerente da sua conta do Google Ads.

Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">como dar permissões a ad networks</Anchor>.

<div id="enabling-google-ads-attribution-for-agencies" />

## Ativação da atribuição do Google Ads para agências

A AppsFlyer oferece suporte para configurações de agência com o Google Ads. É essencial que o anunciante e a agência tenham contas separadas no Google Ads para permitir que a AppsFlyer atribua os dados corretamente. Para mais detalhes, consulte <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-integration-setup-for-agencies">Integração do Google Ads para agências</Anchor>.

<div id="running-with-multiple-google-ads-accounts" />

## Trabalhar com várias contas do Google Ads

A AppsFlyer oferece suporte ao funcionamento com várias contas do Google Ads para o mesmo aplicativo. Isso é realizado pelo compartilhamento do Link ID no Google Ads e pela importação dos eventos para cada conta do Google Ads.

Para mais detalhes, veja <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7365001">a documentação do Google sobre como compartilhar seu Link ID do Google Ads</Anchor>.

<div id="ios-app-campaigns" />

## Campanhas de aplicativos para iOS

**Nota**: Esta seção aplica-se a campanhas de instalação de aplicações e **não** a campanhas de envolvimento.

Em 27 de janeiro de 2021, <Anchor target="_blank" href="https://blog.google/products/ads-commerce/preparing-developers-and-advertisers-for-policy-updates/">o Google anunciou atualizações em suas políticas</Anchor> para acomodar o lançamento do iOS 14.

Desde a ativação da ATT, os aplicativos do Google para iOS não exibem a notificação da ATT e, portanto, os produtos do Google Ads <Anchor target="_blank" href="https://support.google.com/google-ads/answer/10417364">pararam de usar</Anchor> identificadores de dispositivo (IDFA) que se enquadram na ATT, com a exceção do app YouTube, que tem suporte para o prompt da ATT.

Para preservar a otimização de relatórios e campanhas, o Google expandiu as conversões modeladas para o tráfego do iOS 14+.

Como as conversões modeladas não dependem de IDs de dispositivos, a partir da versão iOS14.5, a lógica de inventário da campanha de aplicativos de instalação do iOS empregada pelo Google é a seguinte:

* O inventário de ACI Search do iOS não é atribuído por Device ID. Essa decisão está de acordo com a política do Google de 24 de janeiro de 2020.
* O inventário de ACI Display do iOS pode ser atribuído quando um Device ID está presente, desde que tanto o aplicativo do anunciante quanto o aplicativo do publisher tenham o consentimento do usuário.
* Qualquer campanha ACI do iOS pode ser atribuída através do ICM. Isso se aplica quando o Device ID não está disponível no aplicativo do anunciante, no aplicativo do publisher ou em ambos.
* Atualmente, o Google reivindica apenas cliques no iOS. Ele não reivindica impressões.

<div id="using-deferred-deep-linking-in-app-campaigns" />

## Usando deferred deep linking em campanhas de aplicativos

**O que é deep link e como ele funciona?**

Quando um usuário potencial clica em um feed, ele é redirecionado para a página do aplicativo. Depois que o usuário instala o aplicativo e o inicia, o SDK fornece os detalhes específicos do produto (por exemplo, tênis de corrida) com Deferred deep linking. O programador do aplicativo usa esses dados para oferecer uma experiência de usuário relevante dentro do aplicativo.

**Deferred deep linking no Google**

<Anchor target="_blank" href="https://support.google.com/google-ads/answer/9959794?hl=en&ref_topic=10011599">Feeds do Google em campanhas de apps</Anchor> ou <Anchor target="_blank" href="https://support.google.com/google-ads/answer/12373847?">deferred deep linking de grupo de anúncios</Anchor> permitem criar uma experiência de conteúdo específica e fluida para novos usuários mobile. O Google permite definir deep links no feed ou no grupo de anúncios, e a AppsFlyer oferece suporte a ambos os casos para deferred deep linking.

**Para ativar deferred deep linking com o Google Ads:**

1. Certifique-se de usar <Anchor target="_blank" href="/marketers/pt/docs/conversion-data-payloads-and-scenarios#reatribuição-com-deferred-deep-linking">GCD</Anchor> para receber o parâmetro `af_dp` no SDK da AppsFlyer.
2. No Google, configure os <Anchor target="_blank" href="https://support.google.com/google-ads/answer/9958973?hl=en&ref_topic=10011599">feeds</Anchor> ou configure <Anchor target="_blank" href="https://support.google.com/google-ads/answer/12373847?">deferred deep linking no nível do grupo de anúncios</Anchor>.
3. Na AppsFlyer, vá para **Configuração** > **Integrações ativas**. Selecione **Google Ads (Adwords)**.
4. Na aba **Integração**, ative **Deferred deep linking com Google Ads.**
5. Clique em **Salvar integração.**

<div id="note-2" />

> 📘 **Note**
>
> O valor de deferred deeplink do Google Ads é retornado pelo Google apenas para correspondências determinísticas, com base no device ID, e não é suportado para correspondências probabilísticas (ICM).

<div id="google-ads-parameter-mapping" />

## Mapeamento de parâmetros do Google Ads

A tabela abaixo descreve o mapeamento de parâmetros entre o Google Ads e a AppsFlyer. Observe que os anunciantes não podem adicionar parâmetros personalizados a nenhuma campanha do Google Ads.

| **Tipo de ad network** | **Busca** | **Exibição** | **YouTube** |
| --- | --- | --- | --- |
| Canal (`af_channel`) | Veja a tabela abaixo, [Como preencher o parâmetro `Canal`](/docs/google-ads-adwords-integration-setup-for-advertisers#preencha-o-parâmetro-canal) |  |  |
| Campanha (`c`) | Yes | Sim | Yes |
| ID da campanha (`af_c_id`) | Yes | Sim | Yes |
| Adset (`af_adset`)  <br />Preenchido pelo parâmetro `ad_group_name`.  <br />Se este parâmetro for nulo, a AF preenche `af_adset` com `ad_group_id`. | Yes | Yes | Yes |
| Adset ID (`af_adset_id`) preenchido pelo parâmetro `ad_group_id` do Google. | Yes | Sim | Yes |
| Anúncio (`af_ad`). | N/D | N/D | N/D |
| `af_ad_id`Ad IDaf\_ad\_id  <br />Preenchido pelo parâmetro `creative_id` do Google. | Yes | Yes | Yes |
| Tipo de anúncio (`af_ad_type`) | Yes* | Sim* | Yes* |
| ID do site (`af_siteid`) | GoogleSearch/  <br />Parceiros de busca | N/D | YouTubeVideos/  <br />Parceiros de vídeo |
| Palavras-chave | N/D | N/D | N/D |

<div id="populate-the-channel-parameter" />

### Preencha o parâmetro `Canal`

O Google Ads não envia o parâmetro `Canal (af_channel)`. A AppsFlyer determina como preencher este parâmetro para os tipos de campanha recebidos do Google Ads, de acordo com as seguintes regras:

<table><thead><tr><th colspan="2">Tipo de campanha <strong>E</strong> lógica de tipo de rede:</th><th rowspan="2"> Parâmetro <kbd>Canal</kbd> </th><th rowspan="2">Exemplo</th></tr><tr><th>campaign_type</th><th>tipo_rede</th></tr></thead><tbody><tr><td> <kbd>ACI</kbd>, <kbd>ACE</kbd>, <kbd>ACPRE</kbd>, <kbd>Shopping</kbd> ou <kbd>Hotel</kbd> </td><td>Todos os tipos de ad network</td><td><kbd>campaign_type_network_type</kbd></td><td>canal = <kbd>ACI_Search</kbd> </td></tr><tr><td><p><strong>Não:</strong></p><p><kbd>ACI</kbd>, <kbd>ACE</kbd>, <kbd>ACPRE</kbd>, <kbd>Shopping</kbd> ou <kbd>Hotel</kbd></p></td><td><kbd>Exibição</kbd></td><td><kbd>network_subtype</kbd></td><td>canal = <kbd>mGDN</kbd> </td></tr><tr><td><p><strong>Não:</strong></p><p><kbd>ACI</kbd>, <kbd>ACE</kbd>, <kbd>ACPRE</kbd>, <kbd>Shopping</kbd> ou <kbd>Hotel</kbd></p></td><td><p><strong>Não:</strong></p><p><kbd>Exibição</kbd></p></td><td><kbd>tipo_rede</kbd></td><td>canal = <kbd>Search</kbd> </td></tr></tbody></table>

Para mais informações sobre os tipos de anúncio disponíveis na resposta do Google, veja as <Anchor target="_blank" href="https://developers.google.com/app-conversion-tracking/api/request-response-specs">especificações de solicitação e resposta do Google</Anchor>.

<div id="note-3" />

> 📘 **Importante!**
>
> Quando o Google atribui uma instalação através da atribuição probabilística (ICM), ele não compartilha `network_type` com a AppsFlyer. Assim, o tipo de rede fica ausente e o valor do canal é `ACI_` (sem um sufixo).

<div id="campaign-type-app-campaigns" />

### Tipo de campanha: campanhas de aplicativos

<div id="changes-to-campaign-names-by-google-ads" />

#### Mudanças nos nomes das campanhas pelo Google Ads

| Até 15 de fevereiro de 2021 | A partir de 23 de fevereiro de 2021 |
| --- | --- |
| UAC | ACI |
| UACE | ACE |
| UACPre | ACPRE |

**Atenção:** O tipo de nome da campanha é determinado pela data do clique ou impressão, e não pela data de instalação.

<div id="engaged-view-parameter-in-raw-data-reports" />

### Parâmetro de engaged view em relatórios de dados brutos

Engaged view é uma impressão do usuário sobre um anúncio em vídeo que durou mais de 10 segundos. Tem a mesma prioridade de atribuição que um clique.  Para Android, engaged views são exibidas nos relatórios de dados brutos como `engaged_view` sob os parâmetros `Engagement Type` e `Sub Param 5`.   
Engaged views são contados se ocorrerem dentro da janela de lookback de cliques definida na AppsFlyer, com um limite máximo de 3 dias.

<div id="important-2" />

> 🚧 **Importante!**
>
> * A Google é uma SRN (Self Reporting Network). Para mais informações sobre como o fluxo de atribuição funciona para essas redes, consulte <Anchor target="_blank" href="/marketers/pt/docs/self-reporting-networks-srns">Self-reporting networks (SRNs)</Anchor>.
> * A AppsFlyer pode apresentar qualquer informação de campanha fornecida pelo Google. O tipo de campanha (busca, vídeo, exibição) e as informações associadas são determinados pelo Google. Para mais informações, veja as <Anchor target="_blank" href="https://developers.google.com/app-conversion-tracking/api/request-response-specs">especificações de solicitação e resposta do Google</Anchor>.

<div id="send-complex-in-app-events-to-google-ads" />

## Envie eventos in-app complexos para o Google Ads

Para enviar eventos in-app complexos — eventos com vários itens — para o Google Ads, recomendamos usar o novo objeto de evento `af_order_info`. Para mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/item-level-order-data-for-ad-networks-af-order-info">Dados de pedido no nível do item para ad networks (af\_order\_info)</Anchor>.

<div id="optimize-google-ads-campaigns-for-conversions-without-device-id" />

## Otimização de campanhas do Google Ads para conversões sem device ID

A partir do iOS14.5+ e Android 12+, o Google Ads introduziu vários identificadores. Esses identificadores são usados para atribuição determinística de conversões sem device IDs:

| Identificador | Disponível a partir de | Fonte | Sistema operacional | Usado para | Granularidade dos dados |
| --- | --- | --- | --- | --- | --- |
| gclid | Dezembro de 2021 | Referenciador da Google Play | com o Android | Instalações / reinstalações | Nível do usuário |
| gclid | Dezembro de 2021 | URL de links diretos (deep link) | Android + iOS | Reengajamentos | Nível do usuário |
| gbraid | Março de 2021 | URL de links diretos (deep link) | /docs/ctv-pc-and-console-platform-attribution-concepts | Reengajamentos | Dados agregados |
| odm\_info | Novembro de 2025 | AppsFlyer SDK / S2S | /docs/ctv-pc-and-console-platform-attribution-concepts | Instalações / reinstalações | Dados agregados |

No Google Ads e na AppsFlyer, os anunciantes podem receber dados a nível de campanha para tráfego sem Device IDs para reengajamento, instalações e atividades de reatribuição. No entanto, os dados a nível de adset e de anúncios não são compartilhados pelo Google.  
**Nenhuma ação do anunciante é necessária para permitir o recebimento desses parâmetros.**

<div id="data-visibility-by-operating-system" />

### Visibilidade de dados por sistema operacional

**Apps Android:**

Na AppsFlyer e no Google Ads, os anunciantes podem receber dados completos da campanha para tráfego sem device IDs, tanto para instalações quanto para reengajamentos.

**Apps iOS:**

No Google Ads e na AppsFlyer, anunciantes podem receber dados completos da campanha para tráfego sem device IDs para suas atividades de reengajamento.

<div id="advertising-without-the-firebase-sdk" />

## Anúncios sem o Firebase SDK

Ao anunciar com o Google Ads sem a implementação do Firebase SDK, as seguintes limitações se aplicam:

| Limitação | Detalhes |
| --- | --- |
| tROAS não disponível | A otimização para tROAS (meta de retorno do gasto com anúncios) está disponível apenas ao usar eventos de receita do Firebase SDK. Eventos de receita da AppsFlyer, e de todos os outros MMPs, não são elegíveis para essa otimização. |
| Exclusão de audiência não disponível | Os anunciantes só podem excluir usuários de campanhas de aplicativos quando a campanha é otimizada para eventos do Firebase SDK, não para eventos de MMP. |

<div id="google-probabilistic-attribution-icm-traits-and-limitations" />

## Características e limitações da atribuição probabilística do Google (ICM)

| Limitação | Detalhes |
| --- | --- |
| Escopo de atribuição | Compatível apenas com **instalações e reatribuição**; sem compatibilidade para **reengajamentos.** |
| Dados de reivindicação incluídos | As alegações do Google incluem (na maioria dos casos):<ul><li>**Nome da campanha**</li><li>**ID da campanha**</li><li>**Nome do grupo de anúncios (Adset)**</li><li>**ID do grupo de anúncios (Adset)**</li></ul>Não inclui **informações do anúncio.** |
| Campo de canal | Nenhum tipo ou subtipo de network fornecido; o campo **Canal** conterá um valor parcial: `ACI_`  <br />Para mais informações sobre a lógica de "Canal", veja [como preencher o parâmetro `Canal`](/docs/google-ads-adwords-integration-setup-for-advertisers#preencha-o-parâmetro-canal) . |
| Suporte regional do iOS ODM | **Não é compatível** na UE, no Reino Unido e na Suíça |
| Privacidade Avançada Agregada (AAP) | Quando o botão <Anchor target="_blank" href="/marketers/pt/docs/apply-aggregated-advanced-privacy-framework">AAP</Anchor> (Privacidade Avançada Agregada) estiver **ATIVADO** nas configurações do aplicativo no iOS, os dados atribuídos ao Google nos relatórios de dados brutos são mostrados como restritos. Para visualizar dados não consentidos do Google, certifique-se de que o botão AAP esteja **DESATIVADO**. |
| Hora de atribuição do toque | O timestamp das reivindicações probabilísticas do Google é arredondado para intervalos de 15 minutos (00:00, 00:15, 00:30, etc.) |
| Mascaramento de IP | O uso do mascaramento de IP pode afetar a performance da ICM. O Google recomenda desativar o mascaramento de IP para não afetar a mensuração e a performance do Google Ads. Veja como <Anchor target="_blank" href="/marketers/pt/docs/apply-ip-masking-to-user-data#mascaramento-de-ip">aplicar o mascaramento de IP aos dados dos usuários</Anchor>. |
| IDFV | O Google exige o envio do <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-knowledge-base-glossary#idfv">IDFV</Anchor> (quando disponível) com instalações, aberturas de aplicativos e eventos in-app, para maximizar a performance da ICM. |

<span id="h_01HDP0SBEE75MAT4A4S9E7Y7FF"></span>**Veja também:**

* Para considerações sobre o iOS 14, consulte <Anchor target="_blank" href="/marketers/pt/docs/get-skan-postback-data-from-google-ads">Interoperabilidade do Google Ads para SKAdNetwork com a AppsFlyer</Anchor>.

<div data-zendesk-anchors="google-icm-attribution-flow-with-advanced-data-sharing=fluxo-de-atribui%C3%A7%C3%A3o-do-google-ads-com-compartilhamento-avan%C3%A7ado-de-dados h_01K0VKGRK7XXC4GNF6B9X76M4T=fluxo-de-atribui%C3%A7%C3%A3o-do-google-ads-com-compartilhamento-avan%C3%A7ado-de-dados configuring-google-ads-attribution-for-advertisers=configura%C3%A7%C3%A3o-da-atribui%C3%A7%C3%A3o-do-google-ads-para-anunciantes h_01HACTC1H5MANBCRWYQPNW5CC2=configura%C3%A7%C3%A3o-da-atribui%C3%A7%C3%A3o-do-google-ads-para-anunciantes h_01HACTC1H5R995RXYRFQBFHRF1=importante h_01HACTC1H5EFJKV6AXNSTNFZA4=aten%C3%A7%C3%A3o h_01HSX7TJC7PQ0ATM1J86Z4HMYJ=importante-1 h_01KA6S8V6CKRATXHZQZ4YN7V9R=aten%C3%A7%C3%A3o-1 h_01HACTC1H58WHJDBN2DRQAZKGB=importante-2 h_01HACTC1H5Z3XXS1MGBS4WYJBV=observa%C3%A7%C3%A3o granting-permissions-to-google-ads-team-members=como-conceder-permiss%C3%B5es-aos-membros-da-equipe-do-google-ads h_01HACTC1H5PAY95M4H1A6WTSEF=como-conceder-permiss%C3%B5es-aos-membros-da-equipe-do-google-ads enabling-google-ads-attribution-for-agencies=ativa%C3%A7%C3%A3o-da-atribui%C3%A7%C3%A3o-do-google-ads-para-ag%C3%AAncias h_01HACTC1H5QE93EAYYVVDQV2WC=ativa%C3%A7%C3%A3o-da-atribui%C3%A7%C3%A3o-do-google-ads-para-ag%C3%AAncias running-with-multiple-google-ads-accounts=trabalhar-com-v%C3%A1rias-contas-do-google-ads h_01HACTC1H5Z8B15RHQ75HVV2RP=trabalhar-com-v%C3%A1rias-contas-do-google-ads ios-app-campaigns=campanhas-de-aplicativos-para-ios h_01HACTC1H5X567H6A8M3FWCTAN=campanhas-de-aplicativos-para-ios using-deferred-deep-linking-in-app-campaigns=usando-deferred-deep-linking-em-campanhas-de-aplicativos h_01HACTC1H57HJZNAGDKSQD6MVC=usando-deferred-deep-linking-em-campanhas-de-aplicativos google-ads-parameter-mapping=mapeamento-de-par%C3%A2metros-do-google-ads h_01HACTC1H6P1A2E160Z6GAGZZS=mapeamento-de-par%C3%A2metros-do-google-ads how-to-populate-the-channel-parameter=preencha-o-par%C3%A2metro-canal h_01HACTC1H6TPTDDFSMPQ9YVMDY=preencha-o-par%C3%A2metro-canal h_01KEYE1W4VJYXYHY4FP1KN3SP9=importante-3 campaign-type-app-campaigns=tipo-de-campanha-campanhas-de-aplicativos h_01HACTC1H6CEGD2E3HXHWFWBRB=tipo-de-campanha-campanhas-de-aplicativos changes-to-campaign-names-by-google-ads=mudan%C3%A7as-nos-nomes-das-campanhas-pelo-google-ads h_01HACTC1H6A028HKVXJ66MCF6M=mudan%C3%A7as-nos-nomes-das-campanhas-pelo-google-ads engaged-view-parameter-in-raw-data-reports=par%C3%A2metro-de-engaged-view-em-relat%C3%B3rios-de-dados-brutos h_01HACTC1H6Q6WCTK4Z9RGV6PA4=par%C3%A2metro-de-engaged-view-em-relat%C3%B3rios-de-dados-brutos h_01HACTC1H62HC36C08ZBFZ05XS=importante-4 h_01M20SN9DCHRQP8TD5Q2Z00CWQ=envie-eventos-in-app-complexos-para-o-google-ads optimize-google-ads-campaigns-for-conversions-without-device-id=otimiza%C3%A7%C3%A3o-de-campanhas-do-google-ads-para-convers%C3%B5es-sem-device-id h_01HACTC1H6EFDVN9N89Y17HDFR=otimiza%C3%A7%C3%A3o-de-campanhas-do-google-ads-para-convers%C3%B5es-sem-device-id data-visibility-by-operating-system=visibilidade-de-dados-por-sistema-operacional h_01HACTC1H6WZNMVJK479M5KJYF=visibilidade-de-dados-por-sistema-operacional h_01_advertising-without-firebase-sdk=an%C3%BAncios-sem-o-firebase-sdk advertising-without-the-firebase-sdk=an%C3%BAncios-sem-o-firebase-sdk google-icm-traits-and-limitations=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es-da-atribui%C3%A7%C3%A3o-probabil%C3%ADstica-do-google-icm h_01K0XMCXSS5MKY90DZWJTNVBBS=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es-da-atribui%C3%A7%C3%A3o-probabil%C3%ADstica-do-google-icm" />
