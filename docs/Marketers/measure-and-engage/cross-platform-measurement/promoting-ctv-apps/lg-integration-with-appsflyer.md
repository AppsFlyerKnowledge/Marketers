---
title: Integración de LG con AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Developers
    - CTV
    - Marketers
    - CTV Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - CTV Attribution
  created_at: '2022-07-03T10:31:42Z'
  edited_at: '2026-08-12T12:10:14Z'
  id: 7341725624081
  locale: es
  section: Promoting CTV apps
  section_id: 15328952633489
  url: https://support.appsflyer.com/hc/es/articles/7341725624081
---
> **En resumen:** Integra tu aplicación LG Connected TV (CTV) con AppsFlyer para recibir datos de eventos y atribuciones para tus campañas en LG.

## Sobre la atribución de LG CTV

El sistema operativo LG Webos para streaming se ejecuta en todos los televisores LG.

Las aplicaciones CTV que se transmiten en LG pueden integrarse con AppsFlyer a través de la API para recibir datos de atribución y mediciones de rendimiento sobre qué fuentes (orgánicas y no orgánicas) y campañas impulsan la apertura de la aplicación y eventos in-app. Los marketers confían en estos insights para medir y optimizar las actividades de marketing.

La integración de LG API admite:

* Smart TVs LG.
* Atribución CTV-to-CTV y grabación de eventos. Significado, atribución y grabación en el dispositivo LG de un usuario.

## Procedimientos de integración

La siguiente tabla enumera las tareas necesarias para integrar tu aplicación LG CTV con AppsFlyer.

| Tarea | Acciones | Quién debe participar |
| --- | --- | --- |
| Configuración de la aplicación | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Crea una cuenta de AppsFlyer</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/user-management">Agrega usuarios a la cuenta con los permisos adecuados</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/adding-an-app-to-appsflyer">Agrega tu aplicación LG CTV en AppsFlyer</Anchor></li></ul> | Comercializador |
| Integración de la API con tu aplicación (a través de S2S o SDK) | Hay dos métodos de integración que puedes utilizar: S2S y SDK.<br /><br />Para el método S2S, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">integra la API de AppsFlyer</Anchor> en tu aplicación con comandos para reportar los siguientes eventos a AppsFlyer.<ul><li>Primeras aperturas</li><li>Eventos in-app</li><li>Sesiones</li></ul>**Nota**:<ul><li>Las instalaciones deben reportarse antes de las sesiones y eventos in-app.</li><li>Envía eventos usando la API. Dile a tu desarrollador qué eventos enviar. Verifica que cuando configuras la API, configuras y asignas los eventos para enviar a AppsFlyer.</li></ul>Para informar sobre engagements con medios propios, integra la <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">API de engagement con impresiones.</Anchor><br /><br />Para conocer el método SDK, consulta el centro de desarrolladores para obtener la <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-html5-ctv-sdk">documentación de LG</Anchor>. | Desarrolladores de aplicaciones |
| Integración de partners | Agrega LG Ads como ad network (partner integrado) en AppsFlyer.<ol><li><Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#a-activate-partner">Activar partner</Anchor></li><li>[Opcional] Activa la <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#e-install-attribution">**atribución view-through**</Anchor>.</li></ol> | Comercializador |
| Configuración del enlace | <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-direct-attribution-links">Aprende a crear enlaces de atribución directa</Anchor> | Comercializador |
| Configuración de reportes/ver datos | <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-attribution-concepts#disponibilidad-de-datos">Obtén más información sobre la disponibilidad de datos en dashboards y reportes</Anchor> | Marketer/Ingeniero de datos |

<div id="traits-and-limitations" />

<Accordion title="Rasgos y limitaciones">

| Caducado | Observaciones |
| --- | --- |
| Reorientación | Actualmente no es compatible |
| Datos de costos | Los datos de costos deben enviarse a través de Importación de costos <Anchor target="_blank" href="/marketers/es/docs/import-cost-data">utilizando el método de upload del archivo por correo electrónico.</Anchor> |
| Atribución | LG Ads utiliza modelos probabilísticos para la atribución; La coincidencia de ID no está disponible actualmente. |
| ID de cliente | Completa este parámetro con el ID de cliente de LG (`cust_id`) obtenido de LG Ads. |
| Atribución determinista | Hay una opción para habilitar la coincidencia determinista del ID de anuncio para Atribución. Para ello, se deben cumplir los siguientes requisitos:<ul><li>LG debe llevar a cabo una revisión legal antes de que se puedan habilitar las aplicaciones de partners de contenido para mostrar el ID de anuncio.</li><li>Esta revisión legal implica que el partner de contenido trabaje directamente con LG Electronics y requiere que ambas partes firmen un acuerdo legal.</li><li>Las aplicaciones de partners de contenido deben integrar la funcionalidad para recopilar y transmitir el ID de anuncio de LG, y lanzar una actualización de la aplicación iniciada por el usuario para empezar a mostrar el ID de anuncio a AppsFlyer.</li><li>Para obtener más información, ponte en contacto con tu CSM de AppsFlyer y con  [partnerships@lgads.tv](mailto:partnerships@lgads.tv)</li></ul> |

</Accordion>

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-attribution-concepts">Descripción general de las plataformas CTV, PC y consolas</Anchor>

<div data-zendesk-anchors="about-lg-ctv-attribution=sobre-la-atribuci%C3%B3n-de-lg-ctv 01H7Z17N0YAAGTDPMGZ89F7AVB=sobre-la-atribuci%C3%B3n-de-lg-ctv integration-procedures=procedimientos-de-integraci%C3%B3n 01H7Z17N0Y8RE5PS15N2JG5NRH=procedimientos-de-integraci%C3%B3n 01H7Z17N0YCX89SYYJ1AMPM6W4=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=consulta-tambi%C3%A9n" />
