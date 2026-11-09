---
title: Configuración de la integración de X Ads (anteriormente Twitter Ads)
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T09:33:40Z'
  edited_at: '2026-09-17T00:30:19Z'
  id: 4410472471825
  locale: es
  section: X Ads (formerly Twitter Ads)
  section_id: 6551370375569
  url: https://support.appsflyer.com/hc/es/articles/4410472471825
---
> **En resumen:** Integra tu cuenta de X Ads con AppsFlyer para mostrar los datos de atribución de las campañas de X Ads.

<div id="overview" />

## Observaciones

X Ads es una Red Avanzada de Autorreporte (SRN), que permite a AppsFlyer atribuir eventos de conversión para todos los usuarios, incluso aquellos sin un ID de publicidad.

<div id="x-ads-attribution-flow-in-appsflyer" />

### Flujo de atribución de X-Ads en AppsFlyer

**El flujo de atribución de AppsFlyer para X Ads es el siguiente:**

1. AppsFlyer recibe todos los datos de engagement de X Ads a través de la integración de servidor a servidor (S2S) y atribuye los engagement de la siguiente manera:
   * Si tanto el evento de instalación como el engagement incluyen un ID de anunciante móvil (MAID), AppsFlyer realiza una coincidencia de ID determinista.
   * Si en la instalación o en el engagement falta un ID publicitario, se utiliza el modelado probabilístico para la atribución, a menos que el cliente lo haya configurado de otra manera.
2. AppsFlyer envía todos los postbacks de instalación a X Ads a través de la integración, independientemente de si la instalación se atribuye a X Ads.
3. Cuando el usuario rechaza el consentimiento de App Tracking Transparency (ATT) y la Privacidad Avanzada (AP) está activa, ciertos campos dentro de los postbacks enviados a X Ads estarán restringidos. Los campos restringidos son:

   * ID de engagement de X Ads
   * ID de dispositivo hash
   * Dirección IP
   * Agente de usuario

   <Image align="center" alt="_- visual selection.png" src="https://files.readme.io/8c17755d275e732f88cf93e8e7e33df891911dd640d2dbfc2637313a9d59d43e-small-36433399199249.png" />

<div id="connecting-your-x-ads-account-to-appsflyer" />

## Conexión de tu cuenta de X Ads a AppsFlyer

<div id="note" />

> 📘 **Nota:**
>
> Antes de comenzar, asegúrate de haber agregado un método de pago a tu cuenta de X Ads. De lo contrario, no podrás activar la integración del partner en AppsFlyer.

1. Inicia sesión en tu cuenta de X Ads en <Anchor target="_blank" href="https://business.x.com/en/advertising">X Ads.</Anchor>  
   Si no se te dirige automáticamente a la página de anuncios, haz clic en el botón Anuncios en la esquina superior izquierda.
2. Cuando se te pida que selecciones una campaña **Simple (NUEVA)** o **Avanzada**, selecciona **Avanzada**.
3. En **Objetivo de la campaña**, selecciona **Instalaciones de la app** o **Re-engagements de la app** y, a continuación, haz clic en **Siguiente**.

   <Image align="center" alt="X-Ads-campaign-objective.png" src="https://files.readme.io/44e5aca3895fc5aefa22f91542b9c23f9798b246ac8086e97a3994244fc2c5a8-36433415100561.png" />
4. Elige tu aplicación y, a continuación, haz clic en el enlace del **partner de medición móvil**.
5. En la página **Seguimiento de conversiones**, haz clic en **Ir a AppsFlyer**.

   <Image align="center" alt="X-Ads-mmp-selection.png" src="https://files.readme.io/718bc93d2fcf606a8c165aed70364659ba23b74891b22775c5522ee9e4c7901a-36433422307345.png" />
