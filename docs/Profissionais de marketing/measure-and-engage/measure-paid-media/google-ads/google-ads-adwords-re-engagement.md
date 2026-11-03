---
title: Google Ads (AdWords) — reengajamento
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2022-01-20T09:55:51Z'
  edited_at: '2026-08-18T00:29:55Z'
  id: 4417296925073
  locale: pt
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/pt/articles/4417296925073
---
> **Resumo:** Mensure campanhas de retargeting do Google Ads.

## Campanhas de retargeting do Google Ads

Com a AppsFlyer, você pode mensurar os resultados das **campanhas de aplicativos do Google Ads para engajamento**.  
Na AppsFlyer, essas campanhas são chamadas de campanhas de <Anchor target="_blank" href="/marketers/pt/docs/retargeting-attribution-guide">retargeting</Anchor>. A AppsFlyer oferece suporte à mensuração de dados de custo, clique e impressão para campanhas de retargeting. Essa integração permite que você visualize e mensure o seu gasto com anúncios no Google Ads e, em seguida, calcule o eCPI e o ROI de suas campanhas do Google Ads.

Campanhas de retargeting visam usuários que já instalaram seu aplicativo anteriormente.

* Os engajamentos de retargeting feitos por usuários que ainda têm seu aplicativo instalado são chamados **reengajamentos**. Estes normalmente resultam em usuários com vínculos mais profundos.
* Os engajamentos de retargeting feitos por usuários que não têm seu aplicativo instalado são chamados de **reinstalações** ou **reatribuições**

Para mais informações, consulte a <Anchor target="_blank" href="https://support.google.com/google-ads/answer/9234180">documentação de suporte do Google Ads para engajamento</Anchor>.

## Como configurar campanhas de aplicativos do Google Ads para engajamento

Antes de começar, verifique <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7365001?hl=en">as instruções do Google sobre como compartilhar um link com outras contas do Google Ads</Anchor> para garantir que as suas campanhas de engajamento sejam devidamente mensuradas através do seu link ID existente.

Para avaliar o engajamento das campanhas de aplicativos do Google Ads, siga estas três etapas:

<div id="enabling-retargeting-in-app-settings" />

<Accordion title="Habilitar o retargeting nas configurações do aplicativo">

Para habilitar campanhas de retargeting de qualquer fonte de mídia, você precisa habilitá-la no nível do aplicativo. Se esta for a primeira campanha de retargeting para seu aplicativo, faça o seguinte:

1. Na AppsFlyer, no menu lateral, selecione **Configurações** > **Configurações do aplicativo**.
2. Role para baixo até o final.
3. Ative a **atribuição de reengajamento**.

</Accordion>

<div id="enable-google-ads-retargeting-in-appsflyer" />

<Accordion title="Habilite o retargeting do Google Ads na AppsFlyer">

* Siga o item 5 das <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">instruções</Anchor> para configurar o Google Ads na AppsFlyer.

</Accordion>

<div id="importing-session-start-conversions-in-google-ads" />

<Accordion title="Importar conversões de início de sessão no Google Ads">

Para registrar conversões para campanhas de reengajamento **no Google Ads**, é necessário importar o evento session\_start no Google Ads.

Esse evento aparece no Google Ads se pelo menos um usuário iniciar o aplicativo depois que você ativar o retargeting na AppsFlyer para o Google Ads. Apenas para ter certeza, inicie o aplicativo depois de ativar o retargeting.

Para saber como importar conversões no Google Ads, consulte <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">aqui</Anchor>.

> 📘 **Atenção**
>
> Ao contrário de todos os outros eventos, session\_start pode ser reivindicado pela API do Google Ads, mesmo que você não importe eventos de session\_start para o Google Ads a partir da AppsFlyer.
> No entanto, nesse caso, essas conversões ainda serão atribuídas na AppsFlyer. Isso **cria uma discrepância considerável entre seus dados na AppsFlyer e no Google Ads**. Além disso, isso **impede que o Google Ads otimize** a segmentação de usuários da sua campanha.

</Accordion>

<div id="setting-up-deep-linking-for-app-campaigns-for-engagement" />

<Accordion title="Configurar links diretos para campanhas de aplicativos para engajamento">

