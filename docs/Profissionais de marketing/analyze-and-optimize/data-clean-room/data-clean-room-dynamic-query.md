---
title: Data Clean Room—Consulta Dinâmica
metadata:
  keywords:
    - Premium
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-inbar-agassi
    - Marketers
    - Data Clean Room
  created_at: '2023-09-20T10:05:34Z'
  edited_at: '2026-08-19T00:05:43Z'
  id: 18704719821329
  locale: pt
  section: Data Clean Room
  section_id: 4591191779217
  url: https://support.appsflyer.com/hc/pt/articles/18704719821329
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Em resumo:** Execute consultas personalizadas do DCR em tempo real nos seus dados de atribuição no sistema da AppsFlyer, nas suas fontes personalizadas ou em uma combinação de ambos. Visualize os resultados das suas consultas ou baixe os resultados completos.

<div id="overview" />

## Escritórios

<div id="why-use-dynamic-query" />

### Por que usar o Dynamic Query?

O Dynamic Query permite executar consultas ad hoc e personalizadas nos seus dados do DCR em tempo real para responder às suas perguntas específicas de marketing com rapidez e eficiência.

* Incorporando o poder e a flexibilidade do SQL, ele permite realizar pesquisas avançadas e cálculos complexos que não podem ser feitos de nenhuma outra forma. Com o Dynamic Query, você pode aplicar sua lógica de negócios a dados que, de outra forma, seriam inacessíveis.
* Além disso, o Dynamic Query possibilita obter respostas eficientes para perguntas pontuais ou ocasionais sem a necessidade de configurar relatórios. (É claro que os <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-working-with-reports">relatórios tradicionais do DCR</Anchor> ainda são a solução certa para recuperação e ingestão contínuas de dados.)

O Dynamic Query está disponível para **todos os clientes do DCR**, permitindo que você execute consultas e visualize os resultados sem usar créditos do seu pacote de DCR. Os créditos só serão cobrados se você decidir fazer o download dos resultados completos. Dessa forma, você pode ter certeza de que configurou suas consultas corretamente e de que obterá as respostas de que precisa antes de gerar qualquer cobrança.

<div id="query-language-and-dialect" />

### Linguagem e dialeto de consulta

O Dynamic Query usa SQL **(dialeto Spark SQL)** e oferece suporte a:

* <Anchor target="_blank" href="https://spark.apache.org/docs/3.2.1/sql-ref-syntax-qry-select.html">Instruções SELECT</Anchor>
* <Anchor target="_blank" href="https://spark.apache.org/docs/3.2.1/api/sql/">Funções SQL padrão</Anchor>
* Funções definidas pelo usuário (UDFs), mediante solicitação do cliente
  * Se você precisar de uma função SQL não padrão, entre em contato com seu CSM ou com [hello@appsflyer.com](mailto:hello@appsflyer.com,) e faremos todo o possível para adicioná-la.

<div id="available-sources" />

### Fontes disponíveis

O Dynamic Query permite executar consultas personalizadas nas seguintes fontes de dados:

* Seus dados de atribuição no sistema da AppsFlyer
  * [Saiba mais](#querying-attribution-data) sobre as tabelas de dados de atribuição e como consultá-las
* <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-working-with-sources">Fontes personalizadas</Anchor> que você configurou no DCR

Você pode consultar essas fontes individualmente ou [combinar 2 ou mais](#combining-sources) usando instruções **JOIN** ou **UNION**. Essa flexibilidade torna o Dynamic Query útil em vários cenários, por exemplo:

* Consultar apenas dados de atribuição para [obter insights entre aplicativos](#obtain-crossapp-insights), [explorar a integridade dos dados](#explore-data-integrity) ou [calcular métricas de atribuição personalizadas](#calculate-custom-attribution-metrics)
* Consultar suas fontes personalizadas em conjunto com dados de atribuição para [enriquecer seus dados](#enrich-your-custom-data-with-attribution-insights) com insights de atribuição

Com base nos tipos de fontes usados em uma consulta, [regras são aplicadas](#preservação-da-privacidade) para garantir a preservação rigorosa da privacidade do usuário.

<div id="note" />

> 📘 **Atenção**
>
> No momento, o Dynamic Query não consulta dados de atribuição nem retorna resultados da Meta (Facebook, Instagram etc.) Para consultar esses dados, configure os <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-working-with-reports">relatórios DCR</Anchor>. Para consultar esses dados, configure os <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-working-with-reports">relatórios DCR</Anchor>.

<div id="preserving-privacy" />

### Preservação da privacidade

Para garantir que o Dynamic Query mantenha conformidade rigorosa com os padrões de privacidade do DCR, os seguintes requisitos se aplicam a todas as consultas:

1. Qualquer consulta que use **dados de atribuição** deve incluir uma instrução **GROUP BY** para que os resultados sejam agregados.
2. As instruções **UNION** **não podem** ser usadas para combinar fontes personalizadas com dados de atribuição.
3. O agrupamento pelos campos a seguir **não é permitido:**
   * **Campos de dados de atribuição:**
     * appsflyer\_id
     * idfa
     * idfv
     * advertising\_id
     * android\_id
     * {"customer_user_"}  
       id
     * ip
   * **Campos de fontes personalizadas** associados a qualquer um dos campos de dados de atribuição acima.
4. As funções a seguir **não são permitidas** quando executadas em **dados de atribuição não agregados.** Elas **são permitidas** quando executadas em **dados de atribuição agregados** ou em **dados de fontes personalizadas:**
   * collect\_list
   * collect\_set
   * last
   * last\_value
   * fisrt
   * first\_value
   * máx
   * mín

Para saber mais sobre o que *deve* e o que *não deve* ser feito na criação de consultas, veja exemplos e explicações de consultas [válidas](#queries-de-amostra) e [inválidas](#consultas-inválidas).

<div id="accessing-dynamic-query" />

### Acesso ao Dynamic Query

1. Na AppsFlyer, no menu lateral, vá para **Colaborar** > **Data Clean Room.**
2. No menu superior, selecione a guia **Dynamic Query**.

<div id="reference" />

## Referência

<div id="query-reference" />

### Referência de consultas

As guias a seguir fornecem informações adicionais sobre como criar consultas no ambiente do Dynamic Query.

<div id="combining-sources" />

<Accordion title="Combinação de fontes: JOIN e UNION">

As instruções **JOIN** combinam fontes ao corresponder um campo em comum:

* Pode ser usado para combinar quaisquer fontes: tabelas de dados de atribuição e/ou fontes personalizadas
* Pode ser usado para combinar um número ilimitado de fontes
* **Normalmente usado para enriquecer dados de fontes personalizadas com dados de atribuição**

As instruções **UNION** anexam tabelas com esquema correspondente (com as mesmas colunas e tipos de dados):

* **Pode** ser usado para combinar tabelas de dados de atribuição ***ou*** fontes personalizadas; **não pode** ser usado para combinar tabelas de dados de atribuição ***com*** fontes personalizadas
* Pode ser usado para combinar um número ilimitado de fontes
* **Normalmente usado para executar consultas em** [**múltiplas tabelas de dados de atribuição**](#querying-attribution-data)

</Accordion>

<div id="querying-attribution-data" />

<Accordion title="Consulta de tabelas de dados de atribuição">

Os dados de atribuição no sistema AppsFlyer existem em 8 tabelas diferentes:

* Cada tabela inclui diferentes tipos de eventos de atribuição.
* O período para o qual os dados da consulta estão disponíveis varia de acordo com a tabela.
  * Ao construir sua consulta no console Dynamic Query, passe o cursor sobre o nome de uma tabela no painel de seleção para ver as datas exatas de disponibilidade dos dados dessa tabela.
* As tabelas em cada um dos grupos abaixo têm schema correspondente, o que significa que você pode usar instruções **UNION** para consultar facilmente várias tabelas de uma só vez.

**Grupo 1: Instalações de aplicativos e eventos de retargeting**

| Nome da tabela | A descrição | Datas de disponibilidade dos dados |
| --- | --- | --- |
| installs | Um usuário faz download, instala e abre um app mobile | 180 dias anteriores  <br />(sem incluir o dia atual) |
| re\_installs | Um usuário instala um aplicativo, depois o desinstala e reinstala durante a janela de reatribuição | 180 dias anteriores  <br />(sem incluir o dia atual) |
| re\_engagements | Um usuário inativo de um aplicativo específico interage com uma campanha de retargeting para o aplicativo e, posteriormente, o abre | 180 dias anteriores  <br />(sem incluir o dia atual) |
| re\_attribution | Um ex-usuário de um aplicativo específico (que o havia desinstalado) interage com uma campanha de retargeting para o aplicativo e, posteriormente, o reinstala | 180 dias anteriores  <br />(sem incluir o dia atual) |
| instalações\_orgânicas | Instalação não atribuída a um canal de mídia específico | 180 dias anteriores  <br />(sem incluir o dia atual) |

**Grupo 2: Eventos in-app**

| Nome da tabela | A descrição | Datas de disponibilidade dos dados |
| --- | --- | --- |
| in\_app\_events | Eventos pós-instalação configurados para mensuração no SDK do aplicativo | Dia anterior + dia atual |
| in\_app\_organic\_installs | Eventos in-app após uma instalação orgânica | Dia anterior + dia atual |

**Grupo 3: Impressões**

| Nome da tabela | A descrição | Datas de disponibilidade dos dados |
| --- | --- | --- |
| impressions | Um anúncio é visualizado por um usuário do aplicativo ou visitante do site<ul><li>Dados disponíveis apenas para ad networks não SRN</li></ul> | 5 dias anteriores + dia atual |

</Accordion>

<div id="sample-queries" />

### Queries de amostra

Estas consultas demonstram apenas algumas das possibilidades do que você pode fazer com o Dynamic Query. Você pode usá-las simplesmente para estimular suas ideias ou como ponto de partida para suas próprias consultas.

**Para usar as consultas de exemplo como base para suas consultas:**

1. Copiar e colar: copie os exemplos de SQL de sua escolha e cole-os em uma planilha na guia **Dynamic Query**.
2. Substituir parâmetros: modifique o código SQL substituindo os parâmetros pelas fontes e campos específicos que você quer consultar.
3. Executar: clique no botão **Run** para executar uma consulta e visualizar os resultados.  
   * Executar uma consulta e visualizar os resultados não consome créditos.
   * Os créditos do seu pacote DCR são consumidos apenas se você fizer o download dos resultados completos.

<div id="obtain-crossapp-insights" />

<Accordion title="Obter insights entre aplicativos">

Esta consulta recupera informações sobre os 3 aplicativos com mais reinstalações no Snapchat nos últimos 3 dias.

```sql
SELECT app_id, COUNT(*) AS reinstall_count
FROM re_installs
WHERE media_source = 'snapchat_int' AND dt BETWEEN DATE_SUB(current_date(), 3) AND current_date()
GROUP BY app_id
ORDER BY reinstall_count DESC
LIMIT 3;
```

</Accordion>

<div id="explore-data-integrity" />

<Accordion title="Explore a integridade dos dados">

Para ajudar você a avaliar a integridade de dados, esta consulta calcula a taxa de valores nulos de IDFA para os 10 canais de mídia com o maior número de instalações nos últimos 7 dias.

```sql
SELECT media_source, COUNT(*) AS total_installs, ROUND((SUM(CASE WHEN idfa IS NULL THEN 1 ELSE 0 END) / COUNT(*)) * 100, 2) AS null_idfa_rate
FROM installs
WHERE dt BETWEEN DATE_SUB(current_date(), 3) AND current_date()
GROUP BY media_source
ORDER BY total_installs DESC
LIMIT 10;
```

</Accordion>

<div id="calculate-custom-attribution-metrics" />

<Accordion title="Calcule métricas de atribuição personalizadas">

Ao calcular a média geométrica da diferença de tempo (em segundos) entre o horário de instalação e o horário do toque atribuído para cada canal de mídia e campanha, os dados resultantes fornecem insights sobre a eficiência de vários canais de mídia no que diz respeito às conversões de usuários e aos cronogramas de atribuição.

```sql
SELECT media_source,campaign,geo_mean(GREATEST(1, unix_timestamp(install_time, "yyyy-MM-dd HH:mm:ss") - unix_timestamp(attributed_touch_time, "yyyy-MM-dd HH:mm:ss.SSS")))
FROM installs
GROUP BY 1,2
```

</Accordion>

<div id="enrich-your-custom-data-with-attribution-insights" />

<Accordion title="Enriqueça seus dados personalizados com insights de atribuição">

Esta consulta usa dados de atribuição para agrupar uma pontuação da fonte personalizada C (c.score) por canal de mídia, permitindo que você use sua métrica personalizada para avaliar a performance relativa de vários canais de mídia.

```sql
SELECT media_source, sum(c.score)
FROM client_input c JOIN install i on i.appsflyer_id = c.appsflyer_id
GROUP BY media_source;
```

</Accordion>

<div id="complex-attribution-and-firstparty-data-join" />

<Accordion title="Junção complexa de atribuição e dados first-party">

Esta consulta usa um processo mais complexo de junção de dados, permitindo a geração de insights avançados. Primeiro, ela recupera e unifica dados de 2 tabelas distintas de atribuição ("install" e "installRetarget"). Em seguida, ela combina esses dados com 2 fontes personalizadas first-party para fornecer insights sobre vários tipos de conversão, incluindo uma métrica de performance personalizada agregada (score) e a idade máxima de cada tipo.

```sql
SELECT conversion_type, SUM(sum_score), MAX(max_age)
FROM (SELECT media_source, conversion_type, SUM(score) as sum_score, MAX(age) as max_age
FROM (SELECT * from install union all select * FROM installRetarget) af
JOIN client_input c on c.appsflyer_id = af.appsflyer_id
JOIN client_age ca on ca.appsflyer_id = c.appsflyer_id
GROUP BY media_source, conversion_type)
GROUP BY conversion_type
```

</Accordion>

<div id="invalid-queries" />

### Consultas inválidas

Estas consultas ilustram algumas das regras que a Dynamic Query usa para garantir compliance com os requisitos de privacidade do usuário. Use-as para entender melhor o que *deve* e o que *não deve* ser feito ao construir consultas para o DCR.

<div id="no-group-by-statement" />

<Accordion title="Sem instrução GROUP BY">

Cada uma das consultas a seguir é inválida porque usa dados de atribuição, mas não inclui uma instrução **GROUP BY**:

```sql
SELECT *
FROM install;
```

-----------------------------------------------------

```sql
SELECT media_source, appId
FROM client_input c
JOIN install af on af.appsflyer_id = c.appsflyer_id;
```

</Accordion>

<div id="grouped-by-nonpermitted-attribution-data-field" />

<Accordion title="Agrupada por campo de dados de atribuição não permitido">

A consulta a seguir é inválida porque agrupa por um campo de dados de atribuição não permitido (appsflyer\_id):

```sql
SELECT appsflyer_id, count(*)
FROM install
GROUP BY appsflyer_id
```

-----------------------------------------------------

A consulta a seguir é inválida porque agrupa por um campo de dados de atribuição não permitido (appsflyer\_id). Isso não é permitido, mesmo quando o campo está dentro de uma função:

```sql
SELECT substr(appsflyer_id, 0, 5), count(*)
FROM install
GROUP BY substr(appsflyer_id, 0, 5)
```

-----------------------------------------------------

A consulta a seguir é inválida porque agrupa por um campo de dados de atribuição não permitido (appsflyer\_id). Isso não é permitido, mesmo quando o campo está dentro de um índice:

```sql
SELECT appsflyer_id, count(*)
FROM install
GROUP BY 1
```

</Accordion>

<div id="grouped-by-nonpermitted-custom-data-field" />

<Accordion title="Agrupada por campo de fonte personalizada associado a campo de dados de atribuição não permitido">

A consulta a seguir é inválida porque agrupa por um campo de fonte personalizada (my\_id) vinculado a um campo de dados de atribuição não permitido (appsflyer\_id); portanto, a mesma restrição de agrupamento se aplica a my\_id.

```sql
SELECT my_id, count(*)
FROM installs
JOIN my_source on my_source.my_id = installs.appsflyer_id
GROUP BY my_id
```

</Accordion>

<div id="restricted-function" />

<Accordion title="Função restrita">

A consulta a seguir é **inválida** porque tenta executar a função collect\_list em dados de atribuição **não agregados**:

```sql
SELECT App_id, collect_list(appsflyer_id)
FROM install
GROUP BY app_id
```

-----------------------------------------------------

Compare com a consulta **válida** a seguir, que executa a função collect\_list em dados de atribuição **agregados**:

```sql
SELECT app_id, collect_list(campaign)
FROM (select app_id, campaign
  FROM Install
  GROUP BY 1, 2)
GROUP BY app_id
```

-----------------------------------------------------

Compare com a consulta **válida** a seguir, que executa a função collect\_list em **dados de origem personalizados:**

```sql
SELECT app_id, collect_list(c.score)
FROM client_input c
GROUP BY app_id
```

</Accordion>

<div data-zendesk-anchors="overview=escrit%C3%B3rios h_01HAS0VY179VDWWV6N5YY2578E=escrit%C3%B3rios why-use-dynamic-query=por-que-usar-o-dynamic-query h_01HF9G8TXGTAJDFZFVT8WS3QJE=por-que-usar-o-dynamic-query query-language-and-syntax=linguagem-e-dialeto-de-consulta h_01HF3KZXC2VHNG92YX25K9HX7Q=linguagem-e-dialeto-de-consulta h_01HASGQZ5ATBPQ0HF28ETAGPMJ=fontes-dispon%C3%ADveis h_01HF45KMZNF95SC0K6DE7P4K1R=aten%C3%A7%C3%A3o preserving-privacy=preserva%C3%A7%C3%A3o-da-privacidade 01HF3EJEN2KSRR56F9XF0VSPQF=preserva%C3%A7%C3%A3o-da-privacidade accessing-the-dynamic-query=acesso-ao-dynamic-query h_01J3FBVTVW2NCNESK3SYR0G9Q8=acesso-ao-dynamic-query reference=refer%C3%AAncia h_01HAS0X3NDFM136YMYSAG88JD7=refer%C3%AAncia query-reference=refer%C3%AAncia-de-consultas h_01HFKFTBD7BCVP8PT0FDNGVHXS=refer%C3%AAncia-de-consultas h_01HFM169F3W9FDZZ3A4SG7WW58=combining-sources h_01HFM169F3WECT4M32H1CVCMKS=querying-attribution-data sample-queries=queries-de-amostra h_01HF3TDC0A8N9ZXGJHY4MZE3Y6=queries-de-amostra h_01HF40PRZV7DBMYQRS6YJK2RM4=obtain-crossapp-insights h_01HF40PRZVFHY7B0R1G5S5PRTG=explore-data-integrity h_01HF40PRZVB5N2B14VEYW2CB3N=calculate-custom-attribution-metrics h_01HF40PRZVDXPZBDT25B9JK2EE=enrich-your-custom-data-with-attribution-insights h_01HF40PRZVM2HGQMX9TCK8WF7Y=complex-attribution-and-firstparty-data-join invalid-queries=consultas-inv%C3%A1lidas h_01HF3V03EFAVYR6M4WX0BHSVDK=consultas-inv%C3%A1lidas h_01HF40PRZVZWTSK4BJ6BQ1D7S0=no-group-by-statement h_01HF40PRZVY13XM4RVETNK7E6K=grouped-by-nonpermitted-attribution-data-field h_01HF40PRZVJ9G4BAXKGW5VZMJX=grouped-by-nonpermitted-custom-data-field h_01HF42A4B20727TQGPPMP20629=restricted-function" />
