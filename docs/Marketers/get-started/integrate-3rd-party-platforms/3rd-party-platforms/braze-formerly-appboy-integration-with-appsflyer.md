---
title: Integración de Braze (anteriormente Appboy) con AppsFlyer
metadata:
  keywords:
    - Appboy
    - Advertisers
    - Ad Networks
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
  created_at: '2017-03-30T08:39:03Z'
  edited_at: '2026-08-22T00:10:52Z'
  id: 115001603343
  locale: es
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/es/articles/115001603343
---
> **At a glance:** Braze, un partner integrado de AppsFlyer, ofrece una plataforma de participación durante el ciclo de vida para equipos de marketing, crecimiento y participación. La plataforma permite a los marketers conectarse de persona a persona, a gran escala, con sus clientes, impulsando un engagement profundo y un ROI. El centro de nuestra plataforma es el perfil de usuario holístico, que proporciona una visión única del cliente.

Aprender más en <Anchor target="_blank" href="https://www.braze.com/">braze.com</Anchor>.

> 🚧 **Important**
>
> **Notas importantes**
>
> * <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions#restricciones-de-fuente-de-medios">Algunas fuentes de medios</Anchor> restringen el intercambio de datos con terceros. Por lo tanto, los postbacks para eventos restringidos no se enviarán a este partner, independientemente de la selección configurada para enviar postbacks.
> * No se enviarán postbacks si la fuente es orgánica.

<div id="integration-overview" />

## Resumen general de la integración

Siga las instrucciones a continuación para configurar la integración con Braze.

Requisitos mínimos - SDK de AppsFlyer:

* <Anchor target="_blank" href="/marketers/es/docs/sdk-integration-overview">Android</Anchor> (Android SDK – versión 2.3.1.18 y superiores)
* <Anchor target="_blank" href="/marketers/es/docs/sdk-integration-overview">apps de iOS,</Anchor>

En Android, la integración con Braze requiere que el <Anchor target="_blank" href="https://www.braze.com/docs/partners/advertising_technologies/attribution/appsflyer/#integration">ID del dispositivo</Anchor> Braze (identificador de usuario único de Braze) se complete en el SDK de Android de AppsFlyer. Este parámetro se envía con cada postback y permite la identificación de cada usuario. Para realizar esto debes insertar las siguientes cadenas en el código de tu aplicación:

> 📘 **Note**
>
> **Nota Importante**
>
> Asegúrate de que las líneas de código se inserten en el lugar correcto: después de iniciar Braze SDK y antes del código de inicialización de AppsFlyer SDK (consulta la sección Inicialización del SDK en nuestra Guía de integración de Android SDK).

<Tabs>
<Tab title="Android">

```java
HashMap<String, Object> customData = new HashMap<String,Object>();
String deviceId =(Braze.getInstance(MyActivity.this).getDeviceId());
customData.put("brazeCustomerId", deviceId);
AppsFlyerLib.getInstance().setAdditionalData(customData);
```

</Tab>

<Tab title="apps de iOS,">

**Swift**

Hay dos API de Swift, una con un controlador de finalización y otra que utiliza el nuevo soporte de concurrencia de Swift. Ambos producen el mismo valor: la elección de cuál utilizar depende del contexto.

**Controlador de finalización Swift**

```swift
let configuration = Braze.Configuration(
    apiKey: "<BRAZE_API_KEY>",
    endpoint: "<BRAZE_ENDPOINT>")
configuration.useUUIDAsDeviceId = false
let braze = Braze(configuration: configuration)
braze.deviceId {
    brazeDeviceId in
    AppsFlyerLib.shared().customData = ["brazeDeviceId": brazeDeviceId]
}
```

**En espera de Swift**

```swift
let configuration = Braze. Configuration(
    apiKey: "<BRAZE_API_KEY>",
    endpoint: "<BRAZE_ENDPOINT>")
configuration.useUUIDAsDeviceId = false
let braze = Braze(configuration: configuration)
let brazeDeviceId = await braze.deviceId()
AppsFlyerLib.shared().customData = ["brazeDeviceId": brazeDeviceId]
```

**Objective-C**

```objectivec
BRZConfiguration *configurations = [[BRZConfiguration alloc] initWithApiKey:@"BRAZE_API_KEY" endpoint:@"BRAZE_END_POINT"];
[configurations setUseUUIDAsDeviceId: NO];
Braze *braze = [[Braze alloc] initWithConfiguration:configurations];
[braze deviceIdWithCompletion:^(NSString * _Nonnull brazeDeviceId) {
    NSLog(@">>[BRZ]: %@", brazeDeviceId);
    [[AppsFlyerLib shared] setAdditionalData:@{
        @"brazeDeviceId": brazeDeviceId
    }];
}];
```

</Tab>

<Tab title="Unity">

```csharp
Appboy.AppboyBinding.getDeviceID()
Dictionary<string, string> customData = new Dictionary<string, string>();
customData.Add("brazeCustomerId", Appboy. AppboyBinding.getDeviceId());
AppsFlyer.setAdditionalData(customData);
```

</Tab>
</Tabs>

<div id="setting-up-braze" />

## Configuración de Braze

**Requisito previo:** Antes de configurar la integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Para activar o editar la integración:**

