---
title: Configuración de campañas de anuncios de WiFi Master Key
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
  created_at: '2019-07-05T09:27:19Z'
  edited_at: '2026-09-17T00:26:34Z'
  id: 360001954137
  locale: es
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/es/articles/360001954137
---
> **De un vistazo:** WiFi Master Key Ads es un partner integrado de ad network de AppsFlyer.

<div id="setting-up-wifi-master-key-ads" />

## Configurar WiFi Master Key Ads

**Requisito previo:** Una cuenta con el partner. Si no tienes una cuenta, contacta con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Collaborate > Partner Integrations > Marketplace** .  
   (**Para editar una integración existente:** Ve a la pestaña **Collaborate > Partner Integrations > Active integrations**.)
2. Selecciona la aplicación correspondiente.
3. Busca el partner y selecciona **Integrate**.
4. En la pestaña **Integración**, activa el selector **Activar partner**.   
   **Nota importante:** el selector **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación.

La ventana de configuración de WiFi Master Key Ads incluye 3 pestañas activas: Integración, enlace de atribución y permisos. Haz clic en los elementos que aparecen a continuación para obtener más información sobre la configuración de las pestañas.

<div id="integration-tab" />

<Accordion title="Pestaña Integración">

<div id="activate-partner" />

### Activación de socios

En la **primera visita** aquí, deberás alternar a continuación. ACTIVA el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

<div id="general-settings" />

### Configuración general

**clientid y secretkey**

WiFi Master Key Ads se conecta con AppsFlyer mediante un clientid y un secretkey únicos. Si aún no tienes el clientid y el secretkey, debes obtenerlos de WiFi Master Key Ads para continuar con la integración.

<Image alt="mceclip2.png" src="https://files.readme.io/8b486a98e25837a0d64e0a27e9b3aa7b66b426e8bad3fbae07b7436b91351db5-50900288875153.png" width="406px" />

<div id="default-postbacks" />

### Postbacks predeterminados

<Image alt="mceclip2.png" src="https://files.readme.io/dbb58af826e66fda7a501fdb23bf5f0ded2415e295969472e04c958d3190310e-50899821656721.png" width="509px" />

<div id="in-app-events-settings" />

### Configuración de eventos in-app

En esta sección, puedes asignar tus eventos de AppsFlyer con WiFi Master Key Ads mediante postbacks.

**clientid y secretkey**

WiFi Master Key Ads se conecta con AppsFlyer mediante un clientid y un secretkey únicos. Si aún no tienes el clientid y el secretkey, debes obtenerlos de WiFi Master Key Ads para continuar con la integración.

