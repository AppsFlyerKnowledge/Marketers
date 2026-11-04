---
title: Medición de desinstalaciones
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-alina-koifman
    - Marketers
    - Mobile Attribution
  created_at: '2021-10-14T08:03:47Z'
  edited_at: '2026-08-22T00:09:56Z'
  id: 4408933557137
  locale: es
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/es/articles/4408933557137
---
> **At a glance:** Mide la tasa de desinstalación de tu aplicación y determina qué fuentes (medios de comunicación, campañas, creatividades publicitarias y regiones) atraen a usuarios de calidad.

<div id="overview" />

## Visión general

Para comprender el valor de los usuarios de tu aplicación, es esencial analizar tanto las tasas de instalación como las de desinstalación. La métrica de desinstalación te permite medir el rendimiento de tu aplicación y entender cuándo y por qué los usuarios deciden abandonarla.

<div id="how-does-it-work" />

### ¿Cómo funciona?

1. <span class="af-ol-a"></span>AppsFlyer envía una solicitud diaria de API a Firebase Cloud Messaging (FCM) y Apple Push Notification Services (APNS).
2. Luego, FCM y APNS envían una notificación push silenciosa para verificar si la aplicación sigue instalada en un determinado dispositivo.
3. Se registra una desinstalación si la respuesta indica que la aplicación fue desinstalada (FCM y APNS) o si no se ha registrado actividad del usuario en los últimos 270 días (solo FCM).
4. AppsFlyer atribuye la desinstalación a la fuente de medios que originalmente trajo al usuario.

> 📘 **Note**
>
> **Nota:**
>
> Las métricas de desinstalación están disponibles en el dashboard unificado y en la vista de adquisición de usuarios.

<div id="how-to-use-uninstall-data" />

## Cómo utilizar los datos de desinstalación

Estos son algunos ejemplos de lo que puedes aprender al medir las desinstalaciones y cómo puedes usar los datos para optimizar campañas y mejorar la interacción con los usuarios.

<div id="compare-the-quality-of-sources" />

<Accordion title="Comparar la calidad de las fuentes">

Al comparar la calidad de los usuarios adquiridos de diferentes fuentes (medios de comunicación, campañas, creatividades publicitarias y regiones), puedes identificar las fuentes con las tasas de desinstalación más bajas y reasignar fondos a ellas.

