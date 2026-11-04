---
title: 'Guía de configuración de X Ads (anteriormente Twitter Ads):'
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T09:31:36Z'
  edited_at: '2026-08-12T12:22:35Z'
  id: 4410464316049
  locale: es
  section: X Ads (formerly Twitter Ads)
  section_id: 6551370375569
  url: https://support.appsflyer.com/hc/es/articles/4410464316049
---
> **En resumen:** Aprende el concepto de la integración de tu cuenta de X Ads con AppsFlyer.

<Image alt="Logotipo_X_Ads.png" src="https://files.readme.io/cecae90650321943ad1cb6d22b7f27d3d28b0484f1706cb1be1a19099dfbb20d-20375448207377.png" width="167px" />

<div id="mobile-app-promotion-on-x-ads" />

## Promoción de aplicaciones móviles en X Ads

La promoción de aplicaciones móviles en X Ads es un método para promocionar aplicaciones en X Ads. Permite que los anunciantes promocionen sus aplicaciones móviles mediante un diseño genial de tarjeta para las aplicaciones que impulse las instalaciones, el engagement en la aplicación y los deep linking. Los usuarios pueden instalar con facilidad las aplicaciones e interactuar con ellas directamente desde su cronología de X Ads.

<div id="x-ads-user-privacy" />

## Privacidad del usuario de X Ads

Los usuarios de X Ads pueden controlar cómo comparten información con los anunciantes:

* Si la configuración de los usuarios se establece para evitar el intercambio de la información de engagement con los anunciantes, sus instalaciones y eventos in-app de X Ads se omiten del raw data, pero aún se atribuyen a X Ads.
* Los datos de atribución agregados se reflejan correctamente en AppsFlyer y no se ven afectados por la política de X Ads.
* Como resultado, los reportes de datos agregados y raw data de X Ads no se correlacionan.

A partir del 31 de julio de 2021, los anunciantes que no estén en el programa de medición móvil avanzada (AMM) de X Ads dejarán de recibir todos los datos a nivel de usuario de X Ads MACT.

A través del programa AMM, los anunciantes pueden recibir datos a nivel de usuario más completos después de otorgar a X Ads el derecho a realizar una auditoría para garantizar que los datos de X Ads se utilicen exclusivamente con fines de medición. Esto es consistente con la ley de protección de datos aplicable y las prácticas comunes en toda la industria.  
**Para unirse al programa AMM:** Ve a ads.twitter.com/help > **Aplicación móvil, seguimiento de conversiones y administrador de audiencias**, y selecciona **Formulario de acuerdo del programa de Medición Móvil Avanzada**.

Ten en cuenta que los datos a nivel de usuario recibidos antes de unirte al programa AMM no se pueden exportar.

Para más información, contacta con tu administrador de cuentas de X Ads.

<div id="x-ads-and-appsflyer-skan-interoperation" />

## Interoperación de X Ads y AppsFlyer SKAN

X Ads envía los datos de postbacks de SKAdNetwork a través de una API dedicada. Los datos de SKAN de X Ads se mostrarán en el dashboard de <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">SKAN</Anchor>.

X Ads enriquece los postbacks de SKAN con los siguientes campos de datos:

* Nombre de la campaña
* ID de campaña
* Nombre del conjunto de anuncios
* ID del adset

<div data-zendesk-anchors="mobile-app-promotion-on-twitter=promoci%C3%B3n-de-aplicaciones-m%C3%B3viles-en-x-ads h_01H9QR6TH7M0H5YMXRWVVAYRK9=promoci%C3%B3n-de-aplicaciones-m%C3%B3viles-en-x-ads twitter-user-privacy=privacidad-del-usuario-de-x-ads h_01H9QR6TH74R50K00H7FYN61KC=privacidad-del-usuario-de-x-ads twitter-ads-and-appsflyer-skan-interoperation=interoperaci%C3%B3n-de-x-ads-y-appsflyer-skan h_01H9QR6TH74PKBGM5RC4M118GE=interoperaci%C3%B3n-de-x-ads-y-appsflyer-skan" />
