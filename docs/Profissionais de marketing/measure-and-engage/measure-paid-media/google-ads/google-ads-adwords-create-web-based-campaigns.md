---
title: Google Ads (AdWords) — Crie campanhas na web para apps móveis
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2024-05-16T09:12:15Z'
  edited_at: '2026-10-13T00:13:36Z'
  id: 25096718837137
  locale: pt
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/pt/articles/25096718837137
---
> **At a glance:** Crie campanhas da web para atribuir conversões web-to-app do Google Ads

> 📘 **Note**
>
> esse artigo tem como foco campanhas na web para a divulgação de aplicativos mobile. Se você quiser criar campanhas que dibulguem aplicativos para PC ou console, veja Google Ads Web—Integração para aplicativos de PC e console.

## Resumo

A AppsFlyer permite a integração com o Google Ads (`googleads_int`) para campanhas de aplicativos de sites e registra os dados de conversão através da API de Conversões Offline (OCI) do Google.

Neste artigo, você aprenderá a configurar campanhas da web na AppsFlyer e no Google Ads, com segmentação direcionada a usuários que interagem com o Google Ads e realizam conversões no seu site.

O fluxo da campanha começa quando um usuário clica em um anúncio do Google e acessa seu site. Essa página inclui o Smart Script ou Smart Banners da AppsFlyer, que criam links de atribuição.

Depois de receberem um clique, esses links levam o usuário à loja de aplicativos para baixar e instalar o app. A instalação e os eventos subsequentes no aplicativo são registrados na AppsFlyer e reportados ao Google Ads via OCI.

O Google usa esses dados para otimizar a segmentação de anúncios e mensurar a performance de campanhas.

### Pré-requisitos

Antes de ativar a integração do Google Ads para campanhas de aplicativos de sites, certifique-se de que você tenha:

* Um aplicativo mobile
* Uma conta da AppsFlyer
* AppsFlyer <Anchor target="_blank" href="/marketers/pt/docs/user-management">usuários com funções ou permissões adequadas</Anchor> e acesso aos aplicativos relevantes

### Como configurar uma campanha do Google Ads na web

Esse artigo contém informações relevantes e etapas para configurar uma campanha web no Google Ads para mobile, PC e apps de console com a AppsFlyer. A configuração envolve definir a integração entre o Google Ads e a AppsFlyer e configurar os links de atribuição da campanha.

* Configurar a integração do Google Ads na AppsFlyer (obrigatória)
* O campo `media_source` apresenta `googleadwords_int` para os eventos da web atribuídos ao Google Ads.

Depois de configurar os links de atribuição na etapa um por meio da integração do Google Ads e da AppsFlyer, a etapa dois se concentra na criação da landing page. Aqui, o OneLink Smart Script ou os Smart Banners usarão os links de atribuição para gerar botões de call-to-action, direcionando os usuários para as lojas de aplicativos.

