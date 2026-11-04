---
title: A propos du dépassement des dimensions et des limites de cardinalité
metadata:
  keywords:
    - performance reports
    - Advertisers
    - exceeded
    - reports
    - faq
    - Agencies
    - Exceeded_Events_Limit
    - Exceeded Events Limit
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
  created_at: '2017-10-08T15:20:55Z'
  edited_at: '2024-08-22T08:41:44Z'
  id: 115005099063
  locale: fr
  section: Analytics and aggregate reporting/APIs
  section_id: 6550976670225
  url: https://support.appsflyer.com/hc/fr/articles/115005099063
---
> **En bref :** comprendre pourquoi certaines dimensions de données agrégées s'affichent comme *dépassées*, et savoir comment respecter les limites de cardinalité.

<div id="what-are-exceeded-dimensions" />

## Qu’est-ce qui fait qu’une dimension est dépassée ?

AppsFlyer récupère vos données d'installation et d'événement et les agrège. Les données sont agrégées à l'aide des valeurs uniques en lien avec une dimension donnée. Le nombre de valeurs uniques dans une dimension est appelé *cardinalité*. La plupart des outils d'analyse et de reporting agrégés possède une limite de cardinalité par dimension. Lorsque le nombre de valeurs uniques dans une dimension dépasse la limite de cardinalité fixée, les données excédantes sont rassemblées dans un groupe *dépassement.* Et lorsque le nombre de valeurs uniques dans la dimension d’une source de média dépasse la limite de cardinalité, les données restantes de la source de média **ainsi que toutes les dimensions basées sur les sources média restantes** sont rassemblées dans des groupes *dépassement.*

Les exemples suivants détaillent le principe de cardinalité, et vous expliquent comment elle se répercute dans vos rapports.

<div id="example" />

> 📄 **Exemple**
>
> Exemple A : limite de cardinalité de l'ID de campagne
>
> La limite de cardinalité de l'ID de campagne est fixée à 3000. Si le nombre d'ID de campagne rapportés un jour donné dépasse 3000, tous les ID de campagne restants sont regroupés dans le champ Exceeded\_CampaignID\_Limit.
>
> **Exemple B : Limite de cardinalité des événements**
>
> * Supposons que la limite de cardinalité des événements est fixée à 3.
> * Durant un jour donné, 7 événements uniques sont rapportés : A, B, C, D, E, F et G. En d'autres termes : la cardinalité des événements est 7.
> * Dans les rapports agrégés, les événements A, B et C sont affichés séparément. Les événements D, E, F et G sont regroupés dans le champ Exceeded\_Events\_Limit.

Le dépassement des limites des dimensions et de la cardinalité affecte les données agrégées de la manière suivante :

* Tableau de bord général
* Exportation des données agrégées et rapports d’API Pull
* Rapports d’API principale
* Données sur les clics et les impressions dans les tableaux de bord d'activité et personnalisés
* Tableau de bord Protect360

Les données brutes ne sont pas concernées par les limites de cardinalité.

Si une grande partie de vos données est réunie dans des groupes *dépassés*, ces données ne sont pas ventilées. Cela peut donner des résultats incorrects dans les rapports d'analyse. Si besoin est, utilisez les données brutes pour créer des regroupements sans limite de cardinalité.

Le tableau ci-dessous détaille les limites de cardinalité par jour et par application.

<table><tbody><tr><th>Dimension</th><th>Nom du groupe de dépassement</th><th>Type de limite par...</th><th>Limite de cardinalité par jour </th><th>Cardinalité pour Protect360 par jour</th></tr><tr><td>Publicité</td><td>Exceeded_Ad_Limit</td><td>Source média</td><td>1000</td><td>-</td></tr><tr><td>ID publicitaire</td><td>Exceeded_AdID_Limit</td><td>Source média</td><td>1000</td><td>-</td></tr><tr><td>Adset</td><td>Exceeded_AdSet_Limit</td><td>Source média</td><td>1000</td><td>-</td></tr><tr><td>ID d’adset</td><td>Exceeded_AdSetID_Limit</td><td>Source média</td><td>1000</td><td>-</td></tr><tr><td>Campagne</td><td>Exceeded_Campaign_Limit</td><td>Source média</td><td>3000</td><td><ul><li>Installations/événements in-app : 3000</li><li>Impressions/clics : 100 </li></ul></td></tr><tr><td>ID de campagne</td><td>Exceeded_CampaignID_Limit</td><td>Source média</td><td>3000</td><td><ul><li>Installations/événements in-app : 3000</li><li>Impressions/clics : 100 </li></ul></td></tr><tr><td>Canal</td><td>Exceeded_Channels_Limit</td><td>Source média</td><td>20</td><td>20</td></tr><tr><td>ID de site</td><td>Exceeded_SiteID_Limit</td><td>Source média</td><td>1000</td><td><ul><li>Installations/événements in-app : 1000</li><li>Impressions/clics : 100 </li></ul></td></tr><tr><td>Événements</td><td>Exceeded_Events_Limit</td><td>App </td><td>300</td><td>Installations/événements in-app : 300</td></tr><tr><td>Mots-clés</td><td>Exceeded_Keywords_Limit</td><td>Source média</td><td>1000</td><td>-</td></tr><tr><td>Noms des sources média\*</td><td>Exceeded_MediaSource_Limit</td><td>App</td><td>1000</td><td><ul><li>Installations/événements in-app : 1000</li><li>Impressions/clics : 100 </li></ul></td></tr><tr><td colspan="5">\* Si <span>le nombre de valeurs uniques dans la dimension de la source média dépasse la limite de cardinalité, les données restantes de la source média, </span><strong>ainsi que toutes les dimensions basées sur les sources média restantes,</strong><span> sont rassemblées dans des </span><span> groupes </span><em>dépassement.</em> </td></tr></tbody></table>

