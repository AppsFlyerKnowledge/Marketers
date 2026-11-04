---
title: Données brutes d'API Pull
metadata:
  keywords:
    - Premium
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Raw Reports
  created_at: '2020-04-14T18:24:00Z'
  edited_at: '2023-11-06T08:36:56Z'
  id: 360007530258
  locale: fr
  section: Data delivery tools
  section_id: 6550995484561
  url: https://support.appsflyer.com/hc/fr/articles/360007530258
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En bref :** utilisez cette API pour obtenir des rapports de données brutes en fichiers CSV.

[![PullAPIRaw_us-en.png](https://files.readme.io/1e68c85ee7d41a275ac6e09b35f6913fc10d974fc51c7c9c1357d3fd4d6d561c-33379479618705.png)](https://files.readme.io/1e68c85ee7d41a275ac6e09b35f6913fc10d974fc51c7c9c1357d3fd4d6d561c-33379479618705.png)

<div id="pull-api-raw-data" />

## Données brutes d'API Pull

* L'API Pull permet d'obtenir les rapports de données brutes en fichier de format CSV. <Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview">En savoir plus sur les rapports de données brutes</Anchor>
* Filtrer par options disponibles  : source média, plage de dates, nom de l'événement in-app et géo.
* Les capacités supplémentaires de l'API Pull sont les suivantes :
  * Sélectionner une devise
  * Sélectionner un fuseau horaire

<div id="raw-data-reports-available-via-pull-api" />

#### Rapports de données brutes disponibles via API Pull

<table><tbody><tr><th><span>Rapport</span></th><th><span>Description</span></th><th><span>Fréquence d'actualisation</span></th></tr><tr><td colspan="3"><strong>Rapports de données brutes (non organiques)</strong></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-installs-report-v5" target="_blank">Installations</a></td><td><span>Enregistre les installations non organiques. L’enregistrement est généré lorsqu’un utilisateur ouvre l’app pour la première fois.<br/></span></td><td><span>temps réel</span></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-in-app-events-report-v5" target="_blank">Évènement in-app</a></td><td><span>Enregistre les événements réalisés par les utilisateurs.<br/></span></td><td><span>temps réel</span></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-uninstall-events-report-v5" target="_blank">Désisntallations</a></td><td><span>Enregistre lorsqu’un utilisateur désinstalle l’app.<br/></span></td><td><span>Quotidien</span></td></tr><tr><td><span><a href="https://dev.appsflyer.com/hc/reference/get_app-id-reinstalls-v5" target="_blank">Réinstallations</a><br/></span></td><td><span>Enregistre les utilisateurs qui, après avoir désinstallé l’app, interagissent avec une source média UA puis réinstallent l’app au cours de la fenêtre de réattribution.</span></td><td><span>temps réel</span></td></tr><tr><td colspan="3"> <strong><span>Rapports de données brutes (organiques)</span></strong><br/> </td></tr><tr><td><span><a href="https://dev.appsflyer.com/hc/reference/get_app-id-organic-installs-report-v5" target="_blank">Installations organiques</a><br/></span></td><td><span>Enregistre lorsqu'un utilisateur ouvre l'app pour la première fois.<br/></span></td><td><span>En continu</span></td></tr><tr><td><span><a href="https://dev.appsflyer.com/hc/reference/get_app-id-organic-in-app-events-report-v5" target="_blank">Évènements in-app organiques</a><br/></span></td><td><span>Enregistre les détails des événements réalisés par les utilisateurs.<br/></span></td><td><span>En continu</span></td></tr><tr><td><span><a href="https://dev.appsflyer.com/hc/reference/get_app-id-organic-uninstall-events-report-v5" target="_blank">Désinstallations organiques</a></span></td><td><span>Enregistre les utilisateurs qui désinstallent l’app.<br/></span></td><td><span>Quotidien</span></td></tr><tr><td><span><a href="https://dev.appsflyer.com/hc/reference/get_app-id-reinstalls-organic-v5" target="_blank">Réinstallations organiques</a></span></td><td><span>Enregistre le revenu publicitaire des utilisateurs qui sont attribués à une source média de retargeting au cours de la fenêtre de réengagement.<br/></span></td><td><span>Chaque jour</span></td></tr><tr><td colspan="3"> <strong><span>Données brutes des revenus publicitaires</span></strong><span><br/></span> </td></tr><tr><td> <a href="https://dev.appsflyer.com/hc/reference/get_app-id-ad-revenue-raw-v5" target="_blank">Revenu publicitaire attribué</a><span><br/></span> </td><td>Enregistre le revenu publicitaire des utilisateurs attribués à une source média.</td><td>Quotidien</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-ad-revenue-organic-raw-v5" target="_blank">Revenus publicitaires organiques</a></td><td>Enregistre le revenu publicitaire des utilisateurs non attribués à une source média.</td><td>Quotidien</td></tr><tr><td colspan="3"><span><strong>Antifraude Protect360</strong></span></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-blocked-installs-report-v5" target="_blank">d'installations</a></td><td>Enregistre les installations identifiées comme frauduleuses et par conséquent attribuées à aucune source média.</td><td><span>temps réel</span></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-detection-v5" target="_blank">Installations post-attribution</a></td><td>Enregistre les événements in-app issus d'installations frauduleuses et par conséquent non attribuées.</td><td>temps réel</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-blocked-in-app-events-report-v5" target="_blank">Évènement in-app</a></td><td>Enregistre les événements in-app identifiés comme frauduleux par Protect360.</td><td>Quotidien</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-fraud-post-inapps-v5" target="_blank">Évènements in-app post-attribution</a></td><td>Enregistre les événements in-app des installations identifiées comme frauduleuses après avoir été attribuées à une source média, ou jugées frauduleuses sans égard à l'installation elle-même.</td><td>Quotidien</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-blocked-clicks-report-v5" target="_blank">Clics</a></td><td>Enregistre les clics générés par les utilisateurs bloqués par Protect360.</td><td>Quotidien</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-blocked-install-postbacks-v5" target="_blank">Postbacks d'installations bloquées</a></td><td>Enregistre les copies des postbacks envoyés à la source média à l'origine de l'installation bloquée.</td><td>temps réel</td></tr><tr><td colspan="3"><strong>Les postbacks</strong></td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-postbacks-v5" target="_blank">Postback d'installation</a></td><td>Enregistre les événements d'installation générés lorsqu'un utilisateur ouvre l'app pour la première fois.</td><td>Quotidien</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-in-app-events-postbacks-v5" target="_blank">Postback d'évènements in-app</a></td><td>Enregistre les postbacks d'événements in-app envoyés à la source média.</td><td>Quotidien</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-retarget-in-app-events-postbacks-v5" target="_blank">Postbacks d'évènements in-app de retargeting</a></td><td>Enregistre les événements in-app effectués par les utilisateurs au cours de la fenêtre de réengagement.</td><td>temps réel</td></tr><tr><td><a href="https://dev.appsflyer.com/hc/reference/get_app-id-retarget-install-postbacks-v5" target="_blank">Postbacks de conversion de retargeting</a></td><td>Enregistre les événements in-app effectués par les utilisateurs au cours de la fenêtre de réengagement.</td><td>temps réel</td></tr></tbody></table>

<div id="using-pull-api-raw-data" />

<Accordion title="Utiliser les données brutes de l'API Pull">

**Pour utiliser les données brutes de l'API Pull** :

1. ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) Obtenez le jeton de l'API. Un administrateur doit récupérer le jeton.
2. Donnez à votre développeur le jeton d'API à utiliser dans l'en-tête d'authentification.
3. Transmettez à vos développeurs les paramètres à saisir lorsqu'ils effectuent l'appel d'API, tels que décrits dans les paragraphes suivants. Les paramètres déterminent les points clés du rapport, comment il est organisé, et ils fournissent un calendrier de rapport.
4. Demandez à votre développeur de suivre les instructions relatives aux <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-5">données brutes de l'API Pull</Anchor> du dev hub.

<div id="parameters" />

#### Paramètres

| Paramètre | Description |
| --- | --- |
| from | <ul><li>La plage de dates est définie par les paramètres `from`et `to` . Les dates se rapportent à la date de l'activité.</li><li>Format : `aaaa-mm-jj`, `aaaa-mm-jj hh:mm`, ou `aaaa-mm-jj-hh:mm:ss` Attention ! L'espace doit être encodé comme suit `from=2020-04-01%2001:00:00` -Les navigateurs encodent généralement l'espace.</li><li>Exemple : 2010-01-01 ou 2010-01-01 20:15 (paramètres d'heures et de minutes disponibles pour les rapports de données brutes).</li></ul> |
| to | Date de fin. Comme pour `from` |
| media\_source | `media_source` : pour limiter (filtrer) l'appel à une source média spécifique.<br /><br />Définissez les paramètres `media_source` et `category` comme suit :<ul><li>Pour Meta ads, réglez la catégorie et la source média sur *facebook*</li><li>Pour Twitter, réglez la catégorie et la source média sur *twitter*</li><li>Pour toutes les autres sources média, réglez la catégorie sur *standard* et la source média sur le nom de la source média.</li></ul><ul><li>Exemples<ul><li>`media_source=facebook&category=facebook`</li><li>`media_source=abc_example&category=standard`</li></ul></li></ul> |
| maximum\_rows | Nombre maxi de lignes renvoyées pour chaque appel d'API.<ul><li>[Par défaut] si aucune valeur n'est transmise, le maxi est 200 000 lignes</li><li>200 000 : jusqu'à 200 000 lignes envoyées</li><li>100 0000 : Jusqu'à 100 000 lignes envoyées</li><li>Exemple : `maximum_rows=1000000` permet d'avoir 100 000 lignes disponibles.</li></ul> |
| event\_name | Pour filtrer les événements in-app par évènement spécifique. Pour sélectionner plusieurs événements, créez une liste en les séparant par des virgules.<br /><br />**Exemple** : `event_name=af_purchase,ftd` |
| reattr | Configurer les données d'attribution de retargeting.<ul><li>[Par défaut] si *false*, les campagnes de données d'acquisition d'utilisateurs (AU) sont transmises.</li><li>Si true, les données d'attribution de retargeting sont renvoyées.</li><li>**Exemple** :`reattr=true`</li></ul> |
| additional\_fields | Pour obtenir des champs supplémentaires en plus des champs par défaut. <br /><br />**Exemple** : `additional_fields=device_download_time,deeplink_url` |
| devise | Devise des revenus et des coûts<ul><li>[Par défaut] Si le paramètre n'est pas envoyé, les données sont acheminés en utilisant la devise USD. Cela signifie que si vous ne modifiez rien, les résultats sont transmis en USD.</li><li>Si vous envoyez `currency=preferred`, c'est la devise <Anchor target="_blank" href="/marketers/fr/docs/app-settings#localization-time-zone">spécifique à l'app</Anchor> qui est utilisée. Il s'agit de la devise définie dans les paramètres de l'app.</li></ul>**Exemple** : si la devise spécifique à l'app est EUR, en envoyant  `currency=preferred` ,les valeurs sont transmises en EUR. |
| Fuseau horaire | [Default] Les données sont renvoyées en utilisant le fuseau horaire UTC.<ul><li>Pour obtenir des données dans le fuseau horaire <Anchor target="_blank" href="/marketers/fr/docs/app-settings#localization-time-zone">spécifique à l'app</Anchor>, ajoutez `timezone` à l'appel, comme indiqué ci-dessous :</li></ul><ul><li>`timezone=[Numerical value]`</li><li>Exemple : pour le fuseau horaire UTC+10:00, utilisez`timezone=+10:00` **Attention !** Le `+`,`-`, et `:` doivent être encodés. Exemple : +10:00 s'encode `%2B10%3A00`</li></ul> |
| geo | Filtrer les données par code pays.<br /><br />Limitation : vous ne pouvez définir qu'un seul filtre de code pays par appel d'API. <br /><br />Exemple : `geo=ZA` |
| from\_install time | <ul><li>La plage de dates est définie par les paramètres `from`et `to` . Les dates se rapportent à la date de l'activité.</li><li>Format : `aaaa-mm-jj`</li><li>Exemple : 2010-01-01</li></ul> |
| to\_install\_time | Date de fin. Comme pour `from_install time` |
| agence | Pour limiter (filtrer) l'appel à une agence précise. |

