---
title: Propiedades de la campaña en los reportes ETL de costo
metadata:
  keywords:
    - cost
    - Advertisers
    - Xpend
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - ROI360
  created_at: '2021-06-02T17:21:22Z'
  edited_at: '2026-08-12T11:47:56Z'
  id: 360020994977
  locale: es
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/es/articles/360020994977
---
> **De un vistazo:** Aprende más sobre las propiedades de las campañas y cómo se muestran en los datos de ETL de costos de AppsFlyer.

<div id="about-campaign-properties" />

## Acerca de las propiedades de campaña

Las propiedades de campaña son un grupo especial de dimensiones que representan varias configuraciones de una campaña publicitaria, incluidos el objetivo de la campaña, el tipo de oferta y el monto de la oferta. Estas son las configuraciones que normalmente ves y editas en el panel de control de tu red de publicidad, pero AppsFlyer extrae las dimensiones de las propiedades de la campaña y hace que los datos estén disponibles en el ETL de costos, al igual que ves otras dimensiones.

Con los datos de las propiedades de la campaña, puedes:

* Ver todos los cambios en la oferta realizados por tu equipo UA.
* Medir y analizar la efectividad de un cambio en la oferta y si tuvo el efecto deseado.

Los datos de las propiedades de la campaña de AppsFlyer están disponibles para Anuncios de Meta y Google. Consulta qué datos extrae AppsFlyer y cómo se normalizan y asignan a cada red de publicidad en las secciones siguientes.

<div id="facebook" />

<Accordion title="Meta Ads">

