---
title: Panel de control de Protect360
metadata:
  keywords:
    - dashboard
    - Advertisers
    - Protect360
    - protect 360
    - '360'
    - P360
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2020-08-11T09:58:07Z'
  edited_at: '2026-08-12T11:55:19Z'
  id: 360011793077
  locale: es
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/es/articles/360011793077
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En resumen:** El panel de control de Protect360 proporciona información sobre el tráfico fraudulento y las instalaciones bloqueadas debido a la aplicación de reglas de validación.

<div id="about-protect360-dashboard" />

## Acerca del panel de control de Protect360

El panel de control de Protect360:

* Muestra los datos agregados de fraude a nivel cuenta.
* Tiene dos vistas del panel:
  * Instalaciones (CPI [Costo por instalación])
  * Eventos in-app (CPA [Costo por acción])
* Organiza el fraude en función de categorías, entre ellas:
  * Instalaciones falsas frente a secuestradas
  * Fraude bloqueado en tiempo real frente a fraude identificado después de la atribución
  * Fraude de UA frente a campañas de retargeting
* Permite profundizar para examinar más a fondo los eventos fraudulentos utilizando las opciones de filtrado y agrupación.

Para ver el panel de control de Protect360, en AppsFlyer, ve a **Optimizar** > **Protect360.** 

<div id="filters-and-groupings" />

<Accordion title="Filtros y agrupaciones">

**Ventana de filtros y agrupaciones**

