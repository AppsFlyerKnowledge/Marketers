---
title: Reportes de ROI360 Revenue ETL en Data Locker
metadata:
  keywords:
    - Marketers
    - revenue
    - etl
    - revenueetl
    - revenue etl
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2023-06-25T16:57:02Z'
  edited_at: '2026-08-12T11:49:01Z'
  id: 16464765619985
  locale: es
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/es/articles/16464765619985
---
> **En resumen:** Obtén información sobre los reportes de ingresos de ROI360, sus fuentes, cómo se generan, cuándo están disponibles y cómo puedes acceder a ellos. Para obtener más información sobre los campos y la estructura de los reportes, descarga la muestra de datos.

## Revenue ETL

Con ROI360 Revenue ETL, tus datos de ingresos se envían a través de Data Locker al almacenamiento en la nube para cargarlos en tus sistemas de BI.

La siguiente tabla muestra los reportes de ingresos disponibles. **Nota**: Con la excepción de los reportes de ingresos por publicidad heredados [versión única], todos los reportes requieren una suscripción al paquete ROI360 Advanced.

| Reporte | Tipo de integración | Descripción | Actualización de datos |
| --- | --- | --- | --- |
| [Ingresos por publicidad [versionados]](/docs/revenue-etl-reports#ad-revenue-single-version-report-device-level):<ul><li>Ingresos por publicidad atribuidos [versión única x+1]</li><li>Ingresos por publicidad orgánicos [versión única x+1]</li><li>Ingresos por publicidad de retargeting [versión única x+1]</li></ul> | <ul><li>Nivel de impresión (por SDK)</li><li>Nivel de dispositivo (por API S2S)</li><li>Nivel de impresión (por SDK) con nivel de dispositivo (por API S2S)</li></ul> | <ul><li>Contiene datos de ingresos por publicidad.</li><li>Versión única (sin más actualizaciones de datos).</li><li>Si hay integraciones de API y SDK, los reportes solo contienen datos de API.</li></ul> | <ul><li>Diariamente (disponible el día x+1) <Anchor target="_blank" href="/marketers/es/docs/roi360-guide-ad-revenue-attribution#data-freshness">Aprender más</Anchor></li></ul> |
| [Ingresos por publicidad antigua [versión única]](/docs/revenue-etl-reports#ad-revenue-single-version-report-device-level):<ul><li>Ingresos por publicidad atribuidos [versionado]</li><li>Ingresos orgánicos por publicidad [versionado]</li><li>Ingresos por publicidad de retargeting [versionado]</li></ul> | <ul><li>Nivel de impresión (por SDK)</li><li>Nivel de dispositivo (por API S2S)</li><li>Nivel de impresión (por SDK) con nivel de dispositivo (por API S2S)</li></ul> | <ul><li>Contiene los datos de ingresos por publicidad más actualizados.</li><li><Anchor target="_blank" href="/marketers/es/docs/data-locker-for-marketers#version-folders">Versionado</Anchor></li></ul> | <ul><li>Intradía. <Anchor target="_blank" href="/marketers/es/docs/roi360-guide-ad-revenue-attribution#data-freshness">Aprender más</Anchor></li><li>Los datos se actualizan entre 4 horas y 14 días después de la impresión del anuncio.</li></ul> |
| [Ingresos por publicidad atribuidos [nivel de impresión del SDK]](/docs/revenue-etl-reports#impression-level-report) | <ul><li>Nivel de impresión (por SDK)</li><li>Nivel de impresión (por SDK) con nivel de dispositivo (por API S2S)</li></ul> | <ul><li>Contiene datos del SDK de ingresos por publicidad.</li><li>Proporciona la máxima actualización y granularidad de los datos.</li></ul> | Cada hora. <Anchor target="_blank" href="/marketers/es/docs/roi360-guide-ad-revenue-attribution#data-freshness">Aprender más</Anchor> |
| [Ingresos de tiendas a nivel de transacción](/docs/revenue-etl-reports#transactionlevel-stores-revenue-report) | Integración de ingresos por suscripción e IAP de ROI360 | <ul><li>Contiene raw data de compras in-app y suscripciones validados por ROI360 a nivel de transacción.</li><li>Proporciona la máxima frescura y granularidad de los datos.</li><li>Incluye datos e ingresos netos únicos relacionados con la monetización del ROI360.</li></ul> | Por hora |
| [Ingresos de tiendas a nivel de dispositivo [versionados]](/docs/revenue-etl-reports#devicelevel-stores-revenue-report) | Integración de ingresos por suscripción e IAP de ROI360 | <ul><li>Contiene raw data de compras in-app y raw data de suscripciones validados por ROI360 a nivel de dispositivo.</li><li>Incluye datos únicos de ingresos netos de ROI360.</li></ul> | Cada 8 horas |

## Reportes

Los detalles sobre los diferentes reportes (cómo funcionan, cómo suscribirse a ellos y cómo acceder a ellos) se encuentran en las secciones siguientes.

<div id="ad-revenue-single-version-report-device-level" />

<Accordion title="[Heredado] Ingresos por publicidad (versión única)">

El reporte muestra una versión única de los datos de ingresos por publicidad de un día agregados al nivel del dispositivo. El reporte está disponible el día X+1 (X es el día en que se produjo el evento de ingresos).

**Nota:** Los reportes separados proporcionan los datos de ingresos orgánicos y de retargeting. Estos reportes son idénticos en estructura y disponibilidad.

<span id="download-the-report-data-sample"></span>Descarga el ejemplo de datos del reporte de la versión única de ingresos por publicidad.

#### Fuentes de datos

Según el tipo de integración de partners que genere ingresos por publicidad, los datos del reporte pueden proceder de una de las siguientes maneras:

* **SDK**: Cargas útiles de datos a nivel de impresión enviadas por el conector SDK de ingresos por publicidad de ROI360 Ad.
* **S2S:** Reportes a nivel de dispositivo obtenidos mediante una solicitud de API de los partners (redes de mediación o monetización).

Para obtener información sobre cómo configurar el tipo de integración, consulta: Conéctate a partners integrados en los ingresos por publicidad.

#### Flujo de datos

1. **Ingestión de datos:** El reporte puede provenir del conector del SDK de ingresos por publicidad o de la solicitud de API S2S (consulta la sección anterior).
2. **Procesamiento de datos**: Los ingresos por publicidad de ROI360 de AppsFlyer realizan lo siguiente:

   1. Normalización de datos
   2. Atribución a la fuente de instalación y enriquecimiento de datos,
   3. Generación de eventos de ingresos por publicidad
   4. Los eventos se agregan a nivel de dispositivo

   **Nota:** Un reporte puede tener más de una agregación a nivel de dispositivo para el mismo dispositivo. Esto puede deberse a que la agregación a nivel de dispositivo se basa en dimensiones relacionadas con la monetización, como la red de monetización, la ubicación y el tipo de anuncio. Por ejemplo, si la aplicación muestra anuncios en dos ubicaciones diferentes, los eventos de ingresos de cada ubicación se agregan por separado en el nivel del dispositivo.
3. **Entrega de datos**: Los datos a nivel de dispositivo se escriben en la versión única del reporte.

#### ¿Cuándo están disponibles los datos del reporte?

| Tipo de integración | Día de la versión (X = día de aparición del evento de ingresos) | Versión disponible en | La versión incluye los eventos de ingresos que se producen entre |
| --- | --- | --- | --- |
| SDK | Día X+1 | 20:00 | 00:00 — 24:00 |
| SDK + S2S | Día X+1 | 17:00 | 00:00 — 24:00 |

#### ¿Cómo suscribirse al reporte?

1. En AppsFlyer, en el menú lateral, selecciona **Reporte >** Data Locker.
2. En el panel de **contenido de Data Locker**, desplázate hacia abajo hasta el mosaico **ROI360 RevenueETL**.
3. Selecciona **Ingresos atribuidos [versión única].**

**Nota:** También puedes seleccionar el mismo reporte para el retargeting y el orgánico (retargeting o ingresos por publicidad orgánica [versión única]).

#### ¿Cómo acceder al reporte de tu bucket?

La ruta al reporte consta de la siguiente jerarquía de carpetas:

Con el siguiente formato: `<bucket-name>/t=attributed_ad_revenue/dt=<dt=yyyy-mm-dd>/h=23/`

#### Jerarquía de carpetas de reportes

Un ejemplo de la jerarquía de carpetas del reporte de una sola versión de ingresos por publicidad atribuidos en el grupo de anunciantes:

```
bucket
|
└── t=attributed_ad_revenue
    |
    ├── dt=2023-06-02
    |   |
    |   └── h=23
    |        |
    |        ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |        |
    |        ├── part-00001-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |        │
    |        └── part-00002-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |
    ├── dt=2023-06-01
    |   |
    |   └── h=23
    |        |
    |        ├── part-00000-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        |
    |        ├── part-00001-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        │
    |        └── part-00002-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |
    ├── dt=2023-05-31
    |   |
    .   . 
    .   .
```

**Leyenda:**

* **dt**: Fecha en la que se produjeron los eventos de ingresos incluidos en el reporte.
* **t:** tipo de reporte.
* **h:** hora de creación de una sola versión

</Accordion>

<div id="ad-revenue-versioned-report-device-level" />

<Accordion title="Ingresos por publicidad (versionado)">

El reporte muestra varias versiones de los datos de ingresos de una sola fecha. Por ejemplo, los ingresos del 21 de junio se reportan el 21 de junio, el 22 de junio, el 23 de junio, el 24 de junio, el 28 de junio y el 5 de julio.

El propósito de recopilar varias versiones del mismo día es capturar las variaciones en el cálculo de los ingresos que surgen de condiciones que dependen del tiempo. Por ejemplo, las impresiones que generaron ingresos en tiempo real pueden tener un valor diferente un día después.

**Nota:** Los reportes separados proporcionan los datos de ingresos orgánicos y de retargeting. Estos reportes son idénticos en estructura y disponibilidad.

[Descarga el ejemplo de datos del reporte versionado de ingresos por anuncios](https://docs.google.com/spreadsheets/d/e/2PACX-1vQek1x3rYnYQq3jctSz5hnWG_Nk_LQk2ixMTQFVMb8K6w-UmeNKvKOif3-nudAyIqp9tyuoq9R-FhVz/pub?output=csv).

#### Fuentes de datos

Según el tipo de integración de partners que genere ingresos por publicidad, los datos del reporte pueden proceder de una de las siguientes maneras:

* **SDK**: Cargas útiles de datos a nivel de impresión enviadas por el conector SDK de ingresos por publicidad de ROI360 Ad.
* **S2S:** Reportes a nivel de dispositivo obtenidos mediante una solicitud de API de los partners (redes de mediación o monetización).
* **S2S + SDK:** Cargas útiles que se originan tanto en SDK como en S2S.

Para obtener información sobre cómo configurar el tipo de integración, consulta: Conéctate a partners integrados en los ingresos por publicidad.

#### Flujo de datos

1. **Ingestión de datos:** El reporte puede provenir de la solicitud de API de S2S o del SDK (consulta la sección anterior).
2. **Procesamiento de datos:** Los ingresos por publicidad de ROI360 de AppsFlyer realizan lo siguiente:

   1. Normalización de datos
   2. Atribución a la fuente de instalación y enriquecimiento de datos,
   3. Generación de eventos de ingresos por publicidad
   4. Los eventos se agregan a nivel de dispositivo

   **Nota:** Un reporte puede tener más de una agregación a nivel de dispositivo para el mismo dispositivo. Esto puede deberse a que la agregación a nivel de dispositivo se basa en dimensiones relacionadas con la monetización, como la red de monetización, la ubicación y el tipo de anuncio. Por ejemplo, si la aplicación muestra anuncios en dos ubicaciones diferentes, los eventos de ingresos de cada ubicación se agregan por separado en el nivel del dispositivo.
3. **Entrega de datos**: Los datos a nivel de dispositivo se escriben en varias versiones de reportes de acuerdo con un cronograma predeterminado (que se especifica a continuación).

#### ¿Cuándo están disponibles las versiones del reporte?

La tabla que se proporciona a continuación describe los programas de generación para las versiones S2S y SDK. Los clientes que se beneficien de ROI360 Ad Revenue Freshness to Accuracy recibirán ambas versiones, lo que garantiza una precisión óptima y una información actualizada.

**Nota:** Es posible que no se creen algunas versiones originadas en S2S. Si los datos de los partners no cambiaron desde la última versión, NO se generará una nueva versión.

| Tipo de integración | Día de la versión (X = día de aparición del evento de ingresos) | Versión disponible en | La versión incluye los eventos de ingresos que se producen entre |
| --- | --- | --- | --- |
| SDK | Día X | 03:00-04:00 | 00:00 — 24:00 |
| SDK | Día X | 07:00-08:00 | 00:00 — 07:00 |
| SDK | Día X | 11:00-12:00 | 00:00 — 11:00 |
| SDK | Día X | 15:00-16:00 | 00:00 — 15:00 |
| SDK | Día X | 19:00-20:00 | 00:00 — 19:00 |
| SDK | Día X | 23:00-24:00 | 00:00 — 23:00 |
| SDK | Día X+1 | 04:00-05:00 | 00:00 — 24:00 |
| S2S | Día X+1 | 10:00-11:00 | 00:00 — 24:00 |
| S2S | Día X+1 | 12:00-13:00 | 00:00 — 24:00 |
| S2S | Día X+2 | 00:00-01:00 | 00:00 — 24:00 |
| S2S | Día X+2 | 13:00-14:00 | 00:00 — 24:00 |
| S2S | Día X+3 | 06:00-07:00 | 00:00 — 24:00 |
| S2S | Día X+7 | 08:00-09:00 | 00:00 — 24:00 |
| S2S | Día X+14 | 11:00-12:00 | 00:00 — 24:00 |
| SDK + S2S | Todas las versiones de SDK y S2S anteriores |  |  |

#### ¿Cómo suscribirse al reporte?

1. En AppsFlyer, en el menú lateral, selecciona **Reporte >** Data Locker.
2. En el panel de **contenido de Data Locker**, desplázate hacia abajo hasta el mosaico **ROI360 RevenueETL**.
3. Selecciona **Ingresos por publicidad atribuidos [versionados]**.

**Nota:** También puedes seleccionar el mismo reporte para el retargeting y el orgánico (retargeting o ingresos por publicidad orgánica [versionados]).

#### ¿Cómo acceder al reporte de tu bucket?

La ruta al reporte consta de la siguiente jerarquía de carpetas:

`<bucket-name>/t=attributed_ad_revenue_v2/dt=<dt=yyyy-mm-dd>/version=<9999999>/`

#### Jerarquía de carpetas de reportes

Un ejemplo de un árbol de reportes en el bucket de anunciantes:

```
bucket
|
└── t=attributed_ad_revenue_v2
    |
    └── dt=2023-06-01
        |
        ├── version=1685588879
        |   |
        │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
        |   |
        │   ├── part-00001-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
        |   │
        |   └── part-00002-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
        |
        ├── version=1685603326
        |   |
        │   ├── part-00000-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
        |   |
        │   ├── part-00001-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
        |   │
        |   └── part-00002-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
        |
        ├── version=1685617877
        .
                .
                .
```

* **Leyenda:**
  * **t:** Tipo de reporte
  * **dt**: Fecha en la que se produjeron los eventos de ingresos incluidos en el reporte.
  * **versión:** El nombre de la versión es la marca temporal de la fecha y hora de creación de la versión, por ejemplo, **version=1685588879**.
* El origen de la versión, ya sea S2S o SDK, se puede conocer en el momento de la creación de la versión. Las primeras versiones del SDK se originan en el SDK. Los demás son S2S.

| Tipo de integración | Día de la versión (X = día de aparición del evento de ingresos) | Versión disponible en | La versión incluye los eventos de ingresos que se producen entre |
| --- | --- | --- | --- |
| SDK | Día X | 03:00-04:00 | 00:00 — 24:00 |
| SDK | Día X | 07:00-08:00 | 00:00 — 07:00 |
| SDK | Día X | 11:00-12:00 | 00:00 — 11:00 |
| SDK | Día X | 15:00-16:00 | 00:00 — 15:00 |
| SDK | Día X | 19:00-20:00 | 00:00 — 19:00 |
| SDK | Día X | 23:00-24:00 | 00:00 — 23:00 |
| SDK | Día X+1 | 04:00-05:00 | 00:00 — 24:00 |
| S2S | Día X+1 | 10:00-11:00 | 00:00 — 24:00 |
| S2S | Día X+1 | 18:00-19:00 | 00:00 — 24:00 |
| S2S | Día X+2 | 00:00-01:00 | 00:00 — 24:00 |
| S2S | Día X+2 | 13:00-14:00 | 00:00 — 24:00 |
| S2S | Día X+3 | 06:00-07:00 | 00:00 — 24:00 |
| S2S | Día X+7 | 08:00-09:00 | 00:00 — 24:00 |
| S2S | Día X+14 | 11:00-12:00 | 00:00 — 24:00 |

</Accordion>

<div id="impression-level-report" />

<Accordion title="Ingresos por publicidad [nivel de impresión del SDK]">

El reporte muestra los datos a nivel de impresión divididos en carpetas por hora de aparición. Cada carpeta **solo contiene las impresiones que se produjeron durante esa hora**.

[Descarga el ejemplo de datos del reporte sobre el nivel de impresión de ingresos por publicidad](https://docs.google.com/spreadsheets/d/e/2PACX-1vR5zVxFGaCMNZMbCCYPae6f7MmbtelxrqXb-A5DBENuyTFCN4deRfICvbL0_dNeYVipojmAeUdrGbKI/pub?output=csv)

#### Fuente de datos

Los datos del reporte provienen de datos a nivel de impresión enviados por el conector SDK de ingresos por publicidad de ROI360 y requieren una integración tipo SDK.

Para obtener información sobre cómo configurar el tipo de integración, consulta: Conéctate a partners integrados en los ingresos por publicidad.

#### Flujo de datos

1. **Ingestión de datos:** Los datos del reporte provienen de datos a nivel de impresión enviados por el conector SDK de ingresos por publicidad de ROI360 y requieren una integración tipo SDK.
2. **Procesamiento de datos**: Los ingresos por publicidad de ROI360 de AppsFlyer realizan lo siguiente:
   1. Normalización de datos
   2. Atribución a la fuente de instalación y enriquecimiento de datos,
   3. Generación de eventos de ingresos por publicidad a nivel de impresión.
3. **Entrega de datos**: Los eventos de impresión se escriben en archivos divididos por carpetas según la hora de aparición. Cada carpeta solo contiene las impresiones que se produjeron durante esa hora.

#### ¿Cuándo están disponibles los datos del reporte?

| Tipo de integración | Día de la versión (X = día de aparición del evento de ingresos) | Versión disponible en |
| --- | --- | --- |
| SDK | Día X | Al final de cada hora reportada |

#### ¿Cómo suscribirse al reporte?

1. En AppsFlyer, en el menú lateral, selecciona **Reporte >** Data Locker.
2. En el panel de **contenido de Data Locker**, desplázate hacia abajo hasta el mosaico **ROI360 RevenueETL**.
3. Selecciona **Ingresos por publicidad [nivel de impresión del SDK]**.

#### ¿Cómo acceder al reporte de tu bucket?

La ruta al reporte consta de la siguiente jerarquía de carpetas:

`<bucket-name>/t=attributed_adrevenue_sdk_impression_level/dt=<dt=yyyy-mm-dd>/h=<hh>`

#### Jerarquía de carpetas de reportes

Un ejemplo de un árbol de reportes en el bucket de anunciantes:

```
bucket
|
└── t=attributed_adrevenue_sdk_impression_level/
    |
    ├── dt=2023-06-01
    |   |
    |   ├── h=0
    |   |   |
    |   │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   ├── h=1
    |   |   |
    |   │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   ├── h=2
    |   .   |
    |   .   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   .   .
    |   ├── h=23
    |   |   |
    |   │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   └── h=24
    |       |
    |       └── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |    
    ├── dt=2023-06-02
    |   |  
    |   ├── h=0
        .   .
        .   .
```

**Leyenda:**

* **t:** Tipo de reporte
* **dt**: Fecha en la que se produjeron los eventos de ingresos incluidos en el reporte.
* **h**: Carpeta horaria que contiene el archivo CSV con las impresiones que se produjeron durante esa hora específica.

</Accordion>

<div id="transactionlevel-stores-revenue-report" />

<Accordion title="Ingresos de tiendas a nivel de transacción">

Este reporte presenta raw data diarios a nivel de transacción, divididos en carpetas por horas que contienen solo las transacciones relevantes para esa hora.

[Descarga el ejemplo de datos del reporte de tiendas a nivel de transacciones](https://docs.google.com/spreadsheets/d/e/2PACX-1vRGlRSg_Xrp2EsqK2uaisjhlqeSuZsypqKqSSRGX3AQBwBLlNdG_5LOOKCM9f9gCcLguMQgQwT--Dz7/pub?output=csv)

#### Fuentes de datos

Los datos del reporte provienen de las transacciones recopiladas a través del conector de compra del SDK ROI360 y de las notificaciones de almacenamiento de servidor a servidor.

#### Flujo de datos

1. Los datos del reporte provienen de las transacciones recopiladas a través de las cargas útiles del conector de compras del SDK ROI360 o de las notificaciones de las tiendas S2S.
2. El ROI360 de AppsFlyer mediante VIAP/subscripciones procesa los datos, los atribuye y crea eventos y valores a nivel de transacción.
3. Los eventos a nivel de transacción se escriben en el reporte y se dividen en carpetas por hora.

#### ¿Cuándo están disponibles los datos del reporte?

| Día de la versión (X = día de aparición del evento de ingresos) | Versión disponible en |
| --- | --- |
| Día X | Al final de cada hora reportada |

#### ¿Cómo suscribirse al reporte?

1. En AppsFlyer, en el menú lateral, selecciona **Reporte >** Data Locker.
2. En el panel de **contenido de Data Locker**, desplázate hacia abajo hasta el mosaico **ROI360 RevenueETL**.
3. Selecciona el **reporte de ingresos de tiendas a nivel de transacción**.

#### ¿Cómo acceder al reporte de tu bucket?

La ruta al reporte consta de la siguiente jerarquía de carpetas:

`<bucket-name>/t=stores_rawdata/dt=<dt=yyyy-mm-dd>/h=<hh>`

#### Jerarquía de carpetas de reportes

Un ejemplo de un árbol de reportes en el bucket de anunciantes:

```
bucket
|
└── t=stores_rawdata
    |
    ├── dt=2023-06-01
    |   |
    |   ├── h=0
    |   |   |
    |   │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   ├── h=1
    |   |   |
    |   │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   ├── h=2
    |   .   |
    |   .   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   .   .
    |   ├── h=23
    |   |   |
    |   │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   └── h=24
    |       |
    |       └── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |    
    ├── dt=2023-06-02
    |   |  
    |   ├── h=0
        .   .
        .   .
```

**Leyenda:**

* **t:** tipo de reporte.
* **dt**: Fecha en la que se produjeron los eventos de ingresos incluidos en el reporte.
* **h**: Carpeta horaria que contiene el archivo CSV con las transacciones que se realizaron durante esa hora específica.

</Accordion>

<div id="devicelevel-stores-revenue-report" />

<Accordion title="Ingresos de tiendas a nivel de dispositivo (versionados)">

El reporte de ingresos de las tiendas a nivel de dispositivo especifica los eventos de compra in-app y de suscripción auto-renovables capturados por los productos ROI360. Estos eventos incluyen dimensiones únicas relacionadas con la monetización del ROI360. Los eventos in-app emitidos por los clientes no se incluyen en este reporte.

<span id="download-the-report-data-sample::8cbba4e3"></span>[Descargar el ejemplo de datos del reporte de ingresos de tiendas a nivel de dispositivo](https://docs.google.com/spreadsheets/d/e/2PACX-1vSpomvcf2axYeSFcCh0kEx3ShYYRGVfF9WYZXG1UYBkeymeVfh8mcypAOpq2drqE3zhdmbcmrMtahsl/pub?output=csv)

#### Fuentes de datos

Los datos del reporte provienen de transacciones recopiladas a través de:

1. El conector de compra SDK de ROI360.
2. Las tiendas (por ejemplo, la App Store y la tienda Google Play) mediante notificaciones de servidor a servidor.

#### Flujo de datos

1. Los datos del reporte provienen de las transacciones recopiladas a través de las cargas útiles del conector de compras del SDK ROI360 o de las notificaciones de las tiendas S2S.
2. El ROI360 de AppsFlyer mediante VIAP/subscripciones procesa los datos, los atribuye y crea eventos in-app.
3. Los eventos in-app se agregan al nivel del dispositivo y se escriben en una versión de reporte cada cuatro horas.

#### ¿Cuándo están disponibles las versiones del reporte?

| Día de la versión (X = día de aparición del evento de ingresos) | Versión disponible en | La versión incluye los eventos de ingresos que se producen entre |
| --- | --- | --- |
| Día X | 04:00 — 05:00 | 00:00 — 04:00 |
| Día X | 12:00 — 13:00 | 00:00 — 12:00 |
| Día X | 20:00 — 21:00 | 00:00 — 20:00 |
| Día X+1 | 05:00 — 06:00 | 00:00 — 24:00 |

#### ¿Cómo suscribirse al reporte?

1. En AppsFlyer, en el menú lateral, selecciona **Reporte >** Data Locker.
2. En el panel de **contenido de Data Locker**, desplázate hacia abajo hasta el mosaico **ROI360 RevenueETL**.
3. Selecciona el **reporte de ingresos de tiendas a nivel de dispositivo [versionado]**.

#### ¿Cómo acceder al reporte de tu bucket?

La ruta al reporte consta de la siguiente jerarquía de carpetas:

`<bucket-name>/t=stores_devicedata/dt=<dt=yyyy-mm-dd>/version=<999999999>`

#### Jerarquía de carpetas de reportes

Un ejemplo de un árbol de reportes en el bucket de anunciantes:

```
bucket
|
└── t=stores_devicedata
    |
    └── dt=2023-06-01
        |
        ├── version=1685588879
        |   |
        │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
        |   |
        │   ├── part-00001-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
        |   │
        |   └── part-00002-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
        |
        ├── version=1685603326
        |   |
        │   ├── part-00000-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
        |   |
        │   ├── part-00001-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
        |   │
        |   └── part-00002-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
        |
        ├── version=1685617877
        .
                .
                .
```

**Leyenda:**

* **t:** tipo de reporte.
* **dt**: Fecha en la que se produjeron los eventos de ingresos incluidos en el reporte.
* **versión**: El nombre de la versión es la marca temporal de la fecha y hora de creación de la versión, por ejemplo, **version=1685588879**.

</Accordion>

<div data-zendesk-anchors="h_01HMBTDD8TASZ2NEBXP7CZ3Q81=revenue-etl reports=reportes h_01HME0BBF2M47M2AV437RYQ070=reportes h_01HETBAQVVYW14END06HBPBQSN=ad-revenue-single-version-report-device-level h_01HETBAQVVZB87JNT0JVYSP80D=download-the-report-data-sample the-report-data-sources=fuentes-de-datos h_01HETBAQVVSKVDM4J90A0WGFJW=fuentes-de-datos the-report-data-flow=flujo-de-datos h_01HETBAQVV97R7G6F67RM6K62K=flujo-de-datos when-is-the-report-data-available=cu%C3%A1ndo-est%C3%A1n-disponibles-los-datos-del-reporte h_01HETBAQVVKDAWW2S98TG6682S=cu%C3%A1ndo-est%C3%A1n-disponibles-los-datos-del-reporte how-to-subscribe-to-the-report=c%C3%B3mo-suscribirse-al-reporte h_01HETBAQVVFSDRW778VQSSE107=c%C3%B3mo-suscribirse-al-reporte how-to-access-the-report-in-dl=c%C3%B3mo-acceder-al-reporte-de-tu-bucket h_01HETBAQVV15T92VXRHG2CP2KJ=c%C3%B3mo-acceder-al-reporte-de-tu-bucket the-report-folder-hierarchy-in-aws=jerarqu%C3%ADa-de-carpetas-de-reportes h_01HETBAQVVA750VTE1ABSM2M47=jerarqu%C3%ADa-de-carpetas-de-reportes h_01HETBAQVVCB2SYMW9876HPE7N=ad-revenue-versioned-report-device-level data-sources=fuentes-de-datos-1 h_01HMTZ9VQ5WE6D7E5NEBYH71SZ=fuentes-de-datos-1 data-flow=flujo-de-datos-1 h_01HMTZ9VQ5PS8G9JTQ2YXF1G7X=flujo-de-datos-1 when-are-the-report-versions-available=cu%C3%A1ndo-est%C3%A1n-disponibles-las-versiones-del-reporte h_01HETBAQVVP1M40KHB66AW545S=cu%C3%A1ndo-est%C3%A1n-disponibles-las-versiones-del-reporte how-to-subscribe-to-the-report::cae4aa15=c%C3%B3mo-suscribirse-al-reporte-1 h_01HMTZ9VQ5BBFNNE7Z8EP084CF=c%C3%B3mo-suscribirse-al-reporte-1 how-to-access-the-report-in-your-bucket=c%C3%B3mo-acceder-al-reporte-de-tu-bucket-2 h_01HMTZ9VQ5FGBC56AP4R49P4BX=c%C3%B3mo-acceder-al-reporte-de-tu-bucket-2 report-folder-hierarchy=jerarqu%C3%ADa-de-carpetas-de-reportes-2 h_01HMTZ9VQ5HCKP7T3JQ2RHZV50=jerarqu%C3%ADa-de-carpetas-de-reportes-2 h_01HETBAQVVR90NJC522WNAG190=impression-level-report the-source-of-the-report-data=fuente-de-datos h_01HETBAQVV3KBEW4VV4RY9VRA2=fuente-de-datos data-flow::c7ffb834=flujo-de-datos-2 h_01HMTZ9VQ5J837PGG99S8ARAGV=flujo-de-datos-2 when-is-the-report-data-available::272621c9=cu%C3%A1ndo-est%C3%A1n-disponibles-los-datos-del-reporte-1 h_01HMTZ9VQ5YQKBQ779YWBWESDZ=cu%C3%A1ndo-est%C3%A1n-disponibles-los-datos-del-reporte-1 how-to-subscribe-to-the-report::67646c99=c%C3%B3mo-suscribirse-al-reporte-2 h_01HMTZ9VQ5ZST1M7JYKFC3DA62=c%C3%B3mo-suscribirse-al-reporte-2 how-to-access-the-report-in-aws-the-bucket=c%C3%B3mo-acceder-al-reporte-de-tu-bucket-2 h_01HETBAQVVHE80MH3SM3GX21V1=c%C3%B3mo-acceder-al-reporte-de-tu-bucket-2 report-folder-hierarchy::26ec73c6=jerarqu%C3%ADa-de-carpetas-de-reportes-2 h_01HMTZ9VQ5FFSA1XF7YSATM6WH=jerarqu%C3%ADa-de-carpetas-de-reportes-2 h_01HETBAQVWZKYBAG5E71KVB9PM=transactionlevel-stores-revenue-report data-sources::68e71455=fuentes-de-datos-2 h_01HMTZ9VQ5SWTWTSNW5M9KJ1XN=fuentes-de-datos-2 data-flow::bde19643=flujo-de-datos-4 h_01HMTZ9VQ6XVHDHBKV86F3Q9DJ=flujo-de-datos-4 when-is-the-report-data-available::87d17fc2=cu%C3%A1ndo-est%C3%A1n-disponibles-los-datos-del-reporte-2 h_01HMTZ9VQ64AJQM861M6ENHVWC=cu%C3%A1ndo-est%C3%A1n-disponibles-los-datos-del-reporte-2 how-to-subscribe-to-the-report::6569d202=c%C3%B3mo-suscribirse-al-reporte-3 h_01HMTZ9VQ60HMM6TXAPYSZG5CT=c%C3%B3mo-suscribirse-al-reporte-3 how-to-access-the-report-in-your-bucket::b136ba80=c%C3%B3mo-acceder-al-reporte-de-tu-bucket-4 h_01HMTZ9VQ67ZEX3KM6CV32SNBD=c%C3%B3mo-acceder-al-reporte-de-tu-bucket-4 report-folder-hierarchy::805d4d8=jerarqu%C3%ADa-de-carpetas-de-reportes-4 h_01HMTZ9VQ68VRJRHXSNAE38A0E=jerarqu%C3%ADa-de-carpetas-de-reportes-4 h_01HETBAQVVWAFEMK8ENWN7DYEY=devicelevel-stores-revenue-report h_01HETBAQVV9PSDJNS76SNX522C=download-the-report-data-sample::8cbba4e3 the-report-data-sources::af31e5d1=fuentes-de-datos-3 h_01HETBAQVWE2R75D034VCYMTR1=fuentes-de-datos-3 the-report-data-processing-flow=flujo-de-datos-4 h_01HETBAQVWZRBE84NV403BCZ9F=flujo-de-datos-4 when-are-the-report-versions-available::2f1bc55f=cu%C3%A1ndo-est%C3%A1n-disponibles-las-versiones-del-reporte-1 h_01HETBAQVWQFCKHMT6PJNPXX7D=cu%C3%A1ndo-est%C3%A1n-disponibles-las-versiones-del-reporte-1 how-to-subscribe-to-the-report::a624afde=c%C3%B3mo-suscribirse-al-reporte-4 h_01HETBAQVW54MD9Q09RNC673PE=c%C3%B3mo-suscribirse-al-reporte-4 how-to-access-the-report-in-the-aws-bucket=c%C3%B3mo-acceder-al-reporte-de-tu-bucket-4 h_01HETBAQVWYDR81WS9Q9G20ZND=c%C3%B3mo-acceder-al-reporte-de-tu-bucket-4 the-report-folder-hierarchy-in-aws::45c0d598=jerarqu%C3%ADa-de-carpetas-de-reportes-4 h_01HETBAQVWXHK6DXFA90GJQWPV=jerarqu%C3%ADa-de-carpetas-de-reportes-4" />
