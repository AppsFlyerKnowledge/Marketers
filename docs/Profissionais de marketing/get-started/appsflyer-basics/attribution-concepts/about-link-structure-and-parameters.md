---
title: Sobre estrutura e parâmetros do link
metadata:
  keywords:
    - pid
    - Marketers
    - af_
    - af
    - c
    - af_mp
    - clickid
    - af_siteid
    - af_sub_siteid
    - af_c_id
    - af_adset_id
    - af_ad_type
    - af_viewthrough
    - af_cost_model
    - af_cost_value
    - af_web_dp
    - af_ref
    - af_ip
    - af_os_version
    - deep_link_sub
    - deep_link_value
    - af_og_title
    - af_og_description
    - af_og_image
    - af_prt
    - af_adset
    - af_ad
    - af_ad_id
    - af_channel
    - af_keywords
    - af_cost_currency
    - af_sub
    - af_r
    - af_dp
    - af_force_deeplink
    - is_incentivized
    - af_param_forwarding
    - af_partner_account_id
    - af_ua
    - af_os
    - af_model
    - af_media_type
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2015-12-24T11:50:00Z'
  edited_at: '2026-08-19T00:08:47Z'
  id: 207447163
  locale: pt
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/pt/articles/207447163
---
> **Resumo:**  Conheça a estrutura e os parâmetros do link de atribuição da AppsFlyer.

<div id="overview" />

## Visão geral

Os links de atribuição permitem que os anunciantes coletem dados sobre o engajamento do usuário com um anúncio. Os links de atribuição são incorporados nos anúncios e notificam a AppsFlyer quando os usuários se engajam com um anúncio. A interação pode ocorrer ao clicar em um anúncio ou quando um usuário visualiza uma impressão de anúncio. Uma cópia da URL de atribuição é enviada para a AppsFlyer.

Os links de atribuição são gerados através do **OneLink** ou de um **link de plataforma única**.

