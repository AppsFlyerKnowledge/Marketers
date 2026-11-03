---
title: Análisis de cohortes a través de Data Locker
metadata:
  keywords:
    - Advertisers
    - Premium Feature
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2021-10-14T08:46:00Z'
  edited_at: '2026-08-12T11:49:40Z'
  id: 4408945472529
  locale: es
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/es/articles/4408945472529
---
> **En resumen:** El análisis de cohortes en Data Locker incluye datos agregados de todos los elementos de la estructura publicitaria. Los reportes recogen datos de los usuarios atribuidos en los últimos 365 días. Este reporte está disponible para los anunciantes que tengan raw data, API de cohorte o ambos, como parte de su suscripción. Esto significa que no se requiere una suscripción a Data Locker para este reporte.

## Análisis de cohortes en Data Locker

En algunas ocasiones, la atribución de raw data en AppsFlyer está <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions">restringida</Anchor> debido a políticas de compartición de datos de las fuentes de medios o de tus <Anchor target="_blank" href="/marketers/es/docs/apply-aggregated-advanced-privacy-framework">políticas de preservación de la privacidad.</Anchor> Esta restricción incluye todos los campos relacionados con la atribución, como campaña y conjunto de anuncios. Los reportes de cohorte te proporcionan datos agregados que se pueden utilizar como alternativa a los raw data.

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQ8q_4xv83wHkl4fs6jndEffRu-RHsPobBRfxDG-bUNXb0pOnvJH4QT0nXKdWvi3JPtVUBegTFbxIEe/pub?output=xlsx">Descargar reporte de ejemplo</Anchor>

<div id="enable-data-locker" />

<Accordion title="Habilitar Data Locker">

El reporte está disponible para los suscriptores de Data Locker, API de cohorte y raw data. Para habilitar el reporte en <Anchor target="_blank" href="/marketers/es/docs/data-locker-for-marketers">Data Locker,</Anchor> completa uno de los siguientes procedimientos.

| ¿Obtienes datos actualmente a través de Data Locker? | Procedimiento |
| --- | --- |
| Sí | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)Para agregar los reportes de cohorte a Data Locker:<ol><li>En AppsFlyer, desde el menú lateral, selecciona **Reporte > Data Locker**.</li><li>Selecciona todos los reportes en la sección **Análisis de cohorte**.</li><li>Haz clic en **Guardar configuración**.<br />Los reportes estarán disponibles al día siguiente a las 10:00 UTC.</li></ol> |
| No | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)**Para configurar Data Locker**:<ol><li>Completa la configuración inicial de Data Locker (<Anchor target="_blank" href="/marketers/es/docs/data-locker-for-marketers#set-up-data-locker">anunciante</Anchor> \| <Anchor target="_blank" href="/partners/es/docs/data-locker-for-partners">partner</Anchor>).</li><li>Agrega los reportes de cohorte a Data Locker:<ol><li>En AppsFlyer, desde el menú lateral, selecciona **Reporte > Data Locker**.</li><li>Selecciona todos los reportes en la sección **Análisis de cohorte**.</li><li>Haz clic en **Guardar configuración**.<br />Los reportes estarán disponibles al día siguiente a las 10:00 UTC.</li></ol></li></ol> |

</Accordion>

Puedes cargar los datos en tus sistemas de BI y usarlos como parte de tus procesos de rendimiento y optimización de campañas.

**Métricas disponibles**

Las métricas disponibles incluyen ingresos, usuarios únicos que realizan un evento y el número de veces que ocurre el evento. Para calcular métricas relacionadas con el costo, como ROI y ROAS, se necesitan tanto métricas de ingresos como de costos. Las métricas de ingresos están en el cohorte y las métricas de costos son proporcionadas por <Anchor target="_blank" href="/marketers/es/docs/set-up-and-use-roi360-cost-etl-reports">ROI360 Cost ETL</Anchor>.

