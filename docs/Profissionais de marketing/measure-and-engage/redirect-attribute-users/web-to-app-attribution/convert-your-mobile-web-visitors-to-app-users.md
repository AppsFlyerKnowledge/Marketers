---
title: Converter visitantes da web mobile em usuários do seu app.
metadata:
  keywords:
    - OneLink
    - Advertisers
    - Smart Banner
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2019-03-19T08:54:10Z'
  edited_at: '2026-09-08T00:33:31Z'
  id: 360001237818
  locale: pt
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/pt/articles/360001237818
---
> **Visão geral:** use seu site para converter visitantes da web mobile em novos usuários para o seu aplicativo.

<div id="mobile-web-to-app-attribution-solutions" />

## Soluções de atribuição web-to-app mobile

![Web_para_aplicativo.png](https://files.readme.io/deb9ba0dfd18671666e9f06dc27440759844ea365988f80e05ce7ac2817a7299-46646996021777.png)

<div id="benefits-of-web-to-app-campaigns" />

### Vantagens das campanhas web-to-app

O uso de campanhas web-to-app te ajudam a:

* Converta visitantes da web mobile em usuários do aplicativo. [Consulte também instalações assistidas pela web.](/docs/convert-your-mobile-web-visitors-to-app-users#instalações-assistidas-pela-web)
* Usar páginas na web ou landing pages para ajudar seus usuários a entenderem melhor o seu produto/serviço antes de baixarem o aplicativo.
* Descobrir quais são as suas landing pages/páginas da web que geram mais ou menos conversões.
* Criar ofertas mais específicas para redirecionar seus usuários da web mobile, que também são usuários do seu aplicativo.
* Criar deep links que levam os usuários do site para uma página específica dentro do aplicativo.

<div id="attribution-solutions" />

### Soluções de atribuição

<Embed title="Converter visitantes da web mobile em usuários do seu app." typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/kv67fa3rvn" providerUrl="https://fast.wistia.com" />

Para usuários web-to-app mobile, como ocorrem dois cliques (o primeiro que direciona para a página da web e o segundo que direciona da página da web para a loja de aplicativos), a atribuição e o deep linking podem causar problemas. Os usuários que eventualmente fizerem o download do aplicativo podem ser atribuídos indevidamente ou atribuídos como orgânicos, mesmo que o primeiro clique venha de uma ad network, clique do Google ou canal de mídia próprio. 

A AppsFlyer fornece as seguintes soluções para uma atribuição web-to-app precisa:

<Anchor target="_blank" href="/marketers/pt/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banners</Anchor>:

* Adicione o SDK web do Smart Banner ao seu site e, em seguida, crie banners dinâmicos no dashboard da AppsFlyer.
* Quando um usuário clica em uma URL e é direcionado ao seu site mobile, um Smart Banner aparece com um CTA para o download do aplicativo na loja de aplicativos.
* A URL do Smart Banner é preenchida com base nos parâmetros/UTMs do link recebido, e é usada para atribuição.

O <Anchor target="_blank" href="/marketers/pt/docs/onelink-smart-script-overview">Smart Script do OneLink</Anchor>:

* Executa um script no seu site mobile.
* Quando um usuário clica em uma URL e é direcionado ao seu site mobile, ele acessa uma página com botões que o incentivam a fazer o download do seu aplicativo.
* O script na página da web gera dinamicamente os URLs de saída nesses botões com base na URL de entrada, que é usada para atribuição.
* Substitui o <Anchor target="_blank" href="/marketers/pt/docs/deprecated-mobile-landing-page-attribution-script">script</Anchor> anterior de atribuição da landing page mobile. Se você ainda estiver usando o script anterior, deve realizar a migração.

Ambas as soluções fazem a conexão entre as URLs de campanha recebidas em seu site e a URL de saída do OneLink, criada para a atribuição e o deep linking corretos dos usuários do site mobile.

A tabela a seguir compara as duas soluções para que você possa escolher e implementar a mais adequada às suas necessidades. **Observação**: você pode implementar ambas as soluções e usá-las em conjunto.

<div id="smart-banner-vs-onelink-smart-script" />

#### Smart Banner vs. Smart Script do OneLink

| Característica | Smart Banners | OneLink Smart Script |
| --- | --- | --- |
| Canais de mídia compatíveis | Todos os canais de mídia compatíveis:<ul><li>Links de entrada com parâmetros pid ou UTM (incluindo SRNs)</li><li>Visitantes orgânicos</li></ul> | Todos os canais de mídia compatíveis:<ul><li>Links de entrada (incluindo SRNs)</li><li>Visitantes orgânicos</li></ul> |
| Alterar parâmetros do link de atribuição | Mudança rápida no acesso ao dashboard/assistente da AppsFlyer. | Requer implementação do desenvolvedor no script, mas é totalmente flexível. |
| Usuários de desktop | Não compatível | Com suporte. |
| Configuração do profissional de marketing | Use o assistente para configurar os Smart Banners. | Avalie quais parâmetros e valores devem ser definidos nas URLs de entrada e saída (os valores padrão são fornecidos). |
| Configuração do desenvolvedor | <ul><li>Integre o web SDK.</li><li>Alternativamente, pode ser <Anchor target="_blank" href="/marketers/pt/docs/smart-banners-website-code-implementation-for-marketers">implementado pelo profissional de marketing</Anchor>.</li></ul> | <ul><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script-v2web-to-app-url-generator">Implemente o script</Anchor> que cria a URL de saída.</li><li>Alternativamente, pode ser implementado pelo profissional de marketing por meio de um <Anchor target="_blank" href="/marketers/pt/docs/set-up-smart-script-to-convert-web-visitors#configurar-o-smart-script">gerenciador de tags</Anchor>.</li></ul> |
| Configuração de campanha em andamento | Para ad networks de clique, configure o link da campanha web-to-app. | Siga as instruções por tipo de canal de mídia. |
| Disponibilidade | Disponível com um plano de assinatura pago. | Disponível com um plano de assinatura pago. |

**Observação:** Smart Banners e OneLink Smart Script estão disponíveis somente com <Anchor target="_blank" href="/marketers/pt/docs/account-management-plans-payments-and-billing#appsflyer-plans">planos de assinatura</Anchor> pagos elegíveis. Depende do plano da sua conta na AppsFlyer

<div id="web-assisted-installs" />

### Instalações assistidas pela web

As instalações assistidas pela web ocorrem quando os usuários baixam o seu aplicativo, mas não necessariamente por causa de uma campanha específica. Antes de fazerem o download do seu aplicativo, eles visitaram seu site por qualquer motivo, talvez dias ou semanas antes. Use <Anchor target="_blank" href="/marketers/pt/docs/people-based-attribution-pba-overview">PBA</Anchor> Web-Assisted Installs para ver um detalhamento geral desses *touchpoints* de assistência que eventualmente levam à instalação do aplicativo.  

<div id="web-to-app-solutions-vs-web-assisted-installs" />

#### Soluções web-to-app vs. instalações assistidas pela web

| Característica | Soluções web-to-app mobile | Instalações assistidas pela web (PBA) |
| --- | --- | --- |
| Objetivo | Fornecer ferramentas para executar campanhas projetadas para converter visitantes da web diretamente em usuários do aplicativo, ao mesmo tempo em que atribui o canal de mídia responsável pela visita na web. | Oferecer um detalhamento das instalações precedidas de visitas à web. |
| Fluxos | Fluxo direto da web para o download do aplicativo. | Fluxos diretos, diferidos ou desconexos. As instalações podem ser anteriores a uma visita na web (até 30 dias). |
| Dispositivos de usuário | Mesmo dispositivo | Mesmo ou entre diferentes dispositivos |

| Caraterística | Observações |
| --- | --- |
| Versão do SDK |  |
| Tipo de correspondência | `preload_rfr` |
| Painel de Visão geral | Dahsboard de Visão Geral Os engajamentos são considerados como cliques em relatórios e dashboards agregados. Eles são agregados no parceiro de preload (fonte de mídia) e nos níveis de campanha. |
| Relatório Retargeting | <ul><li>Os engajamentos estão disponíveis nos relatórios de cliques somente por meio do Data Locker.</li><li>Nos relatórios de instalação, os eventos de preload NÃO são encontrados na URL original devido às restrições de privacidade da Samsung.</li><li>Eles podem ser identificados no parâmetro `af_engagement_type` como `preload`.</li></ul> |

<div data-zendesk-anchors="mobile-webtoapp-attribution-solutions=solu%C3%A7%C3%B5es-de-atribui%C3%A7%C3%A3o-web-to-app-mobile h_01KFAFC9DFAES0JGPVCQQV3GAR=solu%C3%A7%C3%B5es-de-atribui%C3%A7%C3%A3o-web-to-app-mobile benefits-of-webtoapp-campaigns=vantagens-das-campanhas-web-to-app h_01KFAFC9DFJ7QWJ6JN60NKVPZ3=vantagens-das-campanhas-web-to-app attribution-solutions=solu%C3%A7%C3%B5es-de-atribui%C3%A7%C3%A3o h_01KFAFC9DFH4JH6DE4KZE424Q3=solu%C3%A7%C3%B5es-de-atribui%C3%A7%C3%A3o smart-banner-vs-onelink-smart-script=smart-banner-vs-smart-script-do-onelink h_01KFAFC9DFGCYRS1C5SVX1ZSCC=smart-banner-vs-smart-script-do-onelink webassisted-installs=instala%C3%A7%C3%B5es-assistidas-pela-web h_01KFAFC9DG4MCVQ5YRGVRQ6K5P=instala%C3%A7%C3%B5es-assistidas-pela-web webtoapp-solutions-vs-webassisted-installs=solu%C3%A7%C3%B5es-web-to-app-vs-instala%C3%A7%C3%B5es-assistidas-pela-web h_01KFAFC9DG4YJ55BYQH9TQ2YPQ=solu%C3%A7%C3%B5es-web-to-app-vs-instala%C3%A7%C3%B5es-assistidas-pela-web" />
