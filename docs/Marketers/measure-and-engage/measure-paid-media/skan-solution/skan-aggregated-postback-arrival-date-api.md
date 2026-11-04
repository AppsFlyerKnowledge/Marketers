---
title: API de fecha de llegada de postbacks agregados de SKAN
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
  created_at: '2020-12-21T09:03:09Z'
  edited_at: '2026-08-12T12:21:25Z'
  id: 360016646557
  locale: es
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/es/articles/360016646557
---
> **A simple vista:** Postbacks agregados de SKAdNetwork vía API. Los datos se agregan utilizando la fecha de llegada del postback.

<div id="skan-aggregated-postback-arrival-date-api" />

## API de fecha de llegada de postbacks agregados de SKAN

La API devuelve postbacks agregados de SKAdNetwork, utilizando el intervalo de fechas de llegada del postback.

[Práctica recomendada]: La fecha de llegada del postback difiere de la fecha de instalación usada en el panel de control y los informes de SKAdNetwork.

<div id="using-skan-aggregated-performance-report-api" />

<Accordion title="Uso de la API de informe de rendimiento agregado de SKAN">

**Para usar la API de informe de rendimiento agregado deSKAN**:

1. Obtén el token de la API. Un administrador necesita recuperar el token.
2. Proporciónale a tu desarrollador el token de la API para que lo use en el encabezado de autenticación.
3. Proporciónales a tus desarrolladores los parámetros a introducir cuando hagan la llamada a la API, tal como se describe en la sección que sigue. Los parámetros determinan en qué se enfoca el informe, cómo está organizado y proveen un marco temporal para el reporte.
4. Indica a tu desarrollador que siga su <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/skan-agg-postback-arrival-date-api-get">API de informe de rendimiento agregado de SKAN</Anchor> en el centro de desarrolladores.

<div id="parameters" />

#### Parámetros

