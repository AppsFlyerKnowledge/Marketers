---
title: Guía básica de integración del SDK
metadata:
  keywords:
    - sdk
    - iOS
    - Android
    - Integration
    - Advertisers
    - appuid
    - anonymous
    - kakao
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2013-08-22T16:09:08Z'
  edited_at: '2026-08-22T00:15:00Z'
  id: 207032066
  locale: es
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/es/articles/207032066
---
> **At a glance:** Colabora con tu desarrollador de aplicaciones móviles o CTV para integrar e instalar el SDK en aplicaciones de Android o iOS. Cuando las tareas básicas de integración estén completas, tu aplicación estará lista para la atribución de instalaciones y la medición de eventos in-app.

<div id="implementing-the-dev-key-in-your-app" />

## **Implementación de la clave de desarrollo en tu aplicación**

AppsFlyer utiliza la clave de desarrollo para identificar de manera única tu cuenta. La clave de desarrollo es esencial porque permite que el SDK envíe y recupere datos de forma segura, pertenecientes a tu cuenta. Tu desarrollador debe instalar e integrar el SDK, e incluir la clave de desarrollo.

<div id="retrieve-the-dev-key" />

#### Recuperar la clave de desarrollo

Antes de que tu desarrollador pueda instalar e integrar el SDK, debes recuperar la clave de desarrollo.