<div id="facts" />

<Accordion title="Datos sobre análisis de cohortes">

| Reportes disponibles | Los reportes siguientes están disponibles para descargar. Los tipos de reportes se describen con más detalle en el <Anchor target="_blank" href="/marketers/es/docs/cohort-and-retention-dashboard#cohort-principles">Dashboard de cohorte</Anchor>.<ul><li>**Adquisición de usuarios:** se atribuye a una fuente de medios de adquisición de usuarios, incluyendo el LTV durante las ventanas de reactivación.</li><li>**Retargeting:** se atribuye a una fuente de medios de retargeting para eventos que ocurren:<ul><li>Durante una ventana de re-engagement</li><li>Como resultado de reatribuciones</li></ul></li><li>**Unificado:** muestra datos bajo la última fuente de medios táctiles que lleva al usuario de acuerdo con las reglas de <Anchor target="_blank" href="/marketers/es/docs/resolve-retargeting-double-attribution">doble atribución</Anchor> de AppsFlyer. Esto significa que el LTV durante los re-engagements se muestra bajo la fuente de medios de retargeting y no bajo la de UA.</li></ul> |
| --- | --- |
| Periodo del reporte | Usuarios que han convertido en los últimos 365 días. Es decir, cada día el reporte incluye a los usuarios que han convertido en los 365 días anteriores. |
| Estructura del reporte | El esquema de cada reporte (las dimensiones y métricas incluidas) es fijo y no se puede modificar. Consulta [estructura del reporte](/docs/cohort-analytics-via-data-locker#report-structure). |
| Entrega de reportes | Consulta [Habilitar reportes de cohorte en Data Locker](/docs/cohort-analytics-via-data-locker#enable-data-locker). |
| Actualización de datos | <ul><li>A diario.</li><li>Las métricas se calculan utilizando los datos disponibles a medianoche en horario UTC. Es decir, al final del día.</li><li>Los reportes están disponibles en Data Locker en la carpeta de fecha-hora (dt) a las 10:00 UTC. Por ejemplo, los datos del lunes están disponibles el martes a las 10:00 UTC en la carpeta del lunes.</li></ul> |
| Impacto de las políticas de retención de partners | Considera que algunos partners implementan una política de retención de datos. En este caso, los eventos ocurridos después del fin del periodo de retención se consideran orgánicos en los reportes de cohorte.<br /><br />Ejemplo: La SRN A tiene una política de retención de datos de 180 días. Los eventos de usuario hasta el día 180 se atribuyen al SRN A. Los eventos que ocurren después de 180 días se consideran orgánicos. |

</Accordion>

<div id="report-structure" />

<Accordion title="Estructura del reporte">

El reporte se compone de dimensiones y métricas.

El formato de los campos es como se indica a continuación:

* **Dimensiones**: Cadena. La longitud máxima de la cadena es dinámica y, en la mayoría de los casos, depende de cómo se llenen los elementos de la jerarquía publicitaria.
* **Métricas**: Número. **Nota:** El formato del campo selected\_currency es una cadena de texto.

#### Dimensiones

<Table>
  <thead>
    <tr>
      <th>
        Nombre del campo
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
        --
      </td>
    </tr>
    <tr>
      <td>
        fuente\_de\_medios
      </td>
      <td>
        --
      </td>
    </tr>
    <tr>
      <td>
        tipo\_de\_conversión
      </td>
      <td>
        Valores posibles: install, install\_unified (para instalaciones en el reporte unificado), re-engagement, re-attribution.
      </td>
    </tr>
    <tr>
      <td>
        tipo\_táctil\_atribuido
      </td>
      <td>
        Valores posibles: click, impressions, pre-install, unknown, tv, null.
      </td>
    </tr>
    <tr>
      <td>
        días\_post\_atribución
      </td>
      <td>
        * Número de días transcurridos desde la fecha de conversión (no desde la marca de tiempo específica de la conversión).
        * Consejo: ¡Consejo! Utiliza esto para calcular los días de retención y KPIs.
      </td>
    </tr>
    <tr>
      <td>
        Cadena
      </td>
      <td>
        * Fecha en que un usuario realiza un evento específico.
        * Formato: aaaa-mm-dd
        * Ejemplo: Fecha en que un usuario realizó un evento determinado en la aplicación. En caso de conversión.
        * ¡Atención! ¡Nota! Si event\_name es af\_conversion, la fecha del evento y la fecha de conversión serán iguales.
      </td>
    </tr>
    <tr>
      <td>
        fecha\_de\_conversión
      </td>
      <td>
        * Fecha de la conversión.
        * Formato: aaaa-mm-dd
        * Ejemplo: Fecha de instalación.
      </td>
    </tr>
    <tr>
      <td>
        nombre\_del\_evento
      </td>
      <td>
        Identifica el evento. Algunos nombres de eventos tienen un significado específico, mientras que otros se refieren a eventos in-app establecidos por el anunciante. 

        | nombre\_del\_evento | ¿Qué hizo el usuario? |
        | --- | --- |
        | af\_conversion | Usuario convertido. Utiliza conversion\_type para identificar si se trata de una instalación, un re-engagement o una reatribución. |
        | af\_session | Abrió la aplicación. |
        | cohort\_uninstalls | Desinstaló la aplicación. |
        | Evento in-app definido por el anunciante. | Se realizó un evento in-app. |
      </td>
    </tr>
    <tr>
      <td>
        campaña única
      </td>
      <td>
        Jerarquía de campañas.

        Considera: No se admiten cambios de nombre de campaña. Por lo tanto, varios nombres pueden estar asociados a un ID de campaña.
      </td>
    </tr>
    <tr>
      <td>
        id\_campaña
      </td>
      <td>
        Jerarquía de campañas.
      </td>
    </tr>
    <tr>
      <td>
        conjunto de anuncios
      </td>
      <td>
        Jerarquía de campañas.
      </td>
    </tr>
    <tr>
      <td>
        id\_anuncio
      </td>
      <td>
        Jerarquía de campañas.
      </td>
    </tr>
    <tr>
      <td>
        anuncio
      </td>
      <td>
        Jerarquía de campañas.
      </td>
    </tr>
    <tr>
      <td>
        id\_adset
      </td>
      <td>
        Jerarquía de campañas.
      </td>
    </tr>
    <tr>
      <td>
        channel
      </td>
      <td>
        Jerarquía de campaña.

        [Actualizado el 27 de octubre de 2021] Actualmente, los Meta Ads no rellenan el canal en los datos proporcionados a través del mecanismo Google Install Referrer.
      </td>
    </tr>
    <tr>
      <td>
        id\_sitio
      </td>
      <td>
        Jerarquía de campañas.
      </td>
    </tr>
    <tr>
      <td>
        es\_atribución\_primaria
      </td>
      <td>
        Utilízalo para identificar y deduplicar datos de retargeting.
      </td>
    </tr>
    <tr>
      <td>
        geolocalización
      </td>
      <td>
        Código de país ISO derivado de la dirección IP del usuario.
      </td>
    </tr>
    <tr>
      <td>
        agencia
      </td>
      <td>
        * Compatibilidad con la transparencia de agencias.
        * En el caso de agencias no transparentes, puede haber varias filas con el mismo nombre de campaña si el anunciante y la agencia realizan campañas con el mismo nombre. No te preocupes. Las filas no están duplicadas.
      </td>
    </tr>
    <tr>
      <td>
        instalar\_tienda\_aplicaciones
      </td>
      <td>
        Solo para aplicaciones Android: La tienda de Android desde donde se descargó la aplicación. Rellenado por los anunciantes que implementan la <Anchor target="_blank" href="/marketers/es/docs/set-up-multi-store-android-attribution">atribución en Android para múltiples tiendas</Anchor>. Si está en blanco, significa Google Play Store.
      </td>
    </tr>
    <tr>
      <td>
        palabras clave
      </td>
      <td>
        Palabra(s) utilizada(s) en la búsqueda online del usuario. reporte de la ad network.
      </td>
    </tr>
    <tr>
      <td>
        keyword\_id
      </td>
      <td>
        [Campo disponible desde el 27 de abril de 2022] ID de palabra clave devuelto por la ad network.
      </td>
    </tr>
  </tbody>
</Table>

#### Métricas

| Nombre del campo | Descripción | Formato |
| --- | --- | --- |
| usuarios\_únicos | Número de usuarios únicos que realizaron el evento en ese día. | Número |
| ingresos\_usd | <ul><li>Monto de ingresos en USD. Por ejemplo, $100.56 se refleja como 100.56.</li><li>Máximo de 2 posiciones después del punto decimal.</li></ul> | Número |
| recuento\_eventos | Número de veces que ocurrió el evento. | Número |
| selected\_currency | Código de moneda de 3 letras (USD, EUR) configurado por ti en los ajustes de la aplicación. Formato <Anchor target="_blank" href="http://www.xe.com/symbols.php#section1">ISO-4217</Anchor>. Es la moneda usada para mostrar ingresos en Cohorte en la interfaz de usuario. | Cadena |
| revenue\_selected\_currency | <ul><li>Cantidad de ingresos en la moneda seleccionada. Por ejemplo, si la moneda seleccionada es EUR, entonces €1234.56 se refleja como 1234.56.</li><li>Máximo de 2 posiciones después del punto decimal</li></ul> | Número |

</Accordion>

<div id="bi-developer-considerations" />

<Accordion title="Consideraciones para desarrolladores de BI">

**Alcance de los datos en el reporte**

Los reportes incluyen instalaciones de adquisición de usuarios, reatribución de retargeting y re-engagements, y sus eventos in-app relacionados.

Puedes cargar reportes unificados, de adquisición de usuarios y de retargeting por separado o todos juntos en tu BI. Si los cargas juntos y deseas filtrar las vistas por tu cuenta:

* Para unificados, utiliza el campo is\_primary\_attribution=true o null.
* Para adquisición de usuarios, utiliza conversion\_type=Install.
* Para retargeting, utiliza conversion\_type=re-engagement o re-attribution.

Si solo utilizas la vista unificada en tu proceso de carga de datos, puedes usar la lógica para dividir los datos entre tipos de campaña, es decir, atribución de usuarios (instalaciones) y retargeting (re-engagements). Para hacerlo, usa conversion\_type=install, install\_unified, re-engagement o re-attribution. Consulta <Anchor target="_blank" href="/marketers/es/docs/resolve-retargeting-double-attribution">Doble atribución de eventos de retargeting.</Anchor>

**Consideraciones a nivel de campo**

* Usa los días posteriores a la atribución para facilitar el cálculo de métricas de retención.
* Cálculo de usuarios únicos usando las dimensiones de nombre de campaña e ID de campaña: Si puedes ignorar la precisión del nombre de la campaña, puedes sumar el recuento único por ID de campaña y las métricas serán correctas.
* Puedes agregar los datos usando los campos de jerarquía de la campaña.
* Los ingresos en USD se calculan usando el tipo de cambio del día del evento.
* Los eventos de ingresos publicitarios se incluyen cuando están disponibles, pero pueden actualizarse con un retraso de hasta 3 días.

**Consideraciones generales**

Los datos de todas las aplicaciones se proporcionan en un solo archivo. Usa el campo ID de aplicación para segregar los datos por aplicación o configura Data Locker para hacerlo.

</Accordion>

<div id="use-cases" />

<Accordion title="Casos de uso">

A continuación, algunos ejemplos de aplicaciones prácticas y populares de datos de cohorte que los desarrolladores de BI pueden extraer a través de Data Locker. Cada ejemplo se ilustra mediante una declaración SQL y un ejemplo visual en Excel.

#### **1. Cálculo de la retención**

En el siguiente ejemplo:

* Calculamos la retención del día 1 y del día 7, así como el número total de instalaciones por campaña y anuncio.
* Sumamos el recuento de eventos por evento de conversión filtrando `event_name` para que sea `af_conversion`.
* Específicamente, analizamos las campañas de adquisición de usuarios en el reporte unificado filtrando los datos para que `conversion_type IN (install, install_unified)`.

**Consulta SQL**

```sql
select
    campaign_id, ad_id,
    sum(if(event_name = 'af_conversion', event_count,0)) as installs,
    sum(if(event_name = 'af_session' and days_post_attribution = 1, unique_users,0)) / sum(if(event_name = 'af_conversion', event_count,0)) as retention_day1,
    sum(if(event_name = 'af_session' and days_post_attribution = 7, unique_users,0)) / sum(if(event_name = 'af_conversion', event_count,0)) as retention_day7
from YOUR_DATA_LOCKER_REPORT
where
    conversion_date between '2023-06-01' and '2023-06-08'
    and app_id = YOUR_APP
group by 1,2
```

**Ejemplo en Excel**

| ID de campaña | ID del anuncio | Instalaciones | Día 1 de retención | Día 7 de retención |
| --- | --- | --- | --- | --- |
| 12345678 | 987654 | 100 | 30% | 10% |
| 98765432 | 123456 | 200 | 25% | 15 % |
| 07315466 | 613770 | 300 | 20% | 12 % |

#### **2. Cálculo del ARPU de múltiples eventos in-app**

En el siguiente ejemplo:

* Calculamos el ARPU de múltiples eventos in-app por campaña.
* Analizamos específicamente las campañas de retargeting filtrando los datos de modo que `conversion_type=re-engagement` y `conversion_type=re-attribution`.
* Sumamos el recuento de eventos por evento de conversión filtrando `event_name` para que sea `af_conversion`.
* Sumamos los ingresos de múltiples eventos, en este caso `af_purchase` y `af_coins`.
* Establece `days_post_attribution` en el mínimo necesario (en este caso, 7) para minimizar la carga de procesamiento de datos.

**Consulta SQL**

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

**Ejemplo en Excel**

| ID de campaña | Tipo de conversión | OPCIONAL<br /><br />Día 1 | OPCIONAL<br /><br />Día 3 | OPCIONAL<br /><br />Día 7 |
| --- | --- | --- | --- | --- |
| 12345678 | re-engagement | 6.23 | 5.11 | 2.34 |
| 98765432 | re-engagement | 3.57 | 1.34 | 4.86 |
| 07315466 | Reatribución | 7.41 | 6.79 | 5.29 |

#### **3. Cálculo de la tasa de conversión de eventos in-app para un día de cohorte específico**

En el siguiente ejemplo:

* Calcula la tasa de conversión del evento in-app del día 0 para múltiples dimensiones (como fecha de conversión, región, campaña, anuncio e ID del sitio).
* Analiza datos unificados (tanto campañas de UA como de retargeting) filtrando los datos de modo que `is_primary_attribution=true`.
* Sumamos el recuento de eventos por evento de conversión filtrando `event_name` para que sea `af_conversion`.
* Establece `days_post_attribution` en el mínimo necesario (en este caso, 7) para minimizar la carga de procesamiento de datos.

**Consulta SQL**

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

**Ejemplo en Excel**

| Fecha de conversión | Geografía | ID de campaña | ID del anuncio | ID del sitio | Día 0 de af\_complete\_tutorial |
| --- | --- | --- | --- | --- | --- |
| 7 de noviembre de 2022 | Estados Unidos | 12345678 | 123456 | site\_123 | 45% |
| 5 de noviembre de 2022 | Reino Unido | 98765432 | nulo | site\_654 | 70% |
| 31 de octubre de 2022 | Corea | 07315466 | nulo | nulo | El 63 % |

#### **4. Cálculo de instalaciones diarias**

En el siguiente ejemplo:

* Calcula el número de instalaciones por ID de aplicación, fecha de conversión, fuente de medios, nombre de evento y tipo de conversión.
* En el reporte unificado, filtra los datos para mostrar instalaciones de UA (no de retargeting) configurando `conversion_type` como `install` o `install_unified`.
* Suma las instalaciones configurando `event_name` como `af_conversion`.

**Consulta SQL**

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

**Ejemplo en Excel**

| ID de aplicación | Fecha de conversión | Fuente de medios | Nombre del evento | Total |
| --- | --- | --- | --- | --- |
| id123456789 | 7 de noviembre de 2022 | adnet1\_int | af\_conversion | 105 |
| id123456789 | 5 de noviembre de 2022 | adnet2\_int | af\_conversion | 216 |
| id123456789 | 31 de octubre de 2022 | adnet3\_int | af\_conversion | 327 |

#### **5. Cálculo de los ingresos de Facebook Ads**

En el siguiente ejemplo:

* Calcula los ingresos del día 3 de Facebook por fecha de conversión e ID de aplicación.
* Analiza los datos de Facebook filtrándolos para que `media_source='Facebook Ads'`.
* Establece `days_post_attribution` en el mínimo necesario (en este caso, 3) para reducir la carga de procesamiento de datos.

**Consulta SQL**

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

**Ejemplo en Excel**

| Fecha de conversión | ID de aplicación | Fuente de medios | Ingresos<br /><br />Día 3 |
| --- | --- | --- | --- |
| 7 de noviembre de 2022 | id123456789 | adnet1\_int | 400.45 |
| 5 de noviembre de 2022 | id123456789 | adnet2\_int | 99.23 |
| 31 de octubre de 2022 | id123456789 | adnet3\_int | 13.34 |

#### **6. Cálculo del ARPU por ID de palabra clave de ASA para hasta 365 días de cohorte**

En el siguiente ejemplo:

* Calcula el ARPU de Apple Search Ads por ID de palabra clave hasta el día 365 de cohorte.
* Analiza los datos de Apple Search Ads filtrando los datos de modo que `media_source='Apple Search Ads'`.
* Sumamos el recuento de eventos por evento de conversión filtrando `event_name` para que sea `af_conversion`.

**Consulta SQL**

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

**Ejemplo en Excel**

| Fuente de medios | ID de palabra clave | OPCIONAL<br /><br />Día 365 |
| --- | --- | --- |
| adnet1\_int | 123456 | 57.019,93 |
| adnet2\_int | 987654 | 64.867,84 |
| adnet3\_int | 666854 | 48.160,02 |

#### **7. Calculando el ARPU del día 7 por tiempo de atribución por geo**

El siguiente ejemplo muestra cómo utilizar los <Anchor target="_blank" href="/marketers/es/docs/cohort-and-retention-dashboard#trend-type%E2%80%94kpi-by-attribution-time">KPIs por tiempo de atribución</Anchor>. En este ejemplo, nosotros:

* Calculamos el ARPU del día 7 por fecha de atribución para cada geo.
* Los resultados están ordenados por número de conversiones, mostrando las 20 principales geografías.
* Datos filtrados para que `conversion_type='install'`.
* La primera columna muestra la geo. La segunda columna muestra las conversiones totales. Las columnas siguientes muestran los ingresos del día 7 para cada día especificado como fila en la consulta.

**Consulta SQL**

```sql
select
    geolocalización,
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
    // Si estás consultando datos de reportes unificados, edita la línea siguiente a: and conversion_type IN ('install', 'install_unified')
    and conversion_type = 'install'
    and app_id = 'YOUR_APP'
group by 1
order by 2 desc
limit 20
```

**Ejemplo en Excel**

| Geografía | Conversiones totales | ARPU Día 7 para el 11/07/2023 | ARPU Día 7 para el 12/07/2023 | ARPU Día 7 para el 13/07/2023 | ARPU Día 7 para el 14/07/2023 | ARPU Día 7 para el 15/07/2023 | ARPU Día 7 para el 16/07/2023 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Corea del Sur | 120.660 | $7.798,89 | $6.997,37 | $8.258,95 | $9.050,21 | $10.018,04 | $13.765,73 |
| Canadá | 35.099 | $64.867,84 | $7.050,19 | $5.656,33 | $9.553,75 | $8.632,41 | $11.308,06 |
| Chile | 26.750 | $48.160,02 | $21.249,55 | $22.584,57 | $22.584,57 | $31.118,91 | $41.145,22 |

</Accordion>

## Información adicional

<div id="traits-and-limitations" />

<Accordion title="Características y limitaciones">

| Caducado |  |
| --- | --- |
| Datos de costos | <ul><li>No disponible. <Anchor target="_blank" href="/marketers/es/docs/set-up-and-use-roi360-cost-etl-reports">Usar Cost ETL</Anchor>.</li><li>Ver también <Anchor target="_blank" href="/marketers/es/docs/combine-cost-etl-and-cohort-reports-via-data-locker">combinar Cost ETL con reportes de cohorte</Anchor>.</li></ul> |
| Cambios de nombre de la campaña | No está soportado. |
| Actualización de datos | Diario UTC. Los reportes están en la carpeta de fecha y hora (dt) del Data Locker del día del reporte, a las 10:00 UTC del día siguiente. |
| Ingresos de anuncios | <ul><li>Disponible</li><li>Para los eventos af\_ad\_revenue, la métrica de usuarios únicos no está disponible para las fechas entre el 5 de octubre de 2022 y el 16 de febrero de 2023.</li></ul> |
| Truemoney | El USD y la moneda específica de la app están disponibles por fila |
| Zona horaria | <ul><li>UTC</li><li>La zona horaria específica de la aplicación está disponible con el <Anchor target="_blank" href="/marketers/es/docs/advanced-aggregated-reports-in-data-locker">reporte avanzado con zona horaria de cohorte agregada</Anchor>.</li></ul> |
| Datos orgánicos | Disponible |
| Días posteriores a la conversión (instalación, reatribución, re-engagement) | <ul><li>Se dispone de 365 días de datos posteriores a la instalación.</li><li>1.095 días disponibles con <Anchor target="_blank" href="/marketers/es/docs/advanced-aggregated-reports-in-data-locker">reportes agregados avanzados</Anchor>.</li></ul> |
| Transparencia de agencia | <ul><li>Compatible</li><li>Los datos de X Ads y Meta Ads siempre son transparentes.</li></ul> |
| Segregación de apps | Compatible |
| Datos de SKAN | No incluidos. Es decir, los datos proporcionados por postbacks de iOS. |
| Reinstalaciones | <ul><li>Si los eventos posteriores a la reinstalación son considerados orgánicos no atribuidos:<ul><li>Se incluirán solo a partir del 26 de mayo de 2024. <Anchor target="_blank" href="/marketers/es/docs/bulletin-cohort-data-includes-unattributed-sessions-and-events">Saber más</Anchor></li><li>El tiempo de instalación se basa en el campo <Anchor target="_blank" href="/marketers/es/docs/raw-data-field-dictionary#device-info::dfd9504e">device\_download\_time</Anchor>.</li><li>No se cuentan para las mediciones de usuarios únicos y de retención.</li></ul></li><li>Si los eventos posteriores a la reinstalación se atribuyen a la primera instalación, siempre se incluyen. <Anchor target="_blank" href="/marketers/es/docs/unique-users">Saber más</Anchor></li></ul> |

</Accordion>

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/combine-cost-etl-and-cohort-reports-via-data-locker">Combinar Cost ETL y reportes de cohorte</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/cohort-and-retention-dashboard">Dashboard de cohorte</Anchor>

<div data-zendesk-anchors="cohort-analytics-in-data-locker=an%C3%A1lisis-de-cohortes-en-data-locker 01H7WG3CA1DDAN79D1PBPE0RJ3=an%C3%A1lisis-de-cohortes-en-data-locker 01H7WG3CA1ZMNTGZ5B8FNXNC4A=enable-data-locker 01H7WG3CA179D6VCWYPCJ1G49M=facts 01H7WG3CA1R3PZCKSGWC90E7RC=report-structure dimensions=dimensiones 01H7WG3CA14PQ2PJ58FX8TE6ZH=dimensiones metrics=m%C3%A9tricas 01H7WG3CA24VQKFVP99S82GCXZ=m%C3%A9tricas 01H7WG3CA2C3HV8YT5ZMP9E0QY=bi-developer-considerations 01H7WG3CA2YF03SC6RBMCJYYVX=use-cases 1-calculating-retention=1-c%C3%A1lculo-de-la-retenci%C3%B3n h_01HMTZ0DZWN54HBQ0ZTY0VFNFM=1-c%C3%A1lculo-de-la-retenci%C3%B3n 2-calculating-arpu-of-multiple-inapp-events=2-c%C3%A1lculo-del-arpu-de-m%C3%BAltiples-eventos-in-app h_01HMTZ0DZWHZ77RYWYAQEJV7X5=2-c%C3%A1lculo-del-arpu-de-m%C3%BAltiples-eventos-in-app 3-calculating-inapp-event-conversion-rate-for-a-specific-cohort-day=3-c%C3%A1lculo-de-la-tasa-de-conversi%C3%B3n-de-eventos-in-app-para-un-d%C3%ADa-de-cohorte-espec%C3%ADfico h_01HMTZ0DZW7VA6T6MQY7BY1JZT=3-c%C3%A1lculo-de-la-tasa-de-conversi%C3%B3n-de-eventos-in-app-para-un-d%C3%ADa-de-cohorte-espec%C3%ADfico 4-calculating-daily-installs=4-c%C3%A1lculo-de-instalaciones-diarias h_01HMTZ0DZWARZFAQ9R4VF56YN3=4-c%C3%A1lculo-de-instalaciones-diarias 5-calculating-revenue-from-facebook-ads=5-c%C3%A1lculo-de-los-ingresos-de-facebook-ads h_01HMTZ0DZW74HWW6Z3VDWDMGRF=5-c%C3%A1lculo-de-los-ingresos-de-facebook-ads 6-calculating-arpu-per-asa-keyword-id-for-up-to-365-cohort-days=6-c%C3%A1lculo-del-arpu-por-id-de-palabra-clave-de-asa-para-hasta-365-d%C3%ADas-de-cohorte h_01HMTZ0DZWSN83V0TEHVM2H5XS=6-c%C3%A1lculo-del-arpu-por-id-de-palabra-clave-de-asa-para-hasta-365-d%C3%ADas-de-cohorte calculating-arpu-days-0-7-by-attribution-time-per-geo=7-calculando-el-arpu-del-d%C3%ADa-7-por-tiempo-de-atribuci%C3%B3n-por-geo 01H8XYTJVQ1YFBHPWVPP9D7MJ8=7-calculando-el-arpu-del-d%C3%ADa-7-por-tiempo-de-atribuci%C3%B3n-por-geo additional-information=informaci%C3%B3n-adicional 01H7WG3CA255TG9HW150RW1QTX=informaci%C3%B3n-adicional 01H7WG3CA2Y59D2EVMN3YFFY1W=traits-and-limitations h_01HDNZ8A0QH74CGSEG6TKKARJP=consulta-tambi%C3%A9n" />
