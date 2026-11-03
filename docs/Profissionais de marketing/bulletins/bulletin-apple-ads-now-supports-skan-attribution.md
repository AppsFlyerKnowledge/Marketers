---
title: 'Boletim: Apple Ads agora oferece suporte para a atribuição na SKAN'
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2025-04-15T08:21:59Z'
  edited_at: '2026-10-20T03:54:44Z'
  id: 34395758837137
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/34395758837137
---
| **Novidades** | Agora, é possível fazer a ingestão completa dos postbacks da SKAN para Apple Ads (AA), que são processados e relatados pela AppsFlyer, oferecendo aos profissionais de marketing o mesmo nível de privacidade de mensuração já disponível para outras ad networks. |
| --- | --- |
| **Data da atualização** | 10/04/2025 |
| **O que você precisa saber** | A partir do **iOS 26.2**, os postbacks do Apple Ads são assinados e enviados usando o **AdAttributionKit (AAK)** em vez do **SKAdNetwork (SKAN)**.<br /><br />No **iOS 26.1 e versões anteriores**, os postbacks do Apple Ads continuam a usar o SKAdNetwork.<br /><br />Para garantir que a AppsFlyer receba todos os postbacks do Apple Ads, configure seu aplicativo para enviar **cópias de postback tanto do SKAdNetwork quanto do AdAttributionKit** para a AppsFlyer, conforme descrito na documentação para desenvolvedores da Apple.<br /><br />**<span id="where-to-find-aa-skan-data"></span>Onde encontrar dados AA na SKAN**<ul><li>**10 de abril de 2025 – 26 de maio de 2025:** Os dados podem ser encontrados no relatório <Anchor target="_blank" href="/marketers/pt/docs/skan-raw-data-reports#postback::315d5a62">cópias de postbacks brutos da SKAN</Anchor> (Data Locker).</li><li>**A partir de 27 de maio de 2025:** Os dados estão disponíveis em todos os dashboards da SKAN, APIs, exportações do Data Locker e SSOT.</li></ul>**Mudanças na atribuição**: agora, o AA pode receber crédito por instalações anteriormente atribuídas a outras ad networks na SKAN.<br /><br />**<span id="data-granularity"></span>Granularidade dos dados:**<ul><li>Os postbacks da SKAN contêm apenas campos padrão do SKAN. Os campos campaign, adset, ad, geo e creative enrichment são **NULL**.</li><li>**Mapeamento de posição (via** **skad\_campaign\_id**):</li><li>10-> Resultados de pesquisa</li><li>20-> Aba de pesquisa</li><li>30-> Aba hoje</li><li>40-> Páginas de produtos</li></ul>**<span id="h_01JXYJ6B8FP8N79CVF84VNYQCR"></span>Importante!**<br />A Apple compartilha somente informações sobre a posição do anúncio. Ela usa o campo Campaign ID nos postbacks da SKAN para refletir as quatro posições diferentes disponíveis (resultados de Pesquisa, aba de pesquisa, aba hoje e páginas de produtos). Isso significa que o Campaign ID real e o relatório Campaign Level Reporting não estarão disponíveis.<ul><li>media\_source é **Apple Search Ads** e skad\_ad\_network\_id é **com.apple.ads**.</li></ul>**<span id="skan-versions-supported"></span>Versões compatíveis da SKAN**<ul><li>O Apple Ads é compatível com as versões **1.0 a 3.0 da SKAN**, somente para **atribuição de click-through**.</li><li>A partir do iOS 26.2, o AdAttributionKit (AAK) é usado.</li><li>No momento, não há suporte para view-through.</li></ul>**SSOT**: sem alterações na lógica de desduplicação. Os postbacks do AA que não são atribuídos pelos métodos clássicos do AppsFlyer estão incluídos, o restante é desduplicado no SSOT. |
| **O que você precisa fazer** | Para ativar os dados do AA na SKAN, certifique-se de que o seu aplicativo esteja configurado para <Anchor target="_blank" href="/marketers/pt/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">encaminhar postbacks da SKAN diretamente para a AppsFlyer</Anchor>.<ul><li>Se o seu aplicativo já estiver configurado, nenhuma ação adicional é necessária.</li></ul>Atenção: os aplicativos devem ter o iOS 15 ou versões posteriores para que isso funcione. De acordo com a Apple, mais de 95% dos usuários atendem a esse requisito. |

<div data-zendesk-anchors="h_01JXYJ7NFNJP83Z2J43841ZENJ=where-to-find-aa-skan-data h_01JXYJ7S61RSK8SV11Y7QGQ9XE=data-granularity h_01JXYJ7Z0ERWPH70A291CEFMH6=skan-versions-supported" />
