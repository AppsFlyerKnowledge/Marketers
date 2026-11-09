---
title: Guía de integración del SDK web para la PBA
metadata:
  keywords:
    - Developers
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2019-05-17T09:05:30Z'
  edited_at: '2026-08-22T00:22:54Z'
  id: 360001610038
  locale: es
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/es/articles/360001610038
---
> **At a glance:** Integra AppsFlyer en sitios web utilizando el SDK web para atribuir y medir visitas, eventos, conversiones e ingresos.

<Image align="center" alt="5107_Infographic_Web_S2S_759x270_option1.jpg" src="https://files.readme.io/11ea958806271989fc6d01a1588762c0ae7313636968d5b878131a4b07d8eaf5-360007722397.jpg" />

<div id="web-sdk-user-and-integration-guide" />

## Guía de integración y del usuario del SDK web

* La etiqueta JavaScript del SDK web:
  * forma parte de la solución de atribución basada en las personas (PBA) para analizar las trayectorias de los usuarios en múltiples plataformas.
  * reporta las visitas y las acciones de los usuarios en tu sitio web a la plataforma de AppsFlyer.
  * es un módulo de pluginpara el sitio webque no requiereprogramación. Es independiente del sistema operativo y del navegador del visitante del sitio web.
  * Tamaño: 40-60 Kb.
* Implementa el SDK web junto con el SDK móvil de AppsFlyer para registrar y asignar la actividad del usuario en tu aplicación móvil y tus entornos web.
* Los eventos que ocurren fuera del sitio web se pueden registrar mediante la <Anchor target="_blank" href="/marketers/es/docs/web-server-to-server-events-api-for-pba-web-s2s">API de eventos web server-to-server</Anchor> (Web S2S).

<div id="selecting-a-code-snippet" />

## Selección de un fragmento de código

Elige el fragmento que mejor se adapte a tu tipo de integración y a los requisitos de seguridad. Las siguientes opciones están disponibles:

* [Standard Web SDK](#standard-web-sdk): La integración estándar.
* [Advanced SDK Verification](#advanced-sdk-verification): Una integración mejorada que agrega protección a la cadena de suministro para el SDK web. Usa esto para agregar una capa adicional de seguridad contra el compromiso de CDN, el DNS hijacking y los ataques de intermediarios.

> 🚧 **Important**
>
> **¡Importante!**
>
> Si estás haciendo la transición del Standard Web SDK al Advanced SDK Verification, reemplaza tu fragmento existente con el nuevo. No agregues el fragmento nuevo además del existente.

### Standard Web SDK

Usa este fragmento para implementar la integración estándar del SDK web. Pégalo cerca de la parte superior de la etiqueta  en todas las páginas donde quieras cargar el SDK.

<div id="standard-without-smart-banners" />

<Accordion title="Sin Smart Banners">

```html
<html>
<head>
    <!-- The Web SDK script loads first -->
    <script>
!function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){
(t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
t. AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
o.src="https://websdk.appsflyersdk.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "WEB_DEV_KEY"}})
    </script>
    <script>
        };
    // This function stores the user email sent to the server after the user reaches the thank you page
    // The response from the server is a unique CUID that should be set using the web SDK setCustomerUserId method
        function storeUserEmail (){
            var userEmail = document.getElementById('email').value;
            localStorage.setItem('user_email', userEmail);
        }
    </script>
</head>
<body>
    <h1>Sign Up</h1>
    <form onsubmit="storeUserEmail()" action="/signup" method="post">
        <div><label>Name</label>
            <input type="text" name="name" id="name"></div>
        <br />
        <div> <label>Email</label>
            <input type="email" name="email" id="email"></div>
        <br />
        <input type="submit" id="submit">
    </form>
</body>
</html>
```

</Accordion>

<div id="standard-with-smart-banners" />

<Accordion title="Con Smart Banners">

```html
<html>
<head>
    <script>
!function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){
(t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
t. AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
o.src="https://websdk.appsflyersdk.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "WEB_DEV_KEY"}})
    </script>
    <script>
        // Using the fetch API to send the user email to the server
        // and get the unique user id in return	
        window.onload = function () {
            var userEmail = localStorage.getItem('user_email');
            fetch('users/' + userEmail).then(function (res) {
                   res.text().then(function (id) {
                    console.log(id);
                    AF('pba', 'setCustomerUserId', id);
                });
            });
        }  </script> 
     </head> 
     <body> 
        <h1>Thank You for Signing Up!</h1> 
     </body> 
</html>
```

</Accordion>

### Advanced SDK Verification

Advanced SDK Verification agrega protección a la cadena de suministro para el SDK web. Garantiza que el código que se ejecuta en los navegadores de tus usuarios sea exactamente el que publicó AppsFlyer. El código fuente del SDK en sí es idéntico a la integración estándar; solo difieren los mecanismos de entrega y verificación.

Advanced SDK Verification:

* Agrega una capa adicional de seguridad contra compromisos de CDN, DNS hijacking y ataques de intermediarios.
* Agrega aproximadamente 250 ms al tiempo de carga del SDK.

Advanced SDK Verification es opcional. La integración estándar sigue siendo totalmente compatible y es el estándar del mercado para los píxeles de análisis de terceros. Advanced SDK Verification proporciona una capa adicional de protección más allá de ese estándar.

Si tu sitio web aplica una Política de Seguridad de Contenido (CSP) mediante una nonce, consulta [Política de Seguridad de Contenido (CSP)](#política-de-seguridad-de-contenido-csp) en la sección “Gestionar privacidad” para ver la variante extendida de este fragmento.

<Accordion title="Sin Smart Banners">

```html
<script>
  // Queue — buffers AF() calls until the SDK is ready
  window. AppsFlyerSdkObject = "AF";
  window. AF = window. AF || function() {
    (window.AF.q = window. AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  window. AF.id = window. AF.id || { pba: { webAppId: "WEB_DEV_KEY" } };
  window. AF.plugins = {};

  // Manifest loader config
  window. AF_LOADER_CONFIG = {
    baseUrl: "https://websdk.appsflyersdk.com",
    plugins: ["pba"]
  };

  // Inject manifest loader
  var loaderScript = document.createElement("script");
  loaderScript.src = "https://websdk.appsflyersdk.com/manifestLoader.v1.js";
  loaderScript.integrity = "sha384-Uncl2YwvjFpFz0PwEfl3bL/0JsOQcDFEpwXHzcN0MBavn9vvFEx5pZxADTq8h+CV";
  loaderScript.crossOrigin = "anonymous";
  loaderScript.async = true;
  document.head.appendChild(loaderScript);
</script>
```

</Accordion>

<Accordion title="Con Smart Banners">

```html
<script>
  // Queue — buffers AF() calls until the SDK is ready
  window. AppsFlyerSdkObject = "AF";
  window. AF = window. AF || function() {
    (window.AF.q = window. AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  window. AF.id = window. AF.id || { pba: { webAppId: "WEB_DEV_KEY" }, banners: { key: "YOUR_BANNER_KEY" } };
  window. AF.plugins = {};

  // Manifest loader config
  window. AF_LOADER_CONFIG = {
    baseUrl: "https://websdk.appsflyersdk.com",
    plugins: ["banners", "pba"]
  };

  // Inject manifest loader
  var loaderScript = document.createElement("script");
  loaderScript.src = "https://websdk.appsflyersdk.com/manifestLoader.v1.js";
  loaderScript.integrity = "sha384-Uncl2YwvjFpFz0PwEfl3bL/0JsOQcDFEpwXHzcN0MBavn9vvFEx5pZxADTq8h+CV";
  loaderScript.crossOrigin = "anonymous";
  loaderScript.async = true;
  document.head.appendChild(loaderScript);
</script>
```

</Accordion>

<div id="integrating-the-web-sdk-into-the-website" />

## Integración del SDK web en el sitio web

<div id="installation-and-integration" />

<Accordion title="Instalación e integración">

<div id="considerations-and-actions-required" />

#### Consideraciones y acciones requeridas

| Lista de verificación de la integración |
| --- |
| Para garantizar que se registren las visitas y los eventos, el SDK web debe instalarse en todas las páginas del sitio web. |
| Coloca el fragmento de código [que has seleccionado anteriormente](#selección-de-un-fragmento-de-código) para que se cargue lo antes posible dentro del alcance de la página. Para ello, inserta el código cerca de la parte superior de la etiqueta de encabezado. |
| Si vas a integrar el SDK mediante Google Tag Manager (GTM):<ul><li>Asegúrate de que el SDK se cargue una vez por cada carga de la página.</li><li>Configura el SDK para que se cargue tan pronto como se cargue la página mediante la <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/2772421?hl=en">priorización GTM</Anchor>.</li></ul> |
| Puedes implementar el SDK web **con** o **sin** Smart Banners. Sigue las instrucciones pertinentes en las secciones que se indican a continuación. |
| Requisitos obligatorios para la integración<ul><li>Registro de visitas</li><li>Registro de eventos</li><li>Configuración del [<mark>Customer User ID</mark>](/docs/pba-web-sdk-integration-guide#identifying-users-using-customer-user-id-cuid) <mark>(CUID)</mark>: Si no tienes un CUID, contacta con tu CSM para analizar las alternativas.</li></ul>Valida la integración mediante la <Anchor target="_blank" href="/marketers/es/docs/test-pba-web-sdk-integration">herramienta de prueba</Anchor>. |

**Antes de empezar**:

* Verifica con el marketer que haya creado el <Anchor target="_blank" href="/marketers/es/docs/pba-brand-bundles-and-settings">paquete de marca</Anchor>.
* Para obtener orientación adicional, consulta la <Anchor target="_blank" href="/marketers/es/docs/onboarding-guide-to-people-based-attribution">Guía de onboarding de PBA</Anchor>.
* Consideración: Si ya tienes el SDK web independiente de Smart Banners, elimínalo y reemplázalo con el SDK web tanto para los Smart Banners como para la atribución people-based; no agregues solo el SDK web independiente para PBA.

**Haz lo siguiente:**

* Obtén la clave de desarrollador web del SDK web. **¡Nota!** Esta no es la misma clave que utilizan las aplicaciones móviles.
  * **Para obtener la clave de desarrollador web:**
    1. En AppsFlyer, en el menú superior, selecciona la pestaña **Mis aplicaciones**.
    2. Haz clic en **Ver paquetes de marca**.
    3. Copia la **clave de desarrollador web requerida. (WEB\_DEV\_KEY)**
* Si implementas Smart Banners, obtén la clave del Smart Banner.
  * **Para obtener la clave del Smart Banner:**
    1. En AppsFlyer, desde el menú lateral, ve a **Engage** > **Web-to-App** > **Smart Banners.**
    2. Copia la **clave del Smart Banner** requerida.
* Obtén los permisos para agregar scripts a etiquetas de encabezado en el sitio web.
* Si utilizas Google Tag Manager, deberá estar integrado en el sitio web.

**A continuación, integra el SDK web utilizando una de las siguientes opciones.**

<Tabs>
<Tab title="Nativo">

<div id="javascript-code-snippet" />

#### Fragmento de código JavaScript

Integra el SDK web utilizando uno de los siguientes métodos.

<div id="to-install-the-web-sdk-without-smart-banners" />

#### **Para instalar el SDK web sin Smart Banners:**

1. Repite el procedimiento que sigue en todas las páginas de tu sitio web.
2. En el fragmento de código que se indica a continuación, reemplaza `WEB_DEV_KEY` con la clave especificada en los requisitos previos.
3. Pega el fragmento de código [que has seleccionado anteriormente](#selección-de-un-fragmento-de-código) en la etiqueta de encabezado de tu sitio web. Pégalo cerca de la parte superior de la etiqueta de encabezado.

<div id="to-implement-the-web-sdk-with-smart-banners" />

#### **Para implementar el SDK web con Smart Banners:**

1. Repite el procedimiento a continuación en todas las páginas de tu sitio web.
2. En el fragmento de código [que has seleccionado anteriormente](#selección-de-un-fragmento-de-código), reemplaza `WEB_DEV_KEY` y `YOUR_BANNER_KEY` con las claves especificadas en los requisitos previos.
3. Pega este fragmento de código en la etiqueta de encabezado del sitio web. Pégalo cerca de la parte superior de la etiqueta de encabezado.

</Tab>

<Tab title="Google Tag Manager">

**Para implementar el SDK web con Google Tag Manager (GTM):**

1. <Anchor target="_blank" href="https://developers.google.com/tag-manager/quickstart">Ve a Google Tag Manager.</Anchor>
2. Crea una nueva etiqueta para el SDK web de AppsFlyer.

   <Image align="center" alt="Crea una nueva etiqueta para el SDK web de AppsFlyer en Google Tag Manager" src="https://files.readme.io/bd695bcbaf3983aac809cb7e1d63af0b89a08cea1751bbd8c2fc39863182fe7a-360002745245.png" />
3. Selecciona **HTML personalizado** el tipo de etiqueta.
4. Asigna un nombre descriptivo a la etiqueta.
5. Realice una de las siguientes acciones:
   * Si vas a integrar el SDK web **sin** Smart Banners:
     1. Pega el fragmento de código [que seleccionaste arriba](#selección-de-un-fragmento-de-código) en la ventana **Configuración de etiquetas**.
     2. En el fragmento de código, sustituye `WEB_DEV_KEY` por la clave mencionada en los requisitos previos.
   * Si vas a integrar el SDK web **con** Smart Banners:
     1. Pega el fragmento de código [que seleccionaste arriba](#selección-de-un-fragmento-de-código) en la ventana **Configuración de etiquetas**.
     2. En el fragmento de código, sustituye el `WEB_DEV_KEY` y `YOUR_BANNER_KEY` usando las claves mencionadas en los requisitos previos.
6. Haz clic en **Guardar**.
7. Realice una de las siguientes acciones:
   * **Para agregar el activador a todas las páginas:**
     1. Haz clic en **Agregar activador**.

        <Image align="center" alt="gtm-af-tag-sdk-trigger.png" src="https://files.readme.io/9cae70cdc376e57d3458fab80f8b9e57aa6981a3f3029c17d32e96b5f569fc28-360007722757.png" />
     2. Selecciona **Todas las páginas**.
     3. Haz clic en **Guardar**.
     4. Escribe un nombre de etiqueta y haz clic en **Guardar**.  
        Has completado el procedimiento.
   * **Para agregar el activador a páginas específicas:**
     1. Haz clic en **Guardar etiqueta**.
     2. En la ventana principal de GTM, selecciona **Activadores.** Haz clic en **Nuevo**.
     3. Haz clic en el icono de lápiz.
     4. Elige el tipo de activador **Vista de página**.  
        <Image align="center" alt="PBAselectTrigger_us-en.jpg" src="https://files.readme.io/e62926fed956da9f3fcbf04f818858c69f07cbac892fafd839451c73d72a6741-360007811677.jpg" />
     5. Selecciona **Algunas vistas de página**.
     6. Configura la página y las condiciones de activación según sea necesario.
     7. Haz clic en **Guardar**.
     8. Asocia el activador a la etiqueta AppsFlyer Web SDK. Para ello:
        1. En la ventana principal de GTM, selecciona Activadores.
        2. Selecciona la etiqueta que creaste anteriormente.
        3. En el panel de activación, haz clic en el lápiz.
        4. Seleccione el activador de vista de página que creaste anteriormente.

           <Image align="center" alt="Selecciona el activador de vista de página que creaste antes en Google Tag Manager" src="https://files.readme.io/c4e9b2e4b4d3ce6b7377d419070be650e758eddcdf5603fa5f3c65560402f1d7-360002745305.png" />
        5. Haz clic en **Guardar**.

</Tab>

<Tab title="Adobe Launch Tag Manager">

1. [Crear una propiedad en Adobe Experience Cloud](/docs/pba-web-sdk-integration-guide#create-a-property-in-adobe-experience-cloud)
2. [Agregar el SDK web a la propiedad de Adobe Launch](/docs/pba-web-sdk-integration-guide#add-the-web-sdk-to-the-adobe-launch-property)
3. [Agregar la etiqueta de Adobe Launch al sitio web](/docs/pba-web-sdk-integration-guide#add-the-adobe-launch-tag-to-the-website)
4. [Publicar el entorno de Adobe Launch](/docs/pba-web-sdk-integration-guide#publish-the-adobe-launch-environment)

<div id="create-a-property-in-adobe-experience-cloud" />

<Accordion title="Crear una propiedad en Adobe Experience Cloud">

<Image align="center" alt="adobe_create_property.png" src="https://files.readme.io/1f97d619d5fdfe47b1dd1a2e17c0169e939c32bcda62580ba259d6e86f61d6c2-20260884824209.png" />

1. Ve a **Adobe Experience Cloud** > **Lanzar**.
2. En **Adobe Experience Cloud Launch**, haz clic en **Ir al lanzamiento**.
3. Haz clic en **Nueva propiedad**.
4. Dale un nombre a la propiedad.
5. En **Plataforma**, selecciona **Web**.
6. Ingresa el dominio de tu sitio web.
7. Haz clic en **Guardar**.

</Accordion>

<div id="add-the-web-sdk-to-the-adobe-launch-property" />

<Accordion title="Agregar el SDK web a la propiedad de Adobe Launch">

<Image align="center" alt="web_property_rules.png" src="https://files.readme.io/5f592f3ce1f5b319c8f6f96a6235618d884a4faccb1387b1f22c1fd2ce662d15-360006168098.png" width="491px" />

1. En la página **Mi sitio web**, selecciona la pestaña **Reglas**.
2. Dale un nombre a la regla. Se recomienda el uso de **Cargar SDK web**.
3. En la sección **SÍ**, en **EVENTOS**, haz clic en **+Agregar**.
   * En **Tipo de evento**, selecciona **Core - DOM Ready**.
   * Haz clic en **Mantener cambios**.
4. En la sección **ENTONCES**, en **Acciones**, haz clic en **+Agregar**.
   * En **Tipo de activación** > **Código personalizado**.
   * Selecciona **JavaScript** > **Abrir editor** y pega el fragmento de código del SDK web **sin las etiquetas &lt;script>**.
   * Haz clic en **Mantener cambios** para cerrar el editor de códigos.
5. Haz clic en **Guardar**.

</Accordion>

<div id="add-the-adobe-launch-tag-to-the-website" />

<Accordion title="Agregar la etiqueta de Adobe Launch al sitio web">

<Image align="center" alt="adobe_tag.png" src="https://files.readme.io/4da5418fc3f2591d15fe68ea1d0451f2b393cb177ae4309d5d431259e2d4003f-small-20260884828049.png" />

1. En la página **My sitio web**, selecciona la pestaña **Entornos**.
2. Busca la fila con el entorno que deseas publicar (desarrollo o producción).
   * En el encabezado **INSTALACIÓN**, haz clic en el ícono de la caja en la fila correspondiente; normalmente se trata de un entorno de producción.
   * Consulta la sección sobre la publicación del entorno **Adobe Launch**.
3. En el cuadro **Instrucciones de instalación web**:
   * Copia el fragmento de código del script.
   * Cierra el cuadro de diálogo.
4. Pega el fragmento de código en la etiqueta &lt;head> de tu sitio web.

</Accordion>

<div id="publish-the-adobe-launch-environment" />

<Accordion title="Publicar el entorno de Adobe Launch">

<Image align="center" alt="adobe_publishing_env.png" src="https://files.readme.io/863b7c81a9f90d774f7f4388a22db3420dca5c5db632efc6c0dc40783702f418-small-20260884829329.png" />

1. En la página **Mi sitio web**, ve a la pestaña **Publicación**.
2. En la sección **Desarrollo**, haz clic en **Agregar biblioteca nueva**.
   * Asigna un nombre a la biblioteca y elige un entorno.
   * En **CAMBIOS DE RECURSOS**, haz clic en **Agregar un recurso**.
   * Haz clic en **Reglas** > **Cargar SDK web** > **Más reciente** > **Seleccionar y crear una nueva revisión**.
   * Haz clic en **Guardar**.
3. En la sección **Desarrollo**:
   * Junto a la biblioteca recién creada, haz clic en el menú de acciones (3 puntos) y selecciona **Crear para desarrollo**.
   * Haz clic de nuevo en el menú de acciones y selecciona **Enviar para aprobación**.
4. En la sección **Enviado**:
   * Haz clic en el menú de acciones y selecciona **Crear para escenario**.
   * Haz clic de nuevo en el menú de acciones y selecciona **Aprobar para publicar**.
5. En la sección **Aprobado**:
   * Haz clic en el menú de acciones > selecciona **Crear y publicar para producción**.
   * El proceso ya está completo.

</Accordion>

Cuando el sitio web se carga en un dispositivo móvil, la creatividad activa se muestra en el banner. Para mostrar el banner en páginas específicas o según las acciones del usuario, consulta las <Anchor target="_blank" href="https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/rules.html">Reglas de Adobe Launch</Anchor>.

</Tab>
</Tabs>

</Accordion>

<div id="ensure-that-the-sdk-is-working" />

<Accordion title="Comprobar que el SDK esté funcionando">

Una vez instalado, comprueba que el navegador del visitante llame al SDK web de AppsFlyer y que se envíen mensajes. Esto se hace examinando la conexión de red de mensajes reportada en el navegador.

**Para comprobar que el SDK se carga y funciona:**

1. Ve al sitio web.
2. Abre las herramientas para desarrolladores del navegador.

   <Image align="center" alt="WebSDK_us-en.jpg" src="https://files.readme.io/5550f0ee8c1a5852a983e6482cb0489696b669ffe5fade49d2308ee32f57201b-360009548497.jpg" />
3. Ve a la pestaña (A) **Red**.
4. Actualiza la página.
5. Filtra por (B) **wa.appsflyer**.
6. Selecciona el mensaje de **eventos** (C).
7. En la pestaña Encabezados (D), asegúrate de que:
   * La **URL de solicitud** es wa.appsflyer.com/events.
   * site\_id query parameter= `WEB_DEV_KEY`.
   * (E) El **estado del código es 200**.
8. Verifica que el valor de site\_id sea igual al valor de `WEB_DEV_KEY` en la configuración del paquete de marca:
   1. En AppsFlyer, en el menú lateral, selecciona **Configuración** > **Paquetes de marca**.
   2. Haz clic en la **Clave de desarrollador web**; al hacerlo, se copia la clave.
   3. Pega la clave en cualquier ubicación (nueva pestaña del navegador, bloc de notas) para mostrar la clave.
   4. Verifica que el site\_id y `WEB_DEV_KEY` coincidan.
9. Asegúrate de que el SDK se cargue solo una vez. La carga múltiple del SDK puede hacer que el SDK deje de funcionar.

</Accordion>

<div id="sending-events-optinoptout" />

<Accordion title="Aceptación/exclusión voluntaria del envío de eventos">

<Image align="center" alt="5578-VistiorPrivacyOptIn_us-en.png" src="https://files.readme.io/cd6cbcaeb7f831f4efe74a9a6c6b20d5095602e7edf4dd38becd90864e73c2fb-360010263157.png" />

El SDK web envía datos de los eventos de los visitantes a AppsFlyer. Puedes controlar, detener o iniciar el envío de eventos como se describe en esta sección.

Consideración:

* **Configuración del estado inicial del SDK**: Determina si el SDK envía eventos al cargar inicialmente la página web o si el SDK debe esperar hasta que des un comando explícito para comenzar a enviar eventos. La configuración está incluida en el fragmento web.
* **Control explícito:** úsalo para detener o iniciar el envío de eventos. Por ejemplo, si implementas banners de aceptación/exclusión voluntaria de datos (también conocidos como banners de consentimiento de cookies), integra los comandos explícitos en los controles de tu banner para iniciar y detener el envío de eventos. El control explícito tiene prioridad sobre la configuración del estado inicial del SDK y utiliza cookies propias persistentes que tienen las siguientes características:
  * Se establecen en el dominio del sitio web.
  * Caducan después de un período establecido por el SDK web o según lo determine el navegador. Después de que caduquen las cookies, el SDK web vuelve a la configuración del estado inicial.
  * La cookie del SDK web no interfiere y siempre está sujeta a la configuración de cookies específica del navegador.

<div id="sdk-initial-state-setting" />

#### Configuración del estado inicial del SDK

| Configuración | Se requiere fragmento |
| --- | --- |
| [Predeterminado] Enviar eventos | Haz el siguiente cambio en el fragmento del SDK web. Si es necesario, agrega el parámetro measurementStatus:<br /><br />Establece measurementStatus=true<br /><br />`{pba: {webAppId: "********-****-****-*****************", measurementStatus:true}` |
| No enviar eventos | Haz el siguiente cambio en el fragmento del SDK web. Si es necesario, agrega el parámetro measurementStatus:<br /><br />Establece measurementStatus=false  <br />  <br />`{pba: {webAppId: "********-****-****-*****************", measurementStatus:false}` |

<div id="explicit-control" />

#### Control explícito

| Opción | Comando |
| --- | --- |
| Iniciar el envío de eventos (optar por la aceptación) | `window.AF_SDK.PLUGINS.PBA.enableMeasurement()` |
| Detener el envío de eventos (optar por la exclusión) | `window.AF_SDK.PLUGINS.PBA.disableMeasurement()` |

</Accordion>

<div id="implement-a-content-security-policy-csp-policy" />

<Accordion title="Implementar una política de Política de Seguridad de Contenido (CSP)">

Si tu sitio web requiere estrictos protocolos de seguridad o privacidad de datos, utiliza los siguientes mecanismos para configurar cómo interactúa el SDK web con tu entorno y tus datos.

<div id="content-security-policy-csp" />

#### Política de Seguridad de Contenido (CSP)

Si tu sitio web requiere que JavaScript esté protegido por un CSP, el SDK web admite dos enfoques según la configuración de tu CSP.

* **CSP usando self**: Agrega `https://websdk.appsflyersdk.com` a tu lista `script-src` de permitidos. Esto funciona tanto para el Standard Web SDK como para Advanced SDK Verification.
* **CSP usando nonce**: Si tu política utiliza `script-src 'nonce-...'`, puedes utilizar la [variante nonce-extended de Advanced SDK Verification](#advanced-sdk-verification-con-fragmentos-de-csp-nonce). Esto reenvía el nonce a las tres etiquetas de script requeridas por el proceso de verificación. Reemplaza `{{CSP_NONCE}}` con tu valor nonce generado por el servidor, por solicitud.

La siguiente tabla muestra qué políticas de CSP son compatibles con la variante nonce-extended.

| Política | Funciona | Notas |
| --- | --- | --- |
| `script-src 'self'` | No | No se permite el origen de CDN externo; el script en línea también se bloquea. |
| `script-src 'self' https://websdk.appsflyersdk.com` | Parcial | Permite el loader y el SDK, pero el script de configuración en línea sigue bloqueado. |
| `script-src 'nonce-...' https://websdk.appsflyersdk.com` | Sí | Nonce cubre el script en línea y el loader; la etiqueta del SDK es reenviada por el loader. |
| `script-src 'nonce-...' 'strict-dynamic'` | Sí (recomendado) | Nonce cubre el script en línea y el loader; `strict-dynamic` propaga confianza a la etiqueta del SDK inyectada dinámicamente. No se necesita origen de CDN en la lista de permitidos. |

Compatibilidad con políticas de CSP

<div id="advanced-sdk-verification-with-csp-nonce-snippets" />

#### Advanced SDK Verification con fragmentos de CSP nonce

<div id="advanced-verification-without-smart-banners" />

<div id="nonce-without-smart-banners" />

<Accordion title="Sin Smart Banners">

```html
<script nonce="{{CSP_NONCE}}">
  // Queue — buffers AF() calls until the SDK is ready
  window. AppsFlyerSdkObject = "AF";
  window. AF = window. AF || function() {
    (window.AF.q = window. AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  window. AF.id = window. AF.id || { pba: { webAppId: "WEB_DEV_KEY" } };
  window. AF.plugins = {};

  // Manifest loader config — nonce forwarded to the injected SDK <script> tag
  window. AF_LOADER_CONFIG = {
    baseUrl: "https://websdk.appsflyersdk.com",
    plugins: ["pba"],
    nonce: "{{CSP_NONCE}}"
  };

  // Inject manifest loader
  var loaderScript = document.createElement("script");
  loaderScript.src = "https://websdk.appsflyersdk.com/manifestLoader.v1.js";
  loaderScript.integrity = "sha384-Uncl2YwvjFpFz0PwEfl3bL/0JsOQcDFEpwXHzcN0MBavn9vvFEx5pZxADTq8h+CV";
  loaderScript.crossOrigin = "anonymous";
  loaderScript.nonce = "{{CSP_NONCE}}";
  loaderScript.async = true;
  document.head.appendChild(loaderScript);
</script>
```

</Accordion>

<div id="advanced-verification-with-smart-banners" />

<div id="nonce-with-smart-banners" />

<Accordion title="Con Smart Banners">

```html
<script nonce="{{CSP_NONCE}}">
  // Queue — buffers AF() calls until the SDK is ready
  window. AppsFlyerSdkObject = "AF";
  window. AF = window. AF || function() {
    (window.AF.q = window. AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  window. AF.id = window. AF.id || { pba: { webAppId: "WEB_DEV_KEY" }, banners: { key: "YOUR_BANNER_KEY" } };
  window. AF.plugins = {};

  // Manifest loader config — nonce forwarded to the injected SDK <script> tag
  window. AF_LOADER_CONFIG = {
    baseUrl: "https://websdk.appsflyersdk.com",
    plugins: ["banners", "pba"],
    nonce: "{{CSP_NONCE}}"
  };

  // Inject manifest loader
  var loaderScript = document.createElement("script");
  loaderScript.src = "https://websdk.appsflyersdk.com/manifestLoader.v1.js";
  loaderScript.integrity = "sha384-Uncl2YwvjFpFz0PwEfl3bL/0JsOQcDFEpwXHzcN0MBavn9vvFEx5pZxADTq8h+CV";
  loaderScript.crossOrigin = "anonymous";
  loaderScript.nonce = "{{CSP_NONCE}}";
  loaderScript.async = true;
  document.head.appendChild(loaderScript);
</script>
```

</Accordion>

</Accordion>

<div id="discard-query-params" />

<Accordion title="Descartar parámetros de consulta">

Si los parámetros de consulta contienen datos que no deseas que AppsFlyer registre, puedes indicar a la plataforma de AppsFlyer que descarte algunos o todos los parámetros de consulta. Al hacerlo, no estarán disponibles en el raw data ni en los reportes.

Puedes implementar los métodos descritos en relación con URL, referentes y header\_referer.

<div id="query-discard-options" />

#### Opciones de descarte de consultas

| Método | Descripción |
| --- | --- |
| Descartar todos los parámetros de consulta | Adjunta `af_url=true` a la URL. |
| Descartar parámetros de consulta especificados | Al establecer una máscara de parámetro de consulta, especifica qué parámetros se descartan.  Establece la máscara de descarte usando `af_url_mask=param`, donde param es el nombre del parámetro.<br /><br />Ejemplo:<br /><br />**URL con máscara:**<br /><br />`param1=value1&param2=value2&param3=value3&af_url_mask=param2;param3`<br /><br />**URL después del descarte:**<br /><br />`param1=value1&af_url_mask=param2;param3` |

</Accordion>

<div id="principles-of-event-recording" />

## Principios de registro de eventos.

<div id="conversion-and-standard-events" />

<Accordion title="Conversión y eventos estándar">

* Los eventos de usuario son registrados por el SDK, que envía el evento a la plataforma AppsFlyer.
* Utilizando la lista de <Anchor target="_blank" href="/marketers/es/docs/pba-brand-bundles-and-settings#web-event-settings">eventos de conversión</Anchor> establecida por el marketer, AppsFlyer divide los eventos en eventos estándar y de conversión.
* Los datos de los eventos de conversión están disponibles en los paneles de control de la PBA.
* Los datos de los eventos estándar y de conversión están disponibles en los <Anchor target="_blank" href="/marketers/es/docs/pba-raw-data-reports">reportes de raw data</Anchor>.

<div id="conversion-events" />

### Eventos de conversión

* Los eventos de conversión brindan insights sobre tus esfuerzos comerciales y de marketing. Los eventos de conversión incluyen compras, descargas, registros y suscripciones.
* La PBA atribuye los eventos de conversión a la fuente de medios que llevó al usuario a visitar el sitio web.
* Al identificar la fuente de medios atribuida, puedes medir y diferenciar la calidad de los usuarios aportados por diferentes fuentes de medios.
* Los eventos de conversión se utilizan para registrar los ingresos y calcular el ROI.
* Utilízalos para comparar el presupuesto de los anuncios de fuentes de medios específicas con los ingresos generados por los usuarios que provienen de estas fuentes de medios.

<div id="standard-events" />

### Eventos estándar

* Los eventos estándar se utilizan para validar la trayectoria del usuario y los embudos que generan conversiones.
* Utilízalos para medir la actividad de los usuarios y resaltar las fuentes de medios que atraen a los usuarios comprometidos.
* Registra la actividad de los usuarios para marcarlos para campañas de reengagement.

<div id="recording-events" />

### Registro de eventos

Activa el SDK web para registrar eventos cuando se cumplan ciertas condiciones, por ejemplo, cuando se carga una página de aterrizaje o cuando los usuarios interactúan con los elementos del sitio web. Consulta los [ejemplos de registro de eventos](#recording-events::f1e16eae).

</Accordion>

<div id="identifying-users-using-customer-user-id-cuid" />

<Accordion title="Identificación de usuarios mediante el ID de usuario del cliente (CUID)">

* Los usuarios web se identifican en AppsFlyer mediante el CUID único que les asignas. Normalmente, el CUID lo administran los servidores backend.
* Utiliza el mismo valor CUID que utilizas en el entorno móvil. Hacerlo te permitirá tener una visión holística de la actividad de los usuarios en múltiples plataformas. La función en el SDK móvil es setCustomerUserId (<Anchor target="_blank" href="/marketers/es/docs/customer-user-id-field-cuid#configuración-del-cuid">iOS</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/customer-user-id-field-cuid#configuración-del-cuid">Android, Unity</Anchor>).
* Para establecer el CUID en el SDK web:
  * Establece el CUID tan pronto como tengas acceso a él. La mayoría de las veces, esto significa que debes esperar a que el usuario se identifique iniciando sesión o registrándose.
  * Activa la llamada de JavaScript a setCustomerUserId() como se muestra en el siguiente ejemplo. tiene un tamaño de 40-60 Kb.   
    Nota: Envía el CUID como una cadena incluso si es un número. Para ello, ponlo entre comillas.
* Si implementas S2S web, ten en cuenta que es posible que debas notificar a la PBA cuando <Anchor target="_blank" href="/marketers/es/docs/web-server-to-server-events-api-for-pba-web-s2s#setcuid-method">asocies</Anchor> un CUID con un ID de visitante web en tu backend.
* Los CUID no deben contener <Anchor target="_blank" href="/marketers/es/docs/customer-user-id-field-cuid#cuid-y-privacidad">información personal directamente identificable,como</Anchor> un número de teléfono o una dirección de correo electrónico.

**Ejemplo: establecer el CUID**

```javascript
// Asocia todos los eventos web actuales del usuario al ID 663274 
AF('pba', 'setCustomerUserId' , '663274')
```

</Accordion>

<div id="web-sdk-event-parameters" />

<Accordion title="Parámetros de eventos del SDK web">

| Nombre de parámetro | Obligatorio | Descripción |
| --- | --- | --- |
| eventType | Sí | Tipo de evento<br /><br />Formato: String<br /><br />Completa siempre este parámetro con EVENT.<br /><br />Ejemplo: eventType: "EVENT" |
| eventName | Sí | Nombre del evento<br /><br />Formato: String<br /><br />Ejemplo: Compra, suscripción |
| ~~eventCategory~~ | No | Este parámetro está obsoleto y se eliminará del sistema en una fecha que se anunciará. En su lugar, utiliza el parámetro eventValue. |
| ~~eventLabel~~ | No | Este parámetro está obsoleto y se eliminará del sistema en una fecha que se anunciará. En su lugar, utiliza el parámetro eventValue. |
| eventRevenue | No | Ingresos asignados a un evento de conversión<br /><br />Formato: Float |
| eventRevenueCurrency | No | Moneda de ingresos<ul><li>Código de divisa <Anchor target="_blank" href="https://en.wikipedia.org/wiki/ISO_4217">ISO 4217</Anchor> de 3 caracteres.</li><li>Valor predeterminado: USD</li></ul>Formato: String |
| valor del evento | No | Mapa de parámetros del evento que describen el evento. Utiliza este parámetro para enviar eventos in-app enriquecidos, como el SKU del producto y el precio del artículo.<br /><br />Formato: JSON<br /><br />**Ejemplo:** Para enviar SKU ABC123, de color azul y un precio unitario de $3,99<br /><br />`{"sku": "ABC123", "color": "blue", "unit_price":3.99,"currency": "USD"}`<br /><br />**Limitación:** 1000 caracteres. si excedes el límite, se truncará. |

</Accordion>

<div id="recording-event-scenarios" />

<Accordion title="Escenarios de registro de eventos">

Evento de ejemplo

```javascript
// purchase event of shoes with associated revenue
AF('pba', 'event', {eventType: 'EVENT', eventName: 'purchase', eventRevenue: 12, eventValue: {"key1": 123, "key2": "name"}});
```

Los eventos que envías dependen de la naturaleza de tu aplicación web. Por ejemplo, una aplicación de tienda en línea requiere un conjunto de eventos diferentes a los de un medio de comunicación. Mira los escenarios siguientes para tener una idea de los eventos que debes enviar y cuándo.

<div id="online-store" />

#### Tienda en línea

Supongamos que administras una tienda en línea. Algunos eventos estándar que quizás quieras registrar serían:

* Buscar: evento estándar
* Agregar al carrito: evento estándar
* Quitar del carrito: evento estándar
* Comprar: evento de conversión

Medio informativo

Supongamos que estás administrando un medio informativo. Algunos eventos que quizás quieras registrar serían:

* Registro: evento de conversión
* Compra de suscripción: evento de conversión

</Accordion>

<div id="ensuring-that-events-are-sent" />

<Accordion title="Garantizar el envío de los eventos">

Esta parte está destinada a desarrolladores web.

<Anchor target="_blank" href="/marketers/es/docs/test-pba-web-sdk-integration">Prueba la integración del SDK web para la PBA:</Anchor> consulta los eventos de prueba en tiempo real.

**Para garantizar que los eventos se envíen a AppsFlyer**:

1. Abre el sitio web.
2. Abre las herramientas para desarrolladores del navegador.
   * <Anchor target="_blank" href="https://developers.google.com/web/tools/chrome-devtools/open#console">Cómo abrir las herramientas para desarrolladores en Chrome</Anchor>
   * <Anchor target="_blank" href="https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/Web_Inspector_Tutorial/EnableWebInspector/EnableWebInspector.html">Cómo abrir las herramientas para desarrolladores en Safari</Anchor>
3. Cambia a la pestaña Network (Red).
4. Activa el evento.
5. Filtro por mensaje.

   <Image align="center" alt="pba_af_event.png" src="https://files.readme.io/394f43890d1aaf09114054a3bca1a003178526e768a5da0b554dbc8d63ef1eb4-360003502238.png" />
6. Busca una solicitud de red que comience con el destino wa.appsflyer.com (observa la captura de pantalla a continuación).
7. Asegúrate de que:
   1. El código de estado es 200.
   2. La carga útil de solicitud se alinea con los parámetros del evento.

</Accordion>

<div id="examples" />

## Ejemplos

<div id="recording-events::f1e16eae" />

<Accordion title="Registro de eventos">

El código proporcionado es solo para fines ilustrativos. No utilices este código tal como está.

* Supuestos: la página ya ha cargado el SDK web en el momento en que se envía el evento.
* Los escenarios de ejemplo contienen el código para registrar eventos cuando:
  * se carga una página de aterrizaje.
  * los usuarios interactúan con el sitio web.

<Tabs>
<Tab title="Registro nativo de eventos">

**Registro de eventos cuando se carga una página de aterrizaje**

* Tienes una página de suscripción para boletines informativos y deseas registrar las suscripciones.
* También puedes configurar una página de agradecimiento y redirigir a los usuarios a ella después de suscribirse.

```html
<html>
    <head>
        <!-- Supón que el servidor devuelve una respuesta con detalles sobre el usuario que se acaba de suscribir -->
        <!-- Como alternativa, puedes extraer datos de localStorage o de las cookies,
            en caso de que se hayan establecido en alguno de ellos durante el proceso de suscripción
        -->
        <script>window.onload = function(){
            AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category': 'holiday_promotion', eventValue: {'label' : 'newspaper'}, eventName: 'subscription',}); } </script> </head> <body> <h1>Gracias por suscribirte a nuestro boletín</h1> </body> </html>
```

* El código anterior contiene una página HTML básica. La página web debe cargar el SDK web para poder enviar eventos.
* Una vez que se carga la página, después de que el usuario es redirigido a ella, el método de carga de ventana llama al método AF() para enviar el evento de suscripción a AppsFlyer.

**Registro de eventos cuando los usuarios interactúan con el sitio web**

* Tienes un sitio web de eCommerce y deseas registrar los eventos de checkout.
* Cuando el usuario hace clic en el botón de checkout, el SDK web envía un evento a AppsFlyer.

```html
<html>
<head>
    <!-- Supón que los datos sobre los productos del carrito de la compra
    se almacenan en localStorage -->
    <script>
        window.onload = function () {
            document.getElementById('checkout').addEventListener('click', function () {
                AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'checkout'});
            });
        }
    </script>
</head>
<body>
    <h1>Carrito de la compra</h1>
    <h2>Camisa</h2>
    <p>
        <ul>
            <li>Color: azul</li>
            <li>Cantidad: 2</li>
            <li>Precio: $20</li>
        </ul>
    </p>
    <h2>Pantalones</h2>
    <p>
        <ul>
            <li>Color: negro</li>
            <li>Cantidad: 3</li>
            <li>Precio: $15</li>
        </ul>
    </p>
    <button id='checkout'>Checkout</button>
</body>
</html>
```

El código anterior muestra una página HTML básica. La página web debe cargar el SDK web para poder enviar eventos.

* Una vez que la página se carga, vincula un listener de clics al botón **Checkout**.
* Cuando el usuario hace clic en el botón **Checkout**, la función de callback:
  * recupera datos de localStorage.
  * llama al método AF() y le pasa datos.
* El método AF() envía el evento a AppsFlyer.

</Tab>

<Tab title="Registro de eventos de Google Tag Manager">

**Registro de eventos cuando se carga una página de aterrizaje**

* Tienes una página de suscripción para boletines informativos y deseas registrar las suscripciones realizadas correctamente.
* Configuras una página de agradecimiento a la que se redirige a los usuarios después de suscribirse correctamente.

1. Configurar una página de agradecimiento

   ```html Markup
   <html>
   <head>
       <script>
            // Google Tag Manager carga el SDK web
           <script>(function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
           new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
           j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
           'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
           })(window,document,'script','dataLayer','GTM-XXXX');
       </script>
        <script>
           // Supón que el servidor devuelve una respuesta con detalles sobre el usuario que se acaba de suscribir
           function getResponseFromServer() {
               return JSON.stringify({ action: 'subscribe', category: 'site actions', label: userEmail })
           }
           //También puedes extraer datos de localStorage o de las cookies,
           //en caso de que se hayan establecido en alguno de ellos durante el proceso de suscripción
           localStorage.setItem('data', JSON.stringify({ action: 'subscribe', category: 'site actions', label: 'user@email.com' }));
       </script>
   </head>
   <body>
       <h1>Gracias por suscribirte a nuestro boletín</h1>
   </body>
   </html>
   ```

   El código anterior carga GTM, que a su vez carga el SDK web. Luego, otras dos acciones tienen lugar en el script. Una es una función que obtiene una respuesta del servidor con los detalles del usuario. La otra establece los datos en el almacenamiento local. GTM tiene acceso tanto a la función como a localStorage. Puedes llamar a la función y acceder a localStorage usando GTM.
2. Agregar una nueva etiqueta para atribuir suscripciones después de que se cargue la página de agradecimiento

   <Image align="center" alt="Añade una nueva etiqueta para atribuir suscripciones en Google Tag Manager" src="https://files.readme.io/c85a3cbc6c9675e4bfa762ff0a9930d58b1e02b13f147342a11b433e1d211b11-360002750309.png" />
3. Dale a la etiqueta un nombre distintivo y selecciona la opción de tipo de etiqueta **Custom HTML** (HTML personalizado).
4. Pon el siguiente código en **Custom HTML** (HTML personalizado).

   ```html
   <script> 
   AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'subscription'}); </script>
   ```

   <Image align="center" alt="gtm_tag_after_subscribe.png" src="https://files.readme.io/6cf080f94a97a7f38c50899a93d154320995e91f60963c075a5dd03b3a080408-360003515298.png" />
5. Expande el control **Advanced Settings** (Configuración avanzada) y luego el control **Tag Sequencing** (Secuenciación de etiquetas) debajo del área de texto y asegúrate de que esté configurado para activar la conversión después de ejecutar la etiqueta.

   <Image align="center" alt="Configuración de secuenciación de etiquetas en Google Tag Manager" src="https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png" />
6. Para activar la etiqueta de conversión, configura un activador. En el ejemplo, el activador se dispara al cargar la página de agradecimiento.

   <Image align="center" alt="Activador configurado para activarse al cargar la página de agradecimiento" src="https://files.readme.io/25fd3944971abc811cbe6192cec8c73bb31b3b3c3715a1b8918a71d7f8bf72b1-360002902185.png" />

**Registro de eventos cuando los usuarios interactúan con el sitio web**

* Tienes un sitio web de eCommerce y deseas registrar los eventos de checkout.
* Después de que el usuario hace clic en el botón de checkout, el SDK web envía un evento a AppsFlyer.

1. Configurar una página de checkout

   ```html Markup
   <html>
   <head>
       <script>
           // Google Tag Manager carga el SDK web
           <script>(function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
           new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
           j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
           'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
           })(window,document,'script','dataLayer','GTM-XXXX');
       </script>
   </head>
   <body>
       <h1>Carrito de la compra</h1>
       <h2>Camisa</h2>
       <p>
           <ul>
               <li>Color: azul</li>
               <li>Cantidad: 2</li>
               <li>Precio: $20</li>
           </ul>
       </p>
       <h2>Pantalones</h2>
       <p>
           <ul>
               <li>Color: negro</li>
               <li>Cantidad: 3</li>
               <li>Precio: $15</li>
           </ul>
       </p>
       <button id='checkout'>Checkout</button>
   </body>
   </html>
   ```

   El código anterior carga el SDK web usando GTM. El resto es simplemente HTML que imita una página de carrito de compras. Observa el botón **Checkout** que tiene el ID de checkout. Es necesario al configurar GTM para manejar un clic en ese botón.
2. En GTM, haz clic en **Variables**, haz clic en **Configure** (Configurar) y marca **Click Element** (Elemento de clic) en la lista de **Built-In Variables** (Variables incorporadas).  

   <Image align="center" alt="gtm-create-variable.png" src="https://files.readme.io/2f38308b4e4b9f279420f0219b220f2796d337a39a79241861c3d31bdb442b24-360002899569.png" />
3. Crea una nueva variable, dale un nombre significativo y elige el tipo de **Todos los elementos.**  

   <Image align="center" alt="gtm-checkout-all-elements.png" src="https://files.readme.io/1c370646a4c21dc0fcb8351c756a9fdc81a1a8039d0557b716bc8a4ae51a3fad-360002899589.png" />
4. En la configuración del activador, elige **Algunos clics**, y elige un **Elemento de clic** que **coincida con el Selector CSS** de #checkout.  

   <Image align="center" alt="gtm-checkout-click-elememt.png" src="https://files.readme.io/a101d6c27438d3e05eed9db7ea58b57df8bba9a92d4f9e30caee005366dbcf8c-360002903565.png" />
5. Crea una nueva etiqueta para la acción de checkout, elige el tipo Custom HTML (HTML personalizado) y configura el activador en el activador de checkout.

   ```html
   <script>
    AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'checkout'}); </script>
   ```

   <Image align="center" alt="gtm-checkout-tag.png" src="https://files.readme.io/8d3f99dcd3c3ff8df9e6fc13076b798237b86f8cbc5bbd26f349fa9948edb0d6-360003431857.png" />

</Tab>
</Tabs>

* Asegúrate de que la etiqueta de funciones del SDK web esté cargada antes de que se active el evento.
* No envíes caracteres especiales en los valores de los eventos, como símbolos de moneda en el valor de los ingresos.
* Las cadenas de valores deben tener menos de 50 caracteres.

</Accordion>

<div id="setting-customer-user-id-after-signup" />

<Accordion title="Configuración del ID de usuario del cliente después del registro">

El código proporcionado en estos ejemplos es solo de referencia. No utilices este código tal como está. Si no estás seguro de cómo utilizar este código, consulta a tu desarrollador web. 

Supuesto: La página carga el SDK web antes de enviar el evento; no cargues el SDK nuevamente.

Situación del usuario:

* Un usuario se registra en tu sitio web.
* El código del sitio web recopila los datos del usuario y los envía a tu servidor.
* El servidor genera un CUID único para el usuario.
* En la página de agradecimiento después del registro, consultas al servidor el nuevo CUID.
* Mediante la respuesta del servidor, configuras el CUID de AppsFlyer mediante el método setCustomerUserId() del SDK web.

<Tabs>
<Tab title="Nativo">

Configura una página de registro:

```html Markup
<html>
<head>
    <script>
         // Google Tag Manager loads the Web SDK
        (function (w, d, s, l, i) {
            w[l] = w[l] || []; w[l].push({
                'gtm.start':
                    new Date().getTime(), event: 'gtm.js'
            }); var f = d.getElementsByTagName(s)[0],
                j = d.createElement(s), dl = l != 'dataLayer' ? '&l=' + l : ''; j.async = true; j.src =
                    'https://www.googletagmanager.com/gtm.js?id=' + i + dl; f.parentNode.insertBefore(j, f);
        })(window, document, 'script', 'dataLayer', 'GTM-5VJ6C7R');

    // This function stores the user email to be sent to the server after the user reaches the thank you page
    // the response from the server is a unique CUID that should be used in the web SDK setCustomerUserId method
        function storeUserEmail (){
            var userEmail = document.getElementById('email').value;
            localStorage.setItem('user_email', userEmail);
        }
    </script>
</head>
<body>
    <h1>Sign Up</h1>
    <form onsubmit="storeUserEmail()" action="/signup" method="post">
        <div><label>Name</label>
            <input type="text" name="name" id="name"></div>
        <br />
        <div> <label>Email</label>
            <input type="email" name="email" id="email"></div>
        <br />
        <input type="submit" id="submit">
    </form>
</body>
</html>
```

El código anterior es un formulario de registro sencillo. Cuando se envía el formulario, el correo electrónico se almacena en localStorage. Cuando el usuario llega a la página de agradecimiento, la dirección de correo electrónico del usuario se envía al servidor para generar el CUID único para la dirección de correo electrónico.

Configura una página de agradecimiento para los usuarios que se registren:

```
Copia la clave de desarrollador web requerida (WEB_DEV_KEY).
```

El código utiliza la API Fetch. Envía al servidor la dirección de correo electrónico ingresada por el usuario. Suponiendo que el servidor crea un usuario con un CUID único al registrarse, enviar la dirección de correo electrónico al servidor tiene como objetivo recibir un CUID único. El servidor responde con un CUID único y este CUID único es el valor que se transmite con el método setCustomerUserId.

</Tab>

<Tab title="Google Tag Manager">

1. Configura una página de registro:

   ```html Markup
   <html>
   <head>
       <script>
            // Google Tag Manager carga el SDK web
           (function (w, d, s, l, i) {
               w[l] = w[l] || []; w[l].push({
                   'gtm.start':
                       new Date().getTime(), event: 'gtm.js'
               }); var f = d.getElementsByTagName(s)[0],
                   j = d.createElement(s), dl = l != 'dataLayer' ? AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
   o.src="https://websdk.appsflyersdk.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
   p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "WEB_DEV_KEY"}})
       </script>
       <script>
           // using the fetch api to send the user email to the server
           // and get the unique user id in return 
           window.onload = function () {
           var userEmail = localStorage.getItem('user_email');
           fetch('users/' + userEmail).then(function (res) {
                  res.text().then(function (id) {
                  console.log(id);
                  AF('pba', 'setCustomerUserId', id);
               });
            });
           } </script> 
       </head>
       <body> 
               <h1>Thank You for Signing Up!</h1> 
        </body> 
    </html>
   ```

   El código anterior es un formulario de registro sencillo. Cuando se envía el formulario, la dirección de correo electrónico se almacena en localStorage. Cuando el usuario llega a la página de agradecimiento, la dirección de correo electrónico del usuario se envía al servidor para obtener el CUID único para ese correo electrónico.
2. Configura una página de agradecimiento para los usuarios que se registren:

   ```
   Fecha de vencimiento
   ```

   El código anterior es una página de agradecimiento que tiene un activador GTM que envía al servidor la dirección de correo electrónico proporcionada por el usuario en el formulario de registro.  
   Suponiendo que, al momento del registro, el servidor crea un usuario con un CUID único.  
   El correo electrónico se envía al servidor con el propósito de recibir un CUID único.  
   El servidor responde con un CUID único que se envía mediante el método setCustomerUserId().  
   Continúa con este procedimiento para crear el activador y la pestaña.
3. Agrega una nueva etiqueta para atribuir las suscripciones después de que se cargue la página de agradecimiento. ![Añade una nueva etiqueta para atribuir suscripciones en Google Tag Manager](https://files.readme.io/c85a3cbc6c9675e4bfa762ff0a9930d58b1e02b13f147342a11b433e1d211b11-360002750309.png)
4. Dale a la etiqueta un nombre distintivo y selecciona la opción de tipo de etiqueta «HTML personalizado» ![GoogleTag.jpg](https://files.readme.io/beab3305bc50c44c291997fa9b77bf4df7dd5dd9207a1bf766c2e1702e314d2c-360016246418.jpg)

   ```html
   <script>
           var userEmail = localStorage.getItem('user_email');
           fetch('users/' + userEmail).then(function (res) {
            res.text().then(function (id) {
                  console.log(id);
                  AF('pba', 'setCustomerUserId', id);
               });
            });
   </script>
   ```
5. Expande el control **Advanced Settings** (Configuración avanzada) y luego el control **Tag Sequencing** (Secuenciación de etiquetas) debajo del área de texto y asegúrate de que esté configurado para activar la conversión después de ejecutar la etiqueta.

   <Image align="center" alt="Configuración de secuenciación de etiquetas en Google Tag Manager" src="https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png" />
6. Establece un activador para que la etiqueta de conversión indique cuándo se debe activar la etiqueta de conversión (en el siguiente ejemplo, se activa al cargar la página de agradecimiento).

   <Image align="center" alt="Activador configurado para activarse al cargar la página de agradecimiento" src="https://files.readme.io/25fd3944971abc811cbe6192cec8c73bb31b3b3c3715a1b8918a71d7f8bf72b1-360002902185.png" />

</Tab>
</Tabs>

La función setCustomerUserId se puede enviar en cualquier etapa del flujo del usuario, por ejemplo, después de iniciar sesión y registrarse. AppsFlyer utiliza el CUID más reciente enviado para actualizar al usuario observado actual para puntos de contacto y eventos pasados ​​o futuros.

Utiliza el mismo valor CUID que utilizas en la función setCustomerUserId en la aplicación móvil (consulta el setCustomerUserId móvil para: <Anchor target="_blank" href="/marketers/es/docs/customer-user-id-field-cuid#configuración-del-cuid">iOS</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/customer-user-id-field-cuid#configuración-del-cuid">Android,</Anchor> Unity)

</Accordion>

<div id="addtional-information" />

## Información adicional

<div id="web-sdk-cookies" />

<Accordion title="Cookies del SDK web">

Las cookies enumeradas en la siguiente tabla son configuradas o utilizadas por el SDK web en tu sitio web.

En la tabla se utilizan las siguientes abreviaturas:

* AMP: Páginas móviles aceleradas
* CDN: Red de entrega de contenido
* 3PC: Cookies de terceros

| Nombre de cookie | Dominio | Vida útil | Cuando se utiliza | Detalles |
| --- | --- | --- | --- | --- |
| afUserid | El dominio de tu sitio web | 395 días | Sin AMP | Identificar a un usuario en el contexto de los eventos de carga web y navegación |
| AF\_SYNC | El dominio de tu sitio web | 1 semana | Sin AMP | <ul><li>Indicador que muestra que se ha establecido un identificador de usuario final</li><li>Esto se utiliza para reducir los tiempos de carga del sitio</li></ul> |
| af\_id | appsflyer.com | 395 días | Sin AMP cuando se permite 3PC | Identificar a un usuario en el contexto de los eventos de inicio de la aplicación y de navegación |
| af\_id | onelink.me | 395 días | Sin AMP cuando se permite 3PC | Enlazar engagements de banners, engagements de OneLink o ambos a eventos de inicio de aplicaciones. |
| amp-afUserid | AMP CDN o el dominio de tu sitio web | 1 año | Para el servicio de páginas por AMP |  |
| AF\_DEFAULT\_MEASUREMENT\_STATUS | El dominio de tu sitio web | 395 días | Almacena el estado de consentimiento de la PBA. Impide el funcionamiento del SDK hasta que se otorga el consentimiento del usuario. No está configurado de forma predeterminada: se usa solo cuando se configura la [puerta de consentimiento](/docs/pba-web-sdk-integration-guide#sending-events-optinoptout). | Sin AMP |

</Accordion>

<div id="release-notes" />

<Accordion title="Notas de la versión del SDK web">

| Fecha | Versión | Notas |
| --- | --- | --- |
| 01-07-2021 | 1.0 | [Descartar parámetros de consulta](/docs/pba-web-sdk-integration-guide#discard-query-params) |
| 01-06-2021 | 1.0 | [Implementar una Política de Seguridad de Contenido (CSP)](/docs/pba-web-sdk-integration-guide#implement-a-content-security-policy-csp-policy) |
| 31-08-2020 | 1.0 | [Se agregó la funcionalidad de aceptación y exclusión opcional](/docs/pba-web-sdk-integration-guide#sending-events-optinoptout) |
| 16-04-2020 | 1.0 | La función CustomerUserId() reemplaza el evento IDENTIFY para enviar el CUID único |
| 30-07-2020 | 1.0 | <ul><li>Control explícito de inicio/parada para enviar eventos</li><li>Cambio del estado inicial predeterminado</li></ul> |

</Accordion>

<div id="deprecations" />

<Accordion title="Entrada en desuso">

* Un aviso de entrada en desuso proporciona un aviso de nuestra intención de dejar de admitir una función o método. La función o el método continúa funcionando hasta su fecha de vencimiento.
* Considera los avisos de entrada en desuso como una oportunidad para realizar cambios en tu código.

| Fecha de desuso | Fecha de baja | Detalles |
| --- | --- | --- |
| 16-04-2020 | Pendiente de anuncio | **Método en desuso:** envío del ID de usuario del cliente (CUID) en el parámetro de evento customUserId con eventType establecido en "IDENTIFY"<br /><br />**Método actual:** envío del CUID utilizando la función setCustomerUserId() . |

</Accordion>

<div data-zendesk-anchors="web-sdk-user-and-integration-guide=gu%C3%ADa-de-integraci%C3%B3n-y-del-usuario-del-sdk-web h_01HFKCMH8HAW5DN4K9H1A5Q2NJ=gu%C3%ADa-de-integraci%C3%B3n-y-del-usuario-del-sdk-web step-2-select-a-code-snippet=selecci%C3%B3n-de-un-fragmento-de-c%C3%B3digo h_01KP11XJV8RDV378GMFF0DVZ8V=selecci%C3%B3n-de-un-fragmento-de-c%C3%B3digo standard=standard-web-sdk h_01KP11XJV8MN64YV17D1M0T5B9=standard-web-sdk h_01KP3CJBZWK17M58W9M2EP8VC3=standard-without-smart-banners h_01KP3CJBZWKW1K9P9V1XGYM5ED=standard-with-smart-banners h_01KP11XJV8ZGF4SDXJH6FKX18E=advanced-sdk-verification h_01KP3CJBZWP7HDJ0GE2DF3TTE3=advanced-verification-without-smart-banners h_01KP3CJBZWJWS9H0XVHQFF758B=advanced-verification-with-smart-banners integrating-the-web-sdk-into-the-website=integraci%C3%B3n-del-sdk-web-en-el-sitio-web h_01HFKCMH8HCDNGFJEN32BNA9F2=integraci%C3%B3n-del-sdk-web-en-el-sitio-web h_01HFKCMH8HVTJX37PD22ZFV0AY=installation-and-integration considerations-and-actions-required=consideraciones-y-acciones-requeridas h_01HFKCMH8H0JBGD2GWY127428R=consideraciones-y-acciones-requeridas javascript-code-snippet=fragmento-de-c%C3%B3digo-javascript h_01HFKCMH8HC064MHGH8D66QCYK=fragmento-de-c%C3%B3digo-javascript to-install-the-web-sdk-without-smart-banners=para-instalar-el-sdk-web-sin-smart-banners h_01HFKCMH8HST7G880G44WXXXB6=para-instalar-el-sdk-web-sin-smart-banners to-implement-the-web-sdk-with-smart-banners=para-implementar-el-sdk-web-con-smart-banners h_01HFKCMH8HX4SQP6YCBHJH4AX5=para-implementar-el-sdk-web-con-smart-banners h_01HFKCMH8JMMPMHFR4399QPRJV=create-a-property-in-adobe-experience-cloud h_01HFKCMH8J8WVHP7RZ2ENHGY9V=add-the-web-sdk-to-the-adobe-launch-property h_01HFKCMH8J2MAXJ3YVHJ2AJHWQ=add-the-adobe-launch-tag-to-the-website h_01HFKCMH8JWE1Q2749N54MAYRT=publish-the-adobe-launch-environment h_01HFKCMH8JFQQG0BEQ5CATGQ2P=ensure-that-the-sdk-is-working h_01HFKCMH8JCHH5WB5XRC8029DE=sending-events-optinoptout sdk-initial-state-setting=configuraci%C3%B3n-del-estado-inicial-del-sdk h_01HFKCMH8JSJR95Y9KNANABBKR=configuraci%C3%B3n-del-estado-inicial-del-sdk explicit-control=control-expl%C3%ADcito h_01HFKCMH8JG2C43P8QZ0SKZCBB=control-expl%C3%ADcito h_01HFKCMH8J9XDX87ES4F5WW4GJ=implement-a-content-security-policy-csp-policy content-security-policy-csp=pol%C3%ADtica-de-seguridad-de-contenido-csp h_01KGJCGCQ0QB7NK6YNZT5XJVJY=pol%C3%ADtica-de-seguridad-de-contenido-csp advanced-sdk-verification-with-csp-nonce-snippets=advanced-sdk-verification-con-fragmentos-de-csp-nonce h_01KP11XJV88YB2NSBZJTX9K7ZQ=advanced-sdk-verification-con-fragmentos-de-csp-nonce h_01KP3CJBZXQ4D538H0T7N9FZ6Z=nonce-without-smart-banners h_01KP3CJBZX8K3WK6RHQMB029VN=nonce-with-smart-banners h_01HFKCMH8JG40DT9NHXG6TPMJ1=discard-query-params query-discard-options=opciones-de-descarte-de-consultas h_01HFKCMH8JYSV81BEY5XQRZ24Y=opciones-de-descarte-de-consultas principles-of-event-recording=principios-de-registro-de-eventos h_01HFKCMH8JZCKH1JPTGBVJ3QP4=principios-de-registro-de-eventos h_01HFKCMH8JEDEDC48AH5A2797D=conversion-and-standard-events conversion-events=eventos-de-conversi%C3%B3n h_01HFKCMH8JYYB7HG2W8XQ7RFPD=eventos-de-conversi%C3%B3n standard-events=eventos-est%C3%A1ndar h_01HFKCMH8JQHSJF3T8SF4ZES7W=eventos-est%C3%A1ndar recording-events=registro-de-eventos h_01HFKCMH8J79VD5BX96ANAYAFQ=registro-de-eventos h_01HFKCMH8JPJZQ81TYZX5PDF91=identifying-users-using-customer-user-id-cuid h_01HFKCMH8JYPNHJGYVRK1SZFYB=web-sdk-event-parameters h_01HFKCMH8J35YT2448PX8ZRM5P=recording-event-scenarios online-store=tienda-en-l%C3%ADnea h_01HFKCMH8JQS3CTE6NTZY4G8ZR=tienda-en-l%C3%ADnea h_01HFKCMH8J1EDH3XM5V4ECYCPS=ensuring-that-events-are-sent examples=ejemplos h_01HFKCMH8J4KQSZ489TMDEN426=ejemplos h_01HFKCMH8JAK25DZ1BZDFS4THD=recording-events::f1e16eae h_01HFKCMH8J4XNY5B9MKAS81T6Z=setting-customer-user-id-after-signup addtional-information=informaci%C3%B3n-adicional h_01HFKCMH8KJDZ0A15RMQ8BDMDH=informaci%C3%B3n-adicional h_01HFKCMH8KV3QD9CPBSVWM3EVE=web-sdk-cookies h_01HFKCMH8KGJTE7BMK4VSQJF33=release-notes h_01HFKCMH8KP1SHA21JZA5PTZXG=deprecations" />
