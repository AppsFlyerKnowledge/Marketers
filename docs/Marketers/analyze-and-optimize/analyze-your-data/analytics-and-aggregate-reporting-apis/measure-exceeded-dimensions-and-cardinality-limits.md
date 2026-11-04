---
title: Acerca de los límites de dimensiones y cardinalidad superados
metadata:
  keywords:
    - performance reports
    - Advertisers
    - exceeded
    - reports
    - faq
    - Agencies
    - Exceeded_Events_Limit
    - Exceeded Events Limit
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
  created_at: '2017-10-08T15:20:55Z'
  edited_at: '2026-08-12T11:49:51Z'
  id: 115005099063
  locale: es
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/es/articles/115005099063
---
> **De un vistazo:** Por qué algunas dimensiones de datos agregados se muestran como *superadas* y cómo evitar que se alcancen los límites de cardinalidad.

<div id="what-are-exceeded-dimensions" />

## ¿Qué son las dimensiones superadas?

AppsFlyer recopila tus datos de instalación y eventos y los agrega. Los datos se agregan mediante valores únicos que llenan una dimensión determinada. El número de valores únicos en una dimensión se denomina cardinalidad. La mayoría de las herramientas de análisis y reportes agregados tienen límites de cardinalidad por dimensión. Cuando el número de valores únicos de una dimensión supera el límite de cardinalidad, los datos restantes se agrupan en un grupo *superado*. Y cuando el número de valores únicos en la dimensión de la fuente de medios supera el límite de cardinalidad, los datos restantes de la fuente de medios, **así como todas las dimensiones basadas en las fuentes de medios restantes**, se agrupan en grupos *superados*.

Los siguientes ejemplos ilustran la cardinalidad y cómo afecta a tus reportes.

<div id="example" />

> 📄 **Ejemplo**
>
> **Ejemplo A: Límite de cardinalidad del identificador de campaña**
>
> El límite de cardinalidad del identificador de campaña es de 3000. Si el número de ID de campaña declarados en un día determinado supera los 3000, los ID de campaña restantes se agrupan en Exceeded\_CampaignId\_Limit.
>
> **Ejemplo B: Límite de cardinalidad de eventos**
>
> * Piensa que el límite de cardinalidad de los eventos es 3.
> * En un día determinado, se reportan 7 eventos únicos: A, B, C, D, E, F y G. En otras palabras, la cardinalidad de los eventos es 7.
> * En los reportes agregados, los eventos A, B y C se enumeran por separado. Los eventos D, E, F y G se agrupan en Exceeded\_Events\_Limit.

Las dimensiones y los límites de cardinalidad superados afectan a los datos agregados de la siguiente manera:

* Panel de vista general
* Reportes de API de extracción y exportación de datos agregados
* Reportes de la API maestra
* Datos de clics e impresiones en los paneles de actividad y personalizados
* Panel de control de Protect360

Los raw data no se ven afectados por los límites de cardinalidad.

Si una gran parte de los datos se agrupan en grupos *superados*, esos datos no se desglosan. Esto puede generar resultados imprecisos en los reportes de análisis. Si es necesario, utiliza raw data para crear agrupaciones sin límites de cardinalidad.

La siguiente tabla muestra los límites de cardinalidad por día y por aplicación.

