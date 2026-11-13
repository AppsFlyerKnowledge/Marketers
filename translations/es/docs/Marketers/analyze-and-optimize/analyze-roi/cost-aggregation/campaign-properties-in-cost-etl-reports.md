---
title: Propiedades de campaña en informes de costo ETL
metadata:
  keywords:
    - coste
    - Anunciantes
    - Xpend
    - Marcadores
    - ROI360
x-zendesk:
  category: Marcadores
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marcadores
    - ROI360
  created_at: '2021-06-02T17:21:22Z'
  edited_at: '2025-04-05T11:08:21Z'
  id: 360020994977
  locale: es-es
  section: Agrupación de costos
  section_id: 6551029483281
  url: >-
    https://support.appsflyer.com/hc/es/articles/360020994977-Campaign-properties-in-cost-ETL
---
> **De un vistazo:** Aprende sobre las propiedades de la campaña y cómo se muestran en los datos ETL de AppsFlyer.

<div id="about-campaign-properties" />

## Acerca de propiedades de la campaña

Las propiedades de la campaña son un grupo especial de dimensiones que representan varias configuraciones de una campaña publicitaria, incluyendo el objetivo de la campaña, el tipo de oferta y la cantidad de la oferta. Estos son los ajustes que normalmente ve y edita en su panel de control de red de anuncios, pero AppsFlyer extrae las dimensiones de las propiedades de la campaña y hace que los datos estén disponibles en ETL de Costo, al igual que usted ve otras dimensiones.

Con los datos de propiedades de la campaña, puede:

- Vea todos los cambios realizados por su equipo de UA.
- Medir y analizar la efectividad de un cambio de oferta y si tuvo el efecto previsto.

Los datos de las propiedades de las campañas de AppsFlyer están disponibles para Meta anuncios y Google. Vea qué datos extrae AppsFlyer, y cómo se normaliza y asigna a cada red de anuncios, en las secciones que siguen.

<div id="facebook" />

<Accordion title="Meta ads">

Vea qué datos extrae AppsFlyer, y cómo está estandarizado y mapeado a Meta ads, en la tabla que sigue.

