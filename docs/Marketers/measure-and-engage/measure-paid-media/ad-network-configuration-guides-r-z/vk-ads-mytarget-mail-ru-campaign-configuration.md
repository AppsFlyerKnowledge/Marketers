---
title: Configuración de campaña de VK Ads (myTarget, Mail.ru)
metadata:
  keywords:
    - mytarget
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-03-28T11:53:13Z'
  edited_at: '2026-09-11T00:25:16Z'
  id: 209731913
  locale: es
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/es/articles/209731913
---
> **Información general:** VK Ads es una plataforma de publicidad móvil orientada a conectar a los anunciantes con usuarios móviles rusohablantes. Con VK Ads, los anunciantes pueden colocar publicidad segmentada en redes sociales (Vkontakte, Odnoklassniki, Moi Mir) y en Mail.Ru Group. Además de la atribución móvil basada en clics, VK Ads también ofrece atribución de retargeting.

![](https://cdn.appsflyer.com/marketplace/static/logo/mail.ru.png?v=1)

## Configuración de VK Ads

**Requisito previo:** Una cuenta con el partner. Si no tienes una cuenta, contacta con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de Partners > Marketplace**.  
   (**Para editar una integración existente:** Ve a la pestaña **Colaborar > Integraciones de Partners > Integraciones activas**.)
2. Selecciona la aplicación correspondiente.
3. Busca el partner y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el selector **Activar partner**.   
   **Nota:** El selector **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de partners.</Anchor>

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

### Activar los partners

En la **primera visita** aquí, tendrás que activar el botón ***Activar Partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

### Configuración general

Los siguientes ajustes generales están disponibles para VK Ads.

### Identificación de la aplicación

Este campo no es obligatorio y su funcionalidad está por determinar. Si tienes alguna otra pregunta, ponte en contacto con VK Ads.

### Habilitar la atribución view-through

Actívalo si deseas atribuir las instalaciones por impresiones de VK Ads. El control deslizante de la ventana retrospectiva por impresiones está disponible en la pestaña del enlace de [***atribución***](/docs/vk-ads-mytarget-mail-ru-campaign-configuration#attribution-link-tab) (se describe a continuación).

### Postbacks predeterminados

Envía postbacks automáticos a VK Ads tras las instalaciones y los re-engagements de los usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

Selecciona **Solo eventos atribuidos a este partner** para eventos provenientes solo de usuarios atribuidos a VK Ads.  
Selecciona **Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada a VK Ads.

### Postbacks de eventos in-app

En esta sección, puedes configurar los postbacks de eventos in-app que se envían a VK Ads.

1. Activar ***Postbacks de eventos in-app***
2. Elige si quieres reportar al partner **eventos seleccionados** o **todos**.
   * Nota: Si eliges reportar todos los eventos, el evento *af\_app\_opened* no se reporta.
3. Si eliges seleccionar eventos manualmente, haz clic en ***Agregar evento*** para añadir un evento de SDK a la lista.
4. Completa los siguientes parámetros:

| Nombre del parámetro | Nota |
| --- | --- |
| **Nombre del evento de SDK** *(obligatorio solo para la selección manual)* | El nombre del evento, tal como lo recibió AppsFlyer, ya sea desde el SDK o desde eventos de servidor a servidor.  <br />**Consejo**: si no ves el evento que quieres en la lista, actívalo en un dispositivo con una instalación no orgánica y vuelve a comprobarlo. |
| **Opción de envío** | Selecciona la opción de envío del evento:  <br />**Solo este partner** para eventos que provienen **solo** de usuarios atribuidos a VK Ads.  <br />**Todas las fuentes, incluidas las orgánicas** para que toda tu base de usuarios esté disponible para ser reportada al partner |
| **Enviar datos de eventos** | <ul><li>**Sin valores ni ingresos:** envía solo el evento en sí sin el valor del evento.</li><li>**Con valores y sin ingresos:** envía todos los parámetros, excepto el valor de ingresos.</li><li>**Con valores e ingresos**: envía todos los parámetros del evento, incluido el valor de ingresos (si existe en el evento).</li></ul> |

5. Haz clic en ***Guardar***.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Genera y guarda enlaces de atribución y envíalos al partner para que te atribuya campañas específicas, conjuntos de anuncios o anuncios únicos, tanto para campañas de UA como de retargeting. Puedes usar un enlace de una sola plataforma o un <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">Aprender más sobre la estructura y los parámetros de los enlaces de atribución</Anchor>.

**Para generar un enlace de atribución,** sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#attribution-link-tab">estas instrucciones</Anchor>.

**Nota**: VK Ads no ofrece soporte para OneLinks. Usa enlaces de atribución estándar para retargeting.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

AppsFlyer obtiene los detalles de costos por API. Consulta la <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabla de integración de costos de ad network</Anchor> para obtener información completa sobre las dimensiones, métricas y funciones compatibles. **Nota**: Los datos de costos requieren una suscripción a ROI360.

**Para habilitar la API de costos**:

* Sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">estas instrucciones de integración</Anchor>.

<div id="cost-data-sync-status" />

<Accordion title="Estado de sincronismo de datos de costos">

<Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Visualiza el estado de tu API de costos</Anchor> y la última vez que AppsFlyer logró extraer los datos de costos coincidentes en el dashboard de estado de la integración de costos (e ingresos por anuncios) o en el dashboard de la ad network individual.

</Accordion>

<div id="removing-connected-accounts" />

<Accordion title="Eliminar cuentas conectadas">

**Para eliminar una cuenta conectada:**

* <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#deleting-connected-accounts-in-the-cost-tab">En la columna «Acciones», desplaza el cursor sobre una cuenta, haz clic en ***Eliminar conexión***</Anchor>

</Accordion>

> 📘 **Notas**
>
> 1. Para dar soporte al costo con VK Ads, el anunciante debe añadir el ID de la campaña al enlace **af\_c\_id=**.
> 2. Una vez que hayas establecido el costo de VK Ads, no cambies el nombre de ninguna campaña, recurso o anuncio único activo, ni utilices macros dinámicas con el parámetro del nombre de la campaña, ya que pueden provocar discrepancias importantes o la falta de datos de costo.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Los datos de ingresos por publicidad no son compatibles con VK Ads.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres otorgarle a VK Ads, tanto si el partner actúa como ad network, agencia o incluso ambas. Ten en cuenta que, incluso si la atribución estuviera deshabilitada para VK Ads, la pestaña de permisos está activa y puedes otorgarle el control a VK Ads.

Usa estos selectores para otorgarle permisos a una ad network para que maneje su propia configuración de tu aplicación:

* ***Permitir la configuración de la integración***: permite que el partner configure la pestaña de integración (excepto postbacks de eventos in-app).
* ***Permitir la configuración de postbacks de eventos in-app***: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña de integración.
* ***Permitir el acceso a tu reporte de retención***: solo para los propios datos de retención del partner.
* ***Permitir acceso a tus datos agregados de usuarios fieles***: solo a los datos de usuarios fieles propios del partner.
* ***Permitir acceso a tus datos agregados de eventos in-app**:* solo a los datos de eventos in-app propios del partner.
* ***Permitir acceso a tus datos agregados de ingresos*a** - solo a los datos de ingresos atribuidos al partner
* ***Permitir el acceso a tu panel de control Protect360***: solo a los datos de Protect360 propios del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-vk-ads=configuraci%C3%B3n-de-vk-ads h_01HJZV9DR3A3W91BQCE2548M0P=configuraci%C3%B3n-de-vk-ads h_01HJZV9DR31B2EW88NG57XV2WH=integration-tab activate-partners=activar-los-partners h_01HJZV9DR4A51AC03J82BMH8R0=activar-los-partners general-settings=configuraci%C3%B3n-general h_01HJZV9DR4WXN4985B5YYHN065=configuraci%C3%B3n-general app-id=identificaci%C3%B3n-de-la-aplicaci%C3%B3n h_01HJZV9DR4RDFCE9FF8P61H5G7=identificaci%C3%B3n-de-la-aplicaci%C3%B3n enable-viewthrough-attribution=habilitar-la-atribuci%C3%B3n-view-through h_01HJZV9DR4EFADPVTYYRT4ZYZD=habilitar-la-atribuci%C3%B3n-view-through default-postbacks=postbacks-predeterminados h_01HJZV9DR408AXGRVRBV6KK9CJ=postbacks-predeterminados inapp-events-postbacks=postbacks-de-eventos-in-app h_01HJZV9DR43RZ5W4B71SASKY42=postbacks-de-eventos-in-app h_01HJZV9DR47N1SFC26DHT4BCCE=attribution-link-tab h_01HJZV9DR4G92S9CZZW3JE5HTS=cost-tab h_01HJZV9DR47Q48ZTJVK1M5DDM8=cost-data-sync-status h_01HJZV9DR5SHYA20GE711S6VT5=removing-connected-accounts h_01HJZV9DR5Q8W34HW2GRWCCMEB=notas h_01HJZV9DR5696R8NE7R5YYZ2JB=ad-revenue-tab h_01HJZV9DR5YQH7HF32M8R1YBKZ=permissions-tab" />
