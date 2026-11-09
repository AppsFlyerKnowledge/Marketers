---
title: Integrar el SDK web de AppsFlyer
deprecated: false
hidden: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2026-09-15T09:07:44Z'
  edited_at: '2026-09-17T00:39:08Z'
  id: 50896216552337
  locale: es
  section: Web platform
  section_id: 50896333547281
  url: https://support.appsflyer.com/hc/es/articles/50896216552337
---
**Resumen:** Instala el SDK web de AppsFlyer (también conocido como el píxel) en tu sitio web para reportar las visitas y los eventos de los usuarios a AppsFlyer, y configura un Customer User ID (CUID) persistente para unificar recorridos entre plataformas.

<div id="overview" />

## Vista general

Web SDK te permite registrar cómo interactúan los visitantes con tu sitio web y envía esta información a AppsFlyer. Es un módulo complementario de 40–60 KB que reporta las visitas y acciones de los usuarios en tu sitio web a la plataforma AppsFlyer.

<div id="integrate-the-sdk-manually" />

### Integrar el SDK manualmente

 Sigue los pasos a continuación para completar la integración de Web SDK, desde la instalación hasta la validación y los controles de privacidad.

1. [Obtén tus claves.](#1-obtén-tus-claves) Obtén el Web SDK ID (también conocido como Web Dev Key).
2. [Selecciona un fragmento de código.](#2-selecciona-un-snippet-de-código) Elige el snippet que coincida con tu tipo de integración y requisitos de seguridad.
3. [Implementa el SDK web.](#3-implementar-el-snippet) Implementa el SDK utilizando un snippet nativo, Google Tag Manager o Adobe Launch Tag Manager.
4. [Asegúrate de que el SDK funcione correctamente.](#4-asegúrate-de-que-el-sdk-funcione-correctamente) Valida que el SDK envíe solicitudes verificando las llamadas de red en las herramientas para desarrolladores del navegador.
5. [Configura y registra eventos.](#5-configurar-y-registrar-eventos) Define y envía eventos personalizados al cargar la página o mediante la interacción del usuario utilizando JavaScript nativo o Google Tag Manager.
6. [Configura el Customer User ID.](#6-establecer-id-de-usuario-de-cliente) Configura un CUID persistente para unificar la actividad web con otras plataformas.
7. [Gestiona la privacidad.](#7-gestionar-la-privacidad) Controla la activación o desactivación de la medición y configura la seguridad y el filtrado de datos (Content Security Policy y descarte de parámetros de consulta).
8. [Referencia de cookies del SDK web.](#referencia-de-cookies-de-web-sdk) Revisa las cookies que Web SDK establece o utiliza, incluyendo su propósito, duración y alcance.

<div id="integrate-the-sdk-with-an-ai-coding-agent" />

#### Integrar el SDK con un agente de programación con IA

En lugar de integrar manualmente el SDK web (consulta los pasos a continuación), usa una herramienta de programación con IA (Cursor, Claude Code, Codex, Copilot) para implementar toda la integración por ti. Copia el prompt, sustituye los dos marcadores de posición y pégalo en tu herramienta de programación con IA.

Este enfoque agiliza el proceso y cubre todos los pasos a continuación, pero aun así debes asegurarte de que el SDK funcione correctamente y revisar la configuración de privacidad después.

Antes de copiar el prompt, sustituye:

* `<WEB_SDK_ID>`: En AppsFlyer, ve a **Configuración de la aplicación**, selecciona tu aplicación web (el dominio de tu sitio web con el prefijo "website-") y copia el **ID del SDK web** desde **Autenticación del SDK**.
* `<PRODUCTION_URL>`: La URL de tu sitio en producción, que se usa para la verificación posterior a la implementación.

> 📘 **Note**
>
> La herramienta de IA crea un plan de eventos a partir de tu base de código y espera tu aprobación antes de implementarlo. Revisa el plan, confirma que los valores de ingresos y moneda solo aparezcan en eventos de ingresos reales y verifica los resultados con los pasos de verificación posteriores a la implementación del prompt.

<Accordion title="Prompt de implementación con IA">

```markdown
# **AppsFlyer Web SDK - Prompt de implementación con IA**

Copia el prompt de abajo en una herramienta de programación con IA que pueda editar tu proyecto (Cursor, Claude Code, Codex, Copilot). Antes de copiarlo, sustituye dos marcadores de posición:

  - <WEB_SDK_ID> - en AppsFlyer, ve a Mis aplicaciones, selecciona tu aplicación web (tu dominio con el prefijo website-) y copia el ID del SDK web (también llamado Web Dev Key) desde Autenticación del SDK.
  - <PRODUCTION_URL> - la URL de tu sitio en producción, que se usa para la verificación posterior a la implementación.

Implementa el SDK web de AppsFlyer (píxel de atribución web) en este sitio web, incluidos los eventos que importan para mi medición de marketing.

Mi ID del SDK web: <WEB_SDK_ID>\n\nMi URL de producción: <PRODUCTION_URL>\n\n## Paso 0 - Bloqueo de configuración\n\nSi falta el ID del SDK web anterior o sigue siendo un marcador de posición, responde SOLO con una breve solicitud para que te lo proporcionen (en AppsFlyer: Mis aplicaciones > la aplicación con prefijo "website-" > autenticación del SDK > ID del SDK web) y detente. No escribas ningún código hasta que se te proporcione. Si falta la URL de producción, solicítala en la misma respuesta: es necesaria para la verificación posterior a la implementación.

Trabaja con cambios mínimos: deduce las rutas de los archivos a partir del repositorio, cambia solo lo que esta integración requiera y conserva los patrones existentes del proyecto.

## Paso 1 - Analiza primero el sitio

Antes de escribir código, revisa la base de código y crea tú mismo el plan de eventos; no me pidas que enumere los eventos:

1. Identifica el framework (HTML simple, React, Next.js, Vue, etc.) y dónde se controla el documento <head>.

2. Detecta las acciones de conversión en el código. Busca, por orden de fiabilidad:

   - Llamadas de analítica existentes: eventos de gtag()/GA4, Segment analytics.track(), fbq('track'), dataLayer.push (incluidos los objetos de eCommerce). Estas te indican tanto las acciones como dónde están ya los valores (importe, divisa, ID del pedido).

   - Lógica de comercio: módulos de checkout/carrito, páginas o rutas de confirmación de pedido y de agradecimiento, callbacks de pago correcto.

   - Lógica de autenticación: flujos de registro y login, y dónde pasa a estar disponible en el código del cliente el ID interno del usuario.

   - Formularios y CTA: formularios de lead, inicios de suscripción o prueba, descargas.

   - Productos sin comercio o de tipo herramienta: si el sitio no tiene flujos de compra, carrito, checkout, registro o login, no inventes eventos de comercio o autenticación. Identifica las acciones reales del producto (p. ej., generar, copiar, exportar, descargar, compartir, seleccionar una plantilla, editar parámetros) y asígnalas en su lugar a nombres de eventos personalizados y descriptivos.

3. Asigna cada acción detectada al nombre estándar de AppsFlyer:

   - pedido completado / "Order Completed" / purchase_success -> af_purchase (con eventRevenue)

   - signup / register / cuenta creada -> af_complete_registration

   - login / signin -> af_login

   - añadir al carrito / "Product Added" -> af_add_to_cart (af_price, sin eventRevenue)

   - iniciar checkout / "Checkout Started" -> af_initiated_checkout (af_price, sin eventRevenue)

   - visualización de producto o contenido -> af_content_view

   - suscripción iniciada -> af_subscribe; prueba gratuita iniciada -> af_start_trial

   - búsqueda -> af_search

   Cualquier elemento sin equivalente estándar mantiene un nombre personalizado descriptivo.

4. Para cada evento, identifica en el código la fuente exacta de: el importe realmente cobrado (para af_purchase), la divisa, el ID del pedido o la transacción y el ID del usuario. Reutiliza las mismas fuentes de datos de las que lee la analítica existente.

5. Comprueba si existe una plataforma de gestión del consentimiento (CMP), como OneTrust o Didomi. Marca también cualquier control de consentimiento desarrollado a medida o preferencia de privacidad que almacene el sitio, y pregúntame cómo debe condicionar la medición en lugar de decidirlo por tu cuenta.

Nota: la analítica existente sirve solo como entrada para el descubrimiento; implementa los eventos de AppsFlyer como llamadas directas a AF(), no reenviadas a través de Segment/GA4 con sus nombres.

Después, muéstrame el plan de eventos propuesto en una tabla (nombre del evento de AppsFlyer, activador + archivo, fuente de ingresos/af_price, fuente del ID de deduplicación) y espera mi aprobación antes de implementarlo. Marca cualquier evento en el que no hayas podido localizar la fuente del valor en lugar de hacer suposiciones.

## Paso 2 - Instala el fragmento del SDK

Añade este fragmento cerca de la parte superior del <head> en todas las páginas, con mi ID del SDK web:

<script>

!function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){

(t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},

t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,

o.src="https://websdk.appsflyer.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),

p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "<WEB_SDK_ID>"}})

</script>

Reglas estrictas:

- Usa el fragmento tal cual. NO lo reescribas como un componente personalizado ni como un módulo contenedor. Los SDK encapsulados pueden enviar eventos personalizados mientras que la visita automática (el evento LOAD del SDK) nunca se activa; entonces el sitio muestra cero visitas y no se puede atribuir nada.

- El SDK debe cargarse exactamente UNA vez por carga de página. En React/Next.js, protégete contra los re-renders y el doble montaje (p. ej., cárgalo en la plantilla HTML/documento raíz, no dentro de un componente que se vuelve a montar). Varias cargas pueden hacer que el SDK deje de funcionar.

- Si el sitio ya carga el SDK de AppsFlyer mediante un gestor de etiquetas (GTM), NO lo añadas también en el código: un cargador, no dos. Avísame si encuentras una etiqueta de AppsFlyer existente.

- NO implementes manualmente un evento de vista de página o un evento de visita. El SDK registra las visitas automáticamente al cargarse; un evento «page_view» hecho manualmente nunca contará como una visita.

- La clave de configuración es webAppId (no appId).

- Si el sitio aplica una Content Security Policy estricta con nonces, añade el nonce a la etiqueta del snippet inline Y asegúrate de que la política incluya 'strict-dynamic': el snippet inyecta el script del SDK de forma dinámica y, sin 'strict-dynamic', una política basada solo en nonce lo bloquea.

## Paso 3 - Implementa eventos

Formato de la llamada al evento:

AF('pba', 'event', {

  eventType: 'EVENT',            // siempre la string literal 'EVENT'

  eventName: 'af_purchase',

  eventRevenue: 49.99,           // nivel superior: solo en ingresos realizados

  eventRevenueCurrency: 'USD',   // nivel superior: código ISO de 3 letras; el valor predeterminado es USD si se omite

  eventValue: {                  // metadatos JSON, máximo 1000 caracteres

    "af_order_id": "TXN-12345",

    "af_customer_event_id": "evt-abc-001"

  }

});

Reglas de eventos: síguelas exactamente:

1. Usa los nombres de eventos estándar de AppsFlyer para que los reportes y funnels multiplataforma estén alineados: af_purchase, af_complete_registration, af_login, af_add_to_cart, af_initiated_checkout, af_content_view, af_subscribe. Si existe una aplicación móvil, usa los MISMOS nombres de eventos que en el SDK móvil. No añadas nunca sufijos de plataforma como «_web».

   Excepción: líneas de compra diferenciadas. Si el sitio vende claramente niveles o categorías de producto distintos que necesitan desgloses separados en el dashboard (p. ej., dos productos de suscripción), propón nombres divididos en el plan de eventos (af_purchase_<tier>) en lugar de un único evento genérico, e indica el motivo. La segmentación solo mediante eventValue no se muestra en las vistas estándar del dashboard. Nunca envíes TANTO un evento de nivel como un evento genérico para la misma compra, porque eso duplica los datos.

2. Los ingresos van SOLO en el campo eventRevenue de nivel superior, y SOLO en los eventos en los que realmente hubo movimiento de dinero (compra completada, suscripción completada, reserva confirmada). Los valores dentro de eventValue (af_revenue, revenue, price, amount, total) NUNCA se contabilizan como ingresos; poner los ingresos ahí es el error de implementación n.º 1 y da como resultado 0 $ de ingresos en cada compra.

3. Envía siempre eventRevenueCurrency junto con eventRevenue cuando la moneda no sea USD; de lo contrario, todos los importes se registrarán como USD.

4. Envía el importe real de la transacción individual como un número sin formato: sin símbolos de moneda, sin céntimos como unidades, sin duplicar el total del carrito más el artículo, y sin valor de vida útil.

5. Para valores monetarios que NO sean ingresos realizados (valor de añadir al carrito, valor de inicio de checkout, precio consultado), NO configures eventRevenue. Pon el importe en "af_price" y la moneda en "af_currency" dentro de eventValue. Enviar eventRevenue tanto en af_initiated_checkout como en af_purchase hace que los ingresos se contabilicen dos veces.

6. En las compras, incluye "af_order_id" (el ID de la transacción) dentro de eventValue. Si la base de código no tiene un ID de transacción real en ese punto, indícalo en el plan de eventos en lugar de sustituirlo por un marcador de posición.

7. Incluye un "af_customer_event_id" único dentro de eventValue en cada evento de conversión. El mismo nombre de evento no debe activarse nunca dos veces con el mismo ID: genéralo por acción y evita que los nuevos renderizados de la SPA disparen el controlador dos veces. Esto también deduplica frente a cualquier flujo del servidor (S2S) que envíe las mismas conversiones.

8. Un evento por acción del usuario. No emitas dos nombres para la misma acción y no retransmitas la misma acción a través de AppsFlyer y de una capa de reenvío con nombres distintos.

9. Para carritos con varios artículos, añade un array "af_order_info" dentro de eventValue: un objeto por artículo con las claves sku, ingresos (precio por unidad), qty, content_name, content_type, content_category, content_category y marca. En una compra, eventRevenue de nivel superior sigue llevando el total del pedido.

10. Los eventos deben activarse después de que el fragmento del SDK se haya cargado en la página. En las conversiones que terminan en una página de confirmación o de agradecimiento, activa el evento cuando cargue esa página; en las acciones dentro de la página (clics en botones en una SPA), actívalo desde el controlador de la acción.

11. Payloads mínimos: omite los campos irrelevantes:

    - NO incluyas eventRevenue ni eventRevenueCurrency a menos que realmente haya habido movimiento de dinero en ese evento. No envíes nunca eventRevenue: 0 ni una moneda predeterminada «por si acaso».

    - NO incluyas eventCategory, eventLabel ni ningún campo de estilo GA/Segment. No forman parte de la API de eventos del SDK web de AppsFlyer.

    - Dentro de eventValue, omite las claves cuyos valores sean una string vacía, null, undefined o false (a menos que false en sí mismo sea significativo para esa propiedad).

    - Si un parámetro no es relevante para un evento concreto, no lo incluyas en el payload en absoluto. Prefiere un objeto mínimo con solo los campos que apliquen.

    - Las columnas vacías de ingresos/moneda en los reportes de AppsFlyer no significan que el cliente deba enviar ceros ni valores predeterminados; deja esos campos sin incluir.

## Paso 4 - Configura el Customer User ID (CUID)

Justo después de que un usuario inicie sesión o se registre (y en las cargas de página en las que el usuario ya esté autenticado), llama a:

AF('pba', 'setCustomerUserId', '<el ID interno del usuario, como string>');

Reglas:

- Usa el MISMO identificador que las aplicaciones móviles pasan a setCustomerUserId, si existen aplicaciones móviles; esto es lo que une el recorrido de un usuario entre la web y el móvil.

- Usa un ID interno opaco. Nunca una dirección de correo electrónico, un número de teléfono ni otros datos personales identificables.

- Llámalo lo antes posible; los eventos que se disparen antes no llevarán el CUID.

- setCustomerUserId por sí solo no crea un evento que se pueda reportar. Dispara también af_complete_registration al registrarse y af_login al iniciar sesión, después de establecer el CUID, para que esos eventos lo incluyan.

## Paso 5 - Consentimiento (solo si existe una CMP)

Si el sitio tiene una plataforma de gestión del consentimiento:

- Inicializa el SDK con la medición desactivada: {pba: {webAppId: "<WEB_SDK_ID>", measurementStatus: false}}

- Cuando se otorgue el consentimiento: window.AF_SDK.PLUGINS.PBA.enableMeasurement()

- Cuando se revoque el consentimiento: window.AF_SDK.PLUGINS.PBA.disableMeasurement()

Notas:

- Estos métodos del plugin solo existen una vez que el script del SDK ha terminado de cargarse, a diferencia de AF(), que es un stub de encolado disponible de inmediato. Respeta ese orden.

- Si la medición empieza desactivada, no se registra ninguna visita hasta que se otorgue el consentimiento. Aclara explícitamente esa compensación antes de implementarla.

Si no hay ninguna CMP, usa el snippet simple (la medición está activada por defecto).

## Paso 6 - Verifica

### 6a. Verificación local (durante la implementación)

Ejecuta el proyecto, automatiza un navegador (Playwright/Puppeteer o una herramienta de navegador, si tienes una) y captura TANTO el payload de la solicitud COMO el estado de respuesta HTTP de cada llamada a dominios de AppsFlyer. Comprueba lo siguiente:

- La solicitud del cargador del SDK devuelve 200 y se dispara exactamente una vez por carga de página (navega entre páginas y vuelve a renderizar componentes para demostrar que no hay doble carga).

- Se dispara una solicitud en la carga de página con eventType "LOAD" y un afWebUserId rellenado, y su respuesta es 2xx; esta es la visita; sin ella no habrá atribución.

- Cada conversión implementada produce exactamente una solicitud de evento, cada una con respuesta 2xx, con eventRevenue y eventRevenueCurrency en el nivel superior en las compras, y con af_customer_event_id presente y único.

- Después de un login simulado, las solicitudes posteriores llevan el ID de usuario del cliente.

Una solicitud capturada NO es prueba de éxito. Un evento cuya respuesta sea 4xx se rechazó y nunca aparecerá en los reportes. Indica el código de estado de cada evento que dispares y nunca describas un evento como verificado sin él.

Si no puedes ejecutar un navegador, verifica estáticamente: el snippet tiene un único punto de inserción que no puede montarse dos veces; cada controlador de eventos se dispara exactamente una vez por acción; los ingresos y la moneda son campos de nivel superior; se puede acceder a setCustomerUserId en todas las rutas de entrada autenticadas. Indica claramente que no se pudo observar ningún estado de respuesta.

### 6b. Verificación posterior al despliegue en el dominio real (obligatoria)

Las ejecuciones locales demuestran la ruta del código, no la página de producción. Los pipelines de compilación y los procesadores de recursos pueden eliminar, aplazar o reubicar scripts inline, así que no basta con comprobar el archivo de origen. Después del despliegue:

- Obtén la URL de producción y confirma que el fragmento esté presente en el HTML SERVIDO.

- Carga la página de producción en un navegador y repite en ella todas las comprobaciones del punto 6a.

- Confirma que el parámetro de consulta af_id de las solicitudes salientes lleve exactamente el ID del SDK web: un ID incorrecto o truncado significa que los eventos se envían con un ID que no existe en mi cuenta y no llegan a ninguna parte sin mostrar ningún error.

- Usa un ID de usuario de cliente dedicado para QA (por ejemplo, qa_<yyyymmdd>_01) para que luego la ejecución se pueda aislar en raw data.

Si aún no he desplegado, indícame que el punto 6b sigue pendiente y dame los comandos exactos y las comprobaciones que debo ejecutar cuando lo haya hecho.

### 6c. Registro de QA

Genera una tabla de la ejecución de verificación para que luego se puedan cotejar las filas en raw data de AppsFlyer, con una línea por evento: timestamp UTC, nombre del evento, CUID, af_order_id, af_customer_event_id, estado HTTP. Indica la hora de inicio y de fin en UTC de toda la ejecución, y la hora en UTC del despliegue si la conoces.

## Paso 7 - Volver a consultar los datos

Incluye en el reporte una guía explícita para confirmar los eventos en AppsFlyer, porque las visitas y las conversiones son tipos de registro distintos y es fácil confundirlos:

- Las visitas se registran automáticamente y aparecen en los datos a nivel de evento como filas SESSION con un nombre de evento vacío y cero ingresos; así es el esquema, no es un fallo. Las primeras visitas y las revisitas aparecen en los datos a nivel de conversión (FIRST_VISIT / REVISIT), no como eventos con nombre. Una exportación con alcance de sesiones nunca puede contener eventos in-app, por correcta que sea la implementación.

- Las conversiones implementadas aparecen como filas independientes con el nombre del evento rellenado (af_purchase, af_login, etc.), y solo las filas de compra incluyen ingresos.

- Ningún dato extraído para una ventana de tiempo ANTERIOR al despliegue puede contener los eventos nuevos. Dame la hora UTC del despliegue y dime que consulte solo después de ella. Señala que los campos de hora de atribución pueden ser mucho más antiguos que la hora del evento y referirse a una visita anterior, no a esta ejecución.

- Indica la latencia de reporting esperada y avísame de que no interprete un reporte vacío dentro de esa ventana como un fallo.

- Dime el filtro exacto que debo usar para encontrar la ejecución de QA del punto 6c (ventana de tiempo más CUID de QA) y qué aspecto tiene un resultado correcto.

- Si los eventos devuelven 2xx pero aun así no aparecen después de la ventana de latencia, indica claramente que se trata de un problema del lado de la cuenta (evento no habilitado para la aplicación web, alcance del reporting o acceso a los datos), y no de un defecto del código, y enumera qué debo comprobar en la interfaz de AppsFlyer.

## Resultado de salida

Cuando termines, dame:

- Una tabla de cada evento implementado: nombre, ubicación del activador (archivo), gestión de ingresos, ID de deduplicación.

- Dónde se instaló el fragmento y cómo se garantiza la carga única.

- Dónde se llama a setCustomerUserId.

- La tabla del registro de QA del punto 6c y una separación clara entre lo que verificaste tú mismo/a (con estados de respuesta) y lo que queda como lista manual de comprobación de QA para mí (página que abrir, acción que realizar, solicitud y estado esperados).

- La guía del paso 7 para volver a consultar los datos.

- Cualquier cosa que no hayas podido implementar o que necesites de mi parte (p. ej., dónde se encuentra el ID de usuario, qué campo del importe de compra corresponde al total final cobrado o cualquier fuente de valor que te hayas negado a suponer).

No implementes nada más allá de la integración del SDK web de AppsFlyer que se describe aquí.
```

</Accordion>

<div id="1-obtain-your-keys" />

## 1. Obtén tus claves

**Obtén el Web SDK ID (también conocido como Web Dev Key):**

1. En AppsFlyer, desde el menú superior, abre **Configuración de la aplicación**.
2. En el selector de aplicaciones de la parte superior de la página, selecciona tu aplicación web (el dominio de tu sitio web con el prefijo "website-").
3. En **Autenticación del SDK**, copia el **ID del SDK web**.

**Obtén la clave de Smart Banner (si es necesario):**

1. En AppsFlyer, en el menú lateral, abre **Engage** > **Web to App** > **Smart Banners**.
2. Copia la Smart Banner Key requerida.

<div id="2-select-a-code-snippet" />

## 2. Selecciona un snippet de código

Elige el snippet que coincida con tu tipo de integración y requisitos de seguridad. Hay dos opciones disponibles:

* [SDK web estándar](#standard-web-sdk): La integración estándar.
* [Verificación avanzada del SDK](#advanced-sdk-verification): Una integración avanzada que añade protección de la cadena de suministro para el SDK web. Usa esto para agregar una capa adicional de seguridad contra el compromiso de CDN, el DNS hijacking y los ataques de intermediarios.

> ❗️ **Warning**
>
> Si estás haciendo la transición del Standard Web SDK al Advanced SDK Verification, reemplaza tu fragmento existente con el nuevo. No agregues el fragmento nuevo además del existente.

### Standard Web SDK

Usa este fragmento para implementar la integración estándar del SDK web. Pégalo cerca de la parte superior de la etiqueta `<head>` en todas las páginas donde quieras cargar el SDK.

<Accordion title="Sin Smart Banners">

```html
<script>
  // Cola — almacena en búfer las llamadas a AF() hasta que el SDK esté listo
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  // Sustituye WEB_DEV_KEY por tu ID del SDK web
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" } };
  window.AF.plugins = {};

  // Insertar el SDK
  var o = document.createElement("script"),
      p = document.getElementsByTagName("script")[0];
  o.async = 1;
  // Sustituye WEB_DEV_KEY por tu ID del SDK web
  o.src = "https://websdk.appsflyersdk.com?" + "st=pba&af_id=WEB_DEV_KEY";
  p.parentNode.insertBefore(o, p);
</script>
```

</Accordion>

<Accordion title="Con Smart Banners">

```html
<script>
  // Cola — almacena en búfer las llamadas a AF() hasta que el SDK esté listo
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  // Sustituye WEB_DEV_KEY por tu ID del SDK web
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" }, banners: { key: "YOUR_BANNER_KEY" } };
  window.AF.plugins = {};

  // Insertar el SDK
  var o = document.createElement("script"),
      p = document.getElementsByTagName("script")[0];
  o.async = 1;
  // Sustituye WEB_DEV_KEY por tu ID del SDK web
  o.src = "https://websdk.appsflyersdk.com?" + "st=pba,banners&af_id=WEB_DEV_KEY";
  p.parentNode.insertBefore(o, p);
  AF('banners', 'showBanner');
</script>
```

</Accordion>

### Advanced SDK Verification

Advanced SDK Verification agrega protección a la cadena de suministro para el SDK web. Garantiza que el código que se ejecuta en los navegadores de tus usuarios sea exactamente el que publicó AppsFlyer. El código fuente del SDK en sí es idéntico a la integración estándar; solo difieren los mecanismos de entrega y verificación.

Advanced SDK Verification:

* Agrega una capa adicional de seguridad contra compromisos de CDN, DNS hijacking y ataques de intermediarios.
* Agrega aproximadamente 250 ms al tiempo de carga del SDK.

Advanced SDK Verification es opcional. La integración estándar sigue siendo totalmente compatible y es el estándar del mercado para los píxeles de análisis de terceros. Advanced SDK Verification proporciona una capa adicional de protección más allá de ese estándar.

Si tu sitio web aplica una Política de Seguridad de Contenido (CSP) mediante un nonce, consulta [Política de Seguridad de Contenido (CSP)](#política-de-seguridad-de-contenido-csp) en la sección Gestionar privacidad para ver la variante de este fragmento ampliada con nonce.

<Accordion title="Sin Smart Banners">

```html
<script>
  // Cola — almacena en búfer las llamadas a AF() hasta que el SDK esté listo
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  // Sustituye WEB_DEV_KEY por tu ID del SDK web
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" } };
  window.AF.plugins = {};

  // Configuración del cargador de manifiesto
  window.AF_LOADER_CONFIG = {
    baseUrl: "https://websdk.appsflyersdk.com",
    plugins: ["pba"]
  };

  // Insertar el cargador de manifiesto
  var loaderScript = document.createElement("script");
  loaderScript.src = "https://websdk.appsflyersdk.com/manifestLoader.v1.js";
  loaderScript.integrity = "sha384-Uncl2YwvjFpFz0PwEfl3bL/0JsOQcDFEpwXHzcN0MBavn9vvFEx5pZxADTq8h+CV";
  loaderScript.crossOrigin = "anonymous";
  loaderScript.async = true;
  document.head.appendChild(loaderScript);
</script>
```

</Accordion>

<Accordion title="Con Smart Banners">

```html
<script>
  // Cola — almacena en búfer las llamadas a AF() hasta que el SDK esté listo
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  // Sustituye WEB_DEV_KEY por tu ID del SDK web
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" }, banners: { key: "YOUR_BANNER_KEY" } };
  window.AF.plugins = {};

  // Configuración del cargador de manifiesto
  window.AF_LOADER_CONFIG = {
    baseUrl: "https://websdk.appsflyersdk.com",
    plugins: ["banners", "pba"]
  };

  // Insertar el cargador de manifiesto
  var loaderScript = document.createElement("script");
  loaderScript.src = "https://websdk.appsflyersdk.com/manifestLoader.v1.js";
  loaderScript.integrity = "sha384-Uncl2YwvjFpFz0PwEfl3bL/0JsOQcDFEpwXHzcN0MBavn9vvFEx5pZxADTq8h+CV";
  loaderScript.crossOrigin = "anonymous";
  loaderScript.async = true;
  document.head.appendChild(loaderScript);
</script>
```

</Accordion>

<div id="3-deploy-the-snippet" />

## 3. Implementar el snippet

Implementa el snippet que seleccionaste en el Paso 2 utilizando uno de los siguientes métodos. Asegúrate de que el SDK se cargue una sola vez por carga de página.

<Accordion title="Opción A: Añadir directamente a tu sitio web">

Repite esto en todas las páginas:

1. En el fragmento del PASO 2, sustituye `WEB_DEV_KEY` por tu ID del SDK web (y `YOUR_BANNER_KEY` si corresponde).
2. Pega el fragmento cerca de la parte superior de la etiqueta `<head>` del sitio web.

</Accordion>

<Accordion title="Opción B: Implementar mediante Google Tag Manager (GTM)">

Asegúrate de que el SDK se cargue una sola vez por carga de página y configúralo para que se cargue tan pronto como la página se cargue utilizando la priorización de GTM.

1. Abre Google Tag Manager.
2. Crea una nueva etiqueta para AppsFlyer Web SDK.
3. Selecciona el tipo de etiqueta **HTML personalizado**.
4. Asigna un nombre descriptivo a la etiqueta.
5. Pega el fragmento del Paso 2 en **Configuración de la etiqueta**.
6. Haz clic en **Guardar**.
7. Agrega un activador:
   * Para todas las páginas:
     1. Haz clic en **Añadir activador**.
     2. Selecciona **Todas las páginas**.
     3. Haz clic en **Guardar**.
     4. Introduce un nombre de etiqueta y, luego, haz clic en **Guardar**.
   * Para páginas específicas:
     1. Haz clic en **Guardar etiqueta**.
     2. En la ventana principal de GTM, selecciona **Activadores**. Haz clic en **Nuevo**.
     3. Haz clic en el ícono de lápiz.
     4. Elige el tipo de activador **Vista de página**.
     5. Selecciona **Algunas vistas de página**.
     6. Configura la página y las condiciones de activación según sea necesario.
     7. Haz clic en **Guardar**.
     8. Asocia el activador a la etiqueta de AppsFlyer Web SDK:
        1. <span class="af-ol-a"></span>En la ventana principal de **GTM**, selecciona **Etiquetas**.
        2. Selecciona la etiqueta que creaste anteriormente.
        3. En el panel de activación, haz clic en el ícono de lápiz.
        4. Seleccione el activador de vista de página que creaste anteriormente.
        5. Haz clic en **Guardar**.

> 📘 **Note**
>
> Las plantillas personalizadas de GTM no son compatibles con Advanced SDK Verification, ya que su entorno aislado no permite configurar el atributo de integridad necesario para la verificación. Utiliza en su lugar el tipo de etiqueta **HTML personalizado**.

</Accordion>

<Accordion title="Opción C: Implementar mediante Adobe Launch Tag Manager">

<div id="create-a-property-in-adobe-experience-cloud" />

#### Crear una propiedad en Adobe Experience Cloud

1. Abre Adobe Experience Cloud > Launch.
2. En Adobe Experience Cloud Launch, haz clic en **Go to Launch**.
3. Haz clic en **Nueva propiedad**.
4. Asigna un nombre a la propiedad.
5. En **Plataforma**, selecciona **Web**.
6. Ingresa el dominio de tu sitio web.
7. Haz clic en **Guardar**.

<div id="add-the-snippet-to-the-adobe-launch-property" />

#### Agregar el snippet a la propiedad de Adobe Launch

1. En la página **Mi propiedad web**, selecciona la pestaña **Reglas**.
2. Asigna un nombre a la regla. Recomendado: Cargar SDK web.
3. En la sección **SI**, dentro de **Eventos**, haz clic en **Agregar**.
   * En **Tipo de evento**, selecciona **Core – DOM Ready**.
   * Haz clic en **Keep Changes**.
4. En la sección **ENTONCES**, dentro de **Acciones**, haz clic en **Agregar**.
   * En **Tipo de acción**, selecciona **Código personalizado**.
   * Selecciona **JavaScript** > **Abrir editor** y pega el fragmento del paso 2 (sin ninguna línea contenedora).
   * Haz clic en **Mantener cambios** para cerrar el editor de código.
5. Haz clic en **Guardar**.

<div id="add-the-adobe-launch-tag-to-the-website" />

#### Agregar la etiqueta de Adobe Launch al sitio web

1. En la página **Mi propiedad web**, selecciona la pestaña **Entornos**.
2. Busca la fila correspondiente al entorno que deseas publicar (desarrollo o producción).
3. En la columna **Instalar**, haz clic en el icono de cuadro de la fila correspondiente.
4. En el cuadro de diálogo **Instrucciones de instalación web**, copia el snippet de código del script y cierra el cuadro de diálogo.
5. Pega el snippet de código en la sección head del sitio web.

<div id="publish-the-adobe-launch-environment" />

#### Publicar el entorno de Adobe Launch

1. En la página **Mi propiedad web**, ve a la pestaña **Publicación**.
2. En la sección **Desarrollo**, haz clic en **Agregar nueva biblioteca**.
   * Asigna un nombre a la biblioteca y elige un entorno.
   * En **CAMBIOS DE RECURSOS**, haz clic en **Agregar un recurso**.
   * Haz clic en **Reglas** > **Cargar SDK web** > **Más reciente** > **Seleccionar & crear una nueva revisión**.
   * Haz clic en **Guardar**.
3. En la sección **Desarrollo**:
   * Junto a la biblioteca recién creada, haz clic en el menú de acciones (3 puntos) > selecciona **Crear para desarrollo**.
   * Haz clic de nuevo en el menú de acciones > selecciona **Enviar para aprobación**.
4. En la sección **Enviado**:
   * Haz clic en el menú de acciones > selecciona **Crear para escenario**.
   * Haz clic de nuevo en el menú de acciones > selecciona **Aprobar para publicar**.
5. En la sección **Aprobado**:
   * Haz clic en el menú de acciones > selecciona **Compilar & publicar en producción**.

</Accordion>

<div id="4-make-sure-the-sdk-is-working" />

## 4. Asegúrate de que el SDK funcione correctamente

Después de la instalación, verifica que el SDK envíe solicitudes revisando las solicitudes de red en las herramientas para desarrolladores de tu navegador.

<Image align="center" alt="Captura de pantalla de DevTools" src="https://files.readme.io/a1bb1f22e9d30059830239e7a4d13d7cde106a3363502cb9e8a054d6e8d65dff-43492318562833.png" width="1015px" />

**Para asegurarte de que el SDK funcione correctamente, sigue estos pasos:**

1. Abre el sitio web.
2. Abre las herramientas para desarrolladores del navegador.
3. Ve a la pestaña (A) **Red**.
4. Actualiza la página.
5. Filtra por (B) `appsflyer`. Pueden aparecer dos solicitudes:
   * **Cargador del SDK** — La URL de la solicitud empieza por `https://websdk.appsflyersdk.com`. Esto confirma que el script del SDK se cargó correctamente.
   * **Datos del evento** — La URL de la solicitud empieza por `https://wa.appsflyer.com/events`. Esto confirma que el SDK está enviando datos de eventos a AppsFlyer.
6. Selecciona el mensaje (C) **events** (la llamada a `wa.appsflyer.com`).
7. En Headers, (D) asegúrate de que:
   * La URL de la solicitud empieza por `https://wa.appsflyer.com/events?site-id=`.
   * El parámetro de consulta `site_id` = `WEB_DEV_KEY`.
   * El código de estado es 200.
8. Verifica que `site_id` coincida con la `WEB_DEV_KEY` en AppsFlyer > menú superior > **Mis aplicaciones**.
9. Verifica que el SDK se cargue una sola vez. La carga múltiple del SDK puede provocar que deje de funcionar.

> 📘 **Note**
>
> Para confirmar en tiempo real y de forma visual la instalación del SDK web y validar que tus eventos se activen correctamente, utiliza la página de prueba del SDK web.

<div id="5-set-and-record-events" />

## 5. Configurar y registrar eventos

Después de inicializar Web SDK, puedes pasar de medir visitas básicas a capturar acciones específicas de los usuarios. Esta sección te guía para definir y registrar eventos personalizados, como compras o registros, utilizando **JavaScript nativo** o **Google Tag Manager**.

<Accordion title="Configurar eventos">

Los eventos son los componentes fundamentales de la medición web y representan acciones específicas de los usuarios que tienen valor para tu negocio. Para registrar estas interacciones, debes definir la lógica y los parámetros de cada evento, asegurándote de que los parámetros correctos, como ingresos y metadatos personalizados, se envíen a la plataforma de AppsFlyer.

**Evento de ejemplo (evento de compra con ingresos asociados)**

```javascript
AF('pba', 'event', {eventType: 'EVENT', eventName: 'purchase', eventRevenue: 12, eventValue: {"key1": 123, "key2": "name", "af_customer_event_id": "evt-abc-001"}});
```

<div id="web-sdk-event-parameters-table" />

<Accordion title="Tabla de parámetros de eventos de Web SDK">

| Nombre del parámetro | Obligatorio | Description |
| --- | --- | --- |
| `eventType` | Sí | Tipo de evento. Formato: cadena. Completa siempre este parámetro con `EVENT`. Ejemplo: `eventType: "EVENT"` |
| `eventName` | Sí | Nombre del evento. Formato: cadena. Ejemplo: Compra, suscripción |
| `eventRevenue` | No | Ingresos asignados a un evento de conversión. Formato: Float |
| `eventRevenueCurrency` | No | Moneda de ingresos. Código de divisa ISO 4217 de 3 caracteres. Predeterminado: USD. Formato: Secuencia |
| `valor del evento` | No | Asignación de parámetros del evento que describen el evento. Utiliza este parámetro para enviar eventos enriquecidos, como SKU de productos y precios de artículos. Formato: JSON. Ejemplo: `{"sku": "ABC123", "color": "blue", "unit_price": 3.99, "currency": "USD"}` Limitación: 3000 caracteres (se trunca si se supera). |

</Accordion>

</Accordion>

<Accordion title="Registrar eventos al cargar la página">

Este es el enfoque estándar para conversiones que terminan con una redirección, como una página de **Gracias** o de confirmación.

Puedes implementar este activador añadiendo un método de carga de ventana a tu **JavaScript nativo** o configurando un activador de vista de página en **Google Tag Manager**.

> 🚧 **Important**
>
> Los siguientes ejemplos de código son solo para fines ilustrativos. **No utilices este código tal cual**; adáptalo a la estructura específica de tu sitio.

<div id="example-record-event-via-af-web-sdk" />

<Accordion title="Ejemplo: Registrar evento mediante AF Web SDK">

Este enfoque es ideal para registrar conversiones que ocurren mediante redirecciones, como una página de agradecimiento para una suscripción a un boletín.

**Caso de uso:** Un usuario completa el registro en el boletín y es redirigido a una página de confirmación. Deseas registrar el evento de suscripción tan pronto como esa página sea visible.

**Ejemplo de carga de página nativa:**

```javascript
window.onload = function(){
  AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category': 'holiday_promotion'}, eventName: 'subscription'});
}
```

**Cómo funciona:**

1. La página carga el contenido necesario.
2. Una vez que la ventana se ha cargado por completo (`window.onload`), el script llama automáticamente al método `AF()`.
3. El evento **subscription**, junto con sus metadatos asociados (categoría y etiqueta), se envía directamente a AppsFlyer.

</Accordion>

<div id="example-record-event-via-gtm" />

<Accordion title="Ejemplo: Registrar evento mediante GTM">

Este enfoque se utiliza para registrar conversiones exitosas, como una suscripción a un boletín, activando una etiqueta cuando se carga una página de "Gracias".

<div id="1-set-up-a-thank-you-page" />

#### 1. Configurar una página de Gracias

La siguiente estructura HTML carga GTM, que a su vez carga Web SDK. También muestra cómo los datos pueden ponerse a disposición de GTM mediante funciones o `localStorage`.

```html
<html>
<head>
    <script>
        // Google Tag Manager carga el SDK web
        (function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
        new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
        j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
        'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
        })(window,document,'script','dataLayer','GTM-XXXX');
    </script>
    <script>
        function getResponseFromServer() {
            return JSON.stringify({ action: 'subscribe', category: 'site actions', label: userEmail })
        }
        localStorage.setItem('data', JSON.stringify({ action: 'subscribe', category: 'site actions', label: 'user@email.com' }));
    </script>
</head>
<body>
    <h1>Gracias por suscribirte a nuestro boletín informativo</h1>
</body>
</html>
```

<div id="2-configure-the-gtm-tag" />

#### 2. Configurar la etiqueta de GTM

1. Crea una nueva etiqueta en GTM y selecciona el tipo de etiqueta **HTML personalizado**.
2. Asigna un nombre distintivo (por ejemplo, "AF Subscription Event").
3. Pega el siguiente script en el área de texto HTML:

   ```javascript
   AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'subscription'});
   ```
4. Expande **Configuración avanzada** > **Secuenciación de etiquetas**. Asegúrate de que esté configurada para activarse después de la etiqueta principal de inicialización de Web SDK.
5. Configura un activador para que esta etiqueta se active en la **vista de página** de tu página de "Gracias".

</Accordion>

</Accordion>

<Accordion title="Registrar eventos mediante la interacción del usuario">

Usa esto para medir acciones sin recargar la página (clics en botones, descargas, añadir al carrito).

Estas interacciones suelen gestionarse vinculando un listener de clic a un **elemento HTML nativo** o utilizando variables de **Google Tag Manager** para identificar y medir los ID de elementos o selectores CSS específicos.

> 🚧 **Important**
>
> Los siguientes ejemplos de código son solo para fines ilustrativos. **No utilices este código tal cual**; adáptalo a la estructura específica de tu sitio.

<div id="example-record-event-via-af-web-sdk-interaction" />

<Accordion title="Ejemplo: Registrar evento mediante AF Web SDK">

Utiliza este método para medir acciones específicas que los usuarios realizan en una página, como hacer clic en un botón de **Checkout** o **Descarga**.

**Caso de uso:** Gestionas un sitio de ecommerce y quieres capturar un **evento checkout** en el momento en que un usuario hace clic en el botón **Checkout** de su carrito de compras.

**Ejemplo de interacción nativa del usuario:**

```html
<html>
<head>
    <script>
        window.onload = function () {
            document.getElementById('checkout').addEventListener('click', function () {
                AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'checkout'});
            });
        }
    </script>
</head>
<body>
    <h1>Carrito de compras</h1>
    <button id='checkout'>Checkout</button>
</body>
</html>
```

**Cómo funciona:**

1. Cuando se carga la página, el script adjunta un listener del evento de **clic** al elemento con el ID `checkout`.
2. Cuando el usuario hace clic en el botón, se ejecuta la función callback.
3. La función puede obtener datos relevantes (por ejemplo, de `localStorage`) y pasarlos al método `AF()`.
4. Luego, el SDK transmite el **evento checkout** a la plataforma AppsFlyer.

</Accordion>

<div id="example-record-event-via-gtm-interaction" />

<Accordion title="Ejemplo: Registrar evento mediante GTM">

Este método captura acciones específicas, como hacer clic en un botón de **Checkout**, utilizando las variables y los activadores integrados de GTM.

<div id="1-set-up-a-checkout-page" />

#### 1. Configurar una página de checkout

```html
<html>
<head>
    <script>
        (function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
        new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
        j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
        'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
        })(window,document,'script','dataLayer','GTM-XXXX');
    </script>
</head>
<body>
    <h1>Carrito de compras</h1>
    <button id='checkout'>Checkout</button>
</body>
</html>
```

<div id="2-configure-gtm-variables-and-triggers" />

#### 2. Configurar variables y activadores de GTM

1. <span class="af-ol-a"></span>En GTM, haz clic en **Variables** > **Configurar** y habilita **Elemento de clic** en la lista de variables integradas.
2. Crea una nueva variable definida por el usuario (tipo: **Todos los elementos**).
3. Crea un nuevo **Activador**:
   * Tipo de activador: **Clic - Todos los elementos**.
   * Este activador se activa con: **Algunos clics**.
   * Condición: **Elemento de clic** coincide con el selector CSS `#checkout`.

<div id="3-create-the-interaction-tag" />

#### 3. Crear la etiqueta de interacción

1. <span class="af-ol-a"></span>Crea una nueva etiqueta de **HTML personalizado** para la acción de checkout.
2. Pega el script de interacción:

   ```html
   <script>
     AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'checkout'});
   </script>
   ```
3. Asigna el activador "Checkout Click" que creaste en el paso anterior.

</Accordion>

</Accordion>

<Accordion title="Mejores prácticas para la implementación de eventos">

Para garantizar la precisión de los datos y una transmisión exitosa, ten en cuenta los siguientes requisitos técnicos:

* **Orden de carga:** Asegúrate de que la etiqueta de funciones de Web SDK esté completamente cargada en el ámbito de la página antes de realizar cualquier llamada de evento.
* **Formato de datos:** No incluyas caracteres especiales en los valores de los eventos. Por ejemplo, utiliza valores numéricos para los ingresos en lugar de incluir símbolos de moneda (usa `10.50` en lugar de `$10.50`).
* **Límites de string:** Mantén las cadenas de `eventValue` concisas; los valores de más de 3000 caracteres se truncarán.
* **Deduplicación de eventos:** Recomendamos enviar `af_customer_event_id` en `eventValue`, con un valor único por evento. Esto es especialmente importante cuando envías el mismo evento a través del SDK web y de la Server-to-Server (S2S) API. AppsFlyer reenvía este valor a la ad network, que lo utiliza para deduplicar el evento del lado del Servidor que recibe de AppsFlyer con respecto al mismo evento que recibió de su propio píxel.
* **Ubicación de los ingresos:** Rellena `eventRevenue` solo en los eventos en los que realmente se haya movido dinero, como una compra o una suscripción confirmada. En los eventos que tienen un valor monetario pero no son ingresos reales (por ejemplo, añadir al carrito, iniciar el checkout o ver contenido), usa en su lugar af\_price y af\_currency en eventValue. Enviar `eventRevenue` tanto en el checkout como en la compra duplica los ingresos en cada reporte.
* **Nomenclatura de eventos:** No añadas sufijos de plataforma como `_web` a los nombres de los eventos. La plataforma ya es una dimensión en el dashboard y en raw data. Usa los mismos nombres de evento que en tu aplicación móvil para mantener unificados los reportes entre plataformas.

</Accordion>

<div id="6-set-customer-user-id" />

## 6. Establecer ID de Usuario de Cliente

Después de implementar la medición de eventos, configura una identidad persistente para vincular la actividad web con otras plataformas (móvil, PC, CTV) mediante `setCustomerUserId`, para obtener una vista unificada del recorrido del usuario entre plataformas.

**Reglas clave**

* **Coherencia:** Usa el mismo valor de CUID que en las implementaciones de tu aplicación móvil (consulta `setCustomerUserId` para móvil en: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-ios-sdk">iOS</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-android-sdk#setting-the-customer-user-id">Android</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/basicintegration#set-customer-user-id">Unity</Anchor>).
* **Momento:** Puedes enviar el CUID en cualquier etapa (por ejemplo, después del inicio de sesión o del registro). Configura el CUID tan pronto como sea posible, una vez que tengas acceso a él. La mayoría de las veces, esto significa que debes esperar a que el usuario se identifique mediante inicio de sesión o registro.
* **Sintaxis:** Envía el valor como un string (entre comillas). **Ejemplo:** `AF('pba', 'setCustomerUserId', '663274')`
* **Privacidad:** No incluyas información de identificación personal (PII), como direcciones de correo electrónico o números de teléfono.

<Accordion title="Ejemplo: Configuración de CUID después del registro (nativo)">

El código proporcionado en estos ejemplos es solo de referencia. No utilices este código tal cual. Si no estás seguro de cómo utilizar este código, consulta con tu desarrollador web.

Supuesto: el SDK web ya está cargado en la página antes de enviar el evento; no lo vuelvas a cargar.

Situación del usuario:

* Un usuario se registra en tu sitio web.
* El código del sitio web recopila los datos del usuario y los envía a tu servidor.
* El servidor genera un CUID único para el usuario.
* En la página de agradecimiento posterior al registro, consultas al servidor para obtener el nuevo CUID.
* Mediante la respuesta del servidor, configuras el CUID de AppsFlyer con el método `setCustomerUserId()` del SDK web.

<div id="a-sign-up-form-example" />

#### Ejemplo de formulario de registro

El siguiente código es un formulario de registro simple. Cuando se envía el formulario, la dirección de correo electrónico se almacena en `localStorage`. Cuando el usuario llega a la página de agradecimiento, la dirección de correo electrónico se envía al servidor para obtener el CUID único asociado a ese correo.

```html
<html>
<head>
    <script>
!function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){
(t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
o.src="https://websdk.appsflyersdk.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "WEB_DEV_KEY"}})
    </script>
    <script>
        function storeUserEmail() {
            var userEmail = document.getElementById('email').value;
            localStorage.setItem('user_email', userEmail);
        }
    </script>
</head>
<body>
    <h1>Registrarse</h1>
    <form onsubmit="storeUserEmail()" action="/signup" method="post">
        <div><label>Nombre</label><input type="text" name="name" id="name"></div>
        <br/>
        <div><label>Correo electrónico</label><input type="email" name="email" id="email"></div>
        <br/>
        <input type="submit" id="submit">
    </form>
</body>
</html>
```

<div id="a-thank-you-page-example" />

#### Ejemplo de página de agradecimiento

El código utiliza la API Fetch. Envía al servidor la dirección de correo electrónico ingresada por el usuario. Suponiendo que el servidor crea un usuario con un CUID único al registrarse, enviar la dirección de correo electrónico al servidor devuelve un CUID único. El servidor responde con un CUID único, y ese CUID único es el valor que se pasa con el método `setCustomerUserId`.

```html
<html>
<head>
    <script>
!function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){
(t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
o.src="https://websdk.appsflyersdk.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "WEB_DEV_KEY"}})
    </script>
    <script>
        window.onload = function () {
            var userEmail = localStorage.getItem('user_email');
            fetch('users/' + userEmail).then(function (res) {
                res.text().then(function (id) {
                    console.log(id);
                    AF('pba', 'setCustomerUserId', id);
                });
            });
        }
    </script>
</head>
<body>
    <h1>¡Gracias por registrarte!</h1>
</body>
</html>
```

</Accordion>

<Accordion title="Ejemplo: Configuración de CUID después del registro (Google Tag Manager)">

1. Configura una página de registro.

   El ejemplo de código a continuación es un formulario de registro simple. Cuando se envía el formulario, la dirección de correo electrónico se almacena en `localStorage`. Cuando el usuario llega a la página de agradecimiento, la dirección de correo electrónico se envía al servidor para obtener el CUID único asociado a ese correo.

   ```html
   <html>
   <head>
       <script>
           (function (w, d, s, l, i) {
               w[l] = w[l] || []; w[l].push({ 'gtm.start': new Date().getTime(), event: 'gtm.js' });
               var f = d.getElementsByTagName(s)[0], j = d.createElement(s),
                   dl = l != 'dataLayer' ? '&l=' + l : ''; j.async = true;
               j.src = 'https://www.googletagmanager.com/gtm.js?id=' + i + dl;
               f.parentNode.insertBefore(j, f);
           })(window, document, 'script', 'dataLayer', 'GTM-5VJ6C7R');
           function storeUserEmail() {
               var userEmail = document.getElementById('email').value;
               localStorage.setItem('user_email', userEmail);
           }
       </script>
   </head>
   <body>
       <h1>Registrarse</h1>
       <form onsubmit="storeUserEmail()" action="/signup" method="post">
           <div><label>Nombre</label><input type="text" name="name" id="name"></div>
           <br />
           <div><label>Correo electrónico</label><input type="email" name="email" id="email"></div>
           <br />
           <input type="submit" id="submit">
       </form>
   </body>
   </html>
   ```
2. Configura una página de agradecimiento para los usuarios que se registran. El siguiente código corresponde a una página de agradecimiento con un activador de GTM que envía al servidor la dirección de correo electrónico proporcionada por el usuario en el formulario de registro. Suponiendo que el servidor crea un usuario con un CUID único al registrarse, enviar el correo electrónico al servidor devuelve un CUID único. El servidor responde con un CUID único, que se envía mediante el método `setCustomerUserId()`.

   ```html
   <script>
       window.onload = function () {
           var userEmail = localStorage.getItem('user_email');
           fetch('users/' + userEmail).then(function (res) {
               res.text().then(function (id) {
                   console.log(id);
                   AF('pba', 'setCustomerUserId', id);
               });
           });
       }
   </script>
   ```
3. Agrega una nueva etiqueta para atribuir suscripciones después de que se cargue la página de agradecimiento.

   <Image align="center" alt="Adición de una nueva etiqueta de GTM para el evento de conversión de CUID" src="https://files.readme.io/c85a3cbc6c9675e4bfa762ff0a9930d58b1e02b13f147342a11b433e1d211b11-360002750309.png" />
4. Dale a la etiqueta un nombre distintivo y selecciona la opción de tipo de etiqueta **Custom HTML**.

   <Image align="center" alt="Asignación de nombre a la etiqueta y selección del tipo de etiqueta Custom HTML en GTM" src="https://files.readme.io/beab3305bc50c44c291997fa9b77bf4df7dd5dd9207a1bf766c2e1702e314d2c-360016246418.jpg" />

   ```html
   <script>
       var userEmail = localStorage.getItem('user_email');
       fetch('users/' + userEmail).then(function (res) {
           res.text().then(function (id) {
               console.log(id);
               AF('pba', 'setCustomerUserId', id);
           });
       });
   </script>
   ```
5. Expande **Configuración avanzada** y luego **Secuenciación de etiquetas** debajo del área de texto, y asegúrate de que esté configurado para activar la conversión después de que se ejecute la etiqueta.

   <Image align="center" alt="Configuración de la secuenciación de etiquetas de GTM para la etiqueta de conversión" src="https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png" />
6. Configura un activador para la etiqueta de conversión que indique cuándo debe ejecutarse (en el ejemplo siguiente, se ejecuta al cargar la página de "Gracias").

   <Image align="center" alt="Configurar el activador de GTM para que active la etiqueta de conversión al cargar la página de agradecimiento" src="https://files.readme.io/25fd3944971abc811cbe6192cec8c73bb31b3b3c3715a1b8918a71d7f8bf72b1-360002902185.png" />

</Accordion>

<div id="7-manage-privacy" />

## 7. Gestionar la privacidad

Después de implementar la medición de eventos, es posible que debas aplicar restricciones específicas de seguridad y privacidad para cumplir con estándares organizacionales o regionales.

<Accordion title="Activar o desactivar el envío de eventos">

Puedes controlar la medición de dos maneras:

<div id="sdk-initial-state-setting-in-the-snippet" />

#### Configuración del estado inicial del SDK (en el snippet)

Determina si el SDK envía eventos cuando la página web se carga por primera vez o si espera hasta que le indiques explícitamente que comience a enviarlos. Esta configuración se define en el snippet web.

* Enviar eventos: `{pba: {webAppId: "...", measurementStatus:true}}`
* No enviar eventos: `{pba: {webAppId: "...", measurementStatus:false}}`

> 📘 **Note**
>
> Si measurementStatus está vacío o es NULL, AppsFlyer lo considera como si fuera measurementStatus:true.

<div id="explicit-control" />

#### Control explícito

El control explícito tiene prioridad sobre la configuración del estado inicial y utiliza cookies persistentes de first-party:

* Se establecen en el dominio del sitio web.
* Expiran después de un período definido por Web SDK o por el navegador.
* Siempre están sujetas a la configuración de cookies del navegador.

**Comandos**

* Empezar a enviar eventos (opt-in): `window.AF_SDK.PLUGINS.PBA.enableMeasurement()`
* Dejar de enviar eventos (opt-out): `window.AF_SDK.PLUGINS.PBA.disableMeasurement()`

</Accordion>

<Accordion title="Proteger y filtrar datos">

Si tu sitio web requiere estrictos protocolos de seguridad o privacidad de datos, utiliza los siguientes mecanismos para configurar cómo interactúa el SDK web con tu entorno y tus datos.

<div id="content-security-policy-csp" />

#### Política de Seguridad de Contenido (CSP)

Si tu sitio web requiere que JavaScript esté protegido mediante una CSP, Web SDK admite dos enfoques según tu configuración de CSP y el snippet que seleccionaste en el Paso 2.

* **CSP con self**: Añade `https://websdk.appsflyersdk.com` a tu lista de permitidos de `script-src`. Esto funciona tanto para Standard Web SDK como para Advanced SDK Verification.
* **CSP con nonce**: Si tu política usa `script-src 'nonce-...'`, utiliza la variante de Advanced SDK Verification ampliada con nonce que aparece a continuación. Esto reenvía el nonce a las tres etiquetas script que requiere el proceso de verificación. Sustituye `{{CSP_NONCE}}` por el valor de nonce, generado por el servidor, para cada solicitud.

La siguiente tabla muestra qué políticas de CSP son compatibles con la variante nonce-extended.

| Política | Funciona | Notas |
| --- | --- | --- |
| `script-src 'self'` | No | No se permite el origen de CDN externo; el script en línea también se bloquea. |
| `script-src 'self' https://websdk.appsflyersdk.com` | Parcial | Permite el loader y el SDK, pero el script de configuración en línea sigue bloqueado. |
| `script-src 'nonce-...' https://websdk.appsflyersdk.com` | Sí | Nonce cubre el script en línea y el loader; la etiqueta del SDK es reenviada por el loader. |
| `script-src 'nonce-...' 'strict-dynamic'` | Sí (recomendado) | El nonce cubre el script en línea y el cargador; `strict-dynamic` propaga la confianza a la etiqueta del SDK inyectada dinámicamente. No se necesita origen de CDN en la lista de permitidos. |

Compatibilidad con políticas de CSP

<div id="advanced-sdk-verification-with-csp-nonce-snippets" />

#### Advanced SDK Verification con fragmentos de CSP nonce

<div id="nonce-without-smart-banners" />

<Accordion title="Sin Smart Banners">

```html
<script nonce="{{CSP_NONCE}}">
  // Cola: almacena en búfer las llamadas a AF() hasta que el SDK esté listo
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  // Sustituye WEB_DEV_KEY por tu ID del SDK web
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" } };
  window.AF.plugins = {};

  // Configuración del cargador de manifiesto: el nonce se reenvía a la etiqueta <script> del SDK inyectada
  window.AF_LOADER_CONFIG = {
    baseUrl: "https://websdk.appsflyersdk.com",
    plugins: ["pba"],
    nonce: "{{CSP_NONCE}}"
  };

  // Inyecta el cargador de manifiesto
  var loaderScript = document.createElement("script");
  loaderScript.src = "https://websdk.appsflyersdk.com/manifestLoader.v1.js";
  loaderScript.integrity = "sha384-Uncl2YwvjFpFz0PwEfl3bL/0JsOQcDFEpwXHzcN0MBavn9vvFEx5pZxADTq8h+CV";
  loaderScript.crossOrigin = "anonymous";
  loaderScript.nonce = "{{CSP_NONCE}}";
  loaderScript.async = true;
  document.head.appendChild(loaderScript);
</script>
```

</Accordion>

<div id="nonce-with-smart-banners" />

<Accordion title="Con Smart Banners">

```html
<script nonce="{{CSP_NONCE}}">
  // Cola: almacena en búfer las llamadas a AF() hasta que el SDK esté listo
  window.AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  // Sustituye WEB_DEV_KEY por tu ID del SDK web
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" }, banners: { key: "YOUR_BANNER_KEY" } };
  window.AF.plugins = {};

  // Configuración del cargador de manifiesto: el nonce se reenvía a la etiqueta <script> del SDK inyectada
  window.AF_LOADER_CONFIG = {
    baseUrl: "https://websdk.appsflyersdk.com",
    plugins: ["banners", "pba"],
    nonce: "{{CSP_NONCE}}"
  };

  // Inyecta el cargador de manifiesto
  var loaderScript = document.createElement("script");
  loaderScript.src = "https://websdk.appsflyersdk.com/manifestLoader.v1.js";
  loaderScript.integrity = "sha384-Uncl2YwvjFpFz0PwEfl3bL/0JsOQcDFEpwXHzcN0MBavn9vvFEx5pZxADTq8h+CV";
  loaderScript.crossOrigin = "anonymous";
  loaderScript.nonce = "{{CSP_NONCE}}";
  loaderScript.async = true;
  document.head.appendChild(loaderScript);
</script>
```

</Accordion>

<div id="discard-query-parameters" />

#### Descartar parámetros de consulta

Si los parámetros de consulta de tu URL contienen información sensible, indica a AppsFlyer que los descarte (URLs, referentes y `header_referer`).

* Descarta **todos** los parámetros de consulta: añade `af_url=true`
* Descarta parámetros **específicos**: usa `af_url_mask=param` (separa varios parámetros con `;`)

Ejemplo:

* Original: `param1=value1&param2=value2&param3=value3&af_url_mask=param2;param3`
* Resultado: `param1=value1&af_url_mask=param2;param3`

</Accordion>

<div id="web-sdk-cookies-reference" />

## Referencia de cookies de Web SDK

Web SDK establece o utiliza las siguientes cookies:

| Nombre de cookie | Dominio | Vida útil | Cuando se utiliza | Detalles |
| --- | --- | --- | --- | --- |
| afUserid | El dominio de tu sitio web | 395 días | Páginas móviles no aceleradas | Identifica a un usuario en el contexto de eventos de carga y navegación de páginas web. |
| AF\_SYNC | El dominio de tu sitio web | 1 semana | Páginas móviles no aceleradas | Indica que se ha establecido un identificador de usuario final. Se utiliza para reducir los tiempos de carga del sitio. |
| af\_id | <Anchor target="_blank" href="http://appsflyer.com/">appsflyer.com</Anchor> | 395 días | Páginas móviles no aceleradas cuando se permiten cookies de terceros | Identifica a un usuario en el contexto de eventos de apertura y navegación de la app. |
| af\_id | <Anchor target="_blank" href="http://onelink.me/">onelink.me</Anchor> | 395 días | Páginas móviles no aceleradas cuando se permiten cookies de terceros | Vincula interacciones con banners, interacciones con OneLink o ambas con eventos de apertura de la app. |
| amp-afUserid | AMP CDN o el dominio de tu sitio web | 1 año | Páginas Móviles Aceleradas |  |
| AF\_DEFAULT\_MEASUREMENT\_STATUS | El dominio de tu sitio web | 395 días | Páginas móviles no aceleradas | Almacena el estado del consentimiento. Impide que el SDK funcione hasta que el usuario otorgue su consentimiento. No se configura de forma predeterminada. Se utiliza solo cuando está configurado el <Anchor target="_blank" href="/marketers/es/docs/pba-web-sdk-integration-guide#sending-events-optinoptout">consent gating</Anchor>. |

<div data-zendesk-anchors="overview=vista-general h_01KGJCGCPZDJ446QHW80H9Z4C3=vista-general h_01M11M9ZXB0PFFPKVDCGVD0RFT=integrar-el-sdk-manualmente ai-prompt=integrar-el-sdk-con-un-agente-de-programaci%C3%B3n-con-ia h_01UJZDE8GXD6NCF10EPF91DH=integrar-el-sdk-con-un-agente-de-programaci%C3%B3n-con-ia step-1-obtain-your-keys=1-obt%C3%A9n-tus-claves h_01KP11XJV8B56W7FK2KAAFH0NE=1-obt%C3%A9n-tus-claves step-2-select-a-code-snippet=2-selecciona-un-snippet-de-c%C3%B3digo h_01KP11XJV8RDV378GMFF0DVZ8V=2-selecciona-un-snippet-de-c%C3%B3digo standard=standard-web-sdk h_01KP11XJV8MN64YV17D1M0T5B9=standard-web-sdk h_01KP11XJV8ZGF4SDXJH6FKX18E=advanced-sdk-verification step-3-deploy-the-snippet=3-implementar-el-snippet h_01KP11XJV8JQ5S2BBS18RV2H2R=3-implementar-el-snippet create-a-property-in-adobe-experience-cloud=crear-una-propiedad-en-adobe-experience-cloud h_01KP11XJV9RWY4TTWACW69YGJH=crear-una-propiedad-en-adobe-experience-cloud add-the-snippet-to-the-adobe-launch-property=agregar-el-snippet-a-la-propiedad-de-adobe-launch h_01KP11XJV9ZHMP9M85S3KG0V6R=agregar-el-snippet-a-la-propiedad-de-adobe-launch add-the-adobe-launch-tag-to-the-website=agregar-la-etiqueta-de-adobe-launch-al-sitio-web h_01KP11XJVBV5J9E0HV5DM9HS7B=agregar-la-etiqueta-de-adobe-launch-al-sitio-web publish-the-adobe-launch-environment=publicar-el-entorno-de-adobe-launch h_01KP11XJVB0Y4RCBS9QCFBAKRD=publicar-el-entorno-de-adobe-launch 2-make-sure-the-sdk-is-working=4-aseg%C3%BArate-de-que-el-sdk-funcione-correctamente h_01KGJCGCPZ38XZAY8SXB48YWBD=4-aseg%C3%BArate-de-que-el-sdk-funcione-correctamente 3-set-and-record-events=5-configurar-y-registrar-eventos h_01KGJCGCPZMPX1FH58MVGM9VQS=5-configurar-y-registrar-eventos h_01KP3CJBZXV66CCP4N0482DG1N=web-sdk-event-parameters-table h_01KP3CJBZXB328CABH2QCRXTHX=example-record-event-via-af-web-sdk h_01KP3CJBZXM3WK0JYB6S8P6SMQ=example-record-event-via-gtm 1-set-up-a-thank-you-page=1-configurar-una-p%C3%A1gina-de-gracias h_01KGJCGCPZQDP9KVBSE1Z1GT48=1-configurar-una-p%C3%A1gina-de-gracias 2-configure-the-gtm-tag=2-configurar-la-etiqueta-de-gtm h_01KGJCGCPZ2YVRY6VYJ0BTC14N=2-configurar-la-etiqueta-de-gtm h_01KP3CJBZXD6MPTQ0KCPMTM1Y9=example-record-event-via-af-web-sdk-interaction h_01KP3CJBZX53G1HABG3TKN2X6S=example-record-event-via-gtm-interaction 1-set-up-a-checkout-page=1-configurar-una-p%C3%A1gina-de-checkout h_01KGJCGCQ0858AAJC82Y2G0GNP=1-configurar-una-p%C3%A1gina-de-checkout 2-configure-gtm-variables-and-triggers=2-configurar-variables-y-activadores-de-gtm h_01KGJCGCQ0GGYDQBP9CJNM9AXQ=2-configurar-variables-y-activadores-de-gtm 3-create-the-interaction-tag=3-crear-la-etiqueta-de-interacci%C3%B3n h_01KGJCGCQ0EV557QF3CGZ6YB4X=3-crear-la-etiqueta-de-interacci%C3%B3n 4-set-customer-user-id=6-establecer-id-de-usuario-de-cliente h_01KGJCGCQ0RNBW7V5T4PXVXQW1=6-establecer-id-de-usuario-de-cliente a-sign-up-form-example=ejemplo-de-formulario-de-registro h_01KGJCGCQ0M0ESXFMK45PJ3SX9=ejemplo-de-formulario-de-registro a-thank-you-page-example=ejemplo-de-p%C3%A1gina-de-agradecimiento h_01KGJCGCQ0FMKFKM2SWV2794T5=ejemplo-de-p%C3%A1gina-de-agradecimiento 5-manage-privacy=7-gestionar-la-privacidad h_01KGJCGCQ01PQWT44ZWE329DWX=7-gestionar-la-privacidad sdk-initial-state-setting-in-the-snippet=configuraci%C3%B3n-del-estado-inicial-del-sdk-en-el-snippet h_01KGJCGCQ0AQM3Y9NNCJF2XP9G=configuraci%C3%B3n-del-estado-inicial-del-sdk-en-el-snippet explicit-control=control-expl%C3%ADcito h_01KGJCGCQ07KKYGN5JZF41A6W7=control-expl%C3%ADcito content-security-policy-csp=pol%C3%ADtica-de-seguridad-de-contenido-csp h_01KGJCGCQ0QB7NK6YNZT5XJVJY=pol%C3%ADtica-de-seguridad-de-contenido-csp advanced-sdk-verification-with-csp-nonce-snippets=advanced-sdk-verification-con-fragmentos-de-csp-nonce h_01KP11XJV88YB2NSBZJTX9K7ZQ=advanced-sdk-verification-con-fragmentos-de-csp-nonce h_01KP3CJBZXQ4D538H0T7N9FZ6Z=nonce-without-smart-banners h_01KP3CJBZX8K3WK6RHQMB029VN=nonce-with-smart-banners discard-query-parameters=descartar-par%C3%A1metros-de-consulta h_01KGJCGCQ010K4RMFMGHD5NDC3=descartar-par%C3%A1metros-de-consulta web-sdk-cookies-reference=referencia-de-cookies-de-web-sdk h_01KGJCGCQ03A1H7NA5ZGPSGKP3=referencia-de-cookies-de-web-sdk" />
