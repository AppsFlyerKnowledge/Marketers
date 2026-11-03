---
title: Integración de Amazon Vega OS con AppsFlyer
metadata:
  keywords:
    - Marketers
    - CTV Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - CTV Attribution
  created_at: '2026-01-19T07:36:38Z'
  edited_at: '2026-08-12T12:10:12Z'
  id: 42971481283601
  locale: es
  section: Promoting CTV apps
  section_id: 15328952633489
  url: https://support.appsflyer.com/hc/es/articles/42971481283601
---
> **En resumen:** Integra tu aplicación Amazon Vega OS Connected TV (CTV) con AppsFlyer para recibir datos de atribución y eventos para tus campañas en Amazon Vega OS.

## **Sobre la atribución CTV de Amazon Vega OS**

El sistema operativo Amazon Vega OS para streaming funciona en todos los dispositivos Amazon Vega OS.

Las aplicaciones de CTV en streaming en Amazon Vega OS pueden integrarse con AppsFlyer a través de la API para recibir datos de atribución y mediciones de performance sobre qué fuentes (orgánicas) y campañas impulsan la apertura de la aplicación y los eventos in-app. Los marketers confían en estos insights para medir y optimizar las actividades de marketing.

La integración de la API de Amazon Vega OS es compatible con:

* Smart TVs de Amazon Vega OS.
* Atribución CTV-to-CTV y registro de eventos. Es decir, atribución y registro en el dispositivo Amazon Vega OS de un usuario.

## **Procedimientos de integración**

La siguiente tabla enumera las tareas necesarias para integrar tu aplicación Amazon Vega OS CTV con AppsFlyer. Para registrar tus progresos, descarga esta [hoja de cálculo](https://docs.google.com/spreadsheets/d/e/2PACX-1vSFsuk9liZ_z34w3kHMyOFzASh5PBDtdn_HxgMqxAYY0wEt5RxCdrXeyLvteC5Cp-x-6ESwO5YbJ0n-/pub?output=xlsx).

| **Tarea** | **Acciones** | **¿Quién participa?** |
| --- | --- | --- |
| Configuración de la aplicación | <ul><li>[Crear una cuenta AppsFlyer](https://www.appsflyer.com/get-started/)</li><li><Anchor target="_blank" href="/marketers/es/docs/user-management">Añadir usuarios de cuenta con los permisos adecuados</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/adding-an-app-to-appsflyer">Añade tu aplicación Amazon Vega OS CTV en AppsFlyer</Anchor> usando la <Anchor target="_blank" href="/marketers/es/docs/adding-an-app-to-appsflyer#amazon-vega-os">estructura de ID de aplicación de Amazon Vega</Anchor>.</li></ul> | Comercializador |
| Integración API con tu aplicación (a través de S2S) | [Integra la API de AppsFlyer CTV](https://dev.appsflyer.com/hc/reference/overview-4) en tu aplicación CTV con comandos para reportar los siguientes eventos a AppsFlyer.<ul><li>Primeras aperturas</li><li>Eventos dentro de la aplicación</li><li>Sesiones</li></ul>**Nota**<ul><li>Las instalaciones deben notificarse antes que las sesiones y los eventos in-app.</li><li>Envía eventos usando la API. Dile a tu desarrollador qué eventos debe enviar. Verifica que cuando configuras la API, configuras y asignas los eventos para enviar a AppsFlyer.</li><li>Para el parámetro `device_ids` , selecciona el tipo `vegaid`.</li><li>Para reportar engagement de medios propios, integra la [API de engagement de impresiones.](https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id)</li></ul> | Tu desarrollador de aplicaciones |
| Configuración del enlace | <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-direct-attribution-links">Aprende a crear enlaces de atribución directa</Anchor> | Comercializador |
| Configuración/visualización de datos de reportes | <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-attribution-concepts#disponibilidad-de-datos">Obtén más insights sobre la disponibilidad de datos en dashboards y reportes</Anchor> | Marketer/Ingeniero de datos |

## Especificaciones y limitaciones

| Caducado | Nota |
| --- | --- |
| Fuentes no orgánicas | En breve |
| Reorientación | Actualmente no es compatible |
| Datos de costo | <Anchor target="_blank" href="/marketers/es/docs/import-cost-data">Los datos de costos deben enviarse a través deImportaci</Anchor>ón de costosutilizando el método de upload del archivo por correo electrónico. |

### **Véase también**

* <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-attribution-concepts">Resumen general de la plataforma de CTV, PC y consola</Anchor>

<div data-zendesk-anchors="about-amazon-vega-os-ctv-attribution=sobre-la-atribuci%C3%B3n-ctv-de-amazon-vega-os h_01KFAJYYX01B4E6CDMCH6REGY9=sobre-la-atribuci%C3%B3n-ctv-de-amazon-vega-os integration-procedures=procedimientos-de-integraci%C3%B3n h_01KFAJYYX0WZY682B0SSWJM40V=procedimientos-de-integraci%C3%B3n traits-and-limitations=especificaciones-y-limitaciones h_01KFAJYYX0E95XEYQCQPCTN700=especificaciones-y-limitaciones see-also=v%C3%A9ase-tambi%C3%A9n h_01KFAJYYX00K3RKMYB9QX6KXKN=v%C3%A9ase-tambi%C3%A9n" />
