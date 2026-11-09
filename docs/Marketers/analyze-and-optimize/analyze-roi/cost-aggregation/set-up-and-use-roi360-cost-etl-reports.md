---
title: Configurar y utilizar reportes de Cost ETL de ROI360
metadata:
  keywords:
    - Campaign
    - eCPI
    - clicks
    - Impressions
    - ROI
    - cost
    - Advertisers
    - Premium
    - Premium Feature
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - ROI360
  created_at: '2020-05-17T15:36:41Z'
  edited_at: '2026-08-22T00:01:18Z'
  id: 360008849238
  locale: es
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/es/articles/360008849238
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En resumen:** Cost ETL, parte de ROI360 de AppsFlyer, proporciona a los anunciantes datos de costos de campaña con la mejor granularidad disponible por fuente de medios. Los datos, actualizados hasta 4 veces al día, se entregan a tu servicio en la nube listos para ser cargados en los sistemas BI de los anunciantes.

<Image align="center" alt="5896_CostETL_graphic__2_.png" src="https://files.readme.io/3c9b8721fa4aba170c1ed7b7b365b4a5fe1cd74080469b3020d395352cede674-11178721788817.png" />

Cost ETL, parte de ROI360 de AppsFlyer, proporciona a los anunciantes datos de costos de campaña con la mejor granularidad disponible por fuente de medios. Hasta cuatro veces al día, los datos se actualizan y se entregan a su servicio en la nube Data Locker, listos para ser cargados en los sistemas BI de los anunciantes.

Los anunciantes pueden enviar reportes a múltiples destinos en la nube a la vez sin esfuerzo. Esto empodera a los equipos al hacer la transición de un servicio en la nube a otro, ya que los datos son accesibles en múltiples servicios simultáneamente.

Los reportes de Cost ETL incluyen datos de costo vinculados a la atribución de AppsFlyer, incluidas métricas de atribución como instalaciones, re-attributions y re-engagements.

<div id="four-types-of-cost-etl-reports" />

## Sobre Cost ETL

AppsFlyer ofrece cuatro tipos de reportes de Cost ETL para cubrir distintas necesidades de análisis.

* **Resumen**: Reporte general que proporciona datos de alto nivel para un consumo más fácil y rápido. Habilitado por defecto. Recomendado para analizar métricas de costo y rendimiento a un nivel general.
* **Reporte de geolocalización:** (opcional) Datos de costo desglosados por país (códigos de 2 letras), como US, CA o FR. Recomendado para el análisis de rendimiento y costo a nivel de geolocalización.
* **Canal**: Datos desglosados por canal para todas las fuentes de medios contenidas en dicho reporte. Por ejemplo, en el caso de Google Ads, los datos se desglosan por YouTube, Shopping, SERP y Gmail. Ideal para el análisis de rendimiento y costo a nivel de canal.  
  <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRqyHRTiLq8KUtELHqdaF6yVTfNE22X5UmUqXX89oOK5ZpS6lksXD0401G8MFmsaEzg2Csvf-d3y08Z/pub?single=true&output=csv">Ver archivo de muestra</Anchor>
* **Reporte All Cost**: una vista completa de los datos de costo móvil y no móvil, obtenidos directamente de las ad network, sin datos de atribución. Actualmente cubre Google Ads, Meta Ads y TikTok.  
  <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vSdjA_4tdWBxxbI_ZM7mcZzCKhrWxQ-0m1DPIig-gMTpnDyLBDE_RGJ5zskNFpbsg/pub?gid=559626950&single=true&output=csv">Ver archivo de muestra</Anchor>

  <div id="note" />

  > 📘 **Nota:**
  >
  > Para empezar a recibir datos de Google Ads y Meta Ads en el reporte All Cost, ponte en contacto con tu representante de AppsFlyer.


<div id="cost-etl-report-types-overview-table" />

### Tabla con el resumen de los tipos de reporte de Cost ETL

<table><thead><tr><th> </th><th>Característica</th><th>Geografía</th><th>Ejemplo</th><th><strong>Reporte All Cost</strong></th></tr></thead><tbody><tr><td><strong>Cómo obtener el reporte</strong></td><td>Activa Costo ETL. El reporte Summary está seleccionado por defecto.</td><td>Activa Costo ETL y selecciona el reporte de geolocalización.</td><td>Activa Costo ETL y selecciona el reporte de canal.</td><td>Activa Costo ETL y selecciona el reporte de <strong>geolocalización</strong>. (El reporte All Cost no tiene un selector específico en la página de Costo ETL)</td></tr><tr><td><strong>Dónde encontrar el reporte</strong></td><td>Depende del servicio de conector en la nube que elijas. Puede ser una carpeta (Summary) o una tabla específica.</td><td>Depende del servicio de conector en la nube que elijas. Puede ser una carpeta (geolocalización) o una tabla específica.</td><td>Depende del servicio de conector en la nube que elijas. Puede ser una carpeta (canal) o una tabla específica.</td><td>Depende del servicio de conector en la nube que elijas. Puede ser una carpeta (Costo total) o una tabla específica.</td></tr><tr><td><strong>Cobertura del tipo de costo</strong></td><td><p>Costo móvil: sin limitaciones.<br/>Costo de CTV y web: limitado a:<br/> </p><ol><li>Campañas con al menos una conversión</li><li>La fuente del costo es InCost API, Cost Import o CPI</li></ol></td><td>Igual que en Resumen.</td><td>Igual que en Resumen.</td><td>Costo de móvil, web, CTV, PC y consola de Google Ads, Meta Ads y TikTok.</td></tr><tr><td><strong>Cadena</strong></td><td>Ninguna limitación</td><td>Ninguna limitación</td><td>Ninguna limitación</td><td><ul><li> <strong>TikTok:</strong> Los datos se añaden automáticamente.</li><li> <strong>Google y Meta:</strong> Ponte en contacto con tu CSM para habilitarlo.</li></ul></td></tr><tr><td><strong>Granularidad del esquema</strong></td><td>Se basa en la configuración del cliente en los ajustes de Cost ETL.</td><td><p>Se basa en la configuración del cliente en los ajustes de Cost ETL.</p><p><br/>En Meta, la dimensión de canal no tiene valores.</p></td><td><p>Se basa en la configuración del cliente en los ajustes de Cost ETL.</p><p><br/>En Meta, la dimensión de geolocalización no tiene valor.</p></td><td><p>Se basa en la configuración del cliente en los ajustes de Cost ETL.</p><p>En Meta, la dimensión de canal no es compatible.<br/><strong>Plataforma:</strong> Una nueva dimensión de la ad network que indica dónde se ejecuta la campaña (p. ej., móvil, escritorio o tablet).</p></td></tr><tr><td><strong>Datos de atribución</strong></td><td>Compatible</td><td>Compatible</td><td>Compatible</td><td><p>No está soportado.</p><p><br/>Los valores de las métricas de atribución se muestran como cero (0), si el cliente los configura para que formen parte del esquema de Cost ETL.</p></td></tr><tr><td><strong>Entero</strong></td><td>Si la ad network no es compatible con la granularidad de ID de aplicación, el ID de aplicación se extrae de los Datos de atribución.</td><td>Igual que en el resumen.</td><td>Igual que en el resumen.</td><td><p>Monto de la oferta original</p><p><br/>Si no se reporta el ID de la App, el valor será desconocido.</p></td></tr><tr><td><strong>Fuente de costos</strong></td><td>Integración de API (Costo + InCost), importación de costos, CPI</td><td>Igual que en el resumen.</td><td>Igual que en el resumen.</td><td>Solo integración de API.</td></tr><tr><td><strong>CNC</strong></td><td>Compatible</td><td>Compatible</td><td>Compatible</td><td>No está soportado.</td></tr><tr><td><strong>Datos de la agencia</strong></td><td>Compatible</td><td>Compatible</td><td>Compatible</td><td><ul><li> <strong>Facebook and Meta:</strong> No compatible con soporte.</li><li> <strong>TikTok:</strong> Compatible solo con campañas con ID de App en AppsFlyer.</li></ul></td></tr><tr><td><strong>Tarifa de la agencia</strong></td><td>Compatible</td><td>Compatible</td><td>Compatible</td><td>No está soportado. El valor siempre es 0.</td></tr><tr><td><strong>Actualización</strong></td><td colspan="4">Los datos se recopilan de la ad network 6 veces al día.<br/>Los reportes se pueden entregar hasta 4 veces al día (según la configuración del cliente).</td></tr></tbody></table>