<table><tbody><tr><th>Dimensión</th><th>Nombre de grupo excedido</th><th>Tipo de límite por...</th><th>Límite de cardinalidad por día </th><th>Cardinalidad para Protect360 por día</th></tr><tr><td>Anuncio</td><td>Límite de anuncios superado</td><td>Fuente de medios</td><td>1000</td><td>-</td></tr><tr><td>ID de anuncio</td><td>Exceeded_AdID_Limit</td><td>Fuente de medios</td><td>1000</td><td>-</td></tr><tr><td>Conjunto de anuncios</td><td>Límite de conjuntos de anuncios superado</td><td>Fuente de medios</td><td>1000</td><td>-</td></tr><tr><td>ID de conjunto de anuncios</td><td>Exceeded_AdSetID_Limit</td><td>Fuente de medios</td><td>1000</td><td>-</td></tr><tr><td>Campaña</td><td>Exceeded_Campaign_Limit</td><td>Fuente de medios</td><td>3000</td><td><ul><li>Instalaciones/eventos in-app: 3000</li><li>Impresiones, clics 100 </li></ul></td></tr><tr><td>ID de campaña</td><td>Exceeded_CampaignID_Limit</td><td>Fuente de medios</td><td>3000</td><td><ul><li>Instalaciones/eventos in-app: 3000</li><li>Impresiones, clics 100 </li></ul></td></tr><tr><td>Canal</td><td>Límite de canales superado</td><td>Fuente de medios</td><td>20</td><td>20</td></tr><tr><td>ID de sitio</td><td>Exceeded_SiteID_Limit</td><td>Fuente de medios</td><td>1000\*\*</td><td><ul><li>Instalaciones/eventos in-app: 1000</li></ul></td></tr><tr><td>Eventos</td><td>Exceeded_Events_Limit</td><td>Aplicación </td><td>300</td><td>Instalaciones/eventos in-app: 300</td></tr><tr><td>Palabras clave</td><td>Límite de palabras clave superado</td><td>Fuente de medios</td><td>1000</td><td>-</td></tr><tr><td>Nombre de fuente de medios.</td><td>Límite de fuente de medios superado</td><td>Aplicación</td><td>1000</td><td><ul><li>Instalaciones/eventos in-app: 1000</li><li>Impresiones, clics 100 </li></ul></td></tr><tr><td colspan="5"><p>\* Si <span>el número de valores únicos en la dimensión de la fuente de medios supera el límite de cardinalidad, los datos restantes de la fuente de medios</span>, <strong>así como todas las dimensiones basadas en las fuentes de medios restantes</strong>, <span>se agrupan en</span> <span>grupos</span> <em>superados</em>.</p><p><span>\*\* Consulta <a href="./measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">Exceeded_SiteID_Limit</a> para obtener más detalles y conocer los límites.</span></p></td></tr></tbody></table>

<div id="cardinality-limits-per-dimension" />

## Límites de cardinalidad por dimensión

<div id="exceeded_adset_limit-and-exceeded_ad_limit" />

<Accordion title="Exceeded_AdSet_Limit and Exceeded_Ad_Limit">

* Están disponibles hasta 1000 nombres de conjuntos de anuncios únicos y 1000 nombres de anuncios únicos por fuente de medios.
  * En un día determinado, la información del conjunto de anuncios del conjunto de anuncios número 1001 y superiores se agrupa en la fuente **Exceeded\_AdSet\_Limit**. Lo mismo se aplica a la fuente **Exceeded\_Ad\_Limit**.

<div id="tip" />

> 👍 **Consejo**
>
> «Divide y vencerás» de nuevo. Define un número reducido de nombres de conjuntos de anuncios generales (idealmente hasta 50) y asigna todos los nombres de conjuntos de anuncios anteriores como anuncios individuales. También puedes usar los parámetros **af\_sub** en los enlaces de atribución de AppsFlyer. Esto te permite:
> 1. prevenir ver **Exceeded\_AdSet\_Limit** o Exceeded\_Ad\_Limit.
> 2. Optimizar de manera eficiente de acuerdo con los conjuntos de anuncios y el tráfico de anuncios importantes.
> 3. Realzar un análisis profundo basado en el conjunto de anuncios y los nombres de los anuncios en los raw data.

</Accordion>

<div id="exceeded_adsetid_limit-and-exceeded_adid_limit" />

<Accordion title="Exceeded_AdSetID_Limit and Exceeded_AdID_Limit">

