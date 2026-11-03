---
title: Guía de Fuente Única de Verdad (SSOT) para atribución en iOS
metadata:
  keywords:
    - iOS
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-11-11T09:28:42Z'
  edited_at: '2026-08-12T12:21:17Z'
  id: 4410634145425
  locale: es
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/es/articles/4410634145425
---
> **De un vistazo**: En el contexto del entorno iOS 14+, AppsFlyer integra datos de múltiples métodos de atribución como IDFA, IDFV, SKAN, Apple Search Ads, entre otros, para ofrecer una visión completa del rendimiento de las campañas de aplicaciones. Ningún método de atribución por sí solo proporciona una imagen completa del rendimiento de la aplicación. El reto es contar a un usuario solo una vez, ya que ese mismo usuario puede ser atribuido a través de dos métodos diferentes. El mecanismo de Fuente Única de Verdad (SSOT) de AppsFlyer se encarga precisamente de eso. Los informes y métricas SSOT son precisos y fiables, contando a cada usuario único solo una vez.

<Embed title="Guía de Fuente Única de Verdad (SSOT) para atribución en iOS" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/545isomgo1" providerUrl="https://fast.wistia.com" />

## Sobre la Fuente Única de Verdad: Datos reales del rendimiento en iOS

A partir de iOS 14, AppsFlyer atribuye a los usuarios de iOS usando datos de diferentes fuentes, como SKAdNetwork, usuarios que consienten en ATT, modelado probabilístico, información basada en incrementalidad y API dedicadas para Apple Search Ads. La falta de IDFA hace que sea casi imposible vincular los métodos de atribución sin duplicar datos.

El mecanismo SSOT elimina la duplicación de datos de instalación y corrige la atribución de los usuarios erróneamente atribuidos. Es decir, se trata de usuarios que fueron atribuidos como orgánicos cuando deberían haber sido asignados a una fuente de medios no orgánica. Como resultado, se corrige el número de instalaciones atribuidas a una campaña y las métricas relacionadas con costos e ingresos, como eCPI, ROI y ROAS, se calculan con precisión.

En resumen, el mecanismo SSOT identifica las instalaciones de SKAN que también se atribuyen mediante otro tipo de coincidencia. Esta identificación se considera al calcular las métricas agregadas para evitar contar al mismo usuario dos veces. De forma similar, se utiliza este indicador al procesar los datos sin procesar de SKAN.

Para incluir la bandera SSOT en tus datos, debes activar SSOT en Conversion Studio.

<div id="turn-on-single-source-of-truth" />

<Accordion title="Activa la Fuente Única de Verdad">

