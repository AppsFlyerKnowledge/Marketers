---
title: Événements recommandé pour les apps de eWallet
metadata:
  keywords:
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
  created_at: '2021-06-10T11:36:07Z'
  edited_at: '2024-10-17T09:17:01Z'
  id: 4402425586065
  locale: fr
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/fr/articles/4402425586065
---
> **En bref :** Mesurez la qualité de vos utilisateurs durant leur parcours en enregistrant les événements in-app que nous vous recommandons pour votre app de eWallet.

## <Image alt="InApp_Events_eWallet.png" src="https://files.readme.io/4d2ed4994bbe8e8eca7009b8ec8f5dbf22a626421a7a1efb213ddb4a12c7b487-4402543191825.png" width="67px" /> eWallet

Les apps de eWallet permettent aux utilisateurs d’effectuer des paiements ou des achats numériques depuis leurs appareils. Parmi les événements que nous vous suggérons d’enregistrer se trouvent : l’ajout de fonds, l’affichage du contenu, la sélection des marchands, l’affichage des promotions et la réalisation de transactions.

En enregistrant ces événements vous pouvez savoir :

* Quel type de contenu et de promotions intéressent les utilisateurs, et ainsi leur proposer des produits similaires
* Pour quels types de services les utilisateurs utilisent souvent le eWallet pour régler les factures
* Quels sont les marchands les plus populaires

> 🚧 **Attention !**
>
> * Veuillez lire les <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview#configuration-des-événements-in-app">instructions</Anchor> à l'attention des marketeurs avant d’implémenter les événements in-app.
> * Pour simplifier les opérations, vous pouvez utiliser notre <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=ewallet">Générateur d’événements in-app</Anchor>. Cet outil contient tous les événements in-app recommandés abordés dans cet article et vous permet de modifier les événements en fonction de vos besoins. Une fois terminé, transmettez le fichier à votre développeur.
> * Pour chacun des événements recommandés de cet article, vous trouverez les extraits de code pour les développeurs iOS, Android et Unity.
> * Si votre développeur a besoin d'instructions plus détaillées, elles se trouvent dans le **<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">hub des développeurs AppsFlyer</Anchor>.**
>
> Pour en savoir plus sur l’enregistrement des événements in-app, rendez-vous dans la section <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview">Guide des événements in-app</Anchor>.

