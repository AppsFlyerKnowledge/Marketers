---
title: Configuration d’une campagne Pinterest
metadata:
  keywords:
    - Pinterest
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2016-11-09T12:51:03Z'
  edited_at: '2024-08-20T06:37:51Z'
  id: 216912786
  locale: fr
  section: Pinterest
  section_id: 6551388216337
  url: https://support.appsflyer.com/hc/fr/articles/216912786
---
> **En bref :** Pinterest, un partenaire intégré à AppsFlyer, est l’un des principaux contributeurs de trafic pour les blogueurs et les marques. Pinterest propose à la fois une attribution mobile basée sur les clics et une attribution mobile post-vue. Pinterest propose également le retargeting basé sur les clics que vous pouvez enregistrer via AppsFlyer.

<div id="note" />

> 📘 **Remarque**
>
> * Depuis juin 2021, Pinterest ne propose plus de campagnes CPI, par conséquent, AppsFlyer n’envoie aucun postbacks d’installation à Pinterest.
> * Après avoir accepté les conditions d’utilisation des publicités Pinterest, vous devez accepter les conditions et termes des mesures de Pinterest Mobile <Anchor target="_blank" href="https://ads.pinterest.com/terms/app_install/">ici</Anchor>.
> * Pinterest demande aux prestataires d'attribution de supprimer ses données de niveau utilisateur <Anchor target="_blank" href="/marketers/fr/docs/user-level-data-retention#périodes-de-conservation-des-données-des-partenaires">6 mois après l'installation.</Anchor> Cela signifie que les évènements effectués par ces utilisateurs 6 mois après l'installation de l'app sont considérés comme organiques. Les données agrégées précédentes restent les mêmes.
> * Depuis le 4 septembre 2023, Pinterest demande aux fournisseurs d’attribution de <Anchor target="_blank" href="/marketers/fr/docs/about-raw-data-identifier-restrictions#restrictions-des-sources-média">restreindre l’affichage de certains champs dans les rapports de données brutes</Anchor>, et ce afin de préserver la confidentialité des utilisateurs et de respecter la législation en cours.

<div id="set-up-pinterest" />

## Configurer Pinterest

**À effectuer :**  avant de configurer une intégration, vous devez  <Anchor target="_blank" href="/marketers/fr/docs/partner-integrations#contacter-le-partenaire">contacter le partenaire</Anchor> et ouvrir un compte chez lui.

**Pour activer ou modifier l'intégration :**

1. **Activation :** dans AppsFlyer, dans le menu latéral, choisissez **Collaboration** /span>>/span> **Partenaire Marketplace**.  
   **Modification :** dans AppsFlyer, dans le menu latéral, sélectionnez **Collaboration** > **Intégrations actives**.
2. Recherchez **Pinterest** et sélectionnez-le.
3. Cliquez sur Configurer l'intégration. Vous êtes alors dirigé vers la page de configuration de l'intégration.
4. Dans l'onglet Integration, sélectionnez l'app à intégrer et cochez l’option **Activer le partenaire**.  
   **Remarque** : **La case doit rester cochée (activée)/span> tant que vous collaborez avec le partenaire.**
5. Terminez la configuration pour chacun des onglets détaillés ci-après.

La fenêtre de configuration de Pinterest contient 4 onglets actifs : Intégration, Lien d’attribution, Coût et Autorisations. Cliquez sur les éléments ci-dessous pour en savoir plus sur la configuration des onglets.

Pour obtenir une description détaillée de l'en-tête de la fenêtre de configuration du partenaire, cliquez <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">ici</Anchor>.

<div id="integration-tab" />

<Accordion title="Onglet Intégration">

<div id="activate-partner" />

### Activer le partenaire

Lors de la **première visite**, vous devrez allumer le bouton **Activer le partenaire** pour permettre la configuration des paramètres de l’onglet intégration. Cette option doit rester activée tant que vous travaillez avec le partenaire.  
Pour plus de détails sur l'activation des partenaires, cliquez sur <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">ici</Anchor>.

<div id="general-settings" />

### Paramètres généraux

Voici les paramètres généraux de l’onglet Intégration de Pinterest.

**Activer l'attribution post-vue**

Activez cette option si vous souhaitez attribuer les installations post-vue de Pinterest. Le curseur rétroactif post-vue est disponible dans l'onglet Lien d'attribution (détails ci-dessous).

<div id="legacy-set-tag-id" />

<div id="in-app-events-settings" />

<div id="including" />

<div id="to-users-from" />

<div id="partner-event-name" />

<div id="appsflyer-event-name" />

<div id="in-app-event-postbacks" />

### Paramètres des événements in-app

Cette section vous permet de mapper vos évènements AppsFlyer à Pinterest au moyen de postbacks.

**ID de balise**

