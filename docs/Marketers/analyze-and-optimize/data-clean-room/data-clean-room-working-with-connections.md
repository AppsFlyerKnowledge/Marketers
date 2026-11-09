---
title: Data Clean Room—Trabajar con conexiones
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
  created_at: '2023-03-20T13:18:17Z'
  edited_at: '2026-08-12T11:52:49Z'
  id: 13886278812817
  locale: es
  section: Data Clean Room
  section_id: 4591191779217
  url: https://support.appsflyer.com/hc/es/articles/13886278812817
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En resumen:** Conecta tus servicios en la nube a Data Clean Room para cargar datos y recibir reportes.

<div id="overview" />

## Visión general

Una vez que hayas configurado tus servicios en la nube para usarlos con Data Clean Room (DCR), el siguiente paso es conectarlos al DCR.

* Las conexiones desde las que el DCR lee datos propios de tus sistemas se llaman **conexiones entrantes.** Utilizas estas conexiones al configurar tus fuentes de datos personalizadas.
* Las conexiones a través de las que el DCR entrega reportes después del procesamiento se llaman **conexiones salientes.** Utilizas estas conexiones al configurar tus reportes.

<div id="creating-inbound-connections" />

## Crear conexiones entrantes

Puedes elegir crear conexiones entrantes de una de estas dos formas:

* Antes de usarlas para crear fuentes; ***o***
* Como parte del proceso de creación de la fuente.

En ambos casos, el proceso es el mismo y puedes usar las conexiones creadas exactamente de la misma manera. La única diferencia es el momento y la forma en que inicias el proceso.

**Para crear una nueva conexión entrante fuera del proceso de creación de la fuente:**

