---
title: '[WIP] Sobre a atribuição de pesquisa orgânica e de respostas orgânicas de IA'
deprecated: false
hidden: false
metadata:
  keywords:
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - Marketers
  created_at: '2026-11-01T17:06:19Z'
  edited_at: '2026-11-02T13:24:22Z'
  id: 52556274395537
  locale: pt
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/pt/articles/52556274395537
---
> **At a glance:** Use a atribuição da pesquisa orgânica (SEO) e das respostas orgânicas de IA (AEO) para ver quais mecanismos de busca e mecanismos de respostas de IA enviam tráfego não pago para o seu site e aplicativo. Atribua a elas as conversões na web, as instalações do aplicativo e os reengajamentos no aplicativo.

<div id="about-seo-and-aeo-attribution" />

## Sobre a atribuição de SEO e AEO

Um usuário pesquisa no Google ou faz uma pergunta ao ChatGPT e depois clica em um resultado que leva ao seu site. A AppsFlyer atribui ao mecanismo de busca ou mecanismo de respostas de IA as visitas e conversões no seu site, as instalações do aplicativo e as aberturas do aplicativo.

<div id="supported-user-journeys" />

## Jornadas do usuário compatíveis

Cada jornada começa quando um usuário pesquisa em um mecanismo de busca compatível ou faz uma pergunta a um mecanismo de respostas de IA compatível. Se a resposta incluir um link não pago e o usuário clicar nele, uma das três jornadas a seguir acontece:

| Jornada | O que a AppsFlyer mede | Implementação necessária |
| --- | --- | --- |
| O usuário acessa o seu site | Visitas à web e conversões na web, como cadastros e compras | SDK de atribuição web da AppsFlyer ou integração server-to-server (S2S) |
| O usuário acessa o seu site e depois toca em um botão de download que leva à loja de aplicativos | Instalações de aplicativos | SDK mobile da AppsFlyer e Smart Script versão 2.10.3 ou posterior, com **Canal de mídia para instalações orgânicas de pesquisa** ativado |
| O usuário acessa o seu site e é direcionado diretamente para o aplicativo já instalado | Reengajamentos no aplicativo (aberturas do aplicativo) | SDK da AppsFlyer para Android e iOS versão 6.12.1 ou posterior, além de Android App Links e iOS Universal Links |

<div id="use-case-1-web-measurement" />

## Caso de uso 1: Mensuração web

Atribua as visitas ao site e as conversões ao mecanismo de busca ou mecanismo de respostas de IA de onde o usuário veio.

**Pré-requisitos:**

* SDK de atribuição web da AppsFlyer ou integração server-to-server (S2S). Saiba mais em <Anchor target="_blank" href="/marketers/pt/docs/web-performance-measurement-overview">Mensuração de performance web - Visão geral</Anchor>.

**Como funciona**

1. Um usuário clica em um resultado de busca não pago ou em um link de resposta de IA e acessa o seu site.
2. O SDK de atribuição web ou a integração S2S lê o referrer da web, o campo que mostra de onde o usuário veio. A AppsFlyer atribui a visita à web ao canal de mídia de SEO ou AEO correspondente.
3. Se o usuário depois concluir uma ação relevante, como se cadastrar ou fazer uma compra, a AppsFlyer atribuirá o evento àquele mecanismo de busca ou mecanismo de respostas com IA.

<Image alt="Google Chrome 2026-11-01 19.17.00.png" src="https://files.readme.io/62c5484c5da854dda37a25e681befe49d9f42ae03d2124f7eff513eb7a3c6630-52588347122577.png" width="2266px" />

Saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/about-traffic-source-resolution#etapa-2-identificação-de-fontes-de-mídia">resolução da fonte de tráfego</Anchor>.

<div id="use-case-2-app-install-measurement" />

## Caso de uso 2: Mensuração de instalação do aplicativo

Atribua instalações do aplicativo ao mecanismo de busca ou mecanismo de respostas com IA que levou o usuário ao seu site.

