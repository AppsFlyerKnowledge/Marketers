---
title: 'Data Clean Room : créer les rapports de données d’attribution'
metadata:
  keywords:
    - Premium Feature
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-inbar-agassi
    - Marketers
    - Data Clean Room
  created_at: '2022-09-11T10:42:43Z'
  edited_at: '2024-09-09T14:56:27Z'
  id: 9035047905297
  locale: fr
  section: Data Clean Room
  section_id: 4591191779217
  url: https://support.appsflyer.com/hc/fr/articles/9035047905297
---
> **En bref :** créez des rapports de données d'attribution pour matcher les données de niveau utilisateur provenant des événements d'installation/ de retargeting avec les données de vos systèmes.

<div id="creating-an-attribution-data-report" />

## Créer un rapport de données d’attribution

**Pour créer un rapport de données d'attribution, suivez les étapes détaillées dans les onglets ci-dessous.**

**Remarque :** Ces étapes ont été divisées en onglets pour faciliter la lecture. Toutes les étapes doivent être complétées pour créer un rapport.

<div id="perform-preliminary-steps" />

<Accordion title="Préparation">

1. Allez sur la page **Rapports** de l’onglet **DCR.**
2. Cliquez sur le bouton **+ Nouveau rapport**.
3. Choisissez **Données d'attribution**comme type de données source, puis cliquez sur **Suivant** (en bas à droite de l’écran).
4. Saisissez le nom du rapport.
   * Vous pouvez choisir n'importe quel nom pourvu qu'il vous permette d’identifier le rapport sur la plateforme DCR.
   * **Attention !** Veillez à ce que le nom du rapport ne soit pas utilisé pour une autre source sur votre compte, ou vous ne pourrez pas **enregistrer le rapport**.
   * Obligations pour le nom du rapport :
     * Longueur : 2-80 caractères
     * Caractères valides :
       * toutes les lettres **(A-Z, a-z)**
       * *le premier caractère du nom ne doit pas être* un chiffre **(0-9)**
       * *le premier caractère du nom ne doit pas être* un trait d’union (-)
     * Caractères non valides :
       * les espaces
       * tous les autres symboles ou caractères spéciaux

</Accordion>

<div id="select-sources" />

<Accordion title="Sélectionner les sources">

Pour définir les données sources à utiliser dans le rapport :

<div id="attribution-data-sources" />

#### **Source des données d'attribution**

* **Apps :** Sélectionnez une ou plusieurs apps dans votre compte AppsFlyer.
* **Types d'attribution :** Sélectionnez un ou plusieurs types de données d’attribution à utiliser dans le rapport : 

| Installations | Une installation est enregistrée lorsqu’un utilisateur télécharge, installe et lance une app mobile. |
| --- | --- |
| Réinstallations | Une réinstallation est enregistrée lorsqu'un utilisateur installe une app, puis la désinstalle et la réinstalle pendant la fenêtre de réattribution.<ul><li>**Remarque :** La durée de la fenêtre de réattribution est définie dans Paramètres > Paramètres de l'app.</li></ul> |
| Réengagements | Un réengagement est enregistré lorsque l’utilisateur inactif d’une app donnée interagit avec une campagne de retargeting pour cette même app, avant de la lancer. |
| Ré-attributions | Une ré-attribution est enregistrée lorsque l’ancien utilisateur d’une app donnée (l’utilisateur l’a désinstallée) interagit avec une campagne de retargeting pour cette même app, avant de la réinstaller. |
| Installations organiques | Les installations organiques sont celles qui ne sont attribuées à aucune source média.<ul><li>**Remarque :** En incluant les installations organiques dans votre rapport vous augmenterez considérablement le nombre de lignes scannées.</li></ul> |

* **Fenêtre temporelle :** sélectionnez le nombre de jours de données historiques pendant lequel la DCR doit rechercher les événements d’attribution qui matchent les événements de votre source personnalisée (de 1 à 180 jours).

<div id="custom-sources" />

#### **Sources personnalisées**

Pour la structure de votre rapport, vous pouvez choisir d’utiliser les données de n’importe quelle <Anchor target="_blank" href="/marketers/fr/docs/data-clean-room-working-with-sources">source personnalisée que vous avez créée.</Anchor> Vous devez sélectionner au moins une source personnalisée.

