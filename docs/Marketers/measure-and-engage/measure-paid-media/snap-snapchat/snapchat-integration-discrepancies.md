---
title: Discrepancias de integración de Snapchat
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2022-01-24T08:57:20Z'
  edited_at: '2026-08-12T12:21:50Z'
  id: 4417686973841
  locale: es
  section: Snap (Snapchat)
  section_id: 6551316540945
  url: https://support.appsflyer.com/hc/es/articles/4417686973841
---
> **En resumen:** Descubre las diferentes discrepancias entre los dashboards de Snapchat y AppsFlyer, y los reportes.

En algunos casos, los anunciantes pueden ver menos instalaciones en el dashboard de AppsFlyer que en el dashboard de Snapchat Ads Manager. A veces, la discrepancia se puede solucionar cambiando la configuración en el dashboard de AppsFlyer o en Snapchat Ads Manager (por ejemplo, la configuración de la zona horaria, las ventanas de atribución, etc.). Sin embargo, es normal que haya discrepancias entre los dos dashboards. Los anunciantes deben basarse en el dashboard de AppsFlyer como fuente de referencia al evaluar el CPI y el rendimiento.

Los anunciantes deben tener en cuenta las siguientes causas y valorar si es necesario realizar las acciones correspondientes.

## Fuentes de discrepancias y soluciones

A continuación se describen varias causas de discrepancias y sus posibles soluciones.

### Diferentes ventanas de lookback

De forma predeterminada, Snapchat Ads Manager y AppsFlyer tienen ventanas de atribución diferentes.

| Ventana retrospectiva | Snapchat Ads Manager | AppsFlyer |
| --- | --- | --- |
| Ventana retrospectiva de atribución por clics | 28 días | 7 días por defecto (se puede configurar entre 1 y 30 días) |
| Ventana Retrospectiva de Atribución por Impresiones | 1 día | 1 día por defecto (se puede configurar entre 1 y 48 horas) |

> 👍 **Soluciones**
>
> 1. Configura la ventana de atribución en AppsFlyer para que coincida con los valores predeterminados de Snapchat.
> 2. Los anunciantes pueden seleccionar ventanas de atribución en el dashboard de Ads Manager para que coincidan con lo que han establecido como predeterminado en el dashboard de su partner de atribución (MMP). Ponte en contacto con tu CSM de Snapchat para que incluyan tu cuenta en la allowlist y así activar esta función.

### Diferencias en la zona horaria

De forma predeterminada, Ads Manager usa la zona horaria PST, mientras que AppsFlyer usa UTC +0. Como resultado, por ejemplo, Snapchat puede atribuir una instalación al viernes, mientras que AppsFlyer la atribuye al sábado.

> 👍 **SOLUCIÓN**
>
> Configura PST como zona horaria de cada app en AppsFlyer. Haz clic <Anchor target="_blank" href="/marketers/es/docs/changing-app-time-zone-settings">aquí</Anchor> para ver los detalles sobre cómo cambiar la zona horaria de las apps existentes.

### Atribución de fuentes multicanal

Un usuario puede interactuar con un anuncio de la misma app en varias plataformas, especialmente en campañas multiplataforma muy grandes. Cuando el usuario instala la app, varias plataformas pueden atribuirse la instalación.

Snapchat Ads Manager:

* Cuenta cada instalación que se produce dentro de la ventana de atribución como una instalación atribuida a Snapchat.
* Atribuye eventos in-app hasta 28 días después de la instalación.

AppsFlyer

* Aplica la atribución de último toque y atribuye el mérito únicamente a la última plataforma que mostró al usuario un anuncio que dio lugar a una instalación.
* Atribuye los eventos in-app a la fuente de la instalación durante un máximo de 180 días.

Esto puede dar lugar a discrepancias de hasta el 40% entre AppsFlyer y Snapchat Ads Manager.

> 👍 **SOLUCIÓN**
>
> Snapchat es solo una aplicación móvil, mientras que otras plataformas tienen varias aplicaciones móviles o ad networks/intercambios de anuncios para móviles. Debido a su alcance adicional en varias propiedades, es posible que la competencia gane el último toque y, aun así, Snapchat siga generando un valor significativo.
>
> En última instancia, AppsFlyer debe ser el dashboard que se utilice para evaluar el eCPI y el rendimiento. Cuando haya una discrepancia, usa AppsFlyer como fuente de referencia. Recuerda que, para evaluar por completo el impacto de tus campañas de Snapchat, debes trabajar con AppsFlyer para mantener un registro del volumen de conversiones en las que Snapchat contribuyó a la conversión, pero no fue el último toque. Es útil entender esto incluso si atribuyes en función del último toque.
>
> Para gestionar la discrepancia, los anunciantes deben mantener registros del porcentaje aproximado del total de conversiones en las que Snapchat contribuyó, pero no fue el último contribuyente y, en consecuencia, crear un nuevo objetivo de eCPI para Snapchat en función de este delta aproximado.

### Menos instalaciones en raw data

En algunos casos, debido a las restricciones de raw data de Snapchat, las instalaciones a través de <Anchor target="_blank" href="/marketers/es/docs/appsflyer-knowledge-base-glossary?query=glossary#aggregated-advancedprivacy">Aggregated Advanced Privacy</Anchor> no aparecerán en los Reportes de raw data. Esto significa que los anunciantes pueden ver en la plataforma de AppsFlyer menos instalaciones en raw data que en Datos agregados.

> 📄 **Ver también**
>
> <Anchor target="_blank" href="/marketers/es/docs/skan-interoperation-with-snapchat">Interoperabilidad de Snapchat y SKAdNetwork de AppsFlyer</Anchor>

<div data-zendesk-anchors="source-of-discrepancies-and-solutions=fuentes-de-discrepancias-y-soluciones h_01HE7RM7ME5JTFFC2MYSBG6SWC=fuentes-de-discrepancias-y-soluciones different-lookback-windows=diferentes-ventanas-de-lookback h_01HE7RM7MEYAZ42A1Y7X8J008Q=diferentes-ventanas-de-lookback h_01HE7RM7ME31WACZRZDXRW5CNR=soluciones time-zone-differences=diferencias-en-la-zona-horaria h_01HE7RM7METGPE38QV8FAMW9WA=diferencias-en-la-zona-horaria h_01HE7RM7MEC91WZDZQMXZ4Q7DV=soluci%C3%B3n multichannel-source-attribution=atribuci%C3%B3n-de-fuentes-multicanal h_01HE7RM7ME2NAB9ET38P5JD82E=atribuci%C3%B3n-de-fuentes-multicanal h_01HE7RM7MFP65KYHFDZZTC8K3J=soluci%C3%B3n-1 fewer-installs-in-raw-data=menos-instalaciones-en-raw-data h_01HE7RM7MFR4CSEK2HCZWB8BT9=menos-instalaciones-en-raw-data h_01HE7RP6VPPAY2CCSNTJ0RVSXM=ver-tambi%C3%A9n" />
