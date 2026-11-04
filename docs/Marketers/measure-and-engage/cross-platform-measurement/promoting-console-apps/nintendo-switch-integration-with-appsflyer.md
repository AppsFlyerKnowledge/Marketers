---
title: Integración de Nintendo Switch con AppsFlyer
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
  created_at: '2023-05-02T10:50:43Z'
  edited_at: '2026-08-12T12:10:04Z'
  id: 14988397864593
  locale: es
  section: Promoting Console apps
  section_id: 15329052471057
  url: https://support.appsflyer.com/hc/es/articles/14988397864593
---
> **En resumen:** Integra tu juego o aplicación de Nintendo Switch con AppsFlyer para recibir datos de atribución y eventos de tus campañas de Nintendo Switch.

<div id="about-nintendo-switch-attribution" />

## Sobre la atribución de Nintendo Switch

Las aplicaciones que se ejecutan en Nintendo Switch pueden integrarse con AppsFlyer a través de la API de S2S para recibir datos de atribución y mediciones de rendimiento sobre qué fuentes y campañas impulsan la apertura de la aplicación y los eventos in-app. Los marketers confían en estos insights para medir y optimizar las actividades de marketing.

<div id="example-attribution-flow" />

### Ejemplo de flujo de atribución

El siguiente es un flujo de ejemplo que destaca los pasos más importantes en el recorrido del usuario desde el engagement de publicidad hasta la atribución. Incluye la landing page multiplataforma recomendada por AppsFlyer. **Nota**: si bien recomendamos utilizar la página de destino multiplataforma, también puedes utilizar enlaces de atribución directa.