6. Aparece una notificación que te informa de que estás a punto de salir de X Ads para ir al sitio web de AppsFlyer. Haz clic en **Ir a AppsFlyer** e inicia sesión en tu dashboard.
7. En AppsFlyer, en el menú lateral, selecciona **Collaborate** > **Partner Integrations > Marketplace** tab.
8. Busca **X Ads** y selecciónalo.
9. En la pestaña **Integración**, acepta los Términos y Condiciones de X Ads para el registro de conversiones en aplicaciones móviles (MACT) y luego haz clic en **Guardar integración**.
10. Activa **Activar partner** y haz clic en **Iniciar sesión con X Ads**.
11. Autoriza a AppsFlyer a usar tu cuenta de X Ads haciendo clic en **Autorizar aplicación**.
12. Activa de nuevo **Activar partner** para mostrar la configuración de la pestaña **Integración** y habilitar la atribución.  
    **Nota:** El activador debe permanecer encendido (activado) mientras trabajes con el partner. Saber más sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activación de partners</Anchor>.
13. Selecciona tus cuentas de X Ads para activarlas y, a continuación, haz clic en **Guardar y cerrar**.

<div id="x-ads-attribution-setup" />

## Configuración de la atribución de X Ads

Para ver una descripción detallada del encabezado de la página de configuración del partner, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">aquí</Anchor>.

<div id="integration-tab" />

<Accordion title="Pestaña de integración">

La pestaña **Integración** está dividida en diferentes secciones, tal como se describe a continuación. El <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">partner debe estar activado</Anchor> al momento de la primera visita para permitir su configuración.

<div id="ad-account-connected" />

### Cuenta de anuncios conectada

Selecciona las cuentas para habilitar la atribución.

<Image align="center" alt="X-Ads_msc_new_4.png" src="https://files.readme.io/8b8ecdfd79bc87d4a65766ce67e48a06524d825e04d5e642eb5e9741069a2f6c-36433422308241.png" />

**Nota:** Puedes conectar hasta 200 cuentas de anuncios en AppsFlyer. Para evitar alcanzar este límite y asegurar la atribución continua para todas las cuentas activas, recomendamos eliminar cualquier cuenta de anuncios que ya no esté en uso.

<div id="advanced-privacy" />

### Privacidad avanzada

Solo para aplicaciones iOS: El interruptor de **Privacidad Avanzada (AP)** te permite controlar el nivel de datos de usuario compartidos con X Ads a través de postbacks. Esta configuración cumple con los requisitos de privacidad de iOS 14.5+.  
Cuando el interruptor de AP está ACTIVADO:

* Los postbacks siguen la <Anchor target="_blank" href="/partners/es/docs/advanced-privacy-guide-postback-macros-for-ad-networks">plantilla de Privacidad Avanzada</Anchor>.
* Solo se comparten <Anchor target="_blank" href="/marketers/es/docs/apply-aggregated-advanced-privacy-framework">datos agregados y anónimos</Anchor>. No se incluyen identificadores a nivel de dispositivo.

<div id="note-1" />

> 📘 **Nota**
>
> * El interruptor de Privacidad Avanzada está **activado por defecto** al activar la integración de X Ads.
> * Según X Ads, mantener la Privacidad Avanzada en **ON** puede resultar en **subreportes** de eventos de campaña y limitar la optimización del rendimiento en X Ads.

<div id="click-through-attribution" />

### Atribución click-through

Utiliza el control deslizante para establecer el **tiempo máximo desde el clic hasta la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de la ventana de lookback pueden atribuirse a X Ads.

Puedes personalizar este valor para que sea de 1-23 horas o de 1-30 días. Te recomendamos configurar la ventana de lookback por clics en 14 días para que coincida con X Ads.

<Image align="center" alt="X-Ads_msc_new_6.png" src="https://files.readme.io/359f6145751f45d38c151572f1ba0c525d232d16ffaee6b68453da0bc1826a69-36433422308369.png" />

<div id="view-through-attribution-lookback-window" />

### Ventana de lookback de atribución view-through

Este control deslizante te permite establecer el **tiempo máximo de la impresión a la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de esta ventana de lookback, tras la impresión de un anuncio, se atribuyen a X Ads, siempre que no haya habido ningún otro clic en el anuncio correspondiente.

