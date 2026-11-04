---
title: >-
  [Legacy] Configuración de la integración de X Ads (anteriormente Twitter Ads)
  anuncios
deprecated: true
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2025-06-22T11:41:06Z'
  edited_at: '2026-09-17T00:30:13Z'
  id: 36433415114769
  locale: es
  section: X Ads (formerly Twitter Ads)
  section_id: 6551370375569
  url: https://support.appsflyer.com/hc/es/articles/36433415114769
---
> **En resumen:** Integra tu cuenta de X Ads con AppsFlyer para mostrar los datos de atribución de las campañas de X Ads.

<div id="connecting-your-x-ads-account-to-appsflyer" />

## Conexión de tu cuenta de X Ads a AppsFlyer

<Accordion title="Ver">

<Embed title="[Legacy] Configuración de la integración de X Ads (anteriormente Twitter Ads) anuncios" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/a65pnqoyxw" providerUrl="https://fast.wistia.com" />

</Accordion>

<Accordion title="Leer texto">

<div id="before-you-begin" />

> 📘 **Antes de comenzar**
>
> Asegúrate de haber <Anchor target="_blank" href="https://business.twitter.com/en/help/account-setup/billing-basics.html">agregado un método de pago</Anchor> a tu cuenta de X Ads. De lo contrario, no podrás activar la integración del partner en AppsFlyer.

1. Inicia sesión en tu cuenta de X Ads en <Anchor target="_blank" href="https://ads.twitter.com">ads.twitter.com</Anchor>  
   Si no se te dirige automáticamente a la página de anuncios, haz clic en el botón Anuncios en la esquina superior izquierda.
