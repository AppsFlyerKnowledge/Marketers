---
title: Reporte de eventos de usuarios finales multiplataforma en Data Locker
metadata:
  keywords:
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Cross-Platform Measurement
  created_at: '2025-10-07T10:37:56Z'
  edited_at: '2026-10-20T03:54:55Z'
  id: 39748676204817
  locale: es
  section: Cross platform reports
  section_id: 50467263168657
  url: https://support.appsflyer.com/hc/es/articles/39748676204817
---
> **Resumen:** El reporte de eventos de usuarios finales multiplataforma mide los recorridos completos de los usuarios, las conversiones y el LTV en todas las plataformas y dispositivos

El reporte de eventos de usuario final multiplataforma es un reporte de raw data que proporciona registros de sesiones y eventos in-app a nivel de evento para cada usuario, vinculados entre plataformas mediante tu Customer User ID (CUID). Cada evento incluye el resultado de la atribución multiplataforma, lo que te permite analizar viajes completos de los usuarios.

Para obtener más información sobre el flujo y la configuración de atribución basada en el usuario, consulta <Anchor target="_blank" href="/marketers/es/docs/beta-user-based-cross-platform-attribution">Atribución multiplataforma basada en el usuario</Anchor>.

<div id="report-fields" />

## Campos de reporte