<div id="cardinality-limits-per-dimension" />

## Limites de cardinalité par dimension

<div id="exceeded_adset_limit-and-exceeded_ad_limit" />

<Accordion title="Exceeded_AdSet_Limit et Exceeded_Ad_Limit">

* Jusqu'à 1000 noms d'adset uniques et 1000 noms de publicité uniques par source média sont possibles.
  * Un jour donné, les informations pour les adsets au-delà du 1001ième sont regroupées dans la source **Exceeded\_AdSet\_Limit.** Il en va de même pour la source **Exceeded\_Ad\_Limit.**

<div id="tip" />

> 👍 **Astuce**
>
> «Diviser pour mieux régner» comme on dit. Définissez un petit nombre de noms d'adset généraux (idéalement jusqu'à 50) et associez tous les noms d'adset précédents à des publicités uniques. Vous pouvez également utiliser les paramètres **af\_sub** dans les liens d'attribution AppsFlyer. Vous pourrez ainsi :
> 1. Eviter de voir s’afficher **Exceeded\_AdSet\_Limit** ou **Exceeded\_Ad\_Limit.** 2. Optimiser en fonction des adsets et du trafic publicitaire.
> 3. Effectuer des analyses approfondies basées sur les adsets et les noms d’adset dans les données brutes.

</Accordion>

<div id="exceeded_adsetid_limit-and-exceeded_adid_limit" />

<Accordion title="Exceeded_AdSetID_Limit et Exceeded_AdID_Limit">

* Il est possible d'utiliser jusqu'à 1 000 ID uniques d’adset et 1 000 ID publicitaires par source média.
  * Un jour donné, les informations pour les ID d’adsets au-delà de 1001 sont regroupées dans la source **Exceeded\_AdSetID\_Limit.** Il en va de même pour la source **Exceeded\_AdID\_Limit.**

</Accordion>

<div id="exceeded_campaign_limit" />

<Accordion title="Exceeded_Campaign_Limit">

