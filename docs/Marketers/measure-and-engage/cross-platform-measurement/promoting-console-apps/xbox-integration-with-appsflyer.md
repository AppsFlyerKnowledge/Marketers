---
title: Integración de Xbox con AppsFlyer
metadata:
  keywords:
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2023-04-13T08:28:00Z'
  edited_at: '2026-08-12T12:10:09Z'
  id: 14504812967057
  locale: es
  section: Promoting Console apps
  section_id: 15329052471057
  url: https://support.appsflyer.com/hc/es/articles/14504812967057
---
> **En resumen:** Integra tu aplicación Xbox con AppsFlyer para recibir datos de eventos y atribuciones para tus campañas en Xbox.

<div id="about-xbox-attribution" />

## Acerca de la atribución de Xbox

El sistema operativo Xbox para consolas y aplicaciones CTV se ejecuta en todas las Xbox.

Las aplicaciones que se ejecutan en Xbox pueden integrarse con AppsFlyer a través de la API S2S para recibir datos de atribución y mediciones de rendimiento sobre qué fuentes (orgánicas) y campañas impulsan la apertura de la aplicación y eventos in-app. Los marketers confían en estos insights para medir y optimizar las actividades de marketing.

La integración de la API de Xbox admite:

* Xbox.
* Atribución y grabación de eventos para aplicaciones de Xbox. Significado, atribución y grabación en el dispositivo Xbox de un usuario.

<div id="integration-procedures" />

## Procedimientos de integración

La siguiente tabla enumera las tareas necesarias para integrar tu aplicación Xbox con AppsFlyer.

| Tarea | Acciones | ¿Quién está involucrado? |
| --- | --- | --- |
| Configuración de la aplicación | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Crea una cuenta de AppsFlyer</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/user-management">Agrega usuarios a la cuenta con los permisos adecuados</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/adding-an-app-to-appsflyer">Agrega tu aplicación Xbox en AppsFlyer</Anchor></li></ul> | Comercializador |
| Integración de la API con tu aplicación (a través de S2S) | <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">Integra la API de AppsFlyer</Anchor> en tu aplicación con comandos para reportar los siguientes eventos a AppsFlyer.<ul><li>Primera apertura</li><li>Eventos in-app</li><li>Sesiones</li></ul>**Nota**:<ul><li>Las primeras aperturas de aplicaciones deben informarse antes de las sesiones y eventos in-app.</li><li>Para el `device_ids` parámetro, selecciona el tipo `custom`.</li><li>Envía eventos usando la API. Díle a tu desarrollador qué eventos enviar. Verifica que cuando configuras la API, configuras y asignas los eventos para enviar a AppsFlyer.</li></ul>Para reportar sobre interacciones con medios propios, integra la <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">API de interacción con impresiones.</Anchor> | Desarrolladores de aplicaciones |
| Configuración de reportes | <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-attribution-concepts#disponibilidad-de-datos">Obtén más insights sobre la disponibilidad de datos en dashboards y reportes</Anchor> | Marketer/Ingeniero de datos |

<div id="traits-and-limitations" />

<Accordion title="Rasgos y limitaciones">

| Caducado | Observaciones |
| --- | --- |
| Reorientación | Actualmente no es compatible |
| Datos de costos | Los datos de costos deben enviarse a través de <Anchor target="_blank" href="/marketers/es/docs/import-cost-data">Importación de costos</Anchor> utilizando el método de upload del archivo por correo electrónico. |

</Accordion>

<div id="see-also" />

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-attribution-concepts">Resumen general de la plataforma de CTV, PC y consola</Anchor>

<div data-zendesk-anchors="about-playstation-attribution=acerca-de-la-atribuci%C3%B3n-de-xbox 01H7Z1NEAJMRWKHS4K168V0753=acerca-de-la-atribuci%C3%B3n-de-xbox integration-procedures=procedimientos-de-integraci%C3%B3n 01H7Z1NEAJJY4ZRVKY74ACXAAR=procedimientos-de-integraci%C3%B3n 01H7Z1NEAJRA11P7NG05KRKR8Q=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=consulta-tambi%C3%A9n" />
