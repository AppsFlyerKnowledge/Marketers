---
title: Calcular usuarios activos diarios y mensuales (DAU y MAU)
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
  edited_at: '2026-08-12T11:49:34Z'
  id: 39071744864657
  locale: es
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/es/articles/39071744864657
---
> **En resumen:** Aprende a calcular usuarios activos diarios y mensuales para obtener insights valiosos sobre tus campañas

<div id="overview" />

## Visión general

Los usuarios activos diarios (DAU) y los usuarios activos mensuales (MAU) son métricas clave para entender el engagement de la aplicación y el comportamiento general del usuario. Proporcionan insights valiosos sobre tu base de usuarios activos, incluyendo la retención de usuarios, el rendimiento de las campañas y las tendencias de crecimiento a lo largo del tiempo.

Este artículo explica cómo calcular DAU y MAU utilizando consultas en dos tablas de raw data de Data Locker que representan la adquisición de usuarios y el tráfico de retargeting: las tablas `sessions` y `sessions_retargeting`.

<div id="note" />

> 📘 **Nota**
>
> A partir de febrero de 2025, el dashboard de actividad en AppsFlyer muestra datos unificados (UA y Retargeting) por defecto. Puedes notar una pequeña diferencia entre los raw data y los números del dashboard debido a <Anchor target="_blank" href="/marketers/es/docs/activity-metrics-in-my-dashboards#especificaciones-y-limitaciones">ajustes algorítmicos aprobados</Anchor>.

<div id="querying-for-active-unique-users" />

### Consultando usuarios únicos activos

Para calcular usuarios únicos, utiliza `advertising_id` como el identificador principal en tu consulta. Si `advertising_id` no está disponible, sustitúyelo por `appsflyer_id`. Este método se aplica solo a aplicaciones configuradas en <Anchor target="_blank" href="/marketers/es/docs/measure-reinstalls#attributed-to-the-first-install">modo de primera instalación</Anchor>.

Para aplicaciones que no utilizan este modo, recomendamos aplicar `count(distinct appsflyer_id)`.

<div id="calculate-daily-active-users-dau" />

## Calcular usuarios activos diarios (DAU)

Calcular el número total de usuarios únicos por día utilizando las consultas a continuación.

<div id="query-for-dau---user-acquisition-ua" />

<Accordion title="Consulta para DAU – Adquisición de Usuarios (UA)">

Seleccionar usuarios activos de UA para un día específico.

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

<Accordion title="Consulta para DAU – Retargeting">

Seleccionar usuarios activos de retargeting para un día específico.

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

<Accordion title="Consulta para DAU – Unificado (UA y Retargeting)">

Seleccionar usuarios activos de UA y retargeting para un día específico.

Para obtener una cobertura completa de usuarios activos, debes **unir** las tablas `sessions` y `sessions_retargeting` . Asegúrate de que los campos estén alineados, generalmente por `app_id`, `event_time`, `advertising_id` y `appsflyer_id`. Si es necesario, normaliza el esquema para que ambas tablas tengan nombres de columnas consistentes.

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

<div id="calculate-monthly-active-users-mau" />

## **Calcular Usuarios Activos Mensuales (MAU)**

Los dashboards de AppsFlyer presentan MAU de dos maneras:

1. **Usuarios activos en los últimos 31 días** – el número de usuarios activos únicos en los últimos 31 días.
2. **MAU en el mes del calendario** – el número de usuarios activos únicos dentro de un mes específico del calendario.

Las consultas a continuación demuestran cómo calcular el primer tipo de MAU. Para calcular el MAU del mes del calendario en su lugar, simplemente ajusta el rango de fechas para que coincida con el mes deseado.

<div id="query-for-mau---user-acquisition-ua" />

<Accordion title="Consultas para MAU – Adquisición de Usuarios (UA)">

Selecciona usuarios activos de UA para un mes específico.

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

<Accordion title="Consultas para MAU – Retargeting">

Selecciona usuarios activos de retargeting para un mes específico.

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

<Accordion title="Consultas para MAU – Unificado (UA y Retargeting)">

Selecciona usuarios activos de UA y retargeting para un mes específico.

Para obtener una cobertura completa de usuarios activos, debes **unir** las tablas `sessions` y `sessions_retargeting` . Asegúrate de que los campos estén alineados, generalmente por `app_id`, `event_time`, `advertising_id` y `appsflyer_id`. Si es necesario, normaliza el esquema para que ambas tablas tengan nombres de columnas consistentes.

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

<div data-zendesk-anchors="overview=visi%C3%B3n-general h_01K58WFCYQJE3JVR6Q4G5P1T3V=visi%C3%B3n-general h_01K58WFCYQSX0YTSGWBC02TCG1=nota querying-for-active-unique-users=consultando-usuarios-%C3%BAnicos-activos h_01K58WFCYQ942VY9P70GHVG6SH=consultando-usuarios-%C3%BAnicos-activos calculate-daily-active-users-dau=calcular-usuarios-activos-diarios-dau h_01K58WFCYQ406CW66EEYPP5GFJ=calcular-usuarios-activos-diarios-dau query-for-dau-%E2%80%93-user-acquisition-ua=query-for-dau---user-acquisition-ua h_01K58WFCYQVXBZN97BWHA8FC3C=query-for-dau---user-acquisition-ua query-for-dau-%E2%80%93-retargeting=query-for-dau---retargeting h_01K58WFCYQ4XNKQ9CW4D3KV2E2=query-for-dau---retargeting query-for-dau-%E2%80%93-unified-ua-retargeting=query-for-dau---unified-ua-retargeting h_01K58WFCYQ0NM0E44531YDJBCH=query-for-dau---unified-ua-retargeting calculate-monthly-active-users-mau=calcular-usuarios-activos-mensuales-mau h_01K58WFCYQ251WMSNSD0EYXV69=calcular-usuarios-activos-mensuales-mau query-for-mau-%E2%80%93-user-acquisition-ua=query-for-mau---user-acquisition-ua h_01K58WFCYQAV6T3S7SABSTMYKS=query-for-mau---user-acquisition-ua query-for-mau-%E2%80%93-retargeting=query-for-mau---retargeting h_01K58WFCYQ4H5CFQPPC5JQKHTJ=query-for-mau---retargeting query-for-mau-%E2%80%93-unified-ua-retargeting=query-for-mau---unified-ua-retargeting h_01K58WFCYQA1W91CHM1PN31MFG=query-for-mau---unified-ua-retargeting" />
