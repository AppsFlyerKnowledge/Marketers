---
title: Vista general de la integración del SDK
metadata:
  keywords:
    - iOS
    - Android
    - SDK
    - Integration
    - Advertisers
    - firetv
    - fire tv
    - Advertiser
    - Developer
    - appuid
    - anonymous
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2012-12-26T14:34:58Z'
  edited_at: '2026-08-22T00:15:11Z'
  id: 207032126
  locale: es
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/es/articles/207032126
---
> **At a glance:** Conoce las funcionalidades del SDK de AppsFlyer que están disponibles y decide qué APIs debería usar tu aplicación en Android o iOS.

## Sobre el SDK

Mira este video para obtener una imagen completa de la integración del SDK.

<Embed title="Vista general de la integración del SDK" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/4iybquc6q3" providerUrl="https://fast.wistia.com" />

El SDK ofrece funciones para la instalación de aplicaciones y el registro de eventos. Puedes registrar instalaciones, sesiones y eventos in-app. Los eventos en la aplicación incluyen, por ejemplo, compras in-app o subir de nivel en un juego. El registro de estos eventos puede ayudarte a evaluar el ROI y la calidad del usuario.

Este artículo describe el proceso de integración del SDK V6+ y ayuda a los anunciantes (dueños de apps) y a los gestores de producto a planificar la integración del SDK de AppsFlyer en sus aplicaciones Android o iOS.

La documentación adicional incluye lo siguiente:

<Tabs>
<Tab title="Android nativo">

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk">Documentación de instalación de SDK para desarrolladores</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/appsflyer-android-sdk-release-notes">Notas de lanzamiento</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference">Documentación de referencia del SDK para desarrolladores</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/fill-out-google-safety-section-form">Sección de seguridad de datos en Google Play</Anchor>

</Tab>

<Tab title="iOS nativo">

* <Anchor target="_blank" href="/marketers/es/docs/updating-to-ios-sdk-v6-and-plugins">Actualizar al SDK de iOS V6</Anchor>. Ten en cuenta que el iOS SDK V5.4.4 es totalmente compatible con iOS 14. Sin embargo, recomendamos adoptar SDK V6.X para asegurar la compatibilidad con futuras versiones de iOS.
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk">Documentación de instalación del SDK para desarrolladores</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/appsflyer-ios-sdk-release-notes#ios-v600-release-notes">Notas de lanzamiento</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference">Documentación de referencia del SDK para desarrolladores</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/preparing-for-the-app-store-review-nutrition-labels">Preparación para la revisión de la App Store: etiquetas nutricionales</Anchor>

</Tab>

<Tab title="Unity">

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/installation">Documentación de instalación del SDK para desarrolladores</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api">Documentación de referencia del SDK para desarrolladores</Anchor>

</Tab>

<Tab title="React Native">

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/installation">Documentación de instalación del SDK para desarrolladores</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api">Documentación de referencia del SDK para desarrolladores</Anchor>

</Tab>
</Tabs>

## Compatibilidad del SDK

El SDK de AppsFlyer es compatible con las siguientes plataformas:

<Tabs>
<Tab title="Android">

* A partir de Android V4.0
* Plataformas Android no móviles, como Smart TVs (incluyendo Amazon Fire TV). <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-attribution-concepts">Ver descripción general de CTV</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/set-up-multi-store-android-attribution">Mercados fuera de la tienda</Anchor> para aplicaciones Android, como Amazon y Baidu

</Tab>

<Tab title="apps de iOS,">

* iOS 9+ (iPhone, iPod, iPad)
* tvOS 9+ (Apple TV)
* Cumple con las redes Apple <Anchor target="_blank" href="https://developer.apple.com/library/content/documentation/NetworkingInternetWeb/Conceptual/NetworkingOverview/UnderstandingandPreparingfortheIPv6Transition/UnderstandingandPreparingfortheIPv6Transition.html#//apple_ref/doc/uid/TP40010220-CH213-SW1">IPv6 DNS64/NAT64</Anchor>

