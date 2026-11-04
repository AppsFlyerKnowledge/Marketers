---
title: 'Primeros pasos: Onboarding para marketers'
metadata:
  keywords:
    - SDK
    - Integration
    - Reports
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2015-01-18T11:03:01Z'
  edited_at: '2026-08-12T12:05:21Z'
  id: 207033486
  locale: es
  section: Marketer onboarding
  section_id: 6550866490129
  url: https://support.appsflyer.com/hc/es/articles/207033486
---
> **En resumen:** Configura todo para aprovechar al máximo tu cuenta de AppsFlyer. Comprende los pasos, los plazos y las dependencias para incorporar tus aplicaciones y a tu equipo.

<Embed title="Primeros pasos: Onboarding para marketers" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/gamcb25kgu" providerUrl="https://fast.wistia.com" />

<div id="introduction" />

## Introducción

Este documento ayuda a los gerentes de producto del marketer (propietario de la aplicación) a **planificar y ejecutar su onboarding con AppsFlyer**. Para cada elemento, se proporcionan el propietario y el tiempo aproximado de implementación.

Ten en cuenta que las estimaciones de tiempo en este artículo están pensadas como orientación general únicamente. Se basan en nuestra experiencia de trabajo con muchos clientes nuevos, pero reconocemos que cada propietario, aplicación e implementación de cada aplicación es diferente. Tus requisitos de tiempo real pueden variar.

<div id="account-setup" />

## Configuración de la cuenta

El **administrador de la cuenta** debe completar los siguientes pasos:

| Paso | Hora | Comentarios |
| --- | --- | --- |
| <Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Regístrate</Anchor> con AppsFlyer | 5 minutos | Lo ideal es que el administrador de la cuenta sea un usuario real de AppsFlyer que pueda recibir mensajes importantes cuando sea necesario. |
| <Anchor target="_blank" href="/marketers/es/docs/user-management#creating-users">Agregar usuarios de cuenta</Anchor> que usarán el dashboard de AppsFlyer, y configurar sus permisos | 1 min por usuario de la cuenta | <Anchor target="_blank" href="/marketers/es/docs/user-management#creating-users">En algunos casos</Anchor>, los usuarios pueden agregarse a múltiples cuentas. |

**Resultado:** ¡Bienvenido! **Resultado:** ¡Bienvenido! Ahora tienes una cuenta de AppsFlyer activa y usuarios de la cuenta que pueden acceder a ella.

<div id="tip" />

> 👍 **Consejo**
>
> ¿Eres nuevo en AppsFlyer y te preguntas qué puede hacer por ti? ¿Eres nuevo en AppsFlyer y te preguntas qué puede hacer por ti? <Anchor target="_blank" href="/marketers/es/docs/welcome-to-appsflyer#qué-puedes-hacer-con-appsflyer">Mira este video de 6 minutos</Anchor>.

<div id="app-onboarding" />

## Onboarding de la aplicación

Los siguientes **pasos del 1 al 3 son obligatorios para cada aplicación** agregada a AppsFlyer (excepto donde se indique como opcional).

Puedes seguir los pasos usando esta guía o a través de la página de onboarding de aplicaciones. La página de onboarding de aplicaciones te guía a través de los pasos básicos necesarios para que tu aplicación esté lista para la atribución. Si prefieres usarla, te recomendamos que consultes también esta guía para ver los pasos adicionales que puedas necesitar para las necesidades específicas de tu negocio.

**Para abrir la página de onboarding de aplicaciones:**

1. En la barra de menú, haz clic en el menú de usuario (desplegable de dirección de correo electrónico).
2. Selecciona onboarding de aplicaciones.

<div id="step-1-app-setup" />

## Paso 1: Configuración de la aplicación

El **administrador de la cuenta** debe completar los siguientes pasos para cada una de tus aplicaciones:

