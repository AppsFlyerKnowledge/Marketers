---
title: API OneLink
metadata:
  keywords:
    - api
    - Premium
    - Marketers
    - QR-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - Premium
    - pm-asaf-mashiah
    - Marketers
    - QR-to-App
  created_at: '2018-06-27T12:00:29Z'
  edited_at: '2023-08-14T09:18:49Z'
  id: 360001250345
  locale: fr
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/fr/articles/360001250345
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En bref :** l'API OneLink vous aide à engager les utilisateurs finaux et à tirer parti des médias propres en générant des liens personnalisés dans les campagnes à grande échelle, par SMS, etc. Nécessite une implémentation côté annonceur et côté développeur.

<div id="about-onelink-api" />

## API OneLink

L'API OneLink est utilisée pour :

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/create-onelink-attribution-link">Créer</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get-onelink-attribution-link">obtenir</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/update-onelink-attribution-link">mettre à jour</Anchor> et <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/delete-onelink-attribution-link">supprimer</Anchor> automatiquement les URL courtes OneLink avec des paramètres personnalisés.  
  Les paramètres peuvent être les suivants :
  * Les paramètres liés à l'attribution, utilisés pour mesurer et surveiller les efforts marketing, comme la source média, la campagne et l'actif. **Note** : le paramètre (pid) de la source média est obligatoire.
  * Les paramètres de personnalisation, qui vous permettent de configurer une expérience utilisateur personnalisée lorsque l'app est ouverte à partir du lien correspondant. Ces paramètres vous permettent de diriger des utilisateurs vers du contenu in-app personnalisé, par exemple, une page produit spécifique, un code coupon ou une promotion.
