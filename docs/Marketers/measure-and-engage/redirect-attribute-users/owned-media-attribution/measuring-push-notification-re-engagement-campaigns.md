---
title: Medición de campañas de notificaciones push para el re-engagement
metadata:
  keywords:
    - Re-Engagement
    - push
    - notifications
    - Advertisers
    - Developers
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2016-01-18T10:03:11Z'
  edited_at: '2026-11-02T01:17:04Z'
  id: 207364076
  locale: es
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/es/articles/207364076
---
> **At a glance:** Mide las campañas de notificaciones push tanto en iOS como en Android.

<div id="overview" />

## Visión general

AppsFlyer admite la medición de las campañas de notificaciones push de todos los proveedores push, así como las campañas implementadas directamente sobre Firebase Cloud Messaging o Apple Push Notification Services (APNS).

Hay dos formas posibles de realizar la integración:

* Utilizando las plantillas de OneLink (recomendado).
* Enviando un objeto JSON con una clave `af` en el payload de la notificación push.

Las conversiones se muestran en el panel de control general, en las vistas de retargeting o unificadas.

<div id="how-does-it-work" />

## ¿Cómo Funciona?

Una vez que hayas completado los pasos de este artículo, tu aplicación funcionará de la siguiente manera:

1. Activas una notificación push que contiene una plantilla de OneLink **o** una clave `af` en tu carga útil.
2. El usuario de la aplicación recibe la notificación push y hace clic en ella.
3. La aplicación se carga y el SDK de AppsFlyer se inicia.
4. El SDK procesa la carga útil de la notificación push que abrió la aplicación.
5. El SDK extrae y envía los datos de atribución a AppsFlyer.

En el escenario de OneLink, si el OneLink está configurado para dirigir al usuario a una ubicación específica en la aplicación, se activa el flujo de enlace profundo.

<div id="prerequisites" />

## Requisitos previos

Antes de continuar, asegúrate de que tu aplicación tenga <Anchor target="_blank" href="/marketers/es/docs/basic-sdk-integration-guide">integrado el SDK de AppsFlyer</Anchor> **y** pueda recibir notificaciones push.

<div id="steps" />

## Pasos

Para configurar la medición de las notificaciones push, hay que completar los siguientes pasos:

