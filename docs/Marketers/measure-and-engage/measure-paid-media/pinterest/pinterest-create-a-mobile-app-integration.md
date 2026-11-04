---
title: Pinterest—Crear una integración de aplicación móvil
metadata:
  keywords:
    - Pinterest
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
  created_at: '2016-11-09T12:51:03Z'
  edited_at: '2026-09-11T00:29:03Z'
  id: 216912786
  locale: es
  section: Pinterest
  section_id: 6551388216337
  url: https://support.appsflyer.com/hc/es/articles/216912786
---
> **En resumen:** Pinterest, un partner integrado de AppsFlyer, es uno de los principales contribuyentes de tráfico para blogueros y marcas. Pinterest ofrece atribución móvil basada en clics y view-through. Además, Pinterest también ofrece un retargeting basado en clics que puedes grabar con AppsFlyer.

<div id="note" />

> 📘 **Nota:**
>
> * Tras aceptar los términos de los anuncios de Pinterest, aceptas los términos y condiciones de medición móvil de Pinterest <Anchor target="_blank" href="https://ads.pinterest.com/terms/app_install/">aquí</Anchor>.
> * Pinterest exige que los proveedores de atribución eliminen sus datos a nivel de usuario <Anchor target="_blank" href="/marketers/es/docs/user-level-data-retention#periodos-de-conservación-de-los-datos-de-partners">6 meses después de la instalación</Anchor>. Esto significa que los eventos efectuados por estos usuarios 6 meses después de que hayan instalado la aplicación se cuentan como orgánicos. Los datos agregados anteriores permanecen iguales.
> * A partir del 4 de septiembre de 2023, Pinterest exige a los proveedores de atribución que <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions#restricciones-de-fuente-de-medios">restrinjan la disponibilidad de algunos campos en los reportes de raw data</Anchor> para preservar la privacidad de los usuarios y garantizar el cumplimiento de la normativa.

<div id="set-up-pinterest" />

## Configurar Pinterest

**Requisito previo:** Una cuenta con el Partners. Si no tienes una cuenta, ponte en contacto con el Partners para abrir una antes de configurar la integración.

**Para configurar una nueva integración:**

1. En AppsFlyer, ve a la pestaña **Colaborar > Integraciones de Partners > Marketplace** .  
   (**Para editar una integración existente:** Ve a la pestaña **Colaborar > Integraciones de Partners > Integraciones activas** .)
2. Selecciona la aplicación correspondiente.
3. Busca el Partners y selecciona **Integrar**.
4. En la pestaña **Integración**, activa el interruptor **Activar partner**.   
   **Nota:** El interruptor **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de Partners.</Anchor>

<div id="integration-tab" />

<Accordion title="Pestaña integración">

<div id="activate-partner" />

### Activar partner

En la **primera visita**, tendrás que activar el botón **Activar partner** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para más detalles sobre la activación de partners, <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">haz</Anchor> clic aquí.

<div id="general-settings" />

### Configuración general

La siguiente es la configuración general de la pestaña de integración de Pinterest.

**Habilitar la atribución por impresiones**

Actívala si quieres atribuir las instalaciones por impresiones directas desde Pinterest. El control deslizante de la ventana de lookback view-through está disponible en la pestaña del enlace de atribución (se describe a continuación).

**Uso compartido de datos de Advanced Matching**

Activa esta opción para compartir con Pinterest los campos de Advanced Matching, como el correo electrónico con hash, el número de teléfono con hash, el nombre con hash y el apellido con hash, si estos campos se incluyen en la información del evento enviada a AppsFlyer. Para más información, consulta: <Anchor target="_blank" href="/marketers/es/docs/advanced-matching-data-sharing">Uso compartido de datos de Advanced Matching</Anchor>.

<div id="in-app-events-settings" />

### Configuración de eventos in-app

Para poder enviar correos electrónicos de postbacks de eventos in-app a Pinterest, debes introducir un identificador de etiqueta. Estas credenciales se incluirán en los postbacks de evento enviados a Pinterest.

* **ID de la cuenta de anuncios** - El identificador único de tu cuenta de Pinterest.
* **Token de acceso** - Un token de acceso generado en Pinterest.

