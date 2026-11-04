---
title: Página de exportación de datos en bruto
metadata:
  keywords:
    - ad networks
    - Advertisers
    - Agencies
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Agencies
    - Raw Reports
    - Ad Networks
  created_at: '2020-05-11T22:25:33Z'
  edited_at: '2026-08-22T00:04:36Z'
  id: 360008613838
  locale: es
  section: Data delivery tools
  section_id: 6550995484561
  url: https://support.appsflyer.com/hc/es/articles/360008613838
---
> **De un vistazo:** Descarga informes de datos en bruto en archivos CSV. Hasta 1 millón de filas por cada descarga. Limita los informes a los datos que necesitas utilizando filtros.

La imagen siguiente se muestra la primera vez que accedes a la página **Exportación de datos en bruto**; la página **Mis informes** se muestra si tienes informes listos para descargar o duplicar.

[![RawDataSplash.png](https://files.readme.io/febb6a32a3a7b86c5b396cd77ff9e7968057f57ed20fd991d6dbb4899d5eaf07-41225791757969.png)](https://files.readme.io/febb6a32a3a7b86c5b396cd77ff9e7968057f57ed20fd991d6dbb4899d5eaf07-41225791757969.png)

**Mis informes**

La página **Mis informes** lista los informes generados previamente y listos para descargar, duplicar o ambas cosas. Los informes listados se generaron en los 90 días anteriores; tienen un período de descarga de 7 días. Después de 7 días, si todavía necesitas el informe, deberás generarlo de nuevo.

Para una descripción de los informes de datos crudos, consulte <Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-overview">Descripción general de la generación de informes de datos crudos</Anchor>

Para generar o descargar informes, consulta la sección de procedimientos de este artículo.

[![MisInformesExportaciónDatosEnBruto.png](https://files.readme.io/1f82e365a7e6cd802ee899666b800be357ea5e99aa6909e75b1fa39a2e4a164e-41225791760145.png)](https://files.readme.io/1f82e365a7e6cd802ee899666b800be357ea5e99aa6909e75b1fa39a2e4a164e-41225791760145.png)

<div id="raw-data-export-page-features-and-filter-options" />

<Accordion title="Características y opciones de filtro de la página de exportación de datos en bruto">

La página de exportación de datos en bruto proporciona informes con las características enumeradas en la siguiente tabla.

<Table>
  <thead>
    <tr>
      <th>
        Función
      </th>
      <th>
        Comentarios
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="report-categories"></span>
        Categorías de informes
      </td>
      <td>
        Difieren según tu plan de suscripción
      </td>
    </tr>
    <tr>
      <td><span id="date-range"></span>
        El rango de datos sEleccionado
      </td>
      <td>
        Los informes de datos en bruto se filtran por fechas de actividad (ocurrencia del evento). También puedes añadir un filtro para las fechas de instalación. Consulta la lista de opciones de filtro en la tabla a seguir.
      </td>
    </tr>
    <tr>
      <td><span id="maximum-number-of-rows"></span>
        Número máximo de filas
      </td>
      <td>
        1 millón de filas
      </td>
    </tr>
    <tr>
      <td><span id="rate-limitation"></span>
        Límite de velocidad
      </td>
      <td>
        Un <Anchor target="_blank" href="/marketers/es/docs/report-generation-quotas-rate-limitations">mecanismo de cuotas</Anchor> limita el número de reportes que se pueden generar al día.
      </td>
    </tr>
    <tr>
      <td><span id="retentionreport-window"></span>
        Ventana de retención/reporte
      </td>
      <td>
        Reportes relacionados con la instalación (instalaciones, postbacks de instalación) **60** de los 90 días anteriores en una sola descarga.

        Reportes relacionados con eventos in-app: 31 de los 90 días anteriores en una sola descarga.
      </td>
    </tr>
    <tr>
      <td><span id="filter-options"></span>
        Opciones de filtro
      </td>
      <td>
        Los filtros listados están disponibles para uso. En algunos casos, dependiendo del filtro, las opciones de filtro se completan automáticamente. Por ejemplo, al filtrar por geolocalización, se enumera la lista de países disponibles.
      </td>
    </tr>
    <tr>
      <td><span id="field-selection"></span>
        Selección de campos
      </td>
      <td>
        Los campos más relevantes están preseleccionados. Puedes añadir o quitar campos seleccionados en la pestaña **Campos del reporte**. Es posible que algunos campos no sean relevantes para un informe determinado. No obstante, puedes seleccionar el campo. Hacemos esto para que pueda disponer de formatos de informes coherentes (columnas).

        Por ejemplo, al seleccionar campos relacionados con fraude (Protect360) en el informe de eventos en la aplicación de adquisición de usuarios, aparecen columnas vacías. Estos campos se completan únicamente en el contexto específico de los informes de Protect360.
      </td>
    </tr>
    <tr>
      <td><span id="report-csv-field-order"></span>
        Orden de campos en el informe (CSV)
      </td>
      <td>
        Las columnas en los informes se ordenan conforme a la configuración del orden de los campos. La secuencia de columnas [que se muestra en una hoja de cálculo](https://docs.google.com/spreadsheets/d/e/2PACX-1vRGYcMOgC5yy_82yn3DWd3ucLE5KtuTA72eJfvu5KVB9fFH_mYwzM3KpR_inQOnat-KzgVjuuvXa6_g/pub?output=xlsx) contiene pestañas separadas para las opciones heredadas y predeterminadas.

        | Configuración | Selección de campos permitida | Comentarios |
        | --- | --- | --- |
        | <span id="default"></span>Por defecto | Sí | * Los campos seleccionados se ordenan según una plantilla de AppsFlyer.<br />* A partir de ahora, la secuencia se mantendrá. Los campos futuros se anexarán a la derecha de los campos existentes. |
        | <span id="alphabetical-az"></span>Alfabético (A-Z) | Sí | Los campos seleccionados se ordenan alfabéticamente (orden ascendente). |
        | <span id="alphabetical-za"></span>Alfabético (Z-A) | Sí | Los campos seleccionados se ordenan en orden inverso alfabéticamente (orden descendente). |
        | <span id="legacy"></span>Heredado | No | * Los campos se ordenan según la secuencia de las columnas en los reportes elaborados utilizando la versión anterior de la página de datos exportados.<br />* La selección de campos es fija y no se puede cambiar.<br />* La variación de los informes por campo depende del informe específico. |
      </td>
    </tr>
  </tbody>
</Table>

| Filtro | Anunciante | Red publicitaria (Ad network) | Agency |
| --- | --- | --- | --- |
| Fuente de medios | Sí | No | Sí |
| Intervalo de fechas de actividad | Sí | Sí | Sí |
| Rango de fechas de instalación | Sí | Sí | Sí |
| Agency | Sí | No | No |
| Geolocalización (territorio/país) | Sí | Sí | Sí |
| Eventos en la aplicación (disponibles en informes de eventos en la aplicación) | Sí | No | Sí |

</Accordion>

<div id="procedures" />

## Procedimientos

<div id="create-a-default-report" />

<Accordion title="Crear un informe por defecto">

Puede crear un informe con la configuración estándar sin personalizar sus campos o filtros.

**Para crear un informe por defecto:**

1. En AppsFlyer, desde el menú lateral, seleccione **Exportar** > **Exportación de datos sin procesar**.
2. Haga clic en + **Nuevo informe**.
3. Desplace el cursor sobre el tipo de informe que desea generar y haga clic en **Crear**.
4. Seleccione **Generar ahora** en el menú desplegable.
5. En la ventana emergente, haga clic en **Generar ahora.** La generación puede tardar hasta 10 minutos.
   * Durante la generación del informe, puede seguir trabajando, crear informes adicionales o navegar a otras páginas.

**Configuración predeterminada del filtro del informe:**

| Filtro | Configuración por defecto |
| --- | --- |
| Fechas de actividad | Los últimos 7 días |
| Máximo de filas por archivo | 200.000 |
| Fuente de medios | Todas las fuentes de medios |
| Agencia | Todas las agencias |
| Geografía | Todas las áreas geográficas |

</Accordion>

<div id="create-a-custom-report" />

<Accordion title="Crear un informe personalizado">

Puede crear un informe personalizado configurando sus filtros y campos.

**Para crear un informe personalizado:**

1. En AppsFlyer, desde el menú lateral, seleccione **Exportar** > **Exportación de datos sin procesar**.
2. Haga clic en + **Nuevo informe**.
3. Desplace el cursor sobre el tipo de informe que desea generar y haga clic en **Crear**.
4. Seleccione **Personalizar** del menú desplegable.
5. Configure los filtros del informe
   * **Fechas de actividad:** Seleccione el intervalo de fechas de la actividad. Puede establecer una fecha específica o elegir entre las opciones como personalizadas, ayer, últimos 7 días, etc.
   * **Máximo de filas por archivo:** [Opcional] Establezca la cantidad máxima de filas que puede incluir un archivo. Elija entre 100, 200K, 500K o 1 millón de filas.
   * **Fuente de medios:** [Opcional] Solo se incluirán los eventos atribuidos a las fuentes de medios seleccionadas en el informe. Puede añadir una fuente de medios a la lista haciendo clic en **Agregar elemento**.

     <div id="note" />

     > 📘 **Nota**
     >
     > Los PID web de las redes de autorreporte (SRN), como `metaweb_int`, `googleds_int` o `tiktokweb_int`, no aparecen automáticamente en la lista desplegable de fuente de medios. Para filtrar los postbacks web de SRN, haz clic en **Add item** e introduce manualmente el PID de la fuente de medios web.

   * **Agencia:** [Opcional] Solo se incluirán los eventos atribuidos a las agencias seleccionadas en el informe. Puede añadir una agencia a la lista haciendo clic en **Agregar elemento**.
   * **Geografía:** [Opcional] Solo se incluirán los eventos de las áreas geográficas seleccionadas en el informe.
   * **Filtro específico del tipo de informe**: Cada tipo de informe puede tener su propio filtro, desde el cual puede seleccionar un criterio de filtrado.
6. [Opcional]: Los informes se completan automáticamente con los campos necesarios. Puede añadir o eliminar campos de la siguiente manera:
   1. <span class="af-ol-a"></span>Acceda a la pestaña **Campos del informe**. Se mostrará la lista de campos seleccionados. No puede cambiar la selección de los campos obligatorios.
   2. Seleccione o deseleccione los campos según sea necesario.
   3. [Opcional] Establezca **Orden de los campos del informe (CSV)** para definir la secuencia de columnas.
   4. [Opción] Haga clic en **Restaurar valores predeterminados** si es necesario.
7. Haga clic en **Crear**.
   * La página **Mis informes** se muestra. Inicialmente, el estado indica que el informe se está generando.
   * La generación puede tardar hasta 10 minutos.
   * Durante la generación del informe, puede seguir trabajando, crear informes adicionales o navegar a otras páginas.

</Accordion>

<div id="download-report" />

<Accordion title="Descargar informe">

**Para descargar un informe**:

1. En AppsFlyer, desde la barra lateral, abra **Exportar** > **Exportación de datos sin procesar**.
2. Haga clic en ![DownloadIcon.png](https://files.readme.io/6c00f4922fc3a835a856d7fdf527aa32d2f50570710c1527b039f43a7acbba79-41225791763217.png) (descargar) para obtener el informe. Los informes generados están disponibles para descargar durante 7 días.

</Accordion>

<div id="duplicate-and-edit-report-settings" />

<Accordion title="Duplicar y editar las configuraciones de informes">

**Para duplicar y editar la configuración del informe:**

1. En AppsFlyer, desde la barra lateral, abra **Exportar** > **Exportación de datos sin procesar**.
2. Haga clic en ![Duplicar.png](https://files.readme.io/f745081f1bf0c4f5861e275a29048fe84e8020f8b3bf4ebe4ad6a8d9254ab4b5-41225784681233.png) para duplicar la configuración del informe y luego edite la configuración.
3. Haga clic en **Crear**. Los informes generados están disponibles durante 7 días.   
   * Se muestra la página **Mis informes**. Inicialmente, el estado indica que el informe se está generando.
   * La generación puede tardar hasta 10 minutos.
   * Durante la generación del informe, puede seguir trabajando, crear informes adicionales o navegar a otras páginas.

</Accordion>

<div id="additional-information" />

## Información adicional

<div id="traits-and-limitations" />

<Accordion title="Características y limitaciones">

| Caducado | Observaciones |
| --- | --- |
| Acceso a la red de anuncios | Sí |
| Acceso a la agencia | Sí |
| Zona horaria específica de la aplicación | Sí |
| Moneda específica de la aplicación | Sí |
| Limitaciones | Hasta un millón de registros por descarga |
| Datos no orgánicos | Disponible |
| Datos orgánicos | Disponible |
| Actualización de datos | Dependiente del informe |
| Datos históricos | Últimos 90 días |
| Acceso del usuario a la cuenta | Usuarios en <Anchor target="_blank" href="/marketers/es/docs/user-management">roles con los permisos requeridos</Anchor> |
| Envio por correo electrónico | No compatible |
| Rango de fechas de instalación | El intervalo de fechas de instalación debe ser anterior al intervalo de fechas de actividad. |
| Informes de devolución de datos brutos | Los postbacks enviados a socios debido a eventos atribuidos a agencias no transparentes no se incluyen en los informes de postbacks de datos brutos del anunciante. |

</Accordion>

<div id="field-sequence-templates" />

<Accordion title="Plantillas de secuencia de campos">

La configuración del orden de los campos del informe le permite especificar la secuencia de columnas en los informes y, en algunos casos, los propios campos.

| Ajustes | Selección de campo permitida | Observaciones |
| --- | --- | --- |
| <span id="default::b7bb6355"></span>Predeterminado | Sí | <ul><li>Los campos seleccionados se ordenan conforme a una plantilla de AppsFlyer.</li><li>A partir de ahora, la secuencia se mantendrá. Los futuros campos se añadirán a la derecha de los existentes.</li></ul> |
| <span id="alphabetical-az::b08af6b3"></span>Alfabético (A-Z) | Sí | Los campos seleccionados se ordenan alfabéticamente. |
| <span id="alphabetical-za::f0b3beb8"></span>Alfabético (Z-A) | Sí | Los campos seleccionados se ordenan en orden alfabético inverso. |
| <span id="legacy::fb5fd8ec"></span>Heredado | No | <ul><li>Los campos se ordenan según la secuencia de columnas en los informes creados con la versión anterior de la página de exportación de datos.</li><li>La selección de campos es fija y no se puede modificar.</li><li>Existen variaciones en los informes por campo según el informe específico.</li></ul> |

Esta [hoja de cálculo](https://docs.google.com/spreadsheets/d/e/2PACX-1vRGYcMOgC5yy_82yn3DWd3ucLE5KtuTA72eJfvu5KVB9fFH_mYwzM3KpR_inQOnat-KzgVjuuvXa6_g/pub?output=xlsx) contiene tanto una hoja predeterminada como una heredada. Cada una contiene la lista del orden de los campos correspondiente.

**Para cambiar el orden de los campos:**

1. En la pestaña de Campos del informe, seleccione una opción de **Orden de campos del informe**.
2. Si es necesario, modifique los campos seleccionados seleccionando o desmarcando los campos necesarios.

</Accordion>

<div data-zendesk-anchors="h_01HA28AT6QRSG68NBFYHH5SQY8=raw-data-export-page-features-and-filter-options procedures=procedimientos h_01HA28AT6Q9PV3M55C1YM3XN2E=procedimientos h_01HZY1HQ9AVH6Q9QAQB4SM1VPX=create-a-default-report h_01HZY1HQ9ACEMZ4N8WPYNHZQP7=create-a-custom-report h_01_web_srn_media_source_filter=nota h_01HA28AT6QV1XP4N952PAEGSSG=download-report h_01HA28AT6QFT88RHJ3M05MV3B3=duplicate-and-edit-report-settings additional-information=informaci%C3%B3n-adicional h_01HA28AT6Q4DXKCZ22R9XEN2RR=informaci%C3%B3n-adicional h_01HA28AT6Q6SE8CB3EEXFMAN0H=traits-and-limitations h_01HA28AT6RW8C99ZGEBTN5E44R=field-sequence-templates" />
