---
title: Cambios de nombres de campañas
metadata:
  keywords:
    - Aggregated Data
    - Agencies
    - Ad Networks
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
    - Agencies
    - Ad Networks
  created_at: '2023-03-26T10:56:19Z'
  edited_at: '2026-08-12T11:49:36Z'
  id: 14038324952465
  locale: es
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/es/articles/14038324952465
---
> **En resumen:** Cambia los nombres de las campañas sin crear visualizaciones de datos duplicados.

## Cambios de nombres de campañas

Cambiar los nombres de las campañas afecta la visualización de los **datos agregados** en los paneles de control y reportes. AppsFlyer muestra las campañas usando el ID de campaña como clave. Si hay más de un nombre asociado con el mismo ID de campaña, se utiliza el nombre reportado más recientemente para mostrar los datos.

* Si bien en este artículo nos referimos a cambios de nombres de **campañas**, se aplican las mismas reglas a los cambios de nombres de anuncios y conjuntos de anuncios.
* El cambio de nombre afecta la visualización de todos los datos conectados a la campaña, incluidas las instalaciones, los eventos in-app, los costos y los ingresos.
* La mayoría de las redes de publicidad admiten cambios de nombres de campañas, pero algunas no lo hacen y en estas es posible que veas filas duplicadas con los mismos datos.
* El raw data no se ve afectado por los cambios de nombre.

La siguiente tabla muestra qué paneles de control y reportes admiten cambios de nombres de campañas.

| Panel de control/reporte | Admite cambios de nombres de campañas |
| --- | --- |
| Panel de vista general | Sí, excepto la vista CTV |
| Panel de control de actividades | Sí |
| Panel de control de cohorte | Sí |
| API de cohorte | Sí |
| API Pull | No se admite con API Pull V5 y versiones anteriores |
| Panel de control de Pivot | No |
| Panel de control personalizado | No |
| Panel de control de retención | No |
| Panel de control de eventos | No |
| Panel de control de Protect360 | No |
| ETL de costos | Sí |
| Panel de control general de SKAN | No |

> 📄 **Ejemplo**
>
> * El 1 de enero comenzó a ejecutarse la campaña **example\_a1**.
> * El 2 de enero, el nombre de la campaña cambió de **example\_a1**a **example\_a2**.
>
> #### Ejemplo de datos de campaña
>
>
>
> | Fecha | Nombre de la campaña | ID de campaña | Instalaciones | Gasto publicitario |
> | --- | --- | --- | --- | --- |
> | 1 de enero | example\_a1 | 123 | 100 | $100 |
> | 2 de enero | example\_a2 | 123 | 200 | $200 |
>
>
>
> #### Visualización del panel de control general
>
>
>
> <table><tbody><tr><th><p><span>Campaña</span></p></th><th><p><span>ID de campaña</span></p></th><th><p><span>Instalaciones</span></p></th><th><p><span>Gasto publicitario</span></p></th></tr><tr><td><p><span>example_a2</span></p></td><td><p><span>123</span></p></td><td><p><span>300</span></p></td><td><p><span>$300</span></p></td></tr><tr><td colspan="4"><p>Resultado: Los datos se muestran bajo el nombre de campaña más reciente.</p></td></tr></tbody></table>

### Práctica recomendada

* La mayoría de las redes de publicidad admiten cambios de nombres de campañas, pero algunas no lo hacen y en estas es posible que veas filas duplicadas con los mismos datos. Para evitar tales anomalías de visualización, asegúrate de que cadacampaña tenga un ID de campaña único asignado.
* No uses el mismo nombre de campaña con diferentes ID de campaña.
* No uses el mismo nombre de anuncio con diferentes ID de anuncio.

<div data-zendesk-anchors="rollout-details=cambios-de-nombres-de-campa%C3%B1as h_01HW896QQ2T4J0N5PDY6YFTJ49=cambios-de-nombres-de-campa%C3%B1as h_01HW896QQ34YVGF6P212ZHAQHG=ejemplo example-campaign-data=ejemplo-de-datos-de-campa%C3%B1a h_01HW896QQ3G07XM06HR2CRXA3G=ejemplo-de-datos-de-campa%C3%B1a overview-dashboard-display-before-the-behavior-change=visualizaci%C3%B3n-del-panel-de-control-general h_01HW896QQ3J9NE9GZRKKAPX46B=visualizaci%C3%B3n-del-panel-de-control-general best-practice=pr%C3%A1ctica-recomendada h_01HW896QQ4RAQ51GPD17YYZBJF=pr%C3%A1ctica-recomendada" />
