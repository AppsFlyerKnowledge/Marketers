---
title: 'Data Clean Room: creación de reportes de datos de atribución'
metadata:
  keywords:
    - Premium Feature
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-inbar-agassi
    - Marketers
    - Data Clean Room
  created_at: '2022-09-11T10:42:43Z'
  edited_at: '2026-08-12T11:52:32Z'
  id: 9035047905297
  locale: es
  section: Data Clean Room
  section_id: 4591191779217
  url: https://support.appsflyer.com/hc/es/articles/9035047905297
---
> **En resumen:** crea reportes de datos de atribución para hacer coincidir los datos a nivel de usuario de los eventos de instalación o retargeting con los datos de tus sistemas.

## Creación de un reporte de datos de atribución

**Para crear un reporte de datos de atribución, sigue los pasos que se detallan en las pestañas siguientes.**

**Nota:** Estos pasos se dividen en pestañas para facilitar la lectura. Se deben completar todos los pasos para crear el reporte.

<div id="perform-preliminary-steps" />

<Accordion title="Realizar los pasos preliminares">

1. Ve a la pestaña **Reportes** de **DCR**.
2. Haz clic en el botón **+ Nuevo reporte**.
3. Selecciona **Datos de atribución** como tipo de datos de origen y, a continuación, haz clic en **Siguiente** en la esquina inferior derecha de la pantalla.
4. Introduce un nombre para el reporte.
   * Puede ser cualquier nombre que te ayude a identificar el reporte en la plataforma DCR.
   * **Nota:** **Importante:** Asegúrate de que el nombre del reporte sea diferente de todos los demás reportes de tu cuenta, de lo contrario no podrás [guardar el reporte](/docs/data-clean-room-creating-attribution-data-reports#set-the-report-destination-and-save-the-report).
   * Requisitos del nombre del reporte:
     * Longitud: de 2 a 80 caracteres
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

Especifica los datos que se van a utilizar para el reporte:

#### **Datos de atribución:**

* **Aplicaciones:** selecciona una o más de las aplicaciones en tu cuenta de AppsFlyer.
* **Tipos de atribución:** Selecciona uno o más tipos de datos de atribución para usarlos en el reporte:

| Instalaciones | Una instalación se registra cuando un usuario descarga, instala e inicia una aplicación móvil. |
| --- | --- |
| Reinstalaciones | Una reinstalación se registra cuando un usuario instala una aplicación, luego la desinstala y la vuelve a instalar durante la ventana de reatribución.<ul><li>**Nota:** La duración de la ventana de reatribución se establece en Configuración > Configuración de la aplicación.</li></ul> |
| Reengagements | Un reengagement se registra cuando un usuario inactivo de una aplicación específica interactúa con una campaña de retargeting para la aplicación y posteriormente la abre. |
| Reatribuciones | Una reatribución se registra cuando un antiguo usuario de una aplicación específica (que la había desinstalado) participa en una campaña de retargeting para la aplicación y, posteriormente, la reinstala. |
| Instalaciones orgánicas | Las instalaciones orgánicas son aquellas que no se atribuyen a una fuente multimedia específica.<ul><li>**Nota:** Incluir las instalaciones orgánicas en tu reporte puede aumentar considerablemente el número de filas escaneadas.</li></ul> |

* **Periodo de tiempo:** Selecciona el número de días de datos históricos en los que deseas que el DCR busque eventos de atribución que coincidan con tus eventos de origen personalizados (de 1 a 180 días).

#### **Fuentes personalizadas**

Al definir la estructura del reporte, puede elegir usar datos de cualquiera de las <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-working-with-sources">fuentes personalizadas que hayas configurado</Anchor>.

</Accordion>

<div id="join-sources" />

<Accordion title="Unirse a fuentes">

Para hacer coincidir los datos entre las fuentes, cada una de las fuentes **personalizadas** utilizadas en el reporte debe incluir un <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-setting-up-cloud-services">identificador</Anchor> asignado a un **identificador clave** en los datos de atribución.

#### **¿Qué es un identificador clave?**

Puedes asignarlos a cualquiera de estos identificadores de datos de atribución como identificadores **clave**:

* un identificador único de la aplicación generado por AppsFlyer en la instalación:
  * Este ID aparece en todos los eventos registrados por AppsFlyer.
  * Se genera un nuevo ID de AppsFlyer si se elimina una aplicación y luego se vuelve a instalar.
* **ID de usuario de cliente (CUID):** un identificador de usuario único, generalmente generado y establecido por el propietario de la aplicación en el momento del registro del usuario.
  * El uso de CUID para asignar datos requiere que la aplicación esté configurada para <Anchor target="_blank" href="/marketers/es/docs/customer-user-id-field-cuid">enviar el CUID a AppsFlyer</Anchor> a través del SDK o de la API de servidor a servidor (S2S).

> 🚧 **Importante:**
>
> No todas las fuentes de medios permiten la coincidencia mediante el CUID. Se recomienda encarecidamente utilizar el ID de AppsFlyer.

#### **Esquemas de asignación (directa/indirecta)**

Si el reporte usa más de una fuente personalizada, solo es necesario asignar una de ellas **directamente** a un identificador de clave de datos de atribución. Se pueden asignar otras fuentes personalizadas **directa o indirectamente**, como se ilustra en el siguiente ejemplo:

> 📄 **Ejemplo**
>
> ![dcr_mapping_identifiers_attribution_data.png](https://files.readme.io/18d1ddd8305f790dc621f871695b8cfb30f5e5a5d758c219e76ec7822ec18f2f-9969690360849.png)
>
> En el escenario que se muestra arriba:
>
> * El identificador de fuente personalizada n.º 1, **AF**, se asigna directamente al identificador clave de datos de atribución **af\_id**.
> * La fuente personalizada n.º 2 se asigna indirectamente: **user\_code** --> **AF** --> **af\_id**.
> * La fuente personalizada n.º 3 se asigna indirectamente (a través de una cadena más larga):
>   **user\_id** --> **user\_code** --> **AF** --> **af\_id.**
> * El identificador de fuente personalizada n.º 4, **AF**, se asigna directamente al identificador clave de datos de atribución **af\_id**.
>   * Ten en cuenta que podría haberse asignado indirectamente en su lugar (a través del identificador de fuente personalizada n.º 3 **user\_id**), pero cualquiera de las dos opciones funciona bien.
>
> ✓ Este esquema de mapeo funciona para hacer coincidir los datos entre todas las fuentes, ya que cada fuente personalizada se asigna directa o indirectamente al identificador de clave de datos de atribución **af\_id.**

</Accordion>

<div id="determine-treatment-of-multiple-matching-events" />

<Accordion title="Determinar el tratamiento de varios eventos coincidentes">

> 📘 **Nota:**
>
> Si los tipos de atribución seleccionados para este reporte **incluyen solo instalaciones u instalaciones orgánicas, esta sección es** irrelevante. Ve a **[Seleccionar dimensiones](/docs/data-clean-room-creating-attribution-data-reports#select-dimensions).**

**reengagements o reatribuciones,** es posible que los datos de atribución incluyan más de un evento durante el período seleccionado con el mismo identificador clave. Cuando este sea el caso, debes indicar al DCR qué eventos coincidentes debe incluir en el reporte.

#### **Coincidir con todos los eventos**

El método de coincidencia más completo permite que tu reporte incluya todos los eventos coincidentes. Para lograr este resultado, debes asignar un identificador de una de las fuentes personalizadas del reporte al identificador de datos de atribución **install\_time**.

* El identificador del código fuente que está asignado a install\_time debe tener el siguiente formato: **aaaa-mm-dd hh:mm:ss.**
* **Nota:** Aunque el nombre del identificador de datos de atribución es install\_time, en realidad significa **hora del evento** cuando se hace referencia a los eventos de reinstalación, reengagement o reatribución.

#### **Emparejar un solo evento**

Si los tipos de atribución que seleccionas para tu reporte incluyen reinstalaciones, reengagements o reatribuciones, pero no asignas un identificador a **install\_time,** debes elegir usar el **último** o el **primer** evento coincidente de tu reporte.

El comportamiento de coincidencia de un solo evento difiere cuando la fuente de datos de atribución de AppsFlyer se usa sola frente a cuando se combina con fuentes personalizadas.

* Cuando la fuente de datos de atribución se usa sola, AppsFlyer selecciona el evento coincidente con el `event_time` más reciente dentro del período de tiempo que coincide con un identificador clave específico.
* Cuando la fuente de datos de atribución se combina con fuentes personalizadas, debes elegir si quieres usar el evento coincidente **último** o **primero** en tu reporte.
  * **Último evento:** el evento de atribución incluido en el reporte es el último evento (cronológicamente) del período que coincide con un identificador clave específico.
  * **Primer evento:** El evento de atribución incluido en el reporte es el primer evento (cronológicamente) del período que coincide con un identificador clave específico.

Haz esta selección en función del evento que consideres más relevante para la información que deseas obtener del reporte.

> 📘 **Nota**
>
> En caso de registros duplicados, DCR elimina los duplicados de los registros con el mismo `appsflyer_id` y selecciona el evento más reciente en función de `event_time`.

</Accordion>

<div id="select-dimensions" />

<Accordion title="Seleccionar las dimensiones">

Recuerda que los datos a nivel de usuario no pueden ser reportados por DCR. En su lugar, te proporciona la información necesaria para la toma de decisiones agregando (o agrupando) los datos por las dimensiones que elijas.

Por lo general, una dimensión es un atributo por el que se clasifican los usuarios de la aplicación (por ejemplo, geolocalización, fecha de instalación, campaña, etc.).

#### **Selección de las dimensiones del reporte**

Las dimensiones del reporte de datos de atribución pueden incluir:

* Cualquier [dimensión de datos de atribución disponible](/docs/data-clean-room-creating-attribution-data-reports#available-attribution-data-dimensions)
* Cualquier campo de las fuentes personalizadas del reporte que se haya <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-working-with-sources#3-define-the-source-structure">clasificado como dimensión</Anchor>

**Para seleccionar las dimensiones que se incluirán en el reporte:**

1. Selecciona una o más dimensiones en la lista **Dimensiones de las fuentes** de la izquierda y usa el botón **Agregar** en el centro de la pantalla para agregarlas a la lista de **Dimensiones del reporte**.  
   * Puedes usar la barra de búsqueda para buscar dimensiones en las listas.
2. Para quitar una dimensión, selecciónala en la lista **Dimensiones del reporte** y usa la función **Quitar** para devolverla a la lista **Dimensiones de las fuentes**.
3. Repite este proceso hasta que hayas agregado cada dimensión que desees incluir en el reporte.

**Nota:** De forma predeterminada, todos los reportes se agrupan según la dimensión de datos de atribución **media\_source.** Si no deseas utilizar esta dimensión en tu reporte, puedes eliminarla de la lista de **dimensiones del reporte**.

#### **[Opcional] Personalización de nombres para mostrar de las dimensiones**

De forma predeterminada, los nombres de las dimensiones se muestran en el reporte exactamente como aparecen en los datos de atribución o en las fuentes personalizadas. Si lo deseas, puedes personalizar los nombres de las dimensiones para el reporte.

**Para personalizar los nombres de visualización de las dimensiones:**

1. En la lista **Dimensiones del reporte**, coloca el cursor sobre el nombre de la dimensión cuyo nombre para mostrar deseas editar.
2. Haz clic en el botón Editar ![edit_button.png](https://files.readme.io/4c3822661beac49fad247c7f5958a535e46031238e975a5323a5550722c89c8a-10753875375377.png) que se muestra a la derecha de la dimensión.
3. Cambia el nombre por el nombre para mostrar de la dimensión que se utilizará en el reporte (hasta 50 caracteres).
4. Haz clic en **Aceptar** para guardar el nombre para mostrar, o en **X** para cancelar.

#### Preservación de la privacidad mientras se agrupa por dimensión (reagrupación)

En función del tamaño del conjunto de datos, el número de dimensiones que elijas y otros factores, es posible que un reporte incluya uno o varios grupos que contengan muy pocos usuarios para permitir la generación de reportes. Si los datos se reportaran de esta manera, se infringirían las restricciones contra el suministro de datos a nivel de usuario.

* **Nota:** **Importante:** La cantidad mínima de usuarios requerida para permitir la presentación de reportes varía según la fuente de medios.

Sin embargo, en lugar de eliminar u ocultar los datos del reporte por completo, DCR utiliza un **Mecanismo de reagrupamiento** para proporcionar tantos detalles como sea posible mientras se mantiene la privacidad del usuario.

> 📄 **Ejemplo de reagrupamiento**
>
> Supongamos que has configurado un reporte de acuerdo con las siguientes dimensiones (en orden):
>
> * **Dimensiones de los datos de atribución:**
>   * fuente de medios
>   * campaña
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
> | medios  <br />fuente | campaña | conjunto de anuncios  <br />conjunto de anuncios | anuncio  <br />ID | usuario  <br />tipo | rev  <br />D0 | ingresos  <br />D7 | cuenta | ¿Reportable? |
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
> Según la lógica de reagrupamiento, el DCR primero «elimina» la última dimensión de datos de atribución de la lista (en este caso, **ad\_id).** A continuación, vuelve a analizar los datos para ver qué filas se pueden reportar.
>
> **Después de reagrupar**
>
> Después de aplicar la lógica de reagrupamiento, el reporte aparece de la siguiente manera:
>
>
>
> | medios  <br />fuente | campaña | conjunto de anuncios  <br />conjunto de anuncios | anuncio  <br />ID | usuario  <br />tipo | rev  <br />D0 | ingresos  <br />D7 | cuenta | ¿Reportable? |
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
> * La dimensión que se eliminó ahora se reporta como RESTRINGIDO.
> * Si todavía hubiera habido filas no reportables (menos de **y** usuarios), DCR continuaría analizando los datos de forma iterativa, eliminando una dimensión tras otra hasta que:
>   * puedas reportar todas las filas; o
>   * se queda sin dimensiones de datos de atribución para eliminar
>
> **Nota:** De forma predeterminada, el DCR aplica la reagrupación solo a las dimensiones de los [**datos de atribución (no a las dimensiones**](/docs/data-clean-room-creating-attribution-data-reports#available-attribution-data-dimensions) de origen personalizadas). Si los datos agrupados por una dimensión de datos de atribución dan como resultado una fila con menos de **y** usuarios, los datos de esa fila se indicarán como RESTRINGIDOS.
>
> * *Consulta a continuación una opción avanzada que puedes usar para aplicar también el reagrupamiento a las dimensiones de fuentes personalizadas.*

#### **[Opcional] Administración de la prioridad de las dimensiones**

De forma predeterminada, las dimensiones de los datos de atribución se eliminan en orden inverso al orden en que aparecen en la lista de **dimensiones del reporte**. Sin embargo, puedes modificar la secuencia predeterminada o aplicar la reagrupación a las dimensiones de origen personalizadas seleccionadas para conservar las dimensiones más importantes para usted.

**Para cambiar el orden en el que se eliminan las dimensiones:**

1. Haz clic en el botón **Administrar la prioridad de las dimensiones**.
2. Selecciona una dimensión y arrástrala a la posición deseada en la lista (o usa los botones de flecha de la derecha para moverla).
   * La dimensión etiquetada como **Máxima prioridad** (en la parte superior de la lista) significa que es la última en ser eliminada si se requiere reagrupamiento.
3. [Opcional] Para aplicar la reagrupación a las dimensiones de origen personalizadas:
   1. Haz clic en **Usar opciones avanzadas para refinar el reagrupamiento**
   2. Selecciona las dimensiones de fuentes personalizadas a las que deseas aplicar el reagrupamiento.
   3. Las dimensiones seleccionadas se añaden a la lista **Administrar la prioridad de las dimensiones**.
      * De forma predeterminada, estas dimensiones se agregan al final de la lista, como **Prioridad más baja** para el reagrupamiento. Sin embargo, puedes reordenarlos igual que las dimensiones de los datos de atribución, tal y como se describe anteriormente.
4. Haz clic en **Aceptar** para guardar los cambios.
   * La lista **Dimensiones del reporte** en la pantalla principal permanece en su orden original, pero el orden revisado se ha guardado. (Haz clic de nuevo en el icono **Administrar la prioridad de las dimensiones** si deseas revisar o editar tu selección).

</Accordion>

<div id="select-metrics" />

<Accordion title="Seleccionar métricas">

Las métricas son los datos numéricos que has recopilado con respecto a un usuario de la aplicación (por ejemplo, pueden incluir ingresos, número de aperturas de la aplicación, LTV, etc.) y pueden ser cualquier campo de datos **numéricos** de tus fuentes que hayas categorizado como métrica.

**Para seleccionar las métricas que se incluirán en el reporte, sigue estos pasos:**

1. Selecciona una o más métricas en la lista **Métricas de las fuentes** de la izquierda y usa el botón **Agregar** en el centro de la pantalla para agregarlas a la lista de **Métricas del reporte**.
   * Puedes utilizar la barra de búsqueda para buscar métricas en las listas.
2. Para cada métrica de la lista **Métricas del reporte**, selecciona si deseas que los datos se reporten como:
   * una suma de valores numéricos; o
   * un recuento de valores distintos
3. Para quitar una métrica, selecciónala en la lista **Métricas del reporte** y usa la función **Quitar** para devolverla a la lista **Métricas de las fuentes**.
4. Repite este proceso hasta que hayas agregado cada métrica que quieras incluir en el reporte.

#### **[Opcional] Personalización de nombres para mostrar de las métricas**

De forma predeterminada, los nombres de las métricas se muestran en tu reporte exactamente como aparecen en los datos de atribución o en tus fuentes personalizadas. Si lo deseas, puedes personalizar los nombres de las métricas para el reporte.

**Para personalizar los nombres para mostrar de las métricas:**

1. En la lista **Métricas del reporte**, coloca el cursor sobre el nombre de la métrica cuyo nombre para mostrar deseas editar.
2. Haz clic en el botón Editar ![edit_button.png](https://files.readme.io/4c3822661beac49fad247c7f5958a535e46031238e975a5323a5550722c89c8a-10753875375377.png) que se muestra a la derecha de la métrica.
3. Cambia el nombre por el nombre para mostrar de la métrica que se utilizará en el reporte (hasta 50 caracteres).
4. Haz clic en **Aceptar** para guardar el nombre para mostrar, o en **X** para cancelar.

#### **[Opcional] Seleccionar los identificadores que se van a contar**

De forma predeterminada, cada fila del reporte termina con una columna que contiene un recuento de los distintos ID de AppsFlyer agrupados en los datos de esa fila.

**Si deseas agregar columnas para los recuentos distintos de otros identificadores de tus fuentes, hazlo de la siguiente manera:**

1. Selecciona uno o más identificadores en la lista **Identificadores de fuentes** de la izquierda y usa el botón **Agregar** en el centro de la pantalla para agregarlos a la lista de **Identificadores de recuento distintos**.
   * Puedes utilizar la barra de búsqueda para buscar identificadores en las listas.
2. Para quitar un identificador, selecciónalo en la lista **Identificadores de recuento distintos** y usa la función **Quitar** para devolverlo a la lista **Identificadores de fuentes**.
3. Repite este proceso hasta que hayas agregado cada identificador que desees contar en el reporte.

</Accordion>

<div id="set-the-report-destination-and-save-the-report" />

<Accordion title="Para establecer el destino del reporte y guardarlo:">

DCR entrega reportes a tus servicios en la nube seleccionados utilizando <Anchor target="_blank" href="/marketers/es/docs/data-locker-for-marketers">AppsFlyer Data Locker</Anchor>. Por lo tanto, especificar el destino del reporte implica seleccionar o crear una conexión de Data Locker.

* **Nota:** Recibir reportes de DCR no requiere una suscripción Premium a Data Locker. Si estás interesado en recibir otros reportes de AppsFlyer a través de Data Locker, comunícate con tu CSM o envía un correo electrónico a [hello@appsflyer.com](mailto:hello@appsflyer.com).

**Para establecer el destino del reporte y guardarlo:**

1. Selecciona de la lista de conexiones de Data Locker disponibles en tu cuenta de AppsFlyer.
   * Si no hay conexiones definidas en tu cuenta:
     * Se abrirá una nueva pestaña en tu navegador (que muestra la página de AppsFlyer Data Locker)
     * Se abrirá el cuadro de diálogo **Nueva conexión**. Sigue <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-working-with-connections#completa-la-conexión-1">estas instrucciones</Anchor> para crear la conexión.
   * Si tienes conexiones existentes pero quieres usar una nueva, haz clic en ![dcr_new_connection_data_locker_button.png](https://files.readme.io/9850a4b8ea4f40f6320903c545c51add7b90207538a27c83a3b02a41197ba567-14995870859281.png) botón:
     * Se abrirá una nueva pestaña en tu navegador (que muestra la página de AppsFlyer Data Locker)
     * Se abrirá el cuadro de diálogo **Nueva conexión**. Sigue <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-working-with-connections#completa-la-conexión-1">estas instrucciones</Anchor> para crear la conexión.
   * Después de crear la conexión, vuelve a la pestaña DCR de tu navegador y selecciona la conexión recién creada de la lista de conexiones de Data Locker.
2. Haz clic en **Guardar** para guardar el reporte.
3. El nuevo reporte ahora se muestra en la pestaña **Reportes** de **Data Clean Room**.

</Accordion>

## ¿Cuándo se publica el reporte?

Una vez que hayas creado y guardado un reporte, se ejecuta cada vez que se detectan nuevas versiones de todas [las fuentes personalizadas que utiliza](/docs/data-clean-room-creating-attribution-data-reports#fuentes-personalizadas):

* Para las fuentes ubicadas en **almacenes de datos** (BigQuery y Snowflake), DCR reconoce que se ha creado una nueva versión de una fuente cuando detecta un nuevo valor en <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-working-with-sources#table-columns">la columna `v` de la tabla de fuentes</Anchor>.
  * **Nota:** **Importante:** Para garantizar la integridad de tu reporte, asegúrate de rellenar la tabla de la fuente con un conjunto completo de datos cada vez que se cambie el valor de la columna.
* Para las fuentes ubicadas en **buckets de almacenamiento en la nube** (Amazon S3 y GCS), DCR reconoce que se ha creado una nueva versión de una fuente cuando detecta que <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-working-with-sources#actualización-de-las-fuentes-para-activar-el-procesamiento-de-reportes">se ha cargado una nueva versión de un archivo de fuente</Anchor> junto con el archivo \_SUCCESS que lo acompaña.

AppsFlyer busca continuamente nuevas versiones de fuentes para la **fecha actual y 2 días antes**.

## Referencia

<div id="available-attribution-data-dimensions" />

<Accordion title="Dimensiones de datos de atribución disponibles">

Además de las dimensiones de tus fuentes personalizadas, puedes usar las siguientes dimensiones de datos de atribución para agrupar reportes:

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
* campaña
* id\_campaña
* canal
* ciudad
* contributor\_1\_campaign¹
* contributor\_1\_engagement\_type¹
* contributor\_1\_match\_type¹
* contributor\_1\_media\_source¹
* contributor\_1\_partner¹
* contributor\_1\_touch\_type¹
* contributor\_2\_campaign¹
* contributor\_2\_engagement\_type¹
* contributor\_2\_match\_type¹
* contributor\_2\_media\_source¹
* contributor\_2\_partner¹
* contributor\_2\_touch\_type¹
* contributor\_3\_campaign¹
* contributor\_3\_engagement\_type¹
* contributor\_3\_match\_type¹
* contributor\_3\_media\_source¹
* contributor\_3\_partner¹
* contributor\_3\_touch\_type¹
* tipo\_de\_conversión
* país
* id\_cliente
* tipo\_de\_dispositivo
* dma
* tipo\_de\_engagement
* geo\_region
* palabras clave
* match\_type
* fuente\_de\_medios
* modelo
* original\_url
* Socio
* plataforma
* id\_sitio

¹ *En el caso de reengagements y reatribuciones, los reportes mostrarán estos campos vacíos*.

</Accordion>

<div data-zendesk-anchors="creating-an-attribution-data-report=creaci%C3%B3n-de-un-reporte-de-datos-de-atribuci%C3%B3n h_01HA9W4BCJSS2803JHV9K5KVP8=creaci%C3%B3n-de-un-reporte-de-datos-de-atribuci%C3%B3n h_01HA9W4BCJX9PJ2E4ADDC58GJ1=perform-preliminary-steps h_01HA9W4BCJNB64K3GZAKM7G0SS=select-sources attribution-data-sources=datos-de-atribuci%C3%B3n h_01HA9W4BCJD51WM7504F94009R=datos-de-atribuci%C3%B3n custom-sources=fuentes-personalizadas h_01HA9W4BCJNRBD1NSWAH92B85V=fuentes-personalizadas h_01HA9W4BCJW56NG637AZNP0DW0=join-sources what-is-a-key-identifier=qu%C3%A9-es-un-identificador-clave h_01HA9W4BCJ6A5EVFVR6G2SHEQD=qu%C3%A9-es-un-identificador-clave h_01HA9W4BCJ2GAZ96FHNN3HP6BY=importante mapping-schemes-directindirect=esquemas-de-asignaci%C3%B3n-directaindirecta h_01HA9W4BCJ6ZT4DSE3J5364D2C=esquemas-de-asignaci%C3%B3n-directaindirecta h_01HA9W4BCJKA8AWQGEHGQ5JT4P=ejemplo h_01HA9W4BCJ6ZM47HQMARQ50ZQ1=determine-treatment-of-multiple-matching-events h_01HA9W4BCJE9ABACTWWTNJXVVQ=nota matching-all-events=coincidir-con-todos-los-eventos h_01HA9W4BCJ6FPCNP8K8D2CR1ST=coincidir-con-todos-los-eventos matching-a-single-event=emparejar-un-solo-evento h_01HA9W4BCJ99Z4A16N05799VZS=emparejar-un-solo-evento 01JFZ2GJTJ566AWS3Z3KTWNMVE=nota-1 h_01HA9W4BCKDVYTG08M2CWBWYC3=select-dimensions selecting-report-dimensions=selecci%C3%B3n-de-las-dimensiones-del-reporte h_01HA9W4BCKWCDWB4W0HZM4Z6E7=selecci%C3%B3n-de-las-dimensiones-del-reporte %5Boptional%5D-customizing-dimension-display-names=opcional-personalizaci%C3%B3n-de-nombres-para-mostrar-de-las-dimensiones h_01HA9W4BCKEW1Z25ZXS9EXZYSA=opcional-personalizaci%C3%B3n-de-nombres-para-mostrar-de-las-dimensiones preserving-privacy-while-grouping-by-dimension-regrouping=preservaci%C3%B3n-de-la-privacidad-mientras-se-agrupa-por-dimensi%C3%B3n-reagrupaci%C3%B3n h_01HA9W4BCKA4248PEYNWZS87EW=preservaci%C3%B3n-de-la-privacidad-mientras-se-agrupa-por-dimensi%C3%B3n-reagrupaci%C3%B3n regrouping-example=ejemplo-de-reagrupamiento h_01HA9W4BCK41W87486KG4RAAX8=ejemplo-de-reagrupamiento %5Boptional%5D-managing-dimension-priority=opcional-administraci%C3%B3n-de-la-prioridad-de-las-dimensiones h_01HA9W4BCKHABH7K80DKAQDDTR=opcional-administraci%C3%B3n-de-la-prioridad-de-las-dimensiones h_01HA9W4BCK1G0A2HTYRDQTMF5B=select-metrics %5Boptional%5D-customizing-metric-display-names=opcional-personalizaci%C3%B3n-de-nombres-para-mostrar-de-las-m%C3%A9tricas h_01HA9W4BCKZTAP4AWMNJKEKX2E=opcional-personalizaci%C3%B3n-de-nombres-para-mostrar-de-las-m%C3%A9tricas %5Boptional%5D-select-identifiers-to-count=opcional-seleccionar-los-identificadores-que-se-van-a-contar h_01HA9W4BCK5Y97RFYEMT24BABV=opcional-seleccionar-los-identificadores-que-se-van-a-contar h_01HA9W4BCKE1P7TBJANN0PD03D=set-the-report-destination-and-save-the-report when-does-the-report-run=cu%C3%A1ndo-se-publica-el-reporte h_01HA9W4BCK3GX1KMVAXN5ZKA3A=cu%C3%A1ndo-se-publica-el-reporte reference=referencia h_01HA9W4BCK0VHS90ZXX00BF80N=referencia h_01HA9W4BCMAYC661HFNRY3HWY2=available-attribution-data-dimensions" />
