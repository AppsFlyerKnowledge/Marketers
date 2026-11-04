---
title: Uso de los dashboards PBA
metadata:
  keywords:
    - pba
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2020-04-21T04:53:54Z'
  edited_at: '2026-08-12T11:51:11Z'
  id: 360007630318
  locale: es
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/es/articles/360007630318
---
> **De un vistazo:** aprovecha al máximo las funciones de nuestros dashboards PBA.

![Atribución basada en personas de AppsFlyer_us-en.png](https://files.readme.io/d2178dfedb2f67420e66626adbd72dd96ba9edc39fcb0be08648b01656fd2d4b-360010094118.png)

<div id="pba-dashboards" />

## Paneles de control de la PBA

Las siguientes secciones se refieren a los dashboards de <Anchor target="_blank" href="/marketers/es/docs/pba-website-attribution-dashboard">Atribución web</Anchor> y <Anchor target="_blank" href="/marketers/es/docs/pba-web-assisted-installs">Instalaciones asistidas por web</Anchor> dashboards.

<div id="settings" />

## Configuración

<div id="filtering-options" />

<Accordion title="Opciones de filtro">

Refina los resultados del dashboard PBA usando el selector de fecha (A), los filtros principales (B) y los filtros adicionales (C) para adaptar el análisis a tus necesidades.

<div id="filter-panel-in-pba-dashboards" />

#### Panel de filtros en los dashboards de PBA

[![PBAHeader_us-en.png](https://files.readme.io/aaa4040b69082c8507c604b530086404080d542b614fd20fcb0d5302221d7586-360019762657.png)](https://files.readme.io/aaa4040b69082c8507c604b530086404080d542b614fd20fcb0d5302221d7586-360019762657.png)

**Leyenda**:

(1) Selector de fecha

(2) Filtros predeterminados

(3) Filtros adicionales: Haz clic en + para seleccionar un filtro adicional.

**Principios**

* El diseño del panel de filtros es común a todos los dashboards de PBA.
* Los filtros disponibles por dashboard varían, como se indica en la tabla siguiente.
* Filtros con contexto: algunos filtros, como se indica en la tabla, requieren asociarse a un contexto. Por ejemplo, en el dashboard de Instalaciones asistidas por web, el filtro de geolocalización requiere el contexto de la fuente de medios web o de la fuente de medios móvil. Puedes configurar un filtro de geolocalización para cada uno definiendo dos filtros de geolocalización: uno para cada contexto.

<div id="available-filter-dimensions-per-dashboard" />

#### Dimensiones de filtro disponibles por dashboard

<table><tbody><tr><th>Filtro</th><th>Descripción/valores</th><th>Atribución del sitio web </th><th>Instalaciones asistidas por web</th><th>Rutas de<br/>conversión</th></tr><tr><td>Selector de fecha</td><td><p>La fecha en la que se produjo uno de los siguientes eventos de conversión de PBA: </p><ul><li>Instalación de aplicaciones</li><li>Conversión web</li><li>Conversión móvil</li></ul></td><td><p>Sí</p></td><td><p>Sí</p></td><td><p>Sí</p></td></tr><tr><td>Geografía </td><td><p>Lista de países/territorios </p></td><td>Sí</td><td><span>Sí (1)</span></td><td><p><span>Sí (2)</span></p></td></tr><tr><td>Contador máximo de eventos</td><td>Orgánico, banner inteligente, enlace personalizado, pagado</td><td>--</td><td><span>Sí</span></td><td><span>--</span></td></tr><tr><td>Valor de ejemplo: store_commission</td><td>Anuncio, directo, correo electrónico, referencia, búsqueda orgánica, social</td><td>Sí</td><td><span>Sí</span></td><td><span>Sí (2)</span></td></tr><tr><td>Plataforma móvil</td><td>Android, iOS</td><td>--</td><td><span>Sí</span></td><td><span>--</span></td></tr><tr><td>Nombre de la app </td><td><p>Fuente de medios a la que se atribuye el evento<span></span></p></td><td><p>Sí</p></td><td><span>Sí(1)</span></td><td><span> <font>Sí (2)</font> </span></td></tr><tr><td><p>Media Type</p></td><td><p>Incluye pagado, <a href="./owned-media-attribution" target="_blank">owned</a> y ganado</p></td><td><p>Sí</p></td><td>Sí</td><td>Sí (2)</td></tr><tr><td><p>Eventos de conversión</p></td><td><p>Muestra las rutas que llevan al evento de conversión para la ruta de conversión</p></td><td><p>Sí</p></td><td><p>--</p></td><td><p><span>Sí</span></p></td></tr><tr><td><p>Longitud de la ruta (pasos) </p></td><td><p>Número de pasos en la vista actual de la ruta de conversión: fuente de medios, canal de medios, tipo de medio</p></td><td><p>--</p></td><td><p>--</p></td><td><p>Sí</p></td></tr><tr><td><p>Duración de la ruta (días)</p></td><td>Duración de la conversión desde el primer punto de contacto</td><td>--</td><td>--</td><td>Sí</td></tr><tr><td colspan="5"><p><strong>(1)</strong> En el dashboard de instalaciones asistidas por web, asocias el filtro con la fuente de medios web o la fuente de medios móvil. Puedes configurar varias instancias del filtro. Caso de ejemplo</p></td></tr></tbody></table>

</Accordion>

<div id="grouping-options" />

<Accordion title="Opciones de agrupación">

Las opciones de Agrupar por están disponibles en los dashboards **Web-Assisted Installs** y **Website Attribution**.

Los datos del dashboard se agrupan, por ejemplo, por fuente de medios, dispositivo o país. Cuando se selecciona un grupo, se añade una columna de datos a la tabla de resultados. El orden en que se eligen los grupos afecta a cómo se muestran los datos.

* Grupo predeterminado: **Fuente de medios/Campaña**
* En la lista desplegable, selecciona 1 o más opciones.

<div id="example" />

> 📄 **Ejemplo**
>
> **Escenario:** La misma campaña de targeting se ejecuta tanto en Net\_A como en Net\_B.
>
> **Objetivo:** Ver qué fuente de medios tiene más éxito.
>
> **¿Cómo?** Agrupa por *fuente de medios* y, a continuación, mira una campaña dirigida al mismo público objetivo.

| Grupo | Nota | Instalaciones asistidas por web | Atribución del sitio web |
| --- | --- | --- | --- |
| Tipo de dispositivo | Incluye smartphone, tablet, desktop, TV y otros (dispositivos no reconocidos) | Sí | Sí |
| Representa el ID del publisher proveniente de la primera atribución asistida. | <ul><li>Se usa para diferenciar entre KPI web y KPI móviles</li><li>Dashboard Website Attribution: combina el sistema operativo y la plataforma. Por ejemplo, Android/Web, iOS/Web, Windows/Web, Linux/Web</li><li>Web-Assisted Installs: iOS, Android, Windows</li></ul> | Sí | N/A |
| Geografía | <ul><li>Ver tendencias de tráfico y engagement por país</li><li>Los resultados pueden tener un impacto directo en las decisiones de inversión por país</li></ul> | Sí | Sí |
| Fuente de medios/campaña | **Nombre de la app**<br /><br />Fuente de medios atribuida a una conversión<ul><li>Para ver datos detallados de la campaña, haz clic siguiendo la jerarquía de la campaña: campaña > conjunto de anuncios > anuncio</li><li>Los niveles de jerarquía disponibles varían entre las distintas fuentes de medios</li></ul>**Nombres de campañas**<ul><li>Nombres de campañas disponibles en función de los parámetros de la URL.</li><li>Los nombres de campañas no están disponibles en todos los casos.</li></ul> | Sí | Sí |
| Valor de ejemplo: store\_commission | Anuncio, directo, correo electrónico, referencia, búsqueda orgánica, social | N/A | Sí |
| Media Type | Incluye pagado, <Anchor target="_blank" href="/marketers/es/docs/owned-media-attribution">propio</Anchor>, ganado | N/A | Sí |
| Destino de engagement |  | N/A | Sí |

</Accordion>

<div id="other-settings" />

<Accordion title="Otros ajustes">

| Ajustes | Nota |
| --- | --- |
| Paquete de marca | Los dashboards de PBA tienen datos a nivel de paquete de marca. Los paquetes constan de un sitio web, 1 aplicación Android y 1 aplicación iOS.<ul><li>Puedes seleccionar paquetes si tus <Anchor target="_blank" href="/marketers/es/docs/pba-brand-bundles-and-settings#preguntas-frecuentes">permisos</Anchor> te permiten ver o editar las aplicaciones que forman el paquete.</li><li>Usa el selector para cambiar entre paquetes.</li><li><Anchor target="_blank" href="/marketers/es/docs/pba-brand-bundles-and-settings">Crear y editar paquetes.</Anchor></li></ul> |
| Configuración de la PBA | <ul><li>Configurar eventos de conversión</li><li>Cambiar la configuración del paquete</li></ul> |

</Accordion>

<div id="additional-information" />

## Información adicional

<div id="traits-and-limitations" />

<Accordion title="Especificaciones y limitaciones">

Los dashboards y reportes de PBA se actualizan <Anchor target="_blank" href="/marketers/es/docs/about-data-freshness-and-timezone-support#eod">diariamente</Anchor> según la zona horaria UTC.

* El procesamiento diario incluye los eventos recibidos durante el día anterior.
* Finalización de los datos:
  * En el caso de las Instalaciones asistidas por Web, Website Attribution PBA identifica eventos relacionados adicionales durante los primeros 7 días posteriores a la conversión. Esto puede cambiar la fuente de medios identificada como la responsable final de impulsar la conversión.
  * En los reportes de datos sin procesar relacionados, el campo *final\_data* es false durante el periodo inicial de 7 días.

Los dashboards de PBA no admiten moneda local y los datos se mostrarán en USD.

</Accordion>

<div data-zendesk-anchors="pba-dashboards=paneles-de-control-de-la-pba h_01HNJGN4BYRH14QXS4SWQAHR8D=paneles-de-control-de-la-pba settings=configuraci%C3%B3n h_01HNJGN4BYF8NFYYWHG30RHEJH=configuraci%C3%B3n h_01HNJGN4BYSHM9PFYQQ86ZR84X=filtering-options filter-panel-in-pba-dashboards=panel-de-filtros-en-los-dashboards-de-pba h_01HNJGN4BYVYY2MKK5G3RCS07W=panel-de-filtros-en-los-dashboards-de-pba filters-and-date-picker=dimensiones-de-filtro-disponibles-por-dashboard h_01HNJGN4BZ2KZAK120ZGT3B23W=dimensiones-de-filtro-disponibles-por-dashboard h_01HNJGN4BZV94W8W2GBXCZF563=grouping-options 01EDDQYQ8RWQZZTEZY9AVT1M64=ejemplo 01EDDQYQ8R5JPZE30ETV70FJVN=other-settings additional-information=informaci%C3%B3n-adicional h_01HNJGN4BZ9BMV7BQRQCKGYSSP=informaci%C3%B3n-adicional h_01HNJGN4BZFMG73SPZ1J4Z7TT5=traits-and-limitations" />
