---
title: Données modélisées par SKAN
metadata:
  keywords:
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2022-06-23T12:02:02Z'
  edited_at: '2023-10-26T14:41:18Z'
  id: 7086372479505
  locale: fr
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/fr/articles/7086372479505
---
> **En bref** : les modèles AppsFlyer agrègent des données qu'un rapport de base SKAdNetwork ne peut pas produire.

<div id="overview" />

## Présentation

Les rapports de SKAdNetwork (SKAN) peuvent être limités pour les raisons suivantes :

* SKAN s'appuie sur des valeurs de conversion (CV) limitées à 6 bits, ce qui donne 64 valeurs possibles (0-63).
* Apple dissimule parfois la CV réelle (et renvoie les données sous la forme « null ») afin de préserver la confidentialité de l'utilisateur.
* Les données ne sont disponibles qu'à l'intérieur d'une fenêtre d'activité de 12 à 72 heures et la valeur totale de la durée de vie (LTV) n'est pas connue.

Les données modélisées par SKAN résolvent ces problèmes :

* AppsFlyer utilise l'apprentissage automatique, les statistiques bayésiennes, les données rapportées par AppsFlyer et les données SKAN pour modéliser les points de données cachés.
* Les annonceurs ont une vision plus complète de la performance des applications et des campagnes en termes de LTV.

**Remarque** : Lorsque vous modifiez votre schéma de valeurs de conversion, les données sont disponibles sous 2 jours.

<div id="inapp-event-ltv" />

<div id="modeled-data-types-and-availability" />

## Types de données modélisées et disponibilité

| Type de données | Disponibilité | Remarques |
| --- | --- | --- |
| Valeurs de conversion nulles | <ul><li>Tableau de bord général, fenêtre SSOT</li><li>Tableau de bord SKAN</li><li>API de rapport des performances agrégé SKAN</li><li>API de rapport de date d'arrivée de postback agrégé SKAN</li></ul> |  |
| Revenus LTV | Tableau de bord général, fenêtre SSOT | La modélisation des revenus LTV est actuellement limitée à 7 jours |
| Géo | Tableau de bord général, fenêtre SSOT |  |

<div id="null-conversion-values" />

<Accordion title="Valeurs de conversion nulles">

Parfois, la valeur de conversion (CV) est nulle parce qu'Apple ne communique pas la CV réelle afin de préserver la confidentialité des utilisateurs. Dans AppsFlyer, une CV nulle compte comme une installation. N'oubliez pas :

* Les termes « null» et « zero » ont des significations différentes :
  * Zero : l'utilisateur a installé l'application mais n'a effectué aucune action mesurable pendant la fenêtre d'activité. Par conséquent, la métrique est précise et n'est pas modélisée.
  * Null : nous ne savons pas ce que l'utilisateur a fait ; Apple n'a pas communiqué la CV.
* Les CV nulles peuvent fausser vos métriques de performance. Pour remédier à cette distorsion et fournir une mesure plus précise de la performance de l'application, les valeurs de conversion nulles sont modélisées en valeurs de conversion comprises entre 0 et 63.

Valeurs de conversion modélisées :

* Utiliser la distribution des installations SKAN avec les valeurs de conversion pour modéliser les installations nulles. L'algorithme utilisé pour modéliser les données est dynamique et prend en compte plusieurs variables. L'exemple suivant illustre son fonctionnement :
  * Il y a 100 installations, 60 nulles, 10 avec CV=1, 5 avec CV=3, et 25 avec CV=5.
  * Cela signifie que sur les 40 installations avec des valeurs de conversion, 25 % ont une CV=1, 12,5 % une CV=3 et 62,5 % une CV=5.
  * Les 60 installations nulles obtiennent la même distribution modélisée : 15 obtiennent V=1, 7 obtiennent CV=3, et 38 obtiennent CV=5.
* Sont incluses dans les mesures du tableau de bord SKAN et de l'API. Les mesures originales, non modifiées, qui n'incluent pas de données modélisées, sont disponibles avec ces mesures et sont marquées comme *non modélisées*.
* Utilisez des données provenant des niveaux de granularité suivants : App, source média, campagne et adset. Si les données modélisées utilisant ces niveaux ne sont pas disponibles, la valeur N/A s'affiche.

Des mesures modélisées sont disponibles sur la base de la valeur de conversion :