Consulta qué datos extrae AppsFlyer, y cómo se estandarizan y asignan a Anuncios de Meta, en la siguiente tabla.

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
        Objetivo de la campaña
      </td>
      <td>
        Extraído de: [campaign.objective](https://developers.facebook.com/docs/marketing-api/reference/ad-campaign-group/insights)
      </td>
    </tr>
    <tr>
      <td>
        Modelo de costo
      </td>
      <td>
        Extraído de: <Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/bidding/overview#opt">adset.optimization\_goal</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        Asignación del modelo de costo normalizado de AppsFlyer
      </td>
      <td>
        | Modelo de costo | Modelo de costo normalizado |
        | --- | --- |
        | * {"LINK_CLICKS"}<br />* {"POST_ENGAGEMENT"}<br />* REPLIES<br />* {"LANDING_PAGE_VIEWS"} | CPC |
        | * {"OFFSITE_"} CONVERSIONS<br />* {"DERIVED_EVENTS"}<br />* {"LEAD_GENERATION"} | CPA |
        | APP\_INSTALLS | CPI |
        | value | ROI (Retorno de la Inversión) |
        | * REACH<br />* IMPRESSIONS<br />* SOCIAL\_IMPRESSIONS | CPM |
        | * THRUPLAY<br />* VIDEO\_VIEWS<br />* TWO\_SECOND\_CONTINUOUS\_VIDEO\_VIEWS | CPCV |
      </td>
    </tr>
    <tr>
      <td>
        Estrategia de la oferta
      </td>
      <td>
        Extraído de: <Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/bidding/overview/bid-strategy">adset.bid\_strategy</Anchor>

        Si no hay bid\_strategy en el nivel de adset, entonces: <Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/bidding/overview/bid-strategy">campaign.bid\_strategy</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        Estrategia de oferta normalizada de AppsFlyer
      </td>
      <td>
        | Estrategia de la oferta | Estrategia de oferta normalizada |
        | --- | --- |
        | * {"LOWEST_COST_"} {"WITHOUT_CAP"}<br />* {"COST_CAP"}<br />* {"LOWEST_COST_"} {"WITH_MIN_ROAS"} | Oferta automática |
        | TARGET\_COST | Oferta objetivo |
        | Cualquier otra cosa | Desconocido |
      </td>
    </tr>
    <tr>
      <td>
        Monto de la oferta
      </td>
      <td>
        Monto de la oferta en la divisa del anunciante
      </td>
    </tr>
    <tr>
      <td>
        Monto de la oferta original
      </td>
      <td>
        Extraído de: adset.bid\_amount
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="google" />

<Accordion title="Google">

Consulta qué datos extrae AppsFlyer, y cómo se estandarizan y asignan a Google, en la siguiente tabla.

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
        Objetivo de la campaña
      </td>
      <td>
        Extraído de: <Anchor target="_blank" href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.advertising_channel_sub_type">campaign.advertising\_channel\_sub\_type</Anchor>

        Nota: El relleno de los campos siguientes depende del channel\_sub\_type:

        * AC: APP\_CAMPAIGN o APP\_CAMPAIGN\_FOR\_ENGAGEMENT
        * No AC: Cualquier otro valor para channel\_sub\_type
      </td>
    </tr>
    <tr>
      <td>
        Modelo de costo
      </td>
      <td>
        * Para AC, extraído de: <Anchor target="_blank" href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.app_campaign_setting.bidding_strategy_goal_type">campaign.app\_campaign\_setting.bidding\_strategy\_goal\_type</Anchor>
        * Para no AC, extraído de: <Anchor target="_blank" href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.bidding_strategy_type">campaign.bidding\_strategy\_type</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        Asignación del modelo de costo normalizado de AppsFlyer
      </td>
      <td>
        <table><thead><tr><th colspan="2">Modelo de costo</th><th>Modelo de costo normalizado</th></tr></thead><tbody><tr><td rowspan="4"> <span>AC</span><span><br/></span> </td><td><ul><li>OPTIMIZE_INSTALLS_TARGET_INSTALL_COST</li><li>OPTIMIZE_IN_APP_CONVERSIONS_TARGET_INSTALL_COST</li></ul></td><td><span>CPI</span></td></tr><tr><td><p>OPTIMIZE_IN_APP_CONVERSIONS_TARGET_CONVERSION_COST</p></td><td><span>CPA</span></td></tr><tr><td>OPTIMIZE_RETURN_ON_ADVERTISING_SPEND</td><td><span>ROI (Retorno de la Inversión)</span></td></tr><tr><td><ul><li>Desconocido </li><li>UNSPECIFIED</li></ul></td><td><span>Otros</span></td></tr><tr><td>No AC</td><td><ul><li>REACH</li><li>ENHANCED_CPC</li><li>MANUAL_CPC</li><li>PERCENT_CPC</li><li>TARGET_SPEND</li></ul></td><td><span>CPC</span></td></tr><tr><td> </td><td><ul><li>MANUAL_CPM</li><li>TARGET_CPM</li><li>TARGET_IMPRESSION_SHARE</li></ul></td><td><span>CPM</span></td></tr><tr><td> </td><td>MANUAL_CPV</td><td><span>CPCV</span></td></tr><tr><td> </td><td><ul><li>MAXIMIZE_CONVERSIONS</li><li>TARGET_CPA</li></ul></td><td><span>CPA</span></td></tr><tr><td> </td><td><ul><li>MAXIMIZE_CONVERSION_VALUE</li><li>TARGET_ROAS</li></ul></td><td><span>ROI (Retorno de la Inversión)</span></td></tr><tr><td><span> </span></td><td><ul><li>COMMISSION</li><li>PAGE_ONE_PROMOTED</li><li>TARGET_OUTRANK_SHARE</li><li>Desconocido </li><li>UNSPECIFIED</li></ul></td><td><span>Otros</span></td></tr></tbody></table>
      </td>
    </tr>
    <tr>
      <td>
        Estrategia de la oferta
      </td>
      <td>
        * Para AC, extraído de: <Anchor target="_blank" href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.app_campaign_setting.bidding_strategy_goal_type">campaign.app\_campaign\_setting.bidding\_strategy\_goal\_type</Anchor>
        * Para no AC, extraído de: <Anchor target="_blank" href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.bidding_strategy_type">campaign.bidding\_strategy\_type</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        Estrategia de oferta normalizada de AppsFlyer
      </td>
      <td>
        <table><thead><tr><th colspan="2"><font> <span>Estrategia de la oferta</span> </font></th><th><font> <span>Estrategia de oferta normalizada</span> </font></th></tr></thead><tbody><tr><td rowspan="3"><font> <span>AC</span> </font></td><td><ul><li><font> <span>OPTIMIZE_INSTALLS_TARGET_INSTALL_COST</span> </font></li><li><font> <span>OPTIMIZE_IN_APP_CONVERSIONS_TARGET_CONVERSION_COST</span> </font></li></ul></td><td><font> <span>Oferta máxima</span> </font></td></tr><tr><td><ul><li><font> <span>OPTIMIZE_IN_APP_CONVERSIONS_TARGET_INSTALL_COST</span> </font></li><li><font> <span>OPTIMIZE_RETURN_ON_ADVERTISING_SPEND</span> </font></li></ul></td><td><font> <span>Oferta objetivo</span> </font></td></tr><tr><td><ul><li><font> <span>Desconocido </span> </font></li><li><font> <span>UNSPECIFIED</span> </font></li></ul></td><td><font> <span>Otros</span> </font></td></tr><tr><td rowspan="5"><font> <span>No AC</span> </font></td><td><ul><li><font> <span>ENHANCED_CPC</span> </font></li><li><font> <span>MANUAL_CPC</span> </font></li><li><font> <span>MANUAL_CPM</span> </font></li><li><font> <span>MANUAL_CPV</span> </font></li></ul></td><td><font> <span>Oferta manual</span> </font></td></tr><tr><td><ul><li><font> <span>MAXIMIZE_CONVERSIONS</span> </font></li><li><font> <span>MAXIMIZE_CONVERSION_VALUE</span> </font></li><li><font> <span>PAGE_ONE_PROMOTED</span> </font></li><li><font> <span>TARGET_IMPRESSION_SHARE</span> </font></li><li><font> <span>TARGET_OUTRANK_SHARE</span> </font></li><li><font> <span>TARGET_SPEND</span> </font></li></ul></td><td><font> <span>Oferta automática</span> </font></td></tr><tr><td><ul><li><font> <span>PERCENT_CPC</span> </font></li><li><font> <span>TARGET_CPA</span> </font></li><li><font> <span>TARGET_CPM</span> </font></li><li><font> <span>TARGET_ROAS</span> </font></li></ul></td><td><font> <span>Oferta objetivo</span> </font></td></tr><tr><td><ul><li><font> <span>COMMISSION</span> </font></li><li><font> <span>Desconocido </span> </font></li><li><font> <span>UNSPECIFIED</span> </font></li></ul></td><td><font> <span>Otros</span> </font></td></tr><tr><td><font> <span>Cualquier otra cosa</span> </font></td><td><font> <span>Desconocido</span> </font></td></tr></tbody></table>
      </td>
    </tr>
    <tr>
      <td>
        Monto de la oferta
      </td>
      <td>
        Monto de la oferta en la divisa del anunciante
      </td>
    </tr>
    <tr>
      <td>
        Monto de la oferta original
      </td>
      <td>
        Extraído de:    <Anchor target="_blank" href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.target_cpa.target_cpa_micros">campaign.target\_cpa.target\_cpa\_micros</Anchor>
      </td>
    </tr>
  </tbody>
</Table>

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
        Nota
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Propiedades de la campaña
      </td>
      <td>
        Extraído de: <Anchor target="_blank" href="https://developers.snapchat.com/api/docs/#campaigns">campaign.objective</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        Modelo de coste
      </td>
      <td>
        Extraído de: <Anchor target="_blank" href="https://developers.snapchat.com/api/docs/#squad-optimization-goals">adsquad.optimization\_goal</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        Asignación del modelo de costo normalizado de AppsFlyer
      </td>
      <td>
        | Modelo de coste | Modelo de costo normalizado |
        | --- | --- |
        | * Deslizamientos<br />* Aperturas de historias | CPC |
        | * Usos<br />* Píxel: añadir al carrito<br />* Píxel: compra<br />* Píxel: registro<br />* App: añadir al carrito<br />* App: compra<br />* App: registro | CPA |
        | APP\_INSTALLS | CPI |
        | * IMPRESSIONS | CPM |
        | * VIDEO\_VIEWS<br />* VIDEO\_VIEWS\_15\_SEC | CPCV |
      </td>
    </tr>
    <tr>
      <td>
        Estrategia de la oferta
      </td>
      <td>
        Extraído de: <Anchor target="_blank" href="https://developers.snapchat.com/api/docs/#bid-strategy">adsquad.bid\_strategy</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        Estrategia de oferta normalizada de AppsFlyer
      </td>
      <td>
        | Estrategia de la oferta | Estrategia de oferta normalizada |
        | --- | --- |
        | * ROAS mínimo<br />* Puja automática | Oferta automática |
        | Coste más bajo con puja máxima | Oferta máxima |
        | TARGET\_COST | Oferta objetivo |
      </td>
    </tr>
    <tr>
      <td>
        Monto de la oferta
      </td>
      <td>
        Monto de la oferta en la divisa del anunciante
      </td>
    </tr>
    <tr>
      <td>
        Monto de la oferta original
      </td>
      <td>
        Extraído de: adsquad.bid\_micro
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div data-zendesk-anchors="about-campaign-properties=acerca-de-las-propiedades-de-campa%C3%B1a h_01J1PX98QNCZG9Y9PRZQ4ZEEFK=acerca-de-las-propiedades-de-campa%C3%B1a h_01J1PX98QNX2T408GB2WV0RFZH=facebook h_01J1PX98QP22PPG9V84DD5WEM1=google h_01J1PXNDS4V16NQQQGMBND9PAF=snap" />
