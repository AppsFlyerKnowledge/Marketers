---
title: Integración de Vidaa con AppsFlyer
metadata:
  keywords:
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
  created_at: '2022-11-06T08:13:09Z'
  edited_at: '2026-08-12T12:10:25Z'
  id: 10400222972433
  locale: es
  section: Promoting CTV apps
  section_id: 15328952633489
  url: https://support.appsflyer.com/hc/es/articles/10400222972433
---
> **En resumen:** Integra tu aplicación Vidaa Connected TV (CTV) con AppsFlyer para recibir datos de atribución y eventos para tus campañas en Vidaa.

## Sobre la atribución CTV de Vidaa

El sistema operativo Vidaa para streaming funciona en todos los televisores Vidaa.

Las aplicaciones de CTV que se transmiten en Vidaa pueden integrarse con AppsFlyer a través de la API para recibir datos de atribución y mediciones de rendimiento sobre qué fuentes (orgánicas) y campañas impulsan la apertura de la aplicación y los eventos in-app. Los marketers confían en estos insights para medir y optimizar las actividades de marketing.

La integración con la API de Vidaa es compatible:

* Smart TV Vidaa.
* Atribución CTV-to-CTV y grabación de eventos. Significado, atribución y grabación en el dispositivo Vidaa de un usuario.

## Procedimientos de integración

La siguiente tabla enumera las tareas necesarias para integrar tu aplicación Vidaa CTV con AppsFlyer. Para registrar tus progresos, descarga esta <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vSFsuk9liZ_z34w3kHMyOFzASh5PBDtdn_HxgMqxAYY0wEt5RxCdrXeyLvteC5Cp-x-6ESwO5YbJ0n-/pub?output=xlsx">hoja de cálculo</Anchor>.

| Tarea | Acciones | Quién debe participar |
| --- | --- | --- |
| Configuración de la aplicación | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Crear una cuenta AppsFlyer</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/user-management">Añadir usuarios de cuenta con los permisos adecuados</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/adding-an-app-to-appsflyer">Añade tu aplicación Vidaa CTV en AppsFlyer</Anchor></li></ul> | Comercializador |
| Integración API con tu aplicación (a través de S2S) | <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">Integra la API CTV de AppsFlyer</Anchor> en tu aplicación CTV con comandos para reportar los siguientes eventos a AppsFlyer.<ul><li>Primera apertura</li><li>Eventos in-app</li><li>Sesiones</li></ul>**Nota**:<ul><li>Las instalaciones deben notificarse antes que las sesiones y los eventos in-app.</li><li>Enviar eventos utilizando la API. Indica a tu desarrollador qué eventos debe enviar. Verifica que cuando configures la API, configures y mapees los eventos a enviar a AppsFlyer.</li><li>Para el`device_ids` parámetro, selecciona el tipo `custom`.</li></ul>Para informar sobre el engagement en medios propios, integra la <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">API de engagement en impresiones.</Anchor> | Desarrolladores de aplicaciones |
| Configuración de enlaces | <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-direct-attribution-links">Aprende a crear enlaces de atribución directa</Anchor> | Comercializador |
| Configuración de reportes/visualización de datos | <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-attribution-concepts#disponibilidad-de-datos">Conoce la disponibilidad de datos en dashboards y reportes</Anchor> | Marketer/Ingeniero de datos |

<div id="traits-and-limitations" />

<Accordion title="Rasgos y limitaciones">

| Caducado | Observaciones |
| --- | --- |
| Fuentes no orgánicas | En breve |
| Reorientación | Actualmente no es compatible |
| Datos de costos | Los datos de costos deben enviarse a través de <Anchor target="_blank" href="/marketers/es/docs/import-cost-data">Importación de costos</Anchor> utilizando el método de upload de archivos por correo electrónico. |

</Accordion>

> 📄 **Consulta también**
>
> * <span id="overview"></span><Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-attribution-concepts">Resumen general de la plataforma de CTV, PC y consola</Anchor>

<div data-zendesk-anchors="about-vidaa-ctv-attribution=sobre-la-atribuci%C3%B3n-ctv-de-vidaa 01H7Z180QRR77E1GBQ0P0RHVN5=sobre-la-atribuci%C3%B3n-ctv-de-vidaa integration-procedures=procedimientos-de-integraci%C3%B3n 01H7Z180QR6HT4R3N9DYSM8WB9=procedimientos-de-integraci%C3%B3n 01H7Z180QR0QQ0HK3N5N1G4ENZ=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=consulta-tambi%C3%A9n" />
