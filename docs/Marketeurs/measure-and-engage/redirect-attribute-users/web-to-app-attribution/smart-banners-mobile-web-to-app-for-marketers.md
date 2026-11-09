---
title: >-
  Bannières intelligentes : transformer un site web en app mobile (web-to-app à
  l'usage des marketeurs)
metadata:
  keywords:
    - Landing Page
    - Advertisers
    - Web Attribution
    - Developers
    - Smart Banner
    - sb
    - Marketers
    - Banner
    - Banners
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2019-01-14T12:33:07Z'
  edited_at: '2023-11-30T11:59:20Z'
  id: 360000764837
  locale: fr
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/fr/articles/360000764837
---
> **En bref :** convertissez les visiteurs de votre site web en utilisateurs d'applis mobiles grâce aux bannières intelligentes.

<Image align="center" alt="" src="https://files.readme.io/2e76dd3d337d7cb8e34af01b34f3a466fa724566058d260f56796bf6eae4b3ff-34734678772881.jpg" />

<div id="note" />

> 📘 **Remarque**
>
> Le SDK web V1 AppsFlyer Smart Banner a été supprimé le 8 novembre 2023. Pour afficher les bannières intelligentes sur votre site web, vous devez passer à la version 2. <Anchor target="_blank" href="/marketers/fr/docs/bulletin-deprecation-of-appsflyer-smart-banner-web-sdk-v1">En savoir plus</Anchor>

## Smart Banners

Bannières intelligentes :

* **Affichez-les sur le site web mobile de votre marque** pour augmenter les taux de conversion des utilisateurs à forte intention d'achat.
* Mesurez la qualité des installations d'apps provenant de visiteurs du site web mobile.
* Attribuez les campagnes web-to-app mobile avec précision pour TOUTES les sources média, y compris les SRN.
* Les bannières intelligentes peuvent utiliser <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-attribution-model#types-dengagement-utilisateur-menant-à-une-attribution">l'attribution post-vue ou post-clic</Anchor> et comptabiliser les impressions :
  * **Clics :** un utilisateur clique sur les bannières intelligentes et installe l'app.
  * **Impressions :** lorsque la bannière se charge (l'utilisateur voit la bannière), elle envoie un événement de comptabilisation d'impression à AppsFlyer.

Le flux est le suivant :

1. Un utilisateur clique sur une annonce et est redirigé vers le site web mobile de l'annonceur.
2. Une bannière intelligente [s'affiche](/docs/smart-banners-mobile-web-to-app-for-marketers#banner-group-display-logic) sur le site web mobile de l'annonceur.
3. L'utilisateur clique sur la bannière intelligente et :
   * **Si l'app n'est pas installée,** l'utilisateur est dirigé vers l'App Store pour installer l'app.
   * **Si l'app est installée** et que des liens universels, des liens d'app et/ou des liens URI sont configurés, l'app est lancée directement.
4. L'utilisateur accède au contenu in-app, dans le cadre de la promotion.
5. L'utilisateur est attribué à la source média qui a diffusé l'annonce originale.

**Personnes concernées**

* Le développeur du site web doit seulement <Anchor target="_blank" href="/marketers/fr/docs/smart-banners-website-code-implementation-for-developers">saisir un extrait de code dans le code HTML du site.</Anchor>
* Pour toute autre action, le marketeur seul suffit.

---

**Conditions préalables**

* Un compte AppsFlyer avec au moins une app
* <Anchor target="_blank" href="/marketers/fr/docs/create-a-onelink-template">Template OneLink</Anchor> contenant les apps à promouvoir via les bannières intelligentes. Ceci est requis par les bannières intelligentes pour diriger vos visiteurs web mobile vers les pages ciblées de l'app store en fonction des appareils qu'ils utilisent.

---

**Durée**

Environ 20 minutes.

---

**Résultat**

* Les utilisateurs qui cliquent sur le lien sont dirigés vers l'app store ou la page web appropriée selon leur appareil.
* Les utilisateurs d'apps mobile qui cliquent sur le bouton CTA peuvent être deep linkés vers l'app.
* Les utilisateurs sont attribués à partir du clic/de l’installation jusqu'aux sources média d’origine ou jusqu'à vos sources média propres.
* Les performances des bannières peuvent être consultées sur la page et les cartes de performances.

---

---

<div id="example" />

> 📄 **Exemple**
>
> Mark est un marketeur travaillant pour le service de livraison de nourriture « Feed Me ».
>
> Mark souhaite convertir les visiteurs du site web mobile de Feed Me en utilisateurs de l'app.
>
> Pour ce faire, Mark utilise des bannières intelligentes réalisées avec ses propres visuels et textes.
>
> Les bannières intelligentes sont optimisées par OneLink. Lorsque les visiteurs du site web mobile cliquent sur le bouton CTA, ils sont **automatiquement redirigés vers l'app store ou la page de destination appropriée**. À partir de là, ils peuvent installer l'app facilement. Lorsque les utilisateurs mobile existants cliquent sur le bouton CTA, l'app se lance.
>
> AppsFlyer **attribue ensuite le clic/l'installation à la source média et à la campagne définies par AppsFlyer**.

> 🚧 **Important !**
>
> Utilisez la bannière intelligente AppsFlyer ou les bannières Smart App pour iOS Safari, mais pas les deux. Si vous utilisez les deux, vous pouvez générer des problèmes d'affichage sur votre site web mobile et des divergences d'attribution.

<div id="setup" />

## Configuration

Suivez ces étapes pour définir une bannière intelligente qui :

* Dirige les utilisateurs de votre site mobile, via une bannière intelligente, vers l'app store ou la page d'app appropriée en fonction de leur appareil.
* Attribue le clic/l'installation à votre source média propre.

<div id="1-website-workplace-setup" />

<Accordion title="1. Configuration de l'espace de travail du site web">

<div id="prepare-your-mobile-site-to-display-smart-banners-for-the-first-time" />

#### Préparez votre site mobile à afficher des bannières intelligentes pour la première fois

1. Dans le tableau de bord AppsFlyer, rendez-vous dans **Expériences et Deep Linking** > **Web-to-app** > **Bannières intelligentes** > **Bannières intelligentes.**
2. Cliquez sur **Démarrer.** L'assistant de configuration vous guidera à travers les étapes requises (ci-dessous). Pour configurer d'autres pages web, voir ci-dessous.
3. Saisissez un nom d'espace de travail pour le site.
4. Cliquez sur **Créer** . L'espace de travail du site web s'ouvre.
5. Copiez la bannière **Extrait de code**.
6. Implémentez l'extrait de code sur votre site web. Cette tâche est à effectuer une seule fois par site web.
   * Pour ajouter le code à votre site via Google Tag Manager, Adobe Tag Manager, Shopify, Wix, Squarespace ou WordPress, consultez l'article <Anchor target="_blank" href="/marketers/fr/docs/smart-banners-website-code-implementation-for-marketers">Implémenter le code web des bannières intelligentes à l'attention des marketeurs.</Anchor>
   * Pour ajouter le code via d'autres plateformes, ou pour apporter des modifications au code en fonction des besoins (y compris l'ajout de paramètres, le deep linking, le masquage de la bannière ou l'intégration de PBA avec Smart Banners), voir <Anchor target="_blank" href="/marketers/fr/docs/smart-banners-website-code-implementation-for-developers">Implémentation du code web Smart Banners pour les développeurs .</Anchor>
7. [facultatif] Copier la **clé web** (cette clé existe déjà en tant que partie de l'extrait de code).
8. Cliquez sur **Continuer**.

<div id="attributed-sources" />

<div id="param-table" />

<div id="to-create-website-workplaces-after-the-first-time" />

#### Pour créer des pages web ensuite

1. Dans le tableau de bord AppsFlyer, rendez-vous dans **Expériences et Deep Linking** > **Web-to-app** > **Bannières intelligentes** > **Studio**.
2. Cliquez sur le menu des options
3. sélectionnez **Nouvelle page web**
4. Saisissez un nom d'espace de travail pour le site.
5. Cliquez sur **Créer** . L'espace de travail du site web s'ouvre.
6. Copiez la bannière **Extrait de code**.
7. Implémentez l'extrait de code sur votre site web. Cette tâche est à effectuer une seule fois par site web.
   * Pour ajouter le code à votre site via Google Tag Manager, Adobe Tag Manager, Shopify, Wix, Squarespace ou WordPress, consultez l'article <Anchor target="_blank" href="/marketers/fr/docs/smart-banners-website-code-implementation-for-marketers">Implémenter le code web des bannières intelligentes à l'attention des marketeurs.</Anchor>
   * Pour ajouter le code via d'autres plateformes, ou pour apporter des modifications au code en fonction des besoins (y compris l'ajout de paramètres, le deep linking, le masquage de la bannière ou l'intégration de PBA avec Smart Banners), voir <Anchor target="_blank" href="/marketers/fr/docs/smart-banners-website-code-implementation-for-developers">Implémentation du code web Smart Banners pour les développeurs .</Anchor>
8. [facultatif] Copier la **clé web** (cette clé existe déjà en tant que partie de l'extrait de code).
9. Cliquez sur **Continuer**.

</Accordion>

<div id="2-banner-group-setup" />

<Accordion title="2. Configuration du groupe de bannières">

Le groupe de bannières contient une ou plusieurs bannières. De là, vous pouvez :

* Sélectionner le modèle OneLink utilisé par le groupe de bannières, qui contient les apps mobile vers lesquelles rediriger les visiteurs de votre site web.
* Définir un schéma spécifique de deep linking
* Définir vos règles de ciblage, votre planification, votre comportement et les détails d'attribution utilisés par toutes les bannières du groupe de bannières.
* Définir les pages qui activent les bannières du groupe de bannières lors de la visite.

**Pour configurer ou dupliquer un groupe de bannières :**

1. Dans le tableau de bord AppsFlyer, rendez-vous dans **Expériences et deep linking** > **Web-to-app** > **Bannières intelligentes**.
2. **Pour créer un premier groupe de bannières**
   1. <span class="af-ol-a"></span>Sur le côté gauche, cliquez sur **Ajouter un groupe de bannières**.
   2. Complétez les étapes 5 et suivantes.
3. **Pour créer des groupes de bannières supplémentaires**
   1. <span class="af-ol-a"></span>Ouvrez l'onglet **Studio**.
   2. Cliquez sur **+ Nouveau.**
   3. Complétez les étapes 5 et suivantes.
4. **Pour dupliquer un groupe de bannières**
   1. <span class="af-ol-a"></span>Cliquez sur l'icône **Dupliquer** (à côté de l'icône *Supprimer*).
5. Saisissez un **nom de groupe de bannières unique**. Le nom doit refléter un thème commun aux bannières à définir dans le groupe de bannières (par exemple, l'app qui est promue).
6. Sélectionnez le template OneLink pour le groupe de bannières.
7. [facultatif] Définissez un **schéma d'URI** pour le groupe de bannières comme solution de secours pour les utilisateurs des liens universels et des liens d'app Android. Ceci est rarement nécessaire car, par défaut, la valeur est prise dans le template OneLink. Définissez cette option pour le groupe de bannières uniquement si vous avez besoin d'une valeur différente de celle du template.
8. Définissez les sources principales et les sources de secours qui seront **attribuées** aux nouvelles installations issues de ce groupe de bannières. Utilisez le tableau suivant pour choisir la meilleure option pour le lien personnalisé. 

| Option | Quand sélectionner | Commentaires |
| --- | --- | --- |
| **Utiliser les paramètres UTM** | Sélectionnez le moment où la plupart des visiteurs non organiques accèdent au site web mobile à partir de sources avec des paramètres UTM. | ◦ Nom de la source média (pid) = UTM\_Source  <br />◦ Campagne (c) = UTM\_campaign  <br />◦ Si UTM\_source ou UTM\_campaign sont manquants, les noms statiques seront utilisés à la place. |
| **Utiliser les paramètres du lien d'attribution entrant** | Sélectionnez le moment où la plupart des visiteurs non organiques accèdent au site web mobile à partir des clics des réseaux publicitaires qui utilisent les liens d'attribution AppsFlyer. | ◦ Tous les paramètres disponibles du lien d'attribution AppsFlyer entrants sont ajoutés au lien de la bannière intelligente.<br /><br />◦ Si un paramètre existe à la fois dans le lien d'attribution AppsFlyer entrant et dans la bannière intelligente, c'est le paramètre entrant qui est prioritaire. |
| **Ajouter un autre paramètre d'attribution** | Si vous le souhaitez, vous pouvez ajouter des données d'attribution liées au site web. Cela permet une analyse plus pointue de chaque installation. | Par exemple, pour les sites de eCommerce, vous pouvez créer des liens personnalisés identiques pour chaque type de catégorie de produit, qui diffèrent selon les valeurs af\_adset (par exemple : af\_adset=fruit) |
| **Utiliser les paramètres d'attribution par défaut** | ◦ Sélectionnez cette fonction lorsque la plupart des visiteurs du site web mobile sont organiques.  ▪ Les visiteurs non organiques n'arrivent pas sur le site web à partir d'un clic de réseau publicitaire ou de sources ayant des paramètres UTM.   ◦ Vous pouvez personnaliser les valeurs des paramètres. | **Important :** la bonne pratique consiste à sélectionner les paramètres du lien d'attribution UTM ou entrant, car les paramètres d'attribution par défaut des bannières intelligentes sont dans tous les cas utilisés comme solution de secours pour le lien personnalisé, en cas d'indisponibilité des noms de source média, de campagne ou de canal. |

9. [Recommandé] Définissez le paramètre d'attribution par défaut **Nom du canal** pour attribuer toutes les installations provenant de la bannière intelligente au canal spécifié. Cela vous permet d'agréger des informations provenant de plusieurs sources média sous le même canal dans le **rapport de cohorte**, le **tableau de bord de présentation**, le **rapport de rétention**, etc.
10. <span id="2-banner-group-setup-step10"></span>[Facultatif] Activez le **retargeting** si vous prévoyez d'utiliser le groupe de bannières pour enregistrer les réengagements effectués par les utilisateurs qui cliquent sur la bannière. Pour en savoir plus sur le retargeting, consultez le <Anchor target="_blank" href="/marketers/fr/docs/retargeting-attribution-guide">guide d'attribution du retargeting.</Anchor>

    <div id="dismissal-behaviour" />

    <div id="important-1" />

    > 🚧 **Important**
    >
    > Pour que le retargeting fonctionne, vous devez également :
    >
    > * <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#activer-le-retargeting-pour-lapp">Activer le retargeting pour l’app</Anchor>


    Les utilisateurs existants qui cliquent sur un OneLink qui n'est pas un lien de retargeting (AU) lancent également l'app, et ils ont la même expérience utilisateur. Mais leurs réengagements sont enregistrés comme des sessions régulières, il est donc impossible de mesurer l'efficacité de la campagne média propre.
11. [Facultatif] Activez **Ignorer les utilisateurs actifs pour le retargeting** et sélectionnez la fenêtre d’inactivité. Le paramètre af\_inactivity\_window=[nombre de jours] est alors ajouté aux liens de votre groupe de bannières intelligentes, et tous les utilisateurs en activité sur la période sont ignorés dans le cadre du retargeting.
12. Définissez la fenêtre de réengagement pour déterminer la période suivant le réengagement, où les événements in-app de l'utilisateur sont attribués à la source média de retargeting.
    * Vous pouvez définir la valeur en jours (1-90), en heures (jusqu'à 23) ou même en valeur vie.
    * La fenêtre de réengagement est ajoutée au lien dans le paramètre af\_reengagement\_window.
13. [Facultatif] Définissez le **comportement d'annulation**, c'est-à-dire le minimum de temps qui s'écoule entre le moment où l'utilisateur ignore la bannière du groupe, et celui où la bannière s'affiche à nouveau. Sélectionnez :
    * Par durée : 1 heure, 1 jour ou 1 semaine.
    * Session suivante : désigne la session qui a lieu dans un autre onglet ou une autre fenêtre, après que l'utilisateur a quitté la bannière.
    * Jamais : la bannière ne s'affiche plus. **Remarque** :
      * Si l'utilisateur efface le cache du navigateur ou consulte le site en mode de navigation privée, le paramètre Dismissal Behaviour (Comportement d'abandon) est perdu.
      * Le comportement d'abandon est appliqué à la bannière que l'utilisateur rejette. Les autres bannières du groupe de bannières peuvent toujours être affichées.
14. [Facultatif] Définir le **plafonnement des fréquences.**    
    Le plafonnement des fréquences détermine le nombre de fois où chaque bannière de groupe est affichée pour un utilisateur unique. Vous pouvez choisir soit **Aucune limite** (les bannières s'affichent toujours), ou **Limiter l'affichage des bannières**.

    Par exemple, si un groupe de bannières est composé de trois bannières et que le plafond de fréquence est fixé à une, chaque bannière du groupe apparaîtra une fois par utilisateur. Dans ce scénario, après trois visites, l'utilisateur aura vu les trois bannières du groupe. Toutefois, à partir de la quatrième visite, l'utilisateur ne verra plus de bannières du groupe. Lorsque la limite de fréquence est fixée à deux, chaque bannière du groupe sera affichée deux fois par utilisateur, ce qui nécessitera un total de six visites pour atteindre la limite de fréquence du groupe.
15. [Facultatif] Définir le **système d'exploitation** sur lequel afficher les bannières :
    * Tous les systèmes d'exploitation mobile.
    * Android ou iOS uniquement.
16. [Facultatif] **Planifiez** l'activation du groupe de bannières : démarrez immédiatement (par défaut) ou définissez une campagne à durée limitée.
17. [Facultatif] Définissez les **emplacements** pour lesquels le groupe de bannières est activé.
    1. <span class="af-ol-a"></span>Sélectionnez **Monde entier** pour diffuser ce groupe de bannières à tous les utilisateurs. Si besoin, vous pouvez exclure les visiteurs provenant de différentes régions, pays ou états.
    2. Sélectionnez **Choisir une région spécifique** pour que ce groupe de bannières ne s'affiche que pour les utilisateurs d'une ou plusieurs régions en particulier.
18. [Facultatif] Définissez **Afficher sur les pages**. Cela correspond aux pages sur lesquelles le groupe de bannières peut afficher pour les visiteurs :
    * [Par défaut] **Afficher sur toutes les pages** du site web.  
      **Remarque** : nous vous conseillons de définir au moins un groupe de bannières contenant toutes les pages, en cas de problème.
    * **Afficher sur des pages spécifiques** : indiquez les éléments que la page ou l'URL doit contenir pour afficher les bannières.
      * Vous pouvez choisir :
        * **Page spécifique** : spécifiez l'hôte et/ou le chemin de la page sur laquelle afficher la bannière. Les requêtes saisies ne seront pas prises en compte. Exemple : http://www.example.com/path?query
        * **Chemin d'URL et requête :** saisissez le chemin d'accès et/ou la requête qui détermine si la bannière s'affiche ou non. Exemple : path?query. **Remarque :** N'entrez pas l'URL en entier, comme http://www.example.com/path?query. Ne saisissez que le chemin et/ou la requête.
      * Vous pouvez ajouter jusqu'à 15 conditions avec et/ou.
      * En cas de conflit entre les conditions, la bannière ne s'affichera pas.
19. Cliquez sur **Créer un groupe de bannières**.
20. [Facultatif] Pour modifier à nouveau le groupe de bannières, survolez **Ciblage et comportement** et cliquez sur **Modifier**.

<div id="example-1" />

> 📄 **Exemple**
>
> Mark est le marketeur d'un service de livraison de courses appelé « Feed Me ». Il décide de créer une campagne pour la vente de prunes dans l'app. Mark décide d'utiliser les SMS, ainsi que des réseaux publicitaires et Google pour la campagne.
>
> Pour préparer la campagne, Mark suit ces étapes :
>
> * Il sélectionne l'utilisation des paramètres d'attribution des liens entrants et des paramètres UTM (ainsi que les paramètres par défaut qui définissent les options de secours pour les clics qui ne proviennent ni d'un lien entrant, ni d'une campagne UTM).
> * Donne au réseau publicitaire un lien d'attribution unique à utiliser dans le cadre de la campagne pour diriger les utilisateurs vers la page de vente des prunes sur le site mobile de Feed Me. Le lien inclut le paramètre URL de redirection (af\_r), avec l'URL de la page de vente des prunes : `http://feedme.com/plums_link`.
> * Il prépare une campagne Google Ads pour les utilisateurs qui visitent les pages du site web mobile contenant « plums\_utm ».
> * Pour les SMS, ajoute des paramètres d'attribution uniques à utiliser dans le lien de la campagne pour diriger les utilisateurs vers la page de vente des prunes sur le site mobile de Feed Me. Le lien inclut le paramètre pid, avec l'URL de la page de vente des prunes : `http://feedme.com/plums_link?pid=sms&c=plums`.
>
> Les campagnes sont lancées.
>
> Les utilisateurs :
>
> * Voient la publicité pour la vente de prunes et cliquent pour arriver sur le site mobile Feed Me.
> * Les clics Google Ads et tous les autres clics arrivent sur la page d'accueil du lien entrant et la bannière intelligente correspondante est activée par page.
> * Voient la bannière intelligente sur le site mobile et cliquent dessus.
> * Arrivent sur l'app Feed Me, la téléchargent et l'installent.
> * Sont dirigés au lancement de l'app vers la vente de prunes.
> * Sont attribués aux sources média qui les ont conduits au site mobile de Feed Me.

<div id="targeting--behavior" />

#### Ciblage et comportement

Le panneau *Targeting et comportement* affiche les paramètres que vous avez définis pour ce groupe de bannières. Pour modifier ces paramètres, cliquez sur l'icône *Modifier*.

</Accordion>

<div id="3-banner-setup" />

<Accordion title="3. Configuration de la bannière">

**Pour créer une bannière dans un groupe de bannières :**

1. Cliquez sur **Créer une bannière** pour ouvrir la page **Modifier les bannières**.
2. Définissez le **nom** de la bannière.
3. Cliquez sur **Concevoir la création** :
   1. <span class="af-ol-a"></span>Cliquez sur **Concevoir la création** pour créer votre bannière.

      Une fenêtre permettant de choisir un template s'ouvre.

      <Image align="center" alt="" src="https://files.readme.io/72baea2c6323742beb17761fdf8dc69048ada303db89855db8a60644ead3ad7f-34734678773649.png" />
   2. Passez la souris sur un **template de création**, puis cliquez sur **Créer** pour accéder à la page de configuration **Démarrer la création**.
   3. Personnalisez tous les éléments de la bannière intelligente. Pour ce faire, sélectionnez les éléments d'après leur nom ou cliquez dessus dans l'image d'aperçu. **Remarque :** Tous les éléments ne sont pas disponibles pour chaque template.
      * Titre
      * Description
      * Étoiles d'évaluation
      * Bouton fermer
      * Appel à l'action
      * Logo de l'app
      * Arrière-plan
      * Position de la bannière
      * Espacement de la bannière (pour ajuster la taille de la bannière)
      * Transparence de l'appareil
      * Pour les images, utilisez l'un des types de fichier suivants : jpeg, jpg, png. **Remarque** : le format webp n'est pas pris en charge.  Les recommandations pour les images sont les suivantes : 

| Type de template | Taille maximale du fichier image | Ratio de l'image | Hauteur de l’image | Largeur de l’image |
| --- | --- | --- | --- | --- |
| Mini | 300 Ko | 3:1 (largeur x hauteur) | 70 px | Ajustée pour s’adapter à l’appareil |
| Standard | 300 Ko | 3:1 (largeur x hauteur) | 70 px | Ajustée pour s’adapter à l’appareil |
| Avancé | 300 Ko | 9:4 (largeur x hauteur) | 110 px | Ajustée pour s’adapter à l’appareil |
| Choix-multiple | 300 Ko | 9:4 (largeur x hauteur) | 110 px | Ajustée pour s’adapter à l’appareil |
| Promotionnel | 300 Ko | 4:5 (largeur x hauteur) | 300 px | Ajustée pour s’adapter à l’appareil |
| Superposition de choix multiples | 300 Ko | 9:4 (largeur x hauteur) | 110 px | Ajustée pour s’adapter à l’appareil |
| Interstitiel | 700 Ko | 9:16 (largeur x hauteur) | Ajustée pour s’adapter à l’appareil | Ajustée pour s’adapter à l’appareil |

   4. Cliquez sur **Corriger** pour revoir la création de la bannière et obtenir un aperçu sur différents appareils. **Remarque** : les bannières peuvent être légèrement différentes dans les campagnes actives par rapport aux aperçus.
   5. Si des modifications sont nécessaires, cliquez sur **Retour à l'éditeur**.
   6. Cliquez sur **Terminé** pour revenir à la page de configuration de la bannière.
4. [Facultatif] Ajoutez des paramètres d'attribution personnalisés. Par exemple, `ad_adset` et `af_ad`. **Remarque** : Les paramètres `pid`, `c` et `channel` ne peuvent pas être ajoutés au niveau de la bannière, car ils appartiennent au niveau du groupe de bannières.
5. Après avoir terminé et enregistré la nouvelle création, le statut de la bannière devient actif. Utilisez le bouton **Statut** pour basculer entre les états **Actif** et **En pause**.
6. Cliquez sur **Tout sauvegarder** pour enregistrer votre travail ou sur **Tout sauvegarder et fermer** pour enregistrer votre travail et fermer la page de configuration de la bannière.

<div id="example-2" />

> 📄 **Exemple**
>
> [Ce document](https://drive.google.com/file/d/1mr6g3uNwlLw6UQ_WgtQZprJMhauw7Xi3/view?usp=sharing) contient des conseils et des astuces, ainsi qu'une liste de contrôle.

</Accordion>

<div id="4-testing" />

<Accordion title="4. Tester">

Une fois que la création est prête,vous pouvez la tester **avant** de la mette en ligne et de l'activer pour vos utilisateurs.

**Pour tester une bannière intelligente :**

**Conditions préalables :** assurez-vous que l'extrait de code de la bannière intelligente est intégré à votre site web.

1. Sur la page **Tester la création**, entrez le lien de la page web où le SDK de la bannière intelligente a été intégré (cf <Anchor target="_blank" href="/marketers/fr/docs/smart-banners-website-code-implementation-for-developers">Bannières intelligentes à l'usage des développeurs</Anchor>).
2. Cliquez sur **Générer**.
3. Copiez le lien généré et envoyez-le à votre appareil de test, ou scannez le QR code avec l'appareil de test. **Le lien ou le QR code doit vous rediriger vers la page web et afficher votre bannière.**
4. Cliquez sur **Modifier la création** pour revenir à la configuration, ou cliquez sur **Terminé** pour enregistrer la création.

</Accordion>

<div id="view-banner-performance" />

## Afficher les performances de la bannière

Vous pouvez consulter et comparer les performances de vos différentes bannières sur la page des performances.

Vous pouvez accéder à une vue rapide des performances de certaines bannières dans leurs cartes individuelles des performances.

Les données sur les performances des bannières comprennent :

* Impressions
* Clics
* d'installations
* Réengagements
* Ré-attributions
* Click through Rate (CTR). Formule : clics/impressions x 100
* Taux de conversion (CVR). Formule : Attributions / Clics x 100

**Remarque** :

* Les données sont basées sur le fuseau horaire UTC.
* Les données sont actualisées <Anchor target="_blank" href="/marketers/fr/docs/about-data-freshness-and-timezone-support#continuous-aka-realtime">en continu.</Anchor>
* Les données s'affichent par bannière et par template OneLink. Cela signifie que si votre bannière et votre template OneLink sont configurés pour plusieurs apps (par exemple, une app Android et une app iOS), les données de performances qui s’affichent concernent plusieurs apps.
* Le CVR peut être plus élevé que prévu, parfois même supérieur à 100 %, car les attributions post vue et post clic sont comptabilisées.

<div id="performance-page" />

<Accordion title="Page des performances">

La page de performance vous permet de visualiser et de comparer les données des performances de toutes vos bannières intelligentes, au cours des 90 derniers jours.

**Pour afficher la page des performances** :

1. Dans le tableau de bord AppsFlyer, rendez-vous dans **Expériences et Deep Linking** > **Web-to-app** > **Bannières intelligentes** > **Performance**.
2. Sélectionnez sur quelle période vous souhaitez accéder aux performances. La période par défaut est fixée aux 7 derniers jours.
3. [Facultatif] **Activez Afficher uniquement les bannières en cours d'activité.** Si cette option est activée, les données des bannières actuellement en pause ou non actives ne s'affichent pas, même si elles étaient actives pendant la période sélectionnée. Les données de performance sur la période sélectionnée s'affichent.

</Accordion>

<div id="performance-cards" />

<Accordion title="Cartes des performances">

Vous pouvez afficher les données de performance des 7 derniers jours pour n’importe quelle bannière.

**Pour afficher les performances de la bannière** :

1. Dans le tableau de bord AppsFlyer, rendez-vous dans **Expériences et Deep Linking** > **Web-to-app** > **Bannières intelligentes** > **Studio**
2. Sélectionnez l'espace de travail du site web et le groupe de bannières pour lequel vous souhaitez afficher les performances.
3. Passez la souris sur l'une des bannières du groupe. Les données de performance sur la semaine écoulée s'affichent.

</Accordion>

<div id="additional-information" />

## Informations supplémentaires

<div id="banner-group-display-logic" />

<Accordion title="Logique d'affichage du groupe de bannières">

AppsFlyer tient compte des éléments suivants pour déterminer quelle bannière intelligente afficher :

* Y a-t-il des règles (comportement d'abandon, plafonnement de la fréquence, emplacements, affichage sur les pages, etc.) définies pour les groupes de bannières ?
* L'utilisateur final respecte-t-il les règles et peut-il voir une bannière ?

Si la réponse aux deux questions est oui, c'est-à-dire s'il y a des règles, et si l'utilisateur peut voir une bannière, AppsFlyer choisit une bannière à afficher comme expliqué dans le tableau qui suit.

| Configuration du groupe de bannières | Quelles bannières s'affichent | Exemple |
| --- | --- | --- |
| Groupe de bannières unique | AppsFlyer répartit uniformément l'affichage de toutes les bannières actives dans tous vos groupes de bannières entre tous les utilisateurs éligibles. | • Exemple 1 : il y a 1 bannière active. Elle s'affiche pour tous les utilisateurs.<br /><br />• Exemple 2 : il y a 2 bannières. 50 % des utilisateurs voient la bannière 1, et 50 % voient la bannière 2.<br /><br />• Exemple 3 : il y a 3 bannières, chaque tiers des utilisateurs éligibles voit une bannière différente.<br /><br />• Exemple 4 : il n'y a aucune bannière active. Rien ne s'affiche. |
| Groupes de bannières multiples avec des règles identiques | AppsFlyer répartit uniformément l'affichage de toutes les bannières actives dans tous vos groupes de bannières entre tous les utilisateurs éligibles. | Il y a 2 groupes de bannières (A et B), chacun avec 3 bannières (6 bannières au total). 1/6 des utilisateurs éligibles voit chaque bannière. |
| Groupes de bannières multiples avec des règles multiples | AppsFlyer répartit uniformément l'affichage de toutes les bannières actives *à partir du groupe de bannières dont les règles décrivent et correspondent le mieux aux utilisateurs*. Si les groupes de bannières sont également spécifiques de différentes manières, les bannières de tous ces groupes de bannières s'affichent. | • Exemple 1 : prenons 2 groupes de bannières : A et B. Le groupe de bannières A est configuré pour être affiché dans le monde entier, et le groupe de bannières B est configuré pour s'afficher au Japon. Le groupe de bannières B étant plus spécifique que le groupe A, seules les bannières de ce groupe s'affichent pour les utilisateurs situés au Japon.  Si le groupe n'a aucune bannière active, rien ne s'affiche.<br /><br />• Exemple 2 : prenons 2 groupes de bannières, A et B. Le groupe de bannières A est configuré pour être affiché dans le monde entier, et le groupe de bannières B est configuré pour s'afficher partout sauf en Ukraine. Le groupe de bannières B étant plus spécifique, seules les bannières de ce groupe s'afficheront pour les utilisateurs du monde entier (en dehors de l'Ukraine).  Si le groupe de bannières B n'a aucune bannière active, rien ne s'affiche. Le groupe de bannières A s'affiche en Ukraine.<br /><br />• Exemple 3 : il y a 2 groupes de bannières, A et B. Le groupe de bannières A est configuré pour être affiché au Japon, et le groupe de bannières B est configuré pour être affiché en avril. Les deux groupes de bannières sont aussi spécifiques l'un que l'autre, mais de différentes manières. Par conséquent, au Japon, en avril, les bannières des deux groupes de bannières s'affichent, car aucun groupe de bannières n'a la priorité sur l'autre. |

</Accordion>

<div id="ab-testing-banner-performance" />

<Accordion title="Test A/B de la performance des bannières">

Vous pourrez comparer les performances des groupes de bannières A et B en accédant au tableau de bord de performances. Pour obtenir plus de données d'attribution, nous vous recommandons d'ajouter `af_adset` , `af_ad` ou tout autre paramètre d'attribution (à l'exception de `pid`, `c` et `channel`) en définissant une valeur unique pour chaque bannière créative ou groupe de bannières. Avec ces paramètres vous pourrez comparer les performances de chaque groupe de bannières en accédant aux données dans les tableaux de bord et rapports AppsFlyer.

</Accordion>

<div id="if-a-smart-banner-is-deleted-from-a-banner-group-will-the-data-associated-with-that-banner-group-also-be-removed" />

## FAQ

<div id="why-does-my-banner-not-display" />

<Accordion title="Pourquoi ma bannière ne s'affiche-t-elle pas ?">

C'est la fréquence maximale définie pour votre groupe de bannières qui est en cause. Le plafonnement des fréquences détermine combien de fois la bannière est montrée à un utilisateur unique. Par exemple, si la limite de fréquence est définie sur trois et qu'un utilisateur visite le site quatre fois, l'utilisateur voit la bannière lors des trois premières visites, mais pas lors de le quatrième et des suivantes. Le plafonnement des fréquences peut être désactivé. Sélectionnez une valeur de plafonnement des fréquences, ou désactivez la fonction.

</Accordion>

<div id="can-i-use-my-own-font-for-my-banner" />

<Accordion title="Puis-je utiliser ma propre police de caractères pour ma bannière ?">

Oui. Vous pouvez définir une police utilisée sur le site web pour votre bannière en suivant les [instructions disponibles sur le hub du développeur.](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#control-smart-banner-font)

* L'implémentation nécessite un développeur web.
* La police s'appliquera à toutes les bannières du site web et à tous les éléments de texte compris dans la bannière.
* La police ne peut pas être visualisée dans l'éditeur créatif.
* Après l'implémentation, [testez votre bannière créative.](/docs/smart-banners-mobile-web-to-app-for-marketers#4-testing)
* Si la police ne s'affiche pas correctement, réenregistrez votre bannière dans [l'éditeur créatif.](/docs/smart-banners-mobile-web-to-app-for-marketers#3-banner-setup)

</Accordion>

<div id="can-i-add-parameters-to-the-url-of-my-smart-banners" />

<Accordion title="Est-il possible d'ajouter des paramètres à l'URL de mes bannières intelligentes ?">

<Anchor target="_blank" href="/marketers/fr/docs/smart-banners-website-code-implementation-for-developers#showbanner">showBanner</Anchor>

<Anchor target="_blank" href="/marketers/fr/docs/smart-banners-website-code-implementation-for-developers#updateparams">updateParams</Anchor>

</Accordion>

<div id="do-smart-banners-support-deep-linking" />

<Accordion title="Les bannières intelligentes prennent-elles en charge le deep linking ?">

Oui. Il suffit d'y ajouter le <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">paramètre deep\_link\_value</Anchor> à l'aide de l'une des méthodes suivantes :

* Dans l'interface utilisateur d'AppsFlyer, ajoutez un paramètre d'attribution statique personnalisé pendant la [configuration de la bannière.](/docs/smart-banners-mobile-web-to-app-for-marketers#3-banner-setup)
* Utilisez additionalParams dans la fonction <Anchor target="_blank" href="/marketers/fr/docs/smart-banners-website-code-implementation-for-developers#showbanner">showBanner</Anchor> pour ajouter le paramètre à l'URL avant l'affichage de la bannière.
* Utilisez la fonction <Anchor target="_blank" href="/marketers/fr/docs/smart-banners-website-code-implementation-for-developers#updateparams">updateParams</Anchor> pour ajouter le paramètre à l'URL après l'affichage de la bannière.

Veillez à ce que votre développeur implémente le comportement souhaité pour la valeur deep\_link\_value.

</Accordion>

<div id="can-smart-banners-show-different-content-based-on-whether-or-not-users-have-the-app-installed" />

<Accordion title="Les bannières intelligentes peuvent-elles afficher un contenu différent pour les utilisateurs qui ont installé l'app et ceux qui ne l'ont pas installée ?">

Non. Si vous ne savez pas si les utilisateurs ont l'application ou non, nous vous recommandons de rendre cette action applicable aux deux. Par exemple : « Aller à l'application » ou « Ouvrir l'app ».

</Accordion>

<div id="do-original-incoming-url-parameters-remain-available-for-the-smart-banner-url-when-users-navigate-away-from-and-then-return-to-the-banners-landing-page" />

<Accordion title="Les paramètres originaux de l'URL entrante s'appliquent-ils toujours à l'URL de la bannière intelligente lorsque les utilisateurs quittent la page d'accueil de la bannière puis y reviennent ?">

Oui. Si l'URL entrante d'origine contient un paramètre utm\_source ou pid, elle est enregistrée pendant la durée de la session de navigation et les paramètres sont appliqués à l'URL de la bannière sortante.

</Accordion>

<div id="can-i-set-my-banners-to-display-on-my-mobile-site-but-not-on-my-wrapperhybrid-app" />

<Accordion title="Puis-je configurer mes bannières pour qu'elles s'affichent sur mon site mobile, mais pas dans mon app d'encapsulation/hybride ?">

Oui. Pour ce faire, lorsque vous implémentez des bannières intelligentes dans une app d'encapsulation/hybride et que vous chargez la page de bannière à partir de l'app (et non à partir d'un navigateur web), n'utilisez pas la fonction <Anchor target="_blank" href="/marketers/fr/docs/smart-banners-website-code-implementation-for-developers#showbanner">showBanner</Anchor>, car celle-ci affiche la bannière dans l'app. Vous pouvez utiliser la fonction <Anchor target="_blank" href="/marketers/fr/docs/smart-banners-website-code-implementation-for-developers#hidebanner">hideBanner.</Anchor>

</Accordion>

<div id="do-smart-banners-support-web-accessibility" />

<Accordion title="Les bannières intelligentes sont-elles compatibles avec l'accessibilité du Web ?">

Nous nous engageons à faire en sorte que tous vos utilisateurs, y compris les personnes en situation de handicap, puissent accéder aux bannières intelligentes et les utiliser.

C'est pourquoi nous nous efforçons de rendre nos bannières intelligentes compatibles avec l'accessibilité Web et de suivre les bonnes pratiques relatives à la norme WCAG 2.1 en fournissant les attributs HTML pertinents dans les éléments des bannières intelligentes.

Toutefois, il est de votre seule responsabilité de déterminer les exigences d'accessibilité pertinentes pour l'utilisation que vous comptez faire de ces bannières intelligentes. Il vous incombe de veiller à ce que les bannières intelligentes que vous utilisez restent accessibles à tous les utilisateurs, conformément aux exigences d'accessibilité Web.

Veuillez noter que diverses modifications apportées aux bannières intelligentes peuvent avoir un impact sur leur compatibilité avec les exigences d'accessibilité pertinentes, y compris, par exemple, en cas de modification des couleurs et de la taille des éléments internes de la bannière.

</Accordion>

<div id="troubleshooting--traits-and-limitations" />

## Particularités et limites

| Particularité | Remarques |
| --- | --- |
| Tablettes | • Les bannières intelligentes sont conçues pour les appareils mobile et leurs résolutions peuvent ne pas être optimisées pour les tablettes dotées d'un grand écran. • Les navigateurs sur tablettes ne sont pas toujours reconnus comme des appareils mobile. |
| Paramètres personnalisés | • Les caractères spéciaux suivants ne sont pas autorisés dans les paramètres personnalisés : ;, *, !, @, #, ?, $, ^, :, &, ~, \`, =, +, ', >, &lt;, / - Si vous définissez un paramètre en utilisant l'un de ces caractères spéciaux, le paramètre n'est pas enregistré. |
| Répartition de l'affichage de la bannière | AppsFlyer répartit l'affichage des bannières actives aux utilisateurs de façon uniforme. Il n'est pas possible de choisir d'afficher plus ou moins certaines bannières. Par exemple, s'il y a 2 bannières dans un groupe, elles s'affichent chacune pour 50 % des utilisateurs. Vous ne pouvez pas définir une répartition 70%-30%. |
| Page spécifique | Lorsque vous configurez votre groupe de bannières pour afficher des bannières sur une page spécifique, la règle de bannière s'applique uniquement à l'hôte/au chemin d'accès que vous saisissez. S'il n'y a pas de correspondance parfaite (par exemple, si la page de votre site comporte des chaînes supplémentaires non incluses dans la configuration de la règle), la règle ne s'applique pas. |
| Changement de nom | Les noms des bannières et des groupes de bannières peuvent être modifiés. Ceci n'impacte aucunement les données de performances qui restent inchangées. |

* [Korean\_compressed\_OneLink\_Smart\_Banner\_cheat\_sheet.pdf](https://support.appsflyer.com/hc/fr/article_attachments/17854820505489)

  (3 Mo)

> 📄 **À consulter également**
>
> * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2">Bannières intelligentes pour les développeurs dans le DevHub.</Anchor>
> * <Anchor target="_blank" href="/marketers/fr/docs/pba-web-sdk-integration-guide#installation-and-integration">Intégration de la PBA avec les Bannières intelligentes</Anchor>

<div data-zendesk-anchors="h_01HB5W700P3GP7JS4PFDF65EWT=remarque h_01HB5W700PWY5G45BYNWPKAC52=smart-banners h_01HB5W700QQMYSEFBBXVJ97M0M=exemple h_01HB5W700QGWTWDXBNB2GAPQ3B=important- setup=configuration h_01HB5W700QVNYJT48VAP9Y7HQS=configuration h_01HB5W700Q7G5E98V0DBN9P5VZ=1-website-workplace-setup prepare-your-mobile-site-to-display-smart-banners-for-the-first-time=pr%C3%A9parez-votre-site-mobile-%C3%A0-afficher-des-banni%C3%A8res-intelligentes-pour-la-premi%C3%A8re-fois h_01HB5W700QE7MDBSN5GH4E7ABR=pr%C3%A9parez-votre-site-mobile-%C3%A0-afficher-des-banni%C3%A8res-intelligentes-pour-la-premi%C3%A8re-fois to-create-website-workplaces-after-the-first-time=pour-cr%C3%A9er-des-pages-web-ensuite h_01HB5W700Q57WXKFSWXNF22QZ1=pour-cr%C3%A9er-des-pages-web-ensuite h_01HB5W700QY1FH2SYX6DM4HDEQ=2-banner-group-setup h_01HDH1BQSXCQV9QCJGZ4VNXGPQ=important h_01HB5W700QYJ9NR5F4VT59NG2Q=exemple-1 targeting-behavior=ciblage-et-comportement h_01HB5W700QYC48YTJY9B8JT0XM=ciblage-et-comportement h_01HB5W700QG54YYQFHGA2J41RY=3-banner-setup h_01HB5W700QD0WKNAP5X6T9E6DQ=exemple-2 h_01HB5W700QX5J59BBK1AV7VFV6=4-testing view-banner-performance=afficher-les-performances-de-la-banni%C3%A8re h_01HB5W700Q6WHMVFNSVM2E9JXN=afficher-les-performances-de-la-banni%C3%A8re h_01HB5W700QEP46WV78KEYD1RT1=performance-page h_01HB5W700QZ705H5EE0PFHB1KY=performance-cards additional-information=informations-suppl%C3%A9mentaires h_01HB5W700Q9XD8MGEK0B3ZZJS3=informations-suppl%C3%A9mentaires h_01HB5W700QHW078W3RRCB81AWM=banner-group-display-logic h_01HB5W700QNYT482FR0FRHP2DC=ab-testing-banner-performance h_01HB5W700Q90F1KMASF94EZWEM=faq h_01HB5W700Q1ZP3RAR94T41SXK2=why-does-my-banner-not-display h_01HB5W700QKBVFQHH9D8WD36R2=can-i-use-my-own-font-for-my-banner h_01HB5W700R2AJC2C1PRT5PTH8G=can-i-add-parameters-to-the-url-of-my-smart-banners h_01HB5W700RAVG10QZDBPXWT14G=do-smart-banners-support-deep-linking h_01HB5W700R12DSA6HF4HVWGW9P=can-smart-banners-show-different-content-based-on-whether-or-not-users-have-the-app-installed h_01HB5W700RT122T2M6NXFPSXDV=do-original-incoming-url-parameters-remain-available-for-the-smart-banner-url-when-users-navigate-away-from-and-then-return-to-the-banners-landing-page h_01HB5W700RH40FGHWVJ9J31R9F=can-i-set-my-banners-to-display-on-my-mobile-site-but-not-on-my-wrapperhybrid-app h_01HB5W700R11SHAKV5W21MXCX8=do-smart-banners-support-web-accessibility traits-and-limitations=particularit%C3%A9s-et-limites h_01HB5W700RXHC22QGXDX4GG1AR=particularit%C3%A9s-et-limites h_01HE7SG3MJ4WTPMTXF0DA0M07D=%C3%A0-consulter-%C3%A9galement" />
