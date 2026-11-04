---
title: Integración de Steam con AppsFlyer
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
  created_at: '2022-12-08T10:02:09Z'
  edited_at: '2026-10-07T00:11:36Z'
  id: 11241130508433
  locale: es
  section: Promoting Desktop apps
  section_id: 15329004312593
  url: https://support.appsflyer.com/hc/es/articles/11241130508433
---
> **En resumen:** Integra tu juego o aplicación de Steam con AppsFlyer para recibir datos de atribución y eventos para tus campañas de Steam. La integración con Steam admite la atribución y la grabación de eventos in-app para las aplicaciones de Steam en el dispositivo Steam de un usuario.

<div id="about-steam-attribution" />

## Acerca de la atribución en Steam

Steam funciona en dispositivos Windows y Mac, Steam Deck y otros dispositivos Steam OS.

Las aplicaciones que se ejecutan en Steam pueden integrarse con AppsFlyer a través de la API o el SDK de S2S para recibir datos de atribución y mediciones de rendimiento sobre qué fuentes y campañas generan eventos de apertura de aplicaciones y eventos in-app. Los marketers se basan en estos insights para medir y optimizar las actividades de marketing.

<div id="example-attribution-flow" />

### Ejemplo de flujo de atribución

El siguiente es un flujo de ejemplo que destaca los pasos más importantes del viaje de un usuario, desde la interacción con el anuncio hasta la atribución. Incluye la landing page multiplataforma recomendada por AppsFlyer. **Nota**: Si bien recomendamos usar la landing page multiplataforma, también puedes usar enlaces de atribución directa

