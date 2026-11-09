---
title: Dashboard de cohort
metadata:
  keywords:
    - Cohort
    - Cohort Report
    - Advertisers
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2015-12-24T10:20:01Z'
  edited_at: '2026-08-19T00:03:37Z'
  id: 207040496
  locale: pt
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/pt/articles/207040496
---
> **Visão geral**: o dashboard de Cohort agrupa usuários de aplicativo por data de aquisição. Realizar análise de desempenho nos ciclos de vida do usuário. Use o dashboard para obter insights sobre como as diferenças de campanha alteram as métricas da campanha.

<Image align="center" alt="cohort main (2).png" src="https://files.readme.io/5a9307f4220a5bc41b5cebefe345a9b93165ac3874dd4faaed184d0309e92615-small-32127933337873.png" />

<div id="cohort-and-retention-dashboard" />

## Dashboard de cohort

Leitura relacionada: <Anchor target="_blank" href="/marketers/pt/docs/aggregated-and-analytics-reporting-overview#cohort-flavors">Diferenças entre as variações de cohort</Anchor>

Para usar o Coorte, selecione usuários de um ou mais aplicativos e segmente-os por horário da conversão. Métricas de coorte como receita, ROI e taxas de conversão de eventos estão disponíveis. Para comparação, divida o coorte em dimensões como campanha ou fonte de mídia. Isso pode revelar padrões ou alterações no desempenho em relação aos ciclos de vida do usuário ou da campanha. Consulte <Anchor target="_blank" href="https://www.appsflyer.com/blog/cohort-report-mobile-marketing-kpis/?utm_campaign=Blog%20Subscription%2003-2019&utm_source=hs_email&utm_medium=email&utm_content=76370689&_hsenc=p2ANqtz-8SX49xuEw2WX_Vrlh11_zxlDFvlfMpBzSQm1I-nFhc0WbZDf0ACC-VEi4qmKhesHCsUNdhU50Oinl-urwnGAOZMwwHSTp6UgdChCi7ARayJFUFTus&_hsmi=76370689">Casos de uso de coorte</Anchor>.

<div id="tip" />

> 👍 **Observações**
>
> Quer saber mais sobre relatórios de coorte? Confira este <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7804/play/18625/your-users-journey-with-retention-and-cohort-reports">curso curto e informativo</Anchor> no Portal de Aprendizado da AppsFlyer.

<div id="using-cohort" />

## Usando Coorte

<div id="setting-up-an-analysis" />

<Accordion title="Configurando uma análise">

1. Acesse **Dashboard**> **Cohort**.  
   O dashboard de Cohort é aberto. O intervalo de datas de conversão e a granularidade são exibidos.  
   <Image align="center" alt="mceclip0__1_.png" src="https://files.readme.io/4113fd619422979d6a26004a55c009ebc48eef59d10ddc7c3e5becd2a758e6d4-32127949494417.png" />