Puedes encontrar el ID de tu cuenta de anuncios y el token de acceso directamente en la interfaz de usuario de Pinterest Ad Manager (consulta la [documentación de Pinterest](https://developers.pinterest.com/docs/api-features/tracking-conversions/#getting-your-access-token-and-ad-account-id)).  Ponte en contacto con el equipo de Pinterest si necesitas ayuda.

**Configura las credenciales de Pinterest:**

1. **Requisito previo:** Antes de configurar la integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">ponerte en contacto con el partner</Anchor> y abrir una cuenta con ellos.
2. Introduce los valores del ID de la cuenta de anuncios y del token de acceso en sus respectivos campos.

<div id="legacy-set-tag-id" />

#### ID de etiqueta

Para obtener el ID de la etiqueta y establecer los postbacks de eventos in-app:

1. En tu cuenta comercial de Pinterest, ve a **Anuncios** > **Conversiones** y copia el **ID de la etiqueta**.  
   Haz clic en **Crear etiqueta** si aún no tienes una y completa el proceso de creación. Copia la nueva etiqueta.
2. En AppsFlyer, en la configuración de integración de Pinterest, desplázate a **Configuraciones de eventos in-app** e ingresa el ID de la etiqueta de Pinterest.

<div id="in-app-event-postbacks" />

### Habilitar la atribución por impresiones

En esta sección, puedes asignar tus eventos de AppsFlyer con Pinterest mediante postbacks.

1. Configuración de la campaña de Pinterest
2. Activa **Postbacks de evento in-app.**
3. Configura la ventana de postbacks de eventos in-app.
4. Selecciona la configuración de postback y los mapeos para los eventos.

| Nombre del parámetro | Descripción |
| --- | --- |
| <span id="appsflyer-event-name"></span>**Nombre del evento de AppsFlyer** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea desde el SDK integrado con tu aplicación o desde eventos de servidor a servidor.  <br /> **Consejo**: Si no ves el evento que buscas en la lista, asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar. |
| <span id="partner-event-name"></span>**Nombre del evento del partner** | El nombre o ID único de cada evento tal y como se define en Pinterest.  <br /> Obtén el ID de evento correspondiente de Pinterest y configúralo en el campo de texto. |
| <span id="to-users-from"></span>**Para usuarios de** | <ul><li>Nota</li><li>**Solo este partner** para eventos que provienen **solo** de usuarios atribuidos a este partner<br />**Todas las fuentes de medios, incluidas las orgánicas** para que toda tu base de usuarios esté disponible para ser reportada al partner.</li></ul> |
| <span id="including"></span>**Incluye** | Selecciona si los ingresos por eventos o los valores de parámetros se envían al partner en el postback, o si estos datos no están incluidos.<br /><br />AppsFluer puede envían todos los parámetros del evento enriquecido in-app, excepto el parámetro de ingresos, que se encuentra en el parámetro **af\_revenue**. O bien, AppsFlyer puede envían todos los parámetros, incluyendo el valor de los ingresos (si existe en el evento). |

5. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlace de atribución">

Genera y guarda enlaces de atribución y envíalos al partner para que te atribuya campañas específicas, conjuntos de anuncios o anuncios únicos, tanto para campañas de UA como de retargeting. Puedes utilizar un enlace de plataforma única o un <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">Saber más sobre la estructura y los parámetros de los enlaces de atribución</Anchor>.

**Para generar un enlace de atribución,** sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#attribution-link-tab">estas instrucciones</Anchor>.

<div id="attribution-link-for-retargeting-campaign" />

#### Enlace de atribución para la campaña de retargeting

Pinterest recomienda utilizar enlaces de atribución específicos del sistema operativo para las campañas de retargeting. Selecciona la opción **Usar un enlace de plataforma única** y agrega los parámetros necesarios al enlace de atribución de retargeting.

<div id="deep-link-url" />

#### URL de deep link

<div id="note-1" />

> 📘 **Nota:**
>
> Los deep linking desde un pin solo funcionarán correctamente cuando tu aplicación esté en la lista de permitidos de Pinterest.
> Ponte en contacto con tu representante de Pinterest o envía un correo electrónico a [apps@pinterest.com](mailto:apps@pinterest.com) para que te permitan incluirlos en la lista de deep linking.

Utiliza este campo si el enlace tiene por objeto establecer deep links entre los usuarios y cualquier actividad específica dentro de tu aplicación.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costo">

Una vez que hayas establecido el coste de Pinterest, no cambies el nombre de ninguna campaña, conjunto de anuncios o anuncio único que se esté ejecutando, ni utilices macros dinámicas con el parámetro del nombre de la campaña, ya que pueden provocar discrepancias importantes o la falta de datos de costes.

<div id="enabling-and-testing-pinterest-integration" />

### Habilitar y probar la integración de Pinterest

AppsFlyer obtiene los detalles de los costos por API. Consulta <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">la tabla de integración de costos de redes de publicidad</Anchor> para obtener más información sobre las dimensiones, métricas y funciones admitidas. **Nota**: Los datos de costos requieren una suscripción a ROI360.

**Para habilitar la API de costos**:

* Sigue <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">estas instrucciones de integración</Anchor>.

<div id="cost-data-sync-status" />

### Estado de sincronización de datos de costos

<Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Visualiza el estado de tu API de costos</Anchor> y la última vez que AppsFlyer logró extraer los datos de costos coincidentes en el dashboard de estado de la integración de costos (e ingresos por publicidad) o en el dashboard de la ad network individual. 

<div id="stop-pinterest-cost-sync" />

### Detener la sincronización de costos de Pinterest

**Para eliminar una cuenta conectada:**

* <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#deleting-connected-accounts-in-the-cost-tab">En la columna “Acciones”, desplaza el cursor sobre una cuenta y haz clic en ***Eliminar conexión***</Anchor>. Una vez eliminado, AppsFlyer deja de recibir el costo. La eliminación de la conexión no afecta a los datos históricos.

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de ingresos por publicidad">

Este partner no admite ingresos por publicidad.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

En esta pestaña, puedes seleccionar los permisos que quieres conceder a Pinterest. Ten en cuenta que, aunque la atribución esté deshabilitada en Pinterest, la pestaña de permisos está activa y puedes conceder el control a Pinterest.

Obtén más información sobre los <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos que puedes conceder a Pinterest</Anchor>.

</Accordion>

</Accordion>

<div id="troubleshooting" />

## Resolución de problemas

Mensaje de error de la pestaña de costos: *La ausencia de datos coincidentes* significa que la cuenta de Pinterest que conectaste a AppsFlyer no es la cuenta de Pinterest correcta. No se encontraron datos que coincidan con la aplicación. Debes iniciar sesión en Pinterest con credenciales diferentes

<div data-zendesk-anchors="h_01H95QTA3ZZ9GJW9EN1VZ01TH2=nota set-up-pinterest=configurar-pinterest h_01H95QTA3Z5HXW39AHAF8FMFWH=configurar-pinterest h_01H95QTA3ZNQWBRA86E6TRQ46Y=integration-tab activate-partner=activar-partner h_01H95QTA3ZGEM34HY1A7NC8NX7=activar-partner general-settings=configuraci%C3%B3n-general h_01H95QTA3Z0NW9V51D8J7MHEX0=configuraci%C3%B3n-general inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01JTDP2T0BFP5WP03X5EMXVAWA=configuraci%C3%B3n-de-eventos-in-app %5Blegacy%5D-set-tag-id=id-de-etiqueta h_01JTMX6DD0G101KC0HQ0D34S48=id-de-etiqueta inapp-event-postbacks=habilitar-la-atribuci%C3%B3n-por-impresiones h_01JTDP2T0BTW986GN5HSWPR3JH=habilitar-la-atribuci%C3%B3n-por-impresiones h_01H95QTA3ZT7PVGAJW5AKPC186=attribution-link-tab attribution-link-for-retargeting-campaigns=enlace-de-atribuci%C3%B3n-para-la-campa%C3%B1a-de-retargeting h_01H95QTA3ZPQZ422AB2JBZAS07=enlace-de-atribuci%C3%B3n-para-la-campa%C3%B1a-de-retargeting deep-link-url=url-de-deep-link h_01H95QTA3ZT23CYTCE2V3728MD=url-de-deep-link h_01H95QTA3ZYHQED2T5B2FA5PV8=nota-1 h_01H95QTA3Z3XJDM5YRXFK7DA0E=cost-tab enabling-and-testing-pinterest-integration=habilitar-y-probar-la-integraci%C3%B3n-de-pinterest h_01H95QTA3ZZ56R8EZBJY1ESX5W=habilitar-y-probar-la-integraci%C3%B3n-de-pinterest cost-data-sync-status=estado-de-sincronizaci%C3%B3n-de-datos-de-costos h_01H95QTA3ZST8WS3TAR79H06FM=estado-de-sincronizaci%C3%B3n-de-datos-de-costos stop-pinterest-cost-sync=detener-la-sincronizaci%C3%B3n-de-costos-de-pinterest h_01H95QTA3ZFCJ82E3YDMP7S716=detener-la-sincronizaci%C3%B3n-de-costos-de-pinterest h_01H95QTA3ZM2REWR2A5DHK1DSA=ad-revenue-tab h_01H95QTA3ZM4WPHV3MB00WZXSB=permissions-tab troubleshooting=resoluci%C3%B3n-de-problemas h_01H95QTA3ZP20DSJQGY4QQX0Z7=resoluci%C3%B3n-de-problemas" />
