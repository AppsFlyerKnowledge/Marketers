---
title: Google Ads (Adwords) — Crie campanhas na web para aplicativos de sites
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2026-04-07T12:46:10Z'
  edited_at: '2026-10-20T03:47:55Z'
  id: 45498975339537
  locale: pt
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/pt/articles/45498975339537
---
> **At a glance:** Configure uma integração do Google Ads para o aplicativo do seu site para enviar sinais de conversão na web ao Google através da API de Conversões Offline (OCI).

<div id="overview" />

## Visão geral

A AppsFlyer permite a integração com o Google Ads (`googleads_int`) para campanhas de aplicativos de sites e registra os dados de conversão através da API de Conversões Offline (OCI) do Google.

Neste artigo, você aprenderá a configurar campanhas da web na AppsFlyer e no Google Ads, com segmentação direcionada a usuários que interagem com o Google Ads e realizam conversões no seu site.

O fluxo da campanha começa quando um usuário clica em um anúncio do Google e acessa seu site. Quando o usuário conclui um evento no site (por exemplo, uma compra ou um cadastro), a AppsFlyer envia o sinal de conversão para o Google Ads via OCI. O Google usa esses dados para otimizar a segmentação de anúncios e mensurar a performance de campanhas.

<div id="prerequisites" />

### Pré-requisitos

Antes de ativar a integração do Google Ads para campanhas de aplicativos de sites, certifique-se de que você tenha:

* Um aplicativo de site configurado na AppsFlyer.
* O SDK web da AppsFlyer implementado no seu site ou uma integração totalmente server-side usando a API Server-to-Server (S2S). Para obter mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/server-to-server-s2s-api-for-web-performance-measurement#configurar-uma-integração-total-do-lado-do-servidor">Configurar uma integração totalmente server-side</Anchor>
* Uma conta da AppsFlyer com funções ou permissões adequadas

<div id="how-to-set-up-a-google-ads-web-campaign" />

### Como configurar uma campanha do Google Ads na web

A configuração é dividida em duas partes:

1. Configurar a integração do Google Ads na AppsFlyer (obrigatória)
2. Configurar a campanha no Google Ads (obrigatória)

<div id="set-up-the-google-ads-integration-in-appsflyer" />

## Configure a integração do Google Ads na AppsFlyer

Comece ativando a integração do Google Ads para campanhas na web e configure os postbacks que a AppsFlyer envia para a OCI.

<div id="step-1-activate-the-integration" />

<Accordion title="Etapa 1: Ative a integração">

1. Na AppsFlyer, no menu lateral, acesse **Colaborar > Partner Marketplace**.
2. Procure por **Google Ads Web** e selecione-o.
3. Clique em **Configurar integração**. Você será direcionado para a página de configuração **Integrações ativas**.
4. No menu suspenso dos aplicativos, selecione o aplicativo web.
5. Na aba **Integração** selecione **Ativar parceiro**.

   <div id="note" />

   > 📘 **Atenção**
   >
   > O botão deve permanecer habilitado (ativado) enquanto você trabalhar com o parceiro.

6. Insira seu **Customer ID**. Você pode encontrá-lo no Google Ads Manager:
   1. Faça login na sua conta do Google Ads.
   2. No canto superior direito, clique no ícone da conta do Google e role para baixo até encontrar o Customer ID.
   3. Siga uma das opções abaixo:
      * Se você tiver várias contas do Google Ads executando campanhas para seu aplicativo, use o Customer ID de uma conta MCC para o rastreamento de conversões entre contas. Cole o MCC ID (e não o Customer ID de uma conta específica) nas caixas de texto "Customer ID" e "MCC Customer ID" (mesmo ID para ambas).  Para mais informações, veja <Anchor target="_blank" href="https://support.google.com/google-ads/answer/3061730?sjid=4528491462900554442-NC">as instruções do Google sobre como configurar uma conta MCC</Anchor>.
      * Se você usar apenas uma única conta do Google Ads para executar anúncios, cole o ID da conta na caixa de texto "Customer ID". Deixe a caixa de texto "MCC Customer ID" vazia.
