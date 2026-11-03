---
title: Integración de Airship con AppsFlyer
metadata:
  keywords:
    - Attribution
    - SDK
    - Configure
    - urban airship
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
  created_at: '2015-12-16T11:31:38Z'
  edited_at: '2026-08-12T11:58:25Z'
  id: 207033976
  locale: es
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/es/articles/207033976
---
> **En resumen:** Airship, partner integrado de AppsFlyer, proporciona la principal plataforma de engagement móvil del mundo y ayuda a miles de empresas de todos los tamaños a establecer una conexión directa y duradera con sus clientes. Con Airship, las empresas obtienen un control total de su presencia móvil —apps, wallets y datos a nivel de usuario— para ofrecer experiencias que llamen la atención e impulsen la acción en móvil o en cualquier otro punto de contacto con el cliente.

> 🚧 **Importante:**
>
> <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions#restricciones-de-fuente-de-medios">Algunas fuentes de medios</Anchor> restringen el intercambio de datos con terceros. Por lo tanto, los postbacks para eventos restringidos no se enviarán a este partner, independientemente de la selección configurada para enviar postbacks.

## Configuración de Airship

**Requisito previo:** Antes de configurar la integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con él. Antes de configurar una integración, asegúrate de <Anchor target="_blank" href="/marketers/es/docs/partner-integrations#contact-details">contactar al partner</Anchor> y abrir una cuenta con este.

**Para activar o editar la integración:**

1. **Para activarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Partner Marketplace**.  
   **Para editarla:** en AppsFlyer, en el menú lateral, selecciona **Colaborar**> **Integraciones activas**.
2. Selecciona la aplicación correspondiente.
3. Haz clic en **Configurar integración**.
4. En la **primera visita** aquí, deberás activar **Activar partner** para habilitar la configuración de los parámetros de integración. El selector debe estar activado mientras trabajes con Medialyzer. Aprende más sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activación de partners</Anchor>.
5. Completa la configuración utilizando las pestañas correspondientes, como se describe en la sección a continuación:

<div id="integration-tab" />

<Accordion title="Pestaña de Integración">

La pestaña Integración está dividida en distintas secciones, tal como se describe a continuación.

### Activar socio

En la **primera visita** aquí, tendrás que activar **Activar partner** para habilitar la configuración de los parámetros de la pestaña de integración. **El selector debe estar activado mientras trabajes con el partner**.  
Aprende más sobre la <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">activación de partners</Anchor>.

### Configuración general

Airship se conecta con AppsFlyer mediante una App Key y un token únicos. Si aún no los tienes, puedes obtenerlos en Airship para continuar con la integración o consultar las instrucciones que aparecen más abajo para saber cómo obtenerlos.

