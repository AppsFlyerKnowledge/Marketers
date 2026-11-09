---
title: Panel de control general de SKAdNetwork (SKAN) de AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2020-07-25T21:27:38Z'
  edited_at: '2026-10-20T03:36:14Z'
  id: 360011307357
  locale: es
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/es/articles/360011307357
---
> **De un vistazo:** El panel de control de SKAdNetwork (SKAN) muestra las métricas de campaña reportadas a través de postbacks SKAN de iOS y puntos de datos adicionales durante las ventanas iniciales de medición del usuario. También hay disponibles métricas modeladas que tienen en cuenta las conversiones nulas. Los datos se muestran utilizando la fecha de instalación o de la llegada del postback.

<Image align="center" alt="SKAdHeadling8_us-en.png" src="https://files.readme.io/72c2eb452741cbd77c5828197f827f238c71c5097b8703528fa180dcafe2364c-360011831017.png" />

<div id="dashboard-principles" />

## Principios del panel de control

El panel de control contiene datos de rendimiento de la campaña de SKAN y se adhiere a los siguientes principios:

* Considera que Apple, debido a un <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork">mecanismo de umbral de privacidad</Anchor>, no siempre rellena el valor de conversión (CV). Se denominan CV nulos. En el caso de CV nulos, solo se registra una instalación.
* Las métricas se calculan de la siguiente manera:
  * Las métricas no orgánicas del panel de control se calculan utilizando los datos de postback de SKAN recibidos por AppsFlyer. Algunas métricas como las descargas repetidas, el ID de la aplicación fuente y las métricas de tipo de fidelidad requieren que configures tu aplicación para <Anchor target="_blank" href="/marketers/es/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">enviar copias de postback directamente a AppsFlyer</Anchor>.
  * Las métricas orgánicas se calculan como datos de atribución de AppsFlyer menos los datos de atribución no orgánicos de SKAN. **Nota**: Las métricas orgánicas no siempre están disponibles. [Aprender más](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#traits-and-limitations).
    * Asegúrate de filtrar por **Instalaciones nuevas** en el campo de tipo de instalación.
  * Algunas métricas, como los ingresos y el ROAS, tienen tanto el valor original derivado de los postbacks, como un [valor modelado](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv) que considera la tasa de CV nulos.
* El tráfico impulsado por la agencia se trata como si procediera de una agencia transparente.
* Actualización de los datos:
  * Diariamente.
  * Los postbacks recibidos en un día determinado se procesan al final del día UTC. Los datos están disponibles antes de las 08:00 UTC del día siguiente. Lo que significa que los postbacks recibidos el lunes están disponibles en los paneles de control el martes por la mañana.
  * Consulta la <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide#timing-from-app-install-until-dashboard-and-reports-update">hora prevista de actualización del panel de control.</Anchor>

<div id="skan-dashboard-view-options" />

## Opciones de vista del panel de control de SKAN

Muestra los datos utilizando la [fecha de instalación o de llegada del postback](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#filter-options).

**Para seleccionar una opción de visualización de la fecha**, en AppsFlyer, ve a **Panel de control** > **Vista general de SKAN.** En la barra de filtros, selecciona una opción de fecha en **Mostrar por**.

En las secciones siguientes se describen otros filtros y opciones de visualización.

<div id="dashboard-use" />

## Uso del panel de control

<div id="dashboard-settings" />

<Accordion title="Configuración del panel de control">

La configuración del panel de control está disponible cuando tu aplicación utiliza la <Anchor target="_blank" href="/marketers/es/docs/skan-conversion-studio#fixed-modes">medición de conversión de modo fijo</Anchor> heredada para seleccionar el evento de conversión.

**Para seleccionar el evento de conversión**:

1. En la parte superior derecha del panel de control, haz clic en **Configuración del panel de control**.
2. Selecciona un evento de conversión.
3. Haz clic en Aplicar.  
   Las métricas de conversión se calculan utilizando este evento.  
   ¡Atención! Nota: Esta configuración hace referencia a la visualización en el panel de control y no afecta la configuración de CV en la aplicación.

</Accordion>

<div id="filter-options" />

<Accordion title="Opciones de filtro">

Utiliza filtros para refinar la información mostrada.

| **Filtrar** | **Observaciones** |
| --- | --- |
| Mostrar por | <ul><li>**Fecha de instalación**: se calcula a partir de la hora de llegada del postback, de la siguiente manera:<ul><li>Si los postbacks son de SKAN V4, la fórmula para la fecha de instalación es: fecha de instalación = hora de llegada del postback - [duración de ventana acumulada] - [retraso promedio del postback].<ul><li>Postback 1: fecha de instalación = hora de llegada del postback - 48 h - 36 h</li><li>Postback 2: fecha de instalación = hora de llegada del postback - 168 h - 84 h</li><li>Postback 3: fecha de instalación = hora de llegada del postback - 840 h - 84 h</li></ul></li><li>Si los postbacks de SKAN son de SKAN V3 o anteriores, la fórmula para la fecha de instalación es: fecha de instalación = hora de llegada del postback - 36 horas - [rango promedio de último activo].<ul><li>El [promedio del último rango activo] predeterminado es de 12 horas.</li><li>Para un valor de conversión de 0, el rango promedio de última actividad se establece en 0.</li></ul></li></ul></li><li>Fecha de llegada del postback<ul><li>La fecha del campo ad\_network\_timestamp en los Reportes de raw data de SKAN. El timestamp depende de la ad network:<ul><li>Google Ads: el timestamp estimado del clic.</li><li>Meta Ads: el timestamp devuelto a través de la API de Meta.</li><li>Todas las demás ad networks: el timestamp del momento en que la ad network recibió el postback de SKAN de Apple.</li></ul></li><li>Cuando comparas las métricas en el panel de control de SKAN de AppsFlyer con las proporcionadas por las redes de publicidad, considera que las redes de publicidad suelen hacer que los datos estén disponibles usando la fecha de llegada del postback.</li><li>Las métricas orgánicas no están disponibles al seleccionar esta opción.</li><li>En el caso de Google Ads, las fechas de llegada e instalación no difieren.</li></ul></li></ul> |
| Rango de fechas | <ul><li>La fecha de instalación atribuida. Esta fecha se obtiene a partir de la hora de llegada del postback.</li><li>Si hay un gran número de instalaciones, la imprecisión debido a problemas de tiempo es insignificante.</li><li>Las instalaciones incluyen redescargas.</li><li>El rango de fechas está limitado a 90 días.</li></ul> |
| Fuente de medios | <ul><li>La red de publicidad atribuida con la instalación</li><li>Tráfico impulsado por la agencia: la fuente de medios real se muestra independientemente del estado de transparencia de la agencia. Por lo tanto, es posible que veas fuentes de medios con las que no estés familiarizado.</li></ul> |
| Campaña | <ul><li>Nombre e ID de la campaña según lo establecido por la red de publicidad.</li><li>AppsFlyer traduce el ID de la campaña de postback al de la red de publicidad.</li><li>Si un ID de campaña determinado tiene varios nombres de campaña asociados, todos los nombres se mostrarán en el panel de control. ¡Atención! Nota: La red de publicidad proporciona el ID y el nombre de la campaña por postback. Tanto el ID como el nombre de la campaña están disponibles en el raw data y en los reportes agregados de SKAN.</li></ul> |
| ID de sitio | <ul><li>Aplicación de origen que muestra tu anuncio.</li><li>Utilizado para analizar las aplicaciones más beneficiosas para ti.</li></ul> |
| Geolocalización | <ul><li>Territorio o país</li><li>La geolocalización se obtiene mediante los datos suministrados por la red de publicidad o mediante la dirección IP del dispositivo.</li><li>Al iniciar iOS 14.6, la dirección IP del dispositivo está enmascarada por un servidor proxy de Apple. Esto significa que se refleja la geolocalización del servidor de Apple y no la del propio dispositivo.</li></ul> |
| Tipo de instalación | <ul><li>Instalaciones</li><li>Descargas repetidas reportadas por la tienda de aplicaciones</li></ul> |
| Conjunto de anuncios | Disponible si la red de publicidad proporciona este punto de datos |
| Anuncio | Disponible si la red de publicidad proporciona este punto de datos |
| Versión | La versión de SKAN |

</Accordion>

<div id="headline-metrics" />

<Accordion title="Métricas principales">

| Métrica | Característica |
| --- | --- |
| Instalaciones | SKAN no reporta las instalaciones si el usuario no interactuó con un anuncio antes de la instalación. AppsFlyer calcula las métricas orgánicas utilizando las instalaciones atribuidas de AppsFlyer (panel de control de LTV).<ul><li>No orgánicas: instalaciones atribuidas a una fuente de medios en el contexto de una campaña de aplicación a aplicación pagada y reportada por SKAN.</li><li>Las orgánicas calculadas por AppsFlyer incluyen lo siguiente:<ul><li>Instalaciones no atribuidas por SKAN o para las que no se recibió ningún postback de una red de publicidad.</li><li>Clips de aplicaciones</li></ul></li></ul>Apple Ads (media-source iossearchads\_int) ahora aparece en el tráfico SKAN no orgánico. |
| Puntos de contacto | Las redes de publicidad reportan las impresiones y los clics por clic o API. |
| Ingresos totales | <ul><li>Disponible cuando el modo de ingresos está activo.</li><li>Se muestra en USD o en la divisa local específica de la aplicación como se establece en la <Anchor target="_blank" href="/marketers/es/docs/app-settings">página de configuración de la aplicación</Anchor>.</li><li>Dividido entre ingresos orgánicos y no orgánicos.</li><li>Los ingresos orgánicos se calculan como los ingresos de todas las fuentes menos los ingresos no orgánicos.</li><li>Para permitir una comparación similar, la duración de la ventana de actividad post-instalación de las instalaciones orgánicas y no orgánicas es la misma.</li><li>Incluye <Anchor target="_blank" href="/marketers/es/docs/skan-modeled-data#null-conversion-values">datos modelados</Anchor></li></ul>**Nota**: Las métricas orgánicas no siempre están disponibles. [Aprender más](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#traits-and-limitations). |
| Costo | <ul><li>Costo reportado por la red de publicidad. Los datos de costos se reportan a AppsFlyer utilizando la API de costos/ROI360. El costo se muestra en USD o en la divisa local específica de la aplicación como se establece en la <Anchor target="_blank" href="/marketers/es/docs/app-settings">página de configuración de la aplicación</Anchor>.</li><li>Si el nombre de la campaña cambia, el costo se muestra bajo el último nombre de campaña utilizado. (Si hay varios nombres de campaña)</li><li>Las métricas de costo solo están disponibles para el filtro Tipo de instalación=Todo, que incluye instalaciones y recargas.</li></ul> |
| Tasa de clic-instalación | Tasa de clic-instalación |
| Tendencia de periodo adyacente | Los valores de la tendencia en % indican el cambio de la métrica actual en relación con la métrica del periodo equivalente anterior. Por ejemplo, si el periodo actual es del 1 al 10 de mayo, el periodo anterior es del 21 al 30 de abril. |

</Accordion>

<div id="charts" />

<Accordion title="Gráficos">

Los gráficos disponibles dependen del tipo de medición seleccionado.

<Table>
  <thead>
    <tr>
      <th>
        Métrica del gráfico
      </th>
      <th>
        Observaciones
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Tendencia de adquisición de usuarios
      </td>
      <td>
        Dimensiones disponibles:

        * Orgánico
        * No orgánico

        [<Image alt="SKAdNetwork_Dashboard_AppsFlyer2_us-en.png" src="https://files.readme.io/5c46dc05b4df07f3f60ff6015f115b4bc89106a6eb594f43d777af2100fdf460-360010368477.png" width="201px" />](https://support.appsflyer.com/hc/article_attachments/49753070513297)
      </td>
    </tr>
    <tr>
      <td>
        Toque a conversión
      </td>
      <td>
        Vistas disponibles:

        * Dimensiones del punto de contacto:
          * Impresiones
          * Clics
        * Tasa de clic-instalación

        [<Image alt="SKAdNetwork_Dashboard_AppsFlyer3_us-en.png" src="https://files.readme.io/3e134f9411b356c8879dad8185b1762e6e039ed277da60fa9f67af351d8ab76d-360010368497.png" width="223px" />](https://files.readme.io/3e134f9411b356c8879dad8185b1762e6e039ed277da60fa9f67af351d8ab76d-360010368497.png)
      </td>
    </tr>
    <tr>
      <td>
        Instalaciones por día agrupadas por elemento de jerarquía de publicidad
      </td>
      <td>
        Elementos disponibles: Fuente de medios, Campaña, ID del sitio, Conjunto de anuncios, Anuncio[<Image alt="SKAdNetwork_Dashboard_AppsFlyer4_us-en.png" src="https://files.readme.io/a9b80aaeb0f34a3054bfb97bb72ff2ab549ff88ae4f6af43bf1c5e1ab604d3d3-360010368537.png" width="206px" />](https://files.readme.io/a9b80aaeb0f34a3054bfb97bb72ff2ab549ff88ae4f6af43bf1c5e1ab604d3d3-360010368537.png)
      </td>
    </tr>
    <tr>
      <td>
        Desglose de métricas por elementos de jerarquía de publicidad
      </td>
      <td>
        Elementos disponibles: Fuente de medios, Campaña, ID del sitio, Conjunto de anuncios, Anuncio

        [<Image alt="SKAdNetwork_Dashboard_AppsFlyer5_us-en.png" src="https://files.readme.io/f201592b110b3137329f7ad3c48c53e20639fb664383d76ceba2a347e969f6e4-360010368657.png" width="198px" />](https://files.readme.io/f201592b110b3137329f7ad3c48c53e20639fb664383d76ceba2a347e969f6e4-360010368657.png)
      </td>
    </tr>
    <tr>
      <td>
        Eventos principales
      </td>
      <td>
        Los principales eventos contienen tanto usuarios orgánicos como no orgánicos. Utiliza el filtro de fuentes de medios, en la parte superior de la página, para distinguir entre usuarios orgánicos y no orgánicos o por fuentes de medios seleccionadas.

        [<Image alt="SKAdNetwork_Dashboard_AppsFlyer6_us-en.png" src="https://files.readme.io/1a569224cec155b54a96433d6b2e36918c9c6f7924629cb09dcfc859358199c3-360010454658.png" width="245px" />](https://files.readme.io/1a569224cec155b54a96433d6b2e36918c9c6f7924629cb09dcfc859358199c3-360010454658.png)
      </td>
    </tr>
    <tr>
      <td>
        Países principales
      </td>
      <td>
        [<Image alt="mceclip1.png" src="https://files.readme.io/aba8db1a2aa7a90d5fd5c07e184eebd6d09762c5564f87f87f584d91686a59c6-360011169298.png" width="181px" />](https://files.readme.io/aba8db1a2aa7a90d5fd5c07e184eebd6d09762c5564f87f87f584d91686a59c6-360011169298.png)

        Nota: Este gráfico está disponible para las agencias y no para los anunciantes
      </td>
    </tr>
    <tr>
      <td>
        Copia de postback
      </td>
      <td>
        Este gráfico está disponible después de configurar la aplicación para enviar <Anchor target="_blank" href="/marketers/es/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">copias de postback</Anchor> de iOS 15+ a AppsFlyer. Si no aparece ningún gráfico, considera que:

        * No estamos recibiendo los postbacks de la aplicación o aún no los hemos recibido. Verifica con el desarrollador de tu aplicación que el punto de conexión de AppsFlyer se haya configurado en la aplicación y que la versión actualizada de la aplicación esté en el App Store.
        * No se ha recibido ningún postback (lo que significa que no hay instalaciones de SKAN) para la fecha seleccionada o has seleccionado una fecha anterior al 1 de enero de 2022.

        Notas:

        * Todas las demás métricas del panel de control se calculan utilizando postbacks de iOS reenviados por las redes de publicidad a AppsFlyer o a partir de los datos proporcionados directamente por las SRN. Se esperan discrepancias entre las métricas de copia de postbacks y las demás métricas.
        * El gráfico de copias de postbacks no está disponible para las agencias.

        [<Image alt="PostbackCopy.png" src="https://files.readme.io/0f2d290817650c87b3719ce2cdd107fdf66f62f575d3b4b75fcdd1f8330a04a9-4417816656657.png" width="207px" />](https://files.readme.io/0f2d290817650c87b3719ce2cdd107fdf66f62f575d3b4b75fcdd1f8330a04a9-4417816656657.png)

        | Dimensión | Observaciones |
        | --- | --- |
        | Fuente de medios | La fuente de medios atribuida a la instalación. <br /><br />* Métricas:<br />  * **Tasa de redescarga:** las métricas se refieren a los postbacks que utilizan SKAdNetwork V2.0+.<br />  * **Tasa de tipo de toque atribuido:** el engagement, la visualización o el clic que lleva a la instalación. Métricas hacen referencia a los postbacks con SKAdNetwork V2.2+<br />* Nota: Si se muestra el ID de la fuente de medios, actualmente no tenemos un nombre asociado con ese ID. Pide a la fuente de medios que actualice su ID de SKAdNetwork en AppsFlyer. |
        | Aplicación fuente | El nombre del publisher del anuncio, en otras palabras, el nombre de la aplicación en que el usuario interactuó con tu anuncio.<br /><br />* Métrica:<br />  * **Recuento de instalaciones**: el número de instalaciones traídas por la aplicación del publisher.<br />* Notas:<br />  * Si Apple retiene el ID de la aplicación fuente, debido a los umbrales de privacidad, la aplicación fuente se muestra como *desconocida*.<br />  * Si no se encuentra el nombre de la aplicación, se muestra el ID de aplicación. |
        | ID de aplicación fuente | El ID de anunciante, en otras palabras, el ID de la aplicación en la que el usuario interactuó con tu anuncio.<br /><br />* Métrica:<br />  * **Recuento de instalaciones**: el número de instalaciones traídas por el ID de aplicación del publisher. |
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="metrics" />

<Accordion title="Métricas">

* Selecciona las métricas entre las disponibles. Las [métricas modeladas](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv) tienen en cuenta la tasa de CV nulos.
* Establece los grupos primarios y secundarios por dimensiones para profundizar en las métricas de rendimiento.

<Image align="center" alt="SKAdNetwork_Dashboard_AppsFlyer7_us-en.png" src="https://files.readme.io/434a848c7a33c052c80101788b066f4bdb90ef36423ea140f85c1cc59ace2ebf-360010368617.png" />

Sobre la tabla de métricas:

* Utiliza la tabla para comparar el rendimiento de las campañas y las fuentes de medios.
* Inicialmente, se muestran las 20 fuentes de medios principales, ordenadas por el número de instalaciones en orden descendente.
* Para ordenar la tabla, haz clic en el encabezado de una columna. Haz clic de nuevo para invertir el orden de clasificación.
* Las métricas relacionadas con el costo (costo, impresiones y clics) están disponibles si al menos 1 instalación está asociada a una campaña determinada. Nota:
  * Las campañas con 0 instalaciones no se muestran en absoluto.
  * Algunas redes de publicidad reportan métricas relacionadas con los costos en el conjunto de anuncios y a nivel de anuncio, pero reportan la instalación a nivel de campaña. En este caso, las métricas relacionadas con los costos de los anuncios se muestran con una métrica de instalación de 0.
* Limitación de dimensión de tipo toque atribuido: las métricas relacionadas con los costos no se pueden desglosar y mostrar como **Desconocido**.

Métricas de la tabla:

<table><thead><tr><th>Métrica</th><th>Fórmula/observaciones</th></tr></thead><tbody><tr><td>Instalaciones</td><td><ul><li>Instalaciones Totales</li><li>Por clics<ul><li>Usuarios traídos a través de la atribución por clics</li><li>Disponible para instalaciones registradas a partir del 22 de diciembre de 2021</li></ul></li><li>Observaciones<ul><li>Disponible para instalaciones registradas a partir del 22 de diciembre de 2021</li><li>Se aplica a las redes de publicidad que implementan SKAdNetwork V2.2+</li></ul></li></ul><p>Estos datos se derivan del campo fidelity_type en el postback</p></td></tr><tr><td>Tasa del valor de conversión nulo</td><td>Postbacks que tienen un valor de conversión nulo/Instalaciones \* 100 </td></tr><tr><td>Impresiones</td><td> </td></tr><tr><td>Clics</td><td> </td></tr><tr><td>Tasa de clic-instalación</td><td>Instalaciones/clics \* 100</td></tr><tr><td>Usuarios convertidos</td><td><p>Recuento de usuarios únicos que realizan un evento de medición designado.</p><ul><li>Modo personalizado: siempre af_skad_revenue (si se selecciona cualquier otra cosa, los usuarios convertidos permanecen vacíos)</li><li>Modo SKAN 4: siempre af_skad_revenue (si se selecciona cualquier otra cosa, los usuarios convertidos permanecen vacíos)</li><li>Modo de ingresos: siempre af_skad_revenue</li><li>Modo de conversión: evento in-app seleccionado en la configuración del panel de control</li><li> <span>Modo de engagement: evento in-app tal como se establece en Conversion Studio</span><br/><br/> </li></ul><p>El tráfico de usuarios convertidos <strong>orgánicos</strong> no se muestra en el Dashboard de SKAN</p></td></tr><tr><td>Usuarios convertidos/instalaciones</td><td> </td></tr><tr><td>Ingresos</td><td>Ingresos, incluidos los datos modelados de valores nulos. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Aprender más</a> </td></tr><tr><td>Ingresos totales (no modelado)</td><td>Ingresos reportados a través de los valores de conversión. Datos modelados no incluidos.</td></tr><tr><td>Ingresos D1-D2</td><td>Ingresos para la ventana 1 de SKAN (días 1-2 a menos que se modifiquen), incluidos los datos modelados de valores nulos. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Aprender más</a> </td></tr><tr><td>Ingresos D1-D2 (no modelado)</td><td>Ingresos recibidos en la ventana 1 de SKAN (días 1-2 a menos que se modifiquen). Datos modelados no incluidos.</td></tr><tr><td>Ingresos D3-D7</td><td>Ingresos de la ventana SKAN 2 (días 3-7 a menos que se modifique)</td></tr><tr><td>Ingresos D8-D35</td><td>Ingresos de la ventana SKAN 3 (días 8-35 a menos que se modifique)</td></tr><tr><td>Costo</td><td><ul><li>Costo reportado por la red de publicidad</li><li>Si el nombre de la campaña cambia, el costo se muestra bajo el último nombre de campaña utilizado. (Si hay varios nombres de campaña)</li></ul></td></tr><tr><td>OPCIONAL</td><td><ul><li>Ingresos promedio por usuario, incluidos los datos modelados de valores nulos. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Aprender más</a> </li><li>Fórmula: Ingresos ($) (modelados) / Instalaciones</li></ul></td></tr><tr><td>ARPU (no modelado)</td><td>Ingresos promedio por usuario, datos modelados no incluidos.</td></tr><tr><td>ROI (Retorno de la Inversión)</td><td><ul><li>Retorno de la inversión, incluidos los datos modelados de valores nulos. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Aprender más</a> </li><li>Fórmula: (Ingresos ($) (modelados) - Costo) / Costo \* 100</li></ul></td></tr><tr><td>ROI (no modelado)</td><td>Retorno de la inversión, datos modelados no incluidos.</td></tr><tr><td>ROAS (Retorno de la Inversión Publicitaria)</td><td><ul><li>Retorno del gasto publicitario, incluidos los datos modelados de valores nulos. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Aprender más</a> </li><li>Fórmula: (Ingresos ($) (modelados)) / Costo \* 100</li></ul></td></tr><tr><td>ROAS (no modelado)</td><td>Retorno del gasto publicitario, datos modelados no incluidos.</td></tr><tr><td>IPC electrónico</td><td> </td></tr><tr><td colspan="2"><strong>Métricas de eventos in-app</strong></td></tr><tr><td>Nombre del evento in-app</td><td> </td></tr><tr><td>Costo Efectivo por Adquisición (eCPA)</td><td><ul><li>Costo efectivo por acción, incluidos los datos modelados de valores nulos. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Aprender más</a> </li><li>Fórmula: Costo / Usuarios únicos que realizan los eventos (modelados)</li></ul></td></tr><tr><td>eCPA (no modelado)</td><td>Costo efectivo por acción, datos modelados no incluidos.</td></tr><tr><td>Recuento total de eventos</td><td>Total de ocurrencias de eventos en todas las ventanas, incluidos los datos modelados de valores nulos. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Aprender más</a> </td></tr><tr><td>Recuento total de eventos (no modelado)</td><td>Total de ocurrencias de eventos en todas las ventanas, datos modelados no incluidos.</td></tr><tr><td>Recuento de eventos <span>D1-D2</span> </td><td>Ocurrencias de eventos para la ventana 1 (días 1-2 a menos que se modifiquen), incluidos los datos modelados de valores nulos. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">Aprender más</a> </td></tr><tr><td>Recuento de eventos <span>D1-D2 (no modelados)</span> </td><td>Ocurrencias de eventos para la ventana 1 (días 1-2 a menos que se modifiquen), datos modelados no incluidos.</td></tr><tr><td>Recuento de eventos <span>D3-D7</span> </td><td>Para los <a href="./skan-conversion-studio#fixed-modes" target="_blank">modos fijos</a>, los datos orgánicos están disponibles tanto para instalaciones como para eventos in-app.</td></tr><tr><td>Recuento de eventos <span>D8-D35</span> </td><td>Ocurrencias de eventos para la ventana 3 (días 8-35, salvo modificación).</td></tr><tr><td>Por impresiones</td><td>Número de usuarios únicos que realizaron el evento para la ventana 1 (días 1-2)</td></tr><tr><td>Divisa</td><td>Número de usuarios únicos que realizaron el evento para la ventana 1 (días 1-2, salvo modificación). Datos modelizados no incluidos.</td></tr><tr><td>Usuarios únicos del evento D3-D7 (no modelados)</td><td>Número de usuarios únicos que realizaron el evento para la ventana 2 (días 3-7, salvo modificación). Datos modelizados no incluidos.</td></tr><tr><td>Valor de tiempo de vida (LTV)</td><td>Número de usuarios únicos que realizaron el evento para la ventana 3 (días 8-35, salvo modificación). Datos modelizados no incluidos.</td></tr></tbody></table>

</Accordion>

<div id="modeled-metrics-and-null-cv" />

<Accordion title="Métricas modeladas y CV nulo">

Los reportes de SKAdNetwork (SKAN) pueden ser limitados porque:

* SKAN se basa en valores de conversión (CV) que están limitados a 6 bits, lo que da lugar a 64 valores posibles (0-63).
* En ocasiones, Apple retiene el CV real (y devuelve los datos como "null") para preservar la privacidad del usuario.
* Los datos solo están disponibles dentro de una ventana de medición y no se conoce el valor de vida útil (LTV) completo.

Los datos modelados SKAN resuelven estos problemas, proporcionando:

* Valores de conversión modelados en lugar de valores nulos.
* Ingresos modelados y ocurrencias de eventos.
* Una imagen más completa sobre el rendimiento de LTV de la aplicación y la campaña.

Las métricas modeladas disponibles incluyen:

* Ingresos
* Recuento de eventos
* Costo Efectivo por Adquisición (eCPA)
* OPCIONAL
* ROI (Retorno de la Inversión)
* ROAS (Retorno de la Inversión Publicitaria)

<Anchor target="_blank" href="/marketers/es/docs/skan-modeled-data">Aprender más sobre los datos modelados de SKAN</Anchor>

</Accordion>

<div id="appsflyer-attribution-vs-skan-attribution" />

<Accordion title="Atribución de AppsFlyer frente a atribución de SKAN">

Las métricas de SKAN difieren de las disponibles mediante el modelo de atribución de AppsFlyer. El cuadro siguiente enumera las principales causas.

Definiciones:

* **Tiempos:** asume la ventana de actividad predeterminada de 24 horas (48 horas una vez que se actualiza a SKAN 4).
* **SDK:** SDK de AppsFlyer integrado en la aplicación.
* **Reglas**: <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model">modelo de atribución de AppsFlyer</Anchor>

<div id="attribution-framework-differences" />

#### Diferencias en el marco de atribución

| Concepto | SKÁN | AppsFlyer |
| --- | --- | --- |
| Metodología de atribución admitida | Apple SKAN para la atribución por clics y por impresiones. Contiene tráfico de campañas de aplicación a aplicación de redes de publicidad y SRN compatibles con SKAN. | El <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model">modelo de atribución de AppsFlyer</Anchor> admite múltiples métodos y escenarios de atribución:<ul><li>Web móvil</li><li>Impresiones</li><li>Por clics</li><li>Clips de aplicaciones</li><li>Atribución web</li><li>Anuncios en la búsqueda de Apple</li><li>Medios propios</li><li>Tráfico de la SRN (usuarios que dan su consentimiento)</li><li>Y más</li></ul> |
| Fuente de datos principal | <ul><li>Postbacks de SKAN</li><li>SDK</li></ul> | SDK y soluciones asociadas.  Ejemplo: Eventos de servidor a servidor. |
| Actualización de los datos | <Anchor target="_blank" href="/marketers/es/docs/about-data-freshness-and-timezone-support#skan">Actualización de los datos de SKAN.</Anchor> | En tiempo real cuando el usuario lanza y utiliza la aplicación. |
| Zona horaria | UTC | Zona horaria específica de la aplicación |
| Horario de instalación | Derivado de la hora de llegada del postback de iOS. | Reportado por SDK. |
| Ventana de actividad | Actividad del usuario durante una ventana de medición fija, comenzando con la aplicación abierta. | Contiene datos de valor de vida útil (LTV) desde la fecha de instalación hasta el presente.<br /><br />Utiliza la Cohorte para ver los datos limitados al día 0 o al día 1 de la cohorte, o ambos en conjunto para ver un período de medición comparable.<br /><br />Ten en cuenta que el día 0 de la cohorte consiste en menos de 24 horas de actividad. Por ejemplo, un usuario que instala a las 18:00 en un día determinado, tiene 6 horas de actividad en el día 0 de la cohorte. |
| Instalaciones reportadas por | <ul><li>**SKAN**: limitado a las instalaciones no orgánicas y a las redescargas no orgánicas.</li><li>**SDK**: se reportan todas las instalaciones. A efectos de la medición, solo se cuentan las primeras instalaciones. Lo que significa que no se tienen en cuenta las reatribuciones.</li></ul> | El SDK reporta todas las instalaciones categorizadas mediante las reglas en primeras instalaciones y reinstalaciones de retargeting (reatribuciones). |
| Nivel de granularidad de la publicidad | Campaña, conjunto de anuncios, ID de conjunto de anuncios, anuncio e ID de anuncio. | Jerarquía completa: campaña, ID de campaña, conjunto de anuncios, parámetros adicionales como canal y partner. |
| Redescargas vs. reinstalaciones | Las redescargas se refieren a las acciones de un determinado usuario del ID de Apple. No son paralelas a las reatribuciones. | El retargeting (reatribuciones de re-engagements) se refleja en el panel de control de retargeting. No es paralelo a las redescargas. |

<div id="metric-differences" />

#### Diferencias entre métricas

| Métrica | SKÁN | Atribución tradicional |
| --- | --- | --- |
| Instalaciones no orgánicas | Recuento de postbacks de iOS válidos recibidos por AppsFlyer.<br /><br />Ten en cuenta que: AppsFlyer no obtiene los postbacks de las redes de publicidad que no han completado la integración de SKAN con AppsFlyer.<br /><br />Esto puede generar un recuento inferior de las instalaciones no orgánicas y un aumento de las instalaciones orgánicas. | <ul><li>Reportado por SDK.</li><li>Atribuidas a una fuente de medios.</li><li>Contadas usando Reglas.</li></ul> |
| Instalaciones orgánicas | Instalaciones de SDK menos instalaciones de SKAN. | <ul><li>Reportado por SDK.</li><li>No se atribuyen a ninguna fuentes de medios.</li><li>Contadas usando Reglas.</li></ul> |
| Ingresos | **No orgánicos**: ingresos reportados por postbacks de SKAN.<br /><br />**Orgánicos:** ingresos reportados por eventos in-app del SDK menos ingresos no orgánicos. **Nota**: Las métricas orgánicas no siempre están disponibles. [Aprender más](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#traits-and-limitations). | <ul><li>Reportados por SDK y API de servidor a servidor.</li></ul> |
| Ingresos por anuncios | <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide#recording-ad-revenue">Disponible</Anchor> | Los ingresos por publicidad a nivel de usuario se atribuyen en función del IDFV. |
| ROI/ROAS | Ingresos durante la ventana de medición. | <ul><li>Característica</li><li>Métricas de UA y campañas de retargeting.</li></ul> |

</Accordion>

<div id="faq-skan-discrepancies" />

<Accordion title="Preguntas frecuentes: discrepancias de SKAN">

| Motivo | Discrepancias: preguntas y respuestas |
| --- | --- |
| A | **P: ¿Por qué los números de conversión en el panel de control de AppsFlyer difieren de los del panel de control de la red de publicidad?**<br /><br />**R**: Motivos para discrepancias<ul><li>**Fecha de instalación frente a la fecha de llegada del postback:**<ul><li>AppsFlyer: la fecha de instalación se deriva mediante una fórmula que tiene en cuenta la hora de llegada del postback de iOS, la duración de la ventana y el tiempo de retraso del postback.</li><li>Red de publicidad: por lo general, utiliza la hora de llegada del postback de iOS como fecha de instalación sin ajustes.</li><li>Usa la opción **Mostrar por fecha de llegada del postback** en el panel de control para eliminar esta diferencia.</li></ul></li><li>**Validación de postbacks:** AppsFlyer valida los postbacks de iOS recibidos y se asegura de que la firma de Apple sea válida. Es posible que la red de publicidad envíe postbacks no válidos no considerados por AppsFlyer.</li><li>**Postbacks faltantes**: los postbacks de iOS deben ser enviados por la red de publicidad a AppsFlyer. AppsFlyer no recibe el postback directamente del dispositivo. Si faltan los postbacks, AppsFlyer no tiene forma de saberlo.</li></ul> |
| B | **P**: **¿Diferencias entre la <Anchor target="_blank" href="/marketers/es/docs/skan-aggregated-performance-report-api">API de rendimiento de SKAN</Anchor> y el panel de control frente a la <Anchor target="_blank" href="/marketers/es/docs/skan-aggregated-postback-arrival-date-api">API de postback agregado de SKAN?</Anchor>**<br /><br />**R**: El rango de fechas de la API de postback se refiere a la fecha en la que AppsFlyer recibió el postback. El rango de fechas de la API de rendimiento se refiere a la fecha de instalación derivada como se describe en el motivo A. |
| C | **P: ¿Todas las redes de publicidad reportan la geolocalización?**<br /><br />**R:** No. |
| D | **P: ¿Por qué hay diferencias entre el panel de control general y el panel de control de SKAN?**<br /><br />**R:** Consulta la sección anterior para ver los motivos para discrepancias. |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Rasgos y limitaciones">

| Caducado | Observaciones |
| --- | --- |
| Ocurrencias del evento modeladas | <ul><li>Los eventos modelados se basan en la fórmula descrita en las [métricas modeladas y CV nulos](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv).</li><li>La fórmula se aplica por fila de datos. Esto puede causar discrepancias entre el recuento de eventos modelados para una fuente de medios determinada y la suma del recuento de eventos modelados de sus campañas.</li></ul> |
| Fecha de llegada del postback | La fecha final de un intervalo de fechas se limita al día en que se registró la última instalación. |
| datos orgánicos | <ul><li>Los **ingresos orgánicos** solo están disponibles para los ingresos en modo <Anchor target="_blank" href="/marketers/es/docs/skan-conversion-studio#fixed-modes">fijo</Anchor> o heredado.</li><li>Para <Anchor target="_blank" href="/marketers/es/docs/skan-conversion-studio#skan-4">SKAN 4</Anchor> y los <Anchor target="_blank" href="/marketers/es/docs/skan-conversion-studio#custom">modos personalizados</Anchor>, los datos orgánicos están disponibles para las instalaciones, no para los eventos in-app ni los ingresos generales.</li><li>Para los **modos no heredados** (<Anchor target="_blank" href="/marketers/es/docs/skan-conversion-studio#skan-4">SKAN4</Anchor>, codificación personalizada y modos de decodificación), los datos orgánicos están disponibles solo para instalaciones.</li><li>Considera usar la SSOT para ver los datos orgánicos, ya que la SSOT elimina los duplicados de los eventos atribuidos por SKAN y atribuidos por el modelo de AppsFlyer.</li><li>Si los datos de atribución de AppsFlyer (nuevas instalaciones tanto orgánicas como no orgánicas) menos los datos de atribución de SKAN (instalaciones no orgánicas) son iguales a un número negativo, el panel de control de SKAN muestra 0 en las instalaciones orgánicas.</li></ul> |
| Historial de datos | Datos de conversión más antiguos admitidos: 1 de noviembre de 2020 |
| Truemoney | Se muestra en USD o en la divisa local específica de la aplicación como se establece en la <Anchor target="_blank" href="/marketers/es/docs/app-settings">página de configuración de la aplicación</Anchor>. |
| Zona horaria | Para los datos reportados por SKAN, las instalaciones y los eventos se muestran usando UTC, con la excepción de los datos Meta y Google SKAN, para los cuales la zona horaria se basa en la zona horaria configurada en sus cuentas Meta y Google, respectivamente. |
| Filtrar por versión de SKAN | Para algunos Partners de medios, se muestra **unknown**. Esto se debe a que actualmente no proporcionan ese campo.<ul><li>Google</li><li>Meta<br />Otros: verás este campo porque el dashboard de SKAN admite métricas previas a la atribución, como el costo, los clics y las impresiones, y no podemos desglosar esas métricas por versión, por lo que una nueva fila incluirá esas métricas.</li></ul> |
| Anuncios en la búsqueda de Apple | Apple Search Ads no comparte datos a nivel de campaña. Las campañas de agencia que requieran un prefijo no aparecerán en la vista de agencia. |

</Accordion>

<div id="see-also" />

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide">Guía de soluciones SKAN de AppsFlyer</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/about-att-and-skan">Qué ha cambiado: actualizaciones de AppsFlyer relacionadas con iOS 14</Anchor>

<div data-zendesk-anchors="dashboard-principles=principios-del-panel-de-control 01H81P8JPZM24J0536GKBPNFMJ=principios-del-panel-de-control skan-dashboard-view-options=opciones-de-vista-del-panel-de-control-de-skan 01H81P8JPZC5K0KZR64P084N4W=opciones-de-vista-del-panel-de-control-de-skan dashboard-use=uso-del-panel-de-control 01H81P8JPZGSHQVMG27YEJPARH=uso-del-panel-de-control 01H81P8JPZ93G4EQY343SV2B1Q=dashboard-settings 01H81P8JPZV5F4VCZHR537HREH=filter-options 01H81P8JQ0KRGXWCVT82YW30CS=headline-metrics 01H81P8JQ0ETB0W3SGS56CBCX8=charts 01H81P8JQ0KK1NMRGFR0GBX4EK=metrics 01H81P8JQ0ZKGTRWNW95D015Z7=modeled-metrics-and-null-cv 01H81P8JQ18NGP8Z74D02DMQ7P=appsflyer-attribution-vs-skan-attribution attribution-framework-differences=diferencias-en-el-marco-de-atribuci%C3%B3n 01H81P8JQ1VTYX3382WDXDMVT3=diferencias-en-el-marco-de-atribuci%C3%B3n metric-differences=diferencias-entre-m%C3%A9tricas 01H81P8JQ1M8M9TSHF0C12Z2QE=diferencias-entre-m%C3%A9tricas faq%E2%80%94skan-discrepancies=faq-skan-discrepancies 01H81P8JQ157YYNX9C527ES4C8=faq-skan-discrepancies 01H81P8JQ1T3DE29Y14VARKASK=traits-and-limitations h_01HE7SWGPWNWG26CEN40VSTA9J=consulta-tambi%C3%A9n" />