<div id="report-details" />

## Detalles del reporte

<div id="data-freshness" />

<Accordion title="Actualización de datos">

Los datos de costos de la campaña se registran:

* En tu servicio en la nube o bucket para ver, transferir y cargar datos de costos en tus sistemas.
* Para todas las aplicaciones que elijas incluir en Cost ETL, por día, por versión.
* Hasta 4 veces al día (frescura de datos: <Anchor target="_blank" href="/marketers/es/docs/about-data-freshness-and-timezone-support#intraday-during-the-day">a lo largo del día)</Anchor>.
* Para el día actual y los 6 días anteriores (denominados 7 días en este artículo), así como los días 14, 29 y 88. Ten esto en cuenta en tu proceso de carga de datos.
  * Ejemplo: Para la fecha 14 de octubre de 2024, el archivo contiene datos del 14 de octubre (el día actual), 13 de octubre (1 día atrás), 12 de octubre (2 días atrás), 11 de octubre (3 días atrás), 10 de octubre (4 días atrás), 9 de octubre (5 días atrás), 8 de octubre (6 días atrás), 30 de septiembre (14 días atrás), 15 de septiembre (29 días atrás) y 18 de julio (88 días atrás).
  * Los datos retroactivos permiten actualizaciones y correcciones en los reportes de datos de costos.
* Para obtener un costo que coincida con la atribución, el clic o la impresión.  
  **Nota**:
  * Los datos de los últimos 7 días provienen nuevamente de las fuentes de medios. Se reprocesan los datos de los días 14, 29 y 88.
  * Solo los datos de costos se actualizan retroactivamente; los datos de atribución no.

</Accordion>

<div id="directory-and-filename-structure" />

<Accordion title="Estructura de directorios y nombres de archivos">

Los datos escritos en el servicio en la nube o bucket tienen la estructura de directorio y archivo descrita:

* Cuando la Cost ETL completa la escritura en un directorio, se establece un indicador creando un archivo *success*. Esta es siempre la marca de tiempo más reciente en el directorio.
* El número de carpetas/archivos es el siguiente:
  * Resumen: Hasta 4 carpetas de versión por día.
    * Cada carpeta por lotes contiene archivos parquet con 7 días de datos.
  * Cadena
    * Cada carpeta por lotes contiene archivos parquet con datos con numeración desde 1.
  * [Beta cerrada] Todos los costos: Basado en la dimensión geográfica, contiene hasta 4 archivos por día.

<div id="data-locker-connection-directory-structure" />

#### Estructura de directorio de conexión de Data Locker

`///t=/dt=/v=<1/2/3/4>/`

| **Variable** | **Contenido** |
| --- | --- |
| client-bucket | Nombre del bucket según lo configurado en el servicio en la nube |
| DL-generated-partition | Partición generada, única por cliente |
| connection-name | Nombre de la conexión según se definió durante la configuración de Data Locker |
| t | El nombre del reporte específico. Elige entre:<ul><li>cost\_etl\_summary</li><li>cost\_etl\_geo</li><li>cost\_etl\_channel</li><li>[Beta cerrada] cost\_etl\_all\_cost\_geo</li></ul> |
| dt | <ul><li>La fecha del reporte, es decir, la fecha en que se envió el reporte.</li><li>AAAA-MM-DD</li></ul> |
| v | <ul><li>La versión cronológica del reporte por día (hasta 4 reportes diarios posibles)</li><li>Número entero entre 1-4</li></ul> |
| Número de archivo parquet | <ul><li>Numerados a partir de 00000</li><li>Ejemplo: `part-`</li></ul> |

<div id="cost-etl-connection-directory-structure" />

#### Estructura del directorio de conexión Cost ETL

`<advertiser bucket name>/cost_etl/version/dt=<yyyy-mm-dd>/b=<n>/<dimension>/<file name/<parquet file number>`

| **Variable** | **Contenido** |
| --- | --- |
| advertiser\_bucket\_name | Como se define en la configuración de la Cost ETL: af-xpend-cost-etl-&lt;af-account-id>-[sufijo del nombre de bucket] |
| cost\_etl | Siempre cost\_etl |
| version | Versión de la Cost ETL |
| fecha | Fecha del costo<br /><br />Formato: aaaa-mm-dd |
| batch | Número: 1-4 |
| dimension | Dimensión de datos:<ul><li>geolocalización</li><li>channel</li></ul> |
| file\_name | <ul><li>summary</li><li>all-cost</li></ul> |
| Número de archivo parquet | <ul><li>Numerados a partir de 00000</li><li>Ejemplo: `part-`</li></ul> |

Ejemplo: **Para la primera extracción de datos del 23 de junio de 2020, la estructura de directorios y nombre de archivo es la siguiente:**

</Accordion>

<div id="file-fields" />

<Accordion title="Campos de archivo">

<div id="fieldsdimensions" />

#### Campos/dimensiones