![mceclip3.png](https://files.readme.io/035ce248d6876cf31870abc49e949fc887f6bef08efd6e132e43b8c74e3aaf45-50900269524881.png)

1. Configura aquí el clientid y el secretkey de WiFi Master Key Ads
2. Activa los postbacks de eventos in-app.
3. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
4. Completa los siguientes parámetros:

| Nombre de parámetro | Nota |
| --- | --- |
| **Nombre de evento del SDK** | El nombre del evento tal como lo recibe AppsFlyer, ya sea del SDK integrado en tu aplicación o de eventos de servidor a servidor.  <br />**Consejo**: Si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| **Identificador de evento de partner** | El nombre o ID único de cada evento según lo define WiFi Master Key Ads.  <br />Obtén el ID de evento correspondiente de WiFi Master Key Ads y configúralo en el campo de texto. |
| **Enviar ingresos** | **Si esta opción no está marcada**: AppsFlyer envía al partner todos los parámetros del evento in-app enriquecido, excepto el parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Si está marcada**: AppsFlyer envía todos los parámetros, incluido el valor de ingresos (si existe en el evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que quieres enviar a WiFi Master Key Ads para atribuir campañas, conjuntos de anuncios o incluso anuncios individuales de WiFi Master Key Ads. Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución generados para el partner.

Esta pestaña se divide en distintas secciones:

<div id="attribution-link-parameters" />

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución en esta sección te permite realizar análisis en profundidad posteriormente. Puedes editar los parámetros ya definidos en el enlace de atribución, agregándolos junto con sus nuevos valores aquí.

* **Campaña**: agrégala para comparar diferentes campañas en funcionamiento con WiFi Master Key Ads.  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios**: define nombres de conjunto de anuncios para comparar diferentes conjuntos de anuncios dentro de campañas específicas de WiFi Master Key Ads.  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre del anuncio**: define nombres de anuncios para comparar distintos creativos dentro de conjuntos de anuncios específicos, dentro de campañas específicas de WiFi Master Key Ads.  
  **Parámetro del enlace de atribución:** af\_ad
* **ID de sitio** e **ID de subsitio**: configura el parámetro de ID de sitio para atribuir las instalaciones a publishers específicos. Si hay muchos publishers, te recomendamos limitar el número de IDs de sitio usados y utilizar el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder las limitaciones del ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor**: utiliza cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el Reporte de raw data, lo que los hace muy útiles para realizar la agregación o el filtrado de datos.  
  **Parámetros del enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

![attribution-link-parameters.png](https://files.readme.io/9cc0845f4492c981fd1db843cb82caf48aecc446fac7800829ee43f858f67e64-360002880417.png)

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Para obtener más información sobre <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**la estructura y los parámetros de los enlaces de atribución de AppsFlyer**</Anchor>.

<div id="click-through-attribution" />

### Atribución por clics

Este control deslizante te permite establecer el **tiempo máximo desde el clic hasta la instalación**. Solo las instalaciones (primeros lanzamientos) que tengan lugar dentro de la ventana de lookback pueden atribuirse a WiFi Master Key Ads.

**Parámetro del enlace de atribución:** af\_click\_lookback

Más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clic aquí</Anchor>.

![netease-click-through.png](https://files.readme.io/338f41569cafb8ebaf45075bf97711af4eb2fb15d25efd036d9873544729380d-50899846629521.png)

<div id="click-attribution-link" />

### Enlace de atribución de clics

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a WiFi Master Key Ads para que se active cuando los leads hagan clic en un anuncio correspondiente.

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

En esta pestaña, puedes seleccionar los permisos que quieres otorgar a WiFi Master Key Ads, tanto si el partner actúa como ad network, agencia o incluso ambos. Ten en cuenta que, aunque la atribución esté deshabilitada para WiFi Master Key Ads, la pestaña de permisos está activa y puedes conceder el control a WiFi Master Key Ads.

![rtb_house-permissions-new.png](https://files.readme.io/645bdfcbb23d0ee5121a6261d5b17ca11a86209bcad2cfd9354e57c8ae281e83-50899852754449.png)

<div id="ad-network-permissions" />

### Permisos para Redes de Publicidad

Utiliza estos selectores para otorgarle permisos a la red de publicidad para que gestione su propia configuración para tu aplicación:

* ***Permitir configurar la integración*** - permite que el partner configure la pestaña Integración (excepto los postbacks de eventos in-app)
* ***Permitir la configuración de postbacks de eventos in-app***: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña de integración.
* ***Permitir el acceso a tu reporte de retención***: solo para los propios datos de retención del partner.
* ***Permitir el acceso a tu panel de control Protect360***: solo a los datos de Protect360 propios del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-wifi-master-key-ads=configurar-wifi-master-key-ads h_01HKW6Z9DPAYATXWJR4GZMD0KM=configurar-wifi-master-key-ads h_01HKW6Z9DPYGREGB9VHJJQP6FS=integration-tab activate-partner=activaci%C3%B3n-de-socios h_01HKW6Z9DP6WQD968EQS8G0SZY=activaci%C3%B3n-de-socios general-settings=configuraci%C3%B3n-general h_01HKW6Z9DQ3K3RTCT7CMT67WCX=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01HKW6Z9DQ26D258602BC43T9B=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HKW6Z9DQ1XMVERFP97HQ7HM7=configuraci%C3%B3n-de-eventos-in-app h_01HKW6Z9DQ0GEE118QKXRA335C=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HKW6Z9DQ8YMNT6W2B8NEV520=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n clickthrough-attribution=atribuci%C3%B3n-por-clics h_01HKW6Z9DQ9D2F75XWZRM0JAQM=atribuci%C3%B3n-por-clics click-attribution-link=enlace-de-atribuci%C3%B3n-de-clics h_01HKW6Z9DQQE4QP37994K8HMCQ=enlace-de-atribuci%C3%B3n-de-clics h_01HKW6Z9DQJ6F8Z074H9JG97EC=cost-tab h_01HKW6Z9DQ6GW0S9KDG0RFK1BX=ad-revenue-tab h_01HKW6Z9DQ3Y12DV461NHST3FT=permissions-tab ad-network-permissions=permisos-para-redes-de-publicidad h_01HKW6Z9DQZ8TBA8DK6NJNQT4F=permisos-para-redes-de-publicidad" />
