---
title: Relatório de performance agregada da SKAN
metadata:
  keywords:
    - Advertisers
    - SKAD
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2020-10-08T09:45:03Z'
  edited_at: '2026-08-18T00:32:15Z'
  id: 360014104157
  locale: pt
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/pt/articles/360014104157
---
> **Visão geral:** Desempenho do SKAN enriquecido com pontos de dados adicionais. Semelhante aos dados no painel do SKAdNetwork. Agregue usando a data de instalação ou a data de chegada do postback.

<div id="skan-aggregated-performance-report-api" />

## Relatório de performance agregada da SKAN

A API retorna métricas de atribuição relatadas pela Apple SKAdNetwork (dados reais) e outros pontos de dados usando a data de chegada de instalação ou postback. O relatório é semelhante em estrutura aos dados apresentados no<Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">Painel da SKAN</Anchor>.

<div id="using-skan-aggregated-performance-report-api" />

<Accordion title="Usar a API de relatório de desempenho agregado do SKAN">

**Para usar a API de relatório de desempenho agregado do SKAN**:

1. Obtenha o token da API. Um administrador precisa obter o token.
2. Forneça ao seu desenvolvedor o token de API a ser usado no cabeçalho de autenticação.
3. Forneça a seus desenvolvedores os parâmetros a serem inseridos quando eles fizerem a chamada de API, conforme descrito na seção a seguir. Os parâmetros determinam o foco do relatório, como ele é organizado e fornecem um cronograma de relatório.
4. Diga ao seu desenvolvedor para seguir a <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/skan-agg-performance-report-api-get">API de relatório de desempenho agregado do SKAN</Anchor> no hub do desenvolvedor.

<div id="parameters" />

#### Parâmetros

