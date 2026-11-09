---
title: Guía de Optimización Creativa
metadata:
  keywords:
    - Premium
    - Marketers
    - Design team
    - Creative Optimization
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-omer-katzburg
    - Marketers
    - Creative Optimization
  created_at: '2023-09-14T13:32:13Z'
  edited_at: '2026-09-28T00:01:46Z'
  id: 18564718580625
  locale: es
  section: Creative Optimization
  section_id: 4419063475217
  url: https://support.appsflyer.com/hc/es/articles/18564718580625
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En resumen:** La Optimización Creativa te permite extraer todos los datos de recursos creativos de todas tus campañas en una sola plataforma, para que puedas analizar su rendimiento, descubrir qué creatividades funcionan mejor y tomar mejores decisiones basadas en datos. Los datos son LTV, lo que significa que las métricas son para conversiones que ocurrieron a partir de creativos durante el rango de fechas seleccionado.

<Image align="center" alt="Main image -Default view.jpg" src="https://files.readme.io/9ef8901b620d54cad031ec142f5dd408406e0a470bae8a0719826777561cd1d1-21362497825169.jpg" />

<div id="about-creative-optimization" />

## Sobre la Optimización Creativa

La **Optimización Creativa** es tu ventanilla única para medir el rendimiento de las creatividades utilizadas en todas tus campañas. Te permite extraer sin esfuerzo todos tus recursos creativos de todos los canales de medios en una sola plataforma, o en tu sistema de BI, y analizar su rendimiento por dimensiones seleccionadas, a través de múltiples campañas, canales y mucho más. La Optimización Creativa te permite dividir y segmentar por diferentes métricas y KPIs para obtener insights críticos antes de planificar, seleccionar y producir tu próximo lote de creatividades.

Sus dashboards te permiten medir el rendimiento de videos, imágenes, HTML y texto, y ver qué tan bien les va a lo largo del tiempo y en todos los canales. Cada creatividad es analizada, agregada y emparejada usando potentes algoritmos de IA. Esto significa que las mismas creatividades utilizadas para diferentes campañas y fuentes de medios se identifican y muestran como una sola en el dashboard, independientemente de su convención de nomenclatura, ID de anuncio o cualquier otro metadato.

Utiliza el <Anchor target="_blank" href="/marketers/es/docs/creative-optimization-overview-dashboard">dashboard general de Optimización Creativa</Anchor> para ver tus datos visualmente en una variedad de gráficos llenos de información y una tabla detallada, que te brinda toda la información necesaria para optimizar y seleccionar las mejores creatividades para tus campañas.

Con el <Anchor target="_blank" href="/marketers/es/docs/creative-optimization-discovery-ai-dashboard">dashboard de descubrimiento de Optimización Creativa</Anchor> impulsado por IA, no hagas suposiciones sobre la producción de creatividades ganadoras. Obtén una visión completa de todas tus creatividades o profundiza en el rendimiento de escenas y elementos individuales para obtener los máximos insights.

<Anchor target="_blank" href="/marketers/es/docs/creative-optimization-etl-reporting">Optimización Creativa ETL</Anchor> equipa a tus analistas de datos con toda la información necesaria para el análisis creativo del rendimiento mediante la transmisión automática de reportes al almacenamiento en la nube para una carga eficiente y programática en tus sistemas BI.

Con la Optimización Creativa puedes:

* Aprender rápidamente qué creatividades, escenas y elementos funcionan y cuáles no
* Optimizar tus creatividades en función de los datos
* Aumentar el rendimiento creativo y el ROI
* Producir las creatividades más exitosas
* Identificar la disminución de la eficacia de las creatividades a lo largo del tiempo/canales/campañas y tomar decisiones informadas para la optimización
* Y más

<div id="creative-assets" />

## Recursos creativos

Esta sección proporciona información sobre los recursos creativos que medimos.

<div id="supported-asset-types" />

<Accordion title="Tipos de recursos admitidos">

Los tipos de recursos compatibles con el dashboard de optimización creativa incluyen:

* Videos
* Imágenes
* Anuncios en carrusel (solo Meta)
* HTML (incluido ejecutable)
* Texto

<div id="notes" />

> 📘 **Notas**
>
> * Los recursos que se pueden obtener en una vista previa en el dashboard incluyen imágenes, videos y texto.
> * La función de "similitud creativa" aún no está disponible para
>   anuncios de carrusel.

</Accordion>

<div id="matching-creatives" />

<Accordion title="Creatividades coincidentes">

La optimización creativa tiene la capacidad única de identificar qué recursos son iguales, a través de múltiples canales y campañas, independientemente de las convenciones de nomenclatura o ID. Esto se realiza mediante algoritmos de IA y visión por computadora que coinciden con propiedades como el contexto visual, el sonido y los píxeles. Adicionalmente:

* Las creatividades coincidentes deben tener la misma relación de aspecto, como vertical, horizontal o cuadrado.
* Los videos con diferentes duraciones se consideran diferentes creatividades.

</Accordion>

<div id="measuring-creatives-with-multiple-assets" />

<Accordion title="Medición de creatividades con múltiples recursos">

**¿Cómo mide la Optimización Creativa una creatividad publicitaria con múltiples recursos?**

Meta Advantage+ (creatividades dinámicas) y Google Universal App Campaigns (UAC) pueden incluir creatividades publicitarias con múltiples recursos. Sin embargo, AppsFlyer no desglosa los datos a nivel de recurso. Anuncios de Meta proporciona datos hasta el **nivel de anuncio** y Google proporciona datos solo hasta el **nivel del grupo de anuncios**. Para estos tipos de creatividades publicitarias, AppsFlyer utiliza el modelado de datos para dividir los datos de rendimiento entre los recursos.

<div id="example" />

