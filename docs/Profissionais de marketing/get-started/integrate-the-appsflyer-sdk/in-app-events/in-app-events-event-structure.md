---
title: Eventos in-app — Estrutura dos eventos
metadata:
  keywords:
    - iOS
    - Android
    - In-App Events
    - In-App
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T10:09:16Z'
  edited_at: '2026-08-19T00:13:13Z'
  id: 4410481112081
  locale: pt
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/pt/articles/4410481112081
---
> **Visão geral:** Consulte a lista de nomes de eventos predefinidos e parâmetros de eventos para registar eventos pós-instalação na aplicação (como login, registo ou compra na aplicação).

## Resumo

Os eventos in-app que você deseja enviar exigem que o desenvolvedor implemente o código quando aplicável ao seu app. Este artigo descreve os nomes e parâmetros de eventos predefinidos.

Para ajudar você a determinar quais eventos e parâmetros registrar, consulte nossos <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#recommended-events-by-business-vertical">artigos que incluem exemplos e fluxos</Anchor> de acordo com as possíveis verticais de negócios.

## Nomes de eventos predefinidos

A seção a seguir oferece uma lista dos nomes de eventos predefinidos e do mapeamento de eventos usado para Meta ads, Google Ads, TikTok, Snap, X Ads, Amazon Ads e Criteo.

Cada nome de evento também inclui os parâmetros de evento predefinidos típicos associados a esse evento. Você pode optar por incluir quaisquer parâmetros de eventos que atendam às necessidades da sua empresa.

<div id="achievement-unlocked-af_achievement_unlocked" />

<Accordion title="Conquista desbloqueada (af_achievement_unlocked)">

**Descrição**: Usado para registar eventos de conquistas desbloqueadas

**Mapeamento de eventos:**

| A AppsFlyer | af\_achievement\_unlocked |
| --- | --- |
| Anúncios Meta | fb\_mobile\_achievement\_unlocked |
| Google Ads | unlock\_achievement |
| Tiktok | UnlockAchievement |
| Snap | ACHIEVEMENT\_UNLOCKED |
| AppsFlyer | ACHIEVEMENT\_UNLOCKED |
| Anúncios da Amazon | - |
| Criteo | achievement |
| Meta Ads | DESBLOQUEAR\_CONQUISTA |

**Parâmetro típico:**

Clique no link para ver o mapeamento para SRNs.

