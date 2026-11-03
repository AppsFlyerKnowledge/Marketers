---
title: Mesurer les campagnes de réengagement de notifications push
metadata:
  keywords:
    - Re-Engagement
    - push
    - notifications
    - Advertisers
    - Developers
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2016-01-18T10:03:11Z'
  edited_at: '2023-02-15T14:40:37Z'
  id: 207364076
  locale: fr
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/fr/articles/207364076
---
> **En bref :** mesurez les campagnes de notification push sur iOS et sur Android.

## Présentation

AppsFlyer prend en charge la mesure des campagnes de notification push pour l'ensemble des fournisseurs de push, ainsi que la mesure des campagnes implémentées directement sur Firebase Cloud Messaging ou Apple Push Notification Services (APNS).

L'intégration peut être implémentée de deux manières :

* En utilisant les templates OneLink (recommandé).
* En envoyant un objet JSON avec une clé `af` dans la charge utile de la notification push (ancienne méthode).

Les conversions s'affichent dans la vue d'ensemble du tableau de bord, dans les vues retargeting et unifiée.

## Comment fonctionne l'API de test ?

Une fois les étapes décrites dans cet article terminées, votre application fonctionnera comme suit :

1. Vous déclenchez une notification push qui contient un template OneLink **ou** une clé `af` au sein de sa charge utile.
2. L'utilisateur de l'app reçoit la notification push, il clique dessus.
3. L'app se charge et le SDK AppsFlyer se lance.
4. Le SDK traite la charge utile de la notification push qui a permis d'ouvrir l’application.
5. Le SDK extrait puis transfère les données d'attribution à AppsFlyer.

Dans le cas d'utilisation du OneLink, si le OneLink est configuré pour diriger l'utilisateur vers un lieu précis dans l'app, le flux de deep link est déclenché.

## Conditions préalables

Avant de continuer, vérifiez que <Anchor target="_blank" href="/marketers/fr/docs/basic-sdk-integration-guide">le SDK AppsFlyer est bien intégré à l'app</Anchor> **et** que cette dernière peut recevoir les notifications push.

## Étapes

Pour configurer la mesure des notifications push, vous devez suivre les étapes suivantes :

