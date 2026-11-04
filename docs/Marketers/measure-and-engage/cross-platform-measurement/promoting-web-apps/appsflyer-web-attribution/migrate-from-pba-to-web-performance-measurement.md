---
title: Migra de PBA a medición del rendimiento web
metadata:
  keywords:
    - Developers
    - Marketers
    - Web Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
  created_at: '2026-07-26T11:53:06Z'
  edited_at: '2026-09-09T00:21:43Z'
  id: 49156441281425
  locale: es
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/es/articles/49156441281425
---
> **At a glance:** People-Based Attribution (PBA) está siendo reemplazado por Web Performance Measurement, la solución mejorada de medición web de AppsFlyer. En este artículo se explica qué cambia, los pasos de la migración y la correspondencia completa de campos para tus reportes e integraciones del lado del servidor.

<div id="why-were-upgrading-your-web-measurement" />

## Por qué estamos mejorando tu medición web

La medición web importa más que nunca. El sitio web es donde muchos de tus usuarios convierten y donde comienza el recorrido hacia tu aplicación móvil. No es solo una landing page; es un funnel de adquisición completo de flujos de cuestionarios, onboarding personalizado, muros de pago y tiendas web que a menudo captan a usuarios con mayor intención a un menor costo de adquisición.

AppsFlyer está llevando la medición web al mismo nivel que la móvil. People-Based Attribution (PBA), el producto web heredado, está siendo reemplazado por Web Performance Measurement, construido sobre el motor principal de atribución y el modelo de datos unificado de AppsFlyer. Web Performance Measurement iguala todo lo que hace PBA hoy y además añade:

* **Una única fuente de verdad**, medición web y de aplicación móvil en un solo lugar, con agregación de costo, postbacks de optimización y Optimización creativa, todo junto.
* **Mejores decisiones de presupuesto**, atribución flexible que se adapta a la lógica de tu negocio para que apuestes más por las campañas que realmente funcionan.
* **ROAS mejorado**, postbacks de optimización enriquecidos para tus ad networks y una configuración completa del lado del servidor que mide más conversiones, para que las redes puedan optimizar con mejores señales.
* **ROI real entre plataformas**, mide cada viaje de usuario en la web, la aplicación y cualquier plataforma.
* **Reportes simples y unificados**, un dashboard y un conjunto de reportes de datos para cada plataforma, actualizados cada hora.

> 📘 **Note**
>
> No necesitas sustituir tu SDK web. Web Performance Measurement usa el mismo SDK, sin cambios de código en tu sitio web. El esfuerzo que implica el resto del cambio varía según cómo recibas actualmente tus datos: a través del dashboard, Data Locker o la API de servidor a servidor (S2S).

<div id="comparing-pba-and-web-performance-measurement" />

## Comparación entre PBA y Web Performance Measurement

En esta sección se comparan PBA y Web Performance Measurement de dos formas: las capacidades generales y la resolución de la fuente de tráfico.

<div id="web-performance-measurement-vs-pba" />

### Web Performance Measurement frente a PBA

La tabla de abajo compara las capacidades de PBA y Web Performance Measurement en datos, reportes y atribución.

<table><tbody><tr><td>Capacidad</td><td>Description</td><td>PBA</td><td>Medición del rendimiento web</td></tr><tr><td colspan="4"><strong>Tus datos</strong></td></tr><tr><td>Datos actualizados</td><td>¿Con qué rapidez están disponibles los datos para reportar</td><td> <span>✗</span> A diario</td><td> <span>✓</span> Reportes por hora, aproximadamente 2 horas de frescura de los datos</td></tr><tr><td>Modelo de datos</td><td>Alineación del esquema con los datos de atribución móvil</td><td> <span>✗</span> Diferente de Móvil</td><td> <span>✓</span> Alineado con Móvil, fácil de unir y analizar</td></tr><tr><td colspan="4"><strong>Reportes</strong></td></tr><tr><td>Panel de actividades</td><td>Dashboard basado en el tiempo del evento</td><td> <span>✓</span> Con soporte</td><td> <span>✓</span> Con soporte</td></tr><tr><td>Panel de control de la cohorte</td><td>Analiza el rendimiento por cohorte de adquisición a lo largo del tiempo</td><td> <span>✗</span> Sin soporte</td><td> <span>✓</span> Con soporte</td></tr><tr><td>Raw data de Data Locker</td><td>Acceso a los Datos de atribución sin procesar mediante la exportación de Data Locker</td><td> <span>✓</span> Con soporte</td><td> <span>✓</span> Con soporte</td></tr><tr><td>Granularidad a nivel de anuncio</td><td>Desglose del reporte desde la campaña hasta el nivel de Anuncio</td><td> <span>✗</span> Solo en el dashboard, no en raw data</td><td> <span>✓</span> Granularidad completa de campaña tanto en el dashboard como en raw data</td></tr><tr><td>LTV cross-platform</td><td>Unifica los viajes del Usuario web y Móvil en un solo LTV</td><td> <span>✗</span> Sin soporte</td><td> <span>✓</span> Con soporte</td></tr><tr><td colspan="4"><strong>Costo y señales</strong></td></tr><tr><td>Costo web</td><td>Recopila y crea reportes sobre el gasto en anuncios de campañas web</td><td> <span>✗</span> No compatible</td><td> <span>✓</span> Con soporte</td></tr><tr><td>Postbacks de optimización</td><td>Envía señales de optimización de vuelta a las ad networks</td><td> <span>✗</span> No compatible</td><td> <span>✓</span> Con soporte</td></tr><tr><td colspan="4"><strong>Implementación</strong></td></tr><tr><td>SDK web (Pixel)</td><td>SDK del lado del cliente para medir visitas web y eventos</td><td> <span>✓</span> Con soporte</td><td> <span>✓</span> El mismo SDK, sin cambios de código necesarios</td></tr><tr><td>Soporte de S2S</td><td>Medición completa del lado del servidor para visitas y eventos</td><td> <span>✗</span> Solo eventos</td><td> <span>✓</span> Eventos y visitas. Con soporte para una implementación completa del lado del servidor.</td></tr><tr><td colspan="4"><strong>Motor de atribución</strong></td></tr><tr><td>Ventanas de atribución</td><td>Ventanas configurables de lookback, atribución, re-engagement e inactividad</td><td> <span>✗</span> Solo ventana de lookback de clics</td><td> <span>✓</span> 5 ventanas configurables (control total)</td></tr><tr><td>Evento de UA personalizado</td><td>Define qué evento cuenta como un evento de adquisición de usuarios (UA) más allá de la primera visita</td><td> <span>✗</span> Solo la primera visita</td><td> <span>✓</span> Cualquier evento personalizado (por ejemplo, registro, compra)</td></tr><tr><td>UA vs. retargeting</td><td>Crédito independiente para la nueva adquisición vs. re-engagement</td><td> <span>✗</span> No existe el concepto de UA; los eventos se atribuyen al último Toque</td><td> <span>✓</span> Vistas específicas de UA y retargeting con crédito de atribución dual</td></tr></tbody></table>

