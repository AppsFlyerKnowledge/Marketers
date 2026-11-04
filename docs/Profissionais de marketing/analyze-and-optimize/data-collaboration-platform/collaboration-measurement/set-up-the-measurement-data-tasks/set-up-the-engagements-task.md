---
title: Configure a tarefa de engajamento
metadata:
  keywords:
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Clean Room
  created_at: '2025-08-18T10:19:20Z'
  edited_at: '2026-08-18T00:06:24Z'
  id: 38188042548113
  locale: pt
  section: Set up the measurement data tasks
  section_id: 38035061674769
  url: https://support.appsflyer.com/hc/pt/articles/38188042548113
---
> **Em resumo:** Saiba como configurar eventos de engajamento para campanhas on-site e combinadas (campanhas on-site e off-site).

<Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#engagements">Eventos de engajamento</Anchor> capturam interações do usuário, como visualizações de anúncios ou cliques, que ocorrem antes de uma conversão. Eles são configurados apenas para campanhas on-site, sozinhas ou combinadas com campanhas off-site. (Para campanhas off-site, os dados de engajamento são fornecidos diretamente por parceiros externos, como Meta ou Google. Este artigo explica como configurar engajamentos por tipo de campanha.

<div id="prerequisites" />

## Pré-requisitos

Antes que a tarefa de engajamentos possa ser configurada, o proprietário da colaboração precisa atribuí-la ao colaborador que é proprietário da plataforma onde os eventos de engajamento são gerados. Para mais informações, consulte Atribuir tarefas de configuração

<div id="set-up-engagements-for-on-site-or-combined-campaigns" />

## Configure engajamentos para campanhas on-site ou combinadas

No contexto de campanhas on-site e combinadas, todos os eventos de engajamento se originam nas propriedades do colaborador, como seu aplicativo, site ou sistemas na loja. Esses eventos de engajamento geralmente são coletados usando o SDK da AppsFlyer ou enviados por fontes de dados personalizadas e são atribuídos exclusivamente à atividade do usuário no site.

<div id="1-prepare-engagement-data" />

<Accordion title="1. Prepare os dados de engajamento">

Antes de configurar a fonte de engajamento personalizada no DCP, você pode fornecer dados de engajamento de uma destas duas formas:

* **Arquivo de fonte personalizada:** Crie um arquivo de fonte de engajamento e faça upload dele para o seu serviço de nuvem. Para mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-engagement-source-scheme">Preparar arquivos de fonte personalizados para engajamentos</Anchor>.
* **SDK da AppsFlyer:** Integre o SDK da AppsFlyer ao seu aplicativo para enviar automaticamente eventos in-app de engajamento ao DCP. Para mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-engagement-inapp-events">Preparar eventos in-app para engajamentos</Anchor>.

</Accordion>

<div id="2-open-engagement-settings" />

<Accordion title="2. Abra as configurações de engajamento">

Na página **Configurações de mensuração**, você configura, como parte da configuração da mensuração da colaboração, como os engajamentos são coletados e atribuídos.

Para abrir a página **Configurações de mensuração**, siga estas etapas:

1. Na AppsFlyer, no menu lateral, vá para **Colaborar** > **Data Clean Room**.
2. Na página **Plataforma de colaboração de dados**, selecione a colaboração que você deseja.
3. Na parte inferior da página de colaboração, clique em **Configurar mensuração.**
   * Se o link estiver esmaecido, configure as <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources">fontes de dados</Anchor> e as <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-build-and-activate-audiences">audiências</Anchor> da colaboração.
4. Na página **Configurações de mensuração**, clique no painel **Engajamentos** para abrir a caixa de diálogo **Engajamentos**.

   <div id="note" />

   > 📘 **Nota**
   >
   > * Se a caixa de diálogo **Engajamentos** estiver bloqueada, isso significa que a tarefa de Engajamentos foi atribuída ao seu colaborador e que você não pode visualizar seu conteúdo. Se você for o proprietário da colaboração, poderá desbloqueá-la reatribuindo a tarefa a si mesmo. No entanto, todas as configurações anteriores serão excluídas, e a tarefa será redefinida.
   > * Se o painel **Engagements** estiver esmaecido, peça ao proprietário da colaboração para atribuir a você a tarefa de Engagements.


</Accordion>

<div id="3-set-data-provision-method" />

<Accordion title="3. Definir método de provisionamento de dados">

Os dados de engajamento são fornecidos ao DCP por meio de eventos in-app, fonte personalizada ou ambos:

* **Eventos in-app** — a origem dos dados de eventos de engajamento é o SDK da AppsFlyer integrado ao seu app mobile. O SDK envia eventos de engajamento em tempo real do seu aplicativo sempre que o usuário realiza uma ação definida.
* **Fonte personalizada** — a origem dos eventos de engajamento é um arquivo de fonte personalizada armazenado na sua nuvem.

Para configurar o método de provisionamento de engajamento no DCP, siga estas etapas:

1. Na janela **Engagements**, selecione o tipo de provisionamento de engajamento: eventos in-app, arquivo de fonte personalizada ou ambos.
2. Dependendo do seu método de provisionamento, insira os seguintes detalhes:
   * **Eventos na Aplicação:**
     1. Selecione o aplicativo que envia os eventos in-app contendo os dados de engajamento.
     2. Na lista **Select ad engagement event**, selecione qual dos eventos in-app enviados pelo SDK da AppsFlyer é o evento de engajamento.
     3. Na lista **Select advertised item (SKU)**, selecione o parâmetro no evento in-app que contém o valor de SKU.
   * **Fonte personalizada:**
     1. Clique em + **Nova fonte de engajamento**.
     2. Na janela **Nova fonte de engajamento**, insira o nome da fonte de engajamento no campo **Nome da fonte**, de acordo com os <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources#requisitos-e-diretrizes">requisitos e diretrizes</Anchor>.
