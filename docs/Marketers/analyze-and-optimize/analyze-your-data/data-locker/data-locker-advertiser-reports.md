---
title: Reportes de anunciantes de Data Locker
metadata:
  keywords:
    - Advertisers
    - Premium Feature
    - Marketers
    - Data Locker
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Data Locker
  created_at: '2021-11-11T09:48:51Z'
  edited_at: '2026-10-20T03:36:29Z'
  id: 4410643856657
  locale: es
  section: Data Locker
  section_id: 6550945728657
  url: https://support.appsflyer.com/hc/es/articles/4410643856657
---
> **En resumen:** Reportes de datos agregados y raw data disponibles a través de Data Locker

<div id="reports-available-via-data-locker-for-advertisers" />

## Reportes disponibles a través de Data Locker para anunciantes

<table><colgroup><col/><col/><col/></colgroup><thead><tr><th>Tipo de datos</th><th>Grupo de reportes</th><th>Se requiere suscripción a Data Locker</th></tr></thead><tbody><tr><td>Raw</td><td>Trayectoria del usuario: raw data</td><td>Sí (2)</td></tr><tr><td>Raw</td><td>Las alertas de Protect360 se actualizan a la hora UTC diaria.</td><td>Sí</td></tr><tr><td>Raw</td><td>Atribución people-based (PBA) </td><td>No </td></tr><tr><td>Raw</td><td>Incrementalidad</td><td>No </td></tr><tr><td>Raw</td><td>SKÁN</td><td>No (1)</td></tr><tr><td>Raw</td><td>Ingresos</td><td><p>El reporte de versión única de ingresos publicitarios requiere una suscripción a Data Locker.</p><p>Todos los demás reportes requieren una suscripción al paquete ROI360 Advanced.</p></td></tr><tr><td>Raw</td><td>Aplicaciones de CTV, PC y consola</td><td>Sí</td></tr><tr><td>Agregado</td><td>Análisis de cohortes</td><td>No (1)</td></tr><tr><td>Agregado avanzado</td><td>Análisis de cohortes</td><td>No (3)</td></tr><tr><td>Agregado</td><td>Optimización creativa</td><td><p>No (1)</p><p>Requiere un plan de suscripción Premium a la Optimización.</p></td></tr><tr><td>Agregado</td><td>Métricas orgánicas del día 7</td><td>No (1)</td></tr><tr><td colspan="3"><p>(1) Si no tienes una suscripción a Data Locker, debes proporcionar <a href="./data-locker-for-marketers#storage-options" target="_blank">almacenamiento de tu propiedad</a>.</p><p>(2) Excepto para engagements cross-platform.</p><p>(3) Disponible con suscripción a Data Locker o con el paquete de APIs de análisis.</p></td></tr></tbody></table>

<div id="data-freshness-explanations" />

<Accordion title="Actualización de los datos">

La disponibilidad de reportes en Data Locker varía según el tipo de reporte. Según el reporte, los datos se entregan utilizando un modelo de actualización por hora, diario o versionado. Para obtener más información sobre cómo estos intervalos de actualización se relacionan con la jerarquía de carpetas de Data Locker, consulta <Anchor target="_blank" href="/marketers/es/docs/data-locker-for-marketers#folder-structure">Estructura de carpetas</Anchor>.

| Actualización de los datos | Descripción | Ejemplo de reporte |
| --- | --- | --- |
| Por hora | Reportes que se actualizan durante el día y se almacenan en carpetas horarias `h` según el momento en que AppsFlyer recibe los datos. | <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview">Reporte de eventos in-app</Anchor> |
| A diario | Reportes que se generan una vez al día en lugar de actualizarse continuamente durante el día. | <Anchor target="_blank" href="/marketers/es/docs/measure-uninstalls">Reporte de desinstalaciones</Anchor> |
| Versionado | Reportes en los que los datos del mismo día pueden publicarse varias veces a medida que hay datos más nuevos o completos disponibles, siendo la versión más reciente la más precisa. | <Anchor target="_blank" href="/marketers/es/docs/revenue-etl-reports#ad-revenue-versioned">Reporte de ingresos publicitarios atribuidos</Anchor> |

</Accordion>

<div id="raw-data-reports" />

## Reportes de raw data

<div id="user-journey" />

<Accordion title="Trayectoria del usuario">

Para obtener una descripción de los tipos de reportes, consulta los <Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-overview">reportes de trayectoria del usuario</Anchor>.

