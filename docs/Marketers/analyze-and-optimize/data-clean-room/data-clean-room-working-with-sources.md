---
title: 'Data Clean Room: trabajar con fuentes'
metadata:
  keywords:
    - Advertisers
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
  created_at: '2022-03-27T10:58:23Z'
  edited_at: '2026-08-22T00:06:02Z'
  id: 5041487011601
  locale: es
  section: Data Clean Room
  section_id: 4591191779217
  url: https://support.appsflyer.com/hc/es/articles/5041487011601
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **At a glance:** Configura las fuentes de datos personalizadas que compartes con Data Clean Room (DCR) para emparejarlas con los datos de atribución y crear reportes de DCR.

## Introducción

Muchos reportes de DCR están diseñados para emparejar tus **datos de atribución** con los datos de tus **fuentes personalizadas.** Este artículo contiene todo lo que necesitas saber para trabajar con tus fuentes personalizadas, incluyendo cómo:

* [Formatear los datos de las fuentes](/docs/data-clean-room-working-with-sources#requisitos-de-los-datos-de-las-fuentes)
* [Crear la fuente](/docs/data-clean-room-working-with-sources#crear-una-fuente) dentro de DCR
  * [Asignar un nombre a la fuente](/docs/data-clean-room-working-with-sources#1-name-the-source)
  * [Especificar la ubicación](/docs/data-clean-room-working-with-sources#2-specify-the-source-location) desde la que DCR recuperará los datos de las fuentes
  * [Definir la estructura](/docs/data-clean-room-working-with-sources#3-define-the-source-structure) de la fuente (etiquetando los campos como métricas, dimensiones e identificadores)
  * [Guardar la fuente](/docs/data-clean-room-working-with-sources#4-save-the-source)
* [Actualiza los datos de origen](/docs/data-clean-room-working-with-sources#actualización-de-las-fuentes-para-activar-el-procesamiento-de-reportes) de forma regular para activar el procesamiento de reportes
* [Trabajar con fuentes existentes](/docs/data-clean-room-working-with-sources#trabajar-con-fuentes-existentes)

> 🚧 **Important**
>
> **Antes de comenzar**
>
> Antes de crear fuentes personalizadas, primero debes hacer lo siguiente:
>
> * [Obligatorio] <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-setting-up-cloud-services">Configura los servicios en la nube</Anchor> desde los que DCR recuperará los datos. Se admiten dos tipos de servicios en la nube:
>   * **Almacenes de datos:** BigQuery y Snowflake
>   * **Buckets de almacenamiento en la nube:** Amazon S3 (AWS) y GCS
> * [Opcional] <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-working-with-connections#crear-conexiones-entrantes">Crea conexiones entrantes</Anchor> en la plataforma AppsFlyer para conectar estos servicios en la nube a DCR.
>   * Si estas conexiones no se configuraron previamente, se te pedirá que las establezcas durante la creación de la fuente.

## Requisitos de los datos de las fuentes

Las fuentes deben cumplir estos requisitos para evitar errores en la creación de fuentes y en el procesamiento de reportes.

<div id="data-format" />

<Accordion title="Formato de los datos (relevante para todas las fuentes)">

Los datos dentro de las fuentes deben cumplir estos requisitos:

* **Fecha y hora:**
  * **Formato:** aaaa-MMM-dd hh:mm:ss (*por ejemplo*, `2023-APR-18 15:30:35`)
  * **Zona horaria:** UTC
* **Números:** máximo 2 dígitos después del punto decimal
* **Longitud de la cadena:** máximo 256 caracteres
* **Limitaciones de caracteres:**
  * **Para los nombres de campo (encabezado de columna):** sin espacios ni caracteres especiales
  * **Todos los demás datos:** sin limitaciones (todos los caracteres son válidos)

</Accordion>

<div id="table-columns" />

<Accordion title="Columnas de la tabla (relevantes solo para las fuentes en almacenes de datos)">

Además de los datos compartidos para su procesamiento, las tablas de fuentes en BigQuery o Snowflake deben incluir 2 columnas adicionales, una para la **fecha** y otra para la **versión:**

* **Fecha:**
  * **Encabezado de columna:** `dt`
  * **Tipo de columna:** fecha
  * **Formato de los datos:** aaaa-mm-dd (*por ejemplo*, `2023-04-18`)
  * **Adicional:** las tablas de BigQuery deben estar <Anchor target="_blank" href="https://cloud.google.com/bigquery/docs/partitioned-tables">particionadas</Anchor> por esta columna
* **Versión:**
  * **Encabezado de columna:** `v`
  * **Tipo de columna:** cadena
  * **Formato de los datos:** número (por ejemplo, `1`, `2`, `3`, `10`)
  * **Nota:** **Importante:** Una nueva versión de un reporte se activa cada vez que DCR detecta un nuevo valor en esta columna. Para garantizar la integridad de tu reporte, asegúrate de rellenar la tabla de la fuente con un conjunto completo de datos cada vez que se cambie el valor de la columna.

</Accordion>

<div id="file-format" />

<Accordion title="Nombre y formato del archivo (relevante solo para las fuentes en los buckets de almacenamiento en la nube)">

Los archivos de fuentes almacenados en Amazon S3 o GCS deben cumplir los siguientes requisitos de nombre y formato de archivo:

* El nombre del archivo debe cumplir los <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-setting-up-cloud-services#dcr-naming-requirements">requisitos de nomenclatura de DCR</Anchor>
* Formato CSV o GZIP
  * El archivo que se encuentra bajo la compresión GZIP debe ser un archivo CSV.
* Número de archivos de fuentes de datos por [carpeta de datos](/docs/data-clean-room-working-with-sources#nested-subfolders-for-each-date-and-version):
  * **CSV:** máximo 1
  * **GZIP:** máximo 1 archivo de una sola parte. Los archivos GZIP de varias partes son compatibles cuando se denominan de la siguiente manera: `filename_part01.gzip`, `filename_part02.gzip`, etc.

</Accordion>

## Crear una fuente

El proceso de creación de una fuente consiste en **todos los pasos descritos a continuación.** Se separan en pestañas simplemente para facilitar la lectura.

**Sigue estos pasos para crear una fuente:**

<div id="1-name-the-source" />

<Accordion title="#1: Asignar un nombre a la fuente">

1. Ve a la pestaña **Fuentes** de **Data Clean Room.**
2. Haz clic en el botón **+ Nueva fuente**.  
   Se abre la página **Nueva fuente**.
3. Introduce el nombre de la fuente en la esquina superior izquierda.
   * Este puede ser cualquier nombre único que te ayude a identificar la fuente en la plataforma DCR. No es necesario que coincida con el nombre del archivo.
   * **¡Importante!** Asegúrate de que el nombre de la fuente sea diferente en todas las demás fuentes de tu cuenta o no podrás [guardar la fuente](/docs/data-clean-room-working-with-sources#4-save-the-source).
   * Requisitos del nombre de la fuente:
     * Longitud: 2-80 caracteres
     * Caracteres válidos:
       * letras `(A-Z, a-z)`
       * números `(0-9)`, *no pueden ser el primer carácter de un nombre;*
     * Caracteres inválidos:
       * espacios
       * todos los demás símbolos o caracteres especiales

</Accordion>

<div id="2-specify-the-source-location" />

<Accordion title="#2: Especificar la ubicación de la fuente">

**Para especificar la ubicación de la fuente:**

1. Selecciona la <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-setting-up-cloud-services#visión-general">conexión</Anchor> en la que se creará (o se creó) la fuente.
   * Si no hay conexiones definidas en tu cuenta, se abrirá el cuadro de diálogo **Nueva conexión**, pidiéndote que crees una. Sigue <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-working-with-connections#completa-la-conexión">estas instrucciones</Anchor> para crearla.
   * Si tienes conexiones existentes pero quieres usar una nueva, haz clic en el botón ![dcr_new_connection_button.png](https://files.readme.io/ea74c7dd6653a544216addddc5fda2a15126a6a26ba2e3ea0a954c58f4fe479e-13916096900753.png) para abrir el cuadro de diálogo **Nueva conexión**. Sigue <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-working-with-connections#completa-la-conexión">estas instrucciones</Anchor> para crearla.
2. Continúa con las instrucciones relevantes a continuación, en función de dónde se encuentren los datos de tu fuente.

#### Fuentes ubicadas en BigQuery

**Para terminar de especificar la ubicación de las fuentes de BigQuery:**

1. Selecciona el conjunto de datos en el que se encuentra la tabla de la fuente.
2. Selecciona la tabla en la que se encuentran los datos de la fuente.

Las listas a partir de las que haces estas selecciones contienen los conjuntos de datos y tablas disponibles, respectivamente, en el proyecto de BigQuery que especificaste al crear la conexión.

#### Fuentes ubicadas en Snowflake

**Para terminar de especificar la ubicación de las fuentes de Snowflake:**

1. Selecciona el recurso compartido que contiene los datos de la fuente.
2. Selecciona el esquema en el que se encuentra la tabla de la fuente.
3. Selecciona la tabla en la que se encuentran los datos de la fuente.

Las listas a partir de las que haces estas selecciones contienen los recursos compartidos, esquemas y tablas, respectivamente, en la cuenta de Snowflake que especificaste al crear la conexión.

#### Fuentes ubicadas en buckets de almacenamiento en la nube

Las ubicaciones de fuente en Amazon S3 o GCS constan del bucket de almacenamiento en la nube especificado por la conexión y de la ruta de la carpeta subyacente desde la que DCR lee el archivo de fuente cada vez que se actualiza.

Una vez especificada la conexión, AppsFlyer puede generar automáticamente la ruta de la carpeta subyacente requerida como parte del proceso de creación de la fuente.

* Permitir que AppsFlyer genere las carpetas facilita el proceso. Sin embargo, puedes optar por crearlas manualmente en su lugar, de acuerdo con las instrucciones <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-setting-up-cloud-services">detalladas aquí</Anchor>.

- o -

* Puedes subir una versión de prototipo del archivo fuente directamente desde su conexión.
  * Si seleccionas esta opción, tendrás que hacer una elección adicional:
    * Permitir que AppsFlyer cree automáticamente la estructura de carpetas fuente; o
    * Crear la estructura de carpetas de fuente manualmente

Si AppsFlyer genera las carpetas, la única información adicional requerida es el nombre que deseas dar a la **carpeta fuente.** (Esta es la carpeta de nivel superior en la que se actualiza la fuente cada vez que desees utilizarla para ejecutar una nueva versión del reporte). También puedes indicar si deseas que la carpeta fuente se cree debajo de una carpeta principal, a menudo denominada **input.**

**Para terminar de especificar la ubicación de la fuente en un bucket de almacenamiento de datos, introduce el nombre de la carpeta de la fuente.**

* Por defecto, el nombre de la carpeta fuente mostrada:
  * Se basa en el [nombre que le diste a la fuente](/docs/data-clean-room-working-with-sources#1-name-the-source). Puedes cambiar el nombre de la carpeta para adaptarlo a tus necesidades, siempre que cumpla los <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-setting-up-cloud-services#dcr-naming-requirements">requisitos de nomenclatura de DCR</Anchor>.
  * Indica que se generará dentro de una carpeta principal denominada **input.** Esta carpeta sirve como carpeta principal para todas las fuentes que cargues en DCR.
    * La carpeta **input** no es obligatoria y puedes eliminarla o asignarle un nombre diferente, siempre y cuando cumpla con los <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-setting-up-cloud-services#dcr-naming-requirements">requisitos de nomenclatura de DCR</Anchor>.
    * Aunque esta carpeta no es obligatoria, se considera una buena práctica disponer de una carpeta **input** (o una carpeta equivalente con un nombre diferente). Se recomienda aún más cuando se utiliza el mismo bucket de almacenamiento en la nube, tanto para subir archivos de datos (entrada) como para recibir reportes (salida).

> 🚧 **Important**
>
> **Importante:**
>
> Si creaste manualmente la ruta de la carpeta, asegúrate de que la conexión y la ruta que introduzcas en la sección **Ubicación de la fuente** coincidan con la ruta que creaste manualmente.

</Accordion>

<div id="3-define-the-source-structure" />

<Accordion title="#3: Definir la estructura de la fuente">

Para todas las fuentes que compartas con DCR para su procesamiento, AppsFlyer necesita saber cómo se debe usar cada campo de datos con el fin de crear los reportes. La definición de la estructura de la fuente consiste en:

* [Cargar los campos de la fuente](/docs/data-clean-room-working-with-sources#cargar-los-campos-de-la-fuente)
* [Categorizar cada campo](/docs/data-clean-room-working-with-sources#clasificar-los-campos) (columna) como uno de los siguientes tipos:
  * **Identificador:** Campo que identifica a un usuario único de la aplicación (por ejemplo, CUID, ID de AppsFlyer, etc.)
    * El objetivo principal de los identificadores en el contexto de DCR es unir las fuentes de datos para poder cotejar los datos de nivel de usuario correspondientes.
  * **Dimensión:** Un atributo por el que categorizas a los usuarios de la aplicación (por ejemplo, geolocalización, fecha de instalación, campaña, etc.)
  * **Métrica:** Datos numéricos que has recopilado con respecto a un usuario de la aplicación (algunos ejemplos podrían ser los ingresos, el número de aperturas de la aplicación, el valor de vida útil (LTV), etc.)
    * Un campo de datos identificado como métrica puede contener **solo valores numéricos.**

#### Cargar los campos de la fuente

Carga los campos de la fuente siguiendo las instrucciones correspondientes a continuación:

**Fuentes de almacén de datos**

Para cargar campos de una fuente ubicada en un almacén de datos (BigQuery o Snowflake), haz clic en el botón ![dcr_load_fields_from_source.png](https://files.readme.io/667761e044a45e9a63bf904ada0ba07917014b5b446379213742510278b5a2dd-14986195290897.png).

> 🚧 **Important**
>
> **Importante:**
>
> Si la tabla de la fuente seleccionada no incluye las [columnas de fecha y versión](/docs/data-clean-room-working-with-sources#table-columns) requeridas, recibirás un error.

**Fuentes de bucket de almacenamiento en la nube**

Para cargar los campos de una fuente ubicada en un bucket de almacenamiento en la nube (Amazon S3 o GCS), debes subir un archivo de fuente prototipo.

Para definir la estructura de la fuente:

* Puedes cargar una versión prototipo de la fuente desde un archivo local.
  * Si seleccionas esta opción, AppsFlyer siempre crea la ruta de la carpeta fuente automáticamente.

- o -

* Puedes subir una versión de prototipo del archivo fuente directamente desde su conexión.
  * Si seleccionas esta opción, tendrás que hacer una elección adicional:
    * Permitir que AppsFlyer cree automáticamente la estructura de carpetas fuente; o
    * Crear la estructura de carpetas de fuente manualmente

**Para cargar el archivo fuente de prototipo, sigue las instrucciones de la pestaña correspondiente a continuación:**

<Tabs>
<Tab title="Archivo local">

1. En la sección **Estructura de la fuente**, haz clic en el botón <Image alt="DCR_load_fields_from_file.png" src="https://files.readme.io/544a069a05fd1afed0b4d9935ccea11dafae6afc78c09491b27809dd52daa373-11240944795025.png" width="125px" />.
2. En la ventana que se abre, selecciona **Cargar un archivo local.**
3. Especifica el archivo CSV o GZIP que deseas cargar y, a continuación, haz clic en Aceptar.

</Tab>

<Tab title="Conexión (creación automática)">

**Para cargar el archivo desde su conexión y permitir que AppsFlyer cree la estructura de carpetas de la fuente:**

1. En la sección **Estructura de la fuente**, haz clic en el botón <Image alt="DCR_load_fields_from_file.png" src="https://files.readme.io/544a069a05fd1afed0b4d9935ccea11dafae6afc78c09491b27809dd52daa373-11240944795025.png" width="125px" />.
2. En la ventana que se abre, selecciona **Cargar desde la conexión.**
3. Haz clic en el enlace **Generar carpetas**.
   * AppsFlyer crea automáticamente la estructura de carpetas y la carpeta de la fuente requeridas (en la conexión especificada, con el nombre de carpeta de fuente especificado).
4. Una vez creada la estructura de carpetas fuente, se muestra un mensaje de confirmación, incluido un enlace a la carpeta fuente. Haz clic en el enlace proporcionado para cargar tu archivo de prototipo en la carpeta fuente.
5. Una vez que el archivo haya terminado de cargarse, haz clic en **Aceptar.**

</Tab>

<Tab title="Conexión (creación manual)">

**Para cargar el archivo fuente de una estructura creada manualmente:**

1. En la sección **Estructura de la fuente**, haz clic en el botón <Image alt="DCR_load_fields_from_file.png" src="https://files.readme.io/544a069a05fd1afed0b4d9935ccea11dafae6afc78c09491b27809dd52daa373-11240944795025.png" width="125px" />.
2. En la ventana que se abre, selecciona **Cargar desde la conexión.**
3. **NO** hagas clic en **Generar carpetas.** En su lugar, sube el archivo directamente a la carpeta de la fuente que creaste para él.
4. Una vez que el archivo haya terminado de cargarse, haz clic en **Aceptar.**

</Tab>
</Tabs>

#### Clasificar los campos

Después de cargar los campos, AppsFlyer analiza el archivo y se muestra una lista de todos los campos de datos (columnas) en la lista **Campos disponibles**.

**Para clasificar los campos:**

1. Selecciona uno o varios campos en la lista **Campos disponibles** de la izquierda y utiliza los botones del centro de la pantalla para clasificarlos como [identificadores, dimensiones o métricas.](/docs/data-clean-room-working-with-sources#3-define-the-source-structure)
   * Una vez categorizado un campo, se muestra en la lista de categorías relevantes en el lado derecho de la pantalla.
   * Puedes utilizar la barra de búsqueda para buscar campos en las listas.
   * Para eliminar un campo de una categoría a la que ha sido asignado, selecciónalo en la lista de categorías correspondiente y utiliza el botón **Eliminar** para devolverlo a la lista **Campos disponibles**.
2. Repite este proceso hasta que hayas categorizado cada campo que desees incluir en los reportes de DCR.
   * No es necesario categorizar cada campo en la lista **Campos disponibles**. Sin embargo, un campo debe ser categorizado para poder utilizarlo posteriormente en un reporte.
3. Si editas la fuente antes de [guardarla](/docs/data-clean-room-working-with-sources#4-save-the-source) y deseas utilizar campos de los datos de la fuente editados, haz clic en el enlace **Recargar campos** en la parte inferior de la lista **Campos disponibles**.
   * Ten en cuenta que al volver a cargar la fuente se sobrescribirán los nombres de los campos en la lista Campos disponibles. Los campos que hayas categorizado previamente permanecerán en las listas **Identificadores,** **Dimensiones,** o **Métricas**.
   * Si un campo previamente categorizado no se encuentra en los datos de la fuente recargados, seguirá apareciendo en la lista de categorías correspondiente, pero se marcará con un icono de error.

> 📘 **Note**
>
> **Nota:**
>
> Si decides utilizar campos adicionales de esta fuente después de guardarla, puedes hacerlo [editando la estructura de la fuente](/docs/data-clean-room-working-with-sources#editing-the-source-structure).

</Accordion>

<div id="4-save-the-source" />

<Accordion title="#4: Guardar la fuente">

**Para guardar la fuente:**

1. [Opcional] Haz clic en <Image alt="DCR_test_source.png" src="https://files.readme.io/c8d2bb2e7062d062a2ed7ddb84472c5acd02fc93b178b2299515b2374a3ad3e3-11240865384849.png" width="43px" /> para comprobar si hay errores en el formato o la validez de los campos de la fuente.
2. Haz clic en **Guardar** para guardar la fuente.

   Se crea la fuente y aparece un mensaje de confirmación.

   * Si has cargado la fuente desde un archivo local, al guardar la fuente se activa la creación automática de la estructura de carpetas, y el mensaje de confirmación que aparece incluye un enlace a la carpeta de la fuente.

   La nueva fuente se muestra en la lista de todas las fuentes existentes en la pestaña **Fuentes** de Data Clean Room.

</Accordion>

## Actualización de las fuentes para activar el procesamiento de reportes

Cada vez que deseas que AppsFlyer procese un archivo de fuente de datos y ejecute un reporte basado en él, subes una nueva versión del archivo a la carpeta fuente, dentro de una serie de subcarpetas anidadas que indican la fecha y el número de versión (más una subcarpeta adicional para que AppsFlyer sepa dónde están los datos).

AppsFlyer busca continuamente nuevas versiones de archivos fuente para la **fecha actual y 2 días antes.** Se activa una nueva versión de un reporte cada vez que se encuentran nuevas versiones de los archivos fuente (incluidos los [archivos \_SUCCESS](/docs/data-clean-room-working-with-sources#_success-files), como se detalla a continuación).

<div id="nested-subfolders-for-each-date-and-version" />

<Accordion title="Subcarpetas anidadas para cada fecha y versión">

La estructura de las subcarpetas anidadas es la siguiente:

* Dentro de la carpeta fuente --> 1 subcarpeta para cada fecha ("carpeta de fecha")
  * **Formato:** `dt=yyyy-mm-dd/`
  * **Ejemplo:** `dt=2022-12-15/`
* Dentro de cada carpeta de fecha --> 1 subcarpeta para cada versión en esa fecha ("carpeta de versión")
  * **Formato:** `v=n/`
  * **Ejemplo:**`v=1/`
  * **Nota:** La carpeta de versión es necesaria aunque solo se cargue el archivo una vez al día.
* Dentro de cada carpeta de versión --> 1 subcarpeta para indicar la ubicación de los datos ("carpeta de datos")
  * **Formato:** `data/`
  * La carpeta de datos es la ubicación a la que se carga el archivo fuente.

En la mayoría de los casos, usarías llamadas a la API u otros medios programáticos disponibles para crear las carpetas de fecha/versión/datos automáticamente cada vez que se cargue el archivo fuente de datos. Para obtener más información, consulta la referencia de la API para tu servicio en la nube: <Anchor target="_blank" href="https://docs.aws.amazon.com/AmazonS3/latest/API/Welcome.html">AWS</Anchor>, <Anchor target="_blank" href="https://cloud.google.com/storage/docs/reference/libraries">GCS</Anchor>.

</Accordion>

<div id="_success-files" />

<Accordion title="Archivos _SUCCESS">

Una vez completada la carga de un archivo de fuente de datos en la carpeta de datos, se debe cargar un archivo vacío denominado `_SUCCESS` en la carpeta de **versiones**. Esto alerta a AppsFlyer de que hay un nuevo archivo disponible para procesar. En la mayoría de los casos, usarías un script de API para generar y cargar automáticamente este archivo.

**¡Importante!** El archivo `_SUCCESS` se carga en la carpeta de **versión**, fuera de la carpeta de datos.

El nombre del archivo \_SUCCESS:

* Debe estar todo en MAYÚSCULAS
* Debe ir precedido de un guión bajo `(_)`
* No debe tener una extensión de archivo

Para archivos GZIP de varias partes:

* Solo debe cargarse un archivo `_SUCCESS` para todas las partes del archivo.
* El archivo `_SUCCESS` debe cargarse solo después de que se haya completado la carga de todas las partes del archivo.

</Accordion>

<div id="example-after-uploading-files" />

<Accordion title="Ejemplo (después de cargar los archivos)">

Después de cargar los archivos fuente en 2 días (y de crear programáticamente carpetas de fecha/versión/datos y archivos `_SUCCESS`), tu estructura de bucket/carpetas podría tener este aspecto:

![dcr_file_structure_after_uploads.png](https://files.readme.io/f6e753cdf8389c0b99cad9cbf1a06261473ef87ce6f840a21ab8d9ccea20aed4-11420299723665.png)

</Accordion>

## Trabajar con fuentes existentes

Hay varias formas de trabajar con las fuentes existentes. Estos procesos se inician desde la pestaña **Sources** de Data Clean Room:

* [Editar el nombre de la fuente](/docs/data-clean-room-working-with-sources#editing-the-source-name)
* [Editar la estructura de la fuente](/docs/data-clean-room-working-with-sources#editing-the-source-structure)
* [Eliminar una fuente](/docs/data-clean-room-working-with-sources#deleting-a-source) (si no se utiliza para un reporte)

<div id="editing-the-source-name" />

<Accordion title="Editar el nombre de la fuente">

Para editar el nombre de la fuente:

1. Ve a la pestaña **Fuentes** de **Data Clean Room.**
2. En la lista de fuentes, pasa el cursor por encima de la fila de la fuente que desees editar.
3. Haz clic en el botón de edición ![edit_button.png](https://files.readme.io/4c3822661beac49fad247c7f5958a535e46031238e975a5323a5550722c89c8a-10753875375377.png) que aparece a la derecha de la fila.
4. En la página **Editar fuente**, edita el nombre de la fuente.
5. Haz clic en el botón **Guardar** para guardar la fuente con el nuevo nombre o en **Cancelar** para deshacer los cambios.

</Accordion>

<div id="editing-the-source-structure" />

<Accordion title="Editar la estructura de la fuente">

Para editar la estructura de la fuente:

1. Ve a la pestaña **Fuentes** de **Data Clean Room.**
2. En la lista de fuentes, pasa el cursor por encima de la fila de la fuente que desees editar.
3. Haz clic en el botón de edición ![edit_button.png](https://files.readme.io/4c3822661beac49fad247c7f5958a535e46031238e975a5323a5550722c89c8a-10753875375377.png) que aparece a la derecha de la fila.
4. En la página **Editar fuente**, los campos que antes estaban categorizados como [identificadores, dimensiones o métricas](/docs/data-clean-room-working-with-sources#3-define-the-source-structure) se mostrarán en las listas de categorías correspondientes en la parte derecha de la pantalla.
5. Puedes mover un campo categorizado anteriormente a una categoría diferente sin volver a cargar los campos del archivo de fuente. Para ello:
   1. En primer lugar, selecciónalo en la lista de categorías correspondiente y utiliza el botón **Eliminar** para devolverlo a la lista **Campos disponibles**.
   2. A continuación, selecciónalo en la lista **Campos disponibles** y utiliza los botones del centro de la pantalla para clasificarlo como identificador, dimensión o métrica.
6. Para trabajar con campos en el archivo de fuente que aún no se han categorizado, se deben volver a cargar desde la ubicación de la fuente o desde un archivo local. Realiza esta selección haciendo clic en el enlace **Volver a cargar campos** en la parte inferior de la lista **Campos disponibles**.
7. AppsFlyer analiza el archivo y se muestra una lista de todos los campos de datos no categorizados anteriormente (columnas) en la lista **Campos disponibles**.
   * Los campos que se categorizaron previamente como identificadores, dimensiones o métricas seguirán apareciendo en las listas de categorías correspondientes en la parte derecha de la pantalla.
   * Si un campo previamente categorizado no se encuentra en el archivo de fuente recargado, seguirá apareciendo en la lista de categorías correspondiente, pero se marcará con un icono de error.
8. Selecciona uno o varios campos en la lista **Campos disponibles** de la izquierda y utiliza los botones del centro de la pantalla para clasificarlos como identificadores, dimensiones o métricas.
9. Una vez que hayas realizado todos los cambios necesarios, haz clic en el botón **Guardar** para guardar la fuente con la estructura actualizada o en **Cancelar** para deshacer los cambios.

> 🚧 **Important**
>
> **Importante:**
>
> No olvides realizar los cambios correspondientes que reflejen la nueva estructura de la fuente en cualquier reporte para el que se utilice esta fuente:
>
> * Los campos que hayan sido eliminados, descategorizados o cambiados de tus categorías anteriores serán eliminados automáticamente de cualquier reporte en el que se utilicen.
> * Los campos recién agregados o categorizados no se incluirán automáticamente en los reportes existentes hasta que edites las definiciones de los reportes para incluirlos.

</Accordion>

<div id="deleting-a-source" />

<Accordion title="Eliminar una fuente">

1. Ve a la pestaña **Fuentes** de **Data Clean Room.**
2. En la lista de fuentes, pasa el cursor por encima de la fila de la fuente que desees eliminar.
3. Haz clic en el botón de eliminación ![delete_button.png](https://files.readme.io/10fbd4d4f09ddb56823a2824629f8bb9362b34c95038b3d9e747ffcde7b30381-24740010666129.png) que aparece a la derecha de la fila.
4. En el cuadro de diálogo, confirma que deseas eliminar la fuente.
   * No puedes eliminar una fuente que esté siendo utilizada por un reporte. Si este es el caso, un mensaje enumerará los reportes en los que se está utilizando la fuente. Para eliminar la fuente, puedes:
     * Eliminar los reportes en los que se está utilizando; o
     * Eliminar los campos de fuente de las definiciones de los reportes en los que se utilizan.

</Accordion>

## Referencia

<div id="manually-creating-a-folder-structure" />

<Accordion title="Creación manual de una estructura de carpetas del bucket de almacenamiento (relevante solo si eliges hacerlo)">

En general, es más fácil permitir que AppsFlyer genere automáticamente la estructura de carpetas requerida como parte del proceso de creación de la fuente. Sin embargo, si deseas crear estas carpetas manualmente, puedes hacerlo de la siguiente manera.

#### Crear una carpeta de claves de DCR

Para garantizar la máxima seguridad, la carpeta directamente debajo del bucket (la "carpeta de clave DCR") debe tener el nombre de la **clave DCR** alfanumérica de 8 caracteres asignada a tu cuenta (por ejemplo, `01bcc5fb`). *Ten en cuenta que esta es diferente de cualquier otra contraseña o clave asociada a tu cuenta de AppsFlyer.*

Por lo general, la carpeta de claves DCR se crea manualmente utilizando la interfaz del servicio en la nube seleccionado.

**Para obtener la clave de DCR de tu cuenta, haz clic en el botón de clave de DCR en la parte superior de la página principal de DCR.**

![dcr_key_button.png](https://files.readme.io/8d02c129ce45b19b28523419e43ec8227a9179e3bafb2b84c0a523b247061c19-16571022734353.png)

Después de crear la carpeta de clave DCR, tu estructura de bucket/carpetas se verá así:

![dcr_file_structure_dcr_key_folder.png](https://files.readme.io/a57ba8076a2af5ef1f5a8339ac6b24e1ab6f8ff60956013a0a6547320a13072f-16571304308497.png)

#### Carpeta de entrada de nivel superior

Aunque no es obligatorio, la práctica recomendada es crear una carpeta de entrada de nivel superior directamente debajo de la carpeta de claves DCR. Esta carpeta estará dedicada a los archivos que subas a DCR.

Por lo general, la carpeta de entrada de nivel superior se crea manualmente utilizando la interfaz del servicio en la nube seleccionado.

* Esta práctica es aún más recomendable cuando se utiliza el mismo bucket tanto para cargar archivos de datos (entrada) como para recibir reportes (salida).
* Puedes nombrar esta carpeta como quieras, siempre y cuando cumpla con los <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-setting-up-cloud-services#dcr-naming-requirements">requisitos de denominación de DCR</Anchor>. Para facilitar su identificación, suele denominarse `input/`.

Después de crear la carpeta de entrada de nivel superior, tu estructura de bucket/carpetas se verá así:

![dcr_file_structure_input_folder.png](https://files.readme.io/cb7249ee0cbc0b4721c701f7d735c73eb7acc0a2a9e73de102b5a5ec9a6a79fd-16571312292753.png)

#### Carpeta de segundo nivel para cada fuente de datos

Puedes cargar regularmente diferentes archivos de origen de datos en DCR para su procesamiento. A cada una de estas fuentes de datos se le debe asignar una carpeta separada ("carpetas de origen de datos").

Por ejemplo, si planeas cargar 2 archivos a DCR para procesarlos todos los días: *BI-data.csv* y *CRM-data.gzip*, asignarías una carpeta a cada una de estas fuentes de datos. Puedes denominar estas carpetas `BI-data/` y `CRM-data/`.

Por lo general, las carpetas de origen de datos se crean manualmente utilizando la interfaz del servicio en la nube seleccionado.

Después de crear 2 carpetas de origen de datos, tu estructura de bucket/carpetas se verá así:

![dcr_file_structure_source_folders.png](https://files.readme.io/f4624a213b79978d8ec080551649fae72d04d2f58a78344fc9df74a859881549-16571312297361.png)

Debajo de cada carpeta de fuente de datos, se deben crear [subcarpetas anidadas por fecha y versión](/docs/data-clean-room-working-with-sources#nested-subfolders-for-each-date-and-version) cada vez que se actualice la fuente.

</Accordion>

<div data-zendesk-anchors="introduction=introducci%C3%B3n h_01HPKB2ERNRQG73AFA0X7XEDEF=introducci%C3%B3n source-format=requisitos-de-los-datos-de-las-fuentes h_01HPKB2ERPANE0CAXFP9RG5YEH=requisitos-de-los-datos-de-las-fuentes h_01HPKB2ERPQ787V0PAABP7Q2YY=data-format h_01HPKB2ERPJ5PVQ2QM5XCYZE0D=table-columns h_01HPKB2ERPWZFZN2DSCHWNXKXX=file-format creating-a-source=crear-una-fuente h_01HPKB2ERPX2T413N3T93YBBZB=crear-una-fuente h_01HPKB2ERPQMT0NKTE5NN40KG4=1-name-the-source h_01HPKB2ERQWDMYBEPDZY17T9PG=2-specify-the-source-location source-locations-in-bigquery=fuentes-ubicadas-en-bigquery h_01HPKB2ERQ28JQ2CK16RYZ38G6=fuentes-ubicadas-en-bigquery source-locations-in-snowflake=fuentes-ubicadas-en-snowflake h_01HPKB2ERQWFGF8MN8ZYAXWC87=fuentes-ubicadas-en-snowflake source-locations-in-cloud-storage-buckets=fuentes-ubicadas-en-buckets-de-almacenamiento-en-la-nube h_01HPKB2ERQZT3Y6GNZ2WWWM0M7=fuentes-ubicadas-en-buckets-de-almacenamiento-en-la-nube h_01HPKB2ERQ40VTVZA5DGNR907G=3-define-the-source-structure loading-source-fields=cargar-los-campos-de-la-fuente h_01HPKB2ERQTJPGG68FSEBHVVJA=cargar-los-campos-de-la-fuente categorize-fields=clasificar-los-campos h_01HPKB2ERSYCFE1EYTCK550VTK=clasificar-los-campos h_01HPKB2ERS55YGWY3RMRPR02Y4=4-save-the-source uploading-source-files-to-trigger-report-processing=actualizaci%C3%B3n-de-las-fuentes-para-activar-el-procesamiento-de-reportes h_01HPKB2ERSCPAPB6WE3354ECW9=actualizaci%C3%B3n-de-las-fuentes-para-activar-el-procesamiento-de-reportes h_01HPKB2ERSEVBTS3DR2TB6Y1AQ=nested-subfolders-for-each-date-and-version h_01HPKB2ERSJ9KNDK6CEBRQB65C=_success-files h_01HPKB2ERSJKGVE61T6J9HXTCK=example-after-uploading-files working-with-existing-sources=trabajar-con-fuentes-existentes h_01HPKB2ERS5PK2P2XTC4ZMPCMC=trabajar-con-fuentes-existentes h_01HPKB2ERTC48MGS0BM5SDR6XV=editing-the-source-name h_01HPKB2ERTS6DEQX0KP0EQTGSP=editing-the-source-structure h_01HPKB2ERVGJYJ9KW1RGX24CGV=deleting-a-source reference=referencia h_01HPKB2ERV1KK3J8YX918GCF3M=referencia h_01HPKB2ERVZ88MJ35JC66YDPAB=manually-creating-a-folder-structure creating-a-dcr-key-folder=crear-una-carpeta-de-claves-de-dcr h_01HPKB2ERV7MQJ9CK44T92GK2G=crear-una-carpeta-de-claves-de-dcr toplevel-input-folder=carpeta-de-entrada-de-nivel-superior h_01HPKB2ERVPG4R9FHWZPQ8TCZQ=carpeta-de-entrada-de-nivel-superior secondlevel-folder-for-each-data-source=carpeta-de-segundo-nivel-para-cada-fuente-de-datos h_01HPKB2ERVVFMP81RE8ATZ6SZ8=carpeta-de-segundo-nivel-para-cada-fuente-de-datos" />