Puedes personalizar este valor para que sea de 1-23 horas o de 1-7 días. Te recomendamos configurar la ventana de lookback por impresiones en 1 día para que coincida con X Ads.

<Image align="center" alt="X-Ads_msc_new_7.png" src="https://files.readme.io/15c9d815b05c03dfdf8578ed5af297c411991ab74accc5539fc1dbca178c3336-36433422308497.png" />

<div id="reinstall-settings" />

### Configuración de reinstalación

Para habilitar la atribución de reinstalación, activa el interruptor de **Atribución de reinstalación**. La atribución de reinstalaciones te permite medir a los usuarios que reinstalan tu app durante su ventana de reatribución.

No es necesario configurar ventanas de lookback para la atribución de reinstalación, ya que los valores se toman de la configuración de atribución de instalación. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/measure-reinstalls">Medir reinstalaciones</Anchor>.

<div id="re-engagement-settings" />

### Configuración de re-engagement

Para campañas de retargeting en X Ads, AppsFlyer solo admite la medición de **re-engagement**. Eso es un engagement con una campaña de retargeting por parte de un usuario que ya tiene la aplicación instalada en el momento del engagement.

<div id="important" />

> 🚧 **¡Importante!**
>
> Asegúrate de que el retargeting esté habilitado para la aplicación en la página de ajustes de la aplicación. Para más detalles, haz clic <Anchor target="_blank" href="/marketers/es/docs/app-settings#reengagement-attribution">aquí</Anchor>.

La atribución de retargeting de X Ads incluye solo las conversiones de re-engagement.

Activa el selector **Atribución de re-engagement** para comenzar a atribuir los re-engagements de X Ads.

<div id="re-engagement-click-through-lookback-window" />

#### Ventana de lookback por click-through de re-engagement

Define la duración de la **ventana de lookback por click-through de re-engagement** (el período de tiempo máximo después de hacer clic en un anuncio, dentro del cual un usuario reorientado puede atribuirse al anuncio). Puedes definir el valor en horas (hasta 23) o en días (1-30).

<Image align="center" alt="X-Ads-reengagement-activate.png" src="https://files.readme.io/318deeab0432870035a163a7b8a5b8c03be7d683bfc369104c8577674fde0036-36433422309905.png" />

<div id="re-engagement-view-through-lookback-window" />

#### Ventana de lookback por view-through de re-engagement

Para comenzar a atribuir impresiones de anuncios de retargeting, activa la **Atribución por view-through de re-engagement**.

Luego, define la duración de la **ventana de lookback por view-through de re-engagement** (el período de tiempo máximo después de que se visualiza un anuncio, dentro del cual un usuario reorientado puede atribuirse al anuncio). Puedes definir el valor en horas (hasta 23) o en días (1-7):

<Image align="center" alt="X-Ads-reengagement-view-through.png" src="https://files.readme.io/4faf93b6d8a8e45043eb9440d8f56a70eba2da51f3a572ea6cd698e072f033c6-36433415112849.png" />

<div id="re-engagement-window" />

#### Ventana de re-engagement

Define la duración de la **Ventana de re-engagement** (el período dentro del cual los eventos in-app del usuario se atribuyen a la fuente de medios de retargeting). Puede configurar el valor en días (1-90), horas (hasta 23) o incluso de por vida:

<Image align="center" alt="X-Ads-reengagement-window.png" src="https://files.readme.io/5bc42bd967929a88fd38f8bdd9cc36046a6f0381d1883ab1f26f5c680185a74c-36433415113105.png" width="628px" />

<div id="ignore-active-users-for-retargeting" />

#### Ignorar usuarios activos para el retargeting

Configura un periodo de inactividad para evitar registrar conversiones de retargeting en usuarios activos durante el periodo especificado. Saber más sobre el <Anchor target="_blank" href="/marketers/es/docs/set-retargeting-inactivity-window">Período de inactividad para retargeting</Anchor>.

<div id="in-app-event-postback-settings" />

### Configuración de postbacks de eventos in-app

