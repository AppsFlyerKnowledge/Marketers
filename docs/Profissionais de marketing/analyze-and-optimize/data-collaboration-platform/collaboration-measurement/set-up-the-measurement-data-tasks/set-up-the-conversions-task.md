---
title: Configure a tarefa de conversão
metadata:
  keywords:
    - Marketers
    - Retail Media Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Retail Media Measurement
  created_at: '2025-08-18T10:13:32Z'
  edited_at: '2026-08-19T00:06:05Z'
  id: 38187770114449
  locale: pt
  section: Set up the measurement data tasks
  section_id: 38035061674769
  url: https://support.appsflyer.com/hc/pt/articles/38187770114449
---
> **Em resumo:** :AAG: Saiba como configurar eventos de conversão para campanhas on-site e off-site.

Os <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#conversions">eventos de conversão</Anchor> capturam ações valiosas pós-engajamento, como compras, em várias configurações de campanha. Embora a estrutura e o conteúdo de cada evento de conversão permaneçam consistentes, a forma como as conversões são mensuradas, atribuídas e compartilhadas varia dependendo de se tratar de uma campanha <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#on-site-campaigns">on-site</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#off-site-campaigns">off-site</Anchor> ou <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#on-site-and-off-site-campaigns">on-site e off-site</Anchor>. Este artigo explica como configurar a tarefa de conversões para cada tipo de campanha.

## Pré-requisitos

Antes que a tarefa de conversões possa ser configurada, o proprietário da colaboração precisa atribuí-la ao colaborador que possui a plataforma em que os eventos de conversão são gerados. Para obter mais informações, consulte Atribuir tarefas de configuração

## Configure conversões de campanhas on-site

No contexto de campanhas on-site, todos os eventos de conversão se originam nas propriedades do colaborador, como o aplicativo, o site ou os sistemas de loja física. Esses eventos de conversão geralmente são coletados usando o SDK da AppsFlyer ou enviados por fontes de dados personalizadas e atribuídos exclusivamente a engajamentos de usuários on-site.

Para configurar conversões on-site, siga estas etapas:

