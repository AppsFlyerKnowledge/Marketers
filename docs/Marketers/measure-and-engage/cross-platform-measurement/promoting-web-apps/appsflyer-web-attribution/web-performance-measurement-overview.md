---
title: 'Medición del rendimiento web: información general'
metadata:
  keywords:
    - Agencies
    - Web Attribution
    - Web Attribution SDK
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
    - Agencies
  created_at: '2026-02-04T15:07:53Z'
  edited_at: '2026-09-19T00:21:14Z'
  id: 43521734577809
  locale: es
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/es/articles/43521734577809
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Resumen:** Web Performance Measurement te permite identificar qué fuentes de medios y campañas impulsan a los usuarios a visitar tu sitio web y medir cómo esas visitas influyen en las acciones posteriores a lo largo del tiempo. Te permite capturar y atribuir las interacciones de los usuarios de principio a fin, tanto para la adquisición de usuarios (visitantes por primera vez) como para el re-engagement, desde la visita inicial hasta la medición del valor de vida útil.

## Acerca de Web Performance Measurement

La atribución web es el proceso de identificar qué fuentes de medios y campañas impulsan a los usuarios a visitar un sitio web e influyen en sus acciones posteriores.

Una visita web representa tanto una actividad de navegación como un engagement con un anuncio que se produjo inmediatamente antes de la visita. A diferencia de la atribución móvil, donde deben asociarse los clics y las instalaciones, una visita web incluye datos de la fuente de marketing en la URL y en el encabezado, lo que hace que la asociación inicial sea inmediata.

El objetivo de este artículo es describir el proceso integral de Web Performance Measurement y explicar cómo se capturan, identifican y miden las interacciones de los usuarios desde la visita inicial al sitio web hasta el valor de vida útil. Este proceso permite que el motor sea compatible tanto con la adquisición de usuarios, para identificar y atribuir a los visitantes por primera vez, como con el retargeting o el re-engagement, para medir el impacto de las campañas dirigidas específicamente a los usuarios que regresan.

#### Si usas la atribución basada en personas (PBA)

Si actualmente usas <Anchor target="_blank" href="/marketers/es/docs/people-based-attribution-pba">la atribución basada en personas (PBA)</Anchor>, valora cambiar a Web Performance Measurement para obtener una atribución más granular y señales adicionales.

### El flujo de Web Performance Measurement

El flujo de Web Performance Measurement sigue una secuencia estructurada de pasos que transforma las visitas sin procesar al sitio en insights de marketing prácticos.

