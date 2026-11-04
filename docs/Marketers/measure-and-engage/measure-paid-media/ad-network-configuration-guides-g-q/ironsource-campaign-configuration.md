---
title: Configuración de campañas de ironSource
metadata:
  keywords:
    - Supersonic
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
  created_at: '2016-03-06T10:47:23Z'
  edited_at: '2026-08-22T00:24:52Z'
  id: 208005096
  locale: es
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/es/articles/208005096
---
> **De un vistazo:** ironSource es un partner integrado de AppsFlyer que crea herramientas de monetización, engagement, análisis y descubrimiento para desarrolladores de aplicaciones, fabricantes de dispositivos, operadores de telefonía móvil y anunciantes. Además de la atribución móvil basada en clics, ironSource también ofrece atribución de costos, ingresos por publicidad, retargeting y por impresiones, que puedes registrar con AppsFlyer.

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/ironsource.png?v=1" width="213px" />

<div id="setting-up-ironsource" />

## Configuración de ironSource

**Requisito previo:** Una cuenta con Partners. Si no tienes una cuenta, ponte en contacto con Partners para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Collaborate > Partner Integrations > Marketplace** .  
   (**Para editar una integración existente:** Ve a la pestaña **Collaborate > Partner Integrations > Active integrations**.)
2. Selecciona la aplicación correspondiente.
3. Busca Partners y selecciona **Integrate**.
4. En la pestaña **Integración**, activa el selector **Activate partner**.   
   **Nota:** El selector **debe permanecer activado (activo) mientras trabajes con Partners**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de Partners.</Anchor>

> 📘 **Nota**
>
> Como red que rastrea todas las instalaciones, ironSource prefiere recibir postbacks de todas las nuevas instalaciones de tu aplicación desde cualquier fuente, incluidas las orgánicas. Para ello, selecciona **Eventos atribuidos a cualquier partner, u orgánicos** para enviar todos los postbacks de instalación a ironSource.

La ventana de configuración de ironSource incluye 5 pestañas: Integración, Enlace de atribución, Costo, Ingresos por publicidad y Permisos. Haz clic en los elementos que aparecen a continuación para obtener más información sobre la configuración de las pestañas.

<div id="note-1" />

> 📘 **Note**
>
> * El paso de Configuración general de la pestaña Integración es **obligatorio** para todos los Partners
> * Todos los demás pasos son descriptivos u **opcionales**.

<div id="integration-tab" />

<Accordion title="Pestaña Integración">

<div id="activate-partners" />

### Activar los partners

En la **primera visita** aquí, deberás activar el selector **Activar partner** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe permanecer activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

<div id="advanced-privacy" />

#### Privacidad avanzada

Solo para aplicaciones iOS, cuando la **Privacidad avanzada (para iOS 14.5+ y posteriores)** está activada, puedes <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#b">controlar qué datos se comparten</Anchor> con ironSource a través de postbacks y reportes.

<div id="transaction-id" />

### ID de transacción

Solo para aplicaciones iOS, cuando **Compartir ID de transacción de SKAN** está activado, estás  permitiendo que AppsFlyer <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">comparta el ID de transacción de los postbacks de SKAdNetwork</Anchor> con ironSource. Al hacerlo, ironSource podría decodificar tus valores de conversión de SKAdNetwork.

<div id="note-2" />

> 📘 **Nota**
>
> Para la interacción de SKAN con AppsFlyer, comunícate con tu administrador de cuentas de ironSource para <Anchor target="_blank" href="https://developers.is.com/ironsource-mobile/general/universal-skan-reporting/#step-1">habilitar el envío de datos SKAN a MMP</Anchor>.

<div id="general-settings" />

### Configuración general

**ID de anunciante**

ironSource se conecta con AppsFlyer a través de un ID de anunciante único (número de 6 dígitos) y una contraseña. Si aún no tienes el ID y la contraseña del anunciante, debes obtenerlos de ironSource para continuar con la integración. De lo contrario, copia el ID y la contraseña y pégalos en los campos respectivos.

