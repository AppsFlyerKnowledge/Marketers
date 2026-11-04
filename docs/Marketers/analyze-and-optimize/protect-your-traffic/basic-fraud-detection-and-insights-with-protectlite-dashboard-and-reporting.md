---
title: >-
  Detección básica de fraude e insights con el dashboard de ProtectLITE y
  reportes
metadata:
  keywords:
    - Advertisers
    - Protect360
    - Marketers
    - Protect360 / Fraud protection
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360 / Fraud protection
  created_at: '2021-01-25T09:47:02Z'
  edited_at: '2026-08-12T11:54:40Z'
  id: 360017223058
  locale: es
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/es/articles/360017223058
---
> **En resumen:** ProtectLITE proporciona insights sobre las instalaciones fraudulentas bloqueadas por nuestro motor de protección básico y gratuito, y las instalaciones bloqueadas debido a la aplicación de reglas de validación.

## ProtectLITE

ProtectLITE proporciona protección básica y gratuita contra el fraude de atribución de instalaciones. La protección y detección avanzadas contra el fraude están disponibles con <Anchor target="_blank" href="/marketers/es/docs/protect360-anti-fraud-guide">Protect360</Anchor>.

Cuando AppsFlyer identifica fraude, se bloquea en los datos de tráfico (disponibles a través de los dashboards de AppsFlyer y los reportes de raw data), pero no afecta a la experiencia del usuario de la aplicación. Esto significa que el usuario de la aplicación puede seguir usando la aplicación y generar ingresos para el anunciante.

El Dashboard de ProtectLITE:

* Muestra datos agregados de todas tus aplicaciones para las instalaciones bloqueadas en tiempo real, ya sea debido a instalaciones fraudulentas, instalaciones secuestradas o tus <Anchor target="_blank" href="/marketers/es/docs/implement-validation-rules-to-prevent-fraud">Reglas de validación</Anchor>.
* Te permite profundizar para examinar más a fondo las instalaciones identificadas utilizando las opciones de filtrado y agrupación.
* Te muestra funcionalidades antifraude adicionales a las que solo se puede acceder con una suscripción a Protect360, incluidas: fraude avanzado en tiempo real, fraude posterior a la atribución, fraude en eventos in-app, reglas de validación de eventos in-app y herramientas de análisis de anomalías.

ProtectLITE <Anchor target="_blank" href="/marketers/es/docs/protect360-raw-data-reports">raw data</Anchor>:

* Está disponible en el reporte de instalaciones de Protect360 a través de la página Export Data y Pull API.

<div id="dashboard" />

## Panel de Control

Para ver el dashboard de ProtectLITE, en AppsFlyer ve a **Protect360**.

Las funciones del panel de control se describen en las siguientes secciones.

<div id="filters-and-groupings" />

<Accordion title="Filtros y agrupaciones">

**Ventana de filtros y agrupaciones**

Las siguientes opciones de filtrado y agrupación están disponibles:

* Filtros básicos:
  * Nombre de aplicación
  * Tipo de fuente: No orgánico y/o orgánico
  * Nombre de la app
  * Geografía
  * Rango de fechas (<Anchor target="_blank" href="/marketers/es/docs/about-data-freshness-and-timezone-support#protect360-dashboard">ver soporte de zona horaria</Anchor>)
* Filtros ampliados: haz clic en la flecha azul, a la derecha del selector de fecha:
  * Agencias
  * Canales
  * Tamaño mínimo de cohorte