El SDK es compatible con <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model">múltiples métodos de atribución</Anchor>. Los métodos de atribución que se utilizan dependen de lo siguiente:

* La versión de iOS instalada en el dispositivo del usuario
* La versión del SDK de iOS instalada en la aplicación

<table><thead><tr><th>Métodos de atribución soportados</th><th>Versión de iOS</th><th>Compatibilidad del SDK de iOS</th><th>Notas</th></tr></thead><tbody><tr><td rowspan="2">Modelado probabilístico</td><td>8 – 14.4</td><td>5.0.0+</td><td> </td></tr><tr><td>14.5+</td><td>6.0.3+</td><td>El modelado probabilístico se limita al contexto de medios propios, promoción cruzada y flujos web-a-aplicación con consentimiento.</td></tr><tr><td rowspan="2">ID matching<br/><br/> </td><td>8 - 13</td><td>5.0.0+</td><td>Los usuarios pueden elegir no participar utilizando la opción Limit Ad Tracking (LAT).</td></tr><tr><td>14.5+</td><td>6.0.3+</td><td>Se requiere App Tracking Transparency (ATT) y el consentimiento del usuario. Para obtener más información, consulta cómo <a href="./basic-sdk-integration-guide#configure-app-tracking-transparency-att-support" target="_blank">configurar el SDK de iOS para que sea compatible con la ATT</a>.</td></tr><tr><td rowspan="2"><a href="./skadnetwork-skan-solution-guide" target="_blank">SKAdNetwork</a></td><td>11.3 - 13</td><td rowspan="2">6.2.3<br/><br/> </td><td>La solución SKAdNetwork (SKAN) está limitada a la atribución de instalaciones de acuerdo con la <a href="https://developer.apple.com/documentation/storekit/skadnetwork" target="_blank">especificación SKAN</a>, lo que implica que no existe un valor de conversión.</td></tr><tr><td>+14</td><td><ul><li>SKAN siempre está disponible en los niveles de iOS y SDK, independientemente de la configuración de la ATT.</li><li>El marketer habilita SKAN desde el dashboard de AppsFlyer.</li></ul></td></tr></tbody></table>

Desde la versión SDK V6.0.8, está disponible la <Anchor target="_blank" href="/marketers/es/docs/apple-app-clips-integration-guide">atribución de Apple App Clips</Anchor>. También puedes leer nuestra <Anchor target="_blank" href="https://www.appsflyer.com/resources/others/apple-app-clips">entrada de blog</Anchor> sobre Apple App Clips.

</Tab>
</Tabs>

## Integración de SDK

El proceso de instalación e integración del SDK requiere la colaboración entre el gerente de producto y el desarrollador móvil. **Antes** de integrar el SDK con tu aplicación, revisa todas las tareas de integración y considera qué funcionalidades deseas que tu aplicación utilice.

### Lista de verificación para la planificación del SDK

Para ayudarte a comenzar, hemos preparado una <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTD4OimHC93iw2AJCcAY45yAc9lOBfJe8PskI_0NFZTnWnrIq1hjPBvCztkbom9acMDDd4d1d5mMFfi/pub?output=xlsx">lista de verificación</Anchor> que te guiará en el proceso de planificación. Para cada tarea, hay enlaces a la documentación para marketers y desarrolladores.

### Tareas de integración del SDK

La integración básica del SDK incluye las siguientes tareas. Las estimaciones de tiempo son solo una guía general.

