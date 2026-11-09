---
title: Guía de Incrementalidad para UA
metadata:
  keywords:
    - Premium
    - Marketers
    - Incrementality
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-niv-klein
    - Marketers
    - Incrementality
  created_at: '2025-11-18T06:58:45Z'
  edited_at: '2026-08-17T11:47:54Z'
  id: 41021758795025
  locale: es
  section: Incrementality for UA
  section_id: 40761623209873
  url: https://support.appsflyer.com/hc/es/articles/41021758795025
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Resumen:** Ejecuta un experimento de Incrementalidad para entender el impacto real de tus campañas de adquisición de usuarios (UA).

<Embed title="Guía de Incrementalidad para UA" typeOfEmbed="youtube" url="https://www.youtube.com/embed/vGrLyOvgdN0?si=91ZV8Xw25mmShB_F" providerUrl="https://www.youtube.com" />

<div id="about-incrementality-for-ua" />

## Información sobre Incrementalidad para UA

En el entorno actual del marketing omnicanal, comprender la eficacia real de una campaña requiere algo más que una sola perspectiva. La atribución de último toque sigue siendo esencial para el monitoreo del rendimiento en tiempo real y para obtener insights granulares, pero no proporciona información sobre si una campaña generó un incremento causal real. Incrementalidad para UA añade una capa crítica al medir si las campañas realmente impulsan el crecimiento de nuevos usuarios.

**Incrementalidad para UA** lo hace complementando la atribución con geoexperimentos científicamente rigurosos. Estos experimentos automatizados miden el incremento causal real de tus campañas, lo que permite asignar el presupuesto de forma más inteligente y tomar decisiones con más confianza.  
Como líder de confianza en marketing cloud, AppsFlyer ofrece Incrementalidad para UA, una forma potente de medir el impacto real de tus campañas. Esta solución ofrece insights críticos y fiables junto con la atribución, lo que permite una medición completa y fluida en una única plataforma unificada.

**¿Por qué usar Incrementalidad para UA?**  
Los equipos de adquisición de usuarios se enfrentan hoy a desafíos complejos, como viajes de usuario fragmentados, restricciones de privacidad cada vez mayores y brechas de visibilidad en varios canales. Incrementalidad para UA te ayuda a superar estas barreras al mostrar el impacto real en el negocio de tus campañas.

**Con Incrementalidad para UA, puedes:**

* **Céntrate en la performance real:** Obtén insights adicionales más allá del engagement con anuncios y las conversiones atribuidas. Entiende qué campañas impulsan realmente el crecimiento y amplía la visión que proporciona la atribución.
* **Haz comparaciones directas:** Prueba varias campañas o fuentes de medios a la vez con asignación automatizada de grupos de prueba y control, y soporte nativo de las principales plataformas publicitarias, como Meta, Google Ads y TikTok.
* **Optimiza la asignación del presupuesto:** Redirige el gasto de las campañas de bajo impacto y reinviértelo en las que impulsan un crecimiento real de usuarios.
* **Automatiza los flujos de trabajo de los experimentos:** Evita la configuración manual y las dependencias de BI. AppsFlyer automatiza el diseño, la ejecución y el análisis de los experimentos.
* **Mide pensando en la privacidad:** Los experimentos se ejecutan con datos agregados a nivel geográfico y cumplen normativas de privacidad como el RGPD y ATT de Apple.

**Información sobre la geoexperimentación**

Incrementalidad para UA utiliza un diseño experimental basado en la geolocalización. Las regiones geográficas se dividen en grupos estadísticamente similares, según las instalaciones históricas o el comportamiento de eventos de la app. Un grupo se expone a tu campaña de UA y al otro no se le expone. Después de que el experimento se ejecute durante un periodo determinado, se analiza la diferencia de rendimiento entre los dos grupos para revelar el lift incremental. La experimentación geográfica protege la privacidad, resiste los sesgos y no depende de datos a nivel de usuario.

Incrementality for UA te proporciona los insights que necesitas para comprender el verdadero valor incremental de tus campañas de marketing, sin verse afectado por datos incoherentes a nivel de usuario ni por solapamientos de targeting. Esto te dará una imagen fiel de la eficacia de tus campañas y te ayudará a tomar mejores decisiones basadas en datos.

<div id="experiment-design-and-insights" />

## Diseño de experimentos e insights

En esta sección se explica cómo se estructuran los experimentos de Incrementality for UA, cómo trabajar con ellos y cómo generan insights causales y fiables sobre la performance de las campañas.

<div id="understanding-geo-experimentation-explainer" />

<Accordion title="Entender la experimentación geográfica">

Incrementality for UA utiliza experimentación basada en geolocalización para medir el impacto real de las campañas de forma científicamente rigurosa. En lugar de segmentar usuarios, segmentamos áreas geográficas en regiones expuestas y de control estadísticamente similares. Estas regiones se seleccionan en función de su tamaño y del comportamiento histórico de la aplicación. Los anuncios se publican solo en las regiones expuestas, mientras que las regiones de control no reciben ninguna exposición. Al comparar el comportamiento de los dos grupos durante el periodo de control, podemos medir el efecto causal real, no solo la correlación.

**Los experimentos de geolocalización siguen una cronología estructurada:**

* **Prueba previa:** Ambos grupos reciben la misma exposición a los anuncios de las campañas medidas. Durante este tiempo, recopilamos datos de referencia y construimos un modelo que capta la relación histórica entre las regiones expuestas y las regiones de control.
* **Intervención (el experimento):** Las campañas se activan solo en las regiones expuestas. Se impide que las regiones de control vean anuncios de las campañas medidas.
* **Cálculo del efecto causal**: La diferencia entre los resultados observados en las regiones de control y en las regiones expuestas durante el experimento se suma a lo largo del tiempo y se utiliza para determinar el impacto acumulado.

**Regresión basada en el tiempo (TBR)**

