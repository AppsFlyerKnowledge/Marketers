---
title: Tipos de engagement enriquecidos
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2024-01-21T13:45:23Z'
  edited_at: '2026-08-12T11:56:33Z'
  id: 21837486015889
  locale: es
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/es/articles/21837486015889
---
> **En resumen:** Aunque los tipos de anuncios se han vuelto sofisticados y complejos, los reportes han seguido siendo muy limitados, centrándose únicamente en la atribución por impresiones y por clics. Los tipos de engagement enriquecidos cambian esta situación al reflejar todo el espectro de engagement e intencionalidad de los usuarios cuando ven un anuncio o interactúan con él.

## Introducción

En los últimos años, se han introducido en el mercado nuevos tipos de anuncios creativos, como los que se pueden reproducir, los que se pueden saltar y los anuncios de vídeo de formato corto, que ofrecen nuevas formas de conectar con los usuarios. Estos nuevos tipos de anuncios difieren significativamente de los banners estáticos y las unidades de vídeo de baja fidelidad del pasado y ofrecen a los anunciantes capacidades y formatos más amplios.

Sin embargo, aunque los tipos de anuncios se han vuelto más sofisticados, más complejos y más interactivos, los reportes han seguido siendo muy limitados, centrándose únicamente en la atribución por impresiones y por clics. Los distintos tipos de engagements tienen diferente peso, nivel de intención e impacto, pero las metodologías de medición actuales han pasado por alto esta nueva realidad. Naturalmente, las ad networks quieren asegurarse de que los niveles de intención y engagement se representen lo mejor posible, lo que ha llevado a una falta de normalización en todo el ecosistema. En última instancia, esto hace que los anunciantes sólo obtengan una comprensión parcial del rendimiento de su inversión publicitaria.

En colaboración con las principales redes, AppsFlyer está introduciendo una nueva norma para que los engagements ofrezcan confianza y transparencia en todo el ecosistema. Los tipos de engagement enriquecidos reflejan todo el espectro de engagement e intencionalidad de los usuarios cuando ven un anuncio o interactúan con él, desde la exposición momentánea hasta la respuesta directa. Este framework garantiza que estas normas se mantengan en todo el ecosistema de partners de AppsFlyer y más allá. A través de tipos de engagement enriquecidos, los anunciantes pueden asegurarse de tener una imagen altamente coherente y rica del rendimiento de su gasto publicitario y pueden aprovechar estos insights para mejorar la asignación del presupuesto y aumentar el ROAS.

## ¿Cuáles son los tipos de engagement enriquecido?

El framework de Tipos de Engagement Enriquecido (EET) proporciona visibilidad a las sutilezas del viaje del usuario, al indicar cuándo las vistas fueron atractivas (por ejemplo, cuando un usuario ve un anuncio de video que se puede omitir durante al menos 5 segundos después de que aparece la opción de omitir) y cuándo los clics llevaron a algo diferente a la apertura de la aplicación o a la tienda de aplicaciones. De este modo, los marketers obtienen más insights sobre las acciones de sus usuarios, lo que a su vez permite asignar mejor el presupuesto y mejorar el ROI.

La siguiente es la lista de los tipos de engagement enriquecidos:

| tipo\_de\_engagement | Descripción |
| --- | --- |
| <span id="preload"></span>Precarga | La app la precarga el OEM de fábrica o el proveedor la primera vez que se activa el dispositivo. Alternativamente, un asistente pide a los usuarios que descarguen la aplicación cuando el dispositivo se activa por primera vez. |
| <span id="click_to_download"></span>click\_to\_download | Cuando el usuario hace clic en un anuncio, la app se descarga e instala automáticamente en el dispositivo sin redireccionarlo a una app store. |
| <span id="click_to_app"></span>click\_to\_app | Un clic en un anuncio, el escaneo de un QR code, un deep link o cualquier otro clic que redireccione al usuario a la aplicación o a la app store correspondiente para descargar la aplicación. |
| <span id="engaged_click"></span>engaged\_click | Un clic que mantiene al usuario en el mismo contexto, interactuando con el anuncio, y NO lo redirecciona a la tienda de apps o a iniciar la aplicación. |
| <span id="engaged_view"></span>engaged\_view | Es cuando se produce una engaged view, dentro de vídeos que se pueden omitir, vídeos recompensados o anuncios renderizados en Storekit. Por ejemplo, cuando un usuario ve un anuncio de video que se puede omitir durante al menos 5 segundos después de que aparece la opción de omitir. |
| <span id="view"></span>Ver | Un ad view es cuando se muestra un anuncio y se produce una impresión. |
| <span id="listening"></span>listening | El listening se produce cuando un usuario escucha un anuncio de audio, como un anuncio de podcast. |

