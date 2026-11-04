---
title: >-
  Plataforma de Colaboración de Datos (DCP): prepara los datos fuente para su
  ingestión
metadata:
  keywords:
    - Marketers
    - Data Management
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Management
  created_at: '2026-01-26T12:08:32Z'
  edited_at: '2026-08-12T11:53:57Z'
  id: 43205325114897
  locale: es
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/es/articles/43205325114897
---
> **Resumen:** Prepara tus datos fuente para maximizar las tasas de coincidencia entre los conjuntos de datos de los colaboradores y optimizar los resultados de la colaboración.

<div id="about-data-preparation" />

## Acerca de la preparación de datos

La <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-guide">Plataforma de Colaboración de Datos (DCP)</Anchor> de AppsFlyer está diseñada para ingerir y procesar datos transaccionales a gran escala, datos a nivel de usuario o una combinación de ambos de varios colaboradores. Una vez ingeridos los datos, la DCP puede hacer coincidir usuarios entre conjuntos de datos mediante identificadores compartidos (por ejemplo, correo electrónico con hash o teléfono con hash) y habilitar flujos de trabajo de colaboración basados en esos datos.

En este artículo se explica lo siguiente:

* Los tipos de datos que la DCP puede procesar (transaccionales, a nivel de usuario o una combinación de ambos)
* Cómo estructurar los datos para maximizar las tasas de coincidencia entre colaboradores y lograr una coincidencia óptima por parte de los partners de activación
* Qué estructuras de datos se recomiendan y cuáles no
* Cómo gestionar identificadores con varios valores al usar archivos CSV

<div id="understand-data-types" />

## Comprender los tipos de datos

La mayoría de las fuentes utilizadas en las colaboraciones incluyen uno o ambos de los siguientes tipos de datos:

* **Datos a nivel de usuario (identidad)**
  * **Objetivo:** representar a cada usuario y los identificadores utilizados para la coincidencia
  * **Estructura recomendada:** una fila por usuario
* **Datos transaccionales (eventos)**
  * **Objetivo:** representar las acciones de los usuarios (compras, visitas, transacciones)
  * **Estructura habitual:** varias filas por usuario (porque un usuario puede tener muchas transacciones)

<div id="data-structuring-guidelines" />

## Directrices para estructurar los datos

En esta sección se describen las directrices y mejores prácticas para estructurar datos en la DCP.

<div id="workflow-and-structuring-guidelines" />

<Accordion title="Estructuras de datos recomendadas">

**Para estructurar tus datos fuente para una ingestión óptima y maximizar los resultados en la DCP:**

