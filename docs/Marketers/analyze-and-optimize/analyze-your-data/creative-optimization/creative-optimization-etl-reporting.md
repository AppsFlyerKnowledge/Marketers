---
title: 'Optimización creativa: reportes de ETL'
metadata:
  keywords:
    - Premium
    - Marketers
    - Creative Optimization
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-omer-katzburg
    - Marketers
    - Creative Optimization
  created_at: '2023-10-10T14:33:17Z'
  edited_at: '2026-08-12T11:50:03Z'
  id: 19253873174801
  locale: es
  section: Creative Optimization
  section_id: 4419063475217
  url: https://support.appsflyer.com/hc/es/articles/19253873174801
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **De un vistazo:** Optimización creativa ETL transmite diariamente tus datos de rendimiento creativo al almacenamiento en la nube para cargarlos directamente en tus sistemas de inteligencia empresarial (BI), sin necesidad de exportaciones manuales. Elige entre **Standard Creative ETL**, que ofrece una estructura de reporte fija, y **Custom Creative ETL**, que te permite elegir exactamente qué dimensiones, métricas y eventos incluir.

## Acerca del ETL de Optimización creativa

Optimización creativa ETL transmite automáticamente a diario tus datos de rendimiento creativo al almacenamiento en la nube, lo que los hace disponibles para su carga programática en tus sistemas de BI. Hay dos opciones disponibles en función de tus necesidades y de tu plan de suscripción.

**Standard Creative ETL** se configura a través de Data Locker y ofrece un reporte diario fijo que cubre las dimensiones creativas principales y las métricas de rendimiento. Está disponible para todos los clientes de Optimización creativa.

**Custom Creative ETL** te da control total sobre el esquema de tu reporte (las dimensiones, métricas y eventos que componen tu reporte, y el orden en que aparecen). Configura tu esquema directamente en la interfaz de Creative ETL y selecciona exactamente las dimensiones, métricas, dimensiones de IA y eventos in-app que necesites, incluidos los desgloses de retargeting y de atribución unificada. Está disponible para los suscriptores del plan Creative Optimization Premium.

<div id="standard-creative-etl" />

<Accordion title="Standard Creative ETL">

La extracción, transformación y carga (ETL) de la Optimización creativa equipa a tus analistas de datos con toda la información que necesitan para el análisis del rendimiento creativo. Esto se logra mediante la transmisión automática de reportes de Optimización creativa al almacenamiento en la nube para la carga programática en tus sistemas de Business Intelligence.

Se proporcionan reportes completos de rendimiento a nivel de recursos, incluidos todos los indicadores clave de rendimiento (KPI), los KPI de embudo superior e inferior, datos de atribución y datos de recursos creativos.

El ETL de Optimización creativa utiliza <Anchor target="_blank" href="/marketers/es/docs/data-locker-for-marketers">Data Locker</Anchor> para enviar tus datos de reportes de Optimización creativa al almacenamiento en la nube. Puedes seleccionar entre varios destinos de almacenamiento, como un bucket propiedad de AppsFlyer en Amazon Web Services (AWS) o tu propio almacenamiento en AWS, GCS, Yandex, BigQuery, Snowflake y más. Data Locker admite múltiples destinos, lo que significa que puedes enviar todos los datos a uno o más destinos, enviar datos específicos a ciertos destinos y personalizar la entrega de datos según tus necesidades.

