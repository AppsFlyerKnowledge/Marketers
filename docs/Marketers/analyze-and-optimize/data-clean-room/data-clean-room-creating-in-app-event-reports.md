---
title: 'Data Clean Room: creación de reportes de eventos in-app'
metadata:
  keywords:
    - Premium
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-inbar-agassi
    - Marketers
    - Data Clean Room
  created_at: '2022-09-22T12:03:40Z'
  edited_at: '2026-08-12T11:52:35Z'
  id: 9312610473233
  locale: es
  section: Data Clean Room
  section_id: 4591191779217
  url: https://support.appsflyer.com/hc/es/articles/9312610473233
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En resumen:** Crea reportes de eventos in-app para centrarte en la actividad del usuario que se produce después de instalar una aplicación. Extrae parámetros de eventos específicos del raw data de tus eventos in-app, haz coincidir los datos con fuentes personalizadas y, luego, procésalos y preséntalos en forma agregada.

## Creación de un reporte de eventos in-app

**Para crear un reporte de eventos in-app, sigue los pasos que se detallan en las pestañas a continuación.**

**Nota:** Estos pasos se dividen en pestañas para facilitar la lectura. Se deben completar todos los pasos para crear el reporte. *(Algunos pasos, como se indica, no son relevantes para los reportes que no usan fuentes personalizadas).*

<div id="perform-preliminary-steps" />

<Accordion title="Realizar los pasos preliminares">

