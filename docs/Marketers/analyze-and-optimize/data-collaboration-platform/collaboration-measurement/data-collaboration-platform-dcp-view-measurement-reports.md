---
title: Plataforma de colaboración de datos (DCP) - Ver reportes de medición
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
  created_at: '2025-04-03T14:39:29Z'
  edited_at: '2026-10-22T03:38:46Z'
  id: 34060852331153
  locale: es
  section: Collaboration measurement
  section_id: 38034865098641
  url: https://support.appsflyer.com/hc/es/articles/34060852331153
---
> **Resumen:** Personaliza tus reportes de medición configurando los campos del reporte, los niveles de agregación, las programaciones y las conexiones en la nube.

Los reportes de medición de la plataforma de colaboración de datos (DCP) proporcionan métricas de alto nivel, como clics, impresiones y ROAS por campaña. También pueden incluir métricas y dimensiones adicionales en función del acceso concedido.

Los reportes se envían directamente a tu almacenamiento en la nube conectado o a tu almacén de datos. Puedes recibir reportes en un formato predefinido o personalizarlos para incluir las métricas y dimensiones específicas que necesites.

<div id="what-are-dimensions-and-metrics" />

<Accordion title="¿Qué son las dimensiones y las métricas?">

El reporte de medición de colaboración es un reporte agregado que resume los datos agrupando y combinando registros individuales. Proporciona insights de alto nivel en lugar de datos sin procesar a nivel de usuario.

Los campos del reporte se dividen en dos tipos: *dimensiones* y *métricas*. Cada uno puede dividirse además en *campos básicos* y *campos calculados*.

### Dimensiones

Una dimensión es una categoría de agrupación que agrega datos a nivel de evento en registros de reporte. Por ejemplo, si se selecciona la fuente de medios como dimensión del reporte, cada fila contendrá datos agregados de todos los eventos atribuidos a esa fuente de medios. El número de filas equivale al número de fuentes de medios.

Añadir más dimensiones aumenta la granularidad de la agrupación. Por ejemplo, seleccionar Fecha del evento, Fuente de medios y Campaña da como resultado una fila por cada combinación única de esos campos.

### Comenzar

Una métrica es un dato numérico agrupado según las dimensiones seleccionadas.

Por ejemplo, si ingresos se selecciona como la métrica y fuente de medios es la única dimensión, el reporte muestra los ingresos totales por fuente de medios.

Cuando se seleccionan varias dimensiones, como Fecha del evento, Fuente de medios y Campaña, los ingresos se agrupan por la combinación de esos campos.

Al seleccionar una métrica, elige su función de agregación. Por ejemplo, para la métrica de ingresos, seleccionarías la función **SUM**.

### ¿Qué son los campos básicos y los campos calculados?

Las dimensiones y las métricas pueden ser campos básicos o campos calculados.

* **Campos básicos:** Los campos básicos contienen raw data de fuentes o eventos in-app.
* **Campos calculados:** Los campos calculados usan campos básicos para calcular valores mediante funciones definidas.

</Accordion>

## Crear un reporte predefinido

Para generar un reporte predefinido, sigue estos pasos:

1. En AppsFlyer, en el menú lateral, ve a **Colaborar** > **Data Clean Room**.
2. En la **Plataforma de Colaboración de Datos** página, selecciona la colaboración correspondiente.
3. En la página de colaboración, haz clic en **Crear reporte.**
4. En el cuadro de diálogo que aparece, haz clic en **Aprobar reporte.** El reporte se envía a tu servicio en la nube conectado con un nombre y una programación predefinidos.

## Crear un informe personalizado

Para crear un reporte personalizado, sigue estos pasos:

<div id="1-open-the-new-report-page" />

<Accordion title="1. Abre la página Nuevo reporte">

1. En AppsFlyer, en el menú lateral, ve a **Colaborar** > **Data Clean Room**.
2. En la **Plataforma de Colaboración de Datos** página, selecciona la colaboración correspondiente.
3. En el dashboard de medición, haz clic en <Image alt="" src="https://files.readme.io/ed483d2c2b845f1274b3cf84887ea15e0b0384a5f1cf3a5148b1fb8458cd6ec9-34061156892177.png" width="25%" /> **Crear reporte.**
4. En el cuadro de diálogo que aparece, haz clic en <Image alt="" src="https://files.readme.io/317ded6d0dbe6b0acfee8d3b8c7898dbab1c9b7ae621802fa867f2a6069f5d79-34061156893457.png" width="25%" /> **Customize**.
5. En la página **Nuevo reporte**, realiza los pasos indicados.

