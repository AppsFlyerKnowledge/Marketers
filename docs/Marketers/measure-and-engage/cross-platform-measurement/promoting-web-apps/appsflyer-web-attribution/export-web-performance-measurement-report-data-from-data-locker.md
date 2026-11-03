---
title: >-
  Exporta los datos de los reportes de medición de rendimiento web desde Data
  Locker
metadata:
  keywords:
    - Agencies
    - Web Attribution
    - Web Attribution SDK
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
    - Agencies
  created_at: '2026-02-04T10:49:59Z'
  edited_at: '2026-08-26T00:22:19Z'
  id: 43510758321809
  locale: es
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/es/articles/43510758321809
---
> **Resumen:** Exporta datos de medición de rendimiento web desde Data Locker en dos tipos de reportes que te permiten analizar el rendimiento del sitio web al nivel adecuado. Usa End User Events para analizar todas las visitas y eventos, y Conversions para contar y atribuir anclas de conversión únicas (primeras visitas, revisitas y eventos de adquisición de usuarios).

> ❗️ **Warning**
>
> **¡Importante!** Debes tener una suscripción a Data Locker para usar los reportes de medición del rendimiento web en Data Locker.

## Acerca de los reportes de medición de rendimiento web

Data Locker proporciona dos reportes para la medición de rendimiento web, **End User Events** y **Conversions**, cada uno diseñado para distintas necesidades de análisis.

* El reporte de **Eventos de usuario final** es la fuente principal para analizar la actividad del sitio web:
  * Incluye **todos los eventos web y todas las visitas**
  * Registra cada visita como una sesión atribuida `SESSION`
  * Ideal para reportes a **nivel de visita** y **nivel de evento**
* El reporte **Conversions** es el más adecuado para el análisis a nivel de conversión. Una conversión es un ancla de atribución, un punto de contacto que determina cuándo y cómo asignar el crédito de marketing. Esto incluye:
  * *primeras visitas* (cuando un usuario llega a tu sitio web por primera vez),
  * *revisitas* (cuando un usuario vuelve después de un engagement con un anuncio no orgánico), y
  * *eventos de adquisición de usuarios* (eventos personalizados como registro o primer depósito) que indican que se ha adquirido un usuario.
* Todos los eventos de usuario se vinculan posteriormente a estas conversiones y heredan los detalles de la campaña

La interfaz de Informes avanzados de Data Locker también muestra **Engagements** y **Eventos de usuario final multiplataforma** como opciones independientes de reportes de medición del rendimiento web. Este artículo abarca **Eventos de usuario final** y **Conversiones**, los dos reportes que se usan para la mayoría de los análisis de medición del rendimiento web.

## Selecciona un reporte de medición del rendimiento web

Antes de exportar datos de medición del rendimiento web, selecciona el reporte correspondiente en Data Locker.

1. En AppsFlyer, desde el menú lateral, selecciona **Exportar > Data Locker**.
2. Haz clic en la pestaña **Informes avanzados**.
3. Selecciona **Eventos de usuario final** o **Conversiones** en la lista de reportes de medición del rendimiento web.
4. Haz clic en **Guardar configuración**.

## Campos de reporte

Para conocer qué campos contienen los reportes, descarga un ejemplo de cada reporte:

