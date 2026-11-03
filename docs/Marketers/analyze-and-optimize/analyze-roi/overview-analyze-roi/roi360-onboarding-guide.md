---
title: Guía de onboarding de ROI360
metadata:
  keywords:
    - ROI
    - cost
    - Marketers
    - revenue
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2024-05-23T08:36:31Z'
  edited_at: '2026-09-11T00:01:07Z'
  id: 25301111725329
  locale: es
  section: Overview
  section_id: 15173289016593
  url: https://support.appsflyer.com/hc/es/articles/25301111725329
---
> **Resumen**: Sigue las instrucciones de esta guía para activar ROI360 para el manejo de datos de costos e ingresos.

![](https://files.readme.io/fa3644980702d735f81d7243f91cb0f0d454bd971e83685ab9759ff7bd925e93-26137252926097.png)

## Sobre ROI360

ROI360 es un conjunto de herramientas únicas para reportes de costos e ingresos que te ofrece datos precisos y actualizados. Gracias a la combinación de datos de costos e ingresos, podrás obtener una visión completa de tu retorno publicitario (ROAS) y de inversión (ROI), permitiéndote optimizar y mejorar.

Sigue las instrucciones a continuación para activar las herramientas de ROI360 para reportes de costos, ingresos por publicidad e ingresos por compras y suscripciones in-app. El onboarding debe ser completado por marketers, desarrolladores de aplicaciones y desarrolladores de BI.

**¡Consejo!** Para incorporarse de manera rápida, prioriza una aplicación y completa todos los pasos para que ROI360 esté activo. Puedes enfocarte en costos, ingresos por publicidad o compras y suscripciones in-app, pero asegúrarte de completar primero el onboarding de una aplicación.

<div id="cost-onboarding" />

<Accordion title="Onboarding de costos">

![](https://files.readme.io/0e7102766b3b7cdba3f301ca89c51edf8e4bd2ec88e09bc912ce3c1436c43fcb-26137252929681.png)

Con la solución de costos de ROI360, obtendrás datos detallados sobre costos y ROI, actualizados varias veces al día. Esto te permitirá gestionar eficazmente los costos de campaña y examinar las asignaciones de presupuesto en distintas fuentes de medios, ya sean ad networks, medios propios o agencias.

Después de finalizar el onboarding de costos, podrás:

* Conseguir vistas generales completas y actualizadas de los costos de campaña con consolidación automática de todas las fuentes de medios.
* Basar tu análisis de datos en información de costos precisa, actualizada después de la instalación.
* Los usuarios avanzados de ROI360 pueden transmitir datos de costos detallados a tu sistema de BI hasta 4 veces al día.
* Gestionar las tarifas de la agencia y medir con precisión los costos totales de la campaña para asegurar la supervisión y transparencia financiera.

| Tarea | Objetivo | Acciones requeridas | ¿Quiénes están involucrados? |
| --- | --- | --- | --- |
| Conecta las integraciones de la API de costos para todas las ad networks con las que trabajas. | Obtén datos de costos de cada fuente vinculada a la atribución al nivel más detallado. | <Anchor target="_blank" href="/marketers/es/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">Habilita la API de costos</Anchor> para cada ad network en la interfaz de AppsFlyer. **Nota:** Antes de integrar, debes obtener las credenciales o información para iniciar sesión en cada ad network. | Comercializador |
| Configura reportes ETL de costos. (Disponible para suscriptores de ROI360 Advanced) | Visualiza datos de costos de campaña con la mejor granularidad disponible por fuente de medios, actualizados hasta 4 veces al día. | Configura reportes ETL de costos para <Anchor target="_blank" href="/marketers/es/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl-for-aws-s3">AWS S3</Anchor> o <Anchor target="_blank" href="/marketers/es/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl-for-gcs">GCS</Anchor>. | Marketer / Desarrollador de BI |
| Sube datos de costos mediante Importación de costos. | Obtén datos de costos:<ul><li>Para ad networks que no reportan costos a través de la API o clics.</li><li>Al utilizar enlaces de OneLink para anuncios a través de influencers, etc.</li><li>Cuando necesitas corregir datos de costos.</li></ul> | Sube o envía por correo archivos de datos de costos usando <Anchor target="_blank" href="/marketers/es/docs/import-cost-data">Importar costos</Anchor>. | Comercializador |
| Configura las tarifas de la agencia. | Si trabajas con agencias, obtén el costo total de campaña, incluyendo el porcentaje de tarifas que cobran por tráfico. | Crea <Anchor target="_blank" href="/marketers/es/docs/incorporate-agency-fees-into-campaign-costs">reglas de tarifas de agencia</Anchor> para cada agencia con la que trabajes. | Comercializador |

</Accordion>

<div id="ad-revenue-onboarding" />

<Accordion title="Onbaording de ingresos publicitarios">

![](https://files.readme.io/877e4abddd466bbe7dfa31f7fffb2f17fe3e6419f3bf6345e9d619253126b0e6-26137252932369.png)

La solución de ingresos publicitarios de ROI360 te proporcionará datos detallados sobre ingresos publicitarios, actualizados varias veces al día.

Una vez completado el onboarding de ingresos publicitarios, incluyendo la conexión a plataformas de mediación o redes de monetización, la implementación de la API a nivel de impresión y el intercambio de datos con partners de UA, podrás:

* Acceder a datos precisos y actualizados sobre ingresos publicitarios en todos los dashboards y reportes de AppsFlyer.
* Transmitir datos a tu sistema de BI con el nivel de detalle y actualización que requiera.
* Mejorar el rendimiento de la campaña al permitir que las redes de UA optimicen según las métricas de ingresos publicitarios.

| Tarea | Objetivo | Acciones requeridas | ¿Quiénes están involucrados? |
| --- | --- | --- | --- |
| Decide tu tipo de integración para la atribución de ingresos publicitarios. | Conoce los beneficios de cada tipo de integración y elige el que mejor se adapta a tus necesidades empresariales. | Infórmate sobre los distintos <Anchor target="_blank" href="/marketers/es/docs/roi360-guide-ad-revenue-attribution#integration-types-for-ad-revenue-attribution">tipos de integración de ingresos publicitarios</Anchor> y elige uno. | Comercializador |
| Conéctate a todas las redes de mediación y monetización de ingresos publicitarios con las que colaboras. | Obtén datos de ingresos publicitarios de tus redes de mediación o monetización. | <Anchor target="_blank" href="/marketers/es/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">Conecta las integraciones de ingresos publicitarios</Anchor> en la interfaz de AppsFlyer. | Comercializador |
| Implementa la API del SDK de ingresos publicitarios a nivel de impresión. | <ul><li>Relevante para tipos de integración a nivel de SDK.</li><li>Obtén datos de ingresos publicitarios con una actualización casi en tiempo real.</li></ul> | <ol><li>Integra la <Anchor target="_blank" href="/marketers/es/docs/integrate-the-roi360-ad-revenue-sdk-api">API del SDK de ingresos publicitarios de ROI360 de AppsFlyer</Anchor>.</li><li>Para visualizar los ingresos publicitarios en el dashboard de SKAN, activa la <Anchor target="_blank" href="/marketers/es/docs/skan-conversion-studio#report-events-by-servertoserver-api">compatibilidad de servidor a servidor de SKAdNetwork</Anchor>.</li></ol> | Desarrollador/Marketer |
| Comparte datos de ingresos publicitarios con partners de adquisición de usuarios (UA). | Las ad networks de UA pueden utilizar estos datos de ingresos para optimizar sus campañas. | <ol><li>Aprende sobre los 2 <Anchor target="_blank" href="/marketers/es/docs/share-ad-revenue-data-with-partners#sobre-el-uso-compartido-de-datos-de-ingresos-publicitarios-con-partners">métodos para compartir datos de ingresos publicitarios con partners de UA</Anchor>.</li><li><Anchor target="_blank" href="/marketers/es/docs/share-ad-revenue-data-with-partners#procedimientos">Implementa el método</Anchor> que elijas.</li></ol> | Comercializador |
| Configura reportes ETL de ingresos. (Disponible para suscriptores de ROI360 Advanced) | Transmite y visualiza datos de ingresos publicitarios en tu BI con la mejor granularidad posible, actualizándose varias veces al día. | Configura <Anchor target="_blank" href="/marketers/es/docs/revenue-etl-reports">reportes ETL de ingresos publicitarios</Anchor>. | Marketer / Desarrollador de BI |

</Accordion>

<div id="revenue-onboarding" />

<Accordion title="Introducción a ingresos por compras y suscripciones in-app.">

![](https://files.readme.io/811c90ec42465994455fe42be8400b4ebb94ab6d1a5703bc9a77251aba95ed3b-26137252934545.png)

Con la solución de ingresos de ROI360, obtienes un control proactivo sobre tus flujos de ingresos.

Al completar el onboarding de ingresos, incluyendo la configuración de notificaciones de la tienda y la implementación de las APIs del SDK para compras en Android e iOS, podrás:

* Establecer validación y medición automática para transacciones en App Store y Google Play.
* Disfrutar de reportes de ingresos precisos sin necesidad de esfuerzos adicionales del desarrollador; ROI360 se encargará de registrar todos los eventos de ingresos in-app por ti.
* Obtener mediciones de ingresos precisas para gestionar iniciativas de crecimiento estratégico en toda tu cartera.

| Tarea | Objetivo | Acciones requeridas | ¿Quiénes están involucrados? |
| --- | --- | --- | --- |
| Implementa la solución de ingresos por suscripciones y compras in-app de ROI360. | Valida y mide automáticamente los ingresos de compras in-app, suscripciones auto renovables y eventos relacionados que llegan a través de App Store (iOS) o Google Play (Android). | Sigue <Anchor target="_blank" href="/marketers/es/docs/purchase-and-subscription-validation-overview">estas instrucciones</Anchor> para:<ol><li>Configurar la integración con Google Play.</li><li>Configurar la integración con iOS App Store.</li><li>Integrar el conector del SDK de compra de AppsFlyer.</li><li>Probar la medición de las compras in-app y los ingresos por suscripción.</li><li>Lanzar las versiones de la aplicación con el conector SDK.</li></ol> | Desarrollador/Marketer |
| Configura reportes ETL de ingresos. (Disponible para suscriptores de ROI360 Advanced) | Transmite y visualiza datos de ingresos en tu BI con la mejor granularidad, actualizándose varias veces al día. | Configura <Anchor target="_blank" href="/marketers/es/docs/revenue-etl-reports">reportes ETL de ingresos</Anchor>. | Marketer / Desarrollador de BI |

</Accordion>

<div data-zendesk-anchors="overview=sobre-roi360 h_01HKHGX9JJQQCKF9SDZRSCM1XJ=sobre-roi360 h_01HYJ8PSPTFR6QH329TBR73AXM=cost-onboarding h_01HYJ8PSPTKBZ60TF7T0EMSCXW=ad-revenue-onboarding h_01HYJ8PSPTWK4SEGVJWG5J86E2=revenue-onboarding" />
