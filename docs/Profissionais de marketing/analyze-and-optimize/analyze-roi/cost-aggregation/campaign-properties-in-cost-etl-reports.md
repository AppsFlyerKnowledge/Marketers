---
title: Propriedades da campanha em relatórios de ETL de custos
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
  edited_at: '2026-08-18T00:01:01Z'
  id: 360020994977
  locale: pt
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/pt/articles/360020994977
---
> **Visão geral:** saiba mais sobre as propriedades da campanha e como elas são exibidas nos dados de Cost ETL da AppsFlyer.

<div id="about-campaign-properties" />

## Sobre as propriedades da campanha

As propriedades da campanha são um grupo especial de dimensões que representam várias configurações de uma campanha de anúncios, incluindo o objetivo da campanha, tipo de bid e valor do bid. Essas são configurações que você normalmente visualiza e edita no dashboard da ad network, mas a AppsFlyer extrai as dimensões das propriedades da campanha e disponibiliza os dados no Cost ETL, assim como você visualiza outras dimensões.

Com os dados das propriedades da campanha, você pode:

* Ver todas as alterações de bids feitas pela sua equipe de UA.
* Mensurar e analisar a eficácia de uma alteração de bid e se ela teve o efeito pretendido.

Os dados de propriedades da campanha da AppsFlyer estão disponíveis para Meta ads e Google. Veja quais dados a AppsFlyer extrai e como eles são padronizados e mapeados para cada ad network, nas seções a seguir.

<div id="facebook" />

<Accordion title="Meta Ads">

Veja quais dados a AppsFlyer extrai e como eles são padronizados e mapeados para o Meta ads, na tabela a seguir.