1. En la parte superior de la página principal de DCR en AppsFlyer, haz clic en el botón **Gestionar conexiones**:

   <Image align="center" alt="dcr_manage_connections_button.png" src="https://files.readme.io/773e9568a1e9e642f127806fa3b80932699e0db6cc6a124d5a09898577ade645-13909932760593.png" />

   * Si ya tienes conexiones entrantes en tu cuenta, verás el cuadro de diálogo **Gestionar conexiones**. Desde allí, haz clic en el botón ![dcr_new_connection_button.png](https://files.readme.io/ea74c7dd6653a544216addddc5fda2a15126a6a26ba2e3ea0a954c58f4fe479e-13916096900753.png) para abrir el cuadro de diálogo **Nueva conexión**.
   * Si estás creando la primera conexión entrante de tu cuenta, el cuadro de diálogo **Nueva conexión** se abrirá automáticamente.
2. Continúa con las instrucciones en la sección [Completa la conexión](#completa-la-conexión), más abajo.

**Para crear una nueva conexión entrante como parte del proceso de creación de la fuente:**

1. Crea la conexión mientras <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-working-with-sources#2-specify-the-source-location">especificas la ubicación de la fuente</Anchor>.
   * Si no hay conexiones definidas en tu cuenta, se abrirá el cuadro de diálogo **Nueva conexión**, pidiéndote que crees una.
   * Si tienes conexiones existentes pero quieres usar una nueva, haz clic en el ![dcr_new_connection_button.png](https://files.readme.io/ea74c7dd6653a544216addddc5fda2a15126a6a26ba2e3ea0a954c58f4fe479e-13916096900753.png) botón para abrir el **cuadro de diálogo Nueva conexión**.
2. Continúa con las instrucciones en la sección [Completa la conexión](#completa-la-conexión) a continuación.

<div id="complete-the-connection" />

#### Completa la conexión

En el cuadro de diálogo **Nueva conexión**, selecciona el servicio en la nube que vas a conectar al DCR y, a continuación, sigue las instrucciones de la pestaña correspondiente más abajo.

<Image align="center" alt="dcr_create_inbound_connection.png" src="https://files.readme.io/b30606026761528f4a0d3efcc1a3207e8b9c99ca8202f76b2d698a86efaa21ee-13913809617297.png" width="457px" />

<div id="bigquery-inbound" />

<Accordion title="BigQuery">

En el cuadro de diálogo **Nueva conexión**, introduce el **ID del proyecto** de BigQuery correspondiente al proyecto que contiene tu fuente de datos personalizada.

* Puedes obtener esta información en la página de Big Query de tu consola de Google Cloud.

  <Image align="center" alt="BQ_project_ID.png" src="https://files.readme.io/de295dfc0224ff90f041b1aeaf2996828ec1920a715ba668b46a2f50489fd15b-13910856739857.png" width="457px" />

</Accordion>

<div id="snowflake-inbound" />

<Accordion title="Snowflake">

En el cuadro de diálogo **Nueva conexión**, introduce el **ID de la cuenta de Snowflake** y la **región** de la cuenta que contiene tu fuente de datos personalizada. Puedes obtener esta información haciendo clic en el nombre de la cuenta en el menú de la esquina inferior izquierda de tu consola de Snowflake:

* **ADMINISTRADOR DE CUENTA** > **Cuenta** > pasa el cursor sobre la cuenta relevante > **Copiar identificador de cuenta**. <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/admin-account-identifier#finding-the-organization-and-account-name-for-an-account">Consulta aquí la documentación de Snowflake</Anchor>.

<Image align="center" alt="ui-snowsight-account-identifier.png" src="https://files.readme.io/9995c3fd523548de93bafc7c575203e7d38be3b6be2a5e876d7a0a8495ca04c9-24698313004433.png" />

</Accordion>

<div id="s3-gcs-inbound" />

<Accordion title="Amazon S3 y GCS">

En el cuadro de diálogo **Nueva conexión**, introduce el nombre del <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-setting-up-cloud-services#buckets-de-almacenamiento-en-la-nube-amazon-s3-y-gcs">bucket que has creado</Anchor> para el uso exclusivo de DCR.

</Accordion>

<div id="creating-outbound-connections" />

## Crear conexiones de salida

DCR entrega reportes a tus servicios en la nube seleccionados utilizando <Anchor target="_blank" href="/marketers/es/docs/data-locker-for-marketers">AppsFlyer Data Locker</Anchor>. Como los reportes se entregan a través de Data Locker, las conexiones DCR de salida son en realidad conexiones de Data Locker. Puedes elegir crear estas conexiones de la siguiente manera:

* Antes de usarlas para crear reportes (desde la página de Data Locker en AppsFlyer); ***o***
* Como parte del proceso de creación del reporte (desde la página de DCR en AppsFlyer).

En cualquier caso, el proceso es prácticamente el mismo y puedes utilizar las conexiones creadas exactamente de la misma manera.

<div id="note" />

> 📘 **Nota:**
>
> Recibir reportes de DCR no requiere una suscripción Premium a Data Locker. Si estás interesado en recibir otros reportes de AppsFlyer a través de Data Locker, comunícate con tu CSM o envía un correo electrónico a [hello@appsflyer.com](mailto:hello@appsflyer.com).

**Para crear una nueva conexión de salida fuera del proceso de creación del reporte:**

1. En el menú lateral izquierdo de AppsFlyer, selecciona **Reporte > Data Locker.**  
   * Si ya tienes conexiones de Data Locker en tu cuenta, accederás a la página principal de Data Locker. Desde allí, haz clic en el botón ![dcr_dl_new_connection_button.png](https://files.readme.io/8261a480674822371c6e585f995a496a6b5682dd935351375db200bbb1272689-13919327056657.png) de la esquina superior derecha para abrir el cuadro de diálogo **Nueva conexión**.
   * Si estás creando la primera conexión de Data Locker de tu cuenta, verás la página **Comenzar** de Data Locker. Haz clic en el botón ![dcr_dl_get_started_button.png](https://files.readme.io/3176ed5c35cba0939dd36de8c1136d15dc8ce27ee2891894ef65dba92fc7e91a-13919329616657.png) para abrir el cuadro de diálogo **Nueva conexión**.
2. Continúa con las instrucciones en la sección [Completa la conexión](#completa-la-conexión-1) a continuación.

**Para crear una nueva conexión de salida como parte del proceso de creación del reporte:**

1. Crea la conexión mientras estás <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-creating-attribution-data-reports#set-the-report-destination-and-save-the-report">configurando el destino del reporte</Anchor>.
   * Si no hay conexiones definidas en tu cuenta:
     * Se abrirá una nueva pestaña en tu navegador (que muestra la página de AppsFlyer Data Locker)
     * Se abrirá el cuadro de diálogo **Nueva conexión**.
   * Si tienes conexiones existentes pero deseas usar una nueva, haz clic en el botón ![dcr_new_connection_data_locker_button.png](https://files.readme.io/16bf3f34eb9f055bd1935a19620279c83947f6fd6a238b7199366c0497a43ed0-21414410403345.png):
     * Se abrirá una nueva pestaña en tu navegador (que muestra la página de AppsFlyer Data Locker)
     * Se abrirá el cuadro de diálogo **Nueva conexión**.
2. Continúa con las instrucciones de la [Completa la conexión](#completa-la-conexión-1) sección, a continuación.
3. Después de crear la conexión, vuelve a la pestaña DCR de tu navegador y selecciona la conexión recién creada de la lista de conexiones de Data Locker.

<div id="complete-the-connection-1" />

#### Completa la conexión

<div id="important" />

> 🚧 **Importante:**
>
> La opción **AppsFlyer AWS Bucket** no debe usarse para los reportes de DCR.

En el cuadro de diálogo **Nueva conexión**, selecciona el servicio en la nube al que te vas a conectar y, a continuación, sigue las instrucciones de la pestaña correspondiente que aparece más abajo.

<Image align="center" alt="dcr_dl_new_connection_dialog.png" src="https://files.readme.io/fe77a008f036e15f6e192a7a2dc660efd54c92fb3bcceb0be9625420f66893e3-13928181611025.png" />

<div id="bigquery-outbound" />

<Accordion title="BigQuery">

1. En el cuadro de diálogo **Nueva conexión**, introduce un nombre para la conexión y, a continuación, selecciona la opción **BigQuery**.
2. Introduce el **ID del proyecto** y el **nombre del conjunto de datos** del proyecto de BigQuery que contiene el <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-setting-up-cloud-services#bigquery-outbound">conjunto de datos que has creado</Anchor> para Data Locker.  
   * Puedes obtener esta información en la página de Big Query de tu consola de Google Cloud.

     <Image align="center" alt="BQ_project_ID_dataset_name.png" src="https://files.readme.io/c784b0369c51a6e123279fdc5b2fa1fba255ae371d436e9247cb5e4685387983-13928683779089.png" width="457px" />
3. Haz clic en el botón ![dcr_dl_test_connection_button.png](https://files.readme.io/8c789303491a4524515216aca06dc4b3435b5b0baa3aaa8726ff73cce968c5bc-13928683412241.png) para asegurarte de que Data Locker esté conectado al conjunto de datos.
4. Haz clic en **Guardar** para crear la conexión.

</Accordion>

<div id="snowflake-outbound" />

<Accordion title="Snowflake">

El procedimiento para conectar Snowflake a Data Locker es un proceso de 2 pasos:

* **[Paso n.º 1](/docs/data-clean-room-working-with-connections#step-1) –** En AppsFlyer, crea la conexión inicial.
  * Esto le da a tu cuenta de Snowflake la capacidad de acceder a un recurso compartido de Snowflake de AppsFlyer.
* **[Paso n.º 2](/docs/data-clean-room-working-with-connections#step-2) –** En tu cuenta de Snowflake, crea una base de datos a partir del recurso compartido.
  * Esto crea una base de datos en tu cuenta que hace referencia a las tablas en el compartido de AppsFlyer.

**Nota:** El siguiente procedimiento debe ser realizado por un **administrador de cuenta** de Snowflake.

<span id="step-1"></span>**Paso 1 (crear la conexión inicial) –**

1. En el cuadro de diálogo **Nueva conexión**, introduce un nombre para la conexión y, a continuación, selecciona la opción **Snowflake**.
2. Ingresa la región de tu cuenta de Snowflake y el ID de cuenta.
   * Puedes obtener esta información haciendo clic en el nombre de la cuenta en la esquina inferior izquierda de tu consola de Snowflake y, a continuación, pasando el cursor sobre el nombre de la cuenta en la ventana emergente. **Nota:** Busca el ID con la etiqueta **Locator.** Este **NO** es el mismo ID que el que se usa para crear conexiones entrantes de Snowflake.  

     <Image align="center" alt="snowflake_account_locator.png" src="https://files.readme.io/23495b3209129f48ed1ca3442a1e96fac791d46df6f87050ac036893a050e427-13930022354961.png" width="536px" />
3. Haz clic en el botón ![dcr_dl_test_connection_button.png](https://files.readme.io/8c789303491a4524515216aca06dc4b3435b5b0baa3aaa8726ff73cce968c5bc-13928683412241.png) para asegurarte de que Data Locker esté conectado a tu cuenta de Snowflake.
4. Haz clic en **Guardar** para crear la conexión.

<span id="step-2"></span>**Paso 2 (crear una base de datos a partir de un recurso compartido)** –

1. <Anchor target="_blank" href="https://docs.snowflake.com/en/user-guide/connecting.html#logging-in-using-the-web-interface">Inicia sesión en tu cuenta de Snowflake</Anchor>.
2. Cambia tu rol a **Accountadmin** (Administrador de cuenta).
3. En el panel izquierdo, selecciona **Private Sharing.**
4. En la página que se abre, selecciona la pestaña **Compartido contigo** .
5. En el recurso compartido cuyo nombre comienza por **APPSFLYER**, haz clic en el botón **Get data** ![snowflake_get_data_button.png](https://files.readme.io/fbda3603d504f08980bd5329aad49e5e0c562e1de556ffb0e04ad4a1abbac89c-13930725492497.png).
6. [Opcional] En el cuadro de diálogo **Get Data**, cambia el nombre predeterminado de la base de datos según tus necesidades y selecciona, además de Accountadmin, los roles que pueden acceder a la base de datos.
7. Haz clic en **Get Data** para crear la base de datos.

</Accordion>

<div id="s3-gcs-outbound" />

<Accordion title="Amazon S3 y GCS">

1. En el cuadro de diálogo **Nueva conexión** de Data Locker, introduce un nombre para la conexión y, a continuación, selecciona la opción **Amazon S3** o **GCS**.
2. Introduce el nombre del <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-setting-up-cloud-services#buckets-de-almacenamiento-en-la-nube-amazon-s3-y-gcs">bucket que has creado</Anchor> para el uso exclusivo de DCR.

</Accordion>

<div data-zendesk-anchors="overview=visi%C3%B3n-general h_01HKA1AS2QGDTPW85WA07K35M0=visi%C3%B3n-general creating-inbound-connections=crear-conexiones-entrantes h_01HKA1AS2QRRBJAYNKSWWZXE3N=crear-conexiones-entrantes complete-the-connection-inbound=completa-la-conexi%C3%B3n h_01HKA1AS2Q06F07RDD8W384RE2=completa-la-conexi%C3%B3n h_01HKA1AS2QXP5H2HBJ911F3TPZ=bigquery-inbound h_01HKA1AS2QCPC6515FZ45E8Q67=snowflake-inbound h_01HKA1AS2QQZWFMRQD0T0FNQM5=s3-gcs-inbound creating-outbound-connections=crear-conexiones-de-salida h_01HKA1AS2QAV9DJWZQ2703TS0Z=crear-conexiones-de-salida h_01HKA1AS2Q76NP9FY7S4H0QP4D=nota complete-the-connection-outbound=completa-la-conexi%C3%B3n-1 h_01HKA1AS2RKTWNY2ZR7VYAJC90=completa-la-conexi%C3%B3n-1 h_01HKA1AS2R7RFWKM2W89QSEH3V=importante h_01HKA1AS2RJXZPCBKE7ST0SA63=bigquery-outbound h_01HKA1AS2R7TV495V39N35CWAR=snowflake-outbound h_01HKA1AS2RBTK8NZF09BYWDX2G=s3-gcs-outbound" />