</Accordion>

<div id="join-sources" />

<Accordion title="Relier les sources">

Pour matcher les données entre les sources, chacune des sources **personnalisées** utilisées dans le rapport doit inclure un <Anchor target="_blank" href="/marketers/fr/docs/data-clean-room-setting-up-cloud-services">identifiant</Anchor> mappé à un **identifiant de clé** dans les données d’attribution.

<div id="what-is-a-key-identifier" />

#### **Qu’est-ce qu’un identifiant de clé ?**

Vous pouvez mapper l’un de ces identifiants de données d’attribution comme **identifiant de clé :**

* **ID AppsFlyer (af\_id) :** un identifiant d'app unique généré par AppsFlyer lors de l'installation –
  * Cet ID s'affiche dans tous les événements enregistrés par AppsFlyer.
  * Un nouvel ID AppsFlyer est généré dans le cas où une app est supprimée puis réinstallée.
* **ID utilisateur client (CUID) :** un identifiant utilisateur unique souvent généré et défini par le propriétaire de l’app au moment de l’inscription de l’utilisateur.
  * L’utilisation du CUID pour mapper des données nécessite que votre app soit configurée pour <Anchor target="_blank" href="/marketers/fr/docs/customer-user-id-field-cuid">envoyer le CUID à AppsFlyer</Anchor> via le SDK ou l’API de serveur à serveur (S2S).

<div id="important" />

> 🚧 **Attention !**
>
> Toutes les sources média ne permettent pas de matcher à l’aide du CUID. Il est fortement recommandé d’utiliser l’ID AppsFlyer.

<div id="mapping-schemes-directindirect" />

#### **Schémas de mappage (direct/indirect)**

Si le rapport utilise plusieurs sources personnalisées, seule l’une d’entre elles doit être mappée **directement** à un identifiant de clé des données d'attribution. Les autres sources personnalisées peuvent être mappées **directement ou indirectement,** comme l’illustre cet exemple :

<div id="example" />

