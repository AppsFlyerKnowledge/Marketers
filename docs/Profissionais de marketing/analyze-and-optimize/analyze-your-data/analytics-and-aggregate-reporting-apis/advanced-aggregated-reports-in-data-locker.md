---
title: Relatórios agregados avançados no Data Locker
metadata:
  keywords:
    - Premium
    - Premium Feature
    - Marketers
    - Data Locker
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Data Locker
  created_at: '2024-03-06T10:46:12Z'
  edited_at: '2026-08-19T00:02:34Z'
  id: 23127074968721
  locale: pt
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/pt/articles/23127074968721
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Visão geral**: Os relatórios agregados avançados no Data Locker oferecem dados agregados atualizados, precisos, granulares e com um volume ilimitado.

<div id="advanced-aggregated-reports-in-data-locker" />

## Relatórios agregados avançados no Data Locker

Relatórios agregados avançados no Data Locker:

* Uma forma eficiente e segura de criar sistemas de BI internos com base em dados agregados: Dados de atribuição, eventos e receita, com todas as dimensões e métricas possíveis.
* Você pode carregar os dados em seus sistemas de BI e usá-los como parte de seus processos de otimização de campanhas e performance.
* A melhor precisão e atualização de dados: Os dados são enviados <Anchor target="_blank" href="/marketers/pt/docs/about-data-freshness-and-timezone-support#intraday-during-the-day">várias vezes ao dia</Anchor> e são atualizados a cada nova versão de com todos os dados disponíveis para um dia em específico.
* Esse recurso oferece mais dados brutos, que podem ser limitados e <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions">restritos</Anchor> por políticas de compartilhamento de dados ou <Anchor target="_blank" href="/marketers/pt/docs/apply-aggregated-advanced-privacy-framework">políticas de proteção à privacidade</Anchor>. As restrições afetam campos relacionados à atribuição, como campanha e adset.

<div id="setup" />

## Configuração

Para obter relatórios agregados avançados, siga um dos procedimentos a seguir.

| Você usa o Data Locker? | Procedimento |
| --- | --- |
| Sim | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)Para adicionar os relatórios ao Data Locker:<ol><li>Na AppsFlyer, no menu lateral, selecione **Exportar > Data Locker**.</li><li>Selecione todos os relatórios que você deseja acessar.</li><li>Clique em **salvar configuração**.<br />Os relatórios estarão disponíveis no dia seguinte.</li></ol> |
| Não | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)**Para configurar o Data Locker**:<ol><li>Conclua a configuração do Data Locker (<Anchor target="_blank" href="/marketers/pt/docs/data-locker-for-marketers#set-up-data-locker">anunciante</Anchor> \| <Anchor target="_blank" href="/partners/pt/docs/data-locker-for-partners">parceiro</Anchor>).</li><li>Adicione os relatórios ao Data Locker:<ol><li>Na AppsFlyer, no menu lateral, selecione **Exportar > Data Locker**.</li><li>Selecione todos os relatórios que você deseja acessar.</li><li>Clique em **salvar configuração**.<br />Os relatórios estarão disponíveis no dia seguinte.</li></ol></li></ol> |

<div id="reports-available" />

## Relatórios disponíveis

<div id="cohort-versioned-report" />

<Accordion title="Agregado avançado (cohort versioned)">

<div id="report-facts" />

### Informações do relatório

