---
title: Integração do Google Analytics (GA4)
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2024-06-06T15:26:00Z'
  edited_at: '2026-09-28T00:05:36Z'
  id: 25707682812561
  locale: pt
  section: Google Analytics
  section_id: 6551226043793
  url: https://support.appsflyer.com/hc/pt/articles/25707682812561
---
> **At a glance:** **Resumo:** A integração da AppsFlyer com o Google Analytics (GA4) permite que os anunciantes enviem dados de atribuição e eventos in-app selecionados da AppsFlyer para o GA4. Essa integração funciona com aplicativos iOS e Android que já têm o [SDK do Google Analytics para Firebase](https://firebase.google.com/docs/analytics) implementado.

> 🚧 **Important**
>
> **Importante!**
>
> Essa integração funciona com aplicativos iOS e Android que já têm o [SDK do Google Analytics para Firebase](https://firebase.google.com/docs/analytics) implementado. Para que a integração seja bem-sucedida, o SDK da AppsFlyer deve coletar o valor `app_instance_id` do SDK do Firebase. Veja as instruções sobre [como recuperar o app instance ID do SDK do Firebase](#5-retrieve-app-instance-id-in-appsflyer-sdk).

## Como funciona?

* **Quando** **uma** **nova instalação ocorre**, a AppsFlyer envia as informações do ponto de contato - fonte de mídia, nome da campanha e ID da campanha - para o GA4. Ela também envia o `app_instance_id` do SDK do Firebase para garantir que o ponto de contato seja registrado no GA4 para aquele usuário.
* **Quando** **um evento in-app ocorre**, o GA4 atribuirá o evento ao último ponto de contato.

## Configurar a integração do Google Analytics (GA4)

Siga as instruções abaixo para configurar a integração com o Google Analytics (GA4).

<Accordion title="1. Selecione o Google Analytics (GA4) no Partner Marketplace">

**Pré-requisito:** Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. **Para ativar:** na AppsFlyer, no menu lateral, selecione **Colaborar** > **Partner Marketplace.Para editar**: na AppsFlyer, vá para o menu lateral e selecione **colaborar** > **integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Pesquise por **Google Analytics (GA4)** e selecione-o.
4. Na **primeira visita** aqui, você precisará ativar a opção ***Ativar parceiro*** para habilitar a configuração dos parâmetros de integração.   
   Observação: o botão de alternância **deve permanecer ativado (ativo) enquanto você trabalhar com o Google Analytics (GA4)**. <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">Saiba mais</Anchor>
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo.

A configuração do Google Analytics inclui apenas a aba **Integração**.

Para uma descrição detalhada do cabeçalho da janela de configuração de parceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

</Accordion>

<Accordion title="2. Configurar a integração do GA4 no AppsFlyer">

Defina as seguintes configurações:

1. Na aba **Integração**, selecione o aplicativo e ative a opção **Ativar parceiro**.

   **Atenção:** Essa opção deve permanecer <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">ativada</Anchor> durante todo o tempo que você trabalhar com o parceiro.

   Para obter mais detalhes sobre a ativação do parceiro, clique aqui.
2. Em **Firebase App ID**, insira o identificador do aplicativo no Firebase. Para saber como localizá-lo, consulte <Anchor target="_blank" href="https://firebase.google.com/support/faq#find-app-id">a documentação do Firebase</Anchor>.
3. Em **API Secret**, insira o API Secret para autenticar os postbacks para o Google Analytics. Um API Secret é gerado através da interface do usuário do Google Analytics. Para visualizar, editar ou criar essa informação (secret), siga as instruções na <Anchor target="_blank" href="https://support.google.com/analytics/answer/9814495?sjid=5179426966283787649-EU">documentação do Google</Anchor>. **Quando instruído a selecionar um fluxo de dados da web, escolha um fluxo de dados do Android ou iOS.**
4. Ative o **Customer User ID** para enviar o Customer User ID (CUID) em vez do advertising ID (IDFA).
5. Em **Postbacks padrão**, em **para usuários de**, selecione **Todas as fontes de mídia, incluindo orgânicas**.

> 📘 **Note**
>
> **Importante!**
>
> O postback de instalação inclui apenas os detalhes do ponto de contato (fonte de mídia, nome da campanha e ID da campanha).

</Accordion>

<Accordion title="3. Configurar postbacks de eventos in-app">

A AppsFlyer pode enviar postbacks automáticos para o GA4 após as instalações de usuários, incluindo instalações e reengajamentos (incluindo reatribuições). Os reengajamentos ocorrem quando um usuário que já tem o aplicativo instalado o abre depois de clicar em um link de campanha. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#default-postbacks">postbacks padrão</Anchor>.

</Accordion>

<Accordion title="4. Configurar postbacks de eventos in-app">

Na aba **Integração**, mapeie os eventos in-app da AppsFlyer para os eventos do Google Analytics (GA4), enviados via postbacks.

> 📘 **Note**
>
> **Importante!**
>
> * Atualmente, postbacks de eventos in-app de aplicativos mobile enviados via S2S não são compatíveis.
> * O GA4 não desduplica eventos enviados tanto do Firebase SDK quanto da AppsFlyer. Portanto, recomendamos que você configure postbacks de eventos in-app apenas para eventos que não são enviados ao GA4 via Firebase SDK.

1. Ative os **postbacks de eventos in-app**.
2. Clique em **Adicionar evento** para adicionar um SDK ou evento de servidor para servidor à lista. A tabela a seguir descreve os campos a serem preenchidos:

| Nome do parâmetro | A descrição |
| --- | --- |
| **Evento na AppsFlyer** | O nome do evento, conforme recebido do SDK integrado no aplicativo ou de eventos de servidor para servidor.<br /><br />**Dica**: não encontrou o evento que está procurando?<ul><li>Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente.</li><li>Digite-o em **evento da AppsFlyer**, depois clique em **criar evento personalizado**.</li></ul>Saiba mais sobre o <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#eventos-personalizados">mapeamento de eventos personalizados</Anchor>. |
| **Mapeado para evento do parceiro** | O nome ou ID único de cada evento, como definido pelo parceiro. As configurações de mapeamento possíveis são:<ul><li>**Campo de texto:** obtenha o ID do evento correspondente no parceiro.</li><li>**Caixa suspensa:** selecione o evento predefinido mais adequado.</li><li>**Como está**: envie os eventos como estão, sem mapeamento de nomes.</li></ul> |
| **para utilizadores de** | Selecione a opção de envio para o evento:<ul><li>**Todas as fontes de mídia, incluindo orgânicas:** Envie postbacks para eventos atribuídos a qualquer parceiro, assim como eventos orgânicos.</li></ul> |
| **Incluindo** | <ul><li>**Sem dados (padrão)**: Envie apenas o evento em si, sem qualquer valor de evento.</li><li>**Valores e receitas**: envie todos os parâmetros de evento, **incluindo** o valor da receita (se existir no evento).</li><li>**Valores sem receita**: envie todos os parâmetros **exceto** o valor de receita.</li></ul> |

3. [Opcional] Clique no ícone **Adicionar condição** (<Image alt="condition-2.png" src="https://files.readme.io/959329be2b1286507b5c87b033785e91ab135592ae37cf3200539400832490c0-25709762755857.png" width="19px" />) para <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#postbacks-condicionais-de-eventos-in-app">definir condições</Anchor> para um evento.
4. Clique em **Guardar integração**.
5. Envie o mapeamento do postback para o evento

</Accordion>

<Accordion title="5. Recuperar app instance ID no SDK da AppsFlyer">

Depois de configurar o mapeamento do evento in-app, envie ao seu desenvolvedor uma tabela onde cada evento mapeado corresponde a uma linha com as seguintes colunas:

* **Evento AF:** nome do evento da AppsFlyer.
* **Mapeado para evento do Google:** nome do evento no Google Analytics.

> 🚧 **Important**
>
> **Importante!**
>
> Não use nenhum dos [eventos reservados do Google](#nomes-de-eventos-reservados---google) como nomes para eventos personalizados do Google Analytics.

* **Parâmetros do evento AF (OBRIGATÓRIO):** Parâmetros de evento pré-definidos na AppsFlyer, que devem ser incluídos no postback enviado ao Google Analytics.

> 🚧 **Important**
>
> **Importante!**
>
> É obrigatório incluir todos os parâmetros pré-definidos na AF dentro da definição do evento, exatamente como eles estão listados na tabela; caso contrário, o postback será rejeitado pelo Google Analytics.

#### Tabela de mapeamento de eventos

A tabela a seguir inclui todos os eventos do Google Analytics e seus parâmetros pré-definidos na AppsFlyer. Envie ao seu desenvolvedor uma tabela contendo apenas os eventos que você mapeou.

| Nome recomendado pela AF (Opcional) | Nome do evento no Google Ads | Parâmetros pré-definidos na AF (OBRIGATÓRIO) |
| --- | --- | --- |
| af\_add\_payment\_info | [add\_payment\_info](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#add_payment_info) | <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [add\_shipping\_info](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#add_shipping_info) | <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
| af\_add\_to\_cart | [adicionar\_ao\_carrinho](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#add_to_cart) | <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
| af\_add\_to\_wishlist | [add\_to\_wishlist](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#add_to_wishlist) | <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
| af\_initiated\_checkout | [begin\_checkout](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#begin_checkout) | <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [campaign\_details](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#campaign_details) | campaign id, campaign name |
| af\_spent\_credits | [earn\_virtual\_currency](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#earn_virtual_currency) | <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor> |
|  | [generate\_lead](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#generate_lead) | <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor> |
|  | [join\_group](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#join_group) |  |
| af\_level\_achieved | [level\_up](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#level_up) |  |
| af\_login | [Iniciar sessão](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#login) |  |
|  | [post\_score](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#post_score) | af\_user\_score |
| af\_compra | [purchase](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#purchase) | <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_content">af\_content</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_receipt_id">af\_receipt\_id</Anchor> |
|  | [refund](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#refund) | <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_content">af\_content</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_receipt_id">af\_receipt\_id</Anchor> |
|  | [remove\_from\_cart](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#remove_from_cart) | <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [screen\_view](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#screen_view) |  |
| af\_search | [search](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#search) |  |
|  | [select\_content](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#select_content) |  |
|  | [select\_item](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#select_item) | <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [select\_promotion](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#select_promotion) | <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [compartilhar](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#share) |  |
|  | [sign\_up](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#sign_up) |  |
|  | [spend\_virtual\_currency](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#spend_virtual_currency) | <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor> |
|  | [tutorial\_begin](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#tutorial_begin) |  |
| af\_tutorial\_completion | [tutorial\_complete](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#tutorial_complete) |  |
| af\_achievement\_unlocked | [Unlock\_achievement](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#unlock_achievement) | af\_achievement\_id |
|  | [view\_cart](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#view_cart) | <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [view\_item](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#view_item) | <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [view\_item\_list](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#view_item_list) | <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [view\_promotion](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#view_promotion) | <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_price">af\_price</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_content_id">af\_content\_id</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_content">af\_content</Anchor> |
|  | [view\_search\_results](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#view_search_results) |  |
| af\_ad\_view | [ad\_impression](https://developers.google.com/analytics/devguides/collection/protocol/ga4/reference/events#ad_impression) | <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_currency">af\_currency</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-event-structure#af_revenue">af\_revenue</Anchor> |

#### Nomes de eventos reservados - Google

Os seguintes nomes de eventos não podem ser usados como nomes de eventos personalizados:

* `ad_activeview`
* `ad_click`
* `exposição_da_unidade_de_anúncio`
* `consulta_do_anúncio`
* `recompensa_do_anúncio`
* `exposição_do_anúncio`
* `limpar_dados_do_aplicativo`
* `exceção_do_aplicativo`
* `instalação_do_aplicativo`
* `remoção_do_aplicativo`
* `reembolso_da_loja_de_aplicativos`
* `app_update`
* `atualização_do_aplicativo`
* `abertura_do_aplicativo_por_link_dinâmico`
* `atualização_do_aplicativo_por_link_dinâmico`
* `primeira_abertura_por_link_dinâmico`
* `erro`
* `campanha_firebase`
* `ação_da_mensagem_no_aplicativo_firebase`
* `dispensar_mensagem_no_aplicativo_firebase`
* `impressão_da_mensagem_no_aplicativo_firebase`
* `primeira_abertura`
* `primeira_visita`
* `in_app_purchase`
* `dispensar_notificação`
* `notificação_em_primeiro_plano`
* `notification_open`
* `recebimento_de_notificação`
* `envio_de_notificação`
* `atualização_do_sistema_operacional`
* `início_da_sessão`
* `engajamento_do_usuario`

</Accordion>

<Accordion title="6. Recuperar o GA4 session ID no SDK da AppsFlyer">

O app instance ID identifica exclusivamente uma instalação específica de um aplicativo no Firebase. Esse valor precisa ser recuperado pelo SDK a partir do SDK do Firebase.

Seu desenvolvedor deve implementar o código para:

1. Coletar o campo `app_instance_id` do Firebase.
2. Chamar `setAddiotionalData` antes da primeira abertura para incluir o app instance ID em instalações, sessões e eventos no aplicativo.

> 🚧 **Important**
>
> **Importante!**
>
> `setAdditionalData` (Android / Unity / React Native) e `customData` (iOS) aceitam um **mapeamento de pares chave-valor**. Envia `app_instance_id` e `ga_session_id` **juntos no mesmo mapeamento,** para que ambos os valores sejam incluídos. Se você enviá-los em chamadas **separadas** `setAdditionalData`, a chamada posterior substituirá a anterior.

<Tabs>
<Tab title="Iniciando o SDK no Android native">

**Kotlin**

```kotlin
FirebaseAnalytics.getInstance(this).appInstanceId.addOnCompleteListener { task ->
   if (task.isSuccessful) {
       AppsFlyerLib.getInstance().setAdditionalData("app_instance_id", task.result)
    }
}
```

**Java**

```java
FirebaseAnalytics.getInstance(this).getAppInstanceId().addOnCompleteListener(task -> {
       if (task.isSuccessful()) {
           AppsFlyerLib.getInstance().setAdditionalData("app_instance_id", task.getResult());
       }
  });
```

Referência da API: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata">setAdditionalData</Anchor>

</Tab>

<Tab title="Android nativo iOS nativo Unity React nativo">

**Android nativo iOS nativo UnityReact nativo**

```swift
let appInstanceId = Analytics.appInstanceID()
    AppsFlyerLib.shared().customData = ["app_instance_id": appInstanceId]
```

**Objetivo c**

```objectivec
(void) fetchAnalyticsInstanceId {
           NSString *instanceID = [FIRAnalytics appInstanceID];
           [[AppsFlyerLib shared] setAdditionalData:@{@"app_instance_id": instanceID}];
}
```

Referência da API: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#customdata">customData</Anchor>

</Tab>

<Tab title="Unity">

```csharp
using Firebase. Analytics;
    public class AnalyticsManager : MonoBehaviour
    {
        private async void Start()
        {
           AppsFlyer.initSDK(devKey, appID, this);
           string appInstanceId = await FirebaseAnalytics. GetAnalyticsInstanceIdAsync();
           Dictionary <string, string> customData = new Dictionary<string, string>();
           customData. Add("app_instance_id", appInstanceId);
           AppsFlyer.setAdditionalData(appInstanceId);
           AppsFlyer.startSDK();
        }
}
```

Referência da API: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setadditionaldata">setAdditionalData</Anchor>

</Tab>

<Tab title="React Native">

Referência da API: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#setadditionaldata">setAdditionalData</Anchor>

</Tab>
</Tabs>

</Accordion>

<Accordion title="7. Validar a integração do GA4">

O `ga_session_id` identifica exclusivamente uma sessão de um aplicativo no Firebase. Esse valor deve ser recuperado do SDK do Firebase e enviado para o GA4 usando a API `setAdditionalData`.

Seu desenvolvedor deve implementar o código para:

1. Coletar o campo `ga_session_id` do Firebase.
2. Chame `setAdditionalData` antes da primeira abertura do app para incluir o session ID.
3. Use a chave `ga_session_id` ao chamar a API.

> 🚧 **Important**
>
> **Importante!**
>
> `setAdditionalData` (Android / Unity / React Native) e `customData` (iOS) aceitam um **mapeamento de pares chave-valor**. Se o seu aplicativo enviar `app_instance_id` e `ga_session_id` (consulte a [etapa 5](#5-retrieve-app-instance-id-in-appsflyer-sdk)), **envie-os juntos no mesmo mapeamento** para que ambos os valores sejam incluídos. Se você enviá-los em chamadas **separadas** `setAdditionalData`, a chamada posterior substituirá a anterior.

<Tabs>
<Tab title="Iniciando o SDK no Android native">

**Kotlin**

```kotlin
FirebaseAnalytics.getInstance(this).sessionId.addOnCompleteListener { task ->
    if (task.isSuccessful) {
        AppsFlyerLib.getInstance().setAdditionalData("ga_session_id", task.result)
    }
}
```

**Java**

```java
FirebaseAnalytics.getInstance(this).getSessionId().addOnCompleteListener(task -> {
    if (task.isSuccessful()) {
        AppsFlyerLib.getInstance().setAdditionalData("ga_session_id", task.getResult());
    }
});
```

Referência da API: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setadditionaldata">setAdditionalData</Anchor>

</Tab>

<Tab title="Android nativo iOS nativo Unity React nativo">

**Swift**

```swift
if #available(iOS 14.0, *) {
    Analytics.sessionID { sessionID, error in
        if let sessionID = sessionID {
            AppsFlyerLib.shared().customData = ["ga_session_id": sessionID]
        }
    }
}
```

**Objetivo-C**

```objectivec
- (void)fetchAnalyticsSessionId {
    if (@available(iOS 14.0, *)) {
        [FIRAnalytics sessionIDWithCompletion:^(NSString * _Nullable sessionID, NSError * _Nullable error) {
            if (sessionID) {
                [[AppsFlyerLib shared] setAdditionalData:@{@"ga_session_id": sessionID}];
            }
        }];
    }
}
```

Referência da API: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#customdata">customData</Anchor>

</Tab>

<Tab title="Unity">

```csharp
using Firebase. Analytics;
using System. Threading. Tasks;
using AppsFlyerSDK;
using UnityEngine;
using System. Collections. Generic;

public class AnalyticsManager : MonoBehaviour
{
    private async void Start()
    {
        AppsFlyer.initSDK("yourDevKey", "yourAppID", this);

        // Get session ID
        string sessionId = await FirebaseAnalytics. GetSessionIdAsync();

        Dictionary<string, string> customData = new Dictionary<string, string>();
        customData. Add("ga_session_id", sessionId);
        AppsFlyer.setAdditionalData(customData);

        AppsFlyer.startSDK();
    }
}
```

Referência da API: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setadditionaldata">setAdditionalData</Anchor>

</Tab>
</Tabs>

</Accordion>

<Accordion title="8. Validar a integração do GA4">

Certifique-se de que os eventos que você envia nos postbacks para o GA4 foram registrados e lidos pelo Google Analytics. Existem dois métodos que os anunciantes podem usar para visualizar seus dados:

* Usando [GA4 Explorations](https://support.google.com/analytics/answer/7579450?hl=en&ref_topic=12153537,12153943,2986333,&sjid=20462331341270448-EU&visit_id=638532662145815538-1056226594&rd=1#access-analysis&zippy=%2Cin-this-article), você pode explorar os dados de eventos brutos com todos os parâmetros associados. **Pré-requisito:** o [Big Query export](https://support.google.com/analytics/answer/9823238) deve ser configurado em sua propriedade
* O **relatório de eventos** permite que os anunciantes vejam seus eventos de postback. O relatório pode ser encontrado em uma ou mais coleções de relatórios.  
  Por exemplo, os relatórios de eventos podem ser encontrados nas coleções [Ciclo de vida](https://support.google.com/analytics/answer/12924233?hl=en) ou [Reportar jogos](https://support.google.com/analytics/answer/12925133?hl=en&sjid=5454549956257318969-NC), em **engajamento** > **Eventos**. Por exemplo, os relatórios de eventos podem ser encontrados na coleção [Life cycle](https://support.google.com/analytics/answer/12924233?hl=en) ou [Games reporting](https://support.google.com/analytics/answer/12925133?hl=en&sjid=5454549956257318969-NC) em **Engagement** > **Events**.

  ![Relatório de eventos do GA4](https://files.readme.io/01625878b13a46b8a87c34bf465c0ef6494a0f528960d62ce5535b69b29e7d0a-25707728713745.png)
* **O relatório de aquisição de tráfego** ajuda a entender de onde vêm os visitantes do seu site e aplicativo.

  Na coleção [Life cycle](https://support.google.com/analytics/answer/12924233?hl=en), vá para **Acquisition** > **Traffic Acquisition**).

  Para mais informações sobre o relatório de aquisição de tráfego, consulte a [documentação do Google](https://support.google.com/analytics/answer/12923437?hl=en&sjid=5454549956257318969-NC#zippy=%2Chow-do-i-filter-out-traffic-sources-from-the-report).

  ![Relatório de aquisição de tráfego do GA4](https://files.readme.io/fa51e22d1a7941666224eb668efcbfc5a3bb8cce42cf373a82f3b1e096d2a9db-25707770926353.png)

</Accordion>

<div data-zendesk-anchors="set-up-google-analytics-ga4-integration=como-funciona h_01HZXY8R12MQWKNHX2BXA68MR3=como-funciona h_01J35AP3FF599P0XA8VPWTS5R9=configurar-a-integra%C3%A7%C3%A3o-do-google-analytics-ga4 the-event-mapping-table=tabela-de-mapeamento-de-eventos h_01HZQ4ABBN0YEVFJXBNS0HTSQ5=tabela-de-mapeamento-de-eventos reserved-google-event-names=nomes-de-eventos-reservados---google h_01HZQ4ABBN6ZEB7RJQMFS0AB73=nomes-de-eventos-reservados---google" />
