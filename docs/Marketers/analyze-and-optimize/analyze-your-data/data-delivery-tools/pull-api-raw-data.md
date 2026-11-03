---
title: Obtener raw data desde la Pull API
metadata:
  keywords:
    - Premium
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Raw Reports
  created_at: '2020-04-14T18:24:00Z'
  edited_at: '2026-08-12T11:51:19Z'
  id: 360007530258
  locale: es
  section: Data delivery tools
  section_id: 6550995484561
  url: https://support.appsflyer.com/hc/es/articles/360007530258
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Resumen:** Utiliza esta API para obtener reportes de raw data en archivos CSV.

[![PullAPIRaw_us-es.png](https://files.readme.io/1e68c85ee7d41a275ac6e09b35f6913fc10d974fc51c7c9c1357d3fd4d6d561c-33379479618705.png)](https://files.readme.io/1e68c85ee7d41a275ac6e09b35f6913fc10d974fc51c7c9c1357d3fd4d6d561c-33379479618705.png)

## Obtener raw data desde la Pull API

* La Pull API permite obtener reportes de raw data en archivos CSV. <Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-overview">Saber más sobre los reportes de raw data</Anchor>
* Filtrar según las opciones disponibles: Fuente de medios, rango de fechas, nombre del evento in-app y geolocalización.
* Otras funciones adicionales de Pull API son:
  * Seleccionar moneda
  * Seleccionar zona horaria

#### Reportes de raw data disponibles a través de la Pull API

<table><thead><tr><th>Reporte</th><th>Descripción</th><th>Frecuencia de actualización</th></tr></thead><tbody><tr><td colspan="3"><h4><strong><span id="raw-data-reports-nonorganic"></span>Reportes de raw data (no orgánicos)</strong></h4></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-installs-report-v5" target="_blank">Instalaciones</a></td><td>Registra instalaciones no orgánicas. El registro se genera cuando un usuario abre la aplicación por primera vez.<br/> </td><td>En tiempo real</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-in-app-events-report-v5" target="_blank">Eventos in-app</a></td><td>Registra los eventos realizados por los usuarios.<br/> </td><td>En tiempo real</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-uninstall-events-report-v5" target="_blank">Desinstalaciones</a></td><td>Registra cuándo un usuario desinstala la aplicación.<br/> </td><td>A diario</td></tr><tr><td> <a href="https://dev.appsflyer.com/hc/reference/get_app-id-reinstalls-v5" target="_blank">Reinstalaciones</a><br/> </td><td>Registra los ingresos por publicidad de los usuarios atribuidos a una fuente de medios de redireccionamiento durante la ventana de reactivación.</td><td>En tiempo real</td></tr><tr><td colspan="3"><h4><strong><span><strong><span id="raw-data-reports-organic"></span>Reportes de raw data (orgánicos)</strong></span></strong></h4></td></tr><tr><td> <a href="https://dev.appsflyer.com/hc/reference/get_app-id-organic-installs-report-v5" target="_blank">Instalaciones orgánicas</a><br/> </td><td>Registra cuándo un usuario abre la aplicación por primera vez.<br/> </td><td>Continuo</td></tr><tr><td> <a href="https://dev.appsflyer.com/hc/reference/get_app-id-organic-in-app-events-report-v5" target="_blank">Eventos orgánicos in-app</a><br/> </td><td>Registra detalles sobre los eventos realizados por los usuarios.<br/> </td><td>Continuo</td></tr><tr><td> <a href="https://dev.appsflyer.com/hc/reference/get_app-id-organic-uninstall-events-report-v5" target="_blank">Desinstalaciones orgánicas</a><br/> </td><td>Registra a los usuarios que desinstalan la aplicación.<br/> </td><td>A diario</td></tr><tr><td> <a href="https://dev.appsflyer.com/hc/reference/get_app-id-reinstalls-organic-v5" target="_blank">Reinstalaciones orgánicas</a><br/> </td><td>Registra a los usuarios que, después de desinstalar la aplicación, interactúan con una fuente de medios de UA y reinstalan la aplicación durante la ventana de reatribución.</td><td>A diario<br/> </td></tr><tr><td colspan="3"><h4><strong><span id="retargeting"></span>Reorientación</strong></h4></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-installs-retarget-v5">Conversiones</a></td><td>Registro de un usuario que abre la aplicación después de participar en una campaña de retargeting.</td><td>En tiempo real</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-in-app-events-retarget-v5">Eventos in-app</a></td><td>Eventos in-app realizados por el usuario durante la ventana de reactivación.</td><td>En tiempo real</td></tr><tr><td colspan="3"><h4><strong><span><strong><span id="ad-revenue-raw-data"></span>Raw data de ingresos por publicidad</strong></span></strong></h4></td></tr><tr><td> <a href="https://dev.appsflyer.com/hc/reference/get_app-id-ad-revenue-raw-v5" target="_blank">Ingresos por publicidad atribuida</a><br/> </td><td>Registra los ingresos por publicidad de los usuarios atribuidos a una fuente de medios.</td><td>A diario</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-ad-revenue-organic-raw-v5" target="_blank">Ingresos por publicidad orgánica</a></td><td>Registra los ingresos por publicidad de los usuarios no atribuidos a una fuente de medios.</td><td>A diario</td></tr><tr><td colspan="3"><h4><strong><span id="protect360-fraud"></span>Fraude en Protect360</strong></h4></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-blocked-installs-report-v5" target="_blank">Instalaciones</a></td><td>Registra las instalaciones que se identificaron como fraudulentas y, por lo tanto, no se atribuyeron a ninguna fuente de medios.</td><td>En tiempo real</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-detection-v5" target="_blank">Instalaciones posteriores a la atribución</a></td><td>Registra eventos in-app provenientes de instalaciones fraudulentas y, por lo tanto, no se atribuyen en absoluto.</td><td>A diario</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-blocked-in-app-events-report-v5" target="_blank">Eventos in-app</a></td><td>Registra eventos in-app identificados como fraudulentos por Protect360.</td><td>Periodo de atribución</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-fraud-post-inapps-v5" target="_blank">Eventos in-app posteriores a la atribución</a></td><td>Registra eventos in-app para instalaciones identificadas como fraudulentas después de ser atribuidas a una fuente de medios o juzgadas como fraudulentas sin tomar en cuenta la instalación en sí.</td><td>A diario</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-blocked-clicks-report-v5" target="_blank">Clics</a></td><td>Registra los clics realizados por usuarios bloqueados por Protect360.</td><td>En tiempo real</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-blocked-install-postbacks-v5" target="_blank">Postbacks de instalación bloqueados</a></td><td>Registra copias de postbacks enviados a una fuente de medios que resultaron en una instalación bloqueada.</td><td>En tiempo real</td></tr><tr><td colspan="3"><strong>Devoluciones de mensajes</strong></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-postbacks-v5" target="_blank">Postbacks de instalaciones</a></td><td>Registra los eventos de instalación generados cuando un usuario abre la aplicación por primera vez.</td><td>A diario</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-in-app-events-postbacks-v5" target="_blank">Postbacks de eventos in-app</a></td><td>Registra los postbacks de eventos in-app enviados a la fuente de medios.</td><td>A diario</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-retarget-in-app-events-postbacks-v5" target="_blank">Redireccionamiento de postbacks de eventos in-app</a></td><td>Registra los eventos in-app que los usuarios realizaron durante la ventana de reactivación.</td><td>En tiempo real</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-retarget-install-postbacks-v5" target="_blank">Postbacks de conversiones de redireccionamiento</a></td><td>Registra los eventos in-app que los usuarios realizaron durante la ventana de reactivación.</td><td>En tiempo real</td></tr></tbody></table>

<div id="using-pull-api-raw-data" />

<Accordion title="Uso de raw data de la Pull API">

**Para utilizar los raw data de Pull API**:

1. ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) Consigue el token de la API. Un administrador necesita recuperar el token.
2. Proporciona a tu desarrollador el token de la API que se usará en el encabezado de autenticación.
3. Proporciona a tus desarrolladores los parámetros que deben introducir al hacer la llamada a la API, como se describe en las secciones a seguir. Los parámetros determinan en qué se centra el reporte, cómo se organiza y proporcionan un marco temporal para el reporte.
4. Dile a tu desarrollador que siga las <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-5">instrucciones de los raw data de la API</Anchor> en el centro para desarrolladores.

#### Parámetros

| Parámetro | Descripción |
| --- | --- |
| desde | <ul><li>El rango de fechas consta de parámetros `from`y `to`. Las fechas se relacionan con la fecha de la actividad.</li><li>Formato: `yyyy-mm-dd`, `yyyy-mm-dd hh:mm`, o `yyyy-mm-dd hh:mm:ss` **Nota**: El espacio  debe codificarse como se muestra aquí `from=2020-04-01%2001:00:00`. Generalmente, los navegadores lo codificarán.</li><li>Ejemplo: 01-01-2010 o 01-01-2010 20:15 (Parámetros de horas y minutos disponibles para reportes de raw data).</li></ul> |
| a | Fecha de finalización. En cuanto a `from_install time` |
| fuente\_de\_medios | `media_source`: Para limitar (filtrar) la llamada a una fuente de medios específica.<br /><br />Establece los parámetros `media_source` y `category` de la siguiente manera:<ul><li>Para Meta Ads, configura la categoría y la fuente de medios en *facebook*</li><li>Para X Ads, configura la categoría y la fuente de medios en *twitter*</li><li>Para todas las demás fuentes de medios, establece la categoría en *estándar* y la fuente de medios en el nombre de la fuente de medios.</li></ul><ul><li>Ejemplos<ul><li>`media_source=facebook&category=facebook`</li><li>`media_source=abc_example&category=standard`</li></ul></li></ul> |
| maximum\_rows | Número máximo de filas devueltas por una única llamada a la API.<ul><li>[Predeterminado] si no se envía ningún valor, hasta 200K filas</li><li>200000: Se devuelven hasta 200K filas</li><li>1000000: Se devuelven hasta 1 millón de filas</li><li>Ejemplo:  habilita hasta 1 millón de filas.</li></ul> |
| nombre\_del\_evento | Filtrar eventos in-app por eventos específicos. Selecciona múltiples eventos utilizando una lista separada por comas.<br /><br />**Ejemplo**: `event_name=af_purchase,ftd` |
| reattr | Establecer datos de atribución de retargeting.<ul><li>[Predeterminado] Si es falso, se devuelven las campañas de adquisición de usuarios (UA).</li><li>Si es verdadero, se devuelven los datos de atribución de retargeting.</li><li>**Ejemplo**:`reattr=true`</li></ul> |
| additional\_fields | Para obtener campos adicionales además de los campos predeterminados.<br /><br />**Ejemplo**: `additional_fields=device_download_time,deeplink_url` |
| moneda | Moneda de los ingresos y los costos<ul><li>[Predeterminado] Si no se envía el parámetro, los datos se devuelven como USD. Es decir, no hacer nada y los resultados se muestran en USD.</li><li>Si la envías, `currency=preferred`la <Anchor target="_blank" href="/marketers/es/docs/app-settings#localization-time-zone">moneda específica</Anchor> de la aplicación se usará.  Es decir, la moneda establecida en la configuración de la aplicación.</li></ul>**Ejemplo**: Si la moneda específica de la aplicación es EUR, al enviar `currency=preferred` los valores se devuelven en EUR. |
| Zona horaria | [Predeterminado] Los datos se devuelven utilizando UTC.<ul><li>Para obtener datos en la zona horaria <Anchor target="_blank" href="/marketers/es/docs/app-settings#localization-time-zone">específica de la aplicación</Anchor>, agrega `timezone`como se muestra en esta sección a la llamada:</li></ul><ul><li>`timezone=[Numerical value]`</li><li>Ejemplo: Para la zona horaria UTC+10:00 utiliza`timezone=+10:00` **Nota**: Es necesario codificar `+`, `-`, y `:`. Ejemplo: +10:00 codifica a `%2B10%3A00`</li></ul> |
| geolocalización | Filtrar los datos por código de país.<br /><br />Limitación: Solo puedes configurar un filtro de código de país por llamada a la API.<br /><br />Ejemplo: `geo=ZA` |
| from\_install time | <ul><li>El rango de fechas consta de parámetros `from`y `to`. Las fechas se relacionan con la fecha de la actividad.</li><li>Formato:</li><li>Ejemplo: 01-01-2010</li></ul> |
| to\_install\_time | Fecha de finalización. En cuanto a `from` |
| agencia | Para limitar (filtrar) la llamada a una agencia específica. |

</Accordion>

<div id="protect360-fields" />

<Accordion title="Campos de Protect360">

<Anchor target="_blank" href="/marketers/es/docs/protect360-raw-data-reports#postattribution-reports">Consulta la guía de raw data de Protect360</Anchor>

</Accordion>

<div id="time-frame-fields" />

<Accordion title="Campos de marco temporal">

Si los resultados de la API superan el máximo, divide el reporte utilizando horas y minutos. Aplica lo siguiente:

* **desde**/**hasta:** **aaaa-mm-dd hh:mm**
* **Ejemplo**: 
  * Solo fecha = desde el inicio (00:00) de la fecha elegida
  * Fecha y hora = desde las 00:00
* Parámetro **a:**
  * Solo fecha = hasta el final (24:00) del día elegido
  * Fecha y hora = hasta, pero sin incluir, la hora mostrada

**Ejemplo:** El propietario de una aplicación alcanza 1.300K instalaciones diarias de todas las fuentes. Para superar el límite de 1 millón de filas, el propietario de la aplicación divide el día en dos llamadas URI de 12 horas. Consulta la tabla a continuación para ver las opciones.

<table><thead><tr><th>Llamada a la API</th><th>De </th><th>A </th></tr></thead><tbody><tr><td><strong>Primera llamada a la API</strong> </td><td><p><strong>desde</strong>=aaaa-mm-dd</p><p><strong>Ejemplo:</strong></p><ul><li> <strong>de</strong>=<code>2019-12-29</code> </li><li>Comienza en esta fecha al comienzo del día a las 00:00</li></ul></td><td><p><span><strong>a</strong>=aaa</span><span>a-mm-dd 12:00</span></p><p><strong>Ejemplo:</strong></p><ul><li> <strong>a</strong>=<code>2019-12-29 12:00</code> </li><li> <span>Continúa hasta las 11:59:59, no hasta las 12:00</span> </li></ul></td></tr><tr><td><p><strong>de:</strong>  </p><p><strong>Ejemplo:</strong> </p><p><code><kbd>&amp;from=2019-12-29 12:00&amp;to=2019-12-29</kbd></code></p><ul><li>Comienza el mediodía del 29 de diciembre de 2019</li><li>Finaliza a medianoche el 29 de diciembre de 2019</li></ul></td><td><p><strong>desde</strong>=aaaa-mm-dd 12:00</p><p><strong><span><strong>Ejemplo:</strong></span></strong></p><ul><li> <strong>de</strong>=<span><code>2019-12-29 12:00</code></span> </li><li>Comienza desde las 12:00 e incluye las 12:00</li></ul></td><td><p><span><strong>a</strong>=aaa</span><span>a-mm-dd </span></p><p><strong>Ejemplo:</strong></p><ul><li> <strong>a</strong>=<code>2019-12-29</code> </li><li>Termina a medianoche</li></ul></td></tr><tr><td><strong>Opción A: <strong><strong>Segunda llamada a la API</strong></strong></strong> </td><td><p><strong>desde</strong>=aaaa-mm-dd 12:00</p><p><strong>Ejemplo:</strong></p><ul><li> <strong>de</strong>=<span><code>2019-12-29 12:00</code></span> </li><li>Comienza desde las 12:00 e incluye las 12:00</li></ul></td><td><p><strong>a</strong>=aaaa-mm-dd+1 00:00</p><p><strong>+1</strong> = día siguiente a las 00:00</p><p><strong>Ejemplo:</strong></p><ul><li> a=<strong><code>2019-12-30 00:00</code></strong> </li><li>Es decir, antes de que haya transcurrido cualquier tiempo el 30 de diciembre.</li></ul></td></tr><tr><td colspan="3"> <strong>Nota:</strong> Utiliza la opción A o B ya que tienen los mismos resultados. </td></tr></tbody></table>

</Accordion>

<div id="additional-fields" />

<Accordion title="Campos adicionales">

Los campos adicionales del reporte no se añaden a la lista predeterminada para que los nuevos campos no afecten tus procesos de importación y adquisición existentes. Utiliza el parámetro `additional_fields` para obtener campos no predeterminados.

* Enumera un campo solo una vez.
* Consulta la <Anchor target="_blank" href="/marketers/es/docs/raw-data-field-dictionary">lista de campos disponibles</Anchor>.
* Ejemplo:

</Accordion>

<div id="default-fields" />

<Accordion title="Campos predeterminados">

| Campos predeterminados de la Pull API |
| --- |
| Tipo de toque atribuido |
| Tiempo de toque atribuido |
| Tiempo de instalación |
| Hora del evento |
| Nombre del evento |
| Valor del evento |
| Ingresos del evento |
| Moneda de ingresos del evento |
| Ingresos del eventos en USD |
| Fuente del evento |
| Recibo validado |
| Fuente de medios |
| Fuente de medios |
| Canal |
| Palabras clave |
| Campaña |
| ID de campaña |
| Conjunto de anuncios |
| ID del adset |
| Anuncio |
| ID del anuncio |
| Tipo de anuncio |
| ID del sitio |
| ID del subsitio |
| Subparámetro 1 |
| Subparámetro 2 |
| Subparámetro 3 |
| Subparámetro 4 |
| Subparámetro 5 |
| Modelo de costos |
| Valor del costo |
| Moneda de costo |
| Partner del Colaborador 1 |
| Fuente de medios del Colaborador 1 |
| Campaña del Colaborador 1 |
| Tipo de toque del Colaborador 1 |
| Tiempo de toque del Colaborador 1 |
| Partner del Colaborador 2 |
| Fuente de medios del Colaborador 2 |
| Campaña del Colaborador 2 |
| Tipo de toque del Colaborador 2 |
| Tiempo de toque del Colaborador 2 |
| Partner del Colaborador 3 |
| Fuente de medios del Colaborador 3 |
| Campaña del Colaborador 3 |
| Tipo de toque del Colaborador 3 |
| Tiempo de toque del Colaborador 3 |
| Región |
| Código del país |
| Estado |
| Ciudad |
| Código Postal |
| DMA |
| IP |
| Wi-Fi |
| Operador |
| Operador |
| Idioma |
| ID de AppsFlyer |
| ID de publicidad |
| Identificador de anunciante (IDFA) |
| ID de Android |
| ID de usuario del cliente |
| IMEI |
| IDFV |
| Plataforma |
| Tipo de dispositivo |
| Versión del sistema operativo |
| Versión de la aplicación |
| Versión del SDK |
| ID de la aplicación |
| Nombre de la aplicación |
| ID del paquete |
| Es retargeting |
| Tipo de conversión de retargeting |
| Atribución retrospectiva |
| Ventana de re-engagement |
| Es atribución primaria |
| Agente de usuario |
| Referente de HTTP |
| URL original |

</Accordion>

## Información adicional

<div id="traits-and-limitations" />

<Accordion title="Características y limitaciones">

| Caducado | Comentarios |
| --- | --- |
| Tipo de token API requerido | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)<Anchor target="_blank" href="/marketers/es/docs/managing-appsflyer-tokens">Token V2.0</Anchor> |
| Acceso a la ad network | No |
| Acceso a la agencia | Sí |
| Transparencia de la agencia | Sí. No obstante, ten en cuenta que si utilizas filtros de agencia junto con los de fuente de medios, estos últimos no se aplican a agencias no transparentes. Esto implica que para agencias no transparentes se incluyen todos los datos, y no solo los de las fuentes de medios filtradas. |
| Moneda específica de la aplicación | Sí |
| Zona horaria específica de la aplicación | Sí |
| Datos actualizados | <ul><li>Equivalente a la disponibilidad de datos en el dashboard general.</li><li>Reportes actualizados con un retraso de algunas horas:<ul><li>Eventos orgánicos in-app</li></ul></li><li>Reportes actualizados diariamente:<ul><li>Desinstalaciones</li><li>Eventos in-app posteriores a la atribución</li><li>Ingresos por publicidad</li></ul></li></ul> |
| Datos históricos | Sí.  De acuerdo con las políticas de <Anchor target="_blank" href="/marketers/es/docs/user-level-data-retention">retención</Anchor> y <Anchor target="_blank" href="/marketers/es/docs/report-generation-quotas-rate-limitations">limitación de tasa</Anchor>. |
| Datos no orgánicos | Sí |
| Datos orgánicos | Sí |
| Limitación de tasa | Limitaciones de la API para <Anchor target="_blank" href="/marketers/es/docs/report-generation-quotas-rate-limitations">raw data</Anchor>. |
| Limitaciones de tamaño | <ul><li>Las llamadas a la API devuelven un máximo de 200K/1M filas.</li><li>Si un reporte tiene exactamente 200K/1M filas, entonces es probable que falten filas.</li><li>Utiliza el parámetro maximum\_rows para seleccionar el número máximo de filas.</li><li>Realiza múltiples llamadas a la API, utilizando los parámetros desde/hasta que incluyan la hora del día.</li></ul> |
| Install\_date\_from and install\_date\_to | El rango de fechas de instalación debe ser anterior al rango de fechas de la actividad. |

</Accordion>

<div id="troubleshooting" />

<Accordion title="Resolución de problemas">

| Síntoma/mensaje | Solución |
| --- | --- |
| El reporte no contiene los datos esperados según el rango de tiempo seleccionado o hay una discrepancia entre el reporte de raw data y el reporte de datos agregados. | Verifica que hayas configurado el parámetro `timezone`. De no hacerlo, los datos se envían utilizando UTC en lugar de la zona horaria de tu aplicación. |

</Accordion>

> 📄 **Véase también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">Selección de la herramienta de entrega de datos/API de reportes adecuados</Anchor>

<div data-zendesk-anchors="pull-api-raw-data=obtener-raw-data-desde-la-pull-api h_01HE7S6WDVJD2XFW498P8FPY7W=obtener-raw-data-desde-la-pull-api aggregate-performance-reports-available-via-pull-api=reportes-de-raw-data-disponibles-a-trav%C3%A9s-de-la-pull-api h_01HE7S6WDV59VTP6Z4X790QDRD=reportes-de-raw-data-disponibles-a-trav%C3%A9s-de-la-pull-api h_01KEVCHC25BDNS9F1GEPBDAW39=raw-data-reports-nonorganic h_01KEVCHJ8TRRM9BYW6C544PNFR=raw-data-reports-organic h_01KEVCHSNGPX2RW917QX4N03A2=retargeting h_01KEVCHYMHGC6VTVSERH611Q8X=ad-revenue-raw-data h_01KEVCJ3GWBZG8SWHZKTRJ6YAX=protect360-fraud h_01HE7S6WDVYJ5MAK04VWB4MF6A=using-pull-api-raw-data parameters=par%C3%A1metros h_01HE7S6WDVF8T4719HWDJH8JN1=par%C3%A1metros h_01HE7S6WDVGSS0F116ZB6QVG1N=protect360-fields h_01HE7S6WDVP47A3Q8J7NPH54T5=time-frame-fields h_01HE7S6WDWZ8FR6GRJ40B4CJAV=additional-fields h_01HE7S6WDWMXYF0RHYPF058A9K=default-fields additional-information=informaci%C3%B3n-adicional h_01HE7S6WDW9V8XC3CJ0F96EHN0=informaci%C3%B3n-adicional h_01HE7S6WDWV87YVJMN76STX7A1=traits-and-limitations h_01HE7S6WDWMZPPTR41VHJQ8MWC=troubleshooting h_01HE7S8S8QCSKRA62A2HVK2MYJ=v%C3%A9ase-tambi%C3%A9n" />