[![Flowchart_for_recommended_events e-Wallet_app_user_journey](https://files.readme.io/cf1f91f9c89d1f45448a6172e48b7f59fdce767f00c893d91b12a5f2d043945f-4404610923409.png)](https://files.readme.io/cf1f91f9c89d1f45448a6172e48b7f59fdce767f00c893d91b12a5f2d043945f-4404610923409.png)

## Structures recommandées pour les événements prédéfinis

Cette section propose la liste des structures d'événement qui sont le plus souvent utilisées dans le secteur eWallet. Chaque structure vous propose un nom d'événement prédéfini, accompagné des suggestions de paramètres d'événement. Notez que les événements in-app peuvent inclure à la base tous les paramètres d'événement que vous recherchez.

<div id="complete-registration-af_complete_registration" />

<Accordion title="Inscription terminée (af_complete_registration)">

**Objectif**

Permet de savoir combien d'utilisateurs ont installé l'app en allant au bout de l'inscription, et quelles méthodes d'inscription vos utilisateurs privilégient.

**Déclencheur**

Lorsque l'utilisateur termine le processus d'inscription

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| af\_registration\_method | Le type de méthode d'inscription | E-mail, Facebook, Google |

</Accordion>

<div id="login-af_login" />

<Accordion title="Connexion (af_login)">

**Objectif**

Comprendre la rétention de vos utilisateurs inscrits

**Déclencheur**

Lorsque l'utilisateur se connecte

**Paramètres d'événement**

Peut être envoyé sans paramètres supplémentaires

</Accordion>

<div id="content-view-af_content_view" />

<Accordion title="Affichage du contenu (af_content_view)">

**Objectif**

Connaître le nombre d’affichage d’un certain contenu. Cet évènement peut vous permettre de :

* Savoir quel type de contenu vos utilisateurs consultent le plus et optimiser vos campagnes marketing en conséquence.
* Associer la consultation des éléments aux marchands

**Déclencheur**

Lorsque l’utilisateur consulte un élément ou un contenu de catégorie précis

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| item | Type d’élément | Ticket de cinéma |
| merchant\_name | Nom du marchand | Cineplex |

</Accordion>

## Structures recommandées pour les événements personnalisés

La section suivante offre une liste des structures d'événements qui incluent les noms d'événements personnalisés et les suggestions de paramètres d'événement. Notez que les événements in-app peuvent inclure à la base tous les paramètres d'événement que vous recherchez.

<div id="wallet-complete-topup-wallet_complete_topup" />

<Accordion title="Recharge complète du wallet (wallet_complete_topup)">

**Objectif**

Les fonds de recharge peuvent être utilisés pour acheter n'importe quel forfait ou service proposé dans l'app. Enregistrez cet évènement et comparez-le aux différentes données pour en savoir plus sur vos utilisateurs. Exemple : vous pouvez découvrir quels montants les utilisateurs sont prêts à déposer sur leurs comptes, puis utiliser les montants de recharge pour les cibler avec des campagnes personnalisées qui suivent leur budget.

**Déclencheur**

Lorsque l’utilisateur effectue la recharge depuis une carte bancaire vers l’application eWallet

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| top\_up\_amount | Montant du paiement | 100 |
| top\_up\_method | Le type de méthode de paiement | virement bancaire |

</Accordion>

<div id="payment-transaction-completed-payment_transaction_completed" />

<Accordion title="Transaction de paiement terminée ( payment_transaction_completed )">

**Objectif**

Cet évènement peut vous permettre de :

* Repérer les utilisateurs qui ont effectué le paiement pour une transaction.
* Repérer les transactions importantes, puis recibler les utilisateurs qui rechargent une grosse somme.

**Déclencheur**

Lorsque la transaction d’un achat est complétée

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| item | Elément payé pour | Recharge de carte prépayée |
| quantity | Montant versé | 1 |
| transaction\_amount | Montant de la transaction | 50 |

</Accordion>

<div id="bill-payment-success-bill_payment_success" />

<Accordion title="Paiement de facture validé (bill_payment_success)">

**Objectif**

Cet événement peut vous aider à savoir pour quel type de service les utilisateurs passent par le eWallet pour régler leurs factures (factures d’eau, factures d’électricité, soldes de carte de crédit, etc).

**Déclencheur**

Lorsque l’utilisateur règle un montant avec son eWallet, par exemple pour une facture, un relevé de carte de crédit ou des tickets de cinéma

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| merchant\_name | Nom du marchand | Fournisseur d’électricité |
| payment\_amount | Montant payé | 100 |
| category | Type de service | Électricité |

</Accordion>

<div id="promo-promo" />

<Accordion title="Promotion (promo)">

**Objectif**

Cet événement peut vous aider à comprendre :

* Si la promo en question est populaire auprès des utilisateurs
* Si la promo encourage la vente croisée d’autres produits aux utilisateurs

**Déclencheur**

Lorsque l’utilisateur sélectionne la promotion proposée dans l’app

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| promo\_type | Type de promotion offerte | <ul><li>30%</li></ul> |

</Accordion>

<div id="voucher-redeem-voucher_redeem" />

<Accordion title="Utilisation de bons d’achat (voucher_redeem)">

**Objectif**

Cet événement peut vous aider à comprendre :

* Combien d’utilisateurs profitent des codes de réduction
* Quel type de bons et de réductions les utilisateurs préfèrent

**Déclencheur**

Lorsqu’un code promo est utilisé

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| voucher\_ID | ID du code promo | 1735103 |
| merchant\_name | Nom du marchand | Cineplex |

</Accordion>

<div id="select-merchant-select_merchant" />

<Accordion title="Sélectionner le marchand ( select_merchant )">

**Objectif**

Cet événement peut vous aider à savoir quel marchand est le plus utilisé pour essayer d’inciter les marchands similaires à rejoindre le service de eWallet.

**Déclencheur**

Lorsque l’utilisateur sélectionne un marchand dans la liste des marchands disponibles

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| merchant\_name | Nom du marchand | Cineplex |
| type | Type d’entreprise | Cinema |
| amount | Devise utilisée par l’annonceur | USD |
| merchant\_ID | ID associé à une entreprise qui indique aux systèmes de traitement des paiements quels fonds doivent être envoyés et où suite à une transaction. | 123456 |

</Accordion>

<div id="scan-barcode-success-scan_barcode_success" />

<Accordion title="Succès de lecture du code-barres ( scan_barcode_success )">

**Objectif**

Cet évènement peut vous permettre de :

* Savoir quand un utilisateur effectue une transaction chez un marchand
* Comprendre quels marchands sont les plus utilisés

**Déclencheur**

Lorsque l’utilisateur scanne le QR code de chaque marchand visité à l’aide de l’application eWallet

**Paramètres d'événement**

| Nom | Description | Exemple de valeur |
| --- | --- | --- |
| merchant\_name | Nom du marchand | Cineplex |
| merchant\_ID | ID associé à une entreprise qui indique aux systèmes de traitement des paiements quels fonds doivent être envoyés et où suite à une transaction. | 123456 |

</Accordion>

<div data-zendesk-anchors="ewallet=-ewallet h_01HGTAEVWFZXCA7AV0P35W992F=-ewallet h_01HGTAEVWFR4QS6XAT1T28N1R5=attention- recommended-structures-for-predefined-events=structures-recommand%C3%A9es-pour-les-%C3%A9v%C3%A9nements-pr%C3%A9d%C3%A9finis h_01HGTAEVWF8SVYTQMQ12219HX0=structures-recommand%C3%A9es-pour-les-%C3%A9v%C3%A9nements-pr%C3%A9d%C3%A9finis h_01HGTAEVWFBA3CD7ZA40VCER95=complete-registration-af_complete_registration h_01HGTAEVWGDBN8B3P2YHQJ5RYF=login-af_login h_01HGTAEVWGYFYEZBD3ZED7GGFG=content-view-af_content_view recommended-structures-for-custom-events=structures-recommand%C3%A9es-pour-les-%C3%A9v%C3%A9nements-personnalis%C3%A9s h_01HGTAEVWG39P9A84P926BG3VE=structures-recommand%C3%A9es-pour-les-%C3%A9v%C3%A9nements-personnalis%C3%A9s h_01HGTAEVWGNYC5Z0ACHV8CFVNQ=wallet-complete-topup-wallet_complete_topup h_01HGTAEVWG36K4V4Z0NN8QYDNV=payment-transaction-completed-payment_transaction_completed h_01HGTAEVWG136M86GM1JPV74RH=bill-payment-success-bill_payment_success h_01HGTAEVWG34EXM28GW2ZN0NRC=promo-promo h_01HGTAEVWG0EHESWPQHCX4P3SH=voucher-redeem-voucher_redeem h_01HGTAEVWGKGC7N8ZB0MMQJ4YE=select-merchant-select_merchant h_01HGTAEVWG20101JC5VVK29Y0E=scan-barcode-success-scan_barcode_success" />
