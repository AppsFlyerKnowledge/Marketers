---
title: Dashboard - Estado de costos e ingresos por publicidad
metadata:
  keywords:
    - ad revenue
    - cost
    - Advertisers
    - Agencies
    - Xpend
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - Agencies
    - ROI360
  created_at: '2020-12-23T12:52:57Z'
  edited_at: '2026-08-22T00:01:04Z'
  id: 360016789458
  locale: es
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/es/articles/360016789458
---
> **De un vistazo:** Los anunciantes y las agencias pueden consultar el estado de las integraciones de costos e ingresos por publicidad.

<div id="cost-and-ad-revenue-integration-status" />

## Estado de la integración de costos e ingresos por publicidad

* El dashboard muestra el estado operativo actual de tus integraciones de costo/ingresos por publicidad.
  * Los anunciantes ven los estados de todas las aplicaciones, fuentes de medios y agencias de su cuenta.
  * Las agencias ven los estados de todas las aplicaciones y fuentes de medios con las que trabajan.
* Las integraciones de ingresos por publicidad se muestran según la fuente de medios de ingresos por publicidad, no según la fuente de medios de adquisición de usuarios.
* En las integraciones que requieren acciones correctivas, se muestra la acción requerida.
* Para ver el estado de costos e ingresos por anuncios, en AppsFlyer, desde el menú lateral, selecciona **Configuración** > **Estado de costos e ingresos por anuncios**.
* La imagen y la tabla siguientes desglosan los componentes del dashboard.

<div id="cost--ad-revenue-status-dashboard" />

#### Dashboard de estado de costo e ingresos por anuncios

