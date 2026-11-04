---
title: Descripción general de reportes agregados y analíticos
metadata:
  keywords:
    - Agencies
    - Ad Networks
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
    - Agencies
    - Ad Networks
  created_at: '2020-02-04T09:38:14Z'
  edited_at: '2026-09-09T00:02:22Z'
  id: 360005437257
  locale: es
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/es/articles/360005437257
---
> **At a glance:** Descripción y comparación de reportes de atribución agregados y analíticos, herramientas y API disponibles.

<div id="aggregated-and-analytics-performance-reporting-overview" />

## Generación de reportes de rendimiento agregados y analíticos: herramientas y reportes

Las herramientas de agregado y análisis de la plataforma proporcionan a los anunciantes métricas que les permiten evaluar el rendimiento de sus aplicaciones, campañas y usuarios.

Las herramientas difieren en la forma en que se presentan los datos. Algunos reportan métricas de valor de vida útil (LTV) de las campañas, mientras que otros, como Cohort, se usan para analizar el engagement de los usuarios a lo largo del tiempo.

Las herramientas detalladas en este artículo se refieren a los datos que se pueden exportar desde la plataforma. Usa la tabla de comparación de herramientas a continuación para comprender la función principal y las diferencias entre las herramientas.

<Accordion title="Comparación de métodos de reporte">

En la siguiente tabla se describen los diferentes métodos de generación de reportes y paneles de control para obtener datos agregados.