> 📄 **Ejemplo**
>
> Supongamos que hay un anuncio creativo en Facebook con múltiples recursos. Facebook lo atribuye con 100 instalaciones en total, desglosado en activos de la siguiente manera: el **recurso A** tiene 60 instalaciones y el **recurso B** tiene 40 instalaciones, según lo medido por Facebook. En AppsFlyer, digamos que al anuncio se le atribuyen 50 instalaciones (debido a diferencias de atribución inherentes entre AppsFlyer y SRN). Para permitir el análisis a nivel de activos, AppsFlyer distribuye los datos de performance (impresiones, clics, instalaciones y costo) en función de la relación de métricas de activos del total, como se ilustra a continuación.
>
> Entonces, **para el recurso A hay:**
> 60 instalaciones divididas por 60+40 (instalaciones totales atribuidas por Facebook) = 0.6
> Luego multiplicamos 0.6 por 50 (número de instalaciones atribuidas de AppsFlyer) = 30 instalaciones
>
> **Para el recurso B hay:**
> 40 instalaciones divididas por 60+40 (instalaciones totales atribuidas por Facebook) = 0.4
> Luego multiplicamos 0.4 por 50 (número de instalaciones atribuidas de AppsFlyer) = 20 instalaciones
>
> Por lo que a la creatividad de anuncios se le atribuye un total de 50 instalaciones por parte de AppsFlyer pero se mantiene el volumen de instalaciones por activo lo que significa que el **recurso A** generó más instalaciones que el **recurso B**, en nuestro ejemplo.
> Las métricas del down-funnel, como Ingresos y ROAS, también se calculan en función de esta relación.
>
> <Image align="center" alt="Creative_data_example_en-us.png" src="https://files.readme.io/ca556904829b809238b8b994fd6d762d6cb58ae993c41dd19a7de978f774e8b9-small-18564727253649.png" />

</Accordion>

<div id="using-the-dashboard" />

## Uso del dashboard

Esta sección proporciona una visión general completa del dashboard principal: Cómo usar filtros, las diversas métricas y dimensiones disponibles para obtener los datos creativos que estás buscando, y cómo guardar y compartir vistas del dashboard.

<Image align="center" alt="Filter bar and metrics -Default view.jpg" src="https://files.readme.io/b68e65ff2cdd2ad2fe0805eb1c2792904af69504d104b6f6ae8a524124272a48-21363121543185.jpg" />

<div id="filter-bar" />

<Accordion title="Barra de filtros">

El primer paso para configurar tu dashboard es seleccionar tus opciones de filtrado. Todos los filtros se aplican tanto al dashboard general de Optimización Creativa como al de descubrimiento.

<Image align="center" alt="filter_bar.jpg" src="https://files.readme.io/99da48c37938e573af66cf1f46ce3273c3ca010e68070cb59b5e12cbad1981e3-18564730224913.jpg" />

Para seleccionar filtros del dashboard

