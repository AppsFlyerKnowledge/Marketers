---
title: Cambia de Adjust a AppsFlyer
metadata:
  keywords:
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2024-12-02T10:01:48Z'
  edited_at: '2026-08-12T12:05:27Z'
  id: 30563700129297
  locale: es
  section: Marketer onboarding
  section_id: 6550866490129
  url: https://support.appsflyer.com/hc/es/articles/30563700129297
---
> **En resumen:** Planifica tu migración de Adjust a AppsFlyer. Descubre cómo evitar cobros dobles, duplicación de datos y pérdida de datos durante el período de migración.

<Image alt="" src="https://files.readme.io/cc012894dd05255c0b7fa448b1c95d925d556ddb43dc461086bb71e9279da90d-30633481029137.png" width="1765px" />

<div id="about-migrating-to-appsflyer" />

## Sobre la migración a AppsFlyer

La migración de Adjust a AppsFlyer proporciona una transición fluida a una plataforma confiable y completa para la atribución y el análisis de marketing. AppsFlyer ofrece soluciones seguras e imparciales junto con un conjunto de herramientas avanzadas diseñadas para ayudar a las marcas a afrontar los cambios en la industria. Con una atención al cliente global y un enfoque en la mejora continua de los productos, AppsFlyer tiene como objetivo equipar a las empresas con las herramientas y los insights necesarios para crecer y adaptarse.

<div id="compare-measurement-between-appsflyer-and-adjust" />

#### Compara las mediciones entre AppsFlyer y Adjust

Al considerar la migración, es posible que desees comparar las medidas de atribución de AppsFlyer y Adjust en las mismas campañas y fuentes de medios. Sin embargo, no todas las fuentes de medios admiten la medición con más de un MMP. Aquellos que sí lo hagan pueden tener ciertas limitaciones y desafíos para evitar discrepancias en la atribución. Saber más sobre la <Anchor target="_blank" href="/marketers/es/docs/measuring-attribution-with-multiple-mmps">medición de la atribución con varios MMPs</Anchor>.

<div id="tasks" />

## Tareas

