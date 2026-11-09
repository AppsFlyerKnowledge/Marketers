---
title: Guide antifraude Protect360
metadata:
  keywords:
    - Advertisers
    - Protect360
    - protect
    - protect 360
    - '360'
    - p360
    - p 360
    - 360protect
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2016-12-06T07:47:17Z'
  edited_at: '2023-11-12T12:53:01Z'
  id: 218254203
  locale: fr
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/fr/articles/218254203
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En bref :** la fraude par attribution épuise les budgets marketing, pollue les données relatives aux performances marketing et peut faire échouer des campagnes prometteuses. **Protect360 fournit aux propriétaires d'app une protection contre la fraude en temps réel et une détection post-attribution**.

<Image align="center" alt="p360intro2.jpg" src="https://files.readme.io/c8476382eeff62164ca93b9bf2f3c4cdbe0609d4160047eac36a44d5f333ffdb-360014803578.jpg" />

<div id="protect360-overview" />

## Présentation de Protect360

* Il s'agit d'une solution de prévention de la fraude liée à l'attribution. Elle regroupe des outils dynamiques capables de détecter la fraude et de bloquer l'attribution frauduleuse.
* Exploite l’étendue, le machine learning et l’analyse comportementale d'AppsFlyer pour offrir une protection contre les formes notoires et nouvelles de fraude au clic/à l'installation, y compris les bots et les anomalies comportementales.
* Protège les marketeurs contre les tentatives de fraude aux niveaux de l'appareil, de l'éditeur et de la source média.
* Utilise une approche par couches de blocage de la fraude en temps réel et d'identification de la fraude post-attribution
* Ne modifie pas l'expérience des utilisateurs de l'app. En cas de tentative de fraude impliquant des utilisateurs réels, les installations de l'app se déroulent normalement, seul l'enregistrement de l'attribution est affecté.

<div id="realtime-blocking" />

<Accordion title="Blocage en temps réel">

* En temps réel, et avant l'attribution, l'installation est identifiée comme provenant d'une source média frauduleuse et est bloquée pour l'attribution.
* Les événements in-app qui s'en suivent sont bloqués s'ils sont issus du même utilisateur.
* Les installations bloquées et les événements in-app sont signalés dans le tableau de bord Protect360 et les rapports de fraude bloquée.
  * Installations bloquées et événements in-app : ne sont pas inclus dans l'attribution et les tableaux de bord d'AppsFlyer car ils n'ont jamais été attribués.
* Les postbacks d'installation bloquée sont transmis aux sources média, avec le motif du blocage, ce qui leur permet une optimisation.

<Anchor target="_blank" href="/marketers/fr/docs/protect360-raw-data-reports">À propos des événements bloqués</Anchor>

</Accordion>

<div id="postattribution-detection" />

<Accordion title="Détection post-attribution">

* Toute fraude identifiée après l'attribution est appelée fraude post-attribution.  Une fraude post-attribution peut être identifiée le jour même de l'installation, et pendant une période de 7 jours suivants (8 jours au total).
* Une fois attribuée, une installation ne peut plus être effacée. Ceci explique pourquoi la fraude post attribution n'est pas traitée comme la fraude en temps réel.
* Les installations et les événements in-app frauduleux identifiés rétrospectivement doivent être traités comme des fraudes avérées et ne doivent pas être facturés.

Une fois qu'une source, par exemple un ad network ou un ID de site, est identifiée comme frauduleuse :

* Les prochains clics provenant de la source sont bloqués.
* Installations passées :
  * Depuis le début du mois calendaire en cours jusqu’à la date du jour, sont qualifiées de fraude post-attribution, mais **ne sont pas supprimées des données**. Depuis janvier 2020, les factures des annonceurs sont créditées des frais d'attribution de ces installations.
  * Celles qui ont eu lieu avant le début du mois en cours ne sont pas modifiées.
* Événements in-app qui se produisent :
  * **Jusqu'à** ce que le libellé d'installation soit étiqueté comme fraude.
  * **Après que** le libellé d'installation a été étiqueté comme fraude.

Exemples de fraude post-attribution :

* Installations apparemment normales suivies de signaux frauduleux dans les évènements in-app.
* Une nouvelle forme de fraude identifiée
* Installations qui se révèlent frauduleuses uniquement une fois que les algorithmes de détection d'anomalies ont collecté suffisamment de données statistiques sur les installations de l'éditeur

</Accordion>

<div id="common-fraud-issues-and-solutions" />

<Accordion title="Principaux problèmes liés à la fraude et solutions">

