---
title: '[Beta cerrada] Configuración de campañas de Amazon Ads'
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2023-01-04T10:14:20Z'
  edited_at: '2026-09-11T00:25:45Z'
  id: 11904659502737
  locale: es
  section: Amazon Ads
  section_id: 28703975923729
  url: https://support.appsflyer.com/hc/es/articles/11904659502737
---
> **Resumen:** Amazon Ads (amazondsp\_int) es un socio avanzado de AppsFlyer integrado con la red de informes automáticos (<Anchor target="_blank" href="/marketers/es/docs/self-reporting-networks-srns">SRN</Anchor>), que permite a los propietarios de aplicaciones medir la atribución basada en clics y vistas para TV, tabletas y dispositivos móviles a través de AppsFlyer.

![mceclip0.png](https://files.readme.io/0a4c9078bd683c51bad40408c894f6e2b7314d7c369bd46ac90c3e622f62f0a7-11927906589329.png)

<div id="activate-partner" />

## Activar socio

**Requisito previo:** Una cuenta con el partner. Si no tienes una cuenta, contacta con el partner para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Collaborate > Partner Integrations > Marketplace** .  
   (**Para editar una integración existente:** Ve a la pestaña **Collaborate > Partner Integrations > Active integrations** .)
2. Selecciona la aplicación correspondiente.
3. Busca el partner y selecciona **Integrate**.
4. En la pestaña **Integración**, activa el conmutador **Activate partner**.   
   **Nota:** El conmutador **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas pertinentes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de partners.</Anchor>

<div id="complete-the-setup-in-amazon-ads" />

## Busque la nueva integración del socio y selecciónela.

Actualmente, esta integración está abierta a un grupo beta cerrado.

1. Los enlaces de atribución no son relevantes para Amazon Ads. La atribución se realiza combinando los datos de interacción de Amazon Ads con los datos de AppsFlyer, usando las ventanas de retroceso de clics y vistas configuradas en la [pestaña Integración](/docs/amazon-ads-campaign-configuration#integration-tab).
2. Cuando crees campañas en Amazon Ads, asegúrate de asociar las conversiones relevantes a la campaña. Consulta <Anchor target="_blank" href="https://advertising.amazon.com/help/GMQBB4PRFK8C33AE">Asignar una definición de conversión a una campaña</Anchor> en la documentación de Amazon Ads.

<div id="setting-up-amazon-ads" />

## Configuración de Amazon Ads

La integración con Amazon Ads admite la atribución de clics e impresiones. La ventana de configuración incluye las siguientes pestañas: Integración, enlace de atribución, coste, ingresos por publicidad y permisos. Las pestañas disponibles para Amazon Ads son Integración y Permisos.

<div id="note" />

> 📘 **Nota:**
>
> Esta integración es compatible con aplicaciones de Android o Fire. Para iOS, la interoperabilidad SKAN está disponible para compartir postbacks SKAN entre AppsFlyer y Amazon Ads.

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña **Integración** incluye varias secciones, como se describe a continuación.

<div id="activate-partner-1" />

#### Activar socio

Para configurar la integración, primero debes [activar](/docs/amazon-ads-campaign-configuration#activar-socio) el conmutador **Activar socio**. Obtenga más información sobre cómo <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation#activar-la-integración-de-un-partner">activar y desactivar integraciones de socios</Anchor>.

<div id="general-settings" />

#### Configuración general

**ID de Anunciante de Amazon**

Esta es una clave única de Amazon para el anunciante, generada por Amazon. Se requiere el ID de Anunciante de Amazon para completar la integración y permitir la atribución a Amazon Ads. Para encontrar el ID del Anunciante de Amazon:

* **Para anunciantes de autoservicio:** Su ID de anunciante está en la consola de informes de Amazon Ads, debajo de su nombre de anunciante, en la pestaña "Anunciantes" del "Administrador de campañas de Amazon DSP".
* **Para anunciantes de servicios gestionados:** Solicite a su gerente de cuenta de Amazon su ID de anunciante.
* Si usas varias cuentas de anuncios de Amazon para la misma aplicación (y, por tanto, tienes varios ID de Anunciante de Amazon), configura la integración de la siguiente manera:
  1. En Amazon Ads, selecciona una cuenta de anuncios y desígnala como **cuenta de origen**. Designa todas las demás cuentas de anuncios como **cuentas de destino**.
  2. Ponte en contacto con el equipo de cuentas de Amazon para configurarlo en su backend.
  3. En AppsFlyer, introduce el ID de Anunciante de Amazon asociado a la cuenta de origen. Esto aplicará la configuración de la integración a todas las cuentas de destino relacionadas.

**ID de paquete de Amazon**

* **Para aplicaciones de Android:** El nombre del paquete. Por ejemplo: `com.example.app`
* **Para aplicaciones de Fire TV o tabletas Fire:** El ASIN del producto (Número de artículo estándar de Amazon)
* **Para aplicaciones iOS (requerido para la atribución de SKAN):** El ID de la aplicación en la App Store (ejemplo: `id12345678`)
* **Para** <Anchor target="_blank" href="/marketers/es/docs/set-up-multi-store-android-attribution#un-solo-panel-de-control-vs-un-panel-de-control-por-tienda">**aplicaciones de panel unificado**</Anchor> (paneles que combinan datos de Google Play y Amazon Store para la misma aplicación de AppsFlyer): Introduzca el nombre del paquete de Android como el ID del paquete.  
  **Nota: <Anchor target="_blank" href="https://advertising.amazon.com/help/GF97FJUFXBDM32P4">Asegúrese de que la aplicación esté</Anchor> <Anchor target="_blank" href="https://advertising.amazon.com/help/GF97FJUFXBDM32P4">registrada</Anchor> como una aplicación de Android en la cuenta de Amazon Ads.**

<div id="install-attribution" />

#### Atribución de instalación

Configure ventanas de atribución por clic y visualización para las instalaciones (primeros lanzamientos). Recuerde que solo las instalaciones dentro de la ventana retrospectiva son atribuidas a Amazon Ads.

**Nota:** No se admite la atribución de reinstalaciones (cualquier instalación que no sea la inicial en el dispositivo).

1. Establezca la **ventana retrospectiva de clic de instalación** en 1 a 24 horas o de 1 a 14 días.  
   **Nota:** Amazon Ads recomienda configurar la ventana retrospectiva de clics en 14 días para alinear con su ventana de atribución y evitar discrepancias.
2. [Opcional] Active **la atribución de visualización de instalación** y configure la **ventana de atribución de visualización de instalación** a 1-24 horas.   
   **Nota:** Amazon Ads recomienda configurar la ventana retrospectiva de visualización en 14 días para alinearse con su ventana de atribución y evitar discrepancias.

<div id="re-engagement-attribution" />

#### Atribución de reengagement

Active el **alternador de atribución de reengagement** y configure las diferentes ventanas de atribución para asignar los reengagements de sus usuarios existentes que vieron, hicieron clic ***o interactuaron*** con su anuncio. Recuerde que solo los reengagements dentro de la ventana retrospectiva pueden ser atribuidos a Amazon Ads.

1. [Opcional] Actívela **atribución de reengagement** y configure la ventana retrospectiva:
   * Configure la **ventana retrospectiva de clics de reengagement** entre 1-23 horas o 1-14 días.
2. [Opcional] Actívela **atribución de visualización de reengagement** y configure las ventanas retrospectivas:
   * Establezca la **ventana retrospectiva de visualización de reengagement** entre 1-23 horas o 1-14 días.
3. Configure la **ventana de reengagement** a 1-23 horas, 1-90 días o **duración de por vida**.

<div id="ignore-active-users-for-retargeting" />

#### Ignorar usuarios activos para retargeting

Establece un período de tiempo para <Anchor target="_blank" href="/marketers/es/docs/set-retargeting-inactivity-window#periodo-de-inactividad">ignorar las re-engagements y reatribuciones</Anchor> de los usuarios que han iniciado tu aplicación. Esto significa que su actividad durante este período no se registra en AppsFlyer.

<div id="note-1" />

> 📘 **Nota:**
>
> Se registran las conversiones de re-engagement y reatribución de usuarios que estuvieron **inactivos** en el periodo seleccionado **se registran**.

1. Activa **Ignorar usuarios activos para retargeting**.
2. Establece la **ventana de inactividad** entre 1 y 30 días.  
   **Nota:** Amazon Ads recomienda fijar la ventana de inactividad en 7 días para alinearse con ellos y evitar discrepancias.

<div id="in-app-event-postbacks" />

#### Postbacks de eventos in-app

Configura la correspondencia de eventos in-app con eventos de Amazon Ads, enviados por postbacks.

**Para configurar postbacks de eventos in-app:**

1. Activa los **postbacks de eventos in-app**.
2. Haz clic en **Agregar evento** para añadir un evento SDK o de servidor a lista. La siguiente tabla describe los campos a completar:

| Nombre del parámetro | Descripción |
| --- | --- |
| **Evento de AppsFlyer** | El nombre del evento tal como lo recibe AppsFlyer desde el SDK integrado en tu app o desde eventos de servidor a servidor.<br />**Consejo**: ¿No encuentras el evento que buscas?<ul><li>Asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a comprobarlo.</li><li>Escríbelo en **evento AppsFlyer** y luego haz clic en **Crear personalizado**. Leer más sobre <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#eventos-personalizados">la asignación de eventos personalizados.</Anchor></li></ul> |
| **Asignado al evento del partner** | El nombre o ID único de cada evento, definido por el partner. Selecciona de la lista de eventos predefinidos del partner, el que corresponde al evento de tu app (evento AppsFlyer).<br /><br />**Notas:**<ul><li>**Nota:** Puedes seleccionar OTROS para eventos que no correspondan directamente con el evento de tu app.</li><li>Cuando la medición de re-engagement esté habilitada, te recomendamos no asignar el evento `af_app_opened` en absoluto, o asignarlo solo a `OTHER`. Esto evitará posibles duplicaciones al enviar este evento.</li></ul> |
| **para usuarios de** | Selecciona la opción de envío para el evento:<ul><li>**Solo este partner**: Envía postbacks solo cuando este evento se atribuye a este partner.</li><li>**Todas las fuentes de medios, incluidas las orgánicas**: Envía postbacks para eventos atribuidos a cualquier partner, así como eventos orgánicos.</li></ul> |
| **incluyendo** | <ul><li>**Sin datos (por defecto)**: Envía solo el evento en sí sin ningún valor de evento.</li><li>**Valores e ingresos**: Envía todos los parámetros del evento, **incluido** el valor de ingresos (si está presente en el evento).</li><li>**Valores sin ingresos**: Envía todos los parámetros **excepto** el valor de ingresos.</li></ul> |

   <div id="note-2" />

   > 📘 **Nota:**
   >
   > Si envías tu evento in-app a AppsFlyer mediante S2S, Amazon recomienda incluir la IP. Esto permite a AppsFlyer enviar a Amazon el código de país de la geolocalización del evento, lo que ayuda con la clasificación de la normativa DMA. Esto, a su vez, garantiza la máxima optimización de tus eventos in-app

3. [Opcional] Haz clic en el icono **Agregar condiciónaltconditional-iae-postbacks-icon.pngalt para <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#postbacks-condicionales-de-eventos-in-app">establecer condiciones</Anchor> para un evento.**
4. Haz clic en **Guardar integración**.
5. [Opcional] Tras guardar la integración, mientras permanezcas en la página de configuración, puedes integrar más aplicaciones con el socio:
   1. Desde la esquina superior izquierda, bajo el nombre del socio, haz clic en el nombre de la aplicación para abrir la lista de aplicaciones.
   2. Selecciona una aplicación diferente del desplegable.
   3. Repite los [pasos de integración](/docs/amazon-ads-campaign-configuration#integration-tab) para la aplicación seleccionada.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlace de atribución">

Los enlaces de atribución no son relevantes para Amazon Ads. La atribución se realiza combinando los datos de engagement de Amazon Ads con los datos de AppsFlyer, usando las ventanas de lookback de clics y de view-through configuradas en la [pestaña Integración](#integration-tab).

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de Costos, clics e impresiones">

Los datos de costos, clics e impresiones no están disponibles para Amazon Ads.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de ingresos por publicidad">

Los ingresos por publicidad no están disponibles para Amazon Ads.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

Selecciona qué permisos otorgar a Amazon Ads para acceder a tus datos y realizar diversas acciones.

<div id="note-3" />

> 📘 **Nota:**
>
> * Cuando la integración esté <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">desactivada</Anchor> mientras el interruptor de Permisos aún está activado, los permisos permanecen concedidos.
> * Aprende más sobre <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">cómo conceder permisos</Anchor>.

</Accordion>

<div id="see-also" />

> 📄 **Véase también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/setting-up-amazon-fire-tv-ad-attribution">Configuración de atribución de anuncios de Amazon Fire TV</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/attribution-discrepancies-between-amazon-ads-and-appsflyer">Discrepancias de atribución entre AppsFlyer y Amazon Ads</Anchor>

<div id="deferred-deep-linking" />

## Enlaces profundos diferidos

* Los enlaces profundos no son compatibles con Amazon Ads.
* Deep links diferidos: ninguno de los dos métodos de AppsFlyer para deep links diferidos está disponible para Amazon Ads:
  * Esta integración no es compatible con agencias.
  * Aunque la API <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl">UDL (enlace profundo unificado)</Anchor> es el método predeterminado para enlaces profundos diferidos con AppsFlyer, esta API no es aplicable cuando la instalación se atribuye a una SRN, como en el caso de Amazon Ads.

<div id="raw-data-restrictions" />

## Restricciones de datos en bruto

Los datos en bruto de Amazon Ads están <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions#restricciones-de-fuente-de-medios">restringidos en la plataforma AppsFlyer</Anchor>. Por lo tanto, la fuente de medios se informa como “restringida” y los detalles de la campaña se muestran como nulos. Del mismo modo que con cualquier SRN, los clics y las impresiones de Amazon Ads no se incluyen en los informes de datos en bruto.

<div id="ctv-to-mobile-attribution" />

## Atribución de CTV a móvil

Amazon puede atribuir instalaciones de aplicaciones móviles a campañas de CTV (Connected TV), como las de Amazon Prime Video. Esto ocurre cuando un usuario que ve el anuncio de CTV ha iniciado sesión en una aplicación de Amazon en su dispositivo móvil.

**Nota:** No hay **ningún indicador de informes** que muestre explícitamente la campaña como CTV. Para mejorar la visibilidad y la medición, te recomendamos incluir `CTV` en el nombre de la campaña cuando corresponda.

<div id="support-amazon-eu-consent-policy" />

## Soporte para la política de consentimiento de Amazon en la UE

Amazon Ads está actualizando su política de consentimiento de los usuarios de la UE en preparación para la aplicación de la <Anchor target="_blank" href="https://commission.europa.eu/strategy-and-policy/priorities-2019-2024/europe-fit-digital-age/digital-markets-act-ensuring-fair-and-open-digital-markets_en">Ley de Mercados Digitales (DMA)</Anchor>. Como Partner de atribución de apps de Amazon, AppsFlyer se está adaptando a estos cambios de política para ayudar a los anunciantes a sacar el máximo partido de sus anuncios en Amazon. La política actualizada entrará en vigor el 30 de junio de 2026.

<div id="note-4" />

> 📘 **Nota**
>
> La política actualizada de consentimiento de la UE se aplica solo a los datos (instalaciones, re-engagements y eventos in-app) de usuarios de la UE, el Reino Unido o Suiza (CH).

Para cumplirla, envía la información de consentimiento DMA de AppsFlyer usando el mismo método que se utiliza para el <Anchor target="_blank" href="/marketers/es/docs/support-google-eu-consent-policy">consentimiento DMA de Google</Anchor>.

<div id="dma-consent-methods" />

### Métodos de consentimiento DMA

Actualmente, AppsFlyer admite dos métodos para compartir el consentimiento DMA:

| Emitido | Nota |
| --- | --- |
| **Manual** | El único campo que requiere Amazon es `ad_user_data_enabled`. |
| <Anchor target="_blank" href="https://iabeurope.eu/transparency-consent-framework/">**TCF**</Anchor> **(Marco de transparencia y consentimiento)** | Si usas una plataforma de gestión del consentimiento (CMP), asegúrate de que el ID del proveedor de Amazon Ads (**793**) esté incluido en la lista de proveedores permitidos. |

<div id="note-5" />

> 📘 **Nota**
>
> Amazon también admite señales de consentimiento a través de la <Anchor target="_blank" href="https://iabtechlab.com/gpp/">Global Privacy Platform (GPP)</Anchor>, pero AppsFlyer no admite actualmente este método.

<div id="see-also-1" />

> 📄 **Véase también**
>
> * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/send-consent-for-dma-compliance">Envía el consentimiento DMA a través del SDK de AppsFlyer</Anchor>
> * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/s2s-events-api3-overview">Envía el consentimiento DMA a través de S2S de AppsFlyer</Anchor> (busca `consent_data`)

<div id="traits-and-limitations" />

## Especificaciones y limitaciones

| Caducado | Nota |
| --- | --- |
| Agencias | La integración de Amazon Ads no es compatible con agencias en este momento, por lo que solo se puede gestionar desde la cuenta del anunciante. |
| Impresiones, clics y costo | Los datos de impresiones, clics y costo todavía no están disponibles para esta integración. |
| Nota | [Los deep links no son compatibles con esta integración](#enlaces-profundos-diferidos). |
| Reinstalación y reatribuciones | La reinstalación y la reatribución no son compatibles con esta integración. |
| Atribución de precarga | La medición de precarga no es compatible como parte de esta integración, pero se puede conseguir mediante la integración heredada amazon\_int. |
| Limitación del postback | En Android, cuando el campo `advertiserIdEnabled` se establece en "false", la instalación o el re-engagement no se enviará a Amazon aunque el ID del anunciante esté disponible. |

<div data-zendesk-anchors="activate-partner=activar-socio 01H88VAJH3B5ESK12D3ATMMVZ8=activar-socio complete-the-setup-in-amazon-ads=busque-la-nueva-integraci%C3%B3n-del-socio-y-selecci%C3%B3nela h_01KMG57HR62CC9TX495SG3WSRD=busque-la-nueva-integraci%C3%B3n-del-socio-y-selecci%C3%B3nela setting-up-amazon-dsp-integration=configuraci%C3%B3n-de-amazon-ads 01H88VAJH3VENKYVRQY5RXN63P=configuraci%C3%B3n-de-amazon-ads 01H88VAJH3BYZSXQGGZZJQ9N0C=nota 01H88VAJH3VZ4GPVE7XXMKTZ2P=integration-tab activate-partner::b746d215=activar-socio-1 01H88VAJH34GP7FK1KTJGRDPM7=activar-socio-1 general-settings=configuraci%C3%B3n-general 01H88VAJH3F2FJK5YP3M2V7RWD=configuraci%C3%B3n-general install-attribution=atribuci%C3%B3n-de-instalaci%C3%B3n 01H88VAJH3SSG6ZNV7XQ46W5CX=atribuci%C3%B3n-de-instalaci%C3%B3n reengagement-attribution=atribuci%C3%B3n-de-reengagement h_01J4RC3GR8B04RNFSD61QK45C0=atribuci%C3%B3n-de-reengagement ignore-active-users-for-retargeting=ignorar-usuarios-activos-para-retargeting h_01HNWSTJZPFQVQ5C8M0JA1J0T5=ignorar-usuarios-activos-para-retargeting h_01HMXNJVHK9C3FT8E04RE0TH99=nota-1 inapp-event-postbacks=postbacks-de-eventos-in-app 01H88VAJH3AS37MVF75GANWX4B=postbacks-de-eventos-in-app 01JEXXHXMEC5M7N1BDSGS3ZZ51=nota-2 01H88VAJH31GZ4KAY280ZRB8MA=attribution-link-tab 01H88VAJH3RM95V449B6DF8B4D=cost-tab 01H88VAJH3A2Q0CZXQQZMW6YRC=ad-revenue-tab 01H88VAJH30TCC574W2DH7R2A2=permissions-tab 01H88VAJH3XYP81GTFBWDBXECP=nota-3 h_01HDNZ59NQEDFC3D8JYGENR1NR=v%C3%A9ase-tambi%C3%A9n deferred-deep-linking=enlaces-profundos-diferidos 01J9G5FQGB0219RGWVW06BQPG7=enlaces-profundos-diferidos raw-data-restrictions=restricciones-de-datos-en-bruto 01JBY7HD39BA9ZNR2N2TYYPBW3=restricciones-de-datos-en-bruto ctvtomobile-attribution=atribuci%C3%B3n-de-ctv-a-m%C3%B3vil h_01JZG6S5TB1888XG9560MKEBF3=atribuci%C3%B3n-de-ctv-a-m%C3%B3vil support-amazon-eu-consent-policy=soporte-para-la-pol%C3%ADtica-de-consentimiento-de-amazon-en-la-ue h_01KP0DJ73P9FRX51SR3RS4YWVP=soporte-para-la-pol%C3%ADtica-de-consentimiento-de-amazon-en-la-ue h_01KP0DJ73PDB7FM1RG0VV99707=nota-4 dma-consent-methods=m%C3%A9todos-de-consentimiento-dma h_01KP0DJ73PG0JMWG3WAWCKXE1S=m%C3%A9todos-de-consentimiento-dma h_01KP0DJ73PNPYT0TRWF089VE9R=nota-5 h_01KP0DJ73PC4ABGRPRDAR7BW5B=v%C3%A9ase-tambi%C3%A9n-1 traits-and-limitations=especificaciones-y-limitaciones h_01J6S6HS0H0M6GQ81WGZ3XT0P9=especificaciones-y-limitaciones" />
