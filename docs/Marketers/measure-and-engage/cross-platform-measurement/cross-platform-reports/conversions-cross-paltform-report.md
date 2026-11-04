---
title: Reporte multiplataforma de conversiones cruzadas
metadata:
  keywords:
    - Marketers
    - Data Locker
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - Marketers
    - Data Locker
    - Cross-Platform Measurement
  created_at: '2026-09-02T07:11:54Z'
  edited_at: '2026-09-18T00:39:34Z'
  id: 50451304393617
  locale: es
  section: Cross platform reports
  section_id: 50467263168657
  url: https://support.appsflyer.com/hc/es/articles/50451304393617
---
> **At a glance:** El reporte de conversiones multiplataforma muestra el viaje completo del usuario detrás de cada conversión multiplataforma, incluida toda la cadena de engagement asistido y el contexto de ingresos, no solo el último punto de contacto.

<div id="about-the-report" />

## Sobre el reporte

El reporte de conversiones multiplataforma es un reporte de raw data que proporciona registros de conversiones a nivel de usuario, vinculados entre plataformas mediante tu <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/set-customer-user-id">Customer User ID (CUID)</Anchor>. Esto te permite analizar el viaje completo del usuario que llevó a una conversión, no solo el último punto de contacto.

Para obtener más información sobre el flujo y la configuración de atribución basada en el usuario, consulta <Anchor target="_blank" href="/marketers/es/docs/beta-user-based-cross-platform-attribution">Atribución multiplataforma basada en el usuario</Anchor>.

<div id="report-fields" />

## Campos de reporte

Para conocer qué campos contiene el reporte, descarga una <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRTFg6HXtHNYwegAjMysjybPbRk4IO8uflwvbGvR_xb11BcCrCWQ7i3xZD_Y2iiYSsx_MjTPN0E_Bmk/pub?gid=670907846&single=true&output=csv">muestra del reporte</Anchor>.

El reporte de ejemplo incluye todos los campos del reporte y sus valores. Para las definiciones de los campos, consulta <Anchor target="_blank" href="/marketers/es/docs/raw-data-field-dictionary">el diccionario de campos</Anchor>.

El reporte contiene tres grupos de campos:

* **Campos de conversión multiplataforma:** fuente de medios, campaña, anuncio, geolocalización, dispositivo, CUID, tipo de conversión, ingresos, marca de tiempo de la conversión multiplataforma e identificadores relacionados.
* **Campos de assists (1, 2 y 3):** para cada una de las tres posiciones de assist, la fuente de medios, campaña, conjunto de anuncios, anuncio, agencia, canal, tipo y subtipo de engagement, ID del sitio y hora del evento correspondientes. Estos campos utilizan la convención de nomenclatura `<field>__assist_1`, `<field>__assist_2` y `<field>__assist_3`.
* **Campos de enriquecimiento:** permiten el análisis del lifetime value (LTV) a nivel de usuario y a nivel de evento. Por ejemplo, combina estos campos con los registros de conversión de un usuario para crear una vista del LTV por usuario en todas las plataformas.

<div id="report-data-freshness" />

## Actualización de los datos del reporte

El reporte ejecuta un proceso por lotes cada 4 horas. Cada ejecución del proceso por lotes procesa los eventos que ingresaron en la base de datos durante las 4 horas anteriores. Por ejemplo, la ejecución por lotes de las 8:00 procesa los eventos que ingresaron en la base de datos entre las 3:00 y las 7:00.

El proceso por lotes asigna los eventos a sus intervalos horarios correspondientes. Por ejemplo, los eventos que ingresaron en la base de datos entre las 3:00 y las 4:00 aparecen en la versión de las 3:00.

> 📘 **Note**
>
> Normalmente hay un breve retraso entre el momento real de un evento y su entrada en la base de datos. El reporte utiliza la hora de entrada en la base de datos para mantener una agrupación por horas precisa y coherente.

<div id="example-the-8-am-batch-run" />

### Ejemplo: la ejecución por lotes de las 8:00