Lorsque AppsFlyer identifie une fraude, **l'événement** **d'attribution**associé à la fraude est bloqué. Cela altère les profits ainsi que la motivation des fraudeurs. **Remarque**: l'installation de l'app a toujours lieu et n'est pas bloquée. Cela signifie que l'utilisateur de l'app peut utiliser l'application et générer des revenus pour l'annonceur. 

Les clics, installations et évènements in-app frauduleux bloqués sont affichés dans <Anchor target="_blank" href="/marketers/fr/docs/protect360-raw-data-reports">les rapports de données brutes Protect360 sur la fraude</Anchor>.

Le tableau ci-dessous décrit certains types de fraude et détaille comment Protect360 les traite.

| Type de fraude | Description | Solution d'AppsFlyer |
| --- | --- | --- |
| <span id="device-id-reset-fraud"></span>**Fraude à la réinitialisation de l'identifiant de l'appareil** | L'ID d'appareil est constamment réinitialisé par le fraudeur sur le même appareil, afin de générer un très grand nombre d'installations. | AppsFlyer identifie les taux anormaux de nouveaux appareils puis interdit l'accès aux sources qui les fournissent. |
| <span id="install-hijacking"></span>**Piratage d'installations** | Les fraudeurs installent sur les appareils mobiles des logiciels malveillants qui les alertent lors du téléchargement d'une application. Un clic est instantanément envoyé à AppsFlyer afin de demander un crédit pour l'installation. | AppsFlyer bloque les clics attribués via un CTIT (<Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/click-to-install-time-ctit/">Click To Install Time</Anchor>) très rapide, sur la base de l'API côté serveur Google Play. |
| <span id="click-hijacking"></span>**<Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/click-hijacking/">Piratage de clics</Anchor>** | Le logiciel malveillant identifie un clic sur le lien d'attribution de l’installation et envoie instantanément un autre clic qui le crédite s’il est attribué. | Bloque les clics attribués qui suivent de très près d'autres clics pour la même application sur le même appareil. |
| <span id="click-flooding"></span>**<Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/click-flooding/">Click flooding</Anchor>** | Fraude mobile pour laquelle un grand nombre de clics frauduleux sont envoyés, dans le but de transmettre le dernier clic avant les installations. | Bloque les clics attribués à partir d'ID de site présentant un taux de conversion faible et un CTIT long. |
| <span id="behavioral-anomalies"></span>**Anomalies comportementales** | Fraude sur mobile pour laquelle le fraudeur génère une activité post-installation incohérente et anormale. | Notre échelle unique nous permet de suivre et de comprendre les modèles d'engagement comportemental à plusieurs niveaux ; par exemple, par application, région, source média et éditeur. Les comportements non humains sont identifiés en temps quasi réel et bloqués à la source. |
| <span id="ip-denylists"></span>**Liste de rejet d'IP** | Les fraudeurs opèrent généralement à partir de <Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/click-farms/">fermes à clics</Anchor>, qui peuvent être identifiées par leur adresse IP pendant de longues périodes. | <ul><li>AppsFlyer met chaque jour sur liste noire les adresses IP soupçonnées de fraude sur la base des données à jour communiquées par le fournisseur mondial tiers <Anchor target="_blank" href="http://www.digitalelement.com/">Digital Element</Anchor>.</li><li>La protection par liste de rejet d'IP est activée pour toutes les apps.</li></ul> |
| <span id="sdk-authentication"></span>**Authentification SDK** | Les fraudeurs envoient de faux messages SDK pour simuler des actions utilisateur intéressantes. | <ul><li>Nous utilisons un protocole de hachage propriétaire pour crypter les messages internes entre nos SDK et nos services web, empêchant ainsi les fraudeurs de les imiter.</li><li>La protection de l'authentification par SDK est activée pour toutes les apps.</li></ul> |
| <span id="store-validations"></span>**Validations en boutique** | Les fraudeurs envoient de faux messages SDK pour simuler des installations ou des achats in-app afin de pouvoir réclamer des frais CPA élevés. <Anchor target="_blank" href="/marketers/fr/docs/implement-apple-app-store-itunes-install-validation">Validations Apple store</Anchor>. | Active <Anchor target="_blank" href="https://www.appsflyer.com/mobile-fraud-glossary/install-validation/">la validation de l'installation</Anchor> sur iTunes et la validation des achats in-app sur iTunes et Google Play, pour toute installation ou tout achat in-app effectué afin d'empêcher l'attribution d'activités frauduleuses. |

**Remarque** : nous conservons les valeurs de temps exactes mentionnées ci-dessus pour protéger nos clients.

D'autres raisons de blocage sont présentées dans l' <Anchor target="_blank" href="/marketers/fr/docs/protect360-raw-data-reports">article sur les données brutes</Anchor>.