En esta sección, puedes asignar tus eventos de AppsFlyer con tus partners a través de postbacks.

<Image align="center" alt="In-app_event_postbacks_es-us.png" src="https://files.readme.io/d89725172c53c309b5b58227ce53812e12f9cd4ee7611a6c375970b395122b15-36433415113361.png" />

**Para configurar postbacks de eventos in-app:**

1. Configura el **ID de partner** (si es necesario).
2. Habilita los **postbacks de eventos in-app.**
3. Haz clic en **Agregar evento** para agregar un evento de SDK o de servidor a servidor a la lista.
4. Completa los parámetros requeridos de acuerdo a la tabla a continuación.

| Parámetro | Descripción |
| --- | --- |
| **Evento de AppsFlyer** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea del SDK integrado en tu aplicación o de los eventos servidor a servidor.<br />**Consejo**: ¿No encuentras el evento que estás buscando?<ul><li>Asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar.</li><li>Escríbelo en **Evento de AppsFlyer**, y luego haz clic en **Crear personalizado**. Obtén más información sobre la <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#eventos-personalizados">asignación de eventos personalizados</Anchor>.</li></ul> |
| **Asignado al evento de partner** | El nombre o ID único de cada evento, tal como lo define el partner. Selecciona el evento predefinido más adecuado de AppsFlyer en el menú desplegable. |
| **para usuarios de** | Selecciona la opción de envío para el evento:<br /><br /><br /><br />**<span id="h_01HDJVBAEZATGM580CNC7BCVTN"></span>Nota:**<br />Para que X Ads reciba los postbacks atribuidos a la agencia, debes seleccionar **Todas las fuentes de medios, incluidas las orgánicas**. De lo contrario, X Ads no recibirá tales postbacks.<ul><li>**Solo este partner**: envía postbacks solo cuando este evento se atribuye a este partner.</li><li>**Todas las fuentes de medios, incluidas las orgánicas**: envían postbacks de eventos atribuidos a cualquier partner y eventos orgánicos.</li></ul> |
| **incluyendo** | <ul><li>**Sin datos (predeterminado)**: envía solo el evento en sí sin el valor del evento.</li><li>**Valores e ingresos**: envía todos los parámetros del evento, **incluido** el valor de ingresos (si existe en el evento).</li><li>**Valores sin ingresos**: envía todos los parámetros **excluyendo** el valor de ingresos.</li></ul> |

5. [Opcional] Haz clic en <Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" /> para establecer condiciones para enviar ciertos eventos in-app.  
   Saber más sobre <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#postbacks-condicionales-de-eventos-in-app">postbacks de eventos in-app condicionales</Anchor>.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlace de atribución">

X Ads no utiliza enlaces de atribución para la atribución.

<div id="note-2" />

> 📘 **Nota**
>
> Para todas las <Anchor target="_blank" href="/marketers/es/docs/self-reporting-networks-srns">redes de autorreporte (SRN)</Anchor>, como Meta Ads, Apple Search Ads, Google Ads, X Ads, etc., esta pestaña no es funcional ya que no utilizan enlaces de atribución externos.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costo">

La integración de costos proporciona los siguientes datos agregados:

* Datos de costos para tus campañas, conjuntos de anuncios, anuncios, canal y geo/países. Consulta la <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabla de integración de costos de ad networks</Anchor> para obtener más información sobre las dimensiones, métricas y funciones admitidas.  
  **Nota:** Los datos de costos requieren una suscripción a <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor> .
* Datos sobre clics, impresiones y datos enriquecidos (palabras clave, nombres de campañas y conjunto de anuncios).

**Para habilitar la API de costos**:

* Sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">estas instrucciones de integración</Anchor>.

<Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Visualiza el estado de tu API de costos</Anchor> y la última vez que AppsFlyer logró extraer los datos de costos coincidentes en el dashboard de estado de la integración de costos (e ingresos por publicidad) o en el dashboard de la ad network individual.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de ingresos publicitarios">

Los ingresos publicitarios no están disponibles para X-Ads.

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