</Accordion>

<div id="2-set-the-report-type" />

<Accordion title="2. Configura el tipo de reporte">

En el paso **Tipo de reporte**, selecciona <Image alt="" src="https://files.readme.io/c94890451d831a5a3f1f12b6f42c1c86de1453c175c40cc450e915f6f1f128ad-34061156898449.png" width="3.47%" />  **Medición de medios de comercio,** y luego haz clic en **Siguiente.**

</Accordion>

<div id="3-set-the-report-scope" />

<Accordion title="3. Configura el alcance del reporte">

En el paso **Filtros y fuentes de datos**:

1. En el cuadro **Nombre del reporte**, introduce un nombre para el reporte.
   * Puede ser cualquier nombre que te ayude a identificar el reporte en la plataforma DCR.
   * **Nota:** Asegúrate de que el nombre del reporte sea diferente de todos los demás reportes de tu cuenta o no podrás <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-creating-attribution-data-reports#set-the-report-destination-and-save-the-report">guardar el reporte</Anchor>.
   * Requisitos del nombre del reporte:
     * Longitud: 2-80 caracteres
     * Caracteres válidos:
       * letras **(A-Z, a-z)**
       * números **(0-9)**, *no pueden ser el primer carácter de un nombre*
       * un guion (-), *no puede ser el primer carácter de un nombre*
     * Caracteres inválidos:
       * espacios
       * todos los demás símbolos o caracteres especiales
2. En el cuadro **Nombre de la colaboración**, selecciona la colaboración correspondiente.
3. En el control deslizante **Periodo**, establece la duración del reporte en días (1-180). En el reporte solo aparecerán los eventos de conversión atribuidos que se produzcan dentro del intervalo seleccionado. El intervalo se calcula hacia atrás desde el día del reporte.
4. Después de la implementación, regresa al **Inicio de sesión único (SSO)** , haz clic en **Confirmar implementación del certificado**y confirma que ha actualizado el último certificado de AppsFlyer.

</Accordion>

<div id="4-set-the-report-dimensions-and-metrics" />

<Accordion title="4. Configura las dimensiones y las métricas del reporte">

