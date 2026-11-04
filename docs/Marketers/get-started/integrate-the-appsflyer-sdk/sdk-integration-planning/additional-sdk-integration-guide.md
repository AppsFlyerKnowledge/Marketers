---
title: Guía adicional de integración del SDK
metadata:
  keywords:
    - iOS
    - Android
    - Integration
    - Advertisers
    - firetv
    - Advertiser
    - appuid
    - anonymous
    - kakao
    - Marketers
    - Web Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Web Attribution
  created_at: '2021-10-10T11:54:14Z'
  edited_at: '2026-08-22T00:14:57Z'
  id: 4408735106193
  locale: es
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/es/articles/4408735106193
---
> **At a glance:** Considera las funcionalidades adicionales del SDK que están disponibles y trabaja con tu desarrollador para implementar la API como la medición de desinstalaciones, la atribución de invitaciones de usuarios, las push notifications y la configuración de la privacidad.

<div id="additional-attribution-methods" />

## Métodos de atribución adicionales

Considera estos métodos de atribución adicionales si planeas medir TV, desinstalaciones o aplicaciones preinstaladas.

**Todas las plataformas**

<Accordion title="Atribución CTV">

Atribuye <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-attribution-concepts">usuarios móviles a anuncios de TV</Anchor> emitidos en ubicaciones específicas y en momentos específicos.

</Accordion>

<Accordion title="Mide desinstalaciones">

Mide la tasa de desinstalaciones de usuarios provenientes de distintas fuentes. La medición de desinstalaciones puede ayudarte a analizar y optimizar tus campañas según este importante KPI.

<Anchor target="_blank" href="/marketers/es/docs/measure-uninstalls">Aprende a configurar la medición de desinstalación</Anchor>.

</Accordion>

**Solo para Android**

<Accordion title="Aplicaciones preinstaladas">

En las <Anchor target="_blank" href="/marketers/es/docs/appsflyer-factory-preinstall-using-manifest-android">campañas de preinstalación</Anchor>, los propietarios de aplicaciones contratan a fabricantes de dispositivos (OEM) para preinstalar sus aplicaciones.

Con AppsFlyer, puedes atribuir instalaciones de aplicaciones preinstaladas con facilidad. Cuando los usuarios inician tu aplicación por primera vez, AppsFlyer atribuye la instalación al partner de precarga como fuente de medios.

</Accordion>

<div id="sessions" />

## Sesiones

Mide el engagement de los usuarios con tu aplicación contando la cantidad de sesiones de usuario durante un período determinado.

**Todas las plataformas**

<Accordion title="Tiempo personalizado entre sesiones">

De manera predeterminada, deben pasar por lo menos 5 segundos entre dos inicios de la aplicación para que cuenten como dos sesiones separadas. Saber más sobre el <Anchor target="_blank" href="/marketers/es/docs/measure-sessions#session-reporting-by-the-app-sdk">recuento de sesiones</Anchor>.

Establecer un **valor alto para el tiempo personalizado entre lanzamientos puede afectar a las API** que dependen de los datos de la Sesión, como el Deep Linking.

</Accordion>

**Solo para Android**

<Accordion title="Sesiones de segundo plano para aplicaciones de utilidad">

Puedes <Anchor target="_blank" href="/marketers/es/docs/measure-sessions#session-reporting-by-the-app-sdk">informar manualmente de las sesiones de usuario</Anchor>. Esto puede resultar útil para aplicaciones utilitarias que se ejecutan en segundo plano.

</Accordion>

<div id="owned-media" />

## Medios propios

Utiliza OneLink para atribuir las fuentes de medios de tu propiedad, como sitios web, redes sociales e invitaciones de usuarios.

**Todas las plataformas**

<Accordion title="Resolución de URL encapsuladas de enlaces profundos">

Algunos servicios de 3rd party, como los <Anchor target="_blank" href="/marketers/es/docs/email-service-provider-esp-integration-guide">proveedores de servicios de correo electrónico</Anchor>, encapsulan enlaces en los correos electrónicos con sus propios dominios de registro de clics. Algunos incluso te permiten configurar tus propios dominios de registro de clics. Si OneLink está encapsulado en tales dominios, su funcionalidad podría verse limitada.

Para solucionar este problema, tu desarrollador debe configurar la aplicación con estas API:

<Tabs>
<Tab title="Android Native">

Consulta [`setResolveDeepLinkURLs`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setresolvedeeplinkurls) en la referencia del SDK de Android

</Tab>

<Tab title="iOS Native">