| Nome do parâmetro | Formato | Obrigatório |
| --- | --- | --- |
| `tipo_de_data` | O tipo de data usado no intervalo de datas delimitado por `start_date` e `end_date`<br /><br />Opções:<ul><li>[Padrão]`install` A data de instalação derivada pela AppsFlyer usando a hora de chegada do postback e depois de considerar o período de mensuração.</li><li>`arrival`: A hora de chegada do postback. Observação: As métricas de instalação orgânica têm o valor N/A.</li></ul>Dados do Google Ads: As datas de instalação e chegada são as mesmas devido à metodologia de relatórios do Google Ads. | Não |
| `start_date` | O intervalo de datas de instalação é limitado por start\_date e end\_date. Atenção! A data de instalação é diferente da data de chegada do postback.<ul><li>Data de instalação mais antiga com formato AAAA-MM-DD</li><li>Data mais antiga permitida: 2020-11-01<br />Exemplo: `2020-11-05`</li></ul> | Sim |
| `end_date` | <ul><li>Data de instalação mais recente com o formato AAAA-MM-DD</li><li>Número máximo de dias por chamada de relatório: 90 dias</li><li>Exemplo: `2020-11-12`</li></ul> | Sim |
| `tipo_de_visualização` | Filtre as instalações por tipo da seguinte maneira:<ul><li>`acquisition`: Instalações</li><li>`retargeting`: Transferências</li><li>`unified`: Aquisição e redownloads combinados.</li><li>[Padrão] `unificado`</li><li>As métricas de custo, clique e impressão retornam quando `view_type=unified`</li></ul> | Não |
| `valores_de_conversão_modelados` | <ul><li>Disponível apenas a partir da V2</li><li>O valor pode ser `true` ou `false`</li><li>Se true, o postback incluirá os dados modelados ao preencher as colunas de métrica decodificadas. [Veja os campos disponíveis](/docs/skan-aggregated-performance-report-api#report-structure-and-example)</li><li>Se `false`, o postback apresenta dados decodificados como recebidos por postbacks brutos da SKAN, sem dados modelados.</li><li>O valor padrão é `false`.</li></ul> | Não |

</Accordion>

<div id="report-structure-and-example" />

<Accordion title="Estrutura e exemplo do relatório">

A API retorna um arquivo CSV.

* Os campos e métricas disponíveis no relatório estão listados na tabela a seguir.
* Algumas métricas (receita, engajamento, conversão) dependem da SKAN <Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio">configurações de mensuração de desempenho.</Anchor>
* O relatório inclui apenas os eventos in-app que os usuários realizaram durante o período do relatório. Dessa forma, o número e a sequência de colunas de eventos in-app podem mudar de relatório para relatório. Não confie na sequência de colunas ao projetar seu processo de importação de dados.
* Exemplos: [V1](https://docs.google.com/spreadsheets/d/e/2PACX-1vSmnyUITQjRxNp6-rz8Xzscu-Rr4Kn2DW1du2VppS-QrpyQSZ0GKQ_qZdWNdNoLuwJAmgh2O-bWiuU3/pub?gid=0&single=true&output=csv) | <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQogLd4w3xgrjQBmEiHLfcvz1e9dtWez_Rdg1OxV8bSRHRE-wxZJItfT6azLr4iZAgsW2Vxr_WVmEYo/pub?gid=0&single=true&output=csv">V2</Anchor>

<div id="report-fields" />

#### Campos do relatório

| Nome do campo | Dimensão ou métrica | Disponível com token API V1 | Disponível com token API V2 | Disponível com token API V2 (para SKAN 4) | Disponível com filtro somente de dados modelados |
| --- | --- | --- | --- | --- | --- |
| Data<br /><br />Os dados estão de acordo com o date\_type selecionado. | Dimensão | Não | S | S | S |
| Fonte de mídia (pid) | Dimensão | S | S | S | S |
| Campanha (c) | Dimensão | S | S | S | S |
| ID da campanha | Dimensão | S | S | S | S |
| ID do site | Dimensão | S | S | S | Não |
| Conjunto de anúncios | Dimensão | Não | S | S | S |
| ID do conjunto de anúncios | Dimensão | Não | S | S | S |
| Anúncio | Dimensão | Não | S | S | Não |
| ID do anúncio | Dimensão | Não | S | S | Não |
| País | Dimensão | S | S | S | Não |
| Sinalizador de atribuição AF<br /><br />Veja: <Anchor target="_blank" href="/marketers/pt/docs/single-source-of-truth-ssot-guide-for-ios-attribution">Guia SSOT</Anchor> | Dimensão | Não | S | S | S |
| Índice de sequência de postback | Dimensão | Não | Não | S | S |
| Criativo | Dimensão | Não | Não | S | Não |
| Canal | Dimensão | Não | Não | S | Não |
| Impressões | Métrica | S | S | S | S |
| Cliques | Métrica | S | S | S | S |
| Click-through rate | Métrica | S | S | S | S |
| Instalações | Métrica | S | S | S | S |
| Clique nas instalações (fidelity\_type = 1) | Métrica | S | S | S | S |
| Instalações de visualização<br /><br />(fidelity\_type = 0) | Métrica | S | S | S | S |
| Taxa de valor de conversão nula<br /><br />[Disponível a partir de 23 de janeiro de 2022] | Métrica | Não | S | S | S |
| Taxa de conversão | Métrica | S | S | S | S |
| Usuários convertidos | Métrica | S | S | S | S |
| Usuários convertidos/Instalações | Métrica | S | S | S | S |
| Receita total | Métrica de receita | S | S | S | S |
| Custo total | Métrica | S | S | S | S |
| ROI | Métrica de receita | S | S | S | S |
| OPCIONAL | Métrica de receita | S | S | S | S |
| eCPI médio | Métrica | S | S | S | S |
| `{af_skad_revenue}` (Usuários únicos) | Métrica de receita | S | S | S | S |
| `{af_skad_revenue}` (Contador de eventos) | Métrica de receita | S | S | S | S |
| `{nome do seu evento in-app}` (Usuários únicos) | Métrica | S | S | S | S |
| `{nome do seu evento in-app}` (Contador de eventos) | Métrica | S | S | S | S |

</Accordion>

<div id="specifications-and-limitations" />

<Accordion title="Especificações e limitações">

| Especificações | Observações |
| --- | --- |
| Atualização dos dados | A disponibilidade de dados está de acordo com a taxa de atualização de dados do <Anchor target="_blank" href="/marketers/pt/docs/about-data-freshness-and-timezone-support#skan">SKAN</Anchor>. |
| Intervalo de datas | <ul><li>Ao definir o intervalo de datas, a data mais recente deve ser a data atual do fuso horário UTC menos 3 dias. Ou seja, em 31 de março, use 28 de março.</li><li>Data mais antiga aceita: 1 de novembro de 2020</li><li>Intervalo máximo de consulta: 90 dias</li></ul> |
| Limites de taxa | <ul><li>As consultas retornam até 250 mil linhas</li><li>10 chamadas por minuto</li></ul> |
| SRNs | <ul><li>Meta ads: os dados estão disponíveis.</li><li>Google Ads: As instalações podem ser registradas até 45 dias após a instalação devido à metodologia de tempo de clique do Google. Se você consultar dados do Google dos últimos 45 dias, isso fornece a cobertura necessária para os dados do Google SKAN.</li></ul> |
| Acesso da ad network | Se você for um parceiro de análise, peça permissão ao anunciante. |
| Acesso de agência | Não disponível |
| Fuso horário específico do aplicativo | Somente UTC |
| Moeda específica do aplicativo | Sempre USD |
| Dados orgânicos | Calculado como a diferença entre todos os dados relatados pelo SDK diretamente à AppsFlyer menos os dados não orgânicos relatados pelos postbacks da SKAN |
| Dados não-orgânicos | Calculado usando postbacks da SKAN recebidos pela AppsFlyer |
| Histórico de dados | Dados de conversão mais antigos aceitos (instalação ou retarget): 1 de novembro de 2020 |
| Acesso do usuário da conta | O token de autorização está disponível para um usuário administrador no painel. |
| Custo total | A API SKAN pode não incluir a métrica de custo total se a atribuição regular (visão geral regular) contiver campanhas do SKAN que, no nível de granularidade mais baixo (por exemplo: anúncio, país ou ID do site) tenham mais de 50 mil linhas. |

</Accordion>

<div data-zendesk-anchors="skadnetwork-postback-arrival-date-aggregation-reporting-api=relat%C3%B3rio-de-performance-agregada-da-skan h_01HH9WHP1SDQ3TJPZ931R9KWKH=relat%C3%B3rio-de-performance-agregada-da-skan h_01HH9WHP1S7PWJHKAKHN434G7Y=using-skan-aggregated-performance-report-api parameters=par%C3%A2metros h_01HH9WHP1SZQZGSZ4WEPAAFNV7=par%C3%A2metros h_01HH9WHP1SYEHGJBBWSMS2XQP0=report-structure-and-example skadnetwork-aggregate-report-structure=campos-do-relat%C3%B3rio h_01HH9WHP1STYNJK3DRESDF23DG=campos-do-relat%C3%B3rio h_01HH9WHP1T4NEMW56XVYKM3KHM=specifications-and-limitations" />
