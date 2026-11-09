---
title: Pruebas de integración de SDK para marketers
metadata:
  keywords:
    - Testing
    - SDK
    - Advertisers
    - Debug
    - Debugging
    - redirects test
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2018-11-12T14:15:08Z'
  edited_at: '2026-08-22T00:15:13Z'
  id: 360001559405
  locale: es
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/es/articles/360001559405
---
> **At a glance:** Prueba la integración de tu aplicación Android o iOS con AppsFlyer.

<div id="overview" />

## Visión general

Una vez completada la integración del SDK, puedes verificar que el SDK se esté comunicando correctamente con los servidores de AppsFlyer. Los marketers pueden elegir entre dos métodos de prueba:

* Pruebas utilizando la página de **Prueba de Integración del SDK** que te permite:
  * <Image alt="" src="https://files.readme.io/16b90e430d7beea0eaa1530130d094d590c0a202f6c6ad298a88aac9508fee7a-31828933593745.png" width="30px" /> [Ver eventos en tiempo real](#view-live-events) a medida que ocurren en tu aplicación probada.
  * [Probar la instalación no orgánica](#h_01HYX9R15931HJEA06SY3K47W5)
  * [Probar deep links (retargeting)](#h_01HYX9R159DDNJW53AWTWT4C2Z)
* [Pruebas utilizando enlaces de atribución.](#pruebas-mediante-enlaces-de-atribución)

Los desarrolladores pueden realizar pruebas de integración en su entorno de desarrollo. Consulta los <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integration-testing">artículos sobre pruebas de integración del Dev Hub</Anchor>.

Las aplicaciones CTV también se pueden probar, consulta [Pruebas CTV](#prueba-ctv).

<div id="testing-using-the-sdk-integration-tests-page" />

## Probando mediante la página de Pruebas de Integración del SDK

Usa la página **Pruebas de integración de SDK** para ver los eventos en vivo en tiempo real, como las instalaciones, los ingresos por publicidad y los eventos in-app, a medida que ocurren en tu aplicación. También puedes probar instalaciones no orgánicas, eventos in-app y deep linking (retargeting), y localizar cualquier problema de integración en tu proyecto. La visualización de eventos en vivo reemplaza la herramienta de prueba de eventos in-app.

> 📘 **Note**
>
> La página de prueba de integración de SDK solo es compatible para aplicaciones iOS que implementan la ATT.
>
> * **iOS:** Asegúrate de que el usuario haya concedido permisos de App Tracking Transparency (ATT) para que se pueda recopilar el IDFA. Puedes probar aplicaciones sin ATT utilizando el procedimiento especificado aquí.
> * **Android:** Aunque el ID de dispositivo (GAID) suele recopilarse automáticamente, te recomendamos verificar que el SDK lo recopile.

<div id="prepare-a-test-device" />

### **Prepara un dispositivo de prueba**

1. Prepara un dispositivo (Android o iOS) que no tenga instalada la aplicación. Si es necesario, desinstala la aplicación del dispositivo.
2. <Anchor target="_blank" href="/marketers/es/docs/registering-test-devices">Registra el dispositivo como un dispositivo de prueba.</Anchor>

<div id="perform-the-integration-tests" />

### Realizar las pruebas de integración

La página de **Pruebas de integración del SDK** proporciona las siguientes tres pruebas:

<Accordion title="Ver eventos en vivo">

Live Event Viewer es una herramienta de prueba que muestra datos en tiempo real enviados desde el SDK a AppsFlyer, como eventos de instalación y otros eventos in-app. Para cada evento capturado, puedes ver el registro y los detalles del evento.

> 📘 **Note**
>
> El Live Events Viewer también admite eventos in-app y sesiones creadas desde un dispositivo de prueba, enviadas a tu servidor e ingeridas en AppsFlyer a través de la API S2S. Asegúrate de que los eventos S2S incluyan el identificador del dispositivo (IDFA para iOS, GAID para Android) del dispositivo de prueba registrado.

**Para ver eventos en el Live Event Viewer:**

1. En AppsFlyer, desde el menú lateral, selecciona **Configuración** > **Pruebas de integración de SDK**.

   <Image align="center" alt="" src="https://files.readme.io/c4f39fb2ddf1de510d9a03e292b05fab444600a8584c0a23e7b3e613c7077799-31828925846033.png" />
2. Haz clic en **Eventos en vivo.**

   <Image align="center" alt="" src="https://files.readme.io/6ec1edba14e51bb27babf80d2d6f4873dbaa5113752217b4fb13399f7a1c61f1-31828925849489.png" />
3. En la lista de la **aplicación**, selecciona la aplicación que deseas probar.
4. En la lista de **dispositivos de prueba,** selecciona el dispositivo que deseas utilizar para probar tu aplicación. Si no tiene un dispositivo de prueba, puedes registrar uno haciendo clic en el enlace **Agregar un dispositivo de prueba**.
5. Haz clic en **Continuar** para comenzar a grabar los eventos de tu aplicación.
6. Abre la aplicación e interactúa con ella para generar sesiones y eventos in-app.

   <Image align="center" alt="" src="https://files.readme.io/72b8822197dc626c1b28a9f8d43bb3c1a91f99e600ae0d8d1f74829bc62dcce6-31828933607313.png" />
7. Haz clic en un elemento de evento para ver los detalles del evento en el panel derecho.
8. Si deseas detener la grabación de los eventos haz clic en **Detener**. Haz clic en **Iniciar** nuevamente cuando desees continuar.

</Accordion>

<Accordion title="Probar instalaciones no orgánicas">

**Para probar instalaciones no orgánicas:**

1. En AppsFlyer, desde el menú lateral, selecciona **Configuración** > **Pruebas de integración de SDK**.

   <Image align="center" alt="" src="https://files.readme.io/c4f39fb2ddf1de510d9a03e292b05fab444600a8584c0a23e7b3e613c7077799-31828925846033.png" />
2. Haz clic en la prueba de**Instalaciones no orgánicas**.

   <Image align="center" alt="" src="https://files.readme.io/34440ab6d328e2d519f759f3c2a1b17dbcbee55af32b47bdbd52bb9f537c6735-31828933612177.png" />
3. En la lista de la **aplicación**, selecciona la aplicación que deseas probar.
4. En la lista de **dispositivos de prueba,** selecciona el dispositivo que deseas utilizar para probar tu aplicación. Si no tiene un dispositivo de prueba, puedes registrar uno haciendo clic en el enlace **Agregar un dispositivo de prueba**.
5. Si la aplicación probada está instalada en tu dispositivo de prueba, debes eliminarla.
6. Selecciona la casilla de verificación **Eliminé la aplicación del dispositivo de prueba**.
7. Haz clic en **Continuar** y sigue los pasos del asistente.

**Si la aplicación no registra una instalación no orgánica, las posibles razones pueden ser:**

* El IDFA está disponible, pero el dispositivo de prueba no se <Anchor target="_blank" href="/marketers/es/docs/registering-test-devices#registro-de-un-dispositivo-de-prueba-ios">registró con este identificador en la página de dispositivos de prueba</Anchor>.
* Tienes más de 1 de tus aplicaciones, además de la aplicación de prueba, instaladas en el dispositivo de prueba, pero el dispositivo de prueba no se <Anchor target="_blank" href="/marketers/es/docs/registering-test-devices#registro-de-un-dispositivo-de-prueba-ios">registró con el IDFV en la página de dispositivos de prueba</Anchor>.
* Se registró una instalación orgánica.
* La prueba se realizó en una versión de la aplicación que no incluye el SDK.

Para errores de integración, comunícate con tu desarrollador.

</Accordion>

<Accordion title="Probar deep links (retargeting)">

**Antes de empezar:**

* Abre la aplicación de prueba al menos 3 veces.
* Para probar deep linking (retargeting), se debes definir OneLink para tu aplicación. Para obtener más información, consulta la <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template">guía de configuración de OneLink</Anchor>.
* Verificar que el <Anchor target="_blank" href="/marketers/es/docs/app-settings#reengagement-attribution">retargeting</Anchor> está encendido.

**Para probar deep links:**

1. En AppsFlyer, desde el menú lateral, selecciona **Configuración** > **Pruebas de integración de SDK**.

   [<Image align="center" alt="Keyboard Maestro Engine 2024-10-06 10.00.47.png" src="https://files.readme.io/c4f39fb2ddf1de510d9a03e292b05fab444600a8584c0a23e7b3e613c7077799-31828925846033.png" width="2895px" />](https://support.appsflyer.com/hc/article_attachments/34207249444753)
2. Haz clic en **Retargeting**.

   <Image align="center" alt="" src="https://files.readme.io/7c5eb6870e8d4c25a817f6c2895163b699e0a4972a6cc675b94396c386288d72-31828925858961.png" />
3. En la lista de la **aplicación**, selecciona la aplicación que deseas probar.
4. En la lista de **dispositivos de prueba,** selecciona el dispositivo que deseas utilizar para probar tu aplicación. Si no tiene un dispositivo de prueba, puedes registrar uno haciendo clic en el enlace **Agregar un dispositivo de prueba**.
5. Haz clic en **Continuar** y sigue los pasos del asistente.

</Accordion>

<div id="testing-using-attribution-links" />

## Pruebas mediante enlaces de atribución

La siguiente sección describe los procedimientos que debes seguir para probar las instalaciones con enlaces de atribución. Puedes realizar estas pruebas incluso si la app aún está pendiente (es decir, no aparece en Google Play Store ni en Apple App Store).

<Accordion title="Probar la atribución de instalaciones">

Probar las instalaciones te permite verificar que el SDK de AppsFlyer atribuya las instalaciones correctamente a varias fuentes de medios.

**Para probar la atribución de instalaciones:**

1. Copia el siguiente enlace (Android o iOS) y realiza estos cambios:

   1. Valor **app\_id** : Añade el ID de tu aplicación en AppsFlyer.
   2. Parámetro **pid** : Especifica el nombre de la fuente de medios a la que se atribuye la instalación.
   3. Parámetro **c**: Especifica el nombre de la campaña.
   4. Si está probando una aplicación disponible a través de una tienda Android de terceros, debes agregar el <Anchor target="_blank" href="/marketers/es/docs/set-up-multi-store-android-attribution#single-dashboard-attribution-links">parámetro af\_r</Anchor> al enlace de atribución.
   5. Reemplaza el GAID, IDFA o IDFV con tu identificador de dispositivo específico.

   <Tabs>
   <Tab title="Android">

   ```
   https://app.appsflyer.com/<app_id>?pid=Test&c=Test&advertising_id=<GAID>
   ```

   </Tab>

   <Tab title="apps de iOS,">

   Identificador de anunciante (IDFA)

   ```
   https://app.appsflyer.com/<app_id>?pid=Test&c=Test&idfa=<IDFA>
   ```

   IDFV

   ```
   https://app.appsflyer.com/<app_id>?pid=Test&c=Test&idfv=<IDFV>
   ```

   </Tab>
   </Tabs>

   Luego, se muestran ejemplos de enlaces de atribución con valores específicos:

   <Tabs>
   <Tab title="Android">

   ```

   ```

   ```
   https://app.appsflyer.com/com.my.app?pid=Test&c=Test&advertising_id=12345f9*-eba*-421*-876*-7654ac67876*
   ```

   </Tab>

   <Tab title="apps de iOS,">

   ```

   ```

   ```
   https://app.appsflyer.com/id123456789?pid=Test&c=Test&idfa=1A2B****-9128-4***-123*-04E***654321
   ```

   </Tab>
   </Tabs>

> 📘 **Note**
>
> Si estás probando una aplicación iOS sin registrar un dispositivo de prueba, tu clic de prueba puede ser marcado como fraudulento por Fraud360.
>
> Para evitar que este evento se detecte como fraude, añade el siguiente parámetro de consulta a tu enlace: pid=ios\_testing

1. Copia el enlace actualizado, envíalo al dispositivo de prueba y, a continuación, haz clic en el enlace.

> 📘 **Note**
>
> En iOS, usa iMessage o el correo electrónico para enviar el enlace al dispositivo. No pegues el enlace en la aplicación Notas de iOS y hagas clic en el enlace. Esta acción puede provocar que el enlace se rompa.

1. Realiza una de las siguientes acciones:

   * Si la aplicación está activa, procede a instalarla.
   * Si la aplicación está pendiente, se muestra el siguiente mensaje: "*La aplicación que estás buscando aún no está disponible en el mercado.*" Este es el resultado esperado. Dado que la aplicación no está activa, el enlace de atribución no conduce a ninguna tienda de aplicaciones. Sin embargo, el enlace de atribución sigue siendo válido para fines de atribución y debes instalar la aplicación de la siguiente manera:
     * **Para Android:** Desde un archivo APK (o Android Studio para desarrolladores)
     * **Para iOS:** Desde TestFlight (o Xcode para desarrolladores)

   Deberías ver una instalación atribuida a la campaña de prueba bajo la fuente de medios llamada **Prueba**. Espere hasta 30 minutos para que la instalación aparezca en el dashboard de la aplicación.

   <Image align="center" alt="Test_Install_Attribution_Link" src="https://files.readme.io/1771da27f7b8c5334d68c3d7c8361e91e0e35a3a08abf60e3d711f83de9ad22d-31828925861265.png" />

> 👍 **Tip**
>
> A continuación se describen formas alternativas de verificar los resultados de las pruebas:
>
> * Si tienes acceso a reportes de raw data, descarga el reporte de raw data de instalaciones. Este reporte tarda varios minutos en descargarse. **Para descargar el reporte:**
>   1. En AppsFlyer, en el menú lateral, selecciona **Reporte** > **Exportación de raw data**.
>   2. En la lista **Adquisición de usuarios (no orgánicos)**, haz clic en **Instalaciones** y luego descarga el reporte.
> * Si tienes acceso a los registros de debug, puedes usar la API de prueba de integración de SDK para recuperar los resultados de atribución de una instalación específica.

</Accordion>

<Accordion title="Probar la atribución de eventos in-app">

Probar eventos in-app te permite verificar que se muestran los ingresos asociados con un evento y que los eventos in-app se atribuyen a la fuente de medios que genera la instalación.

**Para probar la atribución de eventos in-app:**

1. Inicia la aplicación y luego genera algunos eventos in-app.
2. Abre el dashboard de actividades de la aplicación y comprueba que los eventos estén allí.  
   Deberías ver los eventos, los ingresos (si están asociados a los eventos) y la fuente de medios con la cual están relacionados. Es posible que debas esperar hasta 60-70 minutos para que los eventos aparezcan en el dashboard.

**¡Consejo!** Considera descargar el <Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-overview">reporte de raw data de eventos in-app</Anchor> para verificar que los eventos se atribuyan correctamente. Este reporte tarda varios minutos en descargarse.

**Para descargar el reporte:**

1. En AppsFlyer, en el menú lateral, selecciona **Reporte** > **Exportación de Raw Data**.
2. En la sección **Reportes de raw data**, descarga el reporte de raw data de eventos in-app.

</Accordion>

<Accordion title="Probar OneLink">

OneLink te permite definir un enlace de atribución único para Android e iOS. OneLink reconoce el dispositivo del usuario y lo redirecciona a la tienda de aplicaciones correspondiente.

Además, OneLink permite deep linking. Deep linking te permiten abrir la aplicación en una actividad de aplicación específica y al mismo tiempo ofrecer contenido personalizado.

Para obtener más información, consulta nuestra guía sobre <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#testing">pruebas de URL de OneLink</Anchor>.

</Accordion>

<div id="testing-retargeting-using-attribution-links" />

## Cómo probar el retargeting mediante enlaces de atribución

Las siguientes secciones describen los procedimientos que debes seguir para probar la atribución de retargeting.

<Accordion title="Acerca de las pruebas de retargeting">

La atribución de retargeting se produce cuando un usuario se involucra con una campaña de retargeting haciendo clic en un enlace de atribución de retargeting. Esto da como resultado un evento de reatribución o de re-engagement. Para obtener más información, consulta la <Anchor target="_blank" href="/marketers/es/docs/retargeting-attribution-guide">guía de atribución de retargeting</Anchor>.

Las pruebas de retargeting incluyen lo siguiente:

* [**Para la reatribución:**](/docs/testing-the-sdk-integration-for-marketers#test-reattribution) Desinstalar y reinstalar la aplicación. Luego, verificar en el dashboard que se registró una instalación.
* [**Para el re-engagement:**](/docs/testing-the-sdk-integration-for-marketers#test-reengagement) Hacer clic en un enlace de atribución de retargeting o en un deep link y luego verificar que la nueva interacción se atribuya a la fuente de medios correcta.

</Accordion>

<Accordion title="Requisitos previos para ejecutar pruebas de retargeting">

Antes de ejecutar las pruebas de retargeting, se requiere la siguiente configuración:

* El retargeting debe estar activado para la aplicación que estás probando.
* Crea un enlace específico de la aplicación o recupera un enlace personalizado de OneLink. Estos enlaces deben incluir el parámetro de retargeting.

**Para configurar pruebas de retargeting:**

1. Habilita la función de retargeting en la página de configuración de la aplicación.

   En el dashboard de la aplicación, haz clic en **Configuración de la app** y activa **Habilitar atribución de retargeting**.

   <Image align="center" alt="Set_Reattribution_window" src="https://files.readme.io/1fe0c8c4add90c75237b0c5c97b6ff26d8f08ff95bd952912ef746fdec2e9f3d-31828933628561.png" />
2. Realiza una de las siguientes acciones:
   * Crea un enlace de atribución específico para la aplicación. Asegúrate de incluir el parámetro de retargeting, `is_retargeting=true`y el ID de publicidad. Para ver el GAID, IDFA o IDFV, sigue las instrucciones de <Anchor target="_blank" href="/marketers/es/docs/registering-test-devices">Registro de un dispositivo de prueba</Anchor>.   
     El siguiente es un ejemplo de un enlace de atribución que incluye un parámetro específico de Android como el identificador del dispositivo (GAID). Para obtener más información sobre cómo agregar otros parámetros de identificador de dispositivo, como el IDFA o IDFV, consulta <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters#parámetros-específicos-de-ios">Estructura y parámetros de enlaces de atribución</Anchor>.

     ```
     https://app.appsflyer.com/<app_id>?pid=Test&c=Test&is_retargeting=true&advertising_id=<GAID>
     ```
   * Recupera la <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#crear-un-enlace-de-onelink">URL larga del enlace personalizado</Anchor> de una <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#crear-una-plantilla-de-onelink">plantilla de OneLink</Anchor>. Asegúrate de activar la <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">Campaña de retargeting</Anchor>. La siguiente imagen muestra un ejemplo de una URL larga personalizada: ![Testing_LongLink_en-us.png](https://files.readme.io/19c706b0cc11b83a5cb08d51b3418654c6fa1e597ee7ff9e631db21c33c00b82-31828933632401.png)

Ahora puedes seguir probando la reatribución y el reengagement.

</Accordion>

<Accordion title="Probar la reatribución">

**Antes de empezar:**

* Sigue las [instrucciones](/docs/testing-the-sdk-integration-for-marketers#prerequisites-to-run-retargeting-tests) para configurar pruebas de retargeting.
* Asegúrate de que tu dispositivo de prueba **no** esté registrado.

**Para probar la reatribución:**

1. Desinstala la aplicación del dispositivo. Si acabas de instalar la aplicación, espera unos minutos.
2. Copia el [enlace de atribución](/docs/testing-the-sdk-integration-for-marketers#prerequisites-to-run-retargeting-tests) que creaste anteriormente, ya sea el enlace de atribución específico de la aplicación o el enlace largo personalizado de la plantilla de OneLink, envíalo al dispositivo de prueba y luego haz clic en el enlace.

> 📘 **Note**
>
> En iOS, usa iMessage o el correo electrónico para enviar el enlace al dispositivo. No pegues el enlace en la aplicación Notas de iOS y hagas clic en el enlace. Esta acción puede provocar que el enlace se rompa.

1. Realiza una de las siguientes acciones:
   * Si la aplicación está activa, procede a instalarla.
   * Si la aplicación está pendiente, instálala de la siguiente manera:
     * **Para Android**: Instalar desde Android Studio o un archivo APK.
     * **Para iOS:** Instalar desde TestFlight.
2. Abre el dashboard de la aplicación y, en el cuadro **Tipo de vista**, selecciona **Retargeting**.
3. En el cuadro **Tipo de atribución**, selecciona **Reatribuciones**.

   Deberías ver la instalación atribuida a la fuente de medios y la campaña. Es posible que debas esperar hasta 30 minutos para que la instalación con retargeting aparezca en el dashboard.

   <Image align="center" alt="Testing_SDK_Reattribution" src="https://files.readme.io/c5c59709b199262cbefd5cd70ee9fe0db2c788612a8ae6b598c7b2188b696345-small-31828925870609.png" />

> 👍 **Tip**
>
> A continuación se describen formas alternativas de verificar los resultados de las pruebas:
>
> * Si tienes acceso a reportes de raw data, descarga el Reporte de raw data de conversiones. Este reporte tarda varios minutos en descargarse. **Para descargar el reporte:**
>   1. En AppsFlyer, en el menú lateral, selecciona **Reporte** > **Exportación de Raw Data**.
>   2. En la lista **Retargeting**, haz clic en **Conversiones (re-engagements y reatribuciones)** y, a continuación, descarga el reporte.
> * Si tienes acceso a los registros de depuración, puedes usar la API de prueba de integración de SDK para recuperar los resultados de atribución de una instalación específica.

</Accordion>

<Accordion title="Probar el re-engagement">

**Antes de empezar:**

* Sigue las [instrucciones](/docs/testing-the-sdk-integration-for-marketers#prerequisites-to-run-retargeting-tests) para configurar pruebas de retargeting.
* Para fines de prueba, define el tiempo mínimo entre conversiones en **None**. Esto permite que todas las conversiones de reactivación se registren y atribuyan durante las pruebas. ![Testing_Reattribution_window](https://files.readme.io/ec8c7c923093dbed0e99aa5ef57d0239217ead5a9db41f42fe4af8a70eb04551-4406211661841.png)
* Asegúrate de tener la aplicación instalada en tu dispositivo de prueba y de haberla iniciado varias veces. Si acabas de instalar la aplicación, espera unos minutos.

**Para probar el re-engagement (deep linking directos):**

Asegúrate de que tu aplicación esté configurada para <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">deep linking</Anchor> y, luego, sigue <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#testing">este procedimiento</Anchor> para realizar pruebas.

**Para probar el re-engagement (deep linking indirectos):**

1. Copia el [enlace de atribución](/docs/testing-the-sdk-integration-for-marketers#prerequisites-to-run-retargeting-tests) que creaste anteriormente, ya sea el enlace de atribución específico de la aplicación o el enlace largo personalizado de la plantilla de OneLink.
2. Envía el enlace a tu dispositivo de prueba y luego haz clic en el enlace.
3. Para abrir la aplicación, realiza una de las siguientes acciones:

   * En la tienda de aplicaciones, haz clic en **Abrir**.
   * Inicia la aplicación desde tu dispositivo.

   En el dashboard, deberías ver un re-engagement atribuido a la fuente de medios y la campaña. Espera hasta 30 minutos para que aparezca el re-engagement.

   <Image align="center" alt="Testing_SDK_Re-engagement" src="https://files.readme.io/5b64b671c8071f871d9835e8df4d89c18d06c85fe996f7227b6ddf429552fccd-small-31828933643153.png" />

**¡Consejo!** Considera descargar el reporte de raw data de conversiones para verificar que la reactivación se haya atribuido a la fuente de medios correcta. Este reporte tarda varios minutos en descargarse.

**Para descargar el reporte:**

1. En AppsFlyer, en el menú lateral, selecciona **Reporte** > **Exportación de Raw Data**.
2. En la sección **Retargeting**, descarga el reporte de **Conversiones (re-engagements y reatribuciones)**.

</Accordion>

<div id="testing-organic-installs" />

## Pruebas de instalaciones orgánicas

Te recomendamos que comiences probando una instalación orgánica.

**Para probar una instalación orgánica:**

1. Instala la aplicación en un <Anchor target="_blank" href="/marketers/es/docs/registering-test-devices">dispositivo de prueba registrado</Anchor>.
2. Inicia la aplicación.

El dashboard de la aplicación muestra una instalación orgánica nueva. Espera hasta 30 minutos para que aparezca la instalación.

<Image align="center" alt="" src="https://files.readme.io/49c242957324516ba93d6c5ebfa338ec19b05820bcf619d8c39d6f7e4ada9bae-31828925882001.png" />

<div id="testing-ctv" />

## Prueba CTV

Entre los casos de prueba especiales se incluyen los siguientes:

* **Android TV:** El SDK es compatible con smart TVs basados en Android. Un marketer o cualquier miembro del equipo pueden probar estas aplicaciones de TV siguiendo los procedimientos descritos en este artículo.
* **Apple TV (tvOS):** El SDK es compatible con Apple TV (tvOS). Un marketer o cualquier miembro del equipo pueden probar estas aplicaciones de TV siguiendo los procedimientos descritos en este artículo.
* **Aplicaciones tvOS no publicadas:** Requieren que un marketer y un desarrollador trabajen juntos (consulta <Anchor target="_blank" href="/marketers/es/docs/testing-tvos-integration-before-publishing">Probando la integración de tvOS antes de publicar</Anchor>).
* **Amazon Fire TV:** Un marketer puede [probar la integración](/docs/testing-the-sdk-integration-for-marketers#testing-from-the-dashboard) utilizando el método de prueba del SDK de Android en el dashboard de AppsFlyer. (Saber más sobre la <Anchor target="_blank" href="/marketers/es/docs/setting-up-amazon-fire-tv-ad-attribution">atribución de Amazon Fire TV</Anchor>).
* **Eventos web de PBA:** Requieren que un marketer y un desarrollador trabajen juntos (consulta <Anchor target="_blank" href="/marketers/es/docs/test-pba-web-sdk-integration">Probando de integración del SDK web de PBA</Anchor>).

> 📘 **Note**
>
> Ver también
>
> * Pruebas de integración de redes de publicidad Pruebas de integración de redes de publicidad

<div id="traits-and-limitations" />

## Especificaciones y limitaciones

| Caducado | Nota |
| --- | --- |
| Enlaces de prueba | Si usas un dispositivo de prueba registrado, elimina el parámetro `af_inactivity_window` del enlace de prueba. De lo contrario, la instalación puede atribuirse incorrectamente como *orgánica* en lugar de atribuirse al enlace de prueba. |

<div data-zendesk-anchors="overview=visi%C3%B3n-general 01H88X11QS2VYFXJGC95TXC6PN=visi%C3%B3n-general testing-using-the-sdk-integration-tests-page=probando-mediante-la-p%C3%A1gina-de-pruebas-de-integraci%C3%B3n-del-sdk h_01HYX9R159XMZKMH1MBMBH9K9J=probando-mediante-la-p%C3%A1gina-de-pruebas-de-integraci%C3%B3n-del-sdk prepare-a-test-device=prepara-un-dispositivo-de-prueba h_01J9GTS4S2RXJAMYGG6XJ5HFRZ=prepara-un-dispositivo-de-prueba perform-the-integration-tests=realizar-las-pruebas-de-integraci%C3%B3n h_01J9GTW7RAGZXE7GK5BWGBA7N5=realizar-las-pruebas-de-integraci%C3%B3n testing-using-attribution-links=pruebas-mediante-enlaces-de-atribuci%C3%B3n 01H88X11QT0WDRW5GZDCR7MZ3D=pruebas-mediante-enlaces-de-atribuci%C3%B3n testing-retargeting-using-attribution-links=c%C3%B3mo-probar-el-retargeting-mediante-enlaces-de-atribuci%C3%B3n 01H88X11QTQ94BAJGEE1V11F6X=c%C3%B3mo-probar-el-retargeting-mediante-enlaces-de-atribuci%C3%B3n testing-organic-installs=pruebas-de-instalaciones-org%C3%A1nicas h_01HYX9R1594DD9BEZ6PMV9PJM8=pruebas-de-instalaciones-org%C3%A1nicas Testing%20CTV=prueba-ctv 01H88X11QT72F71N49G65BAEAE=prueba-ctv traits-and-limitations=especificaciones-y-limitaciones h_01J6S6HS0H0M6GQ81WGZ3XT0P9=especificaciones-y-limitaciones" />
