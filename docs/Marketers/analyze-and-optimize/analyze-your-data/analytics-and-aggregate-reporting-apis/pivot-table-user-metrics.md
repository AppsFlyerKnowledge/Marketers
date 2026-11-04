---
title: Tabla dinámica—métricas de usuario
metadata:
  keywords:
    - Pivot
    - Advertisers
    - 透视表
    - Premium
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2017-03-16T13:11:23Z'
  edited_at: '2026-08-12T11:49:54Z'
  id: 115001421846
  locale: es
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/es/articles/115001421846
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **De un vistazo**: Ver diferentes métricas de usuario—LTV, actividad, Protect360 y retención. Descarga los resultados en archivos CSV para que los procesen tus sistemas de Business Intelligence. Pivote admite varias aplicaciones en una sola consulta. Úsalo para generar llamadas a la API maestra.

<div id="about-pivot-reports-page" />

## Acerca de la página de informes de pivote

Con Pivote, genera reportes personalizados que contienen métricas de adquisición de usuarios. Pivote viene con una serie de reportes predefinidos que puedes utilizar como base a partir de la cual creas tus reportes personalizados. Los reportes creados por un usuario de la cuenta determinado están disponibles para todos los usuarios.

Los reportes de pivote predefinidos disponibles son:

* Fuente de medios por fecha
* Jerarquía completa
* Análisis de costos

**Nota**: Para que los datos de la campaña sean visibles en los pivotes, las campañas deben tener instalaciones.

<div id="pivot-procedures" />

## Procedimientos de pivote

Crea y modifica pivotes existentes en la interfaz de usuario. Para hacerlo, utiliza los procedimientos de las secciones siguientes.

**Para usar Pivote**:

* En AppsFlyer, desde el menú lateral, seleccione **Analizar** > **Eventos**.  
  Se muestra la lista de reportes definidos actualmente.

<div id="pivot-page-controls-and-options" />

<Accordion title="Página de pivote: controles y opciones">

<Table>
  <thead>
    <tr>
      <th>
        Columna/opción
      </th>
      <th>
        Descripción
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Nombre
      </td>
      <td>
        Selecciona un nombre de reporte para ver el pivote asociado.
      </td>
    </tr>
    <tr>
      <td>
        Clic en columna
      </td>
      <td>
        Algunas columnas, como se indica en la interfaz, se ordenan haciendo clic en el nombre de la columna.
      </td>
    </tr>
    <tr>
      <td>
        Última modificación
      </td>
      <td>
        Última vez que se modificó la estructura del reporte.
      </td>
    </tr>
    <tr>
      <td>
        Modificado por
      </td>
      <td>
        Nombre del usuario que modificó el pivote.
      </td>
    </tr>
    <tr>
      <td>
        Nombre de la aplicación
      </td>
      <td>
        * Si se incluyó una aplicación: el nombre de la aplicación
        * Si se incluyen varias aplicaciones: la cantidad de aplicaciones
      </td>
    </tr>
    <tr>
      <td>
        Acciones
      </td>
      <td>
        | Acción | Observaciones |
        | --- | --- |
        | Duplicar | Copia un reporte de pivote existente. |
        | Cambiar nombre | Cambia el nombre del reporte. |
        | Ver registro de historial | Mira quién manipuló la estructura del reporte, qué se hizo y cuándo. |
        | Copiar enlace de la API maestra | Genera una URL para extraer los datos a través de la <Anchor target="_blank" href="/marketers/es/docs/master-api-user-acquisition-metrics-via-api">API maestra</Anchor>. Para usar la API maestra, es necesario obtener el <Anchor target="_blank" href="/marketers/es/docs/managing-appsflyer-tokens">token de API</Anchor> (se requieren permisos de administrador) que se utilizará en el encabezado de autenticación. |
        | Eliminar | Elimina el pivote seleccionado. |
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="add-a-pivot-report" />

<Accordion title="Agregar un reporte de pivote">

**Para agregar un reporte de pivote**:

1. Haz clic en **Agregar pivote.**  
   Se abre la ventana Nuevo pivote.
2. Ingresa el nombre del pivote.
3. Haga clic en **Enviar**.  
   Se abre la ventana Agregar tabla de pivote.
4. Selecciona aplicaciones, dimensiones y métricas. Establece filtros y ajustes de visualización de valores.

