---
title: Configuración de campañas de Unity Ads
metadata:
  keywords:
    - Unity Ads
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
  created_at: '2016-03-06T10:05:52Z'
  edited_at: '2026-09-11T00:25:14Z'
  id: 208005086
  locale: es
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/es/articles/208005086
---
> **De un vistazo:** Unity Ads, un partner integrado de la red de publicidad de AppsFlyer, es una red de publicidad de video para iOS y Android. Además de la atribución móvil basada en clics, Unity Ads ofrece atribución de costos, ingresos por publicidad e impresiones, que se pueden registrar en AppsFlyer.

Para configurar tus campañas con Unity Ads, sigue los pasos a continuación.

<div id="setting-up-unity-ads" />

## Configuración de Unity Ads

**Requisito previo:** Una cuenta con el Partners. Si no tienes una cuenta, contacta con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de Partners > Marketplace**.  
   (**Para editar una integración existente:** ve a la pestaña **Colaborar > Integraciones de Partners > Integraciones activas**.)
2. Selecciona la aplicación correspondiente.
3. Busca el Partners y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el selector **Activar Partners**.   
   **Nota:** El selector **debe permanecer activado (activo) mientras trabajes con el Partners**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de Partners.</Anchor>

<div id="integration-tab" />

<Accordion title="Pestaña Integración">

<div id="activate-partners" />

### Activar los partners

En la primera visita, tendrás que activar el selector **Activar partner** para configurar la integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

<div id="general-settings" />

### Configuración general

**Envío del ID de dispositivo (ID de publicidad) a Unity**

En la parte superior de la pestaña Integración, hay una nota que dice que Unity Ads requiere enviarles el ID del dispositivo para cada instalación; esto se hace automáticamente, sin necesidad de hacer nada por tu parte.

<Image align="center" alt="Unity_msc_new_2.png" src="https://files.readme.io/4291f0b69f8231f6644872f2dfaec84e7c93047e81f653e76ff7266387fa10a9-360002583918.png" />

**ID de juego de Unity Ads**

Unity Ads requiere conectarse con AppsFlyer a través de un ID de juego único. Si no conoces el tuyo, puedes obtenerlo directamente de Unity Ads o puedes encontrarlo, después de subir el juego, en **Aplicaciones** > **Campañas**, como se muestra en la captura de pantalla a continuación.

<Image align="center" alt="" src="https://files.readme.io/c3315765f33e957b82c39b638bb8113e207bfe80f242bf2e6dde3dce30287a6f-8109147574673.png" />

La plataforma Unity Ads asigna una aplicación a un ID de juego único de Unity Ads, por nivel de cuenta (los anunciantes y las agencias tendrán diferentes ID de juego para la misma aplicación). Varias cuentas en la plataforma Unity Ads no pueden ejecutar la misma aplicación con diferentes ID de juego.

**Habilitar la atribución por impresiones**

Activa esta opción para atribuir las instalaciones por impresiones de Unity Ads. El control deslizante de retrospectiva por impresiones está disponible en la pestaña del enlace de atribución (descrito a continuación).

<Image align="center" alt="Unity_ads_msc_new_3.png" src="https://files.readme.io/fab459ace7e8f1354d3bbfbca8ddefcd11376b7426a8e361abfab1b42b623880-360001875405.png" />

<div id="default-postbacks" />

### Postbacks predeterminados

<Image align="center" alt="Screen_Shot_2022-07-28_at_13.07.25.png" src="https://files.readme.io/a571ddc49e490373b34144e34626a18c6c18908cec3345cd7ac70c49aa855c05-7975491293329.png" />

Envía postbacks automáticos a Unity Ads después de las instalaciones y re-engagements de los usuarios. Utiliza esta sección para definir el origen de los usuarios que permiten enviar estos postbacks:

* **Solo este partner**: para eventos que provienen solo de usuarios atribuidos a Unity Ads.
* **Todas las fuentes de medios, incluidas las orgánicas**: para que toda tu base de usuarios esté disponible para ser reportada a Unity Ads.

<div id="note" />

