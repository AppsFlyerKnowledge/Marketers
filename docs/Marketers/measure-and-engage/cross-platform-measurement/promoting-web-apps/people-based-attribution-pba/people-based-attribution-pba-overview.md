---
title: 'Atribución basada en las personas (PBA): Descripción general'
metadata:
  keywords:
    - People Based Analysis
    - People Based Attribution
    - People Based Attribution SDK
    - Developers
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2019-08-19T11:53:56Z'
  edited_at: '2026-08-12T12:11:42Z'
  id: 360002274017
  locale: es
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/es/articles/360002274017
---
> **De un vistazo:** La atribución basada en las personas (PBA) proporciona una visión unificada de las trayectorias de los clientes a través de canales, plataformas y dispositivos.

<Image align="center" alt="PBANoSilos_us-en.gif" src="https://files.readme.io/1ac3614eb1b9d4c01bffbe904f1a060d1facd681ff32c274b12f0a15612a2e4a-360009359798.gif" />

<div id="pba-principles" />

## Los principios de la PBA

* La PBA consolida los datos de los sitios web y las aplicaciones móviles para proporcionar una visión holística del rendimiento de la campaña a través de las propiedades digitales de una marca. Los anunciantes usan la PBA para entender las trayectorias de los clientes en términos de personas, en lugar de dispositivos.
* Los datos de la PBA, en los paneles de control de la PBA y en los reportes de raw data, se utilizan para los análisis de marketing y la optimización de las campañas.
* Los datos consisten en las visitas a sitios web y los eventos de usuarios que se adquieren usando <Anchor target="_blank" href="/marketers/es/docs/pba-web-sdk-integration-guide">SDK o API</Anchor>.
* Para cada visita al sitio web: se determina la fuente de medios responsable de llevar la visita. Cualquier evento resultante (conversión) se <Anchor target="_blank" href="/marketers/es/docs/pba-media-source-attribution-rules">atribuye</Anchor> a la fuente de medios que causó la visita.

<div id="pba-analytics-dashboards-and-raw-data" />

### Paneles de control analíticos y raw data de la PBA

* Los datos de la PBA se presentan a través de reportes y paneles de control analíticos:
  * Atribución del sitio web
  * Instalaciones asistidas por web
  * Reportes de raw data
* Los datos en los paneles de control <Anchor target="_blank" href="/marketers/es/docs/using-pba-dashboards">se filtran y agrupan</Anchor> usando dimensiones como plataforma móvil, canal de medios y tipo de medios.

<div id="website-attribution" />

### <Anchor target="_blank" href="/marketers/es/docs/pba-website-attribution-dashboard">Atribución del sitio web</Anchor>

<Image align="center" alt="WebsiteAttributionTable" src="https://files.readme.io/327a4830ca20ba9067bb9f7a5e5264908fd918ada9462261befcef2f48fd0fd0-360013135398.jpg" />

Analiza las fuentes de tráfico web y las campañas de marketing que impulsan las visitas de los usuarios y las conversiones en tu sitio web. Descubre las diferencias de rendimiento hasta el nivel de anuncio. Admite todos los parámetros de consulta de AppsFlyer en el enlace sin necesidad de redirigir a los usuarios a los servidores de AppsFlyer.

<div id="web-assisted-installs" />

### <Anchor target="_blank" href="/marketers/es/docs/pba-web-assisted-installs">Instalaciones asistidas por web</Anchor>

<Image align="center" alt="AppsFlyer-Web-to-App_us.en.gif" src="https://files.readme.io/4a278b57379c999d80fd7f1dfea750049f56c03ed32051f9af92577b2a51742a-360009705058.gif" />

Usa las instalaciones asistidas por web para examinar el impacto y los resultados de tus esfuerzos de marketing web para impulsar las instalaciones de aplicaciones móviles.

* Obtén insights sobre cómo interactúan los diferentes tipos de medios (pagados, propios, obtenidos), los canales de medios (directos, redes sociales, búsqueda orgánica) y las fuentes de medios, y cómo contribuyen a tus esfuerzos generales de adquisición de usuarios.
* Atribuye instalaciones orgánicas impulsadas por tus esfuerzos web.
* Examina la interacción entre los esfuerzos web y las instalaciones no orgánicas.

### <Anchor target="_blank" href="/marketers/es/docs/pba-raw-data-reports">Raw Data</Anchor>

Los reportes de raw data están disponibles a través de Data Locker. El raw data ofrece insights en profundidad e incluye la fuente de medios atribuida/responsable de traer al usuario al sitio web.

* **Visitas web:** visitas al sitio web
* **Eventos web**: acciones realizadas en el sitio web como suscribirse o comprar.
* Las trayectorias de la **ruta de conversión** y de las **instalaciones asistidas por web** se proporcionan en su totalidad.
* Las herramientas de Business Intelligence se utilizan para analizar los datos y así obtener insights adicionales.
* <Anchor target="_blank" href="/marketers/es/docs/pba-raw-data-reports">Saber más sobre raw data de PBA</Anchor>.

<div id="see-also" />

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/onboarding-guide-to-people-based-attribution">Guía de onboarding de PBA</Anchor>

<div data-zendesk-anchors="pba-principles=los-principios-de-la-pba 01ECF26CMJ8TB4ADT6VN277EMQ=los-principios-de-la-pba pba-analytics-dashboards-and-raw-data=paneles-de-control-anal%C3%ADticos-y-raw-data-de-la-pba 01ECF26CMJDA1HBC22DGRWY2EA=paneles-de-control-anal%C3%ADticos-y-raw-data-de-la-pba website-attribution=atribuci%C3%B3n-del-sitio-web 01ECF26CMK0T5C9JKQ0SYMXQVM=atribuci%C3%B3n-del-sitio-web webassisted-installs=instalaciones-asistidas-por-web 01ECF26CMKDS16XWRBQ1SDAX2Q=instalaciones-asistidas-por-web 01ECF26CMM4KHX9W94DND4BY8C=raw-data h_01HE0Y2KTXS06WHN57MQ91AD09=consulta-tambi%C3%A9n" />
