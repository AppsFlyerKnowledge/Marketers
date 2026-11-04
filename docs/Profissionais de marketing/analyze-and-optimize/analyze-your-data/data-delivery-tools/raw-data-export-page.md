---
title: Página de exportação de dados brutos
metadata:
  keywords:
    - ad networks
    - Advertisers
    - Agencies
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Agencies
    - Raw Reports
    - Ad Networks
  created_at: '2020-05-11T22:25:33Z'
  edited_at: '2026-08-19T00:04:30Z'
  id: 360008613838
  locale: pt
  section: Data delivery tools
  section_id: 6550995484561
  url: https://support.appsflyer.com/hc/pt/articles/360008613838
---
> **Visão geral:** Descarregar relatórios de dados brutos em ficheiros CSV. Até 1 milhão de linhas por transferência. Restrinja os relatórios aos dados necessários usando filtros.

A ilustração seguinte é apresentada na primeira vez que acede à página **Exportação de dados brutos**; a página **Os meus relatórios** é exibida se tiver relatórios prontos para descarregar ou duplicar.

[![RawDataSplash.png](https://files.readme.io/febb6a32a3a7b86c5b396cd77ff9e7968057f57ed20fd991d6dbb4899d5eaf07-41225791757969.png)](https://files.readme.io/febb6a32a3a7b86c5b396cd77ff9e7968057f57ed20fd991d6dbb4899d5eaf07-41225791757969.png)

**Os meus relatórios**

A página **Os meus relatórios** lista os relatórios previamente gerados e disponíveis para descarregar, duplicar ou ambos. Os relatórios listados foram gerados nos últimos 90 dias; o período de descarregamento é de 7 dias. Após 7 dias, se ainda precisar do relatório, deve gerá-lo novamente.

Para uma descrição dos relatórios de dados brutos, consulte a <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview">Visão geral dos relatórios de dados brutos</Anchor>.

Para gerar ou descarregar relatórios, consulte a secção de procedimentos deste artigo.

[![MyReportsRawDataExport.png](https://files.readme.io/1f82e365a7e6cd802ee899666b800be357ea5e99aa6909e75b1fa39a2e4a164e-41225791760145.png)](https://files.readme.io/1f82e365a7e6cd802ee899666b800be357ea5e99aa6909e75b1fa39a2e4a164e-41225791760145.png)

<div id="raw-data-export-page-features-and-filter-options" />

<Accordion title="Características da página de exportação de dados brutos e opções de filtro">

A página de exportação de dados brutos oferece relatórios com as características listadas na tabela seguinte.

<Table>
  <thead>
    <tr>
      <th>
        Característica
      </th>
      <th>
        Observações
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="report-categories"></span>
        Categorias de relatório
      </td>
      <td>
        Varia de acordo com o seu plano de subscrição.
      </td>
    </tr>
    <tr>
      <td><span id="date-range"></span>
        Intervalo de datas
      </td>
      <td>
        Os relatórios de dados brutos são filtrados por datas de atividade (ocorrência de eventos). Também pode adicionar um filtro para datas de instalação. Consulte a lista de opções de filtro na tabela seguinte.
      </td>
    </tr>
    <tr>
      <td><span id="maximum-number-of-rows"></span>
        Número máximo de linhas
      </td>
      <td>
        1 milhão de linhas
      </td>
    </tr>
    <tr>
      <td><span id="rate-limitation"></span>
        Limitação de taxa
      </td>
      <td>
        Um <Anchor target="_blank" href="/marketers/pt/docs/report-generation-quotas-rate-limitations">mecanismo de quotas</Anchor> limita o número de relatórios que podem ser gerados por dia.
      </td>
    </tr>
    <tr>
      <td><span id="retentionreport-window"></span>
        Janela de retenção/relatório
      </td>
      <td>
        Relatórios relacionados com instalação (instalações, postbacks de instalação) cobrem **60** dos 90 dias anteriores num único download.

        Relatórios relacionados com eventos na aplicação: 31 dos 90 dias anteriores num único download.
      </td>
    </tr>
    <tr>
      <td><span id="filter-options"></span>
        Opções de filtro
      </td>
      <td>
        Os filtros listados estão disponíveis para uso. Em alguns casos, dependendo do filtro, as opções disponíveis são apresentadas. Por exemplo, ao filtrar por localização geográfica, é exibida a lista de países disponíveis.
      </td>
    </tr>
    <tr>
      <td><span id="field-selection"></span>
        Seleção de campos
      </td>
      <td>
        Os campos mais importantes são pré-selecionados. Pode adicionar/remover campos no separador **Campos do relatório**. Alguns campos podem não ser relevantes para um determinado relatório. Ainda assim, tem a opção de selecionar o campo. Fazemos isto para que tenha formatos de relatórios consistentes (colunas).

        Por exemplo, selecionar campos relacionados com fraude (Protect360) no relatório de eventos de aquisição de utilizadores na aplicação resulta em colunas em branco. Estes campos são preenchidos apenas no contexto de relatórios específicos do Protect360.
      </td>
    </tr>
    <tr>
      <td><span id="report-csv-field-order"></span>
        Ordem dos campos no relatório (CSV)
      </td>
      <td>
        As colunas nos relatórios são dispostas conforme a configuração da ordem dos campos. A sequência de colunas [listada numa folha de cálculo](https://docs.google.com/spreadsheets/d/e/2PACX-1vRGYcMOgC5yy_82yn3DWd3ucLE5KtuTA72eJfvu5KVB9fFH_mYwzM3KpR_inQOnat-KzgVjuuvXa6_g/pub?output=xlsx) inclui separadores distintos para as opções legadas e padrão.

        | Configuração | Seleção de campo permitida | Observações |
        | --- | --- | --- |
        | <span id="default"></span>Padrão | Sim | * Os campos selecionados são organizados de acordo com um modelo da AppsFlyer.<br />* A partir de agora, a sequência será mantida. Os campos futuros serão adicionados à direita dos campos atuais. |
        | <span id="alphabetical-az"></span>Alfabético (A-Z) | Sim | Os campos selecionados são ordenados alfabeticamente (crescente). |
        | <span id="alphabetical-za"></span>Alfabético (Z-A) | Sim | Os campos selecionados são ordenados por ordem alfabética inversa (decrescente). |
        | <span id="legacy"></span>Legado | Não | * Os campos são dispostos conforme a sequência de colunas nos relatórios elaborados com a versão anterior da página de exportação de dados.<br />* A seleção dos campos é fixa e não pode ser alterada.<br />* Os relatórios podem variar em função do campo, dependendo do relatório específico. |
      </td>
    </tr>
  </tbody>
</Table>

| Filtro | AppsFlyer | Rede de anúncios | Agência |
| --- | --- | --- | --- |
| Fonte de mídia | Sim | Não | Sim |
| Intervalo de datas da atividade | Sim | Sim | Sim |
| Intervalo de datas da instalação | Sim | Sim | Sim |
| Agência | Sim | Não | Não |
| Geo (território/país) | Sim | Sim | Sim |
| Eventos na aplicação (disponíveis para relatórios de eventos na aplicação) | Sim | Não | Sim |

</Accordion>

<div id="procedures" />

## Procedimentos

<div id="create-a-default-report" />

<Accordion title="Criar um relatório padrão">

Pode criar um relatório com as definições padrão, sem personalizar os campos ou filtros.

**Para criar um relatório padrão:**

1. No AppsFlyer, no menu lateral, selecione **Exportar** > **Exportar Dados Brutos**.
2. Clique em + **Novo relatório**.
3. Passe o cursor sobre o tipo de relatório que deseja gerar e clique em **Criar.**
4. Selecione **Gerar agora** no menu suspenso.
5. Na janela de pop-up, clique em **Gerar agora.** A geração pode levar até 10 minutos.
   * Durante a criação do relatório, pode continuar a trabalhar, gerar relatórios adicionais ou navegar para outras páginas.

**As definições padrão dos filtros do relatório são:**

| Filtro | Configuração padrão |
| --- | --- |
| Datas de atividades | Os últimos 7 dias |
| Número máximo de linhas por ficheiro | 200.000 |
| Fonte de mídia | Todas as fontes de mídia |
| Agência | Todas as agências |
| Geografia | Todas as áreas geográficas |

</Accordion>

<div id="create-a-custom-report" />

<Accordion title="Criar um relatório personalizado">

Pode criar um relatório personalizado ao definir os seus filtros e campos.

**Para criar um relatório personalizado:**

1. No AppsFlyer, no menu lateral, selecione **Exportar** > **Exportar Dados Brutos**.
2. Clique em + **Novo relatório**.
3. Passe o cursor sobre o tipo de relatório que deseja gerar e clique em **Criar.**
4. Selecione **Personalizar** no menu suspenso.
5. Defina os filtros do relatório
   * **Datas da atividade:** Selecione o intervalo de datas da atividade. Pode definir a data específica ou escolher entre opções como personalizado, ontem, últimos 7 dias, etc.
   * **Número máximo de linhas por ficheiro:** [Opcional] Estabeleça o número máximo de linhas que um arquivo pode conter. Escolha entre 100, 200 mil, 500 mil ou 1 milhão de linhas.
   * **Fonte de mídia:** [Opcional] Apenas os eventos atribuídos às fontes de mídia selecionadas serão incluídos no relatório. Pode adicionar uma fonte de mídia à lista clicando em **Adicionar item**.

     <div id="note" />

     > 📘 **Nota**
     >
     > PIDs web de self-reporting network (SRN), como `metaweb_int`, `googleds_int` ou `tiktokweb_int`, não aparecem automaticamente na lista suspensa de canal de mídia. Para filtrar postbacks de SRN da web, clique em **Add item** e insira manualmente o PID do canal de mídia web.

   * **Agência:** [Opcional] Só os eventos atribuídos às agências selecionadas serão incluídos no relatório. Pode adicionar uma agência à lista clicando em **Adicionar item**.
   * **Geográfico:** [Opcional] Só os eventos atribuídos às áreas geográficas selecionadas serão incluídos no relatório.
   * **Filtro específico do tipo de relatório**: Cada tipo de relatório pode ter o seu próprio filtro que permite selecionar critérios de filtragem.
6. [Opcional]: Os relatórios são preenchidos automaticamente com os campos necessários. Pode adicionar ou remover campos da seguinte forma:
   1. Aceda ao separador **Campos do relatório**. Não é possível alterar a seleção de campos obrigatórios.
   2. Selecione ou desmarque os campos conforme necessário.
   3. [Opcional] Defina a **Ordem dos campos do relatório (CSV)** para estabelecer a sequência das colunas.
   4. [Opção] Se necessário, clique em **Restaurar predefinições**.
7. Clique em **Criar.**
   * A página **Os meus relatórios** será apresentada. Inicialmente, o estado indica que o relatório está a ser gerado.
   * A geração pode demorar até 10 minutos.
   * Durante a criação do relatório, pode continuar a trabalhar, gerar relatórios adicionais ou navegar para outras páginas.

</Accordion>

<div id="download-report" />

<Accordion title="Descarregar relatório">

**Para descarregar um relatório**:

1. Na AppsFlyer, na barra lateral, aceda a **Exportar** > **Dados Brutos Exportar.**
2. Clique em ![DownloadIcon.png](https://files.readme.io/6c00f4922fc3a835a856d7fdf527aa32d2f50570710c1527b039f43a7acbba79-41225791763217.png) (descarregar) para descarregar o relatório. Os relatórios gerados estão disponíveis para descarga durante 7 dias.

</Accordion>

<div id="duplicate-and-edit-report-settings" />

<Accordion title="Duplicar e editar definições do relatório">

**Para duplicar e editar definições do relatório:**

1. Na AppsFlyer, na barra lateral, aceda a **Exportar** > **Dados Brutos Exportar.**
2. Clique em ![Duplicate.png](https://files.readme.io/f745081f1bf0c4f5861e275a29048fe84e8020f8b3bf4ebe4ad6a8d9254ab4b5-41225784681233.png) para duplicar as definições do relatório e depois edite as mesmas.
3. Clique em **Criar.** Os relatórios gerados estarão disponíveis durante 7 dias.   
   * A página **Os meus relatórios** será apresentada. Inicialmente, o estado indica que o relatório está a ser gerado.
   * A geração pode demorar até 10 minutos.
   * Durante a criação do relatório, pode continuar a trabalhar, gerar relatórios adicionais ou navegar para outras páginas.

</Accordion>

<div id="additional-information" />

## Informações adicionais

<div id="traits-and-limitations" />

<Accordion title="Características e limitações">

| Caraterística | Observações |
| --- | --- |
| Acesso à rede de anúncios | Sim |
| Acesso da agência | Sim |
| Fuso horário específico da aplicação | Sim |
| Moeda específica da aplicação | Sim |
| Limitações | Até 1 milhão de registos por descarregamento |
| Dados não orgânicos | Disponível |
| Dados orgânicos | Disponível |
| Relevância dos dados | Dependente do relatório |
| Dados históricos | 90 dias anteriores |
| Acesso de utilizador da conta | Utilizadores em <Anchor target="_blank" href="/marketers/pt/docs/user-management">funções com permissões necessárias</Anchor> |
| Envio por email | Não suportado |
| Intervalo de datas da instalação | O intervalo de datas de instalação deve preceder o intervalo de datas de atividade. |
| Relatórios de postback de dados brutos | Os postbacks enviados para parceiros devido a eventos atribuídos a agências não transparentes não são incluídos nos relatórios de postback dos dados brutos do anunciante. |

</Accordion>

<div id="field-sequence-templates" />

<Accordion title="Modelos de sequência de campos">

A configuração da ordem dos campos do relatório permite especificar a sequência das colunas nos relatórios e, em alguns casos, os próprios campos.

| Configuração | Seleção de campo permitida | Observações |
| --- | --- | --- |
| <span id="default::b7bb6355"></span>Padrão | Sim | <ul><li>Os campos selecionados são organizados de acordo com um modelo da AppsFlyer.</li><li>A partir de agora, a sequência será mantida. Os campos futuros serão adicionados à direita dos campos atuais.</li></ul> |
| <span id="alphabetical-az::b08af6b3"></span>Alfabético (A-Z) | Sim | Os campos selecionados são organizados alfabeticamente. |
| <span id="alphabetical-za::f0b3beb8"></span>Alfabético (Z-A) | Sim | Os campos selecionados são organizados por ordem alfabética inversa. |
| <span id="legacy::fb5fd8ec"></span>Legado | Não | <ul><li>Os campos são dispostos conforme a sequência de colunas nos relatórios elaborados com a versão anterior da página de exportação de dados.</li><li>A seleção dos campos é fixa e não pode ser alterada.</li><li>Existe alguma variação nos relatórios por campo, dependendo do relatório específico.</li></ul> |

Esta [folha de cálculo](https://docs.google.com/spreadsheets/d/e/2PACX-1vRGYcMOgC5yy_82yn3DWd3ucLE5KtuTA72eJfvu5KVB9fFH_mYwzM3KpR_inQOnat-KzgVjuuvXa6_g/pub?output=xlsx) contém uma folha padrão e uma de legado. Cada uma contém a lista de ordem de campos relevante.

**Para alterar a ordem dos campos:**

1. No separador Campos do Relatório, selecione uma opção de **Ordem dos Campos do Relatório**.
2. Se necessário, altere os campos selecionados, marcando ou desmarcando os campos necessários.

</Accordion>

<div data-zendesk-anchors="h_01HA28AT6QRSG68NBFYHH5SQY8=raw-data-export-page-features-and-filter-options procedures=procedimentos h_01HA28AT6Q9PV3M55C1YM3XN2E=procedimentos h_01HZY1HQ9AVH6Q9QAQB4SM1VPX=create-a-default-report h_01HZY1HQ9ACEMZ4N8WPYNHZQP7=create-a-custom-report h_01_web_srn_media_source_filter=nota h_01HA28AT6QV1XP4N952PAEGSSG=download-report h_01HA28AT6QFT88RHJ3M05MV3B3=duplicate-and-edit-report-settings additional-information=informa%C3%A7%C3%B5es-adicionais h_01HA28AT6Q4DXKCZ22R9XEN2RR=informa%C3%A7%C3%B5es-adicionais h_01HA28AT6Q6SE8CB3EEXFMAN0H=traits-and-limitations h_01HA28AT6RW8C99ZGEBTN5E44R=field-sequence-templates" />
