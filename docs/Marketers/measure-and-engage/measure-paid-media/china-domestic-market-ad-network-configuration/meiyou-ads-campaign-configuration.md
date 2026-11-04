---
title: Configuración de campañas de Meiyou Ads
metadata:
  keywords:
    - integrated partner
    - Advertisers
    - China
    - meiyou
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2019-08-01T03:26:18Z'
  edited_at: '2026-09-17T00:26:09Z'
  id: 360002141597
  locale: es
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/es/articles/360002141597
---
> **De un vistazo:** Meiyou Ads es un partner integrado de ad network de AppsFlyer.

<div id="setting-up-meiyou-ads" />

## Configuración de Meiyou Ads

**Requisito previo:** Una cuenta con el partner. Si no tienes una cuenta, ponte en contacto con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de partner > Marketplace** .  
   (**Para editar una integración existente:** Ve a la pestaña **Colaborar > Integraciones de partner > Integraciones activas** .)
2. Selecciona la aplicación correspondiente.
3. Busca el partner y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el selector **Activar partner**.   
   **Nota importante:** El selector **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Más información</Anchor>
5. Completa la configuración utilizando las pestañas pertinentes, como se describe a continuación.

La ventana de configuración de Meiyou Ads incluye 3 pestañas activas: Integración, Enlace de atribución y Permisos. Haz clic en los elementos que aparecen a continuación para obtener más información sobre la configuración de las pestañas.

<div id="integration-tab" />

<Accordion title="Pestaña Integración">

<div id="activate-partner" />

### Activación de socios

En la **primera visita** aquí, deberás alternar a continuación. ACTIVA el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

<div id="general-settings" />

### Configuración general

Meiyou Ads se conecta con AppsFlyer mediante una **Key** única. Si aún no tienes la clave, debes obtenerla de Meiyou Ads para continuar con la integración.

