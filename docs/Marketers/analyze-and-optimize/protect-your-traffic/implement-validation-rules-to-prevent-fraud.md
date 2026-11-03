---
title: Implementa reglas de validación para evitar el fraude
metadata:
  keywords:
    - Advertisers
    - validation rule
    - Marketers
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2017-09-14T14:43:46Z'
  edited_at: '2026-11-02T01:04:24Z'
  id: 115004703926
  locale: es
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/es/articles/115004703926
---
> **At a glance:** Las reglas de validación añaden una capa personalizada de protección contra campañas mal segmentadas y el fraude. Las reglas permiten a los propietarios de apps controlar qué atribuciones de instalaciones y eventos in-app se bloquean o se atribuyen a la última fuente válida.

![5906_animation-750x330__1_.gif](https://files.readme.io/2a5fbee83bdbc342c744f8079b743f06cb3205697bd9caa183593c411ae03d08-360014483338.gif)

## Descripción general

* Las reglas de validación se definen en el creador de reglas mediante condiciones y lógicas personalizadas que filtran y seleccionan qué instalaciones de aplicaciones o eventos in-app conservar o bloquear.
* Las reglas se basan en una variedad de parámetros para múltiples casos de uso, que incluyen:
  * Instalaciones no dirigidas para tu campaña (versión de SO, geolocalización incorrecta, etc.)
  * Instalaciones que no cumplen con el orden de inserción firmado con la ad network
  * Instalaciones secuestradas por ad networks
  * Instalaciones falsas o eventos in-app enviados desde bots, emuladores o granjas de dispositivos
* Las reglas definidas para eventos in-app solo tienen efecto en los eventos in-app asociados con instalaciones que no se bloquearon previamente.
* Las reglas que incluyen una ad network son visibles para el personal de esa ad network (pero no pueden ver otras ad networks incluidas en la regla). Esto es en interés de la transparencia y para ayudar a las ad networks a comprender mejor el rendimiento del tráfico que proporcionan.
* Las reglas se ejecutan en tiempo real y entran en acción inmediatamente. Obtén más información en la sección de [resultados](/docs/implement-validation-rules-to-prevent-fraud#outcomes).
* El modo Tagged te permite probar reglas de validación con tráfico en vivo antes de bloquear la atribución. Cuando una regla se configura como Tagged, AppsFlyer marca las instalaciones y los eventos in-app que coinciden para reportes y análisis, pero la atribución no se ve afectada. Utiliza el modo Tagged para supervisar el comportamiento de la regla, identificar posibles falsos positivos y confirmar el impacto de la regla antes de cambiar su estado a Implemented. Consulta más información en [modo Tagged de VR](/docs/implement-validation-rules-to-prevent-fraud#view-validation-rule-impact).
* Hay opciones adicionales de reglas de validación disponibles para los clientes de <Anchor target="_blank" href="/marketers/es/docs/protect360-anti-fraud-guide">Protect360</Anchor>, además del bloqueo y detección del fraude automáticos de Protect360. Estas condiciones son conocidas por ayudar en la detección de diversos tipos de fraude de instalaciones, instalaciones falsas y eventos in-app falsos.  
  **Nota**: Las reglas de validación solo validan instalaciones/eventos in-app que Protect360 no identificó como fraude.

<Accordion title="Resultados">

* For installs: Validation rules, depending on the selected action, either block the attribution and correct to the last valid media source, or block the attribution completely.
* Para eventos in-app: las reglas de validación bloquean la atribución del evento in-app.
* Consulta la siguiente tabla que muestra los resultados del tipo de bloqueo de la regla de validación.

<table><thead><tr><th> </th><th>Tipo de bloqueo</th><th>Description</th><th>Dónde se pueden ver los datos de instalación</th><th>Eventos in-app que siguen</th></tr></thead><tbody><tr><td rowspan="2"><strong>Instalaciones</strong></td><td>Bloquear la atribución y corregirla a la última fuente de medios válida.</td><td><ul><li><span>Se selecciona cuando consideras que la instalación es real, pero tus condiciones determinan qué fuentes deben o no recibir atribución.</span></li><li><span>La atribución se corrige y la instalación se atribuye a la última fuente de medios válida.</span></li><li><span>Si no se identifica una fuente de medios válida, la instalación se marca como orgánica.</span></li></ul></td><td><ul><li>En los dashboard de AppsFlyer y los reportes de raw data como una instalación normal (atribuida a la última fuente de medios válida)</li><li>Con el plan Protect360 Premium::<ul><li><a href="./protect360-dashboard#panel-de-control-de-instalaciones" target="_blank">Dashboard de instalaciones de Protect360</a></li><li>Reporte de raw data de instalaciones de Protect360 (<span>con la fuente de medios bloqueada)</span> </li></ul></li><li>Sin el plan Protect360 Premium:<ul><li>Reporte de raw data de instalaciones de Protect360 (<span>con la fuente de medios bloqueada)</span> </li></ul></li></ul></td><td><ul><li>Tiene la misma atribución corregida que la instalación</li><li>Datos disponibles con el plan Protect360 Premium:<ul><li>Con atribución corregida en los dashboards y reportes de AppsFlyer como un IAE normal</li><li>Con la fuente de medios bloqueada en el dashboard de IAE de Protect360 y en el reporte de raw data de IAE bloqueados de Protect360</li></ul></li></ul></td></tr><tr><td>Marcar las instalaciones como no válidas y no atribuirlas</td><td><ul><li><span>Se selecciona cuando las instalaciones que son inválidas en función de las condiciones de la regla se consideran falsas.</span></li><li><span>La instalación no se atribuye en absoluto (ni como no orgánica ni orgánica)</span></li></ul></td><td><ul><li>Con el plan Protect360 Premium::<ul><li><a href="./protect360-dashboard#panel-de-control-de-instalaciones" target="_blank">Dashboard de instalaciones de Protect360</a></li><li>Reporte de raw data de instalaciones de Protect360 (<span>con la fuente de medios bloqueada)</span> </li></ul></li><li>Sin el plan Protect360 Premium:<ul><li>Reporte de raw data de instalaciones de Protect360 (<span>con la fuente de medios bloqueada)</span> </li></ul></li></ul></td><td><ul><li><span>Bloqueada</span></li><li><span>Datos disponibles con el plan Protect360 Premium en el dashboard de eventos in-app de Protect360 y en el reporte de raw data de eventos in-app bloqueados.</span></li></ul></td></tr><tr><td rowspan="2"><strong>Eventos dentro de la app</strong></td><td>Bloquear atribución </td><td><ul><li><span>Se selecciona cuando los eventos in-app que no son válidos según las condiciones de la regla se consideran falsos.</span></li></ul></td><td><ul><li> <span>Con el plan Protect360 Premium::</span><ul><li><a href="./protect360-dashboard#panel-de-control-de-eventos-in-app" target="_blank">Dashboard de IAE de Protect360</a></li><li>Reporte de raw data de eventos in-app de Protect360</li></ul></li><li>Sin el plan Protect360 Premium: N/D</li></ul></td><td><ul><li> <span>Datos disponibles con el plan Protect360 Premium en Protect360 </span><a href="./protect360-dashboard#panel-de-control-de-eventos-in-app" target="_blank"><span>dashboard de IAE</span></a><span> y en el reporte de raw data de eventos in-app bloqueados</span> </li></ul></td></tr><tr><td>Eliminar de AppsFlyer por completo</td><td><ul><li><span>Recomendado cuando existen eventos in-app para los que no necesitas ningún dato.</span></li><li><span>AppsFlyer no registra estos eventos en absoluto. </span></li></ul></td><td><span></span></td><td><span></span></td></tr></tbody></table>

* Las ad networks y las agencias solo pueden ver los datos si el anunciante les otorga los <Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-overview#protect360-fraud-and-validation-rules">permisos necesarios</Anchor>.
* Cuando la atribución de una instalación se bloquea o se atribuye a una fuente de medios válida en tiempo real, se envía inmediatamente un postback rechazado a la ad network bloqueada para agilizar tu proceso de conciliación. Cuando la atribución se bloquea y se corrige a la última fuente de medios válida, también se envía un postback a la última ad network válida.
* Cuando se bloquea la atribución de un evento in-app, se envía instantáneamente un postback de rechazo a la ad network bloqueada.  
  **Nota**:
  * Un postback solo se envía si la red de publicidad configurada para recibirlo está integrada con AppsFlyer para recibir postbacks.
  * Los reportes de postbacks y postbacks rechazados están disponibles en la página de exportación.
  * Saber más sobre <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">postbacks</Anchor> y <Anchor target="_blank" href="/partners/es/docs/rejected-attribution-postbacks-to-integrated-partners">postbacks rechazados</Anchor>.
* El bloqueo de atribución de instalaciones e IAE solo afecta cómo y dónde se reportan los datos en AppsFlyer. No impiden el uso de la aplicación por parte de tus usuarios finales.
  * Si es necesario, puedes usar los <Anchor target="_blank" href="/marketers/es/docs/protect360-raw-data-reports">reportes de raw data de instalaciones bloqueadas y de IAE bloqueados</Anchor> (disponibles a través de exportación, Pull API y Data Locker) para obtener la lista de usuarios de la app que se deben deshabilitar.
* Los reportes de instalaciones/IAE bloqueados y los postbacks rechazados contienen el nombre de las reglas que bloquearon las instalaciones/IAE en el campo de motivo del bloqueo. Consulta la sección [reglas múltiples](/docs/implement-validation-rules-to-prevent-fraud#multiple-rules) si hay más de una regla.
  * Cuando las instalaciones/eventos in-app son bloqueados por el motor antifraude de Protect360, incluso si también existe una regla de validación, se muestran los motivos de Protect360.
* Las reglas pueden dar lugar a discrepancias en los reportes entre AppsFlyer y las SRN, como <Anchor target="_blank" href="/marketers/es/docs/meta-ads-discrepancies">Meta ads</Anchor> y <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-faq-and-discrepancies">Google Adwords</Anchor> as they deploy their own logic to validate installs.

</Accordion>

<Accordion title="Múltiples reglas">

* Varias reglas de validación pueden ejecutarse sobre la misma instalación/IAE. Esto ocurre cuando la instalación cumple las condiciones de varias reglas.
* La instalación/IAE se clasifica como no válida cuando no cumple las condiciones de cualquiera de las reglas por separado.
* En los reportes de raw data y los postbacks rechazados, el campo **block reason value** contiene los nombres de todas las reglas que clasifican la instalación o el evento in-app como no válidos.
* Varias reglas para la misma instalación se ejecutan en el siguiente orden, según los tipos de bloqueo de las reglas:

| Tipos de regla/bloqueo | Orden |
| --- | --- |
| Bloquear instalaciones | Aleatorio |
| Bloquear atribución | Aleatorio |
| Bloquear evento in-app | Aleatorio |
| Eliminar de AppsFlyer por completo y de cualquier otra cosa | Eliminado de AppsFlyer. Las demás reglas se ignoran. |
| Bloquear instalaciones y bloquear atribución | <ol><li>Bloquear reglas de instalación (en orden aleatorio)</li><li>Bloquear reglas de atribución (en orden aleatorio)</li></ol> |
| Bloquear instalaciones y bloquear atribución con el motor Protect360 y las reglas de validación | <ol><li>Bloquear instalaciones mediante el motor Protect360</li><li>Bloquear instalación mediante reglas de validación</li><li>Bloquear atribución desde el motor Protect360</li><li>Bloquear atribución mediante reglas de validación</li></ol> |
| Bloquear eventos in-app con el motor Protect360 y las reglas de validación | <ol><li>Bloquear IAE mediante el motor Protect360</li><li>Bloquear eventos in-app desde reglas de validación</li></ol> |

</Accordion>

## Creador de reglas

La interfaz de usuario del generador de reglas está diseñada para crear reglas de forma interactiva. **¡Consejo!** Familiarízate y experimenta con el generador de reglas antes de revisar este artículo en detalle.

### Usa dimensiones clasificadas por categorías

Al añadir condiciones de regla, los parámetros se agrupan en categorías para facilitar la configuración de las reglas. Las categorías y los parámetros se muestran en función del tipo de evento seleccionado y de los permisos de tu cuenta.

Puedes buscar en todas las categorías a la vez. Las categorías coincidentes se expanden automáticamente.

Los parámetros que no son relevantes para el tipo de evento seleccionado o que no están incluidos en tus permisos se ocultan.

| Categoría | Parámetros |
| --- | --- |
| Campaña & fuente | Fuente de medios, campaña, ID de campaña, ID del sitio, nombre del conjunto de anuncios, ID del conjunto de anuncios, ID del anuncio, AF Sub 1-5 |
| Geografía & dispositivo | Geolocalización, plataforma, versión del SO, modelo del dispositivo, operador, agente de usuario |
| Atribución | CTIT, días de lookback, horas de lookback, tipo de toque de atribución |
| Identidad | ID de usuario del cliente, IDFA, ID del anunciante, dirección IP |
| Aplicación & SDK | Versión de la aplicación, versión del SDK, instalador/tienda, instalador/tienda personalizado, está preinstalada, es un deep link |
| Evento de usuario final | Nombre del evento, valor del evento, tiempo entre la instalación y el evento, fuente del evento, moneda, ingresos |
| Engagements | Participación |

![New Validation Rule page.jpg](https://files.readme.io/23875c647c24226c09f5aa2f4dbb85264f95b09e867a053ee55bc2d3ebbc9895-21855980276753.png)

El generador de reglas contiene las siguientes secciones:

| Sección. | Comentarios |
| --- | --- |
| Información general | <ul><li>**Nombre de la regla -** Introduce un nombre para la nueva regla.</li><li>**Tipo de regla -** selecciona el tipo de regla, **tiempo real** o **posterior a la atribución**.</li><li>**Eventos**: selecciona el tipo de evento al que se aplica la regla, **Instalaciones** o **Eventos in-app**.</li><li>**Selección de aplicaciones:** selecciona **Aplicaciones seleccionadas** o **Todas las aplicaciones.**<ul><li>Si se selecciona **Aplicaciones seleccionadas**:<br />**Seleccionar aplicaciones -** selecciona las aplicaciones a las que se aplica la regla: una sola aplicación, varias aplicaciones o todas las aplicaciones de la cuenta.</li><li>Si se selecciona **Todas las aplicaciones**:<br />Opción para marcar **Incluir aplicaciones futuras -** Esto permite incluir aplicaciones futuras en esta regla.</li></ul></li></ul>Las selecciones afectan a las opciones disponibles en las siguientes secciones (agencia, fuente de medios, campaña, etc.)<br /><br /><br /><br />**Nota**<br />La versión de la app solo debe contener números. Por ejemplo, 2.2.1<br /><br />Note:<br /><br />Las versiones numéricas de la app (por ejemplo, 2.2.1) admiten todos los operadores (igual a, mayor que, menor que, etc.).<br /><br />Si la versión de la app es un texto personalizado (por ejemplo, version123 u our\_latest\_version), solo funcionan los operadores "igual a" y "distinto de"; los operadores "mayor que" y "menor que" no se aplican. |
| Fuentes de tráfico | Fuente de tráfico a la que se aplica la regla. [Consulta también las fuentes de Protect360](/docs/implement-validation-rules-to-prevent-fraud#protect360-install-and-inapp-event-sources) |
| CONDICIONES | Elige si quieres bloquear instalaciones/eventos in-app que «Coincidan» o «No coincidan» con las condiciones definidas.<ul><li>**Coincidencia de condiciones -** La atribución se bloqueará para las instalaciones/eventos in-app que coincidan con las condiciones definidas, y la acción que selecciones a continuación se aplicará a todos ellos.</li><li>**No coincidencia de condiciones -** La atribución se bloqueará para las instalaciones/eventos in-app que no coincidan con las siguientes condiciones, y la acción que selecciones a continuación se aplicará a todos los demás.</li></ul>Consulta también las condiciones de Protect360 para [instalaciones](/docs/implement-validation-rules-to-prevent-fraud#protect360-install-conditions) y [eventos in-app](/docs/implement-validation-rules-to-prevent-fraud#protect360-inapp-event-conditions). |
| Acciones | Para las instalaciones, selecciona qué hacer con las instalaciones que cumplen las condiciones especificadas:<ul><li>**Marca las instalaciones como inválidas y no las atribuyas**. Las instalaciones no aparecerán en los dashboards de AppsFlyer, excepto en Protect360 y en los reportes.</li><li>**Bloquea la atribución y corrígela a la última fuente de medios válida**. Si no se identifica una fuente de medios válida, la instalación se considera orgánica.</li></ul>Para los eventos in-app, selecciona qué hacer con los eventos que cumplen las condiciones especificadas:<ul><li>**Bloquea la atribución, pero muéstrala en los datos de Protect360**. Los eventos no se atribuyen, pero se muestran en el dashboard de Protect360 y en el raw data.</li><li>**Eliminar de AppsFlyer**. Los eventos no se mostrarán en absoluto en la plataforma de AppsFlyer.</li></ul>Consulta [Resultados](/docs/implement-validation-rules-to-prevent-fraud#outcomes) para obtener más información. |

## Ejemplos de reglas de validación

<Accordion title="Fuentes de instalación">

La sección **Fuentes** es donde defines las fuentes de tráfico de las instalaciones a las que se aplica la regla.

Existen tres opciones principales:

* **Todo el tráfico:** incluye instalaciones orgánicas y no orgánicas. La información de la fuente no está disponible para las instalaciones orgánicas. Esta opción incluye todas las fuentes de medios, incluidas las que se añadirán en el futuro.  
  *Ejemplo*: aplica una regla a todo el tráfico con una versión de la aplicación inferior a X.
* **Todo el tráfico no orgánico:** se aplica a todas las fuentes de tráfico no orgánico de agencias y no agencias, incluidas las nuevas fuentes que se añadan posteriormente.  
  *Ejemplo*: bloquea el tráfico no orgánico de una geolocalización específica donde no ejecutas campañas de UA o retargeting.
* **Tráfico no orgánico seleccionado:** aplica la regla únicamente a agencias o fuentes de medios específicas. Debes seleccionar o añadir manualmente las fuentes de medios al editar la regla.  
  *Ejemplo*: bloquea las instalaciones de una fuente de medios específica si el CTIT es superior a X días.

Hay opciones adicionales de fuentes disponibles para los clientes de Protect360 para [instalaciones](/docs/implement-validation-rules-to-prevent-fraud#protect360-install-and-inapp-event-sources) y [eventos in-app](/docs/implement-validation-rules-to-prevent-fraud#protect360-inapp-event-conditions).

<table><thead><tr><th>Campo</th><th>Operador</th><th>Valor</th><th>Comentarios</th></tr></thead><tbody><tr><td>Agency</td><td><ul><li>En</li></ul></td><td><ul><li>Tráfico de agencia y no agencia</li><li>Tráfico de no agencias</li><li>Agencias transparentes (menú)</li></ul></td><td><p><span>Agencias transparentes:</span></p><ul><li>Estas son agencias que especifican sus fuentes de medios.</li><li>Las agencias que son transparentes solo para algunas de las apps seleccionadas aparecen en el menú de agencias no transparentes.</li><li>Todas las agencias deben compartir sus fuentes de medios.&lt;/li&gt;&lt;li&gt;Las agencias que comparten fuentes de medios solo para algunas de las apps seleccionadas aparecen en el menú de Agencias transparentes.&lt;/li&gt;&lt;/ul&gt;</li></ul></td></tr><tr><td>Fuente de medios</td><td><ul><li><span>En la lista</span></li><li><span>No está en la lista</span></li><li><span>Igual a</span></li><li><span>Distinto de</span></li><li><span>Contiene</span></li><li><span>No contiene</span></li><li><span>Empieza por</span></li><li><span>Termina en</span></li><li> <span>Coincide con la expresión regular</span><span></span> </li></ul></td><td><ul><li><span>Buscar el valor deseado.</span></li><li><span>Selecciona desde el menú.</span></li><li><span>Texto libre (para valores que no existen en tus resultados de búsqueda).</span></li></ul></td><td rowspan="6"><ul><li> <span>El menú se basa en:</span><ul><li>Aplicaciones y agencias seleccionadas.</li><li>Tráfico de los últimos 30 días, ordenado por volumen de tráfico.</li></ul></li><li><span>El texto libre debe introducirse exactamente como aparece en el raw data.</span></li></ul></td></tr><tr><td>Campaña</td><td rowspan="5"><ul><li><span>En la lista</span></li><li><span>No está en la lista</span></li><li><span>Igual a</span></li><li><span>Distinto de</span></li><li><span>Contiene</span></li><li><span>No contiene</span></li><li><span>Empieza por</span></li><li><span>Termina en</span></li><li><span>Está vacío</span></li><li><span>No está vacío</span></li><li><span>Coincide con la expresión regular</span></li></ul></td><td><ul><li>Buscar el valor deseado.</li><li>Selecciona un valor del menú.</li><li>Texto libre (para valores que no existen en tus resultados de búsqueda).</li></ul></td></tr><tr><td>Campaign ID</td><td rowspan="4"><ul><li><span>Solo texto libre.</span></li><li><span>Es posible agregar varios valores separados por espacios.</span></li></ul></td></tr><tr><td>Ad ID</td></tr><tr><td>ID de conjunto de anuncios</td></tr><tr><td>Nombre de conjunto de anuncios</td></tr></tbody></table>

</Accordion>

<Accordion title="Condiciones de instalación">

La sección **Condiciones** es donde se definen las condiciones que determinan cuándo se bloquean las atribuciones de instalación o se atribuyen a la última fuente válida.

Puedes añadir varias condiciones y grupos de condiciones a cada regla.

Las condiciones se definen según las condiciones, los operadores y los valores descritos en la siguiente tabla.

#### Carga masiva

Al seleccionar los operadores **En la lista** o **No está en la lista** en las condiciones que lo admiten, tienes la opción de cargar en masa un archivo CSV al añadir nuevos elementos.

Para hacerlo:

1. Selecciona una condición con un operador **En la lista** o **No está en la lista** .
2. Selecciona **En la lista** o **No está en la lista** en la lista desplegable del operador.
3. Selecciona **Cargar archivo CSV** en el cuadro **Añadir nuevos elementos**.

Nota: El archivo CSV puede contener hasta 17 mil valores.

Hay opciones adicionales de condiciones disponibles para los clientes de Protect360, tanto para [instalaciones](/docs/implement-validation-rules-to-prevent-fraud#protect360-install-conditions) como para [eventos in-app](/docs/implement-validation-rules-to-prevent-fraud#protect360-inapp-event-conditions).

<table><thead><tr><th><span>Condición</span></th><th><span>Operador</span></th><th><span>Valor</span></th><th><span>Comentarios</span></th></tr></thead><tbody><tr><td><span>Campaña</span></td><td rowspan="6"><ul><li><span>Igual a</span></li><li><span>Distinto de</span></li><li><span>No contiene</span></li><li><span>Contiene</span></li><li><span>Empieza por</span></li><li><span>Termina en</span></li><li><span>En la lista</span></li><li><span>No está en la lista</span></li><li><span>Coincide con la expresión regular</span></li><li><span>Está vacío</span></li><li><span>No está vacío</span></li></ul></td><td><ul><li>Buscar el valor deseado.</li><li>Selecciona un valor del menú.</li><li>Texto libre (para valores que no existen en tus resultados de búsqueda).</li></ul></td><td rowspan="11"><ul><li> <span>El menú se basa en:</span><ul><li>Aplicaciones y agencias seleccionadas.</li><li>Tráfico de los últimos 30 días, ordenado por frecuencia de tráfico.</li></ul></li><li><span>El texto libre debe introducirse exactamente como aparece en el raw data.</span></li></ul></td></tr><tr><td><span>Campaign ID</span></td><td rowspan="5"><ul><li><span>Solo texto libre.</span></li><li><span>Es posible agregar varios valores separados por espacios.</span></li></ul></td></tr><tr><td><span>Ad ID</span></td></tr><tr><td><span>ID de conjunto de anuncios</span></td></tr><tr><td><span>Nombre de conjunto de anuncios</span></td></tr><tr><td><span>Tipo de dispositivo</span></td></tr><tr><td><span>Geolocalización</span></td><td rowspan="3"><ul><li><span>En la lista</span></li><li><span>No está en la lista</span></li><li><span>Igual a</span></li><li><span>Distinto de</span></li></ul></td><td><ul><li><span>Busca el valor deseado (según el nombre del país, el código de país, el estado o la ciudad).</span></li><li><span>Selecciona un valor del menú.</span></li></ul></td></tr><tr><td><span>Platform</span></td><td><span>Selecciona un valor del menú.</span></td></tr><tr><td><span>Moneda</span></td><td><p>Solo moneda. Valores posibles:</p><p>USD, NZD, SGD, IMP, ANG, MNT, BIF, BBD, HUF, ERN, AZN, AOA, PYG, MYR, GYD, VUV, SLL', FKP, DJF, GNF, LVL, MMK, MRO, RSD, CLF, XDR, ZAR, TND, PHP, KGS, XPD, RON, RUB, KMF, SCR, GIP, TRY, JEP, UYU, XCD, FJD, GHS, MVR, AWG, UGX, TOP, CVE, MKD, COP, CUC, GTQ, KZT, MXN, MGA, AUD, BDT, ISK, KRW, DZD, GGP, OMR, ZMW, MOP, CUP, JPY, SHP, LSL, ETB, BWP, MAD, AED, NGN, BRL, GEL, IDR, EUR, GBP, WST, XAF, SZL, XOF, SEK, UZS, KES, KYD, ILS, KWD, NPR, BZD, QAR, UAH, BTN, HTG, DKK, VND, SBD, JMD, IQD, LBP, XPT, HRK, HKD, JOD, PAB, CDF, VEF, XAU, BAM, CNY, SOS, XPF, GMD, DOP, XAG, KPW, BOB, BHD, BYN, BYR, LRD, BGN, AMD, CZK, CAD, LAK, EEK, MTL, PLN, LKR, BTC, MWK, LTL, ZMK, PGK, YER, PEN, KHR, RWF, BSD, AFN, ZWL, LYD, TMT, HNL, TWD, IRR, MUR, THB, ALL, TJS, SDG, BMD, CRC, NOK, SRD, MZN, CLP, STD, SYP, TZS, EGP, ARS, MDL, INR, SAR, PKR, TTD, NIO, BND, NAD, SVC, CHF</p></td></tr><tr><td><span>Ingresos</span></td><td><ul><li><span>Menor que</span></li><li><span>Menor o igual que</span></li><li><span>Mayor que</span></li><li><span>Mayor o igual que</span></li><li><span>Está entre</span></li><li><span>Igual a</span></li><li><span>Distinto de</span></li></ul></td><td><ul><li><span>Solo texto libre.</span></li></ul></td></tr><tr><td><span>Versión de SO</span></td><td><ul><li><span>Menor que</span></li><li><span>Menor o igual que</span></li><li><span>Mayor que</span></li><li><span>Mayor o igual que</span></li><li><span>Igual a</span></li><li><span>Distinto de</span></li><li><span>Está entre</span></li><li><span>En la lista</span></li><li><span>No está en la lista</span></li><li><span>Está vacío</span></li><li><span>No está vacío</span></li></ul></td><td><ul><li><span>Buscar el valor deseado.</span></li><li><span>Selecciona desde el menú.</span></li><li><span>Texto libre (para valores que no existen en tus resultados de búsqueda).</span></li></ul></td></tr><tr><td><span>App version</span></td><td><ul><li><span>Menor que</span></li><li><span>Menor o igual que</span></li><li><span>Mayor que</span></li><li><span>Mayor o igual que</span></li><li><span>Igual a</span></li><li><span>Distinto de</span></li><li><span>Está entre</span></li><li><span>En la lista</span></li><li><span>No está en la lista</span></li><li><span>No en las últimas</span></li><li><span>No en la(s) última(s) (principal(es))</span></li><li><span>Está vacío</span></li><li><span>No está vacío</span></li></ul></td><td><ul><li>Buscar el valor deseado.</li><li>Selecciona un valor del menú.</li><li>Texto libre (para valores que no existen en tus resultados de búsqueda).</li></ul></td><td><ul><li> <span>El menú se basa en el </span>tráfico de los últimos 30 días, ordenado por frecuencia de tráfico.</li><li><span>El texto libre debe introducirse exactamente como aparece en el raw data.</span></li><li> <span>Para "No está entre las últimas", si tienes más de una serie de versiones, selecciona "No está entre las últimas (principal)". </span><a href="./implement-validation-rules-to-prevent-fraud#how-do-the-not-in-last-conditions-work"><span>Saber más</span></a> </li></ul></td></tr><tr><td><span>Días de retrospectiva</span></td><td><ul><li><span>Menor que</span></li><li><span>Mayor o igual que</span></li><li><span>Está entre</span></li></ul></td><td><ul><li><span>Texto libre: un solo valor numérico.</span></li></ul></td><td><ul><li><span>Hace referencia a la ventana de lookback de impresiones/clics en días.</span></li><li><span>Garantiza que no pagues por instalaciones con un enlace de atribución que se modificó para permitir un período de atribución más largo.</span></li><li><span>No sustituye la configuración de la ventana de lookback de tu enlace de atribución.</span></li><li> <span>[Recomendado] Úsalo en combinación con la condición de tipo de toque de atribución (</span><a href="./implement-validation-rules-to-prevent-fraud#protect360-install-conditions"><span>disponible con Protect360</span></a><span>)</span> </li></ul></td></tr><tr><td><span>Está preinstalada</span></td><td rowspan="2"><ul><li><span>Sí</span></li><li><span>No</span></li></ul></td><td rowspan="2"><ul><li>Sin valor (el operador es el valor)</li></ul></td><td><ul><li> <span>Valida todos los tipos de preinstalaciones:</span><ul><li><span>Preinstalaciones de fábrica, es decir, una app que viene en el dispositivo como parte del sistema operativo.</span></li><li><span>Preinstalaciones promocionadas, es decir, una app promocionada y ofrecida a los usuarios tan pronto como se inicializa el dispositivo. Esto lo realizan fuentes de medios designadas para preinstalaciones.</span></li></ul></li><li>Para instalaciones con múltiples clics/fuentes, esta condición valida si una de las fuentes es una preinstalación.</li></ul></td></tr><tr><td><span>Es deeplink</span></td><td><span>Un campo de enlace profundo vacío en el raw data se considera como Es enlace profundo = No</span></td></tr></tbody></table>

> 📘 **Nota**
>
> Las instalaciones orgánicas no tienen ninguna campaña ni fuente de medios asociada, por lo que campos como **Campaña** y **Nombre del conjunto de anuncios** siempre son **null** en ellas, no cadenas vacías. Una regla que usa **Coincidir condiciones** con un operador **Está vacío** en estos campos no coincidirá con las instalaciones orgánicas, por lo que no las bloqueará.
>
> Para incluir también el tráfico orgánico, configura la regla con **No coincidir condiciones** y combina las condiciones con **O**, usando **No está vacío** en los mismos campos (por ejemplo, **Campaña no está vacía** **O** **Nombre del conjunto de anuncios no está vacío**, además de cualquier otra condición que necesite la regla). Al invertir la lógica de esta forma, la regla puede coincidir tanto con valores null como con cadenas vacías.

</Accordion>

<Accordion title="Fuentes de eventos in-app">

Cuando se selecciona **Eventos in-app** en la sección **Eventos**, además de las [opciones de fuentes habituales](/docs/implement-validation-rules-to-prevent-fraud#install-sources), los clientes tienen otra opción de fuente para definir a qué eventos in-app se aplica su regla. 

La fuente se define según el campo, los operadores y los valores descritos en la siguiente tabla.

**Nota**: Todas las demás fuentes de eventos in-app se basan en la fuente de instalación con la que está asociado el IAE (por ejemplo, agencia, fuente de medios, campaña, ID de campaña, ID de sitio, etc.).

| Campo | Operador | Valor | Observaciones |
| --- | --- | --- | --- |
| Nombre del evento | <ul><li>En la lista</li><li>Fuera de la lista</li><li>Igual a</li><li>No es igual a</li><li>Contiene</li><li>No contiene</li><li>Comienza con</li><li>Termina con</li><li>Está vacío</li><li>No está vacío</li><li>Coincide con la expresión regular</li></ul> | <ul><li>Buscar el valor deseado.</li><li>Seleccionar el valor del menú.</li><li>Texto libre (para valores que no existen en tus resultados de búsqueda).</li></ul> | <ul><li>El texto libre debe escribirse exactamente como aparece en el raw data.</li></ul> |

</Accordion>

<Accordion title="Condiciones de eventos in-app">

Cuando se selecciona **Eventos in-app** en la sección **Eventos**, los clientes tienen opciones de condición adicionales para definir a qué eventos in-app se aplica su regla. Estas condiciones se pueden mezclar y combinar con cualquiera de las condiciones que no son de Protect360 [listadas anteriormente](/docs/implement-validation-rules-to-prevent-fraud#install-conditions).

Las condiciones de Protect360 se definen según las condiciones, los operadores y los valores descritos en la siguiente tabla.

| Condición | Operador | Valor | Observaciones |
| --- | --- | --- | --- |
| Nombre del evento | <ul><li>En la lista</li><li>Fuera de la lista</li><li>Igual a</li><li>Igual a</li><li>Contiene</li><li>No contiene</li><li>Comienza con</li><li>Termina con</li><li>Está vacío</li><li>Igual a</li><li>Coincide con la expresión regular</li></ul> | <ul><li>Versión del sistema operativo</li><li>Seleccionar el valor del menú.</li><li>Texto libre (para valores que no existen en tus resultados de búsqueda).</li></ul> | <ul><li>El texto libre debe escribirse exactamente como aparece en el raw data.</li></ul> |
| Aleatorio | <ul><li>Menor que</li><li>Menor o igual que</li><li>Mayor que</li><li>Mayor o igual que</li><li>Igual a</li><li>No es igual a</li><li>Entre</li><li>En la lista</li><li>Fuera de la lista</li><li>Igual a</li><li>No en la(s) última(s) (principal(es))</li><li>Igual a</li><li>No está vacío</li></ul> | <ul><li>Buscar el valor deseado.</li><li>Selecciona el valor del menú:</li><li>Texto libre (para valores que no existen en tus resultados de búsqueda).</li></ul> | <ul><li>El menú se basa en el tráfico de los últimos 30 días, ordenado por frecuencia de tráfico.</li><li>El texto libre debe escribirse exactamente como aparece en el raw data.</li><li>Para "No en la(s) última(s)", si tienes más de una serie de versiones, selecciona "No en la(s) última(s) (principal(es))". [Saber más](/docs/implement-validation-rules-to-prevent-fraud#how-do-the-not-in-last-conditions-work)</li></ul> |

> 📘 **Nota**
>
> Las condiciones de los nombres de eventos no distinguen entre mayúsculas y minúsculas. Todos los nombres de eventos se convierten automáticamente a minúsculas antes de la evaluación. Por ejemplo, si ingresas a **Enviar formulario**, el sistema lo trata como **enviar formulario**.

</Accordion>

<Accordion title="Fuentes de eventos in-app e instalación de Protect360">

Además de las [opciones de fuente habituales](/docs/implement-validation-rules-to-prevent-fraud#install-sources), los clientes de Protect360 tienen otra opción de fuente para definir a qué instalaciones se aplica su regla. La fuente se define según el campo, los operadores y los valores descritos en la siguiente tabla.

| Campo | Operador | Valor | Observaciones |
| --- | --- | --- | --- |
| ID del sitio | <ul><li>En la lista</li><li>Fuera de la lista</li><li>Igual a</li><li>No es igual a</li><li>Contiene</li><li>No contiene</li><li>Comienza con</li><li>Termina con</li><li>Está vacío</li><li>No está vacío</li><li>Coincide con la expresión regular</li></ul> | <ul><li>Solo texto libre.</li><li>Es posible agregar varios valores separados por espacios.</li></ul> | <ul><li>El texto libre debe escribirse exactamente como aparece en el raw data.</li></ul> |

</Accordion>

<Accordion title="Condiciones de instalaciones de Protect360">

Los clientes de Protect360 tienen un conjunto adicional de condiciones para validar sus instalaciones. Estas condiciones se pueden mezclar y combinar con cualquiera de las condiciones que no son de Protect360 [listadas anteriormente](/docs/implement-validation-rules-to-prevent-fraud#install-conditions).

Las condiciones de Protect360 se definen según las condiciones, los operadores y los valores descritos en la siguiente tabla.

<table><thead><tr><th><span>Condición</span></th><th><span>Operador</span></th><th><span>Valor</span></th><th><span>Observaciones</span></th></tr></thead><tbody><tr><td><span>CTIT (Tiempo del clic la a instalación)</span></td><td><ul><li><span>Menor que</span></li><li><span>Mayor o igual que</span></li><li><span>Entre</span></li></ul></td><td><ul><li><span>Texto libre: Un solo valor numérico.</span></li></ul></td><td><ul><li> <span>Utiliza este campo solo si estás seguro de un CTIT específico (generalmente en una geolocalización específica). De lo contrario, puedes provocar instalaciones bloqueadas con falsos positivos.</span><br/><span><strong>Nota</strong>: El motor antifraude Protect360 tiene maneras sofisticadas integradas para identificar anomalías complejas de CTIT debido al secuestro de atribuciones, inundaciones de clics, instalaciones falsas de bots y más.</span> </li><li> <span>Considera usar este campo junto con los siguientes campos:</span><ul><li>Está preinstalado</li><li>Es deeplink</li><li>Geografía</li></ul></li></ul><p>Nota: La condición de instalación CTIT no admite el bloqueo de instalaciones atribuidas al tipo de interacción engaged click, solo a clics "normales".</p></td></tr><tr><td><span>ID de usuario de cliente (CUID)</span></td><td><ul><li><span>Igual a</span></li><li><span>No es igual a</span></li><li><span>No contiene</span></li><li><span>Contiene</span></li><li><span>Comienza con</span></li><li><span>Termina con</span></li><li><span>En la lista</span></li><li><span>Fuera de la lista</span></li><li><span>Coincide con la expresión regular</span></li><li><span>Está vacío</span></li><li><span>No está vacío</span></li></ul></td><td><ul><li><span>Solo texto libre.</span></li><li><span>Es posible agregar varios valores separados por espacios.</span></li></ul></td><td><ul><li> <span>El menú se basa en el</span> tráfico de los últimos 30 días, ordenado por frecuencia de tráfico.</li><li><span>El texto libre debe escribirse exactamente como aparece en el raw data.</span></li></ul></td></tr><tr><td><span>Versión del SDK</span></td><td><ul><li><span>Menor que</span></li><li><span>Menor o igual que</span></li><li><span>Mayor que</span></li><li><span>Mayor o igual que</span></li><li><span>Igual a</span></li><li><span>No es igual a</span></li><li><span>Está entre</span></li><li><span>En la lista</span></li><li><span>Fuera de la lista</span></li></ul></td><td><ul><li>Buscar el valor deseado.</li><li>Seleccionar el valor del menú.</li><li>Texto libre (para valores que no existen en tus resultados de búsqueda).</li></ul></td><td><ul><li> <span>El menú se basa en el</span> tráfico de los últimos 30 días, ordenado por frecuencia de tráfico.</li><li><span>El texto libre debe escribirse exactamente como aparece en el raw data.</span></li></ul></td></tr><tr><td><span>Instalador/Tienda</span></td><td rowspan="3"><ul><li>En la lista</li><li>Fuera de la lista</li><li>Igual a</li><li>No es igual a</li></ul></td><td><p><span>Asignación de datos en Data Locker:</span></p><ul><li>Google Play</li><li>Otras tiendas</li><li>Fuera de la tienda</li></ul></td><td><ul><li>Google Play: AppsFlyer identifica que el paquete de instalación es <code>com.android.vending</code>.</li><li>Otras tiendas: AppsFlyer identifica que la instalación proviene de una tienda Android de terceros.</li><li>Fuera de la tienda: AppsFlyer identifica un APK que no está en ninguna tienda Android.</li></ul><p><span>En el caso de que el dispositivo de un usuario no proporcione el parámetro del instalador/tienda a AppsFlyer, la regla no tiene efecto.</span></p></td></tr><tr><td>Instalador/tienda personalizado</td><td>Texto libre (para valores que no existen en tus resultados de búsqueda).</td><td><ul><li>Si el cliente eligió una condición de "otro" Y también una condición de instalador personalizado=X, el bloqueo será solo para el instalador X</li><li>Si el cliente eligió una condición de "otro" O una condición de instalador personalizado=X, el bloqueo será para TODOS los "otros" instaladores/tiendas, y X es parte de ese grupo.</li></ul></td></tr><tr><td><span>Tipo de toque para la atribución</span></td><td><ul><li><span>Clic</span></li><li><span>Impresión</span></li></ul></td><td><ul><li>[Recomendado] Utilízalo en combinación con la condición de días de lookback.</li><li>Para simplemente no atribuir las impresiones, puedes <a href="./measure-view-through-engagements#turn-off-viewthroughattribution" target="_blank">desactivar la atribución por impresiones</a>.</li></ul></td></tr><tr><td><span>Operador</span></td><td><ul><li>En la lista</li><li>tagged_sub_reason</li><li>Igual a</li><li>No es igual a</li></ul></td><td><ul><li><span>Solo texto libre</span></li></ul></td><td> </td></tr><tr><td><span>Agente de usuario</span></td><td><ul><li>Contiene</li><li>No contiene</li></ul></td><td><ul><li><span>Solo texto libre</span></li></ul></td><td> </td></tr><tr><td><span>Dirección IP</span></td><td><ul><li>En la lista</li><li>Fuera de la lista</li><li>Igual a</li><li>No es igual a</li></ul></td><td><ul><li><span>Solo texto libre</span></li></ul></td><td> </td></tr></tbody></table>

</Accordion>

<Accordion title="Condiciones de eventos in-app de Protect360">

Cuando se selecciona **Eventos in-app** en la sección **Eventos**, los clientes de Protect360 tienen opciones de condición adicionales para definir a qué eventos in-app se aplica su regla. Estas condiciones se pueden mezclar y combinar con cualquiera de las condiciones que no son de Protect360 [listadas anteriormente](/docs/implement-validation-rules-to-prevent-fraud#install-conditions).

Las condiciones de Protect360 se definen según las condiciones, los operadores y los valores descritos en la siguiente tabla.

| Condición | Operador | Valor | Observaciones |
| --- | --- | --- | --- |
| Origen del evento | <ul><li>En la lista</li><li>Fuera de la lista</li><li>Igual a</li><li>No es igual a</li></ul> | <ul><li>Buscar el valor deseado.</li><li>Seleccionar el valor del menú.</li></ul> | Selecciona SDK o Servidor a servidor. |
| Valor del evento | <ul><li>En la lista</li><li>Fuera de la lista</li><li>Igual a</li><li>No es igual a</li><li>Contiene</li><li>No contiene</li><li>Comienza con</li><li>Termina con</li><li>Está vacío</li><li>No está vacío</li><li>Coincide con la expresión regular</li></ul> | <ul><li>Solo texto libre.</li><li>Es posible agregar varios valores separados por espacios.</li></ul> | <ul><li>Selecciona tus valores preferidos.</li></ul> |
| Tiempo de la instalación al evento (en segundos) | <ul><li>Menor que</li><li>Mayor o igual que</li><li>Entre</li></ul> | Texto libre. Un solo valor numérico. | <ul><li>Según el flujo de tu aplicación, decides el tiempo válido que debe pasar entre la instalación de la aplicación y un evento in-app.<ul><li>Ejemplo: Tiempo hasta alcanzar el nivel 5, tiempo hasta el primer depósito (FTD), tiempo hasta el checkout, etc.</li></ul></li><li>El tiempo se expresa en segundos, pero puedes validar minutos, horas o días utilizando su equivalente en segundos.</li></ul> |

</Accordion>

<Accordion title="Lógica entre condiciones y grupos de condiciones">

Si agregas varias condiciones o grupos de condiciones a una regla, selecciona la relación lógica entre ellos usando: 

* **Y**: Significa que la instalación cumple con todas las condiciones definidas.
* **O**: Significa que la instalación cumple al menos una de las condiciones definidas.

Por ejemplo, si deseas validar las instalaciones según la plataforma y el sistema operativo, debes seleccionar **y**. De esa forma, la plataforma definida debe acompañar siempre al SO definido. Si deseas validar las instalaciones según la plataforma o el sistema operativo, debes seleccionar **o**.

</Accordion>

## Funciones adicionales

<Accordion title="Ver la lista de reglas">

**Para ver todas las reglas creadas en tu cuenta**:

1. En AppsFlyer, ve a **Configuración** > **Reglas de validación.**  
   Se abre la ventana reglas de validación, con la lista de reglas de validación.
2. Selecciona tu vista de tabla preferida utilizando el selector **Vista de lista/Vista detallada**.
3. Filtra las reglas de la lista mediante las opciones de búsqueda y filtro.
   * Puedes buscar por nombre de la regla, fuente, nombre de la condición y valor.
   * Por ejemplo, escribe **7** para encontrar todas las reglas definidas para una versión del sistema operativo que contenga 7 (por ejemplo: “2.7.4”, “7.1”, etc.). (p. ej.: «2.7.4», «7.1», etc.). O escribe **Canada** para encontrar reglas definidas con Canada en la condición Geo.

La tabla de reglas de validación muestra 25 reglas por página de forma predeterminada. Puedes cambiar el número de reglas mostradas por página a 10, 25 o 50.

La búsqueda y los filtros se aplican al conjunto completo de reglas, independientemente de la página que estés viendo.

</Accordion>

<Accordion title="Agregar regla">

**Para configurar una regla nueva**:

1. En AppsFlyer, ve a **Configuración** > **Reglas de validación.**  
   Se abre la ventana reglas de validación.
2. Haz clic en **Agregar regla.**  
   Se abre la ventana “Agregar nueva regla”.
3. Inserta un **nombre de regla**. Utiliza un nombre único que:
   * Describe exactamente la regla.
   * no resulte ofensivo para las ad networks, ya que aparecerá en el reporte de instalaciones bloqueadas y en los postbacks rechazados enviados a las ad networks.
4. Completa las [secciones del generador de reglas](/docs/implement-validation-rules-to-prevent-fraud#creador-de-reglas).
5. [Opcional] Agrega condiciones y/o grupos de condiciones, según sea necesario. Asegúrate de seleccionar la [lógica relevante entre condiciones/grupos de condiciones](/docs/implement-validation-rules-to-prevent-fraud#logic-between-conditions-and-condition-groups).
6. [Opcional] Haz clic en **Estimar el impacto del tráfico** para [ver cómo afectará tu regla al tráfico](/docs/implement-validation-rules-to-prevent-fraud#view-validation-rule-impact).
7. Haz clic en **Guardar**.

> 📘 **Nota:**
>
> La versión de la aplicación solo debe contener números. Por ejemplo, 2.2.1.
>
> Nota:
>
> Las versiones numéricas de aplicaciones (por ejemplo, 2.2.1) admiten todos los operadores (igual, mayor, menor, etc.).
>
> Si la versión de la aplicación es texto personalizado (por ejemplo, version123 o our\_latest\_version), solo funcionan los operadores "igual" o "no es igual"; no se aplicarán los términos "mayor" o "inferior".

</Accordion>

<Accordion title="Modo Tagged de VR">

Utiliza el modo Tagged para probar las reglas de validación con tráfico en vivo antes de bloquear la atribución. Las reglas Tagged marcan las instalaciones y los eventos in-app que cumplen las condiciones de la regla, pero la atribución no se ve afectada.

El modo Tagged solo admite instalaciones y eventos in-app.

Utiliza el modo Tagged para:

* Probar reglas complejas con tráfico en vivo antes de bloquear la atribución.
* Identificar posibles falsos positivos.
* Revisar por qué se habría activado una regla antes de implementarla.
* Comprender el impacto real en el tráfico antes de cambiar el estado de la regla a Implemented.

Práctica recomendada: Primero crea la regla en modo Tagged, revisa el tráfico marcado en Data Locker y cambia el estado de la regla a Implemented cuando tengas la certeza de que la regla es precisa. Intenta completar esta revisión en menos de 7 días para mantener la protección activa.

#### Cómo funciona el modo Tagged

Al crear o editar una regla de validación, selecciona el Detection status en la sección Rule outcome.

* Tagged: La regla marca los datos que coinciden para su reporte y análisis. La atribución no se ve afectada.
* Implemented: La regla bloquea activamente la atribución según el resultado de regla seleccionado.

Nota: El modo Tagged solo se aplica al tráfico en vivo a partir del momento en que se guarda la regla. No marca datos históricos.

#### Configuración del resultado de la regla

La sección Rule outcome, anteriormente Action, define cómo AppsFlyer gestiona el tráfico que cumple las condiciones de la regla. También proporciona un resumen general de la configuración de la regla para que puedas verificar el impacto esperado antes de guardarla.

| Estado de detección | Efecto en la atribución | Disponibilidad de datos |
| --- | --- | --- |
| Tagged | No afectan. El tráfico se atribuye con normalidad. | Visible en los reportes de Data Locker. |
| Implemented | Bloqueo activo. La atribución se bloquea según el Rule outcome seleccionado. | Visible en los dashboards de Protect360 y en los reportes de exportación. |

#### Qué puedes esperar al configurar una regla

Mientras configuras la regla, un panel de información dinámico muestra el comportamiento esperado de la regla en función de:

* Lógica de coincidencia o no coincidencia
* Selección de app
* Estado de detección

Cuando el estado de detección se configura como Tagged, la regla actúa como una herramienta de detección. AppsFlyer muestra una notificación que confirma que los datos coincidentes se marcan en los reportes de exportación, incluido Data Locker, pero no se bloquean para la atribución.

Cuando el estado de detección se configura como Implemented, las instalaciones o los eventos in-app que cumplen los criterios de la regla se bloquean para la atribución o se reatribuyen según el Rule outcome seleccionado. El panel de información resume el resultado activo antes de que guardes la regla.

#### Ejemplo: Lógica de coincidencia

Para las instalaciones detectadas que cumplen las condiciones de la regla para las apps seleccionadas, el panel de información puede indicar que las instalaciones:

* Se bloquean para la atribución o se detectan como posterior a la atribución.
* Se reatribuyen a la última fuente válida no orgánica u orgánica.
* Son visibles en los reportes de exportación.

#### Ejemplo: No coincidir con la lógica

Para las instalaciones detectadas que no cumplen las condiciones de la regla para las apps seleccionadas, incluidas las futuras apps, el panel de información puede indicar que las instalaciones:

* Se bloquean para la atribución o se detectan como post-attribution.
* Se marcan como fraude sin corregir la atribución.
* Son visibles en los reportes de exportación.

Todas las demás instalaciones que cumplen las condiciones de la regla dentro de estas apps no se bloquean.

#### Configurar una regla en modo Tagged

Para probar una regla de validación con el modo Tagged:

1. En AppsFlyer, ve a Configuración > Reglas de validación.
2. Selecciona una regla existente o haz clic en Agregar Regla.
3. Completa los detalles de la regla, las fuentes de tráfico y las condiciones.
4. En la sección Resultado de la regla, establece el estado de Detección en Tagged.
5. Haz clic en Guardar.

Después de guardar la regla, AppsFlyer marca el tráfico en vivo que coincide para su reporte y análisis. La atribución continúa con normalidad.

#### Analizar datos Tagged

Los datos Tagged de las reglas de validación no son visibles en el dashboard de Protect360 ni en el paquete de protección contra el fraude.

Para analizar el impacto de las reglas Tagged, utiliza Data Locker para exportar los datos Tagged. Los datos Tagged se incluyen en los reportes de instalaciones y eventos in-app, para que puedas comparar el tráfico Tagged con las atribuciones válidas.

**Asignación de datos etiquetados:**

| Datos Tagged | Reporte de Data Locker | Reporte de raw data |
| --- | --- | --- |
| Instalaciones Tagged | Reporte de instalaciones | Instalaciones Tagged |
| Eventos in-app Tagged | Reporte de eventos in-app | Reporte de eventos in-app etiquetados |

**Campos de datos etiquetados**

Utiliza las siguientes columnas en las exportaciones de Data Locker para identificar el tráfico marcado por las reglas de validación:

| Columna | Descripción |
| --- | --- |
| Nombre de la regla<br /><br />(Reportes de raw data) | Nombre de la regla de validación que marcó el registro. |
| ID de la regla<br /><br />(Reportes de raw data) | ID único de la regla de validación que marcó el registro. |
| detected\_rule\_name<br /><br />(Data Locker) | Nombre de la regla de validación que marcó el registro. |
| detected\_rule\_id<br /><br />(Data Locker) | ID único de la regla de validación que marcó el registro. |

#### Cambiar una regla Tagged a Implemented

Después de revisar los datos Tagged y confirmar que la regla funciona según lo previsto, cambia el estado de la regla a Implemented.

Para cambiar una regla de Tagged a Implemented:

1. En AppsFlyer, ve a Configuración > Reglas de validación.
2. Selecciona la regla.
3. En la sección Rule outcome, configura Detection status como Implemented.
4. Haz clic en Guardar.

A partir del momento en que se guarda la regla, AppsFlyer bloquea activamente el tráfico que coincide según el Rule outcome seleccionado.

</Accordion>

<Accordion title="Editar o eliminar una regla">

**Para editar, eliminar, habilitar o deshabilitar una regla**:

* En la [lista de reglas](/docs/implement-validation-rules-to-prevent-fraud), selecciona la acción que quieras realizar para una regla específica.
  * En **Activar**: habilita o deshabilita la regla.
  * En **Acción**: edita o elimina la regla.

</Accordion>

## Preguntas frecuentes

<Accordion title="¿Qué es una 'expresión regular'?">

Un patrón de expresión regular está compuesto por caracteres para los que quieres encontrar una coincidencia. Los patrones simples se construyen con caracteres para los que quieres encontrar una coincidencia directa. Cuando la búsqueda de una coincidencia requiere algo más que una coincidencia directa, puedes incluir caracteres especiales en el patrón.

**Ejemplos**:

| **Expresión regular** | **Descripción** |
| --- | --- |
| ^abc | Empieza con abc |
| xyz$ | Termina con xyz |
| ^abc.*xyz$ | Empieza con abc y termina con xyz |
| ^abc.*(?&lt;xyz)$ | Empieza con abc y no termina con xyz |
| ^([0-9]`{2}`) | Empieza con 2 dígitos |
| "example\_param":"[5\|6] | El valor del parámetro especificado comienza con 5 o 6. |
| ^.\{0\}$\|^\{\}$ | Está vacío, o solo es \{\} |

</Accordion>

<Accordion title="¿Por qué la fuente o la condición no aparecen como un valor sugerido cuando las busco?">

Hay dos razones posibles:

* Asegúrate de que las aplicaciones correspondientes estén seleccionadas. Si la aplicación no está seleccionada, los valores no se muestran en los resultados de búsqueda.
* Los resultados se muestran solo si el valor que estás buscando apareció en tu tráfico durante los últimos 30 días. Además, hay un desfase de hasta 1 día entre el momento en que se produce la conversión y el momento en que la fuente o la condición se muestra como una opción del menú.

Si el valor no aparece como resultado de la búsqueda, puedes escribir el valor como texto libre y pulsar la tecla “Enter” en tu teclado.

</Accordion>

<Accordion title="¿Por qué mis opciones de fuentes de medios solo incluyen Meta Ads y X Ads?">

Las opciones del campo fuente de medios dependen de la selección realizada en agencia.

</Accordion>

<Accordion title="¿Es necesario utilizar 'Y/O' tanto dentro de las condiciones específicas como entre los grupos de condiciones?">

Depende de tu caso de uso. En ocasiones, cualquiera de las dos opciones produce el mismo resultado. Otras veces, ambas opciones son necesarias.

Por ejemplo, si en EE. UU. solo admites instalaciones con la versión 10 del sistema operativo o superior, pero en Brasil admites la versión 7 o superior, necesitarás una regla como esta:

`{[Geo = US] y [versión del OS = 10]} OR {[Geo = Brazil] y [versión del OS = 7]}`

</Accordion>

<Accordion title="¿Bloquean las reglas de validación los clics?">

N.º Las reglas de validación pueden bloquear instalaciones, bloquear la atribución a las fuentes de una instalación (lo que impide que la fuente de medios de un clic o una impresión reciba la atribución) o bloquear eventos in-app. Sin embargo, ninguna de estas opciones bloquea el clic en sí, y los KPIs de clics no se ven afectados por la ejecución de las reglas de validación.

</Accordion>

<Accordion title="Al revisar el raw data, veo que las instalaciones que esperaba que fueran bloqueadas por las reglas de validación muestran un motivo de bloqueo diferente al nombre de mi regla. ¿Por qué?">

Esto significa que el bloqueo se debió al <Anchor target="_blank" href="/marketers/es/docs/protect360-raw-data-reports#motivos-de-bloqueo">motor de Protect360</Anchor> y no a una regla de validación. Consulta también [múltiples reglas](/docs/implement-validation-rules-to-prevent-fraud#multiple-rules).

</Accordion>

<Accordion title="¿Las reglas existentes se aplican automáticamente al tráfico de agencias integradas recientemente?">

Esto depende de la configuración de la **fuente**, como se describe en la siguiente tabla.

Si la regla no se aplica automáticamente, debes editarla:

* Cambia el campo Agencia a **Tráfico de agencia y no agencia** o selecciona la agencia específica.

<table><thead><tr><th>Configuración de fuente</th><th>Selección de campo de agencia</th><th>¿La regla se aplica si se creó antes de integrar cualquier agencia con alguna de tus apps?</th><th>¿La regla se aplica si se creó después de integrar al menos una agencia con alguna de tus apps?</th></tr></thead><tbody><tr><td>Todo el tráfico</td><td>N/R</td><td>Sí</td><td>Sí</td></tr><tr><td rowspan="3">Solo no orgánico</td><td>N/R</td><td>No</td><td>N/R</td></tr><tr><td>Tráfico de agencia y no agencia</td><td>N/R</td><td>Sí</td></tr><tr><td><p>Tráfico de no agencia y/o</p><p>agencias específicas</p></td><td>N/R</td><td>No</td></tr></tbody></table>

</Accordion>

<Accordion title="¿Cómo funcionan las condiciones 'No en la(s) última(s)'?">

Utiliza **No en las últimas** para permitir instalaciones de las **versiones más recientes de tu aplicación** y bloquear instalaciones de las **versiones anteriores**.

* **No en las últimas** ***X*** **versiones**: Permite instalaciones de las **últimas X versiones** de la app seleccionada y **bloquea** las instalaciones de **todas las versiones anteriores**.
* **No en las últimas (mayores)** ***X*** **versiones**: Utilízalo cuando tu esquema de versiones incluya **varias series de versiones principales** (por ejemplo, 1.x y 2.x). Esta condición permite las **últimas X versiones de cada serie principal** y bloquea las versiones anteriores de cada serie.

##### Ejemplo: No en las últimas

Tienes estas versiones existentes de la app:

* 1.0.01
* 1.0.02
* 1.0.03
* 2.0.01
* 2.0.02
* 2.0.03

Una regla definida con **No en las últimas 2 versiones**:

* **Permite**:
  * 2.0.02
  * 2.0.03
* **Bloquea**:
  * 1.0.01
  * 1.0.02
  * 1.0.03
  * 2.0.01

##### Ejemplo: No en las últimas (mayores)

Usando la misma lista de versiones anterior, una regla definida con **No en los últimos (mayores) 2 versiones**:

* **Permite**:
  * 1.0.02
  * 1.0.03
  * 2.0.02
  * 2.0.03
* **Bloquea**:
  * 1.0.01
  * 2.0.01

##### **Comprende cómo funciona esta condición con varias apps**

Si seleccionas **varias apps** en la regla, AppsFlyer evalúa la condición **No en las últimas** **por separado para cada app**.

Por ejemplo, si configuras **No en las últimas 3 versiones** y seleccionas la App A, la App B y la App C:

* La App A permite sus **últimas 3 versiones** según el historial de versiones de la **App A**.
* La App B permite sus **últimas 3 versiones** según el historial de versiones de la **App B**.

La App C permite sus **últimas 3 versiones** según el historial de versiones de la **App C**.

##### Cómo AppsFlyer determina la versión más reciente

Las versiones más recientes que usan las condiciones **Not in last** no son simplemente los números de versión más nuevos de tu tráfico. AppsFlyer calcula a diario la lista de versiones más recientes mediante un mecanismo de protección diseñado para evitar que los defraudadores hagan spoofing de una versión más reciente falsa para eludir la regla.

AppsFlyer añade una versión a la lista de versiones más recientes de una aplicación solo si esa versión cumple estas tres condiciones ese día:

* Se atribuyó a partir de una red de autorreporte (SRN).
* Tiene al menos 100 instalaciones atribuidas ese día.
* Esas instalaciones representan al menos el 70% de las instalaciones atribuidas por SRN de ese día para la aplicación.

##### Ejemplo: cálculo de la versión más reciente

En un día determinado, una aplicación recibe 300 instalaciones atribuidas por SRN: 210 en la v6.1.0, 45 en la v6.2.0 y 45 en la v6.3.0.

* v6.1.0 cumple las tres condiciones: se atribuye a SRN, tiene más de 100 instalaciones y alcanza una cuota del 70%. AppsFlyer la añade a la lista de versiones más recientes y pasa a formar parte de la referencia con la que se compara la regla.
* v6.2.0 y v6.3.0 no cumplen los requisitos. Cada una tiene menos de 100 instalaciones y una cuota inferior al 70%.

Si ninguna versión cumple las tres condiciones en un día determinado, AppsFlyer no actualiza la lista de versiones más recientes ese día. Esto significa que la regla podría no bloquear el tráfico como se espera hasta que una versión cumpla los requisitos.

</Accordion>

<Accordion title="¿Cómo puedo bloquear la atribución de instalaciones o eventos in-app procedentes de impresiones?">

Utiliza una regla de validación cuando quieras evitar la atribución procedente de interacciones basadas en impresiones y mantener la atribución únicamente para clics válidos. Si no se encuentra una fuente de medios válida basada en clics, la instalación se atribuye como orgánica. Esta configuración puede ayudar a abordar escenarios de atribución relacionados con el secuestro de instalaciones.

Para configurar la regla:

* En **Fuentes de tráfico**, selecciona **Todo el tráfico no orgánico.**
* En **Condiciones**, selecciona **Tipo de toque de atribución**.
  * Configura el operador como **En la lista**.
  * Selecciona **Impresiones**.
* En **Acción**, selecciona **Bloquear atribución y corregir a la última fuente de medios válida**.

No selecciones **Marcar instalaciones como inválidas y no atribuirlas** para este caso de uso. Esa acción está pensada para instalaciones que consideras no válidas o falsas. Si la instalación es real, pero no quieres atribuirla a una interacción basada en impresiones, utiliza **Bloquear atribución y corregir a la última fuente de medios válida** en su lugar.

</Accordion>

<Accordion title="¿El modo Tagged admite todos los tipos de condiciones?">

Sí. El modo Tagged admite todos los operadores y campos de las reglas de validación, incluida la lógica And/Or, Geo, OS version, SDK version y Event value.

</Accordion>

<Accordion title="¿Los datos Tagged aparecerán en los reportes de elementos bloqueados?">

N.º Los datos Tagged no se clasifican como tráfico bloqueado. El tráfico Tagged se identifica como Tagged y se considera un subconjunto del tráfico válido. Es visible en los reportes válidos de Data Locker.

</Accordion>

<Accordion title="¿Dónde puedo ver los datos Tagged?">

Utiliza Data Locker para ver los datos Tagged de las reglas de validación. Las instalaciones Tagged están disponibles en el informe de instalaciones y los eventos in-app Tagged están disponibles en el reporte de evento in-app.

Los datos Tagged no son visibles en el dashboard de Protect360 ni en el paquete de protección contra el fraude.

</Accordion>

<Accordion title="¿Puedo cambiar una regla de Tagged a Implemented en cualquier momento?">

Sí. Después de revisar los datos exportados y confirmar que la regla funciona según lo previsto, edita la regla, configura la detección como Implemented y guarda la regla. A partir de ese momento, la regla bloquea activamente el tráfico que coincide según el Rule outcome seleccionado.

</Accordion>

<Accordion title="¿Existe un límite en la cantidad de reglas que pueden configurarse como Tagged?">

El modo Tagged está disponible para los clientes Premium. No existe un límite estricto para la cantidad de reglas que pueden configurarse como Tagged. Como práctica recomendada, revisa las reglas Tagged y cámbialas a Implemented cuando tengas la certeza de que son precisas.

</Accordion>

<Accordion title="Rasgos y limitaciones">

| Caducado | Descripción |
| --- | --- |
| Acceso de usuario a la cuenta | Solo los usuarios de la cuenta con los <Anchor target="_blank" href="/marketers/es/docs/user-management">permisos adecuados</Anchor> pueden ver, agregar y editar reglas de validación. |
| Adquisición de usuarios | Las reglas de validación se aplican a las instalaciones, reinstalaciones y reatribuciones (cuando la aplicación se eliminó del dispositivo). No se aplican en casos de re-engagement, es decir, cuando la aplicación aún está en el dispositivo. |
| Desactivación automática de reglas | Si creas reglas:<ul><li>que utilizan fuentes o condiciones de Protect360 y, posteriormente, tu licencia o prueba de Protect360 caduca, las reglas se desactivan automáticamente.</li></ul> |
| Redes publicitarias | Requieren el permiso del anunciante **Ver reglas de validación** para ver los detalles de las reglas. **Nota**: Los nombres de las reglas siempre son visibles (también en el raw data).<br /><br /><Anchor target="_blank" href="/partners/es/docs/validation-rules-for-ad-networks-and-agencies">Saber más sobre las reglas de validación para las ad networks</Anchor> |
| Agencias | Requieren permiso del anunciante para:<ul><li>**Ver reglas de validación** para ver los detalles de las reglas. **Nota**: Los nombres de las reglas siempre son visibles (también en el raw data).</li><li>**Agregar reglas de validación** para agregar y editar reglas. **Nota**: Las agencias no pueden editar las reglas creadas por los anunciantes.</li><li>**Acceder al dashboard de Protect360 y al raw data** para ver y agregar reglas con las condiciones de Protect360.</li></ul><Anchor target="_blank" href="/partners/es/docs/validation-rules-for-ad-networks-and-agencies">Saber más sobre las reglas de validación para agencias</Anchor> |
| Usuarios únicos | Si tienes configurados más de 100 eventos in-app, aunque utilices reglas de validación para invalidar determinados eventos in-app, la <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#limitations">limitación del recuento de usuarios únicos</Anchor> seguirá aplicándose. Esto significa que los eventos que superen los 100 no contabilizarán usuarios únicos, aunque se invaliden mediante reglas de validación. |
| SKÁN | No compatible |
| Aleatorio | La condición de **engagement** admite el bloqueo únicamente de los tipos de engagement **click\_to\_app** y **view**. No se admiten otros tipos de engagement. |

</Accordion>

<div data-zendesk-anchors="overview=descripci%C3%B3n-general 01H8VFA2ADGT4AMC0NGDFXRB6Z=descripci%C3%B3n-general rule-builder=creador-de-reglas 01H8VFA2ADQVCR8RYV9SBG52R7=creador-de-reglas use-categorized-dimensions=usa-dimensiones-clasificadas-por-categor%C3%ADas h_01KTHT74EKM95D26AJJNCFG0XZ=usa-dimensiones-clasificadas-por-categor%C3%ADas h_01JK5G66CM9TCDK6GATNZC4QMW=nota-2 validation-rule-examples=ejemplos-de-reglas-de-validaci%C3%B3n h_01KQER0NTPGGC7RYVBGKTZP02S=ejemplos-de-reglas-de-validaci%C3%B3n bulk-upload=carga-masiva h_01J4HRXAH6DEXXQZZ3YAWHY4TP=carga-masiva h_01M22JGTYB4YJXBRVWB8RDBK86=nota h_01JWX0RVRCNAQ0SVRDMAJ5HPW1=nota-1 procedures=funciones-adicionales 01H8VFA2AF6M84FKKVDTCXJEFR=funciones-adicionales h_01JK5GDDGAZRKBVXZCCZ0RRB56=nota-2 how-tagged-mode-works=c%C3%B3mo-funciona-el-modo-tagged h_01KQERXDE5SPB182AFA2CM2C78=c%C3%B3mo-funciona-el-modo-tagged rule-outcome-configuration=configuraci%C3%B3n-del-resultado-de-la-regla h_01KQERXDE6668BR0EFDX9F5CYZ=configuraci%C3%B3n-del-resultado-de-la-regla what-to-expect-when-configuring-a-rule=qu%C3%A9-puedes-esperar-al-configurar-una-regla h_01KQERXDE9AM8TWAAQK6XHETSA=qu%C3%A9-puedes-esperar-al-configurar-una-regla example-match-logic=ejemplo-l%C3%B3gica-de-coincidencia h_01KQERXDEAQHC3SVFRT8V5X5S3=ejemplo-l%C3%B3gica-de-coincidencia example-do-not-match-logic=ejemplo-no-coincidir-con-la-l%C3%B3gica h_01KQERXDEA63J9ST9YSF27JKRD=ejemplo-no-coincidir-con-la-l%C3%B3gica set-a-rule-to-tagged-mode=configurar-una-regla-en-modo-tagged h_01KQERXDEBEKF59KBVYTBWS471=configurar-una-regla-en-modo-tagged analyze-tagged-data=analizar-datos-tagged h_01KQERXDEC1574K0V677N6ZGSY=analizar-datos-tagged change-a-tagged-rule-to-implemented=cambiar-una-regla-tagged-a-implemented h_01KQERXDEG3ZQPEYTSXAMMJNYC=cambiar-una-regla-tagged-a-implemented faq=preguntas-frecuentes 01H8VFA2AG5DW5Z9G9FPSWM464=preguntas-frecuentes h_01KHRB9CBYYPK73K7SVC3N4B6A=ejemplo-no-en-las-%C3%BAltimas h_01KHRB9CC3BBTC41SXC482S7EY=ejemplo-no-en-las-%C3%BAltimas-mayores h_01KHRB9CC6GJDNH97N0GSHDNKE=comprende-c%C3%B3mo-funciona-esta-condici%C3%B3n-con-varias-apps h_01M6BACJ5QD39N6V4G455EFA96=c%C3%B3mo-appsflyer-determina-la-versi%C3%B3n-m%C3%A1s-reciente h_01M6BACJ5QAZZNGT5MMGB9Q8WY=ejemplo-c%C3%A1lculo-de-la-versi%C3%B3n-m%C3%A1s-reciente" />
