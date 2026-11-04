---
title: Configuración de campañas de ByteDance Ads China
metadata:
  keywords:
    - bytedance
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
  created_at: '2017-06-18T07:05:42Z'
  edited_at: '2026-09-08T00:26:27Z'
  id: 115003019403
  locale: es
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/es/articles/115003019403
---
> **En resumen:** ByteDance Ads China (Ocean Engine), un partner integrado de AppsFlyer, es una empresa de tecnología de Internet que opera varias plataformas de contenido habilitadas para aprendizaje automático.

<div id="note" />

> 📘 **Nota**
>
> Si deseas promocionar tus aplicaciones de Android con ByteDance Ads China, debes enviar tu OAID al SDK de AppsFlyer, de acuerdo con las instrucciones de <Anchor target="_blank" href="/marketers/es/docs/sdk-integration-overview">Integración del SDK de AppsFlyer - Android</Anchor>. El servicio Google Play está bloqueado en China, el OAID es el ID de dispositivo Android más popular para la atribución de anuncios.

Además de la atribución móvil basada en clics, ByteDance Ads China también ofrece atribución por impresiones, que puedes registrar con AppsFlyer.

Para configurar tus campañas con ByteDance Ads China, sigue los pasos a continuación.

<div id="setting-up-bytedance-ads-china" />

## Configuración de ByteDance Ads China

**Requisito previo:** una cuenta con el partner. Si no tienes una cuenta, ponte en contacto con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Collaborate > Partner Integrations > Marketplace**.  
   (**Para editar una integración existente:** Ve a la pestaña **Collaborate > Partner Integrations > Active integrations**.)
2. Selecciona la aplicación correspondiente.
3. Busca el partner y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el selector **Activar partner**.   
   **Nota:** El selector **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de Partners.</Anchor>

Consejo

> 👍 **Tip**
>
> * El paso <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#d-general-settings">Configuración general</Anchor> de la pestaña Integración es **obligatorio** para todos los partners.
> * Todos los demás pasos son descriptivos u **opcionales**.

<div id="integration-tab" />

<Accordion title="Pestaña Integración">

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

<div id="activate-partners" />

### Activar los partners

En la **primera visita** aquí, debes activar el botón ***Activar partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

Configuración general

**Habilitar la atribución por impresiones**

