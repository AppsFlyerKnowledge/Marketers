---
title: Guía de integración de App Clips de Apple
metadata:
  keywords:
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2020-10-09T00:42:10Z'
  edited_at: '2026-08-12T12:01:57Z'
  id: 360014262358
  locale: es
  section: iOS platform
  section_id: 6551263106577
  url: https://support.appsflyer.com/hc/es/articles/360014262358
---
> **En resumen:** Los App Clips permiten a los usuarios con iOS 14 o posterior acceder y experimentar rápidamente tu aplicación. AppsFlyer permite la atribución de App Clips y redirige a los usuarios que no pueden usarlos (por ejemplo, los usuarios de Android) según sea necesario.

<Image align="center" alt="app_clip_flow_3.png" src="https://files.readme.io/1a5ec7a6b8a061955742d8e79ba78fa0262c0609e1e801decc92300d6c24a774-360012832058.png" />

<div id="app-clip-integration" />

## Integración de App Clips

* Los App Clips brindan a los usuarios de iOS 14 un acceso rápido y conveniente a una experiencia de aplicación, sin la necesidad de descargar la aplicación completa.
* Los App Clips se instalan y se inician desde una invocación (por ejemplo, un código QR o una etiqueta NFC). **Nota**: No se admiten banners y enlaces de aplicación inteligente Safari en mensajes.
* El SDK de AppsFlyer es necesario para la atribución a App Clips de clics, instalaciones, eventos in-app e instalaciones completas de aplicaciones desde App Clips.
* Independientemente del SDK, OneLink redirige a los usuarios según sea necesario:
  * Usuarios sin la aplicación instalada:
    * Con iOS 14 o posterior, se envían al App Clip.
    * Con iOS 13 o anterior, o Android, se redirigen según tu configuración en OneLink (a la tienda de aplicaciones, etc.).
  * Los usuarios con la aplicación instalada se envían a la aplicación según la configuración de enlaces universales o de aplicación en OneLink.

<div id="considerations" />

### Consideraciones

* Los App Clips pueden tener un tamaño de hasta 10 MB. El SDK de AppsFlyer ocupa aproximadamente 1,5 MB.
* No hay identificadores de publicidad disponibles.
* El sistema operativo elimina automáticamente los App Clips después de un período de inactividad de 30 días.

<div id="example" />

> 📄 **Ejemplo**
>
> Mark es el marketer de una cadena de cafeterías. Contrata a su desarrollador de iOS para crear un App Clip que permita a los clientes saltarse cómodamente la cola y realizar pedidos en segundos. Simplemente se identifican usando el <Anchor target="_blank" href="https://developer.apple.com/sign-in-with-apple/">inicio de sesión de Apple</Anchor>, piden su café y pagan con <Anchor target="_blank" href="https://developer.apple.com/apple-pay/">Apple Pay</Anchor>. El desarrollador agrega el SDK de AppsFlyer y se asegura de que funcione tanto en la aplicación como en el App Clip.
>
> Mark crea un OneLink y publica el código QR en la cafetería, junto con el eslogan "¡Evita las colas!".
>
> Los clientes escanean el código QR y:
>
> * Si tienen un dispositivo con iOS 14 o posterior, se abre el App Clip,con la sucursal de cafetería correcta y un cupón de descuento incluido.
> * Si ya tienen la aplicación completa instalada, la aplicación se abre en la página de pedido de café.
> * Si no tienen la aplicación y disponen de un dispositivo con iOS 13 o anterior, o Android, se abre la página de la tienda de aplicaciones de la aplicación de la cafetería.
>
> Mark usa el panel de control y los reportes de AppsFlyer para ver cuántos clics e instalaciones recibe el App Clip, y cuántos usuarios descargan finalmente la aplicación completa.

<div id="metrics-and-reporting" />

## Métricas y reportes

Los datos analíticos y el raw data de los App Clips están disponibles en la plataforma en función de la actividad del usuario que se describe en la siguiente tabla.

