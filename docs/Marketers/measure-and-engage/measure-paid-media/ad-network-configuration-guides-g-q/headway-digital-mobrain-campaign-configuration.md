---
title: Configuración de la campaña de Headway Digital (Mobrain)
metadata:
  keywords:
    - headway
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
  created_at: '2016-04-04T14:59:03Z'
  edited_at: '2026-09-11T00:23:42Z'
  id: 209803183
  locale: es
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/es/articles/209803183
---
> **De un vistazo:** Headway Digital, un partner de ad network integrado con AppsFlyer, proporciona soluciones de marketing centradas en los datos que impulsan la ejecución y ofrecen potentes insights de marca en móviles. Además de la atribución móvil basada en clics, ofrecen atribución de costos, retargeting y view-through, que puedes registrar con AppsFlyer.

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mobrain.png?v=1" width="213px" />

<div id="setting-up-headway-digital-mobrain" />

## Configurar Headway Digital (Mobrain)

**Requisito previo:** Una cuenta con el Partners. Si no tienes una cuenta, ponte en contacto con el Partners para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Collaborate > Partner Integrations > Marketplace**.  
   (**Para editar una integración existente:** Ve a la pestaña **Collaborate > Partner Integrations > Active integrations**.)
2. Selecciona la aplicación correspondiente.
3. Busca el Partners y selecciona **Integrate**.
4. En la pestaña **Integración**, activa el selector **Activate partner**.   
   **Nota:** El selector **debe permanecer activado (activo) mientras trabajes con el Partners**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de partners</Anchor>

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

<div id="activate-partner" />

### Activar socio

En la **primera visita** aquí, tendrás que activar el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

<div id="general-settings" />

### Configuración general

**Habilitar la atribución por impresiones**

Activa esta opción si quieres atribuir las instalaciones por impresiones de Mobrain. El control deslizante de la ventana de lookback view-through está disponible en la pestaña del enlace de atribución (se describe a continuación).

<div id="default-postbacks" />

### Postbacks predeterminados

Envía postbacks automáticos a Mobrain después de las instalaciones y los re-engagements de los usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

Selecciona **Solo eventos atribuidos a este partner** para los eventos que provienen solo de usuarios atribuidos a Mobrain.  
Selecciona **Eventos atribuidos a cualquier partner u orgánico** para tener toda tu base de usuarios disponible para ser reportada a Mobrain.

<div id="in-app-events-settings" />

### Configuración de eventos in-app

En esta sección, puedes asignar tus eventos de AppsFlyer a Mobrain mediante postbacks.

1. Activa los postbacks de eventos in-app.
2. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que provienen **únicamente** de usuarios atribuidos a este partner.  
    **- Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada al partner.
3. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
4. Completa los siguientes parámetros:

| Nombre de Parámetro | Description |
| --- | --- |
| **Nombre del evento del SDK** | El nombre del evento, tal como lo recibe AppsFlyer, ya sea desde el SDK integrado en tu aplicación o desde eventos de servidor a servidor.  <br />**Consejo** - Si no ves el evento que quieres en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a comprobarlo. |
| **Identificador de Evento de Partner** | El nombre o ID único de cada evento, tal como se define del lado de Mobrain.  <br />Obtén el ID de evento correspondiente de Mobrain y configúralo en el campo de texto. |
| **Enviar Ingresos** | **Si esta opción no está marcada**: se envían al partner todos los parámetros del evento in-app enriquecido, excepto el parámetro de ingresos, que está incluido en el parámetro **af\_revenue**.  <br />**Si esta opción está marcada**: se envían todos los parámetros, incluido el valor de ingresos (si existe en el evento). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

En esta pestaña, puedes crear los enlaces de atribución que quieras enviar a Mobrain para atribuir las campañas, los conjuntos de anuncios o incluso los anuncios individuales de Mobrain. Ten en cuenta que AppsFlyer NO guarda los enlaces de atribución generados para el partner.

Esta pestaña se divide en distintas secciones:

<div id="attribution-link-parameters" />

### Parámetros de enlaces de atribución

En esta sección, selecciona los parámetros que quieres agregar al enlace de atribución.

Agregar parámetros al enlace de atribución aquí te permitirá realizar análisis detallados más adelante. Los parámetros que ya están definidos en el enlace de atribución pueden editarse agregándolos junto con sus valores nuevos en esta sección.

* **Campaña**: añádela para comparar distintas campañas en funcionamiento con Mobrain.  
  **Parámetro de enlace de atribución:** c
