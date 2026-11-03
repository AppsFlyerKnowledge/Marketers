---
title: Calcular daily e monthly active users (DAU e MAU)
metadata:
  keywords:
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2025-09-15T15:49:21Z'
  edited_at: '2026-08-18T00:02:43Z'
  id: 39071744864657
  locale: pt
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/pt/articles/39071744864657
---
> **Resumo:** saiba como calcular os usuários ativos diários e mensais para obter insights valiosos sobre as suas campanhas

## Visão geral

Daily Active Users (DAU) e Monthly Active Users (MAU) são métricas fundamentais para entender o engajamento no aplicativo e o comportamento geral de um usuário. Essas métricas fornecem insights valiosos sobre a sua base de usuários ativos, incluindo o stickiness do usuário, performance de uma campanha e tendências de crescimento ao longo do tempo.

Esse artigo explica como calcular o DAU e MAU utilizando consultas em duas tabelas de dados brutos do Data Locker, que representam a aquisição de usuários e o tráfego de retargeting: as tabelas `sessions` e `sessions_retargeting`.

> 📘 **Observação:**
>
> A partir de fevereiro de 2025, o dashboard de atividades na AppsFlyer mostrará dados unificados (UA e retargeting) por padrão. Talvez você observe um pequeno delta entre os dados brutos e os números do dashboard por conta de <Anchor target="_blank" href="/marketers/pt/docs/activity-metrics-in-my-dashboards#especificações-e-limitações">ajustes algorítmicos aprovados</Anchor>.

### Consulta de usuários exclusivos ativos

Para calcular os usuários exclusivos, use `advertising_id` como identificador primário na sua consulta. Se o `advertising_id` não estiver disponível, substitua-o por `appsflyer_id`. Esse método se aplica apenas a aplicativos configurados no <Anchor target="_blank" href="/marketers/pt/docs/measure-reinstalls#attributed-to-the-first-install">modo de primeira instalação</Anchor>.

Para aplicativos que não usam esse modo, recomendamos a aplicação de `count(distinct appsflyer_id)`.

## Calcular Daily Active Users (DAU)

Calcule o número total de usuários exclusivos por dia usando as consultas abaixo.

<div id="query-for-dau---user-acquisition-ua" />

<Accordion title="Consulta para DAU - Aquisição de usuários (UA)">

Selecione os usuários ativos após a aquisição de usuários para um dia específico.

```sql
WITH sessions_cleaned AS (
    SELECT DISTINCT
        app_id,
        COALESCE(advertising_id, appsflyer_id) AS user_id
    FROM sessions
    WHERE app_id = 'your.app.id.here'                      -- Replace with your app ID
		    AND SUBSTR(event_time, 1, 10) = 'YYYY-MM-DD'       -- Target date                 
)

SELECT COUNT(DISTINCT user_id) AS dau_ua
FROM sessions_cleaned;
```

</Accordion>

<div id="query-for-dau---retargeting" />

<Accordion title="Consulta para DAU - Retargeting">

Selecione os usuários de ativos após o retargeting para um dia específico.

```sql
WITH sessions_retargeting_cleaned AS (
    SELECT DISTINCT
        app_id,
        COALESCE(advertising_id, appsflyer_id) AS user_id
    FROM sessions_retargeting
    WHERE app_id = 'your.app.id.here'                      -- Replace with your app ID
		    AND SUBSTR(event_time, 1, 10) = 'YYYY-MM-DD'   -- Target date                 
)
SELECT COUNT(DISTINCT user_id) AS dau_retargeting
FROM sessions_retargeting_cleaned;
```

</Accordion>

<div id="query-for-dau---unified-ua-retargeting" />

<Accordion title="Consulta de DAU - Unificado (UA e retargeting)">

Selecionar usuários ativos após UA e retargeting para um dia específico.

Para visualizar todos os usuários ativos, você deve **unir**  as tabelas `sessions` e `sessions_retargeting`. Certifique-se de que os campos estão alinhados — normalmente por `app_id`, `event_time`, `advertising_id` e `appsflyer_id`. Quando necessário, padronize o esquema de modo que ambas as tabelas tenham nomes de colunas consistentes.

```sql
WITH ua_sessions AS (
    SELECT DISTINCT
        app_id,
        COALESCE(advertising_id, appsflyer_id) AS user_id
    FROM sessions
    WHERE app_id = 'your.app.id.here'                 -- Replace with your app ID
      AND SUBSTR(event_time, 1, 10) = 'YYYY-MM-DD'    -- Target date           
      AND is_primary_attribution = TRUE
),

retargeting_sessions AS (
    SELECT DISTINCT
        app_id,
        COALESCE(advertising_id, appsflyer_id) AS user_id
    FROM sessions_retargeting
    WHERE app_id = 'your.app.id.here'                  -- Same app
      AND SUBSTR(event_time, 1, 10) = 'YYYY-MM-DD'     -- Same date
),

all_sessions AS (
    SELECT * FROM ua_sessions
    UNION ALL
    SELECT * FROM retargeting_sessions
)

SELECT COUNT(DISTINCT user_id) AS dau_unified
FROM all_sessions;
```

</Accordion>

## **Calcular Monthly Active Users (MAU)**

Os dashboards da AppsFlyer apresentam o MAU de duas maneiras diferentes:

1. **Usuários ativos nos últimos 31 dias** — o número de usuários exclusivos ativos nos últimos 31 dias.
2. **MAU do mês selecionado** — número de usuários exclusivos durante um mês específico.

