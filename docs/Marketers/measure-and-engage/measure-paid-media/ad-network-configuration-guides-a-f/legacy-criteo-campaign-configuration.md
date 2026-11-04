---
title: '[Legacy] Configuración de campaña de Criteo'
deprecated: true
metadata:
  keywords:
    - Campaign
    - SDK
    - Configure
    - Criteo
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
  created_at: '2015-06-03T08:06:04Z'
  edited_at: '2026-09-08T00:22:50Z'
  id: 207033946
  locale: es
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/es/articles/207033946
---
> **De un vistazo:** Criteo (Legacy), un partner integrado de ad network de AppsFlyer, es una empresa de retargeting personalizado que trabaja con minoristas de Internet para mostrar anuncios de display online personalizados a consumidores que ya han visitado el sitio web del anunciante. Además de la atribución móvil basada en clics, Criteo (Legacy) también ofrece retargeting, que puedes registrar con AppsFlyer.

<div id="setting-up-criteo-legacy" />

## Configuración de Criteo (legacy)

**Requisito previo:** una cuenta con el Partners. Si no tienes una cuenta, ponte en contacto con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de Partners > Marketplace**.  
   (**Para editar una integración existente:** Ve a la pestaña **Colaborar > Integraciones de Partners > Integraciones activas**.)
2. Selecciona la aplicación correspondiente.
3. Busca el Partners y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el selector **Activar Partners**.   
   **Nota:** El selector **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de Partners</Anchor>

La ventana de configuración de Criteo (Legacy) incluye 4 pestañas: Integración, Enlace de atribución, Enriquecimiento de datos y Permisos. Haz clic en los elementos que aparecen a continuación para obtener más información sobre la configuración de las pestañas.

Para ver una descripción detallada del Partner Configuration Window Header, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aquí</Anchor>.

<div id="tip" />

> 👍 **Consejo**
>
> * El paso de <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#d-general-settings">Configuración general</Anchor> en la pestaña de Integración es **obligatorio** para todos los partners.
> * Todos los demás pasos son descriptivos u **opcionales**.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

<div id="activate-partners" />

### Activar los partners

En la **primera visita** aquí, debes activar el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El activador debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

<div id="note" />

> 📘 **Nota:**
>
> Como red de TODAS las instalaciones, Criteo (Legacy) prefiere recibir postbacks de todas las nuevas instalaciones de tu aplicación desde CUALQUIER fuente, incluidas las orgánicas. Se recomienda seleccionar **Eventos atribuidos a cualquier partner** para enviar todos los postbacks de instalación a Criteo (Legacy).

<div id="default-postbacks" />

### Postbacks predeterminados

Envía postbacks automáticos a Criteo (Legacy) después de las instalaciones y re-engagements de los usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

Selecciona **Solo eventos atribuidos a este partner** para eventos provenientes solo de usuarios atribuidos a Criteo (Legacy).  
Selecciona **Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada a Criteo (Legacy).

<div id="in-app-events-settings" />

### Configuración de eventos in-app

En esta sección, puedes asignar tus eventos de AppsFlyer con Criteo (Legacy) mediante postbacks.

1. Activa los Postbacks de eventos in-app con el selector.
2. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que provienen **únicamente** de usuarios atribuidos a este partner.  
    **- Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada al partner.
3. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
4. Completa los siguientes parámetros:

| Nombre de parámetro | Nota |
| --- | --- |
| **Nombre de evento del SDK** | El nombre del evento tal como lo recibe AppsFlyer, ya sea del SDK integrado en tu aplicación o de eventos de servidor a servidor.  <br />**Consejo**: Si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| **Identificador de evento de partner** | El nombre o ID único de cada evento según lo define Criteo (Legacy).  <br />Obtén el ID de evento correspondiente de Criteo (Legacy) e introdúcelo en el campo de texto. |
| **Enviar ingresos** | **Si esta opción no está marcada**: se envían al partner todos los parámetros del evento in-app enriquecido, con excepción del parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Si está marcada**: AppsFlyer envía todos los parámetros, incluido el de valor correspondiente a los ingresos (si existe en el evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que quieras enviar a Criteo (Legacy) para atribuir las campañas, los conjuntos de anuncios o los anuncios individuales de Criteo (Legacy). Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución generados para el partner.

Esta pestaña se divide en distintas secciones:

<div id="attribution-link-parameters" />

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución en esta sección te permite realizar análisis en profundidad posteriormente. Puedes editar los parámetros ya definidos en el enlace de atribución, agregándolos junto con sus nuevos valores aquí.

* **Campaña**: añádela para comparar diferentes campañas en funcionamiento con Criteo (Legacy).  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios**: define nombres de conjunto de anuncios para comparar diferentes conjuntos de anuncios dentro de campañas específicas de Criteo (Legacy).  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre del anuncio**: define nombres de anuncios para comparar diferentes creatividades dentro de conjuntos de anuncios específicos en campañas específicas de Criteo (Legacy).  
  **Parámetro de enlace de atribución:** af\_ad
* **ID de sitio** e **ID de subsitio**: configura el parámetro ID de sitio para atribuir instalaciones a publishers específicos. Si existen muchos publishers, te recomendamos limitar el número de ID de sitio utilizados y usar el parámetro de ID de sub-sitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder las limitaciones de ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor** - usa cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el Reporte de raw data, lo que los hace muy útiles para realizar la agregación o el filtrado de datos.  
  **Parámetros del enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Para obtener más información sobre <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**la estructura y los parámetros de los enlaces de atribución de AppsFlyer**</Anchor>.

<div id="retargeting-settings" />

### Configuraciones de retargeting

Cuando esta opción está habilitada, AppsFlyer reconoce un enlace como un enlace de atribución de <Anchor target="_blank" href="/marketers/es/docs/retargeting-attribution-guide">retargeting</Anchor>, en lugar de un enlace de adquisición de usuarios, al añadir `&is_retargeting=true` al enlace de registro de clics. Ten en cuenta que actualmente el retargeting solo es compatible con la atribución por clic y no con la atribución view-through.  
**Parámetro del enlace de atribución:** is\_retargeting.

Cuando el retargeting está habilitado, se muestra la siguiente configuración.

1. Enlace estándar vs. OneLink

Selecciona la opción ***enlace de atribución estándar*** si:

* No necesitas un enlace profundo con la URL o
* Planea utilizar solo <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">esquemas de URI</Anchor> para Deep Linking

selecciona ***Usar OneLink*** para:

* Utilizar un solo enlace para aplicaciones de Android y iOS, o
* Establecer enlaces profundos empleando enlaces universales o de aplicaciones.

Ten en cuenta que, si seleccionas OneLink, el enlace de registro de clics cambia de un enlace específico de la aplicación a una <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">URL de OneLink</Anchor>.

2. URL de deep link

Utiliza este campo si el enlace está pensado para dirigir a los usuarios mediante deep linking a cualquier actividad específica dentro de tu aplicación.  
**Parámetro del enlace de atribución:** af\_dp  
Puedes encontrar más información sobre la solución de AppsFlyer para Deep Linking en esta <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">guía.</Anchor>

3. Ventana de recaptación

Defina el plazo posterior al re-engagement, durante el cual los eventos in-app del usuario se atribuyen a la fuente de medios de redireccionamiento. Puede establecer el valor en días (1-90), horas (hasta 23) o incluso durante toda la vida.

**Parámetro del enlace de atribución:** af\_reengagement\_window

<div id="click-through-attribution" />

### Atribución por clic

Este control deslizante te permite establecer el **tiempo máximo desde el clic hasta la instalación**. Solo las instalaciones (primeros inicios) que tengan lugar dentro de la ventana de lookback pueden atribuirse a Criteo (Legacy).

**Parámetro del enlace de atribución:** af\_click\_lookback

Más información sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clic aquí</Anchor>.

<div id="click-attribution-link" />

### Haz clic en el enlace de atribución

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a Criteo (Legacy) para que se active cuando los leads hagan clic en el anuncio correspondiente.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

Los datos de coste mediante integración de API no están disponibles para este partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres conceder a Criteo (Legacy), independientemente de si el partner actúa como ad network, agencia o ambos. Ten en cuenta que, aunque la atribución esté deshabilitada para Criteo (Legacy), la pestaña de permisos está activa y puedes conceder el control a Criteo (Legacy).

**Permisos de ad network**

Usa estos selectores para otorgarle permisos a una ad network para que maneje su propia configuración de tu aplicación:

* ***Permitir la configuración de la integración***: permite que el partner configure la pestaña de integración (excepto postbacks de eventos in-app).
* ***Permitir la configuración de postbacks de eventos in-app***: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña de integración.
* ***Permitir el acceso a tu reporte de retención***: solo para los propios datos de retención del partner.
* ***Permitir acceso a tus datos agregados de usuarios fieles***: solo a los datos de usuarios fieles propios del partner.
* ***Permitir acceso a tus datos agregados de eventos in-app**:* solo a los datos de eventos in-app propios del partner.
* ***Permitir el acceso a tus datos agregados de ingresos*a** - solo a los datos de ingresos atribuidos al partner
* ***Permitir el acceso a tu panel de control Protect360***: solo a los datos de Protect360 propios del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

<div id="agency-permissions" />

### Permisos de la agencia

Utiliza estos selectores para otorgar permisos a una agencia para que gestione su propia configuración para tu aplicación:

* ***Selector principal*** - Actívalo para mostrar las opciones de permisos de la agencia
* ***Permitir la configuración de postbacks de eventos in-app*** - permite que la agencia configure la asignación de postbacks de eventos in-app a sí misma en la pestaña de integración
* ***Permitir el acceso a tu reporte de retención*** - solo a los propios datos de retención de la agencia
* ***Permitir el acceso a datos agregados orgánicos.***
* ***Permitir configurar postbacks de eventos in-app*** - permite que la agencia configure la asignación de postbacks de eventos in-app para sí misma en la pestaña de Integración

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permisos-de-la-agencia">permisos a las agencias</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-criteo-legacy=configuraci%C3%B3n-de-criteo-legacy h_01HKWB5RYT5Y39MWXD6F57T4MN=configuraci%C3%B3n-de-criteo-legacy h_01HKWB5RYT26M2R3HMG35A51GA=consejo h_01HKWB5RYV88ATKSS55B29GT6F=integration-tab activate-partners=activar-los-partners h_01HKWB5RYVSMPRK7RD6QN8BANB=activar-los-partners h_01HKWB5RYVSK56GNW4805XDFCT=nota default-postbacks=postbacks-predeterminados h_01HKWB5RYV68B5XWQA5D9W4ZM9=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HKWB5RYVCPM15F8DWBZ3BEMZ=configuraci%C3%B3n-de-eventos-in-app h_01HKWB5RYV9TKBY8V3R4N8FWNM=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HKWB5RYVKXJT3MFGS7A8EKB9=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n retargeting-settings=configuraciones-de-retargeting h_01HKWB5RYVYMY772BDY4Z83N84=configuraciones-de-retargeting clickthrough-attribution=atribuci%C3%B3n-por-clic h_01HKWB5RYV6Z028TM6YF0X6PWQ=atribuci%C3%B3n-por-clic click-attribution-link=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HKWB5RYVGK3DT0AB89YPZS22=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HKWB5RYVZ367Y3GY329608G3=cost-tab h_01HKWB5RYVNTRC44XVZ3H7M2H5=permissions-tab agency-permissions=permisos-de-la-agencia h_01HKWB5RYV6MSCFCB387342NJ4=permisos-de-la-agencia" />
