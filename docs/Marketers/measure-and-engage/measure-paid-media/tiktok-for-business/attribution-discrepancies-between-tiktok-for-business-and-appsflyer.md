---
title: Discrepancias de atribución entre TikTok for Business y AppsFlyer
metadata:
  keywords:
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2023-10-30T07:45:29Z'
  edited_at: '2026-08-12T12:22:07Z'
  id: 19733501619473
  locale: es
  section: TikTok for Business
  section_id: 12192554266385
  url: https://support.appsflyer.com/hc/es/articles/19733501619473
---
> **Resumen rápido:** Descubra las diferencias en los modelos de atribución entre TikTok for Business y AppsFlyer.

<div id="overview" />

## Visión general

Como dos líderes en el ecosistema de adquisición de usuarios móviles, TikTok for Business y AppsFlyer emplean modelos de atribución distintos. Esto puede provocar discrepancias entre los paneles de TikTok for Business y AppsFlyer. A pesar de nuestra colaboración estrecha con TikTok for Business para minimizar estas discrepancias, los anunciantes deben conocer las causas potenciales.

<div id="differences-in-attribution-models" />

## Diferencias en los modelos de atribución

La tabla a continuación describe los posibles motivos de las discrepancias entre el Administrador de Anuncios de TikTok y los paneles de AppsFlyer:

<table><thead><tr><th>Causa</th><th>Administrador de anuncios de TikTok</th><th>AppsFlyer</th></tr></thead><tbody><tr><td><span id="click-attribution-lookback-window"></span><p><strong>Ventana retrospectiva de atribución por clic</strong></p></td><td><p>La ventana predeterminada es de 7 días. Sin embargo, se puede configurar de manera diferente para las aplicaciones de Android y para aquellas que han pasado a la autoatribución de TikTok (TikTok—SRN).</p></td><td><p>La ventana predeterminada es de 7 días. La ventana se puede ajustar entre 1 y 30 días. Asegúrese de ajustarse a la ventana de atribución de TikTok.</p></td></tr><tr><td><span id="viewthrough-attribution-lookback-window"></span><p><strong>Ventana retrospectiva de atribución de visualización</strong></p></td><td><p>La ventana predeterminada es de 1 día. Sin embargo, se puede configurar de manera diferente para las aplicaciones de Android y para aquellas que han pasado a la autoatribución de TikTok (TikTok—SRN).</p></td><td><p>La ventana predeterminada es de 1 día. La ventana se puede configurar entre 1 y 48 horas. Asegúrese de ajustarse a la ventana de atribución de TikTok.</p></td></tr><tr><td><span id="multichannel-sourceattribution"></span><p><strong>Atribución de fuentes multicanal</strong></p></td><td><p>TikTok autoatribuye las instalaciones sin considerar otras fuentes de medios.</p></td><td><p>AppsFlyer utiliza la atribución de último clic (puede obtener más información sobre el <a href="./appsflyer-attribution-model" target="_blank">modelo de atribución de AppsFlyer</a>).</p></td></tr><tr><td><span id="crossdevice-attribution"></span><p><strong>Atribución entre dispositivos</strong></p></td><td><p>TikTok atribuye a los usuarios que realizan tanto la interacción como la instalación utilizando distintos dispositivos, como iOS, Android y computadoras de escritorio.</p></td><td><p>AppsFlyer atribuye a los usuarios que llevan a cabo ambas acciones en el mismo dispositivo.</p></td></tr><tr><td><span id="different-time-zones"></span><p><strong>Diferentes zonas horarias</strong></p></td><td><p><a href="https://ads.tiktok.com/help/article/time-zone" target="_blank">La zona horaria de TikTok</a> (mostrada junto al rango de fechas) no se puede modificar. Esta se configuró durante la creación de la cuenta publicitaria.</p></td><td><p>La zona horaria predeterminada de la aplicación en AppsFlyer es UTC+0. Para ajustarse a la zona horaria del Administrador de eventos de TikTok, modifique la zona horaria definida en la <a href="./app-settings#localization-time-zone" target="_blank">página de configuración de la aplicación</a>.</p></td></tr><tr><td><span id="ios-attribution"></span><p><strong>Atribución en iOS</strong></p></td><td><p>Para las aplicaciones en iOS, el Administrador de Anuncios de TikTok solo muestra resultados de atribución de SKAN.</p></td><td><p>Para las aplicaciones de iOS, AppsFlyer muestra los resultados de atribución de SKAN, junto con la atribución de AppsFlyer tanto para SRN como para SRN avanzados, y los datos SSOT deduplicados. Se espera que solo los datos de SKAN coincidan en ambas plataformas. </p></td></tr><tr><td><span id="in-app-event-attribution-periods"></span><p><strong>Períodos de atribución de eventos en la aplicación</strong></p></td><td colspan="2"><p>La atribución en cada plataforma puede variar según los períodos desde la instalación inicial:</p></td></tr><tr><td><span id="day-1-90"></span><p>Día 1-90</p></td><td colspan="2"><p>No hay discrepancias en la atribución. Ambas plataformas atribuyen los eventos en la aplicación al momento de la instalación.</p></td></tr><tr><td><span id="day-91-180"></span><p>Día 91-180</p></td><td rowspan="2"><p>Después de 90 días, los eventos dentro de la aplicación no se reportan en TikTok.</p></td><td><div><div><div>AppsFlyer sigue atribuyendo los eventos en la aplicación al momento de la instalación.</div></div></div></td></tr><tr><td><span id="day-180"></span><p>Día 180+</p></td><td><div><div><div>Debido a la <a href="./user-level-data-retention#periodos-de-conservación-de-los-datos-de-partners" target="_blank">política de retención de datos de TikTok</a>, los eventos en la aplicación se atribuyen de manera orgánica.</div></div></div></td></tr></tbody></table>

