---
title: 'Data Clean Room : création de rapports d’événements in-app'
metadata:
  keywords:
    - Premium
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-inbar-agassi
    - Marketers
    - Data Clean Room
  created_at: '2022-09-22T12:03:40Z'
  edited_at: '2024-08-28T14:41:49Z'
  id: 9312610473233
  locale: fr
  section: Data Clean Room
  section_id: 4591191779217
  url: https://support.appsflyer.com/hc/fr/articles/9312610473233
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En bref :** Créer des rapports d’événements in-app pour se concentrer sur l’activité de l’utilisateur après l’installation d’une app. Extrayez des paramètres d’événement spécifiques à partir des données brutes de vos événements in-app, associez éventuellement les données à des sources personnalisées, puis traitez-les et présentez-les sous forme agrégée.

<div id="creating-an-in-app-event-report" />

## Création d’un rapport d’événement in-app

**Pour créer un rapport d’événements in-app, suivez les étapes détaillées dans les onglets ci-dessous.**

**Remarque :** Ces étapes sont divisées en onglets pour faciliter la lecture. Toutes les étapes doivent être franchies afin de créer le rapport. *(Certaines étapes, comme indiqué, ne sont pas pertinentes pour les rapports qui n’utilisent pas de sources personnalisées.)*

<div id="perform-preliminary-steps" />

<Accordion title="Étapes préliminaires">

