---
title: 'Data Locker: configuración del servicio en la nube'
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Data Locker
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Data Locker
  created_at: '2021-02-10T17:35:25Z'
  edited_at: '2026-08-12T11:51:42Z'
  id: 360017603577
  locale: es
  section: Data Locker
  section_id: 6550945728657
  url: https://support.appsflyer.com/hc/es/articles/360017603577
---
> **En resumen:** Configura tu servicio en la nube para recibir datos de Data Locker: GCS, AWS, BigQuery o Snowflake.

Data Locker te permite transmitir datos a tu solución de almacenamiento seleccionada y propia, ya sea un bucket o un almacén de datos. Configura tu servicio en la nube usando uno de los siguientes procedimientos.

## Almacenamiento en la nube de bucket

<div id="gcs-storage" />

<Accordion title="Almacenamiento GCS">

Antes de empezar, ten en cuenta lo siguiente:

* El procedimiento de esta sección debe ser realizado por tu administrador de Google Cloud.
* Puedes eliminar archivos de Data Locker 25 o más horas después de su escritura. No los elimines antes.

**Información para el administrador de GCS**

Data Locker es la solución de AppsFlyer para la transmisión de datos al almacenamiento.

**Requisitos**

* Crea un bucket en GCS para el uso exclusivo de Data Locker. Exclusivo significa que ningún otro servicio escribe datos en el bucket.
* Nombre del bucket sugerido: `af-datalocker`.
* Otorga permisos de Data Locker mediante el siguiente procedimiento.

**Para otorgar permisos de Data Locker:**

En este procedimiento, sustituye `data-locker-example` por el nombre del bucket que creaste anteriormente para Data Locker.