| Categoría | Tipo de reporte (tema) | Actualización de los datos | Orgánico/No-orgánico | Exclusivo para Data Locker |
| --- | --- | --- | --- | --- |
| Adquisición de usuarios | Clics | 1-3 horas | N/D | ✓ |
| Reorientación | Clics | 1-3 horas | N/D | ✓ |
| Adquisición de usuarios | Impresiones | 1-3 horas | N/D | ✓ |
| Reorientación | Impresiones | 1-3 horas | N/D | ✓ |
| Adquisición de usuarios | Instalaciones | 1-3 horas | Ambos |  |
| Adquisición de usuarios | Eventos in-app | 1-3 horas | Ambos |  |
| Adquisición de usuarios | Ingresos por publicidad atribuida | Diario+1 | No orgánico |  |
| Adquisición de usuarios | Ingresos por publicidad orgánica | Diario+1 | Orgánico |  |
| Reorientación | Ingresos por publicidad de retargeting | Diario+1 | No orgánico |  |
| Reorientación | Conversiones | 1-3 horas | No orgánico |  |
| Reorientación | Eventos in-app | 1-3 horas | No orgánico |  |
| Reorientación | Sesiones | 1-3 horas | Ambos | ✓ |
| Adquisición de usuarios | Sesiones | 1-3 horas | Ambos | ✓ |
| Adquisición de usuarios | Desinstalaciones | Desinstalación diaria | No orgánico |  |
| Adquisición de usuarios | Desinstalaciones orgánicas | Desinstalación diaria | Orgánico |  |
| Reinstalaciones | Reinstalaciones | 1-3 horas | No orgánico |  |
| Reinstalaciones | Reinstalaciones orgánicas | 1-3 horas | Orgánico |  |
| Adquisición de usuarios | Interacciones en múltiples plataformas | Por hora | Ambos | ✓ |

</Accordion>

<div id="protect360" />

<Accordion title="Las alertas de Protect360 se actualizan a la hora UTC diaria.">

Ver <Anchor target="_blank" href="/marketers/es/docs/protect360-raw-data-reports">sobre los reportes de Protect360</Anchor>

| Tipo de reporte (tema) | Actualización de los datos |
| --- | --- |
| Instalaciones bloqueadas | 1-3 horas |
| Eventos in-app bloqueados | 1-3 horas |
| Clics bloqueados | 1-3 horas |
| Instalaciones posteriores a la atribución | A diario<br /><br />El reporte de cada día contiene instalaciones posteriores a la atribución reportadas el día anterior. Por ejemplo, el reporte de los datos generados el lunes está en el reporte del martes. |

</Accordion>

<div id="peoplebased-attribution" />

<Accordion title="Atribución people-based">

**Actualización de los datos**

Disponible todos los días 10-12 horas después del final del día anterior UTC. Por ejemplo, los datos recibidos un lunes se procesan después del final del día y están disponibles en la carpeta del lunes h=23. Los datos están disponibles a las 12:00 UTC del martes.

**Consideraciones**

* Los datos de todos los grupos de marcas de PBA en la cuenta siempre se proporcionan sin tener en cuenta el filtro de aplicación.
* La segregación de datos por aplicación no está disponible.

| Tipo de reporte (tema) |
| --- |
| <Anchor target="_blank" href="/marketers/es/docs/pba-raw-data-reports#website-visits-and-website-events">Visitas al sitio web</Anchor> |
| <Anchor target="_blank" href="/marketers/es/docs/pba-raw-data-reports#website-visits-and-website-events">Eventos del sitio web</Anchor> |
| <Anchor target="_blank" href="/marketers/es/docs/pba-raw-data-reports#websiteassisted-installs::7e12586d">Instalaciones asistidas por el sitio web</Anchor> |
| <Anchor target="_blank" href="/marketers/es/docs/pba-raw-data-reports#conversion-paths">Rutas de conversión</Anchor> |

</Accordion>

<div id="incrementality" />

<Accordion title="Incrementalidad">

Consulta los <Anchor target="_blank" href="/marketers/es/docs/incrementality-for-remarketing-overview#available-reports">reportes de incrementalidad</Anchor>

</Accordion>

<div id="skan" />

<Accordion title="SKÁN">

Acerca de los <Anchor target="_blank" href="/marketers/es/docs/skan-raw-data-reports">reportes de raw data de SKAN</Anchor>

**Actualización de los datos**

* Los datos están disponibles el día siguiente al día en que AppsFlyer recibe el postback o en que los datos son reportados a AppsFlyer por la API.
* Los datos están contenidos en la carpeta h=23 de la fecha en que AppsFlyer los recibe. Ejemplo: Si el postback se recibió el lunes, se procesa después del final del día. El procesamiento se completa antes de las 12:00 UTC del martes, los datos están disponibles en la carpeta del lunes h=23.

