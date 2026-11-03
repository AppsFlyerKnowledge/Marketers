---
title: Configure a tarefa de campanhas
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
  created_at: '2025-08-18T11:31:27Z'
  edited_at: '2026-08-18T00:06:18Z'
  id: 38190881693969
  locale: pt
  section: Set up the measurement data tasks
  section_id: 38035061674769
  url: https://support.appsflyer.com/hc/pt/articles/38190881693969
---
> **Em resumo:** Saiba como configurar a fonte da campanha para campanhas on-site, off-site e combinadas (campanhas on-site e off-site).

A <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#campaign-mapping">fonte da campanha</Anchor> conecta eventos de conversão on-site às respetivas campanhas off-site, on-site e combinadas, permitindo uma atribuição precisa e relatórios de performance. Ao contrário de outras tarefas no DCP (como conversões ou engajamentos), a **tarefa de campanhas é idêntica tanto para campanhas on-site quanto para off-site**. Isso significa que você segue o mesmo processo de configuração independentemente do tipo de campanha.

## Pré-requisitos

Antes que a tarefa de campanhas possa ser configurada, o proprietário da colaboração precisa atribuí-la ao colaborador que é proprietário da plataforma em que os eventos de conversão são gerados. Para obter mais informações, consulte Atribuir tarefas de configuração

## Configure a tarefa de campanhas

A fonte de campanhas vincula eventos internos de conversão a identificadores no nível da campanha (por exemplo, ID da campanha) no contexto de campanhas on-site, off-site ou combinadas. As informações da campanha que você define nesta tarefa são enviadas ao DCP por meio de uma fonte de dados personalizada.

<div id="1-prepare-campaign-data" />

<Accordion title="1. Preparar dados da campanha">

Antes de configurar a fonte da campanha no DCP, prepare a fonte personalizada da campanha e faça upload dela para o seu serviço de nuvem. Para detalhes sobre o esquema de mapeamento e como carregar a fonte da campanha para o seu ambiente de nuvem, consulte <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-a-fonte-de-mapeamento-da-campanha">Preparar fonte da campanha</Anchor>.

Para configurar a fonte da campanha no DCP:

1. Acesse a página de **mensuração de colaboração**.
2. Clique em **Campanhas**.
3. Na caixa de diálogo **Campanhas**, clique em **+ Nova fonte de campanha**.
4. Na caixa de diálogo **Nova fonte de campanha**, insira um nome no campo **Nome da fonte** de acordo com os <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources#requisitos-e-diretrizes">requisitos e diretrizes</Anchor>.
5. Clique em **próximo**.

</Accordion>

<div id="2-open-campaigns-settings" />

<Accordion title="2. Abrir configurações de campanhas">

Na página **Configurações de mensuração**, você configura como as campanhas são coletadas, atribuídas e conectadas aos dados de parceiros de mídia como parte da configuração da sua colaboração.

Para abrir a página **Configurações de mensuração**, siga estas etapas:

1. Na AppsFlyer, no menu lateral, vá para **Colaborar** > **Data Clean Room**.
2. Na página **Plataforma de colaboração de dados**, selecione a colaboração que você deseja.
3. Na parte inferior da página de colaboração, clique em **Configurar mensuração.**
   * Se o link estiver desativado, configure as <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources">fontes de dados</Anchor> e as <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-build-and-activate-audiences">audiências</Anchor> da colaboração.
4. Na página **Configurações de mensuração**, clique no painel **Campanhas** para abrir a caixa de diálogo **Campanhas**.

   > 📘 **Nota**
   >
   > * Se a caixa de diálogo **Campanhas** estiver bloqueada, isso significa que a tarefa **Campanhas** foi atribuída ao seu colaborador e você não pode ver o conteúdo dela. Se você for o proprietário da colaboração, poderá desbloqueá-la reatribuindo a tarefa a si mesmo. No entanto, todas as configurações anteriores serão excluídas, e a tarefa será redefinida.
   > * Se o painel **Campanhas** estiver esmaecido, peça ao proprietário da colaboração para atribuir a você a tarefa Campanhas.


</Accordion>

<div id="3-set-campaign-data-provision-method" />

<Accordion title="3. Definir método de fornecimento de dados de campanha">

Os dados da campanha são fornecidos ao DCP em um arquivo de fonte personalizado armazenado na sua nuvem.

Para configurar o método de fornecimento de conversão no DCP, siga estas etapas:

1. Na caixa de diálogo **Campanhas** , clique + **Nova fonte de campanha**.
2. Na caixa de diálogo **Nova fonte de conversão** , na etapa **Nome da fonte**, defina o nome da fonte da campanha no **Nome da fonte** campo, de acordo com os <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources#requisitos-e-diretrizes">requisitos e diretrizes</Anchor>.
3. Clique **Próximo**.