[![p360_filters_2.png](https://files.readme.io/9fd2afbbfc1bdf671ae0427d75c1020085b36da724e40dcfe57da27943e15b0c-4408431325969.png)](https://files.readme.io/9fd2afbbfc1bdf671ae0427d75c1020085b36da724e40dcfe57da27943e15b0c-4408431325969.png)

Las siguientes opciones de filtrado y agrupación están disponibles:

* Filtros básicos:
  * Nombre de aplicación
  * Tipo de fuente: No orgánico y/o orgánico
  * Fuente de medios
  * Geolocalización
  * Rango de fechas (<Anchor target="_blank" href="/marketers/es/docs/about-data-freshness-and-timezone-support#protect360-dashboard">ver soporte de zona horaria</Anchor>)
  * Tipo de atribución Instalaciones, reatribuciones y re-engagements.
  * [Eventos de pago](/docs/protect360-dashboard#payable-events) (disponibles en el panel de control de eventos de in-app)
* Filtros ampliados: haz clic en la flecha azul, a la derecha del selector de fecha:
  * Agencias
  * Campañas
  * Canales
* Opciones de agrupación: elige entre diferentes dimensiones para agrupar los datos sobre fraude y obtener los insights específicos que necesitas:
  * **Aplicación:** Compara la cantidad total de fraude en cada una de tus aplicaciones.
  * **Fuente de medios**(predeterminada): Compara el fraude identificado en cada una de las fuentes de medios utilizadas por tus aplicaciones
  * Fuente de medios/campaña Compara el fraude identificado en todas tus campañas en todas las fuentes de medios utilizadas por tus aplicaciones
  * **Fuente del medio + ID del sitio**: Compara el fraude identificado de todos los editores (ID de sitios) en todas las fuentes de medios utilizadas por tus aplicaciones
  * **Fuente de medios + ID del sitio + Campaña**: Compara el fraude identificado de todos los editores (ID de sitios) en todas las fuentes de medios utilizadas por tus aplicaciones, asociadas con los nombres de campaña relevantes
  * **Fuente de medios + Geolocalización** (disponible en el panel de control Eventos in-app): compara los casos de fraude identificados de cada una de las fuentes de medios utilizadas por tus aplicaciones asociadas con los países relevantes.
  * **Fuente del medio + Tipo de atribución**: Compara el fraude identificado de cada una de tus fuentes de medios, asociado con el tipo de atribución seleccionado (instalaciones, reatribuciones y/o nuevos engagements)
  * **Geolocalización**: compara los casos de fraude identificados de todos los países.

</Accordion>

<div id="installs-dashboard" />

## Panel de control de instalaciones

El panel de control de instalaciones muestra datos basados en el valor de vida útil (LTV), es decir, datos relacionados con instalaciones, reatribuciones y re-engagements que ocurrieron durante el intervalo de fechas seleccionado.

Las funciones del panel de control se describen en las siguientes secciones.

<div id="installs-headline-metrics" />

<Accordion title="Instalaciones: métricas principales">

Las métricas principales te permiten ver:

* **Atribuciones fraudulentas identificadas** - Número total de instalaciones fraudulentas
* Clics bloqueados debido a fraude (incluidos los limitados)
* **Total de atribuciones etiquetadas** - Total de atribuciones etiquetadas
* En la sección **Filtrar por** del panel de control de actividades in-app, habilita los Eventos de pago.
* **Instalaciones comprometidas identificadas** - Número de instalaciones detectadas con engagement no auténtico
* **Engagement promedio por instalación** - Número promedio de  engagement asociado con la instalación

Para cada KPI, hay un valor porcentual. Este valor muestra cómo se encuentra el KPI presentado en relación con el intervalo de fechas paralelo anterior. Por ejemplo, esta semana comparada con la anterior, o cualquier día seleccionado en el rango de fechas comparado con la misma cantidad de días que vinieron antes: si muestra un aumento del X% en el ahorro estimado, significa que el rango de fechas paralelo anterior tuvo un X% menos de instalaciones, reatribuciones y re-engagements.

**Atribuciones fraudulentas identificadas**

[<Image alt="" src="https://files.readme.io/262403803bd074e4742f63d7998d4642e3b17781e178ed3bc24b35dd958ca262-4408437121297.png" width="100%" />](https://files.readme.io/262403803bd074e4742f63d7998d4642e3b17781e178ed3bc24b35dd958ca262-4408437121297.png)

Las métricas del fraude total identificado muestran las cantidades de:

* Instalaciones, reatribuciones y re-engagements fraudulentos bloqueados en tiempo real por todas las diversas razones de bloqueo de fraude.
* Instalaciones, reatribuciones y re-engagements identificados como fraude posterior a la atribución.

**Eventos in-app bloqueados**

[<Image alt="" src="https://files.readme.io/ed6692be83cae6a6bee556e5c763d6313c0d32cb577a9587caac41c54b51b378-4403139249809.png" width="100%" />](https://files.readme.io/ed6692be83cae6a6bee556e5c763d6313c0d32cb577a9587caac41c54b51b378-4403139249809.png)

Las métricas de eventos in-app bloqueados muestran la cantidad de eventos in-app bloqueados por AppsFlyer. Los eventos pueden haberse bloqueado debido a que pertenecen a instalaciones bloqueadas o porque se los marcó como eventos sospechosos posteriores a la atribución.

**Total de atribuciones etiquetadas**

[<Image alt="" src="https://files.readme.io/49e705c39b88c243af92c88e33d1939d1ec54b6a83e94724bdef702c9442a6a6-32184720638097.png" width="100%" />](https://files.readme.io/49e705c39b88c243af92c88e33d1939d1ec54b6a83e94724bdef702c9442a6a6-32184720638097.png)

Las métricas de atribuciones etiquetadas muestran el número de instalaciones que se reconocieron como fraude, pero que el usuario ha marcado como etiquetadas y no bloqueadas. esto no incluye eventos in-app.

**Número de eventos fraudulentos (in-app)**

[<Image alt="" src="https://files.readme.io/79650837a722efdc3bea39664f0d5eb774ac6acbfb15e5f64d9a56f7c03b21fe-32637238112145.png" width="100%" />](https://files.readme.io/49e705c39b88c243af92c88e33d1939d1ec54b6a83e94724bdef702c9442a6a6-32184720638097.png)

Las métricas de eventos in-app etiquetados muestran el número de instalaciones que se reconocieron como fraude, pero que el usuario ha marcado como etiquetadas y no bloqueadas.

**Posterior a la atribución Eventos fraudulentos identificados después de la atribución**

<Image alt="" src="https://files.readme.io/60fdba97e9eb920e26ac2667431b760a7dee62b53396196403d68326bff6c3cc-41459847283729.png" width="624px" />

Instalaciones en las que la lógica de atribución de AppsFlyer detectó que el dispositivo estaba siendo saturado con engagement no auténtico.

**Engagement promedio por instalación**

<Image alt="" src="https://files.readme.io/edb695ad30e16e403d953fd0fad274d5733ca4e2dc411baad7bbe4179cfcd0b0-41459862819857.png" width="624px" />

 Engagement promedio por instalación muestra el número promedio de engagement asociado con la instalación.

</Accordion>

<div id="installs-charts" />

<Accordion title="Instalaciones : gráficos">

<div id="identified-fraud-trend-chart" />

#### Gráfico de tendencias del fraude identificado

El gráfico de tendencias del fraude identificado muestra el número de instalaciones, reatribuciones y re-engagements fraudulentos por día, desglosado por:

* **Tipo de detección**: Instalaciones bloqueadas en tiempo real e instalaciones identificadas como fraude después de la atribución.
* **Tipo de atribución**: Instalaciones, reatribuciones y re-engagements.
* **Tipo de fuente**: No orgánico y orgánico
* **Estado de detección**: comparación de datos etiquetados, no etiquetados y bloqueados.
* **Tasa de comprometidas**: total de atribuciones marcadas como comprometidas del total de atribuciones.

Se puede mostrar como un gráfico de líneas o un gráfico de barras.

<div id="hijacked-installs-attribution-correction-chart" />

#### Gráfico de corrección de atribución de instalaciones secuestradas

El gráfico de corrección de la atribución de instalaciones secuestradas muestra las fuentes de medios que intentaron atribuirse el mérito de instalaciones, reatribuciones y re-engagements, así como las últimas fuentes colaboradoras válidas.

Podrás hacer lo siguiente:

* Filtra por atribuciones secuestradas identificadas en tiempo real, posteriores a la atribución o atribuciones identificadas mediante reglas de validación.
* Configura a qué fuentes válidas se corrige la atribución o desde qué fuentes secuestradas se corrigió la atribución.
* Cambia la vista de gráfico a un formato de tabla y descarga los datos como un archivo CSV.

**Nota:**

* Solo los anunciantes pueden acceder a este gráfico. Las agencias y redes de publicidad no tienen acceso.
* Cuando los secuestros se bloquean en tiempo real, las atribuciones correctas se muestran en los paneles de control y reportes de AppsFlyer (no solo en Protect360). Cuando se identifican secuestros después de la atribución, las atribuciones correctas se muestran solo en el raw data de Protect360.
* Este gráfico puede mostrar la corrección **a** orgánico, pero no **desde** orgánico.

<div id="identified-fraud-chart" />

#### Gráfico de fraude identificado

El gráfico de fraude identificado muestra los tipos de fraude que experimentas, por porcentaje. El desglose del fraude puede realizarse por:

* Razón del bloqueo
* <Anchor target="_blank" href="/marketers/es/docs/protect360-raw-data-reports#nivel-de-instalación-motivos-para-el-bloqueo-de-instalaciones-falsas">Submotivo del bloqueo</Anchor>
* Tipo de etiqueta
* Motivo de la etiqueta
* Submotivo de la etiqueta
* Fuente de medios
* Campaña
* Geolocalización
* Aplicación

<div id="affiliate-attribution-model" />

#### Modelo de atribución de afiliados

El nuevo **Modelo de atribución de afiliados** de AppsFlyer aborda directamente el problema del click-flooding. En su núcleo hay un algoritmo de atribución específico que detecta activamente los dispositivos saturados y valida el engagement mediante métodos de autenticación y análisis del comportamiento con IA en tiempo real. El resultado es una atribución imparcial, resistente al fraude y basada en la intención real del usuario.

* **Tasa de comprometidas:** total de atribuciones marcadas como comprometidas del total de atribuciones
* **Reflexión del candidato:**
  * Candidatos por comprometida: número promedio de candidatos del total de atribuciones **marcadas** como comprometidas
  * Candidatos por no comprometida: número promedio de candidatos del total de atribuciones **no** **marcadas** como comprometidas
* Estas métricas también se reflejan en el gráfico de tendencias a lo largo del tiempo:
  * Número total de instalaciones fraudulentas,
  * Candidatos por comprometida
  * Candidatos por no comprometida

Las instalaciones comprometidas son instalaciones en las que la lógica de atribución de AppsFlyer detectó que el dispositivo estaba siendo saturado con engagement no auténtico. Esto indica que el dispositivo estaba sometido a una intensa manipulación por flooding y se refiere específicamente a casos en los que se manipulan instalaciones

</Accordion>

<div id="installs-table" />

<Accordion title="Instalaciones: tabla">

<div id="identified-fraud-breakdown" />

#### Desglose de casos de fraude identificados

La tabla de **desglose de casos de fraude identificados** muestra los siguientes datos:

* Fraude bloqueado en tiempo real
* Fraude identificado y marcado posterior a la atribución
* Otras indicaciones de fraude por fuente de medios

La tabla se presenta en un formato de vista general, tal como se muestra en la imagen a continuación.

[![p360_main_table.png](https://files.readme.io/15885268068f2b57e9b22b7028a824951690e737a47cb154cd38d1ddf79937b8-4408431449745.png)](https://files.readme.io/15885268068f2b57e9b22b7028a824951690e737a47cb154cd38d1ddf79937b8-4408431449745.png)

Estructura dinámica de la tabla:

* Te permite hacer clic en el botón de configuración de la tabla para agregar o eliminar columnas de la tabla.  
  Si realizas algún cambio en la tabla, asegúrate de hacer clic en el botón **Guardar**.
* Es por usuario, por lo que cada usuario de cuenta con acceso a Protect360 puede personalizar personalmente su propia estructura de tabla. Ver [más opciones de tabla](/docs/protect360-dashboard#opciones-adicionales-de-la-tabla).

[![edit_table.jpg](https://files.readme.io/fcde2bc6970c29902dd7585ee92c2bc38edf1d5c56e65de4e3f10df784108e5c-360011641617.jpg)](https://files.readme.io/fcde2bc6970c29902dd7585ee92c2bc38edf1d5c56e65de4e3f10df784108e5c-360011641617.jpg)

<div id="content-of-the-identified-fraud-breakdown-table" />

#### Contenido de la tabla de desglose de casos de fraude identificados

| Columna de tabla | Descripción |
| --- | --- |
| Agrupaciones | <ul><li>[Predeterminado] La tabla y el panel de control están agrupados por fuente de medios.</li><li>Al seleccionar una fuente de medios específica, la agrupación se realiza automáticamente por ID del sitio y fuente de medios.</li><li>Los grupos opcionales incluyen Campaña, Geolocalización, Canal, Agencia, Agencia + Fuentes de medios, y combinaciones de estos grupos.</li><li>Si seleccionas una agrupación con dimensiones que solo se aplican al tráfico no orgánico, la tabla muestra N/A para la fuente de medios orgánica.</li></ul> |
| **Atribuciones** | **Desglose principal de instalaciones fraudulentas bloqueadas y posteriores a la atribución.** |
| Total (A) | <ul><li>Instalaciones totales = instalaciones regulares (no fraudulentas) + instalaciones bloqueadas</li><li>Las instalaciones regulares están disponibles por fuente de medios (no orgánicas) en el Panel de control de información general.</li></ul> |
| Bloqueos (B) | <ul><li>Cantidad total de instalaciones bloqueadas.</li><li>[Predeterminado] La tabla está ordenada por este KPI en forma descendente.</li></ul> |
| % bloqueado (B/A) | Instalaciones bloqueadas/total de instalaciones |
| Posterior a la atribución (C) | Instalaciones identificadas como fraude posterior a la atribución. |
| Porcentaje posterior a la atribución (C/A) | Instalaciones posteriores a la atribución/cantidad total de instalaciones |
| Instalaciones fraudulentas totales (D) | Instalaciones fraudulentas, bloqueadas en tiempo real o identificadas como fraudulentas posteriores a la atribución. |
| % de instalaciones fraudulentas (D/A) | Instalaciones fraudulentas/número total de instalaciones |
| **Desglose del tipo de atribución de fraude** | **Los tipos de atribución de las instalaciones fraudulentas, desglosados por instalaciones, reatribuciones y re-engagements.** |
| Instalaciones | Fraude originado en una campaña UA. |
| Reatribuciones | El fraude se originó en una campaña de retargeting que llevó a una instalación. |
| Reenganches | El fraude se originó en una campaña de retargeting que llevó a un re-engagement. |
| **Falsos** | **Instalaciones o reatribuciones fraudulentas que simulan la actividad real del usuario, divididas en bloqueos en tiempo real y posterior a la atribución.** |
| Bloqueo en tiempo real | Instalaciones falsas bloqueadas en tiempo real. |
| Fraude posterior a la atribución | Instalaciones falsas identificadas como fraude posterior a la atribución. |
| **Secuestrados** | **Últimos clics fraudulentos que roban la atribución de instalaciones de usuarios reales, dividido por bloqueos en tiempo real y posterior a la atribución.** |
| Bloqueo en tiempo real | Instalaciones secuestradas bloqueadas en tiempo real. |
| Fraude posterior a la atribución | Instalaciones secuestradas identificadas como fraude posterior a la atribución. |
| **Reglas de validación** | **Instalaciones que cumplen con las condiciones de las reglas de validación.** |
| Instalaciones bloqueadas | Instalaciones bloqueadas por las reglas de validación. |
| Atribución bloqueada | Cambios de atribución de instalaciones debido a las reglas de validación. |
| **Desglose de instalaciones falsas bloqueadas** | **Desglose de las instalaciones falsas y fraudulentas bloqueadas y posteriores a la atribución, que por lo general se efectúa de manera programática** |
| Bloqueos por lista de denegación de ID de sitios | Instalaciones bloqueadas debido a que Protect360 incluye en la lista de denegación el SiteID. |
| Lista de denegación de ID de sitios después de la atribución | Instalaciones marcadas como fraude debido a que Protect360 incluye en la lista de denegación el SiteID posterior a la atribución. |
| Bots bloqueados | Intentos de instalación bloqueados realizados por bots automáticos. |
| Bots posteriores a la atribución | Instalaciones marcadas como fraude debido a actividades de bots automáticos identificadas después de la atribución |
| Bloqueos por anomalías de comportamiento | Instalaciones bloqueadas debido a anomalías de comportamiento, es decir, actividad anormal de usuarios en sesiones y eventos in-app. |
| Anomalías de comportamiento posterior a la atribución | Instalaciones marcadas como fraude debido a anomalías de comportamiento posteriores a la atribución. |
| Validación de instalación bloqueada | Total de instalaciones bloqueadas debido a una validación negativa de la tienda. |
| **Desglose de instalaciones secuestradas bloqueadas** | **Desglose de los últimos clics fraudulentos destinados a robar la atribución de instalaciones de aplicaciones reales de usuarios** |
| Secuestro de instalaciones bloqueados | Bloqueos por secuestro de instalaciones de la fuente. |
| Secuestro de instalaciones posteriores de la atribución | Secuestro de instalaciones marcadas como fraude posterior a la atribución. |
| Anomalías en el CTIT bloqueadas | Instalaciones bloqueadas debido a anomalías en el CTIT. |
| Anomalías en el CTIT posteriores a la atribución | Anomalías en el CTIT marcadas como fraude posterior a la atribución. |
| Inundación de clics bloqueados | Instalaciones bloqueadas debido a una inundación de clics (intentos fraudulentos de enviar grandes cantidades de clics con la esperanza de lograr los últimos clics antes de las instalaciones aleatorias). |
| Inundación de clics posteriores de la atribución | Instalaciones por inundación de clics marcadas como fraude posterior a la atribución. |
| **Clics** | **Clics de la fuente**<br /><br />Nota: **Nota:** Todos los tipos de atribución deben seleccionarse en la barra de filtros para que los datos de clics se muestren en la tabla (de lo contrario se mostrará como N/A). Asegúrate de ajustar tus selecciones de filtro de igual manera. |
| Total (E) | Número total de clics legítimos y fraudulentos recibidos de la fuente |
| Bloqueos | Clics bloqueados debido a la limitación de clics |
| **Impresiones** | **Impresiones de la fuente**<br /><br />**Nota:** **Nota:** Todos los tipos de atribución deben seleccionarse en la barra de filtros para que los datos de impresiones se muestren en la tabla (de lo contrario se mostrará como N/A). Asegúrate de ajustar tus selecciones de filtro de igual manera. |
| Total | Número total de impresiones legítimas y fraudulentas recibidas de la fuente |
| Bloqueos | Impresiones bloqueadas debido a fraude (incluidas las limitadas) |
| **Eventos in-app** | **Eventos in-app desde la fuente**<br /><br />Nota: **Nota:** Esto incluye eventos in-app de instalaciones; no reatribuciones ni re-engagements. |
| Total (G) | Total de eventos in-app |
| Bloqueado (H) | Eventos in-app bloqueados |
| Porcentaje (H/G) | Eventos in-app bloqueados/total de eventos in-app |
| **Indicadores de granjas de dispositivos** | **Indicadores de actividad fraudulenta de granjas de dispositivos que emplean el fraude por restablecimiento del ID de dispositivo y el rastreo limitado de anuncios (LAT).**<br /><br />**Nota:** **Nota:** Esto incluye instalaciones y reatribuciones; no re-engagements. |
| Instalaciones (I) | Las instalaciones con un ID de dispositivo nuevo desconocido para AppsFlyer. |
| Porcentaje de instalaciones (I/A) | Instalaciones de dispositivos nuevos/cantidad total de instalaciones |
| % de usuarios leales | KPI general que indica si los usuarios son reales o falsos. |
| **Indicadores de inundación de clics** | **Indicaciones de fraude por inundación de clics basadas en tasas anormales de conversión o asistencia, o tiempo CTIT.** |
| Tasa de conversión (%) | Un porcentaje bajo en comparación con la tasa de conversión general de la aplicación indica fraude por inundación de clics.<br /><br />**Nota**: Todos los tipos de atribución deben seleccionarse en la barra de filtro para que los datos de la tasa de conversión se muestren en la tabla (de lo contrario, se mostrarán como N/D). Asegúrate de ajustar tus selecciones de filtro de igual manera. |
| % de asistencias | Un porcentaje alto en comparación con otras fuentes de medios (en el widget de asistencias de la página de información general) indica fraude por inundación de clics. |
| CTIT > Más de 60 minutos | Instalaciones, reatribuciones y re-engagements en los que el tiempo entre el clic y el primer inicio de la aplicación es de más de 60 minutos. El cálculo solo incluye las instalaciones cuyo CTIT sea inferior a 25 horas (y no todas las instalaciones). Normalmente, alrededor del 30 % de los primeros inicios de la aplicación tienen lugar más de 60 minutos después de la descarga. |
| CTIT > Más de 5 horas | Instalaciones, reatribuciones y re-engagements en los que el tiempo entre el clic y el primer inicio de la aplicación es de más de 5 horas. El cálculo solo incluye las instalaciones cuyo CTIT sea inferior a 25 horas (y no todas las instalaciones). Normalmente, alrededor del 20 % de los primeros inicios de la aplicación tienen lugar más de 5 horas después de la descarga. |

<div id="additional-table-options" />

#### Opciones adicionales de la tabla

* Haz clic en el botón **Exportar CSV** para descargar la tabla en tu escritorio en formato CSV.
* Haz clic en el icono de engranaje para:
  * Cambiar el orden de las columnas de la tabla
  * Agregar o eliminar las columnas descritas anteriormente
  * Agregar o eliminar de la tabla cualquiera de los **eventos in-app recientemente bloqueados** de tu aplicación. Por cada evento in-app agregado, se muestran las siguientes columnas pertinentes:

| Columna de tabla | Descripción |
| --- | --- |
| Contador de eventos (total) | Cantidad de bloqueos del evento específico |
| Usuarios únicos | Cantidad de usuarios únicos con el evento específico bloqueado |

Ten en cuenta que las tasas poco comunes de cualquiera de estos KPIs no indican fraude necesariamente, ya que muchos eventos se bloquean debido a instalaciones fraudulentas posteriores a la atribución.

Los datos de eventos in-app en el panel de control de costo por instalación (CPI) se basan en LTV, lo que significa que son todos los eventos in-app asociados con las instalaciones que ocurrieron durante el rango de fechas especificado.

</Accordion>

<div id="in-app-events-dashboard" />

## Panel de control de eventos in-app

El panel de control de eventos in-app muestra los datos basados en actividades, es decir, los datos relacionados con los eventos in-app que ocurrieron durante el intervalo de fechas seleccionado, incluyendo los eventos de instalaciones que ocurrieron antes del intervalo de fechas.

Las funciones del panel de control se describen en las siguientes secciones.

<div id="inapp-events-headline-metrics" />

<Accordion title="Eventos in-app : métricas principales">

[![](https://files.readme.io/ea33b3ddafc4265eb74b2e1070a77a6afbad429a1aeb20cd1579127f7e8ee605-360012501757.jpg)](https://files.readme.io/ea33b3ddafc4265eb74b2e1070a77a6afbad429a1aeb20cd1579127f7e8ee605-360012501757.jpg)

Las métricas principales te permiten ver:

* Métricas de ahorro estimado:
  * Solo disponible si la opción [**Eventos de pago**](/docs/protect360-dashboard#payable-events) está activada.
  * Se basa en los eventos de pago que has configurado.
* Cantidad total de eventos in-app fraudulentos identificados

</Accordion>

<div id="inapp-events-charts" />

<Accordion title="Eventos in-app: gráficos">

<div id="fraud-trend-over-time-chart" />

#### **Gráfico de tendencia del fraude en el tiempo**

El gráfico de tendencia del fraude en el tiempo muestra la cantidad de eventos por día, desglosados en:

* **Tiempo real.** : Eventos in-app fraudulentos en la aplicación bloqueados en tiempo real
* **Posterior a la atribución**: Eventos fraudulentos identificados después de la atribución
* **No fraudulentos**

<div id="top-iae-fraud-by-media-source-chart" />

#### **Gráfico de los principales eventos in-app fraudulentos por fuente de medios**

La lista de los principales eventos in-app fraudulentos por fuente de medios incluye: 

* Las 5 fuentes de medios con la mayor cantidad de eventos in-app fraudulentos en orden descendente.
* Un gráfico de barras para cada barra de fuente de medios que muestra los siguientes tipos de eventos in-app como porcentaje del total de eventos in-app:
  * **Tiempo real.** : Eventos in-app fraudulentos en la aplicación bloqueados en tiempo real
  * **Posterior a la atribución**: Eventos fraudulentos identificados después de la atribución
  * **No fraudulentos**

</Accordion>

<div id="inapp-events-table" />

<Accordion title="Eventos in-app : tabla">

La tabla de **desglose de eventos in-app fraudulentos** muestra los siguientes datos:

* Fraude bloqueado en tiempo real
* Fraude identificado y marcado posterior a la atribución
* Otras indicaciones de fraude por fuente de medios

La tabla se presenta en un formato de vista general, tal como se muestra en la imagen a continuación.

[![IAE_fraud_table.jpg](https://files.readme.io/dd57a2508911b3e26268ad8cc4508d5402fa091ac95a77900c7f257486c99aeb-360012839758.jpg)](https://files.readme.io/dd57a2508911b3e26268ad8cc4508d5402fa091ac95a77900c7f257486c99aeb-360012839758.jpg)

Estructura dinámica de la tabla:

* Te permite hacer clic en el botón de configuración de la tabla para agregar o eliminar columnas de la tabla.  
  Si realizas algún cambio en la tabla, asegúrate de hacer clic en el botón **Guardar**.
* Es por usuario, por lo que cada usuario de cuenta con acceso a Protect360 puede personalizar personalmente su propia estructura de tabla. Ver [más opciones de tabla](/docs/protect360-dashboard#installs-table).

[![iae_table_structure.jpg](https://files.readme.io/5b2933e2b254d8fa268e30a72ae53691da391e365d781d55bcdb6cfeb1f40a6a-360012839778.jpg)](https://files.readme.io/5b2933e2b254d8fa268e30a72ae53691da391e365d781d55bcdb6cfeb1f40a6a-360012839778.jpg)

<div id="content-of-the-in-app-event-fraud-breakdown-table" />

#### Contenido de la tabla de desglose de eventos in-app fraudulentos

| Columna de tabla | Descripción |
| --- | --- |
| Agrupaciones | <ul><li>[Predeterminado] La tabla y el panel de control están agrupados por fuente de medios.</li><li>Al seleccionar una fuente de medios específica, la agrupación se realiza automáticamente por ID del sitio y fuente de medios.</li><li>Los grupos opcionales incluyen Campaña, Geolocalización, Canal, Agencia, Agencia + Fuentes de medios, y combinaciones de estos grupos.</li></ul> |
| **Eventos in-app** | **Muestra el valor del fraude bloqueado en tiempo real o identificado después de la atribución, que debes resolver con las redes de publicidad.** |
| IAE (A) total | <ul><li>IAE total = IAE regulares (no fraudulentas) + IAE bloqueadas + IAE identificadas como fraude después de la atribución.</li><li>Los IAE regulares están disponibles por fuente de medios (no orgánicos) en el panel de resumen general.</li></ul> |
| IAE fraudulento total (B) | <ul><li>Número total de IAE bloqueados + IAE identificados como fraude después de la atribución.</li><li>[Predeterminado] La tabla está ordenada por este KPI en forma descendente.</li></ul> |
| % de eventos fraudulentos (B/A) | IAE fraudulentas/IAE totales |
| **Bloques falsos de IAE en tiempo real** | **IAE fraudulentos bloqueados en tiempo real.** |
| IAE falso | IAE falso identificado como fraude y bloqueado en tiempo real. |
| Instalaciones falsas | La instalación original se identificó como fraudulenta y se bloqueó en tiempo real. |
| Instalaciones falsas posteriores a la atribución | La instalación original fue identificada como fraude después de la atribución, antes de la IAE. |
| **Recuperado de un secuestro en tiempo real** | **IAE con la instalación original secuestrada por una fuente fraudulenta, que AppsFlyer atribuye correctamente a la última fuente no fraudulenta.** |
| Corregido a orgánico | Instalaciones secuestradas con la última fuente no fraudulenta orgánica. |
| Corregido a la fuente no orgánica | Instalaciones secuestradas con la última fuente de medios no fraudulenta no orgánica. |
| **Fraude del IAE posterior a la atribución** | **Eventos in-app identificados como fraudulentos después de la atribución.** |
| Instalaciones falsas | El IAE ocurrió antes de que la instalación fuera identificada como fraude después de la atribución. |
| Instalaciones secuestradas (Hijacked installs) | El IAE se produjo antes de que se identificara la instalación como secuestrada, y no puede atribuirse correctamente después de la atribución. |
| **Reglas de validación** | **IAE bloqueados por cumplir condiciones de reglas de validación.** |
| Instalaciones bloqueadas | IAE de instalaciones bloqueadas por reglas de validación. |
| IAE bloqueado | IAE bloqueados por reglas de validación. |
| Corregido a orgánico | Instalaciones secuestradas con la última fuente no fraudulenta orgánica. |
| Corregido a la fuente no orgánica | Instalaciones secuestradas con la última fuente de medios no fraudulenta no orgánica. |

<div id="additional-table-options-1" />

#### Opciones adicionales de la tabla

* Haz clic en el botón **Exportar CSV** para descargar la tabla en tu escritorio en formato CSV.
* Haz clic en el icono de engranaje para:
  * Cambiar el orden de las columnas de la tabla
  * Agregar o eliminar las columnas descritas anteriormente

La cantidad de eventos que se muestra se basa en la actividad, no en el valor de vida útil (LTV), es decir, la cantidad exacta de bloqueos de eventos durante el intervalo de fechas especificado.

</Accordion>

<div id="payable-events" />

<Accordion title="Eventos de pago">

Los eventos de pagos son eventos in-app que tienen un costo. Una vez habilitado y configurado, el panel de control de actividades in-app solo muestra los datos relacionados con los eventos de pago.

Para habilitar los eventos de pago en el panel de control de actividades in-app:

* Desglose principal de eventos in-app fraudulentos bloqueados y posteriores a la atribución.  
  [![](https://files.readme.io/8162f6f4f6dcef50fbe0fd998b7a95d20deeb658dd53bafc216b75df050c734c-360012576718.jpg)](https://files.readme.io/8162f6f4f6dcef50fbe0fd998b7a95d20deeb658dd53bafc216b75df050c734c-360012576718.jpg)

Para configurar los eventos de pago:

1. En el panel de control de actividades in-app, haz clic en **Configurar eventos de pago**.

   [![](https://files.readme.io/00b1f4506f0c7ec8e1e1b90c16cc2232d2862b231b2673d2decc7a90b6c6b6af-360012505217.jpg)](https://files.readme.io/00b1f4506f0c7ec8e1e1b90c16cc2232d2862b231b2673d2decc7a90b6c6b6af-360012505217.jpg)

   Aparece la ventana emergente Configurar eventos de pago.

   [![](https://files.readme.io/4643b9d0e0042ca5860d21ec3eb3ff7e4178f92f1f4215db56adda10be41c452-360012580938.jpg)](https://files.readme.io/4643b9d0e0042ca5860d21ec3eb3ff7e4178f92f1f4215db56adda10be41c452-360012580938.jpg)
2. [Opcional] Si estás configurando un evento de pago nuevo, haz clic en **Agregar nuevo**.
3. En base a qué tipo de IAE de pago deseas mostrar en el panel de control, selecciona lo siguiente en los menús desplegables:
   * Apps
   * Eventos in-app
   * Fuentes de medios
   * Campañas
4. Ingresa el costo por acción (CPA) del IAE.
5. Haz clic en **Save** (Guardar).
6. Haz clic en **Cerrar.**

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Características y limitaciones">

| Caducado | Observaciones |
| --- | --- |
| Redireccionamiento | <ul><li>El panel de control de instalaciones (CPI) puede mostrar el desglose del tipo de toque atribuido entre instalaciones, reatribuciones y re-engagements.</li><li>El panel de control de evento in-app (CPA) muestra eventos fraudulentos de instalaciones de UA, pero no de retargeting. **Nota**: Los eventos fraudulentos procedentes de reatribuciones que se identifican en tiempo real pueden visualizarse en los reportes de raw data.</li></ul> |
| Datos históricos | Los datos están disponibles desde el inicio de la suscripción a Protect360 |
| Actualización de datos | Actualizado diariamente.<ul><li>Instalaciones (CPI) a las 16:00 UTC</li><li>Eventos in-app (CPA) a las 21:00 UTC</li></ul> |
| Impresiones bloqueadas debido a la limitación de impresiones | Si una fuente de medios no está disponible en el filtro, puede deberse a que todo su tráfico esté bloqueado.<br /><br />Para filtrar según la fuente de medios, puedes usar su enlace en la tabla de desglose de fraude identificado |

</Accordion>

<div id="see-also" />

> 📄 **Ver también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/protect360-anti-fraud-guide">Resumen general de Protect360</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/protect360-raw-data-reports">Reportes de raw data</Anchor>

<div data-zendesk-anchors="about-protect360-dashboard=acerca-del-panel-de-control-de-protect360 01H8H9GQ17C4PBHCAMXE879BX7=acerca-del-panel-de-control-de-protect360 01H8H9GQ173SQ8P29C4DETJRTD=filters-and-groupings installs-dashboard=panel-de-control-de-instalaciones 01H8H9GQ173H3QH1Y5KZ26XMCW=panel-de-control-de-instalaciones installs%E2%80%94headline-metrics=installs-headline-metrics 01H8H9GQ17FJKWE3M2YSZFTQCS=installs-headline-metrics installs%E2%80%94charts=installs-charts 01H8H9GQ18VHMK7FFV3RY409VB=installs-charts identified-fraud-trend-chart=gr%C3%A1fico-de-tendencias-del-fraude-identificado 01H8H9GQ18JDSZ2H8BKZVWGBPV=gr%C3%A1fico-de-tendencias-del-fraude-identificado hijacked-installs-attribution-correction-chart=gr%C3%A1fico-de-correcci%C3%B3n-de-atribuci%C3%B3n-de-instalaciones-secuestradas 01H8H9GQ18VXBPQRN55WHM3GG0=gr%C3%A1fico-de-correcci%C3%B3n-de-atribuci%C3%B3n-de-instalaciones-secuestradas identified-fraud-chart=gr%C3%A1fico-de-fraude-identificado 01H8H9GQ18FW87TXQZCYERHNDE=gr%C3%A1fico-de-fraude-identificado affiliate-attribution-model=modelo-de-atribuci%C3%B3n-de-afiliados h_01KQY7ARA2Z1WJ1V84X5GH832C=modelo-de-atribuci%C3%B3n-de-afiliados installs%E2%80%94table=installs-table 01H8H9GQ18FYXJA7TXQ4RNQGX2=installs-table identified-fraud-breakdown=desglose-de-casos-de-fraude-identificados 01H8H9GQ18540JJ8X833E6WF44=desglose-de-casos-de-fraude-identificados content-of-the-identified-fraud-breakdown-table=contenido-de-la-tabla-de-desglose-de-casos-de-fraude-identificados 01H8H9GQ18DMPD7YTPTN2XJMSH=contenido-de-la-tabla-de-desglose-de-casos-de-fraude-identificados additional-table-options=opciones-adicionales-de-la-tabla 01H8H9GQ18PZ8ABG3D51M7J91R=opciones-adicionales-de-la-tabla inapp-events-dashboard=panel-de-control-de-eventos-in-app 01H8H9GQ19CQZV00XA62MGVJ86=panel-de-control-de-eventos-in-app inapp-events%E2%80%94headline-metrics=inapp-events-headline-metrics 01H8H9GQ19B95MDK2WEHVNEFS5=inapp-events-headline-metrics inapp-events%E2%80%94charts=inapp-events-charts 01H8H9GQ19XEJ0HNY2Y8BMX7A5=inapp-events-charts fraud-trend-over-time-chart=gr%C3%A1fico-de-tendencia-del-fraude-en-el-tiempo 01H8H9GQ1969AB4KK4ENP8AVQJ=gr%C3%A1fico-de-tendencia-del-fraude-en-el-tiempo top-iae-fraud-by-media-source-chart=gr%C3%A1fico-de-los-principales-eventos-in-app-fraudulentos-por-fuente-de-medios 01H8H9GQ19Z078PK1HR7VEZHXG=gr%C3%A1fico-de-los-principales-eventos-in-app-fraudulentos-por-fuente-de-medios inapp-events%E2%80%94table=inapp-events-table 01H8H9GQ19PTNWGJV6YDWR7SH6=inapp-events-table content-of-the-inapp-event-fraud-breakdown-table=contenido-de-la-tabla-de-desglose-de-eventos-in-app-fraudulentos 01H8H9GQ19773CS8TGS2QXBRG5=contenido-de-la-tabla-de-desglose-de-eventos-in-app-fraudulentos additional-table-options::44e54bfa=opciones-adicionales-de-la-tabla-1 01H8H9GQ192WA6XFNW7CKGBQ03=opciones-adicionales-de-la-tabla-1 01H8H9GQ1AVAVQ31ZZA1K024RF=payable-events 01H8H9GQ1BJX0K01NX8VCC0690=traits-and-limitations h_01HE7S2JKX3VMRCF6913S4MCAR=ver-tambi%C3%A9n" />