| Visão geral | O relatório versionado de cohort contém todos os seus dados agregados, em cohort, com toda a granularidade de dimensões da campanha. O relatório é atualizado no intervalo de algumas horas para maximizar a atualização e a precisão dos dados.<br /><br /><Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vT8NQKO287TxXpdTYpIASL55t4muIt9G3lnkEE436FQhNn5_14DfYgf0ztbm1VVZXI4ecPaGktdixS7/pub?output=xlsx">Baixe uma amostra do relatório</Anchor> |
| --- | --- |
| Relatórios disponíveis | Os relatórios a seguir estão disponíveis para download. Os tipos de relatório estão descritos com mais detalhes no dashboard Cohort.<ul><li>**Aquisição de usuários:** atribuída a uma fonte de mídia de aquisição de usuários, incluindo dados LTV, sendo que a aquisição ocorre durante as janelas de reengajamento.</li><li>**Retargeting:** atribuído a uma fonte de média de retargeting para eventos ocorridos:<ul><li>Durante uma janela de reengajamento</li><li>Como resultado de reatribuições</li></ul></li><li>**Unificado:** exibe os dados sob a última fonte de média que trouxe o utilizador, conforme as regras de <Anchor target="_blank" href="/marketers/pt/docs/resolve-retargeting-double-attribution">dupla atribuição</Anchor> da AppsFlyer. Assim, o LTV que ocorre durante reengajamentos é apresentado na fonte de média de retargeting e não na de UA.</li></ul> |
| Período coberto pelo relatório | Usuários que converteram durante os 1.095 dias anteriores. Em outras palavras, a cada dia, os relatórios incluem eventos de usuários que converteram durante os 1.095 dias anteriores. |
| Estrutura do relatório | O esquema do relatório (as dimensões e métricas incluídas) é fixo e não pode ser editado. |
| Atualização dos dados | <ul><li>Intradiária. Os relatórios são enviados no intervalo de algumas horas.</li><li>Os relatórios contém os dados de um dia específico. Ou seja, em 18 de abril, cada versão do relatório contém todos os dados de 18 de abril. [Saiba mais](/docs/advanced-aggregated-reports-in-data-locker#versões-de-relatório-e-atualização-de-dados)</li></ul> |
| Fuso horário | UTC |
| Diretório e estrutura de nomes de arquivos | [Saiba mais](/docs/advanced-aggregated-reports-in-data-locker#estrutura-do-relatório) |
| Impacto das políticas de retenção de parceiros | Considere que alguns parceiros implementam políticas de retenção de dados. Neste caso, os eventos ocorridos após o término do período de retenção são considerados orgânicos nos relatórios de coorte.<br /><br />Exemplo: A SRN A possui uma política de retenção de dados de 180 dias. Os eventos do usuário até o dia 180 são atribuídos à SRN "A". Eventos que ocorrem após 180 dias são considerados orgânicos. |

<div id="report-structure" />

### Estrutura do relatório

O relatório é composto por dimensões e métricas.

O formato dos campos é o seguinte:

* **Dimensões**: Texto. O comprimento máximo da string é dinâmico e, na maioria dos casos, depende de como se preenchem os elementos da hierarquia publicitária.
* **Métricas**: Número. **Nota:** O formato de campo selected\_currency é uma string.  
  As métricas disponíveis são a receita, os usuários que executam um evento e o número de ocorrências do evento. Para calcular métricas relacionadas a custos, como ROI e ROAS, são necessárias métricas de receita e custo. As métricas de receita são encontradas no cohort, enquanto as métricas de custo são fornecidas pelo <Anchor target="_blank" href="/marketers/pt/docs/set-up-and-use-roi360-cost-etl-reports">Cost ETL do ROI360</Anchor>.

<div id="dimensions" />

#### Dimensões

<Table>
  <thead>
    <tr>
      <th>
        Nome do campo
      </th>
      <th>
        Descrição
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        conjunto\_de\_anúncios
      </td>
      <td>

      </td>
    </tr>
    <tr>
      <td>
        fonte\_de\_mídia
      </td>
      <td>

      </td>
    </tr>
    <tr>
      <td>
        tipo\_de\_conversão
      </td>
      <td>
        Valores possíveis: install, install\_unified (representando instalações no relatório unificado), re-engagement, reatribuição
      </td>
    </tr>
    <tr>
      <td>
        tipo\_de\_toque\_atribuído
      </td>
      <td>
        Valores possíveis: clique, impressões, pré-instalação, desconhecido, tv, nulo
      </td>
    </tr>
    <tr>
      <td>
        dias\_após\_atribuição
      </td>
      <td>
        * O número de dias decorridos desde a data da conversão (não o carimbo de data/hora específico da conversão).
        * Dica! Use isto para calcular retenção e dias para KPIs
      </td>
    </tr>
    <tr>
      <td>
        event\_date
      </td>
      <td>
        * A data em que um utilizador realiza um determinado evento.
        * Formato: aaaa-mm-dd
        * Exemplo: A data em que um utilizador realizou um determinado evento na app. No caso de uma conversão.
        * Nota! Se event\_name for af\_conversion, a data do evento e a data de conversão serão iguais.
      </td>
    </tr>
    <tr>
      <td>
        data\_da\_conversão
      </td>
      <td>
        * A data em que a conversão ocorreu.
        * Formato: aaaa-mm-dd
        * Exemplo: A data de instalação.
      </td>
    </tr>
    <tr>
      <td>
        nome\_do\_evento
      </td>
      <td>
        Identifica o evento. Alguns nomes de eventos têm um significado específico, enquanto outros estão relacionados com eventos definidos pelo anunciante na app. 

        | nome\_do\_evento | O que o utilizador fez |
        | --- | --- |
        | af\_conversion | Utilizador convertido. Use o tipo\_de\_conversão para identificar se é uma instalação, re-engagement ou reatribuição. |
        | af\_sessão | Abriu a app |
        | coorte\_desinstalações | Desinstalou a app |
        | Evento na app definido pelo anunciante | Realizou um evento in-app na app |
      </td>
    </tr>
    <tr>
      <td>
        Twitter
      </td>
      <td>
        Hierarquia da campanha

        Considere: As alterações no nome da campanha não são suportadas. Consequentemente, podem ser associados vários nomes a um determinado ID de campanha.
      </td>
    </tr>
    <tr>
      <td>
        id\_da\_campanha
      </td>
      <td>
        Hierarquia da campanha
      </td>
    </tr>
    <tr>
      <td>
        conjunto\_de\_anúncios
      </td>
      <td>
        Hierarquia da campanha
      </td>
    </tr>
    <tr>
      <td>
        id\_conjunto\_de\_anúncios
      </td>
      <td>
        Hierarquia da campanha
      </td>
    </tr>
    <tr>
      <td>
        anúncio
      </td>
      <td>
        Hierarquia da campanha
      </td>
    </tr>
    <tr>
      <td>
        id\_anúncio
      </td>
      <td>
        Hierarquia da campanha
      </td>
    </tr>
    <tr>
      <td>
        canal
      </td>
      <td>
        Hierarquia da campanha.

        [Atualização de 27 de outubro de 2021] Atualmente, os anúncios Meta não preenchem o canal nos dados fornecidos através do Google Install Referrer.
      </td>
    </tr>
    <tr>
      <td>
        id\_do\_site
      </td>
      <td>
        Hierarquia da campanha
      </td>
    </tr>
    <tr>
      <td>
        é\_atribuição\_primária
      </td>
      <td>
        Use para identificar e desduplicar dados de retargeting.
      </td>
    </tr>
    <tr>
      <td>
        geo
      </td>
      <td>
        O código ISO do país derivado do endereço IP do utilizador.
      </td>
    </tr>
    <tr>
      <td>
        agência
      </td>
      <td>
        * Transparência da agência suportada.
        * No caso de agências não transparentes, podem existir várias linhas com o mesmo nome de campanha se o anunciante e a agência executarem campanhas com o mesmo nome. Não se preocupe. As linhas não estão duplicadas.
      </td>
    </tr>
    <tr>
      <td>
        instalar\_app\_store
      </td>
      <td>
        Apenas para aplicações Android: A loja Android de onde a app foi descarregada. Preenchido por anunciantes que implementam <Anchor target="_blank" href="/marketers/pt/docs/set-up-multi-store-android-attribution">atribuição Android para várias lojas</Anchor>. Se estiver em branco, significa que é a Google Play Store.
      </td>
    </tr>
    <tr>
      <td>
        palavras-chave
      </td>
      <td>
        Palavra(s) usada(s) na pesquisa online do usuário. Conforme relatado pela ad network
      </td>
    </tr>
    <tr>
      <td>
        keyword\_id
      </td>
      <td>
        Keyword ID retornada pela ad network.
      </td>
    </tr>
  </tbody>
</Table>

<div id="metrics" />

#### Métricas

| Nome do campo | Descrição | Formato |
| --- | --- | --- |
| utilizadores\_únicos | Número de utilizadores únicos no dia em que realizam o evento. | Número |
| receita\_usd | <ul><li>Quantia de receita em dólares americanos. Por exemplo, 100,56 dólares são refletidos como 100,56.</li><li>Máximo de 2 casas após o ponto decimal.</li></ul> | Número |
| contagem\_de\_eventos | Número de ocorrências de eventos. | Número |
| moeda\_selecionada | Código de moeda de três letras (USD, EUR) definido por si nas definições da app. Formato <Anchor target="_blank" href="http://www.xe.com/symbols.php#section1">ISO-4217</Anchor>. É a mesma moeda utilizada para exibir a receita na Coorte na interface do utilizador. | Sequência de caracteres |
| receita\_moeda\_selecionada | <ul><li>Quantia de receita na moeda selecionada. Por exemplo, se a moeda selecionada for EUR, então 1.234,56 euros são refletidos como 1.234,56.</li><li>Máximo de 2 casas após o ponto decimal</li></ul> | Número |
| first\_inapp | <ul><li>Número de usuários que realizam o evento pela primeira vez após a conversão.</li><li>A soma das métricas first\_inapp fornece a contagem cumulativa de usuários exclusivos para um evento.</li></ul> | Número |

<div id="directory-and-filename-structure" />

#### Diretório e estrutura de nomes de arquivos

O caminho (path) para o relatório consiste na seguinte hierarquia de pastas:

Com o seguinte formato: `/t=cohort_unified_versioned/dt=/version=/`

<div id="report-folder-hierarchy" />

#### Hierarquia de pastas de relatório

Um exemplo da hierarquia de pastas do relatório versionado de cohort no bucket do anunciante:

```
bucket
|
└── t=cohort_unified_versioned
    |
    ├── dt=2024-05-05
    |   |
    |   └── version=1714890235
    |   |    |
    |   |    ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |    |
    |   |    ├── part-00001-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |    │
    |   |    └── part-00002-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |
    |   |
    |   └── version=1714890286
    |        |
    |        ├── part-00000-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        |
    |        ├── part-00001-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        │
    |        └── part-00002-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |   |
    .   . 
    .   .
```

**Legenda:**

* **dt**: Data em que ocorreram os eventos incluídos no relatório.
* **t:** tipo de relatório.
* **versão**: Carimbo de data/hora do Unix quando a versão foi criada.

<div id="report-versions-and-data-freshness" />

### Versões de relatório e atualização de dados

* Intradiária. Os relatórios são enviados no intervalo de algumas horas.
* Os relatórios são para todos os dados disponíveis em um dia específico. Ou seja, em 18 de abril, cada versão do relatório contém todos os dados de 18 de abril.
* **Use apenas a última versão disponível do relatório.**

| Versão | O relatório inclui dados que a AppsFlyer recebeu por (hora em UTC) | Caso de uso | O relatório de tempo está disponível (hora em UTC) |
| --- | --- | --- | --- |
| 1 | Dia 0 às 4h | Dados parciais do Dia 0 | Dia 0 às 8h |
| 2 | Dia 0 às 8h | Dados parciais do Dia 0 | Dia 0 às 13h |
| 3 | Dia 0 às 12h | Dados parciais do Dia 0 | Dia 0 às 18h |
| 4 | Dia 0 às 16h | Dados parciais do Dia 0 | Dia 0 às 21h |
| 5 | Dia 0 às 20h | Dados parciais do Dia 0 | Dia 0 às 23:59 |
| 6 | Dia 0 às 23:59 | Conversão completa e dados de eventos in-app para o Dia 0 (excluindo eventos S2S que a AppsFlyer recebe entre o Dia 0 às 23h59 e o Dia 1 às 2h) | Dia 1 às 4h |
| 7 | Dia 1 às 3h | Dados completos de conversão e eventos in-app para o Dia 0 e todos os dados de receita de anúncios disponíveis enviados via S2S | Dia 1 às 8h |
| 8 | Dia 1 às 11h | Dados completos de conversão e eventos in-app para o Dia 0 e todos os dados de receita de anúncios disponíveis enviados via S2S | Dia 1 às 18h |
| 9 | Dia 1 às 17h | Dados completos de conversão e eventos in-app para o Dia 0 e todos os dados de receita de anúncios disponíveis enviados via S2S | Dia 1 às 23:59 |
| 10 | Dia 8 às 7h | Dados completos de conversão e eventos in-app para o Dia 0 e dados completos de receita de anúncios enviados via S2S, contabilizando quaisquer problemas que possam ter ocorrido no lado da ad revenue network. | Dia 8 às 13h |

</Accordion>

<div id="cohort-timezone-versioned-report" />

<Accordion title="Relatórios agregados avançados (versão do fuso horário do cohort)">

<div id="report-facts-1" />

### Informações do relatório

| Visão geral | O relatório versionado de fuso horário de cohort contém todos os seus dados agregados, em cohorts, com toda a granularidade de dimensão da campanha, de acordo com fusos horários identificados. O relatório é atualizado no intervalo de algumas horas para maximizar a atualização e a precisão dos dados.<br /><br /><Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQk1cZkeJhlx3trW13SjGbD4aWX3LmXZJRDJRApuAJkjB7XAg4nSFUyN0_YoirX-QMHkhFeMHwEmiVj/pub?output=xlsx">Baixe uma amostra do relatório</Anchor> |
| --- | --- |
| Relatórios disponíveis | Os seguintes relatórios estão disponíveis para descarregar. Os tipos de relatórios são descritos com mais detalhes no <Anchor target="_blank" href="/marketers/pt/docs/cohort-and-retention-dashboard#cohort-principles">Painel de coorte.</Anchor><ul><li>**Aquisição de utilizadores:** atribuída a uma fonte de média de aquisição, incluindo LTV durante as janelas de reengajamento.</li><li>**Retargeting:** atribuído a uma fonte de média de retargeting para eventos ocorridos:<ul><li>Durante uma janela de reengajamento</li><li>Como resultado de reatribuições</li></ul></li><li>**Unificado:** exibe os dados sob a última fonte de média que trouxe o utilizador, conforme as regras de <Anchor target="_blank" href="/marketers/pt/docs/resolve-retargeting-double-attribution">dupla atribuição</Anchor> da AppsFlyer. Assim, o LTV que ocorre durante reengajamentos é apresentado na fonte de média de retargeting e não na de UA.</li></ul> |
| Período coberto pelo relatório | Usuários que converteram durante os 1.095 dias anteriores. Em outras palavras, a cada dia, os relatórios incluem eventos de usuários que converteram durante os 1.095 dias anteriores.<br /><br />**Atenção:** Se um dia ainda não tiver começado no fuso horário local, os relatórios serão enviados sem dados. |
| Estrutura do relatório | O esquema do relatório (as dimensões e métricas incluídas) é fixo e não pode ser editado. |
| Atualização dos dados | <ul><li>Intradiária. Os relatórios são enviados no intervalo de algumas horas.</li><li>Os relatórios contém os dados de um dia específico. Ou seja, em 18 de abril, cada versão do relatório contém todos os dados de 18 de abril. [Saiba mais](/docs/advanced-aggregated-reports-in-data-locker#versões-de-relatório-e-atualização-de-dados-1)</li></ul> |
| Fuso horário | Qualquer fuso horário, exceto UTC. Ou seja, os relatórios não incluem dados para aplicativos com configurações de fuso horário UTC na AppsFlyer. |
| Diretório e estrutura de nomes de arquivos | [Saiba mais](/docs/advanced-aggregated-reports-in-data-locker#estrutura-do-relatório-1) |
| Impacto das políticas de retenção de parceiros | Alguns parceiros possuem uma política de retenção de dados. Nesse caso, os eventos que ocorrem após o término do período de retenção não são considerados nos relatórios de cohort.<br /><br />Exemplo: A SRN A possui uma política de retenção de dados de 180 dias. Os eventos do usuário até o dia 180 são atribuídos à SRN "A". Eventos que ocorrem após 180 dias são desconsiderados.<br /><br />**Atenção:** Os eventos são exibidos no dashboard de Visão geral como orgânicos. |

<div id="report-structure-1" />

### Estrutura do relatório

O relatório é composto por dimensões e métricas.

O formato dos campos é o seguinte:

* **Dimensões**: Texto. O comprimento máximo da string é dinâmico e, na maioria dos casos, depende de como se preenchem os elementos da hierarquia publicitária.
* **Métricas**: Número. **Nota:** O formato de campo selected\_currency é uma string.  
  As métricas disponíveis são a receita, os usuários que executam um evento e o número de ocorrências do evento. Para calcular métricas relacionadas a custos, como ROI e ROAS, são necessárias métricas de receita e custo. As métricas de receita são encontradas no cohort, enquanto as métricas de custo são fornecidas pelo <Anchor target="_blank" href="/marketers/pt/docs/set-up-and-use-roi360-cost-etl-reports">Cost ETL do ROI360</Anchor>.

<div id="dimensions-1" />

#### Dimensões

<Table>
  <thead>
    <tr>
      <th>
        Nome do campo
      </th>
      <th>
        Descrição
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        conjunto\_de\_anúncios
      </td>
      <td>

      </td>
    </tr>
    <tr>
      <td>
        fonte\_de\_mídia
      </td>
      <td>

      </td>
    </tr>
    <tr>
      <td>
        tipo\_de\_conversão
      </td>
      <td>
        Valores possíveis: install, install\_unified (representando instalações no relatório unificado), re-engagement, reatribuição
      </td>
    </tr>
    <tr>
      <td>
        tipo\_de\_toque\_atribuído
      </td>
      <td>
        Valores possíveis: clique, impressões, pré-instalação, desconhecido, tv, nulo
      </td>
    </tr>
    <tr>
      <td>
        dias\_após\_atribuição
      </td>
      <td>
        * O número de dias decorridos desde a data da conversão (não o carimbo de data/hora específico da conversão).
        * Dica! Use isto para calcular retenção e dias para KPIs
      </td>
    </tr>
    <tr>
      <td>
        event\_date
      </td>
      <td>
        * A data em que um utilizador realiza um determinado evento.
        * Formato: aaaa-mm-dd
        * Exemplo: A data em que um utilizador realizou um determinado evento na app. No caso de uma conversão.
        * Nota! Se event\_name for af\_conversion, a data do evento e a data de conversão serão iguais.
      </td>
    </tr>
    <tr>
      <td>
        data\_da\_conversão
      </td>
      <td>
        * A data em que a conversão ocorreu.
        * Formato: aaaa-mm-dd
        * Exemplo: A data de instalação.
      </td>
    </tr>
    <tr>
      <td>
        nome\_do\_evento
      </td>
      <td>
        Identifica o evento. Alguns nomes de eventos têm um significado específico, enquanto outros estão relacionados com eventos definidos pelo anunciante na app. 

        | nome\_do\_evento | O que o utilizador fez |
        | --- | --- |
        | af\_conversion | Utilizador convertido. Use o tipo\_de\_conversão para identificar se é uma instalação, re-engagement ou reatribuição. |
        | af\_sessão | Abriu a app |
        | coorte\_desinstalações | Desinstalou a app |
        | Evento na app definido pelo anunciante | Realizou um evento in-app na app |
      </td>
    </tr>
    <tr>
      <td>
        event\_timezone
      </td>
      <td>
        O fuso horário para:

        * days\_post\_atribution
        * event\_date
        * data\_da\_conversão
      </td>
    </tr>
    <tr>
      <td>
        Twitter
      </td>
      <td>
        Hierarquia da campanha

        Considere: As alterações no nome da campanha não são suportadas. Consequentemente, podem ser associados vários nomes a um determinado ID de campanha.
      </td>
    </tr>
    <tr>
      <td>
        id\_da\_campanha
      </td>
      <td>
        Hierarquia da campanha
      </td>
    </tr>
    <tr>
      <td>
        conjunto\_de\_anúncios
      </td>
      <td>
        Hierarquia da campanha
      </td>
    </tr>
    <tr>
      <td>
        id\_conjunto\_de\_anúncios
      </td>
      <td>
        Hierarquia da campanha
      </td>
    </tr>
    <tr>
      <td>
        anúncio
      </td>
      <td>
        Hierarquia da campanha
      </td>
    </tr>
    <tr>
      <td>
        id\_anúncio
      </td>
      <td>
        Hierarquia da campanha
      </td>
    </tr>
    <tr>
      <td>
        canal
      </td>
      <td>
        Hierarquia da campanha.

        [Atualização de 27 de outubro de 2021] Atualmente, os anúncios Meta não preenchem o canal nos dados fornecidos através do Google Install Referrer.
      </td>
    </tr>
    <tr>
      <td>
        id\_do\_site
      </td>
      <td>
        Hierarquia da campanha
      </td>
    </tr>
    <tr>
      <td>
        é\_atribuição\_primária
      </td>
      <td>
        Use para identificar e desduplicar dados de retargeting.
      </td>
    </tr>
    <tr>
      <td>
        geo
      </td>
      <td>
        O código ISO do país derivado do endereço IP do utilizador.
      </td>
    </tr>
    <tr>
      <td>
        agência
      </td>
      <td>
        * Transparência da agência suportada.
        * No caso de agências não transparentes, podem existir várias linhas com o mesmo nome de campanha se o anunciante e a agência executarem campanhas com o mesmo nome. Não se preocupe. As linhas não estão duplicadas.
      </td>
    </tr>
    <tr>
      <td>
        instalar\_app\_store
      </td>
      <td>
        Apenas para aplicações Android: A loja Android de onde a app foi descarregada. Preenchido por anunciantes que implementam <Anchor target="_blank" href="/marketers/pt/docs/set-up-multi-store-android-attribution">atribuição Android para várias lojas</Anchor>. Se estiver em branco, significa que é a Google Play Store.
      </td>
    </tr>
    <tr>
      <td>
        palavras-chave
      </td>
      <td>
        Palavra(s) usada(s) na pesquisa online do usuário. Conforme relatado pela ad network
      </td>
    </tr>
    <tr>
      <td>
        keyword\_id
      </td>
      <td>
        Keyword ID retornada pela ad network.
      </td>
    </tr>
  </tbody>
</Table>

<div id="metrics-1" />

#### Métricas

| Nome do campo | Descrição | Formato |
| --- | --- | --- |
| utilizadores\_únicos | Número de utilizadores únicos no dia em que realizam o evento. | Número |
| receita\_usd | <ul><li>Quantia de receita em dólares americanos. Por exemplo, 100,56 dólares são refletidos como 100,56.</li><li>Máximo de 2 casas após o ponto decimal.</li></ul> | Número |
| contagem\_de\_eventos | Número de ocorrências de eventos. | Número |
| moeda\_selecionada | Código de moeda de três letras (USD, EUR) definido por si nas definições da app. Formato <Anchor target="_blank" href="http://www.xe.com/symbols.php#section1">ISO-4217</Anchor>. É a mesma moeda utilizada para exibir a receita na Coorte na interface do utilizador. | string |
| receita\_moeda\_selecionada | <ul><li>Quantia de receita na moeda selecionada. Por exemplo, se a moeda selecionada for EUR, então 1.234,56 euros são refletidos como 1.234,56.</li><li>Máximo de 2 casas após o ponto decimal</li></ul> | Número |
| first\_inapp | <ul><li>Número de usuários que realizam o evento pela primeira vez após a conversão.</li><li>A soma das métricas first\_inapp fornece a contagem cumulativa de usuários exclusivos para um evento.</li></ul> | Número |

<div id="directory-and-filename-structure-1" />

#### Diretório e estrutura de nomes de arquivos

O caminho (path) para o relatório consiste na seguinte hierarquia de pastas:

Com o seguinte formato: `/t=cohort_unified_timezone_versioned/dt=/version=/`

<div id="report-folder-hierarchy-1" />

#### Hierarquia de pastas de relatório

Um exemplo da hierarquia de pastas do relatório versionado de fuso horário de cohort no bucket do anunciante:

```
bucket
|
└── t=cohort_unified_timezone_versioned
    |
    ├── dt=2024-05-05
    |   |
    |   └── version=1714890235
    |   |    |
    |   |    ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |    |
    |   |    ├── part-00001-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |    │
    |   |    └── part-00002-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |
    |   |
    |   └── version=1714890286
    |        |
    |        ├── part-00000-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        |
    |        ├── part-00001-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        │
    |        └── part-00002-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |   |
    .   . 
    .   .
```

**Legenda:**

* **dt**: Data em que ocorreram os eventos incluídos no relatório.
* **t:** tipo de relatório.
* **versão**: Carimbo de data/hora do Unix quando a versão foi criada.

<div id="report-versions-and-data-freshness-1" />

### Versões de relatório e atualização de dados

* Intradiária. Os relatórios são enviados no intervalo de algumas horas.
* Os relatórios são para todos os dados disponíveis em um dia específico. Ou seja, em 18 de abril, cada versão do relatório contém todos os dados de 18 de abril.
* Os casos de uso podem ser diferentes a depender da sua região geográfica e fuso horário. [Saiba mais](/docs/advanced-aggregated-reports-in-data-locker#timezone-geos)
* **Use apenas a última versão disponível do relatório.**

| Versão | O relatório inclui dados que a AppsFlyer recebeu por (hora em UTC) | Caso de uso | O relatório de tempo está disponível (hora em UTC) |
| --- | --- | --- | --- |
| 1 | Dia -1 às 4h | Geos orientais - dados parciais para o Dia 0 | Dia -1 às 8h |
| 2 | Dia -1 às 8h | Geos orientais - dados parciais para o Dia 0 | Dia -1 às 13h |
| 3 | Dia -1 às 12h | Geos orientais - dados parciais para o Dia 0 | Dia -1 às 18h |
| 4 | Dia -1 às 16h | Geos orientais - dados parciais para o Dia 0 | Dia -1 às 21h |
| 5 | Dia -1 às 20h | Geos orientais - dados parciais para o Dia 0 | Dia -1 às 23:59 |
| 6 | Dia -1 às 23:59 | Geos Oriental e Central - dados parciais para o Dia 0 | Dia 0 às 4h |
| 7 | Dia 0 às 4h | Todos os geos - dados parciais para o Dia 0 | Dia 0 às 8h |
| 8 | Dia 0 às 8h | Todos os geos - dados parciais para o Dia 0 | Dia 0 às 13h |
| 9 | Dia 0 às 12h | Todos os geos - dados parciais para o Dia 0 | Dia 0 às 18h |
| 10 | Dia 0 às 16h | Todos os geos - dados parciais para o Dia 0 | Dia 0 às 21h |
| 11 | Dia 0 às 20h | <ul><li>Geos orientais - Conversão completa e dados de eventos in-app para o Dia 0</li><li>Geos Central e Ocidental - dados parciais para o Dia 0</li></ul> | Dia 0 às 23:59 |
| 12 | Dia 0 às 23:59 | Geos Central e Ocidental - dados parciais para o Dia 0 | Dia 1 às 4h |
| 13 | Dia 1 às 4h | <ul><li>Geos centrais - Dados completos de conversão e eventos in-app para o Dia 0</li><li>Geos ocidentais - dados parciais para o Dia 0</li><li>Todos os dados de receita de anúncios disponíveis enviados via S2S</li></ul> | Dia 1 às 8h |
| 14 | Dia 1 às 8h | Geos ocidentais - dados parciais para o Dia 0 e dados de receita de anúncios disponíveis enviados via S2S | Dia 1 às 13h |
| 15 | Dia 1 às 12h | Regiões ocidentais - dados parciais para o Dia 0 e quaisquer dados de receita de anúncios atualmente disponíveis enviados via S2S no momento em que o relatório é processado | Dia 1 às 18h |
| 16 | Dia 1 às 12h | Regiões ocidentais - dados parciais para o Dia 0 e dados de receita de anúncios atualizados enviados via S2S (o relatório é processado apenas após a conclusão do processamento dos dados de receita de anúncios) | Dia 1 às 18h |
| 17 | Dia 1 às 16h | Regiões ocidentais - dados parciais para o Dia 0 e dados de receita de anúncios disponíveis enviados via S2S | Dia 1 às 21h |
| 18 | Dia 1 às 18h | Regiões ocidentais - dados parciais para o Dia 0 e dados de receita de anúncios disponíveis enviados via S2S | Dia 1 às 23:59 |
| 19 | Dia 1 às 20h | Regiões ocidentais - Conversão completa, dados de eventos in-app para o Dia 0 e dados completos de receita de anúncios enviados via S2S | Dia 1 às 23:59 |
| 20 | Dia 1 às 23:59 | Dados completos de conversão e eventos in-app para o Dia 0 e dados completos de receita de anúncios enviados via S2S, contabilizando quaisquer problemas que possam ter ocorrido no lado da ad revenue network. | Dia 2 às 4h |
| 21 | Dia 8 às 00:00 | Dados completos de conversão e eventos in-app para o Dia 0 e dados completos de receita de anúncios enviados via S2S, contabilizando quaisquer problemas que possam ter ocorrido no lado da ad revenue network. | Dia 8 às 6h |

</Accordion>

<div id="additional-information" />

## Informações adicionais

<div id="timezone-geos" />

<Accordion title="Geos de fuso horário">

Os casos de uso podem ser diferentes a depender da sua região geográfica e fuso horário. Use a tabela a seguir para entender quais geos correspondem a quais fusos horários.

| Geolocalização | Fuso horário |
| --- | --- |
| Oriental | UTC+12 - UTC-3 |
| Central | UTC+2.5 - UTC-3 |
| Ocidental | UTC-3.5 - UTC-12 |

</Accordion>

<div id="bi-developer-considerations" />

<Accordion title="Considerações para o desenvolvedor de BI">

**Âmbito dos dados no relatório**

Os relatórios contêm instalações de aquisição de utilizadores, reatribuições de retargeting e reengajamentos, além dos seus eventos in-app relacionados.

Pode carregar relatórios unificados, de aquisição de utilizadores e retargeting, separadamente ou em conjunto no seu BI. Se os carregar juntos e quiser filtrar as visualizações por si:

* Para unificado, use o campo é\_atribuição\_primária=true ou nulo.
* Para aquisição de utilizadores, utilize tipo\_de\_conversão=instalação.
* Para retargeting, utilize tipo\_de\_conversão=re-engagement ou reatribuição.

Se apenas usar a vista unificada no seu processo de carregamento de dados, pode usar lógica para dividir os dados entre tipos de campanha, ou seja, atribuição de utilizadores (instalações) e retargeting (reengajamentos). Para isso, utilize conversion\_type=install, install\_unified, re-engajamento ou reatribuição. Consulte <Anchor target="_blank" href="/marketers/pt/docs/resolve-retargeting-double-attribution">Atribuição dupla de eventos de retargeting.</Anchor>

**Considerações ao nível do campo**

* Use dias pós-atribuição para permitir o cálculo fácil das métricas de retenção.
* Cálculo de usuários únicos usando as dimensões de nome de campanha e ID de campanha: Se puder desconsiderar a granularidade do nome da campanha, você pode somar a contagem única no ID da campanha, e as métricas estarão corretas.
* Pode agregar os dados utilizando os campos da hierarquia da campanha.
* A receita está em USD e é calculada usando a taxa de câmbio no dia do evento.

**Considerações gerais**

Os dados de todos os aplicativos são configuráveis; eles podem ser fornecidos em um único arquivo ou em arquivos separados por aplicativo.

</Accordion>

<div id="use-cases" />

<Accordion title="Casos de uso">

A seguir estão exemplos de alguns usos práticos dos dados via Data Locker. Cada exemplo é ilustrado por uma instrução SQL e um exemplo de Excel.

<div id="1-calculate-retention" />

#### **1. Calcule a retenção**

No exemplo seguinte, realizamos as seguintes ações:

* Calcular a retenção do Dia 1 e do Dia 7, bem como o número total de instalações por campanha e anúncio.
* Somar a contagem de eventos por evento de conversão filtrando `event_name`para que seja `af_conversion`.
* Mais especificamente, analisamos as campanhas de aquisição de usuários no relatório Unificado, filtrando os dados para que `conversion_type IN (install, install_unified)`.

**Instrução SQL**

```sql
select
    campaign_id, ad_id,
    sum(if(event_name = 'af_conversion', event_count,0)) as instalação,
    sum(if(event_name = 'af_session' and days_post_attribution = 1, unique_users,0)) / sum(if(event_name = 'af_conversion', event_count,0)) as retention_day1,
    sum(if(event_name = 'af_session' and days_post_attribution = 7, unique_users,0)) / sum(if(event_name = 'af_conversion', event_count,0)) as retention_day7
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08' 
    and app_id = YOUR_APP
group by 1,2
```

**Exemplo Excel**

| ID da campanha | ID do anúncio | Instalações | Retenção Dia 1 | Retenção Dia 7 |
| --- | --- | --- | --- | --- |
| 12345678 | 987654 | 100 | 30% | 10% |
| 98765432 | 123456 | 200 | 25% | 15% |
| 07315466 | 613770 | 300 | 20% | 12% |

<div id="2-calculate-arpu-of-multiple-in-app-events" />

#### **2. Calcule o ARPU de múltiplos eventos no aplicativo**

No exemplo seguinte, realizamos as seguintes ações:

* Calcular o ARPU de múltiplos eventos na aplicação por campanha.
* Analisar especificamente as campanhas de retargeting, filtrando os dados de modo a que `conversion_type=re-engagement` e `conversion_type=re-attribution`.
* Somar a contagem de eventos por evento de conversão filtrando `event_name`para que seja `af_conversion`.
* Somar a receita de múltiplos eventos, neste caso `af_purchase`e `af_coins`.
* Definir `days_post_attribution` como o mínimo necessário (neste caso, 7) para minimizar a carga de processamento de dados.

**Instrução SQL**

```sql
select
    campaign_id,
    sum(if(days_post_attribution <= 1 and event_name in ('af_purchase', 'af_coins') , revenue_usd, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day1,
    sum(if(days_post_attribution <= 3 and event_name in ('af_purchase', 'af_coins') , revenue_usd, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day3,
    sum(if(days_post_attribution <= 7 and event_name in ('af_purchase', 'af_coins') , revenue_usd, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day7
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    and days_post_attribution <= 7
    and conversion_type in ('re-engagement', 're-attribution')
    and app_id = YOUR_APP
group by 1
```

**Exemplo Excel**

| ID da campanha | Tipo de conversão | OPCIONAL<br /><br />Dia 1 | OPCIONAL<br /><br />Dia 3 | OPCIONAL<br /><br />Dia 7 |
| --- | --- | --- | --- | --- |
| 12345678 | re-engajamento | 6.23 | 5.11 | 2.34 |
| 98765432 | re-engajamento | 3.57 | 1.34 | 4.86 |
| 07315466 | reatribuição | 7.41 | 6.79 | 5.29 |

<div id="3-calculate-in-app-event-conversion-rate-for-a-specific-cohort-day" />

#### **3. Calculando a taxa de conversão de eventos in-app para um dia de cohort específico**

No exemplo seguinte, realizamos as seguintes ações:

* Calcular a taxa de conversão de eventos na aplicação no Dia 0 para várias dimensões (neste caso, data de conversão, localização geográfica, campanha, anúncio e ID do site).
* Analisar dados unificados (campanhas de UA e de retargeting) filtrando-os para que `is_primary_attribution=true`.
* Somar a contagem de eventos por evento de conversão filtrando `event_name`para que seja `af_conversion`.
* Definir `days_post_attribution` como o mínimo necessário (neste caso, 7) para minimizar a carga de processamento de dados.

**Instrução SQL**

```sql
select
    conversion_date, geo, campaign_id, ad_id, site_id,
    sum(if(days_post_attribution = 0 and event_name = 'af_complete_tutorial', unique_users, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as day0_af_tutorial_conversion
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    and is_primary_attribution = true
    and app_id = YOUR_APP
group by 1,2,3,4,5
```

**Exemplo Excel**

| Data de conversão | Geografia | ID da campanha | ID do anúncio | ID do site | Dia 0 af\_complete\_tutorial |
| --- | --- | --- | --- | --- | --- |
| 2022-11-07 | EUA | 12345678 | 123456 | site\_123 | 45% |
| 2022-11-05 | Reino Unido | 98765432 | nulo | site\_654 | 70% |
| 2022-10-31 | KR | 07315466 | nulo | nulo | 63% |

<div id="4-calculate-daily-installs" />

#### **4. Calcule as instalações diárias**

No exemplo seguinte, realizamos as seguintes ações:

* Calcular o número de instalações por ID da aplicação, data de conversão, fonte de mídia, nome do evento e tipo de conversão.
* No relatório unificado, filtre os dados para mostrar instalações de UA (não retargeting) configurando `conversion_type` para `install` ou `install_unified`.
* Some as instalações definindo `event_name`para que seja `af_conversion`.

**Instrução SQL**

```sql
select
    app_id,
    conversion_date,
    media_source,
    event_name,
    conversion_type,
    sum(events_count) as total
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    // If you're querying data from unified reports, edit the line below to: and conversion_type IN ('install', 'install_unified')
    and conversion_type = 'install'
    and event_name = 'af_conversion'
    and app_id = YOUR_APP
group by 1,2,3,4,5
```

**Exemplo Excel**

| ID da aplicação | Data de conversão | Fonte de mídia | Nome do evento | Total |
| --- | --- | --- | --- | --- |
| id123456789 | 2022-11-07 | adnet1\_int | af\_conversion | 105 |
| id123456789 | 2022-11-05 | adnet2\_int | af\_conversion | 216 |
| id123456789 | 2022-10-31 | adnet3\_int | af\_conversion | 327 |

<div id="5-calculate-revenue-from-facebook-ads" />

#### **5. Calcule a receita de anúncios do Facebook Ads**

No exemplo seguinte, realizamos as seguintes ações:

* Calcular a receita do Dia 3 de anúncios do Facebook, com base na data de conversão e ID da aplicação.
* Analise os dados do Facebook filtrando para que `media_source='Facebook Ads'`.
* Definir `days_post_attribution` como o mínimo necessário (neste caso, 3) para minimizar a carga de processamento de dados.

**Instrução SQL**

```sql
select
    conversion_date,
    app_id,
    media_source,
    sum(if(days_post_attribution <= 3, revenue_usd, 0)) as revenue_day3
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2022-06-01' and '2023-05-31'
    and days_post_attribution <= 3
    and media_source = 'Facebook Ads'
    and app_id in (APP_ID1, APP_ID2, ...)
group by 1,2,3
group by 1,2,3
group by 1,2,3
```

**Exemplo Excel**

| Data de conversão | ID da aplicação | Fonte de mídia | Resultados<br /><br />Dia 3 |
| --- | --- | --- | --- |
| 2022-11-07 | id123456789 | adnet1\_int | 400.45 |
| 2022-11-05 | id123456789 | adnet2\_int | 99.23 |
| 2022-10-31 | id123456789 | adnet3\_int | 13.34 |

<div id="6-calculate-arpu-per-asa-keyword-id-for-up-to-365-cohort-days" />

#### **6. Calcule o ARPU por ASA keyword ID até 365 dias de cohort**

No exemplo seguinte, realizamos as seguintes ações:

* Calcular o ARPU dos anúncios de pesquisa da Apple por ID de palavra-chave até ao dia de coorte 365.
* Analise os dados do Apple Search Ads filtrando-os de modo a que `media_source='Apple Search Ads'`.
* Somar a contagem de eventos por evento de conversão filtrando `event_name`para que seja `af_conversion`.

**Instrução SQL**

```sql
select
    media_source,
    keyword_id,
    sum(if(days_post_attribution <= 365, revenue_usd,0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day365
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2022-06-01' and '2023-05-31'
    and media_source = 'Apple Search Ads'
    and app_id = YOUR_APP
group by 1
```

**Exemplo Excel**

| Fonte de mídia | ID da palavra-chave | OPCIONAL<br /><br />Dia 365 |
| --- | --- | --- |
| adnet1\_int | 123456 | 57.019,93 |
| adnet2\_int | 987654 | 64.867,84 |
| adnet3\_int | 666854 | 48.160,02 |

<div id="7-calculate-arpu-days-7-by-attribution-time-per-geo" />

#### **7. Cálculo do ARPU Dias 7 por tempo de atribuição para cada área geográfica**

O exemplo seguinte ilustra como utilizar <Anchor target="_blank" href="/marketers/pt/docs/cohort-and-retention-dashboard#trend-type%E2%80%94kpi-by-attribution-time">KPIs por tempo de atribuição</Anchor>. Neste exemplo, nós:

* Calculamos o ARPU Dias 7 por data de atribuição para cada área geográfica.
* Os resultados são classificados pelo número de conversões, exibindo as 20 principais regiões geográficas.
* Os dados são filtrados de maneira que `conversion_type='install'`.
* A primeira coluna mostra a área geográfica. A segunda coluna mostra o total de conversões. As colunas seguintes mostram a receita dos 7 dias para cada dia especificado como uma linha na consulta.

**Instrução SQL**

```sql
select
    geo,
    sum(if(event_name = 'af_conversion', event_count, 0)) total_conversions,
    sum(if(cohort_day = '2023-07-11' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-11' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_11,
    sum(if(cohort_day = '2023-07-12' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-12' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_12,
    sum(if(cohort_day = '2023-07-13' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-13' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_13,
    sum(if(cohort_day = '2023-07-14' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-14' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_14,
    sum(if(cohort_day = '2023-07-15' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-15' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_15,
    sum(if(cohort_day = '2023-07-16' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-16' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_16
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-07-11' and '2023-07-16'
    and days_post_attribution <= 7
    // If you're querying data from unified reports, edit the line below to: and conversion_type IN ('install', 'install_unified')    
    and conversion_type = 'install'
    and app_id = 'YOUR_APP'
group by 1
order by 2 desc
limit 20
```

**Exemplo Excel**

| Geografia | Total de conversões | ARPU Dia 7 para 2023-07-11 | ARPU Dia 7 para 2023-07-12 | ARPU Dia 7 para 2023-07-13 | ARPU Dia 7 para 2023-07-14 | ARPU Dia 7 para 2023-07-15 | ARPU Dia 7 para 2023-07-16 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Coreia do Sul | 120.660 | US$ 7.798,89 | US$ 6.997,37 | US$ 8.258,95 | US$ 9.050,21 | US$ 10.018,04 | US$ 13.765,73 |
| Canadá | 35.099 | US$ 64.867,84 | US$ 7.050,19 | US$ 5.656,33 | US$ 9.553,75 | US$ 8.632,41 | US$ 11.308,06 |
| Chile | 26.750 | US$ 48.160,02 | US$ 21.249,55 | US$ 22.584,57 | US$ 24.033,07 | US$ 31.118,91 | US$ 41.145,22 |

<div id="8-calculate-purchases-day-7-after-conversion" />

#### **8. Calculando compras D7 após a conversão**

No exemplo seguinte, realizamos as seguintes ações:

* Calculamos os usuários cumulativos que concluíram eventos af\_purchase 7 dias após a conversão (no modo de exibição unificado).
* Calculamos a taxa de conversão para o evento, ou seja, a parcela de conversões que levam a uma compra nos 7 dias seguintes à conversão.
* Os dados são filtrados de forma que `conversion_type='install'`.
* Os dados são agrupados por aplicativo, data de conversão, canal de mídia, campanha e adset.

**SQL**

```sql
select
    app_id, conversion_date, media_source, campaign, adset,
    sum(if(event_name = 'af_conversion', event_count,0)) as unified_conversions,
    sum(if(event_name = 'af_purchase', first_inapp, 0)) as af_purchase_day_7_cumulative_unique_users,
    concat(
        cast(
            round(
                sum(if(event_name = 'af_purchase', first_inapp, 0)) /
                sum(if(event_name = 'af_conversion', event_count, 0)) * 100.0
            ,2)
        as varchar),
    '%') as af_purchase_day_7_cumulative_unique_users_conversion_rate
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-12-01' and '2023-12-31'
    and is_primary_attribution = true
    and days_post_attribution <= 7
    and app_id in (APP_ID1, APP_ID2, ...)
group by 1,2,3,4,5
group by 1,2,3,4,5
group by 1,2,3,4,5
```

**Exemplo Excel**

| ID da aplicação | Data de conversão | Fonte de mídia | Campanha | Conjunto de anúncios | Conversões unificadas | D7 af\_purchase cumulativo | Taxa de conversão de af\_purchase D7 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| id123456789 | 28/06/2023 | adnet1\_int | campaign\_1 | adset\_1 | 100 | 20 | 20% |
| id123456789 | 2024-03-07 | adnet2\_int | campaign\_2 | adset\_2 | 200 | 10 | 5% |
| id123456789 | 2024-03-31 | adnet3\_int | campaign\_3 | adset\_3 | 150 | 15 | 10% |

<div id="9-calculate-dau" />

#### **9. Cálculo de DAU**

No exemplo seguinte, realizamos as seguintes ações:

* Calculamos o DAU para cada dia em um intervalo de tempo escolhido, agrupado por fonte de mídia, campanha e anúncio.
* Os dados são filtrados de maneira que `event_name = 'af_session'`.
* Somamos os usuários exclusivos para 1 dia de cada vez, onde cada data é sua própria dimensão (coluna).

Observação:

* Você não pode somar vários dias (por exemplo, para obter WAU ou MAU).
* DAU é baseado na atividade de usuários que converteram nos últimos 1.095 dias. Isso difere dos dados que podem ser vistos no dashboard e relatórios de Atividades, que não têm esse limite. Veja "Dias pós-conversão" na [seção de características e limitações](/docs/advanced-aggregated-reports-in-data-locker#traits-and-limitations).

**Instrução SQL**

```sql
select
media_source,campaign_id, ad_id,
sum(case when event_date = '2024-08-06' then unique_users end) as dau_2024_08_06,
sum(case when event_date = '2024-08-07' then unique_users end) as dau_2024_08_07,
sum(case when event_date = '2024-08-08' then unique_users end) as dau_2024_08_08
from YOUR_DATA_LOCKER_REPORT
where event_date between '2024-08-06' and '2024-08-08'
and event_name = 'af_session'
and app_id = YOUR_APP
group by 1,2,3
```

**Exemplo Excel**

| Fonte de mídia | Campanha | Anúncio | DAU 6 de agosto | DAU 7 de agosto | DAU 8 de agosto |
| --- | --- | --- | --- | --- | --- |
| adnet1\_int | campaign\_1 | adset\_1 | US$ 475.250 | US$ 420.485 | US$ 463.912 |
| adnet2\_int | campaign\_2 | adset\_2 | US$ 380.987 | US$ 355.665 | US$ 401.232 |
| adnet3\_int | campaign\_3 | adset\_3 | US$ 290.042 | US$ 570.322 | US$ 489.787 |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Características e Limitações">

| Caraterística |  |
| --- | --- |
| Dados de custo | <ul><li>Não disponível. <Anchor target="_blank" href="/marketers/pt/docs/set-up-and-use-roi360-cost-etl-reports">Utilizar ETL de custo</Anchor>.</li><li>Consulte também <Anchor target="_blank" href="/marketers/pt/docs/combine-cost-etl-and-cohort-reports-via-data-locker">a combinação do ETL de custos com relatórios de coorte</Anchor>.</li></ul> |
| Mudanças no nome da campanha | Não compatível. Use o ID da campanha para agrupar e filtrar se os nomes da campanha forem alterados. |
| Atualização dos dados | Intradiária |
| Receita de anúncios | Disponível |
| Moeda | USD e moeda específica da aplicação estão disponíveis por linha. |
| Fuso horário | O fuso horário específico do aplicativo está disponível com o relatório versionado de fuso horário. |
| Dados orgânicos | Disponível |
| Em quantos dias após a conversão (instalação, reatribuição, reengajamento) os dados estão disponíveis | 1.095 dias |
| Transparência das agências | <ul><li>Suportado</li><li>Os dados dos X Ads e Meta Ads são sempre transparentes.</li></ul> |
| Segregação de aplicações | Suportado |
| Dados SKAN | Não incluso. Ou seja, os dados são fornecidos pelos postbacks do iOS, não pelos relatórios do Data Locker. |
| Dados de desinstalação | As desinstalações são processadas diariamente. Assim, elas só aparecem em relatórios que contêm dados completos para um dia (não dados parciais). |
| Reinstalações | <ul><li>Se os eventos após reinstalação forem considerados orgânicos não atribuídos:<ul><li>Estão incluídos apenas a partir de 26 de maio de 2024. <Anchor target="_blank" href="/marketers/pt/docs/bulletin-cohort-data-includes-unattributed-sessions-and-events">Saiba mais</Anchor></li><li>O tempo de instalação baseia-se no campo <Anchor target="_blank" href="/marketers/pt/docs/raw-data-field-dictionary#device-info::dfd9504e">device\_download\_time</Anchor>.</li><li>Não são contabilizados para medições de usuários únicos e de retenção.</li></ul></li><li>Se os eventos após reinstalação forem atribuídos à primeira instalação, são sempre incluídos. <Anchor target="_blank" href="/marketers/pt/docs/unique-users">Saiba mais</Anchor></li></ul> |

</Accordion>

<div id="see-also" />

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/combine-cost-etl-and-cohort-reports-via-data-locker">Combine Cost ETL e relatório agregados avançados de cohort</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/cohort-and-retention-dashboard">Dashboard de cohort</Anchor>

<div data-zendesk-anchors="advanced-aggregated-reports-in-data-locker=relat%C3%B3rios-agregados-avan%C3%A7ados-no-data-locker h_01HWWH83KNSF4BRGTDJ0JD271G=relat%C3%B3rios-agregados-avan%C3%A7ados-no-data-locker setup=configura%C3%A7%C3%A3o h_01HWWH83KN9CM7ZY43W01AV6TA=configura%C3%A7%C3%A3o reports-available=relat%C3%B3rios-dispon%C3%ADveis h_01HWWNY76W6RFKX33MXHE4GSBD=relat%C3%B3rios-dispon%C3%ADveis h_01HWWNR256DRMBNFX3NV8ATNAY=cohort-versioned-report report-facts=informa%C3%A7%C3%B5es-do-relat%C3%B3rio h_01HVRBVXS47K91A6KVV33S1BY6=informa%C3%A7%C3%B5es-do-relat%C3%B3rio report-structure=estrutura-do-relat%C3%B3rio h_01HWWH83KNE46SPK1MS99XX64D=estrutura-do-relat%C3%B3rio dimensions=dimens%C3%B5es 01H7WG3CA14PQ2PJ58FX8TE6ZH=dimens%C3%B5es metrics=m%C3%A9tricas 01H7WG3CA24VQKFVP99S82GCXZ=m%C3%A9tricas directory-and-filename-structure=diret%C3%B3rio-e-estrutura-de-nomes-de-arquivos h_01HVRDKKQA17SMJFFAEDG7A2X2=diret%C3%B3rio-e-estrutura-de-nomes-de-arquivos the-report-folder-hierarchy-in-aws=hierarquia-de-pastas-de-relat%C3%B3rio h_01HETBAQVVA750VTE1ABSM2M47=hierarquia-de-pastas-de-relat%C3%B3rio report-versions-and-data-freshness=vers%C3%B5es-de-relat%C3%B3rio-e-atualiza%C3%A7%C3%A3o-de-dados h_01HWWH83KN51RR2VJ2F5N8YQ3J=vers%C3%B5es-de-relat%C3%B3rio-e-atualiza%C3%A7%C3%A3o-de-dados h_01HWWNVFCWJ7DZCKKKSBMH9NM5=cohort-timezone-versioned-report report-facts::15e071f=informa%C3%A7%C3%B5es-do-relat%C3%B3rio-1 h_01HWWH83KNPZETHR2TQS2E4QNT=informa%C3%A7%C3%B5es-do-relat%C3%B3rio-1 report-structure::43ffff28=estrutura-do-relat%C3%B3rio-1 h_01HWWH83KNG0V2ZMZZ7CTV2GE7=estrutura-do-relat%C3%B3rio-1 01HWSX3FA0K39D9M5RQ7J36Q23=dimens%C3%B5es-1 01HWSX3FA035Z8W6EPV4Q6E3JP=m%C3%A9tricas-1 01HWSX3FA189EMBJZ1P21YHC45=diret%C3%B3rio-e-estrutura-de-nomes-de-arquivos-1 01HX97NC4F2WCJABSM2NBSBEDN=hierarquia-de-pastas-de-relat%C3%B3rio-1 report-versions-and-data-freshness::e0755e26=vers%C3%B5es-de-relat%C3%B3rio-e-atualiza%C3%A7%C3%A3o-de-dados-1 h_01HWWH83KPS2ANCQKS2B3V529Z=vers%C3%B5es-de-relat%C3%B3rio-e-atualiza%C3%A7%C3%A3o-de-dados-1 additional-information=informa%C3%A7%C3%B5es-adicionais h_01HWWH83KPK8535X9EBZVJ9SQK=informa%C3%A7%C3%B5es-adicionais h_01HWWN6GAAD75HPC5GTE40QA37=timezone-geos 01H7WG3CA2C3HV8YT5ZMP9E0QY=bi-developer-considerations 01H7WG3CA2YF03SC6RBMCJYYVX=use-cases 1-Calculate-retention=1-calcule-a-reten%C3%A7%C3%A3o h_01HMTZ0DZWN54HBQ0ZTY0VFNFM=1-calcule-a-reten%C3%A7%C3%A3o 2-Calculate-arpu-of-multiple-inapp-events=2-calcule-o-arpu-de-m%C3%BAltiplos-eventos-no-aplicativo h_01HMTZ0DZWHZ77RYWYAQEJV7X5=2-calcule-o-arpu-de-m%C3%BAltiplos-eventos-no-aplicativo 3-Calculate-inapp-event-conversion-rate-for-a-specific-cohort-day=3-calculando-a-taxa-de-convers%C3%A3o-de-eventos-in-app-para-um-dia-de-cohort-espec%C3%ADfico h_01HMTZ0DZW7VA6T6MQY7BY1JZT=3-calculando-a-taxa-de-convers%C3%A3o-de-eventos-in-app-para-um-dia-de-cohort-espec%C3%ADfico 4-Calculate-daily-installs=4-calcule-as-instala%C3%A7%C3%B5es-di%C3%A1rias h_01HMTZ0DZWARZFAQ9R4VF56YN3=4-calcule-as-instala%C3%A7%C3%B5es-di%C3%A1rias 5-Calculate-revenue-from-facebook-ads=5-calcule-a-receita-de-an%C3%BAncios-do-facebook-ads h_01HMTZ0DZW74HWW6Z3VDWDMGRF=5-calcule-a-receita-de-an%C3%BAncios-do-facebook-ads 6-Calculate-arpu-per-asa-keyword-id-for-up-to-365-cohort-days=6-calcule-o-arpu-por-asa-keyword-id-at%C3%A9-365-dias-de-cohort h_01HMTZ0DZWSN83V0TEHVM2H5XS=6-calcule-o-arpu-por-asa-keyword-id-at%C3%A9-365-dias-de-cohort Calculate-arpu-days-0-7-by-attribution-time-per-geo=7-c%C3%A1lculo-do-arpu-dias-7-por-tempo-de-atribui%C3%A7%C3%A3o-para-cada-%C3%A1rea-geogr%C3%A1fica 01H8XYTJVQ1YFBHPWVPP9D7MJ8=7-c%C3%A1lculo-do-arpu-dias-7-por-tempo-de-atribui%C3%A7%C3%A3o-para-cada-%C3%A1rea-geogr%C3%A1fica 8-calculate-purchases-day-7-after-conversion=8-calculando-compras-d7-ap%C3%B3s-a-convers%C3%A3o h_01J7N4VB83T4KZ6G0Q634ASMHV=8-calculando-compras-d7-ap%C3%B3s-a-convers%C3%A3o 9-calculate-dau=9-c%C3%A1lculo-de-dau h_01J55D2FFW0XSH3G6AXRS06RPV=9-c%C3%A1lculo-de-dau 01H7WG3CA2Y59D2EVMN3YFFY1W=traits-and-limitations h_01HDNZ8A0QH74CGSEG6TKKARJP=veja-tamb%C3%A9m" />
