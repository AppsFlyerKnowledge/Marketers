---
title: Guide sur Incrementality
metadata:
  keywords:
    - Analytics
    - Audiences
    - Advertisers
    - Premium
    - Marketers
    - Incrementality
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-niv-klein
    - Marketers
    - Incrementality
  created_at: '2020-05-29T19:29:03Z'
  edited_at: '2024-08-22T08:44:06Z'
  id: 360009360978
  locale: fr
  section: Incrementality for remarketing
  section_id: 6551378485649
  url: https://support.appsflyer.com/hc/fr/articles/360009360978
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En bref :** mesurez le saut incrémentiel généré par les campagnes de retargeting

<div id="what-is-incrementality" />

## Qu'est-ce que l'incrémentalité ?

La meilleure façon de comprendre le fonctionnement de l’incrémentalité est de voir un exemple :

Supposons que vous ayez récemment lancé une campagne de remarketing. Pour simplifier, disons qu’un seul réseau publicitaire était en jeu. Le taux de conversion de la campagne était de 5 %.

Vous souhaitez maintenant évaluer les performances de la campagne, vous devez donc répondre à des questions aussi cruciales que difficiles :

* Est-ce que 5 % représente un bon taux de conversion pour cette campagne ?
* Comment être sûr que la campagne a réellement généré des conversions supplémentaires ?
* La campagne en valait-elle le prix ?

Afin de répondre objectivement à ces questions, il faut prendre en compte plus que la mesure des conversions. Il faut aussi prendre en compte le nombre d’utilisateurs qui auraient converti de manière organique, même s’ils n’avaient jamais participé à une campagne de remarketing.

Cette différence entre les conversions totales et celles qui auraient eu lieu de toute façon, c’est ce que l’on nomme **le saut incrémentiel** (ou simplement **«l’incrémentalité »**), et il est essentiel pour déterminer la véritable valeur d'une campagne. Il peut être assez difficile à mesurer, mais c'est précisément ce à quoi sert la solution d’AppsFlyer *Incrementality*.

<div id="incrementality-experiments" />

### Expériences d'incrémentalité

Avec Incrementality, il est facile de mesurer le saut incrémentiel en créant des expériences qui permettent de mesurer et comparer les comportements de groupes similaires. Ces groupes ne varient que dans la mesure où certains d’entre eux (les **« groupes test »**) sont soumis à votre campagne, quand un autre groupe (le **« groupe témoin »**) ne l'est pas.

<Anchor target="_blank" href="/marketers/fr/docs/run-an-incrementality-for-remarketing-experiment">En savoir plus sur la création et la conduite d'expériences d'incrémentalité</Anchor>

<div id="calculation-methodology" />

## Méthodologie de calcul

Les sections suivantes détaillent les calculs qui amènent aux résultats indiqués indiqués dans le tableau de bord Incrementality.

<div id="lift" />

<Accordion title="Saut">

AppsFlyer Incrementality utilise 2 méthodes différentes pour calculer le saut :

* Intention-de-toucher (ITT)
* Méthode basée sur l’effectivité

Bien que **la méthode basée sur l’effectivité soit préférable** pour évaluer les performances des campagnes, son calcul nécessite la mesure de points de données qui ne sont pas proposés par tous les réseaux publicitaires. Pour ces réseaux, la méthode de l’intention-de-traiter sera utilisée.

<div id="note" />

> 📘 **Remarque**
>
> Avant le 16 décembre 2021, le saut était calculé uniquement selon le principe de l’intention-de-traiter. Toutefois, les données des périodes antérieures à cette date ont été mises à jour pour calculer le taux avec la méthode basée sur l’effectivité, le cas échéant. Vous pouvez donc revoir certaines expériences anciennes pour obtenir de nouveaux résultats à la lumière de la nouvelle méthodologie.

<div id="itt-based-lift" />

#### Saut basé sur l'ITT

La méthode ITT fonctionne comme une expérience scientifique. En utilisant l’ITT, les chercheurs répartissent aléatoirement une population donnée entre un groupe témoin qui n’est pas traité (touché), et un groupe test que les chercheurs ont l’intention de traiter (toucher). Les chercheurs mesurent l’efficacité d’un traitement donné en comparant les résultats des différents groupes. Le fait qu’un membre du groupe test ait *effectivement* été traité ou non n’est pas pris en considération.

