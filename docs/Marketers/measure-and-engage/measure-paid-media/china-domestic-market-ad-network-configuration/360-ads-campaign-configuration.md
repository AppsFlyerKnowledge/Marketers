---
title: Configuración de campañas de 360 Ads
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
  created_at: '2019-08-02T05:47:59Z'
  edited_at: '2026-09-17T00:25:54Z'
  id: 360002152957
  locale: es
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/es/articles/360002152957
---
> **De un vistazo:** 360 Ads es un partner integrado de AppsFlyer para ad network.

<div id="setting-up-360-ads" />

## Configuración de 360 Ads

**Requisito previo:** Una cuenta con el partner. Si no tienes una cuenta, ponte en contacto con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de partner > Marketplace** .  
   (**Para editar una integración existente:** Ve a la pestaña **Colaborar > Integraciones de partner > Integraciones activas** .)
2. Selecciona la aplicación correspondiente.
3. Busca el partner y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el selector **Activar partner**.   
   **Nota importante:** El selector **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas pertinentes, como se describe a continuación.

La ventana de configuración de 360 Ads incluye 3 pestañas activas: Integración, Enlace de atribución y Permisos. Haz clic en los elementos que aparecen a continuación para obtener más información sobre la configuración de las pestañas.

<div id="integration-tab" />

<Accordion title="Pestaña Integración">

<div id="activate-partner" />

### Activación de socios

En la **primera visita** aquí, deberás alternar a continuación. ACTIVA el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

<div id="general-settings" />

### Configuración general

**Habilitar la atribución por impresiones**

Cambia esta opción a ON si quieres atribuir instalaciones view-through de 360 Ads. El control deslizante de la ventana de lookback view-through está disponible en la pestaña del enlace de atribución (se describe a continuación).

<div id="default-postbacks" />

### Postbacks predeterminados

<Image align="center" alt="mceclip2.png" src="https://files.readme.io/dbb58af826e66fda7a501fdb23bf5f0ded2415e295969472e04c958d3190310e-50899821656721.png" width="506px" />

<div id="in-app-events-settings" />

### Configuración de eventos in-app

En esta sección puedes asignar tus eventos de AppsFlyer a 360 Ads mediante postbacks.

**Clave y secreto**

360 Ads se conecta con AppsFlyer mediante una clave y un secreto únicos. Si aún no tienes la clave y el secreto, debes obtenerlos de 360 Ads para continuar con la integración.

<Image align="center" alt="mceclip2.png" src="https://files.readme.io/0d52eb93f8cba6ec283cdf844cc6fa891499884de0c93689653f4d356078dd85-50900375408017.png" width="412px" />

1. Configura aquí la clave y el secreto de 360 Ads
2. Activa los postbacks de eventos in-app.
3. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
4. Completa los siguientes parámetros:

