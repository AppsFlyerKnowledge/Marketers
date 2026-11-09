---
title: Configuración de la campaña de Baidu Native Ads 2.0
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
  created_at: '2019-08-02T04:18:11Z'
  edited_at: '2026-09-17T00:26:01Z'
  id: 360002158958
  locale: es
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/es/articles/360002158958
---
> **Resumen:** Baidu Native Ads 2.0 es un partner integrado de ad network de AppsFlyer.

<div id="setting-up-baidu-native-ads-20" />

## Configurar Baidu Native Ads 2.0

**Requisito previo:** Tener una cuenta con el partner. Si no tienes una cuenta, contacta con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de partners > Marketplace**.  
   (**Para editar una integración existente:** Ve a la pestaña **Colaborar > Integraciones de partners > Integraciones activas**.)
2. Selecciona la aplicación correspondiente.
3. Busca el partner y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el selector **Activar partner**.   
   **Nota importante:** El selector **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas pertinentes, como se describe a continuación.

La ventana de configuración de Baidu Native Ads 2.0 incluye 3 pestañas activas: Integración, enlace de atribución y permisos. Haz clic en los elementos que aparecen a continuación para obtener más información sobre la configuración de las pestañas.

<div id="integration-tab" />

<Accordion title="Pestaña Integración">

<div id="activate-partner" />

### Activación de socios

En la **primera visita** aquí, deberás alternar a continuación. ACTIVA el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

<div id="general-settings" />

### Configuración general

Baidu Native Ads 2.0 se conecta con AppsFlyer a través de una **akey** única. Si aún no tienes la clave, debes obtenerla de Baidu Native Ads 2.0 para continuar con la integración.

<Image align="center" alt="mceclip2.png" src="https://files.readme.io/fe8f44ee7d58fda9ee6289872903f96c716ab6d1191dd831745445cbced8b316-50899807435409.png" width="417px" />

<div id="default-postbacks" />

### Postbacks predeterminados

<Image align="center" alt="mceclip2.png" src="https://files.readme.io/dbb58af826e66fda7a501fdb23bf5f0ded2415e295969472e04c958d3190310e-50899821656721.png" width="552px" />

<div id="in-app-events-settings" />

### Configuración de eventos in-app

En esta sección, puedes asignar tus eventos de AppsFlyer con Baidu Native Ads 2.0 a través de postbacks. 

<Image align="center" alt="mceclip1.png" src="https://files.readme.io/1d929a3ba75da04165e416843f5037b8e299b12ae190aa9068cc3b317348087c-50899846627601.png" width="598px" />

1. Activa los postbacks de eventos in-app.
2. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
3. Completa los siguientes parámetros:

| Nombre de parámetro | Nota |
| --- | --- |
| **Nombre de evento del SDK** | El nombre del evento tal como lo recibe AppsFlyer, ya sea del SDK integrado en tu aplicación o de eventos de servidor a servidor.  <br />**Consejo**: Si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| **Identificador de evento de partner** | El nombre único o ID de cada evento según lo define Baidu Native Ads 2.0.  <br />Obtén el ID de evento correspondiente de Baidu Native Ads 2.0 e introdúcelo en el campo de texto. |
| **Enviar ingresos** | **Si esta opción no está marcada**: AppsFlyer envía al partner todos los parámetros del evento in-app enriquecido, con excepción del parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Si está marcada**: AppsFlyer envía todos los parámetros, incluido el valor de ingresos (si existe en el evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que deseas enviar a Baidu Native Ads 2.0 para atribuir las campañas, los conjuntos de anuncios o incluso los anuncios individuales de Baidu Native Ads 2.0. Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución generados para el partner.

Esta pestaña se divide en distintas secciones:

<div id="attribution-link-parameters" />

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución en esta sección te permite realizar análisis en profundidad posteriormente. Puedes editar los parámetros ya definidos en el enlace de atribución, agregándolos junto con sus nuevos valores aquí.

* **Campaña**: agrégala para comparar distintas campañas de Baidu Native Ads 2.0.  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios**: define nombres de conjunto de anuncios para comparar diferentes conjuntos de anuncios dentro de campañas específicas de Baidu Native Ads 2.0.  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre del anuncio**: define nombres de anuncios para comparar diferentes creatividades dentro de conjuntos de anuncios específicos, dentro de campañas específicas de Baidu Native Ads 2.0.  
  **Parámetro de enlace de atribución:** af\_ad
* **ID de sitio** e **ID de subsitio**: configura el parámetro ID de sitio para atribuir las instalaciones a publishers específicos. Si existen muchos publishers, te sugerimos que limites la cantidad de IDs de sitio usados y utilices el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder las limitaciones de ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor** - usa cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el reporte de raw data, lo que los hace muy útiles para realizar la agregación o el filtrado de datos.  
  **Parámetros del enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

<Image align="center" alt="parametros-del-enlace-de-atribucion.png" src="https://files.readme.io/9cc0845f4492c981fd1db843cb82caf48aecc446fac7800829ee43f858f67e64-360002880417.png" />

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Saber más sobre <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**la estructura y los parámetros del enlace de atribución de AppsFlyer**</Anchor>.

<div id="click-through-attribution" />

### Atribución por clics

Este control deslizante te permite establecer el **tiempo máximo entre el clic y la instalación**. Solo las instalaciones (primeras ejecuciones) que tengan lugar dentro de la ventana de lookback pueden atribuirse a Baidu Native Ads 2.0.

**Parámetro del enlace de atribución:** af\_click\_lookback

Más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clic aquí</Anchor>.

<Image align="center" alt="netease-click-through.png" src="https://files.readme.io/338f41569cafb8ebaf45075bf97711af4eb2fb15d25efd036d9873544729380d-50899846629521.png" />

<div id="attribution-link" />

### Enlace de atribución

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a Baidu Native Ads 2.0 para que se active cuando los leads hagan clic en el anuncio correspondiente.

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

Los permisos no son compatibles con la integración con este partner.


</Accordion>

<div data-zendesk-anchors="setting-up-baidu-native-ads-20=configurar-baidu-native-ads-20 h_01HKW6TZKDHY5D1VZ5PB7VM2MC=configurar-baidu-native-ads-20 h_01HKW6TZKDRECSQTP2VSAZZ5V6=integration-tab activate-partner=activaci%C3%B3n-de-socios h_01HKW6TZKDY6EEHMK5SJWBW0EH=activaci%C3%B3n-de-socios general-settings=configuraci%C3%B3n-general h_01HKW6TZKDGFFMPSZGN8AZWA80=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01HKW6TZKDBAQRP63ST32NN4DN=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HKW6TZKDYHPZXN0TC219XPA1=configuraci%C3%B3n-de-eventos-in-app h_01HKW6TZKEFVXGP11N8G4C6JTP=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HKW6TZKE5GJV1ZSJTVPG668Q=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n clickthrough-attribution=atribuci%C3%B3n-por-clics h_01HKW6TZKEWA482TABZ8651NPP=atribuci%C3%B3n-por-clics attribution-link=enlace-de-atribuci%C3%B3n h_01HKW6TZKEWJTMCK86JZN27R1F=enlace-de-atribuci%C3%B3n h_01HKW6TZKEX2JQQNA5JMQ40848=cost-tab h_01HKW6TZKE4N38GCTBK4VDNNF8=ad-revenue-tab h_01HKW6TZKEY7RSV934KZ6XRXM2=permissions-tab" />