## **Prioridad de atribución EET y ventana de lookback**

El framework de Tipos de Engagement Enriquecidos no afecta la prioridad de atribución del tipo de engagement. Por lo tanto, se espera que la introducción de EET no afecte tu tasa de instalación y conversión.

La tabla a continuación especifica la <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model#prioridades-de-los-métodos-de-atribución-cascada-de-atribución">prioridad de atribución</Anchor> y la <Anchor target="_blank" href="/marketers/es/docs/set-up-lookback-windows#ventanas-de-lookback">ventana de lookback</Anchor> de cada tipo de engagement:

<table><thead><tr><th>Participación</th><th>Tipo de engagement</th><th>Prioridad de atribución\*</th><th>Ventana de lookback\*\*</th></tr></thead><tbody><tr><td rowspan="2">Descargar</td><td>Precarga</td><td>1</td><td>1h-180d | predeterminado: 90d</td></tr><tr><td>click_to_download</td><td>2</td><td>1h-30d | predeterminado: 7d</td></tr><tr><td rowspan="2">Clic</td><td>click_to_app</td><td>2</td><td>1h-30d | predeterminado: 7d</td></tr><tr><td>engaged_click</td><td>2</td><td>1h-7d | predeterminado: 2d </td></tr><tr><td rowspan="3">Impresión</td><td>engaged_view</td><td>2</td><td>1h-7d | predeterminado: 2d</td></tr><tr><td>Ver</td><td>3</td><td>1h-24h | predeterminado: 24 horas</td></tr><tr><td>listening</td><td>3</td><td>1h-24h | predeterminado: 24 horas</td></tr></tbody></table>

*Cuando no se informa un tipo de engagement, se establece la prioridad predeterminada (2 para clics, 3 para impresiones).

<strong>Las ventanas de lookback para `engaged_click` y `engaged_view` solo se pueden establecer para redes que no son SRNs. Para los SRN, `engaged_click` y `engaged_view` comparten la misma ventana de lookback que los clics y, por lo tanto, se establecen mediante </strong>Install Click-Through Attribution Lookback.

## ¿Qué redes pueden reportar sobre view engaged y engaged clicks?

La tabla a continuación enumera las redes que están calificadas por AppsFlyer para reportar `engaged_clicks` y `engaged_views`.  Las redes que deseen unirse a esta lista deben contactar al soporte de AppsFlyer.

| **Ad network** | **Vistas involucradas** | **Engaged clicks** |
| --- | --- | --- |
| facebook\_int | Sí |  |
| googleadwords\_int | Sí |  |
| tiktokglobal\_int* | Sí | Sí |
| twitter\_int | Sí | Sí |
| "snapchat\_int" | Sí | Sí |
| bytedanceglobal\_int | Sí | Sí |
| aarki\_int | Sí | Sí |
| adjoe\_int |  | Sí |
| appier\_int | Sí | Sí |
| appnext\_int | Sí |  |
| bidease\_int | Sí | Sí |
| bigabid\_int | Sí | Sí |
| inmobidsp\_int | Sí | Sí |
| ironsource\_int | Sí |  |
| lap\_int | Sí |  |
| liftoff\_int | Sí | Sí |
| mdsp\_int | Sí | Sí |
| mintegral\_int | Sí | Sí |
| onedigitalturbine\_int | Sí |  |
| personalyrtb\_int | Sí | Sí |
| pinterest\_int | Sí |  |
| remerge\_int | Sí | Sí |
| revx\_int | Sí | Sí |
| rtbhouse\_int | Sí | Sí |
| smadex\_int | Sí | Sí |
| trademob\_int | Sí | Sí |
| unityads\_int | Sí | Sí |
| vungle\_int | Sí |  |
| yahoojapan\_int | Sí |  |
| yandexdirect\_int | Sí | Sí |
| youappi\_int | Sí | Sí |
| jampp\_int | Sí | Sí |

* TikTok apoya el tipo de engagement enriquecido, pero sus engaged views actualmente no se reflejan correctamente en los reportes. AppsFlyer está trabajando con TikTok para resolver este problema.