| Acción del usuario | Evento de AppsFlyer | Panel de control general y herramientas analíticas | Datos sin procesar |
| --- | --- | --- | --- |
| Invocación (p. ej.: código QR) | Sin evento | Sin evento | Sin evento |
| Hace clic en la tarjeta de la aplicación y se abre el App Clip | El clic y la instalación se atribuyen a la fuente de invocación | <ul><li>Clics</li><li>Instalaciones</li></ul> | <Anchor target="_blank" href="/marketers/es/docs/raw-data-field-dictionary#app::5a1697f1">app\_type=app\_clip</Anchor> |
| Utiliza el App Clip | <ul><li>[Opcional] El desarrollador envía un evento in-app</li><li>Después de la primera apertura del App Clip, las aperturas posteriores se cuentan como sesiones.</li></ul> | <ul><li>Evento in-app</li><li>Sesión</li></ul> | <ul><li>Evento in-app enviado por el desarrollador</li><li><Anchor target="_blank" href="/marketers/es/docs/raw-data-field-dictionary#app::5a1697f1">app\_type=app\_clip</Anchor></li></ul> |
| Descarga y ejecuta la aplicación completa | Evento in-app | Nombre del evento in-app = af\_app\_clip\_to\_full\_app | <ul><li>Nombre del evento in-app = af\_app\_clip\_to\_full\_app</li><li><Anchor target="_blank" href="/marketers/es/docs/raw-data-field-dictionary#app::5a1697f1">app\_type=full\_app</Anchor></li></ul> |
| Uso continuo de la aplicación completa | [Opcional] El desarrollador envía un evento in-app | Evento in-app | <ul><li>Evento in-app enviado por el desarrollador</li><li><Anchor target="_blank" href="/marketers/es/docs/raw-data-field-dictionary#app::5a1697f1">app\_type=full\_app</Anchor></li></ul> |

**Panel de control de cohorte**

Consulta el rendimiento de los App Clips en el <Anchor target="_blank" href="/marketers/es/docs/cohort-and-retention-dashboard#trend-type%E2%80%94user-lifetime-performance">panel de control de cohorte</Anchor>, donde puedes:

* Consulta cuánto tiempo les lleva a los usuarios pasar del App Clip a la instalación completa de la aplicación.
* Utiliza la métrica de conversión in-app para comparar el rendimiento de diferentes campañas de invocación.

<div id="app-clip-implementation" />

## Implementación de App Clips

El siguiente procedimiento detalla lo que tú y el desarrollador de iOS deben hacer para desarrollar e integrar App Clips.

<div id="scope-of-work" />

#### Alcance del trabajo

| **¿Quién está involucrado?**<ul><li>**Anunciante**:<ul><li>Configura los App Clips de Apple en plantillas de OneLink.</li><li>Coloca los enlaces de OneLink en el portal Apple App Store Connect.</li><li>Visualiza las métricas en el panel de control y los reportes de AppsFlyer.</li></ul></li><li>**Desarrollador de iOS**:<ul><li>Crea el App Clip.</li><li>Integra el SDK de AppsFlyer en App Clip.</li></ul></li></ul> |
| --- |
| **Requisitos previos**<ul><li>Una cuenta de AppsFlyer con una aplicación como mínimo.</li><li>Una plantilla de OneLink con enlaces universales y un enlace de OneLink configurado para dirigir a los usuarios a tu aplicación completa.<br />**Recomendación**: La plantilla y la invocación del enlace que utilizas para el App Clip envían a todos los usuarios sin tu aplicación completa al App Clip. Por lo tanto, considera tener una plantilla y un enlace personalizado independientes para los casos en los que desees enviar a esos usuarios al App Store, en lugar del App Clip.</li></ul> |

<div id="develop-app-clip" />

<Accordion title="Desarrollo de App Clips">

Para obtener instrucciones completas sobre cómo los desarrolladores crean un App Clip para tu aplicación, consulta la <Anchor target="_blank" href="https://developer.apple.com/app-clips/">guía de App Clips de Apple para desarrolladores</Anchor>.

Para obtener una aplicación de muestra simplificada que demuestra el uso de los App Clips y su integración con una aplicación completa, consulta la <Anchor target="_blank" href="https://www.appsflyer.com/resources/others/apple-app-clips/">guía de App Clips de AppsFlyer</Anchor>.

</Accordion>

<div id="integrate-sdk" />

<Accordion title="Integración del SDK">

* El SDK es necesario para la atribución de AppsFlyer de clics, instalaciones, eventos in-app e instalaciones completas de aplicaciones desde App Clips.
* OneLink redirige a los usuarios independientemente de la integración del SDK.

**Para instalar el SDK y configurar el SDK de la aplicación completa**:

Envía los siguientes enlaces a tu desarrollador de iOS y dile que siga las instrucciones para:

* <Anchor target="_blank" href="https://dev.appsflyer.com/docs/app-clip-sdk-integration">Integración del SDK en el App Clip</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/docs/app-clip-to-full-app-install">Configuración de la atribución de la instalación completa de la aplicación desde el App Clip</Anchor>
* [Opcional] <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events">Configuración de eventos in-app</Anchor>, si aún no tiene eventos in-app que se midan para tu aplicación completa, o si deseas usar diferentes eventos in-app para el App Clip.

</Accordion>

<div id="configure-onelink" />

<Accordion title="Configuración de OneLink">

**Requisitos previos**:

* <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#crear-una-plantilla-de-onelink">Plantilla de OneLink</Anchor> para tu aplicación completa con enlaces universales de iOS configurados.
* <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#crear-un-enlace-de-onelink">Enlace de OneLink</Anchor>.
* **Recomendación**: La plantilla y la invocación del enlace que utilizas para el App Clip envían a todos los usuarios sin tu aplicación completa al App Clip. Por lo tanto, considera tener una plantilla y un enlace personalizado independientes para los casos en los que desees enviar a esos usuarios al App Store, en lugar del App Clip.

**Para configurar la plantilla de OneLink para tu App Clip**:

1. En el panel de control de AppsFlyer, ve a **Captación** > **Administración de OneLink**.
2. Selecciona la **plantilla de OneLink** que utilizas para dirigir a los usuarios a tu aplicación completa.
3. Asegúrate de que la plantilla de OneLink tenga enlaces universales configurados. (Consulta las <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">instrucciones</Anchor> para agregar enlaces universales).
4. Haz clic en **Guardar**.  
   El archivo AASA se actualiza para admitir el App Clip.
5. En el panel de control de AppsFlyer, ve a **Captación** > **Administración de OneLink**.
6. Selecciona el**enlace personalizado de OneLink** basado en la plantilla que configuraste en los pasos 1 a 4, que utilizas para dirigir a los usuarios a tu App Clip.
7. Asegúrate de tener una fuente de medios (pid) especificada.  
   La fuente de medios debe especificarse en la URL (por ejemplo: **pid=chartboost\_int**) o estar incluida dentro del enlace.

**Para verificar que los App Clips estén habilitados en OneLink de AppsFlyer:**

1. Crea una URL para obtener tu archivo de asociación. La URL se crea tomando el dominio de tu plantilla de OneLink y agregando `/.well-known/apple-app-site-association`.   
   Por ejemplo: `coffee.onelink.me/.well-known/apple-app-site-association`.
2. Ve a la URL de tu archivo de asociación.  
   El archivo apple-app-site-association se descarga automáticamente.
3. Abre el archivo apple-app-site-association con un editor de texto (por ejemplo, el Bloc de notas).
4. Asegúrate de que el archivo contenga la palabra "**appclips**" y que el ID del paquete termine con "**.Clip**". y que el ID del paquete termine en "**.Clip**". Por ejemplo:  

   ```java
   "appclips": {\n    "apps": [\n      "ABCD1234.id.your.app.Clip",\n      ...
       ]\n...
   }
   ```

   Si es así, habrás configurado correctamente los App Clips en AppsFlyer y el App Clip estará implementado en cualquier plantilla de OneLink con el mismo subdominio.

</Accordion>

<div id="configure-app-store-connect" />

<Accordion title="Configuración de App Store Connect">

**Requisitos previos**: Finalización de la [configuración de la plantilla de OneLink para App Clips](/docs/apple-app-clips-integration-guide#configure-onelink)

**Para configurar tu App Clip para que funcione con OneLink**:

1. En la página de tu aplicación en App Store Connect, ve a **Build** (Compilar) > **Domain Status** (Estado de dominio).
2. Asegúrate de que tu dominio de OneLink aparezca en **Build domains** (Compilar dominios) y que **Cache status** (Estado de caché) y **Debug status** (Estado de depuración) estén "validados".
3. En el panel de control de AppsFlyer, ve a **Captación** > **Administración de OneLink**.
4. Coloca el cursor sobre el ícono **Acciones** del enlace que deseas utilizar y haz clic en**Obtener URL**.
5. Registre la URL corta (o el prefijo de la URL larga).
6. En la página de tu aplicación en App Store Connect, ve a **App Clip** > **Edit Advanced Experiences** (Editar experiencias avanzadas) > **+Add** (Agregar) > **Next** (Siguiente).
7. En **App Clip Experience URL** (URL de experiencia de App Clip), pega la URL personalizada de OneLink que registraste en el paso 5.  
   **Nota**: Puedes agregar parámetros de consulta después de la URL personalizada principal, pero no puedes cambiar la ruta.
8. Haz clic en **Next** (Siguiente).  
   Tu App Clip ahora está configurado para funcionar con OneLink. Puedes encontrar más instrucciones sobre la configuración de App Store Connect en la <Anchor target="_blank" href="https://developer.apple.com/documentation/app_clips/configuring_your_app_clip_s_launch_experience">guía para desarrolladores de Apple</Anchor>.

</Accordion>

<div id="testing" />

<Accordion title="Pruebas">

**Requisitos previos**: Un <Anchor target="_blank" href="/marketers/es/docs/registering-test-devices">dispositivo de prueba registrado</Anchor> con iOS 14 sin la aplicación completa instalada.

**Para probar la integración de OneLink/App Clip:**

1. En el panel de control de AppsFlyer, ve a**Captación** > **Administración de OneLink**.
2. Desplaza el puntero sobre el icono **Acciones** del enlace que quieres probar y haz clic en **Obtener URL**.
3. Escanea el código QR con tu dispositivo.  
   La tarjeta del App Clip se muestra en tu dispositivo, lo que indica que tu integración de OneLink/App Clip está configurada correctamente.

</Accordion>

<div id="traits-and-limitations" />

## Características y limitaciones

<div id="traits-and-limitations::26141033" />

<Accordion title="Características y limitaciones">

| Característica/limitación | Descripción |
| --- | --- |
| Métodos de invocación | <ul><li>Se admiten códigos QR y etiquetas NFC.</li><li>No se admiten banners y enlaces de aplicación inteligente Safari en mensajes.</li></ul> |
| SKAdNetwork | La funcionalidad SKAdNetwork no está disponible. Por lo tanto, las instalaciones de App Clips se muestran en el panel de control de SKAdNetwork como orgánicas. |
| OneLink | Solo se permite una experiencia avanzada de App Clip por cada enlace personalizado de OneLink. Esto significa que no puedes agregar rutas adicionales a OneLink en App Store Connect. |
| Las alertas de Protect360 se actualizan a la hora UTC diaria. | Protect360 no es compatible con App Clips. |

</Accordion>

<div id="see-also" />

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="https://www.appsflyer.com/resources/guides/ios-14-app-clips/">Solución de atribución de AppsFlyer para App Clips de Apple</Anchor>

<div data-zendesk-anchors="app-clip-integration=integraci%C3%B3n-de-app-clips h_01HDNZQTCBXY0Y3QYCBNVH7EAW=integraci%C3%B3n-de-app-clips considerations=consideraciones h_01HDNZQTCBPJWY6H2M452QH644=consideraciones h_01HDNZQTCB7NB682YTSMNCJSDP=ejemplo metrics-and-reporting=m%C3%A9tricas-y-reportes h_01HDNZQTCBNG3TYRAA7GVPF39P=m%C3%A9tricas-y-reportes app-clip-implementation=implementaci%C3%B3n-de-app-clips h_01HDNZQTCBJK7SB96G8A4DHR34=implementaci%C3%B3n-de-app-clips scope-of-work=alcance-del-trabajo h_01HDNZQTCB1AKW9QFRRM9VVN4D=alcance-del-trabajo h_01HDNZQTCBN04J3GA8H64V70YY=develop-app-clip h_01HDNZQTCBHHENFYJK7MFJTZ14=integrate-sdk h_01HDNZQTCBN9QV4MZAAWMV164Y=configure-onelink h_01HDNZQTCC6F8TTM2FRQK6DB2E=configure-app-store-connect h_01HDNZQTCCN2BX9NZ4027ZCEFB=testing traits-and-limitations=caracter%C3%ADsticas-y-limitaciones h_01HDNZQTCCMW2YNK1G34EBM7DM=caracter%C3%ADsticas-y-limitaciones h_01HDNZQTCCV0S78NRK00PK4S0J=traits-and-limitations::26141033 h_01HDNZS83EKJNZGG1QEVS9RMCA=consulta-tambi%C3%A9n" />