![airship-integration-tab.png](https://files.readme.io/dc33feec09fe551700586b9778a037fa0f5d610224944aea5a0fe56a6d288043-360017400878.png)

**Para configurar la integración con Airship:**

Requisitos mínimos - SDK de AppsFlyer:

* Android – versión 2.3.1.18 y superior
* iOS – versión 3.3.3 y superior

Requisitos mínimos: SDK de Airship, versión 13.1.0 y superior.

1. La integración con Airship requiere que el channelid (identificador de usuario único de Airship) se complete en el SDK de AppsFlyer.

   * [Más información sobre el ID de canal para iOS](https://docs.airship.com/platform/ios/segmentation/#airship-channel-ids).
   * [Más información sobre el ID de canal para Android](https://docs.airship.com/platform/android/segmentation/#airship-channel-ids).

   Este parámetro se envía con cada postback y permite la identificación de cada usuario. Para realizar esto debes insertar las siguientes cadenas en el código de tu aplicación:

   > 📘 **Nota Importante**
   >
   > Asegúrate de que las líneas de código se insertan en el lugar correcto: después de iniciar el SDK de Airship y antes de que se llame al método start en iOS o Android.


   <Tabs>
   <Tab title="Android">

   Para obtener más información sobre el método  `setAdditionalData` method, haz clic <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata">aquí</Anchor>.

   ```java
   HashMap<String, Object> customData = new HashMap<String,Object>();
   String channelId = UAirship.shared().getChannel().getId();
   customData.put("channelid", channelId);
   AppsFlyerLib.getInstance().setAdditionalData(customData);
   ```

   </Tab>

   <Tab title="iOS">

   Para obtener más información sobre el método  `setAdditionalData` method, haz clic <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#customdata">aquí</Anchor>.

   ```objectivec
   let channelID = UAirship.channel().identifier
   print("My Application Channel ID: \(channelID)")
   ```

   </Tab>
   </Tabs>

2. Obtén la App Key de Airship:
   1. Accede a tu cuenta de Airship en: [go.airship.com](http://go.urbanairship.com/)
   2. En el menú de la izquierda, ve a **Settings >** **APIs &** **Integrations** y haz clic en **Airship API**.

      ![airship-appkey-en_us.png](https://files.readme.io/c33611035d8dcadb73e41a3787690726608bddde55edbc38f34990c03948985d-360017666917.png)
   3. Copia la App Key.
   4. En AppsFlyer, pega la App Key en el campo App Key.
3. Obtén el token de Airship:
   1. Accede a tu cuenta de Airship en: [go.airship.com](http://go.urbanairship.com/)
   2. En el menú de la izquierda, ve a **Settings >** **APIs &** **Integrations** y haz clic en **Tokens**.

      ![airship-token-creation-1.png](https://files.readme.io/b0c22d9844dbc93f7dd158a75916eca98404474a65be0c1528f83e6e4ac7b210-360017480697.png)
   3. Haz clic en **Create Token**.

      ![airship-token-creation-2.png](https://files.readme.io/656f6f5a6eebe3ccd1a786f6abec62739633e4150722fec41bc1fbdea78f8275-360017549138.png)
   4. Introduce el nombre del token y selecciona el rol.
   5. Haz clic en **Crear token**.
   6. En AppsFlyer, pega el Token en el campo **Token Authentication**.

### Postbacks predeterminados

AppsFlyer puede enviar postbacks automáticos a Airship tras las instalaciones de usuarios y los re-engagements. Utiliza esta sección para definir el **origen de los usuarios** que permiten enviar estos postbacks.

![urban_airship_msc_new_3.png](https://files.readme.io/394dd47ff26742092f3012e333f137d706f41bc85cd6875013d792ce7f36b01d-360001900305.png)

Selecciona **Events attributed to any partner or organic** para enviar postbacks a Airship para cualquier usuario que descargue la app.

Una vez que hayas guardado la configuración, AppsFlyer envía los siguientes datos a Airship para cada instalación orgánica y no orgánica:

* ID de dispositivo (IDFA / ID de publicidad de Google)
* Fuente de medios
* Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Pestaña de enlaces de atribución">

Los enlaces de atribución no están disponibles para Airship.

</Accordion>

<div id="cost-tab" />

<Accordion title="Pestaña de costos">

Los datos de costos no son compatibles con la integración con este partner.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Pestaña de Ingresos publicitarios">

Los ingresos por publicidad no se admiten en la integración con este partner.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Pestaña de permisos">

Los permisos no están disponibles para Airship.

</Accordion>

## Configura y gestiona los datos de atribución en la consola de Airship

En Airship, los atributos son pares clave-valor que asocias con tu audiencia para ayudarte a hacer targeting con mensajes de forma más eficaz. Usa atributos para segmentar audiencias con mayor precisión que con etiquetas.

Configura tus datos de atribución de AppsFlyer en Airship [añadiendo atributos individuales a tu proyecto](https://docs.airship.com/partners/appsflyer/#setting-attributes-for-integration).

<div data-zendesk-anchors="h_01H9FJYKH3V1TZ4GYEKKG46F2S=importante setting-up-airship=configuraci%C3%B3n-de-airship h_01H9FJYKH3SWMNC8CRPPDQMCGQ=configuraci%C3%B3n-de-airship h_01H9FJYKH4KQMK2N5BTTFTY076=integration-tab activate-partner=activar-socio h_01H9FJYKH4NTCNVKBW9XSENFTP=activar-socio general-settings=configuraci%C3%B3n-general h_01H9FJYKH4MMRE57BNEBD0P5NT=configuraci%C3%B3n-general h_01H9FJYKH4H93Q5S41HK7S4RD6=nota-importante default-postbacks=postbacks-predeterminados h_01H9FJYKH44F4YQSEPKTGN7EYK=postbacks-predeterminados h_01H9FJYKH44S8F34YJ97TE32PM=attribution-link-tab h_01H9FJYKH47DYTR8T197CEXH0Z=cost-tab h_01H9FJYKH46AC5X7F6GAD9MQJG=ad-revenue-tab h_01H9FJYKH4N4T5JTGWHQC0A18Z=permissions-tab set-up-and-manage-the-attribution-data-in-airship-console=configura-y-gestiona-los-datos-de-atribuci%C3%B3n-en-la-consola-de-airship h_01H9FJYKH4Q09JSBJ25RRE02Y3=configura-y-gestiona-los-datos-de-atribuci%C3%B3n-en-la-consola-de-airship" />
