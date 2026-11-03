---
title: Sobre la estructura y los parámetros del enlace
metadata:
  keywords:
    - pid
    - Marketers
    - af_
    - af
    - c
    - af_mp
    - clickid
    - af_siteid
    - af_sub_siteid
    - af_c_id
    - af_adset_id
    - af_ad_type
    - af_viewthrough
    - af_cost_model
    - af_cost_value
    - af_web_dp
    - af_ref
    - af_ip
    - af_os_version
    - deep_link_sub
    - deep_link_value
    - af_og_title
    - af_og_description
    - af_og_image
    - af_prt
    - af_adset
    - af_ad
    - af_ad_id
    - af_channel
    - af_keywords
    - af_cost_currency
    - af_sub
    - af_r
    - af_dp
    - af_force_deeplink
    - is_incentivized
    - af_param_forwarding
    - af_partner_account_id
    - af_ua
    - af_os
    - af_model
    - af_media_type
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2015-12-24T11:50:00Z'
  edited_at: '2026-08-22T00:08:54Z'
  id: 207447163
  locale: es
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/es/articles/207447163
---
> **En resumen:**  Descubre la estructura y los parámetros del enlace de atribución de AppsFlyer.

## Visión general

Los enlaces de atribución permiten a los anunciantes recopilar datos sobre cómo interactúan los usuarios con un anuncio. Estos enlaces se colocan detrás de los anuncios y notifican a AppsFlyer cuando los usuarios interactúan. La interacción puede ser un clic en un anuncio o simplemente ver el anuncio. AppsFlyer recibe una copia de la URL de atribución.

Los enlaces de atribución se generan utilizando **OneLink** o un **enlace de plataforma única**.