<div id="traffic-source-resolution-pba-vs-web-performance-measurement" />

### Resolución de la fuente de tráfico, PBA VS medición del rendimiento web

Si los valores de fuente de medios, canal o campaña difieren de los que notificó PBA, aquí tienes el motivo. Ambos usan el mismo enfoque subyacente: resuelven la fuente de medios a partir de los parámetros de la URL y el referente en la visita web, recorriendo una lista de prioridades hasta que prevalece la primera coincidencia. Pero varias reglas cambiaron, y esos cambios modifican los valores que ves en los reportes, según las <Anchor target="_blank" href="/marketers/es/docs/pba-media-source-attribution-rules">reglas de Atribución de la Fuente de medios de PBA</Anchor> y <Anchor target="_blank" href="/marketers/es/docs/about-traffic-source-resolution">Acerca de la resolución de la fuente de tráfico</Anchor>.

<Accordion title="Valores de fuente de medios cambiados de nombre">

| Disparador | Valor de PBA | Nuevo valor |
| --- | --- | --- |
| Google display/video (utm\_source=Google + utm\_medium= cpm / display/banner/video/listing) | `doubleclick_int` | `dv360_int` |
| Twitter mediante UTM (twitter + cpc) | Anuncios X | Twitter |

Web Performance Measurement también reasigna más valores de PID a nombres para mostrar; por ejemplo, `iossearchads_int` a Apple Search Ads, `metweb_int` a Facebook Ads, `twitterweb_int` a Twitter, `tiktokweb_int` a `tiktokglobal_int` y `snapweb_int` a `snapchat_int`. Los reportes basados en los valores sin procesar antiguos deben contemplar los nuevos.

</Accordion>

<Accordion title="Se amplía la cobertura de los ID de clic y se elimina dclid">

PBA resolvía tres ID de clic: `gclid` a `googleadwords_int`, `dclid` a `doubleclick_int` y `msclkid` a `bingsearch_int`.

Web Performance Measurement resuelve muchos más: `gclid`/`wbraid`/`gbraid` a `googleadwords_int`, `msclkid` a `bingsearch_int`, `twclid` a Twitter, `vmcid` a `yahoogemini_int`, `sccid` a `snapchat_int`, `li_fat_id` a `linkedin_int`, `ttclid` a `tiktokglobal_int`, `tbclid` a `taboola_int`, `ob_click_id`/`dicbo` a `outbrain_int`, `yclid` a `yandex_int` y `rdt_cid` a `reddit_int`.

> 🚧 **Important**
>
> Dos cambios de comportamiento: dclid ya no se usa por sí solo para la resolución (PBA lo resolvía como doubleclick\_int) y fbclid explícitamente no se usa.

</Accordion>

<Accordion title="Se amplían las reglas UTM personalizadas">

La asignación personalizada de `utm_source` + `utm_medium` es más amplia en Web Performance Measurement: incluye más sinónimos de medio (paid, paid\_search, paid-search, etc.) y añade cobertura para TikTok, Snapchat y Pinterest, más allá de las reglas de medio único limitadas de PBA. Si no coincide ninguna regla personalizada, ambos recurren al valor sin procesar de `utm_source`.

</Accordion>

<Accordion title="Ejemplo">

Los **valores** de canal también cambian de formato: de Direct / Organic search / Social media / Email / Ad / Referral / Other en PBA a los nuevos DIRECT / ORGANIC\_SEARCH / SOCIAL\_MEDIA / EMAIL / AD / REFERRAL / OTHER. Los filtros y las agrupaciones basados en las etiquetas antiguas deben actualizarse.

</Accordion>

<div id="migrate-to-web-performance-measurement" />

## Migra a Medición del rendimiento web

La migración tiene un paso obligatorio para todos. Después, realiza los pasos que correspondan según tu configuración de PBA.

> 📘 **Note**
>
> **Espera diferencias en las cifras (todos)**
>
> Las cifras de PBA no coincidirán exactamente con las que obtendrás después de la migración. La lógica de atribución en Web Performance Measurement es más avanzada y flexible. PBA aplicaba sus propias reglas de atribución de fuentes de medios; Web Performance Measurement utiliza una resolución mejorada de fuentes de tráfico. Consulta más abajo «Resolución de la fuente de tráfico: PBA vs. Web Performance Measurement» para saber qué valores puedes esperar. La lógica de registro de sesiones no cambia; una sesión sigue ejecutándose durante 30 minutos de actividad, el estándar del mercado.

<div id="step-1-create-a-web-app-required-everyone" />

### Paso 1. Crea una aplicación web (obligatorio para todos)

1. <Anchor target="_blank" href="/marketers/es/docs/adding-an-app-to-appsflyer#web">Crea la nueva aplicación web</Anchor> y selecciona tu clave de desarrollador web existente en el campo **Web SDK ID**. Esto mantiene el código actual de tu sitio web funcionando tal cual, sin cambios de código.
2. <Anchor target="_blank" href="/marketers/es/docs/configure-web-performance-measurement-settings">Configura los ajustes de atribución</Anchor> en la nueva aplicación.

<div id="step-2-if-you-send-events-through-the-s2s-api" />

### Paso 2. Si envías eventos a través de la API S2S

Migra a la nueva API S2S:

1. Consulta [la migración de PBA Web-S2S a la nueva API S2S](#migración-de-pba-web-s2s-a-la-nueva-api-s2s) para ver qué cambia con respecto a tu integración S2S actual de PBA, los endpoints, la autenticación y los campos de la carga útil.
2. Configura la <Anchor target="_blank" href="/marketers/es/docs/server-to-server-s2s-api-for-web-performance-measurement">nueva API S2S</Anchor> para Web Performance Measurement.
3. Actualiza tu integración del lado del servidor para enviar datos a los nuevos endpoints.

<div id="step-3-if-you-consume-pbas-raw-data-reports" />

### Paso 3. Si utilizas los Reportes de raw data de PBA

Pásate a los nuevos reportes de Data Locker. El reporte End User Events sustituye a los <Anchor target="_blank" href="/marketers/es/docs/pba-raw-data-reports">reportes Website visits y Website events de PBA</Anchor>.

1. Confirma que tienes Data Locker. Si no lo tienes, tendrás que añadirlo a tu cuenta o comprarlo.
2. Consulta [la asignación de campos de raw data](#asignación-de-campos-de-raw-data) para ver la asignación completa a nivel de campo y los campos renombrados, redefinidos o en desuso.
3. Activa el nuevo reporte con <Anchor target="_blank" href="/marketers/es/docs/export-web-performance-measurement-report-data-from-data-locker">Exportar datos de reportes de Atribución web de AppsFlyer desde Data Locker</Anchor>.
4. Haz que tu BI/ETL apunte a la nueva ubicación y a los nuevos campos del reporte. Esto se aplica tanto si tus eventos llegan a través del SDK como por S2S; ambos acaban en el mismo reporte sin procesar.

<div id="step-4-if-you-use-the-pba-brand-bundle-for-cross-platform-reporting" />

### Paso 4. Si usas el PBA Brand Bundle para reportar en multiplataforma

1. <Anchor target="_blank" href="/marketers/es/docs/product-line-group-apps-for-cross-platform-attribution">Crear una línea de producto</Anchor>.
2. Agrupa tu app web con tus otras apps en esa línea de producto para habilitar el <Anchor target="_blank" href="/marketers/es/docs/beta-user-based-cross-platform-attribution">reporte de LTV de usuario en multiplataforma</Anchor>.

<div id="capabilities-being-discontinued" />

## Capacidades que se dejarán de ofrecer

| Capacidad | Qué ha cambiado | Nota |
| --- | --- | --- |
| Ruta de conversión | Ya está obsoleto. | No aplica |
| Instalaciones asistidas por web (crédito a una campaña web que ayudó a impulsar una instalación móvil posterior) | No hay una vista específica de "instalaciones asistidas por web". | Los recorridos web-to-app se miden con Smart Script y Smart Banner. El reporte entre plataformas ofrece un análisis similar, aunque no idéntico. Al igual que PBA, se basa en el Customer User Identifier (CUID):<ul><li>Las campañas web que asistieron una instalación que antes se reportaba como orgánica ahora aparecen como adquisición de usuarios no orgánica. No son asistencias; la campaña web es la fuente de adquisición.</li><li>Campañas web que contribuyeron a una instalación no orgánica: la campaña web actúa como adquisición de usuarios y la instalación móvil como retargeting entre plataformas.</li></ul> |
| Recálculo retrospectivo | No hay recálculo retrospectivo más allá del retraso predeterminado de 30 minutos. | La atribución se finaliza después de un retraso de 30 minutos, lo que da tiempo a los usuarios a identificarse durante esa ventana. |
| Campos de raw data | Los campos relacionados con móvil están obsoletos para la web. Se cambia el nombre de algunos campos y cambian algunos valores. | Consulta [Asignación de campos de raw data](#asignación-de-campos-de-raw-data) para ver la asignación completa de campos. |
| Eventos S2S tardíos | Los eventos que llegan más de 30 minutos después del final del día UTC en el que se produjeron siguen aceptándose, pero la hora del evento se sustituye por la hora a la que AppsFlyer los recibió. | Envía los eventos en tiempo real, preferiblemente en un plazo de 30 minutos desde que se producen, en lugar de agruparlos en una única carga diaria. La atribución precisa depende de recibir los eventos cerca del momento en que se producen. Esto alinea la web con el comportamiento móvil existente. |

<div id="raw-data-field-mapping" />

## Asignación de campos de raw data

Si ya consumes los reportes de raw data de visitas al sitio web y eventos del sitio web de PBA, esto es lo que cambia. El reporte en sí pasa a Data Locker, y esta es la asignación completa, campo por campo, al nuevo reporte de eventos de usuario final, basada en los <Anchor target="_blank" href="/marketers/es/docs/pba-raw-data-reports">reportes de raw data de PBA</Anchor>.

> 📘 **Note**
>
> Los raw data de cualquier plataforma y los reportes entre plataformas solo están disponibles a través de Data Locker. Consulta el paso 3 o el paso 4 anteriores si aún no tienes Data Locker.

* **Sin cambios**, mismo nombre de campo y mismos datos.
* **Cambio de nombre**, mismos datos, nuevo nombre de columna.
* **Redefinido**, mismo nombre o uno similar, pero cambian los datos o el formato del valor (requiere atención antes de reutilizarlo).
* **Obsoleto**, sin equivalente en el nuevo reporte.

| AppsFlyer | Nota | Estado | Nuevo campo/nota |
| --- | --- | --- | --- |
| `advertising_id` | ID de publicidad (GAID) | Número con hasta 4 decimales que representa el porcentaje de impuesto recaudado. | ID de publicidad de móvil/dispositivo, unificado entre plataformas en PBA. Los reportes multiplataforma de LTV y del viaje del usuario se basan en CUID y no usan este campo. |
| `af_web_id` | ID de cookie enviado desde el SDK web | Cambio de nombre | `appsflyer_id_value`, la misma cookie web. |
| `amazon_aid` | ID de publicidad de Amazon Fire TV | Número con hasta 4 decimales que representa el porcentaje de impuesto recaudado. | ID de móvil/dispositivo, no relevante para web. |
| `android_id` | ID de dispositivo de Android | Número con hasta 4 decimales que representa el porcentaje de impuesto recaudado. | ID de móvil/dispositivo, no relevante para web. |
| `id_aplicación` | El ID de la aplicación instalada más recientemente | Obsoleto | Campo multiplataforma móvil. El identificador de la aplicación web en el nuevo reporte es `unified_app_id` («website-`{domain}`»), un concepto diferente. |
| `nombre_aplicación` | Nombre de la aplicación más reciente | Sin cambios | `app_name`. |
| `version_app` | La versión más reciente de la aplicación | Número con hasta 4 decimales que representa el porcentaje de impuesto recaudado. | Campo multiplataforma móvil, no relevante para web. |
| `appsflyer_id` | ID de AppsFlyer (instalación) | Número con hasta 4 decimales que representa el porcentaje de impuesto recaudado. | ID de instalación móvil. El nuevo `appsflyer_id_value` es la cookie web (`af_web_id`), un identificador distinto. |
| `Se establece como TRUE o FALSE.` | Marca temporal de la visita web (atribuida) | Renombrado | `event_time__attribution`, la hora del toque (engagement) atribuido. |
| `tipo_táctil_atribuido` | Tipo de punto de contacto, siempre «visita web» | Número con hasta 4 decimales que representa el porcentaje de impuesto recaudado. | Valor constante en PBA. La distinción entre visita y evento ahora está en `end_user_event_type` (SESSION / IN\_APP). |
| `id_paquete` | ID de paquete de PBA | Número con hasta 4 decimales que representa el porcentaje de impuesto recaudado. | Sustituido por la agrupación de línea de producto (web + aplicaciones móviles) en el reporte multiplataforma. |
| `campaña única` | Atribuido a la visita al sitio web | Renombrado | `campaign_name`. |
| `id_campaña` | Atribuido a la visita al sitio web | Sin cambios | `campaign_id`. |
| `Ingresos por eventos en USD` | Resuelto utilizando la dirección IP | Sin cambios | `city`. |
| `código_de_país` | Resuelto utilizando la dirección IP | Sin cambios | `country_code`. |
| `id_usuario_cliente` | Identificador de usuario del cliente (CUID) | Sin cambios | `customer_user_id`. |
| `tipo_de_dispositivo` | El tipo de dispositivo | Cambió de nombre | `device_category`, los valores difieren («Desktop» frente a «MOBILE\_PHONE» / «TV»). |
| `dma` | Resuelto utilizando la dirección IP | Sin modificar | `dma`. |
| `nombre_del_evento` | Visitas: siempre «website visit». Eventos: se envía el nombre del evento | Redefinido | Vacío en las visitas (PBA escribió «website visit»). Sin cambios para los eventos. |
| `ingresos_evento` | Importe de ingresos en la divisa del evento | Cambió de nombre | `revenue_value_original`. |
| `moneda_ingresos_evento` | Código de moneda de 3 dígitos de `event_revenue` | Renombrado | `revenue_currency_original`. |
| `ingresos_evento_usd` | `event_revenue` convertido a USD | Renombrado | `revenue_usd`. |
| `fuente_del_evento` | O bien el SDK web o servidor a servidor | Sin cambios | `event_source`. |
| `event_time` | Visitas: hora de la visita. Eventos: hora del evento | Sin cambios | `event_time`. |
| `tipo_de_evento` | Evento estándar/evento de conversión/visita al sitio web | Redefinido | La marcación de evento de conversión ya no existe. La distinción entre visita y evento está en `end_user_event_type` (SESSION / IN\_APP). |
| `event_url` | URL de la página web donde se produjo el evento (equivale a la URL original en las visitas) | Sin cambios | `event_url`, ahora también es el lugar principal para leer los parámetros de consulta de la URL (UTM, etc.). |
| `event_value` | Eventos: detalles del evento como JSON. Visitas: null | Sin cambios | `event_value`. |
| `idfa` | Identificador de publicidad | Número con hasta 4 decimales que representa el porcentaje de impuesto recaudado. | ID de dispositivo móvil, no relevante para la web. |
| `idfv` | Identificador de publicidad | Número con hasta 4 decimales que representa el porcentaje de impuesto recaudado. | ID de dispositivo móvil, no relevante para la web. |
| `imei` | Identificador de dispositivo | Número con hasta 4 decimales que representa el porcentaje de impuesto recaudado. | ID de dispositivo móvil, no relevante para la web. |
| `hora_de_instalación` | Hora de instalación de la app más reciente | Número con hasta 4 decimales que representa el porcentaje de impuesto recaudado. | Campo móvil multiplataforma. La hora de adquisición de usuarios web (conversión) es `event_time__conversion` un concepto independiente. |
| `ip` | Dirección IP del visitante | Se ha cambiado el nombre | `ip_address_value`, mismo valor, además de `ip_address_type` para el método de hashing. |
| `Indicador de atribución AF` | Notificado por el agente de usuario (por ejemplo, «English») | Redefinido | `language`, el formato del valor cambia a ISO 639-1 y código de país. |
| `media_channel` | Atribuido a la visita al sitio web («Anuncio») | Número con hasta 4 decimales que representa el porcentaje de impuesto recaudado. | Se puede cubrir con `sub_param_1-5` si es necesario. |
| `fuente_de_medios` | Atribuido a la visita al sitio web | Sin cambios | `media_source`. |
| `media_type` | Atribuido a la visita al sitio web («Pagado») | Número con hasta 4 decimales que representa el porcentaje de impuesto recaudado. | Vacío para la web. La distinción entre orgánico y pagado ahora procede del valor booleano `is_organic`. |
| `oaid` | Identificador de publicidad | Número con hasta 4 decimales que representa el porcentaje de impuesto recaudado. | ID de dispositivo móvil, no relevante para la web. |
| `original_url` | URL que redirigió al usuario en la visita atribuida | Se ha cambiado el nombre | Consolidado en `event_url` (en las visitas, `event_url` equivale a la URL original). La columna independiente ha desaparecido. |
| `Identificador de origen` | La plataforma («macOS», «Windows») | Redefinido | La plataforma siempre es «WEBSITE». El SO se ha trasladado a `os_version` / `user_agent`. |
| `postal_code` | Resuelto utilizando la dirección IP | Sin cambios | `postal_code`. |
| `query_params` | Parámetros de consulta en la URL de redireccionamiento, en formato JSON | Número con hasta 4 decimales que representa el porcentaje de impuesto recaudado. | La cadena de consulta sin procesar está en `event_url`. La columna de JSON analizado ya no existe. |
| `referrer` | Referente HTTP de la visita al sitio web atribuida | Renombrado | `http_referrer`. |
| `Información del dispositivo` | Resuelto mediante la dirección IP («NA») | Renombrado | `continent`, código de continente, por ejemplo, «NA». |
| `state` | Resuelto utilizando la dirección IP | Sin cambios | `state`. |

<Accordion title="Prompt listo para usar para la migración de ETL de Data Locker con un agente de programación">

Para facilitar esta transición, hemos preparado un prompt listo para usar para tu agente de programación con IA (Claude Code, Cursor o similar). Da al agente acceso a tu código ETL actual y pega el prompt que aparece a continuación; contiene la asignación completa de campos y todas las diferencias de comportamiento. Guiará al agente para que aprenda tu canalización actual y la reconstruya para el nuevo reporte.

```
Estás migrando una canalización de ETL desde los reportes heredados de datos sin procesar de PBA de Data Locker de AppsFlyer (visitas al sitio web + eventos del sitio web) al reporte de Data Locker de medición del rendimiento web de AppsFlyer (eventos de usuario final). En este prompt tienes todo lo que necesitas: los cambios estructurales, la asignación completa campo por campo y los pasos de validación. No supongas nada que no esté escrito aquí; si algo es ambiguo, pregúntamelo.

## Paso 1: Aprende la canalización actual

Antes de escribir código, explora el código existente y crea un inventario:
1. Qué reportes de PBA consumimos (visitas al sitio web, eventos del sitio web o ambos) y dónde se ingieren.
2. Todos los campos de PBA que leemos y dónde se usa cada uno posteriormente (transformaciones, uniones, dashboards, alertas, exportaciones).
3. La cadencia de carga y las hipótesis de programación (PBA se entrega a diario).
4. Cualquier lógica que separe o una filas de visitas y filas de eventos.
5. Cualquier filtro, agrupación o valor codificado de forma fija basado en valores de campos de PBA (por ejemplo, nombres de media_source, etiquetas de canal, event_type, valores de plataforma).

Preséntame este inventario y espera mi confirmación antes de continuar.

## Paso 2: Hazme estas preguntas

1. ¿Ya está habilitado en Data Locker el nuevo reporte de eventos de usuario final (habilitado desde la IU de AppsFlyer)? Si no, primero tengo que habilitarlo.
2. ¿Cuál es el Unified App ID de nuestra nueva aplicación web? Formato: "website-{domain}" (por ejemplo, website-www.example.com). Si no lo sé, lo obtendré del Dashboard de AppsFlyer antes de continuar.
3. ¿Queremos un periodo de ejecución en paralelo (pipelines antiguos y nuevos en paralelo, comparando resultados) o un cambio directo? Recomiendo una ejecución en paralelo.
4. ¿Debería el nuevo pipeline consumir también el reporte de conversiones (instancias de atribución únicas, sin filas duplicadas) o el reporte de eventos de usuario final multiplataforma (deduplicado por CUID, a nivel de usuario web+móvil)? El alcance predeterminado es el reporte de eventos de usuario final a nivel de plataforma, el sucesor directo de los reportes de PBA.

## Cambios estructurales que debes tener en cuenta

1. **Un reporte en lugar de dos.** PBA dividía las visitas y los eventos en dos reportes. El nuevo reporte de eventos de usuario final contiene ambos: las visitas son filas con end_user_event_type = 'SESSION' y los eventos son filas con end_user_event_type = 'IN_APP'. Solo las filas IN_APP tienen un event_name válido; en las filas SESSION, event_name está vacío (PBA escribía "website visit" ahí).
2. **Un esquema en todas las plataformas.** El reporte es común para website, móvil, CTV y PC. Filtra siempre platform = 'WEBSITE' para aislar los datos web.
3. **Crédito de atribución doble, deduplica.** La misma acción puede aparecer dos veces: una fila de crédito principal y una fila de crédito secundario (fuente de UA original, para LTV en vista de UA). Filtra is_primary_attribution = true de forma predeterminada para evitar el recuento doble. Quita el filtro solo para análisis específicos de vista de UA frente a vista de retargeting con conversion_type.
4. **Cada hora en lugar de a diario.** El nuevo reporte se entrega cada hora con aproximadamente 2 horas de frescura de datos. Rediseña las cargas incrementales en torno a lotes horarios en lugar de una carga diaria.
5. **Orgánico vs. pagado.** El media_type ("Paid") de PBA ya no existe. Usa el booleano is_organic; no infieras nunca si es orgánico o pagado a partir de media_source.
6. **Recuento de usuarios.** Cuenta y une usuarios con COALESCE(customer_user_id, appsflyer_id_value): primero el ID de usuario de cliente estable y, como alternativa, el ID basado en cookies.
7. **Valores vacíos.** Los campos STRING son '' y los campos NUMERIC son NULL.

## Mapeo campo por campo (PBA → End User Events)\n\nLeyenda de estados: Unchanged = mismo nombre y mismos datos. Renamed = mismos datos, columna nueva. Redefined = cambios en los datos o en el formato del valor (trátalo con cuidado). Deprecated = sin equivalente.

| Campo de PBA | Estado | Campo nuevo / gestión |\n|---|---|---|\n| advertising_id | Deprecated | ID de dispositivo móvil/de dispositivo. Los reportes multiplataforma se basan en CUID; elimínalo. |\n| af_web_id | Renamed | appsflyer_id_value, la misma cookie web. |
| amazon_aid | Deprecated | ID de dispositivo móvil, no relevante para la web. |
| android_id | Deprecated | ID de dispositivo móvil, no relevante para la web. |\n| app_id | Deprecated | Campo multiplataforma móvil. El nuevo identificador de la app web es unified_app_id ("website-{domain}"), un concepto distinto; no es un cambio de nombre. |
| app_name | Unchanged | app_name. |\n| app_version | Deprecated | Campo multiplataforma móvil. |
| appsflyer_id | Deprecated | ID de instalación móvil. Nota: el nuevo appsflyer_id_value es la cookie web (el af_web_id de PBA), NO este campo. |
| attributed_touch_time | Renamed | event_time__attribution. |
| attributed_touch_type | Deprecated | Era una constante. La distinción visita-vs-evento ahora está en end_user_event_type. |\n| bundle_id | Deprecated | Sustituido por la agrupación de línea de producto en el reporte multiplataforma. |
| campaign | Renamed | campaign_name. |
| campaign_id | Sin cambios | campaign_id. |
| city | Sin cambios | city. |
| country_code | Sin cambios | country_code. |
| customer_user_id | Sin cambios | customer_user_id. |
| device_type | Se renombra y cambian los valores | device_category, los valores difieren (por ejemplo, "Desktop" → valores del estilo "MOBILE_PHONE" / "TV"). Actualiza cualquier lógica basada en claves de valor. |
| dma | Sin cambios | dma. |
| event_name | Redefinido | Eventos: sin cambios. Visitas: ahora está vacío (PBA escribió "website visit"). Usa end_user_event_type = 'SESSION' para identificar las visitas. |
| event_revenue | Renombrado | revenue_value_original. |
| event_revenue_currency | Renombrado | revenue_currency_original. |
| event_revenue_usd | Renombrado | revenue_usd. |
| event_source | Sin cambios | event_source. |
| event_time | Sin cambios | event_time. |
| event_type | Redefinido | La marca de «evento de conversión» ya no existe. La distinción entre visita y evento está en end_user_event_type (SESSION / IN_APP). |
| event_url | Sin cambios | event_url, ahora también es el lugar principal desde el que se leen los parámetros de consulta de la URL (UTM, etc.). |
| event_value | Sin cambios | event_value. |
| idfa / idfv / imei / oaid | Obsoleto | ID de dispositivo móvil, no relevante para web. |
| install_time | Obsoleto | Campo móvil. El tiempo de adquisición del usuario web es event_time__conversion, un concepto distinto. |
| ip | Renombrado | ip_address_value (más ip_address_type para el método de hashing). |
| language | Redefinido | language, el formato cambia a ISO 639-1 + código de país (antes era, por ejemplo, "English"). |
| media_channel | Obsoleto | Se puede cubrir con sub_param_1-5 si es necesario. |
| media_source | Sin cambios | media_source (pero consulta los cambios de nombre de valores más abajo). |
| media_type | Obsoleto | Usa el booleano is_organic en su lugar. |
| original_url | Renombrado | Consolidado en event_url (en las visitas, event_url equivale a la URL original). La columna independiente ha desaparecido. |
| platform | Redefinido | platform siempre es "WEBSITE". El SO se ha trasladado a os_version / user_agent. |
| postal_code | Sin cambios | postal_code. |
| query_params | Obsoleto | La cadena de consulta sin procesar está en event_url; la columna de JSON analizado ha desaparecido. Vuelve a implementar el análisis desde event_url si es necesario. |
| referrer | Renombrado | http_referrer. |
| región | Se ha cambiado el nombre | continente, código del continente (por ejemplo, "NA"). |
| state | Sin cambios | state. |

## Cambios en los valores atribuidos (actualiza filtros y agrupaciones)

El motor de atribución resuelve las fuentes de tráfico de forma diferente, por lo que algunos valores cambian incluso cuando los nombres de los campos no:
- cambios de nombre de media_source: doubleclick_int → dv360_int (display/vídeo de Google mediante UTM); "X Ads" → "Twitter" (Twitter mediante UTM). Ahora, más valores de PID se reasignan a nombres para mostrar (por ejemplo, iossearchads_int → Apple Search Ads, metweb_int → Facebook Ads, tiktokweb_int → tiktokglobal_int, snapweb_int → snapchat_int).
- Las etiquetas de canal cambian de formato: Direct / Organic search / Social media / Email / Ad / Referral / Other pasan a ser DIRECT / ORGANIC_SEARCH / SOCIAL_MEDIA / EMAIL / AD / REFERRAL / OTHER.
- Se ha ampliado la cobertura de ID de clic (más redes se resuelven a partir de ID de clic); dclid por sí solo ya no se resuelve; fbclid no se usa.

Busca en el repositorio de código cualquier filtro, CASE, clave de join o agrupación de dashboard basada en estos valores antiguos y actualízalos.

## Paso 3: Compilar

1. Propón el nuevo diseño de ETL (ingesta, esquema, lógica incremental por hora y los filtros obligatorios de «Cambios estructurales»).
2. Tras mi aprobación, impleméntalo reutilizando nuestras convenciones e infraestructura existentes.
3. Para cada campo obsoleto que el inventario haya encontrado en uso downstream, indica el consumidor y propón una solución (eliminarlo, sustituirlo por la alternativa sugerida o marcarlo para el responsable de negocio).

## Paso 4: Validar

1. Ejecuta ambos pipelines en el mismo intervalo de días y compara: visitas (filas de SESSION) vs visitas web de PBA, eventos (filas de IN_APP) vs eventos web de PBA, e ingresos totales.
2. Espera diferencias, no igualdad: la nueva lógica de atribución es más avanzada, por lo que las dimensiones atribuidas (media_source, campaña) no coincidirán exactamente con PBA. La lógica de recuento de sesiones no cambia (30 minutos de actividad), así que el volumen de visitas debería mantenerse en niveles similares.
3. Verifica que el filtro is_primary_attribution se aplique en todas partes; si falta, aparecen recuentos de eventos inflados.
4. Genera un reporte breve de la migración: qué se asignó, qué se descartó, qué cambió en los valores y cualquier elemento pendiente para el responsable del negocio.
```

</Accordion>

<div id="pba-web-s2s-to-new-s2s-api-migration" />

## Migración de PBA Web-S2S a la nueva API S2S

Si reportas eventos a PBA mediante la <Anchor target="_blank" href="/marketers/es/docs/web-server-to-server-events-api-for-pba-web-s2s">API de eventos de servidor a servidor web (Web-S2S)</Anchor>, pásate a la <Anchor target="_blank" href="/marketers/es/docs/server-to-server-s2s-api-for-web-performance-measurement">nueva API S2S</Anchor>. La nueva API admite tanto visitas como eventos, por lo que tu sitio web puede funcionar completamente del lado del servidor; el S2S de PBA solo acepta eventos.

<Accordion title="Endpoints y autenticación">

|  | PBA Web-S2S | Nueva API S2S |
| --- | --- | --- |
| URL base | `https://webs2s.appsflyer.com` | `https://events.appsflyer.com` |
| Llamada de evento | `POST /v1/{bundleId}/event` | `POST /v2.0/s2s/inapps/app/web/{appId}` |
| Llamada de visita | No disponible (las visitas procedían solo del SDK web) | `POST /v2.0/s2s/visits/app/web/{appId}` |
| Llamada de identidad | `POST /v1/{bundleId}/setcuid` (llamada independiente para asociar un CUID a un usuario web) | Ninguna; la identidad se envía en línea en el objeto `user_id` en cada evento/visita |
| Identificador de la aplicación | `bundleId` (ID del bundle de la marca) en la ruta | `appId` = el `unified_app_id` web («website-`{domain}`») en la ruta |
| Autenticación | `webDevKey` dentro del cuerpo JSON en cada llamada | Encabezado Authorization que contiene la clave de la API S2S |
| Tipo de contenido | `application/json` | `application/json` |
| Respuesta exitosa | 200 OK | 202 Aceptado |

</Accordion>

<Accordion title="Asignación de campos del payload">

| Campo S2S de PBA Web | Nuevo campo S2S | Advertencia |
| --- | --- | --- |
| `customerUserId` | `user_id.customer_user_id` | Ahora está anidado en el objeto `user_id`. |
| `afUserId` | `user_id.appsflyer_id` | Ahora está anidado en el objeto `user_id`. Envía al menos uno de `customer_user_id` o `appsflyer_id`; envía ambos siempre que se identifique al usuario. |
| `webDevKey` | No aplica | Se ha eliminado del cuerpo. La autenticación se ha trasladado al encabezado Authorization; la app se identifica mediante `appId` en la ruta. |
| `eventType` (siempre EVENT) | No aplica | Eliminado. El endpoint (/inapps vs. /visits) determina el tipo. |
| `eventName` | `nombre_del_evento` | 1-64 caracteres; no puede contener `@ = + -`. |
| `timestamp` (ms de Unix, 13 dígitos) | `timestamp` (ms de Unix) | El formato es el mismo. Se recomienda en cada llamada; si se omite, AppsFlyer utiliza la hora de recepción. |
| `valor del evento` | `event_value` | Formato libre; admite un subobjeto `custom_parameters`. |
| `eventRevenue` | `ingresos_evento` | Ahora es opcional (PBA lo requería para los dashboard). |
| `eventRevenueCurrency` | `moneda_ingresos_evento` | Ahora es opcional (PBA lo requería para los dashboard). |
| `referrer` | `http_referrer` | Se ha renombrado. |
| `userAgent` | `agente_usuario` | Se ha renombrado. |
| `ip` | `ip` | Sin cambios. |
| No aplica | `event_url` | Nuevo. Obligatorio en las visitas; opcional en los eventos. |
| No aplica | `customer_dedup_id` | Nuevo. Elimina duplicados del mismo evento que llega desde otra fuente (por ejemplo, el SDK web). |
| No aplica | `email_hashed`, `phone_number_hashed`, `phone_number_e164_hashed`, `first_name_hashed`, `last_name_hashed` | Nuevo. SHA256 (hexadecimal en minúsculas de 64 caracteres) de valores normalizados, para el enriquecimiento de identidad. |

</Accordion>

<Accordion title="Notas sobre la API de S2S">

* **Las visitas ahora son del lado servidor.** El S2S de PBA solo aceptaba eventos; las visitas tenían que llegar desde el SDK web. El nuevo endpoint /visits permite que el sitio web funcione completamente del lado del servidor.
* **Ya no hace falta la llamada setcuid.** PBA requería el SDK web, por lo que hacía falta una llamada independiente para vincular un CUID a un usuario web. La nueva API incluye la identidad en línea en cada solicitud, por lo que se elimina ese paso.
* **Ventana de datos tardíos.** Envía los eventos y las visitas en tiempo real, preferiblemente en los 30 minutos posteriores a que se produzca el evento, en lugar de agruparlos en una única carga diaria. Los datos que llegan más de 30 minutos después del final del día UTC en el que se produjo el evento siguen aceptándose, pero su hora del evento se sustituye por la hora a la que AppsFlyer los recibió.

</Accordion>

<Accordion title="Migración del servicio S2S: prompt listo para usar para tu agente de programación">

Si reportas eventos a través de la API de servidor a servidor de PBA, hemos preparado un prompt listo para usar para tu agente de programación con IA (Claude Code, Cursor o similar). Da al agente acceso al servicio que envía eventos a AppsFlyer y pega el prompt a continuación; contiene el endpoint completo y la asignación del payload. Guiará al agente para que aprenda tu implementación actual y cree la actualizada.

```
Estás migrando una integración del lado del servidor desde la API heredada de eventos PBA Web S2S de AppsFlyer (webs2s.appsflyer.com) a la nueva API S2S de AppsFlyer para la medición del rendimiento web (events.appsflyer.com). Todo lo que necesitas está en este prompt: endpoints, autenticación, el mapeo completo de la carga útil y los cambios de comportamiento. No des nada por supuesto más allá de lo que está escrito aquí; si algo es ambiguo, pregúntame.

## Paso 0: Hazme estas preguntas antes de modificar el código

1. ¿Debemos modificar el servicio actual directamente o crear un nuevo servicio/módulo en paralelo (para permitir una ejecución en paralelo y una transición limpia)? Recomienda un módulo nuevo en paralelo.
2. ¿Conozco el Unified App ID de nuestra nueva aplicación web? Formato: «website-{domain}» (por ejemplo, website-www.example.com). Sustituye al bundle ID de PBA en la ruta de la URL. Si no lo sé, lo obtendré del dashboard de AppsFlyer antes de continuar.
3. ¿Tengo la nueva clave de la API S2S? La autenticación pasó de la webDevKey en el cuerpo de la solicitud a una cabecera Authorization que incluye esta clave. Si no la tengo, la recuperaré del dashboard de AppsFlyer.
4. ¿Queremos enviar solo eventos (como PBA) o adoptar también el nuevo endpoint de visitas? La nueva API admite visitas del lado del servidor, por lo que el sitio web puede funcionar completamente del lado del servidor; PBA solo aceptaba eventos.
5. ¿El SDK web de AppsFlyer sigue en funcionamiento en nuestro sitio? (Esto determina si las visitas proceden del SDK y si necesitamos deduplicación de eventos entre el SDK y S2S.)

## Paso 1: Conoce el servicio actual

Explora la base de código y elabora un inventario:
1. Todos los puntos del código que llaman a webs2s.appsflyer.com, las llamadas a /event y cualquier llamada a /setcuid.
2. Los campos que se rellenan en cada llamada (customerUserId, afUserId, eventName, eventValue, eventRevenue, timestamp, referrer, userAgent, ip, etc.) y de dónde proceden sus valores.
3. Gestión de errores y monitorización basadas en la respuesta 200 OK.
4. Comportamiento de reintento, procesamiento por lotes y colas.

Preséntame este inventario y espera mi confirmación antes de continuar.

## Qué ha cambiado: endpoints y autenticación

|  | PBA Web-S2S (anterior) | Nueva API S2S |
|---|---|---|
| URL base | https://webs2s.appsflyer.com | https://events.appsflyer.com |
| Llamada de evento | POST /v1/{bundleId}/event | POST /v2.0/s2s/inapps/app/web/{appId} |
| Llamada de visita | No disponible | POST /v2.0/s2s/visits/app/web/{appId} |
| Llamada de identidad | POST /v1/{bundleId}/setcuid | Ninguna; la identidad va integrada en el objeto user_id en cada llamada |
| Identificador de la aplicación en la ruta | bundleId (bundle ID de la marca) | appId = el Unified App ID web ("website-{domain}") |
| Autenticación | webDevKey en el cuerpo JSON | Cabecera Authorization con la clave de la API S2S |
| Tipo de contenido | application/json | application/json (415 si falta) |
| Respuesta correcta | 200 OK | 202 Accepted |

## Mapeo de campos de la carga útil

| Campo de PBA | Campo nuevo | Nota |
|---|---|---|
| customerUserId | user_id.customer_user_id | Anidado en el objeto user_id. |
| afUserId | user_id.appsflyer_id | Anidado en el objeto user_id. Envía al menos uno de customer_user_id o appsflyer_id; envía ambos siempre que el usuario esté identificado. |
| webDevKey | (eliminado) | La autenticación se ha trasladado al encabezado Authorization; la app se identifica mediante appId en la ruta. |
| eventType (siempre "EVENT") | (eliminado) | El endpoint (/inapps vs /visits) determina el tipo. |
| eventName | event_name | 1-64 caracteres; no puede contener los caracteres @ = + -. |
| timestamp (Unix ms) | timestamp (Unix ms) | Mismo formato. Recomendado en cada llamada; si se omite, AppsFlyer usa la hora de recepción. |
| eventValue | event_value | Formato libre; admite un subobjeto custom_parameters. |
| eventRevenue | event_revenue | Ahora es opcional (PBA lo requería para los dashboards). |
| eventRevenueCurrency | event_revenue_currency | Ahora es opcional (PBA lo requería para los dashboards). |
| referrer | http_referrer | Renombrado. |
| userAgent | user_agent | Renombrado. |
| ip | ip | Sin cambios. |
| (nuevo) | event_url | Obligatorio en /visits; opcional en eventos. |
| (nuevo) | customer_dedup_id | Elimina duplicados del mismo evento que llega desde otra fuente (por ejemplo, el SDK web). |
| (nuevo) | email_hashed, phone_number_hashed, phone_number_e164_hashed, first_name_hashed, last_name_hashed | SHA256 (hexadecimal en minúsculas de 64 caracteres) de valores normalizados, para el enriquecimiento de identidad. |

## Cambios de comportamiento y aspectos a tener en cuenta

1. **appId es el Unified App ID, no el «Web SDK ID».** La página de configuración de la aplicación en AppsFlyer muestra un UUID «Web SDK ID» (el antiguo Web Dev Key, que se mantiene por la continuidad del SDK). La ruta S2S debe incluir el Unified App ID («website-{domain}»), nunca ese UUID. Un 401 «app not found» normalmente significa que hay un appId incorrecto en la ruta o que falta la cabecera Authorization, o bien que no es válida.
2. **El éxito es 202, no 200.** Actualiza las comprobaciones de estado, los reintentos y las alertas en consecuencia.
3. **No valides con el endpoint antiguo.** El endpoint heredado puede seguir devolviendo 200, pero esa respuesta no demuestra que los datos hayan llegado a Web Performance Measurement. Verifica siempre que los eventos aparezcan realmente en los datos de la nueva aplicación web.
4. **Elimina por completo el flujo setcuid.** La identidad viaja integrada en el objeto user_id en cada evento y visita.
5. **Las visitas deben ir antes que los eventos.** El sistema espera una visita antes de cualquier evento de un usuario; los eventos de un usuario sin ninguna visita previa se clasifican como orgánicos. Las visitas proceden del SDK web o, ahora también, del endpoint /visits.
6. **Envía en tiempo real; no agrupes en lotes.** Envía cada evento y visita a medida que se produzca, preferiblemente en un plazo de 30 minutos desde que ocurra el evento. Los datos que llegan más de 30 minutos después del final del día UTC en el que se produjo el evento siguen aceptándose, pero su hora del evento se sustituye por la hora de recepción, lo que distorsiona la Atribución. Envía siempre una marca de tiempo. Ten en cuenta que el retraso de Atribución de aproximadamente 30 minutos del que puedas leer es una retención independiente, del lado del Servidor, por parte de AppsFlyer; no hay nada que tengamos que implementar.
7. **Opción completa del lado del servidor (si adoptamos las visitas).** Sin Web SDK, nuestro servidor controla el identificador de usuario web: genera un ID estable para los visitantes que llegan por primera vez, consérvalo como una cookie HTTP propia establecida por el servidor (cabecera Set-Cookie, no JavaScript; las cookies de JS están limitadas a aproximadamente 7 días en Safari), reutilízalo en cada solicitud y envíalo como user_id.appsflyer_id. La carga útil de la visita debe incluir event_url, y te recomendamos incluir también ip, user_agent y http_referrer para mejorar la calidad de la atribución.
8. **SDK + S2S juntos.** Si ambos envían el mismo evento, rellena customer_dedup_id para que AppsFlyer conserve una sola copia.

## Paso 2: Compilar

1. Propón el diseño: nuevo cliente/módulo, configuración (URL base, appId, almacenamiento de la clave de API en nuestro gestor de secretos, nunca codificada de forma rígida), creadores de carga útil para eventos (y visitas, si entran en el alcance), y la gestión de respuestas/reintentos para 202.
2. Tras mi aprobación, impleméntalo siguiendo nuestras convenciones actuales.
3. Asigna todos los campos del inventario según la asignación de carga útil anterior; marca cualquier campo que enviemos actualmente y que no tenga un equivalente nuevo.

## Paso 3: Validar

1. Envía un evento de prueba (y una visita, si entra en el alcance) y confirma una respuesta 202.
2. Verifica que los datos de prueba aparezcan en la nueva aplicación web de AppsFlyer (en el dashboard o en Data Locker); esta es la señal real de éxito, no la respuesta HTTP.
3. Confirma que los nombres de los eventos cumplan las nuevas restricciones (1-64 caracteres, sin @ = + -).
4. Si funciona en paralelo con el servicio antiguo, compara durante unos días los volúmenes de eventos entre el sistema antiguo y el nuevo antes del cambio y, después, retira las llamadas antiguas, incluida setcuid.
```

</Accordion>

<div data-zendesk-anchors="why-were-upgrading-your-web-measurement=por-qu%C3%A9-estamos-mejorando-tu-medici%C3%B3n-web h_01KYM7JM37WVTV7XHEHVTPKWM9=por-qu%C3%A9-estamos-mejorando-tu-medici%C3%B3n-web comparing-pba-and-web-performance-measurement=comparaci%C3%B3n-entre-pba-y-web-performance-measurement h_01KYM7JM3711FXC132MSC3B4A9=comparaci%C3%B3n-entre-pba-y-web-performance-measurement web-performance-measurement-vs-pba=web-performance-measurement-frente-a-pba h_01KYM7JM3711FXC132MSC3B4A8=web-performance-measurement-frente-a-pba traffic-source-resolution-pba-vs-web-performance-measurement=resoluci%C3%B3n-de-la-fuente-de-tr%C3%A1fico-pba-vs-medici%C3%B3n-del-rendimiento-web h_01KYM7JM387R5YEYJK9CD0AQJ0=resoluci%C3%B3n-de-la-fuente-de-tr%C3%A1fico-pba-vs-medici%C3%B3n-del-rendimiento-web migrate-to-web-performance-measurement=migra-a-medici%C3%B3n-del-rendimiento-web h_01KYM7JM37HG8YAX02XMSKBTPP=migra-a-medici%C3%B3n-del-rendimiento-web h_01KYM7JM37HG8YAX02XMSKBTPP01=paso-1-crea-una-aplicaci%C3%B3n-web-obligatorio-para-todos create-a-web-app=paso-1-crea-una-aplicaci%C3%B3n-web-obligatorio-para-todos h_01KYM7JM37HG8YAX02XMSKBTPP02=paso-2-si-env%C3%ADas-eventos-a-trav%C3%A9s-de-la-api-s2s if-you-send-events-through-the-s2s-api=paso-2-si-env%C3%ADas-eventos-a-trav%C3%A9s-de-la-api-s2s h_01KYM7JM37HG8YAX02XMSKBTPP03=paso-3-si-utilizas-los-reportes-de-raw-data-de-pba if-you-consume-pbas-raw-data-reports=paso-3-si-utilizas-los-reportes-de-raw-data-de-pba h_01KYM7JM37HG8YAX02XMSKBTPP04=paso-4-si-usas-el-pba-brand-bundle-para-reportar-en-multiplataforma if-you-use-pba-brand-bundle-for-cross-platform-reporting=paso-4-si-usas-el-pba-brand-bundle-para-reportar-en-multiplataforma capabilities-being-discontinued=capacidades-que-se-dejar%C3%A1n-de-ofrecer h_01KYM7JM37JJ25D3RFE2V7BM4D=capacidades-que-se-dejar%C3%A1n-de-ofrecer raw-data-field-mapping=asignaci%C3%B3n-de-campos-de-raw-data h_01KYM7JM37Z7Z21FJ2G83T2WPG=asignaci%C3%B3n-de-campos-de-raw-data pba-web-s2s-to-new-s2s-api-migration=migraci%C3%B3n-de-pba-web-s2s-a-la-nueva-api-s2s h_01KYM7JM38K9C01XDZY99KZVTX=migraci%C3%B3n-de-pba-web-s2s-a-la-nueva-api-s2s" />
