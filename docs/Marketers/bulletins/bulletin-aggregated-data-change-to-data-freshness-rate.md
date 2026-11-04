---
title: 'Boletín: cambio en la tasa de actualización de los Datos agregados'
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Marketers
    - Marketing Analytics
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
    - Ad Networks
  created_at: '2021-07-20T11:47:58Z'
  edited_at: '2026-10-20T03:56:49Z'
  id: 4404329828497
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/4404329828497
---

<Table>
  <tbody>
    <tr>
      <td>
        Título
      </td>
      <td>
        Tasa de actualización de los datos de instalaciones y eventos in-app en reportes de analítica y dashboards
      </td>
    </tr>
    <tr>
      <td>
        Fecha del boletín
      </td>
      <td>
        Agosto 24, 2021
      </td>
    </tr>
    <tr>
      <td>
        Qué ha cambiado
      </td>
      <td>
        La tasa de actualización de los datos de instalaciones y de eventos in-app está cambiando. La tabla detalla la tasa de actualización de los datos antes y después del cambio.

        <div id="data-freshness-rate-per-event-type" />

        #### Tasa de actualización de los datos por tipo de evento

        | Tipo de evento | Antes del cambio (minutos) | Después del cambio<br /><br />(minutos) |
        | --- | --- | --- |
        | Instalación, reatribución, re-engagement | 3-5 | 15-30 |
        | Evento en la aplicación | 90 | 30-60 |
      </td>
    </tr>
    <tr>
      <td>
        ¿Dónde está cambiando?
      </td>
      <td>
        El cambio en la tasa de actualización de los datos afecta a los dashboards y a las herramientas de reportes indicados. El cambio se implementa por fases, de la siguiente manera:

        **Fase 1—starting 12 de septiembre de 2021 (sujeto a cambios)**

        * Dashboards:
          * Resumen
          * Vista general V2
          * Reorientación
          * Eventos
          * Personalizar
        * Informes de estadísticas agregadas a través de Pull API

        **Fase 2—starting 6 de octubre de 2021 (previsto)**

        * Dashboards:
          * La actividad del partner
          * Reporte Cohorte
        * API: Cohorte
      </td>
    </tr>
    <tr>
      <td>
        Qué no cambia
      </td>
      <td>
        Master API y raw data
      </td>
    </tr>
    <tr>
      <td>
        Acción requerida
      </td>
      <td>
        * Cuando visualices o descargues datos, ten en cuenta el cambio en la actualización de los datos.
        * Si usas el Dashboard general para probar la integración del SDK o la integración con un partner de ad network, los eventos de instalación tardarán más en mostrarse. Considera usar los Reportes de raw data para verificar tus pruebas de integración.
      </td>
    </tr>
  </tbody>
</Table>

<div id="see-also" />

> 📄 **Consulte también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/about-data-freshness-and-timezone-support">Actualización de datos de AppsFlyer</Anchor>
> * Novedades en AppsFlyer

<div data-zendesk-anchors="data-freshness-rate-per-event-type=tasa-de-actualizaci%C3%B3n-de-los-datos-por-tipo-de-evento h_01HDP21Y0H5S3R4GR5411R6D4Y=tasa-de-actualizaci%C3%B3n-de-los-datos-por-tipo-de-evento h_01HDPE9QAQ41ADC9DQGSK80288=consulte-tambi%C3%A9n" />