[![](https://files.readme.io/3340b894428079e37c238cd78883669abd53cd6895165c5f9b5ea90d27d570c9-50612201111697.png)](https://files.readme.io/3340b894428079e37c238cd78883669abd53cd6895165c5f9b5ea90d27d570c9-50612201111697.png)

**Activa** este selector si deseas atribuir las instalaciones por impresiones desde ByteDance Ads China. El control deslizante de la ventana retrospectiva por impresiones está disponible en la pestaña del enlace de atribución (se describe a continuación).

<div id="default-postbacks" />

### Postbacks predeterminados

AppsFlyer puede enviar postbacks automáticos a ByteDance Ads China luego de las instalaciones y reengagements de los usuarios. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

![bytedance-default-postbacks.png](https://files.readme.io/5f3cb637fb9ff652533fcfd9c02ea8dc1768e0e1c1686a180ea18c0d2e09309f-50612201121425.png)

<div id="in-app-events-settings" />

### Configuración de eventos in-app

En esta sección, puedes asignar tus eventos de AppsFlyer con ByteDance Ads China a través de postbacks.

1. Activa Postbacks de eventos in-app.
2. Selecciona la opción de envío para todos los eventos definidos por el SDK.  
   **- Solo eventos atribuidos a este partner** para eventos que provienen **únicamente** de usuarios atribuidos a este partner.  
    **- Eventos atribuidos a cualquier partner u orgánicos** para tener toda tu base de usuarios disponible para ser reportada al partner.
3. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
4. Completa los siguientes parámetros:

| Nombre de parámetro | Descripción |
| --- | --- |
| **Evento de AppsFlyer** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea del SDK integrado en tu aplicación o de los eventos de servidor a servidor.<br />**Consejo**: ¿No encuentras el evento que estás buscando?<ul><li>Asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificarlo.</li><li>Escríbelo en **Evento de AppsFlyer**, y luego haz clic en **Crear personalizado**. Leer más sobre la <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#eventos-personalizados">asignación de eventos personalizada.</Anchor></li></ul> |
| **Asignado al evento de partner** | El ID o nombre único de cada evento, tal y como lo defina el partner. Existen varias configuraciones de asignación:<ul><li>**Campo de texto:** obtén el ID del evento correspondiente del partner.</li><li>**Cuadro desplegable:** selecciona el evento de AppsFlyer predefinido más adecuado.</li><li>**Como está**: envía los eventos tal como están, sin asignar el nombre del evento.</li></ul> |
| **Para usuarios de** | Selecciona la opción de envío para el evento:<ul><li>**Solo este partner**: envía postbacks solo cuando el evento se atribuya a este partner, es decir, el usuario que lo realizó provino de este partner.</li><li>**Todas las fuentes de medios, incluidas las orgánicas**: envía postbacks para eventos atribuidos a cualquier partner y para eventos orgánicos, es decir, el usuario que lo realizó provino de cualquier fuente de medios.</li></ul> |
| **Incluyendo** | Selecciona los datos del evento que se van a compartir con el partner en el postback:<ul><li>**Sin valores y sin ingresos**: envía solo el evento en sí sin ningún parámetro (valores o ingresos).</li><li>**Valores y sin ingresos**: envía todos los parámetros **excluyendo** el valor de los ingresos.</li><li>**Valores e ingresos**: envía todos los parámetros del evento, **incluido** el valor de los ingresos (si existe en el evento).</li></ul> |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlace de atribución">

Genera y guarda enlaces de atribución y envíalos al partner para que te atribuya campañas específicas, conjuntos de anuncios o anuncios únicos, tanto para campañas de UA como de retargeting. Puedes usar un enlace de una sola plataforma o un <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">Saber más sobre la estructura y los parámetros del enlace de atribución</Anchor>.

**Para generar un enlace de atribución,** sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#attribution-link-tab">estas instrucciones</Anchor>.

<div id="click-attribution-link" />

### Enlace de atribución de clics

Una vez que haya generado el enlace de atribución, completa el proceso de configuración de la campaña en el sitio de ByteDance Ads China.

**1. Crear seguimiento de conversiones en Ocean Engine.**

Inicia sesión en Ocean Engine ([https://ad.oceanengine.com/](https://ad.oceanengine.com/)) > **Library (Biblioteca)** > **Conversion Tracking (Seguimiento de conversiones)**.

![OE_dashboard_1.png](https://files.readme.io/fda140ac7e3023033880b04ed500a675ae78187e4eb694ee200922b729ab119f-50612185108497.png)

Haz clic en **Tracking application (Aplicación de seguimiento)** y crea una **New Application Transformation (Nueva transformación de aplicación)**.

![OE_dashboard_2.png](https://files.readme.io/dbf0c13c23d21d08c195a4ab747e5de0986cb01f5ebde98f6c701ce731480958-50612185109009.png)

Haz clic en el método **API**.

![OE_dashboard3.png](https://files.readme.io/70e7f6ca01c532fafb8f2ab7d31d6de51494f11749329c1c1333d1da6f28f284-50612185110417.png)

En la parte del enlace de monitoreo, introduce el enlace de atribución de clics de AppsFlyer y/o el enlace de atribución de impresiones.

![dashboard4.png](https://files.readme.io/d36ec92a03062fc7ee169bb1ff3863722343577f3ee2b12779065b3e52731348-50612201124369.png)

2. Finaliza la prueba de atribución siguiendo las instrucciones del sitio web.

**3. Crea una campaña publicitaria con la conversión recién creada**.

Ve a **New Ad (Nuevo anuncio)** >> **Set Budget and Bid (Establecer presupuesto y oferta)** y selecciona la conversión que creaste para esta aplicación.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costo">

AppsFlyer obtiene los detalles de los costos por API. Ten en cuenta que AppsFlyer no admite los datos de costos a nivel de anuncios para ByteDance, excepto para las campañas que se ejecutan en el sistema ByteDance v1.0.

<div id="api-dimensions-supported" />

### Dimensiones API admitidas

| Geolocalización | Fuente de medios | Campaña | Conjunto de anuncios | Anuncio | Otros |
| --- | --- | --- | --- | --- | --- |
| Sí | - | Sí | Sí | No<br /><br />(Los anuncios solo son compatibles con las campañas de ByteDance v1.0) | - |

**Para habilitar la API de costos de ByteDance Ads China**:

1. En la pestaña del partner integrado Costo , habilita ***Obtener Costo Data***.
2. Inicia sesión en ByteDance Ads China.
3. Haz clic ***Guardar Costo***.
   * Has completado con éxito el procedimiento. La API está activa. AppsFlyer recopila datos del partner 6 veces al día, en media, una vez cada cuatro horas.
   * La pestaña de costos muestra el estado de integración de tus costos y la última vez que AppsFlyer logró extraer datos de costos coincidentes.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de ingresos por publicidad">

Esta sección es pertinente si actúas como publisher y muestras anuncios del partner a tus usuarios. Como tal, con seguridad te gustaría medir el nivel de engagement de tus usuarios adquiridos a partir de distintas fuentes, a fin de identificar las fuentes que te resultan más rentables.

**Para habilitar la API de ingresos por publicidad**:

* Sigue <Anchor target="_blank" href="/marketers/es/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">estas instrucciones de integración</Anchor>.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que deseas otorgar a ByteDance Ads China, independientemente de si el partner actúa como red de publicidad, agencia o ambas. Ten en cuenta que incluso si la atribución está deshabilitada para ByteDance Ads China, la pestaña de permisos está activa y puedes otorgar el control a ByteDance Ads China.

Utiliza estos selectores para otorgarle permisos a la red de publicidad para que gestione su propia configuración para tu aplicación:

<div id="ad-network-permissions" />

### Permisos de la red de publicidad

* ***Permitir la configuración de la integración***: permite que el partner configure la pestaña de integración (excepto postbacks de eventos in-app).
* ***Permitir la configuración de postbacks de eventos in-app***: permite que el partner configure la asignación de postbacks de eventos in-app a sí mismo en la pestaña de integración.
* ***Permitir el acceso a tu reporte de retención***: solo para los propios datos de retención del partner.
* ***Permitir acceso a tus datos agregados de usuarios fieles***: solo a los datos de usuarios fieles propios del partner.
* ***Permitir acceso a tus datos agregados de eventos in-app**:* solo a los datos de eventos in-app propios del partner.
* ***Permitir acceso a tus datos agregados de ingresos*a** - solo a los datos de ingresos atribuidos al partner
* ***Permitir el acceso a tu panel de control Protect360***: solo a los datos de Protect360 propios del partner, y siempre que la característica esté habilitada para el anunciante.

Aprende más acerca de cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos a la red de publicidad</Anchor>.

</Accordion>

<div data-zendesk-anchors="h_01HJR1HREQDCQDN6JZRPD356VS=nota setting-up-bytedance-ads-china=configuraci%C3%B3n-de-bytedance-ads-china h_01HJR1HREQ6YAW1WPX2BTZS2R7=configuraci%C3%B3n-de-bytedance-ads-china h_01HJR1HRERBBZFKBHH78BK6QW2=integration-tab activate-partners=activar-los-partners h_01HJR1HRER22XX94R1WEQK60GJ=activar-los-partners default-postbacks=postbacks-predeterminados h_01HJR1HRERMXHAAGXEFJS4ZS8C=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HJR1HRERF2Y205KP0J8HZFR3=configuraci%C3%B3n-de-eventos-in-app h_01HJR1HRER391J6PD9Q0M1MW3F=attribution-link-tab click-attribution-link=enlace-de-atribuci%C3%B3n-de-clics h_01HJR1HRERCHNHQGX3X1E1ARDK=enlace-de-atribuci%C3%B3n-de-clics h_01HJR1HRER1G4K3PQG1Z7M6CCX=cost-tab api-dimensions-supported=dimensiones-api-admitidas h_01HJR1HRES86BJM4ABQ0B414F1=dimensiones-api-admitidas h_01HJR1HRES470MKXS1S08X202D=ad-revenue-tab h_01HJR1HRESJ7KNFZ9TDHZKESJ7=permissions-tab ad-network-permissions=permisos-de-la-red-de-publicidad h_01HJR1HRESZCC6YV9D40YYSYX0=permisos-de-la-red-de-publicidad" />
