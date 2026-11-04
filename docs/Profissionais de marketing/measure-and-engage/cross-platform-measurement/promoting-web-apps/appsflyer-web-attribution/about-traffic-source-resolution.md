---
title: Sobre a identificação de fontes de tráfego
metadata:
  keywords:
    - Agencies
    - Web Attribution
    - Web Attribution SDK
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
    - Agencies
  created_at: '2026-02-04T13:46:22Z'
  edited_at: '2026-10-20T03:44:48Z'
  id: 43518064765201
  locale: pt
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/pt/articles/43518064765201
---
> **At a glance:** Use a identificação de fontes de tráfego para determinar as fontes de mídia, as campanhas e os canais de origem para cada visita na web, usando os parâmetros de URL e os dados de referrer disponíveis no carregamento das landing pages. Isto fornece à atribuição o contexto da origem do tráfego de que precisa para atribuir com precisão eventos web subsequentes, incluindo o evento de aquisição de utilizadores.

<div id="what-is-traffic-source-resolution" />

## O que é a identificação de fontes de tráfego?

Para a atribuição da web, o carregamento de landing pages (**visita na web**) é o primeiro engajamento do usuário com o site. A AppsFlyer se baseia nas informações disponíveis no momento, como parâmetros de URL e dados de referrer, para identificar o canal de mídia, a campanha e o canal do usuário.

Esse processo, conhecido como **identificação de fontes de tráfego**, determina a fonte de mídia e as informações da campanha a partir de parâmetros de URL. A AppsFlyer registra e prioriza esses parâmetros para determinar o contexto inicial da fonte de tráfego de uma visita.

A identificação de fontes de tráfego é um **processo pré-atribuição**. Os parâmetros identificados podem ser substituídos posteriormente durante <Anchor target="_blank" href="/marketers/pt/docs/web-performance-measurement-overview#fluxo-de-mensuração-da-performance-web">o processo de atribuição</Anchor>.

O papel da identificação da fonte de tráfego não se limita à visita. O resultado fornece o contexto da fonte de tráfego que o processo de atribuição usa para eventos da web posteriores, incluindo o evento de aquisição de usuários.

Entender o mecanismo da identificação de fontes de tráfego é essencial para criar URLs precisas. Para saber como criar uma URL bem estruturada, veja o artigo sobre a <Anchor target="_blank" href="/marketers/pt/docs/choose-attribution-parameters-for-landing-page-urls">escolha de parâmetros de atribuição para URLs de landing pages</Anchor>.

<div id="the-traffic-source-resolution-flow" />

## O fluxo de identificação de fontes de tráfego

A identificação de fontes de tráfego segue um fluxo estruturado em várias etapas que cria progressivamente o contexto de atribuição para cada visita à web. Cada etapa contribui com uma camada específica de informações, desde a gravação da visita até a classificação do tráfego para relatórios. Os dados usados pelo fluxo de identificação de fontes de tráfego são registrados pelo Web SDK ou pelo Web S2S.

O fluxo consiste nas seguintes etapas:

1. [Gravação de visita](#etapa-1-gravação-de-visita): Registra a chegada do usuário ao site e grava um evento de visita, mesmo quando a fonte do tráfego ainda é desconhecida. Isso garante que todas as entradas de usuários elegíveis sejam mensuradas antes que a lógica de atribuição seja aplicada.
2. [Identificação de fontes de mídia](#etapa-2-identificação-de-fontes-de-mídia): Analisa parâmetros de URL e dados de referrer para identificar a plataforma ou o parceiro que impulsionou a visita, bem como determinar se a visita é orgânica.
3. [Identificação de campanhas](#etapa-3-identificação-de-campanhas): Determina os detalhes granulares de campanhas associados à fonte de mídia identificada, permitindo uma análise precisa de performance.
4. [Classificação de canais](#etapa-4-classificação-de-canais): Atribui cada visita a um canal de tráfego principal com base na fonte de mídia identificada, fornecendo uma visão padronizada para relatórios e análises.

<div id="step-1-visit-recording" />

## Etapa 1: Gravação de visita

A gravação de visita é o primeiro passo no fluxo de mensuração da performance web. Ela acontece antes da identificação e atribuição da fonte de mídia, atuando como uma camada de pré-processamento que registra a atividade original do usuário.

A lógica tem duas fases. Primeiro, ela classifica o **referrer** (o domínio de origem do usuário antes de chegar ao seu site). Depois, com base no tipo de referrer, ela avalia a sessão do usuário e a presença de informações da fonte de mídia para decidir se deve gravar a visita.

<div id="stage-1-referrer-classification" />

#### Fase 1: Classificação do referrer

A AppsFlyer classifica o referrer em um dos três tipos:

* **Externo excluído** (por exemplo, um processador de pagamento ou qualquer domínio que você excluiu)
* **Internal excluded** (por exemplo, seus próprios subdomínios ou fluxos de login)
* **Else** (todos os outros referrers)

<div id="stage-2-session-evaluation-and-visit-recording" />

#### Fase 2: Avaliação da sessão e gravação de visita

Com base no tipo de referrer, a AppsFlyer avalia a sessão e decide se a visita será gravada:

* **External excluded:** A visita nunca é gravada.
* **Internal excluded:** A atribuição baseada em referrer é suprimida, porque o referrer não é uma fonte de aquisição real.
  * Se houver uma sessão ativa (uma sessão é considerada inativa após 30 minutos de inatividade; caso contrário, ela está ativa), a visita não será gravada.
  * Se não houver sessão ativa, a visita será gravada, mas o referrer será considerado self-referral e será ignorado. A visita é gravada como orgânica, a menos que a URL inclua parâmetros de atribuição (UTM, PID, ID de clique, etc.).
* **Else:**
  * Se não houver sessão ativa, você poderia registrar a visita? Uma nova sessão conta como uma nova visita, independentemente de outras condições.
  * Se houver uma sessão ativa e uma fonte de mídia indireta (UTM, PID, ID de clique, etc.), grave a visita. Essa revisita pode acionar uma conversão de retargeting (reengajamento), que é usada para atribuir eventos posteriores.
  * Se houver uma sessão ativa e nenhuma informação da fonte de mídia, não grave uma nova visita durante essa sessão.

<Image alt="traffic resolution flow" src="https://files.readme.io/d5f807d5ced5ed9a90a41cda0f38fe7ffef0b81c321bae90ad410076b484c810-47195479783953.png" width="1494px" />

<div id="step-2-media-source-resolution" />

## Etapa 2: Identificação de fontes de mídia

O processo de identificação de fontes de mídia determina se uma visita é:

* **Não orgânica:** Uma fonte de atribuição específica é encontrada.
* **Orgânica:** Nenhuma fonte de atribuição é encontrada (por exemplo, o usuário digitou a URL diretamente ou usou os favoritos).

Durante o processo de identificação de fontes de mídia, a AppsFlyer determina a origem de uma visita na web ao avaliar parâmetros extraídos do caminho da URL da landing page e da string de consulta.

Para obter os melhores resultados, use os parâmetros específicos da AppsFlyer, como `pid` e `af_campaign`, que fornecem o mais alto nível de granularidade e controle. A AppsFlyer também reconhece parâmetros padrão da indústria, como tags UTM e IDs de clique, permitindo que você comece sem necessidade de alterar sua configuração de mensuração de anúncios.

A AppsFlyer segue uma ordem de prioridade para identificar a fonte de mídia. O processo é interrompido assim que uma fonte é identificada, e nas seguintes etapas: O processo de resolução do canal de mídia consiste nas seguintes etapas:

<Accordion title="1. Excluir domínios">

Primeiro, a AppsFlyer verifica se a visita tem origem em um domínio na sua **lista de exclusão**. Se o domínio for excluído (por exemplo, seu domínio interno ou um processador de pagamento como o PayPal), a visita será automaticamente ignorada ou classificada como **Orgânico.**

Para obter mais informações sobre como especificar os domínios excluídos ao adicionar um aplicativo web à AppsFlyer, confira os <Anchor target="_blank" href="/marketers/pt/docs/configure-web-performance-measurement-settings#domínios-excluídos">domínios excluídos</Anchor>.

</Accordion>

<Accordion title="2. PID da AppsFlyer (ID de parceiro)">

Se o domínio não for excluído, a AppsFlyer buscará o parâmetro `pid=` na URL.

* Se for encontrado, a fonte de mídia é extraída diretamente do valor.
* <span id="social-media-partners"></span>Os seguintes parceiros de redes sociais usam rótulos de exibição específicos em vez do valor original do parâmetro de URL.

| Parâmetro de URL (PID) | Nome de exibição da fonte de mídia |
| --- | --- |
| `pid=iossearchads_int` | Anúncios de Busca da Apple |
| `pid=facebook_int` | Anúncios do Facebook |
| `pid=metaweb_int` | Anúncios do Facebook |
| `pid=twitter_int` | Twitter |
| `pid=twitterweb_int` | Twitter |
| `pid=googleads_int` | googleadwords\_int |
| `pid=tiktokweb_int` | tiktokglobal\_int |
| `pid=snapweb_int` | "snapchat\_int" |

</Accordion>

<Accordion title="3. Parâmetros UTM">

Se nenhum PID for encontrado na URL, a AppsFlyer avalia os parâmetros `utm_source` e `utm_medium` para identificar a fonte de mídia. A combinação destes dois campos determina a resolução resultante.

<div id="how-utm-logic-works" />

#### **Como funciona a lógica de UTM**

* Na maioria dos casos, a AppsFlyer determina a fonte de mídia ao extrair o valor original de `utm_source` e usá-lo como fonte de mídia.
* Se `utm_medium` for `email`, `mail` ou `e-mail`, a fonte de mídia é determinada automaticamente para `e-mail`.
* Se `utm_medium` estiver presente e não for um valor de e-mail, a AppsFlyer verifica o valor com base em regras de mapeamento personalizadas específicas (consulte a tabela de mapeamento abaixo).
* Se `utm_medium` estiver ausente ou não corresponder a nenhuma regra personalizada, a AppsFlyer volta a usar `utm_source` como fonte de mídia.

<div id="utm-mapping-rules" />

#### **Regras de mapeamento da UTM**

| utm\_source | utm\_medium | compras in-app |
| --- | --- | --- |
| Google, googleads\_int | cpc / ppc / paidsearch / paid\_search / paid-search / search / paid | googleadwords\_int |
| Google | cpm / display / banner / video / listing | dv360\_int |
| dfa / dbm / dcm / doubleclick | CPM (custo por mil impressões) | dv360\_int |
| Facebook / FB / Meta, metaweb\_int, facebook\_int | cpc / ppc / cpm / cpa / paidsocial / paid-social / paid\_social / paid | Anúncios do Facebook |
| Bing / Microsoft / MS | cpc / ppc / paidsearch / paid\_search / paid-search / search / paid | bingsearch\_int |
| Yahoo / Gemini | cpm / display / listing | yahoogemini\_int |
| twitter, twitter\_int, twitterweb\_int | cpc / ppc / paid / paidsocial / paid-social / paid\_social | Twitter |
| Snapchat / snap, snapweb\_int | swipe / cpc / ppc / paid / paidsocial / paid-social / paid\_social | "snapchat\_int" |
| Pinterest | cpc / ppc / paid / paidsocial / paid-social / paid\_social | pinterest\_int |
| tiktok, tiktokweb\_int | cpc / ppc / paid / paidsocial / paid-social / paid\_social | tiktokglobal\_int |
| iossearchads\_int | qualquer / nenhum | Anúncios de Busca da Apple |
| chatgpt.com | pago: cpc / ppc / cpm / paid / paid\_search / paidsearch / display / banner / video | openai\_int |
| chatgpt.com | nenhuma das opções acima* | chatgpt\_organic\_aeo (canal: aeo) |
| perplexity | qualquer / nenhum | perplexity\_organic\_aeo (canal: aeo) |

*\*Se estiver presente um* `oppref` *click ID, a AppsFlyer ignora esta linha e determina a visita a partir de* `oppref` *(consulte Click IDs).*

</Accordion>

<Accordion title="4. IDs de clique">

Se nenhum parâmetro PID ou UTM estiver presente na URL, a AppsFlyer tenta identificar a fonte de mídia usando **IDs de clique**, que são identificadores exclusivos anexados automaticamente às URLs por ad networks específicas. que são identificadores exclusivos anexados automaticamente às URLs por ad networks específicas.

A AppsFlyer usa o seguinte mapeamento de IDs de clique para atribuir a visita:

| Parâmetro de ID do clique | Fonte de mídia identificada |
| --- | --- |
| `gclid`, `wbraid` ou `gbraid` | googleadwords\_int |
| `msclkid` | bingsearch\_int |
| `twclid` | Twitter |
| `vmcid` | yahoogemini\_int |
| `sccid` | "snapchat\_int" |
| `li_fat_id` | linkedin\_int |
| `ttclid` | tiktokglobal\_int |
| `tbclid` | taboola\_int |
| `ob_click_id` | outbrain\_int |
| `dicbo` | outbrain\_int |
| `yclid` | yandex\_int |
| `rdt_cid` | reddit\_int |
| `epik` | pinterest\_int |
| `oppref` | openai\_int |

> 📘 **Note**
>
> * A AppsFlyer não usa fbclid para identificar fontes de tráfego porque a Meta anexa o código a cliques pagos e orgânicos do Facebook. Para atribuir o tráfego à Meta, inclua pid=facebook\_int ou defina utm\_source ao valor da fonte relevante da Meta.
> * O parâmetro dclid não é usado para identificar fontes de mídia. dclid é um identificador do Campaign Manager 360 (CM360) que pode acompanhar outros IDs de clique, como fbclid (Facebook) ou ttclid (TikTok), quando o CM360 é usado. Usar somente dclid pode resultar em uma identificação incorreta.

</Accordion>

<Accordion title="5. Referência HTTP">

Se nenhum parâmetro de consulta (PID, UTMs ou IDs de clique) for encontrado na URL, a AppsFlyer usa `http_referrer` para identificar a fonte de tráfego. Isso depende de um mecanismo interno de análise que extrai o host do domínio, mapeando-o para uma fonte de mídia.

<div id="the-parsing-mechanism" />

#### **O mecanismo de análise**

Para identificar a fonte, a AppsFlyer limpa a string de referrer ao:

1. Extrair apenas o **host** da URL
2. Remover **sufixos de domínio** (domínios de primeiro nível como `.com`, `.org` ou extensões como `.co.uk`)
3. Remover **prefixos de domínio** (como `www.`, `m.`, `l.`, `l.`ou `lm.`)

*Exemplo: Um referrer de* `www.mywebsite.com?param=example` *é associado a uma fonte de mídia de* `mywebsite`.

<div id="referrer-mapping-rules" />

#### **Regras de mapeamento de referrers**

| Se o host contiver... | Fonte de mídia identificada |
| --- | --- |
| `mail.` ou `outlook.` | E-mail |
| `t.co` | twitter |
| `googleads.g.doubleclick.net` | googleadwords\_int |
| `tpc.googlesyndication.com` | dv360\_int |

<div id="search-engine-mapping" />

#### **Mapeamento de mecanismos de busca**

| Se o host contiver... | Fonte de mídia identificada |
| --- | --- |
| `google.` | google\_organic\_seo |
| `search.yahoo` | yahoo\_organic\_seo |
| `bing.com` | bing\_organic\_seo |
| `ask.com`, `de.ask.com`, `uk.ask.com` | ask\_organic\_seo |
| `duckduckgo.com` | duckduckgo\_organic\_seo |
| `yandex.com`, `yandex.ru` | yandex\_organic\_seo |
| `search.naver.com` | naver\_organic\_seo |
| `daum.net` | daum\_organic\_seo |
| `baidu.com` | baidu\_organic\_seo |
| `ecosia.org/search` | ecosia\_organic\_seo |
| `coccoc.com/search` | coccoc\_organic\_seo |
| `sogou.com` | sogou\_organic\_seo |
| `yahoo.co.jp` | yahoojapan\_organic\_seo |

Todas as linhas desta tabela são resolvidas para o canal `seo`.

<div id="ai-answer-engine-referrer-mapping" />

#### **Mapeamento de referrer do mecanismo de respostas de IA**

| Se o host contiver... | compras in-app | Disponível apenas em <Anchor target="_blank" href="/marketers/pt/docs/about-data-locker-advanced-reports">relatórios avançados</Anchor>. |
| --- | --- | --- |
| `chatgpt.com`, `chat.openai.com` | chatgpt\_organic\_aeo | aeo |
| `perplexity.ai` | perplexity\_organic\_aeo | aeo |
| `gemini.google.com` | gemini\_organic\_aeo | aeo |
| `claude.ai` | claude\_organic\_aeo | aeo |
| `deepseek.com` | deepseek\_organic\_aeo | aeo |
| `manus.im` | manus\_organic\_aeo | aeo |
| `grok.com` | grok\_organic\_aeo | aeo |
| `copilot.microsoft.com` | copilot\_organic\_aeo | aeo |

<div id="android-app-referrers" />

#### **Referrers de aplicativos Android**

Se a visita for originada um aplicativo Android, o host do referrer será mapeado da seguinte forma:

| String de referrer do aplicativo | Fonte de mídia identificada |
| --- | --- |
| `com.google.android.googlequicksearchbox` | Google Search |
| `com.google.android.gm` | E-mail |
| `com.linkedin.android` | linkedin |
| `com.twitter.android` | twitter |
| `org.telegram.messenger` | telegram |

</Accordion>

<div id="step-3-campaign-resolution" />

## Etapa 3: Identificação de campanhas

Depois que o canal de mídia for confirmado na Etapa 2, a AppsFlyer tenta identificar os detalhes específicos da campanha.

A AppsFlyer extrai informações de campanha dos seguintes parâmetros de URL, em ordem de prioridade:

| Parâmetro(s) de URL | Mapear para | Ordem de prioridade |
| --- | --- | --- |
| `c`, `af_campaign`, `utm_campaign` | Campaign name | <ol><li>`C`</li><li>`af_campaign`</li><li>`utm_campaign`</li></ol> |
| `af_c_id`, `af_campaign_id` | ID da campanha | <ol><li>`af_c_id`</li><li>`af_campaign_id`</li></ol> |
| `af_adset` | Nome do adset | — |
| `af_adset_id` | ID do conjunto de anúncios | — |
| `af_ad` | Ad name | — |
| `af_ad_id` | ID do anúncio | — |
| `af_keywords` | Palavras-chave | — |

<div id="step-4-channel-classification" />

## Etapa 4: Classificação de canais

Além de identificar o canal de mídia, a AppsFlyer classifica cada visita em um canal. Essa classificação oferece uma visão geral dos tipos de tráfego nos relatórios de dados brutos e no dashboard.

<div id="overriding-the-channel-with-af_channel" />

### Substituição do canal com af\_channel

Para atribuir um valor de canal personalizado, adicione o parâmetro `af_channel` à URL da página de destino. Por exemplo, `af_channel=ig` define o canal como `ig`, permitindo detalhar o tráfego em um nível que as categorias padrão não capturam, como por posicionamento do anúncio.

O `af_channel` é resolvido somente quando um canal de mídia também é identificado para a visita. Se a visita for orgânica (nenhuma fonte de mídia identificada), ela sempre será atribuída a `Direct`, independentemente de `af_channel` estar presente ou não.

<div id="default-channel-classification" />

### Classificação padrão de canal

Se `af_channel` não estiver presente ou se a visita não atender à condição acima, a AppsFlyer recorre à classificação automática com base no canal de mídia identificado:

* **Direct:** O usuário digitou a URL diretamente ou usou um favorito. Nenhuma fonte de atribuição é identificada.
* **Rede social:** Tráfego com origem nas plataformas sociais.
* **E-mail:** Tráfego de campanhas de e-mail ou provedores de serviços de e-mail.
* **Anúncio:** Tráfego gerado por publicidade paga.
* **Referral:** Tráfego de outros sites, identificado por meio do referrer.
* **Outro:** Tráfego que não corresponde a nenhuma das categorias acima.
* **seo:** Tráfego não pago proveniente de mecanismos de busca.
* **aeo:** Tráfego de mecanismos de respostas com IA.

**Observação:** Cada visita é atribuída a um canal. A classificação é automática e determinística, com base no canal de mídia identificado e no método de atribuição, a menos que seja substituída por `af_channel`.

<div data-zendesk-anchors="what-is-traffic-source-resolution=o-que-%C3%A9-a-identifica%C3%A7%C3%A3o-de-fontes-de-tr%C3%A1fego h_01KGMEER6DX8W3ECBEBYP4DQV1=o-que-%C3%A9-a-identifica%C3%A7%C3%A3o-de-fontes-de-tr%C3%A1fego the-traffic-source-resolution-flow=o-fluxo-de-identifica%C3%A7%C3%A3o-de-fontes-de-tr%C3%A1fego h_01KGMEER6DA4HMSZ3TVEAG84WZ=o-fluxo-de-identifica%C3%A7%C3%A3o-de-fontes-de-tr%C3%A1fego step-1-visit-recording=etapa-1-grava%C3%A7%C3%A3o-de-visita h_01KGMEER6DV02F44C5ZPSBEQEX=etapa-1-grava%C3%A7%C3%A3o-de-visita stage-1-referrer-classification=fase-1-classifica%C3%A7%C3%A3o-do-referrer h_01KSSEM5P8RX29CD6C6ZD2DVAT=fase-1-classifica%C3%A7%C3%A3o-do-referrer stage-2-session-evaluation-and-visit-recording=fase-2-avalia%C3%A7%C3%A3o-da-sess%C3%A3o-e-grava%C3%A7%C3%A3o-de-visita h_01KSSEM5P8KBYDBCB7PAPGPX5M=fase-2-avalia%C3%A7%C3%A3o-da-sess%C3%A3o-e-grava%C3%A7%C3%A3o-de-visita step-2-media-source-resolution=etapa-2-identifica%C3%A7%C3%A3o-de-fontes-de-m%C3%ADdia h_01KGMEER6D082QTZGZYEXT6726=etapa-2-identifica%C3%A7%C3%A3o-de-fontes-de-m%C3%ADdia how-utm-logic-works=como-funciona-a-l%C3%B3gica-de-utm h_01KGMF0E1XBSJCVDWGC4R8XMPX=como-funciona-a-l%C3%B3gica-de-utm utm-mapping-rules=regras-de-mapeamento-da-utm h_01KGMF0JSBZ3WYM65R55BCDAMN=regras-de-mapeamento-da-utm the-parsing-mechanism=o-mecanismo-de-an%C3%A1lise h_01KGMEZA9ETGK6Z89GM111E64Z=o-mecanismo-de-an%C3%A1lise referrer-mapping-rules=regras-de-mapeamento-de-referrers h_01KGMEZESC451HVJT139BSXEA5=regras-de-mapeamento-de-referrers search-engine-mapping=mapeamento-de-mecanismos-de-busca h_01KGMEZKCTASMNXZG13VTVECVH=mapeamento-de-mecanismos-de-busca ai-answer-engine-referrer-mapping=mapeamento-de-referrer-do-mecanismo-de-respostas-de-ia h_01M2G7SJBDHFPEZ0WREHHD2YQF=mapeamento-de-referrer-do-mecanismo-de-respostas-de-ia android-app-referrers=referrers-de-aplicativos-android h_01KGMEZQYCDS23MVW3MQH9Q5JQ=referrers-de-aplicativos-android step-3-campaign-resolution=etapa-3-identifica%C3%A7%C3%A3o-de-campanhas h_01KGMEER6ES1AYT24MC4HZCX9X=etapa-3-identifica%C3%A7%C3%A3o-de-campanhas step-4-channel-classification=etapa-4-classifica%C3%A7%C3%A3o-de-canais h_01KGMEER6ETWGFFM3E17KHMDAF=etapa-4-classifica%C3%A7%C3%A3o-de-canais h_01_overriding-the-channel-with-af-channel=substitui%C3%A7%C3%A3o-do-canal-com-af_channel overriding-the-channel-with-af_channel=substitui%C3%A7%C3%A3o-do-canal-com-af_channel h_01_default-channel-classification=classifica%C3%A7%C3%A3o-padr%C3%A3o-de-canal default-channel-classification=classifica%C3%A7%C3%A3o-padr%C3%A3o-de-canal" />