**Pré-requisitos:**

* SDK mobile da AppsFlyer
* AppsFlyer Smart Script versão 2.10.3 ou superior, com **fonte de mídia para instalações de pesquisa orgânica** ativada

**Como funciona**

1. Um usuário clica em um resultado de pesquisa não pago ou em um link de resposta de IA e acessa seu site.
2. A página mostra um botão de download com Smart Script por trás dele. O usuário não tem seu aplicativo instalado, então o botão o direciona para a loja de aplicativos.
3. O Smart Script cria um link de atribuição da AppsFlyer. Seu canal de mídia (`pid`) se baseia no referrer da web, ou seja, a página de onde o usuário veio. Por exemplo, um usuário vem de google.com, e a visita não tem indicadores pagos (`pid`, parâmetros UTM, `gclid`, `gbraid` ou `wbraid`). O Smart Script pode então definir `pid=google_organic_seo`.
4. O usuário instala o aplicativo e o abre pela primeira vez. A AppsFlyer pode atribuir a instalação àquele clique e dar crédito ao mecanismo de pesquisa ou ao mecanismo de respostas de IA que enviou o usuário ao seu site.

<Image alt="Google Chrome 2026-11-01 19.18.06.png" src="https://files.readme.io/8247f06616323e07fe6c4d00bca81ac965b6955ef46f2d8554c245ade866b70a-52588347123601.png" width="2250px" />

Saiba mais sobre como <Anchor target="_blank" href="/marketers/pt/docs/set-up-smart-script-to-convert-web-visitors#seo-referrer-mapping">configurar o Smart Script para converter visitantes da web</Anchor>.

<div id="use-case-3-app-re-engagement-measurement" />

## Caso de uso 3: mensuração de reengajamento no aplicativo

Atribua aberturas do aplicativo feitas por usuários que já têm seu aplicativo instalado.

**Pré-requisitos:**

* SDK da AppsFlyer para Android e iOS versão 6.12.1 ou superior
* Conteúdo do site mapeado para o conteúdo do aplicativo usando Android App Links e iOS Universal Links

**Como funciona**

1. Um usuário clica em um resultado de pesquisa não pago ou em um link de resposta de IA.
2. O conteúdo do seu site está mapeado para o seu aplicativo, e o usuário tem o aplicativo instalado. O link abre o aplicativo diretamente no conteúdo relevante.
3. O aplicativo é aberto por meio do deep linking. O referrer da web, a página de onde o usuário veio, é enviado à AppsFlyer. A AppsFlyer o usa para atribuir a abertura do aplicativo ao mecanismo de pesquisa ou mecanismo de respostas de IA correspondente.

<Image alt="Google Chrome 2026-11-01 19.18.53.png" src="https://files.readme.io/28b9c4eddb17c2eb6a63ad1c52158b03200bb45bd079d969e72652c94ed6614a-52588347124113.png" width="2227px" />

Saiba mais sobre como <Anchor target="_blank" href="/marketers/pt/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">configurar a atribuição de reengajamento para pesquisa orgânica (SEO) e respostas orgânicas de IA (AEO)</Anchor>.

<div id="data-availability" />

## Disponibilidade de dados

O tráfego de SEO e AEO aparece na AppsFlyer da seguinte forma:

* **Dashboards e relatórios:** Os mecanismos de pesquisa aparecem como `<search engine>_organic_seo`, por exemplo `google_organic_seo`. Os mecanismos de resposta de IA aparecem como `<AI engine>_organic_aeo`, por exemplo, `chatgpt_organic_aeo`.
* **Relatórios de dados brutos:** O campo `channel` é `seo` para o tráfego de mecanismos de busca e `aeo` para o tráfego de mecanismos de resposta de IA.

<div id="supported-search-engines-and-ai-answer-engines" />

## Mecanismos de busca e mecanismos de resposta de IA compatíveis

A AppsFlyer atribui tráfego dos seguintes mecanismos.

