---
title: '[Beta] Fraud protection studio'
metadata:
  keywords:
    - Marketers
    - Beta feature
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2024-12-08T06:38:30Z'
  edited_at: '2026-08-22T00:07:22Z'
  id: 30754984040977
  locale: es
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/es/articles/30754984040977
---
<span class="af-tag af-tag--beta-feature">Beta feature</span>

> **En resumen:** Fraud protection studio (FPS) proporciona un mayor control sobre cómo se aplica la detección del fraude que los métodos habituales. Con FPS, puede elegir si los datos de detección de fraude se bloquean y se notifican como fraude o se etiquetan, lo que permite una gestión del fraude a medida.

<div id="about-fraud-protection-studio" />

## Sobre fraud protection studio

Fraud protection studio introduce un estado de detección tagged.

Este estado permite a los anunciantes detectar fraudes sin aplicar acciones de forma automática, lo que te proporciona:

* Evaluación: Evalúa el impacto de las actualizaciones de detección antes de que se apliquen.
* Control: Adapta la detección del fraude a tu modelo de negocio y tus necesidades.
* Transparencia: Los datos taggeds proporcionan insights sobre niveles adicionales de protección contra el fraude.

<div id="important" />

> 🚧 **¡Importante!**
>
> Solo los <Anchor target="_blank" href="/marketers/es/docs/user-management#gestionar-roles">roles Admin, Marketing Lead, Team Manager y Security</Anchor> pueden acceder al Fraud Protection Studio.

<div id="how-the-fraud-protection-studio-works" />

## Cómo funciona fraud protection studio

<div id="key-concepts" />

<Accordion title="Conceptos clave">

<div id="fps-modes" />

#### Modos de FPS

FPS tiene dos modos, **implemented** y **tagged**. Los anunciantes pueden cambiar entre estos modos en función de sus objetivos, asegurando que la detección se ajuste a las necesidades específicas.

**Mecanismo de detección actual:** Las instalaciones se consideran:

* Atribuciones **válidas**
* **Detectadas**
  * **Bloqueadas** en tiempo real
  * **Reportadas** como fraude después de la atribución

