---
title: Resolución de discrepancias en los dashboards y reportes de AppsFlyer
metadata:
  keywords:
    - dashboard
    - activity
    - Advertisers
    - ltv
    - life time value
    - lifetime value
    - lifetime
    - Agencies
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
    - Agencies
  created_at: '2017-11-07T12:42:27Z'
  edited_at: '2026-08-12T11:51:08Z'
  id: 115005600889
  locale: es
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/es/articles/115005600889
---
> **En resumen:** Comprende por qué puede haber diferencias y discrepancias al comparar datos de diferentes dashboards y reportes. A menudo, esto puede deberse a que los datos en un lugar son datos de lifetime value (LTV) y en otro son datos de actividad. Los datos de LTV están relacionados con las instalaciones que ocurrieron durante un rango de fechas específico. Los datos de actividad son eventos que ocurrieron durante un rango de fechas específico.

## Acerca de las diferencias y discrepancias de datos

Al comparar datos de diferentes dashboards y reportes, la razón general de las discrepancias es que es posible que no estés comparando los mismos datos con los mismos datos. A seguir, puedes ver una lista de verificación rápida para ayudarte a asegurarte de que estás comparando lo equivalente:

* ¿Las plataformas de aplicaciones son las mismas (Android, iOS, CTV, etc.)?
* ¿Los IDs de aplicación son los mismos?
* ¿El dashboard/filtros de datos son los mismos?
* ¿Las monedas son las mismas?
* ¿Las zonas horarias son las mismas?
* ¿La <Anchor target="_blank" href="/marketers/es/docs/about-data-freshness-and-timezone-support">actualización de datos</Anchor> es la misma?
* ¿Los datos son <Anchor target="_blank" href="/marketers/es/docs/aggregated-and-analytics-reporting-overview#toolapi-comparison">datos agregados</Anchor> o <Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-overview">raw data</Anchor>?
* ¿Los datos son LTV o actividad?

Una de las razones más comunes de las diferencias en los datos se debe a la comparación de un dashboard o reporte de LTV con un dashboard o reporte de actividad. Consulta las siguientes secciones para obtener más información sobre el LTV vs la actividad.

## LTV vs Actividad

Los datos de eventos de usuarios se pueden analizar mediante dos métodos. Los datos de eventos se relacionan con cualquier acción llevada a cabo por los usuarios después de la instalación, como compras in-app, registros y niveles completados. En AppsFlyer, los datos de eventos están disponibles agrupados por la fecha de adquisición del usuario o la fecha del evento.

* Los datos de eventos posteriores a la instalación agrupados por fecha de adquisición del usuario se denominan LTV (lifetime value).
* Los datos de eventos posteriores a la instalación agrupados por fecha del evento se denominan actividad.

**Nota**: Las instalaciones no son LTV ni actividad.

Los anunciantes consideran que ambos tipos de datos son útiles, pero para diferentes fines. Por esta razón, ambos están disponibles.

### Datos de LTV

* Los datos de LTV son los eventos que se realizan durante el ciclo de vida de un usuario que convirtió/instaló la aplicación en un intervalo específico de fechas. El rango de fechas se refiere a los usuarios que instalaron la aplicación durante el período de tiempo y muestra lo valiosos que son durante el tiempo que son como clientes. Si un usuario convirtió/instaló la aplicación antes de la fecha especificada, incluso si los eventos ocurrieron durante el intervalo de fechas especificado, no se muestran en los dashboards y reportes de LTV.
* Los datos de LTV son la herramienta que muestra la **calidad de los usuarios** de diferentes fuentes de medios. La optimización de la campaña depende de los datos de LTV.

### Datos de actividad