> 📘 **Cadena**
>
> Standard Creative ETL tiene un esquema fijo y no admite eventos in-app, dimensiones de IA ni desgloses de retargeting/unificados. Si quieres un esquema totalmente personalizable, consulta [Custom Creative ETL](#custom-creative-etl) a continuación.

#### Comienza

En esta sección se describe cómo configurar Data Locker para el reporting de Creative Optimization.

**Requisitos previos**

* Una suscripción a Creative Optimization Premium (contacta con tu customer success manager de AppsFlyer)

**Para configurar Data Locker:**

1. Sigue estas <Anchor target="_blank" href="/marketers/es/docs/data-locker-for-marketers#set-up-data-locker">instrucciones</Anchor>.
2. Al configurar Data Locker, selecciona **Creatividad** (bajo **Seleccionar reportes**), en la página de configuración de Data Locker.

#### Edición de la configuración de Data Locker

Esta sección describe la disponibilidad de datos en Creative Optimization ETL.

**Para agregar los reportes de Optimización creativa a Data Locker:**

1. En **Integraciones** en el menú lateral principal de AppsFlyer, haz clic en **Data Locker**.
2. En la página de configuración de Data Locker, en **Select reports**, selecciona **Optimización creativa**.

#### Actualización de los datos

Una vez configurado, el reporte de Optimización creativa se transmite a Data Locker una vez al día. Cada entrega incluye datos de los últimos 30 días y se transmite diariamente a las UTC+12. La hora local exacta depende de tu zona horaria:

* Nueva York: UTC+12 − 5 = 7:00 a. m.
* Berlín: UTC+12 + 1 = 1:00 p. m
* Shanghái: UTC+12 + 8 = 8:00 p. m

#### Datos disponibles

Los siguientes datos de la creatividad están disponibles en Data Locker.

| Campo | Cadena |
| --- | --- |
| fecha | Cadena |
| asset\_link | Cadena |
| Creatividad | Cadena |
| fuente\_de\_medios | Cadena |
| campaña única | Cadena |
| id\_campaña | Cadena |
| anuncio | Cadena |
| id\_adset | Cadena |
| conjunto de anuncios | Cadena |
| id\_anuncio | Cadena |
| nombre\_aplicación | Cadena |
| id\_aplicación | Cadena |
| creative\_first\_seen | Cadena |
| Cadena | Cadena |
| creative\_type | Cadena |
| duration | Cadena |
| end\_card\_type | Cadena |
| geolocalización | Cadena |
| Identificador de origen | Cadena |
| Orientación | Cadena |
| Cadena | Cadena |
| Impresiones | Cadena |
| clics | Cadena |
| Cadena | Cadena |
| Cadena | Cadena |
| CVR | Cadena |
| IPM | Cadena |
| Cadena | Cadena |
| eCPI | Cadena |
| reattributions | Cadena |
| reengagements | Cadena |
| Cadena | Cadena |
| roas\_d1 | Cadena |
| roas\_d7 | Cadena |
| roas\_d14 | Cadena |
| roas\_d30 | Cadena |
| roas\_d60 | Cadena |
| roas\_d90 | Cadena |
| retention\_d1 | Cadena |
| retention\_d7 | Cadena |
| retention\_d14 | Cadena |
| retention\_d30 | Cadena |
| retention\_d60 | Cadena |
| retention\_d90 | Cadena |
| revenue\_d1 | Cadena |
| revenue\_d7 | Cadena |
| revenue\_d14 | Cadena |
| revenue\_d30 | Cadena |
| revenue\_d60 | Cadena |
| Cadena | Cadena |
| partner\_cpm | Cadena |
| partner\_ctr | Cadena |
| partner\_cvr | Cadena |
| partner\_clicks | Cadena |
| partner\_cost | Cadena |
| partner\_ipm | Cadena |
| partner\_impressions | Cadena |
| partner\_installs | Cadena |
| partner\_ecpi | Cadena |

Consulta las <Anchor target="_blank" href="/marketers/es/docs/creative-optimization-guide#standard-metrics-and-dimensions">definiciones de las métricas estándar y de las métricas exclusivas de Optimización creativa</Anchor>.

> 📘 **Cadena**
>
> Cuando un anuncio no tiene ninguna vista previa disponible, las columnas `asset_link` y `creative` no se rellenan.

Los siguientes datos **no** están disponibles en Standard Creative ETL:

* Dimensión personalizada
* Cadena
* https://support.appsflyer.com/hc/article_attachments/19284078965009
* Datos de IA (elementos y escenas)
* Datos de retargeting

</Accordion>

<div id="custom-creative-etl" />

<Accordion title="Custom Creative ETL">

Custom Creative ETL te da control total sobre el esquema de tu reporte. Configuras los reportes directamente en la interfaz de usuario de Creative ETL, eligiendo dimensiones, métricas, dimensiones de IA, desgloses por tipo de atribución y eventos in-app. Los datos se entregan a diario en tu destino de Data Locker.

A diferencia del esquema fijo de Standard Creative ETL, Custom Creative ETL te permite crear reportes exactamente como los necesitas:

* **Datos completos de eventos in-app**: incluye hasta 30 eventos in-app por reporte, con submétricas de recuento de eventos, usuarios únicos, ingresos y costo por acción (CPA).
* **Desgloses por tipo de atribución**: crea reportes sobre adquisición de usuarios, retargeting o una vista unificada que combina ambos.
* **Dimensiones de IA**: incluye etiquetas creativas generadas por IA (etiquetas automáticas y dimensiones personalizadas) junto con datos de rendimiento estándar.
* **Configuración de autoservicio**: crea, edita y gestiona reportes directamente en la interfaz de usuario de Creative ETL, sin necesidad de configuración en el backend ni de la intervención de un responsable de éxito del cliente.

#### Antes de comenzar:

Antes de configurar Custom Creative ETL, asegúrate de que esté todo lo siguiente en su lugar:

* Creative Optimization ETL está **disponible con un plan de suscripción Premium de Creative Optimization.** Custom Creative ETL está disponible exclusivamente en el plan Premium. Ponte en contacto con tu representante de AppsFlyer para confirmar tu suscripción.
* **Permisos de administrador.** Solo los usuarios administradores pueden crear, editar o eliminar configuraciones de reportes de ETL.
* **Destino de Data Locker.** Custom Creative ETL entrega los datos a una conexión de Data Locker. Debes tener al menos una conexión ya configurada o crear una como parte de la configuración del reporte (consulta el paso 1 más abajo). Entre los destinos compatibles se incluyen AWS S3, GCS, BigQuery, Snowflake, Azure Blob [beta] y Yandex [beta]. Consulta <Anchor target="_blank" href="/marketers/es/docs/data-locker-cloud-service-setup">Configurar una conexión de Data Locker</Anchor>.

#### Configurar Custom Creative ETL

La configuración de Custom Creative ETL consta de tres pasos: configurar el destino de los datos, definir los detalles del reporte y seleccionar el esquema (las columnas que aparecen en la salida del reporte).

**Para configurar Custom Creative ETL:**

1. En AppsFlyer, ve a **Export** > **Creative ETL**.
2. Selecciona **Creatividad** (bajo **Seleccionar reportes**) en la página de configuración de Data Locker.

##### Paso 1 - Destino

Selecciona o configura la conexión de Data Locker en la que se entregará tu reporte.

3. En la lista desplegable **Data Locker connections**, selecciona una conexión existente.
   * Si aún no tienes una conexión, haz clic en **+ New connection in Data Locker**. Esto abre la página de configuración de Data Locker. Una vez que hayas creado una conexión, vuelve a Creative ETL y selecciónala en el menú desplegable.
   * Puedes seleccionar varias conexiones si quieres que el mismo reporte se entregue a más de un destino.
4. Después de la implementación, regresa al **Inicio de sesión único (SSO)** , haz clic en **Confirmar implementación del certificado**y confirma que ha actualizado el último certificado de AppsFlyer.

##### Paso 2 - Detalles

Define el nombre del reporte y el tipo de reporte.

5. Introduce un **Nombre del reporte**. Este nombre identifica el reporte en la lista de reportes y no se puede cambiar después de guardarlo.

   > 📘 **Cadena**
   >
   > Usa solo letras, números y guiones bajos. El nombre debe tener entre 2 y 80 caracteres.

6. Selecciona un **Tipo de reporte**:

| En esta sección se describe cómo editar la configuración existente de Data Locker para agregar los reportes de Optimización creativa. | Nota |
| --- | --- |
| La adquisición de usuarios | Nuevas instalaciones de usuarios atribuidas a medios pagados |
| Cadena | Actividad de re-engagement y reatribución |
| Unificado | Vista combinada de Adquisición de usuarios y Retargeting en un único reporte |

7. Después de la implementación, regresa al **Inicio de sesión único (SSO)** , haz clic en **Confirmar implementación del certificado**y confirma que ha actualizado el último certificado de AppsFlyer.

##### Paso 3 - Esquema

Selecciona las dimensiones, métricas, dimensiones de IA y eventos in-app que quieres incluir en la salida del reporte.

> 📘 **¿Qué es un esquema?**
>
> Un esquema define las columnas de tu reporte, qué dimensiones (atributos como campaña, geolocalización o tipo de creativo) y métricas (valores de rendimiento como instalaciones, CTR o ROAS) se incluyen y en qué orden. El orden en el que seleccionas los campos en la IU determina el orden de las columnas en el archivo de salida.

9. En **Dimensions**, selecciona las dimensiones de creativo y de campaña que se deben incluir.

   > 📘 **Cadena**
   >
   > Los campos **Event date** (fecha de atribución del evento), **App ID**, **Creative** y **Asset link** son obligatorios y no se pueden eliminar. Dos campos adicionales, `dt` (fecha de partición) y `version` (versión de ejecución para escenarios de backfill), siempre se incluyen en todos los reportes, pero están ocultos en la IU.

10. En **AI Dimensions**, selecciona los campos de etiquetas automáticas o dimensiones personalizadas que quieres incluir. Estos campos los genera el pipeline de análisis creativo con IA de AppsFlyer.

    > 📘 **Nota**
    >
    > Las dimensiones de IA solo se rellenan para los creativos que se han procesado mediante el pipeline de etiquetado con IA. Puede haber un retraso antes de que las etiquetas de IA estén disponibles para los creativos subidos recientemente.

11. En **Métricas**, selecciona los KPI de rendimiento que quieras incluir.
12. En **Eventos in-app**, selecciona los eventos que quieres incluir. Cada evento seleccionado incluye automáticamente cuatro submétricas en el resultado del reporte: recuento de eventos, usuarios únicos, ingresos y CPA.

    > 🚧 **Dos puntos (:)**
    >
    > Puedes incluir un máximo de **30 eventos in-app** por reporte.

13. Haz clic en **Guardar** para activar el reporte.

El reporte ya está configurado. La primera entrega se realizará en la siguiente ejecución diaria.

#### Editar un reporte existente

Puedes modificar un reporte de Creative ETL personalizado existente, incluidos su esquema, su tipo de reporte y su conexión de datos. El nombre del reporte no se puede cambiar después de guardar el reporte.

**Para editar un reporte:**

1. En AppsFlyer, ve a **Export** > **Creative ETL**.
2. En la lista de reportes, haz clic en el icono **Editar** (lápiz) del reporte que quieres modificar.
3. Realiza los cambios en los tres pasos de configuración.
4. Desde la barra superior, abre el menú de cuenta (menú desplegable de dirección de correo electrónico) > **Centro de seguridad**.

> 📘 **Cadena**
>
> Los cambios en el esquema solo se aplican a futuras ejecuciones del reporte. Los archivos entregados anteriormente no se actualizan de forma retroactiva.
>
> Las dimensiones **Fecha del evento**, **ID de la app**, **Enlace del recurso** y **Creativo** son obligatorias y no se pueden eliminar.

También puedes **duplicar** o **eliminar** un reporte con los iconos de acción de cada fila.

> 🚧 **Dos puntos (:)**
>
> Al eliminar un reporte, se eliminan permanentemente la configuración del reporte y todo el historial de ejecuciones asociado. Esta acción no se puede deshacer.

#### Gestión de reportes

La página de Creative ETL muestra todos los reportes de Custom Creative ETL configurados para tu cuenta. Para cada reporte, puedes ver el nombre del reporte, el tipo de reporte y la marca de tiempo de la última entrega correcta.

Las siguientes acciones están disponibles desde los iconos de acción de cada fila de reporte:

* **Ver** (icono de ojo): abre una vista de solo lectura de toda la configuración del reporte.
* **Editar** (icono de lápiz): abre el reporte en modo de edición.
* **Duplicar** (icono de copia), crea una copia de la configuración del reporte.
* **Eliminar** (icono de papelera): elimina permanentemente el reporte y su historial de ejecuciones.

> 📘 **Cadena**
>
> Cada cuenta puede tener un máximo de **5 reportes activos de Custom Creative ETL**.

Si tienes un reporte de Standard Creative ETL configurado mediante Data Locker, aparece un banner de notificación en la parte superior de la página de Creative ETL. Al hacer clic, irás a Data Locker, donde está configurado el reporte estándar.

#### Datos

**Programación de entrega**

Los reportes de Custom Creative ETL se entregan una vez al día. Para monitorear el estado de la entrega, consulta la marca de tiempo de **Última ejecución correcta** en la lista de reportes de Creative ETL.

**Ventana retrospectiva**

Cada entrega diaria incluye datos de una ventana de lookback de 30 días. Cada archivo refleja la ventana móvil completa, no solo el día más reciente. Al cargar datos en tu sistema de BI, sustituye los datos de todas las fechas de la ventana de entrega en lugar de añadir solo las filas del último día.

**Estructura de carpetas**

Los archivos de datos se organizan en tu carpeta de entrega según la configuración que elijas en la configuración de conexión de Data Locker:

* **Unificado (predeterminado):** Todas las aplicaciones se incluyen en archivos de datos unificados. Usa el campo `app_id` a nivel de fila para distinguir entre apps al consumir los datos.
* **Por aplicación:** Los datos se organizan en subcarpetas, una por aplicación.

Consulta <Anchor target="_blank" href="/marketers/es/docs/data-locker-for-marketers#app-segregation">la segregación por aplicación en Data Locker</Anchor> para obtener más información.

#### Referencia del esquema

##### Campos obligatorios

Los siguientes campos siempre se incluyen en todos los reportes de Custom Creative ETL y no se pueden eliminar.

| Cadena | Cadena | Nota |
| --- | --- | --- |
| `Cadena` | Cadena | La fecha a la que se atribuye el evento o la instalación |
| `id_aplicación` | Cadena | ID de la aplicación de AppsFlyer |
| `Data Locker - select Creative.jpg` | Cadena | Nombre de la creatividad |
| `asset_link` | Cadena | URL de la vista previa del recurso creativo. No se rellena cuando no hay ninguna vista previa disponible |
| `dt` | Cadena (AAAA-MM-DD) | Fecha de partición, la fecha en la que los datos del reporte se escribieron en el almacenamiento |
| `version` | Cadena | Identificador de versión de la ejecución; se incrementa en las reejecuciones de backfill del mismo `dt` |

##### Dimensiones

Puedes seleccionar cualquier combinación de las siguientes dimensiones para incluirlas en tu reporte.

| Cadena | Cadena | Nota |
| --- | --- | --- |
| `nombre_aplicación` | Cadena | Nombre de aplicación |
| `anuncio` | Cadena | Nota |
| `id_adset` | Cadena | Retargeting: Primer inicio después del re-engagement o la reatribución. |
| `conjunto de anuncios` | Cadena | Nombre de conjunto de anuncios |
| `id_anuncio` | Cadena | ID de conjunto de anuncios |
| `agencia` | Cadena | Agencia responsable de la colocación del anuncio |
| `campaña única` | Cadena | Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>. |
| `id_campaña` | Cadena | Cadena |
| `channel` | Cadena | Canal dentro de la jerarquía de la fuente de medios |
| `Cadena` | Cadena | Número de días que un creativo ha estado en funcionamiento, calculado a partir de la primera impresión, clic o instalación recibidos por AppsFlyer |
| `Cadena` | Cadena | Agrupa creativos de imagen y vídeo que comparten el mismo tema visual o concepto |
| `creative_type` | Cadena | Tipo de activo (por ejemplo, imagen, vídeo o reproducible) |
| `duration` | Cadena | Duración del vídeo en segundos (para creativos de vídeo) |
| `tarjeta_final` | Cadena | Nombre de la tarjeta final |
| `duración_tarjeta_final` | Cadena | Duración de visualización de la tarjeta final en segundos |
| `orientación_tarjeta_final` | Cadena | Orientación de la tarjeta final (vertical u horizontal) |
| `resolución_tarjeta_final` | Cadena | Resolución de la tarjeta final |
| `end_card_type` | Cadena | Tipo de tarjeta final |
| `visto_por_primera_vez` | Cadena | Fecha en la que se recibieron por primera vez datos de rendimiento del creativo |
| `Cadena` | Cadena (ISO 3166-1 alfa-2) | Código de país |
| `fuente_de_medios` | Cadena | Fuente de medios (ad network) |
| `Cadena` | Cadena | Orientación del creativo (vertical u horizontal) |
| `Identificador de origen` | Cadena | Plataforma del dispositivo (iOS o Android) |
| `Resolución` | Cadena | Data Locker - select Creative.jpg |
| `Cadena` | Cadena | Clasificación del tipo de texto del creativo |

##### Dimensiones de IA

Las dimensiones de IA las genera el motor de análisis de creativos con IA de AppsFlyer e incluyen etiquetas automáticas, etiquetas inteligentes y dimensiones personalizadas.

| Grupo | Cadena | Nota |
| --- | --- | --- |
| Etiquetas automáticas | `at_` | Etiquetas generadas por IA para elementos creativos, escenas, emociones y atributos narrativos. Las etiquetas disponibles son específicas de la cuenta |
| [Próximamente] Smart tags | `cd_ai_label` | Etiquetas inteligentes generadas por IA |
| Cadena | `cd_` | Atributos creativos definidos por el usuario y configurados para tu cuenta |

> 📘 **Cadena**
>
> Las dimensiones de IA solo se completan para los creativos que se han procesado mediante el proceso de etiquetado de IA. Es posible que los creativos subidos recientemente no tengan las etiquetas de IA disponibles de inmediato.

##### Comenzar

| Cadena | Tipo | Nota |
| --- | --- | --- |
| `Cadena` | Entero | Cantidad de impresiones de anuncios |
| `Cadena` | Entero | Cantidad de clics en anuncios |
| `instalaciones` | Entero | Número de instalaciones atribuidas al creativo |
| `reattributions` | Entero | Número de reatribuciones (retargeting) |
| `reengagements` | Entero | Número de re-engagements (retargeting) |
| `costo` | ID del anuncio | Gasto total en anuncios |
| `Cadena` | ID del anuncio | Tasa de clics (clics / impresiones) |
| `Cadena` | ID del anuncio | Tasa de conversión (instalaciones / clics) |
| `Cadena` | ID del anuncio | Instalaciones por mil (instalaciones por cada 1.000 impresiones) |
| `CPM` | ID del anuncio | Costo por mil (costo por cada 1.000 impresiones) |
| `Cadena` | ID del anuncio | Costo efectivo por instalación |
| `roas_d0` | ID del anuncio | Retorno de la inversión publicitaria en el día 0 |
| `roas_d1` | ID del anuncio | Retorno de la inversión publicitaria en el día 1 |
| `roas_d3` | ID del anuncio | Retorno de la inversión publicitaria en el día 3 |
| `roas_d7` | ID del anuncio | Retorno de la inversión publicitaria en el día 7 |
| `roas_d14` | ID del anuncio | Retorno de la inversión publicitaria en el día 14 |
| `roas_d30` | ID del anuncio | Retorno de la inversión publicitaria en el día 30 |
| `roas_d60` | ID del anuncio | Retorno del gasto en anuncios el día 60 |
| `roas_d90` | ID del anuncio | Retorno del gasto en anuncios el día 90 |
| `retention_d0` | ID del anuncio | Tasa de retención del día 0 |
| `retention_d1` | ID del anuncio | Tasa de retención del día 1 |
| `retention_d3` | ID del anuncio | Tasa de retención del día 3 |
| `retention_d7` | ID del anuncio | Tasa de retención del día 7 |
| `retention_d14` | ID del anuncio | Tasa de retención del día 14 |
| `retention_d30` | ID del anuncio | Tasa de retención del día 30 |
| `retention_d60` | ID del anuncio | Tasa de retención del día 60 |
| `retention_d90` | ID del anuncio | Tasa de retención del día 90 |
| `unique_users_0` | Entero | Usuarios únicos el día 0 |
| `unique_users_1` | Entero | Usuarios únicos el día 1 |
| `unique_users_3` | Entero | Usuarios únicos el día 3 |
| `unique_users_7` | Entero | Usuarios únicos el día 7 |
| `unique_users_14` | Entero | Usuarios únicos el día 14 |
| `unique_users_30` | Entero | Usuarios únicos el día 30 |
| `unique_users_60` | Entero | Usuarios únicos en el día 60 |
| `usuarios_únicos_90` | Entero | Usuarios únicos en el día 90 |
| `Cadena` | ID del anuncio | Ingresos totales en el día 0 |
| `revenue_d1` | ID del anuncio | Ingresos totales en el día 1 |
| `Cadena` | ID del anuncio | Ingresos totales en el día 3 |
| `revenue_d7` | ID del anuncio | Ingresos totales en el día 7 |
| `revenue_d14` | ID del anuncio | Ingresos totales en el día 14 |
| `revenue_d30` | ID del anuncio | Ingresos totales en el día 30 |
| `revenue_d60` | ID del anuncio | Ingresos totales en el día 60 |
| `Revenue_d90` | ID del anuncio | Ingresos totales en el día 90 |
| `ingresos_por_anuncios_d0` | ID del anuncio | Ingresos por anuncios en el día 0 |
| `ingresos_por_anuncios_d1` | ID del anuncio | Ingresos por anuncios en el día 1 |
| `ingresos_por_anuncios_d3` | ID del anuncio | Ingresos por anuncios en el día 3 |
| `ingresos_por_anuncios_d7` | ID del anuncio | Ingresos por anuncios en el día 7 |
| `ingresos_por_anuncios_d14` | ID del anuncio | Ingresos por anuncios en el día 14 |
| `Cadena` | ID del anuncio | Ingresos por anuncios en el día 30 |
| `Cadena` | ID del anuncio | Ingresos por anuncios en el día 60 |
| `Página 1` | ID del anuncio | Ingresos por anuncios en el día 90 |
| `partner_impressions` | Entero | Impresiones según las reporta la fuente de medios |
| `partner_clicks` | Entero | Clics según lo reportado por la fuente de medios |
| `partner_installs` | Entero | Instalaciones según lo reportado por la fuente de medios |
| `partner_cost` | ID del anuncio | Costo según lo reportado por la fuente de medios |
| `partner_cpm` | ID del anuncio | CPM según lo reportado por la fuente de medios |
| `partner_ctr` | ID del anuncio | CTR |
| `partner_cvr` | ID del anuncio | CVR según lo reportado por la fuente de medios |
| `partner_ipm` | ID del anuncio | IPM según lo reportado por la fuente de medios |
| `partner_ecpi` | ID del anuncio | eCPI según lo reportado por la fuente de medios |
| `partner_video_viewed_2s` | Entero | Visualizaciones de vídeo a los 2 segundos (reportadas por el partner) |
| `partner_video_viewed_3s` | Entero | Visualizaciones de vídeo a los 3 segundos (reportadas por el partner) |
| `partner_video_viewed_6s` | Entero | Visualizaciones de vídeo a los 6 segundos (reportadas por el partner) |
| `partner_engaged_views_6s` | Entero | Visualizaciones comprometidas a los 6 segundos (reportadas por el partner) |
| `partner_engaged_views_15s` | Entero | Visualizaciones comprometidas a los 15 segundos (reportadas por el partner) |
| `partner_video_started` | Entero | Inicios de vídeo (reportados por el partner) |
| `partner_video_25p_views` | Entero | Vídeo reproducido hasta el 25% (reportado por el partner) |
| `partner_video_50p_views` | Entero | Vídeo reproducido hasta el 50% (reportado por el partner) |
| `partner_video_75p_views` | Entero | Vídeo reproducido hasta el 75% (reportado por el partner) |
| `partner_video_completions` | Entero | Finalizaciones de vídeo (reportadas por el partner) |

##### Eventos in-app

Los eventos in-app aparecen en el reporte como columnas de métricas con el formato `{event_name}.{sub_metric}`. Cuando seleccionas un evento, las cuatro submétricas se incluyen automáticamente. Por ejemplo, al seleccionar `af_purchase` se generan las siguientes columnas: `af_purchase.event_count`, `af_purchase.unique_users`, `af_purchase.revenue` y `af_purchase.cpa`.

| Submétrica | Nota |
| --- | --- |
| `recuento_eventos` | Número total de veces que se activó el evento |
| `usuarios_únicos` | Cantidad de usuarios únicos que activaron el evento |
| `Cadena` | Ingresos totales atribuidos al evento |
| `Cadena` | Costo por acción (costo/recuento de eventos) |

Límites:

* Máximo de **30 eventos in-app** por reporte.
* Los eventos disponibles son específicos de la cuenta y reflejan los eventos que tus apps envían activamente a AppsFlyer.

#### Limitaciones

| Limitación | Nota |
| --- | --- |
| Reportes por cuenta | Máximo de 5 reportes activos por cuenta |
| https://support.appsflyer.com/hc/article_attachments/19276693230353 | Máximo de 30 eventos por reporte |
| Columnas totales por reporte | Máximo de 150 columnas (dimensiones + métricas + submétricas de eventos in-app combinadas) |
| Los siguientes datos no están disponibles: | Los datos están disponibles durante una ventana de lookback de 30 días. Los datos históricos fuera de esta ventana no están disponibles. |
| Frecuencia de entrega | Una vez al día. La entrega intradía no es compatible |
| Disponibilidad de dimensiones de IA | Las dimensiones de IA se completan solo para los creativos procesados por el flujo de etiquetado de IA. Los creativos subidos recientemente pueden tener un retraso |
| Métricas personalizadas | Aún no se admite |
| Acciones de conversión (web) | Aún no se admite |
| Selección de app | Todas las aplicaciones de tu cuenta se incluyen en cada reporte. Está previsto añadir la opción de filtrar por aplicaciones específicas en una versión futura |

</Accordion>

## Preguntas frecuentes

Una lista de preguntas frecuentes sobre los reportes de ETL.

<div id="whats-the-difference-between-standard-creative-etl-and-custom-creative-etl" />

<Accordion title="¿Cuál es la diferencia entre Standard Creative ETL y Creative ETL personalizado?">

**Standard Creative ETL** se configura en la página Select reports de Data Locker y entrega un conjunto fijo de campos (esquema) una vez al día. No admite eventos in-app, retargeting ni desgloses unificados, ni dimensiones de IA.

**Creative ETL personalizado** se configura directamente en la interfaz de usuario de AppsFlyer con un conjunto de campos totalmente personalizable. Puedes incluir hasta 30 eventos in-app, dimensiones de IA y desgloses de adquisición de usuarios/retargeting/unificado, sin necesidad de configuración del backend ni de la intervención de un customer success manager.

</Accordion>

<div id="can-i-run-both-standard-creative-etl-and-custom-creative-etl-at-the-same-time" />

<Accordion title="¿Puedo ejecutar Standard Creative ETL y Creative ETL personalizado al mismo tiempo?">

Sí. Ambos pueden ejecutarse en paralelo. Si tienes un reporte de Standard Creative ETL activo, aparece un banner de notificación en la página de Creative ETL con un enlace a tu configuración de Data Locker.

</Accordion>

<div id="can-i-have-multiple-custom-creative-etl-reports-with-different-report-types" />

<Accordion title="¿Puedo tener varios reportes de Creative ETL personalizado con distintos tipos de reporte?">

Sí. Cada reporte se configura con un único tipo de reporte (Adquisición de usuarios, Retargeting o Unificado), y puedes crear hasta 5 reportes por cuenta.

</Accordion>

<div id="how-do-i-add-new-inapp-events-to-an-existing-custom-creative-etl-report" />

<Accordion title="¿Cómo añado nuevos eventos in-app a un reporte existente de Creative ETL personalizado?">

Ve a **Export** > **Creative ETL**, haz clic en el icono **Edit** del reporte, ve al **Step 3 (Schema)** y añade los nuevos eventos. Los cambios entran en vigor en la siguiente entrega diaria.

</Accordion>

<div id="what-happens-if-a-report-runs-more-than-once-on-the-same-day" />

<Accordion title="¿Qué ocurre si un reporte se ejecuta más de una vez el mismo día?">

Si un reporte se vuelve a ejecutar (normalmente durante un backfill), cada ejecución recibe un valor de `version` incrementado. Usa siempre la versión más alta disponible para una partición `dt` determinada.

</Accordion>

> 📄 **Véase también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/creative-optimization-guide">Guía de Optimización Creativa</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/data-locker-advertiser-reports">Reportes de anunciantes de Data Locker</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/data-locker-cloud-service-setup">Configuración de Data Locker</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/set-up-and-use-roi360-cost-etl-reports">Configurar y utilizar reportes de Cost ETL de ROI360</Anchor>

<div data-zendesk-anchors="about-creative-optimization-etl-reporting=acerca-del-etl-de-optimizaci%C3%B3n-creativa h_01KW7A0CWMCFQA7K6YE909BVW4=acerca-del-etl-de-optimizaci%C3%B3n-creativa h_01KW7A0CWMH2SCPQ917TKASCC7=standard-creative-etl h_01KW7A0CWMJDR014M6JSA2HBHY=cadena get-started=comienza h_01KW7A0CWM2SPE4RYFJKZBDKJG=comienza edit-data-locker-configuration=edici%C3%B3n-de-la-configuraci%C3%B3n-de-data-locker h_01KW7A0CWMAR0E52M7T6PXMCKT=edici%C3%B3n-de-la-configuraci%C3%B3n-de-data-locker data-freshness=actualizaci%C3%B3n-de-los-datos h_01KW7A0CWM9K9J7X64S14TX2AE=actualizaci%C3%B3n-de-los-datos available-data=datos-disponibles h_01KW7A0CWM1JYVQXKBDH06X1BA=datos-disponibles h_01KW7A0CWMT7Q8BFTB8WAT7M0W=cadena-1 h_01KW7A0CWNZMPD7RSX41VNGSCF=custom-creative-etl before-you-begin=antes-de-comenzar h_01KW7A0CWNK0R6XAB37E5ZP7KG=antes-de-comenzar set-up-custom-creative-etl=configurar-custom-creative-etl h_01KW7A0CWN2DZFZP3YK23ZW9EH=configurar-custom-creative-etl h_01KW7A0CWNQJT83A9KAE8E7XHD=paso-1---destino h_01KW7A0CWNH69H47EF7FAV1FRF=paso-2---detalles h_01KW7A0CWN0M4ZFRPQ7BN9TRTC=cadena-2 h_01KW7A0CWNG5PVQNC8ED1RXV28=paso-3---esquema h_01KW7A0CWNER5KD46VJHE1X0VH=qu%C3%A9-es-un-esquema h_01KW7A0CWNJYPD5TXZ301PMF7S=cadena-3 h_01KW7A0CWN4NWNP10TAYD26GCQ=nota h_01KW7A0CWNFWY5BYGVPPXTYQ1X=dos-puntos- edit-an-existing-report=editar-un-reporte-existente h_01KW7A0CWNVJJTVW1MP0V25ZC5=editar-un-reporte-existente h_01KW7A0CWNFZCW1NNBY2H0BSDS=cadena-4 h_01KW7A0CWNY50EV4EDS3BWGP6S=dos-puntos--1 report-management=gesti%C3%B3n-de-reportes h_01KW7A0CWNRKGS9TJ4Y2H7JD5S=gesti%C3%B3n-de-reportes h_01KW7A0CWNN3MN0S8Z563BYQ97=cadena-5 data-delivery=datos h_01KW7A0CWNS62EYWZ8V41E7RRY=datos schema-reference=referencia-del-esquema h_01KW7A0CWNWM3JTMEFF8B3SPXG=referencia-del-esquema h_01KW7A0CWNP32RKD6YW1GNPNEE=campos-obligatorios h_01KW7A0CWNJRT87NYJQ19YHSSG=dimensiones h_01KW7A0CWNTSGC4BPEBME4WWNC=dimensiones-de-ia h_01KW7A0CWNNA03BG2BAQ4MGGMX=cadena-6 h_01KW7A0CWN6H39Q9D7SX2TFXAF=comenzar h_01KW7A0CWP4JQSDP8E2BQESE2A=eventos-in-app limitations=limitaciones h_01KW7A0CWPJ8W3ZE2JZ9YTZFQF=limitaciones faq=preguntas-frecuentes h_01KW9K4YXMJ14TX6FMGYY4811K=preguntas-frecuentes h_01KW9K4YXM8E6ZF226DTTVZHK8=whats-the-difference-between-standard-creative-etl-and-custom-creative-etl h_01KW9K4YXMNDT73BPAV1CC5JZ5=can-i-run-both-standard-creative-etl-and-custom-creative-etl-at-the-same-time h_01KW9K4YXM3F3W45MTNDHS9DM9=can-i-have-multiple-custom-creative-etl-reports-with-different-report-types h_01KW9K4YXMVH2NSM46S63EVX01=how-do-i-add-new-inapp-events-to-an-existing-custom-creative-etl-report h_01KW9K4YXMDQZHF5TZGQE1NR0P=what-happens-if-a-report-runs-more-than-once-on-the-same-day h_01KW7A0CWP90HES8D1S2A1PF6X=v%C3%A9ase-tambi%C3%A9n" />
