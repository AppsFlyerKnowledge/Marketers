---
title: >-
  Plataforma de colaboración de datos (PCD) - Medición de la colaboración -
  General
metadata:
  keywords:
    - Marketers
    - Retail Media Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Retail Media Measurement
  created_at: '2025-01-27T08:21:27Z'
  edited_at: '2026-10-20T03:37:17Z'
  id: 32143318560017
  locale: es
  section: Collaboration measurement
  section_id: 38034865098641
  url: https://support.appsflyer.com/hc/es/articles/32143318560017
---
> **En resumen:**  Comienza en la medición colaborativa aprendiendo sus conceptos fundamentales y el procedimiento de configuración.

<div id="the-three-data-sources-of-measurement" />

## Las tres fuentes de datos de medición

El modelo de medición DCP atribuye los eventos de conversión a los eventos de engagement que se producen en un contexto de colaboración. Este proceso requiere datos de tres fuentes de datos clave: conversiones, engagements y mapeo de campañas. Cada fuente desempeña un papel fundamental en el flujo de atribución.

<div id="conversions" />

<Accordion title="Conversiones">

Los datos de conversión contienen detalles sobre las acciones de los usuarios, como las compras y sus Stock Keeping Units (SKU) o Consumer Packaged Goods (CPG) asociados. Cada instancia de conversión representa un único evento de conversión, capturando detalles como el SKU, el ID de usuario y la hora del evento.

**Ejemplo de parámetros de conversión**

| **Campo** | **Valor** |
| --- | --- |
| `id_aplicación` | FoodDelivery |
| `user_id` | 5abe2ddccca43000af58f0b |
| `event_time` | 2024-08-21T16:06:32.393Z |
| `nombre_del_evento` | compra |
| `sku` | 8711327623057 |
| `sku_revenue` | 6.94 |
| `sku_quantity` | 1 |

AppsFlyer proporciona acceso a las conversiones de aplicaciones a través de la integración con tu aplicación utilizando el SDK de AppsFlyer o a través de fuentes de datos personalizadas proporcionadas por los colaboradores. También se pueden proporcionar eventos de conversión web y en tienda utilizando fuentes de datos personalizadas.

</Accordion>

<div id="engagements" />

<Accordion title="Engagements">

La fuente de engagement contiene detalles sobre las interacciones de los usuarios con los anuncios, como clics o impresiones. Cada instancia representa un evento de interacción e incluye atributos como el ID de la campaña, la fuente del medio y el tipo de contacto (por ejemplo, clic o impresión).

**Ejemplo de parámetros de engagement**

| **Campo** | **Valor** |
| --- | --- |
| `appsflyer_id` | 1727548724223 |
| `fuente_de_medios` | Google |
| `campaña única` | grc\_web\_ftu\_seq |
| `Se establece como TRUE o FALSE.` | 2024-09-28T17:05:34 |
| `tipo_táctil_atribuido` | impresión |
| `nombre_del_evento` | start\_game |

