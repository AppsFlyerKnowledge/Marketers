---
title: Data Locker para marketers
metadata:
  keywords:
    - Reports
    - Data Locker
    - Advertisers
    - Raw Data
    - Developers
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Data Locker
  created_at: '2019-02-03T12:20:08Z'
  edited_at: '2026-08-12T11:51:39Z'
  id: 360000877538
  locale: es
  section: Data Locker
  section_id: 6550945728657
  url: https://support.appsflyer.com/hc/es/articles/360000877538
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En resumen:** Data Locker envía los datos de tus reportes al almacenamiento en la nube para cargarlos en tus sistemas de BI. Puedes seleccionar entre diferentes destinos de almacenamiento: Un bucket de AppsFlyer en AWS, o almacenamiento de tu propiedad en AWS, GCS, Yandex, BigQuery y Snowflake. Data Locker admite [varios destinos](/docs/data-locker-for-marketers#multipleconnections-principles-more-than-one-destination). Esto significa que puedes enviar todos los datos a varios destinos, separar los datos por destino o una combinación de ambos.

## Descripción general

![6133DataLockerForAdvertisers.png](https://files.readme.io/820fee89515ccdcdfac2043bcb9fde722ddc8ec852a140ec250378c581d9c375-32966274469649.png)

En Data Locker, selecciona tus aplicaciones, fuentes de medios, eventos y reportes para incluirlos en los datos que AppsFlyer entrega a tus opciones de almacenamiento en la nube seleccionadas. Luego, carga los datos programáticamente desde el almacenamiento a tus sistemas.

<div id="data-locker-features" />

<Accordion title="Data Locker: funciones">

| Característica | Descripción |
| --- | --- |
| [Opciones de almacenamiento (cloud)](/docs/data-locker-for-marketers#storage-options) | Data Locker puede enviar tus datos a cualquiera de los siguientes proveedores de servicios en la nube:<ul><li>Almacenamiento propiedad de AppsFlyer en AWS</li><li><Anchor target="_blank" href="/marketers/es/docs/data-locker-cloud-service-setup">Almacenamiento propio</Anchor> en:<ul><li>AWS</li><li>GCS</li><li>[Beta] Azure Blob</li><li>[Beta] Yandex</li><li>BigQuery</li><li>Snowflake</li></ul></li></ul>Puedes establecer más de un destino en Data Locker. Esto significa que puedes enviar todos o algunos de tus datos a [múltiples destinos](/docs/data-locker-for-marketers#multipleconnections-principles-more-than-one-destination).<br /><br />**Ejemplos**<ul><li>Separa los datos por tipo de reporte. Envía el raw data a GCS y los datos agregados a Snowflake.</li><li>Separa los datos por aplicación y envía los datos por grupo de aplicaciones a diferentes buckets.</li></ul> |
| Aplicaciones múltiples | Envía datos de 1, más o todas las aplicaciones de tu cuenta. Cuando agregas aplicaciones a la cuenta, se pueden incluir automáticamente. |
| Ventana de disponibilidad | 14 días |
| [Segregación de datos](/docs/data-locker-for-marketers#app-segregation) | Opciones de segregación de datos disponibles (relevantes para el almacenamiento en un bucket en la nube):<ul><li>[Predeterminada] **Unificada:** Datos de todas las aplicaciones combinadas. El campo ID de aplicación a nivel fila se utiliza para identificar la aplicación en archivos de datos.</li><li>**Segregados por aplicación:** Los datos de cada aplicación están en una carpeta separada. El nombre de la carpeta es el ID de la aplicación.</li></ul> |
| Opciones de formato de datos | <ul><li>Para el almacenamiento en un bucket en la nube:<ul><li>CSV</li><li>PARQUET</li><li><Anchor target="_blank" href="/marketers/es/docs/adobe-experience-platform-aep-integration-with-appsflyer-data-locker">Adobe</Anchor></li></ul></li><li>Almacén de datos</li></ul> |
| Actualización de los datos | La actualización depende del tipo de reporte<ul><li>**Por hora:** Los datos se generan continuamente; por ejemplo, los datos de instalaciones y eventos in-app se escriben dentro de las horas posteriores a la llegada del evento a AppsFlyer.</li><li>**A diario:** Los reportes como los de desinstalaciones, se generan diariamente y están listos al día siguiente.</li><li>**Versionado:** Si se genera el mismo reporte varias veces durante el mismo período de tiempo, se implementa un mecanismo de versionado.</li></ul> |

</Accordion>

<div id="reports-available-via-data-locker" />

<Accordion title="Reportes disponibles en Data Locker">

<Anchor target="_blank" href="/marketers/es/docs/data-locker-advertiser-reports">Reportes disponibles en Data Locker</Anchor>

</Accordion>

<div id="set-data-locker-report-settings" />

## Configurar la configuración del reporte de Data Locker

Para configurar Data Locker, sigue estos pasos para conectar tu servicio en la nube, definir la configuración de exportación y personalizar el contenido del reporte:

<div id="1-set-up-your-cloud-service" />

<Accordion title="1. Configura tu servicio en la nube">

Puedes conectar tu Data Locker a uno o más proveedores de servicios en la nube. Consulta lo siguiente para obtener instrucciones sobre cómo configurarlos para que funcionen con Data Locker:

* <Anchor target="_blank" href="/marketers/es/docs/data-locker-cloud-service-setup#aws-storage">AWS</Anchor> bucket
* <Anchor target="_blank" href="/marketers/es/docs/data-locker-cloud-service-setup#gcs-storage">GCS</Anchor> bucket
* [Beta] <Anchor target="_blank" href="/marketers/es/docs/data-locker-cloud-service-setup#beta--azure-storage">Azure</Anchor> Blob
* [Beta] <Anchor target="_blank" href="/marketers/es/docs/data-locker-cloud-service-setup#yandex">Yandex</Anchor> bucket
* Almacén de datos de <Anchor target="_blank" href="/marketers/es/docs/data-locker-cloud-service-setup#bigquery">BigQuery</Anchor>
* <Anchor target="_blank" href="/marketers/es/docs/data-locker-cloud-service-setup#snowflake">Snowflake</Anchor> almacén de datos

[Práctica recomendada]: Si no tienes una suscripción a Data Locker y accedes al análisis de cohortes o a los datos de SKAN, debes completar igualmente un procedimiento de servicio de almacenamiento en la nube propio del marketer.

</Accordion>

<div id="2-add-a-connection-to-your-cloud-service" />

<Accordion title="2. Agrega una conexión a tu servicio en la nube">

Después de configurar tu cuenta de servicio en la nube para trabajar con Data Locker (consulta "Configurar tu servicio en la nube" arriba), crea una conexión en Data Locker utilizando las credenciales de tu cuenta. Puedes crear hasta dos conexiones.

<div id="note" />

> 📘 **Nota**
>
> Por defecto, cada cuenta puede abrir hasta **2 conexiones de Data Locker**. Si necesitas conexiones adicionales, contacta con tu Customer Success Manager (CSM).

Para crear una conexión para tu proveedor de nube, realiza los siguientes pasos:

1. En AppsFlyer, desde la barra lateral, ve a **Exportar** > **Data Locker**.
2. En el lado derecho, haz clic en **Nueva conexión.**
3. En **Nombre de la conexión** ingresa el nombre de tu conexión. Utiliza solo letras minúsculas, números y guiones.
4. Haz clic en el ícono del servicio en la nube al que deseas conectarte.
5. Dependiendo del servicio que has seleccionado, ingresa la siguiente información de conexión.

   <div id="aws-cloud-bucket-connection" />

   <Accordion title="Conexión al bucket de la nube de AWS">

   Antes de configurar la conexión de AWS, crea un bucket de AWS. Para aprender, consulta <Anchor target="_blank" href="/marketers/es/docs/data-locker-cloud-service-setup#aws-storage">aquí</Anchor>.

   Para establecer la conexión:

   1. Introduce el nombre de tu bucket AWS S3. El prefijo `af-` es obligatorio, y debe introducirse manualmente.
   2. Haz clic en **Probar conexión**.
   3. Verifica que no se muestre ningún mensaje de error que indique que la ruta del bucket es inválida.
   4. Selecciona si deseas **hacer que esta conexión sea compatible con Adobe Experience Platform**. Si está seleccionado, haz clic en **Guardar** y continúa con [seleccionar filtros a nivel global](#select-global-level-filters).
   5. Haz clic en **Guardar**.

   </Accordion>

   <div id="gcs-cloud-bucket-connection" />

   <Accordion title="Conexión de bucket de GCS">

   Antes de configurar la conexión de GCS, crea un bucket en GCS. Para aprender cómo, haz clic <Anchor target="_blank" href="/marketers/es/docs/data-locker-cloud-service-setup#gcs-storage">aquí</Anchor>.

   Para establecer la conexión:

   1. Introduce el **nombre de tu bucket de GCS**.
   2. Haz clic en **Probar conexión**.
   3. Verifica que no se muestre ningún mensaje de error que indique que la ruta del bucket es inválida.
   4. Selecciona si deseas **hacer que esta conexión sea compatible con Adobe Experience Platform**. Si está seleccionado, haz clic en **Guardar** y continúa con [seleccionar filtros a nivel global](#select-global-level-filters).
   5. Haz clic en **Guardar**.

   </Accordion>

   <div id="azure-cloud-bucket-connection" />

   <Accordion title="Conexión de bucket de Azure">

   Antes de configurar la conexión de Azure, abre una cuenta de almacenamiento en Azure. Para aprender cómo, haz clic <Anchor target="_blank" href="/marketers/es/docs/data-locker-cloud-service-setup#beta--azure-storage">aquí</Anchor>.

   Para establecer la conexión:

   1. Ingresa tu **nombre de conexión**, **nombre de cuenta de almacenamiento** y **clave**.
   2. Verifica que no se muestre ningún mensaje de error que indique que la ruta del bucket es inválida.
   3. Selecciona si deseas **hacer que esta conexión sea compatible con Adobe Experience Platform**. Si está seleccionado, haz clic en **Guardar** y continúa con [seleccionar filtros a nivel global](#select-global-level-filters).
   4. Haz clic en **Guardar**.

   </Accordion>

   <div id="yandex-cloud-bucket-connection" />

   <Accordion title="Conexión del bucket de Yandex Cloud">

   Antes de configurar la conexión de AWS, crea una cuenta de servicio en Yandex. Para aprender cómo, haz clic <Anchor target="_blank" href="/marketers/es/docs/data-locker-cloud-service-setup#yandex">aquí</Anchor>.

   Para establecer la conexión:

   1. Ingresa tu **Nombre de bucket**, **Clave de acceso** y **Clave secreta**.
   2. Verifica que no se muestre ningún mensaje de error que indique que la ruta del bucket es inválida.
   3. Selecciona si deseas **hacer que esta conexión sea compatible con Adobe Experience Platform**. Si está seleccionado, haz clic en **Guardar** y continúa con [seleccionar filtros a nivel global](#select-global-level-filters).
   4. Haz clic en **Guardar**.

   </Accordion>

   <div id="bigquery-data-warehouse-connection" />

   <Accordion title="Conexión de almacén de datos de BigQuery">

   Antes de configurar la conexión de BigQuery, crea un conjunto de datos en BigQuery. Para aprender cómo, haz clic <Anchor target="_blank" href="/marketers/es/docs/data-locker-cloud-service-setup#bigquery">aquí</Anchor>.

   Para establecer la conexión:

   1. Introduce tu ID de proyecto de BigQuery y el nombre del conjunto de datos.
   2. Haz clic en **Probar conexión**.
   3. Verifica que no se muestre ningún mensaje de error que indique que la ruta del bucket es inválida.
   4. Haz clic en **Guardar** y continúa a [seleccionar filtros a nivel global](#select-global-level-filters).

   </Accordion>

   <div id="snowflake-data-warehouse-connection" />

   <Accordion title="Conexión de almacén de datos de Snowflake">

   Antes de configurar la conexión de Snowflake, abre una cuenta en Snowflake. Para aprender cómo, haz clic <Anchor target="_blank" href="/marketers/es/docs/data-locker-cloud-service-setup#snowflake">aquí</Anchor>.

   Para establecer la conexión:

   1. Introduce tu región de Snowflake y tu ID de cuenta.
   2. Haz clic en **Probar conexión**.
   3. Verifica que no se muestre ningún mensaje de error que indique que la ruta del bucket es inválida.
   4. Haz clic en **Guardar** y continúa a [seleccionar filtros a nivel global](#select-global-level-filters).

   </Accordion>

6. Haz clic en **Guardar. Se muestra** la sección **Configuración de salida del reporte**.

<div id="note-1" />

> 📘 **Nota**
>
> Puedes [usar el registro de auditoría](#track-connection-changes-in-the-audit-log) para confirmar si se creó, actualizó o eliminó una conexión, y quién hizo el cambio.

</Accordion>

<div id="3-set-the-report-output-settings" />

<Accordion title="3. Configura las opciones de salida del reporte">

Después de configurar la conexión con el servicio en la nube, puedes continuar configurando las opciones generales de salida de reportes de tu Data Locker. **Si tu servicio en la nube es BigQuery o Snowflake, puedes omitir este paso**.

1. Bajo la sección **Configuración de salida del reporte**, selecciona la estructura de carpetas ([segregación de datos](/docs/data-locker-for-marketers#app-segregation)):
   * **Unificado** (predeterminado): Los archivos de reportes incluyen registros de todas las aplicaciones.
   * **Segregados por aplicación:** Cada archivo de reporte está dedicado a una aplicación.
2. Selecciona el formato de archivo de reportes: Parquet (predeterminado) o CSV.
3. Selecciona el tipo de compresión de archivo del reporte:
   * Snappy (solo disponible para archivos Parquet)
   * GZIP
4. Selecciona el número máximo de filas que deseas en tu archivo: Ya sea 10k, 25k, 50, 100k, 200k o 500k. Más filas en el archivo significa menos archivos pero un tamaño de archivo más grande.

   <div id="note-2" />

   > 📘 **Nota**
   >
   > Bajo **Ruta esperada**, visualiza los patrones de ruta para tus reportes. Nota: La ruta real puede ser diferente a la que se muestra.


</Accordion>

<div id="select-global-level-filters" />

<Accordion title="4. Selecciona filtros a nivel global">

Los filtros a nivel global te permiten **filtrar tus reportes por aplicaciones o fuentes de medios**. Estos filtros se aplican a la mayoría de los reportes en tu cuenta de Data Locker, pero también puedes configurarlos a nivel de reporte (mira [7-select-the-reportlevel-filters](#select-the-report-level-filters) a continuación). Si el mismo filtro se aplica en ambos niveles, el filtro a nivel de reporte tiene prioridad.

Para aplicar un filtro, realiza lo siguiente:

1. En la sección **Reportes**, haz clic en el filtro y selecciona los elementos a incluir en el reporte. Por ejemplo, haz clic en <Image alt="Untitled.png" src="https://files.readme.io/817568835d9f564c139dca673bf30f570f3f4984deb466b91509404b10634ef4-34623601353745.png" width="53px" /> el filtro **Aplicaciones** y selecciona las aplicaciones a incluir en los reportes.
2. Luego haz clic en el botón Enter (⏎).

</Accordion>

<div id="5-select-the-report" />

<Accordion title="5. Selecciona el grupo de reportes">

Selecciona los reportes que deseas obtener en tu servicio en la nube. Los reportes se enumeran en grupos. Hacer clic en el nombre del grupo de reportes expande o colapsa los grupos.

* Para seleccionar un reporte, haz clic en <Image alt="down.png" src="https://files.readme.io/3f59bcc54434374270c0099394a740cc650a3b4a1be0f3f34d298be1ebcad40c-34623601355409.png" width="20px" /> para expandir el grupo de reportes. Para cada reporte en el grupo, se presenta la siguiente información:
  * **Nombre del reporte:** El título del reporte.
  * **Nombre del conjunto de datos:** El nombre del conjunto de datos que contiene los registros del reporte.
  * **Actualización de los datos:** Con qué frecuencia se actualiza el reporte con nuevos registros (por ejemplo, cada hora, diariamente o por versiones).
  * **Campos:** el número de campos (o columnas) que has seleccionado para el reporte en comparación con el número total de campos disponibles para selección.

</Accordion>

<div id="customize-or-duplicate" />

<Accordion title="6. Personaliza o duplica el reporte">

Después de seleccionar uno o más reportes de un grupo de reportes, puedes optar por **personalizar el reporte original** o **crear una copia personalizada separada** duplicándolo. Esto te permite adaptar los campos y filtros del reporte a tus necesidades específicas sin afectar la versión original.

**Opción A: Personaliza el reporte original**

1. Haz clic en el botón **Personalizar** <Image alt="customize.png" src="https://files.readme.io/35f4653b944cd5dc81c6de76f8dcacd9c3413ea49915ba2b5865a244ede3c4b6-35437232722833.png" width="20px" /> junto al nombre del reporte.
2. Se abrirá el editor de reportes, lo que te permitirá seleccionar campos y aplicar filtros.
3. Los cambios se guardarán en la configuración del reporte original.

*Nota: Esto modifica cómo se entrega el reporte a tu almacenamiento en la nube.*

**Opción B: Duplica el reporte**

* Haz clic en <Image alt="Untitled 2.png" src="https://files.readme.io/b3792460554dedede76f7d78346490280d3bfe00d38696a04c6d8f6f283e0f20-34623592674321.png" width="5px" /> junto al nombre del reporte.
* Selecciona <Image alt="duplicate2.png" src="https://files.readme.io/d8fbf09b3a8e3839f80a0a4fec90e0360dc1c2a4a066bf58438364c0d8a15c65-35439088509073.png" width="17px" /> **Duplicar** del menú desplegable.
* Se creará una copia del reporte, nombrada con el prefijo `copy_of_`.
* El reporte duplicado se abre en modo de edición para una mayor personalización.

*Consejo: Duplicar es ideal para crear variaciones de un reporte para diferentes casos de uso.*

Después de elegir si personalizar o duplicar, procede a configurar los campos del reporte como se describe en el siguiente paso.

</Accordion>

<div id="6-select-the-report-fields" />

<Accordion title="7. Selecciona los campos del reporte">

Una vez que hayas elegido personalizar o duplicar un reporte, el siguiente paso es definir qué campos de datos deben incluirse. Cada reporte proporciona un conjunto completo de campos disponibles, y puedes personalizar tu selección para incluir solo lo que es relevante para tu análisis o integración. Por defecto, todos los campos están seleccionados, pero puedes refinar el reporte eligiendo manualmente campos específicos.

Selecciona los campos que deseas incluir en el reporte:

1. En el cuadro de diálogo del reporte seleccionado, en la pestaña **Campos**, pasa el cursor sobre cualquier campo para ver su descripción.

   [![HQ1_2024-08-26_15.44.23.png](https://files.readme.io/293d227464e3907982e0c82187915ee1b16386a4111e83ebd8db065ade64a48b-34623601367697.png)](https://files.readme.io/293d227464e3907982e0c82187915ee1b16386a4111e83ebd8db065ade64a48b-34623601367697.png)
2. Marca los campos que deseas incluir en el reporte, o desmarca los campos que deseas excluir del reporte.
3. Haz clic en **Aplicar** para guardar tu configuración.

**Copiar selección de campo de otro reporte**

Puedes copiar la selección de campo de otro reporte como punto de partida y luego continuar seleccionando o deseleccionando campos para afinar el reporte.

1. En la pestaña **Campos**, deselecciona cualquier campo aleatorio.
2. Haz clic en **Extraer esquema del reporte**.
3. Selecciona el reporte del que deseas copiar la selección de campo.
4. Continúa seleccionando o deseleccionando campos.
5. Para restaurar la selección de campo original del reporte, haz clic en <Image alt="Untitled 4.png" src="https://files.readme.io/dda26e3d18c52049cf92d7862a87ce7a46e6a00c349afd70dfe6d1809e00b89e-34623601369361.png" width="15px" /> **Actualizar**.

</Accordion>

<div id="7-select-the-reportlevel-filters" />

<Accordion title="8. Selecciona los filtros a nivel de reporte">

Los filtros a nivel de reporte te permiten **filtrar un solo reporte por aplicaciones, fuentes de medios u otras dimensiones**. También puedes establecer filtros que se apliquen a todos los reportes en tu cuenta; consulta [seleccionar filtros a nivel global](#select-global-level-filters). Por defecto, los filtros a nivel de reporte están configurados a la configuración de filtros a nivel global, pero puedes actualizarlos a configuraciones personalizadas que se apliquen solo al reporte seleccionado.

Para seleccionar los filtros que se aplicarán a un reporte específico:

1. Pasa el cursor sobre el reporte específico que deseas personalizar.
2. Haz clic en <Image alt="Untitled 2.png" src="https://files.readme.io/b3792460554dedede76f7d78346490280d3bfe00d38696a04c6d8f6f283e0f20-34623592674321.png" width="6px" /> para abrir el menú de acciones y selecciona <Image alt="Untitled 3.png" src="https://files.readme.io/c27f864253e6749f883047b4529ad292153500db5aebd452568a6aa04407472e-34623601366033.png" width="20px" /> **Editar reporte**.
3. Abre la pestaña **Filtros**. Los filtros están configurados en la configuración de filtro a nivel global.
4. Haz clic en el filtro y selecciona los elementos para incluir en el reporte. Por ejemplo, haz clic en <Image alt="Untitled.png" src="https://files.readme.io/817568835d9f564c139dca673bf30f570f3f4984deb466b91509404b10634ef4-34623601353745.png" width="53px" /> el filtro **Aplicaciones** y selecciona las aplicaciones a incluir en los reportes.
5. Haga clic en el botón Enter (⏎). Tu selección anula la configuración a nivel global.
6. (Opcional) Para el reporte **Inapps**, puedes establecer el filtro **Evento in-app**. Introduce sus nombres con precisión para seleccionarlos.
7. Haz clic en **Aplicar** para guardar tu configuración.

</Accordion>

<div id="8-remove-legacy-fields" />

<Accordion title="9. Eliminar campos antiguos">

Los campos heredados son aquellos que se incluyeron anteriormente en el esquema del reporte pero que ahora están excluidos. Recomendamos eliminar estos campos para asegurarte de que tu reporte contenga solo información relevante. Antes de realizar cualquier cambio, asegúrate de que tus flujos de trabajo e integraciones no dependan de ellos.

**Para eliminar campos heredados específicos**

1. Abra la pestaña **Campos antiguos**.
2. Activar: **Incluir campos antiguos en el reporte**.
3. Deselecciona los campos que deseas excluir.
4. Haz clic en **Aplicar**.
5. Guarda la configuración de conexión.

**Para eliminar todos los campos antiguos:**

1. Abre la pestaña de campos heredados.
2. Desactivar: **Incluir campos antiguos en el reporte**.

<div id="note-3" />

> 📘 **Nota**
>
> Si deseas incluir campos antiguos en el reporte pero no puedes porque la lista de campos antiguos está atenuada y bloqueada, contacta a tu Customer Success Manager.

<div id="non-empty-legacy-fields" />

#### Campos antiguos no vacíos

La mayoría de los campos antiguos están vacíos o `null`. Sin embargo, algunos de ellos contienen valores pero aún se consideran antiguos porque:

* Aparecen en el informe bajo un nombre diferente (renombrados).
* Fueron excluidos del esquema del reporte (obsoleto).

[Descargar la lista de campos antiguos no vacíos (CSV).](https://docs.google.com/spreadsheets/d/e/2PACX-1vRzJr2IgKTHKq_6IFX-PFFv6_89ixtlbGZ9RNH134TniGlWa_M-85D1L2E7LhzQrDjictnSnNNnN2mm/pub?output=csv)

</Accordion>

<div id="9-save-the-connection" />

<Accordion title="10. Guarda la conexión">

Haz clic en **Guardar,** y la primera descarga de datos se escribirá en tu servicio en la nube en un plazo de 3 horas. Los calendarios de actualización de datos posteriores son específicos para cada reporte.

<div id="important" />

> 🚧 **¡Importante!**
>
> Todos los cambios en la configuración de Data Locker tardan hasta 3 horas en surtir efecto.

</Accordion>

<div id="set-user-permissions" />

## Permisos de usuario

Tanto los administradores como los miembros del equipo, con los permisos correctos, pueden acceder a Data Locker.

* Los administradores pueden acceder a la página del Data Locker, crear y gestionar todas las conexiones, añadir editores y asignar propietarios a las conexiones existentes.
* Los miembros del equipo pueden acceder a la página del Data Locker, editar las conexiones existentes que poseen o crear nuevas conexiones. No pueden gestionar la propiedad (establecer el propietario y editores), incluso si son los propietarios de la cuenta.

<div id="manage-data-locker-access-and-ownership-admins" />

### Administradores

<div id="give-data-locker-access" />

#### ¡**Importante**! Si no tienes una suscripción a Data Locker y accedes al análisis de cohortes o a los datos de SKAN, debes completar igualmente un procedimiento de servicio de almacenamiento en la nube propio del marketer.

* Para proporcionar a un miembro del equipo permiso para acceder a Data Locker, asígnale un <Anchor target="_blank" href="/marketers/es/docs/user-management#gestionar-roles">rol</Anchor> con **Data Locker** configurado en '**Administrar**'.

<div id="manage-ownership-and-editors" />

#### Gestionar la propiedad y los editores

Para transferir la propiedad o añadir a un miembro del equipo como editor en una conexión existente:

1. Para transferir la propiedad o añadir a un miembro del equipo como editor en una conexión existente, haz clic en el menú de opciones <Image alt="3 dots icon.png" src="https://files.readme.io/a43c9bec16ef919203a2535aee8aa1f284fb3db7851d5e61245163fe2d8b08cb-22469580700177.png" width="1.18%" /> dentro de la conexión existente, y luego en **Gestionar propiedad** para cambiar el propietario de la conexión o añadir editores.
2. **Nota**:
3. Cambia el propietario de la conexión o añade un editor.

<div id="review-filters-after-changing-ownership" />

#### Revisar los filtros después de cambiar la propiedad

Si cambias el propietario de una conexión de Data Locker a un usuario con restricciones de acceso a los datos (por ejemplo, limitadas por aplicación, fuente de medios, agencia o país), los filtros existentes de [nivel global](#select-global-level-filters) o de [nivel de reporte](#7-select-the-reportlevel-filters) pueden restablecerse para ajustarse a los permisos del nuevo propietario.

Después de transferir la propiedad, revisa los filtros y confirma que la conexión refleje el alcance de datos previsto.

<Anchor target="_blank" href="/marketers/es/docs/data-locker-cloud-service-setup#aws-storage">AWS</Anchor>: Configurado por ti Debe tener el prefijo af-.

<div id="note-4" />

> 📘 **Nota**
>
> En las conexiones de AF AWS, no hay opción de **Gestionar propiedad** incluso para Administradores, ya que solo los Administradores pueden editar, eliminar o crear nuevas conexiones de AF AWS. Esta precaución se toma para evitar la exposición de las credenciales del bucket.

<div id="data-storage-architecture" />

## Arquitectura de almacenamiento de datos

<div id="zd-overview" />

<div id="overview" />

<Accordion title="Descripción general">

La estructura de tus datos en el almacenamiento depende de si los datos se envían al almacenamiento en la nube o a un almacén de datos. La estructura de carpetas descrita aquí se aplica al almacenamiento (buckets). En el caso del almacenamiento en almacén de datos, ten en cuenta que la referencia a las carpetas se aplica a las vistas.

Los datos se escriben en la opción de almacenamiento seleccionada. En el caso del almacenamiento en la nube, el almacenamiento es propiedad de AppsFlyer en AWS o de tu propiedad en AWS, GCS o Yandex. Puedes cambiar de opción de almacenamiento en cualquier momento o enviar algunos o todos tus datos a varias opciones de almacenamiento.

Los datos del almacenamiento en el bucket en la nube están organizados en una estructura jerárquica de carpetas, según el tipo de reporte, la fecha y la hora. La siguiente figura contiene un ejemplo de esta estructura:

![DLFolderOVerview.png](https://files.readme.io/78f360ec1df72253e5b2cd725f3eecf4e17548a7f06b544a94a75a2c319d77a0-18107910420369.png)

Los datos de un reporte determinado están incluidos en las carpetas de horas (h) asociadas con ese reporte:

* La cantidad de carpetas de horas depende de la actualización de los datos del reporte (por hora, por día o versionado).
* Los datos se proporcionan en archivos comprimidos Snappy o GZIP, o en archivos sin comprimir, que tienen formato Parquet o CSV.
* Los archivos de datos constan de columnas (fields).
* La estructura del esquema (field) de los <Anchor target="_blank" href="/marketers/es/docs/data-locker-advertiser-reports#user-journey">reportes de la trayectoria del usuario</Anchor> es idéntica y depende de los campos seleccionados por ti. Otros reportes tienen cada uno sus propios campos explícitos, también conocidos como reportes sin esquema. Consulta <Anchor target="_blank" href="/marketers/es/docs/data-locker-advertiser-reports#user-journey">Reportes para marketers de Data Locker</Anchor> para ver los reportes disponibles y los enlaces a las especificaciones del reporte.

</Accordion>

<div id="folder-structure" />

<Accordion title="Estructura de carpetas">

| Carpeta | Descripción |
| --- | --- |
| ID de suscripción | <Image alt="DataLockerFolders.png" src="https://files.readme.io/0cda5728e48dab772878cad13ed3b81168f152e1bf01604ac45b700af804dd16-32966264039185.png" width="439px" /><ul><li>La carpeta de nivel superior del bucket depende del propietario y proveedor del almacenamiento. En general, la carpeta de nivel superior es tu ID de suscripción, pero en algunos casos, por ejemplo, si utilizas Cyberduck, el ID se establece en el marcador y no se muestra en la estructura de carpetas.</li><li>La carpeta *data-locker-hourly* contiene los temas de los reportes. Las carpetas por encima de este nivel dependen de la propiedad del bucket y del proveedor de servicios en la nube.</li></ul>**Ejemplos de estructura de carpetas en función del propietario del bucket y el proveedor de la nube**<ul><li>**Bucket de AppsFlyer**: &lt;af-ext-reports>/&lt;unique\_identifier>/&lt;data-locker-hourly></li><li>**Tu bucket de AWS**: *&lt;af-datalocker-your bucket prefix>/&lt;generated-home-folder>&lt;subscription-id>*</li><li>**Tu bucket de GCS:** &lt;your bucket name>/&lt;generated-home-folder>/&lt;subscription-id></li></ul> |
| Tema (t) | El tipo de reporte se relaciona con el asunto del reporte. |
| Fecha (dt) | Esta es la fecha de los datos. En el caso de raw data, significa la fecha en que ocurrió el evento. En el caso de los datos agregados, la fecha del reporte en sí. |
| Hora (h o version) | Las carpetas de fecha se dividen en carpetas **por hora (h)** o **por versión** según el tipo de reporte.<br /><br />**<span id="hourly-folders"></span>Carpetas por hora**<br /><br />Las carpetas h se relacionan con la hora en que AppsFlyer recibió los datos. Por ejemplo, los eventos de instalación recibidos entre las 14:00 y 15:00 UTC se escriben en el archivo h=14. ¡Atención! ¡Nota! Hay una demora, de aproximadamente 1 a 3 horas, entre el momento en que los datos llegan a AppsFlyer hasta que la carpeta h se escribe en Data Locker. Por ejemplo, la carpeta h=14 se escribe 1 hora después a las 15:00 UTC.<br /><br />**Características de las carpetas por hora**:<ul><li>Hay carpetas de 24 h numeradas del 0 al 23. Por ejemplo, h=0, h=1, etc.</li><li>La carpeta late (h=late) contiene eventos del día anterior que llegaron después de la medianoche. Es decir que llegan entre las 00:00–02:00 UTC del día siguiente. Por ejemplo, si un usuario instala una aplicación el lunes a las 08:00 UTC y el evento llega el martes a la 01:00 UTC, se registra en la carpeta late del lunes.</li><li>Los datos que llegan después de las 02:00 UTC se escriben en la carpeta de la fecha y hora de llegada reales.</li><li>Asegúrate de procesar los datos de la carpeta h=late. Estos datos no se encuentran en ninguna otra carpeta.</li><li>\_temporary folder: En algunos casos, generamos una carpeta temporal dentro de una carpeta h. Desestimar carpetas y subcarpetas temporales. Ejemplo: /t=impressions/dt=2021-04-11/h=18/**\_temporary**.</li></ul>**Reportes diarios**<ul><li>Los reportes de raw data que tienen una actualización diaria de los datos se almacenan en la carpeta h=23. El reporte de desinstalación suele estar en la carpeta h=2, pero puede estar en cualquier carpeta.</li><li>Los reportes de cohorte e incrementalidad se almacenan directamente en la carpeta dt.</li><li>Los reportes versionados se adhieren a una convención diferente descrita en esta sección.</li></ul>**Consideraciones de los reportes por hora para aplicaciones que no usan la hora UTC.**<br /><br />Para asegurarte de obtener todos los datos para un día determinado del calendario, debes procesar las carpetas de acuerdo con el día definido por la zona horaria de la aplicación como se detalla:<ul><li>**Zona horaria del hemisferio oriental**: Para obtener todos los datos de una fecha dada, debes consumir carpetas de acuerdo con la hora y la fecha UTC. Ejemplo: La zona horaria de tu aplicación es UTC+10 (Sídney, Australia). Para obtener todos los datos horarios relacionados con el martes (Sídney), debes consumir las siguientes carpetas: Lunes h=14–23 y late, Martes h=0–13 y 14-15 ¿Por qué debes usar Martes h=14-15? Algunos datos pueden llegar tarde. Algunos datos pueden llegar tarde. Por lo tanto, las carpetas h=14–15 pueden contener eventos retrasados. Debes filtrar event\_time para alinearlo con el día del calendario de la aplicación en relación con UTC.</li><li>**Zona horaria del hemisferio occidental:** Para obtener todos los datos de una fecha del calendario determinada, debes consumir las carpetas según la hora y la fecha en UTC. Ejemplo: La zona horaria de tu aplicación es UTC-7 (Los Ángeles). Para obtener todos los datos horarios relacionados con el martes (Los Ángeles), debes utilizar las siguientes carpetas: Martes h=7–23 y late, Miércoles h=0–6 y 7-8. ¿Por qué debes utilizar miércoles h=7-8? Algunos datos pueden llegar tarde. Algunos datos pueden llegar tarde. Por lo tanto, las carpetas h=7–8 pueden contener eventos retrasados. Debes filtrar event\_time para alinearlo con el día del calendario de la aplicación en relación con UTC.</li></ul>**<span id="version-folders"></span>Carpetas de versión**<br /><br />Algunos reportes tienen una opción versionada. Esto significa que los datos más actualizados para un día determinado se proporcionan varias veces. Dado que los datos pueden seguir actualizándose debido a datos retrasados o a datos más precisos, el mismo reporte tiene varias versiones en las que la versión más reciente es la más precisa.<br /><br />Los reportes de un día determinado se encuentran en la carpeta de versiones de ese día. Cada versión está contenida en una carpeta separada cuyo nombre se establece mediante una marca de tiempo Epoch que identifica el reporte de forma exclusiva.<br /><br />Tus procesos de importación de datos deben considerar que los datos pueden ser escritos retroactivamente. Por ejemplo, el 14 de enero, los datos se pueden escribir en la carpeta 1 de enero. Si el bucket es de tu propiedad, considera utilizar la notificación de servicio en la nube para activar tu proceso de importación (<Anchor target="_blank" href="https://docs.aws.amazon.com/AmazonS3/latest/userguide/NotificationHowTo.html">AWS</Anchor> \| <Anchor target="_blank" href="https://cloud.google.com/storage/docs/pubsub-notifications">GCS</Anchor>) |

</Accordion>

<div id="app-segregation" />

<Accordion title="Segregación de apps">

Para el almacenamiento en un bucket en la nube, los datos se proporcionan en archivos de datos unificados que contienen los datos de todas las aplicaciones seleccionadas o segregadas en carpetas por aplicación. La segregación está dentro de la carpeta h como se describe en la siguiente tabla.

| Tipo de segregación | Descripción |
| --- | --- |
| [Predeterminada] Unificada | Los datos de todas las aplicaciones se proporcionan en archivos de datos unificados. Al procesar los datos, utiliza el campo app\_id a nivel de fila para distinguir entre aplicaciones.<br /><br />**Ejemplos de archivos de datos que están en la carpeta h=2**<br /><br />![UnifiedByApp.png](https://files.readme.io/dbc39c2ce99c1ff607fd553b9c9034e55728c102f31fd18a501cc00910267b28-18107874522513.png)<br /><br />La convención de nomenclatura de archivos de datos es unique\_id.gz.<ul><li>El proceso de carga de datos debe:<ul><li>Cargar datos después de que se establezca el indicador \_SUCCESS.</li><li>Carga todos los archivos de la carpeta con una extensión *.gz.* No crees tu proceso de importación utilizando la lógica de numeración de piezas.</li></ul></li></ul> |
| Segregado por aplicación | La carpeta contiene subcarpetas por aplicación. Los archivos de datos de una aplicación determinada se encuentran dentro de la carpeta de la aplicación. En la siguiente figura, la carpeta h=19 contiene carpetas de aplicaciones. Cada carpeta de aplicación contiene los archivos de datos asociados. ¡Atención! ¡Nota! Los archivos de datos no contienen el app\_id, debes determinar el app\_id mediante la carpeta.<br /><br />![DLSegregateByApp.png](https://files.readme.io/90639507da82f7dafacfa5bfb67fa96a8277747cd0eee226d74498bf5ff16869-32966264040977.png)<br /><br />En cada carpeta de la aplicación, la convención de nomenclatura es: unique\_id.gz:<ul><li>El proceso de carga de datos debe:<ul><li>Cargar datos después de que se establezca el indicador \_SUCCESS.</li><li>Carga todos los archivos de la carpeta con una extensión *.gz.* No crees tu proceso de importación utilizando la lógica de numeración de piezas.</li></ul></li></ul>Limitación: Esta opción no está disponible para los reportes de la atribución peopled-based. |

</Accordion>

<div id="data-files" />

<Accordion title="Archivos de datos">

Los archivos de datos dependen del tipo de segregación.

<table><thead><tr><th>Contenido</th><th colspan="2">Detalles</th></tr></thead><tbody><tr><td>Indicador de finalización</td><td colspan="2"><p>El indicador de último archivo (finalización) se establece cuando se han escrito todos los datos de una carpeta h determinada. </p><ul><li>No leas datos en una carpeta antes de verificar que tiene el indicador _SUCCESS.</li><li>El indicador _SUCCESS se configura incluso en los casos en que no hay datos para escribir en una carpeta determinada y la carpeta está vacía.</li><li>¡Atención! ¡Nota! En la opción de segregación por aplicación, el indicador se configura en la carpeta h y no en las carpetas individuales de las aplicaciones. Consulta las figuras de la sección anterior. </li></ul></td></tr><tr><td>Tipos de archivo</td><td colspan="2"><ul><li>Los datos se proporcionan en archivos comprimidos Snappy o GZIP, o en archivos sin comprimir, que tienen formato Parquet o CSV.</li><li>Después de descomprimir, los archivos de datos están en formato Parquet o CSV de acuerdo con tu configuración.</li></ul></td></tr><tr><td>Secuencia de columnas (archivos CSV) </td><td colspan="2"><p>En el caso de los archivos CSV, la secuencia de campos en los reportes es siempre la misma. Cuando agregamos campos nuevos, estos se agregan a la derecha de los campos existentes. </p><p>En este sentido: </p><ul><li>La estructura de columnas de los reportes del viaje del usuario es idéntica. Esto significa que puedes tener procedimientos de carga de datos similares para diferentes tipos de reportes. Selecciona los campos contenidos en los reportes. El significado del campo se detalla en el <a href="./raw-data-field-dictionary" target="_blank">diccionario de raw data</a>.</li><li>Los reportes que tienen una notación FF en la sección de disponibilidad del reporte no se adhieren a la estructura de columnas común. </li></ul></td></tr><tr><td>Consideraciones del relleno de campos</td><td colspan="2"><p><strong>Campos en blanco o vacíos:</strong> Algunos campos se completan con <em>null</em> o están vacíos. Esto significa que en el contexto de un reporte determinado no hay datos para reportar. Normalmente, <em>null</em> (nulo) significa que este campo no se completa en el contexto de un reporte y tipo de aplicación determinados. Blank "" (en blanco) significa que el campo es relevante en su contexto, pero no se encontraron datos para completarlo. </p><p>Si la fuente de medios está restringida, el contenido de los campos restringidos se establece en null. </p><p>En general, se considera null y blank como un único producto; no hay datos disponibles. </p><p><strong>Zona horaria y moneda</strong></p><p>La configuración de la zona horaria y divisa específicas de la aplicación no afecta los datos en Data Locker. Aplican las siguientes condiciones: </p><ul><li> <strong>Zona horaria</strong>: La fecha y la hora están en UTC.</li><li> <strong>Moneda</strong>: El campo event_revenue_usd está en USD.</li></ul><p><strong>Valores con comas</strong>: Estas comas están contenidas entre comillas dobles "", por ejemplo, <code>`"iPhone6,1"`</code>.</p></td></tr></tbody></table>

</Accordion>

<div id="storage-options" />

<Accordion title="Opciones de almacenamiento">

<div id="caution" />

> ❗️ **¡Importante!**
>
> Si utilizas la opción de almacenamiento propia del marketer:
>
> * Asegúrate de cumplir con las regulaciones de privacidad de datos como el GDPR y las políticas de retención de datos de ad network/SRN.
> * No utilices la solución de almacenamiento propia del marketer para enviar datos a terceros.

* Los datos se escriben en un propietario de almacenamiento de tu elección de la siguiente manera:
  * Almacenamiento de AppsFlyer
  * Almacenamiento de clientes: AWS, GCS, Azure, Yandex, BigQuery y Snowflake
* Puedes cambiar la selección del almacenamiento en cualquier momento.
* Si cambias el almacenamiento, ocurre lo siguiente:
  * Comenzamos a escribir en el almacenamiento recién seleccionado en una hora.
  * Seguimos escribiendo en el almacenamiento existente durante un período de transición de 7 días. El tiempo de vencimiento del período de transición se muestra en la interfaz de usuario. Usa el período de transición para actualizar tus procesos de carga de datos. Puedes reiniciar el período de transición o volver al bucket de AppsFlyer si es necesario.
  * **Cambio de almacenamiento**: Puedes migrar de una opción de almacenamiento a otra utilizando la opción de almacenamiento múltiple y enviando datos a varios destinos simultáneamente. Una vez que hayas completado la migración y las pruebas, elimina la opción de almacenamiento que ya no necesitas.

|  | Almacenamiento propio de AppsFlyer (AWS) | Almacenamiento propio del marketer (GCS, AWS, Azure, Yandex, BigQuery, Snowflake) |
| --- | --- | --- |
| Nombre del bucket | Configurado por AppsFlyer | <ul><li><Anchor target="_blank" href="/marketers/es/docs/data-locker-cloud-service-setup#gcs-storage">GCS</Anchor>: Sin restricción</li><li><Anchor target="_blank" href="/marketers/es/docs/data-locker-cloud-service-setup#aws-storage">AWS</Anchor>: configurado por ti. Debe tener el prefijo af-.</li></ul>Ejemplo: `af-datalocker-your-bucket-name` |
| Almacenamiento propio | AppsFlyer | Comercializador |
| Plataforma del almacenamiento | AWS | AWS, GCS, Azure, Yandex, BigQuery, Snowflake |
| Credenciales para que accedas a los datos | Disponible en la interfaz de usuario de Data Locker para los administradores de tu cuenta de AppsFlyer | AppsFlyer no las conoce. Usa las credenciales proporcionadas por el proveedor de la nube. |
| Retención de datos | Los datos se eliminan después de 14 días | Responsabilidad del marketer |
| Solicitudes de eliminación de datos | Responsabilidad de AppsFlyer | Responsabilidad del marketer |
| Seguridad | AppsFlyer controla el almacenamiento. El cliente tiene acceso de lectura. | El marketer controla el almacenamiento.<ul><li>**AWS**: AppsFlyer requiere permiso de GetObject, ListBucket, DeleteObject, PutObject para el bucket. El uso del bucket debe ser exclusivo de AppsFlyer. No lo uses para otros fines.</li><li>**GCS**: Consulta el <Anchor target="_blank" href="/marketers/es/docs/data-locker-cloud-service-setup">artículo de configuración de GCS</Anchor>.</li></ul> |
| Capacidad de almacenamiento | Gestionado por AppsFlyer | Gestionado por el marketer |
| Control de acceso mediante puntos de conexión de VPC con políticas de bucket | No aplicable | [Opcional] En AWS, si implementas la seguridad de punto de conexión de VPC a nivel bucket, debes agregar a la lista los servidores de AppsFlyer. |

<div id="notice-to-security-officers-in-the-case-of-customer-controlled-storage" />

#### **Aviso a los agentes de seguridad en el caso de almacenamiento controlado por el cliente**

Ten en cuenta lo siguiente:

* El bucket o destino es para uso exclusivo de AppsFlyer. No debe haber ninguna otra entidad que escriba a un destino determinado.
* Puedes eliminar datos en el destino 25 horas después de que escribamos los datos.
* Los datos escritos en el destino son una copia de los datos que ya están en nuestros servidores. Los datos continúan estando en nuestros servidores de acuerdo con nuestra política de retención.
* Por razones técnicas, a veces eliminamos y reescribimos los datos. Por esta razón, necesitamos permisos de eliminación y listado. Ningún permiso es un riesgo de seguridad para ti. En el caso de la lista, somos la única entidad que escribe en el bucket. En el caso de eliminar, podemos regenerar los datos.
* Para más información, puedes contactar con nuestro equipo de seguridad a través de [hello@appsflyer.com](mailto:hello@appsflyer.com) o a tu CSM.

</Accordion>

<div id="multipleconnections-principles-more-than-one-destination" />

<Accordion title="Principios de las conexiones múltiples (más de un destino)">

En Data Locker, puedes enviar algunos o todos tus datos a 2 destinos (definidos en la configuración de la conexión). Por ejemplo, puedes enviar los datos de la aplicación A a AWS y los de la aplicación B a GCS.

Cada conexión consiste en un conjunto completo de configuraciones de Data Locker, incluido un destino. Las configuraciones de las conexiones son independientes entre sí.

Al administrar tus conexiones, ten en cuenta lo siguiente:

* En la configuración de Data Locker, las conexiones se muestran en pestañas. Cada conexión tiene su propia pestaña de configuración desde la que puedes administrar la conexión. El icono de cada pestaña representa el tipo de almacenamiento.
* Para ver los detalles de la conexión, duplicar una conexión o eliminar una conexión, haz clic en ⋮ (opciones).

</Accordion>

<div id="additional-information" />

## Información adicional

<div id="track-connection-changes-in-the-audit-log" />

<Accordion title="Realiza un seguimiento de los cambios de conexión en el registro de auditoría">

Puedes ver los cambios de conexión del Data Locker en el registro de auditoría, disponible desde el centro de seguridad en el dashboard de AppsFlyer. Utiliza el registro de auditoría para confirmar si se realizó un cambio, cuándo ocurrió y quién lo hizo. Esto puede ayudar a resolver problemas como datos faltantes o cambios de conexión inesperados sin necesidad de contactar al soporte.

Se rastrean los siguientes eventos del ciclo de vida de la conexión:

* Nueva conexión creada
* Conexión actualizada
* Conexión deshabilitada
* Conexión eliminada

**Para acceder a Audit log:**

1. En la barra de navegación superior, abre el menú de cuenta <Image alt="HQ1 2025-05-05 10.48.04.png" src="https://files.readme.io/b7020f3b633fb66e0e2d4988c7903426509b1fa871693cee602a39b8eb9d69d1-34955489919889.png" width="4.24%" />.
2. Selecciona **Centro de seguridad**.
3. En la sección **Audit log**, haz clic en **Ver audit log.**
4. Filtrar por servicio: **Datalocker** para ver entradas relacionadas.

Para más información, consulta: <Anchor target="_blank" href="/marketers/es/docs/audit-log">Audit log.</Anchor>

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Características y limitaciones">

| **Caducado** | Observaciones |
| --- | --- |
| Redes publicitarias | No apto para el uso por parte de ad networks |
| Agencias | No apto para el uso por parte de agencias. |
| Zona horaria específica de la aplicación | No corresponde. Las carpetas de Data Locker se dividen en horas usando UTC. Los eventos reales contienen horarios en UTC. Convierte los horarios a cualquier otra zona horaria según sea necesario. Independientemente de la zona horaria de tu aplicación, el lapso desde que ocurre el evento hasta que se registra en Data Locker sigue siendo el mismo. |
| Moneda específica de la aplicación | No compatible |
| Limitaciones de tamaño | No corresponde |
| Actualización de los datos | Los datos se actualizan de acuerdo con la actualización específica de los datos del reporte que se detalla en <Anchor target="_blank" href="/marketers/es/docs/data-locker-advertiser-reports#reportes-de-raw-data">este artículo</Anchor>. |
| Datos históricos | No se admiten. Si necesitas datos históricos, algunos reportes, pero no todos, están disponibles a través de Pull API. |
| Datos restringidos | Los campos en algunos reportes están restringidos debido a limitaciones de privacidad. <Anchor target="_blank" href="/marketers/es/docs/about-raw-data-identifier-restrictions">Saber más</Anchor> |
| Acceso de usuario | Solo los <Anchor target="_blank" href="/marketers/es/docs/user-management">usuarios de la cuenta con los permisos necesarios</Anchor> pueden configurar Data Locker. |
| Aplicación única/múltiples aplicaciones | Admite múltiples aplicaciones. Data Locker está a nivel de cuenta |
| Conexiones máximas | Por defecto, cada cuenta puede abrir hasta **2 conexiones de Data Locker**. Para solicitar conexiones adicionales, **contacta con tu CSM**. |

</Accordion>

<div id="troubleshooting" />

<Accordion title="Resolución de problemas">

* **Síntoma**: No se pueden recuperar datos con AWS CLI
* **Mensaje de error**: Ocurrió un error (AccessDenied) al llamar a la operación ListObjectsV2: Acceso denegado
* **Causa**: Las credenciales de AWS que se utilizan no son las credenciales correctas para el bucket de AppsFlyer. Esto puede ser causado por tener credenciales múltiples o inválidas en tu máquina.
* **Solución**:
  1. Utiliza un método diferente, como [Cyberduck](/docs/data-locker-for-marketers#cyberduck), para acceder al bucket, es decir, que no sea CLI. Haz esto para verificar que las credenciales que estás utilizando funcionen. Si puedes conectarte con Cyberduck, esto indica un problema con el caché de credenciales.
  2. <Anchor target="_blank" href="https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-role.html">Actualiza el caché de credenciales de AWS</Anchor>.  
     **Captura de pantalla de AWS** ![mceclip0.png](https://files.readme.io/e6608b196c39cb71e0a02e0eabe95378f24659a1578a16fd381bfd0053ca309e-32966264043537.png)

</Accordion>

<div id="aws-data-retrieval" />

## Recuperación de datos de AWS

Utiliza tu herramienta de recuperación de datos de AWS preferida, AWS CLI, o una de las herramientas descritas en las secciones a continuación. ¡Atención! ¡Nota! Las instrucciones exactas son adecuadas para los buckets de propiedad de AppsFlyer. Adapta las instrucciones según sea necesario si la conexión es a tu bucket.

<div id="aws-cli" />

<Accordion title="AWS CLI">

Antes de comenzar:

* Instala AWS CLI en tu computadora.
* En AppsFlyer, accede a Data Locker y recupera la información incluida en el panel de credenciales.

**Para usar AWS CLI**:

1. Abre la terminal. Para hacerlo en Windows, &lt;Windows>+&lt;R>, haz clic en **Aceptar**.  
   Se abre la ventana de línea de comando.
2. Ingresa **aws configure.**
3. Ingresa la clave de acceso de AWS tal como aparece en el panel de credenciales.
4. Ingresa tu clave secreta de AWS tal como aparece en el panel de credenciales.
5. Ingresa **eu-west-1.**
6. Presiona Enter.

Usa los comandos de CLI que siguen según sea necesario.

En los siguientes comandos, el valor de `{home-folder}` se puede encontrar

**Para enumerar carpetas en tu bucket:**

```bash
aws s3 ls s3://af-ext-reports/{home-folder}/data-locker-hourly/
```

<div id="listing-files-and-folders" />

### Enumeración de archivos y carpetas

Hay tres tipos de carpetas en tu bucket de Data Locker:

* Tipo de reporte `t=`
* Fecha `dt=`
* Hora `h=`

Para enumerar todos los reportes de un tipo de reporte específico:

```bash
aws s3 ls s3://af-ext-reports/{home-folder}/data-locker-hourly/t=installs/
```

Para enumerar todos los reportes de un tipo de reporte específico para un día específico:

```bash
aws s3 ls s3://af-ext-reports/{home-folder}/data-locker-hourly/t=installs/dt=2019-01-17
```

Para enumerar todos los reportes de un tipo de reporte específico en un hora específica para un día específico:

```bash
aws s3 ls s3://af-ext-reports/{home-folder}/data-locker-hourly/t=installs/dt=2019-01-17/h=23
```

Para descargar archivos para una fecha específica:

```bash
aws s3 cp s3://af-ext-reports/<home-folder>/data-locker-hourly/t=installs/dt=2020-08-01/h=9/part-00000.gz ~/Downloads/
```

</Accordion>

<div id="cyberduck" />

<Accordion title="Cyberduck">

Antes de comenzar:

* Instala el cliente Cyberduck.
* En AppsFlyer, accede a Data Locker y recupera la información incluida en el panel de credenciales.

**Para configurar Cyberduck**:

1. En Cyberduck, haz clic en Acción.
2. Selecciona **Nuevo marcador**. Se abre la ventana.
3. En el primer campo (marcado [1] en la captura de pantalla a continuación) selecciona **Amazon S3.** [![DataDuckSmall2.png](https://files.readme.io/a2aba523ca9489315260f34c6c42571f67d37f7985d0f18b1eb0ed2a95b4b4ad-32966274482705.png)](https://files.readme.io/a2aba523ca9489315260f34c6c42571f67d37f7985d0f18b1eb0ed2a95b4b4ad-32966274482705.png)
4. Completa los campos de la siguiente manera:
   * **Apodo:** Texto libre
   * **Servidor:** s3.amazonaws.com
   * **ID de clave de acceso:** Copia la clave de acceso de AWS tal como aparece en el panel de credenciales en AppsFlyer.
   * Clave de acceso secreta Copia la clave de acceso de AWS tal como aparece en el panel de credenciales en AppsFlyer.
   * **Ruta**: `{Nombre del Bucket}/{Carpeta de Inicio}` Por ejemplo: **af-ext-reports/1234-abc-ffffffff**
5. Cierra la ventana. Para ello, haz clic en la X de la esquina superior derecha de la ventana.
6. Selecciona la conexión.  
   Se muestran los directorios de datos.

</Accordion>

<div id="amazon-s3-browser" />

<Accordion title="Navegador Amazon S3">

Antes de comenzar:

* Instala el navegador Amazon S3.
* En AppsFlyer, accede a Data Locker y recupera la información incluida en el panel de credenciales.

**Para configurar el navegador Amazon S3**:

1. En el navegador S3, haz clic en **Cuentas** > **Agregar** **Nueva cuenta**.  
   Se abre la ventana Agregar nueva cuenta. [![mceclip0.png](https://files.readme.io/f7ea8b02f27a5e7eaf89b578b177a9e1a9f34273eaa41d41652156a6dbb23d5c-32966274485009.png)](https://files.readme.io/f7ea8b02f27a5e7eaf89b578b177a9e1a9f34273eaa41d41652156a6dbb23d5c-32966274485009.png)
2. Completa los campos de la siguiente manera:
   * **Nombre de la cuenta**: texto libre.
   * **ID de clave de acceso:** copia la clave de acceso de AWS tal como aparece en el panel de credenciales.
   * **Clave secreta de acceso**: copia la clave secreta del bucket tal como aparece en el panel de credenciales.
   * Selecciona **Cifrar claves de acceso** con una contraseña e ingresa una contraseña. Anota esta contraseña.
   * Selecciona **Usar transferencia segura.**
3. Haz clic en **Guardar cambios**.
4. Haz clic en **Buckets** > **Agregar bucket externo**.  
   Se abre la ventana Agregar bucket externo.  
   <Image alt="mceclip2.png" src="https://files.readme.io/88dd43f62dbd68d0295b52a7f7b9b09449bd915e6a6d52703c24a50583e05a6e-32966264054929.png" width="433px" />
5. Ingresa el **Nombre del bucket.** El nombre del bucket tiene el siguiente formato: `{Nombre del Bucket}/{Carpeta de Inicio}`. Los valores necesarios para el nombre del bucket y la carpeta de inicio aparecen en la ventana de credenciales.
6. Haz clic en **Añadir bucket externo.** El bucket se crea y se muestra en el panel izquierdo de la ventana.  
   Ahora puedes acceder a los archivos de Data Locker.

</Accordion>

<div id="see-also" />

> 📄 **Consulta también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/data-locker-advertiser-reports">Reportes disponibles en Data Locker</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">Cómo seleccionar la herramienta de entrega de raw data correcta</Anchor>

<div data-zendesk-anchors="data-locker=descripci%C3%B3n-general h_01HE2S6FANNTNB580CMHNX34YA=descripci%C3%B3n-general data-locker%E2%80%94features=data-locker-features h_01HE2S6FANQH2GZ11S8S87H0YH=data-locker-features h_01HE2S6FAN6BFPJSZJBEE9P5VK=reports-available-via-data-locker set-data-locker-report-settings=configurar-la-configuraci%C3%B3n-del-reporte-de-data-locker h_01JS45N2DNWZBHP5PH8ZG6FBTF=configurar-la-configuraci%C3%B3n-del-reporte-de-data-locker h_01JS45N2DNEZZJRF2RKG1RM9NK=1-set-up-your-cloud-service h_01JS45N2DNVA0SHBA49G42GNFE=2-add-a-connection-to-your-cloud-service h_01K22P5FWJ96CPFJPW0XDCHNNJ=nota h_01JS4ASE6J6X1DD33PEGQAPXPA=aws-cloud-bucket-connection h_01JS4ASE6J587JPHAMCSBA2Z92=gcs-cloud-bucket-connection h_01JS4ASE6J4NC7M0TRFDT7F2X7=azure-cloud-bucket-connection h_01JS4ASE6JKFTM3FYAEKFHRW2M=yandex-cloud-bucket-connection h_01JS4ASE6JKV8WJG68RMHKVCE5=bigquery-data-warehouse-connection h_01JS4ASE6JBNE5BK04QDRM7CW4=snowflake-data-warehouse-connection h_01JTFRHNRRJB76JBXXT1TBNRBY=nota-1 h_01JS45N2DN8JTMQCK76PDBBWA4=3-set-the-report-output-settings h_01JSBTCZ5569RCV6W6QWT400R7=nota-2 h_01JS45N2DNMQAGFVHDDD5JGF2M=select-global-level-filters h_01JS45N2DN388YVP29DDBBBFBP=5-select-the-report h_01JVPJ9CG45JREBKP3ZQXKZWRZ=customize-or-duplicate h_01JS45N2DP4FK9EZYNTY2GX2GK=6-select-the-report-fields h_01JS45N2DPN7B73X0TRC82JW87=7-select-the-reportlevel-filters h_01JS45N2DPYYABS9NXFXP23ARA=8-remove-legacy-fields h_01JS45N2DPYNBG9VPCZJ481DFE=nota-3 nonempty-legacy-fields=campos-antiguos-no-vac%C3%ADos h_01JSCC6KZNKJAVYSFCDDSE80YW=campos-antiguos-no-vac%C3%ADos h_01JS45N2DPH1QAREYGN5H20T8R=9-save-the-connection h_01JS45N2DPNPXAEZ74J0ETP7BS=importante set-user-permissions=permisos-de-usuario h_01KH8D60TDTNS4EWNXJ4JPGXZ2=permisos-de-usuario manage-data-locker-access-and-ownership-admins=administradores h_01KH8D60TEFX2MCW00JT94F9AQ=administradores give-data-locker-access=importante-si-no-tienes-una-suscripci%C3%B3n-a-data-locker-y-accedes-al-an%C3%A1lisis-de-cohortes-o-a-los-datos-de-skan-debes-completar-igualmente-un-procedimiento-de-servicio-de-almacenamiento-en-la-nube-propio-del-marketer h_01KH8D60TE541XMXWCVK0HZTJA=importante-si-no-tienes-una-suscripci%C3%B3n-a-data-locker-y-accedes-al-an%C3%A1lisis-de-cohortes-o-a-los-datos-de-skan-debes-completar-igualmente-un-procedimiento-de-servicio-de-almacenamiento-en-la-nube-propio-del-marketer manage-ownership-and-editors=gestionar-la-propiedad-y-los-editores h_01KH8D60TF69FN7KMBPMZHBW27=gestionar-la-propiedad-y-los-editores review-filters-after-changing-ownership=revisar-los-filtros-despu%C3%A9s-de-cambiar-la-propiedad h_01KH8D60TFYMEY8FEPR4YKJRYJ=revisar-los-filtros-despu%C3%A9s-de-cambiar-la-propiedad h_01KH8D60TGVN75TMS9QES0G6CQ=nota-4 architecture=arquitectura-de-almacenamiento-de-datos data-storage-architecture=arquitectura-de-almacenamiento-de-datos h_01HE2S6FAN4H9DQ5HBTKSNJ72B=arquitectura-de-almacenamiento-de-datos h_01HE2S6FANY1FWEY6Y34T85GHM=overview h_01HE2S6FANDJ65MZ2H2FBAZYJR=folder-structure h_01HE2S6FAN7PBZ8M86FQVSN5KQ=hourly-folders h_01HE2S6FAN366V8HNCY4PFNTFG=version-folders h_01HE2S6FANHFZMCY3WZBZB9QMP=app-segregation h_01HE2S6FANVDFH9S9JN8E9J7ES=data-files h_01HE2S6FAN8ZDF5N4ECKKN1D1H=storage-options h_01HE2S6FAN2HY7V3G9NS9XCVE1=importante-1 notice-to-security-officers-in-the-case-of-customercontrolled-storage=aviso-a-los-agentes-de-seguridad-en-el-caso-de-almacenamiento-controlado-por-el-cliente h_01HE2S6FANRVGYPRWWFA50JAQ4=aviso-a-los-agentes-de-seguridad-en-el-caso-de-almacenamiento-controlado-por-el-cliente h_01HE2S6FANBRXA0NS4E8SP3618=multipleconnections-principles-more-than-one-destination additional-information=informaci%C3%B3n-adicional h_01HE2S6FAP4SA77B0SX7R8JMTY=informaci%C3%B3n-adicional h_01JTFQMKN0046SNBB4YSRJMQG9=track-connection-changes-in-the-audit-log h_01HE2S6FAP6FKAJCW92JVWD828=traits-and-limitations h_01HE2S6FAPJC20G7YZSRWP5E34=troubleshooting aws-data-retrieval=recuperaci%C3%B3n-de-datos-de-aws h_01HE2S6FAPJMKX567HSAR16TCN=recuperaci%C3%B3n-de-datos-de-aws h_01HE2S6FAPB5MW09Y4HKFV3RM8=aws-cli listing-files-and-folders=enumeraci%C3%B3n-de-archivos-y-carpetas h_01HE2S6FAP31H9NK6V870FGXZF=enumeraci%C3%B3n-de-archivos-y-carpetas h_01HE2S6FAP2E2TW4F5PJ4226Q0=cyberduck h_01HE2S6FAP74NG5VNEWKWXXJX2=amazon-s3-browser h_01HE7RB5N99WJ3XP69Z69H81AD=consulta-tambi%C3%A9n" />
