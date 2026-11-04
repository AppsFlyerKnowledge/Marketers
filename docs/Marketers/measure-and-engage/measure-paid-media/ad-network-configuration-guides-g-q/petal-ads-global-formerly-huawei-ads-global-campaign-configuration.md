---
title: >-
  Configuración de la campaña de Petal Ads Global (anteriormente HUAWEI Ads
  Global)
metadata:
  keywords:
    - integrated partner
    - Advertisers
    - Agencies
    - huawei
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2020-06-28T08:40:00Z'
  edited_at: '2026-09-11T00:24:31Z'
  id: 360010605858
  locale: es
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/es/articles/360010605858
---
> **En resumen:** Petal Ads Global, un partner integrado de AppsFlyer, es un servicio de presentación de anuncios de pago proporcionado por Huawei para partners del ecosistema. Su objetivo es ayudar a los partners a establecer un puente de comunicación con los usuarios de dispositivos Huawei para que puedan proporcionar información valiosa y servicios de calidad a los usuarios. Petal Ads Global ofrece espacios para mostrar anuncios habituales, como anuncios nativos, anuncios de vídeo bonificado, anuncios de banner y anuncios intersticiales, a más de 570 millones de usuarios de dispositivos Huawei de todo el mundo.

<Image alt="huaweiadsglobal.png" src="https://files.readme.io/12f1351923768c1afc1ba0f16b267388a8c9b1ae7fc2d6d36b5d1d01381f1bbc-14151449726353.png" width="18.53%" />

<div id="petal-ads-global-introduction" />

## Introducción a Petal Ads Global

Petal Ads Global está integrado en varias apps de terceros y apps de Huawei, como HUAWEI Browser, HUAWEI Video, HUAWEI Assistant, HUAWEI Reader y HUAWEI Music, que son subpublishers de la red de anuncios de display de Petal Ads Global. Además, las ubicaciones de anuncios estándar de AppGallery y App Gallery Search Ads también ofrecen soporte para la atribución de AppsFlyer.

<div id="setting-up-petal-ads-global" />

## Configuración de Petal Ads Global

Petal Ads Global requiere el uso de **OAID** para la atribución. Consulta <Anchor target="_blank" href="/marketers/es/docs/android-oaid-implementation-in-the-sdk">**nuestra guía de implementación de OAID de Android en el SDK**</Anchor> para obtener el OAID en dispositivos HUAWEI. Además, Petal Ads Global recomienda encarecidamente la **atribución del referente de HUAWEI App Gallery** para las apps de la tienda. Para habilitar la atribución del referente de Huawei, actualiza el SDK de Android a la versión 6.14.0 o superior.

| Fuentes de tráfico | Valor del canal | Métodos de atribución | Advertencia |
| --- | --- | --- | --- |
| Anuncios en pantalla | huaweiadsglobal | Coincidencia de ID (OAID o GAID), modelado probabilístico, referente de Huawei | Haz clic <Anchor target="_blank" href="/marketers/es/docs/android-oaid-implementation-in-the-sdk">aquí</Anchor> para consultar la guía de implementación de OAID en el SDK de Android. La atribución del referente de Huawei requiere Android SDK 6.14.0 |
| App Gallery | huaweiappgalleryglobal | Coincidencia de ID (OAID o GAID), referente de Huawei | La atribución del referente de Huawei requiere Android SDK 6.14.0 |
| Petal Search | valor vacío | Coincidencia de ID (OAID o GAID), modelado probabilístico | Haz clic <Anchor target="_blank" href="/marketers/es/docs/android-oaid-implementation-in-the-sdk">aquí</Anchor> para consultar la guía de implementación de OAID en el SDK de Android |

<div id="setting-up-the-petal-ads-global-integration" />

### Configuración de la integración con Petal Ads Global

**Requisito previo:** una cuenta con el Partners. Si no tienes una cuenta, ponte en contacto con el Partners para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de Partners > Marketplace**.  
   (**Para editar una integración existente:** ve a la pestaña **Colaborar > Integraciones de Partners > Integraciones activas**.)
2. Selecciona la aplicación correspondiente.
3. Busca el Partners y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el conmutador **Activar partner**.   
   **Nota:** el conmutador **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe en la sección a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de partners</Anchor>

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La **Pestaña integración** se divide en diferentes secciones:

<div id="activate-partner" />

#### Activar socio

Para habilitar la configuración, <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation#activar-la-integración-de-un-partner">Activar el partner</Anchor>.

Este conmutador debe estar activado mientras trabajes con el partner.

<div id="general-settings" />

#### Configuración general

**Habilitar la atribución view-through**

Para atribuir instalaciones view-through de Petal Ads Global, activa este conmutador. El control deslizante de la ventana de lookback view-through está disponible en la pestaña **Enlace de atribución**.

<div id="default-postbacks" />

#### Postbacks predeterminados

Envía postbacks automáticos a Petal Ads Global tras las instalaciones de usuarios atribuidos solo a Petal Ads Global. Saber más sobre los <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#default-postbacks">postbacks por defecto</Anchor>.

<div id="in-app-events-settings" />

#### Configuración de eventos in-app

Configura los postbacks de eventos in-app que se envían a Petal Ads Global.

**Para configurar postbacks de eventos in-app:**

1. Activa los **postbacks de eventos in-app**.
2. Configura la <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#ventana-de-postback-de-eventos-in-app">**ventana de postbacks de eventos in-app**</Anchor>.
3. Para agregar un evento SDK a la lista, haz clic en **Agregar evento**.
4. Selecciona los siguientes parámetros para cada evento:

| Nombre del parámetro | Nota |
| --- | --- |
| **Nombre de evento SDK** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea desde el SDK o desde eventos de servidor a servidor.  <br />**Consejo**: si no ves el evento que quieres en la lista, actívalo en un dispositivo con una instalación no orgánica y vuelve a comprobarlo. |
| **Identificador de evento de partner** | Introduce el nombre único o el ID de cada evento tal y como se define en Petal Ads Global. Selecciona el evento predefinido más adecuado entre 68 opciones para tu evento SDK, por ejemplo:<ul><li>`browse` (navegación)</li><li>`collection` (añadir a favoritos)</li><li>`addToCart` (añadir al carrito)</li><li>`preOrder` (realización de pedido)</li><li>`register` (registro)</li><li>`retain` (retención al día siguiente)</li><li>`paid` (pagado)</li><li>`custom` (evento de tipo personalizado)</li></ul> |
| **Opción de envío** | Los postbacks solo se pueden enviar para los eventos realizados por usuarios atribuidos a Petal Ads Global. |
| **Enviar datos de eventos** | <ul><li>**Sin valores & sin ingresos:** Envía solo el evento en sí, sin el valor del evento.</li><li>**Valores & sin ingresos:** Envía todos los parámetros, excepto el valor de ingresos.</li><li>**Valores & ingresos**: Envía todos los parámetros del evento, incluido el valor de ingresos (si existe en el evento).</li></ul> |

5. Haz clic en **Guardar integración**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Genera y guarda enlaces de atribución y envíalos al partner para que te atribuya campañas específicas, conjuntos de anuncios o anuncios únicos, tanto para campañas de UA como de retargeting. Puedes utilizar un enlace de plataforma única o un OneLink.  
<Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">Aprender más sobre la estructura del enlace de atribución y los parámetros</Anchor>.

**Para generar un enlace de atribución,** sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#attribution-link-tab">estas instrucciones</Anchor>.  
Al generar el enlace de atribución, selecciona los parámetros de la siguiente lista y asígnalos al nombre de los parámetros de Petal Ads Global detallado en la tabla.

**Parámetros de enlaces de atribución**

