---
title: Selecciona los parámetros de atribución para las URLs de las landing pages
metadata:
  keywords:
    - Agencies
    - Web Attribution
    - Web Attribution SDK
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
    - Agencies
  created_at: '2026-02-04T16:46:08Z'
  edited_at: '2026-08-12T12:10:51Z'
  id: 43525434385809
  locale: es
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/es/articles/43525434385809
---
> **De un vistazo:** Usa parámetros de URL coherentes y completos en los enlaces a las páginas de destino de tu sitio web para obtener la mejor granularidad de campaña y, al mismo tiempo, mantener una atribución precisa en Web Performance Measurement.

## Información sobre las clases de parámetros de atribución de URL

AppsFlyer lee los parámetros de campaña de la URL de tu página de destino (el enlace en el que hace clic un usuario) y los usa para atribuir sesiones y eventos a la **fuente de medios**, la **campaña** y (cuando está disponible) a niveles más profundos de la jerarquía, como el **conjunto de anuncios** y el **anuncio**, correctos.

Los parámetros que incluyes determinan los resultados de medición de tu campaña. En otras palabras, la misma página de destino puede producir resultados muy distintos según los parámetros que incluyas.

Los parámetros de URL pueden pertenecer a una de estas dos clases: PID y UTM.

* La clase PID incluye los parámetros de URL de AppsFlyer.
* La clase UTM incluye los parámetros UTM estándar.

Para obtener más información sobre cómo Web Performance Measurement procesa los parámetros de URL, consulta <Anchor target="_blank" href="/marketers/es/docs/about-traffic-source-resolution">Información sobre la resolución de la fuente de tráfico</Anchor>.

### Parámetros PID y UTM compatibles

Web Performance Measurement admite los siguientes parámetros.

| # | Parámetro | Usado para | Clase de parámetros | Disponible en el dashboard | Campo de raw data |
| --- | --- | --- | --- | --- | --- |
| 1 | `PID` | Nombre de la app | PID no integrados. | Sí | `fuente_de_medios` |
| 2 | `C` | Nombre de la campaña | PID no integrados. | Sí | `campaign_name` |
| 3 | `af_c_id` | ID de campaña | PID no integrados. | Sí | `id_campaña` |
| 4 | `af_conjunto de anuncios` | Nombre de conjunto de anuncios | PID no integrados. | Sí | `adset_name` |
| 5 | `af_adset_id` | ID de conjunto de anuncios | PID no integrados. | Sí | `id_anuncio` |
| 6 | `af_anuncio` | Nombre de anuncio | PID no integrados. | Sí | `ad_name` |
| 7 | `id_del_anuncio_af` | ID de anuncio | PID no integrados. | Sí | `id_adset` |
| 8 | `utm_source` | Nombre de la app | UTM | Sí | `fuente_de_medios` |
| 9 | `utm_medium` | Media Type | UTM | No | `media_type` |
| 10 | `utm_campaign` | Solo disponible en <Anchor target="_blank" href="/marketers/es/docs/about-data-locker-advanced-reports">reportes avanzados</Anchor>. | UTM | Sí | `campaign_name` |

## Elige los parámetros de atribución adecuados

AppsFlyer evalúa los parámetros de URL de forma independiente para cada campo de reporte (como Fuente de medios o Campaña) mediante una cascada de prioridades específica. Este enfoque te permite usar la atribución de AppsFlyer junto con otras herramientas, como Google Analytics, mediante el uso de la **clase PID** (nativa de AppsFlyer) y la **clase UTM** (marketing estándar) en la misma URL.

Web Performance Measurement comprueba el orden de prioridad de cada campo por separado. Si no existe un parámetro de la clase PID de mayor prioridad para un atributo específico, el sistema recurre automáticamente al parámetro correspondiente de la clase UTM para determinar el valor correcto de ese campo.

<div id="scenario-a-url-with-pid-class-only-appsflyer-reporting" />

<Accordion title="Escenario A. URL solo con la clase PID (reporte de AppsFlyer)">

Usa la clase PID cuando los informes de AppsFlyer sean tu objetivo principal.

#### Ejemplo

```http
www.website.com?pid=facebook_int&c={{campaign.name}}&af_c_id={{campaign.id}}
```

**Resultado**: AppsFlyer identifica la fuente de medios mediante `pid` y la campaña mediante `c`.

</Accordion>

<div id="scenario-b-url-with-utm-class-only-fallback" />

<Accordion title="Escenario B. URL solo con la clase UTM (alternativa)">

Si falta `pid`, AppsFlyer recurre a la clase UTM.

#### Ejemplo

```http
 www.website.com?utm_source=facebook&utm_medium=paidsocial&utm_campaign={{campaign.name}}
```

**Resultado**: AppsFlyer identifica la fuente de medios mediante `utm_source` y la campaña mediante `utm_campaign`.

</Accordion>

<div id="scenario-c-url-with-both-pid-and-utm-classes" />

<Accordion title="Escenario C. URL con clases PID y UTM">

AppsFlyer te permite incluir parámetros de distintas clases (por ejemplo, PID y UTM) en la misma URL. Esto es útil cuando necesitas dar soporte a la atribución de AppsFlyer junto con otras herramientas de analítica, como Google Analytics o sistemas internos de medición.

