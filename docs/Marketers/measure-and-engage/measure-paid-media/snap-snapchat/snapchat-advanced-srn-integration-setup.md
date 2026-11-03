---
title: 'Snapchat: configuración avanzada de la integración de SRN'
metadata:
  keywords:
    - configuration
    - snapchat measurement partner
    - snapchat
    - measurement
    - snapchat measurement analytics
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2016-06-13T12:28:59Z'
  edited_at: '2026-10-09T00:15:00Z'
  id: 211011983
  locale: es
  section: Snap (Snapchat)
  section_id: 6551316540945
  url: https://support.appsflyer.com/hc/es/articles/211011983
---
> **At a glance:** Aprende cómo configurar la integración entre AppsFlyer y Snapchat para habilitar la medición de la atribución. Snapchat es una SRN avanzada (red de autoinforme).

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/snapchat.png?v=1" width="52px" />

## Resumen

Una integración avanzada de SRN significa que todo el tráfico <Anchor target="_blank" href="/marketers/es/docs/appsflyer-knowledge-base-glossary?query=glossar#dual-consent">con doble consentimiento</Anchor> se atribuye y se reporta como tráfico SRN regular. Para el tráfico sin consentimiento, AppsFlyer puede atribuir y medir la atribución en función de los clics y las impresiones procedentes de Snapchat mediante <Anchor target="_blank" href="/marketers/es/docs/self-reporting-networks-srns#cómo-funciona-la-atribución-con-las-srns-avanzadas">otros métodos de atribución</Anchor>, de acuerdo con las restricciones de privacidad.

## Configura la integración de Snapchat

**Requisito previo:** Antes de configurar la integración, asegúrate de **ponerte en contacto con el partner** y abrir una cuenta con ellos. Si no tienes una cuenta, ponte en contacto con Snapchat para abrir una antes de configurar la integración.

**Para activar o editar la integración:**

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de Partners > Marketplace**.  
   (**Para editar una integración existente:** ve a la pestaña **Colaborar > Integraciones de Partners > Integraciones activas**.)
2. Selecciona la aplicación correspondiente.
3. Busca Snapchat y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el conmutador **Activar partner**.  
   **Nota:** El selector **debe permanecer activado (activo) mientras trabajes con Snapchat**. Saber más sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activación y desactivación de Partners</Anchor>.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de Partners</Anchor>.

<Accordion title="Pestaña de Integración">

La integración admite la atribución de clic e impresiones, el costo y las audiencias.

#### Activar partner

En la **primera visita** aquí, debes activar **Activate Partner** para habilitar la configuración.  
Para obtener más información sobre la activación del partner, consulta <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Activación y desactivación del partner</Anchor>.

**Habilitar la atribución**

Activa **Activar partner** para permitir la atribución a Snapchat.

