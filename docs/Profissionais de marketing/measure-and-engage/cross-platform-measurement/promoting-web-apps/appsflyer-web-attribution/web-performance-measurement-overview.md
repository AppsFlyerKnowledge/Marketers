---
title: Mensuração da performance web - visão geral
metadata:
  keywords:
    - Agencies
    - Web Attribution
    - Web Attribution SDK
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
    - Agencies
  created_at: '2026-02-04T15:07:53Z'
  edited_at: '2026-09-18T00:21:38Z'
  id: 43521734577809
  locale: pt
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/pt/articles/43521734577809
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Resumo:** A mensuração da performance web permite que você identifique quais canais de mídia e campanhas trazem usuários para o seu site, analisando como essas visitas influenciam ações subsequentes ao longo do tempo. Com essa solução, você captura e atribui as interações dos usuários de forma integrada, impulsionando a aquisição (primeiras visitas) e o reengajamento de usuários, desde a primeira visita até a mensuração do lifetime value (LTV).

## Sobre a mensuração da performance web

A atribuição web é um processo que identifica quais canais de mídia e campanhas incentivam os usuários a visitar um site, impactando ações subsequentes.

Uma visita web representa tanto uma atividade de navegação (browsing) quanto o engajamento com anúncio que ocorreu imediatamente antes da visita. Ao contrário da atribuição mobile, onde cliques e instalações devem passar por um processo de matching, uma visita web oferece dados da fonte de marketing na URL de destino e no header, fornecendo um match imediato.

Neste artigo, descrevemos o processo completo de mensuração da performance web, explicando como todas as interações dos usuários são identificadas, capturadas e mensuradas. Esse processo oferece suporte tanto à aquisição de usuários (para identificar e atribuir primeiras visitas) quanto ao retargeting/reengajamento (para mensurar o impacto de campanhas específicas, focadas em usuários que voltam a acessar seu site).

#### People-Based Attribution (PBA)

Se você usa <Anchor target="_blank" href="/marketers/pt/docs/people-based-attribution-pba">People-Based Attribution (PBA)</Anchor>, considere adotar a nova solução de mensuração da performance web para ter uma atribuição mais granular e sinais adicionais.

### Fluxo de mensuração da performance web

O fluxo de mensuração da performance web segue uma sequência de etapas, onde dados brutos de visitas ao site se transformam em insights de marketing acionáveis.

