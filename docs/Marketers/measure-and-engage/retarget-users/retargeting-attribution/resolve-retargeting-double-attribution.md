---
title: Doble atribución de eventos de retargeting
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2020-12-13T07:35:18Z'
  edited_at: '2026-08-12T12:26:32Z'
  id: 360016371077
  locale: es
  section: Retargeting attribution
  section_id: 6551326229265
  url: https://support.appsflyer.com/hc/es/articles/360016371077
---
> **En resumen:** Para evaluar el rendimiento durante la ventana de re-engagement de la campaña de retargeting, los eventos y sesiones en la aplicación se atribuyen dos veces a las fuentes de medios de adquisición de usuarios (UA) y retargeting.

<Image align="center" alt="" src="https://files.readme.io/fce514999471aa7bfced06fa0e1c7d6fa7363a8d30119bd20d0b5d7e56eb1f7d-9479192551825.png" />

<div id="overview" />

## Visión general

En el modelo de atribución de AppsFlyer, los eventos que ocurren como resultado del engagement de usuario con una campaña de retargeting se atribuyen tanto a la fuente de medios que motiva la instalación como a la fuente de medios que motiva el re-engagement.

La aplicación de las atribuciones dobles difiere entre los re-engagements y las reatribuciones:

* **Re-engagements:** La atribución doble se aplica en todos los re-engagements.
* **Reatribuciones:** La atribución doble se aplica a las aplicaciones que están en modo de primera instalación. En las aplicaciones que no están en modo de primera instalación, no se aplica la atribución doble. (El modo de primera instalación significa que todos los eventos in-app generados a partir de reinstalaciones se atribuyen a la instalación original. Para más información sobre el modo de primera instalación, consulta <Anchor target="_blank" href="/marketers/es/docs/measure-reinstalls#attributed-to-the-first-install">Atribuido a la primera instalación</Anchor>). Te recomendamos contactar con AppsFlyer para migrar tus aplicaciones existentes al modo de primera instalación.

En la figura anterior, el evento de UA se atribuye a green\_network. Se genera un evento. En contraste, después de que el usuario se envuelve con un anuncio de retargeting servido por blue\_network, se generan dos eventos. El crédito de los eventos:

* blue\_network como la fuente principal que motiva el re-engagement.
* green\_network como la fuente secundaria que motivó la instalación original.

Para explicarlo mejor, la tabla a seguir contiene un escenario de cómo se atribuyen los eventos in-app antes, durante y después de una ventana de re-engagement. La notación en la tabla se refiere a los campos de raw data utilizados para identificar eventos de doble atribución:

* is\_primary (is\_primary\_attribution): Si es true, la fuente de medios es la fuente de medios principal
* contexto: utiliza uno de los siguientes campos:
  * [Mejor opción] **conversion\_type**: instalación o re-engagement.
  * is\_retargeting: si es cierto, los datos se relacionan con la campaña de retargeting.

<div id="attribution-relative-to-the-re-engagement-window" />

#### Atribución relativa a la ventana de re-engagement

| Fuente de medios | Antes del re-engagement | Durante el re-engagement | Después del re-engagement |
| --- | --- | --- | --- |
| Adquisición de usuarios | Principal<br /><br />is\_primary: True<br /><br />conversion\_type: install<br /><br />(is\_retargeting: False) | Secundario<br /><br />is\_primary: False<br /><br />conversion\_type: re-engagement<br /><br />(is\_retargeting: False) | Principal<br /><br />is\_primary: True<br /><br />conversion\_type: install<br /><br />(is\_retargeting: False) |
| Reorientación | N/D | Principal<br /><br />is\_primary: True<br /><br />conversion\_type: re-engagement<br /><br />(is\_retargeting: True) | N/D |

<div id="support-for-dashboard-view-types" />

## Compatibilidad con los tipos de vista del dashboard