3. Clique em **próximo**.

</Accordion>

<div id="4-set-source-location" />

<Accordion title="4. Set source location">

Se uma fonte personalizada for usada para fornecer eventos de engajamento ao DCP, defina os detalhes que permitem ao DCP acessá-la no seu serviço de nuvem.

1. Na etapa **Set source location** , selecione a conexão a partir da qual a fonte é acessada.
   * Se não houver conexões configuradas na sua conta, a janela **New connection** será aberta, solicitando que você crie uma.
   * Se você tiver conexões existentes, mas quiser usar uma nova, abra a lista **Selecionar conexão** e selecione **+ Nova conexão.**
2. Configure os detalhes de acesso à fonte de acordo com sua nuvem:
   * <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources#locais-de-origem-no-bigquery">BigQuery</Anchor>
   * <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources#locais-de-origem-no-snowflake">Snowflake</Anchor>
   * <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources#locais-de-origem-em-buckets-de-armazenamento-em-nuvem">Amazon S3 e GCS</Anchor>
   * <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources#local-da-fonte-como-arquivos-locais">Sistema de arquivos local</Anchor>
3. Selecione como os novos dados devem ser tratados. Para mais informações, consulte: <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources#step-3-set-source-update-method">Definir método de sincronização da fonte</Anchor>.
4. Clique em **próximo**.

</Accordion>

<div id="5-map-engagement-source-fields" />

<Accordion title="5. Mapear campos da fonte de engajamento">

Se uma fonte personalizada for usada para fornecer eventos de engajamento ao DCP, mapeie os campos da sua fonte de engajamento personalizada para os campos correspondentes no DCP.

<div id="note-1" />

> 📘 **Nota**
>
> O **banco de dados de eventos de conversão do DCP** armazena todos os eventos de conversão da colaboração atual em um esquema unitário, incluindo eventos de conversão originados de **eventos in-app** ou de **campanhas off-site** (se você estiver executando uma campanha combinada on-site/off-site).

**Carregar campos da fonte de engajamento**

Se os campos da fonte de engajamento ainda não estiverem carregados, talvez seja necessário carregá-los manualmente para mapeá-los para os campos do DCP.

Para carregar os campos da fonte de engajamento, siga estas etapas:

1. Na etapa **Map source fields**, clique **Load fields from source**.
2. Para saber como carregar campos manualmente, consulte: <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources#1-carregar-seus-campos-de-fonte">Carregar seus campos de fonte</Anchor>.

**Mapeamento automático de campos de engajamento**

Quando os campos da fonte de engajamento são carregados, o DCP os mapeia automaticamente para os campos correspondentes do DCP. O mapeamento automático pode levar até 10 segundos. Um banner exibe o resultado do mapeamento, mostrando quantos campos foram mapeados e listando todas as colunas da fonte que não puderam ser correspondidas.

Para acionar o mapeamento automático novamente, clique em **Update mapping**.

**Mapear campos de engajamento**

Se os campos da fonte de engajamento estiverem carregados, você poderá mapeá-los para os campos do DCP.

Para mapear os campos personalizados da fonte de engajamento, siga estas etapas

1. Se você estiver configurando uma **On-site and Off-site campaign** combinada, na etapa **Map source fields**, expanda o **Data for on-site attribution;** caso contrário, pule para a etapa abaixo.
2. Mapeie todos os campos obrigatórios sob **Required**.
3. (Opcional) Expanda **Optional enrichment data** para mapear campos adicionais.
4. Clique em **Salvar**. A mensagem **`{source name}` source created** é exibida.[<Image alt="" src="https://files.readme.io/7741040e43860b110ad1ffa63a55dc08c51cf595717c2fde28f8e7501a1fddfc-38345272613265.png" width="40.62%" />](https://files.readme.io/7741040e43860b110ad1ffa63a55dc08c51cf595717c2fde28f8e7501a1fddfc-38345272613265.png)

</Accordion>

<div data-zendesk-anchors="prerequisites=pr%C3%A9-requisitos h_01K3EFVGA56P7FB605JY1BQ34M=pr%C3%A9-requisitos set-up-engagements-for-onsite-or-combined-campaigns=configure-engajamentos-para-campanhas-on-site-ou-combinadas h_01K3EFVGA6GT10BXJYE9SFM9TE=configure-engajamentos-para-campanhas-on-site-ou-combinadas h_01K3EFVGA6NM4YKZ8MEEYXX58B=1-prepare-engagement-data h_01K3EFVGA65CFME4H3ZC89X471=2-open-engagement-settings h_01K3EFVGA618KT7PGSVQXF6JSV=nota h_01K3EFVGA6BKGAS5GZR3GW2N2M=3-set-data-provision-method h_01K3EFVGA64CQTKZ8C227042PY=4-set-source-location h_01K3EFVGA6J7PX1QE8TRA42QEY=5-map-engagement-source-fields h_01K3EFVGA6E3WH7FEYCW09P74V=nota-1" />