![mceclip3.png](https://files.readme.io/451f74c0a6b45926f89a3f2a5d04b6ef240184c4862b576bee0d0a2b7a832f30-50900150950417.png)

**Habilitar la atribución por impresiones**

Cambia esta opción a ON si quieres atribuir instalaciones view-through de Meiyou Ads. El control deslizante de la ventana retrospectiva por impresiones está disponible en la pestaña del enlace de atribución (se describe a continuación).

<div id="default-postbacks" />

### Postbacks predeterminados

<Image alt="mceclip2.png" src="https://files.readme.io/dbb58af826e66fda7a501fdb23bf5f0ded2415e295969472e04c958d3190310e-50899821656721.png" width="548px" />

<div id="in-app-events-settings" />

### Configuración de eventos in-app

En esta sección puedes asignar tus eventos de AppsFlyer a Meiyou Ads mediante postbacks.

**Clave**

Meiyou Ads se conecta con AppsFlyer mediante una clave única. Si aún no tienes la clave, debes obtenerla de Meiyou Ads para continuar con la integración.

<Image alt="mceclip1.png" src="https://files.readme.io/32b1c68531c7aa752514f9b1c13c4438cddef2e93d2ca04ab287d46acecda15e-50900150956305.png" width="661px" />

1. Configura aquí la clave de Meiyou Ads
2. Activa los postbacks de eventos in-app.
3. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
4. Completa los siguientes parámetros:

| Nombre de parámetro | Nota |
| --- | --- |
| **Nombre de evento del SDK** | El nombre del evento tal como lo recibe AppsFlyer, ya sea del SDK integrado en tu aplicación o de eventos de servidor a servidor.  <br />**Consejo**: Si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| **Identificador de evento de partner** | El nombre o ID único de cada evento según lo define Meiyou Ads.  <br />Obtén el ID de evento correspondiente de Meiyou Ads y configúralo en el campo de texto. |
| **Enviar ingresos** | **Si esta opción no está marcada**: AppsFlyer envía al partner todos los parámetros del evento in-app enriquecido, con excepción del parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Si está marcada**: AppsFlyer envía todos los parámetros, incluido el valor de ingresos (si existe en el evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que quieras enviar a Meiyou Ads para atribuir campañas, conjuntos de anuncios o incluso anuncios individuales de Meiyou Ads. Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución generados para el partner.

![mceclip2.png](https://files.readme.io/3a9b086aa1a76dc64289a512eec56885d108dce5c2778580fc0b2962f00c8a95-50900150957201.png)

Esta pestaña se divide en distintas secciones:

<div id="attribution-link-parameters" />

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución en esta sección te permite realizar análisis en profundidad posteriormente. Puedes editar los parámetros ya definidos en el enlace de atribución, agregándolos junto con sus nuevos valores aquí.

* **Campaña**: añádela para comparar distintas campañas en funcionamiento con Meiyou Ads.  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios**: define nombres de conjunto de anuncios para comparar diferentes conjuntos de anuncios dentro de campañas específicas de Meiyou Ads.  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre del anuncio** - define nombres de conjuntos de anuncios para comparar distintos creativos dentro de conjuntos de anuncios específicos de campañas específicas de Meiyou Ads.  
  **Parámetro del enlace de atribución:** af\_ad
* **ID de sitio** e **ID de subsitio** - configura el parámetro ID de sitio para atribuir instalaciones a publishers específicos. Si existen muchos publishers, te recomendamos limitar el número de ID de sitio usados y utilizar el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">superar las limitaciones del ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor**: utiliza cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el reporte de raw data, lo que los hace muy útiles para realizar la agregación o el filtrado de datos.  
  **Parámetros del enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

![parámetros-del-enlace-de-atribución.png](https://files.readme.io/9cc0845f4492c981fd1db843cb82caf48aecc446fac7800829ee43f858f67e64-360002880417.png)

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Para obtener más información sobre <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**la estructura y los parámetros del enlace de atribución de AppsFlyer**</Anchor>.

<div id="click-through-attribution" />

### Atribución por clics

Este control deslizante te permite establecer el **tiempo máximo del clic a la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de la ventana de lookback pueden atribuirse a Meiyou Ads.

**Parámetro del enlace de atribución:** af\_click\_lookback

Aquí puedes encontrar más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clics</Anchor>.

![netease-click-through.png](https://files.readme.io/338f41569cafb8ebaf45075bf97711af4eb2fb15d25efd036d9873544729380d-50899846629521.png)

<div id="click-attribution-link" />

### Enlace de atribución de clics

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a Meiyou Ads para que se active cuando los clientes potenciales hagan clic en el anuncio correspondiente.

<div id="view-through-attribution-lookback-window" />

### Ventana de lookback de atribución view-through

Este control deslizante te permite establecer el **tiempo máximo de la impresión a la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de esta ventana de lookback, tras la impresión de un anuncio, se atribuyen a Meiyou Ads, siempre que no haya habido ningún otro clic relevante en un anuncio.

Puedes personalizar este valor para que sea de 1-23 horas o de 1-7 días.

**Parámetro del enlace de atribución:** af\_viewthrough\_lookback

Aquí puedes encontrar más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">atribución por impresiones</Anchor>.

[![](https://files.readme.io/2567e7dca91c14a345616e1eb7cb0de8d1a5de7d2f9e90174ffc648fd04510c8-360002234185.png)](https://files.readme.io/2567e7dca91c14a345616e1eb7cb0de8d1a5de7d2f9e90174ffc648fd04510c8-360002234185.png)

<div id="impressions-attribution-link" />

### Enlace de atribución de impresiones

El enlace de atribución de impresiones contiene datos similares a los del enlace de registro de clics, además de una ventana de lookback diferente. Envíalo a Meiyou Ads para que se active cuando se vea el anuncio correspondiente, normalmente durante 1 segundo o más.


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

En esta pestaña, puedes seleccionar los permisos que quieres otorgar a Meiyou Ads, tanto si el partner actúa como ad network, agencia o incluso ambas cosas. Ten en cuenta que, aunque la atribución esté deshabilitada para Meiyou Ads, la pestaña de permisos está activa y puedes otorgar el control a Meiyou Ads.

![rtb_house-permissions-new.png](https://files.readme.io/645bdfcbb23d0ee5121a6261d5b17ca11a86209bcad2cfd9354e57c8ae281e83-50899852754449.png)

<div id="ad-network-permissions" />

### Permisos para Redes de Publicidad

Utiliza estos selectores para otorgarle permisos a la red de publicidad para que gestione su propia configuración para tu aplicación:

* ***Permitir configurar la integración*** - permite que el partner configure la pestaña de integración (excepto postbacks de eventos in-app)
* ***Permitir la configuración de postbacks de eventos in-app***: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña de integración.
* ***Permitir el acceso a tu reporte de retención***: solo para los propios datos de retención del partner.
* ***Permitir el acceso a tu panel de control Protect360***: solo a los datos de Protect360 propios del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-meiyou-ads=configuraci%C3%B3n-de-meiyou-ads h_01HKW6VQGVGFA45SQK1KANQ10Q=configuraci%C3%B3n-de-meiyou-ads h_01HKW6VQGV71MM2T401TGHEMHA=integration-tab activate-partner=activaci%C3%B3n-de-socios h_01HKW6VQGV3HG1ZTR41BD43ZTC=activaci%C3%B3n-de-socios general-settings=configuraci%C3%B3n-general h_01HKW6VQGVNG13KARWZBSD59KX=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01HKW6VQGV32R49RCEKCYK1G18=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HKW6VQGVHCVWR4KDHTH24D17=configuraci%C3%B3n-de-eventos-in-app h_01HKW6VQGVV9X64XHW48VGW6E6=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HKW6VQGVZJ36JVCZ3SW7Z3YD=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n clickthrough-attribution=atribuci%C3%B3n-por-clics h_01HKW6VQGWZQQZWT476QT496YF=atribuci%C3%B3n-por-clics click-attribution-link=enlace-de-atribuci%C3%B3n-de-clics h_01HKW6VQGWG7BH11EK5HQACKVY=enlace-de-atribuci%C3%B3n-de-clics viewthrough-attribution-lookback-window=ventana-de-lookback-de-atribuci%C3%B3n-view-through h_01HKW6VQGWFJEJYD9KG8BH9EX0=ventana-de-lookback-de-atribuci%C3%B3n-view-through impressions-attribution-link=enlace-de-atribuci%C3%B3n-de-impresiones h_01HKW6VQGWXCB2W13TM4WAGWE1=enlace-de-atribuci%C3%B3n-de-impresiones h_01HKW6VQGWY3AFFTN0DP8BCV7S=cost-tab h_01HKW6VQGWARB4409DWKVDY45W=ad-revenue-tab h_01HKW6VQGW20F6TTCBPGDH57JW=permissions-tab ad-network-permissions=permisos-para-redes-de-publicidad h_01HKW6VQGWXBME473RXA5K1217=permisos-para-redes-de-publicidad" />