En el núcleo de nuestra experimentación basada en geolocalización se encuentra la regresión basada en el tiempo (TBR). TBR se utiliza para calcular el lift de marketing al predecir lo que habría ocurrido en ausencia de una intervención de marketing. Esto implica comparar los resultados observados en una región expuesta (donde se realiza la intervención) con los resultados previstos a partir de la relación histórica entre una región de control (no expuesta a la intervención) y la región expuesta.

**Cómo funciona:**

* Creación de diseños de geolocalización de regiones de control y expuestas:
  * Para cada aplicación, AppsFlyer analiza el comportamiento histórico de la instalación de la app o de los eventos in-app y utiliza TBR (explicado en los siguientes pasos) en miles de conjuntos aleatorizados de regiones geográficas de control y expuestas a lo largo de varios periodos para encontrar los que presentan la menor diferencia.
* Periodo de prueba previa:
  * Durante este tiempo, antes de que comience la intervención, se recopilan datos tanto de las regiones de control como de las expuestas.
  * Se crea un modelo de regresión para reflejar la relación entre las series temporales de la región expuesta y la región de control.
* Predicción de contrafactuales:
  * Con el modelo desarrollado en el periodo previo a la prueba, se predicen los resultados esperados para la región de control (si no se hubiera producido ninguna intervención) durante el periodo de prueba. Estos se denominan "contrafactuales".
* Periodo de prueba:
  * En las campañas que forman parte del experimento de incrementalidad, las regiones de control predeterminadas quedan excluidas automáticamente de la visualización de anuncios durante toda la duración del experimento.
* Cálculo del efecto causal:
  * El efecto causal de la intervención en cada momento temporal es la diferencia entre el resultado observado en la región de control y su predicción contrafactual.
* Efectos acumulados:
  * Estas diferencias se suman a lo largo del tiempo para determinar el impacto acumulado de la intervención (por ejemplo, el aumento total de instalaciones o conversiones).
* Incremento de marketing:
  * El incremento de marketing es el efecto acumulado que cuantifica los resultados incrementales impulsados por la actividad de marketing en comparación con lo que se habría esperado sin ella.

</Accordion>

<div id="use-cases" />

<Accordion title="CASOS DE USO">

La incrementalidad para UA te ayuda a resolver retos clave de crecimiento al revelar el verdadero impacto empresarial de tus campañas. A continuación se muestran algunos casos de uso habituales en los que las pruebas de incrementalidad basadas en geolocalización aportan un valor fundamental.

1. **Optimiza la asignación del presupuesto entre plataformas de anuncios**  
   **Desafío:** Las métricas de atribución muestran un rendimiento similar en varias plataformas, pero no tienes claro cuál está impulsando realmente el crecimiento. **Solución:** Ejecuta pruebas de incrementalidad en paralelo usando varias celdas en distintas plataformas. Usa los resultados para identificar qué plataforma genera un incremento real y redistribuir el presupuesto en consecuencia.
2. **Valida la performance de nuevos canales o formatos**  
   **Desafío:** Estás probando un nuevo canal o una plataforma de anuncios nueva, pero las métricas iniciales son incoherentes o están infladas debido a la superposición del targeting. **Solución:** Usa pruebas de geolocalización para aislar el impacto del nuevo canal del resto de tu mix. Determina si contribuye a instalaciones netas nuevas o si solo canibaliza las existentes.
3. **Comprende el impacto de las campañas de marca**  
   **Desafío:** Las campañas de marca tienen buen rendimiento en los reportes de atribución, pero no sabes si los usuarios habrían convertido igualmente. **Solución:** Los experimentos de geolocalización pueden mostrar si los anuncios de búsqueda de marca o los anuncios de display realmente están influyendo en el comportamiento de los usuarios, o si están captando una demanda ya existente.
4. **Compara estrategias de campaña dentro de la misma plataforma**  
   **Desafío:** Quieres probar dos estrategias creativas (por ejemplo, vídeo frente a carrusel) o tipos de puja (por ejemplo, maximizar instalaciones frente a ROAS) dentro de la misma red. **Solución:** Ejecuta un experimento multicelda con cada estrategia asignada a una celda diferente. Compara el lift incremental de cada uno y elige el ganador.
5. **Reasigna el gasto de mercados saturados a mercados escalables**  
   **Desafío:** Los mercados maduros muestran rendimientos decrecientes y costos de adquisición al alza, pero los Datos de atribución no aclaran si estás llegando a nuevos usuarios. **Solución:** Las pruebas de geolocalización-lift muestran si las campañas en estos mercados siguen siendo incrementales. Si no es así, traslada presupuesto a regiones no explotadas o infravaloradas con mayor potencial.

</Accordion>

<div id="selecting-campaigns" />

<Accordion title="Seleccionar qué medir">

En esta sección se describen las mejores campañas para seleccionar en tus experimentos. Aquí tienes algunas cosas a tener en cuenta:

* **Impacto:** ¿Qué prueba podría influir más en tu estrategia general? A menudo, eso significa empezar por tus iniciativas más importantes, ya que comprender mejor cómo afectan al crecimiento dará lugar a optimizaciones significativas.
* **Volumen de conversiones:** Los experimentos sólidos necesitan suficientes datos. Para cada campaña medida, intenta alcanzar un mínimo de 5000 instalaciones mensuales de la app o eventos, según el KPI principal que quieras medir
* **Exploración:** La incrementalidad es una herramienta excelente cuando pruebas algo nuevo, como entrar en un mercado nuevo o lanzar un canal nuevo.
* **Tener una hipótesis clara o una pregunta de prueba:** Como en cualquier otro experimento científico, dedicar algo de tiempo a formular tu pregunta principal contribuirá a la efectividad y capacidad de acción de tu experimento de incrementalidad. Por ejemplo, ¿esperas que un canal sea más incremental que el otro? ¿Cómo afectará a tu estrategia de marketing si se demuestra o se refuta tu hipótesis?