1. Asegúrate de que <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-and-manage-sources#requisitos-de-los-datos-de-las-fuentes">cumple los requisitos de formato de los datos fuente</Anchor>.
2. Para obtener los mejores resultados, **estructura los datos de identidad con una fila por usuario e incluye todos los identificadores disponibles de ese usuario.** Consulta [Estructuras de identificadores recomendadas](#estructuras-de-identificadores-recomendadas).
   * Si los usuarios tienen varias direcciones de correo electrónico o números de teléfono, usa formatos basados en matrices (como Parquet, BigQuery o Snowflake).
3. Comprueba que se sigan las [directrices de Hashing](/docs/data-collaboration-platform-dcp-prepare-source-data-for-ingestion#appendix-e-hashed-data-formatting-guidelines-by-media-partner).
4. Para los conjuntos de datos transaccionales (y otros tipos de datos, cuando corresponda), **usa la herramienta DCP Data View** para crear un subconjunto de tus datos orientado al negocio, seguro en términos de privacidad y optimizado para la colaboración, y compártelo en lugar de las tablas sin procesar. [Por qué se recomiendan las Data Views](/docs/data-collaboration-platform-dcp-prepare-source-data-for-ingestion#appendix-c-why-dataviews-matter-and-recommended).

Aunque se pueden usar otras estructuras, puede que no sean las más adecuadas para sacar el máximo partido a DCP. Consulta [Estructuras de datos no recomendadas](#data-structures-that-arent-recommended).

<div id="recommended-identifier-structures" />

#### Estructuras de identificadores recomendadas

Para maximizar las tasas de coincidencia, se recomienda enviar los datos de identidad a nivel de usuario en una sola fila por usuario siempre que sea posible e incluir todos los identificadores disponibles en una estructura que refleje con precisión cómo se representa a los usuarios.

**Opción 1: Una fila por usuario y un valor por tipo de identificador**

**Sencillo y eficaz.**

Usa esta opción cuando cada usuario tenga como máximo una dirección de correo electrónico con Hashing, un número de teléfono con Hashing, etc.

**Ejemplo**

| ID de usuario | Correo electrónico con Hashing | Teléfono con Hashing |
| --- | --- | --- |
| 123 | 5d41402 | 152d234b70 |
| 456 | 7d793037 |  |
| 789 |  | 0e6e5414 |

**Por qué se recomienda**

* Es lo más sencillo de preparar e ingerir
* Fácil de validar y solucionar problemas
* Buen rendimiento de coincidencia cuando los identificadores están completos y son coherentes (para la coincidencia con conjuntos de datos de colaboradores y la coincidencia de Partners de medios para la activación)

**Más adecuado para**

* Ideal para cargas basadas en CSV
* También funciona bien en Parquet / BigQuery / Snowflake

**Opción 2: Matrices (listas) de identificadores para campos con varios valores**

**La mejor opción para mantener la precisión cuando los usuarios tienen varios correos electrónicos y teléfonos.**

Utiliza esta opción cuando un usuario puede tener varios valores del mismo tipo de identificador, como:

* Varios correos electrónicos con hash
* Varios teléfonos con hash

Esta estructura debe representarse como **matrices nativas**.

**Ejemplo**

| ID de usuario | Correos electrónicos con hash | Teléfonos con hash | MAID |
| --- | --- | --- | --- |
| u\_0001 | [a1b2 · c3d4 · e5f6] | [p1q2 · r3s4] | m001 |
| u\_0002 | [z9y8 · x7w6] |  | m002 |
| u\_0003 |  | [t1u2 · v3w4 · x5y6] |  |

**Por qué se prefiere esta opción**

* Refleja cómo suelen almacenarse internamente los datos de identidad
* No hace falta adivinar cuántas «columnas de correo electrónico» pueden hacer falta
* Evita cambios continuos en el esquema
* Maximiza el potencial de coincidencia (para conjuntos de datos de colaboradores y para la coincidencia de partners de medios de activación) al permitir varios identificadores por usuario

**La mejor opción**

* Parquet (S3/GCS)
* BigQuery
* Snowflake

</Accordion>

<div id="practical-checklist-for-dcp-collaborators" />

<Accordion title="Lista de comprobación práctica para estructurar datos">

<div id="identity-user-level-dataset-checklist" />

#### Lista de comprobación del conjunto de datos de identidad (a nivel de usuario)

* Una fila representa a un usuario.
* Incluye todos los identificadores disponibles (correo electrónico con hash, teléfono con hash, MAID, etc.).
* Si existen varios valores (por ejemplo, varios correos electrónicos), usa arrays nativos siempre que sea posible.
* Evita las listas en las celdas, evita «correo electrónico\_1/correo electrónico\_2/correo electrónico\_3» y evita las estructuras de identidad de varias filas.

<div id="transactional-events-dataset-checklist" />

#### Lista de comprobación del conjunto de datos transaccionales (eventos)

* Mantén las filas de eventos/transacciones tal cual. Consulta los [ejemplos de datos transaccionales](#appendix-a-transactional-data-examples)
* Usa las [Data Views](#appendix-c-why-dataviews-matter-and-recommended) para crear resúmenes a nivel de usuario listos para la colaboración cuando corresponda.

<div id="data-views-checklist" />

#### Lista de comprobación de Data Views

* Crea [Data Views](#appendix-c-why-dataviews-matter-and-recommended) orientadas al negocio (listas para audiencias, resumidas y estandarizadas).
* Comparte Data Views en lugar de tablas sensibles sin procesar siempre que sea posible.
* Minimiza los campos compartidos a solo lo necesario (por privacidad y protección del negocio).
* Considera usar agregaciones para reducir el acceso a datos sensibles y mejorar la eficiencia.

</Accordion>

<div id="supported-ingestion-cloud-services-and-formats" />

<Accordion title="Servicios y formatos de ingesta en la nube compatibles">

El DCP permite la ingesta a través de varios servicios en la nube, como:

* AWS S3
* GCS (Google Cloud Storage)
* BigQuery
* Snowflake

<div id="format-guidance" />

#### Guía de formatos

* Usa **CSV (separado por comas)** cuando cada usuario tenga **un valor por tipo de identificador** (un correo electrónico, un teléfono, etc.).
* Cuando los usuarios puedan tener **varios valores** del mismo tipo de identificador (por ejemplo, varios correos electrónicos con hash), prioriza los **formatos compatibles con matrices**:
  * Parquet (habitual en big data)
  * BigQuery (los arrays están integrados)
  * Snowflake (los arrays están integrados)

**Notas:**

* «Arrays» simplemente significa «una lista de valores».
* Parquet y los arrays en BigQuery/Snowflake son estándar, y la mayoría de los equipos de datos pueden dar soporte a esto de forma natural.

Consulta [activos de ejemplo específicos del conector (AWS S3, GCS, BigQuery, Snowflake).](#appendix-b-connectorspecific-example-assets-aws-s3-gcs-bigquery-snowflake)

<div id="data-structures-that-arent-recommended" />

<Accordion title="Estructuras de datos no recomendadas">

Algunos tipos de estructuración de datos son idóneos para la ingesta en DCP, y otros no. A continuación se muestra una lista de estructuras de datos que **no se recomiendan**:

<div id="avoid-multiple-columns-for-the-same-identifier-type" />

#### Evita: varias columnas para el mismo tipo de identificador

No se recomiendan ejemplos como «correo electrónico principal/secundario/terciario».

**Ejemplo que debes evitar**

| ID de usuario | Hash de correo electrónico 1 | Hash de correo electrónico 2 | Hash de correo electrónico 3 |
| --- | --- | --- | --- |
| 123 | a1b2 | c3d4 |  |
| 456 | z9y8 |  |  |

**Por qué debes evitarlo**

* El número de valores por usuario es impredecible
* Provoca proliferación de columnas y problemas de mantenimiento del esquema

<div id="avoid-lists-inside-a-single-cell-free-text" />

#### Evita: «Listas dentro de una sola celda» (texto libre)

Aunque parezca práctico, es propenso a errores.

**Ejemplo que debes evitar**

| ID de usuario | Correos electrónicos con hash (texto) |
| --- | --- |
| 123 | a1b2 · c3d4 · e5f6 |

**Por qué debes evitarlo**

* No es un tipo de array real
* Los problemas de formato/escape son habituales
* Las pequeñas incoherencias pueden interrumpir la ingesta de datos

<div id="avoid-multiple-rows-per-user-for-identifiers-when-your-goal-is-a-user-identity-table" />

#### Evita: varias filas por usuario para los identificadores (cuando tu objetivo es una tabla de identidad de usuario)

No dividas los datos de identidad entre varias filas cuando puedas mantener una fila por usuario.

**Ejemplo que debes evitar**

| ID de usuario | Tipo de identificador | Valor del identificador |
| --- | --- | --- |
| 123 | hashed\_email | a1b2 |
| 123 | hashed\_email | c3d4 |

**Por qué debes evitarlo**

* Requiere procesamiento adicional para reconstruir usuarios
* Mayor riesgo de duplicados e incoherencias
* Menos eficiente a escala

**Nota:** Varias filas por usuario son normales en las tablas transaccionales, pero no son lo ideal para la tabla de identidad (a nivel de usuario) que se usa para la coincidencia.

</Accordion>

</Accordion>

<div id="additional-information" />

## Información adicional

Esta sección proporciona información adicional y detallada sobre temas relevantes.

<div id="appendix-a-transactional-data-examples" />

<Accordion title="Ejemplos de datos transaccionales">

Los datos transaccionales/de evento pueden tener varias filas por usuario:

| ID de la transacción | ID de usuario | Fecha de la transacción | Cantidad | Categoría |
| --- | --- | --- | --- | --- |
| t\_001 | 123 | 01-12-2025 | 120.00 | Alimentación |
| t\_002 | 123 | 12-15-2025 | 45.00 | Farmacia |
| t\_003 | 456 | 12-20-2025 | 300.00 | Electrónica |

**Recomendado**

* Ingiere los datos transaccionales en su estructura natural
* Usa la herramienta Data View para generar una vista a nivel de usuario lista para colaborar (por ejemplo, gasto en los últimos 30 días, afinidad por categorías y resúmenes de antigüedad/frecuencia)

</Accordion>

<div id="appendix-b-connectorspecific-example-assets-aws-s3-gcs-bigquery-snowflake" />

<Accordion title="Recursos de ejemplo específicos del conector (AWS S3, GCS, BigQuery, Snowflake)">

<div id="what-does-arraylist-of-identifiers-mean" />

### ¿Qué significa «array/lista de identificadores»?

A veces, un solo usuario puede tener más de un correo electrónico o teléfono (por ejemplo, un correo electrónico personal y otro del trabajo). En lugar de forzarlos en columnas adicionales o en campos de texto desordenados, los representamos como una lista de valores.

| ID de usuario | Correos electrónicos con Hashing (lista) |
| --- | --- |
| u\_0001 | [a1b2 · c3d4 · e5f6] |
| u\_0002 | [z9y8 · x7w6] |

<div id="1-aws-s3-and-gcs-connector-parquet" />

### 1. Conector de AWS S3 y GCS (Parquet)

**Qué debe contener la muestra de identidad (esquema)**

| Campo | Tipo de valor esperado | Notas |
| --- | --- | --- |
| user\_id | string | Una fila por usuario |
| hashed\_emails | Matriz de cadenas | Identificador multivalor (recomendado) |
| hashed\_phones | Matriz de cadenas | Identificador multivalor (recomendado) |
| maid | string | Identificador adicional opcional |

Parquet ofrece soporte nativo para listas, por lo que se recomienda cuando los usuarios tienen varios correos electrónicos o teléfonos.

<div id="2-bigquery-connector-table-preview-and-schema-screenshot" />

### 2. Conector de BigQuery (vista previa de la tabla y captura de pantalla del esquema)

**Esquema de identidad de ejemplo (BigQuery)**

| Campo | Tipo de valor esperado | Modo |
| --- | --- | --- |
| user\_id | STRING | NULLABLE |
| hashed\_emails | CADENA | REPETIDO (ARRAY) |
| hashed\_phones | CADENA | REPETIDO (ARRAY) |
| maid | CADENA | ADMITE NULOS |

Las matrices son nativas en BigQuery (campos REPEATED). Este es el enfoque recomendado cuando existen varios correos electrónicos o teléfonos.

<div id="3-snowflake-connector-table-preview-and-schema-screenshot" />

### 3. Conector de Snowflake (vista previa de la tabla y captura de pantalla del esquema)

**Esquema de identidad de ejemplo (Snowflake)**

| Campo | Tipo de valor esperado | Notas |
| --- | --- | --- |
| ID\_USUARIO | VARCHAR | Una fila por usuario |
| CORREOS\_ELECTRÓNICOS\_HASHEADOS | ARRAY | Identificador multivalor |
| TELÉFONOS\_HASHEADOS | ARRAY | Identificador multivalor |
| MAID | VARCHAR | Opcional |

Snowflake admite campos de tipo lista (arrays). Esto se prefiere a crear columnas email\_1/email\_2/email\_3.

</Accordion>

<div id="appendix-c-why-dataviews-matter-and-recommended" />

<Accordion title="Por qué se recomiendan las Data Views">

Las <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-create-customized-data-views">Data views</Anchor> son subconjuntos personalizados de tus fuentes de datos existentes que puedes crear sin modificar el conjunto de datos original. Te permiten ejecutar funciones que modifican, refinan y resumen los datos para que puedas compartir en las colaboraciones solo lo que es relevante, manteniendo los datos que compartes claros y enfocados, y todos los demás datos privados y seguros. Utiliza Data Views en las colaboraciones porque:

<div id="are-business-oriented-and-easier-to-collaborate-with" />

#### Están orientadas al negocio y facilitan la colaboración

* Data Views te permiten presentar los datos en una estructura clara y orientada al negocio (por ejemplo, «Vista de identidad del cliente», «Vista de audiencia apta», «Vista de resumen de compras») en lugar de registros sin procesar o esquemas transaccionales complejos.
* Ayudan a estandarizar definiciones (por ejemplo, «cliente activo», «gasto total de los últimos 30 días») para que ambas partes estén alineadas y utilicen la misma lógica.

<div id="are-more-privacy-safe-by-design" />

#### Son más seguras para la privacidad por diseño

* Data Views permiten la minimización de datos: puedes compartir solo los campos y las filas necesarios para la colaboración, en lugar de exponer conjuntos completos de raw data.
* Reducen el riesgo para la privacidad al permitirte:
  * Excluir atributos innecesarios
  * Limitar la granularidad (por ejemplo, compartir métricas agregadas en lugar de transacciones a nivel de línea)
  * Compartir solo los identificadores necesarios para la coincidencia (y no columnas sensibles adicionales)

<div id="protect-sensitive-business-data" />

#### Protegen los datos empresariales sensibles

* Las tablas transaccionales sin procesar pueden contener señales empresariales muy sensibles (por ejemplo, comportamiento de compra detallado, patrones de precios, relaciones con comercios, IDs internos).
* Data Views te permiten compartir solo lo necesario para la colaboración:
  * Ejemplo: comparte agregados a nivel de categoría en lugar de detalles a nivel de artículo
  * Ejemplo: comparte buckets de gasto o métricas de resumen en lugar de elementos de línea exactos
* Esto reduce el riesgo de revelar sin querer información competitiva o propietaria.

<div id="can-make-your-data-more-cost-effective-and-performant" />

#### Pueden hacer que tus datos sean más rentables y tengan mejor rendimiento

Data Views pueden estructurarse para ser más ligeras y eficientes, lo que a menudo reduce:

* Datos analizados
* Tiempo de procesamiento
* Costos de computación

Estructurar previamente una vista lista para la colaboración (especialmente vistas agregadas) puede hacer que la colaboración sea más rápida y operativamente más predecible.

</Accordion>

<div id="appendix-d-multiple-ids-keys-upload-and-matching-behavior-by-platform" />

<Accordion title="Comportamiento de carga y coincidencia de varios ID/claves por plataforma">

**Carga de identificadores de DCP**

| Partner/plataforma | Tipos de identificador admitidos | Modo de carga | Comportamiento de la carga | Prioridad de identificadores (para partners de un solo tipo) |
| --- | --- | --- | --- | --- |
| Meta | Correo electrónico, teléfono, IDFA, GAID, ID de Android, nombre, apellidos, fecha de nacimiento, ciudad, provincia, código postal, país | Todos los tipos admitidos | Carga todos los tipos de identificador admitidos | No aplica: los carga todos |
| Google | Correo electrónico, teléfono, IDFA, GAID, ID de Android, ID de cliente | Un solo tipo | Carga un tipo de identificador por audiencia | 1. Email 2. Teléfono 3. IDs móviles 4. ID de cliente |
| TikTok | Correo electrónico, teléfono, IDFA, GAID, ID de Android | Todos los tipos admitidos | Carga todos los tipos de identificador admitidos | No aplica: los carga todos |
| Pinterest | Correo electrónico, teléfono, IDFA, GAID | Un solo tipo | Carga un tipo de identificador por audiencia | 1. Email 2. Teléfono 3. IDs móviles |
| Infillion | Correo electrónico, teléfono, IDFA, GAID, MM-UUID | Todos los tipos admitidos | Carga todos los tipos admitidos agrupados en hasta 3 archivos | N/A: los carga todos |
| TheTradeDesk | Correo electrónico, teléfono | Un solo tipo | Carga un tipo de identificador por audiencia | 1. Email 2. Teléfono |
| AppsFlyer Data Locker | Todos los identificadores disponibles | Todos los tipos combinados | Entrega todos los identificadores en un único archivo combinado | N/A: los entrega todos |

| Destino de engagement | ¿Puedes enviar varios ID por usuario? | ¿Pueden hacer coincidir cualquiera de ellos? | ¿Pueden combinar varios ID? | Modelo de coincidencia (práctico) | Notas |
| --- | --- | --- | --- | --- | --- |
| Meta | Sí | Sí | Sí | Determinista, cualquier ID / combinación | Se evalúan correo electrónico, teléfono, MAID y fbp/fbc; comportamiento de «cualquiera de ellos» más sólido |
| Google | Sí | Limitado | No | Determinista, priorizado | Un ID resuelve al usuario; los ID no se combinan para formar una coincidencia |
| TikTok | Sí | Sí | Sí | Determinista, cualquier ID / combinación | Muy similar a Meta; ttclid es potente para eventos |
| Pinterest | Sí | Parcial | Limitado | Determinista, centrado en ID | Principalmente correo electrónico + MAID; refuerzo cruzado entre ID limitado |
| The Trade Desk (TTD) | Sí | A través de un grafo de ID | Sí (a través del grafo) | Determinístico a través del grafo de identidad | UID2 + MAID + cookies resueltos a través del grafo EUID/UID2 |
| Infillion | Sí | A través del grafo de ID | Sí (a través del grafo) | Determinístico a través del grafo de Partners | Se basa en OmniID o en la resolución de identidad de Partners |

**Conclusiones para la planificación de la activación**

* **Meta y TikTok**
  * Envía todo lo que tengas
  * Verdadero comportamiento de «cualquier ID»
  * Las mejores plataformas para la activación en clean rooms con muchas identidades
* **Google**
  * Envía varios ID para ampliar la cobertura
  * No esperes refuerzo entre ID diferentes
  * El predominio del correo electrónico/teléfono es real
* **TTD e Infillion**
  * La calidad de la coincidencia depende más de la participación en el grafo de identidad
  * La cobertura de UID2/OmniID importa más que el número bruto de identificadores
* **Pinterest**
  * Su comportamiento se parece más al de Google que al de Meta
  * Ventaja limitada más allá de correo electrónico + MAID

**TL;DR**

* Solo Meta y TikTok realizan de forma nativa coincidencias de «cualquiera de ellos»
* Google es determinístico, pero se resuelve con un único ID
* Las plataformas de la web abierta establecen coincidencias mediante grafos de identidad, no mediante ID sin procesar

</Accordion>

<div id="appendix-e-hashed-data-formatting-guidelines-by-media-partner" />

<Accordion title="Directrices de formato de datos con hash por Partners de medios">

**Reglas de normalización universales:**  
Antes de aplicar hash a cualquier dato, casi todas las plataformas exigen los siguientes pasos de normalización para garantizar la precisión de la coincidencia:

* **Texto:** Convierte el texto a minúsculas y recorta todos los espacios en blanco iniciales y finales.
* **Teléfono:** conviértelo al formato E.164 (p. ej., +15551234567)
* **Hashing:** SHA-256 es el estándar de la industria, aunque algunas plataformas aceptan MD5 o SHA-1.

| Partner de medio | Pautas de correo electrónico | Pautas del número de teléfono | Pautas del ID móvil (MAID) | Matices específicos de la plataforma & lógica de coincidencia | Referencia relevante |
| --- | --- | --- | --- | --- | --- |
| Google Ads / DV360 | Formato: minúsculas, recorta los espacios en blanco. Incluye el dominio. Regla de Gmail: para @gmail.com / @googlemail.com, elimina los puntos (.) antes de la "@" y los sufijos después del (+). Hashing: SHA-256 (codificación hexadecimal). | Formato: E.164 (p. ej., +16505551212). Debe incluir el código de país. Hashing: SHA-256. | Formato: IDFA (iOS) o GAID (Android). Hashing: no aplicar hash. | Prioridad de coincidencia: determinista y priorizada (1. Correo electrónico, 2. Teléfono, 3. ID móviles). No combina varios ID para formar una coincidencia (resolución de un solo ID). DV360 PAIR: DV360 también da soporte al protocolo PAIR para la conciliación segura entre publisher y anunciante. | <Anchor target="_blank" href="https://developers.google.com/google-ads/api/docs/remarketing/audience-segments/customer-match/get-started">Primeros pasos con Customer Match (API de Google Ads)</Anchor> |
| Meta (Facebook/ Instagram) | Formato: en minúsculas, recorta los espacios en blanco. Hashing: SHA-256 obligatorio.<br /><br />**Nota:** Meta no elimina los puntos de las direcciones de correo electrónico como parte de la normalización del Hashing. Antes del Hashing para Meta, solo se deben aplicar las minúsculas y el recorte de espacios en blanco. Enviar un correo electrónico con Hashing sin puntos («Hashed email (no dots)» en la asignación de fuente de DCP) no coincidirá con el hash propio de Meta y dará como resultado tasas de coincidencia más bajas para usuarios de dominios de correo electrónico. Esta variante de ID está pensada para partners que sí requieren eliminar los puntos (p. ej., Google Ads) y no debe usarse para activaciones de Meta/Facebook. | Formato: elimina símbolos, letras y ceros iniciales. Incluye el código de país (p. ej., 16505551212). Hashing: SHA-256. | Formato: IDFA o GAID. Hashing: no aplicar hash. En minúsculas, conserva los guiones. | Lógica de coincidencia: usa una lógica de «cualquiera de ellos»; combina varios ID (correo electrónico, teléfono, MAID, etc.) para resolver un usuario, lo que proporciona una sólida consolidación entre ID.<br /><br />CAPI: requiere client\_ip\_address y client\_user\_agent sin hash para la coincidencia en navegador. | <Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/conversions-api/parameters/customer-information-parameters/">Parámetros de información del cliente - Conversions API</Anchor> |
| TikTok | Formato: en minúsculas, elimina todos los espacios. Hashing: SHA-256. | Formato: E.164 (+[código de país][número]). También se acepta sin +. Hashing: SHA-256. | Formato: GAID (Android) o IDFA (iOS). Caso: todo en mayúsculas o todo en minúsculas. Hashing: SHA-256 o MD5. | Lógica de coincidencia: al igual que Meta, usa una lógica de coincidencia determinista de «cualquiera de ellos», en la que basta con cualquier ID válido individual.<br /><br />Tamaño de la audiencia: se requiere un mínimo de 1.000 usuarios coincidentes para activar una audiencia personalizada. | <Anchor target="_blank" href="https://ads.tiktok.com/help/article/how-to-create-a-custom-audience-with-a-customer-file">Cómo crear una audiencia personalizada con un archivo de clientes</Anchor> |
| The Trade Desk (UID2) | Formato: la misma «regla de Gmail» que Google (eliminar puntos/signo +). Codificación: codifica en Base64 los bytes sin procesar (el resultado tiene 44 caracteres). | Formato: E.164. Hashing: SHA-256. Codificación: codifica en Base64 los bytes sin procesar. | Formato: AAID (en minúsculas) / IDFA (en mayúsculas). Hashing: SHA-256, MD5 o SHA-1. | Lógica de coincidencia: determinista mediante el grafo de identidad. La coincidencia depende de la participación en el grafo, en lugar de la cobertura bruta de ID.<br /><br />Matiz crítico: debes codificar en Base64 los bytes sin procesar del hash. La codificación de la cadena hexadecimal fallará. |  |
| Pinterest | Formato: debe incluir «@». Hashing: SHA-256, MD5 o SHA-1. | Formato: E.164. Elimina los caracteres especiales (espacios, guiones). Hashing: SHA-256, MD5 o SHA-1. | Formato: IDFA o GAID. Hashing: SHA-256, MD5 o SHA-1. | Lógica de coincidencia: «centrada en el ID». La coincidencia se basa principalmente en el correo electrónico y el MAID. Aportar otros ID tiene un «beneficio limitado», ya que el refuerzo cruzado entre ID es débil en comparación con Meta. Comportamiento de carga: carga un tipo de identificador por audiencia. | Directrices para la ingesta y estructuración de datos del DCP |

</Accordion>

<div data-zendesk-anchors="about-dcp-ingestion-and-preparation-of-data=acerca-de-la-preparaci%C3%B3n-de-datos h_01KFX4HVTT50TZMY2YF37B1C4R=acerca-de-la-preparaci%C3%B3n-de-datos data-types=comprender-los-tipos-de-datos h_01KFX4HVTTAMFEGJQEYXXWG9PT=comprender-los-tipos-de-datos data-ingestion-recommendations=directrices-para-estructurar-los-datos h_01KFX4HVTT2Q2EV4GAC6M8R4A2=directrices-para-estructurar-los-datos h_01KFZJ2PK9XADZ2143VJB3YZ55=workflow-and-structuring-guidelines recommended-identifier-structures=estructuras-de-identificadores-recomendadas h_01KFXB0KEF59QCYET0R8XNH84D=estructuras-de-identificadores-recomendadas h_01KFZN8104KSPFRSS5SED7VT19=practical-checklist-for-dcp-collaborators identity-userlevel-dataset-checklist=lista-de-comprobaci%C3%B3n-del-conjunto-de-datos-de-identidad-a-nivel-de-usuario h_01KFZNGRC0XX7YYBYT09M49YFA=lista-de-comprobaci%C3%B3n-del-conjunto-de-datos-de-identidad-a-nivel-de-usuario transactional-events-dataset-checklist=lista-de-comprobaci%C3%B3n-del-conjunto-de-datos-transaccionales-eventos h_01KFZNJ7YKCT1YFYE400CNY6SP=lista-de-comprobaci%C3%B3n-del-conjunto-de-datos-transaccionales-eventos dataviews-checklist=lista-de-comprobaci%C3%B3n-de-data-views h_01KFZNKBXJQ4S89YHCGKP8J5F4=lista-de-comprobaci%C3%B3n-de-data-views h_01KFZJ2PK9TT2RZQ366Y2THS7E=supported-ingestion-cloud-services-and-formats format-guidance=gu%C3%ADa-de-formatos h_01KFX6XSNACVR9JWZWZW12F6C4=gu%C3%ADa-de-formatos h_01KFZJ2PK92Y5HHFC2D1H8AD9B=data-structures-that-arent-recommended avoid-multiple-columns-for-the-same-identifier-type=evita-varias-columnas-para-el-mismo-tipo-de-identificador h_01KFX72MNYH1CSKWZAGZ2XETXY=evita-varias-columnas-para-el-mismo-tipo-de-identificador avoid-%E2%80%9Clists-inside-a-single-cell%E2%80%9D-free-text=evita-listas-dentro-de-una-sola-celda-texto-libre h_01KFX70V3BHNK93SKCRGGDVY3W=evita-listas-dentro-de-una-sola-celda-texto-libre avoid-multiple-rows-per-user-for-identifiers-when-your-goal-is-a-user-identity-table=evita-varias-filas-por-usuario-para-los-identificadores-cuando-tu-objetivo-es-una-tabla-de-identidad-de-usuario h_01KFX70V3BJE2PR7132QE27C4V=evita-varias-filas-por-usuario-para-los-identificadores-cuando-tu-objetivo-es-una-tabla-de-identidad-de-usuario additional-information=informaci%C3%B3n-adicional h_01KFZJ2PNKB4X962VKCKSYVFFB=informaci%C3%B3n-adicional h_01KFX6XSJYGYFF052EM8NHNMYQ=appendix-a-transactional-data-examples h_01KFX6XSJYZNCTGD5CNSKN5KF7=appendix-b-connectorspecific-example-assets-aws-s3-gcs-bigquery-snowflake what-does-%E2%80%9Carraylist-of-identifiers%E2%80%9D-mean=qu%C3%A9-significa-arraylista-de-identificadores h_01KFX4HVTVPHZQFNRWDH9VCEZQ=qu%C3%A9-significa-arraylista-de-identificadores 1-aws-s3-and-gcs-connector-parquet=1-conector-de-aws-s3-y-gcs-parquet h_01KFX4HVTVNQZY9A8AGEBBHF6Y=1-conector-de-aws-s3-y-gcs-parquet 2-bigquery-connector-table-preview-and-schema-screenshot=2-conector-de-bigquery-vista-previa-de-la-tabla-y-captura-de-pantalla-del-esquema h_01KFX4HVTVCMB0H1B76TCK36SF=2-conector-de-bigquery-vista-previa-de-la-tabla-y-captura-de-pantalla-del-esquema 3-snowflake-connector-table-preview-and-schema-screenshot=3-conector-de-snowflake-vista-previa-de-la-tabla-y-captura-de-pantalla-del-esquema h_01KFX4HVTVN9MSWFB7ZRT9MVCG=3-conector-de-snowflake-vista-previa-de-la-tabla-y-captura-de-pantalla-del-esquema h_01KFX6XSJYF4V3ZTX8X07J0FGS=appendix-c-why-dataviews-matter-and-recommended are-businessoriented-and-easier-to-collaborate-with=est%C3%A1n-orientadas-al-negocio-y-facilitan-la-colaboraci%C3%B3n h_01KFX4HVTV43QFEQARSB2N49Z5=est%C3%A1n-orientadas-al-negocio-y-facilitan-la-colaboraci%C3%B3n are-more-privacysafe-by-design=son-m%C3%A1s-seguras-para-la-privacidad-por-dise%C3%B1o h_01KFX4HVTVJA8Q3FTQB8A94MA1=son-m%C3%A1s-seguras-para-la-privacidad-por-dise%C3%B1o protect-sensitive-business-data=protegen-los-datos-empresariales-sensibles h_01KFX4HVTVF8A0PM90FA6XA0V5=protegen-los-datos-empresariales-sensibles can-make-your-data-more-costeffective-and-performant=pueden-hacer-que-tus-datos-sean-m%C3%A1s-rentables-y-tengan-mejor-rendimiento h_01KFX4HVTVJ70HV606Y8KE4JD1=pueden-hacer-que-tus-datos-sean-m%C3%A1s-rentables-y-tengan-mejor-rendimiento h_01KFX6XSJY4WGJDBP5JEQXC6E3=appendix-d-multiple-ids-keys-upload-and-matching-behavior-by-platform h_01KGFDYKG8KPYR7H5VBKVTXTQS=appendix-e-hashed-data-formatting-guidelines-by-media-partner" />
