---
title: Descubre los parámetros y el comportamiento de los enlaces de tu campaña
metadata:
  keywords:
    - Marketers
    - discover
    - Social-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Social-to-App
  created_at: '2023-07-03T11:56:14Z'
  edited_at: '2026-08-12T12:24:04Z'
  id: 16678138044689
  locale: es
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/es/articles/16678138044689
---
> **En resumen:** Consulta qué parámetros se incluyen en un enlace determinado y comprende la experiencia de usuario esperada y el comportamiento del enlace.

<div id="about-link-discovery" />

## Uso de Link Discovery

La función de Link Discovery proporciona información sobre los enlaces de tu campaña de AppsFlyer, incluidos los parámetros de enlace y la experiencia de usuario esperada que los enlaces pretenden crear.

<div id="benefits" />

### Ventajas

El Link Discovery ayuda a los anunciantes a:

* Obtener una comprensión más profunda del significado y el comportamiento de los enlaces.
* Comunicarse con sus equipos responsables de la creación de enlaces.
* Confirmar los detalles del enlace antes de publicar el enlace en una campaña.
* Solucionar problemas de comportamientos inesperados.
* Consultar los parámetros de atribución para saber qué buscar en los dashboards.

<div id="information-available-via-link-discovery" />

### Información disponible a través del Link Discovery

El Link Discovery muestra la siguiente información sobre una URL:

* **Información general**: Información sobre para qué aplicaciones es el enlace, fuente de creación (por ejemplo, página de administración de OneLink o API), la plantilla de OneLink en la que se basa el enlace y la fecha de vencimiento y el período de renovación del enlace.   
  **Nota:** Si la fuente de creación es «Unknown», es probable que sea porque se trata de un enlace heredado creado a través de la IU (gestión de OneLink) o de un enlace más antiguo creado de otras formas (Bulk/API/SDK) antes de que se empezara a almacenar el llamador de la fuente.
* **Parámetros**: Todos los diferentes parámetros incluidos en el enlace y sus valores, mostrados por categoría.   
  **Nota:** Si hay redireccionamiento a un dominio que no está en tu <Anchor target="_blank" href="/marketers/es/docs/set-up-your-domain-redirect-allowlist">lista de redireccionamientos permitidos</Anchor>, debería aparecer una alerta.
* **Capacidades**: Las diferentes capacidades habilitadas para el enlace. Por ejemplo: retargeting, deep linking, vista previa de redes sociales y landing page de redes sociales.
* **Redireccionamiento**: Un resumen de cómo está diseñado el enlace para redireccionar a los usuarios en función de su dispositivo, plataforma y si ya tienen instalada la aplicación.

<div id="using-link-discovery" />

## Uso del Link Discovery

**Para usar Link Discovery y obtener información sobre una URL**:

1. En AppsFlyer, desde el menú lateral, elige **Engage** > **Link Discovery**.
2. Ingresa tu URL y haz clic en **Descubrir.**

<div id="specifications-and-limitations" />

## Especificaciones y limitaciones

| Especificación | Observaciones |
| --- | --- |
| Enlaces compatibles con Link Discovery | <ul><li>URLs cortas o largas creadas a través de AppsFlyer, ya sean enlaces de plataforma única o enlaces multiplataforma creados a través de OneLink.</li><li>Enlaces creados en la interfaz de usuario de AppsFlyer y mediante API, SDK y creación en masa.</li><li>Enlaces con dominios de marca.</li></ul> |
| Agencias | No compatible |
| Redes publicitarias | No compatible |
| URLs de impresiones | No compatible |
| Enlaces multiplataforma | No compatible |

<div data-zendesk-anchors="what-is-app-attribution=uso-de-link-discovery h_01HKW0CMGXXFKEY7W0NCN1SH76=uso-de-link-discovery benefits=ventajas h_01HKW0CMGXEAYPDFMR4QCS9F52=ventajas information-available-via-link-discovery=informaci%C3%B3n-disponible-a-trav%C3%A9s-del-link-discovery h_01HKW0CMGXHZ2NYP6YVPW6QNX3=informaci%C3%B3n-disponible-a-trav%C3%A9s-del-link-discovery using-link-discovery=uso-del-link-discovery h_01HKW0CMGXD4Z0J7CCKJFZNVCG=uso-del-link-discovery specifications-and-limitations=especificaciones-y-limitaciones h_01HKW0CMGXX4VXBHFGG3TGGPRV=especificaciones-y-limitaciones" />
