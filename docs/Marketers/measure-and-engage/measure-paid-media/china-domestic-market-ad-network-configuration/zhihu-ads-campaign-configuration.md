---
title: Configuración de campañas de Zhihu Ads
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
  created_at: '2019-06-05T06:05:50Z'
  edited_at: '2026-09-17T00:26:41Z'
  id: 360001758338
  locale: es
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/es/articles/360001758338
---
> **De un vistazo:** Zhihu Ads es un partner integrado de ad network de AppsFlyer.

<div id="setting-up-zhihu-ads" />

## Configuración de Zhihu Ads

**Requisito previo:** una cuenta con el partner. Si no tienes una cuenta, contacta con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de partner > Marketplace** .  
   (**Para editar una integración existente:** Ve a la pestaña **Colaborar > Integraciones de partner > Integraciones activas** .)
2. Selecciona la aplicación correspondiente.
3. Busca el partner y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el selector **Activar partner**.   
   **Nota:** el selector **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas pertinentes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de partners</Anchor>.

La ventana de configuración de Zhihu Ads incluye 3 pestañas activas: integración, enlace de atribución y permisos. Haz clic en los elementos que aparecen a continuación para obtener más información sobre la configuración de las pestañas.

<div id="integration-tab" />

<Accordion title="Pestaña Integración">

<div id="activate-partner" />

### Activación de socios

En la **primera visita** aquí, deberás alternar a continuación. ACTIVA el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

<div id="general-settings" />

### Configuración general

**Habilitar la atribución por impresiones**

Activa esta opción si quieres atribuir las instalaciones view-through de Zhihu Ads. El control deslizante de la ventana de lookback view-through está disponible en la pestaña del enlace de atribución (se describe a continuación).

<div id="default-postbacks" />

### Postbacks predeterminados

<Image align="center" alt="mceclip2.png" src="https://files.readme.io/dbb58af826e66fda7a501fdb23bf5f0ded2415e295969472e04c958d3190310e-50899821656721.png" />

<div id="in-app-events-settings" />

### Configuración de eventos in-app

En esta sección puedes asignar tus eventos de AppsFlyer a Zhihu Ads mediante postbacks.

<Image align="center" alt="mceclip2.png" src="https://files.readme.io/39f3b95126da7107b2972b5811d0367d51191eed76cc6ddbef52ffb3a0c1e137-50900503184017.png" />

1. Activa los postbacks de eventos in-app.
2. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
3. Completa los siguientes parámetros:

| Nombre de parámetro | Nota |
| --- | --- |
| **Nombre de evento del SDK** | El nombre del evento tal como lo recibe AppsFlyer, ya sea del SDK integrado en tu aplicación o de eventos de servidor a servidor.  <br />**Consejo**: Si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| **Identificador de evento de partner** | El nombre único o ID de cada evento según lo define Zhihu Ads.  <br />Obtén el ID de evento correspondiente de Zhihu Ads e introdúcelo en el campo de texto. |
| **Enviar ingresos** | **Si esta opción no está marcada** - AppsFlyer envía al partner todos los parámetros del evento in-app enriquecido, excepto el parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Si está marcada** - AppsFlyer envía todos los parámetros, incluido el valor de ingresos (si existe en el evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que quieres enviar a Zhihu Ads para atribuir las campañas, los conjuntos de anuncios o incluso los anuncios individuales de Zhihu Ads. Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución generados para el partner.

<Image align="center" alt="mceclip1.png" src="https://files.readme.io/3f946bccf687826dd2e9ebc318e2510ee5bef5641e9cbfaa1f4b231089ebfee5-50900523405713.png" />

Esta pestaña se divide en distintas secciones:

<div id="attribution-link-parameters" />

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución en esta sección te permite realizar análisis en profundidad posteriormente. Puedes editar los parámetros ya definidos en el enlace de atribución, agregándolos junto con sus nuevos valores aquí.

* **Campaña** - añádela para comparar diferentes campañas de Zhihu Ads.  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios** - define nombres de conjuntos de anuncios para comparar diferentes conjuntos de anuncios dentro de campañas específicas de Zhihu Ads.  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre del anuncio** - define nombres de anuncios para comparar diferentes creatividades dentro de conjuntos de anuncios específicos de campañas específicas de Zhihu Ads.  
  **Parámetro de enlace de atribución:** af\_ad
* **ID de sitio** e **ID de subsitio** - configura el parámetro ID de sitio para atribuir instalaciones a publishers específicos. Si existen muchos publishers, te recomendamos limitar el número de IDs de sitio usados y utilizar el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder las limitaciones de ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor** - utiliza cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el Reporte de raw data, lo que los hace muy útiles para realizar la agregación o el filtrado de datos.  
  **Parámetros del enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

<Image align="center" alt="parámetros-del-enlace-de-atribución.png" src="https://files.readme.io/9cc0845f4492c981fd1db843cb82caf48aecc446fac7800829ee43f858f67e64-360002880417.png" />

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Para obtener más información sobre <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**la estructura y los parámetros de los enlaces de atribución de AppsFlyer**</Anchor>.

<div id="click-through-attribution" />

### Atribución por clics

Este control deslizante te permite establecer el **tiempo máximo del clic a la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de la ventana de lookback pueden atribuirse a Zhihu Ads.

**Parámetro del enlace de atribución:** af\_click\_lookback

Aquí encontrarás más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clic</Anchor>.

<Image align="center" alt="netease-click-through.png" src="https://files.readme.io/338f41569cafb8ebaf45075bf97711af4eb2fb15d25efd036d9873544729380d-50899846629521.png" />

<div id="click-attribution-link" />

### Enlace de atribución de clics

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a Zhihu Ads para que se active cuando los clientes potenciales hagan clic en el anuncio correspondiente.

<div id="view-through-attribution-lookback-window" />

### Ventana de lookback de atribución view-through

Este control deslizante te permite establecer el **tiempo máximo de la impresión a la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de esta ventana de lookback, tras la impresión de un anuncio, se atribuyen a Zhihu Ads, siempre que no haya habido ningún otro clic de anuncio relevante.

Puedes personalizar este valor para que sea de 1-23 horas o de 1-7 días.

**Parámetro del enlace de atribución:** af\_viewthrough\_lookback

Aquí encontrarás más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">atribución view-through</Anchor>.

<Image align="center" alt="" src="https://files.readme.io/2567e7dca91c14a345616e1eb7cb0de8d1a5de7d2f9e90174ffc648fd04510c8-360002234185.png" />

<div id="impressions-attribution-link" />

### Enlace de atribución de impresiones

El enlace de atribución de impresiones contiene datos similares a los del enlace de registro de clics, además de una ventana de lookback diferente. Envíalo a Zhihu Ads para que se active cuando se vea un anuncio correspondiente, normalmente durante 1 segundo o más.


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

En esta pestaña, puedes seleccionar los permisos que quieres otorgarle a Zhihu Ads, tanto si el partner actúa como ad network, agencia o ambas. Ten en cuenta que, incluso si la atribución está deshabilitada para Zhihu Ads, la pestaña de permisos está activa y puedes otorgarle el control a Zhihu Ads.

<Image align="center" alt="rtb_house-permissions-new.png" src="https://files.readme.io/645bdfcbb23d0ee5121a6261d5b17ca11a86209bcad2cfd9354e57c8ae281e83-50899852754449.png" />

<div id="ad-network-permissions" />

### Permisos para Redes de Publicidad

Utiliza estos selectores para otorgarle permisos a la red de publicidad para que gestione su propia configuración para tu aplicación:

* ***Permitir configurar la integración*** - permite que el partner configure la pestaña de integración (excepto los postback de eventos in-app)
* ***Permitir la configuración de postbacks de eventos in-app***: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña de integración.
* ***Permitir el acceso a tu reporte de retención***: solo para los propios datos de retención del partner.
* ***Permitir el acceso a tu panel de control Protect360***: solo a los datos de Protect360 propios del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-zhihu-ads=configuraci%C3%B3n-de-zhihu-ads h_01HKW6ZTB5WW8KHP9TDQGCMY01=configuraci%C3%B3n-de-zhihu-ads h_01HKW6ZTB6SGP5MCASKW4EJNYE=integration-tab activate-partner=activaci%C3%B3n-de-socios h_01HKW6ZTB633DTKTTT6P2DMZ2K=activaci%C3%B3n-de-socios general-settings=configuraci%C3%B3n-general h_01HKW6ZTB6X2EZ9DH0X8XGKWE8=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01HKW6ZTB63KZW3XE3YQQFPFBA=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HKW6ZTB65M8DXV21BWDF1RHK=configuraci%C3%B3n-de-eventos-in-app h_01HKW6ZTB6KKF60N9RSP8VWF7S=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HKW6ZTB62HDV9YM3W71H7FMQ=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n clickthrough-attribution=atribuci%C3%B3n-por-clics h_01HKW6ZTB6M3CTGFRF05S3QQ42=atribuci%C3%B3n-por-clics click-attribution-link=enlace-de-atribuci%C3%B3n-de-clics h_01HKW6ZTB6A2K925V5250TEX0F=enlace-de-atribuci%C3%B3n-de-clics viewthrough-attribution-lookback-window=ventana-de-lookback-de-atribuci%C3%B3n-view-through h_01HKW6ZTB6JSTQ9947YEP3BN4J=ventana-de-lookback-de-atribuci%C3%B3n-view-through impressions-attribution-link=enlace-de-atribuci%C3%B3n-de-impresiones h_01HKW6ZTB7RZEZD9P0N66NZEJG=enlace-de-atribuci%C3%B3n-de-impresiones h_01HKW6ZTB7HKKM3S0NPD8TBNMQ=cost-tab h_01HKW6ZTB7A117WNHQJ0N2V0KS=ad-revenue-tab h_01HKW6ZTB76WTKQNRF385K319K=permissions-tab ad-network-permissions=permisos-para-redes-de-publicidad h_01HKW6ZTB7PFHP0M25A4C6HEEJ=permisos-para-redes-de-publicidad" />