1. [Coleta de dados](#1-data-collection): o sistema captura dados de interação do usuário por meio do Web SDK (Pixel) ou da Server-to-Server (S2S) API.
2. [Gravação de visita](#2-visit-recording)[:](/docs/web-performance-measurement-overview#2-visit-recording) registra a chegada do usuário ao site e grava um evento de visita, mesmo quando a fonte do tráfego ainda é desconhecida.
3. [Identificação de fontes de mídia](#3-media-source-resolution): identifica a fonte de mídia através da análise dos parâmetros da URL, usando uma ordem de prioridade definida.
4. [Identidade - atraso de 30 minutos](#4-the-30minute-identity-delay): adia a decisão de atribuição por 30 minutos para permitir a resolução de identidade por meio do login do usuário.
5. [Resolução de identidade](#5-stitching-and-identity-resolution): conecta a sessão atual a um Customer User ID (CUID) persistente ou um cookie de navegador.
6. [Evento de aquisição de usuários](#6-user-acquisition-ua-event): registra o evento que define o que é uma aquisição (por exemplo, `first_visit` ou um evento personalizado) dentro da janela de lookback.
7. [Período pré-aquisição](#7-preacquisition-period): atribui eventos intermediários que ocorrem entre a primeira visita e o evento de aquisição.
8. [Reengajamento e reaquisição](#8-reengagement-and-reacquisition): atribui usuários recorrentes (que voltam a visitar o site) com base em janelas de inatividade e determina se é um reengajamento ou uma reaquisição.
9. [Mensuração de LTV](#9-ltv-measurement): atribui eventos e receita contínuos para mensurar o valor do lifetime value (LTV) do usuário dentro da janela de atribuição.

## Mensuração da performance web: passo a passo

As seções a seguir explicam cada etapa em detalhes.

<div id="1-data-collection" />

<Accordion title="1. Coleta de dados">

Assim que o usuário chega à landing page, a AppsFlyer captura essa interação por meio de um listener integrado.

* **Web SDK (Pixel)**: um snippet do lado do cliente <Anchor target="_blank" href="/marketers/pt/docs/integrate-appsflyer-web-sdk">implementado diretamente no site ou através do Google Tag Manager (GTM)</Anchor>.
* **Server-to-Server (S2S) API**: uma integração do lado do servidor que ajuda a contornar problemas de mensuração no navegador e bloqueadores de anúncios, permitindo que você enriqueça seus dados antes que eles cheguem à AppsFlyer. A integração S2S pode ser feita diretamente do servidor do cliente ou via Google Tag Manager.

</Accordion>

<div id="2-visit-recording" />

<Accordion title="2. Gravação de visita">

Após a coleta dos dados de sessão, o sistema determina se deve criar uma gravação de primeira visita. Essa gravação serve como um pré-processamento que captura a atividade bruta do usuário antes da resolução e da atribuição da fonte de mídia. Nem toda sessão é registrada como uma visita.

A AppsFlyer registra uma visita quando alguém acessa seu site em uma nova sessão ou com parâmetros de origem reconhecíveis, e ignora visitas de domínios excluídos. Essas regras evitam que as sessões sejam contadas em dobro.

Para mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/about-traffic-source-resolution#etapa-1-gravação-de-visita">gravação de visitas</Anchor>.

</Accordion>

<div id="3-media-source-resolution" />

<Accordion title="3. Identificação de fontes de mídia">

Após a coleta dos dados e a gravação da visita, o mecanismo faz uma análise seguindo uma ordem de prioridade definida. Esse processo em cascata (waterfall) oferece suporte a parâmetros específicos que são um padrão tanto na AppsFlyer quanto no mercado. Assim, nossos clientes **não precisam alterar seus links de atribuição existentes durante a migração**. O primeiro sinal com match é usado para determinar a origem da visita.

* **PID**: o sistema verifica primeiro os parâmetros proprietários da AppsFlyer.
* **Parâmetros UTM**: se não existir um PID, ele procura por tags padrão como `utm_source`.
* **Click IDs**: em seguida, ele procura por IDs específicos da rede, como Google Click ID (`gclid`) ou TikTok Click ID (`ttclid`).
* **Referrer**: como um fallback final, ele identifica a URL onde o usuário estava imediatamente antes de chegar.

Para mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/about-traffic-source-resolution#etapa-2-identificação-de-fontes-de-mídia">resolução da fonte de mídia</Anchor>.

</Accordion>

<div id="4-the-30minute-identity-delay" />

<Accordion title="4. Identidade: atraso de 30 minutos">

Como a maioria dos usuários faz login em 30 minutos após uma visita, a AppsFlyer intencionalmente atrasa as decisões de atribuição por meia hora. Esse atraso evita a classificação incorreta de um usuário como "orgânico", permitindo que o sistema capture o CUID para vincular corretamente os usuários que retornam com cookies expirados à fonte de aquisição original.

</Accordion>

<div id="5-stitching-and-identity-resolution" />

<Accordion title="5. Resolução de identidade">

Após o atraso de 30 minutos, e com a fonte identificada, o sistema conecta sessões fragmentadas em uma única jornada.

* **Vinculação de CUID**: se um Customer User ID (por exemplo, um e-mail anonimizado) for capturado, o mecanismo vincula a sessão ao histórico cross-device do usuário.
* **Fallback de cookie**: se nenhum CUID estiver disponível, o sistema recorre aos cookies do navegador, embora eles sejam menos estáveis e sejam específicos de um dispositivo.

</Accordion>

<div id="6-user-acquisition-ua-event" />

<Accordion title="6. Evento de aquisição de usuários">

Após a resolução de identidade, o mecanismo procura a ação específica que define o usuário como adquirido. O padrão da indústria é o`first_visit`, mas ele geralmente representa um sinal fraco. Por exemplo, ele pode incluir um usuário que clica acidentalmente em um anúncio ou dá um bounce imediato. Ao definir um evento de aquisição personalizado, como um cadastro ou compra, você garante que o lifetime value (LTV) seja atribuído à fonte de marketing que gerou uma ação significativa.

Quando um evento de aquisição ocorre, o mecanismo de atribuição procura retroativamente por um período igual à **janela de lookback (aquisição de usuário)** para identificar uma visita não orgânica à qual esse evento pode ser atribuído. Essa configuração define o tempo máximo permitido entre a visita do usuário e a conclusão do evento de aquisição (Padrão: 30 dias). Se nenhum touchpoint não orgânico for identificado dentro desse período, o evento de aquisição é considerado orgânico e não atribuído. Você pode definir a duração da janela de lookback do evento personalizado ao adicionar seu aplicativo web à AppsFlyer. Para mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/configure-web-performance-measurement-settings#lookback-window-user-acquisition">janela de lookback (aquisição de usuário)</Anchor>.

Dependendo do modelo de negócio, diferentes eventos podem ser configurados para definir uma aquisição de usuário, por exemplo:

* **Evento de cadastro concluído (exemplo: aplicativos bancários)**. O evento de aquisição é acionado apenas quando o fluxo de cadastro é concluído com sucesso.
* **Evento de primeira compra (exemplo: aplicativos de delivery)**. Navegar pelo app ou adicionar itens à sacola não conta; o evento é disparado apenas após uma transação bem-sucedida.
* **Evento de assinatura ativada (exemplo: aplicativos de streaming ou SaaS)**. O evento de aquisição é registrado quando a assinatura é confirmada, não no início da avaliação gratuita ou na instalação do aplicativo.

Para mais informações sobre como definir um evento de aquisição, consulte <Anchor target="_blank" href="/marketers/pt/docs/configure-web-performance-measurement-settings#configurações-de-aquisição-de-usuários">configurações de aquisição de usuário</Anchor>.

</Accordion>

<div id="7-preacquisition-period" />

<Accordion title="7. Período de pré-aquisição">

Após a resolução de identidade, mas antes da aquisição, pode haver uma lacuna na jornada chamada de período de pré-aquisição. Isso é relevante apenas se você definir um evento de aquisição personalizado em vez de usar o evento `first_visit` padrão. Nesse período, os usuários podem realizar ações significativas, como adicionar itens ao carrinho, navegar por produtos ou interagir com conteúdos, antes de completarem o evento que os registra oficialmente como adquiridos, como o cadastro ou uma primeira compra.

A AppsFlyer coleta e atribui esses eventos de pré-aquisição à fonte de marketing, sinalizando-os nos relatórios como eventos de pré-aquisição. A principal diferença entre a atribuição pré-aquisição e pós-aquisição é a janela de atribuição. Durante o período de pré-aquisição, a janela de atribuição é mais curta e corresponde à janela de lookback do evento de UA, pois esses eventos ocorrem antes do evento que define o usuário como adquirido. Após o evento personalizado ser acionado e o usuário ser adquirido, a janela de atribuição se estende para mensurar o valor do lifetime value (LTV), dando crédito de longo prazo à fonte de marketing que adquiriu o usuário.

</Accordion>

<div id="8-reengagement-and-reacquisition" />

<Accordion title="8. Reengajamento e reaquisição">

Depois que um usuário é adquirido, ele pode retornar ao site mais tarde. Uma atribuição de reengajamento (usuário que volta a visitar o site) é acionada quando um usuário recorrente clica em um anúncio e visita o site.

Embora o *reengajamento* foca em usuários existentes, um retorno também pode ser classificado como uma *reaquisição* se o usuário ficar inativo por um longo período. Para ser elegível para a reaquisição, o usuário deve primeiro cruzar a **janela de inatividade** (padrão: 90 dias), que define o período de inatividade necessário para considerá-lo como um usuário "perdido". Passado esse período, se o usuário retornar, o mecanismo registra um novo evento de aquisição de usuário em vez de uma visita padrão.

Para mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/configure-web-performance-measurement-settings#configurações-de-reengajamento">configurações de reengajamento</Anchor> e <Anchor target="_blank" href="/marketers/pt/docs/configure-web-performance-measurement-settings#configurações-de-reaquisição">configurações de reaquisição</Anchor>

</Accordion>

<div id="9-ltv-measurement" />

<Accordion title="9. Mensuração de LTV">

Mesmo que um usuário tenha sido adquirido através de uma campanha de aquisição inicial ou de um esforço de retargeting subsequente, o objetivo final é mensurar seu valor completo ao longo do tempo. Depois que um usuário é atribuído com sucesso a uma fonte, o sistema mensura a atividade contínua para calcular seu lifetime value (LTV).

Essa mensuração é regida pela **janela de atribuição**, que é definida como "para sempre" por padrão. Isso garante que cada ação subsequente (como compras repetidas ou renovações de assinatura) seja creditada de volta à fonte de marketing original que levou o usuário ao site. Ao capturar esses dados de longo prazo, você pode ir além de simples contagens de conversão e determinar o verdadeiro retorno do investimento em anúncios (ROAS) nas suas campanhas.

Para mais informações sobre como definir a **janela de atribuição**, consulte <Anchor target="_blank" href="/marketers/pt/docs/configure-web-performance-measurement-settings#janela-de-atribuição">janela de atribuição</Anchor>.

</Accordion>

<div data-zendesk-anchors="about-web-attribution=sobre-a-mensura%C3%A7%C3%A3o-da-performance-web h_01KGMK4P46QE2HQHADD25TPCQF=sobre-a-mensura%C3%A7%C3%A3o-da-performance-web if-you-use-peoplebased-attribution-pba=people-based-attribution-pba h_01KH0P7BB9KF19S8XRH49DKMZA=people-based-attribution-pba the-appsflyer-web-attribution-flow=fluxo-de-mensura%C3%A7%C3%A3o-da-performance-web h_01KGMK4P4614EEQ28V5FV32CY5=fluxo-de-mensura%C3%A7%C3%A3o-da-performance-web the-appsflyer-web-attribution-process-step-by-step=mensura%C3%A7%C3%A3o-da-performance-web-passo-a-passo h_01KGMK4P46HTB82K2PH9V0E33B=mensura%C3%A7%C3%A3o-da-performance-web-passo-a-passo h_01KGMK4P46VJ0NF1FKFRS8V6J2=1-data-collection h_01KGMK4P46GWBP56NJM2ENARTR=2-visit-recording h_01KGMK4P46ZKS856R5C5KEQDBK=3-media-source-resolution h_01KGMK4P465777YN9MQ1JYZ7HT=4-the-30minute-identity-delay h_01KGMK4P46GFBZTMHDVW2MD3K1=5-stitching-and-identity-resolution h_01KGMK4P46MBT49ECD7RFHDY3X=6-user-acquisition-ua-event h_01KGMK4P46XYPVFV67F000EM6C=7-preacquisition-period h_01KGMK4P472B4TFGVR4VBH4REH=8-reengagement-and-reacquisition h_01KGMK4P47E9TPX0S26TTPW4CB=9-ltv-measurement" />
