---
title: Guide de la solution SKAdNetwork (SKAN)
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - SKAD
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
    - Ad Networks
  created_at: '2020-07-25T21:19:42Z'
  edited_at: '2023-11-12T12:52:55Z'
  id: 360011420698
  locale: fr
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/fr/articles/360011420698
---
> **En bref** : attribuer des installations d'apps avec SKAN.

![5754](https://files.readme.io/a970d7b0e8da300ded2138f941bf2e891f32d396c8500292534992a4b4449d71-30757780264337.png)

## SKAN

SKAdNetwork (SKAN), qui fait partie de l'iOS d'Apple, aide les annonceurs à mesurer les performances de leurs campagnes tout en préservant la confidentialité des utilisateurs. SKAN fonctionne sans IDFA ou autre identifiant publicitaire. Il n'est pas nécessaire d'obtenir le consentement de l'utilisateur pour utiliser SKAN.

> 👍 **Astuce**
>
> * À partir d'iOS 15, nous vous recommandons d'envoyer des <Anchor target="_blank" href="/marketers/fr/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">copies postback SKAN</Anchor> à AppsFlyer. AppsFlyer pourra ainsi vérifier que les valeurs de conversion dans les postbacks n'ont pas été manipulées.
> * Vous voulez en savoir plus sur la solution SKAN AppsFlyer ? Suivez cette <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7810/play/18638/ios14-and-skadnetwork-part-1">formation éclaire</Anchor> sur le portail d'apprentissage AppsFlyer.

**Définitions**

* <Anchor target="_blank" href="/marketers/fr/docs/sdk-integration-overview">SDK</Anchor> : version actuelle du SDK iOS AppsFlyer intégré dans une app.
* **Fenêtre de mesure SKAN**: valable pour SKAN 4 et +. Il y a 3 périodes (fenêtres) pendant lesquelles l'activité post-installation des utilisateurs est mesurée :
  * Fenêtre 1 : 1-2 jours
  * Fenêtre 2 : 3-7 jours
  * Fenêtre 3 : 8-35 jours
* **Valeur de conversion (CV)**: mesure de la qualité de l'utilisateur transmise dans les postbacks envoyés par iOS à la fin des fenêtres de mesure pour SKAN 4 (ou pour SKAN 3 et -, à la fin de la fenêtre d'activité). Le SDK AppsFlyer définit les CV pour vous. Si vous souhaitez régler vous-même la CV, utilisez l'option <Anchor target="_blank" href="/marketers/fr/docs/skan-cv-decode-map-your-cv-to-events">Décoder</Anchor> pour importer votre fichier de mappage CV.
  * Pour SKAN 4+, il existe des valeurs de conversion précises ou approximatives.
* **Conversion Studio** : solution AppsFlyer pour mapper les VC de l'infrastructure en événements
* **Solution :** le SDK, l'infrastructure et la plateforme AppsFlyer qui travaillent ensemble. La solution SKAN d'AppsFlyer fournit aux annonceurs et aux réseaux publicitaires des données LTV via des analyses de tableaux de bord, des rapports et des postbacks.
* **Fenêtre d'activité :** valable pour SKAN 3 et -. A une durée définie par défaut sur 24 heures, le début correspond à la première ouverture de l'app. Si vous utilisez SKAN 4+ mais que les appareils des utilisateurs ou les réseaux publicitaires ne prennent pas en charge SKAN 4, la fenêtre d'activité est alors de 48 heures.

Cet article décrit les caractéristiques et la solution correspondant à l'infrastructure. Pour configurer la mesure, voir <Anchor target="_blank" href="/marketers/fr/docs/skan-conversion-studio">Conversion Studio SKAN</Anchor>.

<div id="about-apple-skan" />

<Accordion title="À propos d'Apple SKAN">

