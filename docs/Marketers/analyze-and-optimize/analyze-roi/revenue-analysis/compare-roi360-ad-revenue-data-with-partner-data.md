---
title: Compara los datos de ingresos por anuncios de ROI360 con los datos de Partners
metadata:
  keywords:
    - ad revenue
    - Marketers
    - ROI360
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2023-10-11T17:40:51Z'
  edited_at: '2026-08-12T11:48:55Z'
  id: 19287636823953
  locale: es
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/es/articles/19287636823953
---
> **De un vistazo:** Compara los datos de ingresos por anuncios de AppsFlyer ROI360 con los datos de mediación y adquisición de usuarios de Partners.

Los datos deben recibirse y procesarse antes de estar disponibles en dashboards y reportes. El tiempo que tardan los datos en estar disponibles depende del paquete de ROI360 que tengas, así como del tipo de integración de Partners, la actualización de los datos y el tipo de reporte.

Las secciones siguientes explican cuándo y cómo comparar los datos de ingresos por anuncios de ROI360 en los reportes de AppsFlyer con los datos que puedes ver en los dashboards y reportes de Partners.

<div id="comparing-appsflyer-data-with-mediation-partner-data" />

<Accordion title="Compara los datos de AppsFlyer con los datos del partner de mediación">

| Tipo de integración | Tipo de datos | Qué datos se pueden comparar entre sí |
| --- | --- | --- |
| API S2S | Nivel de dispositivo | <ul><li>Compara los ingresos totales que se muestran en el dashboard de actividad de AppsFlyer o los ingresos totales que se muestran en los reportes de ingresos por anuncios de versión única a través de Data Locker con los datos de ingresos totales del partner de mediación.</li><li>Espera al día siguiente del evento de ingresos (día 0+1) para comparar los datos, de modo que tanto AppsFlyer como el partner de mediación tengan tiempo de procesarlos.</li><li>No compares el recuento de eventos de ingresos por anuncios (registrado en los eventos af\_ad revenue) con el recuento de impresiones.</li></ul> |
| SDK | Nivel de dispositivo | <ul><li>Compara los ingresos totales que se muestran en el dashboard de actividad de AppsFlyer o los ingresos totales que se muestran en los reportes de ingresos por anuncios de versión única a través de Data Locker con los datos de ingresos totales del partner de mediación.</li><li>Espera al día siguiente del evento de ingresos (día 0+1) para comparar los datos, de modo que tanto AppsFlyer como el partner de mediación tengan tiempo de procesarlos.</li><li>No compares el recuento de eventos de ingresos por anuncios (registrado en los eventos af\_ad revenue) con el recuento de impresiones.</li></ul>**Nota**: Como los datos de ingresos por anuncios son mutables y es posible que no todos los usuarios de la App hayan actualizado a la versión más reciente con el conector SDK de ingresos por anuncios, al comparar los datos de AppsFlyer con los de los partners de mediación pueden producirse diferencias. |
| SDK | Nivel de impresión | Compara los datos del dashboard de ingresos del partner de mediación con:<ul><li>El reporte de ingresos a nivel de impresión en Data Locker.<ul><li>Compáralos el día del evento de ingresos (día 0).</li><li>Relevante solo para clientes de ROI360 Advanced.</li></ul></li><li>Los ingresos por anuncios a nivel de dispositivo en los reportes de ingresos por anuncios de versión única a través de Data Locker.<ul><li>Espera al día siguiente del evento de ingresos (día 0+1) para comparar los datos, de modo que tanto AppsFlyer como el partner de mediación tengan tiempo de procesarlos.</li></ul></li><li>Los ingresos agregados que se muestran en el dashboard de actividad.<ul><li>Espera al día siguiente del evento de ingresos (día 0+1) para comparar los datos, de modo que tanto AppsFlyer como el partner de mediación tengan tiempo de procesarlos.</li></ul></li></ul> |
| SDK y S2S (actualización frente a precisión) | Nivel de impresión (por SDK) | Compara los datos del dashboard de ingresos del partner de mediación con:<ul><li>Los ingresos que se muestran en el dashboard de actividad o los ingresos totales que se muestran en los reportes de ingresos por anuncios de versión única a través de Data Locker.<ul><li>Espera hasta el día siguiente al evento de ingresos (Día 0+1) para comparar los datos, de modo que tanto AppsFlyer como el partner de mediación tengan tiempo de procesarlos.</li></ul></li><li>El reporte de ingresos a nivel de impresión en Data Locker.<ul><li>Compara el día del evento de ingresos (Día 0).</li><li>Relevante solo para clientes de ROI360 Advanced.</li></ul></li></ul>**Nota**: Dado que los datos de ingresos por anuncios son modificables y es posible que no todos los usuarios de la aplicación hayan actualizado a la versión más reciente con el conector SDK de ingresos por anuncios, al comparar los datos de AppsFlyer con los datos del partner de mediación pueden surgir diferencias. |
| SDK y S2S (de frescura a precisión) | Nivel de dispositivo (por API S2S) | <ul><li>Compara los ingresos totales que se muestran en el dashboard de actividad de AppsFlyer o los ingresos totales que se muestran en el reporte de ingresos por anuncios de versión única mediante Data Locker con los datos de ingresos totales del partner de mediación.</li><li>Espera hasta el día siguiente al evento de ingresos (Día 0+1) para comparar los datos, de modo que tanto AppsFlyer como el partner de mediación tengan tiempo de procesarlos.</li><li>No compares el número de eventos de ingresos por anuncios (reportados en eventos af\_ad\_revenue) con el número de impresiones.</li></ul> |

