---
title: Préparation à l'examen de l'App Store—étiquettes nutritionnelles
metadata:
  keywords:
    - iOS
    - iTunes
    - Apple
    - IDFA
    - Guidelines
    - IFA
    - Ad Tracking
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
  created_at: '2014-04-12T13:28:26Z'
  edited_at: '2023-11-06T08:37:18Z'
  id: 207032086
  locale: fr
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/fr/articles/207032086
---
> **En bref** : depuis iOS 14,  les développeurs doivent fournir à l'App Store des éléments concernant leur pratique en matière de protection de la vie privée lorsqu'ils soumettent une app. L'App Store publie ces pratiques sous la forme d'une *étiquette de confidentialité.*

**Un message de nos avocats :** *rien de ce qui est énoncé ici n'a valeur de conseil juridique. Les éléments ne sont fournis qu'à titre d'information. Vous devez travailler en étroite collaboration avec des conseillers juridiques ou assimilés pour déterminer avec précision comment les politiques d'Apple doivent s'appliquer à votre cas.*

## Étiquettes nutritionnelles et examen de l'app store

* Pour que les étiquettes de confidentialité soient générées, les développeurs d'app doivent répondre à un questionnaire au moment où ils soumettent leur application à App Store Connect. Il comprend les sections suivantes :
  * Types de données collectées
  * [Les données sont collectées avec quel objectif d'utilisation ?](/docs/preparing-for-the-app-store-review-nutrition-labels#les-objectifs-dutilisation-des-données)
  * [Le type de données est-il lié à une identité ?](/docs/preparing-for-the-app-store-review-nutrition-labels#données-liées-à-une-identité)
  * Les données sont-elles utilisées pour le suivi (y compris en lien avec tout service tiers ou SDK inclus dans une app) ?
* Développeurs d'apps :
  * Gardez la main sur l'ensemble de l'implémentation et de la configuration du logiciel AppsFlyer, ainsi que sur le choix des données à collecter et la façon dont elles sont utilisées.
  * Les réponses au questionnaire peuvent varier considérablement en fonction de la manière dont vous avez configuré le logiciel AppsFlyer, et des points de données que vous avez décidé de collecter.
* Selon les clauses des directives d'Apple, AppsFlyer n'effectue pas de *suivi.* Ceci étant dit, les développeurs d'app doivent répondre au questionnaire en fonction de leurs propres méthodes et intégrations de partenaire.
* Si vous utilisez les données collectées à des fins de suivi, vous devez implémenter la boîte de dialogue de consentement ATT.
* Ce qui suit suppose les configurations par défaut du logiciel AppsFlyer. Les développeurs sont tenus de s'assurer que leurs configurations et utilisations spécifiques sont conformes.

#### Types de données collectées

| **Type de données** | **Collecte des données AppsFlyer** | **Remarques** |
| --- | --- | --- |
| **Informations de contact**<ul><li>Nom</li><li>Adresse e-mail (y compris hachée)</li><li>Numéro de téléphone (y compris haché)</li><li>Adresse postale</li><li>Autres coordonnées de l'utilisateur</li></ul> | Non | Les coordonnées ne doivent pas être collectées. Mais si vous avez configuré votre app pour qu'elle transmette les e-mails ou numéros de téléphone hachés, vous devez l'indiquer dans le questionnaire de l'App Store. |
| **Forme physique** | Non | Ne pas collecter |
| **Infos bancaires**<ul><li>Informations de paiement</li><li>Infos sur la carte bancaire</li><li>Autres éléments bancaires</li></ul> | Non | Ne pas collecter |
| **Infos de localisation**<ul><li>Localisation précise</li><li>Localisation large</li></ul> | Voir les remarques | <ul><li>Localisation précise : non</li><li>Localisation élargie : oui L'adresse IP est collectée et associée à une localisation élargie.</li></ul> |
| **Informations sensibles** | Non | Ne pas collecter |
| **Contacts** | Non | Ne pas collecter |
| **Contenu de l'utilisateur**<ul><li>E-mails ou SMS</li><li>Photos ou vidéos</li><li>Données audio</li></ul> | Non | Ne pas collecter |
| **Historique de navigation** | Non | Ne pas collecter |
| **Historique de recherche** | Non | Ne pas collecter |
| **Identifiants**<ul><li>ID utilisateur</li><li>ID d'appareil (IDFA)</li></ul> | OPTIONNELLE | <ul><li>ID d'utilisateur : les développeurs d'app peuvent définir et transmettre l'ID d'utilisateur (CUID)</li><li>ID d'appareil : l'identifiant publicitaire (IDFA) est collecté uniquement s'il est accessible.</li></ul> |
| **Achats**<ul><li>Historique des achats</li></ul> | OPTIONNELLE | Les développeurs d'app peuvent choisir de configurer les événements in-app d'achat qui seront mesurés. |
| **Données d'utilisation**<ul><li>Interaction avec les produits</li><li>Données des publicités</li><li>Autres données d'utilisation</li></ul> | <ul><li>Oui</li><li>OPTIONNELLE</li><li>Non</li></ul> | <ul><li>Interactions avec les produits : les lancements d'app sont mesurés, ainsi que toute autre interaction de l'utilisateur qui aura été configurée par le développeur.</li><li>Données publicitaires : elles sont transmises si le développeur d'app utilise le module de revenu publicitaire AppsFlyer.</li></ul> |
| **Données de diagnostic**<ul><li>Données sur les crashs</li><li>Données sur les performances</li><li>Autres données de diagnostic</li></ul> | <ul><li>Non</li><li>Oui</li><li>Non</li></ul> | L'heure de lancement et/ou les niveaux de batterie peuvent être transmis pour détecter les fraudes. |
| **Autres données**<ul><li>Autres types de données</li><li>IDFV</li></ul> | Oui | <ul><li>Les informations techniques sur l'appareil (ex : système d'exploitation, type d'appareil, langue, taille d'écran, etc.) ou les informations sur le réseau (ex : adresse IP, agent utilisateur HTTP) sont transmises à AppsFlyer.</li><li>AppsFlyer applique un ID d'installation à chaque installation d'app : l'ID AF.</li><li>L'IDFV est collecté</li></ul> |

### Les objectifs d'utilisation des données

Apple dispose d'une liste d'objectifs dans laquelle les développeurs d'app doivent choisir, comme indiqué dans le tableau suivant. Vous devez cerner les motifs propres à chaque type de données en fonction de votre utilisation.

| Objectif des données | Sélection reposant sur la manière dont les données d'AppsFlyer seront utilisées |
| --- | --- |
| Publicité tierce | Indiquez si vous partagez le type de données avec dans le but d'afficher des publicités tierces dans votre app. |
| Publicité ou marketing du développeur | À sélectionner en cas d'utilisation pour afficher vos propres publicités dans votre app (si vous les partagez avec un tiers pour qu'il affiche vos publicités également), ou dans tout autre contexte de marketing. |
| Solutions d'analyse | Oui |
| Personnalisation des produits | À sélectionner si vous utilisez les données pour toute personnalisation de produit. |
| Fonctionnalité de l'app | Oui |
| Autres objectifs | À sélectionner si vous utilisez les données pour toute autre raison qui n'apparait pas dans la liste. |