1. [Créez une notification push](/docs/measuring-push-notification-re-engagement-campaigns#1-creating-the-push-notification) qui contient une clé de données personnalisée avec le template OneLink **ou** une clé `af` dont la valeur est un objet JSON.
2. [Configurez le SDK pour qu'il finalise la clé personnalisée](/docs/measuring-push-notification-re-engagement-campaigns#2-configuring-the-sdk) (action effectuée par un développeur).
3. [Testez l'intégration](/docs/measuring-push-notification-re-engagement-campaigns#3-testing-the-integration) en déclenchant une notification push.
4. [Consultez les performances des campagnes de notification push](/docs/measuring-push-notification-re-engagement-campaigns#4-viewing-push-notification-campaigns-in-the-dashboard) dans le tableau de bord.

<div id="1-creating-the-push-notification" />

<Accordion title="1. Créer une notification push">

Commencez par créer une notification push contenant des données d'attribution en suivant l'une des méthodes ci-dessous.

> 📘 **Note**
>
> Dans l'exemple suivant, nous utilisons Firebase comme fournisseur push. Les instructions doivent s’adresser à l'ensemble des fournisseurs push, avec très peu d'exceptions (si possible aucune). Consultez les documents relatifs à chaque fournisseur push pour en savoir plus.

<Tabs>
<Tab title="Avec OneLink (recommandé)">

#### **Avec OneLink (recommandé)**

Il s’agit de la méthode recommandée pour intégrer AppsFlyer aux notifications push.

1. Créez un <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">lien OneLink et configurez-le pour le retargeting.</Anchor>  
   **Remarque** : les URL OneLink courtes et longues sont toutes deux prises en charge.
2. Dans les données personnalisées de notification push, ajoutez le OneLink qui contient les données d'attribution que vous souhaitez transmettre à AppsFlyer.

> 📄 **Exemple avec Firebase**
>
> Dans Firebase :
>
> [![appsflyer-push-custom-data-firebase.png](https://files.readme.io/b2a753e8ec88ef0d0e0a71fe222a8ecc4f03786297696d150f185720b8f4e248-49839256715025.png)](https://files.readme.io/b2a753e8ec88ef0d0e0a71fe222a8ecc4f03786297696d150f185720b8f4e248-49839256715025.png)

</Tab>

<Tab title="Avec JSON (ancienne méthode)">

<div id="using-json-legacy" />

#### **Avec JSON (ancienne méthode)**

> 📘 **Note**
>
> Les instructions suivantes concernent l'ancienne méthode d’intégration des notifications push AppsFlyer, elles s'adressent aux personnes qui se confrontent à des problèmes de compatibilité. Si vous configurez une nouvelle application, mieux vaut utiliser la [solution OneLink recommandée](/docs/measuring-push-notification-re-engagement-campaigns#avec-onelink-recommandé).

Dans les données personnalisées de la notification push, ajoutez une clé personnalisée que vous nommez `af` et qui contient les données d'attribution au format JSON que vous souhaitez transmettre à AppsFlyer. Veuillez suivre les paramètres d’attribution suivants :

* `PID`
* `is_retargeting`
* `C`

> 📄 **Exemple avec Firebase**
>
> Dans Firebase :
>
> [![appsflyer-push-custom-data-firebase-json.png](https://files.readme.io/138aa2abb70cdb0b8a2c1a4b4ce0a8b83b2faae58e29f3223d5653a4d575012b-49839256716049.png)](https://files.readme.io/138aa2abb70cdb0b8a2c1a4b4ce0a8b83b2faae58e29f3223d5653a4d575012b-49839256716049.png)

</Tab>
</Tabs>

</Accordion>

<div id="2-configuring-the-sdk" />

<Accordion title="2. Configurer le SDK">

Cette étape nécessite de modifier le code de l'app. Veuillez suivre les instructions pour configurer le SDK :

* Pour implémenter la solution OneLink recommandée :
  1. Transmettez au développeur de l'app le nom de la clé personnalisée que vous avez ajoutée à la notification. Dans cet exemple, le nom est `af_push_link`.
  2. Demandez au développeur de suivre <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/push-notifications#integrating-appsflyer-with-push-notifications-using-onelink-recommended">ces instructions</Anchor>.
* Pour implémenter l'ancienne solution (via JSON), demandez à vos développeurs de suivre <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/push-notifications#integrating-appsflyer-with-push-notifications-legacy">ces instructions</Anchor>.

</Accordion>

<div id="3-testing-the-integration" />

<Accordion title="3. Tester l'intégration">

Pour vérifier si la mesure des notifications push est correctement intégrée, il suffit de déclencher une notification push dans la campagne que vous avez configurée lors de l'étape 1.

Si tout a bien été configuré, le SDK réalise les actions suivantes :

1. Il écoute les notifications push.
2. Il traite les données d'attribution intégrées à la notification push avant de les transmettre à AppsFlyer.
3. Il continue à suivre le processus de deep linking, dans le cas où la mesure de notification push a été implémentée avec OneLink.

</Accordion>

<div id="4-viewing-push-notification-campaigns-in-the-dashboard" />

<Accordion title="4. Consulter les campagnes de notification push dans le tableau de bord">

Vous pouvez voir s'afficher les données issues des notifications push dans le <Anchor target="_blank" href="/marketers/fr/docs/retargeting-attribution-guide#retargeting-dashboard">tableau de bord de retargeting</Anchor>.

**Remarque** : AppsFlyer supprime les doublons des données de notification push. Si les mêmes charges utiles sont reçues plus d'une fois, une seule sera donc comptabilisée.

</Accordion>

<div data-zendesk-anchors="overview=pr%C3%A9sentation how-does-it-work=comment-fonctionne-lapi-de-test prerequisites=conditions-pr%C3%A9alables steps=%C3%A9tapes using-onelink-recommended=avec-onelink-recommand%C3%A9" />
