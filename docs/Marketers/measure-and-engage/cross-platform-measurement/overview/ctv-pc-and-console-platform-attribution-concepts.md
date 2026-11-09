---
title: Conceptos de atribución de plataformas CTV, PC y consola
metadata:
  keywords:
    - Attribution
    - Advertisers
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
  created_at: '2021-07-15T11:30:45Z'
  edited_at: '2026-10-20T03:44:21Z'
  id: 4404083608849
  locale: es
  section: Overview
  section_id: 15323084579345
  url: https://support.appsflyer.com/hc/es/articles/4404083608849
---
> **At a glance:** Obtén más información sobre cómo funciona la atribución para CTV, PC y consola para permitir que AppsFlyer reciba datos de atribución y eventos para tus campañas en estos dispositivos multiplataforma.

<Image align="center" alt="Diagrama de la solución de atribución multiplataforma de AppsFlyer para CTV, PC y consola" src="https://files.readme.io/7fc57fd80ad86bb173bcf81581b9fe8b4625ed2a044d302a6d72194560019e81-4410336840977.png" width="471px" />

<div id="the-appsflyer-cross-platform-solution" />

## La solución multiplataforma de AppsFlyer

En el panorama digital actual, los profesionales de growth se enfrentan al desafío de llegar a los consumidores a través de múltiples dispositivos y plataformas. Los enfoques de medición tradicionales se quedan cortos a la hora de capturar el alcance completo de los viajes de los usuarios que abarcan las plataformas. La medición multiplataforma es esencial para comprender el impacto de las actividades de marketing y tomar decisiones informadas.

AppsFlyer ofrece una amplia solución multiplataforma que complementa las herramientas convencionales de atribución móvil. Ayuda a los profesionales de crecimiento a medir y atribuir con precisión los esfuerzos de marketing cuando los usuarios interactúan en múltiples plataformas y dispositivos. Esta solución se centra en plataformas CTV, PC y consola.

Los anunciantes pueden promocionar una aplicación en la misma plataforma o en plataformas diferentes a las que se muestra el anuncio. Por ejemplo, un anunciante puede mostrar un anuncio de una aplicación de Steam en la plataforma de Steam. También pueden mostrar un anuncio de una aplicación de Steam en la web de desktop, por ejemplo, a través de Google Ads. <span id="tv-screens"></span>Las campañas de CTV implican específicamente anuncios publicados en pantallas de TV y pantallas similares a TV.

Cualquiera que sea su estrategia de marketing, los anunciantes se integran con AppsFlyer para recibir datos de atribución y mediciones de rendimiento sobre fuentes (orgánicas o no orgánicas) y campañas que impulsan las instalaciones de aplicaciones de plataformas CTV, PC y consola y eventos posteriores a la instalación. Los marketers utilizan estos insights para calcular el lifetime value (LTV) del usuario y medir y optimizar las actividades de marketing. <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model">Saber más sobre la atribución de AppsFlyer</Anchor>

<div id="supported-platforms" />

### Plataformas compatibles

<table><thead><tr><th rowspan="2">Platform</th><th colspan="2">Método de integración de AppsFlyer</th></tr><tr><th>S2S</th><th>SDK</th></tr></thead><tbody><tr><td>Android TV</td><td><span>-</span></td><td><span>✓</span></td></tr><tr><td>tvOS (Apple TV)</td><td><span>-</span></td><td><span>✓</span></td></tr><tr><td>MacOS</td><td><span>-</span></td><td><span>✓</span></td></tr><tr><td>Amazon Fire TV</td><td><span>-</span></td><td><span>✓</span></td></tr><tr><td>Chromecast</td><td><span>-</span></td><td><span>✓</span></td></tr><tr><td>Roku</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Vizio</td><td><span>✓</span></td><td><span>-</span></td></tr><tr><td>Samsung</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>LG</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>PlayStation</td><td><span>✓</span></td><td><span>-</span></td></tr><tr><td>Vidaa</td><td><span>✓</span></td><td><span>-</span></td></tr><tr><td>Steam</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>PC Nativo</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Meta Quest (Oculus)</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Epic Games</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Nintendo Switch</td><td><span>✓</span></td><td><span>-</span></td></tr><tr><td>Xbox</td><td><span>✓</span></td><td><span>-</span></td></tr></tbody></table>

<div id="integrate-with-ad-networks-that-support-specified-ctv-pc-and-console-platforms" />

### Intégrate con ad networks compatibles con las plataformas especificadas de CTV, PC y consolas

Intégrate con ad networks que muestran anuncios en plataformas de CTV, PC y consola en <Anchor target="_blank" href="/marketers/es/docs/partner-integrations">Integraciones de partners</Anchor>.

<div id="cross-platform-attribution-flows" />

