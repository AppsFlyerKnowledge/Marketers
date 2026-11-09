---
title: Resolución de problemas de postbacks para anunciantes
metadata:
  keywords:
    - Postback
    - Partner
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2023-04-04T07:09:26Z'
  edited_at: '2026-09-17T00:27:52Z'
  id: 14272573202833
  locale: es
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/es/articles/14272573202833
---
> **De un vistazo:** Encuentra las principales causas y soluciones de por qué tu partner no recibe los postbacks esperados. Repasa cada uno de los temas a continuación y ve si pueden ser la causa.

<div id="check-the-integration-toggles" />

## Comprueba los selectores de integración

Varios selectores controlan diferentes partes de la integración. El estado del selector podría ser la razón por la que no se reciben los postbacks.

<div id="the-activate-partner-toggle-was-turned-off" />

<Accordion title="Activar partner está desactivado">

Cuando el selector <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">**Activar partner**</Anchor> está desactivado, las conversiones no se atribuyen y los postbacks no se envían a los partners.

<Image align="center" alt="integration_turned_off.png" src="https://files.readme.io/d43b4f465749e343d9523e90e87e43b77a85cdd920f0c0770a94bcb7a585d920-14979273403793.png" />

**Para activar la integración:**

1. En AppsFlyer, desde el menú lateral, selecciona **Colaborar** > **c**
2. Haz clic en el icono Gestionar la integración del partner.
3. En la pestaña **Integración**, activa el selector **Activar partner**.

Otro caso puede ser si el selector <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">**Activar partner**</Anchor> está actualmente activado pero durante el tiempo del evento, se desactivó. Utiliza el registro de auditoría para verificar y ver si la integración de partners estaba activa en el momento del evento:

* <span id="1703758710.321359"></span>Ve a tu correo electrónico de usuario (arriba a la derecha) > **Centro de seguridad** > **Registro de auditoría**.

</Accordion>

<div id="1703760110.503549" />

<div id="the-inapp-event-postbacks-toggle-was-turned-off" />

<Accordion title="Los postbacks de eventos in-app están desactivados">

El selector de **<Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration">Postbacks de eventos in-app</Anchor>** está desactivado o puede haberse desactivado durante el tiempo del evento. Esto significa que no se envían postbacks.

**Para activar los postbacks de eventos in-app:**

1. En AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Integraciones de partners** > **Integraciones activas.**
2. Haz clic en el icono Gestionar la integración del partner.
3. Desde la pestaña **Integración**, desplázate hacia abajo hasta el selector de **postbacks de eventos in-app** y actívalo.

   <Image align="center" alt="integration-in_app_event_postbacks_toggle.png" src="https://files.readme.io/20dadaa71b8b54c4512e74a925e66cec9da5e8138bb28a545c5452eef2d38304-14627453566737.png" />

</Accordion>

<div id="check-the-event-configuration" />

## Comprobar la configuración del evento

El evento podría estar configurado de manera que no se envíen ciertos postbacks.

<div id="the-event-wasnt-configured" />

<Accordion title="El evento no está configurado">

Verifica que el evento esté incluido en la lista de eventos in-app que se configuraron. Si no está definido, no se envía un postback.

<Image align="center" alt="list_of_in_app_events.png" src="https://files.readme.io/c2b3a3a87c4a1f39a3fa3acc28c736fd69d8d6d21d4b9ed5d3c84e8df0d3bf39-14979245450641.png" />

1. En AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Integraciones de partners** > **Integraciones activas.**
2. Haz clic en el icono Gestionar la integración del partner.
3. Desde la pestaña **Integración**, desplázate hacia abajo hasta **Postbacks de eventos in-app** y ve si aparece el nombre del evento.

</Accordion>

<div id="the-event-was-configured-incorrectly" />

<Accordion title="El evento está configurado incorrectamente">

Los postbacks se envían de acuerdo con la configuración de la <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#ventana-de-postback-de-eventos-in-app">ventana de postback</Anchor>. Los postbacks para eventos posteriores a este período no se envían al partner, aunque los eventos aún se registran en AppsFlyer.

