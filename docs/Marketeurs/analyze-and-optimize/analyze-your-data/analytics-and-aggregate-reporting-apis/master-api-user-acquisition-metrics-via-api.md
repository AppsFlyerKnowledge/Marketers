---
title: 'API principale : mesurer l’acquisition d’utilisateurs via API'
metadata:
  keywords:
    - Master API
    - Customizable
    - Aggregated Data
    - Advertisers
    - Developers
    - Premium
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2016-09-27T15:10:38Z'
  edited_at: '2024-09-12T09:05:31Z'
  id: 213223166
  locale: fr
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/fr/articles/213223166
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En bref :** Pour obtenir une certaine partie de la LTV, l’activité, la rétention, la cohorte et des KPI de performance des campagnes Protect360 via API, au format CSV ou JSON. Sélectionner un ou plusieurs événements in-app.

## API principale : mesurer l’acquisition d’utilisateurs via API

API principale :

* Vous permet d’obtenir une certaine partie de la LTV, l’activité, la rétention, la cohorte et des KPI de performance des campagnes Protect360. Les KPI disponibles sont les mêmes KPI que ceux disponibles dans les tableaux de bord Général, d’Activité, de Rétention, de Cohorte et Protect360.
* Le calcul se fait quotidiennement. Les données mises à jour sont disponibles au bout de 24 à 48 heures, en fonction du fuseau horaire spécifique à votre app.
* Il s’agit de l’infrastructure sur laquelle le <Anchor target="_blank" href="/marketers/fr/docs/pivot-table-user-metrics">tableau croisé dynamique</Anchor> AppsFlyer est basé.

Pour utiliser l’API principale, vous devez définir les données que vous souhaitez afficher (comme lorsque vous implémentez<Anchor target="_blank" href="/marketers/fr/docs/pull-api-aggregate-data">l’API Pull</Anchor>). Le résultat est retourné sous forme de fichier CSV ou JSON.

**Pour utiliser l’API principale** :