Para acceder a los datos de engagement, en las [campañas on-site](#onsite-and-offsite-campaign-measurement), puedes configurar nuevos eventos in-app con datos de atribución en el parámetro `event_value` mediante el SDK de AppsFlyer o compartir los datos a través de una fuente personalizada.

En las [campañas off-site](#onsite-and-offsite-campaign-measurement), los datos de engagement se reciben de terceros y no a través de eventos in-app o de una fuente personalizada.

</Accordion>

<div id="campaign-mapping" />

<Accordion title="Mapa de la campaña">

La fuente de asignación de campañas nos permite determinar el engagement que activó cada conversión. DCP mapea la fuente de datos de mapeo de campaña con las SKUs en la fuente de datos de conversión para identificar las conversiones desencadenadas por una campaña. El flujo de atribución DCP asigna eventos de conversión a eventos de engagement haciendo coincidir los SKU de conversión con los engagements que los anuncian. El proceso tiene acceso a las fuentes de datos de colaboración, engagements y mapeo de campañas.

**Ejemplo de parámetros de asignación de campañas**

| **Campo** | **Valor** |
| --- | --- |
| `collaborator_name` | fasion\_site |
| `collaborator_id` | 10079 |
| `id_campaña` | 49fd77a2-8b64-4c9d... |
| `campaign_name` | off\_season\_25\_1 |
| `conversion_targets` | 8711327621978, 8711327622289, 8711327623057 |

La información de mapeo anterior se proporciona a AppsFlyer como una fuente de datos personalizada.

</Accordion>

<div id="on-site-vs-off-site-campaigns" />

## Medición de campañas on-site y off-site

DCP mide las campañas on-site de forma diferente a las campañas off-site. Mientras que las campañas on-site se ejecutan en una de las plataformas del colaborador, las campañas off-site se ejecutan en plataformas de terceros, como Facebook, Google Ads y otras SRNs. Estas diferencias afectan a cómo se llega a las audiencias, cómo se recopilan los datos y cómo se realiza la atribución.

<div id="offsite-campaigns" />

<Accordion title="Campos de mapeo de campaña">

Las campañas off-site implican engagements de usuarios en plataformas de terceros (como Meta o Google), con conversiones que se producen en las propiedades propias del colaborador y que se atribuyen a esos engagements off-site.

* **Ejemplo:** Una marca ejecuta un anuncio de Facebook dirigido a los datos de clientes segmentados de la CMN. Cuando los usuarios ven el anuncio en Facebook y hacen clic en él, se les dirige a la página del producto de la CMN.
* **Atribución:** DCP comparte eventos de conversión con el party, que realiza su propia atribución; después, DCP recupera resultados agregados a través de la API de reportar del party.

</Accordion>

<div id="onsite-campaigns" />

<Accordion title="Cuando un único evento de engagement es responsable de varios eventos de conversión, sólo la primera conversión se atribuye al engagement, mientras que las demás permanecen sin atribuir.">

Las campañas on-site implican engagements de usuarios y conversiones que se producen dentro de las propiedades propias de un colaborador (como su aplicación o sitio web), y las conversiones se atribuyen a engagements on-site.

* **Ejemplo:** Una marca promociona un producto en un sitio web de Commerce Media Network. La audiencia incluye compradores anteriores de la plataforma de la CMN, segmentados por parámetros como el interés por categoría o el historial de compras. Cuando los usuarios ven el banner de la campaña y hacen clic en él, se les dirige a la página de detalle del producto en el mismo sitio.
* **Atribución:** DCP atribuye directamente las conversiones a las campañas on-site mediante datos de engagement del sitio web o la aplicación del colaborador.

<div id="combined-onsite-and-offsite-campaigns" />

<Accordion title="Considera qué caso de uso de la colaboración se ajusta a tu organización.">

Las campañas combinadas implican engagements de usuarios que se producen tanto on-site como off-site, con conversiones que tienen lugar en las propiedades propias del colaborador y se atribuyen a engagements de cualquiera de las dos fuentes mediante una medición unificada y la deduplicación.

* **Ejemplo:** Una marca promociona un producto en el sitio web de la CMN y también publica anuncios de Facebook dirigidos a los clientes de la CMN. Los engagements y las conversiones tanto de la campaña on-site como de la campaña de Facebook se capturan, se deduplican y se miden conjuntamente.
* **Atribución:** DCP consolida los datos de conversión de los canales on-site y off-site en una tabla de atribución compartida, aplica lógica de deduplicación y presenta métricas unificadas por campaña y SKU.

</Accordion>

</Accordion>

<div id="the-dcp-measurement-process" />

## El proceso de medición DCP

El proceso de medición de DCP define cómo se validan, normalizan y relacionan los registros de conversión procedentes de eventos in-app del SDK y archivos de fuente personalizados con los engagements de campaña en las [campañas on-site y off-site](https://www.notion.so/Collaboration-measurement-Overview-255b7b13af5f80fa83d2dc77e337c960?pvs=21).

<div id="onsite-measurement-flow" />

<Accordion title="Flujo de medición on-site">

El flujo de medición on-site de DCP procesa eventos in-app y registros de fuente personalizados recopilados desde la aplicación móvil o el sitio web de la CMN o del anunciante. DCP atribuye estas conversiones internamente mediante la lógica de atribución de AppsFlyer.

El flujo de medición on-site procesa datos de conversión y de engagement procedentes de dos fuentes principales:

* **Eventos in-app (IAEs)** se recopilan a través del SDK de AppsFlyer integrado en la aplicación móvil del colaborador.
* Los **archivos de eventos de fuente personalizados** son enviados a AppsFlyer por los colaboradores.

Ambos tipos de eventos se normalizan en una estructura unificada y se procesan mediante el mismo motor de atribución.

<div id="1-configure-measurement-sources" />

### 1. Configurar fuentes de medición

A continuación se describen las etapas de este proceso.

* **Eventos in-app:** Los colaboradores identifican qué eventos in-app (p. ej., compra o registro) deben medirse como conversiones o engagement. Estos eventos ya deben recopilarse mediante el SDK de AppsFlyer, y los nombres de la aplicación y del evento deben seleccionarse explícitamente en la configuración de DCP.
* **Archivos de eventos de fuente personalizados:** Los colaboradores configuran el acceso a archivos de datos externos (por ejemplo, de BigQuery, S3 o Snowflake) y asignan campos clave como user\_id, campaign\_id y SKU al esquema de DCP para dar soporte a la atribución.

<div id="2-prepare-and-map-conversion-data" />

### 2. Preparar y asignar datos de conversión

Los eventos de conversión incluyen SKU e identificadores de usuario que DCP usa para determinar la actividad desencadenada por la campaña.

* La fuente de mapeo de campaña vincula las conversiones con los engagements mediante el mapeo del SKU del evento de conversión con el ID de campaña del evento de engagement.
* Las conversiones que no se pueden asociar a ninguna campaña se marcan como **orgánico**.

<div id="3-link-conversions-to-engagements" />

### 3. Vincular conversiones a engagements

DCP vincula las conversiones coincidentes con engagements mediante los siguientes criterios:

* Un **ID de usuario** compartido
* El mismo **ID de campaña**

Esto da como resultado registros de conversión atribuidos enriquecidos con metadatos tanto de campaña como de engagement.

<div id="4-split-multi-sku-conversions" />

### 4. Dividir conversiones con varios SKU

Si un evento de conversión incluye varios SKU:

* DCP divide los registros de conversión atribuidos con varias SKUs en registros individuales, cada uno de los cuales representa una única SKU.
* Cada registro refleja la atribución de un único **objetivo de conversión**.

<div id="5-filter-non-target-skus" />

### 5. Filtrar SKU que no son objetivo

Para garantizar que solo se conserven las conversiones relevantes:

* DCP filtra los registros de SKU que no son objetivos de conversión para la campaña.

<div id="6-deduplicate-conversion-events" />

### 6. Eliminar eventos de conversión duplicados

Antes de la atribución, DCP elimina los duplicados:

* Los registros duplicados de la misma fuente personalizada (por ejemplo, cargas repetidas) se descartan.
* Si existe un evento in-app (IAE) coincidente, sustituye al registro de la fuente personalizada.

<div id="7-apply-attribution-logic" />

### 7. Aplicar la lógica de atribución

DCP aplica el modelo de atribución de último toque de AppsFlyer con las siguientes reglas:

* **Múltiples engagements por conversión**: se selecciona el **último toque** según la escala de prioridad de AppsFlyer.
* **Un engagement vinculado a varias conversiones**: solo la **primera** conversión se atribuye al engagement; las conversiones adicionales permanecen sin atribuir.

> Para más información, consulta Prioridades del método de atribución (Cascada de atribución).

<div id="8-output-attributed-conversion-dataset" />

### 8. Resultado: conjunto de datos de conversiones atribuidas

El resultado final incluye:

* Atribución a un único engagement de campaña por conversión
* Registros de conversiones a nivel de SKU depurados y validados
* DCP agrega las conversiones atribuidas para generar insights, incluidas las conversiones totales.
* Registros de conversiones listos para dashboards de analítica y exportaciones

</Accordion>

<div id="offsite-measurement-flow" />

<Accordion title="Flujo de medición off-site">

Los **eventos de conversión off-site** los proporcionan los colaboradores mediante **archivos fuente personalizados** y deben incluir los identificadores necesarios para la atribución, como el ID de clic de Google (`gclid`) o el ID de clic de Facebook (`fbclid`). Estos eventos se comparten con plataformas externas como Google y Meta, que cotejan los datos con sus registros de campaña y devuelven **metadatos enriquecidos**, incluidos identificadores de campaña, conjunto de anuncios y material creativo.

<div id="1-prepare-conversion-data" />

### 1. Preparar datos de conversión

Los registros de conversiones se estandarizan en función de la configuración de la colaboración:

* Los colaboradores asignan campos personalizados a un esquema DCP unificado de conversión.
* Google Ads y Meta Ads requieren campos específicos; las reglas de validación garantizan que las asignaciones cumplan los estándares de cada partner antes de continuar.

<div id="2-deduplicate-conversion-events" />

### 2. Eliminar duplicados de eventos de conversión

Antes de la atribución, DCP elimina los registros duplicados de la misma fuente personalizada (por ejemplo, cargas repetidas) y los descarta.

<div id="3-filter-for-sharing-eligibility" />

### 3. Filtrar por elegibilidad para compartir

DCP comprueba si las conversiones offsite cumplen los criterios para compartirse:

* Hay un identificador válido específico del canal (por ejemplo, GCLID, FBCLID).
* La conversión coincide con una acción de campaña o un SKU definidos.
* La conversión entra dentro de la ventana de lookback:
  * Meta: 1, 7 o 28 días tanto para clic como para view-through.
  * Google: se define en la plataforma; no se admite la sustitución mediante API.

Las conversiones que no cumplan alguno de los criterios se excluyen de la compartición con Partners.

<div id="4-filter-according-to-last-touch-attribution" />

### 4. Filtra según la atribución de último toque

La atribución se asigna en función del punto de contacto más reciente:

* Si un ID de clic válido de Google o Meta es más reciente, la atribución se asigna a ese partner y se comparte solo con ese partner.
* Si ambos ID de clic existen en la conversión, prevalece el más reciente.

<div id="5-share-with-google-and-meta" />

### 5. Compartir con Google y Meta

Las conversiones aptas se comparten de forma segura mediante las API de Partners:

* **Meta:** Conversions API (CAPI)
* **Google:** Offline Conversion API (OCI)

Cada conversión se envía a un solo partner. Los colaboradores deben configurar la cuenta de destino (ID del conjunto de datos de Meta o ID de la acción de conversión de Google).

<div id="6-google-and-meta-response-enrichment" />

### 6. Enriquecimiento de respuestas de Google y Meta

Google y Meta devuelven datos de atribución enriquecidos a través de sus API de Insights, incluidos:

* Cadena
* ID de conjunto de anuncios
* Retargeting: Primer inicio después del re-engagement o la reatribución.
* Creative ID

AppsFlyer realiza la atribución en función de los registros enriquecidos.

<div id="7-output-attributed-conversion-dataset" />

### 7. Resultado: conjunto de datos de conversiones atribuidas

El resultado final incluye:

* Registros de conversión a nivel de SKU depurados y validados
* DCP une cada evento de conversión que se asignó a una campaña a un evento de engagement con el mismo ID de usuario e ID de campaña, creando un registro de conversión atribuido que contiene detalles de campaña y conversión.
* Los registros de conversión están listos para dashboards de analítica y exportaciones

</Accordion>

<div id="combined-onsite-and-offsite-measurement-flow" />

<Accordion title="Flujo combinado de medición on-site y off-site">

Este flujo describe cómo la Data Collaboration Platform (DCP) de AppsFlyer procesa datos de conversión de varias fuentes, entre ellas:

* **Conversiones on-site**, que incluyen eventos in-app y registros de fuentes personalizadas recopilados desde la CMN o desde la aplicación móvil o el sitio web del anunciante. DCP atribuye estas conversiones internamente mediante la lógica de atribución de AppsFlyer.
* **Conversiones off-site**, en las que los datos de conversión proceden de una fuente personalizada y se comparten con plataformas externas como Google y Meta. Estas plataformas relacionan los datos con sus propios registros de campañas y devuelven metadatos enriquecidos, incluidos identificadores de campaña, de conjunto de anuncios y de creativo.

El flujo de atribución off-site y on-site de DCP deduplica, atribuye, enriquece y combina todos los datos de conversión para generar un único conjunto de datos de rendimiento unificado.

[<Image alt="Notion 2025-08-25 16.10.35.png" src="https://files.readme.io/1552e0c84bf4ca98ef0fd9f96096f68bbf1a1f846f3fcc995e1aa0afe065a651-38422017654929.png" width="1622px" />](https://files.readme.io/1552e0c84bf4ca98ef0fd9f96096f68bbf1a1f846f3fcc995e1aa0afe065a651-38422017654929.png)

<div id="1-on-site-and-off-site-record-processing-is-performed" />

### 1. Se realiza el procesamiento de registros on-site y off-site

Los registros de conversión se estandarizan según la configuración de la colaboración:

* Procesamiento on-site hasta e incluido el paso 6 en la atribución on-site.
* Procesamiento off-site hasta e incluido el paso 4 en la atribución off-site.

<div id="2-apply-last-touch-attribution" />

### 2. Aplicar la atribución de último toque

La atribución se asigna en función del punto de contacto más reciente:

* Si un evento de CMN (on-site) es el más reciente, la conversión se atribuye a CMN y no se comparte con Meta ni con Google.
* Si un ID de clic válido de Google o Meta es más reciente, la atribución se asigna a ese partner y se comparte solo con ese partner.
* Si ambos ID de clic existen en la conversión, prevalece el más reciente.

<div id="3-share-with-google-and-meta" />

### 3. Compartir con Google y Meta

Las conversiones aptas se comparten de forma segura a través de las API de partners:

* **Meta:** API de conversiones (CAPI)
* **Google:** API de conversiones offline (OCI)

Cada conversión se envía solo a un partner. Los anunciantes deben configurar la cuenta de destino (ID del conjunto de datos de Meta o ID de la acción de conversión de Google).

<div id="4-off-site-response-enrichment" />

### 4. Enriquecimiento de respuestas off-site

Google y Meta devuelven datos de atribución enriquecidos a través de sus API de Insights, incluidos:

* Cadena
* ID de conjunto de anuncios
* Retargeting: Primer inicio después del re-engagement o la reatribución.
* Creative ID

<div id="5-on-site-and-off-site-conversion-merge" />

### 5. Combinación de conversiones on-site y off-site

DCP combina estas conversiones off-site con las conversiones on-site en un conjunto de datos final en el que cada conversión está:

* Atribuida a una única fuente: Google, Meta o CMN
* Enriquecida con metadatos de campaña
* Lista para dashboards, exportaciones y análisis de rendimiento

</Accordion>

<div id="set-up-collaboration-measurement" />

## Configura la medición de colaboración

El proceso de configuración de la medición puede describirse en seis pasos, cada uno de los cuales tiene un artículo dedicado:

1. <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-determine-your-collaboration-measurement-use-cas">Determina tu caso de uso de medición de la colaboración</Anchor>
2. [Preparar las fuentes de datos que alimentan el proceso de atribución](https://www.notion.so/Prepare-measurement-data-sources-175b7b13af5f8073918df666dc8c0aa9?pvs=21).
3. [Configurar DCP para](https://www.notion.so/Configure-collaboration-measurement-176b7b13af5f805a904acccbbb371a45?pvs=21) acceder a las fuentes de datos y realizar la atribución.
4. <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-view-measurement-dashboard">Consumir los datos de medición atribuidos en dashboards y reportes</Anchor>
5. <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-view-measurement-reports">El proceso de atribución aplica la siguiente lógica:</Anchor>
6. <Anchor target="_blank" href="/marketers/es/docs/data-collaboration-platform-dcp-run-a-dynamic-query-in-dcp">Ejecuta una consulta dinámica</Anchor>

<div data-zendesk-anchors="the-three-data-sources-of-measurement=las-tres-fuentes-de-datos-de-medici%C3%B3n h_01K3GNC7NFJV6W4NPEXJ4SKSKA=las-tres-fuentes-de-datos-de-medici%C3%B3n h_01K3GNC7NF2ZASWHYZJCPYHF2D=conversions h_01K3GNC7NFMAQ8S8A0YN79YRM8=engagements h_01K3GNC7NG2QYKV3ZTGYEHMDYT=campaign-mapping onsite-vs-offsite-campaigns=medici%C3%B3n-de-campa%C3%B1as-on-site-y-off-site h_01K3GNC7NGP2FXZXQRAS5H8DE1=medici%C3%B3n-de-campa%C3%B1as-on-site-y-off-site h_01K3GNC7NGDDSBGTPD7WVH1H2N=offsite-campaigns h_01K3GNC7NGKHSC7W6B5GG3M10Y=onsite-campaigns h_01K3GNC7NGMG4CCSWVJAVEN24E=combined-onsite-and-offsite-campaigns the-dcp-measurement-process=el-proceso-de-medici%C3%B3n-dcp h_01K3GNC7NG1S37JPMH31A6RRSR=el-proceso-de-medici%C3%B3n-dcp h_01K3GNC7NGKJNH3BX53PJ9HQ90=onsite-measurement-flow 1-configure-measurement-sources=1-configurar-fuentes-de-medici%C3%B3n h_01K3GPJQJC29ZJJTMM9BHA97H1=1-configurar-fuentes-de-medici%C3%B3n 2-prepare-and-map-conversion-data=2-preparar-y-asignar-datos-de-conversi%C3%B3n h_01K3GNC7NGMSPQTGNNCRYVWWW4=2-preparar-y-asignar-datos-de-conversi%C3%B3n 3-link-conversions-to-engagements=3-vincular-conversiones-a-engagements h_01K3GNC7NGJPNZ3EEMHQP5E04V=3-vincular-conversiones-a-engagements 4-split-multisku-conversions=4-dividir-conversiones-con-varios-sku h_01K3GNC7NG6DX2B825C5B6TVS0=4-dividir-conversiones-con-varios-sku 5-filter-nontarget-skus=5-filtrar-sku-que-no-son-objetivo h_01K3GNC7NGSED134G0PGDZGPDB=5-filtrar-sku-que-no-son-objetivo 6-deduplicate-conversion-events=6-eliminar-eventos-de-conversi%C3%B3n-duplicados h_01K3GNC7NGBDJ2JCY0HQ61412X=6-eliminar-eventos-de-conversi%C3%B3n-duplicados 7-apply-attribution-logic=7-aplicar-la-l%C3%B3gica-de-atribuci%C3%B3n h_01K3GNC7NG7Y8XZ9VH3SK47DAR=7-aplicar-la-l%C3%B3gica-de-atribuci%C3%B3n 8-output-attributed-conversion-dataset=8-resultado-conjunto-de-datos-de-conversiones-atribuidas h_01K3GNC7NGFY21QVJY8QRNHGVK=8-resultado-conjunto-de-datos-de-conversiones-atribuidas h_01K3GNC7NHG5GBRC0X4M5DZ6PP=offsite-measurement-flow 1-prepare-conversion-data=1-preparar-datos-de-conversi%C3%B3n h_01K3GNC7NH3CP2HMZTFDK050FA=1-preparar-datos-de-conversi%C3%B3n 2-deduplicate-conversion-events=2-eliminar-duplicados-de-eventos-de-conversi%C3%B3n h_01K3GNC7NHD0REAV4Q4EMEXPPX=2-eliminar-duplicados-de-eventos-de-conversi%C3%B3n 3-filter-for-sharing-eligibility=3-filtrar-por-elegibilidad-para-compartir h_01K3GNC7NHX6VN5XV5ADTH92CT=3-filtrar-por-elegibilidad-para-compartir 4-filter-according-to-lasttouch-attribution=4-filtra-seg%C3%BAn-la-atribuci%C3%B3n-de-%C3%BAltimo-toque h_01K3GNC7NH598P4G6VVSBQNVTF=4-filtra-seg%C3%BAn-la-atribuci%C3%B3n-de-%C3%BAltimo-toque 5-share-with-google-and-meta=5-compartir-con-google-y-meta h_01K3GNC7NHAQMGXH6JJKEWHGV5=5-compartir-con-google-y-meta 6-google-and-meta-response-enrichment=6-enriquecimiento-de-respuestas-de-google-y-meta h_01K3GNC7NHVWVZ10A1Y4DW5M6G=6-enriquecimiento-de-respuestas-de-google-y-meta 7-output-attributed-conversion-dataset=7-resultado-conjunto-de-datos-de-conversiones-atribuidas h_01K3GNC7NHFTD0CKQ2GSNNCE25=7-resultado-conjunto-de-datos-de-conversiones-atribuidas h_01K3GNC7NHM6HAYCJ9Q1CX359B=combined-onsite-and-offsite-measurement-flow 1-onsite-and-offsite-record-processing-is-performed=1-se-realiza-el-procesamiento-de-registros-on-site-y-off-site h_01K3GNC7NHW2M399S909QZE9H9=1-se-realiza-el-procesamiento-de-registros-on-site-y-off-site 2-apply-lasttouch-attribution=2-aplicar-la-atribuci%C3%B3n-de-%C3%BAltimo-toque h_01K3GNC7NH3XJRK6N0PC8BWPXT=2-aplicar-la-atribuci%C3%B3n-de-%C3%BAltimo-toque 3-share-with-google-and-meta=3-compartir-con-google-y-meta h_01K3GNC7NHXMDC2CQQN8Q95DNH=3-compartir-con-google-y-meta 4-offsite-response-enrichment=4-enriquecimiento-de-respuestas-off-site h_01K3GNC7NHVGQNNVWMKZTAQ03D=4-enriquecimiento-de-respuestas-off-site 5-onsite-and-offsite-conversion-merge=5-combinaci%C3%B3n-de-conversiones-on-site-y-off-site h_01K3GNC7NH2PZ2KFBJHTG1ZZTE=5-combinaci%C3%B3n-de-conversiones-on-site-y-off-site set-up-collaboration-measurement-in-four-steps=configura-la-medici%C3%B3n-de-colaboraci%C3%B3n h_01K3GNC7NHSCW4C2845N0MVQZM=configura-la-medici%C3%B3n-de-colaboraci%C3%B3n" />
