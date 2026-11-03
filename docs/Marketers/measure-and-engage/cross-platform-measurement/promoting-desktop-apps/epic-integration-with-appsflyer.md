---
title: Integración de Epic con AppsFlyer
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
  created_at: '2023-04-03T07:18:07Z'
  edited_at: '2026-08-12T12:10:33Z'
  id: 14241298075921
  locale: es
  section: Promoting Desktop apps
  section_id: 15329004312593
  url: https://support.appsflyer.com/hc/es/articles/14241298075921
---
> **En resumen:** Integra tu juego de Epic con AppsFlyer para recibir datos de atribución y eventos para tus campañas de Epic. La integración de Epic admite la atribución y el registro de eventos in-app para juegos de Epic (es decir, atribución y registro en el dispositivo de un usuario).

## Acerca de la atribución de juegos de Epic

Los juegos que se ejecutan en Epic pueden integrarse con AppsFlyer mediante la API (tanto S2S como del lado del cliente) para recibir datos de atribución y mediciones de rendimiento sobre qué fuentes y campañas impulsan la apertura de la app y los eventos in-app. Los marketers confían en estos conocimientos para medir y optimizar las actividades de marketing.

### Ejemplo de flujo de atribución

El siguiente es un flujo de ejemplo que destaca los pasos más importantes del viaje de un usuario, desde la interacción con el anuncio hasta la atribución. Incluye la landing page multiplataforma recomendada por AppsFlyer. **Nota**: Si bien recomendamos usar la landing page multiplataforma, también puedes usar enlaces de atribución directa.

