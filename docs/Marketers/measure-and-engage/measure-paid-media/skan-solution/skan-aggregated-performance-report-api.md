---
title: API del reporte de rendimiento agregado de SKAN
metadata:
  keywords:
    - Advertisers
    - SKAD
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2020-10-08T09:45:03Z'
  edited_at: '2026-08-12T12:21:23Z'
  id: 360014104157
  locale: es
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/es/articles/360014104157
---
> **En resumen:** Rendimiento de SKAN enriquecido con puntos de datos adicionales. Similar a los datos en el dashboard de SKAdNetwork. Agrega utilizando la fecha de instalación o la fecha de llegada del postback.

<div id="skan-aggregated-performance-report-api" />

## API del reporte de rendimiento agregado de SKAN

La API devuelve métricas de atribución informadas por el SKAdNetwork de Apple (datos reales) y otros puntos de datos utilizando la fecha de llegada de instalación o postbacks. El reporte es similar en estructura a los datos presentados en el<Anchor target="_blank" href="/marketers/es/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">dashboard SKAN</Anchor>.

<div id="using-skan-aggregated-performance-report-api" />

<Accordion title="API del reporte de rendimiento agregado de SKAN">

**Para utilizar la API del reporte de rendimiento agregado de SKAN**:

1. Obtén el token de API. Un administrador necesita recuperar el token.
2. Entrega a tu desarrollador el token API que se utilizará en el encabezado de autenticación.
3. Proporciona a tus desarrolladores los parámetros que deben ingresar cuando realicen la llamada a la API, como se describe en la sección siguiente. Los parámetros determinan en qué se enfoca el reporte, cómo se organiza y proporcionan un marco de tiempo para la presentación de reportes.
4. Dile a tu desarrollador que siga su <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/skan-agg-performance-report-api-get">API de reporte de rendimiento agregado de SKAN</Anchor> en el centro de desarrolladores.

<div id="parameters" />

#### Parámetros

