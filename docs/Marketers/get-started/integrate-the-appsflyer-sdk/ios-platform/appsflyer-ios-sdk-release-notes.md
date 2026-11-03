---
title: Notas de la versión del SDK para iOS de AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Release Notes
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
  created_at: '2017-03-09T19:49:54Z'
  edited_at: '2026-11-02T01:07:17Z'
  id: 115001224823
  locale: es
  section: iOS platform
  section_id: 6551263106577
  url: https://support.appsflyer.com/hc/es/articles/115001224823
---
> **En resumen:** Las notas de la versión del SDK proporcionan una descripción general rápida de los últimos cambios en el SDK de iOS. Los desarrolladores que busquen detalles más completos deben revisar las <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-release-notes">notas de la versión de iOS en el Dev Hub</Anchor>.

**Las versiones antiguas del SDK para iOS y Android dejarán de ser compatibles con un ciclo fijo de seis meses.** Este ciclo está diseñado para proporcionar aviso previo, lo que ayuda a los equipos a planificar con anticipación y mantener la funcionalidad completa de la aplicación sin interrupciones. La actualización a la última versión del SDK garantiza el acceso a las funciones más recientes, una estabilidad mejorada y soporte continuo.

> 🚧 **Importante:**
>
> Para garantizar una transición fluida, se anima a los desarrolladores de aplicaciones a actualizar a la última versión del SDK antes de la fecha de finalización del soporte.

## Fin del soporte vs Obsoleto

AppsFlyer distingue entre las versiones del SDK **obsoletas** y las de **fin del soporte** para aclarar el nivel de soporte y el impacto en la medición de datos.

* **Versiones obsoletas:** Versiones del SDK que ya no se recomiendan debido a problemas conocidos, como errores críticos. Estas versiones aún pueden enviar datos a AppsFlyer, pero se desaconseja su uso continuo y se recomienda encarecidamente actualizar a una versión compatible. Se recomienda encarecidamente actualizar a una versión compatible.
* **Versiones de fin del soporte:** Versiones del SDK para las que la medición está completamente detenida en todas las plataformas. Tanto para Android como para iOS, no se medirán las instalaciones, sesiones y eventos in-app. Cualquier tráfico de estas versiones (a menos que AppsFlyer lo excluya específicamente) recibirá un código de estado 400, lo que significa que el SDK intentará enviar llamadas de API como de costumbre, pero los servidores de AppsFlyer las rechazarán y los datos no se procesarán.

## Notas de la versión del SDK de iOS

La siguiente tabla proporciona notas de lanzamiento para las versiones compatibles del SDK de iOS, incluidas las fechas de lanzamiento y las actualizaciones clave para los desarrolladores. Para más información para desarrolladores, consulta las <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk">guías de integración</Anchor> para desarrolladores del SDK para iOS.

