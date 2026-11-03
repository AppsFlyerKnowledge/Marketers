---
title: Changements de nom de campagne
metadata:
  keywords:
    - Aggregated Data
    - Agencies
    - Ad Networks
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
    - Agencies
    - Ad Networks
  created_at: '2023-03-26T10:56:19Z'
  edited_at: '2024-10-23T11:18:31Z'
  id: 14038324952465
  locale: fr
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/fr/articles/14038324952465
---
> **En bref :** Modifier les noms des campagnes sans créer de doublons dans l'affichage des données.

## Changements de nom de campagne

La modification des noms des campagnes affecte l'affichage des **données agrégées** dans les tableaux de bord et les rapports. AppsFlyer affiche les campagnes en utilisant l'ID de la campagne comme clé. Si plusieurs noms sont associés au même ID de campagne, le nom le plus récent est utilisé pour afficher les données.

* Bien que nous fassions référence aux changements de noms de **campagnes** dans cet article, les mêmes règles s'appliquent aux changements de noms d'adset et de publicités.
* Le changement de nom affecte l'affichage de toutes les données liées à la campagne, y compris les installations, les événements in-app, les coûts et les revenus.
* La plupart des réseaux publicitaires permettent de modifier le nom des campagnes, mais ce n’est pas le cas de tous. Pour ces réseaux spécifiques, vous pourriez voir des lignes en double contenant les mêmes données.
* Les données brutes ne sont pas affectées par les changements de noms.

Le tableau suivant indique les tableaux de bord et les rapports qui prennent en charge les changements de noms de campagnes.

| Tableau de bord/rapport | Prise en charge des changements de noms de campagnes |
| --- | --- |
| Tableau de bord général | Oui, sauf pour l’affichage CTV |
| Tableau de bord d'activité | Oui |
| Tableau de bord des cohortes | Oui |
| API de cohorte | Oui |
| API Pull | Non pris en charge par l’API Pull V5 et les versions inférieures |
| Tableau de bord croisé dynamique | Non |
| Tableau de bord personnalisé | Non |
| Tableau de bord de rétention | Non |
| Tableau de bord des évènements | Non |
| Tableau de bord Protect360 | Non |
| ETL des coûts | Oui |
| Tableau de bord général SKAN | Non |

> 📄 **Exemple**
>
> * Le 1er janvier, la campagne **exemple\_a1** a été lancée.
> * Le 2 janvier, le nom de la campagne est passé d'**exemple\_a1** à **exemple\_a2**.
>
> #### Exemple de données de campagne
>
>
>
> | Date | Nom de la campagne | ID de campagne | Installations | Dépenses publicitaires |
> | --- | --- | --- | --- | --- |
> | 1er janvier | example\_a1 | 123 | 100 | 100 $ |
> | 2 janvier | example\_a2 | 123 | 200 | 200 $ |
>
>
>
> #### Vue d'ensemble du tableau de bord
>
>
>
> <table><tbody><tr><th><p><span>Campagne</span></p></th><th><p><span>ID de campagne</span></p></th><th><p><span>Installations</span></p></th><th><p><span>Dépenses publicitaires</span></p></th></tr><tr><td><p><span>example_a2</span></p></td><td><p><span>123</span></p></td><td><p><span>300</span></p></td><td><p><span>300 $</span></p></td></tr><tr><td colspan="4"><p>Résultat : les données s'affichent sous le nom de la campagne la plus récente.</p></td></tr></tbody></table>

### Recommandations

* La plupart des réseaux publicitaires permettent de modifier le nom des campagnes, mais ce n’est pas le cas de tous. Pour ces réseaux spécifiques, vous pourriez voir des lignes en double contenant les mêmes données. Pour éviter de telles anomalies d'affichage, veillez à ce queles campagnes soient associées à un ID unique.
* Vous ne pouvez pas utiliser le même nom de campagne avec des ID de campagne différents.
* N'utilisez pas le même nom de publicité avec des ID différents.

<div data-zendesk-anchors="rollout-details=changements-de-nom-de-campagne h_01HW896QQ2T4J0N5PDY6YFTJ49=changements-de-nom-de-campagne h_01HW896QQ34YVGF6P212ZHAQHG=exemple example-campaign-data=exemple-de-donn%C3%A9es-de-campagne h_01HW896QQ3G07XM06HR2CRXA3G=exemple-de-donn%C3%A9es-de-campagne overview-dashboard-display-before-the-behavior-change=vue-densemble-du-tableau-de-bord h_01HW896QQ3J9NE9GZRKKAPX46B=vue-densemble-du-tableau-de-bord best-practice=recommandations h_01HW896QQ4RAQ51GPD17YYZBJF=recommandations" />