![User_windows.jpg](https://files.readme.io/33c9138ef2064832a0bd5d08d52c84bea3e70efb674af362a8ef0d3e5d505db1-small-16332549715217.jpg)

1. <span id="marketing-touchpoint"></span>Punto de contacto de marketing: Los clientes interactúan con tu marca a través de puntos de contacto de marketing online u offline. Estos pueden incluir correo electrónico y boletines informativos, redes sociales, web móvil y más.
2. Página de inicio del juego: La página de inicio del juego dirige a los clientes a la página de descarga de su aplicación. Este paso es importante para recopilar UTM y otros parámetros de URL para atribuir clientes desde el clic/instalación a las fuentes de medios originales o a tus propias fuentes de medios.  
   La página de inicio también es útil porque proporciona enlaces a las distintas plataformas compatibles con tu juego. Por ejemplo, también puedes tener enlaces a tu Xbox, tienda de Microsoft y página de Steam en tu página de inicio.
3. Página de la aplicación: Esta es la URL de la página de tu aplicación de Nintendo Switch que aloja tu aplicación para que los clientes la descarguen.
4. Instalación del juego: El usuario instala el juego, lo que activa la atribución y la grabación de eventos y sesiones en la aplicación.

<div id="integration-procedures" />

## Procedimientos de integración

La siguiente tabla enumera las tareas necesarias para integrar tu aplicación de Nintendo Switch con AppsFlyer.

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
        ¿Quién está involucrado?
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Configuración de la aplicación
      </td>
      <td>
        * <Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Crea una cuenta de AppsFlyer</Anchor>
        * <Anchor target="_blank" href="/marketers/es/docs/user-management">Agrega usuarios a la cuenta con los permisos adecuados</Anchor>
        * <Anchor target="_blank" href="/marketers/es/docs/adding-an-app-to-appsflyer">Agrega tu aplicación de Nintendo Switch en AppsFlyer</Anchor>
      </td>
      <td>
        Comercializador
      </td>
    </tr>
    <tr>
      <td>
        Integración API con tu aplicación (a través de S2S)
      </td>
      <td>
        <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/pc-console-ctv-api-overview">Integra la API de AppsFlyer</Anchor> en tu aplicación con comandos para reportar los siguientes eventos a AppsFlyer.

        * Primeras aperturas
        * Eventos dentro de la aplicación
        * Sesiones

        **Nota**:

        * Las primeras aperturas de aplicaciones deben informarse antes de las sesiones y eventos in-app.
        * Para el parámetro `device_ids`, selecciona el tipo `custom`.
          * El `custom` ID generado para <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_first-open-app-platform-app-id">las primeras aperturas</Anchor> debe coincidir con los <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_inapp-app-platform-app-id">eventos in-app</Anchor> y el ID de las <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_session-app-platform-app-id">sesiones</Anchor> .
          * Envía eventos usando la API. Dile a tu desarollador qué eventos enviar. Verifica que cuando configuras la API, configuras y asignas los eventos para enviar a AppsFlyer.

        Para informar sobre interacciones con medios propios, integra la <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">API de interacción con impresiones.</Anchor>
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
        **Recomendado**: La landing page multiplataforma que ejecuta AppsFlyer Smart Script te permite realizar atribución web-to-app. Es más recomendable cuando tu campaña promociona una aplicación que también está disponible en otras plataformas, como Epic y Native PC.

        <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">Obtén más información sobre las landing page multiplataforma</Anchor>

        <Anchor target="_blank" href="/marketers/es/docs/cross-platform-landing-pages-with-smart-script">Aprende a configurar una landing page</Anchor>

        **Nota**:

        Para Nintendo Switch, se requieren los siguientes parámetros:

        * **plataforma**  
          switch
        * **nintendo\_app\_id**  
          El ID de la página de la aplicación.  

          Puedes encontrar tu ID de aplicación único copiándolo de la barra de URL o yendo a <Anchor target="_blank" href="https://www.nintendo.com/store/products/octopath-traveler-ii-switch/">https://www.nintendo.com/store/products/</Anchor> y buscando tu juego. Por ejemplo:

          ```http
          https://www.nintendo.com/store/products/app-id-switch/
          ```

          donde **app-id** es tu ID de aplicación único.
        * **fuente\_de\_medios**

        Los siguientes parámetros no son obligatorios pero sí recomendados:

        * **campaña única**
        * **anuncio**
        * **ad\_set**
        * **storefront\_redirect\_url**  
          La URL completa de la tienda de Nintendo Switch de tu aplicación, incluido tu **nintendo\_app\_id**.  
          Por ejemplo:

          ```http
          https://www.nintendo.com/store/products/app-id-switch/
          ```
      </td>
      <td>
        Marketer (puede requerir ayuda del desarrollador)
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
        <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-attribution-concepts#disponibilidad-de-datos">Obtén más información sobre la disponibilidad de datos en dashboard y reportes</Anchor>
      </td>
      <td>
        Marketer/Ingeniero de datos
      </td>
    </tr>
  </tbody>
</Table>

<div id="traits-and-limitations" />

<Accordion title="Especificaciones y limitaciones">

| Caducado | Nota |
| --- | --- |
| Reorientación | Actualmente no es compatible |
| Datos de costos | Los datos de costos deben enviarse a través de <Anchor target="_blank" href="/marketers/es/docs/import-cost-data">Ad Spend Ingestion</Anchor> mediante el método de subir el archivo por correo electrónico. |

</Accordion>

<div id="see-also" />

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-attribution-concepts">Resumen general de la plataforma de CTV, PC y consola</Anchor>

<div data-zendesk-anchors="about-nintendo-switch-attribution=sobre-la-atribuci%C3%B3n-de-nintendo-switch 01H7Z1HPD0AB0VP6REMBF2HCR8=sobre-la-atribuci%C3%B3n-de-nintendo-switch example-attribution-flow=ejemplo-de-flujo-de-atribuci%C3%B3n h_01HP1QDGDAXV0Y7MVJYHW3H4SQ=ejemplo-de-flujo-de-atribuci%C3%B3n 01H7Z19FJ54WZ7XV91Y36EKYQ6=marketing-touchpoint integration-procedures=procedimientos-de-integraci%C3%B3n 01H7Z1HPD0VAMPEHBPN8MAT3ST=procedimientos-de-integraci%C3%B3n 01H7Z1HPD0CS7CTX2KS2RVD3VA=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=consulta-tambi%C3%A9n" />