## Flujos de atribución multiplataforma

Cuando se comercializan aplicaciones en plataformas CTV, PC y consolas, existen varios flujos, desde la visualización de anuncios (impresión o clic) hasta la atribución de AppsFlyer, que se aplican a todas las plataformas:

* Enlace de atribución directa
* Enlaces de OneLink multiplataforma
* SRN (red de autorreporte, también conocida como SAN, red de autoatribución)
* Landing page multiplataforma

Cada aplicación, anunciante y plataforma puede tener 1 o más de estos flujos implementados al mismo tiempo. En las secciones siguientes se explican los diferentes tipos de flujo y cuándo se utiliza cada uno.

<Accordion title="Enlace de atribución directa">

Los enlaces de atribución directa son enlaces de AppsFlyer que admiten la redirección y la atribución de una sola aplicación de destino en una sola plataforma a la vez. Por lo general, se utilizan para:

* Publicidad de una plataforma a la misma plataforma. Lo que significa que la plataforma que muestra el anuncio y la plataforma que admite la aplicación son idénticas. Por ejemplo, un anunciante puede mostrar un anuncio de una aplicación de Samsung TV en un televisor Samsung. Se admiten tanto el modelado probabilístico como la coincidencia determinista (la coincidencia determinista se realiza cuando se proporciona en el enlace <Anchor target="_blank" href="/marketers/es/docs/about-device-identifiers#identificadores-de-dispositivos-ctv">un ID compatible</Anchor>).
* Publicidad de cualquier plataforma a cualquier plataforma, con el destino/plataforma predeterminado. Por ejemplo, una landing page web de desktop muestra un anuncio con uno o más botones, cada uno de los cuales redirige a la tienda/marketplace de una plataforma específica. La atribución se realiza mediante modelado probabilístico.

 El flujo de atribución se ilustra en el siguiente diagrama.

<Image align="center" alt="Flujo de atribución de CTV - Flujo de enlace de atribución directa" src="https://files.readme.io/2af32b096faa381843040314c9c183056256d03a7e2e6095e72a59bb7211727f-19374976446225.png" />

Como los enlaces de atribución directa apuntan a una app en una plataforma específica y predeterminada y llevan a un único destino, siempre incluyen el App ID y la información de la plataforma en la URL.

Ejemplo de enlace de atribución directa: `https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/1234561?&af_media_source=game_media_source&af_campaign=campaign_yellow&af_campaign_id=1234&af_ad=game_ad_name&af_adset=game_adset_name&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F1176160%2FSpace_Wars%2F`

<Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-direct-attribution-links#enlace-de-atribución">Aprende a crear enlaces de atribución directa</Anchor>.

</Accordion>

<Accordion title="Enlaces de OneLink multiplataforma">

Los enlaces OneLink multiplataforma admiten el enrutamiento y la atribución cuando la plataforma del anuncio y la plataforma de destino son diferentes. El usuario ve un anuncio de una aplicación móvil en una plataforma y luego continúa el viaje en otra.

Ejemplos:

* CTV-to-mobile. El usuario ve el anuncio de la aplicación móvil en un dispositivo Roku. Luego instalan o abren la aplicación de Android o iOS.
* De web de escritorio a consola. El usuario ve el anuncio del juego en la web de desktop. Luego continúa en una plataforma de PC o consola, como PlayStation, Xbox o Steam.

Los enlaces OneLink multiplataforma solo admiten el método de atribución de modelado probabilístico (basado en la dirección IP). Por este motivo, las instalaciones múltiples de varios usuarios se pueden atribuir a la misma impresión. El flujo de atribución se ilustra en el siguiente diagrama.

Todos los destinos/plataformas de aplicaciones posibles se configuran en la plantilla de OneLink. Con ese fin, los enlaces multiplataforma de OneLink no contienen un ID de aplicación específico o información específica de la plataforma en la URL. En su lugar, la URL incluye el ID de plantilla, que contiene todos los posibles destinos/plataformas de app configurados.

Ejemplo de enlace OneLink multiplataforma:

```
https://impressions.onelink.me/ch/AG7A?pid=game_media_source&c=game_landing_page&af_ad=game_ad_name&af_adset=game_adset_name&af_xplatform=true
```

<Anchor target="_blank" href="/marketers/es/docs/set-up-cross-platform-links-for-multi-device-campaigns">Saber más sobre cómo configurar enlaces OneLink multiplataforma</Anchor>

</Accordion>

<Accordion title="nombres de SRN reservados">

Con enlaces de atribución directa y enlaces OneLink multiplataforma, el atributo de AppsFlyer se instala a través de los datos contenidos en la URL. Por el contrario, las redes de autoreporte (SRN), a veces también conocidas como redes de autoatribución (SAN), se atribuyen automáticamente utilizando el ID del dispositivo cuando AppsFlyer les avisa de una instalación.