De même, dans le remarketing, le saut vient mesurer l’efficacité de la campagne. Peu importe qu'un utilisateur du groupe test ait *réellement* interagi avec une campagne (il a été traité), car c'est uniquement l'*intention* qui est valable dans le calcul de l'incrémentalité. En d’autres termes, les résultats sont calculés comme si chaque membre du groupe test a *réellement* participé à la campagne.

**Quand est-il utilisé ?**

AppsFlyer Incrementality calcule le saut en se basant sur l’ITT pour les SRN.

Bien que ce ne soit pas la meilleure méthode pour mesurer le saut dans notre contexte, l'ITT reste une méthode expérimentale avec un fondement scientifique, il fournit de bons résultats lorsque le calcul basé sur l’effectivité n'est pas disponible.

**Interprétation des résultats**

L’hypothèse selon laquelle tous les membres du groupe test ont été véritablement touchés par une campagne produit souvent des taux de conversion bas, et de fait : un faible saut incrémentiel.

<div id="reach-based-lift" />

#### Saut basé sur l’effectivité

Comme son nom l'indique, le calcul du saut basé sur l’effectivité prend en compte si un membre du groupe de test a été *effectivement touché* (a consulté la publicité d’une campagne) avant la conversion. En plus de nécessiter des données supplémentaires, le calcul du saut basé sur l’effectivité est aussi plus complexe puisqu’il nécessite d’opérer des ajustements mathématiques sur le groupe témoin afin d'être valide. Ces ajustements nécessitent la création d’un groupe témoin « contrefactuel ».

**Quand est-il utilisé ?**