* Los datos de actividad muestran lo que hicieron los usuarios durante un rango de fechas específico. Los datos de actividad muestran lo que hicieron los usuarios durante un intervalo de fechas específico, es decir, qué eventos realizaron los usuarios activos de la aplicación durante un intervalo de fechas específico. No importa si los usuarios convirtieron/instalaron la aplicación fuera del rango de fechas.
* Debido a que los datos de actividad muestran un desglose de eventos cronológicos, resultan útiles para medir el rendimiento general de las fuentes de medios durante intervalos específicos de fechas. Por ejemplo, puedes usar los datos de actividad para ver cuántos eventos de compra realizaron todos los usuarios de la aplicación durante un mes específico.
* Usa los datos de actividad para comparar el comportamiento del usuario en el mes actual en relación con un mes anterior.

> 📄 **La analogía del tren**
>
> Esta analogía te ayudará a comprender la diferencia entre el LTV y los datos de actividad.
>
> **Actividad**: Imagina que ves que pasa un tren. Cuando el tren pasa, solo puedes ver las acciones que realizan los pasajeros en el tren cuando pasan. Estos son los datos de actividad.
>
> <Image alt="activity_data.jpg" src="https://files.readme.io/70a37d5dc16f0817d137f9011be9af5360bd7c4d2469a8abf9430fe69b2671c3-360002436957.jpg" width="400px" />
>
> **LTV**: Ahora, imagina que subes a un tren como observador. El tren está dividido en vagones.
>
> * Subes al vagón con otros pasajeros en el andén de salida. Esta es la instalación.
> * Durante el viaje, puedes observar todas las acciones que realizan los pasajeros en el vagón. Observas las acciones de estos pasajeros hasta que un pasajero se baja del tren, esto es una desinstalación.
> * No puedes ver las acciones de los pasajeros en otros vagones del ferrocarril porque se subieron al tren antes o después de ti. Esto es el LTV.
>
> <Image alt="ltv_data.jpg" src="https://files.readme.io/78925644f263b6d5ea5630a09e0b2155d153ce2c4b3060be5c8d7cb9ba0ce4e6-360002436977.jpg" width="400px" />

### Dashboards y reportes de AppsFlyer: ¿LTV o actividad?

Los dashboards permiten a los marketers optimizar su tráfico no orgánico. La mayoría de los dashboards se basan en el LTV, ya que los marketers generalmente miden el rendimiento en base al LTV. Todos los reportes de datos agregados se basan en el LTV y todos los reportes de raw data se basan en actividades.

La siguiente tabla muestra qué dashboards y reportes son de LTV y cuáles son de actividad.

| Fuente de datos | Tipo de datos |
| --- | --- |
| Dashboard general | Característica |
| [Beta] My Dashboards | Característica |
| Resumen de SKAN | Característica |
| Instalaciones de Protect360 | Característica |
| Eventos in-app de Protect360 | Actividad |
| Dashboard de actividad | Actividad |
| Dashboard de eventos | Característica |
| Panel personalizado | Característica |
| Retención | Característica |
| Cohorte | Característica |
| Reportes de raw data | Característica |
| SKAN general | Actividad |
| Reportes de retargeting | Característica |
| Reportes de prevención de fraude de Protect360 | Actividad |
| API maestra: KPIs de rendimiento de la campaña | Ambos |
| Tabla pivot | Ambos |

## Compara datos entre diferentes dashboards y reportes

Las siguientes secciones explican cómo puedes comparar datos entre diferentes dashboards y reportes, al tiempo que mitigas y resuelves problemas de manera efectiva las razones por las que puedes ver diferencias o discrepancias en los datos.

<div id="compare-ltv-and-activity-data-in-appsflyer" />

<Accordion title="Comparación de LTV y datos de actividad en AppsFlyer">

Al comparar los datos de AppsFlyer, ten en cuenta que al comparar los datos de LTV y los datos de actividad, hay 2 diferencias a considerar:

1. Los datos de actividad incluyen eventos de **instalaciones que ocurrieron antes** del intervalo de fechas.
2. Los datos de LTV incluyen **eventos que ocurrieron después** del intervalo de fechas.

Para comparar ambos tipos de datos correctamente, es necesario neutralizar las diferencias. Para lograrlo, podemos extraer los datos del LTV de los datos de actividad o viceversa. **Nota**: Aún es posible que haya diferencias menores entre fuentes similares debido a las diferencias a la hora de generar los reportes.