1. Inicia sesión en tu consola de GCS.
2. Ve a **Almacenamiento** > **Navegador de almacenamiento**.

   [![mceclip0.png](https://files.readme.io/933df60c2073a7eba97429f3cf95967ae04513a50a14e8c22ec9ee0a94f480d7-360016875898.png)](https://files.readme.io/933df60c2073a7eba97429f3cf95967ae04513a50a14e8c22ec9ee0a94f480d7-360016875898.png)
3. Selecciona el bucket que has creado anteriormente, por ejemplo, `data-locker-example`.
4. Ve a la pestaña **Permisos**.
5. Haz clic en **Agregar**.  
   Se abre la ventana “Agregar miembros”.
6. Completa de la siguiente forma:
   1. **Nuevos miembros**, pega el fragmento que sigue.

      ```http
      af-data-delivery@af-raw-data.iam.gserviceaccount.com
      ```
   2. **Selecciona un rol**: **Almacenamiento en la nube** > **Administrador de objetos de almacenamiento**

      [![mceclip0.png](https://files.readme.io/925501e1f16f4276d4a7aa0be8a78c94057fbdf07d48929e55bafe489f01cd42-360017059798.png)](https://files.readme.io/925501e1f16f4276d4a7aa0be8a78c94057fbdf07d48929e55bafe489f01cd42-360017059798.png)
7. Haz clic en **Guardar**.

</Accordion>

<div id="aws-storage" />

<Accordion title="Almacenamiento AWS">

Antes de empezar, ten en cuenta lo siguiente:

* Tu administrador de AWS debe llevar a cabo el procedimiento en esta sección.
* Puedes eliminar archivos de Data Locker 25 o más horas después de su escritura. No los borres antes.

**Información para el administrador de AWS**

Data Locker es la solución de AppsFlyer para la transmisión de datos al almacenamiento.

**Requisitos**

* Crea un bucket de AWS con el nombre af-datalocker-mybucket. El prefijo af-datalocker- es obligatorio. El sufijo es texto libre.
* Sugerimos af-datalocker-aaaa-mm-dd-hh-mm-texto-libre. Donde aaaa-mm-dd-hh-mm son la fecha y hora actuales, y luego agregas cualquier otro texto que quieras, como se muestra en la siguiente figura.

**Interfaz de usuario en la consola AWS**

![MyBucket.jpg](https://files.readme.io/b8a16d185279200026388e146cfb3eb03ae3c7737ac26da3aa0d116a0cf9c078-4403551836305.jpg)

Una vez creado el bucket, concede los permisos a AppsFlyer mediante el siguiente procedimiento.

**Para crear un bucket y otorgar permisos a AppsFlyer:**

1. Inicia sesión en la consola de AWS.
2. Ve al servicio S3.
3. **Para crear el bucket**:
   1. Haz clic en **Crear bucket**.
   2. Completa el **Nombre del bucket** de la siguiente manera: Comienza con `af-datalocker-` y luego agrega cualquier otro texto como se describió anteriormente.
   3. Especifica una de las regiones [AWS compatibles](#regiones-aws-admitidas).
   4. Haz clic en **Crear bucket**.
4. **Para otorgar permisos a AppsFlyer:**
   1. Selecciona el bucket.
   2. Ve a la pestaña **Permisos**.
   3. En la sección **Política del bucket**, haz clic en **Editar**.   
      Se abre la ventana de Política del bucket.
   4. Pega el siguiente fragmento de código en la ventana.

      ```json
      {
        "Version": "2012-10-17",
        "Statement": [
          {
            "Sid": "AF_DataLocker_Direct",
            "Effect": "Allow",
            "Principal": {
              "AWS": "arn:aws:iam::195229424603:user/product=datalocker__envtype=prod__ns=default"
            },
            "Action": [
              "s3:GetObject",
              "s3:ListBucket",
              "s3:DeleteObject",
              "s3:PutObject"
            ],
            "Resource": [
              "arn:aws:s3:::af-datalocker-my-bucket",
              "arn:aws:s3:::af-datalocker-my-bucket/*"
            ]
          }
        ]
      }
      ```
5. En el fragmento, reemplaza `af-data-locker-my-bucket` por el nombre del bucket que creaste.
6. [Opcional] Agrega soporte para buckets cifrados de KMS. Para ello, en la sección **Política de claves**, elige Cambiar a la vista de políticas y pega el siguiente fragmento en la matriz Statement.

   ```json
   {
         "Sid": "Permitir el uso de la clave",
         "Effect": "Allow",
         "Principal": {
             "AWS": "arn:aws:iam::195229424603:user/product=datalocker__envtype=prod__ns=default"
         },
         "Action": "kms:GenerateDataKey*",
         "Resource": "*"
     }
   ```
7. Haz clic en **Guardar cambios**.
8. Completa la <Anchor target="_blank" href="/marketers/es/docs/data-locker-for-marketers#set-up-data-locker">configuración del Data Locker.</Anchor>

#### **Regiones AWS admitidas**

Data Locker admite las siguientes regiones de AWS:

* Asia Pacífico (Tokio): `ap-northeast-1`
* Asia Pacífico (Seúl): `ap-northeast-2`
* Asia Pacífico (Bombay): `ap-south-1`
* Asia Pacífico (Singapur): `ap-southeast-1`
* Asia Pacífico (Sídney): `ap-southeast-2`
* Canadá (Centro): `ca-central-1`
* UE (Frankfurt): `eu-central-1`
* UE (Irlanda): `eu-west-1`
* UE (Londres): `eu-west-2`
* América del Sur (Sao Paulo): `sa-east-1`
* Este de EE. UU. (N. Virginia): `us-east-1`
* Estados Unidos Este (Ohio): `us-east-2`
* Oeste de EE. UU. (N. California): `us-west-1`
* US West (Oregón): `us-west-2`

</Accordion>

<div id="beta--azure-storage" />

<Accordion title="Almacenamiento en Azure">

Antes de empezar, ten en cuenta lo siguiente:

* El procedimiento de esta sección debe ser realizado por tu administrador de Azure Cloud.
* Puedes eliminar archivos de Data Locker 25 o más horas después de su escritura. No los borres antes.

**Información para el administrador de Azure**

Data Locker es la solución de AppsFlyer para la transmisión de datos a tu cuenta de almacenamiento.

**Para definir una cuenta de almacenamiento para Data Locker:**

1. En tu portal de Azure, ve a [Cuentas de almacenamiento](https://portal.azure.com/#view/HubsExtension/BrowseResource/resourceType/Microsoft.Storage%2FStorageAccounts) de Azure y haz clic en <Image alt="predict_dashboard_plus_symbol.png" src="https://files.readme.io/b1840af83471c0604056a2045752f6d74603a83f371bf89c511e9b53f7e8f218-23044529420305.png" width="18px" />**Crea** una nueva cuenta de almacenamiento para obtener tus datos de AppsFlyer. y haz clic en <Image alt="predict_dashboard_plus_symbol.png" src="https://files.readme.io/b1840af83471c0604056a2045752f6d74603a83f371bf89c511e9b53f7e8f218-23044529420305.png" width="18px" />**Crear** para crear una cuenta de almacenamiento para recuperar tus datos de AppsFlyer.
2. En la pestaña **Básico**
   1. **Suscripción.**
   2. **Grupo de recursos.**  
      Opcional: Si no existe ningún grupo de recursos, haz clic en **Crear nuevo** para crear un grupo de recursos.
3. En **Detalles de instancia:**
   1. Ingresa un **nombre de cuenta de almacenamiento.**
   2. Selecciona una **región** en el menú desplegable.
4. **-> Detalles del proyecto**, selecciona las opciones correspondientes en los menús desplegables:
5. En la pestaña **Seguridad**, selecciona **Habilitar espacio jerárquico.**
6. Haz clic en **Revisar -> Crear.**
7. Cuando finalice la implementación, vuelve a [Azure storage accounts](https://portal.azure.com/#view/HubsExtension/BrowseResource/resourceType/Microsoft.Storage%2FStorageAccounts) y selecciona la cuenta de almacenamiento recién creada.
8. Ve a **Access keys** y copia el **Storage account name** y una de las **claves**.
9. Ve a **Storage browser > Blob containers** y haz clic en <Image alt="predict_dashboard_plus_symbol.png" src="https://files.readme.io/b1840af83471c0604056a2045752f6d74603a83f371bf89c511e9b53f7e8f218-23044529420305.png" width="18px" />**Añadir contenedor.**
   1. Ingresa un **Nombre** para el contenedor nuevo.
   2. Haz clic en **Crear**.
10. Una vez habilitado, en AppsFlyer, ve a <Anchor target="_blank" href="https://hq1.appsflyer.com/datalocker/overview">**Data Locker**</Anchor> **-> <Image alt="predict_dashboard_plus_symbol.png" src="https://files.readme.io/b1840af83471c0604056a2045752f6d74603a83f371bf89c511e9b53f7e8f218-23044529420305.png" width="18px" />Nueva conexión.**
11. En la nueva conexión:
    1. Asigna un nombre a tu conexión.
    2. Selecciona **Azure Blob**.
    3. Introduce el **Container name** de Azure en el campo **Bucket Name** (el que creaste en el paso 9).
    4. Introduce el **Storage account name** que copiaste en el paso 8.
    5. Introduce la **clave** que copiaste en el paso 8.
    6. Haz clic en **Probar conexión**.
    7. **Guardar.**

</Accordion>

<div id="yandex" />

<Accordion title="[Beta] Almacenamiento en la nube de Yandex">

Antes de empezar, ten en cuenta lo siguiente:

* El procedimiento de esta sección debe realizarlo el administrador de Yandex Cloud.
* Puedes eliminar archivos de Data Locker 25 o más horas después de su escritura. No los borres antes.

**Información para el administrador de Yandex Cloud**

Data Locker es la solución de AppsFlyer para la transmisión de datos al almacenamiento.

**Para crear un bucket y otorgar permisos de Data Locker:**

1. En la <Anchor target="_blank" href="https://console.cloud.yandex.com/">Yandex Cloud console</Anchor>, ve a la pestaña **Service Accounts** y haz clic en **Create service account**.
2. Nombra la cuenta de servicio, por ejemplo, `af-datalocker`.
3. Crea una clave de acceso estática para la cuenta de servicio. En la cuenta de servicio:
   1. Haz clic en **Crear una nueva clave**.
   2. Selecciona **Crear clave de acceso estática**.
   3. Guarda el **ID de clave** y la **Clave secreta**.
4. Dale a tu nueva cuenta de servicio el permiso **storage.editor**.
   1. En la configuración del bucket, ve a **Access Bindings** y haz clic en **Assign bindings**.
   2. Para la nueva cuenta de servicio, añade el rol **storage.editor** y haz clic en **Guardar**.
5. Ponte en contacto con tu CSM de AppsFlyer para habilitar Yandex en Data Locker.
6. Una vez habilitado, utiliza el ID de la clave y la clave secreta durante la <Anchor target="_blank" href="/marketers/es/docs/data-locker-for-marketers#set-up-data-locker">configuración de Data Locker</Anchor>.

</Accordion>

## Almacenamiento en la nube de almacén de datos

<div id="bigquery" />

<Accordion title="BigQuery">

El procedimiento de esta sección debe ser realizado por tu administrador de BigQuery.

**Información para el administrador de BigQuery**

Data Locker es la solución de AppsFlyer para la transmisión de datos al almacenamiento.

**Requisitos**

* Crear un conjunto de datos de BigQuery

**Para crear un conjunto de datos de BigQuery:**

1. En BigQuery, crea un proyecto o usa un proyecto existente.
2. En el proyecto, haz clic en **CREAR CONJUNTO DE DATOS**. [![GCSCreateDataSEt_1_.png](https://files.readme.io/702b81dcff4185ce98ad82afd0a9b545f99ef49e3f6292709f3b00330821472c-4405548469521.png)](https://files.readme.io/702b81dcff4185ce98ad82afd0a9b545f99ef49e3f6292709f3b00330821472c-4405548469521.png)
3. Proporciona al conjunto de datos un ID adecuado.

   > 📘 **Nota:**
   >
   > Asegúrate de que el proyecto o conjunto de datos objetivo esté vinculado a una cuenta de facturación activa. Sin una cuenta de facturación, Data Locker no puede crear ni escribir tablas en el destino de BigQuery, y el proceso de configuración de la conexión puede fallar.

4. Otorga a AppsFlyer acceso al conjunto de datos. <Anchor target="_blank" href="https://cloud.google.com/bigquery/docs/control-access-to-resources-iam#grant_access_to_a_resource">Ver instrucciones de Big Query</Anchor>
   * Para **Agregar principal**, utiliza el siguiente usuario de AppsFlyer: [datalocker-bq-admin-prod@datalocker-bq-prod.iam.gserviceaccount.com](mailto:datalocker-bq-admin-prod@datalocker-bq-prod.iam.gserviceaccount.com)
   * En **Asignar roles**, selecciona Editor de datos de BigQuery.
5. Completa la configuración restante según sea necesario.

</Accordion>

<div id="snowflake" />

<Accordion title="Snowflake">

Conecta Data Locker a tu cuenta de Snowflake. Al hacerlo, los datos se envían a Snowflake y continúan estando disponibles en tu almacenamiento en la nube seleccionado.

**Consideraciones para desarrolladores de BI**

* La tasa de actualización de datos es la misma que la de los datos proporcionados en un bucket.
* La estructura de tabla y columna de los datos es equivalente a la que se encuentra en los datos disponibles directamente desde un bucket de Data Locker.
* A medida que se añaden filas al recurso compartido de Snowflake, la columna `_ingestion_time` se completa con la zona horaria local del sistema (no UTC). Para garantizar que cada fila sea única y evitar la ingestión de la misma fila más de una vez:
  1. Guarda el `max_ingestion_time` por tabla ingerida.
  2. Cada vez que ejecutes tu proceso de ingestión, añade solo aquellas filas en las que `_ingestion_time > max_ingestion_time`

Completa los procedimientos siguientes para conectar Snowflake a Data Locker.

#### **Procedimientos de conector de Snowplake**

**Para obtener tu ID de cuenta y región de Snowflake**:

1. En Snowflake, <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/connecting.html#logging-in-using-the-web-interface">inicia sesión en tu cuenta de Snowflake</Anchor>.
2. En la barra de menú, selecciona tu nombre.  
   Se muestra el ID de tu cuenta y la región.

   [<Image alt="Datos de la cuenta Snowflake" src="https://files.readme.io/6f508a5c2c6cd5dd84dd2639c73e62ff819e0a06ea3323d7a999a6b4fc717009-40394499797393.png" width="875px" />](https://files.readme.io/6f508a5c2c6cd5dd84dd2639c73e62ff819e0a06ea3323d7a999a6b4fc717009-40394499797393.png)

**Para conectar Data Locker a Snowflake**:

1. En AppsFlyer, ve a **Reportes** > **Data Locker.**
2. Selecciona Snowflake.
3. Introduce la región de Snowflake y el account locator utilizando la información que recibiste previamente de Snowflake.
4. Haz clic en **Guardar**.

**Para** **crear una base de datos a partir de un recurso compartido en Snowflake**:

1. En Snowflake, <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/connecting.html#logging-in-using-the-web-interface">inicia sesión en tu cuenta de Snowflake</Anchor>.
2. Cambia el rol a **Accountadmin**. Consulta <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/data-share-consumers.html#creating-a-database-from-a-share.">Crear una base de datos a partir de un recurso compartido.</Anchor>
3. Selecciona **Recursos compartidos**.
4. Selecciona el recurso compartido de AppsFlyer. Por ejemplo, APPSFLYER\_ACC\_XXX\_DATA\_LOCKER.
5. Haz clic en **Crear base de datos desde Secure Share** y completa los detalles requeridos. Haz clic en <strong>Siguiente. ¡</strong>Importante!** Debes cargar los datos de la base de datos compartida en tus tablas, porque los datos en la base de datos compartida solo están disponibles por un período limitado (actualmente 14 días).**
6. En tu base de datos, se muestran las tablas importadas. Los nombres y estructuras de las tablas son equivalentes a los de los buckets de Data Locker.

</Accordion>

## Rasgos y limitaciones

| Caducado | Nota |
| --- | --- |
| Conexión a la nube de AppsFlyer | Los reportes no se pueden almacenar sin comprimir |
| Cambio de ubicación del conjunto de datos de BigQuery | Si cambias la ubicación del conjunto de datos en BigQuery, debes volver a guardar tu conexión en AppsFlyer. Dado que no se requiere ningún cambio de configuración real en los ajustes de conexión de AppsFlyer, el botón **Guardar** está deshabilitado. Para habilitar el botón, realiza un cambio temporal, guarda la conexión y, a continuación, revierte el cambio y guarda la conexión de nuevo. |
| Regiones admitidas de Snowflake | **Regiones compatibles**<ul><li>us-east-1</li><li>us-east-2</li><li>us-west-2</li><li>eu-west-1</li><li>eu-west-2</li><li>eu-west-3</li><li>eu-central-1</li><li>eu-north-1</li><li>ca-central-1</li><li>sa-east-1</li><li>ap-sur-1</li><li>ap-southeast-1</li><li>ap-southeast-2</li><li>ap-northeast-1</li><li>ap-northeast-2</li><li>ap-northeast-3</li></ul>**Regiones compatibles con Azure:**<ul><li>australia-east</li><li>east-us-2</li><li>central-us</li><li>southcentral-us</li><li>west-europe</li><li>west-us-2</li></ul>**Regiones compatibles con GCP:**<ul><li>Soporte limitado. Contacta con el soporte técnico de AppsFlyer para verificar la disponibilidad de tu región.</li></ul> |

<div data-zendesk-anchors="bucket-cloud-storage=almacenamiento-en-la-nube-de-bucket h_01HE2SPKYZWFXA63YD5NK4KJRD=almacenamiento-en-la-nube-de-bucket h_01HE2SPKYZM9QQCGFN86J7FNDY=gcs-storage h_01HE2SPKYZK4F9E22MG3K8SJE8=aws-storage supported-aws-regions=regiones-aws-admitidas h_01J2DSZ4NVVMTTNSXP2Z9DAS0Q=regiones-aws-admitidas %5Bbeta%5D-azure-storage=beta--azure-storage h_01HE2SRAJA94R8ZKHRBEFNKX8D=beta--azure-storage h_01HE2SPKYZXAXMKPH5DQV40X1W=yandex data-warehouse-cloud-storage=almacenamiento-en-la-nube-de-almac%C3%A9n-de-datos h_01HE2SPKYZ77X8WP9ZNRB1D05B=almacenamiento-en-la-nube-de-almac%C3%A9n-de-datos h_01HE2SPKYZMNW776CZRZAFVV5H=bigquery h_01JXQM7DAHD40DJYERY106H826=nota h_01HE2SPKYZC3W4G3YXFM10H9D3=snowflake snowflake-connector-procedures=procedimientos-de-conector-de-snowplake h_01HE2SPKYZ11B1MJYX2HRCS07D=procedimientos-de-conector-de-snowplake traits-and-limitations=rasgos-y-limitaciones h_01J6S6HS0H0M6GQ81WGZ3XT0P9=rasgos-y-limitaciones h_01KYVRP8CVMD01EZY5561W2RCJ=rasgos-y-limitaciones" />
