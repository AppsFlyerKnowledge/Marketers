---
title: Notas de la versión del SDK de Android de AppsFlyer
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
  created_at: '2017-03-09T20:17:19Z'
  edited_at: '2026-11-02T01:06:42Z'
  id: 115001256006
  locale: es
  section: Android platform
  section_id: 6551190827921
  url: https://support.appsflyer.com/hc/es/articles/115001256006
---
> **En resumen:** Consulta las notas de la versión del SDK para obtener una vista general de los últimos cambios introducidos en el SDK de Android. Los desarrolladores que deseen información más detallada pueden consultar las <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-release-notes">notas de la versión de Android en el Dev Hub</Anchor>.

**Las versiones antiguas del SDK para iOS y Android dejarán de ser compatibles con un ciclo fijo de seis meses.** Este ciclo está diseñado para proporcionar aviso previo, lo que ayuda a los equipos a planificar con anticipación y mantener la funcionalidad completa de la aplicación sin interrupciones. La actualización a la última versión del SDK garantiza el acceso a las funciones más recientes, una estabilidad mejorada y soporte continuo.

> 🚧 **Importante:**
>
> Para garantizar una transición fluida, se anima a los desarrolladores de aplicaciones a actualizar a la última versión del SDK antes de la fecha de finalización del soporte.

## Fin del soporte vs Obsoleto

AppsFlyer distingue entre las versiones del SDK **obsoletas** y las de **fin del soporte** para aclarar el nivel de soporte y el impacto en la medición de datos.

* **Versiones obsoletas:** Versiones del SDK que ya no se recomiendan debido a problemas conocidos, como errores críticos. Estas versiones aún pueden enviar datos a AppsFlyer, pero se desaconseja su uso continuo y se recomienda encarecidamente actualizar a una versión compatible. Se recomienda encarecidamente actualizar a una versión compatible.
* **Versiones de fin del soporte:** Versiones del SDK para las que la medición está completamente detenida en todas las plataformas. Tanto para Android como para iOS, no se medirán las instalaciones, sesiones y eventos in-app. Cualquier tráfico de estas versiones (a menos que el equipo de producto lo excluya específicamente) recibirá un código de estado 400, lo que significa que el SDK intentará enviar llamadas de API como de costumbre, pero los servidores de AppsFlyer las rechazarán y los datos no se procesarán.

## Lanzamientos del SDK para Android

La siguiente tabla proporciona notas de lanzamiento para las versiones compatibles del SDK de Android, incluidas las fechas de lanzamiento y las actualizaciones clave para los desarrolladores. Para más información sobre los desarrolladores, consulta la <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk">Guía de integración del SDK para desarrolladores</Anchor>.