| Nombre del parámetro | Detalles | Obligatorio |
| --- | --- | --- |
| `start_date` | El intervalo de fechas de llegada del postback está delimitado por start\_date y end\_date. ¡Atención! ¡Nota! La fecha de llegada difiere de la fecha de instalación utilizada en el panel de control y los informes de SKAdNetwork.<ul><li>AAAA-MM-DD</li><li>Fecha más temprana permitida: 2020-11-01<br />Ejemplo: `2020-11-05`</li></ul> | Sí |
| `end_date` | <ul><li>AAAA-MM-DD</li><li>Número máximo de días por llamada de informe: 60 días</li><li>Ejemplo: `2020-11-12`</li></ul> | Sí |
| `ad_network_name` | Filtrar por fuente de medios | No |
| `geolocalización` | Filtrar por código de país usando ISO 3166 (alfa-2). Ejemplo: `US`, `CN` | No |
| `skad_redownload` | Filtrar por `true` o `false` | No |
| `skad_source_app_id` | Filtrar por ID de la aplicación fuente | No |
| `ad_network_campaign_id` | Filtrar por ID de campaña de red publicitaria.<br /><br />**Nota**: Este no es el ID de campaña informado por SKAdNetwork. | No |
| `valores_de_conversión_modelados` | <ul><li>Solo compatible desde V2</li><li>El valor puede ser `true` o `false`</li><li>Si `true`, el postback llena la columna “count” con datos de valor de conversión modelado.  [Ver campo disponible para datos modelados](/docs/skan-aggregated-postback-arrival-date-api#report-structure-and-example)</li><li>Si , el postback presenta el conteo del valor de conversión y con todos los campos disponibles como se recibe y se lista en la estructura del informe, sin datos modelados.</li><li>El valor predeterminado es `false`.</li></ul> | No |

</Accordion>

<div id="report-structure-and-example" />

<Accordion title="Estructura y ejemplo del informe">

La API devuelve un archivo CSV.

Las columnas y métricas disponibles se enumeran en la tabla que sigue.

Ejemplos: <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRXgsWlkyvMS20HgZuOQnH1YC8QQcRhOMYIOxyj_fcgikfDfmW6wNAMHO6alPWVA1j_KZwtqowohqrK/pub?gid=0&single=true&output=csv">V1</Anchor>| <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRMFEELm8JCAQBBAIJqAc1eE5YdN0kOcSVkOPd_Ki2ngnX61wHL4sXypVouOhto8u-JCQmdIYY_5UG6/pub?gid=219191499&single=true&output=csv">V2</Anchor>

| Nombre de columna | Dimensión o medida | Disponible con el token API V1 | Disponible con el token API V2 | Disponible con el token API V2 (para SKAN 4) | Solo disponible con filtro de datos modelados |
| --- | --- | --- | --- | --- | --- |
| skad\_postback\_sequence\_index | Agrupar por | N/A | N/A | S | S |
| skad\_conversion\_value | Agrupar por | S | S | S | S |
| skad\_coarse\_conversion\_value | Agrupar por | N/A | N/A | S | S |
| skad\_ad\_network\_id<br /><br />Algunas SRNs no comparten su ID con nosotros. En ese caso, el campo está en blanco y se rellena ad\_network\_name. | Agrupar por | S | S | S | S |
| ad\_network\_name<br /><br />Actualmente, en la mayoría de los casos, este campo está en blanco. Lo llenamos en el caso de SRNs que no comparten su skad\_ad\_network\_id | Agrupar por | S | S | S | S |
| skad\_source\_identifier | Agrupar por | N/A | N/A | S | S |
| skad\_campaign\_id | Agrupar por | S | S | S | S |
| ad\_network\_campaign\_id | Agrupar por | S | S | S | S |
| ad\_network\_campaign\_name | Agrupar por | S | S | S | S |
| ad\_network\_adset\_id | Agrupar por | N/A | S | S | S |
| ad\_network\_adset\_name | Agrupar por | N/A | S | S | S |
| ad\_network\_ad\_id | Agrupar por | N/A | S | S | N/A |
| ad\_network\_ad\_name | Agrupar por | N/A | S | S | N/A |
| ad\_network\_creative | Agrupar por | N/A | N/A | S | N/A |
| ad\_network\_channel | Agrupar por | N/A | N/A | S | N/A |
| versión\_skad | Agrupar por | S | S | S | N/A |
| skad\_redownload | Agrupar por | S | S | S | N/A |
| skad\_source\_app\_id | Agrupar por | S | S | S | N/A |
| skad\_source\_domain | Agrupar por | N/A | N/A | S | S |
| skad\_fidelity\_type | Agrupar por | N/A | S | S | N/A |
| geolocalización | Agrupar por | S | S | S | N/A |
| arrival\_date | Agrupar por | S | S | S | S |
| cuenta | Medida | S | S | S | S |

</Accordion>

<div id="specifications-and-limitations" />

<Accordion title="Especificaciones y limitaciones">

| Especificación | Observaciones |
| --- | --- |
| Actualización de datos | El informe se actualiza <Anchor target="_blank" href="/marketers/es/docs/about-data-freshness-and-timezone-support#eod">diariamente.</Anchor><br /><br />La disponibilidad de datos es conforme a la tasa de actualización de datos de <Anchor target="_blank" href="/marketers/es/docs/about-data-freshness-and-timezone-support#skan">SKAdNetwork</Anchor>. |
| Rango de fechas | <ul><li>Primera fecha soportada: 1 de noviembre de 2020</li><li>Rango máximo de consulta: 60 días</li></ul> |
| Límite de tasa | <ul><li>Las consultas devuelven hasta 200K filas</li><li>60 llamadas por minuto</li></ul> |
| SRN | Google Ads: La fecha de llegada del postback se deriva del tiempo del último clic informado por Google. |
| Acceso a red de anuncios | Disponible para socios de análisis si el anunciante otorga permiso. |
| Acceso a la agencia | No disponible |
| Zona horaria específica de la aplicación | Solo UTC |
| Moneda específica de la aplicación | Siempre en USD |
| Datos orgánicos | No disponible con esta API |
| Datos no orgánicos | Calculados usando los postbacks de SKAdNetwork recibidos por AppsFlyer |
| Datos históricos | La primera conversión soportada (instalación o redirección): 1 de noviembre de 2020 |
| Acceso de usuario a la cuenta | El token de autorización está disponible para un usuario administrador en el panel de control. |

</Accordion>

<div id="see-also" />

> 📄 **Ver también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/skan-aggregated-performance-report-api">API del informe de rendimiento agregado de SKAN</Anchor>

<div data-zendesk-anchors="skadnetwork-postback-arrival-date-aggregation-reporting-api=api-de-fecha-de-llegada-de-postbacks-agregados-de-skan h_01HDNZKFEHWET0FPX9WN136MB2=api-de-fecha-de-llegada-de-postbacks-agregados-de-skan h_01HDNZKFEH76Y06091QS6Y5K1Z=using-skan-aggregated-performance-report-api parameters=par%C3%A1metros h_01HDNZKFEHA6N6EE4RMG0HGABA=par%C3%A1metros h_01HDNZKFEHM2D7GS3RMSRCKZY7=report-structure-and-example h_01HDNZKFEJ5P3245V1R99DGAQW=specifications-and-limitations h_01HDNZP87CWGVJ3G1BDXAR1WN0=ver-tambi%C3%A9n" />
