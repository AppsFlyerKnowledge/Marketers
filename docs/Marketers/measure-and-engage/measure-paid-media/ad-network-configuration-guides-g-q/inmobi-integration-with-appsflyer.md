---
title: Integración de inMobi con AppsFlyer
metadata:
  keywords:
    - Campaign
    - SDK
    - Configure
    - InMobi
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
  created_at: '2014-11-20T10:29:22Z'
  edited_at: '2026-08-12T12:13:55Z'
  id: 207033896
  locale: es
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/es/articles/207033896
---
> **De un vistazo:** inMobi, un partner de ad network integrado con AppsFlyer, permite a los consumidores descubrir nuevos productos y servicios a través de recomendaciones contextuales y seleccionadas en dispositivos móviles. Además de la atribución móvil basada en clics, inMobi también ofrece atribución de costo, retargeting y view-through, que puedes registrar con AppsFlyer.

<Image alt="inmobi_icon.png" src="https://files.readme.io/cbe0e88492041fc8e1781b397b67a3c8c3a09591974f2cf4fa145a18ca9e6a8d-10602685724817.png" width="128px" />

<div id="setting-up-inmobi" />

## Configuración de inMobi

**Requisito previo:** Antes de configurar la integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con él. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Para activar o editar la integración:**

1. **Para activarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Partner Marketplace**.  
   **Para editarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Integraciones activas**.
2. Selecciona la aplicación correspondiente.
3. Haz clic en **Configurar integración**.
4. En la **primera visita** aquí, deberás activar **Activar partner** para habilitar la configuración de los parámetros de integración. El selector debe estar activado mientras trabajes con el partner.  
    Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe en la sección a continuación. Para ver una descripción detallada del Encabezado de la ventana de configuración de partner, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aquí</Anchor>.

La ventana de configuración de inMobi incluye 4 pestañas activas: **Integración, Enlace de atribución, Costo** y **Permisos**. Haz clic en los siguientes elementos para leer sobre la configuración de las pestañas.

<div id="tip" />

> 👍 **Consejo**
>
> * El paso de <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#d-general-settings">Configuración general</Anchor> en la pestaña de Integración es **obligatorio para todos los partners**.
> * Todos los demás pasos son descriptivos u **opcionales**.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

<div id="activate-partners" />

### Activar los partners

En la **primera visita**, tendrás que activar el botón **Activar partner** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

<div id="note" />

> 📘 **Advertencia**
>
> Como red de TODAS las instalaciones, inMobi prefiere recibir postbacks de todas las nuevas instalaciones de tu app desde CUALQUIER fuente, incluida la orgánica. Para hacerlo, selecciona **Eventos atribuidos a cualquier partner** para enviar todos los postbacks de instalación a inMobi.

<div id="general-settings" />

### Configuración general

**gpm\_ID**

InMobi se conecta con AppsFlyer a través de un ID de red único. Si aún no tienes el ID de red, debes obtenerlo de inMobi para continuar con la integración.

