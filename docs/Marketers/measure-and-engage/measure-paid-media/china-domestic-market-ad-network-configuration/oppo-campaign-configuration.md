---
title: Configuración de la campaña de OPPO
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2019-08-02T06:46:03Z'
  edited_at: '2026-09-17T00:26:14Z'
  id: 360002159158
  locale: es
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/es/articles/360002159158
---
> **De un vistazo:** OPPO es un partner integrado de ad network de AppsFlyer.

## Configuración de OPPO

**Requisito previo:** Una cuenta con el partner. Si no tienes una cuenta, ponte en contacto con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de partners > Marketplace** .  
   (**Para editar una integración existente:** ve a la pestaña **Colaborar > Integraciones de partners > Integraciones activas** .)
2. Selecciona la aplicación correspondiente.
3. Busca el partner y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el selector **Activar partner**.   
   **Nota importante:** El selector **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas pertinentes, como se describe a continuación.

La ventana de configuración de OPPO incluye 3 pestañas activas: Integración, Enlace de atribución y Permisos. Haz clic en los elementos que aparecen a continuación para obtener más información sobre la configuración de las pestañas.

<div id="integration-tab" />

<Accordion title="Pestaña Integración">

La integración con OPPO solo admite el evento de instalación en el postback predeterminado.

### Activación de socios

En la **primera visita**, deberás activar la opción siguiente. ACTIVA el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

### Postbacks predeterminados

![mceclip2.png](https://files.readme.io/dbb58af826e66fda7a501fdb23bf5f0ded2415e295969472e04c958d3190310e-50899821656721.png)

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que quieras enviar a OPPO para atribuir las campañas, los conjuntos de anuncios o incluso los anuncios individuales de OPPO. Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución generados para el partner.

Esta pestaña se divide en distintas secciones:

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución en esta sección te permite realizar análisis en profundidad posteriormente. Puedes editar los parámetros ya definidos en el enlace de atribución, agregándolos junto con sus nuevos valores aquí.

* **Campaña**: añádela para comparar diferentes campañas en ejecución con OPPO.  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios**: define nombres de conjuntos de anuncios para comparar diferentes conjuntos de anuncios dentro de campañas específicas de OPPO.  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre del anuncio**: define nombres de anuncios para comparar diferentes creativos dentro de conjuntos de anuncios específicos de campañas específicas de OPPO.  
  **Parámetro de enlace de atribución:** af\_ad
* **ID de sitio** e **ID de subsitio**: configura el parámetro ID de sitio para atribuir instalaciones a publishers específicos. Si existen muchos publishers, te recomendamos limitar el número de IDs de sitio usados y utilizar el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">superar las limitaciones del ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor**: utiliza cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el reporte de datos sin procesar, lo que los hace muy útiles para realizar la agregación o el filtrado de datos.  
  **Parámetros del enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

<Image alt="attribution-link-parameters.png" src="https://files.readme.io/9cc0845f4492c981fd1db843cb82caf48aecc446fac7800829ee43f858f67e64-360002880417.png" width="561px" />

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Para obtener más información sobre <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**la estructura y los parámetros del enlace de atribución de AppsFlyer**</Anchor>.

### Atribución por clics

Este control deslizante te permite establecer el **tiempo máximo desde el clic hasta la instalación**. Solo las instalaciones (primeras ejecuciones) que tengan lugar dentro de la ventana de lookback pueden atribuirse a OPPO.

**Parámetro del enlace de atribución:** af\_click\_lookback

Aquí encontrarás más información sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clic aquí</Anchor>.

![netease-click-through.png](https://files.readme.io/338f41569cafb8ebaf45075bf97711af4eb2fb15d25efd036d9873544729380d-50899846629521.png)

### Enlace de atribución

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a OPPO para que se active cuando los clientes potenciales hagan clic en el anuncio correspondiente.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña Costo">

Los datos de costos no son compatibles con la integración con este partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña Ingresos por publicidad">

Los ingresos por publicidad no se admiten en la integración con este partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña Permisos">

En esta pestaña, puedes seleccionar los permisos que quieres otorgarle a OPPO, tanto si el partner actúa como ad network, agencia o ambas. Ten en cuenta que, incluso si la atribución está deshabilitada para OPPO, la pestaña de permisos está activa y puedes otorgarle el control a OPPO.

![rtb_house-permissions-new.png](https://files.readme.io/645bdfcbb23d0ee5121a6261d5b17ca11a86209bcad2cfd9354e57c8ae281e83-50899852754449.png)

### Permisos para Redes de Publicidad

Utiliza estos selectores para otorgarle permisos a la red de publicidad para que gestione su propia configuración para tu aplicación:

* ***Permitir configurar la integración*** - permite que el partner configure la pestaña Integración (excepto los postbacks de eventos in-app)
* ***Permitir la configuración de postbacks de eventos in-app***: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña de integración.
* ***Permitir el acceso a tu reporte de retención***: solo para los propios datos de retención del partner.
* ***Permitir el acceso a tu panel de control Protect360***: solo a los datos de Protect360 propios del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-oppo=configuraci%C3%B3n-de-oppo h_01HKW6WR3NKYN9M2J8ZDNYF1ZC=configuraci%C3%B3n-de-oppo h_01HKW6WR3N3RH4GG5AHZ1TTG6V=integration-tab activate-partner=activaci%C3%B3n-de-socios h_01HKW6WR3NJM4XPPJDMPS04JKN=activaci%C3%B3n-de-socios default-postbacks=postbacks-predeterminados h_01HKW6WR3NDWFHVGERDNMS0REC=postbacks-predeterminados h_01HKW6WR3NAE4MNHMCPS2W36F2=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HKW6WR3P6TGT1NDR6DE2JV3B=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n clickthrough-attribution=atribuci%C3%B3n-por-clics h_01HKW6WR3P0NADPBZ51S4EYJV1=atribuci%C3%B3n-por-clics attribution-link=enlace-de-atribuci%C3%B3n h_01HKW6WR3P320PGSBHPH0SWQA6=enlace-de-atribuci%C3%B3n h_01HKW6WR3PBTZTWAPD5D7VXXNE=cost-tab h_01HKW6WR3P0299WKGCAM4PJHDR=ad-revenue-tab h_01HKW6WR3P55EE3YNGX8S164CS=permissions-tab ad-network-permissions=permisos-para-redes-de-publicidad h_01HKW6WR3PBC2PZ87RP91RQCFG=permisos-para-redes-de-publicidad" />
