---
title: 'Obtén datos de conversión con el SDK de AppsFlyer: descripción general'
metadata:
  keywords:
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
  created_at: '2021-11-09T10:06:52Z'
  edited_at: '2026-08-12T12:00:41Z'
  id: 4410481069969
  locale: es
  section: Conversion data
  section_id: 6551287787537
  url: https://support.appsflyer.com/hc/es/articles/4410481069969
---
> **En resumen:** Usa los datos de conversión para identificar varios escenarios de conversión, personalizar la experiencia del usuario y mucho más.

Usa los datos de conversión para:

* Envía usuarios a actividades específicas
* Asístelos con contenido personalizado

<div id="important" />

> 🚧 **Dos puntos (:)**
>
> **Limitaciones de los datos de conversión del SDK**
>
> Si usas la devolución de llamada `onConversionDataSuccess` del SDK de AppsFlyer, ten en cuenta que puede activarse antes de que se complete el proceso de atribución. Como resultado, es posible que los datos devueltos por el SDK no coincidan con los datos de los reportes o las API de AppsFlyer.
>
> **Recomendación:**
> No uses el método Get Conversion Data (GCD) para recopilar o validar Datos de atribución.
> Para obtener resultados de atribución precisos y completos, usa los dashboards, los reportes o las API de AppsFlyer.

<div id="get-conversion-data" />

## Obtener datos de conversión

El SDK de AppsFlyer devuelve los datos de conversión de la siguiente manera:

* * `onConversionDataSuccess`: Conversiones de adquisición de usuarios (UA) y reatribución
    * Android: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerconversionlistener#onconversiondatasuccess">onConversionDataSuccess</Anchor>
    * iOS: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlibdelegate#onconversiondatasuccess">onConversionDataSuccess</Anchor>
    * Unity: loadConversionData
  * `onAppOpenAttribution`: Para conversiones de re-engagement

<div data-zendesk-anchors="h_01K9KSQQDVDEACFRXS0M4JNW9M=dos-puntos- get-conversion-data=obtener-datos-de-conversi%C3%B3n h_01HTZ6M409RPZAQM66R0H5HA16=obtener-datos-de-conversi%C3%B3n" />
