---
title: 'Découverte de OneLink : Guide du débutant'
metadata:
  keywords:
    - Marketers
    - set up
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2024-08-21T11:48:39Z'
  edited_at: '2024-11-27T20:50:49Z'
  id: 27699299657617
  locale: fr
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/fr/articles/27699299657617
---
> **En bref** : Utilisez OneLink pour réaliser une redirection utilisateur puissante et personnalisée, des liens profonds et une attribution à partir de vos campagnes, quel que soit l'appareil, le système d'exploitation, le canal ou la plateforme de l'utilisateur, afin d'optimiser la conversion et les revenus.

## ![53010_Onelink.jpg](https://files.readme.io/c0d24ab87126bf765a89a25077b07d8678159cdb6f1b68eddc14a4cd2759b12a-30192941047185.jpg)

## À propos de OneLink

AppsFlyer <Anchor target="_blank" href="/marketers/fr/docs/onelink-guide">OneLink</Anchor> vous permet de créer des liens pour vos campagnes avec des fonctionnalités d'attribution, de redirection et de liens profonds qui convertissent les utilisateurs des médias détenus en utilisateurs d'applications et engagent les utilisateurs existants avec des parcours contextuels fluides, indépendamment de l'appareil, du système d'exploitation, du canal ou de la plateforme. Utilisez OneLink pour créer des parcours utilisateur contextuels et personnalisés qui orientent vos utilisateurs vers votre application afin d'atteindre les taux de conversion et les revenus les plus élevés possibles. Les expériences personnalisées que vous pouvez créer comprennent :

* **Réseaux sociaux vers application** : Engagez vos utilisateurs sur les réseaux sociaux et dirigez-les des flux de réseaux sociaux vers votre application.
* **Application à application** : Dirigez les utilisateurs vers votre application à partir d'autres applications.
* <Anchor target="_blank" href="/marketers/fr/docs/convert-your-mobile-web-visitors-to-app-users">**Web vers application**</Anchor> : Convertissez les visiteurs de votre site web mobile en nouveaux utilisateurs d'application mobile en utilisant des Bannières Intelligentes et des Scripts Intelligents.
* **QR vers application** : Utilisez des codes QR pour faciliter l'installation d'applications en demandant aux utilisateurs de scanner un code QR à des moments clés de leur expérience client hors ligne. Vous pouvez également intégrer des codes QR sur votre site de bureau ou sur des publicités TV et CTV pour diriger les utilisateurs vers votre application.
* **E-mail vers application** : Utilisez des fournisseurs de services email (ESP) pour interagir avec les utilisateurs par email et les conduire de leur boîte de réception vers votre application.
* **Texte vers application** : Créez des liens pour vos campagnes SMS et de messagerie et engagez les utilisateurs via des messages texte.
* **Référent vers application** : Créez des liens d'invitation utilisateur permettant aux utilisateurs et aux influenceurs d'inviter d'autres personnes à rejoindre votre application ou de partager du contenu spécifique dans l'application, par exemple un article.
* **Personnalisé** : Créez une expérience hautement personnalisée avec une myriade d'options pour une personnalisation maximale. Peu importe d'où viennent vos utilisateurs, qu'ils soient sur un ordinateur de bureau ou un appareil mobile, en ligne ou hors ligne, à partir de médias détenus ou payés, utilisez OneLink pour les diriger facilement vers l'endroit approprié.

## Intégration de OneLink

**Pour commencer à utiliser OneLink, suivez les étapes ci-dessous :**

<span id="h_01J5WC8Z4J352AHSDTRCEP2W9H"></span>**Conditions préalables**

* Un compte <Anchor target="_blank" href="https://www.appsflyer.com/sign-up/">AppsFlyer</Anchor> avec au moins une de vos applications ajoutée.
* Pour configurer OneLink, vous devez être un utilisateur administrateur d'AppsFlyer ou avoir les <Anchor target="_blank" href="/marketers/fr/docs/user-management">autorisations</Anchor> nécessaires pour ajouter\/modifier des modèles OneLink.
* Le <Anchor target="_blank" href="/marketers/fr/docs/integrate-the-appsflyer-sdk">SDK AppsFlyer</Anchor> doit être installé dans vos applications mobiles pour l'attribution des installations, des événements in-app et des liens profonds.
  * Si le SDK n'est pas encore installé dans vos applications, vous pouvez tout de même créer un lien de redirection fonctionnel, mais sans attribution.

