---
title: Métodos de preservación de la privacidad en el SDK
metadata:
  keywords:
    - Advertisers
    - coppa
    - opt-out
    - opt out
    - consent management
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
  created_at: '2018-08-20T11:14:36Z'
  edited_at: '2026-08-22T00:32:41Z'
  id: 360001422989
  locale: es
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/es/articles/360001422989
---
> **At a glance:** Preserva la privacidad de tus usuarios con uno o más de los métodos disponibles a través del SDK de AppsFlyer.

> 📘 **Note**
>
> **Nota:**
>
> La información presentada en este artículo está destinada únicamente a proporcionar insights sobre los métodos disponibles para los desarrolladores de aplicaciones para controlar el intercambio de datos relacionados con el usuario con propietarios de aplicaciones, redes publicitarias y redes sociales. **Este artículo no incluye ni constituye una guía sobre el cumplimiento de normativas de privacidad como la COPPA o el RGPD, ni de ninguna normativa específica de preservación de la privacidad.**

El SDK de AppsFlyer ofrece a los propietarios de aplicaciones varios métodos para proteger la privacidad del usuario y controlar los datos. En este artículo, exploraremos estos métodos y evaluaremos cómo afectan los datos del usuario y cómo usarlos para preservar la privacidad del usuario sin dejar de permitir la atribución.

Después de considerar qué opciones deseas utilizar, comparte la información de implementación en nuestro Dev Hub con tus desarrolladores.

Analicemos cada método.

## Usar métodos de start y stop

El SDK envía instalaciones y eventos in-app a AppsFlyer solo después de que se llama al método de `start`. Cualquier evento que preceda a la llamada de `start` no será reportado por el SDK. De manera similar, si la llamada de `start` se invierte posteriormente invocando el método `stop`, no se enviarán eventos a partir de entonces.

### Impacto en la atribución

La atribución **no** ocurre cuando:

* no se llama al método de `start`.
* se llama al método `stop` para revertir un inicio anterior.

### Casos de uso comunes

| Caso de uso | Descripción |
| --- | --- |
| Opt-in o opt-out en la apertura | El `start` de llamada después de que el usuario acepte compartir datos en la primera apertura.  <br />Si el usuario no da su consentimiento para compartir datos, no llames   <br />`start`. |
| Opt-out de la sesión | En cada sesión de la aplicación, solicita su consentimiento y llama o no a `start` en consecuencia. |
| Opt-out única (cuando un usuario opta por el opt-in y luego decide cambiar). | El `stop` de la llamada evita que el SDK envíe más eventos. |

### Referencia del desarrollador

Para referencia del desarrollador y documentación sobre cómo usar los métodos de start y stop, consulta:

<Tabs>
<Tab title="Android">

