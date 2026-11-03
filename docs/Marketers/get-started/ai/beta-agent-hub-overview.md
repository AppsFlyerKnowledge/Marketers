---
title: '[Beta] Descripción general del Agent Hub'
metadata:
  keywords:
    - Advertisers
    - Beta feature
    - Marketers
    - Agent Hub
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Agent Hub
  created_at: '2025-11-16T10:18:23Z'
  edited_at: '2026-10-27T03:37:20Z'
  id: 40967933109649
  locale: es
  section: AI
  section_id: 36348470056081
  url: https://support.appsflyer.com/hc/es/articles/40967933109649
---
<span class="af-tag af-tag--beta-feature">Beta feature</span>

> **At a glance:** Agent Hub es la plataforma centralizada de AppsFlyer para gestionar agentes impulsados por IA que ofrecen insights de marketing procesables de forma proactiva directamente en tu flujo de trabajo. Estos agentes analizan constantemente tus datos para ofrecer resultados valiosos y recomendar pasos procesables, todo ello dentro del entorno colaborativo de tu equipo.

<Embed title="[Beta] Descripción general del Agent Hub" typeOfEmbed="youtube" url="https://www.youtube.com/embed/LEuqdVEXBD0" providerUrl="https://www.youtube.com" />

## Sobre el Agent Hub

Cada agente se encarga de un trabajo de marketing de principio a fin: analiza tus datos, extrae sus conclusiones y las entrega allí donde trabaja tu equipo. Agent Hub te da acceso a una variedad de agentes creados por AppsFlyer, diseñados para ayudarte a optimizar la actividad de marketing y descubrir oportunidades de crecimiento, además de Custom Agent, que se encarga de un trabajo que tú mismo defines. Todos los agentes operan con integridad para respaldar la toma de decisiones de tu equipo.

## Página de Agent Hub

La página de Agent Hub se compone de dos pestañas: **Mis agentes** y **Actividad**. Use estas pestañas para administrar agentes y revisar las ejecuciones de agentes completadas.

Usa **Mis agentes** para configurar, implementar y gestionar agentes. Usa **Actividad** para revisar los resultados finalizados, ver ejecuciones anteriores, enviar comentarios y analizar el razonamiento de la ejecución con el Asistente de IA.

<Accordion title="Mis agentes">

La pestaña **Mis agentes** muestra los agentes disponibles para tu cuenta.

Utiliza esta pestaña para:

* Ver agentes disponibles.
* Configurar y desplegar agentes.
* Gestionar agentes desplegados.
* Supervisar el estado de ejecución más reciente desde la tarjeta de agente.

#### Requisitos previos y permisos

Algunas capacidades de Agent Hub requieren configuración adicional, dependiendo de los canales de notificación que utilice.

##### Slack (opcional)

La configuración de Slack solo es necesaria si deseas recibir los resultados de los agentes en Slack.

* Aprobación de la aplicación de Slack de AppsFlyer por parte de tu organización. Para hacerlo:
  * Ve a Agent Hub y selecciona el agente que deseas utilizar.
  * Haz clic en **Conectar con Slack** dentro de la tarjeta de configuración del agente.

Para los agentes que envían resultados a Slack, primero debes crear un canal de Slack exclusivo dentro de tu organización e invitar a la aplicación AppsFlyer Agent Hub Slack a ese canal antes de configurar el agente. El nombre del canal es necesario como parte de la configuración del agente.

Para invitar una aplicación a un canal:

1. En el canal de Slack en el que quieras recibir las notificaciones, escribe: **/invite**
2. Elige **Agregar aplicaciones a este canal.**

<Image alt="Opción 'Agregar aplicaciones a este canal' en el menú de detalles del canal de Slack" src="https://files.readme.io/6f4f06ff2a6871c38ab74347b05356b5482a859b3f40b02f01273abd3a10ee84-40967906089745.png" width="624px" />

Selecciona **AppsFlyer Agent Hub** -> **Agregar.**

<Image alt="Aplicación AppsFlyer Agent Hub seleccionada en el directorio de aplicaciones de Slack con el botón Agregar" src="https://files.readme.io/6290174c2950340f7766abb94f0080dbbcbd954cc44896a0f0ec1155fdd00524-40967906092049.png" width="624px" />

* Los siguientes roles tienen acceso completo automático:
  * Administrador
  * Gerente de marketing
  * Administrador de equipo
  * Responsable de marketing

* **Otros roles:** Requieren que la funcionalidad de herramientas de IA esté habilitada a través de <Anchor target="_blank" href="/marketers/es/docs/user-management">Gestión de usuarios</Anchor>.

##### Correo electrónico (opcional)

* Los correos electrónicos solo pueden enviarse a direcciones asociadas a una cuenta de AppsFlyer.
* Los usuarios deben estar suscritos a la lista de correo de AppsFlyer. <Anchor target="_blank" href="/marketers/es/docs/notifications#qué-notificaciones-puedo-recibir">Consulta aquí para más información</Anchor>.

Nota: En cada agente, puedes configurar hasta 5 direcciones de correo electrónico.

#### Configurar un agente

Los agentes pueden configurarse e implementarse para ejecutarse según una programación o de forma manual. También puedes configurar dónde se entregan los resultados del agente, como Slack o correo electrónico.

Puedes supervisar el estado de la última ejecución directamente desde la tarjeta del agente en la pestaña **Mis agentes**. Para ver resultados completados y ejecuciones históricas, haz clic en la pestaña **Actividad**.

