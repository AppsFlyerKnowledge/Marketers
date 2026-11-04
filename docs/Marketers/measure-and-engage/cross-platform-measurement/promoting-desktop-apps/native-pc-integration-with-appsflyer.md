---
title: Integración de Native PC con AppsFlyer
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
  created_at: '2023-06-20T05:52:13Z'
  edited_at: '2026-10-07T00:11:34Z'
  id: 16308237781649
  locale: es
  section: Promoting Desktop apps
  section_id: 15329004312593
  url: https://support.appsflyer.com/hc/es/articles/16308237781649
---
> **En resumen:** integra tu juego o aplicación de PC con AppsFlyer para recibir datos de eventos y atribuciones para tus campañas de PC. La integración de Native PC admite la atribución y la grabación de eventos in-app para aplicaciones de PC (en otras palabras, atribución y grabación en la PC de un usuario).

<div id="about-native-pc-attribution" />

## Acerca de la atribución nativa de PC

La PC nativa se ejecuta en dispositivos Windows, mediante la instalación de una extensión de archivo .EXE o .MSI.

Esto es diferente del <Anchor target="_blank" href="/marketers/es/docs/windows-sdk-integration-for-developers">SDK 2.4.1 de AppsFlyer para Windows</Anchor>, que funciona con instalaciones de Microsoft App Store, teléfonos Windows y UWP.

Las aplicaciones que se ejecutan en PC pueden integrarse con AppsFlyer a través de API o SDK de S2S para recibir datos de atribución y mediciones de rendimiento sobre qué fuentes y campañas impulsan la apertura de aplicaciones y los eventos in-app. Los marketers se basan en estos insights para medir y optimizar las actividades de marketing.

<div id="example-attribution-flow" />

### Ejemplo de flujo de atribución

El siguiente es un flujo de ejemplo que destaca los pasos más importantes en el recorrido del usuario desde el engagement de publicidad hasta la atribución. Incluye la página de inicio multiplataforma recomendada por AppsFlyer. **Nota**: Aunque recomendamos usar la landing page multiplataforma, también puedes usar enlaces de atribución directa

