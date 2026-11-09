---
title: Discrepancias de Anuncios de Meta
metadata:
  keywords:
    - Facebook
    - Advertisers
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
  created_at: '2021-11-09T10:10:54Z'
  edited_at: '2026-08-12T12:20:06Z'
  id: 4410481130641
  locale: es
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/es/articles/4410481130641
---
> **De un vistazo:** Conoce las diferencias en los modelos de atribución entre Anuncios de Meta y AppsFlyer.

<div id="meta-ads-discrepancies-with-appsflyer" />

## Discrepancias de Anuncios de Meta con AppsFlyer

Como dos de los principales actores del ecosistema de adquisición de usuarios móviles, AppsFlyer y Anuncios de Meta cuentan con modelos de atribución diferentes. Esto puede hacer que surjan discrepancias entre los paneles de control de Anuncios de Meta y de AppsFlyer.

Si bien trabajamos en estrecha colaboración con Anuncios de Meta para minimizar estas discrepancias, los anunciantes deben ser conscientes de los factores que suelen originarlas.

<div id="detect-a-discrepancy-between-appsflyer-and-meta-ads" />

### Detectar una discrepancia entre AppsFlyer y Anuncios de Meta

Compara los eventos listados en el **Administrador de eventos** de Anuncios de Meta con los de los reportes de AppsFlyer. Si el número de eventos varía significativamente, puede haber una discrepancia.

<div id="differences-in-attribution-models" />

## Diferencias en los modelos de atribución

<table><thead><tr><th>Causa</th><th>Meta Ads</th><th>AppsFlyer</th></tr></thead><tbody><tr><td><span id="click-attribution-lookback-window"></span><strong>Ventana retrospectiva de atribución por clics</strong></td><td>7 días (Ten en cuenta que <a href="https://www.facebook.com/business/help/395050428485124?id=428636648170202" target="_blank">hay algunos casos específicos en los que el valor predeterminado es diferente</a>).</td><td>1-30 días. Asegúrate de configurarlo en 7 días con Anuncios de Meta.</td></tr><tr><td><span id="viewthrough-attribution-lookback-window"></span><strong>Ventana retrospectiva de atribución por impresiones</strong></td><td>1 día (Ten en cuenta que <a href="https://www.facebook.com/business/help/395050428485124?id=428636648170202" target="_blank">hay algunos casos específicos en los que el valor predeterminado es diferente</a>).</td><td>1 día por defecto, pero puede configurarse en intervalos de entre 1 hora y 48 horas (mantener este valor por defecto)</td></tr><tr><td><span id="multichannel-sourceattribution"></span> <strong>Fuente multicanal</strong><br/><strong>atribución</strong> </td><td>Anuncios de Meta se autoatribuye instalaciones a pesar de ser de fuentes de otros medios.</td><td>AppsFlyer usa la atribución al último clic (puedes encontrar más información sobre la atribución de AppsFlyer <a href="./appsflyer-attribution-model" title="Modelo de atribución de AppsFlyer" target="_blank">aquí</a>).</td></tr><tr><td><span id="crossdevice-attribution"></span><strong>Atribución de dispositivos cruzados</strong></td><td>Anuncios de Meta atribuye sus usuarios que hacen clic e instalan en distintos dispositivos; por ejemplo, iOS/Android/escritorio.</td><td>AppsFlyer atribuye por tipo de dispositivo, aquellos en los que tenga lugar tanto el engagement como la instalación</td></tr><tr><td><span id="different-time-zones"></span><strong>Distintas zonas horarias</strong></td><td>La zona horaria predeterminada de los reportes de Anuncios de Meta es PST. Asegúrate de <a href="https://www.facebook.com/business/help/754049591334898" target="_blank">cambiarla en el Administrador de anuncios de Meta</a> para que coincida con la zona horaria de la aplicación definida en la configuración de la aplicación en AppsFlyer.</td><td>La zona horaria predeterminada de la aplicación de AppsFlyer es UTC+0. Puedes cambiar la zona horaria establecida para la aplicación en la <a href="./app-settings#localization-time-zone" target="_blank">página de configuración de la aplicación</a>, para que coincida con la zona horaria definida en el Administrador de anuncios de Meta.</td></tr><tr><td><span id="google-install-referrer"></span><strong>Referente de instalación de Google</strong></td><td colspan="2">Cuando una instalación sin ID de anunciante se atribuyó a Anuncios de Meta mediante el referente de instalación de Google Play, AppsFlyer no lo comunica a Anuncios de Meta. Esto causará una discrepancia, ya que se mostrará en AppsFlyer y no en Anuncios de Meta.</td></tr></tbody></table>

