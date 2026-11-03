---
title: Sobre a receita da loja do ROI360
metadata:
  keywords:
    - Premium
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2025-12-21T16:34:39Z'
  edited_at: '2026-10-06T00:02:22Z'
  id: 42138855425297
  locale: pt
  section: Purchase and subscription validation
  section_id: 42227328788241
  url: https://support.appsflyer.com/hc/pt/articles/42138855425297
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Resumo:** Use a receita da loja do ROI360 para validar assinaturas e compras in-app, evitar duplicações e calcular a receita líquida.

> 🚧 **Importante!**
>
> A receita da loja do ROI360 está disponível apenas para os clientes do plano premium. Para verificar seu plano ou uma atualização, entre em contato com seu Customer Success Manager (CSM).

A receita da loja do ROI360 é a solução premium da AppsFlyer para uma mensuração completa e precisa das receitas de assinaturas e compras in-app. Com ela, você tem uma visão abrangente da jornada do cliente, permitindo a mensuração precisa do ROAS.

| Funcionalidade | Detalhes |
| --- | --- |
| Escopo da mensuração de receita | <ul><li>Receita de compras in-app de produtos e assinaturas gerenciadas por meio do App Store Connect (iOS) e do Google Play Console (Android)</li><li>Reembolsos</li><li>Receita de transações pendentes e adiadas (Android)</li><li>Eventos relacionados a assinaturas que ocorrem dentro e fora do aplicativo</li><li>Receita líquida, que inclui impostos e comissões da loja</li></ul> |
| Validação e precisão da receita | A solução impede que transações duplicadas sejam registradas. Isso também impede as duplicações devido ao Compartilhamento Familiar no iOS. Além disso, a receita da loja do ROI360 pode enviar os dados das transações da App Store diretamente para os anunciantes. |
| Fontes de dados | <ul><li>Purchase Connector do SDK da AppsFlyer para Android e iOS</li><li>Notificações do servidor da App Store</li><li>Notificações em Tempo Real do Google Play (RTDN)</li></ul> |
| Relatórios e disponibilidade de dados | Os dados de receita estão disponíveis nos dashboards e relatórios da AppsFlyer e também podem ser compartilhados com parceiros por meio de postbacks. |

> ❗️ **Aviso**
>
> Ao usar a receita da loja do ROI360, não envie eventos in-app de compras, pois isso resultará em relatórios de receita duplicados.

## Como funciona a receita da loja do ROI360?

1. Um usuário faz uma compra in-app ou uma assinatura automaticamente renovável.
2. O aplicativo faz uma transação na loja de aplicativos.
3. O Purchase Connector do SDK da AppsFlyer detecta automaticamente as compras e envia seus payloads para a AppsFlyer para validação e registro.
4. A AppsFlyer valida a compra com a loja relevante para garantir que ela não seja fraudulenta.
   * Após a validação bem-sucedida, a AppsFlyer registra a compra ou o evento da assinatura dentro do aplicativo.
   * Se a validação do recibo falhar, o evento será exibido no relatório de dados brutos de eventos in-app bloqueados (disponível para assinantes do Protect360) e na página de visualização de eventos ao vivo com o parâmetro `af_validated` = false.
5. A AppsFlyer transfere a resposta para o Purchase Connector do SDK, que transfere a resposta de validação de recebimento (sucesso ou falha) para o aplicativo.
6. Quaisquer notificações recebidas das lojas de aplicativos também são processadas pela lógica de negócios de receita de assinatura e compra da AppsFlyer.
   * As notificações sobre transações relatadas anteriormente via conector SDK são validadas e processadas, resultando na criação interna de um evento de compra ou ciclo de vida.
   * As notificações sobre transações desconhecidas são descartadas.
   * Para iOS, todas as notificações de servidor podem ser reencaminhadas para os seus próprios servidores.

## Ativar a receita da loja do ROI360

Para ativar a mensuração de receita da loja do ROI360, siga estas etapas:

1. Na AppsFlyer, no menu lateral, abra <Image alt="settings-roi.png" src="https://files.readme.io/23e5d6ac29cfd14f1c34247e6a19cdb86a364c3dbe1122e5fde43bb27902b864-42137277590289.png" width="2.17%" /> **Configurações** e, em **ROI360**, selecione **Configurações de receita.**
2. Abra a aba **Compras e assinaturas**.
3. Em **Escolher o tipo de produto**, selecione **ROI360**.
4. Clique em **Próximo** para continuar.

## Configurar a receita da loja do ROI360

Leia o artigo sobre como <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-store-revenue">configurar a receita da loja do ROI360</Anchor>

## Referência