<Image align="center" alt="in_app_event_postback_mapping_2.png" src="https://files.readme.io/b0b4935f2b40e1c81961fbbecd159ca054816be2c58248624eed177ec17f9c20-14979366291857.png" />

</Accordion>

<div id="the-event-was-configured-correctly-but-with-a-condition" />

<Accordion title="El evento está configurado correctamente pero con una condición">

Si se define una condición para el evento, el postback se envía de acuerdo con la condición. Comprueba si hay alguna condición que limite el envío de postbacks.

<Image align="center" alt="in_app_event_condition__1_.png" src="https://files.readme.io/0f179d79fdb544f209f901370f7c0103e0fc5dbeda2554268b2a06a272a6b8b9-14979535388433.png" />

</Accordion>

<div id="the-event-was-configured-to-send-postbacks-only-to-the-attributed-partner" />

<Accordion title="El evento está configurado para enviar postbacks solo al partner atribuido">

Verifica si la configuración del evento in-app está establecida para enviar postbacks a <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#opciones-para-enviar-postbacks">**Solo este partner** o a **Todas las fuentes de medios, incluidas las orgánicas**</Anchor>. Si está establecido en **Solo este partner**, solo el partner atribuido recibe el postback.

<Image align="center" alt="in_app_event_sending_options.png" src="https://files.readme.io/3fd96860a0a8842dd183a29e9f9dd947b5c9082e2069c0aa74bd8eb781302908-14979359951761.png" />

</Accordion>

<div id="the-event-occurred-outside-of-the-configuration-window" />

<Accordion title="El evento ocurrió fuera de la ventana de configuración">

Verifica que la <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#mapeo-de-eventos">asignación del evento</Anchor> sea correcta. Los postbacks para eventos posteriores a este período no se envían al partner, aunque los eventos aún se registran en AppsFlyer.

<Image align="center" alt="in_app_event_postback_window.png" src="https://files.readme.io/21cae7825d557c1ee89c890ec64c922cb36e31be882850a26bfdc4e5595773f0-14661845664401.png" />

Ten en cuenta que, para las <Anchor target="_blank" href="/marketers/es/docs/self-reporting-networks-srns">SRN,</Anchor> los postbacks de eventos in-app se envían durante el <Anchor target="_blank" href="/marketers/es/docs/user-level-data-retention#periodos-de-conservación-de-los-datos-de-partners">período de retención de datos del partner</Anchor>.

</Accordion>

<div id="privacy-restrictions" />

## Restricciones de privacidad

En los siguientes casos, AppsFlyer no envía postbacks debido a las restricciones de privacidad.

<div id="the-partner-didnt-set-up-advanced-privacy" />

<Accordion title="El partner no admite la Privacidad avanzada o no la configuró">

Si la <Anchor target="_blank" href="/marketers/es/docs/apply-aggregated-advanced-privacy-framework#partner-advanced-privacy-switch">Privacidad avanzada</Anchor> está activada, pero el partner no configuró la Privacidad avanzada para sí mismo o no la admite, no recibirá los <Anchor target="_blank" href="/partners/es/docs/advanced-privacy-guide-postback-macros-for-ad-networks#tipos-de-plantillas-para-enviar-postbacks">postbacks agregados de Privacidad avanzada</Anchor>.

<Image align="center" alt="partner_not_supporting_ap_postbacks.png" src="https://files.readme.io/1d8784e8994eba5c403ac706673490b91b7b34ed4d5dbea8c3fe58f227d382c5-15140294126353.png" />

</Accordion>

<div id="media-source-restrictions-on-thirdparty-platforms" />

<Accordion title="Restricciones de fuentes de medios en plataformas de terceros">

<Anchor target="_blank" href="/marketers/es/docs/discrepancies-between-appsflyer-and-third-party-platforms#restricciones-de-postbacks-en-plataformas-de-terceros">Algunas fuentes de medios</Anchor> restringen el intercambio de datos con terceros. AppsFlyer no permite que se compartan los datos de nivel de usuario adquiridos a través de estas fuentes de medios con ninguna plataforma o servicio de terceros. Por lo tanto, todas las instalaciones de dichas fuentes de medios se envían como orgánicas. Ten en cuenta que Anuncios de Meta no comparte ningún dato con plataformas de terceros.

</Accordion>

