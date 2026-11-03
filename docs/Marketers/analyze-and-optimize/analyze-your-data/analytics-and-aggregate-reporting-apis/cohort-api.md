---
title: API de cohorte
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
  edited_at: '2026-08-12T11:49:43Z'
  id: 360004799057
  locale: es
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/es/articles/360004799057
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En resumen:** La API de Cohort proporciona a los anunciantes una forma programática de obtener datos de cohorte. Utiliza la API para integrar datos de cohorte en sistemas de BI y de automatización de marketing.

## API de cohorte

La API de cohortes se utiliza para obtener datos de rendimiento de campañas de cohortes de la plataforma de AppsFlyer. Es funcionalmente equivalente al <Anchor target="_blank" href="/marketers/es/docs/cohort-and-retention-dashboard">dashboard de cohorte</Anchor>.

Para usar cohorte y retención, defines los datos que deseas ver. Seleccionas usuarios de una aplicación y los segmentas por tiempo de conversión. Se encuentran disponibles métricas de la cohorte como ingresos, ROI y tasas de conversión de eventos. La cohorte se puede desglosar más, con fines comparativos, en dimensiones como campaña o fuente de medios. El resultado se devuelve como un archivo CSV o JSON. Puedes usar los resultados para descubrir patrones o cambios en el rendimiento a lo largo de los ciclos de vida del usuario o de la campaña.

Consulta <Anchor target="_blank" href="https://www.appsflyer.com/blog/cohort-report-mobile-marketing-kpis/?utm_campaign=Blog%20Subscription%2003-2019&utm_source=hs_email&utm_medium=email&utm_content=76370689&_hsenc=p2ANqtz-8SX49xuEw2WX_Vrlh11_zxlDFvlfMpBzSQm1I-nFhc0WbZDf0ACC-VEi4qmKhesHCsUNdhU50Oinl-urwnGAOZMwwHSTp6UgdChCi7ARayJFUFTus&_hsmi=76370689">Casos de uso de la cohorte</Anchor>.

**Para utilizar la API de cohorte**:

1. ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) Consigue el <Anchor target="_blank" href="/marketers/es/docs/managing-appsflyer-tokens">token API</Anchor>. Un administrador debe recuperar el token.
2. Proporciona a tu desarrollador el token API que se usará en el encabezado de autenticación.
3. Otorga a tus desarrolladores los [parámetros](#filtering-and-grouping-parameters) que deben introducir cuando realicen la llamada a la API, como se describe en las secciones que siguen. Los parámetros determinan en qué se centra el reporte, cómo se organiza y proporcionan un marco temporal para el reporte.
4. Dile a tu desarrollador que siga las <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_app-id">instrucciones de la API maestra</Anchor> en el centro de desarrolladores.

<div id="filtering-and-grouping-parameters" />

<Accordion title="Parámetros de la API de cohorte">

Utiliza los siguientes parámetros de filtro para obtener los datos necesarios.

| Nombre de parámetro | Descripción | Obligatorio |
| --- | --- | --- |
| <span id="bearer"></span>portador | Token de la API utilizado en el encabezado de autenticación de la API. | Sí |
| <span id="cohort-_type"></span>cohort \_type | El tipo de atribución de cohorte (conversión) es uno de los siguientes: `user_acquisition`, `retargeting`, `unified`<ul><li>Unificado: combina el rendimiento de las campañas de retargeting y adquisición de usuarios.</li><li>Si un evento se atribuye tanto a campañas de retargeting como a campañas de adquisición de usuarios, solo se incluye el evento de retargeting en los KPIs devueltos, lo que significa que is\_primary=true.</li><li>Formato: cadena</li><li>Ejemplo: `"cohort_type": "user_acquisition"`</li></ul> | Sí |
| <span id="min_cohort_size"></span>min\_cohort\_size | El tamaño mínimo de la cohorte se utiliza para reducir el número de registros devueltos al excluir cohortes que tienen pocos usuarios. Esto significa que el KPI de "usuarios" tiene un valor igual o mayor al especificado.<ul><li>Formato: Entero</li><li>Valor mínimo permitido: 1. No envíes 0 (cero)</li><li>Predeterminado: 1</li><li>Ejemplo: `"min_cohort_size": 50`</li></ul> | No |
| <span id="from"></span>desde | Límite inferior del rango de fechas de atribución de LTV. La fecha más temprana admitida es 720 días antes de la fecha actual.<ul><li>Formato: Cadena aaaa-mm-dd</li><li>Ejemplo: `"from": "2020-01-02"`</li></ul> | Sí |
| <span id="to"></span>a | Límite superior del rango de fechas de atribución del LTV<ul><li>Número de días en el rango: 1-31 días</li><li>Para un solo día: `from` y `to` los valores son idénticos.</li><li>Formato: aaaa-mm-dd</li><li>Ejemplo: `"from": "2020-01-01", "to": 2020-01-31` son 31 días.</li></ul> | Sí |
| <span id="granularity"></span>granularidad | Granularidad horaria para las últimas 72 horas configurando `"granularity": "hour"` y configurando el rango `from` y `to` para incluir la hora del día.<ul><li>Formato: aaaa-mm-dd hh:mm:ss</li><li>Ejemplo:</li></ul>`"granularity": "hour", "from": "2021-12-01 14:00:00", "to": "2021-12-03 11:00:00",` | No |
| <span id="partial_data"></span>partial\_data | Para evitar distorsiones e interpretaciones erróneas de datos, la cohorte devuelve los datos de días completos. Sin embargo, los datos de días parciales pueden ser útiles.<br /><br />El número de días completos de la cohorte para una consulta se calcula como la diferencia entre la fecha de hoy y la fecha *a*.<ul><li>[Predeterminado] Si es falso, se devuelven días completos.</li><li>Si es verdadero, se devuelven hasta 180 días de cohorte, incluidos los días que tienen datos incompletos.</li><li>Formato: Booleano</li><li>Versión de interfaz de usuario de la plataforma: false</li></ul>**Ejemplo**: El 10 de mayo, el número de días completos de la cohorte para los usuarios que se convertirían durante el 1-30 de abril, es de 10.<ul><li>Si es falso [predeterminado], se devuelven los días 0-9 de la cohorte. Este es el número de días (10) entre la última fecha de conversión y hoy.</li><li>Si es verdadero, se devuelven los días 1-40 de la cohorte. Los días 11-40 contienen datos parciales y no se devuelven. Por ejemplo, desde el 20 de abril solo han transcurrido 20 días, y así sucesivamente.</li></ul>**Nota**: Los datos parciales solo se permiten cuando el tipo de agregación es acumulativo. | No |
| <span id="filters"></span>filtros | Permite filtrar los datos y el período de días devueltos. Selecciona los filtros de la [lista de dimensiones del filtro](/docs/cohort-api#list-of-group-by-and-filter-by-dimensions).<ul><li>Formato: Cadenas en un JSON anidado. Los valores deben estar en un array.</li><li>**Ejemplo de limitación a geolocalizaciones específicas:** `"filters": {"geo": ["US"]}` incluye solo los usuarios atribuidos a Estados Unidos.</li><li>**Ejemplo de período (cohorte) días** El filtro `period` establece los días para los cuales se devuelven las medidas. Los valores posibles son: 0-180.</li><li>Predeterminado: Si no se establece ningún filtro de período, se devuelven los días 0-30, 60, 90 y 180. [Ejemplo de filtro con período](/docs/cohort-api#using-period-filters)</li></ul> | No |
| <span id="groupings"></span>agrupación | <ul><li>Utiliza parámetros de agrupación para incluir columnas adicionales y hacer que tus reportes sean menos granulares.</li><li>Selecciona 1-7 agrupaciones de la [lista de dimensiones de agrupación](/docs/cohort-api#list-of-group-by-and-filter-by-dimensions).</li><li>Formato: Cadenas en un array</li><li>Ejemplo: `"groupings": ["af_ad", "c", "af_c_id", "af_prt"]`</li></ul> | Sí |
| <span id="kpis"></span>KPIs | Los KPIs son las métricas utilizadas para obtener insights sobre el comportamiento de tu aplicación. [Aprende a seleccionar y formatear KPIs](/docs/cohort-api#selecting-and-formatting-kpis) | Sí |
| <span id="preferred_currency"></span>preferred\_currency | Un parámetro que establece el formato de los KPI devueltos. [Aprende a formatear los KPIs](/docs/cohort-api#formateando-funciones-de-kpis) | No |
| <span id="preferred_timezone"></span>preferred\_timezone | Un parámetro que establece el formato de los KPI devueltos. [Aprende a formatear los KPIs](/docs/cohort-api#formateando-funciones-de-kpis) | No |
| <span id="aggregation_type"></span>aggregation\_type | Un parámetro que establece el formato de los KPI devueltos. [Aprende a formatear los KPIs](/docs/cohort-api#formateando-funciones-de-kpis) | Sí |
| <span id="per_user"></span>per\_user | Un parámetro que establece el formato de los KPI devueltos. [Aprende a formatear los KPIs](/docs/cohort-api#formateando-funciones-de-kpis) | No |

</Accordion>

<div id="selecting-and-formatting-kpis" />

<Accordion title="Selección y formateo de KPIs">

* La tabla enumera los KPIs disponibles y sus funciones asociadas. Cuando llamas a un KPI, se devuelven todas sus funciones.
* Los siguientes KPIs siempre devuelven: usuarios, eCPI y costo.
* Selecciona un KPI adicional por llamada.
* Por cada KPI solicitado, se devuelven todas las funciones.
* Formato: Cadenas en un array
  * Ejemplo A: `"kpis": ["sessions"]`
  * Ejemplo B: `"kpis": ["event_name"]`

<table><thead><tr><th> </th><th> </th><th colspan="5">Funciones</th></tr><tr><th rowspan="2">Predeterminado/Opcional </th><th rowspan="2">KPI (nombre de dimensiones) </th><th>Recuento</th><th>cvr (tasa de conversión)</th><th>Calificación</th><th>Suma</th><th>Usuarios únicos</th></tr><tr><th>Número</th><th>Porcentaje</th><th>Porcentaje</th><th>Número</th><th>Número</th></tr></thead><tbody><tr><td>Siempre</td><td>usuarios</td><td><span>SÍ</span></td><td>-</td><td>-</td><td>-</td><td>-</td></tr><tr><td>Siempre</td><td>eCPI</td><td>-</td><td>-</td><td>-</td><td><span>SÍ</span></td><td>-</td></tr><tr><td>Siempre</td><td>costo</td><td>-</td><td>-</td><td>-</td><td><span>SÍ</span></td><td>-</td></tr><tr><td>Opcional</td><td> <code>"event_name"</code>(4) </td><td><span>SÍ</span></td><td><span>SÍ</span></td><td>-</td><td><span>Sí (3)</span></td><td><span>SÍ</span></td></tr><tr><td>Opcional</td><td>ingresos</td><td><span>SÍ</span></td><td>-</td><td>-</td><td><span>SÍ</span></td><td>-</td></tr><tr><td>Opcional</td><td>roas</td><td>-</td><td>-</td><td><span>SÍ</span></td><td>-</td><td>-</td></tr><tr><td>Opcional</td><td>roi</td><td>-</td><td>-</td><td><span>SÍ</span></td><td>-</td><td>-</td></tr><tr><td>Opcional</td><td>sesiones</td><td><span>SÍ</span></td><td>-</td><td><span>SÍ</span></td><td>-</td><td><span>Sí(1)</span></td></tr><tr><td>Opcional</td><td>desinstalaciones (2)</td><td><span>SÍ</span></td><td>-</td><td><span>SÍ</span></td><td>-</td><td>-</td></tr><tr><td colspan="7"><p>(1) Las sesiones únicas regresan cuando <em>aggregation_type=on_day</em></p><p>(2) No disponible cuando cohort_type=unified </p><p>(3) La suma significa los ingresos totales generados por el evento. En el reporte, esto se denota por <code>sum_event_name"</code></p><p>Nota Nota Los nombres de los eventos diferencian mayúsculas y minúsculas.</p></td></tr></tbody></table>

#### Formateando funciones de KPIs

Los siguientes parámetros establecen el formato de los KPIs devueltos.

| Parámetro | Los valores | Obligatorio |
| --- | --- | --- |
| preferred\_currency | Divisa de los ingresos de KPIs<ul><li>Si es true, los se devuelven utilizando la <Anchor target="_blank" href="/marketers/es/docs/app-settings#localization-currency">divisa específica de la aplicación</Anchor> establecida en la plataforma.</li><li>[Predeterminado] Si es falso, los resultados se devuelven en USD.</li><li>Formato: Booleano</li><li>Versión de la interfaz de usuario de la plataforma: true</li></ul> | No |
| preferred\_timezone | **Zona horaria de rangos de datos**<ul><li>Si es true, las horas se expresan usando la <Anchor target="_blank" href="/marketers/es/docs/app-settings#localization-time-zone">zona horaria específica de la aplicación</Anchor> establecida en la plataforma.</li><li>[Predeterminado] Si es falso, las horas se expresan usando la zona horaria UTC.</li><li>Formato: Booleano</li><li>Versión de la interfaz de usuario de la plataforma: true</li></ul> | No |
| aggregation\_type | <ul><li>`Acumulado`</li><li>`on_day`</li></ul>`"aggregation_type": "cumulative"`<br /><br />`Formato: cadena` | Sí |
| per\_user | Divide la función de KPIs por el número de usuarios de la aplicación. Aplica únicamente a los KPIs relevantes.<ul><li>Si es true, los valores de KPIs se dividen por el número de usuarios en la cohorte.</li><li>Si es falso, los valores de KPIs no se dividen por el número de usuarios.</li><li>Formato: Booleano</li><li>Ejemplo si es verdadero: el ingreso total es de $1000 dólares, el número de usuarios de la aplicación es de $500, el valor devuelto es de $2 dólares.</li></ul> | No |

</Accordion>

<div id="list-of-group-by-and-filter-by-dimensions" />

<Accordion title="Agrupar por y filtrar dimensiones">

<table><thead><tr><th>Nombre de la dimensión </th><th>Valor de API de la dimensión</th><th>Agrupaciones</th><th>Filtros</th></tr></thead><tbody><tr><td>Anuncio</td><td>af_anuncio</td><td><span>SÍ</span></td><td><span>SÍ</span></td></tr><tr><td>ID del anuncio</td><td>id_del_anuncio_af</td><td><span>SÍ</span></td><td><span>SÍ</span></td></tr><tr><td>Campaña</td><td>C</td><td><span>SÍ</span></td><td><span>SÍ</span></td></tr><tr><td>ID de campaña</td><td>af_c_id</td><td><span>SÍ</span></td><td><span>SÍ</span></td></tr><tr><td>Canal</td><td>af_canal</td><td><span>SÍ</span></td><td><span>SÍ</span></td></tr><tr><td>Fuente de medios</td><td>PID</td><td><span>SÍ</span></td><td><span>SÍ</span></td></tr><tr><td>Subparámetro 1</td><td>af_sub1</td><td><span>SÍ</span></td><td><span>SÍ</span></td></tr><tr><td>Palabras clave</td><td>af_palabras_clave</td><td><span>SÍ</span></td><td><span>SÍ</span></td></tr><tr><td>Agencia</td><td>af_prt</td><td><span>SÍ</span></td><td><span>SÍ</span></td></tr><tr><td>Tipo de conversión (1) </td><td>cohort_type</td><td><span>SÍ</span></td><td><span>SÍ</span></td></tr><tr><td>ID del sitio</td><td>id_sitio</td><td><span>SÍ</span></td><td><span>SÍ</span></td></tr><tr><td>Tipo de ingresos (2)</td><td>tipo_de_ingresos</td><td><span>. </span></td><td><span>SÍ</span></td></tr><tr><td>Tipo de toque atribuido (3)</td><td>tipo_táctil_atribuido</td><td><span>SÍ</span></td><td><span>SÍ</span></td></tr><tr><td>Conjunto de anuncios</td><td>af_conjunto de anuncios</td><td><span>SÍ</span></td><td><span>SÍ</span></td></tr><tr><td>ID del adset</td><td>af_adset_id</td><td><span>SÍ</span></td><td><span>SÍ</span></td></tr><tr><td>País</td><td>geolocalización</td><td><span>SÍ</span></td><td><span>SÍ</span></td></tr><tr><td>Fecha (fecha de instalación/reatribución/re-engagement en el contexto del cohort_type seleccionado) </td><td>fecha</td><td><span>SÍ</span></td><td><span>. </span></td></tr><tr><td>Periodo</td><td><p>period</p><p><a href="./cohort-api#using-period-filters">Explicación detallada</a></p></td><td><span>.</span></td><td><span>SÍ</span></td></tr><tr><td colspan="4"><p>Notas: </p><p>Opciones de dimensión:</p><p>(1) Tipo de conversión:  <code>user_acquisition</code>, <code>retargeting</code>(<code>re-engagement</code> y <code>re-attribution</code>), <code>unified</code></p><ul><li>Al exportar:<ul><li> <code>re-engagement</code> se mostrará como <code>retargeting</code> </li><li> <code>re-attribution</code> se mostrará como <code>reattr</code> </li></ul></li></ul><p>(2) Tipo de ingresos: <code>regular</code>, <code>ad_monetization</code><span></span></p><p>(3) Tipo de toque de atribución: <code>click</code>, <code>impression</code>, <code>TV</code>, <code>pre-installed</code></p></td></tr></tbody></table>

</Accordion>

## Información adicional

<div id="using-period-filters" />

<Accordion title="Uso de filtros de período">

El período se refiere al día posterior a la atribución, donde el período 0 es el día de atribución. Por ejemplo, un usuario instala la aplicación el 1 de enero. Este es el día de la atribución. Una compra realizada en el período 0 significa que se realizó el 1 de enero. Una compra realizada en el período 3 significa que se realizó el 4 de enero. De manera similar, un usuario que instala el 11 de enero, este es el período 0. Una compra realizada el 14 de enero sería el período 3.

Si el rango de fechas de tu reporte es del 1 al 11 de enero, se incluyen en el reporte los usuarios que atribuyeron (instalaron) durante este período. No se incluyen otros datos.

* El valor del período puede ser uno o más de los siguientes 0-180. Por ejemplo: 0, 1, 2, 30, 180.
* Si no se especifica ningún período, se devuelven los valores predeterminados 0, 1, 2 y así sucesivamente hasta 30, 60, 90 y 180.

> 📄 **Ejemplo de filtro de período**
>
> * Este ejemplo contiene los parámetros de la consulta JSON, el raw data y el archivo CSV resultante.
> * La consulta *filtra los períodos* 0, 1 y 2 y el KPI seleccionado es *ingresos*.
> * La consulta especifica el tipo de agregación como "cumulativa". Cambia a "on\_day" si deseas datos del mismo día.
> * Como resultado, los datos devueltos contienen:
>   * Las medidas de usuarios, costo y eCPI que siempre se devuelven
>   * Medidas de ingresos consistentes en suma y recuento para cada período, es decir, los períodos 0, 1 y 2.
>
> **Query**
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
>         "ingresos"
>     ]
> }
> ```
>
> **Datos sin procesar**
>
> **![mceclip1.png](https://files.readme.io/846aade481d3b5fa72536817533bc3edad721f1ce6015edcb48bd500461342b9-32131110606865.png)**
>
> **Resultados**
>
> ![mceclip0.png](https://files.readme.io/c284e5133e4e811b9416c850e399ddefb3c5bfcfcf879f469556b7a6bc0062c6-32131110607249.png)

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Rasgos y limitaciones">

| Caducado | Observaciones |
| --- | --- |
| Acceso a la ad network | No |
| Acceso a la agencia | No |
| Zona horaria específica de la aplicación | Sí |
| Moneda específica de la aplicación | Sí |
| Limitaciones de tamaño | Ninguno |
| Limitación de tasa | <ul><li>Límite de tasa de llamadas a la API: 60 llamadas por minuto y 50.000 llamadas al día por cuenta</li><li>Las consultas devuelven hasta 30.000 filas</li></ul> |
| Datos orgánicos | Disponible |
| Datos no orgánicos | Disponible |
| Limitación de datos de costos | <ul><li>Los datos de costos son solo para campañas con al menos 1 instalación registrada.</li><li>AppsFlyer no reporta los datos de costos de las palabras clave que contienen letras mayúsculas en el reporte de cohortes o la API de cohortes.</li><li>No se pueden combinar algunas combinaciones de agrupamientos con el costo. Por ejemplo, Meta Ads puede tener agrupamientos por geolocalización o canales, pero no ambos. La combinación exacta de agrupaciones depende de la ad network.</li></ul> |
| Actualización de los datos | La actualización de los datos depende de [partial\_data](/docs/cohort-api#partial_data) de la siguiente manera:<ul><li>[Predeterminado] Si es falso, <Anchor target="_blank" href="/marketers/es/docs/about-data-freshness-and-timezone-support#daily">a diario</Anchor>.</li><li>Si es verdadero, <Anchor target="_blank" href="/marketers/es/docs/about-data-freshness-and-timezone-support#continuous-aka-realtime">es continuo (en tiempo real)</Anchor>.</li><li>Las métricas de costos y desinstalaciones se actualizan diariamente en todas las instancias.</li></ul> |
| Datos históricos | Cohortes diarias: 2 años |
| Acceso de usuario a la cuenta | El token de autorización está disponible para los usuarios administradores en el dashboard. |
| Ingresos de anuncios | Para los eventos af\_ad\_revenue, la métrica de usuarios únicos no está disponible cuando el tipo de agregación es:<ul><li>Acumulativa.</li><li>"On day" para fechas entre el 5 de octubre de 2022 y el 16 de febrero de 2023.</li></ul> |
| Agrupaciones semanales y mensuales | Las agrupaciones de dimensiones semanales y mensuales no están disponibles con la API de cohortes. Utiliza el dashboard de cohortes. |
| Período de API de cohorte | <ul><li>El período de conversión se denomina 0 (Hora 0 o Día 0). Al siguiente período posterior a la conversión se le denomina 1 (Hora 1 o Día 1), y así sucesivamente.</li><li>En AppsFlyer un período de cohorte no toma en cuenta la marca de tiempo de instalación específica. Más bien, las horas de cohorte se redondean a la hora más cercana y los días de cohorte se basan en el día de calendario. Esto puede causar discrepancias al comparar los datos de cohortes de AppsFlyer con los datos de cohorte de otras redes, donde todos los períodos de cohorte están determinados por la marca de tiempo de instalación específica (es decir, una hora es 60 minutos después de la instalación, un día es el período posterior a la instalación de 24 horas después de la marca de tiempo de instalación).</li></ul> |
| Fechas | <ul><li>Las fechas o rangos de fechas se refieren a fechas de lifetime value (LTV), es decir, la fecha en que el usuario se atribuyó (convirtió) y no la fecha de la actividad en sí.</li><li>La fecha más antigua admitida: 730 días antes de la fecha actual. Es decir, 2 años.</li><li>Rango máximo de consulta: 60 días.</li></ul> |
| Reinstalaciones | <ul><li>Si los eventos post-reinstalación son considerados orgánicos no atribuidos:<ul><li>Se incluirán solo a partir del 26 de mayo de 2024. <Anchor target="_blank" href="/marketers/es/docs/bulletin-cohort-data-includes-unattributed-sessions-and-events">Más información</Anchor></li><li>El tiempo de instalación se basa en el campo <Anchor target="_blank" href="/marketers/es/docs/raw-data-field-dictionary#device-info::dfd9504e">device\_download\_time</Anchor>.</li><li>No se cuentan para las mediciones de usuarios únicos y de retención.</li></ul></li><li>Si los eventos post-reinstalación se atribuyen a la primera instalación, siempre se incluyen. <Anchor target="_blank" href="/marketers/es/docs/unique-users">Saber más</Anchor></li></ul> |
| API de cohorte para partners | El acceso a la API de cohorte para partners de marketing se está descontinuando a partir del 15 de septiembre de 2024. Se anima a los partners de marketing a <Anchor target="_blank" href="/partners/es/docs/data-locker-reports-for-api-partners">habilitar Data Locker</Anchor> para garantizar el acceso continuo a los datos de los clientes. |

</Accordion>

<div data-zendesk-anchors="cohort-reporting-api=api-de-cohorte 01H7WFZR41YAQX4MFPBMJD1MBP=api-de-cohorte 01H7WFZR42H3CA0CSB4E3XED3H=filtering-and-grouping-parameters 01H7WFZR42XV4JY46GY11KT3CF=selecting-and-formatting-kpis presentation-of-kpi-functions=formateando-funciones-de-kpis 01H7WFZR43HFF65TSWG1AN0JTB=formateando-funciones-de-kpis 01H7WFZR43BJ8E6KVHSGV4CDDP=list-of-group-by-and-filter-by-dimensions additional-information=informaci%C3%B3n-adicional h_01HMY09W324E54VPZWPJVS2KB8=informaci%C3%B3n-adicional 01H7WFZR440NTXWWQ2T4P2ANWK=using-period-filters 01H7WFZR44RCXA56CXSCEZ0KXH=ejemplo-de-filtro-de-per%C3%ADodo 01H7WFZR45VC96KYW1W9A8PBFT=traits-and-limitations" />