<div id="x-ads-features" />

## Características de X-Ads

<div id="mobile-app-promotion-on-x-ads" />

<Accordion title="Promoción de aplicaciones móviles en X Ads">

La promoción de aplicaciones móviles en X Ads es un método para promocionar aplicaciones en X Ads. Permite que los anunciantes promocionen sus aplicaciones móviles mediante un diseño genial de tarjeta para las aplicaciones que impulse instalaciones, el engagement en la aplicación y los deep linking. Los usuarios pueden instalar con facilidad las aplicaciones e interactuar con ellas directamente desde su cronología de X Ads.

</Accordion>

<div id="webtoapp-measuring-app-activity-for-nonapp-campaigns-android-only" />

<Accordion title="Web-to-app: Medición de actividad de la aplicación para campañas que no son de aplicación (solo Android)">

La integración de AppsFlyer con X Ads permite medir la actividad de la aplicación—incluyendo instalaciones, re-engagements y eventos in-app—para **campañas que no son de aplicación** en Android.

Por ejemplo, incluso si el destino del anuncio es una **landing page web**, las instalaciones de la aplicación y otras actividades posteriores a la instalación aún se pueden medir, lo que permite medir el viaje del usuario de web-to-app (W2A).

Para medir la actividad de la aplicación de campañas que no son de aplicación de X y obtener insights valiosos sobre el comportamiento del usuario, sigue estos pasos en el administrador de X Ads:

1. Ve al formulario de creación de campañas en el administrador de X Ads.
2. En la sección **Entrega**, activa la medición de **Conversiones de la aplicación** para habilitar el seguimiento de instalaciones y conversiones in-app resultantes de la campaña. Consulta más detalles en la <Anchor target="_blank" href="https://business.x.com/en/help/campaign-setup/create-an-app-installs-campaign/mobile-app-measurement-and-attribution">documentación de X Ads</Anchor> (bajo *"Medición de conversiones de aplicaciones en objetivos no de aplicación"*).

<div id="important-1" />

> 🚧 **¡Importante!**
>
> Esta funcionalidad es actualmente **compatible solo en Android**.

</Accordion>

<div id="twitter-ads-and-appsflyer-skan-interoperation" />

<Accordion title="Interoperabilidad entre X Ads y AppsFlyer SKAN">

X Ads envía los datos de postbacks de SKAdNetwork a través de una API dedicada. Los datos SKAN de X Ads se mostrarán en el dashboard de <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">SKAN</Anchor>.

X Ads enriquece los postbacks de SKAN con los siguientes campos de datos:

* Nombre de la campaña
* ID de campaña
* Nombre del conjunto de anuncios
* ID del adset

</Accordion>

<div id="twitter-user-privacy" />

<Accordion title="Privacidad del usuario de X Ads">

Los anunciantes y usuarios de X Ads pueden controlar cómo comparten información con anunciantes y partners comerciales:

* A partir del **31 de julio de 2021**, los anunciantes que **no estén inscritos** en el programa de Medición Móvil Avanzada (AMM) de X Ads ya no recibirán datos a nivel de usuario de X Ads MACT. Como resultado, **todos los datos de X Ads estarán restringidos** en las herramientas de raw data de AppsFlyer. <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions#x-ads-formerly-twitter">Saber más sobre las restricciones de datos de X Ads.</Anchor>
* Si el anunciante está en el programa AMM y el usuario ha reconocido el aviso de privacidad, **no se aplicarán restricciones de raw data**.
* Independientemente del estado de AMM, si el usuario está en la UE y ha aceptado compartir datos con partners comerciales, **no se aplicarán restricciones de raw data**.
* Si el usuario está en la UE y **no** ha aceptado compartir datos con partners comerciales, **se aplicarán restricciones de raw data**.
* Los datos de atribución agregados se reflejan correctamente en AppsFlyer y no se ven afectados por la política de X Ads.