1. Selecciona:
   * **Aplicación**
   * **Rango de fechas:** Se muestra un creativo en el dashboard cuando hay datos de conversión para el creativo durante el rango de fechas seleccionado. Los datos son LTV, lo que significa que las métricas son para conversiones que ocurrieron a partir de creativos durante el rango de fechas seleccionado.
   * [Tipo de vista](#view-type)
2. Haz clic en el icono + para agregar cualquiera de las siguientes opciones de filtrado, incluyendo:
   * **Dimensiones y métricas**
   * **Filtros numéricos**, que están disponibles para todas las métricas con las siguientes opciones:
     * Mayor que: muestra creatividades con valores superiores o iguales a la métrica elegida
     * Menor que: muestra creatividades con valores por debajo de la métrica elegida

Además de las [métricas y dimensiones estándar](/docs/creative-optimization-guide#standard-metrics-and-dimensions), el dashboard de Optimización Creativa ofrece varias métricas y dimensiones únicas.

</Accordion>

<div id="view-type" />

<Accordion title="Tipo de vista">

Los datos creativos en los dashboards se presentan en 3 tipos de vista separados: Unificado, Adquisición de Usuarios (UA) y Retargeting:

* **Unificada**: muestra todos los datos de creatividades de anuncios y conjuntos de anuncios de retargeting y UA.
* **Adquisición de usuarios** : muestra los datos de las creatividades asociadas a anuncios y conjuntos de anuncios de UA únicamente.
* **Retargeting**: muestra los datos de las creatividades asociadas a anuncios y conjuntos de anuncios de retargeting únicamente. Los datos de costos también están disponibles aquí.

<Image align="center" alt="View_types.jpg" src="https://files.readme.io/e73cc643581e94d6fbc6455e16615eb2e1d8b387cda626d39b17bbe714122611-18564727261585.jpg" />

</Accordion>

<div id="creative-optimization-roi360" />

<Accordion title="Optimización Creativa + ROI360">

Con una suscripción a ROI360 de AppsFlyer, los datos de costos que se muestran en los dashboards de Optimización Creativa provienen de ROI360, que consolida y procesa los datos de costos de tus partners de ad networks y agregan métricas adicionales basadas en costos. Sin esta suscripción, los datos de costos provienen de los propios reportes de tus partners de medios integrados. Recomendamos una suscripción a ROI360 para acceder a los datos de costos más completos y actuales. La siguiente tabla explica las diferencias de Optimización Creativa con y sin ROI360.

| Con ROI360 | Sin ROI360 |
| --- | --- |
| <ul><li><Anchor target="_blank" href="/marketers/es/docs/roi360-guide-cost-and-revenue-data#herramientas-de-costos">Los datos se informan a través de cualquier método ROI360</Anchor>.</li><li><Anchor target="_blank" href="/marketers/es/docs/roi360-guide-cost-and-revenue-data#herramientas-de-costos">Cuenta con todas las capacidades de reportes de costos de ROI360</Anchor>.</li><li>ETL creativo incluye datos de costos (requiere una suscripción avanzada de ROI360).</li></ul> | <ul><li>Los datos de costos, según lo informado directamente por tus partners integrados, se limitan a los dashboards de Optimización Creativa, no al ETL creativo.</li></ul> |

Saber más sobre <Anchor target="_blank" href="/marketers/es/docs/roi360-guide-cost-and-revenue-data">ROI360</Anchor>

</Accordion>

<div id="standard-metrics-and-dimensions" />

<Accordion title="Métricas y dimensiones estándar">

Las métricas/dimensiones estándar disponibles en el dashboard incluyen:

| Métrica/dimensión | Descripción |
| --- | --- |
| Impresiones | Número de vistas creativas |
| Clics | Número de clics en los anuncios con el creativo |
| Conversiones | <ul><li>Instalaciones: número de usuarios únicos que instalan la aplicación</li><li>Re-engagements: número de usuarios únicos que abren la aplicación después de interactuar con una campaña de retargeting</li><li>Reatribuciones: número de usuarios únicos que reinstalan la aplicación después de interactuar con una campaña de retargeting</li></ul> |
| Costo | Costo de la creatividad |
| CTR (Tasa de click-through) | Tasa (%) de usuarios que han hecho clic en un anuncio en relación con el número de visitas totales. Fórmula: Clics / Impresiones * 100 |
| CVR (tasa de conversión) | Tasa (%) de usuarios que completan la trayectoria desde el clic hasta la atribución (instalaciones, re-engagements y reatribuciones). Fórmula: Conversiones / Clics *100 |
| IPM (instalaciones por mil) | Instalaciones por mil. Número de instalaciones por cada 1000 impresiones de usuario (vistas de anuncios) |
| eCPI (costo efectivo por instalación) | El eCPI excluye las instalaciones orgánicas y calcula el costo por <Anchor target="_blank" href="/marketers/es/docs/about-organic-and-non-organic-installs">atribuciones no orgánicas</Anchor> (instalaciones, re-engagements y reatribuciones) Fórmula: Costo total disponible/todas las atribuciones no orgánicas. |
| CPM (costo por mil) | Costo de 1000 impresiones de anuncios. Fórmula: Gasto creativo total / número de impresiones * 1.000 |
| Plataforma | Se refiere al SO (p. ej.,. Android) |
| Canal | Segmentación del tráfico dentro de fuentes de medios  <br />(por ejemplo, YouTube para Google, Instagram para Meta Ads, etc.) YouTube para Google, Instagram para Anuncios de Meta, etc.) |
| Geografía | País/ubicación |
| ID | <ul><li>Creativo</li><li>Anuncio</li><li>Conjunto de anuncios</li><li>Campaña</li></ul> |
| Agencia | Muestra datos de las creatividades de agencias seleccionadas |
| Ingresos (D0, D1, D3, D7, D14, D30, D60, D90) | Ingresos de cohortes reportados a AppsFlyer |
| ROAS (D0, D1, D3, D7, D14, D30, D60, D90) | Retorno del gasto en publicidad de cohorte (%). Calcula los ingresos generados por unidad de gasto publicitario. Fórmula: Ingresos / Costo * 100 |
| Usuarios únicos (D0, D1, D3, D7, D14, D30, D60, D90) | Cohorte de usuarios únicos que se involucraron con tu aplicación hasta el día especificado (incluido) desde la instalación |
| Retención (D0, D1, D3, D7, D14, D30, D60, D90) | Tasa de cohorte (%) de usuarios que continúan usando tu servicio o producto durante un periodo predeterminado<br /><br />**Nota:** Los datos están alineados con el dashboard de cohorte de AppsFlyer. |

</Accordion>

<div id="unique-metrics-and-dimensions" />

<Accordion title="Métricas y dimensiones únicas">

Las métricas/dimensiones únicas disponibles en el dashboard incluyen:

| Métrica/dimensión | Descripción |
| --- | --- |
| Apariciones | Muestra el número de campañas, conjuntos de anuncios y anuncios en los que se muestra una creatividad específica en los diferentes canales. |
| [Métricas de partners](/docs/creative-optimization-guide#partner-dimensions-and-metrics) | Datos que provienen directamente de partners integrados (no de los datos de atribución de AppsFlyer). |
| Creatividades similares | Agrupa las creatividades parecidas y podrás comparar su rendimiento para determinar la versión más exitosa. Por ejemplo, se agruparían imágenes similares con diferentes orientaciones (vertical vs horizontal), al igual que videos similares en diferentes idiomas. Esta dimensión solo es aplicable a imágenes y videos. |
| Edad de la creatividad | Muestra el número de días que se ha ejecutado una creatividad como parte de las campañas. La edad se calcula a partir de la primera impresión, clic o instalación recibida por AppsFlyer (la "primera vista" de la creatividad) y puede variar según las dimensiones seleccionadas. Por ejemplo, si un día se subió un creativo a una campaña, y luego también se subió a otra campaña en otro día diferente, y tanto las campañas como las dimensiones de edad creativa se agregan al filtro, la edad será la de la primera subida.<br /><br />**Nota:** Para las creatividades en campañas que comenzaron a ejecutarse antes de ser ingeridas en el dashboard de Creative, AppsFlyer muestra sus datos que incluyen hasta 90 días antes de la ingestión. Por ejemplo, si una creatividad se estuvo ejecutando por más de 90 días antes de la ingestión, la “edad de la creatividad” que se mostrará es de 90 al principio pero luego seguirá creciendo acumulativamente cada día. |
| Primera visualización de la creatividad | Muestra las creatividades cuando se recibieron por primera vez los datos de rendimiento (generalmente una impresión). El cálculo " Edad de la creatividad " se activa a partir de esta marca de tiempo. |
| Duración | Duración en segundos de un recurso creativo (aplicable a videos) |
| Resolución | Tamaño de un recurso creativo en píxeles (aplicable a imágenes y videos)<br /><br />**Nota:** Mostramos la resolución real que tus partners de medios integrados sirvieron a los usuarios. Esta puede ser una resolución diferente a la que se les subió originalmente. |
| Orientación | Orientación de un recurso creativo como vertical, cuadrado u horizontal |
| Mes | Desglose del rendimiento por mes |
| Semana | Desglose del rendimiento por semana |
| Tarjetas finales | Esto se refiere a los anuncios estáticos que pueden mostrarse al final de los anuncios de video, y que generalmente contienen información básica sobre la aplicación promocionada. La capacidad de agrupar creatividades por tarjetas finales brinda insights adicionales para la optimización de las creatividades, como comparar la misma tarjeta final con diferentes videos para identificar la mejor combinación. Puedes ver las creatividades por los siguientes datos de la tarjeta final:<ul><li>Nombre de la tarjeta final</li><li>ID de la tarjeta final</li><li>Duración de la tarjeta final</li><li>Resolución de la tarjeta final</li><li>Orientación de la tarjeta final</li><li>Tipo de tarjeta final</li></ul>**Notas:**<ul><li>Los datos de la tarjeta final están disponibles para los siguientes partners: AppLovin, IronSource, Moloco, UnityAds, Snapchat y YouAppi.<ul><li>Actualmente, solo IronSource, Unity Ads y Snap proporcionan los nombres únicos de las tarjetas finales. Para todos los demás partners, los nombres de las tarjetas finales aparecerán idénticos a los nombres creativos en los dashboards.</li></ul></li></ul> |

</Accordion>

<div id="custom-metrics" />

<Accordion title="Métricas personalizadas">

Crea métricas personalizadas para medir el rendimiento de tus creatividades exactamente como te gusta.

**Para crear una métrica personalizada:**

1. Haz clic en el menú desplegable en la parte superior derecha del dashboard y selecciona **Métricas personalizadas**.  
   **![Custom_metric_select.jpg](https://files.readme.io/99ca0ee30d09e42ef2798188e8d95fc4cf56ee31ad055209efadc47c9df8a859-18564742772625.jpg)**
2. **Rellena el formulario:**
   * **Nombre**: introduce un nombre de métrica único.
   * **Tipo**: selecciona un tipo numérico, porcentaje o divisa.
   * **Descripción**: introduce una descripción (opcional).
   * **Fórmula métrica**: crea una fórmula haciendo clic en **+ Agregar fórmula**.   
     * *Las métricas* incluyen impresiones, clics, instalaciones, CTR, CVR, CPM, IPM, costo, eCPI, reatribuciones, reengagements, ingresos, ROAS, retención, usuarios únicos, apariciones y métricas de partners
     * Combina con varios *operadores, números* y/o *eventos in-app*.
     * Los eventos in-app específicos se seleccionan en el menú desplegable. Para cada evento in-app, puedes agregar cualquier métrica para el evento por separado, para obtener insights altamente específicos, por ejemplo, af\_purchase revenue + af\_login count.  
       <Image align="center" alt="" src="https://files.readme.io/2b8bdaa8c1fb47c7e78b59e7e24f37aa3248800c7a3ed5cc821c2e11622a93fe-30129836915729.png" width="892px" />
3. Haz clic en **Guardar**.  
   Tu nueva métrica personalizada se crea y se mostrará en la barra de filtro y la configuración de la tabla con "Personalizado" junto a ella.

**Notas:**

* Puedes crear hasta 30 métricas personalizadas por cuenta.
* Puedes pasar el cursor sobre la pestaña "Personalizado" en la configuración de la tabla para ver la descripción.

Las métricas personalizadas también se pueden editar o eliminar.

**Para editar:**

1. Haz clic en el menú desplegable **Editar métrica personalizada existente** (en el formulario **Métricas personalizadas**) y selecciona la que deseas editar.  
   <Image align="center" alt="" src="https://files.readme.io/b792e08152482bed11ea8ce5ea5795c3df961c257d07397b5b4d787f40a8ea2e-30129836916369.png" width="892px" />
2. Haz los cambios que desees, luego haz clic en **Guardar**.  
   **Nota:** También puedes hacer clic en **Guardar como** para guardarla como una nueva métrica personalizada.

**Para eliminar:**

* Después de seleccionar la métrica personalizada que deseas eliminar en el menú desplegable, haz clic en el icono de eliminar.  
  <Image align="center" alt="" src="https://files.readme.io/8370c5bfec23ef2ac15e266e98be357e496aef51fa14ca5b4c853b0b38910a10-30129810517393.png" width="546px" />

</Accordion>

<div id="partner-dimensions-and-metrics" />

<Accordion title="Dimensiones y métricas de partners">

Las métricas de los partners son datos que provienen directamente de los partners de medios integrados (y no de los datos de atribución de AppsFlyer). Las métricas varían según el partner e incluyen impresiones, clics, conversiones, costo y métricas de porcentaje de reproducción de video. Las métricas se pueden seleccionar en los filtros, ver en todo el dashboard y agregarse a la tabla.

La siguiente tabla enumera todos los partners de optimización creativa, con la granularidad de datos disponible para cada uno:

* Dimensiones
* Métricas (según lo informado por las ad networks)
* Funciones compatibles y sus características

Descargar archivo: <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTQLUxhNMmBPTlm1_KsfLTupNL6tgZeqAt5OFwzLJUmhSXZ7K18aX6enuV4ST1mUVarUV-KPrUnMYS6/pub?output=csv">CSV</Anchor>, <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTQLUxhNMmBPTlm1_KsfLTupNL6tgZeqAt5OFwzLJUmhSXZ7K18aX6enuV4ST1mUVarUV-KPrUnMYS6/pub?output=xlsx">XLS</Anchor>

<div id="to-set-up-partner-metrics" />

#### **Para configurar las métricas de partners:**

Simplemente agrega una nueva integración de partners y las métricas para los partners compatibles se incorporarán automáticamente a la Optimización Creativa (Unity Ads es una excepción y tiene **instrucciones especiales**). Una vez que se configuran, estas métricas se indican con "Partner" junto a la métrica.

<Image align="center" alt="partner metrics image.jpg" src="https://files.readme.io/074948fd8e4707c1353b6f8ce387e76e04801eeef397e94a604619bc8a0ad420-18564730240145.jpg" />

**Instrucciones y consideraciones especiales:**

<div id="applovin-metrics" />

<Accordion title="Métricas de AppLovin">

**Nota:**

* Debido a una restricción en la API de AppLovin, solo se dispone de datos históricos de hasta 45 días. Por lo general, AppsFlyer puede mostrar hasta 90 días de datos históricos; sin embargo, debido a la restricción de AppLovin, solo 45 días de datos de AppLovin están disponibles.
* Los datos de Creative de AppsFlyer están alineados con el reporte probabilístico de AppsFlyer (no el reporte facturable).

</Accordion>

<div id="google-ads-metrics" />

<Accordion title="Métricas de Google Ads">

**Nota:**

* Habrá diferencias en el número de instalaciones reportadas por Google Ads y AppsFlyer debido a la diferente lógica de atribución.
* Habrá diferencias entre Google y AppsFlyer para todas las métricas. Esto se debe al hecho de que las métricas de los partners de Google se basan en el reporte de visualización de recursos de Google, mientras que los datos de AppsFlyer están alineados con la vista de grupo de Google Ads. Estos reportes no están alineados entre sí en términos de rendimiento, por ejemplo, el número total de impresiones de recursos bajo un grupo de anuncios específico no será igual al total de impresiones que informa el grupo de anuncios.
* Existen diferencias entre el producto de Creative y la plataforma Google AdWords; al comparar la vista de recursos entre la plataforma Google y AppsFlyer puede haber ligeras diferencias debido a: 1. Zonas horarias (para Creative, es UTC+0). 2. Tasa de actualización de datos (la diferencia entre ocurrencia de los eventos y la disponibilidad de los datos en la plataforma).

</Accordion>

<div id="meta-ads" />

<Accordion title="Métricas de Meta Ads">

**Nota:**

* Habrá diferencias en el número de aplicaciones reportadas por Anuncios de Meta y AppsFlyer debido a la diferente lógica de atribución.
* Meta no informa sobre las instalaciones en el nivel de recurso para iOS, por lo que no está disponible en Creative.

</Accordion>

<div id="unity-ads-metrics" />

<Accordion title="Métricas de Unity Ads">

**Para obtener métricas de partners desde Unity Ads:**

1. Desde el dashboard de Optimización Creativa, haz clic en el icono ⋮  en la parte superior derecha para llegar a **Integraciones creativas**.  
   <Image align="center" alt="icono de integraciones creativas.jpg" src="https://files.readme.io/5af3cc395743cf305a9d19dca41dc53c7cbf82e18434d2eb335c9e58a4245456-21366803702033.jpg" />
2. Haz clic en **+ Nueva integración**.
3. Selecciona **Unity Ads** en la lista desplegable **Partner**.  
   <Image align="center" alt="New integration - Unity Ads.jpg" src="https://files.readme.io/8a03c4b50287768cd95217af142ec551c8526b2cf5f7f7af06c04704a868093d-18564745005073.jpg" />
4. Introduce el **ID de clave** de Unity, la **Clave secreta** y el **ID principal de la organización** para la integración (consulta las instrucciones de <Anchor target="_blank" href="/marketers/es/docs/creative-optimization-partner-integrations#unity-ads">integración de Unity</Anchor> para obtenerlos).
5. En la sección **Métricas del partner**, ingresa la **clave de la API** de Unity y el **ID de la organización**. Puedes recuperar estas credenciales siguiendo las siguientes instrucciones. **Nota:** Si tienes una integración de costos de ROI360 con Unity Ads, también puedes tomar las credenciales desde allí.
   * **Para obtener la clave de la API:**
     1. Inicia sesión en tu plataforma de Unity Gaming Services.
     2. Haz clic en **Productos** en el menú lateral, luego haz clic en **Crecimiento**.  
        <Image align="center" alt="Unity Org ID step 1.jpg" src="https://files.readme.io/79d445c8588ef6fa7b34ad8983d068b80a7ab733e7dd9906ad079fa647b3e10b-20348482802833.jpg" />
     3. Haz clic en **Adquisición de usuarios de Unity Ads**.  
        <Image align="center" alt="Unity Org ID step 2.jpg" src="https://files.readme.io/1e0efbece8777100ac7046f09c52887f52bc5fba2e28c724298340afe78ba8f4-20348466710545.jpg" width="312px" />
     4. Haz clic en **API management** (Administración de la API).  
        <Image align="center" alt="Unity-from API mngmt, get API key w arrow.jpg" src="https://files.readme.io/c617593d5935fbe8072d9fac0146fb3257c395c8dcf173130b97cc2a4a043285-20348783332881.jpg" />
     5. Copia la clave de la API:
   * **Para obtener el ID de la organización:**
     1. Dentro de Unity Ads, haz clic en **Productos** en el menú lateral, luego haz clic en **Crecimiento**.  
        <Image align="center" alt="Unity Org ID step 1.jpg" src="https://files.readme.io/79d445c8588ef6fa7b34ad8983d068b80a7ab733e7dd9906ad079fa647b3e10b-20348482802833.jpg" width="583px" />
     2. Haz clic en **Adquisición de usuarios de Unity Ads**.
     3. <Image align="center" alt="Unity Org ID step 2.jpg" src="https://files.readme.io/1e0efbece8777100ac7046f09c52887f52bc5fba2e28c724298340afe78ba8f4-20348466710545.jpg" width="336px" />
     4. Haz clic en **Configuración**.  
        <Image align="center" alt="Get Organization ID instructions 2 arrows.jpg" src="https://files.readme.io/7514d25a8c9a7a9f64e7e5b6f9008c649cb949eff7d25c49a1693f806518e07d-20348948474897.jpg" />
     5. Copia el **ID de la organización**

<div id="note" />

> 📘 **Nota**
>
> Recomendamos ingresar las credenciales de métricas de partners al configurar una nueva integración de partners. Sin embargo, no es obligatorio. Puedes guardar la integración y agregar las credenciales en un momento posterior. Pero ten en cuenta que extraemos 90 días de datos de partners desde el momento en que se crea la integración del partner, por lo que no ingresar las credenciales de la métrica del partner puede resultar en la falta de datos.

</Accordion>

</Accordion>

<div id="save-and-share-views" />

<Accordion title="Guardar y compartir vistas">

Después de seleccionar tus filtros, puedes guardar tus selecciones para tener acceso rápido y fácil a la información que deseas ver en los dashboards, por lo que no es necesario volver a seleccionar los filtros cada vez que inicies sesión. La vista guardada se aplica tanto al dashboard general de la Optimización Creativa como al de descubrimiento. Puedes guardar una vista del dashboard como privada o compartida. Las vistas compartidas son visibles para otros usuarios de la cuenta. Además, puedes compartir vistas del dashboard con otros a través de la URL de compartir.

**Nota**: Un indicador naranja aparece junto a la vista actual si has realizado cambios en la configuración del dashboard sin guardar la vista.

<div id="save-private-dashboard-view" />

#### **Guardar vista del dashboard privado**

**Para guardar una vista del dashboard privado (solo visible para ti):**

1. En la parte superior del dashboard que se está mostrando actualmente, haz clic en el ícono de menú desplegable, asegúrate de que el menú tenga seleccionado el ícono privado y luego haz clic en **+ Guardar como nuevo dashboard privado.**  
   <Image align="center" alt="" src="https://files.readme.io/c1ed2ac6917fa105641f054623ad87a562f4b80042379301c8736bffaa57a22e-25381406386065.png" />
2. Ingresa un nombre para el dashboard y hax clic en **Guardar**.
3. Utiliza los íconos del menú para editar y eliminar vistas del dashboard, cambiar la configuración de uso compartido de privada a compartida, o marcar una vista como favorita, estableciéndola como la vista predeterminada que se mostrará al iniciar sesión.

<div id="save-shared-dashboard-view" />

#### **Guardar vista de dashboard compartido**

**Para guardar una vista de dashboard compartido (visible para otros usuarios de la cuenta):**

1. En la parte superior del dashboard que se está mostrando actualmente, haz clic en el ícono de menú desplegable, asegúrate de que el menú tenga seleccionado el ícono compartido y luego haz clic en **+ Guardar como nuevo dashboard compartido.**  
   **![](https://files.readme.io/d4a7f206d49ddea230883ee6e119caab119164fa3bee9d0c3f02d487c9cf8a36-25381406390033.png)**
2. Ingresa un nombre para el dashboard y hax clic en **Guardar**.  
   La vista está guardada y aparece en la lista de vistas del dashboard para todos los demás usuarios de la cuenta.
3. Utiliza los íconos del menú para editar y eliminar vistas del dashboard, cambiar la configuración de uso compartido de compartida a privada, o marcar una vista como favorita, estableciéndola como la vista predeterminada que se mostrará al iniciar sesión.

<div id="share-view-url" />

#### **Compartir URL de vista**

**Para compartir una URL de vista con otro usuario de cuenta:**

* Haz clic en el icono en la parte superior derecha del dashboard para copiar la URL de la página y luego compartirla.  
  <Image align="center" alt="Copy_page_URL_with_cursor.jpg" src="https://files.readme.io/2d1cc2f9585850c1d9c723f959be96e953fe6cc90b6b2a31ac8c16bf4e7b4b8f-18564702245777.jpg" width="121px" />
  **Nota**: Las URL de vista se pueden compartir incluso para dashboards privados. Cuando se abre la URL del dashboard privado, el nombre del reporte que se muestra es "Reporte no guardado".

</Accordion>

<div id="custom-tags" />

## Etiquetas personalizadas

Agrupa y analiza tus creatividades en función de las etiquetas que subas o por los identificadores únicos que se almacenan en los nombres de archivo. En esta sección se describen las diferentes formas de crear etiquetas personalizadas, las cuales aparecen como dimensiones que puedes seleccionar en los filtros y visualizar a lo largo de los dashboards.

<div id="custom-dimensions" />

<Accordion title="Etiquetas personalizadas a través de CSV">

Puedes agregar dimensiones personalizadas al dashboard. Estas dimensiones personalizadas y las creatividades etiquetadas asociadas se agregan a través de un archivo CSV y se alinean con las creatividades actuales utilizadas en las distintas campañas. Utiliza esta función para ver, organizar, ordenar y filtrar creatividades por las dimensiones y etiquetas personalizadas que desees.

<div id="create-and-manage-custom-dimensions" />

<Accordion title="Crear y administrar dimensiones personalizadas">

El proceso de creación y gestión de dimensiones personalizadas incluye las siguientes 3 acciones:

1. Descargar un archivo CSV desde el dashboard de Optimización Creativa que contiene las creatividades actuales.
2. Crear nuevas dimensiones o cambiar las dimensiones y etiquetas actuales. Cada encabezado de columna en el archivo CSV es el nombre de la dimensión personalizada (Por ejemplo: “Color”). Todas las creatividades de esta columna se etiquetarán con la dimensión personalizada y se mostrarán debajo de esta etiqueta en el dashboard. Puedes agregar o cambiar cualquiera de las dimensiones o etiquetas personalizadas a través del archivo CSV. **Nota**: El nuevo CSV no necesita incluir etiquetas y dimensiones personalizadas creadas anteriormente; solo las que deseas editar o agregar.
3. Subir el archivo CSV actualizado en el dashboard de Optimización Creativa. Los datos estarán disponibles después de unos 30 minutos.

A continuación se describen los procedimientos para descargar y subir el archivo CSV:

**Para descargar un archivo CSV con las creatividades actuales desde el dashboard:**

1. Haz clic en el <Image alt="3_dots_icon.png" src="https://files.readme.io/e958f262f824e2d6d259f123f550697f2916628c71cde515697e51af832d2410-18564718539665.png" width="16px" /> menú en la esquina superior derecha del dashboard.  
   <Image align="center" alt="Main menu highlighted.jpg" src="https://files.readme.io/be14a3ab1a9aba6dc20816e53ad692b1697d15a185053cf523d2ae8451842350-21367268248465.jpg" />
2. Haz clic en **Descargar archivo de etiquetas personalizadas**.
3. Selecciona qué creatividades deseas incluir en el archivo (todas las creatividades o solo las creatividades que se muestran actualmente en el dashboard, excluyendo las creatividades que están filtradas).
4. Haz clic en **Descargar**.

Haz las adiciones o cambios deseados en el archivo, luego guarda y vuelve a cargarlo en el dashboard.

**Para subir el archivo CSV al dashboard de Optimización Creativa:**

1. Haz clic en el <Image alt="3_dots_icon.png" src="https://files.readme.io/e958f262f824e2d6d259f123f550697f2916628c71cde515697e51af832d2410-18564718539665.png" width="16px" /> menú en la esquina superior derecha del dashboard.
2. Haz clic en **Subir archivo de etiquetas personalizadas**.
3. Selecciona un archivo para subir.  
   Asegúrate de estar al tanto de las diferentes [características y limitaciones](/docs/creative-optimization-guide#traits-and-limitations) al subir un archivo CSV.
4. Haz clic en **Subir al dashboard**.

Los datos estarán disponibles en aproximadamente 30 minutos.

</Accordion>

<div id="example-csv" />

<Accordion title="Ejemplo de CSV">

Aquí hay un ejemplo de un archivo CSV de dimensiones personalizadas (que se descarga desde el dashboard). Cada encabezado de columna (en la fila 1) es el nombre de una dimensión personalizada (por ejemplo: "Tema" o "Variante"). Puedes agregar dimensiones adicionales o cambiar las existentes. También puedes agregar o cambiar las etiquetas (por ejemplo: "3 Movimientos" o "Paleta Oscura".

<Image align="center" alt="Screen_Shot_2022-08-08_at_16.25.23.png" src="https://files.readme.io/33137d3c8eab51069a3863a2af193d2192cd28546442abcaf8b74073e737c63e-18564702296977.png" />

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Características y limitaciones de las dimensiones personalizadas">

* Las dimensiones personalizadas aparecen con una etiqueta “Personalizada” en los filtros y la tabla.

<Image align="center" alt="Custom_tag.png" src="https://files.readme.io/f8003396943a406dec2b825f4a4725aeb2f0ea3b23f3c67643cc0c096321b401-18564730363025.png" width="477px" />

* Puedes agregar hasta 15 dimensiones personalizadas al dashboard de Optimización Creativa.
* El tamaño del archivo de subida está limitado a 1 MB.
* Las dimensiones y los nombres de las etiquetas existentes se pueden cambiar actualizando el archivo CSV y volviendo a subirlo. **Nota**: Solo puedes actualizar o agregar una dimensión por carga de archivo.
* Las dimensiones personalizadas definidas en el archivo CSV se aplican a nivel de cuenta, es decir, a todas las aplicaciones y usuarios.
* Cada creatividad puede tener una etiqueta por dimensión. Por ejemplo, si "Color" es la dimensión personalizada, la etiqueta solo puede ser de un color, como el rojo.
* Al crear o editar las dimensiones personalizadas, asegúrate de no cambiar el creative\_id para evitar discrepancias.

</Accordion>

</Accordion>

<div id="name-convention-tags" />

<Accordion title="Etiquetas de convención de nomenclatura">

Puedes crear etiquetas personalizadas basadas en tus convenciones de nomenclatura de recursos creativos. Estas etiquetas personalizadas aparecerán como dimensiones que puedes seleccionar en los filtros y ver en todo el dashboard.

Esto es útil para equipos creativos y de marketing cuyas creatividades se nombran intencionalmente, con identificadores únicos integrados en los nombres. Estas creatividades pueden etiquetarse automáticamente por los identificadores integrados y agruparse para fines de análisis y optimización.

<div id="create-and-manage-name-convention-tags" />

<Accordion title="Crear y editar etiquetas de convención de nomenclatura">

**Para crear etiquetas de convención de nomenclatura:**

1. Haz clic en el ícono  ⋮  de la parte superior derecha del dashboard y selecciona **Etiquetas de convención de nomenclatura**.  
   Aparecerá la ventana **Administrar etiquetas de convención de nomenclatura**.  
   <Image align="center" alt="Name convention tags main window.jpg" src="https://files.readme.io/e59721daabccd23ae7735d3e8cca68194983a3c28453daf00bf0ab39ad76fa98-18564727397393.jpg" width="795px" />
2. En **Crear nuevo tipo de convención de nomenclatura**, ingresa los detalles:
   * **Nombre** - Asigna un nombre único al nuevo tipo de convención de nombres.
   * **Separador**: el carácter que separa cada sección. Por ejemplo, en una creatividad llamada “enUS\_bluegalaxy\_launch.mp4”, cada sección está separada por “\_”. “\_” es el separador.
   * **Número de secciones**: por ejemplo, en una creatividad llamada “enUS\_bluegalaxy\_launch.mp4”, hay 3 secciones separadas por un “\_”.  
     **Nota:** El tipo de archivo no está incluido en las etiquetas.
   * **Aplicación** (opcional): puedes incluir todas las aplicaciones o limitar las etiquetas a las creatividades asociadas solo con ciertas aplicaciones.
   * **Fuente de medios** (opcional): puedes incluir todas las fuentes de medios, o limitar las etiquetas a creatividades que se ejecutaron solo en ciertas fuentes de medios.
3. Añade los detalles de la etiqueta personalizada:
   * **Número de sección**: selecciona el número de sección de la etiqueta que deseas crear.
   * **Nombre de etiqueta personalizada**: crea un nombre haciendo clic en **+ Crear nueva etiqueta personalizada**, o selecciona un nombre existente.
   * **Formato**: selecciona cómo deben aparecer las etiquetas en toda la tabla/dashboard: en mayúsculas, minúsculas o el formato original (tal cómo aparece originalmente en el nombre de la creatividad).  
     Puedes agregar etiquetas personalizadas adicionales haciendo clic en **+ Agregar etiqueta personalizada**.
4. Antes de guardar, puedes obtener una vista previa de cómo se aplicarán tus etiquetas personalizadas a tus creatividades haciendo clic en **Descargar archivo de vista previa** (opcional). Esto descargará un archivo con todas las creatividades que coincidan con el tipo de convención de nomenclatura que estás creando, con todas ellas según las nuevas etiquetas.
5. Haz clic en **Guardar**.  
   Las etiquetas se aplicarán y estarán disponibles en el dashboard en unas pocas horas.

**Para editar etiquetas de convención de nomenclatura:**

1. Haz clic en el ícono  ⋮  de la parte superior derecha del dashboard y selecciona **Etiquetas de convención de nomenclatura**.
2. Haz clic en el menú desplegable **Editar tipo de convención de nomenclatura** para hacer tu selección.
3. Haz los cambios necesarios y haz clic en **Guardar**.

**Para eliminar un tipo de convención de nomenclatura:**

1. Haz clic en el menú desplegable **Editar tipo de convención de nomenclatura** y selecciona la que deseas eliminar.
2. Haz clic en el <Image alt="icono de eliminar.jpg" src="https://files.readme.io/a4bb54fefcdd474edbb897dc334b8219c36273fd5e4f45a03e1b39091856e137-18564742905873.jpg" width="19px" />  que aparece cuando pasas el mouse a la derecha de tu selección.  
   **Nota:** Las etiquetas personalizadas asociadas ya no se aplicarán a tus creatividades. El cambio puede tardar algunas horas en surtir efecto.

<div id="name-tag-traits-and-limitations" />

<Accordion title="Rasgos y limitaciones de la etiqueta de nombre">

* Puedes crear hasta 10 tipos de convenciones de nomenclatura diferentes (y las etiquetas personalizadas asociadas).
* Si las etiquetas personalizadas que se han subido a través del archivo CSV entran en conflicto con las etiquetas de convención de nomenclatura que has creado, las etiquetas CSV cargadas tendrán prioridad y solo se aplicarán esas etiquetas.

</Accordion>

</Accordion>

</Accordion>

<div id="additional-information" />

## Información adicional

<div id="h_01HA282W8WHHNDG75XZNSV2QQF" />

<Accordion title="Características y limitaciones">

| Caducado | Observaciones |
| --- | --- |
| Fuente de datos | El origen de los datos de rendimiento en los dashboards de Optimización Creativa (aparte de las métricas de partners) proviene del modelo de atribución de AppsFlyer. **Nota**: Ten en cuenta que existen diferencias en los modelos de atribución utilizados por las distintas plataformas publicitarias y jugadores en el ecosistema publicitario móvil, lo que puede explicar las discrepancias de notificación entre ellos. |
| Múltiples recursos | Para las creatividades que incluyen múltiples recursos, solo se muestra uno (generalmente el video cuando corresponda). |
| Actualización de los datos | Los dashboards Vista general y Discovery de Optimización creativa se actualizan una vez al día a las 10:00 UTC (se actualizan los datos creativos de los últimos 90 días).<br /><br />Según tu zona horaria, la actualización diaria se realiza a:<ul><li>Nueva York: 5:00 a. m. EST / 6:00 a. m. EDT</li><li>Berlín: 11:00 a. m. CET / 12:00 p. m. CEST</li><li>Shanghái: 6:00 p. m. CST</li></ul>Para otras ubicaciones, convierte las 10:00 UTC a tu zona horaria local.<br /><br />**Nota:** Los datos de Optimización creativa se actualizan una vez al día, mientras que el dashboard general principal de AppsFlyer se actualiza en tiempo real, lo que puede provocar discrepancias temporales. |
| Truemoney | Todas los métricas monetarias en la Optimización Creativa están en USD. |

</Accordion>

<div data-zendesk-anchors="overview=sobre-la-optimizaci%C3%B3n-creativa 01H7SZ8R9ZWZ81WHV26P00YAYP=sobre-la-optimizaci%C3%B3n-creativa creative-assets=recursos-creativos 01H7SZ8RA14Q5D32EY5J0WMVYA=recursos-creativos 01H7SZ8RA1C863VRG1P10CJHTR=supported-asset-types h_01HMXES26N1X3KAFRKKCC9NFXW=notas 01H7SZ8RA1D9JVG1145CAXEZFX=matching-creatives 01H7SZ8RA191221K683N1Z9R69=measuring-creatives-with-multiple-assets 01H7SZ8RA1KRPFF9AW5P4QKQXH=ejemplo creative-dashboard=uso-del-dashboard 01H7SZ8RA1JX2TCQHB5XW21EK8=uso-del-dashboard 01H7SZ8RA1ATSBZPMFJC0T7HRG=filter-bar 01H7SZ8RA1RT91HKKD0R93T2TA=view-type h_01HJDKZWTQVTPSJXP2HWSMD8W6=creative-optimization-roi360 h_01H9JS005MCGMPJM7NYTW2HCAF=standard-metrics-and-dimensions 01H7SZ8RA222QS1AXDKT49DEK3=unique-metrics-and-dimensions 01H7SZ8RA23SCGJ435B4V32CP1=custom-metrics 01H7SZ8RA2R9N2NC6JXNZZ7C5Z=partner-dimensions-and-metrics partner-table=para-configurar-las-m%C3%A9tricas-de-partners 01H7SZ8RA2VJ9466WSMN3WHR90=para-configurar-las-m%C3%A9tricas-de-partners 01H8GHNPQKS7REZ9RPH0ZYEBHE=applovin-metrics 01H8GHNPQKCKMDS8AYETEDDZKH=google-ads-metrics 01H8H1GTRV7VNJDKFEF35HCNKY=meta-ads 01H7SZ8RA28T63K3NASWC92R0F=unity-ads-metrics 01H7W4JTRSJJ2R45JQVYHMYGX2=nota 01H7SZ8RA3TPD6ED2HJZGTVRMS=save-and-share-views save-private-dashboard-view=guardar-vista-del-dashboard-privado h_01HYT77DSHZ6FE0MSQS83FRGW0=guardar-vista-del-dashboard-privado save-shared-dashboard-view=guardar-vista-de-dashboard-compartido 01HYT89BRYKRG44AT9MZWKZJNY=guardar-vista-de-dashboard-compartido share-view-url=compartir-url-de-vista h_01HYT8GXVJV8Q6GKBDHTTJ1SM2=compartir-url-de-vista custom-tags=etiquetas-personalizadas h_01H9J4Z9V9SJBTE63C358FME95=etiquetas-personalizadas h_01H9J4R9MTMGF9F1PNZRT2QZ1W=custom-dimensions 01H7SZ8RA3GW927GJBKKR4582T=create-and-manage-custom-dimensions 01H7SZ8RA3P8VQFH268G453FKM=example-csv 01H7SZ8RA307CBMA0533M3VGWK=traits-and-limitations h_01H9J67GSXXZ20W56NDVW2XDJC=name-convention-tags h_01H9J6PCQNVAB88ZCKRT3MVJEH=create-and-manage-name-convention-tags h_01H9J6PCQN6MV2KPYNFF7SB44Q=name-tag-traits-and-limitations additional-information=informaci%C3%B3n-adicional h_01J1VPMV85CT5ZJNN3BW4FCW0D=informaci%C3%B3n-adicional" />
