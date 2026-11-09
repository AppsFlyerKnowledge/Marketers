---
title: Incrementality para la vista general de remarketing
metadata:
  keywords:
    - Analytics
    - Audiences
    - Advertisers
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
  created_at: '2020-05-29T19:29:03Z'
  edited_at: '2026-08-12T12:26:23Z'
  id: 360009360978
  locale: es
  section: Incrementality for remarketing
  section_id: 6551378485649
  url: https://support.appsflyer.com/hc/es/articles/360009360978
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En resumen:** Entender cómo Incrementality mide el aumento incremental generado por las campañas de retargeting.

<div id="what-is-incrementality" />

## ¿Qué es Incrementality?

Probablemente, la mejor manera de entender el análisis de incrementalidad es a través de un ejemplo:

Supongamos que acabas de realizar una campaña de remarketing. Para simplificar, diremos que fue con una sola ad network. La tasa de conversión de la campaña fue del 5%.

Ahora quieres evaluar el éxito de la campaña y necesitas responder a preguntas importantes (y, por supuesto, las más difíciles):

* ¿El 5% es una buena tasa de conversión para esta campaña?
* ¿Cómo sabemos que la campaña ha generado realmente conversiones adicionales?
* ¿Ha valido la pena el costo de la campaña?

Para responder a estas preguntas con precisión y sin prejuicios, debemos tener en cuenta algo más que las conversiones medidas. Debemos tener en cuenta el número de usuarios que se habrían convertido orgánicamente, aunque nunca hubieran participado en una campaña de remarketing.

Esta diferencia entre el total de conversiones y las que se habrían producido de todos modos se conoce como **aumento incremental** (o a veces simplemente **"incremento")**, y es fundamental para determinar el verdadero valor de una campaña. Puede ser bastante difícil de medir, pero eso es precisamente para lo que está diseñado Incrementality de AppsFlyer.

<div id="incrementality-experiments" />

### Experimentos de incrementalidad

Incrementality supera el desafío de medir el aumento incremental permitiéndote crear experimentos científicamente válidos para comparar el comportamiento de grupos similares. Estos grupos varían únicamente en que algunos grupos (los **"grupos de prueba"**) están expuestos a tu campaña y un grupo (el **"grupo de control")** no.

<Anchor target="_blank" href="/marketers/es/docs/run-an-incrementality-for-remarketing-experiment">Saber más sobre la creación y ejecución de experimentos de incrementalidad</Anchor>

<div id="calculation-methodology" />

## Metodología de cálculo

En las siguientes secciones se explican los cálculos en los que se basan las cifras que aparecen en el dashboard de Incrementality.

<div id="lift" />

<Accordion title="Elevación">

Incrementality de AppsFlyer emplea 2 métodos alternativos para calcular el aumento:

* Intent-to-treat
* Basado en el alcance

Mientras que **la metodología basada en el alcance es preferible** para los propósitos de evaluar el rendimiento de la campaña, su cálculo requiere la medición de puntos de datos que no son proporcionados por todas las ad networks. Para estas redes, se utiliza en su lugar la metodología intent-to-treat.

<div id="note" />

> 📘 **Nota**
>
> Antes del 16 de diciembre de 2021, el aumento se calculaba utilizando únicamente el método intent-to-treat. Sin embargo, los datos de fechas anteriores han sido actualizados para utilizar el aumento basado en el alcance donde sea aplicable. Por lo tanto, puedes revisar experimentos históricos para analizar sus resultados con la nueva metodología.

<div id="itt-based-lift" />

#### Incremento basado en ITT

La metodología experimental de intent-to-treat (ITT) tiene sus fundamentos en la ciencia médica. Usando ITT, los investigadores dividen aleatoriamente una dada población entre un grupo de control que no es tratado y un grupo de prueba que los investigadores intentan tratar. Los investigadores miden la eficacia de un tratamiento dado comparando los resultados de los grupos. El hecho de que un miembro del grupo de prueba haya recibido *realmente* el tratamiento, no se tiene en cuenta.

Del mismo modo, en el remarketing, la métrica del incremento mide la eficacia de la campaña. No importa si un usuario en el grupo de prueba *realmente* participó en una campaña (recibió tratamiento) porque es la intención la que es relevante para calcular la incrementalidad. En otras palabras, los resultados se calculan como si cada miembro del grupo de prueba realmente participara en la campaña.