| Tâche | Objectif | Actions requises | Personnes impliquées |
| --- | --- | --- | --- |
| 1. Créer un modèle OneLink | Un modèle OneLink constitue la base nécessaire de la logique de redirection pour tous les liens créés à partir de celui-ci. | <ul><li>Responsable marketing\/chef de produit : Configurer un <Anchor target="_blank" href="/marketers/fr/docs/create-a-onelink-template">modèle OneLink</Anchor> dans AppsFlyer.</li><li>Développeur Android : Configurer les méthodes d'ouverture d'applications pour les utilisateurs existants (Android App Links et schémas URI).</li><li>Développeur iOS : Configurer les méthodes d'ouverture d'applications pour les utilisateurs existants (liens universels iOS et schéma URI).</li></ul><Anchor target="_blank" href="/marketers/fr/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users">Instructions pour les développeurs</Anchor> | Marketeur et développeur |
| 2. Créer un lien OneLink | Créez un lien OneLink à partir de votre modèle nouvellement créé à utiliser dans votre campagne. | <ul><li>Responsable marketing\/chef de produit : Configurer un lien <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#créer-un-lien-onelink">OneLink</Anchor> dans AppsFlyer, y compris le choix de l'expérience utilisateur et l'ajout des paramètres d'attribution et de liens profonds.</li><li>Développeurs Android et iOS : Configurer un <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">lien profond</Anchor> (si nécessaire).</li></ul> | Marketeur et développeur |
| 3. Configurer votre liste de redirection autorisée | Pour des raisons de sécurité, les liens que vous créez dans AppsFlyer ne redirigeront les utilisateurs que vers des URL Web dont les domaines figurent dans votre liste autorisée. | Mettre à jour la <Anchor target="_blank" href="/marketers/fr/docs/set-up-your-domain-redirect-allowlist">liste autorisée de redirection</Anchor> avec tous les domaines vers lesquels vous souhaitez rediriger les utilisateurs. | Responsable marketing |
| 4. Testez votre nouveau lien | Vérifiez que votre lien redirige correctement :<ul><li>Nouveaux utilisateurs sans l'application installée</li><li>Utilisateurs existants avec l'application installée</li></ul> | Vous pouvez <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#testing">tester</Anchor> votre nouveau lien. | Responsable marketing |
| 5. Utilisez le lien en toute confiance dans votre campagne, puis mesurez les résultats |  | <ol><li>Ajoutez le nouveau lien à votre campagne et diffusez-le auprès de votre audience.</li><li>Consultez les résultats de votre campagne dans le tableau de bord Aperçu d'AppsFlyer (filtrez par votre campagne).</li></ol>Félicitations ! Vous avez terminé votre intégration à OneLink. | Marketeur, analyste de données |
| **Fonctionnalités optionnelles** |  | Maintenant que vous êtes prêt, vous pouvez explorer et découvrir les fonctionnalités supplémentaires de OneLink telles que :<ul><li>Web vers application : Transformez les utilisateurs Web en utilisateurs d'applications et mesurez les parcours allant du Web à l'application.</li><li><Anchor target="_blank" href="/marketers/fr/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">API OneLink</Anchor> et <Anchor target="_blank" href="/marketers/fr/docs/perform-onelink-bulk-actions-via-csv">création massive de liens</Anchor> : Gérez et exécutez plusieurs campagnes à la fois, et créez rapidement et facilement des milliers de liens OneLink.<br />*L'API OneLink nécessite un abonnement Enterprise.</li><li><Anchor target="_blank" href="/marketers/fr/docs/export-onelink-urls">Exporter les URL OneLink</Anchor> : Téléchargez vos URL OneLink créées dans AppsFlyer.</li><li><Anchor target="_blank" href="/marketers/fr/docs/measuring-push-notification-re-engagement-campaigns">Mesurez les campagnes de réengagement via les notifications push</Anchor> : Utilisez les notifications push avec OneLink pour mesurer le réengagement des utilisateurs mobiles.</li><li><Anchor target="_blank" href="/marketers/fr/docs/cross-promotion-attribution-for-marketers">Attribution des promotions croisées</Anchor> : Vos utilisateurs actuels sont d'excellents candidats pour installer vos autres nouvelles applications. Apprenez à utiliser les méthodes SDK pour créer et évaluer des campagnes de promotion croisée.</li><li><Anchor target="_blank" href="/marketers/fr/docs/understand-onelink-short-vs-long-urls">URL longues</Anchor> : Ajoutez des paramètres à vos liens personnalisés OneLink ou générez un grand nombre de ces liens en appliquant vos propres formules simples dans une feuille de calcul.</li></ul> | Marketeur et développeur |

Si vous avez besoin d'aide pour commencer avec OneLink, contactez votre représentant commercial ou écrivez à [hello@appsflyer.com](mailto:hello@appsflyer.com)

<div data-zendesk-anchors="overview=%C3%A0-propos-de-onelink h_01J2G7RMHSPPXCWJ60W9HZASXX=%C3%A0-propos-de-onelink h_01HKHGX9JJQQCKF9SDZRSCM1XJ=%C3%A0-propos-de-onelink xyz-onboarding=int%C3%A9gration-de-onelink h_01J2RJFH0B4R815CWDQNEB2C1P=int%C3%A9gration-de-onelink" />
