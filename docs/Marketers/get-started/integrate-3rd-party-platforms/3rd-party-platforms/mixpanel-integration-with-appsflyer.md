---
title: Integración de Mixpanel con AppsFlyer
metadata:
  keywords:
    - Attribution
    - Mixpanel
    - SDK
    - integrated partner
    - Advertisers
    - Ad Networks
    - facebook mixpabel
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2015-12-24T11:33:01Z'
  edited_at: '2026-08-12T11:59:18Z'
  id: 207447103
  locale: es
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/es/articles/207447103
---
> **De un vistazo:** Aprende a compartir automáticamente datos de AppsFlyer con Mixpanel, una plataforma de análisis de productos.

<Image align="center" alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/mixpanel.png" />

La integración entre AppsFlyer y Mixpanel te permite importar la información de la campaña de adquisición de AppsFlyer a Mixpanel.

<div id="important" />

> 🚧 **¡Importante!**
>
> <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions#restricciones-de-fuente-de-medios">Algunas fuentes de medios</Anchor> restringen el intercambio de datos con terceros. Por lo tanto, los postbacks para eventos restringidos no se enviarán a este partner, independientemente de la selección configurada para enviar postbacks.

<div id="setting-up-mixpanel" />

## Configuración de Mixpanel

**Requisito previo:** Antes de configurar la integración, asegúrate de [ponerte en contacto con el partner](#) y abrir una cuenta con ellos. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Para activar o editar la integración:**

1. **Para activarla:** En AppsFlyer, en el menú lateral, selecciona**Colaborar** > **Partner Marketplace**.  
   **Para editarla**: En AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Integraciones activas**.
2. Selecciona la aplicación correspondiente.
3. Busca al partner (`rokuads_int`) y selecciónalo.
4. En la pestaña **Integración**, selecciona la aplicación para la integración y activa **Activar partner**.  
    **Nota:** El conmutador debe permanecer ON (activado) mientras trabajes con el partner. **Nota:** El selector debe permanecer <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activado</Anchor> mientras trabajes con el partner.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Para ver una descripción detallada del encabezado de la ventana de configuración del partner, haz clic <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aquí</Anchor>.

<div id="integration-tab" />

<Accordion title="Pestaña Integración">

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

<div id="general-settings" />

### Configuración general

<Image align="center" alt="mixpanel-general-settings.png" src="https://files.readme.io/df1b95eb3926aa7e10db338f156a87b88aabda6b97a4d28db2953e9e48a114e6-360017400598.png" width="542px" />

* **Residencia de datos en la UE**: AppsFlyer envía datos a los servidores estadounidenses de Mixpanel por defecto. Para enviar los datos a los servidores de Mixpanel en la UE, activa este selector.  
  **\*token**: Mixpanel se conecta con AppsFlyer a través de un Token único. Si aún no lo tienes, debes obtenerlo de Mixpanel para continuar con la integración.

  **Para obtener el Token de Mixpanel:**

  1. Accede a tu cuenta de Mixpanel en: https://mixpanel.com/login/
  2. En **Mixpanel**, ve al panel **Analysis** y haz clic en el icono de engranaje.

     <Image align="center" alt="mixpanel-token-1.png" src="https://files.readme.io/f1fbc76fff621e12a7d91fed5ba49eb20f2b049de65c70b0ab32cadd997287d2-small-360014578477.png" />
  3. Copia tu token de la sección Access Keys de tu proyecto y pégalo en el campo **token** de la pestaña de integración de Mixpanel de AppsFlyer.

     <Image align="center" alt="mixpanel-token-2.png" src="https://files.readme.io/e8e633ec87d963244652a53b9b21c495b0a850e234621a44d93b3034c640bff7-360014578757.png" />
* **Enviar ID de anunciante**:
  * Si utilizas el parámetro customer\_user\_id de AppsFlyer, se enviará a Mixpanel con cada instalación (deja desactivado **Enviar ID de anunciante**).
  * Si no estás utilizando customer\_user\_id de AppsFlyer: activa **Enviar ID de anunciante.** El ID del dispositivo se envía a Mixpanel como customer\_user\_id (unique\_id en Mixpanel).  
    Aprender más sobre la guía de integración del SDK de AppsFlyer para <Anchor target="_blank" href="/marketers/es/docs/sdk-integration-overview">Android</Anchor> e <Anchor target="_blank" href="/marketers/es/docs/sdk-integration-overview">iOS</Anchor>.
* **Eventos:** Activa esta opción para enviar los datos de instalación al punto de conexión de eventos de Mixpanel.
* **Personas:** Activa esta opción para enviar los datos de instalación al punto de conexión de personas de Mixpanel.

  <div id="note" />

  > 📘 **Nota**
  >
  > Para que los postbacks de instalación se envíen a Mixpanel, al menos uno de los dos puntos de conexión, **Eventos** o **Personas**, debe estar activado.

* **Uso compartido de datos avanzado:** Activa esta opción para enviar información adicional a Mixpanel: c (campaña), red (pid), impression\_based (is-impression).

<div id="default-postbacks" />

### Postbacks predeterminados

AppsFlyer puede enviar postbacks automáticos a Mixpanel tras las instalaciones de los usuarios. Utiliza esta sección para definir la fuente de los usuarios a los cuales se envían los postbacks de cada evento. Aprender más sobre los <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#default-postbacks">postbacks por defecto</Anchor>.

<Image align="center" alt="" src="https://files.readme.io/6cf4f0e1b73c634c5fbe8f79e654ff3a3cd318bdca51d5e6b17933c307eb769d-36693858465809.png" />

<div id="in-app-events-settings" />

### Configuración de eventos in-app

<Image align="center" alt="mixpanel-in-app-events-settings.png" src="https://files.readme.io/db5e4e6d5bbe084a94b90425d49345511c214ddc39380a2b8419659ad752cdb2-360014576637.png" />

En esta sección, debes asignar los eventos de AppsFlyer a Mixpanel mediante postbacks.

<div id="note-1" />

> 📘 **Nota**
>
> Mixpanel captura eventos in-app usando su propio SDK. El único evento que se puede enviar a Mixpanel y que no es capturado por ellos es af\_uninstall.

Aprender más sobre los <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">postbacks de eventos in-app</Anchor>.

**Para configurar postbacks de eventos in-app:**

1. Introduce el token de Mixpanel.
2. Habilita los postbacks de eventos in-app.
3. **Para enviar el ID del anunciante de la desinstalación**, activa **Enviar ID de anunciante**.
4. **Para enviar información adicional para la desinstalación**, activa **Uso compartido de datos avanzado**.
5. Haz clic en **Agregar evento** para agregar un evento del SDK a la lista.
6. Selecciona **af\_uninstall** en el menú desplegable.
7. Selecciona el **Identificador de evento de partner** correspondiente en el menú desplegable.
8. Selecciona la opción requerida en el menú desplegable Enviar ingresos:
   * **Sin valores ni ingresos:** envía solo el evento en sí sin el valor del evento.
   * **Con valores y sin ingresos:** envía todos los parámetros, excepto el valor de ingresos.
   * **Con valores e ingresos**: envía todos los parámetros del evento, incluido el valor de ingresos (si existe en el evento).
9. Para completar la configuración de la integración, haz clic en **Guardar integración**.

Una vez guardada la integración, AppsFlyer envía los siguientes datos a Mixpanel por cada instalación orgánica y no orgánica:

* Parámetro token de Mixpanel
* Customer\_user\_id o ID de dispositivo (IDFA/ID de publicidad de Google)
* Fuente de medios
* Nombre de la campaña

**Nota**: El CUID no se envía en los postbacks de desinstalaciones.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Los enlaces de atribución no están disponibles para este partner.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costo">

Los datos de costos no son compatibles con la integración con este partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de ingresos por publicidad">

Los ingresos por publicidad no se admiten en la integración con este partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

Los permisos no están disponibles para este partner.

</Accordion>

<div id="integrating-with-mixpanel-when-using-a-login-mechanism" />

## Integración con Mixpanel al utilizar un mecanismo de inicio de sesión

A continuación se muestra un ejemplo de los pasos de integración:

1. La aplicación ha sido iniciada (abierta) por el usuario.
2. El SDK de Mixpanel genera un ID distintivo aleatorio (**distinct\_id**).
3. Obtén el ID distintivo de Mixpanel, y establécelo como el ID de usuario del cliente, utilizando la función del SDK de Appsflyer **setCustomerUserId**.
4. Envía el <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#start">**Inicio**</Anchor>. Esta API permite que AppsFlyer detecte instalaciones, sesiones y actualizaciones.
5. Una vez atribuida la instalación de la aplicación, se envía un evento de **instalación** a Mixpanel con el ID de usuario del cliente, que incluye el ID distintivo de Mixpanel.
6. Cuando el usuario se registra o inicia sesión, se llama al comando de Mixpanel identify() con el identificador de usuario (por ejemplo, correo electrónico o ID de cliente). Esto asignará el ID distintivo aleatorio inicial al ID de usuario registrado.

   <Tabs>
   <Tab title="Android">

   Mixpanel Android - <Anchor target="_blank" href="https://developer.mixpanel.com/docs/android#section-combining-anonymous-and-identifiable-user-data">Combinación de datos de usuarios anónimos e identificables</Anchor>

   ```java
   MixpanelAPI mixpanel = MixpanelAPI.getInstance(context, MIXPANEL_TOKEN);
   mixpanel.identify("user@example.com");

   // Mixpanel v6.2.0 and below should use the following API:
   mixpanel.getPeople().identify(“user@example.com”);
   ```

   </Tab>

   <Tab title="Objective C">

   Mixpanel iOS Objective C - <Anchor target="_blank" href="https://developer.mixpanel.com/docs/ios#section-combining-anonymous-and-identifiable-user-data">Combinación de datos de usuarios anónimos e identificables</Anchor>

   ```objectivec
   [mixpanel identify:@“user@example.com”];
   ```

   </Tab>

   <Tab title="Swift">

   Mixpanel iOS Swift - [Combinación de datos de usuarios anónimos e identificables](https://developer.mixpanel.com/docs/swift#section-combining-anonymous-and-identifiable-user-data)

   ```swift
   mixpanel.identify(“user@example.com”);
   ```

   </Tab>

   <Tab title="Unity">

   Mixpanel Unity - [Combinación de datos de usuarios anónimos e identificables](https://developer.mixpanel.com/docs/unity#section-combining-anonymous-user-data-with-identifiable-user-data)

   ```csharp
   // set customer user id or device id
   Mixpanel.Identify(“user@example.com”);
   ```

   </Tab>
   </Tabs>

7. Mixpanel recibe el customer\_user\_id de AppsFlyer con el alias del ID de usuario (por ejemplo, dirección de correo electrónico).

<div id="note-2" />

> 📘 **Nota**
>
> Si no estás utilizando ningún proceso de registro dentro de tu aplicación, implementa los pasos 1-3 como se ha descrito anteriormente.

<div id="viewing-appsflyer-data-in-mixpanel" />

## Visualización de los datos de AppsFlyer en Mixpanel

Las siguientes capturas de pantalla son un reporte de embudo para ver la conversión desde la instalación hasta el evento de valor, desglosado por la fuente de medios. Además, se puede ver el tiempo de conversión de cada fuente de medios.

<Image align="center" alt="" src="https://files.readme.io/fdffbe0a2f29c8a8b02b600966583cdeb4917bb48f0502e9b00ef39daa2fa835-9646475113361.png" />

<Image align="center" alt="" src="https://files.readme.io/043a96a00e46a3daaef2b9fa4d58d252391ca2bb14307437f28c447d96ae97d6-9646475229841.png" />

<div data-zendesk-anchors="h_01H9FKEWTEN4F8FM5C9A9ES6HN=importante setting-up-mixpanel=configuraci%C3%B3n-de-mixpanel h_01H9FKEWTEGMEVH3SK739DD719=configuraci%C3%B3n-de-mixpanel h_01H9FKEWTE90WR75PMNN93JAXE=integration-tab general-settings=configuraci%C3%B3n-general h_01H9FKEWTEMT7VGTTFWFMJHYA8=configuraci%C3%B3n-general h_01H9FKEWTEV3RWKMWZN0EXFFNP=nota default-postbacks=postbacks-predeterminados h_01H9FKEWTER31RXAH216TRXQPM=postbacks-predeterminados inapp-events-settings=configuraci%C3%B3n-de-eventos-in-app h_01H9FKEWTERRVKPQFF1B8QQERE=configuraci%C3%B3n-de-eventos-in-app h_01H9FKEWTEEMMQ0KKRZXRJRE25=nota-1 h_01H9FKEWTEEQ0GHF87V20TX9W0=attribution-link-tab h_01H9FKEWTEJ61197SN3R6JXYCP=cost-tab h_01H9FKEWTEA7GN2HHK3QD62A3A=ad-revenue-tab h_01H9FKEWTET4QD1RE0HJZM64D4=permissions-tab integrating-with-mixpanel-when-using-a-login-mechanism=integraci%C3%B3n-con-mixpanel-al-utilizar-un-mecanismo-de-inicio-de-sesi%C3%B3n h_01H9FKEWTE9DEANTXKPD286GD2=integraci%C3%B3n-con-mixpanel-al-utilizar-un-mecanismo-de-inicio-de-sesi%C3%B3n h_01H9FKEWTFZ107Y999WEMB3409=nota-2 viewing-appsflyer-data-in-mixpanel=visualizaci%C3%B3n-de-los-datos-de-appsflyer-en-mixpanel h_01H9FKEWTF9PFNVHTZGDKBX75Y=visualizaci%C3%B3n-de-los-datos-de-appsflyer-en-mixpanel" />