| Caractéristiques | Description |
| --- | --- |
| Conditions préalables | Pour autoriser l'utilisation de SKAN dans l'app :<ul><li>L'app de l'annonceur (votre app), c'est-à-dire l'app faisant l'objet d'une publicité : déployer le SDK AppsFlyer pour définir la VC. Vous pouvez également définir la VC à l'aide du <Anchor target="_blank" href="/marketers/fr/docs/skan-cv-decode-map-your-cv-to-events">mode Décodage</Anchor>.</li><li>Apps des éditeurs (apps affichant une publicité) : ces dernières doivent utiliser la fonction <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/configuring_a_source_app">Configurer une app source.</Anchor></li><li><Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/registering_an_ad_network">Les ad networks doivent s'inscrire auprès d'Apple</Anchor></li></ul> |
| Prise en charge | <ul><li>La version de SKAdNetwork prise en charge dépend de la version d'iOS :<ul><li>iOS 11-13 : V1 (s'installe uniquement sans VC)</li><li>iOS 14 à 14.5 : V2 et + (comprend les CV)</li><li>iOS 14.6 à 16 : V3 (comprend les CV)</li><li>iOS 16.1 et + : V4 et + (comprend les CV pour 3 fenêtres, et des valeurs précises et approximatives)</li></ul></li><li>Attribution d'app à app</li></ul> |
| Limites | <ul><li>Apple Search Ads non prises en charge</li><li>Le web mobile n'est pas pris en charge</li><li>Jusqu'à SKAN 4, la numérotation des ID de campagne <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skstoreproductparameteradnetworkcampaignidentifier">peut aller de 1 à 100 uniquement</Anchor>, il peut donc y avoir 100 valeurs uniques par réseau publicitaire et par application. Les réseaux publicitaires transmettent à AppsFlyer leur ID de campagne et leur nom. Ils apparaissent dans les tableaux de bord et les rapports AppsFlyer.</li><li>Depuis SKAN 4, l'identifiant de la source va de 1 à 10 000.</li><li>Installations organiques : SKAN ne prend pas en charge les installations organiques.</li><li>Réengagement.</li></ul> |
| Principes d'attribution de SKAN | <ul><li>Attributs SKAN utilisant le <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_ad_attributions">modèle d'attribution suivant</Anchor> :<ul><li>L'utilisateur clique sur une publicité dans les 30 jours qui suivent l'installation (téléchargement de l'app), puis dans les 60 jours suivants il ouvre l'app pour la première fois.</li><li>L'utilisateur visionne une publicité dans les 24 heures suivant l'installation (téléchargement de l'app), puis dans les 60 jours suivants il ouvre l'app pour la première fois.</li><li>Depuis SKAdNetwork V2.2, l'attribution post clic est prioritaire sur l'attribution post vue. La version de SKAN dépend de la version d'iOS.</li><li>iOS envoie des postbacks au réseau publicitaire attribué. À partir d'iOS 15, les annonceurs peuvent envoyer une copie du postback directement à AppsFlyer.</li></ul></li></ul> |
| Anonymat des foules | Apple envoie certains postbacks avec des données limitées afin de protéger la vie privée des utilisateurs. Selon Apple, le postback n'inclura pas les CV précises ou approximatives, ni l'ID de l'app source ou l'ID complet de la source si cela enfreint les limites de confidentialité imposées par Apple. <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_postbacks_in_multiple_conversion_windows">En savoir plus</Anchor> |

</Accordion>

## Solution AppsFlyer SKAN

AppsFlyer fournit des résultats agrégés d'attribution iOS en utilisant les postbacks SKAN d'iOS. Ces postbacks sont envoyés par iOS aux réseaux publicitaires qui les transmettent ensuite à AppsFlyer. Les postbacks contiennent des enregistrements d'attribution anonymes auxquels s'ajoutent une valeur de conversion (CV) définie par l'annonceur. La CV correspond à la mesure de la qualité de l'utilisateur au cours d'une fenêtre initiale de post-installation.

La solution SKAN d'AppsFlyer offre aux annonceurs :

* Des tableaux de bord avec les données SKAN ainsi que des rapports obtenus en agrégeant les postbacks de tous les réseaux publicitaires enrichis de différents types de données, comme le coût.
* La possibilité de contrôler (via le studio de conversion AppsFlyer) ce que la CV mesure sans avoir à modifier le code de l'application. La CV peut être utilisée pour mesurer les revenus, les engagements ou les événements de conversion.

<div id="principles-and-flow" />

<Accordion title="Principes et fonctionnement">

#### **Flux d'attribution SKAN**

![SKAN_flow_-_Affinity_diagram_2.png](https://files.readme.io/2e29f01cf9cf3689777bbd42044e42c0b9f1d4fb719ed75413d29dd84489686d-13112278947601.png)

1. L'annonceur définit les paramètres de mesure SKAN dans le Studio de conversion AppsFlyer.
2. L'utilisateur ouvre l'app pour la première fois.
3. Pendant chaque fenêtre, AppsFlyer définit la CV selon les actions de l'utilisateur et le schéma de CV qui a été défini.
4. Après la fermeture de la fenêtre, iOS envoie le postback au réseau publicitaire ainsi qu'une copie du postback à AppsFlyer. Le postback arrive après un certain délai :
   * Pour la fenêtre de mesure 1 de SKAN 4 : 24-48 heures
   * Pour les fenêtres de mesure 2 et 3 de SKAN 4 : 24-144 heures
   * Pour SKAN 3 : 24-48 heures après la dernière augmentation de la valeur de la CV.
5. Les copies des postbacks envoyées directement de l'appareil iOS à AppsFlyer sont transmises au point de terminaison défini par l'annonceur. Cf <Anchor target="_blank" href="/marketers/fr/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">Envoi des copies de postbacks SKAN à AppsFlyer.</Anchor>
6. Le réseau publicitaire transmet les postbacks enrichis à AppsFlyer, ou bien le SRN communique les données de postback via API.
7. AppsFlyer valide et décrypte la CV. Les données décryptées sont enregistrées et attribuées avant d'être consultables dans les tableaux de bord, rapports et API AppsFlyer.

Afin de surmonter les limitations fonctionnelles et structurelles de l'infrastructure SKAdNetwork, la solution SKAN d'AppsFlyer prend en compte les caractéristiques du tableau suivant.

| Caractéristiques | Description |
| --- | --- |
| <span id="data-collection"></span>Collecte des données | <ul><li>Pour l'annonceur, les postbacks SKAdNetwork sont collectés à partir de plusieurs ad networks.</li><li>Les annonceurs évitent la tâche complexe et fastidieuse de s'intégrer individuellement à chaque ad network.</li></ul> |
| <span id="data-validation"></span>Validation des données | <ul><li>S'assure que les postbacks sont signés par Apple, ce qui réduit les risques de manipulation.</li><li>Utilise le champ ID de transaction pour vérifier que les postbacks sont uniques.</li></ul> |
| <span id="data-enrichment"></span>Enrichissement des données | <ul><li>Enrichit les données de postback SKAdNetwork avec d'autres points de données pour fournir une analyse complète du ROI. Exemple : le nom de la campagne fourni par le réseau publicitaire, etc.</li><li>Les points de données incluent les impressions, les clics, les coûts, etc.</li></ul> |
| <span id="data-delivery"></span>Fourniture des données | Les données SKAdNetwork enrichies sont disponibles via les éléments suivants :<ul><li><Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">Tableau de bord de la solution SKAdNetwork</Anchor></li><li>[Rapports téléchargeables](/docs/skadnetwork-skan-solution-guide#reporting-options)</li></ul> |
| <span id="seamless-integration"></span>Intégration transparente | <ul><li>Grâce à l'encapsulation complète, l'annonceur n'a quasiment aucun effort à fournir via la page des paramètres de l'app.</li><li>Aucun codage requis. L'app nécessite la dernière version du SDK.</li><li>Inclut la prise en charge des modifications d'Apple attendues dans l'infrastructure SKAdNetwork.</li></ul> |
| <span id="agility"></span>Agilité | Les annonceurs peuvent modifier les configurations de mesure selon leurs besoins via le tableau de bord. |

</Accordion>

<div id="conversion-studio" />

<Accordion title="Studio de conversion">

<Anchor target="_blank" href="/marketers/fr/docs/skan-conversion-studio">Le Studio de Conversion</Anchor> AppsFlyer est la pierre de voute de la solution SKAN. Il offre une flexibilité maximale pour que chaque valeur de conversion soit mise à profit. Vous déterminez précisément les données de mesure qui doivent être encodées dans la CV, y compris l'activité et la durée de la mesure post-installation. Il existe plusieurs modes de mesure qui vous permettent de configurer les paramètres de votre CV.

| Type | Mode de mesure | Description | Fenêtre d'activité |
| --- | --- | --- | --- |
| Flexible | SKAN 4.0<br /><br />[Bonnes pratiques] | Définir une combinaison de revenus, de conversions (événements in-app) et de mesures de l'engagement durant 3 fenêtres d'activité configurables. | <ul><li>Fenêtre 1 : 1-2 jours</li><li>Fenêtre 2 : 3-7 jours</li><li>Fenêtre 3 : 8-35 jours</li></ul> |
| Flexible | <Anchor target="_blank" href="/marketers/fr/docs/skan-conversion-studio#custom">Personnalisation</Anchor> | Définir une combinaison de revenus, de conversions (événements in-app) et de mesures d'engagement lors d'une fenêtre d'activité configurable. | 12 h-63 j |
| Fixe | Revenu<br /><br />[Par défaut]<br /><br />[Ancienne version] | Mesurer les revenus à l'aide de l'une des plages suivantes :<ul><li>1 $-630 $ par tranches de 10 $</li><li>1 $ à 63 $ par tranches de 1 $</li><li>0,01 $ à 0,63 $ par tranches de 0,01 $.</li></ul> | 24 h |
| Fixe | Conversion<br /><br />[Ancienne version] | Sélectionnez 1 à 6 événements in-app. | 24 h |
| Fixe | Engagement<br /><br />[Ancienne version] | Nombre de fois qu'un utilisateur effectue un événement | 24 h |
| Flexible | <Anchor target="_blank" href="/marketers/fr/docs/skan-cv-decode-map-your-cv-to-events">Décryptage</Anchor> | <ul><li>Créez une valeur de conversion personnalisée pour le mappage d'événements et définissez-la dans l'app. Utiliser cette option s'il est impossible d'intégrer le SDK AppsFlyer dans votre app. Pour utiliser la fonction « Decode », accédez à **SKAN Conversion Studio**, cliquez sur Options (⋮) puis sélectionnez **Importer un fichier de mappage décryptage personnalisé**.</li><li>SKAN 4 non pris en charge</li></ul> | 12-1512 h (63 jours) |

</Accordion>

## Informations supplémentaires relatives à SKAdNetwork

<div id="reporting-options" />

<Accordion title="Options de rapport">

Les rapports SKAdNetwork ne contiennent pas d'identifiants de niveau utilisateur.

| Nom de rapport | Type | Enrichi par AppsFlyer | Méthode de livraison | Fonctionnalité Premium |
| --- | --- | --- | --- | --- |
| <Anchor target="_blank" href="/marketers/fr/docs/skan-aggregated-performance-report-api">Rapport des performances agrégé SKAN.</Anchor><br /><br />Rapport agrégé pour les installations, les événements in-app et les revenus. Les données sont similaires à celles que l'on trouve dans le tableau de bord SKAN. | Données agrégées selon une date d'installation ou d'arrivée de postback | Oui | API | Non |
| <Anchor target="_blank" href="/marketers/fr/docs/skan-aggregated-postback-arrival-date-api">Rapport de postback agrégé SKAN</Anchor>.<br /><br />Postbacks SKAN agrégés au plus haut niveau de granularité possible. | Agrégation des postbacks basée sur la date d'arrivée des postbacks | Non | API | Non |
| <Anchor target="_blank" href="/marketers/fr/docs/skan-raw-data-reports#raw-data-report-types">Rapports de données brutes SKAN (niveau lignes) via Data Locker</Anchor> (avec exemples).<br /><br />Rapports disponibles :<ul><li>Postbacks envoyés par iOS avec enrichissement des données fourni par les partenaires de l'ad network</li><li>d'installations</li><li>[PLEASE TRANSLATE]</li><li>Évènement in-app</li><li>Dimensions publicitaires SRN</li></ul> |  | Oui | Data Locker | Oui. Données brutes requises. L'abonnement à Data Locker n'est pas nécessaire. |
| Données SKAN via API Push |  | Oui | API push | Oui |

</Accordion>

<div id="skadnetwork-solution-implementation-checklist" />

<Accordion title="Liste de vérification pour la mise en œuvre de la solution SKAdNetwork">

| Non. | Action | Description | Responsable |
| --- | --- | --- | --- |
| 1 | Préparer | <ul><li>Lire le <Anchor target="_blank" href="https://www.appsflyer.com/resources/prepare-your-app-ios14/">Guide pour la solution SKAdNetwork</Anchor></li><li>Lecture connexe : <Anchor target="_blank" href="https://www.appsflyer.com/resources/prepare-your-app-ios14/">Préparez vos apps pour iOS 14</Anchor></li></ul> | Marketeurs et développeurs |
| 2 | Configurer | Dans AppsFlyer, configurez la solution SKAdNetwork dans <Anchor target="_blank" href="/marketers/fr/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>. | Marketeur |
| 3 | Préparer l'app | Migrer l'app vers AppsFlyer <Anchor target="_blank" href="/marketers/fr/docs/sdk-integration-overview">SDK V6</Anchor><ul><li>Aucune modification de la logique de l'app ni du code de l'app n'est nécessaire.</li><li>La solution SKAN d'AppsFlyer s'appuie sur des événements in-app pour définir la valeur de conversion et envoyer des événements in-app de manière habituelle. Aucun test spécifique à la solution SKAN n'est requis.</li><li>Envoyer l'app à l'App Store</li><li>Aucun enregistrement ou processus de SKAdNetwork n'est requis dans l'app store.</li></ul> | Développeur |
| 4 | Intégrations de partenaires | Les partenaires de l'ad network doivent s'intégrer à AppsFlyer via l'intégration SKAdNetwork. Important ! La simulation SKAdNetwork AppsFlyer contient les données de tous vos partenaires, quel que soit leur statut d'intégration actuel. Ce ne sera pas le cas pour les données en direct transmises dans les postbacks SKAdNetwork.<br /><br />En ce qui concerne les partenaires chargés de vos campagnes, procédez comme suit :<br /><br />**Non SRN** :<ol><li>Vérifiez que le partenaire possède un <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#c">badge de capacité SKAdNetwork</Anchor> AppsFlyer, et que dans l'interface utilisateur du partenaire les rapports de campagne SKAdNetwork sont bien activés.</li><li>Vérifiez que les [noms d'événements in-app sont mappés](#sending-postbacks-to-integrated-partners) aux noms des événements in-app des partenaires.</li></ol>**Meta Ads** :<ul><li><Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-interoperation-with-meta-ads">Configurer l'interopérabilité d'AppsFlyer SKAdNewtork avec Meta ads</Anchor></li></ul> | Marketeur |

</Accordion>

<div id="troubleshooting-guide" />

<Accordion title="Guide de dépannage">

| Symptôme | Description |
| --- | --- |
| Le tableau de bord ne contient aucune installation non organique. | <ol><li>Vérifiez que la **mesure SKAdNetwork** est activée.<ol><li>Accédez à **Configuration** > **SKAN Conversion Studio.**</li><li>Cliquez sur Options (⋮), et examinez le paramètre de mesure SKAN.</li></ol></li><li>Vérifiez que vous disposez de la version 6.2.6 ou supérieure du SDK<ul><li>Pour ce faire, allez dans **Intégration** > **Informations sur le SDK > Utilisateurs par version du SDK.**</li></ul></li><li>Si vous utilisez des plugins du SDK, vérifiez que la version que vous implémentez prend en charge AppsFlyer SKAdNetwork.</li><li>Vérifiez que vos partenaires de réseau publicitaire sont intégrés à AppsFlyer et qu'ils transmettent des postbacks iOS à AppsFlyer.</li></ol> |
| Le tableau de bord contient des installations non organiques mais aucun événement in-app. | <ol><li>Vérifiez que vous disposez de la version 6.2.6 ou supérieure du SDK<ul><li>Pour ce faire, allez dans **Intégration** > **Informations sur le SDK > Utilisateurs par version du SDK.**</li></ul></li><li>Si vous utilisez des plugins du SDK, vérifiez que la version que vous implémentez prend en charge AppsFlyer SKAdNetwork.</li><li>Envoyez-vous des événements en utilisant S2S ? Si c'est le cas, vérifiez que l'option **Enregistrer les événements in-app envoyés par l'API de serveur à serveur** est activée.<ol><li>Accédez à **Configuration** > **SKAN Conversion Studio.**</li><li>**Cliquez sur Options (⋮), vérifiez que la configuration S2S est activée.** Remarque  : en mode de mesure Personnalisé et Décodage, ce paramètre est toujours activé et ne peut pas être modifié.</li></ol></li></ol> |
| Le tableau de bord contient les installations et certains événements in-app. Certains événements in-app sont manquants. | <ol><li>Envoyez-vous des événements en utilisant S2S ? Si c'est le cas, vérifiez que l'option **Enregistrer les événements in-app envoyés par l'API de serveur à serveur** est activée.<ol><li>Accédez à **Configuration** > **SKAN Conversion Studio.**</li><li>**Cliquez sur Options (⋮), vérifiez que la configuration S2S est activée.** Remarque  : en mode de mesure Personnalisé et Décodage, ce paramètre est toujours activé et ne peut pas être modifié.</li></ol></li><li>Examinez vos <Anchor target="_blank" href="/marketers/fr/docs/skan-raw-data-reports#raw-data-report-types">données brutes de postback</Anchor> pour voir si tous les événements sont signalés.</li></ol> |
| Les emplacements geo (pays) peuvent être trompeurs. | Les données de géolocalisation sont dérivées comme suit :<ul><li>Selon le pays associé à une campagne et signalé à AppsFlyer par le réseau publicitaire.</li><li>Via l'adresse IP de l'appareil. À partir d'iOS 14.6, cette adresse est une adresse proxy et ne représente pas réellement la géolocalisation de l'utilisateur.</li></ul> |

</Accordion>

<div id="timing-from-app-install-until-dashboard-and-reports-update" />

<Accordion title="Délai entre l'installation de l'app et la mise à jour du tableau de bord et des rapports">

| Clé | Nom de l'élément | Description | Exemple A | Exemple B | Exemple C | Exemple D | Exemple E |
| --- | --- | --- | --- | --- | --- | --- | --- |
| A | Fenêtre de mesure 1 de SKAN 4 | <ul><li>Pendant la fenêtre, les valeurs de conversion sont définies par l'app</li><li>0-2 jours</li><li>La fenêtre peut être verrouillée sous 2 jours dans Conversion Studio</li></ul> | - | - | 2 jours | - | - |
| B | Fenêtre de mesure 2 de SKAN 4 | <ul><li>Pendant la fenêtre, la CV est définie par l'app</li><li>3-7 jours</li><li>La fenêtre peut être verrouillée sous 7 jours dans le studio de conversion.</li></ul> | - | - | - | 7 jours | - |
| C | Fenêtre de mesure 3 de SKAN 4 | <ul><li>Pendant la fenêtre, la CV est définie par l'app</li><li>8-35 jours</li><li>La fenêtre peut être verrouillée sous 35 jours dans Conversion Studio</li></ul> | - | - |  | - | 35 jours |
| D | Délai du postback de la fenêtre de mesure 1 de SKAN 4 | 24-48 heures | - | - | 24-48h | - | - |
| E | Délai de la fenêtre de mesure 2-3 de SKAN 4 | 24-144 heures | - | - | - | 24-144h | 24-144h |
| F | Fenêtre d'activité<br /><br />(Non valable pour SKAN 4) | <ul><li>Pendant la fenêtre, la valeur de conversion est définie par l'app.</li><li>La fenêtre commence lors de la première ouverture de l'app.</li><li>Durée 12 heures à 63 jours.</li></ul> | 24 h | 72 h | - | - | - |
| G | Délai SKAdNetwork<br /><br />(Non valable pour SKAN 4) | <ul><li>Compte à rebours : 24 heures</li><li>Le délai est réinitialisé chaque fois que la valeur de conversion augmente. Cela signifie que le décompte commence après 24 heures.</li></ul> | 0-24 h | 0-24 h | - | - | - |
| H | Délai aléatoire SKAdNetwork<br /><br />(Non valable pour SKAN 4) | Délai de postback aléatoire. Le décompte commence à la fin de la période définie par F+G. | 0-24 h | 0-24 h | - | - | - |
| I | Traitement par AppsFlyer | Les postbacks reçus un jour donné sont traités à la fin de la journée (UTC) qui commence à 00:01 le jour suivant. Les données sont disponibles 8 heures plus tard. Ce qui signifie que le traitement dure entre 8 et 32 heures. Délai moyen de 20 heures. Par exemple, un postback reçu le lundi est traité le mardi. Le tableau de bord est mis à jour à 08:00 UTC. | 08-32 h | 08-32 h | 08-32 h | 08-32 h | 08-32 h |
| J | Résumé | Le temps total qui peut s'écouler | 32-104h | 80-152 h | 80-128h | 200-344h | 872-1016h |

</Accordion>

<div id="organic-metrics-in-the-context-of-skadnetwork" />

<Accordion title="Métriques organiques dans le contexte de SKAdNewtork">

Les métriques organiques du tableau de bord SKAdNetwork sont calculées selon le mécanisme suivant :

* Les métriques organiques ne sont pas disponibles pour les événements in-appp si le mode de mesure sélectionné est <Anchor target="_blank" href="/marketers/fr/docs/skan-conversion-studio#studio-de-conversion-skan--présentation">SKAN 4, Personnalisé ou Décodage (Custom ou Decode).</Anchor>
* Apple SKAdNetwork envoie des postbacks concernant les utilisateurs qui effectuent une installation après s'être engagés via une source média. Cela fournit les métriques non organiques.
* Le tableau de bord d'attribution AppsFlyer comprend des métriques de toutes les installations, quelle que soit la source.  Voir <Anchor target="_blank" href="/marketers/fr/docs/ios-metrics-in-the-overview-dashboard-skan-and-appsflyer-metrics-side-by-side">l'attribution AppsFlyer comparée à l'attribution SKAN</Anchor>.
* Les métriques organiques sont calculées en fonction de ces données avec A et B qui correspondent à :
  * A = Total de tous les utilisateurs, sur la base de la vue d'ensemble du tableau de bord classique
  * B = Utilisateurs non organiques tels que rapportés par les postbacks de SKAdNetwork

**Mise en garde relative à Apple Search Ads** : les installations apportées par Apple Search Ads dans le tableau de bord classique ne sont pas organiques. Cependant, dans le contexte de SKAdNetwork, elles font partie de la métrique organique.

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Particularités et limites">

| Particularité | Remarques |
| --- | --- |
| Accès du réseau publicitaire | Les ad networks sont fournis avec des postbacks |
| Agences | Pas de prise en charge. Cela signifie que les agences ne doivent pas activer les réseaux publicitaires exécutant des campagnes SKAdNetwork. Agence ! Demandez à l'annonceur d'activer le réseau publicitaire, ne le faites pas vous-même. Les agences peuvent indiquer qu'elles ont amené l'utilisateur en utilisant la <Anchor target="_blank" href="/partners/fr/docs/getting-started-agency-onboarding#campagnes-skadnetwork-des-agences">reconnaissance d'agence SKAN</Anchor>. |
| Transparence de l'agence | S/O |
| Fuseau horaire | UTC |
| Devise | USD |
| Données organiques | En fonction des données d'événements du SDK. Par exemple, les métriques d'installation organique sont calculées comme suit : les données de toutes les installations rapportées par le SDK moins les installations non organiques rapportées par SKAdNetworks. |
| Données non organiques | En fonction des postbacks SKAdNetwork |
| Actualisation des données | Quotidien |
| Données historiques | Date antérieure, disponibilité d'iOS 14 (16 septembre 2020) |
| Accès des utilisateurs | L'utilisateur du compte doit disposer des <Anchor target="_blank" href="/marketers/fr/docs/user-management">autorisations nécessaires</Anchor> |
| Clips d'app | Les clips d'app sont attribués comme organiques dans le tableau de bord SKAdNetwork. Utilisez la vue d'ensemble du tableau de bord pour visualiser les sources média d'invocation. |

</Accordion>

## Partenaires intégrés de SKAN

<div id="recording-ad-revenue" />

<Accordion title="Enregistrement des revenus publicitaires">

Pour attribuer les revenus publicitaires générés pendant la fenêtre d'activité SKAdNetwork à la campagne qui a conduit l'utilisateur. Cette fonction se limite actuellement aux annonceurs intégrés aux revenus publicitaires de niveau impression via le SDK générique.

Pour enregistrer les revenus publicitaires dans votre tableau de bord SKAN :

* Intégrez le <Anchor target="_blank" href="/marketers/fr/docs/integrate-the-roi360-ad-revenue-sdk-api">SDK générique de revenus publicitaires de niveau impression</Anchor> à votre application.
* Si vous utilisez un mode de SKAN Conversion Studio fixe, <Anchor target="_blank" href="/marketers/fr/docs/skan-conversion-studio#report-events-by-servertoserver-api">activez la prise en charge de serveur à serveur SKAdNetwork</Anchor>.

**Remarque** : Consultez les documents sur le <Anchor target="_blank" href="/marketers/fr/docs/integrate-the-roi360-ad-revenue-sdk-api">connecteur SDK générique</Anchor> pour plus d'infos sur les sources publicitaires disponibles à la médiation.

</Accordion>

<div id="sending-postbacks-to-integrated-partners" />

<Accordion title="Envoi de postbacks aux partenaires intégrés">

AppsFlyer envoie aux partenaires intégrés des postbacks relatifs à l'attribution SKAN (pour SKAN 4, les postbacks sont envoyés uniquement pour la fenêtre 1).

Vous trouverez les différentes options et exigences dans le tableau qui suit

| Sujet | Description |
| --- | --- |
| <span id="transaction-id-sharing"></span>Partage de l'ID de transaction | **Action requise** : vérifiez auprès du partenaire intégré s'il a besoin de l'<Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/verifying_an_install_validation_postback">ID de transaction</Anchor> et configurez le paramètre en conséquence.<br /><br />AppsFlyer transmet les postbacks du partenaire de réseau publicitaire attribué. C'est-à-dire les postbacks décryptés, pas une copie des postbacks de SKAdNetwork reçus d'iOS. Ces postbacks contiennent des données de valeur de conversion décryptées relatives à l'installation et aux données d'événements in-app associées pour les actions effectuées par l'utilisateur pendant la fenêtre de mesure.<br /><br />Puisque l'ID de transaction peut être utilisé pour décrypter votre valeur de conversion, nous ne le partageons pas sans votre autorisation.<br /><br />**Partage de l'ID de transaction**<br /><br />Les annonceurs <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#b">activent le partage d'ID de transaction</Anchor> comme suit : dans AppsFlyer, aller dans **Configuration** > **Intégrations actives** > sélectionner un partenaire > **Onglet Intégration** > **Partage des données**. |
| <span id="inapp-event-mapping-verification"></span>Vérification du mappage des événements dans l'app | **<span id="1611499069.009700"></span>Action requise** : vous devez <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#les-méthodes-de-mappage">mapper vos événements in-app</Anchor> aux noms d'événements partenaires correspondants, afin que le partenaire enregistre correctement les postbacks.<br /><br />Pour chacun des partenaires menant des campagnes SKAdNetwork, vérifiez que l'événement in-app est défini en fonction du type de mesure sélectionné.<br /><br />**Pour vérifier et modifier les mappages d'événements in-app des partenaires** :<ol><li>Dans AppsFlyer, allez dans **Configuration** > **Intégrations actives**.</li><li>Sélectionnez le partenaire.</li><li>Accédez à l'onglet  **Intégration** .</li><li>Vérifiez et, si cela est nécessaire, modifiez les paramètres comme suit :<ol><li>Activez **Postback des événements in-app**.</li><li>Vérifiez que les événements in-app et **les noms d'événements SDK** que vous avez définis dans la mesure SKAdNetwork sont mappés aux  **identifiants d'événements partenaires**.</li></ol></li><li>Cliquez sur **Enregistrer l'intégration**.</li></ol> |

</Accordion>

> 📄 **À consulter également**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/about-att-and-skan">Guide de démarrage rapide et FAQ pour iOS 14, ATT et SKAN</Anchor>
> * <Anchor target="_blank" href="/marketers/fr/docs/skan-conversion-studio">Configurer les mesures à l'aide de Conversion Studio de SKAN (paramètres SKAdNetwork)</Anchor>
> * <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-overview-dashboard-by-appsflyer">Tableau de bord SKAN AppsFlyer</Anchor>
> * <Anchor target="_blank" href="/marketers/fr/docs/skan-integrated-partners-list">Liste des partenaires SKAN intégrés</Anchor>
> * Interopération des partenaires SKAN nécessitant une configuration dans AppsFlyer :
>   * <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-interoperation-with-meta-ads">Meta Ads</Anchor>
>   * <Anchor target="_blank" href="/marketers/fr/docs/get-skan-postback-data-from-google-ads">Google Ads</Anchor>
>   * <Anchor target="_blank" href="/marketers/fr/docs/skan-interoperation-with-tiktok-for-business">TikTok pour les entreprises</Anchor>
>   * <Anchor target="_blank" href="/marketers/fr/docs/skan-interoperation-with-snapchat">Snapchat</Anchor>

<div data-zendesk-anchors="01H7Z06Z03AQY25A3E45Z47A9G=skan 01H7Z06Z03CSKH1ZB9RQP6SHA8=astuce 01H7Z06Z03MRE6BCSG1AEXN947=about-apple-skan appsflyer-skan-solution=solution-appsflyer-skan 01H7Z06Z04G479NAKBEA33SGSZ=solution-appsflyer-skan 01H7Z06Z05CAVK3CR7F5FBKFC5=principles-and-flow skan-attribution-flow=flux-dattribution-skan 01H7Z06Z05EGK5QBDK6G7BJQJK=flux-dattribution-skan 01H7Z06Z053M2H3CJ6SV4VDZPZ=conversion-studio additional-skadnetwork-information=informations-suppl%C3%A9mentaires-relatives-%C3%A0-skadnetwork 01H7Z06Z05556NQ35HMR4E2TRY=informations-suppl%C3%A9mentaires-relatives-%C3%A0-skadnetwork 01H7Z06Z05G0YB56GDG5E196QM=reporting-options 01H7Z06Z05M3BPSBTCMJ3NHK5D=skadnetwork-solution-implementation-checklist 01H7Z06Z05YF4J0MPMJ40EG7BX=troubleshooting-guide 01H7Z06Z0502NW8KFJ7XRZFWJR=timing-from-app-install-until-dashboard-and-reports-update 01H7Z06Z068462E4QTGTSMNS7H=organic-metrics-in-the-context-of-skadnetwork 01H7Z06Z0615QHCY6JZ4MAMTJ8=traits-and-limitations skadnetwork-integrated-partners=partenaires-int%C3%A9gr%C3%A9s-de-skan 01H7Z06Z06KGT6ESN42XTJSK2F=partenaires-int%C3%A9gr%C3%A9s-de-skan 01H7Z06Z06NWJQ6W50MCD3P352=recording-ad-revenue 01H7Z06Z06K2ZB949GGTJV6MJP=sending-postbacks-to-integrated-partners h_01HE7TC49KRRX1RVGX1FY7C52T=%C3%A0-consulter-%C3%A9galement" />