<div id="the-sdk-was-set-not-to-share-information-with-the-partner" />

<Accordion title="El SDK se configuró para no compartir información con el partner">

Se implementó un filtro de uso compartido en el SDK para evitar que el partner reciba información. Este filtro puede activarse mediante una solicitud explícita de exclusión opcional de un usuario o en cualquier otro momento durante el ciclo de vida de la aplicación.

Para obtener más información, consulta: <Anchor target="_blank" href="/marketers/es/docs/apply-privacy-preserving-sdk-methods#evita-el-uso-compartido-de-datos-con-las-redes">Evitar el intercambio de datos con terceros</Anchor> y <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setsharingfilterforpartners">setSharingFilterForPartners</Anchor>.

</Accordion>

<div id="miscellaneous" />

## Misceláneos

<div id="the-postback-was-sent-but-doesnt-show-on-the-partners-platform" />

<Accordion title="El postback se envió pero no se muestra en la plataforma del partner">

En algunos casos, aunque AppsFlyer envía los postbacks a un partner, estos no se muestran del lado del partner. Es este tipo de casos, ponte en contacto con el partner.

**Para ver si el postback se envió desde AppsFlyer:**

1. En AppsFlyer, en **Reportes** ve a **Exportación de raw data**.
2. Consulta el reporte relevante en **Postbacks** (Instalaciones, Eventos in-app, Conversiones de retargeting, Retargeting de eventos in-app).

<Image align="center" alt="postback_reports.JPG" src="https://files.readme.io/21f7ead0f04cf8b67735476348245c5849b638701946236cf649adfa69699df6-14981466637457.png" />

</Accordion>

<div id="the-event-didnt-occur" />

<Accordion title="El evento no ocurrió o no se envió a AppsFlyer">

Todos los eventos que ocurrieron se pueden encontrar en el <Anchor target="_blank" href="/marketers/es/docs/activity-dashboard">panel de control de **Actividad**</Anchor> y en los <Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-overview?query=raw%20data%20reports">reportes de raw data</Anchor>. Si un evento no se muestra allí, significa que no ocurrió o no se envió a AppsFlyer.

Podría ser que el evento no estuviera definido en el SDK. En este caso, no lo verás en la plataforma. Comprueba la configuración del SDK.  <Anchor target="_blank" href="/marketers/es/docs/basic-sdk-integration-guide#registro-de-eventos-in-app">definido en el SDK</Anchor>.

Si crees que ocurrió el evento, consulta a continuación cómo ver si aparece en el panel de control de Actividad o crea un reporte de raw data y búscalo ahí.

**Para ver el panel de control de Actividad:**

* En AppsFlyer, en **Paneles de control** ve a **Actividad** y selecciona al partner y el rango de fechas.

**Para crear un reporte de raw data:**

1. En AppsFlyer, en **Reportes** ve a **Exportación de raw data**.
2. Haz clic en **Crear reporte**.
3. Selecciona el reporte correspondiente.
4. Selecciona el rango de fechas y cualquiera de los campos necesarios y haz clic en **Crear**.
5. Descarga el reporte y busca el evento allí.

</Accordion>

<div id="differences-in-time-zones" />

<Accordion title="Diferencias de zona horaria">

Puede haber discrepancias en la recepción de postbacks debido a una diferencia de zona horaria entre la plataforma AppsFlyer y la plataforma del partner. Los paneles de control y reportes de AppsFlyer se muestran de acuerdo con la zona horaria seleccionada.

**Para ver la zona horaria de la aplicación en AppsFlyer:**

1. En AppsFlyer, en **Configuración** ve a **Configuración de la aplicación**.
2. Consulta la zona horaria de la aplicación en **Localización**.

</Accordion>

<div id="srns-missing-advertising-ids-idfagaid" />

<Accordion title="A las SRN les faltan los ID de publicidad (IDFA/GAID)">

Hay una serie de <Anchor target="_blank" href="/marketers/es/docs/self-reporting-networks-srns#does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid">casos específicos para las SRN</Anchor> en los que AppsFlyer no envía postbacks para las instalaciones, los inicios de aplicaciones o los eventos in-app.

</Accordion>