[**Descarga la tabla como un archivo CSV**](https://docs.google.com/spreadsheets/d/e/2PACX-1vSICicxcvD0996RT59fTLDJvdGUKxqPqr47f5SMD8BmsbZtrWIoxRxJEo7tAXTBBmnIbiH097VtK6L9/pub?output=xlsx) **para ver campos adicionales que explican diversas especificaciones y limitaciones para ayudarte a comparar y contrastar los diferentes métodos de reporte.**

Los campos de especificación adicionales en el archivo CSV descargable incluyen:

* <Anchor target="_blank" href="/marketers/es/docs/about-data-freshness-and-timezone-support">Actualización de datos</Anchor>: período de tiempo entre la ocurrencia del evento y la disponibilidad de los datos a través del método de reporte.
* <Anchor target="_blank" href="/marketers/es/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">LTV/actividad</Anchor>: si los datos son LTV o de actividad.
* <Anchor target="_blank" href="/marketers/es/docs/retargeting-attribution-guide">Retargeting</Anchor>: si se muestran los datos de retargeting (re-engagement y reatribución).
* <Anchor target="_blank" href="/marketers/es/docs/measure-reinstalls#attributed-to-the-first-install">Atribución de eventos de reinstalación a la primera instalación</Anchor>: si los eventos después de una reinstalación se pueden atribuir a la instalación original.
* <Anchor target="_blank" href="/marketers/es/docs/about-data-freshness-and-timezone-support#date-and-timezone-principles">Zona horaria</Anchor>: qué zona horaria (UTC o seleccionada por la aplicación) se utiliza para mostrar los datos.
* <Anchor target="_blank" href="/marketers/es/docs/measure-reinstalls#unattributed-organic-inapps">Eventos sin atribuir</Anchor>: si se muestran los eventos que no se atribuyen después de una reinstalación.
* <Anchor target="_blank" href="/marketers/es/docs/campaign-name-changes?">Cambios en el nombre de la campaña</Anchor>: si puedes cambiar los nombres de las campañas sin crear pantallas duplicadas.

| Método de reporte | Descripción |
| --- | --- |
| <Anchor target="_blank" href="/marketers/es/docs/master-api-user-acquisition-metrics-via-api">API maestra</Anchor>  <br />(función Premium) | LTV seleccionados, actividad, retención, cohorte y KPI de rendimiento de la campaña de Protect360 por API, en formato CSV o JSON. |
| <Anchor target="_blank" href="/marketers/es/docs/pull-api-aggregate-data">Pull API: reportes agregados</Anchor> | Valor de por vida (LTV) de los usuarios que instalan, realizan re-engagement y/o se reatribuyen en archivos CSV. Los datos de UA y retargeting están separados; no hay una opción unificada. |
| <Anchor target="_blank" href="/marketers/es/docs/aggregated-data-export-page">Página de datos exportados: informes de estadísticas agregadas</Anchor> | Valor de por vida (LTV) de los usuarios que instalan, realizan re-engagement y/o se reatribuyen en archivos CSV. Los datos de UA y retargeting están separados; no hay una opción unificada. |
| <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">Resumen de SKAN</Anchor> | Métricas reportadas a través de postbacks SKAN de iOS y puntos de datos adicionales durante las ventanas iniciales de medición del usuario. |
| <Anchor target="_blank" href="/marketers/es/docs/skan-aggregated-performance-report-api">API de datos agregados de SKAN</Anchor> | Métricas reportadas a través de postbacks SKAN de iOS y puntos de datos adicionales durante las ventanas iniciales de medición del usuario. |
| <Anchor target="_blank" href="/marketers/es/docs/protect360-dashboard">Panel de control de Protect360</Anchor> | Métricas e insights relacionados con el tráfico fraudulento.  <br />Datos basados en LTV para las aplicaciones y datos basados en actividades para eventos in-app. |
| <Anchor target="_blank" href="/marketers/es/docs/cohort-and-retention-dashboard">Panel de control de cohorte</Anchor> | Varias métricas de usuario para cada día después de la instalación. |
| <Anchor target="_blank" href="/marketers/es/docs/cohort-api">API de cohorte</Anchor>  <br />(función Premium) | Varias métricas de usuario para cada día después de la instalación. También incluye actividad a nivel de evento por event\_date para los usuarios cuya conversión se produjo en un plazo de 365 días. |
| <Anchor target="_blank" href="/marketers/es/docs/cohort-analytics-via-data-locker">Data Locker de cohorte</Anchor>  <br />(función Premium) | Varias métricas de usuario para cada día después de la instalación. También incluye actividad a nivel de evento por event\_date para los usuarios cuya conversión se produjo en un plazo de 1.095 días. |
| Son <Anchor target="_blank" href="/marketers/es/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">valores de vida útil (LTV)</Anchor>, de modo que el intervalo de fechas del reporte se relaciona con la fecha de atribución que se define de la siguiente manera: | Reportes de datos agregados versionados. Característica. |
| <Anchor target="_blank" href="/marketers/es/docs/custom-dashboards">Panel de control personalizado</Anchor> | Panel de control personalizado con métricas de adquisición de usuarios de LTV. |
| <Anchor target="_blank" href="/marketers/es/docs/pivot-table-user-metrics">Reportes de pivote</Anchor>  <br />(función Premium) | LTV seleccionados, actividad, retención y KPI de rendimiento de la campaña de Protect360, en el panel de control o a través de CSV. |
| <Anchor target="_blank" href="/marketers/es/docs/set-up-and-use-roi360-cost-etl-reports">ETL de costos</Anchor> | Datos de costos de campaña con la mejor granularidad disponible por fuente de medios. |
| Reportes de uso | Una combinación de todas las funciones basadas en el uso de AppsFlyer que afectan las obligaciones contractuales durante los plazos de los ciclos de facturación. |
| <Anchor target="_blank" href="/marketers/es/docs/creative-optimization-guide">Dashboard de Optimización creativa</Anchor> | Datos de rendimiento de LTV sobre los creativos. Esto significa que las métricas corresponden a conversiones que se produjeron a partir de creatividades durante el intervalo de fechas seleccionado. |

</Accordion>

<Accordion title="Métodos de entrega de datos de cohortes">

Cohort está disponible a través de varios métodos de entrega: <Anchor target="_blank" href="/marketers/es/docs/cohort-and-retention-dashboard">dashboard de Cohort</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/cohort-api">API de Cohort</Anchor> y <Anchor target="_blank" href="/marketers/es/docs/cohort-analytics-via-data-locker">análisis de Cohort a través de Data Locker</Anchor>. La tabla que sigue enumera las diferencias.

| Característica | Análisis de cohortes en Data Locker | [Beta cerrada] Reportes agregados avanzados en Data Locker | Panel de control de la cohorte | API de cohortes |
| --- | --- | --- | --- | --- |
| Aplicación múltiple o única | Múltiple. Los datos se agrupan por aplicación en un solo archivo o se dividen en archivos separados por aplicación. | Múltiple. Rendimiento combinado o agrupado por opciones de aplicación. | Múltiple. Rendimiento combinado o agrupado por opciones de aplicación. | Única |
| Agrupaciones | Jerarquía de campaña completa y nombres de eventos. 20 agrupaciones | Jerarquía de campaña completa y nombres de eventos. 20 agrupaciones | 4 agrupaciones | 7 agrupaciones |
| Métricas disponibles | Todas las métricas | Varias métricas de usuario para cada día después de la instalación. | 1 métrica seleccionable y 4 métricas fijas por vista | 1 métrica seleccionable y 4 métricas fijas por llamada |
| Días después de la atribución disponibles (días de cohorte) | 365 | 1095 | 180 | 180 |
| Limitaciones de exportación de datos | Todo el conjunto de datos está disponible | Panel de control general | Descarga manual y configuración | Tasa y tamaño de respuesta limitado |
| Solicitud personalizable | No | No | Sí | Sí |

Diferencias entre los tipos de cohorte

</Accordion>

<div id="user-journey-reports" />

### Reportes de trayectoria del usuario

Los reportes descritos están disponibles a través de la página Datos exportados o mediante el uso de datos agregados de Pull API.

Son reportes de <Anchor target="_blank" href="/marketers/es/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">valor de vida útil (LTV)</Anchor>. Por lo tanto:

* La primera fecha de reporte disponible es la primera fecha de instalación de la aplicación.
* El rango de fechas del reporte se refiere a la fecha de atribución:
  * Fecha de instalación para reportes de UA y Protect360
  * Fecha de reatribución o re-engagement en el caso de reportes de retargeting

<Accordion title="Reportes de datos agregados de LTV en la UA que contienen usuarios no orgánicos y orgánicos">

<table><thead><tr><th>Nombre del reporte</th><th>Agrupado por</th></tr></thead><tbody><tr><td>Partners (fuentes de medios)</td><td>Agencia, fuente de medios, campaña</td></tr><tr><td>Partners por fecha</td><td>Fecha, agencia, fuente de medios, campaña</td></tr><tr><td>Actividad diaria</td><td>Fecha, agencia, fuente de medios, campaña</td></tr><tr><td>Geolocalización</td><td>País, agencia, fuente de medios, campaña</td></tr><tr><td>Geolocalización por fecha</td><td>Fecha, país, agencia, fuente de medios, campaña</td></tr><tr><td>KPI de atribución por impresiones (VTA)</td><td><a href="./pull-api-aggregate-data" target="_blank">Los reportes de VTA están disponibles por Pull API</a></td></tr><tr><td colspan="2"> <strong>Nota</strong>: Si la <em>fuente de medios</em> seleccionada es Meta ads, se incluyen columnas adicionales: ID de grupo de anuncios, nombre del grupo de anuncios, ID del conjunto de anuncios, nombre del conjunto de anuncios</td></tr></tbody></table>

Los campos de fecha en los archivos CSV tienen el formato aaaa-mm-dd. Cuando abres un archivo CSV en Excel, los campos de fecha se formatean según la configuración de fecha y hora de tu computadora. Asegúrate de seleccionar el formato de visualización de fecha adecuado en <Anchor target="_blank" href="https://support.office.com/en-us/article/format-a-date-the-way-you-want-8e10019e-d5d8-47a1-ba95-db95123d273e#ID0EAACAAA=Windows">Excel.</Anchor>

<div id="examples-of-aggregate-reports" />

#### Ejemplos de reportes agregados

[Ejemplos de reporte en una hoja de cálculo](https://docs.google.com/spreadsheets/d/e/2PACX-1vQmzRons779Dk5QWVoPsOF8E7yJLwNPB1IF87shZr6rcMJLjszlSNIbAMVcdeQLysr8Bc4QAby5QB4u/pub?output=xlsx)

<div id="fields-in-ua-aggregate-reports" />

#### Campos en reportes agregados de UA

<table><thead><tr><th rowspan="2">Campo</th><th rowspan="2">Descripción</th><th colspan="5">Nombre del reporte</th></tr><tr><th>Partner (fuente de medios)</th><th>Partner por fecha</th><th>Diario</th><th>Geolocalización</th><th>Geolocalización por fecha</th></tr></thead><tbody><tr><td>País</td><td>País de instalación</td><td></td><td></td><td></td><td>✓</td><td>✓</td></tr><tr><td>Fecha</td><td>Fecha de atribución</td><td></td><td>✓</td><td></td><td></td><td>✓</td></tr><tr><td>Agencia o PMD (af_prt)</td><td>Nombre de agencia o partner</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Fuente de medios (pid)</td><td>Fuente de medios que trae al usuario (pid=fuente de medios)</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Campaña</td><td>Nombre de la campaña (c= nombre de la campaña)</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>ID de campaña</td><td>ID de campaña de Meta</td><td>Solo anuncios de Meta</td><td>Solo anuncios de Meta</td><td>Solo anuncios de Meta</td><td>Solo anuncios de Meta</td><td>Solo anuncios de Meta</td></tr><tr><td>ID de grupo de anuncios</td><td>ID de grupo de anuncios de Meta o ID de anuncio</td><td>Solo anuncios de Meta</td><td>Solo anuncios de Meta</td><td>Solo anuncios de Meta</td><td>Solo anuncios de Meta</td><td>Solo anuncios de Meta</td></tr><tr><td>Nombre de grupo de anuncios</td><td>Grupo de anuncios de Meta</td><td>Solo anuncios de Meta</td><td>Solo anuncios de Meta</td><td>Solo anuncios de Meta</td><td>Solo anuncios de Meta</td><td>Solo anuncios de Meta</td></tr><tr><td>ID de conjunto de anuncios</td><td>ID del conjunto de anuncios de Meta</td><td>Solo anuncios de Meta</td><td>Solo anuncios de Meta</td><td>Solo anuncios de Meta</td><td>Solo anuncios de Meta</td><td>Solo anuncios de Meta</td></tr><tr><td>Nombre del conjunto de anuncios</td><td>Nombre del conjunto de anuncios de Meta</td><td>Solo anuncios de Meta</td><td>Solo anuncios de Meta</td><td>Solo anuncios de Meta</td><td>Solo anuncios de Meta</td><td>Solo anuncios de Meta</td></tr><tr><td>OPCIONAL</td><td>ingresos promedio por usuario</td><td>✓</td><td>✓</td><td></td><td>✓</td><td>✓</td></tr><tr><td>eCPI promedio</td><td>eCPI promedio</td><td></td><td>✓</td><td></td><td></td><td></td></tr><tr><td>Clics</td><td>Cantidad de clics</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>tasa de conversión</td><td>Cantidad de instalaciones/cantidad de clics</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>CTR</td><td>Tasa de clics</td><td></td><td>✓</td><td>✓</td><td></td><td></td></tr><tr><td>`{your event name} (usuarios únicos)</td><td>Cantidad de usuarios únicos que realizaron el evento</td><td>✓</td><td>✓</td><td></td><td>✓</td><td>✓</td></tr><tr><td>{your event name} (contador de eventos)</td><td>Contador de eventos</td><td>✓</td><td>✓</td><td></td><td>✓</td><td>✓</td></tr><tr><td>{your event name}` (Ventas en XXX)</td><td>Evento de ventas en XXX donde XXX es la moneda seleccionada por la aplicación</td><td>✓</td><td>✓</td><td></td><td>✓</td><td>✓</td></tr><tr><td>Impresiones</td><td>Cantidad de impresiones</td><td>✓</td><td>✓</td><td></td><td>✓</td><td>✓</td></tr><tr><td>Instalaciones</td><td>Cantidad de instalaciones</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>usuarios leales</td><td>[predeterminado] Usuario que abre la aplicación más de 3 veces</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Instalaciones/usuarios leales</td><td>Tasa de usuarios leales</td><td>✓</td><td>✓</td><td></td><td></td><td></td></tr><tr><td>ROI (Retorno de la Inversión)</td><td>Retorno de la inversión</td><td>✓</td><td>✓</td><td></td><td></td><td></td></tr><tr><td>Sesiones</td><td><ul><li>Cantidad de aplicaciones no orgánicas abiertas</li><li>Las sesiones orgánicas y no orgánicas están disponibles en el análisis de cohortes</li></ul></td><td>✓</td><td>✓</td><td>✓</td><td>✓</td><td>✓</td></tr><tr><td>Costo total</td><td>-</td><td>✓</td><td>✓</td><td></td><td></td><td></td></tr><tr><td>Ingresos totales</td><td>Ingresos totales generados por la fuente de medios y la campaña</td><td>✓</td><td>✓</td><td></td><td>✓</td><td>✓</td></tr><tr><td colspan="7"> <strong>Nota:</strong> Las columnas que muestran "Solo anuncios de Meta" se incluyen al seleccionar anuncios de Meta como la única fuente de medios.</td></tr></tbody></table>

</Accordion>

<Accordion title="Reportes de datos agregados de Retargeting">

Los reportes de retargeting consisten en usuarios que se involucraron en una <Anchor target="_blank" href="/marketers/es/docs/retargeting-attribution-guide#retargeting-reports-and-raw-data">campaña de retargeting</Anchor> y realizaron un re-engagement o una reatribución.

En los reportes de retargeting, no existe distinción entre los usuarios orgánicos y los no orgánicos.

Para obtener reportes de retargeting a través de Pull API, añade el parámetro *&reattr=true* a los URI de los reportes de rendimiento.

<div id="aggregate-ltv-retargeting-reports" />

#### Reportes agregados de retargeting de LTV

| Nombre del reporte | Agrupado por |
| --- | --- |
| Partners (fuentes de medios) | Agencia, fuente de medios, campaña |
| Partners por fecha | Fecha, agencia, fuente de medios, campaña |
| Actividad por fecha | Fecha, agencia, fuente de medios, campaña |
| País | País, agencia, fuente de medios, campaña |
| País por fecha | Fecha, país, agencia, fuente de medios, campaña |

<div id="aggregate-ltv-retargeting-reports-1" />

#### Reportes agregados de retargeting de LTV

| Campo | Descripción | Partners | Diario | Partners por fecha | Geolocalización por fecha | Geolocalización |
| --- | --- | --- | --- | --- | --- | --- |
| Fecha | Fecha de conversión | - | - | ✓ | ✓ | - |
| País |  | - | ✓ |  | ✓ | ✓ |
| Agencia o PMD (af\_prt) | Nombre de agencia o partner | ✓ | ✓ | ✓ | ✓ | ✓ |
| Fuente de medios (pid) |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Campaña (c) |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Clics |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Conversiones |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Tipo de conversión | Reatribución o re-engagement | ✓ | ✓ | ✓ | ✓ | ✓ |
| tasa de conversión | Conversiones/clics | ✓ | ✓ | ✓ | ✓ | ✓ |
| Sesiones |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| usuarios leales |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Instalaciones/usuarios leales |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| Costo total |  | - | - | - | - | - |
| eCPI promedio |  | - | - | - | - | - |
| Ingresos totales |  | ✓ | ✓ | ✓ | ✓ | ✓ |
| ROI (Retorno de la Inversión) |  | - | - | - | - | - |
| OPCIONAL |  | ✓ | ✓ | ✓ | - | ✓ |

</Accordion>

<div id="feature-reports" />

## Reportes de funciones

<Accordion title="SKAdNetwork">

<Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide#reporting-options">Informes de estadísticas agregadas de SKAdNetwork</Anchor>

</Accordion>

<Accordion title="Protect360: fraude bloqueado">

![Ejemplo de reporte de fraude bloqueado por Protect360](https://theme.zdassets.com/theme_assets/245528/ffbbc473bb0e74b9fb636ed735f69e9af6a25a18.png)

Los reportes agregados de fraude bloqueado proporcionan detalles de los eventos que <Anchor target="_blank" href="/marketers/es/docs/protect360-anti-fraud-guide">Protect360</Anchor> bloquea.

Los reportes están disponibles a través de la Pull API. Estos reportes no están disponibles a través de la página de Datos exportados.

El rango de fechas se refiere a la fecha de instalación.

<div id="aggregate-protect360-reports-available-via-pull-api" />

#### Reportes agregados de Protect360 disponibles a través de Pull API

| Nombre del reporte |
| --- |
| Partners (fuentes de medios) |
| Partners por fecha |
| Geolocalización |
| Geolocalización por fecha |
| Reporte de campaña del partner |

**Limitación:** El motivo de bloqueo **Bots** se muestra incluso en casos en los que el motivo debería ser **versión de la app** o **falta el ID de usuario del cliente**.

</Accordion>

<div id="see-also" />

#### Consulta también

* <Anchor target="_blank" href="/marketers/es/docs/configuring-meta-campaign-management-partners">Configuración de partners de administración de campañas de Meta</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-overview">Información general de los reportes de raw data</Anchor>

<div data-zendesk-anchors="aggregated-and-analytics-performance-reporting%E2%80%94tools-and-reports=generaci%C3%B3n-de-reportes-de-rendimiento-agregados-y-anal%C3%ADticos-herramientas-y-reportes 01EWA9VQ2HH93525BMK6WN0P6S=generaci%C3%B3n-de-reportes-de-rendimiento-agregados-y-anal%C3%ADticos-herramientas-y-reportes user-journey-reports=reportes-de-trayectoria-del-usuario 01ED4D7W8CVAQ9V2GCEX1G6KD7=reportes-de-trayectoria-del-usuario examples-of-aggregate-reports=ejemplos-de-reportes-agregados 01ED4D7W8C3ZNBYR3CMHJF3QSE=ejemplos-de-reportes-agregados fields-in-ua-aggregate-reports=campos-en-reportes-agregados-de-ua h_01HDNYFR9KTQ7ZF35C7E7M7AF1=campos-en-reportes-agregados-de-ua aggregate-ltv-retargeting-reports=reportes-agregados-de-retargeting-de-ltv h_01HDNYFR9MSJWCP3JA4M1WXN1H=reportes-agregados-de-retargeting-de-ltv aggregate-ltv-retargeting-reports::b2093953=reportes-agregados-de-retargeting-de-ltv-1 h_01HDNYFR9MSK9VQQ0Q889Z55TN=reportes-agregados-de-retargeting-de-ltv-1 feature-reports=reportes-de-funciones h_01HDNYFR9MYXVZ5BA9FDZ6D82M=reportes-de-funciones aggregate-protect360-reports-available-via-pull-api=reportes-agregados-de-protect360-disponibles-a-trav%C3%A9s-de-pull-api h_01HDNYFR9MSZ9K8F283J0WBHCZ=reportes-agregados-de-protect360-disponibles-a-trav%C3%A9s-de-pull-api h_01HDNYYJXVY9XHX87K06NXYQNS=consulta-tambi%C3%A9n" />