<div id="differences-in-installs" />

## Diferencias en las instalaciones

En algunos casos, TikTok for Business incluye instalaciones que AppsFlyer rechaza o no considera como nuevas instalaciones.

<div id="re-engagement-campaigns" />

### Campañas de re-engagement

Una campaña de re-engagement puede llevar a que los usuarios abran una aplicación que ya está instalada (**re-engagement**). Cuando AppsFlyer reconoce una instalación anterior de la aplicación en el mismo dispositivo, se refiere a esa conversión como una **reatribución**.

Los usuarios se registran en AppsFlyer como **instalaciones de adquisición de nuevos usuarios** si instalan la aplicación por primera vez desde una campaña de re-engagement de TikTok for Business. Además, si los usuarios instalan la aplicación después de la <Anchor target="_blank" href="/marketers/es/docs/set-up-re-attribution-window">ventana de reatribución designada</Anchor> **tras la instalación inicial, también se consideran nuevas adquisiciones.**

Por otro lado, las instalaciones que ocurren **dentro de la ventana de reatribución establecida** después de la instalación original se clasifican como reatribuciones. Estas instalaciones son visibles en la página de retargeting de AppsFlyer. Sin embargo, TikTok for Business podría considerarlas como nuevas instalaciones.

<div id="rejected-installs-when-using-validation-rules-and-protect360" />

### Instalaciones rechazadas al utilizar reglas de validación y Protect360

<Anchor target="_blank" href="/marketers/es/docs/implement-validation-rules-to-prevent-fraud">Reglas de validación</Anchor> y <Anchor target="_blank" href="/marketers/es/docs/protect360-anti-fraud-guide">Protect360</Anchor> son características de AppsFlyer que añaden protección al rechazar (bloquear) ciertas instalaciones. Al utilizar estas funciones, las instalaciones rechazadas que se originan en TikTok for Business son bloqueadas por AppsFlyer, mientras que TikTok for Business informa por su cuenta estas instalaciones.

<div id="example" />

> 📄 **Ejemplo**
>
> Jeff, el gestor de UA de GreatApp, crea una campaña llamada SPNA, dirigida únicamente a hablantes de español en América del Norte. Para comprobarlo, Jeff establece una regla de validación que acepta solo usuarios de Canadá y EE. UU.
> Cuando un usuario de TikTok for Business en España hace clic e instala la app, TikTok for Business auto-reporta la instalación, mientras que AppsFlyer la rechaza si no pasa la regla de validación.

<div id="reducing-discrepancies" />

## Reducción de discrepancias

Aunque existen diferencias en los modelos de atribución, las discrepancias pueden reducirse en algunos casos.

<div id="click-through-and-view-through-attribution" />

### Atribución por clics y por visualización

AppsFlyer admite la atribución tanto por clics como por visualizaciones. Para minimizar las discrepancias entre TikTok for Business y AppsFlyer, asegúrese de que las ventanas de retrospectiva de clics y visualizaciones sean coherentes con las definidas por TikTok for Business.

<div id="example-1" />

