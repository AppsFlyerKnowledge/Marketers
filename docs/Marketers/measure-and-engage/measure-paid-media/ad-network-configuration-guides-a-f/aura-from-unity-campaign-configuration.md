---
title: Configuración de la campaña de Aura from Unity
metadata:
  keywords:
    - Campaign
    - Advertisers
    - Agencies
    - aura
    - ironsource
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
  created_at: '2020-01-27T11:23:49Z'
  edited_at: '2026-08-12T12:13:07Z'
  id: 360005208578
  locale: es
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/es/articles/360005208578
---
> **Información general:** Aura from Unity, un partner integrado de ad network de AppsFlyer, es una plataforma que permite a los anunciantes conectar con los usuarios cuando configuran un dispositivo nuevo.

![aura_logo.png](https://files.readme.io/83bca93f3dfe8f6ce9bd74b9141b8c3b4dc01cfcf8f1904c0f992346beee5014-17313206447889.png)

<div id="aura-from-unity-integration-in-appsflyer" />

## Integración de Aura from Unity en AppsFlyer

**Requisito previo:** Antes de configurar la integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con él. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Para activar o editar la integración:**

1. **Para activarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Partner Marketplace**.  
   **Para editarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Integraciones activas**.
2. Selecciona la aplicación correspondiente.
3. Haz clic en **Configurar integración**.
4. En la **primera visita** aquí, deberás activar **Activar partner** para habilitar la configuración de los parámetros de integración. El selector debe estar activado mientras trabajes con el partner.  
    Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe en la sección a continuación. Para ver una descripción detallada del Encabezado de la ventana de configuración de partner, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aquí</Anchor>.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

Conéctate a Aura from Unity activando y configurando los parámetros en la pestaña Integración.

**Para configurar la integración**:

1. Habilita **Activate partner**.Sin embargo, asegúrate de crear plantillas separadas con el subdominio; no agregues manualmente el subdominio al ID de plantilla.
2. En **Configuración general**, activa o desactiva la **atribución view-through**:
   * [Predeterminado] **Habilitar**: actívalo para atribuir las instalaciones view-through a Aura from Unity. La ventana de lookback se configura en la pestaña **Enlace de atribución**.
   * **Deshabilitar**: las instalaciones view-through del partner no se atribuyen.
3. Se envían **postbacks predeterminados** a Aura from Unity para:
   * **Instalaciones**: se envían postbacks cada vez que un usuario instala la aplicación. Elige si quieres enviar postbacks de los usuarios atribuidos a Aura from Unity o de todos los usuarios, incluidas las instalaciones orgánicas.
   * **Instalaciones rechazadas**: con **Protect360**, se envían postbacks cuando se envía un <Anchor target="_blank" href="/partners/es/docs/rejected-attribution-postbacks-to-integrated-partners">rechaza una instalación por fraude</Anchor>. Solo se reportan los usuarios atribuidos a Aura from Unity.
4. **Configuración de eventos in-app**: para enviar postbacks, asigna los ID de tus eventos in-app a los ID in-app de Aura from Unity. Configura los parámetros de la siguiente manera:
   * Habilita **postbacks de eventos in-app**.
   * Opción de envío: selecciona si quieres enviar **Solo eventos atribuidos a este partner** o **Eventos atribuidos a cualquier partner**, incluidas las instalaciones orgánicas.
   * Haz clic en **Añadir evento** para agregar un evento de SDK a la lista. Completa los parámetros descritos en la siguiente tabla.

| Nombre de la configuración | Nota |
| --- | --- |
| Nombre de evento SDK | Nombre del evento recibido por AppsFlyer desde:<ul><li>SDK integrado en la aplicación</li><li>Eventos server-to-server (servidor a servidor)</li></ul>**Consejo:** si un evento necesario no aparece en la lista, realiza una instalación no orgánica en un dispositivo y vuelve a comprobarlo. |
| Identificador de evento de partner | Nombre o ID de evento único, tal como lo define Aura from Unity.<br /><br />Elige un nombre de evento (de la lista desplegable) que coincida lo más posible con el evento. |
| Enviar ingresos | [Predeterminado] **No habilitado:** envía todos los parámetros in-app a Aura from Unity, excepto el parámetro de ingresos (`af_revenue`).<br /><br />**Habilitado**: envía todos los parámetros in-app, incluido, cuando esté disponible, el importe de ingresos. |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Genera y guarda enlaces de atribución y envíalos al partner para que te atribuya campañas específicas, conjuntos de anuncios o anuncios únicos, tanto para campañas de UA como de retargeting. Puedes utilizar un enlace de plataforma única o <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">OneLink</Anchor>. <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">Aprende más sobre la estructura y los parámetros de los enlaces de atribución</Anchor>. **Para generar un enlace de atribución,** sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#attribution-link-tab">estas instrucciones</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

AppsFlyer obtiene los detalles de los costos por API. Consulta <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">la tabla de integración de costos de redes de publicidad</Anchor> para obtener más información sobre las dimensiones, métricas y funciones admitidas. **Nota**: Los datos de costos requieren una suscripción a ROI360.

**Para habilitar la API de costos**:

* Sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">estas instrucciones de integración</Anchor>.

<Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Visualiza el estado de tu API de costos</Anchor> y la última vez que AppsFlyer logró extraer los datos de costos coincidentes en el panel de control de estado de la integración de costos (e ingresos por publicidad) o en el panel de control de la red de publicidad individual. 

Para ver la lista completa de Partners que admiten datos de costo <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">haz clic aquí</Anchor>.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

La atribución de ingresos por anuncios no está disponible para este partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

Puedes dar permiso a Aura from Unity para ver información o configurar cambios en la integración. El tipo de permiso varía según la relación comercial (ad network/agencia de anuncios) que tengas con Aura from Unity.

**¡Atención!** Es posible dar permisos a Aura from Unity aunque no haya ninguna integración activa con ellos.

<div id="ad-network-permissions" />

<Accordion title="Permisos de ad network">

**Para habilitar los permisos de ad network**:

1. Activa los **permisos de ad network**.
2. Da acceso a los miembros del equipo de Aura from Unity a una o varias de las siguientes opciones:
   * **Permitir configurar la integración**: permite que el partner configure la pestaña de integración (excepto los postbacks de eventos in-app).
   * **Permitir configurar los postbacks de eventos in-app**: permite que el partner asigne los postbacks de eventos in-app a sí mismo en la pestaña de integración.
   * **Permitir el acceso a tu reporte de retención**: permite acceder solo a los datos de retención propios del partner.
   * **Permitir acceso a tus datos agregados de usuarios fieles**: permite acceder solo a los datos de usuarios fieles propios del partner.
   * **Permitir acceso a tus datos agregados de eventos in-app**: permite acceder solo a los datos de eventos in-app propios del partner.
   * **Permitir acceso a tus datos agregados de ingresos:** permite acceder solo a los datos de ingresos atribuidos al partner.
   * **Permitir la ingesta de gasto**: permite que el partner suba datos de gasto de anuncios para esta aplicación.
   * **Permitir el acceso a tu dashboard de Protect360**: solo a los datos propios de **Protect360** del partner si la función está habilitada para el anunciante.

</Accordion>

</Accordion>

<div data-zendesk-anchors="aura-integration-in-appsflyer=integraci%C3%B3n-de-aura-from-unity-en-appsflyer h_01HKW9GGARZY4X1FAA6BD89K5N=integraci%C3%B3n-de-aura-from-unity-en-appsflyer h_01HKW9GGAR9CWWYGRH6C1EMFVM=integration-tab h_01HKW9GGAR9CVKH192FN4P9YND=attribution-link-tab h_01HKW9GGARNCSQ0TAV69550BS8=cost-tab h_01HKW9GGAR0TET4Q5284NHFM7R=ad-revenue-tab h_01HKW9GGAR5ZTPA9R49WN5P7P4=permissions-tab h_01HKW9GGAREEN9YQ065D1ZX1AQ=ad-network-permissions" />
