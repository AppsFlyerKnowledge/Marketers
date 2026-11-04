---
title: Sobre a validação de recibos
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
  created_at: '2025-12-21T14:32:24Z'
  edited_at: '2026-08-19T00:01:28Z'
  id: 42136725767569
  locale: pt
  section: Purchase and subscription validation
  section_id: 42227328788241
  url: https://support.appsflyer.com/hc/pt/articles/42136725767569
---
> **At a glance:** **Resumo:** Saiba como a validação de recibos mensura as receitas de assinaturas e compras in-app e as verifica junto às lojas de aplicativos, garantindo uma mensuração precisa.

Os anunciantes podem usar a validação de recibos para validar e mensurar compras e assinaturas realizadas dentro do aplicativo a partir da Play Store e da App Store.

Esse tipo de validação é gratuito para todos os planos de conta.

> 📘 **Note**
>
> Considere usar nossa solução premium de receitas da loja do ROI360 para aproveitar o cálculo da receita líquida, a cobertura completa do funil de assinatura, o processamento de reembolsos e a detecção e desduplicação de compras automáticas. Para obter mais informações e comparar as duas soluções, leia o artigo: <Anchor target="_blank" href="/marketers/pt/docs/purchase-and-subscription-validation-overview#duas-soluções-para-validação-de-compras-e-assinaturas">Duas soluções para compra e validação de assinaturas</Anchor>.

<div id="how-does-receipt-validation-work" />

## Como funciona a validação de recibos?

Este é o fluxo da validação de recibos:

1. O usuário realiza uma compra dentro do aplicativo.
2. A loja de aplicativos notifica o aplicativo sobre a compra bem-sucedida.
3. O desenvolvedor do aplicativo chama o método de validação de recibos do SDK: `validateAndLogInAppPurchase`
4. O SDK chama o serviço de validação da AppsFlyer.
5. A AppsFlyer valida a compra para garantir que ela não seja fraudulenta.
6. Após a validação bem-sucedida, a AppsFlyer registra a compra ou o evento de assinatura.
7. Se a validação do recibo falhar, o evento será exibido no <Anchor target="_blank" href="/marketers/pt/docs/protect360-raw-data-reports#blocked-inapp-events">relatório de dados brutos de eventos in-app bloqueados</Anchor> (disponível para assinantes do Protect360) e na <Anchor target="_blank" href="/marketers/pt/docs/testing-the-sdk-integration-for-marketers#view-live-events">página de visualização de eventos ao vivo</Anchor> com o parâmetro `af_validated` definido como `false`.
8. O serviço de validação da AppsFlyer envia a resposta para o SDK.
9. O SDK envia a resposta da validação para o aplicativo (sucesso ou falha).

<div id="activate-receipt-validation" />

## Ativando a validação de recibos

Para ativar a validação de recibos, siga estas etapas:

1. No AppsFlyer, no menu lateral, abra **Configurações** e, em **ROI360** selecione **Configurações de receita**.
2. Abra a aba **Compras e assinaturas**.
3. Embaixo de **1 Escolher o tipo de produto**, selecione **Validação de recibos**.
4. Clique em **Salvar e continuar** para configurar a validação de recibos.

<div id="set-up-receipt-validation" />

## Configurando a validação de recibos

Para obter mais informações, veja como <Anchor target="_blank" href="/marketers/pt/docs/set-up-receipt-validation">configurar a validação de recibos</Anchor><Anchor target="_blank" href="/marketers/pt/docs/set-up-receipt-validation#3-verifique-a-implementação-do-sdk">.</Anchor>

<div id="in-app-purchase-events-and-parameters-for-receipt-validation" />

## Eventos de compras in-app e parâmetros para a validação de recibos

Todos os eventos pré-definidos têm as mesmas propriedades:

* São processados como eventos S2S.
* Estão disponíveis nos dashboards e relatórios de dados brutos como eventos in-app orgânicos ou não orgânicos.
* Podem ser enviados por postbacks para parceiros.
* Podem ser usados no SKAN Conversion Studio.

**Os eventos registrados para compras dentro do aplicativo são:**

* `af_purchase` - Produção
* `af_purchase_sandbox_sdk` - Sandbox

**Eventos de assinatura:**

* `af_ars_trial_started` - Início da assinatura com período de avaliação.
* `af_ars_subscriptions_started` - Início da assinatura paga (sem período de avaliação), produção
* `af_ars_sandbox_sdk` - Início do período de avaliação ou da assinatura paga, sandbox