As consultas abaixo mostram como calcular o primeiro tipo de MAU. Para calcular o MAU de um mês específico, basta ajustar o intervalo de datas para corresponder ao mês desejado.

<div id="query-for-mau---user-acquisition-ua" />

<Accordion title="Consulta de MAU - Aquisição de usuários (UA)">

Selecione os usuários ativos após a aquisição de usuários para um mês específico.

```sql
WITH sessions_cleaned AS (
    SELECT DISTINCT
        app_id,
        COALESCE(advertising_id, appsflyer_id) AS user_id
    FROM sessions
    WHERE app_id = 'your.app.id.here'  -- Replace with your app ID
			AND DATE_DIFF('day', TRY_CAST(SUBSTR(event_time, 1, 10) AS DATE), DATE('YYYY-MM-DD')) <= 31  -- Replace with target end date 
)
SELECT COUNT(DISTINCT user_id) AS mau_ua
FROM sessions_cleaned;
```

</Accordion>

<div id="query-for-mau---retargeting" />

<Accordion title="Consulta de MAU - Retargeting">

Selecione os usuários de ativos após o retargeting para um mês específico.

```sql
WITH sessions_cleaned AS (
    SELECT DISTINCT
        app_id,
        COALESCE(advertising_id, appsflyer_id) AS user_id
    FROM sessions_retargeting
    WHERE app_id = 'your.app.id.here'  -- Replace with your app ID
			AND DATE_DIFF('day', TRY_CAST(SUBSTR(event_time, 1, 10) AS DATE), DATE('YYYY-MM-DD')) <= 31  -- Replace with target end date 
)

SELECT COUNT(DISTINCT user_id) AS mau_retargeting
FROM sessions_cleaned;
```

</Accordion>

<div id="query-for-mau---unified-ua-retargeting" />

<Accordion title="Consulta de MAU - Unificado (UA e retargeting)">

Selecionar usuários ativos após UA e retargeting para um mês específico.

Para visualizar todos os usuários ativos, você deve **unir**  as tabelas `sessions` e `sessions_retargeting`. Certifique-se de que os campos estão alinhados — normalmente por `app_id`, `event_time`, `advertising_id` e `appsflyer_id`. Quando necessário, padronize o esquema de modo que ambas as tabelas tenham nomes de colunas consistentes.

```sql
WITH ua_sessions AS (
    SELECT DISTINCT
        app_id,
        COALESCE(advertising_id, appsflyer_id) AS user_id
    FROM sessions
    WHERE app_id = 'your.app.id.here'                        -- Replace with your app ID
      AND DATE_DIFF('day', TRY_CAST(SUBSTR(event_time, 1, 10) AS DATE), DATE('YYYY-MM-DD')) <= 31  -- Replace with target end date        
      AND is_primary_attribution = TRUE
),

retargeting_sessions AS (
    SELECT DISTINCT
        app_id,
        COALESCE(advertising_id, appsflyer_id) AS user_id
    FROM sessions_retargeting
    WHERE app_id = 'your.app.id.here'                        -- Same app 
      AND DATE_DIFF('day', TRY_CAST(SUBSTR(event_time, 1, 10) AS DATE), DATE('YYYY-MM-DD')) <= 31  -- Replace with target end date
),

all_sessions AS (
    SELECT * FROM ua_sessions
    UNION ALL
    SELECT * FROM retargeting_sessions
)

SELECT COUNT(DISTINCT user_id) AS mau_unified
FROM all_sessions;
```

</Accordion>

<div data-zendesk-anchors="overview=vis%C3%A3o-geral h_01K58WFCYQJE3JVR6Q4G5P1T3V=vis%C3%A3o-geral h_01K58WFCYQSX0YTSGWBC02TCG1=observa%C3%A7%C3%A3o querying-for-active-unique-users=consulta-de-usu%C3%A1rios-exclusivos-ativos h_01K58WFCYQ942VY9P70GHVG6SH=consulta-de-usu%C3%A1rios-exclusivos-ativos calculate-daily-active-users-dau=calcular-daily-active-users-dau h_01K58WFCYQ406CW66EEYPP5GFJ=calcular-daily-active-users-dau query-for-dau-%E2%80%93-user-acquisition-ua=query-for-dau---user-acquisition-ua h_01K58WFCYQVXBZN97BWHA8FC3C=query-for-dau---user-acquisition-ua query-for-dau-%E2%80%93-retargeting=query-for-dau---retargeting h_01K58WFCYQ4XNKQ9CW4D3KV2E2=query-for-dau---retargeting query-for-dau-%E2%80%93-unified-ua-retargeting=query-for-dau---unified-ua-retargeting h_01K58WFCYQ0NM0E44531YDJBCH=query-for-dau---unified-ua-retargeting calculate-monthly-active-users-mau=calcular-monthly-active-users-mau h_01K58WFCYQ251WMSNSD0EYXV69=calcular-monthly-active-users-mau query-for-mau-%E2%80%93-user-acquisition-ua=query-for-mau---user-acquisition-ua h_01K58WFCYQAV6T3S7SABSTMYKS=query-for-mau---user-acquisition-ua query-for-mau-%E2%80%93-retargeting=query-for-mau---retargeting h_01K58WFCYQ4H5CFQPPC5JQKHTJ=query-for-mau---retargeting query-for-mau-%E2%80%93-unified-ua-retargeting=query-for-mau---unified-ua-retargeting h_01K58WFCYQA1W91CHM1PN31MFG=query-for-mau---unified-ua-retargeting" />
