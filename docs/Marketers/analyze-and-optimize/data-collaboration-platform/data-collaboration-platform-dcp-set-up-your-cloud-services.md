---
title: Plataforma de colaboración de datos (DCP) - Configura tus servicios en la nube
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
  created_at: '2024-04-28T14:01:34Z'
  edited_at: '2026-08-12T11:53:59Z'
  id: 24604528827921
  locale: es
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/es/articles/24604528827921
---
> **Resumen:** Configura tus servicios en la nube para poder conectar tus datos de fuente a DCP y exportar audiencias a tus buckets de almacenamiento en la nube.

## Acerca de la configuración de servicios en la nube

DCP utiliza dos tipos de conexiones para mover datos entre tus servicios en la nube y la plataforma:

* **Conexiones de fuente:** Te permiten conectar tus datos propios a DCP para la colaboración y la creación de audiencias.
* **Conexiones de almacenamiento en la nube:** Te permiten exportar tus audiencias a tus buckets de almacenamiento en la nube después de cada actualización de la audiencia.

Configurar una conexión es un proceso de dos pasos:

* **Paso 1:** Usa la interfaz de tu servicio en la nube para prepararlo para usarlo con DCP.
* **Paso 2:** Conéctalo a DCP en la plataforma de AppsFlyer. Consulta <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-add-connections">Plataforma de colaboración de datos (DCP) - Añadir conexiones</Anchor>.

La tabla siguiente muestra qué servicios son compatibles con cada tipo de conexión:

| Servicios en la nube | Fuente (de entrada) | Almacenamiento en la nube (saliente) |
| --- | --- | --- |
| Amazon S3 | ✓ | ✓ |
| Google Cloud Storage (GCS) | ✓ | ✓ |
| BigQuery | ✓ | - |
| Snowflake | ✓ | - |
| Salesforce Cloud/CRM | ✓ | - |

En Amazon S3 y GCS, se aplica la misma configuración y los mismos permisos del bucket tanto a las conexiones de fuente como a las de almacenamiento en la nube, por lo que no necesitas una configuración independiente para cada dirección. Crear una conexión de fuente crea automáticamente una conexión de almacenamiento en la nube correspondiente (y viceversa), y al eliminar una se elimina la otra, ya que en realidad se trata de una única conexión subyacente compartida entre ambas pestañas.

## Configura tu servicio en la nube

Selecciona a continuación tu servicio en la nube para ver las instrucciones de configuración.

<div id="amazon-s3" />

<Accordion title="Amazon S3">

Sigue las instrucciones a continuación para preparar un bucket de Amazon S3 para usarlo con DCP.

> 📘 **Advertencia**
>
> El administrador de AWS debe llevar a cabo el siguiente procedimiento.

**Para crear un bucket:**