<div id="install-and-re-engagement-attribution" />

### Atribución de instalaciones y re-engagements

Estas dos opciones permiten atribuir a ironSource nuevas instalaciones y reatribuciones de usuarios que **vieron** tu anuncio pero **no hicieron** clic en él. Aprende más sobre la <Anchor target="_blank" href="/marketers/es/docs/measure-view-through-engagements">atribución por impresiones.</Anchor>

**Para atribuir nuevas instalaciones:**

1. Activa **Atribución de instalaciones por impresiones**.
2. Configura la longitud de la ventana retrospectiva **por impresiones** en la [pestaña de Enlace de atribución](/docs/ironsource-campaign-configuration#attribution-link-tab).

**Para atribuir nuevos re-engagements de usuarios existentes:**

1. Activa la **Atribución de re-engagements por impresiones**.
2. Configura la longitud de la ventana retrospectiva **por impresiones** en la [pestaña de Enlace de atribución](/docs/ironsource-campaign-configuration#attribution-link-tab).

<div id="default-postbacks" />

### Postbacks predeterminados

Envía postbacks automáticos a ironSource después de las instalaciones y re-engagements de los usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

Selecciona **Solo eventos atribuidos a este partner** para eventos provenientes solo de usuarios atribuidos a ironSource.  
Selecciona **Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada a ironSource.

<div id="note-3" />

> 📘 **Nota**
>
> Nota: Como red que rastrea todas las instalaciones, ironSource prefiere recibir postbacks de todas las nuevas instalaciones de tu aplicación desde CUALQUIER fuente, incluidas las orgánicas. Para ello, selecciona Eventos atribuidos a cualquier partner para enviar todos los postbacks de instalación a ironSource.

<div id="in-app-event-postbacks" />

### Postbacks de eventos in-app

Configura la asignación de eventos in-app con eventos de ironSource, enviados a través de postbacks:

1. Activa **Postbacks de eventos in-app.**
2. Haz clic en **Agregar evento** para agregar un evento de SDK o de servidor a servidor a la lista. En la siguiente tabla se describen los campos que debes completar:

| Nombre de parámetro | Descripción |
| --- | --- |
| **Evento de AppsFlyer** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea del SDK integrado en tu aplicación o de los eventos de servidor a servidor.<br />**Consejo**: ¿No ves el evento que estás buscando?<ul><li>Asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar.</li><li>Escríbelo en **Evento de AppsFlyer**, y luego haz clic en **Crear personalizado**. Leer más sobre la <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#eventos-personalizados">asignación de eventos personalizados.</Anchor></li></ul> |
| **Asignado al evento de partner** | El ID o nombre único de cada evento, tal y como lo defina el partner. Existen varias configuraciones de asignación:<ul><li>**Campo de texto:** obtén el ID del evento correspondiente del partner.</li><li>**Cuadro desplegable:** selecciona el evento de AppsFlyer predefinido más adecuado.</li><li>**Tal como está**: envía los eventos tal como están, sin asignación de nombres.</li></ul> |
| **Para usuarios de** | Selecciona la opción de envío para el evento:<ul><li>**Solo este partner**: envía postbacks solo cuando este evento se atribuya a este partner.</li><li>**Todas las fuentes de medios, incluidas las orgánicas**: envía postbacks para eventos atribuidos a cualquier partner, así como para eventos orgánicos.</li></ul> |
| **Incluyendo** | <ul><li>**Sin datos (predeterminado)**: envía solo el evento en sí sin los valores del evento.</li><li>**Valores e ingresos**: envía todos los parámetros del evento, **incluido** el valor de ingresos (si existe en el evento).</li><li>**Valores sin ingresos**: envía todos los parámetros **excluyendo** el valor de ingresos.</li></ul> |

3. [Opcional] Haz clic en el icono **Agregar condición** <Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" /> para <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#postbacks-condicionales-de-eventos-in-app">establecer las condiciones</Anchor> de un evento.
4. Haz clic en **Guardar integración**.
5. [Opcional] Después de guardar la integración, desde la página de configuración, puedes integrar más de tus aplicaciones con el partner:
   1. En la esquina superior izquierda, debajo del nombre del partner, haz clic en el nombre de la aplicación para abrir la lista de aplicaciones.
   2. Selecciona una aplicación diferente en la lista desplegable.
   3. Repite los <Anchor target="_blank" href="/marketers/es/docs/amazon-ads-campaign-configuration#integration-tab">pasos de integración</Anchor> para la aplicación seleccionada.

<div id="note-4" />

> 📘 **Nota**
>
> * Solo para aplicaciones de iOS: Tu control sobre los datos compartidos con el partner a través de postbacks y <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions">reportes</Anchor> depende del **estado del selector <Anchor target="_blank" href="/marketers/es/docs/tiktok-for-business-advanced-srn-integration-setup#advanced-privacy">Privacidad avanzada (para iOS 14.5+ y posteriores)</Anchor>**.
> * Puedes enviar <Anchor target="_blank" href="/marketers/es/docs/roi360-guide-ad-revenue-attribution#ad-revenue-event-postbacks-for-ad-networks">postbacks de ingresos por publicidad</Anchor> a ironSource para que puedan optimizar las campañas mediante datos de ingresos por publicidad:
>   * **Nombre del evento:** af\_ad\_revenue
>   * **Asignado a:** adRevenue

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Genera y guarda enlaces de atribución y envíalos al partner para atribuir campañas específicas, conjuntos de anuncios o anuncios individuales, tanto para campañas de UA como de retargeting. Puedes utilizar un enlace de plataforma única o <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">Aprende más sobre la estructura del enlace de atribución y los parámetros</Anchor>.

**Para generar un enlace de atribución,** sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#attribution-link-tab">estas instrucciones</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña Costo">

AppsFlyer obtiene los detalles de los costos por API. Consulta la <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabla de integración de costos de redes de publicidad</Anchor> para obtener más información sobre las dimensiones, métricas y funciones admitidas. **Nota:** Los datos de costos requieren una suscripción a ROI360.

**Para habilitar la API de costos**:

* <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">Sigue estas instrucciones de integración</Anchor>

<Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Visualiza el estado de tu API de costos</Anchor> y la última vez que AppsFlyer logró extraer los datos de costos coincidentes en el panel de control de estado de la integración de costos (e ingresos por publicidad) o en el panel de control de la red de publicidad individual.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña Ingresos por publicidad">

Si muestras anuncios en la aplicación proporcionados por la mediación de Unity LevelPlay (antes, ironSource) o por la red de monetización de ironSource, esta sección es relevante.

Están disponibles las siguientes opciones de granularidad de los ingresos por anuncios:

* Nivel agregado (a través de la API S2S).
* Nivel de dispositivo (a través de la API S2S).
* Nivel de impresión (por SDK).
* Nivel de impresión (por SDK) con nivel de dispositivo (por API S2S)

Aprende más sobre la <Anchor target="_blank" href="/marketers/es/docs/roi360-guide-ad-revenue-attribution">atribución de ingresos por publicidad</Anchor>.

**Para habilitar la API de ingresos por publicidad**:

* Sigue <Anchor target="_blank" href="/marketers/es/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">estas instrucciones de integración</Anchor>.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres otorgarle a ironSource, sea que el partner actúe como red de publicidad, agencia o ambas. Ten en cuenta que, incluso si la atribución estuviera deshabilitada para ironSource, la pestaña Permisos se encontraría activa y podrías otorgarle el control a ironSource.

Utiliza estos selectores para otorgarle permisos a la red de publicidad para que gestione su propia configuración para tu aplicación:

<div id="ad-network-permissions" />

### Permisos para red de publicidad

* **Permitir la configuración de la integración**: permite que el partner configure la pestaña Integración (con excepción de postbacks de eventos in-app).
* **Permitir la configuración de postbacks de eventos in-app**: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña Integración.
* **Permitir el acceso a tu reporte de retención**: solo para los datos propios de retención del partner.
* **Permitir acceso a tus datos agregados de usuarios legales**: solo para los datos propios de usuarios leales del partner.
* **Permitir acceso a tus datos agregados de eventos in-app**: solo para los datos de eventos in-app propios del partner.
* **Permitir acceso a tus datos agregados de ingresos**: solo para los datos de ingresos atribuidos al partner.
* **Permitir el acceso a tu panel de control de Protect360**: solo para los datos propios de Protect360 del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

<div id="agency-permissions" />

### Permisos para agencias

Utiliza estos selectores para otorgar permisos a una agencia para que gestione su propia configuración para tu aplicación:

* **Selector principal**: actívalo para mostrar las opciones de permisos para agencias.
* **Permitir el acceso a tu reporte de retención**: solo para los propios datos de retención de la agencia.
* **Permitir el acceso a datos agregados orgánicos.**
* **Permitir la configuración de postbacks de eventos in-app**: permite que la agencia configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña Integración.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permisos-de-la-agencia">permisos a las agencias</Anchor>.

</Accordion>

</Accordion>

<div data-zendesk-anchors="setting-up-ironsource=configuraci%C3%B3n-de-ironsource h_01KZX3MPJ9HY5WJB3MS65SZXNY=configuraci%C3%B3n-de-ironsource h_01HKW1E1KBG121H7YJBW2SZS6E=nota h_01HCFHXQQ8XYCKWPVTMK8HF165=integration-tab activate-partners=activar-los-partners h_01HCFHXQQ8HCXPEWR4CWY55M2H=activar-los-partners advanced-privacy=privacidad-avanzada h_01HCFHXQQ8ABQYRSBGC7Z1F1SV=privacidad-avanzada transaction-id=id-de-transacci%C3%B3n h_01HCFHXQQ8Q3BX7GSGD5MH4QT8=id-de-transacci%C3%B3n h_01HCFHXQQ8D26KT5E6YEQ50DA4=nota-1 general-settings=configuraci%C3%B3n-general h_01HCFHXQQ8J0ZC9FGCNTPMKHK6=configuraci%C3%B3n-general install-and-reengagement-attribution=atribuci%C3%B3n-de-instalaciones-y-re-engagements h_01HCFHXQQ8V2E8982XRSY4G50F=atribuci%C3%B3n-de-instalaciones-y-re-engagements default-postbacks=postbacks-predeterminados h_01HCFHXQQ8Q27JXG2V7G4XZX43=postbacks-predeterminados h_01HCFHXQQ8XZ6H3733GPR3ZFYE=nota-2 inapp-event-postbacks=postbacks-de-eventos-in-app h_01HCFHXQQ891GH196XFRXY8MYS=postbacks-de-eventos-in-app h_01HCFHXQQ8VF25W10CWQHTEAYW=nota-3 h_01HCFHXQQ8AYNTCH9GHZJG594E=attribution-link-tab h_01HCFHXQQ87EBRW9NBY58XYFGP=cost-tab h_01HCFHXQQ8XZ8XQFH3XRFVHRZV=ad-revenue-tab h_01HCFHXQQ891P7ET9Q4BSQWJXT=permissions-tab ad-network-permissions=permisos-para-red-de-publicidad h_01HCFHXQQ86VNX9WRFEZECYV7R=permisos-para-red-de-publicidad agency-permissions=permisos-para-agencias h_01HCFHXQQ936CQ1FVHCRC58H4C=permisos-para-agencias" />
