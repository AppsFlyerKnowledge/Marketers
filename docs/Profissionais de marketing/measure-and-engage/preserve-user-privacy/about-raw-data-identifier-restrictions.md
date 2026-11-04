---
title: Sobre restrições de identificadores de dados brutos
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Agencies
    - Raw Reports
  created_at: '2020-03-23T08:29:01Z'
  edited_at: '2026-11-03T01:32:07Z'
  id: 360006868017
  locale: pt
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/pt/articles/360006868017
---
> **Resumo:** alguns parceiros exigem que a AppsFlyer restrinja certos campos em relatórios de dados brutos específicos. Em outros casos, os parceiros podem solicitar que a fonte de mídia seja ocultada ao compartilhar postbacks com plataformas de terceiros. Este artigo descreve essas restrições e as suas implicações.

<div id="raw-data-restriction" />

## Restrição de dados brutos

A AppsFlyer restringe o acesso a determinados campos do relatório de dados brutos com base nas configurações de <Anchor target="_blank" href="/marketers/pt/docs/apply-aggregated-advanced-privacy-framework">AAP (Aggregated Advanced Privacy)</Anchor> do anunciante ou nas políticas de compartilhamento de dados das ad networks que fornecem os dados. Essas restrições variam dependendo do tipo de relatório e do motivo da restrição.

<div id="media-source-restrictions" />

### Restrições por fonte de mídia

A tabela a seguir lista as restrições por fonte de mídia para conversões, cliques e impressões.

<div id="note" />

> 📘 **Importante!**
>
> Os dados agregados de atribuição e análise estão disponíveis sem restrições. No entanto, todos os postbacks e relatórios a nível de dispositivo estão sujeitos às limitações descritas abaixo.
>
> <Anchor target="_blank" href="/marketers/pt/docs/discrepancies-between-appsflyer-and-third-party-platforms#restrições-de-postback-em-plataformas-externas">Restrições de postback em plataformas de terceiros</Anchor>:
>
> * As restrições descritas na tabela abaixo se aplicam aos eventos incluídos nos postbacks enviados para plataformas terceiras, como plataformas de análise e marketing.
> * Poderão ser aplicadas outras restrições de postback para outros eventos.

