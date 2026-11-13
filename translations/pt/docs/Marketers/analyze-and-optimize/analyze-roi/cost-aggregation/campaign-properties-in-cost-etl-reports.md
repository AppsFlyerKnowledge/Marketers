---
title: Propriedades da campanha em relatórios de custo ETL
metadata:
  keywords:
    - custo
    - Anunciantes
    - Xpend
    - Comerciantes
    - ROI360
x-zendesk:
  category: Comerciantes
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Comerciantes
    - ROI360
  created_at: '2021-06-02T17:21:22Z'
  edited_at: '2025-04-05T11:08:21Z'
  id: 360020994977
  locale: ptbr
  section: Custo agregado
  section_id: 6551029483281
  url: >-
    https://support.appsflyer.com/hc/pt-br/articles/360020994977-Campaign-properties-in-cost-ETL-reports
---
> **Em uma instância:** Saiba mais sobre as propriedades da campanha e como elas são exibidas nos dados da ETL de Custo de AppsFlyer.

<div id="about-campaign-properties" />

## Sobre as propriedades da campanha

As propriedades da campanha são um grupo especial de dimensões que representam várias configurações de uma campanha publicitária, incluindo o objetivo da campanha, tipo de oferta e quantidade de oferta. Estas são as configurações que você normalmente vê e edita no seu painel de rede de anúncios, mas o AppsFlyer puxa as dimensões das propriedades da campanha e torna os dados disponíveis no ETL de Custos, assim como você vê outras dimensões.

Com dados de propriedades da campanha, você pode:

- Ver todas as propostas de alterações feitas pela sua equipe UA.
- Medir e analisar a eficácia de uma mudança de oferta e se teve o efeito pretendido.

Dados de propriedades da campanha AppsFlyer está disponível para Meta anúncios e Google. Veja quais dados o AppsFlyer puxa e como ele é normalizado e mapeado para cada rede de anúncios, nas seções que se seguem.

<div id="facebook" />

<Accordion title="Meta ads">

