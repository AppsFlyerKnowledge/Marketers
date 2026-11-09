---
title: Configuración de las ventanas de lookback
metadata:
  keywords:
    - Advertisers
    - look back
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2016-03-07T09:27:55Z'
  edited_at: '2026-08-12T11:57:16Z'
  id: 208338403
  locale: es
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/es/articles/208338403
---
> **En resumen:** Personaliza las ventanas de lookback click-through y view-through, en función de tus acuerdos con las fuentes de medios.

<div id="lookback-windows" />

## Ventanas de lookback

La ventana de lookback de atribución configurable te permite personalizar el período de atribución en función de tu acuerdo con las fuentes de medios.

Al establecer las ventanas de lookback de atribución por fuente de medios, AppsFlyer atribuye de acuerdo con los términos acordados.

**Tipos de ventana de lookback**:

* **Ventana de lookback por clics**: Período máximo de tiempo después de hacer clic en un anuncio, en el que se puede atribuir una instalación al anuncio. Las instalaciones que se realizan después de la ventana de lookback se consideran orgánicas.
* **Ventana de lookback por engaged clicks:** El período máximo de tiempo después de un engaged click dentro del cual se puede atribuir una instalación al engaged click.  Las instalaciones que se realizan después de la ventana de lookback se consideran orgánicas.
* **Ventana de lookback por engaged clicks:** El período máximo de tiempo después de un engaged click dentro del cual se puede atribuir una instalación al engaged click.  Las instalaciones que se realizan después de la ventana de lookback se consideran orgánicas.
* **Ventana de lookback por view-through**: Período máximo de tiempo después de hacer clic en un anuncio, en el que se puede atribuir una instalación al anuncio. Las instalaciones que se realizan después de la ventana de lookback se consideran orgánicas.

<div id="configurable-lookback-windows-per-attribution-type" />

#### Ventanas de lookback configurables por tipo de atribución

<table><thead><tr><th rowspan="2"><p><strong>Tipo de atribución</strong></p></th><th rowspan="2"><p><strong>Método de atribución</strong></p></th><th colspan="2"><strong>Ventana de lookback</strong> </th></tr><tr><th><strong>Rango</strong></th><th><strong>Predeterminado</strong></th></tr></thead><tbody><tr><td rowspan="3"><p>Por clics</p><p>(Todas las fuentes de medios)</p></td><td>Referencia, matching ID</td><td>1-30 Días O<br/>1-23 horas</td><td>7 días</td></tr><tr><td>Modelado probabilístico (móvil)</td><td><a href="./appsflyer-attribution-model#probabilistic-modeling" target="_blank">Adaptativo</a></td><td>Hasta 24 horas</td></tr><tr><td>Modelado probabilístico (CTV, PC y Consola - enlaces de plataforma única)</td><td>Hasta 7 días. (Establecer en el parámetro de enlace <code>af_lookback_window</code>.)</td><td>7 días</td></tr><tr><td rowspan="2"><p>Engaged click-through</p><p>(<a href="./about-enriched-engagement-types#qué-redes-pueden-reportar-sobre-view-engaged-y-engaged-clicks" target="_blank">Fuentes de medios</a> no SRN seleccionadas\*)</p></td><td>Emparejamiento de ID</td><td>1-7 días o 1-23 horas</td><td>2 días</td></tr><tr><td>Modelado probabilístico (móvil)</td><td><a href="./appsflyer-attribution-model#probabilistic-modeling" target="_blank">Adaptativo</a></td><td>Hasta 24 horas</td></tr><tr><td rowspan="2"><p>Engaged view-through</p><p>(<a href="./about-enriched-engagement-types#qué-redes-pueden-reportar-sobre-view-engaged-y-engaged-clicks" target="_blank">Fuentes de medios</a> no SRN seleccionadas\*)</p></td><td>Emparejamiento de ID</td><td>1-7 días o 1-23 horas</td><td>2 días</td></tr><tr><td>Modelado probabilístico (móvil)</td><td><a href="./appsflyer-attribution-model#probabilistic-modeling" target="_blank">Adaptativo</a></td><td>Hasta 24 horas</td></tr><tr><td rowspan="4"><p>Impresiones</p><p>(<a href="./measure-view-through-engagements#view-vta-partner-list" target="_blank">Fuentes de medios</a> seleccionadas)</p></td><td>Emparejamiento de ID</td><td><p>1-24 horas</p><p>[Hasta el 15 de diciembre de 2021, el límite superior era de 7 días]</p></td><td>24 horas</td></tr><tr><td>Modelado probabilístico (móvil)</td><td><a href="./appsflyer-attribution-model#probabilistic-modeling" target="_blank">Adaptativo</a></td><td>Hasta 24 horas</td></tr><tr><td>Modelado probabilístico (CTV, PC y Consola - enlaces de plataforma única)</td><td>Hasta 7 días. (Establecer en el parámetro de enlace <code>af_lookback_window</code>.)</td><td>24 horas</td></tr><tr><td>Modelado probabilístico (CTV, PC y Consola - <a href="./set-up-cross-platform-links-for-multi-device-campaigns#características-y-limitaciones" target="_blank">enlaces de atribución OneLink multiplataforma</a>)</td><td>Hasta 72 horas. (Establecer en el parámetro de enlace <code>af_xplatform_vt_lookback</code>.)</td><td>24 horas</td></tr></tbody></table>

