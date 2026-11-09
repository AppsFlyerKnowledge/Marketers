---
title: Plataforma de colaboración de datos - Añadir conexiones
metadata:
  keywords:
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Clean Room
  created_at: '2024-04-28T13:26:59Z'
  edited_at: '2026-08-12T11:53:36Z'
  id: 24603890457617
  locale: es
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/es/articles/24603890457617
---
> **En resumen:** Configura las conexiones de DCP para conectar tus fuentes de datos, enriquecer tus datos y exportar audiencias al almacenamiento en la nube y a partners de medios.

<div id="about-dcp-connections" />

## Sobre las conexiones DCP

Las conexiones determinan cómo DCP ingiere tus datos y exporta tus audiencias. Después de <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-set-up-your-cloud-services">configurar tus servicios en la nube</Anchor>, conéctalos a DCP mediante la ventana modal **Gestionar conexiones**. Están disponibles los siguientes tipos de conexión:

* [**Conexiones de fuentes**](#create-source-connections): para ingerir tus datos propios en DCP desde un almacenamiento en la nube o un data warehouse.
* [**Conexiones de almacenamiento en la nube**](#create-cloud-storage-connections): para exportar tus audiencias a tus buckets de Amazon S3 o Google Cloud Storage (GCS).
* [**Conexiones con partners de medios**](#create-media-partner-connections): para enviar tus audiencias a plataformas publicitarias para su activación.
* [**Conexiones de datos e identidad**](#create-data-identity-connections) : para unificar datos fragmentados de usuarios, mejorar las tasas de coincidencia y ampliar las audiencias del partner.

DCP admite distintos servicios en la nube según el tipo de conexión. Consulta la siguiente tabla para ver qué servicios puedes utilizar para cada tipo de conexión:

| Servicios en la nube | Fuente (de entrada) | Exportación de almacenamiento en la nube (salida) |
| --- | --- | --- |
| Amazon S3 | ✓ | ✓ |
| Google Cloud Storage (GCS) | ✓ | ✓ |
| BigQuery | ✓ | - |
| Snowflake | ✓ | - |
| Salesforce Cloud/CRM | ✓ | - |

En Amazon S3 y Google Cloud Storage, una única conexión funciona tanto como fuente (entrada) como destino de exportación al almacenamiento en la nube (salida). Al crear una conexión de fuente para S3 o GCS, también se crea automáticamente la conexión correspondiente de almacenamiento en la nube (exportación), y viceversa.

<div id="create-source-connections" />

<Accordion title="Crear conexiones de fuentes">

Crea conexiones de fuentes para incorporar tus datos propios a DCP.

**Para crear una conexión de fuentes:**

1. En AppsFlyer, ve a **Colaborar** > **Data Clean Room**.
2. Haz clic en **Gestionar conexiones**, en la esquina superior derecha.
3. Ve a la pestaña **Fuente** y haz clic en **+ Nueva conexión**.  
   <Image align="center" alt="2026-07-27_13-30-46.png" src="https://files.readme.io/dec879432c0b9d6ba4eeec2c175dfce145c99652ccabb02d37f3434627f9310f-49189748198289.png" width="529px" />
4. Continúa con las [instrucciones para las conexiones de servicios en la nube para datos de la fuente](#conexiones-de-servicios-en-la-nube-para-datos-de-la-fuente) que aparecen a continuación.

También puedes crear una conexión de la fuente directamente al configurar una fuente. Consulta <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources">Crear y gestionar orígenes</Anchor> para obtener instrucciones.

<div id="note" />

> 📘 **Nota**
>
> Al crear una conexión de fuentes de entrada para Amazon S3 o GCS, también se crea automáticamente la conexión de salida correspondiente de almacenamiento en la nube (y viceversa). Al eliminar una conexión de Amazon S3 o GCS, también se elimina automáticamente la otra. Como en realidad se trata de una única conexión, al eliminarla desde cualquiera de las pestañas se elimina de todos los lugares donde se utiliza.

<div id="cloud-service-connections-for-source-data" />

#### Conexiones de servicios en la nube para datos de la fuente

Las conexiones de fuentes sirven para conectar de forma segura tus fuentes de datos a DCP. En **Nueva conexión**, selecciona tu servicio en la nube y completa la información correspondiente a tu proveedor.

**BigQuery:** En **Nueva conexión**, introduce el **ID del proyecto** de BigQuery correspondiente al proyecto que contiene tus datos de la fuente. Puedes encontrarlo en la página de BigQuery de tu Google Cloud Console.

**Snowflake:** En **Nueva conexión**, introduce el **ID de la cuenta de Snowflake** y la **región** de la cuenta que contiene tus datos de la fuente. Para encontrarlo, haz clic en el nombre de la cuenta en la esquina inferior izquierda de la consola de Snowflake:

**ADMINISTRADOR DE CUENTA** > **Cuenta** > pasa el cursor sobre la cuenta relevante > **Copiar identificador de cuenta**. Consulta la <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/admin-account-identifier#finding-the-organization-and-account-name-for-an-account">documentación de Snowflake</Anchor> para obtener más información.

<div id="important" />

> 🚧 **¡Importante!**
>
> Busca el ID con la etiqueta **Locator**. Este **no** es el mismo ID que se utiliza para crear conexiones de salida de Snowflake.

**Amazon S3 and GCS:** En **Nueva conexión**, introduce el nombre del <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-set-up-your-cloud-services#cloud-storage-buckets-inbound">bucket que has creado</Anchor> para uso exclusivo de AppsFlyer Data Clean Room (DCR).

**Salesforce Cloud/CRM:** Consulta <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-integration-with-salesforce-data-cloud">cómo configurar una conexión con Salesforce</Anchor>.

<div id="local-file-connection" />

#### Conexión de archivo local

Las conexiones de archivos locales te permiten cargar archivos de datos directamente desde tu ordenador a DCP. Esta opción suele utilizarse únicamente para realizar pruebas y no se recomienda para procesos continuos o de gran volumen de ingesta de datos.

<div id="set-up-a-local-file-connection" />

<Accordion title="Configurar una conexión de archivo local">

Se utiliza una conexión de archivo local para probar la plataforma utilizando un archivo de muestra. Te permite familiarizarte con las funcionalidades de DCP antes de empezar a compartir datos. Ten en cuenta que no se recomienda para compartir datos, tiene un periodo de conservación de datos limitado a 14 días y no admite procesos de automatización.

Una conexión de archivo local puede <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources#ubicación-de-la-fuente-como-archivos-locales">configurarse durante la creación de la fuente</Anchor>.

</Accordion>

</Accordion>

<div id="create-cloud-storage-connections" />

<Accordion title="Crear conexiones de almacenamiento en la nube">

Las conexiones de almacenamiento en la nube te permiten exportar automáticamente tus audiencias de DCP a tu bucket de Amazon S3 o Google Cloud Storage (GCS) después de cada actualización de la audiencia.

**Para crear una conexión de almacenamiento en la nube:**

1. En AppsFlyer, ve a **Colaborar** > **Data Clean Room**.
2. Haz clic en **Gestionar conexiones**, en la esquina superior derecha.
3. Ve a la pestaña **Almacenamiento en la nube** y haz clic en **+ Nueva conexión**.  
   <Image align="center" alt="2026-07-27_13-30-34.png" src="https://files.readme.io/1da10127617317d0ff466433c89712d78c104b6a943b4b669e1d7180d22df958-49189843742609.png" width="533px" />
4. Se abre la ventana **Nueva conexión de almacenamiento en la nube**.
5. En la ventana **Nueva conexión de almacenamiento en la nube**, selecciona tu proveedor de servicios en la nube: **Google Cloud Storage** o **Amazon Simple Storage**.
6. Introduce el nombre de tu bucket:
   * **GCS:** Introduce el nombre del bucket de GCS con el formato `gs://my-bucket`.
   * **S3:** Introduce el nombre del bucket de S3.
7. Haz clic en **Probar conexión** para verificar que DCP puede conectarse a tu bucket.
8. Haz clic en **Guardar**. La nueva conexión aparece en **Tus conexiones de almacenamiento en la nube**, dentro de la pestaña **Almacenamiento en la nube**.

También puedes crear una conexión de almacenamiento en la nube directamente desde el creador de audiencias. Consulta <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-build-and-activate-audiences">Crear y activar audiencias</Anchor> para obtener instrucciones.

<div id="understand-export-path" />

<Accordion title="Comprender la ruta de exportación">

Cada vez que se exporta una audiencia, DCP la escribe en tu bucket siguiendo una ruta fija y predecible:

```
<bucket>/dcp-output/audiences/<collaboration-id>/t=<audience_name>_<id>/dt=<YYYY-MM-DD>/v=<version>/<file>.csv
```

**Ejemplo del contenido de una carpeta para una entrega:**

```
s3://af-dcr-example-bucket/dcp-output/audiences/8f3a1c02-44b1-4e9a-9c7d-2b6e1a0f5d3e/t=example_audience_6148a3/dt=2026-07-18/v=1/\n  ├── part-00000-a1b2c3d4-e5f6-47a8-9b0c-1d2e3f4a5b6c-c000.csv\n  ├── part-00001-a1b2c3d4-e5f6-47a8-9b0c-1d2e3f4a5b6c-c000.csv\n  └── _SUCCESS
```

| Segmento de la ruta | Qué significa |
| --- | --- |
| Sin embargo, asegúrate de crear plantillas separadas con el subdominio; no agregues manualmente el subdominio al ID de plantilla. | Tu bucket conectado de S3 o GCS. |
| dcp-output/audiencias/ | Carpeta fija que DCP crea automáticamente para todas las exportaciones de audiencias. |
| Sin embargo, asegúrate de crear plantillas separadas con el subdominio; no agregues manualmente el subdominio al ID de plantilla. | El ID único de la colaboración a la que pertenece esta audiencia. Puedes encontrarlo en la URL de la colaboración en DCP. |
| t=\_ | El nombre de la audiencia (con los espacios y caracteres especiales sustituidos por guiones bajos), además de un ID único. Esto garantiza que una audiencia eliminada y creada de nuevo con el mismo nombre nunca sobrescriba ni entre en conflicto con archivos anteriores. |
| dt= | La fecha de entrega. |
| v= | Un número de versión para las exportaciones de esta audiencia. Aumenta con cada nueva entrega. |
| part-NNNNN--c000.csv | Uno de los archivos de salida de esta entrega; consulta “Formato de archivo y división” más abajo. |
| \_SUCCESS | Un archivo marcador vacío que se genera cuando la exportación termina de escribir todos los archivos parciales. |

<div id="note-1" />

> 📘 **Nota**
>
> Esta estructura de carpetas se crea y gestiona automáticamente. Cualquier proceso automatizado que lea estos archivos debe seguir este patrón de ruta y esperar a que aparezca \_SUCCESS antes de procesar los archivos parciales para evitar leer una entrega incompleta.

**Formato de archivo y división**

* Las audiencias siempre se exportan como archivos CSV sin comprimir, con dos columnas: `value` (el identificador) y `taxonomy` (el tipo de identificador).
* Las audiencias de mayor tamaño pueden entregarse en varios archivos en lugar de uno solo, numerados como `part-00000`, `part-00001`, etc. De forma predeterminada, cada archivo contiene hasta aproximadamente 500.000 filas.
* Un único archivo puede contener una combinación de tipos de identificadores en las mismas filas. Filtra utilizando la columna `taxonomy` para obtener los identificadores que necesitas. Entre los valores habituales de la taxonomía se incluyen `customer_id`, `mobile_ad_id`, `hashed_email` y `hashed_phone_number_without_plus_sha256`.

**Ejemplo:**

```
valor,taxonomy
6f1a2b3c4d5e6f7a8b9c0d1e2f3a4b5c,customer_id
1a2b3c4d-5e6f-4a7b-8c9d-0e1f2a3b4c5d,mobile_ad_id
b7e2c9a1f4d6e8b0a2c4d6e8f0a1b3c5d7e9f1a3b5c7d9e0f2a4b6c8d0e2f4a6,hashed_email
c1d3e5f7a9b1c3d5e7f9a1b3c5d7e9f1a3b5c7d9e1f3a5b7c9d1e3f5a7b9c1d3,hashed_phone_number_without_plus_sha256
```

</Accordion>

</Accordion>

<div id="create-media-partner-connections" />

<Accordion title="Crear conexiones con partners de medios">

Las conexiones de salida con partners de medios te permiten conectar de forma segura tus audiencias de DCP con partners de medios compatibles para activar campañas personalizadas en sus plataformas. Los partners de medios son el principal destino para la activación de audiencias. Descubre cómo <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-media-partner-connections">configurar conexiones específicas con partners de medios</Anchor>.

**Para crear una conexión con un partner de medios:**

1. En AppsFlyer, ve a **Colaborar** > **Data Clean Room**.
2. Haz clic en **Gestionar conexiones**, en la esquina superior derecha.
3. En AppsFlyer, ve a **Colaborar** > **Data Clean Room**. Si ya tienes conexiones creadas, aparecerán en la lista de **Partners de medios**.
4. En **Nueva conexión con un partner de medios**, selecciona el partner de medios correspondiente.
5. Ingresa un nombre de conexión.
6. Inicia sesión en la cuenta del partner de medios con tus credenciales y sigue sus instrucciones para conceder acceso a AppsFlyer.
7. Haz clic en **Seleccionar ID de cuenta** y selecciona la cuenta relevante para esta conexión.
8. Haz clic en **Guardar**. La nueva conexión se añade a la lista de partners.

También puedes crear una conexión con un partner de medios directamente desde el creador de audiencias. Consulta <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-build-and-activate-audiences">Crear y activar audiencias</Anchor> para obtener instrucciones.

</Accordion>

<div id="create-data-identity-connections" />

<Accordion title="Crear conexiones de datos e identidad">

Las conexiones de datos e identidad unifican datos fragmentados de usuarios para mejorar las tasas de coincidencia con los partners de activación. Esto permite ampliar las audiencias del partner y aumentar el impacto de tus campañas.

#### ID5

<Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-enrich-sources-with-id5">Enriquece tus datos propios con identificadores de ID5</Anchor> para unificar datos fragmentados de usuarios, mejorar las tasas de coincidencia con los partners de activación y aumentar el tamaño de las audiencias del partner.

<div id="see-also" />

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-set-up-your-cloud-services">DCP: configurar tus servicios en la nube</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-build-and-activate-audiences">DCP: crear y activar audiencias</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-media-partner-connections">DCP: conexiones con partners de medios</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-enrich-sources-with-id5">DCP: enriquecer orígenes con ID5</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-guide">Guía de la plataforma de colaboración de datos (DCP)</Anchor>

</Accordion>

<div data-zendesk-anchors="about-dcp-connections=sobre-las-conexiones-dcp h_01KXX80P91T92MH8KEGHVG3QP1=sobre-las-conexiones-dcp h_01KXX80P913HRREW60M6S316PP=create-source-connections h_01KY4HCGBBCD5FZD9RYNNVDYRC=nota source-cloud-service-connections=conexiones-de-servicios-en-la-nube-para-datos-de-la-fuente cloud-service-connections-for-source-data=conexiones-de-servicios-en-la-nube-para-datos-de-la-fuente h_01KXX80P914VFMH1T6FQF9KC31=importante local-file-connection=conexi%C3%B3n-de-archivo-local h_01KXX80P91EFCGH3MYV729TGTH=conexi%C3%B3n-de-archivo-local h_01KXX80P91HG17YTWE15ZWTBZ8=set-up-a-local-file-connection h_01KXX80P91F8TG9FR1XQ7QVNCY=create-cloud-storage-connections h_01KYEP2MX3KQ3BAP7VRSGYTFBB=understand-export-path h_01KYEP2MX3SHFCECTSTHV9RMS4=nota-1 h_01KXX80P91BMB45ETZQSKWJWZB=create-media-partner-connections h_01KXX80P91PS35EG5P5YJB9EHC=create-data-identity-connections h_01KXX80P92BXD3B7ZVT1FC5HCF=id5 h_01KXX80P92WMPPRGD7321TBS7Y=consulta-tambi%C3%A9n" />