1. ![AppsFlyerAdmin_us-en.png](https://files.readme.io/11471b4014e8a4805ff15397166298cd02b4df7707bacb62c936f1513dbe34a5-16574754168721.png) Récupérez le <Anchor target="_blank" href="/marketers/fr/docs/managing-appsflyer-tokens">jeton d’API</Anchor>. Seul un admin peut le faire.
2. Donnez à votre développeur le jeton d'API à utiliser dans l'en-tête d'authentification.
3. Transmettez à vos développeurs les paramètres à saisir lorsqu'ils effectuent l'appel d'API, cf détails dans les paragraphes suivants. Les paramètres déterminent les points clés du rapport, comment il est organisé, et ils fournissent un calendrier de rapport.
4. Demandez à votre développeur de suivre les <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-9">instructions concernant l’API principale</Anchor> disponibles dans le dev hub.

<div id="api-parameters" />

<Accordion title="Paramètres de l’API">

| Paramètre | Valeur | Obligatoire |
| --- | --- | --- |
| app\_id | <ul><li>Identifiant d'app, tel qu’il s’affiche dans AppsFlyer.</li><li>Insérez l'ID d'app exactement tel qu’il s’affiche dans AppsFlyer.</li><li>**Ajoutez le préfixe id aux apps IOS**</li><li>Utilisez **tous les ID d’app**pour envoyer des requêtes à l’ensemble de vos apps</li></ul> | Oui |
| from | Seuil le plus bas de la période d'attribution LTV.<ul><li>Format : chaîne aaaa-mm-jj</li><li>Exemple :</li></ul> | Oui |
| to | Seuil le plus élevé de la période d'attribution LTV<ul><li>Nombre de jours dans la période : 1-31 jours</li><li>Pour une seule journée : les valeurs `from` et `to` sont identiques.</li><li>Format : aaaa-mm-jj</li><li>Exemple : `from: 2021-01-01, to: 2021-01-31` fait 31 jours.</li></ul> | Oui |
| [Regroupements](/docs/master-api-user-acquisition-metrics-via-api#groupings) | Regroupez par paramètres, séparés par une virgule. Voir le tableau Regroupements pour la liste des éléments disponibles <br /><br />Exemple :`groupings=pid,geo` | Oui |
| [KPIs](/docs/master-api-user-acquisition-metrics-via-api#kpis) | La liste des KPI à inclure, séparés par une virgule. Cf le tableau des KPI ci-dessous pour voir la liste des KPI.<br /><br />Exemple : `kpis=installs,clicks, impressions,sessions,retention_day_7` | Oui |
| [Filtres](/docs/master-api-user-acquisition-metrics-via-api#filters-optional) | Les données peuvent être filtrées selon une ou plusieurs options de filtrage. | Non |
| [Devise](/docs/master-api-user-acquisition-metrics-via-api#localization) | Pour retourner des données avec la devise spécifique à l’app, indiquez currency=preferred | Non |
| [Fuseau horaire](/docs/master-api-user-acquisition-metrics-via-api#localization) | Pour retourner des données dans le fuseau horaire spécifique à l’app, indiquez timezone=preferred.  Voir [les règles de localisation](/docs/master-api-user-acquisition-metrics-via-api#localization) | Non |
| Format | Par défaut, les données retournées sont reçues au format CSV. Si vous préférez obtenir les données au format JSON, sélectionnez `format=json`. | Non |

</Accordion>

<div id="groupings" />

<Accordion title="Regroupements">

Ces dimensions visent à regrouper les données collectées afin de permettre une lecture plus rapide et précise des informations. Vous trouverez la description de ces champs <Anchor target="_blank" href="/marketers/fr/docs/raw-data-field-dictionary">ici</Anchor>.

<table><thead><tr><th>Regrouper par<br/>nom de l'API</th><th>Regrouper par nom d’affichage</th><th>KPI de LTV</th><th>KPI de rétention</th><th>KPI d'activité</th><th>Protect360</th><th>Cohorte</th></tr></thead><tbody><tr><td><p>app_id</p></td><td><p>ID d'app</p></td><td><p>Oui</p></td><td><p>Oui</p></td><td><p>Oui</p></td><td><p>Oui</p></td><td>Oui</td></tr><tr><td><p>PID</p></td><td><p>Source média</p></td><td><p>Oui</p></td><td><p>Oui</p></td><td><p>Oui</p></td><td><p>Oui</p></td><td>Oui</td></tr><tr><td><p>af_prt</p></td><td><p>agences</p></td><td><p>Oui</p></td><td><p>Oui</p></td><td><p>Oui</p></td><td><p>Oui</p></td><td>Non</td></tr><tr><td><p>C</p></td><td><p>Campagne</p></td><td><p>Oui</p></td><td><p>Oui</p></td><td><p>Oui</p></td><td><p>Oui</p></td><td>Oui</td></tr><tr><td><p>af_adset</p></td><td><p>Adset</p></td><td><p>Oui</p></td><td><p>Oui</p></td><td><p>Oui</p></td><td><p>Non</p></td><td>Non</td></tr><tr><td><p>af_ad</p></td><td><p>Publicité</p></td><td><p>Oui</p></td><td><p>Oui</p></td><td><p>Oui</p></td><td><p>Non</p></td><td>Non</td></tr><tr><td><p>af_channel</p></td><td><p>Canal</p></td><td><p>Oui</p></td><td><p>Oui</p></td><td><p>Oui</p></td><td><p>Oui</p></td><td>Non</td></tr><tr><td><p>af_siteid</p></td><td><p>ID éditeur</p></td><td><p>Oui</p></td><td><p>Oui</p></td><td><p>Oui</p></td><td><p>Oui</p></td><td>Oui</td></tr><tr><td><p>af_keywords</p></td><td><p>Mots-clés</p></td><td><p>Oui</p></td><td><p>Oui</p></td><td><p>Oui</p></td><td><p>Non</p></td><td>Non</td></tr><tr><td><p>is_primary</p></td><td><p>Est une attribution principale</p></td><td><p>Oui</p></td><td><p>Non</p></td><td><p>Oui</p></td><td><p>Oui</p></td><td>Non</td></tr><tr><td><p>af_c_id</p></td><td><p>ID de campagne</p></td><td><p>Oui</p></td><td><p>Non</p></td><td><p>Oui</p></td><td><p>Oui</p></td><td>Non</td></tr><tr><td><p>af_adset_id</p></td><td><p>ID d’adset</p></td><td><p>Oui</p></td><td><p>Non</p></td><td><p>Oui</p></td><td><p>Non</p></td><td>Non</td></tr><tr><td><p>af_ad_id</p></td><td><p>ID publicitaire</p></td><td><p>Oui</p></td><td><p>Non</p></td><td><p>Oui</p></td><td><p>Non</p></td><td>Non</td></tr><tr><td><p>install_time</p></td><td><p>Temps d'installation</p></td><td><p>Oui</p></td><td><p>Oui</p></td><td><p>Oui\*</p></td><td><p>Oui</p></td><td>Oui</td></tr><tr><td><p>attributed_touch_type</p></td><td><p>Type de touch</p></td><td><p>Oui</p></td><td><p>Oui</p></td><td><p>Oui</p></td><td><p>Oui</p></td><td>Non</td></tr><tr><td><p>geo</p></td><td><p>Géo</p></td><td><p>Oui</p></td><td><p>Oui</p></td><td><p>Oui</p></td><td><p>Oui</p></td><td>Oui</td></tr><tr><td colspan="7"><p>\* Dans le cas des KPI d’activité, l’heure d’installation correspond à l’heure de l’événement. </p></td></tr></tbody></table>

</Accordion>

<div id="kpis" />

<Accordion title="Les KPI">

Les KPI sont les métriques qui vous permettent d’obtenir des infos sur le comportement de votre application. Les KPI sont regroupés par type dans les onglets suivants.

<Tabs>
<Tab title="LTV">

Valeur Lifetime - Événements agrégés segmentés par jour d’installation jusqu’au jour présent 

| Nom de l'API de KPI | Description |
| --- | --- |
| impressions | Nombre d'impressions durant la période sélectionnée |
| Clics | Nombre de clics durant la période sélectionnée |
| installs | Nombre d'installations durant la période sélectionnée |
| cr | de l'installation à la première commande |
| Sessions | Nombre de sessions créées par les utilisateurs ont installé l'app durant la période sélectionnée |
| loyal\_users | Nombre d'utilisateurs fidèles qui ont installé l'app durant la période sélectionnée |
| loyal\_users\_rate | Utilisateurs fidèles / Installations |
| cost | Coût total sur la période choisie. [Voir les limitations](/docs/master-api-user-acquisition-metrics-via-api#limitations) |
| revenue | Revenu lifetime généré par les utilisateurs qui ont installé l'app durant la période sélectionnée |
| roi | Retour sur investissement sur une période donnée |
| arpu\_ltv | Revenu moyen par utilisateur, pour les utilisateurs qui ont installé l'app durant la période sélectionnée |
| average\_ecpi | Coût effectif par installation (eCPI) sur une certaine période. Disponible uniquement si le coût et les installations sont inclus dans l’appel. |
| Désinstallations | Les utilisateurs qui désinstallent l'app qu'ils ont installée sur la période sélectionnée |
| uninstalls\_rate | Taux de désinstallation |
| event\_counter\_[event\_name] | Nombre d'événements |
| unique\_users\_[event\_name] | Nombre d'utilisateurs uniques qui ont effectué l'événement |
| sales\_in\_usd\_[event\_name] | Revenus rapportés parmi les événements rapportés |

</Tab>

<Tab title="Rétention">

La rétention mesure combien d'utilisateurs sont actifs dans votre application.

**Remarque :**

* Le nombre maximum de jours de rétention est de 30 jours après l’installation (jour 0 est le jour de l’installation). La valeur [x] ne peut donc pas dépasser 30.
* Si vous lancez une requête pour retention\_day\_1, avant que les données de ce jour ne soient disponibles, le chiffre concernera les utilisateurs qui ont installé l’app le jour précédent. Exemple : le 2 janvier, vous demandez retention\_day\_1 pour les utilisateurs qui ont fait l’installation au 1er janvier. Comme la métrique n’est pas encore disponible, le résultat indique les utilisateurs qui ont installé le 31 décembre.

| KPI | Description |
| --- | --- |
| retention\_day\_[x] | Nombre d'utilisateurs conservés au jour X |
| retention\_rate\_day\_[x] | Nombre d'utilisateurs conservés au jour X sur le nombre total d'utilisateurs qui ont installé l'app |

</Tab>

<Tab title="Activité">

Activité de l'app au cours d'une période sélectionnée. 

| KPI | Description |
| --- | --- |
| activity\_average\_dau | Nombre moyen d'utilisateurs actifs quotidiens (DAU) sur la période sélectionnée |
| activity\_average\_mau | Moyenne mensuelle des utilisateurs actifs durant la période sélectionnée (un jour MAU représente les utilisateurs uniques sur les 30 jours précédents). |
| activity\_average\_dau\_mau\_rate | Taux moyen de DAU / MAU |
| activity\_average\_arpdau | Revenu moyen par utilisateur actif quotidien - le revenu moyen pour un jour donné sur l'ensemble des utilisateurs uniques |
| activity\_sessions | Nombre de sessions réalisées sur la période sélectionnée |
| activity\_revenue | Revenus rapportés sur la période sélectionnée |
| activity\_event\_counter\_[event\_name] | Nombre d'événements générés par les utilisateurs sur la période sélectionnée |
| activity\_sales\_in\_usd\_[event\_name] | Revenus rapportés parmi les événements rapportés sur la période sélectionnée |
| activity\_average\_unique\_users\_[event\_name] | Nombre moyen d'utilisateurs uniques ayant réalisé un événement donné sur la période sélectionnée |

</Tab>

<Tab title="Cohorte">

Les cohortes AppsFlyer offrent aux annonceurs la possibilité d’afficher et de comparer différentes mesures pour plusieurs cohortes, sur des périodes différentes.

**Remarque :**

* **Erreurs d’arrondi :** Les KPI de cohorte par utilisateur sont calculés au dix millième (4 chiffres après la virgule). Cela signifie que si la valeur par utilisateur est inférieure à 0,0001, le résultat affiche 0. Exemple : le nombre d’utilisateurs est 100 000 et le revenu total est 9 $. Le revenu par utilisateur est de 9/100000 = 0,00009. Comme 0,00009 &lt; 0,0001, la valeur affichée sera de 0.
* **Jours de cohorte :** Le nombre maximum de jours de cohorte est de 90 jours après l’installation (jour 0 est le jour de l’installation). La valeur [x] du jour de cohorte doit être comprise entre 1 et 90.  **Remarque** : cohort\_day\_0 n’est pas pris en charge dans l’API Principale, même s’il est pris en charge dans le tableau de bord de Cohorte.
* **API principale V2 et API de cohorte dans le <Anchor target="_blank" href="/marketers/fr/docs/cohort-and-retention-dashboard">tableau de bord de cohorte :</Anchor>** Les résultats peuvent varier en raison d’une gestion différente des réinstallations et des problèmes de synchronisation.

**Sessions**

| KPI | Description |
| --- | --- |
| cohort\_day\_[x]\_total\_sessions\_per\_user | Cohorte Jour x - Nombre cumulé de sessions par utilisateur jusqu'au jour x (jour x inclus) |
| cohort\_day\_[x]\_sessions\_per\_user | Jour x de la cohorte - Sessions du jour x pour la cohorte uniquement |
| cohort\_[x]\_days\_total\_sessions\_per\_user | Remplace dans l'URL Cohort\_day\_1\_total\_sessions\_per\_user par le Cohort\_day\_x\_total\_sessions\_per\_user du KPI.<br /><br />Exemple : cohort\_3\_days\_total\_sessions\_per\_user dans l’URL génère 3 colonnes de rapport :  <br />Cohort\_day\_1\_total\_sessions\_per\_user+ Cohort\_day\_2\_total\_sessions\_per\_user+Cohort\_day\_3\_total\_sessions\_per\_user |

**Revenus**

| KPI | Description |
| --- | --- |
| cohort\_day\_[x]\_total\_revenue\_per\_user | Cohorte Jour x - Total des revenus par utilisateur jusqu'au jour x (jour x inclus) |
| cohort\_day\_[x]\_revenue\_per\_user | Jour x de la cohorte -ARPU accumulé au jour x pour la cohorte uniquement |
| cohort\_[x]\_days\_total\_revenue\_per\_user | Remplace Cohort\_day\_1\_total\_revenue\_per\_user des KPI spécifiées par Cohort\_day\_x\_total\_revenue\_per\_user.<br /><br />Exemple : cohort\_3\_days\_total\_revenue\_per\_user dans l’URL génère 3 colonnes de rapport :  <br />Cohort\_day\_1\_total\_revenue\_per\_user+ Cohort\_day\_2\_total\_revenue\_per\_user+Cohort\_day\_3\_total\_revenue\_per\_user |
| cohort\_day\_[x]\_total\_event\_[eventname]\_revenue\_per\_user | Somme des revenus par utilisateur au jour de cohorte x, selon un événement in-app donné |
| cohort\_day\_[x]\_event\_[eventname]\_revenue\_per\_user | Revenu par utilisateur au jour de cohorte x, selon un événement in-app donné |

**Événements**

| KPI | Description |
| --- | --- |
| cohort\_day\_[x]\_total\_event\_[eventname]\_per\_user | Cohorte Jour x - Total des événements par utilisateur jusqu'au jour x (jour x inclus) |
| cohort\_day\_[x]\_event\_[eventname]\_per\_user | Jour x de la cohorte - Événements accumulés au jour x pour la cohorte uniquement |
| cohort\_[x]\_days\_total\_event\_[eventname]\_per\_user | Remplace les événements des KPI spécifiés par Cohort\_day\_x\_total\_events\_per\_user.<br /><br />Exemple : cohort\_3\_days\_total\_events\_per\_user dans l’URL génère 3 colonnes de rapport :  <br />Cohort\_day\_1\_total\_events\_per\_user+ Cohort\_day\_2\_total\_events\_per\_user+Cohort\_day\_3\_total\_events\_per\_user |

</Tab>

<Tab title="Protect360">

**Les KPI Protect360**

| Description | KPI |
| --- | --- |
| **Installations** |  |
| Total | protect360\_total\_installs |
| Bloqué | blocked\_installs |
| % bloqué | blocked\_installs\_rate |
| Post-attribution | post\_attribution\_installs |
| % post-attribution | post\_attribution\_installs\_rate |
| Nombre total d'installations frauduleuses | total\_fraudulent\_installs |
| % d'installations frauduleuses | fraudulent\_installs\_rate |
| **Fausses installations** |  |
| Blocage en temps réel | real\_time\_fake\_installs |
| Fraude post-attribution | post\_attribution\_fake\_installs |
| **Installations détournées** |  |
| Blocage en temps réel | real\_time\_hijacked\_installs |
| Fraude post-attribution | post\_attribution\_installs\_hijacked\_installs |
| **Règles de validation** |  |
| Installations bloquées | validation\_rules\_blocked\_installs |
| Attribution bloquée | validation\_rules\_blocked\_attribution |
| **Répartition des blocages de fausses installations** |  |
| Liste noire des ID de site bloqués | blocked\_installs\_siteid\_blacklist |
| Liste noire des ID de site post-attribution | post\_attribution\_installs\_siteid\_blacklist |
| Bots bloqués | blocked\_installs\_bots |
| Bots post-attribution | post\_attribution\_installs\_bots |
| Anomalies comportementales bloquées | blocked\_installs\_behavioral\_anomalies |
| Anomalies comportementales post-attribution | post\_attribution\_installs\_behavioral\_anomalies |
| Validation des installations bloquées | blocked\_installs\_install\_validation |
| **Les installations piratées bloquent la répartition** |  |
| Piratage d'installations bloquées | blocked\_installs\_install\_hijacking |
| Piratage d'installations post-attribution | post\_attribution\_installs\_installs\_hijacking |
| Anomalies CTIT bloquées | blocked\_installs\_ctit\_anomalies |
| Anomalies CTIT en post-attribution | post\_attribution\_installs\_ctit\_anomalies |
| Click flooding bloqué | blocked\_installs\_click\_flood |
| Click flooding post-attribution | post\_attribution\_installs\_click\_flood |
| **Clics** |  |
| Total | protect360\_total\_clicks |
| Bloqué | blocked\_clicks |
| % | blocked\_clicks\_rate |
| **Évènement in-app** |  |
| Total | protect360\_total\_in\_apps |
| Bloqué | blocked\_in-app-events |
| % | blocked\_in-app-events\_rate |
| Indicateurs de ferme d'appareils - nouveaux appareils |  |
| Installations | install\_fraud\_new\_devices\_total |
| % installations | install\_fraud\_new\_devices\_total\_installs\_rate |
| % d'utilisateurs fidèles | install\_fraud\_new\_devices\_total\_loyal\_user\_rate |
| **Indicateurs de ferme d'appareils - Appareils LAT** |  |
| Installations | install\_fraud\_lat\_devices\_total |
| % installations | install\_fraud\_lat\_devices\_total\_installs\_rate |
| % d'utilisateurs fidèles | install\_fraud\_lat\_devices\_total\_loyal\_user\_rate |
| **Indicateurs de click flooding** |  |
| de l'installation à la première commande | conversion\_rate |
| **Indicateurs de click flooding - CTIT** |  |
| Plus de 60 minutes | click\_flood\_over\_1\_hour\_rate |
| Plus de 5 heures | click\_flood\_over\_5\_hours\_rate |

</Tab>
</Tabs>

#### Calcul des KPI

En plus des KPI décrits précédemment, vous pouvez ajouter des calculs de KPI à vos rapports de l'API principale. Cela vous permet d'inclure vos propres calculs de rapports dans les rapports de l'API principale.

Vous pouvez insérer autant d’objets KPI intégrés que vous le souhaitez dans les formules de KPI. Chaque objet KPI du calcul contient une clé et une valeur. La clé est le nom que vous donnez au KPI, la valeur est la formule du KPI.

Les opérateurs de calcul standard sont pris en charge : l'addition (+) dont le code est %2b, la soustraction (-), la multiplication (X), la division (/) dont le code est %2f.

Les clés des champs de KPI calculés **doivent** commencer par «calculated\_kpi\_», suivi de n’importe quelle chaîne valide, par exemple «calculated\_kpi\_purchaserate».

> 📄 **Exemple**
>
> Somme des trois premiers jours de rétention
>
> ```http
> kpis=installs,loyal_users_rate&calculated_kpi_3days_retention=
> retention_day_1%2Bretention_day_2%2Bretention_day_3
> ```
>
> Revenu moyen par impression
>
> ```http
> kpis=installs&calculated_kpi_rev_per_impression=revenue%2Fimpression
> ```
>
> ROI au jour 7 de la cohorte
>
> ```http
> kpis=installs,roi,arpu_ltv,cost,revenue&calculated_kpi_roi_day_7=
> (cohort_day_7_total_revenue_per_user-average_ecpi)%2Faverage_ecpi
> ```

</Accordion>

<div id="filters-optional" />

<Accordion title="Filtres (facultatif)">

| Paramètre | Description | Exemple | Obligatoire ? |
| --- | --- | --- | --- |
| pid | <ul><li>Permet de sélectionner les lignes dans lesquelles s’affiche la (ou les) source média spécifiée.</li><li>Il est possible de sélectionner plusieurs lignes (séparées par des virgules).</li></ul> | pid=organic,applovin\_int | Non |
| c | <ul><li>Utilisé pour filtrer par nom de campagne.</li><li>Il est possible de sélectionner plusieurs lignes (séparées par des virgules).</li></ul> | c=my\_sample\_campaign | Non |
| af\_prt | <ul><li>Utilisé pour filtrer par nom d’agence.</li><li>Il est possible de sélectionner plusieurs lignes (séparées par des virgules).</li></ul> | af\_prt=moburst | Non |
| af\_channel | <ul><li>Utilisé pour filtrer par nom de canal.</li><li>Il est possible de sélectionner plusieurs canaux (séparés par des virgules).</li></ul> | af\_channel=Instagram | Non |
| af\_siteid | <ul><li>Utilisé pour le filtrage par ID d’éditeur.</li><li>Il est possible de sélectionner plusieurs ID (séparés par des virgules).</li></ul> | af\_siteid=12345678 | Non |
| geo | <ul><li>Utilisé pour filtrer par pays.</li><li>Il est possible de sélectionner plusieurs pays (séparés par des virgules).</li></ul> | geo=US,DE | Non |

</Accordion>

<div id="localization" />

<Accordion title="Localisation">

La devise locale et le fuseau horaire spécifique à l’app sont définis sur la <Anchor target="_blank" href="/marketers/fr/docs/app-settings">page des paramètres de l’app</Anchor>. Les données de l’API principale peuvent extraire les données en suivant la devise et le fuseau horaire par défaut du système, ou bien le fuseau horaire et la devise spécifiques à l’app.

Ce qui suit s’applique :

* L’utilisation du fuseau horaire ou de la devise spécifique à l’app n’est prise en charge que si toutes les applications ont le même fuseau horaire ou la même devise. Dans le cas contraire, UTC et USD seront utilisés. Le fuseau horaire et la devise sont séparés. Cela signifie que si la devise de toutes les apps est la même, mais que les fuseaux horaires sont différents, vous pouvez utiliser la devise spécifique à l’app, mais pas le fuseau horaire spécifique à l’app.
* Si le fuseau horaire préféré a été modifié dans le tableau de bord pour la période demandée, le rapport généré contient les valeurs produites après le dernier changement de fuseau horaire.

Utilisez les paramètres suivants pour sélectionner le paramètre spécifique à l’app. **Remarque** : Si vous n’utilisez pas de paramètres préférés, vous obtenez les paramètres par défaut, soit USD comme devise et UTC comme fuseau horaire.

| Paramètre | Description | Exemple | Obligatoire ? |
| --- | --- | --- | --- |
| devise | Les valeurs monétaires s'affichent dans la devise de l'app | currency=preferred | Non |
| Fuseau horaire | Le fuseau horaire utilisé est celui du fuseau horaire spécifique à l’app | timezone=preferred | Non |

</Accordion>

## Informations supplémentaires

<div id="limitations" />

<Accordion title="Caractéristiques et limitations">

| Caractéristique | Remarques |
| --- | --- |
| Données de coûts | <ul><li>La disponibilité de certaines dimensions de coût, soit l’adset, la publicité, le géo, le canal et l’ID de site dépendent <Anchor target="_blank" href="/marketers/fr/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">du réseau publicitaire</Anchor>.</li><li>Pour obtenir l’eCPI : Si les données de coût sont disponibles, incluez autant les installations que le coût dans l’appel.</li><li>En général, toutes les sources (y compris les médias propriétaires) qui utilisent des liens AppsFlyer et qui incluent le paramètre de coût dans les liens, prennent entièrement en charge les données de coût, quelles que soient les dimensions demandées. Les réseaux auto-reporting, avec leur propre API, prennent généralement en charge les données de coût, mais avec certaines des dimensions disponibles. Par exemple, <Anchor target="_blank" href="/marketers/fr/docs/meta-ads-faq#what-are-the-limitations-of-facebook-cost-data-in-master-api">les Meta ads</Anchor> ne prennent pas en charge le regroupement par géo et par chaîne dans le même appel. Le regroupement par l’un OU l’autre est par contre pris en charge.</li><li>Les campagnes qui ont des données de coût, mais aucune donnée d’installation dans un passé récent (environ 7 jours), ne sont pas disponibles via l’API principale.</li></ul> |
| Regroupements | Les regroupements spécifiques ne sont disponibles que pour les KPI LTV, les KPI d’activité ou de rétention. L’API renvoie N/A lorsque les données d’un KPI spécifique ne sont pas disponibles. Exemple, la demande de retention\_rate\_day\_7 regroupé par af\_channel renverra N/A. |
| Nombre maximal de lignes par rapport | 200K |
| Noms d'événement | L’API principale ne prend actuellement pas en charge les noms d’événements qui incluent un slash (/)`/`. Pour contourner cette limitation, évitez l’utilisateur de dans les noms d’événements `/`. |
| Délai de traitement | La sélection de plusieurs applications augmente le temps de traitement, la réponse peut donc prendre plus de temps. |
| Période | La granularité temporelle est quotidienne. |
| Agences | API principale non disponible |
| Réseaux publicitaires | API principale non disponible |
| Données historiques | <ul><li>Données LTV : 5 ans</li><li>Données de cohorte (cohorte quotidienne) : 2 ans</li><li>Données d'activité : 3 ans</li></ul> |
| Retargeting | Non pris en charge |

</Accordion>

<div data-zendesk-anchors="master-api%E2%80%94user-acquisition-metrics-via-api=api-principale--mesurer-lacquisition-dutilisateurs-via-api calculated-kpis=calcul-des-kpi additional-information=informations-suppl%C3%A9mentaires" />