* **Conjunto de anuncios**: define nombres de conjuntos de anuncios para comparar distintos conjuntos de anuncios dentro de campañas específicas de Mobrain.  
  **Parámetro de enlace de atribución:** af\_adset
* **Nombre de anuncio**: define nombres de anuncios para comparar distintos creativos dentro de conjuntos de anuncios específicos de campañas específicas de Mobrain.  
  **Parámetro del enlace de atribución:** af\_ad
* **ID de sitio** e **ID de subsitio** - configura el parámetro de ID de sitio para atribuir instalaciones a publishers específicos. Si existen muchos publishers, te recomendamos limitar el número de ID de sitio usados y utilizar el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">superar las limitaciones del ID de sitio</Anchor>.  
  **Parámetros del enlace de atribución:** af\_siteid y af\_sub\_siteid
* **Parámetros de suscriptor**: utiliza cualquiera de los 5 parámetros de suscriptor para insertar valores útiles. Ten en cuenta que estos parámetros se analizan y aparecen en el reporte de raw data, lo que los hace muy útiles para realizar la agregación o el filtrado de datos.  
  **Parámetros del enlace de atribución:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

Agrega cualquier otro parámetro al enlace de atribución simplemente escribiéndolo en un nuevo cuadro de parámetro. Para obtener más información sobre <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">**la estructura y los parámetros de los enlaces de atribución de AppsFlyer**</Anchor>.

<div id="retargeting-settings" />

### Configuraciones de retargeting

Cuando esta opción está habilitada, AppsFlyer reconoce un enlace como un enlace de atribución de <Anchor target="_blank" href="/marketers/es/docs/retargeting-attribution-guide">retargeting</Anchor>, en lugar de un enlace de adquisición de usuarios, al añadir `&is_retargeting=true` al enlace de registro de clics. Ten en cuenta que actualmente el retargeting solo es compatible con la atribución por clics y no con la atribución view-through.  
**Parámetro del enlace de atribución:** is\_retargeting.

Cuando la opción de retargeting está habilitada, se muestra la siguiente configuración.

1. Enlace estándar vs. OneLink

Selecciona la opción ***enlace de atribución estándar*** si:

* No necesitas un enlace profundo con la URL o
* Planeas usar solo <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">esquemas de URI</Anchor> para deep linking

selecciona ***Usar OneLink*** para:

* Utilizar un solo enlace para aplicaciones de Android y iOS, o
* Establecer enlaces profundos empleando enlaces universales o de aplicaciones.

Ten en cuenta que, al seleccionar OneLink, el enlace de registro de clics deja de ser específico de la aplicación y pasa a ser una <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">URL de OneLink</Anchor>.

2. URL de deep link

Usa este campo si el enlace está pensado para llevar a los usuarios mediante deep linking a una actividad específica dentro de tu aplicación.  
**Parámetro del enlace de atribución:** af\_dp  
Puedes encontrar más información sobre la solución de AppsFlyer para deep linking en <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">esta guía.</Anchor>

3. Ventana de recaptación

Defina el plazo posterior al re-engagement, durante el cual los eventos in-app del usuario se atribuyen a la fuente de medios de redireccionamiento. Puede configurar el valor en días (1-90), horas (hasta 23) o incluso de por vida.

**Parámetro del enlace de atribución:** af\_reengagement\_window

<div id="click-through-attribution" />

### Atribución por clic

Este control deslizante te permite establecer el **tiempo máximo entre el clic y la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de la ventana de lookback pueden atribuirse a Mobrain.

**Parámetro del enlace de atribución:** af\_click\_lookback

Aquí encontrarás más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clics</Anchor>.

<div id="click-attribution-link" />

### Haz clic en el enlace de atribución

Este es el enlace de atribución que contiene toda la información de configuración que definiste para dicho enlace. Envíalo a Mobrain para que se active cuando los clientes potenciales hagan clic en el anuncio correspondiente.

<div id="view-through-attribution-lookback-window" />

### Ventana de lookback de atribución view-through

Este control deslizante te permite establecer el **tiempo máximo entre la impresión y la instalación**. Solo las instalaciones (primeras aperturas) que tengan lugar dentro de esta ventana de lookback tras la impresión de un anuncio se atribuyen a Mobrain, siempre que no haya habido ningún otro clic relevante en un anuncio.

Puedes personalizar este valor para que sea de 1-23 horas o de 1-7 días.

**Parámetro de enlace de atribución:** af\_viewthrough\_lookback

Más detalles sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">atribución view-through aquí</Anchor>.

<div id="impressions-attribution-link" />

### Enlace de atribución de impresiones