**[![](https://files.readme.io/6b96713b7a7ef6dc781fdd6d8b61507788bf79b452cfe2a3aa6fd80d7be71e0b-115016680246.png)](https://files.readme.io/6b96713b7a7ef6dc781fdd6d8b61507788bf79b452cfe2a3aa6fd80d7be71e0b-115016680246.png)**

* Jusqu'à 3000 noms de campagne uniques par jour sont possibles.
  * Un jour donné, les informations des campagnes au delà de la 3001ième sont regroupées dans la source **Exceeded\_Campaign\_Limit.**

<div id="tip-1" />

> 👍 **Astuce**
>
> Définissez un petit nombre de noms de campagne généraux (idéalement jusqu'à 300), et associez tous les noms de campagne précédents à des adsets. Dans les liens d'attribution AppsFlyer, le paramètre est **af\_adset.** Vous pourrez ainsi :
> 1. Eviter de voir s’afficher **Exceeded\_Campaign\_Limit.** 2. Optimiser en fonction du trafic des adsets.
> 3. Effectuer des analyses approfondies basées sur les campagnes et les noms d’adset dans les données brutes.

</Accordion>

<div id="exceeded_campaignid_limit" />

<Accordion title="Exceeded_CampaignID_Limit">

* Jusqu'à 3 000 ID de campagne uniques par jour sont possibles.
  * Au cours d'une même journée, toutes les informations de campagne au delà du 3001ième ID de campagne sont attribuées à la source **Exceeded\_CampaignID\_Limit.**

</Accordion>

<div id="exceeded_channels_limit" />

<Accordion title="Exceeded_Channels_Limit">

* Jusqu'à 20 noms de canal uniques par jour et par source média sont possibles. Pour Protect360, la limite est fixée à 1000.
  * Pour un jour donné, toutes les informations de canal au delà du 21ième canal sont attribuées à la source **Exceeded\_Channel\_Limit.**

</Accordion>

<div id="exceeded_events_limit" />

<Accordion title="Exceeded_Events_Limit">

* Jusqu'à 300 noms d'événements uniques par jour sont possibles.
  * Pour un jour donné, toutes les informations d’événements au delà du 301ième événement sont attribuées au nom d'événement **Exceeded\_Events\_Limit.**

<div id="tip-2" />

> 👍 **Astuce**
>
> Pour ne plus voir s’afficher **Exceeded\_Events\_Limit**, vous pouvez utiliser :
>
> * <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview">Événements in-app riches</Anchor> : Plutôt que de rapporter des centaines d'événements différents, mieux vaut fixer un petit nombre de noms d'événements généraux (idéalement jusqu'à 20). Utilisez des valeurs d'événement dynamiques pour différencier ces événements. Vous pourrez ainsi optimiser selon les paramètres de valeur, et obtenir une analyse basée sur les valeurs des événements (disponibles dans le <Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview">rapport de données brutes des événements in-app).</Anchor>
> * <Anchor target="_blank" href="/marketers/fr/docs/implement-validation-rules-to-prevent-fraud">Règles de validation</Anchor> pour retirer les événements in-app inutiles de la plateforme AppsFlyer.

<div id="example-1" />

> 📄 **Exemple**
>
> Votre application com.greatapp envoie un événement d'achat in-app pour chaque couleur de chaussettes vendue, par exemple, acheter\_chaussettes\_rouges, acheter\_chaussettes\_bleues, acheter\_chaussettes\_blanches, etc. Pour éviter cette profusion d'événements différents, vous pouvez les réduire à un seul événement, acheter\_chaussettes, et insérez la couleur comme un <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview">paramètre de l'événement.</Anchor>

</Accordion>

<div id="exceeded_keywords_limit" />

<Accordion title="Exceeded_Keywords_Limit">

* Jusqu'à 1000 mots-clés uniques par jour et par source média sont possibles.
  * Un jour donné, les informations sur les mots-clés au-delà du 1001ième sont regroupées dans la source **Exceeded\_Keywords\_Limit.**

</Accordion>

<div id="exceeded_mediasource_limit" />

<Accordion title="Exceeded_MediaSource_Limit">

* Jusqu'à 1000 noms de sources média uniques par jour sont possibles.
  * Un jour donné, les informations sur les campagnes au delà du 1001ième nom de source média sont regroupées dans la source **Exceeded\_MediasSource\_Limit.**

</Accordion>

<div id="exceeded_siteid_limit" />

<Accordion title="Exceeded_SiteID_Limit">

* Jusqu'à 1000 ID de site uniques par jour et par source média sont possibles.
  * Un jour donné, les informations sur les ID de site au delà du 1001ième ID par source média, sont regroupées dans un seul ID de site **Exceeded\_SiteID\_Limit.** Si l'ID de site **Exceeded\_SiteID\_Limit** s’affiche, c’est qu'il y a trop d'ID de site utilisés par la source média en question, tenter d'optimiser le trafic de la source en fonction des ID de site sera donc beaucoup moins précis et efficace.

<div id="tip-3" />

> 👍 **Astuce**
>
> «Diviser pour mieux régner». Au lieu d'utiliser des milliers d'ID de site par source média, ce qui risque de fausser vos données agrégées, utilisez un second paramètre **af\_sub\_siteid** dans vos liens d'attribution. Fixez un petit nombre d'ID de sites généraux (idéalement jusqu'à 50), puis attribuez-leur tous les ID de sites précédents en tant qu’ID de sous-sites. Vous pourrez ainsi :
> 1. Eviter de voir s’afficher **Exceeded\_SiteID\_Limit.**
> 2. Optimiser correctement en fonction du trafic des ID de site.
> 3. Effectuer des analyses approfondies basées sur les ID de site et les ID de sous-site dans les données brutes.

<div id="note" />

> 📘 **Remarque**
>
> Dans le rapport de rétention, vous ne voyez pas s’afficher Exceeded\_SiteID\_Limit, mais tous les ID de site ne sont pas listés. Les ID de sites sont affichés de manière aléatoire, mais l'interface utilisateur choisit d’afficher l’ensemble des sites (ceux qui dépassent la limite). Pour éviter ce problème, récupérez les données de rétention depuis l'API principale.

</Accordion>

<div id="how-to-avoid-getting-exceeded-sources" />

## Comment éviter le dépassement des sources ?

<div id="the-long-term-solution" />

### Une solution à long terme

La plupart des annonceurs ne rencontrent pas de **dépassement** de source, car ils définissent rarement 3000 campagnes manuellement.

Si vous avez des **dépassements** de source, c'est probablement parce qu'une ou plusieurs sources média utilisent des valeurs dynamiques dans les noms de campagnes, ID de site, adsets ou publicités. Les événements dynamiques in-app dans le code de l'app peuvent provoquer l'apparition de données **Exceeded\_Events\_Limit.**

<div id="tip-4" />

> 👍 **Astuce**
>
> N'utilisez que des valeurs statiques pour les noms des événements in-app, campagnes, ID de site, adsets et publicités afin d'éviter le **dépassement** de vos sources.
>
> Veuillez également suivre nos conseils ci-dessus pour éviter le **dépassement** de source.

<div id="the-short-term-solution" />

### Une solution à court terme

Mettre en place une solution à long terme peut prendre de quelques jours à quelques semaines.

Mais qu'en est-il si vous souhaitez consulter vos données sans attendre ?

Comme nous l’avons vu, un **dépassement** de source se produit lorsque AppsFlyer reçoit un nombre de clics (ou d’événements) N+1 au cours d'une même journée. Il est possible que les sources média que vous utilisez le plus arrivent plus tard dans la journée et soient mêlées aux données d’un **dépassement** de source. Voici une astuce pour minimiser l'effet de tout **dépassement** de source :

<div id="tip-5" />

> 👍 **Astuce**
>
> Oubliez le jour en cours et ne tenez compte que des données de la veille et l’avant-veille. Chaque jour, un processus d'agrégation recalcule les données du jour précédent et, rétrospectivement, n'attribue que les sources les plus faibles (pas les plus récentes) à tout **dépassement** de source. Cela permet de réduire au minimum les problèmes causés par un débordement de clics !

<div data-zendesk-anchors="what-are-exceeded-dimensions=quest-ce-qui-fait-quune-dimension-est-d%C3%A9pass%C3%A9e- h_01J1VY82KFVMRW99RK0SXWSEZ4=quest-ce-qui-fait-quune-dimension-est-d%C3%A9pass%C3%A9e- h_01J1VY82KFXYA0XCA1XFVTJ2DZ=exemple cardinality-limits-per-dimension=limites-de-cardinalit%C3%A9-par-dimension h_01J1VY82KF5WP6PJQ1MKYPP7YY=limites-de-cardinalit%C3%A9-par-dimension h_01J1VY82KF9XQ08EQ2BH89B6QK=exceeded_adset_limit-and-exceeded_ad_limit h_01J1VY82KFM4VAD4FG5CEKTQK6=astuce h_01J1VY82KFWMF6DN3XNFSWBFHH=exceeded_adsetid_limit-and-exceeded_adid_limit h_01J1VY82KFF7AWBCB54KRPJNS4=exceeded_campaign_limit h_01J1VY82KFBPK2PAHSSMCER6TW=astuce-1 h_01J1VY82KF4TFVTGQ31RCE3QK7=exceeded_campaignid_limit h_01J1VY82KFXPX63XKKKTZ9AWN1=exceeded_channels_limit h_01J1VY82KFRDRVNEAG6S72Q1T4=exceeded_events_limit h_01J1VY82KFYXAXTJ613VAN1PXX=astuce-2 h_01J1VY82KF48N1M8DZ89XQBJTD=exemple-1 h_01J1VY82KFAFK03F3SDJBA5ZNX=exceeded_keywords_limit h_01J1VY82KFV85460FCZB77EY1A=exceeded_mediasource_limit h_01J1VY82KFQG2ZGF91F80X2AAK=exceeded_siteid_limit h_01J1VY82KFMD2DJWDYXF8528CY=astuce-3 h_01J1VY82KFQRVCAW82ZSNJ96G7=remarque how-to-avoid-getting-exceeded-sources=comment-%C3%A9viter-le-d%C3%A9passement-des-sources- h_01J1VY82KFE9E2DNRNPBRQSW22=comment-%C3%A9viter-le-d%C3%A9passement-des-sources- the-long-term-solution=une-solution-%C3%A0-long-terme h_01J1VY82KFDBASKPRK2GJ16FDZ=une-solution-%C3%A0-long-terme h_01J1VY82KFSWQ2Y4WSSASYDFWR=astuce-4 the-short-term-solution=une-solution-%C3%A0-court-terme h_01J1VY82KFR7Z8422MYFK71ET8=une-solution-%C3%A0-court-terme h_01J1VY82KF83SADWJCESRNSJCJ=astuce-5" />