La atribución a las SRNs se realiza a través de la coincidencia determinista. Cuando un anunciante integra un SRN, la atribución funciona como en el diagrama a seguir.

<Image align="center" alt="Flujo de atribución de CTV - Flujo de atribución de SRN" src="https://files.readme.io/ba0d84643aefd6a20e95c8aca9424affea8169c95ccc428ddf3d35bb8787a67c-19374961372945.png" />

Actualmente, la atribución de SRN solo funciona para la publicidad de una plataforma a la misma plataforma. Es decir, cuando el punto de contacto (clic o impresión) se produce en la misma plataforma que la instalación. Por ejemplo, si se verifica la instalación CTV de Roku con Roku Endemic Media (el SRN de Roku) y se encuentra que se ha producido una impresión en un dispositivo Roku. Si la impresión se produjo en una plataforma diferente, como un móvil, no se tiene en cuenta para la atribución.

En el futuro, la atribución de SRN puede estar disponible para otros tipos, lo que permitirá una atribución multiplataforma más completa.

</Accordion>

<Accordion title="Página de destino multiplataforma">

Las landing pages multiplataforma están diseñadas para admitir viajes de usuario y flujos de marketing comunes entre plataformas. Son los más utilizados para aplicaciones de juegos. Ejecutan el Smart Script de AppsFlyer para realizar la atribución web-to-app. Esto significa que atribuyen las instalaciones en cualquier plataforma (como CTV, PC, consola y plataformas móviles) a los anuncios que se muestran en la web.

El Smart Script de una landing page multiplataforma utiliza el enlace entrante (el enlace del anuncio web) para hacer dos cosas que garantizan que la fuente de medios original y el anuncio web se atribuyan a la instalación:

* Crea un enlace de OneLink multiplataforma que envíe una impresión a AppsFlyer. Esto permite que AppsFlyer registre una impresión que luego se puede usar para atribuir las instalaciones de los usuarios. Las impresiones se envían cuando se abre la landing page. Incluso si los usuarios abandonan la landing page sin hacer clic en ningún botón y luego descargan e instalan la aplicación por cuenta propia, la impresión se sigue atribuyendo.
* Crear enlaces de atribución directa para cada aplicación o plataforma. Cuando los usuarios hacen clic en estos enlaces, se les dirige a la plataforma/tienda de aplicaciones correcta. Y cuando posteriormente descargan e instalan la aplicación, la instalación se atribuye al clic.

La landing page admite métodos de atribución de modelos probabilísticos y de coincidencia determinista (cuando se proporciona un ID en el enlace). Con el modelado probabilístico, es posible que varias instalaciones de varios usuarios se puedan atribuir a la misma impresión. El flujo de atribución se ilustra en el siguiente diagrama.

<Image align="center" alt="Flujo de atribución de CTV - Flujo de atribución de la landing page" src="https://files.readme.io/28e4d14d14532332027e5d429ac3f95c8d4d451d94125e399cfb9ad04727b278-19374961376529.png" />

Por ejemplo,

1. Tienes una aplicación de juegos que se puede descargar y jugar en plataformas de PC, móviles, Epic o Steam.
2. Anuncias en la web.
3. Un usuario ve el anuncio en la web, ya sea en los resultados de búsqueda pagos o en las promociones de las redes sociales.
4. Los usuarios hacen clic en el anuncio y son redireccionados a una landing page, que tiene botones de descarga separados para cada plataforma: ordenador, móvil, Epic y Steam.
5. La landing page ejecuta el Smart Script de AppsFlyer que:
6. Captura puntos de datos esenciales del enlace entrante (el enlace que llevó al usuario de la web a la landing page), como parámetros de consulta o UTM, o valores predeterminados, que identifican la fuente de medios, la campaña, el anuncio y más.
7. Utiliza los puntos de datos anteriores para generar una impresión y enviarla a AppsFlyer.
8. Genera enlaces salientes para cada uno de los botones de descarga de la plataforma.
9. El usuario hace clic en uno de los botones de descarga, es llevado a la tienda de aplicaciones de la plataforma, descarga y abre la aplicación.
10. La instalación/primera apertura de la aplicación coincide con la impresión y se atribuye a la fuente de medios que mostró el anuncio original en la web.

Información adicional:

* <Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/">Ver ejemplo de landing page multiplataforma</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/cross-platform-landing-pages-with-smart-script">Saber más sobre cómo configurar landing pages multiplataforma con Smart Script</Anchor>

</Accordion>

<div id="data-availability" />

## Disponibilidad de datos

