---
title: Decodificación de CV de SKAN (asigna tu CV a los eventos)
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2020-10-26T20:31:40Z'
  edited_at: '2026-08-12T12:21:36Z'
  id: 360014696297
  locale: es
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/es/articles/360014696297
---
> **En resumen:** AppsFlyer decodifica y transforma el valor de conversión establecido por ti en eventos. Los eventos se utilizan para rellenar el panel de SKAN, los raw data y los postbacks a los partners.

![SKAdNetwork_-_Custom__1_.png](https://files.readme.io/74f0d3836ee6a73f6746afa2d6d6a468c09cba696561c5a2075149ca360b78bf-34255690318097.png)

<div id="decode-skan-conversion-value" />

## Decodificar el valor de conversión de SKAN

Los anunciantes utilizan la decodificación del valor de conversión como alternativa a las opciones disponibles en <Anchor target="_blank" href="/marketers/es/docs/skan-conversion-studio">Conversion Studio</Anchor>. Si usas Decodificar, significa que eres responsable de configurar <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/4097267-updatepostbackconversionvalue">updatePostbackConversionValue</Anchor> de acuerdo con la lógica de tu aplicación.

Además de establecer el valor de conversión (CV) en la aplicación, el resto del flujo, las funciones y las opciones de reportes son los mismos que los descritos en la <Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-solution-guide">guía de soluciones de SKAN</Anchor>. Esto significa que, al expirar el período de actividad (controlado por ti), iOS envía el postback a la red de publicidad que la reenvía a AppsFlyer. AppsFlyer decodifica el CV de acuerdo con tu asignación en eventos procesados de la misma manera que los CV decodificados establecidos por el SDK.

<div id="custom-conversion-valuedecode" />

## Valor de conversión personalizado: decodificar

La implementación de la decodificación de CV personalizada requiere subir un archivo CSV que contenga tu asignación de CV a la plataforma AppsFlyer.

**Decodificar los principios de asignación**

* Proporciona una asignación de decodificación para valores de conversión precisos (1 - 63) y valores de conversión aproximados (bajo, medio y alto) para las ventanas 1 - 3. No es obligatorio asignar todo el rango de valores. Por ejemplo, puedes asignar los valores 1, 2, 10 y 43.
* El CV 0 siempre está asignado para instalarse. No puedes configurarlo.
* La tabla de asignación se carga en AppsFlyer en un archivo CSV. Puedes cargar una tabla de asignación actualizada según sea necesario.
* Al recibir un postback de iOS, el CV se decodifica en eventos, como se ilustra en los ejemplos.
* La hora de instalación se calcula en función de la hora de llegada del postbacks.
* Los eventos tienen la misma hora que la hora de instalación.
* Para entender mejor cómo preparar el esquema, revisa los escenarios de asignación que aparecen a continuación.
* Se permiten nombres de <Anchor target="_blank" href="/marketers/es/docs/in-app-event-postback-configuration#eventos-personalizados">eventos in-app personalizados</Anchor>.
  * Lo que significa que envías nuevos nombres de eventos, incluso si el SDK nunca los ha enviado.
  * Puedes asignar los eventos in-app a los eventos in-app de la red publicitaria.
  * Esto también se aplica a la integración de Anuncios de Meta, sujeta a las reglas específicas de Meta que se detallan en la siguiente sección.

<div id="decode-mapping-scenario-rules" />

<Accordion title="Decodificar las reglas de los escenarios de asignación">

Ten en cuenta lo siguiente:

* Intervalo de valores de conversión precisos: de 1 a 63
* Rango de valores de conversión aproximado: Bajo, medio y alto
* Un valor de conversión determinado se asigna a uno o más eventos in-app que hayas especificado. Los eventos in-app tienen parámetros opcionales.
* Para ver los ejemplos: supongamos que la fecha de instalación es el 1 de febrero a las 08:00.
* La tabla que sigue es un ejemplo de tabla de asignación de decodificación. Su estructura es similar a la del archivo CSV requerido. A continuación de la tabla se muestran los eventos generados como resultado del proceso de decodificación.
* Siempre se genera un evento de instalación, independientemente de tu asignación.
* Medición de ingresos:
  * Los ingresos están en USD.
  * Un valor de conversión determinado tiene un rango de ingresos limitado por min\_revenue y max\_revenue.
  * En los reportes y paneles de control agregados, los ingresos se calculan como el promedio del rango. Ejemplo: min\_revenue=4 y max\_revenue=10. Los ingresos calculados son 7.
  * Los reportes de raw data incluyen los ingresos calculados (skad\_revenue), min\_revenue y max\_revenue.

<div id="meta-specific-rules" />

#### **Reglas específicas de Meta**

Si te integras con Anuncios de Meta, sigue las siguientes reglas:

* Los valores de ingresos mínimos y máximos de un valor de conversión determinado deben ser diferentes. Lo que significa que no es igual.
* Los valores no deben superponerse y deben estar en orden consecutivo, como se muestra para los valores de conversión del 1 al 2 y 62 en la tabla siguiente.
* event\_counter: Los Anuncios de Meta no tienen en cuenta este valor. [Práctica recomendada] Llénalo con un valor de 1.

<div id="example-decode-mapping" />

### Ejemplo: Decodificar la asignación

| valor de  <br />conversión | nombre del  <br />evento | valor del  <br />evento | min\_revenue<br /><br />(no incluido) | max\_revenue (inclusive) | contador de  <br />eventos | horas desde la  <br />instalación |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | af\_compra | `{abc}` | 0 | 3 | 1 | 24 |
| 2 | af\_compra | `{def}` | 3 | 10 | 3 | 36 |
| 21 | event\_a |  |  |  | 1 | 24 |
| 21 | event\_b |  |  |  | 3 | 24 |
| 21 | event\_c | `{xyz}` |  |  | 2 | 24 |
| 21 | event\_d |  |  |  | 1 | 24 |
| 21 | event\_e |  |  |  | 1 | 24 |
| 21 | event\_f |  |  |  | 1 | 24 |
| 21 | event\_g |  |  |  | 1 | 24 |
| 62 | af\_compra | \{fgh) | 10 | 17 | 2 | 72 |
| 62 | event\_a | `{klm}` |  |  | 3 | 72 |

<div id="example-a-fine-conversion-value-1" />

### Ejemplo A : Valor de conversión preciso 1

| nombre\_del\_evento | ingresos\_skad | min\_revenue | max\_revenue | event\_value |
| --- | --- | --- | --- | --- |
| instalar |  |  |  |  |
| af\_compra | 1.5 | 0 | 3 | `{abc}` |

<div id="example-b-fine-conversion-value-2" />

### Ejemplo B: Valor de conversión preciso

| nombre\_del\_evento | ingresos\_skad | min\_revenue | max\_revenue | event\_value |
| --- | --- | --- | --- | --- |
| instalar |  |  |  |  |
| af\_compra | 6.5 | 3 | 10 | `{def}` |
| af\_compra | 6.5 | 3 | 10 | `{def}` |
| af\_compra | 6.5 | 3 | 10 | `{def}` |

<div id="example-c-fine-conversion-value-21" />

### Ejemplo C: Valor de conversión preciso 21

| nombre\_del\_evento | ingresos\_skad | min\_revenue | max\_revenue | event\_value |
| --- | --- | --- | --- | --- |
| instalar |  |  |  |  |
| event\_a |  |  |  |  |
| event\_b |  |  |  |  |
| event\_b |  |  |  |  |
| event\_b |  |  |  |  |
| event\_c |  |  |  | `{xyz}` |
| event\_c |  |  |  | `{xyz}` |
| event\_d |  |  |  |  |
| event\_e |  |  |  |  |
| evento\_f |  |  |  |  |
| evento\_g |  |  |  |  |

<div id="example-d-fine-conversion-value-62" />

### Ejemplo D: Valor de conversión preciso 62

| nombre\_del\_evento | ingresos\_skad | min\_revenue | max\_revenue | event\_value |
| --- | --- | --- | --- | --- |
| instalar |  |  |  |  |
| af\_compra | 13.5 | 10 | 17 | `{fgh}` |
| af\_compra | 13.5 | 10 | 17 | `{fgh}` |
| evento\_a |  |  |  | `{klm}` |
| evento\_a |  |  |  | `{klm}` |
| evento\_a |  |  |  | `{klm}` |

</Accordion>

<div id="ssot-support-for-decode-mode" />

<Accordion title="Soporte de SSOT para el modo Decode">

<div id="overview" />

#### Visión general

Los clientes del modo Decode ahora pueden acceder a la atribución de SSOT (Single Source of Truth), lo que aporta ventajas de deduplicación que antes solo estaban disponibles para los usuarios del modo Encode. Esto mejora la medición del rendimiento no orgánico sin requerir la implementación del modo Encode.

<div id="key-benefits" />

#### Beneficios clave

* Obtén una indicación en tiempo real a través de una API sobre si AppsFlyer atribuye una instalación (no orgánica) o no (orgánica).
* Refleja la señal de atribución de SSOT al actualizar los valores de conversión.
* Usa esquemas de decodificación compatibles con SSOT cargando archivos de esquema actualizados con una marca especial de SSOT.
* Accede a los dashboards de SSOT y a los reportes de DataLocker.
* Deduplica instalaciones no orgánicas entre redes.
* Permite una atribución y unos reportes más precisos.
* Reduce la complejidad del desarrollo y del control de calidad.

<div id="how-to-enable-ssot-for-decode-mode" />

#### Cómo habilitar SSOT para el modo Decode

1. **Extrae el ID de AppsFlyer:** <Anchor target="_blank" href="/marketers/es/docs/server-to-server-events-api-for-mobile-s2s-mobile#fetching-the-appsflyer-id">Recupera el ID de AppsFlyer desde el SDK en el momento de la instalación</Anchor>.
2. **Consulta la API de SSOT:** Usa el ID de AppsFlyer y el ID de la app para comprobar si AppsFlyer atribuyó la instalación.
   * La API devuelve:  
     `"is-non-organic-install": true/false`
3. **Aplica la señal de atribución:** Usa esta señal para ajustar la lógica de CV. Por ejemplo, refleja la atribución añadiendo un evento `af_attribution_flag` a las entradas de CV correspondientes.
4. **Sube el archivo de esquema actualizado -** [Usa tu esquema de descodificación existente](/docs/skan-cv-decode-map-your-cv-to-events#decode-mapping-scenario-rules). En los CV afectados por la atribución de SSOT, añade el evento `af_attribution_flag` para indicar la deduplicación.
5. **Accede a los reportes**  
   Los dashboards de SSOT y los archivos de DataLocker ahora incluyen datos del modo de descodificación.

<div id="faq" />

#### Preguntas frecuentes

**P: ¿Cuándo debo consultar la API para obtener el indicador de atribución de SSOT?**  
**R:**

* Consulta la API inmediatamente después de la instalación.
* Vuelve a consultarla cada 10 segundos (hasta 5 veces) para tener en cuenta el retraso de atribución.
* Como alternativa, consúltala una vez al menos 25 segundos después de la instalación para garantizar la precisión.

</Accordion>

<div id="zd-decode-csv-file-specification" />

<div id="decode-csv-file-specification" />

<Accordion title="Decodificar la especificación del archivo csv">

Los valores de conversión se asignan a uno o más eventos in-app.

**Reglas de archivos**

* Formato: Archivo CSV
* Número máximo de filas: 640 + header row; total 641.
* La fila de encabezado  debe incluir todos los nombres de las columnas tal y como aparecen aquí. Práctica recomendada: Utiliza el archivo de ejemplo adjunto como plantilla. Consulta ejemplos de archivos CSV de decodificación para <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vSCbqgR0D0hqJni36FTOr0MEAaIJSx9h2qaUQ-vWmCUGj7j_-00Ap3J8k4LohMQPndkooLrFFpFPtnH/pub?gid=0&single=true&output=csv">SKAN 3</Anchor> y <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vSCbqgR0D0hqJni36FTOr0MEAaIJSx9h2qaUQ-vWmCUGj7j_-00Ap3J8k4LohMQPndkooLrFFpFPtnH/pub?gid=1187444449&single=true&output=csv">SKAN</Anchor> 4.
* No utilices los siguientes caracteres como primer carácter de una columna: `=`, `+` `-`, y `@` (editado).

### Decodificar la especificación del archivo csv

| Columna | Valor obligatorio | Contenido | Detalles |
| --- | --- | --- | --- |
| valor de conversión | Sí, para:<ul><li>SKAN 3 e inferiores</li><li>SKAN 4 donde postback\_sequence\_index es 0</li></ul> | Valor entero 1—63 | El mismo valor de conversión fina puede aparecer más de una vez. Consulta los ejemplos para obtener una explicación más detallada. |
| coarse\_conversion\_value | Relevante solo para SKAN 4 | String:<ul><li>baja</li><li>mediano</li><li>alto</li></ul> | El mismo valor de conversión aproximado se puede mostrar más de una vez. |
| nombre\_del\_evento | Sí | Cadena | Evento in-app. No tiene que ser un evento que ya exista en AppsFlyer.<br /><br />¡Atención! Los nombres de los eventos in-app distinguen entre mayúsculas y minúsculas.<br /><br />[Práctica recomendada]: Nombre del evento para los ingresos af\_skad\_revenue. |
| event\_value | No | Cadena | Cadena establecida por el desarrollador que contiene los datos que el anunciante debe decodificar en sus sistemas. Por lo general, tiene el formato de un JSON. |
| min\_revenue | No | Entero o flotante | Usa min\_revenue y max\_revenue para establecer un rango de ingresos en USD.<ul><li>Si no quieres asociar los ingresos a un valor de conversión, deja min\_revenue y max\_revenue en blanco.</li><li>El valor establecido en min\_revenue no es inclusivo. Es decir, mayor que 0. Similar a 0.0001</li><li>El valor establecido en max\_value es inclusivo.</li><li>Ejemplo: Si min\_revenue es 0 y max\_revenue es 4, significa que el rango es 0.0001-4</li><li>max\_revenue debe ser mayor que min\_revenue</li></ul>**¡Atención!** **Nota:** Si generas el archivo con Excel, antes de guardarlo, cambia el formato de la columna a coma y no a moneda para evitar que Excel incruste el símbolo $ en el archivo CSV. |
| max\_revenue | No |  | Si completas min\_revenue: max\_revenue debe tener un valor superior a 0.<br /><br />Consulta min\_revenue para obtener la explicación. |
| event\_revenue\_usd | No |  | En desuso desde el 7 de julio de 2021. Usa min\_revenue y max\_revenue |
| Contador de eventos | Sí | Entero | <ul><li>Número de veces que el evento se duplica durante la decodificación. Por lo general, representa la cantidad de veces que el usuario realizó una acción determinada.</li><li>Valor mínimo 1.</li></ul>Ejemplo: Si el usuario realizó un evento determinado 5 veces, se generan 5 eventos.<br /><br />Consideraciones: Si envías ingresos, el importe total en USD declarado se multiplica por el valor de event\_counter. Es decir, si min\_revenue = 0, max\_revenue = 3 y event\_counter = 4, los ingresos totales declarados son 1,5 X 4 = 6.<br /><br />Vea los ejemplos. |
| hours\_from\_install | Sí | Entero | <ul><li>Horas transcurridas desde la instalación</li><li>Valor mínimo: 1</li><li>Valor máximo: 1512 (63 días)</li><li>El valor de todas las filas de un valor de conversión determinado debe ser idéntico. Lo que significa que se permiten valores diferentes para valores de conversión diferentes.</li></ul>AppsFlyer usa esto para derivar y establecer la fecha de instalación de la siguiente manera:<ul><li>Si los postbacks son SKAN V4, la fórmula de la fecha de instalación es: Fecha de instalación = hora de llegada del postback - [duración acumulada de la ventana] - [retraso medio del postback].<ul><li>Postback 1: fecha de instalación = hora de llegada del postback - 48 h - 36 h</li></ul></li><li>Si los postbacks son SKAN V3, la fórmula de la fecha de instalación es: Fecha de instalación = hora de llegada después del postback: 36 horas (promedio del último intervalo activo).<ul><li>El [promedio del último rango activo] predeterminado es de 12 horas.</li><li>Para un valor de conversión de 0, el rango promedio de última actividad se establece en 0.</li></ul></li></ul> |
| postback\_sequence\_index | Sí, pero solo es relevante para SKAN 4 | Entero:<ul><li>0</li><li>1</li><li>2</li></ul> | Para un valor fino, solo se puede recibir el valor 0. |

</Accordion>

<div id="upload-conversion-value-schema-file" />

<Accordion title="Cargar archivo de esquema de valores de conversión">

**Antes de comenzar**:

* Prepare el archivo CSV del esquema de valores de conversión.
* Si te integras con los Anuncios de Meta y mides los ingresos, verifica que tu esquema cumpla con [las reglas relacionadas con Meta.](/docs/skan-cv-decode-map-your-cv-to-events#reglas-específicas-de-meta) Si no lo haces, los Anuncios de Meta no podrán interpretar el esquema.

**Para habilitar la medición SKAN mediante la medición de decodificación:**

1. En AppsFlyer, ve a **Ajustes** > **SKAN Conversion Studio**.
2. Haz clic en Opciones () y selecciona **Cargar archivo de asignación de decodificación**.
3. Si aún no te has actualizado a SKAN 4, elige subir un archivo para SKAN 4 o antes de SKAN 4. Una vez que actualices a SKAN 4, la opción para otras versiones no estará disponible.
4. Realiza una de las siguientes acciones:
   * **Haz clic en Arrastrar y soltar archivo.**
   * **Carga archivo de asignación actualizado.**
5. Sigue las instrucciones de la interfaz de usuario para cargar el archivo.
6. Activa **la medición de SKAN**
7. Haz clic en **Guardar cambios**.   
   Nota: Durante las próximas 48 a 72 horas, los datos sel panel de control son ambiguos. Es decir, debido a problemas con el temporizador de iOS, no podemos estar seguros de si la asignación de decodificación coincide con la asignación de codificación que utilizas.
8. Asegúrate de haber asignado los eventos in-app a los utilizados por los partners para que puedan consumir los postbacks de datos correctamente.

</Accordion>

<div id="troubleshooting-the-csv-upload-errors-file" />

## Solución de problemas del archivo de errores de carga de CSV

<div id="upload-error-messages" />

<Accordion title="Cargar mensajes de error">

Uno o más valores del archivo no coinciden con el formato requerido: El formato del archivo se modificó a partir del 7 de junio de 2021. Compruebe que el formato del archivo coincide con el ejemplo de este artículo.

</Accordion>

<div id="using-excel-to-format-the-event_revenue_usd-column" />

<Accordion title="Uso de Excel para formatear la columna event_revenue_usd">

Al usar hojas de cálculo de Excel/Google para crear un archivo CSV, la columna event\_revenue\_usd debe tener el formato correcto antes de guardar el archivo como archivo CSV.

Después de guardar el archivo CSV, comprueba que el contenido tenga el formato correcto. **Nota**: No utilices Excel para hacer la verificación, utiliza un [editor](/docs/skan-cv-decode-map-your-cv-to-events#visual-inspection-of-the-csv-file-without-excel).

<div id="formatting-event_revenue_usd-cells-in-excel" />

#### Formatear celdas event\_revenue\_usd en Excel

Excel suele dar formato a las celdas de valor con una coma para separar los miles, como se muestra en la figura. Este formato no es adecuado para cargar archivos CSV. También debes eliminar el símbolo $.

![mceclip0.png](https://files.readme.io/3b2aface429f87eb651e6d678760ee3a4b85234a11b0ae2da771d7af7279c1e7-34255643021073.png)

Puedes corregir esto formateando las celdas en Excel.

**Para formatear los importes gastados sin la coma de 1000 ni el símbolo $:**

1. Selecciona las celdas que se van a formatear.
2. Haz clic con el botón derecho y selecciona **Formato de celda**.  
   Se abre la ventana de formato de celda.
3. Selecciona **Número**.  

   <Image alt="Formatnumbers.png" src="https://files.readme.io/4c1b61d1eae9149e818d4cc9793128fbdaafed5daed9acf6cbc503571475cc0e-34255643022481.png" width="381px" />

1. Borra **Usar separador de 1000 (,).** Sin embargo, asegúrate de crear plantillas separadas con el subdominio; no agregues manualmente el subdominio al ID de plantilla.
2. (Opcional) Establece el número de **decimales**. El valor predeterminado es 2. El máximo permitido es 5.
3. Haz clic en **Aceptar**.  
   Las celdas se formatean correctamente.

</Accordion>

<div id="visual-inspection-of-the-csv-file-without-excel" />

<Accordion title="Inspección visual del archivo CSV sin Excel">

Para examinar el contenido del archivo CSV, usa un editor.

* Windows: Bloc de notas, Bloc de notas++
* macOS TextEdit

A continuación se incluye una captura de pantalla del <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vSCbqgR0D0hqJni36FTOr0MEAaIJSx9h2qaUQ-vWmCUGj7j_-00Ap3J8k4LohMQPndkooLrFFpFPtnH/pub?output=csv">archivo CSV de ejemplo</Anchor> mostrado en un editor.

**Vista del editor**

![SKCustomeEditor.png](https://files.readme.io/d8677e9967a70db32e8d04c4ee835bd477b18c1cb464a9cd0e593f72ce3f3c15-34255690323217.png)

Usando un editor, examina el archivo CSV. Presta especial atención a lo siguiente:

* **Espacios en blanco:** Asegúrate de que no haya espacios en blanco al principio o al final antes o después de las comas que separan los campos. En Excel, usa el comando @trim para eliminar los espacios en blanco.
* **event\_revenue\_usd:** Asegúrate de que no haya ni una coma ni un símbolo $ en la columna event\_revenue\_usd.  

  ![mceclip1.png](https://files.readme.io/3b2aface429f87eb651e6d678760ee3a4b85234a11b0ae2da771d7af7279c1e7-34255643021073.png)

</Accordion>

<div id="csv-files-generated-by-excel-dont-have-commas-as-delimiters" />

<Accordion title="Los archivos CSV generados por Excel no tienen comas como delimitadores">

Si Excel crea un archivo CSV con un punto y coma ";" u otro carácter como delimitador, pero no una coma:

* Esto ocurre cuando la configuración regional de tu computadora se establece en un idioma/región que no es el inglés.
* Este tema es particularmente frecuente cuando se selecciona alemán en la configuración regional.
* La solución difiere según el sistema operativo de tu computadora (macOS o Windows).
* Para resolver este problema, busca la guía más reciente de <Anchor target="_blank" href="https://support.office.com/en-us/article/import-or-export-text-txt-or-csv-files-5250ac4c-663c-47ce-937b-339e391393ba#ID0EAAFAAA=Office_2016-2010">Microsoft</Anchor> u otros foros para encontrar una solución. Utiliza los siguientes términos de búsqueda: *Sistema operativo (macOS o Windows) Delimitador de cambios de Excel para archivos CSV.*

</Accordion>

<div data-zendesk-anchors="decode-skan-conversion-value=decodificar-el-valor-de-conversi%C3%B3n-de-skan h_01HAMKKCKJEGCDPN5P8J6X0E8E=decodificar-el-valor-de-conversi%C3%B3n-de-skan custom-conversion-value%E2%80%94decode=valor-de-conversi%C3%B3n-personalizado-decodificar h_01HAMKKCKJ5K6J6NNPF394ZK61=valor-de-conversi%C3%B3n-personalizado-decodificar h_01HAMKKCKJT7MA03SHT4X3MH4W=decode-mapping-scenario-rules facebookspecific-rules=reglas-espec%C3%ADficas-de-meta h_01HAMKKCKJDCEKCNZFSF0V6KH8=reglas-espec%C3%ADficas-de-meta example-decode-mapping=ejemplo-decodificar-la-asignaci%C3%B3n h_01HAMKKCKJ5B7W8FGK01QCKN7Y=ejemplo-decodificar-la-asignaci%C3%B3n example-b-conversion-value-1=ejemplo-a-valor-de-conversi%C3%B3n-preciso-1 h_01HAMKKCKJ1ZRH00A7Q4HZ4BBK=ejemplo-a-valor-de-conversi%C3%B3n-preciso-1 example-b-conversion-value-2=ejemplo-b-valor-de-conversi%C3%B3n-preciso h_01HAMKKCKJZBASWWM1VD0VXWBX=ejemplo-b-valor-de-conversi%C3%B3n-preciso example-c-conversion-value-21=ejemplo-c-valor-de-conversi%C3%B3n-preciso-21 h_01HAMKKCKJ4YHMQENKNVPMV4KC=ejemplo-c-valor-de-conversi%C3%B3n-preciso-21 example-d-conversion-value-62=ejemplo-d-valor-de-conversi%C3%B3n-preciso-62 h_01HAMKKCKJP7V7D26MGM1WVDTE=ejemplo-d-valor-de-conversi%C3%B3n-preciso-62 h_01JQX7MY9QRH71M4S6W9CKCQ5Z=ssot-support-for-decode-mode overview=visi%C3%B3n-general h_01JQX7NZD3KBYTBJMS2VEMK1MT=visi%C3%B3n-general key-benefits=beneficios-clave h_01JQX7PPSRCZXNTH890PP5TD1Q=beneficios-clave how-to-enable-ssot-for-decode-mode=c%C3%B3mo-habilitar-ssot-para-el-modo-decode h_01JQX7QKV73WT10Q8QG0DKSB4S=c%C3%B3mo-habilitar-ssot-para-el-modo-decode faq=preguntas-frecuentes h_01JQX8JC023CMFSD1T6N60YHR8=preguntas-frecuentes h_01HAMKKCKKJFRTXYJNWZNGF97V=decode-csv-file-specification decode-csv-file-specification::d6a1f3f1=decodificar-la-especificaci%C3%B3n-del-archivo-csv h_01HAMKKCKK7G7VP6SDEHBH6383=decodificar-la-especificaci%C3%B3n-del-archivo-csv h_01HAMKKCKKN7WDP6F5E4W91HQJ=upload-conversion-value-schema-file troubleshooting-the-csv-upload-errors-file=soluci%C3%B3n-de-problemas-del-archivo-de-errores-de-carga-de-csv h_01HAMKKCKK0QQ8AS8FZ83MZ8FH=soluci%C3%B3n-de-problemas-del-archivo-de-errores-de-carga-de-csv h_01HAMKKCKK3B2T9VSTYCVE0017=upload-error-messages h_01HAMKKCKKFJAE4B88QV00HYPW=using-excel-to-format-the-event_revenue_usd-column formatting-event_revenue_usd-cells-in-excel=formatear-celdas-event_revenue_usd-en-excel h_01HAMKKCKKKVYCWCQCAEMSBMF7=formatear-celdas-event_revenue_usd-en-excel h_01HAMKKCKK39C9SP7K86ER3HZK=visual-inspection-of-the-csv-file-without-excel h_01HAMKKCKK9GEBC64JE4DSDAMQ=csv-files-generated-by-excel-dont-have-commas-as-delimiters" />
