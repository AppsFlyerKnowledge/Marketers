---
title: 'Google Ads (AdWords): Configuración de integración para anunciantes'
metadata:
  keywords:
    - Integration
    - Google AdWords
    - Configuration
    - google
    - migration
    - Advertisers
    - google ads configuration
    - ads
    - google ads
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2017-05-17T19:16:15Z'
  edited_at: '2026-11-02T01:14:23Z'
  id: 115002504686
  locale: es
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/es/articles/115002504686
---
> **At a glance:** Integra tu cuenta de Google Ads con AppsFlyer para mostrar los datos de atribución de todas tus campañas.

Configura la integración de Google Ads en AppsFlyer para medir y atribuir instalaciones y eventos in-app de tus campañas de Google Ads. En AppsFlyer, esta integración se llama `googleadwords_int`, y los resultados de atribución se informan bajo la fuente de medios `googleadwords_int`.

<div id="google-ads-attribution-flow-with-advanced-data-sharing" />

## Flujo de atribución de Google Ads con intercambio avanzado de datos

![Google ads attribution flow.png](https://files.readme.io/1c49e06e48658a8cb60ae6a9e9a83c0fad751766f3d4ce9c6afdd041fb5e8579-small-38644882427537.png)

1. AppsFlyer envía eventos de instalación a Google, como de costumbre. Si **Advanced Data Sharing** está ACTIVADA, las instalaciones se envían con o sin un ID de dispositivo. Si está DESACTIVADA, las instalaciones se envían **solo cuando hay un ID de dispositivo presente**.
2. Google intenta reclamar la instalación ya sea a través de una reclamación determinista (coincidencia de ID, utilizando el ID de dispositivo si está disponible) o una reclamación no determinista (cuando el ID de dispositivo no está disponible), utilizando modelado probabilístico.
3. En ambos casos, Google responde a AppsFlyer con una reclamación, ya sea determinista o no determinista.
4. AppsFlyer valida la reclamación no determinista utilizando su propio modelado probabilístico. Solo se aceptan reclamaciones validadas.
5. Después de la validación, la reclamación de Google (si se acepta) pasa al paso de decisión de atribución, donde AppsFlyer la compara con otros posibles candidatos de atribución (por ejemplo, otras SRN, redes basadas en clics, orgánico). La instalación se atribuye a la fuente ganadora basada en la lógica de atribución y las reglas de prioridad de AppsFlyer.
6. Si la reclamación es aceptada y seleccionada como el candidato ganador, la instalación se atribuye a Google. En los reportes de raw data, las reclamaciones deterministas mostrarán un <Anchor target="_blank" href="/marketers/es/docs/raw-data-field-dictionary#attribution::cecc12c5">match\_type</Anchor> de `srn`, mientras que las reclamaciones no deterministas mostrarán un tipo de coincidencia de “`probabilistic`”.

<div id="configuring-google-ads-attribution-for-advertisers" />

## Configuración de la atribución de Google Ads para anunciantes

Para comenzar a atribuir campañas de Google Ads con AppsFlyer, sigue estos pasos:

<Accordion title="Paso 1: Verifica los requisitos previos de ICM">

Asegúrate de que se cumplan los requisitos a continuación para soportar las reclamaciones de instalación de Google PMOD en iOS a través de AppsFlyer. Esto es necesario para habilitar On-Device Measurement (ODM) de Google. No se necesita actualización del SDK para Android.

1. [Actualiza el SDK de iOS de AppsFlyer](https://dev.appsflyer.com/hc/docs/install-ios-sdk) a **v6.17.7 o superior** (no se requiere configuración adicional del SDK).
2. Para la actualización del SDK de Google, uno de los siguientes:
   * **SDK de Firebase iOS de Google** **v11.14.0 o superior.** Para más información, consulta la [documentación de Google](https://github.com/firebase/firebase-ios-sdk/releases). **O**
   * **SDK independiente de Google ODM**. Para más información, consulta la [documentación de Firebase.](https://support.google.com/google-ads/answer/16384720).
3. Asegúrate de que el <Anchor target="_blank" href="/marketers/es/docs/appsflyer-knowledge-base-glossary#idfv">IDFV</Anchor> se envíe a AppsFlyer con cada apertura de la aplicación o evento in-app
4. Asegúrate de que la dirección IP se envíe a AppsFlyer con cada evento de apertura de la aplicación. Cuando se configura el enmascaramiento de IP para la aplicación, ICM puede no funcionar.

</Accordion>

<Accordion title="Paso 2: Crear el ID de enlace de Google Ads (obligatorio)">

Para crear un ID de enlace se necesita **acceso administrativo de Google** a la cuenta. Sigue los pasos a continuación o <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7365001?hl=en">la documentación de Google</Anchor>.

1. Inicia sesión en tu cuenta de administrador de Google Ads.
2. Desde el menú superior, haz clic en **Herramientas y configuraciones**.
3. En el menú **Configuración**, selecciona **Administrador de datos** y haz clic en **+ Conectar producto**.
4. En la barra de búsqueda **Fuentes de datos**, escribe "Análisis de aplicaciones de terceros", selecciónalo y haz clic en **Continuar**.
5. Haz clic en **Crear ID de enlace**.
6. Selecciona **AppsFlyer** como tu proveedor de analítica de aplicaciones.
7. Selecciona la plataforma, Android o iOS.
8. Encuentra tu aplicación y selecciónala.
9. Haz clic en **Crear ID de enlace**.

</Accordion>

<Accordion title="Paso 3: Configura Google Ads en AppsFlyer (obligatorio)">

**(Cualquier miembro en la cuenta de AppsFlyer)**

1. En AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Integraciones de partners > la pestaña Marketplace** .
2. Busca **Google Ads**.
3. Haz clic en **Integrate**. Se te dirigirá a la página de configuración de la integración.
4. En la pestaña **Integración**, selecciona **Activar partner**.  
   **Nota:** El conmutador debe permanecer activado (<Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activado</Anchor>) mientras trabajes con el partner<Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">.</Anchor>
5. Pega el **ID de enlace** que has copiado en el paso anterior.
6. Decide si quieres activar o no la opción <Anchor target="_blank" href="/marketers/es/docs/support-google-eu-consent-policy#do-i-have-control-over-consent-data-for-nonue-users">**Usuarios no pertenecientes a la UE**</Anchor>.

   <Image alt="non eu usrs.png" src="https://files.readme.io/fb141c0bd8885facd6574f3e73c5ec8ae8beb596de7fdf3dd8aed9d4e82686dd-22352319155985.png" width="557px" />
7. Activa o desactiva el **uso compartido avanzado de datos.** Cuando está activado, Google Ads recibe postbacks y eventos con identificadores a nivel de dispositivo para todos los dispositivos, incluidos los dispositivos que no han hecho disponible su ID de publicidad (IDFA o ID de publicidad de Google).

   Además, cuando **Advanced Data Sharing** está activado, AppsFlyer atribuye estos eventos. Cuando está desactivado, solo se envían y atribuyen los postbacks y eventos de dispositivos con IDFA.
8. Configuración de la **atribución de instalación**:
   1. <span class="af-ol-a"></span>Define la **ventana de lookback click-through de instalación**.  
      Selecciona las unidades de la ventana de lookback (horas o días) y ajusta el control deslizante al valor que desees. Recomendamos configurar la ventana de lookback en 30 días para alinear con Google Ads.
   2. [Opcional] Si realizas campañas de preinscripción para aplicaciones Android, configura la **ventana de lookback de la campaña de preinscripción** (el valor por defecto es de 90 días). Este control deslizante define la ventana de lookback para atribuir instalaciones a campañas de preinscripción.
   3. Activa la **atribución view-through de instalación.**
   4. Selecciona las unidades de la ventana de lookback (horas o días) y ajusta el control deslizante al valor que desees. Recomendamos configurar la ventana de lookback view-through en 1 día para alinearse con Google Ads.  
      **Nota:** Google no envía datos de reclamación para impresiones en aplicaciones iOS. El interruptor de atribución view-through de instalación y el control deslizante de la ventana de lookback ya no son relevantes para aplicaciones iOS.

      ![](https://files.readme.io/a6f05b9f92abf6dfdbaafc248c0381bfe063086daa10727dc088d484c1b38f0b-30759221879825.png)
9. El selector de **Atribución de reinstalaciones** está activado de forma predeterminada para las nuevas integraciones. La atribución de reinstalaciones te permite medir a los usuarios que reinstalan tu app durante su ventana de reatribución.

   No es necesario configurar una ventana de lookback independiente, ya que la atribución de reinstalaciones utiliza los valores definidos en la configuración de atribución de instalaciones. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/measure-reinstalls">Medir reinstalaciones</Anchor>.

   <div id="important" />

   > 🚧 **¡Importante!**
   >
   > Los datos de conversión de reinstalación se **muestran como un inicio de sesión** en el dashboard de Google Ads. En AppsFlyer, se considera y se atribuye como una reatribución.

10. Configura la **atribución de reengagement**:
    1. <Anchor target="_blank" href="/marketers/es/docs/app-settings#reengagement-attribution">Habilita el retargeting en Configuración de la app</Anchor>.
    2. Habilita la atribución de reengagement en la configuración de integración de Google Ads.
    3. Define la **ventana de lookback click-through de reengagement**, que es el tiempo a partir de un clic en un anuncio, durante el cual la app debe ser abierta para que el clic se registre como un reengagement. Selecciona una ventana de lookback en horas o días y ajusta el control deslizante al valor que desees.
    4. Activa la **atribución view-through por reengagement**.  
       **Nota:** Google no envía datos de reclamación para impresiones en aplicaciones iOS. El interruptor de atribución view-through de instalación y el control deslizante de la ventana de lookback ya no son relevantes para aplicaciones iOS.
    5. Define la **ventana de lookback view-through por reengagement**, que es el período desde una impresión de anuncio, durante el cual la app debe ser iniciada para que la impresión se registre como un reengagement. Selecciona una ventana de lookback en horas o días y ajusta el control deslizante al valor que desees.
    6. Define la **ventana de reengagement**. Este es el período en el que los eventos in-app del usuario se atribuyen a la fuente de medios de retargeting, ya sea tras un clic o una impresión. Puedes establecer el valor en días (1-90), horas (hasta 23) o incluso para siempre. El valor por defecto es de 30 días.

       ![](https://files.readme.io/221a5489e91a15f1d9e4db9ab8f7cbff9e47dc1b50b0f7b43323096b26008870-30759261966225.png)
11. Si tienes un <Anchor target="_blank" href="https://support.google.com/google-ads/answer/2402582?hl=en">activo de aplicación de Google Ads para iOS</Anchor> (anteriormente conocido como extensión de aplicación):  
    Para obtener atribuciones del enlace del anuncio, accede a la pestaña <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#attribution-link-tab">**Enlace de atribución**</Anchor>, crea un enlace de atribución de plataforma única de AppsFlyer e insértalo en la extensión de la aplicación de Google Ads.  
    **Nota:** Asegúrate de añadir un nombre de campaña estático (obligatorio).

    ![](https://files.readme.io/6b7513829fb3abbaab75942e3612760f39f6ae6502064eac1f31b0783a63e95b-30759221884561.png)
12. Dirígete a la pestaña **Costo**.
13. Activa la opción **Obtener datos de costos, clics e impresiones**.
14. Pulsa el botón **Conectar Google Ads** e inicia sesión en tu cuenta de Google para obtener todos los costos de tus campañas de Google Ads en AppsFlyer. <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-cost-and-ad-revenue">Más detalles aquí</Anchor>.
15. Haz clic en **Guardar**.

<div id="stop" />

> ❗️ **¡Alto!**
>
> * Si necesitas mapear tus eventos in-app a Google Ads, completa primero el [paso 5](#h_01HACTC1H50DDS3WCZ9DCHKN0P).

</Accordion>

<Accordion title="Paso 4: verifica las conversiones de tu aplicación (recomendado)">

<div id="important-1" />

> 🚧 **¡Importante!**
>
> Para que Google Ads registre tus nuevas conversiones, debes **iniciar tu aplicación y realizar los eventos mapeados in-app** al menos una vez. Para probar aplicaciones de iOS, debes recopilar IDFA para visualizar el evento. Puede tardar hasta 6 horas en que las conversiones de eventos se agreguen a la fila. Una vez añadidas, las conversiones nuevas cambian de estado, de «No recent conversion» a «recording conversion».

Este paso requiere el **acceso administrativo de Google** a la cuenta para crear un ID de enlace.

Cuando AppsFlyer envía datos de conversión de cualquier evento que aún no esté configurado en tu cuenta de Google Ads, incluidos `first_open`, `session_start` y tus eventos in-app, Google Ads lo añade automáticamente a la lista de conversiones. Para obtener más información, consulta <Anchor target="_blank" href="https://support.google.com/google-ads/answer/17086025?hl=en">Información sobre las acciones de conversión de aplicaciones habilitadas automáticamente</Anchor>.

**Para verificar las conversiones de tu aplicación:**

1. En Google Ads, ve a la página **Conversiones** > **Resumen**.
2. Asegúrate de que el evento `first_open` aparezca en la lista de eventos de conversión de terceros de todas tus aplicaciones. Este evento es obligatorio para la medición de instalaciones.
3. Si tienes pensado medir el re-engagement con Google, asegúrate de que el evento `session_start` también aparezca en la lista.
4. Asegúrate de que cada evento in-app que quieras medir con Google aparezca en la lista.

**Si falta algún evento, está oculto o se ha eliminado, impórtalo manualmente:**

1. En la página **Conversiones** > **Resumen**, haz clic en **Ver todas las acciones de conversión**. Aparecerá el filtro de **Estado**.
2. Haz clic en **Estado** y selecciona **Todos** para ver todos los eventos, incluidos los deshabilitados y eliminados.
3. Si el evento sigue sin aparecer, impórtalo siguiendo los pasos descritos en la <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7382633?sjid=11699141105296914680-EU">documentación de ayuda de Google Ads</Anchor>.

> 📘 **Nota**
>
> Si el identificador del evento del partner en Google Ads ha cambiado o está etiquetado como PERSONALIZADO, y el nombre del evento correspondiente ha sido modificado en AppsFlyer, será necesario volver a importar los datos.

Asegúrate de que tu configuración de "incluir en conversiones" esté alineada con los objetivos de tu campaña en Google Ads. Para más información, contacta con un representante de Google o consulta la documentación de Google <Anchor target="_blank" href="https://support.google.com/google-ads/answer/4677036?hl=en&co=ADWORDS.IsAWNCustomer=false">aquí</Anchor>.

¡Felicitaciones! ¡Enhorabuena! ¡Ya estás midiendo las campañas móviles de Google Ads con AppsFlyer!

</Accordion>

<Accordion title="Paso 5: Mapea tus eventos in-app (recomendado)">

**(Cualquier miembro afiliado a la cuenta de AppsFlyer)**

![In-app_event_postbacks_es-us.png](https://files.readme.io/fbeef1b9d6f4462750d849878045d31b4a6614a9f36d20cd9c6f69d91a34f65a-30759221886609.png)

1. Ve a la pestaña **Integración** y desplázate hacia abajo hasta la sección de **Postbacks de eventos in-app**.

   <div id="note-1" />

   > 📘 **Nota:**
   >
   > Cuando habilites la asignación de eventos en la aplicación de Google Ads por primera vez :
   >
   > * El evento **af\_app\_opened** se define automáticamente y se asigna a **session\_start** (si no es así, agrégalo manualmente).
   > * En **para usuarios de**, debes seleccionar **Todas las fuentes de medios, incluidas las orgánicas** para cada evento, con el fin de permitir a Google Ads recibir estos eventos. Una vez realizada la integración, podrás cambiar esta selección para cualquier evento.

2. Activa los **postbacks de eventos in-app**.
3. Haz clic en **Agregar evento** para agregar un evento de SDK o de servidor a servidor a la lista.
4. Completa los siguientes parámetros:

| Nombre del parámetro | Descripción |
| --- | --- |
| **Evento de AppsFlyer** | El nombre del evento, tal como lo recibió AppsFlyer, ya sea del SDK integrado en tu aplicación o de los eventos servidor a servidor.<br />**Consejo**: ¿No encuentras el evento que estás buscando?<ul><li>Asegúrate de activar el evento en un dispositivo con una instalación no orgánica y vuelve a verificar.</li><li>Escríbelo en **Evento de AppsFlyer** y, a continuación, haz clic en **Crear personalizado**. Obtén más información sobre la <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#eventos-personalizados">asignación de eventos personalizados</Anchor>.</li></ul> |
| **Asignado al evento asociado** | El nombre o ID único de cada evento, tal como se define en Google Ads. Seleccione el evento predefinido más adecuado de AppsFlyer en el menú desplegable. |
| **para usuarios de** | Selecciona la opción de envío para el evento:<ul><li>**Solo este partner**: Envía postbacks únicamente cuando este evento se atribuye a Google Ads.</li><li>**Todas las fuentes de medios, incluidas las orgánicas** Envía postbacks para eventos atribuidos a cualquier partner y eventos orgánicos.</li></ul> |
| **incluyendo** | <ul><li>**Sin datos (predeterminado)**: Envía solo el evento sin el valor del mismo.</li><li>**Valores e ingresos**: Envía todos los parámetros del evento, **incluido** el valor de ingresos (si está presente en el evento).</li><li>**Valores sin ingresos**: Envía todos los parámetros **excepto** el valor de los ingresos.</li></ul> |

5. Haz clic en **Guardar integración**.
6. Después de guardar la integración, mientras sigues en la página de configuración, puedes integrar más aplicaciones con el partner.
   1. Desde la esquina superior izquierda, bajo el nombre del partner, haz clic en el nombre de la aplicación para abrir la lista de aplicaciones.
   2. Selecciona una aplicación diferente en la lista desplegable.
   3. Repite los pasos de integración para la aplicación seleccionada.

</Accordion>

<div id="tip" />

> 👍 **Consejo**
>
> La integración de la API de Google Ads incluye automáticamente la función de remarketing de Google Ads. Completando esta integración y enviando eventos a Google Ads, podrás crear listas de audiencia de remarketing en Google Ads sin necesidad de integraciones adicionales.

<div id="granting-permissions-to-google-ads-team-members" />

## Concesión de permisos a los miembros del equipo de Google Ads

Puedes otorgar a Google Ads <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos para acceder a ciertos datos de tu cuenta.</Anchor> Esto se puede hacer en la página de configuración de Google Ads, en la pestaña Permisos para cada una de tus aplicaciones.

Para obtener estos permisos y acceder a tu aplicación, tu representante de Google Ads debe ser miembro del equipo de la cuenta de partner de Google Ads en Appsflyer.

Debido a los requisitos de privacidad de Google, Google solo puede añadir nuevos miembros al equipo en su cuenta de partner de AppsFlyer cuando un anunciante lo solicita explícitamente.

Para otorgar acceso a tu aplicación a un miembro del equipo de Google Ads, haz lo siguiente:

1. Completa y envía <Anchor target="_blank" href="https://docs.google.com/forms/d/e/1FAIpQLSfJmwEPxy4bXw0mEsKfJ3D5dZmRZgHS3LCiyoEFsZRos0jWIQ/viewform">este formulario</Anchor> para solicitar que tu administrador de cuenta sea añadido a la cuenta de partner de Google en AppsFlyer.
2. Espera la confirmación de Google Ads de que tu administrador de cuenta de GA ha sido añadido.
3. Dirígete a **Configuración** > **Integraciones Activas** > **Google Ads** > **Permisos** y añade el correo electrónico de tu administrador de cuenta a la lista de miembros del equipo.
4. Activa los permisos que quieres otorgar a tu administrador de cuentas de Google Ads.

Lee más sobre <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">cómo proporcionar permisos a ad networks</Anchor>.

<div id="enabling-google-ads-attribution-for-agencies" />

## Activación de la atribución de Google Ads para agencias

AppsFlyer admite configuraciones de agencias con Google Ads. Es fundamental que el anunciante y la agencia tengan cuentas de Google Ads separadas para que AppsFlyer pueda atribuir correctamente los datos. Para obtener más detalles, haz clic <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-integration-setup-for-agencies">aquí</Anchor>.

<div id="running-with-multiple-google-ads-accounts" />

## Operar con múltiples cuentas de Google Ads

AppsFlyer permite trabajar con varias cuentas de Google Ads para la misma aplicación. Esto se logra compartiendo el ID de enlace en Google Ads e importando los eventos a cada cuenta de Google Ads.

Para más detalles sobre cómo compartir tu ID de enlace de Google Ads, haz clic <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7365001">aquí</Anchor>.

<div id="ios-app-campaigns" />

## campañas de aplicaciones para iOS

**Nota**: Esta sección aplica a las campañas de aplicaciones para instalaciones y **no** a las campañas para interacción.

El 27 de enero de 2021, <Anchor target="_blank" href="https://blog.google/products/ads-commerce/preparing-developers-and-advertisers-for-policy-updates/">Google anunció actualizaciones de políticas</Anchor> para adaptarse al lanzamiento de iOS 14.

Desde el comienzo de la aplicación de la ATT, las aplicaciones de Google en iOS no solicitan la ATT y, por tanto, los productos de Google Ads <Anchor target="_blank" href="https://support.google.com/google-ads/answer/10417364">dejaron de usar</Anchor> identificadores de dispositivos (IDFA) sujetos a la ATT, excepto la app de YouTube, que admite la solicitud de la ATT.

Para preservar la generación de reportes y la optimización de campañas, Google amplió las conversiones modeladas al tráfico de iOS 14+.

Dado que las conversiones modeladas no dependen de identificadores de dispositivos, desde el lanzamiento de iOS 14.5, Google utiliza la siguiente lógica para el inventario de campañas de instalación de apps en iOS:

* El inventario de ACI Search de iOS no se atribuye por ID de dispositivo. Esto sigue la política de Google del 24 de enero de 2020.
* El inventario de ACI Display de iOS puede atribuirse cuando hay un ID de dispositivo presente, siempre que tanto la aplicación del anunciante como la aplicación del editor tengan el consentimiento del usuario.
* Cualquier campaña ACI de iOS puede atribuirse a través de ICM. Esto se aplica cuando el ID de dispositivo no está disponible en la aplicación del anunciante, la aplicación del editor o ambas.
* Google actualmente solo reclama clics en iOS. No reclama impresiones.

<div id="using-deferred-deep-linking-in-app-campaigns" />

## Utilizar deferred deep linking en campañas de aplicaciones

**¿Qué es un deep link y cómo funciona?**

Cuando un usuario potencial hace clic en un feed, se lo redirecciona a la página de la aplicación. Una vez que el usuario instala la aplicación y la inicia, el SDK proporciona los detalles específicos del producto (por ejemplo, zapatillas de correr) mediante Deferred deep linking. El desarrollador de la aplicación utiliza estos datos para ofrecer la experiencia de usuario relevante dentro de la app.

**Deferred deep linking en Google**

Los <Anchor target="_blank" href="https://support.google.com/google-ads/answer/9959794?hl=en&ref_topic=10011599">feeds de Google en campañas de aplicaciones</Anchor> o los <Anchor target="_blank" href="https://support.google.com/google-ads/answer/12373847?">deferred deep linking a nivel de grupo de anuncios</Anchor> te permiten ofrecer una experiencia de contenido fluida y personalizada para nuevos usuarios móviles. Google permite configurar deep links tanto en el feed como en el grupo de anuncios, y AppsFlyer admite ambos casos para deferred deep linking.

**Para activar los deferred deep linking con Google Ads:**

1. Asegúrate de utilizar <Anchor target="_blank" href="/marketers/es/docs/conversion-data-payloads-and-scenarios#reatribución-con-enlaces-profundos-diferidos">GCD</Anchor> para recibir el parámetro <Anchor target="_blank" href="/marketers/es/docs/conversion-data-payloads-and-scenarios#reatribución-con-enlaces-profundos-diferidos">en el SDK de AppsFlyer.</Anchor>
2. En Google, <Anchor target="_blank" href="https://support.google.com/google-ads/answer/9958973?hl=en&ref_topic=10011599">configura los feeds</Anchor> o <Anchor target="_blank" href="https://support.google.com/google-ads/answer/12373847?">establece deferred deep linking a nivel del grupo de anuncios</Anchor>.
3. En AppsFlyer, ve a **Configuración** > **Integraciones Activas**. Selecciona **Google Ads (Adwords)**.
4. En la pestaña **Integración**, activa la opción **Deferred deep linking con Google Ads.**
5. Haz clic en **Guardar integración**.

<div id="note-2" />

> 📘 **Note**
>
> El valor del deeplink diferido de Google Ads solo lo devuelve Google para coincidencias deterministas, basadas en el ID de dispositivo, y no es compatible con coincidencias probabilísticas (ICM).

<div id="google-ads-parameter-mapping" />

## Asignación de parámetros de Google Ads

La siguiente tabla describe la asignación de parámetros entre Google Ads y AppsFlyer. Ten en cuenta que los anunciantes no pueden agregar parámetros personalizados a ninguna campaña de Google Ads.

| **Tipo de red** | **Búsqueda** | **Visualización** | **YouTube** |
| --- | --- | --- | --- |
| Canal (`af_channel`) | Consulta la tabla a continuación, [Cómo completar el parámetro `Canal`](/docs/google-ads-adwords-integration-setup-for-advertisers#rellenar-el-parámetro-channel). |  |  |
| Campaña (`c`) | Sí | Sí | Sí |
| ID de campaña (`af_c_id`) | Sí | Sí | Sí |
| Adset (`af_adset`)  <br />Se completa mediante el parámetro `ad_group_name`.  <br />Si este parámetro es null, AF completa `af_adset` con `ad_group_id`. | Sí | Sí | Sí |
| ID del adset (`af_adset_id`) completado por el parámetro `ad_group_id` de Google. | Sí | Sí | Sí |
| Anuncio (`af_ad`). | No aplica | N/D | No aplica |
| ID del anuncio (`af_ad_id`)  <br />Completado por el parámetro `creative_id` de Google. | Sí | Sí | Sí |
| Tipo de anuncio (`af_ad_type`) | Sí* | Sí* | Sí* |
| ID de sitio (`af_siteid`) | GoogleSearch/  <br />SearchPartners | N/D | YouTubeVideos/  <br />VideoPartners |
| Palabras clave | No aplica | N/D | No aplica |

<div id="populate-the-channel-parameter" />

### Rellenar el parámetro `Channel`

Google Ads no envía el parámetro `Channel(af_channel)`. AppsFlyer decide cómo completar este parámetro para los tipos de campaña recibidos de Google Ads, siguiendo las siguientes reglas:

<table><thead><tr><th colspan="2">Tipo de campaña <strong>Y</strong> lógica de tipo de red:</th><th rowspan="2"> Parámetro <kbd>Canal</kbd> </th><th rowspan="2">Ejemplo</th></tr><tr><th>tipo_campaña</th><th>tipo_de_red</th></tr></thead><tbody><tr><td> <kbd>ACI</kbd>, <kbd>ACE</kbd>, <kbd>ACPRE</kbd>, <kbd>Compras</kbd> o <kbd>Hotel</kbd> </td><td>Todos los tipos de redes</td><td><kbd>campaign_type_network_type</kbd></td><td>canal = <kbd>ACI_Search</kbd> </td></tr><tr><td><p><strong>No:</strong></p><p><kbd>ACI</kbd>, <kbd>ACE</kbd>, <kbd>ACPRE</kbd>, <kbd>Compras</kbd> o <kbd>Hotel</kbd></p></td><td><kbd>Visualización</kbd></td><td><kbd>network_subtype</kbd></td><td>canal = <kbd>mGDN</kbd> </td></tr><tr><td><p><strong>No:</strong></p><p><kbd>ACI</kbd>, <kbd>ACE</kbd>, <kbd>ACPRE</kbd>, <kbd>Compras</kbd> o <kbd>Hotel</kbd></p></td><td><p><strong>No:</strong></p><p><kbd>Visualización</kbd></p></td><td><kbd>tipo_de_red</kbd></td><td>canal = <kbd>Buscar</kbd> </td></tr></tbody></table>

Para más información sobre los tipos de anuncios disponibles en la respuesta de Google, consulta <Anchor target="_blank" href="https://developers.google.com/app-conversion-tracking/api/request-response-specs">aquí</Anchor>.

<div id="note-3" />

> 📘 **Nota:**
>
> Cuando Google atribuye una instalación mediante atribución probabilística (ICM), Google no comparte `network_type` con AppsFlyer. Como resultado, falta el tipo de red y el valor del canal es `ACI_` (sin sufijo).

<div id="campaign-type-app-campaigns" />

### Tipo de campaña: campañas de aplicaciones

<div id="changes-to-campaign-names-by-google-ads" />

#### Cambios en los nombres de las campañas por Google Ads

| Hasta el 15 de febrero de 2021 | A partir del 23 de febrero de 2021 |
| --- | --- |
| UAC | ACI |
| UACE | ACE |
| UACPre | ACPRE |

**Nota:** El tipo de nombre de campaña se establece según la fecha de clic o impresión, no por la fecha de instalación.

<div id="engaged-view-parameter-in-raw-data-reports" />

### Parámetro de vista comprometida en reportes de raw data

Una vista comprometida es una impresión de un anuncio en video que duró más de 10 segundos. Tiene la misma prioridad de atribución que un clic.  Para Android, las vistas comprometidas se muestran en los reportes de raw data como `engaged_view` bajo los parámetros `Engagement Type` y `Sub Param 5`.   
Las vistas comprometidas se cuentan si ocurren dentro de la ventana de lookback de clics definida en AppsFlyer, con un límite máximo de 3 días.

<div id="important-2" />

> 🚧 **Importante:**
>
> * Google es un SRN (Self Reporting Network). Para más información sobre el flujo de atribución para estas redes, haz clic <Anchor target="_blank" href="/marketers/es/docs/self-reporting-networks-srns">aquí</Anchor>.
> * AppsFlyer puede presentar cualquier información de campaña proporcionada por Google. El tipo de campaña (Búsqueda, Video, Display) y la información asociada es determinada por Google. Para más información, haz clic <Anchor target="_blank" href="https://developers.google.com/app-conversion-tracking/api/request-response-specs">aquí</Anchor>.

<div id="send-complex-in-app-events-to-google-ads" />

## Envía eventos in-app complejos a los anuncios de Google

Para enviar eventos in-app complejos —eventos con varios elementos— a Google Ads, te recomendamos usar el nuevo objeto de evento `af_order_info`. Para obtener más información, consulta <Anchor target="_blank" href="/marketers/es/docs/item-level-order-data-for-ad-networks-af-order-info">Datos de pedidos a nivel de artículo para ad network (af\_order\_info)</Anchor>.

<div id="optimize-google-ads-campaigns-for-conversions-without-device-id" />

## Optimiza las campañas de Google Ads para conversiones sin usar el ID de dispositivo

A partir de iOS14.5+ y Android 12+, Google Ads introdujo varios identificadores. Estos identificadores se utilizan para la atribución determinista de conversiones sin ID de dispositivo:

| Identificador | Disponible desde | Fuente | Sistema operativo | Utilizado para | Granularidad de los datos |
| --- | --- | --- | --- | --- | --- |
| gclid | Diciembre de 2021 | Referencia de Google Play | Android | Instalaciones / reinstalaciones | Nivel de usuario |
| gclid | Diciembre de 2021 | URL de deep link | Android + iOS | Reenganches | Nivel de usuario |
| gbraid | Marzo de 2021 | URL de deep link | apps de iOS, | Reenganches | Agregados |
| odm\_info | Noviembre de 2025 | AppsFlyer SDK / S2S | apps de iOS, | Instalaciones / reinstalaciones | Agregados |

En Google Ads y AppsFlyer, los anunciantes pueden recibir datos a nivel de campaña para tráfico sin identificadores de dispositivo para re-engagements, instalaciones y actividad de reatribución. Sin embargo, los datos a nivel de adset y de anuncio no son compartidos por Google.  
**El anunciante no necesita realizar ninguna acción para habilitar la recepción de estos parámetros.**

<div id="data-visibility-by-operating-system" />

### Visibilidad de datos por sistema operativo

**Aplicaciones de Android:**

En AppsFlyer y Google Ads, los anunciantes pueden recibir datos completos de las campañas para el tráfico sin ID de dispositivo, tanto para instalaciones como para reengagement.

**Aplicaciones iOS:**

En Google Ads y AppsFlyer, los anunciantes pueden recibir datos completos de las campañas para el tráfico sin ID de dispositivo en sus reengagement.

<div id="advertising-without-the-firebase-sdk" />

## Publicidad sin el SDK de Firebase

Cuando realizas campañas en Google Ads sin tener implementado el SDK de Firebase, se aplican las siguientes limitaciones.

| Limitación | Detalles |
| --- | --- |
| tROAS no compatible | La optimización de tROAS (retorno objetivo sobre el gasto publicitario) solo está disponible cuando se utilizan eventos de ingresos del SDK de Firebase. Los eventos de ingresos de AppsFlyer y los de cualquier otro MMP no son elegibles para esta optimización. |
| Exclusión de audiencias no compatible | Los anunciantes solo pueden excluir usuarios de campañas de apps cuando la campaña está optimizada para eventos del SDK de Firebase, no para eventos de MMP. |

<div id="google-probabilistic-attribution-icm-traits-and-limitations" />

## Rasgos y limitaciones de la atribución probabilística de Google (ICM).

| Limitación | Detalles |
| --- | --- |
| Alcance de atribución. | Solo soporta **App Campaigns for Installs (ACI)**. |
| Datos de reclamo incluidos. | Las reclamaciones de Google incluyen (en la mayoría de los casos):<ul><li>**Nombre de la campaña**</li><li>**ID de campaña**</li><li>**Nombre del grupo de anuncios (Adset)**</li><li>**ID del grupo de anuncios (Adset)**</li></ul>No incluye **información del anuncio.** |
| Campo de canal | No se ha proporcionado ningún tipo ni subtipo de red; el campo **Channel** contendrá un valor parcial: `ACI_`  <br />Para obtener más información sobre “Channel” logic, see [How to populate the `Channel` parameter](/docs/google-ads-adwords-integration-setup-for-advertisers#rellenar-el-parámetro-channel). |
| Soporte regional de iOS ODM | **No compatible** en la UE, el Reino Unido y Suiza |
| Aggregated Advance Privacy (AAP) | Cuando el interruptor <Anchor target="_blank" href="/marketers/es/docs/apply-aggregated-advanced-privacy-framework">AAP</Anchor> (Privacidad Avanzada Agregada) está **activado** en la configuración de la aplicación de iOS, los datos atribuidos a Google en los reportes de raw data se muestran como restringidos. Para ver los datos no consentidos de Google, asegúrate de que el interruptor AAP esté **Desactivado**. |
| Tiempo del toque atribuido | La marca de tiempo de las reclamaciones probabilísticas de Google se redondea a intervalos de 15 minutos (00:00, 00:15, 00:30, etc.) |
| Enmascaramiento de IP | El uso del enmascaramiento de IP puede afectar al rendimiento de ICM. Google recomienda desactivar el enmascaramiento de IP, ya que puede afectar a la medición y al rendimiento de Google Ads. Consulta <Anchor target="_blank" href="/marketers/es/docs/apply-ip-masking-to-user-data#enmascaramiento-de-ip">Aplicar el enmascaramiento de IP a los datos de usuario</Anchor>. |
| IDFV | Google requiere enviar <Anchor target="_blank" href="/marketers/es/docs/appsflyer-knowledge-base-glossary#idfv">IDFV</Anchor> (cuando esté disponible) con las instalaciones, las aperturas de la aplicación y los eventos in-app para maximizar el rendimiento de ICM. |

<span id="h_01HDP0SBEE75MAT4A4S9E7Y7FF"></span>**Consulta también:**

* Para más información sobre consideraciones relacionadas con iOS 14, consulta <Anchor target="_blank" href="/marketers/es/docs/get-skan-postback-data-from-google-ads">Interoperabilidad de Google Ads SKAdNetwork con AppsFlyer</Anchor>.

<div data-zendesk-anchors="google-icm-attribution-flow-with-advanced-data-sharing=flujo-de-atribuci%C3%B3n-de-google-ads-con-intercambio-avanzado-de-datos h_01K0VKGRK7XXC4GNF6B9X76M4T=flujo-de-atribuci%C3%B3n-de-google-ads-con-intercambio-avanzado-de-datos configuring-google-ads-attribution-for-advertisers=configuraci%C3%B3n-de-la-atribuci%C3%B3n-de-google-ads-para-anunciantes h_01HACTC1H5MANBCRWYQPNW5CC2=configuraci%C3%B3n-de-la-atribuci%C3%B3n-de-google-ads-para-anunciantes h_01HACTC1H5R995RXYRFQBFHRF1=importante h_01HACTC1H5EFJKV6AXNSTNFZA4=alto h_01HSX7TJC7PQ0ATM1J86Z4HMYJ=importante-1 h_01KA6S8V6CKRATXHZQZ4YN7V9R=nota h_01HACTC1H58WHJDBN2DRQAZKGB=nota-1 h_01HACTC1H5Z3XXS1MGBS4WYJBV=consejo granting-permissions-to-google-ads-team-members=concesi%C3%B3n-de-permisos-a-los-miembros-del-equipo-de-google-ads h_01HACTC1H5PAY95M4H1A6WTSEF=concesi%C3%B3n-de-permisos-a-los-miembros-del-equipo-de-google-ads enabling-google-ads-attribution-for-agencies=activaci%C3%B3n-de-la-atribuci%C3%B3n-de-google-ads-para-agencias h_01HACTC1H5QE93EAYYVVDQV2WC=activaci%C3%B3n-de-la-atribuci%C3%B3n-de-google-ads-para-agencias running-with-multiple-google-ads-accounts=operar-con-m%C3%BAltiples-cuentas-de-google-ads h_01HACTC1H5Z8B15RHQ75HVV2RP=operar-con-m%C3%BAltiples-cuentas-de-google-ads ios-app-campaigns=campa%C3%B1as-de-aplicaciones-para-ios h_01HACTC1H5X567H6A8M3FWCTAN=campa%C3%B1as-de-aplicaciones-para-ios using-deferred-deep-linking-in-app-campaigns=utilizar-deferred-deep-linking-en-campa%C3%B1as-de-aplicaciones h_01HACTC1H57HJZNAGDKSQD6MVC=utilizar-deferred-deep-linking-en-campa%C3%B1as-de-aplicaciones google-ads-parameter-mapping=asignaci%C3%B3n-de-par%C3%A1metros-de-google-ads h_01HACTC1H6P1A2E160Z6GAGZZS=asignaci%C3%B3n-de-par%C3%A1metros-de-google-ads how-to-populate-the-channel-parameter=rellenar-el-par%C3%A1metro-channel h_01HACTC1H6TPTDDFSMPQ9YVMDY=rellenar-el-par%C3%A1metro-channel h_01KEYE1W4VJYXYHY4FP1KN3SP9=nota-2 campaign-type-app-campaigns=tipo-de-campa%C3%B1a-campa%C3%B1as-de-aplicaciones h_01HACTC1H6CEGD2E3HXHWFWBRB=tipo-de-campa%C3%B1a-campa%C3%B1as-de-aplicaciones changes-to-campaign-names-by-google-ads=cambios-en-los-nombres-de-las-campa%C3%B1as-por-google-ads h_01HACTC1H6A028HKVXJ66MCF6M=cambios-en-los-nombres-de-las-campa%C3%B1as-por-google-ads engaged-view-parameter-in-raw-data-reports=par%C3%A1metro-de-vista-comprometida-en-reportes-de-raw-data h_01HACTC1H6Q6WCTK4Z9RGV6PA4=par%C3%A1metro-de-vista-comprometida-en-reportes-de-raw-data h_01HACTC1H62HC36C08ZBFZ05XS=importante-2 h_01M20SN9DCHRQP8TD5Q2Z00CWQ=env%C3%ADa-eventos-in-app-complejos-a-los-anuncios-de-google optimize-google-ads-campaigns-for-conversions-without-device-id=optimiza-las-campa%C3%B1as-de-google-ads-para-conversiones-sin-usar-el-id-de-dispositivo h_01HACTC1H6EFDVN9N89Y17HDFR=optimiza-las-campa%C3%B1as-de-google-ads-para-conversiones-sin-usar-el-id-de-dispositivo data-visibility-by-operating-system=visibilidad-de-datos-por-sistema-operativo h_01HACTC1H6WZNMVJK479M5KJYF=visibilidad-de-datos-por-sistema-operativo h_01_advertising-without-firebase-sdk=publicidad-sin-el-sdk-de-firebase advertising-without-the-firebase-sdk=publicidad-sin-el-sdk-de-firebase google-icm-traits-and-limitations=rasgos-y-limitaciones-de-la-atribuci%C3%B3n-probabil%C3%ADstica-de-google-icm h_01K0XMCXSS5MKY90DZWJTNVBBS=rasgos-y-limitaciones-de-la-atribuci%C3%B3n-probabil%C3%ADstica-de-google-icm" />
