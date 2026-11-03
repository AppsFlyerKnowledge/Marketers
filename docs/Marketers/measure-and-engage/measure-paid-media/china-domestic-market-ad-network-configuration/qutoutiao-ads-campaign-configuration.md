---
title: Configuración de campañas de Qutoutiao Ads
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
  created_at: '2019-04-11T09:26:22Z'
  edited_at: '2026-09-17T00:26:16Z'
  id: 360001390337
  locale: es
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/es/articles/360001390337
---
> **De un vistazo:** Qutoutiao Ads es un partner integrado de ad network de AppsFlyer.

## Configuración de Qutoutiao Ads

**Requisito previo:** Una cuenta con el partner. Si no tienes una cuenta, contacta con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de partner > Marketplace** .  
   (**Para editar una integración existente:** Ve a la pestaña **Colaborar > Integraciones de partner > Integraciones activas** .)
2. Selecciona la aplicación correspondiente.
3. Busca el partner y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el selector **Activar partner**.   
   **Nota importante:** El selector **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación.

La ventana de configuración de Qutoutiao Ads incluye 3 pestañas activas: Integración, enlace de atribución y permisos. Haz clic en los elementos que aparecen a continuación para obtener más información sobre la configuración de las pestañas.

<div id="integration-tab" />

<Accordion title="Pestaña Integración">

### Activación de socios

En la **primera visita** aquí, deberás alternar a continuación. ACTIVA el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

### Postbacks predeterminados

<Image alt="mceclip2.png" src="https://files.readme.io/dbb58af826e66fda7a501fdb23bf5f0ded2415e295969472e04c958d3190310e-50899821656721.png" width="601px" />

### Configuración de eventos in-app

En esta sección puedes asignar tus eventos de AppsFlyer a Qutoutiao Ads mediante postbacks. 