</Accordion>

<div id="understanding-experiment-results" />

<Accordion title="Comprender los resultados de los experimentos y usar los insights">

**Los principales resultados de KPI del experimento incluyen:**

* **Lift (%):** El impacto causal de la actividad de marketing medida, expresado como las conversiones adicionales (por ejemplo, instalaciones o eventos in-app) que tu campaña impulsó realmente, por encima de lo que habría ocurrido sin ella.
* **Conversiones incrementales:** El número de instalaciones o eventos causados por la campaña medida.
* **Costo por instalación incremental** / **Costo por evento incremental:** El costo medio de cada conversión incremental, según el gasto en anuncios de la campaña.
* **Factor de incrementalidad:** La relación entre las instalaciones o los eventos incrementales (según los mide el experimento) y las instalaciones o los eventos de atribución clásica (según se miden en la atribución clásica de AppsFlyer).

Consulta la lista completa de KPI del experimento en la [sección del Dashboard.](#un-tour-por-el-dashboard)

Para que los insights de incrementalidad sean accionables, AppsFlyer proporciona tanto el Lift % como los KPI de incrementalidad a nivel de campaña para ayudarte a tomar decisiones de marketing eficaces.

**Optimizar en función del Lift %:**

**A. Sin lift:**  
El objetivo final del marketing es generar resultados incrementales. Si se ha medido que tu campaña no tiene lift (las regiones de control tienen el mismo nivel de rendimiento que las regiones expuestas), esto significa que no está aportando valor más allá de lo que habría ocurrido sin ella y que requiere una mayor optimización para que contribuya de forma significativa al crecimiento. Si tu campaña no tiene lift, ten en cuenta lo siguiente:

* Redistribuye los presupuestos a campañas o canales más incrementales.
* Optimiza: Como en cualquier otra campaña de bajo rendimiento, puedes trabajar para mejorarla ajustando las pujas, los objetivos, el público objetivo, los creativos y otros factores relevantes. A continuación, puedes ejecutar otro experimento de incrementalidad después de la actualización para hacer un monitoreo de si la incrementalidad ha mejorado.
* Diagnostica qué factores podrían estar causando un lift bajo revisando la configuración técnica, el targeting, la combinación de canales, las ubicaciones, los presupuestos, las palabras clave, los creativos o la superposición de campañas. Estos aprendizajes serán muy beneficiosos para optimizar resultados incrementales en el futuro.

**B. Lift positivo:**  
Un lift positivo significa que tu campaña está generando resultados incrementales más allá de lo que se consigue sin ella. Como paso inicial, debes validar que todos tus esfuerzos de marketing estén generando un lift positivo. Cuando el lift es positivo, ten en cuenta lo siguiente:

* Aumenta la inversión en plataformas/canales/campañas para escalar lo que ha demostrado impulsar el crecimiento.
* Amplía el alcance expandiendo las audiencias o las ubicaciones para potenciar el impacto.
* Identifica los factores de crecimiento para replicar el éxito y priorizar las estrategias ganadoras.
* Compara campañas o canales en función del lift: el lift es una medida relativa que se calcula comparando las regiones de control con las regiones expuestas. Por lo tanto, comparar campañas en función del lift es complicado. Por ejemplo, si ambas campañas tienen el mismo impacto, pero una de ellas llega a un número significativamente mayor de usuarios o tiene un gasto significativamente superior, su lift será mayor.  
  Al comparar, intenta comparar campañas que sean similares en gasto y alcance y que, por lo general, hagan targeting en las mismas regiones geográficas.
* Si acabas de empezar con la medición de Incrementality para tu aplicación o negocio, es posible que todavía no tengas una referencia sólida para determinar el nivel exacto de lift positivo esperado de una campaña, canal o inversión determinados. En este caso, se recomienda optimizar con los KPI de Incrementality a nivel de campaña de AppsFlyer, como se describe a continuación.

**Optimizar en función de los KPI de incrementalidad a nivel de campaña:**

**A. Métricas de conversiones incrementales totales y costo:**  
Del mismo modo que se usa en la atribución clásica, el volumen global de conversiones incrementales y el gasto en anuncios invertido para generar estas conversiones proporcionan métricas claras y aplicables para la optimización. Puedes usar el recuento de conversiones de incrementalidad a nivel de campaña y el costo por conversión incremental para determinar si la campaña cumple tus objetivos de volumen y ROI, y cómo funciona frente a otras campañas o canales.

**B. Aprovecha los datos de atribución clásica y de incrementalidad en paralelo**  
Para el recuento de conversiones a nivel de campaña y el costo por conversión, el dashboard de incrementalidad presenta los Datos de atribución clásicos («last-touch») y los datos de incrementalidad en paralelo para que puedas conocer la relación entre ambos modelos y aplicar lo aprendido a mayor escala.  
Si se analizan por separado, la atribución clásica («last-touch») y la incrementalidad son dos modelos de atribución diferentes, cada uno con sus propias ventajas e inconvenientes:

* La atribución clásica («last-touch») es en tiempo real, estandarizada, muy escalable y granular. Por tanto, permite la optimización a nivel de usuario tanto del lado del anunciante como mediante algoritmos en tiempo real de la plataforma de anuncios. Sin embargo, está sesgada hacia el engagement de la parte baja del embudo y no proporciona una prueba causal con base científica.
* La incrementalidad es una herramienta excelente para demostrar científicamente el impacto causal y es ideal para la medición omnicanal. Sin embargo, proporciona insights agregados (a nivel de campaña), es periódica y más difícil de escalar.

Cuando se utilizan juntos, los dos modelos ofrecen una visión holística del rendimiento de marketing. El Factor de Incrementalidad de AppsFlyer muestra la relación entre los datos de atribución clásica, que son la «línea base» utilizada para la optimización continua del marketing, y los datos de incrementalidad, que se utilizan para medir el impacto causal. Así puedes usar los factores de incrementalidad para la optimización:

* **Factor de incrementalidad superior al 100%:** La incrementalidad ha medido más conversiones que las conversiones medidas en la atribución clásica para la misma campaña. Por ejemplo, una tasa del 110%% significa que las conversiones incrementales son un 10%% superiores a las conversiones medidas utilizando atribución clásica. Este aumento de las conversiones también se traduce en una disminución del costo por conversión, ya que se generan más conversiones con el mismo gasto.  
  Si el factor de incrementalidad es superior al 100%, ten en cuenta lo siguiente:
  * Vuelve a evaluar la asignación del presupuesto en función de la disminución del costo por conversión incremental.
  * Vuelve a evaluar las pujas y los objetivos de optimización en función del costo por conversión incremental y del retorno incremental sobre el gasto publicitario.
  * Aplica el factor a campañas similares antes de tomar futuras decisiones de marketing. Por ejemplo, si tus campañas de vídeo muestran de forma constante un factor de incrementalidad de ~110% para las instalaciones de la app cuando se miden en experimentos de incrementalidad, puedes considerar que las instalaciones de la app de la atribución clásica en campañas similares son un 10% superiores al tomar decisiones de marketing (es decir, cada 100 instalaciones de la atribución clásica en realidad se acercan más a 110 instalaciones).
* **Factor de incrementalidad inferior al 100%:** La incrementalidad ha medido menos conversiones que las conversiones medidas en la atribución clásica para la misma campaña. Por ejemplo, una tasa del 90% significa que las conversiones incrementales son un 10% inferiores a las conversiones medidas utilizando atribución clásica. Esta disminución de las conversiones también se traduce en un aumento del costo por conversión, ya que se generan menos conversiones con el mismo gasto. Si el factor de incrementalidad es inferior al 100%, ten en cuenta lo siguiente:
  * Vuelve a evaluar la asignación del presupuesto en función del aumento del costo por conversión incremental.

* * Vuelve a evaluar las pujas y los objetivos de optimización en función del costo por conversión incremental y del retorno incremental sobre el gasto publicitario.
  * Aplica este factor en campañas similares para fundamentar futuras decisiones de marketing. Por ejemplo, si tus campañas de vídeo muestran sistemáticamente un factor de incrementalidad de ~90% para las instalaciones de la app cuando se miden en experimentos de incrementalidad, puedes considerar que las instalaciones de la app por atribución clásica en campañas similares son un 10% inferiores al tomar decisiones de marketing (es decir, cada 100 instalaciones por atribución clásica en realidad se acercan más a 90 instalaciones).

</Accordion>

<div id="pausing-or-extending-experiments" />

<Accordion title="Pausar o ampliar experimentos">

**Considera pausar los experimentos (antes de los 30 días predeterminados) si:**

* Las métricas de lift, factor de incrementalidad y costo se han mantenido estables durante más de 7 días.
* Hay una justificación comercial para obtener resultados más rápidos a costa de métricas de incrementalidad potencialmente menos precisas o menos «normalizadas».

**Considera ampliar los experimentos (más allá de los 30 días predeterminados) si:**

* El volumen de la campaña fue inferior a lo esperado y se prevé que aumente por encima del requisito mínimo de conversiones incrementales diarias.
* La ventana de conversión del evento medido es excepcionalmente larga, por lo que se necesita más tiempo para que los usuarios conviertan.

</Accordion>

<div id="get-started" />

## Comienza

Para empezar con Incrementality for UA, sigue estos pasos:

<span id="h_01J5WC8Z4J352AHSDTRCEP2W9H"></span>**Prerrequisitos**

* Una <Anchor target="_blank" href="https://www.appsflyer.com/sign-up/">cuenta</Anchor> de AppsFlyer con una suscripción a **Incrementality for UA** (pide a tu CSM que la habilite).
* El <Anchor target="_blank" href="/marketers/es/docs/basic-sdk-integration-guide">SDK de AppsFlyer</Anchor> instalado en tus aplicaciones móviles.
* Tu app debe tener al menos 120 días de datos de instalación.

<div id="create-the-experiment-" />

<Accordion title="1. Crea el experimento">

El primer paso es crear el experimento.

**Para crear el experimento:**

1. Accede a Incrementality for UA haciendo clic en **Optimize** > **Incrementality for UA**, en el menú lateral de AppsFlyer.

   <Image align="center" alt="Clic en Inc for UA new.png" src="https://files.readme.io/4170287cc98e038272fd91ee36cbf775a33b8a418920c7fabe54e32cff5789cd-41021731857041.png" width="254px" />
2. Haz clic en **+ Nuevo experimento**.
3. **Rellena el formulario del experimento:**
   1. **Introduce el nombre del experimento**: crea un nombre descriptivo para el experimento y, después, haz clic en **Siguiente**.
   2. **Define tu diseño de geolocalización**: selecciona la app, el país y la métrica principal que quieres medir. AppsFlyer usa esta información para calcular la asignación óptima de las regiones expuestas y de control para tu experimento.

      <Image align="center" alt="step 2 geo design.png" src="https://files.readme.io/3a901bd4dcccb788b1d0cc8f118cbdb0c682b570b470d13deba4f6ce0f852c3b-41021758781713.png" width="335px" />

      Después de enviarlo, AppsFlyer revisa tu diseño geográfico; esto suele tardar solo unos minutos. Tu diseño de geolocalización estará listo para usar o no disponible:

      * **Listo** — Tu diseño de geolocalización está aprobado y listo para usar. Puedes continuar con el experimento.
      * **No disponible** — El diseño de geolocalización no cumple actualmente los requisitos para un experimento válido, según los datos disponibles para la combinación de aplicación, país y métrica seleccionada. Puedes volver a enviarlo al cabo de 30 días, ya que la elegibilidad puede cambiar a medida que tu aplicación recopila más datos.

      <div id="note" />

      > 📘 **Advertencia**
      >
      > Si existen reglas de diseño de geolocalización para la aplicación y el país seleccionados, se aplican automáticamente cuando se calcula el diseño de geolocalización. Consulta la [política de diseño de geolocalización](#h_01_geo-design-policy) para obtener más información.


      <div id="note-1" />

      > 📘 **Advertencia**
      >
      > Cada país tiene un número determinado de **celdas** disponibles para tu experimento. Una celda consta de un par de grupos expuesto y de control estructurados para ser similares entre sí y al conjunto del país. Puedes usar varias celdas en un experimento para realizar una comparación directa de diferentes campañas en diferentes fuentes de medios, o usarlas individualmente en experimentos separados.
      >
      > El número de celdas disponibles por país depende del tamaño geográfico del país, de la distribución de la población y de los niveles de actividad de la app, factores que afectan a la capacidad de crear pares expuesto/control estadísticamente válidos. Los países con regiones más granulares y activas admiten más celdas, lo que permite realizar más experimentación.


      * **Seleccionar app** - Selecciona la app pertinente para el experimento.
      * **Seleccionar país** - A continuación, selecciona el país en el que quieres ejecutar el experimento. Después de la implementación, regresa al **Inicio de sesión único (SSO)** , haz clic en **Confirmar implementación del certificado**y confirma que ha actualizado el último certificado de AppsFlyer.
      * Selecciona la **métrica principal** que quieres medir. Pueden ser instalaciones o un evento in-app.
   3. **Ver detalles de la campaña:**

* Tendrás que seleccionar una conexión de **fuente de medios** para cada celda del experimento. Esta es la fuente de medios en la que se ejecuta tu campaña. Si no hay conexiones, puedes [crear una nueva conexión.](#Connections)
* A continuación, selecciona las campañas pertinentes que quieres medir en el experimento.  
  Los experimentos de incrementalidad se pueden configurar para medir campañas individuales (por ejemplo, «¿Cómo funciona la campaña de Google vs. la campaña de Meta?») o toda la fuente de medios, seleccionando varias campañas dentro de una sola celda del experimento (por ejemplo, «¿Cómo funciona Google vs. Meta?»).  

  Elige entre:  
  **Nivel de campaña:** para medir el impacto de una sola campaña dentro de una fuente de medios  
  **Nivel de canal:** para medir el impacto conjunto de varias campañas dentro de una fuente de medios

  **Nota:** si seleccionas varias campañas dentro de una celda:

  * Todas las campañas seleccionadas compartirán las mismas regiones de control.
  * Los insights de incrementalidad se presentarán a nivel de celda, no a nivel de campaña individual.

    <Image align="center" alt="Inc for UA - Configura los detalles de la campaña .png" src="https://files.readme.io/c92c2b785ea80d2c89fd06033b008a3618e04d88a3cc286e923acf88b5924261-45947468030097.png" width="64.57%" />
* Una vez aprobado un diseño de geolocalización, verás el desglose del experimento:
  * **Regiones de control** - Las regiones excluidas de la exposición a tus campañas durante el experimento
  * **Regiones expuestas** - Las regiones expuestas a tus campañas, utilizadas como referencia de medición
  * **Reglas de diseño de geolocalización** - Tus reglas activas y las regiones que cubren. [Saber más](#h_01_geo-design-policy)
* Al seleccionar un nombre de campaña, a continuación verás el número mínimo de instalaciones o eventos incrementales (según la métrica principal seleccionada) necesario para medir el impacto positivo de tu campaña con un alto grado de confianza estadística. Esto se conoce como el «efecto mínimo detectable» del experimento. Asegúrate de que la campaña seleccionada pueda generar al menos este número de conversiones.

  **Consejo:** Elige una campaña que alcance o supere este mínimo de forma habitual para garantizar resultados fiables y estadísticamente válidos.
* Puedes añadir celdas de experimento adicionales si quieres. Para añadirlas: haz clic en **+ Experiment cell** y selecciona la conexión y la campaña pertinentes. Una celda consta de un par de grupos expuesto y de control, estructurados para ser similares entre sí y al conjunto del país. Puedes usar varias celdas en un experimento para realizar una comparación directa de distintas campañas entre fuentes de medios.  

  Después de configurar las celdas, haz clic en **Siguiente**.

4. **Revisar resumen** - Comprueba que el resumen del experimento sea correcto y, a continuación, haz clic en **Iniciar experimento**.  
   El experimento comienza. Los resultados iniciales se mostrarán en un plazo de 24 horas.

   <div id="note-2" />

   > 📘 **Advertencia**
   >
   > Una vez finalizado el experimento, las campañas conectadas volverán a su configuración anterior de geolocalización. Esto garantiza la continuidad y la coherencia de la campaña, y te permite reanudar las actividades de UA sin necesidad de volver a configurar el targeting de forma manual.
   >
   > **Ejemplo**  
   > Imagina que has ejecutado un experimento en Estados Unidos con tres ciudades expuestas designadas. Durante el experimento, tu campaña se limitó únicamente a esas ciudades. Cuando finalice el experimento, la campaña reanudará automáticamente su targeting original, como «Estados Unidos (todas las ubicaciones)», tal como estaba configurado antes de que comenzara el experimento.


</Accordion>

<div id="analyze-the-results" />

<Accordion title="2. Analiza los resultados y obtén insights">

<span id="zd-access-the-experiment-dashboard"></span><span id="access-the-experiment-dashboard"></span>Puedes ver los resultados del experimento en el dashboard del experimento.

#### Accede al dashboard del experimento

1. Ve a Incrementality for UA para tus experimentos de UA haciendo clic **Optimize** > **Incrementality for UA**, en el menú lateral de AppsFlyer. 

   <Image align="center" alt="desde Optimizar, haz clic en Incrementality UA.png" src="https://files.readme.io/922e084c955b3220a5bc3ac82079515f2c07bc4bc1bc3861343132452cc4fc08-41021731858321.png" width="210px" />
2. Haz clic en el experimento específico para acceder al Dashboard del experimento.

   <Image align="center" alt="Tabla de experimentos (1).png" src="https://files.readme.io/ffc37ed1e7381c73883933cb0de7a84495dd737e050849760e427e36d2b9918d-41021758785041.png" />

<div id="a-tour-of-the-dashboard" />

#### Un tour por el dashboard

[**![New Incrementality dashboard.png](https://files.readme.io/721bab22a6a2f936b99abde0cbf37b38b9b569434bb13eb5e691628d864910ac-small-41021731859729.png)**](https://files.readme.io/721bab22a6a2f936b99abde0cbf37b38b9b569434bb13eb5e691628d864910ac-small-41021731859729.png)

**En la parte superior del dashboard se muestran 2 gráficos visuales:**

* El gráfico **Lift: regiones expuestas vs. de control**: muestra el lift incremental por celda del experimento.
* El gráfico **Cronología del experimento: regiones expuestas vs. de control** : muestra una comparación en paralelo de las instalaciones incrementales por día del intervalo de fechas del experimento, por celda.

La sección central del dashboard muestra los **KPI del experimento** por celda de campaña, fuente de medios y campaña:

* **Instalaciones de atribución clásica:** el número de instalaciones que aportó la campaña, medido mediante atribución clásica.
* **Instalaciones incrementales:** el número de instalaciones que aportó la campaña, medido por el experimento.
* **Factor de incrementalidad:** la relación entre las instalaciones incrementales (medidas por el experimento) y las instalaciones de atribución clásica. Por ejemplo, una tasa del 110% significa que las instalaciones incrementales son un 10% más altas que las instalaciones medidas utilizando atribución clásica.
* **Costo por instalación de atribución clásica:** el costo promedio de cada instalación atribuida, según el gasto publicitario de la campaña.
* **Costo por instalación incremental:** el costo promedio de cada instalación incremental, según el gasto publicitario de la campaña.
* **Lift**: cuántas instalaciones más se produjeron gracias a tu campaña, en comparación con lo que habría sucedido sin ella. Se calcula así: Lift (%) = (rendimiento real en el grupo expuesto (regiones excluidas) - rendimiento previsto en el grupo expuesto) / rendimiento previsto en el grupo expuesto * 100 * -1.
* **Confianza**: el nivel de confianza estadística de que el lift es mayor que cero.  

  Para obtener orientación sobre cómo leer los resultados, consulta [Comprender los resultados del experimento y usar los insights.](#understanding-experiment-results)

En la parte inferior del dashboard se encuentra el gráfico **Instalaciones incrementales acumuladas** , que muestra las instalaciones incrementales acumuladas por celda.

**Nota:** si se selecciona la medición de **nivel de canal** (varias campañas dentro de una celda):

* Todas las campañas seleccionadas compartirán las mismas regiones de control.
* Los insights de incrementalidad se presentarán a nivel de celda, y no a nivel de campaña individual.

<Image align="center" alt="Dashboard de experimentos a nivel de canal recortado más estrecho.png" src="https://files.readme.io/4bcf80c6427e58d13b7ab0380033cb7e34852bd402150b2c05c075e5db3604a3-small-46014061198353.png" width="2862px" />

</Accordion>

<div id="manage" />

## Gestionar

En esta sección se explica cómo gestionar tus conexiones, la política de diseño de geolocalización y los experimentos.

<div id="Connections" />

<Accordion title="Conexiones">

Las conexiones hacen referencia a la integración entre Incrementality for UA y tus Partners de medios. Permiten crear un enlace entre campañas y ejecutar experimentos con plataformas conectadas.

**Para añadir conexiones de fuentes de medios:**

1. Accede a Incrementality for UA haciendo clic en **Optimize** > **Incrementality for UA**, en el menú lateral de AppsFlyer.
2. Haz clic en la pestaña **Connections** y, después, en **+ New connection**.

   <Image align="center" alt="from Connections tab click +New connection w arrow.png" src="https://files.readme.io/e9df79d34ec3d94e89f51f42b132f8ba475225b46246d044d2a720991b0900e0-41021731865745.png" width="465px" />
3. Selecciona una fuente de medios para conectarse.

   <Image align="center" alt="Añadir conexión.png" src="https://files.readme.io/c9eab02131220cd28683a717745bff852da28847a4164fa27b5be4780cd98018-41021731866897.png" width="409px" />
4. Introduce tus credenciales para iniciar sesión y crear la conexión.

</Accordion>

<div id="h_01_geo-design-policy" />

<Accordion title="Política de diseño de geolocalización">

La política de diseño de geolocalización te permite definir reglas de diseño de experimentos geográficos a nivel de cuenta. Las reglas se establecen por app y país, y se aplican automáticamente a todos los diseños de geolocalización calculados después de guardar la regla.

Usa reglas de diseño de geolocalización para adaptarte a restricciones legales, proteger mercados de alto valor o aislar regiones afectadas por pruebas paralelas.

<div id="geo-design-rule-types" />

#### Tipos de reglas de diseño de geolocalización

Hay tres tipos de reglas disponibles:

| Tipo de regla | Qué hace | Ejemplo de caso de uso |
| --- | --- | --- |
| **No incluir en el grupo de control** | Estas regiones nunca se incluyen en grupos de control, pero sí pueden estar en grupos expuestos. Tus campañas en estas regiones nunca se pausan ni se interrumpen por el experimento. | Un mercado de alto rendimiento que debe permanecer activo en todo momento. |
| **No segmentar** | Estas regiones se excluyen por completo del targeting de la campaña. No aparecerán ni en los grupos expuestos ni en los grupos de control. | Un mercado donde la publicidad está legalmente restringida. |
| **Excluir del análisis** | Estas regiones seguirán incluidas en el targeting de la campaña para mantener una actividad publicitaria normal, pero no se incluirán en grupos expuestos ni en grupos de control. | <ul><li>Regiones con pruebas paralelas de geo-lift en funcionamiento que podrían sesgar los resultados.</li><li>Regiones con pruebas de lift geolocalizadas en funcionamiento en paralelo o con iniciativas de marketing local previstas que puedan sesgar los resultados.</li></ul> |

<div id="set-up-a-geo-design-rule" />

#### Configurar una regla de diseño de geolocalización

**Para configurar una regla de diseño de geolocalización:**

1. En Incrementality for UA, haz clic en la pestaña **Advanced settings**.
2. En la sección **Geo design policy**, haz clic en **+ New geo design rule**.
3. En el cuadro de diálogo **New geo design rule**, selecciona la **App** y el **país** a los que se aplica esta regla.
4. En **Rules**, configura cada regla:
   1. <span class="af-ol-a"></span>Selecciona el tipo de **Geo design rule**: Don't holdout, Don't target o Exclude from analysis.
   2. Selecciona las **regiones** (estados o regiones subestatales, según el país). Puedes buscar por nombre o código.
5. Para añadir otro tipo de regla para la misma aplicación y el mismo país, haz clic en **+ Add rule**.
6. Revisa el panel **Summary** de la derecha, que se actualiza en tiempo real a medida que haces selecciones.
7. Haga clic en **Guardar**.

La regla ya está activa y se aplicará a todos los diseños de geolocalización calculados para la aplicación y el país seleccionados a partir de ahora.

<div id="delete-a-geo-design-rule" />

#### Eliminar una regla de diseño de geolocalización

**Para eliminar una regla de diseño de geolocalización:**

1. En la sección **Geo design policy**, busca la regla que quieres eliminar.
2. Abre el menú de acciones y selecciona **Delete**.
3. Confirma en **Delete rule?** .

<div id="note-3" />

> 📘 **Advertencia**
>
> Eliminar una regla no afecta a los experimentos activos. Si había reglas anteriores (o no había ninguna regla), eso es lo que seguirá aplicándose a cualquier experimento que ya esté en funcionamiento. Eliminar una regla solo la quita de futuros diseños o experimentos de geolocalización.

<div id="view-geo-design-rules-in-an-experiment" />

#### Ver reglas de diseño de geolocalización en un experimento

Una vez aprobado un diseño de geolocalización y mientras configuras el experimento, verás una sección de desglose por regiones (marcada como **Rules apply**) que muestra lo siguiente:

* **Holdout regions** - Las regiones excluidas de la exposición a tus campañas durante el experimento
* **Exposed regions** - Las regiones expuestas a tus campañas, utilizadas como línea base de medición
* **Reglas de exclusión** - Las reglas activas (No incluir en holdout, No aplicar targeting, Excluir del análisis) y las regiones específicas que abarcan

En el reporte del experimento, puedes ver el desglose geo completo seleccionando **Desglose del diseño geo** en el menú de acciones. Muestra el mismo desglose que aparece arriba e indica qué reglas estaban activas cuando se creó el experimento. Para gestionar tus reglas, haz clic en **Gestionar la política de diseño geo** al final del panel.

<div id="traits-and-limitations" />

#### Especificaciones y limitaciones

Ten en cuenta lo siguiente al trabajar con reglas de diseño geo:

| Caducado | Nota |
| --- | --- |
| Alcance | Las reglas se aplican por combinación de aplicación y país. |
| Granularidad de geolocalización | Las regiones se definen a nivel de estado o subestado, según el país. |
| Persistencia de las reglas | Las reglas permanecen activas hasta que se eliminan. |
| Retroactividad | Las reglas solo se aplican a los diseños de geolocalización calculados después de guardar la regla. Los experimentos activos no se ven afectados. |

</Accordion>

<div id="Experiments" />

<Accordion title="Experimentos">

Puedes ver y gestionar todos tus experimentos en un solo lugar.

**Para ver y gestionar tus experimentos:**

En **Incrementality for UA**, haz clic en la pestaña **Experiments** .

<Image align="center" alt="Tabla de experimentos.png" src="https://files.readme.io/61958568e19f243855237465d132935a339ab18f24b5a8c8318d411239b7fd8b-41021758787089.png" />

Para cada experimento, puedes ver lo siguiente:

* **Nombre del experimento**
* **App** - ordenable
* **País** - ordenable
* **Nombre de la app**
* **Fechas** - El intervalo de fechas del experimento
* [**Estado**](#columna-estado) - Puedes ver cuántos días quedan del experimento o cuándo se ha completado.
* **Elevación**

<div id="status-column" />

#### **Columna Estado**

* **Completado** - El periodo del experimento ha finalizado
* **Activo** - El experimento está actualmente en funcionamiento
* **Pendiente** - Resultados del experimento pendientes (primeras 24 horas)
* **En revisión** - Diseño en revisión (hasta 24 horas para recibir una respuesta)
* **Listo** - El diseño se revisó y se consideró apto
* **No disponible** - El diseño se revisó y no se consideró apto

Pasa el cursor sobre el experimento para acceder al icono de acciones<Image alt="action menu.png" src="https://files.readme.io/0f35ebb6f4527107c1512ef20416108861326423951532c85fb00c7807023eba-41021731867793.png" width="16px" />.

<Image align="center" alt="Menú Experimentos.png" src="https://files.readme.io/5e25e2b4b7f9651ad6a510916b9ee2b2a45d4064a0801a24baa6e3d62bde81a0-41021731868049.png" width="254px" />

Desde aquí puedes:

* Ver detalles del experimento
* Ampliar la duración del experimento
* Detener experimento

</Accordion>

<div id="extend-experiment" />

<Accordion title="Ampliar el experimento">

**Para ampliar un experimento:**

En el experimento, haz clic en el icono de acciones<Image alt="action menu.png" src="https://files.readme.io/0f35ebb6f4527107c1512ef20416108861326423951532c85fb00c7807023eba-41021731867793.png" width="16px" /> (arriba a la derecha) y selecciona **Ampliar la duración del experimento**.

<Image align="center" alt="Ampliar experimento.png" src="https://files.readme.io/191463618d7bcdba2210e71bf38719c8d5af9951a5282a98cc1e3bc87a7e853b-41021731869329.png" width="336px" />

Esto ampliará el experimento 14 días adicionales.

</Accordion>

<div id="stop-experiment" />

<Accordion title="Detener experimento">

**Para detener un experimento:**

En el experimento, haz clic en el icono de acciones ⠇ (arriba a la derecha) y selecciona **Detener experimento**.

<Image align="center" alt="Detener experimento.png" src="https://files.readme.io/2622bca9bafa7894d4ca967f13d6626eb3cd53554720d134d8092ebb0d561740-41021731870609.png" width="331px" />

</Accordion>

<div id="traits-and-limitations-1" />

## Especificaciones y limitaciones

Esta sección describe algunas características clave y limitaciones de Incrementality for UA.

<div id="key-traits-and-limitations" />

<Accordion title="Características clave y limitaciones">

| Caducado | Nota |
| --- | --- |
| Países compatibles | Incrementality for UA actualmente admite experimentos en Estados Unidos, India, México, Brasil, Japón y Alemania. Se añadirán más países a medida que estén disponibles. |
| Geolocalización compatible de las campañas | Incrementality for UA admite campañas dirigidas a un único país completo. No se admiten campañas dirigidas a varios países ni a regiones concretas dentro de un país (por ejemplo, estados o ciudades). |
| Datos históricos de engagement de la aplicación | La aplicación debe tener disponibles al menos 120 días de datos de instalaciones y/o eventos in-app. |
| Instalaciones no orgánicas mínimas mensuales | Cada aplicación medida debe generar al menos 10.000 instalaciones no orgánicas al mes para ejecutar un experimento válido. |

</Accordion>

<div data-zendesk-anchors="overview=informaci%C3%B3n-sobre-incrementalidad-para-ua h_01HBB6EJ8SQ3776WCVQZA4MJ6M=informaci%C3%B3n-sobre-incrementalidad-para-ua get-started=dise%C3%B1o-de-experimentos-e-insights h_01JZQ4N4PEKTP1TZTDQ191ZDM3=dise%C3%B1o-de-experimentos-e-insights h_01JZQ4Q1C035S9EXVJX8YR3PEA=understanding-geo-experimentation-explainer h_01K049CDW93B3C7VZSNFQ1AD0N=use-cases h_01JZQ4Q1C0BZAH7E0J2T1SCPD0=selecting-campaigns h_01JZQ4Q1C0Z3M002TWYKB8SS3M=understanding-experiment-results h_01JZQ4Q1C0NWWVD8ENVJB50RMD=pausing-or-extending-experiments h_01HBB6EJ8S2T9JHKVWH1JK1FPD=comienza h_01HBB6EJ8SVV71R5W9Z96D7WCG=create-the-experiment- h_01K2F27SEQF8N38FMCW8PSFB36=advertencia h_01KVA5SPC58YXP67G86Z2CHGDF=advertencia-1 h_01K2F1FQ0NN5YPWK5026Y7935D=advertencia-2 01JV7F4ECQAY0PJNV2A94E5GA9=analyze-the-results h_01JZJ70C1C0ZRD8WMCKZBHKCEP=accede-al-dashboard-del-experimento a-tour-of-the-dashboard=un-tour-por-el-dashboard h_01JZJ70K0QTGZ2V3T1TJ1VG08H=un-tour-por-el-dashboard manage=gestionar h_01JZ88Y5TQJCYQ2057RASHCP9D=gestionar h_01HBB6EJ8T4RRKJY632180KZWM=Connections geo-design-policy=h_01_geo-design-policy geo-design-rule-types=tipos-de-reglas-de-dise%C3%B1o-de-geolocalizaci%C3%B3n h_01KVA5SPC5PCR7BAK971PGHMCW=tipos-de-reglas-de-dise%C3%B1o-de-geolocalizaci%C3%B3n set-up-a-geo-design-rule=configurar-una-regla-de-dise%C3%B1o-de-geolocalizaci%C3%B3n h_01KVA5SPC5X3VRK60AJ74TJFCS=configurar-una-regla-de-dise%C3%B1o-de-geolocalizaci%C3%B3n delete-a-geo-design-rule=eliminar-una-regla-de-dise%C3%B1o-de-geolocalizaci%C3%B3n h_01KVA5SPC54N4ECEMHJW2PV9K7=eliminar-una-regla-de-dise%C3%B1o-de-geolocalizaci%C3%B3n h_01KVA5SPC5GY7SVPT8BAFF1BPT=advertencia-3 view-geo-design-rules-in-an-experiment=ver-reglas-de-dise%C3%B1o-de-geolocalizaci%C3%B3n-en-un-experimento h_01KVA5SPC5K7M0AEYVGVCAMY4W=ver-reglas-de-dise%C3%B1o-de-geolocalizaci%C3%B3n-en-un-experimento geo-design-policy-traits-and-limitations=especificaciones-y-limitaciones h_01KVA5SPC61N9H7PEKYRX01M9Y=especificaciones-y-limitaciones h_01K2HQ7M74PGY2BC2X1KJ1F0Z4=Experiments status-column=columna-estado h_01K9VPG89HGV9BK8W94WC7WH8Q=columna-estado h_01K2HMD3QVJX9KYPQ7GS91KQ6Y=extend-experiment h_01JZ894VWK49JW8M97GMTC5JPX=stop-experiment traits-and-limitations=especificaciones-y-limitaciones-1 h_01KAZQSWB0H9SM7W9PADRJ9B3N=especificaciones-y-limitaciones-1 h_01KAZQQMBP5AHE8KQ5V71TCVAY=key-traits-and-limitations" />