</Accordion>

<div id="4-set-source-location" />

<Accordion title="4. Set source location">

Defina o local da fonte da campanha no seu serviço de nuvem.

1. Na etapa **Definir local da fonte**, selecione a conexão por meio da qual a fonte é acessada.
   * Se não houver conexões configuradas na sua conta, a caixa de diálogo **Nova conexão** será aberta, solicitando que você crie uma.
   * Se você tiver conexões existentes, mas quiser usar uma nova, abra a lista **Selecionar conexão** e selecione **+ Nova conexão**.
2. Configure os detalhes de acesso de acordo com seu serviço de nuvem:
   * <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources#locais-de-origem-no-bigquery">BigQuery</Anchor>
   * <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources#locais-de-origem-no-snowflake">Snowflake</Anchor>
   * <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources#locais-de-origem-em-buckets-de-armazenamento-em-nuvem">Amazon S3 e GCS</Anchor>
   * <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources#local-da-fonte-como-arquivos-locais">Sistema de arquivos local</Anchor>
3. Selecione como os novos dados devem ser processados. Para mais informações, consulte: <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources#step-3-set-source-update-method">Definir método de sincronização da fonte</Anchor>.
4. Clique em **próximo**.

</Accordion>

<div id="5-map-campaign-fields" />

<Accordion title="5. Mapear campos da campanha">

Se uma fonte personalizada for usada para fornecer eventos de conversão ao DCP, mapeie os campos da sua fonte de conversão personalizada no site para os campos correspondentes no DCP.

**Carregar campos da fonte de campanha**

Se os campos da fonte de campanha ainda não estiverem carregados, talvez seja necessário carregá-los manualmente para mapeá-los aos campos do DCP.

Para carregar os campos da fonte de conversão, siga estas etapas:

1. Na etapa **Mapear campos da fonte**, clique **Carregar campos da fonte**.
2. Para informações sobre como carregar campos manualmente, consulte: <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources#1-carregar-seus-campos-de-fonte">Carregar os campos da sua fonte</Anchor>.

**Mapear automaticamente os campos da campanha**

Quando os campos de fonte da campanha são carregados, o DCP os mapeia automaticamente para os campos correspondentes do DCP. O mapeamento automático pode levar até 10 segundos. Um banner exibe o resultado do mapeamento, mostrando quantos campos foram mapeados e listando as colunas de fonte que não puderam ser correspondidas.

Para acionar novamente o mapeamento automático, clique em **Atualizar mapeamento**.

**Mapear campos da campanha**

Se os campos de fonte de conversão forem carregados, você poderá mapeá-los para os campos do DCP.

Para mapear os campos de fonte personalizados das campanhas, siga estas etapas:

1. Mapeie os campos em **Campos de fonte** para os campos correspondentes em **Campos do DCP**.
   * Para ver uma lista de campos e descrições, consulte O esquema das campanhas.
2. Clique em **Guardar**. A mensagem **campaign\_mapping source created** é exibida.

</Accordion>

<div id="5-align-collaborator-name" />

<Accordion title="6. Alinhar nome do colaborador">

A etapa final após concluir a tarefa de campanhas é alinhar o nome do colaborador. Isso é necessário porque cada conta DCP tem apenas uma fonte de campanha. Como o proprietário da conta pode manter várias colaborações com diferentes colaboradores, o DCP precisa saber qual colaborador está ativo na colaboração atual.

Para alinhar o nome do colaborador:

* Na caixa de diálogo **Campanhas**, em **Alinhar nomes de colaboradores**, selecione o colaborador da colaboração atual.

</Accordion>

<div data-zendesk-anchors="prerequisites=pr%C3%A9-requisitos h_01K3BEVMGMPENVYY18EB0ANQCP=pr%C3%A9-requisitos set-up-the-campaigns-task=configure-a-tarefa-de-campanhas h_01K3BEVMGM6EEP6DY54HDDVKTR=configure-a-tarefa-de-campanhas h_01K3BEVMGMC9C09FJTRVMS2J32=1-prepare-campaign-data h_01K3BEVMGMT28RXKBN31EBAFYJ=2-open-campaigns-settings h_01K3BEVMGMGV8GVGKZFDCSC0DF=nota h_01K3BEVMGM2D9TA52F9F36Z31W=3-set-campaign-data-provision-method h_01K3BEVMGM67JV6VT6TBXTYACC=4-set-source-location h_01K3BEVMGNNFYFF939RHB8Z8E1=5-map-campaign-fields h_01K3BEVMGN4MAV9B0HP2TK5XCC=5-align-collaborator-name" />