| Paso | Hora | Comentarios |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/es/docs/adding-an-app-to-appsflyer">Agrega tu aplicación</Anchor> a la cuenta de AppsFlyer | 1 minuto | Si la adición de una aplicación falla, a menudo se debe a que se definió previamente en una cuenta diferente (generalmente, una agencia publicitaria con la que trabajan tus marketers). Ponte en contacto con tu CSM o hello@appsflyer.com para <Anchor target="_blank" href="/marketers/es/docs/transferring-apps-between-accounts">transferir la aplicación a tu cuenta</Anchor>.<br /><br />Consulta los <Anchor target="_blank" href="/marketers/es/docs/adding-an-app-to-appsflyer#resolución-de-problemas">pasos para la resolución de problemas</Anchor> para agregar aplicaciones. |
| Establece la <Anchor target="_blank" href="/marketers/es/docs/adding-an-app-to-appsflyer#introduzca-información-adicional-no-aplicable-a-aplicaciones-web">zona horaria de la aplicación, la divisa</Anchor> y si está dirigida a un público infantil | 1 minuto |  |
| Configura la  <br /><Anchor target="_blank" href="/marketers/es/docs/set-up-re-attribution-window">ventana de reatribución</Anchor> de la app (en la <Anchor target="_blank" href="/marketers/es/docs/app-settings#reattribution-window">página de configuración de la aplicación</Anchor>) | 1 minuto | La ventana de reatribución es el período, a partir de la fecha de la primera instalación, durante el cual las **reinstalaciones desde el mismo dispositivo no se atribuyen** como nuevas instalaciones. El valor predeterminado es 90 días, que puedes personalizar según sea necesario. |
| [Opcional] Migra los dispositivos de usuarios existentes a AppsFlyer | 2 horas | Si tu aplicación ya tiene una base de usuarios considerable, piensa en <Anchor target="_blank" href="/marketers/es/docs/migration-to-appsflyer-from-other-vendors#migración-de-dispositivosopcional">migrarlos a AppsFlyer</Anchor> para evitar cargos dobles.<br /><br />**Nota:** Con la ayuda de tu CSM de AppsFlyer o del equipo de soporte en [hello@appsflyer.com](mailto:hello@appsflyer.com)). |

**Resultado:** Tus aplicaciones ahora están definidas en el dashboard de AppsFlyer.

<div id="step-2-sdk--api-integration" />

## Paso 2: Integración de SDK / API