> 📘 **Nota:**
>
> **No todas las redes elegibles enumeradas realmente admiten engaged clicks y engaged views.** Para averiguar si una red apta en particular admite en la práctica `engaged_clicks` y `engaged_views`. Para averiguar si una red elegible en particular admite `engaged_clicks` y `engaged_views` en la práctica, consulta el reporte de raw data que contiene los engagements reportados por la red y comprueba si el parámetro `engagement_type` contiene los valores anteriores.

## Establecer ventanas de lookback para engaged clicks y engaged views

**Para establecer las ventanas de lookback para engaged clicks y engaged views:**

1. En AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Integraciones activas**.
2. Selecciona el partner integrado.
3. Establece las ventanas de lookback para engaged view-through y atribución click-through.

   > 📘 **Nota:**
   >
   > Las ventanas de lookback de engaged clicks y engaged views siempre se establecen en la pestaña de **Integración de partners**, a diferencia de las ventanas de lookback de view-through y click-through, que se pueden establecer en los enlaces de atribución.
   >
   > La configuración de la ventana de lookback de click-through también determina las ventanas de lookback de engaged clicks y engaged views.

4. Haz clic en **Guardar integración**.

## Ver y analizar datos de EET

### Reportes de raw data

`engagement_type` se incluirán en los reportes de raw data siempre que los reporte la ad network. También estará disponible para los datos de los contribuyentes.

> 📘 **Nota:**
>
> Las engaged views siempre se incluyen en los reportes de raw data, incluso cuando la atribución de view-through está desactivada.

Cuando no se registren clics, como en los casos de precarga o deep linking, AppsFlyer establecerá el valor correspondiente (precarga o `click_to_app` para deep links) dentro del nuevo campo `engagement_type` en los reportes de raw data.

Los siguientes escenarios resultarán en que el campo `engagement_type` en los reporte de raw data reciba los valores `click_unspecified` y `impression_unspecified`.

* Cuando hay una discrepancia entre el engagement (clic/impresión) y el tipo de engagement.
* Cuando `af_engagement_type` no se envía o se envía con un valor vacío.

Para ver el tipo de engagement en los reportes de raw data, los anunciantes deben seleccionar estos campos en el producto de raw data correspondiente (el tipo de engagement y el tipo de engagement de los colaboradores no están seleccionados por defecto).

### Paneles de control

Se ha añadido la dimensión de tipo de engagement en los dashboards.