* [Criar uma landing page com o OneLink Smart Script](#criar-uma-landing-page-com-o-onelink-smart-script) (opcional)
* [Criar uma landing page com OneLink Smart Banners](#crie-uma-landing-page-com-os-smart-banners-do-onelink) (opcional)

## Configurar a integração do Google Ads na AppsFlyer

Comece ativando a integração do Google Ads para campanhas na web e configure os postbacks que a AppsFlyer envia para a OCI.

<Accordion title="1. Ative a integração do Google Ads para campanhas web">

1. Na AppsFlyer, no menu lateral, acesse **Colaborar** > **Partner Marketplace**.
2. Pesquise por **Google Ads Web** e selecione-o.
3. Clique em **configurar integração**. Você será direcionado para a página de configuração de **Integrações ativas**.
4. Na aba **Integração** selecione **Ativar parceiro**. **Atenção:** O botão deve permanecer ativado (<Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">ligado</Anchor>) durante todo o tempo em que você trabalhar com seu parceiro.
5. Desative a **Privacidade avançada** (se você estiver configurando uma integração de aplicativo iOS).

> 📘 **Note**
>
> A mensagem de erro *Token ausente* deixará de aparecer assim que você fizer o login com o Google e permitir que a AppsFlyer recupere o token. Se o erro persistir após o login, verifique se o seu token tem as permissões necessárias.

1. Em **First open conversion ID**, insira o ID da ação de conversão `First open` que você definiu no Google Ads. Para encontrar o ID, acesse o Google Ads e abra a guia **Details** na página da ação de conversão **First open**. Em seguida, copie o valor do parâmetro de consulta `ctid=*` da URL da página. Por exemplo, se `ctid=123456789`, insira `123456789` na caixa **First open conversion action ID**.

   ![](https://files.readme.io/0bbe655051204d8902b82f2f8d8b12f183ef40f9e84c542972db767707d75a9d-26324053660177.png)

> 👍 **Tip**
>
> Se você ainda precisar definir a ação "Primeira abertura" no Google Ads, poderá inserir um valor de espaço reservado temporariamente até que a ação esteja totalmente configurada.

1. Insira seu **Customer ID**. Você pode encontrá-lo no Google Ads Manager:
   1. Faça login na sua conta do Google Ads.
   2. No canto superior direito, clique no ícone da conta do Google e role para baixo até encontrar o Customer ID.
2. Se você tiver várias contas do Google Ads executando campanhas para seu aplicativo, use o Customer ID de uma conta MCC para o rastreamento de conversões entre contas. Cole o **MCC ID** (e não o Customer ID de uma conta específica) nas caixas de texto **Customer ID** e **MCC Customer ID** (mesmo ID para ambas).   
   Se você usar apenas uma única conta do Google Ads para executar anúncios, basta colar o ID da conta na caixa de texto **Customer ID** e deixar a **MCC Customer ID** vazia. Veja <Anchor target="_blank" href="https://support.google.com/google-ads/answer/3061730?sjid=4528491462900554442-NC">Instruções do Google sobre como configurar uma conta MCC</Anchor>.
3. Clique em **Permitir**

</Accordion>

<Accordion title="2. Ative a atribuição de view-through">

A AppsFlyer oferece suporte para a atribuição de view-through através de campanhas Google Web usando um [Smart Script](#set-up-a-smart-script-crossplatform-landing-page) ou uma landing page habilitada para [Smart Banner](#set-up-a-smart-banners-landing-page). Isso permite a atribuição de instalação de aplicativos por modelagem probabilística (PMOD), que é acionada por impressões de anúncios, mesmo quando os usuários não clicam diretamente no anúncio.

Quando um usuário vê um anúncio do Google e acessa uma landing page habilitada para [Smart Script](#set-up-a-smart-script-crossplatform-landing-page) ou [Smart Banner](#set-up-a-smart-banners-landing-page), a AppsFlyer pode atribuir a instalação resultante de volta à impressão original da web, com um acompanhamento cross-platform.

Quando disponível, a AppsFlyer inclui o `gclid` no postback para o Google.

**Para ativar a atribuição de view-through:**

1. Na AppsFlyer, no menu lateral, abra **Colaborar** > **Integrações de parceiros > Integrações ativas** > **Google Ads Web**
2. Na aba **Integração**, vá até a seção **Atribuição de instalação**.
3. Ative a **Atribuição de instalação por view-through**.
4. **[opcional]** Ative a **Prioridade de atribuição equitativa entre plataformas** e defina sua janela de lookback. Para mais informações, veja o artigo <Anchor target="_blank" href="/marketers/pt/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">Ativar prioridade equitativa para impressões entre plataformas</Anchor>.
5. Abra a aba **Atribuição**.
6. Vá até a seção **Atribuição de view-through** e defina a **janela de lookback de view-through** desejada (de até 24 horas).
7. Clique em **Salvar integração** para aplicar as alterações.

</Accordion>

<Accordion title="3. Ative o compartilhamento de dados de correspondência avançada">

O compartilhamento de dados de correspondência avançada é controlado por parceiro e por aplicativo e deve ser ativado separadamente para o Google Ads Web.

Quando ativado, identificadores com hash, como um endereço de e-mail com hash ou um número de telefone com hash, são compartilhados com o Google OCI se esses campos estiverem incluídos nos dados do evento que você enviar. Para mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/advanced-matching-data-sharing">Compartilhamento de dados de correspondência avançada</Anchor>.

Para ativar o compartilhamento de dados de correspondência avançada:

1. Na AppsFlyer, no menu lateral, acesse **Colaborar** > **Integrações de parceiros** > **Integrações ativas**.
2. Pesquise por **Google Ads Web** e selecione-o.
3. Na aba **Integração**, ative o **Compartilhamento de dados de correspondência avançada**.
4. Clique em **Guardar integração**.

</Accordion>

<Accordion title="4. Configurar postbacks de eventos in-app">

Atualmente, instalações são os únicos eventos que acionam postbacks padrão automáticos para o Google Ads para web via API OCI. Para outros tipos de eventos, você pode criar postbacks personalizados mapeando eventos da AppsFlyer para IDs de ação de conversão do Google Ads (“Ação de conversão” é o termo que o Google Ads usa para eventos de atribuição.) Consulte o Google Ads Manager para saber mais sobre o evento web do Google Ads que você precisa mapear para eventos da AppsFlyer. Consulte o Google Ads Manager para saber qual evento do Google Ads Web você precisa mapear para eventos da AppsFlyer.

1. Ative **Postbacks de eventos in-app.**
2. Se necessário, defina a janela de postback de eventos in-app (leia mais sobre a configuração da janela de postback de eventos in-app em geral <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#janela-de-postback-de-eventos-in-app">neste artigo</Anchor>).
3. Para mapear a nova ação de conversão para o evento de postback da AppsFlyer, recupere o ID da ação de conversão: Na página **Resumo** das metas de conversão, clique na ação de conversão que você criou e copie o valor do parâmetro de consulta `ctid=*` do URL da página.
4. In the **AppsFlyer event** column, select the event name from the drop-down box. A AppsFlyer recebe o nome do evento do SDK integrado ao seu aplicativo ou dos eventos de servidor para servidor.
5. Na coluna **Mapeado para eventos de parceiro**, insira o **ID da ação de conversão** do Google Ads. Antes disso, você precisa criar a ação de conversão no Google Ads (veja a Etapa 2 da Parte 2 abaixo). Para encontrar o ID da ação de conversão:

   **No Google Ads, abra a página das ações de conversão.**

   1. Configurar a campanha no Google Ads (obrigatória)
   2. Abra a página de conversion action que você quer mapear.
   3. Abra a aba **Detalhes**.
   4. Copie o valor do parâmetro de consulta `ctid=*` do URL da página.
   5. Volte para a AppsFlyer.
   6. Copie o valor do parâmetro de consulta `ctid=*` do URL da página. Por exemplo, se `ctid=123456789`, insira `123456789`.
6. Na coluna **Para usuários de**, selecione **Somente este parceiro** ou **Todos os canais de mídia, incluindo orgânico**. **Atenção:** eventos sem atribuição serão enviados somente se o <Anchor target="_blank" href="/marketers/pt/docs/advanced-matching-data-sharing">Compartilhamento de dados de correspondência avançada</Anchor> estiver ativado e incluírem um e-mail ou número de telefone com hash.
7. Na coluna **Incluindo**, selecione se deseja incluir os valores de receita no postback.
8. [Opcional] Clique no ícone **Adicionar condição** para <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#postbacks-condicionais-de-eventos-in-app">definir condições</Anchor> para um evento.
9. Clique em **Guardar Integração**.
10. [Opcional] Após salvar a integração, você pode integrar mais aplicativos com o parceiro em questão:
    1. No canto superior esquerdo clique no nome do aplicativo para abrir a lista de aplicativos.
    2. Selecione um aplicativo diferente na lista suspensa.
    3. Repita as etapas de integração para o aplicativo selecionado.

</Accordion>

<Accordion title="5. Configurar o template do OneLink">

Antes de criar um link de atribuição do OneLink para sua campanha do Google Ads, você precisa definir seu template. Em seguida, você pode criar uma URL de atribuição do OneLink com base no template e usá-lo como o URL do template de rastreamento do Google.

> 📘 **Note**
>
> As instruções abaixo se concentram na criação de um template do OneLink para campanhas da web do Google com o Smart Script. Para obter um guia completo sobre como configurar templates do OneLink, consulte a seção Como criar modelos do OneLink do artigo Templates do OneLink .

1. Na seção **Redirecionamento** da página **Novo modelo** ou **Editar modelo**, defina as seguintes configurações:
   * **Quando o aplicativo não estiver instalado** > **Redirecionar para**: selecione a opção de sua preferência. O valor de redirecionamento definido aqui é substituído pelo valor `{lpurl}` dos parâmetros de redirecionamento ( <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_android_url">`af_android_url`</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_ios_url">`af_ios_url`</Anchor> ) que você coloca no template de rastreamento do Google.
   * **Quando o aplicativo estiver instalado**: certifique-se **não** de configurar Universal Links, esquema de URI ou Todos os links para abrir o aplicativo, pois o Google não permite nenhum redirecionamento além do redirecionamento para o URL final.
   * **Quando o link for clicado em uma página web para desktop** > **Redirecionar para**: selecione a opção de sua preferência. O valor de redirecionamento que você define aqui é substituído pelo valor de `{lpurl}` dos parâmetros de redirecionamento (<Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_web_dp">`af_web_dp`</Anchor>) que você insere no modelo de rastreamento do Google, consulte [Set the Tracking Template URL](#defina-a-url-do-template-de-rastreamento).
2. Clique em **Adicionar evento**.

</Accordion>

## Configurar uma campanha de conversão na web no Google Ads

Configurar a campanha no Google Ads (obrigatória)

<Accordion title="1. Defina o tipo, objetivo e metas da campanha.">

O Google Ads usa o objetivo e as metas do tipo de campanha que você selecionar aqui para definir a estratégia de bidding correta e otimizar a performance da campanha.

1. Entre no Google Ads e crie uma campanha.
2. Selecione um **objetivo para a campanha**:

   ![](https://files.readme.io/90063f7fe5a363ed498271148c4165969cc63c708a73ab25363d2263a79b0828-26324053661201.png)
   * Todos os objetivos são aplicáveis, exceto **Promoção de aplicativos**, que se destina exclusivamente a campanhas de aplicativos mobile.
   * Recomendamos que você configure o objetivo da campanha de “Vendas” para otimização com base em eventos específicos no aplicativo.
3. Selecione seus **objetivos de conversão**.

   ![](https://files.readme.io/5ca0a0425af24d5926dc0a7a3529632e22bd140423e87c026ff1527e7a0341b3-26324096257169.png)
   * Por padrão, os objetivos são apresentados no nível da conta. Você pode mantê-los ou remover aqueles que não são relevantes.
   * Se você não vê o objetivo que deseja que o Google otimize,

     <Anchor target="_blank" href="/marketers/pt/docs/google-ads-web-integration-for-pc-and-console-apps#creating-conversion-actions-and-goals">crie uma ação de conversão e um objetivo personalizados</Anchor>.
   * Você também pode editar suas metas predefinidas na página de conversões.
4. Selecione o **tipo de campanha**:

   ![](https://files.readme.io/14daea1c1edf92854e21d0a4c5d34372a4e062d68a4613967bb4f40d0d1e720f-26324053659281.png)
   * Todos os tipos de campanha são aplicáveis, exceto **Compras**, que exige um catálogo de produtos e domínios verificados.

</Accordion>

<Accordion title="2. Crie ações de conversão personalizadas">

Para cada evento do site mapeado na AppsFlyer, crie uma ação de conversão correspondente no Google Ads. Depois de criá-la, copie o ID e cole-o no mapeamento de eventos da AppsFlyer, na seção anterior.

Etapa 2: Crie ações de conversão

1. No Google Ads, no menu lateral, abra **Objetivos > Conversões > Resumo**.
2. Clique em **+ Nova ação de conversão**.
3. Selecione **Conversões offline** como sua fonte de dados de ações de conversão.
4. Se o objetivo que você deseja otimizar não estiver na lista, crie uma ação de conversão personalizada (consulte a Etapa 2 abaixo).

   * **Importação manual via API ou upload > Rastrear conversões de cliques** ou

   OU

   * **CRM, arquivos ou outras fontes de dados > Rastrear conversões de cliques** e, em "Fonte de dados", selecione *Ignorar esta etapa e configurar a fonte de dados mais tarde*.
5. Clique em **continuar.**
6. Em **Meta de conversão**, selecione uma categoria de ação de conversão.
7. Insira um **nome para a conversão** e clique em **Adicionar**.

> ❗️ **Warning**
>
> Para usar a API de Conversões Offline com GBRAID/WBRAID (além de GCLID), certifique-se de que o campo **Count** na ação de conversão esteja definido como **Every** (padrão) e NÃO *One*.

1. Insira um **nome para a conversão** e clique em **Adicionar**. Se você quiser que suas campanhas sejam otimizadas para uma única ação, inclua somente essa ação para essa categoria. Por exemplo, se você quiser que sua campanha seja otimizada para uma ação de conversão de compra, certifique-se de que ela seja a única em sua categoria. Em seguida, você poderá selecionar essa categoria como a meta de conversão para otimização da performance ao criar a campanha.
2. Clique em **Salvar e continuar** e depois em **Concluído**, sem configurar fontes de dados. Sua nova ação de conversão pode aparecer inicialmente como *Inativa*, mas ela mudará para *Ativa* assim que dados reais forem recebidos.
3. Certifique-se de que os eventos de postback no aplicativo estejam mapeados para o Conversion Action ID certo. Para encontrar o Conversion Action ID no Google Ads, veja a Etapa 2: [Crie ações de conversão](#step-2-create-conversion-actions).

   ![](https://files.readme.io/0bbe655051204d8902b82f2f8d8b12f183ef40f9e84c542972db767707d75a9d-26324053660177.png)
4. Na AppsFlyer, cole o valor `ctid` na coluna **Mapeado para eventos de parceiro** do evento de postback que você deseja que o Google otimize. Veja o artigo "Configuração de postback de eventos in-app"

</Accordion>

<Accordion title="3. Defina as URLs da campanha">

As campanhas do Google Web Ads usam duas URLs para cada engajamento: a URL final e a URL do template de rastreamento. Quando um anúncio do Google é clicado e a landing page carregada, esses parâmetros são disponibilizados na página. Para saber mais sobre os parâmetros ValueTrack disponíveis, consulte a <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6305348">documentação do Google</Anchor>.

#### Etapa 3: Defina o URL final da campanha

O Google <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6080568?sjid=9660882197247124000-EU">define a URL final</Anchor> como "o endereço URL da página web no seu site que as pessoas acessam depois de clicar no seu anúncio". Também conhecido como "página de destino".

**Um aplicativo de site configurado na AppsFlyer.**

1. No Google Ads, abra a página **Campanhas > Anúncios.**
2. Na linha de anúncios, clique no ícone de edição.

   ![](https://files.readme.io/e6b834a0e105324c5b9e4105a5ce7e1f47fa7c00fcf2aee29b6b0e96763150f1-26324098055057.png)
3. No campo **URL final**, insira o URL da sua landing page.

> ❗️ **Warning**
>
> O URL final não pode ser um URL da AppsFlyer (OneLink ou um URL de atribuição de plataforma única), pois isso pode fazer com que sua campanha seja rejeitada. Use somente um endereço direto da web que não tenha redirecionamentos.

1. Este deve ser o local final da web para o qual você deseja redirecionar seus usuários. Pode ser:
   * **Uma URL de página de destino** que aponta para uma página que solicita ao usuário que clique em um botão de CTA para fazer o download do aplicativo no Google Play, na App Store ou em qualquer outra loja de aplicativos. A landing page inclui Smart Script ou Smart Banners, que geram automaticamente as URLs dos botões CTA. Para saber [como criar a página de destino com Smart Script](#criar-uma-landing-page-com-o-onelink-smart-script) ou [Smart Banners](#crie-uma-landing-page-com-os-smart-banners-do-onelink).

     Você pode adicionar parâmetros de atribuição da AppsFlyer ao URL final e mapeá-los para os parâmetros do Google ValueTrack, por exemplo, `af_c_id={campaignid}`. Depois que o anúncio do Google é clicado e a página inicial é carregada, o Smart Script ou os Smart Banners podem copiar os parâmetros para a URL de saída da landing page. Para saber mais sobre os parâmetros ValueTrack disponíveis, consulte a [documentação do Google](https://support.google.com/google-ads/answer/6305348?sjid=9660882197247124000-EU#zippy=%2Cfinal-url-tracking-template-or-custom-parameter).

     Exemplo:

     ```
     https://example.com?product=1234&af_c_id={campaignid}
     ```
   * **Uma URL da loja**, como App Store ou Google Play.

> ❗️ **Warning**
>
> Suponha que você use o URL da loja como seu URL final. A única maneira de enviar informações de atribuição e parâmetros personalizados para a AppsFlyer é inserir e mapear parâmetros AF para a URL do template de rastreamento.

*
  ```
  https://play.google.com/store/apps/details?id=.com.app.id&hl=en&gl=US&referrer={gclid}&gclid={gclid}&campaignid={campaignid}
  ```
* **Um link de download direto para o arquivo APK do aplicativo** se você quiser que os usuários baixem o aplicativo diretamente sem serem redirecionados para uma loja.

#### Defina a URL do template de rastreamento

Como o Google Ads, por padrão, usa o rastreamento paralelo, a URL do template de rastreamento (um link de atribuição da AppsFlyer neste caso) é carregada em segundo plano, e o clique é registrado na AppsFlyer. Não é obrigatório usar URLs de template de rastreamento, especialmente ao usar Smart Banners ou Smart Script. Consulte [Como usar a URL do template de rastreamento com Smart Script ou Smart Banners](#usando-a-url-do-template-de-rastreamento-com-smart-script-ou-smart-banners) neste artigo.

1. No Google Ads, abra a página **Campanhas** > **Campanhas**. Na linha da campanha, clique no ícone de configurações

   ![](https://files.readme.io/ec6503cfb3ff185448f13897240e0eadd7f10fc3678ffa85b4d52d2393b01ca4-26324098054033.png)
2. Expanda **Configurações** > **Configurações adicionais** > **Opções de URL da campanha**

   ![](https://files.readme.io/4959b4129749ff282ee3818c3b5724ac2ed3b1d033d06f8557329cafa812720f-26324053658641.png)
3. Em **Template de rastreamento,** use o seguinte (BaseURL + parâmetros de redirecionamento):
   * **URL base**: defina a URL base de acordo com o destino do clique no anúncio:
     * **Link de atribuição de plataforma única** se o destino do clique no anúncio for o Google Play ou a App Store (veja o exemplo abaixo).
     * **Um link de atribuição OneLink** se o destino do clique no anúncio for uma página web (veja o exemplo abaixo).

> ❗️ **Warning**
>
> Se a sua URL final apontar diretamente para a loja Google Play ou para a App Store (a plataforma do usuário é conhecida), use um link de atribuição de plataforma única na URL do template de rastreamento. Usar uma URL do OneLink nesse cenário resulta em um erro de "Tracking call unsuccessful" do Google.

* **O parâmetro PID:** Adicione o parâmetro obrigatório <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#pid">`pid`</Anchor>`=googleads_int`.

> 👍 **Tip**
>
> Para simplificar a análise da campanha, inclua o tipo de campanha, web ou mobile, como prefixo ou sufixo no nome da campanha, por exemplo, campaign-name\_web

* **O parâmetro de ID do site  :** Adicione o parâmetro obrigatório <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_siteid">`af_siteid`</Anchor> parâmetro. Você pode atribuir manualmente qualquer valor a ele.
* **O parâmetro do nome da campanha:** Adicione o parâmetro obrigatório <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#c">c</Anchor> e atribua manualmente seu valor (não há parâmetro ValueTrack para esse parâmetro).
* **O parâmetro force transparent**: adicione o parâmetro obrigatório `af_force_transparent=true`. Esse parâmetro foi projetado para aumentar a segurança no comportamento de redirecionamento e garantir que a sua configuração esteja em conformidade com os requisitos do Google. Por favor, observe que se você não adicionar o parâmetro necessário, o Google pode reprovar seu anúncio.
* **Parâmetros de redirecionamento para um link de atribuição OneLink:** Para que o rastreamento paralelo funcione como esperado, defina os parâmetros de redirecionamento da AF em uma das seguintes combinações:
  * Os parâmetros `af_android_url`, `af_ios_url` e `af_web_dp` devem ser definidos com o parâmetro do Google ValueTrack `{lpurl}`. **Importante:** Certifique-se de que os três estejam preenchidos para garantir que o link de atribuição funcione em todos os cenários.  
    **Ou**
  * O parâmetro `af_r` deve ser definido como o parâmetro Google ValueTrack `{lpurl}` .
* **Parâmetro de redirecionamento para um link de atribuição de plataforma única:** Para que o rastreamento paralelo funcione como esperado, defina o parâmetro `af_r` como o parâmetro Google ValueTrack `{lpurl}` .

> ❗️ **Warning**
>
> Para cumprir com os requisitos do Google, certifique-se de que o valor `{lpurl}` seja uma URL de redirecionamento válida:
>
> * Ela usa o protocolo HTTPS.
> * Deve ser codificada.
> * O domínio da URL deve fazer parte da sua lista de redirect allowlist.

* **Parâmetros de atribuição da AppsFlyer mapeados para parâmetros do Google ValueTrack**, por exemplo, <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_c_id">`af_c_id`</Anchor>`={campaignid}`. Para saber mais sobre os parâmetros ValueTrack disponíveis, consulte a [documentação do Google](https://support.google.com/google-ads/answer/6305348?sjid=9660882197247124000-EU#zippy=%2Cfinal-url-tracking-template-or-custom-parameter).
* Não inclua nenhum dos parâmetros a seguir. Solicitações que contêm esses parâmetros não são compatíveis com o fluxo de rastreamento paralelo e serão rejeitadas:
  * `af_dp`
  * `af_android_store_csl`
  * `af_ios_store_cpp`
  * `af_og_title`
  * `af_og_description`
  * `af_og_image`
* Não inclua nenhum parâmetro que altere o valor do parâmetro de redirecionamento `{lpurl}`. Isso inclui `af_base_params_forward` e `af_param_forwarding`.

> 📘 **Note**
>
> Para limitações adicionais relacionadas à URL do template de rastreamento, consulte a seção Características e limitações neste artigo.

#### Exemplos de URL do template de rastreamento do Google

Um exemplo de **um** **OneLink** em uma URL de template de rastreamento do Google:

```
https://subdomain.onelink.me/aAB1?pid=googleads_int&af_force_transparent=true&af_android_url={lpurl}&af_ios_url={lpurl}&af_web_dp={lpurl}&c=summer_sale24&af_siteid=123456&af_c_id={campaignid}&af_adset=sum24A&af_adset_id={adgroupid}&af_sub1={gclid}&af_sub2={gbraid}
```

Um exemplo de **um link de plataforma única** em uma URL de template de rastreamento do Google:

```
https://app.appsflyer.com/id1510557250?pid=googleads_int&af_force_transparent=true&c=examplecamp&af_siteid=123456&af_adset=exampleadset&af_adset_id={adgroupid}&af_c_id={campaignid}&af_ad_id={creative}&af_click_lookback=7d&af_r={lpurl}
```

#### Usando a URL do template de rastreamento com Smart Script ou Smart Banners

No entanto, o URL do template de rastreamento não é obrigatório nas campanhas de aplicativos de sites em que o destino do anúncio é um site. Isso ocorre porque essas ferramentas criam automaticamente um link de atribuição que é registrado na AppsFlyer quando o usuário clica no botão CTA da página inicial No entanto, há considerações a favor e contra deixar o campo URL do template de rastreamento vazio: No entanto, há considerações a favor e contra deixar o campo URL do template de rastreamento vazio:

* Se você **não preencher** a URL do template de rastreamento com um link de atribuição, corre o risco de perder instalações que ocorrem quando o usuário clica no anúncio, mas não clica em nenhum dos botões de CTA da página de destino. Se o usuário for diretamente à loja de aplicativos para baixar o aplicativo dentro da janela de lookback, a instalação subsequente não será atribuível.
* Se você **preencher** a URL do template de rastreamento com um link de atribuição e o usuário clicar no anúncio e, depois, clicar nos botões de CTA da página de destino, dois cliques serão registrados em vez de um, o que pode afetar os dados da taxa de conversão.

</Accordion>

## Criar uma landing page com o OneLink Smart Script

**Jornada do usuário:** O usuário clica em um anúncio do Google e é direcionado para o seu site mobile. Ele chegam a uma página com botões de CTA, solicitando que ele faça download do seu aplicativo. Clicar no botão redirecionará o usuário para a loja.

<Accordion title="Fluxo de dados de ponta a ponta">

O caso de uso do W2A Smart Script é composto pelas seguintes fases:

![](https://files.readme.io/95b5a593eba3bc0bafb629bb8a27d83c077d5815a79897c004f8f085fa8e953b-25646834953105.png)

1. Se você usar apenas uma única conta do Google Ads para executar anúncios, basta colar o ID da conta na caixa de texto "Customer ID" e deixar a "MCC Customer ID" vazia.
   * um `gclid` parâmetro para dispositivos Android e para usuários que consentem em dispositivos iOS.
   * `gbraid` e `wbraid` para usuários não consententes em dispositivos iOS.
   * todos os parâmetros de query definidos na URL do template de rastreamento do Google, exceto os parâmetros de redirecionamento.
2. A URL Final redireciona o usuário para a landing page.
3. Simultaneamente, a URL de template de rastreamento do anúncio do Google, que também contém os parâmetros anexados automaticamente `gclid`, `gbraid`, `wbraid` e o `pid=googleads_int` parâmetro, é acionada em segundo plano, e o clique é registrado na AppsFlyer.
4. Quando a página inicial é carregada, o Smart Banner envia um evento de impressão para a AppsFlyer contendo os parâmetros do URL de entrada. Essa impressão permite a atribuição de view-through para a landing page. Para saber mais sobre impressões e atribuição de view-through, veja como <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">criar uma URL de impressão personalizada</Anchor>.
5. O Smart Script gera as URLs de saída para os botões de CTA na página com base nos parâmetros da URL de entrada, incluindo os `gclid`, `gbraid` e `wbraid` parâmetros. Os botões podem levar a:
   * Google Play e App Store por meio de um link de atribuição do OneLink.
   * Lojas de múltiplas plataformas (por exemplo, CTV, Epic e Steam). Nesse caso de uso, o Smart Script gera um único link de saída de atribuição de plataforma para cada plataforma, levando à loja da plataforma especificada.
   * Baixando um arquivo APK para o dispositivo do usuário.
6. Quando o usuário clica no botão CTA, o clique é acionado e registrado na AppsFlyer.
7. O usuário é redirecionado para a loja e baixa o aplicativo.
8. O evento de instalação é registrado na AppsFlyer quando o usuário abre o aplicativo.
9. A AppsFlyer atribui a instalação com base em modelagem probabilística ou deterministicamente se um [install referrer](https://www.appsflyer.com/glossary/install-referrer/) estiver disponível.
10. Um postback contendo `gclid` ou `gbraid` e `wbraid` e parâmetros de evento adicionais é gerado e enviado ao Google Ads via a API OCI. O Google Ads usa o `gclid` ou o parâmetro `gbraid` e `wbraid` para identificar o clique específico, enquanto os outros parâmetros ajudam a otimizar a campanha.

</Accordion>

<Accordion title="Configurar uma landing page de Smart Script">

Mensurar os dados de atribuição web com os custos da web

1. Crie um script inteligente.

> 📘 **Note**
>
> As instruções abaixo se concentram nas etapas necessárias para configurar uma campanha web do Google com o Smart Script. Para obter um guia abrangente sobre como configurar campanhas de Smart Script, você pode consultar a seção Como criar um Smart Script do OneLink do artigo de configuração do OneLink Smart Script V2.

1. Certifique-se de que todos os parâmetros de URL relevantes (que serão posteriormente capturados pelo Smart Script) sejam anexados ao URL de entrada. Para revisar os parâmetros anexados à URL de entrada, abra o Google Ads e verifique os parâmetros de URL definidos ao criar a URL final ou a URL do modelo de rastreamento; consulte: [Definir as URLs da campanha.](#h_01J1MPPMW44NGXN55SFD16Z4HE)
2. Mapeie os parâmetros de URL de entrada necessários para a campanha do Meta Ads com os parâmetros de URL de saída que serão enviados à AppsFlyer quando o usuário clicar no botão CTA:
   * **PID**: Certifique-se de que o Smart Script pegue o valor do parâmetro `pid=googleads_int` da URL de entrada e o mapeie para os parâmetros correspondentes na URL de saída.
   * **GCLID**: O `gclid` parâmetro é essencial para enviar com sucesso postbacks de eventos in-app para o Google Ads. O mapeamento do parâmetro GCLID da URL de saída depende da sua versão do Smart Script:
     * Versão 2.8.1 e superior: O parâmetro `gclid` é encaminhado automaticamente para o parâmetro de URL de saída quando está presente na URL de entrada, eliminando a necessidade de mapeamento manual.
     * Versão 2.8.0 e inferior: O parâmetro `gclid` deve ser mapeado manualmente na seção de **mapeamento de parâmetros de URL** da página do **Smart Script**:
       1. Em **Mapeamento para**, selecione **Parâmetro personalizado**.
       2. Em **parâmetro de URL de saída** e **parâmetros de URL de entrada** insira **gclid**.
   * **GBRAID** e **WBRAID**: Os parâmetros `gbraid` e `wbraid` são essenciais para enviar com sucesso postbacks de eventos in-app para o Google Ads para usuários de dispositivos iOS que não consentiram. O mapeamento dos parâmetros `gbraid` e `wbraid` na URL de saída depende da sua versão do Smart Script:
     * Versão 2.9.0 e superior: Os parâmetros `wbraid` e `gbraid` são encaminhados automaticamente para o parâmetro da URL de saída quando estão presentes na URL de entrada, eliminando a necessidade de mapeamento manual.
     * Versão 2.8.1 e inferior: Os parâmetros `wbraid` e `gbraid` devem ser mapeados manualmente na seção **mapeamento de parâmetros de URL** da página **Smart Script**:
       1. Em **Mapeamento para**, selecione **Parâmetro personalizado**.
       2. Em **parâmetro de URL de saída** e **parâmetros de URL de entrada**, insira **wbraid**.
       3. Repita as etapas acima para o parâmetro `wbraid`.

> 📘 **Note**
>
> Para exibir nos Relatórios de dados brutos da AppsFlyer, os parâmetros de entrada gclid, gbraid e wbraid devem ser mapeados individualmente para um parâmetro af\_sub[1-5] de saída dedicado (além dos parâmetros gclid, gbraid e wbraid da URL de saída).

</Accordion>

<Accordion title="Configurar uma landing page multiplataforma do Smart Script">

Para páginas iniciais não multiplataforma, o profissional de marketing normalmente é responsável por gerar automaticamente o Smart Script por meio da página Smart Script da AppsFlyer. No entanto, quando se trata de páginas iniciais multiplataforma, o desenvolvedor cria o script com base nos parâmetros enviados pelo profissional de marketing.

Mensurar os dados de atribuição web com os custos da web

1. Ative seu template do OneLink para atribuição cross-platform; consulte <Anchor target="_blank" href="/marketers/pt/docs/set-up-cross-platform-links-for-multi-device-campaigns#crie-ou-edite-um-template-do-onelink-para-atribuição-cross-platform">Criar ou editar um template do OneLink para atribuição cross-platform</Anchor>.
2. Certifique-se de que todos os parâmetros de URL relevantes sejam anexados à URL de entrada. Para revisar os parâmetros anexados à URL de entrada, abra o Google Ads e verifique os parâmetros de URL definidos ao criar a URL final ou a URL do modelo de rastreamento; consulte: [Definir as URLs da campanha.](#h_01J1MPPMW44NGXN55SFD16Z4HE)
3. Para cada parâmetro de entrada, decida o parâmetro de saída para onde ele será mapeado. Por exemplo, `af_site_id` na URL de entrada será mapeado para `af_site_id` na URL de saída.
4. Decida o valor padrão para os parâmetros de saída obrigatórios que não podem estar vazios.
5. Envie ao desenvolvedor as seguintes informações:
   * Seu mapeamento de parâmetros de entrada e saída. O desenvolvedor criará um script que gera uma URL direta de saída com base no mapeamento de parâmetros de entrada e saída.
   * Os valores padrão dos parâmetros. O script preencherá os parâmetros de URL de saída com os valores padrão sempre que não houver valores de parâmetros de URL de entrada correspondentes.
   * Se você estiver usando um link de atribuição do OneLink, envie o ID do domínio e do template para seu desenvolvedor. O desenvolvedor usa isso para criar a URL de saída do OneLink. Por exemplo: `your_brand.onelink.me/A1b2` ou exemplo de domínio de marca: `click.yourbrand.com/A1b2`
   * Envie ao seu desenvolvedor os seguintes links do Dev Hub:
     * [Instruções e exemplos de código](https://dev.appsflyer.com/hc/docs/create-direct-click-url) sobre como criar URLs diretas de saída para plataformas não mobile.
     * [Uma demonstração e instruções](https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/) sobre como criar uma landing page multiplataforma.
   * Quando presente na URL de entrada, o parâmetro `gclid` é encaminhado automaticamente para o parâmetro de URL de saída, eliminando a necessidade de mapeamento manual (a partir da versão 2.8.1 do Smart Script). Seu desenvolvedor ainda tem a opção de mapear o `gclid` para um dos parâmetros `af_sub`, disponibilizando-o nos relatórios de dados brutos; consulte Google Ads GCLID.

</Accordion>

## Crie uma landing page com os Smart Banners do OneLink

**Jornada do usuário:** O usuário clica em um anúncio do Google e é direcionado para seu site mobile. Eles chegam a uma página e um Smart Banner é exibido com um CTA para baixar o aplicativo na loja de aplicativos.

<Accordion title="Fluxo de dados de ponta a ponta">

1. Se você usar apenas uma única conta do Google Ads para executar anúncios, basta colar o ID da conta na caixa de texto "Customer ID" e deixar a "MCC Customer ID" vazia.
   * um parâmetro `gclid` para dispositivos Android e para usuários que consentiram em dispositivos iOS.
   * os parâmetros `gbraid` e `wbraid` para usuários de dispositivos iOS que não consentiram.
   * todos os parâmetros de query definidos na URL do template de rastreamento do Google, exceto os parâmetros de redirecionamento.
2. Simultaneamente, a URL do template de rastreamento do Google por trás do anúncio, que contém o parâmetro `gclid` anexado automaticamente e o parâmetro `pid=googleads_int` , é disparada em segundo plano, e o clique é registrado com a AppsFlyer.
3. Quando a landing page é carregada, o Smart Banner envia um evento de <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">impressão</Anchor> para a AppsFlyer, que inclui os parâmetros da URL de entrada. Essa impressão permite a atribuição de view-through para a landing page. Para saber mais sobre impressões e atribuição de view-through, veja como <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">criar uma URL de impressão personalizada</Anchor>.
4. O Smart Banner gera a URL de saída para o botão de CTA no banner com base nos parâmetros de entrada, incluindo o parâmetro `gclid`. O Smart Banner pode gerar apenas links baseados no OneLink.
5. Quando o usuário clica no botão CTA do Smart Banner, o clique é acionado e registrado na AppsFlyer.
6. O usuário é redirecionado para a loja e baixa o aplicativo.
7. O evento de instalação é registrado na AppsFlyer quando o usuário abre o aplicativo.
8. A AppsFlyer atribui a instalação com base em modelagem probabilística ou deterministicamente se um [referenciador de instalação](https://www.appsflyer.com/glossary/install-referrer/) estiver disponível.
9. Um postback contendo o `gclid` e outros parâmetros de evento é gerado e enviado ao Google Ads por meio da API OCI. O Google usa o parâmetro `gclid` para identificar o clique específico, enquanto os outros parâmetros ajudam a otimizar a campanha.

</Accordion>

<Accordion title="Configurar uma landing page do Smart Banner">

> 📘 **Note**
>
> As instruções abaixo se concentram nas etapas necessárias para configurar uma campanha web do Google com o Smart Banner. Para obter um guia abrangente sobre como configurar campanhas de Smart Banners, consulte a seção de configuração do artigo Smart Banners —mobile web-to-app (para profissionais de marketing).

Os dados de atribuição web relativos às campanhas do Google Ads estão disponíveis no dashboard cross-platform e nas exportações de dados brutos:

1. Crie um Smart Banner. Para obter instruções, consulte a <Anchor target="_blank" href="/marketers/pt/docs/smart-banners-mobile-web-to-app-for-marketers#configuração">seção de configuração</Anchor> do artigo <Anchor target="_blank" href="/marketers/pt/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banners—mobile web-to-app (para profissionais de marketing)</Anchor>.
2. Certifique-se de que a URL de entrada inclua o seguinte:
   * O `pid=googleads_int` está disponível na URL de entrada.
   * O parâmetro `gclid` está disponível na URL de entrada. Os Smart Banners encaminham automaticamente o parâmetro `gclid` para a URL do banner de saída. O parâmetro `gclid` é necessário para o envio bem-sucedido de postbacks in-app ao Google OCI.
   * Os parâmetros `gbraid` e `wbraid` estão disponíveis na URL de entrada ao enviar postbacks para usuários de dispositivos iOS que não consentiram. Os Smart Banners encaminham automaticamente esses parâmetros para a URL de saída do banner. Nesse caso, os parâmetros `gbraid` e `wbraid` permitem que o Google acesse dados agregados de eventos na ausência do parâmetro `gclid`.
   * Certifique-se de que todos os parâmetros de URL relevantes sejam anexados à URL de entrada. Para revisar os parâmetros anexados à URL de entrada, abra o Google Ads e verifique os parâmetros de URL definidos como parte da criação da URL final ou da URL do modelo de rastreamento; consulte: [Definir as URLs da campanha](#h_01J1MPPMW44NGXN55SFD16Z4HE).
3. (Opcional) Na página de configuração do grupo de banners, na seção **Parâmetros de atribuição dinâmica**, selecione a primeira caixa de seleção. Essa configuração garante que todos os parâmetros do link de entrada sejam adicionados ao link no Smart Banner.

</Accordion>

## Ver dados de atribuição web

Embora os eventos de conversão baseados na web sejam enviados para o Google sob o PID original `googleads_int`, eles são registrados no dashboard da AppsFlyer e nos relatórios de dados brutos com o PID `googleadwords_int`. Isso se aplica tanto a eventos de conversão primários quanto a eventos de assistência de conversão.

Essa visão unificada permite que você analise a performance de campanhas na web e no app em um só local, incluindo relatórios completos de custos na web e no mobile.

### Ver no dashboard

Todas as atribuições de web-to-app do Google aparecem sob `googleadwords_int` nos dashboards de visão geral e de atividade. Isso fornece uma visão única e consolidada dos resultados da campanha em várias plataformas. Use filtros e análises padrão para comparar o tráfego do app e da web dentro dos seus dados do Google Ads.

### Ver em dados brutos e relatórios de API

* **Exportações de dados brutos e respostas da API** incluem o PID `googleadwords_int` no campo `media_source` para a atividade web do Google. Para verificar os detalhes da configuração da campanha na web, consulte o campo `original_url`, que mostra `googleads_int` como o PID usado durante a criação de campanhas na web.
* **Relatórios de postback** mostram `googleads_int` como a fonte de mídia original para a qual o postback foi enviado.

## Solução de problemas: postbacks de eventos in-app

Se os dados dos eventos não estiverem aparecendo no Google Ads, verifique as opções abaixo antes de entrar em contato com o suporte.

<Accordion title="Configurar permissões de token">

No Google Ads, certifique-se de que seu token de acesso tenha as permissões necessárias para enviar conversões offline:

1. Vá para o Google Developers Console.
2. Certifique-se de que `uploadClickConversions` tenha o escopo OAuth: `https://www.googleapis.com/auth/adwords`
3. Na AppsFlyer, na aba "Integração", clique em **Login com o Google**.
4. Selecione a conta de administrador da conta MCC.
5. Clique em **Permitir**

</Accordion>

<Accordion title="MCC Customer ID">

Se você tiver várias contas do Google Ads executando campanhas para seu aplicativo, use o Customer ID de uma conta MCC. Veja <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6139186">as instruções do Google sobre como configurar uma conta MCC</Anchor>.

</Accordion>

<Accordion title="Conversion Action ID">

Certifique-se de que os eventos de postback no aplicativo estejam mapeados para o Conversion Action ID certo. Para encontrar o ID da ação de conversão no Google Ads, consulte [Encontrar o ID da ação de conversão no Google Ads](#to-find-the-conversion-action-id-in-google-ads).

</Accordion>

<Accordion title="Parâmetros GCLID, GBRAID, WBRAID">

A URL de saída do Smart Script ou do Smart Banners deve incluir `gclid`, `wbraid` ou `gbraid` para que o postback ao Google OCI seja registrado corretamente no Google Ads.

</Accordion>

## Características e limitações

| Caraterística | Observações |
| --- | --- |
| <span id="dashboard"></span>Painel | Os dados de atribuição para campanhas baseadas na web do Google no iOS são visualizados e analisados no dashboard clássico da AppsFlyer. Na maioria dos casos, o dashboard da SKAN não é relevante para campanhas web-to-app. |
| <span id="reengagement-attribution"></span>Atribuição de reengajamento | Os usuários podem observar instalações atribuídas a `googleads_int` e reengajamentos atribuídos a `googleadwords_int`, embora ambos sejam impulsionados pela mesma campanha. Esse comportamento é esperado e não significa um problema técnico.   <br />  <br />Isso geralmente ocorre quando uma integração de SRN `googleadwords_int` também está ativa, permitindo que ela reivindique reengajamentos da mesma campanha web-to-app do Google Ads. |
| <span id="cost-data"></span>Custo, cliques e dados de impressões | Os dados de custo, cliques e impressões do Google Ads Web (`googleads_int`) são suportados pela integração do Google Ads (`googleadwords_int`).<ul><li>Para obter os dados, certifique-se de conectar a conta da ad network ao PID principal (`googleadwords_int`):<ul><li>Com assinatura do ROI360: na página **Configurações de Custo**.</li><li>**Exportação de dados brutos:** Os dados de atribuição web também estão disponíveis na <Anchor target="_blank" href="/marketers/pt/docs/raw-data-export-page">Página de exportação de dados brutos</Anchor>.</li></ul></li><li>Para ver os dados de custo, cliques e impressões das campanhas web do Google Ads, verifique se o ID da campanha (<Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_c_id">af\_c\_id</Anchor>) está incluído no link de atribuição.</li><li>Certifique-se de que o URL inclua toda a hierarquia da campanha para visualizar custos, cliques e impressões correspondentes à atribuição web no nível mais granular.</li></ul> |
| <span id="tracking-template-urls"></span>Tracking template URLs | Tracking template URLs devem estar de acordo com as limitações abaixo. Caso esse não seja o caso, você terá um link quebrado.<ul><li>Os links não devem conter parâmetros duplicados.</li><li>Os links não devem incluir parâmetros inválidos, como:<ul><li>Parâmetros sem valores, parâmetros quebrados ou parâmetros que não podem ser analisados. Isso inclui parâmetros sem valores, como `key=` ou `key`. Por exemplo: `pid=googleads_int&key&c=campaign` ou `pid=googleads_int&key=&c=campaign`</li><li>Valores ausentes em um dos parâmetros do ValueTrack, por exemplo `{placement}`. Para evitar valores ausentes, certifique-se de que o Google Ads os preencheu definindo corretamente o template de rastreamento no Google Ads.</li></ul></li><li>Se você inseriu valores para quaisquer parâmetros na **opção de URL da campanha** na configuração da sua campanha do Google Ads, eles devem corresponder aos valores dos parâmetros no modelo de rastreamento. Se não corresponderem, remova-os do modelo de rastreamento para garantir a conformidade com a atualização da política.</li></ul> |
| <span id="unexpected-srn-attribution"></span>Atribuição de SRN inesperada | Em alguns casos, as instalações de campanhas baseadas na web do Google Ads podem ser atribuídas a `googleadwords_int` via SRN (self-reporting network), mesmo em campanhas baseadas na web. Isso ocorre quando o Google reivindica a instalação. A AppsFlyer atribui a instalação de acordo quando o Google faz a reivindicação. Esse comportamento é esperado e pode se tornar mais comum à medida que o Google expande o suporte para atribuição de instalação de campanhas na web. |
| <span id="agency-managed-campaigns"></span>Campanhas gerenciadas por agência | Se a campanha web for gerenciada exclusivamente por uma agência, as integrações `googleads_int` do anunciante e da agência deverão estar ativas para que os postbacks cheguem ao Google Ads. A agência também deve concluir [Fazer login com o Google](#h_01J1MPPMW3G9B1G116B18CRYJB) para provisionar um token OAuth. Se esta etapa for ignorada, a chamada de postback falhará e não será enviada ao Google. |
| <span id="plan-availability"></span>Disponibilidade do plano | A integração `googleads_int` está disponível apenas para os planos Growth e Enterprise. Clientes dos planos Zero e Welcome não podem ativar essa integração. |

<div data-zendesk-anchors="overview=resumo h_01J1MPPMW38A7EG2W8TJ8F6YQ3=resumo prerequisite=pr%C3%A9-requisitos h_01J1MPPMW3GWQKZVG2HAQA9H46=pr%C3%A9-requisitos how-to-create-a-google-ad-web-campaign=como-configurar-uma-campanha-do-google-ads-na-web h_01J1MPPMW3ZYSPQHT4D2YAJ038=como-configurar-uma-campanha-do-google-ads-na-web create-a-google-ad-for-web-integration-in-appsflyer=configurar-a-integra%C3%A7%C3%A3o-do-google-ads-na-appsflyer h_01J1MPPMW3WTD63M686BHZNKDX=configurar-a-integra%C3%A7%C3%A3o-do-google-ads-na-appsflyer create-a-web-campaign-in-google-ads=configurar-uma-campanha-de-convers%C3%A3o-na-web-no-google-ads h_01J1MPPMW4AQNQEKBN1VSPM4X7=configurar-uma-campanha-de-convers%C3%A3o-na-web-no-google-ads set-the-final-url=etapa-3-defina-o-url-final-da-campanha h_01J1MPPMW48F7X2NYEA735BG51=etapa-3-defina-o-url-final-da-campanha set-the-tracking-template-url=defina-a-url-do-template-de-rastreamento h_01J1MPPMW44596CZVKF9MGDTMP=defina-a-url-do-template-de-rastreamento google-tracking-template-url-examples=exemplos-de-url-do-template-de-rastreamento-do-google 01JCZQR9RJAZF4SJVVKYZNJNPY=exemplos-de-url-do-template-de-rastreamento-do-google using-the-tracking-template-url-with-smart-script-or-smart-banners=usando-a-url-do-template-de-rastreamento-com-smart-script-ou-smart-banners 01JCZQR9RMAW9YP3T3679JAX45=usando-a-url-do-template-de-rastreamento-com-smart-script-ou-smart-banners create-a-landing-page-with-onelink-smart-script=criar-uma-landing-page-com-o-onelink-smart-script h_01J1MPPMW4P7Q18JN7JS9ZXR23=criar-uma-landing-page-com-o-onelink-smart-script create-a-landing-page-with-onelink-smart-banners=crie-uma-landing-page-com-os-smart-banners-do-onelink h_01J1MPPMW4CW8JMJK26PTEY74W=crie-uma-landing-page-com-os-smart-banners-do-onelink google-view-web-to-app=ver-dados-de-atribui%C3%A7%C3%A3o-web view-webtoapp-attribution-data-from-november-2-2025=ver-dados-de-atribui%C3%A7%C3%A3o-web h_01K88H6ETM23EV0PTR8GS13KRN=ver-dados-de-atribui%C3%A7%C3%A3o-web view-in-the-dashboard=ver-no-dashboard h_01K88H6ETMG7007CJ0ADD8VQH4=ver-no-dashboard view-in-raw-data-and-api-reports=ver-em-dados-brutos-e-relat%C3%B3rios-de-api h_01K88H6ETM502Z2XDC63602FGD=ver-em-dados-brutos-e-relat%C3%B3rios-de-api troubleshooting-inapp-events-postbacks=solu%C3%A7%C3%A3o-de-problemas-postbacks-de-eventos-in-app h_01J52V5G2DSF9PW9Z5GJHAD376=solu%C3%A7%C3%A3o-de-problemas-postbacks-de-eventos-in-app traits-and-limitations=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es 01JDW5XHD92VFJ93671YP4JMFQ=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es" />