![mceclip0.png](https://files.readme.io/74a4c9e81ac69f65079f5e214de90dc8725f8aedaf59c7ee4d9a3d947a853a0b-50899821661713.png)

1. Activa los postbacks de eventos in-app.
2. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
3. Completa los siguientes parámetros:

| Nombre de parámetro | Nota |
| --- | --- |
| **Nombre de evento del SDK** | El nombre del evento tal como lo recibe AppsFlyer, ya sea del SDK integrado en tu aplicación o de eventos de servidor a servidor.  <br />**Consejo**: Si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| **Identificador de evento de partner** | El nombre o ID único de cada evento según lo define Qutoutiao Ads.  <br />Obtén el ID de evento correspondiente de Qutoutiao Ads e introdúcelo en el campo de texto. |
| **Enviar ingresos** | **Si esta opción no está marcada**: AppsFlyer envía al partner todos los parámetros del evento in-app enriquecido, excepto el parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Si está marcada**: AppsFlyer envía todos los parámetros, incluido el valor de ingresos (si existe en el evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que quieres enviar a Qutoutiao Ads para atribuir campañas, conjuntos de anuncios o incluso anuncios individuales de Qutoutiao Ads. Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución generados para el partner.

Esta pestaña se divide en distintas secciones:

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución en esta sección te permite realizar análisis en profundidad posteriormente. Puedes editar los parámetros ya definidos en el enlace de atribución, agregándolos junto con sus nuevos valores aquí.

* **Campaña**: añádela para comparar distintas campañas en ejecución con Qutoutiao Ads.  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios**: define nombres de conjuntos de anuncios para comparar distintos conjuntos de anuncios dentro de campañas específicas de Qutoutiao Ads.  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre de anuncio**: define nombres de anuncios para comparar distintos creativos dentro de conjuntos de anuncios específicos de campañas específicas de Qutoutiao Ads.  
  **Parámetro de enlace de atribución:** af\_ad
* **ID de sitio** e **ID de subsitio**: configura el parámetro ID de sitio para atribuir instalaciones a publishers específicos. Si existen muchos publishers, te recomendamos limitar la cantidad de IDs de sitio usados y utilizar el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder las limitaciones de ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor**: utiliza cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el Reporte de raw data, lo que los hace muy útiles para realizar la agregación o el filtrado de datos.  
  **Parámetros del enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

![attribution-link-parameters.png](https://files.readme.io/9cc0845f4492c981fd1db843cb82caf48aecc446fac7800829ee43f858f67e64-360002880417.png)

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Para obtener más información sobre <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**la estructura y los parámetros de los enlaces de atribución de AppsFlyer**</Anchor>.

### Atribución por clics

Este control deslizante te permite establecer el **tiempo máximo desde el clic hasta la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de la ventana de lookback pueden atribuirse a Qutoutiao Ads.

**Parámetro del enlace de atribución:** af\_click\_lookback

Más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clic aquí</Anchor>.

![netease-click-through.png](https://files.readme.io/338f41569cafb8ebaf45075bf97711af4eb2fb15d25efd036d9873544729380d-50899846629521.png)

### Enlace de atribución de clics

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a Qutoutiao Ads para que se active cuando los clientes potenciales hagan clic en el anuncio correspondiente.

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

En esta pestaña, puedes seleccionar los permisos que quieres otorgar a Qutoutiao Ads, tanto si el partner actúa como ad network, agencia o incluso como ambos. Ten en cuenta que, incluso si la atribución está deshabilitada para Qutoutiao Ads, la pestaña de permisos está activa y puedes otorgar el control a Qutoutiao Ads.

![rtb_house-permissions-new.png](https://files.readme.io/645bdfcbb23d0ee5121a6261d5b17ca11a86209bcad2cfd9354e57c8ae281e83-50899852754449.png)

### Permisos para Redes de Publicidad

Utiliza estos selectores para otorgarle permisos a la red de publicidad para que gestione su propia configuración para tu aplicación:

* ***Permitir configurar la integración*** - permite que el partner configure la pestaña de integración (excepto los postbacks de eventos in-app)
* ***Permitir la configuración de postbacks de eventos in-app***: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña de integración.
* ***Permitir el acceso a tu reporte de retención***: solo para los propios datos de retención del partner.
* ***Permitir el acceso a tu panel de control Protect360***: solo a los datos de Protect360 propios del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-qutoutiao-ads=configuraci%C3%B3n-de-qutoutiao-ads h_01HKW6WY2H57T49HJPMF29J8XH=configuraci%C3%B3n-de-qutoutiao-ads h_01HKW6WY2JY25ZMQXA963Z0Q71=integration-tab activate-partner=activaci%C3%B3n-de-socios h_01HKW6WY2J4WMBMSAJEP8GGWYA=activaci%C3%B3n-de-socios default-postbacks=postbacks-predeterminados h_01HKW6WY2JJ52DGPRH5KE6K094=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HKW6WY2JH1QC5QDMQ4RN67JG=configuraci%C3%B3n-de-eventos-in-app h_01HKW6WY2JZ7X4EPZ0C3D4QV7J=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HKW6WY2J5GF13RV6JBW5QPXP=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n clickthrough-attribution=atribuci%C3%B3n-por-clics h_01HKW6WY2J5CBA3VCKKK61N7N7=atribuci%C3%B3n-por-clics click-attribution-link=enlace-de-atribuci%C3%B3n-de-clics h_01HKW6WY2JNAZ769AQ64539P8J=enlace-de-atribuci%C3%B3n-de-clics h_01HKW6WY2J30M3DSQZBY327364=cost-tab h_01HKW6WY2J8MAM70BH33PDKRHB=ad-revenue-tab h_01HKW6WY2J6NHVSVZXC60KATFP=permissions-tab ad-network-permissions=permisos-para-redes-de-publicidad h_01HKW6WY2JJF66DWZS5W4Z95E3=permisos-para-redes-de-publicidad" />
