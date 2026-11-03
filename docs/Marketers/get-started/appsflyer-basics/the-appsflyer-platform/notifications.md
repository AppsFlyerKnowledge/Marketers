---
title: Notificaciones
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2025-03-24T10:10:37Z'
  edited_at: '2026-08-12T11:58:08Z'
  id: 33732395637905
  locale: es
  section: The AppsFlyer platform
  section_id: 6551361489297
  url: https://support.appsflyer.com/hc/es/articles/33732395637905
---
> **En resumen:** Gestiona las notificaciones críticas de la cuenta de AppsFlyer desde la plataforma.

Puedes optar por recibir notificaciones por el correo electrónico de AppsFlyer cuando se produzcan ciertos eventos en tu cuenta. En tus **preferencias de notificación**, puedes optar por recibir o no recibir estas notificaciones.

## Accediendo y configurando las preferencias de notificación

### Para acceder a las notificaciones

* Desde la barra superior, abre el menú de la cuenta (menú desplegable de la dirección de correo electrónico) > Notificaciones
* Desde el ícono de la campana dentro de la plataforma > **Ícono de configuración.**

### Configuración de notificaciones

Para optar por recibir una notificación, actívalas de la lista de notificaciones disponibles.

Para dejar de recibirlos, debes desactivarlas.