| Versión | Fecha de lanzamiento | Notas |
| --- | --- | --- |
| 7.0.4 | 2026-10-26 | <ul><li>Mejora en la gestión de las direcciones de correo electrónico de Gmail en la API `setUserEmail`</li></ul> |
| 7.0.2 | 19-10-2026 | <ul><li>Se ha añadido soporte para reportar ingresos de anuncios de dos nuevos partners de mediación publicitaria: Google Ad Manager y CloudX.</li><li>Se ha añadido un nuevo parámetro de evento para reportar ingresos netos.</li><li>Mejoras de estabilidad y rendimiento</li></ul> |
| 7.0.1 | 26-11-2025 | <ul><li>Las aplicaciones ahora pueden proporcionar al SDK un correo electrónico, un número de teléfono, un nombre y un ID de login de Facebook del cliente con hashing para compartirlos con partners de ad network. El SDK no recopila esta información por sí mismo. La aplicación la proporciona y solo se envían valores con hash, nunca texto sin formato.</li><li>Se han eliminado los métodos `setUserEmails` y `setPhoneNumber`. Los desarrolladores que los utilicen deben cambiar a `setUserEmail` y `setUserPhone`</li></ul> |
| 6.18.1 | 15-10-2025 | <ul><li>Se ha corregido un problema en el Purchase Connector por el que las validaciones de compra que fallaban debido a problemas de conectividad se almacenaban en caché y no se volvían a intentar, lo que podía dar lugar a la falta de datos de compra.</li></ul> |
| 6.18.0 | 18-08-2025 | <ul><li>Obsoleto</li></ul> |
| 6.17.6 | 05-08-2025 | <ul><li>Se ha corregido un problema por el que el SDK no enviaba el valor de AF\_STORE establecido por la aplicación.</li></ul> |
| 6.17.5 | Versión | <ul><li>Mejoras y correcciones de estabilidad</li><li>https://dev.appsflyer.com/hc/docs/unified-deep-linking-udl</li></ul> |
| 6.17.4 | 15-07-2025 | <ul><li>Se actualizó la integración entre el SDK y el módulo de seguridad avanzada. Esta versión es compatible con el módulo de seguridad v2.0.0 y superior.</li><li>Si estás utilizando el módulo de seguridad avanzada y deseas actualizar el SDK a la versión 6.17.4, también debes actualizar el módulo de seguridad a la versión 2.0.0.</li></ul> |
| 6.17.3 | 02-03-2025 | <ul><li>Actualización técnica: Mejoras de estabilidad y rendimiento</li></ul> |
| 6.17.2 | 17-02-2025 | <ul><li>Actualización técnica: Actualizado a targetSDKVersion 35</li></ul> |
| 6.17.1 | 17-12-2024 | <ul><li>Se actualizó la API de `validateAndLogInAppPurchase` para la API de validación de compras in-app (actualmente en versión beta)</li><li>Se agregó la integración con la API de integridad de Google Play para permitir la verificación de la integridad del dispositivo a través de Google Play.</li></ul> |
| 6.17.0 | 10-10-2024 | <ul><li>Se agregó soporte para recopilar el ID de AppSet. Ver <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk#collecting-appset-id">instrucciones para desarrolladores</Anchor></li></ul> |
| 6.16.2 | 28-07-2025 | <ul><li>Se ha corregido un problema que podía causar errores de compilación al integrar el SDK.</li></ul> |
| 6.16.1 | Versión | <ul><li>Se actualizó la API para enviar manualmente los datos de consentimiento de la DMA a AppsFlyer.</li></ul> |
| 6.16.0 | 10-06-2024 | <ul><li>Se agregó soporte para la atribución de precarga de Samsung. <Anchor target="_blank" href="/marketers/es/docs/set-up-appsflyer-preload-referrer-attribution#referencia-de-precarga-de-samsung">Saber más</Anchor>.</li><li>Se agregó soporte para la medición de ingresos en la API de atribución Privacy Sandbox (beta cerrada).</li><li>Se actualizó Dexguard a la versión 9.8.12 para resolver problemas de estabilidad y mejorar la seguridad.</li></ul> |
| 6.15.2 | 29-05-2024 | <ul><li>Mejoras y correcciones de estabilidad</li><li>Actualizaciones internas relacionadas con la API de Atribución de Privacy Sandbox</li></ul> |
| 6.15.1 | 18-04-2024 | Actualización de versiones:<ul><li>targetSDKVersion: v34</li><li>Gradle: v8.7</li><li>Java: v17</li></ul> |
| 6.15.0 | 03-04-2024 | <ul><li>Se agregó el método `logAdRevenue` para enviar datos de ingresos publicitarios a AppsFlyer. **Nota:** A partir de esta versión, ya no se debe utilizar el conector AdRevenue; debe ser reemplazado por el método `logAdRevenue`. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue-1">Saber más</Anchor></li></ul> |
| 6.14.2  <br />Fin del soporte:  <br />2027-03-08 | 08-02-2024 | <ul><li>Se solucionó un problema con la obtención de Meta Install Referrer en aplicaciones creadas con Unity.</li></ul> |
| 6.14.1  <br />Fin del soporte:  <br />2027-03-08 | 29-01-2024 | Mantenimiento del SDK |
| 6.14.0  <br />Fin del soporte:  <br />2027-03-08 | 18-12-2023 | <ul><li>Se ha agregado compatibilidad con el flujo de validación de compras actualizado. Esta función se encuentra actualmente en beta cerrada. Saber más</li><li>Se actualizó la integración de Huawei Referrer. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk#huawei-install-referrer">Saber más</Anchor>.</li></ul> |
| 6.13.1  <br />Fin del soporte:  <br />2027-03-08 | 25-10-2023 | Mantenimiento del SDK |
| 6.13.0  <br />Fin del soporte:  <br />2027-03-08 | 31-08-2023 | <ul><li>Se agregó soporte para la nueva política de consentimiento de la UE de Google.</li></ul> |

## Versiones del SDK no compatibles

Las siguientes versiones del SDK han alcanzado el estado de **finalización del soporte**. Estas versiones ya no pueden enviar datos a AppsFlyer y se rechazará cualquier tráfico que generen.