<Table>
  <thead>
    <tr>
      <th>
        Dimensión
      </th>
      <th>
        Descripción
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        Objetivo de campaña
      </td>
      <td>
        desde: [campaign.objective](https://developers.facebook.com/docs/marketing-api/reference/ad-campaign-group/insights)
      </td>
    </tr>
    <tr>
      <td>
        modelo de coste
      </td>
      <td>
        desde: <Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/bidding/overview#opt">adset.optimization\_objetivo</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        modelo de costo normalizado de AppsFlyer que mapea
      </td>
      <td>
        | Modelo de costo | Modelo de costo normalizado |
        | --- | --- |
| <ul><li>ClicKS</li><li>POST</li><li>REPARACIONES</li><li>Parámetros</li></ul> | CPC |
| <ul><li>CONVERSIONES</li><li>Eventos_DESCRIPTION</li><li>GENERACIÓN LIBRE</li></ul> | CPA |
        | APP\_INSTALLS | CPI |
        | VALUE | ROI |
| <ul><li>REACH</li><li>IMPRESIONES</li><li>IMPRESIONES</li></ul> | CPM |
| <ul><li>TRUJERO</li><li>Vistas</li><li>VIDEO_TITLE</li></ul> | CPCV |
      </td>
    </tr>
    <tr>
      <td>
        Estrategia de oferta
      </td>
      <td>
        desde: <Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/bidding/overview/bid-strategy">adset.bid\_estrategia</Anchor><br /><br />Si no hay bid\_strategy en el nivel de adset, entonces: <Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/bidding/overview/bid-strategy">campaign.bid\_strategy</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        Estrategia normalizada de oferta de AppsFlyer
      </td>
      <td>
        | Estrategia de pujas | Estrategia de puja normalizada |
        | --- | --- |
| <ul><li>{"LOWEST_COST_"} WITHOUT_CAP</li><li>Políticas</li><li>{"LOWEST_COST_"} WITH_MIN_ROAS</li></ul> | Auto puja |
        | TARGET\_COST | Puja objetivo |
        | Cualquier otra cosa | Desconocido |
      </td>
    </tr>
    <tr>
      <td>
        cantidad de oferta
      </td>
      <td>
        Cantidad de la oferta en la moneda del anunciante
      </td>
    </tr>
    <tr>
      <td>
        Cantidad original de oferta
      </td>
      <td>
        desde: adset.bid\_amount
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="google" />

<Accordion title="Google">

Vea qué datos extrae AppsFlyer, y cómo está estandarizado y mapeado a Google, en la tabla que sigue.

<table><thead><tr><th><font> <span>Dimensión</span> </font></th><th><span> <font>Descripción</font> </span></th></tr></thead><tbody><tr><td><span> <font> <span>Objetivo de campaña</span> </font> </span></td><td><p><font> <span>Desde: <a href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.advertising_channel_sub_type" target="_blank">campaign.advertising_channel_sub_type</a></span> </font></p><p><font> <span>Nota: La población de los siguientes campos depende del channel_sub_type:</span> </font></p><ul><li><font> <span>AC: APP_CAMPAIGN o APP_CAMPAIGN_FOR_ENGAGEMENT</span> </font></li><li><font> <span>No AC: Todos los demás valores para channel_sub_type</span> </font></li></ul></td></tr><tr><td><span> <font>modelo de coste</font> </span></td><td><ul><li><span>para AC, extraído de: <a href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.app_campaign_setting.bidding_strategy_goal_type" target="_blank">campaign.app_campaign_setting.bidding_strategy_goal_type</a></span></li><li><span>Para no AC, extraído de: <a href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.bidding_strategy_type" target="_blank">campaign.bidding_strategy_type</a></span></li></ul></td></tr><tr><td><span> <span>Asignación del modelo de costo normalizado de AppsFlyer</span> </span></td><td><table><thead><tr><th colspan="2">Modelo de costo</th><th>Modelo de coste normalizado</th></tr></thead><tbody><tr><td rowspan="4"><span>AC</span><span><br/></span></td><td><ul><li>OPTIMIZE_INSTALLS_BTN</li><li>OPTIMIZE_INSTAL_TITLE</li></ul></td><td><span>CPI</span></td></tr><tr><td><p>OPTIMIZE_IN_TITLE</p></td><td><span>CPA</span></td></tr><tr><td>OPTIMIZE_RETURN_DESCRIPTION</td><td><span>ROI</span></td></tr><tr><td><ul><li>Desconocido</li><li>NO ESPECIFICADO</li></ul></td><td><span>Otra</span></td></tr><tr><td>Non-AC</td><td><ul><li>REACH</li><li>CPC</li><li>CPC</li><li>CPC</li><li>PEND_BTN</li></ul></td><td><span>CPC</span></td></tr><tr><td> </td><td><ul><li>CPM</li><li>TARGET_CPM</li><li>Descomprimir</li></ul></td><td><span>CPM</span></td></tr><tr><td> </td><td>Pirámide</td><td><span>CPCV</span></td></tr><tr><td> </td><td><ul><li>Coordenadas MAXIMIZE</li><li>TARGET_CPA</li></ul></td><td><span>CPA</span></td></tr><tr><td> </td><td><ul><li>MAXIMIZE_CONVERSION</li><li>TARGET_ROAS</li></ul></td><td><span>ROI</span></td></tr><tr><td><span></span></td><td><ul><li>COMISIÓN</li><li>Pegar un</li><li>TARGET_OUTRANK_SHARE</li><li>Desconocido</li><li>NO ESPECIFICADO</li></ul></td><td><span>Otra</span></td></tr></tbody></table></td></tr><tr><td><span> <font>Oferta estrategia</font> </span></td><td><ul><li><span>para AC, extraído de: <a href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.app_campaign_setting.bidding_strategy_goal_type" target="_blank">campaign.app_campaign_setting.bidding_strategy_goal_type</a></span></li><li><span>Para no AC, extraído de: <a href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.bidding_strategy_type" target="_blank">campaign.bidding_strategy_type</a></span></li></ul></td></tr><tr><td><font> <span>Aplicación de estrategia normalizada de oferta</span> </font></td><td><table><thead><tr><th colspan="2"><font> <span>Oferta estrategia</span> </font></th><th><font> <span>Estrategia de oferta normalizada</span> </font></th></tr></thead><tbody><tr><td rowspan="3"><font> <span>AC</span> </font></td><td><ul><li><font> <span>OPTIMIZE_INSTALLS_TARGET_INSTALL_COST</span> </font></li><li><font> <span>OPTIMIZE_IN_APP_CONVERSIONS_TARGET_CONVERSION_COST</span> </font></li></ul></td><td><font> <span>Oferta máxima</span> </font></td></tr><tr><td><ul><li><font> <span>OPTIMIZE_IN_APP_CONVERSIONS_TARGET_INSTALL_COST</span> </font></li><li><font> <span>OPTIMIZE_RETURN_ON_ADVERTISING_SPEND</span> </font></li></ul></td><td><font> <span>Target bid</span> </font></td></tr><tr><td><ul><li><font> <span>DESCONOCIDO</span> </font></li><li><font> <span>NO ESPECIFICADO</span> </font></li></ul></td><td><font> <span>Otros</span> </font></td></tr><tr><td rowspan="5"><font> <span>Non-AC</span> </font></td><td><ul><li><font> <span>ENHANCED_CPC</span> </font></li><li><font> <span>MANUAL_CPC</span> </font></li><li><font> <span>MANUAL_CPM</span> </font></li><li><font> <span>MANUAL_CPV</span> </font></li></ul></td><td><font> <span>Oferta manual</span> </font></td></tr><tr><td><ul><li><font> <span>MAXIMIZE_CONVERSIONES</span> </font></li><li><font> <span>MAXIMIZE_CONVERSION_VALUE</span> </font></li><li><font> <span>PAGE_ONE_PROMOTED</span> </font></li><li><font> <span>TARGET_IMPRESSION_SHARE</span> </font></li><li><font> <span>TARGET_OUTRANK_SHARE</span> </font></li><li><font> <span>TARGET_SPEND</span> </font></li></ul></td><td><font> <span>Auto bid</span> </font></td></tr><tr><td><ul><li><font> <span>PERCENT_CPC</span> </font></li><li><font> <span>TARGET_CPA</span> </font></li><li><font> <span>TARGET_CPM</span> </font></li><li><font> <span>TARGET_ROAS</span> </font></li></ul></td><td><font> <span>Target bid</span> </font></td></tr><tr><td><ul><li><font> <span>COMISIÓN</span> </font></li><li><font> <span>DESCONOCIDO</span> </font></li><li><font> <span>NO ESPECIFICADO</span> </font></li></ul></td><td><font> <span>Otros</span> </font></td></tr><tr><td><font> <span>Cualquier otra cosa</span> </font></td><td><font> <span>Desconocido</span> </font></td></tr></tbody></table></td></tr><tr><td><span> <font>Cantidad de oferta</font> </span></td><td><span> <font>Cantidad de puja en moneda del anunciante</font> </span></td></tr><tr><td><span> <font>Oferta original</font> </span></td><td><span> <font>Desde: </font> </span> <a href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.target_cpa.target_cpa_micros" target="_blank">campaign.target_cpa.target_cpa_micros</a></td></tr></tbody></table>

</Accordion>

<div id="snap" />

<Accordion title="Snap">

<Table>
  <thead>
    <tr>
      <th>
        Dimensión
      </th>
      <th>
        Descripción
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        Objetivo de campaña
      </td>
      <td>
        desde: <Anchor target="_blank" href="https://developers.snapchat.com/api/docs/#campaigns">campaign.objective</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        modelo de coste
      </td>
      <td>
        desde: <Anchor target="_blank" href="https://developers.snapchat.com/api/docs/#squad-optimization-goals">optimización.optimización\_objetivo</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        modelo de costo normalizado de AppsFlyer que mapea
      </td>
      <td>
        | Modelo de costo | Modelo de costo normalizado |
        | --- | --- |
| <ul><li>SWIPES</li><li>OPENS</li></ul> | CPC |
| <ul><li>USOS</li><li>Añadir a la vista</li><li>PURCHASE</li><li>SIGNUP_PLAYLIST</li><li>Añadir a la vista</li><li>Parcela</li><li>SIGNUP</li></ul> | CPA |
        | APP\_INSTALLS | CPI |
| <ul><li>IMPRESIONES</li></ul> | CPM |
| <ul><li>Vistas</li><li>Vistas 15</li></ul> | CPCV |
      </td>
    </tr>
    <tr>
      <td>
        Estrategia de oferta
      </td>
      <td>
        desde: <Anchor target="_blank" href="https://developers.snapchat.com/api/docs/#bid-strategy">adsquad.bid\_estrategia</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        Estrategia normalizada de oferta de AppsFlyer
      </td>
      <td>
        | Estrategia de pujas | Estrategia de puja normalizada |
        | --- | --- |
| <ul><li>MIN_ROAS</li><li>AUTO_BID</li></ul> | Auto bid |
        | {"LOWEST_COST_"} {"WITH_MAX_BID"} | Max bid |
        | TARGET\_COST | Target bid |
      </td>
    </tr>
    <tr>
      <td>
        cantidad de oferta
      </td>
      <td>
        Cantidad de la oferta en la moneda del anunciante
      </td>
    </tr>
    <tr>
      <td>
        Cantidad original de oferta
      </td>
      <td>
        desde: adsquad.bid\_micro
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div data-zendesk-anchors="h_01J1PX98QNCZG9Y9PRZQ4ZEEFK=about-campaign-properties h_01J1PX98QNX2T408GB2WV0RFZH=facebook h_01J1PX98QP22PPG9V84DD5WEM1=google h_01J1PXNDS4V16NQQQGMBND9PAF=snap" />