| Tipo de reporte (tema) |
| --- |
| Devoluciones de mensajes |
| Copia de postbacks (enviados directamente por iOS a AppsFlyer) |
| Instalaciones |
| Re-descargas |
| Eventos in-app |
| Dimensiones publicitarias de SRN |

</Accordion>

<div id="ad-revenue" />

<Accordion title="Ingresos">

Consulta los reportes <Anchor target="_blank" href="/marketers/es/docs/revenue-etl-reports">Revenue ETL de Data Locker</Anchor>

Consulta los <Anchor target="_blank" href="/marketers/es/docs/roi360-guide-ad-revenue-attribution#ad-revenue-raw-data">datos raw data de ingresos publicitarios</Anchor>

</Accordion>

<div id="ctv" />

<Accordion title="Datos de la plataforma de CTV, PC y consola">

Consulta <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-data-via-data-locker">datos de plataformas CTV, PC y consolas a través de Data Locker</Anchor>

</Accordion>

<div id="advanced-raw-data-reports-beta" />

## Reportes avanzados de raw data (Beta)

Los reportes avanzados presenta una nueva generación de reportes de raw data diseñados para ofrecer datasets estructurados, validados y **preparados para IA**. Permiten la ingesta y el análisis del **viaje completo del usuario, desde el primer engagement hasta la conversión y la actividad post-instalación, utilizando solo tres reportes**.  
Diseñados con **campos tipados**, **nombres de campos optimizados** y un esquema consistente en todos los datasets, estos reportes garantizan claridad, precisión y facilidad de uso. La estructura unificada simplifica los joins entre datasets, **reduce la complejidad del ETL y del procesamiento downstream**, y proporciona datos que respaldan análisis avanzados y te brindan flexibilidad para trabajar con tus datos según lo necesites. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">Acerca de los reportes avanzados de Data Locker</Anchor>.

<div id="advanced-reports" />

<Accordion title="Reporte de engagements raw data">

El reporte de engagements raw data consolida datos de clics e impresiones de actividades de adquisición de usuarios y retargeting tanto en plataformas mobile como Connected TV (CTV). Al proporcionar una vista unificada de las interacciones de los usuarios con tus anuncios, este reporte permite un análisis completo del rendimiento del top-of-funnel y ayuda a los marketers a identificar qué creatividades y canales generan engagement significativo. También permite optimizar costos y alcance a nivel de engagement, ofreciendo una base sólida para evaluar la exposición de marketing y la calidad del tráfico. Para más información, consulta el <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports#engagements">reporte de engagements sin procesar</Anchor> en Acerca de los reportes avanzados de Data Locker.

| Categoría | Tipo de reporte (tema) | Actualización de los datos | Exclusivo para Data Locker |
| --- | --- | --- | --- |
| Adquisición de usuarios y retargeting | Clics e impresiones | 1–3 horas | ✅ |

</Accordion>

<div id="conversion-report" />

<Accordion title="Reporte de conversiones">

El reporte de conversiones ofrece una vista completa de todas las instalaciones de apps, incluyendo fuentes orgánicas y no orgánicas en plataformas mobile y Connected TV (CTV). Al centralizar los datos de conversión, los marketers pueden realizar análisis integrales de crecimiento utilizando un único dataset optimizado. Usa este reporte para medir y optimizar con precisión el rendimiento de marketing. Para más información, consulta el <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports#conversions">reporte de conversión</Anchor> en Acerca de los reportes avanzados de Data Locker.

| Categoría | Tipo de reporte (tema) | Actualización de los datos | Exclusivo para Data Locker |
| --- | --- | --- | --- |
| Adquisición de usuarios y retargeting | Conversiones | 1–3 horas | ✅ |

<div id="note" />

> 📘 **Nota**
>
> * Las reinstalaciones no están incluidas en este reporte.
> * Para apps de plataformas extendidas, incluidas CTV, PC y consolas, los eventos de conversión de retargeting no están incluidos.

</Accordion>

<div id="h_01K9CROSSPLATFORMREPORT" />

<Accordion title="Reporte de eventos de usuario final">

