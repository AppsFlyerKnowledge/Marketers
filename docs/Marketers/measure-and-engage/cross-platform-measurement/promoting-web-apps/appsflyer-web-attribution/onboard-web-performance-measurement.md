---
title: Incorpora la medición del rendimiento web
metadata:
  keywords:
    - Attribution
    - Agencies
    - Web Attribution
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
    - Agencies
  created_at: '2026-02-04T19:35:31Z'
  edited_at: '2026-08-26T00:22:25Z'
  id: 43529798016401
  locale: es
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/es/articles/43529798016401
---
> **Resumen:** Sigue las instrucciones de onboarding que se incluyen en esta guía para configurar la atribución web de AppsFlyer. Una vez configurado, podrás medir y atribuir las visitas y los eventos web a las fuentes de marketing, comprender qué factores impulsan los resultados significativos del sitio web y proporcionar soporte para la medición multiplataforma.

<div id="about-web-performance-measurement" />

## Acerca de la medición del rendimiento web

La medición del rendimiento web te ayuda a relacionar lo que ocurre en tu sitio web, como las visitas y los eventos web, con las fuentes de marketing que los impulsaron. En otras palabras, te muestra qué fuentes de medios y campañas atraen a los usuarios a tu sitio web e influyen en sus acciones posteriores, para que puedas medir el rendimiento y optimizar el ROI.

<div id="create-a-web-app-in-appsflyer" />

### Sobre la atribución web de AppsFlyer

<Embed title="Incorpora la medición del rendimiento web" typeOfEmbed="youtube" url="https://www.youtube.com/embed/tJ_LoaQinzY" providerUrl="https://www.youtube.com" />

<div id="set-up-network-integrations-postbacks-and-cost-measurement" />

### Configura integraciones de red, postbacks y medición de costes

<Embed title="Incorpora la medición del rendimiento web" typeOfEmbed="youtube" url="https://www.youtube.com/embed/-sYIv3YQEwo" providerUrl="https://www.youtube.com" />

Para empezar a realizar la medición de las visitas al sitio web y los eventos web en AppsFlyer, sigue los pasos de onboarding que se indican en la siguiente lista de verificación para la configuración de la atribución web de AppsFlyer.

<div id="web-performance-measurement-setup-checklist" />

## Lista de comprobación para la configuración de la atribución web de AppsFlyer

Utiliza la tabla siguiente para completar las tareas clave de configuración, quién debe hacer qué y en qué orden, a fin de empezar a recopilar visitas y eventos web en AppsFlyer.

