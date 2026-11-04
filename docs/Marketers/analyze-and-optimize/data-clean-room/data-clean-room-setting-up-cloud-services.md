---
title: 'Data Clean Room: configuración de servicios en la nube'
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
  created_at: '2022-03-06T08:23:55Z'
  edited_at: '2026-08-12T11:52:46Z'
  id: 4591167507217
  locale: es
  section: Data Clean Room
  section_id: 4591191779217
  url: https://support.appsflyer.com/hc/es/articles/4591167507217
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **De un vistazo:** Configura uno o más almacenes de datos (BigQuery, Snowflake) y/o buckets de almacenamiento en la nube (Amazon S3, GCS) para compartir datos con Data Clean Room y recibir reportes.

<div id="overview" />

## Visión general

La preparación para usar Data Clean Room (DCR) implica configurar:

* Los servicios/ubicaciones en la nube desde los que DCR lee los datos de origen de tus sistemas (fuentes personalizadas). Estas ubicaciones se utilizan para crear **conexiones entrantes.**
* Los servicios/ubicaciones en la nube a los que DCR entrega los reportes después del procesamiento. Estas ubicaciones se utilizan para crear **conexiones salientes.**

Crear una conexión entrante o saliente es un proceso de 2 pasos:

* **Paso 1:** Usa las interfaces de tus servicios en la nube seleccionados para prepararlos para su uso con DCR (este artículo).
* **Paso 2:** Usa la plataforma AppsFlyer para conectarlos a DCR. (Consulta <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-working-with-connections">Data Clean Room: trabajar con conexiones</Anchor>).

<div id="note" />

> 📘 **Nota**
>
> Consulta <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-working-with-sources#requisitos-de-los-datos-de-las-fuentes">Data Clean Room: trabajar con fuentes</Anchor> para obtener información detallada sobre los requisitos de los datos de origen:
>
> * Formato de los datos *(para todas las fuentes)*
> * Columnas de la tabla *(para fuentes en almacenes de datos)*
> * Nombre y formato del archivo *(para fuentes en buckets de almacenamiento en la nube)*

<div id="supported-cloud-services" />

### Servicios en la nube compatibles

Se admiten dos tipos de servicios en la nube para las conexiones entrantes y salientes a DCR:

* **Almacenes de datos:** BigQuery y Snowflake
* **Buckets de almacenamiento en la nube:** Amazon S3 (AWS) y GCS

Puedes usar uno o cualquier combinación de estos servicios para conexiones entrantes y salientes.

<div id="important" />

> 🚧 **¡Importante!**
>
> * Si vas a utilizar varias fuentes personalizadas para un solo reporte, deben ubicarse en buckets de almacenamiento en la nube.
> * Es muy común usar el mismo bucket de almacenamiento en la nube en Amazon S3 o GCS tanto para conexiones entrantes como salientes. Asegúrate de seguir las [instrucciones específicas para esa configuración](/docs/data-clean-room-setting-up-cloud-services#configuración-del-mismo-bucket-de-almacenamiento-en-la-nube-para-conexiones-entrantes-y-salientes).

<div id="setting-up-cloud-services-for-inbound-connections" />

## Configuración de servicios en la nube para conexiones entrantes

Prepara tus servicios en la nube seleccionados para su uso con conexiones entrantes de DCR, de acuerdo con las instrucciones de las siguientes pestañas.

<div id="data-warehouses--bigquery-and-snowflake" />

### Almacenes de datos: BigQuery y Snowflake

<div id="bigquery-inbound" />

<Accordion title="BigQuery">

**Nota:** El siguiente procedimiento debe ser realizado por tu administrador de Google Cloud.

**Para crear un conjunto de datos y otorgar permisos a DCR:**

1. Inicia sesión en tu consola de Google Cloud.
2. Ve a la página de BigQuery.
3. En un proyecto nuevo o existente de Google Cloud, crea un conjunto de datos para el uso exclusivo de DCR:
   1. En el panel **izquierdo**, haz clic en el botón **View actions (Ver acciones)** <Image alt="BQ_view_actions_button.png" src="https://files.readme.io/c6cab0ddae51b561bf3bac606eccb99e0bdafe25b9a4bee957d6ec09ee48a973-13879852813073.png" width="22px" /> a la derecha del ID del proyecto.
   2. Selecciona **Create dataset (Crear conjunto de datos).**

      <Image alt="BQ_create_dataset.png" src="https://files.readme.io/4f6b9e613b3fd83e0b461fdfae5d986f6eac003be5c3dfae78c42eae7b2c92bb-13879858009105.png" width="457px" />
   3. En el panel que se abre en el **lado derecho**, introduce el nombre del conjunto de datos y selecciona otras opciones según tus necesidades.
      * Puedes usar el nombre que más te convenga, usando solo letras, números y guiones bajos (\_).
        * **Recomendado:** Utiliza un nombre que indique que el conjunto de datos se está utilizando para una conexión entrante.
      * Se recomienda encarecidamente **NO** usar la opción **Enable table expiration (Habilitar caducidad de tabla)**, ya que DCR no sería capaz de leer las fuentes después de que caduquen las tablas.
   4. Haz clic en el botón <Image alt="BQ_create_dataset_button.png" src="https://files.readme.io/242c16aaa7e7f1f96b3392452260fa1c1987a8ebfd276c36630a028baa245b16-13879858133137.png" width="88px" />.
4. Otorga los permisos de DCR al conjunto de datos:
   1. En el panel **izquierdo**, haz clic en el botón **View actions (Ver acciones)** <Image alt="BQ_view_actions_button.png" src="https://files.readme.io/c6cab0ddae51b561bf3bac606eccb99e0bdafe25b9a4bee957d6ec09ee48a973-13879852813073.png" width="22px" /> a la derecha del conjunto de datos que creaste.
   2. Selecciona **Share (Compartir)**.
   3. En el panel que se abre en el **lado derecho**, haz clic en el botón ![BQ_add_principal_button.png](https://files.readme.io/77179cb4b9c81faa7cdc13397920699186df15fd1722247ccd8cbecb0cc43bce-13879857984017.png).
   4. En la sección **Add principals** (Agregar principales), introduce la siguiente cuenta en el campo **New principals** (Nuevos principales):  
      `appsflyer-dcr@dcr-report.iam.gserviceaccount.com`
   5. En la sección **Assign roles (Asignar roles)**, selecciona **BigQuery > BigQuery Data Viewer (Visualizador de datos de BigQuery).**

      <Image alt="BQ_data_viewer.png" src="https://files.readme.io/beec60ee830957ff265f8046875d1b8fa006a2c0cb60427ac969d7d45efa8b5b-14964740088721.png" width="311px" />
   6. Haz clic en **Guardar**.
   7. Haz clic en **CLOSE (CERRAR)** para cerrar el panel del lado derecho.

</Accordion>

<div id="snowflake-inbound" />

<Accordion title="Snowflake">

**Nota:** El siguiente procedimiento debe ser realizado por un **administrador de cuenta** de Snowflake.

**Para crear un recurso compartido privado para su uso por parte de DCR:**

1. <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/connecting.html#logging-in-using-the-web-interface">Inicia sesión en la cuenta de Snowflake</Anchor> que contiene los datos que deseas compartir con DCR.
2. Cambia tu rol a **Accountadmin** (Administrador de cuenta).
3. En el panel izquierdo, selecciona **Private Sharing (Compartir en privado).**
4. En la página que se abre, selecciona la pestaña **Shared By Your Account (Compartido por tu cuenta)**.

   <Image alt="snowflake_private_sharing.png" src="https://files.readme.io/e99ddd6acf3a3714ea1818fc1d28489b0ea458abac3519d6e4fe67ab643de5bb-13879858362257.png" width="609px" />
5. Haz clic en el botón **Share (Compartir)**. En la lista que se abre, selecciona **Create a Direct Share (Crear una compartición directa).**

   <Image alt="snowflake_create_direct_share.png" src="https://files.readme.io/0a33cddd326d03a13da19a1e1b4d75a7f6a9c5479dad2fdcad52f111bc5b4e14-13879858320913.png" width="219px" />
6. Selecciona las tablas y/o vistas que desees compartir con DCR y, a continuación, haz clic en **Done (Listo).**
7. Según tus necesidades, cambia el **Secure Share Identifier (Identificador de compartición segura)** y agrega una descripción opcional.
8. En el campo **Add accounts in your region by name (Agrega cuentas en tu región por nombre)**, introduce una de las siguientes cuentas de Snowflake de AppsFlyer, según la región de tu cuenta de Snowflake:

| Región | Cuenta de AppsFlyer |
| --- | --- |
| EU West (eu-west-1) | QL63117 |
| US East - N. Virginia (us-east-1) | MWB70410 |
| US East - Ohio (us-east-2) | BM15378 |

9. Haz clic en el botón **Create Share (Crear compartición)** .

</Accordion>

<div id="cloud-storage-buckets--amazon-s3-and-gcs" />

### Buckets de almacenamiento en la nube: Amazon S3 y GCS

Puedes utilizar uno o más buckets para cargar datos en DCR (en Amazon S3, GCS o ambos). Sin embargo, en la mayoría de los casos, la estructura más fácil de administrar incluye un solo bucket en un solo servicio en la nube.

* Puedes configurar el mismo bucket para su uso con conexiones entrantes y salientes siguiendo [estas instrucciones](/docs/data-clean-room-setting-up-cloud-services#configuración-del-mismo-bucket-de-almacenamiento-en-la-nube-para-conexiones-entrantes-y-salientes).

<span id="both-cloud-services"></span>Los siguientes requisitos son relevantes para los buckets de ambos servicios en la nube:

* **Uso:** el bucket debe ser para uso exclusivo de Data Clean Room de AppsFlyer. En otras palabras, ningún otro servicio puede escribir datos en el bucket.
* **Permisos:** el servicio DCR de AppsFlyer debe tener permisos de bucket. Consulta las instrucciones para otorgar estos permisos en las pestañas de cada servicio en la nube a continuación.
* **Nombre:** el nombre del bucket debe comenzar por `af-dcr-` o `af-datalocker-`.
  * Ejemplo: `af-dcr-example-bucket`
* <span id="dcr-naming-requirements"></span>**Requisitos de nomenclatura de DCR:** los siguientes requisitos de nomenclatura se aplican a todas las entidades de datos de DCR (buckets, carpetas y archivos):
  * Longitud máxima: 200 caracteres
  * Caracteres válidos:
    * letras `(A-Z, a-z)`
    * números `(0-9)`, *no pueden ser el primer carácter de un nombre*
    * guiones `(-)`, *no pueden ser el primer carácter de un nombre*
    * Caracteres inválidos:
      * espacios
      * todos los demás símbolos o caracteres especiales
    * Caracteres utilizados solo con fines especiales:
      * * signos de igual `(=)`, *solo cuando se requiera en* <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-working-with-sources#nested-subfolders-for-each-date-and-version">nombres de carpetas de fechas y versiones</Anchor>
        * guiones bajos `(_)`, *solo cuando se utilizan para identificar las partes de* <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-working-with-sources#file-format">archivos GZIP de varias partes</Anchor> *o para nombrar* <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-working-with-sources#_success-files">archivos \_SUCCESS</Anchor>
        * puntos `(.)`, *solo directamente antes de las extensiones de nombre de archivo* `(.csv, .gzip)`

<div id="amazon-s3-inbound" />

<Accordion title="Amazon S3">

**Nota:** El administrador de AWS debe llevar a cabo el siguiente procedimiento.

**Para crear un bucket y otorgar permisos a AppsFlyer:**

1. Inicia sesión en la consola de AWS.
2. Ve al servicio S3.
3. Crea el bucket:
   1. Haz clic en **Crear bucket**.
   2. Completa el **Bucket name (Nombre del bucket)**, que debe comenzar con `af-dcr-` o `af-datalocker-`, y seguido de tu texto (de acuerdo con los [requisitos de nomenclatura de DCR](/docs/data-clean-room-setting-up-cloud-services#dcr-naming-requirements) anteriores).
   3. Haz clic en **Crear bucket**.
4. <span id="step-4"></span>Otorga permisos de bucket a AppsFlyer:
   1. Selecciona el bucket que creaste.
   2. Ve a la pestaña **Permisos**.
   3. En la sección **Política del bucket**, haz clic en **Editar.** Se abre la ventana **Editar política de bucket**.
   4. <span id="code-snippet"></span>Pega el siguiente fragmento de código en la ventana.

      ```json
      {
        "Version": "2012-10-17",
        "Statement": [
          {
            "Sid": "AF-DCR-DL",
            "Effect": "Allow",
            "Principal": {
              "AWS": [         "arn:aws:iam::195229424603:user/product=dcr-reporter__envtype=prod__ns=default",   "arn:aws:iam::195229424603:user/product=datalocker__envtype=prod__ns=default"
              ]
            },
            "Action": [
              "s3:GetObject",
              "s3:ListBucket",
              "s3:DeleteObject",
              "s3:PutObject"
            ],
            "Resource": [
              "arn:aws:s3:::af-dcr-mybucket",
              "arn:aws:s3:::af-dcr-mybucket/*"
            ]
          }
        ]
      }
      ```
5. En el fragmento, reemplaza *`af-dcr-mybucket`* (en las 2 líneas en las que aparece) con el nombre del bucket que creaste.  
   **¡Importante!** **Precaución**: *Cuando sustituyas el nombre del bucket en el fragmento, asegúrate de no sobrescribir* `/*` *en la segunda línea en la que aparece el nombre del bucket.*
6. Haz clic en **Guardar cambios**.

</Accordion>

<div id="gcs-inbound" />

<Accordion title="GCS">

**Nota:** El siguiente procedimiento debe ser realizado por tu administrador de Google Cloud.

**Para crear un bucket y otorgar permisos a AppsFlyer:**

1. Inicia sesión en tu consola de GCS.
2. Ve a la página de Cloud Storage Browser.
3. Crea el bucket:
   1. Haz clic en **Create bucket** (Crear bucket).
   2. Introduce la información de tu bucket en la página **Create a bucket** (Crear un bucket). Incluye el nombre del bucket, que debe comenzar con `af-dcr-` o `af-datalocker-`, y seguido de tu texto (de acuerdo con los [requisitos de nomenclatura de DCR](/docs/data-clean-room-setting-up-cloud-services#dcr-naming-requirements) anteriores).
   3. Haz clic en **Continue** (Continuar).
   4. Haz clic en **Create** (Crear).
4. Otorga permisos de bucket a AppsFlyer:
   1. Selecciona el bucket que creaste.
   2. Ve a la pestaña **Permisos**.
   3. En la sección **Permissions** (Permisos), haz clic en **+ Add** (Agregar).  
      Se abre la ventana **Add members** (Agregar miembros).
   4. En el cuadro **New members** (Nuevos miembros), introduce la siguiente cuenta:  
      `appsflyer-dcr@dcr-report.iam.gserviceaccount.com`
   5. En la lista **Role** (Rol), selecciona **Cloud Storage** (Almacenamiento en la nube) > **Storage Admin** (Administrador de almacenamiento).  

      ![dcr_gcs_permissions.png](https://files.readme.io/18c05537d96220c6a5b17f3f8344a5774193da68a30195bf3f4c1f660749f9b2-4726630155153.png)
   6. Haz clic en **Guardar**.

</Accordion>

<div id="setting-up-cloud-services-for-outbound-connections" />

## Configuración de servicios en la nube para conexiones salientes

DCR entrega reportes a tus servicios en la nube seleccionados utilizando <Anchor target="_blank" href="/marketers/es/docs/data-locker-for-marketers">AppsFlyer Data Locker</Anchor>.

* **Nota:** Recibir reportes de DCR no requiere una suscripción Premium a Data Locker. Si estás interesado en recibir otros reportes de AppsFlyer a través de Data Locker, comunícate con tu CSM o envía un correo electrónico a [hello@appsflyer.com](mailto:hello@appsflyer.com).

Tus reportes de DCR se pueden entregar a una o más ubicaciones de tus servicios en la nube (independientemente de que utilices o no los mismos servicios para las conexiones entrantes). Prepáralos para su uso con conexiones salientes de acuerdo con las instrucciones de las siguientes pestañas.

<div id="data-warehouses--bigquery-and-snowflake-1" />

### Almacenes de datos: BigQuery y Snowflake

<div id="bigquery-outbound" />

<Accordion title="BigQuery">

**Nota:** El siguiente procedimiento debe ser realizado por tu administrador de Google Cloud.

**Para crear un conjunto de datos y otorgar permisos a Data Locker:**

1. Inicia sesión en tu consola de Google Cloud.
2. Ve a la página de BigQuery.
3. En un proyecto nuevo o existente de Google Cloud, crea un conjunto de datos para el uso exclusivo de Data Locker:
   1. En el panel **izquierdo**, haz clic en el botón **View actions (Ver acciones)** <Image alt="BQ_view_actions_button.png" src="https://files.readme.io/c6cab0ddae51b561bf3bac606eccb99e0bdafe25b9a4bee957d6ec09ee48a973-13879852813073.png" width="22px" /> a la derecha del ID del proyecto.
   2. Selecciona **Create dataset (Crear conjunto de datos).**

      <Image alt="BQ_create_dataset.png" src="https://files.readme.io/4f6b9e613b3fd83e0b461fdfae5d986f6eac003be5c3dfae78c42eae7b2c92bb-13879858009105.png" width="457px" />
   3. En el panel que se abre en el **lado derecho**, introduce el nombre del conjunto de datos y selecciona otras opciones según tus necesidades.
      * Puedes usar el nombre que más te convenga, usando solo letras, números y guiones bajos (\_).
        * **Recomendado:** Utiliza un nombre que indique que el conjunto de datos se está utilizando para una conexión saliente.
      * Se recomienda encarecidamente **NO** usar la opción **Enable table expiration (Habilitar caducidad de tabla)**, ya que Data Locker no sería capaz de escribir los reportes en el conjunto de datos después de que caduquen las tablas.
   4. Haz clic en el botón <Image alt="BQ_create_dataset_button.png" src="https://files.readme.io/242c16aaa7e7f1f96b3392452260fa1c1987a8ebfd276c36630a028baa245b16-13879858133137.png" width="88px" />.
4. Otorgar permisos de Data Locker al conjunto de datos:
   1. En el panel **izquierdo**, haz clic en el botón **View actions (Ver acciones)** <Image alt="BQ_view_actions_button.png" src="https://files.readme.io/c6cab0ddae51b561bf3bac606eccb99e0bdafe25b9a4bee957d6ec09ee48a973-13879852813073.png" width="22px" /> a la derecha del conjunto de datos que creaste.
   2. Selecciona **Share (Compartir)**.
   3. En el panel que se abre en el **lado derecho**, haz clic en el botón ![BQ_add_principal_button.png](https://files.readme.io/77179cb4b9c81faa7cdc13397920699186df15fd1722247ccd8cbecb0cc43bce-13879857984017.png).
   4. En la sección **Add principals** (Agregar principales), introduce la siguiente cuenta en el campo **New principals** (Nuevos principales):  
      `datalocker-bq-admin-prod@datalocker-bq-prod.iam.gserviceaccount.com`
   5. En la sección **Assign roles (Asignar roles)**, selecciona **BigQuery > BigQuery Data Editor (Editor de datos de BigQuery).**

      <Image alt="BQ_data_editor.png" src="https://files.readme.io/cc26288d02f10805c971167d42d77efc9c7702f7fe231724b66eddd9b1b0e252-13879852726929.png" width="323px" />
   6. Haz clic en **Guardar**.
   7. Haz clic en **CLOSE (CERRAR)** para cerrar el panel del lado derecho.

</Accordion>

<div id="snowflake-outbound" />

<Accordion title="Snowflake">

El procedimiento para preparar Snowflake para conexiones salientes se completa en combinación con el <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-working-with-connections#snowflake-outbound">procedimiento para crear la propia conexión saliente</Anchor>.

</Accordion>

<div id="cloud-storage-buckets--amazon-s3-and-gcs-1" />

### Buckets de almacenamiento en la nube: Amazon S3 y GCS

El procedimiento para preparar buckets de almacenamiento en la nube para conexiones salientes es muy similar al de preparación para [conexiones entrantes](/docs/data-clean-room-setting-up-cloud-services#configuración-de-servicios-en-la-nube-para-conexiones-entrantes) (incluyendo las instrucciones relevantes para ambos servicios de almacenamiento en la nube).

Las instrucciones de las pestañas a continuación se aplican cuando estás utilizando un bucket **solo para conexiones salientes.**

* Si vas a utilizar el mismo bucket tanto para conexiones entrantes como salientes, sigue las [instrucciones específicas para dicha configuración](/docs/data-clean-room-setting-up-cloud-services#configuración-del-mismo-bucket-de-almacenamiento-en-la-nube-para-conexiones-entrantes-y-salientes).

<div id="amazon-s3-outbound" />

<Accordion title="Amazon S3">

Sigue las instrucciones para crear un [bucket de Amazon S3 para conexiones entrantes](/docs/data-clean-room-setting-up-cloud-services#amazon-s3-inbound) (sin cambios en ese procedimiento).

</Accordion>

<div id="gcs-outbound" />

<Accordion title="GCS">

Sigue las instrucciones para crear un [bucket de GCS para conexiones entrantes](/docs/data-clean-room-setting-up-cloud-services#gcs-inbound). En el paso 4 de ese procedimiento, introduce la siguiente cuenta en la casilla **New members (Nuevos miembros)**:  
`af-data-delivery@af-raw-data.iam.gserviceaccount.com`

</Accordion>

<div id="setting-up-the-same-cloud-storage-bucket-for-both-inbound-and-outbound-connections" />

## Configuración del mismo bucket de almacenamiento en la nube para conexiones entrantes y salientes

Como se mencionó anteriormente, es común usar el mismo bucket en Amazon S3 o GCS para las conexiones entrantes y salientes.

Las instrucciones para esta configuración varían solo ligeramente de las [instrucciones para las conexiones entrantes](/docs/data-clean-room-setting-up-cloud-services#configuración-de-servicios-en-la-nube-para-conexiones-entrantes). Sin embargo, difieren en función de si vas a:

* crear un nuevo bucket para su uso con conexiones entrantes y salientes de DCR; ***o***
* modificar un bucket previamente usado solo para Data Locker a uno que ahora se usa para conexiones de DCR entrantes y salientes

Las instrucciones para ambos escenarios se incluyen en las pestañas a continuación:

<div id="amazon-s3-inbound-outbound" />

<Accordion title="Amazon S3">

<div id="creating-a-new-bucket-for-inboundoutbound-connections" />

#### Creación de un nuevo bucket para conexiones entrantes/salientes

Sigue las instrucciones para crear un [bucket de Amazon S3 para conexiones entrantes](/docs/data-clean-room-setting-up-cloud-services#amazon-s3-inbound) (sin cambios en ese procedimiento).

<div id="modifying-an-existing-bucket-previously-used-only-for-data-locker" />

#### Modificación de un bucket existente que se usaba anteriormente solo para Data Locker

Modificar un bucket existente que anteriormente usaste solo para Data Locker requiere cambiar los permisos del bucket (para permitir el acceso tanto por DCR como por Data Locker).

**Para modificar los permisos de bucket:**

1. Inicia sesión en la consola de AWS.
2. Ve al servicio S3.
3. Selecciona el bucket usado anteriormente solo para Data Locker.
4. Ve a la pestaña **Permisos**.
5. En la sección **Política del bucket**, haz clic en **Editar.**  
   Se abre la ventana **Editar política de bucket**.
6. **Reemplaza el contenido** de la ventana con el siguiente fragmento de código:

   ```json
   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Sid": "AF-DCR-DL",
         "Effect": "Allow",
         "Principal": {
           "AWS": [         "arn:aws:iam::195229424603:user/product=dcr-reporter__envtype=prod__ns=default",   "arn:aws:iam::195229424603:user/product=datalocker__envtype=prod__ns=default"
           ]
         },
         "Action": [
           "s3:GetObject",
           "s3:ListBucket",
           "s3:DeleteObject",
           "s3:PutObject"
         ],
         "Resource": [
           "arn:aws:s3:::af-dcr-mybucket",
           "arn:aws:s3:::af-dcr-mybucket/*"
         ]
       }
     ]
   }
   ```

   * En el fragmento, reemplaza *`af-dcr-mybucket`* (en las 2 líneas en las que aparece) con el nombre del bucket que creaste.
   * **¡Importante!** **Precaución**: *Cuando sustituyas el nombre del bucket en el fragmento, asegúrate de no sobrescribir* `/*` *en la segunda línea en la que aparece el nombre del bucket.*
7. Haz clic en **Guardar cambios**.

</Accordion>

<div id="gcs-inbound-outbound" />

<Accordion title="GCS">

<div id="creating-a-new-bucket-for-inboundoutbound-connections-1" />

#### Creación de un nuevo bucket para conexiones entrantes/salientes

Sigue las instrucciones para crear un [bucket de GCS para conexiones entrantes](/docs/data-clean-room-setting-up-cloud-services#gcs-inbound). Modifica el paso 4 de ese procedimiento para introducir las siguientes **2 cuentas** en la casilla **New members (Nuevos miembros)**:  
`appsflyer-dcr@dcr-report.iam.gserviceaccount.com`  
`af-data-delivery@af-raw-data.iam.gserviceaccount.com`

<div id="modifying-an-existing-bucket-previously-used-only-for-data-locker-1" />

#### Modificación de un bucket existente que se usaba anteriormente solo para Data Locker

Modificar un bucket existente que anteriormente usaste solo para Data Locker requiere cambiar los permisos del bucket (para permitir el acceso tanto por DCR como por Data Locker).

**Para modificar los permisos de bucket:**

1. Inicia sesión en tu consola de GCS.
2. Ve a la página de Cloud Storage Browser.
3. Selecciona el bucket usado anteriormente solo para Data Locker.
4. Ve a la pestaña **Permisos**.
5. En la sección de permisos, haz clic en **+ Add** (Agregar).  
   Se abre la ventana **Add members** (Agregar miembros).
6. En el cuadro **New members** (Nuevos miembros), introduce la siguiente cuenta:  
   `appsflyer-dcr@dcr-report.iam.gserviceaccount.com`
7. En la lista **Role** (Rol), selecciona **Cloud Storage** (Almacenamiento en la nube) > **Storage Admin** (Administrador de almacenamiento).  

   ![dcr_gcs_permissions.png](https://files.readme.io/18c05537d96220c6a5b17f3f8344a5774193da68a30195bf3f4c1f660749f9b2-4726630155153.png)
8. Haz clic en **Guardar**.

</Accordion>

<div data-zendesk-anchors="overview=visi%C3%B3n-general h_01J6Y2P4CKMZ3R8WZ4X76DZ6ZY=visi%C3%B3n-general h_01J6Y2P4CMJ4CXJZ3EDDXQG4Y3=nota supported-cloud-services=servicios-en-la-nube-compatibles h_01J6Y2P4CMNMTSPWDK9GGSDYMJ=servicios-en-la-nube-compatibles h_01J6Y2P4CM8VDWCD5XH91DJPYX=importante setting-up-cloud-services-inbound=configuraci%C3%B3n-de-servicios-en-la-nube-para-conexiones-entrantes h_01J6Y2P4CM61DEXMWB626X25TT=configuraci%C3%B3n-de-servicios-en-la-nube-para-conexiones-entrantes data-warehouses-inbound=almacenes-de-datos-bigquery-y-snowflake h_01J6Y2P4CMDX64XXGNS7ZP3GKZ=almacenes-de-datos-bigquery-y-snowflake h_01J6Y2P4CMY5DHFEFGHQQPAPK9=bigquery-inbound h_01J6Y2P4CMMZFYDZWK82F5J65W=snowflake-inbound cloud-storage-buckets-inbound=buckets-de-almacenamiento-en-la-nube-amazon-s3-y-gcs h_01J6Y2P4CMCJDT2W6C52MF71TB=buckets-de-almacenamiento-en-la-nube-amazon-s3-y-gcs h_01J6Y2P4CMS2JF9Z7F13XW485F=amazon-s3-inbound h_01J6Y2P4CM9Y9114CH1ESY0QPJ=gcs-inbound setting-up-cloud-services-outbound=configuraci%C3%B3n-de-servicios-en-la-nube-para-conexiones-salientes h_01J6Y2P4CMEEG6PNM2PMEYGQ3A=configuraci%C3%B3n-de-servicios-en-la-nube-para-conexiones-salientes data-warehouses-outbound=almacenes-de-datos-bigquery-y-snowflake-1 h_01J6Y2P4CMNWQ0D3EZXJZZM1EY=almacenes-de-datos-bigquery-y-snowflake-1 h_01J6Y2P4CM8MVS3SZAYE2YDV2T=bigquery-outbound h_01J6Y2P4CN97P8GCV314TQ91EE=snowflake-outbound cloud-storage-buckets-outbound=buckets-de-almacenamiento-en-la-nube-amazon-s3-y-gcs-1 h_01J6Y2P4CNZ61PG9BTCVRFZ20K=buckets-de-almacenamiento-en-la-nube-amazon-s3-y-gcs-1 h_01J6Y2P4CN4ZRAMQ2E3R4Q4KHS=amazon-s3-outbound h_01J6Y2P4CN39GT0QT6THFAA3ZY=gcs-outbound setting-up-cloud-services-inbound-outbound=configuraci%C3%B3n-del-mismo-bucket-de-almacenamiento-en-la-nube-para-conexiones-entrantes-y-salientes h_01J6Y2P4CN2ARMJKRSAFZNN59G=configuraci%C3%B3n-del-mismo-bucket-de-almacenamiento-en-la-nube-para-conexiones-entrantes-y-salientes h_01J6Y2P4CNKC9P1FKECHZJ6AXP=amazon-s3-inbound-outbound creating-a-new-bucket-for-inboundoutbound-connections=creaci%C3%B3n-de-un-nuevo-bucket-para-conexiones-entrantessalientes h_01J6Y2P4CN216K0VZSWRP699TF=creaci%C3%B3n-de-un-nuevo-bucket-para-conexiones-entrantessalientes modifying-an-existing-bucket-previously-used-only-for-data-locker=modificaci%C3%B3n-de-un-bucket-existente-que-se-usaba-anteriormente-solo-para-data-locker h_01J6Y2P4CNDW888XTMKAMZAFCS=modificaci%C3%B3n-de-un-bucket-existente-que-se-usaba-anteriormente-solo-para-data-locker h_01J6Y2P4CN0MEEKG0D2SKMDZVY=gcs-inbound-outbound creating-a-new-bucket-for-inboundoutbound-connections::e1cda9c8=creaci%C3%B3n-de-un-nuevo-bucket-para-conexiones-entrantessalientes-1 h_01J6Y2P4CN336CRH1CWRJVCHHY=creaci%C3%B3n-de-un-nuevo-bucket-para-conexiones-entrantessalientes-1 modifying-an-existing-bucket-previously-used-only-for-data-locker::ba0d4803=modificaci%C3%B3n-de-un-bucket-existente-que-se-usaba-anteriormente-solo-para-data-locker-1 h_01J6Y2P4CNYCTVGN6CH0748S24=modificaci%C3%B3n-de-un-bucket-existente-que-se-usaba-anteriormente-solo-para-data-locker-1" />
