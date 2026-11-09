---
title: >-
  Configure a atribuição de reengajamento da busca orgânica (SEO) e das
  respostas orgânicas de IA (AEO)
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2023-05-07T13:34:36Z'
  edited_at: '2026-09-15T00:09:17Z'
  id: 15123194526353
  locale: pt
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/pt/articles/15123194526353
---
> **At a glance:** Tenha dados de atribuição detalhados sobre reengajamentos (usuários que já têm seu aplicativo instalado) de mecanismos de busca orgânicos e mecanismos de respostas de IA, para que você possa otimizar suas conversões orgânicas e orientadas por IA.

<div id="overview" />

## Visão geral

A atribuição de reengajamento da busca orgânica (SEO) e das respostas orgânicas de IA (AEO) é uma solução de atribuição que permite aos clientes da AppsFlyer atribuir reengajamentos (ou seja, aberturas de app mobile por usuários que já têm seu app instalado) a vários mecanismos de busca orgânica e mecanismos de respostas de IA.

Ter acesso a esses dados exclusivos é muito útil para equipes de SEO (search engine optimization) e AEO (answer engine optimization), além de fornecer um feedback valioso sobre seus esforços de SEO e AEO.

<div id="flow" />

### Fluxo

<Image align="center" alt="Diagrama que mostra o fluxo de atribuição de busca orgânica, desde o clique de um usuário em um resultado de pesquisa até a abertura do aplicativo ou o usuário chegar a uma página web" src="https://files.readme.io/4b33060cfa30a4e2786c4a3a213ca41223ae276d63c97ab7c2cb5a997a4b010c-16540659217809.png" />

O fluxo de atribuição de busca orgânica funciona da seguinte forma:

1. Um usuário pesquisa um termo em seu mecanismo de busca do navegador mobile (Google, Bing, etc.). O mecanismo de busca exibe vários resultados clicáveis.
2. Seu desenvolvedor web mapeia alguns desses resultados de pesquisa para abrir seu app mobile usando Android App Links e iOS Universal Links. Se um usuário tiver o aplicativo instalado, quando clicar no resultado da pesquisa, o aplicativo será aberto (sem redirecionar para uma loja de aplicativos primeiro).
3. Após a abertura do aplicativo, a AppsFlyer coleta as informações necessárias e pode atribuir essa abertura ao mecanismo de pesquisa do usuário.
4. Se o usuário não tiver o aplicativo instalado, ele será enviado para uma landing page na web, onde você pode usar qualquer uma das várias soluções Web-to-app da AppsFlyer (como Smart Banners, Smart Script ou QR codes) para redirecioná-lo e atribuí-lo.

<div id="setup" />

## Configuração

**Pré-requisitos**:

* SDK da AppsFlyer para Android V6.12.1
* SDK da AppsFlyer para iOS V6.12.1

**Para configurar a atribuição de busca orgânica**:

1. Peça aos seus desenvolvedores para habilitar a abertura do aplicativo seguindo as instruções de <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#app-opening-methods">Android App Links</Anchor> e <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#app-opening-methods">iOS Universal Links</Anchor> (usando o domínio de nível superior do aplicativo).
2. Na AppsFlyer, no menu lateral, selecione **configurações** > <Anchor target="_blank" href="/marketers/pt/docs/app-settings">configurações do aplicativo</Anchor> e ative:
   * **Atribuição de reengajamento de app mobile por SEO (busca orgânica) e AEO.**
   * **Atribuição de reengajamento**.

> 📘 **Note**
>
> **Aviso para seu desenvolvedor**
>
> performOnDeepLinking consome e soluciona de forma forçada a URL de deep linking quando invocada. Isso impedirá que o recurso de atribuição de SEO funcione corretamente e resultará na atribuição não ser reportada ao canal de mídia de SEO correto.

<div id="data-availability" />

## Disponibilidade de dados

Os dados estão disponíveis da seguinte forma:

* Em dados agregados em dashboards e relatórios, o campo `media_source` indica de qual mecanismo de busca o usuário veio. Exemplo: `google_organic_seo`
* Nos relatórios de dados brutos:
  * O campo `media_source` indica de qual mecanismo de busca o usuário veio. Exemplo: `google_organic_seo`.
  * O campo `http_referrer` inclui a URL completa da página de resultados de pesquisa, da qual o usuário foi enviado para o aplicativo ou para a mobile landing page.
  * O campo `channel` tem o valor `seo` para tráfego de mecanismos de busca orgânica ou `aeo` para tráfego de mecanismos de respostas de IA.

<div id="additional-information" />

## Informações adicionais

<Accordion title="Lista de mecanismos de busca compatíveis">

A atribuição de pesquisa orgânica é compatível com os seguintes mecanismos de busca:

* Google
* Bing
* Yahoo
* Perguntar
* DuckDuckGo
* Yandex
* Naver
* Daum
* Baidu
* Ecosia
* Coccoc
* Sogou
* Yahoo Japan

> 📘 **Note**
>
> Para outros mecanismos de busca, use a solução legada de atribuição de busca orgânica (requer entrada do desenvolvedor).
>
> Em dashboards e relatórios de dados, os mecanismos de pesquisa são exibidos como `<search engine>` \_organic\_seo. Por exemplo: google\_organic\_seo.

</Accordion>

<Accordion title="Lista de mecanismos de resposta de IA compatíveis">

A atribuição de pesquisa orgânica também oferece suporte aos seguintes mecanismos de resposta de IA:

* ChatGPT
* Claude
* Perplexity
* Manus
* Copilot
* Gemini
* Grok
* Deepseek

> 📘 **Note**
>
> Em dashboards e relatórios de dados, os mecanismos de resposta de IA são exibidos como `<AI engine>`\_organic\_aeo. Por exemplo: chatgpt\_organic\_aeo.

</Accordion>

<Accordion title="Perguntas frequentes">

<Accordion title="A atribuição de SEO orgânico incorre em uma taxa adicional?">

Não, esse recurso está incluído na sua assinatura.

</Accordion>

<Accordion title="As conversões orgânicas de SEO contam como parte do meu pacote?">

Sim, o mesmo que conversões não orgânicas.

</Accordion>

<Accordion title="Posso personalizar o nome da fonte de mídia SEO?">

Sem. A AppsFlyer determina o nome do canal de mídia orgânico de SEO, e isso não pode ser personalizado no momento.

</Accordion>

<Accordion title="Se o mecanismo de busca exibir um botão de instalação ao lado dos resultados da busca orgânica e o usuário clicar nele para acessar a loja de aplicativos, a AppsFlyer atribui a instalação ao mecanismo de busca?">

Sem. Nesse caso, a AppsFlyer não pode coletar as informações necessárias para atribuição. A atribuição de pesquisa orgânica exige que o Aplicativo já esteja instalado.

</Accordion>

<Accordion title="Os dados de palavra-chave estão disponíveis?">

Os dados de palavra-chave não estão disponíveis por meio dessa solução de atribuição de busca orgânica. No entanto, existem casos raros em que os dados de palavras-chave estão disponíveis para Android. Consulte <Anchor target="_blank" href="/marketers/pt/docs/evaluate-keyword-data#palavras-chave-do-android">Disponibilidade de dados de palavras-chave no Android</Anchor>.

</Accordion>

<Accordion title="A atribuição de pesquisa orgânica é compatível com um fluxo de instalação?">

Sim, você pode ver de qual página os usuários que instalaram seu aplicativo chegaram ao seu site.

O Smart Script faz isso da seguinte forma:

* Coletando o domínio da URL da página, chamado de web referrer
* Criando um `pid` relevante (que depois é exibido como o canal de mídia) com base na origem específica do usuário
* Mapeando isso para uma chave de parâmetro de sua escolha, como `af_sub1`, na URL de saída

Para saber como configurar o Smart Script para coletar o web referrer, consulte o <Anchor target="_blank" href="/marketers/pt/docs/set-up-smart-script-to-convert-web-visitors#seo-referrer-mapping">guia de configuração do OneLink Smart Script V2</Anchor>.

</Accordion>

</Accordion>

<Accordion title="Especificações e limitações">

| Caraterística | A descrição |
| --- | --- |
| Navegadores | A atribuição de busca orgânica não é compatível com:<ul><li>Firefox no Android</li><li>Qualquer navegador, exceto o Safari no iOS.</li></ul> |
| Aplicativos SwiftUI (iOS) | A atribuição de pesquisa orgânica não tem suporte para Aplicativos iOS criados com SwiftUI. |
| Indica se o usuário se enquadra na jurisdição do DMA (true) ou não (false) | A busca orgânica tem uma janela fixa de reengajamento de 30 dias. O tamanho da janela não pode ser modificado. Para mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/retargeting-attribution-guide#janelas-de-inclusão">Guia de atribuição de retargeting</Anchor>. |

</Accordion>

<div data-zendesk-anchors="organic-search-attribution=vis%C3%A3o-geral h_01H9G0W21SRDC6ZSR1E8AQFZFC=vis%C3%A3o-geral flow=fluxo h_01H9G0W21S4RB56PNV9DAYZPB2=fluxo setup=configura%C3%A7%C3%A3o h_01H9G0W21S6Z0A5QXC52KSYVQS=configura%C3%A7%C3%A3o data-availability=disponibilidade-de-dados h_01H9G0W21S7KVJ2Z5DRPCHZF4Z=disponibilidade-de-dados additional-information=informa%C3%A7%C3%B5es-adicionais h_01H9G0W21SERW2HC44KD77FNCG=informa%C3%A7%C3%B5es-adicionais" />
