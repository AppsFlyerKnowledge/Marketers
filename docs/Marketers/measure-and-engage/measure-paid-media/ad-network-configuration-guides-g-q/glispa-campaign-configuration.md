---
title: Configuración de la campaña de Glispa
metadata:
  keywords:
    - Glispa
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
  created_at: '2016-04-07T12:53:20Z'
  edited_at: '2026-09-11T00:23:40Z'
  id: 209912983
  locale: es
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/es/articles/209912983
---
> **De un vistazo:** Glispa, un partner de ad network integrado con AppsFlyer, crea soluciones que facilitan que las agencias y las marcas conecten con audiencias objetivo y que los publishers moneticen sus apps. Además de la atribución móvil basada en clics, Glispa también ofrece atribución por costo y view-through, que puedes registrar con AppsFlyer.

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/glispacpa.png?v=1" width="168px" />

## Configuración de Glispa

**Requisito previo:** Una cuenta con el partner. Si no tienes una cuenta, contacta con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de partners > Marketplace** .  
   (**Para editar una integración existente:** Ve a la pestaña **Colaborar > Integraciones de partners > Integraciones activas** .)
2. Selecciona la aplicación correspondiente.
3. Busca el partner y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el selector **Activar partner**.   
   **Nota:** el selector **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Más información</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Más información sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de partners.</Anchor>

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

### Activar socio

En la **primera visita** aquí, tendrás que activar el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El activador debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

### Configuración general

**Habilitar la atribución por impresiones**