A través del programa AMM, los anunciantes pueden recibir datos de usuario a nivel más completos al otorgar a X Ads el derecho a realizar una auditoría. Esta auditoría asegura que los datos de X Ads se utilicen exclusivamente con fines de medición, de acuerdo con los estándares de la industria y las leyes de protección de datos.

<Anchor target="_blank" href="https://business.x.com/en/help/campaign-setup/create-an-app-installs-campaign/mobile-app-measurement-and-attribution">Saber más sobre el programa AMM en la sección de preguntas frecuentes</Anchor>. Para obtener orientación detallada, contacta a tu Gerente de Cuenta de X Ads.

</Accordion>

<div id="advanced-srn-parameter-names" />

## Nombres de parámetros SRN avanzados

Los siguientes campos en la integración SRN avanzada para X Ads **reemplazan** sus contrapartes heredadas en el dashboard de AppsFlyer, reportes agregados y raw data a nivel de evento.

| **AppsFlyer**  <br />**Columna de Datos** | **SRN antiguo** | SRN Avanzado |
| --- | --- | --- |
| **PID no integrados.** | Twitter | Twitter |
| **Nombre de la campaña** | Nombre de la campaña | Nombre de la campaña |
| **ID de campaña** | ID de campaña  <br />(base36: dashboard diferente de X, por ejemplo, 21I3V9) | ID de campaña  <br />(base10: igual que el dashboard de X, por ejemplo, 123456789) |
| **Nombre de conjunto de anuncios** | ID de artículo de línea  <br />(base36: dashboard diferente de X, por ejemplo, 21I3V9) | Nombre del artículo de línea |
| **ID del adset** | ID de artículo de línea  <br />(base36: dashboard diferente de X, por ejemplo, 21I3V9) | ID de artículo de línea  <br />(base10: igual que el dashboard de X, por ejemplo, 123456789) |
| **Nombre del anuncio** | ID del Tweet | Nombre del anuncio  <br />(si está disponible) |
| **ID del anuncio** | ID del Tweet | ID del Tweet |
| **Tipo de coincidencia** | srn | id\_matching / probabilistic |

<div id="traits-and-limitations" />

## Características y limitaciones

| Caducado | Nota |
| --- | --- |
| Atribución de pre-roll no soportada | X Ads no admite la atribución MMP para campañas de pre-roll. |
| Nombre del anuncio "Sin título" | El nombre del anuncio no es un campo obligatorio en el modelo de datos de anuncios de X (anteriormente Twitter), por lo que puede estar ausente. Cuando el nombre del anuncio no está definido en el Administrador de anuncios de X, AppsFlyer lo mostrará como **'Sin título.'** |
| Costo | Para X Ads, los datos de costo de las campañas exclusivas de SKAN (campañas que solo tienen instalaciones de SKAN y ninguna instalación "normal") no están disponibles para las agencias. La integración de costo debe ser configurada por el anunciante. Y solo el anunciante puede ver los datos. |