* Revenu
* Nombre d'évènements
* eCPA
* ARPU
* ROI
* ROAS

</Accordion>

<div id="revenue-ltv" />

<Accordion title="Revenus LTV">

<Image align="center" alt="modeled_d7.png" src="https://files.readme.io/ec175800b52164844c56743a33fe412eef02c3b76975ca572819535bb5e5eff9-12183780248081.png" />

Les rapports SKAN peuvent uniquement fournir des revenus basés sur la fenêtre de mesure SKAN et la configuration de la CV pour les revenus dans Conversion Studio. La modélisation SKAN est capable de modéliser les revenus jusqu'à 7 jours (168 heures) après l'installation.

**Avantages :**

Pour la version 3 et les versions antérieures de SKAN, les données modélisées s'étendent au-delà de la période de la fenêtre d'activité.

Pour SKAN version 4+ :

* Rafraîchissement des données : les revenus LTV sont disponibles avant l'arrivée du deuxième postback SKAN (le délai de postback est compris entre 24 et 144 heures).
* Plus de métriques : vous pouvez utiliser la configuration de la valeur brute du deuxième et troisième postback pour d'autres métriques, comme les événements et la fidélisation, tout en obtenant des données sur les revenus LTV grâce à la modélisation.
* Plus de données : si vous utilisez le deuxième postback pour mesurer les revenus, les données du postback sont utilisées pour améliorer les données modélisées des revenus LTV et fournir des données de revenus à un niveau plus granulaire que les 3 niveaux fournis par le postback.

**Attention** :

* Les mesures des revenus LTV s'affichent pour les apps qui ont les revenus globaux configurés dans SKAN Conversion Studio, pour les revenus provenant des achats in-app et les revenus publicitaires.
* Le revenu LTV nécessite au moins 14 jours de données sur le revenu. En d'autres termes, si vous configurez le revenu global le 1er novembre 2022, la première date d'installation pour laquelle des données modélisées sont disponibles est le 14 novembre 2022. Les données s'affichent 8 jours après (22 novembre 2022).
* Les revenus LTV (actuellement limités à 7 jours) et d'autres métriques dérivées sont disponibles dans le tableau de bord SSOT (dans les widgets, les graphiques et les tableaux) le 8e jour après l'installation, comme suit :
  * Revenus j7
  * ARPU J7
  * Bénéfice brut J7
  * ROI J7
  * ROAS j7

</Accordion>

<div id="geo" />

<Accordion title="Géo">

Les postbacks SKAN n'incluent pas la dimension géo. Par conséquent, les données SKAN ne peuvent pas être regroupées par géo en utilisant uniquement les postbacks SKAN. Cependant, AppsFlyer est capable de modéliser les géos d'installation SKAN pour fournir la dimension géo ainsi que le regroupement des données SKAN.

Géos modélisés :

* Utilisent des outils de machine learning qui prennent en compte la distribution géographique pour les installations des campagnes attribuées avec les autres méthodes AppsFlyer.
* Elles sont disponibles via la dimension Géo dans le tableau de bord SSOT.  
  **Remarque** : Si vous regroupez les données à la fois par Géo et par méthode d'attribution, vous pouvez voir les données de chaque géo réparties entre le modèle AF et les données uniques SKAN. Les données uniques SKAN sont modélisées.

Attention :

* La précision de la géo-modélisation chez AppsFlyer est d'environ 90 %. Si la géo ne peut pas être modélisée, l'installation SKAN est classée dans la catégorie Aucune. Aucune signifie que la géo est inconnue.

</Accordion>

<div data-zendesk-anchors="overview=pr%C3%A9sentation 01H8TZR38AC6P264CGF4PX4SJ5=pr%C3%A9sentation modeled-data-types-and-availability=types-de-donn%C3%A9es-mod%C3%A9lis%C3%A9es-et-disponibilit%C3%A9 01H8TZR38A2V9ZSSGKHF3XCX0P=types-de-donn%C3%A9es-mod%C3%A9lis%C3%A9es-et-disponibilit%C3%A9 01H8TZR38A4RDX42B7J5X9SPMQ=null-conversion-values 01H8TZR38BG9XEM2FTJADJ27VK=revenue-ltv 01H8TZR38BSFVDSQCH915ACSYH=geo" />