Nota: Algunas notificaciones están disponibles solo por correo electrónico. La pestaña de notificación solo por correo electrónico contiene estas configuraciones de [notificaciones](/docs/notifications#notificaciones-solo-por-correo-electrónico).

## ¿Qué notificaciones puedo recibir?

Las siguientes categorías de notificación están disponibles:

* Gestión de cuentas y planes
* Problemas de facturación o transacciones
* Alertas relacionadas con la privacidad
* Insights y configuración
* Características de colaboración
* Capacidades de IA

Nota: Algunas notificaciones están disponibles solo por correo electrónico. Puedes encontrar más información [aquí](/docs/notifications#email-notification).

Para optar por una notificación en particular, debe:

* **Estar disponible en la cuenta de AppsFlyer de tu empresa.** Si no hay una notificación disponible en la cuenta de tu empresa, no se verá el botón para activarla.
  * Por ejemplo, si tu empresa no se suscribe a la función de Push API de AppsFlyer, el conmutador relacionado con esta función no será visible.
* **Disponible para ti, según tus permisos de usuario.** Si una notificación está relacionada con una capacidad o función a la que no se te han asignado permisos, el botón para activar y desactivar estará deshabilitado.
  * * Por ejemplo, si no tienes permisos para agregar o editar partners integrados, el botón para activar o desactivar una notificación relacionada con la configuración de partners integrados está deshabilitado.

## ¿Cuándo recibiré notificaciones?

Si has optado por recibir una notificación en particular, recibirás un correo electrónico cuando se produzca el evento desencadenante de esa notificación, pero **solo cuando** ese evento desencadenante sea aplicable a las **aplicaciones y fuentes de medios** para las que tengas permisos.

<div id="example" />

<Accordion title="Ejemplo">

Considera la siguiente situación:

* Tu empresa tiene 3 aplicaciones en AppsFlyer: Aplicación A, Aplicación B y Aplicación C.
* Cada aplicación tiene integraciones activas con 2 fuentes de medios (partners integrados): Google Ads y TikTok.
* Tu usuario de AppsFlyer tiene permisos para:
  * Agregar/editar partners integrados
  * Acceso a datos para la Aplicación C
  * Acceso a datos para Google Ads
* Has optado por recibir una notificación cuando haya cambios en las configuraciones de los partners integrados.

Resultado:

* **No** recibirás notificaciones cuando haya cambios en la configuración del partner integrado para las Aplicaciones A y B.
* **No** recibirás notificaciones cuando haya cambios en la configuración de TikTok para la Aplicación C.
* **Recibirás** notificaciones cuando haya cambios en la configuración de Google Ads para la Aplicación C.

</Accordion>

## ¿Cuándo recibiré notificaciones?

Las notificaciones se pueden recibir a través del icono de [campana](/docs/notifications#bell-notification), [correo electrónico](/docs/notifications#email-notification) o integración de [Slack](/docs/notifications#slack-notification).

<div id="bell-notification" />

<Accordion title="Notificación de campana">

El icono de notificación de la campana se puede encontrar en la barra superior a la izquierda de tu menú de cuenta (desplegable de dirección de correo electrónico).

Hacer clic en el ícono de engranaje te lleva a las [preferencias de notificación](/docs/notifications#accediendo-y-configurando-las-preferencias-de-notificación).

</Accordion>

<div id="email-notification" />

<Accordion title="Notificaciones por correo electrónico">

Las notificaciones se envían por correo electrónico a la dirección de correo electrónico asociada con tu cuenta de AppsFlyer.

Algunas notificaciones están disponibles solo por correo electrónico. Estos ajustes de notificación se pueden encontrar en la pestaña **Notificación solo por correo electrónico**.

> 📘 **Nota**
>
> Todos los correos electrónicos de notificación de AppsFlyer se envían desde [notifications@appsflyer.com](mailto:notifications@appsflyer.com)

#### Notificaciones solo por correo electrónico

La siguiente tabla enumera las notificaciones disponibles y los eventos que las activan:

| Notificación | Activar evento |
| --- | --- |
| Cambios en la configuración de partners integrados | <ul><li>Se activa un nuevo partner integrado</li><li>Un partner integrado existente se desactiva</li><li>Se realiza un cambio en la configuración de un partner integrado existente.</li></ul> |
| Errores de Push API | El 5% o más de los mensajes de la Push API de una aplicación fallan en un período de 12 horas |
| Errores de conexión de audiencias | Hay errores de conexión de partners de la audiencia que requieren tu atención |
| Integración de ingresos por publicidad suspendida | Una integración de ingresos por publicidad se suspende después de tener un estado de advertencia durante más de 30 días |
| Error en los datos de ingresos por publicidad | Una integración de ingresos por publicidad no recibe datos |
| Cambios en la configuración de costos de partners integrados | Un miembro del equipo cambia la configuración de integración de costos |
| Errores de conexión de SKAN | Hay un problema con tu integración de Google Ads o Meta SKAN con AppsFlyer que requiere tu atención. Es posible que tengas que eliminar la integración actual e iniciar sesión de nuevo. |

</Accordion>

<div id="slack-notification" />

<Accordion title="Notificaciones de Slack">

**Configurar notificaciones de Slack**

Para configurar las notificaciones de Slack, primero debes conectar Slack:

1. En la página de preferencias de notificación, haz clic en el botón **integraciones** en la parte superior derecha de la página.
2. Haz clic en **Conectar** mediante el conector de notificaciones de Slack.
3. Revisa y aprueba la solicitud de permisos.
   1. **Si eres el administrador de Slack**.
      1. En Slack, haz clic en el workspace de Slack.  
         <Image alt="" src="https://a.slack-edge.com/8e8e4/helpcenter/img/workspace-picker@2x.jpg" width="263px" />  
         Nota: Asegúrate de que el workspace de Slack que se muestra sea el correcto al que deseas conectarte.
      2. Ve a **Herramientas y configuraciones** -> **Administrar aplicaciones**
      3. En el **Panel de administración**, selecciona **Solicitudes**.
      4. En la pestaña **Necesita revisión**, haz clic en los tres puntos junto a la solicitud de la aplicación de AppsFlyer.
      5. Haz clic en **aprobar** y luego aprueba el siguiente pop-up.
      6. Regresa a la **página de integración de AppsFlyer** y haz clic en el botón **Permitir**.
   2. **Si no eres el administrador de Slack**.
      1. Solicita permiso a tu administrador de Slack para conectar Slack a AppsFlyer.
      2. El administrador de Slack **debe** realizar todos los pasos anteriores. Mientras tanto:
      3. El conector de Slack pasa a un estado pendiente.
      4. Cuando tu administrador de Slack apruebe la conexión, haz clic en **Conectar** para comenzar la integración y pasar de pendiente a conectado.

</Accordion>

<div data-zendesk-anchors="accessing-email-notifications=accediendo-y-configurando-las-preferencias-de-notificaci%C3%B3n h_01HKA254W4XDVNP816N46N59ZV=accediendo-y-configurando-las-preferencias-de-notificaci%C3%B3n to-access-notifications=para-acceder-a-las-notificaciones h_01JQ66J4YSCSX7ZGG81XHGJ3MM=para-acceder-a-las-notificaciones configuring-notifications=configuraci%C3%B3n-de-notificaciones h_01HKA254W497H0SKTZ33CVSA4P=configuraci%C3%B3n-de-notificaciones what-notifications-can-i-receive=qu%C3%A9-notificaciones-puedo-recibir h_01HKA254W47XRG1D3HZ6VBZ2BH=qu%C3%A9-notificaciones-puedo-recibir when-will-i-receive-notifications=cu%C3%A1ndo-recibir%C3%A9-notificaciones h_01JQ66BX52MV5WQ7RXH6SY3QHK=cu%C3%A1ndo-recibir%C3%A9-notificaciones h_01JQ6EYTZ13FHYERT48K3J25SV=example where-will-i-receive-notifications=cu%C3%A1ndo-recibir%C3%A9-notificaciones-1 h_01HKA254W4Z95M335V7KWAJA6N=cu%C3%A1ndo-recibir%C3%A9-notificaciones-1 h_01JQ667RAW19658DVMZNFXNAJK=bell-notification h_01JQ667RAWCAVYBZD3J0T8XH2G=email-notification h_01JJGTDQFM1WE9G3XWSN9S7Z02=nota emailonly-notifications=notificaciones-solo-por-correo-electr%C3%B3nico h_01JQ6EQR8JRBZ2ECJ7SHHWDWFC=notificaciones-solo-por-correo-electr%C3%B3nico h_01JQ667RAW48YQ64VXW899EW3X=slack-notification" />
