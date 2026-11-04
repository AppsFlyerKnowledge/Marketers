---
title: Audiencias - Importar segmentos de audiencia desde sistemas internos
metadata:
  keywords:
    - Developers
    - Premium
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2020-09-15T10:45:43Z'
  edited_at: '2026-10-07T00:17:47Z'
  id: 360013291857
  locale: es
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/es/articles/360013291857
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> En resumen: Importe segmentos de audiencia predefinidos desde sus sistemas internos (como BI y CRM) a AppsFlyer Audiences, lo que le permite utilizar Audiences para conectar y mantener estos segmentos con sus socios publicitarios.

<div id="why-import-audiences" />

## ¿Por qué importar audiencias?

En ciertas ocasiones, puede que ya tenga segmentos de audiencia predefinidos en sus sistemas internos. Importar estas audiencias (como listas de identificadores de dispositivos y/o usuarios) a AppsFlyer le permite usar Audiences como el punto central para conectar y mantener todos sus segmentos de audiencia con sus socios publicitarios. Además, le ofrece la posibilidad de sacar el máximo partido de otras funciones de Audiences, como la coincidencia de identificadores, el enriquecimiento de datos y las métricas de campañas conectadas.

Considere los siguientes ejemplos:

<div id="examples" />

> 📄 **Ejemplos**
>
> Remarketing promocional
> Desea dirigir ofertas promocionales a los usuarios durante el mes de sus cumpleaños.
>
> A continuación le explicamos cómo hacerlo con Audiences:
>
> 1. Utilice su CRM interno para generar una lista de usuarios con sus fechas de cumpleaños.
> 2. Organice la lista según el mes de cumpleaños y expórtela como listas individuales de identificaciones de publicidad.
> 3. Importe las listas a AppsFlyer como audiencias y conéctelas con los socios con los que desea ejecutar campañas promocionales.
> 4. Configure campañas con los socios pertinentes para dirigirse a las audiencias adecuadamente.
>
> Adquisición de usuarios adicionales
> Su estudio de desarrollo de aplicaciones adquiere otro estudio. El estudio adquirido cuenta con los ID de dispositivos de los usuarios que instalaron previamente sus aplicaciones, y desea enfocar estos usuarios para que instalen sus aplicaciones existentes.
>
> A continuación le explicamos cómo hacerlo con Audiences:
>
> 1. Obtenga la lista de ID de dispositivos del estudio adquirido e impórtela a AppsFlyer como una audiencia.
> 2. Conecte la audiencia con los socios con los que desea ejecutar campañas.
> 3. Configure campañas con los socios pertinentes para llegar a estos usuarios adecuadamente.

<div id="audiences-import-v20" />

## Importación de audiencias V2.0

Este artículo describe los conceptos y procedimientos relacionados con la nueva función de importación de Audiencias V2.0 (con opciones para importar mediante CSV y API).

<div id="imported-audience-types" />

## Tipos de audiencias importadas

Al importar una audiencia, se le asigna uno de dos tipos, lo que determina cómo AppsFlyer la trata, tanto en el procesamiento como en la carga a los socios. **La asignación se realiza al importar una audiencia por primera vez y no se puede cambiar después.**

**Una audiencia estándar importada:**

* Se somete a una comparación de identificadores y enriquecimiento de datos: un proceso en el que Audiences empareja los identificadores importados con los existentes en la base de datos de Audiences (para el mismo usuario en la misma aplicación) con el objetivo de enriquecer los datos de audiencia cargados a los socios.
* Se carga a los socios de acuerdo con la política de identificadores de usuario de su cuenta.
* Debe importarse utilizando la función de importación V2.0 que se describe en este artículo.

**Una audiencia "tal cual" importada:**

* No se somete a comparación de identificadores ni a enriquecimiento de datos.
* Se carga a socios sin tener en cuenta la política de identificadores de usuario de su cuenta (es decir, todos los identificadores importados se cargan a los socios).
* Se puede importar utilizando la función de importación V2.0 (descrita en este artículo).

<div id="important" />

