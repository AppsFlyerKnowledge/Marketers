---
title: Configuración de la campaña de Ligatus
metadata:
  keywords:
    - Ligatus
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
  created_at: '2016-06-20T12:47:01Z'
  edited_at: '2026-08-12T12:14:20Z'
  id: 211189743
  locale: es
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/es/articles/211189743
---
> **En resumen:** Ligatus, un partner integrado de ad network de AppsFlyer, lidera las Soluciones de Publicidad Nativa para publisher, Anunciantes y compradores programáticos, y ofrece resultados de alta calidad y alto rendimiento. Además de la atribución móvil basada en clics, Ligatus también ofrece atribución de costos, ingresos por publicidad, retargeting y por impresiones, que puedes registrar con AppsFlyer.

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/ligatus.png" width="209px" />

## Configuración de Ligatus

**Requisito previo:** Antes de configurar la integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con él. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Para activar o editar la integración:**

1. **Para activarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Partner Marketplace**.  
   **Para editarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Integraciones activas**.
2. Selecciona la aplicación correspondiente.
3. Haz clic en **Configurar integración**.
4. En la **primera visita** aquí, deberás activar **Activar partner** para habilitar la configuración de los parámetros de integración. El selector debe estar activado mientras trabajes con el partner.  
    Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe en la sección a continuación. Para ver una descripción detallada del Encabezado de la ventana de configuración de partner, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aquí</Anchor>.

La ventana de configuración de Ligatus incluye 2 pestañas activas: integración y enlace de atribución. Haz clic en los elementos que aparecen a continuación para obtener más información sobre la configuración de las pestañas.

> 👍 **Consejo**
>
> * El paso de <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#d">Configuración general</Anchor> en la pestaña Integración es **obligatorio** para todos los partners.
> * Todos los demás pasos son descriptivos u **opcionales**.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

### Activar socio

En la **primera visita** aquí, debes activar el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El activador debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

### Postbacks predeterminados

envía postbacks automáticos a Ligatus después de las instalaciones y los re-engagements de los usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

Selecciona **Solo eventos atribuidos a este partner** para eventos que provienen solo de usuarios atribuidos a Ligatus.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que quieres enviar a Ligatus para atribuir las campañas, los conjuntos de anuncios o incluso los anuncios individuales de Ligatus. Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución generados para el partner.

Esta pestaña se divide en distintas secciones:

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Añadir parámetros al enlace de atribución aquí te permite realizar análisis detallados más adelante. Puedes editar los parámetros ya definidos en el enlace de atribución, agregándolos junto con sus nuevos valores aquí.

* **Campaña**: añádela para comparar distintas campañas en funcionamiento con Ligatus.  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios**: define nombres de conjunto de anuncios para comparar distintos conjuntos de anuncios dentro de campañas específicas de Ligatus.  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre del anuncio**: configura nombres de anuncios para comparar distintos creativos dentro de conjuntos de anuncios específicos, dentro de campañas específicas de Ligatus.  
  **Parámetro de enlace de atribución:** af\_ad
* **ID de sitio** y **ID de subsitio**: configura el parámetro ID de sitio para atribuir las instalaciones a publishers específicos. Si existen muchos publishers, te recomendamos que limites la cantidad de ID de sitio usados y utilices el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder las limitaciones de ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor**: usa cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el reporte de raw data, lo que los hace muy útiles para realizar la agregación o el filtrado de datos.  
  **Parámetros del enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Para obtener más información sobre <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**Estructura de enlaces de atribución y parámetros de AppsFlyer**</Anchor>.

### Atribución por clic

Este control deslizante te permite establecer el **tiempo máximo desde el clic hasta la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de la ventana de lookback pueden atribuirse a Ligatus.

**Parámetro del enlace de atribución:** af\_click\_lookback

Más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clic aquí</Anchor>.

### Haz clic en el enlace de atribución

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a Ligatus para que se active cuando los clientes potenciales hagan clic en el anuncio correspondiente.

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

La configuración de permisos no está disponible para Ligatus.

</Accordion>

<div data-zendesk-anchors="setting-up-ligatus=configuraci%C3%B3n-de-ligatus h_01HKW2DXQHTK9HVAWK0ECR46AZ=configuraci%C3%B3n-de-ligatus h_01HKW2DXQJ4DBPP38P4RRZGX10=consejo h_01HKW2DXQJYQ7PJVN6HAM0AHXB=integration-tab activate-partner=activar-socio h_01HKW2DXQJEF1KX2C489M18EB7=activar-socio default-postbacks=postbacks-predeterminados h_01HKW2DXQJPJKBMA7ZN75JSSNR=postbacks-predeterminados h_01HKW2DXQJNFZJT6NVC2R3GDSB=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HKW2DXQJC123Y5DPX0V86M4K=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n clickthrough-attribution=atribuci%C3%B3n-por-clic h_01HKW2DXQK53YBMRBF2RC26SG8=atribuci%C3%B3n-por-clic click-attribution-link=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HKW2DXQKFGXMBB31N3EJAA55=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HKW2DXQKPZBFVKQ71G6076VN=cost-tab h_01HKW2DXQKQ0YDVHMGJ0WMP1CB=ad-revenue-tab h_01HKW2DXQKBC42EMXQRVZSK7N4=permissions-tab" />
