---
title: Rapports de données brutes Protect360
metadata:
  keywords:
    - Advertisers
    - Protect360
    - protect
    - protect 360
    - '360'
    - Raw Data
    - Premium
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2020-11-09T13:03:45Z'
  edited_at: '2023-11-12T12:53:13Z'
  id: 360015179337
  locale: fr
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/fr/articles/360015179337
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En bref** : les rapports de données brutes détaillent les installations et événements in-app bloqués par le moteur Protect360, ainsi que par les règles de validation ajoutées manuellement.

<div id="note" />

<div id="about-protect360-raw-data-reports" />

## À propos des rapports de données brutes Protect360

Rapports de données brutes :

* Afficher les données sur :
  * Clics, installations et événements in-app identifiés comme frauduleux par le moteur Protect360.
  * Installations et événements in-app identifiés par les règles de validation.
* Indiquez la raison du blocage pour chaque clic, installation ou événement in-app.
* Utilisé par les annonceurs pour rapprocher les comptes des réseaux publicitaires, à des fins d'optimisation, et pour ajuster les tableaux de bord d'attribution pour la fraude post-attribution.
* Certains champs <Anchor target="_blank" href="/marketers/fr/docs/about-raw-data-identifier-restrictions">peuvent être restreints ou non disponibles</Anchor> si <Anchor target="_blank" href="/marketers/fr/docs/apply-aggregated-advanced-privacy-framework">la Confidentialité avancée agrégée (CAA) AppsFlyer est appliquée</Anchor>.
* Les types de rapports et leur disponibilité pour les téléchargements, API et Data Locker (compartiment S3) sont décrits ci-dessous.
* Les rapports sur les données historiques brutes sont conservés jusqu'à 90 jours, en fonction de l'outil de reporting et de l'origine des données brutes.

<div id="report-types" />

<Accordion title="Types de rapport">

<div id="blocked-install-postbacks" />

<div id="clicks" />

<div id="postattribution-inapp-events" />

<div id="blocked-inapp-events" />

<div id="postattribution-installs" />

<div id="installs" />

<div id="protect360-raw-data-report-types" />

#### Types de rapports de données brutes Protect 360