<Table>
  <thead>
    <tr>
      <th>
        Dimensão
      </th>
      <th>
        Descrição
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Objetivo da campanha
      </td>
      <td>
        Extraído de: [campaign.objective](https://developers.facebook.com/docs/marketing-api/reference/ad-campaign-group/insights)
      </td>
    </tr>
    <tr>
      <td>
        Modelo de custo
      </td>
      <td>
        Extraído de: <Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/bidding/overview#opt">adset.optimization\_goal</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        Mapeamento do modelo de custo padronizado da Appsflyer
      </td>
      <td>
        | Modelo de custo | Modelo de custo normalizado |
        | --- | --- |
        | * {"LINK_CLICKS"}<br />* {"POST_ENGAGEMENT"}<br />* REPLIES<br />* {"LANDING_PAGE_VIEWS"} | CPC |
        | * {"OFFSITE_"} CONVERSIONS<br />* {"DERIVED_EVENTS"}<br />* {"LEAD_GENERATION"} | CPA |
        | APP\_INSTALLS | CPI |
        | valor | ROI |
        | * REACH<br />* IMPRESSIONS<br />* SOCIAL\_IMPRESSIONS | CPM (custo por mil impressões) |
        | * THRUPLAY<br />* VIDEO\_VIEWS<br />* TWO\_SECOND\_CONTINUOUS\_VIDEO\_VIEWS | CPCV |
      </td>
    </tr>
    <tr>
      <td>
        Estratégia de lances
      </td>
      <td>
        Extraído de: <Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/bidding/overview/bid-strategy">adset.bid\_strategy</Anchor>

        Se não houver bid\_strategy no nível do conjunto de anúncios, então: <Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/bidding/overview/bid-strategy">campaign.bid\_strategy</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        Estratégia de bid padronizado da AppsFlyer
      </td>
      <td>
        | Estratégia de lances | Estratégia de lances normalizada |
        | --- | --- |
        | * {"LOWEST_COST_"} {"WITHOUT_CAP"}<br />* {"COST_CAP"}<br />* {"LOWEST_COST_"} {"WITH_MIN_ROAS"} | Bid automático |
        | TARGET\_COST | Bid escolhido |
        | Outros | Desconhecido |
      </td>
    </tr>
    <tr>
      <td>
        Valor de bidding
      </td>
      <td>
        Valor do bid na moeda do anunciante
      </td>
    </tr>
    <tr>
      <td>
        Valor do lance original
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

Veja quais dados a AppsFlyer extrai e como eles são padronizados e mapeados para o Google, na tabela a seguir.

<Table>
  <thead>
    <tr>
      <th>
        Dimensão
      </th>
      <th>
        Descrição
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Objetivo da campanha
      </td>
      <td>
        Extraído de: <Anchor target="_blank" href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.advertising_channel_sub_type">campaign.advertising\_channel\_sub\_type</Anchor>

        Observação: o preenchimento dos campos a seguir depende do channel\_sub\_type:

        * AC: APP\_CAMPAIGN ou APP\_CAMPAIGN\_FOR\_ENGAGEMENT
        * Não AC: todos os outros valores para channel\_sub\_type
      </td>
    </tr>
    <tr>
      <td>
        Modelo de custo
      </td>
      <td>
        * Para AC, extraído de: <Anchor target="_blank" href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.app_campaign_setting.bidding_strategy_goal_type">campaign.app\_campaign\_setting.bidding\_strategy\_goal\_type</Anchor>
        * Para não-AC, extraído de: <Anchor target="_blank" href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.bidding_strategy_type">campaign.bidding\_strategy\_type</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        Mapeamento do modelo de custo padronizado da Appsflyer
      </td>
      <td>
        <table><thead><tr><th colspan="2">Modelo de custo</th><th>Modelo de custo normalizado</th></tr></thead><tbody><tr><td rowspan="4"> <span>AC</span><span></span><br/> </td><td><ul><li>OPTIMIZE_INSTALLS_TARGET_INSTALL_COST</li><li>OPTIMIZE_IN_APP_CONVERSIONS_TARGET_INSTALL_COST</li></ul></td><td><span>CPI</span></td></tr><tr><td><p>OPTIMIZE_IN_APP_CONVERSIONS_TARGET_CONVERSION_COST</p></td><td><span>CPA</span></td></tr><tr><td>OPTIMIZE_RETURN_ON_ADVERTISING_SPEND</td><td><span>ROI</span></td></tr><tr><td><ul><li>Desconhecido</li><li>UNSPECIFIED</li></ul></td><td><span>Outros</span></td></tr><tr><td>Não AC</td><td><ul><li>REACH</li><li>ENHANCED_CPC</li><li>MANUAL_CPC</li><li>PERCENT_CPC</li><li>TARGET_SPEND</li></ul></td><td><span>CPC</span></td></tr><tr><td> </td><td><ul><li>MANUAL_CPM</li><li>TARGET_CPM</li><li>TARGET_IMPRESSION_SHARE</li></ul></td><td><span>CPM (custo por mil impressões)</span></td></tr><tr><td> </td><td>MANUAL_CPV</td><td><span>CPCV</span></td></tr><tr><td> </td><td><ul><li>MAXIMIZE_CONVERSIONS</li><li>TARGET_CPA</li></ul></td><td><span>CPA</span></td></tr><tr><td> </td><td><ul><li>MAXIMIZE_CONVERSION_VALUE</li><li>TARGET_ROAS</li></ul></td><td><span>ROI</span></td></tr><tr><td><span> </span></td><td><ul><li>COMMISSION</li><li>PAGE_ONE_PROMOTED</li><li>TARGET_OUTRANK_SHARE</li><li>Desconhecido</li><li>UNSPECIFIED</li></ul></td><td><span>Outros</span></td></tr></tbody></table>
      </td>
    </tr>
    <tr>
      <td>
        Estratégia de lances
      </td>
      <td>
        * Para AC, extraído de: <Anchor target="_blank" href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.app_campaign_setting.bidding_strategy_goal_type">campaign.app\_campaign\_setting.bidding\_strategy\_goal\_type</Anchor>
        * Para não-AC, extraído de: <Anchor target="_blank" href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.bidding_strategy_type">campaign.bidding\_strategy\_type</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        Estratégia de bid padronizado da AppsFlyer
      </td>
      <td>
        <table><thead><tr><th colspan="2"><font> <span>Estratégia de lances</span> </font></th><th><font> <span>Estratégia de lances normalizada</span> </font></th></tr></thead><tbody><tr><td rowspan="3"><font> <span>AC</span> </font></td><td><ul><li><font> <span>OPTIMIZE_INSTALLS_TARGET_INSTALL_COST</span> </font></li><li><font> <span>OPTIMIZE_IN_APP_CONVERSIONS_TARGET_CONVERSION_COST</span> </font></li></ul></td><td><font> <span>Bid máx.</span> </font></td></tr><tr><td><ul><li><font> <span>OPTIMIZE_IN_APP_CONVERSIONS_TARGET_INSTALL_COST</span> </font></li><li><font> <span>OPTIMIZE_RETURN_ON_ADVERTISING_SPEND</span> </font></li></ul></td><td><font> <span>Bid escolhido</span> </font></td></tr><tr><td><ul><li><font> <span>Desconhecido</span> </font></li><li><font> <span>UNSPECIFIED</span> </font></li></ul></td><td><font> <span>Outros</span> </font></td></tr><tr><td rowspan="5"><font> <span>Não AC</span> </font></td><td><ul><li><font> <span>ENHANCED_CPC</span> </font></li><li><font> <span>MANUAL_CPC</span> </font></li><li><font> <span>MANUAL_CPM</span> </font></li><li><font> <span>MANUAL_CPV</span> </font></li></ul></td><td><font> <span>Bid manual</span> </font></td></tr><tr><td><ul><li><font> <span>MAXIMIZE_CONVERSIONS</span> </font></li><li><font> <span>MAXIMIZE_CONVERSION_VALUE</span> </font></li><li><font> <span>PAGE_ONE_PROMOTED</span> </font></li><li><font> <span>TARGET_IMPRESSION_SHARE</span> </font></li><li><font> <span>TARGET_OUTRANK_SHARE</span> </font></li><li><font> <span>TARGET_SPEND</span> </font></li></ul></td><td><font> <span>Bid automático</span> </font></td></tr><tr><td><ul><li><font> <span>PERCENT_CPC</span> </font></li><li><font> <span>TARGET_CPA</span> </font></li><li><font> <span>TARGET_CPM</span> </font></li><li><font> <span>TARGET_ROAS</span> </font></li></ul></td><td><font> <span>Bid escolhido</span> </font></td></tr><tr><td><ul><li><font> <span>COMMISSION</span> </font></li><li><font> <span>Desconhecido</span> </font></li><li><font> <span>UNSPECIFIED</span> </font></li></ul></td><td><font> <span>Outros</span> </font></td></tr><tr><td><font> <span>Outros</span> </font></td><td><font> <span>Desconhecido</span> </font></td></tr></tbody></table>
      </td>
    </tr>
    <tr>
      <td>
        Valor de bidding
      </td>
      <td>
        Valor do bid na moeda do anunciante
      </td>
    </tr>
    <tr>
      <td>
        Valor do lance original
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
        Dimensão
      </th>
      <th>
        A descrição
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Objetivo de campanha
      </td>
      <td>
        Extraído de: <Anchor target="_blank" href="https://developers.snapchat.com/api/docs/#campaigns">campaign.objective</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        Modelo de custo
      </td>
      <td>
        Extraído de: <Anchor target="_blank" href="https://developers.snapchat.com/api/docs/#squad-optimization-goals">adsquad.optimization\_goal</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        Mapeamento do modelo de custo padronizado da Appsflyer
      </td>
      <td>
        | Modelo de custo | Modelo de custo normalizado |
        | --- | --- |
        | * DESLIZAMENTOS<br />* ABERTURAS\_DE\_HISTÓRIA | CPC |
        | * USOS<br />* {"PIXEL_ADI"}ÇÃ{"O_AO_CARRINHO"}<br />* {"PIXEL_COMPRA"}<br />* {"PIXEL_CADASTRO"}<br />* {"APP_ADI"}ÇÃ{"O_AO_CARRINHO"}<br />* {"APP_COMPRA"}<br />* {"APP_CADASTRO"} | CPA |
        | APP\_INSTALLS | CPI |
        | * IMPRESSIONS | CPM (custo por mil impressões) |
        | * VIDEO\_VIEWS<br />* VISUALIZAÇÕES\_DE\_VÍDEO\_15\_SEGUNDOS | CPCV |
      </td>
    </tr>
    <tr>
      <td>
        Estratégia de lances
      </td>
      <td>
        Extraído de: <Anchor target="_blank" href="https://developers.snapchat.com/api/docs/#bid-strategy">adsquad.bid\_strategy</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        Estratégia de bid padronizado da AppsFlyer
      </td>
      <td>
        | Estratégia de lances | Estratégia de lances normalizada |
        | --- | --- |
        | * ROAS\_MÍNIMO<br />* LANCE\_AUTOMÁTICO | Bid automático |
        | {"MENOR_CUSTO_"} {"COM_LANCE_M"}ÁXIMO | Bid máx. |
        | TARGET\_COST | Bid escolhido |
      </td>
    </tr>
    <tr>
      <td>
        Valor de bidding
      </td>
      <td>
        Valor do bid na moeda do anunciante
      </td>
    </tr>
    <tr>
      <td>
        Valor do lance original
      </td>
      <td>
        Extraído de: adsquad.bid\_micro
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div data-zendesk-anchors="about-campaign-properties=sobre-as-propriedades-da-campanha h_01J1PX98QNCZG9Y9PRZQ4ZEEFK=sobre-as-propriedades-da-campanha h_01J1PX98QNX2T408GB2WV0RFZH=facebook h_01J1PX98QP22PPG9V84DD5WEM1=google h_01J1PXNDS4V16NQQQGMBND9PAF=snap" />
