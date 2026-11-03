---
title: 'Plataforma de colaboración de datos (DCP): ejecuta y administra la medición'
metadata:
  keywords:
    - Marketers
    - Data Management
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Management
  created_at: '2026-03-04T10:59:23Z'
  edited_at: '2026-08-12T11:53:26Z'
  id: 44427723216017
  locale: es
  section: Collaboration measurement
  section_id: 38034865098641
  url: https://support.appsflyer.com/hc/es/articles/44427723216017
---
> **En resumen:** Después de configurar la medición on-site o off-site, ejecútala como una medición en vivo o como una medición histórica. Elige el modo que mejor se adapte a tu objetivo: mide el rendimiento continuamente o valida los resultados durante un período definido.

## Sobre los modos de ejecución de la medición

Una vez que hayas <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-configure-collaboration-measurement#configurar-la-medición-de-campañas-on-site-y-off-site">configurado la medición on-site o off-site</Anchor>, estarás listo para elegir cómo ejecutar la medición.

Tienes dos modos de ejecución disponibles:

* **Medición en tiempo real**: Medición continua que se actualiza a intervalos regulares, para que puedas monitorear el rendimiento continuamente a medida que se agregan nuevos datos en el dashboard en tiempo real.
* **Medición histórica**: Medición única en un intervalo de fechas específico que puedes ver y analizar en un dashboard histórico.

### Mediciones en tiempo real vs históricas

| Tema | Medición histórica | Medición en tiempo real |
| --- | --- | --- |
| Cuando se ejecuta | Ejecución **bajo demanda** (manual) | Ejecución diaria **automatizada** |
| Fuente de datos | Utiliza **cargas de datos históricos** | Requiere **configuración de SDK/ETL** y se ejecuta a intervalos de tiempo predefinidos |
| Tipos de fuentes compatibles | <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources#step-3-set-source-update-method">Agregar</Anchor> y <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources#step-3-set-source-update-method">sobrescribir (snapshot)</Anchor> | <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources#step-3-set-source-update-method">Fuentes personalizadas de tipo append</Anchor> |
| Selección del marco de tiempo | Selecciona una **fecha de inicio y fin** (a partir de los datos disponibles) | Selecciona una **fecha de inicio** (la plataforma calcula el período histórico de activación y continúa acumulando datos) |
| Cuántos por medición | Múltiples | Uno |

### Elige la medición que necesitas

Utiliza la siguiente guía para decidir qué medición se ajusta a tu objetivo.

**Elige la medición en tiempo real si quieres**

* Medición continua que se actualiza a medida que llegan nuevos datos
* Un dashboard que puedes usar para monitorear el rendimiento continuamente
* Una configuración destinada a una medición a largo plazo y siempre activa (no un análisis único)

**Elige la medición histórica si deseas**

* Ejecutar una medición única para un intervalo de fechas específico.
* Analizar el rendimiento una vez finalizada una campaña.
* Ejecutar un análisis de qué pasa si cambias la ventana de lookback para ver cómo afecta la atribución.

**Consejo:** Si primero estás probando tu configuración o validando un período específico, comienza con la **medición histórica**. Cuando estés listo para el monitoreo continuo, cambia a **medición en tiempo real** para actualizaciones continuas.

## Ejecutar una medición en tiempo real

**Antes de empezar:**  <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-configure-collaboration-measurement#configurar-la-medición-de-campañas-on-site-y-off-site">Configura la campaña de medición on-site u off-site en la página de configuración de la medición</Anchor>.

1. En la página **Configuración de la medición**, haz clic en **Ejecutar ahora**.

   Si **Ejecutar ahora** está deshabilitado, tus tareas de medición están incompletas. Completa todas las tareas de configuración necesarias para ejecutar la medición.
2. En el cuadro **Preparar para ejecutar**, selecciona **Dashboard en tiempo real**.

   > 📘 **Nota:**
   >
   > * Si la medición utiliza fuentes de <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources#step-3-set-source-update-method">sobrescritura</Anchor>, solo está disponible el **dashboard histórico**. El **dashboard en tiempo real** requiere que las fuentes **de tipo append** (o los eventos in-app del SDK de AppsFlyer) se actualicen automáticamente.
   > * Solo se puede ejecutar **una medición en tiempo real** a la vez en una colaboración. Si inicias una nueva medición en tiempo real mientras ya se está ejecutando otra, se te pedirá que pauses la existente.