| Tarea | Acciones requeridas | Dónde aprender a | Quiénes participan |
| --- | --- | --- | --- |
| 1. Crear una aplicación web | En la página de **configuración de la app:**<ul><li>Copia el **ID del SDK web** y compártelo con tus desarrolladores.</li><li>Configura la **zona horaria** y la **moneda** de los reportes.</li><li>Selecciona los **dominios excluidos**.</li></ul> | <ul><li><Anchor target="_blank" href="/marketers/es/docs/adding-an-app-to-appsflyer#web">Configurar los ajustes de la aplicación web</Anchor></li></ul> | Comercializador |
| 2. (Opcional) Crear una línea de productos para el LTV multiplataforma | Para habilitar la atribución multiplataforma y la medición del viaje del usuario en términos de LTV, crea una entidad de línea de productos y asocia las aplicaciones o propiedades web pertinentes, o bien añade tu aplicación web a una línea de productos ya existente. | <ul><li><Anchor target="_blank" href="/marketers/es/docs/product-line-group-apps-for-cross-platform-attribution">Crear una línea de productos</Anchor></li></ul> | Comercializador |
| 3. Instalación y configuración del SDK web | Integra el SDK web de AppsFlyer en tu sitio web. | <ul><li><Anchor target="_blank" href="/marketers/es/docs/integrate-appsflyer-web-sdk">Integra el SDK web en tu sitio web</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/use-the-web-sdk-test-page">Prueba la integración del SDK web</Anchor></li></ul> | desarrollador |
| 4. Configura los ajustes de atribución de la aplicación web. | Usa la API server-to-server (S2S) para enviar visitas web y eventos a AppsFlyer directamente desde tu Servidor. Úsala junto con el SDK web para ampliar la cobertura de medición y enriquecer los datos de eventos, o por sí sola para una integración totalmente del lado del servidor. | <ul><li><Anchor target="_blank" href="/marketers/es/docs/server-to-server-s2s-api-for-web-performance-measurement">Configura la API S2S para la medición del rendimiento web</Anchor></li></ul> | Ingeniero de inteligencia empresarial (BI) |
| 5. Crear URLs para la atribución web de AppsFlyer | En la página de **configuración de la app** , configura los ajustes de atribución de la app web, como las ventanas de lookback y los eventos de adquisición de usuarios.  <br />**Nota:** Los eventos personalizados de adquisición de usuarios solo se pueden seleccionar una vez que se haya integrado el SDK web en tu sitio web. | <ul><li><Anchor target="_blank" href="/marketers/es/docs/configure-web-performance-measurement-settings">Configurar los ajustes de atribución de la aplicación web</Anchor></li></ul> | Comercializador |
| 6. Configurar la integración con los partners compatibles | Crea URLs utilizando el parámetro de atribución correcto para obtener resultados de atribución más precisos y granulares. | <ul><li><Anchor target="_blank" href="/marketers/es/docs/choose-attribution-parameters-for-landing-page-urls">Selecciona los parámetros de atribución para las URLs de las landing pages</Anchor></li></ul> | Comercializador |
| 7. Exportar datos de atribución web de AppsFlyer desde Data Locker | Activa los partners y configura los postbacks que se les remiten.<br />Partners compatibles:<ul><li>Anuncios de Google</li><li>Anuncios de Meta</li><li>Anuncios Tik Tok</li><li>Snapchat Ads</li></ul> | Crea campañas web para aplicaciones web con:<ul><li><Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-create-web-campaigns-for-website-apps">Anuncios de Google</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/meta-ads-create-web-campaigns-for-website-apps">Anuncios de Meta</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/tiktok-for-business-create-web-campaigns-for-website-apps">Anuncios Tik Tok</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/snapchat-create-web-campaigns-for-website-apps">Snapchat Ads</Anchor></li></ul> | Comercializador |
| 8. Exportar datos de atribución web de AppsFlyer desde Data Locker | Configura **Data Locker** para los reportes de datos sin procesar de la medición del rendimiento web, de modo que los equipos de business intelligence y de análisis puedan analizar los viajes web. | <ul><li><Anchor target="_blank" href="/marketers/es/docs/export-web-performance-measurement-report-data-from-data-locker">Exportar datos de atribución web de AppsFlyer desde Data Locker</Anchor></li></ul> | Marketer / Ingeniero de BI |
| 9. Consulta tus datos web en el dashboard multiplataforma | Consulta cómo aparecen las sesiones web y los eventos en el dashboard multiplataforma. | <ul><li><Anchor target="_blank" href="/marketers/es/docs/my-dashboards#atribución-web-en-el-dashboard-entre-plataformas">Atribución web en el dashboard multiplataforma</Anchor></li></ul> | Comercializador |
| 10. Calcular el costo de las campañas en la web<br /><br />**(Solo para ROI360)** | Conecta tu aplicación web a las integraciones de costos en la **configuración de costos** para las redes de auto-reporte (SRN) compatibles: Google, Meta (Facebook), Snapchat y Twitter.  <br />  <br />Una vez conectadas, los datos sobre costos, clics e impresiones de las campañas web se muestran casi en tiempo real en los reportes de Cost ETL y en My Dashboard.  <br />  <br />En el **paquete avanzado de ROI360**, añade tu aplicación web a la lista de aplicaciones incluidas en la página de configuración de Cost ETL.  <br />  <br />**Nota:** Los enlaces de atribución deben incluir un ID de campaña en la URL de la landing page | Conecta tu aplicación web a la integración de costos:<ul><li><Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-create-web-campaigns-for-website-apps#mide-los-datos-de-rendimiento-web-con-el-costo-web">Anuncios de Google</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/meta-ads-create-web-campaigns-for-website-apps#medir-datos-de-atribución-web-con-costo-web">Anuncios de Meta</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/snapchat-create-web-campaigns-for-website-apps#medir-datos-de-atribución-web-con-costo-web">Snapchat Ads</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl">Configurar Cost ETL</Anchor></li></ul> | Marketer / Ingeniero de BI |

<div data-zendesk-anchors="about-appsflyer-web-attribution=acerca-de-la-medici%C3%B3n-del-rendimiento-web h_01KGN43TYPKCQ7H3SRRHHPT387=acerca-de-la-medici%C3%B3n-del-rendimiento-web how-to-create-a-web-app-in-appsflyer=sobre-la-atribuci%C3%B3n-web-de-appsflyer h_01KVSNN9H462X8DVYBS6TJ8JXQ=sobre-la-atribuci%C3%B3n-web-de-appsflyer how-to-set-up-network-integrations-postbacks-and-cost-measurement=configura-integraciones-de-red-postbacks-y-medici%C3%B3n-de-costes h_01KVSNSSZ7QY090JVWVTRF88ND=configura-integraciones-de-red-postbacks-y-medici%C3%B3n-de-costes appsflyer-web-attribution-setup-checklist=lista-de-comprobaci%C3%B3n-para-la-configuraci%C3%B3n-de-la-atribuci%C3%B3n-web-de-appsflyer h_01KGN43TYP1EV5KFQ37FC4SM0C=lista-de-comprobaci%C3%B3n-para-la-configuraci%C3%B3n-de-la-atribuci%C3%B3n-web-de-appsflyer" />