**¿Cuándo se utiliza?**

Incrementality de AppsFlyer utiliza el cálculo de elevación basado en ITT para las SRN.

Aunque no es el método preferido para medir el aumento en nuestro contexto, ITT sigue siendo un método experimental científicamente sólido, y proporciona resultados válidos cuando el cálculo basado en el alcance no es posible.

**Interpretación de los resultados**

La suposición subyacente de que todos los miembros del grupo de prueba fueron realmente alcanzados por una campaña, a menudo da lugar a bajas tasas de conversión y, como consecuencia, a un bajo incremento.

<div id="reach-based-lift" />

#### Incremento por alcance

Como su nombre indica, el cálculo de aumento basado en el alcance tiene en cuenta si un miembro del grupo de prueba fue *realmente alcanzado* (se le mostró un anuncio de campaña) antes de convertir. Además de requerir datos adicionales, el cálculo de aumento basado en el alcance también es más complejo en el sentido de que requiere ciertos ajustes matemáticos al grupo de control para ser estadísticamente válido. Estos ajustes son acumulativamente conocidos como la creación de un grupo de control "contrafactual".

**¿Cuándo se utiliza?**

Incrementality de AppsFlyer utiliza el cálculo de aumento basado en el alcance para no-SRNs (attribution-link networks).

Si bien es el método preferido para calcular el aumento, el cálculo basado en el alcance requiere que las ad networks informen los siguientes datos a AppsFlyer:

* Datos de impresión
* ID de campaña (del enlace de atribución)

Si no se comunican estos datos, la medición de la incrementalidad no está disponible (y se muestra como **N/A** en el dashboard de Incrementality).

**Interpretación de los resultados**

Dado que el cálculo del incremento basado en el alcance sólo tiene en cuenta a los miembros del grupo de prueba a los que realmente llegó una campaña, las redes que se miden utilizando la incrementalidad basada en el alcance normalmente mostrarán resultados amplificados (el incremento positivo será mucho mayor y el negativo mucho menor).

<div id="best-practices" />

#### Mejores prácticas

Dado que las dos metodologías de cálculo del incremento pueden arrojar resultados muy diferentes, se recomiendan las siguientes buenas prácticas para que la interpretación sea más significativa:

* Cuando crees tus experimentos, selecciona audiencias que se dividan únicamente entre un grupo de control y una o más redes del mismo tipo, ya sea:
  * Redes de enlaces de atribución (no SRN) para el cálculo basado en el alcance; o
  * SRN para el cálculo basado en ITT
* En tus experimentos iniciales, considera la posibilidad de utilizar una audiencia dividida únicamente entre una sola red y un grupo de control. Esto hace menos probable que se realicen comparaciones entre 2 o más redes para las que se utilicen diferentes cálculos de incremento.

</Accordion>

<div id="statistical-significance" />

<Accordion title="Importancia estadística">

Al evaluar la validez de los experimentos de Incrementality, una metodología científica sólida requiere que consideremos la **relevancia estadística** (el nivel de confianza de que el resultado del incremento no se deba a eventos aleatorios o al azar).

En el panel de Incrementality, la relevancia se informa como un porcentaje para cada fuente de medios:

* El porcentaje indica la probabilidad de que los resultados de esa fuente de medios se repitan si el experimento se realizara nuevamente en circunstancias similares.
* Si se determina que la relevancia estadística está por debajo del 60%, el dashboard mostrará **Resultados no confiables** en lugar de un porcentaje.
* La relevancia se ve afectada por el tamaño de la audiencia, la duración del experimento, y el rendimiento de la fuente de medios.

</Accordion>

<div id="scaled-control-group" />

<Accordion title="Grupo de control escalonado">