| compras in-app | Restrição por tipo de atribuição |
| --- | --- |
| <span id="amazon-ads"></span>Anúncios da Amazon | Os dados brutos dos Amazon Ads são restritos na plataforma AppsFlyer. Como resultado, o canal de mídia é relatado como "restricted" e os detalhes da campanha ficam nulos.<br /><br />Como em qualquer SRN (Self-Reporting Network), os cliques e as impressões da Amazon não são incluídos nos relatórios de dados brutos. |
| <span id="discord"></span>Discord | Dados brutos do Discord são restritos na plataforma AppsFlyer.<br /><br />As seguintes restrições se aplicam à atribuição de view-through e click-through:<ul><li>original\_url: restricted</li><li>click\_id: restricted</li></ul>Clique e impressões do Discord não são incluídos nos relatórios de dados brutos. |
| <span id="meta-ads"></span>Meta Ads | As seguintes restrições se aplicam aos dados brutos do Meta Ads:<ul><li>Por padrão, o Meta Ads não permite a distribuição de dados device-level que contêm informações de atribuição irrestritas. No entanto, se você aceitar os Termos do Meta Advanced Mobile Measurement (AMM), poderá acessar dados de atribuição device-level do Meta Ads sem restrição. Veja <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-integration-setup#enable-meta-ads-device-level-data">Ativar dados device-level do Meta Ads</Anchor>.</li><li>Os dados da solução de deep link de AEM (iOS), assim como os dados do Google Play Install Referrer e Meta Install Referrer (Android), estão disponíveis sem restrições nos relatórios device-level.</li><li>Os dados do Install Referrer do Google Play e do Meta Install Referrer só podem aparecer em relatórios de instalação.</li><li>Os dados da solução de deep link do AEM (iOS) só podem aparecer em relatórios de reengajamento.</li></ul>Os cliques e as impressões do Meta Ads não são incluídos nos relatórios de dados brutos. |
| <span id="pinterest"></span>Pinterest | O Pinterest gerencia a lógica de restrição de dados brutos para cada evento e a comunica à AppsFlyer por meio da integração. Essa lógica pode se aplicar aos dados de atribuição tanto de clique quanto de view-through.<br /><br />Quando um evento tem restrições de dados brutos, você não pode acessar seus dados de atribuição de clique e de view-through, incluindo todos os campos de atribuição, como canal de mídia, campanha, adset, anúncio, tipo de toque, tipo de engajamento e horário do toque.<br /><br />Em todos os casos, os relatórios de dados brutos não incluem cliques e impressões do Pinterest. |
| <span id="reddit"></span>Reddit | Clique e impressões do Reddit não são incluídos nos relatórios de dados brutos.<br /><br />**Lembrete:** Os dados recebidos sobre uma campanha do Reddit estão sujeitos aos <Anchor target="_blank" href="https://business.reddithelp.com/s/article/Reddit-Business-Tool-Terms">Reddit Business Tool Terms</Anchor> e incluem, entre outras restrições, a proibição de usar dados do Reddit para criar perfis de quaisquer usuários. |
| <span id="samsung-dsp"></span>Samsung DSP | A partir de 17 de outubro de 2023:<br /><br />A atribuição por view-through e click-through da Samsung é limitada. Os seguintes itens não estão incluídos nas ferramentas de entrega de dados brutos:<ul><li>Fonte de mídia (samsungdsp\_int)</li><li>Tipo de toque atribuído (impressão/clique)</li><li>O tempo de toque atribuído está disponível</li><li>Os detalhes da campanha estão disponíveis</li></ul>Cliques e impressões da Samsung não estão incluídos nos relatórios de dados brutos<br /><br />A partir de 30 de agosto de 2025:<br /><br />A atribuição por view-through e click-through da Samsung EMEA é limitada para engajamentos recebidos com `af_data_restriction=attribution` na URL. Os seguintes itens não estão incluídos nas ferramentas de entrega de dados brutos:<ul><li>Canal de mídia: relatado como restricted</li><li>Tipo de toque atribuído (impressão/clique)</li><li>O tempo de toque atribuído está disponível</li><li>Os detalhes da campanha estão disponíveis</li></ul>Cliques e impressões da Samsung não estão incluídos nos relatórios de dados brutos |
| <span id="snapchat"></span>Snapchat | As seguintes restrições se aplicam aos dados brutos do Snapchat:<ul><li>A partir de 1º de março de 2023, as desinstalações do Snapchat não são incluídas nos Relatórios de dados brutos.</li><li>Os dados em nível de dispositivo da atribuição de view-through são limitados em alguns casos. A lógica das restrições de dados brutos é gerenciada pelo Snapchat, por evento, e comunicada à AppsFlyer por meio da integração.</li><li>Quando o evento tem restrições de dados brutos, os itens a seguir **não** são restritos nas ferramentas de entrega de dados brutos:</li></ul><ul><li>Fonte de mídia (snapchat\_int)</li><li>Disponível apenas em <Anchor target="_blank" href="/marketers/pt/docs/about-data-locker-advanced-reports">relatórios avançados</Anchor>.</li><li>Tipo de toque atribuído (impressão)</li><li>Hora do toque atribuído (relatada apenas como data, "dd/mm/aaaa")</li><li>Nome e ID da campanha (a partir de 15 de dezembro de 2025)</li><li>Nome e ID do conjunto de anúncios (a partir de 15 de dezembro de 2025)</li></ul><ul><li>As restrições acima não se aplicam a engaged views.</li></ul>Cliques e impressões do Snapchat não são incluídos nos relatórios de dados brutos. |
| <span id="tiktok-for-business"></span>TikTok para Empresas | As seguintes restrições se aplicam à atribuição por view-through:<ul><li>Media source (tiktokglobal\_int)</li><li>O canal foi relatado como TikTok / Pangle</li><li>Tipo de toque atribuído (impressão)</li><li>Tempo de toque atribuído (relatado apenas como data - "dd/mm/aaaa")</li><li>A campanha é indicada como *"restricted"*</li></ul>A partir de 19 de maio de 2026, as seguintes ferramentas de dados brutos foram atualizadas: Pull API, Data Locker e a página de exportação de dados brutos.<br /><br />A partir de 25 de junho de 2026, as seguintes ferramentas de dados brutos foram atualizadas: Push API e a API Get conversion data (GCD).<br /><br />As alterações são:<ul><li>Apenas o campo `original_url` é restrito (fica vazio)</li><li>Todos os outros campos de atribuição são totalmente compatíveis</li></ul>As restrições acima não se aplicam a engaged views.<br /><br />Cliques e impressões via Data Locker do tiktokglobal\_int são restritos nos relatórios. |
| <span id="uber"></span>Uber | As seguintes restrições se aplicam à atribuição de view-through e click-through:<ul><li>Canal de mídia (uber\_int): disponível</li><li>Detalhes da campanha: disponíveis</li></ul>Cliques e impressões da Uber não são incluídos nos relatórios de dados brutos. |
| <span id="x-ads-formerly-twitter"></span>X Ads (antigo Twitter) | Em alguns casos, a depender das escolhas do usuário no X Ads, os dados brutos podem ser restritos na plataforma da AppsFlyer.<br /><br />**Até 15 de julho de 2025:** Os eventos atribuídos do X Ads não apareciam nos relatórios de dados brutos.<br /><br />**A partir de 15 de julho de 2025:** Eventos atribuídos passaram a ser incluídos nos relatórios de dados brutos, com as seguintes restrições:<ul><li>Canal de mídia (twitter): disponível</li><li>Detalhes da campanha: relatados como *restricted*</li><li>Canal (Twitter): disponível</li><li>Tipo de toque atribuído: disponível</li><li>Hora do toque atribuído: reportada apenas como data (`dd/mm/yyyy`)</li></ul>Cliques e impressões do X Ads não são incluídos nos relatórios de dados brutos.<br /><br />O acesso a dados brutos irrestritos depende da participação no **programa Advanced Mobile Measurement (AMM)** do X Ads e das configurações de privacidade do usuário final:<ul><li>AMM não habilitado: todos os cliques e impressões são enviados com `af_data_restriction=attribution`. Todos os eventos resultantes são restritos.</li><li>AMM habilitado:<ul><li>Usuários da UE: os eventos são restritos se o compartilhamento de dados com parceiros de negócios não for autorizado.</li><li>Usuários que não concordaram em compartilhar dados: os eventos são restritos (`af_data_restriction=attribution`).</li><li>Usuários que concordaram em compartilhar dados com parceiros de negócios: os eventos não são restritos (`af_data_restriction=none`).</li></ul></li></ul>Para mais informações, consulte o <Anchor target="_blank" href="/marketers/pt/docs/x-ads-formerly-twitter-ads-setup-guide-overview#privacidade-do-usuário-no-x-ads">guia de configuração do X Ads, seção de privacidade do usuário</Anchor>. |
| Walmart | As seguintes restrições se aplicam à atribuição de view-through e click-through:<ul><li>`original_url`: restrito</li></ul>Cliques e impressões do Walmart não estão incluídos nos relatórios de dados brutos. |