<strong>Las ventanas de lookback para `engaged_click` y `engaged_view` solo se pueden establecer para redes que no son SRNs. Para los SRN, `engaged_click` y `engaged_view` comparten la misma ventana de lookback que los clics y, por lo tanto, se establecen mediante </strong>Install Click-Through Attribution Lookback.

<div id="probabilistic-modeling-lookback-window" />

### Ventana de lookback de modelado probabilístico

La ventana retrospectiva de modelado probabilístico, utilizada para mantener la precisión de la atribución, tiene las siguientes características:

* Se aplica tanto a clics como a impresiones.
* Tiene una duración adaptativa de hasta 24 horas.
* Ignora la configuración de la duración de la ventana enviada en el enlace de atribución.
* Tiene una duración más corta que las ventanas utilizadas por los modelos deterministas.

Para saber más, lee sobre el <Anchor target="_blank" href="/marketers/es/docs/appsflyer-attribution-model#probabilistic-modeling">método de modelado probabilístico de AppsFlyer</Anchor>.

<div id="lookback-window-setup" />

## Configuración de la ventana de lookback

A continuación, enumeramos el proceso de configuración de la ventana de lookback para SRNs y enlaces de atribución

<Tabs>
<Tab title="Ventana de lookback de SRNs">

<div id="attribution-lookback-window-for-srns" />

### Ventana de lookback de atribución para SRNs

<div id="important" />