1. Ve a la pestaña **Reportes** de **DCR**.
2. Haz clic en el botón **+ Nuevo reporte**.
3. Selecciona **Eventos in-app** como el tipo de datos de origen y, a continuación, haz clic en **Siguiente** en la esquina inferior derecha de la pantalla.
4. Introduce un nombre para el reporte.
   * Puede ser cualquier nombre que te ayude a identificar el reporte en la plataforma DCR.
   * **Nota:** **Importante:** Asegúrate de que el nombre del reporte sea diferente de todos los demás reportes de tu cuenta, de lo contrario no podrás [guardar el reporte](/docs/data-clean-room-creating-in-app-event-reports#configure-report-settings-and-save-the-report).
   * Requisitos del nombre del reporte:
     * Longitud: 2-80 caracteres
     * Caracteres válidos:
       * letras **(A-Z, a-z)**
       * números **(0-9)**, *no pueden ser el primer carácter de un nombre*
       * un guión (-), *no puede ser el primer carácter de un nombre*
     * Caracteres inválidos:
       * espacios
       * todos los demás símbolos o caracteres especiales

</Accordion>

<div id="select-sources" />

<Accordion title="Seleccionar las fuentes">

Especifica los datos de origen que se utilizarán para el reporte:

#### **Fuentes de eventos in-app**

* **Aplicaciones:** selecciona una o más de las aplicaciones en tu cuenta de AppsFlyer.
* **Periodo de tiempo:** selecciona la cantidad de días de datos históricos que deseas que DCR busque para eventos in-app (de 1 a 30 días).
* **Eventos:** selecciona uno o más eventos in-app para incluirlos en el reporte.
  * Los eventos disponibles incluyen todos los eventos in-app **de las aplicaciones seleccionadas** que se configuraron para reportar datos a AppsFlyer a través del SDK o de la API de servidor a servidor (S2S).
* **Tipos de fuentes:** selecciona uno o más tipos de datos de eventos in-app: 

| Instalaciones | Eventos in-app relacionados con las atribuciones de instalaciones<ul><li>Una instalación se registra cuando un usuario descarga, instala e inicia una aplicación móvil.</li></ul> |
| --- | --- |
| Reengagements | Eventos in-app relacionados con reengagements<ul><li>Un reengagement se registra cuando un usuario inactivo de una aplicación específica interactúa con una campaña de retargeting para la aplicación y posteriormente la abre.</li></ul> |
| Reatribuciones | Eventos in-app relacionados con las reatribuciones<ul><li>Una reatribución se registra cuando un antiguo usuario de una aplicación específica (que la había desinstalado) participa en una campaña de retargeting para la aplicación y, posteriormente, la reinstala.</li></ul> |

#### **Fuentes de datos**

1. [Opcional] Agrega más fuentes para usar en el reporte. A la hora de elegir si deseas más fuentes, ten en cuenta la diferencia significativa entre los reportes que **sí** y los que **no** usan fuentes personalizadas.
   * Un reporte que **no** usa fuentes personalizadas extrae parámetros y valores de eventos específicos del raw data de los eventos in-app.
   * Un reporte que **sí** usa fuentes personalizadas extrae parámetros y valores de eventos específicos del raw data de los eventos in-app y, luego, compara estos datos con datos de nivel de usuario de sus fuentes personalizadas (como datos de sus sistemas de BI o CRM).
2. Completa los siguientes pasos en función de si el reporte usa o no fuentes personalizadas:
   * Si tu reporte **no** usa fuentes personalizadas, salta a **[Seleccionar dimensiones](/docs/data-clean-room-creating-in-app-event-reports#select-dimensions),** y luego continúa con los pasos de todas las pestañas restantes.
   * Si tu reporte **sí** usa fuentes personalizadas, continúa con los pasos de la sección [**Unir fuentes**](#join-sources-only-for-reports-containing-custom-sources) (a continuación) y todas las pestañas restantes.

</Accordion>

El siguiente paso es relevante **solo para reportes que usan fuentes personalizadas.**

<div id="join-sources-only-for-reports-containing-custom-sources" />

<Accordion title="Unir fuentes (solo para reportes que contienen fuentes personalizadas)">

Con el fin de hacer coincidir los datos entre las fuentes, cada una de las fuentes **personalizadas** usadas en el reporte debe incluir un <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-setting-up-cloud-services">identificador</Anchor> asignado a un **identificador clave** en los datos del evento in-app.

* Los reportes de eventos in-app incluyen **todos** los eventos seleccionados que coincidan con el identificador clave durante el período de tiempo seleccionado.

#### **¿Qué es un identificador clave?**

Puedes asignar a cualquiera de estos identificadores de datos de eventos in-app como **identificadores clave:**

* **ID de AppsFlyer (af\_id):** un identificador único de la aplicación generado por AppsFlyer en la instalación:
  * Este ID aparece en todos los eventos registrados por AppsFlyer.
  * Se genera un nuevo ID de AppsFlyer si se elimina una aplicación y luego se vuelve a instalar.
* **ID de usuario de cliente (CUID):** un identificador de usuario único, generalmente generado y establecido por el propietario de la aplicación en el momento del registro del usuario.
  * El uso de CUID para asignar datos requiere que la aplicación esté configurada para <Anchor target="_blank" href="/marketers/es/docs/customer-user-id-field-cuid">enviar el CUID a AppsFlyer</Anchor> a través del SDK o de la API de servidor a servidor (S2S).

> 🚧 **¡Importante!**
>
> No todas las fuentes de medios permiten la coincidencia mediante el CUID. Se recomienda encarecidamente utilizar el ID de AppsFlyer.

#### **Esquemas de asignación (directa/indirecta)**

Si el reporte incluye más de una fuente personalizada, solo es necesario asignar una de ellas **directamente** a un identificador clave de evento in-app. Se pueden asignar otras fuentes personalizadas **directa o indirectamente**, como se ilustra en el siguiente ejemplo:

> 📄 **Ejemplo**
>
> ![dcr_mapping_identifiers_in-app events.png](https://files.readme.io/73d0e929663bda4e6f142c64d0228fdf1eeec3b02ef1560f6f03f2a089d00664-9969546429713.png)
>
> En el escenario que se muestra arriba:
>
> * El identificador de fuente personalizada n.º 1, **AF**, se asigna directamente al identificador clave del evento in-app **af\_id**.
> * La fuente personalizada n.º 2 se asigna indirectamente: **user\_code** --> **AF** --> **af\_id**.
> * La fuente personalizada n.º 3 se asigna indirectamente (a través de una cadena más larga):
>   **user\_id** --> **user\_code** --> **AF** --> **af\_id**.
> * El identificador de fuente personalizada n.º 4 **ID** se asigna directamente al identificador clave del evento in-app **af\_id**.
>   * Ten en cuenta que podría haberse asignado indirectamente en su lugar (a través del identificador de fuente personalizada n.º 3 **user\_id**), pero cualquiera de las dos opciones funciona bien.
>
> ✓ Este esquema de asignación funciona para hacer coincidir los datos entre todas las fuentes, ya que cada fuente personalizada se asigna directa o indirectamente al identificador clave de evento in-app **af\_id**.

</Accordion>

Las pestañas restantes son relevantes para **todos los reportes de eventos in-app,** ya sea que incluyan o no fuentes personalizadas.

<div id="select-dimensions" />

<Accordion title="Seleccionar las dimensiones">

Recuerda que los datos a nivel de usuario no pueden ser reportados por DCR. En su lugar, te proporciona la información necesaria para la toma de decisiones agregando (o agrupando) los datos por las dimensiones que elijas.

Por lo general, una dimensión es un atributo por el que se clasifican los usuarios de la aplicación (por ejemplo, geolocalización, fecha de instalación, campaña, etc.).

#### **Extracción de dimensiones de event\_value**

Cuando los eventos in-app se reportan a AppsFlyer a través del SDK o la API de S2S, gran parte del raw data están contenido en un solo campo llamado **event\_value.** Este campo de datos estructurados incluye todos los parámetros específicos de los eventos in-app que se han configurado para los eventos que tus aplicaciones envían a AppsFlyer.

Una de las principales ventajas de los reportes de eventos in-app es que te permiten extraer parámetros específicos y sus valores del **event\_value** para los eventos que elijas.

**Para extraer dimensiones del campo event\_value para utilizarlas en reportes de DCR:**

1. En la lista **Dimensiones de las fuentes**, haz clic en el botón <Image alt="extract_dimension_button.png" src="https://files.readme.io/c238da4a1d2a15fe2249070747fa6247db63ab4129b1c72804b84550675214f3-10754426767761.png" width="123px" /> .

   Se abre la ventana **Extraer campo de event\_value**.
2. En el cuadro **Campo de reporte**, introduce el nombre de la dimensión extraída tal y como deseas que aparezca en el reporte.
3. Del **parámetro event\_value**, selecciona el parámetro de evento in-app que se debe asignar de forma predeterminada al campo de reporte (dimensión) que definiste en el paso 2.
   * Los parámetros disponibles incluyen aquellos que se han configurado en los **eventos in-app seleccionados** **de las aplicaciones seleccionadas**.
4. Es posible que la asignación predeterminada difiera según la aplicación o el evento. Si este es el caso:
   1. Haz clic en el botón **Agregar excepción**
   2. Selecciona la aplicación y el evento para los que se debe asignar el campo de reporte de forma diferente.
   3. Selecciona el parámetro de evento in-app que se debe asignar al campo de reporte para esta combinación de aplicación y evento.
   4. Sigue estos pasos para tantas excepciones como desees configurar.
5. Cuando hayas terminado de configurar la asignación para la dimensión extraída, haz clic en **Guardar y agregar otra** para extraer otra dimensión del campo event\_value o en **Guardar** para volver a la pantalla principal.

**Para editar las dimensiones extraídas:**

1. En la lista **Dimensiones de las fuentes** o **Dimensiones del reporte**, coloca el cursor sobre el nombre de la dimensión que deseas editar.
2. Haz clic en el botón <Image alt="more_options_button.png" src="https://files.readme.io/d52908bc376b10d60f12ec401b8ba13adf1946ca4ef27cb7a588fae33a603384-10755347815441.png" width="21px" /> que se muestra a la derecha de la dimensión.
3. Selecciona **Editar campo extraído**.
4. Realiza los cambios necesarios en la asignación de nombre y/o parámetros del **Campo de reporte**.
5. Haz clic en **Guardar** para guardar tus cambios.

**Para eliminar las dimensiones extraídas:**

1. En la lista **Dimensiones de las fuentes** o **Dimensiones del reporte**, coloca el cursor sobre el nombre de la dimensión que deseas eliminar.
2. Haz clic en el botón <Image alt="more_options_button.png" src="https://files.readme.io/d52908bc376b10d60f12ec401b8ba13adf1946ca4ef27cb7a588fae33a603384-10755347815441.png" width="21px" /> que se muestra a la derecha de la dimensión.
3. Selecciona **Eliminar campo**.
   * **¡Importante!** Si eliminas un campo extraído de la lista **Dimensiones del reporte**, se eliminará la definición del campo extraído. Si deseas quitar el campo del reporte conservando su definición, selecciona el campo y usa el comando **Quitar** en su lugar.

#### **Selección de las dimensiones del reporte**

Las dimensiones del reporte de eventos in-app pueden incluir:

* Dimensiones que has extraído de event\_value
* [Dimensiones predeterminadas de eventos in-app](/docs/data-clean-room-creating-in-app-event-reports#default-inapp-event-dimensions)
* Cualquier campo de las fuentes personalizadas del reporte que se haya <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-working-with-sources#3-define-the-source-structure">categorizado como una dimensión</Anchor> (si corresponde)

**Para seleccionar las dimensiones que se incluirán en el reporte:**

1. Selecciona una o más dimensiones en la lista **Dimensiones de las fuentes** de la izquierda y usa el botón **Agregar** en el centro de la pantalla para agregarlas a la lista de **Dimensiones del reporte**.
   * Puedes usar la barra de búsqueda para buscar dimensiones en las listas.
2. Para quitar una dimensión, selecciónala en la lista **Dimensiones del reporte** y usa la función **Quitar** para devolverla a la lista **Dimensiones de las fuentes**.
3. Repite este proceso hasta que hayas agregado cada dimensión que desees incluir en el reporte.

**Nota:** De forma predeterminada, todos los reportes se agrupan por la dimensión de evento in-app **media\_source**. Si no deseas utilizar esta dimensión en el reporte, puedes quitarla de la lista **Dimensiones del reporte**.

#### **[Opcional] Personalización de nombres para mostrar de las dimensiones**

De forma predeterminada, los nombres de las dimensiones se muestran en el reporte exactamente como se nombran en los datos de eventos in-app o en las fuentes personalizadas. Si lo deseas, puede personalizar los nombres de las dimensiones para el reporte.

**Para personalizar los nombres para mostrar de las dimensiones:**

1. En la lista **Dimensiones del reporte**, coloca el cursor sobre el nombre de la dimensión cuyo nombre para mostrar deseas editar.
2. Haz clic en el botón Editar ![edit_button.png](https://files.readme.io/f4ef4722724c776ce4034ab07492a4ac80825f6f15350911c1cbb51ac4843092-10754262613649.png) que se muestra a la derecha de la dimensión.
3. Cambia el nombre por el nombre para mostrar de la dimensión que se utilizará en el reporte (hasta 50 caracteres).
4. Haz clic en **Aceptar** para guardar el nombre para mostrar, o en **X** para cancelar.

**Nota:** Si deseas cambiar el nombre de una **dimensión extraída**, sigue los pasos para editar las dimensiones extraídas (arriba).

#### **Preservación de la privacidad mientras se agrupa por dimensión (reagrupación)**

En función del tamaño del conjunto de datos, el número de dimensiones que elijas y otros factores, es posible que un reporte incluya uno o varios grupos que contengan muy pocos usuarios para permitir la generación de reportes. Si los datos se reportaran de esta manera, se infringirían las restricciones contra el suministro de datos a nivel de usuario.

Sin embargo, en lugar de eliminar u ocultar los datos del reporte por completo, DCR utiliza un **Mecanismo de reagrupamiento** para proporcionar tantos detalles como sea posible mientras se mantiene la privacidad del usuario.

> 📄 **Ejemplo de reagrupamiento**
>
> Supongamos que has configurado un reporte de acuerdo con las siguientes dimensiones (en orden):
>
> * **Dimensiones de eventos in-app:**
>   * media source
>   * campaña única
>   * adset\_name
>   * id\_adset
> * **Dimensiones de fuentes personalizadas:**
>   * user\_type
>
> **Antes de reagrupar**
>
> Después del análisis inicial de los datos, DCR determina que los datos se desglosarían de la siguiente manera:
>
>
>
> | Fuente de  <br />medios | campaña única | Nombre del  <br />conjunto de anuncios | ID de  <br />anuncio | Tipo de  <br />usuario | rev  <br />D0 | Ingresos  <br />D7 | cuenta | ¿Reportable? |
> | --- | --- | --- | --- | --- | --- | --- | --- | --- |
> | fuente\_de\_medios | UA\_100 | verde | kjh867 | comprador | 1 | 4 | 120 | ✓ |
> | fuente\_de\_medios | UA\_101 | verde | jkj987 | ultra | 2 | 23 | 220 | ✓ |
> | fuente\_de\_medios | UA\_200 | verde | lkh123 | beg | 6 | 7 | . | **X** |
> | fuente\_de\_medios | UA\_200 | verde | ilk945 | beg | 3 | 21 | . | **X** |
> | fuente\_de\_medios | UA\_200 | verde | PLM654 | beg | 8 | 17 | . | **X** |
>
>
>
> En la actualidad, las últimas 3 filas no se pueden notificar porque hay muy pocos usuarios en cada una. (Esta fuente de medios requiere un mínimo de **y** usuarios con el fin de ser reportables. Aquí, solo tenemos **x**).
>
> De acuerdo con la lógica de reagrupamiento, DCR primero "elimina" la última dimensión de evento in-app enumerada (en este caso, **ad\_id**). A continuación, vuelve a analizar los datos para ver qué filas se pueden reportar.
>
> **Después de reagrupar**
>
> Después de aplicar la lógica de reagrupamiento, el reporte aparece de la siguiente manera:
>
>
>
> | Fuente de  <br />medios | campaña única | Nombre del  <br />conjunto de anuncios | ID de  <br />anuncio | Tipo de  <br />usuario | rev  <br />D0 | Ingresos  <br />D7 | cuenta | ¿Reportable? |
> | --- | --- | --- | --- | --- | --- | --- | --- | --- |
> | fuente\_de\_medios | UA\_100 | verde | kjh867 | comprador | 1 | 4 | 120 | ✓ |
> | fuente\_de\_medios | UA\_101 | verde | jkj987 | ultra | 2 | 23 | 220 | ✓ |
> | fuente\_de\_medios | UA\_200 | verde | RESTRINGIDO | beg | 17 | 45 | y (x+x+x) | ✓ |
>
>
>
> **Resultados:**
>
> * La última fila ahora combina los datos que anteriormente habían estado en 3 filas. Ahora, la fila combinada tiene un recuento de usuarios igual a **y**, y se puede reportar.
> * La dimensión que se eliminó ahora se reporta como RESTRICTED.
> * Si todavía hubiera habido filas no reportables (menos de **y** usuarios), DCR continuaría analizando los datos de forma iterativa, eliminando una dimensión tras otra hasta que:
>   * pueda reportar todas las filas; o
>   * se quede sin dimensiones de eventos in-app para eliminar
>
> **Nota:** De forma predeterminada, DCR aplica el reagrupamiento solo a **[dimensiones predeterminadas de eventos in-app](/docs/data-clean-room-creating-in-app-event-reports#default-inapp-event-dimensions)** (no a las dimensiones de eventos in-app extraídas ni a las dimensiones de fuentes personalizadas). Si los datos se agrupan por una dimensión de evento in-app predeterminada, el resultado sería una fila que contiene menos de **y** usuarios, y los datos de esa fila se notificarían como RESTRICTED.
>
> * *Consulta a continuación una opción avanzada que puedes usar para aplicar también el reagrupamiento a las dimensiones de fuentes personalizadas.*

#### **[Opcional] Administración de la prioridad de las dimensiones**

De forma predeterminada, las dimensiones de eventos in-app se eliminan en orden inverso al orden en el que aparecen en la lista **Dimensiones del reporte**. Sin embargo, puedes modificar la secuencia predeterminada y/o aplicar el reagrupamiento a las dimensiones de fuentes personalizadas seleccionadas (si corresponde) para conservar las dimensiones más importantes para ti.

**Para cambiar el orden en el que se eliminan las dimensiones:**

1. Haz clic en el botón **Administrar la prioridad de las dimensiones**.
2. Selecciona una dimensión y arrástrala a la posición deseada en la lista (o usa los botones de flecha de la derecha para moverla).
   * La dimensión etiquetada como **Máxima prioridad** (en la parte superior de la lista) significa que es la última en ser eliminada si se requiere reagrupamiento.
3. [Opcional] Para aplicar el reagrupamiento a dimensiones de fuentes personalizadas (para reportes que utilizan fuentes personalizadas):
   1. Haz clic en **Usar opciones avanzadas para refinar el reagrupamiento**
   2. Selecciona las dimensiones de fuentes personalizadas a las que deseas aplicar el reagrupamiento.
   3. Las dimensiones seleccionadas se añaden a la lista **Administrar la prioridad de las dimensiones**.
      * De forma predeterminada, estas dimensiones se agregan al final de la lista, como **Prioridad más baja** para el reagrupamiento. Sin embargo, puedes reordenarlas al igual que las dimensiones de los eventos in-app, como se ha descrito anteriormente.
4. Haz clic en **Aceptar** para guardar los cambios.
   * La lista **Dimensiones del reporte** en la pantalla principal permanece en su orden original, pero el orden revisado se ha guardado. (Haz clic de nuevo en el icono **Administrar la prioridad de las dimensiones** si deseas revisar o editar tu selección).

</Accordion>

<div id="select-metrics" />

<Accordion title="Seleccionar métricas">

Las métricas son los datos numéricos que has recopilado con respecto a un usuario de la aplicación (por ejemplo, pueden incluir ingresos, número de aperturas de la aplicación, LTV, etc.) y pueden ser cualquier campo de datos numéricos de tus fuentes que hayas categorizado como métrica.

#### **Extracción de métricas de event\_value**

Al igual que para las [dimensiones del reporte](/docs/data-clean-room-creating-in-app-event-reports#select-dimensions), puedes extraer parámetros de eventos in-app del campo **event\_value** para usarlos como métricas en tus reportes.

**Para extraer dimensiones del campo event\_value para utilizarlas en reportes de DCR:**

1. En la lista **Métricas de fuentes**, haz clic en el botón <Image alt="extract_metric_button.png" src="https://files.readme.io/93ca5970968816d452331df4ce5ff4cfb678cbb24f65eb99fe01bd3bb3016959-10755235273233.png" width="102px" /> .

   Se abre la ventana **Extraer campo de event\_value**.
2. En el cuadro **Campo de reporte**, introduce el nombre de la métrica extraída tal y como deseas que aparezca en el reporte.
3. En la lista **Parámetro de event\_value**, selecciona el parámetro de evento in-app que se debe asignar de forma predeterminada al campo de reporte (métrica) que definiste en el paso 2.
   * Los parámetros disponibles incluyen aquellos que se han configurado en los **eventos in-app seleccionados** **de las aplicaciones seleccionadas**.
4. Es posible que la asignación predeterminada difiera según la aplicación o el evento. Si este es el caso:
   1. Haz clic en el botón **Agregar excepción**
   2. Selecciona la aplicación y el evento para los que se debe asignar el campo de reporte de forma diferente.
   3. Selecciona el parámetro de evento in-app que se debe asignar al campo de reporte para esta combinación de aplicación y evento.
   4. Sigue estos pasos para tantas excepciones como desees configurar.
5. Cuando hayas terminado de configurar la asignación para la métrica extraída, haz clic en **Guardar y agregar otra** para extraer otra métrica del campo event\_value o en **Guardar** para volver a la pantalla principal.

**Para editar las métricas extraídas:**

1. En la lista **Métricas de las fuentes** o **Métricas del reporte**, coloca el cursor sobre el nombre de la métrica que deseas editar.
2. Haz clic en el botón <Image alt="more_options_button.png" src="https://files.readme.io/d52908bc376b10d60f12ec401b8ba13adf1946ca4ef27cb7a588fae33a603384-10755347815441.png" width="21px" /> que se muestra a la derecha de la métrica.
3. Selecciona **Editar campo extraído**.
4. Realiza los cambios necesarios en la asignación de nombre y/o parámetros del **Campo de reporte**.
5. Haz clic en **Guardar** para guardar tus cambios.

**Para eliminar las métricas extraídas:**

1. En la lista **Métricas de las fuentes** o **Métricas del reporte**, coloca el cursor sobre el nombre de la métrica que deseas eliminar.
2. Haz clic en el botón <Image alt="more_options_button.png" src="https://files.readme.io/d52908bc376b10d60f12ec401b8ba13adf1946ca4ef27cb7a588fae33a603384-10755347815441.png" width="21px" /> que se muestra a la derecha de la métrica.
3. Selecciona **Eliminar campo**.
   * **¡Importante!** **Precaución:** Si eliminas un campo extraído de la lista **Métricas del reporte**, se eliminará la definición del campo extraído. Si deseas quitar el campo del reporte conservando su definición, selecciona el campo y usa el comando **Quitar** en su lugar.

#### **Seleccionar métricas del reporte**

**Para seleccionar las métricas que se incluirán en el reporte, sigue estos pasos:**

1. Selecciona una o más métricas en la lista **Métricas de las fuentes** de la izquierda y usa el botón **Agregar** en el centro de la pantalla para agregarlas a la lista de **Métricas del reporte**.
   * Puedes utilizar la barra de búsqueda para buscar métricas en las listas.
2. Para cada métrica de la lista **Métricas del reporte**, selecciona si deseas que los datos se reporten como:
   * una suma de valores numéricos; o
   * un recuento de valores distintos
3. Para quitar una métrica, selecciónala en la lista **Métricas del reporte** y usa la función **Quitar** para devolverla a la lista **Métricas de las fuentes**.
4. Repite este proceso hasta que hayas agregado cada métrica que desees incluir en el reporte.

#### **[Opcional] Personalización de nombres para mostrar de las métricas**

De forma predeterminada, los nombres de las métricas se muestran en el reporte exactamente como se nombran en los datos de eventos in-app o en las fuentes personalizadas. Si lo deseas, puede personalizar los nombres de las métricas para el reporte.

**Para personalizar los nombres para mostrar de las métricas:**

1. En la lista **Métricas del reporte**, coloca el cursor sobre el nombre de la métrica cuyo nombre para mostrar deseas editar.
2. Haz clic en el botón Editar ![edit_button.png](https://files.readme.io/f4ef4722724c776ce4034ab07492a4ac80825f6f15350911c1cbb51ac4843092-10754262613649.png) que se muestra a la derecha de la métrica.
3. Cambia el nombre por el nombre para mostrar de la métrica que se utilizará en el reporte (hasta 50 caracteres).
4. Haz clic en **Aceptar** para guardar el nombre para mostrar, o en **X** para cancelar.

**Nota:** Si deseas cambiar el nombre de una **métrica extraída**, sigue los pasos para editar las métricas extraídas (arriba).

#### **[Opcional] Seleccionar los identificadores que se van a contar**

De forma predeterminada, cada fila del reporte termina con una columna que contiene un recuento de los distintos ID de AppsFlyer agrupados en los datos de esa fila.

**Si deseas agregar columnas para los recuentos distintos de otros identificadores de tus fuentes, hazlo de la siguiente manera:**

1. Selecciona uno o más identificadores en la lista **Identificadores de fuentes** de la izquierda y usa el botón **Agregar** en el centro de la pantalla para agregarlos a la lista de **Identificadores de recuento distintos**.
   * Puedes utilizar la barra de búsqueda para buscar identificadores en las listas.
2. Para quitar un identificador, selecciónalo en la lista **Identificadores de recuento distintos** y usa la función **Quitar** para devolverlo a la lista **Identificadores de fuentes**.
3. Repite este proceso hasta que hayas agregado cada identificador que desees contar en el reporte.

</Accordion>

<div id="configure-report-settings-and-save-the-report" />

<Accordion title="Configurar los ajustes del reporte y guardarlo">

#### **Programación (solo para reportes sin fuentes personalizadas)**

Los reportes sin fuentes personalizadas se ejecutan de acuerdo con la programación que definas.

**Para definir la programación del reporte:**

1. Selecciona si desea ejecutar el reporte diariamente o uno o más días a la semana.
2. Selecciona la hora a la que deseas ejecutar el reporte (la zona horaria es UTC).

> 🚧 **¡Importante!**
>
> Las opciones de programación están deshabilitadas para los reportes que utilizan fuentes personalizadas. Este tipo de reporte se ejecuta cada vez que se detectan nuevas versiones de todas las <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-creating-attribution-data-reports#fuentes-personalizadas">fuentes personalizadas que utilizas</Anchor>:
>
> * Para las fuentes ubicadas en **almacenes de datos** (BigQuery y Snowflake), DCR reconoce que se ha creado una nueva versión de una fuente cuando detecta un nuevo valor en <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-working-with-sources#table-columns">la columna `v` de la tabla de fuentes</Anchor>.
>   * **Nota:** **Importante:** Para garantizar la integridad de tu reporte, asegúrate de rellenar la tabla de la fuente con un conjunto completo de datos cada vez que se cambie el valor de la columna.
> * Para las fuentes ubicadas en **buckets de almacenamiento en la nube** (Amazon S3 y GCS), DCR reconoce que se ha creado una nueva versión de una fuente cuando detecta que <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-working-with-sources#actualización-de-las-fuentes-para-activar-el-procesamiento-de-reportes">se ha cargado una nueva versión de un archivo de fuente</Anchor> junto con el archivo \_SUCCESS que lo acompaña.
>
> AppsFlyer busca continuamente nuevas versiones de fuentes para la **fecha actual y 2 días antes**.

#### **Destino del reporte**

DCR entrega reportes a tus servicios en la nube seleccionados utilizando <Anchor target="_blank" href="/marketers/es/docs/data-locker-for-marketers">AppsFlyer Data Locker</Anchor>. Por lo tanto, especificar el destino del reporte implica seleccionar o crear una conexión de Data Locker.

* **Nota:** Recibir reportes de DCR no requiere una suscripción Premium a Data Locker. Si estás interesado en recibir otros reportes de AppsFlyer a través de Data Locker, comunícate con tu CSM o envía un correo electrónico a [hello@appsflyer.com](mailto:hello@appsflyer.com).

**Para establecer el destino del reporte y guardarlo:**

1. Selecciona de la lista de conexiones de Data Locker disponibles en tu cuenta de AppsFlyer.
   * Si no hay conexiones definidas en tu cuenta:
     * Se abrirá una nueva pestaña en tu navegador (que muestra la página de AppsFlyer Data Locker)
     * Se abrirá el cuadro de diálogo **Nueva conexión**. Sigue <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-working-with-connections#completa-la-conexión-1">estas instrucciones</Anchor> para crear la conexión.
   * Si tienes conexiones existentes pero deseas usar una nueva, haz clic en el botón ![dcr_new_connection_data_locker_button.png](https://files.readme.io/21fda59ab30e85ab4ba8b4b5920c901e8bcdedadad393a2205bb34e839f9c8db-16684568466961.png):
     * Se abrirá una nueva pestaña en tu navegador (que muestra la página de AppsFlyer Data Locker)
     * Se abrirá el cuadro de diálogo **Nueva conexión**. Sigue <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-working-with-connections#completa-la-conexión-1">estas instrucciones</Anchor> para crear la conexión.
   * Después de crear la conexión, vuelve a la pestaña DCR de tu navegador y selecciona la conexión recién creada de la lista de conexiones de Data Locker.
2. Haz clic en **Guardar** para guardar el reporte.
3. El nuevo reporte ahora se muestra en la pestaña **Reportes** de **Data Clean Room**.

</Accordion>

## Referencia

<div id="default-inapp-event-dimensions" />

<Accordion title="Dimensiones predeterminadas de eventos in-app">

Además de las dimensiones extraídas de **event\_value** y las dimensiones de tus fuentes personalizadas (si corresponde), se pueden usar las siguientes dimensiones de eventos in-app para agrupar reportes:

* media\_source *([incluido como una dimensión del reporte de forma predeterminada](#selección-de-las-dimensiones-del-reporte))*
* anuncio
* id\_adset
* ad\_type
* id\_anuncio
* adset\_name
* id\_aplicación
* version\_app
* tipo\_táctil\_atribuido
* marca
* campaña única
* id\_campaña
* channel
* Ingresos por eventos en USD
* tipo\_de\_conversión
* País
* tipo\_de\_dispositivo
* dma
* tipo\_de\_engagement
* nombre\_del\_evento
* moneda\_ingresos\_evento
* geo\_region
* is\_attributed
* palabras clave
* match\_type
* modelo
* Socio
* Identificador de origen
* id\_sitio

</Accordion>

<div id="default-inapp-event-metrics" />

<Accordion title="Métricas predeterminadas de eventos in-app">

Además de las métricas extraídas de **event\_value** y las métricas de tus fuentes personalizadas (si corresponde), las siguientes métricas de eventos in-app se pueden incluir en los reportes:

* ingresos\_evento
* event\_revenue\_u\_s\_d

</Accordion>

<div data-zendesk-anchors="creating-an-inapp-event-report=creaci%C3%B3n-de-un-reporte-de-eventos-in-app h_01HA9W7NP4CR9CVXY9CXENYSPF=creaci%C3%B3n-de-un-reporte-de-eventos-in-app h_01HA9W7NP4B55Y2SB6ADKE06JV=perform-preliminary-steps h_01HA9W7NP4A7YK5JFYNFXFY6ZJ=select-sources inapp-event-sources=fuentes-de-eventos-in-app h_01HA9W7NP4G0S2TQT9W2RK1QBA=fuentes-de-eventos-in-app custom-sources=fuentes-de-datos h_01HA9W7NP46D57Q7H8611K4KBB=fuentes-de-datos h_01HA9W7NP4K2055TXTE98HWTAW=join-sources-only-for-reports-containing-custom-sources what-is-a-key-identifier=qu%C3%A9-es-un-identificador-clave h_01HA9W7NP4WTBJ83MY73JQ2ESH=qu%C3%A9-es-un-identificador-clave h_01HA9W7NP5N8W4X8H1WRN1183Z=importante mapping-schemes-directindirect=esquemas-de-asignaci%C3%B3n-directaindirecta h_01HA9W7NP51HWA36BBP1JC3HMW=esquemas-de-asignaci%C3%B3n-directaindirecta h_01HA9W7NP5V1SV5PGF277G5P6T=ejemplo h_01HA9W7NP56M09TF9CB7FCBPBR=select-dimensions extracting-dimensions-from-event_value=extracci%C3%B3n-de-dimensiones-de-event_value h_01HA9W7NP5BV7GJXMEMS57HNJ9=extracci%C3%B3n-de-dimensiones-de-event_value selecting-report-dimensions=selecci%C3%B3n-de-las-dimensiones-del-reporte h_01HA9W7NP5S6EWDE38Q6T42QEB=selecci%C3%B3n-de-las-dimensiones-del-reporte %5Boptional%5D-customizing-dimension-display-names=opcional-personalizaci%C3%B3n-de-nombres-para-mostrar-de-las-dimensiones h_01HA9W7NP5YC8E3B05GV7J1Z5V=opcional-personalizaci%C3%B3n-de-nombres-para-mostrar-de-las-dimensiones preserving-privacy-while-grouping-by-dimension-regrouping=preservaci%C3%B3n-de-la-privacidad-mientras-se-agrupa-por-dimensi%C3%B3n-reagrupaci%C3%B3n h_01HA9W7NP5XJGK4CXNHK02NYT4=preservaci%C3%B3n-de-la-privacidad-mientras-se-agrupa-por-dimensi%C3%B3n-reagrupaci%C3%B3n h_01HA9W7NP596RGHA1BES64GSK1=ejemplo-de-reagrupamiento %5Boptional%5D-managing-dimension-priority=opcional-administraci%C3%B3n-de-la-prioridad-de-las-dimensiones h_01HA9W7NP5781HV31T5DAYSMMT=opcional-administraci%C3%B3n-de-la-prioridad-de-las-dimensiones h_01HA9W7NP6WCSRSH157P78QEQF=select-metrics extracting-metrics-from-event_value=extracci%C3%B3n-de-m%C3%A9tricas-de-event_value h_01HA9W7NP6JEXE67A935BJ93AQ=extracci%C3%B3n-de-m%C3%A9tricas-de-event_value select-report-metrics=seleccionar-m%C3%A9tricas-del-reporte h_01HA9W7NP6EF23ZDGZHDKVTS7V=seleccionar-m%C3%A9tricas-del-reporte %5Boptional%5D-customizing-metric-display-names=opcional-personalizaci%C3%B3n-de-nombres-para-mostrar-de-las-m%C3%A9tricas h_01HA9W7NP6X584YAXT030A6BEY=opcional-personalizaci%C3%B3n-de-nombres-para-mostrar-de-las-m%C3%A9tricas %5Boptional%5D-select-identifiers-to-count=opcional-seleccionar-los-identificadores-que-se-van-a-contar h_01HA9W7NP6YETQ1ND0K8XZTZZ0=opcional-seleccionar-los-identificadores-que-se-van-a-contar h_01HA9W7NP6ZH3KRN7YNWCPFZC9=configure-report-settings-and-save-the-report schedule-only-for-reports-without-custom-sources=programaci%C3%B3n-solo-para-reportes-sin-fuentes-personalizadas h_01HA9W7NP62DCR2SWD8X4M61R7=programaci%C3%B3n-solo-para-reportes-sin-fuentes-personalizadas h_01HA9W7NP6XQE1MN0J08FE89V4=importante-1 report-destination=destino-del-reporte h_01HA9W7NP6BQYAF3RMZSW747HH=destino-del-reporte reference=referencia h_01HA9W7NP6BS0TE332GNPTW9M1=referencia h_01HA9W7NP606HF0MSPQ4S09YRS=default-inapp-event-dimensions h_01HA9W7NP6A1N25KQ947J3EJW3=default-inapp-event-metrics" />