<div id="raw-data-context" />

### Contexto dos dados brutos

A restrição em nível de campo de dados brutos depende do contexto dos dados, conforme listado na tabela a seguir.

| Tipo de restrição | Relatórios afetados |
| --- | --- |
| [Fonte de mídia restrita](/docs/about-raw-data-identifier-restrictions#restrições-por-fonte-de-mídia): Origem do usuário | <ul><li>Atribuição: instalações, conversões de retargeting e desinstalações</li><li>Eventos in-app, sessões</li><li>Relatórios do Protect360</li></ul> |
| Totalmente restrito | <ul><li>Cliques</li><li>Impressões</li><li>Cliques bloqueados (Protect360)</li></ul> |

<div id="delivery-of-raw-data" />

### Envio de dados brutos

Os dados de atribuição a nível de usuário na AppsFlyer estão disponíveis usando as seguintes ferramentas de entrega de dados brutos:

* Relatório do Data Locker
* Pull API de dados brutos
* API de push
* Página de exportação do dashboard
* Postbacks para ad networks
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data">API Get conversion data (GCD)</Anchor> no contexto da API de dados do lado do cliente e a nível de usuário

<div id="unavailable-attribution-fields" />

<Accordion title="Campos de atribuição não disponíveis">

Os campos a seguir ficam indisponíveis quando a fonte de mídia é restrita:

| Nome de exibição | Nome da API |
| --- | --- |
| As ad | af\_ad |
| ID do anúncio | af\_ad\_id |
| Tipo de anúncio | af\_ad\_type |
| Conjunto de anúncios | af\_adset |
| Adset ID | af\_adset\_id |
| Janela de lookback de atribuição | af\_attribution\_lookback |
| ID da campanha | af\_c\_id |
| Canal | af\_canal |
| Moeda do custo | af\_cost\_currency |
| Modelo de custo | af\_cost\_model |
| Valor de custo | af\_cost\_value |
| Palavras-chave | af\_keywords |
| parceira | af\_prt |
| ID do site | af\_siteid |
| ID do subsite | af\_sub\_siteid |
| Sub param [n] (n=1-5) | af\_sub[n] (n=1-5) |
| Hora de atribuição do toque | attributed\_touch\_time |
| Tipo de toque atribuído | tipo\_de\_toque\_atribuído |
| Campaign | Twitter |
| Deeplink URL | deeplink\_url |
| Referência HTTP | http\_referrer |
| Loja de aplicativos na instalação | instalar\_app\_store |
| ID da palavra-chave | keyword\_id |
| Tipo de correspondência das palavras-chave | keyword\_match\_type |
| Tipo de correspondência | match\_type |
| ID da conta da rede | network\_account\_id |
| URL original | original\_url |
| Janela de reengajamento | af\_reengagement \_window |
| Página do produto na loja | store\_product\_page |

</Accordion>

<div id="identifier-restriction" />

<Accordion title="Restrição de identificador">

Quando a restrição de identificador é aplicada, os campos listados na tabela seguinte são os únicos campos disponíveis nos relatórios de dados brutos.

| Nome na API |
| --- |
| <span id="event_time"></span>event\_time |
| <span id="event_name"></span>nome\_do\_evento |
| <span id="event_revenue"></span>event\_revenue |
| <span id="event_revenue_currency"></span>event\_currency |
| <span id="event_revenue_usd"></span>event\_revenue\_usd |
| <span id="af_cost_model"></span>af\_cost\_model |
| <span id="af_cost_value"></span>af\_cost\_value |
| <span id="af_cost_currency"></span>af\_cost\_currency |
| <span id="event_source"></span>event\_source |
| <span id="media_source"></span>fonte\_de\_mídia |
| <span id="af_channel"></span>af\_canal |
| <span id="campaign"></span>Twitter |
| <span id="af_c_id"></span>af\_c\_id |
| <span id="af_adset"></span>af\_adset |
| <span id="af_adset_id"></span>af\_adset\_id |
| <span id="af_ad"></span>af\_ad |
| <span id="af_ad_id"></span>af\_ad\_id |
| <span id="af_ad_type"></span>af\_ad\_type |
| <span id="af_siteid"></span>af\_siteid |
| <span id="af_sub_siteid"></span>af\_sub\_siteid |
| <span id="app_id"></span>ativado |
| <span id="app_name"></span>ativado |
| <span id="bundle_id"></span>bundle\_id |
| <span id="is_retargeting"></span>is\_retargeting |
| <span id="retargeting_conversion_type"></span>retargeting\_conversion\_type |
| <span id="is_primary_attribution"></span>é\_atribuição\_primária |
| <span id="af_attribution_lookback"></span>af\_attribution\_lookback |
| <span id="af_reengagement_window"></span>af\_reengagement \_window |
| <span id="country_code"></span>código\_país |
| <span id="blocked_reason"></span>blocked\_reason |
| <span id="blocked_reason_value"></span>blocked\_reason\_value |
| <span id="blocked_reason_rule"></span>blocked\_reason\_rule |
| <span id="blocked_sub_reason"></span>blocked\_sub\_reason |
| <span id="platform"></span>platforma |
| <span id="is_paid_media"></span>is\_paid\_media |

</Accordion>

<div id="faq" />

## Perguntas frequentes

<div id="what-events-are-restricted" />

<Accordion title="Quais eventos são restritos?">

Os eventos restritos, conforme detalhado na [tabela acima](/docs/about-raw-data-identifier-restrictions#restrições-por-fonte-de-mídia), podem incluir conversões (instalações e reengajamentos) e eventos in-app associados, atribuídos a ad networks restritas.

</Accordion>

<div id="how-does-the-restricted-media-source-impact-raw-data-reports" />

<Accordion title="Como a fonte de mídia restrita afeta os relatórios de dados brutos?">

* O campo *fonte de mídia* é preenchido com *restricted*.
* Os campos de atribuição listados neste artigo estão vazios ou são preenchidos com *null*.

**Exemplo de relatório:** <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vScXJznEex0WwdCy78Bm8LtrhbCk1jNy14O_t7etrq5ab5v4CIEiInfFD4B1EsZCE-_w-dVRAxl_cu4/pub?output=csv">Dados brutos restritos</Anchor> de instalações, enviados via arquivo CSV. Outros relatórios de dados brutos são preenchidos de forma semelhante.

</Accordion>

<div id="how-does-the-restricted-media-source-impact-postbacks-sent-to-partners" />

<Accordion title="Como a fonte de mídia restrita afeta os postbacks enviados para os parceiros?">

Os postbacks enviados para os parceiros não incluem campos de atribuição.

</Accordion>

<div id="how-do-restricted-events-impact-postbacks-to-thirdparty-platforms" />

<Accordion title="Como os eventos restritos impactam os postbacks para plataformas de terceiros?">

Os postbacks para as ad networks atribuídas listadas na [tabela acima](#restrições-por-fonte-de-mídia) não são enviados para plataformas de terceiros.

</Accordion>

<div id="do-nonrestricted-events-impact-postbacks-to-thirdparty-platforms" />

<Accordion title="Os eventos não restritos afetam os postbacks para plataformas terceiras?">

Para eventos enviados para plataformas de terceiros, como plataformas de analytics e marketing, consulte as <Anchor target="_blank" href="/marketers/pt/docs/discrepancies-between-appsflyer-and-third-party-platforms#restrições-de-postback-em-plataformas-externas">restrições de postback em plataformas de terceiros</Anchor>. Em alguns casos, os postbacks de eventos não restritos não incluem o canal de mídia. Isso quer dizer que a atribuição é considerada como orgânica.

</Accordion>

<div id="what-about-the-data-of-assists-that-form-part-of-the-attribution" />

<Accordion title="E quanto aos dados de assistências que fizeram parte da atribuição?">

Os dados de assistências são considerados dados de atribuição e não estão disponíveis.

</Accordion>

<div id="see-also" />

> 📄 **Veja também**
>
> <Anchor target="_blank" href="/marketers/pt/docs/user-level-data-retention">Retenção de dados user-level</Anchor>

<div data-zendesk-anchors="raw-data-restriction=restri%C3%A7%C3%A3o-de-dados-brutos 01H7WQHTV9RM2JF2BV45XF626H=restri%C3%A7%C3%A3o-de-dados-brutos media-source-restrictions=restri%C3%A7%C3%B5es-por-fonte-de-m%C3%ADdia 01H7WQHTV9HJEHHH1N8VN6APX6=restri%C3%A7%C3%B5es-por-fonte-de-m%C3%ADdia 01H7WQHTV90YFRP3Z9AEP7ACRD=importante raw-data-context=contexto-dos-dados-brutos 01H7WQHTVA8H9FTBJ1FB6BJQ2A=contexto-dos-dados-brutos delivery-of-raw-data=envio-de-dados-brutos 01H7WQHTVA0XP6B2H95EEM7EYD=unavailable-attribution-fields 01H7WQHTVA7ERWW1PC3DF5H0NP=identifier-restriction faq=perguntas-frequentes 01H7WQHTVA5439QPE6GNXNKJ63=perguntas-frequentes h_01HDBND48E05P1WV51ZJGD072N=what-events-are-restricted 01H7WQHTVAHCK7QDZ5P25YRQ2D=how-does-the-restricted-media-source-impact-raw-data-reports 01H7WQHTVABKATP6B6XN4NRC54=how-does-the-restricted-media-source-impact-postbacks-sent-to-partners h_01HDBND48EDTAFBFXTADGWJADM=how-do-restricted-events-impact-postbacks-to-thirdparty-platforms h_01HE5TK3WSNBPM6W5D1Y9S6PDX=do-nonrestricted-events-impact-postbacks-to-thirdparty-platforms 01H7WQHTVA60PWZ017WJMRTKVP=what-about-the-data-of-assists-that-form-part-of-the-attribution h_01HE7SCVN3VJ4Y6KF2QZSNBEMZ=veja-tamb%C3%A9m" />