[<Image alt="Descripción de la imagen" src="https://files.readme.io/86996ca9cf4fb83b5cfa24473a302d4e978732495348e3e7432ca2117d1f03c9-30885578633745.png" width="75%" />](https://files.readme.io/86996ca9cf4fb83b5cfa24473a302d4e978732495348e3e7432ca2117d1f03c9-30885578633745.png)   
**Mecanismo con FPS:** Las instalaciones se consideran:

* Atribuciones **válidas**
* **Detectadas** y
  * **Tagged** pero siguen siendo **válidas** para la atribución
  * **Implemented**
    * **Bloqueadas** en tiempo real
    * **Reportadas** como fraude después de la atribución

[<Image alt="Descripción de la imagen" src="https://files.readme.io/465289666e54257f02cfe0a3b34a765e7109426c1f6438f455613cc53351e4f4-31990048826513.png" width="75%" />](https://files.readme.io/465289666e54257f02cfe0a3b34a765e7109426c1f6438f455613cc53351e4f4-31990048826513.png)

<div id="note" />

> 📘 **Nota**
>
> En el modo tagged, todas las detecciones de fraude que sean tagged pero que sigan siendo válidas se consideran válidas según la configuración del cliente y, por lo tanto, no se acreditarán al plan de consumo.

<div id="where-is-tagged-detection-reflected" />

#### ¿Dónde se refleja la detección tagged?

Las detecciones tagged no se reflejan en los reportes de fraude. Las detecciones tagged están disponibles en los reportes de atribución habituales y en el dashboard de Protect360 de la siguiente manera:

**Reportes**:

* Instalaciones tagged en tiempo real
* Instalaciones tagged después de la atribución
* Eventos in-app tagged en tiempo real
* Eventos in-app tagged posteriores a la atribución

Dashboard de Protect360

[<Image alt="example10.png" src="https://files.readme.io/cf4c836ee78519bd0723bcc1fafb202110fa014be1582853646261d89eb37104-48783289649937.png" width="50%" />](https://files.readme.io/cf4c836ee78519bd0723bcc1fafb202110fa014be1582853646261d89eb37104-48783289649937.png)

* Recuento total de tagged en los componentes superiores de la página (1)
* Tendencia a lo largo del tiempo del "Estado de detección" (2)
* Fraude identificado por "Tipo de etiqueta", "Motivo de la etiqueta", "Submotivo de la etiqueta" (3)

</Accordion>

<div id="how-to-use-fraud-protection-studio" />

## ¿Cómo utilizar fraud protection studio?

<div id="general" />

<Accordion title="General">

FPS es una página de configuración que te permite especificar cuándo deseas que las detecciones sean [implemented o tagged](/docs/beta-fraud-protection-studio#modos-de-fps). La plataforma ayuda a definir los requisitos de tagged al proporcionar:

* Datos del estado de detección.
* Opción para cambiar entre los modos implemented y tagged.

Para empezar:

1. Inicia sesión en AppsFlyer.
2. En el menú de la izquierda, ve a **Configuración > Protect360 > Fraud Protection Studio**.
3. Usa el menú desplegable de aplicaciones en la parte superior de la página para seleccionar la aplicación que deseas configurar.
4. Selecciona la tarjeta en el menú de la izquierda. Las opciones actuales son:
   * [Inundación de clics](/docs/beta-fraud-protection-studio#click-flood-detection)
   * [Nuevos lanzamientos](/docs/beta-fraud-protection-studio#new-releases)

</Accordion>

<div id="click-flood-detection" />

<Accordion title="Detección de inundaciones de clic">

FPS hace que la gestión de la detección de inundaciones de clics sea sencilla y personalizable. Permite etiquetar las detecciones de inundaciones de clics a nivel de aplicación (todos los socios) y mostrar los datos de detección de inundaciones de clics taggeds en reportes específicos.

En la página de tarjetas de inundación de clics, puedes [ver y ajustar el estado de detección](/docs/beta-fraud-protection-studio#cómo-acceder-a-inundación-de-clics) entre implemented y tagged, y ver los datos [actuales del estado de detección](/docs/beta-fraud-protection-studio#analyze-click-flood-by-media-source).

Descarga la muestra de datos del reporte de inundación de clics

<div id="important-2" />

<div id="important-1" />

> 🚧 **¡Importante!**
>
> * Cuando se selecciona la detección tagged, se incluyen en los reportes de raw data, es decir, no en los reportes de fraude.
> * El tagged de la inundación de clics se realiza a nivel de aplicación y evitará el bloqueo o la aplicación posterior a la atribución. Por lo tanto, al etiquetarlo, se expone a abusos en tus instalaciones no orgánicas y orgánicas.

<div id="how-to-access-click-flood" />

#### Cómo acceder a inundación de clics

1. Inicia sesión en AppsFlyer.
2. En el menú de la izquierda, ve a **Configuración > Protect360 > Fraud Protection Studio**.
3. Usa el menú desplegable de aplicaciones en la parte superior de la página para seleccionar la aplicación que deseas configurar.
4. En el menú de la izquierda, selecciona la tarjeta **Inundación de Clics**

<div id="click-flood-page" />

### Página de inundación de clics

La página de inundación de clics se divide en tres secciones.

[Estado de detección](/docs/beta-fraud-protection-studio#estado-de-detección)

[Estado de detección actual](/docs/beta-fraud-protection-studio#estado-de-detección-actual)

<div id="detection-status" />

#### Estado de detección

* [Estado de detección](/docs/beta-fraud-protection-studio#cómo-acceder-a-inundación-de-clics): te permite elegir el modo de [detección](/docs/beta-fraud-protection-studio#modos-de-fps). Puedes elegir entre **implemented** y **tagged**
* [Estado de detección actual](/docs/beta-fraud-protection-studio#estado-de-detección-actual): muestra cómo la activación de inundación de clics habría afectado a tus instalaciones y eventos relativos en función de los últimos 7 días anteriores a la semana pasada. Esta sección se divide a su vez en:
  * Widget de detección de corriente
  * Widget de desglose de detección de inundación de clics
  * Inundación de clic por widget de fuente de medios

<div id="how-to-adjust-the-detection-status" />

#### **Cómo ajustar el estado de detección**

El estado de detección te permite elegir el modo de [detección](/docs/beta-fraud-protection-studio#modos-de-fps). Puedes elegir entre **implemented** y **tagged**.

1. En la ventana Inundación de Clics, selecciona el [modo de detección](/docs/beta-fraud-protection-studio#modos-de-fps).
2. Haz clic en el botón **Guardar** en la parte inferior de la página.

   [<Image alt="Imagen ampliable" src="https://files.readme.io/c472a15b2775d97c097196d2ce97d59f997219beb44c662a7c7a0e1c17682fb6-31776609579025.png" width="1906px" />](https://files.readme.io/c472a15b2775d97c097196d2ce97d59f997219beb44c662a7c7a0e1c17682fb6-31776609579025.png)

<div id="current-detection-status" />

#### **Estado de detección actual**

La sección del estado de detección actual muestra una estimación basada en los últimos 7 días anteriores a la semana pasada.

La sección de estado de detección actual muestra lo siguiente:

* Widget de detección de corriente
* Widget de desglose de detección de inundación de clics
* Inundación de clic por widget de fuente de medios

**Widget de detección de corriente**

* **Instalaciones totales**: la cantidad total de instalaciones de la aplicación
* **Detección de inundación de clic**: el total de inundaciones de clics detectadas
* **Detección total** (sin inundación de clics): cantidad total de detecciones de fraude sin incluir la inundación de clics
* **Detección total** (con inundación de clics): el importe total del fraude, incluido la inundación de clics. Calculado por: (Detección de inundación de clic + Detección total (sin inundación de clic) )

**Desglose de la detección de inundación de clics**

Aquí se muestra el desglose de la detección de inundación de clic por instalaciones orgánicas y no orgánicas.

**Inundación de clic por widget de fuente de medios**

Muestra las instalaciones detectadas de inundación de clics desglosadas por fuente de medios.

Nota: para obtener un reporte más detallado, haz en el botón **Exportar** para descargar las métricas de detección como un archivo CSV para su análisis sin conexión.

</Accordion>

<div id="new-releases" />

<Accordion title="Nuevos lanzamientos">

Con las nuevas versiones, puedes evaluar el impacto de las nuevas actualizaciones de detección de fraude antes de la implementación. De forma predeterminada, cada nuevo paquete de detección de fraude se inicia en modo tagged, lo que te da tiempo y control para evaluar su impacto.

Descarga la muestra de datos del reporte de nuevo lanzamiento

<div id="note-1" />

> 📘 **Nota**
>
> Un paquete de detección consiste en una o varias actualizaciones de detección que se agrupan y lanzan juntas.

<div id="how-this-works" />

#### ¿Cómo funciona?

* Las actualizaciones de detección de fraudes se agrupan en paquetes.
* Los paquetes de detección de fraude comienzan en [modo tagged](/docs/beta-fraud-protection-studio#modos-de-fps).
* Los paquetes nuevos se pueden configurar en modo tagged durante un máximo de 14 días.
* El paquete activo actual se puede evaluar e implementar.
* Se te notificará la publicación de nuevos paquetes a través de la campana de notificación.

<div id="how-to-access-new-releases" />

#### Cómo acceder a los nuevos lanzamientos

1. Inicia sesión en AppsFlyer.
2. En el menú de la izquierda, ve a **Configuración > Protect360 > Fraud Protection Studio**.
3. Usa el menú desplegable de aplicaciones en la parte superior de la página para seleccionar la aplicación que deseas configurar.
4. En el menú de la izquierda, selecciona **Nuevo Lanzamiento**.

<div id="new-releases-page" />

### Página de nuevos lanzamientos

La página de nuevos lanzamientos se divide en dos secciones.

* [Lanzamientos futuros](/docs/beta-fraud-protection-studio#cómo-acceder-a-los-nuevos-lanzamientos): te permite evaluar el impacto de los nuevos paquetes de detección de fraude marcando las detecciones como tagged durante un máximo de 14 días antes de que entren en vigor.
* [Nuevas versiones](/docs/beta-fraud-protection-studio#cómo-evaluar-e-implementar-los-paquetes-activos-actuales): te permite evaluar el paquete activo actual supervisando su rendimiento de detección e implementándolo ahora.

<div id="how-to-set-the-tagged-mode-time-period-for-future-packages" />

#### Cómo configurar el período de tiempo del modo tagged para paquetes futuros

Las versiones futuras te permiten establecer el número de días que deseas que los paquetes de detección futuros se marquen como [tagged](/docs/beta-fraud-protection-studio#modos-de-fps) antes de que entren en vigor. Para configurarlo:

1. En la ventana Nuevo lanzamiento, en el cuadro desplegable, selecciona el número de días que quieres marcar los paquetes nuevos como tagged antes de que se implementen (predeterminado: 14 días, ajustable hasta 14 días)
2. Haz clic en **Guardar**.

<Image alt="futrele.png" src="https://files.readme.io/eb832fdacd720f273a5ac26bc8e08fe1d215a99e477ff3bcfe3b91d46c41234a-31500353666321.png" width="2142px" />

<div id="note-2" />

> 📘 **Nota**
>
> * Esto solo afecta a los paquetes futuros. Los paquetes de detección que están actualmente en vigor no se retrasarán ni cambiarán.
> * Seleccionar 0 días en el cuadro desplegable equivale a seleccionar [Implementar ahora](/docs/beta-fraud-protection-studio#para-implementar-el-paquete-actual-si-está-en-estado-tagged) y anula la configuración de los [lanzamientos futuros](/docs/beta-fraud-protection-studio#cómo-acceder-a-los-nuevos-lanzamientos) de este paquete.

<div id="how-to-evaluate-and-implement-current-active-packages" />

#### Cómo evaluar e implementar los paquetes activos actuales

La sección Nuevo lanzamiento actual te permite ver:

* El último paquete publicado
* Fecha de lanzamiento
* Estado: cuándo entrará en vigor este paquete (si este paquete está en modo tagged).
* Métricas sobre cómo afectará este paquete de detección a tus datos
* Exportar reportes detallados
* Omite la configuración de lanzamientos futuros e implementa este paquete de detección ahora

<div id="to-implement-the-current-package-if-in-tagged-status" />

#### Para implementar el paquete actual si está en estado tagged.

1. Abre la sección **nuevo lanzamiento** en la pestaña FPS.
2. Supervisa el rendimiento de la detección mediante la tabla y los reportes exportables.
3. Cuando esté listo, haz clic en **Implementar ahora** para aplicar los cambios.  
   [![](https://files.readme.io/4c11614b4f74ffa435e75cb7e79ef4f61ac750f5bc49331387b45a0ceb83e0da-31776606696081.png)](https://files.readme.io/4c11614b4f74ffa435e75cb7e79ef4f61ac750f5bc49331387b45a0ceb83e0da-31776606696081.png)

<div id="note-3" />

> 📘 **Nota**
>
> Esto anula la configuración de [lanzamiento futuro](/docs/beta-fraud-protection-studio#cómo-acceder-a-los-nuevos-lanzamientos) de este paquete.

</Accordion>

<div id="app-detection-evaluation" />

<Accordion title="Evaluación de detección de la app">

La tarjeta App Detection Evaluation te permite cambiar el estado de una detección según los objetivos de tu negocio. Las decisiones que se toman aquí se aplican a nivel de la app y afectan a todos los partners del anunciante.

Etiquetar una detección en la tarjeta App Detection Evaluation afecta a toda la lógica de Protect360. Sin embargo, las detecciones activadas por las reglas de validación que hayas definido no se ven afectadas. Estas detecciones permanecen en estado implemented a menos que desactives manualmente la regla de validación correspondiente.

En la página App Detection Evaluation puedes [ver y ajustar el estado de detección](/docs/beta-fraud-protection-studio#cómo-acceder-a-inundación-de-clics) entre implemented y tagged, además de consultar los datos del [estado de detección actual](/docs/beta-fraud-protection-studio#analyze-click-flood-by-media-source).

> 🚧 **¡Importante!**
>
> * Cuando se selecciona la detección etiquetada, los datos se incluyen en los reportes de raw data, es decir, no en los reportes de fraude.
> * La configuración de tagged de App Detection Evaluation se aplica a nivel de la app e impide el bloqueo o la implementación posterior a la atribución de las lógicas de Protect360. Por lo tanto, al etiquetarla, tus instalaciones orgánicas y no orgánicas quedan expuestas a actividades fraudulentas.
> * Cualquier regla de validación definida y activada permanecerá siempre en modo implemented. Para pausar la implementación de una regla de validación, ve a la página de reglas de validación y desactívala allí.

<div id="how-to-access-app-detection-evaluation" />

#### **Cómo acceder a App Detection Evaluation**

1. Inicia sesión en AppsFlyer.
2. En el menú de la izquierda, ve a **Settings > Protect360 >Fraud Protection Studio**.
3. Usa el menú desplegable de aplicaciones en la parte superior de la página para seleccionar la aplicación que deseas configurar.
4. En el menú de la izquierda, selecciona la tarjeta **App Detection Evaluation**.

<div id="app-detection-evaluation-page" />

#### **Página App Detection Evaluation**

La página App Detection Evaluation se divide en dos secciones.

* [Estado de detección](/docs/beta-fraud-protection-studio#cómo-acceder-a-inundación-de-clics): permite elegir el  [modo de detección](/docs/beta-fraud-protection-studio#modos-de-fps). doPuedes elegir entre implemented y tagged.
* [Estado de detección actual](/docs/beta-fraud-protection-studio#estado-de-detección-actual): muestra la detección actual que afecta a tus instalaciones y a los eventos relacionados según los últimos 7 días anteriores a la semana pasada. Esta sección se divide además en:
  * **Lógicas de Protect360**  
    Modo de detección implemented:
    * **Tasa de implementación**: representa (*la cantidad de lógica implementada por las lógicas de Protect360*) dividida entre (*el total de atribuciones de la app*).
  * **Nivel de aplicación**  
    Modo de detección tagged:
    * **Tasa de tagged**: representa (*la cantidad de lógica etiquetada mediante App Detection Evaluation*) dividida entre (*el total de atribuciones de la app*).
  * **Total de instalaciones**
  * **Total de detecciones**
  * **Detección implementada**: te ayuda antes de decidir cambiar el [estado de detección](/docs/beta-fraud-protection-studio#cómo-acceder-a-inundación-de-clics) de implemented a tagged.
    * Lógicas de Protect360: esto muestra qué parte de la detección se debe a las lógicas de Protect360. Al cambiar a etiquetado, esta es la cantidad prevista de detección que se convertirá en detección etiquetada
    * Reglas de validación: esto muestra qué parte de la detección se basa en las reglas de validación que has definido y activado. Si cambias el modo de detección a etiquetado, la detección basada en reglas de validación permanecerá en el modo implementado.
  * **Detecciones etiquetadas**: te ayudan antes de decidir cambiar el [estado de detección](/docs/beta-fraud-protection-studio#cómo-acceder-a-inundación-de-clics) de tagged a implemented. Verás todos los motivos de tagged para conocer el resultado esperado antes de cambiar el estado de detección de tagged a implemented.
    * * Nivel de la app: este KPI te permite entender qué parte del tagged se debe a la tarjeta App Detection Evaluation. El valor mostrado en este KPI representa el aumento esperado si implementas el estado de detección.
    * Otro etiquetado: puedes etiquetar la detección en varias capacidades (tarjetas) en el estudio de protección contra el fraude.

<div id="how-to-adjust-the-detection-status-1" />

#### **Cómo ajustar el estado de detección**

El estado de detección te permite elegir el modo de [detección](/docs/beta-fraud-protection-studio#modos-de-fps). Puedes elegir entre implemented y tagged (el valor predeterminado es implemented).

1. En la página App Detection Evaluation, selecciona el [modo de detección](/docs/beta-fraud-protection-studio#modos-de-fps).
2. Haz clic en el botón “Guardar” situado en la parte inferior de la página.

</Accordion>

<div id="reengagement-hijacking-detection" />

<Accordion title="Detección de secuestro de re-engagement.">

La detección de secuestro de re-engagement de Protect360 amplía la cobertura estándar de detección de fraude específicamente para las actividades de re-engagement. Esta detección mejora tu control sobre la gestión del fraude.

De forma predeterminada, esta detección se publica en [modo tagged](/docs/beta-fraud-protection-studio#modos-de-fps), lo que te permite evaluar su eficacia y su posible impacto antes de implementarla.

<div id="how-this-works-1" />

#### ¿Cómo funciona?

* La detección de secuestro de re-engagement está configurada en modo tagged de forma predeterminada. Puedes evaluar su rendimiento de detección sin afectar a tus datos de atribución en producción.
* Cuando se implementa, las detecciones se producen después de la atribución, lo que significa que los re-engagements fraudulentos se identifican y se eliminan de los registros de atribución.
* Cuando se implementa, todos los eventos posteriores in-app a la eliminación de una detección se volverán a atribuir al proveedor original de adquisición de usuarios (UA) o se marcarán como orgánicos si no existe un proveedor de UA válido.

<div id="how-to-access" />

#### Cómo acceder

1. Inicia sesión en **AppsFlyer**.
2. En el menú de la izquierda, ve a **Configuración > Protect360 > Fraud Protection Studio**.
3. Selecciona la app que deseas configurar mediante el menú desplegable situado en la parte superior de la página.
4. En el menú de la izquierda, selecciona la tarjeta **Secuestro de re-engagement**.

<div id="re-engagement-hijacking-page" />

#### Página de secuestro de re-engagement

La página sobre el secuestro de re-engagement se divide en dos secciones.

* [Estado de detección](/docs/beta-fraud-protection-studio#cómo-acceder-a-inundación-de-clics): permite elegir el modo de [detección](/docs/beta-fraud-protection-studio#modos-de-fps). Puedes elegir entre implementeds y taggeds
* [Estado de detección actual](/docs/beta-fraud-protection-studio#estado-de-detección-actual): muestra cómo habría afectado la activación de secuestro de re-engagement a tus instalaciones y eventos relacionados durante los últimos 14 días (sin incluir el día actual).  
  **Nota:** Dado que la detección de secuestro por re-enganche funciona después de la atribución, los datos de los últimos 7 días pueden ser parciales y seguir actualizándose retroactivamente.  

  Esta sección se divide a su vez en:
  * Widget de detección de secuestro de re-engagement
    * Detecciones: número de detecciones realizadas únicamente por la lógica de secuestro de re-engagement.
    * Tasa de detección: porcentaje de detecciones de secuestro de re-engagement sobre el total de detecciones de re-engagement.
  * Widget de detecciones totales de re-engagement: cantidad total de detecciones de re-engagement procedentes de todas las lógicas.
  * Widget de volumen de atribuciones de re-engagement
    * Atribuciones: la cantidad de atribución de re-engagement en el periodo
    * Calificación del total de atribuciones: la parte de las atribuciones de re-engagement de todas las atribuciones de la aplicación
  * Detección de re-engagement por fuente de medios: número de detecciones de secuestro de re-engagement para las principales fuentes de medios detectadas.

<Image alt="" src="https://files.readme.io/bab73f39f3792401dd8795a78c64d88c26d075cdb7d693a5871bba668495f8d1-35682380370321.png" width="624px" />

</Accordion>

<div id="inapp-based-detection" />

<Accordion title="Detección basada en in-app">

La detección basada en eventos in-app marca de forma determinista las instalaciones como fraude después de la atribución mediante el análisis de anomalías de comportamiento en los eventos in-app. Identifica esquemas de fraude sofisticados, como bots que imitan un engagement real, pero muestran flujos de eventos y patrones temporales inusuales después de la instalación.

<div id="how-to-access-1" />

#### Cómo acceder

1. Inicia sesión en AppsFlyer.
2. En el menú de la izquierda, ve a **Configuración > Protect360 > Fraud Protection Studio**.
3. Usa el menú desplegable de aplicaciones en la parte superior de la página para seleccionar la aplicación que deseas configurar.
4. En el menú de la izquierda, selecciona la tarjeta **detección integrada in-app**.

<div id="the-in-app-based-detection-page" />

#### La página de detección integrada in-app

La página de detección integrada in-app se divide en dos secciones.

* [Estado de detección](/docs/beta-fraud-protection-studio#cómo-acceder-a-inundación-de-clics): permite elegir el modo de [detección](/docs/beta-fraud-protection-studio#modos-de-fps). Puedes elegir entre implemented y tagged.
* [Estado de detección actual](/docs/beta-fraud-protection-studio#estado-de-detección-actual): muestra cómo habría afectado la activación de detección integrada in-app a tus instalaciones durante los últimos 14 días (sin incluir el día actual).   

  Nota: Dado que la detección integrada in-app funciona después de la atribución, los datos de los últimos 7 días pueden ser parciales y seguir actualizándose de forma retroactiva.

Esta sección se divide a su vez en:

* **Nuevas detecciones mediante la lógica basada en eventos in-app**
  * Detecciones: número de instalaciones detectadas por la lógica basada en eventos in-app.
  * Tasa de valor añadido: detección basada en eventos in-app dividida entre el total de instalaciones de tu app.
* **Instalaciones falsas detectadas**
  * Detecciones: número total de detecciones falsas.
  * Tasa de detección: detecciones falsas divididas entre el total de instalaciones de tu app.
* **Instalaciones totales**

* **Detección basada en eventos in-app por fuente de medios**: número de instalaciones de las principales fuentes de medios.

<Image alt="" src="https://files.readme.io/63eedf0c4aa28471d4044a8896e349612fb9d8e9f06aed6b1efbaa825330d150-36947287654033.png" width="624px" />

</Accordion>

<div id="h_01K0ASM01ADVSECMOD01" />

<Accordion title="Datos de Advanced Security Module">

Revisa en tiempo real las detecciones de Advanced Security Module sobre posibles ciberataques a instalaciones en apps de Android. Esto ayuda a garantizar que solo el tráfico verificado llegue a tu app.

<div id="how-to-access-2" />

#### Cómo acceder

1. Inicia sesión en AppsFlyer.
2. En el menú de la izquierda, ve a **Configuración > Protect360 > Fraud Protection Studio**.
3. Usa el menú desplegable de aplicaciones en la parte superior de la página para seleccionar la aplicación que deseas configurar.
4. En el menú de la izquierda, selecciona la tarjeta **Advanced Security Module**.

<div id="the-advanced-security-module-page" />

#### Página de Advanced Security Module

La página Advanced Security Module muestra:

* **Versiones principales de la app**: las 5 versiones con mayor volumen de instalaciones, para que puedas identificar dónde se concentra el tráfico falsificado.

Las detecciones se muestran con uno de los siguientes estados:

* **Bloqueado**: tráfico detenido en tiempo real, antes de la atribución.
* **tagged**: tráfico marcado como sospechoso, pero que sigue atribuyéndose para que puedas revisarlo antes de aplicarlo. Este es el modo de detección predeterminado.
* **Sin etiquetar**: posibles instalaciones que el módulo no marcó.

<div id="note-4" />

> 📘 **Nota**
>
> Para consultar la configuración completa, los requisitos y la información detallada, consulta <Anchor target="_blank" href="/marketers/es/docs/beta-advanced-security-protect360-module">[Beta] Advanced Security Protect360 Module</Anchor>.

</Accordion>

<div id="faqs" />

## Preguntas Frecuentes

<div id="can-i-tag-detection-for-specific-partnersmedia-sources" />

<Accordion title="¿Puedo configurar la detección de etiquetas para partners o fuentes de medios?">

Esto depende del tipo de detección. Por ejemplo, el tagged de partners no está disponible para la detección de secuestros para evitar una detección sesgada.

<div id="what-happens-when-the-tagging-period-ends" />

<Accordion title="¿Qué ocurre cuando finaliza el período de tagged?">

Al final del período de evaluación, la detección tagged se convierte automáticamente al modo implemented.

</Accordion>

<div id="where-can-i-see-tagged-installs" />

<Accordion title="¿Dónde puedo ver las instalaciones tagged?">

Los datos taggeds están disponibles en los siguientes reportes de **reportes de raw data**:

* Instalaciones Tagged
  * En tiempo real
* Instalaciones Tagged
  * Después de la atribución
* Eventos in-app Tagged
  * En tiempo real
* Eventos in-app Tagged
* Después de la atribución

El siguiente reporte tagged también está disponible en **Data Locker**:

* Instalaciones Tagged
  * En tiempo real
* Eventos in-app Tagged
  * Tiempo real

</Accordion>

<div id="can-tagged-detection-be-adjusted-for-appspecific-settings" />

<Accordion title="¿Se puede ajustar la detección tagged para la configuración específica de la aplicación?">

Sí, el tagged de inundaciones de clics se puede configurar a nivel de aplicación.

</Accordion>

<div id="can-i-see-tagged-inapp-events" />

<Accordion title="¿Puedo ver los eventos in-app tagged?">

Sí. Los eventos in-app que estén conectados a una instalación tagged con el mismo ID de AppsFlyer también se pondrán como tagged.

</Accordion>

<div id="who-can-change-set-up-or-view-fps" />

<Accordion title="¿Quién puede cambiar, configurar o ver los FPS?">

Solo el administrador puede cambiar la configuración del FPS. El FPS está visible según la <Anchor target="_blank" href="/marketers/es/docs/manage-data-access-permissions">página de permisos</Anchor>.

</Accordion>

<div id="are-tagged-installs-credited-back-to-the-consumption-plan" />

<Accordion title="¿Las instalaciones tagged se acreditan al plan de consumo?">

N.º La detección tagged no se abonará al plan de consumo.

</Accordion>

<div id="are-tagged-installs-considered-as-fraud" />

<Accordion title="¿Las instalaciones tagged se consideran fraude?">

Protect360 detecta las instalaciones tagged. Sin embargo, se etiquetan según la configuración del cliente. Por lo tanto, tanto en el dashboard general como en los dashboards de Protect360 se reflejarán bajo las métricas atribuidas.

</Accordion>

<div id="can-i-see-how-many-installs-are-tagged-only-by-the-click-flood-tagging" />

<Accordion title="¿Puedo ver cuántas instalaciones están etiquetadas solo con la etiqueta Inundación de Clics?">

Sí. Estos datos están disponibles en los nuevos reportes específicos de la página de exportación y en el dashboard de Protect360.

</Accordion>

</Accordion>

<div data-zendesk-anchors="why-flexible-protection=sobre-fraud-protection-studio 01JEQR86DC1CK03DKCZH760N4M=sobre-fraud-protection-studio h_01JK3BGVNMYFQYQGRPJBVN2A7Z=importante how-flexible-protection-works=c%C3%B3mo-funciona-fraud-protection-studio 01JEQR86DEG7RTRNYFP02WHJGQ=c%C3%B3mo-funciona-fraud-protection-studio 01JETRN5S347ZXV8CGZJDHQH56=key-concepts fps-modes=modos-de-fps h_01JEWZEBBA9VAPCKR87NJ5AK3C=modos-de-fps 01JEWZQ7PBD6W4J15W0HE2Q4MJ=nota where-is-tagged-detection-reflected=d%C3%B3nde-se-refleja-la-detecci%C3%B3n-tagged 01JEWZT9N34FZ9SE8H7EGCMPBZ=d%C3%B3nde-se-refleja-la-detecci%C3%B3n-tagged how-to-use-flexible-protection=c%C3%B3mo-utilizar-fraud-protection-studio 01JEQR86ECSYTM7RN3YPYRSAGE=c%C3%B3mo-utilizar-fraud-protection-studio 01JETF4NJX02APNK1TDV91JQAB=general 01JETF4NJZ7P5M5RTCEFFD0WEP=click-flood-detection 01JFSPDB630RE494JG1W618TKR=importante-1 adjust-detection-status=c%C3%B3mo-acceder-a-inundaci%C3%B3n-de-clics 01JEQVJS6YTQD299X39Q8E3506=c%C3%B3mo-acceder-a-inundaci%C3%B3n-de-clics click-flood-page=p%C3%A1gina-de-inundaci%C3%B3n-de-clics h_01JJKE1ZKE5WDRSPKS8JE9MRRG=p%C3%A1gina-de-inundaci%C3%B3n-de-clics detection-status=estado-de-detecci%C3%B3n h_01JZQ81MW4HMY9B782Y7PWVE8Y=estado-de-detecci%C3%B3n h_01JJKE1ZKEJ4QM2HTT37FERA92=c%C3%B3mo-ajustar-el-estado-de-detecci%C3%B3n current-detection-status=estado-de-detecci%C3%B3n-actual 01JEQVZCNSTXY4V8H2Y1QP224C=estado-de-detecci%C3%B3n-actual 01JETF4NK2KT4MY2G6WMWGMVKB=new-releases 01JFQPRZ5NGEAFBWB1FS0D6DCT=nota-1 how-this-works=c%C3%B3mo-funciona h_01JEXC0ABSTCEA939DGQ5SDJBJ=c%C3%B3mo-funciona how-to-set-the-tagged-mode-time-period-for-future-packages=c%C3%B3mo-acceder-a-los-nuevos-lanzamientos h_01JEXC2HAR2S6BWK28N8W3HHSZ=c%C3%B3mo-acceder-a-los-nuevos-lanzamientos new-releases-page=p%C3%A1gina-de-nuevos-lanzamientos h_01JJKE1ZKE0K1W2VE3KHQ639B1=p%C3%A1gina-de-nuevos-lanzamientos h_01JJKE1ZKE13D7EC6BMN3JJNGW=c%C3%B3mo-configurar-el-per%C3%ADodo-de-tiempo-del-modo-tagged-para-paquetes-futuros 01JF50BVZ75ZSXTJEKAV4HVSTZ=nota-2 how-to-evaluate-and-implement-current-active-packages=c%C3%B3mo-evaluar-e-implementar-los-paquetes-activos-actuales h_01JEXC3DESR10WVV34ED30B7BH=c%C3%B3mo-evaluar-e-implementar-los-paquetes-activos-actuales to-implement-the-current-package-if-in-tagged-status=para-implementar-el-paquete-actual-si-est%C3%A1-en-estado-tagged h_01JF505FK4NP88WYXP8PVQRYDS=para-implementar-el-paquete-actual-si-est%C3%A1-en-estado-tagged 01JF50BVZ9QPT5W41P8KQAREKV=nota-3 h_01JQXFMBGXWKXMFFAPHN5V66Q7=app-detection-evaluation h_01JQXPVD4MXPYQQZXNTM2H9BNA=importante-2 how-to-access-app-detection-evaluation=c%C3%B3mo-acceder-a-app-detection-evaluation h_01JQXG4GJ2DB8HM26K3E1WA3A1=c%C3%B3mo-acceder-a-app-detection-evaluation app-detection-evaluation-page=p%C3%A1gina-app-detection-evaluation h_01JQXG6QDSTAPCJDMQVQMXS86W=p%C3%A1gina-app-detection-evaluation how-to-adjust-the-detection-status=c%C3%B3mo-ajustar-el-estado-de-detecci%C3%B3n-1 h_01JQXG6QEAM0Y67G504JV2SA5R=c%C3%B3mo-ajustar-el-estado-de-detecci%C3%B3n-1 h_01JWAVMSW1K6R4FJ8J9AYYNHQW=reengagement-hijacking-detection how-this-works::a0e9054=c%C3%B3mo-funciona-1 h_01JWAVPAVKM9RSXFMZN9CM36ER=c%C3%B3mo-funciona-1 how-to-access=c%C3%B3mo-acceder h_01JWAVPAVK7ZT471AQAFKAS64K=c%C3%B3mo-acceder reengagement-hijacking-page=p%C3%A1gina-de-secuestro-de-re-engagement h_01JWAVPAVKKB4JSP41P967EESS=p%C3%A1gina-de-secuestro-de-re-engagement h_01JZMAX35E1KT04VTKAFB8FAF3=inapp-based-detection how-to-access::db81debe=c%C3%B3mo-acceder-1 h_01JZMAZET0JXYEDGKE0B797TQ7=c%C3%B3mo-acceder-1 the-inapp-based-detection-page=la-p%C3%A1gina-de-detecci%C3%B3n-integrada-in-app h_01JZMB0NET3Y8CFVZ1WP0WDPMJ=la-p%C3%A1gina-de-detecci%C3%B3n-integrada-in-app advanced-security-module=h_01K0ASM01ADVSECMOD01 h_01K0ASM02ADVSECMOD02=c%C3%B3mo-acceder-2 h_01K0ASM07ADVSECMOD07=p%C3%A1gina-de-advanced-security-module the-advanced-security-module-page=p%C3%A1gina-de-advanced-security-module h_01K0ASM13ADVSECMOD13=nota-4 faqs=preguntas-frecuentes 01JEQR86EMZQFNSZ5NWZ08F5YQ=preguntas-frecuentes 01JETRQMEJHZMHAKHHX5SZ028N=can-i-tag-detection-for-specific-partnersmedia-sources 01JETRQMEKJ27S5GGVR73H6WZB=what-happens-when-the-tagging-period-ends 01JETRQMEMKV8K7EQMS1BJB989=where-can-i-see-tagged-installs 01JETRQMEM6BMEXGYJM6WVE313=can-tagged-detection-be-adjusted-for-appspecific-settings 01JF79M50ZZ7HP0XCW1F4YJH7R=can-i-see-tagged-inapp-events 01JF79M50ZTMM1Y2YW8ARTYVTN=who-can-change-set-up-or-view-fps 01JF79M510HGEVC1WTWXAHSAQH=are-tagged-installs-credited-back-to-the-consumption-plan 01JF79M510B5WW067Q4T4FDVSC=are-tagged-installs-considered-as-fraud 01JF79M5105Z9AH95K6VVANANM=can-i-see-how-many-installs-are-tagged-only-by-the-click-flood-tagging" />
