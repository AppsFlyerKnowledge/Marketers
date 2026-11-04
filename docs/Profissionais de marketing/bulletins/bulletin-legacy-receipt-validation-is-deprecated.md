---
title: 'Boletim: a versão legada da validação de recibos está obsoleta'
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
  created_at: '2025-12-21T11:33:45Z'
  edited_at: '2026-10-20T03:54:27Z'
  id: 42133487071121
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/42133487071121
---
| Seção | Detalhes |
| --- | --- |
| **Novidades** | **Validação de recibos**. Uma solução gratuita que valida as compras com as lojas de aplicativos usando o novo método `validateAndLog` do SDK.<br /><br />O método obsoleto será removido completamente nas próximas versões do SDK. Aplicativos que fizerem upgrade para a v7.0.0 ou posterior não poderão chamar o método antigo.<br /><br />A AppsFlyer oferece duas alternativas:<ul><li>**Validação de recibos**, uma solução gratuita que valida compras com as lojas de aplicativos usando o novo método `validateAndLogInAppPurchase` (v2) do SDK.</li><li>**Receita da loja do ROI360**. Uma solução premium de mensuração de receita, que inclui rastreamento de reembolsos, visibilidade completa do ciclo da assinatura e cálculo de receita líquida.</li></ul> |
| **Data de início** | As datas a seguir se aplicam:<ul><li>Data da atualização: 24/12/2025</li><li>Data de descontinuação total: 7 de setembro de 2026</li></ul> |
| **O que você precisa saber** | <ul><li>**O onboarding agora é obrigatório.** Diferente do Legacy, a nova validação de recibos só funciona depois que o tipo de produto e as credenciais da loja forem configurados na AppsFlyer. Sem essa configuração, o SDK retorna um erro.</li><li>**A receita bruta substitui os valores de receita personalizados.** A nova validação de recibos registra a receita bruta retornada pela loja, não o valor que você informa na chamada do SDK. Se você informava antes um valor personalizado (por exemplo, o valor líquido após a dedução da taxa da loja), espere uma diferença nos dashboards e nos postbacks de parceiros após a migração. Para receita líquida, use ROI360 Store Revenue.</li><li>**Dashboards e postbacks usam apenas o preço e a moeda da resposta de validação da loja.** Diferente do Legacy, o novo `validateAndLogInAppPurchase` não aceita preço nem moeda na chamada do SDK. Esses valores são extraídos diretamente da resposta de validação da loja. Qualquer `af_revenue` que você informar como parâmetro adicional vai para o objeto `custom_data` do evento, mas não é usado em dashboards nem em postbacks.</li><li>**Novo parâmetro obrigatório:** `PurchaseType`. Informa ao SDK se a transação é uma compra avulsa ou uma assinatura.</li></ul> |
| **O que você precisa fazer** | Para migrar para uma das duas soluções (antes de 7 de setembro de 2026), execute um dos seguintes procedimentos:<ul><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-receipt-validation">Configurar a Validação de recibos</Anchor> (inclui uma seção para clientes que estão migrando do Legacy)</li><li><Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-store-revenue">Configurar a receita da loja do ROI360</Anchor></li></ul>Para mais informações, consulte:<ul><li><Anchor target="_blank" href="/marketers/pt/docs/purchase-and-subscription-validation-overview#comparar-a-validação-de-recibos-e-a-receita-da-loja-do-roi360">Uma comparação lado a lado entre a validação de recibos e o ROI360 Store Revenue</Anchor></li><li>As [Perguntas frequentes](#perguntas-frequentes) abaixo</li></ul> |

<div id="faq" />

## Perguntas frequentes

<div id="h_faq_01" />

<Accordion title="Como sei quais dos meus aplicativos ainda usam a validação de recibos Legacy?">

O Legacy não aparece como tipo de produto na página de configurações de receita, então você não consegue confirmar o uso do Legacy apenas pela interface. Use os métodos a seguir em conjunto:

* **Primeiro, examine os dados brutos.** Procure eventos `af_purchase` com `event_source: SDK` e `is_receipt_validated: true`. Esses são candidatos, mas chamadas `logEvent` podem produzir eventos semelhantes, então isso não é conclusivo por si só.
* **Confirme no código do SDK.** Se o seu aplicativo chamar `validateAndLogInAppPurchase` com a assinatura legada, ele estará no modo Legacy. A assinatura legada inclui:
  * **Android:** chave de licença, payload JSON, preço, moeda
  * **iOS:** ID do produto, preço, moeda, ID da transação
* **Entre em contato com seu CSM.** Eles podem confirmar quais dos seus aplicativos ainda estão no Legacy.

</Accordion>

<div id="h_faq_02" />

<Accordion title="O que exatamente acontece em 7 de setembro de 2026?">

O serviço de backend de validação de recibos do Legacy será desativado. A partir desse dia:

* O método legado `validateAndLogInAppPurchase` será considerado como obsoleto a partir das seguintes versões do SDK:
* Os eventos `af_purchase` validados e registrados por esse método não são mais registrados na AppsFlyer.
* Dashboards, dados brutos e postbacks de parceiros deixam de receber dados de compra do Legacy.

Para continuar capturando compras validadas, migre para uma das alternativas compatíveis antes de 7 de setembro de 2026.

</Accordion>

<div id="h_faq_03" />

<Accordion title="Ativar a nova validação de recibos afetará minhas versões ativas do aplicativo que ainda chamam o método legado?">

Sem. Os dois produtos funcionam em paralelo até 7 de setembro de 2026. Ativar a nova validação de recibos na AppsFlyer não afeta as versões do aplicativo que ainda chamam o método legado. Elas continuam funcionando como antes até a data de descontinuação.

</Accordion>

<div id="h_faq_04" />

<Accordion title="O que acontece com os usuários em versões antigas do aplicativo que nunca são atualizadas?">

Usuários em versões antigas do aplicativo continuam gerando eventos `af_purchase` validados até 7 de setembro de 2026. Para continuar recebendo dados de compras validadas, lance a versão atualizada do seu aplicativo com antecedência suficiente para alcançar a maior parte da sua base de usuários antes da descontinuação.

</Accordion>

<div id="h_faq_05" />

<Accordion title="Posso mudar da validação de recibos para o ROI360 Store Revenue mais tarde?">

sim, sim, Ambos os produtos usam o mesmo método do SDK `validateAndLogInAppPurchase` (v2), portanto mudar de Validação de recibos para Receita da loja do ROI360 não exige uma alteração no SDK nem o lançamento de uma nova versão do aplicativo. Para mudar, altere o **Tipo de produto** na página **Configurações de receita** e conclua a configuração adicional do ROI360 (notificações do servidor da App Store para iOS, RTDN do Google Play para Android). Veja <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-store-revenue#migrar-para-a-receita-da-loja-do-roi360-da-validação-de-recibos">Mudar para ROI360 Store Revenue da validação de recibos</Anchor>.

Se você quiser ir além e ativar a detecção automática de compras, a cobertura completa do ciclo de vida da assinatura (incluindo renovações, upgrades e assinantes existentes) e o tratamento de alterações no preço da assinatura, integre o componente SDK **Purchase Connector**. Essa é uma atualização do aplicativo, mas é opcional. O fluxo manual `validateAndLogInAppPurchase` (v2) funciona no ROI360 Store Revenue sem isso.

</Accordion>

<div id="h_faq_06" />

<Accordion title="Posso ignorar totalmente a validação de compras da AppsFlyer?">

sim, sim, Você pode reportar eventos de compra in-app com a API padrão `logEvent`. Mas você vai deixar de ter:

* Validação de recibos nas lojas de aplicativos, que filtra compras fraudulentas
* A flag `af_validated` nos eventos: definida como `true` quando a AppsFlyer verifica a compra com sucesso na loja e como `false` quando a verificação falha. Sem validação, essa flag não aparece.
* Postbacks de receita precisos para seus parceiros de UA. Sem validação, qualquer `af_revenue` que você enviar será registrado e enviado às networks como está, sem confirmação de que a compra realmente ocorreu

Por esses motivos, a AppsFlyer recomenda usar a validação de recibos ou o ROI360 Store Revenue, em vez de ignorar totalmente a validação.

</Accordion>

<div id="h_faq_07" />

<Accordion title="O que acontece se o serviço de validação da Apple ou do Google ficar indisponível?">

Depende de qual produto você usa:

* **Validação de recibos:** o callback do SDK retorna um código de erro. Seu aplicativo precisa lidar com a falha e implementar a própria lógica de nova tentativa.
* **ROI360 Store Revenue:** a AppsFlyer tenta validar novamente automaticamente assim que o serviço da loja se recupera e regenera os eventos perdidos durante a janela de indisponibilidade.

</Accordion>

<div id="h_faq_08" />

<Accordion title="Por que a receita no meu dashboard mudou após a migração?">

A fonte da receita mudou. O modelo legado usava o valor que você enviava na chamada do SDK. A nova validação de recibos usa a receita bruta retornada pela loja. Se antes você enviava um valor personalizado, por exemplo, a receita líquida após a dedução da taxa da loja, seus dashboards e postbacks de parceiros vão refletir um número diferente após a migração.

Se você precisa de receita líquida, use **ROI360 Store Revenue**. Ele registra a receita bruta e a líquida (bruta menos taxas e impostos da loja).

</Accordion>

<div id="h_faq_09" />

<Accordion title="O que acontece com meu valor personalizado de af_revenue ?">

Se você ainda enviar o valor de `af_revenue`, ele será preservado no evento dentro do objeto `custom_data`. Dashboards e postbacks de parceiros usam o valor bruto da resposta da loja, não o seu valor personalizado.

</Accordion>

<div id="h_faq_10" />

<Accordion title="Meus parceiros verão a nova receita bruta nos postbacks?">

sim, sim, Após a migração, os postbacks de `af_purchase` passam a incluir a receita bruta da loja. Se você antes passava um valor personalizado em Legacy, seus parceiros verão um número diferente. Informe seus parceiros de UA antes de implementar a migração, especialmente os parceiros que usam dados de receita para otimização de campanha.

</Accordion>

<div id="h_faq_11" />

<Accordion title="Como os nomes dos eventos mudam após a migração?">

O Legacy gerava um único evento `af_purchase` para todos os tipos de transação. A nova validação de recibos usa nomes de eventos distintos:

* Compra única: `af_purchase`
* Início do teste: `af_ars_trial_started`
* Início da assinatura: `af_ars_subscription_started`
* Compra em sandbox: `af_purchase_sandbox_sdk`
* Assinatura ou teste em sandbox: `af_ars_sandbox_sdk`

Os eventos completos do ciclo de vida da assinatura (renovações, cancelamentos, reembolsos, upgrades) estão disponíveis apenas no ROI360 Store Revenue. Para ver a lista completa de eventos, consulte <Anchor target="_blank" href="/marketers/pt/docs/about-receipt-validation">Sobre a validação de recibos</Anchor>.

</Accordion>

<div id="h_faq_12" />

<Accordion title="Posso usar a resposta de validação do SDK para controlar o acesso ao conteúdo comprado?">

A nova validação de recibos ainda retorna um resultado de validação para o callback do seu SDK, que você pode usar para controlar o acesso ao conteúdo comprado. O resultado é mais preciso porque depende dos mecanismos de validação mais recentes fornecidos pela Apple App Store e pelo Google Play, portanto o sinal que você recebe no callback é mais confiável.

</Accordion>

<div id="h_faq_13" />

<Accordion title="Como o novo método distingue assinaturas de compras únicas?">

O novo `validateAndLogInAppPurchase` exige um parâmetro obrigatório `PurchaseType`. Defina-o como `one-time` ou `subscription` com base no tipo de transação.

</Accordion>

<div id="h_faq_14" />

<Accordion title="A solução antiga de validação de recibos para compras dentro do aplicativo se tornou oficialmente obsoleta para todos os SDKs da AppsFlyer.">

Seu aplicativo integrou o novo método `validateAndLogInAppPurchase` (v2), mas o produto não está configurado no dashboard da AppsFlyer. Abra **Configurações > ROI360 > Configurações de receita > Compras & assinaturas**, selecione **Validação de recibos** ou **ROI360** e conclua as etapas de configuração.

</Accordion>

<div id="h_faq_15" />

<Accordion title="Por que minha nova versão do SDK registra apenas eventos de sandbox, e não af_purchase ?">

`af_purchase` é registrado apenas para transações de produção. As transações de sandbox são registradas como `af_purchase_sandbox_sdk`. Para produzir um evento `af_purchase` real, teste por meio de um pipeline de produção (sem TestFlight no iOS, sem Licensed Tester no Android).

</Accordion>

<div data-zendesk-anchors="faq=perguntas-frequentes how-do-i-know-which-apps-still-use-legacy=h_faq_01 what-happens-on-september-7-2026=h_faq_02 will-enabling-new-receipt-validation-affect-live-apps=h_faq_03 what-happens-to-users-on-old-app-versions=h_faq_04 can-i-switch-from-receipt-validation-to-roi360-later=h_faq_05 can-i-skip-appsflyer-purchase-validation-entirely=h_faq_06 what-happens-if-store-validation-service-has-outage=h_faq_07 why-did-my-dashboard-revenue-change-after-migration=h_faq_08 where-does-custom-af-revenue-go=h_faq_09 will-partners-see-new-gross-revenue-in-postbacks=h_faq_10 are-event-names-different-in-new-receipt-validation=h_faq_11 sdk-validation-response-for-content-gating=h_faq_12 do-i-need-to-change-anything-for-subscriptions-vs-one-time=h_faq_13 sdk-returning-purchase-validation-not-enabled=h_faq_14 new-sdk-build-only-logging-sandbox-events=h_faq_15" />
