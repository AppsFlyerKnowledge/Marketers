---
title: Configuración de la campaña de Nativex (anteriormente Mobvista)
metadata:
  keywords:
    - mobvista
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
  created_at: '2016-03-28T09:15:13Z'
  edited_at: '2026-08-22T00:25:20Z'
  id: 208209476
  locale: es
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/es/articles/208209476
---
> **De un vistazo:** Nativex, partner integrado de AppsFlyer, es una plataforma de marketing móvil que ofrece soluciones de adquisición de usuarios, analítica y monetización a desarrolladores y marcas móviles de todo el mundo. Además de la atribución móvil basada en clics, Nativex también ofrece atribución de costo y view-through, que puedes registrar con AppsFlyer.

![nativex.png](https://files.readme.io/840450215d38dc171452049ce1e9ce8c5f289e489fcb985a8d7ecb745fd11ede-49783409596049.png)

<div id="setting-up-nativex" />

## Configuración de Nativex

**Requisito previo:** Una cuenta con el Partners. Si no tienes una cuenta, ponte en contacto con el Partners para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Collaborate > Partner Integrations > Marketplace** .  
   (**Para editar una integración existente:** Ve a la pestaña **Collaborate > Partner Integrations > Active integrations** .)
2. Selecciona la aplicación correspondiente.
3. Busca el Partners y selecciona **Integrate**.
4. En la pestaña **Integración**, activa el conmutador **Activate partner**.   
   **Nota:** El selector **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de partners</Anchor>

La ventana de configuración de Nativex incluye 4 pestañas activas: Integración, enlace de atribución, Costo y Permisos. Haz clic en los elementos que aparecen a continuación para obtener más información sobre la configuración de las pestañas.

<div id="tip" />

> 👍 **Consejo**
>
> * El paso <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#d-general-settings">General Settings</Anchor> de la pestaña Integración es **obligatorio** para todos los Partners
> * Todos los demás pasos son descriptivos u **opcionales**.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

<div id="activate-partners" />

### Activar los partners

En la **primera visita** aquí, tendrás que activar el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

<div id="general-settings" />

### Configuración general

**Mobvista\_campuuid**

Nativex se conecta con AppsFlyer a través de un ID de red único. Si todavía no tienes el ID de red, debes obtenerlo de Nativex para continuar con la integración.

**Habilitar la atribución por impresiones**

Activa esta opción si quieres atribuir instalaciones view-through de Nativex. El control deslizante de la ventana de lookback view-through está disponible en la pestaña del enlace de atribución (se describe a continuación).

<div id="default-postbacks" />

### Postbacks predeterminados

Envía postbacks automáticos a Nativex después de las instalaciones y los re-engagements de los usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

Selecciona **Solo eventos atribuidos a este partner** para eventos provenientes solo de usuarios atribuidos a Nativex.  
Selecciona **Eventos atribuidos a cualquier partner u orgánico** para que toda tu base de usuarios esté disponible para ser reportada a Nativex.

<div id="in-app-events-settings" />

### Configuración de eventos in-app

En esta sección puedes asignar tus eventos de AppsFlyer a Nativex mediante postbacks.

1. Vuelve a configurar aquí el ID de red de Nativex
2. Activa los postbacks de eventos in-app.
3. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que provienen **únicamente** de usuarios atribuidos a este partner.  
    **- Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada al partner.
4. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
5. Completa los siguientes parámetros:

| Nombre de parámetro | Nota |
| --- | --- |
| **Nombre de evento del SDK** | El nombre del evento tal como lo recibe AppsFlyer, ya sea del SDK integrado en tu aplicación o de eventos de servidor a servidor.  <br />**Consejo**: Si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| **Identificador de evento de partner** | El nombre o ID único de cada evento según se define en Nativex.  <br />Obtén el ID de evento correspondiente de Nativex e introdúcelo en el campo de texto. |
| **Enviar ingresos** | **Si esta opción no está marcada**: se envían al partner todos los parámetros del evento in-app enriquecido, con excepción del parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Si está marcada**: AppsFlyer envía todos los parámetros, incluido el de valor correspondiente a los ingresos (si existe en el evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que quieras enviar a Nativex para atribuir las campañas, los conjuntos de anuncios o incluso los anuncios individuales de Nativex. Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución generados para el partner.

Esta pestaña se divide en distintas secciones:

<div id="attribution-link-parameters" />

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución aquí te permite realizar análisis detallados más adelante. Puedes editar los parámetros ya definidos en el enlace de atribución, agregándolos junto con sus nuevos valores aquí.

* **Campaña** - añádela para comparar diferentes campañas en funcionamiento con Nativex.  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios**: define nombres de conjuntos de anuncios para comparar distintos conjuntos de anuncios dentro de campañas específicas de Nativex.  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre del anuncio** - define nombres de anuncios para comparar distintos creativos dentro de conjuntos de anuncios específicos, en campañas específicas de Nativex.  
  **Parámetro de enlace de atribución:** af\_ad
* **ID de sitio** e **ID de subsitio** - configura el parámetro de ID de sitio para atribuir instalaciones a publishers específicos. Si existen muchos publishers, te recomendamos limitar el número de IDs de sitio usados y utilizar el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder las limitaciones del ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor** - utiliza cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el reporte de raw data, lo que los hace muy útiles para realizar la agregación o el filtrado de datos.  
  **Parámetros de enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Para obtener más información sobre <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**la estructura y los parámetros de los enlaces de atribución de AppsFlyer**</Anchor>.

<div id="click-through-attribution" />

### Atribución por clic

Este control deslizante te permite establecer el **tiempo máximo desde el clic hasta la instalación**. Solo las instalaciones (primeras ejecuciones) que tengan lugar dentro de la ventana de lookback pueden atribuirse a Nativex.

**Parámetro del enlace de atribución:** af\_click\_lookback

Aquí encontrarás más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clic</Anchor>.

<div id="click-attribution-link" />

### Haz clic en el enlace de atribución

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a Nativex para que se active cuando los leads hagan clic en un anuncio correspondiente.

<div id="view-through-attribution-lookback-window" />

### Ventana de lookback de atribución view-through

Este control deslizante te permite establecer el **tiempo máximo de la impresión a la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de esta ventana de lookback, tras la impresión de un anuncio, se atribuyen a Nativex, siempre que no haya habido ningún otro clic relevante en un anuncio.

Puedes personalizar este valor para que sea de 1-23 horas o de 1-7 días.

**Parámetro de enlace de atribución:** af\_viewthrough\_lookback

Aquí encontrarás más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">atribución por impresiones</Anchor>.

<div id="impressions-attribution-link" />

### Enlace de atribución de impresiones

El enlace de atribución de impresiones contiene datos similares a los del enlace de registro de clics, además de una ventana de lookback diferente. Envíalo a Nativex para que se active cuando se vea un anuncio correspondiente, normalmente durante 1 segundo o más.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

Nativex envía automáticamente datos de costo de CPI cifrados en el enlace de atribución para todas las instalaciones.

Para ver la lista completa de Partners que admiten datos de costos, haz clic <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#información-adicional">aquí</Anchor>.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Este partner no admite ingresos por publicidad.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres conceder a Nativex, tanto si el partner actúa como ad network, agencia o ambos. Ten en cuenta que, incluso si la atribución está deshabilitada para Nativex, la pestaña Permisos está activa y puedes otorgarle el control a Nativex.

<div id="ad-network-permissions" />

### Permisos de ad network

Utiliza estos selectores para otorgar permisos a Nativex para que gestione su propia configuración para tu app:

* ***Permitir la configuración de la integración*** - permite que Nativex configure la pestaña de integración (excepto los postbacks de eventos in-app)
* ***Permitir la configuración de postbacks de eventos in-app*** - permite que Nativex configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña de integración
* ***Permitir el acceso a tu reporte de retención*** - solo para los propios datos de retención de Nativex
* ***Permitir el acceso a tu dashboard de Protect360*** - solo a los datos de Protect360 propios de Nativex, siempre que la funcionalidad esté habilitada para el anunciante

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

<div id="agency-permissions" />

### Permisos de la agencia

Utiliza estos selectores para otorgar permisos a una agencia para que gestione su propia configuración para tu aplicación:

* ***Selector principal*** - configúralo en Activado para mostrar las opciones de permisos de la agencia
* ***Permitir el acceso a tu reporte de retención***: solo para los propios datos de retención de la agencia
* ***Permitir el acceso a datos agregados orgánicos.***
* ***Permitir la configuración de postbacks de eventos in-app***: permite que la agencia configure la asignación de postbacks de eventos in-app a sí misma en la pestaña de integración

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permisos-de-la-agencia">permisos a las agencias</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-mobvista=configuraci%C3%B3n-de-nativex h_01HKW7VFYJ6CZP5JD29YAS3AAH=configuraci%C3%B3n-de-nativex h_01HKW7VFYJ02HSZ963PX5H38ZS=consejo h_01HKW7VFYJXNP3AP7FZPFBRHA7=integration-tab activate-partners=activar-los-partners h_01HKW7VFYJB9F9M8KGEA52ZQGD=activar-los-partners general-settings=configuraci%C3%B3n-general h_01HKW7VFYJDAT6G9VSC5H50Y9K=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01HKW7VFYJVW66881ZHG2Q1B31=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HKW7VFYJA1919WZ0XPY8SP98=configuraci%C3%B3n-de-eventos-in-app h_01HKW7VFYJKD1BHDDAG8VKFTYB=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HKW7VFYJFGKPDDBT09T3BXAN=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n clickthrough-attribution=atribuci%C3%B3n-por-clic h_01HKW7VFYJMYJ508P8E3B5WNN2=atribuci%C3%B3n-por-clic click-attribution-link=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HKW7VFYJ6N5JMZTDBAKX02A4=haz-clic-en-el-enlace-de-atribuci%C3%B3n viewthrough-attribution-lookback-window=ventana-de-lookback-de-atribuci%C3%B3n-view-through h_01HKW7VFYK0YRYZXMPFRJNQJKP=ventana-de-lookback-de-atribuci%C3%B3n-view-through impressions-attribution-link=enlace-de-atribuci%C3%B3n-de-impresiones h_01HKW7VFYKD6S2NZ280VXRQT1F=enlace-de-atribuci%C3%B3n-de-impresiones h_01HKW7VFYKDN59CAGE3JC11G7D=cost-tab h_01HKW7VFYK3AGC81SBA00C43AD=ad-revenue-tab h_01HKW7VFYKS66EAP51QECZPFQH=permissions-tab ad-network-permissions=permisos-de-ad-network h_01HKW7VFYKRE972AJAM499H241=permisos-de-ad-network agency-permissions=permisos-de-la-agencia h_01HKW7VFYK1T10MR5AJ436C2NS=permisos-de-la-agencia" />