Sigue los pasos a continuación para configurar e implementar un agente.

1. Inicia sesión en AppsFlyer.
2. En el menú de la izquierda, ve a **Agent Hub.**
3. En el agente que deseas configurar e implementar, haz clic en **Implementar**.
4. En la siguiente página, realiza la configuración requerida del agente.
5. Agrega tu dirección de correo electrónico o conecta tu espacio de trabajo de Slack si corresponde.
   1. Asegúrate de que el canal de Slack haya sido configurado. [Ver requisitos previos](#requisitos-previos-y-permisos).
6. Selecciona un horario de ejecución (actualmente basado en UTC; pronto se agregarán zonas horarias adicionales).
7. Haz clic en **Desplegar agente**.

El agente aparece en **Mis agentes**. Consulta **Agentes predefinidos** y **agente personalizado** más abajo para ver la lista completa de agentes disponibles y qué hace cada uno.

</Accordion>

<Accordion title="Pestaña de actividad">

La pestaña **Actividad** muestra los resultados de las ejecuciones completadas de los agentes. Aparece cuando tu cuenta tiene al menos un agente con resultados completados.

Utiliza esta pestaña para revisar la actividad reciente de los agentes, ver resultados anteriores, proporcionar feedback y hacer preguntas al asistente de IA sobre una ejecución específica.

La pestaña actividad incluye dos secciones:

| Sección | Descripción |
| --- | --- |
| Actividad reciente | Muestra la ejecución completada más reciente de cada instancia de agente. |
| Ejecuciones anteriores | Muestra las ejecuciones completadas de los últimos 30 días. |

Puedes filtrar la actividad por:

* Aplicación
* Instancia de agente

Nota: El filtro de agentes se basa en la instancia específica del agente, no en el tipo de agente.

#### Ver resultados de actividad

Para ver los resultados de actividad:

1. Ve a **Agent Hub**.
2. Haz clic en la pestaña **Actividad**.
3. Selecciona los filtros de app o instancia de agente correspondientes.
4. Haz clic en una ejecución para expandirla.

La ejecución expandida muestra el mismo resultado enviado por Slack o correo electrónico.

Desde la ejecución expandida, puedes:

* Copiar el resultado.
* Proporcionar feedback positivo o negativo.
* Añadir comentarios por escrito.
* Haz clic en **Analizar actividad** para hacer preguntas al Asistente de IA sobre la ejecución.

#### Analizar la actividad con el asistente de IA

Utiliza **Analizar actividad** para hacer preguntas al Asistente de IA sobre una ejecución del agente completada específica.

**Analizar actividad** está disponible para todos los agentes. El asistente de IA se abre dentro del contexto de la ejecución seleccionada. Puede ayudarte a comprender cómo el agente llegó a sus resultados, qué datos utilizó y qué factores consideró o descartó.

Esto no es un chat general con el agente. Asistente de IA responde únicamente preguntas sobre la ejecución seleccionada. No realiza nuevos trabajos del agente, no accede a datos fuera de la ejecución ni hace predicciones.

Para hacer preguntas al asistente de IA sobre una ejecución:

1. Ve a **Agent Hub**.
2. Haz clic en la pestaña **Actividad**.
3. Haz clic en una ejecución para expandirla.
4. Haz clic en **Analizar actividad**.
5. Selecciona una pregunta sugerida o ingresa tu propia pregunta.

Por ejemplo, puedes preguntar:

* Explícame tu razonamiento paso a paso.
* ¿En qué datos se basó esto?
* ¿Por qué se priorizó este hallazgo?
* ¿Qué factores consideró el agente?
* ¿Qué factores descartó el agente?

##### Preguntas compatibles y no compatibles

| Puedes preguntar sobre | No puedes preguntar sobre |
| --- | --- |
| Cómo llegó el agente a sus resultados | Datos que no se incluyeron en la ejecución |
| Qué datos utilizó el agente para la ejecución | Nuevos análisis que no formaron parte de la ejecución |
| Por qué ciertos hallazgos fueron priorizados o descartados | Predicciones futuras |
| El contexto y razonamiento de la ejecución seleccionada | Recomendaciones generales de optimización fuera del contexto de la ejecución |

#### Notas

Ten en cuenta lo siguiente al utilizar la pestaña **Actividad** y **Analizar actividad**:

* El asistente de IA debe estar habilitado para la cuenta. Si el asistente de IA está deshabilitado, **Analizar actividad** no estará disponible. Consulta <Anchor target="_blank" href="/marketers/es/docs/account-settings#hub-de-agentes">Configuración de la cuenta</Anchor>.
* El historial de actividad incluye únicamente ejecuciones completadas de los últimos 30 días.
* Eliminar un agente también elimina su actividad anterior, incluidos resultados, hallazgos y datos de razonamiento. Esta acción no se puede deshacer.
* Asistente de IA responde únicamente preguntas sobre la ejecución seleccionada. No realiza nuevos análisis, no accede a datos fuera de la ejecución ni realiza predicciones.

</Accordion>

## Tipos de agentes

Agent Hub incluye dos tipos de agentes: Custom Agent, que configuras tú mismo para un trabajo que defines, y agentes listos para usar, que implementas tal como están.

<div id="h_01M3PDTFQDFQNMHTWKP23JV1A8" />

<Accordion title="[Beta cerrada] Agente personalizado">

Mientras que los agentes listos para usar de Agent Hub realizan tareas específicas y predefinidas, Custom Agent ejecuta un trabajo que adaptas a tus necesidades concretas. Describe la tarea en lenguaje sencillo, elige la aplicación, revisa el plan que redacta el agente y decide cómo y cuándo quieres recibir los resultados. Después, el agente hace el trabajo de principio a fin, bajo demanda o según una programación, y te envía el resultado.

Analiza los datos, ejecuta la tarea especificada y entrega los resultados solicitados. Puede ser una lista clasificada, un resumen semanal de performance, una investigación de la causa raíz, una recomendación con las pruebas que la respaldan o un análisis ad hoc complejo. El resultado adopta la forma que necesite el trabajo.

Le das instrucciones igual que se las darías a un analista de tu equipo, y funciona del mismo modo: confirma lo que ha entendido, te muestra cómo piensa abordar el trabajo y cómo define cada término, y solo se ejecuta cuando das tu visto bueno.

#### Crear un agente personalizado

Tres pasos: define el agente, revisa el plan y luego configura e implementa.

##### Paso 1: Define el agente

1. En AppsFlyer, ve a **Agent Hub** en el menú de la izquierda.
2. En la tarjeta Agente personalizado, haz clic en **Crear**.
3. En **Selecciona tu aplicación**, selecciona la aplicación. Una aplicación por agente.
4. (Opcional) Configura los filtros de **Geolocalización** y **Fuente de medios**. Déjalos vacíos para incluirlo todo.
5. En **Tarea**, describe el trabajo o haz clic en un prompt listo para usar y edítalo según tus necesidades.
6. Haz clic en **Generar plan**.

##### Paso 2: Revisa el plan del agente

El agente convierte tu tarea en un plan y te lo muestra antes de ejecutar nada. Aquí es donde detectas si la tarea se ha interpretado mal o si hay una definición que no encaja con cómo mide tu equipo.

| Sección del plan | Qué comprobar |
| --- | --- |
| Meta | Reformulación en una sola línea del trabajo. |
| Plan del agente | Cómo llevará a cabo el agente la tarea. |
| Definiciones | Todas las métricas, ventanas y umbrales de tu tarea, detallados: qué significa «retención del día 7», qué significa «descenso significativo» y qué fuentes de medios están dentro del alcance. Edita cualquier cosa que difiera de tus propias definiciones. |
| Filtros | La aplicación, la geolocalización y la fuente de medios a la que se aplicará el agente. |

Desde aquí:

* **Editar**: modifica cualquier campo y, después, **Guardar cambios**.
* **Empezar de nuevo** te devuelve a la tarea.
* **Aceptar plan** te permite continuar.

##### Paso 3: Configura y despliega

1. Introduce un **nombre de agente**.
2. En **Selecciona cómo quieres recibir los resultados**, selecciona **Slack**, **correo electrónico** o ambas opciones.
   * Slack: haz clic en **Conectar con Slack** si el espacio de trabajo aún no está conectado y, después, selecciona el canal.
   * Correo electrónico: hasta cinco direcciones de usuarios de AppsFlyer.
3. En **Programación de ejecución**, selecciona una de las opciones.
4. Haz clic en **Desplegar agente**.

Las programaciones se ejecutan en UTC.

El agente aparece en **Mis agentes**. La tarjeta muestra el estado de la última ejecución. Las ejecuciones completadas están en **actividad** y se pueden filtrar por aplicación y nombre del agente.

<div id="h_01M3PDTFQESQY349XK0SNH5NB8" />

<Accordion title="Con qué datos trabaja el agente personalizado">

El agente personalizado tiene dos fuentes de datos, datos a nivel de evento y datos agregados, y elige entre ellas según la tarea; no necesitas especificarlo. Para algunas tareas, el agente usa ambas fuentes en una sola ejecución. En esos casos poco frecuentes, la misma métrica puede mostrar valores ligeramente diferentes entre las dos partes de una ejecución. Para entender qué fuente usó el agente durante una ejecución, explora el razonamiento del agente con la función **Analyze activity**.

**Datos a nivel de evento.** Eventos sin procesar en todo el funnel, desde el engagement hasta la actividad in-app. Esto es lo que hace que el agente personalizado sea diferente de un dashboard: puedes definir tus propias métricas y ratios, trabajar a nivel de usuario individual y rastrear secuencias de eventos.

| Incluidos | Detalles |
| --- | --- |
| Engagements | Clics e impresiones |
| Instalaciones y re-engagement | Conversiones |
| Sesiones | Eventos de apertura de la aplicación |
| Eventos dentro de la app | Incluidos los ingresos por compras in-app |
| Dimensiones | Fuente de medios, campaña, geolocalización hasta el nivel de ciudad, dispositivo, versión del sistema operativo, versión de la aplicación, anuncio, ID del sitio y otros campos de eventos sin procesar |
| Periodo de tiempo de los datos | Últimos 30 días |

**Datos de actividad y cohorte (agregados).** Todos los puntos de datos disponibles en My Dashboards, incluidos los costos.

| Incluidos | Detalles |
| --- | --- |
| Métricas | Instalaciones, conversiones, primeras visitas, sesiones, recuento de eventos, usuarios únicos, usuarios activos, ingresos, ingresos netos, ingresos medios por usuario (ARPU), ingresos por usuario único, recuento por usuario único, tasa de retención |
| Eventos in-app, conversiones, desinstalaciones, sesiones | Recuento, usuarios únicos, ingresos, ingresos netos, recuento del primer evento |
| Métricas de costos | Gasto (costo), eCPI, ROAS, ROI |
| Dimensiones | Fuente de medios, canal, ID y nombre de la campaña, ID y nombre del conjunto de anuncios, ID y nombre del anuncio, ID del sitio, agencia, palabras clave, sub\_param\_1, categoría y tipo de engagement y destino, App ID unificado, plataforma, tienda de aplicaciones de instalación, versión de la aplicación y versión del sistema operativo y código de país (conversión), tipo de evento agregado (conversión, sesión, in-app, desinstalación), nombre y tipo de conversión, tipo de monetización, is-attributed, is-organic, is-primary-attribution, fecha del evento (solo cohorte), fecha del evento (conversión), días posteriores a la conversión, moneda del cliente |
| Periodo de tiempo de los datos | Tres años para la actividad y dos años para la cohorte |

Los datos agregados están en USD y en la moneda de tu cuenta. Los datos agregados por cohorte tienen granularidad diaria.

**Limitaciones actuales.** Estas limitaciones son temporales y evolucionarán a medida que el agente personalizado deje la beta.

* El engagement y el costo están en fuentes distintas. Los clics y las impresiones solo existen en los datos a nivel de evento; el costo solo existe en los datos agregados. El agente no puede unir ambos, así que las métricas que los combinan, como CPC, CPM, CTR, IPM y CPA, no devuelven resultados. Las métricas basadas en costo que no necesitan datos de engagement (gasto, eCPI, ROAS, ROI) funcionan según lo esperado.
* Datos faltantes: datos generados por audiencias, SKAdNetwork, SSOT, Protect360, creatividades e incrementalidad; ingresos por anuncios e ingresos por suscripciones (los ingresos cubren solo las compras in-app).
* Las métricas o dimensiones personalizadas que has definido en tus dashboards no se incluyen.
* Las dimensiones agregadas incluyen datos solo a partir de junio de 2025 para plataforma, sub\_param\_1, destino de engagement, tipo de engagement y fuente (orgánico frente a no orgánico).
* Cuando no hay datos, el agente muestra 0, no N/A.
* "Primeras visitas" y "re-visitas" están disponibles solo para aplicaciones web.

> 📘 **Nota**
>
> Puede haber discrepancias entre las cifras de eventos sin procesar y los datos del dashboard. Las cifras a nivel de evento (raw data) y las cifras agregadas (dashboard) no siempre coincidirán; es normal que haya pequeñas diferencias entre ambas. Las cifras agregadas deberían coincidir con My Dashboards para la misma app y las mismas fechas.

</Accordion>

<div id="h_01M3PDTFQEF8ZPV4PP04YGNGBK" />

<Accordion title="Escribe una buena tarea">

La calidad del plan que redacta el agente depende de la calidad del briefing. Incluye todo lo que corresponda de esto:

1. **La tarea.** Qué quieres que se haga, en lenguaje claro. Los verbos ayudan: comparar, clasificar, señalar, encontrar, recomendar, resumir.
2. **Periodo de tiempo.** Una ventana definida, por ejemplo, "la última semana completa" o "los últimos 14 días frente a los 14 anteriores". Deja fuera el día de hoy; sus datos aún son parciales.
3. **Alcance.** La geolocalización, la fuente de medios, la campaña o la plataforma que importa. También puedes establecer la geolocalización y la fuente de medios como filtros encima del cuadro de tarea.
4. **Métricas y umbrales.** Indica tus KPI y cómo los defines. «Una caída de más del 10% frente a la semana anterior se considera significativa» le da al agente una regla que puede aplicar.
5. **Salida que quieres.** Si importa, indícalo: «una tabla ordenada por gasto», «un resumen breve con los tres hallazgos principales» o «solo marcar, sin explicación».
6. **Por qué.** Una línea de contexto ayuda al agente a decidir qué priorizar.

Consulta **Requisitos previos y permisos** más arriba para ver los detalles de configuración.

</Accordion>

<div id="h_01M3PDTFQE6GP95M541FYHG15N" />

<Accordion title="Revisar y perfeccionar una ejecución">

Las ejecuciones completadas aparecen en **actividad** con el mismo contenido enviado a Slack o por correo electrónico. Desde una ejecución, puedes copiar la salida, dar un pulgar arriba o abajo, añadir comentarios por escrito y abrir [Analizar actividad](#analizar-la-actividad-con-el-asistente-de-ia) para preguntar al Asistente de IA cómo llegó el agente a su resultado.

Si una ejecución vuelve vacía o no cumple el objetivo, lee el razonamiento antes de cambiar la tarea. En [Analizar actividad](#analizar-la-actividad-con-el-asistente-de-ia), pregunta qué datos ha usado el agente, por qué ha llegado a ese resultado y qué debes cambiar en el plan. Reescribir la tarea a ciegas suele dar una respuesta distinta, pero igual de incorrecta. Después, edita el plan o la tarea y vuelve a ejecutar el agente.

Si el razonamiento también vuelve vacío, es posible que hayas solicitado datos que todavía no existen. Consulta **Limitaciones** más arriba, revisa el prompt y vuelve a intentarlo.

> 📘 **Nota**
>
> No puedes volver a tu prompt original una vez que guardas y despliegas un agente. Solo puedes editar el plan del agente aprobado.

Consulta la [página de Agent Hub](#página-de-agent-hub) y [Analizar actividad con Asistente de IA](#analizar-la-actividad-con-el-asistente-de-ia) más arriba para obtener más información.

</Accordion>

<div id="h_01M3PDTFQE2XA949N4GPBSHVKY" />

<Accordion title="Gestionar un agente personalizado">

Desde la tarjeta del agente, en **Mis agentes**, puedes ejecutar el agente ahora, editar su configuración (nombre, entrega, programación) o eliminarlo.

Eliminar un agente también elimina su historial, incluidas las salidas y el razonamiento. Esta acción no se puede deshacer.

</Accordion>

<div id="h_01M3PDTFQEENY4TB2QY7M1MPN9" />

<Accordion title="Información útil">

* Una aplicación por agente. Crea un agente distinto para cada aplicación.
* Actividad conserva las ejecuciones de los últimos 30 días.

</Accordion>

</Accordion>

<div id="h_01M3PDTFQEDCZ7AJFC1FCTHERZ" />

<Accordion title="Agentes listos para usar">

Los agentes listos para usar están preparados para implementarse tal cual: elige uno, configúralo y deja que se ejecute con tus datos. La siguiente tabla muestra de un vistazo lo que hace cada agente. Despliega una sección para ver todos los detalles antes de implementar el agente.

<div id="h_01M3PDTFQET68PRA9CN49CQ8Q7" />

<Accordion title="Descubre oportunidades creativas">

**Función.** Encuentra los creativos que mejor rinden para ti y te dice dónde todavía no están en funcionamiento. El agente evalúa el rendimiento de los creativos en todos tus partners durante los últimos 30 días, clasifica a los ganadores y luego revisa cada partner para ver cuáles de esos ganadores faltan. Recibes una lista de placements concretos para añadir, con las cifras de cada uno.

**En qué funciona.** Gasto y ROAS a nivel de creativo en todos los partners durante los últimos 30 días. Requiere Optimización creativa.

**Qué ofrece una ejecución.** Los creativos con mejor rendimiento, con su gasto y ROAS, además de, para cada partner, cuáles de estos creativos no están actualmente en funcionamiento y el caso para añadirlos. Se envía por Slack o correo electrónico.

**Frecuencia.** Configurable mediante las opciones de programación estándar o bajo demanda.

</Accordion>

<div id="h_01M3PDTFQE2WB2SNWBCS81C2DE" />

<Accordion title="Resúmenes ejecutivos personalizados">

**Función.** Redacta la actualización de rendimiento que, de otro modo, tendrías que preparar a mano para managers y stakeholders. El agente lee tus datos de análisis agregados, identifica las tendencias, a los que mejor rinden y los cambios que importan para el periodo, y los convierte en un resumen con recomendaciones, listo para reenviar.

**En qué funciona.** Datos de análisis agregados de todas tus aplicaciones y fuentes de medios. No se requiere suscripción premium.

**Qué ofrece una ejecución.** Un resumen por escrito: tendencias principales, los que mejor y peor rinden, cambios destacados y próximos pasos recomendados. Se envía por Slack o correo electrónico.

**Frecuencia.** Configurable mediante las opciones de programación estándar o bajo demanda.

</Accordion>

<div id="h_01M3PDTFQEB9MKH44X5XX4AGDT" />

<Accordion title="Análisis de investigación profunda">

**Función.** Ejecuta una investigación semanal sobre qué cambió y por qué. Cada lunes, el agente compara las dos semanas completas más recientes (de lunes a domingo) y analiza los datos sin procesar a nivel de evento, en todos los partners, geolocalizaciones, versiones de SO y versiones de SDK, para detectar cambios que los dashboard agregados no pueden mostrar, incluidos problemas de configuración que parecen cambios de rendimiento.

**En qué funciona.** Datos sin procesar, consolidados, a nivel de evento. El agente excluye deliberadamente la semana actual para evitar datos parciales o aún no consolidados. Por ejemplo, el lunes 26 de enero compara del 12 al 18 de enero con del 5 al 11 de enero. No se requiere suscripción premium.

**Qué ofrece cada ejecución.** Un reporte escrito de los cambios relevantes de una semana a otra, qué los impulsa y qué problemas de configuración se detectan por el camino. Se entrega por Slack o correo electrónico.

**Frecuencia.** Semanalmente, los lunes o bajo demanda.

</Accordion>

<div id="h_01M3PDTFQEPFMS38RWXT923VX7" />

<Accordion title="Detectar anomalías de rendimiento">

**Función.** Supervisa tus KPI clave cada día y te avisa cuando algo cambia y no debería hacerlo. El agente compara cada métrica con su rango esperado, marca anomalías positivas o negativas significativas y explica qué ha cambiado y dónde: un pico de CPI en un partner, una caída del IPM en una geolocalización o una campaña que se ha desplomado.

**En qué funciona.** Datos diarios de KPI en partners, campañas y geolocalizaciones. No se requiere suscripción premium.

**Qué ofrece cada ejecución.** Alertas con formato narrativo: qué métrica se movió, cuánto, en qué partner, campaña o geolocalización, y cuál es el motivo más probable. Se entrega a través de Slack o por correo electrónico.

**Frecuencia.** Configurable mediante las opciones de programación estándar o bajo demanda.

</Accordion>

<div id="h_01M3PDTFQEFHYR29GN1XMRM16N" />

<Accordion title="Detectar problemas de configuración">

**Función.** Audita tu configuración de medición y te avisa de las carencias que deterioran silenciosamente la calidad de los datos. El agente comprueba si hay integraciones inactivas en SKAdNetwork y Costo, si la atribución view-through mediante modelado probabilístico está desactivada y otros problemas de configuración, para que los detectes antes de que distorsionen la lectura de una campaña.

**En qué funciona.** Estado de integración y configuración en tus aplicaciones y partners. No se requiere suscripción premium.

**Qué ofrece cada ejecución.** Alertas con cada incidencia detectada, dónde está y cómo solucionarla. Se entrega a través de Slack o por correo electrónico.

**Frecuencia.** Configurable mediante las opciones de programación estándar o bajo demanda.

</Accordion>

<div id="h_01M3PDTFQEP6E7D4TF5G4PX1KV" />

<Accordion title="Supervisar lanzamientos de aplicaciones">

**Tarea.** Te mantiene al día sobre los lanzamientos de tu propia aplicación sin esperar al equipo de desarrollo. El agente supervisa los lanzamientos en las tiendas de aplicaciones de iOS y Android, te avisa cuando una versión se publica, hace seguimiento del progreso del despliegue y destaca los cambios relevantes para marketing: nuevas funcionalidades, cambios en el comportamiento in-app y eventos añadidos o eliminados. Así puedes alinear las campañas de UA con lo que realmente hay en la aplicación.

**En qué funciona.** Datos de lanzamientos de tiendas de aplicaciones y definiciones de eventos in-app para tus aplicaciones. No se requiere suscripción premium.

**Qué ofrece cada ejecución.** Alertas de lanzamiento con la versión, el estado del despliegue y un resumen de los cambios relevantes para marketing. Se entrega por Slack o por correo electrónico.

**Frecuencia.** Configurable mediante las opciones de programación estándar o bajo demanda.

</Accordion>

<div id="h_01M3PDTFQEEKJQTRKEC9GK4TE6" />

<Accordion title="Optimiza la estrategia antifraude (Protect360)">

**Tarea.** Busca señales tempranas de fraude en tu tráfico y te indica qué hacer al respecto. El agente analiza tus datos de Protect360 en busca de patrones emergentes, reporta los hallazgos clave y recomienda acciones que reducen la exposición al fraude sin sacrificar el rendimiento.

**En qué funciona.** Datos de Protect 360. Requiere Protect360 y las funcionalidades de la beta cerrada de Protect360.

**Qué ofrece cada ejecución.** Hallazgos y recomendaciones en el dashboard de Protect360.

**Frecuencia.** Semanalmente, los lunes o bajo demanda.

</Accordion>

<div id="h_01M57AQ8G83P5H1JDJ4FM9ETCV" />

<Accordion title="Mide la incrementalidad de UA">

**Tarea.** El agente **Measure UA Incrementality** te guía a lo largo de todo el ciclo de vida de las pruebas de incrementalidad para que no tengas que ser un experto para ejecutarlas. Define qué probar, explica qué significan los resultados de tus experimentos y recomienda acciones de marketing concretas, convirtiendo una curva de aprendizaje pronunciada y especializada en un flujo de trabajo guiado orientado a medir el impacto causal de tu gasto en UA pagada: qué instalaciones o eventos se produjeron gracias a tus anuncios, frente al crecimiento que habrías capturado de todos modos.

**En qué se centra.** Instalaciones, eventos in-app, ingresos y datos de costo de los últimos 90 días; y todos los datos de experimentos de Incrementality for UA.

**Qué ofrece cada ejecución.** Un reporte estructurado en tres partes: (1) tu estado actual de UA y el análisis de cualquier experimento activo o completado, (2) un plan secuenciado de pruebas que define qué probar a continuación y por qué es importante para tu presupuesto, y (3) acciones de marketing recomendadas: crecer, mantener, recortar o volver a probar.

**Frecuencia.** Se ejecuta según una programación, semanal de forma predeterminada. Puedes aumentar la frecuencia hasta una vez al día o ejecutarlo ad hoc para obtener una lectura actualizada siempre que la necesites.

**Configuración.** Requiere una suscripción premium al producto Incrementalidad for UA. Inicia el agente desde Agent Hub y selecciona una aplicación, un país y una métrica de éxito; después, establece la frecuencia (o ejecútalo ad hoc). El agente hereda cualquier política de diseño de geolocalización existente de Incrementalidad for UA.

**Información útil.** El agente recomienda: nunca mueve presupuesto ni lanza un experimento por su cuenta; tú apruebas y actúas. Los agentes son específicos por aplicación, país y evento. Por ejemplo, tus aplicaciones de Android y iOS requerirían dos agentes distintos. Como con cualquier salida de IA, valida siempre antes de actuar.

</Accordion>

<div id="h_01M3PDTFQEP2RQW39AD8127J19" />

<Accordion title="Comprobación del estado de la web">

**Función.** Audita cómo tu aplicación web recopila eventos y atribuye conversiones a fuentes de marketing. El reporte muestra qué funciona, señala problemas que podrían hacer que la atribución sea inexacta y recomienda mejoras para tu implementación.

**En qué se centra.** La configuración de atribución de la aplicación web que hayas seleccionado y los datos recientes del SDK o de servidor a servidor. Las comprobaciones abarcan la recopilación de datos, los eventos y los ingresos, los enlaces de campaña, los referentes, la identidad y la configuración multiplataforma. La ventana de análisis predeterminada es de siete días.

**Qué ofrece cada ejecución.** Un reporte con dos secciones: qué se comprobó y está bien, y mejoras recomendadas. Los hallazgos incluyen cifras de soporte, una corrección recomendada y un estado verde, amarillo o rojo en función del impacto.

**Cadencia.** Configurable mediante las opciones de programación estándar o bajo demanda.

</Accordion>

<div id="h_01M5VP47MCYYQVP89CJN9KZ4BP" />

<Accordion title="[Beta cerrada] Optimiza la cuota de voz en Apple Ads">

**Trabajo.** Mantiene tu cuota de voz (SoV) en Apple Ads para tus palabras clave principales dentro del rango que defines, sin pagar de más. La SoV, también llamada cuota de impresiones, es el porcentaje de búsquedas aptas para una palabra clave en las que apareció tu anuncio. Cuando una palabra clave se sale del objetivo, el agente recomienda un cambio de puja: subir la puja máxima de coste por toque (CPT máx.) para recuperar cuota, o bajarla para dejar de pagar de más.

**Cómo comprueba el agente tu SoV.** Apple informa de la SoV con un día de retraso, pero la subasta cambia durante el día. Para cerrar esa brecha, el agente estima tu SoV cada hora a partir de los datos de entrega de hoy. Calibra la estimación con la SoV oficial de Apple del día anterior. Te enteras de los cambios en cuestión de horas.

**Con qué funciona.** Datos horarios de Apple Ads a nivel de palabra clave (impresiones, toques, gasto y puja CPT máx. actual) y el reporte diario de cuota de impresiones de Apple. El agente obtiene ambos a través de tu conexión de Apple Ads en **Configuración de costos** y usa los últimos 30 días como histórico. Requiere ROI360.

**Qué ofrece una ejecución.** Para cada palabra clave y geolocalización que quede fuera del rango objetivo, una ejecución ofrece:

* El rango de SoV más reciente de Apple y si la palabra clave está por encima o por debajo del objetivo.
* El cambio de puja recomendado en %.
* La puja CPT máx. exacta, actual y recomendada para cada campaña y grupo de anuncios en los que se ejecuta la palabra clave.

Las palabras clave que están dentro del objetivo o que aún no tienen recomendación se muestran al final. Se envía a Slack o por correo electrónico, y a la pestaña **Actividad**.

**Aplicar una recomendación.** En la pestaña **Actividad**, cada cambio de puja aparece como una tarjeta. Haz clic en **Aplicar** para enviar la puja recomendada a Apple Ads, edita la puja y luego haz clic en **Aplicar**, o haz clic en **Rechazar**. No cambia nada en Apple Ads hasta que aplicas una recomendación.

**Frecuencia.** Las opciones de programación de ejecución son:

* **Al activarse:** El agente envía un mensaje solo cuando hay una recomendación nueva o modificada. La frecuencia de comprobación depende de cómo el agente comprueba tu SoV. Consulta **Cómo comprueba el agente tu SoV** en esta sección.
* **Sin programación:** El agente se ejecuta solo cuando lo ejecutas manualmente.

**Configuración. Para desplegar el agente:**

1. En **Configuración de costos**, conecta Apple Ads con la cuenta que ejecuta tus palabras clave.

   > 📘 **Nota:**
   >
   > Conecta Apple Ads con permisos de **Read & Write** y con una cuenta que no sea de agencia. Read & Write te permite aplicar cambios de puja directamente desde Agent Hub. Con acceso de solo lectura, recibes recomendaciones, pero no puedes aplicarlas. Tienes que cambiar las pujas manualmente en Apple Ads.

2. En **Agent Hub**, en la tarjeta **Optimizar Share of Voice de Apple Ads**, haz clic en **Desplegar agente**.
3. Introduce un **nombre del agente** o conserva el nombre rellenado automáticamente.
4. En **Selecciona tu app de iOS**, selecciona la app. Una app por agente.
5. En **Palabras clave**, introduce al menos una y hasta tres palabras clave, tal como están configuradas en tus campañas de Apple Ads.
6. En **Geolocalización de Apple Ads**, selecciona hasta cinco geolocalizaciones.
7. En **Rango objetivo de Share of Voice**, selecciona el rango, por ejemplo, 81-90%.
8. En **Selecciona cómo quieres recibir los resultados**, elige **Slack**, **correo electrónico** o ambos.
9. En **Programación de ejecución**, selecciona **Al activarse** o **Sin programación**.
10. Haz clic en **Desplegar agente**.

**Aún no hay recomendaciones.** Una palabra clave y una geolocalización pueden mostrar este estado en dos casos:

* No hay suficientes datos. Por ejemplo, la palabra clave tiene un volumen de búsqueda bajo y Apple no genera un reporte de SoV para ella, o la palabra clave no está en funcionamiento en esta geolocalización.
* La puja ha cambiado hace poco. El agente espera a ver el efecto del cambio antes de volver a recomendar.

**Limitaciones.** Ten en cuenta estas limitaciones:

* **La primera ejecución es al día siguiente.** Después de implementar un agente nuevo, completa 30 días de historial a la mañana siguiente (UTC). El agente empieza a estar en funcionamiento solo después de que se complete el relleno de historial.
* **Conexión de Apple Ads.** La conexión de Apple Ads en **Configuración de costos** debe ser de una cuenta que no sea de agencia. Para aplicar cambios en las pujas, necesitas permisos de lectura & escritura.
* **No se admiten las pujas automáticas.** Si una campaña usa pujas automáticas en Apple Ads, sus palabras clave no tienen una puja CPT máxima manual. El agente no puede recomendar ni aplicar un cambio de puja para ellas.
* **Usa campañas de una sola geolocalización.** Apple Ads establece una puja por palabra clave y grupo de anuncios para todos los países a los que se dirige la campaña. Si una campaña se dirige a varios países, un cambio de puja para una geolocalización también lo cambia para las demás. Puede que la recomendación no sea precisa.
* **Alcance por agente.** Una aplicación, hasta tres palabras clave y hasta cinco geolocalizaciones. Crea más agentes si necesitas más palabras clave o geolocalizaciones.

**Conviene saberlo.** El agente nunca cambia una puja por sí solo. Apruebas cada cambio. Como con cualquier resultado de salida de la IA, valida las recomendaciones antes de aplicarlas.

</Accordion>

</Accordion>

<Accordion title="¿Puedo crear mis propios agentes?">

Sí. El agente personalizado te permite definir la tarea que quieres que se realice. Consulta **Agente personalizado** más arriba.

</Accordion>

<Accordion title="¿Agent Hub está disponible para todos los tipos de cuenta?">

N.º Actualmente, Agent Hub solo está disponible para anunciantes.

</Accordion>

<Accordion title="¿Todos los agentes están disponibles para todos?">

La disponibilidad de los agentes varía según la suscripción a AppsFlyer y el acceso a productos premium. Contacta con tu CSM para obtener detalles específicos.

</Accordion>

<Accordion title="¿Los administradores pueden deshabilitar Agent Hub para la cuenta?">

Sí. Los administradores pueden gestionar la disponibilidad de Agent Hub en **Configuración de la cuenta > Funciones de IA**.

De forma predeterminada, Agent Hub está disponible para la cuenta.

Si un administrador deshabilita Agent Hub:

* Todos los usuarios perderán acceso a Agent Hub.
* Todos los agentes existentes se eliminarán de forma permanente y no podrán restaurarse.
* Todas las ejecuciones activas de agentes se detendrán.

Si un administrador vuelve a habilitar Agent Hub más adelante, los usuarios podrán acceder nuevamente, pero deberán crear e implementar los agentes desde cero.

Consulta <Anchor target="_blank" href="/marketers/es/docs/account-settings#hub-de-agentes">Configuración de la cuenta</Anchor> para más información.

</Accordion>

<Accordion title="¿Dónde puedo recibir notificaciones?">

Puedes recibir notificaciones por correo electrónico o Slack. Las notificaciones por correo electrónico requieren que te registres en las notificaciones de capacidades de IA en el Centro de notificaciones.

</Accordion>

<Accordion title="¿Por qué no estoy recibiendo las notificaciones por correo electrónico de Agent Hub?">

Si completaste los requisitos previos para las notificaciones por correo electrónico pero aún no recibes correos de Agent Hub, es posible que anteriormente te hayas dado de baja de los correos electrónicos de AppsFlyer. Contacta al equipo de Soporte de AppsFlyer para obtener ayuda.

</Accordion>

<Accordion title="¿Usa AppsFlyer mis datos para entrenar modelos de IA?">

N.º AppsFlyer no usa tus datos para entrenar ningún modelo de IA. La IA puede producir resultados inexactos o incompletos, así que revisa las salidas antes de actuar en función de ellas.

</Accordion>

<div data-zendesk-anchors="about-agent-hub=sobre-el-agent-hub h_01KA62R2NX6YEFMVG0SN0Y7NQ9=sobre-el-agent-hub agent-hub-page=p%C3%A1gina-de-agent-hub h_01KQF6P3ED1KB47THJP8J3KAE5=p%C3%A1gina-de-agent-hub prerequisites-and-permissions=requisitos-previos-y-permisos h_01KQF8YAEDQW52YMK3W4FE2KE1=requisitos-previos-y-permisos h_01KQF8H9A6FPB3VVBWAAXM257W=slack-opcional h_01KQF8HEEMRBFK1K54VH2YDPSC=correo-electr%C3%B3nico-opcional set-up-an-agent=configurar-un-agente h_01KQF8T91KTZ01YKJD8JT6G0ZJ=configurar-un-agente view-activity-output=ver-resultados-de-actividad h_01KQF6P3EJMJDMF0BWWXQA091K=ver-resultados-de-actividad analyze-activity-with-ai-assistant=analizar-la-actividad-con-el-asistente-de-ia h_01KQF6P3EMCX0HQKPVQ89S9VGF=analizar-la-actividad-con-el-asistente-de-ia h_01KQF6P3EPWHV7J742F3S4Q0GY=preguntas-compatibles-y-no-compatibles notes=notas h_01KQF7NTQYDGA17KCCMTNYY72H=notas agent-types=tipos-de-agentes h_01M3PDTFQDAEVRHJYK4ZJXQ3DH=tipos-de-agentes create-a-custom-agent=crear-un-agente-personalizado h_01M3PDTFQEJA8GAE579P1AZG0E=crear-un-agente-personalizado step-1-define-the-agent=paso-1-define-el-agente h_01M3PDTFQECPBKDEXMQMPZJTCS=paso-1-define-el-agente step-2-review-the-agent-plan=paso-2-revisa-el-plan-del-agente h_01M3PDTFQEF9QCN15FKMRST3GW=paso-2-revisa-el-plan-del-agente step-3-configure-and-deploy=paso-3-configura-y-despliega h_01M3PDTFQE7FN9GPTJ5GEKSNVG=paso-3-configura-y-despliega h_01M3PDTFQEZJGPZ0AY4ZWRDR8D=nota h_01M3PDTFQENS64JZYT2Y56QMXQ=nota-1 h_01M5VP47MCS7HM339EW9AT6NGG=nota-2" />