> 🚧 **¡Importante!**
>
> Cada SRN tiene su propio lookback predeterminado. Recomendamos hacer coincidir el valor de la ventana de lookback en AppsFlyer con el valor de la SRN para minimizar las discrepancias. Cambiarlo podría resultar en discrepancias. Para saber más, mira un [ejemplo de discrepancia de SRN](#escenarios-y-ejemplos).

1. En AppsFlyer, desde el menú lateral, selecciona **Colaborar** > **Partner Marketplace**.
2. Busca y selecciona la SRN: consulta la <Anchor target="_blank" href="/marketers/es/docs/self-reporting-networks-srns#srns-integradas-con-appsflyer">lista de SRNs compatibles</Anchor>.
3. De forma predeterminada, la atribución view-through está habilitada.
4. En la pestaña **Integración**, desplázate hacia abajo hasta la configuración de **Atribución click-through** y **Atribución view-through**.
5. Utiliza los controles deslizantes para establecer la ventana de atribución

A continuación puedes ver cada ventana de lookback de SRN:

| nombres de SRN reservados | Ventana de lookback de click-through predeterminada (días) | Ventana de lookback de view-through predeterminada (horas) |
| --- | --- | --- |
| Google | 30 | 24 |
| Meta Ads | 7 | 24 |
| Snapchat | 28 | 24 |
| Anuncios X | 14 | 24 |
| Anuncios en la búsqueda de Apple | 30 | 24 |
| Oath (YahooGemini) | 7 | 24 |

</Tab>

<Tab title="Ventana de lookback de no-SRNs">

<div id="attribution-lookback-window-with-attribution-links" />

<div id="h_01JKWVQB6TTA24VAZ9WVJMGY4X" />

<div id="non-srn-attribution-lookback-window-for-click-through-and-view-through" />

### Ventana de lookback de atribución no-SRN para click-through y view-through

1. En AppsFlyer, desde el menú lateral, selecciona **Colaborar** > **Integraciones Activas**.
2. Busca y selecciona un partner.
3. De forma predeterminada, la atribución view-through está habilitada.
4. Haz clic en la pestaña **Enlace de atribución**.
5. Elige si quieres establecer el tiempo en días u horas.
6. Utiliza los deslizadores debajo de **Atribución click-through** (parámetro `af_click_lookback`) y **atribución view-through** (parámetro `af_viewthrough_lookback`) para establecer la ventana de atribución.  
   El tiempo seleccionado se refleja automáticamente en el enlace de atribución.
7. Selecciona los parámetros que corresponden a la campaña, es decir, nombre de la campaña, conjunto de anuncios, etc.
8. Copia y guarda el enlace: este es el enlace que proporcionas a la ad network.

<div id="non-srn-attribution-lookback-window-for-engaged-click-through-and-engaged-view-through" />

### Ventana de lookback de atribución no-SRN para click-through y view-through

1. En AppsFlyer, desde el menú lateral, selecciona **Colaborar** > **Integraciones Activas**.
2. Busca y selecciona un partner.
3. En la pestaña Integración, desplázate hacia abajo hasta **Instalar ventana de lookback de click-through** o hasta **Instalar ventana de lookback de view-through**.
4. Establece la ventana de lookback utilizando los deslizadores.

<div id="tip" />

> 👍 **Consejo**
>
> * ¿Quieres algunos consejos y trucos para la configuración de la ventana lookback? Consulta este <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7768/play/18612/attribution-102-tips-and-tricks">breve curso informativo</Anchor> en el portal de aprendizaje de AppsFlyer.
> * [Haz clic aquí](/docs/set-up-lookback-windows#lookback-in-hours-for-flash-campaigns) para saber cuándo debes usar las horas para las ventanas de atribución.

<div id="lookback-window-in-onelink" />

### Ventana de lookback en OneLink™

También puedes configurar la ventana de lookback en OneLink.

1. <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template">Configura un OneLink</Anchor>
2. <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#crear-un-enlace-de-onelink">Crea un enlace de atribución personalizado.</Anchor>
3. En **Avanzado**, activa **Personalizar ventana de lookback** y configura la ventana de lookback.

</Tab>
</Tabs>

<div id="distribution-of-first-app-launches" />

## Distribución de las primeras aperturas de la aplicación

A continuación se muestra un gráfico que muestra la distribución de las primeras aperturas de la aplicación desde el día del engagement.

<Image align="center" alt="" src="https://files.readme.io/8fdc8b23ba9a1b78bdea7bacad99d6ed5e59d57de32f395cb2fd9e5451483962-360001666918.png" />

El gráfico puede darte una mejor idea de la cantidad de usuarios que instalan la aplicación en función de la ventana de lookback.

La mayoría de los usuarios, un poco más del 97%, que inician la aplicación, lo hacen dentro de los 7 días posteriores al engagement con el anuncio. El 2% restante lo hace entre el día 7 y el final de la ventana de lookback (día 30).

De hecho, casi el 62% de los usuarios que inician la aplicación, lo hacen dentro de los 15 minutos después de envolverse con el anuncio. El 72% de los usuarios lo hace dentro de la primera hora.

<div id="scenarios-and-examples" />

## Escenarios y ejemplos

A continuación se muestra una lista de posibles escenarios y ejemplos de uso de la ventana de lookback.

<div id="srn-discrepancy-srn-lookback-longer-than-appsflyer" />

<Accordion title="Discrepancia de SRN: El lookback de la SRN es menor que el de AppsFlyer">

Estableces una campaña en Twitter y configuras la ventana de lookback por click-through a 7 días. Twitter, por otro lado, tiene una ventana de lookback predeterminada de 14 días.

<Image align="center" alt="srn-discrepancy-srn-lookback-larger-than-appsflyer.png" src="https://files.readme.io/a0a60df2c1b142c9b2871c2083168ef5d88922001f1e5ab6a95c7ffbdcc178a5-360001586637.png" />

</Accordion>

<div id="srn-lookback-smaller-than-appsflyer" />

<Accordion title="El lookback de la SRN es menor que el de AppsFlyer">

Estableces una campaña en Twitter y configuras la ventana de lookback por click-through a 28 días. Twitter, por otro lado, tiene una ventana de lookback predeterminada de 14 días.

<Image align="center" alt="srn-lookback-smaller-than-appsflyer.png" src="https://files.readme.io/9111035d903bfb35be2ab4bff27c16e527b401b12225b71316a7e36ed68ffb0c-360001586697.png" />

</Accordion>

<div id="attribution-link-without-a-lookback-window-parameter" />

<Accordion title="Enlace de atribución sin un parámetro de ventana de lookback">

Es posible tener un enlace de atribución que no tenga un parámetro de ventana de lookback. En tales casos, AppsFlyer toma por defecto una ventana de lookback de 7 días para los clics, y una ventana de lookback de 1 día para las impresiones.

</Accordion>

<div id="lookback-in-hours-for-flash-campaigns" />

<Accordion title="Lookback en horas para campañas flash">

Las campañas flash son campañas cuya intención es incentivar a los usuarios a instalar la aplicación lo más rápido posible y dentro de una breve ventana de promoción.

Una aplicación de eCommerce llamada SuperShopping ejecuta una campaña flash. En esta campaña, un usuario que instale la aplicación en el plazo de una hora obtiene ofertas especiales.

Johnny, el marketer principal de SuperShopping, crea un enlace de atribución y establece la ventana de lookback en 1 hora. De esta manera Johnny sabe cuántos usuarios responden a la campaña.

Además, el desarrollador de la aplicación puede identificar a los usuarios que provienen de esta campaña flash y entregar las promociones que la campaña anuncia.

</Accordion>

<div id="tip-1" />

> 👍 **Consejo**
>
> ¿Quieres algunos consejos y trucos sobre ventanas de lookback y atribución? Consulta este breve y educativo <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7768/play/18612/attribution-102-tips-and-tricks">curso en el Portal de Aprendizaje de AppsFlyer</Anchor>.

<div data-zendesk-anchors="lookback-windows=ventanas-de-lookback h_01HGFQVP7QZACJ3EGSWEP4HPFV=ventanas-de-lookback configurable-lookback-windows-per-attribution-type=ventanas-de-lookback-configurables-por-tipo-de-atribuci%C3%B3n h_01HGFQVP7QM0J507CFQ753YS5X=ventanas-de-lookback-configurables-por-tipo-de-atribuci%C3%B3n probabilistic-modeling-lookback-window=ventana-de-lookback-de-modelado-probabil%C3%ADstico h_01JKWV7S7J5B4YA84VGEB478TT=ventana-de-lookback-de-modelado-probabil%C3%ADstico lookback-window-setup=configuraci%C3%B3n-de-la-ventana-de-lookback h_01HGFQVP7QCCN7CHRCAFSNJVHA=configuraci%C3%B3n-de-la-ventana-de-lookback attribution-lookback-window-for-srns=ventana-de-lookback-de-atribuci%C3%B3n-para-srns h_01HGFQVP7QP61C2K0P7C7YM56Z=ventana-de-lookback-de-atribuci%C3%B3n-para-srns h_01HGFQVP7QXTQKGVQJEZ0NEW0M=importante h_01HGFQVP7QDBFP85A9DJFZE38S=attribution-lookback-window-with-attribution-links h_01HGFQVP7Q69H5621GXMYZ441N=consejo-1 lookback-window-in-onelink%E2%84%A2=lookback-window-in-onelink h_01HGFQVP7QSJEE8D7TCWZMSXGK=lookback-window-in-onelink distribution-of-first-app-launches=distribuci%C3%B3n-de-las-primeras-aperturas-de-la-aplicaci%C3%B3n h_01HGFQVP7Q96827N7Q9Q0363SR=distribuci%C3%B3n-de-las-primeras-aperturas-de-la-aplicaci%C3%B3n scenarios-and-examples=escenarios-y-ejemplos h_01HGFQVP7Q02NS8MXF7WKYQ8V1=escenarios-y-ejemplos h_01HGFQVP7Q1CYRAHAKY3WK8BK0=srn-discrepancy-srn-lookback-longer-than-appsflyer h_01HGFQVP7QAWDP40H89YBN66GV=srn-lookback-smaller-than-appsflyer h_01HGFQVP7QYE3V2DKW7T4171MX=attribution-link-without-a-lookback-window-parameter h_01HGFQVP7Q7CXSK5G8A0937H5Z=lookback-in-hours-for-flash-campaigns h_01HGFQVP7QM3R973QS99661VPG=consejo-1" />