As próximas seções explicam com mais detalhes os principais aspectos da mensuração de compras in-app (IAP) e das receitas de assinatura do ROI360. Isso inclui eventos e parâmetros para IAP e eventos de assinatura, receita líquida (que calcula a receita bruta em relação à receita líquida) e as características e limitações gerais da solução.

> 📘 **Nota**
>
> para enviar parâmetros personalizados adicionais com seus eventos in-app, configure uma **fonte de dados personalizada** no <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/purchase-connector">Purchase SDK Connector</Anchor>. Isso permite que você enriqueça eventos de compra e assinatura usando sua própria lógica de negócios e metadados.
> Esses parâmetros estarão disponíveis no campo `custom_data` do relatório de dados brutos.

<div id="iaprelated-events-and-parameters" />

<Accordion title="Eventos e parâmetros relacionados a IAP">

As seções seguintes mostram os eventos relacionados a compras in-app (IAPs) que a AppsFlyer mensura e os parâmetros que são registrados para cada evento. Consulte o [dicionário de parâmetros de eventos](#parameter-dictionary) para uma explicação detalhada dos parâmetros incluídos.

**Todos os eventos gerados têm as seguintes propriedades:**

* Eventos de servidor para servidor (S2S).
* Disponibilidade em relatórios de dados brutos (como eventos in-app orgânicos ou não orgânicos) e nos relatórios de Revenue ETL Stores.
* Envio aos parceiros por meio de postbacks.
* Compatibilidade com o SKAN Conversion Studio.

<div id="purchase-af_purchase" />

<Accordion title="Compra (af_purchase)">

**Descrição**

Registrado quando um usuário faz uma compra.

**Parâmetros**

* ativado
* customer\_user\_  
  id
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code
* af\_net\_revenue\_factors

</Accordion>

<div id="purchase-af_purchase_free" />

<Accordion title="Compra gratuita (af_purchase_free)">

**Descrição**

Registada quando um usuário faz uma compra que não tem valor de receita. Todos os parâmetros de receita apresentam 0.

**Parâmetros**

* ativado
* customer\_user\_  
  id
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code
* af\_net\_revenue\_factors

</Accordion>

<div id="purchase-canceled-af_purchase_canceled" />

<Accordion title="Compra cancelada (af_purchase_canceled)">

**Descrição**

Registrado quando um usuário cancela uma compra.

**Parâmetros**

* ativado
* customer\_user\_  
  id
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment

</Accordion>

<div id="purchase-pending-af_purchase_pending" />

<Accordion title="Compra pendente (af_purchase_pending)">

**Descrição**

Registrado quando um usuário faz uma compra, mas o pagamento ainda não foi processado.

**Parâmetros**

* ativado
* customer\_user\_  
  id
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment

</Accordion>

<div id="refund-af_purchase_refund" />

<Accordion title="Reembolso (af_purchase_refund)">

**Descrição**

Registrado quando uma compra é reembolsada.

**Parâmetros**

* ativado
* customer\_user\_  
  id
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_discount\_type
* event\_revenue\_usd
* event\_revenue (incluído no evento quando a receita é maior que zero)
* store\_commission
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_factors
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code

</Accordion>

<div id="test-purchase-af_purchase_sandbox_sdk" />

<Accordion title="Compra de teste (af_purchase_sandbox_sdk)">

**Descrição**

Registrado ao testar uma compra registrada por SDK em ambiente de área restrita.

**Parâmetros**

* ativado
* customer\_user\_  
  id
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_purchase\_state
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_net
* af\_sandbox\_revenue

</Accordion>

<div id="test-purchase-af_purchase_sandbox_s2s" />

<Accordion title="Compra de teste (af_purchase_sandbox_s2s)">

**Descrição**

Registrado ao testar uma compra relatada por S2S em um ambiente sandbox.

**Parâmetros**

* ativado
* customer\_user\_  
  id
* af\_currency
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_purchase\_state
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_net
* af\_sandbox\_revenue

</Accordion>

</Accordion>

<div id="subscriptionrelated-events-and-parameters" />

<Accordion title="Eventos e parâmetros de assinatura">

As seções seguintes mostram os eventos relacionados à assinatura que a AppsFlyer mensura, e os parâmetros que são registrados para cada evento. Consulte o [dicionário de parâmetros de eventos](#parameter-dictionary) para acessar uma explicação dos parâmetros incluídos.

Todos os eventos gerados:

* São considerados eventos S2S.
* São acessíveis em relatórios de dados brutos (como eventos in-app orgânicos ou não orgânicos).
* Podem ser enviados por postbacks para parceiros.
* Podem ser usados no Conversion Studio.

**Atenção:** dependendo da plataforma do dispositivo do usuário, alguns parâmetros nem sempre são preenchidos para um evento in-app.

<div id="trial-started-af_ars_trial_started" />

<Accordion title="Teste iniciado (af_ars_trial_started)">

**Descrição**

Registrado quando um assinante inicia um período de teste.

**Parâmetros**

* ativado
* customer\_user\_  
  id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type

</Accordion>

<div id="trial-canceled-af_ars_trial_canceled" />

<Accordion title="Teste cancelado (af_ars_trial_canceled)">

**Descrição**

Registrado quando um assinante cancela a renovação automática da assinatura durante o período de teste. Se um usuário não restaurar a auto-renovação dentro do período de teste, segue-se um evento de churn.

**Parâmetros**

* ativado
* customer\_user\_  
  id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type

</Accordion>

<div id="trial-churned-af_ars_trial_churned" />

<Accordion title="Churn do teste (af_ars_trial_churned)">

**Descrição**

Registrado quando ocorre o churn de um assinante após um período de teste. Isso acontece após o cancelamento da renovação automática e a expiração do período de avaliação. Também pode acontecer após uma cobrança ou questão técnica com a renovação, que leva ao churn.

**Parâmetros**

* ativado
* customer\_user\_  
  id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_reason

</Accordion>

<div id="trial-converted-af_ars_trial_converted" />

<Accordion title="Conversão do teste (af_ars_trial_converted)">

**Descrição**

Registrado quando se inicia uma renovação com preço total após um período de teste.

**Parâmetros**

* ativado
* customer\_user\_  
  id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_discount\_id
* af\_discount\_type
* event\_revenue\_usd
* store\_commission
* af\_revenue (incluído no evento apenas quando a receita for maior que zero.)
* af\_net\_revenue
* af\_net\_revenue\_factors
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code

</Accordion>

<div id="subscription-started-af_ars_subscription_started" />

<Accordion title="Início da assinatura (af_ars_subscription_subscription_started)">

**Descrição**

Registrado quando se inicia uma assinatura com desconto ou a preço integral.

**Observação**:

* Novas assinaturas só podem ser registradas através do conector SDK.
* Para o iOS, se um assinante recompra uma assinatura que já possui, o conector SDK reporta uma validação de recibo bem sucedida de volta ao aplicativo, mas não registra uma nova transação na AppsFlyer.

**Parâmetros**

* ativado
* customer\_user\_  
  id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_discount\_id
* af\_discount\_type
* event\_revenue\_usd
* event\_revenue (incluído no evento quando a receita é maior que zero)
* store\_commission
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_factors
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code

</Accordion>

<div id="subscription-canceled-af_ars_subscription_canceled" />

<Accordion title="Assinatura cancelada (af_ars_subscription_canceled)">

**Descrição**

Registrado quando uma assinatura de renovação automática é cancelada no meio de um período de faturamento. Se um usuário não restaurar a auto-renovação dentro do período de faturamento, segue-se um evento de churn.

**Parâmetros**

* ativado
* customer\_user\_  
  id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type

</Accordion>

<div id="subscription-paused-af_ars_subscription_paused-android-only" />

<Accordion title="Assinatura pausada (af_ars_subscription_paused) - Somente Android">

**Descrição**

Registrado quando um usuário pausa uma assinatura ativa.

**Parâmetros**

* ativado
* customer\_user\_  
  id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type

</Accordion>

<div id="subscription-resumed-af_ars_subscription_resumed" />

<Accordion title="Assinatura retomada (af_ars_subscription_resumed)">

**Descrição**

Registrado quando uma assinatura de preço total é retomada após uma assinatura em que houve churn ou reembolso.

**Parâmetros**

* ativado
* customer\_user\_  
  id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_discount\_id
* af\_discount\_type
* af\_reason
* event\_revenue (incluído no evento quando a receita do evento é maior que zero)
* store\_commission
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_factors

</Accordion>

<div id="subscription-churned-af_ars_subscription_churned" />

<Accordion title="Churn da assinatura (af_ars_subscription_churned)">

**Descrição**

Registrado quando ocorre o churn de um assinante. Isso geralmente acontece após o cancelamento da renovação automática ou a expiração do período de cobrança. Também pode acontecer após uma cobrança ou questão técnica com a renovação, que leva ao churn.

**Parâmetros**

* ativado
* customer\_user\_  
  id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_reason

</Accordion>

<div id="subscription-refunded-af_ars_subscription_refunded" />

<Accordion title="Assinatura reembolsada (af_ars_subscription_refunded)">

**Descrição**

Registrado quando um reembolso é emitido para um assinante.

**Atenção:**

* Esse evento geralmente é gerado junto com um valor negativo. Nos casos em que é impossível detectar quais transações foram reembolsadas, ou os detalhes do reembolso não estão incluídos na notificação, o evento de reembolso não mostra nenhum valor.

**Parâmetros**

* ativado
* customer\_user\_  
  id
* af\_reason
* af\_subscription\_ownership\_type
* af\_discount\_id
* af\_discount\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_refunded\_transaction\_ids
* event\_revenue\_usd
* event\_revenue (incluído no evento quando a receita é maior que zero)
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_store
* af\_environment
* af\_period\_type
* store\_commission
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_factors
* af\_net\_revenue\_tax\_name
* af\_net\_revenue\_tax\_rate
* af\_net\_revenue\_tax\_exclusive
* af\_net\_revenue\_country
* af\_net\_revenue\_subdivision
* af\_net\_revenue\_postal\_code

</Accordion>

<div id="subscription-billing-grace-af_ars_subscription_billing_grace" />

<Accordion title="Carência de faturamento da assinatura (af_ars_subscription_billing_grace)">

**Descrição**

Registrado quando uma renovação de assinatura falha devido a um problema de cobrança e o assinante entra no período de carência de cobrança.

**Parâmetros**

* ativado
* customer\_user\_  
  id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type

</Accordion>

<div id="subscription-renewed-af_ars_subscription_renewed" />

<Accordion title="Assinatura renovada (af_ars_subscription_renewed)">

**Descrição**

Registrado quando uma assinatura de renovação automática é feita.

**Parâmetros**

* ativado
* customer\_user\_  
  id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_discount\_id
* af\_discount\_type
* event\_revenue\_usd
* event\_revenue (incluído no evento quando a receita é maior que zero)
* store\_commission
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_factors

</Accordion>

<div id="subscription-changed-af_ars_subscription_xgraded" />

<Accordion title="Assinatura alterada (af_ars_subscription_xgraded)">

**Descrição**

Registrado quando um assinante faz upgrades, redução, ou cross-grades para um produto diferente.

**Parâmetros**

* ativado
* customer\_user\_  
  id
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_discount\_id
* af\_discount\_type
* event\_revenue\_usd
* event\_revenue (incluído no evento quando a receita é maior que zero)
* store\_commission
* af\_revenue
* af\_net\_revenue
* af\_net\_revenue\_factors

</Accordion>

<div id="existing-subscriber-af_ars_existing_subscriber" />

<Accordion title="Assinante existente (af_ars_existing_subscriber)">

**Descrição**

Registrado quando o conector do SDK é notificado sobre um assinante no meio de um ciclo de cobrança, antes de receber uma notificação de acompanhamento do servidor que faz a transição do assinante para outro estágio relevante do ciclo de vida. Esse evento costuma ser gerado durante o período de integração e adoção do conector do SDK.

**Parâmetros**

* ativado
* customer\_user\_  
  id
* país
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_cuids
* af\_validated

</Accordion>

<div id="test-purchase-af_ars_sandbox_sdk" />

<Accordion title="Compra de teste (af_ars_sandbox_sdk)">

**Descrição**

Registrado ao testar uma compra registrada por SDK em ambiente de área restrita.

**Parâmetros**

* ativado
* customer\_user\_  
  id
* país
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_discount\_id
* af\_discount\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_cuids
* af\_validated
* af\_net
* af\_sandbox\_revenue

</Accordion>

<div id="test-purchase-af_ars_sandbox_s2s" />

<Accordion title="Compra de teste (af_ars_sandbox_s2s)">

**Descrição**

Registrado ao testar uma compra relatada por S2S em um ambiente sandbox.

**Parâmetros**

* ativado
* customer\_user\_  
  id
* país
* af\_currency
* af\_expires\_date\_ms
* af\_subscription\_ownership\_type
* af\_discount\_id
* af\_discount\_type
* af\_original\_transaction\_id
* af\_order\_id
* af\_purchase\_token
* af\_transaction\_id
* af\_product\_id
* android\_id
* idfa
* ip
* appsflyer\_id
* af\_purchase\_date\_ms
* af\_store
* af\_environment
* af\_period\_type
* af\_cuids
* af\_validated
* af\_net
* af\_sandbox\_revenue

</Accordion>

</Accordion>

<div id="parameter-dictionary" />

<Accordion title="Dicionário de parâmetros">

Os parâmetros para IAPs e eventos de assinatura são exibidos em relatórios de dados brutos como suas próprias colunas ou preenchidos como parte do **valor do evento**.

Os parâmetros que possuem suas próprias colunas são:

* ativado
* customer\_user\_  
  id
* código\_país
* af\_currency
* event\_revenue\_usd
* af\_revenue
* android\_id
* ip
* idfa
* appsflyer\_id

Consulte o <Anchor target="_blank" href="/marketers/pt/docs/raw-data-field-dictionary">dicionário de campos de dados</Anchor> para mais detalhes sobre esses parâmetros.

A tabela a seguir descreve os parâmetros de dados brutos disponíveis em eventos ARS e VIAP.

| Parâmetro | Observações | Produto |
| --- | --- | --- |
| af\_cancelation\_date\_ms | Data de cancelamento | compras in-app |
| af\_cuids | <ul><li>No contexto do ARS, esse parâmetro contém uma lista com todos os CUIDs.</li><li>A lista de CUIDs é mostrada independentemente dos device IDs. Assim, os mesmos CUIDs podem ser mostrados para mais de um device ID.</li></ul> | Subscription |
| af\_discount\_id | O offer ID apresentado ao usuário durante a compra inicial. O ID só é preenchido quando existe um código de desconto. | <ul><li>compras in-app</li><li>Subscription</li></ul> |
| af\_discount\_type | Tipo de desconto resgatado pelo usuário. Valores possíveis:<ul><li>iOS<ul><li>introdutório</li><li>promotional</li><li>offer\_codes</li><li>win\_back</li></ul></li><li>com o Android<ul><li>preço inicial</li><li>one\_time\_code</li><li>vanity\_code</li></ul></li></ul> | Subscription |
| af\_environment | O ambiente de onde os dados são recebidos, seja produção ou sandbox. | <ul><li>compras in-app</li><li>Subscription</li></ul> |
| af\_expires\_date\_ms | A data de expiração do ciclo de faturação da assinatura atual | Subscription |
| af\_net\_revenue | Receita líquida calculada com base em todas as razões consideradas. Consulte af\_net\_revenue\_factors. | <ul><li>compras in-app</li><li>Subscription</li></ul> |
| af\_net\_revenue\_country | <ul><li>Código de país ISO de duas letras para o qual o imposto é aplicado.</li><li>Exemplo: CA</li><li>Observação: o código implementado para o Reino Unido é UK, não GB.</li></ul> | <ul><li>compras in-app</li><li>Subscription</li></ul> |
| af\_net\_revenue\_factors | <ul><li>Uma matriz que representa todos os fatores que contribuem para o valor de af\_net\_revenue reportado.</li><li>Valor de exemplo: store\_comission</li></ul> | <ul><li>compras in-app</li><li>Subscription</li></ul> |
| af\_net\_revenue\_postal\_code | <ul><li>String de letras e/ou números</li><li>Exemplo: L4J8E3</li></ul> | <ul><li>compras in-app</li><li>Subscription</li></ul> |
| af\_net\_revenue\_subdivision | <ul><li>Para alguns países, pode haver uma subdivisão ou estado adicional, de acordo com os <Anchor target="_blank" href="https://service.unece.org/trade/locode/2023-1%20SubdivisionCodes.htm">códigos de subdivisão ISO 3166-2</Anchor>. Isso é tratado de acordo com os <Anchor target="_blank" href="https://service.unece.org/trade/locode/2023-1%20SubdivisionCodes.htm">códigos de subdivisão ISO 3166-2</Anchor>.</li><li>Inclui o código do país e o código da subdivisão.</li><li>Exemplo: US-CA</li></ul> | <ul><li>compras in-app</li><li>Subscription</li></ul> |
| af\_net\_revenue\_tax\_exclusive | <ul><li>Parâmetro booleano, true ou false.</li><li>False significa que o imposto está incluído na receita total.</li><li>True significa que o imposto é adicionado à receita declarada geral.</li></ul> | <ul><li>compras in-app</li><li>Subscription</li></ul> |
| af\_net\_revenue\_tax\_name | <ul><li>Nome que aparece na fatura do cliente, descrevendo o tipo específico de imposto.</li><li>Exemplo: Sales, VAT, GST</li></ul> | <ul><li>compras in-app</li><li>Subscription</li></ul> |
| af\_net\_revenue\_tax\_rate | <ul><li>Número com até 4 casas decimais representando o percentual do imposto recolhido.</li><li>Exemplo: 7.25</li></ul> | <ul><li>compras in-app</li><li>Subscription</li></ul> |
| af\_offer\_id | <ul><li>O ID da oferta aplicada à transação, quando relevante. Exemplo: descontos ou ofertas promocionais.</li><li>Exclusivo para Android</li></ul> | <ul><li>compras in-app</li><li>Subscription</li></ul> |
| af\_order\_id | <ul><li>O order ID da transação</li><li>Exclusivo para Android</li></ul> | <ul><li>compras in-app</li><li>Subscription</li></ul> |
| af\_original\_transaction\_id | <ul><li>O ID da transação original</li><li>Exclusivo para iOS</li></ul> | <ul><li>compras in-app</li><li>Subscription</li></ul> |
| af\_original\_transaction\_id | <ul><li>O ID original da transação</li><li>Exclusivo para iOS</li></ul> | <ul><li>compras in-app</li><li>Subscription</li></ul> |
| af\_period\_type | <ul><li>Tipo de período de assinatura ou avaliação.</li><li>Valores possíveis:<ul><li>Avaliação</li><li>intro</li><li>Normal</li></ul></li></ul> | Subscription |
| af\_product\_id | ID do produto assinado | <ul><li>compras in-app</li><li>Subscription</li></ul> |
| af\_purchase\_date\_ms | A data de compra do product ID reportado no evento in-app | <ul><li>compras in-app</li><li>Subscription</li></ul> |
| af\_purchase\_option\_id | <ul><li>O ID da opção de compra associada à transação.</li><li>Exclusivo para Android</li></ul> | compras in-app |
| af\_purchase\_option\_type | O tipo de opção de compra na transação. Valores possíveis (Android):<ul><li>buy</li><li>rent</li></ul> | compras in-app |
| af\_purchase\_state | Valores possíveis:<ul><li>Comprado</li><li>Cancelado</li><li>Pending</li></ul> | compras in-app |
| af\_purchase\_token | <ul><li>Token de compra da transação</li><li>Exclusivo para Android</li></ul> | <ul><li>compras in-app</li><li>Subscription</li></ul> |
| af\_reason | [conteúdo inalterado] | <ul><li>compras in-app</li><li>Subscription</li></ul> |
| af\_refunded\_transaction\_ids | <ul><li>Uma lista de todos os IDs das transações reembolsadas</li><li>Exclusivo para iOS</li></ul> | <ul><li>compras in-app</li><li>Subscription</li></ul> |
| af\_store | A loja de aplicativos onde o produto assinado foi comprado | <ul><li>compras in-app</li><li>Subscription</li></ul> |
| af\_subscription\_ownership\_type | FAMILY\_SHARED significa que o usuário tem acesso através de compartilhamento familiar. PURCHASED significa que o usuário pagante fez a compra. | Subscription |
| af\_transaction\_id | <ul><li>O ID da transação</li><li>Exclusivo para iOS</li></ul> | <ul><li>compras in-app</li><li>Subscription</li></ul> |
| store\_commission | <ul><li>A percentagem calculada de comissão que a loja recebe do produto comprado.</li><li>Exibido como uma casa decimal.</li><li>Exemplo: 30</li></ul> | <ul><li>compras in-app</li><li>Subscription</li></ul> |

</Accordion>

<div id="true-revenue" />

<Accordion title="Net revenue">

A receita líquida é uma camada de lógica de negócio criada para auxiliar a solução de receita da loja do ROI360. Ela calcula automaticamente o valor da receita líquida para cada transação recebida em tempo real e o inclui em relatórios.

> 📘 **Atenção**
>
> A receita líquida é exibida em relatórios de dados brutos e pode ser enviada em tempo real por meio de postbacks de eventos in-app. Os dashboards exibem apenas a receita bruta de compras e assinaturas.
>
> Para enviar a receita líquida em postbacks, configure o evento in-app com a opção **Valores, receita & receita líquida**. Para mais detalhes, leia o artigo <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#dados-a-incluir-nos-postbacks">Configuração de postback de eventos in-app</Anchor>.

> 📘 **Observação**
>
> Você também pode configurar seus postbacks de eventos in-app para enviar a receita líquida em vez da receita bruta no parâmetro padrão de receita (monetário). Para ter acesso à essa configuração, entre em contato com seu Customer Success Manager (CSM).

A True Revenue considera os seguintes fatores no cálculo da receita bruta para líquida:

* **Comissão da loja**:
  * É calculada e informada automaticamente. Nenhuma ação é exigida por você.
  * Para compras IAP, a comissão padrão depende da loja:
    * App Store — Japão e países da UE: 26%. China continental (CN): 25%. Outros países: 30%.
    * Play Store: 30%.
  * Para assinaturas, a comissão é calculada automaticamente por assinante, com base no período de permanência.
    * App Store — primeiros 12 meses: 26% no Japão e nos países da UE, 25% na China continental (CN), 30% no resto do mundo. A partir do 13º mês: 15% no Japão, 12% na China continental (CN), 15% nos outros países.
    * Play Store: 15% desde o primeiro dia.
  * Parâmetros de receita líquida relacionados estão disponíveis em relatórios de dados brutos.
  * Use <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-7">a API de receita líquida</Anchor> para definir uma taxa de comissão da loja diferente da padrão. Isso pode ser útil, por exemplo, se o seu aplicativo estiver cadastrado no programa da App Store para pequenas empresas, em que a taxa de comissão geral é de 15% e 12% na China continental (CN).
* **Imposto**:
  * O imposto é informado por padrão para qualquer transação medida pelo ROI360 usando a configuração de taxa de imposto padrão.
  * Isso se aplica aos países com impostos inclusos (onde o imposto está incluído no preço de tabela). Por exemplo, no Reino Unido, a AppsFlyer desconta o valor total de imposto e comissão da loja. Para países com impostos exclusivos, como os EUA, onde o preço de tabela não inclui impostos, os parâmetros de receita e receita líquida não incluem impostos por padrão.
  * A configuração pode ser editada usando <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-7">a API de receita líquida</Anchor>. Para descobrir as taxas fiscais padrão dos países, consulte <Anchor target="_blank" href="https://docs.google.com/document/d/e/2PACX-1vSl3DwlK2Gt2aa5gmDzD3-K3CtnIM85oMNrqx3PCTamwCERWYU48GugNpD31BFjA2PJjZnqaXIVe2Hx/pub">este arquivo JSON</Anchor>. O programador pode editá-lo ou usá-lo sem alterações na API.

Ao visualizar a receita líquida em relatórios, os parâmetros a seguir contêm os respectivos dados. Consulte o dicionário de parâmetros para saber mais detalhes.

| Parâmetro | Fator de receita líquida |
| --- | --- |
| `store_commission` | Comissão da loja |
| `af_net_revenue_tax_name` | Imposto |
| `af_net_revenue_tax_rate` | Imposto |
| `af_net_revenue_tax_exclusive` | Imposto |
| `af_net_revenue_postal_code` | Imposto |
| `af_net_revenue_country` | Imposto |
| `af_net_revenue_subdivision` | Imposto |
| `af_net_revenue` | <ul><li>Comissão da loja</li><li>Imposto</li></ul> |
| `af_net_revenue_factors` | <ul><li>Comissão da loja</li><li>Imposto</li></ul> |

</Accordion>

<div id="troubleshooting-and-disprepancies" />

<Accordion title="Solução de problemas e discrepâncias">

| Sintoma | Explicação / Solução |
| --- | --- |
| A AppsFlyer mostra menos eventos de compras in-app e de assinaturas do que as lojas de aplicativos reais. | Na AppsFlyer, os eventos são gerados apenas para usuários que atualizaram para uma versão do aplicativo que inclui o conector SDK. Enquanto isso, o aplicativo armazena um log de todos os eventos, independentemente da versão do aplicativo do usuário. Como resultado, até que a versão atualizada do aplicativo seja totalmente adotada, espera-se uma discrepância entre os dados de receita do aplicativo e os dados da loja. |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Características e Limitações">

| Especificação | Produto | Observações |
| --- | --- | --- |
| Assinaturas parceladas (Android) | Receita de assinaturas | Não suportado |
| Assinatura pendendo  <br />transações (Android) | Receita de assinaturas | Não suportado |
| Novas assinaturas | Receita de assinaturas | Registrado apenas por meio do SDK de compra da AppsFlyer |
| Alteração de preço | Receita de assinaturas | Se a receita de assinatura não receber uma notificação gerada pelo SDK com o novo preço do produto, ela continuará a reportar o preço anterior do produto como receita. Assim que o novo preço do produto for recebido do SDK de compra, ele será registrado. |
| Receita bruta | <ul><li>compras in-app</li><li>Receita de assinaturas</li></ul> | Com suporte. |
| Net revenue | <ul><li>compras in-app</li><li>Receita de assinaturas</li></ul> | Com suporte em dados brutos e em My Dashboards (como as métricas Net) |
| Reembolsos | compras in-app | Podem ser relatados até 180 dias após a compra original. |
| Desduplicação | <ul><li>compras in-app</li><li>Receita de assinaturas</li></ul> | Compatível com transações reportadas até 180 dias após a data do evento. |
| Modo restrito do SDK | <ul><li>compras in-app</li><li>Receita de assinaturas</li></ul> | As assinaturas ROI360 e VIAP ficam disponíveis no modo estrito do SDK.<ul><li>Conector do SDK de compra da AppsFlyer para iOS V6.13.0</li><li>Conector do SDK de compra para Unity V2.0.1</li></ul> |
| Moeda | <ul><li>compras in-app</li><li>Receita de assinaturas</li></ul> | A receita é relatada na moeda original (usando o parâmetro event\_revenue) e em USD (usando o parâmetro event\_revenue\_usd parameter). |
| Atualização dos dados | <ul><li>compras in-app</li><li>Receita de assinaturas</li></ul> | <ul><li>Relatório de receita da loja no nível de transações: atualizado a cada hora Por hora</li><li>Relatório de receita da loja a nível de dispositivo: A cada 8 horas</li></ul> |
| StoreKit 2 | <ul><li>compras in-app</li><li>Receita de assinaturas</li></ul> | <ul><li>O StoreKit 2 está disponível a partir da versão 6.16.2 do Purchase SDK Connector.</li><li>Certifique-se de que seu aplicativo use as credenciais atualizadas da App Store descritas <Anchor target="_blank" href="/marketers/pt/docs/bulletin-update-app-store-credentials-for-ios-roi360-receipt-validation">aqui</Anchor>.</li></ul> |
| Produtos de compra única do Google | compras in-app | <ul><li>Opções de venda disponíveis: compra e aluguel</li><li>Pré-venda: indisponível</li></ul> |

</Accordion>

<div data-zendesk-anchors="h_01KSAJW61CZZBWBQ112VR5095C=importante h_01KD0W3J6105033NV6FYKGQ8BQ=aviso how-does-roi360-store-revenue-work=como-funciona-a-receita-da-loja-do-roi360 h_01KD2JZQ0JYVF8S1E2W3N91KYV=como-funciona-a-receita-da-loja-do-roi360 enable-roi360-store-revenue=ativar-a-receita-da-loja-do-roi360 h_01KD2JZQ0JS9YQ2SPNN6NHAJEH=ativar-a-receita-da-loja-do-roi360 set-up-roi360-store-revenue=configurar-a-receita-da-loja-do-roi360 h_01KD2JZQ0JD53598CES8ECAHR3=configurar-a-receita-da-loja-do-roi360 reference=refer%C3%AAncia h_01JKWGTJQY938NV6VCJ7KKS23E=refer%C3%AAncia h_01KD6B3KC75RFDV08G9RT1BX1M=nota h_01HDEPSK8DFQ24EZ5T0EPBSVS4=iaprelated-events-and-parameters 01H8VJJP1ER9N6BPAES8H8CK4T=purchase-af_purchase h_01J50N58GYF2BYC57HA7THSWW6=purchase-af_purchase_free 01H8VJJP1EXYE1EQS08CK8BG02=purchase-canceled-af_purchase_canceled 01H8VJJP1ET5TAAQ17EMK6TVRE=purchase-pending-af_purchase_pending 01H8VJJP1E8JKPGT2V9CCB1XW8=refund-af_purchase_refund 01H8VJJP1ECQMS49M8Z1X1FT4B=test-purchase-af_purchase_sandbox_sdk 01H8VJJP1E3X7YZNYT5D8REVEW=test-purchase-af_purchase_sandbox_s2s h_01HDEQBACTTPZ04YYD1KV49SEZ=subscriptionrelated-events-and-parameters 01H8VJJP1EHAZBGT82WRWB00JT=trial-started-af_ars_trial_started 01H8VJJP1ETCHTK6JMK9ERS5A5=trial-canceled-af_ars_trial_canceled 01H8VJJP1EC45X8PJVPWT3G7S3=trial-churned-af_ars_trial_churned 01H8VJJP1EYPQM50JVX1KPZXAZ=trial-converted-af_ars_trial_converted 01H8VJJP1EA4WTCEJWBB1HPRJF=subscription-started-af_ars_subscription_started 01H8VJJP1EF744NE425Y30VG0M=subscription-canceled-af_ars_subscription_canceled 01H8VJJP1EMKBP27070NRR9CZ5=subscription-paused-af_ars_subscription_paused-android-only 01H8VJJP1EGHNQ35JM1TWV4ND0=subscription-resumed-af_ars_subscription_resumed 01H8VJJP1EM2GJ28VBE6V76SBG=subscription-churned-af_ars_subscription_churned 01H8VJJP1E28XXAQSGZ9PYDT08=subscription-refunded-af_ars_subscription_refunded 01H8VJJP1E399B2AVWP9VKZ0D4=subscription-billing-grace-af_ars_subscription_billing_grace 01H8VJJP1EEZZ0DE75VXAZQP3E=subscription-renewed-af_ars_subscription_renewed 01H8VJJP1FGXHRK3J0XB2G4PCQ=subscription-changed-af_ars_subscription_xgraded 01H8VJJP1FKC8KZ2HKJVGZEV23=existing-subscriber-af_ars_existing_subscriber 01H8VJJP1F720QT97Q0TW4SEM2=test-purchase-af_ars_sandbox_sdk 01H8VJJP1FSRHG26EXMEG3325P=test-purchase-af_ars_sandbox_s2s 01H8VJJP1F0ZV2PX39D9JCG6B4=parameter-dictionary 01H8VJJP1FF219YN3XHRCGW7Z3=true-revenue h_01KBFWTM4XJ417930YVDD36ASK=aten%C3%A7%C3%A3o h_01KRKEP613DR8RZ5Q2A5H7KZAH=observa%C3%A7%C3%A3o 01JHZG8FFHTYE2PMRWWS8WNR6X=troubleshooting-and-disprepancies 01H8VJJP1FP2MPRF8AN77REXD0=traits-and-limitations" />