As campanhas de aplicativos do Google para engajamento exigem que você <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6310747?hl=en&ref_topic=3121770">use deep link para campanhas de reengajamento</Anchor>. Soluções de deep link de terceiros não podem ser usadas devido a uma incompatibilidade de domínio. Isso inclui o OneLink da AppsFlyer. Use seus próprios <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6046977?hl=en">links de aplicativos desenvolvidos internamente, links universais ou esquemas de URI personalizados</Anchor>.

Não há necessidade de acrescentar parâmetros adicionais ao link direto (is\_retargeting=true e pid=adwords não são necessários).

</Accordion>

## Remarketing dinâmico e campanhas de compras

A AppsFlyer é compatível com remarketing dinâmico para aplicativos e campanhas de compras. A plataforma AppsFlyer trata essas campanhas como qualquer outra campanha de reengajamento.

* Para saber mais sobre o remarketing dinâmico para aplicativos, clique <Anchor target="_blank" href="https://support.google.com/adwords/answer/7538938">aqui</Anchor>.
* Para saber mais sobre campanhas de compras, clique <Anchor target="_blank" href="https://support.google.com/google-ads/answer/2454022?hl=en">aqui</Anchor>.
* Para saber mais sobre o Google Ads para engajamento, clique <Anchor target="_blank" href="https://support.google.com/google-ads/answer/9234180">aqui</Anchor>.

### Suporte para campanhas não relacionadas a aplicativos (Demand Gen e SEM)

A AppsFlyer oferece suporte apenas para a mensuração de campanhas de reengajamento não relacionadas a aplicativos no Google, incluindo:

* Campanhas de Demand Gen
* Campanhas de Search Engine Marketing (SEM)

Na AppsFlyer, essas campanhas estão **prontas para uso** e não exigem:

* Rastreamento paralelo
* Implementação de Smart Script

**Limitações:**

* **Instalações** de campanhas de Demand Gen ou SEM não são atribuídas em nenhuma plataforma.

**Opt-out:** no momento, o Google não oferece suporte para opt-in ou opt-out na mensuração de campanhas não relacionadas a aplicativos (ao contrário de plataformas como TikTok e Meta).

> 📄 **Veja também**
>
> * Para considerações sobre o iOS 14, consulte <Anchor target="_blank" href="/marketers/pt/docs/get-skan-postback-data-from-google-ads">Interoperabilidade do Google Ads para SKAdNetwork com a AppsFlyer</Anchor>.

<div data-zendesk-anchors="google-ads-retargeting-campaigns=campanhas-de-retargeting-do-google-ads h_01HDP34BWZFG09ABN5NQB6EY32=campanhas-de-retargeting-do-google-ads setting-up-google-ads-app-campaigns-for-engagement=como-configurar-campanhas-de-aplicativos-do-google-ads-para-engajamento h_01HDP34BWZXXNZDE0SR4MXBC9V=como-configurar-campanhas-de-aplicativos-do-google-ads-para-engajamento h_01HDP34BWZNHY08NDX6YSE9CXR=enabling-retargeting-in-app-settings h_01HDP34BWZNNNT4HRMXJB2X3S2=enable-google-ads-retargeting-in-appsflyer h_01HDP34BWZ8MGJKEZFC77VYWNG=importing-session-start-conversions-in-google-ads h_01HDP34BWZHWVKKNB7CEHY73R0=aten%C3%A7%C3%A3o h_01HDP34BWZ64XG2G0PTH6XCCMG=setting-up-deep-linking-for-app-campaigns-for-engagement dynamic-remarketing-and-shopping-campaigns=remarketing-din%C3%A2mico-e-campanhas-de-compras h_01HDP34BWZ990SD3B1C5DZRESK=remarketing-din%C3%A2mico-e-campanhas-de-compras h_google-non-app-campaign-support=suporte-para-campanhas-n%C3%A3o-relacionadas-a-aplicativos-demand-gen-e-sem support-for-nonapp-campaigns-demand-gen-and-sem=suporte-para-campanhas-n%C3%A3o-relacionadas-a-aplicativos-demand-gen-e-sem h_01HDP2XBSEJVQ5G0MD0V5R05CM=veja-tamb%C3%A9m" />
