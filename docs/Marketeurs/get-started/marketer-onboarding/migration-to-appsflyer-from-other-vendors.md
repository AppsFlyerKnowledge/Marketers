---
title: Migrer vers AppsFlyer à partir d'autres fournisseurs
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2019-07-01T13:11:37Z'
  edited_at: '2023-08-29T09:11:09Z'
  id: 360001923697
  locale: fr
  section: Marketer onboarding
  section_id: 6550866490129
  url: https://support.appsflyer.com/hc/fr/articles/360001923697
---
> **En bref :** planifiez votre migration vers AppsFlyer à partir d'un autre fournisseur d'attribution. Évitez les doubles frais, la duplication et la perte de données pendant la période de migration.

<Image align="center" alt="flux de migration" src="https://files.readme.io/31d67493ae3ae6912b4da3163ebb731a8d58494c3007ef1d08cb7332226d9e81-360017326677.png" />

<div id="compare-measurement-between-appsflyer-and-other-mmps" />

<div id="about-migrating-to-appsflyer-from-other-vendors" />

## Présentation

La migration vers AppsFlyer depuis un autre fournisseur induit les étapes suivantes :

* [Intégration SDK](/docs/migration-to-appsflyer-from-other-vendors#intégration-sdk)
* [Migration d'appareil](/docs/migration-to-appsflyer-from-other-vendors#migration-dappareil-facultatif)
* [Migration de campagne](/docs/migration-to-appsflyer-from-other-vendors#migration-de-campagne)
* [Configuration du rapport de données](/docs/migration-to-appsflyer-from-other-vendors#configuration-du-rapport-de-données)

Vous pouvez travailler sur ces différentes opérations simultanément. Cependant, nous vous recommandons de :

* Terminer toutes les opérations avant de publier votre app mise à jour avec le SDK AppsFlyer.
* Mettre en pause les campagnes marketing existantes avant d'effectuer la migration de l'ID d'appareil.

> 📘 **Remarque**
>
> Si vous souhaitez comparer la mesure d'attribution entre votre MMP actuelle et AppsFlyer pour les mêmes campagnes et la même source média, consultez <Anchor target="_blank" href="/marketers/fr/docs/measuring-attribution-with-multiple-mmps">cet article</Anchor>.

<div id="tasks" />

## Opérations à effectuer

Le tableau suivant contient le contenu de chaque opération et ses besoins. Pour obtenir une répartition des tâches et l'ordre dans lequel vous devez les accomplir, et pour suivre votre progression, téléchargez <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/1x6kdhfnfKLYHJgsROPUv7pQYC6i-Q5H3DdejBr8jKjw/export?format=xlsx">cette feuille de calcul</Anchor>.

<div id="scope-of-work" />

#### Mise en application

<table><thead><tr><th>Tâche</th><th>Action requise</th><th>Personnes concernées</th><th>Temps estimé</th><th>Remarques</th></tr></thead><tbody><tr><td>Conditions préalables</td><td><ol><li> <a href="https://www.appsflyer.com/get-started" target="_blank">Créer un compte AppsFlyer</a>.</li><li> <a href="./adding-an-app-to-appsflyer" target="_blank">Ajouter l'app</a> dans AppsFlyer</li><li>[Facultatif] Modifiez la <a href="./set-up-re-attribution-window" target="_blank">fenêtre de réattribution</a> par défaut de 90 jours pour l'aligner sur votre <span>définition des utilisateurs actifs.</span> </li></ol></td><td>Utilisateur du tableau de bord AppsFlyer/Marketer</td><td><p>2 heures</p></td><td> </td></tr><tr><td><a href="./migration-to-appsflyer-from-other-vendors#intégration-sdk">Intégration SDK</a></td><td><ul><li>Intégrez le SDK AppsFlyer à votre app.</li><li>Mappez les événements in-app du S2S ou SDK.</li><li>Mettez à jour la version de l'app dans les app stores.</li></ul></td><td>Développeurs d'apps</td><td><p>1-2 semaines</p></td><td><ul><li> <strong>Recommandé</strong> : intégrer le SDK AppsFlyer dans une app de pré-production pour la tester.</li><li>Une fois toutes les autres tâches terminées, l'app de production doit être mise à jour dans les app stores.</li></ul></td></tr><tr><td> <a href="./migration-to-appsflyer-from-other-vendors#migration-dappareil-facultatif">Migration de l'appareil</a> [facultatif]</td><td>Migrez les ID d'appareil pour éviter la double attribution de vos utilisateurs existants.</td><td>Spécialiste des données</td><td>1-2 semaines</td><td rowspan="2"><ul><li>Pensez à interrompre les campagnes existantes avant la migration, et à les relancer une fois la version de l'app mise à jour. </li><li>Pour assurer une couverture complète, pensez à répéter la migration des appareils à la date de la migration finale. </li></ul></td></tr><tr><td><a href="./migration-to-appsflyer-from-other-vendors#migration-de-campagne">Migration de campagne</a></td><td><ul><li>Intégrez vos réseaux publicitaires dans AppsFlyer</li><li>Migrez les campagnes existantes depuis :  <ul><li>Les SRN</li><li>Ad networks non SRN</li><li>Médias propres</li></ul></li></ul></td><td>Marketeur/gestionnaire UA</td><td>1-3 semaines</td></tr><tr><td><a href="./migration-to-appsflyer-from-other-vendors#configuration-du-rapport-de-données">Configuration du rapport de données</a></td><td><ul><li>Adaptez/mappez les structures actuelles vos rapports aux structures d'AppsFlyer.</li><li>Préparez-vous à recevoir les rapports d'AppsFlyer.</li></ul></td><td>Spécialiste des données</td><td>2-4 semaines</td><td> </td></tr></tbody></table>

<div id="sdk-integration" />

### Intégration SDK

<div id="sdk-integration::c763138b" />

<Accordion title="Intégration SDK">

Le SDK AppsFlyer intégré à l'app est le lien entre l'app et la plateforme AppsFlyer. Il signale les installations et les ouvertures d'app, les événements in-app, etc.

**Pour intégrer le SDK AppsFlyer** :

1. Intégrez le SDK AppsFlyer dans l'app.Voir les guides de l'intégration du SDK sous <Anchor target="_blank" href="/marketers/fr/docs/sdk-integration-overview">Android</Anchor> et <Anchor target="_blank" href="/marketers/fr/docs/sdk-integration-overview">iOS</Anchor>
2. Mappez les événements in-app que vous souhaitez enregistrer en utilisant les schémas AppsFlyer.  
   Cela peut être fait via le <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview">SDK</Anchor> ou <Anchor target="_blank" href="/marketers/fr/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor>.
3. Supprimez le SDK du vendeur d'attribution concurrent.  
   Vous pouvez le faire immédiatement et passer exclusivement à AppsFlyer, ou exécuter les deux SDK simultanément pendant quelques semaines. Le tableau ci-dessous présente une ventilation de ces options.  

| Option | Que se passe-t-il après la sortie de la version mise à jour de l'app ? | Impact |
| --- | --- | --- |
| Supprimer le SDK du concurrent (recommandé) | Seul AppsFlyer enregistre les nouvelles installations et met à jour les utilisateurs.  <br />Le concurrent continue de montrer les événements réalisés par les utilisateurs, jusqu'à ce que ces derniers mettent également à jour leur app. | <ul><li>Transition rapide.</li><li>Pas de double attribution.</li></ul> |
| Conserver le SDK du concurrent pendant une période de transition | AppsFlyer et les concurrents attribuent les nouvelles installations et créent des rapports d'événements. À une date ultérieure, retirez le SDK du concurrent. | <ul><li>Validation des données possible. Cela signifie que vous pouvez comparer les données d'AppsFlyer et de l'autre fournisseur.</li><li>Double attribution, qui peut entraîner une double facturation avec les ad networks. Consultez l'exemple ci-dessous.</li><li>Charge de travail plus élevée.</li></ul> |

4. Une fois que toutes les autres tâches prévues sont terminées, mettez à jour la version de l'app avec le SDK AppsFlyer du marché. Les nouveaux utilisateurs sont attribués par AppsFlyer.   
   **Remarque** :
   * Veillez à mettre à jour l'app pour iOS, Google Play et tout marché hors magasin Android pertinent.
   * Votre app Android peut exister sur des sites APK non officiels, même si vous ne le savez pas (cherchez sur le web le nom du paquet de votre app pour le découvrir). Les sites APK prennent un certain temps pour se mettre à jour vers la dernière version. Ils peuvent donc amener des utilisateurs organiques, qui installent les anciennes versions sans le SDK AppsFlyer.
   * Le déploiement des mises à jour des apps dans les app stores peut prendre jusqu'à deux jours. Les utilisateurs qui installent pendant cette phase peuvent toujours obtenir la version précédente.

</Accordion>

<div id="device-migrationoptional" />

### Migration d'appareil-facultatif

<div id="about-device-migration" />

<Accordion title="À propos de la migration des appareils">

La migration d'appareil consiste à importer dans AppsFlyer la liste des ID de vos appareils existants (IDFA, IDFV, GAID, CUID). Vous devez effectuer cette opération avant de publier la nouvelle version de l'app, qui inclura le SDK AppsFlyer. Il existe deux manières de migrer des appareils, via [migration attribuée](/docs/migration-to-appsflyer-from-other-vendors#attributed-migration) ou via [migration non attribuée](/docs/migration-to-appsflyer-from-other-vendors#nonattributed-migration).

La migration des appareils vient corriger les erreurs de données qui faisaient que les utilisateurs existants d'une app qui téléchargeaient l'application étaient attribués par votre précédent fournisseur. Par exemple la double facturation SRN, qui a lieu lorsque des utilisateurs initialement attribués à un SRN sous votre précédent fournisseur, et qui se trouvent toujours dans la fenêtre rétrospective, sont attribués une deuxième fois au SRN sous AppsFlyer.

<div id="note" />

<div id="example" />

> 📄 **Exemple**
>
> * Un nouvel utilisateur clique sur une publicité dans Facebook et installe votre app le 15 juin.
> * Le 24 juin, l'utilisateur met à jour l'app avec le SDK AppsFlyer, et la lance. Pour AppsFlyer, il s'agit d'un nouvel utilisateur, qui doit être attribué en temps réel.
> * AppsFlyer interroge Meta ads avec l'ID d'appareil de l'utilisateur. Parce que l'utilisateur est toujours dans la fenêtre rétrospective de 28 jours de Meta ads, Meta ads s'auto-attribue l'utilisateur. Cela entraîne une double facturation au propriétaire de l'app pour le même utilisateur.

Une fois que vous avez migré les appareils, les données apparaissent dans AppsFlyer comme suit :

* **Données relatives aux installations** : comme dans le cas des <Anchor target="_blank" href="/marketers/fr/docs/set-up-re-attribution-window#reinstall">réinstallations</Anchor>, les appareils migrés n'ont pas de données d'installation. Les installations d'appareils migrés ne sont pas affichées dans AppsFlyer.
* **Données d'événements et de sessions in-app** : enregistrées et affichées comme organiques pour la [méthode de migration des appareils non attribués](/docs/migration-to-appsflyer-from-other-vendors#nonattributed-migration), ou attribuées à la source média et à la campagne, si vous utilisez la [méthode attribuée](/docs/migration-to-appsflyer-from-other-vendors#attributed-migration).
* **Retargeting** : les réattributions et les réengagements s'affichent normalement.
* **Données d'activité :** affichage normal.
* **Données de rétention et de cohorte :** il n'y a pas d'enregistrement de l'installation pour les appareils migrés. Par conséquent, ils ne sont associés à aucune cohorte et ne peuvent pas être affichés dans les rapports de rétention et de cohorte.

</Accordion>

<div id="how-to-migrate-devices" />

<Accordion title="Comment migrer un appareil">

**Pour migrer les appareils :**

1. Décidez de la population d'utilisateurs à migrer. Vous pouvez migrer tous les utilisateurs existants (ce qui peut vous empêcher d'obtenir des données de réattribution précises d'AppsFlyer), ou uniquement les utilisateurs qui ont récemment installé votre app (ce qui peut entraîner la double facturation pour certains utilisateurs plus anciens).  
   **Nous vous recommandons de migrer les utilisateurs qui sont actifs pendant votre période de réattribution en cours.** Par exemple, si votre app a une fenêtre de réattribution de 90 jours, migrez les utilisateurs qui comptent au moins une session au cours des 90 jours précédents.
2. [Facultatif] Demandez au responsable marketing/UA de mettre en pause les campagnes marketing existantes (des SRN, des réseaux publicitaires non-SRN, des médias propres, etc.) et ce jusqu'à la migration des appareils.   
   Si vous décidez de ne pas mettre les campagnes en pause, migrez les ID d'appareil restants du précédent fournisseur dès que la version mise à jour de l'app avec le SDK AppsFlyer est disponible en app store.
3. Préparez un fichier CSV en fonction des options sélectionnées par l'utilisateur à l'aide de la structure de migration [attribuée](/docs/migration-to-appsflyer-from-other-vendors#attributed-migration) ou [non attribuée](/docs/migration-to-appsflyer-from-other-vendors#nonattributed-migration). <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQPvcJ3zXjsB5Zrn8vqD_-QXFPjguDU9Y8_LfK6-2eOgdlDltmFdGoM-94Ouw-D327oMp9p0ZbFFawF/pub?output=csv">Voir l'exemple de fichier CSV</Anchor>
4. Envoyez le CSV à votre CSM AppsFlyer.  
   Votre CSM migrera les ID d'appareil vers AppsFlyer.

</Accordion>

<div id="attributed-migration" />

<Accordion title="Migration attribuée">

Les événements in-app et les sessions des appareils migrés vers AppsFlyer avec cette méthode sont enregistrés et affichés d'après la source média indiquée par le fournisseur d'attribution précédent, et selon les politiques de conservation des données des ad networks.

<div id="attributed-device-migration-csv-structure" />

#### Structure CSV de migration de l'appareil attribué

| Nom de la  <br /> colonne | Description | Obligatoire | Exemples |
| --- | --- | --- | --- |
| app\_id | ID de l'app tel qu'il apparaît dans le tableau de bord d'AppsFlyer | Oui | <ul><li>Android : com.great.app1</li><li>iOS : id123456789</li></ul> |
| platform | Plateforme de l'appareil : iOS ou Android | Oui | <ul><li>ios</li><li>android</li></ul> |
| device\_id | <ul><li>Android : gaid</li><li>iOS : IDFV (recommandé, si disponible) ou IDFA</li><li>Ne saisissez pas la même combinaison d'identifiant d'appareil et d'identifiant d'app dans plusieurs lignes. En cas de duplication, la dernière occurrence du fichier est utilisée.</li></ul> | Oui | <ul><li>**gaid** (minuscules) : 9c9a82fb-d5de-4cd1-90c3-527441c11828</li><li>**IDFV** (majuscules) : A7328D98-A973-402A-8B87-D22A8611F2AF</li><li>**IDFA** (majuscules) : 9876F1SS-2983-3855-27RR-2R626772VFNB</li></ul> |
| id\_type | <ul><li>Android : advertiserId (prend également en charge amazon\_aid)</li><li>iOS : idfa ou idfv</li><li>Actuellement, les autres identifiants, OAID, IMEI et Android ID ne sont pas pris en charge.<br />Utilisez la migration non attribuée pour les utilisateurs Android qui ne proviennent pas de Google Play.</li></ul> | Oui | <ul><li>ID d'annonceur</li><li>idfa</li><li>idfv</li></ul> |
| install\_time | L'heure d'installation de l'app originale au format UTC <Anchor target="_blank" href="http://joda-time.sourceforge.net/cal_iso.html">ISO 8601</Anchor> :<br />**aaaa-mm-jjTHH:MM:SS.SSS**<ul><li>**Recommandation** : laissez ce champ vide. Dans ce cas de figure, l'heure de la migration sera utilisée à la place.</li><li>Si vous indiquez la date, il doit s'agir d'une  date passée valide, mais qui ne doit pas se situer avant la fenêtre de réattribution.<ul><li>Dans certains cas, les appareils migrés sont considérés comme de nouvelles installations lors du premier lancement.<br />Exemple 1 : un appareil dont l'heure d'installation précède la date de création du fichier moins la fenêtre de réattribution de l'app ne sera pas migré avec attribution. Lors du premier lancement, l'appareil sera traité comme une nouvelle installation (probablement organique).<br />Exemple 2 : un appareil est migré avec une heure d'installation, mais le premier lancement n'a lieu qu'après la migration et en dehors de la fenêtre de réattribution. Dans ce cas, une nouvelle installation sera enregistrée.</li></ul></li></ul> | Non | 2018-01-22T08:45:33.412 |
| media\_source | <ul><li>Soit :<ul><li>ID du partenaire AppsFlyer tel qu'il apparaît dans le tableau de bord AppsFlyer</li><li>Source média personnalisée (ne peut pas être un ID de partenaire).</li></ul></li><li>Pour obtenir la liste des identifiants des partenaires exigés par AppsFlyer :<ul><li><Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner">Autorisez tous les partenaires intégrés.</Anchor></li><li>Lancez l'<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_v1-integrations">API Obtenir les intégrations actives</Anchor> pour obtenir une liste de toutes les intégrations actives.</li><li>Utilisez **media\_source\_name** de l'API comme valeur de **media\_source** dans le CSV.</li><li>Exceptions :<ul><li>Pour Apple Search Ads, utilisez les **Apple Search Ads**.</li><li>Pour Twitter, utilisez **twitter**.</li></ul></li></ul></li><li>Format : les valeurs sont sensibles à la casse</li></ul> | Oui | Non-organique : facebook\_int, googleadwords\_int<br /><br />Organique : organic |
| integrated\_partner | <ul><li>Indique si la source média est un partenaire intégré ou non. C'est à dire source média organique ou personnalisée.</li><li>Format : les valeurs sont sensibles à la casse</li></ul> | Oui | <ul><li>Oui</li><li>non (si media\_source est personnalisé)</li></ul> |
| Campagne | Pour plus de détails sur l'attribution granulaire, fournissez le nom de la campagne originale.<br /><br />Format : chaîne | Non |  |
| campaign\_id | Pour plus de détails sur l'attribution granulaire, fournissez l'ID de la campagne originale.<br /><br />Format : chaîne, espaces non autorisés | Non |  |

**Règles relatives aux fichiers CSV :**

* Le fichier CSV peut contenir des appareils d'utilisateurs provenant de plusieurs apps.
* Ne saisissez pas la même combinaison d'identifiant d'appareil et d'identifiant d'app dans plusieurs lignes. En cas de duplication, la dernière occurrence du fichier est utilisée.
* Tous les en-têtes de colonne doivent être inclus : app\_id, platform, device\_id, id\_type, install\_time, media\_source, integrated\_partner, campaign, campaign\_id. **Remarque** : L'ordre des champs est important et doit être respecté.
* Vous pouvez ajouter l'IDFV et l'IDFA pour le même appareil, mais ils doivent figurer dans des lignes distinctes. Tous les champs des différentes lignes doivent être identiques, à l'exception de device\_id.
* Chaque ligne doit contenir exactement 9 champs séparés par des virgules.
* Laissez les champs non obligatoires vides (vierges).
* Les fichiers peuvent contenir jusqu'à 20 millions de lignes.
* Si vous avez plusieurs fichiers, donnez un nom unique à chaque fichier.
* Encodez les données à l'aide d'UTF-8.
* [Facultatif] Compresser les fichiers à l'aide de ZIP ou GZIP.

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQPvcJ3zXjsB5Zrn8vqD_-QXFPjguDU9Y8_LfK6-2eOgdlDltmFdGoM-94Ouw-D327oMp9p0ZbFFawF/pub?gid=0&single=true&output=csv">Voir l'exemple de CSV</Anchor>

</Accordion>

<div id="nonattributed-migration" />

<Accordion title="Migration non attribuée">

Les appareils migrés vers AppsFlyer avec cette méthode sont enregistrés comme utilisateurs organiques. Leurs données d'événements et de sessions in-app sont également enregistrées et affichées comme organiques.

<div id="non-attributed-device-migration-csv-file-structure" />

#### Structure de fichier CSV pour la migration des dispositifs non attribués

| Colonnes | Quand l'utiliser | Exemple |
| --- | --- | --- |
| ID d'app + IDFA/GAID/IDFV | <ul><li>Si tous vos utilisateurs Android ont des identifiants GAID.</li><li>Utilisateurs iOS uniquement</li></ul> | [<Image alt="device_migration_file_option_1.png" src="https://files.readme.io/e4902c1fd33dc348d636f0c9a571bddad966c37aa1f8fad19cf6160c8c1b7dfb-360003138317.png" width="244px" />](https://files.readme.io/e4902c1fd33dc348d636f0c9a571bddad966c37aa1f8fad19cf6160c8c1b7dfb-360003138317.png) |
| ID d'app + ID d'appareil + type d'ID d'appareil | <ul><li>Si certains de vos utilisateurs Android n'ont qu'un IMEI ou un identifiant Android, mais pas de GAID (en dehors des marchés hors store, versions Android 4.4.2 ou -).</li><li>L'ID Android doit avoir un format hexadécimal.</li></ul>**Remarque** :<ul><li>Utilisez les chaînes exactes pour la colonne de **type ID** : advertiserId (prend également en charge amazon\_aid), idfa, idfv, android\_id, imei.</li><li>Si vous utilisez un ID Android ou un imei, et que AppsFlyer reçoit ultérieurement un meilleur identifiant, une nouvelle attribution peut être enregistrée.</li></ul> | [<Image alt="device_migration_file_option_2.png" src="https://files.readme.io/a85463bc7fd8f08e9c5e20d09b3b39f951547f18402c225ef3d952b18923b648-360003224698.png" width="244px" />](https://files.readme.io/a85463bc7fd8f08e9c5e20d09b3b39f951547f18402c225ef3d952b18923b648-360003224698.png) |

**Règles relatives aux fichiers CSV :**

* Le fichier CSV peut contenir des appareils d'utilisateurs provenant de plusieurs apps.
* Chaque ligne contient un seul identifiant d'appareil par app.
* Les fichiers doivent comprendre tous les en-têtes de colonne comme suit :
  * Option 1 : le fichier doit inclure tous les en-têtes de colonne comme suit : app\_id,device\_id
  * Option 2 : app\_id,device\_id,id\_type
* Les ID d'app en minuscules
* Les ID Android en minuscules
* IDFA/IDFV en majuscules
* Jusqu'à 25 millions de lignes autorisées

<Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQPvcJ3zXjsB5Zrn8vqD_-QXFPjguDU9Y8_LfK6-2eOgdlDltmFdGoM-94Ouw-D327oMp9p0ZbFFawF/pub?gid=935533759&single=true&output=csv">Voir l'exemple de CSV</Anchor>

</Accordion>

<div id="campaign-migration" />

### Migration de campagne

Passez d'une campagne marketing existante à AppsFlyer pour activer l'attribution AppsFlyer, et éviter la double facturation et la perte de données d'attribution.

**Remarque** : vous pouvez choisir de ne migrer que quelques campagnes de marketing à la fois. Dans ce cas, vous pouvez segmenter celles que vous voulez migrer par source média (ex : ad network ou agence), par géo ou par campagne.

<div id="srns" />

<Accordion title="Les SRN">

Les SRN répondent aux MMP (Mobile Measurement Partners) lorsqu'ils sont interrogés sur les engagements de certains appareils. Si deux MMP, par exemple AppsFlyer et un fournisseur d'attribution concurrent, interrogent le même SRN sur le même appareil installé, cela peut entraîner une double facturation.

**Pour migrer des campagnes SRN** :

* Activez et configurez les <Anchor target="_blank" href="/marketers/fr/docs/self-reporting-networks-srns#srn-intégrés-à-appsflyer">SRN</Anchor> pertinents dans AppsFlyer.

<div id="note-1" />

> 📘 **Remarque**
>
> * Les SRN peuvent exécuter plusieurs MMP (sauf Meta ads et Twitter).
> * Meta ads ne peut pas dédupliquer les événements in-app.

</Accordion>

<div id="nonsrn-ad-networks" />

<Accordion title="Ad networks non SRN">

Les liens d'attribution des ad networks enregistrent les engagements des utilisateurs et sont ensuite utilisés pour attribuer les engagements, qui deviennent des installations réelles.

**Pour migrer les campagnes des ad networks non-SRN**:

1. <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner">Activez</Anchor> les ad networks pertinents dans AppsFlyer.
2. <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#attribution-link-tab">Générer des liens d'attribution AppsFlyer</Anchor> pour chaque ad network.
3. Changez les liens existants dans chacune de vos campagnes avec les liens d'attribution AppsFlyer.

</Accordion>

<div id="owned-media" />

<Accordion title="Médias propres">

Les médias propres font référence aux liens d'attribution que vous utilisez dans :

* Partage de contenu
* Web-to-app
* E-mail
* SMS
* Postes social medias
* Blogs
* Communautés internet (Quora, etc.)
* et plus...

Pour ces campagnes, AppsFlyer utilise des <Anchor target="_blank" href="/marketers/fr/docs/onelink-guide">liens personnalisés OneLink</Anchor>. Les liens personnalisés OneLink redirigent les utilisateurs en fonction de leur appareil vers la bonne app store, directement dans l'app, ou vers une URL/une page d'accueil.

**Pour changer vos liens pour d'autres vendeurs en AppsFlyer OneLinks :**

* Contactez votre CSM, qui vous aidera à migrer en bloc tous vos liens.

</Accordion>

<div id="skan" />

<Accordion title="SKAN">

Pour l'attribution SKAdNetwork (SKAN), vous ne pouvez mettre la valeur de conversion à jour via le SDK qu'une seule fois. Autrement, les données SKAN perdent toute signification. Par conséquent, assurez-vous qu'après la migration, seul le SDK AppsFlyer met à jour la valeur de conversion SKAN.

<Anchor target="_blank" href="/marketers/fr/docs/skan-conversion-studio">Découvrez comment configurer la valeur de conversion SKAN dans AppsFlyer.</Anchor>

</Accordion>

<div id="data-report-setup" />

### Configuration du rapport de données

<div id="adapt-and-map-report-structures" />

<Accordion title="Adapter et mapper les structures des rapports">

Avant la migration, vos systèmes stockent les données d'attribution de votre fournisseur actuel selon les structures de reporting, les champs et les paramètres que vous avez définis avec lui. Pour qu'AppsFlyer puisse rapporter correctement les données, vous devez mapper et adapter vos structures de rapport actuelles à la structure de rapport, aux champs et aux paramètres d'AppsFlyer.

**Pour adapter/mapper les structures de vos rapports :**

* Contactez votre CSM AppsFlyer pour obtenir de l'aide pour adapter/migrer rapidement vos structures de données de rapport d'Adjust, Branch/Tune ou Kochava vers AppsFlyer.

</Accordion>

<div id="prepare-report-methods" />

<Accordion title="Préparer les méthodes de rapport">

Vous pouvez obtenir les données <Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-apis">brutes</Anchor> et <Anchor target="_blank" href="/marketers/fr/docs/analytics-and-aggregate-reporting-apis">agrégées</Anchor> du rapport auprès d'AppsFlyer de différentes manières. Familiarisez-vous avec ces méthodes et configurez celles qui vous conviennent.

Les méthodes de reporting comprennent :

* Exporter CSV
* API push
* API pull
* Data Locker

</Accordion>

<div data-zendesk-anchors="overview=pr%C3%A9sentation 01H8EDSTP8N4GZJQ5J609C3DHM=pr%C3%A9sentation 01H8EDZ8C5F06701DKT71D8T5P=remarque tasks=op%C3%A9rations-%C3%A0-effectuer 01H8EDSTP8YGDZBPEY1976JP8C=op%C3%A9rations-%C3%A0-effectuer scope-of-work=mise-en-application 01H8EDSTP8HGCVHYX49GQQEHBB=mise-en-application sdk-integration=int%C3%A9gration-sdk h_01F0RDXJ4F34DDKRFV5G6WZQX0=int%C3%A9gration-sdk 01H8EDSTP97C85X2E9EKBSVFQJ=sdk-integration::c763138b device-migration%E2%80%94optional=migration-dappareil-facultatif h_01F0RDXVSQ13R9Q2KT7PK1KSCQ=migration-dappareil-facultatif 01H8EDSTP9NDF6611MVEMWQSMZ=about-device-migration 01H8EDSTP93QJA4XZB6TDWWH1V=exemple 01H8EDSTP9M2MDMGZ8QBQGPM6S=how-to-migrate-devices h_01F0RPWKQ4B0T1TXRGPVTYPPFB=attributed-migration attributed-device-migration-csv-structure=structure-csv-de-migration-de-lappareil-attribu%C3%A9 01H8EDSTP9HABKEZJXMB84CDDE=structure-csv-de-migration-de-lappareil-attribu%C3%A9 h_01F0RPX3SJ391M8SPNNN50DDA8=nonattributed-migration nonattributed-device-migration-csv-file-structure=structure-de-fichier-csv-pour-la-migration-des-dispositifs-non-attribu%C3%A9s 01H8EDSTP9AFDMQS6BPQJY19ZH=structure-de-fichier-csv-pour-la-migration-des-dispositifs-non-attribu%C3%A9s campaign-migration=migration-de-campagne h_01F0RDY9WPSBZVP3B7XN3ZEJKK=migration-de-campagne 01H8EDSTP94KSE1J4J5B7HX96Z=srns 01H8EDSTP9ZGMHSM44BWGF1FJN=remarque-1 01H8EDSTP981XVWVM2NE0A45RM=nonsrn-ad-networks 01H8EDSTP9XNJA80Z5XR7WR9QN=owned-media 01H8EDSTP9Q8JAPNXSQWSHSK32=skan data-report-setup=configuration-du-rapport-de-donn%C3%A9es h_01F0RDYKYHAEZ65GZBZ3MWTB5Z=configuration-du-rapport-de-donn%C3%A9es 01H8EDSTP91E934EDXTPXW2ARJ=adapt-and-map-report-structures 01H8EDSTPAF8H5ESHDVK42M0RB=prepare-report-methods" />
