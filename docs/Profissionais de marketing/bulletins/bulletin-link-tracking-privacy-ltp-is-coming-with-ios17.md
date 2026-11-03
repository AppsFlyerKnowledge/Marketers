---
title: 'Boletim: o recurso Link tracking Privacy (LTP) está chegando com o iOS17'
metadata:
  keywords:
    - Marketers
    - Smart Banners and Scripts
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2023-09-21T08:37:39Z'
  edited_at: '2026-10-20T03:56:07Z'
  id: 18730398273553
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/18730398273553
---
| **Novidades** | iOS17 detectará e removerá parâmetros identificados como parâmetros de rastreamento dos links que os usuários compartilham em aplicativos integrados: Mail, Messages e o modo Navegação Privada do Safari.<br /><br />Fizemos testes internos para ver como a LTP afeta o OneLink. Nossos resultados sugerem que nenhum dos parâmetros do AppsFlyer foi removido. Estes são os resultados dos nossos testes:<br /><br />**<span id="h_01HAVEDAEFTDVGS1SXBD7NEJFE"></span>Os seguintes parâmetros são removidos pela LTP**<ul><li>`gclid` - ID do Google Ads / Analytics</li></ul><ul><li>`fbclid` - ID de anúncios do Facebook</li></ul>**<span id="h_01HAVEDAEFN7XEPK3TNCSZRAMW"></span>Os seguintes parâmetros não são afetados pela LTP**<ul><li>Parâmetros UTM</li></ul>**<span id="h_01HAVEDAEFMGD1SFYRJNXE9JBE"></span>Parâmetros de atribuição da AppsFlyer:**<ul><li>`pid`</li></ul><ul><li>`c`</li></ul><ul><li>`Is_regtargeting`</li></ul><ul><li>`af_channel`</li></ul><ul><li>`af_adset`</li></ul><ul><li>`af_ad`</li></ul><ul><li>`af_sub1-10`</li></ul><ul><li>`af_inactivity_window`</li></ul><ul><li>`af_click_lookback`</li></ul><ul><li>`af_cost_value`</li></ul><ul><li>`af_cost_currency`</li></ul>**<span id="h_01HAVEDAEFEFZ1ZCPAZ05C3AWW"></span>Parâmetros de redirecionamento da AppsFlyer**<ul><li>`af_dp`</li></ul><ul><li>`deep_link_value`</li></ul><ul><li>`af_deep_link_sub1-10`</li></ul><ul><li>`af_web_dp`</li></ul><ul><li>`af_ios_url`</li></ul><ul><li>`af_android_url`</li></ul><ul><li>`af_xp`</li></ul> |
| --- | --- |
| **Data de início** | A data do lançamento público do iOS17 (18 de setembro de 2023) |
| **O que isso afeta** | **<span id="h_01HAVEDAEFE7K3FT7RNA0FANHV"></span>Redirecionamento e deep linking**<br /><br />É improvável que o redirecionamento e o deep linking sejam afetados devido a essa mudança. O único caso em que o deep linking pode ser afetado é quando a atribuição depende de GCLID ou FBCLID.<br /><br />**<span id="h_01HAVEDAEFAB2AGW54XW52YAXJ"></span>Web-2-app**<br /><br />Como a LTP se aplica apenas ao modo de navegação privada do Safari, esperamos um impacto mínimo na atribuição de fluxos web-to-app. No entanto, quando o usuário está no modo de navegação privada do Safari, os parâmetros GCLID e FBCLID, que a LTP remove, não serão mapeados pelos Smart Scripts.<br /><br />**<span id="h_01HAVEDAEFTC8QRKTZCQZSC8G6"></span>E-mail, SMS e notificações**<br /><br />Os aplicativos nativos da Apple, como Mail e Messages, bloquearão os parâmetros de rastreamento relevantes mencionados acima. Portanto, usar links nessas campanhas pode resultar na perda de dados em nível de usuário. Além disso, alguns dos identificadores de estatísticas do provedor de serviços de e-mail (ESP) podem ser bloqueados como parte dessa mudança, o que pode impactar as estatísticas das campanhas de e-mail. Recomendamos que você entre em contato com seu ESP para entender totalmente o impacto. |