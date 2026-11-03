---
title: 'Plataforma de colaboración de datos (DCP): crea y gestiona fuentes'
metadata:
  keywords:
    - Marketers
    - Audience Activation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Audience Activation
  created_at: '2024-05-02T13:56:27Z'
  edited_at: '2026-09-24T00:03:12Z'
  id: 24740010687249
  locale: es
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/es/articles/24740010687249
---
> **At a glance:** Crea y gestiona fuentes para compartir de forma segura tus datos de first-party con otros colaboradores.

## Sobre las fuentes de DCP

En la Plataforma de colaboración de datos (DCP), una fuente es un conjunto de datos que normalmente se carga en AppsFlyer desde tu almacenamiento en la nube. Estas fuentes constituyen la base de cualquier colaboración, ya que proporcionan los datos que tus colaboradores pueden usar para la creación y activación de audiencias. Este artículo contiene todo lo que necesitas saber sobre cómo crear y gestionar tus fuentes, incluidos estos temas:

* [Requisitos de los datos de las fuentes](#requisitos-de-los-datos-de-las-fuentes)
* [Crear fuentes](#crear-una-fuente)
* [Gestionar tus fuentes](#gestiona-tus-fuentes)

## Requisitos de los datos de las fuentes

Se recomienda <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-prepare-source-data-for-ingestion">preparar los datos de tu fuente</Anchor> para maximizar las tasas de coincidencia entre los conjuntos de datos de los colaboradores y optimizar los resultados de la colaboración. Además, todas las fuentes **deben cumplir los siguientes requisitos**.

<Accordion title="Formato de los datos (relevante para todas las fuentes)">

Los datos dentro de las fuentes deben cumplir estos requisitos:

* **Fecha** (solo): aaaa-mm-dd (por ejemplo, `2023-04-18`)
* **Fecha y hora:**
  * **Formato:** aaaa-MMM-dd hh:mm:ss (*por ejemplo*, `2023-APR-18 15:30:35`)
  * **Zona horaria:** UTC
* **Números:** máximo 2 dígitos después del punto decimal
* **Longitud de la cadena:** máximo 256 caracteres
* **Limitaciones de caracteres:**
  * **Para los nombres de campo (encabezados de columna):** sin espacios ni caracteres especiales
  * **Todos los demás datos:** sin limitaciones (todos los caracteres son válidos)

</Accordion>

<Accordion title="Columnas de la tabla (relevantes solo para las fuentes en data warehouses)">

Además de los datos compartidos para su procesamiento, las tablas fuente en BigQuery o Snowflake deben incluir 2 columnas adicionales: una para la **fecha** y otra para la **versión**:

* **Fecha:**
  * **Encabezado de columna:** `dt`
  * **Tipo de columna:** fecha
  * **Formato de los datos:** aaaa-mm-dd (*por ejemplo*, `2023-04-18`)
  * **Adicional:** las tablas de BigQuery deben estar <Anchor target="_blank" href="https://cloud.google.com/bigquery/docs/partitioned-tables">particionadas</Anchor> por esta columna
* **Versión:**
  * **Encabezado de columna:** `v`
  * **Tipo de columna:** string
  * **Formato de los datos:** número (por ejemplo, `1`, `2`, `3`, `10`)
  * **¡Importante!** Una nueva versión de un reporte se activa cada vez que DCR detecta un nuevo valor en esta columna. Para garantizar la integridad de tu reporte, asegúrate de rellenar la tabla de la fuente con un conjunto completo de datos cada vez que se cambie el valor de la columna.

</Accordion>

<Accordion title="Nombre y formato del archivo (relevante solo para las fuentes en buckets de almacenamiento en la nube)">

Los archivos de fuentes almacenados en Amazon S3 o GCS deben cumplir los siguientes requisitos de nombre y formato de archivo:

* El nombre del archivo debe cumplir los <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-set-up-your-cloud-services#dcr-naming-requirements">requisitos de nomenclatura de DCR</Anchor>
* Formato CSV o GZIP
  * El archivo que se encuentra bajo la compresión GZIP debe ser un archivo CSV.
* Número de archivos de fuentes de datos por <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-add-connections#snowflake-outbound">carpeta de datos</Anchor>:
  * **CSV:** Máximo: 1
  * **GZIP:** Máximo de 1 archivo de una sola parte. Los archivos GZIP de varias partes son compatibles cuando se nombran de la siguiente manera: `filename_part01.csv.gz`, `filename_part02.csv.gz`, etc.

</Accordion>

## Crear una fuente

**Requisito previo:** Antes de crear tu fuente, <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-set-up-your-cloud-services">configura los servicios en la nube</Anchor> que AppsFlyer DCP usará para recuperar los datos de la fuente. Si estas conexiones no están configuradas, se te pedirá que lo hagas durante la creación de la fuente.

**Para crear una fuente en DCP, sigue estos pasos:**

<Accordion title="Paso 1: Acceso a las fuentes de DCP">

1. En AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Data Clean Room**.

   <Image alt="Haz clic en Data Clean Room.png" src="https://files.readme.io/2dc54e035b17aafa17b7eb4c526643284aa7979919f8caa0add13b7e6ae19e0c-41945704690065.png" width="644px" />
2. Haz clic en **+ Nueva fuente** (en la página principal o en la pestaña **Fuentes**).

   <Image alt="sources empty state cropped.png" src="https://files.readme.io/629d8c7c68bfbce7c2307306128b0d0cc430886dc2a58200cb635bc0044d2bd7-33193030142609.png" width="482px" />
3. Procede con los pasos guiados de **Nueva fuente** :

</Accordion>

<Accordion title="Paso 2: Establece el nombre de la fuente">

Introduce el nombre de la fuente. Puede ser cualquier nombre único que te ayude a identificar la fuente. También puedes añadir una descripción opcional sobre la fuente para ayudarte a identificar fácilmente lo que contiene (por ejemplo, «Todas las compras de 2025»).

#### Requisitos y directrices

* Asegúrate de que el **nombre de la fuente** sea único entre todas las demás fuentes de tu cuenta. De lo contrario, no podrás guardar la fuente.
* Para las integraciones en la nube, no es necesario que el nombre coincida con el nombre del archivo.
* Requisitos del nombre de la fuente:
  * Longitud: 2-80 caracteres
  * Caracteres válidos:
    * letras `(A-Z, a-z)`
    * números `(0-9)`, *no pueden ser el primer carácter de un nombre;*
    * Guion bajo `"_"`
  * Caracteres inválidos:
    * espacios
    * todos los demás símbolos o caracteres especiales

</Accordion>

<Accordion title="Paso 3: Establece la ubicación de la fuente">

**Para especificar la ubicación de la fuente:**

1. Selecciona la <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-set-up-your-cloud-services#overview">conexión</Anchor> en la que se creará (o se ha creado) la fuente.
   * Si no hay conexiones definidas en tu cuenta, se abrirá el cuadro de diálogo **Nueva conexión**, para que crees una. Sigue <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-add-connections">estas instrucciones</Anchor> to create it.
   * Si tienes conexiones existentes pero quieres usar una nueva, haz clic en **+ Nueva conexión** y sigue <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-working-with-connections">estas instrucciones</Anchor> para crearla.
2. Continúa con las instrucciones relevantes a continuación, en función de dónde se encuentren los datos de tu fuente.

**Nota:** Para obtener el mejor rendimiento cuando hay un gran volumen de datos, es posible que se almacene por separado un subconjunto de tus datos. Estos datos se actualizarán cada vez que se actualice la fuente y se eliminarán cuando se elimine la fuente.

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

Las ubicaciones de fuente en Amazon S3 o GCS consisten en el bucket de almacenamiento en la nube especificado por la conexión y la ruta de la carpeta subyacente desde la que DCR lee el archivo de la fuente cada vez que se actualiza.

Una vez especificada la conexión, AppsFlyer puede generar automáticamente la ruta de la carpeta subyacente requerida como parte del proceso de creación de la fuente.

* Si dejas que AppsFlyer genere las carpetas, el proceso será más sencillo. Sin embargo, si lo prefieres, puedes crearlas manualmente siguiendo las instrucciones <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-set-up-your-cloud-services">detalladas aquí</Anchor>.

Si AppsFlyer genera las carpetas, la única información adicional que necesitas es el nombre que quieres dar a la **carpeta fuente.** (Esta es la carpeta de nivel superior en la que actualizas la fuente cada vez que quieres usarla para ejecutar una nueva versión del reporte.) También puedes indicar si quieres que la carpeta fuente se cree dentro de una carpeta principal – que a menudo se llama **de entrada.**

**Para terminar de especificar la ubicación de la fuente en un bucket de almacenamiento de datos, introduce el nombre de la carpeta de la fuente.**

* Por defecto, el nombre de la carpeta fuente mostrada:
  * Se basa en el [nombre que le diste a la fuente](#h_01K1ZHNZEQWRP7ZBK7XJP5F9HA). Puedes cambiar el nombre de la carpeta para adaptarlo a tus necesidades, siempre que cumpla los <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-set-up-your-cloud-services#dcr-naming-requirements">requisitos de nomenclatura de DCR</Anchor>.
  * Indica que se generará dentro de una carpeta principal llamada **input.** Esta carpeta sirve como carpeta principal para todas las fuentes que cargues en DCR.
    * La carpeta **de entrada** no es obligatoria, y puedes eliminarla o ponerle otro nombre, siempre que cumpla con los <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-set-up-your-cloud-services#dcr-naming-requirements">requisitos de nomenclatura de DCR</Anchor>.
    * Aunque esta carpeta no es obligatoria, se considera una buena práctica tener una carpeta **de entrada** (o una carpeta equivalente con otro nombre). Se recomienda aún más cuando se utiliza el mismo bucket de almacenamiento en la nube, tanto para subir archivos de datos (entrada) como para recibir reportes (salida).

> 🚧 **Dos puntos (:)**
>
> Si creaste manualmente la ruta de la carpeta, asegúrate de que la conexión y la ruta que introduzcas en la sección **Ubicación de la fuente** coincidan con la ruta que creaste manualmente.


#### Ubicación de la fuente como archivos locales

También puedes subir datos de la fuente mediante un archivo local. Sin embargo, **se recomienda encarecidamente configurar un servicio en la nube como ubicación de la fuente** (algo crucial para conjuntos de datos más grandes y actualizaciones automáticas). Un archivo local se usa principalmente para hacer pruebas y familiarizarte con las funcionalidades de la plataforma.

**Para subir datos de fuente con un archivo local:**

Al seleccionar la ubicación de la fuente, haz clic en **Sistema de archivos local** y en **Siguiente**; así se añade la opción de subir archivos locales desde tu dispositivo.

<Image alt="Selecciona Sistema de archivos local.png" src="https://files.readme.io/08f4797196c915b73a543c7152b5090913287c61b12fefe893d3893ca76fc4d5-33193021989393.png" width="731px" />

> 📘 **Nota:**
>
> * Tipos de archivo compatibles: archivos .CSV y .GZ (tamaño máximo: 5 GB).
> * Los datos subidos desde un archivo local se guardarán durante 180 días.
> * Las actualizaciones deben realizarse manualmente.

</Accordion>

<Accordion title="Paso 4. Configurar el método de actualización de la fuente">

Al configurar una fuente en la Plataforma de colaboración de datos (DCP), debes elegir cómo quieres que se gestionen las actualizaciones de esa fuente. DCP admite dos métodos de sincronización: **Snapshot** y **Append**. Cada método se adapta a distintos casos de uso y flujos de datos:

* **Snapshot** - Este método sube el conjunto de datos completo cada vez que se actualiza la fuente y sustituye por completo el conjunto de datos anterior por el nuevo. Elige este método solo si tus cargas de archivos siempre contienen el conjunto de datos completo y actualizado.
* **Anexar** - Este método sube solo datos nuevos o modificados, no el conjunto de datos completo. Los conjuntos de datos antiguos no se eliminan ni se actualizan. Es ideal para cargas recurrentes, como reportes diarios o semanales. Entre las ventajas se incluyen cargas más pequeñas (lo que puede impulsar menores costos de almacenamiento en la nube), un mejor rendimiento de carga de datos, una gestión de registros más sencilla y más.

<Image alt="Delta Generate folders.png" src="https://files.readme.io/105f55ff555565e97b82ecf86d58cfd2cf2a0340f83d6261fd3bd1c084b13889-38096875288977.png" width="637px" />

> 🚧 **Dos puntos (:)**
>
> Determina qué método es el mejor antes de seleccionar uno. Una vez que selecciones una opción y hagas clic en **Generate folders**, se creará una ruta de archivo junto con instrucciones para gestionar las cargas de datos dentro del servicio en la nube que hayas seleccionado. Para evitar duplicaciones de carpetas y errores, solo puedes **cambiar el método de sincronización una vez** después de la selección inicial.


#### Requisitos para cargar Snapshot

Usa este método para subir un archivo completo y autónomo que sustituya por completo el conjunto de datos anterior cada vez que se actualice la fuente.

<span id="h_01K2A7MAWT05K506384QHYA0FN"></span>**Servicios en la nube compatibles**

* Amazon S3
* Google Cloud Storage (GCS)
* BigQuery
* Snowflake

**<span id="h_01K2A7MAWTCYF3VAWJRRRJFNN5"></span>Sigue estas directrices para el método de actualización de instantánea:**

1. **Ruta de la carpeta de la fuente**

   Cuando registras una fuente de almacenamiento en la nube en DCP, se define una ruta raíz (p. ej., `input/my_source_folder/`) para esa fuente. Cada vez que actualizas el conjunto de datos, subes a esta carpeta una **instantánea completa**: un archivo que contiene todas las filas actuales. Esto garantiza que DCP siempre procese la vista más actualizada y completa de los datos.
2. <span id="h_01K2A7MAWTPJ621MGBBG40N8H4"></span>**Carga de archivos de instantánea completa**

| Directriz | Por qué es importante: | Cómo cumplirlo |
| --- | --- | --- |
| **Conjunto de datos completo** | DCP debe sustituir por completo el estado anterior | Genera una exportación que incluya todos los registros, no solo los cambios |
| **Carpeta particionada por fecha (**`dt=`) | Permite filtrar por intervalo de fechas & gestionar la retención | Coloca cada instantánea en `dt=YYYY‑MM‑DD/` |
| **Subcarpeta de versión (**`v=`) | Permite varias instantáneas el mismo día | La primera carga va en `v=1/`; los reintentos usan `v=2/`, `v=3/`, etc. |
| `subcarpeta` **data/** | Organiza tus archivos | Almacena archivos Parquet / CSV / Avro en esta carpeta |
| `_SUCCESS` **marcador** | Indica que puede comenzar la ingesta de DCP | Sube un archivo vacío llamado `_SUCCESS` dentro de la carpeta `v=` después de que se hayan cargado todos los archivos de datos |
| **Tipo y tamaño de archivo compatibles** |  | <ul><li>Tipos de archivo compatibles: .csv o .gz</li><li>Tamaño máximo de archivo: 5 GB</li></ul> |

> 🚧 **Dos puntos (:)**
>
> El archivo de instantánea completa (BI-data.csv en la captura de pantalla de abajo) debe colocarse en:
>
> ```
> /v=1/data/
> ```
>
> Después, cuando se haya subido el archivo de datos, coloca un archivo vacío `_SUCCESS` en:
>
> ```
> /v=1/
> ```

**Estructura de la carpeta:**

```
s3://af-dcr-xyz/abcd9876/input/source_name1/dt=2025-mm-dd/v=1/data/\n└ bucket ┘ └ tenant ┘ └ingestion┘ └source┘└snapshot date┘└ver┘└files┘
```

| Segmento | Description | Objetivo |
| --- | --- | --- |
| `af-dcr-xyz` | Bucket de S3 / GCS | Contenedor de nivel superior para todos los datos de DCP |
| `abcd9876/` | ID del tenant / espacio de trabajo | Mantiene aislados los datos de cada cliente |
| `entrada/` | Área de ingesta | Donde llegan las cargas sin procesar antes del procesamiento |
| `source_name1/` | Nombre de la fuente | Conjunto de datos lógico registrado en DCP |
| `dt=2025-mm-dd/` | Fecha de la instantánea | Representa el estado completo del conjunto de datos de ese día |
| `v=1/` | Versión (opcional) | Admite reintentos o instantáneas adicionales |
| `datos de SKAN/` | Archivos | Archivos de instantánea Parquet / CSV / Avro |

<span id="h_01K2A7MAWTYFHBANCV9F2NKNCV"></span>**Ejemplo de una estructura de instantáneas de dos días:**

```
source_name1/
  dt=2025-08-10/
    v=1/
      data/
        snapshot.parquet
      _SUCCESS
  dt=2025-08-11/
    v=1/
      data/
        snapshot.parquet
      _SUCCESS
```

Este es un ejemplo de cómo debería verse la estructura de carpetas después de subir una instantánea completa de los archivos fuente durante 2 días (y de crear programáticamente las carpetas de fecha/versión/datos y los archivos \_SUCCESS); la estructura de tu bucket/carpetas podría verse así:

[<Image alt="Ejemplo de bucket de instantánea.png" src="https://files.readme.io/a96762b43bbcae3d1265aa407e725ba885e27c3a83433d017aa30d7afaf31e37-38096860329233.png" width="219px" />](https://files.readme.io/a96762b43bbcae3d1265aa407e725ba885e27c3a83433d017aa30d7afaf31e37-38096860329233.png)


#### Requisitos de carga de Append

Usa este método para subir solo los datos que cambiaron o se añadieron desde la carga anterior.

¿Por qué usar Append?

* **Eficiencia** – cargas más pequeñas
* **Integridad de datos** – conserva el historial completo de cambios para el análisis de series temporales
* **Cumplimiento de la privacidad** – simplifica la eliminación de registros & la gestión del consentimiento

**Servicios en la nube compatibles:** AWS S3 y Google Cloud Storage (GCS)  
**Nota:** BigQuery y Snowflake no son compatibles con el método Append y deben usar el método Snapshot.

**Sigue estas directrices para el método de actualización Append:**

<span id="h_01K2A7MAWT8E6AX95VG86APXBB"></span>1. **Configuración de la carpeta fuente**

| Paso | Description |
| --- | --- |
| **Crear/asignar bucket** | Usa un bucket de S3/GCS existente o deja que AppsFlyer aprovisione uno para ti |
| **Definir la ruta raíz** | Se configura como directorio de entrada una ruta con alcance de tenant (por ejemplo, `s3://af‑dcr‑xyz/abcd1234/`) |
| **de la nube** | Concede al usuario del servicio permiso de escritura solo en esta ruta |

<span id="h_01K2A7MAWT86J2S65D99BC66PQ"></span>2. **Cargando archivos append (delta)**

| Directriz | Por qué es importante: | Cómo cumplir |
| --- | --- | --- |
| **Frecuencia de carga** | Mantiene bajos el costo de transferencia & la sobrecarga operativa | Carga a diario o agrupa carpetas de 7 días y cárgalas semanalmente |
| **Una carpeta por día** | Permite filtrar por fecha & evita analizar grandes lotes | Coloca el delta de cada día en `dt=YYYY‑MM‑DD/` |
| **Nombres de archivo únicos** | Evita sobrescrituras accidentales | Asigna a los archivos nombres únicos siguiendo este modelo:`events_2025‑08‑04.parquet` `events_2025‑08‑05.parquet` |
| **Columnas obligatorias** | Permite el tracking de los cambios | El archivo debe incluir:<ul><li>Una columna de fecha para asociar los registros a un periodo de reportes.<ul><li>Una columna de versión para trackear las revisiones de los datos.</li></ul></li></ul>**Nota:** Si faltan estas columnas en los archivos, se producirá un error de carga en DCP. |

<span id="h_01K2A7MAWTV3FY1GZSXQFNX4JS"></span>**Estructura de la carpeta:**

```
s3://af-dcr-xyz/abcd1234/input/source_name/dt=2025-08-10/\n└ bucket ┘ └ tenant ┘ └ de entrada ┘ └ fuente ┘ └ partición por día ┘
```

| Segmento | Objetivo |
| --- | --- |
| `af-dcr-xyz` | Bucket de S3/GCS del cliente |
| `abcd1234/` | ID del tenant o del espacio de trabajo |
| `entrada/` | Cargas sin procesar en espera de ingestión |
| `source_name/` | Fuente lógica de DCP (p. ej., CRM\_Events) |
| `dt=2025-08-10/` | Carpeta de partición diaria |

<span id="h_01K2A7MAWTRSYFTTDKG4G0TPZR"></span>**Ejemplo de estructura de carpetas delta semanal:**

```
source_name/
  dt=2025-08-04/
  dt=2025-08-05/
  dt=2025-08-06/
  dt=2025-08-07/
  dt=2025-08-08/
  dt=2025-08-09/
  dt=2025-08-10/
```

<span id="h_01K2A7MAWT5NDJQAYD16NRZSAQ"></span>**Guía rápida práctica:**

| Requisito | ¿Por qué? | Ejemplo |
| --- | --- | --- |
| **Lote semanal (opcional)** | Menos push, misma granularidad | Sube un lote que contenga siete carpetas `dt=` del mismo nivel |
| **Particiones por día** | Acelera las consultas & los filtros de la interfaz | `s3://your‑bucket/source/ dt=2025‑08‑04/ ... dt=2025‑08‑10/` |

**Punto clave:** Incluso al subir datos semanalmente, organiza siempre los datos en carpetas `dt=YYYY‑MM‑DD` específicas de cada día.

</Accordion>

<Accordion title="Paso 5: Asignar campos de la fuente">

Asigna los campos de la fuente a los campos de DCP, pruébalo y guarda los datos configurados:

1. [Cargar los campos de la fuente](#1-carga-tus-campos-de-la-fuente)
2. [Configurar los campos de la fuente](#2-configura-los-campos-de-la-fuente)
3. [Verificar la inclusión de usuarios de la UE](#3-verificar-la-inclusión-de-usuarios-de-la-ue)
4. [Probar los datos de la fuente](#4-probar-los-datos-de-la-fuente)
5. [Guardar la fuente](#5-guardar-la-fuente)

#### 1. Carga tus  campos de la fuente

Los campos de la fuente se cargan automáticamente. En caso de que sea necesario realizar una carga manual, sigue las instrucciones que aparecen a continuación según la ubicación de la fuente:

**Fuentes de almacén de datos**

Para cargar campos desde una fuente ubicada en un data warehouse (BigQuery o Snowflake), haz clic en **Cargar campos desde la fuente**.

> 🚧 **Importante:**
>
> Si la tabla de la fuente seleccionada no incluye las [columnas de fecha y versión](#h_01HPKB2ERPJ5PVQ2QM5XCYZE0D) requeridas, recibirás un error.

**Fuentes de bucket de almacenamiento en la nube**

Para cargar los campos de una fuente ubicada en un bucket de almacenamiento en la nube (Amazon S3 o GCS), debes subir un archivo de fuente prototipo.

Para asignar los campos de la fuente a los campos de DCP:

* Puedes cargar una versión prototipo de la fuente desde un archivo local.
  * Si seleccionas esta opción, AppsFlyer siempre crea la ruta de la carpeta fuente automáticamente.

                                                                - o -

* Puedes cargar una versión de prototipo del archivo fuente directamente desde el cloud bucket conectado.
  * Si seleccionas esta opción, tendrás que hacer una elección adicional:
    * Permite que AppsFlyer genere automáticamente la carpeta en la nube para el archivo fuente, o bien
    * [Crear manualmente la carpeta en la nube para el archivo fuente](#h_01HPKB2ERVZ88MJ35JC66YDPAB)

**Para cargar el archivo fuente de prototipo, sigue las instrucciones de la pestaña correspondiente a continuación:**

<Tabs>
<Tab title="Archivo local">

1. En la sección **Asignar campos de la fuente**, haz clic en **Cargar campos desde la fuente**.
2. En la ventana que se abre, selecciona **Cargar un archivo local.**
3. Especifica el archivo CSV o GZIP que deseas cargar y, a continuación, haz clic en Aceptar.

</Tab>

<Tab title="Conexión (creación automática)">

**Para cargar el archivo desde el cloud bucket conectado y permitir que AppsFlyer genere la carpeta en la nube para el archivo fuente:**

1. En la sección **Asignar campos de la fuente**, haz clic en **Cargar campos desde la fuente**.
2. En la ventana que se abre, selecciona **Cargar desde cloud bucket.**
3. Haz clic en el enlace **Generar carpetas**.
   * AppsFlyer genera automáticamente la estructura de carpetas requerida y la carpeta de la fuente en la nube (en la conexión que especificaste, con el nombre de la carpeta de la fuente que especificaste).
4. Después de que se haya creado la estructura de carpetas de la fuente, se muestra un mensaje de confirmación que incluye un enlace a la carpeta de la fuente. Haz clic en el enlace proporcionado para subir tu archivo de prototipo a la carpeta de la fuente.
5. Una vez que el archivo haya terminado de cargarse, haz clic en **Aceptar.**

</Tab>

<Tab title="Conexión (creación manual)">

**Para cargar el archivo fuente de una estructura creada manualmente:**

1. En la sección **Asignar campos de la fuente**, haz clic en **Cargar campos desde la fuente**.
2. En la ventana que se abre, selecciona **Cargar desde cloud bucket.**
3. **NO** hagas clic en **Generar carpetas.** En su lugar, sube el archivo directamente a [la carpeta de la fuente que creaste para él](#h_01HPKB2ERVZ88MJ35JC66YDPAB).
4. Una vez que el archivo haya terminado de cargarse, haz clic en **Aceptar.**

</Tab>
</Tabs>

#### 2. Configura los campos de la fuente

Después de cargar los campos de la fuente, cada campo de la fuente (columna) se muestra con un campo DCP. Revisa cada campo de la fuente y asígnalo al campo DCP correspondiente en la lista desplegable que aparece junto a él. Ten en cuenta lo siguiente:

> 📘 **Nota:**
>
> * Cuando ambas party comparten sus datos fuente, **al menos un campo debe configurarse como identificador** para que los datos a nivel de usuario coincidan entre las fuentes correspondientes. Un identificador es un campo que identifica de forma única a un usuario de la aplicación (por ejemplo, CUID, AppsFlyer ID o correo electrónico con hash).
> * Aunque no es obligatorio configurar cada uno de los campos fuente (columnas) cargados, es importante para la categorización, la interpretación eficaz de los datos, ayudar a la creación de audiencias, sugerir insights y facilitar de forma eficaz las validaciones.

#### Detección del tipo de campo asistida por IA

DCP puede sugerir un campo de DCP para cada columna de la fuente mediante IA, en función del nombre de la columna.

**Para activar la detección asistida por IA:**

1. En la sección **Asignar campos de la fuente**, busca el banner: «¿Quieres ayuda para asignar los campos rápidamente?» **Activar el Asistente de IA de DCP**." Haz clic en **Activar el asistente de IA de DCP**.
2. Cuando se hayan cargado los campos, haz clic en **Detectar automáticamente los tipos de campo**. DCP evalúa el nombre de cada columna y sugiere un campo de DCP para ella.
3. Revisa cada sugerencia antes de guardar. Puedes aceptar una sugerencia tal cual o cambiar la asignación manualmente, igual que editarías cualquier otro campo.

Cada campo queda en uno de estos estados:

* **Asignado:** la IA ha encontrado una única coincidencia fiable. Revísala y acéptala, o cámbiala manualmente.
* **No se ha podido asignar:** la IA no ha podido determinar un campo. Asígnalo manualmente o déjalo sin asignar.

#### Limitaciones

* **Límite de columnas:** la detección por IA es compatible con hasta 100 columnas por fuente. Las fuentes con más columnas muestran un mensaje de «límite superado».
* **Longitud del nombre del campo:** la detección por IA no es compatible con nombres de columna de más de 100 caracteres.

> 🚧 **Importante:**
>
> Igual que con los campos añadidos manualmente, si una asignación sugerida por IA usa un [tipo Lista de...](#importante-2), el archivo fuente debe cargarse o conectarse como Parquet. Los archivos CSV y GZIP no son compatibles con columnas de tipo array.

**Para eliminar un campo:**

* Coloca el cursor sobre la parte derecha del campo que quieres eliminar y haz clic en el icono de la papelera que aparece al pasar el cursor por encima.

**Para añadir campos manualmente:**

Esta opción te permite incluir en la audiencia un campo que actualmente no está presente en la fuente de datos.

1. Haz clic en **+ New field**. Se añade un campo vacío.
2. Introduce el nombre del campo y selecciona su tipo.

<Image alt="NewField.png" src="https://files.readme.io/8dfb70dcac2cc9a2257c6e092bc2185de74a3804bd608878eaaadf09cd903331-43749881081745.png" width="760px" />

**Los tipos de campo incluyen:**

* [**Identificador**](#identificador-frente-a-lista-de-identificadores)
  * Canal de medios atribuido a la visita al sitio web
  * Identificación de AppsFlyer
  * CUID
  * Correo electrónico
  * Correo electrónico hashed
  * Correo electrónico con hash (sin puntos)
  * Identificador de anunciante (IDFA)
  * Dirección IP
  * ID de ID5
  * ID de MediaMath
  * IDs de anuncios móviles
  * Número de teléfono
  * Teléfono con hash (sin signo +)
  * ID de plataforma
  * ID hashed SHA256
  * Número de teléfono SHA256
  * Código postal ZIP+5
  * Código postal ZIP+4
  * LUID
  * ID de persona
* [**Lista de identificadores**](#identificador-frente-a-lista-de-identificadores)
  * Correos electrónicos con hash (sin puntos)
  * Teléfonos con hash (sin signo +)
  * Correo electrónico hashed
  * Teléfonos hash
  * Correos electrónicos
  * Teléfonos
  * IDs de ID5
  * IDs de MediaMath
  * IDs de anuncios móviles
  * IDFA
  * ID de Android
  * Direcciones IP
* Booleano
* Fecha y hora
  * Fecha y hora
  * Fecha
* DMA
  * Representa el número total de engagements (clics, impresiones y otros tipos de engagement) evaluados para un dispositivo determinado en el momento de la conversión.
  * Una agrupación a nivel de negocio que reúne múltiples valores de Platform en categorías más amplias que reflejan la categoría de plataforma en la que ocurrió el evento.
  * Se aplica la DMA de la UE
* Número
  * Double
  * Lista de números
  * Largo
  * Número
* Característica
  * Característica
  * ID de aplicación
  * Lista de texto

#### **Identificador frente a lista de identificadores:**

Los tipos de identificador contienen un único valor por fila (por ejemplo, un correo electrónico o un CUID por fila). Los tipos de lista de identificadores contienen una matriz de valores por fila (por ejemplo, una sola fila puede contener varios correos electrónicos con hashing o ID de dispositivo). Usa esto cuando una fuente necesite hacer coincidir más de un identificador por registro.

> 🚧 **Importante:**
>
> Si una fuente incluye algún campo asignado a **Lista de...** tipo (Lista de identificadores, Lista de números o Lista de texto), el archivo fuente debe subirse o conectarse como Parquet. Los archivos CSV y GZ no admiten columnas de tipo matriz, por lo que es posible que los campos de lista no se ingieran correctamente desde esos formatos.

#### Recargar campos de la fuente

Si la configuración de uno de tus archivos de datos ha cambiado, puedes actualizar el archivo de la fuente para reflejar los cambios.

> 📘 **Nota:**
>
> Al recargar la fuente, los nombres de las columnas de la fuente se restablecen para que coincidan con los nombres actualizados del archivo. Esto sobrescribirá cualquiera de los nombres de campo de la lista y su tipo.

**Para recargar los campos actualizados desde un archivo:**

1. Haz clic en **Recargar campos**.
2. Selecciona la ubicación del archivo.
   * Para un archivo local: sube el archivo.
   * Para un archivo de tu servicio en la nube: haz clic en **Cargar desde cloud bucket** y sigue las instrucciones.
3. Haz clic en **OK**. Ahora se muestran los archivos actualizados.

#### 3. Verificar la inclusión de usuarios de la UE

* Selecciona **Sí** o **No** para la pregunta: **¿Tu fuente incluye usuarios europeos a los que se aplica la normativa DMA de la UE?**

Más información sobre la normativa de privacidad de la Ley de Mercados Digitales de la UE.

#### 4. Probar los datos de la fuente

* [Opcional] Haz clic en **Test** para comprobar si hay errores en el formato o la validez de los campos de la fuente.

#### 5. Guardar la fuente

* Haz clic en **Guardar** para guardar la fuente.

Después de confirmar, la nueva fuente se añade en la pestaña **Sources** .

> 📘 **Nota:**
>
> Si has cargado la fuente desde un archivo local, al guardar la fuente se activa la creación automática de la estructura de carpetas, y el mensaje de confirmación que aparece incluye un enlace a la carpeta de la fuente.

</Accordion>

## Gestiona tus fuentes

Las fuentes que has creado se muestran en la pestaña **Sources**. Desde aquí, puedes editar el nombre y la estructura de la fuente, compartirla con un colaborador y eliminarla, siempre que no se esté usando ya en una audiencia.

<Accordion title="Editar una fuente">

1. Ve a la pestaña **Fuentes** de **Data Clean Room**.
2. En la lista de fuentes, coloca el cursor sobre la fuente que quieres editar y haz clic en el icono de edición ![edit_button.png](https://files.readme.io/4c3822661beac49fad247c7f5958a535e46031238e975a5323a5550722c89c8a-10753875375377.png) al final de la fila.
3. En la página **Editar fuente**, edita los campos correspondientes, como se detalla a continuación.
4. Haga clic en **Guardar**.

#### Editar el nombre de la fuente

Al editar el nombre de la fuente, asegúrate de [seguir estos requisitos de nomenclatura](#requisitos-y-directrices).

#### Editar la ubicación de la fuente

1. En la página **Editar fuente** > **Ubicación de la fuente**, selecciona una conexión de datos diferente.
2. Selecciona los detalles de ubicación correspondientes.
3. [Opcional] [Probar la fuente](#4-probar-los-datos-de-la-fuente).
4. Haga clic en **Guardar**.

#### Editar la asignación de campos

1. Ve a la asignación de campos y realiza los cambios necesarios: cambia el campo o actualiza el campo de DCP asignado.
2. Haga clic en **Guardar**.

> 🚧 **Importante:**
>
> No olvides realizar los cambios correspondientes que reflejen la nueva estructura de la fuente en cualquier reporte para el que se utilice esta fuente:
>
> * Los campos que se hayan eliminado, dejado sin asignar o cambiado con respecto a su asignación anterior se eliminan automáticamente de cualquier reporte en el que se utilicen.
> * Los campos recién añadidos o asignados no se incluyen automáticamente en los reportes existentes hasta que edites las definiciones de los reportes para incluirlos.

</Accordion>

<Accordion title="Eliminar una fuente">

Puedes eliminar cualquier fuente, excepto cuando se esté usando en una audiencia. Si este es el caso, una notificación especificará qué audiencias están usando esa fuente. Para poder eliminar la fuente, primero debes eliminar la audiencia vinculada a ella. En cuanto a las fuentes compartidas contigo, solo puede eliminarlas el propietario de la fuente.

1. Ve a la pestaña **Fuentes** de **Data Clean Room.**
2. En la lista de fuentes, pasa el cursor por encima de la fila de la fuente que desees eliminar.
3. Haz clic en el icono de eliminación ![delete_button.png](https://files.readme.io/10fbd4d4f09ddb56823a2824629f8bb9362b34c95038b3d9e747ffcde7b30381-24740010666129.png) que aparece a la derecha de la fila.
4. En el cuadro de diálogo, haz clic en **Delete** para confirmar.

</Accordion>

## Permisos de uso compartido

La concesión de permisos a tus colaboradores para ver y usar los datos de tu fuente se realiza al <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-a-collaboration">crear colaboraciones</Anchor>. <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-sharing-permissions">Saber más</Anchor> sobre los permisos de uso compartido.

## Información adicional

Esta sección proporciona algunas referencias adicionales e información útil.

<Accordion title="Crear manualmente una estructura de carpetas del bucket de almacenamiento (opcional)">

En general, es más fácil permitir que AppsFlyer genere automáticamente la estructura de carpetas requerida como parte del proceso de creación de la fuente. Sin embargo, si deseas crear estas carpetas manualmente, puedes hacerlo de la siguiente manera.

#### Crear una carpeta de claves de DCR

Para garantizar la máxima seguridad, la carpeta directamente debajo del bucket (la "carpeta de clave DCR") debe tener el nombre de la **clave DCR** alfanumérica de 8 caracteres asignada a tu cuenta (por ejemplo, `01bcc5fb`). *Ten en cuenta que esta es diferente de cualquier otra contraseña o clave asociada a tu cuenta de AppsFlyer.*

Por lo general, la carpeta de claves DCR se crea manualmente utilizando la interfaz del servicio en la nube seleccionado.

**Para obtener la clave DCR de tu cuenta:**

* Haz clic en el menú de 3 puntos (acciones) de la parte superior derecha y selecciona **DCR key**.

[<Image alt="Clave DCR.png" src="https://files.readme.io/b892831ad68cffb5b8084949d759f402780536c7176aa27733c867aff6560684-43750165616657.png" width="1141px" />](https://support.appsflyer.com/hc/article_attachments/49753181770769)

Después de crear la carpeta de clave DCR, tu estructura de bucket/carpetas se verá así:

<Image alt="dcr_file_structure_dcr_key_folder.png" src="https://files.readme.io/a57ba8076a2af5ef1f5a8339ac6b24e1ab6f8ff60956013a0a6547320a13072f-16571304308497.png" width="308px" />

#### Carpeta de entrada de nivel superior

Aunque no es obligatorio, la práctica recomendada es crear una carpeta de entrada de nivel superior directamente debajo de la carpeta de claves DCR. Esta carpeta estará dedicada a los archivos que subas a DCR.

Por lo general, la carpeta de entrada de nivel superior se crea manualmente utilizando la interfaz del servicio en la nube seleccionado.

* Esta práctica es aún más recomendable cuando se utiliza el mismo bucket tanto para cargar archivos de datos (entrada) como para recibir reportes (salida).
* Puedes nombrar esta carpeta como quieras, siempre y cuando cumpla con los <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-set-up-your-cloud-services#dcr-naming-requirements">requisitos de denominación de DCR</Anchor>. Para facilitar su identificación, suele denominarse `input/`.

Después de crear la carpeta de entrada de nivel superior, tu estructura de bucket/carpetas se verá así:

<Image alt="dcr_file_structure_input_folder.png" src="https://files.readme.io/cb7249ee0cbc0b4721c701f7d735c73eb7acc0a2a9e73de102b5a5ec9a6a79fd-16571312292753.png" width="308px" />

#### Carpeta de segundo nivel para cada fuente de datos

Puedes cargar regularmente diferentes archivos de origen de datos en DCR para su procesamiento. A cada una de estas fuentes de datos se le debe asignar una carpeta separada ("carpetas de origen de datos").

Por ejemplo, si planeas cargar 2 archivos a DCR para procesarlos todos los días: *BI-data.csv* y *CRM-data.gzip*, asignarías una carpeta a cada una de estas fuentes de datos. Puedes denominar estas carpetas `BI-data/` y `CRM-data/`.

Por lo general, las carpetas de origen de datos se crean manualmente utilizando la interfaz del servicio en la nube seleccionado.

Después de crear 2 carpetas de origen de datos, tu estructura de bucket/carpetas se verá así:

<Image alt="dcr_file_structure_source_folders.png" src="https://files.readme.io/f4624a213b79978d8ec080551649fae72d04d2f58a78344fc9df74a859881549-16571312297361.png" width="307px" />

Debajo de cada carpeta de fuente de datos, se deben crear [subcarpetas anidadas por fecha y versión](#nested-subfolders-for-each-date-and-version) cada vez que se actualice la fuente.

</Accordion>

## Regulaciones de privacidad

Esta sección describe información importante sobre la normativa de privacidad actual.

<Accordion title="Entender la política de consentimiento de usuarios de la UE de Google y sus implicaciones">

Como parte de la aplicación de la Ley de Mercados Digitales (DMA) por parte de Google, Google actualizó su política de consentimiento de usuarios de la UE el 6 de marzo de 2024. Como partner de atribución de apps de Google, AppsFlyer realizó los cambios necesarios para dar soporte a los requisitos de su política, al tiempo que garantiza que los anunciantes maximicen el valor de sus canales de marketing de Google Ads.

> 📘 **Nota:**
>
> * La aplicación de la Ley de Mercados Digitales (DMA) por parte de Google se aplica a todas las plataformas.
> * Leer más sobre esto:
>   * <Anchor target="_blank" href="https://www.appsflyer.com/hubs/dma/">Insights y recursos sobre la Ley de Mercados de los Comercializadores Digitales</Anchor>
>   * <Anchor target="_blank" href="https://support.google.com/google-ads/answer/14310715">Preguntas frecuentes de Google</Anchor>

#### Añadir campos de consentimiento

Al configurar una fuente destinada a la activación de audiencias en Google y confirmar **Sí** en la pregunta **¿Tu fuente incluye usuarios europeos sujetos a la normativa DMA de la UE?** asegúrate de que los campos de consentimiento adicionales de la tabla siguiente estén incluidos en el archivo de origen. Esto permite a AppsFlyer transferir la información necesaria a Google durante el proceso de activación.

**Campos de consentimiento adicionales y sus valores de respuesta:**

<table><thead><tr><th>AppsFlyer</th><th>Valor de respuesta</th><th>Campo explicado</th></tr></thead><tbody><tr><td><span id="eea"></span><code>eea</code></td><td>verdadero/falso</td><td>¿El usuario está ubicado en el EEE (Espacio Económico Europeo), donde se aplica la DMA?</td></tr><tr><td><span id="ad_personalization"></span><code>personalización de anuncios</code></td><td>\*true/false</td><td>¿El usuario dio su consentimiento a Google para usar sus datos en publicidad personalizada?</td></tr><tr><td><span id="ad_user_data"></span><code>datos_de_usuario_de_anuncios</code></td><td>\*true/false</td><td>¿El usuario dio su consentimiento para enviar sus datos a Google? </td></tr><tr><td colspan="3"><span id="when--true--appsflyer-sends-user-identifiers-for-users-who-have-granted-consent-to-google--when--false--appsflyer-abstains-from-sending-them"></span>\* Cuando es «<strong>true</strong>», AppsFlyer incluye los identificadores de usuario que has enviado para los usuarios que dieron su consentimiento.<br/>   Cuando es «<strong>false</strong>»: AppsFlyer no los incluye, ya que no se enviaron a AppsFlyer.</td></tr></tbody></table>

#### Posible impacto en el tamaño de la audiencia

El tamaño real y estimado de la audiencia enviada a Google puede variar en función del número de usuarios que otorguen o denieguen su consentimiento.

</Accordion>

<div data-zendesk-anchors="introduction=sobre-las-fuentes-de-dcp h_01HPKB2ERNRQG73AFA0X7XEDEF=sobre-las-fuentes-de-dcp source-format=requisitos-de-los-datos-de-las-fuentes h_01HPKB2ERPANE0CAXFP9RG5YEH=requisitos-de-los-datos-de-las-fuentes creating-a-source=crear-una-fuente h_01HPKB2ERPX2T413N3T93YBBZB=crear-una-fuente requirements-and-guidelines=requisitos-y-directrices h_01K1ZHNZEQ3NSN3V7NQ34G8VC8=requisitos-y-directrices source-locations-in-bigquery=fuentes-ubicadas-en-bigquery 01HX49VY7D8KG5DCB82BP69BXV=fuentes-ubicadas-en-bigquery source-locations-in-snowflake=fuentes-ubicadas-en-snowflake 01HX49VY7DXH5YN8FF0NFAJBC2=fuentes-ubicadas-en-snowflake source-locations-in-cloud-storage-buckets=fuentes-ubicadas-en-buckets-de-almacenamiento-en-la-nube 01HX49VY7D3CSF4SQ79Q7CZKWX=fuentes-ubicadas-en-buckets-de-almacenamiento-en-la-nube 01HX49VY7D307DT5VTMGHPF3WA=dos-puntos- local-file-system=ubicaci%C3%B3n-de-la-fuente-como-archivos-locales h_01HX4SKEGE9NVCA6VYSR77S2DK=ubicaci%C3%B3n-de-la-fuente-como-archivos-locales h_01K1FW3AW2AW4TPDS0ZGPQCMX3=ubicaci%C3%B3n-de-la-fuente-como-archivos-locales h_01HX4T0H6SFQJEWFETKFD1CY6S=nota h_01K29ETW94GQM9YYF5A4Y6DKB6=dos-puntos--1 overwrite-method-specifications=requisitos-para-cargar-snapshot snapshot-upload-requirements=requisitos-para-cargar-snapshot h_01K1G33RX95KP9TJ4002DDJBCE=requisitos-para-cargar-snapshot h_01K2A7MAWS5KR16QV0Y8AE39GW=requisitos-para-cargar-snapshot h_01K2CC62XGAVTD5JH5DYXP0947=dos-puntos--2 data-title=requisitos-de-carga-de-append append-delta-upload-requirements=requisitos-de-carga-de-append h_01K2A7MAWT7CRHY1TV5J41MM0D=requisitos-de-carga-de-append h_01K2C6QNJSAH9D3M48T02JHQ3R=requisitos-de-carga-de-append load-the-source-fields=1-carga-tus-campos-de-la-fuente h_01HPKB2ERQTJPGG68FSEBHVVJA=1-carga-tus-campos-de-la-fuente h_01HPKB2ERRZNPYVVD8GHD7PBPE=importante configure-the-source-fields=2-configura-los-campos-de-la-fuente h_01HX64YHGHMK352E3RXHBFV0B5=2-configura-los-campos-de-la-fuente 01HX6HVZ6DK2WH71JVB0J9WPBF=nota-1 h_01K5AI0D3TFIELDTYPEDETECT=detecci%C3%B3n-del-tipo-de-campo-asistida-por-ia ai-assisted-field-type-detection=detecci%C3%B3n-del-tipo-de-campo-asistida-por-ia h_01K5AI0D3TLIMITATIONS=limitaciones limitations=limitaciones h_01K5AI0D3TIMPORTANT=importante-1 identifier-vs-list-of-identifiers=identificador-frente-a-lista-de-identificadores h_01KYSMJKRA2E13PH2QS671BSKG=identificador-frente-a-lista-de-identificadores h_01KYSJNEWS5QY5Q13Z11TNJHX1=importante-2 reload-source-fields=recargar-campos-de-la-fuente h_01HX6TDNEMJFQM5FA95Y3C1QHD=recargar-campos-de-la-fuente h_01HX6WF7YC014Z7ZX359RB5ZRZ=nota-2 verify-eu-user-inclusion=3-verificar-la-inclusi%C3%B3n-de-usuarios-de-la-ue 01HZKZ2T33TYCQ8J59YGDYN7DK=3-verificar-la-inclusi%C3%B3n-de-usuarios-de-la-ue test-the-source-data=4-probar-los-datos-de-la-fuente h_01HX6WGD421PCWEWTN5YJ7V42H=4-probar-los-datos-de-la-fuente save-the-source=5-guardar-la-fuente h_01HYX92EXSJNM5B2PDXEAEBNFS=5-guardar-la-fuente h_01HYXC06K3ZWQE867NKBT95RFH=nota-3 working-with-existing-sources=gestiona-tus-fuentes h_01HPKB2ERS5PK2P2XTC4ZMPCMC=gestiona-tus-fuentes edit-the-source-name=editar-el-nombre-de-la-fuente 01J1SMACQHFEVAR8ZC6W8T0BAV=editar-el-nombre-de-la-fuente edit-the-source-location=editar-la-ubicaci%C3%B3n-de-la-fuente h_01J1SM789AFJBSD0NG826P98Q4=editar-la-ubicaci%C3%B3n-de-la-fuente edit-the-source-structure=editar-la-asignaci%C3%B3n-de-campos h_01J1SNB66WQMBV1GQE4PDQ0NW4=editar-la-asignaci%C3%B3n-de-campos h_01HPKB2ERTYP6BFAESN3MHZSQG=importante-3 permissions=permisos-de-uso-compartido h_01HZHBDPZ8FFQCB9DZ2Q8XSC2R=permisos-de-uso-compartido reference=informaci%C3%B3n-adicional h_01HPKB2ERV1KK3J8YX918GCF3M=informaci%C3%B3n-adicional creating-a-dcr-key-folder=crear-una-carpeta-de-claves-de-dcr h_01HPKB2ERV7MQJ9CK44T92GK2G=crear-una-carpeta-de-claves-de-dcr toplevel-input-folder=carpeta-de-entrada-de-nivel-superior h_01HPKB2ERVPG4R9FHWZPQ8TCZQ=carpeta-de-entrada-de-nivel-superior secondlevel-folder-for-each-data-source=carpeta-de-segundo-nivel-para-cada-fuente-de-datos h_01HPKB2ERVVFMP81RE8ATZ6SZ8=carpeta-de-segundo-nivel-para-cada-fuente-de-datos privacy-regulations-eu-digital-markets-act=regulaciones-de-privacidad h_01HZHBF0NZDTXAA3MY1A0BPE5E=regulaciones-de-privacidad h_01HZM4EFRJD483NARKDPPPPXCY=nota-4 adding-consent-fields=a%C3%B1adir-campos-de-consentimiento h_01HZHBF0NZSDGDYG2ZWNW4KQYD=a%C3%B1adir-campos-de-consentimiento -when-%E2%80%9Ctrue%E2%80%9D-appsflyer-sends-user-identifiers-for-users-who-have-granted-consent-to-google%C2%A0-when-%E2%80%9Cfalse%E2%80%9D-appsflyer-abstains-from-sending-them=when--true--appsflyer-sends-user-identifiers-for-users-who-have-granted-consent-to-google--when--false--appsflyer-abstains-from-sending-them potential-impact-on-the-audience-size=posible-impacto-en-el-tama%C3%B1o-de-la-audiencia h_01HZHBF0NZJBSXNBDFZH4YKNSH=posible-impacto-en-el-tama%C3%B1o-de-la-audiencia" />