| **Campo** | **Observaciones** | **Siempre completado** | **Formato** | **Incluido en archivo de resumen** |
| --- | --- | --- | --- | --- |
| anuncio | Componente de la jerarquía de publicidad | No | Cadena | - |
| ad\_account | <ul><li>Cuenta publicitaria de la que se extrajeron los datos de costos</li><li>Relevante para redes donde la conexión se realiza mediante oAuth (inicio de sesión con tus credenciales), por ejemplo en Google o Meta Ads</li></ul> | No | Cadena | - |
| id\_adset | Componente de la jerarquía de publicidad | No | Cadena | - |
| conjunto de anuncios | Componente de la jerarquía de publicidad | No | Cadena | - |
| id\_anuncio | Componente de la jerarquía de publicidad | No | Cadena | - |
| af\_bid\_strategy | <Anchor target="_blank" href="/marketers/es/docs/campaign-properties-in-cost-etl-reports">Estrategia de oferta mapeada y normalizada por AppsFlyer. Componente de propiedades de campaña.</Anchor> <Anchor target="_blank" href="/marketers/es/docs/campaign-properties-in-cost-etl-reports">Saber más</Anchor> | No | Cadena | - |
| af\_modelo\_de\_coste | Modelo de costos mapeado y normalizado por AppsFlyer. Componente de propiedades de campaña. <Anchor target="_blank" href="/marketers/es/docs/campaign-properties-in-cost-etl-reports">Saber más</Anchor> | No | Cadena | - |
| agencia | Agencia responsable de colocar el anuncio | No | Cadena | - |
| id\_aplicación | ID de aplicación en la plataforma AppsFlyer | Sí | Cadena | ✓ |
| bid\_amount | Componente de propiedades de campaña. <Anchor target="_blank" href="/marketers/es/docs/campaign-properties-in-cost-etl-reports">Saber más</Anchor> | No | Entero | - |
| bid\_strategy | Componente de propiedades de campaña. <Anchor target="_blank" href="/marketers/es/docs/campaign-properties-in-cost-etl-reports">Saber más</Anchor> | No | Cadena | - |
| campaña única | Componente de la jerarquía de publicidad | No | Cadena | - |
| id\_campaña | Componente de la jerarquía de publicidad | No | Cadena | - |
| campaign\_objective | Componente de propiedades de campaña. <Anchor target="_blank" href="/marketers/es/docs/campaign-properties-in-cost-etl-reports">Saber más</Anchor> | No | Cadena | - |
| channel | Dimensión en la jerarquía de publicidad | No | Cadena | - |
| cost\_model | Componente de propiedades de campaña. <Anchor target="_blank" href="/marketers/es/docs/campaign-properties-in-cost-etl-reports">Saber más</Anchor> | No | Cadena | - |
| moneda | Moneda del gasto del anunciante según lo definido para la aplicación en AppsFlyer | Sí | Cadena de 3 caracteres compatible con ISO-4217 | ✓ |
| fecha | Fecha del costo incurrido reportada por la fuente de medios | Sí | Cadena aaaa-mm-dd | ✓ |
| geolocalización | Dimensión en la jerarquía de publicidad | No | Cadena de 2 caracteres compatible con ISO-3166 | ✓ |
| keyword\_id | ID de los términos de palabras clave de ASA | Sí | Cadena | - |
| keyword\_term | Palabra(s) utilizadas por el usuario para la búsqueda online | Sí | Cadena | - |
| fuente\_de\_medios | Fuente de medios responsable de mostrar el anuncio | Sí | Cadena | ✓ |
| Monto de la oferta original | Componente de propiedades de campaña. <Anchor target="_blank" href="/marketers/es/docs/campaign-properties-in-cost-etl-reports">Saber más</Anchor> | No | Entero | - |
| original\_currency | Moneda del costo según lo reportado por la red antes de cualquier conversión | No | Cadena de 3 caracteres compatible con ISO-4217 | - |
| os | Sistema operativo del dispositivo. Posibles valores:<ul><li>Android</li><li>Windows Phone</li><li>ios</li></ul> | Sí | Cadena | - |
| Identificador de origen | La plataforma utilizada para ejecutar la campaña (móvil, tablet, escritorio y CTV) | Solo en el reporte de costos completo | Cadena | - |
| id\_sitio | ID del publisher | No | Cadena | - |
| Zona horaria | <ul><li>Zona horaria de los datos tal como se almacenan en AppsFlyer</li><li>A veces, las redes reportan datos en una zona horaria diferente a la definida en AppsFlyer. Este dato ayuda a explicar las discrepancias de costos entre AppsFlyer y las redes.</li></ul> | Sí | Cadena | - |

<div id="metrics" />

#### Métricas

