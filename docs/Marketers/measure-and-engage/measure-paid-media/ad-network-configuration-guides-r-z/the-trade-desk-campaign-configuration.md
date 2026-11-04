---
title: Configuración de la campaña de The Trade Desk
metadata:
  keywords:
    - Advertisers
    - The Trade Desk
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2018-05-13T07:34:13Z'
  edited_at: '2026-09-16T00:25:08Z'
  id: 360000894849
  locale: es
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/es/articles/360000894849
---
> **De un vistazo:** The Trade Desk, un partner integrado de la red de publicidad de AppsFlyer, utiliza su solución mejorada de publicidad móvil para cultivar campañas estratégicas, escalables e inteligentes para satisfacer las necesidades de los usuarios de dispositivos cruzados. The Trade Desk ofrece atribución móvil basada en los clics, atribución móvil por impresiones y retargeting basado en los clics, lo cual puede registrarse a través de AppsFlyer.

<div id="setting-up-the-trade-desk-ttd" />

## Configuración de The Trade Desk (TTD)

Sigue estos pasos para habilitar la medición de campañas de AppsFlyer.

<div id="step-1-define-conversion-events-in-ttd" />

<Accordion title="Paso 1: Definir los eventos de conversión en TTD">

1. En el menú de la izquierda de tu página de anunciante de TTD, haz clic en **DATA** (Datos).
2. En el menú superior, haz clic en **Add App Data** (Agregar datos de aplicación).
3. Introduce los siguientes campos en la página **Create App Data** (Crear datos de la aplicación):
   * **App Name** (Nombre de la aplicación): introduce el nombre de la aplicación.
   * **Operating System** (Sistema operativo): selecciona **Android** o **iOS**.   
     **Nota:** TTD admite CTV en las opciones Android e iOS.
   * **Tracking Vendor** (Proveedor de rastreo): selecciona **AppsFlyer**.
   * **Events** (Eventos): haz clic en **ADD EVENT** (Agregar evento) para agregar eventos de conversión e introduce los campos:
     * **EVENT NAME** (Nombre del evento): introduce el nombre del evento.  
       **Nota:** Asegúrate de que el nombre esté escrito exactamente como en AppsFlyer, incluyendo mayúsculas, espacios y símbolos.
     * [Opcional] **DESCRIPTION** (Descripción): agrega una descripción.
     * [Opcional] **USAGE OF COLLECTED DATA** (Uso de los datos recogidos): selecciona **Attribution** (Atribución). Esta opción incluye tanto la atribución como el retargeting.
     * Para agregar más eventos, haz clic en **ADD EVENT** (Agregar evento) y repite el proceso.
   * **Conversion Credit Source** (Fuente de crédito para conversiones): selecciona la fuente para atribuir las conversiones, ya sea AppsFlyer o The Trade Desk.   
     **Nota:**
     * Para medir entre dispositivos y la compra de TTD, selecciona **The Trade Desk**.   
       Para tener una visión global de la medición, no solo en TTD, selecciona **AppsFlyer**.
     * Nunca cambies esta selección durante una campaña.
     * Asegúrate de seleccionar la fuente correcta antes de hacer clic en **CREATE APP DATA**. No puedes cambiar la fuente de crédito de conversión durante una campaña.
4. Haz clic en **CREATE APP DATA** (Crear datos de la aplicación).

</Accordion>

<div id="step-2-define-conversion-events-in-appsflyer" />

<Accordion title="Paso 2: Definir los eventos de conversión en AppsFlyer">