> 📄 **Exemple**
>
> <Image align="center" alt="dcr_mapping_identifiers_attribution_data.png" src="https://files.readme.io/18d1ddd8305f790dc621f871695b8cfb30f5e5a5d758c219e76ec7822ec18f2f-9969690360849.png" />
>
> Dans le scénario ci-dessus :
>
> * L’identifiant de source personnalisée #1 **AF** est mappé directement à l’identifiant de clé des données d'attribution **af\_id.**
> * La source personnalisée #2 est mappée indirectement : **user\_code** --> **AF** --> **af\_id.**
> * La source personnalisée #3 est mappée indirectement (via une chaîne plus longue) :
>   **user\_id** --> **user\_code** --> **AF** --> **af\_id.**
> * L’identifiant de source personnalisée #4 **ID** est mappé directement à l’identifiant de clé des données d'attribution **af\_id.**
>   * Notez qu’il aurait aussi pu être mappé indirectement (via l’identifiant de la source personnalisée #3 **user\_id**), mais les deux méthodes fonctionnent.
>
> ✓ Ce schéma de mappage permet de matcher les données entre toutes les sources, en effet, chaque source personnalisée est mappée directement ou indirectement à l’identifiant de clé d’événement des données d'attribution **af\_id.**

</Accordion>

<div id="determine-treatment-of-multiple-matching-events" />

<Accordion title="Définir le traitement de multiples événements de matching">

<div id="note" />

> 📘 **Remarque**
>
> Si les types d'attribution sélectionnés pour le rapport comprennent **uniquement les installations et/ou installations organiques**, cette section ne vous concerne pas. Veuillez vous rendre directement à la section [Sélection des dimensions](/docs/data-clean-room-creating-attribution-data-reports#select-dimensions).

Si les types d'attribution que vous sélectionnez pour votre rapport incluent des **réinstallations**, des **réengagements ou des réattributions**, il est possible que les données d'attribution incluent plus qu’un seul événement avec le même identifiant de clé sur la période sélectionnée. Si cela se produit, vous devez dire à la DCR quels événements de matching doivent être inclus dans le rapport.

<div id="matching-all-events" />

#### **Matcher tous les événements**

La méthode de matching la plus complète permet à votre rapport d'inclure tous les événements de matching. Pour obtenir ce résultat, vous devez mapper un identifiant dans l'une des sources personnalisées du rapport, à l'identifiant des données d'attribution **install\_time.**

* L'identifiant dans votre source mappé à install\_time doit être au format suivant : **aaaa-MM-jj HH:mm:ss.**
* **Remarque :** Même si le nom de l'identifiant des données d'attribution est install\_time, il indique en réalité **l'heure de l'événement** lorsqu'il fait référence aux événements de réinstallation, ré-engagement ou ré-attribution.

<div id="note-1" />

<div id="matching-a-single-event" />

#### **Matcher un événement unique**

Si les types d'attribution que vous sélectionnez pour votre rapport incluent les ré-installations, ré-engagements ou ré-attributions, mais que vous ne mappez pas d'identifiant à **install\_time**, vous devrez choisir d'utiliser soit le **dernier** soit le **premier** événement de matching dans votre rapport.

* **Dernier événement :** l'événement d'attribution inclus dans le rapport est le dernier événement (le plus récent) sur la période qui matche un certain identifiant de clé.
* **Premier événement :** l'événement d'attribution inclus dans le rapport est le premier événement (le plus ancien) sur la période qui matche un certain identifiant de clé.

faites votre choix en fonction de l’événement qui vous semble le plus pertinent par rapport aux informations que vous souhaitez obtenir du rapport.

</Accordion>

<div id="select-dimensions" />

<Accordion title="Sélectionner les dimensions">

N’oubliez pas que les données de niveau utilisateur ne peuvent pas être rapportées par la DCR. Elles vous fournissent cependant des informations précieuses si vous agrégez (ou regroupez) les données selon les dimensions de votre choix.

Une dimension est généralement un attribut avec lequel vous catégorisez les utilisateurs d’une app (ex. géo, date d’installation, campagne, etc.)

<div id="selecting-report-dimensions" />

#### **Sélection des dimensions d’un rapport**

Les dimensions du rapport des données d'attribution peuvent comprendre :

* N’importe quelle [dimension de données d’attribution disponible](/docs/data-clean-room-creating-attribution-data-reports#available-attribution-data-dimensions)
* N’importe quel champ des sources personnalisées dans le rapport qui a été <Anchor target="_blank" href="/marketers/fr/docs/data-clean-room-working-with-sources#3-define-the-source-structure">catégorisé comme dimension</Anchor>

**Pour sélectionner les dimensions à inclure dans votre rapport :**

1. Sélectionnez une ou plusieurs dimensions dans la liste des **dimensions des sources** sur la gauche, et utilisez le bouton **Ajouter** au milieu de l’écran pour les ajouter à la liste des **dimensions du rapport.**  
   * Vous pouvez utiliser la barre de recherche pour trouver les dimensions dans les listes.
2. Pour supprimer une dimension, sélectionnez-la dans les **dimensions du rapport**, puis utilisez la fonction **Retirer** pour la remettre dans la liste des **dimensions des sources**.
3. Répétez jusqu’à ce que vous ayez ajouté chaque dimension que vous souhaitez inclure dans le rapport.

**Remarque :** Par défaut, tous les rapports sont regroupés par la dimension des données d'attribution **media\_source.** Si vous ne souhaitez pas utiliser cette dimension dans votre rapport, vous pouvez la retirer de la liste des **dimensions du rapport**.

<div id="optional-customizing-dimension-display-names" />

#### **[Facultatif] Personnaliser les noms d’affichage des dimensions**

Par défaut, les noms des dimensions s’affichent dans votre rapport exactement tels que dans les données d’attribution ou dans vos sources personnalisées. Si vous le souhaitez, vous pouvez personnaliser les noms de dimension de votre rapport.

**Pour personnaliser le nom d’affichage d’une dimension :**

1. Dans la liste des **dimensions du rapport**, passez la souris sur le nom de la dimension dont vous souhaitez modifier le nom d’affichage.
2. Cliquez sur le bouton de modification ![edit_button.png](https://files.readme.io/4c3822661beac49fad247c7f5958a535e46031238e975a5323a5550722c89c8a-10753875375377.png) qui s’affiche à droite de la dimension.
3. Remplacez le nom par le nom d’affichage de la dimension à utiliser dans votre rapport (jusqu’à 50 caractères).
4. Cliquez sur **OK** pour enregistrer le nom d’affichage, ou **X** pour l’annuler.

<div id="preserving-privacy-while-grouping-by-dimension-regrouping" />

#### Protection de la confidentialité lors du regroupement par dimension (regroupement)

En fonction de la taille de votre ensemble de données, du nombre de dimensions choisies et de différents facteurs, il peut arriver qu’un rapport contienne un ou plusieurs groupes avec trop peu d’utilisateurs pour permettre le reporting. Si les données étaient rapportées de cette façon, cela enfreindrait les règles concernant la fourniture de données au niveau de l’utilisateur.

* **Attention !** Le nombre minimum d’utilisateurs pour autoriser le reporting varie d’une source média à l’autre.

Toutefois, au lieu de retirer ou masquer complètement les données du rapport, la DCR utilise un **procédé de regroupement** pour fournir autant de détails que possible tout en préservant la confidentialité de l’utilisateur.

<div id="regrouping-example" />

> 📄 **Exemple de regroupement**
>
> Supposons que vous ayez configuré un rapport avec les dimensions suivantes (dans l’ordre) :
>
> * **Dimensions des données d'attribution** :
>   * media source
>   * campaign
>   * adset\_name
>   * ad\_id
> * **Dimensions des sources personnalisées :**
>   * user\_type
>
> **Avant le regroupement**
>
> Après une première analyse des données, la DCR décide que les données se répartissent comme suit :
>
>
>
> | source  <br />média | campagne | nom de  <br />l’adset | ID  <br />publicitaire | type  <br />d’utilisateur | rév  <br />J0 | rév  <br />J7 | total | reporting ? |
> | --- | --- | --- | --- | --- | --- | --- | --- | --- |
> | media\_source | UA\_100 | green | kjh867 | buyer | 1 | 4 | 120 | ✓ |
> | media\_source | UA\_101 | green | jkj987 | ultra | 2 | 23 | 220 | ✓ |
> | media\_source | UA\_200 | green | lkh123 | beg | 6 | 7 | x | **X** |
> | media\_source | UA\_200 | green | ilk945 | beg | 3 | 21 | x | **X** |
> | media\_source | UA\_200 | green | plm654 | beg | 8 | 17 | x | **X** |
>
>
>
> Ici, les 3 dernières lignes ne sont pas rapportées car il y a trop peu d’utilisateurs dans chacune. (Cette source média nécessite un minimum de **y** utilisateurs pour pouvoir être rapportée. Or, ici il n’y en a que **x**.)
>
> Selon la logique du regroupement, la DCR « élimine » d’abord la dernière dimension des données d'attribution listée (dans ce cas précis **ad\_id**). Elle analyse ensuite une seconde fois les données pour déterminer quelles lignes peuvent être incluses dans le rapport.
>
> **Après le regroupement**
>
> Après l’action de regroupement, le rapport s’affiche comme suit :
>
>
>
> | source  <br />média | campagne | nom de  <br />l’adset | ID  <br />publicitaire | type  <br />d’utilisateur | rév  <br />J0 | rév  <br />J7 | total | reporting ? |
> | --- | --- | --- | --- | --- | --- | --- | --- | --- |
> | media\_source | UA\_100 | green | kjh867 | buyer | 1 | 4 | 120 | ✓ |
> | media\_source | UA\_101 | green | jkj987 | ultra | 2 | 23 | 220 | ✓ |
> | media\_source | UA\_200 | green | RESTREINTE | beg | 17 | 45 | y (x+x+x) | ✓ |
>
>
>
> **Résultats :**
>
> * La dernière ligne réunit maintenant les données qui se trouvaient avant sur 3 lignes. Maintenant, la ligne cumulée a un nombre d’utilisateurs égal à **y**, elle peut donc être rapportée.
> * La dimension qui était *éliminée* est maintenant marquée comme RESTREINTE.
> * S’il y a d’autres lignes non rapportables (avec moins de **y** utilisateurs), la DCR continue d’analyser les données sur une base itérative, en éliminant une dimension après l’autre jusqu’à ce que :
>   * Il soit possible de rapporter toutes les lignes ; ou
>   * Il n’y ait plus aucune dimension de données d'attribution à éliminer
>
> **Remarque :** Par défaut, la DCR applique le regroupement uniquement aux [dimensions des données d'attribution](/docs/data-clean-room-creating-attribution-data-reports#available-attribution-data-dimensions) (et non aux dimensions des sources personnalisées). Si les données regroupées par une dimension de données d'attribution produisent une ligne avec moins de **y** utilisateurs, alors les données de cette ligne sont marquées comme RESTREINTES.
>
> * *Ci-dessous vous trouverez une fonctionnalité avancée que vous pouvez aussi utiliser pour appliquer le regroupement aux dimensions des sources personnalisées.*

<div id="optional-managing-dimension-priority" />

#### **[Facultatif] Gérer la priorité d’une dimension**

Par défaut, les dimensions des données d'attribution sont éliminées dans l’ordre inverse de leur apparition dans la liste des **dimensions du rapport**. Toutefois, vous pouvez modifier la séquence par défaut et/ou appliquer le regroupement aux dimensions source personnalisées sélectionnées pour conserver les dimensions qui vous semblent les plus importantes.

**Pour modifier l’ordre dans lequel les dimensions sont éliminées :**

1. Cliquez sur le bouton **Gérer la priorité des dimensions**.
2. Sélectionnez une dimension et faites-la glisser à l’emplacement souhaité dans la liste (vous pouvez aussi utiliser les flèches à droite pour la déplacer).
   * Une dimension marquée comme **Haute priorité** (en haut de la liste) sera la dernière à être éliminée si un regroupement s’impose.
3. [Facultatif] Pour appliquer le regroupement aux dimensions de source personnalisée :
   1. Cliquez sur **Utiliser les options avancées pour modifier le regroupement**
   2. Sélectionnez les dimensions de source personnalisée auxquelles vous souhaitez appliquer le regroupement.
   3. Les dimensions sélectionnées sont ajoutées à la liste **Gérer la priorité des dimensions**.
      * Par défaut, ces dimensions sont ajoutées au bas de la liste, c’est-à-dire qu’elles sont en **Basse priorité** pour le regroupement. Vous pouvez cependant les réorganiser comme n’importe quelle dimension de données d'attribution, comme décrit ci-dessus.
4. Cliquez sur **OK** pour enregistrer vos modifications.
   * Sur l’écran principal, la liste des **dimensions du rapport** reste dans l’ordre d’origine, mais l’ordre corrigé a bien été enregistré. (Cliquez à nouveau sur le bouton **Gérer la priorité des dimensions** si vous souhaitez revoir ou modifier votre sélection.)

</Accordion>

<div id="select-metrics" />

<Accordion title="Sélectionner des métriques">

Les métriques (mesures) sont les données numériques que vous avez collectées pour un utilisateur d’app ( le revenu, le nombre d’ouvertures de l’app, la LTV, etc.), elles peuvent avoir n’importe quel valeur **numéraire** dans les champs des sources que vous avez définies comme métrique.

**Pour sélectionner les métriques (mesures) à inclure dans votre rapport :**

1. Sélectionnez une ou plusieurs mesures dans la liste **Métriques provenant des sources** (sur la gauche) et utilisez le bouton **Ajouter** au milieu de l’écran pour les ajouter à la liste des **Métriques du rapport.**
   * Vous pouvez utiliser la barre de recherche pour localiser les métriques dans les listes.
2. Pour chaque mesure dans la liste **Métriques du rapport**, indiquez si vous souhaitez que les données soient rapportée comme :
   * la somme de valeurs numériques ; ou
   * un décompte séparé des valeurs
3. Pour retirer une métrique, sélectionnez-la dans la liste **Métriques du rapport** et utilisez la fonction **Supprimer** pour la remettre dans la liste **Métriques provenant des sources**.
4. Répétez jusqu’à ce que vous ayez ajouté toutes les mesures que vous souhaitez inclure dans le rapport.

<div id="optional-customizing-metric-display-names" />

#### **[Facultatif] Personnaliser les noms d’affichage des métriques**

Par défaut, les noms des mesures s’affichent dans votre rapport exactement tels que dans les données d’attribution ou dans vos sources personnalisées. Si vous le souhaitez, vous pouvez personnaliser les noms des mesures de votre rapport.

**Pour personnaliser les noms d’affichage des métriques :**

1. Dans la liste **Métriques du rapport**, passez la souris sur le nom de la mesure dont vous souhaitez modifier le nom d’affichage.
2. Cliquez sur le bouton de modification ![edit_button.png](https://files.readme.io/4c3822661beac49fad247c7f5958a535e46031238e975a5323a5550722c89c8a-10753875375377.png) qui s’affiche à droite de la mesure.
3. Remplacez le nom par le nom d’affichage de la métrique à utiliser dans votre rapport (jusqu’à 50 caractères).
4. Cliquez sur **OK** pour enregistrer le nom d’affichage, ou sur **X** pour l’annuler.

<div id="optional-select-identifiers-to-count" />

#### **[Facultatif] Sélectionnez les identifiants à comptabiliser**

Par défaut, chaque ligne du rapport se termine par une colonne avec le nombre d’ID AppsFlyer regroupés dans les données de cette même ligne.

**Si vous souhaitez ajouter des colonnes pour avoir le décompte des autres identifiants de vos sources, procédez comme suit :**

1. Sélectionnez un ou plusieurs identifiants dans la liste des **Identifiants provenant des sources** (sur la gauche), puis utilisez le bouton **Ajouter** au milieu de l’écran pour les envoyer dans le **Décompte des identifiants**.
   * Vous pouvez utiliser la barre de recherche pour localiser les identifiants dans la liste.
2. Pour retirer un identifiant, sélectionnez-le dans la liste **Décompte des identifiants**, puis utilisez la fonction **Retirer** pour le remettre dans la liste des **Identifiants provenant des sources**.
3. Répétez jusqu’à ce que vous ayez ajouté tous les identifiants que vous souhaitez dénombrer dans le rapport.

</Accordion>

<div id="set-the-report-destination-and-save-the-report" />

<Accordion title="Définir la destination du rapport et l’enregistrer">

La DCR fournit des rapports aux services cloud que vous avez sélectionnés via <Anchor target="_blank" href="/marketers/fr/docs/data-locker-for-marketers">Data Locker AppsFlyer</Anchor>. Pour définir la destination d’un rapport vous devez donc sélectionner ou créer une connexion Data Locker.

* **Remarque :** Obtenir les rapports de la DCR ne nécessite pas d’abonnement premium à Data Locker. Si vous souhaitez recevoir d’autres rapports AppsFlyer via Data Locker, contactez votre CSM, ou envoyez un e-mail à [hello@appsflyer.com](mailto:hello@appsflyer.com).

**Pour définir la destination d’un rapport et l’enregistrer :**

1. Sélectionnez dans la liste l’une des connexions Data Locker disponibles dans votre compte AppsFlyer.
   * Si aucune connexion n’a été paramétrée dans votre compte :
     * Un nouvel onglet s’ouvrira dans votre navigateur (affichant la page AppsFlyer Data Locker)
     * Une boîte de dialogue **Nouvelle connexion** s’ouvrira. Veuillez suivre <Anchor target="_blank" href="/marketers/fr/docs/data-clean-room-working-with-connections#complete-the-connection-1">ces instructions</Anchor> pour créer la connexion.
   * Si vous avez déjà des connexions, mais que vous souhaitez en utiliser une nouvelle, cliquez sur le bouton![dcr_new_connection_data_locker_button.png](https://files.readme.io/9850a4b8ea4f40f6320903c545c51add7b90207538a27c83a3b02a41197ba567-14995870859281.png) :
     * Un nouvel onglet s’ouvrira dans votre navigateur (affichant la page AppsFlyer Data Locker)
     * Une boîte de dialogue **Nouvelle connexion** s’ouvrira. Veuillez suivre <Anchor target="_blank" href="/marketers/fr/docs/data-clean-room-working-with-connections#complete-the-connection-1">ces instructions</Anchor> pour créer la connexion.
   * Après avoir créé la connexion, revenez à l’onglet DCR de votre navigateur, puis sélectionnez la connexion que vous venez de créer dans la liste des connexions Data Locker.
2. Cliquez sur **Sauvegarder** pour enregistrer le rapport.
3. Le nouveau rapport s’affiche maintenant dans l’onglet **Rapports** de la **Data Clean Room.**

</Accordion>

<div id="when-does-the-report-run" />

## Quand le rapport est-il généré ?

Une fois qu’un rapport a été créé et enregistré, il s’exécute chaque fois que qu’une nouvelle version de n’importe quelle [source personnalisée qu’il utilise](/docs/data-clean-room-creating-attribution-data-reports#sources-personnalisées) est détectée :

* Pour les sources présentes dans **entrepôts de données** (BigQuery et Snowflake), la DCR décide que la nouvelle version d’une source a été créée lorsqu’elle détecte une nouvelle valeur dans <Anchor target="_blank" href="/marketers/fr/docs/data-clean-room-working-with-sources#table-columns">la colonne du tableau de la source</Anchor>.
  * **Attention !** Pour avoir la certitude que votre rapport est bien complet, pensez à alimenter le tableau de la source avec un ensemble complet de données à chaque fois que la valeur de la colonne est modifiée.
* Pour les sources situées dans des **compartiments de stockage sur le cloud** (Amazon S3 et GCS), la DCR décide que la nouvelle version d’une source a été créée lorsqu’elle détecte que <Anchor target="_blank" href="/marketers/fr/docs/data-clean-room-working-with-sources#mettre-à-jour-les-sources-pour-déclencher-lédition-des-rapports">l’importation d’une nouvelle version d’un fichier source</Anchor>, avec le dossier \_SUCCESS qui l’accompagne.

AppsFlyer recherche en continu les nouvelles versions des fichiers sources pour **le jour en cours et les 2 jours qui le précèdent.**

<div id="reference" />

## Référence

<div id="available-attribution-data-dimensions" />

<Accordion title="Dimensions des données d’attribution disponibles">

En plus des dimensions de vos sources personnalisées, les dimensions des données d'attribution suivantes peuvent servir dans le regroupement des rapports :

* media\_source *([inclus comme dimension de rapport par défaut](#sélection-des-dimensions-dun-rapport))*
* ad
* ad\_id
* ad\_type
* adset\_id
* adset\_name
* app\_id
* app\_version
* attributed\_touch\_type
* brand
* campaign
* campaign\_id
* channel
* city
* contributor\_1\_campaign¹
* contributor\_1\_engagement\_type¹
* contributor\_1\_match\_type¹
* contributor\_1\_media\_source¹
* contributor\_1\_partner¹
* contributor\_1\_touch\_type¹
* contributor\_2\_campaign¹
* contributor\_2\_engagement\_type¹
* contributor\_2\_match\_type¹
* contributor\_2\_media\_source¹
* contributor\_2\_partner¹
* contributor\_2\_touch\_type¹
* contributor\_3\_campaign¹
* contributor\_3\_engagement\_type¹
* contributor\_3\_match\_type¹
* contributor\_3\_media\_source¹
* contributor\_3\_partner¹
* contributor\_3\_touch\_type¹
* conversion\_type
* country
* customer\_id
* device\_type
* dma
* engagement\_type
* geo\_region
* keywords
* match\_type
* media\_source
* model
* original\_url
* partner
* platform
* site\_id

¹ *Pour les ré-engagements et les ré-attributions, les champs resteront vides dans le rapport.*

</Accordion>

<div data-zendesk-anchors="creating-an-attribution-data-report=cr%C3%A9er-un-rapport-de-donn%C3%A9es-dattribution h_01HA9W4BCJSS2803JHV9K5KVP8=cr%C3%A9er-un-rapport-de-donn%C3%A9es-dattribution h_01HA9W4BCJX9PJ2E4ADDC58GJ1=perform-preliminary-steps h_01HA9W4BCJNB64K3GZAKM7G0SS=select-sources attribution-data-sources=source-des-donn%C3%A9es-dattribution h_01HA9W4BCJD51WM7504F94009R=source-des-donn%C3%A9es-dattribution custom-sources=sources-personnalis%C3%A9es h_01HA9W4BCJNRBD1NSWAH92B85V=sources-personnalis%C3%A9es h_01HA9W4BCJW56NG637AZNP0DW0=join-sources what-is-a-key-identifier=quest-ce-quun-identifiant-de-cl%C3%A9- h_01HA9W4BCJ6A5EVFVR6G2SHEQD=quest-ce-quun-identifiant-de-cl%C3%A9- h_01HA9W4BCJ2GAZ96FHNN3HP6BY=attention- mapping-schemes-directindirect=sch%C3%A9mas-de-mappage-directindirect h_01HA9W4BCJ6ZT4DSE3J5364D2C=sch%C3%A9mas-de-mappage-directindirect h_01HA9W4BCJKA8AWQGEHGQ5JT4P=exemple h_01HA9W4BCJ6ZM47HQMARQ50ZQ1=determine-treatment-of-multiple-matching-events h_01HA9W4BCJE9ABACTWWTNJXVVQ=remarque matching-all-events=matcher-tous-les-%C3%A9v%C3%A9nements h_01HA9W4BCJ6FPCNP8K8D2CR1ST=matcher-tous-les-%C3%A9v%C3%A9nements matching-a-single-event=matcher-un-%C3%A9v%C3%A9nement-unique h_01HA9W4BCJ99Z4A16N05799VZS=matcher-un-%C3%A9v%C3%A9nement-unique h_01HA9W4BCKDVYTG08M2CWBWYC3=select-dimensions selecting-report-dimensions=s%C3%A9lection-des-dimensions-dun-rapport h_01HA9W4BCKWCDWB4W0HZM4Z6E7=s%C3%A9lection-des-dimensions-dun-rapport %5Boptional%5D-customizing-dimension-display-names=facultatif-personnaliser-les-noms-daffichage-des-dimensions h_01HA9W4BCKEW1Z25ZXS9EXZYSA=facultatif-personnaliser-les-noms-daffichage-des-dimensions preserving-privacy-while-grouping-by-dimension-regrouping=protection-de-la-confidentialit%C3%A9-lors-du-regroupement-par-dimension-regroupement h_01HA9W4BCKA4248PEYNWZS87EW=protection-de-la-confidentialit%C3%A9-lors-du-regroupement-par-dimension-regroupement h_01HA9W4BCK41W87486KG4RAAX8=exemple-de-regroupement %5Boptional%5D-managing-dimension-priority=facultatif-g%C3%A9rer-la-priorit%C3%A9-dune-dimension h_01HA9W4BCKHABH7K80DKAQDDTR=facultatif-g%C3%A9rer-la-priorit%C3%A9-dune-dimension h_01HA9W4BCK1G0A2HTYRDQTMF5B=select-metrics %5Boptional%5D-customizing-metric-display-names=facultatif-personnaliser-les-noms-daffichage-des-m%C3%A9triques h_01HA9W4BCKZTAP4AWMNJKEKX2E=facultatif-personnaliser-les-noms-daffichage-des-m%C3%A9triques %5Boptional%5D-select-identifiers-to-count=facultatif-s%C3%A9lectionnez-les-identifiants-%C3%A0-comptabiliser h_01HA9W4BCK5Y97RFYEMT24BABV=facultatif-s%C3%A9lectionnez-les-identifiants-%C3%A0-comptabiliser h_01HA9W4BCKE1P7TBJANN0PD03D=set-the-report-destination-and-save-the-report when-does-the-report-run=quand-le-rapport-est-il-g%C3%A9n%C3%A9r%C3%A9- h_01HA9W4BCK3GX1KMVAXN5ZKA3A=quand-le-rapport-est-il-g%C3%A9n%C3%A9r%C3%A9- reference=r%C3%A9f%C3%A9rence h_01HA9W4BCK0VHS90ZXX00BF80N=r%C3%A9f%C3%A9rence h_01HA9W4BCMAYC661HFNRY3HWY2=available-attribution-data-dimensions" />