* Están disponibles hasta 1000 ID de conjunto de anuncios únicos y 1000 ID de anuncios únicos por fuente de medios.
  * En un día determinado, la información del ID del conjunto de anuncios del ID del conjunto de anuncios número 1001 y superiores se agrupa en la fuente **xceeded\_AdSetID\_Limit**. Lo mismo se aplica a la fuente **Exceeded\_ADID\_Limit**.

</Accordion>

<div id="exceeded_campaign_limit" />

<Accordion title="Exceeded_Campaign_Limit">

**[![](https://files.readme.io/6b96713b7a7ef6dc781fdd6d8b61507788bf79b452cfe2a3aa6fd80d7be71e0b-115016680246.png)](https://files.readme.io/6b96713b7a7ef6dc781fdd6d8b61507788bf79b452cfe2a3aa6fd80d7be71e0b-115016680246.png)**

* Hay disponibles hasta 3000 nombres de campaña únicos por día.
  * En un día, la información de la campaña número 3001 y posteriores se agrupa en la fuente **Exceeded\_Campaign\_Limit**.

<div id="tip-1" />

> 👍 **Consejo**
>
> Define un número reducido de nombres generales de campaña (idealmente hasta 300) y asigna todos los nombres de campañas anteriores como conjuntos de anuncios. En los enlaces de atribución de AppsFlyer, el parámetro es **af\_adset.** Esto te permite:
> 1. Evita ver **Exceeded\_Campaign\_Limit**.
> 2. Optimizar de manera eficiente de acuerdo con el tráfico significativo de los conjuntos de anuncios.
> 3. Realizar un análisis profundo en función de los nombres de las campañas y los conjuntos de anuncios de los raw data.

</Accordion>

<div id="exceeded_campaignid_limit" />

<Accordion title="Exceeded_CampaignID_Limit">

* Hay disponibles hasta 3000 ID de campaña únicos por día.
  * Durante un solo día, toda la información de la campaña del identificador de campaña número 3001 y posteriores se atribuye a la fuente **Exceeded\_CampaignID\_Limit**.

</Accordion>

<div id="exceeded_channels_limit" />

<Accordion title="Límite de canales superado">

* Están disponibles hasta 20 nombres de canales únicos por día por fuente de medios. Para Protect360, el límite es 1000.
  * En un día, toda la información del canal 21 y superior se atribuye a la fuente **Exceeded\_Channel\_Limit**.

</Accordion>

<div id="exceeded_events_limit" />

<Accordion title="Exceeded_Events_Limit">

* Hay disponibles hasta 300 nombres de eventos únicos por día.
  * En un día, toda la información del evento número 301 y posteriores se atribuye al nombre del evento denominado **Exceeded\_Events\_Limit**.

<div id="tip-2" />

> 👍 **Consejo**
>
> Para dejar de ver **Exceeded\_Events\_Limit**, considera usar:
>
> * <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview">Eventos in-app enriquecidos</Anchor>. En lugar de informar sobre cientos de eventos diferentes, define una pequeña cantidad de nombres de eventos generales (idealmente hasta 20). Utiliza valores de eventos dinámicos para diferenciar entre estos eventos. Esto te permite optimizar según los parámetros de los valores y realizar análisis en función de los valores de los eventos, que están disponibles a través del <Anchor target="_blank" href="/marketers/es/docs/raw-data-reporting-overview">reporte de raw data de eventos in-app</Anchor>.
> * <Anchor target="_blank" href="/marketers/es/docs/implement-validation-rules-to-prevent-fraud">Reglas de validación</Anchor> para eliminar los eventos in-app innecesarios de la plataforma AppsFlyer.

<div id="example-1" />

> 📄 **Ejemplo**
>
> Tu aplicación com.greatapp envía un evento in-app de compra desde la aplicación para cada color de calcetines que vende, por ejemplo, buy\_red\_socks, buy\_blue\_socks, buy\_white\_socks, etc. Para evitar esta inflación de diferentes eventos, redúzcalos todos a un solo evento, buy\_socks, e inserta el color como parámetro de <Anchor target="_blank" href="/marketers/es/docs/in-app-events-overview">evento</Anchor>.

</Accordion>

<div id="exceeded_keywords_limit" />

<Accordion title="Límite de palabras clave superado">

* Están disponibles hasta 1000 palabras clave únicas por día por fuente de medios.
  * En un día, la información de palabras clave de la palabra clave 1001 y superiores se agrupa en la fuente **Exceeded\_Keywords\_Limit**.

</Accordion>

<div id="exceeded_mediasource_limit" />

<Accordion title="Límite de fuente de medios superado">

* Hay disponibles hasta 1000 nombres de fuentes multimedia únicos por día.
  * En un día, la información de la campaña del nombre de la fuente de medios 1001st y superiores se agrupa en la fuente **Exceeded\_MediasSource\_Limit**.

</Accordion>

<div id="exceeded_siteid_limit" />

<Accordion title="Exceeded_SiteID_Limit">

El ID del sitio (por clics, impresiones, instalaciones y eventos in-app) tiene 2 umbrales: 1000 y 5000.

* Hay disponibles hasta 1000 ID de sitio únicos por día y por medio.
  * En un día, la información del identificador del sitio número 1001 y superior por fuente multimedia se agrupa en un único identificador de sitio denominado **Exceeded\_siteid\_limit.** Por lo tanto, si ves el ID del sitio **Exceeded\_siteid\_limit**, significa que hay demasiados ID de sitio usados por la fuente multimedia en cuestión, y tratar de optimizar el tráfico de la fuente de acuerdo con los ID del sitio se vuelve menos preciso y menos efectivo.
* A partir del 19 de agosto de 2024, si hay más de 5000 ID de sitio al día por fuente de medios, solo se muestran 10 ID de sitio. Todos los demás ID del sitio se agrupan en un único ID del sitio titulado **Exceeded\_SiteID\_Limit**.

<div id="tip-3" />

> 👍 **Consejo**
>
> «Divide y vencerás». En lugar de usar miles de ID de sitios por fuente multimedia, lo que distorsiona los datos agregados, usa un segundo parámetro en los enlaces de atribución llamado **af\_sub\_siteid.** Define un número reducido de ID de sitios generales (idealmente hasta 50) y asigna todos los ID de sitios anteriores como ID de subsitios en estos ID de sitios generales. Esto te permite:
> 1. Prevenir ver **Exceeded\_SITEID\_LIMIT**2. Optimizar de manera eficiente de acuerdo con el tráfico significativo de ID del sitio
> 3. Realizar un análisis profundo basado en los ID del sitio y los ID de los subsitios en los raw data.

<div id="note" />

> 📘 **Nota**
>
> En el reporte de retención, no ves un Exceeded\_SiteID\_Limit, pero no se muestran todos los ID de los sitios. Los ID de los sitios se muestran de forma aleatoria, pero es una limitación de la interfaz de usuario mostrarlos todos (cuando se ha superado el límite). Para solucionar este problema, recupera los datos de retención de la API maestra.

</Accordion>

<div id="how-to-avoid-getting-exceeded-sources" />

## ¿Cómo evitar que se superen las fuentes?

<div id="the-long-term-solution" />

### La solución a largo plazo

La mayoría de los anunciantes no encontrarán fuentes de **Exceeded** (superadas), ya que normalmente no definen 3000 campañas manualmente.

Si encuentras fuentes **Superadas**, probablemente se deba a que una o más fuentes multimedia utilizan valores dinámicos para los nombres de las campañas, los ID de los sitios, los conjuntos de anuncios o los anuncios. Los eventos in-app dinámicos en la aplicación dentro del código de la aplicación pueden hacer que aparezcan los datos de origen de **Exceeded\_Events\_Limit**.

<div id="tip-4" />

> 👍 **Consejo**
>
> Usa solo valores estáticos para los nombres de los eventos in-app, las campañas, los ID de sitios, los conjuntos de anuncios y los anuncios para evitar que se **Superen** las fuentes.
>
> Consulta también los consejos específicos de cualquier fuente de **Superada** anterior.

<div id="the-short-term-solution" />

### La solución a corto plazo

La solución a largo plazo puede tardar entre unos días y unas semanas en implementarse por completo.

Pero, ¿qué pasa si quieres ver tus datos ahora mismo?

Como se explicó antes, una fuente **Superada** ocurre cuando AppsFlyer recibe la fuente de N+1 clics (o eventos) durante un solo día. Es posible que las fuentes multimedia más destacadas que utilizas lleguen más tarde y, por lo tanto, se combinen con los datos de una fuente **Superada**. Este es un truco sencillo para minimizar el efecto de cualquier fuente **Superada** que veas.

<div id="tip-5" />

> 👍 **Consejo**
>
> Olvídate del presente y mira únicamente los datos de ayer y anteriores. Todos los días, un proceso de agregación recalcula los datos del último día y, en retrospectiva, asigna solo las fuentes más pequeñas (no las más tardías) a cualquier fuente **Superada.** ¡Esto asegura que la distorsión causada por el desbordamiento de clics sea mínima!

<div data-zendesk-anchors="what-are-exceeded-dimensions=qu%C3%A9-son-las-dimensiones-superadas h_01J1VY82KFVMRW99RK0SXWSEZ4=qu%C3%A9-son-las-dimensiones-superadas h_01J1VY82KFXYA0XCA1XFVTJ2DZ=ejemplo cardinality-limits-per-dimension=l%C3%ADmites-de-cardinalidad-por-dimensi%C3%B3n h_01J1VY82KF5WP6PJQ1MKYPP7YY=l%C3%ADmites-de-cardinalidad-por-dimensi%C3%B3n h_01J1VY82KF9XQ08EQ2BH89B6QK=exceeded_adset_limit-and-exceeded_ad_limit h_01J1VY82KFM4VAD4FG5CEKTQK6=consejo h_01J1VY82KFWMF6DN3XNFSWBFHH=exceeded_adsetid_limit-and-exceeded_adid_limit h_01J1VY82KFF7AWBCB54KRPJNS4=exceeded_campaign_limit h_01J1VY82KFBPK2PAHSSMCER6TW=consejo-1 h_01J1VY82KF4TFVTGQ31RCE3QK7=exceeded_campaignid_limit h_01J1VY82KFXPX63XKKKTZ9AWN1=exceeded_channels_limit h_01J1VY82KFRDRVNEAG6S72Q1T4=exceeded_events_limit h_01J1VY82KFYXAXTJ613VAN1PXX=consejo-2 h_01J1VY82KF48N1M8DZ89XQBJTD=ejemplo-1 h_01J1VY82KFAFK03F3SDJBA5ZNX=exceeded_keywords_limit h_01J1VY82KFV85460FCZB77EY1A=exceeded_mediasource_limit h_01J1VY82KFQG2ZGF91F80X2AAK=exceeded_siteid_limit h_01J1VY82KFMD2DJWDYXF8528CY=consejo-3 h_01J1VY82KFQRVCAW82ZSNJ96G7=nota how-to-avoid-getting-exceeded-sources=c%C3%B3mo-evitar-que-se-superen-las-fuentes h_01J1VY82KFE9E2DNRNPBRQSW22=c%C3%B3mo-evitar-que-se-superen-las-fuentes the-long-term-solution=la-soluci%C3%B3n-a-largo-plazo h_01J1VY82KFDBASKPRK2GJ16FDZ=la-soluci%C3%B3n-a-largo-plazo h_01J1VY82KFSWQ2Y4WSSASYDFWR=consejo-4 the-short-term-solution=la-soluci%C3%B3n-a-corto-plazo h_01J1VY82KFR7Z8422MYFK71ET8=la-soluci%C3%B3n-a-corto-plazo h_01J1VY82KF83SADWJCESRNSJCJ=consejo-5" />
