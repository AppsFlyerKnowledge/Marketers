---
title: Extraire les données agrégées de l'API
metadata:
  keywords:
    - Performance
    - raw data
    - Pull API
    - Reports
    - API
    - Parameters
    - API Policy
    - Advertisers
    - facebook rawdata
    - facebook raw data
    - Developers
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Raw Reports
  created_at: '2013-04-24T15:08:25Z'
  edited_at: '2023-11-06T08:37:34Z'
  id: 207034346
  locale: fr
  section: Data delivery tools
  section_id: 6550995484561
  url: https://support.appsflyer.com/hc/fr/articles/207034346
---
> **En bref :** utilisez les API Pull pour créer vos rapports agrégés AppsFlyer en fichiers CSV.

[![PullAPIAverage_us-en.png](https://files.readme.io/fb9be34d49394086b37e71d2553d6f926829928a3e1f6cd2ec3e95943ecaa503-360008811078.png)](https://files.readme.io/fb9be34d49394086b37e71d2553d6f926829928a3e1f6cd2ec3e95943ecaa503-360008811078.png)

> 👍 **Vous recherchez les données brutes de l'API Pull ?**
>
> Pour tout savoir sur le sujet rendez-vous <Anchor target="_blank" href="/marketers/fr/docs/pull-api-raw-data">ici</Anchor>.

## Extraire les données agrégées de l'API

* L'API Pull vous permet d'obtenir des rapports de données agrégées pour l'acquisition d'utilisateurs (AU) et le retargeting dans des fichiers CSV.
* Les <Anchor target="_blank" href="/marketers/fr/docs/about-data-freshness-and-timezone-support#data-freshness-rates-and-timezone-support">taux d'actualisation des données</Anchor> sont les mêmes que ceux du rapport équivalent des pages Données d'exportation et Tableau de bord général. La mise à jour du coût peut nécessiter un délai de plusieurs heures, en fonction du partenaire qui fournit les données de coût.
* Filtrer par options disponibles  : source média et plage de dates.
* Les capacités supplémentaires de l'API Pull sont les suivantes :
  * Ajout d'un type de touch d'attribution
  * Sélection du fuseau horaire

#### Les rapports de performance agrégés disponibles via API Pull

<table><tbody><tr><th>Catégorie</th><th> UA</th><th>Retargeting\*</th></tr><tr><td>Partenaires (source média)</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><p>Partenaires par date</p></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><p>Quotidien</p></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><p>Géo</p></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td><p>Rapport géo par date</p></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td colspan="3"><p>\* Pour les rapports de retargeting, ajoutez <code><span>&amp;reattr=true</span></code> à l'URI.</p></td></tr></tbody></table>

<div id="using-pull-api-aggregate-data" />

<Accordion title="Utilisation des données agrégées de l'API Pull">

**Pour utiliser les données agrégées de l'API Pull** :

1. ![AppsFlyerAdmin_us-en.png](https://files.readme.io/5dd980a707877c2ab26826170f7f1313bffba1fed8ab3eacb59954770c302932-19754884868369.png) Obtenez le jeton de l'API. Un administrateur doit récupérer le jeton.
2. Donnez à votre développeur le jeton d'API à utiliser dans l'en-tête d'authentification.
3. Transmettez à vos développeurs les [paramètres](/docs/pull-api-aggregate-data#parameters) à saisir lorsqu'ils effectuent l'appel d'API, tels que décrits ci-dessous. Les paramètres déterminent les points clés du rapport, comment il est organisé, et ils fournissent un calendrier de rapport.
4. Demandez à votre développeur de suivre les instructions relatives aux <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-11">données agrégées de l'API Pull</Anchor> du dev hub.

</Accordion>

<div id="parameters" />

<Accordion title="Paramètres">

| Paramètre | Description |
| --- | --- |
| app\_id | ID de l'app |
| from | <ul><li>La plage de dates se compose des paramètres `FROM`et `TO` . La plage est la plage LTV, la date d'installation.</li><li>Format : `aaaa-mm-jj`,</li><li>Exemple : 2010-01-01</li></ul> |
| to | Date de fin. Comme pour `from` |
| media\_source | À utiliser pour limiter (filtrer) à une source média donnée.<ul><li>Exemple :`media_source=facebook`</li></ul> |
| attribution\_touch\_type | Réglez ce paramètre comme indiqué dans l'exemple pour obtenir les KPI [d'attribution post vue](/docs/pull-api-aggregate-data).<br /><br />Exemple : `attribution_touch_type=impression`<br /><br />Certains KPI d'attribution post vue, comme les clics, les impressions et les API de coût n'ont pas de valeurs associées et affichent la valeur N/A à la place. |
| devise | Devise des revenus et des coûts<br /><br />Les rapports d'API Pull agrégés utilisent toujours la devise spécifique à l'app. |
| reattr | Obtenir les données de conversion de retargeting.<ul><li>Si [Default] est false, les campagnes de données d'acquisition d'utilisateurs (AU) sont renvoyées.</li><li>Si true, les conversions de retargeting sont envoyées.</li><li>**Exemple** :`reattr=true`</li></ul> |
| Fuseau horaire | [Default] Les données sont renvoyées en utilisant le fuseau horaire UTC.<ul><li>Les URI du template sont remplis avec le paramètre de fuseau horaire réglé sur le fuseau horaire spécifique à l'app.</li><li>[Default] Si le paramètre n'est pas envoyé, les données sont renvoyées en utilisant le fuseau horaire UTC.</li><li>Si vous envoyez`timezone=[Joda-Time]`, les données sont retournées en utilisant le fuseau horaire propre à l'app.</li></ul>Remarques sur la sélection des fuseaux horaires<ul><li>Le format de fuseau horaire Joda-Time tient compte de l'heure d'été.</li><li>La valeur Joda-Time doit être identique à la valeur définie à la page des paramètres de l'app. Par exemple, si le fuseau horaire sélectionné est Paris, la valeur du fuseau horaire de l'URL de l'API Pull doit être `timezone=Europe%2fParis`.</li><li>Le regroupement de données dans le fuseau horaire spécifié est uniquement disponible à partir de la date à laquelle le paramètre de fuseau horaire a été défini. Toutes les données antérieures à la date de la modification s'affichent selon le fuseau horaire UTC.</li></ul> |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Particularités et limites">

| Particularité | Commentaires |
| --- | --- |
| Type de jeton API requis | ![AppsFlyerAdmin_us-en.png](https://files.readme.io/5dd980a707877c2ab26826170f7f1313bffba1fed8ab3eacb59954770c302932-19754884868369.png)<Anchor target="_blank" href="/marketers/fr/docs/managing-appsflyer-tokens">Jeton V2.0</Anchor> |
| Accès du réseau publicitaire | N |
| Autorisations de l'agence | Y |
| Transparence de l'agence | Y |
| Devise spécifique à l'app | Y |
| Fuseau horaire spécifique à l'app | Y |
| Coût | Les données de coût concernent uniquement les campagnes UA, elles ne s'appliquent pas aux campagnes de retargeting ou aux campagnes inactives (qui n'ont pas d'installations). |
| Actualisation des données | <Anchor target="_blank" href="/marketers/fr/docs/about-data-freshness-and-timezone-support#continuous-aka-realtime">En continu</Anchor> |
| Données historiques | 5 ans |
| Données non organiques | Y |
| Données organiques | Y |
| Limitations des taux | <Anchor target="_blank" href="/marketers/fr/docs/report-generation-quotas-rate-limitations">Limitation</Anchor> |
| Limitations de taille | <ul><li>Les appels d'API renvoient un max. de 200 000 lignes.</li><li>Si un rapport contient exactement 200 000 lignes, supposez que des lignes sont manquantes.</li><li>Effectuez plusieurs appels d'API, en utilisant des paramètres from/to qui incluent l'heure de la journée.</li></ul>Attention ! Les API Pull ne prennent en charge qu'un million de lignes pour les données brutes. Les rapports de données agrégées sont limités à 200 000 lignes. |
| Changements de nom de campagne | Les rapports API Pull ne prennent pas en charge les changements de nom de campagne |

</Accordion>

> 📄 **À consulter également**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/aggregated-and-analytics-reporting-overview">Descriptions et exemples de rapports agrégés</Anchor>
> * <Anchor target="_blank" href="/marketers/fr/docs/aggregated-and-analytics-reporting-overview">Sélection du bon outil de livraison de données pour les données agrégées</Anchor>

<div data-zendesk-anchors="h_01HE0YP82966QHRAEW979ABCTP=vous-recherchez-les-donn%C3%A9es-brutes-de-lapi-pull- pull-api-aggregate-data=extraire-les-donn%C3%A9es-agr%C3%A9g%C3%A9es-de-lapi h_01HE0YP829WD5TDFHTPYAV30QN=extraire-les-donn%C3%A9es-agr%C3%A9g%C3%A9es-de-lapi aggregate-performance-reports-available-via-pull-api=les-rapports-de-performance-agr%C3%A9g%C3%A9s-disponibles-via-api-pull h_01HE0YP829EQ7N6CST352X917H=les-rapports-de-performance-agr%C3%A9g%C3%A9s-disponibles-via-api-pull h_01HE0YP82954F1ACVR2K4AFD5W=using-pull-api-aggregate-data h_01HE0YP8292131Q2561A4E1GYZ=parameters h_01HE0YP829ZPJAPHPDR9H4HMRT=traits-and-limitations h_01HE0Y2KTXS06WHN57MQ91AD09=%C3%A0-consulter-%C3%A9galement" />
