---
title: Master API–métricas de aquisição de usuários via API
metadata:
  keywords:
    - Master API
    - Customizable
    - Aggregated Data
    - Advertisers
    - Developers
    - Premium
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2016-09-27T15:10:38Z'
  edited_at: '2026-08-19T00:02:55Z'
  id: 213223166
  locale: pt
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/pt/articles/213223166
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Visão geral:** receba KPIs selecionados de LTV, atividade, retenção, cohort e performance de campanha do Protect360 por API, em formato CSV ou JSON. Selecione um ou mais aplicativos.

<div id="master-apiuser-acquisition-metrics-via-api" />

## Master API – métricas de aquisição de usuários via API

Master API:

* Permite que você receba KPIs selecionados de LTV, atividade, retenção, cohort e performance de campanha do Protect360. Os KPIs disponíveis são KPIs equivalentes aos encontrados nos dashboards de Visão Geral, Atividade, Retenção, Cohort e Protect360.
* Os cálculos são realizados diariamente. Os dados atualizados ficam disponíveis dentro de 24 a 48 horas, dependendo do fuso horário específico do seu aplicativo.
* É a infraestrutura que comporta a <Anchor target="_blank" href="/marketers/pt/docs/pivot-table-user-metrics">pivot table</Anchor> da AppsFlyer.

Para usar a Master API, você precisa definir os dados que deseja visualizar (semelhante à implementação da <Anchor target="_blank" href="/marketers/pt/docs/pull-api-aggregate-data">Pull API</Anchor>). O resultado é um arquivo CSV ou JSON.

**Para usar a Master API**:

1. ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) Obtenha o <Anchor target="_blank" href="/marketers/pt/docs/managing-appsflyer-tokens">token da API</Anchor>. Um administrador precisa solicitar o token.
2. Forneça ao seu desenvolvedor o token da API que será usado no header de autenticação.
3. Forneça aos seus desenvolvedores os parâmetros que devem ser inseridos quando eles fizerem a chamada de API, conforme descrito nas seções a seguir. Os parâmetros determinam o foco do relatório e a maneira como ele é organizado, além de fornecerem um cronograma de relatórios.
4. Diga ao seu desenvolvedor para seguir <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-9">as instruções da Master API</Anchor> no developer hub.
5.
   <div id="api-parameters" />

   <Accordion title="Parâmetros da API">

   | Parâmetro | Valor | Obrigatório |
   | --- | --- | --- |
   | ativado | * Identificador do aplicativo (app ID), conforme encontrado na AppsFlyer.<br />* Insira o app ID exatamente conforme encontrado na AppsFlyer<br />* Coloque o prefixo **id** em apps do iOS<br />* Use **todos os app IDs** para consultar todos os seus aplicativos | Sim |
   | início | Limite inferior do período de atribuição de LTV.<br /><br />* Formato: string aaaa-mm-dd<br />* Exemplo: `from: 2020-01-02` | Sim |
   | to (até) | Limite superior do período de atribuição de LTV<br /><br />* Número de dias no intervalo: 1 a 31 dias<br />* Para um único dia: os valores `from` e `to` são idênticos.<br />* Formato: aaaa-mm-dd<br />* Exemplo: `from: 2021-01-01, to: 2021-01-31` são 31 dias. | Sim |
   | [Agrupamentos](/docs/master-api-user-acquisition-metrics-via-api#groupings) | Agrupar por parâmetros, separados por vírgula. Consulte a tabela Agrupamentos para ver a lista disponível <br /><br />Exemplo: `groupings=pid,geo` | Sim |
   | [KPIs](/docs/master-api-user-acquisition-metrics-via-api#kpis) | Lista de KPIs que devem ser incluídos, separados por vírgula. Para acessar a lista de KPIs, veja a tabela abaixo.<br /><br />Exemplo: `kpis=installs,clicks, impressions,sessions,retention_day_7` | Sim |
   | [Filtros](/docs/master-api-user-acquisition-metrics-via-api#filters-optional) | Os dados podem ser filtrados usando uma ou mais opções de filtro. | Não |
   | [Moeda](/docs/master-api-user-acquisition-metrics-via-api#localization) | Para retornar dados usando a moeda específica do aplicativo, defina currency=preferred | Não |
   | [Fuso horário](/docs/master-api-user-acquisition-metrics-via-api#localization) | Para retornar dados usando o fuso horário específico do aplicativo, defina timezone=preferred.  Veja [as regras de localização](/docs/master-api-user-acquisition-metrics-via-api#localization) | Não |
   | Formato | Por padrão, os dados de resposta são recebidos no formato de arquivo CSV. Se preferir obter os dados no formato JSON, selecione `format=json`. | Não |

   </Accordion>

   <div id="groupings" />

   <Accordion title="Agrupamentos">

   As dimensões abaixo são usadas para a coleta de dados, que são agrupados para uma análise mais rápida e precisa das informações recebidas. Você pode acessar as descrições dos campos <Anchor target="_blank" href="/marketers/pt/docs/raw-data-field-dictionary">aqui</Anchor>.

   <table><thead><tr><th>Agrupar por<br/>Nome da API</th><th>Agrupar por nome de exibição</th><th>KPIs de LTV</th><th>KPIs de retenção</th><th>KPIs de atividade</th><th>Os alertas do Protect360 são atualizados no horário UTC diário.</th><th>Coorte</th></tr></thead><tbody><tr><td>ativado</td><td>ID da aplicação</td><td>Sim</td><td>Sim</td><td>Sim</td><td>Sim</td><td>Sim</td></tr><tr><td>pid</td><td>Canal de mídia</td><td>Sim</td><td>Sim</td><td>Sim</td><td>Sim</td><td>Sim</td></tr><tr><td>af_prt</td><td>Agência</td><td>Sim</td><td>Sim</td><td>Sim</td><td>Sim</td><td>Não</td></tr><tr><td>C</td><td>Campanha</td><td>Sim</td><td>Sim</td><td>Sim</td><td>Sim</td><td>Sim</td></tr><tr><td>af_adset</td><td>Conjunto de anúncios</td><td>Sim</td><td>Sim</td><td>Sim</td><td>Não</td><td>Não</td></tr><tr><td>af_ad</td><td>Anúncio</td><td>Sim</td><td>Sim</td><td>Sim</td><td>Não</td><td>Não</td></tr><tr><td>af_canal</td><td>Canal</td><td>Sim</td><td>Sim</td><td>Sim</td><td>Sim</td><td>Não</td></tr><tr><td>af_siteid</td><td>ID do editor</td><td>Sim</td><td>Sim</td><td>Sim</td><td>Sim</td><td>Sim</td></tr><tr><td>af_keywords</td><td>Palavras-chave</td><td>Sim</td><td>Sim</td><td>Sim</td><td>Não</td><td>Não</td></tr><tr><td>is_primary</td><td>É atribuição primária</td><td>Sim</td><td>Não</td><td>Sim</td><td>Sim</td><td>Não</td></tr><tr><td>af_c_id</td><td>ID da campanha</td><td>Sim</td><td>Não</td><td>Sim</td><td>Sim</td><td>Não</td></tr><tr><td>af_adset_id</td><td>Adset ID</td><td>Sim</td><td>Não</td><td>Sim</td><td>Não</td><td>Não</td></tr><tr><td>af_ad_id</td><td>ID do anúncio</td><td>Sim</td><td>Não</td><td>Sim</td><td>Não</td><td>Não</td></tr><tr><td>install_time</td><td>Data/hora da instalação</td><td>Sim</td><td>Sim</td><td>Sim\*</td><td>Sim</td><td>Sim</td></tr><tr><td>tipo_de_toque_atribuído</td><td>Tipo de toque</td><td>Sim</td><td>Sim</td><td>Sim</td><td>Sim</td><td>Não</td></tr><tr><td>geo</td><td>Geolocalização</td><td>Sim</td><td>Sim</td><td>Sim</td><td>Sim</td><td>Sim</td></tr><tr><td colspan="7">\* No contexto dos KPIs de atividade, considere o tempo de instalação como o tempo do evento. </td></tr></tbody></table>

   </Accordion>

   <div id="kpis" />

   <Accordion title="KPIs">

   KPIs são as métricas usadas para obter insights sobre o comportamento do seu aplicativo. Os KPIs são agrupados por tipo nas abas a seguir.

   <div id="ltv" />

   <Accordion title="Dados de LTV: 5 anos">

   Lifetime value - eventos agregados segmentados por data de instalação até hoje

   | Nome do KPI na API | Descrição |
   | --- | --- |
   | impressions | Número de impressões dentro do período selecionado |
   | clicks | Número de cliques dentro do período selecionado |
   | installs | Número de instalações dentro do período selecionado |
   | cr | Taxa de conversão |
   | sessions | Número de sessões criadas por usuários que instalaram o app durante o período selecionado |
   | loyal\_users | Número de usuários fidelizados que instalaram o app durante o período selecionado |
   | loyal\_users\_rate | Usuários fidelizados/instalações |
   | cost | Custo total no período selecionado. [Ver limitações](/docs/master-api-user-acquisition-metrics-via-api#limitations). |
   | revenue | Receita vitalícia gerada por usuários que instalaram o app durante o período selecionado |
   | roi | Retorno do investimento (ROI) durante um determinado período de tempo |
   | arpu\_ltv | Receita média por usuário, para usuários que instalaram o app durante o período selecionado |
   | average\_ecpi | Custo efetivo por instalação (eCPI) durante um determinado período. Disponível somente se o custo e as instalações estiverem incluídos na chamada. |
   | uninstalls | Usuários que desinstalaram o app, que inicialmente o instalaram durante o período selecionado |
   | uninstalls\_rate | Taxa de desinstalação |
   | event\_counter\_[event\_name] | Número de ocorrências de eventos |
   | unique\_users\_[event\_name] | Número de usuários únicos que realizaram o evento |
   | sales\_in\_usd\_[event\_name] | Receita relatada como parte dos eventos registrados |

   </Accordion>

   <div id="retention" />

   <Accordion title="Retenção">

   A retenção é uma métrica de quantos usuários existentes estão ativos no seu aplicativo.

   **Observação:**

   * O número máximo de dias de retenção é 30 dias após a instalação, sendo o dia 0 o dia da instalação. Isso significa que o valor [x] não pode exceder 30.
   * Se você solicitar "retention\_day\_1", antes que os dados desse dia estejam disponíveis, a métrica retornada estará relacionada aos usuários que fizeram a instalação no dia anterior. Por exemplo, em 2 de janeiro, você solicita "retention\_day\_1" para usuários que fizeram a instalação em 1 de janeiro. Como a métrica ainda não está disponível, a métrica retornada está relacionada aos usuários que fizeram a instalação em 31 de dezembro.

   | KPI | Descrição |
   | --- | --- |
   | retention\_day\_[x] | Número de usuários retidos no dia X |
   | retention\_rate\_day\_[x] | Taxa de usuários retidos no dia X do total de usuários que instalaram o app |

   </Accordion>

   <div id="activity" />

   <Accordion title="ativado">

   Atividade no aplicativo durante o período selecionado Atividade no aplicativo durante o período selecionado **Observação**: os KPIs de atividade incluem dados unificados (UA e retargeting juntos).

   | KPI | Descrição |
   | --- | --- |
   | activity\_average\_dau | Média de usuários ativos diários (DAU) durante o período selecionado |
   | activity\_average\_mau | Média de usuários ativos mensais durante o período selecionado (os dados de MAU em determinado dia representam os usuários ativos nos últimos 30 dias) |
   | activity\_average\_dau\_mau\_rate | Taxa média de DAU/MAU |
   | activity\_average\_arpdau | Receita média por usuário diário ativo - a receita média de um determinado dia, obtida de cada usuário |
   | activity\_sessions | Número de sessões realizadas durante o período selecionado |
   | activity\_revenue | Receita relatada durante o período selecionado |
   | activity\_event\_counter\_[event\_name] | Número de eventos gerados pelos usuários durante o período selecionado |
   | activity\_sales\_in\_usd\_[event\_name] | Receita relatada como parte dos eventos relatados durante o período selecionado |
   | activity\_average\_unique\_users\_[event\_name] | Média de usuários únicos que realizaram determinado evento durante o período selecionado |

   </Accordion>

   <div id="cohort" />

   <Accordion title="Coorte">

   Os cohorts da AppsFlyer permitem que os anunciantes visualizem a comparem diferentes métricas para vários cohorts em diferentes períodos de tempo.

   **Observação:**

   * **Erros de arredondamento:** os KPIs de cohort por usuário são calculados usando quatro casas decimais. Isso significa que, se o valor calculado por usuário for &lt; 0,0001, isso será mostrado como 0. Por exemplo, o número de usuários é 100.000 e a receita total é de US$ 9. A receita por usuário é 9/100000=0,00009. Como 0,00009&lt;0,0001, o valor mostrado será 0.
   * **Dias de cohort**: o número máximo de dias de cohort é 90 dias após a instalação, em que o dia 0 é o dia da instalação. O valor do dia da cohort [x] deve estar no intervalo de 1 a 90.  **Observação**: cohort\_day\_0 não é compatível com a Master API, embora seja compatível com o dashboard de Cohort.
   * **Master API vs. Cohort API e <Anchor target="_blank" href="/marketers/pt/docs/cohort-and-retention-dashboard">dashboard de Cohort:</Anchor>** os resultados podem diferir por conta das diferenças no tratamento de reinstalações e problemas de sincronização.

   **Sessões**

   | KPI | Descrição |
   | --- | --- |
   | cohort\_day\_[x]\_total\_sessions\_per\_user | Cohort dia X - sessões cumulativas por usuário até o dia x (incluindo o dia x) |
   | cohort\_day\_[x]\_sessions\_per\_user | Cohort dia X - sessões no dia x realizadas somente pelo cohort em questão |
   | cohort\_[x]\_days\_total\_sessions\_per\_user | Substitui a especificação de KPIs Cohort\_day\_1\_total\_sessions\_per\_user por Cohort\_day\_x\_total\_sessions\_per\_user na URL.<br /><br />Por exemplo: "cohort\_3\_days\_total\_sessions\_per\_user" na URL produz 3 colunas de relatório:  <br />Cohort\_day\_1\_total\_sessions\_per\_user+ Cohort\_day\_2\_total\_sessions\_per\_user+Cohort\_day\_3\_total\_sessions\_per\_user |

   **Resultados**

   | KPI | Descrição |
   | --- | --- |
   | cohort\_day\_[x]\_total\_revenue\_per\_user | Cohort dia X - receita cumulativa por usuário até o dia x (incluindo o dia x) |
   | cohort\_day\_[x]\_revenue\_per\_user | Cohort dia X - ARPU recebido de um determinado cohort no dia x |
   | cohort\_[x]\_days\_total\_revenue\_per\_user | Substitui a especificação de KPIs "Cohort\_day\_1\_total\_revenue\_per\_user" por "Cohort\_day\_x\_total\_revenue\_per\_user".<br /><br />Por exemplo: "cohort\_3\_days\_total\_revenue\_per\_user" na URL produz 3 colunas de relatório:  <br />Cohort\_day\_1\_total\_revenue\_per\_user+ Cohort\_day\_2\_total\_revenue\_per\_user+Cohort\_day\_3\_total\_revenue\_per\_user |
   | cohort\_day\_[x]\_total\_event\_[eventname]\_revenue\_per\_user | Dia do cohort x receita acumulada por usuário de acordo com um evento in-app específico |
   | cohort\_day\_[x]\_event\_[eventname]\_revenue\_per\_user | Dia do cohort x receita por usuário de acordo com evento in-app específico |

   **Eventos**

   | KPI | Descrição |
   | --- | --- |
   | cohort\_day\_[x]\_total\_event\_[eventname]\_per\_user | Cohort dia X - eventos cumulativos por usuário até o dia x (incluindo o dia x) |
   | cohort\_day\_[x]\_event\_[eventname]\_per\_user | Cohort dia X - eventos recebidos de um determinado cohort no dia x |
   | cohort\_[x]\_days\_total\_event\_[eventname]\_per\_user | Substitui a especificação de eventos de KPIs por "Cohort\_day\_x\_total\_events\_per\_user".<br /><br />Por exemplo: "cohort\_3\_days\_total\_events\_per\_user" na URL produz 3 colunas de relatório:  <br />Cohort\_day\_1\_total\_events\_per\_user+ Cohort\_day\_2\_total\_events\_per\_user+Cohort\_day\_3\_total\_events\_per\_user |

   </Accordion>

   <div id="protect360" />

   <Accordion title="Os alertas do Protect360 são atualizados no horário UTC diário.">

   **KPIs do Protect360**

   | Descrição | KPI |
   | --- | --- |
   | **Instalações** |  |
   | Total | protect360\_total\_installs |
   | Bloqueadas | blocked\_installs |
   | Bloqueadas (%) | blocked\_installs\_rate |
   | Pós-atribuição | instalações\_pós\_atribuição |
   | Pós-atribuição (%) | taxa\_de\_instalações\_pós\_atribuição |
   | Total de instalações fraudulentas | total\_de\_instalações\_fraudulentas |
   | Instalações fraudulentas (%) | taxa\_de\_instalações\_fraudulentas |
   | **Instalações falsas** |  |
   | Bloqueio em tempo real | instalações\_falsas\_em\_tempo\_real |
   | Fraude pós-atribuição | instalações\_falsas\_pós\_atribuição |
   | **Hijacking de instalações** |  |
   | Bloqueio em tempo real | instalações\_sequestradas\_em\_tempo\_real |
   | Fraude pós-atribuição | instalações\_pós\_atribuição\_sequestradas |
   | **Regras de validação** |  |
   | Instalações bloqueadas | instalações\_bloqueadas\_por\_regras\_de\_validação |
   | Atribuição bloqueada | atribuição\_bloqueada\_por\_regras\_de\_validação |
   | **Detalhes do bloqueio de instalações falsas** |  |
   | Lista de exclusão de site IDs bloqueados | blocked\_installs\_siteid\_blacklist |
   | Lista de exclusão de site IDs pós-atribuição | instalações\_pós\_atribuição\_blacklist\_de\_siteid |
   | Bots bloqueados | blocked\_installs\_bots |
   | Bots pós-atribuição | instalações\_pós\_atribuição\_bots |
   | Anomalias comportamentais bloqueadas | instalações\_bloqueadas\_anomalias\_comportamentais |
   | Anomalias comportamentais pós-atribuição | instalações\_pós\_atribuição\_anomalias\_comportamentais |
   | Validação de instalações bloqueadas | instalações\_bloqueadas\_validação\_de\_instalação |
   | **Detalhes do bloqueio de hijackings de instalação** |  |
   | Hijacking de instalações bloqueados | instalações\_bloqueadas\_sequestro\_de\_instalação |
   | Hijacking de instalação pós-atribuição | pós-atribuição\_instalações\_sequestro\_de\_instalações |
   | Anomalias de CTIT bloqueadas | blocked\_installs\_ctit\_anomalies |
   | Anomalias de CTIT pós-atribuição | pós-atribuição\_instalações\_anomalias\_de\_ctit |
   | Flooding de cliques bloqueados | blocked\_installs\_click\_flood |
   | Flooding de cliques pós-atribuição | pós-atribuição\_instalações\_inundação\_de\_cliques |
   | **Cliques** |  |
   | Total | protect360\_total\_clicks |
   | Bloqueadas | blocked\_clicks |
   | % | blocked\_clicks\_rate |
   | **Eventos in-app** |  |
   | Total | protect360\_total\_in\_apps |
   | Bloqueadas | blocked\_in-app-events |
   | % | blocked\_in-app-events\_rate |
   | Indicadores de device farm - novos dispositivos |  |
   | Instalações | fraude\_de\_instalação\_novos\_dispositivos\_total |
   | Instalações (%) | install\_fraud\_new\_devices\_total\_installs\_rate |
   | Usuários fidelizados (%) | install\_fraud\_new\_devices\_total\_loyal\_user\_rate |
   | **Indicadores de device farm - dispositivos LAT** |  |
   | Instalações | fraude\_de\_instalação\_dispositivos\_lat\_total |
   | Instalações (%) | fraude\_de\_instalação\_dispositivos\_lat\_total\_taxa\_de\_instalações |
   | Usuários fidelizados (%) | fraude\_de\_instalação\_dispositivos\_lat\_total\_taxa\_de\_usuários\_fiéis |
   | **Indicadores de flooding de cliques** |  |
   | Taxa de conversão | conversion\_rate |
   | **Indicadores de flooding de cliques - CTIT** |  |
   | Mais de 60 minutos | inundação\_de\_cliques\_mais\_de\_1\_hora\_taxa |
   | Mais de 5 horas | inundação\_de\_cliques\_mais\_de\_5\_horas\_taxa |

   </Accordion>

   <div id="calculated-kpis" />

   #### KPIs calculados

   Além dos KPIs descritos anteriormente, você pode adicionar KPIs calculados aos seus relatórios da Master API. Isso permite que você inclua seus próprios relatórios calculados em seus relatórios da Master API.

   Você pode inserir qualquer número de objetos de KPI integrados nas fórmulas de KPI calculadas. Cada cálculo de objeto de KPI inclui uma chave e um valor. A chave é o nome que você dá ao KPI e o valor é a fórmula do KPI.

   Operadores aritméticos padrão podem ser usados: adição (+) codificada como %2b, subtração (-), multiplicação (*), divisão (/) codificada como %2f.

   As chaves do campo de KPI calculado **devem** começar com "calculated\_kpi\_", seguido por qualquer sequência (string) válida, como "calculated\_kpi\_purchaserate".

   <div id="example" />

   > 📄 **Exemplo**
   >
   > **Retenção combinada dos primeiros três dias**
   >
   > ```http
   > kpis=installs,loyal_users_rate&calculated_kpi_3days_retention=
   > retention_day_1%2Bretention_day_2%2Bretention_day_3
   > ```
   >
   > **Receita média por impressão**
   >
   > ```http
   > kpis=installs&calculated_kpi_rev_per_impression=revenue%2Fimpression
   > ```
   >
   > **ROI do D7 da cohort**
   >
   > ```http
   > kpis=installs,roi,arpu_ltv,cost,revenue&calculated_kpi_roi_day_7=
   > (cohort_day_7_total_revenue_per_user-average_ecpi)%2Faverage_ecpi
   > ```

   </Accordion>

   <div id="filters-optional" />

   <Accordion title="Filtros (opcional)">

   | Parâmetro | Descrição | Exemplo | Obrigatório? |
   | --- | --- | --- | --- |
   | pid | * Usado para selecionar as linhas nas quais os canais de mídia especificados são exibidos.<br />* É possível realizar seleção múltipla separada por vírgula. | pid=organic,applovin\_int | Não |
   | C | * Usado para filtrar por nome de campanha.<br />* É possível realizar seleção múltipla separada por vírgula. | c=my\_sample\_campaign | Não |
   | af\_prt | * Usado para filtrar por nome de agência.<br />* É possível realizar seleção múltipla separada por vírgula. | af\_prt=moburst | Não |
   | af\_canal | * Usado para filtrar por nome de canal.<br />* É possível realizar seleção múltipla separada por vírgula. | af\_channel=Instagram | Não |
   | af\_siteid | * Usado para filtrar por publisher ID.<br />* É possível realizar seleção múltipla separada por vírgula. | af\_siteid=12345678 | Não |
   | geo | * Usado para filtrar por país.<br />* É possível realizar seleção múltipla separada por vírgula. | geo=US,DE | Não |

   </Accordion>

   <div id="localization" />

   <Accordion title="Localização">

   A moeda local e o fuso horário específico do aplicativo são definidos na <Anchor target="_blank" href="/marketers/pt/docs/app-settings">página de configurações do aplicativo</Anchor>. Os dados da Master API podem extrair dados usando a moeda e o fuso horário padrão do sistema ou usando o fuso horário e a moeda específicos do aplicativo.

   O seguinte se aplica:

   * O uso do fuso horário/moeda específica do aplicativo só será possível se todos os aplicativos tiverem o mesmo fuso horário/moeda. Caso contrário, serão usados UTC e USD. O fuso horário e a moeda são separados. Isso significa que se a moeda de todos os aplicativos for a mesma, mas os fusos horários não, você poderá usar a moeda específica do aplicativo, mas não o fuso horário específico do aplicativo.
   * Se o fuso horário preferencial tiver sido alterado no dashboard dentro do intervalo de tempo solicitado, o relatório gerado conterá valores a partir da alteração de fuso horário mais recente.

   Use os parâmetros a seguir para selecionar a configuração específica do aplicativo. **Observação**: se você não usar os parâmetros preferenciais, obterá as configurações padrão, que são USD para moeda e UTC para fuso horário.

   | Parâmetro | Descrição | Exemplo | Obrigatório? |
   | --- | --- | --- | --- |
   | símbolos monetários | Valores monetários na moeda específica do aplicativo | currency=preferencial | Não |
   | Fuso horário | O fuso horário usado está de acordo com o fuso horário específico do aplicativo | timezone=preferred | Não |

   </Accordion>

<div id="additional-information" />

## Informações adicionais

<div id="limitations" />

<Accordion title="Características e limitações">

| Caraterística | Observações |
| --- | --- |
| Dados de custo | <ul><li>Disponibilidade de diferentes dimensões de custo, o que significa que o conjunto de anúncios, o anúncio, a geolocalização, o canal e o ID do site <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">dependem da ad network</Anchor>.</li><li>Para obter o eCPI: se os dados de custo estiverem disponíveis, inclua as instalações e o custo na chamada.</li><li>Em geral, todos os canais, incluindo mídia própria, que usam links da AppsFlyer e possuem o parâmetro de custo nos links, são totalmente compatíveis com os dados de custo, independentemente das dimensões solicitadas. Redes de autorrelato, que possuem uma API própria, geralmente são compatíveis com dados de custos, mas com apenas algumas das dimensões disponíveis. Por exemplo, <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-faq#what-are-the-limitations-of-facebook-cost-data-in-master-api">Meta Ads</Anchor> não oferece suporte ao agrupamento por geolocalização e canal na mesma chamada. No entanto, é possível agrupá-los separadamente.</li><li>Campanhas que têm dados de custo, mas não têm dados de instalações no passado recente (aprox. 7 dias), não estão disponíveis via Master API.</li></ul> |
| Agrupamentos | Agrupamentos específicos estão disponíveis apenas para KPIs de LTV, Atividade ou KPIs de Retenção. A API retorna N/A quando os dados de um KPI específico não estão disponíveis. Por exemplo, a solicitação "detention\_rate\_day\_7" agrupada por "af\_channel" retorna N/A. |
| Dados | Para dados de coorte, se uma agência estiver envolvida na atribuição, o canal de mídia retornado será o nome da agência |
| Máximo de linhas por relatório | 200 mil |
| Nomes de eventos | A API Master atualmente não oferece suporte a nomes de eventos que incluam uma barra `/` . Para superar essa limitação, evite o usuário de `/` em nomes de eventos. |
| Tempo de processamento | Selecionar mais de um aplicativo aumenta o tempo de processamento e a resposta pode demorar mais. |
| Date range | A granularidade do prazo é diária. |
| Agências | Master API não disponível |
| Redes de anúncios | Master API não disponível |
| Dados históricos | <ul><li>Dados de LTV: 25 meses (2 anos + 1 mês)</li><li>Dados de coorte (coorte diária): 2 anos</li><li>Dados da atividade: 3 anos</li></ul> |
| Redirecionamento | <ul><li>Não compatível</li><li>Exceção: os KPIs de atividade para tráfego após 1 de fevereiro de 2025 incluem dados unificados (UA e retargeting juntos).</li></ul> |

</Accordion>

<div data-zendesk-anchors="master-api%E2%80%94user-acquisition-metrics-via-api=master-api--m%C3%A9tricas-de-aquisi%C3%A7%C3%A3o-de-usu%C3%A1rios-via-api h_01JJVMXKACJ2V4YZFGYXVB8FQF=master-api--m%C3%A9tricas-de-aquisi%C3%A7%C3%A3o-de-usu%C3%A1rios-via-api h_01JJVMXKACZDXPQG4271HFYWCE=api-parameters h_01JJVMXKAEXMKQQRT0RT6N8P74=groupings h_01JJVMXKAEHM0871GBQHZENRXA=kpis h_01JK2ZEH32Y92Y553540XDYZFA=ltv h_01JK2ZEH32A08EEDZEWFSX3ZFS=retention h_01JK2ZEH3219694E4PFPZ8ZXZF=activity h_01JK2ZEH32NCWZWKTDS0J6DFS2=cohort h_01JK2ZEH32Q7B6RCQYXNHM8KGK=protect360 calculated-kpis=kpis-calculados h_01JJVMXKAFW1TEE35GK9B20TRP=kpis-calculados h_01JJVMXKAFZDPNXKAZCBQ27DBD=exemplo h_01JJVMXKAFWA4D47MH7VSXKN14=filters-optional h_01JJVMXKAFSBXJ9EJJ16BF8H7Q=localization additional-information=informa%C3%A7%C3%B5es-adicionais h_01JJVMXKAFFW2G3N7188DHYCB8=informa%C3%A7%C3%B5es-adicionais h_01JJVMXKAF25YX092NE9DV9862=limitations" />