</Accordion>

Le tableau ci-dessous décrit les différents types d'installations frauduleuses et d'événements in-app, et ce qui se passe lorsque le moteur Protect360 les bloque en temps réel, ou bien les détecte post attribution.

<table><caption>Détection de la fraude par Protect360 et résultats</caption><thead><tr><th>Type de fraude</th><th>Délai de détection</th><th>Action niveau installation</th><th>Action niveau événement in-app</th></tr></thead><tbody><tr><td rowspan="2"><span>Fausse installation</span></td><td><span>temps réel</span></td><td><span>Blocage en temps réel</span></td><td><span>Blocage en temps réel</span></td></tr><tr><td><span>Post-attribution</span></td><td><span>Marqué dans le rapport sur les installations post-attribution</span></td><td><ul><li><span>Les événements in-app qui se sont produits avant la détection de la fraude seront notés dans le rapport comme «Événements in-app post-attribution»</span></li><li><span>Après détection : blocage en temps réel</span></li></ul></td></tr><tr><td rowspan="2"><span>Hijacking de l'attribution d'installation</span></td><td><span>temps réel</span></td><td><ul><li><span>Blocage en temps réel</span></li><li><span>L'attribution est corrigée et donnée à la dernière source valide</span></li></ul></td><td><ul><li><span>Apparaît dans le rapport des événements in-app bloqués</span></li><li><span>Attribution à la même source valide que l'installation</span></li></ul></td></tr><tr><td><span>Post-attribution</span></td><td><span>Marqué dans le rapport sur les installations post-attribution</span></td><td><ul><li><span>Les événements in-app qui se sont produits avant la détection de la fraude seront notés dans le rapport comme «Événements in-app post-attribution»</span></li><li><p>Après la détection de la fraude : noté dans le rapport comme étant un <em>événement in-app post-attribution</em> jusqu'à 30 jours après l'installation\*.</p><p>\*Les événements in-app sont corrigés en fonction de la dernière source média valide au cours des 30 jours suivant l'installation. Les événements survenus après plus de 30 jours ne sont pas corrigés.</p></li></ul></td></tr><tr><td rowspan="2"><span>Événement in-app frauduleux</span></td><td><span>temps réel</span></td><td>-</td><td><span>Blocage en temps réel</span></td></tr><tr><td><span>Post-attribution</span></td><td>-</td><td><span>Marqué dans le rapport des événements in-app post-attribution</span></td></tr></tbody></table>

<div id="using-protect360" />

## Utiliser Protect360

<div id="dashboard" />

<Accordion title="Tableau de bord">

<Anchor target="_blank" href="/marketers/fr/docs/protect360-dashboard">Le tableau de bord Protect360</Anchor> affiche des données agrégées sur les fraudes et des informations relatives au trafic frauduleux.

Vues du tableau de bord :

**Installations**  : informations <Anchor target="_blank" href="/marketers/fr/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">basées sur la LTV</Anchor> concernant les installations frauduleuses, bloquées en temps réel et identifiées post attribution.  Vous pouvez approfondir l'analyse des cas de fraude en utilisant les options de filtrage et de regroupement.

**Événements in-app**  : informations <Anchor target="_blank" href="/marketers/fr/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">basées sur l'activité</Anchor> concernant les événements in-app frauduleux, bloqués en temps réel et identifiés post attribution.  Vous pouvez approfondir l'analyse des cas de fraude en utilisant les options de filtrage et de regroupement.

