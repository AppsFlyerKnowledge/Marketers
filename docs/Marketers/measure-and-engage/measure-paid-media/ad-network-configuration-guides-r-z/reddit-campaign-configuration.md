---
title: Configuración de la campaña de Reddit
metadata:
  keywords:
    - integrated partner
    - Advertisers
    - Agencies
    - reddit
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
  created_at: '2020-07-09T09:50:46Z'
  edited_at: '2026-11-02T13:15:05Z'
  id: 360011016138
  locale: es
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/es/articles/360011016138
---
> **En resumen:** Reddit, un partner integrado de la red de publicidad de AppsFlyer, es el hogar de 430 millones de usuarios mensuales altamente comprometidos que no se pueden encontrar en ningún otro lugar.

## Configuración de Reddit

**Requisito previo:** Una cuenta con el partner. Si no tienes una cuenta, contacta con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de Partners > Marketplace**.  
   (**Para editar una integración existente:** Ve a la pestaña **Colaborar > Integraciones de Partners > Integraciones activas**.)
2. Selecciona la aplicación correspondiente.
3. Busca el partner y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el conmutador **Activar partner**.   
   **Nota:** El conmutador **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de Partners.</Anchor>

<div id="integration-tab" />

<Accordion title="Pestaña Integración">

La ***Pestaña Integración*** se divide en diferentes secciones:

#### Activar los partners

Para habilitar la configuración, <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation#activar-la-integración-de-un-partner">Activar el partner</Anchor>.

#### Privacidad avanzada

**Solo para aplicaciones iOS, cuando la <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#b-advanced-privacy">Privacidad avanzada (para iOS 14.5+ y posteriores)</Anchor>** está activada, puedes controlar qué datos se comparten con Reddit a través de postbacks y reportes.

#### ID de transacción

**Solo para aplicaciones de iOS, cuando <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">Compartir el ID de transacción de SKAN</Anchor>** está encendido, estás permitiendo que AppsFlyer comparta el ID de transacción de los postbacks de SKAdNetwork con Reddit. Al hacerlo, Reddit podría decodificar sus valores de conversión de SKAdNetwork.

#### Configuración general

**Habilitar la atribución view-through**

