---
title: Configuración de la campaña de AdColony
metadata:
  keywords:
    - Adcolony
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
  created_at: '2016-03-06T10:58:12Z'
  edited_at: '2026-09-11T00:22:41Z'
  id: 208005106
  locale: es
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/es/articles/208005106
---
> **De un vistazo:** AdColony, un partner integrado de ad network de AppsFlyer, es una red de publicidad en vídeo premium que proporciona a anunciantes y marcas una audiencia comprometida y receptiva, y ofrece soluciones de monetización a publishers y desarrolladores. Además de la atribución móvil basada en clics, AdColony también ofrece atribución de costos, ingresos por publicidad y view-through, que puedes registrar con AppsFlyer.

## Configuración de AdColony

**Requisito previo:** una cuenta con el partner. Si no tienes una cuenta, contacta con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de Partners > Marketplace** .  
   (**Para editar una integración existente:** Ve a la pestaña **Colaborar > Integraciones de Partners > Integraciones activas** .)
2. Selecciona la aplicación correspondiente.
3. Busca el partner y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el selector **Activar partner**.   
   **Nota:** El selector **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de Partners</Anchor>

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña **Integración** está dividida en distintas secciones, tal como se describe a continuación.

### Activar los partners

Para habilitar la configuración, debes <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation#activar-la-integración-de-un-partner">activar el partner</Anchor> en la primera visita mediante el conmutador ***Activar partner***.

### Configuración general

#### Habilitar la atribución por impresiones

Activa esta opción si quieres atribuir instalaciones view-through de AdColony. El control deslizante de lookback view-through está disponible en la pestaña ***Enlace de atribución***.

### Postbacks predeterminados

Envía postbacks automáticos a AdColony tras las instalaciones y las instalaciones rechazadas. Utiliza esta sección para definir la **fuente de los usuarios** para los postbacks.

Selecciona ***Solo este partner*** para las instalaciones que provengan únicamente de usuarios atribuidos a AdColony.  
Selecciona ***Todas las fuentes, incluidas las orgáni*cas** para que toda tu base de usuarios esté disponible para reportarla a AdColony.

Las instalaciones rechazadas se pueden enviar a **Solo este partner**.

#### Postbacks de lanzamiento

A partir del 1 de julio de 2020, ya no enviamos postbacks de lanzamiento a AdColony. Si tu integración se configuró antes de esta fecha, puede haber cambios en tus configuraciones. La siguiente tabla explica los posibles cambios y las acciones que debes realizar, cuando corresponda:

| Tu configuración | Se actualizará a | Tus próximas acciones |
| --- | --- | --- |
| Enviar a AdColony **todos los lanzamientos** (de todas las fuentes de medios, incluidas las orgánicas) | Enviar a AdColony:<ul><li>**todas las instalaciones** (de todas las fuentes de medios, incluidas las orgánicas)</li><li>**todos los eventos** `af_app_opened` (de todas las fuentes de medios, incluidas las orgánicas)</li></ul> | No se requieren más acciones. Esta actualización no tiene ningún impacto real en la configuración. |
| Enviar a AdColony **solo las primeras aperturas atribuidas** | Enviar a AdColony **instalaciones** atribuidas solo a AdColony | Si también quieres enviar eventos `af_app_open`:<ul><li>En AppsFlyer, en la página de integración de AdColony, configura el envío del evento en la sección ***Postbacks de eventos in-app***</li></ul> |
| Enviar a AdColony **todas las aperturas** (de todas las fuentes de medios, incluidas las orgánicas)<br /><br />**PERO**<br /><br />No se ha atribuido ninguna conversión a AdColony en los 3 meses anteriores al 1/07/2020 | Enviar **todas las instalaciones**<br /><br />**Y**<br /><br />Durante los 30 días posteriores al 1/07/2020, **todas las aperturas** | Si también quieres enviar eventos `af_app_open`:<ul><li>En AppsFlyer, en la página de integración de AdColony, configura el envío del evento en la sección ***Postbacks de eventos in-app***.</li></ul>Si lo haces durante el periodo de 30 días, dejaremos de enviar todas las aperturas y empezaremos a enviar en su lugar todos los eventos `af_app_open`.<br /><br />Si lo haces después del periodo de 30 días, dejaremos de enviar aperturas y no enviaremos eventos `af_app_open` hasta que se configure de otro modo. |

### Configuración de eventos in-app

En esta sección, puedes configurar los postbacks de eventos in-app que se envían a AdColony.

**Para configurar postbacks de eventos in-app:**

