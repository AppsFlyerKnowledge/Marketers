---
title: Gestion des utilisateurs
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2021-10-17T11:54:49Z'
  edited_at: '2024-11-13T11:25:21Z'
  id: 4409128270481
  locale: fr
  section: Account management
  section_id: 6551191075473
  url: https://support.appsflyer.com/hc/fr/articles/4409128270481
---
> **En bref :** Créez et gérez les utilisateurs AppsFlyer de votre compte, et attribuez-leur des autorisations d’accès aux fonctionnalités, aux applications et aux données.

## Aperçu

Les comptes AppsFlyer permettent d'avoir plusieurs utilisateurs, chacun ayant des autorisations gérées individuellement. Le nombre maximum d'utilisateurs par compte est déterminé par votre forfait.

Les autorisations de chaque utilisateur sont définies en fonction de trois dimensions principales :

* **Rôle** (capacités d'accès aux fonctionnalités et d'exécution des fonctions)
* **Accès aux apps** pour les apps actuelles et futures
* **Accès aux données** par source média et zone géographique
  * Attention ! Certains tableaux de bord et fonctionnalités d'AppsFlyer ne sont pas disponibles pour les utilisateurs ayant un accès limité aux données (aux sources média et aux zones géographiques). Ces tableaux de bord et fonctionnalités [sont listés ici](#dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access).

Les autorisations au sein de chacune de ces dimensions sont attribuées de manière indépendante. En d'autres termes, vous pouvez attribuer à un utilisateur **un rôle** avec des capacités fonctionnelles étendues, mais lui permettre d'exercer ces capacités uniquement dans un cadre étroitement défini d'applications **, de sources média et de zones géo.** La seule exception est le rôle d'admin, comme indiqué ci-dessous, qui a accès à toutes les capacités, applications, sources média et zones géo.

