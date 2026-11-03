---
title: 'ROI360: descripción general de la agregación de costos'
metadata:
  keywords:
    - Advertisers
    - Agencies
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
    - Agencies
    - ROI360
  created_at: '2015-12-24T10:45:16Z'
  edited_at: '2026-10-07T00:01:34Z'
  id: 207040526
  locale: es
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/es/articles/207040526
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En resumen:** Descubre los métodos que utilizan los anunciantes para agregar y visualizar los datos de costos de marketing.

## Agregación de costos

ROI360 hace lo siguiente:

* Proporciona datos agregados de costo publicitario y métricas de rendimiento del valor de por vida (LTV) relacionadas con el costo. Estos datos están disponibles en los dashboards y en los reportes de rendimiento. Las métricas de costos disponibles incluyen el retorno de la inversión (ROI), el retorno del gasto publicitario (ROAS), clics, impresiones, ROI de la campaña y el costo efectivo promedio por instalación (eCPI) a lo largo del tiempo.
* Cubre los costos publicitarios en todas las plataformas, incluidas aplicaciones móviles, navegadores web, TV conectada (CTV), PC y consolas.
* Es compatible con diferentes modelos de costos utilizados por la fuente de medios, por ejemplo, costo por instalación (CPI), costo por acción (CPA), costo por clic (CPC) y costo por mil (CPM).
* Registra el costo publicitario a través de API, la Importación de Costos (subida de archivos CSV) y <Anchor target="_blank" href="/marketers/es/docs/view-aggregated-cost-data-for-attribution-links">el costo en el enlace de atribución</Anchor>.
* Permite a las agencias acceder a los datos de costo de ROI360 para anunciantes con una suscripción a ROI360.

Los siguientes datos están disponibles para los anunciantes sin una suscripción a ROI360:

* <Anchor target="_blank" href="/marketers/es/docs/view-aggregated-cost-data-for-attribution-links">Datos de costo en el enlace de atribución</Anchor>
* Datos de clics e impresiones de redes de autorreporte (SRN), que configuras en la pestaña **Costo** del partner integrado de SRN

## Principios de agregación de datos de costos

Esta sección describe los conceptos clave de la agregación de datos de costos de campañas

<div id="cost-aggregation-methods" />

<Accordion title="Métodos de agregación de costos">