|  | OneLink (enlace multiplataforma) | Enlace de plataforma única |
| --- | --- | --- |
| Descripción y cuándo utilizarlos | Utilízalo cuando:<ul><li>Necesitas un único enlace para todas las plataformas.</li><li>Requiere capacidades de deep linking.</li><li>Deseas utilizar enlaces de aplicaciones de Android o Universal Links de iOS para abrir la app.</li></ul><Anchor target="_blank" href="/marketers/es/docs/onelink-guide">Más información sobre OneLink</Anchor> | Utilízalo cuando:<ul><li>Solo cuando utilizas una plataforma única. Por ejemplo, Android, pero no iOS.</li><li>Empleas exclusivamente esquemas URI para abrir la aplicación.</li></ul><Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#attribution-link-tab">Aprende a configurar un partner integrado</Anchor> |
| Requisitos previos | <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template">Plantilla de OneLink</Anchor> | Ninguno |
| Información a incluir | <ul><li>[Fuente de medios](/docs/about-link-structure-and-parameters#partner-id-pid-parameter)</li><li>[Campaña](#c)</li><li>[ID de sitio / ID de subsitio](/docs/about-link-structure-and-parameters#site-id-parameter)</li></ul> | <ul><li>[Fuente de medios](/docs/about-link-structure-and-parameters#partner-id-pid-parameter)</li><li>[Campaña](#c)</li><li>[ID de sitio / ID de subsitio](/docs/about-link-structure-and-parameters#site-id-parameter)</li></ul> |
| URL base | `{subdomain}`.onelink.me | app.appsflyer.com |
| Identificador único | ID de plantilla | id\_aplicación |
| Estructura de URL | `https://{subdomain}.onelink.me/``{templateid}?pid={media_source}``&af_siteid={ApplicationID}``&c={CampaignName}` | `https://app.appsflyer.com/{app_id}?pid={media_source}&af_siteid={ApplicationID}&c={CampaignName}` |
| Ejemplo | `https://yourbrand.onelink.me/aAB1?pid=greatnetwork_int``&c=GreatCampaign&af_siteid=A1b1` | `https://app.appsflyer.com/com.greatapp?pid=greatnetwork_int&``c=GreatCampaign&af_siteid=A1b1` |

> 🚧 **Importante:**
>
> AppsFlyer admite solo el protocolo HTTPS para el tráfico entrante de engagement, es decir, clics e impresiones.

## Parámetros del enlace de atribución

* Los parámetros enumerados están disponibles para su uso en el enlace de atribución.
* La columna **tipo de campo** indica el límite de caracteres del valor del parámetro. Para más información sobre las limitaciones de longitud de los valores de los parámetros, haz clic <Anchor target="_blank" href="/marketers/es/docs/raw-data-field-dictionary">aquí.</Anchor>

### Parámetros de enlace de atribución: UA y retargeting

La siguiente tabla se puede [descargar como archivo `.csv`](https://docs.google.com/spreadsheets/d/e/2PACX-1vTZQnoDdFo2NxBuWXBs5gGgvkGU2pr_hn58H9Dtf5uHBAHv4Io89Wd44rRtL24pRsOXHthnBitaOyfp/pub?gid=0&single=true&output=csv).

<div id="attribution-parameters" />

| Parámetro | Nombre para mostrar en raw data | Descripción | Tipo de campo y longitud |
| --- | --- | --- | --- |
| <span id="pid"></span>PID | Fuente de medios | Identifica de forma única a un partner integrado de AppsFlyer. No lo cambies. [Más detalles](/docs/about-link-structure-and-parameters#partner-id-pid-parameter). | <span id="PID"></span>Cadena 150 |
| <span id="c"></span>C | Campaña | Proporcionado por el anunciante o el publisher. Consulta los [límites en los nombres de campaña](/docs/about-link-structure-and-parameters#what-limits-are-there-on-campaign-names). | <span id="Campaign"></span>Cadena |
| <span id="af_prt"></span>af\_prt | Fuente de medios | <ul><li>El nombre de la cuenta de la agencia permite atribuir las instalaciones a dicha agencia</li><li>**Precaución**: No utilices este parámetro antes de asegurarte de que los **Permisos de agencia** estén habilitados</li></ul> | Cadena 50 |
| <span id="af_mp"></span>af\_mp | N/D | <ul><li>Habilita el envío de postbacks a partners de marketing del publisher por instalación.</li><li>**Nota**: Actualmente, este parámetro solo es relevante para los partners de marketing de Pinterest.</li></ul> |  |
| <span id="clickid"></span>clickid | N/D | Identificador único de clic de la ad network |  |
| <span id="af_siteid"></span>af\_siteid | ID del sitio | <ul><li>ID único que identifica al publisher que muestra el anuncio. [Saber más](/docs/about-link-structure-and-parameters#site-id-parameter)</li></ul> | <span id="Site_id"></span>Cadena 24 |
| <span id="af_sub_siteid"></span>af\_sub\_siteid | ID del subsitio | <ul><li>ID de subred publicitaria/ID del publisher.</li><li>Si, además del publisher principal (ID del sitio), hay un subeditor o deseas incluir información adicional, como tipo de anuncio/ubicación dentro de la aplicación, como banner, intersticial, vídeo, etc., utiliza af\_sub\_siteid. Por ejemplo: af\_sub\_siteid =ABCD\_4567</li></ul> | Cadena |
| <span id="af_c_id"></span>af\_c\_id | ID de campaña | Proporcionado por el anunciante/publisher | Cadena 24 |
| <span id="af_adset"></span>af\_conjunto de anuncios | Conjunto de anuncios | <ul><li>Proporcionado por el anunciante/publisher.</li><li>El conjunto de anuncios es un nivel intermedio en la jerarquía entre Campaña y Anuncio. [Ver más](/docs/about-link-structure-and-parameters#niveles-de-granularidad-de-datos)</li></ul> | Cadena 100 |
| <span id="af_adset_id"></span>af\_adset\_id | ID del adset | Proporcionado por el anunciante/publisher | Cadena 24 |
| <span id="af_ad"></span>af\_anuncio | Anuncio | Nombre del anuncio ([ver más](/docs/about-link-structure-and-parameters#niveles-de-granularidad-de-datos)) proporcionado por el anunciante/publisher | Cadena 100 |
| <span id="af_ad_id"></span>id\_del\_anuncio\_af | ID del anuncio | Proporcionado por el anunciante/publisher | Cadena 24 |
| <span id="af_ad_type"></span>af\_ad\_type | Tipo de anuncio | Utiliza las siguientes convenciones de nomenclatura:<ul><li>**native**: Medios pagados diseñados para coincidir con el contenido de una fuente de medios. Este medio está diseñado para coincidir con el diseño visual y la función del contenido natural, apareciendo en tu feed de vídeos recomendados.</li><li>**banner**: Anuncios gráficos, típicamente pequeños rectángulos que se muestran en varias partes de una página web o interfaz de una aplicación.</li><li>**interstitial**: Anuncios de pantalla completa que cubren toda la interfaz de la aplicación anfitriona. Estos anuncios están diseñados para colocarse entre contenido y generalmente se muestran en puntos de transición dentro del flujo de la aplicación, como entre actividades o niveles de juego, o mientras se encuentra en pausa.</li><li>**rewarded\_video**: Anuncios que los usuarios pueden elegir ver hasta el final a cambio de una recompensa dentro de la aplicación, como ver un vídeo para obtener una vida extra en el juego, acceder a un artículo o conectarse a Wi-Fi en un aeropuerto. Estos anuncios “recompensados” atraen a los usuarios y ofrecen una experiencia general mejorada en la aplicación.</li><li>**audio**: Anuncios en formato de audio presentados dentro de podcasts online o plataformas de transmisión de música.</li><li>**offerwall**: Una unidad publicitaria en la aplicación que los desarrolladores utilizan para monetizar sus aplicaciones. Funciona como una mini-tienda dentro de la aplicación, listando múltiples “ofertas” que los usuarios pueden completar a cambio de una recompensa dentro de la aplicación.</li></ul> | Cadena 24 |
| <span id="af_ad_format"></span>af\_ad\_format | Formato de anuncio | Utiliza las siguientes convenciones de nomenclatura:<ul><li>**text**: Un anuncio basado en texto que suele aparecer como un breve fragmento de texto. Puede incluir un titular, una descripción y un enlace o llamado a la acción, diseñados para generar interés y fomentar un clic hacia un sitio web o una página de destino.</li><li>**image**: Un anuncio visual que destaca un producto, servicio o marca a través de gráficos o fotografías. Suele incluir una imagen atractiva acompañada de un texto conciso y puede incorporar un llamado a la acción.</li><li>**video**: Un anuncio digital que utiliza contenido audiovisual para transmitir un mensaje de marketing. Puede variar en duración y aparecer como pre-roll, mid-roll o post-roll dentro del contenido de vídeo online o como vídeos independientes en varias plataformas.</li><li>**playable**: Un anuncio interactivo que permite a los usuarios probar una versión en miniatura de un juego o aplicación antes de descargarlo o realizar una compra. Ofrece a los usuarios una experiencia directa del juego real o de la funcionalidad de la aplicación.</li><li>**interactive**: Un anuncio motivador y dinámico que invita a los usuarios a interactuar o participar. Puede incluir cuestionarios, encuestas u otros elementos interactivos para captar la atención de los usuarios y fomentar su participación activa.</li><li>**dynamic\_product**: Un formato de anuncio personalizado que rellena dinámicamente información y detalles del producto según el comportamiento, las preferencias o el historial de navegación del usuario. Permite a los anunciantes mostrar anuncios de productos altamente relevantes y adaptados a cada individuo.</li><li>**carousel**: Un formato de anuncio que consta de varias diapositivas o tarjetas dentro de un solo anuncio. Cada tarjeta puede incluir una imagen, un titular y una descripción diferentes, permitiendo a los anunciantes mostrar múltiples productos o características en un solo anuncio.</li></ul> |  |
| <span id="af_click_lookback"></span>af\_click\_lookback | Ventana de lookback de atribución | <ul><li>Ventana de lookback para atribución de clics. La duración de esta ventana es el CTIT (tiempo de clic para instalar) máximo para que un nuevo usuario sea atribuido a la fuente que muestra el anuncio/enlace.</li><li>Número de días configurable para el período de atribución de clics de lookback. Valores de parámetros disponibles: 1d-30d (días) O 1h-23h (horas). El valor predeterminado es 7d.</li><li>La ventana de lookback se puede personalizar para <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows#configuración-de-la-ventana-de-lookback">OneLinks y SRNs</Anchor>.</li></ul>**Nota**: Solo afecta a las URLs de clic y no a las URLs de impresión. | Máximo 3 caracteres |
| <span id="af_viewthrough_lookback"></span>af\_viewthrough\_lookback | N/D | <ul><li>Número de horas configurable para el período de atribución de visualización view-through. Valores de parámetros disponibles: 1h - 24h (horas). El valor predeterminado es 24h.</li><li>La ventana de lookback se puede personalizar para <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows#configuración-de-la-ventana-de-lookback">SRNs</Anchor>.</li></ul>**Nota**: Solo afecta a las URL de impresión y no a las URLs de clic | Máximo 3 caracteres |
| <span id="af_channel"></span>af\_canal | Canal | El canal de origen de medios a través del cual se distribuyen los anuncios, por ejemplo, UAC\_Search, UAC\_Display, Instagram, Meta Audience Network, etc. | Enumeración dinámica. Cadena 20 |
| <span id="af_engagement_destination"></span>af\_engagement\_destination | Destino de engagement | Indica la categoría del destino vinculado desde el anuncio, como una landing page **web**, una aplicación **móvil** (a través de un deep link o una tienda de aplicaciones) u otros tipos de destino, como **CTV**, **PC** o **consola**. | Cadena 50 |
| <span id="af_keywords"></span>af\_palabras\_clave | Palabras clave | Lista de palabras clave para campañas dirigidas por texto. | Cadena 100 |
| <span id="af_cost_model"></span>af\_modelo\_de\_coste | Modelo de costos | <ul><li>El modelo de costo, CPI (por defecto), es actualmente el único modelo compatible al informar del costo por clic, que completa el <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#cost-data-availability-and-reports">valor del costo en los reportes de datos agregados de AppsFlyer</Anchor>.</li><li>Siempre que sea posible, informe del costo por <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#cost-aggregation-methods">API.</Anchor> En los casos donde el costo se informa tanto en el enlace como por API, la API tiene prioridad.</li></ul> | Cadena 20 |
| <span id="af_cost_currency"></span>af\_cost\_currency | Moneda del costo | <ul><li>Código de moneda de 3 letras que cumple con la norma <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#cost-aggregation-methods">ISO-4217</Anchor>. Por ejemplo, USD, ZAR, EUR</li><li>[Por defecto]: USD</li></ul> | Enumeración. 3 caracteres |
| <span id="af_cost_value"></span>af\_valor\_de\_coste | Valor del costo | <ul><li>Valor del costo utilizando la moneda establecida.</li><li>Hasta 4 dígitos después del punto decimal.</li><li>Indica SOLO dígitos numéricos (utiliza un punto decimal si es necesario) Ejemplo: "56", "2.85"</li></ul> | Suscripción IAP |
| <span id="af_sub-n-n15-example-af_sub1"></span>af\_sub[n]<br /><br />(n=1-5) ejemplo: af\_sub1 | Subparámetro [n] | Parámetro personalizado opcional definido por el anunciante. Para más información sobre el uso de estos parámetros, consulta la sección [Características y limitaciones](/docs/about-link-structure-and-parameters#características-y-limitaciones). | Cadena 100 |
| <span id="af_r"></span>af\_r | N/D | Se utiliza para redireccionar a los usuarios a la URL especificada en **todas las plataformas** (Android, iOS y ordenador).<br /><br />En los enlaces multiplataforma (OneLink), este parámetro:<ul><li>Sobrescribe la configuración de redirección a nivel de plantilla</li><li>Es sobrescrito por los siguientes parámetros a nivel de enlace:<ul><li>[`af_android_url`](/docs/about-link-structure-and-parameters#af_android_url)</li><li>[`af_ios_url`](/docs/about-link-structure-and-parameters#af_ios_url)</li><li>[`af_web_dp`](/docs/about-link-structure-and-parameters#af_web_dp)</li></ul></li></ul>**Nota:** Mira las [características y limitaciones](/docs/about-link-structure-and-parameters#special-characters) adicionales del parámetro de redirección. |  |
| <span id="af_web_dp"></span>af\_web\_dp | N/D | URL para redireccionar a los usuarios de ordenador (por ejemplo, Windows o Mac) a una página web diferente a la configurada en la plantilla de OneLink. Utiliza esto para mantener los datos de atribución de usuarios de ordenador en otras plataformas (por ejemplo, Google Analytics u Omniture).<br /><br />**Nota:** Mira las [características y limitaciones](/docs/about-link-structure-and-parameters#special-characters) adicionales del parámetro de redirección. |  |
| <span id="af_dp"></span>af\_dp | N/D | El valor de respaldo del esquema URI para iniciar la aplicación, que se utilizará si falla el método Universal Link o Android App Link, y para usuarios de Android anteriores a 6.0. Debe apuntar solo a la <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">ruta base</Anchor>, es decir, la actividad predeterminada.<br /><br />**Nota:** Si utilizas un valor de URL web para este parámetro (no recomendado), asegúrate de revisar las [características y limitaciones](/docs/about-link-structure-and-parameters#special-characters) de los parámetros de redireccionamiento. |  |
| <span id="af_force_deeplink"></span>af\_force\_deeplink | N/D | <Anchor target="_blank" href="/marketers/es/docs/onelink-troubleshooting-and-faq">Forzar deep linking</Anchor> en la actividad especificada en el valor af\_dp |  |
| <span id="af_ref"></span>af\_ref | N/D | Las ad networks que trabajan con clics S2S pueden enviar un valor de referencia único usando el siguiente parámetro: &af\_ref=**ReferrerValue**<br /><br />El valor af\_ref **debe** consistir en un valor único, estructurado de la siguiente manera:<br /><br />**NetworkName\_UniqueClickValueForEachClick**<br /><br />Ejemplo: af\_ref=networkname\_123456789ABCDEF<br /><br />El nombre de la red puede ser cualquier cadena válida. Puede ser networkname\_int o simplemente el nombre de la red.<br /><br />AppsFlyer puede utilizar este parámetro para la atribución en dispositivos Android. AppsFlyer no utiliza este parámetro para la atribución en dispositivos iOS o Windows. |  |
| <span id="is_incentivized"></span>is\_incentivized | N/D | Booleano: true/false<br /><br />Campañas con o sin incentivos |  |
| <span id="af_param_forwarding"></span>af\_param\_forwarding | N/D | <ul><li>Cuando se establece en falso, los parámetros del enlace de atribución no se reenvían a la página redireccionada.</li><li>Utiliza esto para obtener una URL más limpia en la página redirigida, o si los parámetros del enlace de atribución podrían causar problemas debido al manejo de parámetros de consulta en la página redirigida.</li></ul> |  |
| <span id="af_base_params_forward"></span>af\_base\_params\_forward | N/D | <ul><li>Cuando se establece en falso, los parámetros PID y C de AppsFlyer en el enlace de atribución no se reenvían a la página redireccionada.</li><li>Utiliza esto si la URL se hace clic desde un ordenador y deseas que los parámetros CRM esenciales permanezcan, pero que se eliminen los parámetros C y PID de AppsFlyer. Esto evitará que haya múltiples PID en la URL.</li></ul> |  |
| <span id="af_partner_account_id"></span>af\_partner\_account\_id | ID de cuenta de red | ID de cuenta del anunciante con el partner | Cadena 100 |
| <span id="af_redirect"></span>Redirigir | N/D | Cuando `&redirect=false`, este parámetro indica a AppsFlyer que se trata de un clic S2S y que el partner es responsable de redireccionar al usuario que hizo clic. |  |
| <span id="af_ua"></span>af\_ua | Agente de usuario | Relevante para las ad networks que envían clics e impresiones de <Anchor target="_blank" href="/partners/es/docs/redirecting-users-to-the-app-store">servidor a servidor</Anchor>.<br /><br />**Importante:** No uses `af_ua` en enlaces cliente-servidor (C2S). Usando `af_ua` en un enlace C2S puede afectar la atribución.<br /><br />La cadena del agente de usuario se envía como:<ol><li>Parámetro URL (codificado en URL)</li><li>Encabezado de solicitud HTTP (sin codificar)</li></ol>El agente de usuario debe ser **idéntico tanto en el parámetro URL como en el encabezado HTTP**.<br /><br />En **Android**, el agente de usuario a veces se reduce debido a sugerencias del cliente. Debe enviarse de todos modos.<ul><li>**Ejemplo de user-agent completo:** `Mozilla/5.0 (Linux; Android 12; Pixel 5) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/95.0.4638.16 Mobile Safari/537.36`</li><li>**Ejemplo de user-agent completo: reducido:** `Mozilla/5.0 (Linux; Android 10; K) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/95.0.0.0 Mobile Safari/537.36`</li></ul>**En iOS**, a partir de iOS 26, se agrega la versión.<br />Aquí tienes:<ul><li>**Un ejemplo de la parte adjunta:** `Version/26.0.1 Mobile/15E148 Safari/604.1`</li><li>**Un ejemplo del user-agent completo:**<br />`Mozilla/5.0 (iPhone; CPU iPhone OS 16_4_1 like Mac OS X) AppleWebKit/8615.1.26.10.24 (KHTML, like Gecko) Mobile/20E252 Version/26.0.1 Mobile/15E148 Safari/604.1`</li></ul> |  |
| <span id="af_ip"></span>af\_ip | IP | Relevante para las ad networks que envían clics e impresiones de <Anchor target="_blank" href="/partners/es/docs/redirecting-users-to-the-app-store">servidor a servidor</Anchor>.<br /><br />**Importante:** No uses `af_ip` en enlaces cliente-servidor (C2S). Usando `af_ip` en un enlace C2S puede afectar la atribución.<br /><br />**Dirección IP del dispositivo**<br /><br />**Recomendado**: Si está disponible, proporciona la dirección IP del dispositivo en el parámetro `af_ip`.<br /><br />**Siguiente opción**: Si está disponible, AppsFlyer usará la IP en X-Forwarded-For. |  |
| <span id="deprecated--af_os"></span>[En desuso] af\_os | Versión de SO | [Solo para iOS] La versión del sistema operativo del dispositivo.<br /><br />Este parámetro está en desuso, pero AppsFlyer aún lo admite. Recomendación: Use el parámetro af\_os\_version en lugar de este. |  |
| <span id="af_os_version"></span>af\_os\_version | Versión de SO | <ul><li>Relevante para las ad networks que envían clics e impresiones de <Anchor target="_blank" href="/partners/es/docs/redirecting-users-to-the-app-store">servidor a servidor</Anchor>.</li><li>La versión del sistema operativo del dispositivo.<ul><li>Android:<ul><li>Ejemplo: 12</li><li>Para un agente de usuario reducido (debido a que los navegadores se ejecutan en ordenadores o Android y utilizan el motor Chrome 110+), la ad network debe utilizar la <Anchor target="_blank" href="https://web.dev/migrate-to-ua-ch/">API de Client Hints</Anchor> para obtener este valor.</li><li>Para el agente de usuario que **no está** reducido, utiliza la siguiente expresión regular para extraer la versión del sistema operativo Android de la cadena de agente de usuario: `(\d+(?:\.\d+)*);(?:\s..-..;)?\s(.+?(?=\)\|\s\w*\/))`.</li></ul></li><li>iOS:<ul><li>Incluye la versión completa del sistema operativo para una atribución precisa. Ejemplo: 16.2</li></ul></li></ul></li></ul> |  |
| <span id="af_model"></span>af\_model | Modelo del dispositivo | <ul><li>Relevante para las ad networks que envían clics e impresiones de <Anchor target="_blank" href="/partners/es/docs/redirecting-users-to-the-app-store">servidor a servidor</Anchor>.</li><li>El modelo del dispositivo.<ul><li>Android:<ul><li>Ejemplo: Pixel 5</li><li>Para un agente de usuario reducido (debido a que los navegadores se ejecutan en ordenadores o Android y utilizan el motor Chrome 110+), la ad network debe utilizar la <Anchor target="_blank" href="https://web.dev/migrate-to-ua-ch/">API de Client Hints</Anchor> para obtener este valor.</li><li>Para el agente de usuario que **no está** reducido, emplea la siguiente expresión regular para extraer el modelo de Android de la cadena de agente de usuario: `(\d+(?:\.\d+)*);(?:\s..-..;)?\s(.+?(?=\)\|\s\w*\/))`.</li></ul></li><li>iOS:<ul><li>Incluye el identificador completo del modelo de dispositivo para una atribución precisa. Por ejemplo, `iphone15,1` o `ipad14,2`.</li></ul></li></ul></li></ul> |  |
| <span id="af_media_type"></span>af\_media\_type | Tipo de medio | Ubicación del anuncio que contiene el enlace de la siguiente manera:<ul><li>app: El enlace está disponible a través de una aplicación.</li><li>web: El enlace está disponible dentro de un sitio web móvil.</li></ul> |  |
| <span id="deep_link_sub110"></span>deep\_link\_sub1-10 | N/D | Valores adicionales de deep link. Los desarrolladores implementan el comportamiento deseado de los valores en el código. |  |
| <span id="deep_link_value"></span>deep\_link\_value | N/D | El nombre para el contenido específico dentro de la aplicación al que serán dirigidos los usuarios. Los desarrolladores implementan el comportamiento deseado de deep\_link\_value en el código. |  |
| <span id="af_og_title"></span>af\_og\_title | N/D | Cuando se publica un enlace en redes sociales, el título de Open Graph (OG) generará una vista previa del título. | Cadena 40 |
| <span id="af_og_description"></span>af\_og\_description | N/D | Al publicar un enlace en redes sociales, la descripción de Open Graph (OG) generará una vista previa de la descripción. | Cadena 300 |
| <span id="af_og_image"></span>af\_og\_image | N/D | Cuando se publica un enlace en redes sociales, la imagen de Open Graph (OG) generará una vista previa de la imagen. |  |

### Parámetros de enlace de atribución—solo para retargeting

| Parámetro | Nombre para mostrar en raw data | Descripción | Tipo de campo y ancho |
| --- | --- | --- | --- |
| <span id="is_retargeting"></span>es\_retargeting | Es retargeting (campaña) | La URL de clic de todas las campañas de retargeting debe incluir `&is_retargeting=true`.  <br />Si el parámetro no está incluido o su valor es "false", la campaña se considera una campaña normal de adquisición de usuarios. | Enumeración de 5 caracteres |
| <span id="af_reengagement_window"></span>af\_ventana\_de\_reengagement | Ventana de re-engagement | Cambia la <Anchor target="_blank" href="/marketers/es/docs/retargeting-attribution-guide#reengagement-rules-and-windows">ventana de atribución de re-engagement</Anchor> añadiendo este parámetro al enlace de atribución.<br /><br />Las opciones posibles para el rango de la ventana son:<ul><li>Días: 1-90 o 1-36 horas</li><li>Duración: Esto significa que la ventana de re-engagement es ilimitada. Ejemplo: `&af_reengagement_window=lifetime`</li></ul>Valor por defecto: 30 días<br /><br />Ejemplo: `&af_reengagement_window=30d` establece la ventana de re-engagement en 30 días. | N/D |

### Parámetros de visibilidad

Dependiendo del tipo de anuncio, puedes enviar el parámetro de visibilidad relevante con las especificaciones del engagement.

| Parámetro | Formato del valor | Descripción |
| --- | --- | --- |
| <span id="af_video_total_length"></span>af\_video\_total\_length | seconds | Duración total posible del vídeo |
| <span id="af_video_played_length"></span>af\_video\_played\_length | seconds | Cuánto del video se vio |
| <span id="af_playable_played_length"></span>af\_playable\_played\_length | seconds | Duración de reproducción del elemento jugable una vez cargado |
| <span id="af_ad_time_viewed"></span>af\_ad\_time\_viewed | seconds | Tiempo en que el anuncio estuvo visible en pantalla |
| <span id="af_ad_displayed_percent"></span>af\_ad\_displayed\_percent | % | Porcentaje máximo de visibilidad del anuncio en pantalla |
| <span id="af_audio_total_length"></span>af\_audio\_total\_length | seconds | Duración total posible del audio |
| <span id="af_audio_played_length"></span>af\_audio\_played\_length | seconds | Cuánto del audio fue escuchado |

### Parámetros específicos de Android

| Parámetro | Nombre para mostrar en raw data | Descripción | Tipo de dato |
| --- | --- | --- | --- |
| <span id="advertising_id"></span>advertising\_id | ID de publicidad | ID de publicidad de Google: requiere soporte de ad network | Máximo 40 caracteres |
| <span id="sha1_advertising_id"></span>sha1\_advertising\_id | N/D | ID de publicidad de Google encriptado con SHA1: requiere soporte de ad network |  |
| <span id="md5_advertising_id"></span>md5\_advertising\_id | N/D | ID de publicidad de Google encriptado con MD5: requiere soporte de ad network | Compatible solo con instalaciones y reatribuciones |
| <span id="android_id"></span>android\_id | ID de Android | Dispositivo Android\_id: requiere soporte de ad network | Máximo 20 caracteres |
| <span id="sha1_android_id"></span>sha1\_android\_id | N/D | Dispositivo Android\_id encriptado con SHA1: requiere soporte de ad network |  |
| <span id="md5_android_id"></span>md5\_android\_id | N/D | Dispositivo Android\_id encriptado con MD5: requiere soporte de ad network | Compatible solo con instalaciones y reatribuciones |
| <span id="imei"></span>imei | IMEI | ID IMEI del dispositivo |  |
| <span id="sha1_imei"></span>sha1\_imei | N/D | ID IMEI del dispositivo encriptado con SHA1: requiere soporte de ad network |  |
| <span id="md5_imei"></span>md5\_imei | N/D | ID IMEI del dispositivo encriptado con MD5: requiere soporte de ad network |  |
| <span id="oaid"></span>oaid | OAID | Identificador Abierto Anónimo del Dispositivo | Disponible desde la versión 4.10.3 del SDK de Android |
| <span id="sha1_oaid"></span>sha1\_oaid | N/D | Identificador Abierto Anónimo del Dispositivo encriptado con SHA1: requiere soporte de ad network | Disponible desde la versión 4.10.3 del SDK de Android |
| <span id="md5_oaid"></span>md5\_oaid | N/D | Identificador de dispositivo anónimo abierto codificado con MD5: requiere compatibilidad con ad network. | Disponible desde la versión 4.10.3 del SDK de Android |
| <span id="af_android_url"></span>af\_android\_url | N/D | Envía a los usuarios de Android a una URL diferente a la página de la aplicación en Google Play. Utilízalo para <Anchor target="_blank" href="/marketers/es/docs/set-up-multi-store-android-attribution#un-solo-panel-de-control-vs-un-panel-de-control-por-tienda">tiendas de aplicaciones de terceros</Anchor>.<br /><br />**Nota:** Mira las [características y limitaciones](/docs/about-link-structure-and-parameters#special-characters) adicionales del parámetro de redirección. |  |
| <span id="sha1_el"></span>sha1\_el | N/D | Se utiliza para atribución de ordenador a móvil: correo electrónico codificado con SHA1. Requiere compatibilidad con ad networks. |  |
| <span id="fire_advertising_id"></span>fire\_advertising\_id | N/D | ID de publicidad de Amazon Fire. |  |
| <span id="af_android_store_csl"></span>af\_android\_store\_csl | store\_product\_page | Listado de tienda personalizado en Google Console. | string |

### Parámetros específicos de iOS.

| Parámetros | Nombre para mostrar. | Descripción |
| --- | --- | --- |
| <span id="idfa"></span>idfa | Identificador de anunciante (IDFA) | Usa mayúsculas. Requiere compatibilidad con ad networks.<br /><br />Tipo de campo: Máximo 40 caracteres |
| <span id="idfv"></span>idfv | IDFV | Usa mayúsculas. |
| <span id="af_ios_url"></span>af\_ios\_url |  | Usa esto para enviar a usuarios de iOS (iPhone o iPad) a una URL distinta de la página de la aplicación en iTunes.<br /><br />**Nota:** Mira las [características y limitaciones](/docs/about-link-structure-and-parameters#special-characters) adicionales del parámetro de redirección. |
| <span id="af_ios_store_cpp"></span>af\_ios\_store\_cpp | store\_product\_page | ID de página de producto personalizada (ppid).<br /><br />**Nota:** En los raw data y reportes agregados, se registra el valor del parámetro af\_ios\_store\_cpp (ID de página de producto personalizada) para los clics, pero no para las impresiones. |
| <span id="af_ios_fallback--deprecated"></span>af\_ios\_fallback [obsoleto] | N/D | **Obsoleto**: Los usuarios son enviados según el <Anchor target="_blank" href="/marketers/es/docs/uri-scheme-fallback-for-ios">flujo de esquema de URI de iOS</Anchor>. |
| <span id="sha1_idfa"></span>sha1\_idfa | N/D | IDFA codificado con SHA1. Requiere compatibilidad con ad networks. |
| <span id="sha1_idfv"></span>sha1\_idfv | N/D | IDFV codificado con SHA1. |
| <span id="mac"></span>mac | N/D | Dirección MAC del dispositivo. Requiere compatibilidad con ad networks. |
| <span id="md5_idfa"></span>md5\_idfa | N/D | IDFA hashed con MD5 |
| <span id="md5_idfv"></span>md5\_idfv | N/D | IDFV codificado con MD5. |
| <span id="sha1_mac"></span>sha1\_mac | N/D | Dirección MAC del dispositivo codificada con SHA1. Requiere compatibilidad con ad networks. |

> 📄 **Ejemplo**
>
> ```http
> https://app.appsflyer.com/{app_id}/?pid=airpush_int&c=RedBanner&
> 	  af_siteid={publisher_id}&af_sub1=1.5&af_sub2=USD&af_sub3=burst_campaign
> ```

Todos los parámetros están disponibles en el <Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-overview">reporte de instalación</Anchor> y en <Anchor target="_blank" href="/marketers/es/docs/analytics-and-aggregate-reporting-apis">Análisis, reportes y APIs</Anchor>.

### Parámetros personalizados

Además de los parámetros predeterminados específicos de Android e iOS, también puedes especificar parámetros personalizados. Estos parámetros personalizados pueden ayudarte si deseas personalizar la experiencia del usuario y el contenido de acuerdo con el enlace de atribución que conduce a una instalación.

Puedes añadir parámetros personalizados al enlace de atribución en el formato `parameter=value`. Por ejemplo:

```http
https://app.appsflyer.com/com.greatapp?pid=networkx_int&c=winter&af_adset=coats&af_ad=cashmere&my_custom_param=my_custom_value
```

Dos aspectos importantes que debes conocer sobre los parámetros personalizados:

* Los parámetros personalizados no aparecen en los raw data.
* Puedes recuperar los parámetros personalizados a través de la <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data">API del SDK de obtención de datos de conversión</Anchor>.

<div id="partner-id-pid-parameter" />

<Accordion title="Parámetro de ID del partner (PID)">

De todos los parámetros de enlace de atribución disponibles, el PID es obligatorio. El PID es el identificador único que AppsFlyer asigna a por fuente de medios.

Cada uno <Anchor target="_blank" href="http://appsflyer.com/partners">El partner integrado con</Anchor> tiene un valor de PID único, que termina con el sufijo *\_int.*  Cuando se utilizan <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">enlaces de OneLink,</Anchor> puedes establecer el PID en el valor que prefieras, siempre que no sea no esté reservado por un partner integrado.

> 📘 **Nota:**
>
> AppsFlyer bloquea los enlaces de atribución que utilizan nombres de <Anchor target="_blank" href="/marketers/es/docs/self-reporting-networks-srns#srns-integradas-con-appsflyer">SRN</Anchor> reservados como valores de PID en fuentes de medios personalizadas, como correos electrónicos y SMS. Esta restricción **no** se aplica a las ASRNs.

Ejemplos de ID de publisher reservados integrados importantes: organic, googleadwords\_int (Google AdWords), facebook\_int (Meta ads), y twitter\_int (X Ads). Puedes usar cualquier nombre para fuentes no integradas fuentes como correo electrónico, SMS o palomas mensajeras.

#### Evita problemas comunes con el PID:

* **Incluye siempre el PID en tus enlaces de atribución.** Sin el PID en el enlace de atribución, el usuario se atribuye automáticamente a una fuente de medios "None", y se pierde la fuente original de instalación.
* **Para cada fuente integrada**, usa solo el designado PID para la correcta atribución de sus instalaciones.
* **Para fuentes personalizadas, utiliza PID de socios no integrados.** Para cualquier fuente de medios personalizada, como email, SMS o incluso publicaciones orgánicas virales en Facebook, utiliza valores de PID no integrados. Como owned\_email, sms\_push u otros identificadores personalizado que no coinciden con los nombres de los partners integrados.
* **Usa únicamente caracteres válidos.** Si el parámetro PID en el enlace de atribución contiene algunos de los siguientes caracteres /&lt;>*&?\
  * El clic o la instalación aparecerán en el dashboard debajo de ***af\_invalid\_param***
  * Los enlaces de atribución no se atribuirán.
  * Las capacidades de deep linking no funcionarán en los clics.

> 👍 **Consejo**
>
> Evita usar espacios en blanco en el valor de PID o asegúrate de codificar en URL por URL tus enlaces de atribución antes de usarlos.

</Accordion>

<div id="site-id-parameter" />

<Accordion title="Parámetro de ID del sitio">

El ID del sitio es el identificador único del publisher que muestra el anuncio. Es decir, el sitio web o la app que exhibe el anuncio. Anuncio networks asignan ID de sitio únicos para cada publisher.

Este ID se incluye en el parámetro `af_siteid` aprobado a AppsFlyer en el enlace de atribución y está disponible a través de varios dashboards, opciones de reportes y postbacks.

El ID del sitio debe enviarse a AppsFlyer en el enlace de atribución porque porque:

* Proporciona claridad y transparencia sobre el publisher.
* AppsFlyer lo utiliza para identificar y eliminar publishers fraudulentos, y otros grupos de tráfico.

El parámetro de ID del sitio solo incluye el ID del publisher que publica el anuncio.

Para incluir información adicional, como el tipo de anuncio, la ubicación o ambos dentro de la aplicación, por ejemplo, banner, intersticial o video, utiliza el parámetro ID de subsitio.

> 📄 **Ejemplo**
>
> El siguiente enlace de atribución incluye:
>
> * `af_siteid` (ID del sitio): ID del publisher
> * `af_sub_siteid` (ID del subsitio): Adicional adicional de ID (en este caso, una fuente de afiliado y el tipo de ubicación del anuncio)
>
> `https://app.appsflyer.com/com.yourapp?pid=mediaName_int&clickid={clickid}&advertising_id={gaid}&af_siteid=1234&af_sub_siteid=ABCD_4567`
>
> En el enlace de ejemplo:
>
> * 1234 = ID del publisher
> * ABCD = Fuente afiliada (subpublisher) con la que colabora el publisher está trabajando con
> * 4567 = Ubicación del tipo de anuncio dentro de la aplicación, como banner, intersticial, o video

#### **Preguntas frecuentes: ¿Por qué el tráfico resulta en muchas instalaciones bloqueadas?**

Las instalaciones bloqueadas pueden deberse a lo siguiente:

* **ID de sitio inexistente:** El parámetro `af_siteid` está vacío en la URL de clic. Los engagements enviados con un ID de sitio vacío indican un problema técnico o un intento intencional de evadir los mecanismos de detección de fraude.
* **Diversos IDs de sitios:** El mismo publisher se envía en varias URLs de clic, utilizando diferentes IDs de sitio. Esto se considera un comportamiento fraudulento que oculta la actividad real del publisher y se asocia a menudo con <Anchor target="_blank" href="https://www.appsflyer.com/blog/click-flooding-detection-false-positive-challenge/">inundación de clics</Anchor>.
* **ID del sitio mal formateado:** Enviar un formato incorrecto, combinado con otras señales de fraude, puede provocar el bloqueo no solo del publisher específico, sino también de un mayor nivel de clúster, y podría afectar a mayores volúmenes de la actividad del partner.

Para evitar instalaciones bloqueadas, asegúrate de enviar un único parámetro de ID de sitio por publisher, como se muestra en el ejemplo.

</Accordion>

## Niveles de granularidad de datos

Puedes utilizar hasta cuatro parámetros de URL para analizar en profundidad el rendimiento de tus anuncios.

Utilizar los 4 parámetros en todos tus enlaces de atribución activos permiten:

* Atribuir todas las instalaciones y eventos de usuarios a anuncios específicos.
* Examina detalladamente y compara el rendimiento de todos tus anuncios por conjunto de anuncios, campaña y fuente de medios en reportes agregados para optimizar en todos los niveles.
* Compara todos tus anuncios entre todas las fuentes de medios en los reportes de raw data y en la <Anchor target="_blank" href="/marketers/es/docs/pivot-table-user-metrics">tabla pivot</Anchor>.

Los parámetros son:

* `Fuente de medios (pid=)`
* `Nombre de campaña (c=)`
* `Conjunto de anuncios (af_adset=)`
* `Nombre de anuncio (af_ad=)`

> 📄 **Ejemplo**
>
> El siguiente enlace de atribución utiliza 4 niveles de granularidad para registrar el anuncio "cachemira" en el conjunto de anuncios "abrigos" de la campaña "invierno" que se ejecuta en la fuente de medios integrada "red".
>
> ```http
> https://app.appsflyer.com/com.greatapp?pid=networkx_int&c=winter&
> af_adset=coats&af_ad=cashmere
> ```

## Preguntas frecuentes

<div id="should-i-use-lower-or-upper-case-letters-for-parameters" />

<Accordion title="¿Debo utilizar letras minúsculas o mayúsculas para los parámetros?">

Puedes usar cualquiera de los dos, pero debes ser coherente. Si configuras un parámetro personalizado con caracteres en mayúsculas o minúsculas, asegúrate de usar siempre ese mismo parámetro.

Por ejemplo, si configuras pid=MyMediaSource, asegúrate de usarlo siempre así. Si utilizas pid=MyMediaSource en un enlace de atribución y pid=mymediasource en otro, pueden surgir discrepancias en los datos. Lo mismo aplica para cualquier otro parámetro que configures en el enlace de atribución.

</Accordion>

<div id="is-the-appsflyer-attribution-link-dynamic-or-static" />

<Accordion title="¿El enlace de atribución de AppsFlyer es dinámico o estático?">

Los enlaces de atribución pueden ser dinámicos o estáticos.  
¿Cómo puedes saber si un enlace es dinámico o estático?  
Si el **enlace de atribución contiene parámetros**, es un enlace de atribución predefinido largo y, por lo tanto, **estático**.  
**Solo las URLs cortas** (por ejemplo, `yourbrand.onelink.me/HaT8/r5c2b371`), utilizadas para enlaces de atribución personalizados, **son dinámicas**.  
Esto significa que, una vez que comiences a usar un enlace de atribución para un partner integrado o una URL larga para medios propios, no cambiará para ningún cliente potencial que interactúe con él, incluso si modificas los valores del enlace de atribución en el dashboard de AppsFlyer. Para que el cambio surta efecto, tendrás que utilizar la nueva URL larga desde ahora.  
Por otro lado, las URL cortas para medios propios no contienen parámetros directamente. Cuando un cliente potencial interactúa con una URL corta de AppsFlyer, se redirecciona a AppsFlyer y los parámetros actuales se aplican de manera dinámica.

</Accordion>

<div id="what-is-this-play-store-error-message" />

<Accordion title="¿Qué es este mensaje de error de Play Store?">

Si alguna vez ves el siguiente mensaje de error en Play Store tras seguir un enlace de atribución:

![TL_error_message.png](https://files.readme.io/03e509d3cbe68aa0621bb0f43ab113c25a8427e70826c5af5258f1fc9e3f3d36-360000002485.png)

Esto ocurre porque el enlace de atribución contiene un carácter #. Por ejemplo:

```http
https://app.appsflyer.com/com.travelco?pid=globalwide_int&clickid=#reqid#
```

Normalmente, estos caracteres están en el enlace porque son macros y se sustituyen dinámicamente por un valor. Así que no es un problema importante y puedes ignorar el mensaje.

</Accordion>

<div id="what-are-subscriber-parameters-good-for" />

<Accordion title="¿Para qué sirven los parámetros de suscriptor?">

Los parámetros del suscriptor, es decir, af\_sub1, af\_sub2, ..., af\_sub\_5, se pueden usar para registrar cualquier KPI útil. Estos parámetros se interpretan y se muestran en el reporte de raw data, lo que los hace muy prácticos para la agregación o el filtrado de datos.

> 📄 **Ejemplo**
>
> Una aplicación de transporte, Luber, tiene creatividades con 3 plantillas de colores: azul, amarillo y rojo. Linda, la marketer móvil de Luber, quiere evaluar qué plantilla de color genera más instalaciones. Para ello, añade `&af_sub3=blue` en los enlaces de atribución de todos los anuncios azules en TODAS las fuentes de medios no SRNs. Se realiza el mismo procedimiento para los anuncios amarillos y rojos. Con esta información analizada y presentada en los reporte de raw data, Linda puede analizar el éxito de los anuncios de diferentes colores y seleccionar el que mejor convierta.

</Accordion>

<div id="what-limits-are-there-on-campaign-names" />

<Accordion title="¿Qué límites existen para los nombres de las campañas?">

* La longitud máxima del nombre de una campaña en la URL del enlace de atribución está limitada a 100 caracteres. Si se excede, el nombre de la campaña se modifica a: `c_name_exceeded_max_length`
* El nombre de la campaña no debe comenzar ni terminar con un espacio en blanco, ya que podría causar discrepancias en los dashboards y reportes.

</Accordion>

## Características y limitaciones

| Características | Observaciones |
| --- | --- |
| <span id="special-characters"></span>Caracteres especiales | No se permiten los siguientes caracteres especiales en las claves y valores de parámetros (no aplicable a los parámetros de redireccionamiento y af\_dp):  ;, *, !, @, #, ?, $, ^, :, &, ~, \`, =, +, ’, >, &lt;, /, \{, \}, %, ),( |
| <span id="redirection-parameters"></span>Parámetros de redireccionamiento | <ul><li>Asegúrate de que los dominios URL de redireccionamiento estén agregados a tu <Anchor target="_blank" href="/marketers/es/docs/set-up-your-domain-redirect-allowlist">lista de redireccionamientos</Anchor> permitidos.</li><li>El valor de redireccionamiento debe ser una URL web válida completa (https://[domain][optional-path]) de acuerdo con las <Anchor target="_blank" href="https://datatracker.ietf.org/doc/html/rfc1738">normas RFC 1738</Anchor>;</li><li>Los <Anchor target="_blank" href="https://en.wikipedia.org/wiki/URI_fragment">identificadores de fragmentos URI</Anchor> **no son compatibles** con las URLs de redireccionamiento (por ejemplo, #webpagesection, que desplaza a los usuarios hacia abajo hasta una sección específica de un artículo).</li></ul> |
| <span id="url-characteravailable"></span>Límite de caracteres de la URL | La longitud total de la URL no debe superar los 2000 caracteres |
| <span id="agencies"></span>Redirección de deep linking en WebView de aplicaciones de redes sociales de Android | Consulta los detalles de las limitaciones <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#android-social-apps-webview-deep-linking-redirection">aquí</Anchor> |
| <span id="deep-linking-is-not-supported-in-the-android-naver-blog-app"></span>Deep Linking no es compatible con la app de Android Naver Blog | Deep Linking no es compatible con la app de Android Naver Blog. Los usuarios serán enviados a Google Play Store o a la web según el enlace establecido. |
| <span id="a-popup-appears-when-clicking-on-a-uri-scheme-link-from-chrome-browser-on-ios"></span>Al hacer clic en un enlace de esquema URI desde el navegador Chrome en iOS, aparece una ventana emergente | Debido a un cambio en Chrome iOS, cada vez que un usuario hace clic en un enlace de esquema URI en Chrome en iOS, se muestra una ventana emergente pidiendo al usuario confirmar la apertura de la aplicación o la redirección a la App Store. |
| <span id="uri-scheme-validity-requirements"></span>Requisitos de validez para esquemas URI | Recomendamos utilizar un esquema URI válido que cumpla con <Anchor target="_blank" href="https://www.rfc-editor.org/rfc/rfc3986#section-3.1">RFC 3986</Anchor>. Los esquemas que no cumplan con lo anterior pueden no abrir una aplicación y generar un error al hacer clic desde una web view u otros entornos web. |
| <span id="telegram-webview-attribution"></span>Atribución de WebView en Telegram | Consulta los detalles de las limitaciones <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#telegram-webview">aquí</Anchor> |

<div data-zendesk-anchors="overview=visi%C3%B3n-general 01H8GN1XXC5T2ENFHBK0G4WQ1P=visi%C3%B3n-general 01JENAANV4KTRF882JMEM5N91A=importante attribution-link-parameters=par%C3%A1metros-del-enlace-de-atribuci%C3%B3n 01H8GN1XXDX1XMQ1GJTHCP425D=par%C3%A1metros-del-enlace-de-atribuci%C3%B3n attribution-link-parameters%E2%80%94ua-and-retargeting=par%C3%A1metros-de-enlace-de-atribuci%C3%B3n-ua-y-retargeting 01H8GN1XXDEWPB2MPP3KJVPRJV=par%C3%A1metros-de-enlace-de-atribuci%C3%B3n-ua-y-retargeting af_sub%5Bn%5D%C2%A0%0An15-example-af_sub1=af_sub-n-n15-example-af_sub1 %5Bdeprecated%5D-af_os=deprecated--af_os attribution-link-parameters%E2%80%94retargeting-only=par%C3%A1metros-de-enlace-de-atribuci%C3%B3nsolo-para-retargeting 01H8GN1XXD9X7CWZJN43PSS94R=par%C3%A1metros-de-enlace-de-atribuci%C3%B3nsolo-para-retargeting viewability-parameters=par%C3%A1metros-de-visibilidad 01H8GN1XXETQEYT39F05ZYX4E2=par%C3%A1metros-de-visibilidad androidspecific-parameters=par%C3%A1metros-espec%C3%ADficos-de-android 01H8GN1XXEE9RGSB1H72H025Z4=par%C3%A1metros-espec%C3%ADficos-de-android iosspecific-parameters=par%C3%A1metros-espec%C3%ADficos-de-ios 01H8GN1XXESJ9VE3W8CYKRFFYX=par%C3%A1metros-espec%C3%ADficos-de-ios af_ios_fallback-%5Bdeprecated%5D=af_ios_fallback--deprecated 01H8GN1XXEFRSQSERTB6ARC773=ejemplo custom-parameters=par%C3%A1metros-personalizados 01H8GN1XXEB58JN4SV9HX1ZV6S=par%C3%A1metros-personalizados 01H8GN1XXE8EXMMKDZMJ2WNNH5=partner-id-pid-parameter h_01JRX48BX8W9V9XWPB1DSG4H8Y=nota avoid-common-pid-issues=evita-problemas-comunes-con-el-pid 01H8GN1XXEXTGC4M8AMJ256Q9G=evita-problemas-comunes-con-el-pid 01H8GN1XXEGNVX9GM5JYBMBGCF=consejo 01H8GN1XXEVG65YP782CM37RES=site-id-parameter 01H8GN1XXED2MVSNRXN11KZ955=ejemplo-1 faq-why-does-traffic-result-in-many-blocked-installs=preguntas-frecuentes-por-qu%C3%A9-el-tr%C3%A1fico-resulta-en-muchas-instalaciones-bloqueadas 01H8GN1XXEK0G9TDW8WHWM17HK=preguntas-frecuentes-por-qu%C3%A9-el-tr%C3%A1fico-resulta-en-muchas-instalaciones-bloqueadas levels-of-data-granularity=niveles-de-granularidad-de-datos 01H8GN1XXE4RF9J0APAAKD1WEG=niveles-de-granularidad-de-datos 01H8GN1XXEHPFKX7V0RRW2MH2G=ejemplo-2 frequently-asked-questions=preguntas-frecuentes h_01HN0JW166VHR33T8VVVY47F9P=preguntas-frecuentes 01H8GN1XXEND9X8YVRQE1YFA5W=should-i-use-lower-or-upper-case-letters-for-parameters 01H8GN1XXER749PH4Z14A7AJ0F=is-the-appsflyer-attribution-link-dynamic-or-static 01H8GN1XXEPQTY0XNW6EZSA9ZN=what-is-this-play-store-error-message 01H8GN1XXFYAFYFX9MNBP6D35B=what-are-subscriber-parameters-good-for 01H8GN1XXFEFA498J22GRF5F8G=ejemplo-3 01H8GN1XXFS1DFS3HAHVTVG93A=what-limits-are-there-on-campaign-names traits-and-limitations=caracter%C3%ADsticas-y-limitaciones h_01HN0JW166WH76A5SM293PGKX6=caracter%C3%ADsticas-y-limitaciones" />