Les administrateurs peuvent [Ajouter des utilisateurs à plusieurs comptes](#multiple-accounts) Ils peuvent donc facilement passer d’un compte à l’autre.

## Page de gestion des utilisateurs

**Pour accéder à la page de gestion des utilisateurs :**

* Dans la barre supérieure, ouvrez le menu du compte (liste déroulante de l’adresse e-mail) > **Gestion des utilisateurs**.

[![user-management-page.jpg](https://files.readme.io/0ca6dd472b6f50bfde693bba9c131ce9454dc1df90e3a0fb029e2e05b2330db4-31780969019665.jpg)](https://files.readme.io/0ca6dd472b6f50bfde693bba9c131ce9454dc1df90e3a0fb029e2e05b2330db4-31780969019665.jpg)

<div id="users-tab" />

<Accordion title="Onglet Utilisateurs">

L'onglet **Utilisateurs** affiche un tableau de tous les utilisateurs existants dans votre compte. C'est le point de départ de la création, de la gestion et de la suppression des utilisateurs.

Conseils pour naviguer dans l'onglet Utilisateurs :

* Cliquez sur le titre de colonne **Utilisateurs** pour trier le tableau par ordre alphabétique (croissant/décroissant).
* Utilisez le champ de recherche pour trouver et afficher des utilisateurs spécifiques.
* Cliquez sur l'icône de filtre <Image alt="filter_icon.png" src="https://files.readme.io/1ceaac3efead3a218909988be1d50a2f0af93b07360f7197cd398b11d661992b-16162502598417.png" width="25px" /> dans l'en-tête de la colonne **Rôle** pour filtrer les utilisateurs par rôle (y compris les rôles temporaires).
  * Pour supprimer le filtre, sélectionnez **Aucun** dans la liste déroulante du filtre.
* Cliquez sur le titre de colonne **Dernière connexion** pour trier les utilisateurs en fonction de la date de leur dernière connexion à AppsFlyer.
  * **Conseil :** Utilisez cette fonction pour identifier et [supprimer](#deleting-users) Utilisateurs inactifs, protégez votre compte contre les connexions non autorisées.
* Utilisez les cases à cocher pour sélectionner et [modifier plusieurs utilisateurs](#modification-par-groupes) en même temps.
* Administrateurs uniquement : Cliquez sur l’icône de téléchargement <Image alt="download_icon.png" src="https://files.readme.io/fba5d56ceb7f6b3dc3191e5ec33c85ccbba0f7dc409ad0390de238c12b479b61-31780969029777.png" width="24px" /> dans le coin supérieur droit de la page pour télécharger la table utilisateur complète sous forme de fichier CSV.
  * Le fichier téléchargé comprend les mêmes colonnes que le tableau de l'onglet **Utilisateurs**.

</Accordion>

<div id="roles-tab" />

<Accordion title="Onglet Rôles">

L'onglet **Rôles** affiche une liste de tous les rôles définis dans votre compte, notamment :

* [Rôles prédéfinis](#rôles-prédéfinis)
* [Rôles personnalisés](#gérer-les-rôles-personnalisés) que vous avez créés
* Tous les [Rôles temporaires](#rôles-temporaires) en cours pour les utilisateurs

À côté de chaque rôle, vous pouvez voir le nombre d'utilisateurs actuellement affectés à ce rôle.

Cliquez sur le nom d'un rôle dans le panneau de gauche pour afficher les détails complets des capacités du rôle.

</Accordion>

Découvrez ci-dessous les actions disponibles pour gérer efficacement vos utilisateurs et leurs rôles.

## Gérer les utilisateurs

Les administrateurs peuvent créer de nouveaux utilisateurs, les ajouter à plusieurs comptes, modifier leurs informations telles que leurs rôles et leur accès aux applications et aux données, et supprimer des utilisateurs. Certaines de ces actions peuvent être réalisées [en masse à l’aide d’une API dédiée](#gérez-les-utilisateurs-en-masse-via-lapi).

<div id="creating-users" />

<Accordion title="Créer des utilisateurs">

La page de création ou de modification d’un utilisateur comprend un certain nombre de sections. Assurez-vous de les remplir, comme décrit ci-dessous. Lorsque vous avez terminé d’apporter les modifications nécessaires, cliquez sur **Sauvegarder** en bas à droite de la page.

#### Détails de l’utilisateur

1. Sur le **Utilisateurs** , cliquez sur **Nouvel utilisateur**.
2. Saisissez le nom de l'utilisateur (obligatoire) :
   * Il peut s'agir de lettres, de chiffres, d'espaces, de points (.), de traits d'union (-), de caractères de soulignement (\_) et de guillemets simples (') ou doubles (").
   * Les caractères spéciaux ne sont pas autorisés.
3. Saisissez l'e-mail de l'utilisateur (obligatoire) :
   * Peut inclure des lettres, des chiffres, des apostrophes ('), des esperluettes (&), des signes du dollar ($), des hashtags (#), des traits d'union (-), des traits de soulignement (\_) et des points (.).
   * Deux points à la suite (..) ou tout autre caractère spécial ne sont pas autorisés.
   * Doit se terminer par un domaine e-mail valide.

   > 🚧 **Attention !**
   >
   > L'e-mail d'un utilisateur est ce qui permet de l'identifier sur la plateforme AppsFlyer :
   >
   > * Il sera impossible de le modifier ultérieurement : vous devrez supprimer et recréer l'utilisateur.
   > * L'adresse e-mail de l'utilisateur doit être valide.
   > * Il ne peut pas être associé à un autre utilisateur d'un compte AppsFlyer, [sauf si c'est un utilisateur d'un compte bêta](#multiple-accounts). Si l'e-mail est déjà utilisé (dans votre compte ou dans un autre), le message suivant s'affiche : *Impossible de créer cet utilisateur.* Suivez les [étapes de dépannage ci-dessous](/docs/user-management#troubleshooting-can-t-create-this-user) pour résoudre le problème.

4. [Facultatif] Sélectionnez le service de l’utilisateur.

#### Role

Sélectionnez le rôle de l'utilisateur (obligatoire) - soit un rôle prédéfini, soit un rôle personnalisé que vous avez déjà créé.

#### Accès à l'app

Sélectionnez les applications auxquelles l’utilisateur peut accéder :

* Le paramètre par défaut permet d'accéder à toutes les apps actuelles et futures du compte. Pour modifier ce paramètre, utilisez les cases à cocher pour sélectionner et désélectionner les applications.
* Un utilisateur ne peut avoir accès à toutes les applications futures que s'il a accès à toutes les applications actuelles.

#### Accès aux données

Définissez les niveaux d’accès des utilisateurs pour les sources multimédias et les zones géographiques. Décidez d’accorder l’accès à tous les utilisateurs ou de sélectionner l’accès à des éléments spécifiques.

> 📘 **Remarque**
>
> Les utilisateurs ayant un accès limité à la source multimédia ou aux géos ne peuvent pas accéder à certains [Tableaux de bord et fonctionnalités](/docs/user-management#dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access).

#### Sources médias

Par défaut, le paramètre **Tout** Permet d’accéder à toutes les sources multimédias du compte. Cela inclut ceux qui seront ajoutés à l’avenir. La sélection de sources multimédias spécifiques n’inclut pas l’accès aux sources multimédias futures.

> 📘 **Remarque**
>
> * Les utilisateurs disposant d’un accès limité à la source multimédia ne peuvent pas accéder à certains [Tableaux de bord et fonctionnalités](/docs/user-management#dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access).
> * Les rôles d’administrateur et de sécurité ont un accès illimité à toutes les sources multimédias. Cela ne peut pas être modifié.

**Types de sources multimédias :**

Deux types de sources multimédias sont affichés dans la liste :

* Sources média propres Réseaux publicitaires, réseaux publicitaires autodéclarés (SRN) et agences
* Source média personnalisée Sources multimédias prédéfinies. Il peut s’agir de liens de médias propriétaires, de liens de source unique, de liens OneLink et de liens créés par l’annonceur en dehors d’AppsFlyer.

**Spécifications pour la liste des sources de médias :**

* Présente les sources multimédias avec le trafic des 6 derniers mois, triées par celles avec le trafic le plus récent
* Les organismes sont regroupés séparément au bas de la liste
* Contient un maximum de 10 000 sources multimédias :
  * Jusqu’à 5 000 réseaux publicitaires, SRN et sources multimédias personnalisées
  * Jusqu’à 5 000 agences
* Est mis à jour une fois par jour. Les sources multimédias nouvellement ajoutées ne sont visibles dans la liste qu’un jour après l’entrée du trafic dans le système.
* Les sources médiatiques sans trafic depuis plus de 5 ans sont retirées de la liste.

**Pour modifier le paramètre par défaut :**

1. Sous **Sources médiatiques**cliquer **Tout**.
2. Dans la liste déroulante, sélectionnez les sources multimédias spécifiques auxquelles accorder l’accès à l’utilisateur.

Une fois ces paramètres enregistrés, les tableaux de bord utilisateur affichent uniquement les données des sources multimédias sélectionnées.

#### Géos

Indiquez si les utilisateurs ont accès aux données pour **Tout** Geos ou Geos spécifiques uniquement. Le réglage par défaut permet d'accéder à toutes les zones géo. L’accès limité signifie que les utilisateurs ne peuvent pas accéder à certains [Tableaux de bord et fonctionnalités](/docs/user-management#dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access).

**Pour modifier le paramètre par défaut :**

1. Sous **Géos**cliquer **Tout**.
2. Dans la liste déroulante, sélectionnez les zones géo auxquelles l'utilisateur peut accéder.

#### Activer l'utilisateur

Une fois l’utilisateur créé, vous pouvez le voir dans la table des utilisateurs avec une icône d’enveloppe ![pending_invitation_icon.png](https://files.readme.io/68ac08ab6e52191a592350f82996f7ade9d181773d0bdbc6e2cb60315b60a8f2-16162502609553.png). Elle indique qu'une invitation a été envoyée et que le compte est en attente d'activation. L'utilisateur doit activer son compte en utilisant le lien figurant dans l'e-mail. Le lien d'activation est valable pendant 48 heures. Une fois que l'utilisateur a activé son compte, l'enveloppe disparaît.

> 📘 **Remarque**
>
> Si l'utilisateur ne reçoit pas l'invitation ou si le lien expire, vous pouvez [renvoyer l'invitation](/docs/user-management#resending-a-user-invitation).

</Accordion>

<div id="multiple-accounts" />

<Accordion title="Ajouter des utilisateurs à plusieurs comptes">

Les utilisateurs peuvent être ajoutés à plusieurs comptes et se voir attribuer des rôles différents dans chaque compte. Cela permet aux utilisateurs de travailler avec différents comptes sans avoir à ressaisir leurs identifiants.

#### Connectez-vous à plusieurs comptes

Les utilisateurs peuvent se connecter à plusieurs comptes en utilisant toutes les méthodes de connexion: les identifiants (nom d’utilisateur et mot de passe), <Anchor target="_blank" href="/marketers/fr/docs/implementing-and-using-2fa-login">2FAet</Anchor> <Anchor target="_blank" href="/marketers/fr/docs/set-up-sso-authentication-with-your-identity-provider-idp">SSO</Anchor>.

#### Comptes et utilisateurs pris en charge

Les comptes annonceurs permettent d’avoir le même utilisateur dans plusieurs comptes. Avec les bonnes autorisations, ils peuvent ajouter des utilisateurs à tous leurs comptes. (1) Voir les restrictions ci-dessous

#### Limitations relatives à l’ajout d’utilisateurs à plusieurs comptes

* Cette fonctionnalité n’est disponible que pour les comptes d’annonceurs et uniquement pour les utilisateurs disposant des autorisations de gestion des utilisateurs appropriées.
* Un utilisateur peut avoir le rôle d’un [Propriétaire du compte](#propriétaire-de-compte) pour un seul compte. Dans d’autres comptes, ils peuvent occuper n’importe quel autre rôle.
* Les utilisateurs qui n'ont pas encore [activé leur compte](#activer-lutilisateur) ne peuvent pas être ajoutés à un autre compte.

#### Ajouter des utilisateurs à plusieurs comptes

**Pour ajouter le même utilisateur dans plusieurs comptes :**

1. Connectez-vous au compte dans lequel vous souhaitez ajouter l’utilisateur.
2. Dans la barre de menu, cliquez sur le **menu déroulant pour accéder à l'adresse e-mail**. > **Gestion des utilisateurs**.
3. Dans l'onglet **Utilisateurs**, cliquez sur **Nouvel utilisateur**.
4. Saisissez les informations requises, sélectionnez le rôle de l'utilisateur dans ce compte et cliquez sur **Enregistrer**.
5. Répétez les étapes 1 à 4 pour ajouter les utilisateurs à d'autres comptes.

</Accordion>

<div id="editing-users" />

<Accordion title="Modifier les utilisateurs">

Les utilisateurs peuvent être modifiés un par un, ou par groupes.

#### Modification individuelle

**Pour modifier un seul utilisateur :**

1. Dans l’onglet **Utilisateurs**, cliquez sur le bouton **Actions** <Image alt="actions_icon.png" src="https://files.readme.io/24ad987d1e77d9dfa8559a370733a7b62a6d86954ec1d552eac9c406445ed927-16162502616593.png" width="25px" /> tout à droite de la ligne de l'utilisateur.
2. Sélectionnez **Modifier** dans le menu.
3. Modifiez les paramètres de l'utilisateur.
4. Tous les paramètres autres que l'e-mail sont modifiables (y compris le rôle, les applications, les sources média et les zones géo).
5. Cliquez sur **Enregistrer**.

#### Modification par groupes

La modification par groupes est idéale pour modifier les autorisations de compte de plusieurs utilisateurs en même temps. Cette fonction associée au filtrage dans l'onglet **Utilisateurs** peut s'avérer particulièrement utile pour la gestion d'un grand nombre d'utilisateurs.

> 📘 **Remarque**
>
> Vous ne pouvez pas attribuer d’utilisateurs au rôle d’administrateur à l’aide de la modification multi-utilisateur.

**Pour modifier plusieurs utilisateurs :**

1. Dans l'onglet **Utilisateurs**, cochez l'utilisateur ou les utilisateurs que vous souhaitez modifier.
   * Cochez la case du titre de colonne pour sélectionner tous les utilisateurs visibles.
   * Le nombre d'utilisateurs sélectionnés s'affiche à droite de la boîte de recherche. Notez que le [propriétaire du compte](#propriétaire-de-compte) ne peut pas être sélectionné, il n'est donc pas inclus dans le nombre d'utilisateurs sélectionnés.
2. Une série de boutons s’affiche en haut à droite du tableau : **Rôle, Applications, Sources multimédias,** et **Geos.**
   * Si un ou plusieurs des utilisateurs sélectionnés ont accès aux applications futures, le bouton **Apps** n'est pas disponible (voir [Limitations du rôle temporaire](/docs/user-management#limitations-du-rôle-temporaire) ci-dessous).
3. Cliquez sur le bouton correspondant aux autorisations que vous souhaitez modifier.
4. Effectuez les modifications nécessaires à l'aide de la boîte de dialogue ou des listes déroulantes qui s'affichent.
   * N'oubliez pas que vos modifications s'appliquent à tous les utilisateurs sélectionnés !
5. Les utilisateurs modifiés s’affichent surlignés dans le tableau, et tels qu'ils seront une fois les modifications enregistrées. Cependant, vous aurez toujours la possibilité de revoir vos modifications et de les confirmer ou les annuler à l'étape suivante.
6. Vérifiez vos modifications. Cliquez sur **Sauvegarder** ou sur **Annuler**.

> 📄 **Exemple**
>
> **Scénario :**
>
> * Votre compte inclut 30 utilisateurs. Dix d'entre eux occupent la fonction **Marketing - limitée**.
> * Alice, Bill et Charlie viennent d'être promus et vous souhaitez les faire passer du rôle **Marketing - limité** au rôle **Marketing**.
> * Alice travaillera avec l'application Astounding. Bill travaillera avec l'application Beautiful. Charlie travaillera avec l'application Charming.
>
> **Étapes :**
>
> 1. Utiliser le filtre Rôle <Image alt="filter_icon.png" src="https://files.readme.io/1ceaac3efead3a218909988be1d50a2f0af93b07360f7197cd398b11d661992b-16162502598417.png" width="25px" /> pour ne voir que les utilisateurs dans le **Marketing–limité** rôle.
> 2. Faites passer Alice, Bill et Charlie au rôle **Marketing** :
>    * Cochez les cases pour Alice, Bill et Charlie.
>    * Cliquez sur le bouton **Rôle**.
>    * Sélectionnez **Marketing** dans la liste déroulante.
>    * Cliquez sur **Enregistrer** pour confirmer.
>    * Notez qu'une fois les modifications confirmées, le filtre **Rôle** est supprimé et le tableau affiche tous les utilisateurs.
> 3. Donnez à Alice, Bill et Charlie l'accès à l'app appropriée :
>    * Utilisez la boîte de recherche pour trouver Alice, puis modifiez individuellement son utilisateur pour lui donner accès à l'app Astounding.
>    * Répétez ces étapes pour Bill et Charlie afin de leur donner accès à Beautiful et Charming, respectivement.

</Accordion>

<div id="deleting-users" />

<Accordion title="Supprimer des utilisateurs">

Plusieurs utilisateurs peuvent être supprimés du compte de manière groupée. 

> 📘 **Remarque**
>
> * Le [Propriétaire du compte](/docs/user-management#propriétaire-de-compte) ne peut pas être supprimé
> * La suppression d’utilisateurs est irréversible

<span id="to-delete-users"></span>**Pour supprimer des utilisateurs :**

1. Sur le **Utilisateurs** , cochez les cases des utilisateurs que vous souhaitez supprimer. Vous pouvez uSe la recherche et les filtres pour aider à trouver les utilisateurs.
2. Après avoir sélectionné des utilisateurs, cliquez sur l’icône **Supprimer** qui apparaît maintenant en haut à droite du tableau.
3. La fenêtre de confirmation répertorie les utilisateurs à supprimer. Cliquer **Oui, supprimer** pour confirmer la suppression.

</Accordion>

### Gérez les utilisateurs en masse via l’API

Certaines actions de gestion des utilisateurs peuvent être effectuées en masse à l’aide de <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/create-bulk-users-overview">une API dédiée</Anchor>:

* [Créer](https://dev.appsflyer.com/hc/reference/bulk-users-post) plusieurs utilisateurs
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/bulk-users-delete">Supprimer</Anchor> plusieurs utilisateurs
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/bulk-users-get">Avoir</Anchor> Accéder aux détails de plusieurs utilisateurs

L’API prend en charge les principales fonctionnalités de gestion des utilisateurs sur la plateforme et inclut les mêmes vérifications d’erreurs.

## Gérer les rôles

Un rôle doit être attribué à chaque utilisateur de votre compte AppsFlyer. Chaque rôle définit les fonctionnalités AppsFlyer auxquelles l'utilisateur peut accéder et les fonctions qu'il peut exécuter. La liste complète des capacités accordées à chaque rôle est disponible dans l'onglet [Rôles](#roles-tab) de la page **Gestion des utilisateurs**.

Les rôles dans AppsFlyer peuvent être [des rôles prédéfinis](#rôles-prédéfinis), [des rôles personnalisés](#rôles-personnalisés), ou (dans certains cadres) [des rôles temporaires](#rôles-temporaires).

### Rôles prédéfinis

AppsFlyer propose de nombreux rôles prédéfinis :

* [Admin - un rôle particulier](#admin)
* Responsable d'équipe
* Responsable marketing
* Marketing
* Marketing - limité
* Contributeur
* Comptabilité
* Sécurité
* Assurance qualité

> 📘 **Remarque**
>
> Pour chacun de ces rôles prédéfinis, les capacités fonctionnelles sont configurées de manière fixe : aucun mélange ni matching autorisés. Toutefois, vous pouvez modifier les capacités fonctionnelles d'un utilisateur à tout moment en lui attribuant un autre rôle prédéfini ou personnalisé (à l'exception du [propriétaire du compte](#propriétaire-de-compte)), comme indiqué ci-dessous.

> 📄 **Exemple**
>
> Vous avez confié à Bill Bates le rôle de **responsable d'équipe.** Ce rôle permet à Bill de gérer les **templates OneLink,** mais ne lui donne pas accès aux pages **Mon forfait** ni **Paiements**.
>
> **Question :** Question : puis-je maintenir Bill dans le rôle de responsable d'équipe tout en lui donnant la possibilité d'accéder aux pages Mon forfait et Paiements ? Puis-je lui bloquer pour lui la gestion des templates OneLink ?
>
> **Réponse :** Tant que Bill conserve le rôle de responsable d'équipe, vous ne pouvez pas lui donner la possibilité d'accéder aux pages Mon forfait et Paiements. Vous ne pouvez pas non plus l'empêcher de gérer les templates OneLink. Bien entendu, vous pouvez attribuer à Bill un autre rôle prédéfini, et ses capacités deviendront celles définies par ce rôle. Vous pouvez également créer un rôle personnalisé pour Bill, qui modifie ses capacités en fonction de vos besoins.

### Admin

Un compte AppsFlyer peut avoir **un ou plusieurs admins**. Ce rôle présente plusieurs caractéristiques uniques :

#### Accès

Le rôle d'admin permet d'accéder à **toutes les fonctionnalités du compte**, notamment :

* Toutes les caractéristiques et fonctions
* Toutes les applications actuelles et futures
* Toutes les sources média et zones géo

Cette caractéristique d'accès illimité du rôle d'admin ne peut être ni modifiée ni limitée.

#### Gérer les tokens

Seul un utilisateur disposant d’un rôle d’administrateur peut <Anchor target="_blank" href="/marketers/fr/docs/managing-appsflyer-tokens">Gérer les tokens</Anchor>: créer, renommer et supprimer les jetons d’API et de serveur à serveur.

#### Duplication des rôles

Le rôle d'admin **ne peut pas être dupliqué** lors de la création de [rôles personnalisés](#gérer-les-rôles-personnalisés).

#### Inviter de nouveaux partenaires dans AppsFlyer

Un utilisateur disposant d’un rôle d’administrateur peut <Anchor target="_blank" href="/marketers/fr/docs/partner-integrations#inviter-de-nouveaux-partenaires-dans-appsflyer">Envoyer un lien d’invitation</Anchor> via le Partner Marketplace pour inviter un partenaire qui n’est pas intégré à AppsFlyer.

### Propriétaire de compte

L'utilisateur créé au moment de l'ouverture du compte (**le propriétaire du compte**) se voit attribuer par défaut le rôle d'admin. Le propriétaire du compte est initialement responsable de la création d'utilisateurs supplémentaires (jusqu'à ce que des utilisateurs supplémentaires disposant de capacités de gestion des utilisateurs soient créés).

Un propriétaire de compte possède des caractéristiques uniques au-delà de celles du rôle d’administrateur qui n’est pas le propriétaire du compte. Le propriétaire du compte ne peut pas être supprimé, retiré du rôle d'admin ou modifié d'une autre manière à partir de la page **[Gestion des utilisateurs](/docs/user-management#page-de-gestion-des-utilisateurs)**. Si vous devez changer de propriétaire du compte, suivez les étapes indiquées ci-dessous.

### Rôles personnalisés

Les rôles prédéfinis dans AppsFlyer ont été configurés avec les combinaisons de capacités requises dans la plupart des situations. Grâce à cette fonctionnalité, de nombreux annonceurs estiment qu'ils n'ont pas besoin de personnaliser davantage les rôles. Toutefois, lorsqu'une personnalisation supplémentaire est nécessaire, les rôles prédéfinis restent un excellent point de départ pour gérer les capacités de vos utilisateurs.

En savoir plus sur [la gestion des rôles personnalisés](#gérer-les-rôles-personnalisés).

### Rôles temporaires

Si votre compte AppsFlyer existait dans notre ancien système de gestion des utilisateurs (lorsque les seuls types de comptes disponibles étaient Admin et Membre d'équipe), tous les utilisateurs ont été envoyés dans le nouveau système avec les mêmes autorisations. Par conséquent, la plupart de ces utilisateurs apparaissent dans le système actuel avec des **rôles temporaire**.

En savoir plus sur la [gestion des rôles temporaires.](#managing-temp-roles)

### Obtenir les données des rôles via l’API

Par le biais de la <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_roles">API d’obtention des rôles</Anchor>, vous pouvez récupérer la liste des rôles actuels et leurs attributs correspondants spécifiques à votre compte.

## Gérer les rôles personnalisés

<div id="creating-custom-roles" />

<Accordion title="Créer des rôles personnalisés">

* **Conditions minimum :** Seulement [Titulaires de compte](#propriétaire-de-compte) ou les utilisateurs avec l’option [Accès au rôle d’administrateurPeut](#admin) créer un rôle personnalisé.

**Pour créer un rôle personnalisé :**

1. Sur le panneau gauche de la **Rôles** , sous la barre de recherche, cliquez sur **+ Nouveau rôle personnalisé**.
2. **Nom du rôle :** Saisissez un nom pour le nouveau rôle que vous créez.
   * **Remarque :** Remarque : Une fois le rôle personnalisé enregistré, son nom ne peut plus être modifié.
   * **Recommandé :** Rendez le nom descriptif et facilement identifiable par la suite.
3. **Modèle de rôle :** Comme point de départ, sélectionnez un rôle prédéfini qui correspond étroitement aux capacités et aux autorisations du nouveau rôle personnalisé.
4. Ajustez les paramètres du modèle de rôle sélectionné en fonction de vos exigences de rôle personnalisé. Les niveaux d'autorisation de toutes les capacités modifiables s'affichent sous forme de boutons. Cliquez sur ces boutons pour modifier les niveaux d'autorisation du nouveau rôle personnalisé. (N'oubliez pas de faire défiler la page pour voir la liste complète des capacités).
   * **Remarque :** Les fonctionnalités qui n’apparaissent pas sous forme de boutons ne sont actuellement pas modifiables.
5. Après avoir défini les autorisations sur toutes les fonctionnalités pertinentes, cliquez sur **Enregistrer le rôle**.  
   Le nouveau rôle personnalisé est affiché dans le panneau de gauche et peut être attribué lors de la création de nouveaux utilisateurs ou la modification d'utilisateurs existants.

</Accordion>

<div id="editing-custom-roles" />

<Accordion title="Modifier les rôles personnalisés">

**Pour modifier un rôle personnalisé :**

1. Dans le panneau gauche de l'onglet **Rôles**, cliquez sur le nom du rôle personnalisé que vous souhaitez modifier.
2. Cliquez sur l’icône **Éditer** icône <Image alt="edit-icon.jpg" src="https://files.readme.io/d32f150cb5d0271c5504fb3c107e23f73e59c9a3be1630769ad309edf4e79ea0-31780971794321.jpg" width="25px" /> dans le coin supérieur droit de la page.

   L'affichage du panneau de droite change, vous permettant de modifier les paramètres de permissions du rôle.

   * **Remarque :** Le nom du rôle ne peut pas être modifié. Pour le modifier, vous devez supprimer le rôle et en recréer un nouveau avec un nom différent.
3. Les niveaux d'autorisation de toutes les capacités modifiables s'affichent sous forme de boutons. Cliquez sur ces boutons pour modifier les niveaux d'autorisation du nouveau rôle personnalisé. (N'oubliez pas de faire défiler la page pour voir la liste complète des capacités).
4. Lorsque vous êtes satisfait de toutes vos sélections, cliquez sur le bouton **Enregistrer le rôle**.
5. Les niveaux d'autorisation du rôle sont modifiés pour tous les utilisateurs nouveaux et existants.

> 🚧 **Important !**
>
> Toute modification apportée à un rôle personnalisé est automatiquement appliquée à **tous les utilisateurs existants** dans ce rôle.

</Accordion>

<div id="deleting-custom-roles" />

<Accordion title="Supprimer des rôles personnalisés">

**Pour supprimer un rôle personnalisé :**

1. Dans le panneau gauche de l'onglet **Rôles**, cliquez sur le nom du rôle personnalisé à supprimer.
2. Cliquez sur l’icône **Supprimer** icône <Image alt="delete-icon.jpg" src="https://files.readme.io/87f206e21926af0836690be064a5af7cb3bce0007f0fc62301b2925701b1d9f9-31780971797265.jpg" width="24px" /> dans le coin supérieur droit de la page.
3. Confirmez la suppression.
   * Un rôle personnalisé peut uniquement être supprimé si aucun utilisateur ne lui est attribué. Si des utilisateurs sont actuellement affectés à un rôle personnalisé, affectez-les à un autre rôle avant de supprimer le rôle personnalisé.

</Accordion>

## Situations particulières et procédures complémentaires

<div id="managing-temp-roles" />

<Accordion title="Gérer les rôles temporaires">

Si votre compte utilisait précédemment notre ancien système de gestion des utilisateurs, [**les rôles temporaires**](/docs/user-management#rôles-temporaires) ont été attribués aux utilisateurs existants afin d'assurer leur transfert dans le nouveau système avec les mêmes capacités.

* Les utilisateurs avec les mêmes capacités se sont vu attribuer le même rôle temporaire.
* Utilisez les fonctionnalités de l'onglet [Rôles](/docs/user-management#roles-tab) pour consulter les capacités de chaque rôle temporaire, ainsi que la liste des utilisateurs avec un rôle temporaire.

#### Limitations du rôle temporaire

Les rôles temporaires ont été créés uniquement pour permettre un passage en douceur depuis notre ancien système de gestion des utilisateurs. Ils ne sont donc disponibles que dans des situations précises :

* Les rôles temporaires ne peuvent pas être attribués à un autre utilisateur (nouveau ou existant).
* Un utilisateur ayant déjà un rôle temporaire ne peut pas se voir attribuer un autre rôle temporaire (bien que vous puissiez modifier les applications, les sources média et les zones géo auxquelles il a accès).
  * Notez que l'accès d'un utilisateur aux futures apps **ne peut pas** être modifié lorsque l'utilisateur a un rôle temporaire.
* Lorsqu'un utilisateur ayant un rôle temporaire passe à un rôle prédéfini, il ne peut pas retrouver le rôle temporaire qui lui avait été attribué précédemment (ni d’ailleurs aucun autre rôle temporaire).
* Si le dernier utilisateur avec un rôle temporaire quitte ce rôle, le rôle n'apparaîtra plus dans votre compte.

> 📄 **Exemple**
>
> Votre compte utilisait auparavant notre système de gestion des utilisateurs. Diana et Edward étaient des utilisateurs au moment où votre compte a été transféré vers le nouveau système. Diana a maintenant le rôle temporaire 1, et Edward le rôle temporaire 2.
>
> * Vous embauchez une nouvelle personne, Fiona. Vous pouvez attribuer à Fiona l'un des [rôles prédéfinis](/docs/user-management#rôles-prédéfinis). Toutefois, vous ne pouvez pas attribuer à Fiona le rôle temporaire 1 ou le rôle temporaire 2.
> * Diana ne peut pas passer du rôle temporaire 1 au rôle temporaire 2. Cependant, vous pouvez lui attribuer n'importe lequel des 4 rôles prédéfinis. Vous pouvez également modifier son accès aux applications, aux sources média et aux zones géo si nécessaire.
> * Si vous attribuez à Diana le rôle Comptabilité, vous ne pourrez pas lui réattribuer ultérieurement le rôle temporaire 1.
> * Si Diana était le dernier utilisateur du rôle temporaire 1 lorsque vous l'avez transférée vers le rôle Comptabilité, le rôle temporaire 1 n'apparaîtra plus dans votre compte.

</Accordion>

<div id="dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access" />

<Accordion title="Accès au tableau de bord et aux fonctionnalités pour les utilisateurs ayant un accès limité à la source média/zone géo">

Les tableaux de bord AppsFlyer suivants sont **ne sont pas accessibles** aux utilisateurs dont l'accès est limité à certaines sources média et zones géo :

* Présentation de SKAN
* Protect360
* Rétention
* People-Based Attribution
* Incrementalité

Les fonctions suivantes d'AppsFlyer sont **non disponibles** pour ces utilisateurs :

* Tableau croisé
* OneLink
* Règles de validation
* Audiences (non disponible pour les utilisateurs limités à une source média ; disponible pour les utilisateurs limités à une zone géo).
* Infos sur le SDK
* Ingestion des dépenses publicitaires
* ETL des coûts

</Accordion>

<div id="changing-the-account-owner" />

<Accordion title="Modifier le propriétaire du compte">

Comme tous les admins disposent de facto des mêmes autorisations que le propriétaire du compte, il n'est généralement pas nécessaire de modifier le propriétaire du compte. Mais si vous devez changer le propriétaire du compte, procédez comme suit.

> 🚧 **Important !**
>
> Le changement de propriétaire du compte doit être effectué manuellement en suivant les étapes ci-dessous. Il n'est pas possible de le faire depuis la page **Gestion des utilisateurs**.

#### #1-Envoyer une demande par e-mail

Pour commencer le processus de changement de propriétaire du compte, envoyez une demande par e-mail à AppsFlyer **à partir de l'e-mail du propriétaire actuel du compte.**

* Assurez-vous qu'il s'agit bien de l'e-mail du propriétaire actuel du compte, telle qu'elle apparaît dans votre compte AppsFlyer.
* Si le propriétaire actuel du compte a quitté votre entreprise, demandez à votre équipe informatique de vous permettre d'envoyer un e-mail à partir de son adresse.

Veuillez inclure les informations suivantes dans votre demande :

| À : | Votre CSM AppsFlyer ou hello@appsflyer.com |
| --- | --- |
| CC : | E-mail du nouveau propriétaire du compte |
| Objet : | Demande de changement de propriétaire du compte pour |
| Corps : | Message court comprenant le nom et le titre du nouveau titulaire du compte |

Utilisez cet exemple d'e-mail comme référence :

![account_owner_change_email.png](https://files.readme.io/eb10736386a7a8cfc274979a3aa933e23288c74d1b26c0f06d72005ceebafe06-31780969048081.png)

#### #2-Étapes suivantes

Une fois la modification effectuée, vous serez notifié par e-mail par AppsFlyer.

* Si vous souhaitez que l'ancien propriétaire du compte continue à utiliser votre compte AppsFlyer, [créez un nouvel utilisateur](/docs/user-management#creating-users) pour lui, et donnez-lui un nouveau rôle.
* Les API qui reposent sur le jeton v2 ne sont pas impactées par le changement de propriétaire d’un compte. <Anchor target="_blank" href="/marketers/fr/docs/managing-appsflyer-tokens">En savoir plus sur la gestion des jetons</Anchor>.

</Accordion>

<div id="troubleshooting-can-t-create-this-user" />

<Accordion title="Dépannage « Impossible de créer cet utilisateur »">

Si vous recevez le message d'erreur *Impossible de créer cet utilisateur* lorsque vous saisissez l'e-mail d'un nouvel utilisateur, c’est généralement que l'e-mail est déjà associé à un utilisateur AppsFlyer (soit dans votre compte, soit dans un autre). Choisissez la procédure suivant votre cas :

Si l'utilisateur fait partie de votre compte :

* Vérifiez si l'utilisateur a bien activé son compte. Si ce n'est pas le cas, vous pouvez lui [renvoyer l'invitation](/docs/user-management#resending-a-user-invitation).
* Si l'utilisateur a bien activé son compte, demandez-lui de se connecter à nouveau en utilisant l'e-mail associé à son utilisateur. Vous pouvez lui recommander de suivre les étapes du **Mot de passe oublié** si besoin est.

Si l'e-mail de l'utilisateur est utilisé dans un autre compte, ou si vous ne pouvez pas trouver le compte dans lequel l'e-mail de l'utilisateur est utilisé, effectuez l'une des opérations suivantes :

* Supprimez l’utilisateur de l'autre compte puis ajoutez-le au vôtre (vous - ou l'utilisateur - devez disposer des autorisations nécessaires dans l'autre compte) ; ou
* Ajoutez l’utilisateur à votre compte en définissant un autre e-mail. L'adresse e-mail doit être valide ; ou
* Contactez votre Responsable Réussite client (CSM), ou envoyez un e-mail à notre équipe Engagement client à [hello@appsflyer.com](mailto:hello@appsflyer.com).

</Accordion>

<div id="resending-a-user-invitation" />

<Accordion title="Renvoyer une invitation d’utilisateur">

Si un nouvel utilisateur n'a pas reçu [l'invitation pour activer](#activer-lutilisateur) son compte, ou s'il n'a pas activé son compte sous 48 heures, vous pouvez lui renvoyer l'e-mail en suivant cette procédure :

1. Dans l’onglet **Utilisateurs**, cliquez sur le bouton **Actions** <Image alt="actions_icon.png" src="https://files.readme.io/24ad987d1e77d9dfa8559a370733a7b62a6d86954ec1d552eac9c406445ed927-16162502616593.png" width="25px" /> tout à droite de la ligne de l'utilisateur.
   * Notez que l'utilisateur porte toujours l’icône en forme d'enveloppe ![pending_invitation_icon.png](https://files.readme.io/68ac08ab6e52191a592350f82996f7ade9d181773d0bdbc6e2cb60315b60a8f2-16162502609553.png), qui indique qu'il n'a toujours pas activé son compte).
2. Sélectionnez **Renvoyer l'e-mail d’invitation** dans le menu.

</Accordion>

<div id="resetting-twofactor-authentication-2fa" />

<Accordion title="Réinitialisation de l’authentification à deux facteurs d’un utilisateur (2FA)">

Si votre compte utilise la 2FA, il pourra vous être demandé de réinitialiser les paramètres 2FA d'un utilisateur. Procédez comme suit :

1. Dans l’onglet **Utilisateurs**, cliquez sur le bouton **Actions** <Image alt="actions_icon.png" src="https://files.readme.io/24ad987d1e77d9dfa8559a370733a7b62a6d86954ec1d552eac9c406445ed927-16162502616593.png" width="25px" /> tout à droite de la ligne de l'utilisateur.
2. Sélectionnez **Réinitialiser la 2FA** dans le menu.

**Remarque :** Un admin peut réinitialiser la 2FA de tout autre admin autre que lui, ou celui du [propriétaire du compte](#propriétaire-de-compte). Pour réinitialiser la 2FA du propriétaire du compte, contactez l'équipe d'assistance AppsFlyer.

</Accordion>

<div data-zendesk-anchors="background=aper%C3%A7u h_01H9Q9007QP8YMPDVZ57N4M1HD=aper%C3%A7u user-management-page=page-de-gestion-des-utilisateurs h_01H9Q9007QW1RD3MTTV01Q8QRE=page-de-gestion-des-utilisateurs h_01J6W88SQ45MA3AZ29K3WMW9PV=users-tab h_01J6W88SQ5B16Q897YMJ7ZNMQX=roles-tab managing-users=g%C3%A9rer-les-utilisateurs h_01H9Q9007QYSJZYZMP0C8NA98G=g%C3%A9rer-les-utilisateurs h_01H9Q9007QH3ME2P8PHC9DJBZV=creating-users user-details=d%C3%A9tails-de-lutilisateur h_01HMP4EYM562HFSP80MQQ82B47=d%C3%A9tails-de-lutilisateur h_01H9Q9007Q6SK4391P8C3A147N=attention- h_01HMP4Q56XP10343YFW17VX00W=role app-access=acc%C3%A8s-%C3%A0-lapp h_01HMP4RDXVRM3Z0WDCJD3P2W8S=acc%C3%A8s-%C3%A0-lapp data-access=acc%C3%A8s-aux-donn%C3%A9es h_01HMP4SW7RMESGDFNP1KFN7641=acc%C3%A8s-aux-donn%C3%A9es h_01HR6VBJHTZM48493B29FCWQT8=remarque media-sources=sources-m%C3%A9dias h_01HRPRS4BHX2AMR9W4FNGE0N1P=sources-m%C3%A9dias 01HRPRSF0F8ENJ9ZAE1ZDTMAMB=remarque-1 geos=g%C3%A9os h_01HRPRVXYFX4P2ZG0H5HPNF2AG=g%C3%A9os user-activation=activer-lutilisateur h_01HFRCWNR8T5J990TV68K6B45T=activer-lutilisateur h_01HFRFRQXD1RD66EBRQH0T7Q78=remarque-2 01HFRF6SENRY51A4ZAQJTMTDA3=multiple-accounts log-in-to-multiple-accounts=connectez-vous-%C3%A0-plusieurs-comptes h_01J2GN6ZA29SFC12HR4ZVBDFDT=connectez-vous-%C3%A0-plusieurs-comptes supported-accounts-and-users=comptes-et-utilisateurs-pris-en-charge h_01H9Z7XXE0CKRSE191ZN017MGE=comptes-et-utilisateurs-pris-en-charge limitations-on-adding-users-to-multiple-accounts=limitations-relatives-%C3%A0-lajout-dutilisateurs-%C3%A0-plusieurs-comptes 01J2GMV7ZYV5G0Q6C18RRY1TY0=limitations-relatives-%C3%A0-lajout-dutilisateurs-%C3%A0-plusieurs-comptes add-users-to-multiple-accounts=ajouter-des-utilisateurs-%C3%A0-plusieurs-comptes h_01H9G1MP3Z7VCQQ8ZSQDGSWPC3=ajouter-des-utilisateurs-%C3%A0-plusieurs-comptes h_01H9Q9007RTMXVRMR4RM6J80CW=editing-users individual-editing=modification-individuelle h_01H9Q9007R3QW4AYRJBTF0X7B9=modification-individuelle multiuser-editing=modification-par-groupes h_01H9Q9007R4JQPKQS2HVB251GH=modification-par-groupes h_01H9Q9007R9M9YDMJ2YYNZDW3D=remarque-3 h_01H9Q9007RAFXB899YK6CADD9R=exemple h_01H9Q9007RF8QKS7YBZ1GRXVCF=deleting-users h_01HGTR4NEBYJZTW4BA5V9JJX5X=remarque-4 h_01HGTK2664A0R2RBJM37EYWNZG=to-delete-users manage-users-in-bulk-via-api=g%C3%A9rez-les-utilisateurs-en-masse-via-lapi h_01HYASD07FG0HGX22FTHEQ9APP=g%C3%A9rez-les-utilisateurs-en-masse-via-lapi more-about-roles=g%C3%A9rer-les-r%C3%B4les h_01H9Q9007Q8CMR2RD6E4KN26YE=g%C3%A9rer-les-r%C3%B4les predefined-roles=r%C3%B4les-pr%C3%A9d%C3%A9finis h_01H9Q9007Q28D43B6JRP71NDQM=r%C3%B4les-pr%C3%A9d%C3%A9finis h_01J6VZ7ANV3JHJZ5EVBF1BY585=remarque-5 h_01H9Q9007QXSGG375PR2SCS7QS=exemple-1 admin%E2%80%94a-special-role=admin h_01H9Q9007Q4A6KETAAGAWEPQQ9=admin access=acc%C3%A8s h_01HF8N2Z8ZP3HV06XJPMQ19DTK=acc%C3%A8s manage-tokens=g%C3%A9rer-les-tokens h_01HV1F5S0FE083B73P8MEYX4FM=g%C3%A9rer-les-tokens role-duplication=duplication-des-r%C3%B4les h_01HF8N6DKWYKMBE35QKKB55KEM=duplication-des-r%C3%B4les invite-new-partners-to-appsflyer=inviter-de-nouveaux-partenaires-dans-appsflyer h_01HVK8EB3SMC09VD8TJND9YWCD=inviter-de-nouveaux-partenaires-dans-appsflyer account-owner=propri%C3%A9taire-de-compte h_01HF8N69VYE3ZJVFW1ENC0XA62=propri%C3%A9taire-de-compte custom-roles=r%C3%B4les-personnalis%C3%A9s h_01H9Q9007QZ7F2TX8B9D1TNYPN=r%C3%B4les-personnalis%C3%A9s temp-roles=r%C3%B4les-temporaires h_01H9Q9007QE8YT1DNRPNTFQWYH=r%C3%B4les-temporaires get-roles-data-via-api=obtenir-les-donn%C3%A9es-des-r%C3%B4les-via-lapi h_01J6VZ2XP6HM6NJ2TB5DJXD6SA=obtenir-les-donn%C3%A9es-des-r%C3%B4les-via-lapi managing-custom-roles=g%C3%A9rer-les-r%C3%B4les-personnalis%C3%A9s h_01H9Q9007RQHHNHZ3M38E88YPW=g%C3%A9rer-les-r%C3%B4les-personnalis%C3%A9s h_01H9Q9007RYZD19CFNSM60EARZ=creating-custom-roles h_01H9Q9007R6E6JGD8BC2WY8G3G=editing-custom-roles h_01H9Q9007RANMZP4T6S8R6WA1B=important- h_01H9Q9007R16190B6RB884FY61=deleting-custom-roles special-situations-and-additional-procedures=situations-particuli%C3%A8res-et-proc%C3%A9dures-compl%C3%A9mentaires h_01H9Q9007RSWFVAZQ5DNVNN7T2=situations-particuli%C3%A8res-et-proc%C3%A9dures-compl%C3%A9mentaires h_01H9Q9007RNZ28128XDB76ZVZC=managing-temp-roles temp-role-limitations=limitations-du-r%C3%B4le-temporaire h_01H9Q9007RJ0CQRGEYNEQJ2QR5=limitations-du-r%C3%B4le-temporaire h_01H9Q9007RHBYD2B6PHQRD7TWV=exemple-2 h_01H9Q9007RRY6QERXQ0C4FSYCN=dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access h_01H9Q9007R221KXA7DFTXJY0PE=changing-the-account-owner h_01H9Q9007RR4M8V599A19B2M0F=important--1 1%E2%80%93send-an-email-request=1-envoyer-une-demande-par-e-mail h_01H9Q9007RSA5406WXCB1E4JRK=1-envoyer-une-demande-par-e-mail 2%E2%80%93next-steps=2-%C3%A9tapes-suivantes h_01H9Q9007RZ2X9RAY8067SZETF=2-%C3%A9tapes-suivantes troubleshooting-can%E2%80%99t-create-this-user=troubleshooting-can-t-create-this-user h_01H9Q9007RR4VYEPGT90MEHV3T=troubleshooting-can-t-create-this-user h_01H9Q9007R11BQWQZC66X5FV0N=resending-a-user-invitation h_01H9Q9007R72FAH89XW58MWCXT=resetting-twofactor-authentication-2fa" />
