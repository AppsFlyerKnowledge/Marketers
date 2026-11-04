---
title: '[Beta cerrada] Reportes agregados avanzados en Data Locker'
metadata:
  keywords:
    - Premium
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
  created_at: '2024-03-06T10:46:12Z'
  edited_at: '2026-08-12T11:49:28Z'
  id: 23127074968721
  locale: es
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/es/articles/23127074968721
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En resumen:** Los reportes agregados avanzados en Data Locker contienen datos agregados con una calidad, precisión, granularidad y volumen óptimos e ilimitados.

<div id="advanced-aggregated-reports-in-data-locker" />

## Reportes agregados avanzados en Data Locker

Reportes agregados avanzados en Data Locker:

* Proporciona una manera eficiente y que preserve la privacidad de construir tus sistemas de BI internos basados ​​en datos agregados: Datos de atribución, eventos e ingresos, con todas las dimensiones y métricas posibles.
* Puedes cargar los datos en tus sistemas de BI y utilizarlos como parte de los procesos de optimización y rendimiento de tu campaña.
* Obtén la mejor calidad con precisión: Los datos llegan <Anchor target="_blank" href="/marketers/es/docs/about-data-freshness-and-timezone-support#intraday-during-the-day">varias veces al día</Anchor> y se actualizan con cada versión posterior de un reporte con todos los datos disponibles para ese día.
* Te ayuda a aumentar los raw data que pueden estar limitados y <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions">restringidos</Anchor> debido a las políticas de intercambio de datos de fuentes de medios o tus <Anchor target="_blank" href="/marketers/es/docs/apply-aggregated-advanced-privacy-framework">políticas de preservación de la privacidad</Anchor>. Las restricciones afectan campos relacionados con la atribución, como campaña y anuncio.

<div id="setup" />

## Configuración

Para obtener reportes agregados avanzados, completa uno de los siguientes procedimientos.

| ¿Actualmente obtienes datos a través de Data Locker? | Procedimiento |
| --- | --- |
| Sí | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)Para agregar los reportes a Data Locker:<ol><li>En AppsFlyer, en el menú lateral, selecciona **Reporte > Data Locker**.</li><li>Selecciona todos los reportes que desees obtener.</li><li>Haz clic en **Guardar configuración**.<br />Los reportes estarán disponibles al día siguiente.</li></ol> |
| No | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)**Para configurar Data Locker**:<ol><li>Completa la configuración inicial de Data Locker (<Anchor target="_blank" href="/marketers/es/docs/data-locker-for-marketers#set-up-data-locker">anunciante</Anchor> \| <Anchor target="_blank" href="/partners/es/docs/data-locker-for-partners">partner</Anchor>).</li><li>Agrega los reportes a Data Locker:<ol><li>En AppsFlyer, en el menú lateral, selecciona **Reporte > Data Locker**.</li><li>Selecciona todos los reportes que desees obtener.</li><li>Haz clic en **Guardar configuración**.<br />Los reportes estarán disponibles al día siguiente.</li></ol></li></ol> |

<div id="reports-available" />

## Reportes disponibles

<div id="cohort-versioned-report" />

<Accordion title="Reporte versionado de cohorte">

<div id="report-facts" />

### Reportar hechos

