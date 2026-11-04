---
title: Integración de Amplitude con AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Amplitude
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
  created_at: '2016-08-02T05:18:03Z'
  edited_at: '2026-09-11T00:10:25Z'
  id: 211200306
  locale: es
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/es/articles/211200306
---
> **At a glance:** Integra AppsFlyer con Amplitude para compartir datos de atribución de usuarios y análisis de eventos para obtener mejores insights sobre engagement, retención e ingresos de los usuarios. Elige entre **dos versiones de integración, V1 o V2**, según tu caso de uso y tus necesidades de análisis.

<div id="about-the-integration" />

## Sobre la integración

Amplitude, un partner integrado de AppsFlyer, es una plataforma de análisis de productos utilizada por equipos de producto, crecimiento y marketing para comprender el comportamiento del usuario en dispositivos móviles y web. La integración permite que AppsFlyer envíe datos clave de eventos a Amplitude después de la instalación, lo que permite un análisis integral a nivel de usuario.

Hay dos versiones de integración de Amplitude:

* **Amplitude V1:**  
  Esta versión utiliza la API de atribución de Amplitude. AppsFlyer envía datos de instalación recopilados después de que se completa la integración. Amplitude utiliza el ID de anuncio como identificador y descarta los datos si no se registra ningún evento de usuario coincidente dentro de las 72 horas. <Anchor target="_blank" href="https://amplitude.com/docs/apis/analytics/attribution">Saber más</Anchor>
* **Amplitude V2:**  
  Esta versión utiliza la API HTTP V2 de Amplitude. AppsFlyer envía tanto datos de instalaciones como de eventos in-app después de que se completa la integración. Los identificadores tienen prioridad (user\_id y device\_id), y si la coincidencia falla, se registra un nuevo usuario. <Anchor target="_blank" href="https://amplitude.com/docs/apis/analytics/http-v2">Saber más</Anchor>

<span id="h_01JSE81SX1FR182N1CZJ5CQP5N"></span>**<span id="integration-methods"></span>Versiones de integración:**

| Versión | API utilizada | Identificadores utilizados | Cobertura de eventos |
| --- | --- | --- | --- |
| **V1** | API de atribución | ID de publicidad (AdID) | Se instala el |
| **V2** | HTTP V2 API | `user_id`, `device_id` (lógica de respaldo) | Instalaciones y eventos in-app |

> 🚧 **Important**
>
> **Importante:**
>
> * Elige la integración Amplitude V1 o V2. **No uses ambos** simultáneamente. Usar ambas versiones al mismo tiempo puede resultar en eventos duplicados enviados a Amplitude.
> * Algunas fuentes de medios restringen el intercambio de datos con terceros. Los postbacks de eventos restringidos no se enviarán a este partner, incluso si están configurados.

<div id="prerequisites" />

## Requisitos previos

**Antes de empezar:**

* Contacta a Amplitude para crear una cuenta si aún no tienes una.
* Decide si configurarás la integración Amplitude **V1** o **V2**.
* Asegúrate de evitar enviar los mismos eventos desde el SDK de Amplitude y AppsFlyer para prevenir duplicaciones.
* Consulta el requisito adicional para la integración Amplitude V2.

<div id="additional-prerequisites-for-the-amplitude-v2-integration" />

### Requisitos adicionales para la integración Amplitude V2

La integración V2 requiere la configuración de:

* [ID de dispositivo de Amplitude](/docs/amplitude-integration-with-appsflyer#id-de-dispositivo-de-amplitude)
* [ID de usuario del cliente](/docs/amplitude-integration-with-appsflyer#id-de-usuario-del-cliente)
* [ID de sesión de Amplitude](/docs/amplitude-integration-with-appsflyer#id-de-sesión-de-amplitude)

<div id="amplitude-device-id" />

#### ID de dispositivo de Amplitude

Para habilitar la atribución a nivel de usuario, debes pasar el ID de dispositivo de Amplitude al SDK de AppsFlyer. Este valor se envía con cada postback.

<Tabs>
<Tab title="Android">

```java
AppsFlyerLib.getInstance().setAdditionalData("AmplitudeDeviceId", amplitude.getDeviceId())
```

**Idioma:** Java/Kotlin

**Documentación:** <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference#setadditionaldata">Referencia del SDK de Android</Anchor>, <Anchor target="_blank" href="https://amplitude.com/docs/sdks/analytics/android/android-kotlin-sdk#get-device-id">Amplitude</Anchor>

</Tab>

<Tab title="iOS (Objective-C)">

```objectivec
[[AppsFlyerLib shared] setAdditionalData:@{@"AmplitudeDeviceId": [[Amplitude instance] getDeviceId]}];
```

**Lenguaje:** Objective-C

**Documentación:** [Referencia del SDK de iOS](https://dev.appsflyer.com/hc/docs/ios-sdk-reference#setadditionaldata), <Anchor target="_blank" href="https://amplitude.com/docs/sdks/analytics/ios/ios-sdk#get-device-id">Amplitude</Anchor>

</Tab>

<Tab title="iOS (Swift)">

```swift
AppsFlyerLib.shared().customData = ["AmplitudeDeviceId": Amplitude.instance().getDeviceId()]
```

**Lenguaje:** Swift

**Documentación:** [Referencia del SDK de iOS](https://dev.appsflyer.com/hc/docs/ios-sdk-reference#setadditionaldata), <Anchor target="_blank" href="https://amplitude.com/docs/sdks/analytics/ios/ios-sdk#get-device-id">Amplitude</Anchor>

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> customData = new Dictionary<string, string>();
customData.Add("AmplitudeDeviceId", Amplitude.getInstance().getDeviceId());
AppsFlyer.setAdditionalData(customData);
```

**Lenguaje:** C#

**Documentación:** [Referencia del SDK de Unity](https://github.com/AppsFlyerSDK/appsflyer-unity-plugin)

</Tab>

<Tab title="React Native">

```javascript
appsFlyer.setAdditionalData({"AmplitudeDeviceId": amplitude.getDeviceId()},
(res) => {
//...
}
);
```

**Lenguaje:** JavaScript

**Documentación:** [Referencia del SDK de React Native](https://github.com/AppsFlyerSDK/appsflyer-react-native-plugin)

</Tab>

<Tab title="Cordova">

```javascript
appsFlyer.setAdditionalData({"AmplitudeDeviceId": amplitude.getDeviceId()});
```

**Lenguaje:** JavaScript

**Documentación:** N/A

</Tab>

<Tab title="Flutter">

```
var data = {"AmplitudeDeviceId": amplitude.getDeviceId()};
appsFlyerSdk.setAdditionalData(data);
```

**Lenguaje:** Dart

**Documentación:** [Referencia del SDK de Flutter](https://github.com/AppsFlyerSDK/appsflyer-flutter-plugin)

</Tab>
</Tabs>

<div id="customer-user-id" />

#### ID de usuario del cliente

Configura el ID de usuario de cliente (CUID). Este es un identificador único que generalmente se genera y se establece  
por el propietario de la aplicación durante el registro del usuario. <Anchor target="_blank" href="/marketers/es/docs/customer-user-id-field-cuid?utm_source=chatgpt.com">Saber más</Anchor>

<div id="amplitude-session-id" />

#### ID de sesión de Amplitude

Configura el ID de sesión de Amplitude y pásalo a AppsFlyer (opcional). <Anchor target="_blank" href="https://amplitude.com/docs/data/sources/instrument-track-sessions">Saber más</Anchor>

<Tabs>
<Tab title="Android">

```java
AppsFlyerLib.getInstance().setAdditionalData("AmplitudeSessionId", amplitude.getSessionId())
```

**Lenguaje:** Java/Kotlin

**Documentación:** [Referencia del SDK de Android](https://dev.appsflyer.com/hc/docs/android-sdk-reference#setadditionaldata)

</Tab>

<Tab title="iOS (Objective-C)">

```objectivec
[[AppsFlyerLib shared] setAdditionalData:@{@"AmplitudeSessionId": [[Amplitude instance] getSessionId]}];
```

**Lenguaje:** Objective-C

**Documentación:** [Referencia del SDK de iOS](https://dev.appsflyer.com/hc/docs/ios-sdk-reference#setadditionaldata)

</Tab>

<Tab title="iOS (Swift)">

```swift
AppsFlyerLib.shared().customData = ["AmplitudeSessionId": Amplitude.instance().getSessionId()]
```

**Lenguaje:** Swift

**Documentación:** [Referencia del SDK de iOS](https://dev.appsflyer.com/hc/docs/ios-sdk-reference#setadditionaldata)

</Tab>

<Tab title="Unity">

```csharp
Dictionary<string, string> customData = new Dictionary<string, string>();
customData.Add("AmplitudeSessionId", Amplitude.getInstance().getSessionId());
AppsFlyer.setAdditionalData(customData);
```

**Lenguaje:** C#

**Documentación:** [Referencia del SDK de Unity](https://github.com/AppsFlyerSDK/appsflyer-unity-plugin)

</Tab>

<Tab title="React Native">

```javascript
appsFlyer.setAdditionalData({"AmplitudeSessionId": amplitude.getSessionId()},
(res) => {
//...
}
);
```

**Lenguaje:** JavaScript

**Documentación:** [Referencia del SDK de React Native](https://github.com/AppsFlyerSDK/appsflyer-react-native-plugin)

</Tab>

<Tab title="Cordova">

```javascript
appsFlyer.setAdditionalData({"AmplitudeSessionId": amplitude.getSessionId()});
```

**Lenguaje:** JavaScript

**Documentación:** N/A

</Tab>

<Tab title="Flutter">

```
var data = {"AmplitudeSessionId": amplitude.getSessionId()};
appsFlyerSdk.setAdditionalData(data);
```

**Lenguaje:** Dart

**Documentación:** [Referencia del SDK de Flutter](https://github.com/AppsFlyerSDK/appsflyer-flutter-plugin)

</Tab>
</Tabs>

<div id="set-up-the-integration" />

## Configura la integración

**Para configurar la integración:**

1. En AppsFlyer, ve a **Collaborate** > **Partner Integrations > Marketplace** tab.
2. Para configurar la integración de Amplitude V1, selecciona **Amplitude V1** (Tech partner).

   <Image alt="Select Amplitude V1 doctored.png" src="https://files.readme.io/71721bb1a48dda061ce2a099522edf9baed39ef2d67edad8ac14277b42cd2d70-36713632837777.png" width="511px" />

   Para configurar la integración de Amplitude V2, selecciona **Amplitude V2** (Tech partner).

   <Image alt="Select Amplitude V2.png" src="https://files.readme.io/4bbf57727a2b6e16e5205505b459a78f8642f02d1bb1c4e8f72e26b3bd9e1bd3-36713631187857.png" width="503px" />
3. Una vez que hayas seleccionado tu versión de Amplitude, haz clic en **Configurar integración**.

   ![Click set up integration.png](https://files.readme.io/c13fef10fb4cf0ea12f44d56f8c3b64936376ce181a1d12c9f096ad6103c29a6-36713632857617.png)
4. En la pestaña de **Integración**:
   * Selecciona tu aplicación.
   * Activa el interruptor **Activar partner**.

     <Image alt="Activate partner blurred.png" src="https://files.readme.io/5e0e7ae537cd89b2c561c8561de9ebc160f6d6eb0fedc5c7ba0c761ddb73632a-36713631194641.png" width="521px" />
5. Completa la configuración en las pestañas restantes:

<Accordion title="Pestaña de Integración">

La pestaña Integración está dividida en diferentes secciones, tal como se describe a continuación.

<div id="activate-partner" />

### Activar partner

En tu **primera visita**, tendrás que activar **Activate Partner** para poder configurar los parámetros de la pestaña de integración. El conmutador debe estar activado mientras trabajes con el partner.  
Saber más sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activación de Partners</Anchor>.

<div id="general-settings" />

### Configuración general

<div id="advanced-data-sharing" />

#### Intercambio avanzado de datos

Para compartir información adicional de instalación con Amplitude, activa **Advanced data sharing**. Cuando se activa, Amplitude recibe los siguientes datos sobre las instalaciones (no eventos in-app) asignadas a la propiedad Amplitude indicada en la lista:

| Propiedad de Amplitude | Punto de datos de AppsFlyer |
| --- | --- |
| sub\_publisher | af\_siteid |
| network\_name | pid |
| adgroup\_name | af\_conjunto de anuncios |
| creative\_name | id\_del\_anuncio\_af |
| installed\_at | install\_timestamp |
| search\_term | af\_palabras\_clave |
| channel | af\_canal |
| user\_id | af\_customer\_user\_id |
| af\_sub1 | af\_sub1 |
| af\_sub2 | af\_sub2 |
| af\_sub3 | af\_sub3 |
| af\_sub4 | af\_sub4 |
| af\_sub5 | af\_sub5 |
| version\_app | version\_app |

<div id="amplitude-eu-data-center" />

#### Centro de Datos de Amplitude en la UE

Cuando el **Centro de Datos de Amplitude en la UE** está desactivado, los postbacks de instalación se envían al centro de datos de Estados Unidos.  
Para enviar postbacks de instalación al Centro de Datos de Amplitude en la UE, activa el Centro de Datos de Amplitude de la UE.

<div id="api-key" />

#### Clave API

Amplitude se conecta con AppsFlyer a través de una clave de API única. Si aún no la tienes, debes obtenerla de Amplitude para continuar con la integración o seguir los pasos que se indican a continuación.

<span id="obtaining-the-api-key-from-amplitude"></span>**Obtención de la clave API de Amplitude**

**Nota**: Solo los usuarios que tienen el rol de administrador o gerente en Amplitude pueden acceder a la clave de API.

1. Accede a tu cuenta de Amplitude.
2. Desde la parte superior derecha de la página, haz clic en el icono de configuración > **Configuración de la organización**.

   <Image alt="Amplitude" src="https://files.readme.io/214df773c045239924b65a4a1e6b0a1957f6b7ea09e225af80d83ffa0a469c26-16258070772625.png" width="240px" />
3. Haz clic en **Proyectos** y selecciona el proyecto desde el que enviarás datos a AppsFlyer.

   ![Amplitude](https://files.readme.io/eaf158e4505f47f8da0fdae4f97be773ab32910352b50cab5ca5d4de3e8782ac-16335170399505.png)
4. Desde la pestaña **Proyecto**, copia tu clave API.

   <Image alt="Amplitude" src="https://files.readme.io/cf65648a9a8c122febe2b36fd4bd0b9f7f436cac49cfeec7f41870f614a16c6c-16258070773649.png" width="648px" />
5. Continúa para configurar Amplitude en el dashboard de AppsFlyer.

<div id="default-postbacks" />

### Postbacks predeterminados

AppsFlyer puede enviar postbacks automáticos a Amplitude después de las instalaciones de usuarios, incluidas tanto las instalaciones como los re-engagements (incluidas las reatribuciones). Los re-engagements se producen cuando un usuario que ya tiene la app instalada la abre después de hacer clic en una campaña. Saber más sobre los <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#default-postbacks">postbacks predeterminados</Anchor>.

<Image alt="Screenshot 2025-12-03 at 1.57.03 PM.png" src="https://files.readme.io/3454ca573ee63ea076251459a9c619a747fc5640862e83582b2d10a985c2489a-41748033847953.png" width="703px" />

<div id="in-app-event-settings" />

### Configuración de eventos in-app

* Introduce la clave API.
* Cuando **Amplitude Data Center** está desactivado, los postbacks de eventos in-app se envían al centro de datos de Estados Unidos.  
  **Para enviar postbacks de eventos in-app al centro de datos de Amplitude en la UE, activa Amplitude Data Center.**

Una vez guardada la configuración, AppsFlyer envía los siguientes datos a Amplitude:

* ID de dispositivo (IDFV/ID de publicidad de Google)
* Media Source
* Nombre de la campaña

El envío del IDFA para dispositivos iOS está sujeto al <Anchor target="_blank" href="/marketers/es/docs/apply-aggregated-advanced-privacy-framework">consentimiento de ATT por parte del usuario y a la configuración de privacidad avanzada</Anchor>.

<div id="in-app-event-postbacks" />

### Postbacks de eventos in-app

<Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">Configura el envío de postbacks de eventos in-app</Anchor> a Amplitude.

</Accordion>

<Accordion title="Pestaña de enlaces de atribución">

Los enlaces de atribución no están disponibles para Amplitude.

</Accordion>

<Accordion title="Pestaña de costo">

Los datos de costos no son compatibles con la integración con este partner.

</Accordion>

<Accordion title="Pestaña de ingresos por publicidad">

Los ingresos por publicidad no se admiten en la integración con este partner.

</Accordion>

<Accordion title="Pestaña de permisos">

Los permisos no están disponibles para Amplitude.

</Accordion>

<div id="viewing-attribution-data-in-the-amplitude-console" />

## Visualización de datos de atribución en la consola de Amplitude

Los datos de atribución enviados desde AppsFlyer a Amplitude se muestran en tus dashboards como eventos y propiedades prefijados con **[AppsFlyer]**:

![amplitude-properties.png](https://files.readme.io/bf52831ea6060172ce251136f47962ffb7f1ec9ffce13b9e35c614c4178e77f1-360009623597.png)

> 🚧 **Important**
>
> **Importante:**
>
> En algunos casos, Amplitude muestra los datos procedentes de AppsFlyer como "Blocked". Si no puedes ver los datos de AppsFlyer en Amplitude, verifica si están definidos como evento bloqueado.

<div id="sending-amplitude-events-to-appsflyer" />

## Enviando eventos de Amplitude a AppsFlyer

La integración también permite enviar tus eventos de Amplitude a AppsFlyer a través de una API de servidor a servidor. Consulta la <Anchor target="_blank" href="https://www.docs.developers.amplitude.com/data/destinations/appsflyer/">documentación de Amplitude</Anchor> sobre cómo hacer esto.

<div data-zendesk-anchors="about-the-integration=sobre-la-integraci%C3%B3n h_01JSE81SX1B1RH978Y08W1XXX8=sobre-la-integraci%C3%B3n set-up-the-integration=requisitos-previos h_01JSE958V510B9P6VEQTXC55S7=requisitos-previos additional-prerequisites-for-the-v2-integration=requisitos-adicionales-para-la-integraci%C3%B3n-amplitude-v2 h_01JSKEMMEB00PERVQWPYNF5V2E=requisitos-adicionales-para-la-integraci%C3%B3n-amplitude-v2 amplitude-device-id=id-de-dispositivo-de-amplitude h_01JSKFH7KPSE5P0CRPVJ3FJ2WN=id-de-dispositivo-de-amplitude customer-user-id=id-de-usuario-del-cliente h_01JSKFK4BFH3PP98XAZ0W8GG11=id-de-usuario-del-cliente amplitude-session-id=id-de-sesi%C3%B3n-de-amplitude h_01JSKFQXPPJVCW68C4H9B4EJ76=id-de-sesi%C3%B3n-de-amplitude set-up-the-integration::45aa5acf=configura-la-integraci%C3%B3n h_01JSKFQAZ8Q76KF1JJKZTAPVBQ=configura-la-integraci%C3%B3n activate-partner=activar-partner 01H8KPA9JKDRA680Y0WPZ172EM=activar-partner general-settings=configuraci%C3%B3n-general 01H8KPA9JKF4VCA4S22SYT40WT=configuraci%C3%B3n-general advanced-data-sharing=intercambio-avanzado-de-datos 01H8KPA9JKJ2XN1AEPV74QVJYZ=intercambio-avanzado-de-datos amplitude-data-center=centro-de-datos-de-amplitude-en-la-ue 01H8KPA9JKP0T0FDND97VA23EY=centro-de-datos-de-amplitude-en-la-ue api-key=clave-api 01H8KPA9JKDYDPDGRXZSH2BAV8=clave-api 01H8KPA9JK510YKV47816DT7E7=obtaining-the-api-key-from-amplitude default-postbacks=postbacks-predeterminados 01H8KRBGYQ973CT3H8GHZ8R0BH=postbacks-predeterminados inapp-event-settings=configuraci%C3%B3n-de-eventos-in-app 01H8KPA9JKM4S79160BEYN3B6V=configuraci%C3%B3n-de-eventos-in-app inapp-event-postbacks=postbacks-de-eventos-in-app 01H8KSQ76XE9Z191P1RMANF6EQ=postbacks-de-eventos-in-app viewing-attribution-data-in-the-amplitude-console=visualizaci%C3%B3n-de-datos-de-atribuci%C3%B3n-en-la-consola-de-amplitude 01H8KPA9JK75TA0H8T4P65BMSE=visualizaci%C3%B3n-de-datos-de-atribuci%C3%B3n-en-la-consola-de-amplitude sending-amplitude-events-to-appsflyer=enviando-eventos-de-amplitude-a-appsflyer h_01HPYFZDX1WWDWJEBZ4DK706B4=enviando-eventos-de-amplitude-a-appsflyer" />
