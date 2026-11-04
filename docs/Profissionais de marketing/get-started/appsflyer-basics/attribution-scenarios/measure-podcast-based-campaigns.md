---
title: Meça campanhas baseadas em podcasts
metadata:
  keywords:
    - Advertisers
    - Agencies
    - audio
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2019-12-22T15:49:12Z'
  edited_at: '2026-08-18T00:10:08Z'
  id: 360004494318
  locale: pt
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/pt/articles/360004494318
---
> **Em resumo:** Supere o desafio da atribuição de publicidade de apps mobile em podcasts usando uma das várias soluções da AppsFlyer.

<div id="podcast-attribution-methods" />

## Métodos de atribuição para podcasts

Os podcasts são uma fonte relativamente inexplorada de tráfego de usuários mobile. Os usuários de podcasts podem reagir favoravelmente a anúncios de app mobile, mas a atribuição é um desafio. Isso acontece porque os podcasts não têm uma interface visual que gere impressões ou cliques de usuários.

No entanto, há opções que contornam essas limitações para realizar a atribuição de podcasts com sucesso:

* Página de destino dedicada
* Disparo de um clique do OneLink a partir de um aplicativo de podcast dedicado

<div id="dedicated-landing-page" />

### Página de destino dedicada

Uma call-to-action (CTA) em podcast, quando anuncia um app mobile, geralmente envolve mencionar o nome do app para que os usuários possam procurá-lo.

* Em um cenário de página de destino dedicada, a CTA é um destino web específico em uma página de destino.
* Essa página inclui um elemento web (botão, banner etc.) com tecnologia OneLink. Para criar facilmente banners dinâmicos em páginas de destino sem programação, recomendamos usar <Anchor target="_blank" href="/marketers/pt/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banners</Anchor>.
* Os usuários que interagem com esse elemento e instalam o app mobile recebem atribuição de acordo com os parâmetros do OneLink.

<div id="example" />

> 📄 **Exemplo**
>
> Você decide promover seu aplicativo no podcast de Joe Rogan e usar uma página de destino dedicada.
>
> Joe fuma, fala sobre seu aplicativo e depois conclui com "acesse www.greatapp.com/joe e ganhe 25% de desconto".
>
> A página de destino tem um banner **Download do app** com uma URL do OneLink. A URL inclui o canal de mídia "podcast" (&pid=podcast) e o nome da campanha "joe" (&c=joe).
>
> Os usuários que clicam na URL do OneLink e instalam o app recebem atribuição na plataforma AppsFlyer ao canal de mídia "podcast" e à campanha "joe".

<div id="firing-onelink-click-from-a-podcast-app" />

### Disparo de clique do OneLink a partir de um aplicativo de podcast

Esse método supera a ausência de interface visual e permite a atribuição de usuários sem visitar uma página de destino dedicada.

* Em um cenário de disparo de clique do OneLink, o aplicativo de podcast dispara um clique na URL do OneLink (ou uma impressão) quando um usuário é exposto ao anúncio.
* Normalmente, isso ocorre no final de um anúncio, mas o momento pode ser diferente.
* Os usuários que instalam um app depois de ouvir um anúncio em podcast recebem atribuição de acordo com os parâmetros do OneLink.

<div id="example-1" />

> 📄 **Exemplo**
>
> Você decide promover seu aplicativo no podcast "Making history", que permite acionar o OneLink diretamente após os usuários ouvirem o anúncio.
>
> A URL do OneLink contém o Device ID, o canal de mídia "podcast" (&pid=podcast) e o nome da campanha "making history" (&c=making%20history).
>
> O anúncio menciona o nome do seu aplicativo várias vezes, mas sem uma URL específica. Ainda assim, no AppsFlyer, os usuários que instalam o aplicativo são atribuídos ao canal de mídia "podcast" e à campanha "making history".

<div id="who-gets-the-attribution" />

#### Quem recebe a atribuição?

No AppsFlyer, o canal de mídia "podcast" é considerado um canal de mídia personalizado, e não um parceiro integrado. No entanto, ao se integrar ao AppsFlyer, os proprietários de aplicativos de podcast podem receber postbacks de instalações atribuídas a eles. Os proprietários de aplicativos de podcast podem <Anchor target="_blank" href="https://www.appsflyer.com/get-started/partners">entrar em contato</Anchor> com o grupo de desenvolvimento de parceiros da AppsFlyer.

<div data-zendesk-anchors="podcast-attribution-methods=m%C3%A9todos-de-atribui%C3%A7%C3%A3o-para-podcasts 01JB9NB6DY4ZTS1VAK9S0QSM2R=m%C3%A9todos-de-atribui%C3%A7%C3%A3o-para-podcasts dedicated-landing-page=p%C3%A1gina-de-destino-dedicada 01JB9NB6E5BHETTEY7Q0WD8JXE=p%C3%A1gina-de-destino-dedicada 01JB9NB6E9DZXTJTGDPT6HA3FS=exemplo firing-onelink-click-from-a-podcast-app=disparo-de-clique-do-onelink-a-partir-de-um-aplicativo-de-podcast 01JB9NB6EANCCA0FG7ZQY48VSB=disparo-de-clique-do-onelink-a-partir-de-um-aplicativo-de-podcast 01JB9NB6EDW22XGAM2HCA3CY9Q=exemplo-1 who-gets-the-attribution=quem-recebe-a-atribui%C3%A7%C3%A3o 01JB9NB6EDFJ3YNP1JYKDGPHEX=quem-recebe-a-atribui%C3%A7%C3%A3o" />
