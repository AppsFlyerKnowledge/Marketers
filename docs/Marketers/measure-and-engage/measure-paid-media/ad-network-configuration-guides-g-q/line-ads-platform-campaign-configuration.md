---
title: Configuración de campaña de LINE Ads Platform
metadata:
  keywords:
    - Advertisers
    - LINE Ads
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-08-10T15:26:17Z'
  edited_at: '2026-09-11T00:24:06Z'
  id: 213050543
  locale: es
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/es/articles/213050543
---
> **En resumen:** LINE Ads Platform, un partner integrado de AppsFlyer, combina un sistema de ofertas y orientación personalizado. Además de la atribución móvil basada en clics, LINE Ads Platform también ofrece atribución de retargeting, que puedes registrar con AppsFlyer.

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/lap.png" width="71px" />

<div id="setting-up-line-ads-platform" />

## Configurando LINE Ads platform

**Requisito previo:** Una cuenta con el Partners. Si no tienes una cuenta, contacta con el Partners para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Collaborate > Partner Integrations > Marketplace** .  
   (**Para editar una integración existente:** Ve a la pestaña **Collaborate > Partner Integrations > Active integrations** .)
2. Selecciona la aplicación correspondiente.
3. Busca el Partners y selecciona **Integrate**.
4. En la pestaña **Integración**, activa el interruptor **Activate partner**.   
   **Nota:** El interruptor **debe permanecer activado (activo) mientras trabajes con el Partners**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de Partners.</Anchor>

<div id="integration-tab" />

<Accordion title="Pestaña de integración">

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

<div id="note" />

> 📘 **Nota**
>
> Como red de TODAS las instalaciones, LINE prefiere recibir postbacks de todas las nuevas instalaciones de tu aplicación desde CUALQUIER fuente, incluida la orgánica. Para hacerlo, selecciona **Eventos atribuidos a cualquier partner** para enviar todos los postbacks de instalación a LINE. Esto sólo lo puede realizar el propietario de la cuenta.

<div id="activate-partner" />

### Activar partner

En la **primera visita** aquí, deberás alternar a continuación. ACTIVA el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El activador debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

<div id="general-settings" />

### Configuración general

**ID de cuenta e ID de aplicación**

LINE Ads Platform se conecta con AppsFlyer a través de un LINE\_Ad\_account\_id y LINE\_Ad\_app\_ID únicos.  
**Para habilitar la integración:** Ingresa tu <Anchor target="_blank" href="https://lineforbusiness.com/th-en/service/line-ads/manual#Tracking:~:text=Tracking%20app%20conversions">LINE\_Ad\_account\_id y LINE\_Ad\_app\_ID</Anchor>únicos.

* Introduce tu **LINE\_Ad\_account\_id** único y tu **LINE\_Ad\_app\_ID**.   
  Consulta la <Anchor target="_blank" href="https://lineforbusiness.com/th-en/service/line-ads/manual#Tracking:~:text=Tracking%20app%20conversions">documentación de Line Ads sobre cómo crear un ID de empresa</Anchor>.

<div id="connect-multiple-accounts-and-apps" />

#### Conecta varias cuentas y aplicaciones

Puedes conectar varias cuentas y aplicaciones de Line Ads a AppsFlyer añadiendo manualmente un parámetro de ID de cuenta o de ID de aplicación a un enlace de atribución, después de crearlo.

<div id="note-1" />

> 📘 **Nota**
>
> Los parámetros que existen tanto en el enlace de atribución como en **Configuración general** provocan conflictos. Para evitarlo, consulta la **lógica de prioridad de parámetros** que se describe más abajo antes de añadir parámetros al enlace de atribución.

**Lógica de prioridad de parámetros**

* Cuando ambos tipos de parámetros, ID de cuenta e ID de aplicación (line\_ad\_account\_id, line\_ad\_app\_id), se incluyen en el enlace de atribución, se sobrescribe cualquier ID correspondiente configurado en Configuración general.
* Cuando falta uno de los tipos de parámetros en el enlace de atribución, pero se ha configurado en la Configuración general, el valor configurado en la Configuración general se incluirá en la conexión.
* Cuando faltan ambos tipos de parámetros, el ID de cuenta y el ID de aplicación, tanto en la Configuración general como en los enlaces de atribución, es posible que la integración no funcione como se espera.

**Para conectar varios parámetros de ID de cuenta e ID de aplicación:**

1. Configura uno o varios <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">enlaces de atribución</Anchor>.
2. Añade a cada enlace de atribución un parámetro de ID de cuenta y uno de ID de aplicación con letras minúsculas. Consulta la parte resaltada en el ejemplo siguiente.

<div id="example" />

> 📄 **Ejemplo**
>
> Ejemplo de enlace de atribución con parámetros de ID de cuenta e ID de aplicación:
>
> ```http
> https://app.appsflyer.com/id123456789?pid=example_int;...line_ad_account_id=A123456789123&line_ad_app_id=1234567891234&...;redirect=false
> ```