![Inmobi_msc_new_3.png](https://files.readme.io/9c2efaed833211582a33b3a2bbd7d07336bc78d6e2d4e3a7645b5ca14be2fd73-360001865845.png)

**Habilitar la atribución por impresiones**

Activa esta opción si quieres atribuir las instalaciones view-through de inMobi. El control deslizante de la ventana de lookback view-through está disponible en la pestaña del enlace de atribución (se describe a continuación).

<div id="default-postbacks" />

### Postbacks predeterminados

Envía postbacks automáticos a inMobi tras las instalaciones y los re-engagements de los usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

Selecciona **Solo eventos atribuidos a este partner** para eventos provenientes solo de usuarios atribuidos a inMobi.  
Selecciona **Eventos atribuidos a cualquier partner u orgánico** para tener toda tu base de usuarios disponible para ser reportada a inMobi.

<div id="in-app-events-settings" />

### Configuración de eventos in-app

En esta sección puedes asignar tus eventos de AppsFlyer a inMobi mediante postbacks.

1. Vuelve a configurar aquí el gpm\_id de inMobi.
2. Activa los Postbacks de eventos in-app con el selector.
3. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que provienen **solo** de usuarios atribuidos a este partner.  
   **- Eventos atribuidos a cualquier partner u orgánico** para tener toda tu base de usuarios disponible para ser reportada al partner.
4. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
5. Completa los siguientes parámetros:

| Nombre de parámetro | Nota |
| --- | --- |
| **Nombre de evento del SDK** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea del SDK integrado en tu aplicación o de los eventos server-to-server.  <br />**Consejo**: Si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| **Identificador de evento de partner** | El nombre o ID único de cada evento, según lo define inMobi.  <br />Obtén el ID de evento correspondiente de inMobi e introdúcelo en el campo de texto. |
| **Enviar ingresos** | **Si esta opción no está marcada**: se envían al partner todos los parámetros del evento in-app enriquecido, con excepción del parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Cuando está marcada**: se envían todos los parámetros incluyendo el valor de ingresos (si existe en el evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que quieres enviar a inMobi para atribuir las campañas, los conjuntos de anuncios o incluso los anuncios individuales de inMobi. Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución generados para el partner. [![](https://files.readme.io/1f198f652bc960ea8d20c58d4bf704b8aff1361d105d9ed72c52c070eb88d2ce-360002187398.png)](https://files.readme.io/1f198f652bc960ea8d20c58d4bf704b8aff1361d105d9ed72c52c070eb88d2ce-360002187398.png)

[![](https://files.readme.io/03371cdc64826e77cee3bd0adb90280aa59ebddd34ec85d8946ae9646ce86ce8-360001866409.png)](https://files.readme.io/03371cdc64826e77cee3bd0adb90280aa59ebddd34ec85d8946ae9646ce86ce8-360001866409.png)

Esta pestaña se divide en distintas secciones:

<div id="attribution-link-parameters" />

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución en esta sección te permite realizar análisis en profundidad posteriormente. Puedes editar los parámetros ya definidos en el enlace de atribución, agregándolos junto con sus nuevos valores aquí.

* **Campaña** - añádela para comparar distintas campañas en funcionamiento con inMobi.  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios** - define nombres de conjuntos de anuncios para comparar distintos conjuntos de anuncios dentro de campañas específicas de inMobi.  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre del anuncio** - define nombres de anuncios para comparar distintos creativos dentro de conjuntos de anuncios específicos de campañas específicas de inMobi.  
  **Parámetro de enlace de atribución:** af\_ad
* **ID de sitio** e **ID de subsitio** - configura el parámetro de ID de sitio para atribuir instalaciones a publishers específicos. Si existen muchos publishers, te recomendamos limitar la cantidad de IDs de sitio usados y utilizar el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">superar las limitaciones de ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor** - utiliza cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el Reporte de raw data, lo que los hace muy útiles para realizar la agregación o el filtrado de datos.  
  **Parámetros del enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

[![](https://files.readme.io/f026eec1923611f33be47d7ad3b1a8654f697145be30f552cef5578fe895944c-360002234165.png)](https://files.readme.io/f026eec1923611f33be47d7ad3b1a8654f697145be30f552cef5578fe895944c-360002234165.png)

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Para obtener más información sobre <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**la estructura y los parámetros de los enlaces de atribución de AppsFlyer**</Anchor>.

<div id="retargeting-settings" />

### Configuraciones de retargeting

Cuando esta opción está habilitada, AppsFlyer reconoce un enlace como un enlace de atribución de <Anchor target="_blank" href="/marketers/es/docs/retargeting-attribution-guide">retargeting</Anchor>, en lugar de un enlace de adquisición de usuarios, al añadir `&is_retargeting=true` al enlace de registro de clics. Ten en cuenta que actualmente el retargeting solo es compatible con la atribución por clics y no con la atribución view-through.  
**Parámetro del enlace de atribución:** is\_retargeting.

Cuando la opción de retargeting está habilitada, se muestra la siguiente configuración.

![msc_new_7.png](https://files.readme.io/b90bbd6e3bea9dd862808343896b005071b7d9e564d31039c188c3ebf8e81077-360002254489.png)

1. Enlace estándar vs. OneLink

Selecciona la opción **enlace de atribución estándar** si:

* No necesitas un enlace profundo con la URL o
* Planeas utilizar solo <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">esquemas de URI</Anchor> para deep linking

selecciona **Use OneLink** for:

* Utilizar un solo enlace para aplicaciones de Android y iOS, o
* Establecer enlaces profundos empleando enlaces universales o de aplicaciones.

Ten en cuenta que seleccionar OneLink cambia el enlace de registro de clics de un enlace específico de la aplicación a una <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">URL de OneLink</Anchor>.

2. URL de deep link

Utiliza este campo si el enlace está pensado para hacer Deep Linking de los usuarios a cualquier actividad específica dentro de tu aplicación.  
**Parámetro de enlace de atribución:** af\_dp  
Puedes encontrar más información sobre la <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">solución de Deep Linking de AppsFlyer en esta guía.</Anchor>

3. Ventana de recaptación

Defina el plazo posterior al re-engagement, durante el cual los eventos in-app del usuario se atribuyen a la fuente de medios de redireccionamiento. Puede establecer el valor en días (1-90), horas (hasta 23) o incluso durante toda la vida.

**Parámetro de enlace de atribución:** af\_reengagement\_window

<div id="click-through-attribution" />

### Atribución por clic

Este control deslizante te permite establecer el **tiempo máximo entre el clic y la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de la ventana de lookback pueden atribuirse a inMobi.

**Parámetro del enlace de atribución:** af\_click\_lookback

Más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clic aquí</Anchor>.

[![](https://files.readme.io/930deba7817e7ede9504624111c3190dcd01a1f6dfb626463a844fcaa2d66930-360002254509.png)](https://files.readme.io/930deba7817e7ede9504624111c3190dcd01a1f6dfb626463a844fcaa2d66930-360002254509.png)

<div id="click-attribution-link" />

### Haz clic en el enlace de atribución

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a inMobi para que se active cuando los clientes potenciales hagan clic en el anuncio correspondiente.

<div id="view-through-attribution-lookback-window" />

### Ventana de lookback de atribución view-through

Este control deslizante te permite establecer el **tiempo máximo desde la impresión hasta la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de esta ventana de lookback, tras la impresión de un anuncio, se atribuyen a inMobi, siempre que no haya habido ningún otro clic relevante en un anuncio.

Puedes personalizar este valor para que sea de 1-23 horas o de 1-7 días.

**Parámetro del enlace de atribución:** af\_viewthrough\_lookback

Más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">atribución view-through aquí</Anchor>.

[![](https://files.readme.io/2567e7dca91c14a345616e1eb7cb0de8d1a5de7d2f9e90174ffc648fd04510c8-360002234185.png)](https://files.readme.io/2567e7dca91c14a345616e1eb7cb0de8d1a5de7d2f9e90174ffc648fd04510c8-360002234185.png)

<div id="impressions-attribution-link" />

### Enlace de atribución de impresiones

El enlace de atribución de impresiones contiene datos similares a los del enlace de registro de clics, además de una ventana de lookback diferente. Envíalo a inMobi para que se active cuando se vea el anuncio correspondiente, normalmente durante 1 segundo o más.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

AppsFlyer obtiene los detalles de costos por API. Consulta la <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabla de integración de costos de redes de publicidad</Anchor> para obtener detalles completos sobre las dimensiones, métricas y funciones admitidas. **Nota**: Los datos de costos requieren una suscripción a ROI360.

**Para habilitar la API de costos**:

* Sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">estas instrucciones de integración</Anchor>.

<Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Visualiza el estado de tu API de costos</Anchor> y la última vez que AppsFlyer logró extraer los datos de costos coincidentes en el panel de control de estado de la integración de costos (e ingresos por publicidad) o en el panel de control de la red de publicidad individual.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Este partner no admite ingresos por publicidad.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

Selecciona qué <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos otorgar</Anchor> a inMobi para acceder a tus datos y realizar diversas acciones.

<div id="note-1" />

> 📘 **Nota:**
>
> Cuando la integración esté <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">desactivada</Anchor> mientras el interruptor de Permisos aún está activado, los permisos permanecen concedidos.

</Accordion>

<div data-zendesk-anchors="setting-up-glispa=configuraci%C3%B3n-de-inmobi h_01HKA0TGE08PJDBQHFER5ZZ785=configuraci%C3%B3n-de-inmobi h_01HHVXZ7FSGDRCECE93ZF69VMS=consejo h_01HHVXZ7FSZ7W855TSN5TSPD0G=integration-tab activate-partners=activar-los-partners h_01HHVXZ7FSJ0PS5KQ0YZHVSFKF=activar-los-partners h_01HHVXZ7FSM5PT4VJRGVWDBRDK=advertencia general-settings=configuraci%C3%B3n-general h_01HHVXZ7FSDF06G1848W0YH8W6=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01HHVXZ7FS0DEZPEEH7D68SH0B=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HHVXZ7FS47Y4T3KDR732WCE6=configuraci%C3%B3n-de-eventos-in-app h_01HHVXZ7FSX2TJC13GT3TGR7ZK=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HHVXZ7FSCE4NP1XC0ZJ81858=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n retargeting-settings=configuraciones-de-retargeting h_01HHVXZ7FSAVKE25TSS98RMK8V=configuraciones-de-retargeting clickthrough-attribution=atribuci%C3%B3n-por-clic h_01HHVXZ7FTE8EZYBA4HS45MFAR=atribuci%C3%B3n-por-clic click-attribution-link=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HHVXZ7FTP962PWNMEEDB31H5=haz-clic-en-el-enlace-de-atribuci%C3%B3n viewthrough-attribution-lookback-window=ventana-de-lookback-de-atribuci%C3%B3n-view-through h_01HHVXZ7FT8HVSEXB5YWABPXNA=ventana-de-lookback-de-atribuci%C3%B3n-view-through impressions-attribution-link=enlace-de-atribuci%C3%B3n-de-impresiones h_01HHVXZ7FT7V6M8VC69EYRK700=enlace-de-atribuci%C3%B3n-de-impresiones h_01HHVXZ7FT9W1RN6P06JE53S7X=cost-tab h_01HHVXZ7FTGSKZCB57RT9GPYC9=ad-revenue-tab h_01HHVY4WHSM3B33KYACR9DJ5ZW=permissions-tab 01H88VAJH3XYP81GTFBWDBXECP=nota" />