| Parámetro | Nombre del parámetro | Macro de Petal Ads Global | Nota |
| --- | --- | --- | --- |
| Apps asociadas que pertenecen a una plantilla OneLink relacionada para atribución multiplataforma | c  <br />af\_c\_id | \_\_CID\_\_ | Añádelo para comparar diferentes campañas en funcionamiento en Petal Ads Global. |
| Conjunto de anuncios | af\_adset  <br />af\_adset\_id | \_\_ADSETID\_\_ | Úsalo para diferenciar los conjuntos de anuncios. |
| El valor puede tener hasta 4 dígitos. | af\_ad  <br />af\_ad\_id | \_\_ADID\_\_ | Úsalo para diferenciar entre creativos dentro del conjunto de anuncios. |
| ID del sitio y del subsitio | af\_siteid  <br />af\_subsiteid | \_\_SITEID\_\_ | Úsalo para atribuir instalaciones a publishers específicos.<br /><br />**¡Práctica aconsejable!** Si hay varios publishers,<ul><li>Limita el número de ID de sitio en uso.</li><li>Usa el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">superar la limitación del ID de sitio</Anchor>.</li></ul> |
| Canal | af\_canal | \_\_CHANNEL\_\_ | Úsalo para diferenciar las ubicaciones de los anuncios.<br /><br />huaweiadsglobal<br /><br />huaweiappgalleryglobal<br /><br />Si el valor está en blanco, entonces anuncios de búsqueda de Huawei. |
| Parámetros de suscriptor | af\_sub1, af\_sub2, af\_sub3, af\_sub4 y af\_sub5 |  | Se usa para insertar valores útiles adicionales.<ul><li>Los parámetros se analizan y se incluyen en el Reporte de raw data.</li><li>Úsalos para realizar la agregación o el filtrado de datos.</li></ul> |
| Tipo de anuncio | af\_ad\_type | \_\_APP\_STATUS\_\_ | se usa para distinguir si la aplicación se activó anteriormente.<ul><li>si la campaña se usa para hacer targeting a los usuarios que instalaron la aplicación pero nunca la abrieron, el parámetro será</li></ul>af\_ad\_type=installed<ul><li>si la campaña se usa para hacer targeting a los usuarios que nunca instalaron la aplicación, el parámetro será</li></ul>af\_ad\_type=notinstalled |

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

Este partner no admite datos de costos.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Este partner no admite ingresos por publicidad.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres otorgar a Petal Ads Global. Ten en cuenta que, aunque la atribución esté deshabilitada para Petal Ads Global, la pestaña de permisos está activa y puedes otorgar el control a Petal Ads Global.

<Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">Descubre cómo otorgar permisos a Petal Ads Global.</Anchor>

</Accordion>

<div id="configuring-campaigns-on-petal-ads-global" />

## Configuración de campañas en Petal Ads Global