| Versión | Fecha de lanzamiento | Notas |
| --- | --- | --- |
| 7.0.4 | 2026-10-27 | <ul><li>Mejor gestión de las direcciones de correo electrónico de Gmail en la API `setUserEmail`.</li></ul> |
| 7.0.3 | 10-12-2026 | <ul><li>El SDK ahora es compatible con googleAdManager y cloudX como partners de mediación de ingresos por anuncios.</li><li>Se ha añadido un campo de ingresos netos que los desarrolladores pueden asociar a eventos in-app para reportar los ingresos con mayor precisión.</li><li>Se ha reducido la huella de memoria del SDK.</li></ul> |
| 7.0.1 | 15-10-2025 | <ul><li>Ahora, las aplicaciones pueden proporcionar al SDK un correo electrónico, un número de teléfono, un nombre y un ID de inicio de sesión de Facebook del cliente con hash para compartirlos con partners de ad network. El SDK no recopila esta información por sí mismo. La aplicación la proporciona y solo se envían valores con hash; nunca texto sin formato.</li><li>Se han eliminado los métodos `setUserEmails` y `setPhoneNumber`. Los desarrolladores que los usen deben cambiar a `setUserEmail` y `setUserPhone`</li></ul> |
| 6.18.1 | 21-09-2025 | <ul><li>Se ha corregido un problema por el que las solicitudes de validación de compras del Purchase Connector que fallaban debido a un error de red se perdían de forma permanente después de reiniciar la aplicación.</li></ul> |
| 6.18.0 | 03-09-2025 | <ul><li>Se ha añadido soporte para recuperar AppTransaction, una representación de la descarga de una aplicación, firmada criptográficamente por la tienda de aplicaciones.</li><li>Corrección de errores y mejoras</li></ul> |
| 6.17.9 | 06-08-2024 | <ul><li>Se ha corregido un problema por el que el SDK podía quedarse bloqueado al intentar recuperar datos de ODM, lo que impedía que las solicitudes se enviaran al servidor.</li><li>Se ha corregido un problema por el que el ID de usuario del cliente establecido por la aplicación no se enviaba en el evento de instalación.</li></ul> |
| 6.17.8 | 21-08-2025 | <ul><li>https://dev.appsflyer.com/hc/docs/unified-deep-linking-udl</li></ul> |
| 6.17.7 | 15-07-2025 | <ul><li>Se ha corregido un problema al recuperar datos de la biblioteca ICM de Google.</li></ul> |
| 6.17.6 | 24-06-2025 | <ul><li>Se ha corregido un problema introducido en la versión 6.17.3 que podía causar una caída cuando el SDK intenta enviar datos de ICM a AppsFlyer.</li></ul> |
| 6.17.5  <br />Obsoleto | 23-04-2025 | <ul><li>**Esta versión está en desuso y no debe utilizarse.**</li></ul> |
| 6.17.4  <br />Obsoleto | 27-08-2025 | <ul><li>**Esta versión está en desuso y no debe utilizarse.**</li><li>Se ha corregido un problema por el que, en raras ocasiones, la aplicación se bloqueaba cuando se iniciaba el SDK.</li></ul> |
| 6.17.3  <br />Obsoleto | 18-02-2025 | <ul><li>**Esta versión está en desuso y no debe utilizarse.**</li><li>Lógica actualizada para obtener datos de la biblioteca ICM de Google para mejorar la precisión.</li></ul> |
| 6.17.2 | 19-01-2025 | <ul><li>API`validateAndLogInAppPurchase` actualizada (beta)</li><li>Manejo mejorado de tokens de Apple Search Ads (ASA) para aplicaciones que recopilan el consentimiento de la ATT (AppTrackingTransparency).</li></ul> |
| 6.17.1 | 23-09-2024 | <ul><li>Se agregó soporte para la medición de <Anchor target="_blank" href="https://support.google.com/google-ads/answer/16203286">conversiones integradas de Google</Anchor> (ICM).</li><li>Se ha corregido un problema que provocaba que apareciera un mensaje emergente de inicio de sesión de la App Store cuando se ejecutaba el SDK en un entorno de desarrollo.</li></ul> |
| 6.17.0 | Versión | <ul><li>Mejoras de estabilidad y rendimiento</li></ul> |
| 6.16.2 | Versión | <ul><li>Actualización técnica necesaria para lanzar esta versión en plugins</li></ul> |
| 6.16.1 | 18-02-2025 | <ul><li>Se actualizó la API para enviar manualmente los datos de consentimiento de la DMA a AppsFlyer.</li></ul> |
| 6.16.0 | 24-07-2024 | <ul><li>Se agregó soporte para las APIs StoreKit 2 de Apple para reportes de suscripciones y compras in-app a través del conector de compras. Esta función se encuentra actualmente en beta cerrada.</li></ul> |
| 6.15.3 | 03-07-2024 | Mantenimiento del SDK |
| 6.15.2 | 10-06-2024 | <ul><li>Se ha corregido un problema con la transmisión de eventos en el conector de compra. Esta corrección no afecta a ninguna versión de producción del conector de compra y está relacionada con su actualización a la versión 6.15.x.</li></ul> |
| 6.15.1 | 26-04-2024 | <ul><li>Se ha corregido un problema con la detección de reinstalación que se producía cuando se instalaban dos o más aplicaciones del mismo proveedor en el dispositivo.</li></ul> |
| 6.15.0 | 19-04-2024 | <ul><li>Se agregó el método de API `logAdRevenue` para enviar datos de ingresos publicitarios a AppsFlyer. **Nota:** A partir de esta versión, ya no se debe utilizar el conector AdRevenue; debe ser reemplazado por el método `logAdRevenue`. Para más información, consulta [aquí](https://dev.appsflyer.com/hc/docs/ad-revenue-2).</li><li>Se han realizado actualizaciones internas relacionadas con el conector de compras. Las aplicaciones que usan el conector de compra y se actualizan a esta versión del SDK también deben actualizar su conector de compra a la versión 6.15.0.</li></ul> |
| 6.14.6  <br />Fin del soporte técnico:  <br />2027-03-08 | 18-04-2024 | <ul><li>Se ha corregido un problema por el que el SDK realizaba llamadas redundantes a la función de API `getConversionData` (GCD) al iniciar una nueva sesión; Esto no afecta a la medición.</li></ul> |
| 6.14.5  <br />Fin del soporte técnico:  <br />2027-03-08 | 07-04-2024 | <ul><li>Se ha corregido un problema por el que el SDK enviaba los datos de consentimiento manual establecidos por la aplicación, incluso si se había eliminado el código para enviar el consentimiento manual.</li></ul> |
| 6.14.4  <br />Fin del soporte técnico:  <br />2027-03-08 | 26-03-2024 | <ul><li>Privacy Manifest actualizado para el <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk#strict-mode-sdk">SDK de modo estricto</Anchor>.</li></ul> |
| 6.14.3  <br />Fin del soporte técnico:  <br />2027-03-08 | 05-03-2024 | <ul><li>Se corrigió la fusión automática del manifiesto de privacidad para las aplicaciones que utilizan Cocoapods.</li></ul> |
| 6.14.2  <br />Fin del soporte técnico:  <br />2027-03-08 | 19-04-2024 | Mantenimiento del SDK |
| 6.14.1  <br />Fin del soporte técnico:  <br />2027-03-08 | 04-01-2024 | <ul><li>Se ha agregado compatibilidad con el flujo de validación de compras actualizado. Esta función se encuentra actualmente en beta cerrada. Saber más</li></ul> |
| 6.14.0  <br />Fin del soporte técnico:  <br />2027-03-08 | 24-08-2023 | <ul><li>Se ha añadido compatibilidad con el manifiesto de privacidad. <Anchor target="_blank" href="/marketers/es/docs/implement-privacy-manifest-in-your-app">Saber más sobre el Manifiesto de Privacidad en AppsFlyer</Anchor>.</li><li>Se agregó una firma XCFramework al SDK, lo que permite a los desarrolladores que usan Xcode 15 validar el origen y la autenticidad del SDK.</li></ul> |
| 6.13.2  <br />Fin del soporte técnico:  <br />2027-03-08 | 20-07-2023 | <ul><li>Se ha corregido un problema que provocaba un error en el lanzamiento de aplicaciones que usaban SPM en Xcode 15.3. Mira las <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-release-notes#version-6132">Notas de la versión para desarrolladores</Anchor> para obtener más información.</li></ul> |
| 6.13.1  <br />Fin del soporte técnico:  <br />2027-03-08 | 10-03-2025 | <ul><li>Se solucionó un problema con el envío de datos de consentimiento para usuarios que no pertenecen al GDPR en un flujo de consentimiento de CMP (DMA).</li></ul> |
| 6.13.0   <br />Fin del soporte técnico:  <br />2027-03-08 | 13-06-2023 | <ul><li>Se agregó soporte para la nueva política de consentimiento de la UE de Google.</li></ul> |

## Versiones del SDK no compatibles

Las siguientes versiones del SDK han alcanzado el estado de **finalización del soporte**. Estas versiones ya no pueden enviar datos a AppsFlyer y se rechazará cualquier tráfico que generen.

| Versión | Fecha de lanzamiento | Notas |
| --- | --- | --- |
| 6.12.3 | 24-05-2023 | <ul><li>Se ha agregado un nuevo parámetro `original_link` al callback de Deep Linking dentro del flujo de resolución del Proveedor de Servicios de Correo electrónico (ESP).</li><li>Se han eliminado todas las referencias a iAd Framework.</li></ul> |
| 6.12.2 | 25-04-2023 | Mantenimiento del SDK |
| 6.12.1 | 02-04-2023 | <ul><li>Se corrigió un problema en SKAdNetwork 4.0 que provocaba que el valor de conversión aproximado se reportara como "None"</li><li>Se corrigió un bloqueo en la implementación de tvOS</li></ul> |
| 6.12.0 | 15-02-2023 | Se eliminó el soporte de código de bits del SDK |
| 6.11.2 | 19-08-2024 | `validateAndLogInAppPurchase`Se solucionó un problema introducido en v6.11.0, al realizar la llamada (la antigua API para validación y registro de compras) no registra el evento de compra.   <br />  <br />**Importante:** Si estas usando `v6.11.0` o `v6.11.1`, y la API `validateAndLogInAppPurchase`, actualiza a esta versión. |
| 6.11.1 | 28-08-2024 | Mantenimiento del SDK |
| 6.11.0 | 28-06-2023 | <ul><li>Un nuevo nombre de dominio de AppsFlyer en la URL utilizada por el SDK para enviar solicitudes a los servidores de AppsFlyer.</li><li>Se modificó el comportamiento de la API setHost cuando se envían valores vacíos o nulos. [Aprender más](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#sethost)</li></ul> |
| 6.10.1 | 02-04-2023 | Se agregó el parámetro `link` para el payload UDL de escenarios de Direct Deep Linkinig |
| 6.10.0 | 08-02-2024 | Soporte de SKAdNetwork 4.0. <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide">Saber más sobre la solución SKAdNetwork de AppsFlyer</Anchor> |
| 6.9.2  <br />Fin del soporte:  <br />2025-09-08 | 31-01-2023 | Se actualizó la estructura interna de las solicitudes para Get Conversion Data (GCD). **Nota**: Los datos de respuesta siguen siendo los mismos. |
| 6.9.1  <br />Fin del soporte:  <br />2025-09-08 | 28-11-2022 | Se actualizó la estructura interna de las solicitudes para Get Conversion Data (GCD). **Nota**: Los datos de respuesta siguen siendo los mismos. |
| 6.9.0  <br />Fin del soporte:  <br />2025-09-08 | 06-11-2022 | Se actualizó la API interna para la generación de reportes de ingresos por publicidad. A partir de esta versión, solo se admite el [Conector genérico para AdRevenue](https://dev.appsflyer.com/hc/docs/ad-revenue-2).<br /><br />Esta versión del SDK es compatible con AdRevenue Connector `V6.9.0`. |
| 6.8.1  <br />Fin del soporte:  <br />2025-09-08 | 09-08-2022 | **Detección de reinstalaciones**: se mejoró la capacidad de detectar y reportar reinstalaciones de la app mediante el almacenamiento en el dispositivo. Esta capacidad se puede controlar en el dashboard de AppsFlyer desde la <Anchor target="_blank" href="/marketers/es/docs/app-settings">página Configuración de la app</Anchor>. |
| 6.8.0  <br />Fin del soporte:  <br />2025-03-03 | 19-07-2022 | Para la detección de reinstalaciones, utiliza el SDK V6.8.1+ |
| 6.7.0  <br />Fin del soporte:  <br />2025-03-03 | 19-06-2022 | Actualiza la implementación de SKAdNetwork para usar la API de Apple actualizada `updatePostbackConversionValue`, introducida en iOS 15.4.<br /><br />Esto no tiene ningún efecto sobre los datos enviados desde SKAdNetwork y no requiere ningún cambio en el código de la aplicación. |
| 6.6.1  <br />Fin del soporte:  <br />2025-03-03 | 16-05-2022 | Mantenimiento del SDK |
| 6.6.0  <br />Fin del soporte:  <br />2025-03-03 | 01-05-2022 | Se agregaron más parámetros a la devolución de llamada `didResolveDeepLink` de UDL para el flujo de Deep Linking directo (usuarios existentes). <Anchor target="_blank" href="/marketers/es/docs/bulletin-additional-parameters-available-for-deep-linking-existing-users">Para obtener más información</Anchor>. |
| 6.5.4  <br />Fin del soporte:  <br />2025-03-03 | 23-03-2022 | Mantenimiento del SDK |
| 6.5.3  <br />Fin del soporte:  <br />2025-03-03 | 02-03-2022 | **Corrección de errores:** Se corrigió un problema con una doble invocación de `didResolveDeepLink` en enlaces basados en el esquema URI. |
| 6.5.2  <br />Fin del soporte:  <br />2025-03-03 | 26-01-2022 | Mantenimiento del SDK |
| 6.5.1  <br />Fin del soporte:  <br />2025-03-03 | 03-01-2022 | Mantenimiento del SDK |
| 6.5.0  <br />Fin del soporte:  <br />2025-03-03 | 22-12-2021 | Refactorización y cambios internos. |
| 6.4.4  <br />Fin del soporte:  <br />2025-03-03 | 12-12-2021 | Mantenimiento del SDK |
| 6.4.3  <br />Fin del soporte:  <br />2025-03-03 | 30-11-2021 | Corrección de estabilidad para MacOS 10.14.6 con xcframework. |
| 6.4.2  <br />Fin del soporte:  <br />2025-03-03 | 28-10-2021 | Mantenimiento del SDK |
| 6.4.1  <br />Fin del soporte:  <br />2025-03-03 | 24-10-2021 | Se resolvió la estabilidad en las aplicaciones de Unity. |
| 6.4.0  <br />Fin del soporte:  <br />2025-03-03 | 12-09-2021 | **API agregada:** <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setsharingfilterforpartners">`setSharingFilterForPartners`</Anchor> te permite configurar qué Partners debe excluir el SDK del intercambio de datos.<br /><br />A partir de esta versión, `setSharingFilter` y <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setsharingfilterforallpartners">`setSharingFilterForAllPartners`</Anchor> están obsoletos. |
| 6.3.5  <br />Fin del soporte: 2024-08-31 | 19-08-2021 | **API agregada**: [`setCurrentDeviceLanguage`](https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setcurrentdevicelanguage)<br /><br />A partir de esta versión el idioma ya no es recopilado automáticamente por el SDK. |
| 6.3.4  <br />Fin del soporte: 2024-08-31 | 21-07-2021 | <ul><li>**Corrección de errores:** Se corrigió un problema al ejecutar el SDK en simuladores de Xcode 12.5</li><li>Correcciones y actualizaciones menores.</li></ul> |
| 6.3.2  <br />Fin del soporte: 2024-08-31 | 2021-06-17 | Registros de depuración mejorados. |
| 6.3.1  <br />Fin del soporte: 2024-08-31 | 02-06-2021 | Mantenimiento del SDK |
| 6.3.0  <br />Fin del soporte: 2024-08-31 | 13-05-2021 | <ul><li>Soporte para Apple Silicon: se agregó soporte para ejecutar el SDK en un simulador usando máquinas Mac con el chipset M1</li><li>A partir de esta versión, el SDK es compatible con iOS `9`+. iOS `8` ya no cuenta con soporte.</li><li>SDK de modo estricto para iOS: se agregó soporte para el administrador de dependencias de Carthage</li><li>Actualización técnica de la API de OneLink</li></ul> |
| 6.2.6  <br />Fin del soporte: 2024-08-31 | 25-04-2021 | <ul><li>Corrección de errores: las reglas de SKAdNetwork no se cargaban cuando se inicializaba el SDK después de `didFinishLaunchingWithOptions`</li><li>Corrección de errores: un caso límite de `waitForATTUserAuthorization` hacía que el evento de inicio se enviara sin IDFA, incluso si se otorgaba el consentimiento del usuario</li><li>Permitir que el SDK se ejecute en dispositivos iOS 8</li><li>Limpieza y eliminación de código y datos no utilizados</li></ul> |
| 6.2.5  <br />Fin del soporte: 2024-08-31 | 06-04-2021 | Refactorización, limpieza, eliminación de datos no utilizados del SDK.<br /><br />A partir de esta versión:<ul><li>El método `setShouldCollectDeviceName` está en desuso y no devolverá el nombre del dispositivo</li><li>El parámetro `wifi` enviado desde el SDK se establece en `False`</li></ul> |
| 6.2.4  <br />Fin del soporte: 2024-08-31 | 15-03-2023 | Corrección de errores relacionada con el modo de medición de ingresos de SKAdNetwork y los eventos in-app que contienen el parámetro `AF_REVENUE` .<br /><br />A partir de esta versión, en el caso de la medición de ingresos: cualquier evento que contenga `AF_REVENUE` afecta al valor de conversión. Antes de este cambio, el valor de conversión se establecía solo si estaba en el marco del evento`AF_PURCHASE`.<br /><br />**Nota:** Si implementas la medición de ingresos de SKAdNetwork, debes actualizar a esta versión. |
| 6.2.3  <br />Fin del soporte: 2024-08-31 | 07-03-2021 | Corrección de errores relacionados con la llamada a `updateConversionValue` de SKAdNetwork. |
| 6.2.2  <br />Fin del soporte: 2024-08-31 | 18-02-2021 | Mantenimiento del SDK |
| 6.2.1  <br />Fin del soporte: 2024-08-31 | 15-02-2021 | Soporte para <Anchor target="_blank" href="/marketers/es/docs/server-to-server-events-api-for-mobile-s2s-mobile">reportar eventos por S2S</Anchor> |
| 6.2.0  <br />Fin del soporte: 2024-08-31 | 07-02-2021 | API adicional: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#setpartnerdata">setPartnerData</Anchor> |
| 6.1.4  <br />Fin del soporte: 2024-08-31 | 12-01-2021 | Mantenimiento del SDK |
| 6.1.3  <br />Fin del soporte: 2024-08-31 | 24-12-2020 | <ul><li>API adicional: <Anchor target="_blank" href="/marketers/es/docs/additional-sdk-integration-guide#record-push-notifications">`addPushNotificationDeepLinkPath`</Anchor> (admite Movable Ink)</li><li>Soporte para <Anchor target="_blank" href="https://developer.apple.com/documentation/adservices">Apple AdServices Framework</Anchor></li></ul> |
| 6.1.2  <br />Fin del soporte: 2024-08-31 | 03-12-2020 | Mantenimiento del SDK |
| 6.1.1  <br />Fin del soporte: 2024-08-31 | 17-11-2020 | Presenta <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk#strict-mode-sdk">Strict mode SDK</Anchor> |
| 6.1.0  <br />Fin del soporte: 2024-08-31 | 09-11-2020 | Soporte para <Anchor target="_blank" href="https://dev.appsflyer.com/docs/ios-unified-deep-linking">Unified deep linking API</Anchor> |
| 6.0.8  <br />Fin del soporte: 2024-08-31 | 28-10-2020 | Soporte <Anchor target="_blank" href="/marketers/es/docs/apple-app-clips-integration-guide">Apple App Clips</Anchor> atribución |
| 6.0.7  <br />Fin del soporte: 2024-08-31 | 21-10-2020 | Mantenimiento del SDK |
| 6.0.6  <br />Fin del soporte: 2024-08-31 | 20-10-2020 | Mantenimiento del SDK |
| 6.0.5  <br />Fin del soporte: 2024-08-31 | 08-10-2020 | Mantenimiento del SDK |
| 6.0.4  <br />Fin del soporte: 2024-08-31 | 30-09-2020 | Admite múltiples redirecciones desde ESPs |
| 6.0.3  <br />Fin del soporte: 2024-08-31 | 06-09-2020 | <ul><li>Cambio de nombre de la API:<br />waitForAdvertisingIdentifier --> waitForATTUserAuthorization</li><li>El SDK recopila el IDFA de forma predeterminada para iOS 14 (y versiones anteriores de iOS)</li></ul> |
| 6.0.2   <br />Fin del soporte: 2024-08-31 | 27-08-2020 | <ul><li>Cambio del nombre de la API:<br />deviceLoggingDisabled --> anonymizeUser</li><li>Se requiere el diálogo AppTrackingTransparency (ATT) para recopilar el IDFA para iOS 14</li><li>Se agregó soporte para la atribución de promoción cruzada del IDFV</li></ul> |
| 6.0.1 beta  <br />Fin del soporte: 2024-08-31 | 06-08-2020 | <ul><li>Se agregó soporte para la <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide">atribución de SKAdNetwork</Anchor>, para ayudar a los anunciantes a medir el éxito de la campaña mientras se mantiene la privacidad del usuario</li></ul> |
| 6.0.0 beta  <br />Fin del soporte: 2024-08-31 | 04-08-2020 | <ul><li>Capacidades de depuración extendidas</li><li>Cambios importantes en la funcionalidad del SDK y la API. [Saber más](/docs/appsflyer-ios-sdk-release-notes#ios-v600-release-notes)</li></ul> |

> 📄 **Ver también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/about-att-and-skan">Guía de inicio rápido de iOS 14, ATT y SKAdNetwork</Anchor>

<div data-zendesk-anchors="h_01JVHFG6PN34YFWNZKX2CYHJV8=importante end-of-support-vs-deprecated=fin-del-soporte-vs-obsoleto h_01JVHEKR4MTFV0FDHMTQW00BCS=fin-del-soporte-vs-obsoleto ios-sdk-v6=notas-de-la-versi%C3%B3n-del-sdk-de-ios 01H8W3DDM1BYRSPMFTA3TCY8EQ=notas-de-la-versi%C3%B3n-del-sdk-de-ios unsupported-sdk-versions=versiones-del-sdk-no-compatibles h_01JVHGN5NVRMGN9SJ5DWEAJYN3=versiones-del-sdk-no-compatibles h_01HE7RE2EPQX872DKNDBJ2G2QE=ver-tambi%C3%A9n" />