| Fecha | Versión del reporte | Disponible en | Incluye eventos que ocurren entre | Incluye eventos que ingresan en la base de datos entre |
| --- | --- | --- | --- | --- |
| 2025-10-01 | 3:00 | 9:00 | 2:00-4:00 | 3:00-4:00 |
| 2025-10-01 | 4:00 | 9:00 | 3:00-5:00 | 4:00-5:00 |
| 2025-10-01 | 5:00 | 9:00 | 4:00-6:00 | 5:00-6:00 |
| 2025-10-01 | 6:00 | 9:00 | 5:00-7:00 | 6:00-7:00 |

Algunas notas sobre este ejemplo:

* El lote no procesa eventos de la última hora antes de la ejecución, para dejar suficiente tiempo para enriquecer los eventos con su CUID relacionado. En el ejemplo anterior, el proceso por lotes de las 8:00 procesa los eventos que ingresaron en la base de datos entre las 3:00 y las 7:00. Los eventos que ingresaron en la base de datos entre las 7:00 y las 8:00 no se procesan en esa ejecución.
* El reporte está disponible una hora después de la ejecución del proceso por lotes, ya que durante esa hora un proceso interno actualiza el lote. En el ejemplo anterior, el proceso por lotes de las 8:00 a. m. está disponible a las 9:00 a. m.

<div id="subscribe-to-the-report" />

## Regístrate en el reporte

Para registrarte en el reporte:

1. En AppsFlyer, en el menú lateral, selecciona **Exportar** > **Data Locker**.
2. En el panel **Contenido de Data Locker**, desplázate hacia abajo hasta la sección **Reportes avanzados**.
3. Selecciona **Conversiones multiplataforma**.

<div id="access-the-report-data-in-your-cloud-bucket" />

## Accede a los datos del reporte en tu bucket de la nube

La ruta del reporte consta de la siguiente jerarquía de carpetas:

```text
<bucket-name>/<DataLocker connection name>/t=conversions_user_level_cross_platform/dt=<yyyy-mm-dd>/h=<hour>/
```

<div id="business-intelligence-bi-developer-considerations" />

## Consideraciones para desarrolladores de business intelligence (BI)

Recuerda lo siguiente al conectar tu base de datos o dashboard a este reporte:

* Cada versión horaria del reporte contiene registros de conversión únicos. Asegúrate de extraer todos los reportes cada hora o a diario.
* Los campos de asistencia (`__assist_1`, `__assist_2`, `__assist_3`) reflejan los engagement de asistencia detrás de cada conversión, en función de los datos de conversión subyacentes. Úsalos para reconstruir la secuencia de puntos de contacto que llevó a cada conversión.
* El reporte ofrece los ingresos en tres divisas: `revenue_usd` (normalizado), `revenue_value_original` (la divisa del evento reportado; consulta `revenue_currency_original`) y `revenue_value_customer` (tu divisa preferida; consulta `currency_customer`). Usa la que mejor se ajuste a tus necesidades de reporte.
* Este reporte no incluye campos de costo (costo, clics, impresiones). En su lugar, extráelos del <Anchor target="_blank" href="/marketers/es/docs/set-up-and-use-roi360-cost-etl-reports">reporte ETL de costos</Anchor>.
* El reporte proporciona todos los datos de la aplicación en un único archivo. Usa el campo ID de aplicación para segregar datos por aplicación o configura Data Locker para que segregue por aplicación. Te recomendamos usar el <Anchor target="_blank" href="/marketers/es/docs/data-locker-for-marketers#app-segregation">tipo de segregación unificada</Anchor>.

<div data-zendesk-anchors="h_01=sobre-el-reporte about-the-report=sobre-el-reporte h_02=campos-de-reporte report-fields=campos-de-reporte h_03=actualizaci%C3%B3n-de-los-datos-del-reporte report-data-freshness=actualizaci%C3%B3n-de-los-datos-del-reporte h_07=ejemplo-la-ejecuci%C3%B3n-por-lotes-de-las-800 example-8am-batch-run=ejemplo-la-ejecuci%C3%B3n-por-lotes-de-las-800 h_04=reg%C3%ADstrate-en-el-reporte subscribe-to-the-report=reg%C3%ADstrate-en-el-reporte h_05=accede-a-los-datos-del-reporte-en-tu-bucket-de-la-nube access-report-data-cloud-bucket=accede-a-los-datos-del-reporte-en-tu-bucket-de-la-nube h_06=consideraciones-para-desarrolladores-de-business-intelligence-bi bi-developer-considerations=consideraciones-para-desarrolladores-de-business-intelligence-bi" />
