---
title: Configuración de la integración de ChatGPT Ads (OpenAI)
metadata:
  keywords:
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2026-07-05T13:42:23Z'
  edited_at: '2026-10-30T03:39:00Z'
  id: 48439655791249
  locale: es
  section: Measure paid media
  section_id: 6550990672401
  url: https://support.appsflyer.com/hc/es/articles/48439655791249
---
> **Resumen:** ChatGPT Ads, un partner integrado con AppsFlyer, es la plataforma publicitaria de OpenAI. Configura la integración para medir y atribuir las instalaciones de apps móviles, los eventos in-app y las conversiones del sitio web generadas por tus campañas de ChatGPT Ads.

## Sobre la integración con ChatGPT Ads

La integración de AppsFlyer con ChatGPT Ads (OpenAI) te permite medir y atribuir las instalaciones de apps, los eventos in-app y las conversiones del sitio web generadas por tus campañas de ChatGPT Ads. Es compatible con la medición tanto de apps móviles como de sitios web.

* **App móvil**: AppsFlyer atribuye las instalaciones y los re-engagements a tus campañas de ChatGPT Ads, y envía postbacks de eventos in-app.
* **Sitio web**: AppsFlyer reenvía los eventos web, como vistas de página, vistas de contenido y compras, capturados por el SDK web de AppsFlyer a la Conversions API (CAPI) de ChatGPT Ads, además del píxel JavaScript de ChatGPT Ads (o en lugar de este).

Si también utilizas el píxel de ChatGPT Ads en tu sitio web, ChatGPT Ads elimina los duplicados de los eventos del lado del servidor (enviados a través de la API de conversiones, o CAPI) frente a los eventos del píxel mediante un ID de evento compartido, para que puedas ejecutar CAPI y el píxel en paralelo sin inflar el recuento de conversiones.