**Para configurar la atribución de AppsFlyer en Petal Ads Global, haz clic** [**aquí**](https://developer.huawei.com/consumer/en/doc/distribution/promotion/appsflyer-0000001122291488) **para saber más en el Centro de soporte de Huawei.**

1. <span id="EN-US_TOPIC_0000001122291488__li7712141055015"></span><span id="EN-US_TOPIC_0000001122291488__en-us_topic_0000001122291488_ol75772831710"></span>Obtén las URL de tracking de impresiones y clics en AppsFlyer.
2. Asocia AppsFlyer en Petal Ads Global.
3. Configura el postback de datos en AppsFlyer.
4. Crea una conversión en Petal Ads Global.
5. Prueba la conversión en Petal Ads Global.
6. Crea una tarea de anuncio en Petal Ads Global.
7. [Ver los datos de conversión](https://developer.huawei.com/consumer/en/doc/distribution/promotion/tracking-shu-0000001139892541) en Petal Ads Global.

<div id="data-discrepancies" />

## Discrepancias en los datos

**Nota:** En el dashboard de Petal Ads Global, los datos de conversión (p. ej., instalaciones/activaciones) tienen 2 fuentes de datos: una es AppsFlyer y la otra es HMS. Si quieres comparar los datos, como las instalaciones, entre AppsFlyer y el dashboard de Petal Ads Global, selecciona "Activations" en lugar de "Activations(HMS)" en el dashboard de Huawei.

[![](https://files.readme.io/fd2878d20c78ebc87d8536225882c8613396178b920c570677edc668dabb810e-360015414918.png)](https://files.readme.io/fd2878d20c78ebc87d8536225882c8613396178b920c570677edc668dabb810e-360015414918.png)

<div id="data-reporting-on-petal-ads-global-and-faqs-of-data-discrepancy" />

#### Reporte de datos en Petal Ads Global y preguntas frecuentes sobre discrepancias de datos

| Métrica | Fuente de datos | Preguntas frecuentes | Nota |
| --- | --- | --- | --- |
| ID de transacción de reembolso | Huawei | Impresiones de Huawei &lt; impresiones de AF | AppsFlyer registra todas las impresiones que Huawei envía a AF, mientras que Petal Ads Global realiza cierto procesamiento de datos antes de mostrar las impresiones en el dashboard de Petal Ads Global. |
| Clics | Huawei | Clics de Huawei &lt; clics de AF | AppsFlyer registra todos los clics que Huawei envía a AF, mientras que Petal Ads Global realiza cierto procesamiento de datos antes de mostrar los clics en el dashboard de Petal Ads Global. |
| Descargas | Huawei | n/d | AF no tiene esta métrica. |
| Activaciones | Las activaciones proceden de AppsFlyer; Activations HMS procede de Huawei | Activaciones de Huawei > instalaciones de AF | Las activaciones de Huawei son las instalaciones de AF. La discrepancia en los datos se debe a distintas lógicas de reporte de datos. <br /><br />Por ejemplo, un usuario descargó la aplicación desde AppGallery el 24 de diciembre y la abrió por primera vez el 25 de diciembre. En este caso, AF registrará la instalación el 25 de diciembre, mientras que Petal Ads Global registrará esta activación el 24 de diciembre. |
| Retención de Day2 y otros eventos in-app | En los que no son HMS, las fuentes de datos son AppsFlyer. | Huawei > AF | La discrepancia en los datos se debe a distintas lógicas de reporte de datos. <br /><br />Siguiendo el ejemplo anterior, el usuario se registró en la aplicación el 26 de diciembre; el dashboard general de AF mostrará los datos de registro el 25 de diciembre, igual que la fecha de instalación. Mientras que el dashboard de promociones de Petal Ads Global mostrará el registro el 24 de diciembre, igual que la fecha de descarga. |

<div data-zendesk-anchors="huawei-ads-introduction=introducci%C3%B3n-a-petal-ads-global h_01HJQZWW4SH5E9C3VXYM6NNPBA=introducci%C3%B3n-a-petal-ads-global setting-up-huawei-ads=configuraci%C3%B3n-de-petal-ads-global h_01HJQZWW4SQ3CDC1TP9NZGQHH5=configuraci%C3%B3n-de-petal-ads-global setting-up-the-petal-ads-global-integration=configuraci%C3%B3n-de-la-integraci%C3%B3n-con-petal-ads-global h_01HJRA1NPKF36ZV8AB3PKGWMXS=configuraci%C3%B3n-de-la-integraci%C3%B3n-con-petal-ads-global h_01HJQZWW4SPFQAKKPJCZ38YNV4=integration-tab activate-partner=activar-socio h_01HJQZWW4TR0XVYFYWPGAQ2FMX=activar-socio general-settings=configuraci%C3%B3n-general h_01HJQZWW4T9QYECWJKFN8SV5D5=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01HJQZWW4T62ZJSH1RBGJSC8MY=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HJQZWW4T44X5H42KAR432VN7=configuraci%C3%B3n-de-eventos-in-app h_01HJQZWW4T7TEZ27VRFPFY7DKA=attribution-link-tab h_01HJQZWW4TGDKCV8Q7B80Y5ZWG=cost-tab h_01HJQZWW4T384J7GVEEJ2EQZ0N=ad-revenue-tab h_01HJQZWW4T2P0NZ51TSF8VDEBP=permissions-tab configuring-campaigns-on-huawei-ads-global=configuraci%C3%B3n-de-campa%C3%B1as-en-petal-ads-global h_01HJQZWW4TEX7SDZSG03AK51H9=configuraci%C3%B3n-de-campa%C3%B1as-en-petal-ads-global data-discrepancies=discrepancias-en-los-datos h_01HJQZWW4VNTKP5R4KYWX80P5P=discrepancias-en-los-datos data-reporting-on-huawei-ads-and-faqs-of-data-discrepancy=reporte-de-datos-en-petal-ads-global-y-preguntas-frecuentes-sobre-discrepancias-de-datos h_01HJQZWW4VZV1R32TMGGEVNCVA=reporte-de-datos-en-petal-ads-global-y-preguntas-frecuentes-sobre-discrepancias-de-datos" />
