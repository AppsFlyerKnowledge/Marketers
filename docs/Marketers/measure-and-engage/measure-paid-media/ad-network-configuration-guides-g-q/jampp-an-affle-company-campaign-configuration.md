---
title: Configuración de campañas de Jampp, una empresa de Affle
metadata:
  keywords:
    - Advertisers
    - Jampp
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-12-29T12:49:55Z'
  edited_at: '2026-09-11T00:23:56Z'
  id: 115000151226
  locale: es
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/es/articles/115000151226
---
> **De un vistazo:** Jampp, una empresa de Affle y partner integrado de AppsFlyer, ofrece una plataforma de marketing de performance para adquirir clientes de aplicaciones y hacer retargeting. Además de la atribución móvil basada en clics, Jampp también ofrece atribución de costo, retargeting y view-through, que puedes registrar con AppsFlyer.

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/jampp.png" width="213px" />

<div id="setting-up-jampp-integration" />

## Configuración de la integración de Jampp

**Requisito previo:** Una cuenta con el partner. Si no tienes una cuenta, ponte en contacto con el partner para abrir una antes de configurar la integración.

**Configura una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de Partners > Marketplace**.  
   (**Para editar una integración existente:** ve a la pestaña **Colaborar > Integraciones de Partners > Integraciones activas**.)
2. Selecciona la aplicación correspondiente.
3. Busca el partner y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el selector **Activar partner**.   
   **Nota:** El selector **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de Partners</Anchor>

<div id="h_01HKW1V0MN1PQ9HWC0TK0WSWER" />

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

<div id="activate-partner" />

### Activar socio

En la **primera visita** aquí, deberás alternar a continuación. ACTIVA el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

<div id="note" />

> 📘 **Nota:**
>
> Como red de TODAS las instalaciones, Jampp prefiere recibir postbacks de todas las nuevas instalaciones de tu aplicación desde CUALQUIER fuente, incluida la orgánica. Para hacerlo, selecciona **Eventos atribuidos a cualquier partner** para enviar todos los postbacks de instalación a Jampp.

<div id="general-settings" />

### Configuración general

**Habilitar la atribución por impresiones**

Activa esta opción si quieres atribuir instalaciones por impresiones de Jampp. El control deslizante de la ventana de lookback view-through está disponible en la pestaña del enlace de atribución (se describe a continuación).

<div id="default-postbacks" />

### Postbacks predeterminados

Envía postbacks automáticos a Jampp después de las instalaciones y los re-engagements de los usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

Selecciona **Solo eventos atribuidos a este partner** para eventos procedentes solo de usuarios atribuidos a Jampp.  
Selecciona **Eventos atribuidos a cualquier partner u orgánicos** para que toda tu base de usuarios esté disponible para reportarla a Jampp.

<div id="in-app-events-settings" />

### Configuración de eventos in-app

En esta sección puedes asignar tus eventos de AppsFlyer a Jampp mediante postbacks.

1. Activa los postbacks de eventos in-app.
2. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que provienen **únicamente** de usuarios atribuidos a este partner.  
    **- Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada al partner.
3. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
4. Completa los siguientes parámetros:

| Nombre de Parámetro | Description |
| --- | --- |
| **Nombre del evento del SDK** | El nombre del evento, tal como lo recibe AppsFlyer, ya sea desde el SDK integrado con tu aplicación o desde eventos de servidor a servidor.  <br />**Consejo** - Si no ves el evento que quieres en la lista, asegúrate de activar el evento en un dispositivo con una Instalación no orgánica y vuelve a comprobarlo. |
| **Identificador de Evento de Partner** | El nombre único o el ID de cada evento, según se define en Jampp.  <br />Obtén el ID de evento correspondiente de Jampp e introdúcelo en el campo de texto. |
| **Enviar Ingresos** | **Si no está marcada** - Se envían al partner todos los parámetros del evento in-app enriquecido, excepto el parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Si está marcada** - Se envían todos los parámetros, incluido el valor de ingresos (si existe en el evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que quieras enviar a Jampp para atribuir las campañas, los conjuntos de anuncios o incluso los anuncios individuales de Jampp. Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución generados para el partner.

Esta pestaña se divide en distintas secciones:

<div id="attribution-link-parameters" />

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución en esta sección te permite realizar análisis en profundidad posteriormente. Los parámetros que ya están definidos en el enlace de atribución pueden editarse agregándolos junto con sus valores nuevos en esta sección.

* **Campaña** - añádela para comparar diferentes campañas en funcionamiento con Jampp.  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios** - define nombres de conjuntos de anuncios para comparar diferentes conjuntos de anuncios dentro de campañas específicas de Jampp.  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre del anuncio** - define nombres de anuncios para comparar diferentes creatividades dentro de conjuntos de anuncios específicos de campañas específicas de Jampp.  
  **Parámetro de enlace de atribución:** af\_ad
* **ID de sitio** e **ID de subsitio** - configura el parámetro de ID de sitio para atribuir las instalaciones a publishers específicos. Si existen muchos publishers, te recomendamos limitar el número de IDs de sitio usados y utilizar el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">superar las limitaciones del ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor**: utiliza cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el reporte de raw data, lo que los hace muy útiles para realizar la agregación o el filtrado de datos.  
  **Parámetros del enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Para obtener más información sobre <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**la estructura y los parámetros de los enlaces de atribución de AppsFlyer**</Anchor>.

<div id="retargeting-settings" />

### Configuraciones de retargeting

Cuando está habilitada, AppsFlyer reconoce un enlace como un <Anchor target="_blank" href="/marketers/es/docs/retargeting-attribution-guide">enlace de atribución de retargeting</Anchor>, en lugar de un enlace de adquisición de usuarios, al añadir `&is_retargeting=true` al enlace de registro de clics. Ten en cuenta que actualmente el retargeting solo es compatible con la atribución por clic y no con la atribución view-through.  
**Parámetro del enlace de atribución:** is\_retargeting.

Cuando la opción de retargeting está habilitada, se muestra la siguiente configuración.

1. Enlace estándar vs. OneLink

Selecciona la opción ***enlace de atribución estándar*** si:

* No necesitas un enlace profundo con la URL o
* Planea utilizar solo <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">esquemas de URI</Anchor> para Deep Linking

Selecciona ***Usar OneLink*** para:

* Utilizar un solo enlace para aplicaciones de Android y iOS, o
* Establecer enlaces profundos empleando enlaces universales o de aplicaciones.

Ten en cuenta que, al seleccionar OneLink, el enlace de registro de clics pasa de ser específico de la aplicación a ser una <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">URL de OneLink</Anchor>.

2. URL de deep link

Utiliza este campo si el enlace está pensado para dirigir a los usuarios mediante Deep Linking a cualquier actividad específica dentro de tu aplicación.  
**Parámetro de enlace de atribución:** af\_dp  
Puedes encontrar más información sobre la <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">solución de AppsFlyer para Deep Linking en esta guía.</Anchor>

3. Ventana de recaptación

Defina el plazo posterior al re-engagement, durante el cual los eventos in-app del usuario se atribuyen a la fuente de medios de redireccionamiento. Puede configurar el valor en días (1-90), horas (hasta 23) o incluso de por vida.

**Parámetro de enlace de atribución:** af\_reengagement\_window

<div id="click-through-attribution" />

### Atribución por clic

Este control deslizante te permite establecer el **tiempo máximo desde el clic hasta la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de la ventana de lookback pueden atribuirse a Jampp.

**Parámetro de enlace de atribución:** af\_click\_lookback

Más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clic aquí</Anchor>.

<div id="click-attribution-link" />

### Haz clic en el enlace de atribución

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a Jampp para que se active cuando los leads hagan clic en el anuncio correspondiente.

<div id="view-through-attribution-lookback-window" />

### Ventana de lookback de atribución view-through

Este control deslizante te permite establecer el **tiempo máximo desde la impresión hasta la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de esta ventana de lookback, tras la impresión de un anuncio, se atribuyen a Jampp, siempre que no haya habido ningún otro clic relevante en un anuncio.

Puedes personalizar este valor para que sea de 1-23 horas o de 1-7 días.

**Parámetro de enlace de atribución:** af\_viewthrough\_lookback

Más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">atribución por impresiones aquí</Anchor>.

<div id="impressions-attribution-link" />

### Enlace de atribución de impresiones

El enlace de atribución para impresiones contiene datos de atribución similares a los del enlace de registro del clic (aparte de la ventana retrospectiva diferente). Envíalo a Jampp para que se active cuando se vea el anuncio correspondiente, normalmente durante 1 segundo o más.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

AppsFlyer obtiene los detalles de costos por API. Consulta la <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabla de integración de costos de ad network</Anchor> para ver todos los detalles sobre las dimensiones, métricas y funciones compatibles. **Nota**: Los datos de costos requieren una suscripción a ROI360.

**Para habilitar la API de costos**:

* Sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">estas instrucciones de integración</Anchor>.

<Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Visualiza el estado de tu API de costos</Anchor> y la última vez que AppsFlyer logró extraer los datos de costos coincidentes en el dashboard de estado de la integración de costos (e ingresos por publicidad) o en el dashboard de la ad network individual.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

La integración de ingresos por publicidad no está disponible para este partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres otorgarle a Jampp, tanto si el partner actúa como ad network, agencia o incluso como ambas cosas. Ten en cuenta que, incluso si la atribución estuviera deshabilitada para Jampp, la pestaña de permisos seguiría activa y podrías otorgarle el control a Jampp.

Usa estos selectores para otorgarle permisos a una ad network para que maneje su propia configuración de tu aplicación:

<div id="ad-network-permissions" />

### Permisos de ad network

* ***Permitir la configuración de la integración***: permite que el partner configure la pestaña de integración (excepto postbacks de eventos in-app).
* ***Permitir la configuración de postbacks de eventos in-app***: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña de integración.
* ***Permitir el acceso a tu reporte de retención***: solo para los propios datos de retención del partner.
* ***Permitir acceso a tus datos agregados de usuarios fieles***: solo a los datos de usuarios fieles propios del partner
* ***Permitir acceso a tus datos agregados de eventos in-app** -* solo a los datos de eventos in-app propios del partner
* ***Permitir acceso a tus datos agregados de ingresos*a** - solo a los datos de ingresos atribuidos al partner
* ***Permitir el acceso a tu panel de control Protect360***: solo a los datos de Protect360 propios del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

<div id="agency-permissions" />

### Permisos de la agencia

Utiliza estos selectores para otorgar permisos a una agencia para que gestione su propia configuración para tu aplicación:

* ***Selector principal*** - Configúralo en On para mostrar las opciones de permisos de agencia
* ***Permitir el acceso a tu reporte de retención*** - solo a los propios datos de retención de la agencia
* ***Permitir el acceso a datos agregados orgánicos.***
* ***Permitir configurar postbacks de eventos in-app*** - permite que la agencia configure en la pestaña de integración la asignación de postbacks de eventos in-app para sí misma

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permisos-de-la-agencia">permisos a las agencias</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-jampp-integration=configuraci%C3%B3n-de-la-integraci%C3%B3n-de-jampp h_01HKW1V0MNP0000KY7SHWQNF16=configuraci%C3%B3n-de-la-integraci%C3%B3n-de-jampp h_01HKW1V0MNSFFFKSQJTDF91NCS=integration-tab activate-partner=activar-socio h_01HKW1V0MN2CQGVKBRQ67SMQ2P=activar-socio h_01HKW1V0MNKR4M4EA5JNT361Y1=nota general-settings=configuraci%C3%B3n-general h_01HKW1V0MNDPJ67HMC0GXYG55B=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01HKW1V0MNVEYNY7PZ12QX30QP=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HKW1V0MN1Q4AR9HASGTCM6AJ=configuraci%C3%B3n-de-eventos-in-app h_01HKW1V0MN5HD3TN7AQ1SS8VM7=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HKW1V0MNDJG02Q0V315N2HAZ=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n retargeting-settings=configuraciones-de-retargeting h_01HKW1V0MNHZ2JKKEAYWWQ36BA=configuraciones-de-retargeting clickthrough-attribution=atribuci%C3%B3n-por-clic h_01HKW1V0MNKJCETPMASGRYJ368=atribuci%C3%B3n-por-clic click-attribution-link=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HKW1V0MND4RT49E8TX448Q9H=haz-clic-en-el-enlace-de-atribuci%C3%B3n viewthrough-attribution-lookback-window=ventana-de-lookback-de-atribuci%C3%B3n-view-through h_01HKW1V0MN3VB4HJFDKAH1KAAG=ventana-de-lookback-de-atribuci%C3%B3n-view-through impressions-attribution-link=enlace-de-atribuci%C3%B3n-de-impresiones h_01HKW1V0MN86VRX5VPB1K8HACD=enlace-de-atribuci%C3%B3n-de-impresiones h_01HKW1V0MNY13FH61E5AJ27NWJ=cost-tab h_01HKW1V0MNG84N4GKFDACB498E=ad-revenue-tab h_01HKW1V0MNQHRZCMV9WZMFY1G5=permissions-tab ad-network-permissions=permisos-de-ad-network h_01HKW1V0MNP0K2WYMQ1AHBKH17=permisos-de-ad-network agency-permissions=permisos-de-la-agencia h_01HKW1V0MNV7HGV88HVVPG1397=permisos-de-la-agencia" />