* Permettre le partage du contenu des sites web et des apps directement avec les utilisateurs mobile (ce qui augmente l'engagement et les installations mobile).
* Générer instantanément un grand nombre de liens d'attribution personnalisés OneLink.  
  **Remarque** : pour les liens de parrainage, consultez l'<Anchor target="_blank" href="/marketers/fr/docs/user-invite-attribution">article sur l'attribution des invitations utilisateurs</Anchor>.

> 📄 **Exemple**
>
> Feed Me, un service de livraison de produits alimentaires, souhaite envoyer un lien personnalisé par SMS à ses clients existants pour les encourager à télécharger l'app Feed Me et à acheter des bananes. En fonction du pays du client, Feed Me utilise l'API REST OneLink pour construire une URL OneLink personnalisée qui contient des détails spécifiques pour le pays, l'identité de l'utilisateur et une offre spéciale pour les bananes en vente.

Le nombre de requêtes API OneLink que vous pouvez lancer est limité en fonction de votre type de compte. Vous pouvez voir combien de requêtes vous avez déjà effectuées, et combien il vous en reste, dans le tableau de bord de l'API OneLink. 

Vous pouvez contacter votre CSM pour augmenter le nombre de requêtes API autorisé.  

### Configuration

**Pour configurer l'API OneLink :**

1. <Anchor target="_blank" href="/marketers/fr/docs/create-a-onelink-template#procédures">Créez un modèle OneLink</Anchor>.
2. Enregistrez l'ID OneLink.   

   [![](https://files.readme.io/b25f9c4dfe6f4a5a39e9b0a4d1b82d68330f8c0853248284564ac46c72d4d423-360019487418.jpg)](https://files.readme.io/b25f9c4dfe6f4a5a39e9b0a4d1b82d68330f8c0853248284564ac46c72d4d423-360019487418.jpg)
3. Enregistrez la clé API OneLink.Un utilisateur admin doit forcément récupérer la clé API, les utilisateurs du compte n'y ont pas accès. 
   * Dans le tableau de bord AppsFlyer, allez dans **Expériences et deep Linking** > **API OneLink** > **Voir la clé API OneLink**
   * Si l'admin ne peut pas récupérer la clé API OneLink, cela signifie que vous n'avez pas le package requis et que vous devez contacter votre CSM.
4. Donnez l'ID OneLink et la clé API OneLink au développeur.
5. Demandez au développeur de suivre les <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/onelink_rest_api">instructions du dev hub</Anchor>.

<div id="dashboard" />

### Tableau de bord

Le tableau de bord OneLink API s'affiche :

* Votre utilisation quotidienne, mensuelle et trimestrielle de l'API.
* La clé API OneLink.

**Pour afficher le tableau de bord de l'API OneLink** : 

Dans AppsFlyer, allez dans **Expériences et deep Linking** > **API OneLink**.

<div id="traits-and-limitations" />

### Particularités et limites

| **Particularité** | **Remarques** |
| --- | --- |
| Quota de l'API | <ul><li>La limite d'utilisation de l'API OneLink pour créer, modifier ou supprimer des liens OneLink est de 7,5 millions par mois (fuseau horaire UTC) par compte.</li><li>Toutes les requêtes lancées **après** le dépassement de ce quota ne seront pas prises en charge et les liens ne seront pas créés, l'appel d'API recevra le code d'erreur 429 avec le message «Quota mensuel dépassé»".</li><li>Le tableau de bord de l'API OneLink affiche les informations sur la consommation et le nombre de requêtes restantes.</li></ul> |
| Seuil limite | <ul><li>Le débit maxi de l'API par compte est de 500 requêtes par seconde (30000 par minute).</li><li>Toutes les requêtes dépassant 500 par seconde (30000 par minute) ne sont pas traitées et les liens ne sont pas créés; l'appel d'API reçoit le code d'erreur 429 avec le message «Limite dépassée».</li></ul> |
| Visibilité des liens | <ul><li>Les liens créés via l'API n'apparaissent pas dans la liste des liens personnalisés OneLink dans le tableau de bord AppsFlyer.</li><li>Bonne pratique : enregistrez les liens créés avec l'API dans un tableau local, afin de pouvoir accéder aux liens à tout moment.</li></ul> |
| Durée de vie | <ul><li>La durée de vie (TTL) par défaut des URL courtes OneLink créées par API OneLink est de 31 jours. Elle est prolongée de 31 jours à chaque fois que le lien est cliqué.Le fait de cliquer sur un tel lien une fois que la TTL a expiré entraînera toujours le comportement défini dans la configuration de base de OneLink, mais l'attribution ne fonctionnera pas.<ul><li>La suppression d'une URL courte OneLink peut prendre jusqu'à 48 heures après expiration de la TTL.</li></ul></li><li>La durée de vie maximum est de 31 jours. Toute valeur de durée de vie supérieure à 31 est remplacée par la valeur de durée de vie par défaut de 31.</li><li>Vous pouvez modifier la TTL par défaut en ajoutant le paramètre `ttl={value}` et en spécifiant le nombre de jours, d'heures ou de minutes. Par exemple `ttl=7d`, `ttl=12h`, ou `ttl=10m`.</li><li>Vous pouvez envoyer une <Anchor target="_blank" href="https://dev.appsflyer.com/reference/onelink_rest_api#update-onelink-attribution-link">demande de mise à jour</Anchor> pour spécifier la durée de vie. Toute demande de mise à jour réinitialise la durée de vie (pour les liens existants) à celui spécifié dans le corps de la demande.<ul><li>Cela signifie que la durée de vie est remplacée. Par exemple, si vous effectuez un appel de mise à jour avec une durée de vie de 2 jours pour un lien qui possède actuellement une durée de vie 29 jours, il passera à **TTL=2j** (pas 31 j).</li><li>Un appel de mise à jour peut potentiellement prolonger la durée de vie du lien d'attribution. Par exemple, si vous effectuez un appel de mise à jour avec une durée de vie de 31 jours pour un lien qui possède actuellement une durée de vie 20 jours, mais que 5 jours se sont écoulés, la durée de vie passera à 31 jours au moment de la mise à jour.</li></ul></li><li>Si vous ne souhaitez pas que les TTL des liens soient automatiquement prolongées, ajoutez le paramètre `renew_ttl=false` à vos liens. La valeur de ce paramètre est un booléen, soit true (par défaut), soit false.</li><li>Le paramètre `renew_ttl` ne s'affiche pas dans l'URL actuelle.</li></ul> |
| Caractères spéciaux | Les caractères suivants doivent être encodés s'ils sont utilisés pour les liens créés par l'API : ;, *, !, @, #, ?, $, ^, :, &, ~, \`, =, +, ', >, &lt;, /  <br />Si vous n'encodez pas ces caractères, ils seront remplacés par un espace vide, et le lien et sa fonctionnalité pourront être défectueux. |
| Charge utile | La chaîne de requête de la charge utile ne peut pas dépasser 2048 caractères. |
| ID d'URL | L'ID de l'URL (ou ID du lien court) peut être modifié pour mettre en avant l'offre de votre campagne.Par exemple : https://myapp.onelink.me/abc123/pommes.L'ID d'URL peut comporter au maximum 50 caractères et peut inclure des lettres et des chiffres.Par défaut, il comporte 8 caractères.<br /><br />**Remarque** :<ul><li>Vous ne pouvez modifier l'ID de l'URL que si l'ID actuel n'est pas déjà utilisé.</li><li>Si l'ID URL est déjà utilisé, la création du lien échouera et enverra une réponse d'erreur (400).Vous devez décider avec votre développer de l'action à prendre dans un tel cas.</li><li>L'échec de l'appel sera pris en compte dans votre quota mensuel d'API.</li></ul> |

<div data-zendesk-anchors="onelink-api=api-onelink setup=configuration dashboard=tableau-de-bord traits-and-limitations=particularit%C3%A9s-et-limites" />