Actívalo, si deseas atribuir las instalaciones por impresiones de Reddit. El control deslizante de la ventana retrospectiva por impresiones está disponible en la pestaña del enlace de [***atribución***](/docs/reddit-campaign-configuration#attribution-link-tab) (se describe a continuación).

**Uso compartido de datos de coincidencia avanzada**

Activa esta opción para compartir con Reddit los campos de coincidencia avanzada, como el correo electrónico con hash, el número de teléfono con hash, el nombre con hash y el apellido con hash, si estos campos se incluyen en la información del evento enviada a AppsFlyer. Para más información, consulta: <Anchor target="_blank" href="/marketers/es/docs/advanced-matching-data-sharing">Uso compartido de datos de Advanced Matching</Anchor>.

#### Postbacks predeterminados

Envía postbacks automáticos a Reddit después de las instalaciones de los usuarios. Selecciona si deseas enviar postbacks para las instalaciones atribuidas a:

* Solo en Reddit
* Todas las fuentes, incluidas las orgánicas

#### Configuración de eventos in-app

En esta sección, puedes configurar los postbacks de eventos in-app que se envían a Reddit.

**Para configurar postbacks de eventos in-app:**

1. Activar ***Postbacks de eventos in-app***
2. Haz clic en *Agregar evento* para agregar un evento del SDK a la lista.
3. Rellena los siguientes datos:

| Nombre del parámetro | Descripción |
| --- | --- |
| **Nombre de evento SDK** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea desde el SDK o desde eventos de servidor a servidor.  <br />**Consejo**: si no ves el evento que quieres en la lista, actívalo en un dispositivo con una instalación no orgánica y vuelve a comprobarlo. |
| **Identificador de evento de partner** | El nombre o ID único de cada evento, tal como se define en el lado de Reddit. Selecciona el evento predefinido más adecuado para tu evento SDK:<ul><li>rdt\_install</li><li>rdt\_signup</li><li>rdt\_app\_launch</li><li>rdt\_search</li><li>rdt\_view\_content</li><li>rdt\_add\_payment\_info</li><li>rdt\_add\_to\_cart</li><li>rdt\_purchase</li><li>rdt\_completed\_tutorial</li><li>rdt\_level\_achieved</li><li>rdt\_spend\_credits</li><li>rdt\_ad\_click</li><li>rdt\_ad\_view</li><li>rdt\_add\_to\_wishlist</li><li>rdt\_unlock\_achievement</li><li>rdt\_login</li><li>rdt\_rate</li><li>rdt\_checkout</li><li>rdt\_start\_trial</li><li>rdt\_subscribe</li><li>rdt\_onboard\_started</li><li>rdt\_onboard\_completed</li><li>rdt\_first\_time\_purchase</li></ul> |
| **Opción de envío** | Selecciona si deseas enviar eventos de la siguiente manera:<ul><li>Solo en Reddit</li><li>todas las fuentes, incluidas las orgánicas</li></ul> |
| **Enviar datos de eventos** | <ul><li>**Sin valores ni ingresos:** envía solo el evento en sí sin el valor del evento.</li><li>**Con valores y sin ingresos:** envía todos los parámetros, excepto el valor de ingresos.</li><li>**Con valores e ingresos**: envía todos los parámetros del evento, incluido el valor de ingresos (si existe en el evento).</li></ul> |

4. Haz clic en ***Save*** (Guardar).

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlace de atribución">

Genera y guarda enlaces de atribución y envíalos al partner para que te atribuya campañas específicas, conjuntos de anuncios o anuncios únicos, tanto para campañas de UA como de retargeting. Puedes utilizar un enlace de plataforma única o un OneLink.  
<Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">Saber más sobre la estructura y los parámetros de los enlaces de atribución</Anchor>.

**Para generar un enlace de atribución,** sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#attribution-link-tab">estas instrucciones</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costo">

AppsFlyer obtiene los detalles de los costos por API. Consulta <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">la tabla de integración de costos de redes de publicidad</Anchor> para obtener más información sobre las dimensiones, métricas y funciones admitidas. **Nota**: Los datos de costos requieren una suscripción a ROI360.

**Para habilitar la API de costos**:

* Sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">estas instrucciones de integración</Anchor>.

<Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Visualiza el estado de tu API de costos</Anchor> y la última vez que AppsFlyer logró extraer los datos de costos coincidentes en el panel de control de estado de la integración de costos (e ingresos por publicidad) o en el panel de control de la red de publicidad individual.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de ingresos por publicidad">

Los datos de ingresos por publicidad no son compatibles con Reddit.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos para otorgar a Snapchat. Ten en cuenta que incluso si la atribución está deshabilitada para Reddit, la pestaña de permisos está activa y puedes otorgar el control a Reddit.

#### Permisos para red de publicidad

En esta pestaña, puedes seleccionar los permisos para otorgar a Snapchat. Ten en cuenta que incluso si la atribución está deshabilitada para Reddit, la pestaña de permisos está activa y puedes otorgar el control a Reddit.

Utiliza estos selectores para otorgarle permisos a la red de publicidad para que gestione su propia configuración para tu aplicación:

* <span id="01EDKYCTJGZCQ05BQ5JXR6457Y"></span>***<span id="01EDKYCTJHNYT3SRD6Q40YJKR1"></span>Permitir la configuración de la integración***: Permite que el partner configure la pestaña Integración (con excepción de postbacks de eventos in-app).
* <span id="01EDKYCTJHVW0E6TD5ARMFEQQC"></span>***Permitir la configuración de postbacks de eventos in-app***: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña de integración.
* <span id="01EDKYCTJH6C06V91M50CXNSZS"></span>***Permitir el acceso a tu reporte de retención***: solo para los propios datos de retención del partner.
* <span id="01EDKYCTJHY2JXJHQRQM6S1T7H"></span>***Permitir acceso a tus datos agregados de usuarios fieles***: solo a los datos de usuarios fieles propios del partner.
* <span id="01EDKYCTJHF1W3FPJCSSEKJ4GZ"></span>***Permitir acceso a tus datos agregados de eventos in-app**:* solo a los datos de eventos in-app propios del partner.
* <span id="01EDKYCTJHVN8E1QPY3BSMC3WD"></span>***Permitir acceso a tus datos agregados de ingreso*a:** : solo a los datos de ingresos atribuidos al partner.
* <span id="01EDKYCTJHX0T89JNPJKY71WVW"></span>***Permitir la ingesta de gastos:*** Permitir que el partner envíe datos de inversión publicitaria en archivos solo para esta aplicación.
* <span id="01EDKYCTJHWKWYJS7ZFCJ8558V"></span>***Permitir el acceso a tu panel de control de Protect360***: solo a los datos de Protect360 propios del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

</Accordion>

## Restricciones de raw data

A partir del 8 de septiembre de 2026: se eliminaron las restricciones anteriores y se admiten completamente todos los campos de atribución.

Los clics e impresiones de Reddit no se incluyen en los informes de datos sin procesar.

**Recordatorio:** Los datos recibidos sobre una campaña de Reddit están sujetos a los <Anchor target="_blank" href="https://protect.checkpoint.com/v2/___https:/business.reddithelp.com/s/article/Reddit-Business-Tool-Terms___.YzJ1OnJlZGRpdDpjOmc6OGFlZGI3Y2U5MDg3ZTgxNzYxYzdjMzEzYzgwZjI3ZDI6NjowMDg5Ojg1MmViZDg4YWY2ZTg4NThjMDE2NjhkYTk2ZjZkYmZlYWI1NGY3MGEwNDk0MmE0ODQ0NTI3ZDM0ZWYwOWVlMmI6cDpUOk4#:%7E:text=These%20Reddit%20Business%20Tool%20Terms,advertising%20purposes%20or%20to%20otherwise">Términos de las herramientas para empresas de Reddit</Anchor> y, entre otras restricciones, incluyen la prohibición de usar datos de Reddit para crear perfiles de cualquier usuario.

<div data-zendesk-anchors="setting-up-reddit=configuraci%C3%B3n-de-reddit 01EDKYCH117BTY81G0Z2NF181F=configuraci%C3%B3n-de-reddit 01EDKYCH11YM04HDJTAWP4XHWH=integration-tab activate-partners=activar-los-partners 01EDKYCH11E2X1VSSG2HKKP6VS=activar-los-partners advanced-privacy=privacidad-avanzada h_01HJRZF42CYME3EZ37470339CF=privacidad-avanzada transaction-id=id-de-transacci%C3%B3n h_01HJRZF42CN7VT8SKNX5E638R0=id-de-transacci%C3%B3n general-settings=configuraci%C3%B3n-general 01EDKYCH11WFJ09XBND6RQT0XA=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados 01EDKYCH11KZT2BN64AGETTMD6=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app 01EDKYCH11QAYSV2GMYD4R6DJJ=configuraci%C3%B3n-de-eventos-in-app h_01HJRZF42DHDDHPCE4NYA7QKV2=attribution-link-tab h_01HJRZF42DYG18DTKSV4G8NHV4=cost-tab 01EDKYCH124QTAFK6VQ3ARHCTM=ad-revenue-tab 01EDKYCH12RY4P6DY3QSWG1A18=permissions-tab ad-network-permissions=permisos-para-red-de-publicidad 01EDKYCH12FXE1WASY5YQF80CV=permisos-para-red-de-publicidad raw-data-restrictions=restricciones-de-raw-data 01JAQ0TCR54Q03RQWPNT5PJGPN=restricciones-de-raw-data" />