[Utiliza start para compartir solo el evento de instalación](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-android#use-start-to-share-only-the-install-event)

</Tab>

<Tab title="apps de iOS,">

[Utiliza start para compartir solo el evento de instalación](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-ios#use-start-to-share-only-the-install-event)

</Tab>
</Tabs>

## Evita el uso compartido de datos con las redes

En el momento de la integración con una red de anuncios o una red de autoreporte (SRN), puedes optar por compartir o no compartir información a nivel de usuario con ese partner. En el SDK, puedes filtrar aún más el uso compartido de datos con todos o algunos asociados de negocios de **acuerdo con las preferencias del usuario final** mediante el método `setSharingFilterForPartners`.

Cuando utilizas este método, AppsFlyer deshabilitará el intercambio de datos del usuario con el partner excluido por cualquier medio, incluidos postbacks, APIs, reportes de raw data, etc.

### Impacto en la atribución

* Las instalaciones **de ad networks excluidas** **(non-SRNs)** se atribuyen en AppsFlyer, pero las ad networks no recibirán ninguna notificación de ningún tipo.
* Las instalaciones **de SRN excluidos** no se atribuyen y sus datos no se comparten con tus Partners integrados. Esto no se aplica a los **SRN avanzados**, donde la Atribución sigue siendo posible; sin embargo, las instalaciones, los re-engagements y los eventos in-app no se compartirán debido al filtro de compartición.

  > 📘 **Note**
  >
  > **Nota:**
  >
  > AppsFlyer no puede atribuir datos de engagement a ningún SRN excluido de la obtención de tus datos.


### Referencia del desarrollador

Para referencia del desarrollador y documentación sobre cómo evitar el intercambio de datos con terceros, consulta:

<Tabs>
<Tab title="Android">

[Impide compartir datos con terceros](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-android#prevent-sharing-data-with-third-parties)

</Tab>

<Tab title="apps de iOS,">

[Impide compartir datos con terceros](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-ios#prevent-sharing-data-with-third-parties)

</Tab>
</Tabs>

## Anonimiza la información del usuario

Puedes configurar el SDK para indicar a AppsFlyer que elimine toda la información que identifique al usuario mediante el método `anonymizeUser`. En este caso, el SDK envía instalaciones y eventos in-app a AppsFlyer, donde toda la información de identificación se elimina o se aplica hash:

* **Eliminados:** identificadores personales (GAID, IDFA, IDFV y CUID)
* **Hashed:** ID de AppsFlyer y dirección IP

La siguiente imagen muestra una fila de ejemplo de raw data después de la anonimización (eliminación y hash).

![Ejemplo de fila de raw data que muestra campos eliminados y con Hashing tras la anonimización](https://files.readme.io/5cae15ee0e38c84b2f9876d0dca2145543e83e624933ca138017da5206e7a834-35847868223633.png)

### Impacto en la atribución

Si llamas a `anonymizeUser` antes de llamar a `start`, la atribución no puede usar identificadores de dispositivo ni la dirección IP del dispositivo. Como resultado, no se aplican los métodos de atribución estándar basados en estos identificadores.

Sin embargo, la atribución puede seguir produciéndose mediante los siguientes métodos, que no dependen de identificadores de dispositivo:

* <Anchor target="_blank" href="/marketers/es/docs/self-reporting-networks-srns#atribución">Atribución de red de autorreporte (SRN)</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model#probabilistic-modeling">Modelado probabilístico (PMOD)</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model#install-referrer-android-only">Atribución basada en el referrer</Anchor>

Para atribuir el evento de instalación, llama a la función `anonymizeUser` solo después de confirmar que el SDK ha enviado el evento de instalación a AppsFlyer.

Este flujo garantiza que:

* El evento de instalación se puede atribuir con normalidad.
* Todos los eventos in-app que se produzcan después de llamar a `anonymizeUser` se envían **sin identificadores**.

Como resultado, estos eventos in-app se contabilizan como **orgánicos** o se **descartan**, según el método de generación de informes.

> 📘 **Note**
>
> **Nota:**
>
> Se admiten <Anchor target="_blank" href="/marketers/es/docs/self-reporting-networks-srns#atribución">SRN</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model#probabilistic-modeling">PMOD (probabilístico)</Anchor> y <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model#install-referrer-android-only">Atribución basada en el referrer</Anchor> en modo anonimizado. Esto incluye <Anchor target="_blank" href="/marketers/es/docs/basic-sdk-integration-guide#referencia-de-instalación-de-google-play">Google Play Install Referrer</Anchor>, otros referrers de tiendas (como <Anchor target="_blank" href="/marketers/es/docs/set-up-multi-store-android-attribution#referrer-implementation-thirdparty-android-app-stores">Xiaomi, Huawei,</Anchor> <Anchor target="_blank" href="/marketers/es/docs/set-up-appsflyer-preload-referrer-attribution#referencia-de-precarga-de-samsung">y Samsung</Anchor>) y <Anchor target="_blank" href="/marketers/es/docs/set-up-appsflyer-preload-referrer-attribution?utm_source=chatgpt.com">AppsFlyer preload referrer</Anchor>

### Referencia del desarrollador

Para referencia del desarrollador y documentación sobre cómo anonimizar la información del usuario, consulte:

<Tabs>
<Tab title="Android">

[Anonimizar información del usuario](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-android#anonymize-user-information)

</Tab>

<Tab title="apps de iOS,">

[Anonimiza la información del usuario](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-ios#anonymize-user-information)

</Tab>
</Tabs>

## Elimina identificadores de dispositivos específicos

Puedes evitar que el SDK recopile y envíe identificadores de dispositivo específicos a AppsFlyer. A diferencia de usar el método `anonymizeUser`, deshabilitar identificadores específicos te permite decidir los identificadores que desea conservar.

La API del SDK incluye los siguientes métodos para deshabilitar identificadores.

### Identificadores de Android

| Método | Identificadores desactivados |
| --- | --- |
| [`Las instalaciones de los SRNs excluidos no se atribuyen y sus datos no se comparten con tus partners integrados.`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setdisableadvertisingidentifiers) | <ul><li>Google Advertising ID (GAID)</li><li>Open Anonymous Device Identifier (OAID)</li><li>Amazon Advertising ID (AAID)</li></ul> |
| [`setcollectoaid`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectoaid) | Open Anonymous Device Identifier (OAID) |

### Identificadores de iOS

| Método | Identificador deshabilitado |
| --- | --- |
| [`Si llamas a anonymizeUser antes del start de la llamada, no se producirá ninguna atribución.`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disableadvertisingidentifier) | IDFA (iOS 13 y anteriores) |
| [`disableIDFVCollection`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disableidfvcollection) | IDFV |

### Referencia del desarrollador

Para la referencia del desarrollador y la documentación sobre cómo eliminar identificadores de dispositivos específicos, consulta:

<Tabs>
<Tab title="Android">

[Deshabilitar IDs](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-android#disable-ids)

</Tab>

<Tab title="apps de iOS,">

[Deshabilitar IDs](https://dev.appsflyer.com/hc/docs/preserve-user-privacy-ios#disable-ids)

</Tab>
</Tabs>

> 📘 **Note**
>
> **¿Tienes preguntas sobre la privacidad en AppsFlyer?**
>
> La relación de privacidad entre tú y AppsFlyer se rige por la [Declaración de AppsFlyer sobre el Tratamiento de Datos](https://www.appsflyer.com/legal/processing-customer-data/). Si tienes alguna pregunta relacionada con esta declaración o para ponerte en contacto con nuestro responsable de protección de datos, envía un correo electrónico a [dpo@appsflyer.com](mailto:dpo@appsflyer.com).

<div data-zendesk-anchors="use-start-and-stop-methods=usar-m%C3%A9todos-de-start-y-stop h_01HKD1N2C8V0SP1NG8W2EJPRQZ=usar-m%C3%A9todos-de-start-y-stop impact-on-attribution=impacto-en-la-atribuci%C3%B3n h_01HKD1N2C80QAJSNE83SD45DJA=impacto-en-la-atribuci%C3%B3n common-use-cases=casos-de-uso-comunes h_01HKD1N2C8YHWYARRAGX1TD6DM=casos-de-uso-comunes developer-reference=referencia-del-desarrollador h_01HKM6VNJFCW77F2268XXDF65Q=referencia-del-desarrollador prevent-sharing-data-with-networks=evita-el-uso-compartido-de-datos-con-las-redes h_01HKD1N2C8ASV10XWY33R972MC=evita-el-uso-compartido-de-datos-con-las-redes impact-on-attribution::aa0a9f9e=impacto-en-la-atribuci%C3%B3n-1 h_01HKD1N2C8RA34M4TSWYCW3A9F=impacto-en-la-atribuci%C3%B3n-1 developer-reference::f2007ab7=referencia-del-desarrollador-1 h_01HKM6VNJFP8C7KCFSV1046H0B=referencia-del-desarrollador-1 anonymize-user-information=anonimiza-la-informaci%C3%B3n-del-usuario h_01HKD1N2C8CWSWK0VSXZ39MQ3D=anonimiza-la-informaci%C3%B3n-del-usuario anonymize-impact=impacto-en-la-atribuci%C3%B3n-2 h_01KK93D18X4QYG87CFMZWNHSBA=impacto-en-la-atribuci%C3%B3n-2 developer-reference::e4cacf1f=referencia-del-desarrollador-2 h_01HKM6VNJF7XPZ9ME61JG4KM9Z=referencia-del-desarrollador-2 remove-specific-device-identifiers=elimina-identificadores-de-dispositivos-espec%C3%ADficos h_01HKD1N2C8S3Y73AZ9J7JFDKQE=elimina-identificadores-de-dispositivos-espec%C3%ADficos android-identifiers=identificadores-de-android h_01HKD1N2C8HZ61XHMBC0JNTK7S=identificadores-de-android ios-identifiers=identificadores-de-ios h_01HKD1N2C8AHK4EYANG6N6ST06=identificadores-de-ios developer-reference::4e0971d1=referencia-del-desarrollador-3 h_01HKM6VNJFV0YJWV8KT23VTKKH=referencia-del-desarrollador-3" />