* [Ejemplo del reporte de eventos de usuario final](https://docs.google.com/spreadsheets/d/e/2PACX-1vQYFF0r4pMpo_voSK8QObpiRtx-diU_0a-0XVuKIVMEfh6rRPudIDXA5bgDw_lcc0qwBPcPhYtLdWwh/pub?output=csv)
* [Ejemplo del reporte de eventos de conversión](https://docs.google.com/spreadsheets/d/e/2PACX-1vTMqcc6PKBATBg1DYVO8MWKrAs_wlqXxyANe3a_gu62xp3hFZV9wWT1X8c9oRekaIEwCfKZ2y9agVeV/pub?output=csv)

El reporte de ejemplo incluye todos los campos del reporte y sus valores. Para ver las definiciones de los campos, consulta el <Anchor target="_blank" href="/marketers/es/docs/raw-data-field-dictionary">diccionario de campos</Anchor>.

## Frecuencia del reporte y actualización de los datos

Usa estos detalles para entender cuándo se añaden datos nuevos y cuándo los eventos recientes pasan a estar disponibles en el reporte.

* **Frecuencia del reporte**: Se añaden datos nuevos cada hora.
* **Actualización de los datos**: Los eventos suelen aparecer en el reporte en un plazo de 2 a 3 horas desde que se producen.

### Así es como funciona cada lote:

* Cada lote **procesa** eventos de una ventana de 1,5 horas.
* Dentro de esa ventana, solo se **atribuyen** los eventos de la primera hora.
* Los 30 minutos restantes se usan **únicamente para enriquecer** los eventos atribuidos con IDs de usuario de cliente (CUIDs).
* Los 30 minutos más recientes de eventos **todavía no se atribuyen**; se incluirán en el siguiente lote.

[![](https://files.readme.io/1957b8b0c6b29fb44934ef7d10fd04278d541a4f2c12bb90e49fc8cb61ec7db5-44460048223761.png)](https://files.readme.io/1957b8b0c6b29fb44934ef7d10fd04278d541a4f2c12bb90e49fc8cb61ec7db5-44460048223761.png)

### ¿Cuándo aparecerán estos eventos en el reporte?

Los eventos se escriben en los reportes **cuando termina el procesamiento**. Por ejemplo, los eventos de **08:00–09:00**, atribuidos en el lote de las 10:00, aparecerán en la **versión del reporte de las 11:00**.

### Ejemplo: qué hace el lote de las 10:00

| **Fecha** | **Reporte disponible en** | **Eventos web atribuidos (hora del evento)** | **Eventos web procesados para enriquecer eventos anteriores con CUIDs** |
| --- | --- | --- | --- |
| 01-28-2026 | 11:00 | 08:00 — 09:00 | 09:00-09:30 |
| 01-28-2026 | 12:00 | 09:00 — 10:00 | 10:00-10:30 |
| 01-28-2026 | 13:00 | 10:00 — 11:00 | 10:00-11:30 |

## Descarga los datos del reporte desde tu cloud bucket

Para obtener más información sobre cómo descargar los datos del reporte desde tu cloud bucket, consulta <Anchor target="_blank" href="/marketers/es/docs/data-locker-for-marketers#folder-structure">la estructura de carpetas de Data Locker</Anchor>.

## Consideraciones para desarrolladores de BI

<Accordion title="Diferencias clave: Web frente a móvil">

La atribución web difiere de la atribución móvil tanto en los identificadores como en la lógica de los datos. Para mejorar la precisión de los datos, aplica los siguientes filtros y mejores prácticas en tus consultas.

| Aspecto | Móvil | Web |
| --- | --- | --- |
| Filtro de plataforma | `platform = 'IOS'` o `platform = 'ANDROID'` | `platform = 'WEBSITE'` |
| Identificador de usuario (valor) | `appsflyer_id` (basado en el dispositivo) | `appsflyer_id_value` (basado en cookies) |
| Tipo de identificador | Varía según el dispositivo | `appsflyer_id_type` siempre es `web_id` |
| Evento de adquisición | Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>. | First Visit es el valor predeterminado, pero la adquisición de usuarios se puede personalizar |
| Reengagement | `RE-ENGAGEMENT` | `REVISITA` |
| Reatribución | Compatible | No compatible: la web solo tiene adquisición de usuarios y revisitas |
| Identificación de la aplicación | ID de la app (por ejemplo, `id123456789`) | Dominio con prefijo (por ejemplo, `website-www.example.com`) |

</Accordion>

<Accordion title="¿Qué tabla consultar?">

El reporte de **Eventos de usuario final** es adecuado para la mayoría de los análisis. Incluye todos los eventos y visitas del sitio web. En este reporte, cada visita web también se registra como una `SESSION` atribuida, lo que lo convierte en la fuente principal para reportar a nivel de visita y de evento.

La tabla de **conversiones** es adecuada principalmente para contar primeras visitas, revisitas y adquisiciones de usuarios cuando necesitas conversiones únicas sin registros de eventos duplicados.

| Caso de uso | Tabla | ¿Por qué? |
| --- | --- | --- |
| Contar visitas/sesiones | `end_user_events` | Cada fila es una sesión o un evento |
| Contar conversiones únicas | `conversiones` | Evita duplicados |
| Analiza los eventos in-app | `end_user_events` con `end_user_event_type = 'IN_APP'` | Solo los eventos in-app tienen nombres de evento |

</Accordion>

<Accordion title="Implementar filtros de consulta">

Aplica los siguientes filtros para asegurarte de que tus consultas de raw data sean precisas. Si no los implementas, el resultado será entradas duplicadas y métricas mezcladas entre plataformas.

* **Filtrar por plataforma (obligatorio):** Incluye `WHERE platform = 'WEBSITE'` para aislar los datos de origen web y excluir los registros de entornos móviles, PC o CTV.
* **Filtrar por crédito de atribución (obligatorio):** La misma acción del usuario puede aparecer dos veces en `end_user_events` porque AppsFlyer puede asignarle dos créditos de atribución diferentes, según la vista de reporte.

  Esto puede ocurrir cuando el usuario tiene:

  * una fuente original de **Adquisición de usuarios (UA)** y, más adelante,
  * una fuente de **re-engagement**.

  En ese caso, AppsFlyer puede escribir dos registros para el mismo evento:

  * **Crédito principal:** atribuye el evento a la interacción de marketing relevante más reciente. Se usa en las vistas Unificada y Retargeting.

    Para evitar el recuento doble, consulta `end_user_events` usando solo el registro de crédito principal de forma predeterminada:

    ```sql
    WHERE platform = 'WEBSITE'
      AND is_primary_attribution = true
    ```
  * **Crédito secundario:** atribuye el evento a la fuente de UA original. Se utiliza en la vista de adquisición de usuarios para la medición del valor del ciclo de vida (LTV).

    Como la misma acción del usuario puede almacenarse como dos registros (uno con crédito principal y otro con crédito secundario), contar eventos sin un filtro puede contabilizar esa acción dos veces.

    Usa estas consultas como plantillas para analizar datos de atribución web en BigQuery u otras herramientas de BI.

* **Filtrar por tipo de conversión (opcional):** Incluye `WHERE conversion_type = 'USER_ACQUISITION'` o `WHERE conversion_type = 'RETARGETING'` para aislar los datos de atribución según el tipo de campaña.

#### Tabla de resumen de filtros

| Requisito del filtro | Lógica SQL | Contexto de implementación |
| --- | --- | --- |
| Especificación de la plataforma | `WHERE platform = 'WEBSITE'` | Aísla los datos de origen web de los registros de otras plataformas. |
| Vista unificada (evita duplicados) | `WHERE is_primary_attribution = true AND plataforma = 'WEBSITE'` | Prioriza el crédito de la campaña de retargeting sobre la campaña de UA original. Úsalo para reportes generales y evitar el doble conteo. |
| Vista solo de retargeting | `WHERE conversion_type = 'RETARGETING' AND plataforma = 'WEBSITE'` | Úsalo específicamente cuando analices el rendimiento solo de las campañas de retargeting. |
| Vista solo de adquisición de usuarios | `WHERE conversion_type = 'USER_ACQUISITION' AND plataforma = 'WEBSITE'` | Úsalo específicamente en vistas centradas en la adquisición, donde los eventos deben vincularse a la visita inicial. |

</Accordion>

<Accordion title="Identificación y recuento de usuarios finales">

En raw data de Web Performance Measurement, un usuario final puede aparecer con dos ID distintos:

* `customer_user_id`: Un identificador estable que configuras tú (normalmente para usuarios que han iniciado sesión).
* `appsflyer_id_value`: Un ID basado en cookies que puede caducar con el tiempo.

Para identificar correctamente a los **usuarios únicos** y calcular **métricas a nivel de usuario**, usa siempre:

```sql
COALESCE(customer_user_id, appsflyer_id_value)
```

Así es como funciona:

* Si existe `customer_user_id`, AppsFlyer lo usa (preferido y estable).
* Si no, AppsFlyer recurre a `appsflyer_id_value`.

Usa `COALESCE(customer_user_id, appsflyer_id_value)` siempre que necesites:

* Contar usuarios distintos
* Agrupar por usuario
* Filtrar por usuarios específicos
* Unir tablas por usuario
* Calcular cualquier métrica a nivel de usuario

#### Ejemplo: contar usuarios distintos

```sql
SELECT 
  COUNT(DISTINCT COALESCE(customer_user_id, appsflyer_id_value)) AS unique_users
FROM `end_user_events`
WHERE platform = 'WEBSITE'
  AND is_primary_attribution = TRUE
```

</Accordion>

<Accordion title="Tráfico orgánico vs. no orgánico">

Utiliza el campo `is_organic`:

| Tipo de tráfico | Filtro |
| --- | --- |
| Utilizando la dirección IP del dispositivo reportada por el SDK. | `is_organic = true` |
| No orgánicas | `is_organic = false` |

</Accordion>

<Accordion title="Gestión de valores vacíos">

| Tipo de datos | Valor vacío |
| --- | --- |
| Cadena | `''` (cadena vacía) |
| Suscripción IAP | `NULL` |

</Accordion>

<Accordion title="Ejemplos de consultas">

<Accordion title="1. Total de visitas por fuente de medios (7 días)">

Cuenta las sesiones web atribuidas a cada fuente de medios.

```sql
SELECT media_source, COUNT(*) AS total_visits
FROM end_user_events
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND is_primary_attribution = true
  AND end_user_event_type = 'SESSION'
GROUP BY media_source
ORDER BY total_visits DESC
```

</Accordion>

<Accordion title="2. Primeras visitas y revisitas por campaña">

```sql
SELECT campaign_name, conversion_name, COUNT(*) AS conversion_count
FROM conversions
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND conversion_name IN ('FIRST_VISIT', 'REVISIT')
GROUP BY campaign_name, conversion_name
ORDER BY conversion_count DESC
```

</Accordion>

<Accordion title="3. Contar nombres de evento distintos (solo eventos in-app)">

```sql
SELECT
  event_name,
  COUNT(*) AS event_count
FROM end_user_events
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND is_primary_attribution = true
  AND end_user_event_type = 'IN_APP'
GROUP BY event_name
ORDER BY event_count DESC
```

</Accordion>

<Accordion title="4. Contar usuarios distintos por fuente de medios">

```sql
SELECT
  media_source,
  COUNT(DISTINCT COALESCE(customer_user_id, appsflyer_id_value)) AS unique_users
FROM end_user_events
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND is_primary_attribution = true
GROUP BY media_source
ORDER BY unique_users DESC
```

</Accordion>

<Accordion title="5. Tasa de conversión: de First Visit a Purchase (unión entre tablas)">

```sql
WITH first_visits AS (
  SELECT
    COALESCE(customer_user_id, appsflyer_id_value) AS user_id,
    media_source
  FROM conversions
  WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 30 DAY)
    AND platform = 'WEBSITE'
    AND unified_app_id = 'website-example.com'
    AND conversion_name = 'FIRST_VISIT'
),
purchases AS (
  SELECT DISTINCT
    COALESCE(customer_user_id, appsflyer_id_value) AS user_id
  FROM end_user_events
  WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 30 DAY)
    AND platform = 'WEBSITE'
    AND unified_app_id = 'website-example.com'
    AND is_primary_attribution = true
    AND end_user_event_type = 'IN_APP'
    AND event_name = 'purchase'
)
SELECT
  fv.media_source,
  COUNT(DISTINCT fv.user_id) AS first_visit_users,
  COUNT(DISTINCT p.user_id) AS purchasers,
  SAFE_DIVIDE(COUNT(DISTINCT p.user_id), COUNT(DISTINCT fv.user_id)) AS conversion_rate
FROM first_visits fv
LEFT JOIN purchases p ON fv.user_id = p.user_id
GROUP BY fv.media_source
ORDER BY conversion_rate DESC
```

</Accordion>

<Accordion title="6. Ingresos por campaña (últimos 7 días)">

```sql
SELECT
  campaign_name,
  media_source,
  SUM(revenue_usd) AS total_revenue_usd,
  COUNT(*) AS revenue_events
FROM end_user_events
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND is_primary_attribution = true
  AND revenue_usd IS NOT NULL
  AND revenue_usd <> 0.0
GROUP BY campaign_name, media_source
ORDER BY total_revenue_usd DESC
```

</Accordion>

<Accordion title="7. Primeras visitas orgánicas vs. no orgánicas por día">

```sql
SELECT
  DATE(event_time) AS visit_date,
  CASE WHEN is_organic = true THEN 'Organic' ELSE 'Non-Organic' END AS traffic_type,
  COUNT(*) AS first_visits
FROM conversions
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 30 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND conversion_name = 'FIRST_VISIT'
GROUP BY visit_date, traffic_type
ORDER BY visit_date, traffic_type
```

</Accordion>

<Accordion title="8. Desglose de adquisición de usuarios vs. retargeting">

```sql
SELECT
  conversion_type,
  conversion_name,
  COUNT(*) AS conversions
FROM conversions
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
GROUP BY conversion_type, conversion_name
ORDER BY conversions DESC
```

</Accordion>

<Accordion title="9. Distribución de ID de clic (Google, Meta, TikTok, etc.)">

```sql
SELECT
  click_id_type,
  COUNT(*) AS events_with_click_id
FROM end_user_events
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 7 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND is_primary_attribution = true
  AND click_id_type != ''
GROUP BY click_id_type
ORDER BY events_with_click_id DESC
```

</Accordion>

<Accordion title="10. Agrupa a los usuarios en cohortes por fecha de conversión (equivalente a la fecha de instalación en móvil)">

```sql
SELECT
  DATE(event_time__conversion) AS cohort_date,
  media_source,
  COUNT(DISTINCT COALESCE(customer_user_id, appsflyer_id_value)) AS cohort_users
FROM end_user_events
WHERE event_time >= TIMESTAMP_SUB(CURRENT_TIMESTAMP(), INTERVAL 30 DAY)
  AND platform = 'WEBSITE'
  AND unified_app_id = 'website-example.com'
  AND is_primary_attribution = true
GROUP BY cohort_date, media_source
ORDER BY cohort_date, cohort_users DESC
```

</Accordion>

</Accordion>

## Especificaciones y limitaciones

Los siguientes campos **no son compatibles con los datos web** y siempre estarán vacíos:

| Caducado | Descripción |
| --- | --- |
| `advertising_id_type`, `hardware_id_type`, etc. | Ambos |
| `agency`, `site_id`, `ad_type` | Ambos |
| `platform_group` | conversiones |
| `app_version__conversion` | end\_user\_events |
| Todos los campos `__assist_*` | conversiones |

## Consulte también

* <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">Acerca de los informes avanzados de Data Locker</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/data-locker-for-marketers">Data Locker para marketers</Anchor>

<div data-zendesk-anchors="about-the-data-locker-web-attribution-reports=acerca-de-los-reportes-de-medici%C3%B3n-de-rendimiento-web h_01KGM4FT90X1K2V8M8GJV6EW5K=acerca-de-los-reportes-de-medici%C3%B3n-de-rendimiento-web h_01_select-web-performance-measurement-report=selecciona-un-reporte-de-medici%C3%B3n-del-rendimiento-web select-a-web-performance-measurement-report=selecciona-un-reporte-de-medici%C3%B3n-del-rendimiento-web report-fields=campos-de-reporte h_01KGM4FT90WP73N1D75WWNT2TE=campos-de-reporte report-timing-and-data-freshness=frecuencia-del-reporte-y-actualizaci%C3%B3n-de-los-datos h_01KGM4FT90B6W7KBS9K1FSSETD=frecuencia-del-reporte-y-actualizaci%C3%B3n-de-los-datos here%E2%80%99s-how-each-batch-works=as%C3%AD-es-como-funciona-cada-lote h_01KGM4FT91MCGCBYSHE18JHQ96=as%C3%AD-es-como-funciona-cada-lote when-will-these-events-appear-in-the-report=cu%C3%A1ndo-aparecer%C3%A1n-estos-eventos-en-el-reporte h_01KGM4FT91XF7HCM8E8TQ56D0D=cu%C3%A1ndo-aparecer%C3%A1n-estos-eventos-en-el-reporte example-what-the-1000-am-batch-does=ejemplo-qu%C3%A9-hace-el-lote-de-las-1000 h_01KGM4FT91D90DWYGSE3SES2ZY=ejemplo-qu%C3%A9-hace-el-lote-de-las-1000 download-report-data-from-your-cloud-bucket=descarga-los-datos-del-reporte-desde-tu-cloud-bucket h_01KGM4FT91NECKXMDW60A4B9X5=descarga-los-datos-del-reporte-desde-tu-cloud-bucket bi-developer-considerations=consideraciones-para-desarrolladores-de-bi h_01KGM4FT91C2KP050ZAYW6K8FD=consideraciones-para-desarrolladores-de-bi filter-summary-table=tabla-de-resumen-de-filtros h_01KGM4FT91MSN2SN7TKNJZ54V4=tabla-de-resumen-de-filtros example-count-distinct-users=ejemplo-contar-usuarios-distintos h_01KGM4FT91VDR0FWTMAPW6GM83=ejemplo-contar-usuarios-distintos traits-and-limitations=especificaciones-y-limitaciones h_01KGM4FT91QZR30KJAQ87AG691=especificaciones-y-limitaciones h_01_web-perf-see-also=consulte-tambi%C3%A9n see-also=consulte-tambi%C3%A9n" />
