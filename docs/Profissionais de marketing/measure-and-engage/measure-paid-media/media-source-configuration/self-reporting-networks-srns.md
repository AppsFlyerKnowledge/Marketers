---
title: Networks de autorrelato (SRNs)
metadata:
  keywords:
    - Facebook
    - Advertisers
    - Agencies
    - Ad Networks
    - srn
    - Self-reporting
    - networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2018-10-22T05:21:45Z'
  edited_at: '2026-08-18T00:30:38Z'
  id: 360001546905
  locale: pt
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/pt/articles/360001546905
---
> **Resumo:** saiba mais sobre redes de autorrelato (SRNs)—atribuição, deep linking, implicações do iOS e FAQ.

## SRNs integradas à AppsFlyer

| **SRN** | **Logo** |
| --- | --- |
| <Anchor target="_blank" href="/marketers/pt/docs/amazon-ads-campaign-configuration">Anúncios da Amazon</Anchor> | <Image alt="amazon-ads-logo.png" src="https://files.readme.io/0a4c9078bd683c51bad40408c894f6e2b7314d7c369bd46ac90c3e622f62f0a7-11927906589329.png" width="134px" /> |
| <Anchor target="_blank" href="/marketers/pt/docs/apple-ads-integration-setup">Apple Search Ads</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/iossearchads.png" width="131px" /> |
| <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-integration-setup-for-advertisers">Google Ads</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/googleadwords.png?v=1" width="47px" /> |
| <Anchor target="_blank" href="/marketers/pt/docs/google-marketing-platform-display-video-360-dv360-integration">Google Marketing Platform</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/doubleclick.png?v=1" width="45px" /> |
| <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-integration-setup">Anúncios Meta</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/facebook.png?v=1" width="67px" /> |
| <Anchor target="_blank" href="/marketers/pt/docs/roku-integration-with-appsflyer">Roku</Anchor> | <Image alt="roku.png" src="https://files.readme.io/4909a45e611700e5c2a69f94710226e65e10faf620e3a7939a2c038bea1736ca-33565070184337.png" width="150px" /> |
| <Anchor target="_blank" href="/marketers/pt/docs/snapchat-advanced-srn-integration-setup">Snapchat — SRN Avançada</Anchor> | <Image alt="snapchat_logo.png" src="https://files.readme.io/c9b62d55d5c1497011d7411a21dca6f1668308bbe2806ab238b71742c421b182-32259457816209.png" width="41px" /> |
| Tencent Social Ads | <Image alt="blobid0.jpg" src="https://files.readme.io/6d6e9661c9d81f80ffeedfdf4850a84f3cc183faa49a514d1d3bb116641738da-32259428896017.jpg" width="80px" /> |
| <Anchor target="_blank" href="/marketers/pt/docs/tiktok-for-business-advanced-srn-integration-setup">TikTok for Business—SRN Avançada</Anchor> | ![TTFB_logo__4C_horizontal_black.png](https://files.readme.io/caa8c9e02b161eea10740cb79f26d04d3324e87b9cfd929281374d2d7936ef2e-32259428903953.png) |
| <Anchor target="_blank" href="/marketers/pt/docs/x-ads-formerly-twitter-ads-setup-guide-overview">AppsFlyer</Anchor> | <Image alt="X Ads logo.png" src="https://files.readme.io/cecae90650321943ad1cb6d22b7f27d3d28b0484f1706cb1be1a19099dfbb20d-20375448207377.png" width="37px" /> |
| <Anchor target="_blank" href="/marketers/pt/docs/yahoo-integration-setup">Yahoo (Oath: Plataformas de anúncios / Yahoo Gemini)</Anchor> | <Image alt="verizonmedia.png" src="https://files.readme.io/36291ff556d07a5dbf2ae8ff693ea33d21dae9e0518a94b251202634a24049cf-32259428916369.png" width="76px" /> |
| <Anchor target="_blank" href="/marketers/pt/docs/yahoo-japan-search-ads-campaign-configuration">Yahoo! Anúncios de Pesquisa</Anchor> | <Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/yahoojapansearch.png" width="139px" /> |

**Atenção:** As SRNs têm <Anchor target="_blank" href="/marketers/pt/docs/user-level-data-retention">restrições de uso e retenção de dados a nível de usuário.</Anchor>

## Atribuição

Ao contrário de não-SRNs (ad networks), que usam links de atribuição para relatar eventos à AppsFlyer, os SRNs se autoatribuem usando o ID do dispositivo quando notificados de uma instalação pela AppsFlyer. Para aplicativos no iOS, a <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide">SKAN</Anchor> e o <Anchor target="_blank" href="/marketers/pt/docs/apply-aggregated-advanced-privacy-framework">framework de Privacidade Avançada Agregada</Anchor> são usados para atribuição.

A atribuição da AppsFlyer para SRNs e não SRNs é baseada em:

* Metodologias último toque e multitoque.
* Lógica de atribuição padrão da AppsFlyer para sequenciar a impressão relevante e os dados de clique.

### Como a atribuição funciona com SRNs?

As SRNs relatam eventos, como novas instalações e eventos in-app, para a AppsFlyer da seguinte maneira:

* Usando APIs para se comunicar com provedores de atribuição e métrica.
* Quando os provedores terceirizados de atribuição detectam uma instalação, eles consultam a rede usando o advertising ID.
* A SRN informa os detalhes relevantes de cliques ou impressões de anúncios.

Depois que a AppsFlyer realiza a atribuição, <Anchor target="_blank" href="/marketers/pt/docs/user-level-data-retention#períodos-de-retenção-de-dados-de-parceiros">os postbacks in-app são enviados ao SRN durante o período de retenção de dados do parceiro.</Anchor>

### Como funciona a atribuição para SRNs—Avançadas?

As SRNs avançadas fazem a atribuição da mesma forma que as SRNs. No entanto, SRNs avançadas também podem atribuir engajamentos quando não há device ID (IDFA)—usando a estrutura de <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-knowledge-base-glossary#privacidade-avançada-agregada">Privacidade Avançada Agregada</Anchor>. Em certos casos, a atribuição é realizada usando <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model#device-id-matching">ID matching</Anchor> com consentimento duplo e, para algumas SRNs avançadas, por meio de <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model#probabilistic-modeling">modelagem probabilística</Anchor> através de comunicação por API para cliques e impressões.

### Atribuição de instalação

Os usuários em potencial veem e interagem com vários anúncios antes de instalar um aplicativo. Em geral, os provedores de atribuição oferecem aos anunciantes a atribuição de último toque, o que atribui uma instalação ao último toque feito antes da instalação real.

Quando um aplicativo é inicializado pela primeira vez:

* A AppsFlyer verifica se:
  * O aplicativo está configurado para receber tráfego de SRNs.
  * O usuário tem um advertising ID.
* Se ambas as condições forem cumpridas, a AppsFlyer consulta SRNs usando o advertising ID.
* A AppsFlyer executa a atribuição após considerar as reivindicações da SRN.

#### Exemplos de atribuição de instalação

<div id="example-a-assisted-attribution" />

<Accordion title="Exemplo A: Atribuição assistida">

![SRN_1.png](https://files.readme.io/8e244c99f54b36a4e88b03bf05bb7ca0da2db5c7c601882ea9f68c191c38981b-32259428920337.png)

**Segunda-feira:** A Network A relata um clique do usuário.

**Terça-feira:** A Network B relata um engajamento com um vídeo.

**Quarta-feira:** A Network C relata o clique em um anúncio jogável e, 30 minutos depois, ocorre uma instalação.

A **AppsFlyer** atribui a instalação à Network C e dá crédito às Networks A e B por auxiliarem a instalação.

A AppsFlyer fornece aos anunciantes dados de assistência (engajamentos não atribuídos que ocorrem antes de uma instalação). Isso permite que os anunciantes personalizem seus modelos de atribuição multitouch ou parcial. Para mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/measure-assisted-installs">entendendo as instalações assistidas</Anchor>.

</Accordion>

<div id="example-b-last-click-attribution" />

<Accordion title="Exemplo B: Atribuição do último clique">

![SRN_2.png](https://files.readme.io/6817d8235acfdbbb5324d07ea8a31ace21cf2306e8e099129d9802e3e0d58b0c-32259457863825.png)

A **Network D** (SRN) relata um clique alguns minutos antes da Network C.

A **Network C** usa a integração de atribuição padrão.

A **AppsFlyer** atribui a instalação à Network C porque ela teve o último clique.

</Accordion>

### Janelas de atribuição

As janelas de atribuição incluem lookback e view-through. Algumas SRNs cobram anunciantes por uma instalação baseada no Custo por Impressão (em CPM) e no Custo por ação (CPA)—elas são baseadas em cliques ou impressões que ocorrem dentro de um período de 1 a 28 dias.

A **AppsFlyer** atribui instalação, atividade, Custo efetivo por instalação (eCPI) e Custo efetivo por ação (eCPA) com base na metodologia de atribuição preferida de um anunciante e nas janelas de lookback.

**Os anunciantes** podem ter que pagar por instalações baseadas em janelas de lookback de atribuição e modelos de exibição de SRN.

* Os anunciantes esperam que a metodologia de atribuição universal externa da AppsFlyer otimize e distribua seus gastos com anúncios.
* Porquê? Porque a AppsFlyer reporta eCPI e eCPA reais com base em termos definidos pelo anunciante.
* As SRNs podem se beneficiar a curto prazo, pois geralmente configuram suas próprias condições de pagamento. Mas os anunciantes corrigem isso usando provedores de atribuição externos.

## Deep linking com SRNs

Para que os usuários possam abrir o aplicativo quando o link é clicado, você só precisa configurar o esquema de App Links/Universal Links/URI. No entanto, para executar deep links ou deferred deep linking para uma página ou atividade específica em seu aplicativo, as SRNs usam seus próprios métodos, sem envolver o método de deep linking da AppsFlyer.

Então, como pode realizar deep linking dos seus usuários e obter dados relevantes dos SRNs?

<div id="direct-deep-linking" />

<Accordion title="Deep linking direto">

Quando um dispositivo de usuário executa deep linking, o deep linking direto com SRNs é feito sem chamar o método de deep linking da AppsFlyer. No exemplo abaixo, os usuários existentes que clicam em um anúncio são redirecionados para a atividade diretamente usando os métodos do Facebook, enquanto os novos usuários obtêm a mesma experiência usando os dados de conversão da AppsFlyer. Saiba como o <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-faq#who-needs-facebooks-sdk">Meta ads usa o OneLink para deep linking</Anchor>

> 📄 **Exemplo**
>
> João, profissional de marketing mobile do "greatapp", decide realizar uma campanha de deep linking no Meta ads, direcionado ao público geral. A campanha redireciona quaisquer usuários que clicarem para uma atividade "bônus".
> Paulo, o desenvolvedor mobile, adiciona essa lógica após obter os dados de conversão:
>
> 1. Tem origem no Facebook ("is\_fb=true")?
> 2. Se verdadeiro (true), obtenha o parâmetro do grupo de anúncios.
> 3. Se o valor contém a palavra "bonus", envie o usuário para a atividade "bonus".

</Accordion>

<div id="deferred-deep-linking" />

<Accordion title="Deep linking diferido">

Ao contrário do deep linking, o deferred deep linking com SRNs pode ser feito usando a API GCD da Appsflyer.  A AppsFlyer sempre recebe os dados de conversão e os disponibiliza para o aplicativo quando ele é aberto pela primeira vez. Usuários novos que instalam após clicar em uma campanha de deep linking/retargeting em uma SRN podem ser redirecionados dentro do aplicativo após a inicialização.

O deferred deep linking é compatível com Google Ads, Snapchat e TikTok for Business usando o valor real do deep link, que pode ser consultado através do GCD usando o campo `af_dp`. No caso do TikTok for Business, esse valor também pode ser acessado a partir do campo `deep_link_value`.

No entanto, com outras SRNs, os parâmetros de deep linking regulares da AppsFlyer não estão presentes como parte dos dados de deep link. Para usar esses dados dentro do aplicativo, o desenvolvedor precisa implementar uma lógica adicional com base nos parâmetros disponíveis, como campaign, ad set ou single ad names.

</Accordion>

## Implicações para iOS

A maioria das SRNs é compatível com a SKAdNetwork e tem a integração necessária com a AppsFlyer.

<div id="ios-145-srn-attribution" />

<Accordion title="Atribuição SRN no iOS 14.5">

A partir do iOS 14.5, quando os usuários dão o consentimento à ATT nos aplicativos do anunciante e do publisher (<Anchor target="_blank" href="/marketers/pt/docs/appsflyer-knowledge-base-glossary#duplo-consentimento">consentimento duplo</Anchor>), as instalações SRN, que são registradas no <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">dashboard da SKAdNetwork</Anchor>, também são exibidas nos dashboards tradicionais.

> 📘 **Nota**
>
> * O dashboard tradicional mostra uma redução nas instalações atribuídas a SRNs. Ao considerar a performance da SRN, use o <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">dashboard da SKAdNetwork</Anchor>. No geral, espere uma redução nas atribuições SRN das instalações, com um aumento correspondente nas instalações orgânicas. No entanto, para SRNs avançadas, o impacto é menor, pois eles também atribuem engajamentos quando não há device ID.
> * O <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">dashboard da SKAdNetwork</Anchor> é atualizado com um atraso de 48 a 72 horas após a instalação.
> * As instalações trazidas pelo Apple Search Ads (ASA) não são atribuídas no dashboard da SKAdNetwork.

</Accordion>

<div id="sending-event-postbacks-to-srns" />

<Accordion title="Enviar postbacks de eventos para SRNs">

SRNs que recebem postbacks de eventos dependem da inclusão do device ID no postback. Isso permite que as SRNs atribuam automaticamente as ações do usuário relatadas. Muitos usuários do iOS 14 não consentem — ou seja, não permitem o acesso ao device ID (IDFA). Nesse caso, você deve esperar:

* Uma diminuição no número de postbacks de eventos enviados para SRNs
* Discrepâncias no número de postbacks de eventos entre SRNs e a AppsFlyer — que registra todos os eventos.

> 📘 **Nota**
>
> * Se não houver IDFA, postbacks para instalações, aberturas de aplicativos ou eventos in-app não serão enviados às SRNs. [No entanto, em alguns casos, a AppsFlyer envia postbacks para SRNs mesmo sem o advertising ID](/docs/self-reporting-networks-srns#does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid).
> * As ad networks de cliques não são afetadas, pois usam suas próprias IDs de transação, e não IDs de dispositivo, para autoatribuir informações de postback de eventos.

</Accordion>

## Perguntas frequentes

<div id="how-does-retargeting-work-with-srns" />

<Accordion title="Como funciona o retargeting com SRNs?">

Os cliques de retargeting de não SRNs são facilmente identificáveis pela existência do parâmetro `is_retargeting=true` no link de atribuição de retargeting.  
Com SRNs, não há uma indicação semelhante. Em vez disso, para permitir a atribuição de reengajamentos de SRNs, a AppsFlyer usa outra lógica:

* Pré-requisitos:
  * Na página **Configurações do aplicativo**, habilite **Ativar retargeting.**
  * Na página **Integrações ativas**, selecione a SRN e ative **Retargeting**.
* Com cada inicialização de aplicativo, a AppsFlyer consulta a SRN sobre engajamentos recentes do device ID com anúncios de campanha para o aplicativo.
  * Se a SRN responder com informações de engajamento, a AppsFlyer valida que o engajamento está dentro da janela de lookback e além do tempo mínimo entre os reengajamentos.
  * Os engajamentos validados são registrados como reengajamentos e atribuídos à SRN.

</Accordion>

<div id="what-is-srn-mistargeting" />

<Accordion title="O que é uma segmentação equivocada de SRN?">

As campanhas de SRNs devem ter como alvo um público específico, mas nem sempre isso acontece: Pessoas que não são usuários em campanhas de aquisição e usuários existentes em campanhas de retargeting.

Se uma SRN for usada para executar tanto campanhas de aquisição quanto de retargeting de usuários, isso pode levar a erros de segmentação de usuários. Como resultado, você paga pelo tráfego errado.

Cenário: uma SRN na plataforma da AppsFlyer está habilitada para uma campanha de aquisição de usuários.

* Após cada abertura do aplicativo, a AppsFlyer consulta a SRN para verificar se o advertising ID (usuário) teve um engajamento recente.
* Se sim,
  * a SRN responde com o nome da campanha.
  * A AppsFlyer determina se essa é a primeira abertura (ou não) e atribui os atributos em conformidade:  
    **Primeira abertura**: Uma nova instalação é atribuída à campanha.  
    **Demais aberturas**: Um evento de retargeting é atribuído à campanha.

**Conclusão:** receber eventos de retargeting de uma campanha de aquisição de usuários é um desperdício.

#### O erro de direcionamento é um problema?

Analistas de dados da AppsFlyer verificaram as campanhas de **aquisição de usuários** do Meta ads durante um determinado mês.

* O retargeting estava ativado.
* Em 30% das campanhas, pelo menos 15% dos usuários segmentados já eram usuários do aplicativo.
* Em 5% das campanhas, pelo menos 40% já eram usuários do aplicativo.
* **Conclusão: em campanhas de aquisição de usuários dessa SRN, 1 a cada 10 usuários segmentados já é um usuário existente.**

[![mistargeted_users.png](https://files.readme.io/e135e9fc9ccda47a5d06c9595f171a60f9892f4c63212b4e459eeec897b16a3b-32259428927505.png)](https://files.readme.io/e135e9fc9ccda47a5d06c9595f171a60f9892f4c63212b4e459eeec897b16a3b-32259428927505.png)

#### Resolvendo o problema de erros de segmentação

**Solução básica:** não inclua usuários existentes em uma campanha de aquisição de usuários.

* A SRN segmentará somente novos usuários em potencial.
* **Maximize os resultados de aquisição de novos usuários com o mesmo orçamento**.
* Atualize periodicamente (e manualmente) a campanha - por exemplo, uma vez por mês.
* No entanto, com diferentes intervalos de tempo, os usuários existentes podem ser segmentados em campanhas de aquisição de usuário durante o primeiro mês após a instalação de um aplicativo.

<Anchor target="_blank" href="/marketers/pt/docs/audiences-guide">**Audiences**</Anchor>, um recurso premium da AppsFlyer, permite que você envie automaticamente, e diariamente, qualquer segmento da sua base de usuários para dezenas de ad networks.

A pesquisa da AppsFlyer mostra que resolver erros de segmentação pode ter um impacto significativo nos seus esforços de marketing e aquisição de usuários.

</Accordion>

<div id="why-is-the-original-url-field-empty-in-raw-data-reports" />

<Accordion title="Por que o campo URL original está vazio nos relatórios de dados brutos?">

O clique ocorre no ambiente SRN, mas não tem um link de atribuição da AppsFlyer. Portanto, os dados de URL Original associados ao clique não estão disponíveis para a AppsFlyer.

</Accordion>

<div id="dashboard-doesnt-show-srn-clicks-and-impressions" />

<Accordion title="O dashboard não mostra cliques e impressões da SRN">

O clique ocorre no ambiente SRN, mas não tem um link de atribuição da AppsFlyer. Por isso, algumas SRNs não fornecem dados de cliques e impressões para a AppsFlyer.

<Anchor target="_blank" href="/marketers/pt/docs/meta-ads-integration-setup#cost-clicks-and-impressions">Meta ads</Anchor> e <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-cost-and-ad-revenue">Google</Anchor> fornecem alguns dados agregados à AppsFlyer.

</Accordion>

<div id="can-agencies-configure-srn-campaigns" />

<Accordion title="As agências podem configurar campanhas SRN?">

Sim, <Anchor target="_blank" href="/partners/pt/docs/about-agency-accounts#redes-de-anúncios-com-autorrelato">veja aqui sobre configuração de SRN por agências</Anchor>.

</Accordion>

<div id="does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid" />

<Accordion title="A AppsFlyer envia postbacks para advertising IDs ausentes (IDFA/GAID)?">

Quando os advertising IDs contêm uma string vazia ("") ou mostram o valor '00000000-0000-0000-0000-000000000000' (IDFAs zerados), a AppsFlyer não envia postbacks para instalações, eventos de abertura ou eventos in-app, exceto para os seguintes cenários:

* Google Ads: Como parte da integração para a mensuração de remarketing com o Google Ads, quando um usuário não autorizado do iOS abre o aplicativo ou realiza um evento in-app, a AppsFlyer envia o `gbraid` e informações do evento para o Google Ads (para o evento `additional_data_json`).
* Google Ads: No Android, quando não existe um device ID, mas o valor do referrer contém `gclid` (para instalações) ou um evento de reengajamento contém um deep link com o parâmetro `gclid`, a AppsFlyer envia o `gclid` e a informação do evento para o Google Ads.
* Meta: Cookies do Facebook ou IDs de campanha (em deep link ou reengajamento anterior) ou toggle de AEM ativado.
* Snapchat e <Anchor target="_blank" href="/marketers/pt/docs/tiktok-for-business-advanced-srn-integration-setup">TikTok for Business—Advanced SRN</Anchor>: se uma instalação for atribuída ao Snapchat ou ao TikTok via modelo probabilístico e um evento in-app vinculado a essa instalação for recebido, o postback será enviado.

Parâmetro `gbraid` do Google Ads: Um identificador agregado gerado pelo Google que identifica um grupo de dispositivos e é referenciado pelo link direto.

**ID de clique do Google (parâmetro  ):** um parâmetro enviado na URL com cliques em um anúncio, que identifica a campanha e outros atributos de clique associados ao anúncio. Isso é utilizado para rastreamento de anúncios e atribuição de campanhas.

</Accordion>

<div id="are-clicks-and-impressions-from-srns-available-in-raw-data-reports" />

<Accordion title="Os cliques e impressões de SRNs estão disponíveis nos relatórios de dados brutos?">

Não, cliques e impressões de SRNs não são compartilhados em relatórios de dados brutos. Embora os dados da SRN sejam usados para atribuição, cliques e impressões brutos não estão incluídos nos relatórios. Isso se aplica a todas as SRNs, incluindo TikTok, Snap, Meta e Google.

</Accordion>

<div data-zendesk-anchors="srns-integrated-with-appsflyer=srns-integradas-%C3%A0-appsflyer h_01HFM2MET40AFB84AW5N8GKWF3=srns-integradas-%C3%A0-appsflyer attribution=atribui%C3%A7%C3%A3o h_01HFM2MET4ZNKEZBT3S74N8CMC=atribui%C3%A7%C3%A3o how-does-attribution-work-with-srns=como-a-atribui%C3%A7%C3%A3o-funciona-com-srns h_01HFM2MET42R6C87XB5RWX9ABJ=como-a-atribui%C3%A7%C3%A3o-funciona-com-srns how-does-attribution-work-with-advanced%E2%80%94srns=como-funciona-a-atribui%C3%A7%C3%A3o-para-srnsavan%C3%A7adas h_01HFM2MET4Q6WCSANH18VTGBQX=como-funciona-a-atribui%C3%A7%C3%A3o-para-srnsavan%C3%A7adas install-attribution=atribui%C3%A7%C3%A3o-de-instala%C3%A7%C3%A3o h_01HFM2MET4YQGN3GZKTTBRQ4HK=atribui%C3%A7%C3%A3o-de-instala%C3%A7%C3%A3o install-attribution-examples=exemplos-de-atribui%C3%A7%C3%A3o-de-instala%C3%A7%C3%A3o h_01HFM2MET40Y9V8YGA20CCGVNN=exemplos-de-atribui%C3%A7%C3%A3o-de-instala%C3%A7%C3%A3o h_01HFM2MET47BP3T07NTRVDWSJ3=example-a-assisted-attribution h_01HFM2MET4FY6SRS534NEA25WV=example-b-last-click-attribution attribution-windows=janelas-de-atribui%C3%A7%C3%A3o h_01HFM2MET4ZJF290QNE3TPXQMA=janelas-de-atribui%C3%A7%C3%A3o deep-linking-with-srns=deep-linking-com-srns h_01HFM2MET4ZA6WD6HX92JNFW7X=deep-linking-com-srns h_01HFM2MET4VZX943736W52V0ZJ=direct-deep-linking h_01HFM2MET4HSVHM0Q1C8D5Z279=exemplo h_01HFM2MET4WGVMRJW7NJ7TF8GQ=deferred-deep-linking ios-implications=implica%C3%A7%C3%B5es-para-ios h_01HFM2MET4DGERZJ18A7CEFDS9=implica%C3%A7%C3%B5es-para-ios h_01HFM2MET4SRX0YRZRMHBY6DKT=ios-145-srn-attribution h_01HFM2MET471M5J2XFE7G2Z6J3=nota h_01HFM2MET42KNAMWE9S9BSF4PK=sending-event-postbacks-to-srns h_01HFM2MET4WJ6TMTXM03NFFCAG=nota-1 faq=perguntas-frequentes h_01HFM2MET49FZ8QHDMA7H92BTE=perguntas-frequentes h_01HFM2MET4VYGPWR98HMAWK4YP=how-does-retargeting-work-with-srns h_01HFM2MET4JGYTW6P1VGYMYGFS=what-is-srn-mistargeting is-mistargeting-a-problem=o-erro-de-direcionamento-%C3%A9-um-problema h_01HFM2MET4C1HMWH715XP42ZAQ=o-erro-de-direcionamento-%C3%A9-um-problema solving-the-mistargeting-problem=resolvendo-o-problema-de-erros-de-segmenta%C3%A7%C3%A3o h_01HFM2MET41CDCP8VNGR39YMCK=resolvendo-o-problema-de-erros-de-segmenta%C3%A7%C3%A3o h_01HFM2MET4DETEHT8PACHS6C6B=why-is-the-original-url-field-empty-in-raw-data-reports h_01HFM2MET48Y4ATGB1HNDGSFEP=dashboard-doesnt-show-srn-clicks-and-impressions h_01HFM2MET4JEA8BBGN564CQPYX=can-agencies-configure-srn-campaigns h_01HFM2MET42V7AVV2BPZGDRARV=does-appsflyer-send-postbacks-for-missing-advertising-ids-idfagaid h_01JMJ79S862T4M96ECZPVRZVJJ=are-clicks-and-impressions-from-srns-available-in-raw-data-reports" />