| Nombre de parámetro | Nota |
| --- | --- |
| **Nombre de evento del SDK** | El nombre del evento tal como lo recibe AppsFlyer, ya sea del SDK integrado en tu aplicación o de eventos de servidor a servidor.  <br />**Consejo**: Si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| **Identificador de evento de partner** | El nombre o ID único de cada evento según lo define 360 Ads.  <br />Obtén el ID de evento correspondiente de 360 Ads y configúralo en el campo de texto. |
| **Enviar ingresos** | **Si esta opción no está marcada**: AppsFlyer envía al partner todos los parámetros del evento in-app enriquecido, excepto el parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Si está marcada**: AppsFlyer envía todos los parámetros, incluido el valor de ingresos (si existe en el evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que quieras enviar a 360 Ads para atribuir campañas, conjuntos de anuncios o incluso anuncios individuales de 360 Ads. Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución generados para el partner.

Esta pestaña se divide en distintas secciones:

<div id="attribution-link-parameters" />

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución en esta sección te permite realizar análisis en profundidad posteriormente. Puedes editar los parámetros ya definidos en el enlace de atribución, agregándolos junto con sus nuevos valores aquí.

* **Campaña**: añádela para comparar distintas campañas en funcionamiento con 360 Ads.  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios**: define nombres de conjunto de anuncios para comparar diferentes conjuntos de anuncios dentro de campañas específicas de 360 Ads.  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre del anuncio**: define nombres de anuncios para comparar distintos creativos dentro de conjuntos de anuncios específicos de campañas específicas de 360 Ads.  
  **Parámetro de enlace de atribución:** af\_ad
* **ID de sitio** e **ID de subsitio** - configura el parámetro ID de sitio para atribuir las instalaciones a publishers específicos. Si existen muchos publishers, te recomendamos limitar el número de IDs de sitio usados y utilizar el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder las limitaciones del ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor**: utiliza cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el reporte de raw data, lo que los hace muy útiles para realizar la agregación o el filtrado de datos.  
  **Parámetros del enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

<Image align="center" alt="attribution-link-parameters.png" src="https://files.readme.io/9cc0845f4492c981fd1db843cb82caf48aecc446fac7800829ee43f858f67e64-360002880417.png" width="588px" />

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Para obtener más información sobre <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**la estructura y los parámetros de los enlaces de atribución de AppsFlyer**</Anchor>.

<div id="click-through-attribution" />

### Atribución por clics

Este control deslizante te permite establecer el **tiempo máximo del clic a la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de la ventana de lookback pueden atribuirse a 360 Ads.

**Parámetro del enlace de atribución:** af\_click\_lookback

Más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clic aquí</Anchor>.

<Image align="center" alt="netease-click-through.png" src="https://files.readme.io/338f41569cafb8ebaf45075bf97711af4eb2fb15d25efd036d9873544729380d-50899846629521.png" />

<div id="attribution-link" />

### Enlace de atribución

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a 360 Ads para que se active cuando los leads hagan clic en un anuncio correspondiente. 

<div id="view-through-attribution-lookback-window" />

### Ventana de lookback de atribución view-through

Este control deslizante te permite establecer el **tiempo máximo de la impresión a la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de esta ventana de lookback, tras la impresión de un anuncio, se atribuyen a 360 Ads, siempre que no haya habido ningún otro clic relevante en el anuncio.

Puedes personalizar este valor para que sea de 1-23 horas o de 1-7 días.

**Parámetro del enlace de atribución:** af\_viewthrough\_lookback

Más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">atribución por impresiones aquí</Anchor>.

<Image align="center" alt="" src="https://files.readme.io/2567e7dca91c14a345616e1eb7cb0de8d1a5de7d2f9e90174ffc648fd04510c8-360002234185.png" />

<div id="impressions-attribution-link" />

### Enlace de atribución de impresiones

El enlace de atribución de impresiones contiene datos similares a los del enlace de registro de clics, además de una ventana de lookback diferente. Envíalo a 360 Ads para que se active cuando se vea un anuncio correspondiente, normalmente durante 1 segundo o más.

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

En esta pestaña, puedes seleccionar los permisos que quieres otorgarle a 360 Ads, tanto si el partner actúa como ad network, agencia o incluso ambas cosas. Ten en cuenta que, incluso si la atribución está deshabilitada para 360 Ads, la pestaña de permisos está activa y puedes otorgarle el control a 360 Ads.

<Image align="center" alt="rtb_house-permissions-new.png" src="https://files.readme.io/645bdfcbb23d0ee5121a6261d5b17ca11a86209bcad2cfd9354e57c8ae281e83-50899852754449.png" />

<div id="ad-network-permissions" />

### Permisos para Redes de Publicidad

Utiliza estos selectores para otorgarle permisos a la red de publicidad para que gestione su propia configuración para tu aplicación:

* ***Permitir configurar la integración*** - permite que el partner configure la pestaña de integración (excepto los postbacks de eventos in-app)
* ***Permitir la configuración de postbacks de eventos in-app***: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña de integración.
* ***Permitir el acceso a tu reporte de retención***: solo para los propios datos de retención del partner.
* ***Permitir el acceso a tu panel de control Protect360***: solo a los datos de Protect360 propios del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-360-ads=configuraci%C3%B3n-de-360-ads h_01HKW6S90SZY55XRP6YN8B3QTJ=configuraci%C3%B3n-de-360-ads h_01HKW6S90TSD0WKZ4ZT7701DX7=integration-tab activate-partner=activaci%C3%B3n-de-socios h_01HKW6S90TVP4K2XFP5EEFWDC4=activaci%C3%B3n-de-socios general-settings=configuraci%C3%B3n-general h_01HKW6S90T9ABAX8E7DK02N538=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01HKW6S90TEJ68RG9B3S5KD63Y=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HKW6S90TN3J07GXS8C7NTETR=configuraci%C3%B3n-de-eventos-in-app h_01HKW6S90T7P66TMWFA4T4C350=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HKW6S90TCMRFHFXBEJBCP9C6=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n clickthrough-attribution=atribuci%C3%B3n-por-clics h_01HKW6S90TQW75T0HCCC38ETWB=atribuci%C3%B3n-por-clics attribution-link=enlace-de-atribuci%C3%B3n h_01HKW6S90T0SVWCEV905DC2VTW=enlace-de-atribuci%C3%B3n viewthrough-attribution-lookback-window=ventana-de-lookback-de-atribuci%C3%B3n-view-through h_01HKW6S90T813FYKMGDAF935YJ=ventana-de-lookback-de-atribuci%C3%B3n-view-through impressions-attribution-link=enlace-de-atribuci%C3%B3n-de-impresiones h_01HKW6S90T4TS5EHK8M7E4QV8G=enlace-de-atribuci%C3%B3n-de-impresiones h_01HKW6S90TXR07SQJW3DTD9VS4=cost-tab h_01HKW6S90T489CVTQXQPRM0M8B=ad-revenue-tab h_01HKW6S90VWKHEWNY7AYKRWGBH=permissions-tab ad-network-permissions=permisos-para-redes-de-publicidad h_01HKW6S90V1ZV766FZ20EKJR0N=permisos-para-redes-de-publicidad" />
