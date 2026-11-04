---
title: 'Boletín: cambio en el reporte de ingresos por anuncios'
metadata:
  keywords:
    - ad revenue
    - Agencies
    - data freshness
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - Agencies
    - ROI360
  created_at: '2020-05-05T15:30:21Z'
  edited_at: '2026-10-20T03:57:08Z'
  id: 360007980057
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/360007980057
---
* **Qué cambia**: La fecha de los datos de ingresos por anuncios (a nivel de usuario y a nivel agregado) en la plataforma pasa a ser el mismo día del evento de visualización del anuncio (el día en que se producen los ingresos por anuncios), en lugar del día siguiente. Esto significa que, si un anuncio se muestra el lunes, los ingresos se muestran el lunes. Esto ofrece a los anunciantes una visión más precisa y útil de sus datos de ingresos publicitarios.
* **A quién afecta**: propietarios de aplicaciones, agencias
* **Dónde cambia**: Básicamente, la alineación de los datos con el día del evento de visualización del anuncio está activa en todos los reportes y las API, para todo tipo de integraciones de red. Consulta la siguiente tabla para ver dónde y cuándo entró en vigor la alineación.

<div id="ad-revenue-reporting-change" />

#### Cambio en el reporte de ingresos publicitarios

| Método de reporte | Fecha de entrada en vigor (cuando se produce el cambio de fecha) | Fecha de publicación (fecha del anuncio) |
| --- | --- | --- |
| Reportes de cohortes | 13 de mayo de 2020 | 7 de mayo de 2020 |
| Reportes de raw data | 17 de junio, 2020 | 14 de junio, 2020 |
| Pull API (para raw data) | 17 de junio, 2020 | 14 de junio, 2020 |
| Panel de actividades | 17 de junio, 2020 | 14 de junio, 2020 |
| Data Locker (carpeta h=23) | Agosto 3, 2020 | Agosto 3, 2020 |
| Pull API (para datos agregados) | 1 de septiembre de 2020 | 31 de agosto de 2020 |

<div id="before-the-change" />

### Antes del cambio

La fecha de los datos de ingresos publicitarios en la plataforma es el día posterior al propio evento de visualización del anuncio. Esto significa que, si un anuncio se muestra el lunes, los ingresos se muestran el martes. Los datos están disponibles en la plataforma el miércoles, después del procesamiento.

Esto significa que la fecha de los ingresos por anuncios no está alineada con el engagement real de los usuarios. En algunos verticales, esta falta de alineación distorsiona significativamente los KPI.

<div id="after-the-change" />

### Después del cambio

El cambio depende del tipo de integración entre la app y la red de monetización, de la siguiente manera:

* Este cambio afecta a los ingresos por anuncios a nivel de usuario y a nivel agregado disponibles a través de los métodos de reporte descritos en la tabla anterior.
* La fecha de los datos de ingresos publicitarios en la plataforma es el mismo día del propio evento de visualización del anuncio. Esto significa que, si un anuncio se muestra el lunes, los ingresos se muestran el lunes. Los datos están disponibles en los reportes a partir del miércoles, después del procesamiento.
* No hay ningún cambio en los datos históricos registrados antes de la fecha de entrada en vigor.
* Los ingresos en la fecha de entrada en vigor incluyen los ingresos de dos días: los de la fecha de entrada en vigor y los del día anterior. Según el escenario de reportes, es posible que detectes un pico de ingresos ese día.

Mira el ejemplo que sigue.

<div id="example" />

> 📄 **Ejemplo**
>
> * La visualización de anuncios y los ingresos por publicidad se producen el Día 0 (el día de la adquisición de usuarios).
> * Los datos de ingresos por publicidad se extraen el Día 1.
> * Los datos de ingresos por publicidad se procesan y están disponibles en la plataforma AppsFlyer el Día 2.
> * Los datos de ingresos por publicidad se reportan con el Día 0.
>   * En el Dashboard de actividad, Data Locker (carpeta h=23) y los reportes de raw data, también está disponible la hora de visualización del anuncio.
>
> [![](https://files.readme.io/b22207f1e7009f3f8f1172fbb8bf9147c1251e7d1f51864b777cbf4eab4b84e4-360010993537.jpg)](https://files.readme.io/b22207f1e7009f3f8f1172fbb8bf9147c1251e7d1f51864b777cbf4eab4b84e4-360010993537.jpg)

<div data-zendesk-anchors="ad-revenue-reporting-change=cambio-en-el-reporte-de-ingresos-publicitarios before-the-change=antes-del-cambio after-the-change=despu%C3%A9s-del-cambio" />