[![cost_and_ad_revenue_status_dashboard.jpg](https://files.readme.io/da713daae6c7044e8e4f32274520961e1b43c183d8e4cb95f58854cb614efb39-360016000898.jpg)](https://files.readme.io/da713daae6c7044e8e4f32274520961e1b43c183d8e4cb95f58854cb614efb39-360016000898.jpg)

| Sección | Nota |
| --- | --- |
| <span id="a-filters"></span>A. Filtros | <ul><li>Submotivo de bloqueo</li><li>Agencias</li><li>Nombre de la app</li><li>Estado</li><li>Tipo de integración (costo o ingresos por publicidad)</li><li>Problema</li></ul> |
| <span id="b-headline-metrics"></span>D. Métricas principales | <ul><li>**Total de integraciones**: número de aplicaciones/partners para las que la integración está habilitada, independientemente del estado. Por ejemplo, si tienes una aplicación Android y otra iOS, ambas integradas con Meta ads, el total de integraciones es dos.</li><li>**Acción requerida**: número de aplicaciones y fuentes de medios de tu cuenta con problemas de API que deben actualizarse.</li><li>**Advertencia**: número de integraciones para las que no hay datos o que están experimentando un error temporal de red.</li><li>**En espera de sincronización**: número de integraciones que están conectadas, pero a la espera de que se extraigan los datos. Puede tardar hasta 24 horas en verse los datos en AppsFlyer.</li><li>**Activo**: número de partners con las API de costo/ingresos por publicidad sincronizadas y operativas.</li></ul> |
| <span id="c-status"></span>C. Estado | Cada estado tiene una tabla independiente en el dashboard con todas las integraciones correspondientes. Para ver las definiciones de los estados, consulta las métricas principales anteriores.<ul><li>**Acción requerida**</li><li>**Advertencia**</li><li>**Esperando sincronización**</li><li>**Activo**</li></ul> |
| <span id="d-columns"></span>D. Columnas | Cada sección de estado contiene varias columnas:<ul><li>Nombre de la app</li><li>Aplicación: aplicación con integración de API de datos de costo o ingresos por publicidad.</li><li>Última sincronización: el momento más reciente en que se recibieron los datos.</li><li>Tipo de integración:<ul><li>Coste</li><li>Ingresos por anuncios (atr.): Significa que los ingresos por anuncios se atribuyen a la fuente de medios de adquisición de usuarios</li><li>Ingresos por anuncios (agr.): Significa que los ingresos por anuncios se agregan en función de la fuente de monetización (la fuente de medios que mostró el anuncio)</li></ul></li><li>Costo/ingresos de la campaña (según la API): costo de la campaña o ingresos por anuncios de la aplicación por fuente de medios durante los últimos 7 días.</li><li>Problema: Consulta la siguiente lista.</li><li>Acción: Acción necesaria para habilitar los datos si la integración de la API tiene algún problema. Al hacer clic en **Reconnect** se lleva a cabo la acción requerida.</li></ul> |
| <span id="e-problem"></span>E. Problema | <ul><li>**Credenciales no válidas**: AppsFlyer no puede obtener datos a través de la API porque las credenciales no son válidas. Vuelve a conectarte utilizando las credenciales correctas.</li><li>**En espera de la primera sincronización**: En espera de la extracción inicial de datos del partner. Vuelve a consultar en varias horas.</li><li>**No habilitado**: El anunciante o la agencia recibió tráfico y más de 20 instalaciones de este partner en los últimos 28 días, pero la integración de costos no está habilitada. Habilita la integración de costos.</li><li>**Sin datos**: La integración está activa, pero el partner no devuelve datos.<ul><li>Para recibir una notificación cuando se produzca el problema, habilita la alerta por correo electrónico de fallo de datos de ingresos por anuncios.</li></ul></li><li>**No disponible**: La integración está activa, pero no hay datos de costos del partner de los últimos 30 días porque no hay campañas activas.</li><li>**Problema de red**: Hay un problema temporal con este partner. Vuelve a consultar en varias horas.</li><li>**Error general**: Hay un problema temporal con este partner. Contactar con el soporte.</li><li>**Versión antigua de la API**: Revisa la integración y actualiza las credenciales de la API.</li><li>**Configuración no válida**: No se encontró el nombre del evento configurado para la atribución de ingresos. Revisa la configuración y actualiza el nombre de la fuente del evento.</li><li>**Integración deshabilitada**: Vuelve a conectar tu integración.</li><li>**Restringido por el partner**: Tu cuenta no está habilitada en el sistema del partner para obtener el costo. Póngase en contacto con el socio.</li><li>**Integración suspendida**: La integración del partner tuvo el estado de advertencia durante 30 días consecutivos. Vuelve a conectarte con el partner.<ul><li>Para recibir una notificación cuando se produzca el problema, habilita la alerta por correo electrónico de integración suspendida de ingresos por anuncios.</li><li>**Nota**: Después de 180 días, los Partners con una integración suspendida no se muestran en el dashboard de estado.</li></ul></li><li>**Incompatibilidad entre la API y la atribución**: La API del partner no devuelve datos de costo coincidentes. Esto sucede porque:<ul><li>Se integró una cuenta de anuncios de socio diferente al iniciar sesión en el socio a través de AppsFlyer (por ejemplo, otra cuenta de anuncios de Meta). Compruebe que ha conectado la cuenta de publicidad de socio correcta.</li><li>Uno de los campos de credenciales en la integración de costes del socio es incorrecto. Por ejemplo, el ID del paquete. Revisa y corrige las credenciales de integración.</li></ul></li><li>**Error de configuración**: La API del partner no devuelve datos. Esto sucede porque:<ul><li>Sus campañas están en pausa y no hay datos.</li><li>Se integró una cuenta de anuncios de socio diferente al iniciar sesión en el socio a través de AppsFlyer (por ejemplo, otra cuenta de anuncios de Meta). Compruebe que ha conectado la cuenta de publicidad de socio correcta.</li><li>Uno de los campos de credenciales en la integración de costes del socio es incorrecto. Por ejemplo, el ID del paquete. Revisa y corrige las credenciales de integración.</li></ul></li></ul> |

<div data-zendesk-anchors="cost-and-ad-revenue-integration-status=estado-de-la-integraci%C3%B3n-de-costos-e-ingresos-por-publicidad h_01HKW10FWXCZ1QFFJA1FTYH50F=estado-de-la-integraci%C3%B3n-de-costos-e-ingresos-por-publicidad cost-ad-revenue-status-dashboard=dashboard-de-estado-de-costo-e-ingresos-por-anuncios h_01HKW10FWXGWHSQKFTHRDHGWSP=dashboard-de-estado-de-costo-e-ingresos-por-anuncios" />
