---
title: Acerca de la resolución de la fuente de tráfico
metadata:
  keywords:
    - Agencies
    - Web Attribution
    - Web Attribution SDK
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
    - Agencies
  created_at: '2026-02-04T13:46:22Z'
  edited_at: '2026-10-20T03:44:48Z'
  id: 43518064765201
  locale: es
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/es/articles/43518064765201
---
> **At a glance:** Usa la resolución de la fuente de tráfico para identificar la fuente de medios, la campaña y el canal iniciales de cada visita web, a partir de los parámetros de la URL y de los datos de referencia disponibles cuando se carga la página de destino. Esto proporciona a la atribución el contexto de la fuente de tráfico que necesita para atribuir con precisión los eventos web posteriores, incluido el evento de adquisición de usuarios.

<div id="what-is-traffic-source-resolution" />

## ¿Qué es la resolución de la fuente de tráfico?

En la atribución web, la carga de la página de destino (**visita web**) es la primera interacción del usuario con el sitio web. AppsFlyer se basa en la información disponible en ese momento, como los parámetros de la URL y los datos de referencia, para identificar la fuente de medios, la campaña y el canal del usuario.

Este proceso, conocido como **resolución de la fuente de tráfico**, identifica y resuelve la información de la fuente de medios y de la campaña a partir de los parámetros de la URL. AppsFlyer captura y prioriza estos parámetros para determinar el contexto inicial de la fuente de tráfico de una visita.

La resolución de la fuente de tráfico es un **proceso previo a la atribución**. Los parámetros resueltos pueden sobrescribirse más adelante durante <Anchor target="_blank" href="/marketers/es/docs/web-performance-measurement-overview#el-flujo-de-web-performance-measurement">el proceso de atribución</Anchor>.

La función de la resolución de la fuente de tráfico no termina con la visita. Su resultado proporciona el contexto de la fuente de tráfico que el proceso de atribución utiliza más adelante para atribuir los eventos web posteriores, incluido el evento de adquisición de usuarios.

Entender cómo funciona la resolución de la fuente de tráfico es esencial para crear URL precisas. Para saber cómo crear una URL bien estructurada, consulta <Anchor target="_blank" href="/marketers/es/docs/choose-attribution-parameters-for-landing-page-urls">Elegir parámetros de atribución para las URL de las páginas de destino</Anchor>.

<div id="the-traffic-source-resolution-flow" />

## El flujo de resolución de la fuente de tráfico

La resolución de la fuente de tráfico sigue un flujo estructurado de varios pasos que va construyendo progresivamente el contexto de atribución de cada visita web. Cada paso aporta una capa específica de información, desde capturar la propia visita hasta clasificar el tráfico para reportar. Los datos que utiliza el flujo de resolución de la fuente de tráfico se capturan a través del SDK web o de Web S2S.

El flujo consta de los siguientes pasos:

1. [Registro de visitas](#paso-1-registro-de-visitas): captura la llegada del usuario al sitio web y registra un evento de visita, incluso cuando todavía no se conoce la fuente de tráfico. Esto garantiza que se midan todas las entradas de usuario aptas antes de aplicar la lógica de atribución.
2. [Resolución de la fuente de medios](#paso-2-resolución-de-la-fuente-de-medios): analiza los parámetros de la URL y los datos del referente para identificar la plataforma o los Partners que impulsaron la visita, o determinar que la visita es orgánica.
3. [Resolución de campaña](#paso-3-resolución-de-la-campaña): resuelve los detalles granulares de la campaña asociados a la fuente de medios identificada, lo que permite un análisis detallado del rendimiento.
4. [Clasificación de canales](#paso-4-clasificación-de-canales): asigna cada visita a un canal de tráfico de alto nivel en función de la fuente de medios resuelta, lo que proporciona una vista estandarizada para reportar.

<div id="step-1-visit-recording" />

## Paso 1: Registro de visitas

El registro de visitas es el paso inicial del flujo de medición del rendimiento web. Ocurre antes de la resolución de la fuente de medios y de la atribución, y actúa como una capa de preprocesamiento que captura la actividad sin procesar del usuario.

La lógica funciona en dos etapas. Primero, clasifica el **referrer** (el dominio del que procedía el usuario antes de llegar a tu sitio). Después, según el tipo de referrer, evalúa el estado de la sesión del usuario y la presencia de información de la fuente de medios para decidir si debe registrar la visita.

<div id="stage-1-referrer-classification" />

#### Fase 1: Clasificación del referrer

AppsFlyer clasifica el referrer en uno de tres tipos:

* **Externo excluido** (por ejemplo, un procesador de pagos o cualquier dominio que hayas excluido)
* **Interno excluido** (por ejemplo, tus propios subdominios o flujos de login)
* **Resto** (todos los demás referrers)

<div id="stage-2-session-evaluation-and-visit-recording" />

#### Fase 2: Evaluación de la sesión y registro de visitas

Según el tipo de referrer, AppsFlyer evalúa el estado de la sesión y decide si debe registrar la visita:

* **Externo excluido:** La visita no se registra nunca.
* **Interno excluido:** La atribución basada en el referrer se suprime, porque el referrer no es una fuente de adquisición real.
  * Si hay una sesión activa (una sesión se considera inactiva después de 30 minutos de inactividad; en caso contrario, está activa), la visita no se registra.
  * Si no hay ninguna sesión activa, la visita se registra, pero el referrer se trata como una autorreferencia y se ignora. La visita se registra como orgánica, a menos que la URL incluya parámetros de atribución (UTM, PID, click ID, etc.).
* **Else:**
  * Si no hay ninguna sesión activa, ¿podrías registrar la visita? Una sesión nueva cuenta como una visita nueva, independientemente de las demás condiciones.
  * Si hay una sesión activa y existe una fuente de medios no directa (UTM, PID, click ID, etc.), registra la visita. Esta revisita puede activar una conversión de retargeting (re-engagement), que se utiliza para atribuir los eventos posteriores.
  * Si hay una sesión activa y no hay información de la fuente de medios, no registres una visita nueva dentro de esa sesión.

<Image alt="flujo de resolución del tráfico" src="https://files.readme.io/d5f807d5ced5ed9a90a41cda0f38fe7ffef0b81c321bae90ad410076b484c810-47195479783953.png" width="1494px" />

<div id="step-2-media-source-resolution" />

## Paso 2: Resolución de la fuente de medios

El proceso de resolución de la fuente de medios determina si una visita es:

* **No orgánico:** Se encuentra una fuente de atribución específica.
* **Orgánico:** No se identifica ninguna fuente de atribución (por ejemplo, el usuario escribió la URL directamente o usó un marcador).

Durante el proceso de resolución de la fuente de medios, AppsFlyer determina el origen de una visita web evaluando los parámetros extraídos de la ruta de la URL de la página de destino y de la cadena de consulta.

Para obtener los mejores resultados, utiliza parámetros específicos de AppsFlyer, como `pid` y `af_campaign`, que proporcionan el mayor nivel de granularidad y control. AppsFlyer también reconoce parámetros estándar del sector, como las etiquetas UTM y los ID de clics, lo que te permite empezar de inmediato sin cambiar tu configuración actual de medición de anuncios.

AppsFlyer sigue un orden de prioridad para resolver la fuente de medios. El proceso se detiene en cuanto se identifica correctamente una fuente. El proceso de resolución de la fuente de medios consta de los siguientes pasos:

<Accordion title="1. Excluir dominios">

Primero, AppsFlyer comprueba si la visita procede de un dominio de tu **lista de exclusión**. Si el dominio está excluido (por ejemplo, tu dominio interno o un procesador de pagos como PayPal), la visita se ignora automáticamente o se clasifica como **Orgánico.**

Para obtener más información sobre cómo especificar los dominios excluidos al añadir una aplicación web a AppsFlyer, consulta <Anchor target="_blank" href="/marketers/es/docs/configure-web-performance-measurement-settings#dominios-excluidos">Dominios excluidos</Anchor>.

</Accordion>

<Accordion title="2. PID de AppsFlyer (ID del partner)">

Si el dominio no está excluido, AppsFlyer busca el parámetro `pid=` en la URL.

* Si se encuentra, la fuente de medios se toma directamente de este valor.
* <span id="social-media-partners"></span>Los siguientes partners de redes sociales usan etiquetas de visualización específicas en lugar del valor sin procesar del parámetro URL.

| Parámetro de la URL (PID) | Nombre para mostrar de la fuente de medios |
| --- | --- |
| `pid=iossearchads_int` | Anuncios en la búsqueda de Apple |
| `pid=facebook_int` | Facebook Ads |
| `pid=metaweb_int` | Facebook Ads |
| `pid=twitter_int` | Twitter |
| `pid=twitterweb_int` | Twitter |
| `pid=googleads_int` | googleadwords\_int |
| `pid=tiktokweb_int` | tiktokglobal\_int |
| `pid=snapweb_int` | snapchat\_int |

</Accordion>

<Accordion title="3. Parámetros UTM">

Si no se encuentra ningún PID en la URL, AppsFlyer evalúa los parámetros `utm_source` y `utm_medium` para identificar la fuente de medios. La combinación de estos dos campos determina la resolución resultante.

<div id="how-utm-logic-works" />

#### **Cómo funciona la lógica de UTM**

* En la mayoría de los casos, AppsFlyer determina la fuente de medios extrayendo el valor sin procesar de `utm_source` y usándolo como fuente de medios.
* Si `utm_medium` es `email`, `mail` o `e-mail`, la fuente de medios se resuelve automáticamente en `e-mail`.
* Si `utm_medium` está presente y no es un valor de correo electrónico, AppsFlyer comprueba el valor con reglas específicas de asignación personalizada (consulta la tabla de asignación a continuación).
* Si falta `utm_medium` o no coincide con ninguna regla personalizada, AppsFlyer recurre a `utm_source` como fuente de medios.

<div id="utm-mapping-rules" />

#### **Reglas de asignación de UTM**

| utm\_source | utm\_medium | Fuente de medios |
| --- | --- | --- |
| Google, googleads\_int | cpc / ppc / paidsearch / paid\_search / paid-search / search / paid | googleadwords\_int |
| Google | cpm / display / banner / video / listing | dv360\_int |
| dfa / dbm / dcm / doubleclick | CPM | dv360\_int |
| Facebook / FB / Meta, metaweb\_int, facebook\_int | cpc / ppc / cpm / cpa / paidsocial / paid-social / paid\_social / paid | Facebook Ads |
| Bing / microsoft / ms | cpc / ppc / paidsearch / paid\_search / paid-search / search / paid | bingsearch\_int |
| Yahoo / gemini | cpm / display / listing | yahoogemini\_int |
| twitter, twitter\_int, twitterweb\_int | cpc / ppc / paid / paidsocial / paid-social / paid\_social | Twitter |
| Snapchat / snap, snapweb\_int | swipe / cpc / ppc / paid / paidsocial / paid-social / paid\_social | snapchat\_int |
| pinterest | cpc / ppc / paid / paidsocial / paid-social / paid\_social | pinterest\_int |
| tiktok, tiktokweb\_int | cpc / ppc / paid / paidsocial / paid-social / paid\_social | tiktokglobal\_int |
| iossearchads\_int | cualquiera / ninguno | Anuncios en la búsqueda de Apple |
| chatgpt.com | pagado: cpc / ppc / cpm / pagado / paid\_search / paidsearch / display / banner / video | openai\_int |
| chatgpt.com | ninguna de las anteriores* | chatgpt\_organic\_aeo (canal: aeo) |
| perplexity | cualquiera / ninguno | perplexity\_organic\_aeo (canal: aeo) |

*\*Si hay un* `oppref` *click ID presente, AppsFlyer omite esta fila y, en su lugar, resuelve la visita a partir de* `oppref` *(consulta los ID de clic).*

</Accordion>

<Accordion title="4. ID de clic">

Si en la URL no hay ni un PID ni parámetros UTM, AppsFlyer intenta identificar la fuente de medios mediante **ID de clic**. Son identificadores únicos que determinadas ad networks añaden automáticamente a las URL.

AppsFlyer usa la siguiente asignación de ID de clic para atribuir la visita:

| Parámetro de ID de clic | Fuente de medios resuelta |
| --- | --- |
| `gclid`, `wbraid` o `gbraid` | googleadwords\_int |
| `msclkid` | bingsearch\_int |
| `twclid` | Twitter |
| `vmcid` | yahoogemini\_int |
| `sccid` | snapchat\_int |
| `li_fat_id` | linkedin\_int |
| `ttclid` | tiktokglobal\_int |
| `tbclid` | taboola\_int |
| `ob_click_id` | outbrain\_int |
| `dicbo` | outbrain\_int |
| `yclid` | yandex\_int |
| `rdt_cid` | reddit\_int |
| `epik` | pinterest\_int |
| `oppref` | openai\_int |

> 📘 **Note**
>
> * AppsFlyer no usa fbclid para la resolución de la fuente de tráfico porque Meta lo añade tanto a los clics de Facebook pagados como a los orgánicos. Para atribuir el tráfico a Meta, incluye pid=facebook\_int o configura utm\_source con el valor de fuente de Meta correspondiente.
> * El parámetro dclid no se usa para la resolución de la fuente de medios. dclid es un identificador de Campaign Manager 360 (CM360) que puede aparecer junto con otros click ID, como fbclid (Facebook) o ttclid (TikTok), cuando se utiliza CM360. Usar solo dclid puede dar lugar a una resolución incorrecta.

</Accordion>

<Accordion title="5. Referencia HTTP">

Si no se encuentran parámetros de consulta (PID, UTMs o click ID) en la URL, AppsFlyer usa el `http_referrer` para identificar la fuente de tráfico. Esto se basa en un mecanismo de análisis interno que extrae el host del dominio y lo asigna a una fuente de medios.

<div id="the-parsing-mechanism" />

#### **El mecanismo de análisis**

Para identificar la fuente, AppsFlyer limpia el string del referente de la siguiente manera:

1. Reduciendo la URL al **host**
2. Eliminando los **sufijos del dominio** (dominios de nivel superior como `.com`, `.org` o extensiones como `.co.uk`)
3. Eliminando los **prefijos del dominio** (como `www.`, `m.`, `l.`o `lm.`)

*Ejemplo: un referente de* `www.mywebsite.com?param=example` *se resuelve en una fuente de medios* `mywebsite`.

<div id="referrer-mapping-rules" />

#### **Reglas de asignación de referentes**

| Si el host del dominio contiene… | Fuente de medios resuelta |
| --- | --- |
| `mail.` o `outlook.` | De correo electrónico |
| `t.co` | twitter |
| `googleads.g.doubleclick.net` | googleadwords\_int |
| `tpc.googlesyndication.com` | dv360\_int |

<div id="search-engine-mapping" />

#### **Asignación de motores de búsqueda**

| Si el host del dominio contiene… | Fuente de medios resuelta |
| --- | --- |
| `google.` | google\_organic\_seo |
| `search.yahoo` | yahoo\_organic\_seo |
| `bing.com` | bing\_organic\_seo |
| `ask.com`, `de.ask.com`, `uk.ask.com` | ask\_organic\_seo |
| `duckduckgo.com` | duckduckgo\_organic\_seo |
| `yandex.com`, `yandex.ru` | yandex\_organic\_seo |
| `search.naver.com` | naver\_organic\_seo |
| `daum.net` | daum\_organic\_seo |
| `baidu.com` | baidu\_organic\_seo |
| `ecosia.org/search` | ecosia\_organic\_seo |
| `coccoc.com/search` | coccoc\_organic\_seo |
| `sogou.com` | sogou\_organic\_seo |
| `yahoo.co.jp` | yahoojapan\_organic\_seo |

Todas las filas de esta tabla se asignan al canal `seo`.

<div id="ai-answer-engine-referrer-mapping" />

#### **Asignación de referentes de motores de respuesta de IA**

| Si el host del dominio contiene… | Fuente de medios | Channel |
| --- | --- | --- |
| `chatgpt.com`, `chat.openai.com` | chatgpt\_organic\_aeo | aeo |
| `perplexity.ai` | perplexity\_organic\_aeo | aeo |
| `gemini.google.com` | gemini\_organic\_aeo | aeo |
| `claude.ai` | claude\_organic\_aeo | aeo |
| `deepseek.com` | deepseek\_organic\_aeo | aeo |
| `manus.im` | manus\_organic\_aeo | aeo |
| `grok.com` | grok\_organic\_aeo | aeo |
| `copilot.microsoft.com` | copilot\_organic\_aeo | aeo |

<div id="android-app-referrers" />

#### **Referentes de apps de Android**

Si la visita procede de una aplicación de Android, el host del referente se asigna de la siguiente manera:

| String del referente de la aplicación | Fuente de medios resuelta |
| --- | --- |
| `com.google.android.googlequicksearchbox` | Google Search |
| `com.google.android.gm` | De correo electrónico |
| `com.linkedin.android` | linkedin |
| `com.twitter.android` | twitter |
| `org.telegram.messenger` | telegram |

</Accordion>

<div id="step-3-campaign-resolution" />

## Paso 3: resolución de la campaña

Una vez que se confirma la fuente de medios en el paso 2, AppsFlyer intenta identificar los detalles específicos de la campaña.

AppsFlyer extrae la información de la campaña de los siguientes parámetros de URL, por orden de prioridad:

| Parámetro(s) de URL | Se asigna a | Orden de prioridad |
| --- | --- | --- |
| `c`, `af_campaign`, `utm_campaign` | Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>. | <ol><li>`C`</li><li>`af_campaign`</li><li>`utm_campaign`</li></ol> |
| `af_c_id`, `af_campaign_id` | Cadena | <ol><li>`af_c_id`</li><li>`af_campaign_id`</li></ol> |
| `af_conjunto de anuncios` | Nombre de conjunto de anuncios | — |
| `af_adset_id` | ID de conjunto de anuncios | — |
| `af_anuncio` | Nota | — |
| `id_del_anuncio_af` | Retargeting: Primer inicio después del re-engagement o la reatribución. | — |
| `af_palabras_clave` | Información del dispositivo | — |

<div id="step-4-channel-classification" />

## Paso 4: clasificación de canales

Además de identificar la fuente de medios, AppsFlyer clasifica cada visita en un canal. Esta clasificación ofrece una visión general de alto nivel de los tipos de tráfico en los Reportes de raw data y en el Dashboard.

<div id="overriding-the-channel-with-af_channel" />

### Sobrescribir el canal con af\_channel

Para asignar un valor de canal personalizado, añade el parámetro `af_channel` a la URL de la página de destino. Por ejemplo, `af_channel=ig` establece el canal como `ig`, lo que te permite desglosar el tráfico a un nivel que las categorías estándar no captan, por ejemplo, por ubicación del anuncio.

`af_channel` solo se resuelve cuando también se identifica una fuente de medios para la visita. Si la visita es orgánica (no se identifica ninguna fuente de medios), siempre se resuelve como `Direct`, esté o no presente `af_channel`.

<div id="default-channel-classification" />

### Clasificación predeterminada del canal

Si `af_channel` no está presente, o la visita no cumple la condición anterior, AppsFlyer recurre a la clasificación automática en función de la fuente de medios identificada:

* **Direct:** El usuario escribió la URL directamente o usó un marcador. No se identifica ninguna fuente de atribución.
* **Redes sociales:** Tráfico procedente de las plataformas sociales.
* **Correo electrónico:** Tráfico de campañas de correo electrónico o de proveedores de servicios de correo electrónico.
* **Anuncio:** Tráfico generado por publicidad pagada.
* **Referral:** Tráfico de otros sitios web, identificado mediante el referente.
* **Otro:** Tráfico que no coincide con ninguna de las categorías anteriores.
* **seo:** Tráfico no de pago procedente de los motores de búsqueda.
* **aeo:** Tráfico procedente de los motores de respuestas de IA.

**Nota:** A cada visita se le asigna un canal. La clasificación es automática y determinista, y se basa en la fuente de medios identificada y en el método de atribución, salvo que se sobrescriba con `af_channel`.

<div data-zendesk-anchors="what-is-traffic-source-resolution=qu%C3%A9-es-la-resoluci%C3%B3n-de-la-fuente-de-tr%C3%A1fico h_01KGMEER6DX8W3ECBEBYP4DQV1=qu%C3%A9-es-la-resoluci%C3%B3n-de-la-fuente-de-tr%C3%A1fico the-traffic-source-resolution-flow=el-flujo-de-resoluci%C3%B3n-de-la-fuente-de-tr%C3%A1fico h_01KGMEER6DA4HMSZ3TVEAG84WZ=el-flujo-de-resoluci%C3%B3n-de-la-fuente-de-tr%C3%A1fico step-1-visit-recording=paso-1-registro-de-visitas h_01KGMEER6DV02F44C5ZPSBEQEX=paso-1-registro-de-visitas stage-1-referrer-classification=fase-1-clasificaci%C3%B3n-del-referrer h_01KSSEM5P8RX29CD6C6ZD2DVAT=fase-1-clasificaci%C3%B3n-del-referrer stage-2-session-evaluation-and-visit-recording=fase-2-evaluaci%C3%B3n-de-la-sesi%C3%B3n-y-registro-de-visitas h_01KSSEM5P8KBYDBCB7PAPGPX5M=fase-2-evaluaci%C3%B3n-de-la-sesi%C3%B3n-y-registro-de-visitas step-2-media-source-resolution=paso-2-resoluci%C3%B3n-de-la-fuente-de-medios h_01KGMEER6D082QTZGZYEXT6726=paso-2-resoluci%C3%B3n-de-la-fuente-de-medios how-utm-logic-works=c%C3%B3mo-funciona-la-l%C3%B3gica-de-utm h_01KGMF0E1XBSJCVDWGC4R8XMPX=c%C3%B3mo-funciona-la-l%C3%B3gica-de-utm utm-mapping-rules=reglas-de-asignaci%C3%B3n-de-utm h_01KGMF0JSBZ3WYM65R55BCDAMN=reglas-de-asignaci%C3%B3n-de-utm the-parsing-mechanism=el-mecanismo-de-an%C3%A1lisis h_01KGMEZA9ETGK6Z89GM111E64Z=el-mecanismo-de-an%C3%A1lisis referrer-mapping-rules=reglas-de-asignaci%C3%B3n-de-referentes h_01KGMEZESC451HVJT139BSXEA5=reglas-de-asignaci%C3%B3n-de-referentes search-engine-mapping=asignaci%C3%B3n-de-motores-de-b%C3%BAsqueda h_01KGMEZKCTASMNXZG13VTVECVH=asignaci%C3%B3n-de-motores-de-b%C3%BAsqueda ai-answer-engine-referrer-mapping=asignaci%C3%B3n-de-referentes-de-motores-de-respuesta-de-ia h_01M2G7SJBDHFPEZ0WREHHD2YQF=asignaci%C3%B3n-de-referentes-de-motores-de-respuesta-de-ia android-app-referrers=referentes-de-apps-de-android h_01KGMEZQYCDS23MVW3MQH9Q5JQ=referentes-de-apps-de-android step-3-campaign-resolution=paso-3-resoluci%C3%B3n-de-la-campa%C3%B1a h_01KGMEER6ES1AYT24MC4HZCX9X=paso-3-resoluci%C3%B3n-de-la-campa%C3%B1a step-4-channel-classification=paso-4-clasificaci%C3%B3n-de-canales h_01KGMEER6ETWGFFM3E17KHMDAF=paso-4-clasificaci%C3%B3n-de-canales h_01_overriding-the-channel-with-af-channel=sobrescribir-el-canal-con-af_channel overriding-the-channel-with-af_channel=sobrescribir-el-canal-con-af_channel h_01_default-channel-classification=clasificaci%C3%B3n-predeterminada-del-canal default-channel-classification=clasificaci%C3%B3n-predeterminada-del-canal" />
