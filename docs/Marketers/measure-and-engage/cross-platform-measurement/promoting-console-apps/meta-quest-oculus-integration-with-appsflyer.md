---
title: Integración de Meta Quest (Oculus) con AppsFlyer
metadata:
  keywords:
    - CTV
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2022-12-08T10:10:00Z'
  edited_at: '2026-10-07T00:11:14Z'
  id: 11241398279569
  locale: es
  section: Promoting Console apps
  section_id: 15329052471057
  url: https://support.appsflyer.com/hc/es/articles/11241398279569
---
> **En resumen:** Integra tu aplicación Meta Quest (Oculus) con AppsFlyer para recibir datos de eventos y atribuciones para tus campañas en Meta Quest (Oculus).

## Acerca de la atribución de Meta Quest (Oculus)

El sistema operativo Meta Quest (Oculus) para juegos se ejecuta en todos los dispositivos Meta Quest (Oculus).

Las aplicaciones que se ejecutan en Meta Quest pueden integrarse con AppsFlyer a través de la API o el SDK de S2S para recibir datos de atribución y mediciones de rendimiento sobre qué fuentes y campañas impulsan la apertura de la aplicación y eventos in-app. Los marketers se basan en estos insights para medir y optimizar las actividades de marketing.

## Procedimientos de integración

La siguiente tabla enumera las tareas necesarias para integrar tu aplicación Meta Quest (Oculus) con AppsFlyer.

<Table>
  <thead>
    <tr>
      <th>
        Tarea
      </th>
      <th>
        Acciones
      </th>
      <th>
        ¿Quiénes están involucrados?
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Configuración de la aplicación
      </td>
      <td>
        * <Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Crea una cuenta de AppsFlyer.</Anchor>
        * <Anchor target="_blank" href="/marketers/es/docs/user-management">Añadir usuarios de cuenta con los permisos adecuados</Anchor>
        * <Anchor target="_blank" href="/marketers/es/docs/adding-an-app-to-appsflyer">Agrega tu aplicación Meta Quest (Oculus) en AppsFlyer</Anchor>
      </td>
      <td>
        marketer
      </td>
    </tr>
    <tr>
      <td>
        Integración de SDK con tu aplicación (a través de S2S o SDK)
      </td>
      <td>
        Hay dos métodos de integración que puedes usar: S2S y SDK.

        Para el método S2S, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">integra la API de AppsFlyer</Anchor> en tu aplicación con comandos para reportar los siguientes eventos a AppsFlyer.

        * Primero abre
        * Eventos dentro de la app
        * Sesiones

        **Nota**:

        * Las primeras aperturas de aplicaciones deben informarse antes de las sesiones y eventos in-app.
        * Para el parámetro `device_ids`, selecciona el tipo `personalizado`.
          * El ID `personalizado` generado para las <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_first-open-app-platform-app-id">primeras aperturas</Anchor> debe coincidir con el ID de tus <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_inapp-app-platform-app-id">eventos in-app</Anchor> y con el ID de las <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_session-app-platform-app-id">sesiones</Anchor>.
          * Envía eventos usando la API. Dile a tu desarollador qué eventos enviar. Verifica que cuando configuras la API, configuras y asignas los eventos para enviar a AppsFlyer.
          * Para reportar el engagement de medios propios, integra la <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">API de engagement de impresiones.</Anchor>

        Para el método SDK, existen dos versiones: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/meta-quest2-unity">Unity</Anchor>, y <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/meta-quest2-unreal">Unreal</Anchor>.

        **Nota**:

        Si tienes una base de usuarios existente y, por lo tanto, deseas que la primera sesión se considere una sesión y no una instalación, el desarrollador puede utilizar el método `skipFirst=true`.
      </td>
      <td>
        Desarrolladores de aplicaciones
      </td>
    </tr>
    <tr>
      <td>
        Configuración de la página de destino multiplataforma
      </td>
      <td>
        **Recomendado**: una landing page multiplataforma que ejecuta AppsFlyer Smart Script te permite realizar la atribución web-to-app. Es más recomendable cuando tu campaña promociona una aplicación que también está disponible en otras plataformas, como Epic y Native PC.

        <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">Obtén más información sobre las landing page multiplataforma</Anchor>

        <Anchor target="_blank" href="/marketers/es/docs/cross-platform-landing-pages-with-smart-script">Aprende a configurar una landing page</Anchor>

        **Nota**:

        Para Meta Quest, se requieren los siguientes parámetros:

        * **plataforma**: quest
        * **QUEST\_APP\_ID**: El ID de la aplicación Quest Store.  
          Para Quest 2, este es el número en la URL de la tienda, por ejemplo:

          ```http
          https://www.oculus.com/experiences/quest/XXXXXXXXXXXXXXXX/
          ```

          donde **XXXXXXXXXXXXXXXX** es tu ID único de la aplicación.
        * **fuente\_de\_medios**

        Los siguientes parámetros no son obligatorios pero sí recomendados:

        * **campaña única**
        * **anuncio**
        * **ad\_set**
        * **storefront\_redirect\_url**: La URL completa del escaparate de Oculus para tu aplicación, incluida tu **QUEST\_APP\_ID**. Por ejemplo, `https://www.oculus.com/experiences/quest/XXXXXXXXXXXXXXXX/`
      </td>
      <td>
        Marketer (puede requerir la asistencia del desarrollador)
      </td>
    </tr>
    <tr>
      <td>
        Configuración de enlaces
      </td>
      <td>
        <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-direct-attribution-links">Saber más sobre cómo crear direct attribution links</Anchor>
      </td>
      <td>
        marketer
      </td>
    </tr>
    <tr>
      <td>
        Configuración de reportes/ver datos
      </td>
      <td>
        <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-attribution-concepts#disponibilidad-de-datos">Obtén más insights sobre la disponibilidad de datos en dashboards y reportes</Anchor>
      </td>
      <td>
        Marketer/Ingeniero de datos
      </td>
    </tr>
  </tbody>
</Table>

<div id="traits-and-limitations" />

<Accordion title="Rasgos y limitaciones">

| Rasgo | Comentarios |
| --- | --- |
| Reorientación | Actualmente no es compatible |
| Datos de costos | Importa datos de costo a través de <Anchor target="_blank" href="/marketers/es/docs/import-cost-data">Cost Import</Anchor> usando el método de carga de archivos **por correo electrónico**. También puedes extraer datos **a través de la API** de Google, Meta o TikTok. |

</Accordion>

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-attribution-concepts">Resumen general de la plataforma de CTV, PC y consola</Anchor>

<div data-zendesk-anchors="about-meta-quest-attribution=acerca-de-la-atribuci%C3%B3n-de-meta-quest-oculus 01H7Z1MK9JHA4C5CB7YME4AJMA=acerca-de-la-atribuci%C3%B3n-de-meta-quest-oculus integration-procedures=procedimientos-de-integraci%C3%B3n 01H7Z1MK9JNRKAY9VNH5RTF03F=procedimientos-de-integraci%C3%B3n 01H7Z1MK9KXFY4XVPCDSJPQ26N=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=consulta-tambi%C3%A9n" />
