---
title: Implicaciones de ATT (iOS 14+) y desuso de LAT
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Developers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
    - Ad Networks
  created_at: '2020-10-07T17:33:35Z'
  edited_at: '2026-08-12T12:21:11Z'
  id: 360014090597
  locale: es
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/es/articles/360014090597
---
> **En resumen:** A partir de iOS 14, iOS utiliza ATT para determinar las preferencias de privacidad del usuario y la función Limitar seguimiento de anuncios (LAT) queda obsoleta.

### Valor ATT

* A partir de iOS 14: Apple <Anchor target="_blank" href="https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/">ATTrackingManager</Anchor> (ATT) proporciona los valores de estado para la autorización de seguimiento de aplicaciones.
* AppsFlyer obtiene ATT de las siguientes fuentes:
  * AppsFlyer SDK V6+ integrado en la aplicación.
  * Por API de anunciantes. Por ejemplo, API S2S.
* ATT está disponible en reportes de raw data. Debes solicitarlo explícitamente de la siguiente manera:
  * API Pull Agrega ATT *al*parámetro additional\_fields en tus solicitudes de API Pull.
  * Página de datos exportados: En la pestaña de campos del reporte, selecciona explícitamente ATT.
  * Observación
  * API Push En la página de acceso a la API, agrega explícitamente ATT a la lista de campos.
* En algunos casos, ATT se completa con valores definidos por AppsFlyer. Se indican con el prefijo *af* en la tabla.
* Si IDFA no está disponible, se completa con ceros.

#### Valores ATT definidos por Apple

| Estado de ATT | Disponibilidad de IDFA | Comportamiento |
| --- | --- | --- |
| not\_determined | En iOS 14-14.4: Disponible<br /><br />A partir de iOS 14.5: No disponible | Valor predeterminado de ATT |
| restringido | No disponible | Esto lo determina Apple en función de la cuenta de iTunes y no está relacionado con el comportamiento del usuario. Por ejemplo, en función de la edad del usuario, los dispositivos son controlados por organizaciones. |
| Denegado | No disponible | Ocurre si se cumple alguna de las siguientes situaciones:<ul><li>Se estableció después de mostrar el aviso.</li><li>El usuario desactivó *Permitir que las aplicaciones soliciten el seguimiento* (interruptor maestro a nivel de dispositivo).</li><li>Antes de instalar iOS 14 en el dispositivo, LAT estaba activado.</li></ul> |
| autorizado | disponible | El usuario dio su consentimiento explícito. |

#### Valores ATT adicionales definidos por AppsFlyer

| Estado de ATT | Nota | Disponibilidad de IDFA |
| --- | --- | --- |
| af\_unknown | El anunciante reportó el valor ATT pero no es un valor conocido según la especificación <Anchor target="_blank" href="https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/">ATTrackingManager</Anchor> | Depende de la versión de iOS |
| af\_authorized | El uso de IDFA está permitido por una de las siguientes razones:<ul><li>Versión iOS del dispositivo: anterior a iOS 14.</li><li>El evento reportado contenía IDFA pero no ATT. Por ejemplo, una aplicación que tiene SDK V5.X en un dispositivo que ejecuta una versión de iOS anterior a iOS 14.</li></ul> | disponible |
| af\_unavailable | <ul><li>El anunciante no reportó ATT en el evento y el IDFA no está disponible.</li><li>La versión V5.X del SDK de AppsFlyer no puede obtener ATT y no obtuvo IDFA</li></ul> | No disponible |

### ¿LAT está en iOS? Consideraciones y cómo se traduce LAT a ATT en iOS 14

| Versión de iOS | Uso de Is LAT |
| --- | --- |
| Hasta iOS 13 | <Image alt="IsLatTrue_us-en.png" src="https://files.readme.io/28440075d9c3913a148228a85ede15048d76f24913b48799ec4de3952d8f33e7-360011938457.png" width="221px" /><br /><br />Si es verdadero, el Limit Ad Tracking (IDFA) habilitado para el usuario no está disponible. |
| A partir de iOS 14 | <Anchor target="_blank" href="https://developer.apple.com/documentation/adsupport/asidentifiermanager/1614148-isadvertisingtrackingenabled">Apple dejó obsoleto el sistema *Is LAT*</Anchor>. Ignora el valor *Is LAT* y utiliza ATT en su lugar. |

**Cómo se traduce LAT a ATT en iOS 14**

[<Image alt="LATtoiOS14.5.png" src="https://files.readme.io/872b3acdcd975337ff4de791a9fc98cd45eb50a487e80b3dfad6a1c7d9495739-360017977837.png" width="522px" />](https://files.readme.io/872b3acdcd975337ff4de791a9fc98cd45eb50a487e80b3dfad6a1c7d9495739-360017977837.png)

<div data-zendesk-anchors="att-values=valor-att h_01HGX9468F5YF0KSHB3S49CW2Y=valor-att att-values-defined-by-apple=valores-att-definidos-por-apple h_01HGX9468F0TFTMKP1W2J6GEBV=valores-att-definidos-por-apple additional-att-values-defined-by-appsflyer=valores-att-adicionales-definidos-por-appsflyer h_01HGX96RG9NX9QM2WTX8789DDR=valores-att-adicionales-definidos-por-appsflyer is-lat-in-ios%E2%80%94considerations-and-how-lat-translates-to-att-in-ios-14=lat-est%C3%A1-en-ios-consideraciones-y-c%C3%B3mo-se-traduce-lat-a-att-en-ios-14 h_01HGX9468F0VTYNXBJRSTNBCMB=lat-est%C3%A1-en-ios-consideraciones-y-c%C3%B3mo-se-traduce-lat-a-att-en-ios-14" />