* [af\_description](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="ad-click-af_ad_click" />

<Accordion title="Clique em anúncio (af_ad_click)">

**Descrição**: Usado para registar cliques em anúncios exibidos na aplicação

**Descrição**: moeda usada para a compra

| A AppsFlyer | af\_ad\_click |
| --- | --- |
| Anúncios Meta | AdClick |
| Google Ads | - |
| Tiktok | InAppADClick |
| Snap | AD\_CLICK |
| AppsFlyer | - |
| Anúncios da Amazon | - |
| Criteo | - |

**Parâmetros típicos:**

Clique nos links para visualizar o mapeamento para SRNs.

* [af\_adrev\_ad\_type](/docs/in-app-events-event-structure#af_adrev_ad_type)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)

</Accordion>

<div id="ad-view-af_ad_view" />

<Accordion title="Visualização de anúncio (af_ad_view)">

**Descrição**: Usado para registar visualizações de anúncios exibidos na aplicação

**Mapeamento de eventos:**

| A AppsFlyer | af\_ad\_view |
| --- | --- |
| Anúncios Meta | AdImpression |
| Google Ads | - |
| Tiktok | InAppADImpr |
| Snap | AD\_VIEW |
| AppsFlyer | - |
| Anúncios da Amazon | - |
| Criteo | - |

**Parâmetros típicos:**

Clique nos links para visualizar o mapeamento para SRNs.

* [af\_adrev\_ad\_type](/docs/in-app-events-event-structure#af_adrev_ad_type)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)

</Accordion>

<div id="add-payment-info-af_add_payment_info" />

<Accordion title="Adicionar informações de pagamento (af_add_payment_info)">

**Descrição**: Usado para registar o estado da configuração das informações de pagamento

Presente nos seguintes setores: <Anchor target="_blank" href="/marketers/pt/docs/recommended-ride-hailing-app-events#add-payment-info-af_add_payment_info">Transporte</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/recommended-flight-booking-app-events#add-payment-info-af_add_payment_info">Reserva de voos</Anchor>

**Descrição**: usado para registrar eventos de reservas de viagem (e associar receita a eles) Para relatar um evento que contém vários itens, clique <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">aqui</Anchor>.

| A AppsFlyer | af\_add\_payment\_info |
| --- | --- |
| Anúncios Meta | fb\_mobile\_add\_payment\_info |
| Google Ads | add\_payment\_info |
| Tiktok | AddPaymentInfo |
| Snap | ADD\_BILLING |
| AppsFlyer | ADDED\_PAYMENT\_INFO |
| Anúncios da Amazon | - |
| Criteo | ADD\_BILLING |
| af\_purchase\_currency | ADICIONAR\_INFORMAÇÕES\_DE\_PAGAMENTO |

**Parâmetro típico:**

Clique no link para ver o mapeamento para SRNs.

* [af\_success](/docs/in-app-events-event-structure#af_success)

</Accordion>

<div id="add-to-cart-af_add_to_cart" />

<Accordion title="Adicionar ao carrinho (af_add_to_cart)">

**Descrição**: Utilizado para registar eventos de adição ao carrinho de itens específicos. Para reportar um evento com vários itens, clique <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">aqui</Anchor>.

**Aparece nestas verticais:** <Anchor target="_blank" href="/marketers/pt/docs/recommended-ecommerce-app-events#add-to-cart-af_add_to_cart">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/recommended-healthcare-app-events#add-to-cart-af_add_to_cart">Saúde</Anchor>

**Mapeamento de eventos:**

| A AppsFlyer | af\_add\_to\_cart |
| --- | --- |
| Anúncios Meta | fb\_mobile\_add\_to\_cart |
| Google Ads | adicionar\_ao\_carrinho |
| Tiktok | AddToCart |
| Snap | ADD\_CART |
| AppsFlyer | ADD\_TO\_CART |
| Anúncios da Amazon | ADD\_TO\_SHOPPING\_CART |
| Criteo | viewBasket |
| af\_purchase\_currency | ADD\_TO\_CART |

**Parâmetros típicos:**

Clique nos links para visualizar o mapeamento para SRNs.

* [af\_preço](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_quantity](/docs/in-app-events-event-structure#af_quantity)

</Accordion>

<div id="add-to-wishlist-af_add_to_wishlist" />

<Accordion title="Adicionar à lista de desejos (af_add_to_wishlist)">

**Descrição**: Utilizado para registar eventos de adição à lista de desejos de itens específicos. Para relatar um evento que contém vários itens, clique <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">aqui</Anchor>.

**Aparece nestas verticais:** <Anchor target="_blank" href="/marketers/pt/docs/recommended-ecommerce-app-events#add-to-wishlist-af_add_to_wishlist">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/recommended-hotel-booking-app-events#add-to-wishlist-af_add_to_wishlist">Reserva de hotel</Anchor>

**Mapeamento de eventos:**

| A AppsFlyer | af\_add\_to\_wishlist |
| --- | --- |
| Anúncios Meta | fb\_mobile\_add\_to\_wishlist |
| Google Ads | add\_to\_wishlist |
| Tiktok | AddToWishlist |
| Snap | ADD\_TO\_WISHLIST |
| AppsFlyer | ADD\_TO\_WISHLIST |
| Anúncios da Amazon | - |
| Criteo | - |
| af\_purchase\_currency | ADD\_TO\_WISHLIST |

**Parâmetros típicos:**

Clique nos links para visualizar o mapeamento para SRNs.

* [af\_preço](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_quantity](/docs/in-app-events-event-structure#af_quantity)

</Accordion>

<div id="app-open-af_app_opened" />

<Accordion title="Abertura do aplicativo (af_app_opened)">

Mapeamento de eventos:

| A AppsFlyer | af\_app\_opened |
| --- | --- |
| Meta Ads | INÍCIO\_DA\_SESSÃO |

</Accordion>

<div id="complete-registration-af_complete_registration" />

<Accordion title="Cadastro completo (af_complete_registration)">

**Descrição**: usado para registrar métodos de cadastro do usuário

**Aparece nestas verticais:** <Anchor target="_blank" href="/marketers/pt/docs/recommended-gaming-app-events#complete-registration-af_complete_registration">Jogos</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/recommended-ecommerce-app-events#complete-registration-af_complete_registration">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/recommended-entertainment-app-events#complete-registration-af_complete_registration">Entretenimento</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/recommended-finance-and-banking-app-events#complete-registration-af_complete_registration">Finanças e serviços bancários</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/recommended-p2p-lending-app-events#complete-registration-af_complete_registration">Empréstimo P2P</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/recommended-online-education-app-events#complete-registration-af_complete_registration">Educação online</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/recommended-ride-hailing-app-events#complete-registration-af_complete_registration">Transporte de passageiros por aplicativo</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/recommended-hotel-booking-app-events#complete-registration-af_complete_registration">Reserva de hotel</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/recommended-healthcare-app-events#complete-registration-af_complete_registration">Cuidados de saúde</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/recommended-telecommunication-app-events#complete-registration-af_complete_registration">Telecomunicação</Anchor>

**Mapeamento de eventos:**

| A AppsFlyer | af\_complete\_registration |
| --- | --- |
| Anúncios Meta | fb\_mobile\_complete\_registration |
| Google Ads | sign\_up |
| Tiktok | Registro |
| Snap | SIGN\_UP |
| AppsFlyer | SIGN\_UP |
| Anúncios da Amazon | SIGN\_UP |
| Criteo | - |
| Atenção | CONCLUIR\_CADASTRO |

**Parâmetro típico:**

Clique no link para ver o mapeamento para SRNs.

* [af\_registration\_method](/docs/in-app-events-event-structure#af_registration_method)

</Accordion>

<div id="content-view-af_content_view" />

<Accordion title="Visualização de conteúdo (af_content_view)">

**Descrição**: usado para registrar eventos de gasto com créditos. Para relatar um evento que contém vários itens, clique <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">aqui</Anchor>.

**Aparece nestas verticais:** <Anchor target="_blank" href="/marketers/pt/docs/recommended-ecommerce-app-events#content-view-af_content_view">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/recommended-flight-booking-app-events#content-view-af_content_view">Reserva de voos</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/recommended-hotel-booking-app-events#content-view-af_content_view">Reserva de hotel</Anchor>

**Mapeamento de eventos:**

| A AppsFlyer | af\_content\_view |
| --- | --- |
| Anúncios Meta | fb\_mobile\_content\_view |
| Google Ads | view\_item |
| Tiktok | ViewContent |
| Snap | VIEW\_CONTENT |
| AppsFlyer | CONTENT\_VIEW |
| Anúncios da Amazon | PAGE\_VIEW |
| Criteo | viewProduct |
| Meta Ads | VIEW\_CONTENT |

**Parâmetros típicos:**

Clique nos parâmetros relevantes para as necessidades do seu negócio para visualizar o mapeamento para SRNs.

* [af\_preço](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_content\_list](/docs/in-app-events-event-structure#af_content_list)
* [af\_date\_a](/docs/in-app-events-event-structure#af_date_a)
* [af\_date\_b](/docs/in-app-events-event-structure#af_date_b)
* [af\_departing\_departure\_date](/docs/in-app-events-event-structure#af_departing_departure_date)
* [af\_returning\_departure\_date](/docs/in-app-events-event-structure#af_returning_departure_date)
* [af\_destination\_a](/docs/in-app-events-event-structure#af_destination_a)
* [af\_destination\_b](/docs/in-app-events-event-structure#af_destination_b)
* [af\_destination\_list](/docs/in-app-events-event-structure#af_destination_list)
* [af\_city](/docs/in-app-events-event-structure#af_city)
* [af\_region](/docs/in-app-events-event-structure#af_region)
* [af\_country](/docs/in-app-events-event-structure#af_country)
* [af\_departing\_arrival\_date](/docs/in-app-events-event-structure#af_departing_arrival_date)
* [af\_returning\_arrival\_date](/docs/in-app-events-event-structure#af_returning_arrival_date)
* [af\_suggested\_destinations](/docs/in-app-events-event-structure#af_suggested_destinations)
* [af\_travel\_start](/docs/in-app-events-event-structure#af_travel_start)
* [af\_travel\_end](/docs/in-app-events-event-structure#af_travel_end)
* [af\_num\_adults](/docs/in-app-events-event-structure#af_num_adults)
* [af\_num\_children](/docs/in-app-events-event-structure#af_num_children)
* [af\_num\_infants](/docs/in-app-events-event-structure#af_num_infants)
* [af\_class](/docs/in-app-events-event-structure#af_class)
* [af\_suggested\_hotels](/docs/in-app-events-event-structure#af_suggested_hotels)
* [af\_user\_score](/docs/in-app-events-event-structure#af_user_score)
* [af\_hotel\_score](/docs/in-app-events-event-structure#af_hotel_score)
* [af\_preço](/docs/in-app-events-event-structure#af_price)
* [af\_preferred\_star\_ratings](/docs/in-app-events-event-structure#af_preferred_star_ratings)
* [af\_preferred\_price\_range](/docs/in-app-events-event-structure#af_preferred_price_range)
* [af\_preferred\_neighborhoods](/docs/in-app-events-event-structure#af_preferred_neighborhoods)
* [af\_preferred\_num\_stops](/docs/in-app-events-event-structure#af_preferred_num_stops)

</Accordion>

<div id="initiated-checkout-af_initiated_checkout" />

<Accordion title="Check-out iniciado (af_initiated_checkout)">

**Descrição**: usado para registrar eventos de compra (e associar receita a eles). Para relatar um evento que contém vários itens, clique <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">aqui</Anchor>.

**Aparece nas verticais:** <Anchor target="_blank" href="/marketers/pt/docs/recommended-ecommerce-app-events#initiated-checkout-af_initiated_checkout">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/recommended-hotel-booking-app-events#initiated-checkout-af_initiated_checkout">Reserva de hotel</Anchor>

**Mapeamento de eventos:**

| A AppsFlyer | af\_initiated\_checkout |
| --- | --- |
| Anúncios Meta | fb\_mobile\_initiated\_checkout |
| Google Ads | begin\_checkout |
| Tiktok | Checkout |
| Snap | START\_CHECKOUT |
| AppsFlyer | CHECKOUT\_INITIATED |
| Anúncios da Amazon | CHECKOUT |
| Criteo | viewBasket |
| Meta Ads | INICIAR\_CHECKOUT |

**Parâmetros típicos:**

Clique nos parâmetros relevantes para as necessidades do seu negócio para visualizar o mapeamento para SRNs.

* [af\_preço](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_quantity](/docs/in-app-events-event-structure#af_quantity)
* [af\_payment\_info\_available](/docs/in-app-events-event-structure#af_payment_info_available)
* [af\_content\_list](/docs/in-app-events-event-structure#af_content_list)
* [af\_date\_a](/docs/in-app-events-event-structure#af_date_a)
* [af\_date\_b](/docs/in-app-events-event-structure#af_date_b)
* [af\_departing\_departure\_date](/docs/in-app-events-event-structure#af_departing_departure_date)
* [af\_returning\_departure\_date](/docs/in-app-events-event-structure#af_returning_departure_date)
* [af\_destination\_a](/docs/in-app-events-event-structure#af_destination_a)
* [af\_destination\_b](/docs/in-app-events-event-structure#af_destination_b)
* [af\_destination\_list](/docs/in-app-events-event-structure#af_destination_list)
* [af\_city](/docs/in-app-events-event-structure#af_city)
* [af\_region](/docs/in-app-events-event-structure#af_region)
* [af\_country](/docs/in-app-events-event-structure#af_country)
* [af\_departing\_arrival\_date](/docs/in-app-events-event-structure#af_departing_arrival_date)
* [af\_returning\_arrival\_date](/docs/in-app-events-event-structure#af_returning_arrival_date)
* [af\_suggested\_destinations](/docs/in-app-events-event-structure#af_suggested_destinations)
* [af\_travel\_start](/docs/in-app-events-event-structure#af_travel_start)
* [af\_travel\_end](/docs/in-app-events-event-structure#af_travel_end)
* [af\_num\_adults](/docs/in-app-events-event-structure#af_num_adults)
* [af\_num\_children](/docs/in-app-events-event-structure#af_num_children)
* [af\_num\_infants](/docs/in-app-events-event-structure#af_num_infants)
* [af\_class](/docs/in-app-events-event-structure#af_class)
* [af\_suggested\_hotels](/docs/in-app-events-event-structure#af_suggested_hotels)
* [af\_user\_score](/docs/in-app-events-event-structure#af_user_score)
* [af\_hotel\_score](/docs/in-app-events-event-structure#af_hotel_score)
* [af\_preço](/docs/in-app-events-event-structure#af_price)
* [af\_preferred\_star\_ratings](/docs/in-app-events-event-structure#af_preferred_star_ratings)
* [af\_preferred\_price\_range](/docs/in-app-events-event-structure#af_preferred_price_range)
* [af\_preferred\_neighborhoods](/docs/in-app-events-event-structure#af_preferred_neighborhoods)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_preferred\_num\_stops](/docs/in-app-events-event-structure#af_preferred_num_stops)

</Accordion>

<div id="invite-af_invite" />

<Accordion title="Convite (af_invite)">

**Descrição**: usado para registrar eventos de convites (sociais)

**Aparece nestas verticais:** <Anchor target="_blank" href="/marketers/pt/docs/recommended-gaming-app-events#invite-af_invite">Jogos</Anchor>

**Mapeamento de eventos:**

| A AppsFlyer | af\_invite |
| --- | --- |
| Anúncios Meta | - |
| Google Ads | invite |
| Tiktok | - |
| Snap | INVITE |
| AppsFlyer | INVITE |
| Anúncios da Amazon | - |
| Criteo | - |

**Parâmetro típico:**

Clique no link para ver o mapeamento para SRNs.

* [af\_description](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="lead-lead" />

<Accordion title="Lead (lead)">

Mapeamento de eventos:

| A AppsFlyer | lead |
| --- | --- |
| af\_purchase\_currency | LEAD |

</Accordion>

<div id="level-achieved-af_level_achieved" />

<Accordion title="Nível alcançado (af_level_achieved)">

**Descrição**: usado para registrar eventos no nível do jogo

**Aparece nestas verticais:** <Anchor target="_blank" href="/marketers/pt/docs/recommended-gaming-app-events#level-achieved-af_level_achieved">Jogos</Anchor>

**Mapeamento de eventos:**

| A AppsFlyer | af\_level\_achieved |
| --- | --- |
| Anúncios Meta | fb\_mobile\_level\_achieved |
| Google Ads | level\_up |
| Tiktok | AchieveLevel |
| Snap | LEVEL\_COMPLETE |
| AppsFlyer | LEVEL\_ACHIEVED |
| Anúncios da Amazon | - |
| Criteo | userLevel |
| Atenção | ATINGIR\_O\_NÍVEL |

**Parâmetros típicos:**

Clique nos links para visualizar o mapeamento para SRNs.

* [af\_level](/docs/in-app-events-event-structure#af_level)
* [af\_score](/docs/in-app-events-event-structure#af_score)

</Accordion>

<div id="list-view-af_list_view" />

<Accordion title="Visualização de lista (af_list_view)">

**Descrição**: usado para registrar eventos de visualização de lista

**Aparece nestas verticais:** <Anchor target="_blank" href="/marketers/pt/docs/recommended-ecommerce-app-events#list-view-af_list_view">eCommerce</Anchor>

**Mapeamento de eventos:**

| A AppsFlyer | af\_list\_view |
| --- | --- |
| Anúncios Meta | - |
| Google Ads | view\_item\_list |
| Tiktok | - |
| Snap | LIST\_VIEW |
| AppsFlyer | - |
| Anúncios da Amazon | - |
| Criteo | viewListing |

**Parâmetros típicos:**

Clique nos links para visualizar o mapeamento para SRNs.

* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_list](/docs/in-app-events-event-structure#af_content_list)

</Accordion>

<div id="login-af_login" />

<Accordion title="Login (af_login)">

**Descrição**: usado para registrar eventos de login do usuário

**Aparece nestas verticais:** <Anchor target="_blank" href="/marketers/pt/docs/recommended-gaming-app-events#login-af_login">Jogos</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/recommended-ecommerce-app-events#login-af_login">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/recommended-entertainment-app-events#login-af_login">Entretenimento</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/recommended-finance-and-banking-app-events#login-af_login">Finanças e serviços bancários</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/recommended-online-education-app-events#login-af_login">Educação online</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/recommended-hotel-booking-app-events#login-af_login">Reserva de hotel</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/recommended-healthcare-app-events#login-af_login">Cuidados de saúde</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/recommended-telecommunication-app-events#login-af_login">Telecomunicação</Anchor>

**Mapeamento de eventos:**

| A AppsFlyer | af\_login |
| --- | --- |
| Anúncios Meta | - |
| Google Ads | Iniciar sessão |
| Tiktok | Login |
| Snap | Iniciar sessão |
| AppsFlyer | Iniciar sessão |
| Anúncios da Amazon | - |
| Criteo | - |

</Accordion>

<div id="opened-from-push-notification-af_opened_from_push_notification" />

<Accordion title="Aberto a partir de notificação push (af_opened_from_push_notification)">

**Descrição**: usado para registrar eventos de abertura do aplicativo a partir de notificação push

**Mapeamento de eventos:**

| A AppsFlyer | af\_opened\_from\_push\_notification |
| --- | --- |
| Anúncios Meta | - |
| Google Ads | notification\_open |
| Tiktok | - |
| Snap | - |
| AppsFlyer | - |
| Anúncios da Amazon | - |
| Criteo | - |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="Compra (af_purchase)">

**Descrição**: usado para registrar compras de assinaturas pagas

* Para uma lista dos símbolos de moeda compatíveis com a AppsFlyer, clique <Anchor target="_blank" href="https://docs.openexchangerates.org/docs/supported-currencies">aqui</Anchor>.
* **Descrição**: usado para registrar eventos de exibição de conteúdo Para relatar um evento que contém vários itens, clique <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">aqui</Anchor>.
* Para registrar e validar este evento, consulte <Anchor target="_blank" href="/marketers/pt/docs/purchase-and-subscription-validation-overview">Validação de compra e assinatura</Anchor>.

Aparece nas verticais: <Anchor target="_blank" href="/marketers/pt/docs/recommended-gaming-app-events#purchase-af_purchase">Jogos</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/recommended-ecommerce-app-events#purchase-af_purchase">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/recommended-online-education-app-events#purchase-af_purchase">educação online</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/recommended-healthcare-app-events#purchase-af_purchase">saúde</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/recommended-telecommunication-app-events#purchase-af_purchase">telecomunicações</Anchor>

**Mapeamento de eventos:**

| A AppsFlyer | af\_compra |
| --- | --- |
| Anúncios Meta | fb\_mobile\_purchase |
| Google Ads | in\_app\_purchase |
| Tiktok | Compras |
| Snap | COMPRAR |
| AppsFlyer | COMPRAR |
| Anúncios da Amazon | OFF\_AMAZON\_PURCHASES |
| Criteo | transactionConfirmation |
| Meta Ads | COMPRAR |

**Parâmetros típicos:**

Clique nos parâmetros relevantes para as necessidades do seu negócio para visualizar o mapeamento para SRNs.

* [af\_revenue](/docs/in-app-events-event-structure#af_revenue)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_quantity](/docs/in-app-events-event-structure#af_quantity)
* [af\_validated](/docs/in-app-events-event-structure#af_validated)
* [af\_receipt\_id](/docs/in-app-events-event-structure#af_receipt_id)
* [af\_order\_id](/docs/in-app-events-event-structure#af_order_id)
* [af\_content\_list](/docs/in-app-events-event-structure#af_content_list)
* [af\_date\_a](/docs/in-app-events-event-structure#af_date_a)
* [af\_date\_b](/docs/in-app-events-event-structure#af_date_b)
* [af\_departing\_departure\_date](/docs/in-app-events-event-structure#af_departing_departure_date)
* [af\_returning\_departure\_date](/docs/in-app-events-event-structure#af_returning_departure_date)
* [af\_destination\_a](/docs/in-app-events-event-structure#af_destination_a)
* [af\_destination\_b](/docs/in-app-events-event-structure#af_destination_b)
* [af\_destination\_list](/docs/in-app-events-event-structure#af_destination_list)
* [af\_city](/docs/in-app-events-event-structure#af_city)
* [af\_region](/docs/in-app-events-event-structure#af_region)
* [af\_country](/docs/in-app-events-event-structure#af_country)
* [af\_departing\_arrival\_date](/docs/in-app-events-event-structure#af_departing_arrival_date)
* [af\_returning\_arrival\_date](/docs/in-app-events-event-structure#af_returning_arrival_date)
* [af\_suggested\_destinations](/docs/in-app-events-event-structure#af_suggested_destinations)
* [af\_travel\_start](/docs/in-app-events-event-structure#af_travel_start)
* [af\_travel\_end](/docs/in-app-events-event-structure#af_travel_end)
* [af\_num\_adults](/docs/in-app-events-event-structure#af_num_adults)
* [af\_num\_children](/docs/in-app-events-event-structure#af_num_children)
* [af\_num\_infants](/docs/in-app-events-event-structure#af_num_infants)
* [af\_class](/docs/in-app-events-event-structure#af_class)
* [af\_suggested\_hotels](/docs/in-app-events-event-structure#af_suggested_hotels)
* [af\_user\_score](/docs/in-app-events-event-structure#af_user_score)
* [af\_hotel\_score](/docs/in-app-events-event-structure#af_hotel_score)
* [af\_preço](/docs/in-app-events-event-structure#af_price)
* [af\_preferred\_star\_ratings](/docs/in-app-events-event-structure#af_preferred_star_ratings)
* [af\_preferred\_price\_range](/docs/in-app-events-event-structure#af_preferred_price_range)
* [af\_preferred\_neighborhoods](/docs/in-app-events-event-structure#af_preferred_neighborhoods)
* [af\_preferred\_num\_stops](/docs/in-app-events-event-structure#af_preferred_num_stops)

</Accordion>

<div id="rate-af_rate" />

<Accordion title="Taxa (af_rate)">

**Descrição**: usado para registrar eventos de classificação do aplicativo/item. Para relatar um evento que contém vários itens, clique <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">aqui</Anchor>.

**Mapeamento de eventos:**

| A AppsFlyer | af\_rate |
| --- | --- |
| Anúncios Meta | fb\_mobile\_rate |
| Google Ads | submit\_rating |
| Tiktok | Classificar |
| Snap | RATE |
| AppsFlyer | RATED |
| Anúncios da Amazon | - |
| Criteo | - |

**Parâmetros típicos:**

Clique nos links para visualizar o mapeamento para SRNs.

* [af\_rating\_value](/docs/in-app-events-event-structure#af_rating_value)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)
* [af\_max\_rating\_value](/docs/in-app-events-event-structure#af_max_rating_value)

</Accordion>

<div id="reengage-af_re_engage" />

<Accordion title="Reengajar (af_re_engage)">

**Descrição**: usado para registrar eventos de reengajamento do usuário

**Mapeamento de eventos:**

| A AppsFlyer | af\_re\_engage |
| --- | --- |
| Anúncios Meta | - |
| Google Ads | custom\_event |
| Snap | - |
| AppsFlyer | RE\_ENGAGE |
| Anúncios da Amazon | - |
| Criteo | - |

**Parâmetro típico:**

Clique no link para ver o mapeamento para SRNs.

* [af\_description](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="search-af_search" />

<Accordion title="Pesquisa (af_search)">

**Descrição**: usado para registrar eventos de pesquisa

**Aparece nestas verticais:** <Anchor target="_blank" href="/marketers/pt/docs/recommended-ecommerce-app-events#search-af_search">eCommerce</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/recommended-flight-booking-app-events#search-af_search">Reserva de voo</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/recommended-hotel-booking-app-events#search-af_search">Reserva de hotel</Anchor>

**Mapeamento de eventos:**

| A AppsFlyer | af\_search |
| --- | --- |
| Anúncios Meta | fb\_mobile\_search |
| Google Ads | view\_search\_results |
| Tiktok | Busca |
| Snap | Pesquisar |
| AppsFlyer | Pesquisar |
| Anúncios da Amazon | Pesquisar |
| Criteo | viewSearch |
| af\_purchase\_currency | Pesquisar |

**Parâmetros típicos:**

Clique nos parâmetros relevantes para as necessidades do seu negócio para visualizar o mapeamento para SRNs.

* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_search\_string](/docs/in-app-events-event-structure#af_search_string)
* [af\_date\_a](/docs/in-app-events-event-structure#af_date_a)
* [af\_date\_b](/docs/in-app-events-event-structure#af_date_b)
* [af\_destination\_a](/docs/in-app-events-event-structure#af_destination_a)
* [af\_destination\_b](/docs/in-app-events-event-structure#af_destination_b)
* [af\_success](/docs/in-app-events-event-structure#af_success)
* [af\_content\_list](/docs/in-app-events-event-structure#af_content_list)
* [af\_departing\_departure\_date](/docs/in-app-events-event-structure#af_departing_departure_date)
* [af\_returning\_departure\_date](/docs/in-app-events-event-structure#af_returning_departure_date)
* [af\_destination\_list](/docs/in-app-events-event-structure#af_destination_list)
* [af\_city](/docs/in-app-events-event-structure#af_city)
* [af\_region](/docs/in-app-events-event-structure#af_region)
* [af\_country](/docs/in-app-events-event-structure#af_country)
* [af\_departing\_arrival\_date](/docs/in-app-events-event-structure#af_departing_arrival_date)
* [af\_returning\_arrival\_date](/docs/in-app-events-event-structure#af_returning_arrival_date)
* [af\_suggested\_destinations](/docs/in-app-events-event-structure#af_suggested_destinations)
* [af\_travel\_start](/docs/in-app-events-event-structure#af_travel_start)
* [af\_travel\_end](/docs/in-app-events-event-structure#af_travel_end)
* [af\_num\_adults](/docs/in-app-events-event-structure#af_num_adults)
* [af\_num\_children](/docs/in-app-events-event-structure#af_num_children)
* [af\_num\_infants](/docs/in-app-events-event-structure#af_num_infants)
* [af\_class](/docs/in-app-events-event-structure#af_class)
* [af\_suggested\_hotels](/docs/in-app-events-event-structure#af_suggested_hotels)
* [af\_user\_score](/docs/in-app-events-event-structure#af_user_score)
* [af\_hotel\_score](/docs/in-app-events-event-structure#af_hotel_score)
* [af\_preço](/docs/in-app-events-event-structure#af_price)
* [af\_preferred\_star\_ratings](/docs/in-app-events-event-structure#af_preferred_star_ratings)
* [af\_preferred\_price\_range](/docs/in-app-events-event-structure#af_preferred_price_range)
* [af\_preferred\_neighborhoods](/docs/in-app-events-event-structure#af_preferred_neighborhoods)
* [af\_preferred\_num\_stops](/docs/in-app-events-event-structure#af_preferred_num_stops)

</Accordion>

<div id="share-af_share" />

<Accordion title="Compartilhar (af_share)">

**Descrição**: usado para registrar eventos de compartilhamento

**Aparece nestas verticais:** <Anchor target="_blank" href="/marketers/pt/docs/recommended-gaming-app-events#share-af_share">Jogos</Anchor>

**Mapeamento de eventos:**

| A AppsFlyer | af\_share |
| --- | --- |
| Anúncios Meta | - |
| Google Ads | compartilhar |
| Tiktok | - |
| Snap | Compartilhar |
| AppsFlyer | Compartilhar |
| Anúncios da Amazon | - |
| Criteo | - |

**Parâmetro típico:**

Clique no link para ver o mapeamento para SRNs.

* [af\_description](/docs/in-app-events-event-structure#af_description)

</Accordion>

<div id="spent-credits-af_spent_credits" />

<Accordion title="Créditos utilizados (af_spent_credits)">

**Descrição**: usado para registrar eventos de atualização. Para relatar um evento que contém vários itens, clique <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">aqui</Anchor>.

**Aparece nos seguintes setores:** <Anchor target="_blank" href="/marketers/pt/docs/recommended-ride-hailing-app-events#spent-credits-af_spent_credits">Serviços de transporte por aplicativo</Anchor>

**Mapeamento de eventos:**

| A AppsFlyer | af\_spent\_credits |
| --- | --- |
| Anúncios Meta | fb\_mobile\_spent\_credits |
| Google Ads | spend\_virtual\_currency |
| Tiktok | SpendCredits |
| Snap | SPENT\_CREDITS |
| AppsFlyer | SPENT\_CREDITS |
| Anúncios da Amazon | - |
| Criteo | transactionConfirmation |

**Parâmetros típicos:**

Clique nos links para visualizar o mapeamento para SRNs.

* [af\_preço](/docs/in-app-events-event-structure#af_price)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)

</Accordion>

<div id="start-trial-af_start_trial" />

<Accordion title="Iniciar teste gratuito (af_start_trial)">

**Descrição**: usado para registrar compras de assinaturas pagas. Para registrar e validar este evento, consulte <Anchor target="_blank" href="/marketers/pt/docs/purchase-and-subscription-validation-overview">Validação de compra e assinatura</Anchor>.

**Aparece nestas verticais:** <Anchor target="_blank" href="/marketers/pt/docs/recommended-entertainment-app-events#start-trial-af_start_trial">Entretenimento</Anchor>

**Mapeamento de eventos:**

| A AppsFlyer | af\_start\_trial |
| --- | --- |
| Anúncios Meta | Iniciar avaliação |
| Google Ads | - |
| Tiktok | Iniciar avaliação |
| Snap | START\_TRIAL |
| AppsFlyer | - |
| Anúncios da Amazon | - |
| Criteo | - |
| fb\_purchase\_currency | START\_TRIAL |

**Parâmetros típicos:**

Clique nos links para visualizar o mapeamento para SRNs.

* [af\_preço](/docs/in-app-events-event-structure#af_price)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_subscription\_id](/docs/in-app-events-event-structure#af_subscription_id)

> 📘 **Nota**
>
> Se você estiver mapeando esse evento para o evento Meta ads StartTrial e quiser associar receita, use o parâmetro af\_price em vez do parâmetro af\_revenue.

</Accordion>

<div id="subscription-af_subscribe" />

<Accordion title="Assinatura (af_subscribe)">

**Descrição**: usado para registrar conclusões de tutoriais. Para relatar um evento que contém vários itens, clique <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">aqui</Anchor>.

**Aparece nestas verticais:** <Anchor target="_blank" href="/marketers/pt/docs/recommended-entertainment-app-events#subscription-af_subscribe">Entretenimento</Anchor>

**Mapeamento de eventos:**

| A AppsFlyer | af\_subscribe |
| --- | --- |
| Anúncios Meta | Enviar inscrição |
| Google Ads | - |
| Tiktok | Enviar inscrição |
| Snap | SUBSCRIBE |
| AppsFlyer | - |
| Anúncios da Amazon | SUBSCRIBE |
| Criteo | SUBSCRIBE |
| af\_purchase\_currency | SUBSCRIBE |

**Parâmetros típicos:**

Clique nos links para visualizar o mapeamento para SRNs.

* [af\_revenue](/docs/in-app-events-event-structure#af_revenue)
* [af\_currency](/docs/in-app-events-event-structure#af_currency)
* [af\_subscription\_id](/docs/in-app-events-event-structure#af_subscription_id)

</Accordion>

<div id="travel-booking-af_travel_booking" />

<Accordion title="Reserva de viagem (af_travel_booking)">

**Descrição**: usado para registrar conclusões de tutoriais. Para relatar um evento que contém vários itens, clique <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">aqui</Anchor>.

**Aparece nestas verticais:** <Anchor target="_blank" href="/marketers/pt/docs/recommended-flight-booking-app-events#travel-booking-af_travel_booking">Reserva de voo</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/recommended-hotel-booking-app-events#travel-booking-af_travel_booking">Reserva de hotel</Anchor>

**Mapeamento de eventos:**

| A AppsFlyer | af\_travel\_booking |
| --- | --- |
| Anúncios Meta | fb\_mobile\_purchase |
| Google Ads | ecommerce\_purchase |
| Tiktok | Compras |
| Snap | RESERVE |
| AppsFlyer | COMPRAR |
| Anúncios da Amazon | - |
| Criteo | transactionConfirmation |

**Parâmetros típicos:**

Clique nos parâmetros relevantes para as necessidades do seu negócio para visualizar o mapeamento para SRNs.

* [af\_revenue](/docs/in-app-events-event-structure#af_revenue)
* [af\_customer\_user\_id](/docs/in-app-events-event-structure#af_customer_user_id)
* [af\_content\_type](/docs/in-app-events-event-structure#af_content_type)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_class](/docs/in-app-events-event-structure#af_class)
* [af\_date\_a](/docs/in-app-events-event-structure#af_date_a)
* [af\_date\_b](/docs/in-app-events-event-structure#af_date_b)
* [af\_destination\_a](/docs/in-app-events-event-structure#af_destination_a)
* [af\_destination\_b](/docs/in-app-events-event-structure#af_destination_b)
* [af\_success](/docs/in-app-events-event-structure#af_success)
* [af\_content\_list](/docs/in-app-events-event-structure#af_content_list)
* [af\_departing\_departure\_date](/docs/in-app-events-event-structure#af_departing_departure_date)
* [af\_returning\_departure\_date](/docs/in-app-events-event-structure#af_returning_departure_date)
* [af\_destination\_list](/docs/in-app-events-event-structure#af_destination_list)
* [af\_city](/docs/in-app-events-event-structure#af_city)
* [af\_region](/docs/in-app-events-event-structure#af_region)
* [af\_country](/docs/in-app-events-event-structure#af_country)
* [af\_departing\_arrival\_date](/docs/in-app-events-event-structure#af_departing_arrival_date)
* [af\_returning\_arrival\_date](/docs/in-app-events-event-structure#af_returning_arrival_date)
* [af\_suggested\_destinations](/docs/in-app-events-event-structure#af_suggested_destinations)
* [af\_travel\_start](/docs/in-app-events-event-structure#af_travel_start)
* [af\_travel\_end](/docs/in-app-events-event-structure#af_travel_end)
* [af\_num\_adults](/docs/in-app-events-event-structure#af_num_adults)
* [af\_num\_children](/docs/in-app-events-event-structure#af_num_children)
* [af\_num\_infants](/docs/in-app-events-event-structure#af_num_infants)
* [af\_class](/docs/in-app-events-event-structure#af_class)
* [af\_suggested\_hotels](/docs/in-app-events-event-structure#af_suggested_hotels)
* [af\_user\_score](/docs/in-app-events-event-structure#af_user_score)
* [af\_hotel\_score](/docs/in-app-events-event-structure#af_hotel_score)
* [af\_preço](/docs/in-app-events-event-structure#af_price)
* [af\_preferred\_star\_ratings](/docs/in-app-events-event-structure#af_preferred_star_ratings)
* [af\_preferred\_price\_range](/docs/in-app-events-event-structure#af_preferred_price_range)
* [af\_preferred\_neighborhoods](/docs/in-app-events-event-structure#af_preferred_neighborhoods)
* [af\_preferred\_num\_stops](/docs/in-app-events-event-structure#af_preferred_num_stops)
* [af\_order\_id](/docs/in-app-events-event-structure#af_order_id)

</Accordion>

<div id="tutorial-completion-af_tutorial_completion" />

<Accordion title="Conclusão do tutorial (af_tutorial_completion)">

**Descrição**: usado para registrar eventos de atualização. Para relatar um evento que contém vários itens, clique <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">aqui</Anchor>.

**Aparece nestas verticais:** <Anchor target="_blank" href="/marketers/pt/docs/recommended-gaming-app-events#tutorial-completion-af_tutorial_completion">Jogos</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/recommended-gaming-app-events#tutorial-completion-af_tutorial_completion">Educação online</Anchor>

**Mapeamento de eventos:**

| A AppsFlyer | af\_tutorial\_completion |
| --- | --- |
| Anúncios Meta | fb\_mobile\_tutorial\_completion |
| Google Ads | tutorial\_complete |
| Tiktok | CompleteTutorial |
| Snap | COMPLETE\_TUTORIAL |
| AppsFlyer | TUTORIAL\_COMPLETE |
| Anúncios da Amazon | - |
| Criteo | - |

**Parâmetros típicos:**

Clique nos links para visualizar o mapeamento para SRNs.

* [af\_success](/docs/in-app-events-event-structure#af_success)
* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)
* [af\_content](/docs/in-app-events-event-structure#af_content)

</Accordion>

<div id="update-af_update" />

<Accordion title="Atualização (af_update)">

**Descrição**: usado para registrar eventos de atualização. Para relatar um evento que contém vários itens, clique <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#can-i-add-multiple-items-to-a-single-transaction">aqui</Anchor>.

**Mapeamento de eventos:**

| A AppsFlyer | af\_update |
| --- | --- |
| Anúncios Meta | - |
| Google Ads | app\_update |
| Snap | - |
| AppsFlyer | UPDATE |
| Anúncios da Amazon | - |
| Criteo | - |

**Parâmetro típico:**

Clique no link para ver o mapeamento para SRNs.

* [af\_content\_id](/docs/in-app-events-event-structure#af_content_id)

</Accordion>

> 📘 **Nota**
>
> Além dos nomes de eventos predefinidos descritos nesta seção, o <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-in-app-event-mapping#mapeamento-de-eventos-predefinidos">Meta ads oferece eventos adicionais</Anchor> que são enviados sem atributos.

## Parâmetros de eventos predefinidos

A seção a seguir oferece uma lista dos parâmetros de eventos predefinidos. Cada parâmetro de evento inclui o mapeamento usado para o Meta Ads, Google Ads, Snap, X Ads e Criteo. Você pode optar por incluir qualquer um dos parâmetros em um evento.

> 📘 **Nota**
>
> Você pode ver os parâmetros do evento na coluna Valor do Evento nos <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview">relatórios de dados brutos</Anchor> (recurso premium).

<div id="af_adrev_ad_type" />

<Accordion title="af_adrev_ad_type">

**Descrição**: tipo de anúncio (por exemplo, banner ou intersticial)

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_adrev\_ad\_type |
| --- | --- |
| Anúncios Meta | ad\_type |
| Google Ads | - |
| Snap | - |
| AppsFlyer | - |
| Tiktok | - |
| Criteo | - |

</Accordion>

<div id="af_city" />

<Accordion title="af_city">

**Descrição**: cidade onde a viagem foi reservada

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_city |
| --- | --- |
| Anúncios Meta | fb\_city |
| Google Ads | - |
| Snap | - |
| AppsFlyer | - |
| Tiktok | flight\_city |
| Criteo | - |

</Accordion>

<div id="af_class" />

<Accordion title="af_class">

**Descrição**: classe do voo

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_class |
| --- | --- |
| Anúncios Meta | fb\_travel\_class |
| Google Ads | travel\_class |
| Snap | - |
| AppsFlyer | - |
| Tiktok | flight\_class |
| Criteo | - |

</Accordion>

<div id="af_content" />

<Accordion title="af_content">

**Descrição**: título do conteúdo (por exemplo, nome de uma música ou o título e episódio de um programa de TV)

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_content |
| --- | --- |
| Anúncios Meta | fb\_content |
| Google Ads | - |
| Snap | - |
| AppsFlyer | - |
| Tiktok | - |
| Criteo | - |

</Accordion>

<div id="af_content_id" />

<Accordion title="af_content_id">

**Descrição**: ID do item

**Atenção:** Os eventos predefinidos do Snapchat `af_content_id` e `af_content_id` compartilham o mesmo parâmetro de evento. Quando ambos os eventos são registrados em simultâneo, apenas o evento `af_content_list` é enviado para o Snapchat.

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_content\_id |
| --- | --- |
| Anúncios Meta | fb\_content\_id |
| Google Ads | item\_id |
| Snap | item\_ids |
| AppsFlyer | content\_id |
| Tiktok | content\_id |
| Criteo | id |

</Accordion>

<div id="af_content_list" />

<Accordion title="af_content_list">

**Descrição**: lista de IDs de conteúdo

**Observação:** Quando você usa `af_content_list`, a AppsFlyer trata a lista inteira como um único valor. As ferramentas de segmentação de audiências da AppsFlyer não podem filtrar IDs de conteúdo individuais dentro da lista. Por exemplo, se  `af_content_list` for `["ID1","ID2","ID3"]`, a ferramenta de audiências não poderá isolar nem corresponder apenas a `ID1`.

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_content\_list |
| --- | --- |
| Anúncios Meta | fb\_content\_id |
| Google Ads | item\_id |
| Snap | item\_ids |
| AppsFlyer | - |
| Tiktok | - |
| Criteo | - |

</Accordion>

<div id="af_content_type" />

<Accordion title="af_content_type">

**Descrição**: Categoria de produto

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_content\_type |
| --- | --- |
| Anúncios Meta | fb\_content\_type |
| Google Ads | item\_category |
| Snap | item\_category |
| AppsFlyer | content\_type |
| Tiktok | content\_type |
| Criteo | - |

</Accordion>

<div id="af_country" />

<Accordion title="af_country">

**Descrição**: país onde a viagem foi reservada

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_country |
| --- | --- |
| Anúncios Meta | fb\_country |
| Google Ads | - |
| Snap | - |
| AppsFlyer | - |
| Tiktok | flight\_country |
| Criteo | - |

</Accordion>

<div id="af_currency" />

<Accordion title="af_currency">

**Descrição**: código da moeda

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_currency |
| --- | --- |
| Anúncios Meta | fb\_currency |
| Google Ads | currency\_code |
| Snap | símbolos monetários |
| AppsFlyer | price\_currency |
| Tiktok | símbolos monetários |
| Anúncios da Amazon | símbolos monetários |
| Criteo | símbolos monetários |

</Accordion>

<div id="af_customer_user_id" />

<Accordion title="af_customer_user_id">

**Descrição**: ID do cliente

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_customer\_user\_id |
| --- | --- |
| Anúncios Meta | - |
| Google Ads | customer\_user\_  <br />id |
| Snap | - |
| AppsFlyer | - |
| Tiktok | - |
| Criteo | cid |

</Accordion>

<div id="af_date_a" />

<Accordion title="af_date_a">

**Descrição**: data de check-in

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_date\_a |
| --- | --- |
| Anúncios Meta | fb\_checkin\_date |
| Google Ads | start\_date |
| Snap | - |
| AppsFlyer | - |
| Tiktok | checkin\_date |
| Criteo | din |

</Accordion>

<div id="af_date_b" />

<Accordion title="af_date_b">

**Descrição**: data de check-out

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_date\_b |
| --- | --- |
| Anúncios Meta | fb\_checkout\_date |
| Google Ads | end\_date |
| Snap | - |
| AppsFlyer | - |
| Tiktok | checkout\_date |
| Criteo | dout |

</Accordion>

<div id="af_departing_arrival_date" />

<Accordion title="af_departing_arrival_date">

**Descrição**: data de chegada

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_departing\_arrival\_date |
| --- | --- |
| Anúncios Meta | fb\_departing\_arrival\_date |
| Google Ads | - |
| Snap | - |
| AppsFlyer | - |
| Tiktok | - |
| Criteo | - |

</Accordion>

<div id="af_departing_departure_date" />

<Accordion title="af_departing_departure_date">

**Descrição**: data de partida

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_departing\_ departure\_date |
| --- | --- |
| Anúncios Meta | fb\_departing\_ departure\_date |
| Google Ads | - |
| Snap | - |
| AppsFlyer | - |
| Tiktok | departing\_date |
| Criteo | - |

</Accordion>

<div id="af_description" />

<Accordion title="af_description">

**Descrição**: breve descrição (string)

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_description |
| --- | --- |
| Anúncios Meta | fb\_description |
| Google Ads | description |
| Snap | description |
| AppsFlyer | description |
| Tiktok | description |
| Criteo | ui\_achievement |

</Accordion>

<div id="af_destination_a" />

<Accordion title="af_destination_a">

**Descrição**: primeiro destino

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_destination\_a |
| --- | --- |
| Anúncios Meta | fb\_origin\_airport |
| Google Ads | origin |
| Snap | - |
| AppsFlyer | - |
| Tiktok | departing\_airport |
| Criteo | - |

</Accordion>

<div id="af_destination_b" />

<Accordion title="af_destination_b">

**Descrição**: segundo destino

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_destination\_b |
| --- | --- |
| Anúncios Meta | fb\_destination\_  <br />airport |
| Google Ads | destination |
| Snap | - |
| AppsFlyer | - |
| Tiktok | destination\_airport |
| Criteo | - |

</Accordion>

<div id="af_destination_list" />

<Accordion title="af_destination_list">

**Descrição**: lista de destinos incluídos em um catálogo de destinos (por exemplo, uma lista de museus ou restaurantes que estão perto de um hotel)

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_destination\_list |
| --- | --- |
| Anúncios Meta | fb\_destination\_ids |
| Google Ads | - |
| Snap | - |
| AppsFlyer | - |
| Tiktok | - |
| Criteo | - |

</Accordion>

<div id="af_hotel_score" />

<Accordion title="af_hotel_score">

**Descrição**: pontuação do hotel por avaliações

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_hotel\_score |
| --- | --- |
| Anúncios Meta | fb\_hotel\_score |
| Google Ads | - |
| Snap | - |
| AppsFlyer | - |
| Tiktok | - |
| Criteo | - |

</Accordion>

<div id="af_level" />

<Accordion title="af_level">

**Descrição**: nível que o usuário alcançou

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_level |
| --- | --- |
| Anúncios Meta | fb\_level |
| Google Ads | level\_up |
| Snap | level |
| AppsFlyer | level |
| Tiktok | - |
| Criteo | ui\_level |

</Accordion>

<div id="af_max_rating_value" />

<Accordion title="af_max_rating_value">

**Descrição**: topo de uma escala de classificação (por exemplo, 5 de 5)

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_max\_rating\_value |
| --- | --- |
| Anúncios Meta | fb\_max\_rating\_value |
| Google Ads | max\_rating |
| Snap | - |
| AppsFlyer | max\_rated\_value |
| Tiktok | - |
| Criteo | - |

</Accordion>

<div id="h_01NEWAFNETREVENUE0001" />

<Accordion title="af_net_revenue">

**Descrição**: receita líquida reportada para o evento. O valor representa a receita líquida de acordo com a sua própria lógica de negócios; a AppsFlyer não determina como ela é calculada e agrega o valor que você envia. Exemplos comuns: receita após taxas da loja de aplicativos e/ou impostos, margem bruta ou receita após taxas bancárias ou de serviço (eCommerce, finanças etc.). Usado para as métricas de receita líquida (Receita líquida, ROI líquido, ROAS líquido, ARPU líquido, lucro líquido) em <Anchor target="_blank" href="/marketers/pt/docs/my-dashboards">Meus dashboards</Anchor>.

O valor está na moeda da transação, expressa por af\_currency (USD por padrão). As mesmas regras de formatação que af\_revenue: sem separadores de vírgula, símbolos de moeda, caracteres especiais ou texto (por exemplo, 1234.56), com até cinco casas decimais.

**Observação:** Não há uma constante de SDK predefinida para esse parâmetro, então envie-o como um parâmetro personalizado com a chave af\_net\_revenue.

> 📘 **Atenção**
>
> Para aplicativos com a <Anchor target="_blank" href="/marketers/pt/docs/about-roi360-store-revenue">receita da loja do ROI360</Anchor> ativada, a AppsFlyer preenche af\_net\_revenue automaticamente nos eventos de compra in-app e de assinatura que registra, calculada como a receita bruta menos as taxas da loja de aplicativos e os impostos (líquida = bruta - taxas da loja - impostos).

</Accordion>

<div id="af_num_adults" />

<Accordion title="af_num_adults">

**Descrição**: número de adultos viajando

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_num\_adults |
| --- | --- |
| Anúncios Meta | fb\_num\_adults |
| Google Ads | - |
| Snap | - |
| AppsFlyer | - |
| Tiktok | num\_people |
| Criteo | - |

</Accordion>

<div id="af_num_children" />

<Accordion title="af_num_children">

**Descrição**: número de crianças viajando

Mapeamento de parâmetros:

| A AppsFlyer | af\_num\_children |
| --- | --- |
| Anúncios Meta | fb\_num\_children |
| Google Ads | - |
| Snap | - |
| AppsFlyer | - |
| Tiktok | num\_children |
| Criteo | - |

</Accordion>

<div id="af_num_infants" />

<Accordion title="af_num_infants">

**Descrição**: número de bebês viajando

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_num\_infants |
| --- | --- |
| Anúncios Meta | fb\_num\_infants |
| Google Ads | - |
| Snap | - |
| AppsFlyer | - |
| Tiktok | - |
| Criteo | - |

</Accordion>

<div id="af_order_id" />

<Accordion title="af_order_id">

**Descrição**: ID da transação

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_order\_id |
| --- | --- |
| Anúncios Meta | fb\_order\_id |
| Google Ads | order\_id |
| Snap | transaction\_id |
| AppsFlyer | - |
| Tiktok | order\_id |
| Criteo | transaction\_id |

</Accordion>

<div id="af_payment_info_available" />

<Accordion title="af_payment_info_available">

**Descrição**: informa se as informações de pagamento do usuário estão disponíveis

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_payment\_info\_available |
| --- | --- |
| Anúncios Meta | fb\_payment\_info\_available |
| Google Ads | payment\_info\_available |
| Snap | payment\_info\_available |
| AppsFlyer | user\_payment\_  <br />info |
| Tiktok | - |
| Criteo | - |

</Accordion>

<div id="af_preferred_neighborhoods" />

<Accordion title="af_preferred_neighborhoods">

**Descrição**: área na qual o hotel está localizado

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_preferred\_neighborhoods |
| --- | --- |
| Anúncios Meta | fb\_preferred\_neighborhoods |
| Google Ads | - |
| Snap | - |
| AppsFlyer | - |
| Tiktok | - |
| Criteo | - |

</Accordion>

<div id="af_preferred_num_stops" />

<Accordion title="af_preferred_num_stops">

**Descrição**: número de paradas que o usuário está procurando (por exemplo, voo direto ou sem conexões)

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_preferred\_num\_stops |
| --- | --- |
| Anúncios Meta | fb\_preferred\_num\_stops |
| Google Ads | - |
| Snap | - |
| AppsFlyer | - |
| Tiktok | - |
| Criteo | - |

</Accordion>

<div id="af_preferred_price_range" />

<Accordion title="af_preferred_price_range">

**Descrição**: Faixa de preço preferida do hotel

Mapeamento de parâmetros:

| A AppsFlyer | af\_preferred\_price\_range |
| --- | --- |
| Anúncios Meta | fb\_preferred\_price\_range |
| Google Ads | - |
| Snap | - |
| AppsFlyer | - |
| Tiktok | - |
| Criteo | - |

</Accordion>

<div id="af_preferred_star_ratings" />

<Accordion title="af_preferred_star_ratings">

**Descrição**: classificação de estrelas desejada para o hotel

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_preferred\_star\_ratings |
| --- | --- |
| Anúncios Meta | fb\_preferred\_star\_ratings |
| Google Ads | - |
| Snap | - |
| AppsFlyer | - |
| Tiktok | - |
| Criteo | - |

</Accordion>

<div id="af_price" />

<Accordion title="af_preço">

**Descrição**: preço do produto. Você pode usar af\_price como um parâmetro monetário que não é contado como receita (como um evento Adicionar ao carrinho). Esse parâmetro se refere ao preço do item individual. A quantia total de todas as compras é exibida sob o parâmetro [af\_revenue](/docs/in-app-events-event-structure#af_revenue).

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_preço |
| --- | --- |
| Anúncios Meta | fb\_price |
| Google Ads | price |
| Snap | price |
| AppsFlyer | price\_micro |
| Tiktok | price |
| Criteo | price |

</Accordion>

<div id="af_projected_revenue" />

<Accordion title="af_projected_revenue">

A receita estimada que um anunciante espera de um usuário com base nas suas interações iniciais antes de a receita real ser atingida.

</Accordion>

<div id="af_quantity" />

<Accordion title="af_quantity">

**Descrição**: número de itens

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_quantity |
| --- | --- |
| Anúncios Meta | fb\_num\_items |
| Google Ads | quantidade |
| Snap | number\_items |
| AppsFlyer | number\_items |
| Tiktok | quantidade |
| Criteo | quantidade |

</Accordion>

<div id="af_rating_value" />

<Accordion title="af_rating_value">

**Descrição**: valor de classificação selecionado

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_rating\_value |
| --- | --- |
| Anúncios Meta | \_valueToSum |
| Google Ads | Atenção |
| Snap | - |
| AppsFlyer | price\_micro |
| Tiktok | - |
| Criteo | - |

</Accordion>

<div id="af_receipt_id" />

<Accordion title="af_receipt_id">

**Descrição**: ID do recibo

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_receipt\_id |
| --- | --- |
| Anúncios Meta | - |
| Google Ads | transaction\_id |
| Snap | - |
| AppsFlyer | - |
| Tiktok | - |
| Criteo | transaction\_id |

</Accordion>

<div id="af_region" />

<Accordion title="af_region">

**Descrição**: região onde a viagem é reservada

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_region |
| --- | --- |
| Anúncios Meta | fb\_region |
| Google Ads | - |
| Snap | - |
| AppsFlyer | - |
| Tiktok | flight\_region |
| Criteo | - |

</Accordion>

<div id="af_registration_method" />

<Accordion title="af_registration_method">

**Descrição**: tipo de método de inscrição

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_registration\_method |
| --- | --- |
| Anúncios Meta | fb\_registration\_method |
| Google Ads | registration\_method |
| Snap | sign\_up\_method |
| AppsFlyer | registration\_method |
| Tiktok | - |
| Criteo | - |

</Accordion>

<div id="af_returning_arrival_date" />

<Accordion title="af_returning_arrival_date">

**Descrição**: data e hora em que a viagem de volta termina

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_returning\_arrival\_date |
| --- | --- |
| Anúncios Meta | fb\_returning\_arrival\_date |
| Google Ads | - |
| Snap | - |
| AppsFlyer | - |
| Tiktok | - |
| Criteo | - |

</Accordion>

<div id="af_returning_departure_date" />

<Accordion title="af_returning_departure_date">

**Descrição**: data e hora em que a viagem de volta começa

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_returning\_departure\_date |
| --- | --- |
| Anúncios Meta | fb\_returning\_departure\_date |
| Google Ads | - |
| Snap | - |
| AppsFlyer | - |
| Tiktok | returning\_date |
| Criteo | - |

</Accordion>

<div id="af_revenue" />

<Accordion title="af_revenue">

**Descrição**: total das compras. af\_receita é considerada como receita na plataforma da AppsFlyer. Também conta a <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#revenue-events">receita negativa</Anchor>, de cancelamentos ou reembolsos.

> 🚧 **Importante!**
>
> O valor da receita não deve conter separadores de vírgula, moeda, caracteres especiais ou texto. Por exemplo, um valor de receita deve ser semelhante a 1234,56. A AppsFlyer oferece o valor de receita com uma precisão de até cinco casas decimais.

Para saber mais sobre como usar o parâmetro de receita, clique <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview#revenue-events">aqui</Anchor>.

**Receita líquida:** Para reportar a receita líquida junto com a receita bruta, envie [af\_net\_revenue](/docs/in-app-events-event-structure#h_01NEWAFNETREVENUE0001) como um parâmetro de evento personalizado. Você define o que líquido significa para a sua empresa (por exemplo, receita após taxas da loja e/ou impostos, margem bruta ou receita após taxas de serviço). Aplicativos com a receita da loja do ROI360 ativada têm esse valor preenchido automaticamente nos eventos de compra e assinatura que registram, como o valor bruto menos as taxas da loja de aplicativos e os impostos.

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_revenue |
| --- | --- |
| Anúncios Meta | \_valueToSum |
| Google Ads | Atenção |
| Snap | price |
| AppsFlyer | price\_micro |
| Tiktok | VALIDADO |
| Anúncios da Amazon | Valor do evento |
| Criteo | ui\_revenue |

</Accordion>

<div id="af_score" />

<Accordion title="af_score">

**Descrição**: pontuação associada à conquista do usuário

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_score |
| --- | --- |
| Anúncios Meta | - |
| Google Ads | - |
| Snap | - |
| AppsFlyer | score |
| Tiktok | - |
| Criteo | - |

</Accordion>

<div id="af_search_string" />

<Accordion title="af_search_string">

**Descrição**: termo de pesquisa

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_search\_string |
| --- | --- |
| Anúncios Meta | fb\_search\_string |
| Google Ads | search\_string |
| Snap | search\_string |
| AppsFlyer | search\_string |
| Tiktok | - |
| Criteo | - |

</Accordion>

<div id="af_subscription_id" />

<Accordion title="af_subscription_id">

**Descrição**: ID de assinatura do usuário

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_subscription\_id |
| --- | --- |
| Anúncios Meta | subscription\_id |
| Google Ads | - |
| Snap | - |
| AppsFlyer | - |
| Tiktok | - |
| Criteo | - |

</Accordion>

<div id="af_success" />

<Accordion title="af_success">

**Descrição**: indica se a conclusão da ação foi bem-sucedida

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_success |
| --- | --- |
| Anúncios Meta | fb\_success |
| Google Ads | success |
| Snap | success |
| AppsFlyer | - |
| Tiktok | - |
| Criteo | - |

</Accordion>

<div id="af_suggested_destinations" />

<Accordion title="af_suggested_destinations">

**Descrição**: lista de destinos sugeridos

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_purchase\_currency |
| --- | --- |
| Anúncios Meta | fb\_suggested\_destinations |
| Google Ads | - |
| Snap | - |
| AppsFlyer | - |
| Tiktok | - |
| Criteo | - |

</Accordion>

<div id="af_suggested_hotels" />

<Accordion title="af_suggested_hotels">

**Descrição**: lista de hotéis sugeridos

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_suggested\_hotels |
| --- | --- |
| Anúncios Meta | fb\_suggested\_hotels |
| Google Ads | - |
| Snap | - |
| AppsFlyer | - |
| Tiktok | - |
| Criteo | - |

</Accordion>

<div id="af_travel_end" />

<Accordion title="af_travel_end">

**Descrição**: data final da viagem

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_travel\_end |
| --- | --- |
| Anúncios Meta | fb\_travel\_end |
| Google Ads | - |
| Snap | - |
| AppsFlyer | - |
| Tiktok | - |
| Criteo | - |

</Accordion>

<div id="af_travel_start" />

<Accordion title="af_travel_start">

**Descrição**: data de início da viagem

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_travel\_start |
| --- | --- |
| Anúncios Meta | fb\_travel\_start |
| Google Ads | - |
| Snap | - |
| AppsFlyer | - |
| Tiktok | - |
| Criteo | - |

</Accordion>

<div id="af_user_score" />

<Accordion title="af_user_score">

**Descrição**: significado relativo do usuário para o anunciante

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_user\_score |
| --- | --- |
| Anúncios Meta | fb\_user\_score |
| Google Ads | - |
| Snap | - |
| AppsFlyer | - |
| Tiktok | - |
| Criteo | - |

</Accordion>

<div id="af_validated" />

<Accordion title="af_validated">

**Descrição**: valida uma compra

**Mapeamento de parâmetros:**

| A AppsFlyer | af\_validated |
| --- | --- |
| Anúncios Meta | - |
| Google Ads | VALIDADO |
| Snap | success |
| AppsFlyer | - |
| Tiktok | - |
| Criteo | - |

</Accordion>

Veja a seguir uma lista de parâmetros de eventos predefinidos que não incluem mapeamento por SRN:

* af\_achievement\_id
* af\_coupon\_code
* af\_customer\_segment
* af\_deep\_link
* af\_event\_end
* af\_event\_start
* af\_lat
* af\_long
* af\_new\_version
* af\_old\_version
* af\_param\_1
* af\_param\_2
* af\_param\_3
* af\_param\_4
* af\_param\_5
* af\_param\_6
* af\_param\_7
* af\_param\_8
* af\_param\_9
* af\_param\_10
* af\_review\_text
* af\_tutorial\_id
* af\_virtual\_currency\_name
* af\_duration\_seconds

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration">Configuração de postback de eventos in-app</Anchor>

<div data-zendesk-anchors="overview=resumo h_01H9HT8C713A4NV9WCB0FJZJ4R=resumo predefined-event-names=nomes-de-eventos-predefinidos h_01H9HT8C7189W1JXAR3J3KT8KV=nomes-de-eventos-predefinidos h_01H9HT8C71MV7V7C75MB6ESHMM=achievement-unlocked-af_achievement_unlocked h_01H9HT8C7171PB7KAC83MYBWQ8=ad-click-af_ad_click h_01H9HT8C72KJ6ZA663SH7HJ7MP=ad-view-af_ad_view h_01H9HT8C72HSM88DJG0PDV5140=add-payment-info-af_add_payment_info h_01H9HT8C72BWFSPKWDVQW926WG=add-to-cart-af_add_to_cart h_01H9HT8C7228B57XKAACPZG8NK=add-to-wishlist-af_add_to_wishlist h_01K0PJ4C3HP9DMJT1DFZ848WF0=app-open-af_app_opened h_01H9HT8C72DX0DXBDHRJFG19G2=complete-registration-af_complete_registration h_01H9HT8C72SPY9VQ9AD648AKZK=content-view-af_content_view h_01H9HT8C722T2VH6A9257Q7T4P=initiated-checkout-af_initiated_checkout h_01H9HT8C72F0RZ4JS9929SE465=invite-af_invite h_01K0PJ4C3H72BDTRH7WAYW4V7S=lead-lead h_01H9HT8C72VFGC08Q858EX7XTN=level-achieved-af_level_achieved h_01H9HT8C72DZW77YTQ9KB0XEVG=list-view-af_list_view h_01H9HT8C720W10QEBCTPAGMRFB=login-af_login h_01H9HT8C72QC4WV10Z4JZTZM7D=opened-from-push-notification-af_opened_from_push_notification h_01H9HT8C7263J0YSX5K10R497N=purchase-af_purchase h_01H9HT8C73MPYMG8KSYE04DKDZ=rate-af_rate h_01H9HT8C734DAC6GPJE58DB5JD=reengage-af_re_engage h_01H9HT8C73YSYBK0YSDPRWDBNW=search-af_search h_01H9HT8C734GJ07V67QC9V3TVC=share-af_share h_01H9HT8C73H4VT2M0P3M1SYG88=spent-credits-af_spent_credits h_01H9HT8C73YWDCKAZPY0BVRS6F=start-trial-af_start_trial h_01H9HT8C736BF2VNRCFSJSVXWS=nota h_01H9HT8C73N69S45H82NWQ5FN1=subscription-af_subscribe h_01H9HT8C73CD6HNT5GA6B4CHQ9=travel-booking-af_travel_booking h_01H9HT8C73NFDPS1P5AVXXZEX7=tutorial-completion-af_tutorial_completion h_01H9HT8C73JPH6Q9XFKA3GNYT8=update-af_update h_01H9HT8C74SGGK2FW92JH4BJPZ=nota-1 predefined-event-parameters=par%C3%A2metros-de-eventos-predefinidos h_01H9HT8C74N4TJZ5ZVBTKAX810=par%C3%A2metros-de-eventos-predefinidos h_01H9HT8C74VQ9ZWF079V50E5HE=nota-2 h_01H9HT8C74Y0BWS565DFTY75KJ=af_adrev_ad_type h_01H9HT8C742NHGXFKWSS4P07K2=af_city h_01H9HT8C7442PFZEK7QC6R0K67=af_class h_01H9HT8C7462KG3030WWZ2XGZW=af_content h_01H9HT8C74ZX07907NXFHKGJ91=af_content_id h_01H9HT8C744CMWSYHJB74JFSS5=af_content_list h_01H9HT8C74GKGG5V4X54BCAADC=af_content_type h_01H9HT8C74RD08Z9EBZTKY5KSD=af_country h_01H9HT8C75BJYK4R3WYSN4BF43=af_currency h_01H9HT8C752E2PK6QKTA2GNGH5=af_customer_user_id h_01H9HT8C75BN0A92X9BRY4A74T=af_date_a h_01H9HT8C75406KV9264ZZT9DKM=af_date_b h_01H9HT8C7526AEHJAA7FM7442E=af_departing_arrival_date h_01H9HT8C75W9X61ZH0849EPDBY=af_departing_departure_date h_01H9HT8C75VEV3C8CJBDN6X5HW=af_description h_01H9HT8C75Z8TBZEPEY9EGSR4Y=af_destination_a h_01H9HT8C751G216VB6GYTPEPE1=af_destination_b h_01H9HT8C75CVM0MHSKTK2CZ8HD=af_destination_list h_01H9HT8C75CVVDFABSTN5R4MWT=af_hotel_score h_01H9HT8C75GEMHE2NHEFK9J7NT=af_level h_01H9HT8C7505H4CMY70EMDQWSF=af_max_rating_value af_net_revenue=h_01NEWAFNETREVENUE0001 h_01NEWAFNETREVENUENOTE0001=aten%C3%A7%C3%A3o h_01H9HT8C75ST9XBDC3SR6XFDPB=af_num_adults h_01H9HT8C75NNZ5NP6PRPXDSKP8=af_num_children h_01H9HT8C757X70AAGNWFV0CKRY=af_num_infants h_01H9HT8C75A0HESE5FD10VD1P8=af_order_id h_01H9HT8C75B488VKY8SW9M4GG4=af_payment_info_available h_01H9HT8C75W7SRB0KF4E5FB2YF=af_preferred_neighborhoods h_01H9HT8C75GC61D1A0P6P42TMR=af_preferred_num_stops h_01H9HT8C76XRY6CD1TJEPCJJTR=af_preferred_price_range h_01H9HT8C76Y9ZQQ2X4EJT2DC14=af_preferred_star_ratings h_01H9HT8C76KCDRJKBWSM9JKFE1=af_price 01J9XHWVFHXPN6N3EZF1P8XWYM=af_projected_revenue h_01H9HT8C76Y5VXBKF3TBVVJG1C=af_quantity h_01H9HT8C768WXZ126Q425PHDWX=af_rating_value h_01H9HT8C76XX9J6FZ6RWQB6B6R=af_receipt_id h_01H9HT8C760S0F7QZMFYW1BKRD=af_region h_01H9HT8C76N4S3SGES5SQ2J4AC=af_registration_method h_01H9HT8C76ZR36A4CM2PY6PJ10=af_returning_arrival_date h_01H9HT8C760JPVXYC5WH9ZSDPX=af_returning_departure_date h_01H9HT8C76PYB14WPCQKSEK69J=af_revenue h_01H9HT8C762BGPRHFX228APEHR=importante h_01H9HT8C76P55HN8K6D7PHFS2J=af_score h_01H9HT8C76TB4KNTZVD6JVPEYQ=af_search_string h_01H9HT8C762R2PJ573W8TJFJHG=af_subscription_id h_01H9HT8C76VZ6FA20K471V0EKK=af_success h_01H9HT8C76029H94AY5EHCZX6X=af_suggested_destinations h_01H9HT8C76N6C694TCPVCK4EC3=af_suggested_hotels h_01H9HT8C765EM1SAEJ67FNXZDE=af_travel_end h_01H9HT8C76YP8VEM5E6WB9NQ7T=af_travel_start h_01H9HT8C771SYQWQ8VBTPA2V2E=af_user_score h_01H9HT8C771XFSQJX42QVBNZAJ=af_validated h_01HDNZ30NH2QXSHD7B4EMFG4T5=veja-tamb%C3%A9m" />