| Tareas básicas de integración del SDK | Tiempo de planificación |
| --- | --- |
| Recupera la <Anchor target="_blank" href="/marketers/es/docs/basic-sdk-integration-guide#implementación-de-la-clave-de-desarrollo-en-tu-aplicación">clave de desarrollador de AppsFlyer</Anchor> y envía el enlace junto con las instrucciones de instalación e integración a tu desarrollador. | 15 minutos |
| Revisa las <Anchor target="_blank" href="/marketers/es/docs/basic-sdk-integration-guide#atribución">consideraciones de atribución</Anchor> y determina qué identificadores de dispositivo recopilar. | 30 minutos |
| Determina los <Anchor target="_blank" href="/marketers/es/docs/basic-sdk-integration-guide#registro-de-eventos-in-app">eventos in-app</Anchor> que deseas medir y envía los nombres y parámetros de los eventos al desarrollador. | 1 hora |
| Determina los <Anchor target="_blank" href="/marketers/es/docs/basic-sdk-integration-guide#deep-linking-con-onelink">métodos de Deep Linking</Anchor> que se usarán. | 30 minutos |
| Determina los métodos para <Anchor target="_blank" href="/marketers/es/docs/basic-sdk-integration-guide#acceso-a-datos-de-atribución-y-de-deep-linking">acceder a los datos de atribución</Anchor>. | 30 minutos |
| Una vez completada la integración básica, cualquier usuario de la cuenta con acceso al Dashboard de AppsFlyer puede realizar <Anchor target="_blank" href="/marketers/es/docs/basic-sdk-integration-guide#prueba-de-integración-del-sdk">pruebas básicas</Anchor>.<br /><br />Los desarrolladores pueden utilizar registros de debug en el <Anchor target="_blank" href="/marketers/es/docs/testing-the-sdk-integration-for-marketers#testing-in-the-development-environment">entorno de desarrollo</Anchor>. | 1 hora |

Colabora con tus desarrolladores móviles para implementar estas APIs adicionales en el SDK.

| Tareas adicionales para la integración del SDK | Tiempo de planificación |
| --- | --- |
| Determina si tu aplicación necesita una configuración de <Anchor target="_blank" href="/marketers/es/docs/additional-sdk-integration-guide#métodos-de-atribución-adicionales">atribución adicional</Anchor> (por ejemplo, medición de desinstalaciones o atribución de instalaciones para tiendas de aplicaciones de terceros). | 30 minutos |
| Determina los <Anchor target="_blank" href="/marketers/es/docs/additional-sdk-integration-guide#sesiones">informes de sesiones de usuario</Anchor>. | 30 minutos |
| Determina los métodos de atribución que se utilizarán para las <Anchor target="_blank" href="/marketers/es/docs/additional-sdk-integration-guide#medios-propios">fuentes de medios de medios propios</Anchor>. | 1 hora |
| Administra las políticas de <Anchor target="_blank" href="/marketers/es/docs/additional-sdk-integration-guide#privacidad-del-usuario">privacidad del usuario</Anchor> para garantizar que tu aplicación cumpla con las normativas de privacidad (GDPR, CCPA). | 1 hora |

> 📘 **Note**
>
> **Consulta también**
>
> * Descripción general de las plataformas CTV, PC y consolas

<div data-zendesk-anchors="about-the-sdk=sobre-el-sdk h_01H9FHRVKE6BHGW05G6YMKF737=sobre-el-sdk sdk-compatibility=compatibilidad-del-sdk h_01H9FHRVKEQ837Q0GFECNPPAN2=compatibilidad-del-sdk sdk-integration=integraci%C3%B3n-de-sdk h_01H9FHRVKEN0MMGTSD362FTWPS=integraci%C3%B3n-de-sdk sdk-planning-checklist=lista-de-verificaci%C3%B3n-para-la-planificaci%C3%B3n-del-sdk h_01H9FHRVKE468M1RTMF7VTYV1R=lista-de-verificaci%C3%B3n-para-la-planificaci%C3%B3n-del-sdk sdk-integration-tasks=tareas-de-integraci%C3%B3n-del-sdk h_01H9FHRVKERHXY19R97EN86EGP=tareas-de-integraci%C3%B3n-del-sdk" />
