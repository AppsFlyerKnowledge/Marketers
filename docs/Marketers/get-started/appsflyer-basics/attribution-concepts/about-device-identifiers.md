---
title: Identificadores de dispositivo
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2021-10-12T14:16:09Z'
  edited_at: '2026-08-12T11:56:30Z'
  id: 4408847686161
  locale: es
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/es/articles/4408847686161
---
> **De un vistazo:** Comprende los identificadores de dispositivos compatibles con el SDK de AppsFlyer.

<div id="overview" />

## Visión general

El SDK de AppsFlyer recopila identificadores de dispositivos con fines de <Anchor target="_blank" href="/marketers/es/docs/basic-sdk-integration-guide#atribución">atribución</Anchor>.

El SDK recopila automáticamente identificadores como el ID de AppsFlyer y el ID de publicidad de Google (GAID). La recopilación de otros identificadores para tu aplicación depende de tus necesidades (por ejemplo, recopilar tiendas de aplicaciones de Android de terceros o aplicaciones comercializadas en China).

<div id="android-device-identifiers" />

## Identificadores de dispositivos Android

El SDK admite los siguientes identificadores de dispositivo para todas las plataformas:

<div id="apps-published-on-google-play" />

#### Apps publicadas en Google Play

| Identificador de dispositivo | Finalidad |
| --- | --- |
| <span id="gaid"></span>GNA Company | Un identificador **que el usuario puede restablecer**, para los usuarios de Android de Google Play.<br /><br />A partir del SDK V4.8.0, AppsFlyer recopila automáticamente este identificador de dispositivo. |

<div id="apps-published-in-third-party-app-stores" />

#### Aplicaciones publicadas en tiendas de aplicaciones de terceros

| Identificador de dispositivo | Finalidad |
| --- | --- |
| <span id="amazon-advertising-id"></span>ID de publicidad de Amazon | Un identificador único y **que el usuario puede restablecer**, utilizado por Fire TV de Amazon. <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-attribution-concepts">Ver descripción general de CTV</Anchor> |
| <span id="oaid"></span>OAID | Un identificador **que el usuario puede restablecer**, utilizado por algunos mercados de Android fuera de la tienda.  Para obtener más información, consulta la <Anchor target="_blank" href="/marketers/es/docs/android-oaid-implementation-in-the-sdk">Guía para implementar el OAID</Anchor>. |
| <span id="android-id"></span>ID de Android | Identificador de dispositivo móvil único y **que no se puede restablecer**, que se utiliza en tiendas de aplicaciones de terceros. El SDK no recopila automáticamente el ID de Android. Sin embargo, si es necesario recopilar estos identificadores, tu desarrollador puede implementar la recopilación.<br /><br />**Nota:** El ID de Android no se puede usar junto con el GAID. |

<div id="apple-device-identifiers" />

## Identificadores de dispositivos Apple

El SDK admite los siguientes identificadores de dispositivo para plataformas Android:

| Identificador de dispositivo | Finalidad |
| --- | --- |
| <span id="idfa"></span>Identificador de anunciante (IDFA) | Un identificador único que **que el usuario puede restablecer**, para usuarios de Apple iOS o tvOS (Apple TV). Desde el lanzamiento de iOS 14.5, el IDFA está disponible solo si el usuario consiente a través del <Anchor target="_blank" href="/marketers/es/docs/about-att-and-skan#att-principles">aviso de ATT</Anchor>. |
| <span id="idfv"></span>IDFV | Un identificador de dispositivo compartido por todas las aplicaciones del **mismo proveedor** en el dispositivo. Una vez instalada la primera aplicación, se le asigna el ID, y a otras aplicaciones del mismo proveedor se les asigna el mismo IDFV. A las aplicaciones de otros proveedores se les asigna un IDFV diferente.<br /><br />Además, cuando se eliminan todas las aplicaciones de un proveedor específico, se elimina el IDFV de ese proveedor y, tras una nueva instalación, se asignará un nuevo IDFV. |

<div id="ctv--pc-and-console-app-device-identifiers" />

## Identificadores de dispositivos CTV

El SDK admite los siguientes identificadores de dispositivo para plataformas iOS:

| Destino de engagement | Identificador de dispositivo |
| --- | --- |
| Android TV | advertising\_id |
| tvOS (Apple TV) | idfa |
| Amazon Fire TV | amazon\_fire\_id |
| Chromecast | advertising\_id |
| Roku | rida |
| Vizio | VIDA |
| Samsung | TIFA |
| LGUDID | IMEI |
| Xbox | custom |
| Finalidad | vidaaid |
| Steam | steamid |
| Meta Quest (Oculus) | custom |
| Epic Games | epicid |
| PlayStation | psid |
| PC Nativo | custom |
| Google Play Games para PC | Identificador de dispositivo |

<div data-zendesk-anchors="overview=visi%C3%B3n-general h_01H9YXEYC3PA271B3G3Y3GM9PS=visi%C3%B3n-general android-device-identifiers=identificadores-de-dispositivos-android h_01H9YXEYC3D95A6G70EGNR8ENK=identificadores-de-dispositivos-android apps-published-on-google-play=apps-publicadas-en-google-play h_01H9YXEYC3RG2XCVVW8MJ5VZSC=apps-publicadas-en-google-play apps-published-in-thirdparty-app-stores=aplicaciones-publicadas-en-tiendas-de-aplicaciones-de-terceros h_01H9YXEYC3JA3DPN6P43J1ZXR9=aplicaciones-publicadas-en-tiendas-de-aplicaciones-de-terceros apple-device-identifiers=identificadores-de-dispositivos-apple h_01H9YXEYC3733B1A85TEF35EAY=identificadores-de-dispositivos-apple ctv-device-identifiers=identificadores-de-dispositivos-ctv h_01H9YXEYC3DFPWVXA5Y3XANQ3P=identificadores-de-dispositivos-ctv" />