Pour pouvoir envoyer des postbacks d’évènements in-app à Pinterest, vous devez saisir un ID de balise. Si vous n’avez pas d’ID de balise, vous pouvez le récupérer dans Pinterest.

Dans votre compte Pinterest Business :

1. Allez dans **Publicités** > **Conversions**.
2. Dans la page **Conversions**, copiez l’**ID de balise**.  
   Cliquez sur **Créer une balise** si vous n’avez pas encore de balise, et terminez la création. Copiez la nouvelle balise.

**Remarque** : L’ID de balise n’est requis que pour les postbacks d’événement.

<Image align="center" alt="" src="https://files.readme.io/8d5c3b6d1dd7542860d58b2cff8581a8eb72880764b730a4c87b8161eb04edab-360001712765.png" />

1. Définissez l’ID de la balise Pinterest ici.
2. Activez les**Postbacks d'événement in-app.**
3. Sélectionnez le type d'envoi pour tous les évènements définis dans SDK.  
   **- Seuls les évènements attribués à ce partenaire** pour les évènements issus **exclusivement** des utilisateurs attribués à ce partenaire  
   **- Évènements attribués à n’importe quel partenaire ou organique** pour que l’intégralité de votre base d'utilisateurs puisse être rapportée au partenaire
4. Cliquez sur **Ajouter un événement** pour ajouter un événement SDK à la liste
5. Remplissez les paramètres suivants :

| Nom du paramètre | Description |
| --- | --- |
| **Nom de l'évènement SDK** | Le nom de l'événement tel que transmis à AppsFlyer, soit par le SDK intégré à votre app, soit par les événements de serveur à serveur.  <br />**Astuce** : si l'événement que vous cherchez n'est pas dans la liste, vérifiez que vous activez bien l'événement sur un appareil avec une installation non-organique. |
| **ID d'événement partenaire** | Le nom ou l’identifiant unique de chaque événement, tel que défini du côté de Pinterest.  <br />Obtenez l’ID d’événement correspondant dans Pinterest, puis inscrivez-le dans le champ de texte. |
| **Envoyer les revenus** | **Lorsque cette case n'est pas cochée**, AppsFlyer envoie tous les paramètres de l'évènement rich in-app au partenaire, à l'exception du paramètre revenu, qui se trouve dans le paramètre **af\_revenue**.  <br />**Lorsque cette case est cochée**, AppsFlyer envoie tous les paramètres, y compris la valeur de revenu (si elle existe dans l'évènement). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Onglet Lien d'attribution">

Pour générer et enregistrer les liens d’attribution et les envoyer au partenaire dans le but d’attribuer des campagnes spécifiques, des ad sets ou des publicités uniques, et ce autant pour les campagnes UA que les campagnes de retargeting. Vous pouvez utiliser un lien à plateforme unique ou un <Anchor target="_blank" href="/marketers/fr/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters">En savoir plus sur la structure et les paramètres des liens d’attribution</Anchor>.  

**Pour générer un lien d’attribution, veuillez**suivre <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#attribution-link-tab">ces instructions</Anchor>.

<div id="attribution-link-for-retargeting-campaign" />

#### Lien d’attribution pour une campagne de retargeting

Pinterest recommande d’utiliser les liens d’attribution propres au système d’exploitation pour les campagnes de retargeting. Sélectionnez l’icône **Utiliser un lien de plateforme unique** et ajoutez les paramètres nécessaires au lien d’attribution de retargeting.

<div id="deep-link-url" />

#### URL de deep link

<div id="note-1" />

> 📘 **Remarque**
>
> Le deep linking depuis un pin ne fonctionneront correctement que si votre application est autorisée par Pinterest.
> Contactez votre représentant Pinterest, ou envoyez un e-mail à [apps@pinterest.com](mailto:apps@pinterest.com) pour que votre app soit autorisée à être deep linkée.

Utilisez ce champ si le lien est destiné à deep linker les utilisateurs à une quelconque activité de votre app.

</Accordion>

<div id="cost-tab" />

<Accordion title="Onglet Coût">

Une fois que vous avez défini les coûts dans Pinterest, ne modifiez aucun nom de campagne en cours, adset ou publicité unique, et n’utilisez pas de macros dynamiques dans le paramètre du nom des campagnes, au risque de générer de grosses erreurs dans les résultats de coûts, ou de perdre ces données.

<div id="enabling-and-testing-pinterest-integration" />

### Activer et tester l’intégration de Pinterest

AppsFlyer reçoit les données de coûts par API. Consultez le <Anchor target="_blank" href="/marketers/fr/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tableau d'intégration des coûts du réseau publicitaire</Anchor> pour obtenir plus d'infos sur les dimensions, les métriques et les fonctionnalités prises en charge. **Remarque** : Les données de coût nécessitent un abonnement ROI360./span>

**Pour activer l'API de coûts :**