| **Campo** | **Observaciones** | **Siempre completado** | **Formato** | **Incluido en archivo de resumen** |
| --- | --- | --- | --- | --- |
| ccvr | <ul><li>Costo por conversión</li><li>Fórmula: Costo / (instalaciones + reatribuciones + reengagements)</li></ul> |  | Entero | - |
| Cadena | <ul><li>Contado por AppsFlyer.</li><li>Incluye tanto UA como retargeting.</li><li>Los <Anchor target="_blank" href="/marketers/es/docs/about-enriched-engagement-types#engaged_click">engaged clicks</Anchor> se restan del número total de clics.</li></ul> |  | Entero | ✓ |
| clicks\_discrepancy | <ul><li>Diferencia entre el recuento de la ad network y de AppsFlyer</li><li>Ignora esta métrica si:<ul><li>No hay coincidencia entre costo y atribución.</li><li>La ad network no admite <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">clics reportados.</Anchor></li></ul></li></ul> |  | Entero | - |
| Cadena | Monto del gasto (incluidos los honorarios de la agencia cuando corresponda) |  | Valor | ✓ |
| cost\_without\_fees | Costo menos los honorarios de la agencia. Contado por AppsFlyer | Sí | Entero | - |
| cpi | <ul><li>Contado por AppsFlyer</li><li>Fórmula: Costo / instalaciones</li></ul> |  | Entero | - |
| Cadena | <ul><li>Tasa de conversión. Contado por AppsFlyer</li><li>Fórmula: Clic / impresiones</li></ul> | No | Entero | - |
| CVR | <ul><li>tasa de conversión. Contado por AppsFlyer</li><li>Fórmula: Instalación / clics</li></ul> |  | Entero | - |
| cvvr | <ul><li>Tasa de visualización de video finalizada. Contado por AppsFlyer</li><li>Fórmula: Visualizaciones del video / impresiones</li></ul> |  | Entero | - |
| ecpc | <ul><li>Contado por AppsFlyer</li><li>Fórmula: Costo / Clics</li></ul> |  | Entero | - |
| ecpm | <ul><li>Contado por AppsFlyer</li><li>Fórmula: (Costo / Impresiones) * 1000</li></ul> |  | Entero | - |
| fees | Honorarios que cobra una agencia además del costo publicitario habitual. Contado por AppsFlyer | Sí | Entero | - |
| Validación de compra de AppsFlyer | <ul><li>Contado por AppsFlyer.</li><li>Incluye tanto UA como retargeting.</li><li>Las <Anchor target="_blank" href="/marketers/es/docs/about-enriched-engagement-types#engaged_view">engaged views</Anchor> se restan del número total de impresiones.</li></ul> | Sí.<br /><br />Si no hay ningún valor disponible para una métrica en particular, se completa con 0. | Entero | ✓ |
| impressions\_discrepancy | <ul><li>Diferencia entre el recuento de la ad network y de AppsFlyer</li><li>Ignora esta métrica si:<ul><li>No hay coincidencia entre costo y atribución.</li><li>La ad network no admite <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">impresiones reportadas.</Anchor></li></ul></li></ul> |  | Entero | - |
| Cadena | Contado por AppsFlyer |  | Entero | ✓ |
| installs\_discrepancy | <ul><li>Diferencia entre el recuento de la ad network y de AppsFlyer</li><li>Ignora esta métrica si:<ul><li>No hay coincidencia entre costo y atribución.</li><li>La ad network no admite <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">conversiones reportadas.</Anchor></li></ul></li></ul> |  | Entero | - |
| original\_cost | Costo reportado por la red, en la moneda reportada por la red antes de cualquier conversión de moneda (con los honorarios de la agencia calculados por AppsFlyer agregados cuando corresponda) |  | Valor | - |
| original\_cost\_without\_fees | Costo original según lo reportado por la ad network, sin los honorarios de la agencia | Sí | Entero | - |
| re\_attributions | Contado por AppsFlyer |  | Entero | ✓ |
| re\_engagements | Contado por AppsFlyer |  | Entero | ✓ |
| reported\_clicks | Contado por la fuente de medios |  | Entero | ✓ |
| reported\_conversions | Contado por la fuente de medios |  | Entero |  |
| reported\_cvr | <ul><li>Tasa de conversión reportada</li><li>Fórmula: Conversiones reportadas / clics reportados</li></ul> |  | Entero | - |
| reported\_impressions | Contado por la fuente de medios |  | Entero | ✓ |
| video\_25p\_views | Video reproducido al 25%. Reportado por la ad network |  | Entero | - |
| video\_50p\_views | Video reproducido al 50%. Reportado por la ad network |  | Entero | - |
| video\_75p\_views | Video reproducido al 75%. Reportado por la ad network |  | Entero | - |
| video\_completions | Reportado por la ad network |  | Entero | - |

</Accordion>

<div id="procedures" />

## Procedimientos

<div id="set-up-cost-etl" />

<Accordion title="Configurar Cost ETL">

Este procedimiento de configuración debe ser realizado por un usuario administrador.

**Antes de empezar**:

La configuración de Cost ETL requiere:

* Un servicio en la nube configurado con permiso para que AppsFlyer escriba datos en él. Esto significa que necesitas configurar uno o más de los siguientes servicios en la nube:
  * Bucket de <Anchor target="_blank" href="/marketers/es/docs/data-locker-cloud-service-setup#aws-storage">AWS</Anchor>
  * Bucket de <Anchor target="_blank" href="/marketers/es/docs/data-locker-cloud-service-setup#gcs-storage">GCS</Anchor>
  * [Beta] <Anchor target="_blank" href="/marketers/es/docs/data-locker-cloud-service-setup#beta--azure-storage">Azure</Anchor> Blob
  * [Beta] Bucket de <Anchor target="_blank" href="/marketers/es/docs/data-locker-cloud-service-setup#yandex">Yandex</Anchor>
  * Almacén de datos de <Anchor target="_blank" href="/marketers/es/docs/data-locker-cloud-service-setup#bigquery">BigQuery</Anchor>
  * Almacén de <Anchor target="_blank" href="/marketers/es/docs/data-locker-cloud-service-setup#snowflake">Snowflake</Anchor>
* Privilegios de administrador de AppsFlyer y acceso a la interfaz de usuario de AppsFlyer para completar la configuración de Cost ETL.

[**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)**](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) **Para configurar Cost ETL:**