1. Activar ***Postbacks de eventos in-app***
2. Haz clic en ***Agregar evento*** para agregar un evento del SDK a la lista
3.
   | Nombre del parámetro | Nota |
   | --- | --- |
   | **Nombre de evento SDK** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea desde el SDK o desde eventos de servidor a servidor.  <br />**Consejo**: si no ves el evento que quieres en la lista, actívalo en un dispositivo con una instalación no orgánica y vuelve a comprobarlo. |
   | **Identificador de evento de partner** | El nombre exclusivo o ID de cada evento definido por el socio. Selecciona el evento predefinido más adecuado para tu evento SDK. |
   | **Opción de envío** | Selecciona la opción de envío del evento:  <br />**Solo este partner** para eventos que provienen **solo** de usuarios atribuidos a AdColony.  <br />**Todas las fuentes, incluidas las orgánicas** para que toda tu base de usuarios esté disponible para ser reportada al partner |
   | **Enviar datos de eventos** | * **Sin valores ni ingresos:** envía solo el evento en sí sin el valor del evento.<br />* **Con valores y sin ingresos:** envía todos los parámetros, excepto el valor de ingresos.<br />* **Con valores e ingresos**: envía todos los parámetros del evento, incluido el valor de ingresos (si existe en el evento). |

4. Haz clic en ***Save*** (Guardar).

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Genera y guarda enlaces de atribución y envíalos al partner para que te atribuya campañas específicas, conjuntos de anuncios o anuncios únicos, tanto para campañas de UA como de retargeting. Puedes utilizar un enlace de plataforma única o un OneLink.

<Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">Aprende más sobre la estructura y los parámetros de los enlaces de atribución</Anchor>.

**Para generar un enlace de atribución,** sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#attribution-link-tab">estas instrucciones</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

La integración de costos a través de API no está disponible para este partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Los ingresos por publicidad no son compatibles actualmente con esta integración de partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres conceder a AdColony. Ten en cuenta que, aunque la atribución esté deshabilitada para AdColony, la pestaña de permisos está activa y puedes otorgar el control a AdColony.

Usa estos selectores para otorgarle permisos a una ad network para que maneje su propia configuración de tu aplicación:

### Permisos de ad network

* ***Permitir la configuración de la integración***: permite que el partner configure la pestaña de integración (excepto postbacks de eventos in-app).
* ***Permitir la configuración de postbacks de eventos in-app***: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña de integración.
* ***Permitir el acceso a tu reporte de retención***: solo para los propios datos de retención del partner.
* ***Permitir acceso a tus datos agregados de usuarios fieles*** - solo a los datos de usuarios fieles propios del partner
* ***Permitir acceso a tus datos agregados de eventos in-app**:* solo a los datos de eventos in-app propios del partner.
* ***Permitir acceso a tus datos agregados de ingresos***: solo a los datos de ingresos atribuidos al partner.
* ***Permitir el acceso a tu panel de control Protect360***: solo a los datos de Protect360 propios del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-adcolony=configuraci%C3%B3n-de-adcolony h_01HJR62VJZXTFPXYRMYT05EV1X=configuraci%C3%B3n-de-adcolony h_01HJR62VJZZZQRBHAA6FT8D6GY=integration-tab activate-partners=activar-los-partners h_01HJR62VJZQRBWFACANBJ6HG14=activar-los-partners general-settings=configuraci%C3%B3n-general h_01HJR62VJZFDKC4N7BC5P1TSZK=configuraci%C3%B3n-general enable-viewthrough-attribution=habilitar-la-atribuci%C3%B3n-por-impresiones h_01HJR62VJZEC4E5FZVCKWDXNEY=habilitar-la-atribuci%C3%B3n-por-impresiones default-postbacks=postbacks-predeterminados h_01HJR62VJZR34JMT4TM0YG1DC6=postbacks-predeterminados launch-postbacks=postbacks-de-lanzamiento h_01HJR62VJZJX57VMDNEQFKFB9C=postbacks-de-lanzamiento inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HJR62VJZJHHH4Q8P8ZERXVRM=configuraci%C3%B3n-de-eventos-in-app h_01HJR62VK0980EE3ZKYT2KFB5H=attribution-link-tab h_01HJR62VK0G62A2S3WTW49150C=cost-tab h_01HJR62VK0869W4K5R1JF7V0C4=ad-revenue-tab h_01HJR62VK0GMA3TTGPPS3ND64F=permissions-tab ad-network-permissions=permisos-de-ad-network h_01HJR62VK0AHRTPN92TGGCMC5D=permisos-de-ad-network" />
