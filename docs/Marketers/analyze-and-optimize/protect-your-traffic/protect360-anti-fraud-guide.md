---
title: Guía antifraude de Protect360
metadata:
  keywords:
    - Advertisers
    - Protect360
    - protect
    - protect 360
    - '360'
    - p360
    - p 360
    - 360protect
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2016-12-06T07:47:17Z'
  edited_at: '2026-08-12T11:55:10Z'
  id: 218254203
  locale: es
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/es/articles/218254203
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En resumen:** El fraude de atribución agota los presupuestos de marketing, contamina los datos de rendimiento de marketing y puede convertir campañas exitosas en fracasos. **Protect360 ofrece, a los propietarios de las aplicaciones, protección en tiempo real y detección del fraude posterior a la atribución.** Sin embargo, asegúrate de crear plantillas separadas con el subdominio; no agregues manualmente el subdominio al ID de plantilla.

![p360intro2.jpg](https://files.readme.io/c8476382eeff62164ca93b9bf2f3c4cdbe0609d4160047eac36a44d5f333ffdb-360014803578.jpg)

<div id="protect360-overview" />

## Descripción general de Protect360

* Protege contra el fraude de atribución. Consiste en herramientas dinámicas capaces de detectar fraudes y bloquear la atribución fraudulenta.
* Utiliza la escala de AppsFlyer, el aprendizaje de máquina y el análisis de comportamiento, para proporcionar cobertura contra formas conocidas y nuevas de fraude por clics/instalaciones fraudulentas, incluidos bots y anomalías de comportamiento.
* Protege a los marketers del fraude a nivel dispositivo, publisher y fuentes de medios.
* Utiliza un enfoque por capas de bloqueo de fraude en tiempo real e identificación del fraude posterior a la atribución
* No afecta a la experiencia del usuario de la aplicación. En caso de intentos de fraude que involucren a usuarios reales, las instalaciones de la aplicación se completan normalmente y solo se ve afectado el registro de atribución.

<div id="realtime-blocking" />

<Accordion title="Bloqueo en tiempo real">

* En tiempo real, antes de la atribución, la instalación se identifica como procedente de una fuente de medios fraudulenta y se bloquea su atribución.
* Los eventos in-app posteriores, del mismo usuario, se bloquean.
* Las instalaciones bloqueadas y los eventos in-app se reportan en el dashboard de Protect360 y en los reportes de fraude bloqueado.
  * Instalaciones y eventos in-app bloqueados: No se incluyen en la atribución ni los dashboards de AppsFlyer porque nunca se atribuyeron.
* Los postbacks de instalaciones bloqueadas se envían a fuentes de medios, con la razón del bloqueo, lo cual permite optimizarlos.

<Anchor target="_blank" href="/marketers/es/docs/protect360-raw-data-reports">Sobre los eventos bloqueados</Anchor>

</Accordion>

<div id="postattribution-detection" />

<Accordion title="Detección posterior a la atribución">

* El fraude identificado después de la atribución se denomina fraude posterior a la atribución. El fraude posterior a la atribución se puede identificar el día de la instalación y hasta 7 días después (8 días en total).
* Una vez atribuida, una instalación no puede eliminarse. Por esta razón, el fraude posterior a la atribución se maneja de manera diferente al fraude en tiempo real.
* Las instalaciones fraudulentas y los eventos in-app identificados en retrospectiva deben tratarse como fraude real y no se debe cobrar por ellos.

Una vez que una fuente, como una ad network o un ID de sitio, se identifica como fraudulenta:

* Se bloquean los futuros clics provenientes de la fuente.
* Instalaciones anteriores:
  * Desde el inicio del mes actual hasta el presente, se etiquetan como instancias de fraude posterior a la atribución, pero **no se borran de los datos**. A partir de enero de 2020, las facturas de los anunciantes se acreditan por las tarifas de atribución de estas instalaciones.
  * Desde antes del inicio del mes en curso, no se cambian.
* Eventos in-app que ocurren:

  * **Hasta** el etiquetado de la instalación: se etiqueta como fraude.
  * **Después** del etiquetado de la instalación: se etiqueta como fraude.

  Nota: Para la adquisición de usuarios (UA), las reinstalaciones identificadas como fraudulentas, Protect360 corrige la atribución reasignando la instalación a una fuente orgánica. En consecuencia, cualquier evento in-app posterior de estas reinstalaciones se atribuye a orgánico y aparecerá en los reportes de eventos in-app orgánicos.

Ejemplos de fraude posterior a la atribución:

* Instalaciones en apariencia regulares seguidas de señales fraudulentas dentro de eventos in-app
* Se ha descubierto una nueva forma de fraude
* Instalaciones que resultan ser fraudulentas solo después de que los algoritmos de detección de anomalías recopilan suficientes datos estadísticos acerca de las instalaciones de cualquier publisher

</Accordion>

<div id="common-fraud-issues-and-solutions" />

<Accordion title="Problemas y soluciones habituales del fraude">

Cuando AppsFlyer identifica el fraude, se bloquea el **evento** **de atribución** asociado con el fraude. Esto elimina las ganancias y la motivación de los estafadores. **Nota**: La instalación de la aplicación se lleva a cabo y no está bloqueada. Esto significa que el usuario de la aplicación puede usar la aplicación y generar ingresos para el anunciante.

Los clics, las instalaciones y los eventos in-app fraudulentos bloqueados se encuentran en los  <Anchor target="_blank" href="/marketers/es/docs/protect360-raw-data-reports">reportes de raw data sobre fraude de Protect360</Anchor>.

En la tabla a continuación, se describen algunos tipos de fraude y cómo los maneja Protect360.

| Tipo de fraude | Descripción | Solución de AppsFlyer |
| --- | --- | --- |
| <span id="device-id-reset-fraud"></span>**Fraude por reinicio de ID de dispositivo** | El defraudador reinicia constantemente el ID de dispositivo en el mismo dispositivo físico, para generar una gran cantidad de instalaciones. | AppsFlyer identifica las tasas anormales de nuevos dispositivos y, en consecuencia, incluye en la lista de denegación las fuentes que los entregan. |
| <span id="install-hijacking"></span>**Secuestro de instalaciones** | Los defraudadores colocan malwares en dispositivos móviles que alertan cuando se produce una descarga de una aplicación. Al instante, se envía un clic a AppsFlyer para reclamar el crédito por la instalación. | Bloquea los clics atribuidos con un CTIT (<Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/click-to-install-time-ctit/">tiempo del clic a la instalación</Anchor>) muy rápido y según la API del lado del servidor de Google Play. |
| <span id="click-hijacking"></span><Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/click-hijacking/">**Secuestro de clics**</Anchor> | El malware identifica un clic de enlace de atribución de instalación y al instante envía otro clic que le da crédito si se atribuye. | Bloquea los clics atribuidos que suceden con mucha rapidez después de otros clics de la misma aplicación en el mismo dispositivo. |
| <span id="click-flooding"></span><Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/click-flooding/">**Inundación de clics**</Anchor> | Fraude móvil que consiste en el envío de grandes cantidades de clics con el objetivo de lograr el último clic antes de la instalación. | Bloquea los clics atribuidos de ID de sitios con una tasa de conversión baja y un CTIT largo. |
| <span id="behavioral-anomalies"></span>**Anomalías de comportamiento** | Fraude móvil que consiste en la generación de actividad incoherente y anormal posterior a la instalación por parte del defraudador. | Nuestra escala única nos permite rastrear y entender los patrones de comportamiento en cuanto al engagement en varios niveles, como ser por aplicación, región, fuente de medios y anunciante. Los patrones de comportamiento que no son humanos se identifican casi en tiempo real y se bloquean en la fuente. |
| <span id="ip-denylists"></span>**Listas de denegación de IP** | Por lo general, los defraudadores operan desde <Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/click-farms/">granjas de clics</Anchor>, que pueden identificarse mediante sus direcciones IP durante períodos prolongados. | <ul><li>AppsFlyer elabora a diario listas de direcciones IP sospechosas de fraude, a partir de los datos actualizados recibidos de un proveedor externo a nivel mundial, <Anchor target="_blank" href="http://www.digitalelement.com/">Digital Element</Anchor>.</li><li>La protección mediante listas de denegación de IP está activada para todas las aplicaciones.</li></ul> |
| <span id="sdk-authentication"></span>**Autenticación de SDK** | Los defraudadores envían mensajes falsos de SDK para simular acciones valiosas de usuarios. | <ul><li>Se utiliza un protocolo de hashing propio para cifrar los mensajes entre los SDK y los servicios web, evitando que los estafadores imiten los mensajes.</li><li>La protección de la autenticación del SDK está activada para todas las aplicaciones.</li></ul> |
| <span id="store-validations"></span>**Validaciones de la tienda** | Los defraudadores envían mensajes falsos del SDK para simular instalaciones o compras in-app a fin de reclamar cargos elevados de costo por acción (CPA). <Anchor target="_blank" href="/marketers/es/docs/implement-apple-app-store-itunes-install-validation">Validaciones de Apple Store</Anchor>. | Habilita la <Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/install-validation/">validación de instalaciones</Anchor> en iTunes y la validación de compras in-app, tanto para iTunes como para Google Play, en relación con cualquier instalación o compra in-app que haya tenido lugar para impedir la atribución de actividades fraudulentas. |

**Nota**: Los valores exactos de tiempo mencionados anteriormente no se revelan para proteger a nuestros clientes.

Podrás encontrar más explicaciones sobre motivos de bloqueo en el <Anchor target="_blank" href="/marketers/es/docs/protect360-raw-data-reports">artículo de raw data</Anchor>.

</Accordion>

La tabla a continuación describe los diversos tipos de instalaciones y eventos in-app fraudulentos, y lo que sucede cuando el motor Protect360 los bloquea en tiempo real o los detecta después de la atribución.

<table><thead><tr><th>Tipo de fraude</th><th>Tiempo de detección</th><th>Qué sucede con una instalación</th><th>Qué sucede con un evento in-app</th></tr></thead><tbody><tr><td rowspan="2"><span>Instalación falsa</span></td><td><span>En tiempo real</span></td><td><span>Se bloquea en tiempo real</span></td><td><span>Se bloquea en tiempo real</span></td></tr><tr><td><span>Después de la atribución</span></td><td><span>Se marca en el reporte de instalaciones posteriores a la atribución.</span></td><td><ul><li><span>Los eventos in-app que ocurrieron antes de la detección del fraude se marcarán en el reporte de eventos in-app posteriores a la atribución.</span></li><li><span>Después de la detección: se bloquea en tiempo real</span></li></ul></td></tr><tr><td rowspan="2"><span>Secuestro de atribución de instalaciones</span></td><td><span>En tiempo real</span></td><td><ul><li><span>Se bloquea en tiempo real</span></li><li><span>La atribución se corrige a la última fuente válida</span></li></ul></td><td><ul><li><span>No se muestra en los informes sin procesar y solo es visible en el dashboard</span></li><li><span>Se atribuye a la misma fuente válida que la instalación</span></li></ul></td></tr><tr><td><span>Después de la atribución</span></td><td><span>Se marca en el reporte de instalaciones posteriores a la atribución.</span></td><td><ul><li><span>Los eventos in-app que ocurrieron antes de la detección del fraude se marcarán en el reporte de eventos in-app posteriores a la atribución.</span></li><li><p>Después de la detección de fraude: se marca en el reporte de eventos in-app posteriores a la atribución hasta 30 días desde la instalación.\*</p><p>\*Los eventos in-app se corrigen a la última fuente de medios válida durante 30 días desde la instalación. Los eventos que ocurren después de 30 días no se corrigen.</p></li></ul></td></tr><tr><td rowspan="2"><span>Evento in-app fraudulento</span></td><td><span>En tiempo real</span></td><td>-</td><td><span>Se bloquea en tiempo real</span></td></tr><tr><td><span>Después de la atribución</span></td><td>-</td><td><span>Se marca en el reporte de eventos in-app posteriores a la atribución.</span></td></tr></tbody></table>

Detección del fraude de Protect360 y sus resultados

<div id="using-protect360" />

## Uso de Protect360

<div id="dashboard" />

<Accordion title="Panel de Control">

El <Anchor target="_blank" href="/marketers/es/docs/protect360-dashboard">dashboard de Protect360</Anchor> muestra datos agregados de fraude y proporciona insights sobre el tráfico fraudulento.

Vistas del dashboard:

**Instalaciones**: Insights <Anchor target="_blank" href="/marketers/es/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">basados en LTV</Anchor> de instalaciones fraudulentas, bloqueadas en tiempo real e identificadas posteriormente a la atribución. Puedes bajar de nivel para examinar más a fondo los eventos de fraude utilizando las opciones de filtrado y agrupación.

**Eventos in-app**: Insights <Anchor target="_blank" href="/marketers/es/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">basados en actividades</Anchor> de eventos in-app fraudulentos, bloqueados en tiempo real e identificados posteriormente a la atribución. Puedes bajar de nivel para examinar más a fondo los eventos de fraude utilizando las opciones de filtrado y agrupación.

</Accordion>

<div id="raw-data" />

<Accordion title="Datos sin procesar">

El <Anchor target="_blank" href="/marketers/es/docs/protect360-raw-data-reports">raw data</Anchor> sobre el fraude está disponible a través de la Pull API, datos exportados y <Anchor target="_blank" href="/marketers/es/docs/data-locker-for-marketers">Data Locker (una herramienta premium)</Anchor>.

Los reportes de raw data se dividen de la siguiente manera:

* Reportes bloqueados: Instalaciones, clics y eventos in-app de usuarios cuya atribución se bloqueó y no se atribuyó a ninguna fuente de medios.
* Reportes posteriores a la atribución:
  * Instalaciones atribuidas a una fuente de medios, pero que posteriormente se descubrió que eran fraudulentas.
  * Eventos in-app:
    * de las instalaciones identificadas como fraude después de ser atribuidas a una fuentes de medios.
    * juzgados como fraudulentos sin tener en cuenta la propia instalación.

* Los anunciantes utilizan estos reportes para conciliar las cuentas de la ad network, para la optimización y para ajustar los dashboards de atribución para el fraude posterior a la atribución.

</Accordion>

<div id="validation-rules" />

<Accordion title="Reglas de validación">

Las <Anchor target="_blank" href="/marketers/es/docs/implement-validation-rules-to-prevent-fraud">Reglas de validación</Anchor> permiten a los propietarios de aplicaciones configurar condiciones para bloquear ciertas instalaciones, bloquear la atribución (y garantizar que las instalaciones se atribuyan a la fuente de medios válida más reciente) o bloquear eventos in-app.

</Accordion>

<div id="fraud-reconciliation-with-ad-networks" />

<Accordion title="Conciliación del fraude con las ad networks">

Con Protect360, los anunciantes obtienen raw data con respecto a instalaciones y eventos in-app fraudulentos que las ad networks pueden no haber registrado como fraude.

Si descubres que una ad network te ha estado enviando tráfico desde fuentes sospechosas, notifica a la ad network y pídele que deje de enviarte tráfico desde esas fuentes sospechosas. Usa la columna del reporte de instalaciones de raw data llamada **Attributed Touch Time** (hora del toque atribuido) para verificar que no se reciban más instalaciones de la fuente después de tu solicitud para detenerlas.

También puedes usar los datos de Protect360 para conciliar con las ad network y recibir reembolsos totales o parciales por el tráfico anterior proveniente de fuentes sospechosas.

**Para conciliar las campañas basadas en el costo por instalación (CPI) mediante Protect360:**

* Al comienzo de cada mes, comunícate con el gerente de cuenta de cada ad network en la que se haya producido fraude.
* Recopila el raw data relevante de instalaciones fraudulentas a partir de los reportes de instalaciones bloqueadas e [instalaciones posteriores a la atribución](/docs/protect360-anti-fraud-guide#postattribution-detection).
* Comparte el raw data sobre fraude con la red para conciliar y optimizar su tráfico.
* Es posible crear un reporte de raw data que incluya solo las instalaciones válidas, pero excluya las instalaciones fraudulentas posteriores a la atribución. Para hacer esto, necesitas descargar el reporte mensual de ***Instalaciones atribuidas de UA*** y excluir todas las entradas del reporte de ***Instalaciones posteriores a la atribución***.

**Para conciliar las campañas basadas en costo por acción (CPA)/CPE utilizando Protect360:**

* Al comienzo de cada mes, comunícate con el gerente de cuenta de cada ad network en la que se haya producido fraude.
* Recopila el raw data relevante de los eventos in-app fraudulentos a partir de los reportes de eventos in-app bloqueados y eventos in-app [posteriores a la atribución](/docs/protect360-anti-fraud-guide#postattribution-detection).
* Comparte el raw data sobre fraude con la red para conciliar y optimizar su tráfico.
* Es posible crear un reporte de raw data que incluya solo las instalaciones válidas, pero excluya las instalaciones fraudulentas posteriores a la atribución. Para hacer esto, necesitas descargar el reporte mensual de ***Eventos in-app atribuidos de UA*** y excluir todas las entradas del reporte de ***Eventos in-app posteriores a la atribución***.

</Accordion>

<div id="traits-and-limitations" />

## Características y limitaciones

<div id="traits-and-limitations::a07033c3" />

<Accordion title="Características y limitaciones">

| Caducado | Observaciones |
| --- | --- |
| Acceso para anunciantes | Todos los usuarios de la cuenta. |
| Acceso a ad network | <ul><li>El dashboard de Protect360 y el acceso al raw data requieren <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permisos-de-ad-network">permiso del anunciante</Anchor>.</li><li>El anunciante debe tener la ad network como partner integrado.</li></ul> |
| Acceso a la agencia | El dashboard de Protect360 y el acceso al raw data requieren <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permisos-de-ad-network">permiso del anunciante</Anchor>. |
| Transparencia de agencia | Agencia transparente: Puede ver fuentes de medios específicas<br /><br />Agencia no transparente: Puede ver fuentes de medios específicas |
| Zona horaria específica de la aplicación | <ul><li>La zona horaria específica de la aplicación se usa en el dashboard siempre que todas las aplicaciones estén configuradas en la misma zona horaria.</li><li>Si las aplicaciones no están configuradas en la misma zona horaria, entonces el dashboard establece UTC de forma predeterminada.</li></ul> |
| Actualización de los datos | <ul><li><Anchor target="_blank" href="/marketers/es/docs/about-data-freshness-and-timezone-support#eod">Dashboard de Protect360</Anchor> Actualizado <Anchor target="_blank" href="/marketers/es/docs/about-data-freshness-and-timezone-support#eod">diariamente</Anchor>.<br />La hora de actualización más reciente se muestra debajo del filtro de rango de fechas en el dashboard.</li><li>Reportes:<ul><li>Instalaciones y eventos in-app bloqueados: Actualización continua en tiempo casi real.</li><li>Posterior a la atribución: <Anchor target="_blank" href="/marketers/es/docs/about-data-freshness-and-timezone-support#eod">A diario</Anchor> usando UTC.</li></ul></li></ul> |
| Reinstalaciones | Los datos de fraude para reinstalaciones solo están disponibles en raw data. Por lo tanto, puede haber discrepancias entre los números totales en el dashboard y los reportes de raw data. |
| Reorientación | <ul><li>Para las instalaciones identificadas como fraude, se muestra el desglose del tipo de toque atribuido entre instalaciones, reatribuciones y re-engagements.</li><li>Para eventos in-app:<ul><li>El dashboard de eventos in-app (CPA) muestra eventos fraudulentos de instalaciones de UA, pero no de retargeting.</li><li>Los eventos fraudulentos procedentes de reatribuciones que se identifican en tiempo real pueden visualizarse en los reportes de raw data. No se pueden identificar eventos fraudulentos de re-engagements.</li><li>Los eventos fraudulentos de retargeting no se pueden identificar después de la atribución.</li></ul></li></ul> |
| Limitaciones | <ul><li>Tablas limitadas a un máximo de 20.000 filas.</li><li>Si haces una consulta con respecto a un conjunto de datos más grande, es posible que se excluyan algunas fuentes de medios. Para superar esta limitación, recomendamos lo siguiente:<ul><li>Hacer una consulta sobre un conjunto de datos más pequeño: un intervalo de fechas más reducido, aplicaciones y fuentes de medios específicas</li><li>Exportar los <Anchor target="_blank" href="/marketers/es/docs/protect360-raw-data-reports">reportes de raw data</Anchor> de Protect360</li><li>Exportar los reportes agregados de detección avanzada de Protect360 <Anchor target="_blank" href="/marketers/es/docs/pull-api-aggregate-data">mediante la Pull API</Anchor></li></ul></li></ul> |

Características y limitaciones

</Accordion>

<div id="faq-and-tips" />

## Preguntas frecuentes y consejos

<div id="faq" />

<Accordion title="Preguntas frecuentes">

| **¿Protect360 funciona contra el fraude proveniente de enlaces de atribución personalizados?**<br /><br />¡Definitivamente! ¡Definitivamente! Protect360 detecta y bloquea el fraude proveniente de enlaces de atribución personalizados, además de las ad networks. Eso significa que también estás protegido si tienes campañas de medios propios, como influencers, campañas de correo electrónico y SMS, banners de sitios web y páginas de inicio, publicaciones virales en las redes sociales, push notifications o incluso QR codes. |
| --- |
| **¿Qué hay de nuevo en Protect360 V2 en comparación con la V1?**<ol><li>Hay 3 cambios principales en P360 V2.0:<br />Fraude posterior a la atribución: dondequiera que presentemos instalaciones bloqueadas, también mostramos instalaciones de fraude posterior a la atribución. Los datos posteriores a la atribución también están disponibles en forma de reporte de raw data.</li><li>Insights sobre anomalías: se agregó una nueva sección, llamada “Insights sobre anomalías”, en la que los anunciantes pueden analizar anomalías mediante herramientas de visualización. Esta sección reemplaza las 2 gráficas de la anterior pestaña “Detección avanzada”.</li><li>Centralización de todos los datos sobre fraude: eliminamos la pestaña “Detección avanzada” y, en su lugar, presentamos toda la información en una pestaña.</li></ol> |
| **¿Por qué los raw data posteriores a la atribución no están disponibles en la página Datos Exportados?**<br /><br />Los reportes con datos posteriores a la atribución se encuentran a nivel de cuenta por fuente de medios a fin de facilitar el proceso de conciliación. La página **Datos exportados** se encuentra a nivel de aplicación individual y aún contiene los datos sobre bloqueo de fraude a nivel de aplicación para asegurar la compatibilidad con versiones anteriores. |
| **¿Los datos posteriores a la atribución se actualizan de manera retroactiva?**<ul><li>**Instalaciones**: los datos sobre instalaciones que se encuentran en la página de información general y en todos los demás reportes fuera del dashboard de Protect360 no se actualizan de manera retroactiva.</li><li>**Eventos in-app**: una vez que la capa de protección posterior a la atribución identifica una instalación como falsa, se bloquean los siguientes eventos in-app procedentes de esta instalación. Los eventos in-app anteriores no se actualizan retroactivamente.</li></ul> |
| **¿Por qué los datos se ven diferentes al seleccionar redes específicas/diferentes en los insights de anomalías?**<br /><br />Cuando observas las anomalías de CTIT y seleccionas AF\_Baseline como benchmark, es posible que veas las anomalías de la Red A. Luego, si, por ejemplo, seleccionas la Red A como benchmark, verás las anomalías de otras redes, pero no la Red A.<br /><br />Este resultado en realidad es lo que deberías esperar. Cuando se utiliza el benchmark confiable de AppsFlyer, se muestran las redes con tasas anormales de CTIT. Cuando la red anómala se utiliza como benchmark, sus instalaciones ya no se incluyen como anomalías, pero las instalaciones de otras redes pueden considerarse anómalas en relación con ella. |
| **¿El tráfico orgánico anormal es realmente fraudulento?**<br /><br />Es posible que los picos anormales en el tráfico orgánico sean realmente fraudulentos. En general, si ves tráfico orgánico en AppsFlyer, que tienes razones para creer que es realmente fraudulento, podría ser uno de los 3 casos siguientes:<ul><li>**Fraude de atribución fallida:** Los clics del defraudador no pudieron recibir la atribución, por ejemplo, inundación de clics y el último clic se llevó a cabo más allá de la ventana retrospectiva por clics.</li><li>**Fraude no atribuido:** El usuario lleva a cabo un fraude que no está relacionado con la atribución, por ejemplo, el uso del fraude para recolectar elementos en juegos de estrategia.</li><li>**Problemas de integración del SDK:** Comprueba que los eventos in-app se envíen correctamente, es decir, en el momento correcto del flujo y con los valores correctos de los parámetros del evento.</li></ul> |

Preguntas frecuentes

</Accordion>

<div id="benchmarks-and-tips" />

<Accordion title="Benchmarks y consejos">

| **Cómo detectar el fraude de nuevos dispositivos**<br /><br />Los defraudadores pueden enmascarar sus dispositivos restableciendo con frecuencia los IDs principales de sus dispositivos, es decir, el IDFA para iOS y el GAID para Android.<br /><br />Por suerte, AppsFlyer identifica más del 98% de los dispositivos móviles en todo el mundo.<br /><br />Por lo tanto, un alto porcentaje de dispositivos nuevos desconocidos es un buen indicio de fraude por parte de granjas de clics, a menos que se apunte a dispositivos nuevos a propósito.<br /><br />**Cómo detectar nuevos dispositivos:**<ol><li>En Protect360, ve a la tabla de ***desglose de casos de fraude identificados***.</li><li>Desplázate a la derecha hasta las columnas ***Indicadores de la granja de dispositivos: nuevos dispositivos***.</li><li>Haz clic en el nombre de la columna ***% de instalaciones*** para ordenar la tabla en orden descendente para la proporción de nuevos dispositivos.</li><li>Indicadores de fraude de nuevos dispositivos:</li></ol><ul><li>Fuentes con un alto porcentaje de **nuevos** dispositivos. **Nota**: A medida que aumenta la cantidad de instalaciones, también se pueden considerar porcentajes más bajos como fraude, ya que el monto total es grande.<ul><li>Cuando se compara la proporción de usuarios leales de la fuente con la proporción general de usuarios leales, un porcentaje relativamente bajo es un fuerte indicio de fraude.</li></ul></li></ul>**Nota**: Las campañas de <Anchor target="_blank" href="/marketers/es/docs/appsflyer-factory-preinstall-using-manifest-android">aplicaciones preinstaladas</Anchor> por lo general tienen tasas extremadamente altas de dispositivos nuevos, ya que pueden encontrarse entre las primeras aplicaciones que inician los usuarios cuando activan sus nuevos dispositivos. Por lo tanto, en el caso de las aplicaciones preinstaladas, el fraude con dispositivos nuevos es poco probable, incluso cuando se observan tasas elevadas de dispositivos nuevos. |
| --- |
| **Detección del fraude LAT**<br /><br />Los usuarios con LAT (Limit Ad Tracking) optan por no exponer el ID, IDFA o GAID de sus dispositivos a los anunciantes. Aproximadamente el 15% de los usuarios de iOS y el 10% de los usuarios de Android eligen esta opción.<br /><br />De manera similar a la clasificación de dispositivos nuevos, los usuarios de LAT pueden ser legítimos. Sin embargo, un alto porcentaje de ellos podría ser un indicio de actividad fraudulenta.<br /><br />**Detección del LAT:**<ol><li>En Protect360, ve a la tabla de ***desglose de casos de fraude identificados***.</li><li>Desplázate a la derecha hasta las columnas ***Indicadores de la granja de dispositivos: dispositivos LAT***.</li><li>Haz clic en el nombre de la columna ***% de instalaciones*** para ordenar la tabla en orden descendente para la proporción de dispositivos nuevos.</li><li>Indicadores de fraude de dispositivos de LAT:</li></ol><ul><li>Fuentes con un alto porcentaje de dispositivos **LAT**. **Nota**: A medida que aumenta la cantidad de instalaciones, también se pueden considerar porcentajes más bajos como fraude, ya que el monto total es grande.</li><li>Cuando se compara la proporción de usuarios leales de la fuente con la proporción general de usuarios leales, un porcentaje relativamente bajo es un fuerte indicio de fraude.</li></ul> |
| **Detección del fraude por inundación de clics**<ol><li>Mediante la inundación de clics, los defraudadores envían millones de clics con ID de dispositivos reales, con la esperanza de quedar registrados como los últimos clics de usuarios reales. Las fuentes con este tipo de fraude tienen **tasas de conversión muy bajas, pero usuarios de alta calidad**, dado que se trata de usuarios reales.</li></ol>**Detección de casos de inundación de clics:**<ol><li>En Protect360, ve a la tabla de ***desglose de casos de fraude identificados***.</li><li>Desplázate a la derecha hasta las columnas *Indicadores de inundación de clics*.</li><li>Haz clic en el nombre de la columna ***Tasa de conversión*** para organizar la tabla en orden ascendente de tasa de conversión.</li><li>Benchmarks del fraude por inundación de clics:</li></ol><ul><li>Las tasas de conversión normales de ***Conversion Rates*** están entre 0.5% y 35%.<br />Desconfía de las fuentes cuyos índices de conversión son anormalmente bajos, o que **tienen un 25% o menos de la tasa de conversión promedio** de la aplicación. Puedes encontrar este KPI en la tabla del reporte de rendimiento agregado, en la página de información general del dashboard.</li><li>En el caso de las fuentes que se encuentran en el límite, compara el ***% de asistencias*** con la proporción promedio de asistencias. Puedes ver la proporción normal de asistencias en el widget de asistencias, que se encuentra en la página de información general del dashboard.<br />Las fuentes cuya proporción de asistencias sea un **50% mayor que la proporción promedio** de asistencias de la aplicación se consideran sospechosas.<br />Ten en cuenta que cuantas más fuentes use una aplicación, mayores serán sus tasas de contribución.</li></ul> |
| **Cómo detectar casos de inundación de clics con indicadores de CTIT**<br /><br />Otra indicación de inundación de clics es la **distribución uniforme del CTIT**.<br />Por lo general, alrededor del 70% de las instalaciones normales tienen lugar en el plazo de 1 hora a partir del engagement de un anuncio.<br />En el caso de una inundación de clics, no hay ninguna conexión entre el falso engagement y la instalación real. Esto tiene como resultado mucho más que el 30% de las instalaciones fraudulentas, que tienen un CTIT de más de 1 hora.<br /><br />**Detección de casos de inundación de clics con el CTIT como indicador:**<ol><li>En Protect360, ve a la tabla de ***desglose de casos de fraude identificados***.</li><li>Desplázate a la derecha hasta las columnas ***Indicadores de inundación de clics***: ***CTIT***.</li><li>Benchmarks del CTIT con respecto al fraude por inundación de clics:</li></ol><ul><li>Normalmente, los valores de ***más de 60 minutos*** deberían ser del 30% aproximadamente. Sospecha de las fuentes que tengan más del 50% con esta métrica.</li><li>Normalmente, los valores de ***más de 5 horas*** deberían ser del 20% aproximadamente. Sospecha de las fuentes que tengan más del 40% con esta métrica.</li></ul>Usa la <Anchor target="_blank" href="/marketers/es/docs/protect360-dashboard#anomalies-dashboard">página</Anchor> ***Insights de anomalías*** para investigar las fuentes con un CTIT sospechoso. |

Benchmarks y consejos

</Accordion>

<div id="advanced-antifraud-tips" />

<Accordion title="Consejos antifraude avanzados">

| **Número de instalaciones**<br /><br />Cuando filtres por cantidad de instalaciones por cada fuente verificada, es importante detectar las fuentes con mayor cantidad de casos de fraude. Además, puede que una cantidad menor de instalaciones no sea matemáticamente significativa. Nota:<br /><br />**Nota**: Las fuentes con menos de 30 instalaciones, o incluso 50, no son lo suficientemente significativas para sacar conclusiones. Amplía el intervalo de fechas u otros criterios de búsqueda para obtener resultados más significativos. |
| --- |
| **Cambiar la definición de usuario leal**<br /><br />La definición predeterminada de usuario fiel consiste en 3 o más aperturas de la aplicación. Se trata de un KPI importante para el engagement de usuarios, pero desafortunadamente, muchos defraudadores lo conocen y lo usan para falsificar tasas elevadas de usuarios fieles y, de ese modo, evitar sospechas. Para evitar que te engañen, crea y selecciona una definición mejor y más elaborada de usuario fiel.<br /><br />Analiza los KPIs de la calidad de los usuarios de tu aplicación como el registro, la finalización de tutoriales, las compras, las sesiones múltiples, etc. Dentro del código de la aplicación, envía un nuevo evento in-app de usuario fiel si un usuario completa TODA la lista de **KPIs**.<br /><br />Después de enviar el primer evento no orgánico de **usuario fiel**, ve a **Configuración de la aplicación** y selecciónalo para indicar los usuarios fieles de tu aplicación. Es probable que las tasas generales de usuarios fieles presenten un descenso leve y, a continuación, una caída drástica en el caso de las fuentes fraudulentas. |

Consejos antifraude avanzados

</Accordion>

<div id="tip" />

> 👍 **Consejo**
>
> ¿Quieres entender más sobre la protección contra el fraude? Consulta este curso breve e informativo en el <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7809/play/18635/mobile-app-fraud-and-protect360">Portal de Aprendizaje de AppsFlyer</Anchor>.

<div id="see-also" />

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/protect360-raw-data-reports">Datos sin procesar</Anchor>
> * <Anchor target="_blank" href="https://www.appsflyer.com/resources/others/marketers-guide-mobile-ad-fraud/">Guía introductoria al fraude de anuncios móviles para marketers</Anchor>

<div data-zendesk-anchors="protect360-overview=descripci%C3%B3n-general-de-protect360 h_01HE7RSPPQ4T5J3W038EZRCTCE=descripci%C3%B3n-general-de-protect360 h_01HE7RSPPQ5BH7HBK0R8SY1T16=realtime-blocking h_01HE7RSPPRW4CQ3GB9ZEYAA6YN=postattribution-detection h_01HE7RSPPRYMQKJH46JET2ZZ0T=common-fraud-issues-and-solutions using-protect360=uso-de-protect360 h_01HE7RSPPR8Y8J1VJJXXDCAZE6=uso-de-protect360 h_01HE7RSPPR04G3SCSYHSWJKQDG=dashboard h_01HE7RSPPRS6PSTZCR5RT4A5ND=raw-data h_01HE7RSPPR8C9MHRAGJXYD2VVZ=validation-rules h_01HE7RSPPR1PQ2R6NJPRQGS1K1=fraud-reconciliation-with-ad-networks traits-and-limitations=caracter%C3%ADsticas-y-limitaciones h_01HE7RSPPRV797PS12NFQHX1X5=caracter%C3%ADsticas-y-limitaciones h_01HE7RSPPRWRKR1Y25PZV2RMVV=traits-and-limitations::a07033c3 faq-and-tips=preguntas-frecuentes-y-consejos h_01HE7RSPPSV2TT8SMK8JZXFKMC=preguntas-frecuentes-y-consejos h_01HE7RSPPS01J796008HDS1CRW=faq h_01HE7RSPPS018W98JWZGED54W8=benchmarks-and-tips h_01HE7RSPPSEDZWRH929DBSWEWM=advanced-antifraud-tips h_01HE7RSPPSY161MSQVQW7M767F=consejo h_01HE7RX6167Q5QP5JNZDSXCCK5=consulta-tambi%C3%A9n" />
