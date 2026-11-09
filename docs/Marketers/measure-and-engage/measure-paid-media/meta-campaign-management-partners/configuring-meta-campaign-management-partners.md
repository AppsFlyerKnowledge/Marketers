---
title: Configuración de partners de administración de campañas de Meta
metadata:
  keywords:
    - Facebook
    - FMP
    - Advertisers
    - Partners
    - facebook marketing partner
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2018-03-18T12:43:51Z'
  edited_at: '2026-08-12T12:20:34Z'
  id: 360000562569
  locale: es
  section: Meta campaign management partners
  section_id: 6551188365457
  url: https://support.appsflyer.com/hc/es/articles/360000562569
---
> **En resumen:** Optimiza las campañas de Anuncios de Meta utilizando partners de administración de campañas de Meta (antes conocidos como partners de marketing de Facebook), como Kenshoo, Bidalgo y Smartly. Una vez configurados, AppsFlyer les envía los postbacks.

<div id="configure-meta-campaign-management-partners" />

## Configurar partners de administración de campañas de Meta

**Requisito previo:** Antes de configurar la integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con él. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Para activar o editar la integración:**

1. **Para activarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Partner Marketplace**.  
   **Para editarla**: en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Integraciones activas**.
2. Selecciona la aplicación correspondiente.
3. Busca al partner (`rokuads_int`) y selecciónalo.
4. En la pestaña de **Integración**, selecciona la aplicación para la integración y activa **Activar partner** .  
    **Nota:** El selector debe estar <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activado</Anchor> mientras trabajes con el partner. Aprende más sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activación de partners</Anchor>.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación.

<div id="in-app-event-postback-setup" />

## Configuración de postbacks de eventos in-app

**Requisito previo**:

Para que el partner obtenga postbacks, los nombres de las campañas **deben** tener como prefijo el nombre del partner de administración de campañas de Meta. Por ejemplo, si el nombre del partner de administración de campañas de Meta es *Mcmpexample* y el segmento es *Young\_Segment,* configura el nombre de la campaña como *mcmpexample\_Young\_Segment*.  
**Nota:** El nombre del partner de administración de campañas de Meta **distingue entre mayúsculas y minúsculas.**

**Para configurar postbacks de eventos in-app**:

<Image align="center" alt="in-app_event_mapping.png" src="https://files.readme.io/ced254c1aa0ad454c1876cfc0bc85de20d275824efb34c9665ca144dabffaa2a-14050539243793.png" />

1. Activa **Postbacks de eventos in-app**.
2. Completa los parámetros requeridos según el <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#métodos-de-mapeo">método de asignación</Anchor>:

   

| Nombre de parámetro | Descripción |
| --- | --- |
| <span id="appsflyer-event"></span>**Evento de AppsFlyer** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea del SDK integrado en tu aplicación o de los eventos de servidor a servidor.<br />**Consejo**: ¿No ves el evento que estás buscando?<ul><li>Asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar.</li><li>Escríbelo en **Evento de AppsFlyer**, y luego haz clic en **Crear personalizado**. Lee más sobre la <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#eventos-personalizados">asignación de eventos personalizados</Anchor>.</li></ul> |
| <span id="mapped-to-partner-event"></span>**Asignado al evento de partner** | El ID o nombre único de cada evento, tal y como lo defina el partner. Existen <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#métodos-de-mapeo">varias configuraciones de asignación</Anchor>:<ul><li>**Campo de texto:** obtén el ID del evento correspondiente del partner.</li><li>**Cuadro desplegable:** selecciona el evento de partner predefinido más adecuado.</li><li>**Como está**: envía los eventos tal como están, sin asignar el nombre del evento.</li></ul> |
| <span id="for-users-from"></span>**Para usuarios de** | Selecciona la opción de envío para el evento:<ul><li>**Solo este partner**: envía postbacks solo cuando el evento se atribuya a este partner, es decir, el usuario que lo realizó provino de este partner.</li><li>**Todas las fuentes de medios, incluidas las orgánicas**: envía postbacks de eventos atribuidos a cualquier partner y de eventos orgánicos, es decir, el usuario que los realizó provino de cualquier fuente de medios.</li></ul> |
| <span id="including"></span>**Incluyendo** | Selecciona <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#datos-a-incluir-en-los-postbacks">qué datos del evento</Anchor> compartir con el partner en el postback:<ul><li>**Sin valores y sin ingresos**: envía solo el evento en sí sin ningún parámetro (valores o ingresos).</li><li>**Valores y sin ingresos**: envía todos los parámetros **excluyendo** el valor de los ingresos.</li><li>**Valores e ingresos**: envía todos los parámetros del evento, **incluido** el valor de los ingresos (si existe en el evento).</li></ul> |

3. [Opcional] Haz clic en ![conditional-iae-postbacks-icon.png](https://files.readme.io/5345c5ebe95b3f1a0d0858b88ce29f9965178ce750df86c04cb131a93d006a5e-14050481317393.png) para <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#postbacks-condicionales-de-eventos-in-app">establecer condiciones</Anchor> para enviar ciertos eventos in-app al partner.
4. [Opcional] Haz clic en **Agregar evento** para agregar otro SDK o evento de servidor a servidor a la lista.
5. Haz clic en **Guardar integración**.

<div id="important-notes" />

> 📘 **Notas importantes**
>
> * Deshabilitar la atribución de Anuncios de Meta impide el envío de postbacks a los partners de administración de campañas de Meta.
> * La asignación de eventos in-app con los partners de administración de campañas de Meta, o la falta de ella, no afecta el envío de eventos in-app a Anuncios de Meta directamente desde la cuenta del anunciante.
> * La asignación de eventos in-app puede requerir diferentes parámetros de configuración según el partner de administración de campañas de Meta.
> * Los nombres de las campañas de Anuncios de Meta y X Ads deben comenzar con el nombre de la cuenta del partner de administración de campañas de Meta, tal como se define en la plataforma AppsFlyer, seguido de un guión bajo "\_". Cuando las campañas no tienen el nombre mencionado, son visibles para el anunciante pero no para el partner de administración de campañas de Meta. El nombre del partner de administración de campañas de Meta **distingue entre mayúsculas y minúsculas**.

<div data-zendesk-anchors="configuring-facebook-marketing-partners=configurar-partners-de-administraci%C3%B3n-de-campa%C3%B1as-de-meta h_01HGFQCBT217ZV0R6E2YHTV88N=configurar-partners-de-administraci%C3%B3n-de-campa%C3%B1as-de-meta inapp-event-postback-setup=configuraci%C3%B3n-de-postbacks-de-eventos-in-app h_01HGFQCBT3R7HH8M5SQJK1EPSP=configuraci%C3%B3n-de-postbacks-de-eventos-in-app h_01HGFQCBT3HGZVFHCC1S04MVQW=notas-importantes" />