2. Selecione a [granularidade do período de cohort](/docs/cohort-and-retention-dashboard#cohort-periods):
   * Horas
   * Dias
   * Semanas
   * meses
3. Defina o período de atribuição (aquisição do usuário ou engajamento por retargeting). Os dados relativos às datas mais recentes podem resultar em [dados parciais](/docs/cohort-and-retention-dashboard#partial-data) indicados por traços em gráficos e tabelas.
4. Clique em **Editar Coorte**.  
   A janela de configuração da Coorte é aberta.  
   <Image align="center" alt="CohortSetup.jpg" src="https://files.readme.io/f09cc190770d16a2ddf60e1f210f458114ac43d4c19fc5507fb50b0d1d2f5c77-32127949495825.jpg" width="365px" />
5. Complete o seguinte:
   * [**Tipo de visualização de cohort**](/docs/cohort-and-retention-dashboard#view-types):
     * **Aquisição de usuário.**
     * **Redirecionamento**
     * **Unificado:** inclui os eventos in-app de atribuição de usuários e atribuições de retargeting. **Observação**: os eventos de retargeting têm precedência sobre os eventos de aquisição de usuários, o que significa que o relatório contém eventos em que <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview">is\_primary\_attribution=true</Anchor>.
   * [**Tipo de tendência**](/docs/cohort-and-retention-dashboard#trend-types):
     * A função de exportação de CSV é limitada aos relatórios de **Desempenho da vida útil do usuário** .
     * **KPI por tempo de atribuição**.
   * **Usuários de**: selecione 1 ou mais aplicativos. **Usuários dos aplicativos**: selecione 1–muitos ou **todos** (significa os melhores 100 aplicativos em sua conta). **Observação**: as agências podem selecionar apenas um aplicativo.
   * **Agrupado por**: selecione uma ou mais [dimensões](/docs/cohort-and-retention-dashboard#list-of-dimensions-for-grouping-and-filtering) [Padrão: Fonte de mídia].
   * **Tamanho mínimo da coorte**: defina o tamanho mínimo da coorte. Isso evita sobrecarregar seu relatório com coortes insignificantes (pequenas). [Padrão=1]
   * Campos opcionais:
     * **Filtrado por**: selecione uma ou mais [dimensões](/docs/cohort-and-retention-dashboard#list-of-dimensions-for-grouping-and-filtering) para filtrar. Não há filtros padrão.
6. **No dia** ou **Cumulativo**:
7. Selecione a métrica (KPI) para a qual você quer realizar a análise de cohort. Para eventos in-app, selecione o evento in-app e a métrica.
8. Selecione os períodos de cohort para os quais você quer visualizar os dados. Ou seja, quais horas, dias, semanas ou meses após a conversão. O número de períodos de cohort que você pode selecionar depende do tipo de tendência selecionado.
9. **Por usuário**: quando selecionada, a soma ou a contagem é dividida pelo número de usuários do aplicativo.
10. **No dia** ou **Cumulativo**:
    * Cumulativo significa o total cumulativo ou em execução da métrica. Isso significa que o Cohort 3 mostra os totais dos períodos de cohort de 0 a 3.
    * **No dia:** o valor apenas no dia da coorte especificado. Por exemplo, no caso do dia 7, isso significa o valor no dia 7 após a conversão.
11. **Tabela** ou **Gráfico:**
12. Selecione se deseja visualizar os dados como tabela ou gráfico. Se você selecionar tabela, poderá escolher quantas linhas de dados ver: 25, 50, 100 ou 200.
13. [Opcional] [Gerenciando relatórios de cohort salvos](/docs/cohort-and-retention-dashboard#using-my-reports-save-and-select-reports).

</Accordion>

<div id="using-my-reports-save-and-select-reports" />

<Accordion title="Usando Meus relatórios—Salve e selecione relatórios">

* A opção "Meus relatórios" permite que você salve as configurações atuais do dashboard para uso futuro.
* Selecione um relatório salvo para exibir os dados de cohort mais recentes disponíveis.
* Você pode salvar um ou mais relatórios.
* Somente você pode acessar Meus relatórios.

| Característica | Observações |
| --- | --- |
| Meus relatórios | ![MyReports.png](https://files.readme.io/8f49c0e6dee55427bf3a64149ac48f67547967b8cd24aa8de3e34b760708f992-32127933340305.png)<br /><br />Selecione um relatório para exibir os dados mais recentes disponíveis. |
| Salvar alterações | Salvar relatório. Observação: o relatório selecionado está sobreposto. |
| Opções de ação (![Elipse.png](https://files.readme.io/14b74dc6e733867bd16b6a3594f5f0856d7437462b2e0cf7c12adf11cfa295b3-32127949499409.png)) | <ul><li>**Salvar como novo**<ul><li>Salvar relatório usando um nome de relatório diferente</li><li>[Opção] Tornar esse relatório padrão</li></ul></li><li>**Renomear**: alterar o nome do relatório</li><li>**Definir como padrão**: tornar o relatório padrão. Quando você abre o Cohort, este é o relatório que é exibido inicialmente</li><li>**Excluir**: excluir o relatório</li></ul> |

</Accordion>

<div id="export-the-cohort-to-a-csv-file" />

<Accordion title="Exportar a coorte para um arquivo CSV">

* Os relatórios de coorte podem ser exportados para arquivos CSV.
* Nomes de colunas que possuem sufixo [parcial  equivalem a traços exibidos em gráficos e tabelas na interface do usuário.](/docs/cohort-and-retention-dashboard#partial-data)

**Para exportar relatórios de coorte para arquivos CSV:**

* No lado superior direito da janela de Relatórios de Cohort, clique em <Image alt="Download.png" src="https://files.readme.io/50af9c6cde00dada58a1bb89a9eb3e566f316c0e7336af68f4ce403584047a5b-32127933341969.png" width="21px" />(exportar).  
  O arquivo CSV do relatório de cohort é baixado.

</Accordion>

<div id="cohort-concepts" />

## Princípios de cohort

<div id="cohort-periods" />

<Accordion title="CohortTable.png">

O período de conversão é referido como 0 (Hora 0, Dia 0, Semana 0 ou Mês 0). O próximo período após a conversão é chamado de 1 (Hora 1, Dia 1, Semana 1 ou Mês 1) e assim por diante.

O número de períodos disponíveis depende da granularidade de período selecionada:

* Para granularidade de horas, o número máximo de horas é 72.
* Para a granularidade do dia, o número máximo de dias é 180.
* Para granularidade semanal, o número máximo de semanas é 156
* Para a granularidade do mês, o número máximo de meses é 36

Na AppsFlyer, um período de cohort não leva em consideração o timestamp de data/hora específico da instalação. Em vez disso, as horas de coorte são arredondadas para a hora mais próxima e os dias, semanas e meses de coorte são baseados no dia, semana ou mês do calendário. Isso pode causar discrepâncias ao comparar os dados de coorte da AppsFlyer com os dados de coorte de outras redes, onde todos os períodos de coorte são determinados pelo carimbo de data/hora de instalação específico (o que significa que uma hora é de 60 minutos após a instalação, um dia é o registro de 24 horas após a instalação período após o carimbo de data/hora da instalação, etc).

</Accordion>

<div id="view-types" />

<Accordion title="Tipo de cohort">

Há 3 tipos de visualização de cohort:

* **Unificado**:
  * O desempenho conjunto das campanhas de aquisição e retargeting de usuários (incluindo custo e receita).
  * Se um evento for atribuído a ambos os tipos de conversão, apenas o evento de retargeting será incluído. Ou seja, o relatório é gerado usando a fonte de mídia de último toque real. Para quem está familiarizado com dados brutos, isso significa eventos em que <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview">is\_primary\_attribution=true</Anchor>.
* **Aquisição de usuário:** dados de desempenho de instalações (reinstalações excluídas, a menos que <Anchor target="_blank" href="/marketers/pt/docs/measure-reinstalls#attributed-to-the-first-install">sejam especialmente habilitadas</Anchor>)
* **Retargeting:** dados de performance de reatribuições ou reengajamentos

<Image align="center" alt="OV.png" src="https://files.readme.io/738bf91c1a12671b32b088993c43d4103498907a8bbe15821ddc53a0b071b876-32127949500305.png" />

</Accordion>

<div id="trend-types" />

<Accordion title="Tipo de tendência">

Há 2 tipos de tendência de cohort:

* **Tipo de tendência—desempenho da vida útil do usuário**
* **Tipo de tendência—KPI por tempo de atribuição**

<div id="user-lifetime-performance" />

#### **Usuários (4)**

* Cada coluna na tabela ou ponto no gráfico representa outro período de cohort (hora/dia/semana/mês). O dia de conversão é chamado de dia pós-conversão 0. O primeiro período pós-conversão é o período de cohort 1 e assim por diante. Isso permite comparar a performance do usuário pós-conversão, começando com o dia da conversão, conhecido como dia 0 do cohort.
* Você pode selecionar para quais períodos de cohort obter dados, até o máximo de cada opção de granularidade (hora/dia/semana/mês).

<div id="kpi-by-attribution-time" />

#### **Não está disponível para a tendência KPI por tempo de atribuição.**

* **KPI por tempo de atribuição:** usuários são agrupados pela **hora** da conversão. Isso permite avaliar o desempenho da campanha ao longo do tempo e visualizar os KPIs da campanha em relação à hora da conversão
* O número máximo de períodos de cohort que você pode selecionar para obter dados é 5.
* Se você selecionar a visualização dos dados como gráfico em vez de tabela, o gráfico exibirá apenas 1 período de cohort (o menor período selecionado).

<div id="example-user-lifetime-performance-trend-vs-kpi-by-attribution-time-trend" />

#### Exemplo: tendência de desempenho da vida útil do usuário x KPI por tendência de tempo de atribuição

Nesse exemplo, os mesmos dados brutos são usados para gerar os dois tipos de tendência de coorte. A tabela de dados brutos contém eventos de atribuição relacionados a diferentes usuários A, B, C e D. Os usuários engajam com um anúncio, instalam o aplicativo e, após a conversão, fazem uma ou mais compras. O dia de coorte 0 é o dia da instalação.

[<Image align="center" alt="CohortExample_en-us.jpg" src="https://files.readme.io/013f6ebe78e8a94e7dcc36e62f73ad151ecd9a88c5b32e5e41ffa52f1567f744-38187655867025.png" width="2284px" />](https://support.appsflyer.com/hc/article_attachments/49929174392337)

</Accordion>

<div id="partial-data" />

<Accordion title="O que são dados parciais?">

Para um determinado dia no intervalo de conversão de dados, se o número de dias decorridos desde a data da conversão for menor que o dia do cohort, esse dia do cohort contém dados parciais. O que significa que os dados parciais ocorrem em qualquer dia em que a data do coorte é maior que a data do dia da conversão.

Use o controle **Cohort em tempo real** para selecionar o modo de exibição de dados:

* [Padrão]**Em tempo real:**
  * Dados de atribuição atualizados continuamente em tempo real, incluindo a receita.
  * Os dados de custo são atualizados 6 vezes por dia, a cada quatro horas, em média.
  * Dados parciais (indicados por traços em relatórios e gráficos) estão incluídos
* **Diariamente:** os dados são atualizados diariamente e ficam disponíveis alguns minutos após a meia-noite. Dados de dias parciais não são exibidos.

</Accordion>

<div id="list-of-dimensions-for-grouping-and-filtering" />

<Accordion title="Lista de dimensões para agrupamento e filtragem">

| Dimensão | Comentários | Agrupar por | Filtrar por |
| --- | --- | --- | --- |
| <span id="ad"></span>Anúncio |  | ✓ | ✓ |
| <span id="ad-id"></span>ID do anúncio |  | ✓ | ✓ |
| <span id="adset"></span>Conjunto de anúncios |  | ✓ | ✓ |
| <span id="adset-id"></span>ID do conjunto de anúncios |  | ✓ | ✓ |
| <span id="agency"></span>Agência |  | ✓ | ✓ |
| <span id="apps"></span>Aplicativos | Relevante quando o relatório contém vários aplicativos | ✓ | **X** |
| <span id="attributed-touchtype"></span>Tipo do toque atribuído | Valores: clique, impressão ou NA (orgânico) | ✓ | ✓ |
| <span id="campaign"></span>Campanha |  | ✓ | ✓ |
| <span id="campaign-id"></span>ID da campanha |  | ✓ | ✓ |
| <span id="channel"></span>Canal |  | ✓ | ✓ |
| <span id="conversion-type"></span>Tipo de conversão | Dependente do tipo de coorte:<ul><li>**Aquisição de usuário**: Instalação</li><li>**Retargeting**: Reengajamento, Reatribuição</li></ul> | ✓ | ✓ |
| <span id="country-geo"></span>País (geolocalização) | Com base no endereço de IP do usuário | ✓ | ✓ |
| <span id="time-in-the-case-of-daily-granularity-is-the-date-hourly-granularity-is-the-hour-of-the-day-weekly-granularity-is-the-week-of-the-year-monthly-granularity-is-the-month-of-the-year"></span>Hora. No caso de:<ul><li>Granularidade dia dia é a data</li><li>Granularidade por hora é a hora do dia</li><li>Granularidade por semana é a semana do ano</li><li>Granularidade do mês é o mês do ano</li></ul> | Dependente do tipo de coorte:<ul><li>**Aquisição e unificação de usuários**: a data em que o aplicativo foi inicializado pela primeira vez.</li><li>**Retargeting**: o horário em que o aplicativo foi inicializado pela primeira vez após o reengajamento.</li></ul> | ✓ | **X** |
| <span id="install-app-store"></span>Loja de aplicativos da instalação | Relevante para aplicativos que implementam a <Anchor target="_blank" href="/marketers/pt/docs/set-up-multi-store-android-attribution">atribuição de várias stores do Android.</Anchor> Entre em contato com seu CSM para habilitar essa dimensão. | ✓ | ✓ |
| <span id="keywords"></span>Palavras-chave | Palavras-chave de busca fornecidas pelos parceiros integrados | ✓ | ✓ |
| <span id="media-source"></span>Fonte de mídia |  | ✓ | ✓ |
| <span id="revenue-type"></span>Tipo de receita | Compra in-app ou receita de anúncios | . | ✓ |
| <span id="site-id"></span>ID do site |  | ✓ | ✓ |
| <span id="sub-param-1"></span>Subparâmetro 1 |  | ✓ | ✓ |

</Accordion>

<div id="metrics-available" />

<Accordion title="Métricas disponíveis">

| Métrica | Descrição |
| --- | --- |
| de instalações | Número de instalações durante o intervalo de tempo selecionado |
| Conversões de retargeting | Número de conversões de retargeting (reatribuições e reengajamentos) durante o intervalo de tempo selecionado |
| Atribuições | Número de instalações, reengajamentos e reatribuições durante o intervalo de tempo selecionado |
| Custo (3) | <ul><li>Custo da campanha reportado à AppsFlyer via clique ou API</li><li>Sempre<ul><li>O tipo de visualização é unificado</li><li>Período permitido</li></ul></li></ul> |
| eCPI | Custo médio efetivo por instalação (atribuição): custo / atribuições |
| Resultados | Receita reportada para a AppsFlyer (cumulativa ou no dia, dependendo da sua configuração) |
| Contagem | Número de vezes que o evento de receita ocorreu (cumulativo ou no dia, dependendo da sua configuração) |
| OPCIONAL | Receita média por usuário: Receita / Usuários únicos |
| Contagem média de receita | Contagem média de eventos de receita reportada para a AppsFlyer (cumulativa ou no dia, dependendo da sua configuração) |
| Contagem | Número cumulativo de vezes que o aplicativo é iniciado, trazido para o primeiro plano do dispositivo ou outra mensuração definida pelo desenvolvedor |
| Média de sessões (cumulativa) | Média de aberturas do aplicativo por usuário, destacada em primeiro plano. Também pode representar outra mensuração definida pelo desenvolvedor (cumulativa) |
| Sessões (2) | No dia, número de vezes que o aplicativo é iniciado, trazido para o primeiro plano do dispositivo ou outra mensuração definida pelo desenvolvedor |
| Média de sessões (no dia) | Número médio de vezes por usuário que o aplicativo é iniciado, trazido para o primeiro plano do dispositivo ou outra mensuração definida pelo desenvolvedor (no dia) |
| Retenção | Taxa de retenção: Número diário de usuários únicos que abriram o aplicativo / conversões * 100 |
| ROI | <ul><li>Retorno sobre investimento: (Receita - custo) / custo * 100</li><li>Sempre<ul><li>Selecione um tipo de tendência:</li><li>Opções de granularidade</li></ul></li></ul> |
| ROAS | <ul><li>Retorno sobre gastos com anúncio: Receita / Custo * 100</li><li>Métricas relacionadas ao custo não disponíveis<ul><li>Tipo de coorte:</li><li>Selecione a granularidade.</li></ul></li></ul> |
| Contagem de desinstalações | <ul><li>Número de usuários do aplicativo que instalam o aplicativo e, posteriormente, desinstalam o aplicativo (relevante somente para aquisição de usuários).</li><li>Incluso<ul><li>O tipo de visualização é retargeting ou unificado.</li><li>Para a granularidade do dia, o número máximo de dias é 180.</li></ul></li></ul> |
| Contagem média de desinstalações | <ul><li>Número médio de usuários do aplicativo que instalam o aplicativo e depois desinstalam o aplicativo (relevante somente para aquisição de usuários)</li><li>Sempre<ul><li>O tipo de visualização é retargeting ou unificado.</li><li>Tipo de granularidade</li></ul></li></ul> |
| Contagem de IAE | Número de vezes que o evento in-app foi realizado (cumulativo ou no dia, dependendo da sua configuração) |
| eCPI médio | Número médio de vezes que o evento in-app foi realizado (cumulativo ou no dia, dependendo da sua configuração) |
| Receita de IAE | Receita gerada pelo evento in-app (cumulativa ou no dia, dependendo da sua configuração) |
| Regular, Monetização de anúncios | Receita média gerada pelo evento in-app (cumulativa ou no dia, dependendo da sua configuração) |
| Usuários únicos | Número de usuários únicos que realizam o evento in-app (cumulativo ou no dia, dependendo da sua configuração) |
| Conversões de IAE (cumulativas) | **Conversão no aplicativo**: taxa de conversão de instalação/retargeting para um evento in-app. O número de usuários únicos que realizam um determinado evento in-app pela**primeira** **vez** dividido pelo número de usuários únicos na coorte. Por exemplo, o número de usuários [únicos] em uma coorte é 100. |
| Conversões de IAE (no dia) | Taxa de conversão de evento in-app: número de usuários únicos no dia que realizam o IAE / conversões * 100 |
| eCPA | Custo efetivo por ação (evento): custo / número cumulativo de usuários únicos que realizam o evento in-app |

</Accordion>

<div id="additional-information" />

## Informações adicionais

<div id="cohort-for-agencies" />

<Accordion title="Coorte para agências">

* O anunciante precisa conceder permissão à agência para usar Coorte.
  * Para dar permissão a uma agência, o anunciante:
    1. Vá para **Configuração** > **Integrações ativas.**
    2. Seleciona a agência.
    3. Acesse a guia de permissões, ative **Permitir acesso aos seus relatórios de retenção e coorte.**
* As agências estão limitadas a acessar os dados de tráfego gerados pela agência. Elas não podem ver os dados relacionados ao tráfego orgânico ou não orgânico gerado em outro lugar.

</Accordion>

<div id="use-cases" />

<Accordion title="Casos de uso">

<div id="revenue-sum-by-geo" />

#### Soma da receita por geo

**Gráfico: receita acumulada por usuário**

<Image align="center" alt="Screenshot 2023-10-31 at 16.56.31.png" src="https://files.readme.io/cde4e25a051e159cd4e1a1f192eda79df1d3df6f5891fcda2c24a01e0baa462b-small-32127949501201.png" />

**Tabela: receita por dia**

<Image align="center" alt="Full_cohort2_us-en.png" src="https://files.readme.io/be3949a33cdf489eb7735acbf06c7abbecfd46f84a20d463e50ddfe815cc3368-small-32127949501969.png" />

<div id="in-app-event-conversion" />

#### Conversão de evento in-app

Um anunciante define um evento in-app af\_purchase. O gráfico de coorte exibe a porcentagem de usuários de aplicativos na coorte que efetuaram uma compra em mobile. Podemos ver que no dia 10, por exemplo, quase 30% (11,11 %+9.71%+7,47%) dos usuários da coorte realizaram uma compra em mobile

<Image align="center" alt="cohort use case 3.png" src="https://files.readme.io/d2709ec30a9f6cc3fe55503af557153b6a2677948d0ca0b9a477af9e47746c33-small-32127933347089.png" />

</Accordion>

<div id="faq" />

<Accordion title="Perguntas frequentes">

| Pergunta | Resposta |
| --- | --- |
| Posso visualizar o <Anchor target="_blank" href="/marketers/pt/docs/apple-ads-integration-setup#analyze-keyword-cost">Custo e ROI da palavra-chave</Anchor> do Apple Search Ads? | Sim, é possível.  <br />O Apple Search Ads nos mostra o custo de cada palavra-chave por dia, separado por Campanha/Conjunto de Anúncios/Anúncio. **Observação:** a análise detalhada por localização/país não está disponível. |
| Para uma determinada fonte de mídia, por que o mesmo nome de campanha é exibido mais de uma vez? | <ul><li>Se você usar o mesmo nome de campanha com campanhas que tem IDs de campanha diferentes, o nome será exibido mais de uma vez.</li><li>Você deve alocar nomes exclusivos de IDs de campanha</li><li>Ao alterar os nomes da campanha, os dados são alinhados com o último nome usado.</li></ul> |
| Posso visualizar usuários orgânicos? | Por definição, os usuários orgânicos estão incluídos nos relatórios de Cohort.<br /><br />**Para limitar o relatório de Cohort apenas a usuários orgânicos:**<ol><li>No **dashboard de Cohort**, clique no botão **Editar Cohort**.</li><li>Na janela de configuração de Cohort defina **Filtrar por** > **Fonte de mídia** é **Orgânico**: [![cohort_setup_filtered_by_media_source_is_organic.png](https://files.readme.io/ba95397eac2b66a365a2aabb2f56587e78624be5ecd06dd6c0463e19dfe9e26a-32127949503889.png)](https://files.readme.io/ba95397eac2b66a365a2aabb2f56587e78624be5ecd06dd6c0463e19dfe9e26a-32127949503889.png)</li><li>Clique em **Aplicar alterações**</li></ol> |
| Posso ver dados de instalações excluídas? | Instalações excluídas, como instalações de SRNs que foram excluídas devido a políticas de retenção de dados ou instalações excluídas do GDPR, não podem ser vistas no painel de coorte.<br /><br />Para obter mais informações, <Anchor target="_blank" href="/marketers/pt/docs/user-level-data-retention#períodos-de-retenção-de-dados-de-parceiros">clique aqui.</Anchor> |
| Posso comparar os dados da visualização diária com os dados das visualizações semanais ou mensais? | Não é fácil comparar dados de uma granularidade diária com uma granularidade semanal ou mensal, porque os LTVs de coorte não se alinham.<br /><br />Ao visualizar coortes em granularidade diária, **o Dia 0** exibe os dados do dia das instalações. O dia 1 é o dia seguinte à instalação, o dia 2 é 2 dias após a instalação, etc. <br /><br />Ao visualizar coortes em granularidade semanal, os dados são exibidos para todas as instalações feitas em **toda a Semana 0**. A semana 1 é a semana após a instalação, a semana 2 é 2 semanas após a instalação, etc. <br /><br />Ao visualizar coortes em granularidade mensal, os dados são exibidos para todas as instalações feitas em **todo o Mês 0**. Mês 1 é o mês após a instalação, Mês 2 é 2 meses após a instalação, etc. <br /><br />Isso significa que os cronogramas de LTV não se alinham. Por exemplo, se você observar os dados de 9 a 15 de janeiro: se você usar a granularidade diária, **o Dia 0** contém os dados do primeiro dia de todas as **instalações feitas de 9 a 15 de janeiro.** E **o Dia 6** contém dados dos primeiros 6 dias pós-instalação de todas as instalações feitas **de 9 a 15 de janeiro**. Enquanto isso, na **granularidade semanal**, **a Semana 0** contém dados de **todo o período** para todas as instalações **feitas de 9 a 15 de janeiro**. Portanto, para instalações em **9 de janeiro**, os dados são como **o dia 6**. Mas para instalações em **15 de janeiro**, é como **o dia 0**. |
| Por que há uma diminuição na receita cumulativa entre períodos de cohort? | Normalmente, a receita cumulativa aumenta a cada período de cohort; por exemplo, D2 é maior que D1. No entanto, às vezes ela diminui por causa de receita negativa, por exemplo, de eventos de devolução. Você pode verificar isso consultando os dados no dia (hora/dia/semana/mês) para ver se há receita negativa em um período de cohort específico. |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Limitações">

| Caraterística | Observações |
| --- | --- |
| Acesso da ad network ao Coorte | Não disponível |
| Acesso das agências | Disponível<ul><li>Limitado a um aplicativo.</li><li>Contas híbridas não podem acessar Coorte</li><li>Solicite permissão de acesso para cada aplicativo.</li><li>Não é possível selecionar vários aplicativos.</li><li>Acesso a dados orgânicos não é possível.</li></ul> |
| Transparência da agência | Disponível a partir de 10 de janeiro de 2021 |
| Fuso horário específico do aplicativo | <ul><li>Disponível</li><li>Exceção: em todos os casos a seguir, a AppsFlyer ignora o fuso horário específico do aplicativo e usa como fuso horário padrão UTC +0:<ul><li>O relatório de coorte contém dados de vários aplicativos, e os aplicativos têm fusos horários diferentes.</li><li>Todos os aplicativos têm o mesmo fuso horário e o fuso horário de pelo menos um dos aplicativos foi alterado durante o período do relatório da coorte. Para determinar o período do relatório:<ul><li>Data inicial: a primeira data no período da conversão</li><li>Data final: é calculada somando o número de dias na duração da exibição à última data no período da conversão. Exemplo: Última data: 1 de janeiro de 2019. Duração do relatório: 30 dias. Data final: 31 de janeiro de 2019</li></ul></li><li>Os dados semanais e mensais serão exibidos no fuso horário UTC</li></ul></li></ul> |
| Custo | <ul><li>**Métricas relacionadas ao custo:** no Coorte, os dados de custo são incluídos somente se houver uma atribuição associada (instalação, reengajamento ou reatribuição). Em outras palavras, se uma campanha incorrer em custos com base em cliques e impressões, mas não tiver atribuições, o custo não será incluído nos relatórios de coorte. Esse princípio é válido para todos os níveis da hierarquia de publicidade.</li><li>Custo: a AppsFlyer não reporta dados de custo para palavras-chave que contêm letras maiúsculas no relatório de cohort ou na API de cohort.</li></ul> |
| Moeda específica do aplicativo | <ul><li>Disponível</li><li>Exceção: todos os aplicativos precisam usar a mesma moeda. Se não usarem, USD é usado.</li></ul> |
| Download de arquivos CSV: | <ul><li>Máximo de 10.000 linhas.</li><li>Disponível somente para relatórios de performance do tempo de vida do usuário. Não está disponível para a tendência KPI por tempo de atribuição.</li><li>Limite de 10 exportações CSV por minuto e 100 por dia (por usuário).</li></ul> |
| CohortGraph.png | Os gráficos exibem os 5 ou 10 melhores classificados pelo número de usuários de aplicativos no cohort. Isso é independente da dimensão exibida. |
| Tabela | As tabelas exibem até 50 linhas. Os usuários, o custo e o eCPI médio (custo efetivo por instalação) sempre são exibidos independentemente da métrica selecionada. |
| Reinstalações | <ul><li>Reinstalações: se os eventos pós-reinstalação forem considerados orgânicos não atribuídos, eles não serão incluídos no Coorte.<ul><li>Estão incluídos apenas a partir de 26 de maio de 2024. <Anchor target="_blank" href="/marketers/pt/docs/bulletin-cohort-data-includes-unattributed-sessions-and-events">Saiba mais</Anchor></li><li>O tempo de instalação baseia-se no campo <Anchor target="_blank" href="/marketers/pt/docs/raw-data-field-dictionary#device-info::dfd9504e">device\_download\_time</Anchor>.</li><li>Não são contabilizados para medições de usuários únicos e de retenção.</li></ul></li><li>Se os eventos após reinstalação forem atribuídos à primeira instalação, são sempre incluídos. <Anchor target="_blank" href="/marketers/pt/docs/measure-reinstalls#inapp-events-and-how-they-are-attributed">Saiba mais</Anchor></li></ul> |
| Informações | Limite de 20 consultas de dados por minuto e 500 por dia (por usuário). Alterar período de tempo, agrupamento, KPI, etc. é considerado uma nova consulta. |
| Dados orgânicos | Incluso |
| Dados não orgânicos | Incluso |
| Atualização de dados | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/about-data-freshness-and-timezone-support#eod">em tempo real</Anchor></li><li>Exceções:<ul><li>Coortes diárias:<ul><li>Métricas de custo, receita publicitária e desinstalação são atualizadas diariamente.</li><li>As desinstalações são calculadas uma vez por dia usando o horário UTC.</li></ul></li><li>Coortes semanais e mensais:<ul><li>Dados em tempo real não estão disponíveis. Os dados só aparecerão depois de concluídos (ou seja, no final da semana ou do mês).<br />No entanto, os dados em que alguns dos dados de instalação foram finalizados, como alguns dados concluídos (tempo pós-instalação) e outros ainda não iniciados, serão exibidos.</li></ul></li></ul></li></ul> |
| Dados históricos | <ul><li>Coorte diária: 2 anos</li><li>Coortes semanais/mensais: 3 anos</li></ul> |
| Geolocalização/país | <ul><li>Disponível</li><li>Quando a localização geográfica é desconhecida (N/A), os dados de receita de anúncios não são exibidos no agrupamento por localização.</li></ul> |
| Contagem de sessões | A contagem de sessões para o Dia 0 na visualização de Retargeting pode ser menor do que a contagem de usuários.<br />Há algumas razões para isso acontecer. As mais comuns são:<ul><li>A sessão de reengajamento já foi atribuída antes que o reengajamento tenha sido registrado. Neste caso, não será atribuído à sessão de retargeting</li><li>Filtrando por outras configurações, como o **Tempo mínimo entre as sessões**. Nesse caso, o reengajamento é registrado. No entanto, as sessões são filtradas e não serão gravadas</li></ul> |
| Retargeting e dados unificados | Os dados mensais da sessão estão disponíveis apenas de 1º de setembro de 2021 em diante |
| Receita de anúncios | <ul><li>Não disponível ao visualizar coortes com granularidade por hora.</li><li>Podem haver discrepâncias entre os valores das receitas de anúncios exibidas nos dashboards de Cohort e Visão Geral. Isso ocorre quando as ad networks informam a receita em UTC e os aplicativos têm um fuso horário diferente.</li><li>Para eventos af\_ad\_revenue, a métrica de usuários únicos não está disponível quando o tipo de agregação é:<ul><li>"Cumulativo".</li><li>"No dia", para datas entre 5 de outubro de 2022 e 16 de fevereiro de 2023.</li></ul></li></ul> |
| Granularidade de semanas e meses | <ul><li>A granularidade de semana e mês só está disponível no painel de coorte.</li><li>**Usuários únicos** e métricas de **taxa de conversão** não estarão disponíveis se os dados incluírem instalações anteriores a novembro de 2022.</li><li>Os dados históricos estão disponíveis apenas a partir do ano de 2021.</li><li>Dias pós-instalação: para cohorts que incluem instalações de janeiro de 2021 a dezembro de 2022, o período pós-instalação é limitado a um ano (o que significa 52 semanas ou 12 meses). Para cohorts que incluem instalações posteriores, os dados pós-instalação estão disponíveis por até 3 anos (o que significa 156 semanas ou 36 meses).</li></ul> |
| Período de coorte | <ul><li>O período de conversão é referido como 0 (Hora 0, Dia 0, Semana 0 ou Mês 0). O dia seguinte é o dia pós-conversão 1, e assim por diante.</li><li>Na AppsFlyer, um período de coorte não leva em consideração o carimbo de data/hora de instalação específico. Em vez disso, as horas de coorte são arredondadas para a hora mais próxima e os dias, semanas e meses de coorte são baseados no dia, semana ou mês do calendário. Isso pode causar discrepâncias ao comparar os dados de coorte da AppsFlyer com os dados de coorte de outras redes, onde todos os períodos de coorte são determinados pelo carimbo de data/hora de instalação específico (o que significa que uma hora é de 60 minutos após a instalação, um dia é o registro de 24 horas após a instalação período após o carimbo de data/hora da instalação, etc).</li><li>A consulta do período máximo de cohort (intervalo de tempo) é de 60 dias para granularidade diária, 60 horas para horária, 12 meses para mensal e 26 semanas para semanal.</li></ul> |
| "event\_name" | Recomendação: escolha nomes descritivos para seus eventos in-app, não apenas "Receita". Um evento in-app chamado "Receita" às vezes pode gerar confusão e interferir em outras métricas de receita. |
| Classificar | Ao filtrar por campanhas, você pode selecionar até 100 valores. |
| Dados parciais | Dados parciais estão disponíveis apenas para períodos diários; não para horários, semanais ou mensais. |
| Recurso | Os 1.000 principais eventos in-app (por contagem de eventos) são exibidos em ordem alfabética no menu suspenso da configuração da análise de cohort. |

</Accordion>

<div data-zendesk-anchors="cohort-dashboard=dashboard-de-cohort 01H7T5AGP75A36TVWSM7H81E8P=dashboard-de-cohort 01H7T5AGP7SGPZNK8VTDYBTY2B=observa%C3%A7%C3%B5es using-cohort=usando-coorte 01H7T5AGP7XDKN85TR0J4V8TP3=usando-coorte 01H7T5AGP7FDZNVM9PDBQJPMA0=setting-up-an-analysis using-my-reports%E2%80%94save-and-select-reports=using-my-reports-save-and-select-reports 01H7T5AGP8KRZ9207DCYGRGGC0=using-my-reports-save-and-select-reports 01H7T5AGP84HVD2BQ9Z8S13D5K=export-the-cohort-to-a-csv-file cohort-concepts=princ%C3%ADpios-de-cohort 01H8K817ZPJTRBP1KK90FVV57T=princ%C3%ADpios-de-cohort 01H8K817ZPZTG476KZ83F6Z460=cohort-periods h_01JJH967X8P2NF3AFBSNMBD7B4=view-types 01H8K817ZPBVTGT5R18XGQHYT2=trend-types user-lifetime-performance=usu%C3%A1rios-4 01H8VNMYN0149T418BXM8RGBN9=usu%C3%A1rios-4 kpi-by-attribution-time=n%C3%A3o-est%C3%A1-dispon%C3%ADvel-para-a-tend%C3%AAncia-kpi-por-tempo-de-atribui%C3%A7%C3%A3o 01H8VNRGMWS8SSDM5KX08EDAS2=n%C3%A3o-est%C3%A1-dispon%C3%ADvel-para-a-tend%C3%AAncia-kpi-por-tempo-de-atribui%C3%A7%C3%A3o example-user-lifetime-performance-trend-vs-kpi-by-attribution-time-trend=exemplo-tend%C3%AAncia-de-desempenho-da-vida-%C3%BAtil-do-usu%C3%A1rio-x-kpi-por-tend%C3%AAncia-de-tempo-de-atribui%C3%A7%C3%A3o 01H8K98XE9T23QGB440GHRB8E8=exemplo-tend%C3%AAncia-de-desempenho-da-vida-%C3%BAtil-do-usu%C3%A1rio-x-kpi-por-tend%C3%AAncia-de-tempo-de-atribui%C3%A7%C3%A3o 01H7T5AGP8PN12P2C4RGGQ0R95=partial-data 01H7T5AGP8XNG1CW2FPJSEEJ45=list-of-dimensions-for-grouping-and-filtering time-in-the-case-of%0A%20%20%0A%20%20daily-granularity-is-the-date%0A%20%20hourly-granularity-is-the-hour-of-the-day%0A%20%20weekly-granularity-is-the-week-of-the-year%0A%20%20monthly-granularity-is-the-month-of-the-year=time-in-the-case-of-daily-granularity-is-the-date-hourly-granularity-is-the-hour-of-the-day-weekly-granularity-is-the-week-of-the-year-monthly-granularity-is-the-month-of-the-year 01H7T5AGP708H7JGTS1RJ07H27=metrics-available information=informa%C3%A7%C3%B5es-adicionais 01H7T5AGP8J9AQ1BREYZ0JWWZ4=informa%C3%A7%C3%B5es-adicionais 01H7T5AGP83FRX1H9WVMS485MT=cohort-for-agencies 01H7T5AGP8JF0EAX8WEFNSEKM9=use-cases revenue-sum-by-country=soma-da-receita-por-geo 01H7T5AGP8R6913GPXWM6DGASF=soma-da-receita-por-geo inapp-event-conversion=convers%C3%A3o-de-evento-in-app 01H7T5AGP80W5J1VEZ40MHGPPF=convers%C3%A3o-de-evento-in-app 01H7T5AGP85T7H25863GXJCVCW=faq 01H7T5AGP90NADB7YXTFEMTSAX=traits-and-limitations" />