[![eet-dashboard.png](https://files.readme.io/d32fd98394a8025fb438259f5f058daed0daf297301b0cf4fbfbade0ece5d76f-27059768599569.png)](https://files.readme.io/d32fd98394a8025fb438259f5f058daed0daf297301b0cf4fbfbade0ece5d76f-27059768599569.png)

> 📘 **Nota:**
>
> Las engaged views siempre son visibles en el dashboard, incluso cuando la atribución view-through está desactivada.

### Cómo calcular **instalaciones por mil** (IPM)

Las impresiones totales incluyen tanto engaged views como vistas regulares. Para calcular el IPM, debes **restar las engaged views de las impresiones totales** porque las vistas engaged views son un subconjunto de las impresiones, y contarlas dos veces aumentaría el conteo de impresiones.

## Preguntas Frecuentes

<div id="what-kinds-of-campaigns-are-relevant-for-enriched-engagement-types" />

<Accordion title="¿Qué tipos de campañas son relevantes para los tipos de engagement enriquecidos?">

Los tipos de engagement enriquecidos puede aplicarse tanto a campañas de UA como de retargeting, según la red correspondiente. Para saber si una red admite campañas de retargeting, consulta los reportes de raw data de la red y comprueba si `engagement_type` está rellenado para la campaña de retargeting.

</Accordion>

<div id="are-engaged_clicks-and-engaged_views-included-in-the-aggregate-numbers-of-clicks-and-impressions-on-the-overview-dashboard" />

<Accordion title="¿Se incluyen los engaged clicks y las engaged views en el número total de clics e impresiones del dashboard general?">

En las redes que no son SRNs, estas cifras se incluyen y contabilizan según el tipo de touch (es decir, los engaged clicks se contabilizan como clics y las engaged views como impresiones). En el caso de los SRN, actualmente no se incluye ni se cuenta, a la espera de que las API de los SRN lo admitan.

</Accordion>

<div id="why-cant-i-see-the-engagement-type-in-metas-gp_referrer-conversions" />

<Accordion title="¿Por qué no puedo ver el tipo de engagement en las conversiones gp_referrer de Meta?">

Meta solo reporta sobre engagement\_type=engaged\_view en su API SRN. No hay un valor de engagement\_type disponible para otras conversiones, incluyendo gp\_referrer.

</Accordion>

<div id="why-cant-i-see-the-engagement-type-i2" />

<Accordion title="¿Por qué sigo viendo instalaciones y re-engagements con attributed_touch_type = impression incluso después de desactivar las opciones de view-through?">

Las engaged views se miden y reportan incluso si los interruptores de **view-through** están desactivados. Para identificar esas impresiones como engaged views, utiliza la métrica `engagement_type = engaged_views` en los dashboards y en los reportes de raw data en lugar de basarte únicamente en `attributed_touch_type`.

</Accordion>

## Características y limitaciones

| Caducado | Observaciones |
| --- | --- |
| <span id="cross-platform-engaged-view-support"></span>Soporte de engaged view multiplataforma | Los tipos de engagement mejorados aún no son compatibles en casos de uso multiplataforma. Incluso cuando se envía `engaged_view` en la URL de impresión, los partners y anunciantes verán `view` en los datos de atribución. |
| <span id="owned-media-support"></span>Soporte de medios propios | Actualmente no se admiten medios propios. Los enlaces utilizados en medios propios no deben incluir el parámetro `af_engagement_type`. |

<div data-zendesk-anchors="introduction=introducci%C3%B3n h_01HNCNA03SZ0MJFQ9XHDFXNTA1=introducci%C3%B3n enriched-engagement-types=cu%C3%A1les-son-los-tipos-de-engagement-enriquecido h_01HNCNBR7KMT1KQBG5CPZY8YQY=cu%C3%A1les-son-los-tipos-de-engagement-enriquecido eet-attribution-priority-and-lookback-window=prioridad-de-atribuci%C3%B3n-eet-y-ventana-de-lookback h_01HNCVYDH17NGA8SH5XNWR4P9X=prioridad-de-atribuci%C3%B3n-eet-y-ventana-de-lookback allowed-networks=qu%C3%A9-redes-pueden-reportar-sobre-view-engaged-y-engaged-clicks h_01J00XFV136HPEHVQNPD934409=qu%C3%A9-redes-pueden-reportar-sobre-view-engaged-y-engaged-clicks 01JENXRAMPFXTMF7SKDN2Y0E5M=nota set%C2%A0engaged-enrichment-attribution=establecer-ventanas-de-lookback-para-engaged-clicks-y-engaged-views h_01J5B6EVM9P3M1SVR3K7WWK02J=establecer-ventanas-de-lookback-para-engaged-clicks-y-engaged-views h_01J5B97RCQQG6GN4PCKTQWVF54=nota-1 reporting=ver-y-analizar-datos-de-eet h_01J00XFV13YN8QNFZJTGM78EG2=ver-y-analizar-datos-de-eet raw-data=reportes-de-raw-data h_01J00XFV132M8TM6EGFZ7A7C3A=reportes-de-raw-data 01JFCPX6WKCWY9RM470H23EDQ0=nota-2 dashboards=paneles-de-control h_01J00XFV13W0SD4MD7H4BT1RC9=paneles-de-control 01JFCPX6WNCFC0R0N90G4HFYZX=nota-3 how-to-calculate-installs-per-mille-ipm=c%C3%B3mo-calcular-instalaciones-por-mil-ipm h_01JHG3EQN6FNJAHX1S91JE3MPT=c%C3%B3mo-calcular-instalaciones-por-mil-ipm faqs=preguntas-frecuentes 01JFCKK7FK0B5Z7QCZNSX14WF2=preguntas-frecuentes h_01HNFTS74KF3YFA0SWRGEQAGYQ=what-kinds-of-campaigns-are-relevant-for-enriched-engagement-types h_01HNYY1S6YQ6YNR6RSY7B8H4EM=are-engaged_clicks-and-engaged_views-included-in-the-aggregate-numbers-of-clicks-and-impressions-on-the-overview-dashboard h_01HQG5Y4JVNCB60AXR9K2GGD0H=why-cant-i-see-the-engagement-type-in-metas-gp_referrer-conversions h_01JJP3TT2QMH5Y94C4Q7V6HFP1=why-cant-i-see-the-engagement-type-i2 cross-platform-traits-limitations=caracter%C3%ADsticas-y-limitaciones traits-and-limitations=caracter%C3%ADsticas-y-limitaciones" />