2. Cuando se te pida que selecciones una campaña **Simple (NUEVA)** o **Avanzada**, selecciona **Avanzada**.
3. En **Objetivo de la campaña**, selecciona **Instalaciones de la app** o **Re-engagements de la app** y, a continuación, haz clic en **Siguiente**.

   ![twitter-campaign-objective.png](https://files.readme.io/44e5aca3895fc5aefa22f91542b9c23f9798b246ac8086e97a3994244fc2c5a8-36433415100561.png)
4. Elige tu aplicación y, a continuación, haz clic en el **enlace del partner de medición móvil**.
5. En la página **Seguimiento de conversiones** , haz clic en **Ir a AppsFlyer**. 

   ![twitter-mmp-selection.png](https://files.readme.io/718bc93d2fcf606a8c165aed70364659ba23b74891b22775c5522ee9e4c7901a-36433422307345.png)
6. Aparece una notificación que te informa de que estás a punto de salir de X Ads para ir al sitio web de AppsFlyer. Haz clic en **Ir a AppsFlyer** e inicia sesión en tu dashboard.

   <Image alt="twitter-go-to-appsflyer.png" src="https://files.readme.io/bca10eea5032a495fd38c996d0aa4a9f2db8a285211e6cf0860dd6f21bcfa670-36433422307601.png" width="576px" />
7. En AppsFlyer, en el menú lateral, selecciona **Collaborate** > **Partner Integrations > Marketplace** tab.
8. Busca **X Ads** y selecciónalo.
9. En la pestaña **Integración** , acepta los Términos y Condiciones de X Ads para el registro de conversiones en aplicaciones móviles (MACT) y luego haz clic en **Guardar integración**.
10. Activa **Activar partner** y haz clic en **Iniciar sesión con X Ads**.
11. Autoriza a AppsFlyer a usar tu cuenta de X Ads haciendo clic en **Autorizar aplicación**.

    [<Image alt="" src="https://support.appsflyer.com/hc/en-us/article_attachments/4411037924497/Twitter_Ads_6.png" width="476px" />](https://support.appsflyer.com/hc/en-us/article_attachments/4411037924497/Twitter_Ads_6.png)
12. Activa de nuevo **Activar partner** para mostrar la configuración de la pestaña **Integración** y habilitar la atribución.  
    **Nota:** El selector debe permanecer activado (activado) mientras trabajes con el partner. Saber más sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activación de partners.</Anchor>
13. Selecciona tus cuentas de X Ads para activarlas y, a continuación, haz clic en **Guardar & cerrar**.

    ![twitter_account_name.png](https://files.readme.io/d74e9b3edd08c4ca3396b95ae20e20db99bcbe1a220318403bd6c9d6f9600282-36433415108497.png)

</Accordion>

<div id="x-ads-attribution-setup" />

## Configuración de la atribución de X Ads

Para ver una descripción detallada del encabezado de la página de configuración del partner, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">aquí</Anchor>.

<div id="integration-tab" />

<Accordion title="Pestaña de integración">

La pestaña **Integración** está dividida en diferentes secciones, tal como se describe a continuación. El <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">partner debe estar activado</Anchor> al momento de la primera visita para permitir su configuración.

<div id="ad-account-connected" />

### Cuenta de anuncios conectada

Selecciona las cuentas para habilitar la atribución.

![Twitter_msc_new_4.png](https://files.readme.io/8b8ecdfd79bc87d4a65766ce67e48a06524d825e04d5e642eb5e9741069a2f6c-36433422308241.png)

<div id="click-through-attribution" />

### Atribución por clic

Utiliza el control deslizante para establecer el **tiempo máximo desde el clic hasta la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de la ventana de lookback pueden atribuirse a X Ads.

Puedes personalizar este valor para que sea de 1-23 horas o de 1-30 días. Te recomendamos configurar la ventana de lookback por clics en 14 días para que coincida con X Ads.

![Twitter_msc_new_6.png](https://files.readme.io/359f6145751f45d38c151572f1ba0c525d232d16ffaee6b68453da0bc1826a69-36433422308369.png)

<div id="view-through-attribution-lookback-window" />

### Ventana de lookback de atribución view-through

Este control deslizante te permite establecer el **tiempo máximo de la impresión a la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de esta ventana de lookback, tras la impresión de un anuncio, se atribuyen a X Ads, siempre que no haya habido ningún otro clic en el anuncio correspondiente.

Puedes personalizar este valor para que sea de 1-23 horas o de 1-7 días. Te recomendamos configurar la ventana de lookback por impresiones en 1 día para que coincida con X Ads.

![Twitter_msc_new_7.png](https://files.readme.io/15c9d815b05c03dfdf8578ed5af297c411991ab74accc5539fc1dbca178c3336-36433422308497.png)

<div id="re-engagement-settings" />

### Configuración de re-engagement

Para campañas de retargeting en X Ads, AppsFlyer solo admite **Re-engagement** medición. Eso es un engagement con una campaña de retargeting por parte de un usuario que ya tiene la aplicación instalada en el momento del engagement. **Actualmente, X Ads no admite la medición de re-engagement.**

<div id="important" />

> 🚧 **¡Importante!**
>
> Asegúrate de que el retargeting esté habilitado para la aplicación en la página de ajustes de la aplicación. Para más detalles, haz clic <Anchor target="_blank" href="/marketers/es/docs/app-settings#reengagement-attribution">aquí</Anchor>.

<div id="re-engagement-click-through-lookback-window" />

#### Ventana de lookback por click-through de re-engagement

Define la duración de la **ventana de lookback por click-through de re-engagement** (el período de tiempo máximo después de hacer clic en un anuncio, dentro del cual un usuario reorientado puede atribuirse al anuncio). Puedes definir el valor en horas (hasta 23) o en días (1-30).

![twitter-reengagement-activate.png](https://files.readme.io/318deeab0432870035a163a7b8a5b8c03be7d683bfc369104c8577674fde0036-36433422309905.png)

<div id="re-engagement-view-through-lookback-window" />

#### Ventana de lookback por view-through de re-engagement

Para comenzar a atribuir impresiones de anuncios de retargeting, activa la **Atribución por view-through de re-engagement**.

Luego, define la duración de la **ventana de lookback por view-through de re-engagement** (el período de tiempo máximo después de que se visualiza un anuncio, dentro del cual un usuario reorientado puede atribuirse al anuncio). Puedes definir el valor en horas (hasta 23) o en días (1-7):

![twitter-reengagement-view-through.png](https://files.readme.io/4faf93b6d8a8e45043eb9440d8f56a70eba2da51f3a572ea6cd698e072f033c6-36433415112849.png)

<div id="re-engagement-window" />

#### Ventana de re-engagement

Define la duración de la **Ventana de re-engagement** (el período dentro del cual los eventos in-app del usuario se atribuyen a la fuente de medios de retargeting). Puede configurar el valor en días (1-90), horas (hasta 23) o incluso de por vida:

![Twitter-reengagement-window.png](https://files.readme.io/5bc42bd967929a88fd38f8bdd9cc36046a6f0381d1883ab1f26f5c680185a74c-36433415113105.png)

<div id="in-app-event-postback-settings" />

### Configuración de postbacks de eventos in-app

En esta sección, puedes asignar tus eventos de AppsFlyer con tus partners a través de postbacks.

[![In-app_event_postbacks_es-us.png](https://files.readme.io/d89725172c53c309b5b58227ce53812e12f9cd4ee7611a6c375970b395122b15-36433415113361.png)](https://files.readme.io/d89725172c53c309b5b58227ce53812e12f9cd4ee7611a6c375970b395122b15-36433415113361.png)

**Para configurar postbacks de eventos in-app:**

1. Configura el **ID de partner** (si es necesario).
2. Habilita los **postbacks de eventos in-app.**
3. Haz clic en **Agregar evento** para agregar un evento de SDK o de servidor a servidor a la lista.
4. Completa los parámetros requeridos de acuerdo a la tabla a continuación.

| Parámetro | Nota |
| --- | --- |
| **Evento de AppsFlyer** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea del SDK integrado en tu aplicación o de los eventos servidor a servidor.<br />**Consejo**: ¿No encuentras el evento que estás buscando?<ul><li>Asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar.</li><li>Escríbelo en **Evento de AppsFlyer**, y luego haz clic en **Crear personalizado**. Obtén más información sobre la <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#eventos-personalizados">asignación de eventos personalizados</Anchor>.</li></ul> |
| **Asignado al evento de partner** | El nombre o ID único de cada evento, tal como lo define el partner. Posibles <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#mapeo-de-eventos">configuraciones de asignación</Anchor>:<ul><li>**Campo de texto:** Obtén el ID del evento correspondiente del partner.</li><li>**Cuadro desplegable:** Selecciona el evento de AppsFlyer predefinido más adecuado.</li><li>**Como está**: Envía los eventos tal como están, sin asignación de nombres.</li></ul> |
| **para usuarios de** | Selecciona la opción de envío para el evento:<br /><br /><br /><br />**<span id="note"></span><span id="h_01HDJVBAEZATGM580CNC7BCVTN"></span>Nota:**<br />Para que X Ads reciba los postbacks atribuidos a la agencia, debes seleccionar **Todas las fuentes de medios, incluidas las orgánicas**. De lo contrario, X Ads no recibirá tales postbacks.<ul><li>**Solo este partner**: envía postbacks solo cuando este evento se atribuye a este partner.</li><li>**Todas las fuentes de medios, incluidas las orgánicas**: envían postbacks de eventos atribuidos a cualquier partner y eventos orgánicos.</li></ul> |
| **incluyendo** | <ul><li>**Sin datos (predeterminado)**: envía solo el evento en sí sin el valor del evento.</li><li>**Valores e ingresos**: envía todos los parámetros del evento, **incluido** el valor de ingresos (si existe en el evento).</li><li>**Valores sin ingresos**: envía todos los parámetros **excluyendo** el valor de ingresos.</li></ul> |

5. [Opcional] Haz clic en <Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" /> para establecer condiciones para enviar determinados eventos in-app al partner.  
   Saber más sobre <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#postbacks-condicionales-de-eventos-in-app">postbacks de eventos in-app condicionales</Anchor>.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlace de atribución">

X Ads no utiliza enlaces de atribución para la atribución.

> 📘 **Advertencia**
>
> Para todas las <Anchor target="_blank" href="/marketers/es/docs/self-reporting-networks-srns">redes de autorreporte (SRN)</Anchor>, como Meta Ads, Apple Search Ads, Google Ads, X Ads, etc., esta pestaña no es funcional ya que no utilizan enlaces de atribución externos.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costo">

La integración de costos proporciona los siguientes datos agregados:

* Datos de costos para tus campañas, conjuntos de anuncios, anuncios, canal y geo/países. Consulta la <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabla de integración de costos de redes de publicidad</Anchor> para obtener más información sobre las dimensiones, métricas y funciones admitidas.  
  **Nota:** Los datos de costos requieren una suscripción a <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor> .
* Datos sobre clics, impresiones y datos enriquecidos (palabras clave, nombres de campañas y conjunto de anuncios).

**Para habilitar la API de costos**:

* Sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">estas instrucciones de integración</Anchor>.

<Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Visualiza el estado de tu API de costos</Anchor> y la última vez que AppsFlyer logró extraer los datos de costos coincidentes en el dashboard de estado de la integración de costos (e ingresos por publicidad) o en el dashboard de la red de publicidad individual.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Los ingresos por anuncios no están disponibles actualmente para X Ads.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres otorgarle a X Ads, sea que el partner actúe como ad network, agencia o ambas. Ten en cuenta que, incluso si la atribución estuviera deshabilitada para X Ads, la pestaña permisos se encontraría activa y podrías otorgarle el control a X Ads.

Usa estos selectores para otorgarle permisos a una ad network para que maneje su propia configuración de tu aplicación:

<div id="ad-network-permissions" />

### Permisos de ad network

* **Permitir la configuración de la integración**: permite que el partner configure la pestaña integración (con excepción de postbacks de eventos in-app).
* **Permitir la configuración de postbacks de eventos in-app**: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña integración.
* **Permitir el acceso a tu reporte de retención**: solo para los datos propios de retención del partner.
* **Permitir acceso a tus datos agregados de usuarios legales**: solo para los datos propios de usuarios leales del partner.
* **Permitir acceso a tus datos agregados de eventos in-app**: solo a los datos de eventos in-app propios del partner
* **Permitir acceso a tus datos agregados de ingresos**: solo para los datos de ingresos atribuidos al partner.
* **Permitir el acceso a tu dashboard de Protect360**: solo para los datos propios de Protect360 del partner, y siempre que la característica esté habilitada para el anunciante.

Saber más sobre cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos de ad network.</Anchor>

<div id="agency-permissions" />

### Permisos de la agencia

Saber más sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permisos-de-la-agencia">concesión de permisos de agencia</Anchor>.

</Accordion>

<div id="advanced-x-ads-setup-video" />

## Video de configuración avanzada de X Ads

<Accordion title="Ver">

<Embed title="[Legacy] Configuración de la integración de X Ads (anteriormente Twitter Ads) anuncios" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/3ypfld8enr" providerUrl="https://fast.wistia.com" />

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Especificaciones y limitaciones">

| Caducado | Observaciones |
| --- | --- |
| Atribución de pre-roll no soportada | X Ads no admite la atribución MMP para campañas de pre-roll. |
| Nombres | El dashboard muestra IDs en lugar de nombres para los **nombres de elementos de línea** (nombres de conjuntos de anuncios) y los **nombres de publicaciones** (nombres de anuncios). Esto se debe a que AppsFlyer recibe de X Ads solo los IDs para estos elementos y no sus nombres. |
| Coste | Para X Ads, los datos de costo de las campañas exclusivas de SKAN (campañas que solo tienen instalaciones de SKAN y ninguna instalación "normal") no están disponibles para las agencias. La integración de costo debe ser configurada por el anunciante. Y solo el anunciante puede ver los datos. |

Especificaciones y limitaciones

</Accordion>

<div data-zendesk-anchors="connecting-your-twitter-ads-account-to-appsflyer=conexi%C3%B3n-de-tu-cuenta-de-x-ads-a-appsflyer h_01HDJVCRYQESA17XZ83GS81YZ3=conexi%C3%B3n-de-tu-cuenta-de-x-ads-a-appsflyer h_01HDJVBAEZXA0WJ94JYMK84MAX=antes-de-comenzar twitter-ads-attribution-setup=configuraci%C3%B3n-de-la-atribuci%C3%B3n-de-x-ads h_01HDJVBAEZ5W3JH1BN7WXJ08P6=configuraci%C3%B3n-de-la-atribuci%C3%B3n-de-x-ads h_01HDJVBAEZSFKRXAKQJP58N550=integration-tab ad-account-connected=cuenta-de-anuncios-conectada h_01HDJVBAEZD89BSGHQTPR84HSC=cuenta-de-anuncios-conectada clickthrough-attribution=atribuci%C3%B3n-por-clic h_01HDJVBAEZFJWQ6FD4Q4GSPD76=atribuci%C3%B3n-por-clic viewthrough-attribution-lookback-window=ventana-de-lookback-de-atribuci%C3%B3n-view-through h_01HDJVBAEZ2H91WBHNSMRQYQ7H=ventana-de-lookback-de-atribuci%C3%B3n-view-through reengagement-settings=configuraci%C3%B3n-de-re-engagement h_01HDJVBAEZZR1W06YH4XJSBKHV=configuraci%C3%B3n-de-re-engagement h_01JV9YQ7ZHRDD2NA5ENQXJQ31V=importante reengagement-clickthrough-lookback-window=ventana-de-lookback-por-click-through-de-re-engagement h_01HDJVBAEZ59ERYD2WQQYK6T37=ventana-de-lookback-por-click-through-de-re-engagement reengagement-viewthrough-lookback-window=ventana-de-lookback-por-view-through-de-re-engagement h_01HDJVBAEZSCK7430NJ8AMQYVY=ventana-de-lookback-por-view-through-de-re-engagement reengagement-window=ventana-de-re-engagement h_01HDJVBAEZCMWY5X47FEEFXTBX=ventana-de-re-engagement inapp-event-postback-settings=configuraci%C3%B3n-de-postbacks-de-eventos-in-app h_01HDJVBAEZ5ZM9RDXPWTJPPYVA=configuraci%C3%B3n-de-postbacks-de-eventos-in-app h_01HDJVBAEZR1Q2SVE9MEQ9EXKP=attribution-link-tab h_01HDJVBAEZ7R7BKFAZYXXBGS5Y=advertencia h_01HDJVBAEZYSWN59VNXTDEWX93=cost-tab h_01HDJVBAF0VPBBAEHJPG40HJP8=ad-revenue-tab h_01HDJVBAF0KEVSWJ0EW54AEAWV=permissions-tab ad-network-permissions=permisos-de-ad-network h_01HDJVBAF0BMSCKF6J9NJ019YJ=permisos-de-ad-network agency-permissions=permisos-de-la-agencia h_01HDJVBAF0W3ZE7J93CRE8EBRP=permisos-de-la-agencia advanced-twitter-ads-setup-video=video-de-configuraci%C3%B3n-avanzada-de-x-ads h_01HDJVBAF0SJ93TNQ8WSFVE91P=video-de-configuraci%C3%B3n-avanzada-de-x-ads h_01HGWGG2422VR9PFV88AMEHNT8=traits-and-limitations" />