1. [Recopilación de datos](#1-data-collection): El sistema captura los datos de interacción de los usuarios a través del SDK web (Pixel) o de una API de servidor a servidor (S2S).
2. [Registro de visitas](#2-visit-recording)[:](/docs/web-performance-measurement-overview#2-visit-recording) Captura la llegada del usuario al sitio web y registra un evento de visita, incluso cuando todavía no se conoce la fuente de tráfico.
3. [Resolución de la fuente de medios](#3-media-source-resolution): Identifica la fuente de medios analizando los parámetros de la URL en un orden de prioridad definido.
4. [Retraso de identidad de 30 minutos](#4-the-30minute-identity-delay): Retrasa la decisión de atribución durante 30 minutos para permitir la resolución de identidad mediante el login del Usuario.
5. [Vinculación y resolución de identidad](#5-stitching-and-identity-resolution): Enlaza la Sesión actual con un Customer User ID (CUID) persistente o con una cookie del navegador.
6. [Evento de adquisición de usuarios](#6-user-acquisition-ua-event): Registra el evento que define la adquisición (por ejemplo, `first_visit` o un evento de adquisición personalizado) dentro de la ventana de lookback de UA.
7. [Periodo previo a la adquisición](#7-preacquisition-period): Atribuye los eventos intermedios que se producen entre la primera visita y el evento de UA.
8. [Re-engagement y readquisición](#8-reengagement-and-reacquisition): Atribuye a los usuarios que regresan (revisitas) en función de ventanas de inactividad y determina si el regreso es un re-engagement o una readquisición.
9. [Medición de LTV](#9-ltv-measurement): Atribuye los eventos e ingresos continuos para medir el valor de vida útil del Usuario, regido por la Ventana de atribución.

## El proceso de Web Performance Measurement, paso a paso

En las siguientes secciones se explica cada paso en detalle.

<div id="1-data-collection" />

<Accordion title="1. Recopilación de datos">

Una vez que el Usuario llega a la página de destino, AppsFlyer debe capturar esa interacción mediante un listener integrado.

* **SDK web (píxel)**: Un fragmento del lado del cliente <Anchor target="_blank" href="/marketers/es/docs/integrate-appsflyer-web-sdk">implementado directamente en el sitio web o mediante Google Tag Manager (GTM)</Anchor>.
* **API de servidor a servidor (S2S)**: Una integración robusta del lado del servidor que te ayuda a evitar la prevención de la medición en el navegador y los bloqueadores de anuncios, al tiempo que te permite enriquecer los datos antes de que lleguen a AppsFlyer. La integración S2S puede hacerse directamente desde un servidor del cliente o mediante Google Tag Manager Server Side.

</Accordion>

<div id="2-visit-recording" />

<Accordion title="2. Registro de visitas">

Después de recopilar los datos de la sesión, el sistema determina si debe crear un registro de primera visita. Este registro actúa como una capa de preprocesamiento que captura la actividad sin procesar del usuario antes de la resolución real de la fuente de medios y la atribución. No todas las sesiones se registran como visitas.

AppsFlyer registra una visita cuando alguien llega a tu sitio en una nueva sesión o con parámetros de fuente reconocibles, e ignora las visitas de dominios excluidos. Estas reglas de registro de visitas evitan la contabilización doble de las sesiones.

Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/about-traffic-source-resolution#paso-1-registro-de-visitas">Registro de visitas</Anchor>.

</Accordion>

<div id="3-media-source-resolution" />

<Accordion title="3. Resolución de la fuente de medios">

Después de recopilar los datos y registrar la visita, el motor los evalúa según un orden de prioridad definido. Esta cascada admite tanto parámetros específicos de AppsFlyer como parámetros estándar del mercado, por lo que los clientes **no necesitan cambiar sus enlaces de atribución actuales durante la migración**. La primera señal coincidente de la cascada se utiliza para determinar el origen de la visita.

* **PID**: El sistema comprueba primero si hay parámetros propietarios de AppsFlyer.
* **Parámetros UTM**: Si no existe ningún PID, busca etiquetas estándar como `utm_source`.
* **ID de clic**: A continuación, busca ID específicos de la red, como Google Click ID (`gclid`) o TikTok Click ID (`ttclid`).
* **Referrer**: Como último recurso, identifica la URL en la que estaba el usuario inmediatamente antes de llegar.

Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/about-traffic-source-resolution#paso-2-resolución-de-la-fuente-de-medios">Resolución de la fuente de medios</Anchor>.

</Accordion>

<div id="4-the-30minute-identity-delay" />

<Accordion title="4. El retraso de identidad de 30 minutos">

Como la mayoría de los usuarios inician sesión en los 30 minutos posteriores a una visita, AppsFlyer retrasa intencionadamente las decisiones de atribución durante ese mismo tiempo. Este retraso evita una clasificación incorrecta como «orgánico», ya que permite al sistema capturar el CUID y vincular correctamente a los usuarios recurrentes con cookies caducadas a su fuente original.

</Accordion>

<div id="5-stitching-and-identity-resolution" />

<Accordion title="5. Stitching y resolución de identidad">

Una vez identificada la fuente y completado el retraso de 30 minutos, el sistema pasa a "stitching" las sesiones fragmentadas del usuario en un único viaje.

* **CUID Stitching**: Si se captura un Customer User ID (por ejemplo, un correo electrónico con hash), el motor vincula la sesión con el historial entre dispositivos del usuario.
* **Respaldo de cookies**: Si no hay ningún CUID disponible, el sistema recurre a las cookies del navegador, aunque son menos estables y específicas del dispositivo.

</Accordion>

<div id="6-user-acquisition-ua-event" />

<Accordion title="6. Evento de adquisición de usuarios">

Una vez que se resuelve la identidad del usuario, el motor busca la acción específica que lo define como adquirido. El estándar de la industria es `first_visit`, pero a menudo esto representa una señal débil: un usuario puede hacer clic en un anuncio por accidente o abandonar inmediatamente. Al configurar un evento de adquisición personalizado, como un registro o una compra, te aseguras de que el valor a largo plazo (LTV) se atribuya a la fuente de marketing que impulsó una acción significativa, y no solo un clic por curiosidad.

Cuando se produce un evento de adquisición de usuarios, el motor de atribución busca hacia atrás durante un periodo igual a la **ventana de lookback (adquisición de usuarios)** para encontrar una visita no orgánica a la que atribuir. Esta configuración define el tiempo máximo permitido entre la visita de un usuario y la finalización del evento de UA (valor predeterminado: 30 días). Si no se encuentra ningún punto de contacto no orgánico dentro de este periodo de lookback, el evento de UA se considera orgánico y no se atribuye. Puedes configurar la duración de la ventana de lookback del evento personalizado al añadir tu aplicación web a AppsFlyer; consulta <Anchor target="_blank" href="/marketers/es/docs/configure-web-performance-measurement-settings#lookback-window-user-acquisition">Ventana de lookback (adquisición de usuarios)</Anchor>.

Según el modelo de negocio, se pueden definir distintos eventos como desencadenante de la adquisición de usuarios, por ejemplo

* **Evento de registro completado (p. ej., una aplicación bancaria)**. El evento de adquisición se activa solo cuando el flujo de registro se completa correctamente.
* **Evento del primer pedido (p. ej., una aplicación de reparto de comida)**. Navegar o añadir artículos no cuenta; el evento se activa solo después de que la transacción se complete correctamente.
* **Evento de activación de suscripción (p. ej., una aplicación de streaming o SaaS)**. El evento de adquisición se registra cuando se confirma la suscripción, no al iniciar la prueba ni con la instalación de la app.

Para obtener más información sobre cómo configurar un evento de adquisición de usuarios, consulta <Anchor target="_blank" href="/marketers/es/docs/configure-web-performance-measurement-settings#configuración-de-adquisición-de-usuarios">Configuración de adquisición de usuarios</Anchor>.

</Accordion>

<div id="7-preacquisition-period" />

<Accordion title="7. Periodo previo a la adquisición">

Después de que el sistema resuelve la identidad del usuario, pero antes de que se considere adquirido, puede haber una brecha en el recorrido llamada periodo previo a la adquisición. Esto solo es relevante si defines un evento de adquisición de usuarios (UA) personalizado en lugar de usar `first_visit` de forma predeterminada. En este periodo, los usuarios pueden realizar acciones significativas, como añadir artículos al carrito, navegar por productos o interactuar con contenido, antes de completar el evento que oficialmente los adquiere, como el registro o una primera compra.

AppsFlyer recopila y atribuye estos eventos previos a la adquisición a la fuente de marketing y los marca en los reportes como previos a la adquisición. La diferencia clave entre la atribución previa a la adquisición y la posterior a la adquisición es la ventana de atribución. Durante el periodo previo a la adquisición, la ventana de atribución es más corta y coincide con la ventana de lookback del evento de UA, porque estos eventos se producen antes del evento de UA que define al usuario como adquirido. Después de que se activa el evento de UA personalizado y se adquiere al usuario, la ventana de atribución se amplía para medir el valor a largo plazo (LTV), lo que da crédito a largo plazo a la fuente de marketing que adquirió al usuario.

</Accordion>

<div id="8-reengagement-and-reacquisition" />

<Accordion title="8. Re-engagement y readquisición">

Una vez adquirido un usuario, puede volver al sitio más adelante. Se activa una atribución de re-engagement (revisita) cuando un usuario que regresa hace clic en un anuncio y visita tu sitio.

Aunque el *re-engagement* se centra en los usuarios existentes, un regreso también puede clasificarse como una *readquisición* si el usuario ha estado inactivo durante un período prolongado. Para poder optar a la readquisición, el usuario debe primero superar la **ventana de inactividad** (valor predeterminado: 90 días), que define el período de inactividad necesario para considerarlo «churned». Una vez transcurrida esta ventana, si el usuario regresa, el motor registra un nuevo evento de adquisición de usuarios en lugar de una revisita estándar.

Para obtener más información, consulta <Anchor target="_blank" href="/marketers/es/docs/configure-web-performance-measurement-settings#configuración-de-re-engagement">Configuración de Re-engagement</Anchor> y <Anchor target="_blank" href="/marketers/es/docs/configure-web-performance-measurement-settings#configuración-de-re-adquisición">Configuración de readquisición</Anchor>

</Accordion>

<div id="9-ltv-measurement" />

<Accordion title="9. Medición del LTV">

Tanto si el usuario llegó a través de una campaña de adquisición inicial como de una acción posterior de retargeting, el objetivo final es medir su valor total a lo largo del tiempo. Una vez que un usuario se atribuye correctamente a una fuente, el sistema mide su actividad continua para calcular el Lifetime Value (LTV).

Esta medición se rige por la **ventana de atribución**, que está configurada como «Forever» de forma predeterminada. Esto garantiza que cada acción posterior —como compras repetidas o renovaciones de suscripciones— se atribuya a la fuente de marketing original que llevó al usuario al sitio. Al capturar estos datos a largo plazo, puedes ir más allá del simple recuento de conversiones y determinar el verdadero Return on Ad Spend (ROAS) de tus campañas.

Para obtener más información sobre cómo configurar la **ventana de atribución**, consulta la <Anchor target="_blank" href="/marketers/es/docs/configure-web-performance-measurement-settings#ventana-de-atribuciones">Ventana de atribución</Anchor>.

</Accordion>

<div data-zendesk-anchors="about-web-attribution=acerca-de-web-performance-measurement h_01KGMK4P46QE2HQHADD25TPCQF=acerca-de-web-performance-measurement if-you-use-peoplebased-attribution-pba=si-usas-la-atribuci%C3%B3n-basada-en-personas-pba h_01KH0P7BB9KF19S8XRH49DKMZA=si-usas-la-atribuci%C3%B3n-basada-en-personas-pba the-appsflyer-web-attribution-flow=el-flujo-de-web-performance-measurement h_01KGMK4P4614EEQ28V5FV32CY5=el-flujo-de-web-performance-measurement the-appsflyer-web-attribution-process-step-by-step=el-proceso-de-web-performance-measurement-paso-a-paso h_01KGMK4P46HTB82K2PH9V0E33B=el-proceso-de-web-performance-measurement-paso-a-paso h_01KGMK4P46VJ0NF1FKFRS8V6J2=1-data-collection h_01KGMK4P46GWBP56NJM2ENARTR=2-visit-recording h_01KGMK4P46ZKS856R5C5KEQDBK=3-media-source-resolution h_01KGMK4P465777YN9MQ1JYZ7HT=4-the-30minute-identity-delay h_01KGMK4P46GFBZTMHDVW2MD3K1=5-stitching-and-identity-resolution h_01KGMK4P46MBT49ECD7RFHDY3X=6-user-acquisition-ua-event h_01KGMK4P46XYPVFV67F000EM6C=7-preacquisition-period h_01KGMK4P472B4TFGVR4VBH4REH=8-reengagement-and-reacquisition h_01KGMK4P47E9TPX0S26TTPW4CB=9-ltv-measurement" />