AppsFlyer Incrementality calcule le saut avec la méthode basée sur l’effectivité pour les réseaux non-SRN (réseaux à liens d'attribution).

Bien qu'il s'agisse de la méthode privilégiée pour calculer le saut, le calcul basé sur l’effectivité nécessite que les réseaux publicitaires transmettent les données suivantes à AppsFlyer :

* Données d'impression
* ID de campagne (à partir du lien d'attribution)

Si ces données ne sont pas transmises, la mesure de l'incrémentalité n'est pas disponible (et s'affiche comme **N/A** dans le tableau de bord d'incrémentalité).

**Interprétation des résultats**

Comme le calcul du saut basé sur l’effectivité ne prend en compte que les membres du groupe test qui ont été *effectivement* touchés par une campagne, les réseaux mesurés via l'incrémentalité basée sur l’effectivité afficheront généralement des résultats gonflés (le saut positif sera beaucoup plus grand et le saut négatif sera beaucoup plus bas).

<div id="best-practices" />

#### Recommandations

Vu que les deux méthodes de calcul du saut peuvent donner des résultats très différents, nous vous recommandons les pratiques suivantes pour obtenir des résultats fiables :

* Lors de la création de vos expériences, sélectionnez des audiences réparties uniquement entre un groupe témoin et un ou plusieurs réseaux du même type, c’est-à-dire :
  * Des réseaux de liens d'attribution (non-SRN) pour le calcul basé sur l’effectivité ; ou
  * Des SRN pour le calcul basé sur l'ITT
* Lors des premières expériences, nous vous conseillons d’utiliser une audience divisée uniquement entre un réseau unique et un groupe témoin. Vous réduirez ainsi les chances que des comparaisons soient faites entre les réseaux pour lesquels s’appliquent des méthodes de calcul du saut différentes.

</Accordion>

<div id="statistical-significance" />

<Accordion title="Probabilité statistique">

Pour évaluer la validité mathématique des expériences d'incrémentalité, il faut prendre en compte **la probabilité statistique** (c’est-à-dire le niveau de confiance dans le fait que le saut obtenu n'est pas dû à des événements aléatoires, ou au hasard). 

Dans le tableau de bord d'incrémentalité, la probabilité statistique est indiquée sous forme de pourcentage pour chaque source média :

* Le pourcentage indique la probabilité que les résultats pour cette source média seront identiques si l’expérience est renouvelée dans les mêmes conditions.
* Si la probabilité statistique est inférieure à 60 %, le tableau de bord affichera **des résultats non fiables** à la place d'un pourcentage.
* La probabilité statistique varie en fonction de la taille de l’audience, la durée de l’expérience et des performances de la source média.

</Accordion>

<div id="scaled-control-group" />

<Accordion title="Groupe témoin mis à l'échelle">

Pour [les mesures au niveau du groupe test](/docs/incrementality-for-remarketing-overview#::2c5f08ec) (par opposition aux [mesures par utilisateur](/docs/incrementality-for-remarketing-overview#::6143ff4f)), le saut est calculé d’après un **groupe de contrôle mis à l'échelle**. En d’autres termes, la taille du groupe de contrôle s’ajuste à la taille du groupe de contrôle de chaque source média.

<div id="example" />

> 📄 **Exemple**
>
> Voyons le scénario suivant :
>
> * Taille du groupe test pour le réseau A = 100 membres
> * Taille du groupe témoin = 90 membres
> * Résultats de l'expérience :
>   * Le réseau A a enregistré 40 conversions
>   * Le groupe témoin a produit 20 conversions
> * Les conversions totales seront ajustées en fonction de la taille du groupe témoin présumée (mise à l’échelle) de 100 membres :
>   * Nombre de membres présumé - Nombre de membres réel = 100 - 90 = 11%
>                       Nombre de membres réels 90
>   * Conversions incrémentielles réelles + 11 % = 20 x 1,11 = 22
>
> Le saut sera calculé sur la base d'un groupe témoin ajusté à 100 membres, et de 22 conversions incrémentielles.

</Accordion>

<div id="incrementality-dashboard" />

## Tableau de bord d'incrémentalité

[![New_Incrementality_Guide_image.jpg](https://files.readme.io/a14fa7ae346177dbdd7de5fde4917d7300cbc148097a2239e29460a67eacd9a6-15317247527569.jpg)](https://files.readme.io/a14fa7ae346177dbdd7de5fde4917d7300cbc148097a2239e29460a67eacd9a6-15317247527569.jpg)

<div id="accessing-the-dashboard" />

<Accordion title="Accéder au tableau de bord">

**Pour ouvrir le tableau de bord d'incrémentalité :**

1. Dans AppsFlyer, dans le menu latéral, sélectionnez **Optimiser** > **Incrémentalité**.
2. Dans la liste des expériences, cliquez sur la ligne correspondant à l’expérience pour laquelle vous souhaitez ouvrir le tableau de bord.

</Accordion>

<div id="a-tour-of-the-dashboard" />

<Accordion title="Visite guidée du tableau de bord">

<Table>
  <thead>
    <tr>
      <th>

      </th>
      <th>
        Composant
      </th>
      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        ![A.png](https://files.readme.io/ac7d37f68811559b92cac8032fa2304646903b4aa623e6ee3c35e265d34250fe-5397347579665.png)
      </td>
      <td>
        Barre des filtres
      </td>
      <td>
        **Mesure :** sélectionne la mesure que vous souhaitez afficher dans le tableau de bord

        * **Conversions** – Le nombre d’utilisateurs uniques qui ont effectué l’événement sélectionné
        * **Revenus** – Revenus générés par la conversion des utilisateurs de l'événement sélectionné
        * **Événements** – Le nombre de fois où l'événement sélectionné a été réalisé par les utilisateurs convertis

        Votre choix dans le filtre **Mesure** détermine quelles mesures s’affichent dans le tableau de bord.

        **Événement :** sélectionne l’événement in-app pour lequel vous souhaitez afficher les données dans le tableau de bord.

        **Source média :** filtre le tableau de bord pour afficher une ou plusieurs des sources média testées dans l’expérience.

        **Période :** filtre l'analyse incrémentale de l'audience en fonction de période sélectionnée.
      </td>
    </tr>
    <tr>
      <td>
        ![B.png](https://files.readme.io/ae2685f993019ee2bd461055c7be9ce739797a0b43bb28b85bf4f54997936f5b-5397362069393.png)
      </td>
      <td>
        <span id="::3b361a96"></span>Bilan de l'expérience
      </td>
      <td>
        Résume toute l'expérience avec des résultats centralisés et en accès rapide.
      </td>
    </tr>
    <tr>
      <td>
        ![C.png](https://files.readme.io/b428e77b299e10fe0701b7850cea1da8942905ad38d7b30c32f99f0240b22a63-5397303804945.png)
      </td>
      <td>
        <span id="::6ba593ae"></span>Volet Probabilité statistique
      </td>
      <td>
        Affiche la [probabilité statistique](/docs/incrementality-for-remarketing-overview#statistical-significance) des résultats affichés dans le tableau de bord
      </td>
    </tr>
    <tr>
      <td>
        ![D.png](https://files.readme.io/9d9abd09fc45ec65fc52cbc1c8011117b555629d243444d076a392b4245effdd-5397362181265.png)
      </td>
      <td>
        <span id="::4c3ffd21"></span>Volet Mesures principale
      </td>
      <td>
        La mesure qui s’affiche dépend de votre sélection dans le filtre Mesure, comme indiqué ci-dessous.

        | Sélection du filtre Mesure | Mesure principale affichée |
        | --- | --- |
        | <span id="conversionsevents"></span>Conversions/Événements | Coût par action incrémentale (CPiA)<br /><br />* Coût moyen de chaque événement incrémental, basé sur le coût de la campagne |
        | <span id="revenue"></span>Revenus | Retour incrémental sur les dépenses publicitaires (iROAS)<br /><br />* Part des revenus supplémentaires générés pour chaque dollar investi dans la campagne |

        **Remarque :** Le calcul des mesures affichées dans le volet principal nécessite des données de coût. Par conséquent, ces mesures ne sont disponibles que pour les abonnés à <Anchor target="_blank" href="/marketers/fr/docs/roi360-cost-aggregation-overview">ROI360</Anchor> . Si les données de coût et/ou de revenu nécessaires ne sont pas disponibles (pour cette raison ou une autre), la mesure concernée affichera comme résultat **N/A.**
      </td>
    </tr>
    <tr>
      <td>
        ![E.png](https://files.readme.io/28563cf0057cdd6ccfd8ebb5b727ae80bef81ec66697f8e11eadc698f72e7acd-5397355189777.png)
      </td>
      <td>
        <span id="::c0b74d1b"></span>Volet Taille ciblée et effectivité
      </td>
      <td>
        **Taille ciblée :** le nombre d'utilisateurs distincts, pour chaque source média, qui ont été ajoutés à l'audience pour la première fois sur la période de l'expérience

        * Représenté également par le cercle au centre du graphique en anneaux (couleur plus foncée)

        Effectivité : le pourcentage de la cible qui a effectivement vu une publicité de la campagne dans la source média concernée

        * Représenté également par le cercle à l’extérieur du graphique en anneaux (couleur plus claire)
      </td>
    </tr>
    <tr>
      <td>
        ![F.png](https://files.readme.io/99f2fb8f45215ddebf9582f215e3647bc35f5a812015733b3f6e3cb8d2784bd7-5397365201809.png)
      </td>
      <td>
        <span id="::2c5f08ec"></span>Volet Sait au niveau du groupe test
      </td>
      <td>
        Affiche la mesure incrémentielle **totale** et le saut **pour le groupe test** (par source média) :

        * Le saut incrémentiel total est calculé à l'aide d'un [groupe témoin mis à l'échelle](/docs/incrementality-for-remarketing-overview#scaled-control-group).
        * La mesure qui s’affiche dépend de votre sélection dans le filtre Mesure, comme indiqué ci-dessous.

        | Sélection du filtre Mesure | Mesure affichée |
        | --- | --- |
        | <span id="conversions"></span>Conversions | Conversions incrémentielles totales |
        | <span id="events"></span>Événements | Total des événements incrémentiels |
        | <span id="revenue::3f000a8e"></span>Revenus | Total des revenus incrémentiels |
      </td>
    </tr>
    <tr>
      <td>
        ![G.png](https://files.readme.io/7301cda39a8a6bcd08d199097ff9b11d496c5f01ab34422364a4e467a752338a-5397303963409.png)
      </td>
      <td>
        <span id="::6143ff4f"></span>Volet Saut par utilisateur
      </td>
      <td>
        Affiche les mesures incrémentielles et le saut **par utilisateur** (par source média) :

        * Le saut incrémentiel par utilisateur est calculé d’après le nombre réel d'utilisateurs dans le groupe test et le groupe témoin.
        * La mesure qui s’affiche dépend de votre sélection dans le filtre Mesure, comme indiqué ci-dessous.

        | Sélection du filtre Mesure | Mesure affichée |
        | --- | --- |
        | <span id="conversions::b51393dc"></span>Conversions | Taux de conversion incrémentiel |
        | <span id="events::3b4fa416"></span>Événements | Événements incrémentiels par utilisateur |
        | <span id="revenue::b432caf"></span>Revenus | Revenus supplémentaires par utilisateur |
      </td>
    </tr>
    <tr>
      <td>
        ![H.png](https://files.readme.io/36085f38ba02d718acc766af3865073bf13960b2a1c755bd48302ab5415ff89a-5397355274513.png)
      </td>
      <td>
        <span id="::a6a95657"></span>Diagramme des tendances
      </td>
      <td>
        Affiche la mesure/le saut incrémentiel **par utilisateur** sur la période de l'expérience :

        * La mesure affichée dépend de votre sélection dans le filtre Mesure, c’est la même que celle affichée dans le **volet Saut par utilisateur.**
        * Une ligne en pointillé (dans la vue graphique) indique des données partielles pour la date définie (ce qui signifie que les événements futurs peuvent encore transformer les données).
        * Sélectionnez différentes options d'affichage et de téléchargement avec les**Commandes d'affichage du graphique des tendances** (cf détails plus loin ci-dessous).
      </td>
    </tr>
    <tr>
      <td><span id="::64e4f3f6"></span>
        <Image alt="I.jpg" src="https://files.readme.io/19ab5c305d3eb2609031a1a88f6f4069015b6eefe9ef4f1501613f62e5024739-15317326904465.jpg" width="29px" />
      </td>
      <td>
        Commandes d’affichage du graphique des tendances
      </td>
      <td>
        Utilisez les commandes d'affichage pour choisir les options d'affichage et de téléchargement **du graphique des tendances**  :

        * Valeurs cumulées ou quotidiennes (au jour J)
        * Au format graphique ou tableau

        Utilisez le bouton **Exporter** pour télécharger les données sous forme de rapport au format CSV.

        * Les données téléchargées dépendent de votre choix dans les commandes d'affichage : **Cumulatif** ou **au jour J**

        **Description des termes employés dans le rapport**

        | Terme | Description |
        | --- | --- |
        | Mesure brute | Le montant total des conversions/événements/revenus générés par le groupe test, indépendamment des impressions (repose uniquement sur le réseau auquel chaque utilisateur a été affecté lors de la répartition). |
        | Mesure effective | Le montant des conversions/événements/revenus générés par le groupe test, uniquement par les utilisateurs qui ont eu une impression de la campagne sélectionnée avant de déclencher l'événement lié. |
        | Mesure non effective | La mesure brute moins la mesure effective. Correspond au montant total des conversions/événements/revenus générés par les utilisateurs du groupe test qui n'ont pas eu d'impression avant de déclencher l'événement lié. |
        | Mesure par utilisateur | Mesure effective/brute du groupe test (dépend si le réseau sélectionné prend en charge ou non l’effectivité), divisée par la taille du groupe/l’effectivité du groupe test. |
        | Mesure brute du groupe témoin | Le montant total des conversions/événements/revenus générés par le groupe témoin. |
        | Mesure effective du groupe témoin | Le montant des conversions/événements/revenus générés par le groupe témoin, ajusté en fonction de l’effectivité du groupe test (cette valeur est contrefactuelle et permet de comparer les éléments comparables). |
        | Mesure non effective du groupe témoin | La mesure brute moins la mesure contrefactuelle effective. Correspond au montant total des conversions/événements/revenus générés par les utilisateurs du groupe témoin. |
        | Groupe témoin par mesure utilisateur | Mesure effective/brute contrefactuelle du groupe témoin (dépend si le réseau sélectionné prend en charge ou non l’effectivité), divisée par la taille du groupe/l’effectivité contrefactuelle du groupe témoin. |
        | Total des mesures incrémentielles | La mesure test effective moins la mesure de contrôle contrefactuelle effective. |
        | Mesure incrémentielle par utilisateur | La mesure par utilisateur moins la mesure de contrôle par utilisateur. |
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="raw-data-reports" />

## Rapports de données brutes

Les rapports de données brutes d'incrémentalité vous permettent d’analyser l'interaction des utilisateurs avec les campagnes de remarketing :

* **Contenu :** données au niveau des lignes des utilisateurs participant aux expériences d’incrémentalité.
* **Disponibilité :**
  * Via <Anchor target="_blank" href="/marketers/fr/docs/data-locker-for-marketers">Data Locker</Anchor>
  * Actualisation des données : tous les jours de 19:00 à 23:00 UTC

<Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/360012600697">Téléchargez ici des exemples de fichiers de données brutes d'incrémentalité</Anchor>

<div id="available-reports" />

<Accordion title="Rapports disponibles">

<table><thead><tr><th>Catégorie</th><th>Nom du rapport </th><th><p>Dossier Data Locker</p></th></tr></thead><tbody><tr><td><p>Première-vue</p></td><td><p>Utilisateurs qui visualisent pour la première fois</p></td><td>incrementality_first_seen_users</td></tr><tr><td rowspan="3"><p>Événements in-app</p></td><td><p>Événements in-app organiques</p></td><td>incrementality_organic_inapps</td></tr><tr><td><p>Événements in-app non organiques</p></td><td>incrementality_inapps</td></tr><tr><td><p>Réattributions d'événements in-app</p></td><td>incrementality_inapps_reattr</td></tr><tr><td rowspan="3"><p>Sessions</p></td><td><p>Sessions organiques</p></td><td>incrementality_organic_sessions</td></tr><tr><td><p>Sessions non-organiques</p></td><td>incrementality_sessions</td></tr><tr><td><p>Réattributions des sessions</p></td><td>incrementality_sessions_reattr</td></tr><tr><td><p>Désinstallations</p></td><td><p>Désinstallations<br/>(actuellement non renseigné) </p></td><td>incrementality_uninstalls</td></tr></tbody></table>

</Accordion>

<div id="report-logic" />

<Accordion title="Fonctionnement du rapport">

La logique de base de la structure du rapport est la suivante :

* **Utilisateurs participant à l'expérience – Rapport première-vue**
  * Dans Audiences, des règles sont définies pour caractériser les utilisateurs à inclure dans l'expérience.
  * Lorsqu'un utilisateur lambda est identifié comme répondant aux règles, l'événement est enregistré dans le rapport *first\_seen* (première-vue) .
    * Les utilisateurs sont affectés aléatoirement à un groupe test ou témoin, indiqué par le champ *is\_control\_group* .
    * Les utilisateurs du groupe test sont affectés à une source média (*pid\_destination*) pour le retargeting.
* **Engagement des utilisateurs dans l'application :** L'engagement de l'utilisateur dans l'application au cours de l'expérience est enregistré dans des rapports propres au contexte :
  * **Type d'engagement :** Session ou événement in-app
  * **Statut d'attribution de l'utilisateur** lorsque l'utilisateur visualise pour la première fois : organique, non organique, réattribution. Par exemple, un utilisateur a un jour installé l’application et a été attribué comme organique. Ainsi, lors d’une expérience, son statut d’attribution sera organique.
* **Désinstallations :** Les utilisateurs désinstallent l'app au cours de l'expérience. La mesure des désinstallations doit être active.

</Accordion>

<div id="data-characteristics-and-fields" />

<Accordion title="Caractéristiques et champs des données">

La disponibilité des champs varie selon le type de rapport, comme indiqué ci-dessous :

<div id="fields-unique-to-incrementality-per-report-type" />

#### Champs spécifiques à l'incrémentalité (par type de rapport)

| Champ | Description | Première vue | Événements in-app | Sessions | Désinstallations |
| --- | --- | --- | --- | --- | --- |
| <span id="is_control_group"></span>is\_control\_group | Si *true*, l'utilisateur fait partie du groupe témoin | Y | Y | Y | Y |
| <span id="pid_destination"></span>pid\_destination | La source média où l'utilisateur est envoyé | Y | Y | Y | Y |
| <span id="audience_id"></span>audience\_id | Identifiant unique | Y | Y | Y | Y |
| <span id="joined_audience_date"></span>joined\_audience\_date | Date où l'utilisateur a rejoint l'audience pour la première fois | Y | Y | Y | Y |
| <span id="audience_name"></span>audience\_name | Nom de l’audience (n’est pas unique) | Y | Y | Y | Y |
| <span id="tm"></span>tm | Heure de la journée |  | Y | Y | Y |
| <span id="timestamp"></span>timestamp | Horodatage de l'événement AAAA-MM-JJ HH:MM |  | Y | Y |  |
| <span id="app_ids"></span>app\_ids | ID d'app associés aux règles de l’audience | Y |  |  |  |

<div id="other-incrementality-report-fields-per-report-type" />

#### Autres champs du rapport d'incrémentalité (par type de rapport)

<table><thead><tr><th>Champ</th><th>Nom d'affichage\*</th><th>Première-vue</th><th>Événements in-app</th><th>Sessions</th><th>Désinstallations</th></tr></thead><tbody><tr><td><span id="advertising_id"></span>advertising_id</td><td>ID publicitaire (GAID)</td><td>Y</td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td><span id="android_id"></span>android_id</td><td>ID Android </td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="app_id"></span>app_id</td><td>ID d'app</td><td>Y</td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td><span id="app_name"></span>app_name</td><td>Nom de l'app</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="app_version"></span>app_version</td><td>Version de l'app</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="appsflyer_id"></span>appsflyer_id</td><td>ID AppsFlyer</td><td> </td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td><span id="revenue_alt"></span>revenue_alt</td><td>Devise spécifique à l'app</td><td> </td><td>Y</td><td> </td><td> </td></tr><tr><td><span id="bundle_id"></span>bundle_id</td><td>ID de bundle</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="country"></span>country</td><td>Code pays</td><td> </td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td><span id="currency"></span>currency</td><td>Code de la devise</td><td> </td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td><span id="customer_user_id"></span>customer_user_id</td><td>ID utilisateurdu client</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="brand"></span>brand</td><td>Marque de l'appareil</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="device_category"></span>device_category</td><td>Catégorie de l'appareil</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="model"></span>model</td><td>Modèle de l'appareil</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="device_model"></span>device_model</td><td>Modèle de l'appareil</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="device_type"></span>device_type</td><td>Type d'appareil</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="event_name"></span>event_name</td><td>Nom de l'événement</td><td> </td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td><span id="event_revenue"></span>event_revenue</td><td>Revenu des évènements</td><td> </td><td>Y</td><td> </td><td> </td></tr><tr><td><span id="event_revenue_currency"></span>event_revenue_currency</td><td>Devise du revenu des évènements</td><td> </td><td>Y</td><td> </td><td> </td></tr><tr><td><span id="event_revenue_u_s_d"></span>event_revenue_u_s_d</td><td>Revenu de l'évènement en USD</td><td> </td><td>Y</td><td> </td><td> </td></tr><tr><td><span id="event_time"></span>event_time</td><td>Heure de l'évènement</td><td> </td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td><span id="event_value"></span>event_value</td><td>Valeur de l'événement</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="idfa"></span>idfa</td><td>IDFA</td><td>Y</td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td><span id="idfv"></span>idfv</td><td>IDFV</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="imei"></span>imei</td><td>imei</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="is_purchase_validated"></span>is_purchase_validated</td><td>Est validé par reçu</td><td> </td><td>Y</td><td> </td><td> </td></tr><tr><td><span id="os_version"></span>os_version</td><td>Version OS</td><td> </td><td>Y</td><td>Y</td><td> </td></tr><tr><td><span id="platform"></span>platform</td><td>Plateforme</td><td> </td><td>Y</td><td>Y</td><td>Y</td></tr><tr><td><span id="sdk_version"></span>sdk_version</td><td>Version du SDK</td><td> </td><td>Y</td><td>Y</td><td> </td></tr></tbody><tfoot><tr><td colspan="6"><span id="-according-to-raw-data-specification"></span>\* <a href="./raw-data-field-dictionary#data-fields-dictionary" target="_blank">Selon les spécifications des données brutes</a> </td></tr></tfoot></table>

</Accordion>

<div id="incrementality-specifications-and-limitations" />

## Spécifications et limitations de l'incrémentalité

| Caractéristique | Remarques |
| --- | --- |
| Accès du réseau publicitaire | Non disponible |
| Autorisations de l'agence | Non disponible. L'incrémentalité est disponible uniquement pour les comptes annonceur. |
| Transparence de l'agence | Vous pouvez mesurer les campagnes menées par les agences dont la transparence est activée. |
| Fuseau horaire | UTC |
| Devise | USD |
| Données organiques | Oui |
| Données non organiques | Oui |
| Actualisation des données | Tableau de bord : tous les jours à 18:00 UTC pour le jour précédent<br /><br />Rapports de données brutes dans Data Locker : tous les jours de 19:00 à 23:00 pour le jour précédent |
| Données historiques | N/A |
| Accès utilisateur du compte | Oui (selon autorisations du compte) |

<div id="see-also" />

> 📄 **Articles connexes**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/audiences-guide">Guide sur les audiences</Anchor>
> * <Anchor target="_blank" href="https://www.appsflyer.com/blog/tips-strategy/incrementality-testing-for-marketers/">Blog sur les tests d'incrémentalité pour les marketeurs</Anchor>
> * <Anchor target="_blank" href="https://www.appsflyer.com/blog/topic/incrementality/">Blog sur Incrementality</Anchor>

<div data-zendesk-anchors="what-is-incrementality=quest-ce-que-lincr%C3%A9mentalit%C3%A9- h_01HB86QVQ0TM91XB8VSZYD42ZA=quest-ce-que-lincr%C3%A9mentalit%C3%A9- incrementality-experiments=exp%C3%A9riences-dincr%C3%A9mentalit%C3%A9 h_01HB86QVQ0HR436K24V3SQXVXT=exp%C3%A9riences-dincr%C3%A9mentalit%C3%A9 calculation-methodology=m%C3%A9thodologie-de-calcul h_01HB86QVQ0FYTCEVATBEC91ZC1=m%C3%A9thodologie-de-calcul h_01HB86QVQ0SMJFEPJ8048NBQTN=lift h_01HB86QVQ1MREDW50YTKSY2KZJ=remarque ittbased-lift=saut-bas%C3%A9-sur-litt h_01HB86QVQ1NGWZM604A45K03TA=saut-bas%C3%A9-sur-litt reachbased-lift=saut-bas%C3%A9-sur-leffectivit%C3%A9 h_01HB86QVQ1N67SFWKRG1BKZE5A=saut-bas%C3%A9-sur-leffectivit%C3%A9 best-practices=recommandations h_01HB86QVQ1RDMFT5FH53BYDNSV=recommandations h_01HB86QVQ1K2SPBXTG67B5PV33=statistical-significance h_01HB86QVQ1CAZ0ZDJDKPC1B36S=scaled-control-group h_01HB86QVQ16EZVAATG4DPTDVTQ=exemple incrementality-dashboard=tableau-de-bord-dincr%C3%A9mentalit%C3%A9 h_01HB86QVQ10C1YHC8HZ9Z8T089=tableau-de-bord-dincr%C3%A9mentalit%C3%A9 h_01HB86QVQ1ECVT0BT4GYC81DH4=accessing-the-dashboard h_01HB86QVQ1JN8SPHXJGHT4NFSB=a-tour-of-the-dashboard raw-data-reports=rapports-de-donn%C3%A9es-brutes h_01HB86QVQ27FXXBRSH2V8ZK78X=rapports-de-donn%C3%A9es-brutes h_01HB86QVQ24932F7CHY666730J=available-reports h_01HB86QVQ2YXRVFKEE20E787BK=report-logic h_01HB86QVQ2VK6TX3CSA4S6QSKZ=data-characteristics-and-fields fields-unique-to-incrementality-per-report-type=champs-sp%C3%A9cifiques-%C3%A0-lincr%C3%A9mentalit%C3%A9-par-type-de-rapport h_01HB86QVQ2CAN02B8GWEZTTTVW=champs-sp%C3%A9cifiques-%C3%A0-lincr%C3%A9mentalit%C3%A9-par-type-de-rapport other-incrementality-report-fields-per-report-type=autres-champs-du-rapport-dincr%C3%A9mentalit%C3%A9-par-type-de-rapport h_01HB86QVQ221QK6WYRZQ3MJDSY=autres-champs-du-rapport-dincr%C3%A9mentalit%C3%A9-par-type-de-rapport incrementality-specifications-and-limitations=sp%C3%A9cifications-et-limitations-de-lincr%C3%A9mentalit%C3%A9 h_01HB86QVQ2W6X5Z485WM371GGE=sp%C3%A9cifications-et-limitations-de-lincr%C3%A9mentalit%C3%A9 h_01HE7RBMSE1RHVSJC7B7FZG8SJ=articles-connexes" />