[![](https://files.readme.io/7deffffc032dce24c30b5b73ae09c083a227ac6f4ec13be224bb7f7fb5b7042f-30642410251793.png)](https://files.readme.io/7deffffc032dce24c30b5b73ae09c083a227ac6f4ec13be224bb7f7fb5b7042f-30642410251793.png) En la tabla siguiente se describen los pasos principales necesarios para la migración. Para ver un desglose preciso de las tareas generales, así como para registrar tu progreso, descarga <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQqbJIkE7kD87uSm7MH7zfkPN1VLuBaeotTEHAID2pYFVWM_LuQIA2AE2-8fVnXH-DrbXUQCs2iaiDe/pub?output=xlsx">esta hoja de cálculo</Anchor>.

Puedes trabajar en estas tareas simultáneamente, lo que significa que los marketers, desarrolladores e ingenieros de datos pueden, en su mayor parte, trabajar en las tareas asignadas de forma simultánea. Te recomendamos:

* Completar todas las tareas antes de lanzar tu aplicación actualizada con el SDK de AppsFlyer.
* Detener las campañas de marketing existentes antes de realizar la migración del ID de dispositivo.

<table><thead><tr><th>Paso</th><th>¿Quién participa?</th><th>Tiempo estimado</th><th>Observaciones</th></tr></thead><tbody><tr><td>1. Crear una cuenta AppsFlyer</td><td>Usuario del dashboard de AppsFlyer/Marketer</td><td>2 horas</td><td> </td></tr><tr><td>2. Agrega la aplicación en AppsFlyer</td><td>Usuario del dashboard de AppsFlyer/Marketer</td><td>2 horas</td><td> </td></tr><tr><td>3. Integrar el SDK</td><td>Desarrolladores de aplicaciones</td><td>1 día + 1 semana de pruebas e iteraciones</td><td><ul><li> <strong>Recomendado</strong>: Integra el SDK de AppsFlyer en una aplicación de preproducción para realizar pruebas.</li><li>La aplicación de producción debe actualizarse en las tiendas de aplicaciones después de que se completen todas las demás tareas.</li></ul></td></tr><tr><td>4. Migrar dispositivos (opcional)</td><td>Ingeniero de datos</td><td>1-2 semanas</td><td rowspan="2"><ul><li>Considera pausar las campañas existentes antes de la migración y reanudarlas después de actualizar la versión de la aplicación. </li><li>Considera repetir la migración de dispositivos en la fecha final de migración para garantizar una cobertura completa. </li></ul></td></tr><tr><td>5. Migrar campañas</td><td>Gerente de UA/marketer</td><td>De 1 a 3 días para cada fuente de medios</td></tr><tr><td>6. Configurar la generación de reportes de datos</td><td>Ingeniero de datos</td><td>3-6 semanas</td><td> </td></tr></tbody></table>

<div id="step-1-create-an-appsflyer-account" />

<Accordion title="1. Crear una cuenta AppsFlyer">

**Para crear una cuenta de AppsFlyer**:

1. Crea una cuenta de AppsFlyer
2. Agrega usuarios a la cuenta con los permisos adecuados

</Accordion>

<div id="step-2-add-your-app" />

<Accordion title="2. Agregación de la aplicación">

**Para añadir tu aplicación en AppsFlyer**:

1. <Anchor target="_blank" href="/marketers/es/docs/adding-an-app-to-appsflyer">Agrega la aplicación</Anchor> en AppsFlyer.
2. [Opcional] Cambia la <Anchor target="_blank" href="/marketers/es/docs/set-up-re-attribution-window">ventana de reatribución</Anchor> predeterminada de 90 días para alinearla con tu definición de usuarios activos.
3. Como parte del asistente de onboarding de aplicaciones en AppsFlyer, prepara y envía un correo electrónico a tu desarrollador con instrucciones y tareas para la integración del SDK y el mapeo de eventos in-app.

</Accordion>

<div id="step-3-integrate-the-sdk" />

<Accordion title="3. Integrar el SDK">

El SDK de AppsFlyer integrado en la aplicación es el enlace entre la aplicación y la plataforma de AppsFlyer. Reporta las instalaciones de aplicaciones, aperturas de aplicaciones, eventos in-app, etc.

**Para integrar el SDK de AppsFlyer**:

1. Recibe el correo electrónico del marketer con instrucciones y tareas para la integración del SDK y el mapeo de eventos in-app.
2. Sigue las instrucciones de ese correo electrónico y usa el <Anchor target="_blank" href="https://dj.dev.appsflyer.com/?sourceos=android&utm_source=kb&utm_medium=sdk-int-wizard-orvw">asistente de integración del SDK de AppsFlyer</Anchor> para integrar el SDK de AppsFlyer en la aplicación.
   * El asistente lleva al desarrollador desde la instalación hasta la prueba satisfactoria de la integración. También ayuda al desarrollador a definir los eventos in-app y a probar con éxito su transmisión a AppsFlyer. <Anchor target="_blank" href="/marketers/es/docs/for-ios-and-android-the-sdk-integration-wizard">Saber más sobre el asistente de integración del SDK</Anchor>
   * Consulta guías adicionales para desarrolladores sobre la integración de los SDK de <Anchor target="_blank" href="/marketers/es/docs/sdk-integration-overview">Android</Anchor> e <Anchor target="_blank" href="/marketers/es/docs/sdk-integration-overview">iOS</Anchor>.
   * Asigna los eventos in-app que deseas registrar, utilizando los esquemas de AppsFlyer.  
     Esto se puede hacer a través de <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview">SDK</Anchor> o de <Anchor target="_blank" href="/marketers/es/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor>.
3. Elimina el SDK de Adjust.  
   Puedes hacerlo de inmediato y cambiar exclusivamente a AppsFlyer, o ejecutar ambos SDKs simultáneamente durante un tiempo. Observa un desglose de estas opciones en la tabla que figura a continuación.

| Opción | Qué pasa después del  <br />lanzamiento de la versión actualizada de la aplicación | Impacto |
| --- | --- | --- |
| Eliminar el SDK de Adjust (recomendado) | Solo AppsFlyer registra las nuevas instalaciones y actualizaciones de los usuarios.  <br />Adjust sigue mostrando los eventos realizados por los usuarios, hasta que los usuarios también actualicen su aplicación. | <ul><li>Transición rápida.</li><li>Sin atribución doble.</li></ul> |
| Conserva el SDK de Adjust durante el período de transición | AppsFlyer y Adjust atribuyen nuevas instalaciones y reportan eventos. Más adelante, elimina el SDK de Adjust. | <ul><li>La validación de datos es posible. Es decir, puedes comparar los datos de AppsFlyer y Adjust.</li><li>Doble atribución, lo cual puede provocar un cobro doble de las ad networks. Ver ejemplo a continuación.</li><li>Carga de trabajo más alta.</li></ul> |

4. Cuando se hayan completado todas las demás tareas de este artículo sobre migración, lanza al mercado la versión de la aplicación con el SDK de AppsFlyer. AppsFlyer atribuye a los usuarios nuevos.   
   **Nota**:
   * Asegúrate de actualizar la aplicación para iOS, Google Play y cualquier mercado fuera de la tienda de Android relevante.
   * Es posible que tu aplicación Android exista en sitios APK no oficiales, aunque no la conozcas (busca en internet el nombre del paquete de tu aplicación para averiguarlo). Los sitios APK tardan un tiempo en actualizarse a la última versión, por lo que pueden traer usuarios orgánicos, que instalan versiones anteriores sin el SDK de AppsFlyer.
   * Las implementaciones de actualizaciones de la aplicación en las tiendas de aplicaciones pueden tardar hasta un par de días en completarse. Es posible que los usuarios que realizaron la instalación durante esta fase obtengan la versión anterior.

</Accordion>

<div id="step-4-migrate-devices-optional" />

<Accordion title="4. Migrar dispositivos — opcional">

La migración de dispositivos es el proceso de subir una lista de tus ID de dispositivos de usuario existentes (IDFA, IDFV, GAID) a AppsFlyer. (Si no tienes todos los ID de dispositivo necesarios, puedes ponerte en contacto con tu CSM para que te ayude a guiarte en el proceso de migración mediante CUID). Debes realizar este proceso antes de lanzar la nueva versión de la aplicación, que incluirá el SDK de AppsFlyer. Hay dos opciones a la hora de migrar dispositivos: migración [atribuida](/docs/migrate-from-adjust-to-appsflyer#attributed-migration) o [no atribuida](/docs/migrate-from-adjust-to-appsflyer#nonattributed-migration).

La migración de dispositivos resuelve los problemas de datos asociados con los usuarios existentes de la aplicación que descargaron la aplicación y que Adjust les atribuyó. Por ejemplo, los cargos dobles de SRN, que se producen cuando los usuarios que originalmente se atribuyeron a un SRN en Adjust y que aún están dentro del período de lookback, vuelven a ser reclamados por el SRN en AppsFlyer.

<div id="example" />

> 📄 **Ejemplo**
>
> * Un usuario nuevo hace clic en un anuncio en la aplicación de Facebook e instala tu aplicación el 15 de junio.
> * El 24 de junio, el usuario actualiza la aplicación a la versión con el SDK de AppsFlyer y la inicia. Para AppsFlyer, este es un usuario nuevo, que debe atribuirse en tiempo real.
> * AppsFlyer consulta Meta Ads sobre el ID de dispositivo del usuario. Dado que el usuario aún se encuentra dentro de la ventana retrospectiva de 28 días de Meta Ads, Meta Ads se autoatribuye al usuario. Esto provoca un cobro doble al propietario de la aplicación por el mismo usuario.

Una vez que migras los dispositivos, los datos se reflejan en AppsFlyer de la siguiente manera:

* **Datos de** **instalación**: Al igual que en las <Anchor target="_blank" href="/marketers/es/docs/set-up-re-attribution-window#reinstall">reinstalaciones</Anchor>, los dispositivos migrados no tienen datos de instalación. Las instalaciones de los dispositivos migrados no se muestran en AppsFlyer.
* **Datos de sesiones y eventos integrados in-app:** Se graba y se muestra como orgánico para el [método de migración de dispositivos sin atribución](/docs/migrate-from-adjust-to-appsflyer#nonattributed-migration), o se atribuye a la fuente de medios y a la campaña, si se utiliza el [método atribuido](/docs/migrate-from-adjust-to-appsflyer#attributed-migration).
* **Redireccionamiento:** Las reatribuciones y re-engagements se muestran con normalidad.
* **Datos de actividad:** Se muestra con normalidad.
* **Datos de retención y cohorte:** Los dispositivos migrados no tienen ningún registro de instalación. Por lo tanto, no están asociados a ninguna cohorte y no se pueden mostrar en los reportes de cohorte ni de retención.

<div id="note" />

> 📘 **Nota**
>
> Si la aplicación no se abre en un plazo de 180 días a partir de la fecha de migración, se eliminan todos los datos del dispositivo migrado. Por lo tanto, si la aplicación se abre después del período de 180 días, se registrará una nueva instalación.

**Para migrar dispositivos:**

1. Decide qué usuarios deseas migrar. Puedes migrar a todos los usuarios existentes (lo que puede impedir que obtengas datos de reatribución precisos de AppsFlyer) o a los usuarios que instalaron tu aplicación recientemente (lo que puede hacer que se les cobre el doble a los usuarios algo más antiguos).  
   **Recomendamos migrar a los usuarios que estén activos durante el período de reatribución actual.** Por ejemplo, si tu aplicación tiene un período de reatribución de 90 días, migra a los usuarios que hayan tenido al menos una sesión durante los 90 días anteriores.
2. [Opcional] Pídele al marketer/gerente de UA que pause las campañas de marketing existentes (de SRNs, ad networks no SRNs, medios propios, etc.) hasta que se complete la migración del dispositivo.  
   Si decides no pausar las campañas, migra los ID de dispositivo restantes del otro proveedor tan pronto como se publique en las tiendas de aplicaciones la versión actualizada de la aplicación con el SDK de AppsFlyer.
3. Prepara un archivo CSV basado en la población de usuarios seleccionada, utilizando la estructura de migración [atribuida](/docs/migrate-from-adjust-to-appsflyer#attributed-migration) o [no atribuida](/docs/migrate-from-adjust-to-appsflyer#nonattributed-migration). <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQPvcJ3zXjsB5Zrn8vqD_-QXFPjguDU9Y8_LfK6-2eOgdlDltmFdGoM-94Ouw-D327oMp9p0ZbFFawF/pub?output=csv">Ver ejemplo de CSV</Anchor>
4. Envía el CSV a tu CSM de AppsFlyer.  
   Tu CSM migrará los IDs de los dispositivos a AppsFlyer.

</Accordion>

<div id="step-5-migrate-campaigns" />

<Accordion title="Paso 5. Migrar campañas">

Cambia las campañas de marketing actuales a AppsFlyer para habilitar la atribución de AppsFlyer, y evita cargos duplicados y la pérdida de datos de atribución.

**Nota**: Puedes elegir migrar solo unas cuantas campañas de marketing a la vez. En este caso, puedes segmentar los que quieres migrar por fuente de medios (por ejemplo, ad network o agencia), ubicación geográfica o campaña.

En las siguientes secciones, se explica lo que se necesita para habilitar la medición de AppsFlyer para diferentes tipos de fuentes de medios: SRN, ad networks no SRN, medios propios y SKAN.

<div id="srns" />

#### SRN

Las SRNs responden a los MMPs (partners de medición móvil) cuando se les pregunta sobre los engagements de dispositivos específicos. Si AppsFlyer y Adjust consultan el mismo SRN sobre la instalación del mismo dispositivo, es posible que se te cobre el doble.

**Para migrar campañas de SRN**:

* Activa y configura las <Anchor target="_blank" href="/marketers/es/docs/self-reporting-networks-srns#srns-integradas-con-appsflyer">SRN</Anchor> relevantes en AppsFlyer.

<div id="note-1" />

> 📘 **Nota**
>
> * Las SRN pueden ejecutar varios MMP (excepto Meta Ads y Twitter).
> * Meta Ads no puede desduplicar eventos in-app.

<div id="non-srn-ad-networks" />

#### Ad networks no SRNs

Los enlaces de atribución de ad networks registran los engagements de los usuarios y se usan posteriormente para atribuir los engagements, que se convierten en instalaciones reales.

**Para migrar campañas de ad networks que no sean SRN**:

1. <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">Activa</Anchor> las ad networks relevantes en AppsFlyer.
2. <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#attribution-link-tab">Genera enlaces de atribución de AppsFlyer</Anchor> para cada ad network.
3. Cambia los enlaces existentes en cada una de tus campañas por los enlaces de atribución de AppsFlyer.

<div id="owned-media" />

#### Medios propios

Los medios propios se refieren a los enlaces de atribución que utilizas en:

* Uso compartido de contenido
* Aplicaciones de CTV, PC y consola
* Correo electrónico
* SMS
* Publicaciones en redes sociales
* Blogs
* Comunidades de internet (Quora, etc.)
* y más...

Para estas campañas, AppsFlyer usa <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">enlaces de OneLink.</Anchor>  Los enlaces de OneLink redireccionan a los usuarios según su dispositivo a la tienda de aplicaciones correcta, directamente a la aplicación o a una URL web/landing page.

**Para cambiar tus enlaces de Adjust por enlaces OneLink de AppsFlyer**:

* Ponte en contacto con tu CSM, quien te ayudará a transformar tus propios enlaces de medios en enlaces de OneLink según los canales y las herramientas que utilices actualmente.

<div id="skan" />

#### SKÁN

En el caso de la atribución SKAdNetwork (SKAN), solo puedes hacer que un SDK actualice el valor de conversión. De lo contrario, los datos de SKAN no tienen sentido. Por lo tanto, asegúrate de que después de la migración, solo el SDK de AppsFlyer actualice el valor de conversión de SKAN.

<Anchor target="_blank" href="/marketers/es/docs/skan-conversion-studio">Saber más sobre cómo configurar el valor de conversión de SKAN en AppsFlyer.</Anchor>

</Accordion>

<div id="step-6-set-up-data-reporting" />

<Accordion title="Paso 6. Configurar la generación de reportes de datos">

Puedes obtener reportes de <Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-apis">raw data</Anchor> y <Anchor target="_blank" href="/marketers/es/docs/analytics-and-aggregate-reporting-apis">agregados</Anchor> de AppsFlyer utilizando varios métodos. Familiarízate con los métodos y configura los que sean relevantes para ti.

Los métodos de reportes incluyen:

* Paneles de control
* Exportar reportes
* API Push
* API Pull
* Casillero de datos

Antes de la migración, tus sistemas almacenan los datos de atribución de Adjust de acuerdo con las estructuras de reportes, los campos y los parámetros que hayas configurado con ellos. Para que AppsFlyer reporte correctamente los datos, debes adaptar y asignar tus estructuras de reportes actuales a los parámetros, campos y estructuras de reportes de AppsFlyer.

**Para adaptar/asignar tus estructuras de reportes:**

* Ponte en contacto con tu CSM de AppsFlyer para que te ayude a adaptar o migrar rápidamente las estructuras de datos de tus reportes de Adjust a AppsFlyer.

</Accordion>

<div id="additional-information" />

## Información adicional

<div id="attributed-migration" />

<Accordion title="Migración atribuida">

Los eventos y sesiones integrados en la aplicación de los dispositivos migrados a AppsFlyer con este método se graban y se muestran de acuerdo con la fuente de medios reportada por el proveedor de atribución anterior y de acuerdo con las políticas de retención de datos de las ad networks.

<div id="attributed-device-migration-csv-structure" />

#### Estructura del archivo CSV de migración de dispositivos atribuidos

| Columna  <br />nombre | Nota | Obligatorio | Ejemplos |
| --- | --- | --- | --- |
| app\_id | ID de aplicación tal como aparece en el dashboard de AppsFlyer | Sí | <ul><li>Android: com.great.app1</li><li>iOS: id123456789</li></ul> |
| plataforma | Plataforma del dispositivo: iOS o Android | Sí | <ul><li>ios</li><li>Android</li></ul> |
| device\_id | <ul><li>Android: gaid o android\_id</li><li>iOS: IDFV (recomendado, si está disponible) o IDFA</li><li>No dupliques la misma combinación de ID de dispositivo e ID de aplicación en varias filas. Si se produce una duplicación, se utiliza la última aparición en el archivo.</li></ul> | Sí | <ul><li>**gaid** (minúsculas): 9c9a82fb-d5de-4cd1-90c3-527441c11828</li><li>**android\_id** (minúsculas): f35aea8908254891</li><li>**IDFV** (mayúsculas): A7328D98-A973-402A-8B87-D22A8611F2AF</li><li>**IDFA** (mayúscula): 9876F1SS-2983-3855-27RR-2R626772VFNB</li></ul> |
| id\_type | <ul><li>Android: advertiserId (también es compatible con amazon\_aid), android\_id</li><li>iOS :idfa o idfv</li><li>Actualmente, no se admiten otros identificadores, OAID e IMEI.<br />Usa la migración sin atributos para los usuarios de Android que no sean de Google Play.</li></ul> | Sí | <ul><li>advertiserId</li><li>android\_id</li><li>idfa</li><li>idfv</li></ul> |
| install\_time | La hora de instalación original de la aplicación con el formato UTC <Anchor target="_blank" href="http://joda-time.sourceforge.net/cal_iso.html">ISO 8601</Anchor>:  <br />**yyyy-mm-ddTHH:MM:SS.SSS** | No | 2018-01-22T08:45:33.412 |
| media\_source | <ul><li>Elige entre:<ul><li>AppsFlyer partner ID</li><li>Fuente de medios personalizada (no puede ser un ID de partner).</li></ul></li><li>Para obtener la lista de ID de partners que requiere AppsFlyer:<ul><li><Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">Habilita todos los partners integrados relevantes.</Anchor></li><li>Ejecuta la API para <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_v1-integrations">obtener las integraciones activas</Anchor> para obtener una lista de todas las integraciones activas.</li><li>Utiliza el **media\_source\_name** de la API como valor **media\_source** en el CSV.</li><li>Excepciones:<ul><li>Para Apple Search Ads, usa **Apple Search Ads**.</li><li>Para Twitter, usa **twitter**.</li></ul></li></ul></li><li>Formato: Los valores distinguen entre mayúsculas y minúsculas.</li></ul> | Sí | No orgánico: facebook\_int, googleadwords\_int<br /><br />Orgánico: organic |
| integrated\_partner | <ul><li>Indica si la fuente de medios es un partner integrado o no. Esto significa una fuente de medios orgánica o personalizada.</li><li>Formato: Los valores distinguen entre mayúsculas y minúsculas</li></ul> | Sí | <ul><li>Sí</li><li>no (si media\_source es personalizado)</li></ul> |
| campaign | Para obtener detalles de atribución más granulares, suministra el nombre original de la campaña.<br /><br />Formato: cadena | No |  |
| campaign\_id | Para obtener información más detallada sobre la atribución, introduce el identificador de la campaña original.<br /><br />Formato: Strings no permiten espacios | No |  |

**Reglas de archivo CSV:**

* El archivo CSV puede contener dispositivos de usuarios de varias aplicaciones.
* No dupliques la misma combinación de ID de dispositivo e ID de aplicación en varias filas. Si se produce una duplicación, se utiliza la última aparición en el archivo.
* Deben incluirse todos los encabezados de las columnas: app\_id,platform,device\_id,id\_type,install\_time,media\_source,integrated\_partner,campaign,campaign\_id. **Nota**: El orden de los campos es importante y debe mantenerse.
* Puedes agregar el IDFV y el IDFA para el mismo dispositivo, pero deben estar en filas separadas. Todos los campos de las filas separadas deben ser los mismos, excepto device\_id.
* Cada fila debe contener exactamente 9 campos separados por comas.
* Deja los campos no obligatorios vacíos (en blanco).
* Los archivos pueden contener hasta 5 millones de filas.
* Si tienes varios archivos, ponle a cada uno un nombre único.
* Codifica datos utilizando UTF-8.
* [Opcional] Comprime archivos con ZIP o GZIP.

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQPvcJ3zXjsB5Zrn8vqD_-QXFPjguDU9Y8_LfK6-2eOgdlDltmFdGoM-94Ouw-D327oMp9p0ZbFFawF/pub?gid=0&single=true&output=csv">Ver ejemplo de CSV</Anchor>

</Accordion>

<div id="nonattributed-migration" />

<Accordion title="Migración no atribuida">

Los dispositivos migrados a AppsFlyer con este método se atribuyen, pero no se muestran, como usuarios orgánicos. Los datos de sus sesiones y eventos in-app también se atribuyen y se muestran como orgánicos.

<div id="non-attributed-device-migration-csv-file-structure" />

#### Estructura del archivo CSV de migración de dispositivos no atribuidos

| Opción | Columnas | Cuándo usar | Ejemplo |
| --- | --- | --- | --- |
| 1 | ID de aplicación + IDFA/GAID/IDFV | <ul><li>Si todos tus usuarios de Android tienen identificadores GAID.</li><li>Solo usuarios de iOS</li></ul> | [![device_migration_file_option_1.png](https://files.readme.io/278f509a6078439feaddee429ebdd59b6098fa9a7ca1803da0f1520019cd1006-30563700100497.png)](https://files.readme.io/278f509a6078439feaddee429ebdd59b6098fa9a7ca1803da0f1520019cd1006-30563700100497.png) |
| 2 | ID de aplicación + ID de dispositivo + tipo de ID de dispositivo | <ul><li>Si algunos de tus usuarios de Android solo tienen IMEI o ID de Android, pero no ID de publicidad de Google (GAID) (mercados fuera de la tienda, versiones de Android inferiores a 4.4.2).</li><li>El ID de Android debe tener un formato hexadecimal.</li></ul>**Nota**:<ul><li>Utiliza las cadenas exactas para la columna de **tipo de ID**: advertiserId (también es compatible con amazon\_aid), idfa, idfv, android\_id, imei.</li><li>Si usas android\_id o imei, y más tarde, AppsFlyer recibe un mejor identificador, se puede registrar una nueva atribución.</li></ul> | [![device_migration_file_option_2.png](https://files.readme.io/40459c68eecf4e402178c2a5b93fe94d8ae2f2dd9ccebc376387a60734612fa3-30563700109969.png)](https://files.readme.io/40459c68eecf4e402178c2a5b93fe94d8ae2f2dd9ccebc376387a60734612fa3-30563700109969.png) |

**Reglas de archivo CSV:**

* El archivo CSV puede contener dispositivos de usuarios de varias aplicaciones.
* Cada fila contiene un único ID de dispositivo por aplicación. Sin embargo, asegúrate de crear plantillas separadas con el subdominio; no agregues manualmente el subdominio al ID de plantilla.
* Según la opción de estructura de archivos que elijas, las columnas de los archivos deben ser las siguientes (y en el orden indicado):
  * Opción 1: app\_id,device\_id
  * Opción 2: app\_id,device\_id,id\_type
* ID de aplicación en minúsculas
* Identificadores de Android en minúsculas
* IDFA/IDFV en mayúsculas
* Se permiten hasta 25 millones de filas

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQPvcJ3zXjsB5Zrn8vqD_-QXFPjguDU9Y8_LfK6-2eOgdlDltmFdGoM-94Ouw-D327oMp9p0ZbFFawF/pub?gid=935533759&single=true&output=csv">Ver ejemplo de CSV</Anchor>

</Accordion>

<div data-zendesk-anchors="overview=sobre-la-migraci%C3%B3n-a-appsflyer 01H8EDSTP8N4GZJQ5J609C3DHM=sobre-la-migraci%C3%B3n-a-appsflyer compare-measurement-between-appsflyer-and-adjust=compara-las-mediciones-entre-appsflyer-y-adjust h_01HQJ10ZFJR43KBYMD9A07CJ99=compara-las-mediciones-entre-appsflyer-y-adjust tasks=tareas 01H8EDSTP8YGDZBPEY1976JP8C=tareas 01JE3EC4C847ZEK769Y9G237KG=step-1-create-an-appsflyer-account 01JE3EC4C9V83D0V46EJK49JZ2=step-2-add-your-app 01JE3EC4CAKY4FQBPPZSJFP5V5=step-3-integrate-the-sdk step-4-migrate-devices%E2%80%94optional=step-4-migrate-devices-optional 01JE3EC4CPT4KAER27C8C0DHH7=step-4-migrate-devices-optional 01H8EDSTP93QJA4XZB6TDWWH1V=ejemplo 01JA2CAMW3HCHC4B9FX7517FJ6=nota 01JE3EJ5DVXF1VT28ZCGR7SMF3=step-5-migrate-campaigns srns=srn 01JE3EXVNRMA2MFVPSJZ2RMR09=srn 01H8EDSTP9ZGMHSM44BWGF1FJN=nota-1 nonsrn-ad-networks=ad-networks-no-srns 01JE3EXVNTWK4ZJS55WXHFKSMX=ad-networks-no-srns owned-media=medios-propios 01JE3EXVNTS4FVXN370G1CR8Z9=medios-propios skan=sk%C3%A1n 01JE3EXVP4TSMGSZD4B460RSQA=sk%C3%A1n 01JE3F6VXDG9MDCVWN81RSHXVG=step-6-set-up-data-reporting additional-information=informaci%C3%B3n-adicional 01JE3E5VHV2WCFWABC9FYQW3VG=informaci%C3%B3n-adicional 01JE3FG6K95QT60C36R88WGDG4=attributed-migration attributed-device-migration-csv-structure=estructura-del-archivo-csv-de-migraci%C3%B3n-de-dispositivos-atribuidos 01H8EDSTP9HABKEZJXMB84CDDE=estructura-del-archivo-csv-de-migraci%C3%B3n-de-dispositivos-atribuidos 01JE3FG6MKNJMTHSR5B2ZMQP1K=nonattributed-migration nonattributed-device-migration-csv-file-structure=estructura-del-archivo-csv-de-migraci%C3%B3n-de-dispositivos-no-atribuidos 01H8EDSTP9AFDMQS6BPQJY19ZH=estructura-del-archivo-csv-de-migraci%C3%B3n-de-dispositivos-no-atribuidos" />
