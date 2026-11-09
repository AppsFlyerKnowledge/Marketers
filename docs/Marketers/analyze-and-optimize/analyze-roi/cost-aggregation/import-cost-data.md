---
title: Importar datos de costo
metadata:
  keywords:
    - Ad Network
    - Agency
    - Advertisers
    - Agencies
    - Premium
    - Premium Feature
    - Xpend
    - Marketers
    - ROI360
    - Ad Networks
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - Agencies
    - ROI360
    - Ad Networks
  created_at: '2019-09-15T15:53:44Z'
  edited_at: '2026-08-12T11:48:05Z'
  id: 360002516838
  locale: es
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/es/articles/360002516838
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En resumen:** Cost Import, parte de AppsFlyer ROI360, permite a los anunciantes obtener una cobertura completa y precisa de su costo de marketing al importar archivos CSV a través de uplaod o correo electrónico.

<div id="overview" />

## Visión general

Utiliza Cost Import para:

* Obtener los costos de campaña de cualquier actividad de marketing (campañas móviles, campañas de influencers, CTV y más) a AppsFlyer. Esto es particularmente importante para las fuentes de medios que no informan el costo a través de API o en el enlace de atribución.
* Sobrescribir y corregir retroactivamente los datos de costo existentes.

El costo se reporta a través de archivos CSV o enviados por correo electrónico a AppsFlyer. Una vez que AppsFlyer recibe el archivo, los datos se procesan y están disponibles en dashboards en unas pocas horas. Esto te da una imagen completa de los costos de tu campaña y del ROI.

**Nota**:

* Las ad networks pueden importar archivos de costo para sus clientes si se proporcionan los permisos relevantes.
* Las agencias no pueden subir datos. Pueden preparar sus archivos y enviarlos al anunciante para que los suban.

<div id="procedures" />

## Procedimientos

Para utilizar Cost Import y enviar datos de costo a AppsFlyer, necesitas:

1. [Preparar el archivo CSV](/docs/import-cost-data#prepare-csv-file-with-cost-data) con los datos de costo para enviar.
2. Envía el archivo a AppsFlyer a través de:
   * [Subir](/docs/import-cost-data#email-file) el archivo en la IU de AppsFlyer.
   * [Correo electrónico](/docs/import-cost-data#email-file). **Nota**: Para aplicaciones en plataformas de CTV, PC y consola, utiliza solo este método.

Consulta las secciones que siguen para obtener instrucciones detalladas.

<div id="prepare-csv-file-with-cost-data" />

<Accordion title="Prepara el archivo CSV con datos de costo">

Los anunciantes, las ad networks y agencias pueden preparar el archivo CSV de Cost Import. <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQ0oJTWdlNyT1gBHkGaN1QP-tUatugbPBzC2qYVNmjl_T_i3fKo1abYzTp6F7OqGeN_f7bBAJa3hxVz/pub?gid=0&single=true&output=csv">Ver archivo de muestra</Anchor>

**Para preparar el archivo CSV**:

* Sigue el esquema del archivo, formato y reglas detalladas en las siguientes tablas.  
  De forma opcional, también puedes incluir los clics y las impresiones reportados por la ad network junto con tus datos de costo. **Nota**: ¿Estás utilizando Excel/Google Sheets para preparar el archivo? [Lee esto](/docs/import-cost-data#using-excel-or-google-sheets-to-prepare-csv-file).

<div id="csv-schema" />

#### Esquema CSV

<table><thead><tr><th><p><span>Nombre de columna </span></p><p><span>(distingue entre mayúsculas y minúsculas)</span></p></th><th><span>Formato/observaciones</span></th><th><span>Ejemplo</span></th><th><span>Obligatorio</span></th></tr></thead><tbody><tr><td><span>fecha</span></td><td><ul><li><span>La fecha en que ocurrió el costo</span></li><li> <span><strong>Anunciantes</strong>: </span><ul><li><span>AAAA-MM-DD</span></li><li><span>MM/DD/YYYY </span></li><li><span>MM-DD-YYYY</span></li><li> <span>Token de ad network</span>:<br/> </li></ul></li><li>No se permiten fechas futuras.</li><li> <strong>Prácticas recomendadas</strong>: Utiliza la misma zona horaria que la definida para tu aplicación en AppsFlyer.</li><li> <strong>Nota</strong>: ¿Estás usando Excel/Google Sheets para preparar el archivo? ¿Estás utilizando Excel/Google Sheets para preparar el archivo? <a href="./import-cost-data#using-excel-or-google-sheets-to-prepare-csv-file">Lee esto</a>. </li></ul></td><td><ul><li><span>05-2019-30</span></li><li><span>2019/05/30</span></li><li><span>30-5-2019</span></li><li>5/30/2019</li><li>05-30-2019</li><li>05/30/2019</li></ul></td><td><span>✓</span></td></tr><tr><td><span>app-id</span></td><td><ul><li><span>Formato: Cadena</span></li><li> ID de la aplicación tal como aparece en AppsFlyer</li><li>Se permiten múltiples aplicaciones en un solo archivo.</li><li>Todos los IDs de la aplicación deben pertenecer a la misma cuenta de anunciante.</li></ul></td><td><ul><li><span>com.app.name </span></li><li><span>id12356789</span></li></ul></td><td><span>✓</span></td></tr><tr><td><span>media-source</span></td><td><ul><li><span>Formato: Cadena</span></li><li><span>Nombre de la fuente de medios <strong>exactamente</strong> como aparece en AppsFlyer. <strong>Nota:</strong> Incluye el sufijo _int si es necesario.</span></li><li> <span>Solo se permite una fuente de medios por archivo. </span><span></span>Se permiten múltiples aplicaciones para la misma fuente de medios.</li></ul></td><td><span>network_x_int</span></td><td><span>✓</span></td></tr><tr><td><span>campaña única</span></td><td><ul><li> <span>Formato: String</span><span></span> </li><li><span>Nombre de la campaña. Si el nombre de la campaña aparece en la ad network, el nombre en este archivo debe coincidir (sensible a mayúsculas y minúsculas).</span></li><li>No utilices el mismo nombre de campaña para varias aplicaciones.</li></ul></td><td>campaign_a</td><td><p><span>✓</span></p><p><span><strong>Nota</strong>: Si los datos de atribución existen con nombre e ID, el CSV debe contener ambos para que coincidan.</span></p></td></tr><tr><td><span>spend</span></td><td><ul><li><span>Costo monetario</span></li><li><span>Se permiten cinco dígitos después del punto decimal</span></li><li><span>Se permite el valor 0 (cero).</span></li><li> <span><strong>Nota</strong>: </span><ul><li>No se permiten separadores de coma en 1000, por ejemplo: "2,874.12".</li><li>¿Estás utilizando Excel/Google Sheets para preparar el archivo? ¿Estás utilizando Excel/Google Sheets para preparar el archivo? <a href="./import-cost-data#using-excel-or-google-sheets-to-prepare-csv-file">Lee esto</a>.</li></ul></li></ul></td><td><p><span>2874.12345</span></p></td><td><span><span>✓</span></span></td></tr><tr><td><span>clics-reportados</span></td><td><ul><li><span>Formato: Entero</span></li><li><span>La cantidad de clics reportados por la ad network.</span></li><li><span>Solo números enteros. No se permiten decimales, separadores de comas, símbolos de moneda ni notación científica.</span></li><li><span>El valor debe ser 0 o superior. Se permite el valor 0.</span></li></ul></td><td><span>1200</span></td><td><span>No</span></td></tr><tr><td><span>impresiones-reportadas</span></td><td><ul><li><span>Formato: Entero</span></li><li><span>La cantidad de impresiones reportadas por la ad network.</span></li><li><span>Solo números enteros. No se permiten decimales, separadores de comas, símbolos de moneda ni notación científica.</span></li><li><span>El valor debe ser 0 o superior. Se permite el valor 0.</span></li></ul></td><td><span>45000</span></td><td><span>No</span></td></tr><tr><td><span>geolocalización</span></td><td><ul><li><span>Formato: Cadena</span></li><li> Código de país de dos letras que cumple con la norma <a href="https://www.iso.org/iso-3166-country-codes.html">ISO 3166</a>. <strong>Nota</strong>: Asegúrate de enviar dos caracteres sin espacios en blanco. </li><li> <strong>Asunto</strong><span>: Pega el token para la importación de correos electrónicos en el campo del asunto.</span><br/> </li></ul></td><td><p><span>US, CN, AU</span></p></td><td><span>No</span></td></tr><tr><td><span>moneda</span></td><td><ul><li><span>Formato: Cadena</span></li><li>Código de moneda de tres letras que cumple con la norma <a href="https://www.iso.org/iso-4217-currency-codes.html" target="_blank">ISO 4217</a>. <strong>Nota</strong>: Asegúrate de enviar tres caracteres sin espacios en blanco iniciales o finales.</li><li> <span>Se permite un código de moneda por aplicación en el archivo. Diferentes</span><span> aplicaciones pueden tener diferentes códigos de moneda.</span>  </li></ul></td><td><span>USD, GBP, EUR, JPY</span></td><td><p><span>N.º</span></p><p><span>El valor predeterminado será USD si se deja vacío.</span></p></td></tr><tr><td><span>campaign-id</span></td><td>Formato: Cadena</td><td>abc1234def</td><td rowspan="5"><p>N.º</p><p><strong>Nota</strong>: Si los datos de atribución existen con nombre e ID, el CSV debe contener ambos para que coincidan.</p></td></tr><tr><td><span>conjunto de anuncios</span></td><td>Formato: Cadena </td><td>my_adset_1</td></tr><tr><td><span>adset-id</span></td><td>Formato: Cadena</td><td>id5678ghi</td></tr><tr><td><span>anuncio</span></td><td>Formato: Cadena </td><td>my_ad_name</td></tr><tr><td> <span>ad-</span><span>id</span> </td><td>Formato: Cadena </td><td>id91011jkl</td></tr><tr><td><span>site-id</span></td><td><ul><li>Formato: Cadena </li><li>ID único que identifica al publisher que muestra el anuncio.<span> </span><a href="./about-link-structure-and-parameters#site-id-parameter" target="_blank">Saber más</a> </li></ul></td><td>id1213mno</td><td>No</td></tr><tr><td><span>channel</span></td><td>Formato: Cadena </td><td> Video</td><td>No</td></tr><tr><td><span><span>palabras clave</span></span></td><td>Formato: Cadena</td><td><ul><li>mejor</li><li>mejora tu app</li><li>better you online</li></ul></td><td>No</td></tr><tr><td><span>agencia</span></td><td><ul><li>Formato: Cadena</li><li>El nombre de la agencia. (El valor en el parámetro af_prt)</li><li>Solo se puede incluir una agencia en un archivo. Y solo se pueden incluir en el archivo las campañas gestionadas por esa agencia.</li><li>El nombre de la agencia es obligatorio por fila. No se permiten celdas en blanco en la columna de la agencia.</li><li>La agencia debe tener permiso para todas las aplicaciones incluidas en el archivo.</li><li>Solo los anunciantes pueden subir el archivo. Las agencias no pueden subir datos. Pueden preparar sus archivos y enviarlos al anunciante para que los suban.</li><li>Si se vuelven a enviar datos de costo para las mismas fechas y el nombre de la agencia (<code>af_prt</code>) se incluye en un envío posterior cuando no estaba presente en el original, esto da como resultado datos de costo duplicados.</li></ul></td><td>Nombre de la agencia</td><td>No</td></tr><tr><td colspan="4"><span><strong>Nota:</strong> Los nombres que tengan caracteres que no estén en inglés deben codificarse con UTF-8.</span></td></tr></tbody></table>

<div id="csv-format-and-rules" />

#### Formato y reglas CSV

| Regla | Requisito |
| --- | --- |
| Caracteres prohibidos | Los campos en formato de cadena no pueden tener `=`, `+`, `-` o `@` como primer carácter. Por ejemplo, `@example_campign` o `=123` están prohibidos. |
| Propietario de la aplicación | Se permite un anunciante (propietario de la aplicación) por archivo. Se permiten múltiples aplicaciones de la misma cuenta de anunciante. |
| Extensión del nombre de archivo | Ejemplo CSV: abc123.csv |
| Estructura de archivos | <ul><li>**Formato**: Los archivos tienen un formato CSV, lo que significa que cada columna está separada por una coma.</li><li>**Fila de encabezado**: La primera fila es una fila de encabezado que coincide con el esquema.</li><li>**Filas de datos**: Contiene las columnas obligatorias. **Nota**: Asegúrate de que no haya espacios en blanco al final de los datos. Por ejemplo, [USD] (con un espacio en blanco después de la **D**) debe cambiarse a [USD].</li><li>**Filas en blanco**: No permitido</li><li>**Filas duplicadas** que tienen la misma clave: No está permitido. La clave se deriva del uso de los campos obligatorios.</li><li>**Celdas en blanco:** <mark>No se permiten valores vacíos en el archivo.</mark> Si no quieres subir ciertos campos, no deben estar en el archivo.</li></ul> |
| Jerarquía publicitaria | El costo debe registrarse a nivel de campaña, siendo opcionales otras dimensiones en la jerarquía publicitaria.<br /><br />Cualquier dato parcial que se suba en una jerarquía inferior anulará todos los datos del nivel de campaña hacia abajo.<br /><br />**Por ejemplo:** Si importas un archivo con el costo de la campaña para el adset 1 e importas por separado otro archivo para el adset 2 de la misma campaña, se reemplazará el costo total de la campaña y solo se mostrarán los datos del adset 2. Para el costo total de la campaña, el archivo que importes debe incluir el adset 1 y el adset 2. |

</Accordion>

<div id="upload-file" />

<Accordion title="Upload archivo">

Los anunciantes y las ad networks pueden cargar archivos CSV de Cost Import.

Para el Reino Unido, utiliza UK, no GB.

**Para cargar el archivo CSV a través de la interfaz de usuario de AppsFlyer**:

1. En AppsFlyer, en el menú lateral, selecciona **Configuración** > **Cost Import.**  
   Aparece la página de Cost Import. Sin embargo, asegúrate de crear plantillas separadas con el subdominio; no agregues manualmente el subdominio al ID de plantilla.
2. Haz clic en **+ Importar archivo de costos**  
   Se abre la ventana de importación de costos.
3. Arrastra el archivo CSV a la ventana de **Importación de costos**.  
   Se muestra el mensaje procesando archivo.
4. Si aparece un mensaje de error durante el upload, corrígelo y repite los pasos correspondientes.
5. Se abre la ventana **Cost Import: resumen de archivos**.
6. Realiza una de las siguientes acciones:
   * Anula el upload, haz clic en **Cancelar importación**.
   * Completa el proceso de importación, haz clic en **importar archivo.**  
     Se muestra el mensaje “¡Todo listo!” muestra.
   * Si se muestra un mensaje de error, sigue las [instrucciones del mensaje de error](/docs/import-cost-data#cost-import-permissions-for-ad-networks).
7. Haz clic en **importar otro archivo** o en **Listo**.

</Accordion>

<div id="email-file" />

<Accordion title="Archivo de correo electrónico">

Los anunciantes y las ad networks pueden enviar por correo electrónico archivos CSV de Cost Import.

**Requisitos previos**:

* **Requisitos previos**: Las ad networks requieren [permiso de Cost Import del anunciante](/docs/import-cost-data#cost-import-permissions-for-ad-networks). 
  * El correo electrónico del remitente debe ser de un usuario registrado de AppsFlyer.
* **Redes publicitarias**:
  * El correo electrónico del remitente debe ser de un usuario registrado de AppsFlyer.
  * En AppsFlyer, en el menú lateral, selecciona **Configuración** > **Cost Import.**

**Para enviar el archivo CSV por correo electrónico**:

1. Obtén el [token para la importación por correo electrónico](/docs/import-cost-data#token-for-email-import).
   1. Borra **Usar separador de 1000 (,).** Sin embargo, asegúrate de crear plantillas separadas con el subdominio; no agregues manualmente el subdominio al ID de plantilla.
   2. En la parte superior derecha de la página, haga clic en **Token para la importación de correos electrónicos.**
   3. Copia y guarda el token.
2. Redacta el correo electrónico con los siguientes campos:
   * **Para**:`adspend-upload@appsflyer.com`
   * CC: Usuarios que deben recibir una copia de los comentarios automáticos
   * **Asunto**: Pega el token para la importación por correo electrónico en el campo del asunto.
   * **Archivo adjunto**: CSV con los datos.
3. Envía el correo electrónico.
   * Una vez que se reciba y procese el archivo, un correo electrónico de estado resume los detalles, problemas o errores encontrados durante el procesamiento. El correo electrónico se envía a todas las partes del correo electrónico de envío y al administrador del anunciante. Donde se identifiquen errores, sigue las instrucciones del mensaje del error.
   * Puedes ver el estado de los archivos enviados en el [dashboard de Cost Import](/docs/import-cost-data#error-messages-and-solutions)

</Accordion>

<div id="dashboard" />

## Panel de Control

El dashboard de Cost Import es donde puedes cargar archivos y ver detalles de archivos previamente cargados.

<div id="cost-import-dashboard" />

<Accordion title="Dashboard de Cost Import">

Para ver el dashboard de Cost Import, en AppsFlyer, desde el menú lateral, selecciona **Configuración** > **Cost Import**.

Los detalles sobre la información disponible para archivos importados previamente se describen en la siguiente tabla.

| Nombre de columna | Descripción |
| --- | --- |
| Nombre de archivo CSV | El nombre de los archivos de costos importados a AppsFlyer. |
| Fecha de upload | Fecha en que se importó el archivo. |
| Fuente de medios | Fuente de medios incluida en el archivo. |
| Rango de fechas | Fechas de inicio y fin en el archivo en las que se produjo el gasto publicitario. |
| Filas con coincidencias (%) | El porcentaje de filas en el archivo donde el costo se asignó a la atribución. [Saber más](#matched-rows). |
| Estado | El estado del archivo importado:<ul><li>**Éxito**: Acción completada con éxito. El costo se registra y está disponible en los dashboards y reportes de AppsFlyer.</li><li>**Error de validación**: Problema del sistema de AppsFlyer. Espera 10 minutos e inténtalo de nuevo. Si vuelve a fallar, comunícate con el soporte de AppsFlyer.</li><li>**Sin permisos**: El token no está aprobado para esta aplicación.<ul><li>Anunciantes: Asegúrate de que el ID de la aplicación sea correcto.</li><li>Ad networks: Confirma con el anunciante que le han dado permiso para Cost Import.</li></ul></li><li>**Revertido**: Acción completada con éxito. El archivo fue sobrescrito/reemplazado por otros datos.</li></ul> |
| Acción | <ul><li>Si tienes permiso de aplicación para la aplicación, puedes:<ul><li>**Descargar el archivo CSV**: Esta es una copia del archivo CSV importado.</li><li>**Descargar el reporte sin coincidencias** para todas las aplicaciones en el archivo. Consulta la sección de filas coincidentes de esta tabla para más información.</li></ul></li><li>A nivel de archivo: Si tienes permisos de aplicación para todas las aplicaciones contenidas en el archivo, puedes:<ul><li>**Descargar los datos de la aplicación.**</li><li>**Descargar el reporte sin coincidencias** para la aplicación.</li><li>**Revertir**(cancelar) el Cost Import de la aplicación seleccionada.</li></ul></li></ul> |

</Accordion>

<div id="matched-rows" />

<Accordion title="Filas con coincidencias">

La coincidencia de filas es el proceso donde el costo reportado por la importación se empareja con los datos de atribución registrados en AppsFlyer. Esto se hace utilizando todos los nombres de dimensiones (no IDs) disponibles, como fuente de medios, campaña, conjunto de anuncios, anuncio, etc. Si todas coinciden, las filas se designan como is-matching=TRUE.

El costo se registra y está disponible en los dashboards y reportes de AppsFlyer, independientemente del estado de coincidencia.

El porcentaje de filas coincidentes se muestra en el dashboard de Cost Import. Si las filas no coincidentes son inesperadas o el número de filas coincidentes (%) es mayor de lo esperado:

* Descarga el reporte de no coincidentes para investigar la causa. El reporte sin coincidencias contiene una columna, is-matched, que puede tener un valor de filas TRUE (con coincidencias) o FALSE (sin coincidencias).
* Si es necesario, cancela la importación revirtiéndola.
* Consulta la sección de Acción de esta tabla para más detalles.

</Accordion>

<div id="additional-information" />

## Información adicional

<div id="using-excel-or-google-sheets-to-prepare-csv-file" />

<Accordion title="Utilizando Excel o Google Sheets para preparar el archivo CSV">

Al utilizar Excel/Google Sheets para crear un archivo CSV, las columnas de fecha y gasto deben tener el formato correcto antes de guardar el archivo como un archivo CSV. Después de guardar el archivo CSV, comprueba que el contenido tenga el formato correcto. Utiliza las siguientes pautas para:

* Formatear las celdas de fecha.
* Formatear las celdas de gasto.
* Verificar el formato del contenido.

<div id="format-date-cells" />

#### Formatear celdas de fecha

**Para formatear celdas de fecha en Excel con el formato AAAA-MM-DD**:

1. Selecciona las celdas que se van a formatear.
2. Haz clic derecho y luego selecciona **Formato de celdas**.  
   Se abre la ventana de formato de celda.  
   <Image align="center" alt="Formatdate..png" src="https://files.readme.io/43d0f370f299d73b8ce93fec1c912cb7525d0071db779a64a58f5917df2a5531-360004042458.png" width="379px" />
3. Selecciona **Personalizado**.
4. En el campo Tipo, ingresa **AAAA-MM-DD**
5. Haz clic en **OK**.  
   Se aplica el formato a la fecha.

<div id="formatting-spend-cells" />

#### Formato de celdas de gasto

Excel suele dar formato a las celdas de valor con una coma para separar los miles, como se muestra en la figura. Este formato no es adecuado para archivos de Cost Import.

<Image align="center" alt="mceclip1.png" src="https://files.readme.io/d54e21ddd937dfe25a33bb96193761a5a724c22a35a55bb7d71eb03a6433d7ed-360003949177.png" width="291px" />

Para formatear celdas de gasto sin un separador de coma de 1000:

1. Selecciona las celdas que se van a formatear.
2. Haz clic derecho y luego selecciona **Formato de celdas**.  
   Se abre la ventana de formato de celda.
3. Selecciona **Número**.  
   <Image align="center" alt="Formatnumbers.png" src="https://files.readme.io/4c1b61d1eae9149e818d4cc9793128fbdaafed5daed9acf6cbc503571475cc0e-34255643022481.png" width="381px" />
4. Borrar **Usa el separador de miles (,).**
5. (Opcional) Establece el número de **decimales**. El valor predeterminado es 2. El máximo permitido es 5.
6. Haz clic en **OK**.  
   Las celdas se formatean correctamente.

<div id="verify-content-format" />

#### Verificar el formato del contenido

**Para verificar el formato del contenido**:

1. Utiliza un editor para ver el archivo.
   * Windows: Bloc de notas, Bloc de notas++
   * macOS TextEdit
2. Presta especial atención a lo siguiente:
   * **Espacios en blanco:** Asegúrate de que no haya espacios en blanco al principio o al final antes o después de las comas que separan los campos. En Excel, usa el comando @trim para eliminar los espacios en blanco.
   * **Fecha:** Asegúrate de que las celdas de fecha tengan el formato AAAA-MM-DD.
   * **Gasto:** Asegúrate de que no haya comas en las celdas de gasto.
   * **Delimitadores**: Deben ser comas. Si son punto y coma:
     * Esto puede ocurrir cuando la configuración regional de tu computadora está configurada en un idioma/región que no es inglés, especialmente alemán.
     * La solución difiere según el sistema operativo de tu ordenador (macOS o Windows).
     * Para resolver este problema, busca la guía más reciente de <Anchor target="_blank" href="https://support.office.com/en-us/article/import-or-export-text-txt-or-csv-files-5250ac4c-663c-47ce-937b-339e391393ba#ID0EAAFAAA=Office_2016-2010">Microsoft</Anchor> u otros foros para encontrar una solución. Utiliza los siguientes términos de búsqueda: Sistema operativo (macOS o Windows) delimitador de cambios de Excel para archivos CSV.

A continuación se incluye una captura de pantalla del [archivo CSV de ejemplo](https://docs.google.com/spreadsheets/d/e/2PACX-1vQ0oJTWdlNyT1gBHkGaN1QP-tUatugbPBzC2qYVNmjl_T_i3fKo1abYzTp6F7OqGeN_f7bBAJa3hxVz/pub?gid=0&single=true&output=csv) mostrado en un editor.

<Image align="center" alt="mceclip1.png" src="https://files.readme.io/1398c5e9bad7a46b697e3b21030e64d656162e33a4a63f39475c64993bbe7a72-360003996197.png" width="672px" />

</Accordion>

<div id="token-for-email-import" />

<Accordion title="Token para importación de correo electrónico">

El token para la importación de correo electrónico se utiliza para verificar que el remitente del correo electrónico está autorizado para enviar el archivo de Cost Import.

Los tokens del anunciante y de la ad network son diferentes.

* Token del anunciante:
  * El mismo token es válido para todas las aplicaciones de la cuenta.
  * Cualquier usuario de la cuenta puede obtener el token.
* Token de red de publicidad:
  * Se utiliza el mismo token para todos los anunciantes.

¡Los anunciantes y las ad networks no deben compartir sus tokens entre sí!

</Accordion>

<div id="cost-import-permissions-for-ad-networks" />

<Accordion title="Permisos de Cost Import para ad networks">

Las ad networks requieren permiso del anunciante por aplicación para acceder al Cost Import.

**Para conceder a la ad network el permiso de Cost Import:**

1. En AppsFlyer, el **anunciante** debe ir al menú lateral y seleccionar **Colaborar** > **Integraciones activas.**   
   Aparece la página de Partner Integrado.
2. Selecciona el partner integrado.
3. Ve a la pestaña **Permisos**.
4. Habilita los **Permisos para ad networks** si no lo están.
5. (Opcional) Agrega usuarios de la cuenta.
6. Habilita **Usar Cost Import**.
7. Haz clic en **Guardar permisos**.

</Accordion>

<div id="troubleshooting-traits-and-limitations" />

## Solución de problemas, rasgos y limitaciones

<div id="error-messages-and-solutions" />

<Accordion title="Mensajes de error y soluciones">

En la tabla siguiente se enumeran todos los posibles mensajes de error de importación de costos y las soluciones correspondientes.

| Mensaje de error | Descripción | Solución |
| --- | --- | --- |
| Ninguno de los IDs de aplicación proporcionados en el archivo existe en AppsFlyer. Verifica la exactitud de los IDs de aplicación. | El ID de aplicación no existe en la cuenta. | Cambia el ID de aplicación y vuelve a enviarlo. |
| La línea [line name] tiene un número incorrecto de columnas. Se esperaban [number] columnas, se recibieron [number] columnas. | Todas las columnas del archivo deben tener un valor. | Cambia los valores rellenados en el archivo en función de los encabezados que hayas definido. |
| Falta 'media-source' en el encabezado del archivo. | <ul><li>Al encabezado del archivo le falta la fuente de medios.</li><li>El nombre de la columna debe ser exactamente como está en el esquema.</li></ul> | Agrega media-source como nombre de encabezado. |
| El archivo solo puede contener una fuente de medios. Múltiples fuentes de medios encontradas en el archivo: [number of media sources]. | No se puede subir un archivo con más de una fuente de medios. Las líneas vacías ocultas o las filas con formato incorrecto en el CSV también pueden provocar este error, aunque no sean visibles en Excel. | Abre el archivo en un editor de texto, como Notepad++, y elimina las líneas vacías o las filas con formato incorrecto. Guarda el archivo y vuelve a subirlo. Si el archivo contiene más de una fuente de medios, divídelo en un archivo por fuente de medios. |
| El valor proporcionado [value] para [field] no es un valor válido para esta columna. | El formato de los datos en la columna es incorrecto. Por ejemplo, la fecha es dd-mm-aa en lugar de aaaa-mm-dd. | Corrige el formato y vuelve a enviarlo. |
| Varias divisas identificadas para la aplicación. Por favor, utiliza una única divisa para cada aplicación en el archivo. Divisas encontradas: %number of currencies%. | Solo se puede usar una divisa para cada aplicación. | Utiliza una sola divisa en el upload y vuelve a enviarlo. |
| No se admiten las siguientes columnas en el encabezado del archivo: [file headers] | El encabezado del archivo no coincide con el esquema. Es decir, el nombre de la columna debe ser exactamente como está en el esquema. | Elimina las columnas no compatibles y vuelve a enviarlo. |
| Faltan columnas requeridas en el encabezado del archivo: [file headers] | Al encabezado del archivo le falta una columna obligatoria. | Agrega la columna que falta y sus valores y vuelve a enviarlo. |
| La aplicación contiene una fecha futura: [date] | No se permiten fechas futuras. | Corrige la fecha a la fecha actual o anterior, y vuelve a enviarlo. |
| El archivo está vacío. No hay datos que procesar. | El archivo está vacío. | Rellena los datos en el archivo y vuelve a enviarlo. |
| Las siguientes dos filas entran en conflicto debido a dimensiones idénticas. Proporciona una sola fila de gasto por conjunto de dimensiones. [filas conflictivas] | Hay más de una fila con los mismos campos clave (obligatorios). | Elimina las filas duplicadas y vuelve e enviarlo. |
| El archivo solo puede contener datos de una sola cuenta de anunciante. Se encontraron diferentes anunciantes en el archivo: [advertiser names] | Para los partners, una subida no puede ser para más de un anunciante. | Divide la subida en un archivo por cada anunciante. |
| La aplicación [app ID] no existe en la cuenta. Verifica el ID de la aplicación. | El ID de aplicación no existe. | Corrige el ID de aplicación y vuelve a enviarlo. |
| No se encontró el código de geolocalización (país) para la aplicación [app ID]. Usa un código ISO 3166 de 2 letras | La geolocalización no existe. | Corrige la geolocalización y vuelve a enviarlo. |
| No se encontró el código de divisa de la aplicación [app ID]. Utiliza un código ISO 4217 de 3 letras. | La divisa no existe. | Cambia la divisa por una que sea válida y vuelve a enviarlo. |
| Hubo errores de validación para una o más aplicaciones en el archivo. Revisa la información del archivo para obtener más detalles. | Hay más de un error en el archivo. | Descarga el archivo y revisa los errores. |
| Hubo un error interno al procesar el archivo, intenta subirlo nuevamente. | <ul><li>Problema de backend al procesar el archivo.</li><li>Normalmente se trata de un problema temporal.</li></ul> | Espera 1 hora y vuelve a subirlo. |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Rasgos y limitaciones">

| Caducado | Observaciones |
| --- | --- |
| Redes publicitarias | Compatible.<br /><br />Excepciones:<ul><li>Anuncios de Meta</li><li>Anuncios X</li><li>ASA</li></ul> |
| Agencias | <ul><li>Las agencias no pueden subir datos. Pueden preparar sus archivos y enviarlos al anunciante para que los suban.</li><li>Para ello, los archivos CSV deben contener una columna Agencia con el nombre de la agencia  (el nombre de la agencia es el valor del parámetro af\_prt). [Consulta el esquema CSV](/docs/import-cost-data#esquema-csv)</li></ul> |
| Transparencia de agencia | No es compatible |
| Zona horaria específica de la aplicación | Compatible |
| Moneda específica de la aplicación | Compatible. Los costos de campaña se convierten a la divisa específica de la aplicación. |
| Nombre de la campaña | El mismo nombre de campaña no se puede usar para varias aplicaciones, o el costo de una aplicación se aplicará a ambas. |
| Nombres de campo | Si los nombres de campo en la jerarquía de la campaña no coinciden con los nombres de campo tal como aparecen en los datos de atribución, se contabilizarán por separado. <br /><br />Por ejemplo, si los nombres de las campañas no coinciden, entonces aunque los IDs de campaña sean los mismos, se contabilizarán como campañas diferentes. |
| Tamaño del archivo | Al cargar un archivo de importación de costos CSV, el límite de tamaño es:<ul><li>A través del dashboard de AppsFlyer: 2 MB</li><li>Por correo electrónico: 5 MB por archivo</li></ul> |
| Datos orgánicos | Compatible |
| Datos no orgánicos | Compatible |
| Actualización de los datos | <Anchor target="_blank" href="/marketers/es/docs/about-data-freshness-and-timezone-support#intraday-during-the-day">Gasto publicitario</Anchor> |
| Datos históricos | Compatible. Los costos reportados pueden revertirse y los datos corregidos enviarse en un plazo de hasta 90 días. |
| Reorientación | No es compatible. |
| Acceso de usuario a la cuenta | No está disponible para usuarios con restricciones de geolocalización o fuente de medios. |

</Accordion>

<div id="see-also" />

> 📄 **Véase también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/about-link-structure-and-parameters">Estructura y parámetros del enlace de atribución</Anchor>
> * Filas con coincidencias

<div data-zendesk-anchors="ad-spend-import=visi%C3%B3n-general 01H7VYHJ2BN3EFDC4J3YN3P4WM=visi%C3%B3n-general procedures=procedimientos h_01HYZBZMNTM0244V4PN6AJ45KR=procedimientos h_01HYZD52VRTMGJ0BFBFJNGQ50E=prepare-csv-file-with-cost-data ad-spend-csv-schema=esquema-csv 01H7VYHJ2CWF2HWHCTZDEZHT29=esquema-csv csv-format-and-rules=formato-y-reglas-csv h_01HYZEDYKCAPTK1WD6VGWTA6PQ=formato-y-reglas-csv h_01HYZD52VRWK7D6Q0YBW9SEFK6=upload-file h_01HYZKN3YEPFG8525GFQD0PC5K=email-file dashboard=panel-de-control h_01HZ4NVKPVHV1KT12V59MZBGPZ=panel-de-control h_01HZ1SXQQ2CHG77KX96D74J6TQ=cost-import-dashboard h_01HZ4NVKPVSM5ZTG76HJF3GW4J=matched-rows additional-information=informaci%C3%B3n-adicional h_01HYZFNKFEQW13F0BWAG3FZF69=informaci%C3%B3n-adicional h_01HYZFNKFE3AVH1GNGDT511M5B=using-excel-or-google-sheets-to-prepare-csv-file formatting-date-cells-in-excel=formatear-celdas-de-fecha 01H7VYHJ2DSWC2J1NY04Q9Q620=formatear-celdas-de-fecha formatting-spend-cells-in-excel=formato-de-celdas-de-gasto 01H7VYHJ2DA9JM4Q33V2TF7BD3=formato-de-celdas-de-gasto verify-content-format=verificar-el-formato-del-contenido h_01HYZJJVC463C141AQ3VY5Z0TQ=verificar-el-formato-del-contenido h_01HYZFNKFEXK4CYRBZ3ABRCWNJ=token-for-email-import h_01HZ1XV6ZX5FAN9JJPQM9RYD3Z=cost-import-permissions-for-ad-networks troubleshooting-traits-and-limitations=soluci%C3%B3n-de-problemas-rasgos-y-limitaciones h_01HZ4PBGAG9R9JMHPXVQC1GX3V=soluci%C3%B3n-de-problemas-rasgos-y-limitaciones h_01HZ2859J5P6MFKACKBK46J6GP=error-messages-and-solutions h_01HZ27W0409NF4Y6RNT8WPW8HP=traits-and-limitations h_01KZ8QYNGH1Q6QXQDC14QG96FZ=v%C3%A9ase-tambi%C3%A9n" />