Para [métricas a nivel de grupo de prueba](/docs/incrementality-for-remarketing-overview#::2c5f08ec) (a diferencia de las [métricas por usuario](/docs/incrementality-for-remarketing-overview#::6143ff4f)), el aumento se calcula en función de un **grupo de control escalado**. En otras palabras, el tamaño del grupo de control se ajusta para coincidir el tamaño del grupo de control para cada fuente de medios.

<div id="example" />

> 📄 **Ejemplo**
>
> Supongamos el siguiente escenario:
>
> * Tamaño del grupo de prueba para la red A = 100 miembros
> * Tamaño del grupo de control = 90 miembros
> * Resultados del experimento
>   * La Red A tuvo 40 conversiones
>   * El grupo de control tuvo 20 conversiones
> * Las conversiones totales se ajustarán en función de un tamaño estimado (escalado) del grupo de control de 100 miembros:
>   * Miembros estimados - Miembros reales = 100 - 90 = 11%
>      Miembros reales      90
>   * Conversiones incrementales reales + 11% = 20 x 1,11 = 22
>
> El aumento se calculará en función de un tamaño de grupo de control escalado de 100 miembros y 22 conversiones incrementales.

</Accordion>

<div id="incrementality-dashboard" />

## Dashboard de Incrementality

<Image align="center" alt="New_Incrementality_Guide_image.jpg" src="https://files.readme.io/a14fa7ae346177dbdd7de5fde4917d7300cbc148097a2239e29460a67eacd9a6-15317247527569.jpg" />

<div id="accessing-the-dashboard" />

<Accordion title="Acceso al dashboard">

La incrementalidad es una función premium. Para comenzar, contacta con tu Customer Success Manager o escribe a [hello@appsflyer.com](mailto:hello@appsflyer.com). Después de suscribirte, podrás acceder al dashboard de Incrementality.

**Para acceder al dashboard de Incrementality:**

1. En AppsFlyer, desde el menú lateral, selecciona **Optimizar** > **Incrementality**.
2. Desde la lista de experimentos, haz clic en la fila del experimento para el cual deseas ver el dashboard.

</Accordion>

<div id="a-tour-of-the-dashboard" />

<Accordion title="Un tour por el dashboard">

<Table>
  <thead>
    <tr>
      <th>

      </th>
      <th>
        Componente
      </th>
      <th>
        Descripción
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        ![A.png](https://files.readme.io/66b5bb0c4ea35f232f65dbc8dcbdfd6a91c12cf94915b19d33dae44834127058-31237653543313.png)
      </td>
      <td>
        Barra de filtros
      </td>
      <td>
        **Mide:** Selecciona la métrica que deseas ver en el dashboard:

        * **Conversiones** – El número de usuarios únicos que realizaron el evento seleccionado
        * **Ingresos** – Ingresos generados por la conversión de usuarios del evento seleccionado
        * **Eventos** – Número de veces que se ha producido el evento seleccionado realizado por los usuarios convertidos.

        Tu selección en el filtro **Medición** determina qué métricas se muestran en todo el dashboard.

        **Evento:** Selecciona el evento in-app para el cual deseas ver datos en el dashboard.

        **Fuente de medios:** Filtrar el dashboard de visualización por una o más fuentes de medios probadas en el experimento.

        **Rango de fechas:** Filtrar el análisis incremental de la audiencia según el rango de datos seleccionado.
      </td>
    </tr>
    <tr>
      <td>
        ![B.png](https://files.readme.io/f63914d3fefb55b627559c6e4c7d7cdef89239c0376a14c25c713a0a76dbad1b-31237653544337.png)
      </td>
      <td>
        <span id="::3b361a96"></span>Resumen del experimento
      </td>
      <td>
        Resume todo el experimento con resultados rápidos y claros.
      </td>
    </tr>
    <tr>
      <td>
        ![C.png](https://files.readme.io/b428e77b299e10fe0701b7850cea1da8942905ad38d7b30c32f99f0240b22a63-5397303804945.png)
      </td>
      <td>
        <span id="::6ba593ae"></span>Módulo de importancia
      </td>
      <td>
        Muestra la [relevancia estadística](/docs/incrementality-for-remarketing-overview#statistical-significance) de los resultados mostrados en el dashboard
      </td>
    </tr>
    <tr>
      <td>
        ![D.png](https://files.readme.io/9d9abd09fc45ec65fc52cbc1c8011117b555629d243444d076a392b4245effdd-5397362181265.png)
      </td>
      <td>
        <span id="::4c3ffd21"></span>Módulo métrico del encabezado
      </td>
      <td>
        La métrica mostrada está controlada por tu selección en el filtro de Medición, como se muestra a continuación.

        | Selección del filtro de medición | Métrica de encabezados mostrada |
        | --- | --- |
        | <span id="conversionsevents"></span>Conversiones/Eventos | Costo por acción incremental (CPiA)<br /><br />* Costo promedio de cada evento incremental, basado en el costo de la campaña |
        | <span id="revenue"></span>Ingresos | Retorno incremental de la inversión publicitaria (iROAS)<br /><br />* Ratio de ingresos incrementales generados por cada dólar gastado en la campaña |

        **Nota:** Cálculo de métricas mostradas en el headline requieren datos de costo. Por lo tanto, estas métricas están disponibles solo para usuarios de <Anchor target="_blank" href="/marketers/es/docs/roi360-cost-aggregation-overview">ROI360</Anchor> . Si los datos de costo y/o ingresos requeridos no están disponibles por esta o cualquier otra razón, la métrica relevante se mostrará como **N/A.**
      </td>
    </tr>
    <tr>
      <td>
        ![E.png](https://files.readme.io/28563cf0057cdd6ccfd8ebb5b727ae80bef81ec66697f8e11eadc698f72e7acd-5397355189777.png)
      </td>
      <td>
        <span id="::c0b74d1b"></span>Tamaño del objetivo y módulo de alcance
      </td>
      <td>
        **Tamaño del objetivo:** El número de distintos usuarios, para cada fuente de medios, que fueron añadidos a la audiencia por primera vez durante el rango de fechas del experimento

        * También representado por el interior del gráfico circular (color más oscuro)

        **Alcance:** El porcentaje del público objetivo que realmente vio un anuncio de la campaña de la fuente de medios correspondiente

        * También representado por el exterior del gráfico circular (color más claro)
      </td>
    </tr>
    <tr>
      <td>
        ![F.png](https://files.readme.io/99f2fb8f45215ddebf9582f215e3647bc35f5a812015733b3f6e3cb8d2784bd7-5397365201809.png)
      </td>
      <td>
        <span id="::2c5f08ec"></span>Módulo de incremento a nivel de grupo de prueba
      </td>
      <td>
        Muestra **métrica incremental total** y el aumento **para el grupo de prueba** (por fuente de medios):

        * El aumento incremental total se calcula utilizando un [grupo de control escalonado](/docs/incrementality-for-remarketing-overview#scaled-control-group).
        * La métrica mostrada está controlada por tu selección en el filtro de Medición, como se muestra a seguir.

        | Selección del filtro de medición | Métrica mostrada |
        | --- | --- |
        | <span id="conversions"></span>Conversiones | Conversiones incrementales totales |
        | <span id="events"></span>Eventos | Eventos incrementales totales |
        | <span id="revenue::3f000a8e"></span>Ingresos | Ingresos incrementales totales |
      </td>
    </tr>
    <tr>
      <td>
        ![G.png](https://files.readme.io/7301cda39a8a6bcd08d199097ff9b11d496c5f01ab34422364a4e467a752338a-5397303963409.png)
      </td>
      <td>
        <span id="::6143ff4f"></span>Módulo de incremento por usuario
      </td>
      <td>
        Muestra métrica incremental y aumento **por usuario** (por fuente de medios):

        * El aumento incremental por usuario se calcula utilizando el número real de usuarios en el grupo de prueba y grupo de control.
        * La métrica mostrada está controlada por tu selección en el filtro de Medición, como se muestra a seguir.

        | Selección del filtro de medición | Métrica mostrada |
        | --- | --- |
        | <span id="conversions::b51393dc"></span>Conversiones | Tasa de conversión incremental |
        | <span id="events::3b4fa416"></span>Eventos | Eventos incrementales por usuario |
        | <span id="revenue::b432caf"></span>Ingresos | Ingresos adicionales por usuario |
      </td>
    </tr>
    <tr>
      <td>
        ![H.png](https://files.readme.io/36085f38ba02d718acc766af3865073bf13960b2a1c755bd48302ab5415ff89a-5397355274513.png)
      </td>
      <td>
        <span id="::a6a95657"></span>Gráfico de tendencias
      </td>
      <td>
        Muestra la métrica/aumento **incremental por usuario** seleccionada durante el rango de datos del experimento:

        * La métrica mostrada está controlada por tu selección en el filtro de Medición y es la misma métrica que la que se muestra en el **módulo de aumento por usuario**.
        * Una línea punteada (en la vista del gráfico) indica datos parciales para la fecha reportada (lo que significa que los eventos futuros aún pueden afectar los datos).
        * Selecciona varias opciones de vista y descarga usando los **Controles de la vista del gráfico de tendencias** (como se describe a continuación).
      </td>
    </tr>
    <tr>
      <td><span id="::64e4f3f6"></span>
        <Image alt="I.jpg" src="https://files.readme.io/19ab5c305d3eb2609031a1a88f6f4069015b6eefe9ef4f1501613f62e5024739-15317326904465.jpg" width="29px" />
      </td>
      <td>
        Controles de la vista del gráfico de tendencias
      </td>
      <td>
        Utiliza los controles de vista para seleccionar opciones para la visualización y descarga del **gráfico de tendencias**:

        * Valores acumulados o diarios (en el día)
        * Formato de gráfico o tabla

        Utiliza el botón **Exportar** para descargar los datos como un reporte en formato CSV.

        * Los datos descargados están controlados por tu selección con los controles de vista: **Acumulativo** o **diario**

        **Descripción de los términos del reporte**

        | Término | Descripción |
        | --- | --- |
        | Medida bruta | La cantidad total de conversiones/eventos/ingresos generados por el grupo de prueba, independientemente de las impresiones (únicamente basado en la red a la que cada usuario fue asignado por la configuración dividida. |
        | Medida alcanzada | La cantidad de conversiones/eventos/ingresos generados por el grupo de prueba, solo por usuarios que tuvieron una impresión de la campaña seleccionada antes de desencadenar el evento subyacente. |
        | Medida no alcanzada | Medida bruta menos medida alcanzada. Esto describe la cantidad total de conversiones/eventos/ingresos generados por usuarios del grupo de prueba que no tuvieron una impresión antes de desencadenar el evento subyacente. |
        | Medida por usuario | Medida alcanzada/bruta del mejor grupo (dependiendo de si la red seleccionada admite alcance) dividido por el tamaño/alcance del grupo de prueba. |
        | Medida bruta del grupo de control | La cantidad total de conversiones/eventos/ingresos generados por el grupo de control. |
        | El grupo de control alcanzó la medida | La cantidad de conversiones/eventos/ingresos generados por el grupo de control, ajustado para la prueba de alcance del grupo (este valor es contrafactual y sirve como un medio para comparar entre iguales). |
        | Grupo de control medida no alcanzada | Medida bruta menos medida contrafactual alcanzada. Esto describe la cantidad total de conversiones/eventos/ingresos generados por usuarios del grupo de control. |
        | Grupo de control por medida de usuario | Medida contrafactual alcanzada/bruta del grupo de control (dependiendo de si la red seleccionada admite alcance) dividido por el tamaño del grupo/alcance contrafactual del grupo de control. |
        | Medida incremental total | Medida alcanzada en prueba menos medida contrafactual alcanzada en control. |
        | Medida incremental por usuario | Medida por usuario menos medida de control por usuario. |
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="raw-data-reports" />

## Reportes de raw data

Utiliza los reportes de raw data de Incrementality para analizar la interacción de los usuarios con las campañas de remarketing:

* **Contenido:** datos a nivel de fila de los usuarios incluidos en los experimentos de incrementalidad.
* **Disponibilidad:**
  * A través de <Anchor target="_blank" href="/marketers/es/docs/data-locker-for-marketers">Data Locker</Anchor>
  * Actualización de datos: diaria 19:00-23:00 UTC

<Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/360012600697">Descargar ejemplos de archivos de raw data de incrementalidad</Anchor>

<div id="available-reports" />

<Accordion title="Reportes disponibles">

<table><thead><tr><th>Categoría</th><th>Nombre del reporte </th><th>Carpeta Data Locker</th></tr></thead><tbody><tr><td>Visto por primera vez</td><td>Primeros usuarios vistos</td><td>incrementality_first_seen_users</td></tr><tr><td rowspan="3">Eventos in-app</td><td>Eventos orgánicos in-app</td><td>incrementality_organic_inapps</td></tr><tr><td>Eventos in-app no orgánicos</td><td>incrementality_inapps</td></tr><tr><td>Reatribuciones de eventos in-app</td><td>incrementality_inapps_reattr</td></tr><tr><td rowspan="3"><p>Sesiones</p></td><td>Sesiones orgánicas</td><td>incrementality_organic_sessions</td></tr><tr><td>Sesiones no orgánicas</td><td>incrementality_sessions</td></tr><tr><td>Sesiones reatribuidas</td><td>incrementality_sessions_reattr</td></tr><tr><td>Desinstalaciones</td><td>Desinstalaciones<br/>(no rellenado actualmente) </td><td>incrementality_uninstalls</td></tr></tbody></table>

</Accordion>

<div id="report-logic" />

<Accordion title="Lógica de reporte">

La lógica básica que subyace a la estructura del reporte es la siguiente:

* **Usuarios participantes en el experimento-reporte de primera vista**
  * En Audiencias, se establecen reglas que caracterizan a los usuarios que se incluirán en el experimento.
  * Cuando se identifica a un usuario determinado que cumple las normas, el suceso se registra en el reporte *first\_seen*.
    * Los usuarios se asignan aleatoriamente a un grupo de prueba o de control indicado por el campo *is\_control\_group*.
    * Los usuarios del grupo de prueba se asignan a una fuente de medios*(pid\_destination*) para el retargeting.
* **Participación del usuario en la aplicación:** La interacción del usuario con la aplicación durante el experimento se registra en reportes específicos para cada contexto:
  * **Tipo de engagement:** Sesión o evento in-app
  * **Estado de atribución** del usuario cuando es visto por primera vez: orgánico, no orgánico, reatribución. Por ejemplo, en el pasado, un usuario instalaba la aplicación y se le atribuía carácter orgánico. Así, durante un experimento, el estado de atribución es orgánico.
* **Desinstalaciones:** usuarios que desinstalan la aplicación durante el experimento. La medida de desinstalación debe estar activa.

</Accordion>

<div id="data-characteristics-and-fields" />

<Accordion title="Características y campos de datos">

La disponibilidad de campo varía según el tipo de reporte, como se indica a continuación:

<div id="fields-unique-to-incrementality-per-report-type" />

#### Campos exclusivos de Incrementality (por tipo de reporte)

| Campo | Descripción | Visto por primera vez | Eventos in-app | Sesiones | Desinstalaciones |
| --- | --- | --- | --- | --- | --- |
| <span id="is_control_group"></span>is\_control\_group | Si es verdadero, el usuario forma parte del grupo de control | Sí | Sí | Sí | Sí |
| <span id="pid_destination"></span>pid\_destination | La fuente multimedia a la que se envía al usuario | Sí | Sí | Sí | Sí |
| <span id="audience_id"></span>audience\_id | Identificador único | Sí | Sí | Sí | Sí |
| <span id="joined_audience_date"></span>joined\_audience\_date | Fecha en que el usuario se unió por primera vez a la audiencia | Sí | Sí | Sí | Sí |
| <span id="audience_name"></span>Nombre de audiencia | Nombre de la audiencia (no único) | Sí | Sí | Sí | Sí |
| <span id="tm"></span>TM | Hora del día |  | Sí | Sí | Sí |
| <span id="timestamp"></span>timestamp | Hora del evento AAAA-MM-DD HH: MM |  | Sí | Sí |  |
| <span id="app_ids"></span>app\_ids | ID de aplicaciones asociadas a las reglas de audiencia | Sí |  |  |  |

<div id="other-incrementality-report-fields-per-report-type" />

#### Otros campos del reporte de incrementalidad (por tipo de reporte)

<table><thead><tr><th>Campo</th><th>Nombre para mostrar\*</th><th>Visto por primera vez</th><th>Eventos in-app</th><th>Sesiones</th><th>Desinstalaciones</th></tr></thead><tbody><tr><td><span id="advertising_id"></span>advertising_id</td><td>ID de publicidad (GAID)</td><td>Sí</td><td>Sí</td><td>Sí</td><td>Sí</td></tr><tr><td><span id="android_id"></span>android_id</td><td>ID de Android</td><td> </td><td>Sí</td><td>Sí</td><td> </td></tr><tr><td><span id="app_id"></span>id_aplicación</td><td>ID de aplicación</td><td>Sí</td><td>Sí</td><td>Sí</td><td>Sí</td></tr><tr><td><span id="app_name"></span>nombre_aplicación</td><td>Nombre de la aplicación</td><td> </td><td>Sí</td><td>Sí</td><td> </td></tr><tr><td><span id="app_version"></span>version_app</td><td>Versión de la aplicación</td><td> </td><td>Sí</td><td>Sí</td><td> </td></tr><tr><td><span id="appsflyer_id"></span>appsflyer_id</td><td>ID de Appsflyer</td><td> </td><td>Sí</td><td>Sí</td><td>Sí</td></tr><tr><td><span id="revenue_alt"></span>revenue_alt</td><td>Moneda específica de la aplicación</td><td> </td><td>Sí</td><td> </td><td> </td></tr><tr><td><span id="bundle_id"></span>id_paquete</td><td>ID del paquete</td><td> </td><td>Sí</td><td>Sí</td><td> </td></tr><tr><td><span id="country"></span>País</td><td>Código del país</td><td> </td><td>Sí</td><td>Sí</td><td>Sí</td></tr><tr><td><span id="currency"></span>moneda</td><td>Código de la moneda</td><td> </td><td>Sí</td><td>Sí</td><td>Sí</td></tr><tr><td><span id="customer_user_id"></span>id_usuario_cliente</td><td>ID de usuario del cliente</td><td> </td><td>Sí</td><td>Sí</td><td> </td></tr><tr><td><span id="brand"></span>marca</td><td>Marca del dispositivo</td><td> </td><td>Sí</td><td>Sí</td><td> </td></tr><tr><td><span id="device_category"></span>categoría_del_dispositivo</td><td>Categoría de dispositivo</td><td> </td><td>Sí</td><td>Sí</td><td> </td></tr><tr><td><span id="model"></span>modelo</td><td>Modelo del dispositivo</td><td> </td><td>Sí</td><td>Sí</td><td> </td></tr><tr><td><span id="device_model"></span>device_model</td><td>Modelo del dispositivo</td><td> </td><td>Sí</td><td>Sí</td><td> </td></tr><tr><td><span id="device_type"></span>tipo_de_dispositivo</td><td>Tipo de dispositivo</td><td> </td><td>Sí</td><td>Sí</td><td> </td></tr><tr><td><span id="event_name"></span>nombre_del_evento</td><td>Nombre del evento</td><td> </td><td>Sí</td><td>Sí</td><td>Sí</td></tr><tr><td><span id="event_revenue"></span>ingresos_evento</td><td>Ingresos del evento</td><td> </td><td>Sí</td><td> </td><td> </td></tr><tr><td><span id="event_revenue_currency"></span>moneda_ingresos_evento</td><td>Moneda de ingresos del evento</td><td> </td><td>Sí</td><td> </td><td> </td></tr><tr><td><span id="event_revenue_u_s_d"></span>event_revenue_u_s_d</td><td>Ingresos por eventos en USD</td><td> </td><td>Sí</td><td> </td><td> </td></tr><tr><td><span id="event_time"></span>event_time</td><td>Hora del evento</td><td> </td><td>Sí</td><td>Sí</td><td>Sí</td></tr><tr><td><span id="event_value"></span>event_value</td><td>Valor del evento</td><td> </td><td>Sí</td><td>Sí</td><td> </td></tr><tr><td><span id="idfa"></span>idfa</td><td>Identificador de anunciante (IDFA)</td><td>Sí</td><td>Sí</td><td>Sí</td><td>Sí</td></tr><tr><td><span id="idfv"></span>idfv</td><td>IDFV</td><td> </td><td>Sí</td><td>Sí</td><td> </td></tr><tr><td><span id="imei"></span>imei</td><td>IMEI</td><td> </td><td>Sí</td><td>Sí</td><td> </td></tr><tr><td><span id="is_purchase_validated"></span>is_purchase_validated</td><td>¿El recibo está validado?</td><td> </td><td>Sí</td><td> </td><td> </td></tr><tr><td><span id="os_version"></span>versión_sistema_operativo</td><td>Versión de SO</td><td> </td><td>Sí</td><td>Sí</td><td> </td></tr><tr><td><span id="platform"></span>Identificador de origen</td><td>Plataforma</td><td> </td><td>Sí</td><td>Sí</td><td>Sí</td></tr><tr><td><span id="sdk_version"></span>version_sdk</td><td>Versión del SDK</td><td> </td><td>Sí</td><td>Sí</td><td> </td></tr><tr><td colspan="6"><span id="-according-to-raw-data-specification"></span>\* <a href="./raw-data-field-dictionary#data-fields-dictionary" target="_blank">Según especificación de raw data</a> </td></tr></tbody></table>

</Accordion>

<div id="incrementality-specifications-and-limitations" />

## Especificaciones y limitaciones de Incrementality.

| Caducado | Observaciones |
| --- | --- |
| Acceso de usuario a la cuenta | Según los permisos de la cuenta. |
| Acceso a la ad network | No disponible |
| Acceso a la agencia | No disponible. No disponible Incrementality sólo está disponible para las cuentas de anunciantes. |
| Transparencia de agencia | Puedes medir campañas realizadas por agencias que tengan activada la transparencia de agencia. |
| Truemoney | USD (Dólar estadounidense) |
| Actualización de los datos | Dashboard: diariamente a las 18:00 UTC para el día anterior<br /><br />Reportes de raw data en Data Locker: diariamente a las 19:00-23:00 para el día anterior |
| Datos históricos | N/A |
| Datos no orgánicos | Sí |
| Datos orgánicos | Sí |
| Eventos S2S | Para ser medido en Incrementality, <Anchor target="_blank" href="/marketers/es/docs/server-to-server-events-api-for-mobile-s2s-mobile#api-de-eventos-de-servidor-a-servidor-para-móviles">S2S eventos</Anchor> debe incluir el ID de publicidad en su payload (IDFA para iOS, GAID para Android). |
| Zona horaria | UTC |

<div id="see-also" />

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/audiences-guide">Guía de Audiences</Anchor>
> * <Anchor target="_blank" href="https://www.appsflyer.com/blog/tips-strategy/incrementality-testing-for-marketers/">Pruebas de incrementalidad para marketers</Anchor>
> * <Anchor target="_blank" href="https://www.appsflyer.com/blog/topic/incrementality/">Blog sobre Incrementality</Anchor>

<div data-zendesk-anchors="what-is-incrementality=qu%C3%A9-es-incrementality h_01HB86QVQ0TM91XB8VSZYD42ZA=qu%C3%A9-es-incrementality incrementality-experiments=experimentos-de-incrementalidad h_01HB86QVQ0HR436K24V3SQXVXT=experimentos-de-incrementalidad calculation-methodology=metodolog%C3%ADa-de-c%C3%A1lculo h_01HB86QVQ0FYTCEVATBEC91ZC1=metodolog%C3%ADa-de-c%C3%A1lculo h_01HB86QVQ0SMJFEPJ8048NBQTN=lift h_01HB86QVQ1MREDW50YTKSY2KZJ=nota ittbased-lift=incremento-basado-en-itt h_01HB86QVQ1NGWZM604A45K03TA=incremento-basado-en-itt reachbased-lift=incremento-por-alcance h_01HB86QVQ1N67SFWKRG1BKZE5A=incremento-por-alcance best-practices=mejores-pr%C3%A1cticas h_01HB86QVQ1RDMFT5FH53BYDNSV=mejores-pr%C3%A1cticas h_01HB86QVQ1K2SPBXTG67B5PV33=statistical-significance h_01HB86QVQ1CAZ0ZDJDKPC1B36S=scaled-control-group h_01HB86QVQ16EZVAATG4DPTDVTQ=ejemplo incrementality-dashboard=dashboard-de-incrementality h_01HB86QVQ10C1YHC8HZ9Z8T089=dashboard-de-incrementality h_01HB86QVQ1ECVT0BT4GYC81DH4=accessing-the-dashboard h_01HB86QVQ1JN8SPHXJGHT4NFSB=a-tour-of-the-dashboard raw-data-reports=reportes-de-raw-data h_01HB86QVQ27FXXBRSH2V8ZK78X=reportes-de-raw-data h_01HB86QVQ24932F7CHY666730J=available-reports h_01HB86QVQ2YXRVFKEE20E787BK=report-logic h_01HB86QVQ2VK6TX3CSA4S6QSKZ=data-characteristics-and-fields fields-unique-to-incrementality-per-report-type=campos-exclusivos-de-incrementality-por-tipo-de-reporte h_01HB86QVQ2CAN02B8GWEZTTTVW=campos-exclusivos-de-incrementality-por-tipo-de-reporte other-incrementality-report-fields-per-report-type=otros-campos-del-reporte-de-incrementalidad-por-tipo-de-reporte h_01HB86QVQ221QK6WYRZQ3MJDSY=otros-campos-del-reporte-de-incrementalidad-por-tipo-de-reporte incrementality-specifications-and-limitations=especificaciones-y-limitaciones-de-incrementality h_01HB86QVQ2W6X5Z485WM371GGE=especificaciones-y-limitaciones-de-incrementality h_01HE7RBMSE1RHVSJC7B7FZG8SJ=consulta-tambi%C3%A9n" />
