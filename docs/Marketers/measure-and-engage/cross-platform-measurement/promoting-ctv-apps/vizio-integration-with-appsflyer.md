---
title: Integración de Vizio con AppsFlyer
metadata:
  keywords:
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
  created_at: '2022-03-27T15:48:04Z'
  edited_at: '2026-08-12T12:10:28Z'
  id: 5045234293777
  locale: es
  section: Promoting CTV apps
  section_id: 15328952633489
  url: https://support.appsflyer.com/hc/es/articles/5045234293777
---
> **En resumen:** Integra tu aplicación Vizio Connected TV (CTV) con AppsFlyer para recibir datos de atribución y eventos para tus campañas en Vizio.

<div id="about-vizio-ctv-attribution" />

## Sobre la atribución CTV de Vizio

El sistema operativo Vizio SmartCast para streaming se ejecuta en todas las TVs Vizio.

Las aplicaciones CTV que se transmiten en Vizio se pueden integrar con AppsFlyer a través de la API para recibir datos de atribución y mediciones de rendimiento sobre qué fuentes (orgánicas u no orgánicas) y campañas pagas impulsan la apertura de la aplicación y eventos in-app. Los marketers confían en estos insights para medir y optimizar las actividades de marketing.

La integración de Vizio API admite:

* Smart TVs de Vizio.
* Atribución CTV-to-CTV y grabación de eventos. Significado, atribución y registro de las aperturas de la primera aplicación de Vizio (el equivalente a instalaciones) y eventos que ocurren en el dispositivo Vizio de un usuario.

<div id="vizio-attribution-flow" />

### Flujo de atribución de Vizio

<Image align="center" alt="CTV_attribution_flow_-_Vizio__1_.png" src="https://files.readme.io/f4ab4b6c9e045fe00b537814fa9f10746b525a5512e5805e62eb0c2e4c9a8615-6318406872337.png" />

<div id="integration-procedures" />

## Procedimientos de integración

La siguiente tabla enumera las tareas necesarias para integrar tu aplicación Vizio CTV con AppsFlyer.

| Tarea | Acciones | ¿Quién está involucrado? |
| --- | --- | --- |
| Configuración de la aplicación | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Crea una cuenta de AppsFlyer</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/user-management">Agrega usuarios a la cuenta con los permisos adecuados</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/adding-an-app-to-appsflyer">Agrega tu aplicación Vizio CTV en AppsFlyer</Anchor></li></ul> | Comercializador |
| Integración de la API con tu aplicación (a través de S2S) | <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">Integra la API de AppsFlyer CTV</Anchor> en tu aplicación CTV con comandos para reportar los siguientes eventos a AppsFlyer.<ul><li>Primeras aperturas</li><li>Eventos in-app</li><li>Sesiones</li></ul>**Nota**:<ul><li>Las instalaciones deben reportarse antes de las sesiones y eventos in-app.</li><li>Envía eventos usando la API. Dile a tu desarrollador qué eventos enviar. Verifica que cuando configuras la API, configuras y asignas los eventos para enviar a AppsFlyer.</li></ul>Para informar sobre interacciones con medios propios, integra la <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">API de interacción con impresiones.</Anchor> | Desarrolladores de aplicaciones |
| Integración de partners | Agrega Vizio como red publicitaria (partner integrado) en AppsFlyer:<ol><li><Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#a-activate-partner">Activar partner</Anchor></li><li>[Opcional] Activa la **<Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#e-install-attribution">atribución view-through</Anchor>.**</li></ol> | Comercializador |
| Configuración del enlace | <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-direct-attribution-links">Aprende a crear enlaces de atribución directa</Anchor> | Comercializador |
| Configuración/visualización de datos de reportes | <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-attribution-concepts#disponibilidad-de-datos">Obtén más información sobre la disponibilidad de datos en dashboard y reportes</Anchor> | Marketer/Ingeniero de datos |

<div id="traits-and-limitations" />

<Accordion title="Rasgos y limitaciones">

| Caducado | Observaciones |
| --- | --- |
| Reorientación | Actualmente no es compatible |
| Atribución por view-through | El valor predeterminado es de 24 horas |
| Datos de costos | Los datos de costos deben enviarse a través de <Anchor target="_blank" href="/marketers/es/docs/import-cost-data">Importación de costos</Anchor> utilizando el método de upload del archivo por correo electrónico. |

</Accordion>

<div id="see-also" />

> 📄 **Consulta también**
>
> * <span id="overview"></span><Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-attribution-concepts">Resumen general de la plataforma de CTV, PC y consola</Anchor>

<div data-zendesk-anchors="about-vizio-ctv-attribution=sobre-la-atribuci%C3%B3n-ctv-de-vizio 01H7Z16QWWCPR309JDKV7H0469=sobre-la-atribuci%C3%B3n-ctv-de-vizio vizio-attribution-flow=flujo-de-atribuci%C3%B3n-de-vizio 01H7Z16QWW3GJEAGV0F3JHTKE1=flujo-de-atribuci%C3%B3n-de-vizio integration-procedures=procedimientos-de-integraci%C3%B3n 01H7Z16QWW1WX5F947WPH9HBQX=procedimientos-de-integraci%C3%B3n 01H7Z16QWX24K8QCEJVBX1SQEA=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=consulta-tambi%C3%A9n" />
