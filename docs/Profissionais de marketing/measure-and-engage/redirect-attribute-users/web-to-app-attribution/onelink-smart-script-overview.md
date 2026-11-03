---
title: Entenda os recursos do OneLink Smart Script
metadata:
  keywords:
    - OneLink
    - Adwords
    - Advertisers
    - referral
    - referal
    - landing
    - redirect
    - gclid
    - facebook
    - landing page
    - Developers
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2018-12-12T16:32:47Z'
  edited_at: '2026-08-18T00:36:06Z'
  id: 360000677217
  locale: pt
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/pt/articles/360000677217
---
> **Visão Geral:** use o OneLink Smart Script para converter e atribuir os visitantes do seu site mobile, provenientes de qualquer fonte, em usuários do app mobile.

![7901_Smart_Script_flow_1920x1080_2__1_.png](https://files.readme.io/5181971c27e89974a86afeb83f48eb5c127b64765334bc3b5644ed47adb974e8-30193884510225.png)

## Sobre o OneLink Smart Script

Os usuários chegam ao seu site mobile antes de chegar à página de sua loja de aplicativos, seja organicamente, ou após se engajarem com campanhas publicitárias. Para isso, são necessários dois cliques:

* Direto para a página web
* Direto da página da web para a loja de aplicativos

Nesse cenário, a atribuição e o deep linking podem ser um desafio. Instalações feitas por novos usuários podem ser atribuídas de forma indevida, ou atribuídas como orgânicas. Isso pode ocorrer mesmo que o primeiro clique venha de uma ad network, clique no Google ou de um canal de mídia próprio.

O OneLink Smart Script resolve esses problemas, pois ele:

* Usa as URLs de entrada que levam à página web para gerar dinamicamente URLs longas de saída exclusivas que levam à loja de aplicativos.
* Fornece atribuição precisa de web-to-app para todos os canais de mídia, incluindo ad networks, SRNs, cliques do Google e mídias próprias.
* Pode ser usado para deep linking.
* Funciona perfeitamente em qualquer página da web ou landing page.
* Não requer o uso de Smart Banners.   
  **Atenção**: os Smart Banners podem ser uma ótima ferramenta de conversão para muitas verticais e não requerem a ajuda de um desenvolvedor para sua configuração. No entanto, eles adicionam um passo adicional, o banner, à jornada do usuário.
* Pode ser criado pelo profissional de marketing no Google Tag Manager.

Existem duas versões do OneLink Smart Script:

<Anchor target="_blank" href="/marketers/pt/docs/set-up-smart-script-to-convert-web-visitors">**OneLink Smart Script V2 (recomendado)**</Anchor>: Se você estiver configurando o OneLink Smart Script pela primeira vez, essa é a versão ideal. Ele pode ser configurado na interface da AppsFlyer, o trabalho de desenvolvimento é mais fácil, e também pode ser configurado usando o Google Tag Manager.

<Anchor target="_blank" href="/marketers/pt/docs/legacy-onelink-smart-script-v1-setup">**OneLink Smart Script V1 (antigo)**</Anchor>: Se você já tiver o Onelink Smart Script configurado, use a documentação dessa versão para manter e editar este script. **Atenção**: embora não seja obrigatório, considere migrar para a V2. 

> 📘 **Nota**
>
> Não tem certeza se o OneLink Smart Script é a solução certa para você? <Anchor target="_blank" href="/marketers/pt/docs/convert-your-mobile-web-visitors-to-app-users">Compare</Anchor> o OneLink Smart Script com outras soluções web-to-app da AppsFlyer.

### Exemplos

Os exemplos dessa seção mostram como o OneLink Smart Script é usado para gerar URLs de saída do OneLink que fornecem uma atribuição precisa, ou uma funcionalidade de deep linking. Para tipos de campanha com canais de mídia específicas, veja <Anchor target="_blank" href="/marketers/pt/docs/set-up-smart-script-to-convert-web-visitors#casos-de-uso">Casos de uso</Anchor>.

<div id="attribution" />

<Accordion title="Atribuição">

Mark é o profissional de marketing de uma rede de hotéis. Emma recebe um e-mail com uma sugestão de férias em um hotel em Orlando, na Flórida. O e-mail mostra esse link: https://hotel.me/pid=email&c=orlando

O link redireciona os usuários para o site mobile do hotel. Lá, os usuários são convidados a baixar o aplicativo mobile do hotel. O OneLink Smart Script gera automaticamente uma URL que contém os mesmos parâmetros **pid** e **c** do link original no e-mail. Esse é o link: https://hotel.onelink.me/Ac4G?pid=email&c=orlando

Quando os usuários clicam nos botões do site mobile para fazer o download do app, a instalação é atribuída à campanha de e-mail "Orlando" do Mark.

</Accordion>

<div id="deep-linking" />

<Accordion title="Deep linking">

Emma recebe um e-mail com uma sugestão de férias em um hotel em Orlando, na Flórida.

O e-mail mostra esse link: https://hotel.me?type=email&campaign=Florida&city=orlando

Quando ela clica no link, ele a redireciona para o site mobile do hotel. Lá, ela é convidada a baixar o aplicativo mobile do hotel. O OneLink Smart Script gera automaticamente uma URL que contém os mesmos parâmetros **pid** e **c** do link original no e-mail. Esse é o link: https://hotel.onelink.me/Ac4G?pid=email&c=Florida&deep_link_value=orlando

**Quando Emma clica nos botões do site mobile, ela é redirecionada para a loja de aplicativos. Ao fazer o download e abrir o app, ela é enviada através do deep link para a página de férias em Orlando.**

> 📘 **Nota**
>
> O deep linking segue as configurações do aplicativo implementadas pelos desenvolvedores do aplicativo. <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#crie-um-link-do-onelink">Saiba mais</Anchor>.

</Accordion>

<div data-zendesk-anchors="about-onelink-smart-script=sobre-o-onelink-smart-script h_01HE7RW9G26CNME9TP350GFGS4=sobre-o-onelink-smart-script h_01HE7RW9G2BV2NFJ0YZ9QKAA2V=nota examples=exemplos h_01HE7RW9G2WBZ1A0RS66CJ7BNH=exemplos h_01HE7RW9G24Y604NTZFGKJJXSS=attribution h_01HE7RW9G2ZDDWE1M1B2G175ZF=deep-linking h_01HE7RW9G3W5GKQ2CD2BZW8YAW=nota-1" />