[![appl013.png](https://files.readme.io/513c24cf8bcf72d8efc3324411a1bea1fd45e8c7cb721c7f1144463fa030492c-50706625495953.png)](https://files.readme.io/513c24cf8bcf72d8efc3324411a1bea1fd45e8c7cb721c7f1144463fa030492c-50706625495953.png)

Activa esta opción si quieres atribuir instalaciones view-through de Glispa. El control deslizante de la ventana de lookback view-through está disponible en la pestaña del enlace de atribución (se describe a continuación).

### Postbacks predeterminados

Envía postbacks automáticos a Glispa después de las instalaciones y re-engagements de los usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

Selecciona **Solo eventos atribuidos a este partner** para los eventos que provengan únicamente de usuarios atribuidos a Glispa.  
Selecciona **Eventos atribuidos a cualquier partner u orgánicos** para tener disponible toda tu base de usuarios para reportarla a Glispa.

### Configuración de eventos in-app

En esta sección, puedes asignar qué eventos de AppsFlyer enviar a Glispa mediante postbacks.

1. Activa los Postbacks de eventos in-app con el selector.
2. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que provienen **únicamente** de usuarios atribuidos a este partner.  
    **- Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada al partner.
3. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
4. Completa los siguientes parámetros:

| Nombre de parámetro | Nota |
| --- | --- |
| **Nombre de evento del SDK** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea desde el SDK integrado con tu aplicación o desde eventos de servidor a servidor.  <br />**Consejo**: Si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| **Enviar ingresos** | **Si no está marcada**: se envían al partner todos los parámetros del evento in-app enriquecido, con excepción del parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Si está marcada**: se envían todos los parámetros, incluido el valor de ingresos (si existe en el evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que quieras enviar a Glispa para atribuir las campañas, los conjuntos de anuncios o incluso los anuncios individuales de Glispa. Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución generados para el partner.

Esta pestaña se divide en distintas secciones:

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución en esta sección te permite realizar análisis en profundidad posteriormente. Puedes editar los parámetros ya definidos en el enlace de atribución, agregándolos junto con sus nuevos valores aquí.

* **Campaña**: añádela para comparar distintas campañas en funcionamiento con Glispa.  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios**: define nombres de conjunto de anuncios para comparar diferentes conjuntos de anuncios dentro de campañas específicas de Glispa.  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre del anuncio**: define nombres de anuncios para comparar distintos creativos dentro de conjuntos de anuncios específicos de campañas específicas de Glispa.  
  **Parámetro del enlace de atribución:** af\_ad
* **ID de sitio** e **ID de subsitio** - configura el parámetro de ID de sitio para atribuir las instalaciones a publishers específicos. Si existen muchos publishers, te recomendamos limitar el número de IDs de sitio usados y utilizar el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">superar las limitaciones del ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor**: utiliza cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el reporte de raw data, lo que los hace muy útiles para realizar la agregación o el filtrado de datos.  
  **Parámetros del enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Para obtener más información sobre <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**los parámetros y la estructura de los enlaces de atribución de AppsFlyer**</Anchor>.

### Atribución por clic

Este control deslizante te permite establecer el **tiempo máximo desde el clic hasta la instalación**. Solo las instalaciones (primeras ejecuciones) que tengan lugar dentro de la ventana de lookback pueden atribuirse a Glispa.

**Parámetro del enlace de atribución:** af\_click\_lookback

Aquí encontrarás más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clic</Anchor>.

[![](https://files.readme.io/72e192640be302ffede694bc264f1ce5746022242bfa441b29f835605a07004d-50706581523217.png)](https://files.readme.io/72e192640be302ffede694bc264f1ce5746022242bfa441b29f835605a07004d-50706581523217.png)

### Haz clic en el enlace de atribución

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a Glispa para que se active cuando los leads hagan clic en un anuncio correspondiente.

### Ventana de lookback de atribución view-through

Este control deslizante te permite establecer el **tiempo máximo de la impresión a la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de esta ventana de lookback, tras la impresión de un anuncio, se atribuyen a Glispa, siempre que no haya habido ningún otro clic relevante en un anuncio.

Puedes personalizar este valor para que sea de 1-23 horas o de 1-7 días.

**Parámetro del enlace de atribución:** af\_viewthrough\_lookback

Aquí encontrarás más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">atribución por impresiones</Anchor>.

### Enlace de atribución de impresiones

El enlace de atribución de impresiones contiene datos similares a los del enlace de registro de clics, además de una ventana de lookback diferente. Envíalo a Glispa para que se active cuando se vea un anuncio correspondiente, normalmente durante 1 segundo o más.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

Glispa Media CPI envía automáticamente datos de costos de CPI encriptados en el enlace de atribución para todas las instalaciones.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Los ingresos por publicidad no se admiten en la integración con este partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

Utiliza estos selectores para otorgar a Glispa permisos para gestionar su propia configuración para tu app:

### Permisos de ad network

* ***Permitir la configuración de la integración***: permite que el partner configure la pestaña de integración (excepto postbacks de eventos in-app).
* ***Permitir la configuración de postbacks de eventos in-app***: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña de integración.
* ***Permitir el acceso a tu reporte de retención***: solo para los propios datos de retención del partner.
* ***Permitir acceso a tus datos agregados de usuarios fieles***: solo a los datos de usuarios fieles propios del partner.
* ***Permitir acceso a tus datos agregados de eventos in-app**:* solo a los datos de eventos in-app propios del partner.
* ***Permitir acceso a tus datos agregados de ingresos*a** - solo a los datos de ingresos atribuidos al partner
* ***Permitir el acceso a tu panel de control Protect360***: solo a los datos de Protect360 propios del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

### Permisos de la agencia

Utiliza estos selectores para otorgar permisos a una agencia para que gestione su propia configuración para tu aplicación:

* ***Selector principal*** - actívalo para mostrar las opciones de permisos para agencias
* ***Permitir el acceso a tu reporte de retención*** - solo a los propios datos de retención de la agencia
* ***Permitir el acceso a datos agregados orgánicos.***
* ***Permitir configurar postbacks de eventos in-app*** - permite que la agencia configure en la pestaña de integración la asignación de postbacks de eventos in-app a sí misma

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permisos-de-la-agencia">permisos a las agencias</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-glispa=configuraci%C3%B3n-de-glispa h_01HKA0TGE08PJDBQHFER5ZZ785=configuraci%C3%B3n-de-glispa h_01HKA0TGE02G8YFSQSKMQVSWK2=integration-tab activate-partner=activar-socio h_01HKA0TGE02R2V2WP9S47QZRDC=activar-socio general-settings=configuraci%C3%B3n-general h_01HKA0TGE04YGTY2D9758KFJ0P=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01HKA0TGE0TPCZWZXX5YQHW59Q=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HKA0TGE0Y9ZQDZBRHQGCSEHH=configuraci%C3%B3n-de-eventos-in-app h_01HKA0TGE0VQY6MB69G02TE1T6=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HKA0TGE0BYX5YB9XYCWX5YJH=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n clickthrough-attribution=atribuci%C3%B3n-por-clic h_01HKA0TGE0TVP7JRW3J9E4QGKC=atribuci%C3%B3n-por-clic click-attribution-link=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HKA0TGE10GVS8G2HYTB9V13X=haz-clic-en-el-enlace-de-atribuci%C3%B3n viewthrough-attribution-lookback-window=ventana-de-lookback-de-atribuci%C3%B3n-view-through h_01HKA0TGE1CNX84Y3JSWQPMP1Y=ventana-de-lookback-de-atribuci%C3%B3n-view-through impressions-attribution-link=enlace-de-atribuci%C3%B3n-de-impresiones h_01HKA0TGE1GVH38JF1AYEBM8EC=enlace-de-atribuci%C3%B3n-de-impresiones h_01HKA0TGE1QXYQ1A5MYHGHZ4B4=cost-tab h_01HKA0TGE10TWPQZRF1NMET76A=ad-revenue-tab h_01HKA0TGE12N0Y8Y88C9PTTF6P=permissions-tab ad-network-permissions=permisos-de-ad-network h_01HKA0TGE1TANWDZ23PJKRPWKT=permisos-de-ad-network agency-permissions=permisos-de-la-agencia h_01HKA0TGE16J58NXGA0VDBBHWY=permisos-de-la-agencia" />