![SSOTControl.png](https://files.readme.io/fd99117e9278ebda3b1f0cc137afb266643e5e45325345ec51aeb58c16d4f13c-31247514683153.png)

**Para activar SSOT:**

1. Antes de comenzar, ten en cuenta la política de facturación de <Anchor target="_blank" href="https://content.appsflyer.com/ios-hub/billing/">Fuente Única de Verdad</Anchor> de AppsFlyer.
2. En AppsFlyer, ve a **Configuración** > **SKAN Conversion Studio**.
3. Selecciona el modo **Personalizado**.
4. Activa la **Fuente Única de Verdad.**
5. Completa la configuración según sea necesario.

Consulta <Anchor target="_blank" href="/marketers/es/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>

</Accordion>

## Panel de vista general para la Fuente Única de Verdad

![SSOTisNowOn.png](https://files.readme.io/8e21fd0c64bb85fb94af752eb037472726d68cd55bf028dc5306b0acb398d199-31247490958225.png)

La vista Fuente Única de Verdad disponible a través del panel de vista general proporciona un panorama completo de las métricas de rendimiento no orgánicas. En la vista:

* Las métricas de instalación son exactas.
* Las métricas relacionadas con costes e ingresos, que dependen de las métricas de instalación, como el eCPI, ARPU y ROAS, se calculan correctamente.
* Métricas orgánicas ajustadas tras tener en cuenta las instalaciones mal atribuidas.

Esta sección destaca las diferencias y características únicas de la vista SSOT. Supone que estás familiarizado con el panel de vista general.

<div id="turn-on-single-source-of-truth-view" />

<Accordion title="Activar vista Fuente Única de Verdad">

Los datos en la vista SSOT están disponibles entre 3 y 5 días después de habilitar la Fuente Única de Verdad en Conversion Studio.

**Para habilitar la vista de Fuente Única de Verdad**:

1. Antes de empezar, verifica que en Conversion Studio esté activada la opción <Anchor target="_blank" href="/marketers/es/docs/skan-conversion-studio#single-source-of-truth">Fuente Única de Verdad</Anchor>.
2. En AppsFlyer, ve a **Panel de control** > **Vista general.**   
   <Image alt="SeleccionarInformeGuardado.png" src="https://files.readme.io/863a9c66c37e031a1f1b2a7fb3e0c68eb9c29405283214e68a432357c35524dd-31247514684177.png" width="243px" />
3. Haz clic en ▼.
4. Selecciona Vista general Lite.  
   Se muestra el interruptor de Fuente Única de Verdad.  
   <Image alt="VistaSSOTon.png" src="https://files.readme.io/7b0a664f0882dad46e7239b5363592717358a79d920377dde13aa9c5dfbe84c3-31247514684433.png" width="246px" />
5. Activa la Fuente Única de Verdad.
6. Ocurrirá una de las siguientes situaciones:
   * Se muestran las métricas y gráficos del panel.  
     Las secciones que siguen describen los datos disponibles. Consulta las secciones que siguen sobre los datos que se muestran.  
     Guarda la vista SSOT como un nuevo informe. Para hacerlo:  
     1. Haz clic en ▼.
     2. Haz clic en **+ Guardar nuevo informe.**
     3. Introduce un nombre para el informe.
     4. Haz clic en **Guardar**.
   * Los datos no se muestran. Ten en cuenta que pueden pasar de 3 a 5 días tras activar SSOT hasta que los datos se muestren. Espera a que pase este período y visita el panel de control de nuevo.

Desactiva el interruptor SSOT en cualquier momento para ver datos habituales con las dimensiones que no están disponibles en la vista SSOT.  De este modo, podrás profundizar en el análisis.

</Accordion>

<div id="ssot-view-considerations" />

<Accordion title="Consideraciones de la vista SSOT">

En la vista SSOT:

* **Valores de conversión nulos (CV)**: Modelado. Se emplea aprendizaje automático avanzado para modelar un valor nulo atribuido por AppsFlyer o SKAN utilizando el indicador [af\_attribution](/docs/single-source-of-truth-ssot-guide-for-ios-attribution#campo-del-indicador-de-atribución). Si se atribuyen a SKAN, todas las mediciones de SKAN post-instalación se incluyen en el panel de control de SSOT. <Anchor target="_blank" href="/marketers/es/docs/skan-modeled-data">Más información</Anchor>
* **Descargas repetidas**: Incluido en la métrica de instalaciones. No hay distinción entre instalaciones y redescargas.
* **Zona horaria**: Las instalaciones y eventos reportados por AppsFlyer se muestran en UTC o en la zona horaria local de la app, configurada en la página de configuración de la app . Para los datos reportados por SKAN, las instalaciones y eventos se muestran en UTC, a excepción de los datos de SKAN de Meta y Google, cuya zona horaria está basada en la configurada en tus cuentas de Meta y Google, respectivamente.
* **Moneda**: Se muestra en USD o en la moneda local de la app, configurada en la página de configuración de la app .
* **Métricas de ingresos (D2, D7):** Incluye datos modelados para tener en cuenta los postbacks de SKAN incompletos o faltantes (valores de conversión nulos) Las cohortes más largas (D14, D21, D30) se exportan mediante el reporte de SSOT Data Locker

#### Consideraciones sobre los filtros

Ten en cuenta el impacto de los filtros en la visualización de datos y métricas, como se describe en las tablas que siguen.

| Filtro | Consideración |
| --- | --- |
| Fuente Única de Verdad | Para ver las métricas de la Fuente Única de Verdad, verifica que el control esté activado. |
| Tipo de vista | <ul><li>**Adquisición de usuarios:** La vista preferida para los datos SSOT.</li><li>**Redireccionamiento**: SKAN no admite redireccionamiento.</li><li>**Unificada**: Las campañas de instalación contienen datos SSOT. Las campañas de redireccionamiento no se ven afectadas por SSOT.</li></ul> |
| Fechas | <ul><li>[Mejor práctica] Seleccione un rango de fechas de 7 días o más que no incluya los 3 días más recientes para obtener resultados precisos.</li><li>La fecha más temprana disponible suele ser 3 días después de haber activado SSOT. Esta fecha es determinada por AppsFlyer.</li><li>Ejemplo de selección óptima de fecha:<ul><li>Si la fecha actual es el 10 de febrero y activaste SSOT el 29 de enero. Puede seleccionar del 1 al 7 de febrero.</li></ul></li><li>Ciertos datos (como ingresos) pueden estar disponibles solo 8 días después de activar SSOT.</li><li>Las instalaciones de Google SKAN pueden reportarse con hasta 45 días de retraso.</li></ul> |
| Filtros de campaña | Filtros disponibles en la jerarquía de campañas:<ul><li>Fuente de medios</li><li>Campaña</li></ul> |
| Principales indicadores clave de rendimiento | Los KPI principales disponibles en el panel de SSOT le permiten ver:<ul><li>Adquisición de usuarios: Tanto orgánicos como no orgánicos</li><li>Duplicados de SKAN</li><li>Redireccionamiento: Re-engagements y reatribuciones</li><li>Coste</li><li>IPC electrónico</li></ul>Para cada KPI, hay un valor porcentual. Este valor muestra la relación del KPI presentado con el rango de fechas paralelo anterior. Por ejemplo, esta semana en comparación con la semana pasada, o cualquier día seleccionado en el rango de fechas en comparación con el mismo número de días anteriores: Por ejemplo, si muestra un aumento del X% en las instalaciones, significa que el rango de fechas paralelo anterior tuvo un X% menos de instalaciones. |
| Gráficos | **Dimensiones disponibles:**<ul><li>Método de atribución:<ul><li>Instalaciones únicas de SKAN: Instalaciones que coinciden únicamente con SKAN y ningún otro método. En los datos sin procesar de SKAN, el af\_attribution\_flag de la instalación se establece en falso.</li><li>Instalaciones que coinciden con más de un método, incluido SKAN. En los datos sin procesar de SKAN, el atributo af\_attribution\_flag de la instalación se establece en verdadero.</li></ul></li><li>Tipo de atribución</li><li>Tipo de interacción atribuida</li><li>Campaña</li><li>ID de campaña</li><li>Fuente de medios</li><li>Fuente</li><li>ID de la aplicación (para algunos gráficos)</li><li>Geo (las ubicaciones de SKAN están <Anchor target="_blank" href="/marketers/es/docs/skan-modeled-data#geo">modeladas</Anchor>)</li><li>Nombre del evento en la aplicación (es decir, el nombre de un evento específico en la aplicación configurado en SKAN Conversion Studio).</li></ul>**Métricas:**<br /><br />Como se describe en las secciones de métricas. |
| Tabla | **Agrupaciones:**<ul><li>[Predeterminado] La tabla está agrupada por fuente de medios y campaña.</li><li>Las opciones de agrupamiento incluyen: fuente de medios, tipo de atribución, método de atribución, campaña, ID de campaña, tipo de toque atribuido, fecha, fuente, geolocalización y combinaciones de los mismos. **Nota**: Las ubicaciones geográficas de SKAN están <Anchor target="_blank" href="/marketers/es/docs/skan-modeled-data#geo">modeladas</Anchor>.</li><li>Si selecciona una agrupación con dimensiones que solo aplican al tráfico no orgánico, la tabla mostrará N\/D para la fuente de medios orgánicos.</li></ul>**Métricas:**<br /><br />Como se describe en las secciones de métricas. |

</Accordion>

<div id="metrics" />

<Accordion title="Métricas">

Métricas disponibles en el panel de SSOT:

| Métrica | Descripción y consideraciones |
| --- | --- |
| Agrupaciones | <ul><li>[Predeterminado] La tabla está agrupada por fuente de medios y campaña.</li><li>Las opciones de agrupación incluyen: Fuente de medios, tipo de atribución, método de atribución, campaña, ID de campaña, tipo de contacto atribuido, fecha, origen y sus combinaciones.</li><li>Si selecciona una agrupación con dimensiones que solo aplican al tráfico no orgánico, la tabla mostrará N\/D para la fuente de medios orgánicos.</li></ul> |
| **Atribuciones SSOT** | **Desglose principal de instalaciones, reatribuciones y reenganches de SSOT durante las fechas seleccionadas.**<ul><li>**No orgánico: La campaña que atrae al usuario. El mecanismo SSOT garantiza que la misma instalación se cuente solo una vez.**</li><li>**Métricas orgánicas.**</li></ul> |
| Total | Número de instalaciones, reatribuciones y nuevas interacciones. |
| Instalaciones | Número de usuarios únicos que instalan la aplicación. Calculado como instalaciones atribuidas por AppsFlyer dentro del contexto de campañas UA más la cantidad de nuevas instalaciones y descargas reportadas por SKAN, eliminando duplicados. |
| Re-atribuciones | Las métricas de retargeting están disponibles en los tipos de vista Unificado y Retargeting. Ten en cuenta que SKAN no admite retargeting. |
| Reenganches | Las métricas de retargeting están disponibles en los tipos de vista Unificado y Retargeting. Ten en cuenta que SKAN no admite retargeting. |
| **Otras métricas** | **Diversas otras métricas relacionadas con SSOT y el rendimiento publicitario** |
| Duplicados de SKAN | El número de instalaciones de SKAN con af\_attribution\_flag=true |
| Clics | Datos de clics e impresiones reportados por redes publicitarias a través de API. El mecanismo SSOT no afecta las métricas de los puntos de contacto. |
| Impresiones | Datos de clics e impresiones reportados por redes publicitarias a través de API. El mecanismo SSOT no afecta las métricas de los puntos de contacto. |
| Tasa de conversión | Clic a instalación |
| Costo ($) | <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview">Costo de campaña</Anchor> datos reportados por las redes publicitarias a través de API. Se muestran datos de campañas con al menos una instalación. El mecanismo SSOT no afecta al costo total reportado. Afecta solo a las métricas calculadas con números de instalación. |
| CPI medio ($) | La métrica del costo efectivo por instalación se calcula utilizando las métricas de instalación de la vista SSOT. Excluye instalaciones orgánicas. |
| CPM | Coste por mil (1000 impresiones). Fórmula: (Coste / Impresiones) * 1000 |
| CPC | Coste por clic. Fórmula: Coste / Clics |
| Clics efectivos | Número de atribuciones que ocurren después de que un usuario hace clic en un anuncio (CTA) |
| CTR | Tasa de clics. Fórmula: Clics / Impresiones |
| Vistas acumuladas | <span id="simple-tabpanel-2"></span>Número de atribuciones que ocurren después de que un usuario ve un anuncio (VTA) |
| Ingresos (D2) | <ul><li>Incluye datos modelados para tener en cuenta los postbacks de SKAN incompletos o faltantes (valores de conversión nulos)</li></ul>Ingresos de SKAN y Classic (incluye ingresos por publicidad) en la primera ventana de medición de SKAN (D2):<ul><li>**Ingresos SKAN:** Ingresos por instalaciones SKAN (donde af\_attribution\_flag=false/null). Basado en la configuración del valor de conversión de <Anchor target="_blank" href="/marketers/es/docs/skan-conversion-studio#revenue-component">ingresos en Conversion Studio</Anchor> y el periodo de la ventana de medición.</li><li>Ingresos clásicos: Ingresos generados por usuarios de la app después de una instalación atribuida por el método clásico dentro del plazo de medición de SKAN.</li><li>Para aquellos que utilizan SKAN 4 en Conversion Studio, estos son datos de 2 días después de la instalación. Para aquellos que utilizan SKAN 3 en Conversion Studio, los datos se basan en la ventana de actividad SKAN definida, ya sea más o menos de 2 días.</li><li>**Ejemplo**:<ul><li>La ventana de actividad es de 24h.</li><li>Los eventos de ingresos ocurren el día posterior a la instalación (día X+1), pero dentro del marco de 24 horas de actividad.<ul><li>Tanto para los ingresos reportados por SKAN como por AF, los ingresos se contabilizan, según se produjeron dentro del periodo de 24 horas (incluso si fue en un día diferente al de la instalación).</li></ul></li></ul></li></ul>**Consejo**: Para mejorar la precisión de los ingresos de SKAN:<ul><li>Sigue las instrucciones de <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide#recording-ad-revenue">ingresos por publicidad de SKAN</Anchor>.</li><li>Usa las recomendaciones de ingresos.</li></ul> |
| Ingresos D7 | <ul><li>Incluye datos modelados para tener en cuenta los postbacks de SKAN incompletos o faltantes (valores de conversión nulos)</li><li>Incluye datos modelados, más allá del periodo de medición de SKAN, hasta 7 días después de la instalación. <Anchor target="_blank" href="/marketers/es/docs/skan-modeled-data#revenue-ltv">Más información</Anchor></li><li>Requiere datos de ingresos D2 para el modelado.</li></ul> |
| ARPU D2 | Ingresos medios por usuario.<br /><br />Fórmula: Ingresos/Usuarios únicos<br /><br />Para aquellos que utilizan SKAN 4 en Conversion Studio, estos son datos de 2 días después de la instalación. Para aquellos que utilizan SKAN 3 en Conversion Studio, los datos se basan en la ventana de actividad SKAN definida, ya sea más o menos de 2 días. |
| ARPU D7 | Incluye datos modelados, más allá del periodo de medición de SKAN, hasta 7 días después de la instalación. <Anchor target="_blank" href="/marketers/es/docs/skan-modeled-data#revenue-ltv">Más información</Anchor> |
| ROAS D2 | Retorno sobre el gasto publicitario (%).<br /><br />Fórmula: Ingresos/Costos * 100<br /><br />Para aquellos que utilizan SKAN 4 en Conversion Studio, estos son datos de 2 días después de la instalación. Para aquellos que utilizan SKAN 3 en Conversion Studio, los datos se basan en la ventana de actividad SKAN definida, ya sea más o menos de 2 días. |
| ROAS d7 | Incluye datos modelados, más allá del periodo de medición de SKAN, hasta 7 días después de la instalación. <Anchor target="_blank" href="/marketers/es/docs/skan-modeled-data#revenue-ltv">Más información</Anchor> |
| ROI D2 | Retorno de la inversión (%).<br /><br />Fórmula: (Ingresos - Costos)/Costos * 100<br /><br />Para aquellos que utilizan SKAN 4 en Conversion Studio, estos son datos de 2 días después de la instalación. Para aquellos que utilizan SKAN 3 en Conversion Studio, los datos se basan en la ventana de actividad SKAN definida, ya sea más o menos de 2 días. |
| ROI D7 | Incluye datos modelados, más allá del periodo de medición de SKAN, hasta 7 días después de la instalación. <Anchor target="_blank" href="/marketers/es/docs/skan-modeled-data#revenue-ltv">Más información</Anchor> |
| Beneficio bruto D2 | Ganancia tras deducir el costo de la campaña.<br /><br />Fórmula: Ingresos - Costos<br /><br />Para aquellos que utilizan SKAN 4 en Conversion Studio, estos son datos de 2 días después de la instalación. Para aquellos que utilizan SKAN 3 en Conversion Studio, los datos se basan en la ventana de actividad SKAN definida, ya sea más o menos de 2 días. |
| Beneficio bruto D7 | Incluye datos modelados, más allá del periodo de medición de SKAN, hasta 7 días después de la instalación. <Anchor target="_blank" href="/marketers/es/docs/skan-modeled-data#revenue-ltv">Más información</Anchor> |
| **Métricas de eventos in-app** | **Métricas referentes a eventos específicos in-app (IAE)** |
| Usuarios únicos del evento (D2) | Usuarios únicos que realizan el evento, medidos mediante AppsFlyer y SKAN, incluidos datos modelados de valores nulos. Para quienes usan SKAN 4, estos datos se acumulan durante los primeros 2 días posteriores a la instalación. Para los que usan SKAN 3, los datos representan una acumulación de días posteriores a la instalación según la Ventana de Actividad definida. |
| Usuarios únicos del evento (D7) | Usuarios únicos que realizan el evento, basado en una combinación de AppsFlyer y SKAN. Incluye datos modelados, más allá de la ventana de medición SKAN, hasta 7 días después de la instalación. <Anchor target="_blank" href="/marketers/es/docs/skan-modeled-data#inapp-event-ltv">Más información</Anchor><br /><br />Nota: Los usuarios únicos en (D7) también incluyen a los usuarios únicos en D2. |
| eCPA del evento (D2) | Costo efectivo por acción: Costo/usuarios únicos que realizan el evento. |
| eCPA del evento (D7) | Ingresos generados con este evento, dentro de los días definidos después de la instalación. Incluye datos modelados, más allá de la ventana de medición SKAN, hasta 7 días después de la instalación. <Anchor target="_blank" href="/marketers/es/docs/skan-modeled-data#inapp-event-ltv">Más información</Anchor> |
| Conversión del evento (D2) | Tasa (%) de usuarios únicos que realizan el evento, como proporción de los usuarios que lo atribuyen (instalan, vuelven a interactuar o reatribuyen). Fórmula: Usuarios únicos / atribuciones * 100. |
| Conversión del evento (D7) | Tasa (%) de usuarios únicos que realizan el evento, como proporción de los usuarios que lo atribuyen (instalan, vuelven a interactuar o reatribuyen). Fórmula: Usuarios únicos / atribuciones * 100. Incluye datos modelados, más allá de la ventana de medición SKAN, hasta 7 días después de la instalación. <Anchor target="_blank" href="/marketers/es/docs/skan-modeled-data#inapp-event-ltv">Más información</Anchor> |
| Ingresos por eventos (D2) | Ingresos generados con este evento, dentro de los días definidos después de la instalación |
| Ingresos por eventos (D7) | Ingresos generados con este evento, dentro de los días definidos posteriores a la instalación. Incluye datos modelados, más allá de la ventana de medición SKAN, hasta 7 días después de la instalación. <Anchor target="_blank" href="/marketers/es/docs/skan-modeled-data#inapp-event-ltv">Más información</Anchor> |

</Accordion>

## ¿Cómo funciona el SSOT?

<div id="understanding-skanaf-modeled-attribution-duplication" />

<Accordion title="Entendiendo la duplicación de atribución modelada SKAN-AF">

La atribución de SKAN y la modelada por AF operan diferente, con características y limitaciones distintas. Por ello, cada instalación puede atribuirse a una fuente de medios no orgánica de la siguiente manera:

* Exclusivamente a través de SKAN o un modelo AF (atribución única).
* A través de ambos, SKAN y un modelo AF al mismo tiempo (duplicados). En este caso, el mecanismo SSOT identifica una instalación duplicada por SKAN con la señal: af\_attribution\_flag=TRUE. Y en el panel de control de SSOT, se muestra solo una instalación en lugar de dos.
* Ni modelo SKAN ni AF, lo que indica que la instalación es orgánica.

Los posibles escenarios de atribución del modelo SKAN-AF se ilustran en el siguiente diagrama de Venn.

![altskan_af_model_diagram.pngalt](https://files.readme.io/1b305d053044f79d12b9190d0b6c24dcc7e0bd17e17ef29029ad0b1c3c7d84c0-31247514684689.png)

La tabla siguiente describe las razones para cada escenario de atribución.

| Solo SKAN | Solo modelo AF | Tanto modelo SKAN como AF | Ni modelo SKAN ni AF |
| --- | --- | --- | --- |
| <ul><li>La fuente de medios es una SRN, el dispositivo del usuario tiene iOS 14.5+ y el usuario no otorga el consentimiento dual ATT.</li><li>La fuente de medios no es una SRN, el dispositivo del usuario tiene iOS 14.5+, el modelo probabilístico no está disponible y el usuario no otorga el consentimiento dual ATT.</li></ul> | <ul><li>El dispositivo del usuario tiene iOS 14.4 o versiones anteriores.</li><li>La fuente de medios no es compatible con SKAN.</li><li>La instalación vino a través de un flujo de web a app (SKAN solo admite flujos de app a app).</li><li>La instalación es a través de retargeting (no compatible con SKAN)</li></ul> | No existen limitaciones y tanto SKAN como un modelo AF atribuyen la instalación.<br /><br />Esto crea instalaciones duplicadas y es cuando se necesita SSOT para eliminarlas. | El usuario es orgánico |

</Accordion>

<div id="ssot-mechanism-workings" />

<Accordion title="Funcionamiento del mecanismo SSOT">

SSOT funciona como se detalla en el gráfico a continuación.

![SingleSourceOfTruth.png](https://files.readme.io/882527d4828cf3c7156caf183652368de33463a440715c69f7ec39bfd0f655fa-31247514685329.png)

**¿Cómo funciona el mecanismo SSOT?**

El mecanismo SSOT se encuentra en el SDK de AppsFlyer dentro de tu aplicación en el dispositivo del usuario y en la plataforma de AppsFlyer, de la siguiente manera:

**Dispositivo del usuario:**

* El usuario abre la aplicación por primera vez. La plataforma AppsFlyer intenta atribuir al usuario. La capacidad de atribución depende del tipo de campaña y del estado de consentimiento del usuario (ATT).
* Si la atribución tiene éxito, el SDK establece el bit de atribución en el Valor de Conversión (CV).
* El flujo regular de SKAdNetwork continúa sin cambios. Esto significa que se sigue midiendo la actividad del usuario y fijando el CV hasta que termine la ventana de medición.
* Posteriormente, iOS envía el postback.

**Plataforma AppsFlyer**

* AppsFlyer recibe el postback de iOS, decodifica el valor de conversión y muestra el valor del bit de atribución mediante af\_attribution\_flag, como se detalla en la tabla siguiente.

**Consideraciones**

* Generalmente, AppsFlyer no cuenta las reinstalaciones. En el contexto de SSOT, no se considera el estado de reinstalación. Esto significa que SSOT no elimina las instalaciones SKAN duplicadas provenientes de reinstalaciones en el contexto del análisis de SSOT y no influyen en la configuración del indicador af\_attribution.

#### **Campo del indicador de atribución**

| Indicador SSOT en el Valor de Conversión | Significado | Campo af\_attribution\_flag |
| --- | --- | --- |
| en | SSOT está activado en Conversion Studio y AppsFlyer logró atribuir al usuario. | Verdadero |
| Apagado | SSOT está activado en Conversion Studio y AppsFlyer no atribuyó al usuario. | Falso |
| -- | SSOT está desactivado en Conversion Studio. | Nulo |

**¿Cómo afecta el af\_attribution\_flag (bit de atribución) a las herramientas de informes?**

* Panel de control SKAN: Refleja únicamente el rendimiento informado a través de los postbacks de SKAN. Por lo tanto, el indicador af\_attribution no se considera y no se eliminan los duplicados.
* Informes de desempeño <Anchor target="_blank" href="/marketers/es/docs/skan-aggregated-performance-report-api">agregados</Anchor> e informes de <Anchor target="_blank" href="/marketers/es/docs/skan-raw-data-reports">datos sin procesar</Anchor> de SKAN: Úselo según sus necesidades de informes. Si combinas datos de SKAN con datos de AppsFlyer, utiliza la bandera para eliminar datos duplicados. Esto se aplica a los informes de datos en bruto y agregados.
* Vista SSOT en el panel de resumen: Los datos de todos los métodos de atribución, como SKAN, IDFA, IDFV, Apple Search Ads, etc., se combinan en una sola vista después de eliminar los datos duplicados de SKAN.

</Accordion>

<div id="metrics-derived-by-combining-data-from-multiple-attribution-methods" />

<Accordion title="Métricas derivadas al combinar datos de múltiples métodos de atribución">

Cuando combines datos de SKAN con otros métodos de atribución, utiliza af\_attribution\_flag para eliminar los datos duplicados. Esto se aplica a los informes de datos en bruto y agregados.

Las siguientes métricas ejemplo se pueden calcular utilizando el af\_attribution\_flag:

* Instalaciones no orgánicas
* Instalaciones orgánicas
* IPC electrónico
* Ingresos por cohorte

Fórmula para calcular métricas de ejemplo:

| Descripción de la métrica | Designación | Fórmula |
| --- | --- | --- |
| Instalaciones no orgánicas de AppsFlyer | A | Instalaciones no orgánicas reportadas por AppsFlyer |
| Instalaciones únicas de SKAN | B | Instalaciones de SKAN donde af\_attribution\_flag=false |
| Todas las instalaciones no orgánicas | C | A + B |
| Instalaciones orgánicas | D | Instalaciones totales - C<br /><br />**Nota**: Las instalaciones totales significan todas las instalaciones registradas por el SDK de AppsFlyer, independientemente de la atribución. |
| CPI de campaña | E | Costo / C |
| Ingresos por cohorte | F | Suma lo siguiente:<ul><li>Ingresos de los usuarios definidos por A. Incluye eventos generados durante el periodo inicial posterior a la instalación, equivalente a tu ventana de medición SKAN.</li><li>Ingresos de SKAN donde af\_attribution\_flag = false</li></ul> |
| Ingresos orgánicos D2 | G | Ingresos D2 totales - ingresos D2 de las instalaciones A y B |
| Usuarios únicos del IAE orgánico D2 | H | Total de usuarios únicos de IAE D2 - usuarios únicos de eventos D2 de las instalaciones A y B |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Características y limitaciones">

| Caducado | Observaciones |
| --- | --- |
| Vista SSOT | SSOT solo está disponible si hay al menos un postback de SKAN para cada uno de los últimos 5 días que incluya `af_attribution_flag=true`. |
| Instalaciones totales | En algunos casos, es posible que se muestren más instalaciones cuando la SSOT está activada frente a cuando está desactivada. Una de las razones de esto es que el modelado de valores de conversión nulos puede influir en el cálculo de la fecha de instalación y provocar diferencias al comparar instalaciones en fechas similares. Además, el total de instalaciones puede aumentar si no se modelan los CV nulos, ya que en ese caso, cada instalación de SKAN se cuenta como única (con el indicador ). |
| Ingresos | Los ingresos y otras métricas relacionadas (ARPU, ROAS, ROI, beneficio bruto) son compatibles desde el 1 de septiembre de 2022. |
| Agencias | Los usuarios de agencias pueden ver la vista SSOT en el panel de resumen. |
| Redes publicitarias | <ul><li>Las redes publicitarias pueden acceder a la vista SSOT en el panel de resumen para ver los datos atribuidos a su fuente de medios. Para ver la vista SSOT:<ul><li>El anunciante debe activar el SSOT en Conversion Studio.</li><li>La red publicitaria debe estar ejecutando campañas SKAN.</li><li>La red publicitaria debe contar con los <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos requeridos</Anchor> por el anunciante para acceder a los datos agregados.</li></ul></li><li>Las redes publicitarias pueden recibir señales SSOT a través de postbacks de SKAN añadiendo la macro de campo skad\_af\_attribution\_flag. <Anchor target="_blank" href="/partners/es/docs/skan-integration-guide-for-ad-networks#recibir-datos-de-appsflyer">Más información</Anchor></li></ul> |
| Métricas D7 | Las métricas del D7 para el tráfico orgánico están disponibles a partir del 16 de febrero de 2025.<br /><br />Es posible que falten métricas D7 o que sean inferiores a las métricas D2 si:<ul><li>El rango de fechas incluye fechas para las que no han pasado 8 días.</li><li>No se dispone de datos modelados. Por ejemplo, si no hay datos de ingresos de 14 días. <Anchor target="_blank" href="/marketers/es/docs/skan-modeled-data#revenue-ltv">Más información</Anchor></li><li>Se ha modificado la configuración de SKAN Conversion Studio en los últimos 14 días.</li><li>Hay menos de 10 instalaciones para una fecha específica.</li></ul> |
| Cambios en la configuración de SKAN Conversion Studio | Al cambiar la configuración de SKAN Conversion Studio, puede haber inexactitudes en los datos SSOT durante aproximadamente 96 horas. Esto se debe a que AppsFlyer comienza inmediatamente a decodificar los postbacks de SKAN con el nuevo esquema, aunque los postbacks siguen llegando de instalaciones codificadas con el esquema anterior. |
| Datos reportados por AF | <ul><li>Los datos reportados por AF, a veces denominados datos del modelo AF, se refieren a datos de las instalaciones u otros eventos atribuidos a través de otro método de atribución de AppsFlyer, diferente de SKAN.</li><li>El propósito del panel de control SSOT es evitar la duplicación de las instalaciones y los eventos atribuidos tanto a través de SKAN como de otro método AppsFlyer.</li><li>Si activas SSOT, pero deseas ver los datos anteriores a la activación de SSOT, el panel de control SSOT solo muestra los datos reportados por AF.</li></ul> |
| Eventos dentro de la aplicación | Los eventos in-app (como dimensiones) y sus métricas están disponibles solo para:<ul><li>Están disponibles los eventos que ocurrieron durante el período de Ventana 1.</li></ul> |
| Retraso del postback SKAN | Cuando los postbacks de SKAN llegan con un retraso significativo, por ejemplo, desde la API de Google, que puede tardar hasta 15 días, los datos de los días posteriores (como D7) pueden parecer inicialmente inferiores a los de los días anteriores (como D2). Este retraso puede afectar a la precisión del modelo de SSOT. Por este motivo, te recomendamos esperar al menos 15 días después de la fecha de instalación para que los datos se completen por completo antes de evaluar la precisión del modelo. |

</Accordion>

> 📄 **Consulte también**
>
> * Panel de vista general
> * <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide">Guía de la solución SKAN</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/skan-conversion-studio">Estudio de conversión SKAN</Anchor>

<div data-zendesk-anchors="how-to-get-true-ios-14-performance-data=sobre-la-fuente-%C3%BAnica-de-verdad-datos-reales-del-rendimiento-en-ios 01H8TZV6P41Z3ZEZ8VS86DK1J9=sobre-la-fuente-%C3%BAnica-de-verdad-datos-reales-del-rendimiento-en-ios 01H8TZV6P4G5AF2MJDQB8J6W2M=turn-on-single-source-of-truth overview-dashboard-single-source-of-truth-view=panel-de-vista-general-para-la-fuente-%C3%BAnica-de-verdad 01H8TZV6P4ZBJTDH0FQ6F5D6Q9=panel-de-vista-general-para-la-fuente-%C3%BAnica-de-verdad 01H8TZV6P47ZE6PMPF7S9GCJ16=turn-on-single-source-of-truth-view 01H8TZV6P4VCC5NRKBRQNJ4NX3=ssot-view-considerations filter-considerations=consideraciones-sobre-los-filtros 01H8TZV6P4QXEXYWSXKDB7B5SV=consideraciones-sobre-los-filtros 01H8TZV6P4YNTFBX5RXVKK8J0F=metrics how-does-ssot-work=c%C3%B3mo-funciona-el-ssot 01H8TZV6P4K8VXNKDR7JHM8PFW=c%C3%B3mo-funciona-el-ssot 01H8TZV6P4QYQJ177E2ZG676MH=understanding-skanaf-modeled-attribution-duplication 01H8TZV6P58E502Y1FDFHC3KHM=ssot-mechanism-workings attribution-flag-field=campo-del-indicador-de-atribuci%C3%B3n 01H8TZV6P5SSKDTKV4BV3TTA7D=campo-del-indicador-de-atribuci%C3%B3n 01H8TZV6P5AHZD8VRWRS4SPBYW=metrics-derived-by-combining-data-from-multiple-attribution-methods 01H8TZV6P5KN4F24ZN33V0TK7K=traits-and-limitations h_01HE182N43SSBX051E4GK7NFQ8=consulte-tambi%C3%A9n" />
