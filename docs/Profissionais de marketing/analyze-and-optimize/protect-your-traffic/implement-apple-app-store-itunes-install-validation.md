---
title: >-
  Implementar a validação de instalações da loja de aplicativos da Apple
  (iTunes)
metadata:
  keywords:
    - Validation
    - iTunes
    - Apple
    - Store Install
    - Advertisers
    - app store
    - appstore
    - Marketers
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2017-07-02T08:36:31Z'
  edited_at: '2026-08-18T00:07:52Z'
  id: 115003285626
  locale: pt
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/pt/articles/115003285626
---
> **Em resumo:** Evite a atribuição de atividades fraudulentas usando o serviço de validação de instalações da Apple para qualquer instalação no iOS (tanto orgânica quanto não orgânica).

<div id="receipt-validation-flow" />

## Fluxo de validação de recibos

Este é o fluxo da validação de recibos:

1. O SDK da AppsFlyer coleta os dados do recibo de instalação da Apple e os envia com a mensagem de inicialização para os servidores da AppsFlyer.
2. Os servidores da AppsFlyer validam esses dados de recibo por meio do serviço de validação de instalações da Apple.
3. Se o serviço de validação de instalações da Apple responder com códigos de erro que indiquem que a instalação é inválida:
   * A instalação é rejeitada e não aparece no nosso dashboard
   * A ad network não recebe um postback nem uma chamada de API para a instalação invalidada
   * A instalação e todos os eventos in-app correspondentes são registrados nos Relatórios de dados brutos do Protect360: Instalações e eventos in-app bloqueados.

<div id="notes" />

> 📘 **Observações**
>
> * A versão do SDK iOS da AppsFlyer deve ser 6.9.2+
> * Dispositivos iOS com versão do iOS 7+ têm suporte para validação de instalações.
> * Há casos em que a Apple não fornece os dados do recibo de instalação e, nesse caso, a AppsFlyer considera essa uma instalação válida em termos de validação de instalações da loja de aplicativos. No entanto, o Protect360 pode bloquear essa instalação por outros motivos de fraude.

<div data-zendesk-anchors="receipt-validation-flow=fluxo-de-valida%C3%A7%C3%A3o-de-recibos h_01JR7ST09GNZ2NTMP8D2YQ1DCH=fluxo-de-valida%C3%A7%C3%A3o-de-recibos h_01JR7ST09G5QFHFTWK98NCJE97=observa%C3%A7%C3%B5es" />