1. [Preparar dados de conversão](#preparar-dados-de-conversao)
2. [Abrir configurações de conversão](#abrir-configuracoes-de-conversao)
3. [Definir método de fornecimento de dados](#definir-metodo-de-fornecimento-de-dados-de-conversao)
4. [Set source location](#definir-local-da-fonte-de-conversao)
5. [Mapear campos da fonte de conversão on-site](#mapear-campos-da-fonte-de-conversao-on-site)

## Configure conversões de campanhas off-site

No contexto de campanhas off-site, os eventos de conversão ocorrem nas propriedades do colaborador, como o aplicativo, o site ou os sistemas de loja física, mas a atribuição se baseia em engajamentos que ocorreram em plataformas externas, como Meta ou Google.

Para configurar conversões off-site, siga estas etapas:

1. [Preparar dados de conversão](#preparar-dados-de-conversao)
2. [Abrir configurações de conversão](#abrir-configuracoes-de-conversao)
3. [Definir método de fornecimento de dados de conversão](#definir-metodo-de-fornecimento-de-dados-de-conversao)
4. [Set source location](#definir-local-da-fonte-de-conversao)
5. [Mapear campos da fonte de conversão off-site](#mapear-campos-da-fonte-de-conversao-off-site)

## Configurar conversões on-site e off-site

Em configurações combinadas de campanhas on-site e off-site, as conversões das propriedades do colaborador podem ser atribuídas a engajamentos de fontes on-site ou off-site.

Para configurar conversões on-site e off-site, siga estas etapas:

1. [Preparar dados de conversão](#preparar-dados-de-conversao)
2. [Abrir configurações de conversão](#abrir-configuracoes-de-conversao)
3. [Definir método de fornecimento de dados de conversão](#definir-metodo-de-fornecimento-de-dados-de-conversao)
4. [Set source location](#definir-local-da-fonte-de-conversao)
5. [Mapear campos da fonte de conversão on-site](#mapear-campos-da-fonte-de-conversao-on-site)
6. [Mapear campos da fonte de conversão off-site](#mapear-campos-da-fonte-de-conversao-off-site)

## Atividades de configuração

<div id="prepare-conversion-data" />

<Accordion title="Preparar dados de conversão">

Antes de configurar a fonte de conversão personalizada no DCP, você pode fornecer os dados de conversão de uma destas duas formas:

* **Arquivo de fonte personalizado:** Crie um arquivo de fonte de conversão e faça upload dele para o seu serviço de nuvem. Para mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#the-conversion-source-scheme">Prepare arquivos de fonte personalizados para conversões</Anchor>.
* **SDK da AppsFlyer:** Integre o SDK da AppsFlyer ao seu aplicativo para enviar automaticamente eventos de conversão in-app ao DCP. Para mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement#prepare-conversion-inapp-events">Prepare eventos in-app para conversões.</Anchor>

</Accordion>

<div id="open-conversion-settings" />

<Accordion title="Abra as configurações de conversão">

A página **Configurações de mensuração** é onde você configura como conversões e engajamentos são coletados, atribuídos e compartilhados com parceiros de mídia como parte da configuração da sua colaboração off-site.

Para abrir a **configurações de mensuração** página, siga estas etapas:

1. Na AppsFlyer, no menu lateral, vá para **Colaborar** > **Data Clean Room**.
2. Na **Data Collaboration Platform** página, selecione a colaboração que você deseja configurar.
3. Na parte inferior da página de colaboração, clique **Set up measurement.** (Se o link estiver desativado, configure as <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources">fontes de dados</Anchor> e <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-build-and-activate-audiences">audiências</Anchor>.)
4. Na página **Configurações de mensuração** , clique no painel **Conversões** para abrir a caixa de diálogo **Conversões**.

   > 📘 **Nota**
   >
   > * Se a caixa de diálogo **Conversão** estiver bloqueada, isso significa que a tarefa de **Conversão** foi atribuída ao seu colaborador e que você não pode visualizar seu conteúdo. Se você for o proprietário da colaboração, poderá desbloqueá-la reatribuindo a tarefa a si mesmo. No entanto, todas as configurações anteriores serão excluídas, e a tarefa será redefinida.
   > * Se o painel **Conversão** estiver esmaecido, peça ao proprietário da colaboração para atribuir a você a tarefa de conversão.


</Accordion>

<div id="set-conversion-data-provision-method" />

<Accordion title="Definir método de fornecimento de dados de conversão">

Os dados de conversão são fornecidos ao DCP por eventos in-app, fonte personalizada ou ambos:

* **Eventos in-app** — A origem dos dados do evento de conversão é o SDK da AppsFlyer integrado ao seu aplicativo mobile. O SDK envia eventos de conversão em tempo real sempre que o usuário realiza uma atividade de conversão.
* **Fonte personalizada** — A origem dos eventos de conversão é um arquivo de fonte personalizado armazenado na sua nuvem.

Para configurar o método de fornecimento de conversão no DCP, siga estas etapas:

1. Na caixa de diálogo **Conversões** , selecione o tipo de fornecimento de conversão: eventos in-app, arquivo de fonte personalizado ou ambos.
2. Dependendo do seu método de fornecimento, insira os seguintes detalhes:
   * **Eventos na Aplicação:**
     1. Selecione o aplicativo que envia os eventos in-app contendo os dados de conversão.
     2. Na lista **Selecionar evento de conversão** , selecione qual dos eventos in-app enviados pelo SDK da AppsFlyer é o evento de conversão.
     3. No campo **Item anunciado (SKU)** escolha o parâmetro que contém os SKUs dos eventos de conversão.
   * **Fonte personalizada:**
     1. Clique em + **Nova fonte de conversão**.
     2. Na caixa de diálogo **Nova fonte de conversão** , insira o nome da fonte de conversão no campo **Nome da fonte** de acordo com os <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources#requisitos-e-diretrizes">requisitos e diretrizes</Anchor>.
3. Clique em **Próximo**.

</Accordion>

<div id="set-conversion-source-location" />

<Accordion title="Definir local da fonte de conversão">

Se uma fonte personalizada for usada para fornecer eventos de conversão, habilite o DCP para acessá-los seguindo estas etapas:

1. Na etapa **Definir local da fonte** , selecione a conexão a partir da qual a fonte é acessada.
   * Se não houver conexões configuradas na sua conta, a caixa de diálogo **Nova conexão** será aberta, solicitando que você crie uma.
   * Se você tiver conexões existentes, mas quiser usar uma nova, abra a lista **Selecionar conexão** e selecione **+ Nova conexão.**
2. Configure os detalhes de acesso à fonte de acordo com sua nuvem:
   * <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources#locais-de-origem-no-bigquery">BigQuery</Anchor>
   * <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources#locais-de-origem-no-snowflake">Snowflake</Anchor>
   * <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources#locais-de-origem-em-buckets-de-armazenamento-em-nuvem">Amazon S3 e GCS</Anchor>
   * <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources#local-da-fonte-como-arquivos-locais">Sistema de arquivos local</Anchor>
3. Selecione como os novos dados devem ser tratados. Para mais informações, consulte: <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources#step-3-set-source-update-method">Definir método de sincronização da fonte</Anchor>.
4. Clique em **Próximo**.

</Accordion>

<div id="map-onsite-conversion-source-fields" />

<Accordion title="Mapear campos da fonte de conversão no site">

Se uma fonte personalizada for usada para fornecer eventos de conversão ao DCP, mapeie os campos da sua fonte de conversão personalizada no site para os campos correspondentes do DCP.

> 📘 **Nota**
>
> O **banco de dados de eventos de conversão do DCP** armazena todos os eventos de conversão da colaboração atual em um esquema unificado, incluindo eventos de conversão originados de **Eventos in-app** ou de **campanhas off-site** (se você estiver executando uma campanha combinada on-site/off-site).

**Carregar campos da fonte de conversão**

Se os campos da fonte de conversão ainda não estiverem carregados, talvez seja necessário carregá-los manualmente para mapeá-los para os campos do DCP.

Para carregar os campos da fonte de conversão, siga estas etapas:

1. Na etapa **Mapear campos da fonte** , clique **Carregar campos da fonte**.
2. Para informações sobre como carregar campos manualmente, consulte: <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources#1-carregar-seus-campos-de-fonte">Carregar seus campos da fonte</Anchor>.

**Mapeamento automático de campos de conversão**

Quando os campos da fonte de conversão são carregados, o DCP os mapeia automaticamente para os campos DCP correspondentes. O mapeamento automático pode levar até 10 segundos. Um banner exibe o resultado do mapeamento, mostrando quantos campos foram mapeados e listando quaisquer colunas da fonte que não puderam ser correspondidas.

Para acionar novamente o mapeamento automático, clique em **Atualizar mapeamento**.

**Mapear campos de conversão**

Se os campos da fonte de conversão estiverem carregados, você poderá mapeá-los para os campos do DCP.

Para mapear os campos personalizados de fonte de conversão, siga estas etapas

1. Se você estiver configurando uma **campanha combinada** **no site e fora do site**, expanda **Dados para atribuição no site;** caso contrário, pule para a etapa abaixo.
2. Mapeie todos os campos obrigatórios sob **Obrigatório**.
3. (Opcional) Expanda **Dados opcionais de enriquecimento** para mapear campos adicionais.

   > 📘 **Nota**
   >
   > Se a campanha estiver combinada com uma campanha off-site e você mapear um campo (por exemplo, Event ID) que já está mapeado em um canal off-site, você receberá o prompt **Override field?** . Clique **Yes, continue** para confirmar e aplicar o mapeamento em todos os canais.

4. Clique em **Salvar**. A mensagem **`{source name}` source created** é exibida.[<Image alt="" src="https://files.readme.io/7741040e43860b110ad1ffa63a55dc08c51cf595717c2fde28f8e7501a1fddfc-38345272613265.png" width="40.33%" />](https://files.readme.io/7741040e43860b110ad1ffa63a55dc08c51cf595717c2fde28f8e7501a1fddfc-38345272613265.png)

</Accordion>

<div id="map-offsite-conversion-source-fields" />

<Accordion title="Mapear campos de fonte de conversão fora do site">

Se uma fonte personalizada for usada para fornecer eventos de conversão de campanhas fora do site, mapeie os campos da sua fonte personalizada de conversão fora do site para os campos DCP correspondentes.

> 📘 **Nota**
>
> O **banco de dados de eventos de conversão do DCP** armazena todos os eventos de conversão da colaboração atual em um esquema unificado, incluindo eventos de conversão originados de **eventos in-app** ou **campanhas no site** (se você estiver executando uma campanha combinada no site e fora do site).

**Carregar campos de fonte de conversão**

Se os campos da fonte de conversão ainda não estiverem carregados, talvez seja necessário carregá-los manualmente para mapeá-los para os campos DCP.

Para carregar campos de fonte de conversão, siga estas etapas:

1. Na etapa **Mapear campos da fonte**, clique **Carregar campos da fonte**.
2. Para obter informações sobre como carregar campos manualmente, consulte: <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources#1-carregar-seus-campos-de-fonte">Carregar seus campos da fonte</Anchor>.

**Mapear campos de conversão automaticamente**

Quando os campos da fonte de conversão são carregados, o DCP os mapeia automaticamente para os campos correspondentes no DCP. O mapeamento automático pode levar até 10 segundos. Um banner exibe o resultado do mapeamento, mostrando quantos campos foram mapeados e listando as colunas da fonte que não puderam ser correspondidas.

Para acionar novamente o mapeamento automático, clique em **Atualizar mapeamento**.

**Mapear campos de conversão**

Se os campos da fonte de conversão estiverem carregados, você poderá mapeá-los para os campos DCP. Quando você compartilha dados de conversão com plataformas externas, como Meta ou Google, a AppsFlyer envia apenas os campos necessários para que cada parceiro compare as conversões com os próprios eventos de engajamento de campanha.

Os campos mostrados aqui dependem dos tipos de fonte de conversão que você selecionou durante a configuração:

1. Se você estiver configurando uma **campanha combinada** **no site e fora do site**, expanda **Dados para atribuição fora do site;** caso contrário, pule para a etapa abaixo.
2. Ative **Meta Ads** ou **Google Ads**, dependendo das suas fontes de dados:

   > 📘 **Nota**
   >
   > Quando você compartilha dados de conversão com plataformas externas como Meta ou Google, a AppsFlyer envia apenas os campos necessários para que cada parceiro relacione as conversões aos próprios eventos de engajamento de campanha.


   **Mapeamento de campos do Meta Ads**

   Mapeie os campos em **Campos de fonte** para os campos correspondentes em **Campos de DCP**. Os campos de DCP listados aqui refletem os parâmetros obrigatórios do Meta Ads.

   * Mapeie todos os seis campos obrigatórios em **Required**.
   * Expanda **Optional enrichment data** para mapear campos adicionais (por exemplo, First name, IDFA e e-mail).

   **Mapeamento de campos do Google Ads**

   Mapeie os campos em **Campos de fonte** para os campos correspondentes em **Campos de DCP**. Os campos de DCP listados aqui refletem os parâmetros obrigatórios do Google Ads.

   * Mapeie todos os cinco campos obrigatórios em **Required**.
   * Mapeie pelo menos um identificador em **At least one is required**.
   * Expanda **Optional enrichment data** para mapear campos recomendados, como receita, user agent do cliente ou identificadores com hash.

   > 📘 **Nota**
   >
   > Se a campanha estiver combinada com uma campanha fora do site e você mapear um campo (por exemplo, ID do evento) que já esteja mapeado em um canal fora do site, a mensagem **Substituir campo?** será exibida . Clique **Sim, continuar** para confirmar e aplicar o mapeamento em todos os canais.

3. Clique **Save** para concluir a configuração da fonte.

</Accordion>

<div data-zendesk-anchors="prerequisites=pr%C3%A9-requisitos h_01K38T7G97M4403CPYYVG4F0SG=pr%C3%A9-requisitos set-up-onsite-campaign-conversions=configure-convers%C3%B5es-de-campanhas-on-site h_01K38T7G970AVGNTPN6JN7E5SC=configure-convers%C3%B5es-de-campanhas-on-site set-up-offsite-campaign-conversions=configure-convers%C3%B5es-de-campanhas-off-site h_01K38T7G97KP9NHFPPFG3F4992=configure-convers%C3%B5es-de-campanhas-off-site set-up-onsite-and-offsite-conversions=configurar-convers%C3%B5es-on-site-e-off-site h_01K38T7G97ZXZZQ48ZRY4A019F=configurar-convers%C3%B5es-on-site-e-off-site configuration-activities=atividades-de-configura%C3%A7%C3%A3o h_01K38T7G975KF5036EZTNA4NYJ=atividades-de-configura%C3%A7%C3%A3o h_01K38T7G974NCK1XE35KG4CF79=prepare-conversion-data h_01K38T7G97156TM1AJD7HTNZ2K=open-conversion-settings h_01K38T7G97VGR60QBE1YP565XQ=nota h_01K38T7G975CFGND94MK9B4PZS=set-conversion-data-provision-method h_01K38T7G979CKD39QCFV7ZESY5=set-conversion-source-location h_01K38T7G97XNE4AS4YE64QWK80=map-onsite-conversion-source-fields h_01K38T7G9738EZBAM1XVMASGK0=nota-3 h_01K38T7G97HV111FQ6CQCQMXHH=nota-2 h_01K38T7G976GHY5W6YDHJD1DY7=map-offsite-conversion-source-fields h_01K38T7G97WFBS0HHX1ASR2F5W=nota-3 h_01K38T7G97MZF6RYY3YRG2EVPQ=nota-4 h_01K38T7G976MJZWGDYMK6EB76A=nota-5" />
