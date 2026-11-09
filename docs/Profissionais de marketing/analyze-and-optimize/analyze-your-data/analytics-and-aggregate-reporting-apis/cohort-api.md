---
title: API de Coorte
metadata:
  keywords:
    - API
    - Advertisers
    - Partners
    - Developer
    - Premium
    - Gray
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2020-01-14T07:04:32Z'
  edited_at: '2026-08-18T00:02:53Z'
  id: 360004799057
  locale: pt
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/pt/articles/360004799057
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Resumo:** a Cohort API permite que os anunciantes acessem dados de cohort de forma programática. Use a API para integrar dados de cohort em sistemas de BI e de automação de marketing.

<div id="cohort-api" />

## API de Coorte

A Cohort API é usada para coletar dados de performance de campanhas de cohort na plataforma da AppsFlyer. Funcionalmente, ela equivale ao <Anchor target="_blank" href="/marketers/pt/docs/cohort-and-retention-dashboard">dashboard de Cohort</Anchor>.

Para usar cohort e retenção, você escolhe os dados que deseja visualizar. Você seleciona usuários de um aplicativo e os segmenta pela hora da conversão. Métricas de cohort como receita, ROI e taxas de conversão de eventos estão disponíveis. Para comparação, separe o cohort em dimensões como campanha ou fonte de mídia. O resultado é um arquivo CSV ou JSON. Você pode usar os resultados para descobrir padrões ou mudanças na performance ao longo dos ciclos de vida dos usuários ou da campanha.

Consulte <Anchor target="_blank" href="https://www.appsflyer.com/blog/cohort-report-mobile-marketing-kpis/?utm_campaign=Blog%20Subscription%2003-2019&utm_source=hs_email&utm_medium=email&utm_content=76370689&_hsenc=p2ANqtz-8SX49xuEw2WX_Vrlh11_zxlDFvlfMpBzSQm1I-nFhc0WbZDf0ACC-VEi4qmKhesHCsUNdhU50Oinl-urwnGAOZMwwHSTp6UgdChCi7ARayJFUFTus&_hsmi=76370689">Casos de uso de cohort</Anchor>.

Para usar a Cohort API

1. ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) Acesse o <Anchor target="_blank" href="/marketers/pt/docs/managing-appsflyer-tokens">token da API</Anchor>. Um administrador precisa solicitar o token.
2. Forneça ao seu desenvolvedor o token da API para ser usado no header de autenticação.
3. Forneça aos seus desenvolvedores os [parâmetros](#filtering-and-grouping-parameters) a serem inseridos quando eles fizerem a chamada de API, conforme descrito nas seções a seguir. Os parâmetros determinam o foco do relatório, como está organizado e fornecem um período para o relatório.
4. Diga ao seu desenvolvedor para seguir <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_app-id">as instruções da Master API</Anchor> no developer hub.

<div id="filtering-and-grouping-parameters" />

<Accordion title="Parâmetros da Cohort API">

Use os parâmetros de filtro a seguir para obter os dados necessários.

| Nome do parâmetro | Descrição | Obrigatório |
| --- | --- | --- |
| <span id="bearer"></span>bearer | Token da API usado no header de autenticação da API. | Sim |
| <span id="cohort-_type"></span>cohort \_type | O tipo de atribuição de cohort (conversão) é um dos seguintes: `user_acquisition`, `retargeting`, `unified`<ul><li>Unified combina a performance de campanhas de aquisição de usuários e retargeting.</li><li>Se um evento for atribuído a campanhas de retargeting e de aquisição de usuários, somente o evento de retargeting será incluído nos KPIs retornados, o que significa is\_primary=true.</li><li>Formato: Sequência de caracteres</li><li>Exemplo: `"cohort_type": "user_acquisition"`</li></ul> | Sim |
| <span id="min_cohort_size"></span>min\_cohort\_size | O tamanho mínimo do cohort é usado para reduzir o número de registros retornados, excluindo cohorts com poucos usuários. Isso significa que o KPI "usuários" tem um valor igual ou maior do que o especificado.<ul><li>Formato: Inteiro</li><li>Valor mínimo permitido: 1. Não envie 0 (Zero)</li><li>Padrão: 1</li><li>Exemplo: `"min_cohort_size": 50`</li></ul> | Não |
| <span id="from"></span>início | Limite inferior do período de atribuição de LTV. A data mais antiga disponível é 720 dias antes da data atual.<ul><li>Formato: String aaaa-mm-dd</li><li>Exemplo: `"from": "2020-01-02"`</li></ul> | Sim |
| <span id="to"></span>to (até) | Limite superior do período de atribuição de LTV<ul><li>Número de dias no intervalo: 1 a 31 dias</li><li>Para um único dia: os valores `from` e `to` são idênticos.</li><li>Formato: aaaa-mm-dd</li><li>Exemplo: `"from": "2020-01-01", "to": 2020-01-31` é 31 dias.</li></ul> | Sim |
| <span id="granularity"></span>granularity | Granularidade horária para as últimas 72 horas, com a configuração `"granularity": "hour"` e a configuração do intervalo `from` e `to` para incluir o horário do dia.<ul><li>Formato: aaaa-mm-dd hh:mm:ss</li><li>Exemplo:</li></ul>`"granularity": "hour", "from": "2021-12-01 14:00:00", "to": "2021-12-03 11:00:00",` | Não |
| <span id="partial_data"></span>partial\_data | Para evitar distorção e má interpretação dos dados, o cohort retorna dados de dias completos. No entanto, os dados de dias parciais podem ser úteis.<br /><br />O número de dias de cohort completos para uma consulta é calculado como a diferença entre a data de hoje e a data final *(to)*.<ul><li>[Padrão] Se for "false", retorna dias completos.</li><li>Se for "true", retorna até 180 dias de cohort, incluindo dias com dados incompletos.</li><li>Formato: Booleano</li><li>Versão da UI da plataforma: false</li></ul>**Exemplo**: em 10 de maio, o número de dias de cohort completos para usuários que realizaram conversões entre 1 e 30 de abril é 10.<ul><li>Se for "false" [padrão], com dias de cohort de 0-9 são retornados. Esse é o número de dias (10) entre a última data de conversão e hoje.</li><li>Se for "true", os dias de coorte 1 a 40 são retornados. Os dias 11 a 40 contêm dados parciais e não retornam. Por exemplo, desde 20 de abril, se passaram apenas 20 dias, e assim por diante.</li></ul>**Atenção:** : dados parciais só são permitidos quando o tipo de agregação é cumulativo. | Não |
| <span id="filters"></span>filters | Filtre os dados e os dias do período retornados. Selecione filtros na [lista de dimensões de filtro](/docs/cohort-api#list-of-group-by-and-filter-by-dimensions).<ul><li>Formato: Strings em um nested JSON. Os valores precisam estar em array.</li><li>**Exemplo de limite para áreas geográficas específicas:** `"filters": {"geo": ["US"]}`: inclui apenas usuários atribuídos aos Estados Unidos.</li><li>**Exemplo de período (cohort) em dias**: O filtro `period` define os dias para os quais as métricas são retornadas. Os valores possíveis são: 0-180.</li><li>Padrão: se nenhum filtro de "period" for definido, os dias 0 a 30, 60, 90 e 180 serão retornados. [Exemplo de filtro com "period"](/docs/cohort-api#using-period-filters)</li></ul> | Não |
| <span id="groupings"></span>groupings | <ul><li>Use parâmetros de agrupamento para incluir colunas adicionais e tornar seus relatórios menos granulares.</li><li>Selecione de 1 a 7 agrupamentos na [lista de dimensões](/docs/cohort-api#list-of-group-by-and-filter-by-dimensions).</li><li>Formato: Strings em array</li><li>Exemplo: `"groupings": ["af_ad", "c", "af_c_id", "af_prt"]`</li></ul> | Sim |
| <span id="kpis"></span>kpis | KPIs são as métricas usadas para obter insights sobre o comportamento dos usuários no seu aplicativo. [Aprenda a selecionar e formatar KPIs](/docs/cohort-api#selecting-and-formatting-kpis) | Sim |
| <span id="preferred_currency"></span>preferred\_currency | Um parâmetro que define o formato dos KPIs retornados. [Aprenda a formatar KPIs](/docs/cohort-api#formatando-funções-de-kpi) | Não |
| <span id="preferred_timezone"></span>preferred\_timezone | Um parâmetro que define o formato dos KPIs retornados. [Aprenda a formatar KPIs](/docs/cohort-api#formatando-funções-de-kpi) | Não |
| <span id="aggregation_type"></span>aggregation\_type | Um parâmetro que define o formato dos KPIs retornados. [Aprenda a formatar KPIs](/docs/cohort-api#formatando-funções-de-kpi) | Sim |
| <span id="per_user"></span>per\_user | Um parâmetro que define o formato dos KPIs retornados. [Aprenda a formatar KPIs](/docs/cohort-api#formatando-funções-de-kpi) | Não |

</Accordion>

<div id="selecting-and-formatting-kpis" />

<Accordion title="Selecionando e formatando KPIs">

* A tabela abaixo lista os KPIs disponíveis e suas funções associadas. Quando você chama um KPI, todas as suas funções retornam.
* Os seguintes KPIs sempre retornam: users, ecpi e cost
* Selecione um KPI adicional por chamada.
* Para cada KPI solicitado, todas as funções são retornadas.
* Formato: Strings em array
  * Exemplo A: `"kpis": ["sessions"]`
  * Exemplo B: `"kpis": ["event_name"]`

<table><thead><tr><th> </th><th> </th><th colspan="5">Funções</th></tr><tr><th rowspan="2">Padrão/Opcional </th><th rowspan="2">KPI (nome das dimensões) </th><th>Contagem</th><th>cvr (taxa de conversão)</th><th>Classificar</th><th>Soma</th><th>Usuários únicos</th></tr><tr><th>Número</th><th>Percentual</th><th>Percentual</th><th>Número</th><th>Número</th></tr></thead><tbody><tr><td>Sempre</td><td>usuários</td><td><span>S</span></td><td>-</td><td>-</td><td>-</td><td>-</td></tr><tr><td>Sempre</td><td>eCPI</td><td>-</td><td>-</td><td>-</td><td><span>S</span></td><td>-</td></tr><tr><td>Sempre</td><td>cost</td><td>-</td><td>-</td><td>-</td><td><span>S</span></td><td>-</td></tr><tr><td>Opcional</td><td> <code>"event_name"</code>(4) </td><td><span>S</span></td><td><span>S</span></td><td>-</td><td><span>S (3)</span></td><td><span>S</span></td></tr><tr><td>Opcional</td><td>revenue</td><td><span>S</span></td><td>-</td><td>-</td><td><span>S</span></td><td>-</td></tr><tr><td>Opcional</td><td>roas</td><td>-</td><td>-</td><td><span>S</span></td><td>-</td><td>-</td></tr><tr><td>Opcional</td><td>roi</td><td>-</td><td>-</td><td><span>S</span></td><td>-</td><td>-</td></tr><tr><td>Opcional</td><td>sessions</td><td><span>S</span></td><td>-</td><td><span>S</span></td><td>-</td><td><span>S(1)</span></td></tr><tr><td>Opcional</td><td>uninstalls (2)</td><td><span>S</span></td><td>-</td><td><span>S</span></td><td>-</td><td>-</td></tr><tr><td colspan="7"><p>(1) Sessões únicas retornam quando <em>agregation_type=on_day</em></p><p>(2) Indisponível quando cohort_type=unified </p><p>(3) Soma significa a receita total gerada pelo evento. No relatório, isso é indicado por <code>sum_event_name"</code></p><p>(4) Atenção! Os nomes dos eventos diferenciam maiúsculas de minúsculas</p></td></tr></tbody></table>

<div id="formatting-kpi-functions" />

#### Formatando funções de KPI

Os seguintes parâmetros definem o formato dos KPIs retornados.

| Parâmetro | Valores | Obrigatório |
| --- | --- | --- |
| preferred\_currency | Moeda de receita do KPI<ul><li>Quando "true", a receita será retornada usando a <Anchor target="_blank" href="/marketers/pt/docs/app-settings#localization-currency">moeda específica do aplicativo</Anchor> definida na plataforma.</li><li>[Padrão] Quando "false", os resultados serão retornados em USD.</li><li>Formato: Booleano</li><li>Versão da interface da plataforma: true</li></ul> | Não |
| preferred\_timezone | **Fuso horário dos intervalos de dados**<ul><li>Quando "true", os horários serão exibidos usando o <Anchor target="_blank" href="/marketers/pt/docs/app-settings#localization-time-zone">fuso horário específico do aplicativo</Anchor> definido na plataforma.</li><li>[Padrão] Quando "false", os horários serão exibidos usando o fuso horário UTC.</li><li>Formato: Booleano</li><li>Versão da interface da plataforma: true</li></ul> | Não |
| aggregation\_type | <ul><li>`cumulativo`</li><li>`on_day`</li></ul>`"aggregation_type": "cumulative"`<br /><br />`Formato: Sequência de caracteres` | Sim |
| per\_user | Divida a função KPI pelo número de usuários do aplicativo. Aplica-se apenas a KPIs relevantes.<ul><li>Quando "true", os valores de KPI serão divididos pelo número de usuários na cohort.</li><li>Quando "false", os valores de KPI não serão divididos pelo número de usuários.</li><li>Formato: Booleano</li><li>Exemplo em caso de "false": a receita total é de US$ 1000, o número de usuários do aplicativo é 500, o valor retornado é de US$ 2.</li></ul> | Não |

</Accordion>

<div id="list-of-group-by-and-filter-by-dimensions" />

<Accordion title="Agrupar por e filtrar dimensões">

<table><thead><tr><th>Nome da dimensão </th><th>Valor da API de dimensão</th><th>Agrupamentos</th><th>Filtros</th></tr></thead><tbody><tr><td>As ad</td><td>af_ad</td><td><span>S</span></td><td><span>S</span></td></tr><tr><td>ID do anúncio</td><td>af_ad_id</td><td><span>S</span></td><td><span>S</span></td></tr><tr><td>Campaign</td><td>C</td><td><span>S</span></td><td><span>S</span></td></tr><tr><td>ID da campanha</td><td>af_c_id</td><td><span>S</span></td><td><span>S</span></td></tr><tr><td>Canal</td><td>af_canal</td><td><span>S</span></td><td><span>S</span></td></tr><tr><td>Media Source</td><td>pid</td><td><span>S</span></td><td><span>S</span></td></tr><tr><td>Subparâmetro 1</td><td>af_sub1</td><td><span>S</span></td><td><span>S</span></td></tr><tr><td>Palavras-chave</td><td>af_keywords</td><td><span>S</span></td><td><span>S</span></td></tr><tr><td>Acesso para</td><td>af_prt</td><td><span>S</span></td><td><span>S</span></td></tr><tr><td>Conversion Type (1) </td><td>cohort_type</td><td><span>S</span></td><td><span>S</span></td></tr><tr><td>ID do site</td><td>id_do_site</td><td><span>S</span></td><td><span>S</span></td></tr><tr><td>Tipo de receita (2)</td><td>tipo_de_receita</td><td><span>X </span></td><td><span>S</span></td></tr><tr><td>Tipo de toque atribuído (3)</td><td>tipo_de_toque_atribuído</td><td><span>S</span></td><td><span>S</span></td></tr><tr><td>Conjunto de anúncios</td><td>af_adset</td><td><span>S</span></td><td><span>S</span></td></tr><tr><td>Adset ID</td><td>af_adset_id</td><td><span>S</span></td><td><span>S</span></td></tr><tr><td>Country</td><td>geo</td><td><span>S</span></td><td><span>S</span></td></tr><tr><td>Date (data de instalação/reatribuição/reengajamento no contexto do cohort_type selecionado) </td><td>data</td><td><span>S</span></td><td><span>X </span></td></tr><tr><td>Período</td><td><p>period</p><p><a href="./cohort-api#using-period-filters">Explicação detalhada</a></p></td><td><span>X</span></td><td><span>S</span></td></tr><tr><td colspan="4"><p>Observações: </p><p>Opções de dimensão:</p><p>(1) Tipo de conversão:  <code>user_acquisition</code>, <code>retargeting</code>(<code>re-engagement</code> e <code>re-attribution</code>), <code>unified</code></p><ul><li>Ao exportar:<ul><li> <code>re-engagement</code> será exibido como <code>retargeting</code> </li><li> <code>re-attribution</code> será exibido como <code>reattr</code> </li></ul></li></ul><p>(2) Tipo de receita: <code>regular</code>, <code>ad_monetization</code><span></span></p><p>(3) Tipo de toque atribuído: <code>click</code>, <code>impression</code>, <code>TV</code>, <code>pre-installed</code></p></td></tr></tbody></table>

</Accordion>

<div id="additional-information" />

## Informações adicionais

<div id="using-period-filters" />

<Accordion title="Usando filtros de período">

O período refere-se ao dia pós-atribuição, onde o período 0 é o dia da atribuição. Por exemplo, um usuário instala o aplicativo em 1 de janeiro. Esse é o dia da atribuição. Uma compra feita no período 0 significa que ela foi feita em 1 de janeiro. Uma compra feita no período 3 significa que ela foi feita em 4 de janeiro. Da mesma forma, para um usuário que instala em 11 de janeiro, o período é 0. Uma compra feita em 14 de janeiro seria o período 3.

Se o intervalo de datas do seu relatório for de 1 a 11 de janeiro, os usuários que atribuíram (instalaram) durante esse período serão incluídos no relatório. Nenhum outro dado é incluso.

* O valor do período pode ser um ou mais de 0-180. Por exemplo, 0, 1, 2, 30, 180.
* Se nenhum período for especificado, os valores padrão de 0, 1, 2 até 30, 60, 90 e 180 serão retornados.

<div id="example-period-filter" />

> 📄 **Exemplo de filtro de período**
>
> * Esse exemplo contém os parâmetros de consulta JSON, dados brutos e arquivo CSV resultante.
> * A consulta *filtrar o período* de 0, 1 e 2 e o KPI selecionado é *receita*.
> * A consulta especifica o tipo de agregação como "cumulativa". Mude para "on\_day" se você quiser acessar os dados do dia.
> * Como resultado, os dados retornados contêm:
>   * As métricas de usuários, custo e ecpi, que sempre retornam
>   * Métricas de receita que consistem em soma e contagem para cada período, significando os períodos 0, 1 e 2.
>
> **Consulta**
>
> ```json
> {
>     "cohort_type": "user_acquisition",
>     "min_cohort_size": 1,
>     "preferred_timezone": false,
>     "from": "2019-12-01",
>     "to": "2020-01-01",
>     "filters": {
>         "period": [
>             0,
>             1,
>             2
>         ]
>     },
>     "aggregation_type": "cumulative",
>     "per_user": false,
>     "groupings": [
>         "pid"
>     ],
>     "kpis": [
>         "receita"
>     ]
> }
> ```
>
> **Dados brutos**
>
> **![mceclip1.png](https://files.readme.io/846aade481d3b5fa72536817533bc3edad721f1ce6015edcb48bd500461342b9-32131110606865.png)**
>
> **Resultados**
>
> <Image align="center" alt="mceclip0.png" src="https://files.readme.io/c284e5133e4e811b9416c850e399ddefb3c5bfcfcf879f469556b7a6bc0062c6-32131110607249.png" />

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Características e limitações">

| Caraterística | Observações |
| --- | --- |
| Acesso da ad network | Não |
| Acesso da agência | Não |
| Fuso horário específico do aplicativo | Sim |
| Moeda específica da aplicação | Sim |
| Limitações de tamanho | Nenhuma. |
| Limitação de taxa | <ul><li>Limite de taxa de chamadas da API: 60 chamadas por minuto e 50.000 chamadas por dia, por conta</li><li>As consultas retornam até 30.000 linhas</li></ul> |
| Dados orgânicos | Disponível |
| Dados não orgânicos | Disponível |
| Limitação de dados de custo | <ul><li>Os dados de custo referem-se apenas a campanhas com pelo menos uma instalação registrada.</li><li>A AppsFlyer não informa dados de custo para palavras-chave que contenham letras maiúsculas no relatório de cohort ou na API de cohort</li><li>Você não pode mesclar algumas combinações de agrupamentos com custo. Por exemplo, o Meta Ads pode ter agrupamentos por geolocalização ou por canal, mas não ambos. A combinação exata de agrupamentos depende da ad network.</li></ul> |
| Atualização dos dados | A atualização dos dados depende de [parcial\_data](/docs/cohort-api#partial_data) da seguinte forma:<ul><li>[Padrão] Quando "false", <Anchor target="_blank" href="/marketers/pt/docs/about-data-freshness-and-timezone-support#daily">Diariamente</Anchor></li><li>Quando "true", <Anchor target="_blank" href="/marketers/pt/docs/about-data-freshness-and-timezone-support#continuous-aka-realtime">Contínuo (tempo real)</Anchor></li><li>As métricas de custo e desinstalação são atualizadas diariamente em todas as instâncias</li></ul> |
| Dados históricos | Cohorts diárias: 2 anos |
| Acesso do usuário à conta | O token de autorização está disponível no dashboard para administradores. |
| Receita de anúncios | Para eventos af\_ad\_revenue, a métrica de usuários únicos não está disponível quando o tipo de agregação é:<ul><li>Cumulativo.</li><li>"No dia", para datas entre 5 de outubro de 2022 e 16 de fevereiro de 2023.</li></ul> |
| Agrupamentos semanais e mensais | Os agrupamentos de dimensões semanais e mensais não estão disponíveis com a Cohort API. Use o dashboard Cohort. |
| Período da Cohort API | <ul><li>O período de conversão é definido como 0 (Hora 0 ou Dia 0). O próximo período após a conversão é definido como 1 (Hora 1 ou Dia 1) e assim por diante.</li><li>Na AppsFlyer, um período de cohort não leva em consideração o timestamp de data/hora específico da instalação. Em vez disso, as horas da cohort são arredondadas para a hora mais próxima e os dias da cohort se baseiam no dia do calendário. Isso pode causar discrepâncias na comparação entre os dados de cohort da AppsFlyer e os dados de cohort de outras ad networks, onde todos os períodos de cohort são determinados pelo timestamp de data/hora de instalação específico (ou seja, uma hora equivale a 60 minutos após o timestamp de data/hora da instalação e um dia é o período de 24 horas após a instalação depois do timestamp de data/hora da instalação).</li></ul> |
| Datas | <ul><li>Datas ou intervalos de datas referem-se às datas de lifetime value (<Anchor target="_blank" href="/marketers/pt/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTV</Anchor>) ou seja, a data na qual o usuário foi atribuído (converteu) e não a data da atividade em si.</li><li>Data mais antiga disponível: 730 a 5 dias antes da data atual. (ou seja, 2 anos).</li><li>Intervalo máximo de consulta: 60 dias</li></ul> |
| Reinstalações | <ul><li>Se os eventos após reinstalação forem considerados orgânicos não atribuídos:<ul><li>Estão incluídos apenas a partir de 26 de maio de 2024. <Anchor target="_blank" href="/marketers/pt/docs/bulletin-cohort-data-includes-unattributed-sessions-and-events">Saiba mais</Anchor></li><li>O tempo de instalação baseia-se no campo <Anchor target="_blank" href="/marketers/pt/docs/raw-data-field-dictionary#device-info::dfd9504e">device\_download\_time</Anchor>.</li><li>Não são contabilizados para medições de usuários únicos e de retenção.</li></ul></li><li>Se os eventos após reinstalação forem atribuídos à primeira instalação, são sempre incluídos. <Anchor target="_blank" href="/marketers/pt/docs/unique-users">Saiba mais</Anchor></li></ul> |
| Cohort API para parceiros | O acesso à Cohort API por parceiros foi desativado em 15 de setembro de 2024. Recomendamos que os parceiros <Anchor target="_blank" href="/partners/pt/docs/data-locker-reports-for-api-partners">ativem o Data Locker</Anchor> para garantir o acesso contínuo aos dados dos clientes. |

</Accordion>

<div data-zendesk-anchors="cohort-reporting-api=api-de-coorte 01H7WFZR41YAQX4MFPBMJD1MBP=api-de-coorte 01H7WFZR42H3CA0CSB4E3XED3H=filtering-and-grouping-parameters 01H7WFZR42XV4JY46GY11KT3CF=selecting-and-formatting-kpis presentation-of-kpi-functions=formatando-fun%C3%A7%C3%B5es-de-kpi 01H7WFZR43HFF65TSWG1AN0JTB=formatando-fun%C3%A7%C3%B5es-de-kpi 01H7WFZR43BJ8E6KVHSGV4CDDP=list-of-group-by-and-filter-by-dimensions additional-information=informa%C3%A7%C3%B5es-adicionais h_01HMY09W324E54VPZWPJVS2KB8=informa%C3%A7%C3%B5es-adicionais 01H7WFZR440NTXWWQ2T4P2ANWK=using-period-filters 01H7WFZR44RCXA56CXSCEZ0KXH=exemplo-de-filtro-de-per%C3%ADodo 01H7WFZR45VC96KYW1W9A8PBFT=traits-and-limitations" />
