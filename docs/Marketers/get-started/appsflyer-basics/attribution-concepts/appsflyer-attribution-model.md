---
title: Modelo de atribución de AppsFlyer
metadata:
  keywords:
    - Attribution
    - NativeTrack
    - Look-Back
    - Twiiter
    - Multi-Channel
    - Re-Install
    - Facebook
    - media source
    - Advertisers
    - Ad Networks
    - reinstall
    - branch
    - attribution determination
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2015-12-24T10:54:37Z'
  edited_at: '2026-08-17T11:49:40Z'
  id: 207447053
  locale: es
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/es/articles/207447053
---
> **En resumen:** AppsFlyer identifica la fuente de medios que lleva a un usuario a instalar o volver a involucrarse con una aplicación y atribuye la acción del usuario a esa fuente utilizando su modelo de atribución.

<Image align="center" alt="" src="https://files.readme.io/20b5c0674ce4b20df7c82398d7a769274dd8467d129adbaad0d40e4f37d39091-31937603228177.png" />

<div id="what-is-attribution" />

## ¿Qué es la atribución?

La **atribución** consiste en determinar qué ha motivado a un usuario a instalar una aplicación o a realizar acciones posteriores, como el reengagement o la reatribución. El resultado de la atribución puede ser:

* **Una fuente de medios no orgánica**: El usuario interactuó (comúnmente mediante una impresión o un clic) con una fuente de medios.
* **Orgánico**: El usuario no interactuó con una fuente de medios. ¡Nota importante! Para simplificar, a menudo hablamos de un usuario *atribuido orgánicamente*. Sabemos que esto no es totalmente exacto, ya que los usuarios que instalan orgánicamente no están atribuidos.

La atribución es fundamental para optimizar la adquisición de usuarios, las estrategias de reengagement y sus resultados.

<div id="what-is-an-app-install" />

## ¿Qué es una instalación de la aplicación?

El **modelo de atribución** es un conjunto de reglas que decide cómo se asigna el crédito de un evento a los puntos de contacto en los caminos de conversión. Cada componente del ecosistema de marketing de aplicaciones, como Google Play, App Store, Apple, las plataformas CTV, PC y consola, ad networks como Meta Ads y X Ads, y empresas de medición móvil, tiene su propio modelo de atribución. Cada uno cuenta las instalaciones y eventos de manera distinta.

Lo relevante no es tanto la diferencia entre los modelos, sino que las reglas sean claras e imparciales. Esto permite a los anunciantes optimizar campañas y evaluar la calidad del rendimiento de los usuarios de manera efectiva.

Es crucial conocer los modelos y reglas de los actores con los que trabajas. Lo más importante es entender el modelo y las particularidades de los métodos compatibles con AppsFlyer.

En AppsFlyer, un evento atribuible ocurre cuando pasa cualquiera de lo siguiente:

* En el contexto de la adquisición de usuarios: Una **instalación** se registra y atribuye después de que el usuario descarga y abre la aplicación. Esto significa que en AppsFlyer, la **marca temporal de una instalación es la primera apertura** de la aplicación. Por el contrario, las ad networks utilizan el tiempo de engagement y las tiendas de aplicaciones usan el tiempo de descarga.
* En el contexto del [retargeting](/docs/appsflyer-attribution-model#retargeting-attribution):
  * **Reengagement**
  * **Re-atribución**

<div id="attribution-methods" />

## Métodos de atribución

AppsFlyer utiliza varios métodos de atribución, enumerados en la tabla a seguir:

<table><tbody><tr><td>Emitido</td><td>Utiliza el ID del dispositivo</td><td>Técnica</td><td>Atribuido por</td><td>Android (Google Play y tiendas de terceros)</td><td>apps de iOS,</td><td>Universal Windows Platform (UWP)</td><td>Plataformas CTV, PC y consola (3)</td></tr><tr><td> <a href="#install-referrer-android-only">Referencia</a> (1)</td><td>No</td><td>Determinista</td><td>AppsFlyer</td><td>Sí (2)</td><td>No</td><td>Sí</td><td>No</td></tr><tr><td> <a href="#device-id-matching">Coincidencia de ID de dispositivo</a> (1)</td><td>Sí</td><td>Determinista</td><td>AppsFlyer</td><td>Sí</td><td>Sí</td><td>Sí</td><td>Sí</td></tr><tr><td> <a href="#probabilistic-modeling">Modelado probabilístico</a> (1)</td><td>No</td><td>Probabilístico</td><td>AppsFlyer</td><td>Sí</td><td>Sí</td><td>No</td><td>Sí</td></tr><tr><td> <a href="#preload-campaigns">Precarga</a> (1)</td><td>No</td><td>Determinista</td><td>AppsFlyer</td><td>Sí</td><td>No</td><td>Sí</td><td>No</td></tr><tr><td><a href="./skadnetwork-skan-solution-guide" target="_blank">SKAdNetwork (SKAN)</a></td><td>No</td><td>Determinista</td><td>Apple</td><td>No</td><td>Sí</td><td>No</td><td>No</td></tr><tr><td> <a href="./apple-ads-integration-setup" target="_blank">Apple Search Ads</a> (1)</td><td>No</td><td>Determinista</td><td>Apple</td><td>No</td><td>Sí</td><td>No</td><td>No</td></tr><tr><td> <a href="#deep-link">Enlace profundo</a> (1)</td><td>No</td><td>Determinista</td><td>AppsFlyer</td><td>Sí</td><td>Sí</td><td>Sí</td><td>No</td></tr><tr><td colspan="8">(1) A veces se denomina el método de Atribución «clásico» en los dashboard y reportes de AppsFlyer.<br/>(2) Compatible con algunas tiendas de terceros.<br/>(3) Consulta la <a href="./ctv-pc-and-console-platform-attribution-concepts#plataformas-compatibles" target="_blank">lista completa de plataformas CTV, PC y consola</a>.</td></tr></tbody></table>

<div id="attribution-method-priorities-attribution-waterfall" />

### Prioridades de los métodos de atribución (cascada de atribución)

En una nueva instalación, si hay más de un engagement válido, **AppsFlyer prioriza los clics sobre las impresiones y los métodos deterministas sobre los probabilísticos**. Los métodos de atribución se utilizan de acuerdo con las prioridades mostradas en el gráfico.

<Image align="center" alt="af_ip" src="https://files.readme.io/8110571047a972a247d21d5b34d64c3afd010fd733f625ca1321cff93061e374-37555863998865.png" width="1378px" />

Encuentra a continuación descripciones detalladas de los modelos de atribución de AppsFlyer.

<div id="install-referrer-android-only" />

<Accordion title="Referente de instalación (solo Android)">

* Las aplicaciones de Android descargadas de Google Play y algunas otras tiendas de aplicaciones generalmente se atribuyen mediante el método del referente de instalación. El referente proporciona la URL original donde se hizo clic antes de redireccionar a la tienda de Android. Este es el método principal para la atribución en Android. Actualmente, Google Play, la tienda de aplicaciones de Huawei, Samsung Galaxy Store y Xiaomi GetApps Store admiten la atribución mediante referente de instalación. <Anchor target="_blank" href="/marketers/es/docs/set-up-multi-store-android-attribution#referrer-implementation-thirdparty-android-app-stores">Atribución de tiendas de aplicaciones alternativas usando el referente.</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/meta-ads-integration-setup#Meta_install_referrer_anchor">Referente de instalación de Meta:</Anchor> AppsFlyer admite la atribución de anuncios meta para aplicaciones de Android al recibir metadatos de campañas publicitarias del almacenamiento local de un dispositivo. Estos datos se utilizan para la medición de atribución (atribución de Meta en el dispositivo).

</Accordion>

<div id="device-id-matching" />

<Accordion title="Coincidencia de ID de dispositivo">

Un método clásico de atribución en el que la ad network, que tiene acceso al dispositivo del usuario, envía el ID del dispositivo a AppsFlyer en la URL de clic o al notificar a AppsFlyer que se ha servido una impresión. Esto permite a AppsFlyer emparejar el ID del dispositivo del clic con el ID del dispositivo obtenido por el SDK de AppsFlyer.

La coincidencia de ID de dispositivo es el método principal de atribución en iOS.

Los IDs disponibles son:

* **Dispositivos iOS**: IDFA, IDFV
* **Dispositivos Android con servicios de Google Play:** GAID
* **Dispositivos Android sin servicios de Google Play:** OAID, Android ID, IMEI, Fire ID

Los IDs de dispositivos pueden ser codificados con SHA1 o MD5 en los enlaces de atribución.

</Accordion>

<div id="device-id-matching-for-selfreporting-networks" />

<Accordion title="Coincidencia de ID de dispositivo para redes de autoreporte.">

Un método clásico de atribución donde, al iniciar por primera vez la aplicación, AppsFlyer comprueba en la configuración si se espera tráfico de alguna de las <Anchor target="_blank" href="/marketers/es/docs/self-reporting-networks-srns#srns-integradas-con-appsflyer">redes de autoreporte</Anchor> (SRNs), como Meta Ads, Snapchat y Google Ads.

AppsFlyer consulta a las SRNs relevantes utilizando el ID de dispositivo único de la nueva instalación. La consulta hace uso de las APIs de Mobile Measurement Partners (MMP) según lo definido por las SRNs. Dependiendo de la respuesta, AppsFlyer puede atribuir los nuevos usuarios a una SRN.

</Accordion>

<div id="probabilistic-modeling" />

<Accordion title="El modelado probabilístico click-through siempre está activado.">

AppsFlyer utiliza el modelado probabilístico como un método estadístico que preserva la privacidad para reportar el performance de las campañas de marketing de los desarrolladores de apps. Genera reportes agregados del performance de campañas a nivel de campaña para desarrolladores de apps.

**Características de implementación**

* Se basa en estadísticas y no en IDs únicos.
* Estima cuántas instalaciones o engagement se produjeron tras las propias campañas de marketing del desarrollador —anuncios, enlaces de sitios web, correos electrónicos, QR code, SMS u otros medios propios— para su propia aplicación.
* Utiliza solo las señales necesarias para generar un reporte agregado.
* El resultado es un reporte del rendimiento de la campaña, no la identificación de ningún dispositivo ni de un usuario individual.
* Los métodos de atribución determinista, como los clics con referentes o coincidencia de ID, tienen prioridad si ocurren dentro de la ventana de lookback.

</Accordion>

<div id="preload-campaigns" />

<Accordion title="Campañas precargadas">

Un método clásico de atribución para campañas precargadas, cuando las aplicaciones son instaladas en el dispositivo del usuario por un partner de precarga, ya sea en la fábrica o al activar el dispositivo. Los partners de precarga pueden ser:

* Original Equipment Manufacturers (OEMs)
* Plataformas de descubrimiento de aplicaciones
* Operadores móviles

Hay 3 métodos para atribuir campañas precargadas. Los tres métodos pueden utilizarse simultáneamente, ya que no interfieren entre sí.

Los tres métodos y algunas especificaciones clave se presentan en la tabla siguiente. Haz clic en los enlaces para obtener más información sobre cada método de precarga.

<table><thead><tr><th>Método de atribución de precarga</th><th>Caso de uso</th><th>Información desde la activación del dispositivo hasta el inicio de la aplicación\*</th><th>Ventana de lookback\*\*</th><th>Reporte de raw data.</th></tr></thead><tbody><tr><td> <a href="./set-up-appsflyer-preload-referrer-attribution" target="_blank">Referente de AppsFlyer</a>\*</td><td><ul><li>Precargado en fábrica</li><li>Precargado al activar el dispositivo</li></ul></td><td>Sí</td><td><ul><li>Hasta 180 días</li><li>El valor por defecto es 90 días.</li></ul></td><td><ul><li>Precarga: preload_rfr</li><li>Haz clic para descargar: af_referrer</li></ul></td></tr><tr><td> <a href="./measure-preload-campaigns-with-google-play-install" target="_blank">Instalación automática de Google Play</a>\*\*</td><td>Precargado al activar el dispositivo (para aplicaciones de Google Play)</td><td>No</td><td><ul><li>Hasta 180 días</li><li>El valor por defecto es 90 días.</li></ul></td><td>precarga_pai</td></tr><tr><td> <a href="./appsflyer-factory-preinstall-using-manifest-android" target="_blank">Precarga en fábrica vía System Property o manifest (Android)</a>\*\*</td><td><ul><li>Precargado en fábrica</li><li>Precargado al activar el dispositivo</li></ul></td><td>No</td><td>Sin límite</td><td>precarga_conf</td></tr><tr><td colspan="5"><p>\* La solución de precarga de referente de AppsFlyer proporciona capacidades de visibilidad y medición desde la primera activación del dispositivo hasta el primer inicio de la aplicación. Esto te permite ver cuántos dispositivos fueron activados con la aplicación precargada por un partner específico y luego observar cuándo se lanza la aplicación por primera vez.</p><p>Para los otros dos métodos, la atribución solo se determina después de que el usuario inicia la aplicación por primera vez; no está disponible la cantidad de dispositivos que tenían la aplicación instalada antes de ese momento.</p><p>\*\* Puede tardar días o semanas desde que el usuario enciende el dispositivo hasta que abre por primera vez la aplicación precargada. Por ello, AppsFlyer otorga la máxima prioridad a las campañas de precarga en la determinación de la atribución, utilizando ventanas de lookback más largas.</p></td></tr></tbody></table>

</Accordion>

<div id="deep-link" />

<Accordion title="Deep link">

Un método clásico de atribución solo para re-engagements, cuando los usuarios no son redirigidos a una tienda de aplicaciones para descargar la app. Por lo tanto, la información de la URL se puede relacionar directamente con el clic (y la posterior apertura de la app). Este método de atribución se denomina enlace profundo porque es la URL del enlace profundo la que lleva la información utilizada para atribuir el reengagement.

</Accordion>

<div id="attribution-methods-per-media-source-and-appsflyer-feature" />

### Métodos de atribución por fuente de medios y característica de AppsFlyer

Consulta las siguientes secciones para obtener un desglose completo de los métodos de atribución compatibles, dependiendo de:

* Fuente de medios: propia o de pago
* Funcionalidad de AppsFlyer utilizada
* Dispositivo del usuario: Android o iOS

<div id="owned-media" />

<Accordion title="Medios propios">

<table><thead><tr><th rowspan="2">Fuente de medios</th><th rowspan="2">Característica</th><th colspan="2">A diferencia de otros métodos de atribución, el objetivo del algoritmo de aprendizaje automático de AAP es maximizar la precisión del rendimiento agregado de la campaña, y no la precisión de la atribución del usuario final.</th></tr><tr><th>Android</th><th>apps de iOS,</th></tr></thead><tbody><tr><td>Medios propios: correo electrónico (incluidos ESPs), SMS, publicaciones en redes sociales, influencers/afiliados, medios impresos, etc.</td><td><a href="./onelink-guide" target="_blank"><span>OneLink</span></a></td><td><ul><li>Referencia de instalación</li><li>Modelado probabilístico</li></ul></td><td>Modelado probabilístico</td></tr><tr><td rowspan="2">Sitio web móvil/landing page propia con tráfico entrante, ya sea de pago u orgánico</td><td><a href="./smart-banners-mobile-web-to-app-for-marketers" target="_blank">Banners inteligentes</a></td><td><ul><li>Referencia de instalación</li><li>Modelado probabilístico</li></ul></td><td>Modelado probabilístico</td></tr><tr><td><a href="./onelink-smart-script-overview" target="_blank">Smart Script de OneLink</a></td><td><ul><li>Referencia de instalación</li><li>Modelado probabilístico</li></ul></td><td>Modelado probabilístico</td></tr><tr><td rowspan="2">Aplicaciones móviles propias</td><td><a href="./user-invite-attribution" target="_blank">Invitaciones/referencias de usuarios</a></td><td><ul><li>Referencia de instalación</li><li>Modelado probabilístico</li></ul></td><td>Modelado probabilístico</td></tr><tr><td><a href="./cross-promotion-attribution-for-marketers" target="_blank">Promoción cruzada</a></td><td><ul><li>Referencia de instalación</li><li>Coincidencia de ID de dispositivo</li></ul></td><td>Coincidencia de ID de dispositivo usando IDFV (iOS)</td></tr></tbody></table>

</Accordion>

<div id="paid-media" />

<Accordion title="Medios de pago">

<table><thead><tr><th rowspan="2">Fuente de medios</th><th colspan="3">Prioridades de métodos de atribución 23.png</th></tr><tr><th>Android</th><th>apps de iOS,</th><th><strong>Plataformas CTV, PC y consolas</strong></th></tr></thead><tbody><tr><td><a href="./self-reporting-networks-srns" target="_blank">SRN</a></td><td>Coincidencia de ID de dispositivo</td><td><ul><li>Coincidencia de ID de dispositivo</li><li>SKAdNetwork (iOS 14+)</li></ul></td><td>Coincidencia de ID de dispositivo</td></tr><tr><td><ul><li>Ad networks (no SRN) a través de <a href="./set-up-an-integrated-partner#attribution-link-tab" target="_blank">enlaces de atribución para partners</a> </li><li><span>Plataformas CTV, PC y consolas</span></li></ul></td><td><ul><li>Referencia de instalación</li><li>Coincidencia de ID de dispositivo</li><li>Modelado probabilístico</li></ul></td><td><ul><li>Coincidencia de ID de dispositivo</li><li>Modelado probabilístico </li><li>SKAdNetwork (iOS 14+)</li></ul></td><td> </td></tr><tr><td><a href="./appsflyer-factory-preinstall-using-manifest-android" target="_blank">Preinstalado en el dispositivo</a></td><td>Preinstalaciones</td><td>--</td><td> </td></tr></tbody></table>

</Accordion>

<div id="user-engagement-attribution-types" />

## Tipos de atribución por engagement de usuario

La atribución se realiza en función de los engagement de click-through y view-through, utilizando los distintos métodos de medición de campañas de AppsFlyer.

<div id="clickthrough-attribution" />

<Accordion title="Atribución click-through">

La mayoría de las instalaciones son resultado de clics de usuarios en anuncios, como banners, videos e intersticiales.

Al hacer clic en el anuncio, se abre una ventana de lookback con una duración predeterminada de 7 días. Las instalaciones que ocurren dentro de este período no son orgánicas y se atribuyen a la fuente de medios. Las instalaciones que se producen después del final de la ventana de lookback se consideran orgánicas. A menudo se denominan atribuidas orgánicamente.

* Una ventana de lookback de siete días se considera el estándar de la industria. Establece la duración de la ventana según tu acuerdo con la fuente de medios.
* Alinea las ventanas de lookback del SRN con la duración determinada por el propio SRN.

<table><thead><tr><th rowspan="2"> <strong>Tipo de atribución</strong> </th><th rowspan="2"> <strong>Método de atribución</strong> </th><th rowspan="2">Rango</th><th rowspan="2">Rango</th></tr></thead><tbody><tr><td rowspan="2"><p>Click-Through</p><p>(Todos los partners integrados)</p></td><td>Referente, coincidencia de ID</td><td>1–30 días</td><td>7 días</td></tr><tr><td>af_model</td><td>La Privacidad Avanzada Agregada (AAP) es un método clásico de atribución en el cual los resultados del rendimiento de las campañas se exponen de forma agregada, evitando así la posibilidad de registrar usuarios en aplicaciones y sitios web propiedad de distintas empresas, y la capacidad de identificar de manera única a un usuario o dispositivo.</td><td><ul><li>Agregado</li><li>Determinada por AppsFlyer</li></ul></td></tr></tbody></table>

<Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">Obtén más información sobre las ventanas de lookback</Anchor>

</Accordion>

<div id="viewthrough-attribution" />

<Accordion title="Atribución view-through">

Los usuarios que ven anuncios pero no interactúan con ellos pueden atribuirse a las ad networks que los muestra.

La ventana de lookback para la atribución view-through:

* es más corta que la de atribución click-through
* Es configurable.

Esto resulta especialmente útil para las ad networks de video, que tradicionalmente tienen CTR bajos en sus anuncios, pero también para ad networks convencionales.

En los casos donde se produce tanto un clic como una impresión, el **clic siempre prevalece**, ya que representa un engagement activo.

<table><thead><tr><th><strong>Tipo de coincidencia en raw data</strong></th><th><strong>Método de atribución</strong></th><th><strong>Rango</strong></th><th> <strong>Predeterminado</strong><br/> </th></tr></thead><tbody><tr><td rowspan="2"><p>View-through (para <a href="./measure-view-through-engagements#view-vta-partner-list" target="_blank">partners integrados seleccionados</a>)</p></td><td>Coincidencia de ID de dispositivo</td><td>0-24 horas</td><td>1 día</td></tr><tr><td>Parámetros del modelado probabilístico para ad networks</td><td>0-24 horas</td><td><ul><li>af_os_version</li><li>/docs/about-link-structure-and-parameters#af_model</li></ul></td></tr></tbody></table>

**Para activar la atribución view-through:**

* Configura la ventana de lookback en la <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#ventana-retrospectiva-de-atribución-por-visualización">ventana de configuración</Anchor>.

<Anchor target="_blank" href="/marketers/es/docs/measure-view-through-engagements">Atribución de promoción cruzada.</Anchor>

</Accordion>

<div id="engaged-click-attribution" />

<Accordion title="Atribución de clic comprometido">

Los clics comprometidos se producen cuando los usuarios hacen clic en un anuncio y permanecen en el mismo contexto —interactuando con el anuncio— sin ser redirigidos a la tienda de aplicaciones ni abrir la aplicación. Por ejemplo, las interacciones pueden incluir permanecer dentro de un anuncio reproducible, interactuar con elementos dentro del anuncio o seguir navegando por el contenido dentro del contenedor del anuncio. Para más información, consulta: <Anchor target="_blank" href="/marketers/es/docs/about-enriched-engagement-types">Acerca de los tipos de engagement mejorados.</Anchor>

* La ventana de lookback del clic comprometido para la atribución por coincidencia de ID es de 1 a 7 días. El valor predeterminado es de 2 días.
* La ventana de lookback para el modelado probabilístico es de 0 a 24 horas. El valor predeterminado es adaptativo.
* Establece la duración de la ventana según tu acuerdo con la fuente de medios.
* El clic comprometido es compatible con determinados Partners integrados.
* Los clics comprometidos comparten la misma prioridad de atribución que click-to-download y click-to-app.

| Tipo de atribución | Método de atribución | Rango | Predeterminado |
| --- | --- | --- | --- |
| Inicialmente, al hacer clic o al ver un anuncio (si está habilitado) | El SDK de AppsFlyer recopila IDFV por defecto. | AAP (iOS 14.5+) | Sí |
|  | Modelado probabilístico (antes de iOS 14.5) | La Privacidad Avanzada Agregada (AAP) es un método clásico de atribución en el cual los resultados del rendimiento de las campañas se exponen de forma agregada, evitando así la posibilidad de registrar usuarios en aplicaciones y sitios web propiedad de distintas empresas, y la capacidad de identificar de manera única a un usuario o dispositivo. | <ul><li>Adaptativo</li><li>/docs/about-link-structure-and-parameters#af\_ip</li></ul> |

<Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">Para aplicaciones de CTV, PC y consola, la ventana de atribución se determina por el parámetro de enlace `af_lookback_window`, pero no puede exceder los 7 días.</Anchor>

</Accordion>

<div id="engaged-view-attribution" />

<Accordion title="Atribución de visualización comprometida">

Las visualizaciones comprometidas se producen cuando los usuarios ven un anuncio y realizan una acción válida —como ver un vídeo más allá de un determinado umbral o interactuar con una unidad de anuncio— sin hacer clic. Estas acciones indican intención y se utilizan para atribuir la instalación. Para más información, consulta: <Anchor target="_blank" href="/marketers/es/docs/about-enriched-engagement-types">Acerca de los tipos de engagement mejorados.</Anchor>

* La ventana de lookback de la visualización comprometida es de 0 a 24 horas tanto para la atribución determinística como para la probabilística.
* La ventana de lookback predeterminada para la atribución determinística es de 2 días.
* La visualización comprometida es compatible con determinados Partners integrados.
* Las visualizaciones comprometidas comparten la misma prioridad de atribución que los clics comprometidos y click-to-app.

| Audiences. | Método de atribución | Rango | Rango |
| --- | --- | --- | --- |
| [Privacidad avanzada agregada (AAP)](#aggregated-advanced-privacy-aap) (1) | Coincidencia de ID | AAP (iOS 14.5+) | Consejo |
|  | Modelado probabilístico | 0–24 horas | <ul><li>Adaptativo</li><li>Determinado por AppsFlyer</li></ul> |

**Las ad networks que implementan la atribución mediante modelado probabilístico deben enviar los siguientes parámetros a través del enlace de atribución o mediante los encabezados de solicitud HTTP:**

* <Anchor target="_blank" href="https://developer.apple.com/documentation/uikit/uidevice/1620059-identifierforvendor">Según Apple,</Anchor> *el valor de esta propiedad es el mismo para las aplicaciones que provienen del mismo proveedor y se ejecutan en el mismo dispositivo.*

<Anchor target="_blank" href="/marketers/es/docs/measure-view-through-engagements">Obtén más información sobre la atribución view-through</Anchor>

</Accordion>

<div id="advanced-attribution-topics" />

## Temas avanzados de atribución

<div id="in-app-events" />

<Accordion title="Y nuevamente cuando se inicia la aplicación">

AppsFlyer utiliza el ID del dispositivo o ID único de AppsFlyer para atribuciones (como una instalación, reinstalación o reatribución de la app) para **atribuir eventos in-app a la fuente de medios**. Los anunciantes pueden utilizar esta información para seguir los viajes de los usuarios en los raw data de su app. En el agregado diario, el ID del dispositivo/ID de AppsFlyer se utiliza para calcular el número de usuarios únicos, por ejemplo, la cantidad de usuarios únicos que realizan un evento in-app.

Para más información sobre la atribución de eventos, haz clic <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview?query=in%20app%20event#how-does-appsflyer-attribute-events">aquí</Anchor>.

</Accordion>

<div id="assisted-installs" />

<Accordion title="Atribución de reinstalación en el mismo dispositivo.">

AppsFlyer atribuye completamente solo una fuente de medios por instalación, generalmente utilizando el último clic en el anuncio o la última impresión (si no hubo clics).

Las instalaciones asistidas (también llamadas atribución multitáctil) son instalaciones en las que la fuente de medios o campaña no fue el último punto de contacto, sino que interactuó con el usuario antes de la instalación, dentro de la ventana de atribución.

Las redes que ayudan se muestran como contribuyentes a la instalación en AppsFlyer.

Para más información, haz clic <Anchor target="_blank" href="/marketers/es/docs/measure-assisted-installs">aquí</Anchor>.

</Accordion>

<div id="reinstalls" />

<Accordion title="Reinstalaciones">

Una reinstalación ocurre cuando un usuario instala la aplicación, la desinstala y luego vuelve a instalarla. La atribución de reinstalación está regulada por la <Anchor target="_blank" href="/marketers/es/docs/set-up-re-attribution-window">ventana de reatribución</Anchor> de la siguiente manera:

* Si la reinstalación se produce después de que expire la ventana de reatribución: se registra una nueva instalación.
* Si la reinstalación ocurre durante la ventana de reatribución, se aplica una de las siguientes situaciones:
  * Si el usuario interactuó con una campaña de retargeting antes de la reinstalación: se registra una <Anchor target="_blank" href="/marketers/es/docs/retargeting-attribution-guide">reinstalación de retargeting</Anchor> (también conocida como reatribución).
  * Si el usuario no interactuó con ninguna campaña o solo participó en una campaña de UA: no se registra ninguna instalación. Dependiendo del estado de <Anchor target="_blank" href="/marketers/es/docs/measure-reinstalls#overview">**Atribución de eventos posteriores a la reinstalación**</Anchor>, los eventos in-app de estos usuarios que reinstalan la aplicación se atribuyen a la instalación orgánica o a la original.

Para probar el dispositivo y realizar múltiples instalaciones, <Anchor target="_blank" href="/marketers/es/docs/registering-test-devices">registra</Anchor> el dispositivo en AppsFlyer. Si no se registra el dispositivo, solo se registrará la primera instalación.

Ten en cuenta que AppsFlyer permite mayor precisión al atribuir reinstalaciones de iOS sin un ID de anunciante. Puedes activar esta función en la <Anchor target="_blank" href="/marketers/es/docs/app-settings#reinstall-detection-using-ondevice-storage-ios-only">página de configuración de la aplicación</Anchor>.

<div id="reinstalling-ios-apps-that-are-backed-up-in-icloud" />

#### Reinstalar aplicaciones de iOS respaldadas en iCloud

Cuando una aplicación se respalda utilizando iCloud y luego se restaura (en el mismo dispositivo o en otro), AppsFlyer no la cuenta como una nueva instalación o reinstalación. Un usuario que restaura una aplicación desde iCloud conserva su ID de AppsFlyer y sus datos de atribución.

</Accordion>

<div id="retargeting-attribution" />

<Accordion title="Atribución de retargeting">

<Image align="center" alt="Retargeting_-_Flujo__2_.png" src="https://files.readme.io/64b8d9f5040daa281ae13f0855749ab4a88a2e7e8616d6ada37975899db92c80-31937591646097.png" />

Un usuario que reinstala una aplicación dentro de la <Anchor target="_blank" href="/marketers/es/docs/set-up-re-attribution-window">ventana de reatribución</Anchor> (por defecto, 90 días) se considera una reatribución. Si esta instalación ocurre tras interactuar con una campaña de retargeting, se registra como una reinstalación de retargeting, también conocida como reatribución, y se reporta en <Anchor target="_blank" href="/marketers/es/docs/retargeting-attribution-guide">retargeting</Anchor>.

</Accordion>

<div id="app-updates" />

<Accordion title="Actualizaciones de la aplicación">

* Cuando los usuarios ya existentes actualizan la aplicación a una versión posterior, no se considera un evento atribuible, si el usuario fue previamente atribuido por AppsFlyer. ¡Atención! ¡Importante! Si migras a AppsFlyer desde otro MMP, los usuarios ya existentes en la primera apertura de la app tras la migración, se atribuyen como orgánicos.
* Las métricas relacionadas con el número de usuarios por versión de la app están disponibles en el <Anchor target="_blank" href="/marketers/es/docs/sdk-information-version-consent-dashboard">dashboard de información del SDK</Anchor>.

</Accordion>

<div data-zendesk-anchors="what-is-attribution=qu%C3%A9-es-la-atribuci%C3%B3n 01H8GG9XPSS8KA9CHPD6ECNR2J=qu%C3%A9-es-la-atribuci%C3%B3n what-is-an-app-install=qu%C3%A9-es-una-instalaci%C3%B3n-de-la-aplicaci%C3%B3n 01EDRHGMTXK94Y97DPKFAMCJ5B=qu%C3%A9-es-una-instalaci%C3%B3n-de-la-aplicaci%C3%B3n attribution-methods=m%C3%A9todos-de-atribuci%C3%B3n 01EDRHGMTXCRNVXS9JGHQ1JAQT=m%C3%A9todos-de-atribuci%C3%B3n attribution-waterfall=prioridades-de-los-m%C3%A9todos-de-atribuci%C3%B3n-cascada-de-atribuci%C3%B3n h_01JBC8582ABTE00W29PM5Y5X0B=prioridades-de-los-m%C3%A9todos-de-atribuci%C3%B3n-cascada-de-atribuci%C3%B3n 01H8GG9XPS6P3CXX5AN2KY8WN4=install-referrer-android-only 01H8GG9XPSGVK90FV0K9HZARH7=device-id-matching 01H8GG9XPSV247F3JRCR870JK0=device-id-matching-for-selfreporting-networks 01EDRHGMTXHAKWZK99Q2X86BND=probabilistic-modeling 01H8GG9XPSZ5CPKNSCV7NF1MKW=preload-campaigns h_01K0XWKWQ7TJ2DBT1JZPY5Q4F6=deep-link attribution-methods-per-media-source-and-appsflyer-feature=m%C3%A9todos-de-atribuci%C3%B3n-por-fuente-de-medios-y-caracter%C3%ADstica-de-appsflyer 01H8GG9XPTXDR41QANF4XVSZMM=m%C3%A9todos-de-atribuci%C3%B3n-por-fuente-de-medios-y-caracter%C3%ADstica-de-appsflyer 01H8GG9XPT65G88DE8548HZREE=owned-media 01H8GG9XPTADWMQ37WBB6P9WVS=paid-media user-engagement-attribution-types=tipos-de-atribuci%C3%B3n-por-engagement-de-usuario 01EDRHGMTX7851H14R20F9KNAN=tipos-de-atribuci%C3%B3n-por-engagement-de-usuario 01EDRHGMTXJ7WKTWQXFCHTD9AV=clickthrough-attribution 01EDRHGMTXN0Y0ZRVBX7HHW7NN=viewthrough-attribution h_01K0XYZWBVPSXT0T6XGPQT20X8=engaged-view-attribution advanced-attribution-topics=temas-avanzados-de-atribuci%C3%B3n 01EDRHGMTYYXBSCDPKXCDK1641=temas-avanzados-de-atribuci%C3%B3n 01EDRHGMTYMH3SVNBTQ28D4F42=in-app-events h_01K0XWKWQ7J20YKEND9A43DRNR=assisted-installs 01EDRHGMTY2CF0B70T3RAGPCJ1=reinstalls reinstalling-ios-apps-that-are-backed-up-in-icloud=reinstalar-aplicaciones-de-ios-respaldadas-en-icloud 01EDRHGMTYDSNJKQNPNYFXJPAZ=reinstalar-aplicaciones-de-ios-respaldadas-en-icloud 01EDRHGMTYYB9XVM5CBWSPJGMN=retargeting-attribution 01EDRHGMTYTQRMG1W7ZBW4G6W4=app-updates" />