1. Allez à la page **Rapports** de l’onglet **DCR.**
2. Cliquez sur l’icône **+ Nouveau rapport** bouton.
3. Choisissez **Événements in-app**comme type de données source, puis cliquez sur **Prochain** dans le coin inférieur droit de l’écran.
4. Entrez un nom pour le rapport.
   * Il peut s’agir de n’importe quel nom qui vous aidera à identifier le rapport dans la plateforme DCR.
   * **Attention !** Assurez-vous que le nom du rapport est différent de tous les autres rapports de votre compte, sinon vous ne pourrez pas [Enregistrer le rapport](/docs/data-clean-room-creating-in-app-event-reports#configure-report-settings-and-save-the-report).
   * Exigences relatives au nom du rapport :
     * Longueur: 2-80 caractères.
     * Caractères valides :
       * lettres **(A-Z, a-z)**
       * un chiffre **(0-9)** *ne peuvent pas être le premier caractère d'un nom*
       * un trait d’union (-), *ne peut pas être le premier caractère d’un prénom*
     * Caractères non valides :
       * espaces
       * tous les autres symboles ou caractères spéciaux

</Accordion>

<div id="select-sources" />

<Accordion title="Sélectionner les sources">

Spécifiez les données sources à utiliser pour le rapport :

<div id="in-app-event-sources" />

#### **Sources d'événements in-app**

* **Apps :** Sélectionnez une ou plusieurs apps dans votre compte AppsFlyer.
* **Période :** Sélectionnez le nombre de jours de données historiques pendant lesquels vous souhaitez que la DCR recherche les événements in-app (de 1 à 30 jours).
* **Évènements :** Sélectionnez un ou plusieurs événements in-app à inclure dans le rapport.
  * Les événements disponibles incluent tous les événements in-app **à partir des apps sélectionnées** qui ont été configurés pour signaler des données à AppsFlyer via le SDK ou l’API de serveur à serveur (S2S).
* **Types de sources :** Sélectionnez un ou plusieurs types de données d’événement in-app : 

| Installations | Événements in-app liés aux attributions d’installation<ul><li>Une installation est enregistrée lorsqu’un utilisateur télécharge, installe et lance une app mobile.</li></ul> |
| --- | --- |
| Réengagements | Événements in-app liés aux réengagements<ul><li>Un réengagement est enregistré lorsqu’un utilisateur inactif d’une app spécifique s’engage dans une campagne de retargeting pour l’app et la lance par la suite.</li></ul> |
| Réattributions | Événements in-app liés aux réattributions<ul><li>Une réattribution est enregistrée lorsqu’un ancien utilisateur d’une app spécifique (qui l’avait désinstallée) s’engage dans une campagne de retargeting pour cette app et la réinstalle par la suite.</li></ul> |

<div id="data-sources" />

#### **Sources des données**

1. [Facultatif] Ajoutez d’autres sources à utiliser dans le rapport. Lorsque vous choisissez d’ajouter d’autres sources, notez la différence significative entre les rapports qui **utilisent** et qui **n’utilisent pas** des sources personnalisées.
   * Un rapport qui **n’utilise pas** de sources personnalisées extrait des paramètres et des valeurs d’événement spécifiques à partir des données brutes de l'événement in-app.
   * Un rapport qui **utilise**des sources personnalisées extrait des paramètres et des valeurs d'événements spécifiques des données brutes des événements in-app, puis fait correspondre ces données avec des données au niveau de l'utilisateur provenant de vos sources personnalisées (telles que les données de vos systèmes de BI ou de CRM).
2. Effectuez les étapes suivantes selon que votre rapport utilise ou non des sources personnalisées :
   * Si votre rapport **n’utilise pas** de sources personnalisées, passez à **[Sélectionner les dimensions](/docs/data-clean-room-creating-in-app-event-reports#select-dimensions),** puis poursuivez ensuite les étapes dans tous les onglets restants.
   * Si votre rapport **utilise** des sources personnalisées, poursuivez les étapes de la section [**Joindre des sources**](#join-sources-only-for-reports-containing-custom-sources) (immédiatement après) et de tous les autres onglets.

</Accordion>

L’étape suivante est pertinente **uniquement pour les rapports qui utilisent des sources personnalisées.**

<div id="join-sources-only-for-reports-containing-custom-sources" />

<Accordion title="Joindre des sources (uniquement pour les rapports contenant des sources personnalisées)">

Afin de faire correspondre les données entre les sources, chacune des sources **personnalisées** utilisées dans le rapport doivent inclure un <Anchor target="_blank" href="/marketers/fr/docs/data-clean-room-setting-up-cloud-services">identifiant</Anchor> mappé à un **identifiant de clé** dans les données d’événement in-app.

* Les rapports d’événements in-app comprennent **tout** les événements sélectionnés correspondant à l’identifiant de clé au cours de la période sélectionnée.

<div id="what-is-a-key-identifier" />

#### **Qu’est-ce qu’un identifiant de clé ?**

Vous pouvez mapper l’un de ces identifiants de données d’événement in-app en tant qu’**identifiant de clé :**

* **ID AppsFlyer (af\_id) :** un identifiant d'app unique généré par AppsFlyer lors de l'installation –
  * Cet ID s'affiche dans tous les événements enregistrés par AppsFlyer.
  * Un nouvel ID AppsFlyer est généré si une app est supprimée puis réinstallée.
* **ID utilisateur client (CUID) :** un identifiant utilisateur unique généralement généré et défini par le propriétaire de l’app au moment de l’inscription de l’utilisateur.
  * L’utilisation du CUID pour mapper des données nécessite que votre app soit configurée pour <Anchor target="_blank" href="/marketers/fr/docs/customer-user-id-field-cuid">envoyer le CUID à AppsFlyer</Anchor> via le SDK ou l’API de serveur à serveur (S2S).

<div id="important" />

> 🚧 **Attention !**
>
> Toutes les sources média ne permettent pas la correspondance à l’aide du CUID. Il est fortement recommandé d’utiliser l’ID AppsFlyer.

<div id="mapping-schemes-directindirect" />

#### **Schémas de mappage (direct/indirect)**

Si le rapport comprend plusieurs sources personnalisées, une seule d’entre elles doit être mappée **directement** à un identifiant de clé d’événement in-app. D’autres sources personnalisées peuvent être mappées soit **directement ou indirectement,** comme illustré dans l’exemple suivant :

<div id="example" />

> 📄 **Exemple**
>
> ![dcr_mapping_identifiers_in-app events.png](https://files.readme.io/73d0e929663bda4e6f142c64d0228fdf1eeec3b02ef1560f6f03f2a089d00664-9969546429713.png)
>
> Dans le scénario illustré ci-dessus :
>
> * L’identifiant de source personnalisée #1 **AF** est mappé directement à l’identifiant de clé d’événement in-app **af\_id.**
> * La source personnalisée #2 est mappée indirectement : **user\_code** --> **AF** --> **af\_id.**
> * La source personnalisée #3 est mappée indirectement (via une chaîne plus longue) :
>   **user\_id** --> **user\_code** --> **AF** --> **af\_id.**
> * L’**ID** de source personnalisée #4 est mappé directement à l’identifiant de clé d’événement in-app **af\_id.**
>   * Notez qu’il aurait pu être mappé indirectement à la place (via l’identifiant de source #3 personnalisé **user\_id**), mais l’une ou l’autre option fonctionne correctement.
>
> ✓ Ce schéma de mappage permet de faire correspondre les données entre toutes les sources, car chaque source personnalisée est mappée directement ou indirectement à l’identifiant de clé d’événement in-app **af\_id.**

</Accordion>

Les autres onglets sont pertinents pour **tous les rapports d’événements in-app,** qu’ils incluent ou non des sources personnalisées.

<div id="select-dimensions" />

<Accordion title="Sélectionner les dimensions">

N’oubliez pas que les données au niveau de l’utilisateur ne peuvent pas être signalées par le DCR. Au lieu de cela, elles vous fournissent les informations décisionnelles dont vous avez besoin en agrégeant (ou en regroupant) les données selon les dimensions que vous choisissez.

Une dimension est généralement un attribut par lequel vous catégorisez les utilisateurs de l’app (par exemple, géo, date d’installation, campagne, etc.)

<div id="extracting-dimensions-from-event_value" />

#### **Extraction de dimensions à partir de event\_value**

Lorsque des événements in-app sont signalés à AppsFlyer via le SDK ou l’API S2S, une grande partie des données brutes est contenue dans un seul champ appelé **event\_value.** Ce champ de données structurées inclut tous les paramètres d’événement in-app spécifiques qui ont été configurés pour les événements que vos apps envoient à AppsFlyer.

L’un des principaux avantages des rapports d’événements in-app est qu’ils vous permettent d’extraire des paramètres spécifiques et leurs valeurs de la **event\_value** pour les événements que vous choisissez.

**Pour extraire des dimensions du champ event\_value à utiliser dans les rapports DCR :**

1. Dans la liste **Dimensions des sources**, cliquez sur le bouton <Image alt="extract_dimension_button.png" src="https://files.readme.io/c238da4a1d2a15fe2249070747fa6247db63ab4129b1c72804b84550675214f3-10754426767761.png" width="123px" />.

   La fenêtre **Extraire le champ d’event\_value** s’ouvre.
2. Dans le **Champ de rapport** , entrez le nom de la dimension extraite tel que vous souhaitez qu’elle apparaisse dans votre rapport.
3. De la liste **Event\_value parameter**, sélectionnez le paramètre d’événement in-app qui doit être mappé par défaut au champ de rapport (dimension) que vous avez défini à l’étape 2.
   * Les paramètres disponibles incluent ceux qui ont été configurés dans le **événements in-app sélectionnés** **dans les apps sélectionnées**.
4. Il se peut que le mappage par défaut diffère selon l’app et/ou l’événement. Si tel est le cas :
   1. Cliquez sur le bouton **Ajouter une exception**
   2. Sélectionnez l’app et l’événement pour lesquels le champ de rapport doit être mappé différemment.
   3. Sélectionnez le paramètre d’événement in-app qui doit être mappé au champ de rapport pour cette combinaison app/évènement.
   4. Suivez ces étapes pour autant d’exceptions que vous souhaitez configurer.
5. Lorsque vous avez terminé de configurer le mappage de la dimension extraite, cliquez sur **Enregistrer et ajouter un autre** pour extraire une autre dimension du champ event\_value ou **Sauvegarder** pour revenir à l’écran principal.

**Pour modifier les dimension extraites :**

1. Dans les **Dimensions des sources** ou les **Dimensions du rapport**, passez la souris sur le nom de la dimension que vous souhaitez modifier.
2. Cliquez sur l’icône <Image alt="more_options_button.png" src="https://files.readme.io/d52908bc376b10d60f12ec401b8ba13adf1946ca4ef27cb7a588fae33a603384-10755347815441.png" width="21px" /> qui s’affiche à droite de la dimension.
3. Choisir **Modifier le champ extrait.**
4. Apportez des modifications au nom du **Champ de rapport** et/ou au mappage de paramètres si nécessaire.
5. Cliquez sur **Sauvegarder** pour enregistrer vos modifications.

**Pour supprimer les dimensions extraites :**

1. Dans les **Dimensions des sources** ou les **Dimensions du rapport**, passez la souris sur le nom de la dimension que vous souhaitez supprimer.
2. Cliquez sur l’icône <Image alt="more_options_button.png" src="https://files.readme.io/d52908bc376b10d60f12ec401b8ba13adf1946ca4ef27cb7a588fae33a603384-10755347815441.png" width="21px" /> qui s’affiche à droite de la dimension.
3. Choisissez **Supprimer le champ.**
   * **Attention !** Si vous supprimez un champ extrait de la **Dimensions du rapport**, cela supprimera la définition du champ extrait. Si vous souhaitez supprimer le champ du rapport tout en conservant sa définition, sélectionnez-le et utilisez le bouton **Enlever** à la place.

<div id="selecting-report-dimensions" />

#### **Sélection des dimensions d’un rapport**

Les dimensions du rapport d’événement in-app peuvent inclure :

* Les dimensions que vous avez extraites de event\_value
* [Les dimensions d’événement in-app par défaut](/docs/data-clean-room-creating-in-app-event-reports#default-inapp-event-dimensions)
* Tout champ des sources personnalisées de l’état qui a été <Anchor target="_blank" href="/marketers/fr/docs/data-clean-room-working-with-sources#3-define-the-source-structure">catégorisé en tant que dimension</Anchor> (le cas échéant)

**Pour sélectionner les dimensions à inclure dans votre rapport :**

1. Sélectionnez une ou plusieurs dimensions dans les **dimensions des sources** sur la gauche et utilisez le bouton **Ajouter** au milieu de l’écran pour les ajouter à la liste des **dimensions du rapport.**
   * Vous pouvez utiliser la barre de recherche pour rechercher des dimensions dans les listes.
2. Pour supprimer une dimension, sélectionnez-la dans les **dimensions du rapport** et utilisez la fonction **Supprimer** pour la renvoyer à la liste des **dimensions des sources**.
3. Répétez ce processus jusqu’à ce que vous ayez ajouté chaque dimension que vous souhaitez inclure dans le rapport.

**Remarque :** Par défaut, tous les rapports sont regroupés par la dimension d’événement in-app **media\_source.** Si vous ne souhaitez pas utiliser cette dimension dans votre rapport, vous pouvez la supprimer de la liste des **dimensions du rapport**.

<div id="optional-customizing-dimension-display-names" />

#### **[Facultatif] Personnalisation des noms d’affichage des dimensions**

Par défaut, les noms des dimensions s’affichent dans votre rapport exactement comme ils sont nommés dans les données d’événement in-app ou dans vos sources personnalisées. Si vous le souhaitez, vous pouvez personnaliser les noms de dimension de votre rapport.

**Pour personnaliser les noms d’affichage des dimensions :**

1. Dans la liste des **dimensions du rapport**, passez la souris sur le nom de la dimension dont vous souhaitez modifier le nom d’affichage.
2. Cliquez sur le bouton de modification ![edit_button.png](https://files.readme.io/f4ef4722724c776ce4034ab07492a4ac80825f6f15350911c1cbb51ac4843092-10754262613649.png) qui s’affiche à droite de la dimension.
3. Remplacez le nom par le nom d’affichage de la dimension à utiliser dans votre rapport (jusqu’à 50 caractères).
4. Cliquez sur **OK** pour enregistrer le nom d’affichage, ou **X** pour l’annuler.

**Remarque :** Si vous souhaitez changer le nom d’une **dimension extraite**, suivez les étapes de modification des dimensions extraites (ci-dessus).

<div id="preserving-privacy-while-grouping-by-dimension-regrouping" />

#### **Préservation de la confidentialité lors du regroupement par dimension (regroupement)**

En fonction de la taille de votre ensemble de données, du nombre de dimensions que vous choisissez et d’autres facteurs, il est possible qu’un rapport comprenne un ou plusieurs groupes contenant trop peu d’utilisateurs pour permettre la création de rapports. Si les données étaient déclarées de cette façon, cela enfreindrait les restrictions contre la fourniture de données au niveau de l’utilisateur.

Toutefois, au lieu de supprimer ou de masquer complètement les données du rapport, le DCR utilise un **mécanisme de regroupement** pour fournir autant de détails que possible tout en préservant la confidentialité de l’utilisateur.

<div id="regrouping-example" />

> 📄 **Exemple de regroupement**
>
> Supposons que vous ayez configuré un rapport selon les dimensions suivantes (dans l’ordre) :
>
> * **Dimensions de l’événement in-app :**
>   * source média
>   * campagne
>   * adset\_name
>   * ad\_id
> * **Dimensions de la source personnalisée :**
>   * user\_type
>
> **Avant le regroupement**
>
> Après une analyse initiale des données, le DCR détermine que les données se répartissent comme suit :
>
>
>
> | source  <br />média | campagne | adset  <br />nom | publicité  <br />id | utilisateur  <br />Type | rév  <br />J0 | rév  <br />J7 | décompte | rapportable? |
> | --- | --- | --- | --- | --- | --- | --- | --- | --- |
> | media\_source | UA\_100 | vert | kjh867 | acheteur | 1 | 4 | 120 | ✓ |
> | media\_source | UA\_101 | vert | jkj987 | ultra | 2 | 23 | 220 | ✓ |
> | media\_source | UA\_200 | vert | lkh123 | demandeur | 6 | 7 | X | **X** |
> | media\_source | UA\_200 | vert | ilk945 | demandeur | 3 | 21 | X | **X** |
> | media\_source | UA\_200 | vert | plm654 | demandeur | 8 | 17 | X | **X** |
>
>
>
> Dans l’état actuel des choses, les 3 dernières rangées ne sont pas signalées car il y a trop peu d’utilisateurs dans chacune. (Cette source média nécessite un minimum de **y** utilisateurs afin d’être déclarable. Ici, nous n’avons que **x**.)
>
> Selon la logique de regroupement, le DCR « élimine » d’abord la dernière dimension d’événement in-app listée (dans ce cas, **ad\_id**). Il analyse ensuite à nouveau les données pour voir quelles lignes doivent être incluses dans le rapport.
>
> **Après le regroupement**
>
> Après l’application de la logique de regroupement, le rapport s’affiche comme suit :
>
>
>
> | source  <br />média | campagne | adset  <br />nom | publicité  <br />id | utilisateur  <br />Type | rév  <br />J0 | rév  <br />J7 | décompte | rapportable? |
> | --- | --- | --- | --- | --- | --- | --- | --- | --- |
> | media\_source | UA\_100 | vert | kjh867 | acheteur | 1 | 4 | 120 | ✓ |
> | media\_source | UA\_101 | vert | jkj987 | ultra | 2 | 23 | 220 | ✓ |
> | media\_source | UA\_200 | vert | RESTREINT | demandeur | 17 | 45 | y (x+x+x) | ✓ |
>
>
>
> **Résultats :**
>
> * La dernière ligne combine maintenant les données qui se trouvaient auparavant sur 3 lignes. Maintenant, la ligne combinée a un nombre d’utilisateurs égal à **y** et peut être signalé.
> * La dimension qui a été éliminée est désormais signalée comme RESTREINTE.
> * S’il y avait encore eu des rangées non signalées (moins de **y** utilisateurs), le DCR continuerait d’analyser les données sur une base itérative, en éliminant une dimension après l’autre jusqu’à ce qu’il :
>   * puisse signaler toutes les rangées ; ou
>   * n’ait plus de dimensions d’événement in-app à éliminer.
>
> **Remarque :** Par défaut, le DCR applique le regroupement uniquement aux **[Dimensions d’événement in-app par défaut](/docs/data-clean-room-creating-in-app-event-reports#default-inapp-event-dimensions)** (ne pas extraire les dimensions d’événement in-app ou les dimensions de source personnalisées). Si les données regroupées par une dimension d’événement in-app par défaut entraînent une ligne contenant moins de **y** utilisateurs, les données de cette ligne seront signalées comme RESTREINTES.
>
> * *Voir ci-dessous pour une option avancée que vous pouvez utiliser pour appliquer le regroupement aux dimensions source personnalisées.*

<div id="optional-managing-dimension-priority" />

#### **[Facultatif] Gestion de la priorité de dimension**

Par défaut, les dimensions d’événement in-app sont éliminées dans l’ordre inverse de l’ordre dans lequel elles apparaissent dans la liste des **dimensions du rapport**. Toutefois, vous pouvez modifier la séquence par défaut et/ou appliquer le regroupement aux dimensions source personnalisées sélectionnées (le cas échéant) afin de conserver les dimensions les plus importantes pour vous.

**Pour modifier l’ordre dans lequel les dimensions sont éliminées :**

1. Cliquez sur le bouton **Gérer la priorité des dimensions**.
2. Sélectionnez une dimension et faites-la glisser à l’emplacement souhaité dans la liste (ou utilisez les boutons fléchés à droite pour la déplacer).
   * La dimension étiquetée comme **Priorité** (en haut de la liste) signifie qu’elle sera la dernière à être éliminée si un regroupement est nécessaire.
3. [Facultatif] Pour appliquer le regroupement aux dimensions de source personnalisées (pour les rapports utilisant des sources personnalisées) :
   1. Cliquez sur **Utiliser les options avancées pour affiner le regroupement**
   2. Sélectionnez les dimensions source personnalisées auxquelles vous souhaitez appliquer le regroupement.
   3. Les dimensions sélectionnées sont ajoutées à la liste **Gérer la priorité des dimensions**.
      * Par défaut, ces dimensions sont ajoutées au bas de la liste, comme **Priorité la plus basse** pour le regroupement. Toutefois, vous pouvez les réorganiser comme les dimensions d’événement in-app, comme décrit ci-dessus.
4. Cliquez sur **OK** pour enregistrer vos modifications.
   * La liste des **dimensions du rapport** sur l’écran principal reste dans son ordre d’origine, mais l’ordre révisé a été enregistré. (Cliquez à nouveau sur le bouton **Gérer la priorité des dimensions** si vous souhaitez revoir ou modifier votre sélection.)

</Accordion>

<div id="select-metrics" />

<Accordion title="Sélectionner des indicateurs">

Les métriques sont les données numériques que vous avez collectées concernant un utilisateur d’app (par exemple, le chiffre d’affaires, le nombre d’ouvertures d’apps, la LTV, etc.) et peuvent être n’importe quel champ de données numériques de vos sources que vous avez classé en tant que métrique.

<div id="extracting-metrics-from-event_value" />

#### **Extraction de métriques à partir de event\_value**

Tout comme vous pouvez le faire pour [Dimensions du rapport](/docs/data-clean-room-creating-in-app-event-reports#select-dimensions), vous pouvez extraire les paramètres d’événement in-app à partir du champ **event\_value** pour les utiliser comme mesures dans vos rapports.

**Pour extraire des dimensions du champ event\_value à utiliser dans les rapports DCR :**

1. Dans la liste **Métriques provenant des sources**, cliquez sur le bouton <Image alt="extract_metric_button.png" src="https://files.readme.io/93ca5970968816d452331df4ce5ff4cfb678cbb24f65eb99fe01bd3bb3016959-10755235273233.png" width="102px" /> bouton.

   La fenêtre **Extraire le champ d’event\_value** s’ouvre.
2. Dans le **Champ de rapport**, entrez le nom de la mesure extraite tel que vous souhaitez qu’elle apparaisse dans votre rapport.
3. Dans la liste **Event\_value parameter**, sélectionnez le paramètre d’événement in-app qui doit être mappé par défaut au champ de rapport (métrique) que vous avez défini à l’étape 2.
   * Les paramètres disponibles incluent ceux qui ont été configurés dans les **événements in-app sélectionnés** **dans les apps sélectionnées**.
4. Il se peut que le mappage par défaut diffère selon l’app et/ou l’événement. Si tel est le cas :
   1. Cliquez sur le bouton **Ajouter une exception**
   2. Sélectionnez l’app et l’événement pour lesquels le champ de rapport doit être mappé différemment.
   3. Sélectionnez le paramètre d’événement in-app qui doit être mappé au champ de rapport pour cette combinaison app/évènement.
   4. Suivez ces étapes pour autant d’exceptions que vous souhaitez configurer.
5. Lorsque vous avez terminé de configurer le mappage de la métrique extraite, cliquez sur **Enregistrer et ajouter autre** pour extraire une autre métrique du champ event\_value ou **Sauvegarder** pour revenir à l’écran principal.

**Pour modifier les métriques extraites :**

1. Dans la liste **Métriques des sources** ou**Métriques du rapport**, passez la souris sur le nom de la dimension que vous souhaitez modifier.
2. Cliquez sur l’icône <Image alt="more_options_button.png" src="https://files.readme.io/d52908bc376b10d60f12ec401b8ba13adf1946ca4ef27cb7a588fae33a603384-10755347815441.png" width="21px" /> qui s’affiche à droite de la métrique.
3. Choisir **Modifier le champ extrait.**
4. Apportez des modifications au nom du **Champ de rapport** et/ou au mappage de paramètres si nécessaire.
5. Cliquez sur **Sauvegarder** pour enregistrer vos modifications.

**Pour supprimer les métriques extraites :**

1. Dans la liste **Métriques des sources** ou **Métriques du rapport**, passez la souris sur le nom de la métrique que vous souhaitez supprimer.
2. Cliquez sur l’icône <Image alt="more_options_button.png" src="https://files.readme.io/d52908bc376b10d60f12ec401b8ba13adf1946ca4ef27cb7a588fae33a603384-10755347815441.png" width="21px" /> qui s’affiche à droite de la métrique.
3. Choisissez **Supprimer le champ.**
   * **Attention !** Si vous supprimez un champ extrait de la liste des **métriques du rapport**, cela supprimera la définition du champ extrait. Si vous souhaitez supprimer le champ du rapport tout en conservant sa définition, sélectionnez-le et utilisez le bouton **Supprimer** à la place.

<div id="select-report-metrics" />

#### **Sélectionner les statistiques du rapport**

**Pour sélectionner les statistiques à inclure dans votre rapport :**

1. Sélectionnez une ou plusieurs mesures dans la liste **Métriques provenant des sources** sur la gauche et utilisez le bouton **Ajouter** au milieu de l’écran pour les ajouter à la liste des **métriques du rapport.**
   * Vous pouvez utiliser la barre de recherche pour rechercher des statistiques dans les listes.
2. Pour chaque métrique de la liste **Métriques du rapport**, indiquez si vous souhaitez que les données soient signalées comme suit :
   * une somme de valeurs numériques ; ou
   * un décompte de valeurs distinctes
3. Pour supprimer une métrique, sélectionnez-la dans la liste **Statistiques du rapport** et utilisez la fonction **Supprimer** pour la renvoyer à la liste **Métriques provenant des sources**.
4. Répétez ce processus jusqu’à ce que vous ayez ajouté chaque mesure que vous souhaitez inclure dans le rapport.

<div id="optional-customizing-metric-display-names" />

#### **[Facultatif] Personnalisation des noms d’affichage des métriques**

Par défaut, les noms des métriques s’affichent dans votre rapport exactement comme ils sont nommés dans les données d’événement in-app ou dans vos sources personnalisées. Si vous le souhaitez, vous pouvez personnaliser les noms des métriques de votre rapport.

**Pour personnaliser les noms d’affichage des métriques :**

1. Dans la liste **Métriques du rapport**, passez la souris sur le nom de la métrique dont vous souhaitez modifier le nom d’affichage.
2. Cliquez sur le bouton de modification ![edit_button.png](https://files.readme.io/f4ef4722724c776ce4034ab07492a4ac80825f6f15350911c1cbb51ac4843092-10754262613649.png) qui s’affiche à droite de la métrique.
3. Remplacez le nom par le nom d’affichage de la métrique à utiliser dans votre rapport (jusqu’à 50 caractères).
4. Cliquez sur **OK** pour enregistrer le nom d’affichage, ou **X** pour l’annuler.

**Remarque :** Si vous souhaitez changer le nom d’une **métrique extraite**, suivez les étapes de modification des métriques extraites (ci-dessus).

<div id="optional-select-identifiers-to-count" />

#### **[Facultatif] Sélectionnez les identifiants à compter**

Par défaut, chaque ligne du rapport se termine par une colonne contenant le nombre d’ID AppsFlyer distincts regroupés dans les données de cette ligne.

**Si vous souhaitez ajouter des colonnes pour les nombres distincts d’autres identifiants de vos sources, procédez comme suit :**

1. Sélectionnez un ou plusieurs identifiants dans la section **Identifiants provenant des sources** sur la gauche et utilisez le bouton **Ajouter** au milieu de l’écran pour les ajouter à la liste des **Identifiants de comptage distincts**.
   * Vous pouvez utiliser la barre de recherche pour rechercher des identifiants dans les listes.
2. Pour supprimer un identifiant, sélectionnez-le dans la section **identifiants de comptage distincts**et utilisez la fonction **Supprimer** pour le renvoyer à la liste des **identifiants provenant des sources**.
3. Répétez ce processus jusqu’à ce que vous ayez ajouté chaque identifiant que vous souhaitez comptabiliser dans le rapport.

</Accordion>

<div id="configure-report-settings-and-save-the-report" />

<Accordion title="Configurer les paramètres du rapport et l’enregistrer">

<div id="schedule-only-for-reports-without-custom-sources" />

#### **Planification (uniquement pour les rapports sans sources personnalisées)**

Les rapports sans sources personnalisées sont exécutés selon la planification que vous définissez.

**Pour définir la planification du rapport :**

1. Indiquez si vous souhaitez exécuter le rapport quotidiennement ou un ou plusieurs jours par semaine.
2. Sélectionnez l’heure à laquelle vous souhaitez exécuter le rapport (le fuseau horaire est UTC).

<div id="important-1" />

> 🚧 **Attention !**
>
> Les options de planification sont désactivées pour les rapports qui utilisent des sources personnalisées. Ce type de rapport s’exécute chaque fois que les nouvelles versions de tous les <Anchor target="_blank" href="/marketers/fr/docs/data-clean-room-creating-attribution-data-reports#sources-personnalisées">sources personnalisées qu’il utilise</Anchor> sont détectées :
>
> * Pour les sources situées dans **entrepôts de données** (BigQuery et Snowflake), le DCR reconnaît qu’une nouvelle version d’une source a été créée lorsqu’il détecte une nouvelle valeur dans <Anchor target="_blank" href="/marketers/fr/docs/data-clean-room-working-with-sources#table-columns">la colonne `v` du tableau source</Anchor>.
>   * **Attention !** Pour garantir que votre rapport est bien complet, pensez à alimenter le tableau source avec un ensemble complet de données à chaque fois que la valeur de la colonne est modifiée.
> * Pour les sources situées dans des **compartiments de stockage cloud** (Amazon S3 et GCS), le DCR reconnaît qu’une nouvelle version d’une source a été créée lorsqu’il détecte qu’une <Anchor target="_blank" href="/marketers/fr/docs/data-clean-room-working-with-sources#mettre-à-jour-les-sources-pour-déclencher-lédition-des-rapports">nouvelle version d’un fichier source a été téléchargée</Anchor> ainsi que le dossier \_SUCCESS qui l’accompagne.
>
> AppsFlyer recherche en permanence les nouvelles versions des fichiers sources pour **le jour en cours et les 2 jours précédents.**

<div id="report-destination" />

#### **Destination du rapport**

Le DCR fournit des rapports aux services cloud que vous avez sélectionnés à l’aide de <Anchor target="_blank" href="/marketers/fr/docs/data-locker-for-marketers">Data Locker AppsFlyer</Anchor>. Par conséquent, la spécification de la destination du rapport implique la sélection ou la création d’une connexion Data Locker.

* **Remarque :** La réception de rapports DCR ne nécessite pas d’abonnement premium à Data Locker. Si vous souhaitez recevoir d’autres rapports AppsFlyer via Data Locker, contactez votre CSM ou envoyez un e-mail à [hello@appsflyer.com](mailto:hello@appsflyer.com).

**Pour définir la destination du rapport et l’enregistrer :**

1. Sélectionnez dans la liste des connexions Data Locker disponibles dans votre compte AppsFlyer.
   * Si aucune connexion n’est définie dans votre compte :
     * Un nouvel onglet s’ouvrira dans votre navigateur (affichant la page AppsFlyer Data Locker)
     * Une boîte de dialogue **Nouvelle connexion** s’ouvrira. Suivez <Anchor target="_blank" href="/marketers/fr/docs/data-clean-room-working-with-connections#complete-the-connection-1">ces instructions</Anchor> pour créer la connexion.
   * Si vous avez déjà des connexions mais que vous souhaitez en utiliser une nouvelle, cliquez sur le bouton![dcr_new_connection_data_locker_button.png](https://files.readme.io/21fda59ab30e85ab4ba8b4b5920c901e8bcdedadad393a2205bb34e839f9c8db-16684568466961.png) :
     * Un nouvel onglet s’ouvrira dans votre navigateur (affichant la page AppsFlyer Data Locker)
     * Une boîte de dialogue **Nouvelle connexion** s’ouvrira. Suivez <Anchor target="_blank" href="/marketers/fr/docs/data-clean-room-working-with-connections#complete-the-connection-1">ces instructions</Anchor> pour créer la connexion.
   * Après avoir créé la connexion, revenez à l’onglet DCR de votre navigateur et sélectionnez la connexion nouvellement créée dans la liste des connexions Data Locker.
2. Cliquez sur **Sauvegarder** pour enregistrer le rapport.
3. Le nouveau rapport s’affiche maintenant dans l’onglet **Rapports** de la **Data Clean Room.**

</Accordion>

<div id="reference" />

## Référence

<div id="default-inapp-event-dimensions" />

<Accordion title="Les dimensions d’événement in-app par défaut">

En plus des dimensions extraites de **event\_value** et de vos sources personnalisées (le cas échéant), les dimensions d’événement in-app suivantes peuvent être utilisées pour regrouper des rapports :

* media\_source *([inclus en tant que dimension de rapport par défaut](#sélection-des-dimensions-dun-rapport))*
* publicité
* ad\_id
* ad\_type
* adset\_id
* adset\_name
* app\_id
* app\_version
* attributed\_touch\_type
* marque
* campagne
* campaign\_id
* canal
* ville
* conversion\_type
* country
* device\_type
* dma
* Type d’engagement
* event\_name
* event\_revenue\_currency
* geo\_region
* is\_attributed
* Mots-clés
* match\_type
* modèle
* partenaire
* platform
* site\_id

</Accordion>

<div id="default-inapp-event-metrics" />

<Accordion title="Métriques d’événement in-app par défaut">

En plus des métriques extraites de **event\_value** et des métriques provenant de vos sources personnalisées (le cas échéant), les métriques d’événement in-app suivantes peuvent être incluses dans les rapports :

* event\_revenue
* event\_revenue\_u\_s\_d

</Accordion>

<div data-zendesk-anchors="creating-an-inapp-event-report=cr%C3%A9ation-dun-rapport-d%C3%A9v%C3%A9nement-in-app h_01HA9W7NP4CR9CVXY9CXENYSPF=cr%C3%A9ation-dun-rapport-d%C3%A9v%C3%A9nement-in-app h_01HA9W7NP4B55Y2SB6ADKE06JV=perform-preliminary-steps h_01HA9W7NP4A7YK5JFYNFXFY6ZJ=select-sources inapp-event-sources=sources-d%C3%A9v%C3%A9nements-in-app h_01HA9W7NP4G0S2TQT9W2RK1QBA=sources-d%C3%A9v%C3%A9nements-in-app custom-sources=sources-des-donn%C3%A9es h_01HA9W7NP46D57Q7H8611K4KBB=sources-des-donn%C3%A9es h_01HA9W7NP4K2055TXTE98HWTAW=join-sources-only-for-reports-containing-custom-sources what-is-a-key-identifier=quest-ce-quun-identifiant-de-cl%C3%A9- h_01HA9W7NP4WTBJ83MY73JQ2ESH=quest-ce-quun-identifiant-de-cl%C3%A9- h_01HA9W7NP5N8W4X8H1WRN1183Z=attention- mapping-schemes-directindirect=sch%C3%A9mas-de-mappage-directindirect h_01HA9W7NP51HWA36BBP1JC3HMW=sch%C3%A9mas-de-mappage-directindirect h_01HA9W7NP5V1SV5PGF277G5P6T=exemple h_01HA9W7NP56M09TF9CB7FCBPBR=select-dimensions extracting-dimensions-from-event_value=extraction-de-dimensions-%C3%A0-partir-de-event_value h_01HA9W7NP5BV7GJXMEMS57HNJ9=extraction-de-dimensions-%C3%A0-partir-de-event_value selecting-report-dimensions=s%C3%A9lection-des-dimensions-dun-rapport h_01HA9W7NP5S6EWDE38Q6T42QEB=s%C3%A9lection-des-dimensions-dun-rapport %5Boptional%5D-customizing-dimension-display-names=facultatif-personnalisation-des-noms-daffichage-des-dimensions h_01HA9W7NP5YC8E3B05GV7J1Z5V=facultatif-personnalisation-des-noms-daffichage-des-dimensions preserving-privacy-while-grouping-by-dimension-regrouping=pr%C3%A9servation-de-la-confidentialit%C3%A9-lors-du-regroupement-par-dimension-regroupement h_01HA9W7NP5XJGK4CXNHK02NYT4=pr%C3%A9servation-de-la-confidentialit%C3%A9-lors-du-regroupement-par-dimension-regroupement h_01HA9W7NP596RGHA1BES64GSK1=exemple-de-regroupement %5Boptional%5D-managing-dimension-priority=facultatif-gestion-de-la-priorit%C3%A9-de-dimension h_01HA9W7NP5781HV31T5DAYSMMT=facultatif-gestion-de-la-priorit%C3%A9-de-dimension h_01HA9W7NP6WCSRSH157P78QEQF=select-metrics extracting-metrics-from-event_value=extraction-de-m%C3%A9triques-%C3%A0-partir-de-event_value h_01HA9W7NP6JEXE67A935BJ93AQ=extraction-de-m%C3%A9triques-%C3%A0-partir-de-event_value select-report-metrics=s%C3%A9lectionner-les-statistiques-du-rapport h_01HA9W7NP6EF23ZDGZHDKVTS7V=s%C3%A9lectionner-les-statistiques-du-rapport %5Boptional%5D-customizing-metric-display-names=facultatif-personnalisation-des-noms-daffichage-des-m%C3%A9triques h_01HA9W7NP6X584YAXT030A6BEY=facultatif-personnalisation-des-noms-daffichage-des-m%C3%A9triques %5Boptional%5D-select-identifiers-to-count=facultatif-s%C3%A9lectionnez-les-identifiants-%C3%A0-compter h_01HA9W7NP6YETQ1ND0K8XZTZZ0=facultatif-s%C3%A9lectionnez-les-identifiants-%C3%A0-compter h_01HA9W7NP6ZH3KRN7YNWCPFZC9=configure-report-settings-and-save-the-report schedule-only-for-reports-without-custom-sources=planification-uniquement-pour-les-rapports-sans-sources-personnalis%C3%A9es h_01HA9W7NP62DCR2SWD8X4M61R7=planification-uniquement-pour-les-rapports-sans-sources-personnalis%C3%A9es h_01HA9W7NP6XQE1MN0J08FE89V4=attention--1 report-destination=destination-du-rapport h_01HA9W7NP6BQYAF3RMZSW747HH=destination-du-rapport reference=r%C3%A9f%C3%A9rence h_01HA9W7NP6BS0TE332GNPTW9M1=r%C3%A9f%C3%A9rence h_01HA9W7NP606HF0MSPQ4S09YRS=default-inapp-event-dimensions h_01HA9W7NP6A1N25KQ947J3EJW3=default-inapp-event-metrics" />