Consulta [`resolveDeepLinkURLs`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#resolvedeeplinkurls) en la referencia del SDK de iOS

</Tab>

<Tab title="Unity">

Consulta [`setResolveDeepLinkURLs`](https://dev.appsflyer.com/hc/docs/api#setresolvedeeplinkurls) en la referencia del SDK de Unity

</Tab>
</Tabs>

</Accordion>

<Accordion title="Atribución de push notifications">

AppsFlyer admite la medición de las campañas de push notifications de todos los proveedores, incluidos los mensajes en la nube de Google y los servicios de push notification de Apple.

<Anchor target="_blank" href="/marketers/es/docs/measuring-push-notification-re-engagement-campaigns">Saber más sobre la medición de push notifications</Anchor>.

</Accordion>

<Accordion title="Atribución de invitaciones de usuarios">

Permitir que tus usuarios existentes inviten a sus amigos y contactos como nuevos usuarios a tu aplicación puede ser un factor de crecimiento clave para tu aplicación. Con AppsFlyer, puedes atribuir y registrar instalaciones que se originen a partir de invitaciones de usuarios dentro de tu aplicación.

<Anchor target="_blank" href="/marketers/es/docs/user-invite-attribution">Saber más sobre la atribución de invitaciones de usuarios</Anchor>.

</Accordion>

<Accordion title="Atribución de promociones cruzadas">

Las aplicaciones de promoción cruzada pueden ser un importante factor de crecimiento para generar instalaciones adicionales para tus aplicaciones. AppsFlyer te permite atribuir y registrar las instalaciones que se originan en una promoción cruzada de la aplicación que el usuario tiene actualmente, a otra de tus aplicaciones.

<Anchor target="_blank" href="/marketers/es/docs/cross-promotion-attribution-for-marketers">Saber más sobre la atribución de promoción cruzada</Anchor>.

</Accordion>

<Accordion title="Atribuir sesiones de aplicaciones iniciadas desde sitios web propios (dominios)">

Los propietarios de apps que utilizan App Links o Universal Links para Deep Linking (sin OneLink) pueden configurar el SDK para atribuir sesiones iniciadas a través del dominio asociado con su app (<Anchor target="_blank" href="https://developer.android.com/studio/write/app-link-indexing#associatesite">Android</Anchor>/<Anchor target="_blank" href="https://developer.apple.com/documentation/xcode/supporting-associated-domains?preferredLanguage=occ">iOS</Anchor>).

Por ejemplo:

* Un usuario busca en Google y hace clic en tu dominio, **[www.example.com](https://www.example.com)**.
* Si el usuario no tiene la aplicación instalada, se le dirige al sitio web ([www.example.com](https://www.example.com)).
* Si el usuario tiene la aplicación instalada en su dispositivo, se le redirige mediante Deep Linking a la aplicación asociada con [www.example.com](https://www.example.com). La sesión se atribuye a la fuente de medios (parámetro `pid`) configurada en el SDK.

La documentación para desarrolladores puede encontrarse en:

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#appendparameterstodeeplinkingurl">Referencia del SDK de Android</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#appendparameterstodeeplinkingurl">Referencia del SDK de iOS</Anchor>

**Consejo!** <Anchor target="_blank" href="/marketers/es/docs/convert-your-mobile-web-visitors-to-app-users#soluciones-de-atribución">OneLink Smart Script</Anchor> puede ayudar a los propietarios de aplicaciones a convertir a los visitantes del sitio web en usuarios de la aplicación.

</Accordion>

<div id="user-privacy" />

## Privacidad del usuario

Revisa las regulaciones como el GDPR y CCPA y los requisitos de tu negocio, y considera qué políticas de aceptación y exclusión opcionales implementar.

**Todas las plataformas**

<Accordion title="Política de exclusión opcional">

En algunos casos, es posible que debas indicar a tu desarrollador que configure el SDK de AppsFlyer para que detenga o limite la recopilación de datos (por ejemplo, para cumplir con las regulaciones del GDPR y CCPA). Existen diferentes métodos para preservar la privacidad de los usuarios en el SDK. Para más información sobre los distintos métodos, consulta el artículo <Anchor target="_blank" href="/marketers/es/docs/apply-privacy-preserving-sdk-methods">Métodos de preservación de la privacidad en el SDK</Anchor>.

</Accordion>

<Accordion title="Excluir a los partners de la obtención de datos">

En algunos casos, es posible que los anunciantes deseen dejar de compartir datos a nivel de usuario con las ad networks/partners para usuarios específicos. Las razones para esto incluyen:

* Políticas de privacidad como la CCPA o el GDPR
* Mecanismos de exclusión opcional de los usuarios
* Competencia con algunos partners (ad networks, third-party)

El intercambio de datos con los partners se controla mediante el método `setSharingFilterForPartners`:

<Tabs>
<Tab title="Android nativo">

Consulta <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setsharingfilterforpartners">`setSharingFilterForPartners`</Anchor> en la referencia del SDK de Android

</Tab>

<Tab title="iOS nativo">

Consulta <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setsharingfilterforpartners">`resolveDeepLinkURLs`</Anchor> en la referencia del SDK de iOS

</Tab>

<Tab title="Unity/React Native">

Consulta <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setsharingfilterforpartners">`setSharingFilterForPartners`</Anchor> en la referencia del SDK de Unity

Consulta <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#setsharingfilterforpartners">`setSharingFilterForPartners`</Anchor> en la referencia del SDK de React Native

</Tab>
</Tabs>

</Accordion>

<Accordion title="Enviar consentimiento para el cumplimiento de la DMA">

Como parte de la legislación de la [Ley de Marketing Digital (DMA)](https://commission.europa.eu/strategy-and-policy/priorities-2019-2024/europe-fit-digital-age/digital-markets-act-ensuring-fair-and-open-digital-markets_en) de la UE, las grandes empresas de tecnología deben obtener el consentimiento de los usuarios finales europeos antes de utilizar datos personales de servicios de terceros para la publicidad.

Para cumplir con la legislación, Google exige que los clientes de AppsFlyer incluyan campos de consentimiento específicos al enviar eventos originados en usuarios finales de la UE a Google. El SDK de AppsFlyer (Android - v6.13.0+, iOS - v6.13.1+) puede enviar los datos de consentimiento necesarios con cada evento para cumplir los requisitos de Google.

El SDK ofrece dos métodos alternativos para recopilar datos de consentimiento:

* **A través de una Consent Management Platform (CMP):** Si la aplicación utiliza un CMP que cumpla con el [protocolo Transparency and Consent Framework (TCF)](https://iabeurope.eu/tcf-supporting-resources/) v2.2, el SDK puede recuperar automáticamente los detalles del consentimiento.

  O
* **A través de una API de SDK dedicada**: Los desarrolladores pueden pasar los datos de consentimiento necesarios de Google directamente al SDK utilizando una API específica diseñada para este fin.

Para implementar la recopilación de datos de consentimiento de los usuarios para el cumplimiento de la DMA, consulta nuestras guías del centro de desarrollo:

<Tabs>
<Tab title="Android nativo">

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-send-consent-for-dma-compliance">Enviar consentimiento para el cumplimiento de la DMA</Anchor>

</Tab>

<Tab title="iOS nativo">

[Enviar consentimiento para el cumplimiento de la DMA](https://dev.appsflyer.com/hc/docs/ios-send-consent-for-dma-compliance)

</Tab>
</Tabs>

</Accordion>

**Solo para iOS**

<Accordion title="SDK de modo estricto">

Usa el SDK de modo estricto para eliminar completamente la funcionalidad de recopilación del IDFA y las dependencias del framework de AdSupport (por ejemplo, al desarrollar <Anchor target="_blank" href="https://developer.apple.com/app-store/review/guidelines/#kids-category">aplicaciones dirigidas a un público infantil</Anchor>).

Si comercializas aplicaciones dirigidas a un público infantil, tu desarrollador debe instalar el <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk#strict-mode-sdk">SDK de modo estricto</Anchor> en lugar del SDK normal. **Nota:** El IDFV sigue estando disponible.

</Accordion>

<Accordion title="Deshabilitar frameworks de anuncios">

Para deshabilitar los frameworks AdSupport e iAd, el SDK proporciona los siguientes setters:

<Tabs>
<Tab title="iOS nativo">

* [`disableCollectASA`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disablecollectasa) para optar por la exclusión de las atribuciones de Apple Search Ads.
* [`disableAdvertisingIdentifier`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#disableadvertisingidentifier) para no recopilar `advertisingIdentifier` de Apple

</Tab>

<Tab title="Unity">

* [`setDisableCollectIAd`](https://dev.appsflyer.com/hc/docs/api#setdisablecollectiad) para optar por la exclusión de las atribuciones de Apple Search Ads.
* [`setDisableCollectAppleAdSupport`](https://dev.appsflyer.com/hc/docs/api#setdisablecollectappleadsupport) para no recopilar `advertisingIdentifier` de Apple

</Tab>
</Tabs>

</Accordion>

<div data-zendesk-anchors="additional-attribution-methods=m%C3%A9todos-de-atribuci%C3%B3n-adicionales 01H8W01DRHQHJKNMJA24PR5S2T=m%C3%A9todos-de-atribuci%C3%B3n-adicionales sessions=sesiones 01H8W01DRHD3EZBQT0ZKDMM1QB=sesiones owned-media=medios-propios 01H8W01DRHV8H3QFJX5QKABK5E=medios-propios user-privacy=privacidad-del-usuario 01H8W01DRHJFB71DVJ64QWJME4=privacidad-del-usuario" />