AppsFlyer obtiene datos de costo de las fuentes de medios mediante uno o más métodos. Si una fuente de medios reporta costos mediante más de un método, el [mecanismo de priorización de costos](#cost-prioritization-mechanism) determina qué datos utiliza AppsFlyer. Esto evita que los datos de costo se inflen.

Después de que AppsFlyer procesa los datos, se muestran en la zona horaria UTC (por defecto) o según la configuración de tu <Anchor target="_blank" href="/marketers/es/docs/changing-app-time-zone-settings">zona horaria específica de la aplicación</Anchor>.

<table><thead><tr><th>Método de agregación de costos</th><th>Modelos de costos compatibles</th><th>Granularidad de datos</th><th>Actualización de datos</th><th>Observaciones</th></tr></thead><tbody><tr><td> <a href="./set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api" target="_blank">API</a>\*</td><td>Todas</td><td>El nivel depende de la integración</td><td><a href="./about-data-freshness-and-timezone-support#intraday-during-the-day" target="_blank">Intradía</a></td><td>Los datos pueden cambiar después del evento de costo porque AppsFlyer intenta recuperar datos de hasta 7 días atrás (dependiendo de la fuente de medios). Esto permite a AppsFlyer tener en cuenta los cambios retroactivos realizados por la fuente de medios.</td></tr><tr><td><a href="./import-cost-data" target="_blank">Importación de costos (subida de archivos)</a></td><td>Todas</td><td>El nivel depende del archivo subido</td><td>Hasta 4 horas después de la importación</td><td>Puedes revertir el costo reportado y enviar datos corregidos durante un máximo de 90 días.</td></tr><tr><td><a href="./view-aggregated-cost-data-for-attribution-links" target="_blank">Costo en el enlace de atribución</a></td><td>CPI</td><td>Nivel de usuario</td><td><p>Mínimo: tiempo real</p><p>Máximo: Hasta 4 horas después de que se haga clic en el enlace</p></td><td>No es posible realizar cambios</td></tr><tr><td colspan="5">\* Las integraciones de API entre fuentes de medios y AppsFlyer se realizan a través de Cost API o InCost API (nunca ambas). La API utilizada y la granularidad de los datos proporcionados dependen de la fuente de medios.</td></tr></tbody></table>

</Accordion>

<div id="cost-data-availability-and-reports" />

<Accordion title="Disponibilidad de datos de costos y reportes">

La tabla al final de esta sección indica dónde están disponibles los datos de costo.

Para entender la tabla, se aplican las siguientes explicaciones, a menos que se indique lo contrario en las observaciones de la tabla:

#### Costos en la vista UA

AppsFlyer clasifica los datos de costo de la campaña como adquisición de usuarios (UA) según reglas de correspondencia que varían según la fuente de medios, como se muestra a continuación.

| Fuentes de medios | Regla de correspondencia |
| --- | --- |
| Google Ads, DV360, Facebook, TikTok, Apple Search Ads y Aura | AppsFlyer clasifica el costo como UA si registra al menos una instalación, un clic o una impresión dentro de un margen de ±10 días desde la fecha de instalación (la fecha en que la fuente de medios reporta el costo). |
| Todas las demás fuentes de medios | AppsFlyer clasifica el costo como UA si registra al menos una instalación, un clic o una impresión en la propia fecha de procesamiento de la fuente de medios. No se aplica ninguna ventana de ±10 días. |

> 📘 **Nota:**
>
> Esto se aplica a ambas filas. AppsFlyer basa las correspondencias en la fuente de medios, el ID de campaña y la agencia.

#### Costos en la vista unificada

La vista unificada incluye datos de costos de todas las campañas de la app seleccionada, independientemente de si existen instalaciones, clics o impresiones dentro de ±10 días de la fecha en la que se reporta el costo (fecha de instalación).

#### Ejemplo

Los siguientes ejemplos muestran cómo la ventana de ±10 días afecta a dónde aparece el costo:

* Si una fuente de medios que usa la ventana de ±10 días reporta el costo de la campaña X el 15 de marzo, y la campaña X tiene al menos un clic, una instalación o una impresión entre el 5 y el 25 de marzo, el costo del 15 de marzo aparece en UA y en Unified.
  * Si no existe actividad dentro de esa ventana de tiempo, el costo del 15 de marzo aparece **solo en Unified**. En las fuentes de medios que solo coinciden por fecha de procesamiento, se aplica la misma regla al propio 15 de marzo, sin ventana de ±10 días.

#### Disponibilidad de datos de costos y reportes

| Método de reporte | Vista/tipo de datos | Soporte para cambio de nombre de campaña | Observaciones |
| --- | --- | --- | --- |
| Dashboard general | <ul><li>Ucrania</li><li>Unificado</li></ul> | Sí | La vista de retargeting no muestra el costo. El costo de retargeting se muestra en la vista Unified. |
| Dashboard de actividad | Ucrania | Sí |  |
| Dashboard de cohorte | <ul><li>Ucrania</li><li>Unificado</li></ul> | Sí | <ul><li>La vista de retargeting no muestra el costo</li><li>Estos datos de Unified están disponibles solo para campañas con al menos una instalación, un clic o una impresión registrada dentro de ±10 días de la fecha en la que se reporta el costo (fecha de instalación) para Google Ads, DV360, Facebook, TikTok, Apple Search Ads y Aura. Para todas las demás fuentes de medios, estos datos están disponibles solo para campañas con actividad registrada en la misma fecha de procesamiento que el costo.</li></ul> |
| API de cohorte | <ul><li>Ucrania</li><li>Unificado</li></ul> | Sí | Estos datos de Unified están disponibles solo para campañas con al menos una instalación, un clic o una impresión registrada dentro de ±10 días de la fecha en la que se reporta el costo (fecha de instalación) para Google Ads, DV360, Facebook, TikTok, Apple Search Ads y Aura. Para todas las demás fuentes de medios, estos datos están disponibles solo para campañas con actividad registrada en la misma fecha de procesamiento que el costo. |
| Dashboard de SKAN | SKÁN | No | Este dashboard muestra las instalaciones de SKAdNetwork (SKAN), junto con los datos de costo de **todas** las instalaciones (incluidas las que no son de SKAN). |
| API de rendimiento agregado de SKAN | SKÁN | No | Esta API muestra las instalaciones de SKAN, junto con los datos de costo de **todas** las instalaciones (incluidas las que no son de SKAN). |
| Dashboard pivot | Ucrania | No |  |
| API maestra | Ucrania | No |  |
| Dashboard personalizado | Ucrania | No |  |
| ETL de costos | Unificado | Sí | Se muestran todos los datos de costos disponibles. |
| Pull API agregada | Ucrania | No |  |
| API push | Datos de clics originales (no agregados) | No es relevante |  |
| Pull API de raw data | Datos de clics originales (no agregados) | No es relevante |  |
| Casillero de datos | Datos de clics originales (no agregados) | No es relevante | La cohorte de Data Locker no admite costos. |

> 📘 **Nota:**
>
> Los siguientes puntos se aplican a la tabla:
>
> * La granularidad de los datos puede cambiar dependiendo del tipo de dashboard o reporte. La herramienta de reportes de <Anchor target="_blank" href="/marketers/es/docs/set-up-and-use-roi360-cost-etl-reports">ETL de costos</Anchor> contiene el conjunto completo de datos. Esto incluye detalles de la jerarquía de la campaña (fuente de medios, nombre de la campaña, anuncio, adset y las dimensiones disponibles de la fuente de medios, incluidas geolocalización, canal, ID del sitio y palabras clave).
> * Los datos de costos informados en el enlace de atribución están disponibles en los reportes de raw data.
> * Si una fuente de medios no admite cambios en el nombre de la campaña, se muestran ambos nombres de campaña: uno con datos de atribución y otro con datos de costo. Ninguno de los dos nombres de campaña incluye la imagen completa de los datos.

</Accordion>

<div id="cost-prioritization-mechanism" />

<Accordion title="Mecanismo de priorización de costos">

Para una fuente de medios específica, el costo se puede proporcionar mediante más de un método. Para evitar la inflación de costos, un mecanismo de priorización del costo de campaña decide qué datos de costo aparecen en la plataforma. AppsFlyer asigna la prioridad según el método de agregación. La prioridad de menor a mayor es: Costo en el enlace de atribución > API de costos > Importación de costos.

![Diagrama que muestra el orden de prioridad del costo: costo en el enlace de atribución, luego Cost API y luego Cost Import](https://files.readme.io/8dbea1b8561d67f77d27cad85ab109e5203930273f32d2a9b04900b810c46ec2-25433450962577.png)

El mecanismo de priorización de costos afecta los reportes y dashboards de datos agregados. No afecta a los datos de costo del enlace de atribución en los Reportes de raw data, como se indica arriba.

**Consideraciones**:

* El mecanismo de prioridad opera a nivel de campaña. Esto significa que, si recibes dos entradas de costo para una campaña a través de mecanismos diferentes, compiten entre sí y la de mayor prioridad se aplica a toda la campaña.
  * En cualquier día, cuando hay datos de costo para una aplicación específica y una fuente de medios (o agencia) a través de Cost API, AppsFlyer ignora los datos de costo del enlace de atribución.
* Si cambias los métodos de agregación de costos, el cambio tiene un efecto retroactivo. Los datos históricos de costos agregados pueden modificarse.
* Un cambio en el método de Agregación de costo afecta del mismo modo al tráfico generado por agencias. Esto incluye tanto agencias transparentes como no transparentes.

> 📄 **Ejemplo**
>
> **Escenario:** Una fuente de medios reporta costos mediante el enlace de atribución, pero decides habilitar la API de costos de esa fuente de medios.
>
> **Resultado:** AppsFlyer agrega el costo tanto del enlace de atribución como de la API de costo. Como la API de costo tiene prioridad, AppsFlyer ignora el costo del enlace de atribución.

</Accordion>

<div id="closed-beta--cost-split" />

<Accordion title="División de costos">

Algunas fuentes de medios reportan los datos de costo de la campaña sin un App ID asociado. Cuando esto sucede, AppsFlyer completa el/los ID(s) de app utilizando datos de engagement y atribución.

AppsFlyer asocia apps basándose en aquellas vinculadas a los clics, impresiones y conversiones de la campaña dentro de una ventana de ±10 días alrededor de la fecha de costo reportada.

Si el proceso de completado de apps da como resultado varias apps coincidentes, AppsFlyer distribuye el costo de la campaña entre esas apps de la siguiente manera:

#### Distribución proporcional (por conversiones)

Si existen conversiones (instalaciones, reatribuciones y re-engagements) en la fecha de costo reportada, AppsFlyer divide el costo proporcionalmente según el número de conversiones de cada aplicación.

**Ejemplo:** Si el costo total del Día 1 es de **$100** y la campaña genera **60 instalaciones en iOS** y **40 instalaciones en Android**, entonces:

* iOS: **$60**
* Android: **$40**

> 📘 **Advertencia**
>
> La división proporcional (basada en conversiones) solo se aplica cuando la granularidad de conversión disponible en atribución coincide exactamente con la granularidad que reporta la fuente de medios para sus datos de costo. Cuando ambas solo coinciden parcialmente, AppsFlyer no puede asignar el costo a las conversiones de cada app, así que en su lugar aplica una división equitativa entre las apps coincidentes.

#### División equitativa (sin conversiones)

Si no existen conversiones en la fecha de costo reportada, AppsFlyer divide el costo por igual entre las aplicaciones coincidentes.

**Ejemplo:** Si el costo total del Día 1 es de **$100** y la campaña tiene impresiones pero ninguna conversión en esa fecha, entonces:

* iOS: **$50**
* Android: **$50**

#### Limitaciones

Esta función tiene las siguientes limitaciones:

* AppsFlyer es compatible con esta función para campañas cross-platform y web-to-app (W2A) de Google, TikTok y DV360 (campañas con un objetivo de campaña distinto de móvil/aplicación).
* **Campañas de Google Performance Max (PMAX)**: la división proporcional (basada en conversiones) no se aplica. La API de Google no reporta la granularidad de Ad ID ni de geolocalización para las campañas PMAX, por lo que AppsFlyer divide el costo por igual entre las apps coincidentes, independientemente del número de conversiones por app. A nivel de campaña, cuando se seleccionan todas las plataformas (iOS, Android, etc.) en el dashboard, el costo total sigue coincidiendo con el costo reportado por Google.

</Accordion>

## Información adicional

<div id="ad-networks-supporting-cost-api" />

<Accordion title="Lista de fuentes de medios compatibles con la API de costos">

La tabla descargable a continuación enumera todas las fuentes de medios compatibles con la API de costos, junto con la granularidad de datos disponible para cada una.

* Dimensiones
* Funciones compatibles y sus características
* Métricas (según las reportan las fuentes de medios)

Descargar archivo: <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQT0acJlUFIwS5NUuD8tJ5MA7OmL0N9a55qLp4ib5FYL_eat1H4IWNW9ZCtAEeDa1kTZK5bRD2ez-ee/pub?output=csv">CSV</Anchor>, <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQT0acJlUFIwS5NUuD8tJ5MA7OmL0N9a55qLp4ib5FYL_eat1H4IWNW9ZCtAEeDa1kTZK5bRD2ez-ee/pub?output=xlsx">XLSX</Anchor>

</Accordion>

<div id="changing-campaign-names" />

<Accordion title="Cambio de nombres de campañas">

AppsFlyer muestra las campañas usando el ID de campaña como clave.

Para evitar anomalías en la visualización, asegúrate de lo siguiente:

* Cada campaña tiene un ID de campaña único.
* No utilices el mismo nombre para diferentes campañas con distintos IDs.

<Anchor target="_blank" href="/marketers/es/docs/campaign-name-changes">Saber más sobre los cambios de nombre de las campañas</Anchor>

</Accordion>

<div id="costs-without-installs" />

<Accordion title="Costos sin instalaciones">

**¿Por qué veo datos de costos sin instalaciones?** Esto ocurre cuando el costo se proporciona a nivel superior en la jerarquía (por ejemplo, a nivel de campaña), pero la información de rendimiento (clics e instalaciones) se ofrece a un nivel inferior (por ejemplo, adset). Esto ocurre cuando una fuente de medios proporciona el costo en un nivel superior de la jerarquía (por ejemplo, el nivel de campaña), pero proporciona información de rendimiento (clics e instalaciones) en un nivel inferior de la jerarquía publicitaria (por ejemplo, el nivel de anuncio o adset).

AppsFlyer completa los datos de costo de las dimensiones faltantes desde un nivel más alto de la jerarquía. Esto asegura una visión completa de los datos de costos a cualquier nivel y minimiza discrepancias internas.

> 📄 **Ejemplo**
>
> Un anunciante lleva a cabo una campaña. La jerarquía publicitaria se presenta de la siguiente manera:
>
> * **Fuente de medios**: media\_eg
> * **Campaña**: campaña\_eg
> * **Adsets**: **adset\_1**, **adset\_2**
>
> La siguiente tabla muestra información relacionada con la fuente de medios.
>
> Jerarquía: Todas las fuentes de medios > media\_eg
>
>
>
> | Campaña | Costo | Instalaciones |
> | --- | --- | --- |
> | campaign\_eg | $100 | 100 |
> | campaign\_yy | $200 | 1000 |
> | campaign\_zz | $300 | 2000 |
>
>
>
> Al profundizar en campaign\_eg, se muestra el nivel de adset.
>
> Jerarquía: Todas las fuentes de medios > media\_eg > campaign\_eg
>
>
>
> | Conjunto de anuncios | Costo | Instalaciones |
> | --- | --- | --- |
> | Ninguno | $100 |  |
> | adset\_1 | N/D | 30 |
> | adset\_2 | N/D | 70 |
>
>
>
> En este caso, AppsFlyer proporciona el costo de $100 de campaign\_eg a nivel de campaña. Al desglosar hasta el nivel de adset, que en este caso es el nivel más bajo de la jerarquía, AppsFlyer no puede desglosar el costo por adset.
>
> Para superar esto, AppsFlyer desglosa el costo desde el nivel de campaña y lo muestra en una fila separada. En este caso, el adset se muestra como None y el campo de instalaciones permanece en blanco.

</Accordion>

<div id="cost-currency-conversion" />

<Accordion title="Conversión de divisa de costo">

Si la moneda del costo de la campaña proporcionada por la fuente de medios difiere de la moneda definida para la app en la plataforma, AppsFlyer convierte el costo a la moneda definida para la app de la siguiente manera:

* AppsFlyer obtiene los tipos de cambio de <Anchor target="_blank" href="https://openexchangerates.org/">openexchangerates.org</Anchor>.
* AppsFlyer actualiza los tipos de cambio cada hora para datos de hasta siete días atrás.
* AppsFlyer realiza las conversiones de moneda utilizando el último tipo de cambio conocido.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Características y limitaciones">

| Caducado | Descripción |
| --- | --- |
| Agencias | <ul><li>Cuando las agencias transparentes gestionan campañas, los anunciantes pueden ver el costo mostrado en dashboards y reportes que permiten una vista unificada. [Saber más sobre la disponibilidad de los datos de costo y los reportes](#cost-data-availability-and-reports)</li><li>Si un anunciante pone fin a su relación con una agencia y la agencia tiene configurados los costos para la aplicación, AppsFlyer seguirá obteniendo datos de costo aunque el anunciante deshabilite los permisos de la agencia a nivel de aplicación. Para evitarlo, el anunciante debe pedir a la agencia que desactive su integración de costos en AppsFlyer antes de deshabilitar los permisos de la agencia.</li><li>Para algunas fuentes de medios, las agencias deben contactar con el anunciante para activar la integración, y la interfaz de AppsFlyer se lo indica. Para estas fuentes de medios, las agencias y los anunciantes deben asegurarse de que, cuando la fuente de medios envíe datos, incluya el parámetro `af_prt`, necesario para la atribución de costos de la agencia.</li><li>Para los anuncios de X, los datos de costo de las campañas exclusivas de SKAN (campañas que solo tienen instalaciones de SKAN y ninguna instalación "normal") no están disponibles para las agencias. El anunciante debe configurar la integración de costos. Solo el anunciante puede ver los datos.</li></ul> |
| Actualización de datos de la API | <ul><li><Anchor target="_blank" href="/marketers/es/docs/about-data-freshness-and-timezone-support#intraday-during-the-day">Intradía</Anchor> (excepto para Moloco)</li><li>Los datos de Mintegral están disponibles vía API al día siguiente, aproximadamente 4 horas después de que finalice el día anterior. Por ejemplo, si el evento ocurrió el Día 1, los datos de costo estarán disponibles el Día 2, aproximadamente a las 4:00.</li></ul> |
| Multiplataforma | Los datos de gasto publicitario muestran el nombre de campaña informado más reciente. Esto se aplica solo a los datos agregados, no a los raw data en sí. |
| Zona horaria | Si una fuente de medios admite solo una zona horaria y esa zona horaria es distinta de la configurada en los ajustes de tu aplicación, AppsFlyer utiliza la zona horaria de la fuente de medios. |
| Plataformas CTV, PC y consola | Para las aplicaciones en estas plataformas, importa los datos a través de <Anchor target="_blank" href="/marketers/es/docs/import-cost-data">Ad Spend Ingestion</Anchor> mediante el método de carga por correo electrónico.<br /><br />También puedes extraer datos a través de la API para Google, Meta o TikTok en las siguientes plataformas:<ul><li>Steam</li><li>PC Nativo</li><li>Smart Cast</li><li>Tizen</li><li>Quest</li></ul> |
| Multiplataforma | Los datos de costo no están disponibles para los clics y las impresiones multiplataforma, lo que significa que la impresión o el clic pueden producirse en una plataforma y la instalación de la app en otra. |
| Aplicaciones out-of-store | Los datos de costo de Mintegral no están disponibles para aplicaciones out-of-store (aplicaciones de plataformas distintas de Google Play y App Store). |
| Geografía | El desglose geográfico/por país no está disponible para las campañas agrupadas de Mistplay (campañas dirigidas a varios países). Para estas campañas, la ubicación geográfica se muestra como N/A. |
| Smadex | Los dashboards y los reportes Cost ETL pueden mostrar los datos de costo y de atribución por separado. Esto ocurre cuando Smadex incluye otros elementos (como el ID de inventario) en el valor del ID de sitio. |
| Apple Search Ads | Para reportes únicamente de SKAN, los datos de costos de ASA no están disponibles en el dashboard de SKAN ni en Pull API, ya que Apple no incluye datos a nivel de campaña en los postbacks de SKAN. Sin embargo, los datos de costo están disponibles en los reportes de fuente única de verdad (SSOT) mediante la integración clásica de AppsFlyer. |
| Límite de caracteres de la dimensión de datos de costos | En las fuentes de medios que se indican a continuación, las siguientes dimensiones no deben superar la longitud de caracteres especificada. Si no cumples estos límites, AppsFlyer excluye los valores de dimensión del reporte.<ul><li>`app_id`: hasta 100 caracteres</li><li>`publisher`: hasta 250 caracteres</li><li>`partner`: hasta 250 caracteres</li><li>`campaign`: hasta 250 caracteres</li><li>`campaign_id`: hasta 250 caracteres</li><li>`adset`: hasta 250 caracteres</li><li>`adset_id`: hasta 250 caracteres</li><li>`ad`: hasta 250 caracteres</li><li>`ad_id`: hasta 250 caracteres</li><li>`site_id`: hasta 250 caracteres</li><li>`site_name`: hasta 250 caracteres</li><li>`canal`: hasta 250 caracteres</li><li>`ad_account`: hasta 250 caracteres</li><li>`ad_account_name`: hasta 250 caracteres</li></ul>Las limitaciones se aplican solo a las siguientes fuentes de medios:<ul><li>`mintegral_int`</li><li>`moloco_int`</li><li>`applovin_int`</li><li>`liftoff_int`</li><li>`aura_int`</li><li>`tiktokglobal_int`</li><li>`pinterest_int`</li><li>`vungle_int`</li><li>`iossearchads_int`</li></ul> |
| Disponibilidad de datos de costos vía API | AppsFlyer muestra los datos de costo de la API solo para clientes con un activo de ROI360 activo. Si ROI360 se desactiva, los datos de costo de las fuentes API dejan de estar disponibles y el dashboard solo muestra datos de costo basados en CPI. |
| Mintegral: granularidad a nivel de anuncio | Para obtener reportes de costo con granularidad a nivel de anuncio desde Mintegral, cada cuenta publicitaria requiere los siguientes permisos de ad network: **Sub/Package × Creative dimension**. |

</Accordion>

<div data-zendesk-anchors="cost-aggregation=agregaci%C3%B3n-de-costos h_01HC7K2Y627P56F5JH9QT47GB2=agregaci%C3%B3n-de-costos principles-of-cost-data-aggregation=principios-de-agregaci%C3%B3n-de-datos-de-costos h_01HC7K2Y62ZC932EDX00YP7DAW=principios-de-agregaci%C3%B3n-de-datos-de-costos h_01HC7K2Y62K78M02ZN034N99T0=cost-aggregation-methods h_01HC7K2Y62YPM3A6Z0HBY58J00=cost-data-availability-and-reports cost-in-the-ua-view=costos-en-la-vista-ua h_01KGS7NM964HW175AW2CF59P5K=costos-en-la-vista-ua h_01M3VZAVTP7F3TF607B49TGZQ4=nota cost-in-unified-view=costos-en-la-vista-unificada h_01KGS7QG5GNKG1YVACWQKCQFZ4=costos-en-la-vista-unificada example=ejemplo h_01KGS7R5SJ3NSVJAHG3BM922VS=ejemplo cost-data-availability-and-reports::865c5bcd=disponibilidad-de-datos-de-costos-y-reportes h_01HC7K2Y62ZY6HWG5TJDEPHZKH=disponibilidad-de-datos-de-costos-y-reportes h_01M3VZAVTPK4Q2X817ER2CW62D=nota-1 h_01HC7K2Y62112X308A0Y7DDDRM=cost-prioritization-mechanism h_01HC7K2Y62SZKXD4W0EJGYF6RS=ejemplo-1 %5Bclosed-beta%5D-cost-split=closed-beta--cost-split h_01KHR3PQTNF5XP7J4HZEYVRK95=closed-beta--cost-split proportional-split-by-conversions=distribuci%C3%B3n-proporcional-por-conversiones h_01KHR3PQTNMDX8AGM1C73N7SMK=distribuci%C3%B3n-proporcional-por-conversiones h_01KZ8TMT06KNYFZ7VBX1GY07JB=advertencia equal-split-no-conversions=divisi%C3%B3n-equitativa-sin-conversiones h_01KHR3PQTPG8GTHV64MFCM628H=divisi%C3%B3n-equitativa-sin-conversiones limitations=limitaciones h_01KHR3PQTPPJYKXRYKNHM4W95A=limitaciones list-of-ad-networks=informaci%C3%B3n-adicional h_01HC7K2Y63T9GK0WW95YM39B5C=informaci%C3%B3n-adicional h_01HC7K2Y63MG10M4Z66VHY5WYW=ad-networks-supporting-cost-api h_01HE0T3TGPZFB2ZBHFGGWXY6AP=changing-campaign-names h_01HE0T3TGQGK6135KM7AYJ7S1G=costs-without-installs h_01HE0T3TGQMK285N8RV48KG8N9=ejemplo-2 h_01HE0T3TGQ7MSSB09GFNPYFKR1=cost-currency-conversion h_01HJ10FMTJKH48CEXM0G40Y9J1=traits-and-limitations" />