#### Para recuperar los datos del LTV a partir de los raw data de actividad:

1. En AppsFlyer, en el menú lateral, selecciona **Reporte** > **Exportación de raw data**.
2. Configura el **día actual como el último día** del intervalo de fechas (esto resuelve la segunda diferencia).
3. Descarga el reporte de raw data de eventos in-app.
4. Usa la columna **Hora de instalación** para filtrar y dejar afuera las instalaciones anteriores al primer día del intervalo de fechas (esto resuelve la primera diferencia).

#### Para recuperar los datos de actividad a partir de los datos de LTV:

1. **Selecciona fuentes que comenzaron a enviar instalaciones dentro del intervalo de fechas especificado en AppsFlyer** (esto resuelve la primera diferencia).  
   Esto garantiza que los datos de actividad no incluyan eventos efectuados dentro del intervalo de fechas que pertenecen a instalaciones ocurridas con anterioridad al intervalo de fechas.
2. Configura el **día actual como el último día** del intervalo de fechas (esto resuelve la segunda diferencia).  
   Esto garantiza que los datos del LTV no incluyan eventos efectuados después del intervalo de fechas que pertenezcan a instalaciones ocurridas dentro del intervalo de fechas.

</Accordion>

<div id="compare-different-appsflyer-aggregated-data-dashboards-and-reports" />

<Accordion title="Compara diferentes reportes y dashboards de datos agregados de AppsFlyer">

Al comparar datos entre diferentes dashboards y reportes de datos agregados de AppsFlyer, el LTV vs la actividad pueden ser la razón de las discrepancias.

Si estás agregando datos por geolocalización, otra razón de discrepancia podría ser que en los dashboards de AppsFlyer, agregar por geolocalización significa la geolocalización donde ocurrió la instalación, mientras que en los reportes de raw data significa la geolocalización donde ocurrió el evento.

Sin embargo, ten en cuenta que también pueden haber otras razones. <Anchor target="_blank" href="/marketers/es/docs/aggregated-and-analytics-reporting-overview#toolapi-comparison">Consulta la comparación de métodos de reportes agregados para más información</Anchor>

</Accordion>

<div id="compare-appsflyer-data-with-external-data" />

<Accordion title="Compara los datos de AppsFlyer con los datos externos">

La inmensa mayoría de fuentes de datos, incluidos los datos de actividad de visualización, de Google y Apple, no consiste en datos del LTV. Por lo tanto, para comparar los datos de fuentes externas con los de AppsFlyer, por lo general usarás los datos de actividad de AppsFlyer, que se encuentran disponibles en los reportes de raw data.

Ten en cuenta que Meta Ads ofrece datos de LTV parciales, limitados a un período de 28 días posteriores a la instalación.

También pueden haber otras razones de discrepancia entre los datos de AppsFlyer y los datos externos. Consulta también:

* <Anchor target="_blank" href="/marketers/es/docs/google-analytics-integration-discrepancies">Discrepancias de análisis de Google</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/meta-ads-discrepancies">Discrepancias de Meta Ads</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/snapchat-integration-discrepancies">Discrepancias de Snapchat</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/google-ads-adwords-faq-and-discrepancies">Discrepancias de Google Ads</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/x-ads-formerly-twitter-ads-faq-and-discrepancies">Discrepancias de X Ads</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/attribution-discrepancies-between-tiktok-for-business-and-appsflyer">Discrepancias de TikTok</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/resolve-appsflyer-app-stores-discrepancies">Discrepancias de la tienda de aplicaciones</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/discrepancies-between-appsflyer-and-third-party-platforms">Discrepancias de plataformas de third-party</Anchor>

</Accordion>

<div id="compare-inapp-event-raw-data-with-the-activity-view" />

<Accordion title="Compara la raw data de eventos in-app con la vista de actividad">

Los eventos in-app aparecen tanto en LTV como en la vista de actividad del Dashboard. Sin embargo, cada uno emplea una lógica de recuento diferente.  
Al reconciliar los recuentos de eventos con la raw data, compáralos siempre con el dashboard de actividad o con la vista de actividad de My Dashboards, ya que estas vistas representan las ocurrencias de eventos el día en que se produjeron.