Para saber qué campos contiene el reporte, [descarga una muestra del reporte](https://docs.google.com/spreadsheets/d/e/2PACX-1vRhOl-tyaJvgPd9rxGkGMNrgzHPpr7ZsMMnONOHkzdObor158gJPt7XwCBkreM4ka4OkGIyDmqCp_hh/pub?output=csv).

El reporte de ejemplo incluye todos los campos del reporte y sus valores. Para las definiciones de los campos, consulta el <Anchor target="_blank" href="/marketers/es/docs/raw-data-field-dictionary">diccionario de campos</Anchor>.

<div id="report-data-freshness" />

## Actualización de los datos del reporte

* El reporte ejecuta un proceso por lotes cada 4 horas.
* Cada ejecución del proceso por lotes procesa los eventos que ingresaron en la base de datos durante las 4 horas anteriores.
  * Ejemplo: La ejecución del proceso por lotes de las 8:00 procesa los eventos que ingresaron en la base de datos entre las 3:00 y las 7:00.

* Los eventos se asignan al intervalo horario correspondiente.
  * Ejemplo: Los eventos que ingresaron en la base de datos entre las 3:00 y las 4:00 aparecerán en el bucket de las 3:00 a. m.

<div id="important" />

> 🚧 **¡Importante!**
>
> Normalmente hay un breve retraso entre el momento real de un evento y su entrada en la base de datos. El reporte utiliza la hora de entrada en la base de datos para garantizar una agrupación por horas precisa y coherente.

<div id="example-of-the-800-am-batch-run" />

### Ejemplo de la ejecución del proceso por lotes de las 8:00

| Fecha | Versión del reporte | Reporte disponible en | El reporte incluye eventos que ocurren entre | El reporte incluye eventos que ingresaron a la base de datos entre |
| --- | --- | --- | --- | --- |
| 2025-10-01 | 3:00 | 9:00 | 2:00-4:00 | 3:00-4:00 |
| 2025-10-01 | 4:00 | 9:00 | 3:00-5:00 | 4:00-5:00 |
| 2025-10-01 | 5:00 | 9:00 | 4:00-6:00 | 5:00-6:00 |
| 2025-10-01 | 6:00 | 9:00 | 5:00-7:00 | 6:00-7:00 |

Notas sobre el ejemplo anterior:

* Los eventos de la última hora antes de la ejecución no se procesan para disponer del tiempo suficiente para enriquecerlos con su CUID correspondiente. En el ejemplo anterior, el proceso por lotes de las 8:00 procesa los eventos que ingresaron en la base de datos entre las 3:00 y las 7:00. Los eventos que ingresaron en la base de datos entre las 7:00 y las 8:00 no se procesan.
* El reporte solo está disponible una hora después de la ejecución del proceso por lotes, ya que durante esa hora un proceso interno actualiza el lote. En el ejemplo anterior, el proceso por lotes de las 8:00 está disponible a las 9:00.

<div id="how-to-subscribe-to-the-report" />

## ¿Cómo me suscribo al reporte?

1. En AppsFlyer, desde el menú lateral, selecciona **Exportar** > **Data Locker**.
2. En el **panel de contenido de Data Locker** , desplázate hacia abajo hasta la **sección de reportes avanzados**.
3. Selecciona **Eventos de usuarios finales multiplataforma.**

<div id="how-to-access-the-report-data-in-your-cloud-bucket" />

## ¿Cómo accedo a los datos del reporte en tu bucket de la nube?

La ruta del reporte consta de la siguiente jerarquía de carpetas:

```
<bucket-name>/<DataLocker connection name>/t=end_user_events_user_level_cross_platform/dt=<dt=yyyy-mm-dd>/h=<hour>/
```

<div id="dl-report-folder-hierarchy" />

### Jerarquía de carpetas del reporte de Data Locker

[![](https://files.readme.io/c10bd982197388cbe412d491829ae896bffbcb13921f008ba1508dc46b173032-39751330744209.png)](https://files.readme.io/c10bd982197388cbe412d491829ae896bffbcb13921f008ba1508dc46b173032-39751330744209.png)

<div id="bi-developer-considerations" />

## Consideraciones para desarrolladores de BI

* Cada intervalo horario del reporte contiene eventos únicos de usuarios finales. Asegúrate de extraer todos los reportes cada hora o diariamente.
* Los eventos de ingresos por publicidad aún no están incluidos.
* Todos los datos de la aplicación se proporcionan en un único archivo. Usa el campo ID de aplicación para segregar datos por aplicación o configura Data Locker para que segregue por aplicación. Se recomienda utilizar el tipo de segregación unificada.
* Los datos previos a la atribución, como los costos, los clics y las impresiones, deben extraerse del reporte ETL de costos.

<div id="query-examples" />

### Ejemplos de consultas

A continuación se muestran algunos ejemplos de aplicaciones prácticas y habituales de los datos que los desarrolladores de BI pueden extraer mediante Data Locker. Cada ejemplo se ilustra mediante una instrucción SQL.

<div id="calculating-total-user-acquisitions" />

<Accordion title="Cálculo del total de adquisiciones de usuarios">

Cuenta el número de nuevos usuarios únicos por fuente de medios y campaña.

```sql
SELECT DATE (event_time__conversion) AS install_date
	,CASE 
		WHEN media_source IS NULL
			OR media_source = ''
			OR media_source = 'null'
			THEN 'organic'
		ELSE media_source
		END AS media_source
	,campaign_name
	,count(DISTINCT customer_user_id) AS user_acquisition
	,
FROM end_user_events_user_level_cross_platform
WHERE product_line_name = 'YOUR_PRODUCT_LINE_NAME'
GROUP BY install_date
	,media_source
	,campaign_name
```

</Accordion>

<div id="calculating-total-platform-activations" />

<Accordion title="Cálculo del total de activaciones de plataformas">

Suma el número total de nuevas plataformas, grupos, fuentes de medios y campañas atribuidas por usuario.

```sql
SELECT DATE (event_time__conversion) AS install_date
	,CASE 
		WHEN media_source IS NULL
			OR media_source = ''
			OR media_source = 'null'
			THEN 'organic'
		ELSE media_source
		END AS media_source
	,campaign_name
	,count(DISTINCT CASE 
			WHEN platform_group = 'PC'
				THEN customer_user_id
			ELSE NULL
			END) + count(DISTINCT CASE 
			WHEN platform_group = 'CONSOLE'
				THEN customer_user_id
			ELSE NULL
			END) + count(DISTINCT CASE 
			WHEN platform_group = 'CTV'
				THEN customer_user_id
			ELSE NULL
			END) + count(DISTINCT CASE 
			WHEN platform_group = 'MOBILE'
				THEN customer_user_id
			ELSE NULL
			END) + count(DISTINCT CASE 
			WHEN platform_group = 'Web'
				THEN customer_user_id
			ELSE NULL
			END) + count(DISTINCT CASE 
			WHEN platform_group = 'Other'
				THEN customer_user_id
			ELSE NULL
			END) AS total_activations
FROM end_user_events_user_level_cross_platform
WHERE product_line_name = 'YOUR_PRODUCT_LINE_NAME'
GROUP BY install_date
	,media_source
	,campaign_name
```

</Accordion>

<div id="calculating-total-revenue" />

<Accordion title="Cálculo de los ingresos totales">

Suma los ingresos totales por fuente de medios y campaña.

```sql
SELECT DATE (event_time__conversion) AS install_date
	,CASE 
		WHEN media_source IS NULL
			OR media_source = ''
			OR media_source = 'null'
			THEN 'organic'
		ELSE media_source
		END AS media_source
	,campaign_name
	,SUM(revenue_value_customer) AS total_revenue
FROM end_user_events_user_level_cross_platform
WHERE product_line_name = ’YOUR_PRODUCT_LINE_NAME’
GROUP BY install_date
	,media_source
	,campaign_name;
```

</Accordion>

<div data-zendesk-anchors="the-report-fields=campos-de-reporte h_01K6Z40KG9H1AC81H77XXEGK1B=campos-de-reporte report-data-freshness=actualizaci%C3%B3n-de-los-datos-del-reporte h_01K6Z40KG9PTRAFGXB3XJH5TJ7=actualizaci%C3%B3n-de-los-datos-del-reporte h_01K6Z40KG9QPSMXT13N50TE7KE=importante example-of-the-800-am-batch-run=ejemplo-de-la-ejecuci%C3%B3n-del-proceso-por-lotes-de-las-800 h_01K6Z40KG9JTHGJG7YJNH9TTDT=ejemplo-de-la-ejecuci%C3%B3n-del-proceso-por-lotes-de-las-800 how-to-subscribe-to-the-report=c%C3%B3mo-me-suscribo-al-reporte h_01K6Z40KG9J1XWV99Z9M7AG0BY=c%C3%B3mo-me-suscribo-al-reporte how-to-access-the-report-in-your-bucket=c%C3%B3mo-accedo-a-los-datos-del-reporte-en-tu-bucket-de-la-nube h_01K6Z40KG9CDQ43ASM5T80AK65=c%C3%B3mo-accedo-a-los-datos-del-reporte-en-tu-bucket-de-la-nube dl-report-folder-hierarchy=jerarqu%C3%ADa-de-carpetas-del-reporte-de-data-locker h_01K6Z40KG9NSVWTRSHR71Q7PM6=jerarqu%C3%ADa-de-carpetas-del-reporte-de-data-locker bi-developer-considerations=consideraciones-para-desarrolladores-de-bi h_01K6Z7QHDT4Q2D4JFGC28W8MND=consideraciones-para-desarrolladores-de-bi query-examples=ejemplos-de-consultas h_01K6Z40KG9E2F30Q9P5GFA9TWT=ejemplos-de-consultas h_01K6Z40KG9Y4MWKY6HX8A5NPXA=calculating-total-user-acquisitions h_01K6Z40KG9J9VKC3JH6XNNDA52=calculating-total-platform-activations h_01K6Z40KG9SE8068HG75H59E8Q=calculating-total-revenue" />