| Versión | Fecha de lanzamiento | Notas |
| --- | --- | --- |
| 6.12.6 | 02-08-2023 | Mantenimiento del SDK |
| 6.12.5 | 29-06-2023 | <ul><li>Se ha añadido el parámetro `original_link` al callback de deep linking en el flujo de resolución ESP.</li></ul> |
| 6.12.4 | 28-06-2023 | <ul><li>Dexguard se actualizó a la versión 9.4.16 para mejorar la estabilidad del SDK.</li></ul> |
| 6.12.3 | 29-06-2023 | Mantenimiento del SDK |
| 6.12.2 | 28-08-2024 | <ul><li>Se ha corregido un error que podía provocar que la aplicación fallara en algunos dispositivos en Android 8.1.0 y Android 11.</li></ul> |
| 6.12.1 | 16-05-2022 | <ul><li>Se ha corregido un problema que hacía que la apertura de la Play Store se retrasara en la promoción cruzada.</li><li>Se ha corregido un error que provocaba que la aplicación fallara en algunos dispositivos.</li></ul> |
| 6.12.0 | 25-04-2023 | <ul><li>En desuso: utiliza la versión 6.12.1.</li></ul> |
| 6.11.2 | 06-06-2023 | <ul><li>Se ha corregido un error que provocaba que la aplicación fallara en algunos dispositivos.</li></ul> |
| 6.11.1 | 01-03-2023 | <ul><li>En desuso: utiliza la versión 6.12.1.</li><li>Se corrigió un error por el que la aplicación a veces fallaba después de inicializar el SDK.</li></ul> |
| 6.11.0 | 13-02-2023 | <ul><li>Se ha corregido un problema que a veces provocaba que la aplicación se congelara en algunos dispositivos cuando el SDK intentaba obtener el Google Play Referrer.</li></ul> |
| 6.10.3 | 24-04-2025 | Mantenimiento del SDK |
| 6.10.2 (obsoleto) |  | Número con hasta 4 decimales que representa el porcentaje de impuesto recaudado. |
| 6.10.1 | 01-03-2023 | <ul><li>Se corrigió un problema que a veces provocaba que las aplicaciones de los dispositivos Samsung se cerraran al inicializar el SDK. Este problema afectó a las aplicaciones con SDK V6.6.0 y superiores.</li></ul> |
| 6.10.0 | 29-12-2021 | <ul><li>Nuevo dominio de AppsFlyer para la comunicación entre el SDK y los servidores de AppsFlyer.</li><li>Se ha cambiado la API setHost cuando se envían valores vacíos o nulos. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#sethost">Saber más</Anchor></li></ul> |
| 6.9.4  <br />Fin del soporte:  <br />2025-09-08 | 06-12-2022 | <ul><li>Se ha corregido un problema por el cual el envío de un evento de ingresos por publicidad desde el conector del SDK de ingresos por publicidad activaba una llamada al oyente de conversión.</li><li>Se ha corregido un problema que a veces provocaba que las aplicaciones se congelaran cuando se enviaba un evento de ingresos por publicidad desde el conector del SDK de ingresos por publicidad.</li></ul> |
| 6.9.3  <br />Fin del soporte:  <br />2025-09-08 | 28-11-2022 | <ul><li>Se actualizó la estructura interna de las solicitudes para Get Conversion Data (GCD). **Nota**: Los datos de la respuesta siguen siendo los mismos.</li><li>Se corrigió un problema por el que el SDK activaba una solicitud de GCD cuando la aplicación tenía el ConversionListener establecido en nulo.</li></ul> |
| 6.9.2  <br />Fin del soporte:  <br />2025-09-08 | 02-10-2022 | <ul><li>Se corrigió un problema relacionado con un retraso en la solicitud de una validación de compra usando la API validateAndLogInAppPurchase.</li></ul> |
| 6.9.1  <br />Fin del soporte:  <br />2025-09-08 | 19-09-2022 | Mantenimiento del SDK |
| 6.9.0  <br />Fin del soporte:  <br />2025-09-08 | 12-09-2022 | <ul><li>Se agregó soporte para el referente de Xiaomi GetApps Store.</li><li>Se actualizó la API interna para la generación de reportes de ingresos por publicidad. A partir de esta versión, solo se admite el <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue-1">conector genérico del SDK de ingresos por anuncios</Anchor> .</li></ul> |
| 6.8.2  <br />Fin del soporte:  <br />2025-09-08 | 29-08-2022 | <ul><li>Se corrigió un problema crítico con el mecanismo de almacenamiento en caché del SDK introducido en la V6.7.0, que provocaba que los eventos en caché se enviaran varias veces.</li></ul> |
| 6.8.1  <br />(En desuso)  <br />Fin del soporte:  <br />2025-09-08 | 24-08-2022 | <ul><li>**En desuso.** Utilice V6.8.2.</li></ul> |
| 6.8.0  <br />(En desuso)  <br />Fin del soporte:  <br />2025-09-08 | 18-07-2022 | <ul><li>**En desuso.** Utilice V6.8.2.</li><li>Se eliminó la API <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#enablelocationcollection">`enableLocationCollection`</Anchor> del SDK. La aplicación aún puede reportar los datos de ubicación del usuario pasándolos al SDK directamente a través de la API <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#loglocation">`logLocation`</Anchor>.</li><li>Se agregó el permiso `com.google.android.gms.permission.AD_ID` al `AndroidManifest.xml` del SDK. Leer más <Anchor target="_blank" href="/marketers/es/docs/bulletin-the-android-sdk-adds-the-ad-id-permission">aquí</Anchor>.</li><li>Se corrigió un problema relacionado con la optimización y ofuscación mediante el uso de R8.</li></ul> |
| 6.7.0  <br />(En desuso)  <br />Fin del soporte:  <br />2025-09-08 | 19-06-2022 | <ul><li>**En desuso.** Utilice V6.8.2.</li><li>Se cambió el modo en que el SDK gestiona las peticiones a los servidores de AppsFlyer. Después de este cambio, la solicitud para reportar la primera apertura de la aplicación (conversión) se priorizará sobre los eventos in-app y otros tipos de solicitudes. Leer más <Anchor target="_blank" href="/marketers/es/docs/bulletin-adding-a-priority-queue-to-the-android-sdk">aquí</Anchor>.</li><li>**Nueva API:** <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setdisablenetworkdata">`setDisableNetworkData`</Anchor> para optar por no recopilar la información sobre la red de telefonía celular (nombre de la compañía telefónica, nombre del operador).</li></ul> |
| 6.6.1  <br />Fin del soporte:  <br />2025-03-03 | 16-05-2022 | Mantenimiento del SDK |
| 6.6.0  <br />Fin del soporte:  <br />2025-03-03 | 01-05-2022 | <ul><li>Se agregaron más parámetros a la devolución de llamada `onDeepLinking` de UDL para el flujo de Direct Deep Linking (usuarios existentes). <Anchor target="_blank" href="/marketers/es/docs/bulletin-additional-parameters-available-for-deep-linking-existing-users">Para obtener más información</Anchor>.</li></ul> |
| 6.5.4  <br />Fin del soporte:  <br />2025-03-03 | 23-03-2022 | Mantenimiento del SDK |
| 6.5.3  <br />Fin del soporte:  <br />2025-03-03 | 09-03-2022 | <ul><li>**Corrección de errores:** Se solucionó un problema en la creación de enlaces de invitación de usuario que contienen caracteres que no son del inglés.</li></ul> |
| 6.5.2  <br />Fin del soporte:  <br />2025-03-03 | 26-01-2022 | <ul><li>Se solucionó el problema al resolver la URL para los deferred deep linking en UDL.</li><li>Actualizado a DexGuard 9.2</li><li>Refactorización y cambios internos.</li></ul> |
| 6.5.1  <br />Fin del soporte:  <br />2025-03-03 | 29-12-2021 | <ul><li>Resolución de Deep Linking con UDL para aplicaciones que utilizan la <Anchor target="_blank" href="/marketers/es/docs/set-up-multi-store-android-attribution#channel-name">opción out-of-Store with Channel</Anchor></li></ul> |
| 6.5.0  <br />Fin del soporte:  <br />2025-03-03 | 07-12-2021 | <ul><li>Refactorización y cambios internos.</li></ul> |
| 6.4.3  <br />Fin del soporte:  <br />2025-03-03 | 14-11-2021 | <ul><li>Se solucionó un error introducido en  `V6.4.2` con `LinkGenerator` que causaba la creación de enlaces con parámetros de URL faltantes.</li></ul> |
| 6.4.2  <br />Fin del soporte:  <br />2025-03-03 | 24-10-2021 | Se resolvieron los siguientes:<ul><li>El parámetro `pid` se anexa dos veces a las URL personalizadas generadas por `LinkGenerator`.</li><li>Se agregó un `/` adicional al valor `af_dp` al usar `LinkGenerator` para crear esquemas URI personalizados.</li><li>Se recopilaban tanto el IMEI como el AndroidID, si la aplicación activaba la recopilación de solo uno de ellos.</li></ul> |
| 6.4.1  <br />Fin del soporte:  <br />2025-03-03 | 17-10-2021 | Se resolvió el error de compilación al usar una versión de Gradle anterior a V3.5.4. |
| 6.4.0  <br />Fin del soporte:  <br />2025-03-03 | 12-09-2021 | **Nueva API:** <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setsharingfilterforpartners">`setSharingFilterForPartners`</Anchor> te permite configurar qué partners debe excluir el SDK del uso compartido de datos.<br /><br />A partir de esta versión, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setsharingfilter">`setSharingFilter`</Anchor> y <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setsharingfilterforallpartners">`setSharingFilterForAllPartners`</Anchor> están en desuso. |
| 6.3.2<br /><br />Fin del soporte: 2024-08-31 | 06-06-2021 | **Nueva API**: [`setDisableAdvertisingIdentifiers`](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setdisableadvertisingidentifiers) |
| 6.3.1  <br />Fin del soporte: 2024-08-31 | 26-05-2021 | <ul><li>**Nueva API**: [`performOnDeepLinking`](https://dev.appsflyer.com/hc/docs/conversion-data)</li><li>Se agregó la capacidad de activar la <Anchor target="_blank" href="/marketers/es/docs/user-invite-attribution#procedimientos">API de invitación de usuarios</Anchor> antes de llamar a `start`/después de llamar a `stop`</li><li>**Corrección de errores**: se corrigió un problema por el que una llamada a `waitForCustomerUserId` no se liberaba incluso después de llamar a `setCustomerUserId`</li></ul> |
| 6.3.0  <br />Fin del soporte: 2024-08-31 | 29-04-2021 | <ul><li>**Corrección de errores**: invocación incorrecta de `onConversionDataFail` tras un error en la solicitud de envío de eventos in-app</li><li>**Corrección de errores**: recopilación de métricas del sensor de movimiento (para la detección de fraude)</li><li>**Corrección de errores**: corrección relacionada con la ofuscación de <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unified-deep-linking-udl">UDL</Anchor></li><li>Actualización técnica de la API de OneLink</li></ul> |
| 6.2.3  <br />Fin del soporte: 2024-08-31 | 04-03-2021 | Mantenimiento del SDK |
| 6.2.0  <br />Fin del soporte: 2024-08-31 | 07-02-2021 | <ul><li>**Nueva API**: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setpartnerdata">`setPartnerData`</Anchor></li></ul> |
| 6.1.4  <br />Fin del soporte: 2024-08-31 | 12-01-2021 | <ul><li>Se agregó soporte para DexGuard V9</li></ul> |
| 6.1.3  <br />Fin del soporte: 2024-08-31 | 24-12-2020 | <ul><li>**Nueva API**: <Anchor target="_blank" href="/marketers/es/docs/additional-sdk-integration-guide#record-push-notifications">`addPushNotificationDeepLinkPath`</Anchor> (admite Movable Ink)</li></ul> |
| 6.1.1  <br />Fin del soporte: 2024-08-31 | 03-12-2020 | <ul><li>Se agregó soporte para Samsung Galaxy Store referrer</li><li>Corrección de errores menores y mejoras de rendimiento.</li></ul> |
| 6.1.0  <br />Fin del soporte: 2024-08-31 | 09-11-2020 | <ul><li>Se agregó soporte para la <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unified-deep-linking-udl">API de deep linking unificado</Anchor></li></ul> |
| 6.0.1  <br />Fin del soporte: 2024-08-31 | 28-10-2020 | Mantenimiento del SDK |
| 6.0.0  <br />Fin del soporte: 2024-08-31 | 2020-10-14 | <ul><li>Cambios importantes en la funcionalidad del SDK y en la API, incluidos cambios en los nombres de los métodos y en las versiones obsoletas. [Saber más](/docs/appsflyer-android-sdk-release-notes#android-v600-release-notes)</li></ul> |

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/appsflyer-sdk-version-control-policy">Política de control de versiones del SDK de AppsFlyer</Anchor>

<div data-zendesk-anchors="h_01JVHFG6PN34YFWNZKX2CYHJV8=importante end-of-support-vs-deprecated=fin-del-soporte-vs-obsoleto h_01JVHEKR4MTFV0FDHMTQW00BCS=fin-del-soporte-vs-obsoleto android-sdk-v6=lanzamientos-del-sdk-para-android h_01H9ZPCP8RWF24WAZ6YYMA1GS0=lanzamientos-del-sdk-para-android deprecated-versions=versiones-del-sdk-no-compatibles 01JHFAXXV51DHADQ7P2Q6RHFX0=versiones-del-sdk-no-compatibles h_01HDNZ774ME3SVT89JS7R4MSKE=consulta-tambi%C3%A9n" />
