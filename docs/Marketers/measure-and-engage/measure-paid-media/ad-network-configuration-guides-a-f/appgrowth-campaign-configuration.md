---
title: Configuración de la campaña de App Growth
metadata:
  keywords:
    - Advertisers
    - Appgrowth
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2018-01-21T15:13:54Z'
  edited_at: '2026-09-11T00:22:52Z'
  id: 360000068905
  locale: es
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/es/articles/360000068905
---
> **De un vistazo:** Appgrowth, un partner integrado de ad network de AppsFlyer, es un productor de contenido original para profesionales del crecimiento de aplicaciones móviles. Además de la atribución móvil basada en clics, Appgrowth también ofrece atribución por impresiones, que puedes registrar con AppsFlyer.

## Configuración de Appgrowth

**Requisito previo:** una cuenta con el partner. Si no tienes una cuenta, ponte en contacto con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de Partners > Marketplace**.  
   (**Para editar una integración existente:** Ve a la pestaña **Colaborar > Integraciones de Partners > Integraciones activas**.)
2. Selecciona la aplicación correspondiente.
3. Busca el partner y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el selector **Activar partner**.   
   **Nota:** El selector **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de partner.</Anchor>

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

### Activar socio

En la **primera visita**, tendrás que activar el botón **Activate Partner** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

#### Nota:

Como red de TODAS las instalaciones, Appgrowth prefiere recibir postbacks de todas las nuevas instalaciones de tu aplicación desde CUALQUIER fuente, incluidas las orgánicas. Se recomienda seleccionar **Eventos atribuidos a cualquier partner** para enviar todos los postbacks de instalación a Appgrowth.

### Configuración general

**Habilitar la atribución por impresiones**

Activa esta opción si quieres atribuir las instalaciones por impresiones de Appgrowth. El control deslizante de la ventana de lookback view-through está disponible en la pestaña del enlace de atribución (se describe a continuación).

### Postbacks predeterminados

Envía postbacks automáticos a Appgrowth después de las instalaciones y los re-engagements de los usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

Selecciona **Solo eventos atribuidos a este partner** para eventos que procedan solo de usuarios atribuidos a Appgrowth.  
Selecciona **Eventos atribuidos a cualquier partner u orgánico** para que toda tu base de usuarios esté disponible para ser reportada a Appgrowth.

### Configuración de eventos in-app

En esta sección, puedes asignar tus eventos de AppsFlyer a Appgrowth mediante postbacks.

1. Activa los postbacks de eventos in-app
2. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que provienen **únicamente** de usuarios atribuidos a este partner.  
    **- Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada al partner.
3. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
4. Completa los siguientes parámetros:

| Nombre de parámetro | Nota |
| --- | --- |
| **Nombre de evento del SDK** | El nombre del evento tal como lo recibe AppsFlyer, ya sea del SDK integrado en tu aplicación o de eventos de servidor a servidor.  <br />**Consejo**: Si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| **Identificador de evento de partner** | El nombre único o ID de cada evento según lo definido por Appgrowth.  <br />Obtén el ID de evento correspondiente de Appgrowth y configúralo en el campo de texto. |
| **Enviar ingresos** | **Si esta opción no está marcada**: se envían al partner todos los parámetros del evento in-app enriquecido, con excepción del parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Si está marcada**: AppsFlyer envía todos los parámetros, incluido el de valor correspondiente a los ingresos (si existe en el evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que quieras enviar a Appgrowth para atribuir las campañas, los conjuntos de anuncios o los anuncios individuales de Appgrowth. Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución generados para el partner.

Esta pestaña se divide en distintas secciones:

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución en esta sección te permite realizar análisis en profundidad posteriormente. Puedes editar los parámetros ya definidos en el enlace de atribución, agregándolos junto con sus nuevos valores aquí.

* **Campaña** - añádela para comparar diferentes campañas en ejecución con Appgrowth.  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios** - define nombres de conjuntos de anuncios para comparar diferentes conjuntos de anuncios dentro de campañas específicas de Appgrowth.  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre del anuncio** - define nombres de anuncios para comparar distintos creativos dentro de conjuntos de anuncios específicos de campañas específicas de Appgrowth.  
  **Parámetro de enlace de atribución:** af\_ad
* **ID de sitio** e **ID de subsitio** - configura el parámetro de ID de sitio para atribuir las instalaciones a publishers específicos. Si existen muchos publishers, te aconsejamos limitar el número de ID de sitio usados y utilizar el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">superar las limitaciones del ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor**: usa cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el Reporte de raw data, lo que los hace muy útiles para realizar la agregación o el filtrado de datos.  
  **Parámetros del enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Para obtener más información sobre <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**la estructura y los parámetros de los enlaces de atribución de AppsFlyer**</Anchor>.

### Atribución por clic

Este control deslizante te permite establecer el **tiempo máximo desde el clic hasta la instalación**. Solo las instalaciones (primeras ejecuciones) que tengan lugar dentro de la ventana de lookback pueden atribuirse a Appgrowth.

**Parámetro del enlace de atribución:** af\_click\_lookback

Aquí encontrarás más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clics</Anchor>.

### Haz clic en el enlace de atribución

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a Appgrowth para que se active cuando los leads hagan clic en el anuncio correspondiente.

### Ventana de lookback de atribución view-through

Este control deslizante te permite establecer el **tiempo máximo de la impresión a la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de esta ventana de lookback, tras la impresión de un anuncio, se atribuyen a Appgrowth, siempre que no haya habido ningún otro clic relevante en un anuncio.

Puedes personalizar este valor para que sea de 1-23 horas o de 1-7 días.

**Parámetro del enlace de atribución:** af\_viewthrough\_lookback

Aquí encontrarás más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">atribución por impresiones</Anchor>.

### Enlace de atribución de impresiones

El enlace de atribución de impresiones contiene datos similares a los del enlace de registro de clics, además de una ventana de lookback diferente. Envíalo a Appgrowth para que se active cuando se vea un anuncio correspondiente, normalmente durante 1 segundo o más.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

AppsFlyer obtiene los detalles de costos por API. Consulta la <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabla de integración de costos de la ad network</Anchor> para ver todos los detalles de las dimensiones, métricas y funciones compatibles. **Nota**: Los datos de costos requieren una suscripción a ROI360.

**Para habilitar la API de costos**:

* Sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">estas instrucciones de integración</Anchor>.

<Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Consulta el estado de tu API de costos</Anchor> y la última vez que AppsFlyer logró extraer datos de costos coincidentes, ya sea en el dashboard de estado de la integración de costos (y de ingresos por anuncios) o en el dashboard de la ad network individual.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

La integración de los ingresos por publicidad no está disponible para Appgrowth.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres conceder a Appgrowth. Ten en cuenta que, aunque la atribución esté deshabilitada para Appgrowth, la pestaña de permisos está activa y puedes conceder el control a Appgrowth.

Usa estos selectores para otorgar permisos a la ad network para que gestione su propia configuración para tu App: Permisos de la ad network

* **Permitir la configuración de la integración**: permite que el partner configure la pestaña integración (con excepción de postbacks de eventos in-app).
* **Permitir la configuración de postbacks de eventos in-app**: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña integración.
* **Permitir el acceso a tu reporte de retención**: solo para los datos propios de retención del partner.
* **Permitir acceso a tus datos agregados de usuarios legales**: solo para los datos propios de usuarios leales del partner.
* **Permitir acceso a tus datos agregados de eventos in-app** - solo a los datos de eventos in-app propios del partner
* **Permitir acceso a tus datos agregados de ingresos**: solo para los datos de ingresos atribuidos al partner.
* **Permitir el acceso a tu dashboard de Protect360**: solo para los datos propios de Protect360 del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-appgrowth=configuraci%C3%B3n-de-appgrowth h_01HKW91NDN5S9VVD22TA6KVS2S=configuraci%C3%B3n-de-appgrowth h_01HKW91NDNDC6C4779ZPGPH6E8=integration-tab activate-partner=activar-socio h_01HKW91NDNW6G9ZKCTAHWQW5KH=activar-socio h_01HKW91NDN3N9YD7V6JAGWRS92=nota general-settings=configuraci%C3%B3n-general h_01HKW91NDNC7SRAWTRR1H31WBP=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01HKW91NDNNRR61DZVKQNHRKAG=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HKW91NDNTHR6GJVVM7A3DHS9=configuraci%C3%B3n-de-eventos-in-app h_01HKW91NDN2D5W7KPYHP5SD5B5=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HKW91NDNEVVA1Q02GBF6K80R=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n clickthrough-attribution=atribuci%C3%B3n-por-clic h_01HKW91NDNZD32XS6YJKDC8D1G=atribuci%C3%B3n-por-clic click-attribution-link=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HKW91NDN5KX133F15F82HBRV=haz-clic-en-el-enlace-de-atribuci%C3%B3n viewthrough-attribution-lookback-window=ventana-de-lookback-de-atribuci%C3%B3n-view-through h_01HKW91NDNA7ZS51JCAC445SW2=ventana-de-lookback-de-atribuci%C3%B3n-view-through impressions-attribution-link=enlace-de-atribuci%C3%B3n-de-impresiones h_01HKW91NDNXB02SM5Y4FB10NCN=enlace-de-atribuci%C3%B3n-de-impresiones h_01HKW91NDN8QRNGMDTZK9HD4D2=cost-tab h_01HKW91NDNFKKEK85D48VWF6A0=ad-revenue-tab h_01HKW91NDN82M8KCR1A722D4FK=permissions-tab" />
