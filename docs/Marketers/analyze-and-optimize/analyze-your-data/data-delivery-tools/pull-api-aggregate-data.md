---
title: Datos agregados de Pull API
metadata:
  keywords:
    - Performance
    - raw data
    - Pull API
    - Reports
    - API
    - Parameters
    - API Policy
    - Advertisers
    - facebook rawdata
    - facebook raw data
    - Developers
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Raw Reports
  created_at: '2013-04-24T15:08:25Z'
  edited_at: '2026-08-12T11:51:16Z'
  id: 207034346
  locale: es
  section: Data delivery tools
  section_id: 6550995484561
  url: https://support.appsflyer.com/hc/es/articles/207034346
---
> **De un vistazo:** Usa esta Pull API para obtener tus reportes de estadísticas agregadas de AppsFlyer en archivos CSV.

[![PullAPIAverage_us-es.png](https://files.readme.io/fb9be34d49394086b37e71d2553d6f926829928a3e1f6cd2ec3e95943ecaa503-360008811078.png)](https://files.readme.io/fb9be34d49394086b37e71d2553d6f926829928a3e1f6cd2ec3e95943ecaa503-360008811078.png)

<div id="looking-for-pull-api-raw-data" />

> 👍 **¿Buscas raw data de Pull API?**
>
> Puedes obtener más información al respecto <Anchor target="_blank" href="/marketers/es/docs/pull-api-raw-data">aquí</Anchor>.

<div id="pull-api-aggregate-data" />

## Datos agregados de Pull API

* La Pull API te permite obtener reportes de datos agregados para la adquisición de usuarios (UA) y el retargeting en archivos CSV.
* <Anchor target="_blank" href="/marketers/es/docs/about-data-freshness-and-timezone-support#data-freshness-rates-and-timezone-support">Las tasas de actualización de datos</Anchor> son las mismas que las del reporte equivalente en la página Datos exportados y la página del panel de control general. Ten en cuenta que el costo puede actualizarse con un retraso de varias horas, en función del partner que proporcione los datos de costos.
* Filtrar por opciones disponibles: fuente de medios e intervalo de fechas.
* Las capacidades adicionales en la Pull API son las siguientes:
  * Agregar tipo de toque de atribución
  * Seleccionar la zona horaria

<div id="aggregate-performance-reports-available-via-pull-api" />

#### Reportes agregados de rendimiento disponibles a través de Pull API

<table><thead><tr><th>Categoría</th><th> Ucrania</th><th>Reorientación\*</th></tr></thead><tbody><tr><td>Partners (fuente de medios)</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Partners por fecha</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Diario</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Geolocalización</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Reporte de Geolocalización por Fecha</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td colspan="3">\* Para los reportes de retargeting, agrega <code><span>&amp;reattr=true</span></code> al URI. </td></tr></tbody></table>

<div id="using-pull-api-aggregate-data" />

<Accordion title="Uso de datos agregados de Pull API">

**Para utilizar los datos agregados de la Pull API**:

1. ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) Obtén el token de API. Un administrador deberá recuperar el token.
2. Dale a tu desarrollador el token de API que se utilizará en el encabezado de autenticación.
3. Proporciona a tus desarrolladores los [parámetros](/docs/pull-api-aggregate-data#parameters) que deben introducir cuando realicen la llamada a la API, como se describe en la sección que sigue. Los parámetros determinan en qué se enfoca el reporte, cómo se organiza, y proporcionan un marco de tiempo para la presentación de reportes.
4. Dile a tu desarrollador que siga sus <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-11">instrucciones de datos agregados de Pull API</Anchor> en el centro de desarrolladores.

</Accordion>

<div id="parameters" />

<Accordion title="Parámetros">

| Parámetro | Descripción |
| --- | --- |
| id\_aplicación | ID de aplicación |
| desde | <ul><li>El rango de fechas consiste en los parámetros `from`y `to`. El rango es el rango de valor de vida útil (LTV), que es la fecha de instalación.</li><li>Formato: `yyyy-mm-dd`,</li><li>Ejemplo: 2010-01-01</li></ul> |
| hasta | Fecha de finalización. Igual que para `from` |
| fuente\_de\_medios | Usar para limitar (filtrar) a una fuente de medios específica.<ul><li>Ejemplo: `media_source=facebook`</li></ul> |
| tipo de atribución táctil | Configura este parámetro tal como se muestra en el ejemplo para obtener KPI de [atribución por impresiones](/docs/pull-api-aggregate-data) (VTA).<br /><br />Ejemplo: `attribution_touch_type=impression`<br /><br />Algunos KPI de VTA, como los clics, las impresiones y las API de costos, no tienen valores asociados y, en cambio, muestran el valor N/A. |
| moneda | Divisa de ingresos y costos.<br /><br />Los reportes agregados de la Pull API siempre usan la divisa específica de la aplicación. |
| reattr | Obtener datos de conversión de retargeting.<ul><li>[Predeterminado] Si es falso, las campañas de datos de adquisición de usuarios (UA) vuelven.</li><li>Si es "true", la conversión de retargeting regresa.</li><li>**Ejemplo**:`reattr=true`</li></ul> |
| Zona horaria | [Predeterminado] Los datos se devuelven utilizando UTC.<ul><li>Las plantillas de URI se rellenan con el parámetro de zona horaria establecido en la zona horaria específica de la aplicación.</li><li>[Predeterminado] Si el parámetro no se envía, los datos regresan usando UTC.</li><li>Si envías `timezone=[Joda-Time]`, los datos se devuelven utilizando la zona horaria específica de la aplicación.</li></ul>Notas sobre la selección de zonas horarias<ul><li>El formato de zona horaria Joda-Time tiene en cuenta el horario de verano.</li><li>El valor de Joda-Time debe ser idéntico al valor definido en la página de configuración de la aplicación. Por ejemplo, si la zona horaria seleccionada en la configuración es París, el valor de la zona horaria de la URL de la Pull API debe ser `timezone=Europe%2fParis`.</li><li>La extracción de datos en la zona horaria seleccionada solo está disponible a partir de la fecha en la que se configuró la zona horaria. Cualquier dato anterior a la fecha del cambio usa UTC como la zona horaria.</li></ul> |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Rasgos y limitaciones">

| Caducado | Comentarios |
| --- | --- |
| Se requiere el tipo de token de la API | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)<Anchor target="_blank" href="/marketers/es/docs/managing-appsflyer-tokens">Token V2.0</Anchor> |
| Acceso a la red de publicidad | N/A |
| Acceso de agencias | Sí |
| Transparencia de Agencias | Sí |
| Divisa específica de la aplicación | Sí |
| Zona horaria específica de la aplicación | Sí |
| Costo | Los datos de costos son solo para campañas de UA; no son para retargeting o campañas inactivas (campañas sin instalaciones). |
| Actualización de los datos | <Anchor target="_blank" href="/marketers/es/docs/about-data-freshness-and-timezone-support#continuous-aka-realtime">Continua</Anchor> |
| Historial de datos | Los datos agregados de LTV están disponibles durante un máximo de 25 meses (2 años + 1 mes) |
| Datos no orgánicos | Sí |
| datos orgánicos | Sí |
| Limitaciones de velocidad | <Anchor target="_blank" href="/marketers/es/docs/report-generation-quotas-rate-limitations">Limitación</Anchor> |
| Limitaciones de tamaño | <ul><li>¡Nota! Pull API para soporte de datos sin procesar 1 millón de filas. Pull API para **datos agregados** puede agregar hasta 1 M de filas de raw data.</li><li>Las llamadas de la API devuelven un máximo de 200 000 filas.<ul><li>Si un reporte tiene exactamente 200 000 filas, entonces asume que faltan filas.</li><li>Realiza múltiples llamadas a la API, utilizando los parámetros from/to que incluyan la hora del día.</li></ul></li></ul> |
| Cambios del nombre de campaña | Los reportes de la Pull API no admiten cambios del nombre de campaña |

</Accordion>

<div id="see-also" />

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/aggregated-and-analytics-reporting-overview">Descripciones y ejemplos de reportes de estadísticas agregadas</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/aggregated-and-analytics-reporting-overview">Selecciona la herramienta de entrega de datos adecuada para datos agregados</Anchor>

<div data-zendesk-anchors="h_01HE0YP82966QHRAEW979ABCTP=buscas-raw-data-de-pull-api pull-api-aggregate-data=datos-agregados-de-pull-api h_01HE0YP829WD5TDFHTPYAV30QN=datos-agregados-de-pull-api aggregate-performance-reports-available-via-pull-api=reportes-agregados-de-rendimiento-disponibles-a-trav%C3%A9s-de-pull-api h_01HE0YP829EQ7N6CST352X917H=reportes-agregados-de-rendimiento-disponibles-a-trav%C3%A9s-de-pull-api h_01HE0YP82954F1ACVR2K4AFD5W=using-pull-api-aggregate-data h_01HE0YP8292131Q2561A4E1GYZ=parameters h_01HE0YP829ZPJAPHPDR9H4HMRT=traits-and-limitations h_01HE0Y2KTXS06WHN57MQ91AD09=consulta-tambi%C3%A9n" />
