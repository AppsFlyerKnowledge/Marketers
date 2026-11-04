---
title: Realiza acciones masivas de OneLink mediante CSV
metadata:
  keywords:
    - Marketers
    - bulk
    - QR-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - QR-to-App
  created_at: '2023-04-13T11:31:43Z'
  edited_at: '2026-08-22T00:33:21Z'
  id: 14511403892369
  locale: es
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/es/articles/14511403892369
---
> **De un vistazo:** La página Enlaces masivos de OneLink te permite crear y gestionar enlaces cortos personalizados de OneLink de forma masiva.

Los enlaces en masa te permiten crear y ver enlaces creados de forma masiva. Estos enlaces en masa se agrupan en un conveniente formato de colección que te permite realizar acciones en toda la colección, como agregar nuevos enlaces o descargarlos.

<div id="getting-started" />

## Primeros pasos

1. En AppsFlyer, ve a **Engage** > **Enlaces masivos**.
2. Verás una página de introducción con uno de los siguientes botones:
   1. <span class="af-ol-a"></span> **Comenzar**: envía para crear tu primera colección.
   2. **Crear una plantilla de OneLink**: se necesita una plantilla de OneLink para crear una colección. Consulta <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template">plantillas de OneLink</Anchor>.
   3. **Actualizar**: los enlaces en masa no están disponibles con tu paquete actual. Contacta a tu CSM o escríbenos a [hello@appsflyer.com](mailto:hello@appsflyer.com) sobre la actualización de tu paquete.

<div id="creating-your-first-collection" />

## Crear tu primera colección

1. Haz clic en **+ Nueva colección.**
2. Introduce un nombre para tu colección.  
   Elige un nombre que refleje el propósito de tu colección, para que puedas identificarla fácilmente más adelante.
