---
title: >-
  Mesures iOS dans le tableau de bord général (résultats SKAN et AppsFlyer
  accolés)
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-08-02T07:18:18Z'
  edited_at: '2024-08-26T13:38:01Z'
  id: 4404976682257
  locale: fr
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/fr/articles/4404976682257
---
> **En bref :** affichez les mesures des structures d'attribution SKAdNetwork (SKAN) et AppsFlyer les unes à côté des autres dans le tableau de bord général.  Identifiez l’infrastructure qui vous donne les meilleures résultats de campagne, puis utilisez ces informations pour optimiser les campagnes.

**Les mesures d'attribution s'affichent côte à côte dans le tableau de bord Général V2.0**

![SBSDB.png](https://files.readme.io/550c465c329eac484d2b2e5a65c8f48831c350c3c4b967315e3b2059ab95a36d-4409263804049.png)

## Trouver les meilleurs résultats de performance pour les campagnes iOS 14 et +.

À partir d'iOS 14, les structures d'<Anchor target="_blank" href="/marketers/fr/docs/appsflyer-attribution-model">attribution</Anchor> SKAN et <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-attribution-model">AppsFlyer</Anchor> produisent des chiffres liés aux performances des campagnes. Leur attribution, caractéristiques et limitations étant différentes, les mesures ne sont pas toujours les mêmes. Par exemple, SKAN ne contient pas de données sur les campagnes d'Apple Search Ads ni sur les médias propriétaire. Inversement, les données AppsFlyer des SRN n'incluent pas les installations des utilisateurs non consentants. De plus, SKAN mesure les performances sur une fenêtre initiale post-installation de 1 à 3 jours, quand AppsFlyer mesure sur une durée lifetime<Anchor target="_blank" href="/marketers/fr/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">(LTV).</Anchor>

En les affichant côte à côte, vous voyez les performances des campagnes avec les données fournies par les deux structures. En comparant les mesures de chaque structure vous pouvez savoir lesquelles reflètent vraiment les performances d’une campagne.

**Limitation dans le partage des données** : Les mesures SKAN du tableau de bord général ne sont pas disponibles pour les réseaux publicitaires et les agences.

Si les mesures SKAN ne s'affichent pas dans le tableau de bord, vous devez mettre à jour les [paramètres du tableau](/docs/ios-metrics-in-the-overview-dashboard-skan-and-appsflyer-metrics-side-by-side#display-skan-metrics-in-the-table).

L'affichage accolé permet d’analyser les mesures de la campagne. Il vous permet d’évaluer les performances de la campagne en termes de :

* [Précision](/docs/ios-metrics-in-the-overview-dashboard-skan-and-appsflyer-metrics-side-by-side#campaign-precision) :
  * Combien d'installations la campagne a-t-elle provoquées ?
  * Pourquoi les mesures SKAN et AppsFlyer sont-elles différentes ?
* [Efficacité](/docs/ios-metrics-in-the-overview-dashboard-skan-and-appsflyer-metrics-side-by-side#campaign-effectiveness) : combien d'utilisateurs ont été convertis et quel est le ROI ?
* [Efficacité](/docs/ios-metrics-in-the-overview-dashboard-skan-and-appsflyer-metrics-side-by-side#campaign-efficiency): quel est l'eCPI de la campagne ?

Cet article offre des conseils basés sur notre expérience dans le secteur et nos multiples observations sur la manière d'interpréter les données pour en tirer le maximum d’informations. N’oubliez pas que chaque application a son environnement marketing, replacez donc nos conseils dans le cadre de la votre.

**Terminologie**

* **Installation** :
  * AppsFlyer : Nouvelles installations et réattributions
  * SKAN : Nouvelles installations et re-téléchargements
* **Réel/véritable :** Le terme «réel» ou «véritable» indique que la mesure représente le mieux les données, même si elle n'inclut pas toutes les données.
* **Utilisateurs consentants :** Un utilisateur iOS 14+ qui a accordé l'<Anchor target="_blank" href="/marketers/fr/docs/about-att-and-skan#att-principles">autorisation ATT</Anchor> à la fois dans l'app de l'éditeur et dans celle de l'annonceur.

<div id="campaign-precision" />

<Accordion title="Fiabilité des résultats d’une campagne">

| Question | Combien d'installations réelles sont attribuées à une campagne ? |
| --- | --- |
| Problème | Les mesures d'installation diffèrent d'une structure à l'autre. Chaque structure compte une partie des installations, et il peut y avoir des chevauchements et des écarts entre chacune. |
| Solution | <ul><li>Comparez les mesures des installations des structures au niveau de la campagne.</li><li>La structure avec le plus grand nombre d'installations est considéré comme ayant la mesure la plus précise, même si cette mesure n'inclut pas 100 % des attributions.</li></ul> |
| Exemple | ![S2Sinstalls.png](https://files.readme.io/9599ef8ac37aa1bc0da46112c1a7d6b4c42f3ff82efda0d0e4b47b8bddc6b52a-4406110225425.png)<br /><br />Dans le tableau, la structure qui a fourni le plus d'installations a été encadrée. Il s'agit du nombre réel d'installations générées par la campagne. |
| Conseil | Vous pouvez automatiser l’étape visant à repérer la plus grande mesure en important le tableau dans une feuille de calcul. Utilisez la fonction @max et la mise en forme conditionnelle pour identifier la structure qui a rapporté le plus d'installations. |

| Question | Pourquoi les mesures SKAN et AppsFlyer sont-elles différentes ? |
| --- | --- |
| Problème | Les mesures des installations sont différentes. |
| Explication | <ul><li>La structure AppsFlyer détermine les installations selon un <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-attribution-model">modèle d'attribution</Anchor> AppsFlyer qui couvre différents types de campagnes et méthodes d'attribution, tandis que SKAN mesure les installations dans le cadre des campagnes payantes app-to-app.</li><li>Généralement, les mesures SKAN des installations des campagnes SRN sont plus élevées que celles d'AppsFlyer car AppsFlyer n'enregistre que les utilisateurs consentants.</li><li>Dans le cas des réseaux non-SRN (réseaux de clics), on observe souvent une plus grande similitude entre les mesures de chaque structure.</li></ul> |

</Accordion>

<div id="campaign-effectiveness" />

<Accordion title="Efficacité de la campagne">

| Question | combien d'utilisateurs ont été convertis et quel est le ROI ? |
| --- | --- |
| Attention | <ul><li>Pour déterminer les revenus et les taux de conversion, il faut mesurer les performances des utilisateurs au fil du temps.</li><li>SKAN n’effectue les mesures que sur une période allant de 12 à 72 heures après l'installation, tandis qu’AppsFlyer effectue les mesures sans limitation dans le temps (LTV).</li><li>L'attribution d'AppsFlyer ne contient que les mesures des utilisateurs consentants.</li></ul> |
| Solution | Vérifiez si les mesures d'attribution d'AppsFlyer représentent effectivement l'ensemble de la population des utilisateurs (y compris les utilisateurs rapportés via SKAN). Si c'est bien le cas, utilisez les résultats pour obtenir les mesures sur l’efficacité de la campagne,comme le ROI et le taux de conversion.<br /><br />**Pour calculer le nombre d'utilisateurs convertis :**<ol><li>Utilisez le taux de conversion AppsFlyer (par événement).</li><li>Multipliez le taux de conversion par le nombre réel d'utilisateurs, que vous obtenez en suivant les instructions de la section *Fiabilité des résultats d’une campagne*.</li></ol>**Pour calculer les revenus de la campagne et le ROI :**<ol><li>Calculez le nombre réel d'utilisateurs (a), en suivant les instructions de la section *Fiabilité des résultats d’une campagne*.</li><li>Utilisez l’ARPU (b) issu de l’attribution AppsFlyer.</li><li>Calculer les revenus de la campagne avec la formule : a X b</li><li>Utilisez le coût de la campagne tel qu'il s’affiche dans le tableau de bord.</li><li>ROI = (revenus de la campagne - coût de la campagne) / (coût de la campagne X 100)</li></ol> |
| Exemple | **Calcul du ROI**<br /><br />![SBSCost.png](https://files.readme.io/052c862e0a93c4e938f84b22e04e8b088bf50acbf047b821ca6cd20f5b9eae57-4409270882577.png)<br /><br />**Exemple de calcul du ROI pour la campagne a :**<ol><li>Nombre présumé d'utilisateurs : 2000</li><li>ARPU dans le tableau de bord : 0,76$</li><li>Revenus de la campagne = 2000 X 0.76 = 1520$</li><li>Coût de la campagne : 905,88$</li><li>ROI= (1520$- 905.88$) / (905.88$ X 100) = 68%</li></ol> |
| Conseil | Utilisez votre outil d'analyse des produits BI pour comparer les performances des utilisateurs consentants avec celles de l'ensemble des utilisateurs de l'app. Si les résultats diffèrent, vous devez ajuster le calcul de la solution pour en tenir compte. |

</Accordion>

<div id="campaign-efficiency" />

<Accordion title="Efficacité de la campagne">

| Question | Quel est l'eCPI réel de la campagne ? |
| --- | --- |
| Problème | Les mesures liées au coût des campagnes (comme l'eCPI) sont trompeuses car elles reposent sur un nombre précis d'utilisateurs. |
| Solution | <ol><li>Calculez le nombre réel d'utilisateurs (a), en suivant les instructions de la section *Fiabilité des résultats d’une campagne*.</li><li>Calculez l'eCPI à l'aide de la formule suivante : eCPI = coût / (a)</li></ol> |
| Exemple | ![mceclip1.png](https://files.readme.io/98fc80d1e995ba8ef0cce267fa12f22d48a77d7e25db4add1108144c6de7136d-4406111715217.png)<ul><li>Le nombre réel d'installations est donné par la structure avec le plus grand nombre d'installations.</li><li>L'eCPI est calculé à l'aide de la formule suivante : coût/nombre d'installations.</li></ul> |

</Accordion>

## Utilisation de l’affichage accolé

<div id="principles" />

<Accordion title="Principes de base">

* Contient les installations rapportées par les deux structures d'attribution.
* Utilisez la vue unifiée, dans Général V2.0, pour vous assurer que toutes les données disponibles dans une campagne s'affichent, et qu’elles ne sont pas cachées par erreur à cause d’un filtre.
* Les données SKAN sont les mêmes que celles disponibles dans le tableau de bord SKAN.
* Pour réduire les écarts dus aux différentes gestion du temps de chaque structure, définissez dans le tableau de bord une période comme suit :
  * Durée : Minimum 7 jours
  * Date la plus récente :
    * 3 à 5 jours avant le jour en cours. La fourchette dépend de votre fenêtre d'activité
    * Si vous menez des campagnes Google Ads, la date la plus récente doit remonter à moins de 8 jours.

</Accordion>

<div id="display-skan-metrics-in-the-table" />

<Accordion title="Afficher les mesures SKAN dans le tableau">

**Pour afficher les mesures SKAN dans le tableau** :

1. Cliquez sur ⚙ (paramètres du tableau).   
   La fenêtre de sélection des mesures s'ouvre.

   ![SelectSkan.png](https://files.readme.io/6b60fa8e2d10a1b61b1bfb4b7a968adb5ee16086d80c9cc8bc097b8e8ed77b51-4408473842833.png)
2. Cliquez sur **Attribution SKAN**.
3. Cliquez sur **Installations SKAN**.
4. Cliquez sur **Revenus SKAN**.
5. [Facultatif] Pour ajouter ou supprimer un événement in-app :
   1. Sélectionner les évènements in-app.
   2. Ajoutez ou supprimez les événements in-app.
6. Cliquez sur **Appliquer**.   
   Les mesures et événements in-app sélectionnés s'affichent.

</Accordion>

<div id="timerelated-differences" />

<Accordion title="Différences temporelles">

<table><thead><tr><th>Différence</th><th>AppsFlyer</th><th>SKAN</th></tr></thead><tbody><tr><td>Données historiques</td><td><p>Disponible ; pas de limitation</p></td><td><p>Disponible ; pas de limitation </p></td></tr><tr><td>Fuseau horaire</td><td><p>Fuseau horaire propre à l'app</p></td><td>UTC </td></tr><tr><td>Actualisation des données </td><td>Mise à jour continue avec une latence pouvant aller jusqu'à 60 min.</td><td><p><span>Mises à jour quotidienne à 08:00 UTC. </span></p><p><span>La latence dépend de la durée de la fenêtre d'activité. Par défaut : 2 à 5 jours ; dans le cas des campagnes menées par Google Ads, jusqu'à 13 jours.</span></p></td></tr><tr><td>Date d'installation</td><td>Le jour où l’installation a eu lieu </td><td>Découle de l’heure d'arrivée du postback. (1) </td></tr><tr><td>Durée de la mesure</td><td>Illimité ; basée sur la LTV</td><td><p>Limité à la durée de la fenêtre d'activité de 12 à 72 heures. Par défaut : 24 heures.</p></td></tr><tr><td>Fenêtre d'attribution rétrospective</td><td><ul><li>Déterminé par l'annonceur ou le SRN</li><li>Cliquer pour ouvrir : 7 jours</li></ul></td><td><ul><li>Déterminé par Apple</li><li>Clic pour télécharger : 30 jours</li><li>Télécharger pour ouvrir : 60 jours</li></ul></td></tr><tr><td colspan="3"><p>Remarques</p><p>(1) Les données de Google Ads sont mises à jour avec un retard pouvant aller jusqu'à 13 jours.</p></td></tr></tbody></table>

</Accordion>

<div id="cost-clicks-and-impressions" />

<Accordion title="Coûts, clics et impressions">

Les réseaux publicitaires transmettent à AppsFlyer les mesures des coûts, clics et impressions, qui sont communes aux deux structures. Ces mesures ne sont pas séparées par structure.

Dans le cas des mesures de coûts, les règles suivantes s'appliquent :

* Mise à jour 6 fois par jour, en moyenne toutes les 4 heures.
* AppsFlyer enregistre le premier engagement (clic ou impression) associé à une campagne ; ensuite, le coût de la campagne relatif à l'engagement s'affiche.
* Étant donné que les installations SKAN sont rapportées de 72 à 120 heures après la première ouverture de l’app, les mesures des coûts peuvent s’afficher quelques jours avant qu'elles ne soient associées aux installations.
* Pour les installations via Google Ads, le délai peut aller jusqu'à 13 jours.

</Accordion>

<div id="data-scope-differences" />

<Accordion title="Différences dans l'étendue des données">

| Différence | AppsFlyer | SKAN |
| --- | --- | --- |
| Plateforme | Tous | iOS |
| Types d'attribution | <ul><li>Installations</li><li>Réengagements</li><li>Ré-attributions</li></ul> | <ul><li>Installations</li><li>Re-téléchargements</li></ul> |
| Revenus publicitaires | Disponible | <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide#recording-ad-revenue">Limité ; dépend du partenaire de médiation.</Anchor> |
| Apple Search Ads | Disponible | Non applicable à l'attribution SKAN |
| Média propriétaire | Disponible | Non applicable à l'attribution SKAN |
| Web-to-app | Disponible | Disponible pour l'attribution SKAN 4 |
| Devise | Devise propre à l'app | USD |

</Accordion>

<div id="matching-considerations" />

<Accordion title="À propos du matching">

<table><thead><tr><th>Remarque</th><th>AppsFlyer</th><th>SKAN</th></tr></thead><tbody><tr><td>Transparence de l'agence</td><td>Pris en charge</td><td><p>Attribué à la source média qui a porté l'installation. Les agences peuvent demander aux sources média de préfixer les noms de campagne avec leur <em><a href="/partners/fr/docs/getting-started-agency-onboarding" target="_blank">prt</a>, ce qui</em> permet d'identifier le trafic généré par l'agence . </p></td></tr><tr><td>Changements de nom de campagne</td><td><ul><li>Pris en charge</li><li>Le nom le plus récent transmis par le réseau publicitaire indique le nom de la campagne qui sera utilisé pour toutes les installations associées à un ID de campagne donné. Cela comprend les installations déjà enregistrées. </li></ul></td><td><ul><li>Non pris en charge</li><li>On utilise le nom de la campagne rapporté lors de l'installation de l'app par l'utilisateur. Ce nom ne peut pas évoluer ensuite. Par conséquent, plusieurs noms peuvent être associés à un même ID de campagne. </li></ul></td></tr><tr><td>Dimensions prises en charge</td><td>Aucune limite</td><td><p><strong>Disponible :</strong> geo, ad, ID publicitaire, canal, adset, ID de site.</p><p><strong>Agence :</strong> pas pour l’instant.</p><p>Si vous sélectionnez une dimension qui n'est pas prise en charge, les données SKAN s'affichent comme non disponibles.</p></td></tr><tr><td>Mesures des installations SRN</td><td>Limité aux utilisateurs consentants, de fait, les mesures rapportées par AppsFlyer peuvent être inférieures aux mesures rapportées par SKAN, ainsi qu’aux mesures fournies par le SRN lui-même. </td><td>Toutes les installations attribuées à SKAN. Mesure généralement plus élevée que du côté AppsFlyer. </td></tr><tr><td>Campagnes cachées de SKAN</td><td colspan="2"><p>Le tableau contient un nombre limité de lignes. Les lignes restantes sont regroupées dans une ligne désignée comme <em>autres</em>.</p><p>Pour obtenir la répartition de cette ligne, exportez l’entièreté du tableau dans une feuille de calcul. </p></td></tr></tbody></table>

</Accordion>

<div id="dimensions-available" />

<Accordion title="Dimensions disponibles">

Les dimensions suivantes sont disponibles dans l’affichage accolé :

* Source média
* Nom de la campagne
* ID de campagne
* Date
* Type d'attribution

</Accordion>

<div data-zendesk-anchors="finding-the-best-ios-14-campaign-performance-metrics=trouver-les-meilleurs-r%C3%A9sultats-de-performance-pour-les-campagnes-ios-14-et- h_01HYAQAR84BP9MRRXP7BPPDJ4N=trouver-les-meilleurs-r%C3%A9sultats-de-performance-pour-les-campagnes-ios-14-et- h_01HYAQAR856G6VARSH746SJB5Z=campaign-precision h_01HYAQAR856JT2JX28SE3QY7VZ=campaign-effectiveness h_01HYAQAR85GZN1RZYNV2MV7DAP=campaign-efficiency using-sidebyside=utilisation-de-laffichage-accol%C3%A9 h_01HYAQAR85FY6K8R574GWFQW91=utilisation-de-laffichage-accol%C3%A9 h_01HYAQAR85Z09SXSE8JGTG5AMF=principles h_01HYAQAR85V6CD29T9AY9XYX0Z=display-skan-metrics-in-the-table h_01HYAQAR85QSTB8QZPGMEV6MR9=timerelated-differences h_01HYAQAR85A03KNAHC5TEAZAZK=cost-clicks-and-impressions h_01HYAQAR85SPYQKDFP3CRGW5FN=data-scope-differences h_01HYAQAR85FSAXQ25X16N6XQEW=matching-considerations h_01HYAQAR85XF7CEG6F7PC44F1C=dimensions-available" />
