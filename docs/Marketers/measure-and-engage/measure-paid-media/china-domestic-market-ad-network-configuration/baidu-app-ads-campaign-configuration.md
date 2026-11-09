---
title: Configuración de campañas de Baidu App Ads
metadata:
  keywords:
    - Baidu App Ads
    - Baidu
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
  created_at: '2017-06-18T07:40:30Z'
  edited_at: '2026-09-17T00:25:56Z'
  id: 115003044146
  locale: es
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/es/articles/115003044146
---
> **En resumen:** Baidu App Ads (Baitong), un partner integrado de ad network de AppsFlyer, es una de las plataformas más grandes de promoción y distribución de aplicaciones del mercado nacional de China, ya que integra el tráfico móvil de tiendas de aplicaciones (Baidu Mobile Assistant, Android Market, 91 Mobile Assistant, etc.), Baidu Mobile Search, Super App y Baidu Affiliates.

<div id="setting-up-baidu-app-ads-baitong" />

## Configuración de Baidu App Ads (Baitong)

**Requisito previo:** Una cuenta con el partner. Si no tienes una cuenta, ponte en contacto con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de partner > Marketplace** .  
   (**Para editar una integración existente:** Ve a la pestaña **Colaborar > Integraciones de partner > Integraciones activas** .)
2. Selecciona la aplicación correspondiente.
3. Busca el partner y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el selector **Activar partner**.   
   **Nota importante:** El selector **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación.

La ventana de configuración de Baidu App Ads incluye 3 pestañas activas: Integración, enlace de atribución y permisos. Haz clic en los elementos que aparecen a continuación para obtener más información sobre la configuración de las pestañas.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

<div id="activate-partner" />

### Activar socio

En la **primera visita** aquí, debes activar el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

<div id="default-postbacks" />

### Postbacks predeterminados

AppsFlyer puede enviar postbacks automáticos a Baidu App Ads (Baitong) después de las instalaciones y los re-engagements de los usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

La integración con Baidu Baitong Ads solo admite el evento de instalación para los postbacks predeterminados.

<Image align="center" alt="baidu-baitong-default-postback.png" src="https://files.readme.io/c464429db3eae2dac9fbc13df1a56090ef587cd386ed8214eabd21dac653a622-50900467293713.png" />

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que quieras enviar a Baidu App Ads (Baitong) para atribuir campañas, conjuntos de anuncios o incluso anuncios individuales de Baidu App Ads (Baitong). Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución generados para el partner.

Esta pestaña se divide en distintas secciones:

<div id="attribution-link-parameters" />

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución en esta sección te permite realizar análisis en profundidad posteriormente. Puedes editar los parámetros ya definidos en el enlace de atribución, agregándolos junto con sus nuevos valores aquí.

* **Campaña** - añádela para comparar distintas campañas en funcionamiento con Baidu App Ads（Baitong).  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios**: define nombres de conjuntos de anuncios para comparar distintos conjuntos de anuncios dentro de campañas específicas de Baidu App Ads（Baitong).  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre del anuncio**: define nombres de anuncios para comparar distintos creativos dentro de conjuntos de anuncios específicos de campañas específicas de Baidu App Ads（Baitong).  
  **Parámetro de enlace de atribución:** af\_ad
* **ID de sitio** e **ID de subsitio** - configura el parámetro ID de sitio para atribuir instalaciones a publishers específicos. Si hay muchos publishers, te recomendamos limitar el número de ID de sitio que usas y utilizar el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">superar las limitaciones del ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor**: usa cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el Reporte de raw data, lo que los hace muy útiles para realizar la agregación o el filtrado de datos.  
  **Parámetros del enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Para obtener más información, consulta <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**la estructura y los parámetros de los enlaces de atribución de AppsFlyer**</Anchor>.

<div id="click-through-attribution" />

### Atribución por clic

Este control deslizante te permite establecer el **tiempo máximo entre el clic y la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de la ventana de lookback pueden atribuirse a Baidu App Ads（Baitong).

**Parámetro del enlace de atribución:** af\_click\_lookback

Más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clic aquí</Anchor>.

<div id="click-attribution-link" />

### Haz clic en el enlace de atribución

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a Baidu App Ads（Baitong) para que se active cuando los clientes potenciales hagan clic en el anuncio correspondiente.

Pestaña de costos

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

En esta pestaña, puedes seleccionar los permisos que quieres otorgarle a RTB House, ya sea que el partner actúe como red de publicidad, agencia o ambas. Ten en cuenta que incluso si la atribución está deshabilitada para RTB House, la pestaña de permisos está activa y puedes otorgar el control a RTB House.

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

<div data-zendesk-anchors="setting-up-baidu-app-ads-baitong=configuraci%C3%B3n-de-baidu-app-ads-baitong h_01HKW6SB83X3G0CV5A8SNB6DSJ=configuraci%C3%B3n-de-baidu-app-ads-baitong h_01HKW6SB83NPWAQ0HKVJDMSXKR=integration-tab activate-partner=activar-socio h_01HKW6SB83QKQW6D8F72ENFDB1=activar-socio default-postbacks=postbacks-predeterminados h_01HKW6SB83XK3V4FT17PK0X5PZ=postbacks-predeterminados h_01HKW6SB83G06N2PWR760310XV=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HKW6SB83VTAYK08P42698YRR=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n clickthrough-attribution=atribuci%C3%B3n-por-clic h_01HKW6SB83R8X1PWPTWG528HPY=atribuci%C3%B3n-por-clic click-attribution-link=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HKW6SB84ZA8KXN7A7N9PEZ7X=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HKW6SB840JT24A8QTB6Z7N7T=cost-tab h_01HKW6SB84MV2RYRQQVPYMFFJ8=ad-revenue-tab h_01HKW6SB84XA73Y64M3S8D2V58=permissions-tab ad-network-permissions=permisos-de-ad-network h_01HKW6SB84Q2NWK0Z3YF7ZQ5QJ=permisos-de-ad-network" />
