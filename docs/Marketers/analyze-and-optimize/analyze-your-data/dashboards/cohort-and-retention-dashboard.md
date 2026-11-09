---
title: Panel de control de cohorte y retención
metadata:
  keywords:
    - Cohort
    - Cohort Report
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
  created_at: '2015-12-24T10:20:01Z'
  edited_at: '2026-08-12T11:50:31Z'
  id: 207040496
  locale: es
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/es/articles/207040496
---
> **De un vistazo**: El panel de control de la cohorte agrupa a los usuarios de la aplicación por fecha de adquisición. Permite realizar un análisis de rendimiento a través de los ciclos de vida de los usuarios. Usa el panel de control para obtener insights sobre cómo las diferencias en las campañas alteran las métricas de la campaña.

<Image align="center" alt="cohort main (2).png" src="https://files.readme.io/5a9307f4220a5bc41b5cebefe345a9b93165ac3874dd4faaed184d0309e92615-small-32127933337873.png" />

<div id="cohort-and-retention-dashboard" />

## Panel de control de cohorte y retención

Lectura relacionada: <Anchor target="_blank" href="/marketers/es/docs/aggregated-and-analytics-reporting-overview#cohort-flavors">Diferencias entre los tipos de cohorte</Anchor>

Para utilizar la cohorte, selecciona usuarios de una o más aplicaciones y segméntalos por tiempo de conversión. Se encuentran disponibles métricas de la cohorte como ingresos, ROI y tasas de conversión de eventos. La cohorte se puede desglosar más, con fines comparativos, en dimensiones como campaña o fuente de medios. De este modo, se pueden descubrir patrones o cambios en el rendimiento sobre los ciclos de vida de los usuarios o de las campañas. Consulta <Anchor target="_blank" href="https://www.appsflyer.com/blog/cohort-report-mobile-marketing-kpis/?utm_campaign=Blog%20Subscription%2003-2019&utm_source=hs_email&utm_medium=email&utm_content=76370689&_hsenc=p2ANqtz-8SX49xuEw2WX_Vrlh11_zxlDFvlfMpBzSQm1I-nFhc0WbZDf0ACC-VEi4qmKhesHCsUNdhU50Oinl-urwnGAOZMwwHSTp6UgdChCi7ARayJFUFTus&_hsmi=76370689">Casos de uso de la cohorte</Anchor>.

<div id="tip" />

> 👍 **Consejo**
>
> ¿Quieres saber más sobre los reportes de cohortes? ¿Quieres saber más sobre los reportes de cohortes? Consulta este breve <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7804/play/18625/your-users-journey-with-retention-and-cohort-reports">curso informativo en el portal de aprendizaje de AppsFlyer</Anchor>.

<div id="using-cohort" />

## Uso de la Cohorte

<div id="setting-up-an-analysis" />

<Accordion title="Configurar un análisis">

1. Ve a **Panel de control**> **Cohorte**.  
   Se abre el panel de control de la cohorte. Se muestra el intervalo de fechas de granularidad y conversión.  
   <Image align="center" alt="mceclip0__1_.png" src="https://files.readme.io/4113fd619422979d6a26004a55c009ebc48eef59d10ddc7c3e5becd2a758e6d4-32127949494417.png" />
