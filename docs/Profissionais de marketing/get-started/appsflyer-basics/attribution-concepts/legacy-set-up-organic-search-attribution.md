---
title: '[Legacy] Configurar a Atribuição de busca orgânica'
deprecated: true
metadata:
  keywords:
    - Android
    - organic
    - keyword
    - search
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2016-04-28T06:35:08Z'
  edited_at: '2026-08-18T00:08:53Z'
  id: 210195193
  locale: pt
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/pt/articles/210195193
---
> **Resumo:** Obtenha dados detalhados de atribuição de busca orgânica para otimizar as conversões orgânicas. <Anchor target="_blank" href="/marketers/pt/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">Veja nosso método atualizado de atribuição de busca orgânica</Anchor>.

<div id="important" />

> 🚧 **Importante!**
>
> Recomendamos implementar nosso <Anchor target="_blank" href="/marketers/pt/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">método atualizado de atribuição de busca orgânica</Anchor>.

<div id="organic-search-attribution" />

## Atribuição de pesquisa orgânica

A atribuição de busca orgânica é uma solução de atribuição inovadora que permite que clientes da AppsFlyer atribuam à busca orgânica as aberturas do app mobile de usuários que já têm o seu aplicativo instalado.

Use a atribuição de busca orgânica para atribuir esses usuários existentes que reengajam com seu aplicativo após uma pesquisa orgânica na web.

<div id="flow" />

#### FLUXO

<Image align="center" alt="Organic_SEO_attribution_flow.png" src="https://files.readme.io/1772808df9d9e521204153d9f0689b3f9f156dd8c0ab8555673b1d321f28aece-15320495862545.png" />

1. Um usuário pesquisa um termo (por exemplo, “sapatos masculinos”) no mecanismo de busca do navegador mobile (Google, Bing etc.). O mecanismo de busca exibe vários resultados clicáveis.
2. Alguns desses resultados de pesquisa são mapeados pelo seu desenvolvedor web para abrir o app mobile usando Android App Links e iOS Universal Links. Se um usuário tiver o aplicativo instalado, quando clicar no resultado da pesquisa, o aplicativo será aberto (sem redirecionar para uma loja de aplicativos primeiro).
3. Ao abrir o aplicativo, a AppsFlyer coleta as informações necessárias e consegue atribuir a abertura do aplicativo ao canal de mídia configurado (por exemplo, search\_engine).
4. Se o usuário não tiver o aplicativo instalado, ele será enviado para uma landing page na web, onde você pode usar qualquer uma das várias soluções web-to-app da AppsFlyer (como Smart Banners, Smart Script ou QR codes) para redirecioná-los e atribui-los.

**Para configurar a atribuição**:

1. Forneça aos desenvolvedores de aplicativos Android e iOS do seu aplicativo o domínio associado ao seu aplicativo. No Android, isso significa o domínio com Android App Links configurados para abrir o aplicativo para usuários existentes. E, no iOS, isso significa que o domínio com Universal Links está configurado para abrir o aplicativo para usuários existentes.
2. Informe aos desenvolvedores qual valor usar para o parâmetro de canal de mídia (`pid`). Por exemplo: search\_engine.
3. Peça aos seus desenvolvedores para seguir as instruções de atribuição de busca orgânica para <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_organic_search_attr">Android</Anchor> e <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_organic_search_attr">iOS</Anchor>.  
   Todas as instalações de pesquisas orgânicas serão exibidas com o valor de canal de mídia que você escolheu. Por exemplo: search\_engine.

**Dica!** Saiba mais sobre a <Anchor target="_blank" href="https://gs.statcounter.com/search-engine-market-share">distribuição do uso de mecanismos de busca por geo</Anchor>

<div data-zendesk-anchors="organic-search-attribution=atribui%C3%A7%C3%A3o-de-pesquisa-org%C3%A2nica flow=fluxo" />