| Sección | Descripción |
| --- | --- |
| Apps | Selecciona 1 o más aplicaciones para incluir en el pivote. |
| Dimensiones | [<Image alt="" src="https://files.readme.io/9b0fda106b5de3401a71ceaeb45bac5cc4215b164e263a1422bf6097a9320553-360002246845.png" width="221px" />](https://files.readme.io/9b0fda106b5de3401a71ceaeb45bac5cc4215b164e263a1422bf6097a9320553-360002246845.png)<br /><br />Utiliza las dimensiones para agrupar, estructurar y ordenar tus reportes de pivote.<br /><br />**Para seleccionar dimensiones**:<ol><li>Haz clic en **Dimensiones.**</li><li>Selecciona una dimensión, luego arrástrala a una sección. Las dimensiones tienen el siguiente impacto en el pivote:<ul><li>**Filas**: las dimensiones colocadas en las filas determinan la jerarquía de agrupación.</li><li>Columnas Columnas: las dimensiones colocadas en columnas multiplican el resultado de toda la tabla de acuerdo con los valores de dimensión.</li></ul></li></ol> |
| KPIs | [<Image alt="" src="https://files.readme.io/6b210b1bdc38ee96ef8b73dcacbac3389b914aaef76a680604e41d4becbad807-360000640109.png" width="294px" />](https://files.readme.io/6b210b1bdc38ee96ef8b73dcacbac3389b914aaef76a680604e41d4becbad807-360000640109.png)<br /><br />Los KPI se agrupan por tipo de la siguiente manera:<ul><li>Característica</li><li><Anchor target="_blank" href="/marketers/es/docs/activity-dashboard#especificaciones-y-limitaciones">ACTIVIDAD</Anchor></li><li>Retención Día de retención, tasa de retención. **Nota**: Nota: Desplázate hacia abajo en la sección de retención para seleccionar Tasas de retención y Protect360 (para cuentas que tienen Protect360 habilitado).</li><li><Anchor target="_blank" href="/marketers/es/docs/master-api-user-acquisition-metrics-via-api#kpis">Sobre las métricas.</Anchor></li></ul>La mayoría de las veces, coloca los KPI en la sección de valor. Si es necesario, los KPI se pueden utilizar como dimensión.<br /><br />Arrastra y suelta el KPI en la sección correspondiente. |
| Los valores | Para cada KPI, establece el método de cálculo seleccionando un operador:<ul><li>Suma</li><li>Recuento</li><li>Máx.</li><li>Mín.</li><li>Calificación</li><li>Promedio</li></ul> |
| Filtros | Coloca los filtros necesarios en la sección de filtros. Configura cómo se establecen los filtros:<ul><li>Texto</li><li>Selección múltiple</li></ul> |

</Accordion>

<div id="view-a-pivot-report" />

<Accordion title="Ver un reporte de pivote">

[![](https://files.readme.io/cb549ba9b17e75f05d723cdb56335232dd40c419ebfe7ecad08b80a71be46296-360002246865.png)](https://files.readme.io/cb549ba9b17e75f05d723cdb56335232dd40c419ebfe7ecad08b80a71be46296-360002246865.png)

**Para ver un reporte de pivote**:

* Selecciona un reporte en la página Pivote para mostrarlo.
* Opciones de visualización de reportes:

| Sección | Descripción |
| --- | --- |
| (1) Dimensiones seleccionadas | La primera columna contiene las dimensiones seleccionadas para los grupos del reporte. Las dimensiones se agrupan según el orden en la página de edición de pivote. En el ejemplo anterior, la dimensión principal es el nombre de la aplicación, seguido de la fuente de medios y terminando con la fecha de instalación. |
| (2) Métricas | El resto de las columnas son KPI seleccionados como **Valores** en la página de edición de pivote. En el ejemplo anterior, el primer KPI son las impresiones, seguidas de los clics, las instalaciones, etc. |
| (3) Filtros | Los filtros establecidos para el reporte en la página de edición de pivote aparecen aquí. Puedes escribir tu cadena de filtrado o seleccionar varios elementos con los cuadros desplegables.<br /><br />[**![](https://files.readme.io/e7f16a6e848b8e9f6942615dd14257b3c0e358cefabbdcfe86c498612fcaae26-115004149786.png)**](https://files.readme.io/e7f16a6e848b8e9f6942615dd14257b3c0e358cefabbdcfe86c498612fcaae26-115004149786.png) |
| (4) Fecha seleccionada | Usa el selector de fechas para refinar tu búsqueda en fechas específicas. Selecciona tu propio intervalo de fechas personalizado o usa uno de los botones de intervalo de fechas preestablecidos. |
| (5) Acciones | Puedes acceder a las mismas acciones por reporte de pivote que están disponibles en la [lista de reportes de pivote](/docs/pivot-table-user-metrics#view-a-pivot-report). |

</Accordion>

<div id="traits-and-limitations" />

## Rasgos y limitaciones

<div id="traits-and-limitations::e6883df" />

<Accordion title="Rasgos y limitaciones">

| Caducado | Observaciones |
| --- | --- |
| Acceso a la red de publicidad para reportar | No |
| Acceso a la agencia | No |
| Transparencia de agencia | Sí |
| Zona horaria específica de la aplicación | Sí<br /><br />Excepción: Excepción: en todos los casos siguientes, AppsFlyer ignora la zona horaria específica de la aplicación y utiliza la zona horaria por defecto UTC +0:<ul><li>El reporte contiene datos de múltiples aplicaciones, y las aplicaciones tienen diferentes zonas horarias.</li><li>Todas las aplicaciones tienen la misma zona horaria, y la zona horaria de por lo menos una de las aplicaciones cambió durante el periodo del reporte de cohortes. Para determinar el periodo del reporte:<ul><li>fecha de inicio La primera fecha en el rango de fechas de conversión.</li><li>Fecha de finalización: se calcula sumando el número de días de la duración que se muestra hasta la última fecha del intervalo de fechas de conversión. Ejemplo: Última fecha: ENE 1, 2019 Duración del informe: 30 días Fecha de finalización. Duración del reporte: 30 días. Fecha de finalización.</li></ul></li></ul> |
| Moneda específica de la aplicación | Los resultados siempre se devuelven en USD. |
| Datos orgánicos | Incluidos |
| Datos no orgánicos | Incluidos |
| Actualización de los datos | Actualización de datos: Diariamente. La actualización de los datos es equivalente a la de la <Anchor target="_blank" href="/marketers/es/docs/master-api-user-acquisition-metrics-via-api">API maestra</Anchor>. |
| Acceso de usuario a la cuenta | Sí |
| Ingresos de retargeting | Incluidos |
| Cambios de nombre de la campaña | Pivot no alinea el costo del nombre de la campaña con el nombre de la campaña recientemente reportado. Esto significa que cada nombre de campaña utilizado tendrá un costo asociado. |
| Datos de retargeting | <ul><li>En general, usa <Anchor target="_blank" href="/marketers/es/docs/cohort-and-retention-dashboard">Cohorte</Anchor> para ver datos de retargeting.</li><li>Los KPI de actividad para el tráfico posterior al 1 de febrero de 2025 incluyen datos unificados (UA y retargeting juntos).</li></ul> |
| Datos de costes | AppsFlyer obtiene los datos de costos principalmente a través de la API de costos. Los datos los proporcionan los partners integrados. <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">Lista de dimensiones por partner integrado.</Anchor> |
| Tasa de retención | Para obtener la tasa de retención, incluye las instalaciones en el reporte. |
| Máximo de filas por reporte | 200 000 |
| Datos históricos | <ul><li>Datos de LTV: 5 años</li><li>Datos de actividad: 3 años</li></ul> |
| DAU medio y MAU medio | Cuando se usa DAU promedio o MAU promedio con la agregación Suma en cualquier agrupación (por ejemplo, fuente de medios o campaña), los totales pueden incluir recuentos de usuarios duplicados. Esto ocurre cuando un usuario realiza tanto una instalación como un re-engagement dentro del periodo seleccionado, lo que hace que aparezca en varias agrupaciones. |

</Accordion>

<div data-zendesk-anchors="pivot-reports-page=acerca-de-la-p%C3%A1gina-de-informes-de-pivote h_01HJR8389QPFKR9X6V52N7PHMM=acerca-de-la-p%C3%A1gina-de-informes-de-pivote pivot-procedures=procedimientos-de-pivote h_01HJR8389QPNRX8Y26VQWN0ZXP=procedimientos-de-pivote pivot-page%E2%80%94controls-and-options=pivot-page-controls-and-options h_01HJR8389QDDWR8ZKCSDZGVAGP=pivot-page-controls-and-options h_01HJR8389R2C1E42JN9NFMS4CJ=add-a-pivot-report h_01HJR8389SQ40HZ8EXQME4807S=view-a-pivot-report traits-and-limitations=rasgos-y-limitaciones h_01HJR8389SPJZG6AYGABB17V1N=rasgos-y-limitaciones h_01HJR8389S19TVMVR60ZYAJMAA=traits-and-limitations::e6883df" />