Completa los siguientes pasos para cada aplicación definida en AppsFlyer en el [Paso 1: Configuración de la aplicación](/docs/getting-started-onboarding-for-marketers#paso-1-configuración-de-la-aplicación):

| Paso | Propietario | Hora | Comentarios |
| --- | --- | --- | --- |
| Considera las opciones disponibles y selecciona las <Anchor target="_blank" href="/marketers/es/docs/sdk-integration-overview">funcionalidades de SDK</Anchor> que deseas que utilice tu aplicación | Gerente de producto | 1 hora | <ul><li>Algunas consideraciones más allá de la atribución básica:<ul><li>¿Tus campañas vincularán con un deep link a los usuarios a la aplicación?</li><li>¿Necesitará la aplicación <Anchor target="_blank" href="/marketers/es/docs/basic-sdk-integration-guide#acceso-a-datos-de-atribución-y-de-deep-linking">acceder a datos de atribución o deep linking</Anchor>?</li><li>¿Los datos de AppsFlyer deben contener tu <Anchor target="_blank" href="/marketers/es/docs/basic-sdk-integration-guide#integrate-unique-identifiers-from-your-bi-system-with-appsflyer">ID de usuario de cliente</Anchor> como referencia?</li><li>¿Cómo implementarás <Anchor target="_blank" href="/marketers/es/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support">la configuración de privacidad para dispositivos iOS 14+</Anchor>? ¿Medirás las desinstalaciones, ejecutarás campañas de promoción cruzada y más? ¿Medirás las desinstalaciones, ejecutarás campañas de promoción cruzada y más?</li></ul></li><li>¿Tienes una aplicación de CTV? Mira nuestra <Anchor target="_blank" href="/marketers/es/docs/ctv-pc-and-console-platform-attribution-concepts">vista general de CTV</Anchor>.</li></ul> |
| Selecciona qué <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview">eventos in-app</Anchor> registrar | Gerente de producto | 1 hora | Registrar los eventos posteriores a la instalación que tus usuarios realizan en la aplicación te ayuda a comprender mejor la **calidad** de tus usuarios.<br /><br />Visita el [Generador de eventos in-app](https://evgen.appsflyer.com/) para usar nuestra lista completa de <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview#recommended-events-by-business-vertical">eventos in-app recomendados</Anchor> y parámetros para tu vertical. Puedes agregar tus propios eventos y parámetros.  <br />Haz clic en el botón **Código** para ver y copiar el código generado automáticamente para sus desarrolladores (y hacerlos felices). |
| Selecciona métodos para recuperar datos de atribución/deep linking | Gerente de producto | 30 minutos | Obtén más información sobre los <Anchor target="_blank" href="/marketers/es/docs/basic-sdk-integration-guide#acceso-a-datos-de-atribución-y-de-deep-linking">métodos</Anchor> disponibles:<ul><li><Anchor target="_blank" href="/marketers/es/docs/pull-api-raw-data">API Pull</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/push-api-streaming-raw-data">API Push</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template">API de deep linking unificada</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/conversion-data-payloads-and-scenarios">Obtener datos de conversión</Anchor></li></ul> |
| Transferencia del desarrollador | Gerente de producto | 5 minutos | Prepara y envía un correo electrónico a tu desarrollador con instrucciones y tareas para:<ul><li>Integración de SDK / API</li><li>Mapeo de eventos in-app</li></ul>Estos se pueden encontrar en la pestaña <Anchor target="_blank" href="https://hq1.appsflyer.com/onboarding/apps">Integrar el SDK</Anchor> del asistente para agregar una aplicación. |
| Implementación por desarrollador | Desarrolladores de aplicaciones | 3 horas | Recibe el correo electrónico del marketer con instrucciones y tareas para la integración del SDK y el mapeo de eventos in-app.<br /><br />Impleméntalo automáticamente para Android e iOS utilizando el <Anchor target="_blank" href="https://dj.dev.appsflyer.com/?utm_source=dashboard&utm_medium=app-onbrd-mail-a">AppsFlyer Dev Journey</Anchor> o manualmente utilizando los enlaces a continuación.<br /><br />Recursos de AppsFlyer para tus desarrolladores:<ul><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk">Android</Anchor></li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk">apps de iOS,</Anchor></li><li>Unity</li><li><Anchor target="_blank" href="/marketers/es/docs/windows-sdk-integration-for-developers">Windows Phone</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/other-platforms">Otras plataformas</Anchor></li></ul> |
| <Anchor target="_blank" href="/marketers/es/docs/testing-the-sdk-integration-for-marketers">Pruebas de integración</Anchor> | Gerente de producto/  <br />Desarrolladores de aplicaciones | 1 hora | Puedes probar la integración de tu SDK antes o después de que tu aplicación esté activa en la tienda de aplicaciones. Puedes utilizar aplicaciones de depuración para mantener limpios los datos de tu aplicación.<br /><br />Solo para aplicaciones de Android e iOS: Asegúrate de <Anchor target="_blank" href="/marketers/es/docs/registering-test-devices">registrar tus dispositivos de prueba</Anchor>. |
| Lanza la nueva versión de la aplicación | Gerente de producto | 1 hora | <Anchor target="_blank" href="/marketers/es/docs/preparing-for-the-app-store-review-nutrition-labels">Prepárate para la revisión de la App Store de iOS</Anchor>. |

**Resultado:** Tus aplicaciones están listas para la atribución de instalación, la medición de eventos in-app y otras funcionalidades de AppsFlyer que no requerirán recursos de desarrollo adicionales.

<div id="step-3-attribution-setup" />

## Paso 3: Configuración de atribución

Completa los siguientes pasos para cada aplicación definida en AppsFlyer en el [Paso 1: Configuración de la aplicación](/docs/getting-started-onboarding-for-marketers#paso-1-configuración-de-la-aplicación):

| Paso | Propietario | Hora | Comentarios |
| --- | --- | --- | --- |
| Configura fuentes de medios **de pago** para la atribución en AppsFlyer | Gerente de producto/  <br />Marketer | 15 minutos por fuente de medios | Saber más sobre cómo atribuir <Anchor target="_blank" href="/marketers/es/docs/self-reporting-networks-srns">redes de autoreporte</Anchor> (SRN), específicamente:<ul><li><Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-integration-setup-for-advertisers">Anuncios de Google</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/meta-ads-integration-setup">Meta Ads</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/apple-ads-integration-setup">Anuncios en la búsqueda de Apple</Anchor></li><li>GMP (DoubleClick)</li></ul>Saber más sobre cómo atribuir ad networks que no son SRN:<ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">Otros partners integrados</Anchor></li><li>Estructura y parámetros de <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">enlace de atribución</Anchor> de AppsFlyer</li></ul> |
| Utiliza OneLink para atribuir fuentes de medios **propias**: sitios web móviles, redes sociales, invitaciones de usuarios y más | Gerente de producto | 1 hora | Saber más sobre las <Anchor target="_blank" href="/marketers/es/docs/onelink-guide#opciones-adicionales">soluciones basadas en OneLink</Anchor> para tus casos de uso de medios propios |
| Implementación de desarrollador de medios propios | Desarrolladores de aplicaciones | 0-6,5 horas (dependiendo de las soluciones implementadas) | Para desarrolladores: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/getting-started-1">Empezando con Deep Linking</Anchor> |
| Configura ventanas de atribución | Gerente de producto | 2 minutos por fuente de medios | Saber más: <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows">Explicación de las ventanas de lookback por click y view-through</Anchor> |
| [Opcional] Habilita campañas de retargeting | Gerente de producto | 2 minutos | Activa el Retargeting en la página de Configuración de la aplicación.<br /><br />Saber más: <Anchor target="_blank" href="/marketers/es/docs/retargeting-attribution-guide">Guía de retargeting</Anchor> |

**Resultado:** Todas las fuentes de medios que atraen tráfico a tus aplicaciones se atribuyen cada vez que los usuarios nuevos o recurrentes interactúan con ellos.

<div id="step-4-additional-setup" />

## Paso 4: Configuración adicional

Completa los siguientes pasos para cada aplicación definida en AppsFlyer en el [Paso 1: Configuración de la aplicación.](/docs/getting-started-onboarding-for-marketers#paso-1-configuración-de-la-aplicación)

Ciertos pasos pueden ser obligatorios para cumplir con tus objetivos comerciales.

| Paso | Propietario | Recursos adicionales |
| --- | --- | --- |
| Optimiza las campañas de adquisición de usuarios registrando los ingresos | Gerente de producto/  <br />Desarrolladores | <ul><li><Anchor target="_blank" href="/marketers/es/docs/legacy-receipt-validation-for-in-app-purchases">Validaciones de compras in-app</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/roi360-guide-ad-revenue-attribution">Monetización de anuncios</Anchor></li><li>Suscripciones de usuarios</li></ul> |
| Conoce los métodos para agregar y ver datos de costos de marketing | Gerente de producto | <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview">ROI360—vista general de la agregación de costos</Anchor> |
| Configura otras <Anchor target="_blank" href="/marketers/es/docs/3rd-party-platforms">plataformas de third-party</Anchor> con las que funciona tu aplicación | Gerente de producto/  <br />Desarrolladores | <ul><li><Anchor target="_blank" href="/marketers/es/docs/mparticle-integration-with-appsflyer">mParticle</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/segment-integration">Segment</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/mixpanel-integration-with-appsflyer">Mixpanel</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/amplitude-integration-with-appsflyer">Amplitude</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/adobe-analytics-integration-with-appsflyer">Adobe Analytics</Anchor> (Omniture)</li><li><Anchor target="_blank" href="/marketers/es/docs/braze-formerly-appboy-integration-with-appsflyer">Braze</Anchor></li></ul> |
| Echa un vistazo a estas funciones premium de AppsFlyer que pueden ahorrarte tiempo y dinero. | Gerente de producto | <ul><li><Anchor target="_blank" href="/marketers/es/docs/audiences-guide">Audiencias</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/pivot-table-user-metrics">Tabla dinámica</Anchor></li><li><Anchor target="_blank" href="/marketers/es/docs/data-locker-for-marketers">Casillero de datos</Anchor></li></ul> |
| Protege tus campañas del fraude y el targeting erróneo | Gerente de producto | <ul><li><Anchor target="_blank" href="/marketers/es/docs/protect360-anti-fraud-guide">Protect360: solución antifraude</Anchor></li><li>Usa las <Anchor target="_blank" href="/marketers/es/docs/implement-validation-rules-to-prevent-fraud">reglas de validación</Anchor> para asegurarte de que las campañas no tengan objetivos erróneos.</li></ul> |
| Implementa la API de servidor a servidor para los eventos in-app reportados fuera de la aplicación | Gerente de producto/  <br />Desarrolladores | <Anchor target="_blank" href="/marketers/es/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S REST API</Anchor> |
| Mide las tasas de desinstalación de tus fuentes de medios | Gerente de producto/  <br />Desarrolladores | Medición de desinstalaciones |
| Consigue una vista unificada de las trayectorias de los clientes en todos los canales, plataformas y dispositivos | Gerente de producto/  <br />Desarrolladores | <Anchor target="_blank" href="/marketers/es/docs/people-based-attribution-pba-overview">Atribución people-based (PBA)</Anchor> |
| Asegurar el cumplimiento de las regulaciones de privacidad: GDPR, CCPA, etc. | Gerente de producto/  <br />Desarrolladores | Permitir a los usuarios <Anchor target="_blank" href="/marketers/es/docs/apply-privacy-preserving-sdk-methods">excluirse</Anchor> de la atribución. |

<div id="enrich-your-knowledge" />

## Enriquece tus conocimientos

Recomendado para todos los usuarios de AppsFlyer:

| Paso | Hora |
| --- | --- |
| Familiarízate con el dashboard general de AppsFlyer | 15 minutos |
| Explora la diferencia entre los datos de <Anchor target="_blank" href="/marketers/es/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">lifetime value (LTV) y los datos de actividad</Anchor> en AppsFlyer (resolviendo el misterio de por qué el resumen de eventos in-app difiere entre los dashboards general y de actividad) | 15 minutos |
| Comprende el <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model">modelo de atribución</Anchor> de AppsFlyer | 30 minutos |
| Saber más sobre <Anchor target="_blank" href="/marketers/es/docs/aggregated-and-analytics-reporting-overview">análisis y herramientas de reportes agregadas</Anchor> | 30 minutos |
| Saber más sobre <Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-overview">reportes de raw data</Anchor> | 30 minutos |

<div id="related" />

## Relacionado

<div id="tip-1" />

> 👍 **Consejo**
>
> ¿Eres nuevo en UA (adquisición de usuarios)? Aprende <Anchor target="_blank" href="https://www.appsflyer.com/resources/ecommerce/getting-started-user-acquisition-apps-complete-guide/">todo sobre</Anchor> los desafíos principales y elementos esenciales de la planificación, ejecución y optimización continua de tus esfuerzos de adquisición de usuarios.

<div id="note" />

> 📘 **Nota**
>
> ¿Eres nuevo en AppsFlyer pero no eres un marketer? ¡No te preocupes!
> Elige la guía para ti a continuación y comienza:
>
> * <Anchor target="_blank" href="/partners/es/docs/getting-started-agency-onboarding">Primeros pasos para agencias</Anchor>
> * <Anchor target="_blank" href="/partners/es/docs/getting-started-onboarding-guide-for-ad-networks">Primeros pasos para ad networks</Anchor>

<div data-zendesk-anchors="introduction=introducci%C3%B3n 01H8BD2FJ6TQ5FP9625MNP2B3Z=introducci%C3%B3n step-1-account-setup=configuraci%C3%B3n-de-la-cuenta 01H8BD2FJ6E8KZW41V04SBDQPQ=configuraci%C3%B3n-de-la-cuenta 01H8BD2FJ6A39JB8J0PQ3EY52N=consejo app-onboarding=onboarding-de-la-aplicaci%C3%B3n 01H8V6FS97NTTF1VPQQDZQT973=onboarding-de-la-aplicaci%C3%B3n step-2-app-setup=paso-1-configuraci%C3%B3n-de-la-aplicaci%C3%B3n 01H8BD2FJ61S3Z22CD01H6F39E=paso-1-configuraci%C3%B3n-de-la-aplicaci%C3%B3n step-3-sdk-integration=paso-2-integraci%C3%B3n-de-sdk--api 01H8BD2FJ6CY53QXVB5QC98KTT=paso-2-integraci%C3%B3n-de-sdk--api step-4-attribution-setup=paso-3-configuraci%C3%B3n-de-atribuci%C3%B3n 01H8BD2FJ6Q8R83FV0XS5B93B3=paso-3-configuraci%C3%B3n-de-atribuci%C3%B3n step-5-additional-setup=paso-4-configuraci%C3%B3n-adicional 01H8BD2FJ76WD0MRCJXZH8XABN=paso-4-configuraci%C3%B3n-adicional enrich-your-knowledge=enriquece-tus-conocimientos 01H8BD2FJ7ZV0ZYHQZ8DBTTFFK=enriquece-tus-conocimientos related=relacionado 01H8BD2FJ748GFC4VJWWYGGN1K=relacionado 01H8BD2FJ712NGA534TCSWQGR8=consejo-1 01H8BD2FJ7PRJAA1K8MESRK7VA=nota" />