![mceclip0.png](https://files.readme.io/cf4e73fec951e4e9d2c1919ca20adff88fc0d49d7fea9b033ab9c39194ce2702-360003259638.png)

#### Configuración general

**ID de aplicación de Snap**

1. En tu Snap Business Manager, ve a Aplicaciones y copia el ID de aplicación de Snap (consulta la guía de Snapchat sobre <Anchor target="_blank" href="https://businesshelp.snapchat.com/en-US/a/snap-app-id">cómo generar un ID de aplicación de Snap</Anchor>).
2. Pega el ID en el campo ID de aplicación de Snap en AppsFlyer.

![snapchat-app-id.png](https://files.readme.io/2e5f53240893e2a80ba36065f67f4504f69e1167d96ef35bd7a4ab874d5a7bb9-360008280878.png)

**En caso de que una agencia promocione la aplicación**:

* El ID de aplicación de Snap solo puede agregarlo el anunciante.
* Si la agencia está bajo la misma organización que tú en la plataforma de anuncios de Snapchat, usa solo un ID de aplicación de Snap.
* Si la agencia está bajo una organización diferente en la plataforma de anuncios de Snapchat, solicítales que proporcionen su ID de aplicación de Snap para esta aplicación e introdúcelo en este campo. Se pueden introducir varios ID. Presiona Enter después de cada ID.

#### Privacidad Avanzada

El interruptor **Privacidad avanzada** (AP) controla qué eventos AppsFlyer envía a Snapchat. Esta configuración también se denomina **Conversiones avanzadas** en Snapchat.

* **Privacidad avanzada DESACTIVADA**: AppsFlyer envía todas las instalaciones, los re-engagement y los eventos in-app a Snapchat para la atribución, incluidos los eventos de los usuarios que no han puesto su IDFA (identificador para anunciantes) a disposición.  
  **Importante:** Para usar la <Anchor target="_blank" href="https://businesshelp.snapchat.com/s/article/unified-attribution?language=en_US">solución de atribución unificada</Anchor> de Snapchat, debes desactivar el interruptor de Privacidad avanzada.
* **Privacidad avanzada ACTIVADA**: AppsFlyer envía solo instalaciones, re-engagement y eventos in-app de los usuarios que han puesto su IDFA a disposición.

> 📘 **Note**
>
> Las agencias no pueden activar la Privacidad avanzada, incluso cuando el anunciante les concede permiso. Esta configuración está limitada únicamente al anunciante.

#### Uso compartido de datos de Advanced Matching

Cuando la opción **Uso compartido de datos de Advanced Matching** está activada, los campos de Advanced Matching, como el correo electrónico hashed, el número de teléfono hashed, el nombre hashed y el apellido hashed, se comparten con Snapchat si estos campos se incluyen en la información del evento enviada a AppsFlyer. Para obtener más información, consulta: <Anchor target="_blank" href="/marketers/es/docs/advanced-matching-data-sharing">Uso compartido de datos de Advanced Matching</Anchor>.

#### Atribución de instalación.

Configura las diferentes ventanas de atribución para atribuir nuevas instalaciones (primeros lanzamientos) de usuarios que vieron, hicieron clic o interactuaron con tu anuncio. Tenga en cuenta que solo las instalaciones dentro de la ventana de retroceso pueden atribuirse a Snapchat.

**Nota:** No se admite la atribución de reinstalaciones (cualquier instalación que no sea la configuración inicial en el dispositivo).

1. Configura la **ventana de lookback de instalaciones por clic** en 1-23 horas o 1-30 días. **Nota:** Snapchat recomienda alinearte con ellos configurando la ventana de lookback de instalaciones por clic en 7 días.

> 📘 **Note**
>
> La configuración de la ventana retrospectiva de clic también determina las ventanas retrospectivas de clics y por impresiones de engagement.

2. [Opcional] Activa **la atribución view-through de instalación** y configura las ventanas de lookback:
   * **Ventana de lookback de instalación por view-through** entre 1-24 horas. **Nota:** Snapchat recomienda alinearte con ellos configurando la ventana de lookback de instalación por view-through en 1 día.

#### Atribución de re-engagement

Configura las diferentes ventanas de atribución para atribuir las nuevas interacciones de tus usuarios existentes que vieron, hicieron clic o interactuaron con tu anuncio. Ten en cuenta que solo los nuevos re-engagements de la ventana retrospectiva se pueden atribuir a Snapchat.

1. Configura la **ventana de lookback de re-engagement por clic** en 1-23 horas o 1-30 días. **Nota:** Snapchat recomienda alinearte con ellos configurando la ventana de lookback de re-engagement por clic en 7 días.

> 📘 **Note**
>
> La configuración de la ventana retrospectiva de clic de re-engagement también determina las ventanas retrospectivas de clics y por impresiones de engagement.

2. [Opcional] Activa **la atribución view-through de re-engagement** y configura las ventanas de lookback:
   * **Ventana de lookback de re-engagement por view-through** entre 1-24 horas. **Nota:** Snapchat recomienda alinearse con ellos configurando la ventana de lookback de view-through de Re-engagement en 1 día.
3. Configura la **ventana de Re-engagement** en 1-23 horas, 1-90 días o **Lifetime**.

#### Ignorar usuarios activos para retargeting

Establece un período de ventana para <Anchor target="_blank" href="/marketers/es/docs/set-retargeting-inactivity-window#periodo-de-inactividad">ignorar los re-engagements y las reatribuciones</Anchor> de los usuarios que abrieron tu aplicación. Esto significa que su actividad durante el periodo de la ventana no se registra en AppsFlyer.

> 📘 **Note**
>
> Las conversiones de Re-engagement y reatribución de los usuarios que estuvieron **inactivos** durante el período establecido **se registran**.

1. Activa **Ignorar usuarios activos para el retargeting**.
2. Configura la ventana de inactividad.

#### Postbacks de eventos in-app

Asigna eventos de AppsFlyer con el partner a través de postbacks. Si el envío de postbacks está activado, esto incluye los eventos in-app rechazados (eventos bloqueados por Protect360 o eventos que no cumplen con las reglas de validación del targeting).

[![mceclip0.png](https://files.readme.io/9df3455b102ff280e8b0fae4bfc006fa87f8830d74064eb955fc829d06708165-23458868914577.png)](https://files.readme.io/9df3455b102ff280e8b0fae4bfc006fa87f8830d74064eb955fc829d06708165-23458868914577.png)

**Para configurar postbacks de eventos in-app:**

1. Establece el **ID de partner** (si es necesario).
2. Habilita el **postback de evento in-app**.
3. Establece la **ventana de postback de evento in-app**, si es necesario (lee más sobre la <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#ventana-de-postback-de-eventos-in-app">configuración de la ventana de postback de evento in-app</Anchor>).
4. Si está disponible, selecciona si deseas enviar los eventos de forma automática o manual. Saber más sobre <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#send-events-as-they-are-unmapped">enviar todos los eventos tal como están</Anchor>.
5. Haz clic en **Agregar evento** para añadir un evento de SDK o de servidor a servidor a la lista.
6. Completa los parámetros según sea necesario.
7. [Opcional] Haz clic en <Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" /> para establecer condiciones para enviar ciertos eventos in-app al partner.  
   Aprende más sobre los <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#postbacks-condicionales-de-eventos-in-app">postbacks condicionales de eventos in-app</Anchor>.

| Nombre del parámetro | Description |
| --- | --- |
| **Evento de AppsFlyer** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea del SDK integrado en tu aplicación o de los eventos servidor a servidor.<br />**Consejo**: ¿No ves el evento que estás buscando?<ul><li>Asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar.</li><li>Escríbelo en **evento de AppsFlyer** , y luego haz clic en **Crear personalizado**. Lee más sobre la <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#eventos-personalizados">asignación de eventos personalizada</Anchor>.</li></ul> |
| **Asignado al evento de socio** | El nombre o ID único de cada evento, definido por el partner. Existen varias configuraciones de asignación:<ul><li>**Campo de texto:** obtén el ID del evento correspondiente del partner.</li><li>**Cuadro desplegable:** selecciona el evento de AppsFlyer predefinido más adecuado.</li><li>**Tal como está**: envía los eventos tal como están, sin asignación de nombres.</li></ul> |
| **Para usuarios de** | Seleccione la opción de envío para el evento:<ul><li>**Solo este partner**: envía postbacks solo cuando este evento se atribuye a este partner.</li><li>**Todas las fuentes de medios, incluidas las orgánicas**: envía postbacks de eventos atribuidos a cualquier partner y eventos orgánicos.</li></ul> |
| **incluye** | <ul><li>**Sin datos (predeterminado)**: envía solo el evento en sí, sin el valor del evento.</li><li>**Valores e ingresos**: envía todos los parámetros del evento, **incluido** el valor de ingresos (si existe en el evento).</li><li>**Valores sin ingresos**: envía todos los parámetros **excluyendo** el valor de ingresos.</li></ul> |

</Accordion>

<Accordion title="Pestaña de enlaces de atribución">

Los enlaces de atribución no están disponibles para Snapchat.

> 📘 **Note**
>
> Para todas las SRN, como Facebook, Apple Ads, Google Ads y Snapchat, esta pestaña no funciona, ya que no usan enlaces de atribución externos.

</Accordion>

<Accordion title="Pestaña de costo">

La integración de costos proporciona los siguientes datos agregados:

* Datos de costos de tus campañas, a nivel de conjuntos de anuncios, anuncios y canal. Consulta la <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabla de integración de costos de ad network</Anchor> para obtener todos los detalles sobre las dimensiones, métricas y funciones compatibles.  
  **Nota:** Los datos de costo requieren una suscripción a <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor>.
* Datos sobre clics e impresiones.

**Para habilitar la API de costo**:

* Sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">estas instrucciones de integración</Anchor>.

<div id="cost-data-sync-status" />

<Accordion title="Estado de sincronismo de datos de costos">

<Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Consulta el estado de tu API de costo</Anchor> y la última vez que AppsFlyer logró extraer datos de costo coincidentes, ya sea en el dashboard de estado de integración de costo (e ingresos por anuncios) o en el dashboard de la ad network individual.

</Accordion>

<div id="stop-snapchat-cost-sync" />

<Accordion title="Detener la sincronización de costos de Snapchat">

**Para dejar de obtener los costos de Snapchat y eliminar una cuenta de Snapchat conectada:**

* <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#deleting-connected-accounts-in-the-cost-tab">En la columna de acciones, coloca el cursor sobre una cuenta y haz clic en **Eliminar conexión**</Anchor>.  
  Una vez eliminado, AppsFlyer deja de recibir el costo. Eliminar la conexión no afecta los datos anteriores.

</Accordion>

> 📘 **Note**
>
> * Asegúrate de que la configuración de tu campaña en Snapchat sea para una aplicación iOS o Android, no para ambas. Si la campaña es para ambas aplicaciones, AppsFlyer no puede desglosar el costo por aplicación, y el costo no se muestra en AppsFlyer.
> * Para evitar discrepancias en los datos de costos, establece la misma zona horaria tanto en la configuración de la aplicación como en tu cuenta de publicidad de Snapchat.
> * Una vez que configures el costo de Snap, no cambies el nombre de ninguna campaña activa, conjunto de anuncios ni anuncio individual, ya que esto puede provocar discrepancias graves o datos de costo faltantes.

</Accordion>

<Accordion title="Pestaña de ingresos por publicidad">

Los ingresos por publicidad no se admiten en la integración con este partner.

</Accordion>

<Accordion title="Pestaña de permisos">

Selecciona qué <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos conceder</Anchor> a Snapchat para acceder a tus datos y realizar varias acciones.

> 📘 **Note**
>
> Cuando la integración está desactivada pero el ajuste de Permisos sigue activado, los permisos permanecen vigentes.

</Accordion>

## Web a app: medición de la actividad de la aplicación para campañas que no son de aplicaciones

La integración de AppsFlyer con Snapchat permite una medición exhaustiva de la actividad de la aplicación, como instalaciones, re-engagements y eventos in-app, para campañas que no son de aplicaciones atribuidas a Snapchat.

Por ejemplo, las instalaciones de aplicaciones se pueden medir incluso cuando el destino del anuncio es una landing page web, lo que permite medir la trayectoria del usuario web-to-app (W2A). Para habilitar este tipo de medición, activa el <Anchor target="_blank" href="https://businesshelp.snapchat.com/s/article/app-id-tracking">Snap App ID Tracking Toggle</Anchor> en Snapchat Ads Manager.

Si sigues estas instrucciones, podrás medir de forma eficaz la actividad de la aplicación de las campañas no relacionadas con la aplicación de Snapchat y obtener insights valiosos sobre el comportamiento de los usuarios.

## Enlaces profundos con Snapchat

Los enlaces profundos con Snapchat se basan en el uso de un enlace profundo nativo en la plataforma de Snapchat, al tiempo que se le agregan parámetros de AppsFlyer.

Para realizar enlaces profundos con Snapchat:

1. Verifica que **deep linking** para [retargeting esté habilitado para Snapchat](/docs/snapchat-advanced-srn-integration-setup#configura-enlaces-profundos-en-la-plataforma-snap).
2. Verifica que <Anchor target="_blank" href="/marketers/es/docs/app-settings#reengagement-attribution">la atribución de re-engagement esté habilitada en AppsFlyer</Anchor>.
3. Toma el URI del esquema de enlace profundo de la aplicación y añade **al menos** los siguientes parámetros:
   * **PID** - La fuente de medios en este caso siempre es **snapchat\_int**. Esto permite que todos los datos aparezcan en el dashboard de AppsFlyer bajo la fuente de medios **Snapchat\_int** .
   * **C -** el nombre de la campaña correspondiente
   * **is\_retargeting=true**: este campo define la campaña como una campaña de retargeting. Los engagements de los usuarios existentes con la campaña de retargeting se marcan como re-engagements debido a la existencia de este campo en el URI. Esto asegura que los datos del usuario aparezcan en el dashboard de retargeting.

> 📘 **Note**
>
> **Ejemplo de URI**
>
> client://home?pid=snapchat\_int&c=TEST&is\_retargeting=true

### Configura enlaces profundos en la plataforma Snap

1. Ve al tipo de oportunidad **Drive traffic to app** .
2. Agrega el URI de enlace profundo:  
     
   [![](https://files.readme.io/428258bbc5eb2fc7332ea07356e098eb66ac2cfdd0955117a14666eb76a20f79-360001717778.png)](https://files.readme.io/428258bbc5eb2fc7332ea07356e098eb66ac2cfdd0955117a14666eb76a20f79-360001717778.png)

### Enlaces profundos diferidos con Snapchat

AppsFlyer ofrece una serie de soluciones para enlaces profundos diferidos:

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl">**UDL (Unified deep linking)**</Anchor> : Los clics de Snapchat incluyen un campo <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#deep_link_value">deep\_link\_value</Anchor> (cuando se establece un deep link para el anuncio) y son compatibles con la solución UDL.
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#recommended-implement-extended-deferred-deep-linking">**GCD (Get Conversions Data) API**</Anchor> : Esta es la opción recomendada para acceder a los datos de conversión de usuarios de Snapchat en tiempo real, directamente en el nivel del SDK. Los datos devueltos en la API de GCD incluyen el parámetro <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#af_dp">`af_dp`</Anchor>, que contiene el destino real del deep link (destino del usuario dentro de la aplicación).
* **Uso de parámetros de datos de conversión:** Puedes crear una lógica personalizada para dirigir al usuario a tu contenido usando otros parámetros, como el nombre de la campaña, el nombre del conjunto de anuncios o cualquier otro campo que se devuelva como parte de los datos de atribución de las instalaciones de Snapchat.

## Configuración de Snapchat para agencias

Las agencias que trabajan en nombre de los anunciantes pueden activar la integración de Snapchat y comenzar a obtener atribución por sus campañas. No obstante, esta integración tiene algunas limitaciones cuando se trata de agencias.

### Limitaciones para agencias

* Una agencia puede acceder a la integración de Snapchat solo después de que el anunciante con el que trabaja la haya activado en su lado.
* Los parámetros de atribución que aparecen en la página de integración de la agencia se heredan de la integración del anunciante en modo **solo visualización** . Esto significa que la agencia puede ver cómo el anunciante configuró las ventanas retrospectivas de atribución pero no puede configurarlas por su cuenta.
* Para los eventos posteriores a la atribución, si el anunciante le otorga permiso, una agencia puede configurar postbacks de eventos in-app.
* Una agencia no puede activar Privacidad avanzada, incluso cuando se le concede permiso (consulta **Advanced Privacy** arriba).

**Para configurar Snapchat para agencias:**

1. En AppsFlyer, en **Configuración**, ve a **Partner Marketplace**.
2. Busca **Snapchat** y selecciónalo.
3. Introduce el **ID de cuenta de Snapchat** de tu agencia. Esto **identifica el tráfico de la agencia y lo distingue del anunciante.** Puedes ingresar hasta 50 ID de cuentas de Snapchat diferentes. Todos los datos de atribución procedentes de las cuentas que has introducido son visibles en el dashboard de la agencia.
4. Haz clic en **Guardar integración**.

![snapchat-agency-integration.png](https://files.readme.io/261a0246bb7da0899e653a776eb25e17ce3ae8bff1efef33acac0ef0bf99abcf-21074932431505.png)

> 🚧 **Important**
>
> Los ID de cuenta de Snapchat no deben compartirse entre el anunciante y la agencia. Si se comparten, todas las instalaciones del anunciante se atribuyen automáticamente en el dashboard de la agencia.

## Restricciones de raw data

* Desde el 1 de marzo de 2023, las desinstalaciones de Snapchat no se incluyen en los reportes de raw data.
* A partir del 12 de septiembre de 2023, Snapchat proporciona a los anunciantes datos de atribución por impresiones limitados a nivel de dispositivo. Para fuentes a nivel de usuario, como reportes de raw data, mensajes de Push API, reportes de Pull API, la página Datos exportados y Data Locker, se completan los siguientes campos:
  * Fuente de medios (snapchat\_int)
  * Canal
  * Tipo de toque atribuido (impresión)
  * Hora de toque atribuida (reportada solo como fecha - "dd/mm/aaaa")
  * Nombre e ID de la campaña (a partir del 15 de diciembre de 2025)
  * Nombre e ID del conjunto de anuncios (a partir del 15 de diciembre de 2025)
* A partir del 6 de octubre de 2026, los datos de atribución view-through de `snapchat_int` están limitados (restringidos) en raw data solo en algunos casos. La lógica de las restricciones de evento la gestiona Snapchat.

## Retención de datos de Snapchat

Snapchat exige que los proveedores de atribución eliminen sus datos de nivel de usuario 12 meses después de la instalación. Esto significa que los eventos efectuados por estos usuarios 12 meses después de que hayan instalado la aplicación se cuentan como orgánicos.

Los datos agregados anteriores permanecen iguales.

<div data-zendesk-anchors="overview=resumen 01H8F1RWVPTHBDGF3830DY7G7M=resumen setting-up-snapchat-integration=configura-la-integraci%C3%B3n-de-snapchat 01H7WQ47ECTZHPKMG5Z5ZPAND5=configura-la-integraci%C3%B3n-de-snapchat activate-partner=activar-partner 01H7WQ47ECZB5GNCQ0XH68N1DK=activar-partner general-settings=configuraci%C3%B3n-general 01H7WQ47ECQSQPP63H398NTQ6M=configuraci%C3%B3n-general h_01_advanced-privacy=privacidad-avanzada advanced-privacy=privacidad-avanzada h_01_advanced-matching-data-sharing=uso-compartido-de-datos-de-advanced-matching advanced-matching-data-sharing=uso-compartido-de-datos-de-advanced-matching install-attribution=atribuci%C3%B3n-de-instalaci%C3%B3n 01H8VVCC8GK8VFPBEPAMVHCAWM=atribuci%C3%B3n-de-instalaci%C3%B3n reengagement-attribution=atribuci%C3%B3n-de-re-engagement 01H8VVCC8HHG5290PYF0BT29QA=atribuci%C3%B3n-de-re-engagement ignore-active-users-for-retargeting=ignorar-usuarios-activos-para-retargeting h_01HNWSTJZPFQVQ5C8M0JA1J0T5=ignorar-usuarios-activos-para-retargeting inapp-event-postback-settings=postbacks-de-eventos-in-app 01H8VVCC8HHZRFQ2T1X478YZMP=postbacks-de-eventos-in-app 01H7WQ47ED1HYEBHFJDHTB6HJH=cost-data-sync-status 01H7WQ47ED3P53B269W93Z341E=stop-snapchat-cost-sync web-to-app-measuring-app-activity-for-nonapp-campaigns=web-a-app-medici%C3%B3n-de-la-actividad-de-la-aplicaci%C3%B3n-para-campa%C3%B1as-que-no-son-de-aplicaciones h_01JJMAS0W9WMEPJCQWD9BXAEZ2=web-a-app-medici%C3%B3n-de-la-actividad-de-la-aplicaci%C3%B3n-para-campa%C3%B1as-que-no-son-de-aplicaciones deep-linking-with-snapchat=enlaces-profundos-con-snapchat 01H7WQ47EDC973V7CPE38QAQE7=enlaces-profundos-con-snapchat how-to-set-up-deep-links-on-snap-platform=configura-enlaces-profundos-en-la-plataforma-snap 01H7WQ47EDJAX2DW7A2JJ4XVJN=configura-enlaces-profundos-en-la-plataforma-snap deferred-deep-linking-with-snapchat=enlaces-profundos-diferidos-con-snapchat 01H7WQ47EDS3MYRN9A9ZPHXG9Z=enlaces-profundos-diferidos-con-snapchat setting-up-snapchat-for-agencies=configuraci%C3%B3n-de-snapchat-para-agencias 01H7WQ47EDARK9SSP47V5MGX18=configuraci%C3%B3n-de-snapchat-para-agencias agency-limitations=limitaciones-para-agencias h_01HHVGS94CB9XC0T63VFDZ18JS=limitaciones-para-agencias raw-data-restrictions=restricciones-de-raw-data h_01HA3XZPWSKVRX7VTRXT1WQ1EZ=restricciones-de-raw-data keeping-snapchat-data=retenci%C3%B3n-de-datos-de-snapchat 01H7WQ47ED9STKS1CVW5EXYX0Z=retenci%C3%B3n-de-datos-de-snapchat" />