> 📄 **Ejemplo**
>
> Supongamos que la ventana retrospectiva de clics de TikTok for Business está configurada en 1 día en AppsFlyer para su aplicación `com.greatapp`, mientras que en TikTok for Business está configurada con el valor por defecto de 7 días. Los usuarios que hacen clic en el anuncio de Greatapp en TikTok pero abren la aplicación por primera vez después de 2 a 7 días se consideran usuarios orgánicos en AppsFlyer, mientras que TikTok for Business los auto-reporta.

<div id="in-app-event-attribution" />

### Atribución de eventos dentro de la app

Las diferencias entre plataformas también pueden aparecer en eventos posteriores a la instalación (como compras dentro de la app), que se presentan tanto en TikTok for Business como en AppsFlyer. La siguiente tabla describe las razones más comunes de estas diferencias y ofrece consejos sobre cómo reducirlas:

| Causa | Descripción | Consejo de AppsFlyer |
| --- | --- | --- |
| <span id="selfattribution"></span>**Autoatribución** | TikTok siempre atribuye las instalaciones y eventos a sus propias campañas, mientras que AppsFlyer los atribuye a la fuente de adquisición. Estos eventos se señalan como asistencia de TikTok en AppsFlyer. | Combine los datos sin procesar de las conversiones atribuidas a TikTok con los datos sin procesar donde TikTok es el contribuyente. |
| <span id="unmapped-events"></span>**Eventos no asignados** | AppsFlyer recibe eventos originados en el SDK, pero no están mapeados a TikTok for Business y, por tanto, no se envían. | Asegúrate de <Anchor target="_blank" href="/marketers/es/docs/tiktok-for-business-advanced-srn-integration-setup#postbacks-de-eventos-in-app">mapear con TikTok for Business</Anchor> los eventos en la app que indiquen calidad de usuario. |
| <span id="unsent-revenue"></span>**Ingresos no enviados** | AppsFlyer obtiene los ingresos de los eventos originados por el SDK, pero no se envían a TikTok for Business. | Asegúrate de incluir los ingresos al <Anchor target="_blank" href="/marketers/es/docs/tiktok-for-business-advanced-srn-integration-setup#postbacks-de-eventos-in-app">mapear los eventos dentro de la aplicación en TikTok for Business</Anchor>. |
| <span id="missing-event-values-on-tiktok"></span>**Valores de eventos no registrados en TikTok for Business** | AppsFlyer envía parámetros y valores a TikTok for Business como parte del mapeo de eventos, siempre que tengan las estructuras correctas. | Desarrolla los eventos de tu SDK dentro de la aplicación siguiendo las <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure">estructuras recomendadas por AppsFlyer</Anchor> para mapear por completo los valores de los eventos con TikTok for Business. |

<div data-zendesk-anchors="overview=visi%C3%B3n-general h_01HFXTVVZNJQJFAAR1F3HW1D5M=visi%C3%B3n-general differences-in-attribution-models=diferencias-en-los-modelos-de-atribuci%C3%B3n h_01HFXTVVZN79JX9E5PTXMPB8BS=diferencias-en-los-modelos-de-atribuci%C3%B3n differences-in-installs=diferencias-en-las-instalaciones h_01HFXTVVZNDQKNW85BBWR0PE2Z=diferencias-en-las-instalaciones reengagement-campaigns=campa%C3%B1as-de-re-engagement h_01HFXTVVZNA1R59KCA41H2YSBJ=campa%C3%B1as-de-re-engagement rejected-installs-when-using-validation-rules-and-protect360=instalaciones-rechazadas-al-utilizar-reglas-de-validaci%C3%B3n-y-protect360 h_01HFXTVVZNJVFHE0W5DTP5PDCG=instalaciones-rechazadas-al-utilizar-reglas-de-validaci%C3%B3n-y-protect360 01H890CZSYCTQZCAYAZP9TCBBF=ejemplo minimizing-discrepancies=reducci%C3%B3n-de-discrepancias h_01HFXTVVZNW9GZB8QYMR1KTNMN=reducci%C3%B3n-de-discrepancias clickthrough-and-viewthrough-attribution=atribuci%C3%B3n-por-clics-y-por-visualizaci%C3%B3n h_01HFXTVVZNN45WY997DK9K8WA4=atribuci%C3%B3n-por-clics-y-por-visualizaci%C3%B3n h_01HFRQMF6HTT84J4EDFXZMK7CP=ejemplo-1 inapp-event-attribution=atribuci%C3%B3n-de-eventos-dentro-de-la-app h_01HFXTVVZNG7TKQVY1229X594G=atribuci%C3%B3n-de-eventos-dentro-de-la-app" />