1. Inicia sesión en la consola de AWS.
2. Ve al servicio S3.
3. Crea el bucket:
   1. Haz clic en **Crear bucket**.
   2. Completa el **nombre del bucket**, empezando por `af-dcr-`

       y seguido del texto que quieras, de acuerdo con los [requisitos de nomenclatura de DCR](#dcr-naming-requirements).
   3. Haz clic en **Crear bucket**.

**Para otorgar permisos de bucket a AppsFlyer:**

1. Selecciona el bucket que creaste.
2. Ve a la pestaña **Permissions** (Permisos).
3. En la sección **Política del bucket**, haz clic en **Editar**. Se abre la ventana **Editar la política del bucket**.
4. Pega el siguiente fragmento de código en la ventana:

   ```json
   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Sid": "AF-DCR-DL",
         "Effect": "Allow",
         "Principal": {
           "AWS": [
             "arn:aws:iam::195229424603:user/product=dcr-reporter__envtype=prod__ns=default",
             "arn:aws:iam::195229424603:user/product=datalocker__envtype=prod__ns=default"
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
5. En el fragmento, reemplaza `af-dcr-mybucket` (en las dos líneas en las que aparece) por el nombre del bucket que has creado.
6. Desde la barra superior, abre el menú de cuenta (menú desplegable de dirección de correo electrónico) > **Centro de seguridad**.

> 🚧 **Dos puntos (:)**
>
> Al sustituir el nombre del bucket en el fragmento, no sobrescribas `/*` en la segunda línea en la que aparece el nombre del bucket.

</Accordion>

<div id="google-cloud-storage-gcs" />

<Accordion title="Google Cloud Storage (GCS)">

Usa las siguientes instrucciones para preparar un bucket de GCS para su uso con DCP.

> 📘 **Anunciante**
>
> El siguiente procedimiento debe realizarlo tu administrador de Google Cloud.

**Para crear un bucket:**

1. Inicia sesión en tu consola de GCS.
2. Ve a la página de Cloud Storage Browser.
3. Crea el bucket:
   1. Haz clic en **Crear bucket**.
   2. Introduce la información de tu bucket en la página **Create a bucket**. Incluye el nombre del bucket, empezando por `af-dcr-`

       y seguido del texto que quieras, de acuerdo con los [requisitos de nomenclatura de DCR](#dcr-naming-requirements).
   3. Haz clic en **Continuar**.
   4. Haz clic en **Crear**.

**Para otorgar permisos de bucket a AppsFlyer:**

1. Selecciona el bucket que creaste.
2. Ve a la pestaña **Permissions** (Permisos).
3. En la sección **Permissions**, haz clic en **+ Add**. Se abre la ventana **Add members**.
4. En el cuadro **New members**, introduce las siguientes cuentas:
   * `appsflyer-dcr@dcr-report.iam.gserviceaccount.com`
   * `af-data-delivery@af-raw-data.iam.gserviceaccount.com`
5. En la lista **Role**, selecciona **Cloud storage** > **Storage Admin**.
6. Haz clic en Guardar.

</Accordion>

<div id="bigquery" />

<Accordion title="BigQuery">

BigQuery solo admite conexiones de origen. Usa las siguientes instrucciones para crear un conjunto de datos y conceder permisos a AppsFlyer.

> 📘 **Anunciante**
>
> El siguiente procedimiento debe realizarlo tu administrador de Google Cloud.

**Para crear un conjunto de datos:**

1. Inicia sesión en tu consola de Google Cloud.
2. Ve a la página de BigQuery.
3. En un proyecto nuevo o existente de Google Cloud, crea un conjunto de datos para el uso exclusivo de DCP:
   1. En el panel izquierdo, haz clic en el icono del menú de tres puntos (**View actions**) situado a la derecha del ID del proyecto.
   2. Selecciona **Create dataset**.
   3. En el panel que se abre en el lado derecho, introduce el nombre del conjunto de datos y selecciona otras opciones según sea necesario.
      * Puedes usar cualquier nombre: solo letras, números y guiones bajos.
        * **Recomendado:** Utiliza un nombre que indique que el conjunto de datos se está usando para una conexión de fuente.
      * No uses la opción **Enable table expiration**, ya que DCP no podrá leer tus datos cuando caduquen las tablas.
   4. Haz clic en **Crear conjunto de datos**.

**Para otorgar a AppsFlyer permisos para el conjunto de datos:**

1. En el panel izquierdo, haz clic en el icono del menú de tres puntos (**View actions**) situado a la derecha del conjunto de datos que creaste.
2. Selecciona **Share**.
3. En el panel que se abre en el lado derecho, haz clic en **Add principal**.
4. En la sección **Add principals**, introduce la siguiente cuenta en el campo **New principals**:
   * `appsflyer-dcr@dcr-report.iam.gserviceaccount.com`
5. En la sección **Assign roles**, selecciona **BigQuery** > **BigQuery Data Viewer**.
6. Haz clic en Guardar.
7. Haz clic en **Close** para cerrar el panel del lado derecho.

</Accordion>

<div id="snowflake" />

<Accordion title="Snowflake">

Snowflake solo admite conexiones de fuente. Sigue estas instrucciones para crear un recurso compartido privado para que lo use DCP.

> 📘 **Anunciante**
>
> El siguiente procedimiento debe ser realizado por un **Accountadmin** de Snowflake.

**Para crear un recurso compartido privado:**

1. <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/connecting.html#logging-in-using-the-web-interface">Inicia sesión en la cuenta de Snowflake</Anchor> que contiene los datos que deseas compartir con DCP.
2. Cambia tu rol a **Account admin**.
3. En el panel izquierdo, selecciona **Private Sharing**.
4. En la página que se abre, selecciona la pestaña **Shared By Your Account**.
5. Haz clic en **Share**. En la lista que se abre, selecciona **Create a Direct Share**.
6. Selecciona las tablas y/o vistas que quieras compartir con DCP y, a continuación, haz clic en **Done**.
7. Cambia el **Secure Share Identifier** y añade una descripción opcional según sea necesario.
8. En el campo **Add accounts in your region by name**, introduce la cuenta de Snowflake de AppsFlyer de tu región:

| Información del dispositivo | Cuenta de AppsFlyer |
| --- | --- |
| EU West (eu-west-1) | QL63117 |
| US East - N. Virginia (us-east-1) | MWB70410 |
| US East - Ohio (us-east-2) | BM15378 |

9. Haz clic en **Create Share**.

</Accordion>

<div id="salesforce-cloudcrm" />

<Accordion title="Salesforce Cloud/CRM">

Salesforce Cloud/CRM solo admite conexiones de fuente. Consulta <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-integration-with-salesforce-data-cloud">DCP - Integración con Salesforce Data Cloud</Anchor> para ver las instrucciones de configuración.

</Accordion>

## Especificaciones y limitaciones

| Caducado | Descripción |
| --- | --- |
| Servicios en la nube compatibles | Amazon S3 y GCS admiten tanto conexiones de fuente como de almacenamiento en la nube. BigQuery, Snowflake y Salesforce Cloud/CRM solo admiten conexiones de fuente. |
| Uso del bucket | Los buckets de S3 y GCS deben ser de uso exclusivo para DCP. Ningún otro servicio puede escribir datos en el bucket. |
| <span id="dcr-naming-requirements"></span>Requisitos de denominación de DCR | Los siguientes requisitos de denominación se aplican a todas las entidades de datos de DCR, incluidos los buckets, las carpetas y los archivos:<ul><li>**Longitud máxima:** 200 caracteres</li><li>**Caracteres válidos:** letras (A-Z, a-z), números (0-9), guiones (-)</li><li>**Caracteres no válidos:** espacios y todos los demás símbolos o caracteres especiales</li><li>Los números y los guiones no pueden ser el primer carácter de un nombre</li><li>**Solo caracteres de uso específico:**<ul><li>Signos de igual (=): solo en los <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-working-with-sources#nested-subfolders-for-each-date-and-version">nombres de carpetas de fecha y versión</Anchor></li><li>Guiones bajos {"(_):"} solo en los <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources#file-format">nombres de archivos GZIP de varias partes</Anchor> o en los archivos <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources#_success-files">{"_SUCCESS"}</Anchor></li><li>Puntos (.): solo directamente antes de las extensiones de nombre de archivo (.csv, .gzip)</li></ul></li></ul> |
| Denominación del bucket | Los nombres de los buckets deben empezar por `af-dcr-` seguido de tu texto. Ejemplo: `af-dcr-example-bucket`. |

> 📄 **Véase también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-add-connections">DCP - Agregar conexión</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-build-and-activate-audiences">DCP: crear y activar audiencias</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources">DCP - Crear y gestionar fuentes</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-guide">Guía de la plataforma de colaboración de datos (DCP)</Anchor>

<div data-zendesk-anchors="about-cloud-service-setup=acerca-de-la-configuraci%C3%B3n-de-servicios-en-la-nube h_01KY1VRHDTX2W1YC4QX1N093GF=acerca-de-la-configuraci%C3%B3n-de-servicios-en-la-nube set-up-your-cloud-services=configura-tu-servicio-en-la-nube h_01KY1VRHDT63WWBPNNN3QC9N49=configura-tu-servicio-en-la-nube h_01KY1VRHDT2GRP2MMYTKFNRN3P=amazon-s3 h_01KY1VRHDTYMG39CRENZC971RS=advertencia h_01KY1VRHDVV1ZHTVV5SXGXRZ59=dos-puntos- h_01KY1VRHDVS3S0F22T0EQ5MCKY=google-cloud-storage-gcs h_01KY1VRHDVX4KYCT627NN92TCT=anunciante h_01KY1VRHDVR3CZAZK0PGXDBWRC=bigquery h_01KY1VRHDV8Q3TRG7TBM5TRDYM=anunciante-1 h_01KY1VRHDVSE9WJSDFXYV7W2R3=snowflake h_01KY1VRHDVDDK9B8Y7DKA5GA75=anunciante-2 h_01KY1VRHDV9PJQMAGBY52G9RS8=salesforce-cloudcrm traits-and-limitations=especificaciones-y-limitaciones h_01KY1VRHDVT3PYP5QVKNKQ803G=especificaciones-y-limitaciones h_01KY1VRHDVEWNCDKZYCGWD1SRM=v%C3%A9ase-tambi%C3%A9n" />