Veja quais dados o AppsFlyer pulls, e como ele é padronizado e mapeado para os Meta ads, na tabela que se segue.

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
      <td>U
        Objetivo da Campanha
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
        Extraído de: <Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/bidding/overview#opt">adset.optimization\_gol</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        AppsFlyer normalizado mapeamento dos modelos de custos
      </td>
      <td>
        | Modelo de custo | Modelo de custo normalizado |
        | --- | --- |
        | <ul><li>LINK_CLIQUE</li><li>LOCAL_NOTIF_SETTINGS_POPUP_TITLE</li><li>RESPOSTAS</li><li>PLAYLIST_SHOP_DESCRIPTION</li></ul> ★ CPC &
        de CPC <ul><li>CONVERSÕES_ OFSITES</li><li>GET_EVENTOS</li><li>LAD_GENERAÇÃO</li></ul> de CPA £
        £APP\_INSTALLS ├CPI :trade_mark
        ├VALUE ├ROI ├
 <ul><li>ANQUIRES</li><li>IMPRESSÕES</li><li>SOCIAL_IMPRESSIONS</li></ul> ★ CPM L&gU
        L&br <ul><li>ALGULAR</li><li>VIDEO_NOTIF_SETTINGS_POPUP_TITLE</li><li>YOU_NEED_PLAYLISTS_LABEL</li></ul> (ExplicitText="CPCV (EN
      </td>
    </tr>
    <tr>
      <td>
        Estratégia de lances
      </td>
      <td>
        Extraído de: <Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/bidding/overview/bid-strategy">Adset.bid\_estratégia</Anchor><br /><br />Se não houver bid\_strategy no nível do conjunto de anúncios, então: <Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/bidding/overview/bid-strategy">campanha.bid\_estratégia</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        Estratégia de oferta normalizada de AppsFlyer
      </td>
      <td>Estratégia de Ajuda de 
        Econômica e estratégia de oferta normalizada ¶
        Econômica --- ├
├ <ul><li>{"LOWEST_COST_"} WITHOUT_CAP</li><li>COST_CAPS</li><li>{"LOWEST_COST_"} WITH_MIN_ROAS</li></ul> 『Auto oferta £
        ├TARGET\_COST 「Alvo de oferta :trade_mark
        『Qualquer outra coisa ë
      </td>
    </tr>
    <tr>
      <td>
        Valor do lance
      </td>
      <td>U
        valor de renda na moeda de anunciante
      </td>
    </tr>
    <tr>
      <td>
        Valor original da oferta
      </td>
      <td>
        Puxado de: adset.bid\_amount
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="google" />

<Accordion title="Google">

Veja quais dados AppsFlyer pulls, e como eles são padronizados e mapeados ao Google, na tabela que se segue.

<table><thead><tr><th><font> <span>Dimensão</span> </font></th><th><span> <font>Descrição</font> </span></th></tr></thead><tbody><tr><td><span> <font> <span>Objetivo da Campanha</span> </font> </span></td><td><p><font> <span>Puxado de: <a href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.advertising_channel_sub_type" target="_blank">campaign.advertising_channel_sub_type</a></span> </font></p><p><font> <span>Nota: A seguinte população de campos depende do channel_sub_type:</span> </font></p><ul><li><font> <span>AC: APP_CAMPAIGN ou APP_CAMPAIGN_FOR_ENGAGEMENT</span> </font></li><li><font> <span>Não AC: Cada outro valor para channel_sub_type</span> </font></li></ul></td></tr><tr><td><span> <font>Modelo de custo</font> </span></td><td><ul><li><span>Para AC, puxado de: <a href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.app_campaign_setting.bidding_strategy_goal_type" target="_blank">campaign.app_campaign_setting.bidding_strategy_goal_type</a></span></li><li><span>Para non-AC, puxado de: <a href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.bidding_strategy_type" target="_blank">campaign.bidding_strategy_type</a></span></li></ul></td></tr><tr><td><span> <span>AppsFlyer normalizado modelo de custo mapeamento</span> </span></td><td><table><thead><tr><th colspan="2">Modelo de custo</th><th>Modelo de custo normalizado</th></tr></thead><tbody><tr><td rowspan="4"><span>AC</span><span><br/></span></td><td><ul><li>OPTIMIZE_INSTALLS_TARGET_TITLE</li><li>OPTIMIZE_APP_CONVERSIONS_TARGET_TITLE</li></ul></td><td><span>CPI</span></td></tr><tr><td><p>OPTIMIZE_APP_CONVERSIONS_TITLE</p></td><td><span>CPA</span></td></tr><tr><td>OPTIMIZE_RETURN_PLAYLIST_DESCRIPTION</td><td><span>ROI</span></td></tr><tr><td><ul><li>DESCONHECIDO</li><li>ESPECÍFICO</li></ul></td><td><span>Outro</span></td></tr><tr><td>Non-AC</td><td><ul><li>ANQUIRES</li><li>PLAYLIST_DEACTIVATE_BTN</li><li>MANUAL_CPC</li><li>PLAYLIST_SHOP_DESCRIPTION</li><li>TARGET_PICK_PLAYLIST</li></ul></td><td><span>CPC</span></td></tr><tr><td> </td><td><ul><li>MANUAL_CPM</li><li>TARGET_CPM</li><li>PLAYLIST_DEACTIVATE_DESCRIPTION</li></ul></td><td><span>CPM</span></td></tr><tr><td> </td><td>MANUAL_CPV</td><td><span>CPCV</span></td></tr><tr><td> </td><td><ul><li>MAXIMIZE_CONVERSÕES</li><li>TARGET_CPA</li></ul></td><td><span>CPA</span></td></tr><tr><td> </td><td><ul><li>MAXIMIZE_CONVERSION_VALOR</li><li>TARGET_ROAS</li></ul></td><td><span>ROI</span></td></tr><tr><td><span> </span></td><td><ul><li>COMISSÃO</li><li>PAGE_ONE_PROMOTED</li><li>TARGET_OUTRANK_SHARE</li><li>DESCONHECIDO</li><li>ESPECÍFICO</li></ul></td><td><span>Outro</span></td></tr></tbody></table></td></tr><tr><td><span> <font>Estratégia de lances</font> </span></td><td><ul><li><span>Para AC, puxado de: <a href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.app_campaign_setting.bidding_strategy_goal_type" target="_blank">campaign.app_campaign_setting.bidding_strategy_goal_type</a></span></li><li><span>Para non-AC, puxado de: <a href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.bidding_strategy_type" target="_blank">campaign.bidding_strategy_type</a></span></li></ul></td></tr><tr><td><font> <span>AppsFlyer normalizado estratégia de oferta</span> </font></td><td><table><thead><tr><th colspan="2"><font> <span>Estratégia de lances</span> </font></th><th><font> <span>Estratégia de oferta normalizada</span> </font></th></tr></thead><tbody><tr><td rowspan="3"><font> <span>AC</span> </font></td><td><ul><li><font> <span>OPTIMIZE_INSTALLS_TARGET_INSTALL_CST</span> </font></li><li><font> <span>OPTIMIZE_IN_APP_CONVERSIONS_TARGET_CONVERSION_COST</span> </font></li></ul></td><td><font> <span>Anual</span> </font></td></tr><tr><td><ul><li><font> <span>OPTIMIZE_IN_APP_CONVERSIONS_TARGET_INSTALL_COST</span> </font></li><li><font> <span>OPTIMIZE_RETURN_ON_ADVERTISING_SPEND</span> </font></li></ul></td><td><font> <span>Target bid</span> </font></td></tr><tr><td><ul><li><font> <span>DESCONHECIDO</span> </font></li><li>U<font> <span>ESPECIFICADO</span> </font></li></ul></td><td><font> <span>Outro</span> </font></td></tr><tr><td rowspan="5"><font> <span>Non-AC</span> </font></td><td><ul><li>U<font> <span>INHANCED_CPC</span> </font></li><li>U<font> <span>MANUAL_CPC</span> </font></li><li>U<font> <span>MANUAL_CPM</span> </font></li><li>U<font> <span>MANUAL_CPV</span> </font></li></ul></td><td><font> <span>Oferta manual</span> </font></td></tr><tr><td><ul><li><font> <span>MAXIMIZE_CONVERSIONS</span> </font></li><li><font> <span>MAXIMIZE_CONVERSION_VALUE</span> </font></li><li><font> <span>PAGE_ONE_PROMOTED</span> </font></li><li>U<font> <span>TARGET_IMPRESSION_SHARE</span> </font></li><li><font> <span>TARGET_OUTRANK_SHARE</span> </font></li><li><font> <span>TARGET_SPEND</span> </font></li></ul></td><td><font> <span>Auto bid</span> </font></td></tr><tr><td><ul><li><font> <span>PERCENT_CPC</span> </font></li><li><font> <span>TARGET_CPA</span> </font></li><li><font> <span>TARGET_CPM</span> </font></li><li><font> <span>TARGET_ROAS</span> </font></li></ul></td><td><font> <span>Target bid</span> </font></td></tr><tr><td><ul><li>U<font> <span>COMISSÃO</span> </font></li><li><font> <span>DESCONHECIDO</span> </font></li><li>U<font> <span>ESPECIFICADO</span> </font></li></ul></td><td><font> <span>Outro</span> </font></td></tr><tr><td>U<font> <span>Qualquer outra coisa</span> </font></td><td><font> <span>Desconhecido</span> </font></td></tr></tbody></table></td></tr><tr><td><span> <font>Valor do lance</font> </span></td><td><span> <font>Valor do lance na moeda do anunciante</font> </span></td></tr><tr><td><span> <font>Valor Original da licitação</font> </span></td><td><span> <font>Puxado de: </font> </span> <a href="https://developers.google.com/google-ads/api/fields/v5/campaign#campaign.target_cpa.target_cpa_micros" target="_blank">campaign.target_cpa.target_cpa_micros</a></td></tr></tbody></table>

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
        Descrição
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>U
        Objetivo da Campanha
      </td>
      <td>
        Extraído de: <Anchor target="_blank" href="https://developers.snapchat.com/api/docs/#campaigns">campanha.objetivo</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        Modelo de custo
      </td>
      <td>
        Extraído de: <Anchor target="_blank" href="https://developers.snapchat.com/api/docs/#squad-optimization-goals">adsquad.optimization\_target</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        AppsFlyer normalizado mapeamento dos modelos de custos
      </td>
      <td>
        | Modelo de custo | Modelo de custo normalizado |
        | --- | --- |
        | <ul><li>ESPECIAS</li><li>CHAT_NOTIF_SETTINGS_POPUP_TITLE</li></ul> ★ CPC &
        de CPC <ul><li>USOS</li><li>PLAYLIST_ACTIVATE_DESC</li><li>PLAYLIST_DEACTIVATE_DESCRIPTION</li><li>PICK_PLAYLIST_DESCRIPTION</li><li>APP_ADD_TO_CHALLENGE_CHALLENGES</li><li>PLAYLIST_DEACTIVATE_TEXT</li><li>PLAYLIST_SHOP_DESCRIPTION</li></ul> | CPA |
        | APP\_INSTALLS | CPI |
        | <ul><li>IMPRESSÕES</li></ul> ★ CPM L&gU
        L&br <ul><li>VIDEO_NOTIF_SETTINGS_POPUP_TITLE</li><li>VIDEO_VIEWS_15_SEC</li></ul> (ExplicitText="CPCV (EN
      </td>
    </tr>
    <tr>
      <td>
        Estratégia de lances
      </td>
      <td>
        Extraído de: <Anchor target="_blank" href="https://developers.snapchat.com/api/docs/#bid-strategy">estratégia adsquad.bid\_</Anchor>
      </td>
    </tr>
    <tr>
      <td>
        Estratégia de oferta normalizada de AppsFlyer
      </td>
      <td>Estratégia de Ajuda de 
        Econômica e estratégia de oferta normalizada ¶
        Econômica --- ├
├ <ul><li>MIN_ROAS</li><li>AUTO_BID</li></ul> | Auto bid |
        | {"LOWEST_COST_"} {"WITH_MAX_BID"} | Max bid |
        | TARGET\_COST | Target bid |
      </td>
    </tr>
    <tr>
      <td>
        Valor do lance
      </td>
      <td>U
        valor de renda na moeda de anunciante
      </td>
    </tr>
    <tr>
      <td>
        Valor original da oferta
      </td>
      <td>
        Puxado de: adsquad.bid\_micro
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div data-zendesk-anchors="h_01J1PX98QNCZG9Y9PRZQ4ZEEFK=about-campaign-properties h_01J1PX98QNX2T408GB2WV0RFZH=facebook h_01J1PX98QP22PPG9V84DD5WEM1=google h_01J1PXNDS4V16NQQQGMBND9PAF=snap" />
