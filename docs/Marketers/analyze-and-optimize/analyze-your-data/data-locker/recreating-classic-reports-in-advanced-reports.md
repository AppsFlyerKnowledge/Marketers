---
title: Recrear reportes clásicos en reportes avanzados
metadata:
  keywords:
    - Marketers
    - Data Locker
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Data Locker
  created_at: '2026-06-15T08:16:54Z'
  edited_at: '2026-08-12T11:51:44Z'
  id: 47741416390161
  locale: es
  section: Data Locker
  section_id: 6550945728657
  url: https://support.appsflyer.com/hc/es/articles/47741416390161
---
> **De un vistazo:** Si estás migrando desde los reportes raw clásicos de Data Locker, usa esta guía para encontrar las selecciones de filtros exactas que reproducen cada reporte clásico en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">Reportes avanzados</Anchor>.

<div id="overview" />

## Visión general

Data Locker clásico ofrecía el viaje del usuario como múltiples temas de reporte independientes. Reportes avanzados consolida todo eso en un reporte por producto de datos, cuyo alcance puedes acotar con filtros a nivel de reporte.

Los tres Reportes avanzados y los temas clásicos que sustituyen son:

* El **reporte avanzado** **Engagements** sustituye los temas clásicos de clics e impresiones.
* El **reporte avanzado** **Conversions** sustituye los temas clásicos de instalaciones, conversiones de retargeting e instalaciones de CTV.
* El **reporte avanzado** **End-user events** sustituye los temas clásicos de eventos in-app, sesiones, eventos in-app de CTV, sesiones de CTV y desinstalaciones.

Para recrear un reporte clásico específico, aplica los filtros a nivel de reporte que se describen en las secciones siguientes. Para consultar la lista completa de filtros disponibles por reporte, consulta <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports#filtros-a-nivel-de-reporte">Filtros a nivel de reporte</Anchor>.

<div id="recreate-classic-reports-in-the-engagements-advanced-report" />

## Recrear reportes clásicos en el reporte avanzado Engagements

En el Reporte avanzado Engagements, configura el filtro **Tipo de campaña** para que coincida con la categoría del reporte clásico (por ejemplo, Adquisición de usuarios o Retargeting) y el filtro **Tipo de engagement** para que coincida con su tipo de evento (por ejemplo, Clics o Impresiones).

| Reporte clásico | Filtro de tipo de campaña | Filtro de tipo de engagement |
| --- | --- | --- |
| Adquisición de usuarios – Clics | La adquisición de usuarios | `clic` + `clic con engagement` |
| Adquisición de usuarios – Impresiones | La adquisición de usuarios | `View` + `Engaged view` |
| Retargeting – Clics | Reorientación | `clic` + `clic con engagement` |
| Retargeting – Impresiones | Reorientación | `View` + `Engaged view` |

<div id="recreate-classic-reports-in-the-conversions-advanced-report" />

## Recrear reportes clásicos en el reporte avanzado Conversions

En el Reporte avanzado Conversions, configura el filtro **Tipo de conversión** para que coincida con la categoría del reporte clásico (por ejemplo, Adquisición de usuarios o Retargeting) y el filtro **Grupo de plataformas** para que coincida con su plataforma (por ejemplo, Móvil o CTV).

| Reporte clásico | Filtro de tipo de conversión | Filtro de grupo de plataformas | Comentarios |
| --- | --- | --- | --- |
| Adquisición de usuarios – Instalaciones | La adquisición de usuarios | Móvil | <ul><li>El valor del campo `conversion_name` es `INSTALL`.</li><li>Incluye instalaciones orgánicas y no orgánicas.</li></ul> |
| Retargeting – Conversiones | Reorientación | Móvil | <ul><li>El valor del campo `conversion_name` es `RE-ENGAGEMENT` o `RE-ATTRIBUTION`.</li><li>Incluye solo tráfico no orgánico.</li></ul> |
| CTV – Instalaciones | La adquisición de usuarios | CTV | <ul><li>El valor del campo `conversion_name` es `INSTALL`.</li><li>Incluye instalaciones orgánicas y no orgánicas.</li></ul> |

<div id="recreate-classic-reports-in-the-end-user-events-advanced-report" />

## Recrea reportes clásicos en el reporte avanzado de eventos del usuario final

En el reporte avanzado de eventos del usuario final, configura el filtro **Tipo de conversión** para que coincida con la categoría del reporte clásico (por ejemplo, Adquisición de usuarios o Retargeting) y el filtro **Grupo de plataformas** para que coincida con su plataforma (por ejemplo, Móvil o CTV).

| Reporte clásico | Filtro de tipo de evento del usuario final | Filtro de tipo de conversión | Filtro de grupo de plataformas | Comentarios |
| --- | --- | --- | --- | --- |
| Adquisición de usuarios – Eventos in-app | `Dentro de la aplicación` | La adquisición de usuarios | Móvil | <ul><li>Incluye eventos in-app orgánicos y no orgánicos.</li></ul> |
| Retargeting – Eventos in-app | `Dentro de la aplicación` | Reorientación | Móvil | <ul><li>Incluye solo no orgánico.</li><li>Configura **Is primary attribution** en `True` para eliminar duplicados de eventos de retargeting publicados más de una vez.</li></ul> |
| Adquisición de usuarios – Sesiones | `Sesión` | La adquisición de usuarios | Móvil | <ul><li>Incluye sesiones orgánicas y no orgánicas.</li></ul> |
| Retargeting – Sesiones de retargeting | `Sesión` | Reorientación | Móvil | <ul><li>Solo incluye tráfico no orgánico.</li></ul> |
| CTV – Eventos in-app | `Dentro de la aplicación` | cualquier valor | CTV |  |
| CTV – Sesiones | `Sesión` | cualquier valor | CTV |  |

<div id="traits-and-limitations" />

## Especificaciones y limitaciones

| Caducado | Nota |
| --- | --- |
| Reportes no reproducibles | Los engagements multiplataforma, las reinstalaciones y las reinstalaciones orgánicas no se pueden reproducir con Advanced Reports. |

<div id="see-also" />

> 📄 **Véase también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">Acerca de Advanced Reports de Data Locker</Anchor>

<div data-zendesk-anchors="about-recreating-classic-reports=visi%C3%B3n-general h_01KV55PGFSSE3GWZ9ZW0TXSVNB=visi%C3%B3n-general reproduce-classic-reports-in-the-engagements-advanced-report=recrear-reportes-cl%C3%A1sicos-en-el-reporte-avanzado-engagements h_01KV55PGFSBHV59ZA7KFVQVM1S=recrear-reportes-cl%C3%A1sicos-en-el-reporte-avanzado-engagements reproduce-classic-reports-in-the-conversions-advanced-report=recrear-reportes-cl%C3%A1sicos-en-el-reporte-avanzado-conversions h_01KV55PGFSK35M9XC7EHVDX53X=recrear-reportes-cl%C3%A1sicos-en-el-reporte-avanzado-conversions reproduce-classic-reports-in-the-end-user-events-advanced-report=recrea-reportes-cl%C3%A1sicos-en-el-reporte-avanzado-de-eventos-del-usuario-final h_01KV55PGFSCD4AQQWRBY0MHJGK=recrea-reportes-cl%C3%A1sicos-en-el-reporte-avanzado-de-eventos-del-usuario-final traits-and-limitations=especificaciones-y-limitaciones h_01KV55PGFSF8QVSBAWA3XN7A8W=especificaciones-y-limitaciones h_01KV8SEHV9KVY6R5HQA6K2M2JZ=v%C3%A9ase-tambi%C3%A9n" />
