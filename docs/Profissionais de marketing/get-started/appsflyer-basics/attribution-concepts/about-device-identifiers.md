---
title: Identificadores de dispositivo (device IDs)
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
  edited_at: '2026-08-18T00:09:02Z'
  id: 4408847686161
  locale: pt
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/pt/articles/4408847686161
---
> **Visão geral:** entenda quais identificadores de dispositivos são compatíveis com o SDK da AppsFlyer.

<div id="overview" />

## Visão geral

O SDK da AppsFlyer coleta identificadores de dispositivos para <Anchor target="_blank" href="/marketers/pt/docs/basic-sdk-integration-guide#atribuição">fins de atribuição</Anchor>.

O SDK coleta automaticamente identificadores como o AppsFlyer ID e o Google Advertising ID (GAID). A coleta de outros identificadores para seu aplicativo depende das suas necessidades (por exemplo, coleta de lojas de aplicativos Android de terceiros ou aplicativos comercializados na China).

<div id="android-device-identifiers" />

## Identificadores de dispositivos Android

O SDK oferece suporte aos seguintes identificadores de dispositivo para todas as plataformas:

<div id="apps-published-on-google-play" />

#### Aplicativos publicados no Google Play

| Identificador de dispositivo | Objetivo |
| --- | --- |
| <span id="gaid"></span>GAID | Um identificador **que pode ser redefinido pelo usuário** para usuários do Google Play no Android.<br /><br />A partir do SDK V4.8.0, a AppsFlyer passou a coletar automaticamente esse identificador de dispositivo. |

<div id="apps-published-in-third-party-app-stores" />

#### Aplicativos publicados em outras lojas de aplicativos

| Identificador de dispositivo | Objetivo |
| --- | --- |
| <span id="amazon-advertising-id"></span>Amazon Advertising ID | Um identificador exclusivo **que pode ser redefinido pelo usuário**, usado pelo Amazon Fire TV. <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-attribution-concepts">Veja a visão geral do CTV</Anchor> |
| <span id="oaid"></span>OAID | Um identificador **que pode ser redefinido pelo usuário** usado fora da loja de aplicativos em alguns mercados Android.  Para mais informações, consulte o <Anchor target="_blank" href="/marketers/pt/docs/android-oaid-implementation-in-the-sdk">Guia de implementação do OAID</Anchor>. |
| <span id="android-id"></span>ID Android | Um identificador de dispositivo mobile exclusivo e **não reconfigurável** usado em lojas de aplicativos de terceiros. O SDK não coleta automaticamente o Android ID. Porém, caso haja necessidade de coletar esses identificadores, seu desenvolvedor poderá implementar a coleta.<br /><br />**Observação:** o Android IDnão pode ser usado em conjunto com o GAID. |

<div id="apple-device-identifiers" />

## Identificadores de dispositivos Apple

O SDK oferece suporte para os seguintes identificadores de dispositivos para plataformas Android:

| Identificador de dispositivo | Objetivo |
| --- | --- |
| <span id="idfa"></span>IDFA | Um identificador exclusivo **que pode ser redefinido pelo usuário** para usuários do iOS da Apple ou tvOS (Apple TV). Desde o lançamento do iOS 14.5, o IDFA está disponível apenas caso o usuário permita o rastreamento no <Anchor target="_blank" href="/marketers/pt/docs/about-att-and-skan#att-principles">prompt da ATT</Anchor>. |
| <span id="idfv"></span>IDFV | Um identificador de dispositivo compartilhado por todos os aplicativos do **mesmo fornecedor** no dispositivo. Depois que o primeiro aplicativo é instalado, o ID é atribuído a ele, e outros aplicativos do mesmo fornecedor recebem o mesmo IDFV. Um IDFV diferente é atribuído aos aplicativos de outros fornecedores.<br /><br />Além disso, quando todos os aplicativos de um fornecedor específico são removidos, o IDFV desse fornecedor é excluído e, após uma nova instalação, um novo IDFV será atribuído. |

<div id="ctv--pc-and-console-app-device-identifiers" />

## Identificadores de dispositivos CTV

O SDK oferece suporte para os seguintes identificadores de dispositivo para plataformas iOS:

| Platform | Identificador de dispositivo |
| --- | --- |
| Android TV | advertising\_id |
| tvOS (Apple TV) | idfa |
| Amazon Fire TV | amazon\_fire\_id |
| Chromecast | advertising\_id |
| Roku | rida |
| Vizio | VIDA |
| Samsung | TIFA |
| LGUDID | IMEI |
| Xbox | personalizado |
| RIDA | vidaaid |
| Steam | steamid |
| Meta Quest (Oculus) | personalizado |
| Epic Games | epicid |
| PlayStation | psid |
| PC nativo | personalizado |
| Google Play Games no PC | Identificador de dispositivo |

<div data-zendesk-anchors="overview=vis%C3%A3o-geral h_01H9YXEYC3PA271B3G3Y3GM9PS=vis%C3%A3o-geral android-device-identifiers=identificadores-de-dispositivos-android h_01H9YXEYC3D95A6G70EGNR8ENK=identificadores-de-dispositivos-android apps-published-on-google-play=aplicativos-publicados-no-google-play h_01H9YXEYC3RG2XCVVW8MJ5VZSC=aplicativos-publicados-no-google-play apps-published-in-thirdparty-app-stores=aplicativos-publicados-em-outras-lojas-de-aplicativos h_01H9YXEYC3JA3DPN6P43J1ZXR9=aplicativos-publicados-em-outras-lojas-de-aplicativos apple-device-identifiers=identificadores-de-dispositivos-apple h_01H9YXEYC3733B1A85TEF35EAY=identificadores-de-dispositivos-apple ctv-device-identifiers=identificadores-de-dispositivos-ctv h_01H9YXEYC3DFPWVXA5Y3XANQ3P=identificadores-de-dispositivos-ctv" />