7. Para permitir que a AppsFlyer envie conversões para o Google Ads, clique em **Login com o Google**.
8. Selecione a conta de administrador da conta MCC da qual você recuperou o Customer ID.
9. Clique em **Permitir**.

   <div id="note-1" />

   > 📘 **Atenção**
   >
   > A mensagem de erro **Token ausente** deixará de aparecer assim que você fizer o login com o Google e permitir que a AppsFlyer recupere o token. Se o erro persistir após o login, verifique se o seu token tem as permissões necessárias.


</Accordion>

<div id="step-2-set-inapp-event-postbacks" />

<Accordion title="Etapa 2: Configure os postbacks de eventos in-app">

Associe os eventos do seu site às ações de conversão do Google Ads. A AppsFlyer envia esses eventos para a Google via OCI, para permitir a otimização baseada na conversão.

<div id="note-2" />

> 📘 **Atenção**
>
> No caso dos aplicativos web, todos os eventos são eventos web. Não há eventos de instalação. Cada evento para o qual você deseja que o Google faça a otimização deve ser associado a um ID de ação de conversão correspondente do Google Ads.

1. Ative **Postbacks de eventos in-app**.
2. Defina a **janela de postback de eventos in-app**, se necessário. A janela é aberta durante o primeiro evento de conversão do usuário no site (equivalente à data de instalação no mobile).
3. Clique em **Adicionar evento**.
4. Na coluna **Eventos da AppsFlyer**, selecione o evento do site que você deseja enviar (por exemplo, `purchase`, `sign_up`).

   <div id="note-3" />

   > 📘 **Atenção**
   >
   > Os eventos de visita são excluídos. Apenas os eventos personalizados na web estão disponíveis.

