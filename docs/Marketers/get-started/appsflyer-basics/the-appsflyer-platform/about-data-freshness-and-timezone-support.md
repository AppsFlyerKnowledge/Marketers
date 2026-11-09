---
title: Actualización de los datos y soporte de zona horaria
metadata:
  keywords:
    - Reports
    - Advertisers
    - Agencies
    - Ad Networks
    - timezone
    - data freshness
    - data
    - Developers
    - Gray
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
    - Ad Networks
  created_at: '2018-02-19T15:57:01Z'
  edited_at: '2026-10-29T01:13:03Z'
  id: 360000310629
  locale: es
  section: The AppsFlyer platform
  section_id: 6551361489297
  url: https://support.appsflyer.com/hc/es/articles/360000310629
---
> **At a glance:** La actualización de los datos es el período entre la ocurrencia de los eventos y la disponibilidad de los datos en la plataforma.

**Zonas horarias**

<Image align="center" alt="TimeZoneMap.jpg" src="https://files.readme.io/eddfa3df4d43fed82ba5e867eb1278466d1ba51f9fbc2970f62fa61c6659d340-360005463738.jpg" />

<div id="data-freshness-and-support-for-app-specific-time-zones" />

## Actualización de los datos y soporte para zonas horarias específicas de la aplicación

<div id="data-freshness" />

### Actualización de los datos