![Usuario_windows.jpg](https://files.readme.io/33c9138ef2064832a0bd5d08d52c84bea3e70efb674af362a8ef0d3e5d505db1-small-16332549715217.jpg)

1. <span id="marketing-touchpoint"></span>Punto de contacto de marketing: Los clientes interactúan con tu marca a través de puntos de contacto de marketing online u offline. Estos pueden incluir correo electrónico y boletines informativos, redes sociales, web móvil y más.
2. Landing page del juego: Una landing page del juego dirige a los clientes a la página de descarga de tu aplicación. Este paso es importante para recopilar los parámetros UTM y otros parámetros de URL a fin de atribuir a los clientes que han hecho clic o han hecho la instalación a las fuentes multimedia originales o a las fuentes multimedia de tu propiedad.  
   La página de inicio también es útil porque proporciona enlaces a las distintas plataformas compatibles con tu juego. Por ejemplo, también puedes tener enlaces a tu Xbox, tienda de Microsoft y página de Steam en tu página de inicio.
3. Página de la aplicación: Esta es la URL de la página de tu aplicación Native PC, donde los clientes pueden descargar tu aplicación.
4. Instalación del juego: El usuario instala el juego, lo que activa la atribución y el registro de eventos in-app y sesiones.

<div id="integration-procedures" />

## Procedimientos de integración

La siguiente tabla enumera las tareas necesarias para integrar tu aplicación para PC con AppsFlyer.

**Nota:** No es obligatorio agregar miembros al equipo ni configurar reportes en Data Locker.

| Tarea | Acciones | ¿Quiénes están involucrados? |
| --- | --- | --- |
| Configuración de la aplicación | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Crea una cuenta de AppsFlyer.</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/user-management">Añadir usuarios de cuenta con los permisos adecuados</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/adding-an-app-to-appsflyer">Agrega tu aplicación para PC en AppsFlyer</Anchor></li></ul> | marketer |
| Integración de SDK con tu aplicación (a través de S2S o SDK) | Hay dos métodos de integración que puedes usar: S2S y SDK.<br /><br />Para el método S2S, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">integra la API de AppsFlyer</Anchor> en tu aplicación con comandos para reportar los siguientes eventos a AppsFlyer.<ul><li>Primero abre</li><li>Eventos dentro de la app</li><li>Sesiones</li></ul>**Nota**:<ul><li>Las primeras aperturas de aplicaciones deben informarse antes de las sesiones y eventos in-app.</li><li>Para el parámetro `device_ids`, selecciona el tipo `personalizado`.<ul><li>El ID `personalizado` generado para <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_first-open-app-platform-app-id">las primeras aperturas</Anchor> debe coincidir con el ID de tus <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_inapp-app-platform-app-id">eventos in-app</Anchor> y con el ID de las <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_session-app-platform-app-id">sesiones</Anchor> .</li></ul></li><li>Envía eventos usando la API. Dile a tu desarollador qué eventos enviar. Verifica que cuando configuras la API, configuras y asignas los eventos para enviar a AppsFlyer.</li><li>Para reportar engagement de medios propios, integra la <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">API de engagement con impresiones.</Anchor></li></ul>Para el método SDK, hay tres versiones: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/nativepc-vanilla">C++</Anchor> nativo, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unreal-nativepc">Unreal</Anchor> y <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unity-nativepc">Unity</Anchor>.<br /><br />**Nota**:<br /><br />Si tienes una base de usuarios existente y, por lo tanto, deseas que la primera sesión se considere una sesión y no una instalación, el desarrollador puede utilizar el método `skipFirst=true`. | Desarrolladores de aplicaciones |
| Configuración de la landing page multiplataforma | **Recomendado**: A una landing page multiplataforma que ejecuta AppsFlyer Smart Script te permite realizar atribución web-to-app. Es más recomendable cuando tu campaña promociona una aplicación que también está disponible en otras plataformas, como Epic y Steam.<br /><br /><Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">Aprender más sobre las páginas de aterrizaje multiplataforma</Anchor><br /><br /><Anchor target="_blank" href="/marketers/es/docs/cross-platform-landing-pages-with-smart-script">Aprender más cómo configurar las páginas de aterrizaje multiplataforma</Anchor><br /><br />Para Native PC, se requieren los siguientes parámetros:<ul><li>**Nombre de aplicación**</li><li>**app\_id**<br />AppsFlyer necesita un App ID para usarlo. Las aplicaciones Native PC no tienen reglas de ID de aplicación específicas, por lo que tu desarrollador puede elegir y crear cualquier ID de aplicación que desee para tu aplicación. **Recomendado:** Elige una identificación significativa para ti, pero que sea poco probable que las aplicaciones la utilicen. Por ejemplo,  `app-name-is-the-best`.</li><li>**media\_source**</li><li>**af\_campaign\_id**</li><li>**plataforma**<br />Ejemplo: steam</li></ul>Los siguientes parámetros no son obligatorios pero sí recomendados:<ul><li>**campaña única**</li><li>**anuncio**</li><li>**ad\_set**</li></ul> | Marketer (puede requerir la asistencia del desarrollador) |
| Configuración del enlace de atribución directa | <ul><li>Si no utilizas una página de destino multiplataforma, puedes crear enlaces de atribución directa para colocarlos detrás de los anuncios.</li><li>Si usas una página de destino multiplataforma, te recomendamos que también uses enlaces de atribución directa y los coloques detrás de los botones específicos de cada plataforma en la página de destino.</li><li><Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-direct-attribution-links">Aprende a crear enlaces de atribución directa</Anchor></li></ul> | Comercializador |
| Configuración de reportes/ver datos | <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-attribution-concepts#disponibilidad-de-datos">Aprender más sobre la disponibilidad de datos en paneles de control y reportes</Anchor> | Marketer/Ingeniero de datos |

<div id="removing-appsflyer-data-when-uninstalling-the-app" />

### Eliminar los datos de AppsFlyer al desinstalar la aplicación

Para eliminar todos los datos del SDK de AppsFlyer al desinstalar la aplicación, pide a tus desarrolladores que realicen los pasos especificados [aquí](https://dev.appsflyer.com/hc/docs/nativepc-vanilla#deleting-appsflyer-data-on-uninstall).

<div id="traits-and-limitations" />

## Rasgos y limitaciones

| Caducado | Observaciones |
| --- | --- |
| Reorientación | Actualmente no es compatible |
| Datos de costos | Importa datos de costo a través de <Anchor target="_blank" href="/marketers/es/docs/import-cost-data">Importación de costos</Anchor> usando el método de carga de archivos **por correo electrónico**. También puedes extraer datos **mediante API** para Google, Meta o TikTok. |

<div id="see-also" />

> 📄 **Consulta también**
>
> * <span id="overview"></span><Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-attribution-concepts">Resumen general de la plataforma de CTV, PC y consola</Anchor>

<div data-zendesk-anchors="about-steam-attribution=acerca-de-la-atribuci%C3%B3n-nativa-de-pc 01H7Z19FJ5J1CB4ESE55Z32C1C=acerca-de-la-atribuci%C3%B3n-nativa-de-pc flow=ejemplo-de-flujo-de-atribuci%C3%B3n 01H7Z19FJ5R869054GDRKHTBJ8=ejemplo-de-flujo-de-atribuci%C3%B3n 01H7Z19FJ54WZ7XV91Y36EKYQ6=marketing-touchpoint integration-procedures=procedimientos-de-integraci%C3%B3n 01H7Z19FJ5KKPJ88KAQM49FNVA=procedimientos-de-integraci%C3%B3n removing-appsflyer-data-when-uninstalling-the-app=eliminar-los-datos-de-appsflyer-al-desinstalar-la-aplicaci%C3%B3n h_01J3349MAA4J231B6FJ74V3PTB=eliminar-los-datos-de-appsflyer-al-desinstalar-la-aplicaci%C3%B3n traits-and-limitations=rasgos-y-limitaciones h_01HF9W8YG149TMQE1F57BG0ZS7=rasgos-y-limitaciones h_01HE0T79YSNWGB3W4S7WEBW1B5=consulta-tambi%C3%A9n" />