El Reporte de eventos de usuario final captura datos detallados de eventos in-app, incluidas sesiones, compras, registros y finalización de niveles, en plataformas mobile y CTV. Cada evento se enriquece con un contexto completo de atribución, lo que permite un análisis detallado del comportamiento del usuario, la retención y el lifetime value, garantizando al mismo tiempo una trazabilidad completa de la atribución. Para más información, consulta el [reporte de eventos del usuario final](#enduser-events) en Acerca de los reportes avanzados de Data Locker.

| Categoría | Tipo de reporte (tema) | Actualización de los datos | Exclusivo para Data Locker |
| --- | --- | --- | --- |
| Adquisición de usuarios y retargeting | Eventos de usuario final | 1–3 horas | ✅ |

<div id="note-1" />

> 📘 **Nota**
>
> Para apps de plataformas extendidas, incluidas CTV, PC y consolas, los eventos de usuario final de retargeting no están incluidos.

</Accordion>

<div id="aggregated-reports" />

## Reportes agregados

<div id="cohort-analytics" />

<Accordion title="Análisis de cohortes">

**Actualización de los datos**

Los reportes suelen estar disponibles a las 12:00 UTC en la carpeta del día anterior. Por ejemplo, si el procesamiento se completa antes de las 12:00 UTC del martes, los datos estarán disponibles en la carpeta del lunes.

| Tipo de reporte (tema) |
| --- |
| <Anchor target="_blank" href="/marketers/es/docs/cohort-analytics-via-data-locker">Cohorte unificada</Anchor> |
| <Anchor target="_blank" href="/marketers/es/docs/cohort-analytics-via-data-locker">Adquisición de usuarios de cohortes</Anchor> |
| <Anchor target="_blank" href="/marketers/es/docs/cohort-analytics-via-data-locker">Retargeting de cohortes</Anchor> |

</Accordion>

<div id="advanced-aggregated-reports" />

<Accordion title="Reportes agregados avanzados">

Los reportes agregados avanzados en Data Locker contienen datos agregados con una calidad, precisión, granularidad y volumen óptimos e ilimitados. <Anchor target="_blank" href="/marketers/es/docs/advanced-aggregated-reports-in-data-locker">Saber más</Anchor>

</Accordion>

<div id="creative-optimization-etl" />

<Accordion title="ETL de Optimización Creativa">

Los reportes ETL de Optimización creativa brindan a tus analistas de datos toda la información necesaria para analizar el rendimiento creativo. Se proporcionan reportes completos de rendimiento a nivel de recursos, incluidos todos los indicadores clave de rendimiento (KPI), los KPI de embudo superior e inferior, datos de atribución y datos de recursos creativos. <Anchor target="_blank" href="/marketers/es/docs/creative-optimization-etl-reporting">Saber más</Anchor>

</Accordion>

<div data-zendesk-anchors="reports-available-via-data-locker-for-advertisers=reportes-disponibles-a-trav%C3%A9s-de-data-locker-para-anunciantes 01H7WFZN6P1S49NYX8Q0W55P0B=reportes-disponibles-a-trav%C3%A9s-de-data-locker-para-anunciantes 01H7WFZN6PQWASTMXM9V72QZER=data-freshness-explanations raw-data-reports=reportes-de-raw-data 01H7WFZN6P94YW1V79NT3HV5G4=reportes-de-raw-data 01H7WFZN6PD75S557PDB5PSFFR=user-journey 01H7WFZN6QY2GV69N464EE196M=protect360 01H7WFZN6QW72FDBTMW2ZD7NZQ=peoplebased-attribution 01H7WFZN6QZ1B7BS6E59RVAF30=incrementality 01H7WFZN6Q0P99DCFA7MZQTVSX=skan 01H7WFZN6Q717F9Z1HG38JVBG3=ad-revenue 01H7WFZN6QMJGSAJR00MHYJB6Z=ctv Unified%20raw-data-reports=reportes-avanzados-de-raw-data-beta h_01JX9T0PGE93JNJ3S4NDP0C2YW=reportes-avanzados-de-raw-data-beta h_01K85EE8DA4E8D4SVHYV2PE42E=conversion-report h_01K85EE8DAWY52B7RJQ33MJ59B=nota cross-platform-end-user-events-report=h_01K9CROSSPLATFORMREPORT h_01KMD3WY9MQABBWFCTJYVWG66S=nota-1 aggregated-reports=reportes-agregados 01H7WFZN6Q90AT8N0VY5PKQ407=reportes-agregados 01H7WFZN6QNKXTRM7G6VFANSZ7=cohort-analytics h_01J0K1MEKEEAQBXF1YRZTG8V0X=advanced-aggregated-reports h_01J0TQ88VNSFZJ27T3E2P3MVE6=creative-optimization-etl" />