1. En AppsFlyer, desde el menú lateral, elige **Configuración** > **Configuración de la aplicación**.
2. Copia tu clave de desarrollo y envíala a tu desarrollador móvil.

   ![](https://files.readme.io/5078fdabbcce4d3977f3d32351b61bacbc8af406a68911f2c6b4cdca458712a5-30603573703057.png)

<div id="provide-the-dev-key-to-your-developer" />

#### Proporciona la clave de desarrollo a tu desarrollador

Proporciona la clave de desarrollo, el ID de la aplicación y el token de la API v2 de AppsFlyer a tu desarrollador móvil con instrucciones para:

* Utiliza el asistente de integración de SDK para la instalación e integración automatizada del SDK.
* Utiliza las instrucciones paso a paso para instalar e integrar el SDK.

<div id="where-to-start-the-sdk" />

## **¿Dónde iniciar el SDK?**

Al planificar la integración del SDK de AppsFlyer, la primera decisión que debes tomar es dónde inicializar e iniciar el SDK dentro del flujo de inicio de tu aplicación.

La regla general es que el SDK comience a enviar datos tan pronto como sea posible después de iniciar la aplicación. **Esto asegura que el SDK capture el evento de instalación y todos los demás eventos in-app que se produzcan durante la sesión.**

No obstante, para cumplir con las normativas de protección de la privacidad, como GDPR y CCPA, a menudo es necesario retrasar el envío de datos a AppsFlyer hasta que los usuarios consientan compartir su información.

<Tabs>
<Tab title="Android nativo">

<div id="starting-the-sdk-in-android-native" />

### Iniciando el SDK en Android nativo

<div id="select-in-what-class-to-start-the-sdk" />

#### SELECCIONA EN QUÉ CLASE INICIAR EL SDK

Decide si quieres iniciar el SDK en la clase global `Application` o en la clase `Activity`:

* **Inicia el SDK en la clase global** `Application`: Inicializar el SDK en la clase/subclase global `Application` es, generalmente, una buena práctica, ya que la clase `Application` se carga e inicializa antes de que cualquier interfaz de usuario de la aplicación se muestre. Esto asegura que el SDK pueda iniciarse en cualquier situación, incluso con enlaces profundos.
* <strong>Inicia el SDK en una clase</strong> (inicio diferido)<strong> para permitir que los usuarios opten por compartir datos. Esto se debe a que para obtener el consentimiento del usuario es necesaria una interfaz de usuario (UI) en una clase `Activity`.</strong>

<div id="android-developer-instructions" />

#### INSTRUCCIONES PARA DESARROLLADORES DE ANDROID

* Informa al desarrollador sobre tu decisión respecto a lo siguiente:
  * ¿En qué clase - `Application` o `Activity` - iniciar el SDK?
  * ¿Qué escenario de inclusión/exclusión voluntaria utilizar?
* Envía al desarrollador el siguiente enlace de referencia:
  * [Cómo realizar un inicio diferido](https://dev.appsflyer.com/hc/docs/integrate-android-sdk#starting-the-android-sdk)

</Tab>

<Tab title="iOS nativo">

<div id="starting-the-sdk-in-ios" />

<div id="starting-the-sdk-in-ios-native" />

### Cómo iniciar el SDK en iOS nativo

<div id="delay-the-sdk-start-in-ios" />

#### RETRASAR EL INICIO DEL SDK EN IOS

Una consideración importante al planificar cómo iniciar el SDK es si conviene retrasar `start` hasta que se otorgue el consentimiento del usuario.

El SDK proporciona el `waitForATTUserAuthorization` método, que te permite **configurar cuánto tiempo debe esperar el SDK para obtener el consentimiento del usuario antes de enviar datos a los servidores de AppsFlyer**.

Para obtener más información sobre el flujo de datos del método y su interacción con el marco ATT de iOS, consulta la sección [Configurar el soporte de App Tracking Transparency (ATT)](/docs/basic-sdk-integration-guide#vista-general-de-waitforattuserauthorization) .

<div id="ios-developer-instructions" />

#### INSTRUCCIONES PARA DESARROLLADORES DE IOS

Comparte la siguiente información con tu desarrollador:

* ¿Cuánto tiempo en segundos es el tiempo de espera antes de enviar datos a AppsFlyer?
* Enlaces para desarrolladores:
  * [Inicio del SDK para iOS](https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#starting-the-ios-sdk) para la guía para desarrolladores y referencia sobre cómo iniciar el SDK.
  * [Configurar el soporte de App Tracking Transparency (ATT)](/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support) para obtener información sobre el `waitForATTUserAuthorization` flujo de datos del método y cómo interactúa con el marco de ATT de iOS
  * [Habilitación del soporte de App Tracking Transparency (ATT)](https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#enabling-app-tracking-transparency-att-support) para la guía para desarrolladores y la referencia sobre `waitForATTUserAuthorization`

</Tab>

<Tab title="Unity">

<div id="starting-the-sdk-in-Unity" />

<div id="starting-the-sdk-in-unity" />

### Cómo iniciar el SDK en Unity

Envía <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/basicintegration#manual-integration">este artículo del Dev Hub</Anchor> a tu desarrollador sobre cómo iniciar el SDK.

</Tab>

<Tab title="React Native">

<div id="starting-the-sdk-in-react" />

<div id="starting-the-sdk-in-react-native" />

### Cómo iniciar el SDK en React Native

Envía a tu desarrollador <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#startsdk">este artículo del Dev Hub</Anchor> sobre cómo iniciar el SDK.

</Tab>
</Tabs>

<div id="select-your-privacy-preserving-strategy" />

## Elige tu estrategia de preservación de la privacidad

Selecciona **cómo preservar la privacidad del usuario.** Por ejemplo, elige entre detener el SDK durante la instalación, evitar el intercambio de datos con terceros, anonimizar los datos del usuario o desactivar identificadores específicos.

Para más información sobre los diferentes métodos de protección de privacidad disponibles, consulta <Anchor target="_blank" href="/marketers/es/docs/apply-privacy-preserving-sdk-methods">Métodos de preservación de la privacidad en el SDK</Anchor>.

<div id="attribution" />

## **Atribución**

El SDK recopila <Anchor target="_blank" href="/marketers/es/docs/about-device-identifiers">identificadores</Anchor> con el propósito de atribución. Para asegurar que las instalaciones se registren y atribuyan correctamente, revisa y sigue estas pautas.

**Todas las plataformas**

<Accordion title="Identificador único para instalaciones">

Un ID de AppsFlyer se crea automáticamente para cada nueva instalación de la aplicación. No se requiere ninguna acción por parte del responsable de marketing.

Puedes utilizar este identificador para realizar las siguientes acciones:

* Enviar <Anchor target="_blank" href="/marketers/es/docs/server-to-server-events-api-for-mobile-s2s-mobile">eventos in-app de servidor a servidor</Anchor>.
* Vincular el ID de AppsFlyer con los registros de usuarios en tus sistemas de backend.
* Descargar el <Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-overview">reporte de eventos in-app con raw data</Anchor> y usar **appsflyer\_id** para analizar el comportamiento y el viaje de los usuarios.

</Accordion>

<Accordion title="Integrar identificadores únicos de ttu sistema de BI con AppsFlyer">

Configura tu propio ID de usuario de cliente (CUID) en el SDK de AppsFlyer para cruzar el ID único de tu sistema de BI con el ID de AppsFlyer y otros identificadores. El CUID está disponible en los reportes de <Anchor target="_blank" href="/marketers/es/docs/raw-data-field-dictionary">raw data</Anchor> de AppsFlyer. También puedes usarlo en las APIs de postback para realizar referencias cruzadas con tus IDs internas.

Para aprender más sobre CUID, consulta <Anchor target="_blank" href="/marketers/es/docs/customer-user-id-field-cuid">este artículo</Anchor>.

</Accordion>

**Solo para Android**

Las siguientes secciones describen consideraciones de atribución para Google Play Store o tiendas de aplicaciones de terceros.

<Accordion title="Atribuir aplicaciones publicadas en Google Play">

<div id="google-play-install-referrer" />

#### REFERENCIA DE INSTALACIÓN DE GOOGLE PLAY

La [API de Google Play Install Referrer](https://developer.android.com/google/play/installreferrer) mejora la precisión de la <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model#métodos-de-atribución">atribución</Anchor>, protege contra el fraude de instalación, y permite la recuperación segura de datos de referencia de Google Play (por ejemplo, la versión de la aplicación en el momento de su instalación inicial).

Se recomienda que proporciones a tu desarrollador [instrucciones para agregar la API de Google Play Install Referrer](https://developer.android.com/google/play/installreferrer/library).

<div id="gaid" />

#### GNA Company

A partir del SDK V4.8.0, AppsFlyer recopila automáticamente este identificador de dispositivo.

</Accordion>

<Accordion title="Atribuir aplicaciones en tiendas de aplicaciones de terceros">

Con AppsFlyer, puedes <Anchor target="_blank" href="/marketers/es/docs/set-up-multi-store-android-attribution">atribuir instalaciones que se originan en tiendas de aplicaciones de terceros</Anchor>, como Amazon, Opera, GetJar, Baidu, y Huawei. Esto te permite promocionar tus aplicaciones y alcanzar audiencias más amplias en mercados donde Google Play Store no está disponible.

AppsFlyer admite la atribución en el contexto de tiendas de aplicaciones de terceros de la siguiente manera:

* **IMEI o ID de Android:** El SDK no recopila automáticamente ni el IMEI ni el ID de Android. Sin embargo, si es necesario recopilar estos identificadores (por ejemplo, para <Anchor target="_blank" href="/marketers/es/docs/measure-attribution-in-the-chinese-domestic-market#atribución-de-aplicaciones-android-en-el-mercado-nacional-chino">aplicaciones en el mercado local chino</Anchor>), tu desarrollador puede implementar uno de los siguientes métodos de recopilación:
  * Recopilación manual: La aplicación transfiere el IMEI o el ID de Android al SDK utilizando la API `setImeiData` o `setAndroidIdData` (mira la referencia de funciones en las pestañas a continuación). El SDK envía los datos a los servidores de AppsFlyer.

    <Tabs>
    <Tab title="Android nativo">

    Consulta la referencia del SDK de Android para:

    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setimeidata">`setImeiData`</Anchor>
    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setandroididdata">`setAndroidIdData`</Anchor>

    </Tab>

    <Tab title="Unity">

    Consulta la referencia del SDK de Unity para:

    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setimeidata">`setImeiData`</Anchor>
    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setandroididdata">`setAndroidIdData`</Anchor>

    </Tab>
    </Tabs>

  * Participar en la recopilación de ID de dispositivo: Obliga al SDK a recopilar el IMEI o ID de Android mediante setCollectIMEI y setCollectAndroidID (mira la referencia de funciones en las pestañas a continuación).

    <Tabs>
    <Tab title="Android nativo">

    Consulta la referencia del SDK de Android para:

    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectimei">`setCollectIMEI`</Anchor>
    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectandroidid">`setCollectAndroidID`</Anchor>

    </Tab>

    <Tab title="Unity">

    Consulta la referencia del SDK de Unity para:

    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setcollectimei">`setCollectIMEI`</Anchor>
    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setcollectandroidid">`setCollectAndroidID`</Anchor>

    </Tab>

    <Tab title="React Native">

    Consulta la referencia de React Native para:

    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#setcollectimei">`setCollectIMEI`</Anchor>
    * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#setcollectandroidid">`setCollectAndroidID`</Anchor>

    </Tab>
    </Tabs>

* **OAID:** Atribuye instalaciones desde tiendas de aplicaciones Android de terceros. Para más información, lee la <Anchor target="_blank" href="/marketers/es/docs/android-oaid-implementation-in-the-sdk">guía para implementar OAID</Anchor>.
* **Referencias de instalación:** El SDK soporta la recuperación de datos de referencia de Samsung Gallery y Huawei AppGallery.

</Accordion>

**Sólo iOS**

Las siguientes secciones incluyen información esencial sobre el soporte para dispositivos iOS 14+.

<Accordion title="Configurar el soporte para App Tracking Transparency (ATT)">

**ANTECEDENTES**

Desde iOS 14.5, la recopilación del IDFA requiere el consentimiento del usuario. En la práctica, esto significa que el acceso al IDFA está regulado por el framework de [**App Tracking Transparency**](https://developer.apple.com/documentation/apptrackingtransparency) (ATT). En dispositivos iOS 14+, el SDK utiliza el framework de la ATT para acceder al IDFA del dispositivo. Para una introducción a la ATT, lee los <Anchor target="_blank" href="/marketers/es/docs/about-att-and-skan#att-principles">principios de la ATT</Anchor>.

<Tabs>
<Tab title="iOS nativo">

Consulta el Centro de Desarrollo para <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#enabling-app-tracking-transparency-att-support">instrucciones sobre cómo implementar la ATT</Anchor>.

</Tab>

<Tab title="Unity">

Consulta el Centro de Desarrollo para <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/basicintegration#collect-idfa-with-attrackingmanager">instrucciones sobre cómo implementar la ATT</Anchor>.

</Tab>
</Tabs>

Cuando la atribución se realiza utilizando IDFA, es crucial que el IDFA se envíe en el **primer lanzamiento. `waitForATTUserAuthorization`Por esta razón, el SDK ofrece el método `waitForATTUserAuthorization`.**

<div id="waitforattuserauthorization-overview" />

#### Vista general de waitForATTUserAuthorization

> 🚧 **Important**
>
> No llames a waitForATTUserAuthorization si no tienes la intención de invocar el aviso de la ATT.

`waitForATTUserAuthorization` te permite configurar el tiempo que el SDK debe posponer y esperar el estado de la ATT antes de enviar datos a los servidores de AppsFlyer.

![](https://files.readme.io/a41e66c5aa23d2c673aba5b06589dcc24d34175e90900a8232343272ecca427c-30603573710993.png)

Cuando un usuario abre la aplicación, el estado de la ATT es **notDetermined.** Durante el período de espera `waitForATTUserAuthorization`, el SDK almacena en memoria el evento de inicio y los eventos consecutivos in-app, de manera similar a como se registran los [eventos offline](https://dev.appsflyer.com/hc/docs/in-app-events-sdk#offline-in-app-events):

* Si el usuario **acepta** la solicitud de la ATT (recopilación de IDFA):
  * El SDK añade el IDFA a los eventos en caché.
  * El SDK se activa y envía eventos con IDFA sin esperar a que finalice el tiempo de espera.
* Si el usuario **rechaza** la solicitud de la ATT: El SDK se activa y envía eventos en caché sin IDFA sin esperar a que finalice el tiempo de espera.
* Si el período de espera finaliza y el estado de la ATT sigue siendo **notDetermined:** El SDK se activa y envía eventos en caché sin IDFA.

**Consideraciones**

* Llamar a [`requestTrackingAuthorization`](https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/3547037-requesttrackingauthorization) sin configurar `waitForATTUserAuthorization` resultará en el envío de inicios y eventos sin IDFA para dispositivos iOS 14+.
* Si el usuario coloca la aplicación en segundo plano durante el período de espera:
  * El temporizador se pausa hasta que la aplicación regresa al primer plano.
  * Los eventos se almacenan en memoria.
* Si el usuario cierra la aplicación durante el período de espera:
  * El temporizador se reinicia en el siguiente inicio de la aplicación.
  * Se pierden los eventos en caché.

</Accordion>

<Accordion title="Personalizar el diálogo de consentimiento de ATT">

Puedes personalizar el mensaje de la solicitud ATT. Un mensaje que explique claramente el propósito de la solicitud podría ayudar a aumentar las tasas de opt-in por parte de los usuarios.

Ten en cuenta lo siguiente al crear tu mensaje:

* Usa una redacción que explique claramente a tus usuarios por qué la aplicación solicita su consentimiento.
* Informa a los usuarios sobre cómo se utilizarán sus datos. [Infórmate más sobre la privacidad del usuario y el uso de datos.](https://developer.apple.com/app-store/user-privacy-and-data-use/)

Una vez que tu mensaje esté terminado, proporciona a tu desarrollador el texto y las instrucciones de implementación.

<Tabs>
<Tab title="iOS nativo">

Consulta el Hub de Desarrolladores para <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-ios-sdk#customizing-the-att-consent-dialog">instrucciones sobre cómo personalizar el diálogo de consentimiento de la ATT</Anchor>.

</Tab>

<Tab title="Unity">

Consulta el Hub de Desarrolladores para [instrucciones sobre cómo personalizar el diálogo de consentimiento de la ATT](https://dev.appsflyer.com/hc/docs/basicintegration#collect-idfa-with-attrackingmanager).

</Tab>
</Tabs>

</Accordion>

<Accordion title="Soporte para la atribución SKAN">

> 📘 **Note**
>
> Para admitir completamente la atribución SKAN, actualiza a iOS SDK V6.2.3+.

SKAN es una clase utilizada por iOS para validar instalaciones de aplicaciones promovidas por anunciantes. El proceso de validación de instalación de la aplicación involucra tanto la aplicación fuente como la aplicación anunciada.

Una aplicación fuente es aquella que participa en campañas publicitarias mostrando anuncios de una ad network. La configuración de tu aplicación para mostrar anuncios no está cubierta por el SDK de AppsFlyer. Para configurarla, sigue las [instrucciones de Apple](https://developer.apple.com/documentation/storekit/skadnetwork/configuring_a_source_app).

Para la aplicación anunciada (la que incorpora el SDK de AppsFlyer), la <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide">solución SKAN</Anchor> de AppsFlyer utiliza SKAN para proporcionar la atribución mientras AppsFlyer recopila, traduce y agrega los datos, protegiendo la privacidad del usuario. Cuando la aplicación se inicia por primera vez, la plataforma de AppsFlyer utiliza la configuración establecida por el marketer para indicar al SDK cómo establecer el valor de conversión de SKAN.

Para emplear la solución SKAN:

* El marketer debe configurar la medición SKAN en AppsFlyer. El desarrollador no tiene que llevar a cabo ninguna tarea.
* El SDK de AppsFlyer llama automáticamente a las APIs de SKAN necesarias.
* Asegúrate de deshabilitar las llamadas al SKAN en otros SDKs si confías en AppsFlyer para la atribución SKAN.
* Ni el desarrollador ni el marketer necesitan realizar ninguna otra acción o proceso de registro en la App Store.

Para desactivar la atribución SKAN, dile a tu desarrollador que lo desactive en el SDK.

<Tabs>
<Tab title="iOS nativo">

Para desactivar la atribución SKAN utiliza <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disableskadnetwork">`disableSKAdNetwork`</Anchor>

</Tab>

<Tab title="Unity">

Para desactivar la atribución SKAN utiliza <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#disableskadnetwork">`disableSKAdNetwork`</Anchor>

</Tab>

<Tab title="React Native">

Para desactivar la atribución SKAN utiliza <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#disableskad">`disableSKAd`</Anchor>

</Tab>
</Tabs>

</Accordion>

<div id="recording-in-app-events" />

## **Registro de eventos in-app**

Los eventos in-app (IAE) proporcionan insights sobre lo que ocurre en tu aplicación. Registrar eventos in-app te ayuda a medir KPIs como el Retorno de la Inversión (ROI) y el Lifetime Value (LTV). Les recomendamos que se tomen el tiempo necesario para definir los eventos que desean registrar.

Una vez que decidas qué eventos in-app quieres medir, envía los nombres de los eventos y sus parámetros a tu desarrollador, e incluye un enlace a:

* El [asistente de instalación del SDK](https://dj.dev.appsflyer.com/?utm_source=kb&amp;utm_medium=kb-basic-sdk-integration) que tiene un viaje dedicado para eventos in-app.
* <Anchor target="_blank" href="http://dev.appsflyer.com/hc/docs/in-app-events-sdk">Las instrucciones de implementación paso a paso para eventos in-app en el SDK</Anchor>.

Para aprender a definir eventos in-app y enviarlos a tu desarrollador, consulta nuestra <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview">guía de eventos enriquecidos in-app</Anchor>.

**Todas las plataformas**

<Accordion title="Registrar ingresos">

Puedes asociar ingresos con cualquier evento in-app. Asegúrate de utilizar el parámetro **af\_revenue** para incluir los ingresos. Es el único parámetro de evento que AppsFlyer cuenta como ingreso real en el dashboard y en los reportes de raw data. <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#revenue-events">Saber más</Anchor>.

<Tabs>
<Tab title="Android nativo">

Para obtener instrucciones para desarrolladores sobre cómo definir eventos de ingresos, consulta [aquí](https://dev.appsflyer.com/hc/docs/in-app-events-android#logging-revenue).

</Tab>

<Tab title="iOS nativo">

Para obtener instrucciones para desarrolladores sobre cómo definir eventos de ingresos, consulta [aquí](https://dev.appsflyer.com/hc/docs/in-app-events-ios#logging-revenue).

</Tab>

<Tab title="Unity">

* Para instrucciones generales para desarrolladores sobre eventos dentro de la aplicación, consulta [aquí](https://dev.appsflyer.com/hc/docs/inappevents#send-event).
* Para instrucciones específicas sobre ingresos en iOS y Android, consulta las pestañas de Android e iOS.

</Tab>
</Tabs>

</Accordion>

<Accordion title="Validar compras in-app">

El SDK de AppsFlyer ofrece verificación del servidor para compras in-app. Al validar una compra in-app, se envía automáticamente un evento de compra a AppsFlyer. Si envías este evento tú mismo, se generarán reportes de eventos duplicados.

</Accordion>

<Accordion title="Verticales de la industria">

Consulta nuestra <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#recommended-events-by-business-vertical">lista de eventos in-app recomendados por vertical</Anchor>, por ejemplo, viajes, juegos o e-commerce.

</Accordion>

<div id="deep-linking-with-onelink" />

## **Deep linking con OneLink**

OneLink es la solución de AppsFlyer para la atribución multiplataforma, **redirección y deep linking**.

**Todas las plataformas**

<Accordion title="Detección y redirección de dispositivos">

Para usuarios que no tienen instalada tu aplicación, OneLink detecta el tipo de dispositivo y los redirecciona al destino correcto (por ejemplo, Google Play, Apple App Store, una tienda de aplicaciones de terceros o una página web). Esto se basa en la configuración de tu plantilla OneLink. <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template">Saber más</Anchor>

</Accordion>

<Accordion title="Enlaces profundos">

Para usuarios que tienen instalada tu aplicación, OneLink abre la aplicación. Además de abrir la aplicación, también puedes enviar a los usuarios a una actividad o página específica dentro de la misma. Esto requiere que tu desarrollador implemente Deep Linking Unificado (UDL):

* El [asistente de instalación del SDK](https://dj.dev.appsflyer.com/?utm_source=kb&amp;utm_medium=kb-basic-sdk-integration) que tiene un recorrido dedicado para la implementación de deep linking, o
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl">Las instrucciones de implementación del SDK paso a paso para deep linking unificado</Anchor>.

**Nota**:

* UDL requiere SDK V6.1+.
* Los clientes ya usando OneLink para deep linking pueden estar utilizando el [método heredado](https://dev.appsflyer.com/hc/docs/dl_work_flow#legacy-use-only-gcd-api-for-deep-linking), en lugar de UDL.

Consulta nuestra guía sobre cómo configurar <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">deep linking y deferred deep linking</Anchor>.

</Accordion>

<Accordion title="Enlaces profundos diferidos">

Para usuarios que no tienen instalada tu aplicación, OneLink detecta el tipo de dispositivo y los redirecciona al destino correcto: Google Play, Apple App Store, una tienda de aplicaciones de terceros o una página web. Una vez que el usuario inicia la aplicación, puedes usar deferred deep linking para redireccionarlo a una actividad o página específica dentro de la aplicación.

Esto requiere que tu desarrollador implemente deferred deep linking.

* El [asistente de instalación del SDK](https://dj.dev.appsflyer.com/?utm_source=kb&amp;utm_medium=kb-basic-sdk-integration) que tiene un recorrido dedicado para la implementación de deep linking, o
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#recommended-implement-extended-deferred-deep-linking">Las instrucciones de implementación del SDK paso a paso para deferred deep linking</Anchor>.

**Nota**:

* UDL requiere SDK V6.1+.
* Clientes que ya utilizan OneLink para deferred deep linking podrían estar usando el [método heredado](https://dev.appsflyer.com/hc/docs/dl_work_flow#legacy-use-only-gcd-api-for-deep-linking), en lugar de UDL.

Consulta nuestra guía sobre cómo configurar <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">deep linking y deferred deep linking</Anchor>.

</Accordion>

<div id="accessing-attribution-and-deep-linking-data" />

## **Acceso a datos de atribución y de deep linking**

La siguiente tabla describe los métodos disponibles para obtener datos de atribución y de deep linking:

| Método | ¿Quién está involucrado? | Resultados de retorno | Método de recuperación | Datos de atribución | Datos de deep linking | Disponibilidad |
| --- | --- | --- | --- | --- | --- | --- |
| <Anchor target="_blank" href="/marketers/es/docs/push-api-streaming-raw-data">**API Push**</Anchor> | • Marketer • Desarrollador back-end | Normalmente en cuestión de minutos | Back-end | Sí | N/A | Premium |
| <Anchor target="_blank" href="/marketers/es/docs/pull-api-raw-data">**API Pull**</Anchor> | • Marketer • Desarrollador back-end | • Periódico (no en tiempo real). • Puede programar descargas de informes de datos sin procesar. | Back-end | Y | Y | Premium para reportes de raw data |
| <Anchor target="_blank" href="/marketers/es/docs/data-locker-for-marketers">**Casillero de datos**</Anchor> | • Marketer • Desarrollador back-end | Los reportes de horarios están disponibles en un plazo de 1 a 3 horas. | Almacenamiento en la nube mediante una de las siguientes opciones: • Espacio propiedad de AppsFlyer en AWS • Almacenamiento propio (AWS o GCS) | Y | Y | Premium |
| <Anchor target="_blank" href="/marketers/es/docs/conversion-data-payloads-and-scenarios#información-general">**Obtener datos de conversión (GCD)**</Anchor> | • Marketer • Desarrollador de aplicaciones móviles <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#legacy-use-only-gcd-api-for-deep-linking">Ver documentación para desarrolladores</Anchor> | Hasta 5 segundos | SDK | Sí | Y | Todas las cuentas |
| <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template">**Deep Linking Unificada (UDL)**</Anchor> | • Marketer • Desarrollador de aplicaciones móviles <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl">Ver documentación para desarrolladores</Anchor> | Hasta 1 segundo | SDK | N/A | Sí | Todas las cuentas |

Ten en cuenta lo siguiente para los usuarios que no dan su permiso en iOS 14.5+:

* Al usar UDL para medios de pago y propios, los datos de deep linking están disponibles.
* Al usar GCD para medios de pago, los datos son limitados y no incluyen detalles de atribución ni de deep linking.

> 👍 **Tip**
>
> Recomendamos lo siguiente:
>
> * Utiliza la Push API para recuperar datos de atribución y enviarlos a tus servidores para procesamiento adicional. Este método espera a que los datos estén disponibles, siendo muy preciso y casi en tiempo real. GCD proporciona datos en tiempo real, pero puede ser inexacto cuando las decisiones finales de atribución se determinan después de más de 5 segundos.
> * Utiliza la Pull API para complementar periódicamente (por ejemplo, diariamente) los datos de atribución en tiempo real, compensando cualquier error de comunicación que pueda ocurrir.

<div id="testing-your-sdk-integration" />

## **Prueba de integración del SDK**

Una vez terminada la integración del SDK, puedes acceder al dashboard de AppsFlyer y, desde la página de Pruebas de Integración del SDK, probar instalaciones orgánicas y no orgánicas, eventos in-app y deep linking (retargeting). Esto asegura que las instalaciones y los eventos in-app se registren y atribuyan correctamente.

Para conocer los escenarios de prueba y las instrucciones, consulta <Anchor target="_blank" href="/marketers/es/docs/testing-the-sdk-integration-for-marketers">Prueba de integración del SDK</Anchor>.

**Nota:** Al realizar pruebas de atribución, <Anchor target="_blank" href="/marketers/es/docs/registering-test-devices">registra un dispositivo de prueba</Anchor> (Android o iOS) para asegurarse de que cada instalación se registre como una nueva instalación. Un dispositivo de prueba registrado evita que las instalaciones se registren como reinstalaciones.

> 📘 **Note**
>
> **Ver también**
>
> * Descripción general de las plataformas CTV, PC y consolas

<div data-zendesk-anchors="retrieving-the-dev-key=implementaci%C3%B3n-de-la-clave-de-desarrollo-en-tu-aplicaci%C3%B3n h_01HAWCK9K4QBRE74JAS8Q7MEXW=implementaci%C3%B3n-de-la-clave-de-desarrollo-en-tu-aplicaci%C3%B3n retrieve-the-dev-key=recuperar-la-clave-de-desarrollo h_01HHHKTARNPQTBXQ6CQGEHMJRG=recuperar-la-clave-de-desarrollo embed-the-dev-key=proporciona-la-clave-de-desarrollo-a-tu-desarrollador h_01HHHKXMBGV6EM0CCW842RQQZ6=proporciona-la-clave-de-desarrollo-a-tu-desarrollador where-to-start-the-sdk=d%C3%B3nde-iniciar-el-sdk h_01HAWCK9K4MBS0F0HE6QE1W1AN=d%C3%B3nde-iniciar-el-sdk starting-the-sdk-in-android=iniciando-el-sdk-en-android-nativo h_01HAWCK9K45HCJEDRW761WHKES=iniciando-el-sdk-en-android-nativo select-in-what-class-to-start-the-sdk=selecciona-en-qu%C3%A9-clase-iniciar-el-sdk h_01HAWCK9K428SDFBFCCSZ15X9J=selecciona-en-qu%C3%A9-clase-iniciar-el-sdk android-developer-instructions=instrucciones-para-desarrolladores-de-android h_01HAWCK9K4XR1HZHP7Y15Q2Q4N=instrucciones-para-desarrolladores-de-android h_01HAWCK9K4693729EX1WYFR6XT=starting-the-sdk-in-ios h_01HAWCK9K4QSBP874RX2ZRA7EB=delay-the-sdk-start-in-ios h_01HAWCK9K4VHDFB9CYHC144BZN=ios-developer-instructions h_01JQ73M8DWMVQ98V1DQMPT0316=starting-the-sdk-in-Unity h_01JQ73M8DW350GBH9P52W4516V=starting-the-sdk-in-react select-the-optoutin-scenario::ae4c6e25=elige-tu-estrategia-de-preservaci%C3%B3n-de-la-privacidad h_01HAWCK9K4EXBA2F0BPVBXFAMG=elige-tu-estrategia-de-preservaci%C3%B3n-de-la-privacidad attribution=atribuci%C3%B3n h_01HAWCK9K41T5GGWDB3ABYGRHW=atribuci%C3%B3n google-play-install-referrer=referencia-de-instalaci%C3%B3n-de-google-play h_01HAWCK9K4V91MPQHXDZBD0HKR=referencia-de-instalaci%C3%B3n-de-google-play gaid=gna-company h_01HAWCK9K4YD8CYQDB2YRA8W1F=gna-company waitforattuserauthorization-overview=vista-general-de-waitforattuserauthorization h_01HAWCK9K5JHDWS8KTBTTGSS9G=vista-general-de-waitforattuserauthorization recording-inapp-events=registro-de-eventos-in-app h_01HAWCK9K5ZZYQR8KPCWANZEA5=registro-de-eventos-in-app deep-linking-with-onelink=deep-linking-con-onelink h_01HAWCK9K5PK9RE7WZQVCY97KC=deep-linking-con-onelink accessing-attribution-and-deep-linking-data=acceso-a-datos-de-atribuci%C3%B3n-y-de-deep-linking h_01HAWCK9K5ACPZ2WKBTVR3VVTD=acceso-a-datos-de-atribuci%C3%B3n-y-de-deep-linking testing-your-sdk-integration=prueba-de-integraci%C3%B3n-del-sdk h_01HAWCK9K6JQ33T32RYKYH20P1=prueba-de-integraci%C3%B3n-del-sdk" />