1. En AppsFlyer, desde el menú lateral, ve a **Exportar** > **Cost ETL**.
2. Selecciona o configura una **conexión de datos**:
   * Si ya tienes conexiones de datos configuradas, en el menú desplegable de **Conexión**, selecciona las que deseas para Cost ETL.  

     <Image align="center" alt="" src="https://files.readme.io/483cc971805232bca48f4da7f4ee6bd98e43cb3f8e70cfb79fd158746b889e35-31233921523601.png" width="700px" />
   * Si aún no tienes una conexión de datos, haz clic en **+ New connection in Data Locker** y crea una conexión allí:  
     <Image align="center" alt="" src="https://files.readme.io/066e0829340c34f1f01fe3f637bc75b4a414cebeecb5257b01df877e6e5da7e3-31233961342865.png" width="700px" />
     1. Asigna un nombre a tu conexión.  

        <Image align="center" alt="" src="https://files.readme.io/734060321cf14a4ebbce66fe2abc71ff299218f7c52cb64dc5b8e71c42d3632d-31233921530001.png" width="2100px" />
     2. **Selecciona un destino de datos de servicio en la nube**. Realiza una de las siguientes acciones:
        * Entero  
          <Image align="center" alt="" src="https://files.readme.io/1a78090f00407d44a5b74f3cb3b94e3a28064bc9b991b1cecf506fa0b9053842-31233961351441.png" width="945px" />
          1. Introduce el nombre de tu bucket AWS S3. El prefijo `af-` es obligatorio, y debe introducirse manualmente.
          2. Haz clic en **Probar conexión**.
          3. Verifica que no se muestre ningún mensaje de error que indique que la ruta del bucket es inválida.
          4. Selecciona si deseas **hacer que esta conexión sea compatible con Adobe Experience Platform**.
          5. Haz clic en **Guardar**.
          6. En la configuración de Cost ETL, en el menú desplegable de **Conexión**, selecciona el servicio en la nube que has creado.
        * Selecciona **GCS**.  

          <Image align="center" alt="" src="https://files.readme.io/6da526f43131887270136e9fcfa9434ad88c2ce8cebdb896c07dac4a0652d683-31233921536913.png" width="944px" />
          1. Introduce el **nombre de tu bucket de GCS**.
          2. Haz clic en **Probar conexión**.
          3. Verifica que no se muestre ningún mensaje de error que indique que la ruta del bucket es inválida.
          4. Selecciona si deseas **hacer que esta conexión sea compatible con Adobe Experience Platform**.
          5. Haz clic en **Guardar**.
          6. En la configuración de Cost ETL, en el menú desplegable de **Conexión**, selecciona el servicio en la nube que has creado.
        * [Beta] Selecciona **Azure**.  

          <Image align="center" alt="" src="https://files.readme.io/cd718eeebc5965d24a2d38457d4fa22c5691d6a186464187bea12199fb96671b-31233921550481.png" width="943px" />
          1. Ingresa tu **nombre de conexión**, **nombre de cuenta de almacenamiento** y **clave**.
          2. Verifica que no se muestre ningún mensaje de error que indique que la ruta del bucket es inválida.
          3. Selecciona si deseas **hacer que esta conexión sea compatible con Adobe Experience Platform**.
          4. Haz clic en **Guardar**.
          5. En la configuración de Cost ETL, en el menú desplegable de **Conexión**, selecciona el servicio en la nube que has creado.
        * [Beta] Selecciona **Yandex**.  

          <Image align="center" alt="" src="https://files.readme.io/230e0d9c0b56b4c9f85da8c97f1ab91818c16ecfbabbf81ecb35f12d41716888-31233961360273.png" width="944px" />
          1. Ingresa tu **Nombre de bucket**, **Clave de acceso** y **Clave secreta**.
          2. Verifica que no se muestre ningún mensaje de error que indique que la ruta del bucket es inválida.
          3. Selecciona si deseas **hacer que esta conexión sea compatible con Adobe Experience Platform**.
          4. Haz clic en **Guardar**.
          5. En la configuración de Cost ETL, en el menú desplegable de **Conexión**, selecciona el servicio en la nube que has creado.
        * Selecciona **BigQuery**.  

          <Image align="center" alt="" src="https://files.readme.io/6989fa8c869c08440da757b3ebb385754a4f23dbe4e2d38c50837448c08ab03b-31233921555857.png" width="945px" />
          1. Introduce tu ID de proyecto de BigQuery y el nombre del conjunto de datos.
          2. Haz clic en **Probar conexión**.
          3. Verifica que no se muestre ningún mensaje de error que indique que la ruta del bucket es inválida.
          4. Haz clic en **Guardar**.
          5. En la configuración de Cost ETL, en el menú desplegable de **Conexión**, selecciona el servicio en la nube que has creado.
        * Cadena  
          <Image align="center" alt="" src="https://files.readme.io/b0e5f5ece797f46006d6e29a6afd01bc120b035590bd2ee87a54daa8c36bb0ed-31233961363985.png" width="944px" />
          1. Introduce tu región de Snowflake y tu ID de cuenta.
          2. Haz clic en **Probar conexión**.
          3. Verifica que no se muestre ningún mensaje de error que indique que la ruta del bucket es inválida.
          4. Haz clic en **Guardar**.
          5. En la configuración de Cost ETL, en el menú desplegable de **Conexión**, selecciona el servicio en la nube que has creado.
3. **Nota**:  
   <Image align="center" alt="" src="https://files.readme.io/4237ca8e7e70e0c04e924b61839d47d88e42075b4c257fcdf5e78870712d3582-31233921563153.png" width="746px" />