1. En AppsFlyer, ve a la pestaña **Collaborate > Partner Integrations > Marketplace**.  
   (**Para editar una integración existente:** Ve a la pestaña **Collaborate > Partner Integrations > Active integrations**.)
2. Selecciona la aplicación correspondiente.
3. En la pestaña **Integración**, selecciona la aplicación para la integración y activa **Activar partner**.
4. En la pestaña **Integración**, activa el selector **Activate partner**.  
   **Nota:** El selector **debe permanecer activado (activo) mientras trabajes con el partner**. <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">Saber más</Anchor>
5. Completa la configuración utilizando las pestañas correspondientes, como se describe a continuación. Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integraciones de Partners</Anchor>.

<Accordion title="Pestaña Integración">

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

<div id="activate-partner" />

### Activar partner

En la **primera visita** aquí, debes ***Activar el Partner*** para habilitar la configuración de los parámetros de la pestaña de integración. El selector debe estar activado mientras trabajes con el partner.  
Para obtener más detalles sobre la activación de partners, haz clic <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">aquí</Anchor>.

<div id="general-settings" />

### Configuración general

Braze se conecta con AppsFlyer a través de una clave API única y un punto final REST.

**Para obtener la clave API y el punto final REST de Braze:**

1. En tu cuenta de Braze, en **Technology Partners,** ve a **Atribución**.
2. Selecciona**AppsFlyer**.  ![Selecciona AppsFlyer como partner tecnológico en Braze](https://files.readme.io/db96e8b5e2363f5250c6c1146a1f7a15e1ed6457fe4543dbe649f8818bb5db78-360017328637.png)
3. En **Data Import for Install Attribution**, haz clic en Generate API Key.
4. ¡Importante!
5. En AppsFlyer, inserta la clave API de Braze y el punto final REST.  ![Introduce la clave API y el endpoint REST de Braze en AppsFlyer](https://files.readme.io/b13aba84c394c0b4603e0aad2edd723525dadf204250349620b571bc47b0ba9d-360001907229.png)
6. Haz clic en **Guardar y Cerrar**.

Una vez que haya guardado la configuración, AppsFlyer envía los siguientes datos a Braze para cada instalación orgánica y no orgánica:

* Identificación de desarrollador de Braze
* Fuente de medios
* Nombre de la campaña
* Nombre adgroup
* Nombre de anuncio

<div id="default-postbacks" />

### Postbacks predeterminados

AppsFlyer puede enviar postbacks automáticos a las instalaciones de usuarios de Braze. Usa esta sección para definir el envío de estos postbacks.

 <Image align="center" alt="Sección de postbacks predeterminados" src="https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png" />

Selecciona **Eventos atribuidos a cualquier partner u orgánico** para enviar postbacks a Braze para cualquier usuario que descargue la aplicación.

Haz clic en **Save** (Guardar).

> 📘 **Note**
>
> **Nota:**
>
> Aunque todos los eventos son enviados por AppsFlyer, Braze no cuenta las instalaciones orgánicas y, por lo tanto, la API de Braze las ignora.

</Accordion>

<Accordion title="Pestaña de enlace de atribución">

Los enlaces de atribución no están disponibles para Braze.

</Accordion>

<Accordion title="Pestaña de costo">

Los datos de costos no son compatibles con la integración con este partner.

</Accordion>

<Accordion title="Pestaña de ingresos por publicidad">

Los ingresos por publicidad no se admiten en la integración con este partner.

</Accordion>

<Accordion title="Pestaña de permisos">

Los permisos no están disponibles para Braze.

</Accordion>

<div id="viewing-user-attribution-data-in-braze" />

## Visualización de datos de atribución de usuarios en Braze

Su base de usuarios se puede segmentar por datos de atribución en el panel de Braze utilizando los filtros de atribución de instalación.

 <Image align="center" alt="Filtros de atribución de instalación en el dashboard de Braze" src="https://files.readme.io/7289491d4d301eb38618298536ac5b895a610024bf162c733409d3f50b10b8f4-360001908045.png" />

Además, los datos de atribución de un usuario en particular están disponibles en el perfil de cada usuario en el panel de control de Braze.

 <Image align="center" alt="Datos de atribución en un perfil de usuario de Braze" src="https://files.readme.io/d9ee5206a8bf3c092c5297c361cf38b2c77717fbb9638b282032e4fc4c31091e-360001907289.png" />

<div data-zendesk-anchors="integration-overview=resumen-general-de-la-integraci%C3%B3n h_01H9FK453A9W5DCPR4X8PR06MZ=resumen-general-de-la-integraci%C3%B3n setting-up-braze=configuraci%C3%B3n-de-braze h_01H9FK453AWXF006KEVKD797QF=configuraci%C3%B3n-de-braze activate-partner=activar-partner h_01H9FK453AVK4YKF41FEP0YRJN=activar-partner general-settings=configuraci%C3%B3n-general h_01H9FK453AG6AXA7J43X6NGZT1=configuraci%C3%B3n-general default-postbacks=postbacks-predeterminados h_01H9FK453ASAKVHT7GV8BG56YS=postbacks-predeterminados viewing-user-attribution-data-in-braze=visualizaci%C3%B3n-de-datos-de-atribuci%C3%B3n-de-usuarios-en-braze h_01H9FK453AQXG7NNT2841686MJ=visualizaci%C3%B3n-de-datos-de-atribuci%C3%B3n-de-usuarios-en-braze" />