![Steam_user_journey.jpg](https://files.readme.io/4979821043af1ed3e662b55c84df10a17a863e79084d050c478fa31767ed8eaa-51473918246929.jpg)

1. Punto de contacto de marketing: Los clientes interactúan con tu marca a través de puntos de contacto de marketing online u offline. Estos pueden incluir el correo electrónico y los boletines informativos, las redes sociales, la web móvil y más.
2. Landing page del juego: La landing page de un juego dirige a los clientes a tu página de juego de Steam. Este paso es importante para recopilar los parámetros UTM y otros parámetros de URL a fin de atribuir a los clientes que han hecho clic o han hecho la instalación a las fuentes multimedia originales o a las fuentes multimedia de tu propiedad.  
   La landing page también es útil porque proporciona enlaces a las distintas plataformas compatibles con el juego. Por ejemplo, puedes incluir enlaces de Xbox, Microsoft Store y Steam.  
   ![awesome_game.png](https://files.readme.io/37cabff10a2e0a721b4d2901e7df47f53a7dedff25bdac80b97003b60eaef430-51473918248465.png)
3. <span id="marketing-touchpoint"></span>Página de la aplicación Steam: Esta es la página principal de tu tienda de Steam que aloja tu aplicación Steam para que los clientes la descarguen.
4. Instalación del juego: el usuario instala el juego, lo que activa la atribución y el registro de eventos in-app y sesiones.

<div id="integration-procedures" />

## Procedimientos de integración

En la siguiente tabla se enumeran las tareas necesarias para integrar tu aplicación Steam con AppsFlyer.

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
        * <Anchor target="_blank" href="/marketers/es/docs/adding-an-app-to-appsflyer">Añade tu aplicación de Steam a AppsFlyer</Anchor>
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
        Hay dos métodos de integración que puedes utilizar: S2S y SDK.

        Para el método S2S, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/pc-console-ctv-api-overview">integra la API de AppsFlyer</Anchor> en tu aplicación con comandos para reportar los siguientes eventos a AppsFlyer.

        * Primero abre
        * Eventos dentro de la app
        * Sesiones

        **Nota**:

        * Las primeras aperturas de aplicaciones deben informarse antes de las sesiones y eventos in-app.
        * Para el parámetro `platform`, selecciona `steam`.
        * Para el parámetro `device_ids`, selecciona el tipo `custom` o `steamid`.
          * El `custom` o `steamid` for <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_first-open-app-platform-app-id">primeras aperturas</Anchor> debe coincidir con el ID de tus <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_inapp-app-platform-app-id">eventos in-app</Anchor>, y con el ID de tus <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_session-app-platform-app-id">sesiones</Anchor> ID.
        * Envía eventos usando la API. Dile a tu desarollador qué eventos enviar. Verifica que cuando configuras la API, configuras y asignas los eventos para enviar a AppsFlyer.
        * Para reportar engagements de medios propios, integra la <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">API de engagement de impresiones.</Anchor>

        Para el método SDK, hay tres versiones: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/steam-vanilla">C++</Anchor> nativo, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unreal-steam">Unreal</Anchor>, y <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unity-steam">Unity</Anchor>.

        **Nota**:

        Si tienes una base de usuarios existente y, por lo tanto, deseas que la primera sesión se considere una sesión y no una instalación, el desarrollador puede utilizar el método `skipFirst=true`.
      </td>
      <td>
        Desarrolladores de aplicaciones
      </td>
    </tr>
    <tr>
      <td>
        Configuración de la landing page multiplataforma
      </td>
      <td>
        **Recomendado**: Una landing page multiplataforma que ejecuta AppsFlyer Smart Script te permite realizar atribución web-to-app. Es más recomendable cuando tu campaña promociona una aplicación que también está disponible en otras plataformas, como Epic y Native PC.

        <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">Obtén más información sobre las landing page multiplataforma</Anchor>

        <Anchor target="_blank" href="/marketers/es/docs/cross-platform-landing-pages-with-smart-script">Aprende a configurar una landing page</Anchor>

        **Nota**:

        Para Steam, se requieren los siguientes parámetros:

        * **plataforma**: steam
        * **steam\_app\_id**: El ID de la página de la aplicación.

          Puedes encontrar tu ID de aplicación único copiándolo de la barra de URL o yendo a <Anchor target="_blank" href="https://steamdb.info/">https://steamdb.info/</Anchor> y buscando tu juego. Por ejemplo,

          ```http
          https://store.steampowered.com/app/12345678/
          ```

          donde **12345678** es tu ID de aplicación único.
        * **fuente\_de\_medios**

        Los siguientes parámetros no son obligatorios pero sí recomendados:

        * **campaña única**
        * **anuncio**
        * **ad\_set**
        * **storefront\_redirect\_url**: la URL completa de la tienda de Steam de tu aplicación, incluido tu **steam\_app\_id**. Por ejemplo, `https://store.steampowered.com/app/12345678/`
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
        Si no utilizas una página de destino multiplataforma, puedes crear enlaces de atribución directa para colocarlos detrás de los anuncios.

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

<div id="removing-appsflyer-data-when-uninstalling-the-app" />

### Eliminar los datos de AppsFlyer al desinstalar la app

Para eliminar todos los datos del SDK de AppsFlyer al desinstalar la aplicación, pide a tu desarrollador que siga los pasos especificados [aquí](https://dev.appsflyer.com/hc/docs/steam-vanilla#deleting-appsflyer-data-on-uninstall).

<div id="traits-and-limitations" />

## Características y limitaciones

| Rasgo | Comentarios |
| --- | --- |
| Reorientación | Actualmente no es compatible |
| Datos de costos | Importa datos de costo a través de <Anchor target="_blank" href="/marketers/es/docs/import-cost-data">Importación de costos</Anchor> utilizando el método de carga de archivos **por correo electrónico**. También puedes extraer datos **a través de la API** para Google, Meta o TikTok. |

<div id="see-also" />

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-attribution-concepts">Atribución de plataformas CTV, PC y consolas</Anchor>

<div data-zendesk-anchors="about-steam-attribution=acerca-de-la-atribuci%C3%B3n-en-steam 01H7Z1DJRW1KPJQ4CZ6T85ASRK=acerca-de-la-atribuci%C3%B3n-en-steam flow=ejemplo-de-flujo-de-atribuci%C3%B3n 01H7Z1DJRWHB8TQC15WW4FVSHG=ejemplo-de-flujo-de-atribuci%C3%B3n integration-procedures=procedimientos-de-integraci%C3%B3n 01H7Z1DJRWX54DN2SNS21GPGXB=procedimientos-de-integraci%C3%B3n removing-appsflyer-data-when-uninstalling-the-app=eliminar-los-datos-de-appsflyer-al-desinstalar-la-app h_01J3349MAA4J231B6FJ74V3PTB=eliminar-los-datos-de-appsflyer-al-desinstalar-la-app traits-and-limitations=caracter%C3%ADsticas-y-limitaciones h_01HDEHMH0HF201TH4XDW691STH=caracter%C3%ADsticas-y-limitaciones h_01HDP1K6FDDEED5P2WNESST7GE=consulta-tambi%C3%A9n" />