El enlace de atribución para impresiones contiene datos de atribución similares a los del enlace de registro del clic (aparte de la ventana retrospectiva diferente). Envíalo a Mobrain para que se active cuando se vea el anuncio correspondiente, normalmente durante 1 segundo o más.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

Mobrain envía automáticamente datos de costes de CPI en el enlace de atribución para todas las instalaciones.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Mobrain no es compatible con los datos de ingresos por publicidad.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres otorgar a Mobrain, tanto si el partner actúa como ad network, agencia o ambas. Ten en cuenta que, aunque la atribución esté deshabilitada para Mobrain, la pestaña de permisos está activa y puedes otorgar el control a Mobrain.

Usa estos selectores para otorgarle permisos a una ad network para que maneje su propia configuración de tu aplicación:

<div id="ad-network-permissions" />

### Permisos de ad network

* ***Permitir la configuración de la integración***: permite que el partner configure la pestaña de integración (excepto los postbacks de eventos in-app)
* ***Permitir la configuración de postbacks de eventos in-app***: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña de integración.
* ***Permitir el acceso a tu reporte de retención***: solo para los propios datos de retención del partner.
* ***Permitir el acceso a tus datos agregados de usuarios fieles*** - solo a los datos de usuarios fieles propios del Partners
* ***Permitir el acceso a tus datos agregados de eventos in-app** -* solo a los datos de eventos in-app propios del Partners
* ***Permitir acceso a tus datos agregados de ingresos*a** - solo a los datos de ingresos atribuidos al partner
* ***Permitir el acceso a tu panel de control Protect360***: solo a los datos de Protect360 propios del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

<div id="agency-permissions" />

### Permisos de la agencia

Utiliza estos selectores para otorgar permisos a una agencia para que gestione su propia configuración para tu aplicación:

* ***Selector principal***: actívalo para mostrar las opciones de permisos para agencias
* ***Permitir la configuración de postbacks de eventos in-app***: permite que la agencia configure en la pestaña de integración la asignación de postbacks de eventos in-app a sí misma
* ***Permitir el acceso a datos agregados orgánicos.***
* ***Permitir el acceso a tu reporte de retención***: solo para los propios datos de retención de la agencia

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permisos-de-la-agencia">permisos a las agencias</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-headway-digital-mobrain=configurar-headway-digital-mobrain h_01HKA1AEYTDZ5H5J33Z9FW10QW=configurar-headway-digital-mobrain h_01HKA1AEYV5A1J168WK2D6FTVP=integration-tab activate-partner=activar-socio h_01HKA1AEYVAM34GGG30SKTGK3X=activar-socio general-settings=configuraci%C3%B3n-general h_01HKA1AEYVQEEJZQBVXG29T999=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01HKA1AEYVPH65388RM6SCPH8H=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HKA1AEYVYSNGNKR738X9QCKB=configuraci%C3%B3n-de-eventos-in-app h_01HKA1AEYV3C0VN31RM44N2Q93=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HKA1AEYV50HE549X8FGZ48DJ=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n retargeting-settings=configuraciones-de-retargeting h_01HKA1AEYVDJSSQGSCYRK75J35=configuraciones-de-retargeting clickthrough-attribution=atribuci%C3%B3n-por-clic h_01HKA1AEYV721RG0D13GQDTAFH=atribuci%C3%B3n-por-clic click-attribution-link=haz-clic-en-el-enlace-de-atribuci%C3%B3n h_01HKA1AEYVBZH3W5M8GWDGM8NS=haz-clic-en-el-enlace-de-atribuci%C3%B3n viewthrough-attribution-lookback-window=ventana-de-lookback-de-atribuci%C3%B3n-view-through h_01HKA1AEYV0X18DS118ZRW9XXH=ventana-de-lookback-de-atribuci%C3%B3n-view-through impressions-attribution-link=enlace-de-atribuci%C3%B3n-de-impresiones h_01HKA1AEYV0KM6GCZESTM7DGD5=enlace-de-atribuci%C3%B3n-de-impresiones h_01HKA1AEYVWANYAXHW5Z8N3KEK=cost-tab h_01HKA1AEYW6HCFKSSF9MZZ3BJ9=ad-revenue-tab h_01HKA1AEYWHD46RKKV3R13FXJE=permissions-tab ad-network-permissions=permisos-de-ad-network h_01HKA1AEYWXZT0S754P18VY9R2=permisos-de-ad-network agency-permissions=permisos-de-la-agencia h_01HKA1AEYWJDXRM0QVBQQ7J58T=permisos-de-la-agencia" />