Si quieres personalizar el reporte, puedes seleccionar las [dimensiones y métricas](#what-are-dimensions-and-metrics) de tu reporte. Para consultar una lista completa de los campos del reporte, consulta [el esquema del reporte](#esquema-del-reporte) en este artículo.

Para configurar las dimensiones y las métricas del reporte, sigue estos pasos:

1. En el paso **Structure**, en la lista **Dimension from sources**, selecciona los campos que quieres incluir en el reporte.
2. Si quieres crear un [campo calculado](#qué-son-los-campos-básicos-y-los-campos-calculados), haz clic en **+ Calculated field** y consulta [Crear campo calculado](#crear-campo-calculado) en este artículo.
3. Puedes incluir el campo en el reporte como dimensión o como métrica.
   * Para incluir el campo en el reporte como dimensión, haz clic en **Set as dimension**.
   * Para incluir el campo en el reporte como métrica, haz clic en **Set as metric**.
4. Si configuras el campo como métrica, selecciona su función de agregación:
   * **Suma:** El valor de la métrica es la suma de los valores a nivel de evento agregados en el registro del reporte. Por ejemplo, la métrica de ingresos es la suma de  `sku_revenue` de todos los eventos agrupados en el registro.
   * **Recuento:** El valor de la métrica es el recuento de los valores a nivel de evento agregados en el registro del reporte. Por ejemplo, la métrica de conversiones es el recuento de todas las conversiones incluidas en el registro agrupado.
   * **Recuento distinto**: El valor de la métrica es el número de valores únicos de un campo determinado en todos los eventos agrupados en el registro del reporte. Por ejemplo, si la métrica seleccionada es el recuento distinto de `sku` y un registro agrupado incluye 10 eventos que contienen 4 SKU diferentes, el valor de la métrica será **4**.
5. Para cambiar el nombre para mostrar del campo, coloca el cursor sobre el campo y haz clic en **Edit display name.**

#### Crear campo calculado

Los campos calculados contienen valores calculados a partir de valores básicos mediante una función específica.

Para crear o editar un campo calculado, haz lo siguiente:

1. Para crear o editar un campo calculado, realiza una de las siguientes acciones
   * **Crear**: Haz clic en **+ Calculated field.**
   * **Editar**: Coloca el cursor sobre el campo calculado y haz clic en el menú de acciones → Edit calculated field.
2. En el cuadro de diálogo **Editar** o **Nuevo campo calculado**, haz lo siguiente:
   1. En el cuadro **Campo**, introduce el nombre del campo.
   2. En la lista **Establecer función**, selecciona la función que se usa para calcular el nuevo valor.
3. Configura la función según la tabla que se indica a continuación:

| **Función** | **Description** | **Cálculo de ejemplo** | **Descripción del ejemplo** |
| --- | --- | --- | --- |
| `AGREGAR` | Suma de dos números | `Clics + Impresiones` | Interacciones totales (clics + impresiones de anuncios). |
| `ARRAY SIZE` | Transforma el array de cadenas JSON a su tamaño | `ARRAY_SIZE(Products_Clicked)` | Número de productos en los que un usuario hizo clic en una campaña (desde JSON). |
| `CASE WHEN` | Devuelve un valor cuando se cumple la primera condición o ELSE | `CASE WHEN Conversions > 0 THEN 'Successful' ELSE 'Failed' END` | Clasifica la performance de la campaña en función de las conversiones. |
| `CONCAT` | Concatenación de dos cadenas | `CONCAT(Campaign_Name, ' - ', Region)` | Combina el nombre de la campaña con la región para reportar. |
| `CONST` | Devuelve su parámetro | `CONST('Límite del presupuesto de marketing: $5000')` | Devuelve un valor constante como referencia del presupuesto. |
| `DATETIME DIFF` | Período en las unidades seleccionadas entre `start` y `end` | `DATETIME_DIFF(End_Date, Start_Date, 'day')` | Calcula la duración de la campaña en días. |
| `MAX` | Máximo de dos números | `MAX(Click_Through_Rate, Conversion_Rate)` | Encuentra el valor más alto entre el CTR y la tasa de conversión. |
| `MIN` | Mínimo de dos números | `MIN(Budget_Remaining, Daily_Spend_Limit)` | Garantiza que el gasto no supere el presupuesto diario. |
| `MULTIPLY` | Multiplicar dos números | `Conversions * Avg_Order_Value` | Calcula los ingresos totales a partir de las conversiones. |
| `REGEX EXTRACT` | Extrae el primer grupo por regex. | `REGEX_EXTRACT(Ad_Text, 'PromoCode: (\\w+)')` | Extrae el código promocional del texto del anuncio mediante regex. |
| `SUBSTRING` | Subcadena de un string desde el índice `start` hasta `end` | `SUBSTRING(Campaign_ID, 0, 5)` | Extrae los 5 primeros caracteres del ID de la campaña. |
| `SUBTRACT` | Resta de dos números | `Budget_Allocated - Budget_Spent` | Calcula el presupuesto restante de la campaña. |


</Accordion>

<div id="5-manage-dimension-priority" />

<Accordion title="5. Gestionar la prioridad de las dimensiones">

Los grupos de dimensiones con muy pocos eventos a nivel de usuario pueden entrar en conflicto con las normativas de privacidad de datos.

Para resolverlo, **DCR fusiona los grupos pequeños** con grupos más grandes eliminando las dimensiones con mayor especificidad.

De forma predeterminada, las dimensiones se eliminan en orden inverso a su posición en la lista **Dimensiones del reporte**. Sin embargo, puedes ajustar el orden predeterminado y aplicar una prioridad de reagrupación diferente para conservar las dimensiones más importantes para ti. Para saber más, consulta un <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-creating-attribution-data-reports#preservación-de-la-privacidad-mientras-se-agrupa-por-dimensión-reagrupación">ejemplo de reagrupación</Anchor>.

**Para cambiar la prioridad de la dimensión:**

1. En el paso **Administrar la prioridad de las dimensiones**, haz clic en **Administrar la prioridad de las dimensiones**
2. Arrastra la dimensión para reorganizar el orden.
   * La dimensión etiquetada como **Máxima prioridad** (en la parte superior de la lista) indica que será la última en eliminarse si se requiere reagrupamiento.
3. [Opcional] Para aplicar la reagrupación a las dimensiones de origen personalizadas:
   1. Haz clic **Usar opciones avanzadas para refinar el reagrupamiento**
   2. Selecciona las dimensiones de fuentes personalizadas a las que deseas aplicar el reagrupamiento.
   3. Las dimensiones seleccionadas se añaden a la **Administrar la prioridad de las dimensiones** lista.
      * De forma predeterminada, estas dimensiones se agregan al final de la lista como la **Prioridad más baja** para el reagrupamiento. Sin embargo, puedes reordenarlas igual que las dimensiones de los datos de atribución, tal y como se describe anteriormente.
4. Haz clic **Siguiente** para guardar tus cambios.
   * La **Dimensiones del reporte** lista en la pantalla principal permanece en su orden original, pero el orden revisado se ha guardado. (Haz clic de nuevo en el **Administrar la prioridad de las dimensiones** botón para revisar o editar tu selección.)

</Accordion>

<div id="6-set-the-report-schedule-and-destination" />

<Accordion title="6. Configura la programación y el destino del reporte">

DCP entrega reportes a tus servicios en la nube seleccionados mediante <Anchor target="_blank" href="/marketers/es/docs/data-locker-for-marketers">AppsFlyer Data Locker</Anchor>. Por lo tanto, especificar el destino del reporte implica seleccionar o crear una conexión de Data Locker.

**Para configurar la programación y el destino del reporte:**

1. En el paso **Configuración**, en la sección **Programación**, selecciona la programación del reporte (diaria, semanal o mensual).
2. Según el intervalo seleccionado, selecciona la hora, el día de la semana o el mes del reporte.
3. En la sección **Destino**, selecciona de la lista de conexiones de Data Locker disponibles en tu cuenta de AppsFlyer.
   * Si no hay conexiones definidas en tu cuenta:
     * Se abrirá una nueva pestaña en tu navegador (que muestra la página de AppsFlyer Data Locker)
     * Se abrirá el cuadro de diálogo **Nueva conexión** . Sigue <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-working-with-connections#completa-la-conexión-1">estas instrucciones</Anchor> para crear la conexión.
   * Si tienes conexiones existentes pero quieres usar una nueva, haz clic en **+ New connection in Data Locker**:
     * Se abrirá una nueva pestaña en tu navegador (que muestra la página de AppsFlyer Data Locker)
     * Se abrirá el cuadro de diálogo **Nueva conexión** . Sigue <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-working-with-connections#completa-la-conexión-1">estas instrucciones</Anchor> para crear la conexión.
     * Después de crear la conexión, vuelve a la pestaña DCP de tu navegador y selecciona la conexión recién creada de la lista de conexiones de Data Locker.
4. Para recibir notificaciones del estado del reporte a través de la API, activa **Notificaciones del estado del reporte,** y, en el cuadro del endpoint de la API, introduce la URL de tu API.
5. Haz clic **Guardar** para guardar el reporte.
6. El nuevo reporte ahora se muestra en la **Reportes** pestaña.

</Accordion>

## Esquema del reporte

El reporte está compuesto por las siguientes dimensiones y métricas, categorizadas como campos calculados y campos de atribución:

<div id="calculated-fields" />

<Accordion title="Campos calculados">

| **Campo** | **Description** |
| --- | --- |
| `clicks` | Número total de clics en el anuncio. |
| `CTR` | Tasa de clics (clics divididos entre impresiones). |
| `event_date` | Fecha en la que ocurrió el evento. |
| `Impresiones` | Número de veces que se mostró el anuncio. |
| `ingresos_totales` | Ingresos totales generados en todos los eventos. |
|  |  |

</Accordion>

<div id="attribution-fields" />

<Accordion title="Campos de atribución">

| **Campo** | **Description** |
| --- | --- |
| `ad_id` | Identificador único del anuncio. |
| `ad_name` | Nombre del anuncio. |
| `ad_type` | Tipo de anuncio (p. ej., banner, vídeo). |
| `adset_id` | Identificador único del conjunto de anuncios. |
| `adset_name` | Nombre del conjunto de anuncios. |
| `advertising_id` | ID de dispositivo restablecible por el usuario (p. ej., GAID). |
| `android_id` | ID de dispositivo Android permanente. |
| `id_aplicación` | Identificador único de la aplicación. |
| `app_name` | Nombre de la aplicación. |
| `version_app` | Versión de la aplicación. |
| `appsflyer_id` | ID único asignado por AppsFlyer. |
| `campaign_id` | Identificador único de la campaña. |
| `campaign_name` | Nombre de la campaña. |
| `channel` | Canal de la fuente de medios (p. ej., YouTube). |
| `city` | Ciudad del usuario según la ubicación de la IP. |
| `código_de_país` | Código de país ISO 3166-1 alfa-2 (p. ej., US, GB). |
| `cuid` | Identificador único del cliente/usuario. |
| `categoría_del_dispositivo` | Tipo de dispositivo (p. ej., teléfono, tableta). |
| `nombre_del_evento` | Nombre del evento (p. ej., instalación, compra). |
| `ingresos_evento` | Ingresos generados por el evento. |
| `idfa` | ID de publicidad de iOS restablecible por el usuario. |
| `idfv` | ID del proveedor asignado por iOS. |
| `plataforma` | La plataforma (iOS, Android, etc.). |
| `region` | Región del usuario según la ubicación de la IP. |
| `ingresos_sku` | Ingresos asociados con un SKU específico. |
| `state` | Estado del usuario en función de la ubicación de la IP. |

</Accordion>

<div id="scheme-fields" />

<Accordion title="Campos del esquema">

| **Campo** | **Description** | **Disponibilidad en el sitio** | **Disponibilidad fuera del sitio** |
| --- | --- | --- | --- |
| conversiones | Número de conversiones | Verdadero | FALSO |
| Count\_AFID | Cantidad total de usuarios únicos | Verdadero | Verdadero |

</Accordion>

<div data-zendesk-anchors="h_01JQY1FA02JN6VR67HJ5118SFF=what-are-dimensions-and-metrics dimensions=dimensiones h_01JR5NBE6NQ22QCFZG9XRVGM45=dimensiones metrics=comenzar h_01JR5NC59TQ45QPWP7JG6BQKXX=comenzar what-are-basic-and-calculated-fields=qu%C3%A9-son-los-campos-b%C3%A1sicos-y-los-campos-calculados h_01JQY33FZ2H59YZVVXBN9J61RE=qu%C3%A9-son-los-campos-b%C3%A1sicos-y-los-campos-calculados create-a-predefined-report=crear-un-reporte-predefinido h_01JQY1FA03AXH588Z5C9HCJHMS=crear-un-reporte-predefinido create-a-custom-report=crear-un-informe-personalizado h_01JQY1FA038V0V1PKBF1CC0B5J=crear-un-informe-personalizado h_01JQY1FA035K7VWX4BDC796SVT=1-open-the-new-report-page h_01JQY1FA03Z0W8N8PFVGEC3HRM=2-set-the-report-type h_01JQY1FA03CWP0GSJY46CEJRJY=3-set-the-report-scope h_01JQY1FA03WA8NNB4RT1VBK0F5=4-set-the-report-dimensions-and-metrics create-calculated-field=crear-campo-calculado h_01JQY1FA03PA40NCTZXHWGQ86C=crear-campo-calculado h_01JQY1FA03TMN4N7V3F83EK4EY=5-manage-dimension-priority h_01JQY1FA03PRSGHSKNTKNV4NH3=6-set-the-report-schedule-and-destination report-scheme=esquema-del-reporte h_01JQY1FA03S41J7TR5HAF6G8PW=esquema-del-reporte h_01JQY1FA0494AK29M0R7ZRJ4DT=calculated-fields h_01JQY1FA0486WK4GHV5G3TZ77V=attribution-fields h_01JQY1FA04DTN2C6A541J25RZJ=scheme-fields" />