2. Selecciona la [granularidad del período de cohorte](/docs/cohort-and-retention-dashboard#cohort-periods):
   * Horas
   * Días
   * Semanas
   * meses
3. Establece el período de atribución (adquisición de usuarios o engagement de retargeting). Los datos relativos a las fechas más recientes pueden dar lugar a [datos parciales](/docs/cohort-and-retention-dashboard#partial-data) indicados con guiones en los gráficos y las tablas.
4. Haz clic en **Editar la Cohorte**.  
   Se abre la ventana de configuración de la Cohorte.  
   <Image align="center" alt="CohortSetup.jpg" src="https://files.readme.io/f09cc190770d16a2ddf60e1f210f458114ac43d4c19fc5507fb50b0d1d2f5c77-32127949495825.jpg" width="365px" />
5. Completa lo siguiente:
   * [**Tipo de vista de cohorte**](/docs/cohort-and-retention-dashboard#view-types):
     * **Adquisición de usuarios.**
     * **Reorientación**
     * **Unificado:** incluye los eventos in-app tanto de atribución de usuarios como de atribuciones de retargeting. **Nota**: Los eventos de retargeting tienen prioridad sobre los eventos de adquisición de usuarios, lo que significa que el reporte contiene eventos donde <Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-overview">is\_primary\_attribution=true</Anchor>.
   * [**Tipo de tendencia**](/docs/cohort-and-retention-dashboard#trend-types):
     * La función de exportación del CSV se limita a los reportes del **Rendimiento de la vida útil del usuario**.
     * **KPI por tiempo de atribución**.
   * **Usuarios de**: selecciona 1 o más apps. **Usuarios de las aplicaciones**: selecciona una, varias o **todas** (significa las 100 aplicaciones principales de tu cuenta). **Nota**: Las agencias solo pueden seleccionar una aplicación.
   * **Agrupado por**: Selecciona una o más [dimensiones](/docs/cohort-and-retention-dashboard#list-of-dimensions-for-grouping-and-filtering) [Predeterminada: Fuente de medios].
   * **Tamaño mínimo de la cohorte**: establece el tamaño mínimo de la cohorte. Esto evita que tu reporte se llene de cohortes insignificantes (pequeñas). [Predeterminado=1]
   * Campos opcionales:
     * **Filtrado por**: selecciona una o más [dimensiones](/docs/cohort-and-retention-dashboard#list-of-dimensions-for-grouping-and-filtering) para filtrar. No hay filtros predeterminados.
6. **En el día** o **Acumulado**:
7. Selecciona la métrica (KPI) sobre la que quieres realizar el análisis de cohorte. Para los eventos in-app, selecciona el evento in-app y la métrica.
8. Selecciona los períodos de cohorte para los que quieres ver datos. Es decir, qué horas, días, semanas o meses posteriores a la conversión. El número de períodos de cohorte que puedes seleccionar depende del tipo de tendencia que hayas seleccionado.
9. Selecciona si quieres incluir **datos parciales** o mostrar solo **datos completos** (datos de períodos de cohorte que ya han finalizado).
10. Utiliza el control de **cohorte en tiempo real** para seleccionar el modo de visualización de datos:
    * Acumulado significa el total acumulado o actualizado de la métrica. Esto significa que la cohorte 3 muestra los totales de los períodos de cohorte 0-3.
    * **En el día**: el valor solo en el día de la cohorte especificada. Por ejemplo, en el caso del día 7, esto significa el valor del día 7 posterior a la conversión.
11. **Tabla** o **Gráfico:**
12. Selecciona si quieres ver los datos como tabla o gráfico. Si seleccionas tabla, puedes elegir cuántas filas de datos quieres ver: 25, 50, 100 o 200.
13. [Opcional] [Gestión de reportes de cohortes guardados](/docs/cohort-and-retention-dashboard#using-my-reports-save-and-select-reports).

</Accordion>

<div id="using-my-reports-save-and-select-reports" />

<Accordion title="Uso de Mis reportes: guardar y seleccionar reportes">

* Mis reportes te permiten guardar la configuración actual del panel de control para el uso futuro.
* Selecciona un reporte guardado para mostrar los datos de cohortes más actuales disponibles.
* Puedes guardar uno o más reportes.
* Solo tú puedes acceder a tu sección de Mis reportes.

| Característica | Característica |
| --- | --- |
| Mis reportes | ![MyReports.png](https://files.readme.io/8f49c0e6dee55427bf3a64149ac48f67547967b8cd24aa8de3e34b760708f992-32127933340305.png)<br /><br />Selecciona un reporte para mostrar los datos más actuales disponibles. |
| Guardar cambios | Guarda el reporte. Nota: Se sobrescribe el reporte actualmente seleccionado. |
| Opciones de acción (![Elipse.png](https://files.readme.io/14b74dc6e733867bd16b6a3594f5f0856d7437462b2e0cf7c12adf11cfa295b3-32127949499409.png)) | <ul><li>**Guardar como nuevo**<ul><li>Guarda el reporte usando un nombre de reporte diferente.</li><li>[Opción] Hace que este reporte sea el reporte predeterminado.</li></ul></li><li>**Renombrar**: Cambia el nombre del reporte.</li><li>**Establecer como predeterminado**: Hace que este reporte sea el reporte predeterminado. Cuando se abre la Cohorte este es el reporte que se muestra inicialmente</li><li>**Eliminar**: Elimina el reporte.</li></ul> |

</Accordion>

<div id="export-the-cohort-to-a-csv-file" />

<Accordion title="Exportar la cohorte a un archivo CSV">

* Los reportes de cohortes se pueden exportar a archivos CSV.
* Los nombres de las columnas que tienen sufijos [parciales son equivalentes a los guiones que aparecen en los gráficos y las tablas de la interfaz de usuario.](/docs/cohort-and-retention-dashboard#partial-data)

**Para exportar los reportes de cohortes a archivos CSV, se debe realizar lo siguiente:**

* En la parte superior derecha de la ventana de reportes de cohortes, haz clic en <Image alt="Download.png" src="https://files.readme.io/50af9c6cde00dada58a1bb89a9eb3e566f316c0e7336af68f4ce403584047a5b-32127933341969.png" width="21px" /> (exportar).  
  Se ha descargado el archivo CSV del reporte de cohortes.

</Accordion>

<div id="cohort-concepts" />

## Principios de la cohorte

<div id="cohort-periods" />

<Accordion title="Cohorte in-app">

El periodo de conversión se denomina 0 (Hora 0, Día 0, Semana 0 o Mes 0). El siguiente periodo posterior a la conversión se denomina 1 (Hora 1, Día 1, Semana 1 o Mes 1), y así sucesivamente.

El número de períodos disponibles depende de la granularidad del período seleccionada:

* Para la granularidad horaria, el número máximo de horas es 72.
* Para la granularidad diaria, el número máximo de días es 180.
* Para la granularidad semanal, el número máximo de semanas es 156.
* Para la granularidad mensual, el número máximo de meses es 36.

En AppsFlyer un periodo de cohorte no toma en cuenta la marca de tiempo de instalación específica. Más bien, las horas de cohorte se redondean a la hora más cercana, y los días, semanas y meses de cohorte se basan en el día, semana o mes calendario. Esto puede causar discrepancias al comparar los datos de cohortes de AppsFlyer con los datos de cohorte de otras redes, donde todos los períodos de cohorte están determinados por la marca de tiempo de instalación específica (es decir, una hora es 60 minutos después de la instalación, un día es el período post-instalación de 24 horas después de la marca de tiempo de instalación, etc.).

</Accordion>

<div id="view-types" />

<Accordion title="Tipo de cohorte">

Depende del tipo de la cohorte:

* **Unificado**:
  * El rendimiento combinado de las campañas de adquisición de usuarios y de retargeting (incluidos los costos e ingresos).
  * Si un evento se atribuye a ambos tipos de conversiones, solo se incluye el evento de retargeting. Esto significa que el reporte se genera utilizando la última fuente de medios que se tocó. Si estás familiarizado con el raw data, significa eventos en los que <Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-overview">is\_primary\_attribution=true</Anchor>.
* **Adquisición de usuarios:** datos de rendimiento de las instalaciones (reinstalaciones excluidas a menos que estén <Anchor target="_blank" href="/marketers/es/docs/measure-reinstalls#attributed-to-the-first-install">especialmente habilitadas</Anchor>)
* **Retargeting:** datos de rendimiento de las reatribuciones o re-engagements

<Image align="center" alt="beta_feature.png" src="https://files.readme.io/738bf91c1a12671b32b088993c43d4103498907a8bbe15821ddc53a0b071b876-32127949500305.png" />

</Accordion>

<div id="trend-types" />

<Accordion title="Tipo de tendencia">

Tipo de tendencia:

* **Tipo de tendencia: rendimiento de la vida útil del usuario**
* **KPI por momento de atribución**

<div id="user-lifetime-performance" />

#### **Usuarios (4)**

* Cada columna de la tabla o punto del gráfico representa otro período de cohorte (hora/día/semana/mes). El período de conversión se denomina período de cohorte 0. El primer período posterior a la conversión es el período de cohorte 1, y así sucesivamente. Esto permite comparar el rendimiento del usuario posterior a la conversión, empezando por el día de la conversión, denominado día 0 de la cohorte.
* Puedes seleccionar para qué períodos de cohorte quieres obtener datos, hasta el máximo de cada opción de granularidad (hora/día/semana/mes).

<div id="kpi-by-attribution-time" />

#### **KPI por momento de atribución**

* **KPI por momento de atribución:** los usuarios se agrupan por **tiempo** de conversión. Esto te permite evaluar el rendimiento de la campaña a lo largo del tiempo y ver los KPI de la campaña en relación con el momento de la conversión.
* El número máximo de períodos de cohorte que puedes seleccionar para obtener datos es 5.
* Si seleccionas ver los datos como gráfico en lugar de como tabla, el gráfico muestra solo 1 período de cohorte (el período más bajo seleccionado).

<div id="example-user-lifetime-performance-trend-vs-kpi-by-attribution-time-trend" />

#### No está disponible para la tendencia de KPI por momento de atribución.

En este ejemplo, se utiliza el mismo raw data para generar los dos tipos de tendencias de la cohorte. La tabla de raw data contiene eventos de atribución relacionados con los diferentes usuarios A, B, C y D. Los usuarios se involucran con un anuncio, instalan la aplicación y después de la conversión realizan una o más compras. El día 0 de la cohorte es el día de la instalación.

[<Image align="center" alt="CohortExample_en-us.jpg" src="https://files.readme.io/013f6ebe78e8a94e7dcc36e62f73ad151ecd9a88c5b32e5e41ffa52f1567f744-38187655867025.png" width="2284px" />](https://support.appsflyer.com/hc/article_attachments/49753028968209)

</Accordion>

<div id="partial-data" />

<Accordion title="¿Qué son los datos parciales?">

Para un día determinado en el rango de datos de conversión, si la cantidad de días transcurridos desde la fecha de conversión es inferior al día de la cohorte, el día de la cohorte contiene datos parciales. Eso significa que los datos parciales se producen cualquier día en que el día de la cohorte > fecha actual - fecha de conversión.

Utiliza el control de datos parciales/completos para seleccionar el modo de visualización de datos:

* [Predeterminado] **Tiempo real:**
  * Datos de atribución actualizados continuamente en tiempo real, incluidos los ingresos.
  * Los datos de costos se actualizan 6 veces al día, una vez cada cuatro horas en promedio.
  * Se incluyen datos parciales (indicados por guiones en reportes y gráficos)
* **Diaria:** Los datos se actualizan diariamente y están disponibles unos minutos después de la medianoche. No se muestran datos de días parciales.

</Accordion>

<div id="list-of-dimensions-for-grouping-and-filtering" />

<Accordion title="Lista de dimensiones para agrupar y filtrar">

| Dimensión | Comentarios | Agrupar por | Filtrar por |
| --- | --- | --- | --- |
| <span id="ad"></span>Anuncio |  | ✓ | ✓ |
| <span id="ad-id"></span>ID de anuncio |  | ✓ | ✓ |
| <span id="adset"></span>Conjunto de anuncios |  | ✓ | ✓ |
| <span id="adset-id"></span>ID de conjunto de anuncios |  | ✓ | ✓ |
| <span id="agency"></span>Agencia |  | ✓ | ✓ |
| <span id="apps"></span>Apps | Relevante cuando el reporte contiene múltiples aplicaciones | ✓ | . |
| <span id="attributed-touchtype"></span>Tipo de toque atribuido | Valores: clic, impresión o NA (orgánico) | ✓ | ✓ |
| <span id="campaign"></span>Campaña |  | ✓ | ✓ |
| <span id="campaign-id"></span>ID de campaña |  | ✓ | ✓ |
| <span id="channel"></span>Canal |  | ✓ | ✓ |
| <span id="conversion-type"></span>Tipo de conversión | Tipo de la cohorte:<ul><li>**Adquisición de usuarios**: instalación</li><li>**Retargeting**: re-engagement, reatribución</li></ul> | ✓ | ✓ |
| <span id="country-geo"></span>Geografía | En función de la dirección IP del usuario | ✓ | ✓ |
| <span id="time-in-the-case-of-daily-granularity-is-the-date-hourly-granularity-is-the-hour-of-the-day-weekly-granularity-is-the-week-of-the-year-monthly-granularity-is-the-month-of-the-year"></span>Momento. En el caso de:<ul><li>La granularidad diaria es la fecha</li><li>La granularidad horaria es la hora del día</li><li>La granularidad semanal es la semana del año</li><li>La granularidad mensual es el mes del año</li></ul> | Depende del tipo de la cohorte:<ul><li>**Adquisición de usuarios y unificado**: la hora en que la aplicación se inició por primera vez.</li><li>**Retargeting**: la hora en que la aplicación se inició por primera vez después del re-engagement.</li></ul> | ✓ | **X** |
| <span id="install-app-store"></span>Tienda de aplicaciones de la instalación | Relevante para las aplicaciones que implementan la <Anchor target="_blank" href="/marketers/es/docs/set-up-multi-store-android-attribution">atribución de múltiples tiendas</Anchor> de Android. Ponte en contacto con tu CSM para habilitar esta dimensión. | ✓ | ✓ |
| <span id="keywords"></span>Palabras clave | Busca palabras clave proporcionadas por los partners integrados | ✓ | ✓ |
| <span id="media-source"></span>Fuente de medios |  | ✓ | ✓ |
| <span id="revenue-type"></span>Tipo de ingresos | Compra en la aplicación o ingresos por anuncios | **X** | ✓ |
| <span id="site-id"></span>ID de sitio |  | ✓ | ✓ |
| <span id="sub-param-1"></span>Subparámetro 1 |  | ✓ | ✓ |

</Accordion>

<div id="metrics-available" />

<Accordion title="Métricas disponibles">

| Métrica | Descripción |
| --- | --- |
| Instalaciones asistidas | Número de instalaciones durante el rango de tiempo seleccionado |
| Conversiones de retargeting | Número de conversiones de retargeting (reatribuciones y re-engagements) durante el rango de tiempo seleccionado |
| Recuento | Número de instalaciones, re-engagements y reatribuciones durante el rango de tiempo seleccionado |
| Costo (3) | <ul><li>Costo de la campaña reportado a AppsFlyer a través de clic y/o la API</li><li>Siempre<ul><li>Observaciones</li><li>Selecciona de 1 a 72 horas de las 72 horas anteriores</li></ul></li></ul> |
| eCPI | Costo efectivo promedio por instalación (atribución): Costo / atribuciones |
| Ingresos | Ingresos informados a AppsFlyer (acumulados o del día, según tu configuración) |
| Cantidad | Número de veces que se produjo el evento de ingresos (acumulado o del día, según tu configuración) |
| OPCIONAL | Ingresos promedio por usuario: Ingresos / usuarios únicos |
| Recuento de ingresos promedio | Recuento promedio de eventos de ingresos reportados a AppsFlyer (acumulado o del día, según tu configuración) |
| Cantidad | Número acumulado de veces que se inicia la aplicación, se coloca en primer plano en el dispositivo u otra medida establecida por el desarrollador |
| Sesiones promedio (acumuladas) | Media de veces que un usuario inicia la aplicación, se lleva al primer plano del dispositivo u otra medida establecida por el desarrollador (acumulativo) |
| Sesiones (2) | Número de veces del día que se inicia la aplicación, se coloca en primer plano en el dispositivo u otra medida establecida por el desarrollador |
| Sesiones promedio (del día) | Media de veces que un usuario inicia la aplicación, se lleva al primer plano del dispositivo u otra medida establecida por el desarrollador (en el día) |
| Retención | Tasa de retención: Número de usuarios únicos del día que abrieron la aplicación / conversiones * 100 |
| ROI (Retorno de la Inversión) | <ul><li>Retorno de la inversión: (Ingresos - costo) / costo * 100</li><li>Las métricas relacionadas con los costos no están disponibles<ul><li>Selecciona un tipo de tendencia:</li><li>Selecciona la granularidad.</li></ul></li></ul> |
| ROAS (Retorno de la Inversión Publicitaria) | <ul><li>Retorno del gasto en publicidad: Ingresos / Costo * 100</li><li>Siempre<ul><li>Tipo de granularidad</li><li>Para la granularidad diaria, el número máximo de días es 180.</li></ul></li></ul> |
| Recuento de desinstalaciones | <ul><li>Número de usuarios de la aplicación que la instalan y luego la desinstalan (relevante solo para la adquisición de usuarios).</li><li>Siempre/Opcional<ul><li>El tipo de vista está unificado.</li><li>Período permitido</li></ul></li></ul> |
| Recuento promedio de desinstalaciones | <ul><li>Número promedio de usuarios de la aplicación que la instalan y luego la desinstalan (relevante solo para la adquisición de usuarios)</li><li>Siempre<ul><li>Diferencias entre los tipos de cohorte</li><li>Opciones de granularidad</li></ul></li></ul> |
| Recuento de IAE | Número de veces que se realizó el evento in-app (acumulado o del día, según tu configuración) |
| eCPI promedio | Número promedio de veces que se realizó el evento in-app (acumulado o del día, según tu configuración) |
| Ingresos de IAE | Ingresos generados por el evento in-app (acumulados o del día, según tu configuración) |
| Regular, monetización de anuncios | Ingresos medios generados por el evento in-app (acumulados o del día, según tu configuración) |
| Usuarios únicos | Número de usuarios únicos que realizan el evento in-app (acumulados o del día, según tu configuración) |
| Conversiones de IAE (acumuladas) | Por ejemplo, la cantidad de usuarios [únicos] en una cohorte es de 100. De estos, 20 realizan un evento in-app específico por primera vez. La tasa de conversión in-app es 20/100=20%. |
| Conversiones de IAE (del día) | Tasa de conversión del evento in-app: Número de usuarios únicos que realizan el IAE en el día / conversiones * 100 |
| Costo Efectivo por Adquisición (eCPA) | Costo efectivo por acción (evento): Costo / Número acumulado de usuarios únicos que realizan el evento in-app |

</Accordion>

<div id="additional-information" />

## Información adicional

<div id="cohort-for-agencies" />

<Accordion title="Cohorte para agencias">

* El anunciante debe conceder a la agencia permiso para usar la Cohorte.
  * Para conceder el permiso a una agencia, el anunciante debe realizar lo siguiente:
    1. Ir a **Configuración** **Integraciones activas.**
    2. Seleccionar la agencia.
    3. Ve a la pestaña de permisos, habilita **Permitir el acceso a tus reportes de retención y de cohortes.**
* Las agencias solo pueden acceder a los datos del tráfico que genera la agencia. No pueden ver datos relacionados con el tráfico orgánico o el tráfico no orgánico generado en otro lugar.

</Accordion>

<div id="use-cases" />

<Accordion title="CASOS DE USO">

<div id="revenue-sum-by-geo" />

#### Suma de ingresos por país

**Gráfico: ingresos acumulados por usuario**

<Image align="center" alt="Captura de pantalla 2023-10-31 a 16.56.31.png" src="https://files.readme.io/cde4e25a051e159cd4e1a1f192eda79df1d3df6f5891fcda2c24a01e0baa462b-small-32127949501201.png" />

**Tabla: ingresos por día**

<Image align="center" alt="Full_cohort2_us-en.png" src="https://files.readme.io/be3949a33cdf489eb7735acbf06c7abbecfd46f84a20d463e50ddfe815cc3368-small-32127949501969.png" />

<div id="in-app-event-conversion" />

#### Conversión de eventos in-app

Un anunciante define af\_purchase de un evento in-app. El gráfico de cohortes muestra el porcentaje de usuarios de la aplicación en la cohorte que realizó una compra desde un entorno móvil. Podemos ver en el día 10, por ejemplo, que cerca del 30% (11,11%+9.71%+7,47%) de los usuarios de la cohorte realizó una compra desde un entorno móvil.

<Image align="center" alt="CohortTable.png" src="https://files.readme.io/d2709ec30a9f6cc3fe55503af557153b6a2677948d0ca0b9a477af9e47746c33-small-32127933347089.png" />

</Accordion>

<div id="faq" />

<Accordion title="Preguntas frecuentes">

| Pregunta | Respuesta |
| --- | --- |
| ¿Puedo ver <Anchor target="_blank" href="/marketers/es/docs/apple-ads-integration-setup#analyze-keyword-cost">las palabras clave Costo y ROI</Anchor> de Apple Search Ads? | Sí.  <br />Apple Search Ads nos proporciona el costo de cada palabra clave por día, desglosado por campaña/conjunto de anuncios/anuncio. **Nota:** El desglose por geolocalización/país no está disponible. |
| ¿Por qué el mismo nombre de campaña aparece más de una vez para una determinada fuente de medios? | <ul><li>Si usas el mismo nombre de campaña con campañas que tienen diferentes ID de campaña, entonces el nombre se muestra más de una vez.</li><li>Debes asignar ID de campaña únicos.</li><li>Cuando se cambian los nombres de campañas, los datos se alinean con el nombre utilizado.</li></ul> |
| ¿Puedo ver a los usuarios orgánicos? | Los usuarios orgánicos, de forma predeterminada, se incluyen en los reportes de cohortes.<br /><br />**Para limitar el reporte de cohortes a los usuarios orgánicos solamente:**<ol><li>En el **panel de control de la cohorte**, haz clic en el botón **Editar cohorte**.</li><li>En la ventana de configuración de la cohorte se configura **Filtrar por** > **Fuente de medios** como **Orgánica**: [![cohort_setup_filtered_by_media_source_is_organic.png](https://files.readme.io/ba95397eac2b66a365a2aabb2f56587e78624be5ecd06dd6c0463e19dfe9e26a-32127949503889.png)](https://files.readme.io/ba95397eac2b66a365a2aabb2f56587e78624be5ecd06dd6c0463e19dfe9e26a-32127949503889.png)</li><li>Haz clic en **Aplicar los cambios**</li></ol> |
| ¿Puedo ver los datos de instalaciones eliminadas? | Las instalaciones eliminadas, como las de SRN que se eliminaron debido a políticas de retención de datos o las instalaciones eliminadas por el RGPD, no se pueden ver en el panel de control de la cohorte.<br /><br />Para obtener más información, <Anchor target="_blank" href="/marketers/es/docs/user-level-data-retention#periodos-de-conservación-de-los-datos-de-partners">haz clic aquí.</Anchor> |
| ¿Puedo comparar los datos para la vista diaria con los datos en vistas semanales o mensuales? | No es fácil comparar datos de una granularidad diaria con una granularidad semanal o mensual, porque los LTV de cohorte no se alinean. <br /><br />Al ver cohortes en granularidad diaria, el **Día 0** muestra los datos del día de las instalaciones. El Día 1 es el día después de la instalación, el Día 2 es 2 días después de la instalación, etc. <br /><br />Al visualizar cohortes en granularidad semanal, se muestran los datos de todas las instalaciones realizadas en **toda la Semana 0**. La Semana 1 es la semana después de la instalación, la Semana 2 es 2 semanas después de la instalación, etc. <br /><br />Al visualizar cohortes en granularidad mensual, se muestran los datos de todas las instalaciones realizadas en **todo el Mes 0**. El Mes 1 es el mes posterior a la instalación, el Mes 2 es 2 meses después de la instalación, etc. <br /><br />Esto significa que las líneas de tiempo de LTV no se alinean. Por ejemplo, si miras los datos del 9 al 15 de enero: si usas granularidad diaria, el **Día 0** contiene datos del primer día de todas las **instalaciones realizadas del 9 al 15 de enero.** Y el **Día 6** contiene datos de los primeros 6 días posteriores a la instalación de todas las instalaciones realizadas del **9 al 15 de enero**. Mientras que en la granularidad semanal, la **Semana 0** contiene datos de **todo el periodo** para todas las instalaciones **realizadas del 9 al 15 de enero**. Entonces, para las instalaciones del **9 de enero**, los datos son como el **Día 6**. Pero para las instalaciones del **15 de enero**, son como el **Día 0**. |
| ¿Por qué hay una disminución de los ingresos acumulados entre periodos de cohorte? | Normalmente, los ingresos acumulados aumentan con cada periodo de cohorte; por ejemplo, D2 es superior a D1. Sin embargo, a veces disminuyen debido a ingresos negativos, por ejemplo, por eventos de devolución. Puedes comprobarlo revisando los datos del día (hora/día/semana/mes) para ver si hay ingresos negativos en un periodo de cohorte concreto. |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Rasgos y limitaciones">

| Caducado | Observaciones |
| --- | --- |
| Acceso de la red de publicidad a cohortes | No disponible |
| Acceso de agencias | Disponible:<ul><li>Limitado a una aplicación.</li><li>Las cuentas híbridas no pueden acceder a la Cohorte.</li><li>Requiere permiso de acceso para cada aplicación en particular.</li><li>No se pueden seleccionar múltiples aplicaciones.</li><li>El acceso a datos orgánicos no es posible.</li></ul> |
| Transparencia de Agencias | Disponible a partir del 10 de enero de 2021 |
| Zona horaria específica de la aplicación | <ul><li>Disponible</li><li>Excepción: en todos los casos siguientes, AppsFlyer ignora la zona horaria específica de la aplicación y utiliza la zona horaria por defecto que es UTC +0:<ul><li>El reporte de cohortes contiene datos de múltiples aplicaciones, y las aplicaciones tienen diferentes zonas horarias.</li><li>Todas las aplicaciones tienen la misma zona horaria, y la zona horaria de por lo menos una de las aplicaciones cambió durante el periodo del reporte de cohortes. Para determinar el periodo del reporte:<ul><li>Fecha de inicio: la primera fecha en el rango de fechas de conversión</li><li>Fecha de finalización: se calcula sumando el número de días de la duración que se muestra hasta la última fecha del intervalo de fechas de conversión. Ejemplo: Última fecha: 1 de enero de 2019. Duración del reporte: 30 días. Fecha de finalización: 31 de enero de 2019</li></ul></li><li>Los datos semanales y mensuales se mostrarán en la zona horaria UTC</li></ul></li></ul> |
| Costo | <ul><li>**Métricas relacionadas con los costos:** en la Cohorte, los datos de costos se incluyen solo si hay una atribución asociada (instalación, re-engagement o reatribución). En otras palabras, si una campaña incurre en costos basados en clics e impresiones, pero no tiene atribuciones, el costo no se incluye en los reportes de cohorte. Este principio es cierto para todos los niveles de la jerarquía publicitaria.</li><li>Costo: AppsFlyer no reporta los datos de costos de las palabras clave que contienen letras mayúsculas en el reporte de cohorte o la API de cohorte.</li></ul> |
| Moneda específica de la aplicación | <ul><li>Disponible</li><li>Excepción: todas las aplicaciones deben usar la misma divisa. Si no lo hacen, se usa USD.</li></ul> |
| Archivos de descarga CSV: | <ul><li>Máximo 10 000 filas</li><li>Ejemplo: Tendencia del rendimiento de la vida útil del usuario vs. KPI por tendencia del momento de atribución</li><li>Límite de 10 exportaciones de CSV por minuto y 100 por día (por usuario).</li></ul> |
| CohortGraph.png | Los gráficos muestran los primeros 5 o 10 clasificados por la cantidad de usuarios de la aplicación en la cohorte. Esto independiente de la dimensión que se muestra. |
| Tabla | Las tablas muestran hasta 50 filas. Los usuarios, el costo y el promedio de eCPI (costo efectivo por instalación) siempre se muestran independientemente de la métrica seleccionada. |
| Reinstalaciones | <ul><li>Reinstalaciones: si los eventos posteriores a la reinstalación se consideran orgánicos no atribuidos, no se incluyen en la Cohorte.<ul><li>Se incluirán solo a partir del 26 de mayo de 2024. <Anchor target="_blank" href="/marketers/es/docs/bulletin-cohort-data-includes-unattributed-sessions-and-events">Más información</Anchor></li><li>El tiempo de instalación se basa en el campo <Anchor target="_blank" href="/marketers/es/docs/raw-data-field-dictionary#device-info::dfd9504e">device\_download\_time</Anchor>.</li><li>No se cuentan para las mediciones de usuarios únicos y de retención.</li></ul></li><li>Si los eventos post-reinstalación se atribuyen a la primera instalación, siempre se incluyen. <Anchor target="_blank" href="/marketers/es/docs/measure-reinstalls#inapp-events-and-how-they-are-attributed">Aprender más</Anchor></li></ul> |
| Consultas de datos | Límite de 20 consultas de datos por minuto y 500 por día (por usuario). El cambio de periodo de tiempo, agrupación, KPI, etc. se considera una nueva consulta. |
| datos orgánicos | Incluidos |
| Datos no orgánicos | Incluidos |
| Actualización de los datos | <ul><li><Anchor target="_blank" href="/marketers/es/docs/about-data-freshness-and-timezone-support#eod">Tiempo real</Anchor></li><li>Excepciones:<ul><li>Cohortes diarias:<ul><li>Las métricas de costo, ingresos por publicidad y desinstalaciones se actualizan diariamente.</li><li>Las desinstalaciones se calculan una vez al día mediante el reloj UTC.</li></ul></li><li>Cohortes semanales y mensuales:<ul><li>No hay datos en tiempo real disponibles. Los datos solo se mostrarán después de que se haya completado (es decir, al final de la semana o mes).<br />Sin embargo, se mostrarán datos en aquellos casos en que algunos datos de instalación se hayan completado, por ejemplo si algunos datos han finalizado (tiempo post-instalación) y otros aún no se han iniciado.</li></ul></li></ul></li></ul> |
| Historial de datos | <ul><li>Cohorte diaria: 2 años</li><li>Cohortes semanales/mensuales: 3 años</li></ul> |
| Geografía | <ul><li>Disponible</li><li>Cuando se desconoce la geolocalización (N/A), los datos de ingresos por publicidad no se muestran al agrupar por geolocalización.</li></ul> |
| Recuento de sesiones | El recuento de sesiones para el día 0 en la vista de retargeting podría ser inferior al recuento de usuarios.<br />Hay algunas razones por las que esto puede suceder. Las más comunes son:<ul><li>La sesión de re-engagement ya se atribuyó antes de registrar el re-engagement. En este caso, no se atribuirá a la sesión de retargeting.</li><li>Filtrado por otros ajustes como el **Tiempo mínimo entre sesiones**. En este caso, se registra el re-engagement. Sin embargo, las sesiones se filtran y no se registran.</li></ul> |
| Datos unificados y de retargeting | Los datos mensuales de la sesión solo están disponibles a partir del 1 de septiembre de 2021. |
| Ingresos por anuncios | <ul><li>No disponible al visualizar cohortes con granularidad horaria.</li><li>Puede haber discrepancias entre los importes de los ingresos por publicidad que se muestran en los paneles control de Cohorte y General. Esto ocurre cuando las redes reportan los ingresos en UTC y las aplicaciones tienen una configuración de zona horaria diferente.</li><li>Para los eventos af\_ad\_revenue, la métrica de usuarios únicos no está disponible cuando el tipo de agregación es:<ul><li>"Acumulativa".</li><li>"En el día" para fechas entre el 5 de octubre de 2022 y el 16 de febrero de 2023.</li></ul></li></ul> |
| Granularidad de semana y mes | <ul><li>La granularidad de semana y mes solo está disponible en el panel de control de la cohorte.</li><li>Las métricas de **usuarios únicos** y **tasa de conversión** no están disponibles si los datos incluyen instalaciones anteriores a noviembre de 2022.</li><li>Los datos históricos solo están disponibles a partir del año 2021 y en adelante.</li><li>Días posteriores a la instalación: Para cohortes que incluyen instalaciones de enero de 2021 a diciembre de 2022, el tiempo posterior a la instalación está limitado a un año (lo que significa 52 semanas o 12 meses). Para cohortes que incluyen instalaciones posteriores, los datos posteriores a la instalación están disponibles por hasta 3 años (lo que significa 156 semanas o 36 meses).</li></ul> |
| Periodo de cohorte | <ul><li>El día de conversión se denomina día 0 posterior a la conversión. El siguiente como día 1 posterior a la conversión y así sucesivamente.</li><li>En AppsFlyer un período de cohorte no toma en cuenta la marca de tiempo de instalación específica. Más bien, las horas de cohorte se redondean a la hora más cercana, y los días, semanas y meses de cohorte se basan en el día, semana o mes calendario. Esto puede causar discrepancias al comparar los datos de cohortes de AppsFlyer con los datos de cohorte de otras redes, donde todos los períodos de cohorte están determinados por la marca de tiempo de instalación específica (es decir, una hora es 60 minutos después de la instalación, un día es el período post-instalación de 24 horas después de la marca de tiempo de instalación, etc.).</li><li>La consulta del periodo máximo de cohorte (intervalo de tiempo) es de 60 días para granularidad diaria, 60 horas para la horaria, 12 meses para la mensual y 26 semanas para la semanal.</li></ul> |
| "event\_name" | Recomendación: Elige nombres descriptivos para tus eventos in-app, no simplemente «Revenue». Un evento in-app llamado «Revenue» a veces puede generar confusión e interferir con otras métricas de ingresos. |
| Calificación | Al filtrar por campañas, puedes seleccionar hasta 100 valores. |
| Datos parciales | Los datos parciales solo están disponibles para marcos de tiempo diarios; no para marcos horarios, semanales ni mensuales. |
| KPIdays.jpg | Los 1.000 principales eventos in-app (por recuento de eventos) se muestran en orden alfabético en el menú desplegable de la configuración del análisis de cohorte. |

</Accordion>

<div data-zendesk-anchors="cohort-dashboard=panel-de-control-de-cohorte-y-retenci%C3%B3n 01H7T5AGP75A36TVWSM7H81E8P=panel-de-control-de-cohorte-y-retenci%C3%B3n 01H7T5AGP7SGPZNK8VTDYBTY2B=consejo using-cohort=uso-de-la-cohorte 01H7T5AGP7XDKN85TR0J4V8TP3=uso-de-la-cohorte 01H7T5AGP7FDZNVM9PDBQJPMA0=setting-up-an-analysis using-my-reports%E2%80%94save-and-select-reports=using-my-reports-save-and-select-reports 01H7T5AGP8KRZ9207DCYGRGGC0=using-my-reports-save-and-select-reports 01H7T5AGP84HVD2BQ9Z8S13D5K=export-the-cohort-to-a-csv-file cohort-concepts=principios-de-la-cohorte 01H8K817ZPJTRBP1KK90FVV57T=principios-de-la-cohorte 01H8K817ZPZTG476KZ83F6Z460=cohort-periods h_01JJH967X8P2NF3AFBSNMBD7B4=view-types 01H8K817ZPBVTGT5R18XGQHYT2=trend-types user-lifetime-performance=usuarios-4 01H8VNMYN0149T418BXM8RGBN9=usuarios-4 kpi-by-attribution-time=kpi-por-momento-de-atribuci%C3%B3n 01H8VNRGMWS8SSDM5KX08EDAS2=kpi-por-momento-de-atribuci%C3%B3n example-user-lifetime-performance-trend-vs-kpi-by-attribution-time-trend=no-est%C3%A1-disponible-para-la-tendencia-de-kpi-por-momento-de-atribuci%C3%B3n 01H8K98XE9T23QGB440GHRB8E8=no-est%C3%A1-disponible-para-la-tendencia-de-kpi-por-momento-de-atribuci%C3%B3n 01H7T5AGP8PN12P2C4RGGQ0R95=partial-data 01H7T5AGP8XNG1CW2FPJSEEJ45=list-of-dimensions-for-grouping-and-filtering time-in-the-case-of%0A%20%20%0A%20%20daily-granularity-is-the-date%0A%20%20hourly-granularity-is-the-hour-of-the-day%0A%20%20weekly-granularity-is-the-week-of-the-year%0A%20%20monthly-granularity-is-the-month-of-the-year=time-in-the-case-of-daily-granularity-is-the-date-hourly-granularity-is-the-hour-of-the-day-weekly-granularity-is-the-week-of-the-year-monthly-granularity-is-the-month-of-the-year 01H7T5AGP708H7JGTS1RJ07H27=metrics-available information=informaci%C3%B3n-adicional 01H7T5AGP8J9AQ1BREYZ0JWWZ4=informaci%C3%B3n-adicional 01H7T5AGP83FRX1H9WVMS485MT=cohort-for-agencies 01H7T5AGP8JF0EAX8WEFNSEKM9=use-cases revenue-sum-by-country=suma-de-ingresos-por-pa%C3%ADs 01H7T5AGP8R6913GPXWM6DGASF=suma-de-ingresos-por-pa%C3%ADs inapp-event-conversion=conversi%C3%B3n-de-eventos-in-app 01H7T5AGP80W5J1VEZ40MHGPPF=conversi%C3%B3n-de-eventos-in-app 01H7T5AGP85T7H25863GXJCVCW=faq 01H7T5AGP90NADB7YXTFEMTSAX=traits-and-limitations" />