3. Cambia el nombre del dashboard o mantén el nombre predeterminado.
4. Selecciona la **fecha de inicio** de la medición. El valor predeterminado es la fecha de hoy, pero puedes seleccionar una fecha pasada del selector de fechas. (Solo puedes seleccionar las fechas que existen en tus fuentes de datos).
5. Haz clic en **Iniciar** para comenzar la medición en tiempo real. Serás redireccionado a la página de medición de la colaboración.
6. En la página de medición de la colaboración, después de que las comprobaciones de validación automáticas se completen correctamente, haz clic en **Ejecutar ahora**.

## Ejecutar una medición histórica

**Antes de empezar:**  <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-configure-collaboration-measurement#configurar-la-medición-de-campañas-on-site-y-off-site">Configura la campaña de medición on-site u off-site en la página de configuración de la medición</Anchor>.

1. En **Configuración de medición**, haz clic en **Ejecutar ahora**.  
   Si **Ejecutar ahora** está deshabilitado, tus tareas de medición están incompletas. Completa todas las tareas de configuración necesarias para ejecutar la medición.
2. En el cuadro **Preparar para ejecutar**, selecciona **Dashboard histórico**.
3. Cambia el nombre del dashboard o mantén el nombre predeterminado.
4. Selecciona el **rango de fechas de medición** (solo puedes seleccionar las fechas que existen en tus fuentes de datos):
   * Establece la **fecha de inicio**.
   * Establece la **fecha de finalización**.
5. Haz clic en **Iniciar** para comenzar la medición histórica. Serás redireccionado a la página de medición de la colaboración.
6. En la página de medición de la colaboración, después de que las comprobaciones de validación automáticas se completen correctamente, haz clic en **Ejecutar ahora**.

## Gestionar la medición

Después de configurar y ejecutar la medición, administrala desde el panel de medición de la página de medición de la colaboración. Puedes pausarla o reiniciarla en tiempo real, ajustar las fechas, volver a ejecutar mediciones históricas o duplicar una medición para crear una nueva ejecución.

### La página de medición de la colaboración

