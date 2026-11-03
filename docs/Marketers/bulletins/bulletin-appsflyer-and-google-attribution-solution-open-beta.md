---
title: 'Boletín: solución de atribución de AppsFlyer y Google [beta abierta]'
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2025-08-06T13:24:32Z'
  edited_at: '2026-10-20T03:54:33Z'
  id: 37857301293457
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/37857301293457
---
<Embed title="Reproductor de vídeos de YouTube" typeOfEmbed="youtube" url="https://www.youtube.com/embed/VilMr6T0Yd0?si=p7FezQwuKkBtwkaB" providerUrl="https://www.youtube.com" />

| Sección. | Detalles |
| --- | --- |
| **¿Qué hay de nuevo?** | La solución Integrated Conversions Measurement (ICM) de Google estará disponible para todos los clientes que usen Google Ads para medir instalaciones y reatribuciones. |
| **Fecha estimada de disponibilidad general (beta abierta):** | <ul><li>**iOS** – beta abierta (a partir del 12 de noviembre) - abierta a todas las aplicaciones.</li><li>**Android** – beta abierta (a partir del 5 de diciembre de 2025) - abierta a todas las aplicaciones.</li></ul> |
| **Lo que debes saber:** | <ul><li>ICM permite a AppsFlyer atribuir instalaciones a Google Ads sin necesidad de ID de dispositivo, mediante métodos que preservan la privacidad.</li><li>Google envía reclamaciones de instalación no deterministas a AppsFlyer.<br />Si AppsFlyer las valida con sus datos, estas reclamaciones se usan para la atribución. Para obtener más información, consulta <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-integration-setup-for-advertisers#flujo-de-atribución-de-google-ads-con-intercambio-avanzado-de-datos">Flujo de atribución de Google Ads con Advanced Data Sharing</Anchor>.</li></ul> |
| **Lo que debes hacer** | <ul><li>**Requisitos del SDK:**<ul><li>**iOS:** Requiere AppsFlyer <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-release-notes">iOS SDK versión 6.17.9</Anchor> o posterior *y* Google <Anchor target="_blank" href="https://github.com/firebase/firebase-ios-sdk/releases">Firebase SDK versión 11.14.0</Anchor> o posterior, o el <Anchor target="_blank" href="https://support.google.com/google-ads/answer/16384720">Google ODM SDK</Anchor> independiente.</li><li>**Android:** No se requiere actualizar el SDK.</li></ul></li><li>**Botón de alternancia de Advanced Data Sharing:** Un nuevo ajuste en las integraciones `googleadwords_int` de iOS y Android:<ul><li>Cuando está **activado**: AppsFlyer enviará todos los eventos de instalación a Google, incluso sin ID de dispositivo.</li><li>Cuando está **desactivado**: solo se compartirán los eventos de instalación con ID de dispositivo disponible o GCLID, lo que limita la eficacia de ICM.</li></ul></li><li>**Importante (solo iOS):** ICM no está disponible para el tráfico procedente de usuarios del Espacio Económico Europeo (EEE), el Reino Unido y Suiza.</li></ul> |