La plataforma AppsFlyer utiliza diferentes [tipos de actualización de los datos,](/docs/about-data-freshness-and-timezone-support#data-freshness-types) como diaria y en tiempo real. Se utilizan para presentar y hacer que los datos estén disponibles. Cada uno tiene su propia [tasa de actualización de datos](/docs/about-data-freshness-and-timezone-support#data-freshness-rates-and-timezone-support).

Ejemplo: Índices de actualización de datos en el panel de control de Eventos:

* Métrica KPI: en tiempo real
* KPI promedio: diario

<div id="time-zones" />

### Zonas horarias

En la plataforma AppsFlyer, un día comienza a las 00:01 y termina a las 24:00. La zona horaria predeterminada es UTC (GMT). Puedes modificar el valor predeterminado estableciendo una <Anchor target="_blank" href="/marketers/es/docs/changing-app-time-zone-settings">zona horaria específica de la app.</Anchor>

<Accordion title="Principios de fecha y zona horaria">

La hora UTC es constante y no tiene horarios de verano/invierno.

Hemisferios

* Este: Las zonas horarias designadas como UTC+ son aquellas ubicadas al este de UTC.
* Occidental: las zonas horarias designadas como UTC son aquellas ubicadas al oeste de UTC.

<div id="app-specific-time-zone" />

#### Zona horaria específica de la aplicación

Puedes establecer una zona horaria específica de la aplicación. Esto significa que los datos se agrupan en días utilizando la hora local en lugar de UTC.

Ejemplo:

**Pekín:** si la zona horaria específica de la aplicación se establece en Pekín (UTC +8), el día comienza a las 16:01 UTC y finaliza a las 16:00 UTC del día siguiente.

**Los Ángeles**: si la zona horaria específica de la aplicación se establece en Los Ángeles (UTC -8), entonces el día comienza a las 08:01 UTC y finaliza a las 08:00 UTC del día siguiente.

<div id="time-zone-guidelines" />

#### Lineamientos de zona horaria

* Alinea tu zona horaria específica de la aplicación con la zona horaria que establezcas para otros proveedores de servicios de atribución, como Google y Anuncios de Meta.
* Si tienes más de una aplicación, la mejor práctica es configurar todas las aplicaciones en la misma zona horaria. Para ver la configuración de la zona horaria de una aplicación, ve a **Configuración** > **Configuración de la aplicación.**
* La mayoría de los reportes y las herramientas de extracción de datos admiten zonas horarias específicas de la aplicación. Esto incluye reportes de varias aplicaciones si todas las aplicaciones están configuradas en la misma zona horaria específica de la aplicación.

<div id="daily-processing" />

#### Procesamiento diario

Algunos reportes y listas desplegables se procesan una vez al día, esto se conoce como actualización diaria o procesamiento diario. Estos son los principios del procesamiento diario:

* Los datos que pertenecen a un día específico, por ejemplo, el lunes, se recopilan en un *bucket*. El día comienza a las 00:01 y termina a las 24:00 usando la hora específica de la aplicación.
* Los datos recibidos hasta dos horas después de la medianoche se incluyen en el bucket del día. Los datos recibidos hasta las 02:00 del martes se incluyen en el bucket del lunes.
* A las 02:00 hora local, el bucket se cierra y no se pueden agregar más datos a él.
* Los datos recibidos después de las 02:00 se colocan en el siguiente bucket disponible, independientemente de la fecha del evento.
* El procesamiento diario del bucket cerrado comienza dos horas después de la medianoche UTC, independientemente de la zona horaria específica de la aplicación. En aras de la simplicidad, afirmamos que el procesamiento comienza a la medianoche UTC. Esto significa que, dependiendo de la zona horaria local, el bucket debe esperar hasta la medianoche UTC antes de que comience el procesamiento.

**Hemisferio oriental y zona horaria UTC**:

![[SE NECESITA TEXTO ALT DESCRIPTIVO — CONFIRMAR]: diagrama de los tiempos de espera del procesamiento diario para las zonas horarias del hemisferio este](https://files.readme.io/cbea9d910695b39f59b342da6f56fa51df76afc910c4eea60f6dd49fbee2a0d6-8272818122769.png)

* Pueden pasar hasta 11 horas desde que termina el día (hora local) hasta que comienza el procesamiento. Por ejemplo:
  * Pekín (UTC+8): se debe esperar ocho horas antes de que comience el procesamiento
  * Berlín (UTC +1): se debe esperar una hora antes de que comience el procesamiento
  * UTC: sin tiempo de espera.
* Según el tipo de reporte, los datos están disponibles entre 8 y 20 horas después del inicio del procesamiento. Por ejemplo, los datos de Beijing están disponibles a partir de las 16:00 hora local. Los datos de Berlín están disponibles a partir de las 09:00.

**Hemisferio occidental:**

![[SE NECESITA TEXTO ALT DESCRIPTIVO — CONFIRMAR]: diagrama de los tiempos de espera del procesamiento diario para las zonas horarias del hemisferio oeste](https://files.readme.io/ac5e3046b3f55916bb73732801c7e0bdef714cc45b89b6c4d70bbc2009cd64c8-8272698121489.png)

* Pueden pasar hasta 23 horas desde el momento en que finaliza el día hasta que comienza el procesamiento. Por ejemplo:
  * Los Ángeles (UTC -8): se debe esperar 16 horas antes de que comience el procesamiento
  * Nueva York (UTC -5): se debe esperar 19 horas antes de que comience el procesamiento
* Según el tipo de reporte, los datos procesados están disponibles 8-20 horas después del inicio del procesamiento. Por ejemplo, los datos de Los Ángeles están disponibles a partir de las 00:01 hora local dos días después del evento. Los datos de Nueva York están disponibles a partir de las 03:01 hora local dos días después del evento.
* Ejemplo:
  * Los eventos tienen lugar el lunes, hora de Los Ángeles (UTC -8), el procesamiento diario comienza a la medianoche UTC del martes. Esto es Los Ángeles, martes 16:01.
  * Ocho horas después, el miércoles a las 00:01, hora de Los Ángeles, el procesamiento de datos está completo. En términos prácticos, los datos del lunes están disponibles para los anunciantes de Los Ángeles cuando comienzan a trabajar el miércoles por la mañana.

</Accordion>

<Accordion title="Tipos de actualización de datos">

| Calificación | Disponibilidad | Descripción |
| --- | --- | --- |
| Continua (es decir, en tiempo real) | 15–60 minutos después de que ocurra el evento | El procesamiento de datos es continuo. Este término lo distingue del procesamiento por lotes que tiene lugar, por ejemplo, a diario. Los datos continuos se actualizan con un retraso de 15 a 60 minutos después de que se produzca un evento de la siguiente manera:<ul><li>Atribuciones (instalaciones, reatribuciones y reengagements): de 15 a 30 minutos.</li><li>Eventos in-app: de 30 a 60 minutos.</li></ul> |
| Reporte en tiempo real | Pocos minutos después de solicitar un reporte | Los datos se actualizan en minutos a partir del momento en que ocurre el evento. |
| Diaria | **Zona UTC**: 8 horas después de la medianoche UTC del día del evento<br /><br />**Hemisferio oriental**: 9-20 horas después de la medianoche UTC del día del evento<br /><br />**Hemisferio occidental**: 21-32 horas después de la medianoche UTC del día del evento | <ul><li>Los datos se procesan diariamente.</li><li>La disponibilidad de estos datos difiere según la zona horaria específica de la aplicación.</li><li>Los tipos de datos que no admiten zonas horarias específicas de la aplicación usan la hora UTC.</li><li>Los tiempos de disponibilidad de los datos pueden variar de un día a otro o según se indique en artículos específicos.</li></ul> |
| Final del día | Diariamente al final del día, zona horaria específica de la aplicación | Al final del día calendario. Es decir, a las 00:01 del día siguiente. Ejemplo: los datos registrados el lunes están disponibles a partir del martes a las 00:01, independientemente de la zona horaria específica de la aplicación. |
| Intradía (durante el día) | Cada 4 horas en promedio | <ul><li>Los datos se recopilan seis veces al día, en promedio cada cuatro horas.</li><li>Los datos de clics e impresiones de SRN para clientes sin ROI360 se recopilan 3 veces al día.</li><li>Los datos de ETL de costos se envían 4 veces al día, de media cada 6 horas.</li></ul> |
| Ingresos por publicidad | Depende del tipo de integración y del reporte | <Anchor target="_blank" href="/marketers/es/docs/roi360-guide-ad-revenue-attribution#data-freshness">Consulta el artículo sobre los ingresos por publicidad para obtener más información</Anchor>. |
| PBA diaria | Los datos están disponibles 11-12 horas después del final del día UTC. | <ul><li>El dashboard y los reportes de PBA se actualizan [a diario](/docs/about-data-freshness-and-timezone-support#date-and-timezone-principles) usando la zona horaria UTC.</li><li>El procesamiento diario incluye los eventos recibidos durante el día anterior.</li><li>Durante los primeros siete días posteriores a la conversión, la PBA puede identificar eventos adicionales relacionados con una conversión. Esto puede cambiar los KPI y la atribución de fuentes de medios de forma retroactiva.</li><li>Después de siete días, las rutas se congelan y no se producen más cambios.</li><li>Los reportes de raw data incluyen el campo *final\_data.* Cuando los datos verdaderos son definitivos.</li><li><Anchor target="_blank" href="/marketers/es/docs/using-pba-dashboards#traits-and-limitations">Ejemplo detallado</Anchor></li></ul> |
| SKÁN | <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide#timing-from-app-install-until-dashboard-and-reports-update">Consulta sobre el tiempo</Anchor> desde la hora de llegada del postback hasta la disponibilidad de los datos en los paneles de control y reportes. | Los postbacks recibidos en un día determinado se procesan al final del día UTC. Los datos están disponibles antes de las 11:00 UTC del día siguiente. Lo que significa que los postbacks de iOS recibidos el lunes están disponibles en los reportes y paneles de control el martes por la mañana. Del mismo modo, los postbacks a los partners se envían el martes por la mañana.<br /><br />La fecha de instalación en los reportes y paneles de control se deriva de la hora de llegada del postback como se detalla en el <Anchor target="_blank" href="/marketers/es/docs/skan-conversion-studio#activity-window">artículo de SKAN Conversion Studio</Anchor>. |
| Data Locker diario | Los datos están disponibles entre 8 y 10 horas después del final del día UTC | <ul><li>Los datos se procesan diariamente.</li><li>Los datos están contenidos en la carpeta h=23 en la fecha del evento. Por ejemplo, los datos de los lunes están disponibles en la carpeta h=23 los martes a las 08:00–10:00 UTC.</li><li>Los datos de SKAN pueden llegar un poco más tarde (ver información de SKAN arriba).</li></ul> |

</Accordion>

<Accordion title="Tasas de actualización de datos y soporte de zona horaria">

<table><thead><tr><th>Datos relacionados</th><th>Cómo se presenta</th><th>Tasa de actualización de los datos<br/>(Consulta la sección anterior para conocer la clave de las tasas)</th><th>Visualizaciones de datos usando la zona horaria específica de la aplicación</th></tr></thead><tbody><tr><td>Instalaciones</td><td>KPI</td><td><p>Continua</p><p>Live Alerts</p><ul><li>Las alertas de Protect360 se actualizan a la hora UTC diaria.<ul><li>Se actualiza diariamente a las 16:00 UTC</li></ul></li></ul></td><td><span>✓</span></td></tr><tr><td>Sesiones, clics, impresiones, usuarios fieles</td><td>KPI</td><td><ul><li>Enlaces de atribución: Continua</li><li>SRN: Intradía</li></ul></td><td><span>✓</span></td></tr><tr><td>Eventos in-app de ingresos</td><td>KPI</td><td>Continua</td><td><span>✓</span></td></tr><tr><td>Ingresos por publicidad</td><td>KPI</td><td>Ingresos por publicidad</td><td><span>✓</span></td></tr><tr><td>Gasto publicitario (costo)</td><td>KPI</td><td><ul><li>Enlace de atribución: Continua (máximo hasta 2 horas después del clic)</li><li>API: Intradía</li><li>Procesamiento de gastos publicitarios Hasta 4 horas después de la ingestión</li></ul></td><td><span>✓</span></td></tr><tr><td>Desinstalar</td><td>KPI</td><td>Diaria. AppsFlyer hace ping a las tiendas de aplicaciones cada 24 horas. La hora del evento de la desinstalación representa el momento en que AppsFlyer lanzó la notificación push que no se ve y descubrió que la aplicación se desinstaló. Esta no es la hora real de la desinstalación.</td><td><span>.</span></td></tr><tr><td>Eventos in-app en la interfaz</td><td>Lista desplegable</td><td><p>Los nombres de eventos in-app que se muestran en las listas desplegables se actualizan diariamente.</p><p>Esto no afecta la tasa de actualización de los datos en sí.</p><p><strong>Ejemplos:</strong> Listas desplegables de eventos in-app en Push API, dashboards y audiencias.</p></td><td><span>✓</span></td></tr><tr><td>Panel de vista general</td><td>Página</td><td>Continua</td><td><span>✓</span></td></tr><tr><td>Panel de control de Protect360</td><td>Página</td><td>Diaria</td><td> <span>✓ </span>(1)</td></tr><tr><td>Panel de control de SKAN</td><td>Página</td><td>Diaria</td><td><span>.</span></td></tr><tr><td>Página de actividad</td><td>Página</td><td><ul><li>KPIs Continua</li><li>Promedios: A medianoche de la zona horaria específica de la aplicación</li></ul></td><td><p><span>✓</span></p><p>Excepción: Los datos MAU son UTC</p></td></tr><tr><td>Página de eventos</td><td>Página</td><td>Continua</td><td><span>✓</span></td></tr><tr><td> </td><td> </td><td>(Esta fila se ha dejado en blanco intencionalmente)</td><td> </td></tr><tr><td>Retención</td><td>Página</td><td><p>Los KPI de retención están disponibles con granularidad diaria y semanal. La actualización de los datos para cada uno es diferente.</p><ul><li>KPI regulares:</li><li>KPI semanales de retención: La semana comienza el lunes y termina el domingo. La retención se calcula el lunes a las 12:00 UTC. La falta de soporte para la zona horaria específica de la aplicación para el KPI semanal resulta en una diferencia insignificante.</li></ul></td><td><p>Diario: <span>✓</span></p><p>Semanal: <span><strong>x</strong></span></p></td></tr><tr><td>Cohorte</td><td>Página</td><td>Continua</td><td> <span>✓ </span>(2)</td></tr><tr><td>Panel de control personalizado</td><td>Página</td><td>Continuo</td><td> <span>✓ </span>(3)</td></tr><tr><td>Audiencias</td><td>Página</td><td><ul><li>Las actualizaciones se envían a los partners cada 24 horas.</li><li>La base de usuarios se actualiza diariamente y almacena hasta 90 días de datos del dispositivo</li></ul></td><td><span>✓</span></td></tr><tr><td>Página de información del SDK</td><td>Página</td><td>Diaria</td><td><span>.</span></td></tr><tr><td>Exportar datos</td><td>Página</td><td><p>Continua</p><p>Excepciones a tener en cuenta:</p><ul><li>Raw data de ingresos por publicidad: Diaria</li><li>Protect360:<ul><li>Reportes agregados:</li><li>Raw data bloqueado: Continua</li><li>Final del día</li></ul></li><li>Eventos in-app orgánicos: Actualización con un desfase de varias horas.</li></ul></td><td><span>✓</span></td></tr><tr><td>API Pull</td><td>API</td><td>La actualización de los datos de API Pull es la misma que la de Datos exportados.</td><td><p><span>✓</span></p><p><span>Predeterminado: UTC</span></p></td></tr><tr><td>Pivot</td><td>Página</td><td>Diaria</td><td><p><span>✓</span></p><p>KPI semanales de retención: <strong><span>x</span></strong></p></td></tr><tr><td>API maestra</td><td>API</td><td>Diaria</td><td> <span>✓ </span>(3)</td></tr><tr><td>Casillero de datos</td><td>API</td><td>Como se especifica en el artículo de Data Locker.</td><td><p><span>.</span></p><p><span><strong>UTC</strong></span></p></td></tr><tr><td>Devoluciones de mensajes</td><td>API</td><td>Continua</td><td>N/D</td></tr><tr><td>API Push</td><td>API</td><td>Continuo (4)</td><td><p><span>✓</span></p><p><span><strong>Ambos</strong></span></p></td></tr><tr><td>Eventos in-app de servidor a servidor</td><td>API</td><td>Continua</td><td>N/D</td></tr><tr><td colspan="4"><p>Notas:</p><p>(1) Todas las aplicaciones para las que el usuario tenga permiso deben usar la misma zona horaria específica de la aplicación. De lo contrario, la zona horaria vuelve a ser UTC.</p><p>(2) Consulta en <a href="./cohort-and-retention-dashboard#traits-and-limitations" target="_blank">Rasgos y limitaciones de la cohorte</a> cuándo la zona horaria volverá a ser UTC.</p><p>(3) Todas las aplicaciones seleccionadas deben utilizar la misma zona horaria específica de la aplicación. De lo contrario, la zona horaria vuelve a ser UTC.</p><p>(4) Los datos del reporte SKAN estarán disponibles todos los días entre las 08:00 y las 10:00 UTC.</p></td></tr></tbody></table>

<div id="exception-my-dashboards-cohort-and-activity-metrics" />

> 📘 **Excepción: métricas de cohorte y actividad de My Dashboards**
>
> Estas métricas tienen su propia frecuencia de actualización de datos:
>
> * **Métricas de cohorte (apps web, CTV, PC y de consola):** Los datos del mismo día están disponibles al día siguiente, una vez finaliza el procesamiento diario.
> * **Métricas de actividad (atribución clásica):** La actualización de datos depende del tipo de app:
>   * **Aplicaciones web:** hasta 3,5 horas
>   * **Apps de CTV, PC y de consola:** hasta 50 minutos
>   * **Aplicaciones móviles:** hasta 70 minutos
> * **Atribución multiplataforma:** La actualización solo se aplica a la atribución clásica. La actualización de datos multiplataforma en My Dashboards sigue siendo diaria.
>
> Consulta <Anchor target="_blank" href="/marketers/es/docs/my-dashboards#traits-and-limitations">las características y limitaciones de My Dashboards</Anchor> para obtener más información.

</Accordion>

<div data-zendesk-anchors="data-freshness-and-support-for-appspecific-time-zones=actualizaci%C3%B3n-de-los-datos-y-soporte-para-zonas-horarias-espec%C3%ADficas-de-la-aplicaci%C3%B3n 01EDBBPAH96ADJ56FRNB34K3VB=actualizaci%C3%B3n-de-los-datos-y-soporte-para-zonas-horarias-espec%C3%ADficas-de-la-aplicaci%C3%B3n data-freshness=actualizaci%C3%B3n-de-los-datos 01EDBBPAH9M5KQRXJ1TNN3RJAX=actualizaci%C3%B3n-de-los-datos time-zones=zonas-horarias 01EDBBPAH92JJVVGXN61N4SV89=zonas-horarias appspecific-time-zone=zona-horaria-espec%C3%ADfica-de-la-aplicaci%C3%B3n 01EDBBPAH9WHDY875Y913PV00Z=zona-horaria-espec%C3%ADfica-de-la-aplicaci%C3%B3n timezone-guidelines=lineamientos-de-zona-horaria 01EDBBPAH9TRH8HBB0JAX2369H=lineamientos-de-zona-horaria daily-processing=procesamiento-diario 01EDBBPAH98F0641D934W9NJD8=procesamiento-diario h_01M2MJESA4EG1BEVM5T6N9FH0D=excepci%C3%B3n-m%C3%A9tricas-de-cohorte-y-actividad-de-my-dashboards" />