Las diferencias suelen surgir cuando la raw data no se filtra correctamente, especialmente en el caso de los eventos de retargeting.

#### **Reconciliar la raw data con las métricas de eventos de actividad**

Para comparar los totales de eventos in-app:

1. **Reportes de rendimiento de datos agregados**

* Eventos no orgánicos in-app
* Eventos de retargeting en la aplicación
* Eventos orgánicos en la aplicación

2. **Filtra los eventos de retargeting para evitar el recuento duplicado.**  
   En escenarios de retargeting, se produce una doble atribución. Un evento in-app se atribuirá a ambos:

* La fuente de medios de retargeting (**atribución principal**)
* La fuente de medios que impulsó la instalación original (**atribución secundaria**)

Para evitar contar el mismo evento dos veces en tus reportes, filtra el campo **Is primary attribution = True** en tu raw data.  
Aplica este filtro antes de agregar los reportes de UA para que solo se incluya la instancia de atribución principal. Esto evita que los eventos de retargeting duplicados inflen los totales.

3. **Agrega los totales de eventos.**  
   Suma los eventos de todos los conjuntos filtrados.
4. **Compara el total agregado** con el recuento de eventos que se muestra en el **dashboard de actividad**.

</Accordion>

<div data-zendesk-anchors="ltv-vs-activity=acerca-de-las-diferencias-y-discrepancias-de-datos h_01HKA0R42YZMAM5Y20B7T2JCDZ=acerca-de-las-diferencias-y-discrepancias-de-datos h_01J5WGZ13WPMNSB1NA0SMA77WJ=ltv-vs-actividad ltv-data=datos-de-ltv h_01HKA0R42YQ2CJS67MDQSJHKEW=datos-de-ltv activity-data=datos-de-actividad h_01HKA0R42Y987PJRM70M7DFJ98=datos-de-actividad h_01J5WGZ13W5W8NJ1CRZQPHY939=la-analog%C3%ADa-del-tren appsflyer-dashboards%E2%80%94ltv-or-activity=dashboards-y-reportes-de-appsflyer-ltv-o-actividad h_01HKA0R42Y558BQ45Y9MFZHZM0=dashboards-y-reportes-de-appsflyer-ltv-o-actividad compare-data-between-different-dashboards-and-reports=compara-datos-entre-diferentes-dashboards-y-reportes h_01J5WKA06A7XYFN07V60VQ4FY5=compara-datos-entre-diferentes-dashboards-y-reportes h_01J5WHVQSNEA2WK83RBRDM1GT3=compare-ltv-and-activity-data-in-appsflyer retrieving-ltv-data-out-of-raw-activity-data=para-recuperar-los-datos-del-ltv-a-partir-de-los-raw-data-de-actividad h_01HKA0R42Z3ZSMEM7T5F0V3VM7=para-recuperar-los-datos-del-ltv-a-partir-de-los-raw-data-de-actividad retrieving-activity-data-out-of-ltv-data=para-recuperar-los-datos-de-actividad-a-partir-de-los-datos-de-ltv h_01HKA0R42ZHFM4RHG78GE51XK3=para-recuperar-los-datos-de-actividad-a-partir-de-los-datos-de-ltv h_01J5WK0AEN2N6J4P06CC3DMWPJ=compare-different-appsflyer-aggregated-data-dashboards-and-reports h_01J5WHVQSNZW66CQ4VGQGAKZB1=compare-appsflyer-data-with-external-data h_01KCNZWKFAWQ3KBJPCXP4BP8RM=compare-inapp-event-raw-data-with-the-activity-view reconcile-raw-data-with-activity-event-metrics=reconciliar-la-raw-data-con-las-m%C3%A9tricas-de-eventos-de-actividad h_01KCNZXRJKTGPH104H5Y1QNTM9=reconciliar-la-raw-data-con-las-m%C3%A9tricas-de-eventos-de-actividad" />
