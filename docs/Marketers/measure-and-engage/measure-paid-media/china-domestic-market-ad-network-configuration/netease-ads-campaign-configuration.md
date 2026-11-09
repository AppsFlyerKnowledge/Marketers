---
title: Configuración de campañas de Netease Ads
metadata:
  keywords:
    - netease ads
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
  created_at: '2017-06-18T06:59:42Z'
  edited_at: '2026-09-17T00:26:11Z'
  id: 115003044126
  locale: es
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/es/articles/115003044126
---
> **De un vistazo:** Netease, partner integrado de AppsFlyer, es un proveedor líder de servicios publicitarios en el mercado chino.

<div id="setting-up-netease" />

## Configuración de Netease

**Requisito previo:** Una cuenta con el partner. Si no tienes una cuenta, contacta con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de partner > Marketplace** .  
   (**Para editar una integración existente:** Ve a la pestaña **Colaborar > Integraciones de partner > Integraciones activas** .)
2. Selecciona la aplicación correspondiente.
3. Busca el partner y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el selector **Activar partner**.   
   **Nota importante:** El selector **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación.

La ventana de configuración de Netease incluye 3 pestañas activas: Integración, enlace de atribución y permisos. Haz clic en los elementos que aparecen a continuación para obtener más información sobre la configuración de las pestañas.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La integración con Netease Ads solo admite el evento de instalación en el postback predeterminado.

<div id="activate-partner" />

### Activar socio

En la **primera visita** aquí, debes activar el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

<div id="default-postbacks" />

### Postbacks predeterminados

<Image align="center" alt="netease-default-postback.png" src="https://files.readme.io/0b1db2d0f9e772ad7459c8d28d46cf92bb26501da47b9e5f2f3dd4951a469470-50900350199825.png" width="513px" />

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que quieras enviar a Netease para atribuir las campañas, los conjuntos de anuncios o incluso los anuncios individuales de Netease. Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución generados para el partner.

Esta pestaña se divide en distintas secciones:

<div id="attribution-link-parameters" />

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución en esta sección te permite realizar análisis en profundidad posteriormente. Puedes editar los parámetros ya definidos en el enlace de atribución, agregándolos junto con sus nuevos valores aquí.

* **Campaña** - añádela para comparar diferentes campañas de Netease en funcionamiento.  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios** - define nombres de conjunto de anuncios para comparar diferentes conjuntos de anuncios dentro de campañas específicas de Netease.  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre del anuncio** - define nombres de anuncios para comparar diferentes creativos dentro de conjuntos de anuncios específicos de campañas específicas de Netease.  
  **Parámetro de enlace de atribución:** af\_ad
* **ID de sitio** e **ID de subsitio** - configura el parámetro ID de sitio para atribuir las instalaciones a publishers específicos. Si existen muchos publishers, te sugerimos que limites la cantidad de IDs de sitio usados y utilices el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder las limitaciones de ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor** - utiliza cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el Reporte de raw data, lo que los hace muy útiles para realizar la agregación o el filtrado de datos.  
  **Parámetros de enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

<Image align="center" alt="attribution-link-parameters.png" src="https://files.readme.io/9cc0845f4492c981fd1db843cb82caf48aecc446fac7800829ee43f858f67e64-360002880417.png" />

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Para obtener más información sobre <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**Estructura y parámetros del enlace de atribución de AppsFlyer**</Anchor>.

<div id="click-through-attribution" />

### Atribución por clic

Este control deslizante te permite establecer el **tiempo máximo desde el clic hasta la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de la ventana de lookback pueden atribuirse a Netease.

**Parámetro del enlace de atribución:** af\_click\_lookback

Más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clic aquí</Anchor>.

<Image align="center" alt="netease-click-through.png" src="https://files.readme.io/338f41569cafb8ebaf45075bf97711af4eb2fb15d25efd036d9873544729380d-50899846629521.png" />

<div id="click-attribution-link" />

### Haz clic en el enlace de atribución

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a Netease para que se active cuando los clientes potenciales hagan clic en el anuncio correspondiente.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

Los datos de costos no son compatibles con la integración con este partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Los ingresos por publicidad no se admiten en la integración con este partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres otorgarle a RTB House, tanto si el partner actúa como ad network, agencia o ambas cosas. Ten en cuenta que incluso si la atribución está deshabilitada para RTB House, la pestaña de permisos está activa y puedes otorgar el control a RTB House.

<Image align="center" alt="rtb_house-permissions-new.png" src="https://files.readme.io/645bdfcbb23d0ee5121a6261d5b17ca11a86209bcad2cfd9354e57c8ae281e83-50899852754449.png" />

<div id="ad-network-permissions" />

### Permisos de ad network

Utiliza estos selectores para otorgarle permisos a la red de publicidad para que gestione su propia configuración para tu aplicación:

* ***Permitir la configuración de la integración***: permite que el partner configure la pestaña de integración (excepto postbacks de eventos in-app).
* ***Permitir la configuración de postbacks de eventos in-app***: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña de integración.
* ***Permitir el acceso a tu reporte de retención***: solo para los propios datos de retención del partner.
* ***Permitir acceso a tus datos agregados de usuarios fieles***: solo a los datos de usuarios fieles propios del partner.
* ***Permitir acceso a tus datos agregados de eventos in-app**:* solo a los datos de eventos in-app propios del partner.
* ***Permitir acceso a tus datos agregados de ingresos*a** - solo a los datos de ingresos atribuidos al partner
* ***Permitir el acceso a tu panel de control Protect360***: solo a los datos de Protect360 propios del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-netease=configuraci%C3%B3n-de-netease h_01HKW6VWQKD2K6REG5MN6274MD=configuraci%C3%B3n-de-netease h_01HKW6VWQKNZ067ASNH3W5MK2H=integration-tab activate-partner=activar-socio h_01HKW6VWQKVN9NKJ67HEJXRBZJ=activar-socio default-postbacks=postbacks-predeterminados h_01HKW6VWQKJGFGER02BFXNV88C=postbacks-predeterminados h_01HKW6VWQKK3P5TE72MQRV0TPA=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HKW6VWQKEB8DK5YN4E976SQV=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n clickthrough-attribution=atribuci%C3%B3n-por-clic h_01HKW6VWQKNNE4Y46QWR8VZHP0=atribuci%C3%B3n-por-clic click-attribution-link=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HKW6VWQKSW8NYCK7VCQ2PRHW=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HKW6VWQKBRWE8RHFTPF9JADE=cost-tab h_01HKW6VWQMJFES084XN3Z52GC2=ad-revenue-tab h_01HKW6VWQMJ419903HKE1C0GRD=permissions-tab ad-network-permissions=permisos-de-ad-network h_01HKW6VWQMDR1K426AVZ25Z7VH=permisos-de-ad-network" />
