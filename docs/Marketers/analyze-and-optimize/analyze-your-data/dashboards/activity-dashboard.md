---
title: Dashboard de actividad
metadata:
  keywords:
    - activity report
    - Advertisers
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2016-01-12T15:50:15Z'
  edited_at: '2026-08-12T11:50:21Z'
  id: 207602503
  locale: es
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/es/articles/207602503
---
> **En resumen:** Consulta la actividad de la aplicación, el engagement y las métricas internas durante un periodo específico. Las métricas del día actual se actualizan en tiempo real.

![ActividadDB.png](https://files.readme.io/8150eafc018c83ae2b1030702129bda12419dfac60eb8664187c2acd66136df3-4420170646289.png)

## Dashboard de actividad

* Contiene tráfico orgánico y no orgánico.
* El rango de fechas se refiere a la fecha del evento y no está <Anchor target="_blank" href="/marketers/es/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">basado en LTV.</Anchor>
* Actualización de datos:
  * **Día actual**: <Anchor target="_blank" href="/marketers/es/docs/about-data-freshness-and-timezone-support#continuous-aka-realtime">Continuo</Anchor>. Ejemplo: DAU, sesiones, ingresos
  * **Promedio:** A diario. Ejemplo: MAU, DAU promedio, MAU promedio
* El filtro Geo se refiere a la ubicación del usuario en el momento de la instalación.

> 👍 **Consejo**
>
> ¿Quieres saber más sobre el dashboard de actividad? Consulta este breve <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7802/play/18621/the-activity-dashboard">curso informativo en el portal de aprendizaje de AppsFlyer</Anchor>.

## Características y diseño del dashboard

<div id="metric-definitions" />

<Accordion title="Definición de métricas">

<Table>
  <thead>
    <tr>
      <th>
        Métrica
      </th>
      <th>
        Descripción
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="dau"></span>
        DAU
      </td>
      <td>
        * Usuarios activos diarios: Cantidad de usuarios únicos que abrieron la aplicación al menos una vez en el día.
        * DAU se basa en sesiones.
        * <Anchor target="_blank" href="/marketers/es/docs/unique-users">Más información sobre usuarios únicos</Anchor>
      </td>
    </tr>
    <tr>
      <td><span id="average-dau"></span>
        DAU promedio
      </td>
      <td>
        Número promedio de usuarios activos diarios por día, durante el periodo seleccionado.

        Ejemplo: Cálculo del DAU promedio

        > 📄
        >
        > |  | Domingo | Lunes | Martes |
        > | --- | --- | --- | --- |
        > | <span id="daily-active-unique-users"></span>Usuarios únicos activos al día | 10 | 12 | 8 |
        >
        >
        >
        > **DAU promedio** = (10+12+8)/3 = 10.
      </td>
    </tr>
    <tr>
      <td><span id="mau"></span>
        MAU
      </td>
      <td>
        Usuarios activos mensuales:

        * **Detallado:** Número de usuarios únicos (contados solo una vez) que abrieron la aplicación al menos una vez durante los 31 días anteriores.
        * **Alto nivel:** Número de usuarios únicos (contados solo una vez) que abrieron la aplicación al menos una vez durante el mes.
      </td>
    </tr>
    <tr>
      <td><span id="daumau-rate"></span>
        Tasa DAU/MAU
      </td>
      <td>
        * Esta métrica muestra la proporción de usuarios que regresan. Una tasa DAU/MAU del 50% indica que el usuario medio abrió la aplicación en 15 de los últimos 31 días.
        * La tasa DAU/MAU mide la fidelidad del usuario y ofrece una instantánea de su retención.
      </td>
    </tr>
    <tr>
      <td><span id="revenue"></span>
        Ingresos
      </td>
      <td>
        Ingresos generados durante el periodo seleccionado. Los ingresos comprenden compras in-app (si se reportan) e ingresos por publicidad.
      </td>
    </tr>
    <tr>
      <td><span id="arpdau"></span>
        ARPDAU
      </td>
      <td>
        Ingresos promedio por usuario activo diario.  
        Fórmula: Suma de (Ingresos del día [n] / DAU del día [n]) / Número de días.

        > 📄 **Ejemplo: Cálculo del ARPDAU**
        >
        > | Día | Ingresos ($) por día | DAU | Ingresos diarios promedio por usuario ($) |
        > | --- | --- | --- | --- |
        > | <span id="day-1"></span>Día 1 | 10 | 5 | 2 |
        > | <span id="day-2"></span>Día 2 | 16 | 4 | 4 |
        > | <span id="day-3"></span>Día 3 | 30 | 5 | 6 |
        > |  |  | Total: | 12 |
        > |  <span id="::4eb0b020"></span>|  | Número de días | 3 |
        > |  <span id="::b35cc38c"></span>|  | **ARPDAU** | 4 |
      </td>
    </tr>
    <tr>
      <td><span id="sessions"></span>
        Sesiones
      </td>
      <td>
        Sesiones durante el rango de fechas seleccionado (si se reporta por la aplicación)
      </td>
    </tr>
    <tr>
      <td><span id="installs"></span>
        Instalaciones
      </td>
      <td>
        Número de instalaciones durante el rango de fechas especificado.
      </td>
    </tr>
    <tr>
      <td><span id="average-ecpi"></span>
        eCPI promedio
      </td>
      <td>
        Costo promedio por instalación Costo promedio por instalación Nota: Las instalaciones son instalaciones de UA y el costo es unificado (UA y retargeting).
      </td>
    </tr>
    <tr>
      <td><span id="conversion-rate"></span>
        Tasa de conversión
      </td>
      <td>
        Tasa de instalaciones a partir de clics. **Nota**: Las instalaciones son instalaciones de UA y los clics son unificados (UA y retargeting).
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="detailed-tab" />

<Accordion title="Pestaña detallada">

La pestaña de análisis detallado se divide en secciones: métricas principales, tendencia de actividad y resumen de actividad.

<table><tbody><tr><td colspan="2"><h4><strong><span id="headline-metrics"></span>Métricas principales</strong></h4></td></tr><tr><td> </td><td><img alt="ActivityHeadLines_us-en__1_.png" src="https://files.readme.io/a4f1a5316eeacf0f635bbeadf52d490dd0276bb8a1fe9c0e32db7008d11d044b-360012584838.png"/></td></tr><tr><td> </td><td><p><strong>Promedio de usuarios activos</strong></p><ul><li>DAU promedio: número promedio de usuarios activos diarios en el periodo especificado.</li><li>MAU promedio: número promedio de usuarios activos mensuales en el periodo especificado. Se calcula como un promedio móvil de los días en el rango seleccionado, donde cada día observa los 31 días anteriores. Nota: Para ver el valor de MAU de un mes dado, como marzo, ajusta el rango de fechas al primer día después de ese mes (por ejemplo, el 1 de abril) y consulta el valor de MAU promedio.</li></ul></td></tr><tr><td> </td><td> <strong>Instalaciones totales:</strong> Número de instalaciones divididas en orgánicas y no orgánicas.</td></tr><tr><td> </td><td> <strong>Sesiones totales</strong>: Número de sesiones divididas entre usuarios orgánicos y no orgánicos.</td></tr><tr><td> </td><td> <strong>Ingresos totales</strong>: Ingresos, divididos entre usuarios orgánicos y no orgánicos.</td></tr><tr><td colspan="2"><h4> <br/><strong><span id="activity-trends"></span>Tendencias de actividad</strong><br/> </h4></td></tr><tr><td> </td><td><p> <strong>Línea de tendencia comparativa</strong></p><p><img alt="TrendLinWithComp_us-es.png" src="https://files.readme.io/b9edb3e409dc13bc72aebdccdc499fa2dcd9abf4549fb0170bf0cdc7036eee15-360012507997.png"/></p><ul><li>El gráfico de tendencias muestra los KPIs o las métricas relacionadas con eventos in-app.</li><li>Se puede agregar una línea de tendencia comparativa opcional habilitando la opción <strong>Comparar con el periodo</strong> previo (día, semana, mes, trimestre, año).</li><li>Por ejemplo, si seleccionas "mes", significa que para un día particular en el gráfico, la comparación es con el mismo día del mes anterior. </li></ul><p>Los KPIs disponibles son:</p><ul><li><span>DAU</span></li><li><span>MAU</span></li><li><span>Ingresos</span></li><li><span>ARPDAU</span></li><li><span>Sesiones</span></li><li><span>Tasa DAU/MAU</span></li></ul><p><span>Las métricas disponibles para eventos in-app son: </span></p><ul><li><span>Recuento</span></li><li><span>Usuarios únicos</span></li><li><span>Ingresos</span></li></ul></td></tr><tr><td colspan="2"><h4> <br/><strong><span id="activity-summary-table"></span>Tabla de resumen de actividad</strong> </h4></td></tr><tr><td> </td><td><p>La tabla de resumen de actividad:</p><ul><li>Muestra hasta 50 fuentes de medios con datos sobre impresiones, clics, instalaciones, etc. (Para obtener todos los datos, utiliza <a href="./master-api-user-acquisition-metrics-via-api" target="_blank">Master API</a> o <a href="./pivot-table-user-metrics" target="_blank">Pivot).</a> </li><li>Está ordenada por el número de sesiones.</li><li>Te permite profundizar hasta el nivel de campaña (no es posible profundizar más allá de este nivel).</li><li>Es una buena manera de ver cuántos DAUs son nuevos y cuántos son usuarios existentes (DAUs menos instalaciones).</li></ul><p><span>Para utilizar la tabla de resumen:</span></p><ul><li><span>Refina los datos mostrados usando los campos Filtrar por y Agrupar por.</span></li><li><span>Las columnas de la tabla se pueden ordenar haciendo clic en el encabezado de cada columna.</span></li><li>Filtra por <strong>Eventos in-app</strong> para limitar la visualización a eventos específicos.</li><li>Cambia entre diferentes tipos de vista:<ul><li> <strong>Resumen:</strong> El total de todos los eventos in-app seleccionados</li><li> Eventos <strong><strong>in</strong>-app:</strong> Desglosado por evento in-app</li></ul></li></ul></td></tr></tbody></table>

</Accordion>

<div id="highlevel-tab-previous-twelvemonths" />

<Accordion title="Pestaña de alto nivel: últimos doce meses">

![ActivityHiLevel.png](https://files.readme.io/42636f5b13dca3a2209ea295c02e784175dfc92a2523c861220b87baed859541-4420194466065.png)

La pestaña ofrece una visión general del rendimiento de la actividad de la aplicación a lo largo de doce meses y cuenta con los siguientes gráficos: 

* Usuarios activos e ingresos
* Ganancias brutas mensuales: ingresos, costos, beneficios brutos

</Accordion>

## Especificaciones y limitaciones

| Especificaciones | Observaciones |
| --- | --- |
| Actualización de los datos | <ul><li>**Métricas:** En tiempo real. Ver la imagen a continuación.</li><li>**Métricas promedio**: A diario. Mira la imagen a continuación. **Nota**: Las métricas promedio no se calculan en tiempo real para evitar distorsiones debido a datos de días incompletos. Si el rango de fechas incluye el día actual, sucede lo siguiente:<ul><li>Si el rango es solo para el día actual: no se muestran resultados promedio.</li><li>Si el rango incluye el día actual: el promedio se calcula sin incluir datos de este día.</li></ul></li><li>**Procesamiento de datos del día anterior:** El procesamiento de datos comienza a medianoche UTC para los datos del día anterior. Para las aplicaciones que operan en zonas horarias por detrás de UTC (UTC-), esto significa que su día local puede seguir en curso cuando empieza el procesamiento, lo que puede hacer que los datos aparezcan inicialmente incompletos. Los datos restantes se procesan y se incorporan al día siguiente.</li><li>Ingresos publicitarios: <Anchor target="_blank" href="/marketers/es/docs/roi360-guide-ad-revenue-attribution#data-freshness">Registrado con retraso</Anchor> y reportado bajo la siguiente fecha:<ul><li>Datos agregados: bajo el Día 1 (el día en que se extraen los datos).</li><li>Datos agregados: bajo el Día 1 (el día en que se extraen los datos).</li><li>Datos a nivel de usuario: bajo el Día 0 (el día en que se muestra el anuncio).</li></ul></li></ul>[![Whats_realtime.png](https://files.readme.io/39969fe7395e1b22910aed5d6ca61f6b5603171650f0d0ce88218a2491c02cc5-4407209143953.png)](https://files.readme.io/39969fe7395e1b22910aed5d6ca61f6b5603171650f0d0ce88218a2491c02cc5-4407209143953.png) |
| Desinstalaciones | No compatible |
| Reorientación | A partir del 1 de febrero de 2025, todas las métricas de actividad son datos unificados (UA y retargeting juntos). Sin embargo, antes del 1 de febrero de 2025, las siguientes métricas incluyen solo datos de tráfico de UA:<ul><li>Sesiones totales</li><li>DAU</li><li>MAU</li><li>DAU/MAU</li><li>ARPDAU</li><li>Costo</li><li>Clics</li><li>Impresiones</li><li>Tasa de conversión</li><li>IPC electrónico</li></ul>Unificado es la única vista disponible; los usuarios no pueden cambiar a solo UA o retargeting. |
| ARPDAU | Puede haber discrepancias entre ARPDAU en el dashboard de actividad y pivot. |
| Datos históricos | <ul><li>3 años</li><li>Pestaña de alto nivel: 1 año</li></ul> |
| Rango de visualización | <ul><li>Máximo 2 meses. Si se especifica un periodo más largo, el rango se reduce a dos meses y se muestra un mensaje.</li></ul> |
| Agrupar por geo | <ul><li>La agregación por geo se basa en la geolocalización donde ocurrió la instalación.</li><li>Muestra hasta 62 localizaciones (clasificadas por las sesiones de actividad más destacadas).</li></ul> |
| Agrupar por campaña | Este agrupamiento solo está disponible tras seleccionar fuentes de medios específicas. |
| Valores de dimensión | Los valores de dimensiones como fuente de medios, nombre de la campaña o nombre del activo son sensibles a mayúsculas y minúsculas. Por ejemplo, esto significa que "Facebook" y "facebook" se tratarán como entidades diferentes al filtrar los resultados. Para ver los resultados sin distinción de mayúsculas y minúsculas, utiliza la <Anchor target="_blank" href="/marketers/es/docs/pivot-table-user-metrics">tabla pivot</Anchor>. |
| Agencias | Las agencias no tienen acceso al dashboard de actividad. <Anchor target="_blank" href="/marketers/es/docs/manage-data-access-permissions">Saber más</Anchor> |
| DAU promedio y MAU promedio | Las métricas de DAU promedio y MAU promedio pueden contabilizar al mismo usuario en varias agrupaciones. Por ejemplo, si un usuario instala una aplicación a través de la red A y, más tarde, interactúa con ella a través de la red B, aparecerá en ambas redes al agrupar por Fuente de medios o Campaña. Como resultado, sumar estos valores directamente puede dar lugar a duplicaciones. Para obtener el total preciso de DAU promedio o MAU promedio, consulta la métrica KPI en lugar de agregar los valores de la tabla. |
| Redes publicitarias | Para algunas ad networks, la tabla de actividad puede mostrar dos filas en lugar de una. En estos casos:<ul><li>Las Impresiones, los Clics, el Costo y las Conversiones deben calcularse como la suma de ambas filas.</li><li>Las sesiones de actividad, los ingresos de actividad, el DAU promedio, el MAU promedio, la tasa promedio de DAU/MAU y el ARPDAU deben tomarse solo de una de las filas.</li></ul> |
| Modo heredado de in-apps orgánicos sin atribuir | Si tu aplicación usa el modo heredado **Unattributed organic in-apps** modo, los tiempo real **usuarios activos** orgánicos pueden aparecer por debajo de lo esperado. Los valores se corrigen automáticamente después de que termine el día actual. Para obtener la vista en tiempo real más precisa, te recomendamos cambiar a **first-install mode**.  <br />Saber más sobre <Anchor target="_blank" href="/marketers/es/docs/measure-reinstalls#unattributed-organic-inapps">Unattributed organic in-apps mode</Anchor> y <Anchor target="_blank" href="/marketers/es/docs/measure-reinstalls#attributed-to-the-first-install">first-install mode</Anchor>. |

<div data-zendesk-anchors="activity-dashboard=dashboard-de-actividad h_01HHYHP1HE8G5VA6GSAVTQDDDN=dashboard-de-actividad h_01HHYHP1HEJHKQKCNC5R26ZE3J=consejo dashboard-features-and-layout=caracter%C3%ADsticas-y-dise%C3%B1o-del-dashboard h_01HHYHP1HEBTACW6Q3MJ3QJJ95=caracter%C3%ADsticas-y-dise%C3%B1o-del-dashboard h_01HHYHP1HESQBPYJWK81ZHQDVH=metric-definitions h_01HHYHP1HFZBRTWB8MJ1F6XKZS=ejemplo-c%C3%A1lculo-del-arpdau h_01HHYHP1HFF92WQMQAFKWWNDJK=detailed-tab h_01HHYHP1HFNDXC2E55Q7PDE9WY=headline-metrics h_01HHYHP1HFZR9JN2H0RNAG1QTK=activity-trends h_01HHYHP1HFV8AZ2FYKJ300488A=activity-summary-table h_01HHYHP1HF6FCXPS2SHTH0RBXC=highlevel-tab-previous-twelvemonths specifications-and-limitations=especificaciones-y-limitaciones h_01HHYHP1HFNJF4JJZY4CSVZ3GY=especificaciones-y-limitaciones" />
