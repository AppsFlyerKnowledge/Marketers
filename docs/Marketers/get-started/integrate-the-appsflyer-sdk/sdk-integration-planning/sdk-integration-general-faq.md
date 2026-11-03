---
title: Preguntas frecuentes generales sobre la integración del SDK
metadata:
  keywords:
    - Advertisers
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
  created_at: '2015-01-18T11:13:24Z'
  edited_at: '2026-08-22T00:15:08Z'
  id: 207033546
  locale: es
  section: SDK integration planning
  section_id: 6551182964369
  url: https://support.appsflyer.com/hc/es/articles/207033546
---
> **At a glance:** El SDK de AppsFlyer te permite publicitar de forma segura tu aplicación, atribuir, hacer enlaces profundos y recopilar información de comportamiento de tus usuarios móviles. Puedes configurar y comenzar a trabajar con cualquier red de publicidad y/o plataforma en cuestión de minutos, ¡no semanas o meses!

## ¿Cómo instalar y actualizar el SDK de AppsFlyer?

Para saber cómo instalar y actualizar el SDK de AppsFlyer, consulta <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/sdk-installation">el Centro de desarrollo</Anchor>. **Nota**: actualizar el SDK implica lanzar una nueva versión de tu app en las tiendas.

## ¿Es difícil integrar el SDK de AppsFlyer?

En menos de una hora, un desarrollador experimentado puede preparar aplicaciones para la atribución con AppsFlyer. Luego, solo necesitan Unos minutos por aplicación.

Echa un vistazo a las guías de integración del SDK de AppsFlyer para <Anchor target="_blank" href="/marketers/es/docs/sdk-integration-overview">Android</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/sdk-integration-overview">iOS</Anchor>, Unity, o estas <Anchor target="_blank" href="/marketers/es/docs/other-platforms">otras plataformas</Anchor>.

## ¿El SDK de AppsFlyer afecta el tiempo de descarga de la aplicación?

Los paquetes del SDK de AppsFlyer están diseñados y desarrollados para tener un efecto *casi nulo* en el rendimiento de la aplicación. Todas las versiones del SDK son ligeras y, por lo general, ocupan menos del 1 % del tamaño de una aplicación. En otras palabras, **el efecto en el tiempo total de descarga de la aplicación es marginal**.

* **SDK de Android:** ~300KB
* **SDK de iOS:** ~3,4 MB

## ¿El SDK de AppsFlyer afecta el rendimiento de la aplicación?

Las API del SDK de AppsFlyer son principalmente métodos *setter*/*getter* o métodos rápidos de servicios web asíncronos que envían/reciben datos de los servidores de AppsFlyer. Esto significa que las API del SDK tienen un efecto insignificante en el rendimiento de la aplicación.

En otras palabras, **el SDK de AppsFlyer no tiene ningún efecto en el rendimiento de la aplicación ni en la experiencia del usuario**.

## ¿Puedo registrar eventos in-app que ocurran fuera de mi aplicación?

Puedes usar la <Anchor target="_blank" href="/marketers/es/docs/server-to-server-events-api-for-mobile-s2s-mobile">API de S2S para reportar eventos</Anchor> que tienen lugar fuera de la app; por ejemplo, un usuario renueva su suscripción usando tu interfaz web. Los eventos S2S, una vez registrados, están disponibles en toda la plataforma, incluyendo paneles, raw data y análisis.

<div data-zendesk-anchors="how-to-install-and-update-the-appsflyer-sdk=c%C3%B3mo-instalar-y-actualizar-el-sdk-de-appsflyer h_01HSXBYM9WMD9CDX03RFHM0JY1=c%C3%B3mo-instalar-y-actualizar-el-sdk-de-appsflyer is-it-hard-to-integrate-the-appsflyer-sdk=es-dif%C3%ADcil-integrar-el-sdk-de-appsflyer h_01HMTWQHQRGE6Z2BM1BBQY04H1=es-dif%C3%ADcil-integrar-el-sdk-de-appsflyer does-the-appsflyer-sdk-affect-app-download-time=el-sdk-de-appsflyer-afecta-el-tiempo-de-descarga-de-la-aplicaci%C3%B3n h_01HMTWQHQRQQ47CAJCA4Y0AASZ=el-sdk-de-appsflyer-afecta-el-tiempo-de-descarga-de-la-aplicaci%C3%B3n does-the-appsflyer-sdk-affect-app-performance=el-sdk-de-appsflyer-afecta-el-rendimiento-de-la-aplicaci%C3%B3n h_01HMTWQHQRXBPQN75J0KM48AJ2=el-sdk-de-appsflyer-afecta-el-rendimiento-de-la-aplicaci%C3%B3n can-i-record-inapp-events-that-occur-outside-my-app=puedo-registrar-eventos-in-app-que-ocurran-fuera-de-mi-aplicaci%C3%B3n h_01HMTWQHQSP646Y8KVZSBA01TF=puedo-registrar-eventos-in-app-que-ocurran-fuera-de-mi-aplicaci%C3%B3n" />