### Données liées à une identité

Les types de données recueillis via AppsFlyer sont généralement liés à un identifiant, par exemple l'ID d'appareil (si disponible), ou les ID définis par le client lors de la configuration.  

Les développeurs d'app doivent donc répondre **Oui** lorsqu'on leur demande si les données sont liées à une identité.

> 📄 **À consulter également**
>
> * <Anchor target="_blank" href="https://www.appsflyer.com/services-privacy-policy/">Politique de confidentialité des services AppsFlyer</Anchor> : comment AppsFlyer gère et utilise les données
> * <Anchor target="_blank" href="https://developer.apple.com/app-store/app-privacy-details/">Infos détaillées sur la confidentialité d'une app dans l'app store par Apple</Anchor>.

<div data-zendesk-anchors="nutrition-labels-and-the-app-store-review=%C3%A9tiquettes-nutritionnelles-et-examen-de-lapp-store h_01HE7T7J409620K5KX5XKPEQVZ=%C3%A9tiquettes-nutritionnelles-et-examen-de-lapp-store data-types-collected=types-de-donn%C3%A9es-collect%C3%A9es h_01HE7T7J4004XVJTMF6S964DVB=types-de-donn%C3%A9es-collect%C3%A9es data-use-purposes=les-objectifs-dutilisation-des-donn%C3%A9es h_01HE7T7J4098NNW8D0BCD3EFBJ=les-objectifs-dutilisation-des-donn%C3%A9es data-linked-to-an-identity=donn%C3%A9es-li%C3%A9es-%C3%A0-une-identit%C3%A9 h_01HE7T7J41BJG9GTBWMVKG7031=donn%C3%A9es-li%C3%A9es-%C3%A0-une-identit%C3%A9 h_01HE7TES34MEF1XR4B6BDEMJW4=%C3%A0-consulter-%C3%A9galement" />
