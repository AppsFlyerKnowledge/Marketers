---
title: Validação de compras e assinaturas - Visão geral
metadata:
  keywords:
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2025-12-20T16:30:47Z'
  edited_at: '2026-09-28T00:00:54Z'
  id: 42120228484241
  locale: pt
  section: Purchase and subscription validation
  section_id: 42227328788241
  url: https://support.appsflyer.com/hc/pt/articles/42120228484241
---
> **At a glance:** Entenda como a AppsFlyer valida compras e assinaturas e compare as duas soluções disponíveis: validação de recibos e receita da loja do ROI360.

<div id="about-purchase-and-subscription-validation" />

## Sobre a validação de compras e assinaturas

A validação de compras e assinaturas é fundamental para garantir a precisão e a confiabilidade dos seus dados de receita. Quando os usuários fazem compras no seu aplicativo, seja uma compra avulsa ou uma assinatura, validar essas transações com as lojas de aplicativos (Apple App Store e Google Play) garante que apenas transações legítimas e pagas sejam mensuradas e atribuídas.

A AppsFlyer oferece duas soluções que validam e mensuram compras no aplicativo e receita de assinaturas: Validação de recibos e receita da loja do ROI360.

Este artigo traz uma introdução geral de cada solução e [compara suas ofertas](#comparar-a-validação-de-recibos-e-a-receita-da-loja-do-roi360) para ajudá-lo a determinar qual é a opção certa para o seu aplicativo.

<div id="the-two-solutions-for-purchase-and-subscription-validation" />

## Duas soluções para validação de compras e assinaturas

<div id="receipt-validation" />

### Validação de recibos

A validação de recibos é nossa solução gratuita para iOS e Android. Ela garante que apenas transações reais sejam mensuradas. Isso é feito validando recibos diretamente com as lojas de aplicativos.

Com essa solução, o SDK da AppsFlyer integrado ao seu aplicativo fornece dados mínimos, como o product ID, purchase ID e tipo de compra. A AppsFlyer recupera os detalhes completos da receita a partir da resposta da loja. Isso inclui o valor da compra e a moeda. Esta solução não fornece cálculo de receita líquida, cobertura completa do funil de assinaturas, tratamento de reembolsos, mensuração completa de compras in-app nem detecção & desduplicação automatizadas de compras.

Use a validação de recibos para tomar decisões informadas e otimizar campanhas com base em dados de receita verificados.

Para mais informações, consulte:

* <Anchor target="_blank" href="/marketers/pt/docs/about-receipt-validation">Sobre a validação de recibos</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/set-up-receipt-validation">Configurando a validação de recibos</Anchor>

<div id="roi360-store-revenuepremium" />

### Receita da loja do ROI360 (Premium)

<div id="important" />

> 🚧 **Importante:**
>
> A receita da loja do ROI360 está disponível apenas para os clientes do plano premium. Para verificar seu plano ou uma atualização, entre em contato com seu Customer Success Manager (CSM).

A solução de receita da loja do ROI360 é um produto premium da AppsFlyer, que fornece uma mensuração completa e precisa da receita de assinaturas e compras in-app. Ela valida transações S2S com as lojas de aplicativos e retorna dados de receita verificados e enriquecidos.

Dentro desse fluxo de validação, a receita da loja do ROI360 faz a desduplicação, calcula a receita líquida após taxas e impostos da loja e oferece cobertura completa do ciclo de vida da assinatura, incluindo renovações, cancelamentos, reembolsos e upgrades. Ela também processa eventos de assinantes existentes e soluciona questões de pagamentos atrasados de lojas como o Google Play.

Essa é a solução ideal se você precisa de precisão total na receita, insights sobre o ciclo de vida da assinatura e suporte para modelos de negócios complexos.

Para mais informações, consulte:

* <Anchor target="_blank" href="/marketers/pt/docs/about-roi360-store-revenue">Sobre a receita da loja do ROI360</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-store-revenue">Configurar a receita da loja do ROI360</Anchor>

<div id="compare-receipt-validation-and-roi360-store-revenue" />

## Comparar a validação de recibos e a receita da loja do ROI360

Use as tabelas abaixo para determinar qual solução se adapta melhor às suas necessidades.

<Accordion title="Comparar recursos">

| **Características** | **Validação de recibos** | **Receita da loja do ROI360** Premium |
| --- | --- | --- |
| **Validação de recibos**  <br />Verifique compras in-app para filtrar transações fraudulentas. | ✔ | ✔ |
| **Detecção & desduplicação automatizadas de compras**  <br />Detecta automaticamente compras in-app (IAPs) e assinaturas, incluindo transações de assinantes existentes, e remove duplicatas para relatórios mais limpos. | ✖ | ✔ |
| **Reembolsos**  <br />Detecta reembolsos e os atribui à compra original para refletir a receita real. | ✖ | ✔<sup>*</sup> |
| **Mensuração completa de compras in-app**  <br />Gerencie o compartilhamento familiar e relate o resultado final de compras pendentes usando a confirmação da loja de aplicativos. | ✖ | ✔ |
| **Cobertura completa do funil de assinatura**  <br />Mensure renovações, atualizações e conversões para acessar o valor completo da sua base de assinantes. | ✖ | ✔ |
| **Cálculo da receita líquida**  <br />Calcula tanto a receita bruta quanto a líquida, deduzindo automaticamente as taxas e impostos da loja. | ✖ | ✔ |

<sup>*</sup> O tratamento de reembolsos **para compras in-app** está disponível apenas no plano ROI360 Advanced.

</Accordion>

<Accordion title="Comparar o suporte a eventos de compras in-app">

| **Tipo de correspondência do colaborador[n]** | **Validação de recibos** | **Receita da loja do ROI360** |
| --- | --- | --- |
| af\_compra | ✔ | ✔ |
| af\_purchase\_refund<sup>*</sup> | ✖ | ✔ |
| af\_purchase\_pending | ✖ | ✔ |
| af\_purchase\_canceled<sup>*</sup> | ✖ | ✔ |
| af\_purchase\_free | ✖ | ✔ |
| af\_purchase\_sandbox\_sdk | ✔ | ✔ |
| af\_purchase\_sandbox\_s2s<sup>*</sup> | ✖ | ✔ |

<sup>*</sup> Disponível somente para o ROI360 Advanced.

</Accordion>

<Accordion title="Comparar o suporte a eventos relacionados a assinaturas">

| **Tipo de correspondência do colaborador[n]** | **Validação de recibos** | **Receita da loja do ROI360** |
| --- | --- | --- |
| af\_ars\_trial\_started | ✔ | ✔ |
| af\_ars\_trial\_canceled | ✖ | ✔ |
| af\_ars\_trial\_churned | ✖ | ✔ |
| af\_ars\_trial\_converted | ✖ | ✔ |
| af\_ars\_subscription\_started | ✔ | ✔ |
| af\_ars\_subscription\_canceled | ✖ | ✔ |
| af\_ars\_subscription\_paused | ✖ | ✔ |
| af\_ars\_subscription\_resumed | ✖ | ✔ |
| af\_ars\_subscription\_churned | ✖ | ✔ |
| af\_ars\_subscription\_refunded | ✖ | ✔ |
| af\_ars\_subscription\_billing\_grace | ✖ | ✔ |
| af\_ars\_subscription\_renewed | ✖ | ✔ |
| af\_ars\_subscription\_xgraded | ✖ | ✔ |
| af\_ars\_existing\_subscriber | ✖ | ✔ |
| af\_ars\_sandbox\_sdk | ✔ | ✔ |
| af\_ars\_sandbox\_s2s | ✖ | ✔ |

</Accordion>

<div data-zendesk-anchors="about-purchase-validation=sobre-a-valida%C3%A7%C3%A3o-de-compras-e-assinaturas h_01KCY9DHB7PBM3CZS65WMHR8B5=sobre-a-valida%C3%A7%C3%A3o-de-compras-e-assinaturas appsflyer-solutions=duas-solu%C3%A7%C3%B5es-para-valida%C3%A7%C3%A3o-de-compras-e-assinaturas h_01KCY9DHB7XKWP0P8WMTSXVT4A=duas-solu%C3%A7%C3%B5es-para-valida%C3%A7%C3%A3o-de-compras-e-assinaturas receipt-validation=valida%C3%A7%C3%A3o-de-recibos h_01KCY9DHB7DC66Q3H9W9064CZY=valida%C3%A7%C3%A3o-de-recibos roi360-store-revenue=receita-da-loja-do-roi360-premium h_01KCY9DHB70VN27BYR3ZG0JD86=receita-da-loja-do-roi360-premium h_01KSAJM50XFXVQXZC59D1BE5XN=importante compare-receipt-validation-and-roi360-stores-revenue=comparar-a-valida%C3%A7%C3%A3o-de-recibos-e-a-receita-da-loja-do-roi360 h_01KCY9DHB7RJ89GB5CM29T2AK5=comparar-a-valida%C3%A7%C3%A3o-de-recibos-e-a-receita-da-loja-do-roi360" />