| Resumen general | El reporte versionado por cohortes contiene todos los datos agregados, por cohortes, con la granularidad de todas las dimensiones de la campaña. El reporte se actualiza cada pocas horas para maximizar la actualidad y precisión de los datos.<br /><br /><Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vT8NQKO287TxXpdTYpIASL55t4muIt9G3lnkEE436FQhNn5_14DfYgf0ztbm1VVZXI4ecPaGktdixS7/pub?output=xlsx">Descargar un reporte de muestra</Anchor> |
| --- | --- |
| Reportes disponibles | Los siguientes reportes están disponibles para descargar. Los tipos de reportes se describen con más detalle en el dashboard de cohortes.<ul><li>**Adquisición de usuarios:** atribuida a una fuente de medios de adquisición de usuarios, incluido el LTV, que se produce durante las ventanas de re-engagement.</li><li>**Retargeting:** atribuido a una fuente de medios de retargeting para eventos que ocurren:<ul><li>Durante una ventana de re-engagement.</li><li>Como resultado de las reatribuciones.</li></ul></li><li>**Unificado:** muestra datos bajo la fuente de medios de último toque, trayendo al usuario según las reglas de <Anchor target="_blank" href="/marketers/es/docs/resolve-retargeting-double-attribution">doble atribución</Anchor> de AppsFlyer. Lo que significa que el LTV que ocurre durante las nuevas interacciones se muestra debajo de la fuente de medios de retargeting y no bajo la fuente de medios de UA.</li></ul> |
| Período de reporte | Usuarios que realizaron conversiones durante los 1.095 días anteriores. En otras palabras, cada día, los reportes incluyen eventos de usuarios que realizaron conversiones durante los 1.095 días anteriores. |
| Estructura del reporte | El esquema del reporte (las dimensiones y métricas incluidas) es fijo y no se puede editar. |
| Actualización de datos | <ul><li>A diario. Los reportes se envían cada pocas horas.</li><li>Los reportes son para los datos de ese día. Es decir, el 18 de abril, cada versión del reporte contiene todos los datos actuales del 18 de abril. [Saber más](/docs/advanced-aggregated-reports-in-data-locker#versiones-de-reportes-y-calidad-de-los-datos-1)</li></ul> |
| Zona horaria | UTC |
| Estructura de directorios y nombres de archivos | [Saber más](/docs/advanced-aggregated-reports-in-data-locker#estructura-del-reporte) |
| Impacto de las políticas de retención de partners | Considera que algunos partners implementan una política de retención de datos. En este caso, los eventos que ocurren después del final del período de retención no se tienen en cuenta en los reportes de cohorte.<br /><br />Ejemplo: SRN A tiene una política de retención de datos de 180 días. Los eventos de usuario hasta el día 180 se atribuyen al SRN A. Los eventos que ocurren después de 180 días no se tienen en cuenta. |

<div id="report-structure" />

### Estructura del reporte

El reporte se compone de dimensiones y métricas.

El formato de los campos es el siguiente:

* **Dimensiones**: String. La longitud máxima del string es dinámica y en la mayoría de los casos depende de cómo se completan los elementos de la jerarquía publicitaria.
* **Métricas**: Number. **Nota:** El formato del campo moneda\_seleccionada es tipo string.  
  Las métricas disponibles son los ingresos, los usuarios únicos que realizan un evento y el número de ocurrencias del evento. Para calcular métricas relacionadas con los costos, como el ROI y el ROAS, necesitas métricas tanto de ingresos como de costos. Las métricas de ingresos están en Cohorte y las métricas de costos las proporciona <Anchor target="_blank" href="/marketers/es/docs/set-up-and-use-roi360-cost-etl-reports">ROI360 Cost ETL</Anchor>.

<div id="dimensions" />

#### Dimensiones

<Table>
  <thead>
    <tr>
      <th>
        Nombre de campo
      </th>
      <th>
        Descripción
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        id\_aplicación
      </td>
      <td>

      </td>
    </tr>
    <tr>
      <td>
        fuente\_de\_medios
      </td>
      <td>

      </td>
    </tr>
    <tr>
      <td>
        tipo\_de\_conversión
      </td>
      <td>
        Valores posibles: instalación, instalación unificada (que representa instalaciones en el reporte unificado), re-engagement, reatribución
      </td>
    </tr>
    <tr>
      <td>
        tipo\_táctil\_atribuido
      </td>
      <td>
        Valores posibles: clic, impresiones, preinstalación, desconocido, tv, nulo
      </td>
    </tr>
    <tr>
      <td>
        días\_post\_atribución
      </td>
      <td>
        * La cantidad de días transcurridos desde la fecha de conversión (no la marca de tiempo de conversión específica).
        * Consejo: ¡Consejo! Utiliza esto para calcular los días de retención y KPIs.
      </td>
    </tr>
    <tr>
      <td>
        Cadena
      </td>
      <td>
        * La fecha en que un usuario realiza un evento determinado.
        * Formato: aaaa-mm-dd
        * Ejemplo: La fecha en que un usuario realizó un evento determinado en la aplicación. En el caso de una conversión.
        * ¡Atención! ¡Nota! Si event\_name es af\_conversion, la fecha del evento y la fecha de conversión serán iguales.
      </td>
    </tr>
    <tr>
      <td>
        fecha\_de\_conversión
      </td>
      <td>
        * La fecha en que ocurrió la conversión.
        * Formato: aaaa-mm-dd
        * Ejemplo: La fecha de instalación
      </td>
    </tr>
    <tr>
      <td>
        nombre\_del\_evento
      </td>
      <td>
        Identifica el evento. Algunos nombres de eventos tienen un significado específico, mientras que otros se relacionan con eventos in-app establecidos por el anunciante en la aplicación. 

        | nombre\_del\_evento | Qué hizo el usuario |
        | --- | --- |
        | af\_conversion | Usuario convertido. Utilice conversion\_type para identificar si se trata de una instalación, un re-engagement o una reatribución. |
        | af\_session | Abre la aplicación |
        | cohort\_uninstalls | Desinstaló la aplicación |
        | Evento in-app definido por el anunciante | Realizó un evento in-app en la aplicación. |
      </td>
    </tr>
    <tr>
      <td>
        campaña única
      </td>
      <td>
        Jerarquía de campañas

        Ten en cuenta lo siguiente: No se admiten cambios de nombre de campaña. En consecuencia, se pueden asociar varios nombres con un ID de campaña determinado.
      </td>
    </tr>
    <tr>
      <td>
        id\_campaña
      </td>
      <td>
        Jerarquía de campañas
      </td>
    </tr>
    <tr>
      <td>
        conjunto de anuncios
      </td>
      <td>
        Jerarquía de campañas
      </td>
    </tr>
    <tr>
      <td>
        id\_anuncio
      </td>
      <td>
        Jerarquía de campañas
      </td>
    </tr>
    <tr>
      <td>
        anuncio
      </td>
      <td>
        Jerarquía de campañas
      </td>
    </tr>
    <tr>
      <td>
        id\_adset
      </td>
      <td>
        Jerarquía de campañas
      </td>
    </tr>
    <tr>
      <td>
        canal
      </td>
      <td>
        Jerarquía de campañas

        [Actualizado el 27 de octubre de 2021] Actualmente, los Meta Ads no completan el canal con los datos proporcionados a través del mecanismo de Google Install Referrer.
      </td>
    </tr>
    <tr>
      <td>
        id\_sitio
      </td>
      <td>
        Jerarquía de campañas
      </td>
    </tr>
    <tr>
      <td>
        es\_atribución\_primaria
      </td>
      <td>
        Utilizalo para identificar y deduplicar datos de retargeting.
      </td>
    </tr>
    <tr>
      <td>
        geolocalización
      </td>
      <td>
        El código de país ISO derivado de la dirección IP del usuario.
      </td>
    </tr>
    <tr>
      <td>
        agencia
      </td>
      <td>
        * Soporta la transparencia de la agencia.
        * En el caso de agencias no transparentes, puede haber varias filas que contengan el mismo nombre de campaña si tanto el anunciante como la agencia ejecutan campañas con el mismo nombre. No te preocupes. Las filas no están duplicadas.
      </td>
    </tr>
    <tr>
      <td>
        instalar\_tienda\_aplicaciones
      </td>
      <td>
        Solo aplicaciones Android: La tienda de Android desde donde se descargó la aplicación. Rellenado por anunciantes que implementan la <Anchor target="_blank" href="/marketers/es/docs/set-up-multi-store-android-attribution">atribución de Android en múltiples tiendas</Anchor>. Si está en blanco, significa Google Play Store.
      </td>
    </tr>
    <tr>
      <td>
        palabras clave
      </td>
      <td>
        Palabra(s) utilizada(s) en la búsqueda online del usuario. Según informa la red publicitaria.
      </td>
    </tr>
    <tr>
      <td>
        keyword\_id
      </td>
      <td>
        ID de palabra clave devuelta por la red publicitaria.
      </td>
    </tr>
  </tbody>
</Table>

<div id="metrics" />

#### Métricas

| Nombre de campo | Descripción | Formato |
| --- | --- | --- |
| usuarios\_únicos | Número de usuarios únicos del día que realizan el evento. | Cantidad |
| ingresos\_usd | <ul><li>Cantidad de ingresos en USD. Por ejemplo, $100,56 se refleja como 100,56.</li><li>Máximo de 2 lugares después del punto decimal.</li></ul> | Cantidad |
| recuento\_eventos | Número de ocurrencias de eventos. | Cantidad |
| selected\_currency | Código de la moneda de 3 letras (USD, EUR) establecido por ti en la configuración de la aplicación. Formato <Anchor target="_blank" href="http://www.xe.com/symbols.php#section1">ISO-4217</Anchor>. Esta es la misma moneda utilizada para mostrar los ingresos en Cohorte en la interfaz de usuario. | Cadena |
| revenue\_selected\_currency | <ul><li>Cantidad de ingresos en la moneda seleccionada. Por ejemplo, si la moneda seleccionada es EUR, entonces 1234,56 € se refleja como 1234,56</li><li>Máximo de 2 lugares después del punto decimal</li></ul> | Cantidad |
| first\_inapp | <ul><li>Número de usuarios que realizan el evento por primera vez después de su conversión.</li><li>La suma de las métricas de first\_inapp te da el recuento acumulado de usuarios únicos para el evento.</li></ul> | Cantidad |

<div id="directory-and-filename-structure" />

#### Estructura de directorios y nombres de archivos

La ruta al reporte consta de la siguiente jerarquía de carpetas:

Con el siguiente formato: `/t=cohort_unified_versioned/dt=/version=/`

<div id="report-folder-hierarchy" />

#### Jerarquía de carpetas de reportes

Un ejemplo de la jerarquía de carpetas de reportes versionados por cohortes en el segmento de anunciantes:

```
bucket
|
└── t=cohort_unified_versioned
    |
    ├── dt=2024-05-05
    |   |
    |   └── version=1714890235
    |   |    |
    |   |    ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |    |
    |   |    ├── part-00001-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |    │
    |   |    └── part-00002-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |
    |   |
    |   └── version=1714890286
    |        |
    |        ├── part-00000-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        |
    |        ├── part-00001-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        │
    |        └── part-00002-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |   |
    .   . 
    .   .
```

**Leyenda:**

* **dt**: teFecha en que ocurrieron los hechos incluidos en el reporte.
* **t:** tipo de reporte.
* **versión**: Marca de tiempo de Unix cuando se creó la versión.

<div id="report-versions-and-data-freshness" />

### Versiones de reportes y calidad de los datos

* A diario. Los reportes se envían cada pocas horas.
* Los reportes son para todos los datos disponibles actualmente para el día. Es decir, el 18 de abril, cada versión del reporte contiene todos los datos disponibles hasta ese momento para el 18 de abril.
* **Ingiere únicamente la última versión del reporte disponible.**

| Versión | El reporte incluye datos que AppsFlyer recibió antes de (hora en UTC) | Caso de uso | El reporte de tiempo está disponible (hora en UTC) |
| --- | --- | --- | --- |
| 1 | Día 0 a las 4h | Datos parciales del día 0 | Día 0 a las 8h |
| 2 | Día 0 a las 8h | Datos parciales del día 0 | Día 0 a la 1 PM |
| 3 | Día 0 a las 12h | Datos parciales del día 0 | Día 0 a las 6 PM |
| 4 | Día 0 a las 4 PM | Datos parciales del día 0 | Día 0 a las 9 PM |
| 5 | Día 0 a las 8 PM | Datos parciales del día 0 | Día 0 a las 11:59 PM |
| 6 | Día 0 a las 11:59 PM | Datos completos de conversión y eventos in-app para el día 0 (excluidos los eventos S2S que AppsFlyer recibe entre el día 0 a las 11:59 PM y el día 1 a las 2 AM) | Día 1 a las 4 AM |
| 7 | Día 1 a las 3 AM | Datos completos de conversión y eventos in-app para el día 0, y cualquier dato de ingresos por publicidad disponible actualmente enviado a través de S2S. | Día 1 a las 8h |
| 8 | Día 1 a las 11 AM | Datos completos de conversión y eventos in-app para el día 0, y cualquier dato de ingresos por publicidad disponible actualmente enviado a través de S2S. | Día 1 a las 18h |
| 9 | Día 1 a las 5 PM | Datos completos de conversión y eventos in-app para el día 0, y cualquier dato de ingresos por publicidad disponible actualmente enviado a través de S2S. | Día 1 a las 23:59h |
| 10 | Día 8 a las 7 AM | Datos completos de conversión y eventos in-app para el día 0, y datos completos de ingresos publicitarios enviados a través de S2S, teniendo en cuenta cualquier problema potencial que pueda haber ocurrido en el lado de la red de ingresos publicitarios. | Día 8 a la 1 PM |

</Accordion>

<div id="cohort-timezone-versioned-report" />

<Accordion title="Reporte versionado de la zona horaria de cohorte">

<div id="report-facts-1" />

### Reportar hechos

| Resumen general | El reporte versionado de la zona horaria de cohorte contiene todos los datos agregados, agrupados en cohortes, con la granularidad de todas las dimensiones de la campaña, según las zonas horarias localizadas. El reporte se actualiza cada pocas horas para maximizar la actualidad y precisión de los datos.<br /><br /><Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQk1cZkeJhlx3trW13SjGbD4aWX3LmXZJRDJRApuAJkjB7XAg4nSFUyN0_YoirX-QMHkhFeMHwEmiVj/pub?output=xlsx">Descargar un reporte de muestra</Anchor> |
| --- | --- |
| Reportes disponibles | Los siguientes reportes están disponibles para descargar. Los tipos de reportes se describen con más detalle en el <Anchor target="_blank" href="/marketers/es/docs/cohort-and-retention-dashboard#cohort-principles">dashboard de cohortes.</Anchor><ul><li>**Adquisición de usuarios:** atribuida a una fuente de medios de adquisición de usuarios, incluido el LTV, que se produce durante las ventanas de re-engagement.</li><li>**Retargeting:** atribuido a una fuente de medios de retargeting para eventos que ocurren:<ul><li>Durante una ventana de re-engagement.</li><li>Como resultado de las reatribuciones.</li></ul></li><li>**Unificado:** muestra datos bajo la fuente de medios de último toque, trayendo al usuario según las reglas de <Anchor target="_blank" href="/marketers/es/docs/resolve-retargeting-double-attribution">doble atribución</Anchor> de AppsFlyer. Lo que significa que el LTV que ocurre durante las nuevas interacciones se muestra debajo de la fuente de medios de retargeting y no bajo la fuente de medios de UA.</li></ul> |
| Período de reporte | Usuarios que realizaron conversiones durante los 1.095 días anteriores. En otras palabras, cada día, los reportes incluyen eventos de usuarios que realizaron conversiones durante los 1.095 días anteriores.<br /><br />**Nota**: Si aún no ha comenzado un día en tu zona horaria local, los reportes con versiones de zona horaria llegarán sin datos. |
| Estructura del reporte | El esquema del reporte (las dimensiones y métricas incluidas) es fijo y no se puede editar. |
| Datos actualizados | <ul><li>A diario. Los reportes se envían cada pocas horas.</li><li>Los reportes son para los datos de ese día. Es decir, el 18 de abril, cada versión del reporte contiene todos los datos actuales del 18 de abril. [Saber más](/docs/advanced-aggregated-reports-in-data-locker#versiones-de-reportes-y-calidad-de-los-datos)</li></ul> |
| Zona horaria | Cualquier zona horaria excepto UTC. Es decir, los reportes omiten datos de cualquier aplicación con configuración de zona horaria UTC en AppsFlyer. |
| Estructura de directorios y nombres de archivos | [Saber más](/docs/advanced-aggregated-reports-in-data-locker#estructura-del-reporte-1) |
| Impacto de las políticas de retención de partners | Considera que algunos partners implementan una política de retención de datos. En este caso, los eventos que ocurren después del final del período de retención no se tienen en cuenta en los reportes de cohorte.<br /><br />Ejemplo: SRN A tiene una política de retención de datos de 180 días. Los eventos de usuario hasta el día 180 se atribuyen al SRN A. Los eventos que ocurren después de 180 días no se tienen en cuenta.<br /><br />**Nota**: Los eventos se muestran en el dashboard general como orgánicos. |

<div id="report-structure-1" />

### Estructura del reporte

El reporte se compone de dimensiones y métricas.

El formato de los campos es el siguiente:

* **Dimensiones**: String. La longitud máxima del string es dinámica y en la mayoría de los casos depende de cómo se completan los elementos de la jerarquía publicitaria.
* **Métricas**: Number. **Nota:** El formato del campo moneda\_seleccionada es tipo string.  
  Las métricas disponibles son los ingresos, los usuarios únicos que realizan un evento y el número de ocurrencias del evento. Para calcular métricas relacionadas con los costos, como el ROI y el ROAS, necesitas métricas tanto de ingresos como de costos. Las métricas de ingresos están en Cohorte y las métricas de costos las proporciona <Anchor target="_blank" href="/marketers/es/docs/set-up-and-use-roi360-cost-etl-reports">ROI360 Cost ETL</Anchor>.

<div id="dimensions-1" />

#### Dimensiones

<Table>
  <thead>
    <tr>
      <th>
        Nombre de campo
      </th>
      <th>
        Descripción
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        id\_aplicación
      </td>
      <td>

      </td>
    </tr>
    <tr>
      <td>
        fuente\_de\_medios
      </td>
      <td>

      </td>
    </tr>
    <tr>
      <td>
        tipo\_de\_conversión
      </td>
      <td>
        Valores posibles: instalación, instalación unificada (que representa instalaciones en el reporte unificado), re-engagement, reatribución
      </td>
    </tr>
    <tr>
      <td>
        tipo\_táctil\_atribuido
      </td>
      <td>
        Valores posibles: clic, impresiones, preinstalación, desconocido, tv, nulo
      </td>
    </tr>
    <tr>
      <td>
        días\_post\_atribución
      </td>
      <td>
        * La cantidad de días transcurridos desde la fecha de conversión (no la marca de tiempo de conversión específica).
        * Consejo: ¡Consejo! Utiliza esto para calcular los días de retención y KPIs.
      </td>
    </tr>
    <tr>
      <td>
        Cadena
      </td>
      <td>
        * La fecha en que un usuario realiza un evento determinado.
        * Formato: aaaa-mm-dd
        * Ejemplo: La fecha en que un usuario realizó un evento determinado en la aplicación. En el caso de una conversión.
        * Nota ¡Nota! Si event\_name es af\_conversion, la fecha del evento y la fecha de conversión serán iguales.
      </td>
    </tr>
    <tr>
      <td>
        fecha\_de\_conversión
      </td>
      <td>
        * La fecha en que ocurrió la conversión.
        * Formato: aaaa-mm-dd
        * Ejemplo: La fecha de instalación
      </td>
    </tr>
    <tr>
      <td>
        nombre\_del\_evento
      </td>
      <td>
        Identifica el evento. Algunos nombres de eventos tienen un significado específico, mientras que otros se relacionan con eventos in-app establecidos por el anunciante en la aplicación. 

        | nombre\_del\_evento | Qué hizo el usuario |
        | --- | --- |
        | af\_conversion | Usuario convertido. Utilice conversion\_type para identificar si se trata de una instalación, un re-engagement o una reatribución. |
        | af\_session | Abre la aplicación |
        | cohort\_uninstalls | Desinstaló la aplicación |
        | Evento in-app definido por el anunciante | Realizó un evento in-app en la aplicación. |
      </td>
    </tr>
    <tr>
      <td>
        event\_timezone
      </td>
      <td>
        La zona horaria para:

        * days\_post\_atribution
        * Cadena
        * fecha\_de\_conversión
      </td>
    </tr>
    <tr>
      <td>
        campaña
      </td>
      <td>
        Jerarquía de campañas

        Ten en cuenta lo siguiente: No se admiten cambios de nombre de campaña. En consecuencia, se pueden asociar varios nombres con un ID de campaña determinado.
      </td>
    </tr>
    <tr>
      <td>
        id\_campaña
      </td>
      <td>
        Jerarquía de campañas
      </td>
    </tr>
    <tr>
      <td>
        conjunto de anuncios
      </td>
      <td>
        Jerarquía de campañas
      </td>
    </tr>
    <tr>
      <td>
        id\_anuncio
      </td>
      <td>
        Jerarquía de campañas
      </td>
    </tr>
    <tr>
      <td>
        anuncio
      </td>
      <td>
        Jerarquía de campañas
      </td>
    </tr>
    <tr>
      <td>
        id\_adset
      </td>
      <td>
        Jerarquía de campañas
      </td>
    </tr>
    <tr>
      <td>
        canal
      </td>
      <td>
        Jerarquía de campañas

        [Actualizado el 27 de octubre de 2021] Actualmente, los Meta Ads no completan el canal con los datos proporcionados a través del mecanismo de Google Install Referrer.
      </td>
    </tr>
    <tr>
      <td>
        id\_sitio
      </td>
      <td>
        Jerarquía de campañas
      </td>
    </tr>
    <tr>
      <td>
        es\_atribución\_primaria
      </td>
      <td>
        Utilizalo para identificar y deduplicar datos de retargeting.
      </td>
    </tr>
    <tr>
      <td>
        geolocalización
      </td>
      <td>
        El código de país ISO derivado de la dirección IP del usuario.
      </td>
    </tr>
    <tr>
      <td>
        agencia
      </td>
      <td>
        * Soporta la transparencia de la agencia.
        * En el caso de agencias no transparentes, puede haber varias filas que contengan el mismo nombre de campaña si tanto el anunciante como la agencia ejecutan campañas con el mismo nombre. No te preocupes. Las filas no están duplicadas.
      </td>
    </tr>
    <tr>
      <td>
        instalar\_tienda\_aplicaciones
      </td>
      <td>
        Solo aplicaciones Android: La tienda de Android desde donde se descargó la aplicación. Rellenado por anunciantes que implementan la <Anchor target="_blank" href="/marketers/es/docs/set-up-multi-store-android-attribution">atribución de Android en múltiples tiendas</Anchor>. Si está en blanco, significa Google Play Store.
      </td>
    </tr>
    <tr>
      <td>
        palabras clave
      </td>
      <td>
        Palabra(s) utilizada(s) en la búsqueda online del usuario. Según informa la red publicitaria.
      </td>
    </tr>
    <tr>
      <td>
        keyword\_id
      </td>
      <td>
        ID de palabra clave devuelta por la red publicitaria.
      </td>
    </tr>
  </tbody>
</Table>

<div id="metrics-1" />

#### Métricas

| Nombre de campo | Descripción | Formato |
| --- | --- | --- |
| usuarios\_únicos | Número de usuarios únicos del día que realizan el evento. | Cantidad |
| ingresos\_usd | <ul><li>Cantidad de ingresos en USD. Por ejemplo, $100,56 se refleja como 100,56.</li><li>Máximo de 2 lugares después del punto decimal.</li></ul> | Cantidad |
| recuento\_eventos | Número de ocurrencias de eventos. | Cantidad |
| selected\_currency | Código de la moneda de 3 letras (USD, EUR) establecido por ti en la configuración de la aplicación. Formato <Anchor target="_blank" href="http://www.xe.com/symbols.php#section1">ISO-4217</Anchor>. Esta es la misma moneda utilizada para mostrar los ingresos en Cohorte en la interfaz de usuario. | Cadena |
| revenue\_selected\_currency | <ul><li>Cantidad de ingresos en la moneda seleccionada. Por ejemplo, si la moneda seleccionada es EUR, entonces 1234,56 € se refleja como 1234,56</li><li>Máximo de 2 lugares después del punto decimal</li></ul> | Cantidad |
| first\_inapp | <ul><li>Número de usuarios que realizan el evento por primera vez después de su conversión.</li><li>La suma de las métricas de first\_inapp te da el recuento acumulado de usuarios únicos para el evento.</li></ul> | Cantidad |

<div id="directory-and-filename-structure-1" />

#### Estructura de directorios y nombres de archivos

La ruta al reporte consta de la siguiente jerarquía de carpetas:

Con el siguiente formato: `/t=cohort_unified_timezone_versioned/dt=/version=/`

<div id="report-folder-hierarchy-1" />

#### Jerarquía de carpetas de reportes

Un ejemplo de la jerarquía de carpetas de reportes versionados de zona horaria de cohorte en el grupo de anunciantes:

```
bucket
|
└── t=cohort_unified_timezone_versioned
    |
    ├── dt=2024-05-05
    |   |
    |   └── version=1714890235
    |   |    |
    |   |    ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |    |
    |   |    ├── part-00001-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |    │
    |   |    └── part-00002-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   |
    |   |
    |   └── version=1714890286
    |        |
    |        ├── part-00000-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        |
    |        ├── part-00001-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        │
    |        └── part-00002-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |   |
    .   . 
    .   .
```

**Leyenda:**

* **dt**: teFecha en que ocurrieron los hechos incluidos en el reporte.
* **t:** tipo de reporte.
* **versión**: Marca de tiempo de Unix cuando se creó la versión.

<div id="report-versions-and-data-freshness-1" />

### Versiones de reportes y calidad de los datos

* A diario. Los reportes se envían cada pocas horas.
* Los reportes son para todos los datos disponibles actualmente para el día. Es decir, el 18 de abril, cada versión del reporte contiene todos los datos disponibles hasta ese momento para el 18 de abril.
* Los casos de uso de reportes pueden ser diferentes según tu ubicación geográfica y zona horaria. [Saber más](/docs/advanced-aggregated-reports-in-data-locker#timezone-geos)
* **Ingiere únicamente la última versión del reporte disponible.**

| Versión | El reporte incluye datos que AppsFlyer recibió antes de (hora en UTC) | Caso de uso | El reporte de tiempo está disponible (hora en UTC) |
| --- | --- | --- | --- |
| 1 | Día -1 a las 4h | Geos orientales - datos parciales del día 0 | Día -1 a las 8h |
| 2 | Día -1 a las 8h | Geos orientales - datos parciales del día 0 | Día -1 a las 21h |
| 3 | Día -1 a las 12h | Geos orientales - datos parciales del día 0 | Día -1 a las 16h |
| 4 | Día -1 a las 20h | Geos orientales - datos parciales del día 0 | Día -1 a las 13h |
| 5 | Día -1 a las 18h | Geos orientales - datos parciales del día 0 | Día -1 a las 23:59h |
| 6 | Día -1 a las 23:59h | Geos orientales y centrales - datos parciales del día 0 | Día 0 a las 4 AM |
| 7 | Día 0 a las 4h | Todas las geos - datos parciales del día 0 | Día 0 a las 8 AM |
| 8 | Día 0 a las 8 AM | Todas las geos - datos parciales del día 0 | Día 0 a las 21h |
| 9 | Día 0 a las 12 PM | Todas las geos - datos parciales del día 0 | Día 0 a las 16h |
| 10 | Día 0 a las 20h | Todas las geos - datos parciales del día 0 | Día 0 a las 13h |
| 11 | Día 0 a las 18h | <ul><li>Geos orientales - conversión completa y datos de eventos in-app para el día 0</li><li>Geos centrales y occidentales - datos parciales del día 0</li></ul> | Día 0 a las 11:59 PM |
| 12 | Día 0 a las 11:59 PM | Geos centrales y occidentales - datos parciales del día 0 | Día 1 a las 4h |
| 13 | Día 1 a las 4h | <ul><li>Geos centrales - conversión completa y datos de eventos in-app para el día 0</li><li>Geo occidentales - datos parciales del día 0</li><li>Cualquier dato de ingresos publicitarios disponible actualmente enviado a través de S2S</li></ul> | Día 1 a las 8 AM |
| 14 | Día 1 a las 8h | Geos occidentales: datos parciales del día 0 y cualquier dato de ingresos publicitarios disponible actualmente enviado a través de S2S | Día 1 a las 21h |
| 15 | Día 1 a las 13h | Geos occidentales: datos parciales del día 0 y cualquier dato de ingresos publicitarios disponible actualmente enviado a través de S2S | Día 1 a las 6 PM |
| 16 | Día 1 a las 12h | select conversion\_date, app\_id, media\_source, sum(if(days\_post\_attribution &lt;= 3, revenue\_usd, 0)) as revenue\_day3 from YOUR\_DATA\_LOCKER\_REPORT where conversion\_date between '2022-06-01' and '2023-05-31' and days\_post\_attribution &lt;= 3 and media\_source = 'Facebook Ads' and app\_id in (APP\_ID1, APP\_ID2, ...) group by 1,2,3 | Día 1 a las 16h |
| 17 | ¡Consejo! Utiliza esto para calcular los días de retención y KPI | Geos occidentales: datos parciales del día 0 y cualquier dato de ingresos publicitarios disponible actualmente enviado a través de S2S | ¡Consejo! Utiliza esto para calcular los días de retención y KPI |
| 18 | Día 1 a las 18h | Geos occidentales: datos parciales del día 0 y cualquier dato de ingresos publicitarios disponible actualmente enviado a través de S2S | Día 1 a las 23:59h |
| 19 | Día 1 a las 8 PM | Geos occidentales: conversión completa, datos de eventos in-app para el día 0 y datos completos de ingresos publicitarios enviados a través de S2S | Día 1 a las 11:59 PM |
| 20 | Día 1 a las 23:59h | Datos completos de conversión y eventos in-app para el día 0, y datos completos de ingresos publicitarios enviados a través de S2S, teniendo en cuenta cualquier problema potencial que pueda haber ocurrido en el lado de la red de ingresos publicitarios. | Día 2 a las 4h |
| 21 | Día 8 a las 00:00h | Datos completos de conversión y eventos in-app para el día 0, y datos completos de ingresos publicitarios enviados a través de S2S, teniendo en cuenta cualquier problema potencial que pueda haber ocurrido en el lado de la red de ingresos publicitarios. | Día 8 a las 6h |

</Accordion>

<div id="additional-information" />

## Información adicional

<div id="timezone-geos" />

<Accordion title="Geos de zonas horarias">

Los casos de uso de reportes pueden ser diferentes según tu ubicación geográfica y zona horaria. Utiliza la siguiente tabla para comprender qué geos coinciden con qué zonas horarias.

| Geolocalización | Zona horaria |
| --- | --- |
| Oriental | UTC+12 - UTC+3 |
| Central | UTC+2.5 - UTC-3 |
| Occidental | UTC-3.5 - UTC-12 |

</Accordion>

<div id="bi-developer-considerations" />

<Accordion title="Consideraciones del desarrollador de BI">

**Alcance de los datos en el reporte**

Los reportes contienen instalaciones de adquisición de usuarios y reatribuciones y nuevas interacciones de retargeting, y sus eventos relacionados en la aplicación.

Puedes cargar reportes unificados, de adquisición de usuarios y de retargeting por separado o juntos en tu BI. Si los cargas juntos y deseas filtrar las vistas por tu cuenta:

* Para unificado, utiliza el campo is\_primary\_attribution=true o null.
* Para la adquisición de usuarios, utiliza conversion\_type=Install.
* Para retargeting, utiliza conversion\_type=re-engagement o re-attribution.

Si solo utilizas la vista unificada en tu proceso de carga de datos, puedes usar la lógica para dividir los datos entre tipos de campaña, es decir, atribución de usuario (instalaciones) y retargeting (nuevas interacciones). Para hacerlo, utiliza conversion\_type=install, install-unified, re-engagement o re-attribution. Consulta <Anchor target="_blank" href="/marketers/es/docs/resolve-retargeting-double-attribution">Doble atribución de eventos de retargeting.</Anchor>

**Consideraciones a nivel de campo**

* Usa los días posteriores a la atribución para permitir un cálculo sencillo de las métricas de retención.
* Calcular usuarios únicos utilizando las dimensiones del nombre de la campaña y del ID de la campaña: Si puedes ignorar la granularidad del nombre de la campaña, puedes sumar el recuento único del ID de la campaña y las métricas serán correctas.
* Puedes agregar los datos utilizando los campos de jerarquía de campaña.
* Los ingresos en USD se calculan utilizando el tipo de cambio del día del evento.

**Consideraciones generales**

Los datos de todas las aplicaciones son configurables; Puede proporcionarse en un solo archivo o en archivos separados por aplicación.

</Accordion>

<div id="use-cases" />

<Accordion title="Casos de uso">

Los siguientes son ejemplos de algunas aplicaciones prácticas y populares de los datos que los desarrolladores de BI pueden extraer a través de Data Locker. Cada ejemplo está ilustrado por una declaración SQL y un objeto visual de Excel de muestra.

<div id="1-calculate-retention" />

#### **1. Calculando la retención**

En el siguiente ejemplo, nosotros:

* Calculamos la retención el día 1 y el día 7, así como el número total de instalaciones por campaña y anuncio.
* Sumamos el recuento de eventos por evento de conversión filtrando `event_name` para `af_conversion`.
* Analizamos específicamente las campañas de adquisición de usuarios filtrando los datos para que `conversion_type=install`.

**SQL**

```sql
select
    campaign_id, ad_id,
    sum(if(event_name = 'af_conversion', event_count,0)) as installs,
    sum(if(event_name = 'af_session' and days_post_attribution = 1, unique_users,0)) / sum(if(event_name = 'af_conversion', event_count,0)) as retention_day1,
    sum(if(event_name = 'af_session' and days_post_attribution = 7, unique_users,0)) / sum(if(event_name = 'af_conversion', event_count,0)) as retention_day7
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    and conversion_type = 'install'
    and app_id = YOUR_APP
group by 1,2
```

**Excel**

| ID de campaña | ID de anuncio | Instalaciones | Retención del Día 1 | Retención del Día 7 |
| --- | --- | --- | --- | --- |
| 12345678 | 987654 | 100 | 30% | 10% |
| 98765432 | 123456 | 200 | 25% | 15 % |
| 07315466 | 613770 | 300 | 20% | 12 % |

<div id="2-calculate-arpu-of-multiple-in-app-events" />

#### **2. Calculando el ARPU de múltiples eventos en la aplicación**

En el siguiente ejemplo, nosotros:

* Calculamos el ARPU de múltiples eventos in-app por campaña.
* Analizamos específicamente las campañas de retargeting filtrando los datos para que `conversion_type=re-engagement` y `conversion_type=re-attribution`.
* Sumamos el recuento de eventos por evento de conversión filtrando `event_name` para `af_conversion`.
* Sumamos los ingresos de múltiples eventos, en este caso `af_purchase` y `af_coins`.
* Colocamos `days_post_attribution` al mínimo necesario (en este caso, 7) para minimizar la carga de procesamiento de datos.

**SQL**

```sql
select
    campaign_id,
    sum(if(days_post_attribution <= 1 and event_name in ('af_purchase', 'af_coins') , revenue_usd, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day1,
    sum(if(days_post_attribution <= 3 and event_name in ('af_purchase', 'af_coins') , revenue_usd, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day3,
    sum(if(days_post_attribution <= 7 and event_name in ('af_purchase', 'af_coins') , revenue_usd, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day7
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    and days_post_attribution <= 7
    and conversion_type in ('re-engagement', 're-attribution')
    and app_id = YOUR_APP
group by 1
```

**Excel**

| ID de campaña | Tipo de conversión | OPCIONAL<br /><br />Día 1 | OPCIONAL<br /><br />Día 3 | OPCIONAL<br /><br />Día 7 |
| --- | --- | --- | --- | --- |
| 12345678 | re-engagement | 6.23 | 5.11 | 2.34 |
| 98765432 | re-engagement | 3.57 | 1.34 | 4.86 |
| 07315466 | Reatribución | 7.41 | 6.79 | 5.29 |

<div id="3-calculate-in-app-event-conversion-rate-for-a-specific-cohort-day" />

#### **3. Calculando la tasa de conversión de eventos in-app para un día de cohorte específico**

En el siguiente ejemplo, nosotros:

* Calculamos la tasa de conversión del evento in-app del Día 0 para múltiples dimensiones (en este caso, fecha de conversión, geo, campaña, anuncio e ID del sitio).
* Analizamos datos unificados (tanto campañas de UA como de retargeting) filtrando los datos para que `is_primary=true`.
* Sumamos el recuento de eventos por evento de conversión filtrando `event_name` para `af_conversion`.
* Colocamos `days_post_attribution` al mínimo necesario (en este caso, 7) para minimizar la carga de procesamiento de datos.

**SQL**

```sql
select
    conversion_date, geo, campaign_id, ad_id, site_id,
    sum(if(days_post_attribution = 0 and event_name = 'af_complete_tutorial', unique_users, 0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as day0_af_tutorial_conversion
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    and is_primary = true
    and app_id = YOUR_APP
group by 1,2,3,4,5
```

**Excel**

| Fecha de conversión | Geolocalización | ID de campaña | ID de anuncio | ID de sitio | Día 0 af\_complete\_tutorial |
| --- | --- | --- | --- | --- | --- |
| 7 de noviembre de 2022 | Estados Unidos | 12345678 | 123456 | site\_123 | 45% |
| 5 de noviembre de 2022 | Reino Unido | 98765432 | nulo | site\_654 | 70% |
| 31 de octubre de 2022 | Corea | 07315466 | nulo | nulo | El 63 % |

<div id="4-calculate-daily-installs" />

#### **4. Calculando instalaciones diarias**

En el siguiente ejemplo, nosotros:

* Calculamos la cantidad de instalaciones por ID de aplicación, fecha de conversión, fuente de medios, nombre del evento y tipo de conversión.
* Filtramos los datos para mostrar las instalaciones de UA (no el retargeting), configurando `conversion_type` para `install`.
* Sumamos las instalaciones configurando `event_name` para `af_conversion`.

**SQL**

```sql
select
    app_id,
    conversion_date,
    media_source,
    event_name,
    conversion_type,
    sum(events_count) as total
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    and conversion_type = 'install'
    and event_name = 'af_conversion'
    and app_id = YOUR_APP
group by 1,2,3,4,5
```

**Excel**

| ID de aplicación | Fecha de conversión | Fuente de medios | Nombre del evento | Total |
| --- | --- | --- | --- | --- |
| id123456789 | 7 de noviembre de 2022 | adnet1\_int | af\_conversion | 105 |
| id123456789 | 5 de noviembre de 2022 | adnet2\_int | af\_conversion | 216 |
| id123456789 | 31 de octubre de 2022 | adnet3\_int | af\_conversion | 327 |

<div id="5-calculate-revenue-from-facebook-ads" />

#### **5. Calculando los ingresos de los anuncios de Facebook**

En el siguiente ejemplo, nosotros:

* Calculamos los ingresos del Día 3 de Facebook por fecha de conversión e ID de la aplicación.
* Analizamos los datos de Facebook filtrándolos para que `media_source='Facebook Ads'`.
* Colocamos `days_post_attribution` al mínimo necesario (en este caso, 3) para minimizar la carga de procesamiento de datos.

**SQL**

```sql
select
    conversion_date,
    app_id,
    media_source,
    sum(if(days_post_attribution <= 3, revenue_usd, 0)) as revenue_day3
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2022-06-01' and '2023-05-31'
    and days_post_attribution <= 3
    and media_source = 'Facebook Ads'
    and app_id in (APP_ID1, APP_ID2, ...)
group by 1,2,3
group by 1,2,3
```

**Excel**

| Fecha de conversión | ID de aplicación | Fuente de medios | Ingresos<br /><br />Día 3 |
| --- | --- | --- | --- |
| 7 de noviembre de 2022 | id123456789 | adnet1\_int | 400.45 |
| 5 de noviembre de 2022 | id123456789 | adnet2\_int | 99.23 |
| 31 de octubre de 2022 | id123456789 | adnet3\_int | 13.34 |

<div id="6-calculate-arpu-per-asa-keyword-id-for-up-to-365-cohort-days" />

#### **6. Calculando el ARPU por ID de palabra clave de ASA para hasta 365 días de cohorte**

En el siguiente ejemplo, nosotros:

* Calculamos el ARPU de Apple Search Ads por ID de palabra clave hasta el día 365 de cohorte.
* Analizamos los datos de Apple Search Ads filtrándolos para que `media_source='Apple Search Ads'`.
* Sumamos el recuento de eventos por evento de conversión filtrando `event_name` para `af_conversion`.

**SQL**

```sql
select
    media_source,
    keyword_id,
    sum(if(days_post_attribution <= 365, revenue_usd,0)) / sum(if(event_name = 'af_conversion', event_count, 0)) as ARPU_day365
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2022-06-01' and '2023-05-31'
    and media_source = 'Apple Search Ads'
    and app_id = YOUR_APP
group by 1
```

**Excel**

| Calidad de los datos | ID de palabra clave | OPCIONAL<br /><br />Día 365 |
| --- | --- | --- |
| adnet1\_int | 123456 | 57.019,93 |
| adnet2\_int | 987654 | 64.867,84 |
| adnet3\_int | 666854 | 48.160,02 |

<div id="7-calculate-arpu-days-7-by-attribution-time-per-geo" />

#### **7. Calculando el ARPU del Día 7 por tiempo de atribución por geo**

El siguiente ejemplo ilustra cómo utilizar los <Anchor target="_blank" href="/marketers/es/docs/cohort-and-retention-dashboard#trend-type%E2%80%94kpi-by-attribution-time">KPIs por tiempo de atribución</Anchor>. En el ejemplo, nosotros:

* Calculamos el ARPU del Día 7 por fecha de atribución por geo.
* Los resultados se ordenan por la cantidad de conversiones y se muestran las 20 geos principales.
* Los datos se filtran para que `conversion_type='install'`.
* La primera columna muestra geo. La segunda columna muestra las conversiones totales. A partir de entonces, las columnas muestran los días de ingresos del Día 7 para cada día especificado como fila en la consulta.

**SQL**

```sql
select
    geo,
    sum(if(event_name = 'af_conversion', event_count, 0)) total_conversions,
    sum(if(cohort_day = '2023-07-11' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-11' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_11,
    sum(if(cohort_day = '2023-07-12' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-12' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_12,
    sum(if(cohort_day = '2023-07-13' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-13' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_13,
    sum(if(cohort_day = '2023-07-14' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-14' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_14,
    sum(if(cohort_day = '2023-07-15' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-15' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_15,
    sum(if(cohort_day = '2023-07-16' and days_post_attribution <= 7, revenue_usd, 0)) / sum(if(cohort_day = '2023-07-16' and event_name = 'af_conversion', event_count, 0)) as ARPU_day7_2023_07_16
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-07-11' and '2023-07-16'
    and days_post_attribution <= 7
    and conversion_type = 'install'
    and app_id = 'YOUR_APP'
group by 1
order by 2 desc
limit 20
```

**Excel**

| Geolocalización | Conversiones totales | ARPU Día 7 para 2023-07-11 | ARPU Día 7 para 2023-07-12 | ARPU Día 7 para 2023-07-13 | ARPU Día 7 para 2023-07-14 | ARPU Día 7 para 2023-07-15 | ARPU Día 7 para 2023-07-16 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Corea del Sur | 120.660 | $7.798,89 | $6.997,37 | $8.258,95 | $9.050,21 | $10.018,04 | $13.765,73 |
| Canadá | 35.099 | $64.867,84 | $7.050,19 | $5.656,33 | $9.553,75 | $8.632,41 | $11.308,06 |
| Chile | 26.750 | $48.160,02 | $21.249,55 | $22.584,57 | $22.584,57 | $31.118,91 | $41.145,22 |

<div id="8-calculate-purchases-day-7-after-conversion" />

#### **8. Calculando compras del Día 7 después de la conversión**

En el siguiente ejemplo, nosotros:

* Calculamos los usuarios únicos acumulados que realizan eventos af\_purchase 7 días después de su conversión (en vista unificada).
* Calculamos la tasa de conversión del evento, es decir, la proporción de conversiones que realizan una compra en los 7 días posteriores a su conversión.
* Los datos se filtran para que `conversion_type='install'`.
* Los datos se agrupan por aplicación, fecha de conversión, fuente de medios, campaña y anuncio.

**SQL**

```sql
select
    app_id, conversion_date, media_source, campaign, adset,
    sum(if(event_name = 'af_conversion', event_count,0)) as unified_conversions,
    sum(if(event_name = 'af_purchase', first_inapp, 0)) as af_purchase_day_7_cumulative_unique_users,
    concat(
        cast(
            round(
                sum(if(event_name = 'af_purchase', first_inapp, 0)) /
                sum(if(event_name = 'af_conversion', event_count, 0)) * 100.0
            ,2)
        as varchar),
    '%') as af_purchase_day_7_cumulative_unique_users_conversion_rate
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-12-01' and '2023-12-31'
    and is_primary_attribution = true
    and days_post_attribution <= 7
    and app_id in (APP_ID1, APP_ID2, ...)
group by 1,2,3,4,5
```

**Excel**

| ID de aplicación | Fecha de conversión | Fuente de medios | Campaña | Conjunto de anuncios | Conversiones unificadas | D7 af\_purchase acumulativo | D7 tasa de conversión af\_purchase |
| --- | --- | --- | --- | --- | --- | --- | --- |
| id123456789 | 10-03-2025 | adnet1\_int | campaña\_1 | adset\_1 | 100 | 20 | 20% |
| id123456789 | 2024-03-07 | adnet2\_int | campaña\_2 | adset\_2 | 200 | 10 | 5 % |
| id123456789 | 2024-03-31 | adnet3\_int | campaña\_3 | adset\_3 | 150 | 15 | 10% |

<div id="9-calculate-dau" />

#### **9. Calcular DAU**

En el siguiente ejemplo:

* Calcula el DAU de cada día en un intervalo de tiempo seleccionado, agrupado por fuente de medios, campaña y anuncio.
* Los datos se filtran para que `event_name = 'af_session'`.
* Suma los usuarios únicos 1 día a la vez, donde cada fecha es su propia dimensión (columna).

**Nota**: Los eventos se muestran en el dashboard general como orgánicos.

* No puedes sumar varios días (por ejemplo, para obtener WAU o MAU).
* El DAU se basa en la actividad de los usuarios que convirtieron en los últimos 1.095 días. Esto difiere de los datos que pueden verse en el Dashboard de actividad y en los reportes, que no tienen este límite. Consulta «Días posteriores a la conversión» en la [sección de características y limitaciones](/docs/advanced-aggregated-reports-in-data-locker#traits-and-limitations).

**Consulta SQL**

```sql
select
    app_id, conversion_date, media_source, campaign, adset,
    sum(if(event_name = 'af_conversion', event_count,0)) as unified_conversions,
    sum(if(event_name = 'af_purchase', first_inapp, 0)) as af_purchase_day_7_cumulative_unique_users,
    concat(
        cast(
            round(
                sum(if(event_name = 'af_purchase', first_inapp, 0)) /
                sum(if(event_name = 'af_conversion', event_count, 0)) * 100.0
            ,2)
        as varchar),
    '%') as af_purchase_day_7_cumulative_unique_users_conversion_rate
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-12-01' and '2023-12-31'
    and is_primary = True
    and days_post_attribution <= 7
    and app_id in (APP_ID1, APP_ID2, ...)
group by 1,2,3,4,5
```

**Ejemplo en Excel**

| Fuente de medios | Característica | Versión | DAU 6 de agosto | Nota: Si event\_name es af\_conversion, entonces la fecha del evento y la fecha de conversión serán las mismas. | DAU 8 agosto |
| --- | --- | --- | --- | --- | --- |
| adnet1\_int | campaña\_1 | adset\_1 | 475.250 | Calidad de los datos | Calidad de los datos |
| adnet2\_int | campaña\_2 | adset\_2 | Nota: Si event\_name es af\_conversion, entonces la fecha del evento y la fecha de conversión serán las mismas. | beta\_feature.png | 401.232 |
| adnet3\_int | campaña\_3 | conjunto de anuncios\_3 | 290.042 | 570.322 | Divisa |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Rasgos y limitaciones">

| Versión |  |
| --- | --- |
| Datos de costos | <ul><li>No disponible. <Anchor target="_blank" href="/marketers/es/docs/set-up-and-use-roi360-cost-etl-reports">Utiliza Cost ETL</Anchor>.</li><li>Ver también <Anchor target="_blank" href="/marketers/es/docs/combine-cost-etl-and-cohort-reports-via-data-locker">combinar Cost ETL con reportes de cohorte</Anchor>.</li></ul> |
| Cambios del nombre de campaña | No se admite. Utiliza el ID de campaña para agrupar y filtrar si se cambiaron los nombres de las campañas. |
| Datos actualizados | Intradía |
| Ingresos por anuncios | Disponible |
| Truemoney | USD y la moneda específica de la aplicación están disponibles por fila |
| Zona horaria | La zona horaria específica de la aplicación está disponible con el reporte versionado de zona horaria. |
| Datos orgánicos | Disponible |
| Los datos de los días posteriores a la conversión (instalación, reatribución, re-engagement) están disponibles | 1.095 días. |
| Transparencia de Agencias | <ul><li>Compatible</li><li>Los datos de X Ads y Meta Ads son siempre transparentes</li></ul> |
| Segregación de aplicaciones | Compatible |
| Datos SKAN | No incluido. Es decir, los datos los proporcionan los postbacks de iOS. |
| Datos de desinstalación | Las desinstalaciones se procesan diariamente. Por lo tanto, sólo aparecen en reportes que contienen datos completos de un día (sin datos parciales). |
| Reinstalaciones | <ul><li>Reinstalaciones: si los eventos posteriores a la reinstalación se consideran orgánicos no atribuidos, no se incluyen en la Cohorte.<ul><li>Se incluirán solo a partir del 26 de mayo de 2024. <Anchor target="_blank" href="/marketers/es/docs/bulletin-cohort-data-includes-unattributed-sessions-and-events">Más información</Anchor></li><li>El tiempo de instalación se basa en el campo <Anchor target="_blank" href="/marketers/es/docs/raw-data-field-dictionary#device-info::dfd9504e">device\_download\_time</Anchor>.</li><li>No se cuentan para las mediciones de usuarios únicos y de retención.</li></ul></li><li>Si los eventos post-reinstalación se atribuyen a la primera instalación, siempre se incluyen. <Anchor target="_blank" href="/marketers/es/docs/measure-reinstalls#inapp-events-and-how-they-are-attributed">Aprender más</Anchor></li></ul> |

</Accordion>

<div id="see-also" />

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/combine-cost-etl-and-cohort-reports-via-data-locker">Combinar ETL de costos y reportes de cohortes agregados avanzados</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/cohort-and-retention-dashboard">Dashboard de cohorte</Anchor>

<div data-zendesk-anchors="advanced-aggregated-reports-in-data-locker=reportes-agregados-avanzados-en-data-locker h_01HWWH83KNSF4BRGTDJ0JD271G=reportes-agregados-avanzados-en-data-locker setup=configuraci%C3%B3n h_01HWWH83KN9CM7ZY43W01AV6TA=configuraci%C3%B3n reports-available=reportes-disponibles h_01HWWNY76W6RFKX33MXHE4GSBD=reportes-disponibles h_01HWWNR256DRMBNFX3NV8ATNAY=cohort-versioned-report report-facts=reportar-hechos h_01HVRBVXS47K91A6KVV33S1BY6=reportar-hechos report-structure=estructura-del-reporte h_01HWWH83KNE46SPK1MS99XX64D=estructura-del-reporte dimensions=dimensiones 01H7WG3CA14PQ2PJ58FX8TE6ZH=dimensiones metrics=m%C3%A9tricas 01H7WG3CA24VQKFVP99S82GCXZ=m%C3%A9tricas directory-and-filename-structure=estructura-de-directorios-y-nombres-de-archivos h_01HVRDKKQA17SMJFFAEDG7A2X2=estructura-de-directorios-y-nombres-de-archivos the-report-folder-hierarchy-in-aws=jerarqu%C3%ADa-de-carpetas-de-reportes h_01HETBAQVVA750VTE1ABSM2M47=jerarqu%C3%ADa-de-carpetas-de-reportes report-versions-and-data-freshness=versiones-de-reportes-y-calidad-de-los-datos h_01HWWH83KN51RR2VJ2F5N8YQ3J=versiones-de-reportes-y-calidad-de-los-datos h_01HWWNVFCWJ7DZCKKKSBMH9NM5=cohort-timezone-versioned-report report-facts::15e071f=reportar-hechos-1 h_01HWWH83KNPZETHR2TQS2E4QNT=reportar-hechos-1 report-structure::43ffff28=estructura-del-reporte-1 h_01HWWH83KNG0V2ZMZZ7CTV2GE7=estructura-del-reporte-1 01HWSX3FA0K39D9M5RQ7J36Q23=dimensiones-1 01HWSX3FA035Z8W6EPV4Q6E3JP=m%C3%A9tricas-1 01HWSX3FA189EMBJZ1P21YHC45=estructura-de-directorios-y-nombres-de-archivos-1 01HX97NC4F2WCJABSM2NBSBEDN=jerarqu%C3%ADa-de-carpetas-de-reportes-1 report-versions-and-data-freshness::e0755e26=versiones-de-reportes-y-calidad-de-los-datos-1 h_01HWWH83KPS2ANCQKS2B3V529Z=versiones-de-reportes-y-calidad-de-los-datos-1 additional-information=informaci%C3%B3n-adicional h_01HWWH83KPK8535X9EBZVJ9SQK=informaci%C3%B3n-adicional h_01HWWN6GAAD75HPC5GTE40QA37=timezone-geos 01H7WG3CA2C3HV8YT5ZMP9E0QY=bi-developer-considerations 01H7WG3CA2YF03SC6RBMCJYYVX=use-cases 1-Calculate-retention=1-calculando-la-retenci%C3%B3n h_01HMTZ0DZWN54HBQ0ZTY0VFNFM=1-calculando-la-retenci%C3%B3n 2-Calculate-arpu-of-multiple-inapp-events=2-calculando-el-arpu-de-m%C3%BAltiples-eventos-en-la-aplicaci%C3%B3n h_01HMTZ0DZWHZ77RYWYAQEJV7X5=2-calculando-el-arpu-de-m%C3%BAltiples-eventos-en-la-aplicaci%C3%B3n 3-Calculate-inapp-event-conversion-rate-for-a-specific-cohort-day=3-calculando-la-tasa-de-conversi%C3%B3n-de-eventos-in-app-para-un-d%C3%ADa-de-cohorte-espec%C3%ADfico h_01HMTZ0DZW7VA6T6MQY7BY1JZT=3-calculando-la-tasa-de-conversi%C3%B3n-de-eventos-in-app-para-un-d%C3%ADa-de-cohorte-espec%C3%ADfico 4-Calculate-daily-installs=4-calculando-instalaciones-diarias h_01HMTZ0DZWARZFAQ9R4VF56YN3=4-calculando-instalaciones-diarias 5-Calculate-revenue-from-facebook-ads=5-calculando-los-ingresos-de-los-anuncios-de-facebook h_01HMTZ0DZW74HWW6Z3VDWDMGRF=5-calculando-los-ingresos-de-los-anuncios-de-facebook 6-Calculate-arpu-per-asa-keyword-id-for-up-to-365-cohort-days=6-calculando-el-arpu-por-id-de-palabra-clave-de-asa-para-hasta-365-d%C3%ADas-de-cohorte h_01HMTZ0DZWSN83V0TEHVM2H5XS=6-calculando-el-arpu-por-id-de-palabra-clave-de-asa-para-hasta-365-d%C3%ADas-de-cohorte Calculate-arpu-days-0-7-by-attribution-time-per-geo=7-calculando-el-arpu-del-d%C3%ADa-7-por-tiempo-de-atribuci%C3%B3n-por-geo 01H8XYTJVQ1YFBHPWVPP9D7MJ8=7-calculando-el-arpu-del-d%C3%ADa-7-por-tiempo-de-atribuci%C3%B3n-por-geo 8-calculate-purchases-day-7-after-conversion=8-calculando-compras-del-d%C3%ADa-7-despu%C3%A9s-de-la-conversi%C3%B3n h_01J7N4VB83T4KZ6G0Q634ASMHV=8-calculando-compras-del-d%C3%ADa-7-despu%C3%A9s-de-la-conversi%C3%B3n 9-calculate-dau=9-calcular-dau h_01J55D2FFW0XSH3G6AXRS06RPV=9-calcular-dau 01H7WG3CA2Y59D2EVMN3YFFY1W=traits-and-limitations h_01HDNZ8A0QH74CGSEG6TKKARJP=consulta-tambi%C3%A9n" />