|  | OneLink (link multiplataforma) | Link de plataforma única |
| --- | --- | --- |
| Descrição e quando utilizar | Utilizar quando:<ul><li>Você deseja um único link para todas as plataformas.</li><li>São necessárias capacidades de deep linking.</li><li>Você quer usar os App Links do Android ou os Links Universais do iOS para abrir o aplicativo.</li></ul><Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">Saiba mais sobre o OneLink</Anchor> | Utilizar quando:<ul><li>Você só utiliza uma única plataforma. Por exemplo, Android e não iOS.</li><li>Você só usa esquemas URI para abrir o aplicativo.</li></ul><Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">Saiba mais sobre como configurar um parceiro integrado</Anchor> |
| Pré-requisitos | <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template">Template do OneLink</Anchor> | Nenhum |
| Informações necessárias | <ul><li>[Canal de mídia](/docs/about-link-structure-and-parameters#partner-id-pid-parameter)</li><li>[Campaign](#c)</li><li>[ID do site/ID do subsite](/docs/about-link-structure-and-parameters#site-id-parameter)</li></ul> | <ul><li>[Canal de mídia](/docs/about-link-structure-and-parameters#partner-id-pid-parameter)</li><li>[Campaign](#c)</li><li>[ID do site/ID do subsite](/docs/about-link-structure-and-parameters#site-id-parameter)</li></ul> |
| URL base | `{subdomain}`.onelink.me | app.appsflyer.com |
| Identificador único | ID do template | ativado |
| Estrutura da URL | `https://{subdomain}.onelink.me/``{templateid}?pid={media_source}``&af_siteid={ApplicationID}``&c={CampaignName}` | `https://app.appsflyer.com/{app_id}?pid={media_source}&af_siteid={ApplicationID}&c={CampaignName}` |
| Exemplo | `https://suamarca.onelink.me/aAB1?pid=greatnetwork_int``&c=GreatCampaign&af_siteid=A1b1` | `https://app.appsflyer.com/com.greatapp?pid=greatnetwork_int&``c=GreatCampaign&af_siteid=A1b1` |

<div id="important" />

> 🚧 **Importante!**
>
> A AppsFlyer oferece suporte apenas ao protocolo HTTPS para tráfego de engajamento de entrada, ou seja, cliques e impressões.

<div id="attribution-link-parameters" />

## Parâmetros do link de atribuição

* Os parâmetros listados estão disponíveis para uso no link de atribuição.
* A coluna **tipo de campo** indica o limite de caracteres do valor do parâmetro. Saiba mais sobre as limitações de comprimento dos valores dos parâmetros <Anchor target="_blank" href="/marketers/pt/docs/raw-data-field-dictionary">aqui.</Anchor>

<div id="attribution-link-parametersua-and-retargeting" />

### Parâmetros do link de atribuição – UA e retargeting

A tabela abaixo pode ser [baixada como](https://docs.google.com/spreadsheets/d/e/2PACX-1vTZQnoDdFo2NxBuWXBs5gGgvkGU2pr_hn58H9Dtf5uHBAHv4Io89Wd44rRtL24pRsOXHthnBitaOyfp/pub?gid=0&single=true&output=csv) [arquivo](https://docs.google.com/spreadsheets/d/e/2PACX-1vTZQnoDdFo2NxBuWXBs5gGgvkGU2pr_hn58H9Dtf5uHBAHv4Io89Wd44rRtL24pRsOXHthnBitaOyfp/pub?gid=0&single=true&output=csv) .

<div id="attribution-parameters" />

| Parâmetro | Nome de exibição nos dados brutos | Descrição | Tipo e comprimento do campo |
| --- | --- | --- | --- |
| <span id="pid"></span>pid | Media Source | Identifica exclusivamente um parceiro integrado da AppsFlyer. Não altere isso. [Mais detalhes](/docs/about-link-structure-and-parameters#partner-id-pid-parameter). | <span id="PID"></span>String 150 |
| <span id="c"></span>C | Campaign | Fornecido pelo anunciante ou pelo publisher. Consulte [os limites de nomes de campanha](/docs/about-link-structure-and-parameters#what-limits-are-there-on-campaign-names). | <span id="Campaign"></span>Sequência de caracteres |
| <span id="af_prt"></span>af\_prt | parceira | <ul><li>Nome de conta da agência - permite a atribuição de novas instalações à agência</li><li>**Atenção**: não use esse parâmetro antes de garantir que as **Permissões de Agência** estejam ativadas</li></ul> | Sequência de caracteres 50 |
| <span id="af_mp"></span>af\_mp | N/D | <ul><li>Ative o envio de postbacks para parceiros de marketing de publisher por instalação.</li><li>**Atenção:** Atualmente, esse parâmetro é relevante apenas para Pinterest Marketing Partners.</li></ul> |  |
| <span id="clickid"></span>clickid | N/D | Identificador de clique único da ad network |  |
| <span id="af_siteid"></span>af\_siteid | ID do site | <ul><li>ID exclusivo que identifica o publisher que exibe o anúncio. [Saiba mais](/docs/about-link-structure-and-parameters#site-id-parameter)</li></ul> | <span id="Site_id"></span>Sequência de caracteres 24 |
| <span id="af_sub_siteid"></span>af\_sub\_siteid | ID do subsite | <ul><li>Ad sub-network/Publisher ID.</li><li>Se, além do publisher principal (ID do site), houver um sub-publisher, ou você desejar incluir informações adicionais, como tipo de anúncio/posicionamento dentro do aplicativo, como banner, intersticial, vídeo etc, use af\_sub\_siteid. Exemplo: af\_sub\_siteid=ABCD\_4567</li></ul> | Sequência de caracteres |
| <span id="af_c_id"></span>af\_c\_id | ID da campanha | Fornecido pelo anunciante/publisher. | Sequência de caracteres 24 |
| <span id="af_adset"></span>af\_adset | Conjunto de anúncios | <ul><li>Fornecido pelo anunciante/publisher.</li><li>Adset é um nível intermediário na hierarquia entre Campanha e Anúncio. [Saiba mais](/docs/about-link-structure-and-parameters#níveis-de-granularidade-de-dados)</li></ul> | Sequência de caracteres 100 |
| <span id="af_adset_id"></span>af\_adset\_id | Adset ID | Fornecido pelo anunciante/publisher. | Sequência de caracteres 24 |
| <span id="af_ad"></span>af\_ad | As ad | Nome do anúncio ([saiba mais](/docs/about-link-structure-and-parameters#níveis-de-granularidade-de-dados)) fornecido pelo anunciante/publisher. | Sequência  100 |
| <span id="af_ad_id"></span>af\_ad\_id | ID do anúncio | Fornecido pelo anunciante/publisher. | Sequência de caracteres 24 |
| <span id="af_ad_type"></span>af\_ad\_type | Tipo de anúncio | Use as seguintes convenções de nomenclatura:<ul><li>**native**: Mídia paga desenvolvida para combinar com o conteúdo de uma fonte de mídia. Esse tipo de mídia é concebida para combinar com o design visual e a função de um conteúdo natural, aparecendo no seu feed de vídeos recomendados.</li><li>**banner**: Anúncios gráficos que normalmente são pequenos e retangulares, que aparecem em vários locais de uma página da web ou interface do aplicativo.</li><li>**interstitial**: Anúncios em tela cheia que cobrem toda a interface do aplicativo hospedeiro. Eles são colocados no meio do conteúdo e normalmente são exibidos em pontos de transição no fluxo do aplicativo, como entre atividades ou níveis de um jogo, ou durante uma pausa.</li><li>**rewarded\_video**: Anúncios que os usuários podem optar por visualizar até o final em troca de uma recompensa in-app – como assistir a um vídeo para ganhar uma vida extra, acessar um artigo ou usar o wi-fi de um aeroporto. Esses anúncios “premiados” engajam os usuários e oferecem uma melhor experiência geral no aplicativo.</li><li>**audio**: Anúncios em formato áudio apresentados em podcasts online ou em plataformas de streaming de música.</li><li>**offerwall**: Uma unidade de anúncio in-app usada pelos desenvolvedores para monetizar seus aplicativos. Ele funciona como uma mini-loja dentro do app, listando várias “ofertas” que os usuários podem completar em troca de uma recompensa no aplicativo.</li></ul> | Sequência de caracteres 24 |
| <span id="af_ad_format"></span>af\_ad\_format | Ad format | Use as seguintes convenções de nomenclatura:<ul><li>**text**: Um anúncio em texto que geralmente aparece como um snippet curto. Pode incluir um título, uma descrição e um link ou call-to-action. Seu objetivo é gerar interesse e incentivar um clique em um site ou landing page.</li><li>**image**: Um anúncio visual que apresenta um produto, serviço ou marca por meio de gráficos ou fotografias. Normalmente inclui uma imagem cativante junto com um texto conciso e também pode incorporar um call-to-action.</li><li>**video**: Um anúncio digital que utiliza conteúdo audiovisual para transmitir uma mensagem de marketing. Sua duração pode variar, podendo ser exibido como pre-roll, mid-roll e post-roll em conteúdos de vídeo online ou como vídeos independentes em diferentes plataformas.</li><li>**playable**: Um anúncio interativo que permite que os usuários se engajem com uma versão em miniatura de um jogo ou aplicativo antes do download ou de fazer uma compra. Ele oferece uma experiência prática do gameplay ou dos recursos do aplicativo.</li><li>**interactive**: Um anúncio atraente e dinâmico que incentiva os usuários a interagir ou a participar de uma ação. Pode incluir questionários, enquetes ou outros elementos interativos para captar a atenção dos usuários e incentivar a participação ativa.</li><li>**dynamic\_product**: Um formato de anúncio personalizado que preenche dinamicamente informações e detalhes do produto com base no comportamento, preferências ou histórico de navegação do usuário. Ele permite que os anunciantes mostrem anúncios de produtos altamente relevantes e personalizados.</li><li>**carousel**: Um formato de anúncio que consiste em vários slides ou cards em um único asset. Cada card pode incluir uma imagem, um título e uma descrição diferentes, permitindo que os anunciantes exibam vários produtos ou recursos em um único anúncio.</li></ul> |  |
| <span id="af_click_lookback"></span>af\_click\_lookback | Janela de lookback de atribuição | <ul><li>Janela de lookback para atribuição de clique. A duração da janela é o CTIT (tempo entre o clique e a instalação) máximo para que o novo usuário seja atribuído à fonte que exibe o anúncio/link.</li><li>Número de dias configurável do período de lookback para atribuição do clique. Valores dos parâmetros disponíveis: 1d - 30d (dias) OU 1h-23h (horas). O valor padrão é 7d.</li><li>A janela de lookback pode ser personalizada para <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows#configuração-da-janela-de-lookback">OneLinks e SRNs</Anchor>.</li></ul>**Atenção:** Afeta apenas URLs de clique, não URLs de impressão. | No máximo 3 caracteres |
| <span id="af_viewthrough_lookback"></span>af\_viewthrough\_lookback | N/D | <ul><li>Número de horas configurável para o período de atribuição por lookback view-through. Valores dos parâmetros disponíveis: 1h - 24h (horas). O valor padrão é 24h.</li><li>A janela de lookback pode ser personalizada para <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows#configuração-da-janela-de-lookback">SRNs</Anchor>.</li></ul>**Atenção:** Afeta apenas URLs de impressão, não URLs de clique | No máximo 3 caracteres |
| <span id="af_channel"></span>af\_canal | Canal | O canal da fonte de mídia através do qual os anúncios são distribuídos, por exemplo: UAC\_Search, UAC\_Display, Instagram, Meta Audience Network, etc. | Enumeração dinâmica. String 20 |
| <span id="af_engagement_destination"></span>af\_engagement\_destination | Destino de engajamento | Indica a categoria do destino vinculado a partir do anúncio, como uma página inicial da **web**, um aplicativo **mobile** (via deep link ou loja de aplicativos) ou outros tipos de destino, como **CTV**, **PC** ou **console**. | Sequência de caracteres 50 |
| <span id="af_keywords"></span>af\_keywords | Palavras-chave | Lista de palavras-chave para campanhas direcionadas por texto. | Sequência de caracteres 100 |
| <span id="af_cost_model"></span>af\_cost\_model | Modelo de custo | <ul><li>Modelo de custo - CPI (padrão) é atualmente o único modelo com suporte, que pode preencher <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#cost-data-availability-and-reports">o valor de custo em dados agregados da AppsFlyer</Anchor> nos relatórios.</li><li>Sempre que possível, reporte o custo por <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#cost-aggregation-methods">API.</Anchor> Nos casos em que o custo é reportado pelo link e pela API - a API tem prioridade.</li></ul> | String 20 |
| <span id="af_cost_currency"></span>af\_cost\_currency | Moeda do custo | <ul><li>Código de moeda de três letras de acordo com o <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#cost-aggregation-methods">ISO-4217.</Anchor> Por exemplo, USD, ZAR, EUR</li><li>[Padrão]: USD</li></ul> | Enum. 3 caracteres |
| <span id="af_cost_value"></span>af\_cost\_value | Valor de custo | <ul><li>Cost value in using cost currency.</li><li>Até 4 dígitos após o ponto decimal.</li><li>Configure APENAS dígitos numéricos (use um ponto decimal se necessário). Exemplo: "56", "2,85"</li></ul> | Numérico |
| <span id="af_sub-n-n15-example-af_sub1"></span>af\_sub[n]<br /><br />(n=1-5) exemplo: af\_sub1 | Sub param [n] | Parâmetro personalizado e opcional configurado pelo anunciante. Para obter mais informações sobre o uso desses parâmetros, consulte a seção [Características e limitações](/docs/about-link-structure-and-parameters#características-e-limitações). | Sequência de caracteres 100 |
| <span id="af_r"></span>af\_r | N/D | Usado para redirecionar usuários para a URL especificada em **todas as plataformas** (Android, iOS e desktop).<br /><br />Em links multiplataforma (OneLink), esse parâmetro:<ul><li>Substitui a configuração de redirecionamento a nível de template.</li><li>É substituído pelos seguintes parâmetros a nível de link:<ul><li>[`af_android_url`](/docs/about-link-structure-and-parameters#af_android_url)</li><li>[`af_ios_url`](/docs/about-link-structure-and-parameters#af_ios_url)</li><li>[`af_web_dp`](/docs/about-link-structure-and-parameters#af_web_dp)</li></ul></li></ul>**Atenção:** Veja as [características e limitações](/docs/about-link-structure-and-parameters#special-characters) adicionais do parâmetro de redirecionamento. |  |
| <span id="af_web_dp"></span>af\_web\_dp | N/D | URL para redirecionar usuários de desktop (por exemplo, Windows ou Mac) para uma página da web diferente da configurada no template do OneLink. Use-a para manter dados de atribuição de usuários de desktop em outras plataformas (por exemplo, Google Analytics ou Omniture)<br /><br />**Atenção:** Veja as [características e limitações](/docs/about-link-structure-and-parameters#special-characters) adicionais do parâmetro de redirecionamento. |  |
| <span id="af_dp"></span>af\_dp | N/D | O valor de fallback do esquema URI para iniciar o aplicativo, a ser usado se o método Universal Link ou Android App Link falham, e para usuários de Android de versões anteriores à 6.0. Ele só deve apontar para o <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">caminho base</Anchor>, ou seja, a atividade padrão.<br /><br />**Atenção:** Se você usar um valor de web URL para esse parâmetro (não recomendado), revise as [características e limitações](/docs/about-link-structure-and-parameters#special-characters) do parâmetro de redirecionamento. |  |
| <span id="af_force_deeplink"></span>af\_force\_deeplink | N/D | <Anchor target="_blank" href="/marketers/pt/docs/onelink-troubleshooting-and-faq">Force o deep linking</Anchor> na atividade especificada no valor af\_dp |  |
| <span id="af_ref"></span>af\_ref | N/D | As ad networks que trabalham com cliques S2S podem enviar um valor de referência único usando o seguinte parâmetro: &af\_ref=**ReferrerValue**<br /><br />O valor de af\_ref **deve** consistir em um único valor, estruturado da seguinte forma:<br /><br />**NetworkName\_UniqueClickValueForEachClick**<br /><br />Exemplo: af\_ref=nomedaadnetwork\_123456789ABCDEF<br /><br />O nome da ad network pode ser qualquer string válida. Pode ser nomeadnetwork ou simplesmente nome da ad network.<br /><br />A AppsFlyer pode usar este parâmetro para atribuição em dispositivos Android. A AppsFlyer não usa esse parâmetro para atribuição em dispositivos iOS ou Windows. |  |
| <span id="is_incentivized"></span>is\_incentivized | N/D | Booleano: true/false<br /><br />Campanhas incentivadas ou não incentivadas |  |
| <span id="af_param_forwarding"></span>af\_param\_forwarding | N/D | <ul><li>Quando configurados como falsos, os parâmetros que estão no link de atribuição não são encaminhados para a página redirecionada</li><li>Use isso para uma URL de aparência mais limpa na página redirecionada, ou caso os parâmetros de link de atribuição causem problemas devido ao tratamento de parâmetros de consulta na página redirecionada</li></ul> |  |
| <span id="af_base_params_forward"></span>af\_base\_params\_forward | N/D | <ul><li>Quando definidos como false, os parâmetros PID e C da AppsFlyer que estão no link de atribuição não são encaminhados para a página redirecionada.</li><li>Use isso se a URL receber um clique no desktop e você desejar que os parâmetros essenciais do CRM permaneçam, mas que os parâmetros PID e C da AppsFlyer sejam removidos. Isso evitará que você tenha vários PIDs na URL.</li></ul> |  |
| <span id="af_partner_account_id"></span>af\_partner\_account\_id | ID da conta da rede | ID da conta do anunciante com o parceiro | Sequência de caracteres 100 |
| <span id="af_redirect"></span>redirect | N/D | Quando `&redirect=false`, esse parâmetro permite que a AppsFlyer saiba que esse é um clique S2S e que o parceiro é responsável por redirecionar o usuário que clicou. |  |
| <span id="af_ua"></span>af\_ua | Agente de usuário | Relevante para ad networks que enviam cliques e impressões <Anchor target="_blank" href="/partners/pt/docs/redirecting-users-to-the-app-store">server-to-server (S2S)</Anchor>.<br /><br />**Importante:** Não use `af_ua` em links client-to-server (C2S). Usar `af_ua` em um link C2S pode afetar a atribuição.<br /><br />A string user-agent enviada como:<ol><li>Parâmetro da URL (codificado em URL)</li><li>Header de solicitação HTTP (não codificado)</li></ol>O User-Agent deve ser **idêntico no parâmetro de URL e no header HTTP**.<br /><br />**No Android**, o user-agent às vezes é reduzido a Client Hints. Deve ser enviado independentemente.<ul><li>**Exemplo de user-agent completo:** `Mozilla/5.0 (Linux; Android 12; Pixel 5) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/95.0.4638.16 Mobile Safari/537.36`</li><li>**Exemplo de user-agent reduzido:** `Mozilla/5.0 (Linux; Android 10; K) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/95.0.0.0 Mobile Safari/537.36`</li></ul>**No iOS**, a partir do iOS 26, a versão será anexada.<br />Veja abaixo:<ul><li>**Exemplo da parte anexada:** `Version/26.0.1 Mobile/15E148 Safari/604.1`</li><li>**Exemplo do user-agent completo:**<br />`Mozilla/5.0 (iPhone; CPU iPhone OS 16_4_1 like Mac OS X) AppleWebKit/8615.1.26.10.24 (KHTML, like Gecko) Mobile/20E252 Version/26.0.1 Mobile/15E148 Safari/604.1`</li></ul> |  |
| <span id="af_ip"></span>af\_ip | IP | Relevante para ad networks que enviam cliques e impressões <Anchor target="_blank" href="/partners/pt/docs/redirecting-users-to-the-app-store">de servidor para servidor</Anchor>.<br /><br />**Importante:** Não use `af_ip` em links client-to-server (C2S). Usar `af_ip` em um link C2S pode afetar a atribuição.<br /><br />**Endereço de IP do dispositivo**<br /><br />**Recomendado**: Se disponível, forneça o device IP no parâmetro `af_ip`.<br /><br />**Próxima opção**: se disponível, a AppsFlyer usará o IP em X-Forwarded-For. |  |
| <span id="deprecated--af_os"></span>[Descontinuado] af\_os | Versão do sistema operacional | [Somente para iOS] A versão do sistema operacional do dispositivo.<br /><br />Esse parâmetro está obsoleto, mas ainda é compatível com a AppsFlyer. Recomendação: em vez disso, use o parâmetro af\_os\_version. |  |
| <span id="af_os_version"></span>af\_os\_version | Versão do sistema operacional | <ul><li>Relevante para ad networks que enviam cliques e impressões <Anchor target="_blank" href="/partners/pt/docs/redirecting-users-to-the-app-store">de servidor para servidor</Anchor>.</li><li>A versão do sistema operacional do dispositivo.<ul><li>Android:<ul><li>Exemplo: 12</li><li>Para user-agent reduzido (devido a navegadores executados em desktop ou Android e usando o mecanismo Chrome 110+), a ad network deve usar a <Anchor target="_blank" href="https://web.dev/migrate-to-ua-ch/">API Client Hints</Anchor> para obter esse valor.</li><li>Para o user-agent que **não é** reduzido, use o seguinte regex para extrair a versão do sistema operacional Android da string do user-agent: `(\d+(?:\.\d+)*);(?:\s..-..;)?\s(.+?(?=\)\|\s\w*\/))`.</li></ul></li><li>iOS:<ul><li>Inclua a versão completa do SO para garantir uma atribuição precisa. Exemplo: 16.2</li></ul></li></ul></li></ul> |  |
| <span id="af_model"></span>af\_model | Modelo do dispositivo | <ul><li>Relevante para ad networks que enviam cliques e impressões <Anchor target="_blank" href="/partners/pt/docs/redirecting-users-to-the-app-store">de servidor para servidor</Anchor>.</li><li>O modelo do dispositivo.<ul><li>Android:<ul><li>Exemplo: Pixel 5</li><li>Para user-agent reduzido (devido a navegadores executados em desktop ou Android e usando o mecanismo Chrome 110+), a ad network deve usar a <Anchor target="_blank" href="https://web.dev/migrate-to-ua-ch/">API Client Hints</Anchor> para obter esse valor.</li><li>Para o user-agent que **não é** reduzido, use o seguinte regex para extrair o modelo Android da string do user-agent: `(\d+(?:\.\d+)*);(?:\s..-..;)?\s(.+?(?=\)\|\s\w*\/))`.</li></ul></li><li>iOS:<ul><li>Inclua o identificador completo do modelo de dispositivo para garantir uma atribuição precisa. Por exemplo `iphone15,1` ou `ipad14,2`.</li></ul></li></ul></li></ul> |  |
| <span id="af_media_type"></span>af\_media\_type | Tipo de mídia | Posição do anúncio que transporta o link da seguinte forma:<ul><li>app: o link está disponível através de um aplicativo</li><li>web: o link está disponível em um site mobile</li></ul> |  |
| <span id="deep_link_sub110"></span>deep\_link\_sub1-10 | N/D | Valores adicionais de deep link. Os desenvolvedores implementam o comportamento desejado dos valores no código. |  |
| <span id="deep_link_value"></span>deep\_link\_value | N/D | A nomenclatura para o conteúdo específico em formato de arquivo que será direcionado aos usuários. Os desenvolvedores implementam o comportamento desejado do deep\_link\_value no código. |  |
| <span id="af_og_title"></span>af\_og\_title | N/D | Quando um link é postado nas redes sociais, o título Open Graph (OG) irá gerar uma pré-visualização do título. | Sequência 40 |
| <span id="af_og_description"></span>af\_og\_description | N/D | Quando um link é postado nas redes sociais, o título Open Graph (OG) irá gerar uma pré-visualização da descrição. | Sequência 300 |
| <span id="af_og_image"></span>af\_og\_image | N/D | Quando um link é postado nas redes sociais, o título Open Graph (OG) irá gerar uma pré-visualização da imagem. |  |

<div id="attribution-link-parametersretargeting-only" />

### Parâmetros do link de atribuição — apenas para retargeting

| Parâmetro | Nome de exibição nos dados brutos | Descrição | Tipo e comprimento do campo |
| --- | --- | --- | --- |
| <span id="is_retargeting"></span>is\_retargeting | Is Retargeting (campaign) | A URL de clique de cada campanha de redirecionamento deve incluir `&is_retargeting=true`.  <br />Se o parâmetro não for incluído ou se seu valor for "false", a campanha é considerada uma campanha normal de aquisição de usuários. | Enumeração 5 caracteres |
| <span id="af_reengagement_window"></span>{"af_reengagement"} {"_window"} | Janela de reengajamento | Altere a <Anchor target="_blank" href="/marketers/pt/docs/retargeting-attribution-guide#reengagement-rules-and-windows">janela de atribuição de reengajamento</Anchor> adicionando esse parâmetro ao link de atribuição.<br /><br />As possíveis opções de intervalo de janelas são:<ul><li>Dias: 1-90 ou Horas 1-36</li><li>Duração: significa que a janela de reengajamento é ilimitada. Exemplo:`&af_reengagement_window=lifetime`</li></ul>Valor padrão: 30 dias<br /><br />Exemplo:`&af_reengagement_window=30d` define a janela de reengajamento para 30 dias. | N/D |

<div id="viewability-parameters" />

### Parâmetros de visibilidade

Dependendo do tipo de anúncio, você também pode enviar o parâmetro de visibilidade relevante detalhando as especificações do engajamento.

| Parâmetro | Formato do valor | Descrição |
| --- | --- | --- |
| <span id="af_video_total_length"></span>af\_video\_total\_length | segundos | A duração total possível do vídeo |
| <span id="af_video_played_length"></span>af\_video\_played\_length | segundos | Quanto do vídeo foi visualizado |
| <span id="af_playable_played_length"></span>af\_playable\_played\_length | segundos | Por quanto tempo o elemento jogável foi jogado uma vez totalmente carregado |
| <span id="af_ad_time_viewed"></span>af\_ad\_time\_viewed | segundos | Por quanto tempo a unidade de anúncio estava visível na tela |
| <span id="af_ad_displayed_percent"></span>af\_ad\_displayed\_percent | % | A porcentagem máxima da unidade de anúncios que estava visível na tela do dispositivo |
| <span id="af_audio_total_length"></span>af\_audio\_total\_length | segundos | A duração total possível do áudio |
| <span id="af_audio_played_length"></span>af\_audio\_played\_length | segundos | Quanto do áudio foi ouvido |

<div id="android-specific-parameters" />

### Parâmetros específicos para Android

| Parâmetro | Nome de exibição nos dados brutos | Descrição | Tipo de campo |
| --- | --- | --- | --- |
| <span id="advertising_id"></span>advertising\_id | ID de publicidade | Google Advertising ID – requer suporte da ad network | Máximo de 40 caracteres |
| <span id="sha1_advertising_id"></span>sha1\_publicidade\_id | N/D | Google Advertising ID anonimizado com SHA1 - requer suporte da ad network |  |
| <span id="md5_advertising_id"></span>md5\_advertising\_id | N/D | Google Advertising ID anonimizado com MD5 - requer suporte da ad network | Compatível apenas com instalações e reatribuições |
| <span id="android_id"></span>android\_id | ID Android | Device Android\_id - requer suporte da ad network | Máximo de 20 caracteres |
| <span id="sha1_android_id"></span>sha1\_android\_id | N/D | Device Android\_id anonimizado com SHA1 - requer suporte da ad network |  |
| <span id="md5_android_id"></span>md5\_android\_id | N/D | Device Android\_id anonimizado com MD5 - requer suporte da ad network | Compatível apenas com instalações e reatribuições |
| <span id="imei"></span>imei | IMEI | Device IMEI ID |  |
| <span id="sha1_imei"></span>sha1\_imei | N/D | Device IMEI ID anonimizado com SHA1 - requer suporte da ad network |  |
| <span id="md5_imei"></span>md5\_imei | N/D | Device IMEI ID anonimizado com MD5 - requer suporte da ad network |  |
| <span id="oaid"></span>OAID | OAID | Identificador de Dispositivo Anônimo Aberto | Disponível a partir da versão 4.10.3 do Android SDK |
| <span id="sha1_oaid"></span>sha1\_oaid | N/D | Open Anonymous Device Identifier anonimizado com SHA1 - requer suporte da ad network | Disponível a partir da versão 4.10.3 do Android SDK |
| <span id="md5_oaid"></span>md5\_oaid | N/D | Open Anonymous Device Identifier anonimizado com MD5 - requer suporte da ad network | Disponível a partir da versão 4.10.3 do Android SDK |
| <span id="af_android_url"></span>af\_android\_url | N/D | Redirecione os usuários do Android para uma URL diferente da página do aplicativo no Google Play. Use para <Anchor target="_blank" href="/marketers/pt/docs/set-up-multi-store-android-attribution#dashboard-único-vs-dashboard-por-loja">lojas externas</Anchor>.<br /><br />**Atenção:** Veja as [características e limitações](/docs/about-link-structure-and-parameters#special-characters) adicionais do parâmetro de redirecionamento. |  |
| <span id="sha1_el"></span>sha1\_el | N/D | Usado para atribuição de desktop para mobile — e-mail anonimizado com SHA1. Requer suporte da ad network |  |
| <span id="fire_advertising_id"></span>fire\_advertising\_id | N/D | Amazon Fire Advertising ID |  |
| <span id="af_android_store_csl"></span>af\_android\_store\_csl | store\_product\_page | Listagem personalizada no Google Console | string |

<div id="ios-specific-parameters" />

### Parâmetros específicos do iOS

| Parâmetros | Nome de exibição | Descrição |
| --- | --- | --- |
| <span id="idfa"></span>idfa | IDFA | Use letras maiúsculas. Requer suporte da ad network<br /><br />Tipo de campo: Máximo de 40 caracteres |
| <span id="idfv"></span>idfv | IDFV | Use letras maiúsculas. |
| <span id="af_ios_url"></span>af\_ios\_url |  | Use-o para redirecionamentos de landing page, redirecionando usuários do iOS (iPhone or iPad) para uma URL diferente da página do aplicativo no iTunes<br /><br />**Atenção:** Veja as [características e limitações](/docs/about-link-structure-and-parameters#special-characters) adicionais do parâmetro de redirecionamento. |
| <span id="af_ios_store_cpp"></span>af\_ios\_store\_cpp | store\_product\_page | ID da página do produto personalizada (ppid)<br /><br />**Atenção:** Em dados brutos e relatórios agregados, o valor do parâmetro af\_ios\_store\_cpp (Custom product page ID) é registrado para cliques, mas não para impressões. |
| <span id="af_ios_fallback--deprecated"></span>af\_ios\_fallback [desativado] | N/D | **Descontinuado**: os usuários são redirecionados com base no <Anchor target="_blank" href="/marketers/pt/docs/uri-scheme-fallback-for-ios">fluxo do esquema URI do iOS</Anchor>. |
| <span id="sha1_idfa"></span>sha1\_idfa | N/D | IDFA anonimizado com SHA1. Requer suporte da ad network |
| <span id="sha1_idfv"></span>sha1\_idfv | N/D | IDFV anonimizado com SHA1. |
| <span id="mac"></span>mac | N/D | Endereço MAC do dispositivo. Requer suporte da ad network |
| <span id="md5_idfa"></span>md5\_idfa | N/D | IDFA anonimizado com MD5. |
| <span id="md5_idfv"></span>md5\_idfv | N/D | IDFV anonimizado com MD5. |
| <span id="sha1_mac"></span>sha1\_mac | N/D | Endereço MAC do dispositivo anonimizado com SHA1. Requer suporte da ad network |

<div id="example" />

> 📄 **Exemplo**
>
> ```http
> https://app.appsflyer.com/{app_id}/?pid=airpush_int&c=RedBanner&
> 	  af_siteid={publisher_id}&af_sub1=1.5&af_sub2=USD&af_sub3=burst_campaign
> ```

Todos os parâmetros estão disponíveis no <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview">relatório de instalação</Anchor> e nas <Anchor target="_blank" href="/marketers/pt/docs/analytics-and-aggregate-reporting-apis">análises, relatórios e APIs</Anchor>.

<div id="custom-parameters" />

### Parâmetros personalizados

Além dos parâmetros padrão específicos do Android e iOS, você também pode especificar parâmetros personalizados. Esses parâmetros personalizados podem ser úteis se você desejar personalizar a experiência e o conteúdo do usuário de acordo com o link de atribuição que leva à instalação.

Você pode adicionar qualquer outro parâmetro personalizado ao link de atribuição no formato `parameter=value`. Por exemplo:

```http
https://app.appsflyer.com/com.greatapp?pid=networkx_int&c=winter&af_adset=coats&af_ad=cashmere&my_custom_param=my_custom_value
```

Duas coisas importantes que você deve saber sobre parâmetros personalizados:

* Os parâmetros personalizados não aparecem nos dados brutos.
* Parâmetros personalizados podem ser recuperados da <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/conversion-data">get conversion data SDK API</Anchor>.

<div id="partner-id-pid-parameter" />

<Accordion title="Parâmetro Partner ID (PID)">

Entre todos os parâmetros do link de atribuição disponíveis, o PID é obrigatório. O PID é o identificador exclusivo definido pela AppsFlyer para a fonte de mídia.

Cada <Anchor target="_blank" href="http://appsflyer.com/partners">parceiro integrado</Anchor> tem um PID único, que termina com o sufixo *\_int* . Ao usar <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">links do OneLink</Anchor>, você pode definir o PID para qualquer valor que desejar, desde que não seja reservado por um parceiro integrado.

<div id="note" />

> 📘 **Nota**
>
> A AppsFlyer bloqueia links de atribuição que usam nomes de <Anchor target="_blank" href="/marketers/pt/docs/self-reporting-networks-srns#srns-integradas-à-appsflyer">SRN</Anchor> reservados como valores de PID em fontes de mídia personalizadas (exemplo: e-mail e SMS). Essa restrição **não** se aplica a ASRNs.

Exemplos de importantes IDs de publishers integrados reservados: organic, googleadwords\_int (Google AdWords), facebook\_int (Meta ads), e twitter\_int (X Ads). Você pode usar qualquer nome para fontes não-integradas, como e-mail, SMS ou canais alternativos.

<div id="avoid-common-pid-issues" />

#### Evite problemas comuns de PID:

* **Sempre inclua o PID nos seus links de atribuição.** Sem o PID no link de atribuição, os usuários são automaticamente atribuídos a uma fonte de mídia "None" (Nenhuma) e a fonte de instalação original desaparece.
* **Para cada fonte integrada**, use somente o PID designado para a atribuição correta das suas instalações.
* **Para fontes personalizadas, use PIDs de parceiros não integrados.** Para qualquer fonte de mídia personalizada, como e-mail, SMS ou até mesmo publicações não pagas virais no Facebook, use outros valores de PID não-integrados, como owned\_email, sms\_push ou outros identificadores personalizados que não correspondem aos nomes dos parceiros integrados. como owned\_email, sms\_push ou outros identificadores personalizados que não correspondem aos nomes dos parceiros integrados.
* **Use apenas caracteres permitidos.** Se o parâmetro PID no link de atribuição contiver um dos seguintes caracteres /&lt;>*&?\
  * O clique ou a instalação aparece no dashboard em ***af\_invalid\_param***
  * Os links de atribuição não serão reconhecidos
  * As funcionalidades de deep linking não funcionarão com cliques

<div id="tip" />

> 👍 **Dica**
>
> Evite usar espaços em branco no valor do PID ou certifique-se de que a URL codifique seus links de atribuição antes de usá-los.

</Accordion>

<div id="site-id-parameter" />

<Accordion title="Parâmetro do Site ID">

O ID do site é o identificador exclusivo do publisher que veicula por meio de anúncio. Em outras palavras, o site ou aplicativo que exibe o anúncio. Ad networks alocam IDs de site exclusivos para cada publisher.

Este ID está incluído no parâmetro `af_siteid` enviado para a AppsFlyer no link de atribuição e é disponibilizado por meio de vários dashboards, relatórios e postbacks.

O ID do site deve ser enviado para a AppsFlyer no link de atribuição, pois ele:

* Proporciona clareza e transparência sobre o publisher.
* É usado pela AppsFlyer para identificar e eliminar publishers fraudulentos e outros clusters de tráfego.

O parâmetro ID do site inclui apenas o ID do publisher que exibe o anúncio.

Para incluir informações adicionais, como o tipo de anúncio e sua posição dentro do app, como em um banner, intersticial ou vídeo, use o parâmetro de ID do subsite.

<div id="example-1" />

> 📄 **Exemplo**
>
> O seguinte link de atribuição inclui:
>
> * `af_siteid` (ID do site): ID do publisher
> * `af_sub_siteid` (sub-site ID): Adicional Informação adicional de ID (nesse caso, uma fonte afiliada e a posição de acordo com o tipo de anúncio)
>
> `https://app.appsflyer.com/com.yourapp?pid=mediaName_int&clickid={clickid}&advertising_id={gaid}&af_siteid=1234&af_sub_siteid=ABCD_4567`
>
> No exemplo do link:
>
> * 1234 = ID do publisher
> * ABCD = Fonte afiliada (sub-publisher) com a qual o publisher está trabalhando
> * 4567 = posição de acordo com o tipo de anúncio no app (banner, intersticial ou vídeo)

<div id="faq-why-does-traffic-result-in-many-blocked-installs" />

#### **FAQ: por que o tráfego apresenta muitas instalações bloqueadas?**

Isso ocorre por alguns motivos:

* **Site ID em falta:** O parâmetro `af_siteid` está vazio na URL de clique. Os engajamentos enviados com um ID de site vazio implicam um problema técnico ou uma tentativa intencional de ignorar mecanismos de detecção de fraudes.
* **Múltiplos site IDs:** O mesmo publisher é enviado em várias URLs de clique, usando diferentes IDs de site. Isso é considerado  um comportamento fraudulento que mascara a atividade real do publisher e frequentemente está associado à prática de <Anchor target="_blank" href="https://www.appsflyer.com/pt/blog/mobile-fraud/click-flooding-detection-false-positive-challenge/">flooding de cliques</Anchor>.
* **Site ID mal formatado:** Enviar o formato errado, combinado com outras indicações de fraude, pode resultar no bloqueio não apenas do publisher em questão, mas também de um nível de cluster mais alto, que pode afetar maiores volumes da atividade do parceiro.

Para evitar instalações bloqueadas, certifique-se de enviar um único parâmetro ID do site por publisher, como mostramos no exemplo.

</Accordion>

<div id="levels-of-data-granularity" />

## Níveis de granularidade de dados

Você pode usar até quatro parâmetros de URL para analisar os detalhes da performance dos seus anúncios.

Usar todos os quatro parâmetros em todos os seus links de atribuição ativos permite que você:

* Atribuir todas as instalações de utilizadores e eventos a anúncios específicos
* Analise e compare a performance de todos os seus anúncios por conjunto de anúncios (adset), por campanha e por fonte de mídia em relatórios agregados para otimização em todos os níveis
* Compare todos os seus anúncios em todas as fontes de mídia no <Anchor target="_blank" href="/marketers/pt/docs/pivot-table-user-metrics">Pivot Table</Anchor> e em relatórios de dados brutos

Os parâmetros são:

* `Fonte de mídia (pid=)`
* `nome da campanha (c=)`
* `Conjunto de anúncios (af_adset=)`
* `Nome do anúncio (af_ad=)`

<div id="example-2" />

> 📄 **Exemplo**
>
> O seguinte link de atribuição usa quatro níveis de granularidade para registrar o anúncio de "cashmere" no conjunto de anúncios de "coats" na campanha "winter", que é executada na fonte de mídia integrada "network".
>
> ```http
> https://app.appsflyer.com/com.greatapp?pid=networkx_int&c=winter&
> af_adset=coats&af_ad=cashmere
> ```

<div id="frequently-asked-questions" />

## Perguntas frequentes

<div id="should-i-use-lower-or-upper-case-letters-for-parameters" />

<Accordion title="Devo usar letras minúsculas ou maiúsculas nos parâmetros?">

Você pode usar tanto letras minúsculas quanto maiúsculas, mas é preciso ser consistente. Se você definir um parâmetro personalizado com caracteres maiúsculos ou minúsculos, use sempre esse parâmetro.

Por exemplo, se você definir pid=MyMediaSource, certifique-se de sempre usá-lo dessa forma. Se você usar pid=MyMediaSource em um link de atribuição e pid=mymediasource em outro, podem ocorrer discrepâncias nos dados. O mesmo vale para quaisquer outros parâmetros que você definiu no link de atribuição.

</Accordion>

<div id="is-the-appsflyer-attribution-link-dynamic-or-static" />

<Accordion title="O link de atribuição da AppsFlyer é dinâmico ou estático?">

Os links de atribuição podem ser dinâmicos ou estáticos.  
Como pode saber se um link é dinâmico ou estático?  
Se o **link de atribuição tiver parâmetros**, ele é um link de atribuição longo e predefinido e, portanto, é **estático**.  
**Somente URLs curtas** (por exemplo`yourbrand.onelink.me/HaT8/r5c2b371`), usadas para links de atribuição personalizados, **são dinâmicas**.  
Isso significa que, uma vez que você começa a usar um link de atribuição para um parceiro integrado ou uma URL longa para mídias próprias, ela não se altera para nenhum lead que se engaje com ela, mesmo que você altere os valores do link de atribuição no dashboard da AppsFlyer. Para que a alteração ocorra, você deve usar a nova URL longa a partir de então.  
Por outro lado, URLs curtas para mídias próprias não contêm parâmetros diretamente. Quando um lead se engaja com uma URL curta da AppsFlyer, ele é redirecionado para a AppsFlyer e os parâmetros definidos atualmente ocorrem dinamicamente.

</Accordion>

<div id="what-is-this-play-store-error-message" />

<Accordion title="O que é essa mensagem de erro da Play Store?">

Se alguma vez encontrar a seguinte mensagem de erro na Play Store depois de seguir um link de atribuição:

![TL_error_message.png](https://files.readme.io/03e509d3cbe68aa0621bb0f43ab113c25a8427e70826c5af5258f1fc9e3f3d36-360000002485.png)

Isso ocorre porque o link de atribuição inclui um caractere #. Por exemplo:

```http
https://app.appsflyer.com/com.travelco?pid=globalwide_int&clickid=#reqid#
```

Geralmente, esses caracteres estão no link porque são macros e são substituídos dinamicamente por um valor, então esse não é um problema significativo e você pode ignorar a mensagem.

</Accordion>

<div id="what-are-subscriber-parameters-good-for" />

<Accordion title="Para que servem os parâmetros de assinante?">

Os parâmetros do assinante, ou seja, af\_sub1, af\_sub2, ..., af\_sub\_5 podem ser usados para registrar quaisquer KPIs úteis. Esses parâmetros são analisados e aparecem no relatório de dados brutos, o que os torna muito úteis para realizar a agregação e filtragem de dados.

<div id="example-3" />

> 📄 **Exemplo**
>
> O Luber, um aplicativo hail ride, tem criativos com modelos de três cores: azul, amarelo e vermelho. A responsável por marketing mobile do Luber, Linda, quer testar qual modelo de cor traz mais instalações. Para isso, ela acrescenta `&af_sub3=blue` nos links de atribuição de todos os anúncios azuis em TODAS as fontes de mídia não SRN. O mesmo processo é realizado para os anúncios amarelos e vermelhos. Com essa informação analisada e exibida nos relatórios de dados brutos, Linda é capaz de avaliar o sucesso dos anúncios de cores diferentes e escolher aquele que mais gera conversões de usuários.

</Accordion>

<div id="what-limits-are-there-on-campaign-names" />

<Accordion title="Quais são os limites para os nomes das campanhas?">

* O tamanho máximo de um nome de campanha na URL do link de atribuição é limitado a 100 caracteres. Se esse limite for excedido, o nome da campanha é alterado para: `c_name_exceeded_max_length`
* O nome da campanha não deve começar nem terminar com um espaço em branco, pois isso pode causar discrepâncias nos dashboards e relatórios.

</Accordion>

<div id="traits-and-limitations" />

## Características e limitações

| Características | Observações |
| --- | --- |
| <span id="special-characters"></span>Caracteres especiais | Os seguintes caracteres especiais não são permitidos nas chaves e nos valores de parâmetros (não aplicáveis aos parâmetros de redirect e af\_dp): ;, *, !, @, #, ?, $, ^, :, &, ~, \`, =, +, ’, >, &lt;, /, \{, \}, %, ),( |
| <span id="redirection-parameters"></span>Parâmetros de redirecionamento | <ul><li>Certifique-se de que seus domínios de URL de redirecionamento sejam adicionados à sua <Anchor target="_blank" href="/marketers/pt/docs/set-up-your-domain-redirect-allowlist">redirect allowlist</Anchor>.</li><li>O valor do redirecionamento deve ser uma URL web completa (https://[domain][optional-path]) em conformidade com os <Anchor target="_blank" href="https://datatracker.ietf.org/doc/html/rfc1738">padrões RFC 1738</Anchor>;</li><li><Anchor target="_blank" href="https://en.wikipedia.org/wiki/URI_fragment">Os identificadores de fragmentos de URI</Anchor> **não são compatíveis** com URLs de redirecionamento (por exemplo, #webpagesection que leva os usuários até uma seção específica em um artigo).</li></ul> |
| <span id="url-characteravailable"></span>Limite de caracteres da URL | O comprimento total da URL não pode exceder 2.000 caracteres. |
| <span id="agencies"></span>Redirecionamento de deep link em WebView de aplicativos sociais do Android | Veja os detalhes das limitações <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#android-social-apps-webview-deep-linking-redirection">aqui</Anchor> |
| <span id="deep-linking-is-not-supported-in-the-android-naver-blog-app"></span>O deep linking não é compatível com o aplicativo Android Naver Blog. | O deep linking não é compatível com o aplicativo Android Naver Blog. Os usuários serão redirecionados para a Google Play Store ou para a web, conforme definido pelo link. |
| <span id="a-popup-appears-when-clicking-on-a-uri-scheme-link-from-chrome-browser-on-ios"></span>Um pop-up aparece ao clicar em um link de esquema URI no navegador Chrome no iOS | Devido a uma alteração no Chrome, sempre que um usuário clica em um link de esquema URI no Chrome no iOS, um pop-up é exibido, solicitando que o usuário confirme a abertura do app ou o redirecionamento para a App Store. |
| <span id="uri-scheme-validity-requirements"></span>Requisitos de validade para esquemas URI | Recomendamos o uso de um esquema URI válido que cumpra com as normas da <Anchor target="_blank" href="https://www.rfc-editor.org/rfc/rfc3986#section-3.1">RFC 3986</Anchor>. Os esquemas que não cumprem com os requisitos acima podem não abrir o app e gerar um erro quando recebem um clique na Web ou em outros ambientes Web. |
| <span id="telegram-webview-attribution"></span>Atribuição de WebView do Telegram | Veja os detalhes das limitações <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#telegram-webview">aqui</Anchor> |

<div data-zendesk-anchors="overview=vis%C3%A3o-geral 01H8GN1XXC5T2ENFHBK0G4WQ1P=vis%C3%A3o-geral 01JENAANV4KTRF882JMEM5N91A=importante attribution-link-parameters=par%C3%A2metros-do-link-de-atribui%C3%A7%C3%A3o 01H8GN1XXDX1XMQ1GJTHCP425D=par%C3%A2metros-do-link-de-atribui%C3%A7%C3%A3o attribution-link-parameters%E2%80%94ua-and-retargeting=par%C3%A2metros-do-link-de-atribui%C3%A7%C3%A3o--ua-e-retargeting 01H8GN1XXDEWPB2MPP3KJVPRJV=par%C3%A2metros-do-link-de-atribui%C3%A7%C3%A3o--ua-e-retargeting af_sub%5Bn%5D%C2%A0%0An15-example-af_sub1=af_sub-n-n15-example-af_sub1 %5Bdeprecated%5D-af_os=deprecated--af_os attribution-link-parameters%E2%80%94retargeting-only=par%C3%A2metros-do-link-de-atribui%C3%A7%C3%A3o--apenas-para-retargeting 01H8GN1XXD9X7CWZJN43PSS94R=par%C3%A2metros-do-link-de-atribui%C3%A7%C3%A3o--apenas-para-retargeting viewability-parameters=par%C3%A2metros-de-visibilidade 01H8GN1XXETQEYT39F05ZYX4E2=par%C3%A2metros-de-visibilidade androidspecific-parameters=par%C3%A2metros-espec%C3%ADficos-para-android 01H8GN1XXEE9RGSB1H72H025Z4=par%C3%A2metros-espec%C3%ADficos-para-android iosspecific-parameters=par%C3%A2metros-espec%C3%ADficos-do-ios 01H8GN1XXESJ9VE3W8CYKRFFYX=par%C3%A2metros-espec%C3%ADficos-do-ios af_ios_fallback-%5Bdeprecated%5D=af_ios_fallback--deprecated 01H8GN1XXEFRSQSERTB6ARC773=exemplo custom-parameters=par%C3%A2metros-personalizados 01H8GN1XXEB58JN4SV9HX1ZV6S=par%C3%A2metros-personalizados 01H8GN1XXE8EXMMKDZMJ2WNNH5=partner-id-pid-parameter h_01JRX48BX8W9V9XWPB1DSG4H8Y=nota avoid-common-pid-issues=evite-problemas-comuns-de-pid 01H8GN1XXEXTGC4M8AMJ256Q9G=evite-problemas-comuns-de-pid 01H8GN1XXEGNVX9GM5JYBMBGCF=dica 01H8GN1XXEVG65YP782CM37RES=site-id-parameter 01H8GN1XXED2MVSNRXN11KZ955=exemplo-1 faq-why-does-traffic-result-in-many-blocked-installs=faq-por-que-o-tr%C3%A1fego-apresenta-muitas-instala%C3%A7%C3%B5es-bloqueadas 01H8GN1XXEK0G9TDW8WHWM17HK=faq-por-que-o-tr%C3%A1fego-apresenta-muitas-instala%C3%A7%C3%B5es-bloqueadas levels-of-data-granularity=n%C3%ADveis-de-granularidade-de-dados 01H8GN1XXE4RF9J0APAAKD1WEG=n%C3%ADveis-de-granularidade-de-dados 01H8GN1XXEHPFKX7V0RRW2MH2G=exemplo-2 frequently-asked-questions=perguntas-frequentes h_01HN0JW166VHR33T8VVVY47F9P=perguntas-frequentes 01H8GN1XXEND9X8YVRQE1YFA5W=should-i-use-lower-or-upper-case-letters-for-parameters 01H8GN1XXER749PH4Z14A7AJ0F=is-the-appsflyer-attribution-link-dynamic-or-static 01H8GN1XXEPQTY0XNW6EZSA9ZN=what-is-this-play-store-error-message 01H8GN1XXFYAFYFX9MNBP6D35B=what-are-subscriber-parameters-good-for 01H8GN1XXFEFA498J22GRF5F8G=exemplo-3 01H8GN1XXFS1DFS3HAHVTVG93A=what-limits-are-there-on-campaign-names traits-and-limitations=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01HN0JW166WH76A5SM293PGKX6=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es" />