<div id="click-through-and-view-through-attribution" />

## Atribución por clics y por impresiones

AppsFlyer admite tanto atribuciones por clics como por impresiones. Para minimizar las discrepancias entre Anuncios de Meta y AppsFlyer, asegúrate de que tanto la ventana retrospectiva por impresiones como la ventana retrospectiva por clics sean coherentes con las predeterminadas definidas por Anuncios de Meta.

La ventana retrospectiva por clics predeterminada de Anuncios de Meta está configurada en 7 días. Aunque [hay algunos casos específicos en los que el valor predeterminado es diferente](https://www.facebook.com/business/help/395050428485124?id=428636648170202), se recomienda configurar la ventana retrospectiva por clics en AppsFlyer en 7 días para cubrir todas las opciones predeterminadas de Anuncios de Meta.

Recomendamos configurar las ventanas de atribución en AppsFlyer según valores de Anuncios de Meta como se muestra en la siguiente pantalla: <Anchor target="_blank" href="https://www.facebook.com/business/help/654970342692714">Consulta la documentación de Meta for Developers sobre cómo comparar la configuración de atribución.</Anchor>

<Image align="center" alt="image (13).png" src="https://files.readme.io/215d2234aae1ec6b4e1c6ac922915851bf8ab02574a874119d286fa49c64f9ba-25899749062033.png" />

<div id="example" />

> 📄 **Ejemplo**
>
> Supongamos que la ventana retrospectiva por clics de Anuncios de Meta se configura en AppsFlyer en 1 día para tu aplicación com.greatapp, mientras que en Anuncios de Meta mantiene el valor predeterminado de 7 días. Los usuarios que hacen clic en el anuncio de greatapp en Facebook, pero inician la aplicación por primera vez después de 2-7 días se atribuyen como usuarios orgánicos en AppsFlyer, a la vez que Anuncios de Meta autorreporta estos usuarios.

<div id="in-app-events-differences" />

## Diferencias de eventos in-app

Las diferencias entre plataformas también pueden estar presentes con eventos posteriores a la instalación (por ejemplo, compras in-app), que se muestran en Anuncios de Meta y en AppsFlyer. La siguiente tabla describe los motivos más frecuentes de estas diferencias y brinda consejos sobre cómo minimizarlos:

| Causa | Descripción | Consejo de AppsFlyer |
| --- | --- | --- |
| <span id="different-lifetime-definition"></span>**Definición de tiempo de vida diferente** | El ciclo de vida de un usuario en Anuncios de Meta se define como de hasta 7 días, lo que significa que Anuncios de Meta no muestra los eventos si ocurrieron más de 7 días después del clic en el anuncio.  <br />En AppsFlyer, la vida de un usuario de Anuncios de Meta se define como un máximo de 180 días. | Cuando evalúes el valor de los usuarios de las campañas de Anuncios de Meta que ocurrieron después de 7 días, usa los datos de AppsFlyer para obtener una visión más amplia. |
| <span id="unmapped-events"></span>**Eventos no asignados** | AppsFlyer obtiene eventos originados en el SDK, pero no están asignados a Anuncios de Meta y, por lo tanto, no son enviados. | Asegúrate de <Anchor target="_blank" href="/marketers/es/docs/meta-ads-in-app-event-mapping">asignar con Anuncios de Meta</Anchor> todos los eventos in-app que indican la calidad de los usuarios. |
| <span id="unsent-revenue"></span>**Ingresos no enviados** | AppsFlyer recibe los ingresos de eventos originados en el SDK, pero estos no se envían a Anuncios de Meta. | Asegúrate de que las casillas **Enviar ingresos** de los eventos in-app estén siempre marcadas; por ejemplo, el evento de compra en la siguiente captura. |
| <span id="missing-event-values-on-facebook"></span>**Faltan los valores de eventos en Anuncios de Meta** | AppsFlyer envía parámetros y valores a Anuncios de Meta como parte de la asignación de eventos, si tienen las estructuras correctas. | Crea tus eventos in-app de SDK según las <Anchor target="_blank" href="/marketers/es/docs/in-app-events-event-structure">estructuras recomendadas por AppsFlyer</Anchor> para asignar completamente los valores de eventos con Anuncios de Meta. |
| <span id="different-event-count"></span>**Atribución de fuente multicanal** | El recuento de un evento in-app específico (por ejemplo, un evento de compra) en el dashboard de Facebook (FB) difiere de su recuento correspondiente en el dashboard de AppsFlyer (AF). | El dashboard de Facebook (FB) se basa en la actividad, mientras que los dashboards Overview y Event de AppsFlyer (AF) se basan en el LTV. Para comparar recuentos de eventos, usa un dashboard de AF basado en la actividad. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports#acerca-de-las-diferencias-y-discrepancias-de-datos">LTV frente a actividad</Anchor> |

<div id="installs-from-re-engagement-campaigns-in-my-ua-dashboard" />

## ¿Instalaciones de campañas de re-engagement en mi panel de control de UA?

Una campaña de re-engagement puede hacer que los usuarios abran una aplicación ya instalada (**re-engagement**). Además, cuando AppsFlyer reconoce que ya hay una instalación anterior de la aplicación en el mismo dispositivo, AppsFlyer puede tomar esta conversión como una **reatribución**.

Si, en una campaña de re-engagement, Anuncios de Meta se dirige a **nuevos usuarios** o a usuarios que han instalado la aplicación por primera vez **después de un período superior** **al de la <Anchor target="_blank" href="/marketers/es/docs/set-up-re-attribution-window">ventana de reatribución</Anchor>** establecida, luego de la instalación original, los usuarios en cuestión se registran como **nuevas instalaciones de adquisición de usuarios** en AppsFlyer, que corresponden a campañas de re-engagement en Anuncios de Meta.

Por otro lado, las instalaciones que tienen lugar **dentro de la ventana de reatribución establecida**,  después de la instalación original, se consideran reatribuciones y aparecen en la página de retargeting de AppsFlyer, mientras que pueden aparecer como nuevas instalaciones en Anuncios de Meta.

<div id="note" />

> 📘 **Nota**
>
> Si bien Anuncios de Meta muestra todas las instalaciones de una campaña de retargeting en el mismo lugar, en el panel de control de AppsFlyer, las instalaciones se dividen entre la página de información general (nuevas instalaciones) y la página de retargeting (reatribución y re-engagements).

<div id="cross-device-attribution" />

## Atribución de dispositivos cruzados

Anuncios de Meta informa sobre la atribución de dispositivos cruzados. A veces esto puede causar problemas cuando una campaña para una plataforma (iOS/Android) muestra instalaciones en otra plataforma.

<div id="example-1" />

> 📄 **Ejemplo**
>
> Linda hace clic en un anuncio móvil de GreatApp en Facebook desde su teléfono Android. Anuncios de Meta registra el clic de Linda bajo la campaña dirigida original de Android "Mujeres con Android". Linda decide instalar GreatApp en el iPad de su casa. En el primer inicio, AppsFlyer solicita a Anuncios de Meta el origen de esta instalación de iOS y Anuncios de Meta responde con la campaña "Mujeres con Android".

<div id="validation-rules-and-protect360" />

## Protect360 y reglas de validación

Si utilizas las <Anchor target="_blank" href="/marketers/es/docs/implement-validation-rules-to-prevent-fraud">reglas de validación de AppsFlyer</Anchor>, los resultados pueden diferir entre AppsFlyer y Anuncios de Meta cuando hay instalaciones rechazadas que originalmente provienen de Anuncios de Meta. En estos casos, Anuncios de Meta se autorreporta instalaciones, mientras que AppsFlyer rechaza esas mismas instalaciones.

Asimismo, si se utiliza la solución antifraude de AppsFlyer, Protect360, puede haber instalaciones dado que Anuncios de Meta autorreporta, mientras que AppsFlyer rechaza.

<div id="example-2" />

> 📄 **Ejemplo**
>
> Jeff, gerente de UA de GreatApp, crea una campaña llamada SPNA dirigida exclusivamente a personas de habla hispana de América del Norte. Para verificar esto, Jeff define una regla de validación, que acepta solo usuarios de Canadá y los Estados Unidos.
> Cuando un usuario de Anuncios de Meta de España hace clic e instala la aplicación, Anuncios de Meta se autorreporta la instalación, mientras que AppsFlyer rechaza la instalación que no pasa la regla de validación.

<div id="sdk-related-discrepancies" />

## Discrepancias relacionadas con el SDK

Podría haber <Anchor target="_blank" href="/marketers/es/docs/meta-ads-faq#who-needs-facebooks-sdk">varias ocasiones en las que los anunciantes implementen tanto el SDK de AppsFlyer como el de Facebook</Anchor>. Esto podría causar discrepancias para los eventos in-app. Anuncios de Meta no desduplica los eventos in-app que se reportan desde ambos SDK. Esto significa que Anuncios de Meta puede reportar falsamente los ingresos y otros eventos.

* Usa cualquiera de los métodos siguientes para evitar reportes de eventos in-app duplicados en Anuncios de Meta:
  * No configures eventos en el SDK de Facebook.
  * Deshabilita la <Anchor target="_blank" href="/marketers/es/docs/meta-ads-in-app-event-mapping">asignación de eventos in-app de Anuncios de Meta</Anchor> desde AppsFlyer.

<div id="meta-probabilistic-modeling-aem-discrepancies-in-ios-apps" />

## Discrepancias del modelado probabilístico de Meta (AEM) en aplicaciones iOS

Cuando la medición de eventos agregados (AEM) está habilitada para aplicaciones iOS, Meta puede atribuir instalaciones o eventos in-app mediante su modelado probabilístico. **Meta puede aplicar distintos métodos de modelado en sus informes internos en comparación con lo que comparte con AppsFlyer.** Debido a estas diferencias en los métodos de modelado, los recuentos de instalaciones que se muestran en Meta Ads Manager y AppsFlyer pueden variar; a veces son más altos y otras, más bajos. En concreto:

* Meta puede registrar conversiones internamente, pero optar por no enviar a AppsFlyer las reclamaciones de AEM correspondientes.
* Meta puede enviar a AppsFlyer una reclamación de AEM por una conversión modelada que no aparece en Ads Manager.

<div data-zendesk-anchors="facebook-ads-discrepancies-with-appsflyer=discrepancias-de-anuncios-de-meta-con-appsflyer 01H890CZSXPMK0BDMC4202HNYM=discrepancias-de-anuncios-de-meta-con-appsflyer detect-a-discrepancy-between-appsflyer-and-facebook=detectar-una-discrepancia-entre-appsflyer-y-anuncios-de-meta 01H890CZSXGHVBH21SQA0671JQ=detectar-una-discrepancia-entre-appsflyer-y-anuncios-de-meta differences-in-attribution-models=diferencias-en-los-modelos-de-atribuci%C3%B3n 01H890CZSX8M6VGGREYX4W2X37=diferencias-en-los-modelos-de-atribuci%C3%B3n clickthrough-and-viewthrough-attribution=atribuci%C3%B3n-por-clics-y-por-impresiones 01H890CZSX40JDGY8P8AQ4CYGS=atribuci%C3%B3n-por-clics-y-por-impresiones 01H890CZSXRD7PCZBK52GW7QE9=ejemplo inapp-events-differences=diferencias-de-eventos-in-app 01H890CZSXKC5JKK9051MC0VY6=diferencias-de-eventos-in-app installs-from-reengagement-campaigns-in-my-ua-dashboard=instalaciones-de-campa%C3%B1as-de-re-engagement-en-mi-panel-de-control-de-ua 01H890CZSYE21K7PBQK4PNMGJR=instalaciones-de-campa%C3%B1as-de-re-engagement-en-mi-panel-de-control-de-ua 01H890CZSY7TRCA4NVKSVPY7DB=nota crossdevice-attribution::77a37a1f=atribuci%C3%B3n-de-dispositivos-cruzados 01H890CZSYS8QKEAF6799SBS8J=atribuci%C3%B3n-de-dispositivos-cruzados 01H890CZSY2Z3S6E9R5MYC1CHX=ejemplo-1 validation-rules-and-protect360=protect360-y-reglas-de-validaci%C3%B3n 01H890CZSYDHZE4V0ZWTT8V0EJ=protect360-y-reglas-de-validaci%C3%B3n 01H890CZSYCTQZCAYAZP9TCBBF=ejemplo-2 sdk-related-discrepancies=discrepancias-relacionadas-con-el-sdk 01H890CZSYVFPQP0SKNPWMPB1R=discrepancias-relacionadas-con-el-sdk meta-probabilistic-modeling-aem-discrepancies-in-ios-apps=discrepancias-del-modelado-probabil%C3%ADstico-de-meta-aem-en-aplicaciones-ios h_01KA6NEZSRFSAJYZ5C4HJ4SKTQ=discrepancias-del-modelado-probabil%C3%ADstico-de-meta-aem-en-aplicaciones-ios" />
