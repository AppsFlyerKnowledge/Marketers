---
title: Integración de Samsung con AppsFlyer
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
  created_at: '2022-05-03T09:19:48Z'
  edited_at: '2026-10-07T00:11:24Z'
  id: 5860544738065
  locale: es
  section: Promoting CTV apps
  section_id: 15328952633489
  url: https://support.appsflyer.com/hc/es/articles/5860544738065
---
> **At a glance:** Integra tu aplicación Samsung Connected TV (CTV) con AppsFlyer para recibir datos de atribución y eventos para tus campañas en Samsung.

<div id="about-samsung-ctv-attribution" />

## Acerca de la atribución de CTV de Samsung

El sistema operativo Samsung Tizen para streaming se ejecuta en todos los televisores Samsung.

Las aplicaciones de CTV que hacen streaming en Samsung pueden integrarse con AppsFlyer a través de la API para recibir Datos de atribución y mediciones de rendimiento sobre qué fuentes (orgánicas y no orgánicas) y campañas impulsan la apertura de la Aplicación y los eventos in-app. Los marketers confían en estos insights para medir y optimizar las actividades de marketing.

La integración de la API de Samsung admite:

* Smart TVs de Samsung.
* Atribución de CTV a CTV y registro de eventos, lo que significa que la atribución y el registro se realizan en el dispositivo Samsung del usuario.

<div id="samsung-attribution-flow" />

### Flujo de atribución de Samsung

![[CONFIRM: Diagrama del flujo de atribución de Samsung CTV, que muestra los datos de instalación, Sesión y evento in-app moviéndose desde la Aplicación de Samsung a AppsFlyer a través de la API S2S o del SDK]](https://files.readme.io/a1031878e8aced81da5762d06ae0163770cd73b9a7c91224ea7665aa142d2ce8-7215151128209.png)

<div id="integration-procedures" />

## Procedimientos de integración

La siguiente tabla enumera las tareas necesarias para integrar tu aplicación Samsung CTV con AppsFlyer.

| Tarea | Acciones | ¿Quiénes están involucrados? |
| --- | --- | --- |
| Configuración de la aplicación | Para integrar tu aplicación Samsung CTV con AppsFlyer:<ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Crea una cuenta de AppsFlyer.</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/user-management">Añadir usuarios de cuenta con los permisos adecuados</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/adding-an-app-to-appsflyer">Agrega tu aplicación Samsung CTV en AppsFlyer</Anchor></li></ul> | marketer |
| Integración API con tu aplicación (a través de S2S o SDK) | Hay dos métodos de integración que puedes usar: server-to-server (S2S) y SDK.<br /><br />Para el método S2S, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/pc-console-ctv-api-overview">integra la API de AppsFlyer</Anchor> en tu aplicación con comandos para reportar los siguientes eventos a AppsFlyer.<ul><li>Primero abre</li><li>Eventos dentro de la app</li><li>Sesiones</li></ul>**<span id="h_01M349521V96NRS5CJKXZKMA6P"></span>Nota:**<ul><li>Reporta las instalaciones antes que los eventos in-app y las sesiones.</li><li>Envía eventos usando la API. Indica a tu desarrollador qué eventos debe enviar y verifica que configuras y asignas los eventos que vas a enviar a AppsFlyer.</li></ul><br /><br />Para reportar interacciones con Medios propios, integra la <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">API de engagement de impresiones</Anchor>.<br /><br />Para el método del SDK, consulta el centro para desarrolladores para ver la <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-html5-ctv-sdk">documentación de Samsung</Anchor>. | Desarrolladores de aplicaciones |
| Integración de partners | Agrega Samsung como red publicitaria (partner integrado) en AppsFlyer.<ol><li><Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#a-activate-partner">Activar partner</Anchor></li><li>[Opcional] Activa la <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#e-install-attribution">**atribución view-through**</Anchor>.</li></ol> | Comercializador |
| Configuración de OneLink | <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-direct-attribution-links">Aprende a crear enlaces de atribución directa</Anchor> | Comercializador |
| Configuración de reportes/ver datos | <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-attribution-concepts#disponibilidad-de-datos">Aprender más sobre la disponibilidad de datos en paneles de control y reportes</Anchor> | Marketer/Ingeniero de datos |

<div id="traits-and-limitations" />

## Rasgos y limitaciones

| Caducado | Observaciones |
| --- | --- |
| Reorientación | Actualmente no es compatible |
| Datos de costo | Importa datos de costo a través de <Anchor target="_blank" href="/marketers/es/docs/import-cost-data">Cost Import</Anchor> utilizando el método de carga de archivos **por correo electrónico**. También puedes extraer datos **a través de la API** de Google, Meta o TikTok. |
| Regiones compatibles | El soporte para CTV y las campañas de precarga varía según la región, de la siguiente manera.<ul><li>AppsFlyer admite campañas de Connected TV (CTV) solo en EE. UU., lo que incluye compartir postbacks con Samsung a través de la integración de la plataforma DSP (Demand-side platform) de Samsung (`samsungdsp_int`).</li><li>En la región de EMEA (Europa, Oriente Medio y África), AppsFlyer admite campañas de CTV sin compartir postbacks con Samsung a través de la integración DSP de Samsung para EMEA (`samsungemea_int`).</li><li>Otras regiones no admiten campañas de CTV.</li><li>AppsFlyer admite campañas de precarga a nivel global.</li></ul> |

<div data-zendesk-anchors="about-samsung-ctv-attribution=acerca-de-la-atribuci%C3%B3n-de-ctv-de-samsung 01H7Z17A1QPJQH9R5MRBVTMG37=acerca-de-la-atribuci%C3%B3n-de-ctv-de-samsung samsung-attribution-flow=flujo-de-atribuci%C3%B3n-de-samsung 01H7Z17A1Q03CEJT848FRFHDPQ=flujo-de-atribuci%C3%B3n-de-samsung integration-procedures=procedimientos-de-integraci%C3%B3n 01H7Z17A1QQN4FYJXZFS5FP2NY=procedimientos-de-integraci%C3%B3n traits-and-limitations=rasgos-y-limitaciones 01H7Z17A1QVW58B2FZE7SDJHHJ=rasgos-y-limitaciones" />