Los datos de plataformas CTV, PC y consola incluyen datos de instalación, así como datos de eventos in-app que brindan a los anunciantes información sobre el lifetime value (LTV) de los usuarios orgánicos y no orgánicos, incluidos en la suscripción, las compras in-app y la monetización de anuncios. Las métricas de LTV se calculan desde la fecha de atribución hasta el presente.

Los datos están disponibles de la siguiente manera:

* Agrega datos a través del Dashboard general.
* Raw data a través de:
  * <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-data-via-data-locker">Casillero de datos</Anchor>
  * <Anchor target="_blank" href="/marketers/es/docs/raw-data-export-page">Exportación</Anchor>
  * <Anchor target="_blank" href="/marketers/es/docs/pull-api-raw-data">API Pull</Anchor>
* **Las impresiones de las campañas multiplataforma** (por ejemplo, de CTV a móvil) no se muestran en los dashboards a nivel de aplicación. Una sola impresión de CTV puede dar lugar a varias conversiones móviles, por lo que es imposible dividir las impresiones con precisión entre aplicaciones. Para acceder al recuento total de impresiones, utiliza el <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-data-via-data-locker">reporte de engagements multiplataforma a través de Data Locker</Anchor>.

<div id="note" />

> 📘 **Nota:**
>
> En las plataformas con sistemas operativos Android e iOS, la disponibilidad de los <Anchor target="_blank" href="/marketers/es/docs/aggregated-and-analytics-reporting-overview">datos agregados</Anchor> y los <Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-overview">Reportes de raw data</Anchor> es la misma que para las aplicaciones móviles.

<Accordion title="Rasgos y limitaciones">

| Caducado | Observaciones |
| --- | --- |
| Ventana de reatribución | Para CTV, PC y consola, la ventana de reatribución se basa en un período definido de inactividad (por defecto 90 días). |
| Eventos posteriores a la reinstalación | Atribuido a la primera instalación. <Anchor target="_blank" href="/marketers/es/docs/measure-reinstalls#attributed-to-the-first-install">Saber más</Anchor> |
| Reorientación | <ul><li>Reatribución: Compatible con cross-platform-to-mobile.</li><li>Re-engagement: Compatible con cualquier plataforma que no sea Android, iOS, Windows Phone o sitio web. En la práctica, esto significa aplicaciones para CTV, PC y consolas.</li></ul> |
| Método de atribución | <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model#métodos-de-atribución">Consulta los métodos de atribución de plataformas CTV, PC y consola</Anchor> |
| Truemoney | USD o como se define en la configuración de la aplicación de AppsFlyer |
| Zona horaria | UTC |
| Datos de costos | Para las aplicaciones en estas plataformas, importa los datos de costo a través de <Anchor target="_blank" href="/marketers/es/docs/import-cost-data">Cost Import</Anchor> utilizando el método de carga por correo electrónico.<br /><br />También puedes extraer datos a través de la API para Google, Meta o TikTok en las siguientes plataformas:<ul><li>Steam</li><li>PC Nativo</li><li>Smart Cast</li><li>Windows Phone</li><li>Tizen</li><li>Quest</li></ul> |
| Datos actualizados | En My Dashboards, las métricas de instalaciones, re-engagements y reatribuciones para las plataformas CTV, PC y consola se sirven desde nuestra canalización de datos preparada para IA (migrada entre el 21 de julio y el 10 de agosto de 2026). Esto significa que estas métricas para estas plataformas ahora aparecen con retraso en lugar de hacerlo de forma continua. Consulta <Anchor target="_blank" href="/marketers/es/docs/my-dashboards#traits-and-limitations">las características y limitaciones de My Dashboards</Anchor> para más información. |

</Accordion>

<div data-zendesk-anchors="about-ctv-attribution=la-soluci%C3%B3n-multiplataforma-de-appsflyer 01H7ZRK7PCNZG54ZQ0804HMR38=la-soluci%C3%B3n-multiplataforma-de-appsflyer list-of-supported-ctv-and-gaming-device-types=plataformas-compatibles 01H7ZRK7PCP1KWRX1A5K81F4KR=plataformas-compatibles list-of-specified-platforms=int%C3%A9grate-con-ad-networks-compatibles-con-las-plataformas-especificadas-de-ctv-pc-y-consolas h_01JMA8F9F6M2MZFNRXFQWJF8B8=int%C3%A9grate-con-ad-networks-compatibles-con-las-plataformas-especificadas-de-ctv-pc-y-consolas crossplatform-attribution=flujos-de-atribuci%C3%B3n-multiplataforma 01H8EHHJNBA8NKMX2C8RSV7P31=flujos-de-atribuci%C3%B3n-multiplataforma data-availability=disponibilidad-de-datos h_01H9G52NKMQG9QD9S3N537BM7N=disponibilidad-de-datos h_01M2MN6SN9SW7RGGK5R1MFW91B=nota" />