> 🚧 **¡Importante!**
>
> * Todas las audiencias existentes a partir del 23 de noviembre de 2021 **se designan como audiencias tal como están y no se pueden cambiar a audiencias estándar.** Puede seguir actualizando estas audiencias según sea necesario utilizando la función de importación V2.0 (descrita en este artículo).
> * Puedes tener hasta 500 audiencias importadas activas al mismo tiempo.
> * Solo un administrador puede designar una nueva audiencia importada como una audiencia tal como está.
> * Al importar una audiencia con CUID como identificador, AppsFlyer debe haber recibido la asociación de CUID en el momento de la instalación (no solo en eventos post-instalación) para garantizar una asociación completa con los dispositivos relevantes y un enriquecimiento exitoso con identificadores de dispositivos (es decir, GAID, IDFA). <Anchor target="_blank" href="/marketers/es/docs/customer-user-id-field-cuid#configuración-del-cuid">Más información</Anchor>

<div id="audience-import-procedures" />

## Procedimientos de importación de audiencias

Importa una audiencia cargando un archivo CSV o utilizando la API de importación de audiencias.

<div id="import-a-csv-file" />

<Accordion title="Importar un archivo CSV">

Prepara un archivo CSV con las siguientes especificaciones:

**Formato**

* Una columna para cada identificador de usuario que se suba
* Una fila de encabezado con el nombre del identificador en cada columna (todo en minúsculas)
* Sin filas en blanco
* Número máximo de filas: 1 millones
* Si preparas el archivo con Excel, guárdalo como un archivo **CSV (delimitado por comas) (\*.csv)**, como se muestra en la siguiente imagen:

<Image alt="CSV.jpg" src="https://files.readme.io/863505596fd525ff0750f05db70413e9aaee51beb208bd0fbc8ab718ad4e4576-32897281151633.jpg" width="339px" />

<div id="identifier-hash" />

#### hash del identificador

<div id="note" />

> 📘 **Nota:**
>
> Este formato CSV sirve para importar segmentos de audiencia. Si en su lugar importas datos de atributos de usuario, consulta <Anchor target="_blank" href="/marketers/es/docs/audiences-create-better-audiences-with-user-attribute-data">Crear mejores audiencias con datos de atributos de usuario</Anchor>, que utiliza un formato CSV distinto sin fila de encabezado.

**Columnas e identificadores**

* Los datos se procesan usando la fila de encabezado para identificar los datos en cada columna, por lo siguiente:
  * No es necesario que las columnas aparezcan en un orden específico.
  * No es obligatorio incluir columnas para identificadores que no se estén subiendo.
  * Puedes importar tantos identificadores como desees en un único archivo CSV siempre que cada fila incluya los identificadores requeridos, como se detalla a continuación.
* Identificadores disponibles:
  * id\_aplicación
  * idfv
  * idfa
  * gaid
  * oaid
  * imei
  * cuid
  * correos electrónicos
  * teléfono
  * teléfono\_e164
  * braze\_id
  * amplitude\_id  

    **Nota:** Los identificadores adicionales, como los correos electrónicos y los números de teléfono, deben estar en formato sha256 cifrado o dejarse en blanco.
* Identificadores requeridos:
  * Para audiencias de Android: **app\_id** + uno de los siguientes: **gaid** O **oaid** O **imei** O **cuid** O **braze\_id** O **amplitude\_id**
  * Para audiencias de iOS: **app\_id** + uno de los siguientes: **idfv** O **cuid** O **braze\_id** O **amplitude\_id**
* De acuerdo con la aplicación del <Anchor target="_blank" href="/marketers/es/docs/audiences-user-identifier-policy#eu-digital-markets-act">Digital Markets Act (DMA)</Anchor> por Google el 6 de marzo de 2024, al importar una audiencia tal cual, será necesario agregar dos columnas adicionales de consentimiento de AppsFlyer. Estas son:

| Columnas de consentimiento de AppsFlyer | Campo de Google | Valores | Campo explicado |
| --- | --- | --- | --- |
| <span id="ad_personalization"></span>personalización de anuncios habilitada | personalización de anuncios | verdadero/falso | ¿El usuario ha dado su consentimiento a Google para usar sus datos con fines de personalización de anuncios? |
| <span id="ad_user_data"></span>datos de usuario de anuncios habilitados | datos\_de\_usuario\_anuncio | verdadero/falso | ¿El usuario ha dado su consentimiento para enviar sus datos de usuario a Google? |