| Nombre de parámetro | Formato | Obligatorio |
| --- | --- | --- |
| `tipo_de_fecha` | El tipo de fecha utilizado en el rango de fechas delimitado por `start_date` y `end_date`<br /><br />Opciones:<ul><li>[Predeterminado] `install`: La fecha de instalación obtenida por AppsFlyer utilizando la hora de llegada del postback y después de considerar el período de medición.</li><li>`arrival`: La hora de llegada del postback. Nota: Las métricas de instalación orgánica tienen el valor N/A.</li></ul>Datos de Google Ads: Las fechas de instalación y llegada son las mismas debido a la metodología de reportes de Google Ads. | No |
| `start_date` | El intervalo de fechas de instalación está limitado por la fecha de inicio y la fecha de finalización. ¡Atención! Nota: La fecha de instalación difiere de la fecha de llegada del postback.<ul><li>Fecha de instalación más temprana con formato AAAA-MM-DD</li><li>Fecha más temprana permitida: 2020-11-01<br />Ejemplo: `2020-11-05`</li></ul> | Sí |
| `end_date` | <ul><li>Fecha de instalación más reciente con formato AAAA-MM-DD</li><li>Número máximo de días por llamada de reporte: 90 días</li><li>Ejemplo: `2020-11-12`</li></ul> | Sí |
| `tipo_de_vista` | Filtra las instalaciones por tipo de la siguiente manera:<ul><li>`acquisition`: Instalaciones</li><li>`retargeting`: [PLEASE TRANSLATE]</li><li>`unified`: Adquisición y redescargas combinadas.</li><li>[Predeterminado] `unified`</li><li>Las métricas de costos, clics e impresiones regresan cuando `view_type=unified`</li></ul> | No |
| `valores_de_conversión_modelados` | <ul><li>Sólo disponible a partir de V2</li><li>El valor puede ser `true` o `false`</li><li>Si es verdadero, el postback incluye los datos modelados al completar las columnas de métricas decodificadas. [Ver campos disponibles](/docs/skan-aggregated-performance-report-api#report-structure-and-example)</li><li>Si `false`, el postback presenta datos decodificados tal como se recibieron mediante postbacks SKAN sin procesar, sin datos modelados.</li><li>El valor predeterminado es `false`.</li></ul> | No |

</Accordion>

<div id="report-structure-and-example" />

<Accordion title="Estructura del informe y ejemplo.">

La API devuelve un archivo CSV.

* Los campos y métricas disponibles en el reporte se enumeran en la siguiente tabla.
* Algunas métricas (ingresos, engagement, conversión) dependen de la <Anchor target="_blank" href="/marketers/es/docs/skan-conversion-studio">configuración de medición del desempeño de SKAN.</Anchor>
* El reporte incluye solo los eventos in-app que realizaron los usuarios durante el período del reporte. Como tal, el número y la secuencia de las columnas de eventos in-app pueden cambiar de un reporte a otro. No confíes en la secuencia de columnas al diseñar tu proceso de importación de datos.
* Ejemplos: [V1](https://docs.google.com/spreadsheets/d/e/2PACX-1vSmnyUITQjRxNp6-rz8Xzscu-Rr4Kn2DW1du2VppS-QrpyQSZ0GKQ_qZdWNdNoLuwJAmgh2O-bWiuU3/pub?gid=0&single=true&output=csv) | <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQogLd4w3xgrjQBmEiHLfcvz1e9dtWez_Rdg1OxV8bSRHRE-wxZJItfT6azLr4iZAgsW2Vxr_WVmEYo/pub?gid=0&single=true&output=csv">V2</Anchor>

<div id="report-fields" />

#### Campos de reporte

| Nombre de campo | Dimensión o métrica | Disponible con token API V1 | Disponible con token API V2 | Disponible con token API V2 (para SKAN 4) | Disponible con filtro solo de datos modelados |
| --- | --- | --- | --- | --- | --- |
| Fecha<br /><br />Los datos son según el data\_type seleccionado. | Dimensión | N/A | Sí | Sí | Sí |
| Fuente de medios (pid) | Dimensión | Sí | Sí | Sí | Sí |
| Campaña (c) | Dimensión | Sí | Sí | Sí | Sí |
| ID de campaña | Dimensión | Sí | Sí | Sí | Sí |
| ID de sitio | Dimensión | Sí | Sí | Sí | N/A |
| Conjunto de anuncios | Dimensión | N/A | Sí | Sí | Sí |
| ID de conjunto de anuncios | Dimensión | N/A | Sí | Sí | Sí |
| Anuncio | Dimensión | N/A | Sí | Sí | N/A |
| ID de anuncio | Dimensión | N/A | Sí | Sí | N/A |
| País | Dimensión | Sí | Sí | Sí | N/A |
| Bandera de atribución de AF<br /><br />Consulta: <Anchor target="_blank" href="/marketers/es/docs/single-source-of-truth-ssot-guide-for-ios-attribution">guía SSOT</Anchor> | Dimensión | N/A | Sí | Sí | Sí |
| Índice de secuencia de postback | Dimensión | N/A | N/A | Sí | Sí |
| Creatividad | Dimensión | N/A | N/A | Sí | N/A |
| Canal | Dimensión | N/A | N/A | Sí | N/A |
| Impresiones | Métrica | Sí | Sí | Sí | Sí |
| Clics | Métrica | Sí | Sí | Sí | Sí |
| CTR | Métrica | Sí | Sí | Sí | Sí |
| Instalaciones | Métrica | Sí | Sí | Sí | Sí |
| Click Through Installs (fidelity\_type = 1) | Métrica | Sí | Sí | Sí | Sí |
| View Through Installs<br /><br />(fidelity\_type = 0) | Métrica | Sí | Sí | Sí | Sí |
| Tasa de valor de conversión nulo<br /><br />[Disponible a partir del 23 de enero de 2022] | Métrica | N/A | Sí | Sí | Sí |
| Tasa de Conversión | Métrica | Sí | Sí | Sí | Sí |
| Usuarios convertidos | Métrica | Sí | Sí | Sí | Sí |
| Usuarios convertidos/instalaciones | Métrica | Sí | Sí | Sí | Sí |
| Ingresos totales | Métrica de ingresos | Sí | Sí | Sí | Sí |
| Costo total | Métrica | Sí | Sí | Sí | Sí |
| ROI (Retorno de la Inversión) | Métrica de ingresos | Sí | Sí | Sí | Sí |
| OPCIONAL | Métrica de ingresos | Sí | Sí | Sí | Sí |
| eCPI promedio | Métrica | Sí | Sí | Sí | Sí |
| `{af_skad_revenue}` (usuarios únicos) | Métrica de ingresos | Sí | Sí | Sí | Sí |
| `{af_skad_revenue}` (Contador de eventos) | Métrica de ingresos | Sí | Sí | Sí | Sí |
| `{nombre de tu evento in-app}` (usuarios únicos) | Métrica | Sí | Sí | Sí | Sí |
| `{el nombre de tu evento in-app}` (contador de eventos) | Métrica | Sí | Sí | Sí | Sí |

</Accordion>

<div id="specifications-and-limitations" />

<Accordion title="Especificaciones y limitaciones">

| Espec | Observaciones |
| --- | --- |
| Actualización de datos | La disponibilidad de datos depende de la tasa de actualización de datos <Anchor target="_blank" href="/marketers/es/docs/about-data-freshness-and-timezone-support#skan">SKAN</Anchor>. |
| Rango de fechas | <ul><li>Al configurar el rango de fechas, la fecha más reciente debe ser la fecha actual, zona horaria UTC menos 3 días. Es decir, el 31 de marzo, utiliza el 28 de marzo.</li><li>Fecha más temprana admitida: 1 de noviembre de 2020</li><li>Rango máximo de consulta: 90 días</li></ul> |
| Límites de tasas | <ul><li>Las queries devuelven hasta 250.000 filas</li><li>10 llamadas por minuto</li></ul> |
| SRN | <ul><li>Meta ads: los datos están disponibles.</li><li>Google Ads: Las instalaciones se pueden registrar hasta 45 días después de la instalación debido a la metodología de tiempo de clic de Google. Siconsultas los datos de Google de los últimos 45 días todos los días, esto proporciona la cobertura necesaria para los datos de Google SKAN.</li></ul> |
| Acceso a la red publicitaria | Si es un partner de análisis, solicita permiso al anunciante. |
| Acceso de agencias | No disponible |
| Zona horaria específica de la aplicación | Solo UTC |
| Divisa específica de la aplicación | Siempre USD |
| Datos orgánicos | Calculado como la diferencia entre todos los datos reportados por el SDK directamente a AppsFlyer menos los datos no orgánicos reportados por los postbacks de SKAN. |
| Datos no orgánicos | Calculado utilizando los postbacks SKAN recibidos por AppsFlyer |
| Historial de datos | Datos de conversión más antiguos (instalación o retarget) admitidos: 1 de noviembre de 2020 |
| Acceso de usuario a la cuenta | El token de autorización está disponible para un usuario administrador en el dashboard. |
| Costo total | Es posible que la API de SKAN no incluya la métrica de costo total si la atribución regular (descripción general regular) contiene campañas de SKAN que en el nivel de granularidad más bajo (por ejemplo: anuncio, país o ID de sitio) tienen más de 50.000 filas. |

</Accordion>

<div data-zendesk-anchors="skadnetwork-postback-arrival-date-aggregation-reporting-api=api-del-reporte-de-rendimiento-agregado-de-skan h_01HH9WHP1SDQ3TJPZ931R9KWKH=api-del-reporte-de-rendimiento-agregado-de-skan h_01HH9WHP1S7PWJHKAKHN434G7Y=using-skan-aggregated-performance-report-api parameters=par%C3%A1metros h_01HH9WHP1SZQZGSZ4WEPAAFNV7=par%C3%A1metros h_01HH9WHP1SYEHGJBBWSMS2XQP0=report-structure-and-example skadnetwork-aggregate-report-structure=campos-de-reporte h_01HH9WHP1STYNJK3DRESDF23DG=campos-de-reporte h_01HH9WHP1T4NEMW56XVYKM3KHM=specifications-and-limitations" />