* Suivez  <Anchor target="_blank" href="/marketers/fr/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">ces instructions d'intégration</Anchor>.

<div id="cost-data-sync-status" />

### État de synchronisation des données de coût

<Anchor target="_blank" href="/marketers/fr/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">Affichez le statut de votre API des coûts,</Anchor> ainsi que la dernière fois où AppsFlyer a pu extraire les données de coûts correspondantes, soit dans le tableau de bord du statut d'intégration des coûts (et des revenus publicitaires), soit dans le tableau de bord du réseau publicitaire individuel.

<div id="stop-pinterest-cost-sync" />

### Arrêter la synchronisation des coûts Pinterest

**Pour supprimer un compte connecté :**

* Dans la colonne Actions, survolez le compte, cliquez sur <Anchor target="_blank" href="/marketers/fr/docs/set-up-roi360-cost-api-to-measure-cost-data#deleting-connected-accounts-in-the-cost-tab">Supprimer la connexion.</Anchor> Une fois supprimée, AppsFlyer cesse de recevoir les <Anchor target="_blank" href="/marketers/fr/docs/set-up-roi360-cost-api-to-measure-cost-data#deleting-connected-accounts-in-the-cost-tab">coûts</Anchor>. Supprimer la connexion n’a aucun impact sur les données historiques.

<div id="ad-revenue-tab" />

<Accordion title="Onglet Revenus publicitaires">

Les données des revenus publicitaires ne sont pas prises en charge par ce partenaire.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Onglet Autorisations">

Dans cet onglet, vous pouvez sélectionner les autorisations à accorder à Pinterest. Notez que même si l'attribution est désactivée pour Pinterest, l'onglet des autorisations est actif et vous pouvez accorder le contrôle à Pinterest.

En savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#permissions-tab">les autorisations qui peuvent être accordée à Pinterest.</Anchor>

</Accordion>

</Accordion>

<div id="troubleshooting" />

## Dépannage

Message d’erreur de l’onglet Coût : *Aucune donnée correspondante* indique que le compte Pinterest que vous avez connecté à AppsFlyer n’est pas le bon compte Pinterest. Aucune donnée correspondant à l’app n’a été trouvée. Connectez-vous à Pinterest avec des identifiants différents.

<div data-zendesk-anchors="h_01H95QTA3ZZ9GJW9EN1VZ01TH2=remarque set-up-pinterest=configurer-pinterest h_01H95QTA3Z5HXW39AHAF8FMFWH=configurer-pinterest h_01H95QTA3ZNQWBRA86E6TRQ46Y=integration-tab activate-partner=activer-le-partenaire h_01H95QTA3ZGEM34HY1A7NC8NX7=activer-le-partenaire general-settings=param%C3%A8tres-g%C3%A9n%C3%A9raux h_01H95QTA3Z0NW9V51D8J7MHEX0=param%C3%A8tres-g%C3%A9n%C3%A9raux inapp-events-settings=param%C3%A8tres-des-%C3%A9v%C3%A9nements-in-app h_01H95QTA3ZWSF0JYZ9D4HEB4A4=param%C3%A8tres-des-%C3%A9v%C3%A9nements-in-app h_01H95QTA3ZT7PVGAJW5AKPC186=attribution-link-tab attribution-link-for-retargeting-campaigns=lien-dattribution-pour-une-campagne-de-retargeting h_01H95QTA3ZPQZ422AB2JBZAS07=lien-dattribution-pour-une-campagne-de-retargeting deep-link-url=url-de-deep-link h_01H95QTA3ZT23CYTCE2V3728MD=url-de-deep-link h_01H95QTA3ZYHQED2T5B2FA5PV8=remarque-1 h_01H95QTA3Z3XJDM5YRXFK7DA0E=cost-tab enabling-and-testing-pinterest-integration=activer-et-tester-lint%C3%A9gration-de-pinterest h_01H95QTA3ZZ56R8EZBJY1ESX5W=activer-et-tester-lint%C3%A9gration-de-pinterest cost-data-sync-status=%C3%A9tat-de-synchronisation-des-donn%C3%A9es-de-co%C3%BBt h_01H95QTA3ZST8WS3TAR79H06FM=%C3%A9tat-de-synchronisation-des-donn%C3%A9es-de-co%C3%BBt stop-pinterest-cost-sync=arr%C3%AAter-la-synchronisation-des-co%C3%BBts-pinterest h_01H95QTA3ZFCJ82E3YDMP7S716=arr%C3%AAter-la-synchronisation-des-co%C3%BBts-pinterest h_01H95QTA3ZM2REWR2A5DHK1DSA=ad-revenue-tab h_01H95QTA3ZM4WPHV3MB00WZXSB=permissions-tab troubleshooting=d%C3%A9pannage h_01H95QTA3ZP20DSJQGY4QQX0Z7=d%C3%A9pannage" />