> 📘 **Note**
>
> **Ejemplo**
>
> Eres un especialista en marketing de aplicaciones de juegos para PlayIt Gaming International. Acabas de lanzar una nueva aplicación y estás ejecutando campañas en dos fuentes de medios distintas (fuente de medios A y fuente de medios B).
>
> Cuando revisas el panel de control, ves que aunque la fuente de medios A tiene la mayor cantidad de instalaciones (10.390), también tiene la tasa de desinstalación más alta (30%).
>
> Por otro lado, la fuente de medios B tiene 5.949 instalaciones y la tasa de desinstalación más baja (12%).
>
>  ![adjusted.png](https://files.readme.io/36fb732bfe3a63729b1aa0913f2fe3f24df6a7c86adde9f5c2b95424d840dec4-33839423253137.png)
>
> Con esta información, podrías destinar una mayor parte de tu presupuesto a la fuente de medios B y así tratar de conseguir más usuarios activos.

</Accordion>

<div id="share-uninstall-data-with-ad-networks-for-optimization" />

<Accordion title="Compartir datos de desinstalación con redes publicitarias para optimizar">

Enviar postbacks de eventos de desinstalación a las redes publicitarias con las que colaboras es útil para optimizar las campañas de adquisición de usuarios. Puedes enviar el evento de desinstalación [asignando af\_uninstall a tu red publicitaria](/docs/measure-uninstalls#mapeo-del-evento-de-desinstalación). Una vez completado el mapeo, se envía un evento cada vez que se identifica que un usuario ha desinstalado la aplicación. Las redes publicitarias pueden utilizar esta información para identificar a los usuarios menos comprometidos y enfocarse en alcanzar usuarios más comprometidos.

> 📘 **Note**
>
> **Ejemplo**
>
> Eres un responsable de marketing de aplicaciones de juegos para PlayIt Gaming International. La fuente de medios A es una red publicitaria con la que estás colaborando para el lanzamiento de tu nueva aplicación de Android. En la campaña anterior realizada con la fuente de medios A, 1.000 usuarios nuevos instalaron tu aplicación y, posteriormente, 300 la desinstalaron. Para la nueva campaña, deseas que la fuente de medios A reciba datos de desinstalación. Esto permitirá que la fuente de medios A aborde rápidamente los retos vinculados a las desinstalaciones.
>
> Con base en la experiencia de la campaña anterior, la fuente de medios A elabora una lista de exclusión de usuarios específicos para los anuncios de tu nueva campaña:
>
> * Usuarios que ya han demostrado tener un menor valor para tu aplicación.
> * Usuarios que desinstalan tus aplicaciones con regularidad.
>
> Esto permite que la fuente de medios A optimice la segmentación de la audiencia, asegurándose de que el presupuesto de tu campaña no se desperdicie en usuarios que no necesitan ver ciertos anuncios.

</Accordion>

<div id="exclude-uninstalls-from-retargeting-campaigns" />

<Accordion title="Excluir desinstalaciones de campañas de retargeting">

En algunos casos, para cumplir con normativas como el GDPR y la CCPA, puede ser necesario excluir a los usuarios que han desinstalado tu aplicación de las campañas de retargeting. La información sobre desinstalaciones te permite crear listas de exclusión y aplicar medidas de protección para salvaguardar la privacidad y los datos de tus clientes.

Los métodos para excluir usuarios incluyen los siguientes:

* <Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-overview#user-journey-report-availability">Informes de datos sin procesar:</Anchor> Un método manual en el que se obtiene una lista de usuarios que han desinstalado desde el informe **Desinstalaciones** y se elabora una lista de exclusión.
* <Anchor target="_blank" href="/marketers/es/docs/audiences-guide">Audiencias de AppsFlyer:</Anchor> Un método automático en el que se define una audiencia objetivo según criterios específicos (por ejemplo, usuarios que **no han** desinstalado tu aplicación). Los usuarios que no cumplen con los criterios son excluidos de la audiencia.

> 📘 **Note**
>
> **Ejemplo**
>
> Eres un responsable de marketing de aplicaciones de juegos para PlayIt Gaming International. Estás llevando a cabo una campaña de retargeting para una de tus aplicaciones Android y decides utilizar Audiencias de AppsFlyer para definir la audiencia de retargeting. Los criterios para tu audiencia son los siguientes:
>
> * Usuarios que no han desinstalado la aplicación.
> * Usuarios que no han abierto la aplicación en los últimos 30 días.
>
> Esto te permite crear una audiencia de retargeting más precisa. Cuando tu campaña de retargeting se ejecute, los anuncios solo se mostrarán a los usuarios definidos en tu audiencia de retargeting.

</Accordion>

<div id="setting-up-uninstall-measurement" />

## Configuración de la medición de desinstalación

El proceso para configurar la métrica de desinstalación requiere la colaboración entre el especialista en marketing y el desarrollador. Las instrucciones de implementación dependen del sistema operativo en el que funcione tu aplicación.

El flujo para el especialista en marketing y el desarrollador es el siguiente:

<Tabs>
<Tab title="Android">

| Tarea | Propietario |
| --- | --- |
| [Conectar Firebase Cloud Messaging (FCM) con AppsFlyer](/docs/measure-uninstalls#conectar-firebase-cloud-messaging-a-appsflyer-android) | marketer |
| [Configurar la medición de desinstalaciones en AppsFlyer](/docs/measure-uninstalls#configura-la-medición-de-desinstalación-en-appsflyer) | marketer |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/uninstall-measurement">Integra con el SDK</Anchor> | Desarrollador Android |
| [Probar la medición de desinstalaciones](/docs/measure-uninstalls#prueba-de-medición-de-desinstalación) | marketer |
| [Opcional] [Asigna el evento de desinstalación](/docs/measure-uninstalls#mapeo-del-evento-de-desinstalación) a los partners relevantes en el dashboard | marketer |

</Tab>

<Tab title="apps de iOS,">

| Tarea | Propietario |
| --- | --- |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/uninstall-measurement-ios#creating-a-p12-certificate">Generar certificado P12</Anchor> | Desarrollador de iOS |
| [Configurar la medición de desinstalación en AppsFlyer](/docs/measure-uninstalls#configura-la-medición-de-desinstalación-en-appsflyer) | Comercializador |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/uninstall-measurement">Integrarse con el SDK</Anchor> | Desarrollador de iOS |
| [Probar la medición de desinstalación](/docs/measure-uninstalls#prueba-de-medición-de-desinstalación) | Comercializador |
| [Opcional] [Mapear el evento de desinstalación](/docs/measure-uninstalls#mapeo-del-evento-de-desinstalación) a los socios relevantes en el panel de control | Comercializador |

</Tab>
</Tabs>

<div id="implementation-procedures" />

## Procedimientos de implementación

La implementación requiere que tu desarrollador móvil integre un mecanismo que responda a las notificaciones push dentro de tu aplicación. Las instrucciones de implementación varían según el sistema operativo.

<div id="connect-firebase-cloud-messaging-to-appsflyer-android" />

### Conectar Firebase Cloud Messaging a AppsFlyer (Android)

La medición de desinstalación en Android está disponible al configurar la medición de desinstalación en AppsFlyer e integrar Firebase Cloud Messaging (FCM) en tu aplicación.

<div id="http-v1" />

<Accordion title="HTTP V1">

**Para configurar FCM HTTP V1 para desinstalaciones:**

1. **Para obtener el ID del proyecto**:
   1. Accede a la <Anchor target="_blank" href="https://console.firebase.google.com/">consola FCM.</Anchor>
   2. Selecciona un proyecto.
   3. [altalt](https://files.readme.io/255f5cf42ba1b07cae905ec0acbe6459303c3bd5b03f2d36e1ac3f9606fbb229-33839382512145.png)

       ![DesinstalarFirebase.png](https://files.readme.io/15e74e10daa2f1f1d872f0c8fea274c9819c52c4655baa903728257dd6337e80-33839423254289.png)
   4. Copia el ID del proyecto. Lo necesitarás más adelante en el proceso.
2. Para habilitar la API de FCM:
   1. Ve a la pestaña **Mensajería en la nube**.
   2. Asegúrate de que **Firebase Cloud Messaging API (V1)** esté configurada como **Habilitada**
3. **Para asignar a AppsFlyer el rol de desinstalación:**
   1. Ve a la pestaña **Cuentas de servicio**.
   2. Haz clic en **Administrar permisos de cuenta de servicio**.   
      Se abrirá una nueva pestaña del navegador en Google Cloud Platform.
   3. En el menú lateral, selecciona **Roles**.
   4. Haz clic en **+Crear rol.**
   5. Completa de la siguiente forma:
      * Título: Introduce **Desinstalaciones de AppsFlyer**.
      * ID: Introduce `af_uninstalls`.
      * Etapa de lanzamiento del rol: Selecciona **Disponibilidad General**.
   6. Haz clic en **Añadir permisos.**
   7. **Filtro**, selecciona el permiso **cloudmessaging.messages.create**.

       ![Filtro de permisos de mensajes en la nube](https://files.readme.io/255f5cf42ba1b07cae905ec0acbe6459303c3bd5b03f2d36e1ac3f9606fbb229-33839382512145.png)
   8. Haz clic en **Añadir** y luego en **Crear**.
4. **Para asignar a AppsFlyer el rol de desinstalación de FCM:**
   1. En el menú lateral, selecciona **IAM**.
   2. Abre la pestaña **PERMISOS** -> **VER POR PRINCIPALES**.
   3. Haz clic en **Otorgar acceso.**
   4. En **Añadir principales** -> **Nuevos principales**, introduce **af-uninstalls-tracking@af-uninstalls-tracking.iam.gserviceaccount.com**
   5. En **Asignar roles** -> **Rol** selecciona el personalizado que creaste: **Desinstalaciones de AppsFlyer**.
   6. Haz clic en **Guardar**.   
      Se ha asignado a la cuenta de servicio de AppsFlyer el rol correspondiente a las desinstalaciones de AppsFlyer.

      > 📘 **Note**
      >
      > **Nota:**
      >
      > AppsFlyer utiliza notificaciones push silenciosas únicamente para medir desinstalaciones o identificar usuarios inactivos, no para ningún otro fin.


</Accordion>

<div id="legacy-http" />

<Accordion title="[Obsoleto] HTTP clásico">

> 🚧 **Important**
>
> **Importante:**
>
> La API HTTP heredada fue discontinuada por Firebase el 20 de junio de 2023 y se eliminará el 21 de junio de 2024. Si utilizas la API heredada, te recomendamos encarecidamente que [uses la API HTTP v1](/docs/measure-uninstalls#http-v1). <Anchor target="_blank" href="https://firebase.google.com/docs/cloud-messaging/http-server-ref">Más información</Anchor>

La medición de desinstalación con Firebase Messaging es compatible con Android SDK V4.7.0 o superior.

**Para obtener la clave del servidor de Firebase:**

1. Crea un proyecto de aplicación Android en Firebase (si no lo has hecho ya), o migra tu proyecto desde **Google Developer Console** (sigue las instrucciones allí). Para más información, visita <Anchor target="_blank" href="https://firebase.google.com/docs/cloud-messaging/android/client">Firebase</Anchor>.
2. Abre la <Anchor target="_blank" href="https://console.firebase.google.com">Consola</Anchor> de Firebase.
3. En la consola de Firebase, ve a Configuración del proyecto (haz clic en el engranaje junto a Descripción general del proyecto en el panel izquierdo de la página).

    ![firebase_cloud_messaging_server_key.png](https://files.readme.io/4e31c02a1bea013c823b0148ba1704d4492f66d04e23f0e13e00a9c0c22d286c-33839382513041.png)
4. En la pestaña de Mensajería en la nube, verás dos claves de servidor.
5. Copia la **clave del servidor**.

</Accordion>

<div id="configure-uninstall-measurement-in-appsflyer" />

### Configura la medición de desinstalación en AppsFlyer.

<Tabs>
<Tab title="Android">

**Requisito previo**: El desarrollador de Android debe completar sus <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/uninstall-measurement">instrucciones de integración</Anchor>.

Para configurar la medición de desinstalación en AppsFlyer:

1. En AppsFlyer, en el menú lateral, selecciona **Configuración** > **Configuración de la aplicación**.
2. Si es necesario, activa **Medición de desinstalación**.
3. Selecciona **HTTP V1 e introduce el ID del proyecto que preparaste anteriormente.**

    ![DesinstalarHTTPV1.png](https://files.readme.io/80d13e47ea7ae1585d2ecc0e2f7210572e47dba936557c8e96314e49b0d738d8-33839423258641.png)
4. Haz clic en **Probar conexión**.  
   Se muestra el mensaje de éxito.

   > 📘 **Note**
   >
   > **Nota:**
   >
   > Si, tras probar la conexión, aparece el mensaje de error **El ID del proyecto no es válido o faltan permisos de acceso**, revisa la configuración de la conexión en FCM. Para obtener más información, consulta [Conecta Firebase Cloud Messaging con AppsFlyer (Android)](#conectar-firebase-cloud-messaging-a-appsflyer-android) en este artículo.  
   > y asegúrate de que los permisos y el ID del proyecto estén establecidos correctamente

5. Haz clic en **Guardar configuración**.

</Tab>

<Tab title="apps de iOS,">

**Requisito previo**: el desarrollador de iOS debe completar sus <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/uninstall-measurement">instrucciones de integración</Anchor>.

**Para configurar la medición de desinstalación en AppsFlyer:**

1. Obtén el archivo P12 de tu desarrollador.
2. En AppsFlyer, en el menú lateral, selecciona **Configuración** > **Configuración de la aplicación**.
3. Desplázate hacia abajo hasta la sección Desinstalar.
4. Activa **Medición de desinstalación**.

    ![Desinstalar_iOS_p2.png](https://files.readme.io/3f9de3ebe6099886fa9bc210bd6e491ba91e8ff2c890c980f66c4d48398a597c-33839423260561.png)
5. Haz clic en el icono de carga y selecciona el archivo P12.
6. [Opcional] Si el certificado P12 está protegido con contraseña, introduce la contraseña.
7. Haz clic en **Validar** para enviar el certificado a AppsFlyer para su verificación.
8. Haz clic en **Guardar configuración**.

</Tab>
</Tabs>

<div id="testing-uninstall-measurement" />

## Prueba de medición de desinstalación

Una vez que hayas completado los procedimientos de implementación, puedes instalar y luego desinstalar la aplicación para verificar que las desinstalaciones se registran correctamente. Las desinstalaciones y las tasas de desinstalación se muestran en el panel de descripción general.

<Tabs>
<Tab title="Android">

Puedes realizar esta prueba en aplicaciones que estén:

* En la tienda Google Play
* Pendiente (sin aparecer en la tienda Google Play)
* Disponible a través de descarga directa
* En tiendas de aplicaciones alternativas

Tenga en cuenta lo siguiente al probar aplicaciones de Android:

* La medición de desinstalaciones se procesa <Anchor target="_blank" href="/marketers/es/docs/about-data-freshness-and-timezone-support#uninstalls">diariamente</Anchor>. Un evento de desinstalación se registra dentro de las 24 horas, pero si se reinstala la aplicación durante este tiempo, no se registra ningún evento.
* **Los eventos de desinstalación pueden tardar hasta 48 horas en mostrarse** en <Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-overview">informes de datos sin procesar</Anchor> y en el panel de AppsFlyer (Informe de Rendimiento Agregado).

</Tab>

<Tab title="apps de iOS,">

Tenga presente lo siguiente al probar aplicaciones iOS:

* Las desinstalaciones no aparecen inmediatamente en el panel de AppsFlyer. Debido al servicio de notificaciones push de Apple, el tiempo mínimo que tardan en aparecer las desinstalaciones en el panel es de 9 días. AppsFlyer actualiza y agrega métricas de desinstalaciones cada 24 horas.

  > 📘 **Note**
  >
  > **Ejemplo**
  >
  > * Día 1: Un usuario instala tu aplicación.
  > * Día 4: Un usuario desinstala tu aplicación.
  > * Día 12: El servicio de notificaciones push de Apple reporta la eliminación de la aplicación 8 días después de la desinstalación.
  > * Día 13: Los datos de desinstalación aparecen en el panel de AppsFlyer y en los datos sin procesar.

* Si realizas pruebas en una versión de prueba de la aplicación, asegúrate de usar el entorno sandbox. Consulta las instrucciones para desarrolladores del [procedimiento de entorno de pruebas de desinstalación](https://dev.appsflyer.com/hc/docs/uninstall-measurement-ios#testing-uninstall-measurement).

</Tab>
</Tabs>

<div id="mapping-the-uninstall-event" />

## Mapeo del evento de desinstalación

 ![Desinstalación_evento_postback.png](https://files.readme.io/9c3c7f3fd330720d4f6f41fdf509c5af00d042291c1350ab83a1951464ac8e8f-33839423261713.png) 

Para compartir datos de desinstalación con una ad network, debes mapear el <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">evento af\_uninstall</Anchor> a un partner. A diferencia de los postbacks para eventos normales dentro de la aplicación, el evento de desinstalación no se envía en tiempo real. El tiempo del evento que se informa representa el momento en que AppsFlyer determinó que la aplicación fue desinstalada, y no el momento real de la desinstalación.

Considere lo siguiente:

* AppsFlyer solo puede enviar el postback si el evento realmente ocurre y es registrado por AppsFlyer.
* Si no ves desinstalaciones en la página de descripción general del panel o en el informe de datos sin procesar, significa que no se enviaron postbacks de desinstalación al socio, incluso si el evento **af\_uninstall** fue asignado.

<div id="limitations" />

#### Limitaciones

* Los eventos de desinstalación no se incluyen en los informes de postback de eventos dentro de la aplicación.
* El evento **af\_uninstall** es compatible con todos los socios. Si deseas asignarlo a un socio, pero el evento no está disponible en la pestaña de Integración del socio, contacta con tu CSM o escribe a [hello@appsflyer.com](mailto:hello@appsflyer.com).

<div id="turning-off-uninstall-measurement" />

## Desactivar medición de desinstalación

<Tabs>
<Tab title="Android">

Si se proporciona una clave de servidor Firebase/GCM, la medición de desinstalación de aplicaciones está habilitada por defecto. Los propietarios de aplicaciones pueden desactivar esta función desde el panel de control.

</Tab>

<Tab title="apps de iOS,">

Si se proporciona y valida un certificado P12, la medición de desinstalación de aplicaciones está activada por defecto. Los propietarios de aplicaciones pueden desactivar esta función desde el panel de control.

</Tab>
</Tabs>

**Nota:** Para que se informe una desinstalación, la opción **Habilitar medición de desinstalación** debe estar activada al momento de instalar la aplicación. Las instalaciones que ocurren cuando **Habilitar medición de desinstalación** está desactivada no se informan.

<div id="to-turn-off-uninstall-measurement" />

#### **Para desactivar la medición de desinstalaciones**:

1. En AppsFlyer, en el menú lateral, selecciona **Configuración** > **Configuración de la aplicación**.
2. Ve a **Atribución** > **Medición de desinstalación** y desactiva **Habilitar medición de desinstalación.**

<div id="traits-and-limitations" />

<Accordion title="Características y limitaciones">

| En | Nota |
| --- | --- |
| CUID | El CUID no se envía en los postbacks de desinstalación. |

</Accordion>

<div data-zendesk-anchors="overview=visi%C3%B3n-general h_01HB8CXQ4824V2WEPYGK8YS4DC=visi%C3%B3n-general how-does-it-work=c%C3%B3mo-funciona h_01HB8CXQ48JEJECC1HR79DXCRK=c%C3%B3mo-funciona how-to-use-uninstall-data=c%C3%B3mo-utilizar-los-datos-de-desinstalaci%C3%B3n h_01HB8CXQ48E2SRN95MH4E2H7ZH=c%C3%B3mo-utilizar-los-datos-de-desinstalaci%C3%B3n h_01HB8CXQ48HX9RH50G45FZMZTK=compare-the-quality-of-sources h_01HB8CXQ488E22GPCEBE69VQ3M=share-uninstall-data-with-ad-networks-for-optimization h_01HB8CXQ48JTET73GH0QQBX5HF=exclude-uninstalls-from-retargeting-campaigns setting-up-uninstall-measurement=configuraci%C3%B3n-de-la-medici%C3%B3n-de-desinstalaci%C3%B3n h_01HB8CXQ4810HTB45FAS5ZVRHF=configuraci%C3%B3n-de-la-medici%C3%B3n-de-desinstalaci%C3%B3n implementation-procedures=procedimientos-de-implementaci%C3%B3n h_01HB8CXQ489HRF72VRZ4G532GX=procedimientos-de-implementaci%C3%B3n connect-firebase-cloud-messaging-to-appsflyer-android=conectar-firebase-cloud-messaging-a-appsflyer-android h_01HB8CXQ48ZD5Y0RKTG1W51TKW=conectar-firebase-cloud-messaging-a-appsflyer-android h_01HB8CXQ4865MNVG0VERSNSE3F=http-v1 h_01HB8CXQ48H079WQ6Q6G0XSQC7=legacy-http configure-uninstall-measurement-in-appsflyer=configura-la-medici%C3%B3n-de-desinstalaci%C3%B3n-en-appsflyer h_01HB8CXQ48CVA9B8B78W0H357C=configura-la-medici%C3%B3n-de-desinstalaci%C3%B3n-en-appsflyer testing-uninstall-measurement=prueba-de-medici%C3%B3n-de-desinstalaci%C3%B3n h_01HB8CXQ48SW2TT5Z85XD3XWT6=prueba-de-medici%C3%B3n-de-desinstalaci%C3%B3n mapping-the-uninstall-event=mapeo-del-evento-de-desinstalaci%C3%B3n h_01HB8CXQ499ABX9ZGDFB1VAE8W=mapeo-del-evento-de-desinstalaci%C3%B3n limitations=limitaciones h_01HB8CXQ49F2ARQTEV8Q032P9V=limitaciones turning-off-uninstall-measurement=desactivar-medici%C3%B3n-de-desinstalaci%C3%B3n h_01HB8CXQ49Y5NCG7GK93HXHYMD=desactivar-medici%C3%B3n-de-desinstalaci%C3%B3n to-turn-off-uninstall-measurement=para-desactivar-la-medici%C3%B3n-de-desinstalaciones h_01HB8CXQ49WXZS4M6CK5XG1BCX=para-desactivar-la-medici%C3%B3n-de-desinstalaciones h_01HB8CXQ4916CJ9NDZWGWQHKSA=traits-and-limitations" />