4. Establece el **horario de la versión del informe (UTC)**:  
   <Image align="center" alt="" src="https://files.readme.io/427b18043c0ab53ea559d53094efb6f04ad7505659c08ba7345b3a647f78d64d-31233961369105.png" width="607px" />
   <Image align="center" alt="" src="https://files.readme.io/427b18043c0ab53ea559d53094efb6f04ad7505659c08ba7345b3a647f78d64d-31233961369105.png" width="607px" />
   1. Selecciona cuántos reportes recibir cada día (1, 2, 3 o 4).
   2. Selecciona a qué hora recibir los reportes. [Saber más](/docs/set-up-and-use-roi360-cost-etl-reports#report-schedule)
   3. Haz clic en **Siguiente**.
5. Configura los detalles del reportes:
   1. Selecciona 1 o más aplicaciones para incluir en los reportes. Selecciona **Agregar todas las aplicaciones futuras** para incluir automáticamente las aplicaciones que agregues en el futuro.  

      <Image align="center" alt="" src="https://files.readme.io/a5d453f40a7c5318f6a4c6cdfc5cf4d645c540c4b684362a796cda41d3c058c6-31233961373585.png" width="566px" />
   2. Selecciona los reportes que mejor se adapten a tus necesidades de análisis. Consulta las descripciones en la sección [Tipos de reporte](#report-types).
      * El **reporte de resumen** está seleccionado por defecto.
      * [Beta cerrada] **Reporte de todos los costos**: Basado en la dimensión de geolocalización.  
        <Image align="center" alt="" src="https://files.readme.io/3662c55c71f3390ac651c9269eac519f846b53ad675dab224b62fb09f81d4578-31233921571345.png" width="1921px" />
   3. Selecciona las dimensiones que se incluirán en los reportes. **Nota**: Si has elegido recibir el reporte geográfico, la dimensión geográfica se incluye por defecto. Si has elegido recibir el reporte de canal, la dimensión de canal se incluye por defecto.   
      <Image align="center" alt="" src="https://files.readme.io/dbbea34c466b2263638a0937392ab004eab471a9e44d4c3713d6487507cef14b-4476081988241.png" width="1921px" />
   4. Selecciona las métricas que se incluirán en los reportes.  
      <Image align="center" alt="" src="https://files.readme.io/2b865bb9cdb355287d99e81278fed5fd374da80a9f93499bd7b75777c8d5d11e-360019263038.jpg" width="1863px" />
6. Haz clic en **Aplicar**.

</Accordion>

<div id="edit-or-change-connection" />

<Accordion title="Editar o cambiar conexión">

Puedes editar o cambiar conexiones para enviar datos a diferentes (o adicionales) lugares.

**Nota**: Después de cambiar a una conexión existente, no podrás volver a la conexión Cost ETL anterior.

<div id="edit-connection" />

#### Editar conexión

Para editar los detalles de la conexión:

1. En AppsFlyer, desde el menú lateral, ve a **Exportar** > **Cost ETL**.
2. En la sección de **conexión de datos**, ya sea:
   * Para conexiones de Cost ETL, haz clic en el menú desplegable de **detalles** de **conexión**. Se muestran los detalles de la conexión.  
      <Image align="center" alt="" src="https://files.readme.io/67a1fb2ce45a49fc75d12eba4d1c3e67875b83883b0fc05307c080c6050be0f2-31233961380369.png" width="651px" />
     <Image align="center" alt="" src="https://files.readme.io/95c76d3bfc4a4db4bb9b4e67e4460680e0039e91dd930903515771e52c00ac7a-31233961377937.png" width="695px" />
   * Para las conexiones de Cost ETL, haz clic en el menú desplegable de **Detalles de la conexión**. Se muestran los detalles de la conexión.  
     <Image align="center" alt="" src="https://files.readme.io/67a1fb2ce45a49fc75d12eba4d1c3e67875b83883b0fc05307c080c6050be0f2-31233961380369.png" width="651px" />
3. Sigue las instrucciones en pantalla para editar los detalles de tu conexión.
4. Haz clic en **Guardar cambios** o **Aplicar** según se te indique.

<div id="change-data-locker-connection" />

#### Cambiar conexión de Data Locker

**Para cambiar de una conexión de Data Locker a otra**:

1. En AppsFlyer, desde el menú lateral, ve a **Exportar** > **Cost ETL**.
2. En la sección de **conexión de datos**, ya sea:
   * Si ya tienes las conexiones de Data Locker que deseas configuradas, en el menú desplegable de **Conexión**, selecciona las que deseas para Cost ETL.  

     <Image align="center" alt="" src="https://files.readme.io/483cc971805232bca48f4da7f4ee6bd98e43cb3f8e70cfb79fd158746b889e35-31233921523601.png" width="700px" />
   * Si aún no tienes configurada la conexión de Data Locker que deseas, haz clic en **+ Nueva conexión en Data Locker** y crea una conexión allí. Luego regresa a la configuración de Cost ETL y selecciónalo en el menú desplegable de **Conexión**.  

     <Image align="center" alt="" src="https://files.readme.io/066e0829340c34f1f01fe3f637bc75b4a414cebeecb5257b01df877e6e5da7e3-31233961342865.png" width="700px" />
3. Haz clic en **Guardar cambios**.

<div id="change-from-cost-etl-to-data-locker-connection" />

#### Cambia de la conexión Cost ETL a la conexión Data Locker

Antes de comenzar:

* Ten en cuenta que después de cambiar a una conexión Data Locker, no puedes volver a tu conexión Cost ETL anterior.
* Ten en cuenta que al cambiar a una conexión Data Locker, la estructura de la ruta de la carpeta cambia al siguiente formato sin afectar los datos del reporte:

  `///t=/dt=/v=<1/2/3/4>/`

**Para cambiar de una conexión Cost ETL obsoleta a una conexión Data Locker**:

1. En AppsFlyer, desde el menú lateral, ve a **Exportar** > **Cost ETL**.
2. En la sección de **conexión de datos**, haz clic en **conexiones de Data Locker**.  

   <Image align="center" alt="" src="https://files.readme.io/2608d88368579c9fd3aa7648905484a56a7f0d989a96582cee51303409ce427c-31233961382289.png" width="631px" />
3. Haz una de las siguientes opciones para configurar la conexión Data Locker:
   * Si ya tienes configuradas las conexiones de datos que quieres, en el menú desplegable de **Conexión**, selecciona las que quieras para Cost ETL.  
     <Image align="center" alt="" src="https://files.readme.io/da486f6399e92c49923527da3348f4535691768cebd7a776ec84f7a2a739c204-31233961385617.png" width="501px" />
   * Si aún no tienes configurada la conexión de datos que quieres, haz clic en **+ New connection in Data Locker** y crea una conexión allí. Luego regresa a la configuración de Cost ETL y selecciónalo en el menú desplegable de **Conexión**.  

     <Image align="center" alt="" src="https://files.readme.io/0d48f83f30954f5f68efecf7e6c4cf2b39b295e0b893711bd2e2756406c42461-31233921587985.png" width="631px" />
4. Haz clic en **Guardar cambios**.

</Accordion>

<div id="aws-object-ownership" />

<Accordion title="Cambiar la propiedad del objeto de AWS">

En AWS, de forma predeterminada, cuando AppsFlyer escribe objetos en tu bucket, el propietario del objeto es AppsFlyer. Dependiendo de tu proceso de carga de datos, es posible que debas cambiar la propiedad predeterminada a ti como propietario del bucket.

**Para cambiar la propiedad de los objetos en tu bucket**:

1. Inicia sesión en la consola de administración de AWS y abre la consola de Amazon S3 en <Anchor target="_blank" href="https://console.aws.amazon.com/s3/">https://console.aws.amazon.com/s3/</Anchor>.
2. En la lista **Buckets**, elige el nombre del bucket para el que deseas habilitar la propiedad de objetos S3.
3. Ve a la pestaña **Permisos**.
4. En **Propiedad del objeto**, haz clic en **Editar**.
5. Selecciona **Propietario del bucket preferido**.
6. Haz clic en **Guardar**.

</Accordion>

<div id="best-practices" />

## Mejores prácticas

<div id="report-schedule" />

<Accordion title="Programación de reportes">

La configuración del horario del reporte te permite obtener los datos más recientes justo cuando los necesitas.

Al elegir tu horario del reporte:

* Selecciona la hora para obtener el reporte lo más cerca posible de la hora en que comienzas a procesar datos en tu sistema BI.
* Si tienes alguna ad network que proporciona los datos de ayer más tarde que otras, establece un reporte adicional a la hora en que esos datos de la ad network estén listos.

</Accordion>

<div id="override-data" />

<Accordion title="Reemplazo de datos">

Al extraer y analizar tus datos, se recomienda extraer los datos de una fecha y lote específicos, o reemplazar todos los datos anteriores para los días que proporciona el lote actual. De lo contrario, es posible que veas los mismos datos repetidos.

Por ejemplo, el lote 1 del 20 de febrero contiene datos del 14 al 20 de febrero. Pero los lotes escritos el 19 de febrero también contenían datos del 14 al 19 de febrero. Reemplaza los datos de los días anteriores recibidos el 19 de febrero con los datos recibidos en el lote más reciente del 20 de febrero.

</Accordion>

<div id="geo-versus-channel" />

<Accordion title="Geolocalización versus canal">

No todas las redes proporcionan datos para todas las dimensiones juntas. Los datos de geolocalización y de canal en Anuncios de Meta son los ejemplos más comunes. Es por eso que se proporcionan dos conjuntos de datos separados. Se garantiza que el conjunto de datos de geolocalización tendrá datos de geolocalización y se garantiza que el conjunto de datos del canal tendrá datos de canal.

En muchos casos y para muchas fuentes de medios, los datos en los conjuntos de geolocalización y de canal serán idénticos. Así, consume uno de los conjuntos de datos (geolocalización o canal), según lo que mejor se adapte a tus necesidades.

Si el acuerdo de integración con una fuente de medios determinada no incluye el canal, por lo que ese canal está en blanco, tratamos esos datos como si contuvieran el canal.

</Accordion>

<div id="aggregate-data" />

<Accordion title="Datos agregados">

La ETL de costos proporciona datos flexibles y granulares tan profundos como se pueden extraer de la red de publicidad. Para extraer información útil a partir de cantidades potencialmente enormes de datos, se recomienda agregar los datos de la forma que mejor se adapte a las necesidades de tu negocio. Por ejemplo, si necesitas comprender los datos de costos a nivel de campaña y de país, utiliza esas dimensiones.

</Accordion>

<div id="standardization-across-networks" />

<Accordion title="Estandarización entre redes">

No todas las redes proporcionan datos con la misma granularidad. Por ejemplo, Meta Ads no proporciona datos de costos de ID del sitio, mientras que los X Ads no brindan datos de costos por geolocalización. Ten en cuenta estos casos al agregar datos de la Cost ETL y asegúrate de observar datos similares al comparar redes.

</Accordion>

<div id="compare-data" />

<Accordion title="Comparación de datos">

La Cost ETL proporciona información sobre todos tus datos de costos. Algunas campañas proporcionadas en la Cost ETL no aparecen en algunos dashboards de AppsFlyer, por ejemplo, los datos de campañas inactivas, es decir, campañas sin instalaciones registradas. Para comparar los datos, busca un ID de campaña específico en el dashboard general y compáralo con sus datos de costos en la Cost ETL. <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#cost-data-availability-and-reports">Saber más sobre la disponibilidad de datos de costos</Anchor>

</Accordion>

<div id="combine-geo-report-and-all-cost-report" />

<Accordion title="Combina el reporte de geolocalización y el reporte de costo total">

Para obtener datos de costo completos vinculados con la atribución de Google, Meta, TikTok (móvil y no móvil) y otras fuentes de medios (solo móvil), usa la siguiente consulta:

```sql
with etl as (
    select *
    from etl
    where media_source = 'Facebook Ads'
      and date = '2025-07-16'
),

allcost as (
    select *
    from allcost
    where media_source = 'Facebook Ads'
      and date = '2025-07-16'
),

main as (
    select
        case when etl.date is null then 'all cost' else 'cost etl' end as report,
        coalesce(etl.date, allcost.date) as date,
        coalesce(etl.app_id, allcost.app_id) as app_id,
        etl.os,
        allcost.platform,
        coalesce(etl.media_source, allcost.media_source) as media_source,
        coalesce(etl.agency, allcost.agency) as agency,
        coalesce(etl.campaign_id, allcost.campaign_id) as campaign_id,
        coalesce(etl.campaign, allcost.campaign) as campaign,
        coalesce(etl.adset_id, allcost.adset_id) as adset_id,
        coalesce(etl.adset, allcost.adset) as adset,
        coalesce(etl.ad_id, allcost.ad_id) as ad_id,
        coalesce(etl.ad, allcost.ad) as ad,
        coalesce(etl.geo, allcost.geo) as geo,
        coalesce(etl.channel, allcost.channel) as channel,
        coalesce(etl.site_id, allcost.site_id) as site_id,
        coalesce(etl.ad_account, allcost.ad_account) as ad_account,
        coalesce(etl.keyword_id, allcost.keyword_id) as keyword_id,
        coalesce(etl.keywords, allcost.keywords) as keywords,
        coalesce(etl.campaign_objective, allcost.campaign_objective) as campaign_objective,
        coalesce(etl.af_cost_model, allcost.af_cost_model) as af_cost_model,
        coalesce(etl.bid_strategy, allcost.bid_strategy) as bid_strategy,
        coalesce(etl.af_bid_strategy, allcost.af_bid_strategy) as af_bid_strategy,
        coalesce(etl.currency, allcost.currency) as currency,
        coalesce(etl.cost, allcost.cost) as cost,
        coalesce(etl.impressions, allcost.impressions) as impressions,
        coalesce(etl.clicks, allcost.clicks) as clicks,
        coalesce(etl.installs, allcost.installs) as installs,
        coalesce(etl.re_attributions, allcost.re_attributions) as re_attributions,
        coalesce(etl.re_engagements, allcost.re_engagements) as re_engagements,
        coalesce(etl.original_cost, allcost.original_cost) as original_cost,
        coalesce(etl.reported_impressions, allcost.reported_impressions) as reported_impressions,
        coalesce(etl.reported_clicks, allcost.reported_clicks) as reported_clicks,
        coalesce(etl.reported_conversions, allcost.reported_conversions) as reported_conversions,
        coalesce(etl.ctr, allcost.ctr) as ctr,
        coalesce(etl.cvr, allcost.cvr) as cvr,
        coalesce(etl.ecpm, allcost.ecpm) as ecpm,
        coalesce(etl.cpi, allcost.cpi) as cpi,
        coalesce(etl.ccvr, allcost.ccvr) as ccvr,
        coalesce(etl.cvvr, allcost.cvvr) as cvvr,
        coalesce(etl.reported_cvr, allcost.reported_cvr) as reported_cvr,
        coalesce(etl.install_diff, allcost.install_diff) as install_diff,
        coalesce(etl.click_diff, allcost.click_diff) as click_diff,
        coalesce(etl.impression_diff, allcost.impression_diff) as impression_diff,
        coalesce(etl.ecpc, allcost.ecpc) as ecpc,
        coalesce(etl.video_25p_views, allcost.video_25p_views) as video_25p_views,
        coalesce(etl.video_50p_views, allcost.video_50p_views) as video_50p_views,
        coalesce(etl.video_75p_views, allcost.video_75p_views) as video_75p_views,
        coalesce(etl.video_completions, allcost.video_completions) as video_completions
    from etl
    full join allcost
        on etl.date = allcost.date
        and etl.app_id = allcost.app_id
        and etl.media_source = allcost.media_source
        and etl.campaign_id = allcost.campaign_id
        and etl.adset_id = allcost.adset_id
        and etl.ad_id = allcost.ad_id
        and etl.channel = allcost.channel
        and etl.geo = allcost.geo
        and etl.agency = allcost.agency
        and etl.site_id = allcost.site_id
        and etl.keyword_id = allcost.keyword_id
),

dedup as (
    select *,
           row_number() over (
               partition by date, media_source, agency, campaign_id, adset_id, ad_id, geo, channel, site_id, keyword_id
               order by report desc, cost desc
           ) as rank_for_dedup
    from main
)

select *
from dedup
where rank_for_dedup = 1;
```

</Accordion>

<div id="combine-cost-etl-and-cohort-reports" />

<Accordion title="Combinar Cost ETL y reportes de cohorte">

Considera combinar reportes de Cost ETL con reportes de cohortes avanzadas agregadas (o reportes de cohortes regulares a través de Data Locker) en tu sistema BI. Juntos, ofrecen la imagen más completa del rendimiento del marketing con datos frescos y precisos, incluidos clics, impresiones, costos, ingresos, eventos in-app, etc.). Y puedes usar estos datos combinados para obtener ROAS, CPA, etc. <Anchor target="_blank" href="/marketers/es/docs/combine-cost-etl-and-cohort-reports-via-data-locker">Saber más</Anchor>

</Accordion>

<div id="additional-information" />

## Información adicional

<div id="traits-and-limitations" />

<Accordion title="Características y limitaciones">

| Caducado | Observaciones |
| --- | --- |
| Zona horaria | Si se cambia la zona horaria, los datos de costos se duplican ese día y el día siguiente al cambio. <Anchor target="_blank" href="/marketers/es/docs/changing-app-time-zone-settings">Saber más</Anchor> |
| Actualización de los datos | <ul><li><Anchor target="_blank" href="/marketers/es/docs/about-data-freshness-and-timezone-support#intraday-during-the-day">A lo largo del día</Anchor>. Durante la configuración de la Cost ETL, debes establecer el cronograma para los reportes, es decir, cuándo deseas que estos lleguen.</li><li>Los datos generalmente llegan dentro de una hora de la hora que seleccionas. Así que si seleccionas que un reporte debe llegar antes de las 6 AM, llega entre las 5 y las 6 AM.</li></ul>**Nota**: Una vez que los datos de costos llegan a tu bucket, la transferencia adicional de datos a tus sistemas de BI puede variar mucho, según el reporte y el tamaño del archivo parquet, que puede ser desde unos pocos KBs hasta muchas GBs. |
| Todo reporte de costos | <ul><li>Todos los reportes de costos (beta cerrada) actualmente no incluyen datos de costos para las campañas de Google Performance Max.</li><li>No admite cambios en los nombres de las campañas</li></ul> |
| Datos de costo de campaña de SKAN | <ul><li>Cost ETL proporciona datos de costos para campañas de SKAN solo si la campaña tiene al menos una conversión clásica.</li><li>Para campañas con conversiones solo de SKAN, los datos de costos están disponibles solo si:<ul><li>La ad network relacionada es Twitter (X) o Meta, o</li><li>La integración con la ad network relacionada está marcada como campaña inactiva (Columna M= "Sí" en esta lista).</li></ul></li></ul> |
| Compatibilidad con aplicaciones de CTV y PC | Las aplicaciones de PC y CTV no son compatibles con los reportes de Cost ETL. |
| Disponibilidad de costos de Google Web y Meta Web | Para incluir datos de costo de <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-create-web-based-campaigns#crear-una-integración-de-google-ads-en-appsflyer">Google Web (`pid=googleads_int`)</Anchor> y <Anchor target="_blank" href="/marketers/es/docs/meta-ads-create-web-based-campaigns#cómo-crear-una-campaña-para-meta-web-ads">Meta Web (`pid=metaweb_int`)</Anchor> en el reporte All Cost, debes crear una conexión de costo en la pestaña Costo de tus integraciones activas de <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">Google Ads (`pid=googleadwords_int`)</Anchor> y <Anchor target="_blank" href="/marketers/es/docs/meta-ads-integration-setup#cost-clicks-and-impressions">Meta Ads (`pid=facebook_int`)</Anchor>. Sin estas conexiones, los datos de costo de Google y Meta Web no aparecerán en el reporte. |

</Accordion>

<div data-zendesk-anchors="four-types-of-cost-etl-reports=sobre-cost-etl h_01K4WKGHP4S2B23R0Z57NFESPE=sobre-cost-etl h_01JZJVXY0BA25QM9PK4YRT8DZ6=nota cost-etl-report-comparison-table=tabla-con-el-resumen-de-los-tipos-de-reporte-de-cost-etl h_01K4WN2VMPZYA6273EDW7CSJZ9=tabla-con-el-resumen-de-los-tipos-de-reporte-de-cost-etl report-details=detalles-del-reporte h_01JYXKJFYG6FKM8S6C8GYHPK6T=detalles-del-reporte h_01JYXKJFYGE8SHR071RNXW5V97=data-freshness h_01HA29GW8PWN30BCQCK29V0FTA=directory-and-filename-structure data-locker-connection-directory-structure=estructura-de-directorio-de-conexi%C3%B3n-de-data-locker h_01JD4P98XF9S47EDHP38VXW1XS=estructura-de-directorio-de-conexi%C3%B3n-de-data-locker cost-etl-connection-directory-structure=estructura-del-directorio-de-conexi%C3%B3n-cost-etl h_01JKWMF6V57C35F1A0BVH18CY1=estructura-del-directorio-de-conexi%C3%B3n-cost-etl h_01HA29GW8P0B1JJTGYDW863D7Z=file-fields fieldsdimensions=camposdimensiones h_01HA29GW8PQATB4K5VJP1HD4NW=camposdimensiones metrics=m%C3%A9tricas h_01HA29GW8PZTS7XDWGYWXFZPYG=m%C3%A9tricas procedures=procedimientos 01JCZDRERADNNX04RT752793PG=procedimientos 01JCZP8A5W67W66N886KHNRR4A=set-up-cost-etl 01JCZME67YK848NM0RJTM1J5ZG=edit-or-change-connection edit-connection=editar-conexi%C3%B3n h_01JCZMGC8J41Y7H4JGZDVWYDJS=editar-conexi%C3%B3n change-data-locker-connections=cambiar-conexi%C3%B3n-de-data-locker h_01JCZNQF3QE7P8PBQPKXZK1SA2=cambiar-conexi%C3%B3n-de-data-locker change-from-cost-etl-to-data-locker-connection=cambia-de-la-conexi%C3%B3n-cost-etl-a-la-conexi%C3%B3n-data-locker h_01JKWMF6V70W9FA90SSKJ77R2Z=cambia-de-la-conexi%C3%B3n-cost-etl-a-la-conexi%C3%B3n-data-locker h_01HA29GW8Q6D630E8SDVSFYVG7=aws-object-ownership best-practices=mejores-pr%C3%A1cticas h_01HA29GW8QKPQXE4GHECAC5R5X=mejores-pr%C3%A1cticas h_01J0NRD227RQR50CMNW60SF7SK=report-schedule h_01HA29GW8QHX8AMK4T7E85H7RS=override-data h_01HA29GW8QT5FNNYSWHCT99D68=geo-versus-channel h_01HA29GW8QA3FP46EMZVYDEZF3=aggregate-data h_01HA29GW8QPW0NXEMF1WGJMKSF=standardization-across-networks h_01HA29GW8Q3FNS0W7SKTG7S9R1=compare-data h_01K4WNM1ZFSMFZEV3V2HQ5PYQE=combine-geo-report-and-all-cost-report h_01J582E5JNR5DJ9T8HKDG2XSRR=combine-cost-etl-and-cohort-reports additional-information=informaci%C3%B3n-adicional h_01HA286GA6WPYVNN7KCXK7DGFM=informaci%C3%B3n-adicional h_01HA282W8WHHNDG75XZNSV2QQF=traits-and-limitations" />