<div data-zendesk-anchors="overview=observaciones h_01JV7CGQNZNEM3P98K6KSYKB0D=observaciones xads-attribution-flow-in-appsflyer=flujo-de-atribuci%C3%B3n-de-x-ads-en-appsflyer h_01JZG83EKX39SF8355EW62C462=flujo-de-atribuci%C3%B3n-de-x-ads-en-appsflyer connecting-your-X-Ads-ads-account-to-appsflyer=conexi%C3%B3n-de-tu-cuenta-de-x-ads-a-appsflyer h_01HDJVCRYQESA17XZ83GS81YZ3=conexi%C3%B3n-de-tu-cuenta-de-x-ads-a-appsflyer h_01JV7D6AWYQ981HY6C130B021B=nota X-Ads-ads-attribution-setup=configuraci%C3%B3n-de-la-atribuci%C3%B3n-de-x-ads h_01HDJVBAEZ5W3JH1BN7WXJ08P6=configuraci%C3%B3n-de-la-atribuci%C3%B3n-de-x-ads h_01HDJVBAEZSFKRXAKQJP58N550=integration-tab ad-account-connected=cuenta-de-anuncios-conectada h_01HDJVBAEZD89BSGHQTPR84HSC=cuenta-de-anuncios-conectada xads_advanced_privacy_toggle=privacidad-avanzada advanced-privacy=privacidad-avanzada h_01JV7HVQJ2GTP74G6JYB300E71=nota-1 clickthrough-attribution=atribuci%C3%B3n-click-through h_01HDJVBAEZFJWQ6FD4Q4GSPD76=atribuci%C3%B3n-click-through viewthrough-attribution-lookback-window=ventana-de-lookback-de-atribuci%C3%B3n-view-through h_01HDJVBAEZ2H91WBHNSMRQYQ7H=ventana-de-lookback-de-atribuci%C3%B3n-view-through reinstall-settings=configuraci%C3%B3n-de-reinstalaci%C3%B3n h_01HDJVBAF0XRWRZJQSS4STH7YN=configuraci%C3%B3n-de-reinstalaci%C3%B3n reengagement-settings=configuraci%C3%B3n-de-re-engagement h_01HDJVBAEZZR1W06YH4XJSBKHV=configuraci%C3%B3n-de-re-engagement h_01JV9YQ7ZHRDD2NA5ENQXJQ31V=importante reengagement-clickthrough-lookback-window=ventana-de-lookback-por-click-through-de-re-engagement h_01HDJVBAEZ59ERYD2WQQYK6T37=ventana-de-lookback-por-click-through-de-re-engagement reengagement-viewthrough-lookback-window=ventana-de-lookback-por-view-through-de-re-engagement h_01HDJVBAEZSCK7430NJ8AMQYVY=ventana-de-lookback-por-view-through-de-re-engagement reengagement-window=ventana-de-re-engagement h_01HDJVBAEZCMWY5X47FEEFXTBX=ventana-de-re-engagement ignore-active-users=ignorar-usuarios-activos-para-el-retargeting h_01JVC3PWDR9KHEFBQF5NWHCQJN=ignorar-usuarios-activos-para-el-retargeting inapp-event-postback-settings=configuraci%C3%B3n-de-postbacks-de-eventos-in-app h_01HDJVBAEZ5ZM9RDXPWTJPPYVA=configuraci%C3%B3n-de-postbacks-de-eventos-in-app h_01HDJVBAEZR1Q2SVE9MEQ9EXKP=attribution-link-tab h_01HDJVBAEZ7R7BKFAZYXXBGS5Y=nota-2 h_01HDJVBAEZYSWN59VNXTDEWX93=cost-tab 01H88VAJH3A2Q0CZXQQZMW6YRC=ad-revenue-tab h_01HDJVBAF0KEVSWJ0EW54AEAWV=permissions-tab ad-network-permissions=permisos-de-ad-network h_01HDJVBAF0BMSCKF6J9NJ019YJ=permisos-de-ad-network agency-permissions=permisos-de-la-agencia h_01HDJVBAF0W3ZE7J93CRE8EBRP=permisos-de-la-agencia x-ad-features=caracter%C3%ADsticas-de-x-ads h_01JZWQA6DXRZ17SRVT4HM2MQSH=caracter%C3%ADsticas-de-x-ads h_01JZWQA6DX3BRNG8B5CJGA57AM=mobile-app-promotion-on-x-ads h_01JZWQA6DX7W9102P5S6KWJ1WB=webtoapp-measuring-app-activity-for-nonapp-campaigns-android-only h_01JZWQA6DX8AX5XG3W4A6XB53S=importante-1 h_01H9QR6TH74PKBGM5RC4M118GE=twitter-ads-and-appsflyer-skan-interoperation h_01H9QR6TH74R50K00H7FYN61KC=twitter-user-privacy x-ads-data-differences=nombres-de-par%C3%A1metros-srn-avanzados advanced-srn-parameter-names=nombres-de-par%C3%A1metros-srn-avanzados traits-and-limitations=caracter%C3%ADsticas-y-limitaciones h_01JYGPBHHNQARG3GRMQJA95JKD=caracter%C3%ADsticas-y-limitaciones" />
