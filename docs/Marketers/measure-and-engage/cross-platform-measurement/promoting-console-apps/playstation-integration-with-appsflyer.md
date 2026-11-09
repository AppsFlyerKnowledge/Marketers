---
title: Integración de PlayStation con AppsFlyer
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
  created_at: '2022-11-03T15:12:14Z'
  edited_at: '2026-09-16T00:20:46Z'
  id: 10342860530961
  locale: es
  section: Promoting Console apps
  section_id: 15329052471057
  url: https://support.appsflyer.com/hc/es/articles/10342860530961
---
> **At a glance:** Descubre cómo integrar tu aplicación de PlayStation con AppsFlyer y cómo medir los anuncios que se ejecutan en PlayStation.

Este artículo abarca dos integraciones relacionadas, pero distintas.

* [Integra tu aplicación de PlayStation con AppsFlyer](#integra-tu-aplicación-de-playstation-con-appsflyer): recibe datos de atribución y de eventos de tu aplicación de PlayStation, independientemente de dónde procedan tus usuarios.
* [Mide los anuncios que se ejecutan en PlayStation](#mide-anuncios-que-se-publican-en-playstation): activa la integración de PlayStation Ads para medir los anuncios que se ejecutan en las consolas PlayStation e impulsar las instalaciones de tu aplicación.

<div id="integrate-your-playstation-app-with-appsflyer" />

## Integra tu aplicación de PlayStation con AppsFlyer

El sistema operativo de PlayStation para las apps de consola y CTV (Connected TV) se ejecuta en todos los dispositivos PlayStation.

Las aplicaciones que se ejecutan en PlayStation pueden integrarse con AppsFlyer a través de la API S2S (server-to-server) para recibir datos de atribución y mediciones de rendimiento sobre qué fuentes y campañas impulsan la apertura de la aplicación y los eventos in-app. Los marketers confían en estos insights para medir y optimizar las actividades de marketing.

La integración de la API de PlayStation admite:

* PlayStations.
* Atribución y registro de eventos para aplicaciones de PlayStation, lo que significa atribución y registro en el dispositivo PlayStation de un usuario.

<div id="example-attribution-flow" />

### Ejemplo de flujo de atribución

El siguiente es un flujo de ejemplo que destaca los pasos más importantes del viaje de un usuario, desde la interacción con el anuncio hasta la atribución. Incluye la página de inicio multiplataforma recomendada por AppsFlyer. **Nota**: Si bien recomendamos usar la landing page multiplataforma, también puedes usar enlaces de atribución directa.

<Image align="center" alt="Diagrama del flujo de atribución desde un punto de contacto de marketing, a través de una landing page multiplataforma, hasta la instalación de una aplicación de PlayStation" src="https://files.readme.io/33c9138ef2064832a0bd5d08d52c84bea3e70efb674af362a8ef0d3e5d505db1-small-16332549715217.jpg" width="3938px" />

1. <span id="marketing-touchpoint"></span>Puntos de contacto de marketing: Los clientes interactúan con tu marca a través de canales online u offline. Estos pueden incluir el correo electrónico y los boletines informativos, las redes sociales, la web móvil y más.
2. Página de inicio del juego: La página de inicio del juego dirige a los clientes a la página de descarga de su aplicación. Este paso es importante para recopilar UTM (Urchin Tracking Module) y otros parámetros de URL a fin de atribuir a los clientes desde el clic o la instalación hasta las fuentes de medios originales o tus medios propios.  
   La landing page también es útil porque proporciona enlaces a las distintas plataformas compatibles con el juego. Por ejemplo, también puedes tener enlaces a tu Xbox, tienda de Microsoft y página de Steam en tu página de destino.
3. Página de la aplicación: Esta es la URL de la página de tu aplicación de PlayStation que aloja tu aplicación para que los clientes la descarguen.
4. Instalación del juego: El usuario instala el juego, lo que activa la atribución y la grabación de eventos y sesiones en la aplicación.

<div id="integration-procedures" />

### Procedimientos de integración

En la siguiente tabla se enumeran las tareas necesarias para integrar tu aplicación PlayStation con AppsFlyer.

| Tarea | Acciones | ¿Quiénes están involucrados? |
| --- | --- | --- |
| Configuración de la aplicación | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Crear una cuenta AppsFlyer</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/user-management">Añadir usuarios de cuenta con los permisos adecuados</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/adding-an-app-to-appsflyer">Añade tu aplicación de PlayStation a AppsFlyer</Anchor></li></ul> | Comercializador |
| Integración API con tu aplicación (a través de S2S) | <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/pc-console-ctv-api-overview">Integra la API de AppsFlyer</Anchor> en tu aplicación con comandos para informar de los siguientes eventos a AppsFlyer.<ul><li>Primeras aperturas</li><li>Eventos dentro de la aplicación</li><li>Sesiones</li></ul>**Nota**:<ul><li>Reporta el evento de primera apertura de la aplicación antes de los eventos in-app y las sesiones.</li><li>Para el `device_ids` parámetro, seleccione el tipo `custom`.<ul><li>El ID generado `personalizado` para las <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_first-open-app-platform-app-id">primeras aperturas</Anchor> debe coincidir con el ID que usas para los <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_inapp-app-platform-app-id">eventos in-app</Anchor> y las <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_session-app-platform-app-id">sesiones</Anchor>.</li></ul></li><li>Envía eventos usando la API. Dile a tu desarrollador qué eventos debe enviar. Cuando configures la API, verifica que has mapeado los eventos que quieres enviar a AppsFlyer.</li><li>El tipo de ID de dispositivo `psid` está pensado para usarse como ID de publicidad. Por el momento, PlayStation no admite la coincidencia de ID de publicidad, por lo que no es necesario usar este tipo de ID de dispositivo.</li><li>Te recomendamos compartir el `psn_uid`, que es el ID de la cuenta de PlayStation, en el campo `customer_user_id`. Asegúrate de anonimizar el valor antes de compartirlo.</li></ul>Para informar sobre engagements con medios propios, integra la <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">API de engagement con impresiones.</Anchor> | Tu desarrollador de aplicaciones |
| Configuración de la landing page multiplataforma | **Recomendado**: La landing page multiplataforma que ejecuta AppsFlyer Smart Script te permite realizar atribución web-to-app. Se recomienda cuando tu campaña promociona una aplicación que también está disponible en otras plataformas, como Epic y Native PC.<br /><br /><Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">Más información sobre las landing pages multiplataforma</Anchor><br /><br /><Anchor target="_blank" href="/marketers/es/docs/cross-platform-landing-pages-with-smart-script">Más información sobre cómo configurar una landing page multiplataforma</Anchor><br /><br />**Nota**:<br /><br />Para PlayStation, se requieren los siguientes parámetros:<ul><li>**plataforma**: playstation</li><li>**app\_id**: El ID de la aplicación</li><li>**fuente\_de\_medios**</li></ul>Los siguientes parámetros no son obligatorios pero sí recomendados:<ul><li>**campaña única**</li><li>**anuncio**</li><li>**ad\_set**</li></ul> | Marketer (puede requerir la asistencia del desarrollador) |
| Configuración del enlace | Si no utilizas una landing page multiplataforma, puedes crear enlaces de atribución directos para colocarlos detrás de los anuncios.<br /><br /><Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-direct-attribution-links">Aprende a crear enlaces de atribución directa</Anchor> | Comercializador |
| Configuración/visualización de datos de reportes | <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-attribution-concepts#disponibilidad-de-datos">Obtén más insights sobre la disponibilidad de datos en dashboards y reportes</Anchor> | Marketer/Ingeniero de datos |

<div id="measure-ads-that-run-on-playstation" />

## Mide anuncios que se publican en PlayStation

AppsFlyer admite la medición de anuncios que se publican en consolas PlayStation y generan instalaciones de tu aplicación de PlayStation. Este flujo es independiente de la integración general de [Procedimientos de integración](#procedimientos-de-integración) anterior. Solo se aplica si PlayStation también es una de tus fuentes de anuncios y está disponible para anunciantes que ya tengan una aplicación de PlayStation activa configurada en AppsFlyer.

Para ejecutar y medir anuncios de PlayStation:

1. **Crea un enlace de atribución.** Sigue las directrices de <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-direct-attribution-links">enlaces de atribución directa para plataformas de CTV, PC y consolas</Anchor> y establece el valor de la plataforma en `playstation`.
2. **Envía el enlace a PlayStation.** Pide a tu equipo de gestión de anuncios de PlayStation que incluya el enlace de atribución en tus anuncios.
3. **Activa la integración de anuncios de PlayStation en AppsFlyer.** Usa el ID de partner `playstation_int`. Para consultar los pasos generales de activación, consulta <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">Configurar un partner integrado</Anchor>.
4. **Consulta los resultados en AppsFlyer.** La performance aparece en tus dashboards y reportes estándar de AppsFlyer, atribuida a la fuente de medios de PlayStation.

<div id="important" />

> 🚧 **Importante**
>
> En esta fase, no puedes compartir señales, como conversiones, eventos o postbacks, con el equipo de anuncios de PlayStation. Los datos de medición permanecen en AppsFlyer y no se envían de vuelta a PlayStation para su optimización.

<div id="sample-attribution-links" />

### Ejemplos de enlaces de atribución

A continuación tienes ejemplos de enlaces de atribución de clics e impresiones para PlayStation.

**Clic**

```
https://engagements.appsflyer.com/v1.0/s2s/click/app/playstation/10000000
?af_media_source=playstation_int
&af_campaign_id={campaign_id}
&af_ip={USER_IP}
&af_campaign={campaign_name}
```

**Impresión**

```
https://engagements.appsflyer.com/v1.0/s2s/impression/app/playstation/10000000
?af_media_source=playstation_int
&af_campaign_id={campaign_id}
&af_ip={USER_IP}
&af_campaign={campaign_name}
```

| Marcador de posición | Tipo | Significado |
| --- | --- | --- |
| 10000000 | Parámetro de ruta | El App ID de la aplicación de PlayStation del anunciante en AppsFlyer. Sustitúyelo por el App ID real, sin prefijo de plataforma. |
| s2s / c2s | Parámetros de ruta | Indica si la solicitud se envía de servidor a servidor (s2s) o de cliente a servidor (c2s). Sustituye el segmento s2s que se muestra en las URL de ejemplo anteriores. El equipo de anuncios de PlayStation decide cuál corresponde. |
| `{campaign_id}` | Parámetro de consulta | ID de campaña, completado por PlayStation. |
| `{campaign_name}` | Parámetro de consulta | Nombre de la campaña, completado por PlayStation. |
| `{USER_IP}` | Parámetro de consulta | Dirección IP del usuario final, completada por PlayStation. |

<div id="traits-and-limitations" />

## Especificaciones y limitaciones

| Caducado | Descripción |
| --- | --- |
| Datos de costo | Envía los datos de costo mediante <Anchor target="_blank" href="/marketers/es/docs/import-cost-data">Ad Spend Ingestion</Anchor>, usando el método de carga de archivos por correo electrónico. |

<div id="see-also" />

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-attribution-concepts">Resumen general de la plataforma de CTV, PC y consola</Anchor>

<div data-zendesk-anchors="integrate-your-playstation-app-with-appsflyer=integra-tu-aplicaci%C3%B3n-de-playstation-con-appsflyer 01H7Z1HPD0AB0VP6REMBF2HCR8=integra-tu-aplicaci%C3%B3n-de-playstation-con-appsflyer example-attribution-flow=ejemplo-de-flujo-de-atribuci%C3%B3n h_01HP1Q8B11P0Q8F2Z2FRDSPNDE=ejemplo-de-flujo-de-atribuci%C3%B3n 01H7Z19FJ54WZ7XV91Y36EKYQ6=marketing-touchpoint 01H7Z1HPD0VAMPEHBPN8MAT3ST=procedimientos-de-integraci%C3%B3n run-and-measure-ads-on-playstation=mide-anuncios-que-se-publican-en-playstation h_01M2FS60HDHKN7GZWFADVMAEKD=mide-anuncios-que-se-publican-en-playstation h_01M2FS60HDVJVBNN2MGCA8CVXG=importante sample-attribution-links=ejemplos-de-enlaces-de-atribuci%C3%B3n h_01M2FS60HDQGDT1KCSGCPJAFJC=ejemplos-de-enlaces-de-atribuci%C3%B3n traits-and-limitations=especificaciones-y-limitaciones 01H7Z1HPD0CS7CTX2KS2RVD3VA=especificaciones-y-limitaciones h_01HE0T79YSNWGB3W4S7WEBW1B5=consulta-tambi%C3%A9n" />
