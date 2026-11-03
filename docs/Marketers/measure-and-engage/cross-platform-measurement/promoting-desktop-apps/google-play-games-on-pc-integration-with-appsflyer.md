---
title: Integración de Google Play Games para PC con AppsFlyer
metadata:
  keywords:
    - Marketers
    - cross-platform
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2023-09-05T13:06:17Z'
  edited_at: '2026-08-12T12:10:36Z'
  id: 18315431772817
  locale: es
  section: Promoting Desktop apps
  section_id: 15329004312593
  url: https://support.appsflyer.com/hc/es/articles/18315431772817
---
> **En resumen:** Integra tu juego o aplicación de Google Play Games para PC/Android con AppsFlyer para medir el rendimiento de las campañas de marketing que promocionan estas aplicaciones.

## Acerca de la atribución en Google Play Games para PC

Google Play Games es una aplicación para PC que permite a los usuarios explorar, descargar y jugar a juegos móviles de Android seleccionados en un ordenador de sobremesa o portátil con Windows. Google Play Games funciona en dispositivos PC con Windows.

Las aplicaciones que se ejecutan en Google Play Games son como cualquier otra aplicación de Android. Se trata básicamente de juegos móviles de Android disponibles en PC. Y, como cualquier otra aplicación móvil de Android, pueden integrarse de forma inmediata con AppsFlyer mediante el SDK de AppsFlyer para Android para recibir datos de atribución y mediciones de rendimiento sobre  qué fuentes y campañas impulsan la apertura de la aplicación  y los eventos in-app. Los marketers confían en estos insights para medir y optimizar las actividades de marketing.

AppsFlyer utiliza el mismo flujo de atribución para las aplicaciones que se ejecutan en Google Play Games que para las aplicaciones móviles de Android.

## Procedimientos de integración

En la siguiente tabla se enumeran las tareas necesarias para integrar tu aplicación de Google Play Games con AppsFlyer.

| Tarea | Acciones | ¿Quién está involucrado? |
| --- | --- | --- |
| Configuración de la aplicación | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Crea una cuenta de AppsFlyer</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/user-management">Agrega usuarios a la cuenta con los permisos adecuados</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/adding-an-app-to-appsflyer">Agrega tu aplicación Android en AppsFlyer</Anchor></li></ul> | Comercializador |
| Integración del SDK con tu aplicación | Integra el <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk">SDK de AppsFlyer para Android</Anchor>. | Desarrolladores de aplicaciones |
| Configuración de la landing page multiplataforma | **Recomendado**: La landing page multiplataforma que ejecuta AppsFlyer Smart Script te permite realizar atribución web-to-app. Es más recomendable cuando tu campaña promociona una aplicación que también está disponible en otras plataformas, como Epic y Steam.<br /><br /><Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">Obtén más información sobre las landing page multiplataforma</Anchor><br /><br /><Anchor target="_blank" href="/marketers/es/docs/cross-platform-landing-pages-with-smart-script">Aprende a configurar una landing page</Anchor> | Marketer (puede requerir ayuda del desarrollador) |
| Configuración del enlace | Si no utilizas una landing page multiplataforma, puedes crear enlaces de atribución directos para colocarlos detrás de los anuncios. Las campañas de marketing para aplicaciones de Google Play Games usan enlaces similares a los enlaces de atribución creados en AppsFlyer para aplicaciones móviles.<br /><br /><Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">Aprende a crear enlaces</Anchor> | Comercializador |
| Configuración/visualización de datos de reportes | Los dashboards y reportes de AppsFlyer para aplicaciones de Google Play Games son similares a los disponibles para aplicaciones móviles.<br /><br /><Anchor target="_blank" href="/marketers/es/docs/analyze-your-data">Saber más sobre los dashboards y reportes de AppsFlyer</Anchor> | Marketer/Ingeniero de datos |

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-attribution-concepts">Conceptos de plataformas de CTV, PC y consolas</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/google-ads-web-integration-for-pc-and-console-apps">Integración web de Google Ads para aplicaciones de PC y consola</Anchor>

<div data-zendesk-anchors="about-steam-attribution=acerca-de-la-atribuci%C3%B3n-en-google-play-games-para-pc 01H7Z1DJRW1KPJQ4CZ6T85ASRK=acerca-de-la-atribuci%C3%B3n-en-google-play-games-para-pc integration-procedures=procedimientos-de-integraci%C3%B3n 01H7Z1DJRWX54DN2SNS21GPGXB=procedimientos-de-integraci%C3%B3n h_01HDP2XBSEJVQ5G0MD0V5R05CM=consulta-tambi%C3%A9n" />