Si los campos de consentimiento no se completan con valores, se enviarán a Google como 'No especificado', y es probable que no se incluyan en la audiencia de Google. Rellenar estos campos garantiza la máxima inclusión de usuarios del <Anchor target="_blank" href="https://ec.europa.eu/eurostat/statistics-explained/index.php?title=Glossary:European_Economic_Area_(EEA)">Espacio Económico Europeo (EEE)</Anchor> en tus audiencias de Google.

**Archivos CSV de ejemplo:**

<Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/4413851475729">nuevo-ejemplo-importación-android.csv</Anchor>  
<Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/4413840980497">nuevo-ejemplo-importación-ios.csv</Anchor>

<span id="01ECF4ZD0RB90HZC6ZFNTKMDSG"></span>**Para crear e importar una nueva audiencia usando un archivo CSV:**

1. En el panel izquierdo de AppsFlyer, dirígete a **Interactuar** > **Audiencias**.
2. Haz clic en **Nueva audiencia**.
3. Selecciona **Importar audiencia**.  
   Se abrirá la ventana **Importar audiencia**.
4. Introduce un **nombre de audiencia** único. **Nota:** Los nombres de la audiencia no pueden incluir caracteres especiales (" ’ # % & * + / : ; `< = >` ? ( ) [ ] `{ }` \ | ~)
5. Elige la plataforma de audiencia: **Android** o **iOS.**
6. Indica si esta audiencia es una audiencia [**estándar** o **tal cual**](/docs/audiences-import-audience-segments-from-internal-systems#tipos-de-audiencias-importadas).
7. Para una audiencia estándar, deja la casilla sin marcar.
8. Para una audiencia tal cual, marca la casilla. (**Nota:** (Esta opción está disponible solo para administradores).
9. Haz clic en **Siguiente**.  
   **Se muestra la pestaña Conectar.**
10. En la sección **Importar usando CSV**, mantén configurado por defecto **Agregar nuevos dispositivos/usuarios** (ya que se trata de una nueva audiencia).
11. Selecciona el archivo CSV que deseas cargar.  
    Espera el mensaje de confirmación **Cargado exitosamente.**
12. Haz clic en **Siguiente**.  
    **Se muestra la pestaña Conectar.**
13. **(Opcional)** Sigue las instrucciones para <Anchor target="_blank" href="/marketers/es/docs/audiences-guide#connect-an-audience-to-media-partners">conectar una audiencia con socios</Anchor>.
14. Haz clic en **Listo.**

Tu audiencia ahora es visible en el panel de Audiencias y se ha importado y conectado con los socios. Sin embargo, ten en cuenta que la lista de audiencia recién importada aún no está disponible para cargarla a los socios, ya que las audiencias importadas se procesan con una <Anchor target="_blank" href="/marketers/es/docs/about-data-freshness-and-timezone-support#eod">frescura de datos diaria</Anchor>.

**Para actualizar una audiencia existente usando un archivo CSV:**

1. En el panel izquierdo de AppsFlyer, dirígete a **Interactuar** > **Audiencias**.
2. Haz clic en el nombre de la audiencia que deseas actualizar.  
   Se abrirá la pantalla **Editar audiencia**, mostrando la pestaña **Definir**.
3. Si deseas editar el nombre de la audiencia, puedes hacerlo aquí. Si no, selecciona la pestaña **Importar** para cargar el nuevo archivo CSV.
4. En la sección **Importar usando CSV**, elige qué hacer con la lista cargada:
5. **Agregar nuevos dispositivos/usuarios:** Añadir identificadores de dispositivo/usuario a la audiencia existente
6. **Eliminar dispositivos/usuarios de la audiencia existente:** Eliminar identificadores de dispositivo/usuario en la lista cargada de la audiencia
7. **Sobrescribir la audiencia existente con nuevos dispositivos/usuarios:** Reemplazar toda la audiencia con la lista cargada
8. Selecciona el archivo CSV que deseas cargar.  
   Espera el mensaje de confirmación **Cargado exitosamente.**
9. Haz clic en **Siguiente**.  
   **Se muestra la pestaña Conectar.**
10. Realiza cambios en las <Anchor target="_blank" href="/marketers/es/docs/audiences-guide#connect-an-audience-to-media-partners">conexiones de socios</Anchor> para esta audiencia si es necesario.
11. Haz clic en **Listo.**

Tu audiencia se ha actualizado usando el archivo CSV. Sin embargo, tenga en cuenta que la lista de audiencia revisada aún no se ha cargado para los socios, ya que las audiencias importadas se procesan con una <Anchor target="_blank" href="/marketers/es/docs/about-data-freshness-and-timezone-support#eod">actualización diaria de datos</Anchor>.

<div id="error-messages" />

### Mensajes de error

| Mensaje | Causa | Qué hacer |
| --- | --- | --- |
| Hay un problema con la lista de dispositivos. | Hay uno o varios problemas con la lista de dispositivos. | Por favor, verifique que el archivo CSV:<ul><li>esté lleno de dispositivos e identificadores GAID/IDFA en el formato correcto</li><li>contenga los identificadores requeridos</li><li>contenga una fila de encabezado con los encabezados en el formato correcto</li><li>no tenga filas vacías</li><li>app\_id esté lleno con la aplicación correcta que utiliza para las audiencias</li></ul> |
| Parece que tu lista de dispositivos está vacía. Añade algunos identificadores de dispositivos e inténtalo de nuevo. | El archivo CSV está vacío | Asegúrate de que el CSV contenga al menos un ID de dispositivo. |
| No hemos podido entender uno o más de tus ID de dispositivos. | <ul><li>El formato del CSV es incorrecto</li><li>El archivo que has subido no es un archivo CSV</li><li>El archivo CSV fue editado y guardado por un programa que no es un editor de CSV válido (como Microsoft Excel). Microsoft Excel)</li><li>Uno o más ID de dispositivos tienen un formato incorrecto.</li></ul> | <ul><li>Asegúrate de que el CSV esté en el formato requerido.</li><li>Asegúrate de que todos los ID de dispositivos estén en el formato correcto.</li><li>Si usaste Excel, guarda el archivo como un archivo CSV, tal como se describe anteriormente.</li></ul> |
| No se puede utilizar la importación v1 mientras se aplica la política de cuenta de usuario en la audiencia. | Has cargado un archivo CSV para una [audiencia estándar](/docs/audiences-import-audience-segments-from-internal-systems#tipos-de-audiencias-importadas) utilizando la estructura de importación V1.0. Las audiencias estándar deben cargarse utilizando un CSV en la estructura V2.0. | Edita el archivo CSV que estás cargando para que use el formato, las columnas y los identificadores descritos anteriormente. |
| Tuvimos un problema de conexión temporal y no pudimos cargar tu archivo. Puedes intentarlo de nuevo ahora. | Posible error de red | Intenta cargar el archivo CSV nuevamente. |

</Accordion>

<div id="use-the-import-audience-api" />

<Accordion title="Utiliza la API de Importación de Audiencia">

La API de Importación de Audiencia se usa para agregar o eliminar dispositivos de una audiencia.

**Para importar una nueva audiencia utilizando la API:**

1. En el panel izquierdo de AppsFlyer, dirígete a **Interactuar** > **Audiencias**.
2. Haz clic en **Nueva audiencia.**
3. Selecciona **Importar audiencia**.  
   Se abrirá la ventana **Importar audiencia**.
4. Introduce un **nombre de audiencia** único.  
   **Nota:** Los nombres de la audiencia no pueden incluir caracteres especiales (" ’ # % & * + / : ; `< = >` ? ( ) [ ] `{ }` \ | ~)
5. Elige la plataforma de audiencia: **Android** o **iOS.**
6. Indica si esta audiencia es una audiencia [**estándar** o **tal cual**](/docs/audiences-import-audience-segments-from-internal-systems#tipos-de-audiencias-importadas).
   * Para una **audiencia estándar**, deja la casilla sin marcar.
   * Para una **audiencia tal como está**, marca la casilla (ten en cuenta que esta opción solo está disponible para administradores). <Anchor target="_blank" href="/marketers/es/docs/audiences-user-identifier-policy#importación-de-audiencias">Se requieren dos campos de consentimiento adicionales</Anchor> al importar una audiencia 'tal cual' según la normativa de la Ley de Mercados Digitales (DMA) impuesta por Google el 6 de marzo de 2024. Al completar estos campos, se garantiza la máxima inclusión de usuarios del <Anchor target="_blank" href="https://ec.europa.eu/eurostat/statistics-explained/index.php?title=Glossary:European_Economic_Area_(EEA)">Espacio Económico Europeo (EEE)</Anchor> en tus audiencias de Google.
7. Haz clic en **Guardar**.  
   Se muestra la página de Importación.
8. En la sección **Importar utilizando la API**, mantén el valor predeterminado de **Añadir nuevos dispositivos/usuarios** (ya que se trata de una nueva audiencia).
9. Copia la URL de solicitud de API de la página <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/audience-import-post">Importar una nueva API de Audiencia</Anchor> (el token de API ya está incluido).
10. Luego copia y pega el cuerpo de la solicitud de API.
11. Haz clic en **Listo**.  
    **Se muestra la pestaña Conectar.**
12. **(Opcional)** Sigue las instrucciones para <Anchor target="_blank" href="/marketers/es/docs/audiences-guide#connect-an-audience-to-media-partners">conectar una audiencia con socios</Anchor>.
13. Haz clic en **Listo.**
14. Prepara la solicitud de API, incluyendo los identificadores de usuario/dispositivo, y envíala a AppsFlyer.

**Para actualizar una audiencia existente mediante la API:**

1. En el panel izquierdo de AppsFlyer, dirígete a **Interactuar** > **Audiencias**.
2. Haz clic en el nombre de la audiencia que deseas actualizar.  
   Se abrirá la pantalla **Editar audiencia**, mostrando la pestaña **Definir**.
3. Si deseas editar el nombre de la audiencia, puedes hacerlo aquí. Si no, selecciona la pestaña **Importar**.
4. En la sección **Importar mediante la API**, elige qué hacer con la lista cargada:
5. Agregar nuevos dispositivos/usuarios: Agrega identificadores de dispositivo/usuario a la audiencia existente.
6. **Eliminar dispositivos/usuarios de la audiencia existente:** Elimina identificadores de dispositivo/usuario de la audiencia existente.
7. Copia la **URL de solicitud de API** de la página <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/audience-import-post">Importar una nueva API de Audiencia</Anchor> (el token de API ya está incluido). **Nota:** Al cambiar esta opción se modifica la ruta del endpoint en el código que se va a copiar. Asegúrate de usar el endpoint correcto para la acción que estás realizando (en esta y futuras solicitudes de API).
8. Luego copia el **cuerpo de la solicitud de API.**
9. **Se muestra la pestaña Importar.**
10. Realiza cambios en las <Anchor target="_blank" href="/marketers/es/docs/audiences-guide#connect-an-audience-to-media-partners">conexiones de socios</Anchor> para esta audiencia si es necesario.
11. Haz clic en **Listo.**
12. Prepara la solicitud de API, incluyendo los identificadores de usuario/dispositivo, y envíala a AppsFlyer.

**Nota:** Al importar mediante la API, la audiencia tardará 24 horas en actualizarse.

<div id="response-codes" />

### Códigos de respuesta

| Código | Mensaje | Descripción |
| --- | --- | --- |
| 200 | La solicitud fue exitosa | Audiencia importada con éxito |
| 400 | Plataforma de audiencia no válida, esta audiencia ya está configurada para Android/iOS. Para usar una plataforma diferente, crea una nueva audiencia en la interfaz de usuario. | La plataforma especificada en el cuerpo de la solicitud no coincide con la plataforma especificada al crear la audiencia |
| 400 | X o más de tus filas no contienen un ID de aplicación. Debes adjuntar un ID de aplicación a cada fila. | Es necesario que cada fila contenga un **app\_id**<ul><li>**Nota:** no es necesario el app\_id para una [audiencia tal cual](/docs/audiences-import-audience-segments-from-internal-systems#tipos-de-audiencias-importadas) que se importa utilizando la función de importación heredada V1.0.</li></ul> |
| 400 | X o más de tus filas no contienen un identificador único válido | Al menos una o algunas filas no contienen alguno de los siguientes identificadores en un formato válido:<ul><li>Para audiencias de Android: **gaid** O **oiad** O **imei** O **cuid** O **braze\_id** O **amplitude\_id**</li><li>Para audiencias de iOS: **idfv** O **cuid** O **braze\_id** O **amplitude\_id**</li></ul> |
| 400 | No se pueden procesar más de Y dispositivos por solicitud (se han contado n dispositivos en esta solicitud) | El cuerpo de la solicitud incluye una lista con más de 10.000 ID de dispositivos. |
| 400 | La lista de dispositivos no puede estar vacía | El cuerpo de la solicitud contiene una lista vacía de dispositivos.<br /><br />Debe proporcionar al menos un ID de dispositivo por cada solicitud |
| 400 | No pudimos interpretar uno o más de los identificadores de sus dispositivos | Algunos o todos los ID de dispositivos no tienen un formato válido |
| 400 | X o más de los dispositivos a eliminar contienen más de un identificador por dispositivo | La solicitud de eliminación fue enviada con más de un identificador por dispositivo |
| 403 | Prohibido | Solicitud no autorizada: Clave de importación incorrecta o faltante |
| 429 | Demasiadas solicitudes | Las solicitudes están limitadas a 350 por minuto |
| 500 | No se pudo procesar la solicitud | El formato del cuerpo de la solicitud no es válido (no es la estructura JSON esperada o no es un JSON)<br /><br />Consulte la solicitud de ejemplo anterior |

**Limitaciones de la API**

* Solo se pueden agregar dispositivos a una audiencia por solicitud.
* Solo se pueden eliminar dispositivos de una audiencia por solicitud.
* Puedes enviar hasta 10.000 IDs de dispositivo por solicitud.
* Se pueden enviar hasta 350 solicitudes por minuto.

</Accordion>

<div id="imported-audience-management-api" />

<Accordion title="API de gestión de audiencias importadas">

La <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-2">API de gestión de audiencias importadas</Anchor> permite a los anunciantes crear y configurar audiencias importadas, conectarlas con socios, subirlas a los socios, entre otras funciones.

</Accordion>

<div data-zendesk-anchors="why-import-audiences=por-qu%C3%A9-importar-audiencias h_01HA4M61P4H5AVXQFA5ETABA67=por-qu%C3%A9-importar-audiencias 01ECF4ZD0QQ5JJNH624D0E9WRF=ejemplos audiences-import-v20=importaci%C3%B3n-de-audiencias-v20 h_01HA4M61P41RSJMKSJ2V9WJH8W=importaci%C3%B3n-de-audiencias-v20 imported-audience-types=tipos-de-audiencias-importadas h_01HA4M61P4TEBNF264RNFC57YP=tipos-de-audiencias-importadas h_01HA4M61P4NVDJ393HA4V75PQV=importante audience-import-procedures=procedimientos-de-importaci%C3%B3n-de-audiencias h_01HA4M61P4EEYGJNZ3N2D0KXS5=procedimientos-de-importaci%C3%B3n-de-audiencias 01ECF4ZD0RHJAQ31NKFCX8QEWW=import-a-csv-file identifier-hash=hash-del-identificador h_01HA4M61P4BJZKN97ZTT8TKRBK=hash-del-identificador h_01M45CYAAKF4MV0S3Z89NW6PQS=nota confirmation-messages=mensajes-de-error h_01HA4M61P57TMZRK4XX7ARK896=mensajes-de-error h_01HA4M61P5XZR7C20Y5D3XX4K9=use-the-import-audience-api response-codes=c%C3%B3digos-de-respuesta h_01HA4M61P5YGX4QP2PDSVW7D3G=c%C3%B3digos-de-respuesta h_01HA4M61P6CE4RBCVTA3KE15VN=imported-audience-management-api" />