5. Na coluna **Mapeado para eventos de parceiro**, insira o **ID da ação de conversão** do Google Ads. Antes de fazer isso, você precisa criar a ação de conversão no Google Ads (consulte [Etapa 2: Criar ações de conversão](#step-2-create-conversion-actions)). Para encontrar o ID da ação de conversão:
   * No Google Ads, abra a página das ações de conversão.
   * Abra a aba **Detalhes**.
   * Copie o valor do parâmetro de consulta `ctid=*` do URL da página. Por exemplo, se `ctid=123456789`, insira `123456789`.
6. Na coluna **Para usuários de**, selecione **Apenas este parceiro** para enviar eventos atribuídos exclusivamente ao Google Ads.
7. Na coluna **Incluindo**, selecione se deseja incluir os valores de receita no postback.
8. Clique em **Salvar integração**.

<div id="note-4" />

> 📘 **Atenção**
>
> Se você enviar eventos S2S e quiser que a AppsFlyer envie postbacks deles para o Google Ads, verifique se cada evento tem pelo menos um click ID do Google: `gclid`, `gbraid` ou `wbraid`. Se um evento não tiver nenhum, a AppsFlyer não enviará o postback. Para ver todos os campos de evento compatíveis, consulte <Anchor target="_blank" href="/marketers/pt/docs/server-to-server-s2s-api-for-web-performance-measurement#mensurar-um-evento">API Server-to-Server (S2S) para Mensuração de performance web</Anchor>.

</Accordion>

<div id="set-up-a-web-conversion-campaign-in-google-ads" />

## Configurar uma campanha de conversão na web no Google Ads

<div id="step-1-set-the-campaign-type-objective-and-goals" />

<Accordion title="Etapa 1: Defina o tipo, o objetivo e as metas da campanha.">

1. Entre no Google Ads e crie uma campanha.
2. Selecione um **objetivo para a campanha**:
   * Todos os objetivos são aplicáveis, exceto **Promoção de aplicativos**, que se destina exclusivamente a campanhas de aplicativos mobile.
   * Recomendamos as opções **Vendas** ou **Leads** para otimizar com base em eventos de conversão específicos do site.
3. Selecione seus **objetivos de conversão**. Por padrão, os objetivos são apresentados no nível da conta. Você pode mantê-los ou remover aqueles que não são relevantes.
   * Se o objetivo que você deseja otimizar não estiver na lista, crie uma ação de conversão personalizada (consulte [Etapa 2: Criar ações de conversão](#step-2-create-conversion-actions)).
4. Selecione o **tipo de campanha**:
   * Todos os tipos de campanha são aplicáveis, exceto **Compras**, que exige um catálogo de produtos e domínios verificados.

</Accordion>

<div id="step-2-create-conversion-actions" />

<Accordion title="Etapa 2: Crie ações de conversão">

Para cada evento do site mapeado na AppsFlyer, crie uma ação de conversão correspondente no Google Ads. Depois de criá-la, copie o ID e cole-o no mapeamento de eventos da AppsFlyer, na seção anterior.

1. No Google Ads, no menu lateral, abra **Objetivos > Conversões > Resumo**.
2. Clique em **+ Nova ação de conversão**.
3. Selecione **Importar** como fonte de dados de conversão e escolha uma das seguintes opções:
   * **Importação manual via API ou upload > Rastrear conversões de cliques** ou
   * **CRM, arquivos ou outras fontes de dados > Rastrear conversões de cliques** e, em "Fonte de dados", selecione **Ignorar esta etapa e configurar a fonte de dados mais tarde**.
4. Clique em **Continuar**.
5. Em **Meta de conversão**, selecione uma categoria de ação de conversão.
6. Insira um **nome para a conversão** e clique em **Adicionar**.

   <div id="important" />

   > 🚧 **Importante!**
   >
   > Para usar a API de Conversões Offline com GBRAID/WBRAID (além de GCLID), certifique-se de que o campo **Count** na ação de conversão esteja definido como **Every** (padrão) e NÃO **One**.


   <div id="note-5" />

   > 📘 **Atenção**
   >
   > Se você quiser que suas campanhas sejam otimizadas para uma única ação, inclua somente essa ação para essa categoria. Por exemplo, se você quiser que sua campanha seja otimizada para uma ação de conversão de compra, certifique-se de que ela seja a única em sua categoria. Em seguida, você poderá selecionar essa categoria como a meta de conversão para otimização da performance ao criar a campanha.

7. Clique em **Salvar e continuar** e depois em **Concluído**, sem configurar fontes de dados. Sua nova ação de conversão pode aparecer inicialmente como **Inativo**. Ela mudará para **Ativo** assim que dados reais forem enviados.
8. Para mapear a nova ação de conversão para o evento de postback da AppsFlyer, recupere o ID da ação de conversão: Na página **Resumo** das metas de conversão, clique na ação de conversão que você criou e copie o valor do parâmetro de consulta `ctid=*` do URL da página.
9. Na AppsFlyer, cole o valor `ctid` na coluna **Mapeado para eventos de parceiro** do evento de postback que você deseja que o Google otimize. Consulte [Etapa 2: Configure os postbacks de eventos in-app](#step-2-set-inapp-event-postbacks).

</Accordion>

<div id="step-3-set-the-campaigns-final-url" />

<Accordion title="Etapa 3: Defina o URL final da campanha">

O Google <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6080568?sjid=9660882197247124000-EU">define o URL final</Anchor> como "o endereço da página do seu site para onde as pessoas são direcionadas depois de clicarem no seu anúncio, também conhecido como "landing page".

1. No Google Ads, abra a página **Campanhas > Anúncios.**
2. Na linha de anúncios, clique no ícone de edição.
3. No campo **URL final**, insira o URL da sua landing page.

   <div id="important-1" />

   > 🚧 **Importante!**
   >
   > O URL final não pode ser um URL da AppsFlyer (OneLink ou um URL de atribuição de plataforma única), pois isso pode fazer com que sua campanha seja rejeitada. Use somente um endereço direto da web que não tenha redirecionamentos.
   >
   > Você pode adicionar parâmetros de atribuição da AppsFlyer ao URL final e mapeá-los para os parâmetros do Google ValueTrack, por exemplo, `af_c_id={campaignid}`. Quando um anúncio do Google é clicado e a landing page carregada, esses parâmetros são disponibilizados na página. Para saber mais sobre os parâmetros ValueTrack disponíveis, consulte a <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6305348">documentação do Google</Anchor>.
   >
   > Exemplo:
   >
   > ```http
   > https://example.com?product=1234&af_c_id={campaignid}
   > ```


<div id="note-6" />

> 📘 **Atenção**
>
> As campanhas do Google Web Ads podem usar dois URLs por engajamento: o URL final e o URL do template de rastreamento. No entanto, o URL do template de rastreamento não é obrigatório nas campanhas de aplicativos de sites em que o destino do anúncio é um site. Um URL de modelo de rastreamento pode ser necessário somente quando o objetivo da campanha for web-to-mobile. Para mais informações, veja o artigo sobre as <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-create-web-based-campaigns">campanhas web-to-app do Google Ads</Anchor>.

</Accordion>

<div id="view-web-performance-measurement-data" />

## Ver dados de mensuração de performance web

Os dados de atribuição web relativos às campanhas do Google Ads estão disponíveis no dashboard cross-platform e nas exportações de dados brutos:

* **Dashboard:** No <Anchor target="_blank" href="/marketers/pt/docs/my-dashboards#crossplatform-dashboard">dashboard cross-platform</Anchor>, os dados da web e do aplicativo são apresentados lado a lado, oferecendo uma visão unificada da performance de campanhas em todas as plataformas.
* **Exportação de dados brutos:** Os dados de atribuição web também estão disponíveis na <Anchor target="_blank" href="/marketers/pt/docs/raw-data-export-page">Página de exportação de dados brutos</Anchor>.
  * O campo `media_source` apresenta `googleadwords_int` para os eventos da web atribuídos ao Google Ads.

<div id="note-7" />

> 📘 **Importante!**
>
> Essa visão unificada permite que você analise a performance de campanhas na web e no aplicativo em um só local, incluindo relatórios completos de custos na web e no mobile.

<div id="measure-web-performance-data-with-web-cost" />

## Mensurar dados de performance web com custo web

Você pode ter uma visão completa da performance dos dados de atribuição web e dos dados de custo web do Google Ads no dashboard e nos <Anchor target="_blank" href="/marketers/pt/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl">relatórios do Cost ETL</Anchor>. Para fazer isso, verifique se você tem <Anchor target="_blank" href="/marketers/pt/docs/roi360-onboarding-guide#sobre-o-roi360">o pacote ROI360</Anchor> e conclua a seguinte configuração:

1. Conecte custos ao aplicativo do seu site via `googleadwords_int` (não via `googleads_int`) da aba **Custos** ou da página **Configurações de custo**. Para mais informações sobre como conectar custos, leia o artigo <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#enabling-cost-api">Configure a ROI360 cost API para mensurar dados de custo</Anchor>.
2. Inclua o ID da campanha (`af_c_id`) no URL da landing page. Certifique-se de que o URL inclua toda a hierarquia da campanha para visualizar custos, cliques e impressões correspondentes à atribuição web no nível mais granular.

<div id="troubleshooting-in-app-event-postbacks" />

## Solução de problemas: postbacks de eventos in-app

Se os dados dos eventos não estiverem aparecendo no Google Ads, verifique as opções abaixo antes de entrar em contato com o suporte.

<div id="set-token-permissions" />

<Accordion title="Configurar permissões de token">

No Google Ads, certifique-se de que seu token de acesso tenha as permissões necessárias para enviar conversões offline:

1. Vá para o Google Developers Console.
2. Certifique-se de que `uploadClickConversions` tenha o escopo OAuth: `https://www.googleapis.com/auth/adwords`
3. Na AppsFlyer, na aba "Integração", clique em **Login com o Google**.
4. Selecione a conta de administrador da conta MCC.
5. Clique em **Permitir**.

</Accordion>

<div id="mcc-customer-id" />

<Accordion title="ID do cliente do MCC">

Se você tiver várias contas do Google Ads executando campanhas para seu aplicativo, use o Customer ID de uma conta MCC. Veja <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6139186">as instruções do Google sobre como configurar uma conta MCC</Anchor>.

</Accordion>

<div id="conversion-action-id" />

<Accordion title="ID da ação de conversão">

Certifique-se de que os eventos de postback no aplicativo estejam mapeados para o Conversion Action ID certo. Para encontrar o Conversion Action ID no Google Ads, veja a Etapa 2: [Crie ações de conversão](#step-2-create-conversion-actions).

</Accordion>

<div id="traits-and-limitations" />

## Características e limitações

| Caraterística | Observações |
| --- | --- |
| Cliques e impressões | Cliques e impressões para campanhas na web exigem uma <Anchor target="_blank" href="/marketers/pt/docs/roi360-onboarding-guide">assinatura do ROI360</Anchor>. |

<div id="see-also" />

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/web-performance-measurement-overview">Mensuração da performance web - visão geral</Anchor>

<div data-zendesk-anchors="overview=vis%C3%A3o-geral h_01KNM00RR7V9BAA2BSPDECHC9F=vis%C3%A3o-geral prerequisites=pr%C3%A9-requisitos h_01KNM00RR7H7A9CE06APEZSXKR=pr%C3%A9-requisitos how-to-set-up-a-google-ads-web-campaign=como-configurar-uma-campanha-do-google-ads-na-web h_01KNM00RR77P8VD2YJ2R7DZBVX=como-configurar-uma-campanha-do-google-ads-na-web set-up-the-google-ads-integration-in-appsflyer=configure-a-integra%C3%A7%C3%A3o-do-google-ads-na-appsflyer h_01KNM00RR7E8MFSTGYKFEJDS1C=configure-a-integra%C3%A7%C3%A3o-do-google-ads-na-appsflyer h_01KNM00RR71ZXB72H8X1YXWKED=step-1-activate-the-integration h_01KNM00RR84CCGBR3T5WG7C5VW=aten%C3%A7%C3%A3o h_01KNM00RR86C5VKBVTA9X6QRAS=aten%C3%A7%C3%A3o-1 h_01KNM00RR8BCJTMPZ29C841BY1=step-2-set-inapp-event-postbacks h_01KNM00RR8PSJ7FEAP7MMEJ1XG=aten%C3%A7%C3%A3o-2 h_01KNM00RR89XJ0BZKFDXVC4860=aten%C3%A7%C3%A3o-3 h_01M520ZTQ1QT2F03TMY9TZBPSY=aten%C3%A7%C3%A3o-4 set-up-a-web-conversion-campaign-in-google-ads=configurar-uma-campanha-de-convers%C3%A3o-na-web-no-google-ads h_01KNM00RR8SAS3TM1NG5DC58TF=configurar-uma-campanha-de-convers%C3%A3o-na-web-no-google-ads h_01KNM00RR8S24AG7FMN6067PZ2=step-1-set-the-campaign-type-objective-and-goals h_01KNM00RR8H1ZFSHFT0DVB11GN=step-2-create-conversion-actions h_01KNM00RR8EV8XY02YJFV5XSX8=importante h_01KNM00RR8N96SNP1YK0CTN6YZ=aten%C3%A7%C3%A3o-5 h_01KNM00RR82NZSKB7K06HCP1VE=step-3-set-the-campaigns-final-url h_01KNM00RR8EP6J43G29Q8VVA5B=importante-1 h_01KNM00RR8A704MKGVVC6MQ2KN=aten%C3%A7%C3%A3o-6 view-web-attribution-data=ver-dados-de-mensura%C3%A7%C3%A3o-de-performance-web h_01KNM00RR8EYJAX2KRGCM65E9M=ver-dados-de-mensura%C3%A7%C3%A3o-de-performance-web h_01KNM00RR86Q2GTHVNC505KCXZ=importante-2 measure-web-attribution-data-with-web-cost=mensurar-dados-de-performance-web-com-custo-web h_01KNM00RR9TF8JRTJXWN23MF1S=mensurar-dados-de-performance-web-com-custo-web troubleshooting-in-app-event-postbacks=solu%C3%A7%C3%A3o-de-problemas-postbacks-de-eventos-in-app h_01KNM00RR9Z0BM5EE62M17EE0F=solu%C3%A7%C3%A3o-de-problemas-postbacks-de-eventos-in-app h_01KNM00RR9CJJQAP4GAXZ9KK8N=set-token-permissions h_01KNM00RR9215H3KB024BBFZX2=mcc-customer-id h_01KNM00RR9DBR5979GA0FVD5AK=conversion-action-id traits-and-limitations=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01KQAE3JKMQ6ZEATDAEXBC4PT6=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01KQC2B644Y44631ZQKC1HPEF4=veja-tamb%C3%A9m" />