[![](https://files.readme.io/f1ff9677dcae50df83fe32a8c54925c52ea91f5a2f7f133bc6bce3041fe0341d-44437720904209.png)](https://files.readme.io/f1ff9677dcae50df83fe32a8c54925c52ea91f5a2f7f133bc6bce3041fe0341d-44437720904209.png)

<div id="pause-or-restart-live-measurement" />

<Accordion title="Pausar o reiniciar la medición en tiempo real">

#### Leyenda

* **A** - El panel de medición
* **B** - La medición seleccionada
* **C** - El conmutador compartido
* **D** - Menú de opciones.

1. Abre la página de medición de la colaboración.
2. Selecciona el **dashboard en tiempo real** en el panel de medición ([A](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#la-página-de-medición-de-la-colaboración)).
3. Abre el menú de opciones ([D](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#la-página-de-medición-de-la-colaboración)) y haz clic en **Configuración de medición**.
4. En la página **Configuración de la medición**, realiza una de las siguientes acciones:
   * Para **pausar** la atribución en tiempo real, desactiva **Activar medición** y, a continuación, confirma en el cuadro **¿Pausar medición?** .
   * Para **reiniciar** la atribución en tiempo real, activa **Activar medición**.

</Accordion>

<div id="change-measurement-start-and-end-dates" />

<Accordion title="Cambiar las fechas de inicio y fin de la medición">

Puedes cambiar:

* La **fecha de inicio** de una medición en tiempo real, o
* Las **fechas de inicio y fin** de una medición histórica.

Para cambiar las fechas de inicio y fin de la medición, sigue estos pasos:

1. Abre la página de medición de la colaboración.
2. Selecciona la medición en el panel de medición ([A](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#la-página-de-medición-de-la-colaboración)).
3. Abre el menú de opciones ([D](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#la-página-de-medición-de-la-colaboración)) y haz clic en **Configuración de medición**.
4. En la página **Configuración de la medición**, haz clic en el icono del lápiz.
5. Haz clic en la fecha de inicio o fin.
6. Selecciona la nueva fecha del selector de fechas.

</Accordion>

<div id="rerun-a-historical-measurement" />

<Accordion title="Vuelve a ejecutar la medición histórica">

Volver a ejecutar una medición histórica recalcula la atribución utilizando los datos más recientes. Los resultados actuales se reemplazan por los nuevos.

1. Abre la página de medición de la colaboración.
2. Selecciona la medición en el panel de medición ([A](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#la-página-de-medición-de-la-colaboración)).
3. Abre el menú de opciones ([D](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#la-página-de-medición-de-la-colaboración)) y haz clic en **Volver a ejecutar**.
4. En el mensaje de solicitud, haz clic en **Vovler a ejecutar**.
5. En la página de medición de la colaboración, después de que las comprobaciones de validación automáticas se completen correctamente, haz clic en **Ejecutar ahora**.

</Accordion>

<div id="duplicate-a-live-or-historical-measurement" />

<Accordion title="Duplica una medición en tiempo real o histórica">

Duplicar crea una nueva medición basada en una configuración existente. Puedes actualizar la configuración y ejecutarla como una nueva medición.

1. Abre la página de medición de la colaboración.
2. Selecciona la medición en el panel de medición ([A](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#la-página-de-medición-de-la-colaboración)).
3. Abre el menú de opciones ([D](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#la-página-de-medición-de-la-colaboración)) y haz clic en **Duplicar**.
4. En la página duplicada de **configuración de medición**, personaliza la medición según tus necesidades.

</Accordion>

<div id="share-a-dashboard" />

<Accordion title="Compartir un dashboard">

Puedes compartir un dashboard con tus colaboradores activando el selector **Compartido**. Cuando **Compartido** está ACTIVADO, el dashboard (y sus resultados de medición) está disponible para otros usuarios de la colaboración.

Lo que pueden hacer los colaboradores, cuando **Compartido** está ACTIVADO, depende de si están **asignados** al dashboard.

* **Los usuarios asignados pueden:**
  * Abrir y **ver el dashboard**
  * Abre la **Configuración de medición** y **edita solo las tareas asignadas.**

* **Los usuarios asignados no pueden:**
  * Activa/desactiva **Compartido** (compartir o dejar de compartir)
  * **Vuelve a ejecutar** la medición

* Los **usuarios no asignados** tienen un acceso más limitado, incluso si el dashboard es compartido (por ejemplo, es posible que no vean el resumen de resultados y no puedan volver a ejecutarse o compartirse).

Para compartir un dashboard:

1. Abre la página de medición de la colaboración y selecciona el **dashboard** que deseas compartir desde el panel de medición ([A](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#la-página-de-medición-de-la-colaboración)).
2. Activar **Compartido** ([C](/docs/data-collaboration-platform-dcp-run-and-manage-measurement#la-página-de-medición-de-la-colaboración)). El dashboard estará disponible en tu página de medición de colaboradores.
3. Desactivar **Compartido** para dejar de compartir. Cuando se desactiva el uso compartido, solo tú (y los usuarios con los permisos adecuados) pueden acceder al dashboard.

</Accordion>

<div data-zendesk-anchors="about-the-measurement-run-modes=sobre-los-modos-de-ejecuci%C3%B3n-de-la-medici%C3%B3n h_01KJW81RSZPK2Y1PSAF9FSMXB6=sobre-los-modos-de-ejecuci%C3%B3n-de-la-medici%C3%B3n live-vs-historical-measurements=mediciones-en-tiempo-real-vs-hist%C3%B3ricas h_01KJW81RSZBG5ZC8HE9WFXE34D=mediciones-en-tiempo-real-vs-hist%C3%B3ricas choose-the-measurement-you-need=elige-la-medici%C3%B3n-que-necesitas h_01KJW81RSZQG21Z0MRHWPMD69F=elige-la-medici%C3%B3n-que-necesitas run-a-live-measurement=ejecutar-una-medici%C3%B3n-en-tiempo-real h_01KJW81RT0Q1RWEHZP66B5141M=ejecutar-una-medici%C3%B3n-en-tiempo-real h_01KJW81RT0N37ARE5570X7MYJF=nota run-a-historical-measurement=ejecutar-una-medici%C3%B3n-hist%C3%B3rica h_01KJW81RT0QECMGBTRFSETA5A8=ejecutar-una-medici%C3%B3n-hist%C3%B3rica manage-measurements=gestionar-la-medici%C3%B3n h_01KJW81RT046RE5FVHPGEDMCC5=gestionar-la-medici%C3%B3n the-collaboration-measurement-page=la-p%C3%A1gina-de-medici%C3%B3n-de-la-colaboraci%C3%B3n h_01KJWNTR04PRG54W0GZVGQY72X=la-p%C3%A1gina-de-medici%C3%B3n-de-la-colaboraci%C3%B3n legend=leyenda h_01KJWNF8NAJ9NT5T8NAVTCMZVA=leyenda h_01KJW81RT0A148W49X0BR0V9YM=pause-or-restart-live-measurement h_01KJW81RT0GYDCZCXXV2G5EJD7=change-measurement-start-and-end-dates h_01KJW81RT054CCYMTKFN7TS1XV=rerun-a-historical-measurement h_01KJW81RT0RKQJRCTRVP36YBKV=duplicate-a-live-or-historical-measurement h_01KJW81RT0C3R95JQVPGSZ043B=share-a-dashboard" />
