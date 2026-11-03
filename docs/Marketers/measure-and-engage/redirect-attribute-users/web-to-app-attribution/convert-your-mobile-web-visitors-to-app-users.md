---
title: Convertir a los visitantes de la web móvil en usuarios de la aplicación.
metadata:
  keywords:
    - OneLink
    - Advertisers
    - Smart Banner
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2019-03-19T08:54:10Z'
  edited_at: '2026-09-09T00:33:43Z'
  id: 360001237818
  locale: es
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/es/articles/360001237818
---
> **De un vistazo:** Utiliza tu sitio web móvil para convertir a los visitantes de la web móvil en nuevos usuarios de la aplicación móvil.

## Soluciones móviles de atribución de la web a la aplicación

![Web_to_app_.png](https://files.readme.io/deb9ba0dfd18671666e9f06dc27440759844ea365988f80e05ce7ac2817a7299-46646996021777.png)

### Beneficios de las campañas de la web a la aplicación

El uso de campañas de la web a la aplicación te ayuda a:

* Convierte a los visitantes de la web móvil en usuarios de la aplicación. [Consulta también Instalaciones asistidas por web.](/docs/convert-your-mobile-web-visitors-to-app-users#instalaciones-asistidas-por-web)
* Usar páginas web o de aterrizaje para aumentar la comprensión de tus usuarios sobre tu producto/servicio antes de que descarguen la aplicación.
* Encontrar tus páginas web/de aterrizaje de mejor y menor conversión.
* Crear ofertas más específicas para el retargeting de tus usuarios web móviles, que también son usuarios de tu aplicación.
* Enlazar profundamente sin problemas a los usuarios desde el sitio a una página específica de la aplicación.

### Soluciones de atribución

<Embed title="Convertir a los visitantes de la web móvil en usuarios de la aplicación." typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/kv67fa3rvn" providerUrl="https://fast.wistia.com" />

Para los usuarios móviles de la web a la aplicación, dado que hay dos clics (el primero que dirige a la página web y el segundo que dirige desde la página web a la tienda de aplicaciones), la atribución y los enlaces profundos son problemáticos. Los usuarios que finalmente descargan la aplicación pueden ser atribuidos erróneamente, o atribuidos como orgánicos, incluso si el primer clic proviene de una red de publicidad, clic de Google o fuente de medios propia. 

AppsFlyer ofrece las siguientes soluciones para una atribución precisa de la web a la aplicación:

<Anchor target="_blank" href="/marketers/es/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banners</Anchor>:

* Añade el SDK web de Smart Banner a tu sitio web y, a continuación, crea banners dinámicos en el dashboard de AppsFlyer.
* Cuando un usuario hace clic en una URL y es dirigido a tu sitio web móvil, aparece un Smart Banner con un CTA para descargar la aplicación de la tienda de aplicaciones.
* La URL de Smart Banner se rellena en función de los parámetros y UTM en el enlace entrante y se utiliza para la atribución.

<Anchor target="_blank" href="/marketers/es/docs/onelink-smart-script-overview">OneLink Smart Script</Anchor>:

* Ejecuta un script en tu sitio web móvil.
* Cuando un usuario hace clic en una URL y es dirigido a tu sitio web móvil, aterriza en una página con botones que le instan a descargar tu aplicación.
* El script en la página web genera dinámicamente las URL salientes en estos botones en función de la URL entrante, que se utiliza para la atribución.
* Reemplaza el <Anchor target="_blank" href="/marketers/es/docs/deprecated-mobile-landing-page-attribution-script">script</Anchor> de atribución de la página de aterrizaje móvil anterior. Si aún estás usando el script anterior, debes migrar.

Ambas soluciones acortan la brecha entre las URL de campaña entrantes a tu sitio web y la URL saliente de OneLink creada para la atribución correcta y el enlace profundo de los usuarios del sitio web móvil.

En la siguiente tabla se comparan las dos soluciones para que puedas elegir e implementar la más adecuada a tus necesidades. **Nota**: Se pueden implementar ambas soluciones y utilizarlas en tándem.

#### Smart Banner vs. OneLink Smart Script

| Característica | Banners inteligentes | Smart Script de OneLink |
| --- | --- | --- |
| Fuentes de medios compatibles | Todas las fuentes de medios compatibles:<ul><li>Enlaces entrantes con parámetros pid o UTM (incluidas las SRN)</li><li>Visitantes orgánicos</li></ul> | Todas las fuentes de medios compatibles:<ul><li>Enlaces entrantes (incluidas las SRN)</li><li>Visitantes orgánicos</li></ul> |
| Cambiar parámetros de enlace de atribución | Cambio rápido en el acceso al panel de control/asistente de AppsFlyer. | Requiere la implementación del desarrollador en el script, pero es totalmente flexible. |
| Usuarios de escritorio | No se admite | Compatible |
| Configuración de marketers | Utiliza el asistente para configurar Smart Banners. | Decide los parámetros y valores que se van a establecer en las URL entrantes y salientes (se suministran los valores predeterminados). |
| Configuración del desarrollador | <ul><li>Integra el SDK web.</li><li>Alternativamente, puede ser <Anchor target="_blank" href="/marketers/es/docs/smart-banners-website-code-implementation-for-marketers">implementado por el marketer</Anchor>.</li></ul> | <ul><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script-v2web-to-app-url-generator">Implementa el script</Anchor> que crea la URL saliente.</li><li>Alternativamente, puede ser implementado por el marketer a través de un <Anchor target="_blank" href="/marketers/es/docs/set-up-smart-script-to-convert-web-visitors#configuración-de-smart-script-de-onelink">administrador de etiquetas</Anchor>.</li></ul> |
| Configuración de campaña en curso | Para redes de publicidad de clic, configura el enlace de la campaña web a la aplicación. | Sigue las instrucciones por tipo de fuente de medios. |
| Disponibilidad | Disponible con un plan de suscripción de pago. | Disponible con un plan de suscripción de pago. |

**Nota:** Smart Banners y OneLink Smart Script solo están disponibles con <Anchor target="_blank" href="/marketers/es/docs/account-management-plans-payments-and-billing#appsflyer-plans">planes de suscripción</Anchor> pagados aptos. Depende de tu plan de cuenta de AppsFlyer

### Instalaciones asistidas por web

Las instalaciones asistidas por web ocurren cuando los usuarios descargan tu app, pero no necesariamente por una campaña específica. Antes de que descarguen tu app, visitaron tu sitio web por cualquier motivo, quizá días o semanas antes. Usa <Anchor target="_blank" href="/marketers/es/docs/people-based-attribution-pba-overview">PBA</Anchor> Web-Assisted Installs para ver un desglose general de estos *puntos de contacto de asistencia* que finalmente conducen a la instalación de la app.  

#### Soluciones móviles de atribución de la web a la aplicación

| Característica | Soluciones móviles de la web a la aplicación | Instalaciones asistidas por web (PBA) |
| --- | --- | --- |
| Finalidad | Te brinda herramientas para ejecutar campañas diseñadas para convertir directamente a los visitantes de la web en usuarios de la aplicación, a la vez que atribuye la fuente de medios responsable de la visita web. | Consulta un desglose de las instalaciones precedidas de visitas a la web. |
| Flujos | Flujo directo de la web a la descarga de la aplicación. | Flujos directos, diferidos o desarticulados. Las instalaciones pueden estar precedidas por una visita a la web (hasta 30 días). |
| Dispositivos de usuario | Mismo dispositivo | Mismo o multidispositivo |

| Caducado | Observaciones |
| --- | --- |
| Versión del SDK |  |
| Tipo de coincidencia | `preload_rfr` |
| Panel de vista general | Los engagements cuentan como clics en los reportes agregados y dashboards. Se agregan a nivel de partner de precarga (fuente de medios) y campaña. |
| Reportes de raw data | <ul><li>Los engagements están disponibles en los reportes de clics solo a través de Data Locker.</li><li>En los reportes de instalación, los eventos de precarga NO se encuentran en la URL original debido a las restricciones de privacidad de Samsung.</li><li>Pueden identificarse en el parámetro `af_engagement_type` como `preload`.</li></ul> |

<div data-zendesk-anchors="mobile-webtoapp-attribution-solutions=soluciones-m%C3%B3viles-de-atribuci%C3%B3n-de-la-web-a-la-aplicaci%C3%B3n h_01KFAFC9DFAES0JGPVCQQV3GAR=soluciones-m%C3%B3viles-de-atribuci%C3%B3n-de-la-web-a-la-aplicaci%C3%B3n benefits-of-webtoapp-campaigns=beneficios-de-las-campa%C3%B1as-de-la-web-a-la-aplicaci%C3%B3n h_01KFAFC9DFJ7QWJ6JN60NKVPZ3=beneficios-de-las-campa%C3%B1as-de-la-web-a-la-aplicaci%C3%B3n attribution-solutions=soluciones-de-atribuci%C3%B3n h_01KFAFC9DFH4JH6DE4KZE424Q3=soluciones-de-atribuci%C3%B3n h_01KFAFC9DFGCYRS1C5SVX1ZSCC=smart-banner-vs-onelink-smart-script webassisted-installs=instalaciones-asistidas-por-web h_01KFAFC9DG4MCVQ5YRGVRQ6K5P=instalaciones-asistidas-por-web webtoapp-solutions-vs-webassisted-installs=soluciones-m%C3%B3viles-de-atribuci%C3%B3n-de-la-web-a-la-aplicaci%C3%B3n-1 h_01KFAFC9DG4YJ55BYQH9TQ2YPQ=soluciones-m%C3%B3viles-de-atribuci%C3%B3n-de-la-web-a-la-aplicaci%C3%B3n-1" />