**Mecanismos de busca:** Google, Bing, Yahoo, Ask, DuckDuckGo, Yandex, Naver, Daum, Baidu, Ecosia, Coccoc, Sogou e Yahoo Japão.

**Mecanismos de resposta de IA:** ChatGPT, Claude, Perplexity, Manus, Copilot, Gemini, Grok e DeepSeek.

<div id="faq" />

## Perguntas frequentes

<div id="is-there-an-additional-fee-for-seo-and-aeo-attribution" />

### Há uma taxa adicional para a atribuição de SEO e AEO?

Sem. Isso está incluído na sua assinatura. As conversões orgânicas contam para o seu pacote da mesma forma que as conversões não orgânicas.

<div id="can-i-customize-the-seo-or-aeo-media-source-name" />

### Posso personalizar o nome do canal de mídia de SEO ou AEO?

Sem. A AppsFlyer define o nome do canal de mídia.

<div id="does-appsflyer-attribute-an-install-when-the-user-taps-an-install-button-shown-in-the-search-results" />

### A AppsFlyer atribui uma instalação quando o usuário toca em um botão de instalação exibido nos resultados de busca?

Sem. Nesse fluxo, a AppsFlyer não pode coletar as informações necessárias para atribuição.

<div id="is-keyword-search-term-or-prompt-data-available" />

### Os dados de palavra-chave, termo de busca ou prompt estão disponíveis?

Sem. O referrer da web não inclui essas informações.

<div id="see-also" />

## Consulte também

* <Anchor target="_blank" href="/marketers/pt/docs/about-traffic-source-resolution">Sobre a identificação de fontes de tráfego</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/set-up-smart-script-to-convert-web-visitors">Configure o Smart Script para converter visitantes da web</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">Configurar a atribuição de reengajamento para busca orgânica (SEO) e respostas orgânicas de IA (AEO)</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model">Modelo de atribuição da AppsFlyer</Anchor>

<div data-zendesk-anchors="h_01M6C15DBDG1JVJ11WZ2ZB5A0R=sobre-a-atribui%C3%A7%C3%A3o-de-seo-e-aeo h_01M6C15DBDFD0H52Y2V2X9J89K=jornadas-do-usu%C3%A1rio-compat%C3%ADveis h_01M6C15DBDKJH8NN771ED3ZWVX=caso-de-uso-1-mensura%C3%A7%C3%A3o-web h_01M6C15DBDY5Y4KM23NBYN12RH=caso-de-uso-2-mensura%C3%A7%C3%A3o-de-instala%C3%A7%C3%A3o-do-aplicativo h_01M6C15DBDK3HC4SD9X9V7BGWD=caso-de-uso-3-mensura%C3%A7%C3%A3o-de-reengajamento-no-aplicativo h_01M6C15DBDSSBM7JK28KT01EA9=disponibilidade-de-dados h_01M6C15DBDQSE84ZGBJ7EBHR99=mecanismos-de-busca-e-mecanismos-de-resposta-de-ia-compat%C3%ADveis h_01M6C15DBDFQ4R4CE8021ANQ8Z=perguntas-frequentes h_01M6C15DBDP74VR7JTPMMDP91H=h%C3%A1-uma-taxa-adicional-para-a-atribui%C3%A7%C3%A3o-de-seo-e-aeo h_01M6C15DBDSVC2E5HTRPJ27PM2=posso-personalizar-o-nome-do-canal-de-m%C3%ADdia-de-seo-ou-aeo h_01M6C15DBD6Q000S8S8VZ2PEK9=a-appsflyer-atribui-uma-instala%C3%A7%C3%A3o-quando-o-usu%C3%A1rio-toca-em-um-bot%C3%A3o-de-instala%C3%A7%C3%A3o-exibido-nos-resultados-de-busca h_01M6C15DBDQ2JPM01NX82N110A=os-dados-de-palavra-chave-termo-de-busca-ou-prompt-est%C3%A3o-dispon%C3%ADveis h_01M6C15DBD6442ATGZVZNZKGJ9=consulte-tamb%C3%A9m" />
