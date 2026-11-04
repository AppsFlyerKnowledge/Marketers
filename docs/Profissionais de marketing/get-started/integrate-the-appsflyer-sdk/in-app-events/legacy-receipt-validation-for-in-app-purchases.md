---
title: '[Legado] Validação de recibo para compras in-app'
deprecated: true
metadata:
  keywords:
    - iOS
    - Android
    - Receipt
    - Validation
    - Receipt Validation
    - SDK
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2015-02-26T10:30:58Z'
  edited_at: '2026-08-18T00:13:41Z'
  id: 207032106
  locale: pt
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/pt/articles/207032106
---
<div id="important" />

> 🚧 **Importante!**
>
> Esse artigo traz informações sobre uma versão obsoleta da validação de recibos. Para obter mais informações, consulte o <Anchor target="_blank" href="/marketers/pt/docs/bulletin-legacy-receipt-validation-is-deprecated">Boletim: a Validação de recibos legada foi descontinuada</Anchor>

> **Resumo:** Implemente a validação de recibos para se proteger contra compras in-app fraudulentas feitas nas lojas de aplicativos do iOS e Android e garantir que uma compra in-app realmente ocorreu conforme relatado. **Observação**: Este é um recurso antigo. Saiba mais sobre o novo mecanismo de <Anchor target="_blank" href="/marketers/pt/docs/purchase-and-subscription-validation-overview">validação de compras in-app, totalmente automático e aprimorado</Anchor>.

<div id="receipt-validation-flow" />

## Fluxo de validação de recibos

Este é o fluxo da validação de recibos:

1. O usuário realiza uma compra dentro do aplicativo.
2. A loja de aplicativos notifica o aplicativo sobre a compra bem-sucedida.
3. O desenvolvedor do aplicativo chama a função SDK Receipt Validation.

   ```
   validateAndLogInAppPurchase
   ```
4. O SDK chama o serviço de validação da AppsFlyer.
5. A AppsFlyer valida a compra para garantir que ela não seja fraudulenta.
6. Caso ela verifique que a compra é verdadeira, a AppsFlyer cria internamente um evento af\_purchase comum. Caso contrário, o evento criado é marcado como fraudulento (disponível via Protect360).
7. O serviço de validação da AppsFlyer envia a resposta para o SDK.
8. O SDK envia a resposta da validação de recibos para o aplicativo (sucesso ou falha).  
   Se a validação de recibos falhar, o evento será exibido no <Anchor target="_blank" href="/marketers/pt/docs/protect360-raw-data-reports#inapp-level-blocked-reasons">blocked in-app events raw-data</Anchor> relatório (disponível para assinantes do Protect360).

Para detalhes sobre a implementação da validação de recibos, veja nossa documentação do SDK para desenvolvedores:

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-android#validating-purchases">com o Android</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-ios#purchase-validation-using-validateandloginapppurchase">/docs/ctv-pc-and-console-platform-attribution-concepts</Anchor>

**Atenção:**

* Para iOS aplicativos sandbox, ou seja, aplicativos que não estão disponíveis na App Store, a Validação de recibos requer <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/validate-and-log-purchase-ios#testing-purchase-validation-in-sandbox-mode">algum código adicional</Anchor>.
* Compras feitas no ambiente sandbox são registradas como eventos af\_purchase regulares, e sua receita é refletida nos dashboards e relatórios da AppsFlyer.
* O serviço de Validação de recibos da AppsFlyer é gratuito para todos os planos de conta.
* Para Android, a validação de recibos pode retornar um resultado `null` e considerar a validação como falha se o usuário final não tiver acesso à internet durante a compra.

<div id="important-1" />

> 🚧 **Importante!**
>
> Chamar `validateAndLogInAppPurchase` também gera um evento in-app **af\_purchase**. Assim sendo, não gere um evento af\_purchase ao validar. Fazer isso resulta em eventos de receita duplicados.

<div id="note" />

> 📘 **Nota**
>
> * *A* validação de recibos legada explicada aqui não é compatível com *StoreKit v2*. Para a versão atual, consulte Configure a integração com a loja de aplicativos do iOS.
> * A validação de recibos para compras in-app não é compatível para lojas de aplicativos não-nativas no Android.

<div data-zendesk-anchors="h_01KDJ7QZD8X692EVP1XXGV0KY4=importante receipt-validation-flow=fluxo-de-valida%C3%A7%C3%A3o-de-recibos 01JDSM0JDAQXH8QX8ZAXNB0ZMB=fluxo-de-valida%C3%A7%C3%A3o-de-recibos 01JDSM0JDT6Q3WYW9K484QHY2M=importante-1 01JDSM0JD90J3EDMVN6D6Z9J40=nota" />