Algunos dashboards y reportes de cohortes contienen múltiples opciones de vista unificadas, adquisición de usuarios y retargeting. Estos tipos de vista emplean una lógica similar a la empleada en los raw data.

<Image align="center" alt="" src="https://files.readme.io/738bf91c1a12671b32b088993c43d4103498907a8bbe15821ddc53a0b071b876-32127949500305.png" />

<div id="data-filtering-by-view-type-using-the-conversion_type-field" />

#### Filtrado de datos por tipo de vista mediante el campo conversion\_type

<table><thead><tr><th>Tipo de vista</th><th>tipo_de_conversión</th><th>es_primario</th><th>Atribución</th></tr></thead><tbody><tr><td rowspan="2">Adquisición de usuarios</td><td>instalar</td><td>True o False</td><td>Atribuyen eventos de la UA a la fuente de medios de UA</td></tr><tr><td>re-engagement</td><td>Falso</td><td>Eventos de retargeting atribuidos a la fuente de medios de UA.</td></tr><tr><td>Reorientación</td><td>Re-engagement o reatribución</td><td>Verdadero</td><td>Eventos de retargeting atribuidos a la fuente de medios de retargeting</td></tr><tr><td>Unificado</td><td>instalación o re-engagement</td><td>Verdadero</td><td>Todos los eventos atribuidos a la fuente de medios de último toque</td></tr></tbody></table>

<div id="how-do-i-identify-double-attributed-retargeting-events-in-user-acquisition-in-app-reports" />

## ¿Cómo identifico eventos de retargeting de doble atribución en los reportes de adquisición de usuarios en la aplicación?

En los  **reportes de eventos in-app de UA**, los eventos registrados como resultado de doble atribución se identifican de la siguiente manera:

* El campo is\_primary\_attribution identifica las fuentes de medios primaria y secundaria; cuando es false, significa que la atribución es el resultado de una campaña de retargeting y la fuente de medios de UA es secundaria.
* El campo is\_retargeting siempre es true.

El registro correspondiente en el retargeting de los reportes de eventos in-app durante la ventana de re-engagement se relata de la siguiente manera:

* El campo is\_primary\_attribution siempre es true.
* El campo is\_retargeting siempre es false.
* Para aclarar, no hay registro de ningún tipo si el evento no ocurre durante una ventana de re-engagement.

<div data-zendesk-anchors="overview=visi%C3%B3n-general h_01J8FJW0TE4DV5BFHGARS4ERT6=visi%C3%B3n-general attribution-relative-to-the-reengagement-window=atribuci%C3%B3n-relativa-a-la-ventana-de-re-engagement h_01J8FJW0TEJH716NXMM2RDN4J1=atribuci%C3%B3n-relativa-a-la-ventana-de-re-engagement support-for-dashboard-view-types=compatibilidad-con-los-tipos-de-vista-del-dashboard h_01J8FJW0TEDFGFPPYZEAREKY4Q=compatibilidad-con-los-tipos-de-vista-del-dashboard data-filtering-by-view-type-using-the-conversion_type-field=filtrado-de-datos-por-tipo-de-vista-mediante-el-campo-conversion_type h_01J8FJW0TETSV5X6D7NJ4EQHGC=filtrado-de-datos-por-tipo-de-vista-mediante-el-campo-conversion_type how-do-i-identify-doubleattributed-retargeting-events-in-user-acquisition-inapp-reports=c%C3%B3mo-identifico-eventos-de-retargeting-de-doble-atribuci%C3%B3n-en-los-reportes-de-adquisici%C3%B3n-de-usuarios-en-la-aplicaci%C3%B3n h_01J8FJW0TED4T9JN89PCRA3M9R=c%C3%B3mo-identifico-eventos-de-retargeting-de-doble-atribuci%C3%B3n-en-los-reportes-de-adquisici%C3%B3n-de-usuarios-en-la-aplicaci%C3%B3n" />