1. [Crea una notificación push](/docs/measuring-push-notification-re-engagement-campaigns#1-creating-the-push-notification) que contenga una clave de datos personalizada con la plantilla de OneLink **o** una clave `af` con un objeto JSON como valor.
2. [Configura el SDK para resolver la clave personalizada](/docs/measuring-push-notification-re-engagement-campaigns#2-configuring-the-sdk) (realizado por el desarrollador de la aplicación).
3. [Prueba la integración](/docs/measuring-push-notification-re-engagement-campaigns#3-testing-the-integration) activando una notificación push.
4. [Consulta el rendimiento de las campañas de notificaciones push](/docs/measuring-push-notification-re-engagement-campaigns#4-viewing-push-notification-campaigns-in-the-dashboard) en el panel de control.

<Accordion title="1. Creación de la notificación push">

En primer lugar, crea una notificación push que contenga datos de atribución utilizando uno de los siguientes métodos.

> 📘 **Note**
>
> **Nota:**
>
> En la siguiente demostración, estamos usando Firebase como proveedor de push. Las instrucciones deberían ser aplicables a cualquier proveedor de push, con pequeñas diferencias (si las hubiera). Consulta la documentación del respectivo proveedor de push.

<Tabs>
<Tab title="Usando OneLink (recomendado)">

<div id="using-onelink-recommended" />

#### **Usando OneLink (recomendado)**

Este es el método recomendado para integrar AppsFlyer con notificaciones push.

1. Crea un <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">enlace de OneLink y configúralo para el retargeting.</Anchor>  
    **Nota**: Las URL cortas y largas de OneLink son compatibles.
2. En los datos personalizados de la notificación push, añade el OneLink que contiene los datos de atribución que quieres enviar a AppsFlyer.

> 📘 **Note**
>
> **Ejemplo de Firebase**
>
> En Firebase:
>
>  ![appsflyer-push-custom-data-firebase.png](https://files.readme.io/b2a753e8ec88ef0d0e0a71fe222a8ecc4f03786297696d150f185720b8f4e248-49839256715025.png)

</Tab>

<Tab title="Uso de JSON">

<div id="using-json-legacy" />

<div id="using-json" />

#### **Uso de JSON**

> 📘 **Note**
>
> **Nota:**
>
> A continuación se documenta el método basado en JSON para integrar AppsFlyer con notificaciones push, disponible por motivos de compatibilidad con versiones anteriores. Si estás configurando una nueva aplicación, utiliza la [solución recomendada basada en OneLink](/docs/measuring-push-notification-re-engagement-campaigns#usando-onelink-recomendado).

En los datos personalizados de la notificación push, añade una clave personalizada llamada `af` que contenga los datos de atribución que quieres enviar a AppsFlyer en formato JSON. Se requieren los siguientes parámetros de atribución:

* `pid`
* `is_retargeting`
* `C`

> 📘 **Note**
>
> **Ejemplo de Firebase**
>
> En Firebase:
>
>  ![appsflyer-push-custom-data-firebase-json.png](https://files.readme.io/138aa2abb70cdb0b8a2c1a4b4ce0a8b83b2faae58e29f3223d5653a4d575012b-49839256716049.png)

</Tab>
</Tabs>

</Accordion>

<Accordion title="2. Configuración del SDK">

Esta tarea requiere cambios en el código de la aplicación. Sigue las instrucciones para configurar el SDK:

* Al implementar la solución recomendada basada en OneLink:
  1. Permite que el desarrollador de la aplicación sepa cuál es el nombre de la clave personalizada que has agregado a la notificación. En este ejemplo, es `af_push_link`.
  2. Envíales <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/push-notifications#integrating-appsflyer-with-push-notifications-using-onelink-recommended">estas instrucciones</Anchor>.
* Cuando implementes la solución heredada basada en JSON, envía a tus desarrolladores <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/push-notifications#integrating-appsflyer-with-push-notifications-legacy">estas instrucciones</Anchor>.

</Accordion>

<Accordion title="3. Prueba de la integración">

Para probar que la medición de notificaciones push está integrada correctamente, simplemente activa una notificación push en la campaña que configuraste en el Paso 1.

Si todo está configurado correctamente, el SDK:

1. Escuchará las notificaciones push.
2. Procesará los datos de atribución incrustados en la notificación push y los enviará a AppsFlyer.
3. Continuará con el flujo regular de enlaces profundos, si se implementa la medición de notificaciones push con OneLink.

</Accordion>

<Accordion title="4. Visualización de las campañas de notificaciones push en el panel de control">

Puedes ver los datos procedentes de notificaciones push en el <Anchor target="_blank" href="/marketers/es/docs/retargeting-attribution-guide#retargeting-dashboard">Dashboard de retargeting</Anchor>.

**Nota**: AppsFlyer desduplica los datos de las notificaciones push. Es decir, si se reciben cargas útiles idénticas más de una vez, solo se cuenta una.

</Accordion>

<div data-zendesk-anchors="overview=visi%C3%B3n-general h_01J5XFSEG9DR31DP73KTAGQPFW=visi%C3%B3n-general how-does-it-work=c%C3%B3mo-funciona h_01J5XFSEG967HXNT3GFSC2AQYE=c%C3%B3mo-funciona prerequisites=requisitos-previos h_01J5XFSEG91SER3JKB3RKK6B6G=requisitos-previos steps=pasos h_01J5XFSEG9W3RTP62NW7SV4D0F=pasos using-onelink-recommended=usando-onelink-recomendado h_01J5XFSEG9W73JYPHH9VRZSTZ8=usando-onelink-recomendado h_01J5XFSEG9V46T6XSG31J4AVET=using-json-legacy" />