AppsFlyer procesa los campos de atribución, como Fuente de medios y Campaña, de forma independiente. Para cada campo específico, el sistema sigue una cascada de prioridad para determinar qué valor registrar. Por lo general, la **clase PID** tiene prioridad sobre la **clase UTM** para ese campo específico.

#### Ejemplo 1: Parámetros superpuestos

```http
www.website.com?pid=facebook_ads&c=summer_sale&utm_source=facebook&utm_campaign=seasonal_promo
```

* **Fuente de medios:** AppsFlyer detecta tanto `pid` como `utm_source`. Siguiendo la cascada de prioridad de este campo, registra `facebook_ads`.
* **Campaña:** AppsFlyer detecta tanto `c` como `utm_campaign`. Siguiendo la cascada de prioridad de este campo, registra `summer_sale`.
* **Resultado:** AppsFlyer usa los valores de la clase PID, que tiene mayor prioridad, mientras que las herramientas externas aún pueden leer los valores UTM.

#### Ejemplo 2: Clases de parámetros mixtas

```http
www.website.com?utm_source=facebook&c=summer_sale
```

* **Fuente de medios:** AppsFlyer detecta `utm_source`. Como no hay ningún equivalente de la clase PID (`pid`), registra `facebook` de la clase UTM.
* **Campaña:** AppsFlyer detecta `c`. Como no hay ningún equivalente de la clase UTM (`utm_campaign`), registra `summer_sale` de la clase PID.
* **Resultado:** AppsFlyer atribuye correctamente el evento usando valores de ambas clases, porque cada campo se resuelve de forma independiente.

</Accordion>

## Otras Mejores prácticas

<div id="keep-parameter-values-in-a-consistent-case" />

<Accordion title="Mantén los valores de los parámetros en un caso coherente">

Los valores de los parámetros **distinguen mayúsculas de minúsculas**. Por ejemplo, `utm_source=channel1` y `utm_source=CHANNEL1` se tratan como **fuentes de medios diferentes**.

Mejores prácticas: Define una convención de uso de mayúsculas y minúsculas (lo habitual es usar minúsculas) y aplícala en todas las URL.

</Accordion>

<div id="use-question-marks-only-once" />

<Accordion title="Usa los signos de interrogación solo una vez">

Rules:

* Usa solo **un** signo de interrogación (`?`) antes de los parámetros de consulta en la URL.
* No uses signos de interrogación adicionales en la URL.

Correcto:

* `www.website.com?parameters`

Incorrecto:

* `www.website.com??parameters`
* `www.website.com?parameter1?parameter2`

</Accordion>

<div id="don-t-use-anchor-signs" />

<Accordion title="No uses signos de anclaje (#)">

No uses signos de anclaje (`#`) en la URL.

Por qué: es posible que los parámetros que van después de `#` no se carguen ni se registren en el SDK web.

</Accordion>

<div data-zendesk-anchors="about-website-attribution-urls=informaci%C3%B3n-sobre-las-clases-de-par%C3%A1metros-de-atribuci%C3%B3n-de-url h_01KGMRXNWGXQ3CH5XGSREV6Z3R=informaci%C3%B3n-sobre-las-clases-de-par%C3%A1metros-de-atribuci%C3%B3n-de-url supported-pid-and-utm-parameters=par%C3%A1metros-pid-y-utm-compatibles h_01KGMRXNWG88REW1CVJ4XMYFHQ=par%C3%A1metros-pid-y-utm-compatibles choose-the-right-attribution-parameters=elige-los-par%C3%A1metros-de-atribuci%C3%B3n-adecuados h_01KGMRXNWGP1SFBWE3KG6VRZ9V=elige-los-par%C3%A1metros-de-atribuci%C3%B3n-adecuados h_01KGMRXNWGT9MS799QH9EP29XR=scenario-a-url-with-pid-class-only-appsflyer-reporting example=ejemplo h_01KGMS1RMN3F1D0Q7HDZMGG19E=ejemplo h_01KGMRXNWG0T3YCK0RPKX4B3BT=scenario-b-url-with-utm-class-only-fallback example::4f5c28b5=ejemplo-1 h_01KGMS215ARDSY6NFQ8VEF6C2Y=ejemplo-1 h_01KGMRXNWGZH2ZBP9XR8C8TNFN=scenario-c-url-with-both-pid-and-utm-classes example-1-overlapping-parameters=ejemplo-1-par%C3%A1metros-superpuestos h_01KGMS10B1QCRJ5N28FBNEEKR2=ejemplo-1-par%C3%A1metros-superpuestos example-2-mixed-parameter-classes=ejemplo-2-clases-de-par%C3%A1metros-mixtas h_01KGMS17B500RPGHSKJ1AJSYH8=ejemplo-2-clases-de-par%C3%A1metros-mixtas other-best-practices=otras-mejores-pr%C3%A1cticas h_01KGMRXNWGVJY55M83FVMKBP1X=otras-mejores-pr%C3%A1cticas h_01KGMRXNWG9S03GGBDXPN34DDM=keep-parameter-values-in-a-consistent-case h_01KGMRXNWGEF9D0ZH5M81RP0PH=use-question-marks-only-once don%E2%80%99t-use-anchor-signs-=don-t-use-anchor-signs h_01KGMRXNWGX6HA0R9X3VC2WFXV=don-t-use-anchor-signs" />