| Rapport | Description |
| --- | --- |
| d'installations | Les rapports comprennent :<ul><li>**Fausses installations** : installations identifiées comme frauduleuses par le moteur Protect360. Ces éléments n'apparaissent dans aucun tableau de bord ou données brutes d'AppsFlyer, à l'exception du tableau de bord et des données brutes de Protect360.</li><li>**Installations détournées** : l'utilisateur réel installe là où l'attribution est volée, mais Protect360 [corrige l'attribution](/docs/protect360-raw-data-reports#correction-de-lattribution-des-installations-détournées).</li><li>**Règles de validation** : qui ont bloqué soit l'installation, soit l'attribution (Protect360 [corrige l'attribution](/docs/protect360-raw-data-reports#correction-de-lattribution-des-installations-détournées)).</li></ul> |
| Installations post-attribution | Les rapports incluent les installations attribuées à une source média, mais qui se sont révélées frauduleuses par la suite.Protect360 [corrige l'attribution](/docs/protect360-raw-data-reports#correction-de-lattribution-des-installations-détournées). |
| Événements in-app bloqués | Les rapports incluent les événements in-app de :<ul><li>**Fausses installations** : les IAE sont bloqués.</li><li>**Événement in-app** : identifié comme frauduleux indépendamment des installations initiales.</li><li>**Règles de validation** :<ul><li>Les IAE provenant d'une règle qui bloquait l'installation ou l'attribution bloquée.</li><li>Les IAE provenant d'une règle qui bloquait l'événement in-app.</li></ul></li></ul> |
| Évènements in-app post-attribution | Les rapports incluent les événements in-app de :<ul><li>Identifié après l'attribution.</li><li>Des installations attribuées à une source média, mais qui se sont révélées frauduleuses par la suite.</li></ul> |
| Clics | Les rapports incluent les clics bloqués avec les raisons du blocage. |
| Postbacks d'installations bloquées | Les rapports incluent des copies des postbacks de rejet envoyés aux sources média apportant des installations bloquées. |

</Accordion>

<div id="postattribution-reports" />

<Accordion title="Rapports post-attribution">

* Les rapports de fraude de données brutes post-attribution possèdent la même structure que les rapports sur les fraudes bloquées.
* Le rapport post-attribution du mois en cours (par date d'installation) continue d'être mis à jour jusqu'au septième jour du mois suivant (date de détection).
* Les rapports de données brutes post-attribution sont réservés aux annonceurs. Les agences ont besoin que les <Anchor target="_blank" href="/partners/fr/docs/protect360-for-integrated-partners">autorisations</Anchor> soient activées pour y accéder.
* Les rapports contiennent les événements de fraude post-attribution identifiés par Protect360 et rassemblent toutes les sources média dans un rapport unique.  **Remarque** : Si aucun événement de fraude post-attribution n'a été identifié pour la période sélectionnée, le rapport est vide.
* Les rapports de fraude sur les données brutes post-attribution sont disponibles comme suit :

  * Interface utilisateur du tableau de bord : limitée à une source média pendant un mois civil.
  * API Pull : contient toutes les sources média.  (Restriction : disponible uniquement pour les propriétaires d'app)

<div id="using-post-attribution-reports" />

#### **Utilisation des rapports post-attribution**

* Sélectionnez n'importe quelle combinaison d'installation/IAE et détectez les plages de dates selon vos besoins.
* Tenez compte du fait que Protect360 procède à la détection post-attribution pendant le mois civil de l'installation et jusqu'au septième jour du mois suivant. Cela signifie, par exemple, que pour les installations de novembre, Protect360 vérifie la fraude jusqu'au 7 décembre.
* La meilleure pratique pour utiliser cette API Pull est la suivante :
  * Supposons que vous génériez un rapport quotidiennement.
  * Définissez la plage de dates d'installation sur 60 jours à partir de la journée en cours.
  * Définissez la plage de détection detect-from/detect-to jusqu'à la veille du jour en cours.  
    Cela signifie que vous obtiendrez la liste des fraudes post-attribution détectées la veille. Si vous n'avez pas généré de rapport pendant quelques jours, ajustez la plage de dates de détection et extrayez le rapport.

<div id="example" />

> 📄 **Exemple**
>
> **Exemple A** : en décembre (date d'installation), 15 installations sont attribuées à *example\_media* . Le 3 janvier (date de détection), Protect360 identifie *example\_media* comme un fraudeur. Les 15 installations attribuées à *example\_media* sont donc répertoriées comme frauduleuses dans le rapport de fraude post-attribution, pour que le propriétaire de l'application prenne les mesures nécessaires.
>
> **Exemple B** : en décembre, 15 installations sont attribuées à example\_media. Le 9 janvier, Protect360 identifie example\_media comme un fraudeur. Dans ce cas, aucune action n'est entreprise par Protect360, car le fraudeur a été identifié après la clôture du mois, le 7 janvier.

</Accordion>

<div id="raw-data-availability-by-tool-type" />

<Accordion title="Disponibilité des données brutes par type d'outil">

<div id="protect360-raw-data-availability-by-tool-type" />

#### Disponibilité des données brutes Protect 360 par type d'outil

<table><thead><tr><th>Rapport</th><th>Actualisation des données</th><th>API pull</th><th>Page Données d'exportation</th><th>Data Locker</th></tr></thead><tbody><tr><td>d'installations</td><td>temps réel</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>Événements in-app bloqués </td><td>temps réel</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Clics</td><td>temps réel</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Postbacks d'installations bloquées</td><td>temps réel</td><td>-</td><td><span>✓</span></td><td>-</td></tr><tr><td>Installations post-attribution</td><td><p>Tous les jours à 10:00 UTC</p></td><td><p><span>✓</span></p></td><td><span>✓</span></td><td><span>✓\*</span></td></tr><tr><td>Évènements in-app post-attribution</td><td><p>Tous les jours à 10:00 UTC</p></td><td><span>✓</span></td><td><span>✓</span></td><td>-</td></tr></tbody><tfoot><tr><td colspan="5"><p>\* Limitations du rapport via Data Locker :</p><ul><li>Transparence de l'agence non prise en charge. Ce qui signifie que le trafic généré par une agence ne contient pas le nom de la source média qui envoie l'installation. </li><li>Le rapport contient un ensemble de champs unique comparé aux autres rapports Data Locker. Cette liste n'est pas modifiable. </li><li>Les données de retargeting ne sont pas disponibles dans le rapport d'installations, elles apparaissent uniquement dans le rapport d'installations post-attribution. </li></ul></td></tr></tfoot></table>

</Accordion>

<div id="getting-raw-data-reports" />

## Obtenir des rapports de données brutes

Les rapports de données brutes sont disponibles via téléchargement, API Pull et Data Locker (compartiment S3). Vous pouvez également <Anchor target="_blank" href="/partners/fr/docs/protect360-for-integrated-partners">donner à vos partenaires l'accès aux rapports</Anchor>.

<div id="download" />

<Accordion title="Télécharger">

**À télécharger :**

1. Dans le tableau de bord Protect360, allez dans **Rapports de données brutes** > **Blocages** ou **Post-attribution.**
   * Pour les rapports post-attribution, choisissez une source média et un mois.
2. Sélectionnez le rapport **Protect360 et des règles de validation** à télécharger.

**OU**

1. Dans le tableau de bord AppsFlyer, allez dans **données d'exportation**.
2. Sélectionnez le rapport **Protect360 et des règles de validation** à télécharger.

**Remarque** : les rapports téléchargés depuis la page des données d'exportation contiennent l'ensemble des sources média.

</Accordion>

<div id="pull-api" />

<Accordion title="API pull">

**Pour télécharger les rapports de données brutes disponibles via API Pull :**

**Avant de commencer :**

Vous devez avoir un jeton d'API Pull. Le jeton s'obtient auprès d'un <Anchor target="_blank" href="/marketers/fr/docs/managing-appsflyer-tokens">utilisateur admin</Anchor>.

1. Rendez-vous dans **Intégration > Accès API.** La page<Anchor target="_blank" href="/marketers/fr/docs/pull-api-raw-data">API Pull</Anchor> s'ouvre.
2. Dans la section des rapports de fraude Protect360, sélectionnez l'appel API Pull requis.
3. Remplissez les paramètres selon vos besoins. Le tableau qui suit répertorie les paramètres.
4. Extrayez le rapport.

<div id="pull-api-raw-data-report-parameters" />

#### Paramètres de rapport des données brutes de l'API Pull

| Paramètre | Description | Format | Obligatoire |
| --- | --- | --- | --- |
| app\_id | L'ID app tel qu'il apparaît dans AppsFlyer | Chaîne | Oui |
| api\_token | Récupérez la clé depuis le tableau de bord. Rendez-vous dans **Intégration** > **Accès API.** Seul un utilisateur admin peut récupérer le jeton d'API. | Chaîne | Oui |
| from | Début de la plage de dates :<ul><li>Pour les installations, il s'agit de la date d'installation.</li><li>Pour les événements in-app, il s'agit de la date de l'événement.</li></ul> | AAAA-MM-JJ | Oui |
| to | Fin de la plage de dates :<ul><li>Pour les installations, il s'agit de la date d'installation.</li><li>Pour les événements in-app, il s'agit de la date de l'événement.</li></ul> | AAAA-MM-JJ | Oui |
| event\_name | [Facultatif pour les fraudes d'événements in-app post-attribution]<br /><br />Filtrez les événements par événement in-app. Limitez le rapport à des événements spécifiques. Un ou plusieurs événements peuvent être inclus.<br /><br />Exemple d'utilisation : `&event_name=af_purchase,af_login` | Chaîne | Non |
| additional\_fields=rejected\_reason\_value | [Facultatif pour les fraudes d'événements in-app post-attribution]<br /><br />**<Anchor target="_blank" href="/marketers/fr/docs/raw-data-field-dictionary#protect360">rejected\_reason\_value</Anchor>** affiche le contributeur valide (source média) pour les installations/événements in-app détournés. Renseigné par <Anchor target="_blank" href="/marketers/fr/docs/raw-data-field-dictionary#attribution::2a6fd501">**contributeur[1-3]**</Anchor> ou bien **organique**. | Chaîne | Non |
| detect-from | [Facultatif pour les installations post-attribution]<br /><br />Début de la plage de dates de détection de fraude. (La valeur par défaut est *from.*) (Utilisée pour la fraude d'installation post-attribution). (Utilisée pour la fraude d'installation post-attribution). | AAAA-MM-JJ | Non |
| detect-to | [Facultatif pour les installations post-attribution]<br /><br />Fin de la plage de dates de détection de fraude (La valeur par défaut est *to.)* | AAAA-MM-JJ | Non |

</Accordion>

<div id="data-locker" />

<Accordion title="Data Locker">

Data Locker inscrit les données brutes dans un compartiment AWS S3.

<Anchor target="_blank" href="/marketers/fr/docs/data-locker-advertiser-reports#protect360">Voir la liste des rapports Protect360 disponibles</Anchor>.

<Anchor target="_blank" href="/marketers/fr/docs/data-locker-for-marketers#aws-cli">Reportez-vous aux instructions de configuration de Data Locker</Anchor>.

</Accordion>

<div id="protect360-report-structure" />

## Structure de rapports Protect360

Les rapports Protect360 ont la même structure globale de champs que les rapports d'acquisition utilisateur.

En plus <Anchor target="_blank" href="/marketers/fr/docs/raw-data-field-dictionary">des champs de rapports des données brutes</Anchor> habituels, les rapports Protect360 incluent les champs de retargeting et de motifs de blocage suivants :

<div id="blocked-reasons" />

### Motifs de blocage

<div id="click-level-blocked-reasons" />

<Accordion title="Raisons du blocage au niveau des clics">

Au niveau des clics, seuls les clics sont bloqués. Le processus d'attribution se contente de les ignorer.

| Motif bloqué | Description |
| --- | --- |
| ip\_blacklist | Basé sur une liste créée dynamiquement (<Anchor target="_blank" href="/marketers/fr/docs/protect360-anti-fraud-guide#ip-denylists">détails</Anchor>) |
| invalid\_fingerprint | Clics S2S uniquement : les paramètres non valides sont envoyés par la source (pour la correspondance probabiliste) |
| click\_capping | Des taux extrêmement élevés de clics frauduleux sont détectés sur ce réseau publicitaire. <Anchor target="_blank" href="/partners/fr/docs/protect360-for-integrated-partners#impression-capping">En savoir plus</Anchor> |
| click\_signing | La signature du clic n'est pas validée. <Anchor target="_blank" href="/partners/fr/docs/click-signing-for-ad-networks">En savoir plus</Anchor> |
| input\_validation | Nom de source média invalide |

</Accordion>

<div id="install-level-blocked-reasons" />

<Accordion title="Raisons de blocage au niveau de l'installation">

Au niveau de l'installation, nous identifions suffisamment d'informations au moment de l'installation pour déterminer si :

* L'installation est frauduleuse, c'est à dire si l'utilisateur qui installe l'app n'est pas une vraie personne. Dans ce cas, l'attribution est complètement bloquée.
* L'attribution est détournée, car l'utilisateur est une vraie personne mais l'engagement est falsifié. Dans ce cas, l'engagement frauduleux est bloqué et l'attribution est réattribuée au premier ad network contributeur valide.

Les tableaux suivants répertorient les différentes raisons qui peuvent bloquer une installation :

<div id="install-level-fake-install-block-sub-reasons" />

#### Niveau installation : causes de blocage des installations frauduleuses

| Motif bloqué | Sous-motif bloqué | Description |
| --- | --- | --- |
| Robots | fake\_device\_parameters | Comportement non humain détecté dans les paramètres de l'appareil durant le processus d'installation de l'app |
| Robots | fake\_install\_parameters | Comportement non humain détecté dans les paramètres de l'installation durant le processus d'installation de l'app |
| Robots | bayesian\_network | Identification de schémas frauduleux selon le réseau bayésien |
| install\_store\_validation | - | Échec de <Anchor target="_blank" href="/marketers/fr/docs/implement-apple-app-store-itunes-install-validation">validation du reçu d'installation</Anchor> de l'App Store Apple |
| validation\_bots | invalid\_device\_parameters | Anomalie au niveau du contenu de certains champs de l'appareil - défini par le client |
| validation\_bots | validation\_rules | Règles avec lesquelles les installations sont bloquées en fonction d'une règle de validation définie manuellement |

<div id="install-level-attribution-hijacking-block-sub-reasons" />

#### Niveau installation : causes de blocage des installations piratées

| Motif bloqué | Sous-motif bloqué | Description |
| --- | --- | --- |
| ctit\_anomalies | short\_ctit | Installations bloquées à cause d'un CTIT trop court : défini par Protect360 |
| install\_hijacking | referrer\_hijack | Tentative de piratage bloquée selon les paramètres de l'API GooglePlay et du SDK AppsFlyer |
| install\_hijacking | integration\_temporarily\_blocked | Installation bloquée car le partenaire (pid) présente un niveau de fraude extrêmement élevé ainsi que d'importantes anomalies sur l'ensemble de son trafic |
| validation\_hijacking | short\_ctit | Installations bloquées à cause d'un CTIT trop court : défini par le client |
| validation\_hijacking | empty\_site\_id | Installations bloquées en raison d'un identifiant de site non renseigné. La mise en place des règles se fait progressivement |
| validation\_hijacking | validation\_rules | Règles avec lesquelles les attributions sont bloquées en fonction d'une règle de validation définie manuellement |

</Accordion>

<div id="cluster-level-blocked-reasons" />

<Accordion title="Motifs de blocage au niveau du regroupement">

Lorsqu'un modèle de fraude est détecté, la source frauduleuse est classée dans la liste bloquée. Les installations provenant des sources figurant sur cette liste sont bloquées pour les raisons suivantes :

* L'installation est frauduleuse, c'est à dire si l'utilisateur qui installe l'app n'est pas une vraie personne. Dans ce cas, l'attribution est complètement bloquée.
* L'attribution est détournée, car l'utilisateur est une vraie personne mais l'engagement est falsifié. Dans ce cas, l'engagement frauduleux est bloqué et l'attribution est réattribuée au premier ad network contributeur valide.

Les tableaux suivants répertorient les différentes raisons qui peuvent entraîner le blocage au niveau regroupement :

<div id="cluster-level-fake-install-block-reasons" />

#### Niveau regroupement : causes de blocage des installations frauduleuses

| Motif bloqué | Sous-motif bloqué | Description |
| --- | --- | --- |
| Robots | timestamp\_anomalies | Anomalies liées au temps de clics du flux d'attribution et autres marqueurs temporels collectés sur l'appareil |
| bots, site\_blacklist | device\_emulators | Installations générées à grande échelle par des scripts automatiques s'exécutant dans un environnement virtuel. |
| site\_blacklist | device\_farms | Taux élevés de (nouveaux) appareils inconnus |
| behavioral\_anomalies | behavioral\_anomalies | Comportement in-app suspect par rapport au modèle de comportement utilisateur habituel de l'app |

<div id="cluster-level-attribution-hijacking-block-reasons" />

#### Niveau regroupement : causes de blocage des attributions piratées

| Motif bloqué | Sous-motif bloqué | Description |
| --- | --- | --- |
| ctit\_anomalies, install\_hijacking | ctit\_anomalies | Modèle CTIT anormal selon les critères habituels de l'app |
| click\_flood | click\_flood | Volume de clics anormalement élevé sur une distribution CTIT longue |
| install\_hijacking | click\_clusters | Clics générés par un malware au niveau de l'appareil |

</Accordion>

<div id="inapp-level-blocked-reasons" />

<Accordion title="Raisons de blocage au niveau in-app">

Les événements in-app peuvent être bloqués pour les raisons suivantes :

* L'installation initiale a été identifiée comme frauduleuse.
* À cause d'une règle de validation définie.
* Notre algorithme a détecté la fraude.

Le tableaux suivant répertorient les différentes causes qui peuvent créer un blocage au niveau in-app :

<div id="in-app-level-block-reasons" />

#### Causes de blocage au niveau in-app

| Motif bloqué | Sous-motif bloqué | Description |
| --- | --- | --- |
| Hérite de l'installation | Hérite de l'installation | Installation initiale identifiée comme frauduleuse au niveau [installation](/docs/protect360-raw-data-reports#install-level-blocked-reasons) ou [liste bloquée](/docs/protect360-raw-data-reports#cluster-level-blocked-reasons). |
| inapps\_bots | fake\_device\_parameters | L'algorithme AppsFlyer détecte la fraude |
| in\_app\_store\_validation | - | Échec de la <Anchor target="_blank" href="/marketers/fr/docs/legacy-receipt-validation-for-in-app-purchases">validation de réception</Anchor> pour les achats intégrés. |
| validation\_inapps | validation\_rules | Basé sur une règle de validation définie manuellement |

</Accordion>

### Retargeting

Les données brutes Protect360 incluent les installations et sessions frauduleuses issues de campagnes de retargeting (nommées respectivement : réattributions et réengagements). Les données affichent les champs <Anchor target="_blank" href="/marketers/fr/docs/raw-data-field-dictionary#event">nom de l'événement</Anchor> et  <Anchor target="_blank" href="/marketers/fr/docs/raw-data-field-dictionary#attribution::e9c68f6c">type de conversion de retargeting</Anchor>. Elles sont signalées comme étant soit :

* Installation (concerne le nom de l'événement, mais pas le type de conversion de retargeting)
* Réattribution
* RÉENGAGEMENT
* Réinstallation

Les données brutes de retargeting Protect360 sont proposées pour les blocages en temps réel et la fraude identifiée en post attribution comme suit :

<table><thead><tr><th>Rapport </th><th>Données d'exportation</th><th>API pull</th><th>Data Locker</th></tr></thead><tbody><tr><td>d'installations</td><td><span>✓\*</span></td><td><span>✓\*</span></td><td>-</td></tr><tr><td>Installations post-attribution</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td colspan="4"> <span>\* Données de réengagement non disponibles</span><span></span><br/> </td></tr></tbody></table>

<div id="traits-and-limitations" />

<div id="hijacked-installs-attribution-correction" />

### Correction de l'attribution des installations détournées

En ce qui concerne les installations détournées, AppsFlyer bloque l'attribution au réseau frauduleux et attribue l'installation à la dernière source contributrice légitime. 

Pour les installations détournées, utilisez le champ <Anchor target="_blank" href="/marketers/fr/docs/raw-data-field-dictionary#protect360">rejected\_reason\_value</Anchor> pour identifier le contributeur valide (source média), c'est-à-dire le contributeur qui aurait dû recevoir l'attribution à l'origine.

* La valeur **rejected\_reason\_value** est renseignée avec <Anchor target="_blank" href="/marketers/fr/docs/raw-data-field-dictionary#attribution::2a6fd501">**contributeur[1-3]**</Anchor> ou **organique**. Consultez les champs **contributeur[1-3]** **source média/partenaire**pour accéder aux informations du contributeur et faire le rapprochement.
* Si les champs du contributeur ne s'affichent pas dans votre rapport, vous pouvez les ajouter depuis la page **Données d'exportation**.

**Remarque** : lorsque les installations détournées sont bloquées en temps réel, les attributions correctes s'affichent dans les tableaux de bord et les rapports AppsFlyer (pas seulement dans Protect360). Lorsque des installations détournées sont identifiées post-attribution, les attributions correctes s'affichent uniquement dans les données brutes de Protect360.

<div data-zendesk-anchors="about-protect360-raw-data-reports=%C3%A0-propos-des-rapports-de-donn%C3%A9es-brutes-protect360 h_01HE7S55TCE60A34T6RCNTCQK8=%C3%A0-propos-des-rapports-de-donn%C3%A9es-brutes-protect360 h_01HE7S55TC4G31R9EANMKCZ7V5=report-types protect360-rawdata-report-types=types-de-rapports-de-donn%C3%A9es-brutes-protect-360 h_01HE7S55TCKQYTXPV6J54SHM0D=types-de-rapports-de-donn%C3%A9es-brutes-protect-360 h_01HE7S55TC4F5S243BSGN74RDK=postattribution-reports using-postattribution-reports=utilisation-des-rapports-post-attribution h_01HE7S55TC7KCF75KFXHCE3K2K=utilisation-des-rapports-post-attribution h_01HE7S55TCR8BKZ0PQ5B14X3X4=exemple h_01HE7S55TC95YC1BJJ0ZERCQ14=raw-data-availability-by-tool-type protect360-rawdata-availability-by-tool-type=disponibilit%C3%A9-des-donn%C3%A9es-brutes-protect-360-par-type-doutil h_01HE7S55TCH4CES29C5J3QXQK4=disponibilit%C3%A9-des-donn%C3%A9es-brutes-protect-360-par-type-doutil getting-raw-data-reports=obtenir-des-rapports-de-donn%C3%A9es-brutes h_01HE7S55TC3MRT6E9QV0J0X6FC=obtenir-des-rapports-de-donn%C3%A9es-brutes h_01HE7S55TCBVFQ1DH06G53BNEN=download h_01HE7S55TCMT81J4SWBFQFYV2C=pull-api pull-api-raw-data-report-parameters=param%C3%A8tres-de-rapport-des-donn%C3%A9es-brutes-de-lapi-pull h_01HE7S55TCRRD95D0QPCXBRF8T=param%C3%A8tres-de-rapport-des-donn%C3%A9es-brutes-de-lapi-pull h_01HE7S55TCMAY86J1HKYB0APZ6=data-locker protect360-report-structure=structure-de-rapports-protect360 h_01HE7S55TCS91ZC9V3K0VDSVXK=structure-de-rapports-protect360 blocked-reasons=motifs-de-blocage h_01HE7S55TC1ZEDD5ABD21FCPY2=motifs-de-blocage h_01HE7S55TDMDSVQCVSV5YS3CZN=click-level-blocked-reasons h_01HE7S55TD754T07FWHFK5P71K=install-level-blocked-reasons install-level-fake-install-block-reasons=niveau-installationcauses-de-blocage-des-installations-frauduleuses h_01HE7S55TDHTE5P47N1CCREGZX=niveau-installationcauses-de-blocage-des-installations-frauduleuses install-level-attribution-hijacking-block-reasons=niveau-installationcauses-de-blocage-des-installations-pirat%C3%A9es h_01HE7S55TDFA6WGAHE80ECV8CA=niveau-installationcauses-de-blocage-des-installations-pirat%C3%A9es h_01HE7S55TDCHG0CVJA3JRSAW3G=cluster-level-blocked-reasons cluster-level-fake-install-block-reasons=niveau-regroupement-causes-de-blocage-des-installations-frauduleuses h_01HE7S55TDBES0BY0FF3WKSSVG=niveau-regroupement-causes-de-blocage-des-installations-frauduleuses cluster-level-attribution-hijacking-block-reasons=niveau-regroupement-causes-de-blocage-des-attributions-pirat%C3%A9es h_01HE7S55TD3M45TH4PY2W805W7=niveau-regroupement-causes-de-blocage-des-attributions-pirat%C3%A9es h_01HE7S55TDGB05PEZX8KS3J3QJ=inapp-level-blocked-reasons inapp-level-block-reasons=causes-de-blocage-au-niveau-in-app h_01HE7S55TD661EHCV50S9BW5MS=causes-de-blocage-au-niveau-in-app h_01HE7S55TDSYDC8BWZ8D8DF9JE=retargeting hijacked-installs-attribution-correction=correction-de-lattribution-des-installations-d%C3%A9tourn%C3%A9es h_01HE7S55TD8SDCQJCCYQC0MNES=correction-de-lattribution-des-installations-d%C3%A9tourn%C3%A9es" />