</Accordion>

<div id="protect360-fields" />

<Accordion title="Champs Protect360">

<Anchor target="_blank" href="/marketers/fr/docs/protect360-raw-data-reports#postattribution-reports">Consultez le guide sur les données brutes Protect360</Anchor>

</Accordion>

<div id="time-frame-fields" />

<Accordion title="Champs temporels">

Si les résultats de l'API dépassent le maximum autorisé, divisez le rapport en heures et minutes. Appliquez ce qui suit :

* **from**/**to :** **aaaa-mm-jj hh:mm**
* **from:** 
  * Date uniquement = commence au début (00:00) du jour choisi
  * Date et heure = à partir de 00:00 inclus
* Paramètre **to :** 
  * Date uniquement = termine à la fin (24:00) du jour choisi
  * Date et heure = jusqu'à l'heure indiquée (mais non incluse)

**Exemple :** un propriétaire d'app a 300 000 installations quotidiennes provenant de multiples sources. Pour ne pas dépasser la limite quotidienne de 200 000 lignes, le propriétaire de l'app divise la journée en deux appels d'URI de 12 heures chacun. Cf tableau suivant pour voir les options.

<table><tbody><tr><th>Appel d'API</th><th>De </th><th>À </th></tr><tr><td><strong>Premier appel d'API</strong> </td><td><p><span><strong>depuis=aaaa-mm-jj</strong></span></p><p><span><strong>Exemple :</strong></span></p><ul><li><span><strong>from</strong>=<code>2019-12-29</code></span></li><li><span>Commence la première minute de ce jour à 00:00</span></li></ul></td><td><p><span><strong>jusqu'à</strong>=aaaa</span><span>-mm-jj 12:00</span></p><p><strong>Exemple :</strong> </p><ul><li><span><strong>to</strong>=<code>2019-12-29 12:00</code></span></li><li> <span>Continue jusqu'à 11:59:59 (et non 12:00)</span><span> </span> </li></ul></td></tr><tr><td><p><strong>Option A :deuxième appel d'API</strong> </p><p><span><strong>Exemple :</strong></span><span> </span></p><p><span><strong><kbd><code><kbd>&amp;from=2019-12-29 12:00&amp;to=2019-12-29</kbd></code></kbd></strong></span></p><ul><li><span>Commence à midi (12:00) le 29 déc 2019</span></li><li><span>Se termine à minuit (00:00) le 29 déc 2019</span></li></ul></td><td> <p><span><strong>depuis</strong>=aaaa-mm-jj 12:00</span></p><p><strong>Exemple :</strong> </p><ul><li> <strong>from</strong>=<span><code>2019-12-29 12:00</code></span> </li><li><span>Commence à partir de ce moment, 12:00 inclus</span></li></ul></td><td><p><span> </span></p><p><span><strong>to</strong>=aaa</span><span>a-mm-jj </span></p><p><span><strong>Exemple :</strong> </span></p><ul><li><span><strong>to</strong>=<code>2019-12-29</code></span></li><li><span>Se termine à minuit</span></li></ul><p><span> </span></p></td></tr><tr><td><strong>Option B : deuxième appel d'API</strong></td><td><p><span><strong>depuis</strong>=aaaa-mm-jj 12:00</span></p><p><strong>Exemple :</strong> </p><ul><li> <strong>from</strong>=<span><code>2019-12-29 12:00</code></span> </li><li><span>Commence à partir de ce moment, 12:00 inclus</span></li></ul></td><td><p><span><strong>to</strong>=aaaa-mm-jj+1 00:00</span></p><p><span><strong>+1</strong> = jour suivant à 00:00</span></p><p><strong>Exemple :</strong> </p><ul><li><span><strong>to=<code>2019-12-30 00:00</code></strong></span></li><li>C'est-à-dire avant qu'une seule seconde ne se soit écoulée le 30 décembre.</li></ul></td></tr><tr><td colspan="3"><p><span><strong>Remarque !</strong> Les options A et B donnent les mêmes résultats. </span></p></td></tr></tbody></table>

</Accordion>

<div id="additional-fields" />

<Accordion title="Champs supplémentaires">

Les champs de rapport complémentaires ne sont pas ajoutés à la liste des champs par défaut, et ce afin d'éviter que les nouveaux champs n'affectent vos processus d'importation et d'intégration. Utilisez le paramètre `additional_fields` pour obtenir des champs supplémentaires non disponibles par défaut.

* Ne faites apparaitre chaque champ qu'une seule fois.
* Voir la liste des <Anchor target="_blank" href="/marketers/fr/docs/raw-data-field-dictionary">champs disponibles</Anchor>.
* Exemple : `additional_fields=device_download_time,deeplink_url`

</Accordion>

<div id="default-fields" />

<Accordion title="Champs par défaut">

| Champs de l'API Pull par défaut |
| --- |
| Temps de touch attribué |
| Temps d'installation |
| Heure de l'évènement |
| Nom de l'événement |
| Valeur de l'événement |
| Revenu de l'évènement |
| Devise du revenu des évènements |
| Revenu de l'évènement en USD |
| Source de l'évènement |
| Possède une validation de reçu |
| Partenaire |
| Source média |
| Canal |
| Mots-clés |
| Campagne |
| Identifiant de la campagne |
| Ensemble de publicités |
| Identifiant de l'ensemble de publicités |
| Publicité |
| Identifiant de publicité |
| Type de publicité |
| ID site |
| Identifiant du sous-site |
| Sous-paramètre 1 |
| Sous-paramètre 2 |
| Sous-paramètre 3 |
| Sous-paramètre 4 |
| Sous-paramètre 5 |
| Modèle de coût |
| Valeur des coûts |
| Devise des coûts |
| Partenaire du contributeur 1 |
| Source média du contributeur 1 |
| Campagne du contributeur 1 |
| Type de touch du contributeur 1 |
| Heure de touch du contributeur 1 |
| Partenaire du contributeur 2 |
| Source média du contributeur 2 |
| Campagne du contributeur 2 |
| Type de touch du contributeur 2 |
| Heure de touch du contributeur 2 |
| Partenaire du contributeur 3 |
| Source média du contributeur 3 |
| Campagne du contributeur 3 |
| Type de touch du contributeur 3 |
| Heure de touch du contributeur 3 |
| Région |
| Code pays |
| État |
| city |
| Code postal |
| DMA |
| IP |
| wifi |
| operator |
| carrier |
| langue |
| ID AppsFlyer |
| ID publicitaire |
| idfa |
| ID Android |
| ID utilisateur du client |
| imei |
| IDFV |
| Plate-forme |
| Type d'appareil |
| Version du système d'exploitation |
| Version de l'app |
| Version du SDK |
| ID d'app |
| Nom de l'app |
| ID de groupe |
| Retargeting en cours |
| Type de conversion de retargeting |
| Attribution rétrospective |
| Fenêtre de réengagement |
| Est une attribution principale |
| Agent utilisateur |
| Référent HTTP |
| URL d'origine |

</Accordion>

<div id="additional-information" />

## Informations supplémentaires

<div id="traits-and-limitations" />

<Accordion title="Particularités et limites">

| Particularité | Commentaires |
| --- | --- |
| Type de jeton API requis | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)<Anchor target="_blank" href="/marketers/fr/docs/managing-appsflyer-tokens">Jeton V2.0</Anchor> |
| Accès du réseau publicitaire | Non |
| Autorisations de l'agence | Oui |
| Transparence de l'agence | Oui. Notez cependant que si vous utilisez en même temps un filtre d'agence et un filtre de source média, le filtre de source de média ne s'appliquera pas aux agences non transparentes. Cela signifie que pour les agences non transparentes, toutes les données sont incluses (et pas uniquement les données provenant des sources média filtrées). |
| Devise spécifique à l'app | Oui |
| Fuseau horaire spécifique à l'app | Oui |
| Actualisation des données | <ul><li>A la même valeur que la disponibilité des données du tableau de bord.</li><li>Les rapports sont mis à jour avec un décalage de quelques heures :<ul><li>Rapport In-App Events Organiques</li></ul></li><li>Rapports mis à jour quotidiennement :<ul><li>Désisntallations</li><li>Évènements in-app post-attribution</li><li>Revenus publicitaires</li></ul></li></ul> |
| Données historiques | Oui.  Conformément aux règles de rétention  et de limitation des taux . |
| Données non organiques | Oui |
| Données organiques | Oui |
| Limitation de taux | Limitations de l'API pour les <Anchor target="_blank" href="/marketers/fr/docs/report-generation-quotas-rate-limitations">données brutes</Anchor>. |
| Limitations de taille | <ul><li>Les appels d'API renvoient un max. de 200 000 lignes.</li><li>Si un rapport contient exactement 200 000 lignes, il lui manque probablement des lignes.</li><li>Le paramètre maximum\_rows permet de choisir le nombre maximum de lignes.</li><li>Effectuez plusieurs appels d'API, en utilisant des paramètres from/to qui incluent l'heure.</li></ul> |
| Install\_date from et install\_date\_to | La date d'installation doit être antérieure à la date d'activité. |

</Accordion>

<div id="troubleshooting" />

<Accordion title="Dépannage">

| Problème/message | SOLUTION |
| --- | --- |
| Le rapport ne contient pas les données correspondant à la période définie, ou il y a une différence de résultats entre le rapport de données brutes et le rapport de données agrégées. | Vérifiez que vous avez bien défini le paramètre `timezone`. Si timezone n'est pas configuré, les données sont envoyées en utilisant l'UTC et non le fuseau horaire de votre application. |

</Accordion>

<div id="see-also" />

> 📄 **À consulter également**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">Sélection du bon outil de livraison de données / de la bonne API de création de rapports</Anchor>

<div data-zendesk-anchors="pull-api-raw-data=donn%C3%A9es-brutes-dapi-pull h_01HE7S6WDVJD2XFW498P8FPY7W=donn%C3%A9es-brutes-dapi-pull aggregate-performance-reports-available-via-pull-api=rapports-de-donn%C3%A9es-brutes-disponibles-via-api-pull h_01HE7S6WDV59VTP6Z4X790QDRD=rapports-de-donn%C3%A9es-brutes-disponibles-via-api-pull h_01HE7S6WDVYJ5MAK04VWB4MF6A=using-pull-api-raw-data parameters=param%C3%A8tres h_01HE7S6WDVF8T4719HWDJH8JN1=param%C3%A8tres h_01HE7S6WDVGSS0F116ZB6QVG1N=protect360-fields h_01HE7S6WDVP47A3Q8J7NPH54T5=time-frame-fields h_01HE7S6WDWZ8FR6GRJ40B4CJAV=additional-fields h_01HE7S6WDWMXYF0RHYPF058A9K=default-fields additional-information=informations-suppl%C3%A9mentaires h_01HE7S6WDW9V8XC3CJ0F96EHN0=informations-suppl%C3%A9mentaires h_01HE7S6WDWV87YVJMN76STX7A1=traits-and-limitations h_01HE7S6WDWMZPPTR41VHJQ8MWC=troubleshooting h_01HE7S8S8QCSKRA62A2HVK2MYJ=%C3%A0-consulter-%C3%A9galement" />