<div id="default-postbacks" />

### Postbacks predeterminados

Envía postbacks automáticos a LINE Ads Platform después de las instalaciones y nuevas interacciones del usuario. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

Selecciona **Solo eventos atribuidos a este partner** para eventos que provienen únicamente de usuarios atribuidos a LINE Ads Platform.  
Selecciona **Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para informar a LINE Ads Platform.

<div id="in-app-events-settings" />

### Configuración de eventos in-app

En esta sección puedes mapear tus eventos de AppsFlyer con LINE Ads Platform mediante postbacks.

1. Ingresa LINE\_Ad\_app\_ID y LINE\_Ad\_account\_id nuevamente.
2. Activa los Postbacks de eventos in-app con el selector.
3. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que provienen **únicamente** de usuarios atribuidos a este partner  
   **- Eventos atribuidos a cualquier partner u orgánico** para tener toda tu base de usuarios disponible para ser reportada al partner
4. En la lista desplegable, selecciona un ***Nombre de evento del SDK***.
5. Desde el ***Identificador de Evento de Partner*** lista desplegable, seleccione la opción correspondiente.
6. Haz clic en ***Agregar evento*** para agregar nombres de eventos adicionales.
7. Completa los siguientes parámetros:

| Nombre de parámetro | Descripción |
| --- | --- |
| **Nombre de evento SDK** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea desde el SDK integrado con tu aplicación o desde eventos de servidor a servidor.  <br />**Consejo**: Si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| **Identificador de Evento de Partner** | El nombre o ID único de cada evento tal como se define en el lado de la plataforma LINE Ads.  <br />Obtén el ID de evento correspondiente de LINE Ads Platform y configúralo en el campo de texto. |
| **Enviar ingresos** | **Si esta opción no está marcada**: se envían al partner todos los parámetros del evento in-app enriquecido, con excepción del parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Cuando está marcada**: se envían todos los parámetros incluyendo el valor de ingresos (si existe en el evento). |

<div id="custom-in-app-events-mapping" />

### Asignación de eventos in-app personalizados

AppsFlyer te permite asignar cualquier evento personalizado en la aplicación para enviarlo a LINE, utilizando la opción Identificador de evento de partner PERSONALIZADO.

El nombre y el valor del evento (incluidos sus parámetros) configurados en el SDK se reenvían a Facebook, tal como están.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlace de atribución">

Genera y guarda enlaces de atribución y envíalos al partner para que te atribuya campañas específicas, conjuntos de anuncios o anuncios únicos, tanto para campañas de UA como de retargeting. Puedes utilizar un enlace de plataforma única o <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">Saber más sobre la estructura y los parámetros de los enlaces de atribución</Anchor>.

**Para generar un enlace de atribución,** sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#attribution-link-tab">estas instrucciones</Anchor>.

[Sigue estas instrucciones](https://help.line.me/admanager/web/categoryId/20007423/pc) para activar el enlace de atribución en LINE Ads Platform.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de Costo">

Este partner no admite datos de costos.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de ingresos publicitarios">

Este partner no admite ingresos publicitarios.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

No hay configuraciones de permisos disponibles para LINE Ads Platform.

</Accordion>

<div data-zendesk-anchors="setting-up-line-ads-platform=configurando-line-ads-platform h_01HKW2TJ83EZSV30XH3CM0HHB7=configurando-line-ads-platform h_01HKW2TJ83RG7W6F2PZMAY7BXZ=integration-tab h_01HKW2TJ83VEK727ZH9FPH6TPJ=nota activate-partner=activar-partner h_01HKW2TJ83VPWD1GK99S4MY3ZB=activar-partner general-settings=configuraci%C3%B3n-general h_01HKW2TJ83PFS3TCPHKZ9HY5PE=configuraci%C3%B3n-general connect-multiple-accounts-and-apps=conecta-varias-cuentas-y-aplicaciones h_01JAA89AWAQ4JZS3522EVZZN8D=conecta-varias-cuentas-y-aplicaciones 01JB6YF9SFD2TWTZGR0RPVEBTC=nota-1 01JAT9SYW9C06P185S9TWKAFM0=ejemplo default-postbacks=postbacks-predeterminados h_01HKW2TJ838FFTAR7NQC9WX295=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HKW2TJ833VC6SGSRNJSZ53WR=configuraci%C3%B3n-de-eventos-in-app custom-inapp-events-mapping=asignaci%C3%B3n-de-eventos-in-app-personalizados h_01HKW2TJ83GQ7SFKV6YPM49QP1=asignaci%C3%B3n-de-eventos-in-app-personalizados h_01HKW2TJ83JPB6DSW8Z5PCY1SC=attribution-link-tab h_01HKW2TJ839R8NS3PFHCAJGXTZ=cost-tab h_01HKW2TJ835JT0WD3GN4H3XHT5=ad-revenue-tab h_01HKW2TJ83MPGHKGEMDQQYGGJ1=permissions-tab" />
