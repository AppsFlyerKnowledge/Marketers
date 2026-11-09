---
title: Guide des audiences
metadata:
  keywords:
    - Audiences
    - Advertisers
    - Premium
    - Premium Feature
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2017-05-30T07:21:22Z'
  edited_at: '2024-06-10T08:17:28Z'
  id: 115002689186
  locale: fr
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/fr/articles/115002689186
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En bref :** Augmentez l'efficacité de vos campagnes d'acquisition d'utilisateurs et de remarketing en utilisant AppsFlyer Audiences pour construire et connecter des segments d'audience à vos réseaux de partenaires.

<Image align="center" alt="Intro_image.png" src="https://files.readme.io/645503f41e6a76c854c62236fc279be591849879790d02001eafc75f0d1a974a-30258966500753.png" />

<div id="audiences-basics" />

## Les bases de l'audience

Avec AppsFlyer Audiences vous créez rapidement des segments d’audience que vous connectez à vos canaux propriétaires et payants, ainsi, vous diffusez des campagnes sur mesure qui améliorent l’engagement et les performances. De plus, une fois la campagne lancée, vous pouvez suivre les résultats de performance dans Audiences.

Une audience est un segment des utilisateurs actuels ou précédents de votre application répondant à certains critères de votre choix. Les audiences peuvent se baser sur les caractéristiques personnelles, le comportement, l'activité in-app, la source d'attribution, le revenu généré, l'emplacement géo, le type d'appareil, etc.

**Étape 1 - Créer votre audience dans AppsFlyer :** Vous pouvez créer une audience personnalisée de A à Z, en importer une, ou bien choisir parmi notre suggestion d’audiences prêtes à l’emploi 100% personnalisables, elles suivent les meilleures pratiques du secteur et vous feront gagner un temps précieux.

**Étape 2 - Connecter l’audience :** Une fois votre audience établie, il reste à la connecter à vos partenaires média depuis AppsFlyer, qui transmet les identifiants des membres de l’audience aux partenaires afin de créer l'audience dans leurs systèmes. Ceci permet au partenaire de diffuser des publicités destinées exclusivement à ces utilisateurs. Les audiences sont automatiquement mises à jour et envoyées aux partenaires une fois par jour. De plus, vous pouvez importer votre audience vers les services tiers de type compartiment Amazon S3, ou la télécharger sous la forme d'un fichier CSV directement depuis le tableau de bord.

Toutes les informations permettant d'importer les données d'une audience vers un partenaire média sont contenues dans la connexion du partenaire. Vous pouvez avoir plusieurs connexions pour un même partenaire média (en utilisant différents comptes, informations de connexion, etc.).

> 📘 **Remarque concernant la confidentialité**
>
> Afin de garantir la conformité avec les règles de confidentialité d'iOS 14.5 et de protéger la vie privée des utilisateurs, Audiences vous laisse l'entière liberté de définir quels identifiants sont partagés avec les partenaires, que ce soit au niveau du compte ou pour chacune des connexions du partenaire.

<div id="audience-split-and-incrementality-testing" />

### Partage d'audience et test d'incrémentalité

Le test d'incrémentalité mesure l'impact réel de vos campagnes grâce à des tests A/B qui mesurent avec précision l’écart incrémentiel, c'est-à-dire la différence entre les conversions qui ont eu lieu suite à vos campagnes marketing et celles qui auraient eu lieu de toutes manières. AppsFlyer Audiences prépare les tests grâce à une fonctionnalité optionnelle qui répartit l'audience entre les partenaires média sélectionnés et un groupe de contrôle. Vous pouvez ainsi utiliser le tableau de bord d'incrémentalité pour savoir ce que vous rapporte vraiment vos campagnes.

<div id="get-started" />

## Démarrer

Suivez ces étapes pour démarrer avec Audiences :

