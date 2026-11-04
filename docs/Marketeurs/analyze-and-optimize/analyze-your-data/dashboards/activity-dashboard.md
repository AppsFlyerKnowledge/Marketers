---
title: Tableau de bord d'activité
metadata:
  keywords:
    - activity report
    - Advertisers
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2016-01-12T15:50:15Z'
  edited_at: '2024-09-19T07:18:23Z'
  id: 207602503
  locale: fr
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/fr/articles/207602503
---
> **En bref :** pour accéder à l'activité d’une app, l'engagement et les mesures in-app sur une période donnée. Les données de la journée sont mises à jour en temps réel.

![ActivityDB.png](https://files.readme.io/8150eafc018c83ae2b1030702129bda12419dfac60eb8664187c2acd66136df3-4420170646289.png)

<div id="activity-dashboard" />

## Tableau de bord d'activité

* Comprend le trafic organique et non organique
* La période se rapporte à la date de l'événement et n'est pas <Anchor target="_blank" href="/marketers/fr/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">basée sur le LTV.</Anchor>
* Actualisation des données :  
  * **Jour en cours** : <Anchor target="_blank" href="/marketers/fr/docs/about-data-freshness-and-timezone-support#continuous-aka-realtime">en continu</Anchor>. Ex. DAU, sessions, revenu
  * **Moyenne :** quotidienne. Ex. MAU, DAU moyen, MAU moyen
* Le filtre géo indique l'emplacement de l'utilisateur au moment de l'installation.

<div id="tip" />

> 👍 **Astuce**
>
> Vous voulez en savoir plus sur le tableau de bord d’activité ? Suivez cette <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7802/play/18621/the-activity-dashboard">brève formation sur le portail d'apprentissage AppsFlyer.</Anchor>

<div id="dashboard-features-and-layout" />

## Fonctionnalités et contenu du tableau de bord

<div id="metric-definitions" />

<Accordion title="Définitions des métriques">

<Table>
  <thead>
    <tr>
      <th>
        Métrique
      </th>
      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="dau"></span>
        DAU
      </td>
      <td>
        * Utilisateurs actifs quotidiens (DAU) : Le nombre d'utilisateurs uniques qui ont ouvert l'app au moins une fois dans la journée.
        * Le DAU est basé sur les sessions.
        * <Anchor target="_blank" href="/marketers/fr/docs/unique-users">En savoir plus sur les utilisateurs uniques</Anchor>
      </td>
    </tr>
    <tr>
      <td><span id="average-dau"></span>
        DAU moyen
      </td>
      <td>
        Nombre moyen d'utilisateurs actifs quotidiens, par jour, sur la période sélectionnée.

        Ex. Calcul du DAU moyen

        > 📄
        >
        > |  | Dimanche | Lundi | Mardi |
        > | --- | --- | --- | --- |
        > | <span id="daily-active-unique-users"></span>Utilisateurs uniques actifs par jour | 10 | 12 | 8 |
        >
        >
        >
        > **DAU moyen** = (10+12+8)/3= 10.
      </td>
    </tr>
    <tr>
      <td><span id="mau"></span>
        MAU
      </td>
      <td>
        Utilisateurs actifs mensuels (MAU) :

        * **Détaillé :** nombre d'utilisateurs uniques (comptés une seule fois) qui ont ouvert l'app au moins une fois les 31 derniers jours.
        * **Haut-niveau :** nombre d'utilisateurs uniques (comptés une seule fois) qui ont ouvert l'app au moins une fois au cours du mois civil.
      </td>
    </tr>
    <tr>
      <td><span id="daumau-rate"></span>
        Taux DAU / MAU
      </td>
      <td>
        * Cette mesure donne un aperçu du taux de retour des utilisateurs. Un taux DAU/MAU de 50 % signifie que l'utilisateur moyen a ouvert l'app sur 15 des 31 jours écoulés.
        * Le taux DAU/MAU mesure la fidélité des utilisateurs et donne un aperçu de la rétention des utilisateurs.
      </td>
    </tr>
    <tr>
      <td><span id="revenue"></span>
        Revenu
      </td>
      <td>
        Revenu généré sur la période sélectionnée. Le revenu comprend les achats in-app (si rapportés) et les revenus publicitaires.
      </td>
    </tr>
    <tr>
      <td><span id="arpdau"></span>
        ARPDAU
      </td>
      <td>
        Revenu moyen par utilisateur actif quotidien  
        Formule : Somme de (Revenu au jour [n] / DAU au jour [n])]/Nombre de jours.

        <div id="h_01HHYHP1HFZBRTWB8MJ1F6XKZS" />

        > 📄 **Ex. Calcul de l'ARPDAU**
        >
        > | Jour | Revenu ($) au jour | DAU | Revenu quotidien moyen des utilisateurs ($) |
        > | --- | --- | --- | --- |
        > | <span id="day-1"></span>Jour 1 | 10 | 5 | 2 |
        > | <span id="day-2"></span>Jour 2 | 16 | 4 | 4 |
        > | <span id="day-3"></span>Jour 3 | 30 | 5 | 6 |
        > |  |  | Total : | 12 |
        > |  <span id="::4eb0b020"></span>|  | Nombre de jours | 3 |
        > |  <span id="::b35cc38c"></span>|  | **ARPDAU** | 4 |
      </td>
    </tr>
    <tr>
      <td><span id="sessions"></span>
        Sessions
      </td>
      <td>
        Sessions durant la période sélectionnée (si rapportées par l'app)
      </td>
    </tr>
    <tr>
      <td><span id="installs"></span>
        Installations
      </td>
      <td>
        Nombre d'installations sur la période définie
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="detailed-tab" />

<Accordion title="Onglet détaillé">

L'onglet *Analyse détaillée* est divisé en plusieurs sections : mesures principales, tendances d'activité et résumé de l'activité. 

<table><tbody><tr><td colspan="2"><h4><strong><span id="headline-metrics"></span>Métriques principales</strong></h4></td></tr><tr><td> </td><td><p><img alt="ActivityHeadLines_us-en__1_.png" src="https://files.readme.io/a4f1a5316eeacf0f635bbeadf52d490dd0276bb8a1fe9c0e32db7008d11d044b-360012584838.png"/></p></td></tr><tr><td></td><td><p><strong>Moyenne des utilisateurs actifs</strong></p><ul><li>DAU moyen : nombre moyen d'utilisateurs actifs quotidiens sur la période spécifiée.</li><li>MAU moyen : nombre moyen d'utilisateurs actifs mensuels sur la période choisie. Il s'agit d'une moyenne glissante pour les jours de la période sélectionnée, chaque jour étant calculé à partir des 31 jours. Remarque : pour accéder au MAU d'un mois donné, définissez la période au premier jour du mois suivant (exemple : pour mars, choisissez le 1er avril), la valeur que vous cherchez est le MAU moyen.</li></ul></td></tr><tr><td> </td><td> <strong>Total des installations :</strong> le nombre d'installations divisé entre les installations organiques et non organiques</td></tr><tr><td> </td><td> <strong>Total des sessions</strong> : le nombre de sessions divisé en sessions d'utilisateurs organiques et non organiques</td></tr><tr><td> </td><td> <strong>Revenu total</strong> : les revenus, divisés en revenus attribuables aux utilisateurs organiques et non organiques</td></tr><tr><td colspan="2"><h4><strong><br/><span id="activity-trends"></span>Tendances d'activité<br/></strong></h4></td></tr><tr><td> </td><td><p> <strong>Ligne des tendances comparative</strong></p><p><img alt="TrendLinWithComp_us-en.png" src="https://files.readme.io/b9edb3e409dc13bc72aebdccdc499fa2dcd9abf4549fb0170bf0cdc7036eee15-360012507997.png"/></p><ul><li>Le diagramme des tendances affiche les mesures des KPI ou événements in-app.</li><li>Une ligne des tendances comparative optionnelle peut être ajoutée en activant la fonction <strong>Comparer avec la période précédente</strong> (jour, semaine, mois, trimestre, année). </li><li>Par exemple, en sélectionnant "mois", pour un jour donné du diagramme, la comparaison se basera sur le même jour du mois précédent. </li></ul><p>Les KPI disponibles sont les suivants :</p><ul><li><span>DAU</span></li><li><span>MAU </span></li><li><span>Revenu</span></li><li><span>ARPDAU</span></li><li><span>Sessions</span></li><li><span>Taux DAU / MAU</span></li></ul><p><span>Les mesures d'événements in-app disponibles sont les suivantes </span>:</p><ul><li><span>Décompte</span></li><li><span>Utilisateurs uniques</span></li><li><span>Revenu</span></li></ul></td></tr><tr><td colspan="2"><h4><strong><br/><span id="activity-summary-table"></span>Tableau récapitulatif des activités</strong></h4></td></tr><tr><td> </td><td><p>Le tableau récapitulatif des activités :</p><ul><li><p>Affiche jusqu'à 50 sources média avec les données des impressions, clics, installations, etc. (Pour obtenir l’ensemble des données, utilisez <a href="./master-api-user-acquisition-metrics-via-api" target="_blank">l’API principale</a> ou  <a href="./pivot-table-user-metrics" target="_blank">le croisé dynamique).</a></p></li><li><p>Les données sont rangées par nombre de sessions. </p></li><li><p>Vous pouvez descendre dans la hiérarchie jusqu’au niveau campagne (il n'est pas possible de descendre plus bas).</p></li><li>Vous permet de voir combien de DAU sont nouveaux et combien sont liés à des utilisateurs existants (DAU moins (-) installations).</li></ul><p><span>Pour utiliser le tableau récapitulatif :</span></p><ul><li><span>Affinez les données en utilisant les champs <i>Filtrer par</i> et <i>Regrouper par.</i></span></li><li><span>Les colonnes du tableau peuvent être ordonnées en cliquant sur l'en-tête d'une colonne.</span></li><li>Filtrez par <strong>événements in-app</strong> pour afficher certains événements in-app précis.</li><li>Passer d'un type d'affichage à l'autre : <ul><li> <strong>Résumé :</strong> le total de tous les événements in-app sélectionnés</li><li> <strong>Événements in-app</strong>: répartition par événement in-app</li></ul></li></ul></td></tr></tbody></table>

</Accordion>

<div id="highlevel-tab-previous-twelvemonths" />

<Accordion title="Onglet Haut niveau : douze mois précédents">

![ActivityHiLevel.png](https://files.readme.io/42636f5b13dca3a2209ea295c02e784175dfc92a2523c861220b87baed859541-4420194466065.png)  

L'onglet contient l’historique sur douze mois des performances de l'activité de l'app, et présente les diagrammes suivants : 

* Utilisateurs actifs et revenus
* Marge brute mensuelle : revenu, coût, profit brut

</Accordion>

<div id="specifications-and-limitations" />

## Caractéristiques et limitations

| Caractéristiques | Remarques |
| --- | --- |
| Actualisation des données | <ul><li>**Métriques :** en temps réel. Cf image ci-dessous.</li><li>**Métriques moyennes**: quotidienne. Cf image ci-dessous. **Remarque** : Les mesures moyennes ne sont pas calculées en temps réel pour éviter de fausser le résultat avec les données issues de journées incomplètes. Si la période comprend le jour en cours, il se produit ceci :<ul><li>Si la période ne concerne que le jour en cours : les résultats moyens ne sont pas affichés.</li><li>Si la période correspond à une fenêtre qui inclut le jour en cours : la moyenne est calculée sans inclure les données du jour en cours.</li></ul></li><li>**Revenu publicitaire :** <Anchor target="_blank" href="/marketers/fr/docs/roi360-guide-ad-revenue-attribution#data-freshness">Enregistré avec un décalage</Anchor> et rapporté aux moments suivants :<ul><li>Données agrégées : au Jour 1 (le jour où les données sont extraites).</li><li>Données de niveau utilisateur : au Jour 0 (le jour où la publicité a été affichée).</li></ul></li></ul>[![Whats_realtime.png](https://files.readme.io/39969fe7395e1b22910aed5d6ca61f6b5603171650f0d0ce88218a2491c02cc5-4407209143953.png)](https://files.readme.io/39969fe7395e1b22910aed5d6ca61f6b5603171650f0d0ce88218a2491c02cc5-4407209143953.png) |
| Désinstallations | Ne sont pas prises en charge |
| Retargeting | <ul><li>Pris en charge, avec les exceptions suivantes :<ul><li>Les clics et impressions de retargeting ne sont pas comptabilisés.</li><li>Pour les DAU, MAU et sessions, les sessions de retargeting ne sont pas prises dans le décompte.</li></ul></li><li>Pour le DAU et le MAU, les événements de retargeting in-app sont comptabilisés.</li></ul> |
| ARPDAU | Il peut y avoir des ARPDAU différents entre dans le tableau de bord des activités et le tableau croisé dynamique. |
| Données historiques | <ul><li>3 ans</li><li>Onglet Haut niveau : 1 an</li></ul> |
| Période d'affichage | <ul><li>Maximum 2 mois. Si une période plus longue est définie, la période est réduite à deux mois et un message s'affiche.</li></ul> |
| Regroupement par zone géo | Affiche jusqu'à 62 géos (classées selon les sessions d'activité les plus importantes). |
| Regroupement par campagne | Ce regroupement n'est disponible qu'après avoir sélectionné des sources média précises. |
| Valeurs des dimensions | Les valeurs de dimension de type source média, nom de la campagne ou nom de l'actif sont sensibles à la casse. Cela signifie que "Facebook" et "facebook" seront traités comme des entités distinctes lors du filtrage des résultats. Pour voir les résultats sans tenir compte de la casse, utilisez le <Anchor target="_blank" href="/marketers/fr/docs/pivot-table-user-metrics">tableau croisé dynamique</Anchor>. |

<div data-zendesk-anchors="activity-dashboard=tableau-de-bord-dactivit%C3%A9 h_01HHYHP1HE8G5VA6GSAVTQDDDN=tableau-de-bord-dactivit%C3%A9 h_01HHYHP1HEJHKQKCNC5R26ZE3J=astuce dashboard-features-and-layout=fonctionnalit%C3%A9s-et-contenu-du-tableau-de-bord h_01HHYHP1HEBTACW6Q3MJ3QJJ95=fonctionnalit%C3%A9s-et-contenu-du-tableau-de-bord h_01HHYHP1HESQBPYJWK81ZHQDVH=metric-definitions h_01HHYHP1HFZBRTWB8MJ1F6XKZS=ex-calcul-de-larpdau h_01HHYHP1HFF92WQMQAFKWWNDJK=detailed-tab h_01HHYHP1HFNDXC2E55Q7PDE9WY=headline-metrics h_01HHYHP1HFZR9JN2H0RNAG1QTK=activity-trends h_01HHYHP1HFV8AZ2FYKJ300488A=activity-summary-table h_01HHYHP1HF6FCXPS2SHTH0RBXC=highlevel-tab-previous-twelvemonths specifications-and-limitations=caract%C3%A9ristiques-et-limitations h_01HHYHP1HFNJF4JJZY4CSVZ3GY=caract%C3%A9ristiques-et-limitations" />