Incluye ese ID compartido como `af_customer_event_id` en la carga útil del evento que envíes a AppsFlyer. Consulta [Integra tu sitio web](#integra-tu-sitio-web) a continuación.

## Configura la integración

Configura la integración por separado para cada app móvil y sitio web que quieras medir. Necesitarás un ID del píxel y una clave de API de tu cuenta de ChatGPT Ads (OpenAI) Ads Manager para cada uno.

**Requisitos previos:**

* Antes de configurar la integración, crea una cuenta en ChatGPT Ads.
* Tus aplicaciones móviles y web están configuradas en AppsFlyer. <Anchor target="_blank" href="/marketers/es/docs/adding-an-app-to-appsflyer">Saber más</Anchor>

**Para configurar la integración:**

1. **Para activar:** En AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Integraciones de partners** > la pestaña **Marketplace**.  
   **Para editar:** En AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Integraciones de partners** > la pestaña **Integraciones activas**.
2. Configura la integración para:

* [**App móvil**](#integra-tu-app-móvil): atribuye instalaciones, re-engagements y eventos in-app a las campañas de ChatGPT Ads.
* [**Sitio web**](#integra-tu-sitio-web): reenvía eventos de conversión web a la Conversions API de ChatGPT Ads, con deduplicación respecto al píxel de ChatGPT Ads.

## Integra tu app móvil

Sigue estos pasos para configurar la atribución y los postbacks de eventos in-app de ChatGPT Ads para tu app móvil.

**Para integrar tu app móvil:**

1. En AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Integraciones de partners** > la pestaña **Marketplace**.
2. Selecciona tu app móvil en el menú desplegable.  
   **Nota:** Deberás repetir estos pasos para cada plataforma en la que se ejecute tu app, como Android e iOS.
3. Busca **ChatGPT Ads (OpenAI)** y haz clic en **Integrar**.
4. Completa la configuración en las pestañas como se describe a continuación.

<div id="integration-tab" />

<Accordion title="Pestaña de integración">

#### Activar partner

**Para activar la integración:**

Activa el interruptor **Activar partner**.

**Nota importante:** El interruptor **debe permanecer activado** mientras trabajes con ChatGPT Ads. Si desactivas la integración, se desactivarán la atribución y los postbacks de tus campañas.  
Obtén más información sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activación del partner</Anchor>.

#### Configuración general

Introduce las siguientes credenciales:

* **ID del píxel**: se crea un píxel en tu ChatGPT Ads Manager. Puedes obtenerlo en la pestaña “Conversiones” de tu cuenta de Ads Manager.
* **Clave de API**: se requiere una clave de API para autenticar las llamadas a la Events API. Puedes obtenerla en la pestaña “Conversiones” de tu cuenta de ChatGPT Ads Manager.   
  **Nota:** Asegúrate de utilizar la clave de API de conversiones y no la clave de API de Ads Management, ya que los permisos necesarios requieren la clave de CAPI.

##### **Privacidad Avanzada**

El interruptor de Privacidad avanzada (AP) controla cómo se envían los eventos a OpenAI para los usuarios de iOS (14.5 y versiones posteriores) que no han puesto su IDFA a disposición (por parte del anunciante o del publisher):

* Privacidad avanzada **desactivada**: los eventos se envían con todos los identificadores de usuario disponibles (IP, agente de usuario, etc.), incluso cuando el IDFA no está disponible.
* Privacidad avanzada **activada**: solo se envían los eventos atribuidos a `openai_int`, y estos postbacks solo incluyen datos de atribución. Todos los identificadores a nivel de usuario se eliminan del postback antes de enviarlo.

> 📘 **Note**
>
> OpenAI no recopila ni comparte el IDFA en dispositivos iOS, por lo que la única forma de garantizar que se envíen postbacks sin atribuir es desactivar la privacidad avanzada.

##### **Compartición avanzada de datos de coincidencias avanzadas**

Actívalo para compartir los campos de coincidencias avanzadas, como el correo electrónico hashed, el número de teléfono hashed, el nombre hashed y el apellido hashed, con ChatGPT Ads, si estos campos se incluyen en la información del evento enviada a AppsFlyer. Para más información, consulta: <Anchor target="_blank" href="/marketers/es/docs/advanced-matching-data-sharing">Uso compartido de datos de Advanced Matching</Anchor>.

#### Postbacks predeterminados

Un postback es una notificación de servidor a servidor que AppsFlyer envía a ChatGPT Ads para informar de un evento atribuido (como una instalación o una acción in-app). En esta sección se muestran tus postbacks. Obtén información sobre cómo <Anchor target="_blank" href="/marketers/es/docs/set-up-re-attribution-window">configurar los postbacks de instalaciones y reatribuciones</Anchor>.

Obtén más información sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#default-postbacks">configuración de postbacks predeterminados</Anchor>.

#### Configuración de eventos in-app

Para poder enviar postbacks de eventos in-app a ChatGPT Ads, introduce las credenciales requeridas:

* ID de píxel
* Clave de la API

Para más información, consulta la sección [Configuración general](#configuración-general) anterior.

#### Postbacks de eventos in-app

Configura los postbacks de eventos in-app que se enviarán a ChatGPT Ads. <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration">Saber más</Anchor>

**Para habilitar los postbacks de eventos in-app:**

Activa el interruptor **Postbacks de eventos in-app**.

**Ventana de postback de eventos in-app**

Define el período posterior a una instalación, reatribución o re-engagement durante el cual AppsFlyer envía postbacks de eventos in-app a ChatGPT Ads. <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration">Saber más</Anchor>

**Mapea tus eventos**

Para asegurarte de que tus eventos coincidan con los eventos correspondientes en ChatGPT Ads, asigna los nombres de tus eventos. <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#mapeo-de-eventos">Saber más</Anchor>

ChatGPT Ads admite los siguientes eventos estándar, además de una alternativa **personalizada** para cualquier evento no incluido a continuación:

| Nombre del evento de ChatGPT Ads | Cuándo usar |
| --- | --- |
| página\_vista | El usuario accede o visualiza una página importante. |
| contents\_viewed | El usuario visualiza un producto, anuncio, artículo o contenido específico. |
| items\_added | El usuario añade uno o varios artículos al carrito, a un paquete o a una selección. |
| checkout\_started | El usuario inicia el proceso de compra. |
| order\_created | Compra completada. |
| registration\_completed | El usuario completa el registro de una cuenta o de un evento. |
| lead\_created | El usuario envía un formulario de lead o solicita que se pongan en contacto con él. |
| appointment\_scheduled | El usuario solicita una reunión, una demo o una consulta. |
| trial\_started | Comienza la prueba gratuita. |
| subscription\_created | Comienza la suscripción de pago. |
| app\_opened | El usuario abre la app móvil. |
| custom | Cualquier evento que no esté contemplado en la taxonomía estándar. |

**Desduplicación de eventos**

Si también utilizas el píxel de ChatGPT Ads en tu sitio web, envía el mismo ID de evento tanto a AppsFlyer como a ChatGPT Ads para que AppsFlyer pueda eliminar los duplicados de eventos:

* Incluye `af_customer_event_id` en la carga útil del evento que envías a AppsFlyer, dentro de eventValue para el SDK web o event\_value para la API S2S (server-to-server).
* Envía el mismo valor en el evento de píxel correspondiente.

AppsFlyer reenvía este valor a ChatGPT Ads como ID de evento. ChatGPT Ads luego lo usa para eliminar los duplicados del evento del lado del servidor que recibe de AppsFlyer frente al evento de píxel, para que AppsFlyer cuente la conversión una sola vez.

Si no envías `af_customer_event_id`, AppsFlyer genera un ID de evento automáticamente. Este ID no coincidirá con tus eventos de píxel.

Para más información, consulta Integrate AppsFlyer Web SDK.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlace de atribución">

ChatGPT Ads (OpenAI) admite enlaces de atribución.

#### Elige tu tipo de atribución

Decide si quieres:

1. Enviar a los usuarios directamente a la tienda de aplicaciones. Si es así, tendrás que crear un enlace de atribución para una sola plataforma o un <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">OneLink</Anchor> como URL final, en función de las necesidades de tu campaña y la configuración de targeting.   

   O
2. Usa una landing page como destino del anuncio y, después, usa <Anchor target="_blank" href="/marketers/es/docs/onelink-smart-script-overview">Smart Script</Anchor> o <Anchor target="_blank" href="/marketers/es/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banner</Anchor> para dirigir al usuario a la tienda de aplicaciones o a Google Play (mientras creas un enlace que permitirá la atribución).

#### Seleccionar parámetros

Selecciona los parámetros del enlace de atribución que quieres incluir.

* Selecciona los parámetros del enlace de atribución que quieras incluir (por ejemplo, **Nombre de la campaña** y **ID del sitio**) y configura la **ventana de lookback de clics** (el valor predeterminado recomendado por AppsFlyer es de 7 días). AppsFlyer genera automáticamente el enlace de atribución para utilizarlo en tus campañas de ChatGPT Ads.
* ChatGPT puede completar automáticamente los siguientes parámetros de URL mediante estas macros de URL dinámicas:
  * `af_partner_account_id={ad_account_id}`
  * `af_c_id={campaign_id}`
  * `af_adset_id={ad_group_id}`
  * `af_ad_id={ad_id}`
  * `clickid={oppref}`
* Las macros del campo de nombre no son compatibles.

> 🚧 **Importante**
>
> * Para que AppsFlyer capture el ID de clic de los anuncios de ChatGPT y lo envíe de vuelta a los anuncios de ChatGPT, asegúrate de usar `clickid={oppref}` si tus anuncios dirigen directamente a la tienda de aplicaciones o a Google Play. Si el destino del anuncio es una landing page con Smart Script, asegúrate de capturar el parámetro entrante `oppref` y asignarlo a `clickid` en la URL saliente.
> * ChatGPT Ads solo resuelve macros (como `{campaign_id}`) cuando los parámetros correspondientes se incluyen en el campo **Parámetros de tracking**, no en el campo **URL de destino del anuncio**. Pega tus parámetros de consulta (por ejemplo, `af_c_id={campaign_id}`) en el campo **Parámetros de tracking** y usa el campo **URL de destino del anuncio** solo para la propia URL de destino.

**Nota:** El enlace generado incluye `openai_int` (el ID de integración de ChatGPT Ads en AppsFlyer).

Saber más sobre los <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#attribution-link-tab">enlaces de atribución</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costo">

Actualmente no existe una integración con la API de costos para ChatGPT Ads.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de ingresos por publicidad">

No es posible obtener datos de ingresos por anuncios desde ChatGPT Ads. Utiliza postbacks o señales de UA para compartir datos de ingresos por anuncios y optimizar las campañas.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

Activa **Permisos de la ad network** para conceder al equipo de ChatGPT Ads acceso a tus datos. Una vez activado, selecciona los permisos individuales que deseas conceder, como configurar la integración, acceder a los reportes de retención y cohortes o consultar datos agregados de conversiones e ingresos. Ten en cuenta que, aunque la atribución esté deshabilitada para ChatGPT Ads, podrás seguir concediendo permisos.

Obtén más información sobre los <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos</Anchor>.

</Accordion>

## Integra tu sitio web

Sigue estos pasos para configurar el reenvío de eventos del lado del servidor a ChatGPT Ads para tu sitio web.

**Para integrar tu sitio web:**

1. En AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Integraciones de partners** > la pestaña **Marketplace**.
2. Selecciona tu aplicación web en el menú desplegable.
3. Busca **ChatGPT Ads (OpenAI)** y haz clic en **Integrar**.
4. Completa la configuración en la pestaña Integración como se describe a continuación.

<div id="integration-tab::2739744d" />

<Accordion title="Pestaña de integración">

#### Activar partner

**Para activar la integración:**

Activa el interruptor **Activar partner**.

**Nota importante:** El interruptor **debe permanecer activado** mientras trabajes con ChatGPT Ads. Si desactivas la integración, se desactivará el reenvío de eventos de tu sitio web.  
Obtén más información sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activación del partner</Anchor>.

#### Configuración de eventos in-app

Para poder enviar postbacks de eventos a ChatGPT Ads, introduce las siguientes credenciales:

* **ID del píxel**: se crea un píxel en tu ChatGPT Ads Manager. Puedes obtenerlo en la pestaña “Conversiones” de tu cuenta de Ads Manager.
* **Clave de API**: se requiere una clave de API para autenticar las llamadas a la Events API. Puedes obtenerla en la pestaña “Conversiones” de tu cuenta de ChatGPT Ads Manager.

**Uso compartido de datos de Advanced Matching:** Actívalo para compartir con ChatGPT Ads los campos de Advanced Matching, como el correo electrónico con hash, el número de teléfono con hash, el nombre con hash y el apellido con hash, si estos campos se incluyen en la información del evento enviada a AppsFlyer. Para más información, consulta: <Anchor target="_blank" href="/marketers/es/docs/advanced-matching-data-sharing">Uso compartido de datos de Advanced Matching</Anchor>.

#### Postbacks de eventos in-app

Configura los postbacks de eventos que se enviarán a ChatGPT Ads. <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration">Saber más</Anchor>

**Para habilitar los postbacks de eventos:**

Activa el interruptor **Postbacks de eventos in-app**.

**Mapea tus eventos**

Para asegurarte de que tus eventos coincidan con los eventos equivalentes en ChatGPT Ads, asocia los nombres de tus eventos. Consulta la tabla de eventos estándar anterior para ver los eventos compatibles con ChatGPT Ads. <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#mapeo-de-eventos">Saber más</Anchor>

</Accordion>

<div id="h_01KWVSPJ9WATTRLNK" />

<Accordion title="Pestaña de enlace de atribución">

ChatGPT Ads (OpenAI) no utiliza enlaces de atribución externos para las integraciones de sitios web. El SDK web de AppsFlyer mide los eventos web y los reenvía directamente a la Conversions API de ChatGPT Ads, por lo que no es necesario configurar la atribución basada en enlaces.

</Accordion>

<div id="h_01KWVSPJ9WCOST" />

<Accordion title="Pestaña de costo">

Los datos de costos no están disponibles para las integraciones de sitios web con ChatGPT Ads.

</Accordion>

<div id="h_01KWVSPJ9WADREV" />

<Accordion title="Pestaña de ingresos por publicidad">

Los datos de ingresos por anuncios no están disponibles para las integraciones de sitios web con ChatGPT Ads.

</Accordion>

<div id="h_01KWVSPJ9WPERM" />

<Accordion title="Pestaña de permisos">

Los permisos no están disponibles para las integraciones de sitios web con ChatGPT Ads.

</Accordion>

## Características y limitaciones

| Caducado | Descripción |
| --- | --- |
| Países compatibles | <Anchor target="_blank" href="https://help.openai.com/en/articles/20001245-ads-manager-availability">Lista de países</Anchor> donde ChatGPT Ads Manager está disponible. |

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">Integraciones de partners</Anchor>

<div data-zendesk-anchors="about-the-integration=sobre-la-integraci%C3%B3n-con-chatgpt-ads h_01KWS8SS8RE2VQ275MFB7CT39J=sobre-la-integraci%C3%B3n-con-chatgpt-ads set-up-the%20integration=configura-la-integraci%C3%B3n h_01H95QTA3Z5HXW39AHAF8FMFWH=configura-la-integraci%C3%B3n integrate-your-mobile-app=integra-tu-app-m%C3%B3vil h_01KWVBQG0G85W6QJ8AT2520GTX=integra-tu-app-m%C3%B3vil h_01KWVK5J7FBA81238JD4AD0219=integration-tab activate-partner=activar-partner h_01H95QTA3ZGEM34HY1A7NC8NX7=activar-partner general-settings=configuraci%C3%B3n-general h_01KWVKHV36H34XCHYBFRHNF8TB=configuraci%C3%B3n-general h_01M39MMERMEBK470T0NDCVRN2E=privacidad-avanzada h_01M39MP266X5KME19RBVQZRDE6=compartici%C3%B3n-avanzada-de-datos-de-coincidencias-avanzadas default-postbacks=postbacks-predeterminados h_01KWVKZJ7AZ8Z4CFM8J0PV071A=postbacks-predeterminados inapp-event-settings=configuraci%C3%B3n-de-eventos-in-app h_01JTDP2T0BFP5WP03X5EMXVAWA=configuraci%C3%B3n-de-eventos-in-app inapp-event-postbacks=postbacks-de-eventos-in-app h_01KWVMZC74AQSN7BDQP2QQWBT4=postbacks-de-eventos-in-app h_01KWVK5J7FE0ZF74NGXKSASMBV=attribution-link-tab h_01_choose-your-attribution-type=elige-tu-tipo-de-atribuci%C3%B3n choose-your-attribution-type=elige-tu-tipo-de-atribuci%C3%B3n h_01_select-parameters=seleccionar-par%C3%A1metros select-parameters=seleccionar-par%C3%A1metros h_01M254BFC0V68RJ6B903D8XKD3=importante h_01KWVK5J7FK8BAQKEMNA35ABPY=cost-tab h_01KWVK5J7FQRYXQ9FGCWHWY16T=ad-revenue-tab h_01KWVK5J7G3E8NSNDG4CR9FA7N=permissions-tab integrate-your-website=integra-tu-sitio-web h_01KWVSJRYSQEH12C5RH7BN4CC2=integra-tu-sitio-web h_01KWVSPJ9WJERF84ZNGTS7P0HZ=integration-tab::2739744d activate-partner::3c5a91e7=activar-partner-1 h_01KWVSPJ9WBQ2AS5JZPTJZPTRG=activar-partner-1 inapp-event-settings::a3adef08=configuraci%C3%B3n-de-eventos-in-app-1 h_01KWVSPJ9WV7ZQZD00ZB7T639X=configuraci%C3%B3n-de-eventos-in-app-1 inapp-event-postbacks::c3d06354=postbacks-de-eventos-in-app-1 h_01KWVSPJ9WA7Q1M281Q5NBYHV7=postbacks-de-eventos-in-app-1 attribution-link-tab::3e2b1646=h_01KWVSPJ9WATTRLNK cost-tab::c486dc3c=h_01KWVSPJ9WCOST ad-revenue-tab::84884d8a=h_01KWVSPJ9WADREV permissions-tab::6f805250=h_01KWVSPJ9WPERM traits-and-limitations=caracter%C3%ADsticas-y-limitaciones h_01KX3DAS0FBTKGKE7CZJTDTY2X=caracter%C3%ADsticas-y-limitaciones h_01KWVT1XJ2FKP1CACRV24C1R8E=consulta-tambi%C3%A9n" />