* Opciones de agrupación: elige entre diferentes dimensiones para agrupar los datos sobre fraude y obtener los insights específicos que necesitas:
  * **Aplicación:** compara la cantidad total de fraude en cada una de tus aplicaciones.
  * **Fuente de medios** (opción predeterminada): compara los casos de fraude manejados por cada una de las fuentes de medios que usan tus aplicaciones.
  * **Fuente de medios + Campaña**: compara los casos de fraude manejados por todas tus campañas en todas las fuentes de medios usadas por tus aplicaciones.
  * **Fuente de medios + ID de sitio**: compara los casos de fraude manejados por todos los publishers (ID de sitio) en todas las fuentes de medios usadas por tus aplicaciones.
  * **Fuente de medios + ID de sitio + Campaña**: compara los casos de fraude manejados por todos los publishers (ID de sitio) en todas las fuentes de medios usadas por tus aplicaciones, asociados con los nombres de campaña pertinentes.
  * **Geolocalización**: compara los casos de fraude manejados de todos los países.
  * **Fuente de medios + Geolocalización** (disponible en el dashboard de eventos in-app): compara los casos de fraude manejados por cada una de las fuentes de medios usadas por tus aplicaciones, asociados con los países pertinentes.

</Accordion>

<div id="installs-headline-metrics" />

<Accordion title="Instalaciones: métricas principales">

Las métricas principales te permiten ver:

* Métricas de ahorro estimado:
* Instalaciones identificadas
* Se sospecha una amenaza de fraude general

Las métricas son relevantes para el periodo de tiempo seleccionado en el filtro de fecha.

Para los KPI de ahorro estimado e instalaciones identificadas, hay un valor porcentual. Este valor muestra la relación del KPI presentado con el rango de fechas paralelo anterior. Por ejemplo, esta semana comparada con la anterior, o cualquier día seleccionado en el rango de fechas comparado con la misma cantidad de días que vinieron antes: si muestra un aumento del X % en el ahorro estimado, significa que el rango de fechas paralelo anterior tuvo un X % menos de instalaciones fraudulentas.

<div id="estimated-savings" />

#### Métricas de ahorro estimado:

[![](https://files.readme.io/f53d6245eb8bb81fb652a05869fe71102ed50ab304d2fc8faf1cc17198794470-360019038197.jpg)](https://files.readme.io/f53d6245eb8bb81fb652a05869fe71102ed50ab304d2fc8faf1cc17198794470-360019038197.jpg)

Métricas de ahorro estimado:

* Muestra el valor del fraude identificado y bloqueado en tiempo real por ProtectLITE y las Reglas de validación, que debes liquidar con las ad network.
* Usa la fórmula: Ahorro estimado = número de instalaciones bloqueadas X eCPI promedio de la aplicación.
* No son relevantes para orgánico tráfico.

Para conocer más detalles sobre cómo se calcula esta cantidad, lee esta <Anchor target="_blank" href="/marketers/es/docs/protect360-anti-fraud-guide#faq">FAQ</Anchor>.

<div id="identified-installs" />

#### Instalaciones identificadas

[![](https://files.readme.io/2bc38a1ee19b4a13c18ed7571d97efd0f855d27142e8a6cd9a761cac276d3bd0-360019090998.jpg)](https://files.readme.io/2bc38a1ee19b4a13c18ed7571d97efd0f855d27142e8a6cd9a761cac276d3bd0-360019090998.jpg)

Las métricas de instalaciones identificadas muestran el número de instalaciones identificadas y bloqueadas en tiempo real por ProtectLITE y las Reglas de validación.

<div id="suspected-overall-fraud-threat" />

#### Se sospecha una amenaza de fraude general

[![](https://files.readme.io/bb6a33cfea1dbff695d46a4b2f6547b756740cf35b750db25097d7ec772cc3d8-360019091058.jpg)](https://files.readme.io/bb6a33cfea1dbff695d46a4b2f6547b756740cf35b750db25097d7ec772cc3d8-360019091058.jpg)

El nivel general de amenaza sospechado:

* Es una estimación del fraude que Protect360 bloquearía si tuvieras una suscripción.
* Te da una buena idea de si deberías pasarte a Protect360 para recibir una protección antifraude más avanzada.

</Accordion>

<div id="installs-chart" />

<Accordion title="Instalaciones: gráfico">

<div id="fraud-trend-over-time-chart" />

#### Gráfico de tendencia del fraude en el tiempo

El gráfico muestra el número de instalaciones por día bloqueadas por ProtectLITE y las Reglas de validación durante el periodo seleccionado en el filtro de fechas.

</Accordion>

<div id="installs-table" />

<Accordion title="Instalaciones: tabla">

<div id="identified-fraud-breakdown" />

#### Desglose de casos de fraude identificados

La tabla muestra el número de instalaciones bloqueadas por ProtectLITE y las Reglas de validación durante el periodo seleccionado en el filtro de fechas.

Haz clic en **Export CSV** para descargar la tabla en tu escritorio en formato CSV.

La tabla se presenta en un formato de vista general, tal como se muestra en la imagen a continuación.

[![plite_fraud_table.jpg](https://files.readme.io/81246675ce8f0e1243e0c0d64e1cf347246bb403894718ad9e23c56fc594eb84-360019038257.jpg)](https://files.readme.io/81246675ce8f0e1243e0c0d64e1cf347246bb403894718ad9e23c56fc594eb84-360019038257.jpg)

La estructura dinámica de la tabla te permite:

* Haz clic en el botón de configuración de la tabla para añadir o quitar columnas de la tabla.  
  Si haces algún cambio, asegúrate de hacer clic en el botón Guardar después para que tus personalizaciones se guarden para futuras visitas.
* Cambia el orden de las columnas arrastrando las secciones de columnas en la configuración de columnas.

[![plite_edit_columns.jpg](https://files.readme.io/52fc1378d4c758d80ed2a89b24f5b7fa949c9ccccae7ff5edf4af307538e805a-360019038297.jpg)](https://files.readme.io/52fc1378d4c758d80ed2a89b24f5b7fa949c9ccccae7ff5edf4af307538e805a-360019038297.jpg)

<div id="content-of-the-identified-fraud-breakdown-table" />

#### Contenido de la tabla de desglose de casos de fraude identificados

| Columna de la tabla | Nota |
| --- | --- |
| Agrupaciones | <ul><li>[Predeterminado] La tabla y el panel de control están agrupados por fuente de medios.</li><li>Al seleccionar una fuente de medios específica, la agrupación se realiza automáticamente por ID del sitio y fuente de medios.</li><li>Los grupos opcionales incluyen campaña, geolocalización, canal, agencia y combinaciones de estos grupos.</li><li>Si seleccionas una agrupación con dimensiones que solo se aplican al tráfico no-orgánico , la tabla muestra N/A para la orgánica fuente de medios.</li></ul> |
| **Instalaciones asistidas** | **Desglose principal de las instalaciones bloqueadas por fraude y reglas de validación** |
| Total (A) | <ul><li>Total de instalaciones = Todas las instalaciones de la app, incluidas las instalaciones fraudulentas y las instalaciones identificadas mediante reglas de validación.</li><li>Las instalaciones regulares están disponibles por fuente de medios (no orgánicas) en el Panel de control de información general.</li></ul> |
| Instalaciones identificadas (B) | <ul><li>Número total de instalaciones identificadas y bloqueadas en tiempo real</li><li>Las instalaciones orgánicas bloqueadas no se muestran en el dashboard. Para ver las instalaciones orgánicas bloqueadas, usa los reportes de raw data.</li><li>[Predeterminado] La tabla está ordenada por este KPI en forma descendente.</li></ul> |
| **% de instalaciones identificadas** (B/A) | Instalaciones identificadas / Total de instalaciones |
| **Identificado tras la atribución (C)** | Requiere Protect360 |
| **Identificado tras la atribución % (C/A)** | Requiere Protect360 |
| **Instalaciones falsas** | **Instalaciones fraudulentas que simulan la actividad real del usuario.** |
| Bloqueo en tiempo real | Instalaciones falsas bloqueadas en tiempo real. |
| Identificados tras la atribución | Requiere Protect360 |
| **Instalaciones secuestradas (Hijacked installs)** | **Últimos clics fraudulentos que roban la atribución de instalaciones reales de usuario.** |
| Bloqueo en tiempo real | Instalaciones secuestradas bloqueadas en tiempo real. |
| Identificados tras la atribución | Requiere Protect360 |
| **Reglas de validación** | **Instalaciones consideradas no válidas debido a las condiciones de las reglas de validación.** |
| Instalaciones bloqueadas | Instalaciones bloqueadas por las reglas de validación. |
| Atribución bloqueada | Instalaciones con la atribución corregida debido a las reglas de validación. |
| **Clics** | **Clics legítimos de la fuente.**<br /><br />Nota: **Nota:** Todos los tipos de atribución deben seleccionarse en la barra de filtros para que los datos de clics se muestren en la tabla (de lo contrario se mostrará como N/A). Asegúrate de ajustar tus selecciones de filtro de igual manera. |
| Total (E) | Número total de clics legítimos recibidos de la fuente. |
| Bloqueos | Clics bloqueados debido a la limitación de clics |
| **ID de transacción de reembolso** | **Impresiones de la fuente.**<br /><br />**Nota:** **Nota:** Todos los tipos de atribución deben seleccionarse en la barra de filtros para que los datos de impresiones se muestren en la tabla (de lo contrario se mostrará como N/A). Asegúrate de ajustar tus selecciones de filtro de igual manera. |
| Total | Número total de impresiones legítimas y fraudulentas recibidas de la fuente |
| Bloqueos | Impresiones bloqueadas debido a fraude (incluidas las limitadas) |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Especificaciones y limitaciones">

| Caducado | Observaciones |
| --- | --- |
| Acceso para anunciantes | Todos los usuarios de la cuenta. |
| Acceso a la red publicitaria | <ul><li>El dashboard de ProtectLITE y el acceso al raw data requieren <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permisos-de-ad-network">permiso del anunciante</Anchor></li><li>El anunciante debe tener la ad network como partner integrado.</li></ul> |
| Acceso a la agencia | El dashboard de ProtectLITE y el acceso al raw data requieren <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permisos-de-ad-network">permiso del anunciante</Anchor> |
| Transparencia de agencia | Agencia transparente: Puede ver fuentes de medios específicas<br /><br />Agencia no transparente: Puede ver fuentes de medios específicas |

</Accordion>

<div data-zendesk-anchors="01JDHEKR6W19WD6HXFFMRNXKFF=protectlite dashboard=panel-de-control 01JDHEKR6YGEKRB23M19F5ZGQ5=panel-de-control 01JDHEKR6YPNDQAK3ATDRDDZTC=filters-and-groupings installs%E2%80%94headline-metrics=installs-headline-metrics 01JDHEKR75TF5RHJTFM91XPYPY=installs-headline-metrics estimated-savings=m%C3%A9tricas-de-ahorro-estimado 01JDHEKR76MMVSJSWFTZS5PRBK=m%C3%A9tricas-de-ahorro-estimado identified-installs=instalaciones-identificadas 01JDHEKR77VGHR1BWQFPYSWW2E=instalaciones-identificadas suspected-overall-fraud-threat=se-sospecha-una-amenaza-de-fraude-general 01JDHEKR78BBFEZS98VG0VTERN=se-sospecha-una-amenaza-de-fraude-general installs%E2%80%94chart=installs-chart 01JDHEKR795RK8KP9BZ0WECQW8=installs-chart fraud-trend-over-time-chart=gr%C3%A1fico-de-tendencia-del-fraude-en-el-tiempo 01JDHEKR79YM7VWE6NH2FJ70NS=gr%C3%A1fico-de-tendencia-del-fraude-en-el-tiempo installs%E2%80%94table=installs-table 01JDHEKR79ZBQVSTT4GA162J94=installs-table identified-fraud-breakdown=desglose-de-casos-de-fraude-identificados 01JDHEKR79H7PQFEJGWAY4RMJC=desglose-de-casos-de-fraude-identificados content-of-the-identified-fraud-breakdown-table=contenido-de-la-tabla-de-desglose-de-casos-de-fraude-identificados 01JDHEKR7BR6ESS9DX03NMHPT0=contenido-de-la-tabla-de-desglose-de-casos-de-fraude-identificados 01JDHEKR9JCAR22V33B7TFZSPV=traits-and-limitations" />