![Epic_journey.jpg](https://files.readme.io/c5807442cff142ceb4aa3c4d55628e75b37627a011ca531fa390e46ccc3e23b8-small-14241275857553.jpg)

1. Punto de contacto de marketing: Los clientes interactúan con tu marca a través de puntos de contacto de marketing online u offline. Estos pueden incluir el correo electrónico y los boletines informativos, las redes sociales, la web móvil y más.
2. Landing page del juego:  La landing page de un juego dirige a los clientes a tu página del juego de Epic. Este paso es importante para recopilar los parámetros UTM y otros parámetros de URL a fin de atribuir a los clientes que han hecho clic o han hecho la instalación a las fuentes multimedia originales o a las fuentes multimedia de tu propiedad.  
   La landing page también es útil porque proporciona enlaces a las distintas plataformas compatibles con el juego. Por ejemplo, también puedes tener enlaces a tu Xbox, tienda de Microsoft y página de Steam en tu página de inicio.
3. Página de la app de Epic: Esta es la página del escaparate de Epic que aloja tu juego de Epic para que los clientes lo descarguen.
4. Instalación del juego: El usuario instala el juego, lo que activa la atribución y la grabación de eventos in-app y sesiones.

## Procedimientos de integración

La siguiente tabla enumera las tareas necesarias para integrar tu juego de Epic con AppsFlyer.∑

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
        ¿Quién participa?
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Configuración de la aplicación
      </td>
      <td>
        * <Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Crear una cuenta AppsFlyer</Anchor>
        * <Anchor target="_blank" href="/marketers/es/docs/user-management">Añadir usuarios de cuenta con los permisos adecuados</Anchor>
        * <Anchor target="_blank" href="/marketers/es/docs/adding-an-app-to-appsflyer">Agrega tu juego de Epic en AppsFlyer</Anchor>
      </td>
      <td>
        Comercializador
      </td>
    </tr>
    <tr>
      <td>
        Integración de API con tu aplicación (a través de S2S o del lado del cliente)
      </td>
      <td>
        Hay dos métodos de integración que puedes utilizar: S2S y del lado del cliente.

        Para el método S2S:

        <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-epic-sample">Integra la API de Epic de AppsFlyer</Anchor> en tu aplicación con comandos para reportar los siguientes eventos a AppsFlyer.

        * Primeras aperturas
        * Eventos dentro de la aplicación
        * Sesiones

        **Nota**:

        * Las primeras aperturas de aplicaciones deben informarse antes de las sesiones y eventos in-app.
        * Para el parámetro `device_ids`, selecciona el tipo `personalizado` o `epicid`.
          * El `personalizado` o `epicid` para las <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_first-open-app-platform-app-id">primeras aperturas</Anchor> debe coincidir con el ID de tus <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_inapp-app-platform-app-id">eventos in-app</Anchor> y con el ID de las <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_session-app-platform-app-id">sesiones</Anchor> ID.
        * Envía eventos usando la API. Dile a tu desarrollador qué eventos debe enviar.
        * Para informar sobre las interacciones con los medios de comunicación propias, integra la API de <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">interacción con las impresiones</Anchor>.

        Para el método del lado del cliente, hay tres versiones: <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-epic-sample">C++</Anchor> nativo, <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-unreal-epic-sample-app">Unreal</Anchor> y <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-unity-epic-sample-app">Unity</Anchor>.

        **Nota**:

        Si tienes una base de usuarios existente y, por lo tanto, deseas que la primera sesión se considere una sesión y no una instalación, el desarrollador puede utilizar el método `skipFirst=true`.
      </td>
      <td>
        Tu desarrollador de aplicaciones
      </td>
    </tr>
    <tr>
      <td>
        Configuración de la landing page multiplataforma
      </td>
      <td>
        **Recomendado**: La landing page multiplataforma que ejecuta AppsFlyer Smart Script te permite realizar atribución web-to-app. Es más recomendable cuando tu campaña promociona una aplicación que también está disponible en otras plataformas, como Epic y Steam.

        <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">Más información sobre las landing pages multiplataforma</Anchor>

        <Anchor target="_blank" href="/marketers/es/docs/cross-platform-landing-pages-with-smart-script">Más información sobre cómo configurar una landing page multiplataforma</Anchor>

        **Nota**:

        Para Epic, se requieren los siguientes parámetros:

        * **plataforma**  
          epic
        * **app\_id**  
          El ID de la app de la página del juego en la tienda de Epic.

          Puedes encontrar el ID único de tu juego en la consola para desarrolladores de Epic. Por ejemplo:

          ```http
          https://store.epicgames.com/en-us/p/YOUR-GAME-ID
          ```
        * **fuente\_de\_medios**

        Los siguientes parámetros no son obligatorios pero sí recomendados:

        * **campaña única**
        * **anuncio**
        * **ad\_set**
        * **storefront\_redirect\_url**  
          La URL completa de tu escaparate de Epic para tu app, incluida tu **app\_id**.  
          Por ejemplo, `https://store.epicgames.com/en-us/p/12345678/`
      </td>
      <td>
        Marketer (puede requerir la asistencia del desarrollador)
      </td>
    </tr>
    <tr>
      <td>
        Configuración del enlace
      </td>
      <td>
        Si no utilizas una landing page multiplataforma, puedes crear enlaces de atribución directos para colocarlos detrás de los anuncios.

        <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-direct-attribution-links">Aprende a crear enlaces de atribución directa</Anchor>
      </td>
      <td>
        Comercializador
      </td>
    </tr>
    <tr>
      <td>
        Configuración/visualización de datos de reportes
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

### Eliminar los datos de AppsFlyer al desinstalar la app

Para eliminar todos los datos del SDK de AppsFlyer al desinstalar la aplicación, pídele a tu desarrollador que realice los pasos indicados [aquí](https://dev.appsflyer.com/hc/docs/epic-vanilla#deleting-appsflyer-data-on-uninstall).

## Especificaciones y limitaciones

| Caducado | Nota |
| --- | --- |
| Reorientación | Actualmente no es compatible |
| Datos de costo | Los datos de costo deben enviarse a través de <Anchor target="_blank" href="/marketers/es/docs/import-cost-data">Ad Spend Ingestion</Anchor> mediante el método de carga de archivos por correo electrónico. |

> 📄 **Véase también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-attribution-concepts">Resumen general de la plataforma de CTV, PC y consola</Anchor>

<div data-zendesk-anchors="about-steam-attribution=acerca-de-la-atribuci%C3%B3n-de-juegos-de-epic 01H7Z1F3SE03BXJD0WAJV8RE7Q=acerca-de-la-atribuci%C3%B3n-de-juegos-de-epic flow=ejemplo-de-flujo-de-atribuci%C3%B3n 01H7Z1F3SETVXQKRQ71YAJACY3=ejemplo-de-flujo-de-atribuci%C3%B3n integration-procedures=procedimientos-de-integraci%C3%B3n 01H7Z1F3SF4J2WJ2Y6QG3VGGVK=procedimientos-de-integraci%C3%B3n removing-appsflyer-data-when-uninstalling-the-app=eliminar-los-datos-de-appsflyer-al-desinstalar-la-app h_01J3349MAA4J231B6FJ74V3PTB=eliminar-los-datos-de-appsflyer-al-desinstalar-la-app traits-and-limitations=especificaciones-y-limitaciones h_01HF9WA5FJ6P4C357ZE231GMR0=especificaciones-y-limitaciones h_01HE7T4JX3RX3SZW2VPW5ZZY7E=v%C3%A9ase-tambi%C3%A9n" />