Para que AppsFlyer defina eventos de conversión y te permita enviar postbacks de eventos a TTD, primero debes [integrar TTD con AppsFlyer](/docs/the-trade-desk-campaign-configuration#integración-de-ttd-con-appsflyer) y realizar las siguientes configuraciones:

* Configuración de la integración (incluida la configuración de los postbacks de los eventos)
* Enlace de atribución
* Permisos

</Accordion>

<div id="step-3-map-defined-conversion-events-from-appsflyer" />

<Accordion title="Paso 3: Asignar los eventos de conversión definidos desde AppsFlyer">

1. En el menú de la izquierda de TTD, haz clic en **CAMPAIGNS** (Campañas).
2. Desplázate hasta **Campaigns** (Campañas) y selecciona una campaña de la lista.
3. Haz clic en **Edit Reporting & Attribution** (Editar reportes y atribución).
4. Haz clic en **ADD CONVERSION DATA SOURCE** (Agregar fuente de datos de conversión).
5. En **CONVERSION DATA SOURCE** (Fuente de datos de conversión), selecciona o escribe **AppsFlyer**. Los eventos de AppsFlyer ahora se asignan a los eventos de TTD.
6. **CROSS-DEVICE CONCEPT** (Concepto interdispositivo):
   * Si en el [Paso 1](/docs/the-trade-desk-campaign-configuration#step-1-define-conversion-events-in-ttd) (Fuente de crédito de conversión) elegiste que TTD atribuya las conversiones, selecciona aquí **Household** para ver las conversiones en todos los canales disponibles (como móvil in-app y CTV).
   * Si elegiste AppsFlyer en el [Paso 1](/docs/the-trade-desk-campaign-configuration#step-1-define-conversion-events-in-ttd), selecciona aquí **None** (Ninguno).
7. Haz clic en **SAVE** (Guardar).

</Accordion>

<div id="step-4-add-click-and-impression-trackers-to-campaign-creatives" />

<Accordion title="Paso 4: Agregar rastreadores de clics e impresiones a las creatividades de la campaña">

En este paso, agregarás los rastreadores de clics e impresiones que se crearon en AppsFlyer a cada una de las creatividades en TTD.

1. En **CAMPAIGNS** (Campañas) en el menú de la izquierda de TTD, haz clic en **CREATIVES** (Creatividades) en la pestaña superior.
2. Selecciona una creatividad de la lista de creatividades asociadas a la campaña actual.
3. Desplázate hasta **Tracking** (Seguimiento).
4. Copia el enlace de Atribución view-through de [atribución](/docs/the-trade-desk-campaign-configuration#attribution-link-tab) de AppsFlyer y pégalo en el campo 1x1 Pixel Impression Tracking URL.
5. Copia el enlace de Atribución click-through de AppsFlyer y pégalo en el campo click-Through URL.
6. Haz clic **SAVE CHANGES** (Guardar cambios).
7. Repite este paso para cada una de las creatividades asociadas con la campaña.

</Accordion>

<div id="note" />

> 📘 **Nota**
>
> Si has elegido que las conversiones sean atribuidas por TTD (en el [Paso 1](/docs/the-trade-desk-campaign-configuration#step-1-define-conversion-events-in-ttd)), puedes editar las ventanas de atribución:
>
> 1. En el menú de iconos de la derecha de cualquier página de TTD, haz clic en la rueda dentada para abrir las **preferencias del anunciante**.
> 2. Desplázate hasta **Attribution Windows** (Ventanas de atribución) y haz clic en el botón de edición de la derecha.
> 3. Desde la página **Manage Attribution Windows** (Administrar ventanas de atribución), edita las ventanas de atribución:
>    * **De-duplication Windows** (Ventanas de desduplicación): el número de conversiones que se pueden ver en un determinado periodo de tiempo.
>    * **Campaign Attribution Windows** (Ventanas de atribución de campañas): el periodo de tiempo desde la exposición del anuncio hasta la conversión.
> 4. Haz clic en **SAVE** (Guardar).

<div id="integrating-ttd-with-appsflyer" />

## Integración de TTD con AppsFlyer

**Requisito previo:** una cuenta con el partner. Si no tienes una cuenta, contacta con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Collaborate > Partner Integrations > Marketplace** .  
   (**Para editar una integración existente:** Ve a la pestaña **Collaborate > Partner Integrations > Active integrations** .)
2. Selecciona la aplicación correspondiente.
3. Busca el Partners y selecciona **Integrate**.
4. En la pestaña **Integración**, activa el selector **Activate partner**.   
   **Nota:** El selector **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de Partners</Anchor>

La ventana de configuración de TTD incluye tres pestañas activas: Integración, Enlace de atribución y Permisos. Haz clic en los elementos que aparecen a continuación para obtener más información sobre la configuración de las pestañas.

Para ver una descripción detallada del encabezado de la ventana de configuración de Partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aquí</Anchor>.

<div id="integration-tab" />

<Accordion title="Pestaña Integración">

<div id="activate-partner" />

#### Activar el partner

En la primera visita, tendrás que activar el conmutador **Activar partner** para configurar la integración. El conmutador debe permanecer encendido durante todo el tiempo que se trabaje con TTD.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

<div id="advanced-privacy" />

#### Privacidad avanzada

En las aplicaciones de iOS, aparece el selector <Anchor target="_blank" href="/marketers/es/docs/apply-aggregated-advanced-privacy-framework">Habilitar privacidad avanzada</Anchor>. Cuando está activado, limita el uso compartido de identificadores de usuario con el partner. Ten en cuenta que cuando la opción <Anchor target="_blank" href="/marketers/es/docs/apply-aggregated-advanced-privacy-framework">Privacidad avanzada agregada</Anchor> está activada en la configuración de la aplicación, **Habilitar privacidad avanzada** se activa y se bloquea de forma predeterminada. 

<div id="general-settings" />

#### Configuración general

**ID de rastreador y anunciante**

The Trade Desk se conecta con AppsFlyer a través de un ID de red y único. Si aún no tienes el Tracker\_ID y el advertiserid, debes obtenerlos de The Trade Desk para continuar con la integración.

![TTD_General_Settings_.png](https://files.readme.io/f7f2b66556f2713ff56a3bd2fcfe6fe8fe8d346a9b322904f93670ee55cf94c3-50612291000849.png)

**Habilitar la atribución por impresiones**

Activa **Habilitar atribución por impresiones** para atribuir las instalaciones por impresiones desde The Trade Desk. El control deslizante de retrospectiva por impresiones está disponible en la pestaña del enlace de atribución (descrito a continuación).

<div id="default-postbacks" />

#### Postbacks predeterminados

![default_postbacks_en-us.png](https://files.readme.io/b291c9fd4ac858723f3071bf271a041403639d49bfb1984030fc7c7306c40c16-50612291002385.png)

Envía postbacks automáticos a The Trade Desk después de las instalaciones y re-engagements de los usuarios. Utiliza esta sección para definir el origen de los usuarios que permiten enviar estos postbacks:

* **Solo este partner**: para eventos que provienen solo de usuarios atribuidos a The Trade Desk.
* **Todas las fuentes de medios, incluidas las orgánicas**: para que toda tu base de usuarios esté disponible para reportarla a The Trade Desk.

<div id="note-1" />

> 📘 **Nota**
>
> Como red de instalaciones, The Trade Desk prefiere recibir postbacks de todas las nuevas instalaciones de tu app desde cualquier fuente, y recomienda seleccionar **Todas las fuentes de medios, incluidas las orgánicas** para enviar todos los postbacks de instalación a The Trade Desk.

<div id="in-app-events-settings" />

#### Configuración de eventos in-app

Asigna eventos de AppsFlyer con TTD a través de postbacks. Si el envío de postbacks está activado, esto incluye los eventos in-app rechazados (eventos bloqueados por Protect360 o eventos que no cumplen con las reglas de validación del targeting).

![the_trade_desk_in_app_event_settings_en-us.png](https://files.readme.io/a72231e1f7d21eeb6ffd0b8e0ce056872ec7ef4670470a86e93eb7094ff9cea8-50612307447185.png)

**Para configurar postbacks de eventos in-app:**

1. Introduce el **advertiserid** y el **Tracker\_ID**.
2. Habilita **los postbacks de eventos in-app**.
3. Configura la **ventana de postback de eventos in-app**, si es necesario (lee más sobre <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#ventana-de-postback-de-eventos-in-app">la configuración de la ventana de postback de eventos in-app</Anchor>).
4. Si está disponible, selecciona si deseas enviar los eventos de forma automática o manual. Saber más sobre <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#send-events-as-they-are-unmapped">enviar todos los eventos tal como están</Anchor>.
5. Haz clic en **Agregar evento** para agregar un evento de SDK o de servidor a servidor a la lista.
6. Completa los parámetros según sea necesario.
7. [Opcional] Haz clic en<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" />para establecer condiciones para enviar ciertos eventos in-app a TTD.  
   Saber más sobre <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#postbacks-condicionales-de-eventos-in-app">los postbacks de eventos in-app condicionales</Anchor>.

| Nombre de Parámetro | Description |
| --- | --- |
| **Evento de AppsFlyer** | El nombre del evento, tal como lo recibe AppsFlyer, ya sea del SDK integrado en tu aplicación o de eventos de servidor a servidor.<br />**Consejo**: ¿No ves el evento que estás buscando?<ul><li>Asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar.</li><li>Escríbelo en **evento de AppsFlyer**, luego haz clic **Crear personalizado**. Leer más sobre la <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#eventos-personalizados">asignación de eventos personalizados</Anchor></li></ul> |
| **para usuarios de** | Selecciona la opción de envío para el evento:<ul><li>**Solo este partner**: envía postbacks solo cuando este evento se atribuye a este partner.</li><li>**Todas las fuentes de medios, incluidas las orgánicas**: envía postbacks de eventos atribuidos a cualquier partner, así como eventos orgánicos.</li></ul> |
| **Incluyendo** | <ul><li>**Sin datos (predeterminado)**: envía solo el evento en sí, sin el valor del evento.</li><li>**Valores e ingresos**: envía todos los parámetros del evento, **incluido** el valor de ingresos (si existe en el evento).</li><li>**Valores sin ingresos**: envía todos los parámetros **excluyendo** el valor de ingresos.</li></ul> |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Genera y guarda enlaces de atribución y envíalos a TTD para atribuir campañas específicas, conjuntos de anuncios o anuncios individuales, tanto para campañas de UA como de retargeting. Puedes usar tanto un enlace de una sola plataforma como <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">OneLink</Anchor>.

<div id="attribution-link-parameters" />

#### Parámetros de enlaces de atribución

Agregar parámetros al enlace de atribución te permitirá realizar análisis detallados. Los parámetros que ya están definidos en el enlace de atribución pueden editarse agregándolos junto con sus valores nuevos en esta sección. Al guardar el enlace de atribución, se guardan todos los parámetros configurados en esta pestaña.

Selecciona los parámetros que quieres agregar al enlace de atribución.

![ttd_attribution_link_parameters_en-us.png](https://files.readme.io/2658797286fd7d922c68a9c2f1705166672066d4179d72cf4fe0039ac3ede212-50612291012625.png)

<div id="default-parameters" />

#### Parámetros por defecto

| Nombre | Descripción | Parámetro |
| --- | --- | --- |
| ID de sitio | Configura el parámetro de ID de tu sitio para atribuir instalaciones a publishers específicos. Si hay muchos publishers, te recomendamos limitar el número de ID de sitio utilizados y usar el parámetro de ID de subsitio para evitar <Anchor target="_blank" href="/marketers/es/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">superar las limitaciones del ID de sitio</Anchor>. | af\_siteid |
| Nombre de la campaña | Agrega el nombre de tu campaña para comparar las diferentes campañas que se ejecutan con TTD. | C |
| ID de campaña | Agrega el ID de tu campaña. | af\_c\_id |
| ID de conjunto de anuncios | Agrega el ID de tu conjunto de anuncios para comparar el rendimiento de todos tus anuncios por conjunto de anuncios. | af\_conjunto de anuncios |
| ID de anuncio | Agrega el ID de tu anuncio. | id\_del\_anuncio\_af |

Puede agregar más parámetros para el enlace de atribución. Saber más sobre <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#attribution-link-tab">cómo configurar el enlace de atribución</Anchor> y sobre la <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">estructura y los parámetros del enlace de atribución</Anchor>.

<div id="parameters-for-measuring-ctv" />

#### Parámetros para medir el CTV

Puedes medir el tráfico de CTV con AppsFlyer agregando los siguientes parámetros y valores:

| Parámetro | value | Comentarios |
| --- | --- | --- |
| Redirigir | false |  |
| af\_xplatform\_vt\_lookback | 1 - 72 horas | Se puede ingresar cualquier valor entre 1 y 72 horas |

<div id="click-through-attribution" />

#### Atribución por clics

![click-through_attribution_ttd_en-us.png](https://files.readme.io/9d8c4aed6aa5d8b3cba5b4e32a5245f4bd8b6d9cf50e8cc800dce66842487355-50612291014673.png)

Utiliza el control deslizante para establecer el tiempo máximo desde el clic hasta la instalación. Solo se atribuyen las instalaciones (primeros inicios) que ocurran dentro de la ventana retrospectiva.

Intervalo de ventana retrospectiva: 1-23 horas o 1-30 días.

Parámetro de enlace de atribución: af\_click\_lookback

Saber más sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">ventana de lookback de clics</Anchor>.

**Enlace de atribución por clic:** Contiene todos los parámetros que incluiste en la configuración del enlace de atribución. Puedes copiar el enlace y enviarlo al partner para que se active cuando tus clientes potenciales hagan clic en un anuncio correspondiente.

<div id="view-through-attribution" />

#### Atribución por view-through

![view-through_attribution_ttd_en-us.png](https://files.readme.io/7435384719e46f0534149ef41612db6ee54c930bab8e8eadc1fd86ae84d5d777-50612307451921.png)

Utiliza el cursor para establecer el tiempo máximo desde la impresión hasta la instalación. Solo las instalaciones (primeras aperturas) que ocurren dentro de esta ventana, después de una impresión de anuncio, se atribuyen al partner, siempre que no haya otro clic relevante en un anuncio.

Intervalo de ventana retrospectiva: 1-24 horas.

Parámetro en el enlace de atribución: af\_viewthrough\_lookback

Saber más sobre la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">Atribución view-through</Anchor>.

**Enlace de atribución por impresiones:** contiene todos los parámetros que incluiste en la configuración del enlace de atribución. Puedes copiar el enlace y enviarlo al partner para que se active cuando tus clientes potenciales hagan clic en un anuncio correspondiente.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña Costo">

La integración de costos no está disponible para The Trade Desk.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña Ingresos por publicidad">

Los ingresos por publicidad no están disponibles para The Trade Desk.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres otorgarle a The Trade Desk, ya sea que actúe como red de publicidad, agencia o ambas. Ten en cuenta que incluso si la atribución está deshabilitada para The Trade Desk, la pestaña de permisos se puede activar y puedes otorgar control a The Trade Desk.

![](https://files.readme.io/8d8c3d5eb38384d92e52afdc01b0631d8fe5c9590dd618386cbf6ce90fc978f3-50612307452817.png)

Utiliza estos selectores para otorgarle permisos a la red de publicidad para que gestione su propia configuración para tu aplicación:

<div id="ad-network-permissions" />

#### **Permisos para red de anuncios**

* **Permitir la configuración de la integración:** permite que TTD configure la pestaña de integración, excepto los postbacks de eventos in-app.
* **Permitir la configuración de postback de eventos in-app:** permite que TTD configure y se asigne postbacks de eventos in-app en la pestaña de integración.
* **Permitir el acceso a tu reporte de retención:** solo para los datos propios de retención de TTD.
* **Permitir el acceso a tus datos agregados de usuarios leales:** solo a los datos propios de usuarios leales de TTD.
* **Permitir acceso a tus datos agregados de eventos in-app:** solo a los datos de eventos in-app propios de TTD.
* **Permitir acceso a tus datos agregados de ingresos:** solo a los datos de ingresos atribuidos a TTD.
* **Permitir el acceso a panel de control de Protect360:** solo para los datos de Protect360 propios de TTD, y siempre que tengas habilitada esta función.

Saber más sobre cómo otorgar <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos de ad network</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-the-trade-desk-ttd=configuraci%C3%B3n-de-the-trade-desk-ttd h_01HH2DHQWXTB9K2R07SJP1AXER=configuraci%C3%B3n-de-the-trade-desk-ttd h_01HH2DHQWX9Y6R1J3HPYWTAC2Z=step-1-define-conversion-events-in-ttd h_01HH2DHQWXTZ5EMJNYRGJMY7QA=step-2-define-conversion-events-in-appsflyer h_01HH2DHQWXCWF0H1GJGJS2YYDA=step-3-map-defined-conversion-events-from-appsflyer step-4-add-click-and-impression-trackers%C2%A0to-campaign-creatives=step-4-add-click-and-impression-trackers-to-campaign-creatives h_01HH2DHQWX1Z10PTRM8S7538YX=step-4-add-click-and-impression-trackers-to-campaign-creatives h_01HH2DHQWXX1EEARNBC61W3CDK=nota integrating-ttd-with-appsflyer=integraci%C3%B3n-de-ttd-con-appsflyer h_01GFNDH51M6KYE39C7DJW3BJ8W=integraci%C3%B3n-de-ttd-con-appsflyer h_01GF8CKQYVDW5Z7141MJDGGW4C=integration-tab activate-partner=activar-el-partner h_01HH2DHQWYME21J7JV176N71P2=activar-el-partner advanced-privacy=privacidad-avanzada h_01HH2DHQWYFJB3ZCWVZZ048AQP=privacidad-avanzada general-settings=configuraci%C3%B3n-general h_01HH2DHQWYN3CZZCFT9X2R2N9J=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01HH2DHQWY1GPVP5W5R4XV2H9C=postbacks-predeterminados h_01HH2DHQWY284121FR8HSFGH45=nota-1 inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01HH2DHQWY0XM70BPE7222XE78=configuraci%C3%B3n-de-eventos-in-app h_01HH2DHQWY7X522JKKC4A45BHN=attribution-link-tab attribution-link-parameters=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n h_01HH2DHQWY4GXPMCV5JEBFERG6=par%C3%A1metros-de-enlaces-de-atribuci%C3%B3n default-parameters=par%C3%A1metros-por-defecto h_01HH2DHQWYZSECQWRQEKDB9KZH=par%C3%A1metros-por-defecto parameters-for-measuring-ctv=par%C3%A1metros-para-medir-el-ctv h_01HH2DHQWYZPKCY947MWK7GEAP=par%C3%A1metros-para-medir-el-ctv clickthrough-attribution=atribuci%C3%B3n-por-clics h_01HH2DHQWYCFGJK4ZT9CXFX3X3=atribuci%C3%B3n-por-clics viewthrough-attribution=atribuci%C3%B3n-por-view-through h_01HH2DHQWYP6S95MRAS39Q4RTT=atribuci%C3%B3n-por-view-through h_01HH2DHQWYP5GYN2GH3C839P3N=cost-tab h_01HH2DHQWYG3KZTE0HH7QV4H6X=ad-revenue-tab h_01HH2DHQWYA9HAWT5PV092T6E9=permissions-tab ad-network-permissions=permisos-para-red-de-anuncios h_01HH2DHQWYCWYQFBDA19Z9BA8W=permisos-para-red-de-anuncios" />