> 📘 **Nota**
>
> Como red que rastrea todas las instalaciones, Unity Ads prefiere recibir postbacks de todas las nuevas instalaciones de tu aplicación desde cualquier fuente, y recomienda seleccionar **Todas las fuentes de medios, incluidas las orgánicas** para enviar todos los postbacks de instalaciones a Unity Ads.

<div id="in-app-events-settings" />

### Configuración de eventos in-app

Asigna eventos de AppsFlyer con el partner a través de postbacks. Si el envío de postbacks está activado, esto incluye los eventos in-app rechazados (eventos bloqueados por Protect360 o eventos que no cumplen con las reglas de validación del targeting).

<Image align="center" alt="" src="https://files.readme.io/e0d0af3c57c8452b646dfede7b4899215825ef8455d4e41293088f98ecc026eb-7975565240337.png" />

<div id="to-configure-in-app-event-postbacks" />

#### Para configurar postbacks de eventos in-app

1. Introduce el **game\_id**. Asegúrate de que el game\_id es correcto y es el mismo que se usa para la atribución de instalaciones.
2. Activa **Postbacks de eventos in-app.**
3. Establece la **Ventana de postback de eventos in-app**, si es necesario (leer más sobre la <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#ventana-de-postback-de-eventos-in-app">configuración de la ventana de postback de eventos in-app</Anchor>).
4. Haz clic en **Agregar evento** para agregar un evento de SDK o de servidor a servidor a la lista.
5. Completa los siguientes parámetros:

| Nombre de parámetro | Descripción |
| --- | --- |
| **Evento de AppsFlyer** | El nombre del evento, tal y como lo recibe AppsFlyer, ya sea desde el SDK integrado en tu aplicación o desde los eventos de servidor a servidor.<br />**Consejo**: ¿No ves el evento que buscas?<ul><li>Asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar.</li><li>Escríbelo en **Evento de AppsFlyer**, luego haz clic en **Crear personalizado**. Leer más sobre <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#eventos-personalizados">la asignación de eventos personalizados.</Anchor></li></ul> |
| **Asignado al evento de partner** | El ID o nombre único de cada evento, tal y como lo defina el partner. Existen varias configuraciones de asignación:<ul><li>**Campo de texto:** obtén el ID del evento correspondiente del partner.</li><li>**Cuadro desplegable:** selecciona el evento de AppsFlyer predefinido más adecuado.</li><li>**Tal como está**: envía los eventos tal como están, sin asignación de nombres.</li></ul> |
| **Para usuarios de** | Selecciona la opción de envío para el evento:<ul><li>**Solo este partner**: envía postbacks solo cuando este evento se atribuya a este partner.</li><li>**Todas las fuentes de medios, incluidas las orgánicas**: envía postbacks para eventos atribuidos a cualquier partner, así como para eventos orgánicos. Según Unity Ads, se recomienda esta opción.</li></ul> |
| **Incluyendo** | <ul><li>**Sin datos (predeterminado)**: envía solo el evento en sí sin el valor del evento.</li><li>**Valores e ingresos**: envía todos los parámetros del evento, **incluido** el valor de ingresos (si existe en el evento). Según Unity Ads, se recomienda esta opción.</li><li>**Valores sin ingresos**: envía todos los parámetros **excluyendo** el valor de ingresos.</li></ul> |

<div id="important" />

> 🚧 **¡Importante!**
>
> Selecciona el evento de SDK/servidor a servidor correcto y el identificador de evento del partner correspondiente. No dupliques eventos (no transmitas los mismos eventos bajo diferentes nombres de eventos de SDK/servidor a servidor).

<div id="note-1" />

> 📘 **Nota**
>
> Puedes enviar <Anchor target="_blank" href="/marketers/es/docs/roi360-guide-ad-revenue-attribution#ad-revenue-event-postbacks-for-ad-networks">postbacks de ingresos por publicidad</Anchor> a Unity Ads para que puedan optimizar las campañas mediante datos de ingresos por publicidad:
>
> * **Nombre del evento:** af\_ad\_revenue
> * **Asignado a:** ad\_revenue

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Genera y guarda los enlaces de atribución y envíalos al partner para atribuir campañas específicas, conjuntos de anuncios o anuncios individuales, tanto para UA como para campañas de retargeting. Puedes usar un enlace de plataforma única o un <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">Aprender más sobre la estructura del enlace de atribución y los parámetros</Anchor>.

**Para generar un enlace de atribución,** sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#attribution-link-tab">estas instrucciones</Anchor>.

**Notas:**

* Cuando la audiencia objetivo de una aplicación de Android incluye niños, Unity envía el ID de publicidad cero.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña Costo">

El costo por clic no es compatible. AppsFlyer obtiene los detalles de costos por API. Consulta la <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabla de integración de costos de redes de publicidad</Anchor> para obtener detalles completos sobre las dimensiones, métricas y características compatibles. 

**Nota**:

* Los datos de costos requieren una suscripción a ROI360.
* Los datos de costos de Unity Ads solo se pueden recibir para descargas provenientes de Google Play o Apple App Store. Para Android, los datos de costos para tiendas de aplicaciones Android de terceros no son compatibles.
* El costo de la agencia no se admite a través del costo por clic o API. Los anunciantes pueden enviar datos de costos de agencia a través del <Anchor target="_blank" href="/marketers/es/docs/import-cost-data">Procesamiento de gastos publicitarios</Anchor>.

**Para habilitar la API de costos**:

* Sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">estas instrucciones de integración</Anchor>. **Nota**: Para integraciones de costos de Unity, todas las aplicaciones con la misma clave API deben contener el mismo Org ID. De lo contrario, la obtención de datos de costos se ve afectada. Asegúrate de seleccionar el **ID principal de la organización**.

<Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Visualiza el estado de tu API de costos</Anchor> y la última vez que AppsFlyer logró extraer los datos de costos coincidentes en el panel de control de estado de la integración de costos (e ingresos por publicidad) o en el panel de control de la red de publicidad individual.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña Ingresos por publicidad">

Esta sección es pertinente si actúas como publisher y muestras anuncios del partner a tus usuarios. Como tal, con seguridad te gustaría medir el nivel de engagement de tus usuarios adquiridos a partir de distintas fuentes, a fin de identificar las fuentes que te resultan más rentables.

**Para habilitar la API de ingresos por publicidad**:

* Leer más sobre cómo Unity Ads define los clics y las visualizaciones.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos para conceder a Unity Ads para realizar ciertas acciones. Ten en cuenta que incluso si la atribución está deshabilitada para Unity Ads, la pestaña de permisos está activa y puedes conceder permisos de Unity Ads.  
Aprende más sobre <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">los permisos que puedes conceder</Anchor>.

</Accordion>

</Accordion>

<div data-zendesk-anchors="setting-up-unity-ads=configuraci%C3%B3n-de-unity-ads h_01HAPVZ510GTJRY1NXE0T3SMR6=configuraci%C3%B3n-de-unity-ads h_01HAPVZ510KPB0HQS9X6R4BCWT=integration-tab activate-partners=activar-los-partners h_01HAPVZ510BGQ4KZ3S6ZP0QRE8=activar-los-partners general-settings=configuraci%C3%B3n-general h_01HAPVZ510EZ3HKJQVPMKHV5FH=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01HAPVZ511MRQXKPC78HR61X9P=postbacks-predeterminados h_01HAPVZ511CCXS93Y714STGQ67=nota inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HAPVZ511CJ6JP49HYG9T6RPF=configuraci%C3%B3n-de-eventos-in-app to-configure-inapp-event-postbacks=para-configurar-postbacks-de-eventos-in-app h_01HAPVZ511RMEVNASSTJNXKCJG=para-configurar-postbacks-de-eventos-in-app h_01HAPVZ511AV30DEKMZ0YB5ZBD=importante h_01HAPVZ511PC45Q5FEXQMZ4MFC=nota-1 h_01HAPVZ5110QVYGGCGQDHRJEQM=attribution-link-tab h_01HAPVZ511DSKFAKKNWTKV9522=cost-tab h_01HAPVZ5111WPRRMPF6GZJTRJS=ad-revenue-tab h_01HAPVZ511RBNY3HHSHJHJDPWG=permissions-tab" />