3. Selecciona una plantilla de OneLink. Nota: todos los enlaces de la colección se basarán en esta plantilla
4. Haz clic en **Guardar y continuar.**
5. Sube tu archivo CSV. Puedes usar el siguiente <Anchor target="_blank" href="https://cdn.appsflyer.com/onelink-bulk-links-mgmt/sample_file.csv">CSV de muestra</Anchor> como guía.  
   Consulta [Formato de subida](/docs/perform-onelink-bulk-actions-via-csv#upload-format) para asegurarte de que tu CSV es compatible y se sube correctamente. Una vez que se sube el archivo CSV, se valida. Si hay filas no válidas, un reporte de validez CSV estará disponible para descargar para ayudarte a reparar tu archivo. Sigue las instrucciones de la interfaz de usuario y sube un archivo corregido.
6. Haz clic en **Crear colección.**

<div id="managing-your-bulk-links-with-collections" />

## Gestionar tus enlaces en masa con colecciones

Los enlaces en masa se gestionan en colecciones.

* En la parte superior de la página, el widget **Uso de enlaces en masa este mes** muestra el número de solicitudes de enlace (que incluye creaciones y actualizaciones de enlaces) fuera de la cuota mensual para el mes actual.
  * Actualmente, el límite predeterminado es de 20 000 creaciones de enlaces por mes

* La sección **Colecciones** te permite crear una nueva colección y realizar otras acciones a tus colecciones de enlaces actuales.
* Si hay más de siete colecciones, puedes buscar y filtrar tu lista de colecciones.
* Máximo de 2000 enlaces por colección.

<div id="other-actions" />

## Otras acciones

A continuación se presentan las otras acciones que se pueden realizar en una colección:

<div id="creating-a-new-collection" />

<Accordion title="Crear una nueva colección">

La creación de una nueva colección está disponible cuando no se ha superado el [uso mensual](/docs/perform-onelink-bulk-actions-via-csv#collection-features).

1. Haz clic en **Nueva colección**.
2. Sigue las instrucciones.
   1. <span class="af-ol-a"></span>El proceso sigue los mismos pasos que [Crear tu primera colección](/docs/perform-onelink-bulk-actions-via-csv#crear-tu-primera-colección).

</Accordion>

<div id="downloading-a-collection-of-links" />

<Accordion title="Descargar una colección">

La opción de descargar una colección está disponible cuando:

* Hay enlaces activos en esa colección.
* Tienes permisos de acceso a aplicaciones para al menos una de las aplicaciones móviles de la plantilla OneLink relacionada con la colección.

Para descargar una colección:

1. Enlaces en masa
2. Haz clic en el icono de descarga en la fila de la colección.
3. Selecciona el dominio para la URL corta resultante.
4. Haz clic en **Descargar**.

<div id="important" />

> 🚧 **¡Importante!,**
>
> AppsFlyer recomienda usar dominios de marca, ya que pueden mejorar el rendimiento de la campaña al impulsar la confianza y promover el conocimiento de la marca. <Anchor target="_blank" href="/marketers/es/docs/brand-onelink-with-your-domain">Aprende más aquí.</Anchor>

</Accordion>

<div id="downloading-a-collection-of-qr-codes" />

<Accordion title="Descargar una colección de códigos QR">

Puedes crear imágenes de QR code para toda la colección.

1. Enlaces en masa
2. En la fila de la colección, haz clic en el icono de descarga de imágenes de QR code <Image alt="generate qr.png" src="https://files.readme.io/23dbd4b2e3ed248e868ae7d5deee3cac383b0e018ae17204f9547f5707a428c9-21656949404561.png" width="22px" />.
3. En el cuadro de diálogo **Generar imágenes de QR code**, configura lo siguiente:
   * **Dominio:** Selecciona el subdominio o el dominio de marca de la URL que verán los usuarios finales después de escanear el QR code.
   * **Formato de imagen de QR code:** Elige PNG o SVG como formato de la imagen de QR code.
   * **Formato del nombre de archivo de QR code:** Selecciona el parámetro cuyos valores se usarán como prefijo de los nombres de archivo de las imágenes de QR code. Asegúrate de que los valores de este parámetro aporten un contexto significativo a los nombres de archivo para ayudarte a identificar el propósito de cada imagen QR.
4. Haz clic en **Generar.** Puedes supervisar el proceso de generación de archivos en el panel **Descargar imágenes de QR code**.
5. Para descargar el archivo ZIP, haz clic en el icono de descarga <Image alt="download-bulk.png" src="https://files.readme.io/8436aed2633bbed2f6cb65c00690711766c153c97042b5b157c199333e8723c2-21656949409041.png" width="18px" />.

<div id="note" />

> 📘 **Nota**
>
> * Una vez generado correctamente, el archivo estará disponible en el panel durante 24 horas y después se eliminará automáticamente.
> * El archivo descargado se proporciona en formato ZIP porque la carga útil consta de varios archivos de imágenes de QR code. Si tu navegador te solicita permitir descargas ZIP, proporciona la confirmación necesaria para continuar.
> * Puedes ejecutar hasta 2 procesos de generación de QR code simultáneamente.

</Accordion>

<div id="adding-links-to-a-collection" />

<Accordion title="Agregar enlaces a una colección">

La opción de agregar enlaces está disponible cuando:

* Tienes permisos de acceso a aplicaciones para al menos una de las aplicaciones móviles de la plantilla OneLink relacionada con la colección.
* Hay menos de 2000 enlaces activos en la colección.
* No se ha superado el [uso mensual](/docs/perform-onelink-bulk-actions-via-csv#collection-features).

Para agregar enlaces a una colección, haz clic en las **opciones del menú** > **Agregar enlaces a la colección.**

* Los enlaces se agregarán usando el mismo método descrito en [Crear tu primera colección](/docs/perform-onelink-bulk-actions-via-csv#crear-tu-primera-colección), a partir del punto 5.

</Accordion>

<div id="editing-links-in-a-collection" />

<Accordion title="Edición de enlaces en una colección">

La opción de editar enlaces está disponible cuando:

* Hay enlaces activos en esa colección.
* Tienes permisos de acceso a aplicaciones para al menos una de las aplicaciones móviles de la plantilla OneLink relacionada con la colección.
* No se ha superado el [uso mensual](/docs/perform-onelink-bulk-actions-via-csv#collection-features).

**Para editar enlaces en una colección:**

1. Haz clic en las **opciones del menú** > **Editar enlaces**.
2. Descarga el CSV base de la colección. Este archivo contiene todos los enlaces de la colección que puedes editar.
3. Sigue las instrucciones del primer paso para editar los parámetros del enlace. Para cualquier enlace que quieras actualizar, asegúrate de que **Marcar para actualización** esté configurado como **true**.
4. Haz clic en **Siguiente**.
5. Sube tu CSV editado. Consulta [Formato de subida](/docs/perform-onelink-bulk-actions-via-csv#upload-format) para asegurarte de que tu CSV es compatible y se sube correctamente.
   * Una vez que se sube el archivo CSV, se valida.
   * Si hay filas no válidas, un reporte de validez CSV está disponible para descargar para ayudarte a reparar tu archivo. Sigue las instrucciones de la interfaz de usuario y sube un archivo corregido.
6. Haz clic en **Actualizar enlaces**.

<div id="notes" />

> 📘 **Notas**
>
> * Si has descargado imágenes de QR code de esta colección de enlaces, puedes actualizar los parámetros del enlace y seguir usando las mismas imágenes, ya que los propios QR code no cambian.
> * Actualizar enlaces mediante la edición masiva ampliará el tiempo de vida (TTL) de los enlaces en 365 días.

</Accordion>

<div id="viewing-the-collection-history" />

<Accordion title="Ver el historial de la colección">

Para ver el historial de una colección, haz clic en las **opciones del menú** > **Ver historial de colecciones**.

La ventana del historial te mostrará las siguientes acciones, así como la fecha y hora en que se realizó la acción y por quién:

* **Cambios de nombre**: los cambios en el nombre de la colección.
* **Enlaces agregados**: cuando se agregaron enlaces a la colección.
* **Enlaces actualizados**: cuando se editaron y actualizaron enlaces de la colección.
* **Colección** **creada**: cuando se creó la colección.
* **ZIP de QR code descargado**: cuándo se generaron y descargaron las imágenes de QR code para la colección.

Los **enlaces agregados y actualizados** también te muestran cómo los cambios afectaron tu [cantidad de uso](/docs/perform-onelink-bulk-actions-via-csv#collection-features) y te permiten descargar un reporte de acción sobre ese cambio.

* Los reportes de acción solo se pueden descargar si tienes permisos de acceso a aplicaciones para al menos una de las aplicaciones móviles de la plantilla de OneLink relacionada con la colección.

</Accordion>

<div id="editing-the-collection-name" />

<Accordion title="Edición del nombre de la colección">

La opción de editar el nombre de la colección está disponible cuando:

* Tienes permisos de acceso a aplicaciones para al menos una de las aplicaciones móviles de la plantilla OneLink relacionada con la colección.

Para editar el nombre de una colección:

1. Coloca el cursor sobre el nombre de la colección que quieras cambiar.
2. Haz clic en el icono de edición junto al nombre de la colección.
3. Después de haber editado el nombre, pulsa enter o haz clic en otra parte de la pantalla.

</Accordion>

<div id="deleting-empty-collections" />

<Accordion title="Comenzar">

Selecciona una plantilla de OneLink  Nota: Todos los enlaces de la colección se basarán en esta plantilla.

**¿Por qué?**

1. Las agencias necesitan agregar manualmente el parámetro `af_prt` a sus enlaces.
2. Si una colección está vacía y tienes permisos de acceso a la aplicación para al menos una de las aplicaciones móviles de la plantilla de OneLink relacionada con la colección, se puede eliminar haciendo clic en las **opciones del menú -> Eliminar colección**.

<div id="important-notes" />

> 📘 **Notas importantes**
>
> * Asegúrate de que quieres eliminar la colección. Eliminar una colección con enlaces activos hará que los enlaces dejen de funcionar, lo que significa que los usuarios que hagan clic en ellos no se atribuirán ni se redirigirán correctamente. **Eliminar una colección es irreversible.**
> * Si quieres conservar un registro de los enlaces que has eliminado, puedes descargar la colección antes de eliminarla. **Para descargarla como archivo CSV:**
>   Haz clic en **Descargar la colección** en el mensaje de confirmación.

<div id="empty-collections" />

### Eliminar colecciones vacías

**Las colecciones pueden estar vacías debido a lo siguiente:**

* El <Anchor target="_blank" href="/marketers/es/docs/bulletin-onelink-short-url-ttls-automatically-extend">TTL (tiempo de vida)</Anchor> de todos los enlaces de la colección expiró.
* El proceso de nueva colección se canceló o no se completó antes de que se crearan los enlaces.

Máximo de 35 columnas de parámetros.

</Accordion>

<div id="general-information" />

## Información general

<div id="note-1" />

> 📘 **Nota**
>
> Los enlaces en masa creados antes de abril de 2023 no se mostrarán ni se administrarán en la página de enlaces en masa.

<div id="upload-format" />

<Accordion title="Formato de subida">

Para asegurarte de que tu CSV se suba sin errores, comprueba que tu archivo cumpla con los siguientes estándares:

* El archivo debe estar en formato CSV.
* El archivo no puede ocupar más de 4 MB.
* El archivo solo debe contener contenido para los enlaces que estás creando/actualizando.
* Cada enlace debe estar en su propia fila.
* El **ID de enlace personalizado** es una columna única que permite al usuario establecer el ID de la URL corta del enlace. El ID de la URL corta no se puede editar después de crear el enlace. Para saber más sobre el ID de URL, consulta <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#url-id">aquí</Anchor>.
* Cada columna representa un parámetro (máximo 35 columnas de parámetros)
* Solo se acepta la codificación de caracteres UTF-8.

</Accordion>

<div id="parameters-in-the-uploaded-csv" />

<Accordion title="Parámetros CSV">

* Los parámetros en el CSV pueden ser cualquier parámetro que sea aceptable en un enlace de AppsFlyer. Podrían ser parámetros reservados para la atribución (por ejemplo: c, af\_channel, af\_adset, etc.), para redirección & deep-linking (por ejemplo: af\_ios\_url, af\_dp, deep\_link\_value, etc.), o parámetros personalizados.
* El parámetro de la fuentes de medios (pid) es obligatorio.
* Incluso si se establece un esquema URI en la plantilla de OneLink, para los enlaces creados en masa, el parámetro af\_dp con el esquema URI debe especificarse en tu archivo CSV.

</Accordion>

<div id="faq" />

## PREGUNTAS FRECUENTES

<div id="qr-with-long-links-vs-short-links---is-there-any-difference" />

<Accordion title="QR con enlaces largos vs. enlaces cortos: ¿hay alguna diferencia?">

Tu código QR funcionará con una URL larga o corta. Sin embargo, si usas una URL corta, podrás actualizar los parámetros y el comportamiento del enlace desde el dashboard de OneLink (en la sección Gestión de enlaces) sin necesidad de sustituir el código QR publicado, ya que la propia URL corta no cambia.

* **URL cortas:** Si cambias los parámetros en la configuración de la URL corta, el código QR sigue siendo el mismo. No necesitas volver a publicarlo.
* **URL largas (por ejemplo, Smart Script):** Si cambias los parámetros de una URL larga, el código QR también cambia. Una vez que lo hayas publicado, no podrás actualizar el contenido de la URL de forma remota: tendrás que generar y distribuir un nuevo código QR.

</Accordion>

<div id="can-you-create-a-qr-code-and-change-the-behavior-behind-it-retroactively-after-printing-the-qr-for-example" />

<Accordion title="¿Puedes crear un código QR y cambiar retroactivamente el comportamiento asociado después de imprimirlo, por ejemplo?">

Sí, puedes hacerlo si el código QR se basa en una URL corta de OneLink que puedes editar (por ejemplo, una creada mediante la interfaz de OneLink). Un **código QR es una representación visual de la URL que tiene detrás**.  Si cambias la propia URL, se creará un nuevo código QR correspondiente (por ejemplo, el código QR de mike.onelink.me/123A/shorturl es diferente del código QR de mike.onelink.me/123A/example).

Sin embargo, como una URL corta de OneLink es una URL con hash, sus parámetros y reglas de redirección se configuran en el backend y no son visibles en la URL. Esto significa que puedes mantener la misma URL visible y el mismo código QR mientras editas su configuración en el backend.

</Accordion>

<div id="what-options-are-available-for-generating-qr-codes-in-appsflyer" />

<Accordion title="¿Qué opciones hay disponibles para generar códigos QR en AppsFlyer?">

Tienes las siguientes opciones:

* **A través del Dashboard de AppsFlyer → IU de OneLink:**
  * Genera automáticamente un QR code cuando creas un enlace
  * Permite personalizar los QR code
  * Se puede exportar como SVG o PNG
  * Basado en una URL corta
* **Creación masiva de QR code (a través de la página Bulk Links):**
  * Permite personalizar los QR code
  * Se puede exportar como SVG o PNG
  * Permite nombres de archivo contextuales
  * Basado en URL cortas
* **Generación de QR code con Smart Script:**
  * Basado en URL largas generadas dinámicamente
  * Los QR code se crean en consecuencia
  * Permite personalizar los QR code
  * Permite la creación masiva de QR code a partir de URL

</Accordion>

<div id="can-you-bulk-create-qr-codes" />

<Accordion title="¿Se pueden crear QR code de forma masiva?">

Sí. Puedes crear QR codes de forma masiva con la [función de creación masiva de QR codes](/docs/perform-onelink-bulk-actions-via-csv) disponible en la página Bulk Links.

</Accordion>

<div data-zendesk-anchors="getting-started=primeros-pasos h_01HKWSS511PMGTVEJN82SF5NX5=primeros-pasos creating-your-first-collection=crear-tu-primera-colecci%C3%B3n h_01HKWSS511SD4DFH7TMZV1EETH=crear-tu-primera-colecci%C3%B3n managing-your-bulk-links-with-collections=gestionar-tus-enlaces-en-masa-con-colecciones h_01HKWSS511XMB3CZ563SBZTEAC=gestionar-tus-enlaces-en-masa-con-colecciones other-actions=otras-acciones h_01HKWSS5113EPY13J2KHMWGDS7=otras-acciones h_01HKWSS511G8AREWDP05F6ZMER=creating-a-new-collection h_01HKWSS511DN9BSXFDNV053K63=downloading-a-collection-of-links h_01HKWSS511EDVWMAPHNGN711MG=importante h_01HKWSS511SQR18RGSSKGTERCV=downloading-a-collection-of-qr-codes h_01HKWSS5112CT9HV7K81QSHMGM=nota h_01HKWSS51125ZBCRQ087159YFH=adding-links-to-a-collection h_01HKWSS511AWCA4QV2NKVTTNKA=editing-links-in-a-collection h_01HKWSS512QYQBY0ZRE317528Z=notas h_01HKWSS512NZC3X8CPDDWB47JH=viewing-the-collection-history h_01HKWSS512RP5ATJWB38G88793=editing-the-collection-name h_01HKWSS512Q4MDFX75CK9VCREK=deleting-empty-collections h_01JQ69NF4SR7FT765JQP35B25G=notas-importantes empty-collections=eliminar-colecciones-vac%C3%ADas h_01JQ69A1511N1GQFMBA2S748JK=eliminar-colecciones-vac%C3%ADas general-information=informaci%C3%B3n-general h_01HKWSS512JYNT3386P1KPZ452=informaci%C3%B3n-general h_01HKWSS5123XVFKBZ892YCTFAC=nota-1 h_01HKWSS5126A9XVE645CHCJD7X=upload-format h_01HKWSS512P7ZB213PCZ7JQTYP=parameters-in-the-uploaded-csv faq=preguntas-frecuentes h_01K42S97K7KSKFC6BYEHPT0GZ5=preguntas-frecuentes qr-with-long-links-vs-short-links-%E2%80%93-is-there-any-difference=qr-with-long-links-vs-short-links---is-there-any-difference h_01K42Q4QQVKGQZKAS1PZ3B9H20=qr-with-long-links-vs-short-links---is-there-any-difference h_01K42Q4QQVTV0KP280D15JF7NB=can-you-create-a-qr-code-and-change-the-behavior-behind-it-retroactively-after-printing-the-qr-for-example h_01K42Q4QQVV1RZZXZK2Y9W8R58=what-options-are-available-for-generating-qr-codes-in-appsflyer h_01K42Q4QQVZF4H8FYZCTJPR0RX=can-you-bulk-create-qr-codes" />