|  | Étapes |
| --- | --- |
| 1 | Dans AppsFlyer, dans le menu latéral, sélectionnez **Engager** > **Audiences** |
| 2 | Définissez la <Anchor target="_blank" href="/marketers/fr/docs/audiences-user-identifier-policy">politique</Anchor> au niveau du compte pour le partage d'identifiants utilisateurs avec les partenaires |
| 3 | Créer une nouvelle audience :<ul><li>[Audience personnalisée](/docs/audiences-guide#create-a-custom-audience) - Créez votre audience de A à Z</li><li>[Suggestions d'audiences](/docs/audiences-guide#create-a-suggested-audience) - Des audiences clefs en mains et personnalisables, qui répondent aux meilleures pratiques du secteur.</li><li><Anchor target="_blank" href="/marketers/fr/docs/audiences-import-audience-segments-from-internal-systems">Importer l'audience</Anchor> - Importez des segments d'audience à partir de vos systèmes internes (de type BI ou CRM).</li></ul> |
| 4 | Connecter l'audience à un ou plusieurs partenaires média |
| Optionnel | [Partagez l'audience entre les partenaires et un groupe de contrôle](/docs/audiences-guide#audience-split-and-control-groups) |
| Optionnel | <Anchor target="_blank" href="/marketers/fr/docs/audiences-create-better-audiences-with-user-attribute-data">Importer les attributs d'utilisateur</Anchor> |

<div id="notes" />

<div id="create-and-manage-audiences" />

## Créer et gérer les audiences

Cette section aborde la création et la gestion des audiences et la mise en place des tests d'incrémentalité.

<div id="create-a-custom-audience" />

<Accordion title="Créer une audience personnalisée">

Une audience personnalisée se fabrique de A à Z, elle utilise les ensembles de règles et filtres que vous souhaitez.

**Pour créer une audience personnalisée :**

1. Dans AppsFlyer, dans le menu latéral, sélectionnez **Engager** > **Audiences**.
2. Cliquez sur **Nouvelle audience**.
3. Sélectionnez **Audience personnalisée**.  
   L'onglet **Créer** s'affiche.
4. Saisissez un **nom d'audience** unique.*
5. Sélectionnez la plateforme : **Android** ou **iOS**.
6. Sélectionnez [l'identifiant utilisateur](/docs/audiences-guide#user-identifier-device-id-vs-customer-id) :
7. [Par défaut] **ID de l’appareil** : Évalue les règles par ID d’appareil uniquement.
8. **ID de client** : Évalue les règles en regroupant les appareils selon le CUID (méthode à utiliser uniquement après avoir vérifié que vos données ont des CUID valides).
9. Sélectionnez **Nouvel ensemble de règles**, ou si vous souhaitez ajouter les utilisateurs d'une audience existante, cliquez sur **Audience existante** puis sélectionnez l'audience spécifique dans la liste.
10. Créez l'audience guidée par l'interface utilisateur. Pour plus d'informations sur les différentes règles, vous pouvez consulter [Tout savoir sur les ensembles de règles](/docs/audiences-guide#tout-savoir-sur-les-ensembles-de-règles).
11. Combinez des ensembles de règles en utilisant les opérateurs et, ou, exclure.
12. Lorsque vous créez votre audience, les volets de droite mettent automatiquement à jour les estimations d'audience ainsi que la taille des importations pour chaque partenaire.
13. Terminez le paramétrage de l'audience, puis cliquez sur **Suivant.**  
    La **fenêtre de connexion de l'audience** s'ouvre. C'est là que vous pouvez connecter l'audience à vos partenaires média/strong>.

**Remarques :**

* Vous pouvez avoir jusqu’à 100 audiences personnalisées/suggérées actives à la fois.
* *Les noms des audiences peuvent être visibles sur les sites de vos partenaires média connectés. Veillez à ne pas inclure d'informations confidentielles.

</Accordion>

<div id="create-a-suggested-audience" />

<Accordion title="Créer une audience avec la fonctionnalité Suggestions d'audiences">

Suggestions d'audiences vous permet d'explorer et de découvrir **des segments d'audience prêts à l'emploi, basés sur les meilleures pratiques du secteur.** Vous pouvez sélectionner une audience, la personnaliser et la relier à vos réseaux de partenaires pour des campagnes de marketing parfaitement ciblées.

Choisissez parmi plus de 30 audiences dans les catégories **acquisition, activation, engagement, monétisation et audiences spécifiques à un secteur d'activité.** Les audiences sont 100 % personnalisables, ce qui vous permet de créer l'audience précise dont vous avez besoin. La fonctionnalité Audiences inclut :

* Convertir les clics publicitaires en installations
* Le clonage des audiences
* Des listes de suppression
* Encourager l'inscription
* Encourager l’achat
* Monétiser les acheteurs
* Et bien plus encore...

<div id="example-use-case" />

<div id="notes-1" />

> 📄 **Exemple d'utilisation**
>
> Cet exemple aborde un cas précis. Supposons que vous souhaitiez inciter les utilisateurs actifs de votre app qui n'ont pas encore acheté, à effectuer leur premier achat. Vous pouvez sélectionner l'audience « Encourager l'achat », puis la personnaliser pour préciser quel événement définit un achat in-app. Vous pouvez ensuite connecter l'audience à vos partenaires et lancer une campagne promotionnelle qui mènera l'utilisateur sur la page d'achat de l'app pour l'inciter à acheter.
>
> <Image align="center" alt="Encourage_purchase_image_this_one.jpeg" src="https://files.readme.io/8b49590a0c97707bd4a0b151d30cc48183e15ffb13d2d4e9ee25d522de71846c-30259018203153.jpg" />

**Pour créer une audience suggérée :**

1. Dans AppsFlyer, dans le menu latéral, sélectionnez **Engager** > **Audiences**.
2. Cliquez sur **Nouvelle audience**.
3. Sélectionner **Audience suggérée**.
4. Sélectionnez l'app.
5. Parcourez les différentes catégories et sélectionnez une audience qui correspond à vos objectifs.  Remarque : Certaines audiences nécessitent que vous ajoutiez des <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview">événements in-app</Anchor> précis pour définir les critères de l’audience. Si l’événement <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-event-structure#noms-dévénements-prédéfinis">prédéfini</Anchor> AppsFlyer  a déjà été configuré dans votre application, il sera présélectionné. Dans le cas contraire, vous devrez sélectionner l’événement personnalisé dans le menu déroulant.

   <Image align="center" alt="Select_an_event__1_.jpeg" src="https://files.readme.io/b5055ca61791f15efc3a91f3f2d749e1df9e3f5e8b956b9167e186474de57ac4-30258966520721.jpg" width="419px" />
6. Cliquez sur **Sélectionner et personnaliser**.
7. Sélectionnez [l'identifiant utilisateur](/docs/audiences-guide#user-identifier-device-id-vs-customer-id) :
   * [Par défaut] **ID de l’appareil** : Évalue les règles par ID d’appareil uniquement.
   * **ID de client** : Évalue les règles en regroupant les appareils selon le CUID (méthode à utiliser uniquement après avoir vérifié que vos données ont des CUID valides).
8. Si vous souhaitez personnaliser plus avant l'audience en ajoutant des [ensembles de règles](/docs/audiences-guide#tout-savoir-sur-les-ensembles-de-règles), cliquez sur **+ Filtre**. Une fois terminé, cliquez sur [Suivant](/docs/audiences-guide#tout-savoir-sur-les-ensembles-de-règles).   
   La **fenêtre de connexion de l'audience** s'ouvre. C'est là que vous pouvez connecter l'audience à vos partenaires média/strong>.

**Remarque :** Vous pouvez avoir jusqu’à 100 audiences personnalisées/suggérées actives à la fois.

</Accordion>

<div id="import-an-audience" />

<Accordion title="Importer une audience">

Vous pouvez <Anchor target="_blank" href="/marketers/fr/docs/audiences-import-audience-segments-from-internal-systems">importer un segment d'audience prédéfini</Anchor> à partir de vos systèmes internes (tels que BI et CRM) vers AppsFlyer Audiences, et l'utiliser comme point central pour connecter et traiter tous vos segments d'audience avec vos partenaires publicitaires. Cela vous permet également de profiter des fonctionnalités d'Audiences, telles que la correspondance des identifiants/l'enrichissement des données et les mesures de campagnes connectées.

</Accordion>

<div id="connect-an-audience-to-media-partners" />

<Accordion title="Connecter une audience à des partenaires média">

Une fois que vous avez défini votre audience, l'étape suivante consiste à la connecter avec vos partenaires média.

**Pour connecter votre audience avec des partenaires média :**

1. Après avoir défini votre nouvelle audience sur la page **Créer**, cliquez sur **Suivant**. La **fenêtre de connexion de l'audience** s'ouvre.
2. Cliquez sur **+ Connexion partenaire**, puis effectuez l'une des opérations suivantes :
   * **Pour ajouter une nouvelle connexion**, cliquez sur **+ Ajouter une connexion partenaire** (voir la section [Créer une nouvelle connexion](/docs/audiences-guide#create-a-new-connection) ci-dessous pour des instructions détaillées).
   * **Pour choisir parmi des connexions existantes :**
     1. Recherchez la connexion du partenaire.
     2. Sélectionnez une ou plusieurs connexions existantes.
     3. Cliquez sur **Enregistrer**.  
        La fenêtre de connexion de l'audience s'ouvre.
     4. [Facultatif] [Partager une audience entre des partenaires et un groupe de contrôle.](/docs/audiences-guide#audience-split-and-control-groups)
     5. [Facultatif] [Copier le partage des groupes dans S3](/docs/audiences-guide#audience-split-and-control-groups).
3. Cliquez sur **Enregistrer**.  
   Une fois connectée, l'audience est mise à jour et envoyée quotidiennement aux partenaires.

</Accordion>

<div id="user-identifier-device-id-vs-customer-id" />

<Accordion title="Identifiant utilisateur : ID de périphérique et ID de client">

L’évaluation des règles d’audience est effectuée à l’aide d’un identifiant d’utilisateur de l’application. Choisissez parmi :

* [Par défaut] **ID d’appareil :** La conformité de l’ensemble de règles est évaluée à l’aide de l’ID d’appareil (GAID ou IDFA/IDFV). S'il est conforme à l'ensemble de règles, l'ID d'appareil est ajouté à la liste d'audience. **Remarque :** L'ID d'appareil sera partagé avec les partenaires uniquement si votre politique d'identifiant utilisateur l'autorise.
* **<Anchor target="_blank" href="/marketers/fr/docs/customer-user-id-field-cuid"><span id="cite_ref-1"></span>ID de client (CUID)</Anchor> :**
  * La conformité de l'ensemble de règles est évaluée en regroupant tous les ID d'appareil qui sont associés au même CUID. Si le groupe est conforme à l'ensemble de règles, les ID d'appareil contenus dans le groupe sont alors ajoutés à l'audience. **Remarque** : Le CUID en lui-même ne fait pas partie de la liste d'audience et n'est pas envoyé aux partenaires média.
  * Recommandations concernant l'implémentation du CUID :
    * Assurez-vous que vos données sont remplies avec des CUID valides.
    * Les utilisateurs d’applications (appareils) sans CUID sont ignorés.
    * Lorsqu'un ID d'appareil est associé à un CUID, les données historiques de l’audience pour l'utilisateur sont mises à jour d'une manière rétroactive, puis incorporées aux créations d'audience suivantes. **Remarque** : Aucune modification n’est apportée aux données brutes.
    * Si un ID d'appareil est associé à deux CUID différents, c'est le CUID associé le plus récent qui est utilisé.
    * Lors de la création d’une audience avec CUID comme identifiant, l’appairage du CUID doit avoir été réceptionné par AppsFlyer lors de l’installation (et pas seulement lors des événements post-installation), ceci afin de garantir une association complète avec les appareils concernés, et un enrichissement réussi avec les ID d’appareil (soit GAID et IDFA). <Anchor target="_blank" href="/marketers/fr/docs/customer-user-id-field-cuid#paramétrer-le-cuid">En savoir plus</Anchor>

<Image align="center" alt="CuidExaplainded_us-en.jpg" src="https://files.readme.io/d40309ab2fd34a4862b9c089ac2fade2f5642973fc4d4977da66f1ee6bf1e390-30258966523921.jpg" width="387px" />

<div id="pause" />

<div id="h_01K0PAQ4SFXBK0TZ3MH07PWN4A" />

<div id="example-device-id-vs-cuid" />

> 📄 **Exemple : ID d’appareil et CUID**
>
> Une audience d'utilisateurs qui ont dépensé plus de 5 $
>
>
>
> | Publicitaire  <br />ID | CUID | Achat en $ |
> | --- | --- | --- |
> | A | 99 | 1 |
> | A | 99 | 2 |
> | B | 77 | 1 |
> | B | 77 | 5 |
> | C | 99 | 3 |
> | D | Aucun | 50 |
>
>
>
>
> | Règle évaluée par | ID d'appareil inclus dans l'audience | Explication |
> | --- | --- | --- |
> | Identifiant d'appareil | B, D | A et C ne sont pas inclus : la dépense était inférieure à 5 $ |
> | CUID | A, B, C | * A et C ont le même CUID (99) : la dépense cumulée est de 6 $.<br />* D est ignoré : il n’y a pas de CUID |

</Accordion>

<div id="audience-split-and-control-groups" />

<Accordion title="Groupes de contrôle et partage d'audience">

Activez l'option qui divise l'audience entre les partenaires et un groupe de contrôle pour préparer rapidement les tests A/B et la <Anchor target="_blank" href="/marketers/fr/docs/incrementality-for-remarketing-overview">mesure de l'incrémentalité</Anchor>, vous obtiendrez ainsi des informations précieuses sur les effets de la campagne. Lorsqu'elle est activée, cette fonction répartit aléatoirement l'audience entre les partenaires sélectionnés et un groupe de contrôle. Le groupe de contrôle est la partie de l'audience qui n’est pas transmise aux partenaires. Elle est la condition sine qua non à la mesure de l'incrémentalité. Vous pouvez ajuster les pourcentages de répartition comme vous le souhaitez, et désactiver ou réactiver la répartition par audience.

| Fonctionnalité | Description |
| --- | --- |
| Répartir l'audience | <ul><li>Cette fonctionnalité permet de répartir aléatoirement l'audience entre les partenaires sélectionnés et un groupe de contrôle. **Elle est activée par défaut pour les abonnés à l'incrémentalité** et peut être désactivée ou réactivée à tout moment.</li><li>Les divisions d’audiences sont utilisées pour diverses raisons, comme les tests A/B et la mesure de l'incrémentalité.</li><li>**Remarque : La modification d'une division entre partenaires existante entraîne la redistribution de l'ensemble de l'audience. Cela peut mettre en doute la validité des tests A/B et entraîner la fin des expériences d'incrémentalité actives, qui redémarreront alors en tant que nouvelles expériences.**</li></ul> |
| Groupe de contrôle | Une partie de l'audience est conservée dans un groupe de contrôle, qui n'est donc envoyé à aucun partenaire :<ul><li>Les groupes de contrôle sont utilisés dans les tests A/B, et pour mesurer l'incrémentalité de vos campagnes de marketing.</li><li>Pour obtenir un groupe de contrôle efficace, il est recommandé de représenter 15 % de l'audience (minimum).</li><li>Le pourcentage de groupe de contrôle minimum pour mener correctement une expérience d'incrémentalité est de 1 %.</li></ul> |
| Envoyer une copie des listes de fractionnement à un compartiment S3 | Les fichiers CSV contenant les listes d'audience fractionnées ainsi que le groupe de contrôle peuvent être envoyés dans un compartiment Amazon S3.<ul><li>**Remarque** : Cela ne veut pas dire que le S3 Amazon est défini en tant que partenaire connecté.</li><li>Les listes d'audience peuvent être téléchargées dans un fichier CSV. Le fichier CSV peut être par exemple envoyé aux partenaires qui ne sont pas intégrés à AppsFlyer.</li></ul> |

**Pour diviser l'audience et effectuer d'autres actions de partenaire :**

1. À gauche dans le panneau AppsFlyer, allez dans **Engager** > **Audiences**.
2. Dans l'onglet **Audiences**, sélectionnez l'audience.
3. Rendez-vous dans l'onglet **Connecter**.  

   <Image align="center" alt="audience_split_1200px.png" src="https://support.appsflyer.com/hc/article_attachments/360018673137" />

   Les paramètres en cours s'affichent :  
   * Le volet en haut à droite donne une estimation de l'audience totale, ainsi que la taille des importations (pour l’ensemble des partenaires).
   * En bas à droite, vous pouvez voir :
     * Une estimation de la taille de l’importation pour chaque partenaire
     * Le chevauchement de partenaires (pour les audiences non fractionnées)
4. Effectuez l'une des actions suivantes :

<Table>
  <thead>
    <tr>
      <th>
        Action
      </th>
      <th>
        Marche à suivre
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="split-an-audience-between-partners-and-control-group"></span>
        Diviser une audience entre des partenaires et un groupe de contrôle
      </td>
      <td>
        1. Assurez-vous que l'option **Diviser l'audience/Mesurer l’écart incrémentiel**est activée.
           * Le cumul du groupe de contrôle et de la fraction aux partenaires doit représenter 100 %.
           * Si vous ne souhaitez pas inclure le groupe de contrôle dans la répartition : indiquez 0 %.
           * Tous les partenaires connectés doivent avoir une part dans la répartition (n'attribuez pas 0 % à un partenaire).
           * Pour afficher le total alloué : faites défiler l’écran pour afficher le pourcentage total de la répartition.
        2. Saisissez le pourcentage alloué pour :
           * **Le groupe de contrôle -** 15 % ou plus recommandé.
           * Entrez un pourcentage à répartir par connexion.
           * Faites défiler pour afficher l'allocation totale en pourcentage, et vérifiez que l'allocation totale est bien de 100%.
           * Cliquez sur **Enregistrer la répartition**.
           * Cliquez sur **Enregistrer**.
      </td>
    </tr>
    <tr>
      <td><span id="copy-split-groups-to-s3"></span>
        Copier les groupes fractionnés dans S3
      </td>
      <td>
        **Pour envoyer une copie de la liste des répartitions de l'audience à un compartiment S3 :**

        1. Cliquez sur **Copier les groupes fractionnés dans S3.**
        2. Sélectionnez la connexion.
        3. Cliquez sur **Enregistrer**.

        Les fichiers sont transmis en utilisant la structure de répertoire et les noms de fichier suivants :

        * **Répertoire** :

          ```
           \YYYY-MM-DD\audienceID_audienceName_timestamp\
          ```
        * **Nom de fichier** : nom du partenaire ou du groupe de contrôle  
          Remarque : Si la connexion au partenaire échoue et que le fichier n’est pas importé, le terme **failed** (échec) est ajouté au nom du partenaire (ex.*partnenaire\_nom\_failed.csv*)
      </td>
    </tr>
    <tr>
      <td><span id="create-and-add-a-new-connection"></span>
        Créer et ajouter une nouvelle connexion
      </td>
      <td>
        **Pour créer une nouvelle connexion :**

        1. Cliquez sur **Ajouter** **une connexion** **de partenaire.**
        2. Tapez un nom de connexion.
        3. Sélectionnez un partenaire.
        4. Terminez le processus en suivant les instructions de l'interface utilisateur.
        5. Cliquez sur **Ajouter une connexion de partenaire.**
      </td>
    </tr>
    <tr>
      <td><span id="add-or-remove-an-existing-connection"></span>
        Ajouter ou supprimer une connexion existante
      </td>
      <td>
        **Pour supprimer ou ajouter une connexion existante :**

        1. Survolez la connexion du partenaire.
        2. Cliquez sur l'icône « Supprimer ».
        3. Cliquez sur **Enregistrer**.
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="manage-audiences" />

<Accordion title="Gérer les audiences">

**Gérer les audiences depuis le tableau de bord Audiences :**

1. À gauche dans le panneau AppsFlyer, allez dans **Engager** > **Audiences**.
2. Parmi les options proposées vous trouverez :  

| Option | Description |
| --- | --- |
| <span id="create-a-new-audience"></span>Créer une nouvelle audience | Créer une nouvelle audience |
| <span id="change-audience-settings"></span>Modifier les paramètres de l'audience | Cliquez sur un **nom d'audience** et procédez de l'une des manières suivantes :<ul><li>Dans l’onglet **Créer** : Afficher et modifier les ensembles de règles.</li><li>Dans l’onglet **Connecter** : Définissez les options de répartition de l’audience et du groupe de contrôle.</li></ul> |
| <span id="actions"></span>Actions | Dans le menu de l’icône <Image alt="3_dots_icon.png" src="https://support.appsflyer.com/hc/article_attachments/8796592031889" width="7px" /> qui apparaît à droite lorsque vous survolez une audience sur la page principale Audiences :<ul><li>**Afficher historique :** Affiche l'historique de l’importation de l'audience, y compris la taille de l'audience et la répartition entre les partenaires.</li><li>**Importer maintenant :** Envoie l’audience à des partenaires connectés.</li><li>**Télécharger en CSV** :<ul><li>Génère et importe la liste d'audiences dans un (ou plusieurs) fichier CSV qui contient les identifiants que vous avez sélectionnés. Seules les données conformes à votre <Anchor target="_blank" href="/marketers/fr/docs/audiences-user-identifier-policy">politique d'identifiant utilisateur</Anchor> seront téléchargées.</li><li>Un fichier est généré pour chaque partenaire.</li><li>Le (ou les) fichier se télécharge après calcul de l'audience, ce qui peut prendre un certain temps après que la création ou modification de l'audience.</li><li>Les fichiers téléchargés sont limités à 5 millions d'enregistrements. Pour les fichiers plus volumineux, envoyez le fichier dans un <Anchor target="_blank" href="/marketers/fr/docs/audiences-partner-connections#amazon-s3">compartiment S3</Anchor>, ou passez par un <Anchor target="_blank" href="/marketers/fr/docs/audiences-partner-connections#sftp">SFTP</Anchor>.</li><li>Seule une audience connectée à des réseaux de partenaires sera mise à jour quotidiennement. Si l'audience n'est pas connectée à des réseaux partenaires, elle ne sera pas maintenue à jour au-delà de sa date de création. Si vous souhaitez télécharger les informations les plus récentes, vous pouvez dupliquer l'audience pour la recréer (voir ci-dessous), puis télécharger le fichier CSV de l'audience dupliquée.</li></ul></li><li>**Dupliquer** :<ul><li>Copie les critères de l'audience.</li><li>Lorsque vous dupliquez une audience, donnez-lui un nom qui n'est utilisé nulle part ailleurs.</li><li>[Option] Supprimer un ou plusieurs des partenaires connectés durant la duplication.</li></ul></li><li>**Calculer maintenant**: [pour les audiences importées] Recalcule le nombre d'utilisateurs dans une audience. Permet d'actualiser la taille d'une audience si elle vous semble incorrecte.</li><li>**Supprimer :** Supprime définitivement l’audience.</li></ul> |
| <span id="bulk-actions"></span>Actions groupées | Effectuer la même action sur plusieurs audiences. Pour utiliser les actions groupées, sélectionnez deux audiences minimum, puis sélectionnez l'une des actions groupées suivantes :<ul><li>**Importer maintenant**</li><li>**Afficher le chevauchement d'audience**: affiche le chevauchement entre les audiences sélectionnées</li><li>**Supprimer**</li></ul> |

</Accordion>

<div id="all-about-rulesets" />

## Tout savoir sur les ensembles de règles

Apprenez à utiliser les ensembles de règles pour définir vos audiences.

<div id="audience-segmentation-rulesets" />

<Accordion title="Ensembles de règles pour la segmentation d'audience">

<Image align="center" alt="audience_segmentation_rulesets.jpg" src="https://support.appsflyer.com/hc/article_attachments/8862762173201" />

* Un ensemble de règles de segment d'audience est constitué d'une ou de plusieurs règles qui permettent un filtrage très précis.
* Combinez les ensembles de règles à l’aide des opérateurs : et, ou, exclure.
* Au fur et à mesure que les règles sont définies et superposées, la taille estimée de l'audience s'affiche en temps réel.
* Les ensembles de règles peuvent être dupliqués en cliquant sur l’icône <Image alt="duplicate_icon.png" src="https://support.appsflyer.com/hc/article_attachments/21386046257297" width="17px" /> .
* Lorsqu'une audience se compose de plusieurs ensembles de règles, utilisez l'affichage du chevauchement pour mieux comprendre vos segments d'audience.
* L'[identifiant utilisateur](/docs/audiences-guide#user-identifier-device-id-vs-customer-id) qui sert à évaluer les règles est soit l'ID d'appareil (par défaut) soit l'ID d'utilisateur client (CUID).

Les exemples qui suivent illustrent la mise en œuvre d'un ensemble de règles dans des cas différents.

</Accordion>

<div id="ruleset-examples" />

<Accordion title="Exemples d’ensembles de règles">

<div id="example-location-based-rule" />

> 📄 **Exemple : Règle basée sur la localisation**
>
> Utilisateurs de New York qui ont désinstallé l’app au cours du dernier mois
>
> <Image align="center" alt="example_location_based_rule.jpg" src="https://support.appsflyer.com/hc/article_attachments/8862756141713" />

<div id="example-user-attributes-based-rule" />

> 📄 **Exemple : Règle basée sur les attributs d’utilisateur**
>
> Utilisateurs ayant lancé l'app au moins une fois au cours des 7 derniers jours, et dont l'arme préférée est l'épée.
>
> <Image align="center" alt="example_user_attributes_based_rule.jpg" src="https://support.appsflyer.com/hc/article_attachments/8862801164433" />

<div id="example-revenue" />

> 📄 **Exemple : Revenus**
>
> Les utilisateurs qui ont installé l’application au cours des sept derniers jours et qui ont dépensé 1 $
>
> <Image align="center" alt="example_revenue.jpg" src="https://support.appsflyer.com/hc/article_attachments/8862765137041" />

<div id="example-remarketing" />

<div id="example-owned-media-filter" />

> 📄 **Exemple : Filtre de média propriétaire**
>
> Créez des audiences ciblées composées d'utilisateurs qui ont été attribués à des sources média spécifiques, comme les réseaux sociaux (hors publicité payée), SMS, e-mails, référents, le web ou les codes QR. Vous pouvez également choisir votre degrés de précision et cibler les utilisateurs qui proviennent d'une source média, d'une campagne, d'un ensemble de publicités ou d'une publicité individuelle en particulier.
>
> Voici un exemple avec des utilisateurs qui ont lancé l'app au moins une fois au cours des sept derniers jours, et dont l'installation a été attribuée à une certaine campagne d’e-mail, ainsi qu'à des ensembles de publicités et publicités spécifiques.
>
> <Image align="center" alt="Owned_media_example.jpg" src="https://support.appsflyer.com/hc/article_attachments/8862802677777" />
>
> L'audience peut être utilisée pour réengager ces utilisateurs avec des messages personnalisés (que ce soit sur les médias propriétaires ou payés), ou comme liste d'exclusion pour éviter qu'ils ne voient des publicités inutiles lors des campagnes.

> 📄 **Exemple : Remarketing**
>
> Utilisation des clics et des vues pour un remarketing efficace. Pour convertir ces utilisateurs, il faut les convaincre un peu plus, ou leur envoyer un rappel. Ces utilisateurs ont une forte probabilité de se convertir, de sorte que le remarketing peut donner sur eux de bien meilleurs résultats que dans le cas d’une publicité tournée vers de nouveaux segments. Créez des audiences affinées pour le remarketing en fonction des clics et des impressions recueillis.
>
> Créez une audience d'utilisateurs potentiels qui ont cliqué sur une publicité mais qui n'ont pas effectué d'installation au cours des deux derniers jours.
>
> <Image align="center" alt="example_remarketing.jpg" src="https://support.appsflyer.com/hc/article_attachments/8862801851409" />
>
> Il s'agit d'utilisateurs qui étaient récemment suffisamment intéressés par votre app mobile pour cliquer sur votre publicité, mais qui, pour différentes raisons, n'ont pas installé l'app (ou l'ont installée mais sans la lancer). Certains utilisateurs ont simplement besoin d'un rappel (push) pour l'installer. D'autres ont besoin de voir plus d’images ou de fonctionnalités de votre app pour passer le cap. Par conséquent, si vous avez une création principale que vous utilisez sur les nouvelles audiences, il peut être bon d'utiliser une création différente pour les audiences qui ont cliqué mais n'ont pas installé.

</Accordion>

<div id="ruleset-filters" />

<Accordion title="Filtres d'ensemble de règles">

* Un ensemble de règles est constitué d'une ou de plusieurs règles.
* Il existe plusieurs catégories de filtres telles que les événements, le revenu, la géo, l'attribution, les attributs d’utilisateurs, les appareils et les médias propriétaires.
* Les règles ont différents paramètres et réglages, comme l’indique le tableau ci-dessous.

<table><tbody><tr><td colspan="3"><h4><span id="h_01K5EH9WVTEX56980MCR81ZAHH"></span><span id="contains-does-not-contain-logic"></span><span id="h_01K5EHGKDPWS16HP9Q7KX9JXFY"></span><span id="events"></span>Événements</h4><p><img alt="engagement_filter_with_A___B.jpg" src="https://support.appsflyer.com/hc/article_attachments/8862867078545"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://support.appsflyer.com/hc/article_attachments/8862869108625"/></p><ul><li>A regardé une publicité</li><li>A cliqué sur une publicité</li><li>A installé l'application</li><li>N'a pas installé l'app</li><li>A lancé l'app</li><li>N'a pas lancé l'app</li><li>A désinstallé l'app </li></ul></td><td colspan="2"><p><img alt="B.jpg" src="https://support.appsflyer.com/hc/article_attachments/8862869246097"/></p><p>Délai et fréquence </p></td></tr><tr><td colspan="3"><h4><span id="inapp-events"></span>Événements in-app</h4><p><img alt="in-app_event_filter.jpg" src="https://support.appsflyer.com/hc/article_attachments/8862873195281"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://support.appsflyer.com/hc/article_attachments/8862869108625"/></p><ul><li>Did event (a effectué l'événement) [<em>event name</em>]</li><li>Did not do event (n'a pas effectué l'événement): [<em>event name]</em> </li></ul></td><td><p><img alt="B.jpg" src="https://support.appsflyer.com/hc/article_attachments/8862869246097"/></p><p>Délai et fréquence </p></td><td><p><img alt="C.jpg" src="https://support.appsflyer.com/hc/article_attachments/8862873752721"/></p><p>Attribut de l'événement + valeur :</p><ul><li>Est égal</li><li>Est plus grand que</li><li>Est plus petit que</li></ul></td></tr><tr><td colspan="3"><p>Remarques sur les événements in-app</p><ul><li>La liste des événements in-app est mise à jour <a href="./about-data-freshness-and-timezone-support#traitement-quotidien" target="_blank">quotidiennement</a>. </li><li>Si <strong>Did event</strong> (a effectué l'événement) est sélectionné et que l'événement in-app a des attributs qui lui sont associés, vous pouvez appliquer un filtre par valeur d'attribut d'événement in-app. </li><li>Les événements in-app sont limités par défaut à 100 valeurs uniques par attribut. Exemple : si l'événement est « purchase » et l'attribut « content-type », il ne peut y avoir que 100 (ou moins) types de contenu possibles. Les valeurs numériques sont quant à elles illimitées.<br/>Si des attributs d'événements in-app (paramètres) et des valeurs n’apparaissent pas dans la liste, vous pouvez les ajouter manuellement en cliquant sur <strong>Ajouter un attribut d'événement</strong> &gt; <strong><strong>Ajouter un élément</strong></strong><br/><p><strong><img alt="Add_item.jpg" src="https://support.appsflyer.com/hc/article_attachments/10515147347089"/></strong></p><br/><p>Remarque :</p><p>- Tous les éléments d'événement ajoutés manuellement doivent être saisis sous forme de chaîne de caractères (texte) uniquement. Les valeurs numériques ne doivent pas être ajoutées, elles ne fonctionneront pas correctement.</p><p>- Lorsqu'un événement est ajouté manuellement, l'estimation de la taille de l'audience peut être inexacte. <br/>Si vous souhaitez que plus de 100 attributs/valeurs apparaissent dans la liste, vous pouvez également contacter votre CSM ou envoyer un e-mail à hello@AppsFlyer.com.</p></li></ul></td></tr><tr><td colspan="3"><h4><span id="revenue::3358edf4"></span>Revenus</h4><p><img alt="revenue_filter.jpg" src="https://support.appsflyer.com/hc/article_attachments/8862929615633"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://support.appsflyer.com/hc/article_attachments/8862869108625"/></p><ul><li>Total des revenus d’achats in-app</li><li>Total des revenus publicitaires</li><li>Revenu total </li></ul></td><td colspan="2"><p><img alt="B.jpg" src="https://support.appsflyer.com/hc/article_attachments/8862869246097"/></p><ul><li>Est égal</li><li>Est plus grand que</li><li>Est plus petit que </li></ul><p><strong>Définitions :</strong></p><ul><li> <strong>Revenu total des achats intégrés :</strong> valeur totale de tous les événements rapportés d’après le <code>af_revenue</code> paramètre d’un appareil/CUID spécifique</li><li> <strong>Revenu publicitaire total :</strong> <span>revenus publicitaires totaux générés par un appareil/CUID spécifique</span> </li><li><span><strong>Revenus totaux :</strong> Revenu total des achats in-app + revenus publicitaires totaux</span></li></ul><p><strong>Remarques :</strong></p><ul><li><span>Pour utiliser les filtres <strong>Revenus publicitaires totaux</strong> et <strong>Revenus totaux</strong>, <a href="./roi360-guide-ad-revenue-attribution" target="_blank">l’attribution des revenus publicitaires</a> doit être implémentée dans votre compte AppsFlyer.</span></li><li>Toutes les options de filtrage des revenus sont mesurées en USD.<span></span> </li></ul></td></tr><tr><td colspan="3"><h4><span id="geo"></span>Géo</h4><p><img alt="location_filter.jpg" src="https://support.appsflyer.com/hc/article_attachments/8862931272593"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://support.appsflyer.com/hc/article_attachments/8862869108625"/></p><ul><li>Localisation </li></ul></td><td><p><img alt="B.jpg" src="https://support.appsflyer.com/hc/article_attachments/8862869246097"/></p><ul><li>Est</li><li>N'est pas</li></ul></td><td><p><img alt="C.jpg" src="https://support.appsflyer.com/hc/article_attachments/8862873752721"/></p><p><strong>Options d'emplacement</strong></p><ul><li>Pays</li><li>État </li><li>city</li></ul></td></tr><tr><td colspan="3"><p><strong>Remarques concernant l'emplacement :</strong></p><ul><li>Si vous sélectionnez plusieurs pays, vous ne pouvez pas sélectionner d'états.</li><li>Si vous sélectionnez plusieurs états, vous pouvez choisir les villes.</li></ul></td></tr><tr><td colspan="3"><h4><span id="owned-media"></span>Médias propres</h4><p><img alt="doctored_owned_media_image_with_app_specified__final_version_.jpg" src="https://support.appsflyer.com/hc/article_attachments/8862985217297"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://support.appsflyer.com/hc/article_attachments/8862869108625"/></p><ul><li>Source média propriétaire</li><li>Campagne de médias propriétaires</li><li>Ensemble de publicités média propriétaire</li><li>Publicités média propriétaire</li></ul></td><td><p><img alt="B.jpg" src="https://support.appsflyer.com/hc/article_attachments/8862869246097"/></p><ul><li>Est</li><li>N'est pas</li></ul></td><td><p><img alt="C.jpg" src="https://support.appsflyer.com/hc/article_attachments/8862873752721"/></p><p>Des valeurs telles que :</p><ul><li>E-mail</li><li>SMS</li><li>Web</li><li>Réseaux sociaux (hors publicité payante)</li><li>Codes QR</li><li>Les parrainages</li><li>Campagnes média spécifiques, ensembles de publicités et publicités</li></ul></td></tr><tr><td colspan="3"><p>Vous pouvez créer des audiences ciblées composées d'utilisateurs qui ont été attribués à des sources média spécifiques. Vous pouvez également choisir votre niveau de granularité et cibler les utilisateurs qui proviennent d'une source média, d'une campagne, d'un ensemble de publicités ou d'une certaine publicité individuelle propriétaire.</p><p>L'audience peut être utilisée pour réengager ces utilisateurs avec des messages personnalisés, que ce soit sur les médias propriétaires ou payés, ou comme liste d'exclusion pour éviter qu'ils ne voient des publicités non pertinentes ou inutiles lors de l'exécution des campagnes d'acquisition d'utilisateurs ou de réengagement.</p></td></tr><tr><td colspan="3"><h4><span id="device"></span>Appareil</h4><p><img alt="device_filter.jpg" src="https://support.appsflyer.com/hc/article_attachments/8863003498641"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://support.appsflyer.com/hc/article_attachments/8862869108625"/></p><ul><li><span>Marque de l'appareil</span></li><li><span>Modèle d'appareil</span></li><li><span>Version de l'app</span></li><li><span>Version OS</span></li><li><span>carrier</span></li></ul></td><td><p><img alt="B.jpg" src="https://support.appsflyer.com/hc/article_attachments/8862869246097"/></p><ul><li>Est</li><li>N'est pas </li></ul></td><td><p><img alt="C.jpg" src="https://support.appsflyer.com/hc/article_attachments/8862873752721"/> Valeur sélectionnée</p></td></tr><tr><td colspan="3"><h4><span id="attribution"></span>Attribution</h4><p><img alt="Attribution_filter.jpg" src="https://support.appsflyer.com/hc/article_attachments/8863047608593"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://support.appsflyer.com/hc/article_attachments/8862869108625"/></p><ul><li>Organique</li><li>Retargeting</li></ul></td><td><p><img alt="B.jpg" src="https://support.appsflyer.com/hc/article_attachments/8862869246097"/></p><ul><li>False</li><li>True</li></ul></td><td> </td></tr><tr><td colspan="3"><h4><a href="./audiences-create-better-audiences-with-user-attribute-data" target="_blank"><span id="user-attributes"></span>Attributs d’utilisateur</a></h4><p><img alt="user_attribute_filter.jpg" src="https://support.appsflyer.com/hc/article_attachments/8863049711377"/></p></td></tr><tr><td><p><img alt="A_.jpg" src="https://support.appsflyer.com/hc/article_attachments/8862869108625"/></p><p>Nom d'attribut d'utilisateur</p></td><td><p><img alt="B.jpg" src="https://support.appsflyer.com/hc/article_attachments/8862869246097"/></p><ul><li>Type de chaîne <ul><li>Est</li><li>N'est pas</li></ul></li><li>Type de numéro <ul><li>Est</li><li>est supérieur à</li><li>Est inférieur à</li></ul></li></ul></td><td><p><img alt="C.jpg" src="https://support.appsflyer.com/hc/article_attachments/8862873752721"/><br/>Pour la chaîne : Sélectionnez une valeur</p><p>Pour le chiffre : Entrez une valeur</p></td></tr></tbody></table>

</Accordion>

<div id="combine-rulesets" />

<Accordion title="Assembler les ensembles de règles">

**Pour associer un ensemble de règles à une audience existante :**

1. Allez dans **Engager** > **Audiences**.
2. Cliquez sur **Ajouter une audience**.  
   L'onglet **Créer** s'affiche.
3. Saisissez un **nom d'audience** unique.
4. Sélectionnez la plateforme : **Android** ou **iOS**.
5. [Facultatif] Sélectionnez **Paramètres avancés** pour choisir [l'identifiant utilisateur](/docs/audiences-guide#user-identifier-device-id-vs-customer-id) :
   * [Par défaut] **ID d'appareil** : évalue les règles par ID d'appareil exclusivement.
   * **ID de client** : évalue les règles en regroupant les appareils d'après le CUID. Utilisez cette méthode après avoir vérifié que vos données ont bien des CUID valides.
6. Cliquez sur **Audience existante**, puis sélectionnez l'audience concernée.
7. Sélectionnez un opérateur : et, ou exclure.

**Limitations :**

* L'audience existante doit être sur la même plateforme (iOS ou Android) que la nouvelle audience.
* Une audience basée sur une audience existante ne peut pas être utilisée.
* Une audience importée ne peut pas être utilisée.

</Accordion>

<div id="create-and-manage-partner-connections" />

## Créer et gérer les relations avec les partenaires

Cette section explique comment créer et gérer des connexions avec des partenaires média.

<div id="create-a-new-connection" />

<Accordion title="Créer une nouvelle connexion">

L'onglet **Connexions** affiche toutes les connexions de votre partenaire et le statut de chacune d'entre elles. Toutes les informations permettant d'importer les données d'une audience vers un partenaire média sont contenues dans la connexion du partenaire. Vous pouvez avoir plusieurs connexions pour un même partenaire média (en utilisant différents comptes, informations de connexion, etc.).

**Pour créer une nouvelle connexion :**

1. Allez dans **Engager** > **Audiences > Connexions**.
2. Cliquez sur **+ Nouvelle connexion**.  
   **Remarque :** Si vous créez une nouvelle connexion partenaire à partir de l'outil de création d'audience, cliquez sur **+ Ajouter une connexion partenaire** dans la fenêtre **Gérer les connexions d'audience**.
3. Sélectionnez un **nom de partenaire**.
4. Saisissez un **nom de connexion.**
5. Remplissez les champs obligatoires / informations de connexion pour le partenaire. Certains partenaires donnent <Anchor target="_blank" href="/marketers/fr/docs/audiences-partner-connections">des instructions détaillées en lien avec la connexion.</Anchor>
6. Sélectionnez les identifiants d'utilisateur dont vous autorisez le partage avec ce partenaire.
   * Les identifiants pris en charge varient selon les partenaires. Seuls les identifiants pris en charge par le partenaire que vous sélectionnez apparaîtront dans la liste.
   * Seuls les identifiants conformes à votre <Anchor target="_blank" href="/marketers/fr/docs/audiences-user-identifier-policy">politique d'identification des utilisateurs au niveau du compte</Anchor> seront importés. Un message d'alerte s'affichera si jamais vous sélectionnez un identifiant qui n'est pas en accord avec la politique de votre compte. <Anchor target="_blank" href="/marketers/fr/docs/audiences-user-identifier-policy">![doctored_connection_image.jpg](https://support.appsflyer.com/hc/article_attachments/8863064248081)</Anchor>
7. Cliquez sur **Enregistrer**.

</Accordion>

<div id="manage-connections" />

<Accordion title="Gérer les connexions">

**Pour gérer une connexion existante :**

1. Sélectionnez un partenaire.
2. Sélectionnez la connexion.

   <Image align="center" alt="Edit_connection_screen.jpg" src="https://support.appsflyer.com/hc/article_attachments/8863066051217" />
3. Effectuez l'une des actions suivantes :

| Option | Marche à suivre |
| --- | --- |
| <span id="change-the-connection-name"></span>Modifier le nom de la connexion | **Pour changer le nom d'une connexion,** modifiez-le directement dans le champ **Nom de la connexion**. |
| <span id="reconnect"></span>Reconnecter | **Pour reconnecter :**<ol><li>Si le statut de la connexion n'est pas actif, cliquez sur **Reconnecter**.</li><li>Mettez les éléments d'identification de la connexion à jour, ou connectez-vous au partenaire pour vous authentifier à nouveau selon les instructions qui s’affichent.</li></ol> |
| <span id="modify-user-identifiers"></span>Modifier les identifiants d'utilisateur | **Pour modifier les identifiants d'utilisateur,** sélectionnez/désélectionnez les identifiants d'utilisateur dont vous autorisez le partage avec ce partenaire.  Seuls les identifiants conformes à votre <Anchor target="_blank" href="/marketers/fr/docs/audiences-user-identifier-policy">politique d'identification des utilisateurs au niveau du compte</Anchor> seront importés. |
| <span id="delete-connection"></span>Supprimer la connexion | **Pour supprimer une connexion :**<ol><li>S'il y a des audiences connectées, supprimez-les comme suit :<ol><li>Sélectionnez l'audience.</li><li>L'onglet Connexions de l'audience s'ouvre dans un nouvel onglet.</li><li>Supprimez la connexion.</li><li>Fermez l'onglet.</li></ol></li><li>Répétez cette procédure jusqu'à ce que plus aucune audience ne soit connectée.</li><li>Cliquez sur **Supprimer la connexion**.</li></ol> |

</Accordion>

<div id="dashboard-and-metrics" />

## Tableau de bord et métriques

Cette section décrit les fonctionnalités et les résultats de campagne qui apparaissent dans le tableau de bord.

<div id="audiences-dashboard" />

<Accordion title="Tableau de bord des audiences">

<Image align="center" alt="new_dashboard_image_doctored.jpg" src="https://support.appsflyer.com/hc/article_attachments/12059490072465" />

| Colonne | Description |
| --- | --- |
| <span id="audience-name"></span>Nom de l’audience | Nom de l’audience |
| <span id="size"></span>Taille | Tous les utilisateurs qui répondent aux critères de l’audience |
| <span id="upload-size"></span>Taille de l’importation | Estimation de la taille de l'audience pouvant être importée d’après la politique d'identification des utilisateurs au niveau de votre compte, et les identifiants sélectionnés pour les connexions de partenaires liées.<br /><br />**Remarque :** La taille réelle côté partenaire peut être différente selon leur procédure de matching. |
| <span id="app-name"></span>Nom de l'app | L'app (ou les apps) référencée dans la définition de l'audience. Ne correspond pas forcément aux apps qui sont ciblées par les campagnes utilisant l'audience. |
| <span id="upload-to"></span>Importer vers | <ul><li>Icônes des partenaires à qui l'audience est envoyée</li><li><Image alt="SplitAudiences.png" src="https://support.appsflyer.com/hc/article_attachments/360004529437" width="36px" /> indique que l’audience est répartie entre les partenaires</li></ul> |
| <span id="incrementality"></span>Incrementalité | Cette colonne s'affiche si vous avez souscrit à la fonctionnalité <Anchor target="_blank" href="/marketers/fr/docs/incrementality-for-remarketing-overview">Incrementality.</Anchor> Les statuts sont les suivants :<ul><li>**En attente** - Période initiale de collecte de données (48 heures) à compter de la date de début de campagne.</li><li>**Lier la campagne** - Sélectionnez la ou les campagne(s) à lier à l'expérience. Si nous avons une suggestion de campagne pour vous, elle sera présélectionnée (les suggestions suivantes seront classées par pertinence dans la liste déroulante).</li><li>**Active** - L'expérience est en cours</li><li>**Terminée** - L'expérience est terminée</li></ul>En cliquant sur un statut, vous accédez au tableau de bord de l'incrémentalité. |
| <span id="upload-status"></span>Statut de l’importation | <ul><li>Statut actuel de l'importation de l'audience</li><li>L'infobulle affiche la date et l'heure de la dernière importation.</li><li>En cas d'échec, cliquez sur **Afficher les détails** et corrigez les erreurs en fonction du message d’instruction qui s'affiche</li></ul> |

</Accordion>

<div id="campaign-metrics" />

<Accordion title="Métriques de campagne">

<div id="metrics-hash" />

#### métriques codées

<div id="campaign-metrics-basics" />

#### Les métriques de campagne : ce qu'il faut savoir

La section **Métriques de campagne** du tableau de bord des Audiences regroupe les données des campagnes qui ont utilisé une audience pour le ciblage (pour l'inclusion, l'exclusion ou comme base pour une audience clonée).

* Utiliser une audience pour le ciblage (et décider comment l'utiliser) fait partie des étapes de création des campagnes avec les partenaires média. Les partenaires média varient en fonction de la manière dont les audiences peuvent être utilisées.

**Partenaires soutenus :** **Partenaires pris en charge :** pour l'instant, les données ne sont proposées que pour Facebook, Google Ads et Snapchat. La section **Métriques de campagne** du tableau de bord ne s'affiche que si vous avez des audiences connectées aux partenaires pris en charge.

**Pour afficher les métriques de campagne :**

1. Faites défiler jusqu’à la droite du tableau de bord des Audiences pour afficher l'ensemble de la section **Métriques de campagne**.
2. Utilisez le sélecteur de date pour choisir la période dont vous souhaitez obtenir les données. (Par défaut le tableau de bord affiche les données des 7 derniers jours).

**Pour télécharger les métriques de campagne** **sur la période choisie :**

1. Cliquez sur le bouton **Exporter**, en haut du tableau de bord des Audiences.
2. Une fois le fichier généré, il se téléchargera automatiquement.

<div id="summary-view" />

#### Aperçu

L’aperçu des **Métriques de campagne** offre un résumé des données de la campagne pour chaque audience :

<Image align="center" alt="campaign_metrics_summary_view.jpg" src="https://support.appsflyer.com/hc/article_attachments/8863145932177" width="433px" />

| Colonne | Description |
| --- | --- |
| <span id="campaigns"></span>Campagnes | Le nombre total de campagnes qui ont utilisé l'audience pour le ciblage sur la période choisie (uniquement les campagnes menées avec les partenaires pris en charge). |
| <span id="campaign-cost"></span>Coût de la campagne | Le coût total de ces campagnes sur la période définie |
| <span id="campaign-revenue"></span>Revenus de la campagne | Le total des revenus attribués à ces campagnes au cours de la période choisie |

<div id="detailed-view" />

#### Vue détaillée

Dans l’aperçu, cliquez sur l’icône <Image alt="show_detailed_view_icon.png" src="https://support.appsflyer.com/hc/article_attachments/4406917127569" width="24px" /> pour accéder à la vue détaillée de l’audience sélectionnée. (L’icône <Image alt="show_detailed_view_icon.png" src="https://support.appsflyer.com/hc/article_attachments/4406917127569" width="24px" /> apparaît au bout à droite d’une ligne lorsque vous y placez votre souris.)

La vue détaillée affiche les données regroupées par partenaire pris en charge et par campagne.

<Image align="center" alt="campaign_metrics_detailed_view.jpg" src="https://support.appsflyer.com/hc/article_attachments/8863148809105" />

Si l'audience sélectionnée a été utilisée pour cibler plusieurs applications, utilisez le menu déroulant ![](https://support.appsflyer.com/hc/article_attachments/4406924702353) pour filtrer les données par application.

Cliquez sur le lien ![](https://support.appsflyer.com/hc/article_attachments/4406917170833)**Tableau de bord général** altpin\_B.pngalt pour afficher les campagnes dans le tableau de bord général :

* Le tableau de bord s'ouvrira dans un nouvel onglet de votre navigateur, et il sera automatiquement filtré en fonction des campagnes concernées.
* Si le lien **Tableau de bord général** est désactivé, vous pouvez l'activer en ne sélectionnant qu'une seule application dans le menu déroulant ![](https://support.appsflyer.com/hc/article_attachments/4406924702353). Une fois que le lien est activé, si vous le cliquez vous accédez au tableau de bord général de l'app sélectionnée.

| Colonne | Description |
| --- | --- |
| <span id="cost"></span>Coût | Le coût de la campagne sur la période sélectionnée (coût total, puis coût regroupé par partenaire pris en charge et par campagne) |
| <span id="revenue"></span>Revenus | Le revenu attribué aux campagnes sur la période sélectionnée (coût total, puis coût divisé par partenaire pris en charge et par campagne) |
| <span id="daily-reach"></span>Portée quotidienne | Le nombre moyen et journalier d'utilisateurs uniques qui ont vu les publicités de la campagne durant la période choisie (tel que transmis par le partenaire) |

<div id="data-sources-and-availability" />

#### Sources de données et disponibilité

Il est plus simple de comprendre la disponibilité des **métriques de campagne** en regardant d'où sont issues les données :

* **Données des partenaires :** Comme c'est via vos partenaires média que vous sélectionnez l'audience (ou les audiences) qui sera ciblée par une campagne, seuls ces partenaires sont en capacité de vous fournir certaines informations :
  * La connexion d'une audience à une campagne (c'est à dire le fait qu'une audience spécifique a été utilisée comme cible par cette campagne)
  * Le nombre journalier d'utilisateurs uniques qui ont vu les publicités de la campagne (« portée quotidienne »)
* **Données AppsFlyer :** Les données sur les coûts et les revenus sont fournies par AppsFlyer.

<div id="partner-data-availability" />

<Accordion title="Disponibilité des données des partenaires">

Les données ne sont fournies que pour les campagnes qui sont menées avec des [partenaires pris en charge.](/docs/audiences-guide#les-métriques-de-campagne--ce-quil-faut-savoir)

* **Remarque :** Google Ads ne prend pas en charge les rapports de portée quotidienne.

</Accordion>

<div id="appsflyer-data-availability" />

<Accordion title="Disponibilité des données AppsFlyer">

Les données de coûts et de revenus sont disponibles dans la catégorie **Métriques de campagne** uniquement si elles apparaissent aussi pour vos apps dans d'autres sections AppsFlyer (ex : tableau de bord Général ou d'Événement).

* Les données sur les coûts nécessitent un abonnement à <Anchor target="_blank" href="/marketers/fr/docs/roi360-cost-aggregation-overview">ROI360</Anchor>.
* Les données de revenus requièrent d'avoir configuré <Anchor target="_blank" href="/marketers/fr/docs/roi360-guide-ad-revenue-attribution">l'attribution des revenus publicitaires</Anchor> et/ou <Anchor target="_blank" href="/marketers/fr/docs/roi360-revenue-attribution-overview">l'attribution des revenus d'événements in-app</Anchor>.

</Accordion>

<div id="why-dont-i-see-campaign-metrics-data-for-campaigns-run-with-supported-partners" />

<Accordion title="Je ne vois pas mes données dans les métriques de campagne pour les campagnes menées avec des partenaires pris en charge.">

Les données des mesures de campagne sont disponibles uniquement pour :

* Les campagnes connectées à une audience.
* Les campagnes lancées sur les sites des partenaires média pris en charge.
* Les campagnes actives dans la période principale sélectionnée.
* Les campagnes pour lesquelles nous recevons du trafic d'installation sur la période sélectionnée, dans le filtre Métriques de campagne.
* Les utilisateurs configurés pour la connexion du partenaire qui ont l'autorisation de recevoir les données de niveau campagne. Pour afficher les données, modifiez les autorisations de l'utilisateur liées au partenaire, ou utilisez d'autres identifiants dans les paramètres de connexion du partenaire.

</Accordion>

</Accordion>

<div id="traits-and-limitations" />

## Caractéristiques et limitations

Les caractéristiques et limitations suivantes s’appliquent :

<div id="traits" />

<Accordion title="Caractéristiques">

| Caractéristique | Prise en charge | Remarques |
| --- | --- | --- |
| Réseaux publicitaires | **x** |  |
| Agences | **x** |  |
| Transparence de l'agence | **x** |  |
| Fuseau horaire spécifique à l'app | N/A |  |
| Devise spécifique à l'app | N/A |  |
| Limitations de taille | N/A |  |
| Données organiques | ✓ | Inclus |
| Données non organiques | ✓ | Inclus |
| Actualisation des données | UTC quotidien | <ul><li>Les mises à jour sont envoyées quotidiennement aux partenaires.</li><li>Les listes d’événements in-app dans la mise à jour quotidienne du générateur de règles.</li></ul> |
| Données historiques | ✓ | Audiences a accès aux données des évènements de l’app sur les 90 jours qui précédent la date de votre abonnement à Audiences (31 jours pour les clics et impressions). Les données sont entièrement disponibles une fois que le processus de rétro-collecte est terminé (ce qui peut prendre jusqu'à 2 semaines). |
| Accès utilisateur du compte | ✓ | <ul><li>Certaines fonctionnalités, comme le téléchargement du CSV, la configuration des connexions S3, SFTP et des partenaires Slack, nécessitent l'autorisation du compte utilisateur d’accéder aux données brutes.</li><li>Par mesure de sécurité, en cas de suppression du compte d'un utilisateur qui a créé une audience, AppsFlyer interrompt l'envoi des données de cette audience au(x) partenaire(s) média. Pour vérifier l’état de mise en ligne de vos audiences, allez dans **Engager** > **Audiences**. Pour réactiver l'audience, dupliquez-la et configurez les paramètres de l'[audience fractionnée.](/docs/audiences-guide#audience-split-and-control-groups)</li></ul> |

</Accordion>

<div id="limitations" />

<Accordion title="Restrictions">

* Windows Phone n'est pas pris en charge.
* Les noms d’audience ne peuvent pas être modifiés du côté des partenaires connectés.
* Les valeurs d'événement imbriquées ne sont pas prises en charge.
* Lors de la création d'une audience, seuls les 100 principaux événements s'affichent. Cependant, lorsque vous commencez à saisir un nom d'événement, tous les événements s'affichent.
* Dans les ensembles de règles, les événements in-app sont limités à 100 valeurs uniques par attribut. Exemple : si l'événement est « purchase » et l'attribut « content-type », il ne peut y avoir que 100 (ou moins) types de contenu possibles. Les valeurs numériques sont quant à elles illimitées. Si vous avez besoin de plus de valeurs par attribut, contactez votre CSM ou envoyez un e-mail à hello@AppsFlyer.com.
* Les données sur les clics et les impressions ne contiennent que les appareils qui ont un *advertising\_id/idfa* sur leur URL de clic d'origine. Les appareils des utilisateurs issus des SRN, qui n'utilisent donc pas de liens d'attribution externes, ne sont pas inclus dans les données de clics pour les audiences.
* Seuls les nombres entiers sont pris en charge dans les filtres numériques de l'ensemble de règles. Les nombres décimaux (avec une virgule) ne sont pas pris en charge. **Exemple :** Un revenu in-app égal à 1 $ est pris en charge, mais pas un revenu à 1,5 $.
* Lorsque vous utilisez le filtre *Revenus totaux* dans le générateur de requêtes, l'estimation de la taille de l'audience n'est pas disponible. Ceci n'affecte pas la création de l'audience.
* Vous ne pouvez pas associer les audiences <Anchor target="_blank" href="/marketers/fr/docs/audiences-import-audience-segments-from-internal-systems">importées</Anchor> avec d'autres audiences ou ensembles de règles.
* La taille des fichiers téléchargés est limitée à 5 millions d'enregistrements.
* <Anchor target="_blank" href="/marketers/fr/docs/audiences-partner-connections#google-ads">Google Ads</Anchor> : Les campagnes UAC ne sont pas prises en charge. Il existe d'autres types de campagnes qui sont pris en charge.
* Les rapports d'événements via S2S doivent avoir un identifiant d'utilisateur CUID en accord avec l'ensemble de règles.
* Les audiences inactives sont mises en pause. Cela signifie qu'elles ne seront plus calculées, ni envoyées aux partenaires connectés. L'audience peut toujours être réactivée en cliquant sur **Importer maintenant.** Les calculs de l'audience et les envois automatiques aux partenaires reprendront alors leur fonctionnement.

</Accordion>

<div id="see-also" />

> 📄 **Articles connexes**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/incrementality-for-remarketing-overview">Guide Incrementality</Anchor>
> * <Anchor target="_blank" href="/marketers/fr/docs/run-an-incrementality-for-remarketing-experiment">Réaliser une expérience d'incrémentalité</Anchor>

<div data-zendesk-anchors="audiences-basics=les-bases-de-laudience h_01HBQMA619CKEESZD3ADSP3PSB=les-bases-de-laudience h_01HBQMA619K0TSN4KXEK9WC2B8=remarque-concernant-la-confidentialit%C3%A9 audience-split-and-incrementality-testing=partage-daudience-et-test-dincr%C3%A9mentalit%C3%A9 h_01HBQMA619KMJFVX7Y8MXMMQ6N=partage-daudience-et-test-dincr%C3%A9mentalit%C3%A9 get-started=d%C3%A9marrer h_01HBQMA619118PWF4TA98C4X0B=d%C3%A9marrer create-and-manage-audiences=cr%C3%A9er-et-g%C3%A9rer-les-audiences h_01HBQMA619DBX2C7DRY7MSV3P9=cr%C3%A9er-et-g%C3%A9rer-les-audiences h_01HBQMA6195AT0YD7783V6BQR6=create-a-custom-audience h_01HBQMA619F2P2CVPCSMX9RTKB=create-a-suggested-audience h_01HBQMA619RBRYNMVMNQ839196=exemple-dutilisation h_01HBQMA619ATHVJARHYXQNY955=import-an-audience h_01HBQMA6193FFM66XDTB6WYX06=connect-an-audience-to-media-partners user-identifier%E2%80%94device-id-vs-customer-id=user-identifier-device-id-vs-customer-id h_01HBQMA61A192YFES8TK1347FJ=user-identifier-device-id-vs-customer-id 01ECF4ZD0NWN5QQPP88ZKW0578=exemple--id-dappareil-et-cuid 01ECF4ZD0WNEF6FRPF1NJHZ9WR=audience-split-and-control-groups h_01HBQMA61ANM52HBDAFA5QZPFN=manage-audiences all-about-rulesets=tout-savoir-sur-les-ensembles-de-r%C3%A8gles h_01HBQMA61ANB4K0TCJ4WBHMV8D=tout-savoir-sur-les-ensembles-de-r%C3%A8gles h_01HBQMA61A30YGERD8Z6DXV3KA=audience-segmentation-rulesets h_01HBQMA61AF7V3M0Y8ZN1R0HZC=ruleset-examples h_01HBQMA61ATV5MHN35XMTJ8MEH=exemple--r%C3%A8gle-bas%C3%A9e-sur-la-localisation h_01HBQMA61ATB7NYKBP7CD6SZZH=exemple--r%C3%A8gle-bas%C3%A9e-sur-les-attributs-dutilisateur h_01HBQMA61APWHKS4EP2NKABSQD=exemple--revenus 01ECF4ZD0MJ8HVQCC54YHFE6DX=exemple--filtre-de-m%C3%A9dia-propri%C3%A9taire h_01HBQMA61AEKT6N97SJBW4B01C=ruleset-filters h_01HBQMA61A17Y4928D2ZDGAEXV=events h_01HBQMA61BK8NZF79KDPK0JBX6=inapp-events h_01HBQMA61B4FGBE11W6BW2Z9AH=revenue::3358edf4 h_01HBQMA61BX9XQKBX3MAGYXC2Y=geo h_01HBQMA61B9DRMSNKJM3B0WBE1=owned-media h_01HBQMA61BC1G2VZSJEJF90T7Q=device h_01HBQMA61BF2N8FN6TJ3JD6YXC=attribution h_01HBQMA61CKVMYYS8GG6CP72WD=user-attributes h_01HBQMA61C7K8R4AR13D4WHTHX=combine-rulesets create-and-manage-partner-connections=cr%C3%A9er-et-g%C3%A9rer-les-relations-avec-les-partenaires h_01HBQMA61C6WS72DQ8FXVR0KVW=cr%C3%A9er-et-g%C3%A9rer-les-relations-avec-les-partenaires h_01HBQMA61CRDF41WBYCDQ91M3R=create-a-new-connection h_01HBQMA61CXZYEW2R12KS99X2N=manage-connections dashboard-and-metrics=tableau-de-bord-et-m%C3%A9triques h_01HBQMA61C6WPFFR1F8P0HE4KA=tableau-de-bord-et-m%C3%A9triques h_01HBQMA61CMPNC9TYAW82ED18Q=audiences-dashboard h_01HBQMA61CWHR9GDANKT7P6Z27=campaign-metrics metrics-hash=m%C3%A9triques-cod%C3%A9es h_01HBQMA61CMF3WZFPXKY89076K=m%C3%A9triques-cod%C3%A9es campaign-metrics-basics=les-m%C3%A9triques-de-campagne--ce-quil-faut-savoir h_01HBQMA61C4D5HFCDY83HNF5K7=les-m%C3%A9triques-de-campagne--ce-quil-faut-savoir summary-view=aper%C3%A7u h_01HBQMA61DW9Z84G8CH1RNY2RF=aper%C3%A7u detailed-view=vue-d%C3%A9taill%C3%A9e h_01HBQMA61D3VHDKD103EMN61YH=vue-d%C3%A9taill%C3%A9e data-sources-and-availability=sources-de-donn%C3%A9es-et-disponibilit%C3%A9 h_01HBQMA61DB595QKRTPE97F94E=sources-de-donn%C3%A9es-et-disponibilit%C3%A9 h_01HBQMA61DCV0M97GMXRA1A30F=partner-data-availability h_01HBQMA61DXNR275AT9SK0G32S=appsflyer-data-availability h_01HBQMA61DH9P5B1H5GYXQ9CCN=why-dont-i-see-campaign-metrics-data-for-campaigns-run-with-supported-partners traits-and-limitations=caract%C3%A9ristiques-et-limitations h_01HBQMA61DT46P43FNSRC1KGAX=caract%C3%A9ristiques-et-limitations h_01HBQMA61DYHF0REXYKDQBDXP5=traits h_01HBQMA61D28F5RG2WXT801XXZ=limitations h_01HDNZ24ZDXSAPJ1F5QCB9X1EN=articles-connexes" />