</Accordion>

<div id="comparing-appsflyer-data-with-user-acquisition-partner-data" />

<Accordion title="Comparación de los datos de AppsFlyer con los datos del partner de adquisición de usuarios">

Se requiere ROI360 Advanced para que los partners de adquisición de usuarios tengan disponibles datos de ingresos por anuncios (mediante postbacks de ingresos por anuncios o señales de UA) para poder compararlos.

| Tipo de integración | Tipo de datos | Fuente de datos del Partners | Qué datos se pueden comparar con cuáles |
| --- | --- | --- | --- |
| API S2S | Nivel de dispositivo | Señales UA | <ul><li>Compara los ingresos totales que se muestran en el dashboard de actividad de AppsFlyer o los ingresos totales que se muestran en los reportes de ingresos por anuncios de versión única mediante Data Locker con los datos de ingresos totales del partner de UA.</li><li>Espera hasta el día siguiente al evento de ingresos (Día 0+1) para comparar los datos.</li><li>No compares el número de eventos de ingresos por anuncios (reportados en los eventos af\_ad revenue) con el número de impresiones.</li></ul> |
| SDK | Nivel de dispositivo | Señales UA | <ul><li>Compara los ingresos totales que se muestran en el dashboard de actividad de AppsFlyer o los ingresos totales que se muestran en los reportes de ingresos por anuncios de versión única mediante Data Locker con los datos de ingresos totales del partner de UA.</li><li>Espera hasta el día siguiente al evento de ingresos (Día 0+1) para comparar los datos.</li><li>No compares el número de eventos de ingresos por anuncios (reportados en los eventos af\_ad revenue) con el número de impresiones.</li></ul> |
| SDK | Nivel de impresión | Postbacks de ingresos publicitarios | Compara los datos del dashboard de ingresos del partner de adquisición de usuarios con:<ul><li>Dashboard/reporte de cohortes de AppsFlyer.<ul><li>Agrupa los datos por la fuente de medios específica (partner de UA).</li><li>Consulta los ingresos totales de los eventos af\_ad\_revenue al filtrar por una fecha específica. Esto permite comparar los ingresos por anuncios generados a partir de instalaciones que se produjeron en una determinada fecha de reporte con los ingresos por anuncios reportados en los postbacks relacionados con esas instalaciones.</li><li>Espera hasta el día siguiente al evento de ingresos (Día 0+1) para comparar los datos.</li></ul></li><li>Dashboard de actividad de AppsFlyer/reportes de ingresos por anuncios de versión única a través de Data Locker.<ul><li>Agrupa los datos por la fuente de medios específica (partner de UA).</li><li>Consulta los ingresos totales de los eventos af\_ad\_revenue al filtrar por una fecha específica. Esto permite comparar los ingresos por anuncios generados a partir de instalaciones que se produjeron en una determinada fecha de reporte con los ingresos por anuncios reportados en los postbacks relacionados con esas instalaciones.</li><li>Espera hasta el día siguiente al evento de ingresos (Día 0+1) para comparar los datos.</li></ul></li></ul> |
| SDK y S2S (de inmediatez a precisión) | Nivel de impresión (por SDK) | Postbacks de ingresos publicitarios | Compara los datos del dashboard de ingresos del partner de adquisición de usuarios con lo siguiente:<ul><li>Reporte de ingresos por anuncios de ROI360 ETL a nivel de impresión del SDK.<ul><li>Espera hasta el día siguiente al evento de ingresos (Día 0+1) para comparar los datos, de modo que tanto AppsFlyer como el partner de mediación tengan tiempo de procesarlos.</li></ul></li><li>Reporte de postbacks de raw data de eventos in-app.<ul><li>Espera hasta el día siguiente al evento de ingresos (Día 0+1) para comparar los datos, de modo que tanto AppsFlyer como el partner de mediación tengan tiempo de procesarlos.</li></ul></li></ul> |
| SDK y S2S (de inmediatez a precisión) | Nivel de dispositivo (por API S2S) | Señales UA | <ul><li>Compara los ingresos totales que se muestran en el dashboard de actividad de AppsFlyer o los ingresos totales que se muestran en los reportes de ingresos por anuncios de versión única a través de Data Locker con los datos de ingresos totales del partner de UA.</li><li>Espera hasta el día siguiente al evento de ingresos (Día 0+1) para comparar los datos.</li><li>No compares el recuento de eventos de ingresos por anuncios (reportados en los eventos af\_ad\_revenue) con el recuento de impresiones.</li></ul> |

</Accordion>

<div data-zendesk-anchors="h_01HCSS64Y99ZNAX64JRE5ZN3J7=comparing-appsflyer-data-with-mediation-partner-data h_01HCSS64Y9FDE00JN8XPWXG0CV=comparing-appsflyer-data-with-user-acquisition-partner-data" />