**O evento inclui os seguintes parâmetros pré-definidos:**

* `af_product_id`
* `af_transaction_id` (exclusivo para iOS)
* `af_purchase_token` (exclusivo para Android)
* `af_revenue` (para eventos de Sandbox - `af_sandbox_revenue`)
* `af_currency`
* `af_store` (app\_store / play\_store)
* `af_environment` (sandbox/produção)
* `af_validation_type` (receipt\_validation)

**Outros parâmetros personalizados:**

* Quaisquer outros parâmetros personalizados enviados ao chamar o SDK serão exibidos no campo`custom_data` dos relatórios de dados brutos

<div id="switch-from-roi360-store-revenue-to-receipt-validation" />

## Transição da receita da loja do ROI360 para a validação de recibos

Se você está usando a receita da loja do ROI360 e deseja mudar para a validação de recibos, siga estas etapas:

1. Na AppsFlyer, no menu lateral, abra <Image alt="settings-roi.png" src="https://files.readme.io/23e5d6ac29cfd14f1c34247e6a19cdb86a364c3dbe1122e5fde43bb27902b864-42137277590289.png" width="2.02%" /> **Configurações** e, em **ROI360**, selecione **Configurações de receita.**
2. Na aba **Compras e assinaturas**, confirme se o **Tipo de produto** está definido para **ROI360**.
3. Clique em <Image alt="Untitled 3.png" src="https://files.readme.io/c27f864253e6749f883047b4529ad292153500db5aebd452568a6aa04407472e-34623601366033.png" width="2.07%" />.
4. Você verá uma mensagem com os impactos da mudança para a validação de recibos:
   * Os recursos do ROI360, como atribuição de reembolso, mensuração de renovação da assinatura e cálculos de receita líquida, serão desativados.
   * A precisão dos dados pode diminuir.
   * O conector de compras não é compatível com a validação de recibos.
   * Somente o método `validateAndLogInAppPurchase` do SDK é compatível.
5. Consulte o quadro comparativo, se necessário, em **Ver comparação dos produtos**.
6. Se ainda quiser continuar, clique em **Trocar** para confirmar a mudança.
7. Depois disso, o **Tipo de produto** é atualizado para **Validação de recibos** e a tela exibe a configuração simplificada.
8. Você precisará validar novamente o item a seguir:
   * **Implementação do SDK** para o método validateAndLog

<div id="traits-and-limitations" />

## Características e limitações

| Caraterística | Observação |
| --- | --- |
| Lojas compatíveis | • Play Store  <br />• App Store  <br />• Para outras lojas (de terceiros), você deve enviar manualmente os eventos de compras in-app. |
| Aplicativos sandbox no iOS | Para aplicativos sandbox no iOS, ou seja, aplicativos que não estão disponíveis na App Store, a função “Validar a chave” sempre exibirá o status “inválido” |

<div data-zendesk-anchors="how-does-receipt-validation-work=como-funciona-a-valida%C3%A7%C3%A3o-de-recibos h_01KD0PBEK0M2NEZJ95QXBA1H3W=como-funciona-a-valida%C3%A7%C3%A3o-de-recibos enable-receipt-validation=ativando-a-valida%C3%A7%C3%A3o-de-recibos h_01KD0PBEK0BZNW8YP02EW0DHH4=ativando-a-valida%C3%A7%C3%A3o-de-recibos set-up-receipt-validation=configurando-a-valida%C3%A7%C3%A3o-de-recibos h_01KD0PBEK1GZSJQPTP0P2TJMNJ=configurando-a-valida%C3%A7%C3%A3o-de-recibos inapp-purchase-events-and-parameters-for-receipt-validation=eventos-de-compras-in-app-e-par%C3%A2metros-para-a-valida%C3%A7%C3%A3o-de-recibos h_01KD0PBEK1DVMRXR64EMSWT75W=eventos-de-compras-in-app-e-par%C3%A2metros-para-a-valida%C3%A7%C3%A3o-de-recibos switch-from-roi360-store-revenue-to-receipt-validation=transi%C3%A7%C3%A3o-da-receita-da-loja-do-roi360-para-a-valida%C3%A7%C3%A3o-de-recibos h_01KD0PBEK1AKE1XM2XVTCNTJ68=transi%C3%A7%C3%A3o-da-receita-da-loja-do-roi360-para-a-valida%C3%A7%C3%A3o-de-recibos traits-and-limitations=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01KD0PBEK1HQKTGM7JP2KYPJAR=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es" />