Anomalies : fournit des informations sur les sources média dont les installations contiennent des valeurs CTIT (Click To Install Time, durée entre le clic et l'installation) anormales par rapport aux autres sources de confiance.

* Comparez les éléments entre les installations suspectes et vos données d'installations brutes, puis recherchez les élements suspects, tels que les numéros inhabituels de version d'app, les anciennes versions de système d'exploitation, les emplacements caractéristiques, etc.
* Vous pouvez également utiliser la fonction <Anchor target="_blank" href="/marketers/fr/docs/implement-validation-rules-to-prevent-fraud#protect360-install-and-inapp-event-sources">Règles de validation</Anchor> pour bloquer les installations qui ont des valeurs CTIT courtes. N'oubliez cependant pas que Protect360 bloque automatiquement les installations présentant des valeurs CTIT très courtes).

</Accordion>

<div id="raw-data" />

<Accordion title="Données Brutes">

Les <Anchor target="_blank" href="/marketers/fr/docs/protect360-raw-data-reports">données brutes</Anchor> sur la fraude sont disponibles via l'API Pull, les données d'exportation et <Anchor target="_blank" href="/marketers/fr/docs/data-locker-for-marketers">Data Locker (fonctionnalité premium)</Anchor>.

Les rapports de données brutes sont répartis comme suit :

* Rapports bloqués : installations, clics et événements in-app des utilisateurs dont l'attribution a été bloquée et qui n'ont été attribués à aucune source média.
* Rapports post-attribution :
  * Installations attribuées à une source média, mais qui se sont révélées frauduleuses par la suite.
  * Évènements in-app :
    * des installations identifiées comme frauduleuses après avoir été attribuées à une source média.
    * jugée frauduleuse sans égard à l'installation elle-même.

* Les annonceurs utilisent ces rapports pour rapprocher les comptes des réseaux publicitaires, à des fins d'optimisation, et pour ajuster les tableaux de bord d'attribution en ce qui concerne la fraude post-attribution.

</Accordion>

<div id="validation-rules" />

<Accordion title="Règles de validation">

Les <Anchor target="_blank" href="/marketers/fr/docs/implement-validation-rules-to-prevent-fraud">règles de validation</Anchor> permettent aux propriétaires d'apps de définir des conditions pour bloquer certaines installations, bloquer l'attribution (et s'assurer que les installations sont attribuées à la source média valide la plus récente) ou bloquer les événements in-app.

</Accordion>

<div id="fraud-reconciliation-with-ad-networks" />

<Accordion title="Conciliation de la fraude avec les réseaux publicitaires">

Avec Protect360, les annonceurs obtiennent les données brutes relatives aux installations frauduleuses et aux événements in-app que les ad networks n'ont peut-être pas enregistrés comme fraudes.

Si vous découvrez qu'un ad network vous a envoyé du trafic à partir de sources suspectes, informez-le et demandez-lui d'arrêter de vous envoyer du trafic à partir de ces sources. Utilisez la colonne du rapport de données brutes relatives aux installations intitulée **Temps de contact attribué** pour vérifier qu'aucune autre installation n'est reçue de la source après votre demande d'arrêt.

Vous pouvez également utiliser les données Protect360 pour faire le point avec des ad networks et recevoir des remboursements complets ou partiels pour le trafic passé provenant de sources suspectes.

**Pour concilier les campagnes basées sur le CPI en utilisant Protect360 :**

* Au début de chaque mois, contactez votre responsable de compte pour chacun des ad networks ayant subi une fraude.
* Rassembler les données brutes des installations frauduleuses concernées à partir des installations bloquées et des rapports d'[installations post-attribution](/docs/protect360-anti-fraud-guide#postattribution-detection).
* Partagez les données brutes des fraudes avec le réseau à des fins de rapprochement et d'optimisation du trafic.
* Il est possible de générer un rapport de données brutes incluant uniquement les installations valides mais excluant les installations frauduleuses post-attribution. Pour ce faire, vous devez télécharger le rapport mensuel des ***Installations d'UA attribuées*** et exclure toutes les entrées du ***rapport*** des installations post-attribution.

**Pour concilier les campagnes basées sur le CPA/CPE en utilisant Protect360 :**

* Au début de chaque mois, contactez votre responsable de compte pour chacun des ad networks ayant subi une fraude.
* Rassembler les données brutes pertinentes sur les événements in-app frauduleux à partir des événements in-app bloqués et des rapports [d'événements in-app](/docs/protect360-anti-fraud-guide#postattribution-detection) post-attribution.
* Partagez les données brutes des fraudes avec le réseau à des fins de rapprochement et d'optimisation du trafic.
* Il est possible de générer un rapport de données brutes incluant uniquement les IAE valides mais excluant les événements frauduleux post-attribution. Pour ce faire, vous devez télécharger le rapport mensuel des ***Événements in-app UA attribuées*** et exclure toutes les entrées du ***rapport*** des événements in-app post-attribution.

</Accordion>

<div id="traits-and-limitations" />

## Particularités et limites

<div id="traits-and-limitations::a07033c3" />

<Accordion title="Particularités et limites">

| Particularité | Remarques |
| --- | --- |
| Accès des annonceurs | Tous les utilisateurs du compte. |
| Accès du réseau publicitaire | <ul><li>L'accès au tableau de bord Protect360 et aux données brutes requièrent <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#autorisations-pour-le-réseau-publicitaire">l'autorisation de l'annonceur.</Anchor></li><li>L'annonceur doit avoir l'ad network comme partenaire intégré.</li></ul> |
| Autorisations de l'agence | L'accès au tableau de bord Protect360 et aux données brutes requièrent <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#autorisations-pour-le-réseau-publicitaire">l'autorisation de l'annonceur.</Anchor> |
| Transparence de l'agence | Agence transparente : peut voir des sources média spécifiques<br /><br />Agence non transparente : ne peut pas voir des sources média spécifiques |
| Fuseau horaire spécifique à l'app | <ul><li>Le fuseau horaire spécifique à l'app est utilisé dans le tableau de bord, sous réserve que toutes les apps soient définies sur le même fuseau horaire.</li><li>Si les apps ne sont pas réglées sur le même fuseau horaire, alors le tableau de bord est réglé par défaut sur UTC.</li></ul> |
| Actualisation des données | <ul><li>Tableau de bord Protect360 : mise à jour <Anchor target="_blank" href="/marketers/fr/docs/about-data-freshness-and-timezone-support#eod">Quotidienne</Anchor>.<br />L'heure de la toute dernière mise à jour s'affiche dans le filtre des périodes du tableau de bord.</li><li>Rapports :<ul><li>Installations et événements in-app bloqués : mise à jour continue quasiment en temps réel.</li><li>Post-attribution : <Anchor target="_blank" href="/marketers/fr/docs/about-data-freshness-and-timezone-support#eod">Quotidien</Anchor> en UTC.</li></ul></li></ul> |
| Réinstallations | Les données relatives à la fraude pour les réinstallations ne sont disponibles que sous forme de données brutes. Par conséquent, il peut y avoir des différences de totaux dans le tableau de bord et les rapports de données brutes. |
| Retargeting | <ul><li>Pour les installations identifiées comme frauduleuses, la répartition par type de touch attribué pour les installations, réattributions et réengagements est affichée.</li><li>Pour les événements in-app :<ul><li>Le tableau de bord des événements in-app (CPA) affiche les événements frauduleux provenant des installations AU, mais pas celles provenant du retargeting.</li><li>Les événements frauduleux de réattribution identifiés en temps réel se retrouvent dans les rapports de données brutes. Les événements frauduleux résultant de réengagements ne peuvent pas être identifiés.</li><li>Les événements frauduleux issus du retargeting ne peuvent pas être identifiés post attribution.</li></ul></li></ul> |
| Limites | <ul><li>Les tableaux sont limités à 20 000 lignes.</li><li>Si votre demande porte sur un ensemble de données plus volumineux, certaines sources média peuvent en être exclues. Pour surmonter cette limitation, nous vous recommandons de procéder ainsi :<ul><li>Demande portant sur un ensemble réduit de données - plage de dates réduite, applications spécifiques et sources média spécifiques</li><li>Exporter les <Anchor target="_blank" href="/marketers/fr/docs/protect360-raw-data-reports">rapports de données brutes</Anchor> Protect360</li><li>Exporter les rapports de détection avancée Protect360 agrégés <Anchor target="_blank" href="/marketers/fr/docs/pull-api-aggregate-data">via l'API Pull</Anchor></li></ul></li></ul> |

</Accordion>

<div id="faq-and-tips" />

## FAQ et conseils

<div id="faq" />

<Accordion title="FAQ">

| **Comment fonctionne le calcul du widget ***Économies estimées*** ?**<br /><br />Pour les <Anchor target="_blank" href="/marketers/fr/docs/roi360-cost-aggregation-overview">réseaux qui prennent en charge le partage des données de coût</Anchor>, vous obtenez une estimation précise des économies réalisées.<br /><br />Pour les réseaux qui ne prennent pas en charge cette application, AppsFlyer se base sur l'eCPI moyen issu de l'ensemble du groupe d'installations vérifiées à partir de toutes les sources contenant les données de coût. |
| --- |
| **Protect360 fonctionne-t-il contre la fraude provenant de liens d'attribution personnalisés ?**<br /><br />Absolument ! Protect360 détecte et bloque les fraudes provenant de liens d'attribution personnalisés, en plus des ad networks Cela signifie que vous êtes également protégé pour les campagnes de médias vous appartenant, comme avec des influenceurs, des campagnes par e-mail et SMS, des bannières de sites Web, des pages de destination, des publications virales sur les médias sociaux, des notifications Push ou même des codes QR. |
| **Quelles sont les nouveautés de Protect360 V2 par rapport à V1 ?**<ol><li>P360 V2.0 propose 3 changements principaux :<br />Fraude post-attribution - à chaque fois que nous présentons des installations bloquées, nous affichons également les installations de fraude post-attribution. Les données post-attribution sont également disponibles sous forme de rapport de données brutes.</li><li>Insights des anomalies : la nouvelle section « Insights des anomalies » a été ajoutée. Elle permet aux annonceurs d’analyser les anomalies à l'aide d'outils de visualisation. Elle remplace les deux graphiques de l'ancien onglet « Détection avancée ».</li><li>Centralisation de toutes les données de fraude : l'onglet « Détection avancée » a été supprimé et nous présentons désormais toutes les informations dans un seul onglet.</li></ol> |
| **Pourquoi les données brutes post-attribution ne sont-elles pas disponibles dans la page ***Données d'exportation*** ?**<br /><br />Les rapports post-attribution sont établis au niveau du compte par source média, afin de faciliter le processus de rapprochement. La page**Données d'exportation**se trouve au niveau de l'app unique. Pour des raisons de rétrocompatibilité, elle contient toujours les données relatives aux données de fraudes bloquées au niveau de l'app. |
| **Les données post-attribution sont-elles mises à jour rétroactivement ?**<ul><li>**Installations**- les données d'installation fournies sur la page de présentation et tous les autres rapports en dehors du tableau de bord Protect360 ne sont pas mises à jour rétroactivement.</li><li>**Événements in-app** - une fois que la couche de protection post-attribution identifie une installation comme fausse, les événements in-app suivants provenant de cette installation sont bloqués. Les événements in-app précédents ne sont pas mis à jour rétroactivement.</li></ul> |
| **Pourquoi les données sont-elles différentes en fonction des réseaux sélectionnés dans Aperçu des anomalies ?**<br /><br />Lorsque vous consultez les anomalies CTIT en sélectionnant comme référence AF\_Baseline, vous avez accès aux anomalies du réseau A. Mais si vous choisissez comme référence le Réseau A, alors vous avez accès aux anomalies de tous les réseaux, sauf du Réseau A.<br /><br />Ce résultat est en fait logique. Lorsqu'on utilise une référence vérifiée par AppsFlyer, ce sont les réseaux qui ont des CTIT anormaux qui s'affichent. Lorsque un réseau défaillant est utilisé comme référence, ses installations ne sont plus considérées comme des anomalies, mais les installations issues des autres réseaux peuvent par contre être vues comme anormales pour lui. |
| **Le trafic organique anormal est-il réellement frauduleux ?**<br /><br />Il est possible que des pics anormaux de trafic organique soient réellement frauduleux. En général, si vous voyez du trafic organique dans AppsFlyer et que vous avez des raisons de croire qu'il est réellement frauduleux, il pourrait s'agir de l'un des 3 cas suivants :<ul><li>**Échec de l'attribution de la fraude :** les clics frauduleux n'ont pas reçu d'attribution (par exemple, click flooding avec le dernier clic ayant lieu au-delà de la période d'analyse des clics).</li><li>**Fraude sans attribution :** l'utilisateur effectue une fraude non liée à l'attribution, par exemple en utilisant la fraude pour collecter des objets dans des jeux de stratégie.</li><li>**Problèmes d'intégration du SDK :** Vérifiez que vos événements in-app sont correctement envoyés, c'est-à-dire au bon moment dans le flux et avec des valeurs de paramètres d'événement correctes.</li></ul> |

</Accordion>

<div id="benchmarks-and-tips" />

<Accordion title="Références et astuces">

| **Détecter la fraude des nouveaux appareils**<br /><br />Les fraudeurs peuvent masquer leurs appareils en réinitialisant fréquemment les principaux ID de leurs appareils, à savoir : l'IDFA pour iOS et le GAID pour Android.<br /><br />Heureusement, AppsFlyer identifie plus de 98 % des appareils mobiles dans le monde.<br /><br />Par conséquent, un pourcentage élevé de nouveaux appareils inconnus est un signe sérieux signalant une fraude liée aux fermes à clics, à moins de cibler intentionnellement de nouveaux appareils.<br /><br />**Détection des nouveaux appareils :**<ol><li>Dans Protect360, ouvrez le tableau ***Répartition des fraudes identifiées***.</li><li>Faites défiler vers la droite jusqu'aux colonnes ***Indicateurs de ferme d'appareils - nouveaux appareils***.</li><li>Cliquez sur le nom de la colonne ***% des installations*** pour trier le tableau par ordre décroissant selon le ratio de nouveaux appareils.</li><li>Nouveaux indicateurs de fraude basée sur l'appareil :</li></ol><ul><li>Sources avec un pourcentage élevé de **nouveaux** appareils. **Note** : au fur et à mesure que le nombre d'installations augmente, des pourcentages plus faibles peuvent également être considérés comme une fraude (puisque le montant global est important).<ul><li>Lorsque le rapport d'utilisateur fidèle à la source est comparé au ratio d'utilisateur fidèle global, un pourcentage relativement faible est une indication forte de fraude.</li></ul></li></ul>**Remarque** : les campagnes d'<Anchor target="_blank" href="/marketers/fr/docs/appsflyer-factory-preinstall-using-manifest-android">apps pré-installées</Anchor> présentent généralement des taux extrêmement élevés de nouveaux appareils, car elles figurent souvent parmi les toutes premières apps que les utilisateurs lancent lors de l'activation de leurs nouveaux appareils. Par conséquent, la fraude aux nouveaux appareils est peu probable dans le cas des apps pré-installées, même avec des taux de nouveaux appareils conséquents. |
| --- |
| **Détection de fraude LAT**<br /><br />Les utilisateurs LAT (Limited Tracking Ad) choisissent de ne pas communiquerl'ID, l'IDFA ou le GAID de leur appareil aux annonceurs. Près de 15 % des utilisateurs iOS et de 10 % des utilisateurs Android font ce choix.<br /><br />Comme pour le classement des nouveaux appareils, les utilisateurs LAT peuvent être des utilisateurs légitimes. Cependant, un pourcentage élevé de ces utilisateurs peut indiquer une activité frauduleuse.<br /><br />**Détection LAT :**<ol><li>Dans Protect360, ouvrez le tableau ***Répartition des fraudes identifiées***.</li><li>Faites défiler vers la droite jusqu'aux colonnes ***Indicateurs de ferme d'appareils - Appareils LAT***.</li><li>Cliquez sur le nom de la colonne ***% des installations*** pour trier le tableau par ordre décroissant du ratio de nouveaux appareils.</li><li>Indicateurs de fraude des appareils LAT :</li></ol><ul><li>Sources avec un pourcentage élevé d'appareils **LAT**. **Note** : au fur et à mesure que le nombre d'installations augmente, des pourcentages plus faibles peuvent également être considérés comme une fraude (puisque le montant global est important).</li><li>Lorsque le rapport d'utilisateur fidèle à la source est comparé au ratio d'utilisateur fidèle global, un pourcentage relativement faible est une indication forte de fraude.</li></ul> |
| **Détection de la fraude par click flooding**<ol><li>Avec le click flooding, les fraudeurs envoient des millions de clics issus de vrais ID d'appareils, dans l’espoir d'être enregistrés en tant que dernier clic pour les vrais utilisateurs. Les sources présentant ce type de fraude ont **des taux de conversion très faibles, mais des utilisateurs de grande qualité**, puisqu'il s'agit de vrais utilisateurs.</li></ol>**Détection du click flooding :**<ol><li>Dans Protect360, ouvrez le tableau ***Répartition des fraudes identifiées***.</li><li>Faites défiler vers la droite jusqu'aux colonnes ***Indicateurs de click flooding***.</li><li>Cliquez sur le nom de colonne ***Taux de conversion*** pour trier le tableau par ordre croissant du taux de conversion.</li><li>Repères de la fraude par click flooding :</li></ol><ul><li>Les ***taux de conversion*** normaux sont compris entre 0,5 % et 35 %.<br />Sources suspectes dont les taux de conversion sont anormalement bas, ou qui **ont 25 % ou moins du taux de conversion moyen** de l'app. Vous pouvez trouver ce KPI dans le tableau de rapports de performances agrégés sur la page d'aperçu du tableau de bord.</li><li>Pour les sources qui sont à la limite, comparez le ***% d'assistance*** avec le taux moyen d'assistance. Vous pouvez connaître le taux d'assistance normal dans le widget d'assistance, sur la page de présentation du tableau de bord.<br />Les sources dont le taux d'assistance est **50% plus élevé que le taux moyen** d'assistance de l'app sont considérées comme suspectes.<br />Notez que plus une application utilise de sources, plus ses taux de contribution sont forts.</li></ul> |
| **Détection du click flooding avec les indicateurs CTIT**<br /><br />Un autre élément pour repérer le click flooding est la **répartition uniforme du CTIT**.<br />En règle générale, près de 70 % des installations normales ont lieu dans l'heure qui suit l'engagement publicitaire.<br />Avec le click flooding, il n'existe pas de lien entre le faux engagement et l'installation réelle. Ce qui fait que pas moins de 30 % des installations frauduleuses ont un CTIT de plus d'une heure.<br /><br />**Détection des indications de click flooding par le CTIT :**<ol><li>Dans Protect360, ouvrez le tableau ***Répartition des fraudes identifiées***.</li><li>Faites défiler vers la droite jusqu'aux colonnes ***Indicateurs de click flooding*** ***- CTIT***.</li><li>Repères CTIT de la fraude par click flooding :</li></ol><ul><li>Normalement, les valeurs ***Plus de 60 minutes***  doivent se situer aux environs de 30 %. Les sources qui affichent plus de 50 % de cette métrique sont suspectes.</li><li>Normalement, les valeurs ***Plus de 5 heures*** doivent se situer aux environs de 20 %</li></ul>Utilisez la <Anchor target="_blank" href="/marketers/fr/docs/protect360-dashboard#anomalies-dashboard">page</Anchor> ***Insights des anomalies*** pour passer en revue les sources présentant un CTIT suspect. |

</Accordion>

<div id="advanced-antifraud-tips" />

<Accordion title="Conseils anti-fraude avancés">

| **nombre d’installations**<br /><br />Le filtrage par nombre d'installations par source vérifiée est important pour détecter les sources de fraude les plus importantes. En outre, un faible nombre d'installations n'est pas toujours mathématiquement significatif. Remarque :<br /><br />**Remarque**: les sources qui ont moins de 30 installations, même 50, ne sont pas assez significatives pour en tirer des conclusions. Développez la plage de dates ou d'autres critères de recherche pour obtenir des résultats plus précis. |
| --- |
| **Modifier la définition des utilisateurs fidèles**<br /><br />La définition par défaut des utilisateurs fidèles est au moins 3 lancements de l'app. Il s'agit d'un KPI important pour l'engagement des utilisateurs, mais malheureusement, les fraudeurs en ont souvent conscience et l’emploient pour simuler des taux élevés d’utilisateurs fidèles, évitant ainsi les soupçons. Évitez de vous faire abuser en créant et en sélectionnant une définition plus juste et plus élaborée des utilisateurs fidèles.<br /><br />Analysez les KPI de qualité de l'utilisateur de votre application, tels que l'inscription, l'achèvement de tutoriel, l'achat, plusieurs sessions. Dans le code de l'app, envoyez un nouvel événement in-app **utilisateur fidèle** lorsqu'un utilisateur couvre TOUS les KPI.<br /><br />Une fois le premier événement **utilisateur fidèle** non-organique envoyé, accédez à **Paramètres de l'app** et sélectionnez-le pour indiquer les utilisateurs fidèles de votre application. Les taux généraux des utilisateurs fidèles devraient normalement enregistrer une légère baisse, puis une chute drastique, pour les sources frauduleuses. |

</Accordion>

<div id="tip" />

> 👍 **Astuce**
>
> Vous voulez en savoir plus sur la protection anti fraude ? Suivez cette <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7809/play/18635/mobile-app-fraud-and-protect360">formation rapide sur le portail d'apprentissage AppsFlyer</Anchor>.

<div id="see-also" />

> 📄 **À consulter également**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/protect360-raw-data-reports">Données Brutes</Anchor>
> * <Anchor target="_blank" href="https://www.appsflyer.com/resources/others/marketers-guide-mobile-ad-fraud/">Guide d'introduction à la fraude publicitaire mobile à l'intention des marketeurs</Anchor>

<div data-zendesk-anchors="protect360-overview=pr%C3%A9sentation-de-protect360 h_01HE7RSPPQ4T5J3W038EZRCTCE=pr%C3%A9sentation-de-protect360 h_01HE7RSPPQ5BH7HBK0R8SY1T16=realtime-blocking h_01HE7RSPPRW4CQ3GB9ZEYAA6YN=postattribution-detection h_01HE7RSPPRYMQKJH46JET2ZZ0T=common-fraud-issues-and-solutions using-protect360=utiliser-protect360 h_01HE7RSPPR8Y8J1VJJXXDCAZE6=utiliser-protect360 h_01HE7RSPPR04G3SCSYHSWJKQDG=dashboard h_01HE7RSPPRS6PSTZCR5RT4A5ND=raw-data h_01HE7RSPPR8C9MHRAGJXYD2VVZ=validation-rules h_01HE7RSPPR1PQ2R6NJPRQGS1K1=fraud-reconciliation-with-ad-networks traits-and-limitations=particularit%C3%A9s-et-limites h_01HE7RSPPRV797PS12NFQHX1X5=particularit%C3%A9s-et-limites h_01HE7RSPPRWRKR1Y25PZV2RMVV=traits-and-limitations::a07033c3 faq-and-tips=faq-et-conseils h_01HE7RSPPSV2TT8SMK8JZXFKMC=faq-et-conseils h_01HE7RSPPS01J796008HDS1CRW=faq h_01HE7RSPPS018W98JWZGED54W8=benchmarks-and-tips h_01HE7RSPPSEDZWRH929DBSWEWM=advanced-antifraud-tips h_01HE7RSPPSY161MSQVQW7M767F=astuce h_01HE7RX6167Q5QP5JNZDSXCCK5=%C3%A0-consulter-%C3%A9galement" />
