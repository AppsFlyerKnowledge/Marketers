---
title: Actualisation des données et prise en charge des fuseaux horaires
metadata:
  keywords:
    - Reports
    - Advertisers
    - Agencies
    - Ad Networks
    - timezone
    - data freshness
    - data
    - Developers
    - Gray
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
    - Ad Networks
  created_at: '2018-02-19T15:57:01Z'
  edited_at: '2024-07-02T11:07:28Z'
  id: 360000310629
  locale: fr
  section: The AppsFlyer platform
  section_id: 6551361489297
  url: https://support.appsflyer.com/hc/fr/articles/360000310629
---
> **En bref :** L’actualisation des données représente le temps qui s'écoule entre un événement et la disponibilité de ses données sur la plateforme.

**Fuseaux horaires**

[![TimeZoneMap.jpg](https://files.readme.io/eddfa3df4d43fed82ba5e867eb1278466d1ba51f9fbc2970f62fa61c6659d340-360005463738.jpg)](https://files.readme.io/eddfa3df4d43fed82ba5e867eb1278466d1ba51f9fbc2970f62fa61c6659d340-360005463738.jpg)

## Actualisation des données et prise en charge des fuseaux horaires spécifiques à une application

### Actualisation des données

La plateforme AppsFlyer fonctionne avec différents types [d’actualisation des données,](/docs/about-data-freshness-and-timezone-support#data-freshness-types) exemple : actualisation quotidienne ou en temps réel. L’actualisation sert à présenter les données, et à définir leur disponibilité. Chaque type possède son propre [taux d’actualisation des données](/docs/about-data-freshness-and-timezone-support#data-freshness-rates-and-timezone-support).

Exemple : Taux d’actualisation des données dans le tableau de bord des événements :

* KPI mesuré : en temps réel
* KPI moyen : quotidien

### Fuseaux horaires

Pour la plateforme AppsFlyer, une journée commence à 00:01 et se termine à 24:00. Le fuseau horaire par défaut est l’UTC (GMT). Vous pouvez modifier la valeur par défaut en définissant un fuseau <Anchor target="_blank" href="/marketers/fr/docs/changing-app-time-zone-settings">horaire spécifique à l'app</Anchor>.

<div id="date-and-timezone-principles" />

<Accordion title="Fonctionnements de la date et du fuseau horaire">

L'heure UTC est invariable sur l’année et n'a pas d'heure d'été/hiver.

Hémisphères

* Oriental Les fuseaux horaires désignés par UTC  + sont situés à l'est de l'UTC.
* Occidental Les fuseaux horaires désignés par UTC sont situés à l'ouest de l'UTC.

#### Fuseau horaire spécifique à l'app

Vous pouvez définir un fuseau horaire spécifique à une application. Les données sont alors regroupées en jours, en utilisant l'heure locale au lieu de l'UTC.

Exemple :

**Pékin** Si le fuseau horaire spécifique à l'app est défini sur Pékin (UTC +8), alors la journée commence à 16:01 UTC et se termine à 16:00 UTC le jour suivant.

**Los Angeles** : Si le fuseau horaire spécifique à l'app est défini sur Los Angeles (UTC -8), alors la journée commence à 08:01 UTC et se termine à 08:00 UTC le jour suivant.

#### Consignes à propos des fuseaux horaires

* Alignez le fuseau horaire spécifique à votre app avec celui que vous avez défini pour les autres fournisseurs de services d'attribution, comme Google et Meta Ads.
* Si vous possédez plusieurs apps, nous vous conseillons de régler toutes vos applications sur le même fuseau horaire. Pour afficher les paramètres de fuseau horaire d'une app, allez dans **Paramètres** > **Paramètres de l'app.**
* La plupart des rapports et outils d'extraction des données prennent en charge les fuseaux horaires spécifiques aux apps. Cela inclut les rapports multi-applications lorsque toutes les apps sont définies sur le même fuseau horaire spécifique à l'app.

#### Traitement quotidien

Il existe des rapports et listes déroulantes qui sont traités une fois par jour, c'est ce que l'on appelle l’actualisation quotidienne (ou le traitement quotidien). Voici comment fonctionne le traitement quotidien :

* Les données concernant un jour particulier, par exemple le lundi, sont collectées dans un *compartiment*. La journée commence à 00:01 et se termine à 24:00 (heure spécifique à l'app).
* Les données reçues jusqu'à deux heures après minuit sont comprises dans le compartiment du jour. Les données reçues jusqu'à 2 h le mardi sont incluses dans le compartiment du lundi.
* À 02:00 heure locale, le compartiment est fermé et aucune autre donnée ne peut plus y être ajoutée.
* Les données reçues après 02:00 sont placées dans le compartiment disponible suivant, quelle que soit la date de l'événement.
* Le traitement quotidien du compartiment fermé commence deux heures après minuit UTC, quel que soit le fuseau horaire spécifique à l'app. Pour simplifier les choses, nous annonçons que le traitement commence à minuit UTC. Ce qui signifie que, selon le fuseau horaire local, le compartiment doit attendre minuit UTC avant de démarrer le traitement des données.

**Hémisphère oriental et fuseau horaire UTC** :

![mceclip9b.png](https://files.readme.io/cbea9d910695b39f59b342da6f56fa51df76afc910c4eea60f6dd49fbee2a0d6-8272818122769.png)

* Il peut s’écouler jusqu'à 11 heures entre la fin de la journée (heure locale) et le démarrage du traitement. Exemple :
  * Pékin (UTC+8) : il faut attendre huit heures avant le début du traitement
  * Berlin (UTC +1) : il faut attendre une heure avant le début du traitement
  * UTC : aucune attente
* Selon le type de rapport, les données sont disponibles entre 8 et 20 heures après le démarrage du traitement. Par exemple, les données de Pékin sont disponibles à compter de 16:00, heure locale. Les données de Berlin sont disponibles à partir de 9:00.

**Hémisphère occidental :**

![mceclip7a.png](https://files.readme.io/ac5e3046b3f55916bb73732801c7e0bdef714cc45b89b6c4d70bbc2009cd64c8-8272698121489.png)

* Il peut s'écouler jusqu'à 23 heures entre la fin de la journée et le début du traitement. Exemple :
  * Los Angeles (UTC -8) : il faut attendre 16 heures avant le début du traitement
  * New York (UTC -5) : il faut attendre 19 heures avant le début du traitement
* Selon le type de rapport, les données traitées sont disponibles entre 8 et 20 heures après le démarrage du traitement. Par exemple, les données de Los Angeles sont disponibles à 00:01 heure locale, deux jours après l'événement. Les données de New York sont disponibles à 03:01 heure locale, deux jours après l'événement.
* Exemple :
  * Les événements se produisent le lundi, heure de Los Angeles (UTC -8), le traitement quotidien commence à minuit UTC le mardi. C'est à dire le mardi 16:01 pour Los Angeles.
  * Huit heures plus tard, soit le mercredi à 00:01 heure de Los Angeles, le traitement des données est terminé. Concrètement, les données du lundi sont accessibles aux annonceurs de Los Angeles lorsqu'ils démarrent le mercredi matin.

</Accordion>

<div id="data-freshness-types" />

<Accordion title="Types d'actualisation des données">

| Taux | Disponibilité | Description |
| --- | --- | --- |
| <span id="continuous-aka-realtime"></span>Continu (c'est-à-dire en temps réel) | 15 à 60 minutes après l'événement | Le traitement des données est continu. Ce terme le distingue du traitement par lots qui a lieu, par exemple, quotidiennement. Les données continues sont mises à jour avec un décalage allant de 15 à 60 minutes après l’événement :<ul><li>Attributions (installations, réattributions et réengagements) : 15–30 minutes.</li><li>Évènements in-app : 30–60 minutes.</li></ul> |
| <span id="realtime-report"></span>Rapport en temps réel | Quelques minutes après avoir demandé le rapport | Les données sont mises à jour quelques minutes après l'événement. |
| <span id="daily"></span>Quotidien | **Zone UTC** : 8 heures après minuit UTC le jour de l'événement<br /><br />**Hémisphère oriental** : 9 à 20 heures après minuit UTC le jour de l'événement<br /><br />**Hémisphère occidental** : 21 à 32 heures après minuit UTC le jour de l'événement | <ul><li>Les données sont traitées quotidiennement</li><li>La disponibilité de ces données varie en fonction du fuseau horaire spécifique à l'app</li><li>Les types de données qui ne prennent pas en charge les fuseaux horaires spécifiques aux apps utilisent l'heure UTC</li><li>L’attente avant la mise à disposition des données peut varier, si elle n’est pas indiquée dans des articles spécifiques</li></ul> |
| <span id="eod"></span>EOD | Chaque fin de journée du fuseau horaire spécifique à l'app | À la fin du jour civil. C'est-à-dire 00:01 le jour suivant. Exemple : Les données enregistrées le lundi sont disponibles à compter du mardi à 00:01, quel que soit le fuseau horaire spécifique à l'app. |
| <span id="intraday-during-the-day"></span>Intra-jour (pendant la journée) | Toutes les 4 heures en moyenne | <ul><li>Les données sont collectées six fois par jour, en moyenne toutes les quatre heures.</li><li>Les données SRN des clics et impressions pour les clients qui n’ont pas ROI360, sont collectées 3 fois par jour.</li><li>Les données de coût ETL sont transmises 4 fois par jour, en moyenne toutes les 6 heures.</li></ul> |
| <span id="ad-revenue"></span>Revenus publicitaires | Dépend du type d'intégration et du rapport | <Anchor target="_blank" href="/marketers/fr/docs/roi360-guide-ad-revenue-attribution#data-freshness">Cf l'article sur les revenus publicitaires pour en savoir plus</Anchor>. |
| <span id="pba-daily"></span>PBA quotidienne | Les données sont disponibles 11 à 12 heures après la fin de la journée UTC. | <ul><li>Le tableau de bord et les rapports PBA sont mis à jour [quotidiennement](/docs/about-data-freshness-and-timezone-support#date-and-timezone-principles) en utilisant le fuseau horaire UTC.</li><li>Le traitement quotidien inclut les événements reçus la veille.</li><li>Au cours des sept premiers jours post-conversion, la PBA peut identifier d’autres événements liés à une conversion. Ceci peut donc modifier après coup les KPI et l'attribution de la source média.</li><li>Au bout de sept jours, les chemins sont gelés et plus aucun changement n'a lieu.</li><li>Les rapports de données brutes incluent le champ *final\_data.* Quand les données true sont définitives.</li><li><Anchor target="_blank" href="/marketers/fr/docs/using-pba-dashboards#traits-and-limitations">Exemple détaillé</Anchor></li></ul> |
| <span id="skan"></span>SKAN | <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide#timing-from-app-install-until-dashboard-and-reports-update">Voir les délais</Anchor> entre l’heure d’arrivée des postbacks et la disponibilité des données dans les tableaux de bords et rapports. | Les postbacks reçus un jour donné sont traités en fin de journée UTC. Les données sont disponibles à 11:00 UTC le jour suivant. Les postbacks iOS reçus le lundi sont donc disponibles dans les rapports et les tableaux de bord le mardi matin. De même, les postbacks sont envoyés aux partenaires le mardi matin.<br /><br />La date d'installation dans les rapports et les tableaux de bord correspond à l'heure d'arrivée du postback, comme indiqué dans cet article du <Anchor target="_blank" href="/marketers/fr/docs/skan-conversion-studio#activity-window">studio de conversion conversion SKAN</Anchor>. |
| <span id="data-locker-daily"></span>Data Locker quotidien | Les données sont disponibles de 8 à 10 heures après la fin de la journée UTC | <ul><li>Les données sont traitées quotidiennement.</li><li>Les données sont contenues dans le dossier h=23 correspondant à la date de l'événement. Exemple : les données du lundi comprises dans le dossier h=23 du lundi, sont disponibles le mardi de 8:00 à 10:00 UTC.</li><li>Les données SKAN peuvent arriver un peu plus tard (voir les infos SKAN ci-dessus).</li></ul> |

</Accordion>

<div id="data-freshness-rates-and-timezone-support" />

<Accordion title="taux d’actualisation des données et prise en charge des fuseaux horaires">

<table><thead><tr><th>Données connexes </th><th>Présentation </th><th>Taux d'actualisation des données<br/>(cf la section précédente pour le détail des taux)</th><th>Affichage des données dans le fuseau horaire spécifique à l'app</th></tr></thead><tbody><tr><td><span id="installs"></span><p>Installations</p></td><td>KPI</td><td>En continu</td><td><span>✓</span></td></tr><tr><td><span id="sessions-clicks-impressions-loyal-users"></span><p>Sessions, clics, impressions, utilisateurs fidèles</p></td><td>KPI</td><td><ul><li>Liens d'attribution : En continu</li><li>SRN : Dans la journée</li></ul></td><td><span>✓</span></td></tr><tr><td><span id="revenue-inapp-events"></span><p>Événements in-app / revenus</p></td><td>KPI</td><td><p>En continu</p></td><td><p><span>✓</span></p></td></tr><tr><td><span id="ad-revenue::94fcd383"></span><p>Revenus publicitaires</p></td><td>KPI</td><td><p>Revenus publicitaires</p></td><td><span>✓</span></td></tr><tr><td><span id="ad-spend-cost"></span><p>Dépenses publicitaires (coût)</p></td><td>KPI</td><td><ul><li>Lien d'attribution : En continu (maxi 2 heures après le clic)</li><li>API : Dans la journée</li><li>Ingestion des dépenses publicitaires : Jusqu'à 4 heures après l'ingestion</li></ul></td><td><span>✓</span></td></tr><tr><td><span id="uninstalls"></span><p>Désinstallations</p></td><td>KPI</td><td><p>Quotidiennement. AppsFlyer envoie un ping aux app stores toutes les 24 heures. L'heure de l'événement de désinstallation correspond au moment où AppsFlyer a envoyé un ping à la notification push silencieuse, et a découvert que l'app était désinstallée. Il ne s'agit pas de l'heure réelle de la désinstallation.</p></td><td><strong><span>x</span></strong></td></tr><tr><td><span id="inapp-events-in-the-interface"></span><p>Événements in-app dans l'interface</p></td><td><p>Liste déroulante</p></td><td><p>Les noms des événements in-app affichés dans les listes déroulantes sont mis à jour quotidiennement. </p><p>Cela n’impacte aucunement le taux d’actualisation des données. </p><p><strong>Exemples :</strong> Listes déroulantes des événements in-app dans l'API Push, les tableaux de bord et les audiences.</p></td><td><span>✓</span></td></tr><tr><td><span id="overview-dashboard"></span><p>Vue d'ensemble du tableau de bord </p></td><td>Page</td><td>En continu</td><td><span>✓</span></td></tr><tr><td><span id="protect360-dashboard"></span><p>Tableau de bord Protect360</p></td><td>Page </td><td>Quotidien</td><td> <span>✓ </span>(1)</td></tr><tr><td><span id="skan-dashboard"></span><p>Tableau de bord SKAN</p></td><td>Page</td><td>Quotidien</td><td><span><strong><span>x</span></strong></span></td></tr><tr><td><span id="activity-page"></span><p>Page d'activité </p></td><td>Page</td><td><ul><li>Les KPI : En continu</li><li>Moyennes : À minuit, dans le fuseau horaire spécifique à l'app</li></ul></td><td><p><span>✓</span></p><p>Exception : Les données MAU sont en UTC</p></td></tr><tr><td><span id="events-page"></span><p>Page d'évènements </p></td><td>Page</td><td>En continu</td><td><p><span>✓</span></p></td></tr><tr><td><span id="blank-row"></span>(ligne vide) </td><td> </td><td>(Cette ligne a été laissée vide volontairement)</td><td> </td></tr><tr><td><span id="retention"></span><p>Rétention</p></td><td><p>Page</p></td><td><p>Les KPI de rétention sont disponibles avec une granularité quotidienne et hebdomadaire. L’actualisation des données est différente pour chacun. </p><ul><li>KPI de rétention quotidiens : Quotidien</li><li>KPI de rétention hebdomadaires : La semaine commence le lundi et se termine le dimanche. La rétention est calculée le lundi à 12:00 UTC. L'absence de prise en charge du fuseau horaire spécifique à l'app pour les KPI hebdomadaires entraîne une différence imperceptible. </li></ul></td><td><p>Quotidien : <span>✓</span></p><p>Hebdomadaire : <span><strong>x</strong></span></p></td></tr><tr><td><span id="cohort"></span><p>Cohorte</p></td><td>Page</td><td><p>En continu</p></td><td><p><span>✓ </span>(2)</p></td></tr><tr><td><span id="custom-dashboard"></span><p>Tableau de bord personnalisé</p></td><td>Page</td><td>En continu</td><td><p><span>✓ </span>(3)</p></td></tr><tr><td><span id="audiences"></span><p>Audiences</p></td><td>Page</td><td><ul><li>Les mises à jour sont envoyées aux partenaires toutes les 24 heures.</li><li>La base d'utilisateurs est mise à jour quotidiennement, elle détient jusqu'à 90 jours de données sur l'appareil</li></ul></td><td><span>✓</span></td></tr><tr><td><span id="sdk-information-page"></span><p>Page d'informations du SDK</p></td><td>Page</td><td><p>Quotidien</p></td><td><span> <strong>x</strong></span></td></tr><tr><td><span id="live-alerts"></span><p>Alertes en direct</p></td><td>Page</td><td><ul><li>KPI réguliers : <ul><li>utilisent le fuseau horaire spécifique à l'app</li><li>sont traités à minuit</li><li>sont transmis à 07:00 heure locale</li></ul></li><li>Les alertes Protect360 sont mises à jour quotidiennement en UTC. </li></ul></td><td><span>✓</span></td></tr><tr><td><span id="export-data"></span><p>Données d'exportation</p></td><td>Page</td><td><p>En continu</p><p>Les exceptions :</p><ul><li>Données brutes des revenus publicitaires : Quotidien </li><li>Protect360 : <ul><li>Rapports agrégés : Quotidien</li><li>Données brutes bloquées : En continu</li><li>Données brutes post attribution : Quotidien</li></ul></li><li>Evènements in-app organiques : Mise à jour avec un décalage de plusieurs heures.</li></ul></td><td><p><span>✓</span></p></td></tr><tr><td><span id="pull-api"></span><p>API Pull</p></td><td>API </td><td>L’actualisation des données de l'API Pull est la même que celle des données d'exportation.</td><td><p><span>✓</span></p><p><span>Par défaut UTC</span></p></td></tr><tr><td><span id="pivot"></span><p>Tableau croisé </p></td><td>Page</td><td><p>Quotidien</p></td><td><p><span>✓</span></p><p>KPI de rétention hebdomadaires : <strong><span>x</span></strong></p></td></tr><tr><td><span id="master-api"></span><p>API principale</p></td><td> API</td><td><p>Quotidien </p></td><td><p><span>✓ </span>(3)</p></td></tr><tr><td><span id="data-locker"></span><p>Data Locker</p></td><td>API</td><td>Comme indiqué dans l'article Data Locker. </td><td><p><span><strong>x</strong></span></p><p><font> <strong>UTC</strong> </font></p></td></tr><tr><td><span id="postbacks"></span><p>Postbacks</p></td><td>API</td><td><p>En continu</p></td><td><p>N/A</p></td></tr><tr><td><span id="push-api"></span><p>API Push</p></td><td>API</td><td>En continu</td><td><p><span>✓<br/></span></p><p><span><strong>Les deux</strong></span></p></td></tr><tr><td><span id="servertoserver-inapp-events"></span><p>Evénements in-app de serveur à serveur</p></td><td>API</td><td><p>En continu</p></td><td>N/A</td></tr></tbody><tfoot><tr><td colspan="4"><span id="notes"></span><p>Remarques :</p><p>(1) Toutes les apps autorisées à l'utilisateur doivent utiliser le même fuseau horaire spécifique à l'app. Dans le cas contraire, le fuseau horaire revient en UTC.</p><p>(2) Voir les <a href="./cohort-and-retention-dashboard#traits-and-limitations" target="_blank">Caractéristiques et limitations de la cohorte</a> lorsque le fuseau horaire revient en UTC.</p><p>(3) Toutes les apps sélectionnées doivent utiliser le même fuseau horaire spécifique à l'app. Dans le cas contraire, le fuseau horaire revient en UTC.</p></td></tr></tfoot></table>

</Accordion>

<div data-zendesk-anchors="data-freshness-and-support-for-appspecific-time-zones=actualisation-des-donn%C3%A9es-et-prise-en-charge-des-fuseaux-horaires-sp%C3%A9cifiques-%C3%A0-une-application 01EDBBPAH96ADJ56FRNB34K3VB=actualisation-des-donn%C3%A9es-et-prise-en-charge-des-fuseaux-horaires-sp%C3%A9cifiques-%C3%A0-une-application data-freshness=actualisation-des-donn%C3%A9es 01EDBBPAH9M5KQRXJ1TNN3RJAX=actualisation-des-donn%C3%A9es time-zones=fuseaux-horaires 01EDBBPAH92JJVVGXN61N4SV89=fuseaux-horaires 01EDBBPAH9Z1989ZYYTH0SEDBX=date-and-timezone-principles appspecific-time-zone=fuseau-horaire-sp%C3%A9cifique-%C3%A0-lapp 01EDBBPAH9WHDY875Y913PV00Z=fuseau-horaire-sp%C3%A9cifique-%C3%A0-lapp timezone-guidelines=consignes-%C3%A0-propos-des-fuseaux-horaires 01EDBBPAH9TRH8HBB0JAX2369H=consignes-%C3%A0-propos-des-fuseaux-horaires daily-processing=traitement-quotidien 01EDBBPAH98F0641D934W9NJD8=traitement-quotidien 01EDBBPAHAFSPCYM9JHM0E18NJ=data-freshness-types 01EDBBPAHAA8B8SAK8D64SPKG0=data-freshness-rates-and-timezone-support" />