<div id="media-source-restrictions-on-thirdparty-platforms::40092c14" />

<Accordion title="Restricciones de fuentes de medios en plataformas de terceros">

<Anchor target="_blank" href="/marketers/es/docs/discrepancies-between-appsflyer-and-third-party-platforms#restricciones-de-postbacks-en-plataformas-de-terceros">Algunas fuentes de medios</Anchor> restringen el intercambio de datos con terceros. AppsFlyer no permite que se compartan los datos de nivel de usuario adquiridos a través de estas fuentes de medios con ninguna plataforma o servicio de terceros. Por lo tanto, todas las instalaciones de dichas fuentes de medios se envían como orgánicas. Ten en cuenta que Anuncios de Meta no comparte ningún dato con plataformas de terceros.

</Accordion>

<div id="advanced-privacy-postbacks" />

<Accordion title="Postbacks de privacidad avanzada">

Cuando la privacidad avanzada (AP) está activada, los datos a nivel de usuario de los usuarios que no dan su consentimiento y ejecutan iOS 14.5+ no están disponibles a través de postbacks. Los postbacks se envían de acuerdo con la <Anchor target="_blank" href="/partners/es/docs/advanced-privacy-guide-postback-macros-for-ad-networks#tipos-de-plantillas-para-enviar-postbacks">plantilla de Privacidad avanzada</Anchor>.

</Accordion>

<div id="see-also" />

> 📄 **Consulta también**
>
> <Anchor target="_blank" href="/partners/es/docs/postback-troubleshooting-for-ad-networks">Resolución de problemas con los postbacks para redes de publicidad</Anchor>

<div data-zendesk-anchors="activation-toggles=comprueba-los-selectores-de-integraci%C3%B3n h_01H9FT385FY1QJC6M2YVMZF2NC=comprueba-los-selectores-de-integraci%C3%B3n h_01H9FT385FJ0W62NB6FBB6ASKP=the-activate-partner-toggle-was-turned-off h_01H9FT385FKK7VQ293HH9RANBP=the-inapp-event-postbacks-toggle-was-turned-off event-configuration-issues=comprobar-la-configuraci%C3%B3n-del-evento h_01H9FT385FW71JV2KKZ22TP6TN=comprobar-la-configuraci%C3%B3n-del-evento h_01H9FT385FHFX4PNRQVRXX8A5X=the-event-wasnt-configured h_01H9FT385FE4GCP9D5XCNZ1FAR=the-event-was-configured-incorrectly h_01H9FT385FTT97PJ9NN09K0X9F=the-event-was-configured-correctly-but-with-a-condition h_01H9FT385FDEC21CAZ7V9BBT7M=the-event-was-configured-to-send-postbacks-only-to-the-attributed-partner h_01H9FT385G8HSVJWWGKSRKT381=the-event-occurred-outside-of-the-configuration-window privacy-restrictions=restricciones-de-privacidad h_01H9FT385G84E2A1J64VWG8H4Z=restricciones-de-privacidad h_01H9FT385G3ECF0PXCE6S2GD5A=the-partner-didnt-set-up-advanced-privacy h_01H9FT385G9YMX9BAEYY0XQR4C=media-source-restrictions-on-thirdparty-platforms h_01HG0YAHWJ565C7BAXAXT75ACB=the-sdk-was-set-not-to-share-information-with-the-partner miscellaneous=miscel%C3%A1neos h_01H9FT385GSWRPKEHKJ4HXCX01=miscel%C3%A1neos h_01H9FT385GTSH1K93WNCARY2BA=the-postback-was-sent-but-doesnt-show-on-the-partners-platform h_01H9FT385G5HK6N2JEE8C6S245=the-event-didnt-occur h_01H9FT385GPVT9WAC6ZTPK6D10=differences-in-time-zones h_01H9FT385G8RXJD25KAQJ28TF6=srns-missing-advertising-ids-idfagaid h_01H9FT385GAYCY615W7M88XJT3=media-source-restrictions-on-thirdparty-platforms::40092c14 h_01JK86ZFXJGPVYJCAAVAY6F4YD=advanced-privacy-postbacks h_01HE7R6G699RG30ZSSQF02AK5Y=consulta-tambi%C3%A9n" />
