---
title: 'Boletín: nuevos campos en los reportes de ingresos por anuncios'
metadata:
  keywords:
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
  created_at: '2024-07-22T13:25:32Z'
  edited_at: '2026-10-20T03:55:12Z'
  id: 26907692192273
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/26907692192273
---

<Table>
  <tbody>
    <tr>
      <td>
        **Novedades**
      </td>
      <td>
        Los informes de ingresos por publicidad tienen nuevos campos.
      </td>
    </tr>
    <tr>
      <td>
        **Fecha de entrada en vigor**
      </td>
      <td>
        19 de septiembre de 2024
      </td>
    </tr>
    <tr>
      <td>
        **Lo que debes saber**
      </td>
      <td>
        La siguiente tabla muestra qué campos se están añadiendo a qué informes. Consulta el <Anchor target="_blank" href="/marketers/es/docs/raw-data-field-dictionary">diccionario de campos de raw data</Anchor> para ver las definiciones y los detalles de cada campo.

        | Informe | Nombres de campos API |
        | --- | --- |
        | <Anchor target="_blank" href="/marketers/es/docs/revenue-etl-reports#ad-revenue-single-version-report-device-level">Ingresos por publicidad antiguo [una versión]</Anchor> | * {"engagement_type"}<br />* {"datos_personalizados"}<br />* {"id_usuario_cliente"}<br />* {"ad_revenue_ad_type"} |
        | <Anchor target="_blank" href="/marketers/es/docs/revenue-etl-reports#ad-revenue-single-version-report-device-level">Ingresos por publicidad [versionado]</Anchor> | * {"engagement_type"}<br />* {"datos_personalizados"}<br />* {"id_usuario_cliente"}<br />* {"ad_revenue_ad_type"} |
        | <Anchor target="_blank" href="/marketers/es/docs/revenue-etl-reports#impression-level-report">Ingresos por publicidad atribuidos [nivel de impresión del SDK]</Anchor> | * {"engagement_type"}<br />* {"datos_personalizados"}<br />* {"id_usuario_cliente"}<br />* {"ad_revenue_ad_type"}<br />* {"ad_revenue_custom_parameters"}<br />* {"version_app"}<br />* versió{"n_sdk"} |
      </td>
    </tr>
    <tr>
      <td>
        **Lo que debes hacer**
      </td>
      <td>
        * En la <Anchor target="_blank" href="/marketers/es/docs/data-locker-for-marketers#set-up-data-locker">configuración de AppsFlyer Data Locker</Anchor>, selecciona los nuevos campos que quieres añadir a tus reportes.  
          **Tip**¡! Si ya recibes un campo como customer\_user\_id a través de la configuración predeterminada de Data Locker, para completar los campos de los reportes de ingresos por anuncios, tienes que añadir otro campo nuevo y guardar la configuración. Después puedes revertir los cambios.
        * Configura tus sistemas de BI para ingerir y usar los nuevos campos.
      </td>
    </tr>
  </tbody>
</Table>
