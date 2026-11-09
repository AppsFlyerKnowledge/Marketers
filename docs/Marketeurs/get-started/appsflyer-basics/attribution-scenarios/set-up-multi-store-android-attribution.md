---
title: "Mise en place de l'attribution mutli-stores Android\_ "
metadata:
  keywords:
    - Android
    - Google
    - Google Play
    - Add App
    - amazon
    - Advertisers
    - Agencies
    - baidu
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2015-12-24T10:48:17Z'
  edited_at: '2023-07-30T12:49:34Z'
  id: 207447023
  locale: fr
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/fr/articles/207447023
---
> **En bref :** attribuez vos apps dans plusieurs boutiques Android et consultez les données dans un tableau de bord des apps unique, ou dans un tableau de bord des apps par boutique.

<div id="multi-store-android-attribution" />

## Attribution mutli-stores Android

AppsFlyer attribue les apps, quel que soit l'app store.  C'est-à-dire le store Google Play et les stores Android tiers comme Amazon, Opera, GetJar, Baidu et Huawei. (En d'autres termes les stores hors-marché ou autres app store Android). Les propriétaires d'app qui commercialisent une app via plusieurs stores peuvent choisir entre un **tableau de bord** **unique** avec les données de tous les stores, ou bien un **tableau de bord pour chaque store**.

> 📘 **Note**
>
> * L'attribution Android d'AppsFlyer prend en charge tous les types d'identifiant d'appareil, y compris le GAID et <Anchor target="_blank" href="/marketers/fr/docs/android-oaid-implementation-in-the-sdk">OAID</Anchor>.
> * Pour les apps commercialisées en Chine, veuillez consulter <Anchor target="_blank" href="/marketers/fr/docs/measure-attribution-in-the-chinese-domestic-market">Attribution des apps Android sur le marché intérieur chinois</Anchor>

<Image align="center" alt="DashboardType_us-en-new.jpg" src="https://files.readme.io/10fdd08c4e57f799756f46922b5f8dc45c67f7550f9105e65076652f459c98f7-9545756936593.jpg" />

<div id="single-dashboard-vs-dashboard-per-store" />

### Tableau de bord unique et tableau de bord par store

* **Tableau de bord unique** : un tableau de bord qui regroupe les données de tous les stores, y compris le Google Play Store
* **Tableau de bord par store :** tableaux de bord multiples (chaque store a son propre tableau de bord). Ce qui veut dire que vous avez autant de tableaux de bord que de stores proposant l'app.

<table><thead><tr><th> </th><th><p>Tableau de bord unique<br/> [Recommandé]</p></th><th> Tableau de bord par store</th></tr></thead><tbody><tr><td><span id="android-package-name"></span>Nom du package Android</td><td colspan="2">Utilisez le même nom de package (identique) quelle que soit l'option choisie. </td></tr><tr><td><span id="channel-name"></span>Nom du canal</td><td>Rien à paramétrer</td><td><ul><li><span>Lorsque vous ajoutez l'app dans le tableau de bord AppsFlyer en utilisant l'option <strong>APK Android hors-store</strong> , vous devez paramétrer le canal.</span></li><li><span>Le canal identifie le store. </span></li><li>La combinaison entre le nom du package Android et le canal permet d'identifier de manière unique chaque tableau de bord AppsFlyer.</li><li>Exemple : le nom du package Android est com.abc.def et le canal est xyz_device_store. L'identifiant unique du tableau de bord sera com.abc.def-xyz_device_store.</li><li>Si l'APK a un paramètre de canal mais qu'il n'y a pas d'app avec ce paramètre, le trafic est attribué à l'app par défaut, c'est-à-dire l'app avec un paramètre de canal non rempli, c'est-à-dire Google Play Store.</li></ul></td></tr><tr><td><span id="populating-the-install_app_store-field"></span>Remplissage du champ install_app_store</td><td><ul><li>Identifie de manière unique le store qui fournit l'app par téléchargement.</li><li>Dans le cas du Google Play Store, ce champ reste vide. </li><li>Le nom du store est défini dans le <a href="./set-up-multi-store-android-attribution#single-dashboard-apk-preparation">manifeste / l'APK.</a> </li></ul></td><td><p>S/O</p></td></tr><tr><td><span id="onelink-template"></span><a href="./create-a-onelink-template#procédures" target="_blank">Template OneLink</a></td><td>Cette méthode est recommandée si vous travaillez avec OneLink. </td><td>N/A </td></tr><tr><td><span id="measurementattribution-links"></span>Liens de mesures / d'attribution </td><td><ul><li>Les liens sont les mêmes quel que soit le store.</li><li>Pour rediriger vers le bon store, utilisez <a href="./set-up-multi-store-android-attribution#single-dashboard-attribution-links">&amp;af_r</a> pour définir l'URL de redirection</li></ul></td><td><ul><li>Un lien unique est requis pour chaque store.</li><li>Vous pouvez les créer sur la page <strong>Integrations actives</strong>.</li><li>L'ID d'app résulte de l'assemblage entre le nom du canal et le nom du package Android. Ex : com.abc.def-def_store.<br/>Les liens d'attribution seront donc différents.</li></ul></td></tr><tr><td><span id="reporting-options-available-having-install_app_store-field"></span>Options de reporting disponibles avec le champ install_app_store</td><td><p>Les rapports de cohortes et de données brutes comprennent ce champ.  Contactez votre CSM pour lui demander d'ajouter le flag de fonctionnalité SFDC requis. </p></td><td>N/A </td></tr><tr><td><span id="considerations"></span><p>Attention</p></td><td><ul><li>Exactitude des attributions : les réinstallations de différents stores ne gonflent pas le nombre d'installations.</li><li><span>Les installations organiques afficheront l'ensemble des installations organiques des APK de tous les stores sur un même tableau de bord.</span></li><li><span>Les options de reporting, ventilées par store, sont actuellement limitées à la cohorte et aux données brutes.</span></li></ul></td><td><ul><li>Exactitude des attributions : les réinstallations sont comptées, ce qui entraîne une attribution moins précise.</li><li> <span>Consultez </span><span>les installations organiques</span><span> et </span><span>non organiques</span><span> ainsi que les données d'évènements in-app pour chaque store (canal) sur les différents tableaux de bord d'app dans AppsFlyer.</span> </li><li><span>Utilisez le cohorte pour afficher les rapports combinés de tous les stores</span></li><li>Vérifiez que les partenaires avec qui vous travaillez sont <strong>actifs</strong> (l'option <a href="./partner-activation-deactivation" target="_blank">Activer le partenaire</a> est enclenchée) dans <strong>tous les tableaux de bord</strong>.  cela vous permettra <span>d'éviter les différences de résultat (plus fréquentes lors de la comparaison des données avec les SRN).</span><span></span> </li></ul></td></tr></tbody></table>

<div id="tasks" />

<div id="before-you-begin" />

<div id="set-up-tasks" />

## Opérations de mise en place

La procédure suivante indique les activités requises pour mettre en place l'option souhaitée. Les opérations sont réparties entre le marketeur et le développeur.

Pour l'option Tableau de bord par store, répétez les opérations pour chaque store.

Avant de commencer :

* Convenez d'un type de dénomination pour le canal et les paramètres install\_app\_store.
* Utilisez le tableau de dénomination suivant pour unifier les canaux et les stores.
* Le tableau permet au développeur de préparer les APK.

<table><thead><tr><th>Paramètre</th><th><p>Instruction</p></th><th><p>Tableau de bord unique<br/> [Recommandé]</p></th><th>Tableau de bord par store</th></tr></thead><tbody><tr><td>Nom du package Android</td><td>Le nom de package identique pour toutes les options du tableau de bord</td><td colspan="2">Si l'app se trouve déjà dans le Google Play Store, utilisez le nom du package existant. Exemple : comb.abc.def</td></tr><tr><td>Nom du canal</td><td>Une valeur unique pour chaque store.</td><td><p>Non défini. Ne pas remplir. </p></td><td><p>Unique pour chaque store. Définissez la valeur dans l'APK unique préparé pour le store et lors de l'ajout de l'app dans AppsFlyer. </p><p>Ne définissez pas de canal pour l'APK du Google Play Store. </p></td></tr><tr><td>App store d'installation AF_STORE</td><td>Une valeur unique qui identifie le store</td><td><p><span>Unique pour chaque store. Défini dans l'APK via le manifeste. Chaque store a son propre APK. </span></p></td><td> Non défini</td></tr></tbody></table>

Opérations à effectuer

| Étape | Responsable | Tableau de bord unique | Tableau de bord par store |
| --- | --- | --- | --- |
| 1 | Développeur | [Préparation de l'APK](/docs/set-up-multi-store-android-attribution#single-dashboard-apk-preparation) | [Préparation de l'APK](/docs/set-up-multi-store-android-attribution#dashboard-per-store-apk-preparation) |
| 2 | Marketeur | Aucune action requise. On part du principe que l'app est déjà active dans AppsFlyer. | [Ajout de l'app](/docs/set-up-multi-store-android-attribution#dashboard-per-store-adding-the-app) dans AppsFlyer. |
| 3 | Marketeur | [Préparation des liens d'attribution](/docs/set-up-multi-store-android-attribution#single-dashboard-attribution-links) | Préparation des liens d'attribution en ajoutant l'ID de l'app au nom du canal. À effectuer sur la page des **Intégrations actives** en suivant la procédure habituelle. |
| 4 | Développeur et marketeur | [Test](/docs/set-up-multi-store-android-attribution#testing-both-dashboard-options) | [Test](/docs/set-up-multi-store-android-attribution#testing-both-dashboard-options) |

<div id="note-1" />

<div id="procedures" />

## Procédures

<div id="single-dashboard-apk-preparation" />

<Accordion title="Tableau de bord unique — préparation de l'APK">

Le nom du package Android détermine quel tableau de bord contiendra les données d'attribution. Dans la méthode du tableau de bord unique, tous les stores ont le même nom de package Android. Le principe de paramètre de canal ne s'applique pas dans ce cas.

L'identification du store de téléchargement se fait grâce au jeu de paramètres AF\_STORE défini dans le SDK, comme expliqué dans ce chapitre.  Le paramètre AF\_STORE n'est pas sensible à la casse. Par exemple : ABC, abc, Abc.

**Pour préparer l'APK :**

1. Créez une copie de la version de votre app. **Remarque** : ne changez pas le nom du package Android.
2. Pour identifier le store individuel, utilisez l'une des méthodes suivantes :
   * **Méthode via manifeste :** ajoutez ce qui suit dans la balise `<application>` du fichier AndroidManifest.xml pour identifier le store. Réglez le paramètre AF\_STORE sur le nom de l'app store.

     ```xml
     <application>  
     <meta-data android:name="AF_STORE" android:value="enter_store_name_here">  
     </application>
     ```

     **--OU BIEN--**
   * **Méthode API :** préparer un APK séparé pour chaque app store alternatif. Appelez l'API setOutOfStore pour définir la valeur AF\_STORE. Définissez une valeur unique par store.

     ```java
     AppsFlyerLib.getInstance().setOutOfStore("enter_store_name_here")
     ```

La valeur définie ici apparaît dans le champ install\_app\_store des données brutes d'AppsFlyer. Ce champ est disponible dans :

* Vue d'ensemble du tableau de bord
* Tableau de bord des cohortes
* <Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">Les rapports de données brutes</Anchor> (les rapports de données brutes sont une fonctionnalité premium AppsFlyer)

</Accordion>

<div id="single-dashboard-attribution-links" />

<Accordion title="Tableau de bord unique — liens d'attribution">

1. Allez dans **Configuration** > **Integrations actives,** et choisissez le réseau publicitaire.
2. Dans l'onglet **Lien d'attribution**, réglez le paramètre **URL hors store**. Cette action renseigne la macro `af_r` du lien d'attribution pour rediriger les utilisateurs vers la page d'app store qui convient. Par exemple, `&af_r=http://www.destinationurl.com` L'URL par défaut est définie dans la page <Anchor target="_blank" href="/marketers/fr/docs/app-settings">Paramètres de l'app</Anchor>. Si l'option n'est pas disponible sur la page Paramètres de l'app, demandez à votre CSM de l'activer pour vous.
3. Remplissez la macro af\_r avec l'URL de la page d'accueil du magasin.
4. Définissez les <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#paramètres-du-lien-dattribution">paramètres de lien d'attribution</Anchor> supplémentaires.
5. Les sources média hors store **utilisent la correspondance d'ID pour l'attribution**, et la <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-attribution-model#probabilistic-modeling">modélisation probabiliste</Anchor> AppsFlyer est utilisée en solution de secours.
6. Ajoutez un ou plusieurs paramètres d'identifiant utilisateur à l'URL du lien :
   * android\_id
   * advertising\_id
   * OAID
7. Copiez le lien d'attribution et transmettez-le au partenaire du ad network.

</Accordion>

<div id="dashboard-per-store-apk-preparation" />

<Accordion title="Tableau de bord par store — Préparation APK">

Le nom du package Android combiné à l'ensemble des paramètres du canal définis dans le manifeste détermine quel tableau de bord de store contiendra les données d'attribution.

**Pour préparer un APK/manifeste propre à chaque store :**

* Ajoutez ce qui suit dans la balise `<application>` du fichier AndroidManifest.xml pour identifier le store. Réglez le paramètre CHANNEL sur le nom de l'app store.

  ```xml
  <application>
       ...
       <meta-data android:name="CHANNEL" android:value="enter_store_name_here"/>
       ...
  </application>
  ```

  **Remarque :** les paramètres sont sensibles à la casse.

</Accordion>

<div id="dashboard-per-store-adding-the-app" />

<Accordion title="Tableau de bord par store — ajout de l'app">

Ajout d'un tableau de bord (app) qui sera identifié par l'assemblage du nom du package Android et du canal définis dans l'APK/le manifeste. Exemple : le nom du package Android est com.monapp et le nom du canal est abcstore. L'identifiant unique du tableau de bord sera com.monapp—abcstore.

**Pour ajouter un tableau de bord par store dans AppsFlyer** :

1. Ouvrez **Mes apps**, puis cliquez sur **Ajouter une app**.
2. Dans **store tierce, sélectionnez Android.**
3. Complétez les éléments suivants :
   * **Nom du package Android :** le nom du package tel qu'il apparaît dans le package de l'app.
   * **Nom du canal :** identifiant unique (nom du store) pour différencier les tableaux de bord qui ont le même nom de package. Veillez à utiliser la même valeur dans l'APK préparé pour le store. **Remarque :** Pour le nom du canal, vous devez utiliser uniquement des lettres majuscules ou minuscules (a-z ou A-Z). Aucun autre caractère, de type trait d'union (-) ou tiret du bas (\_), n'est autorisé.
   * **URL de l'app :**
     * **URL de l'app :** contient l'adresse URL de téléchargement par défaut qui renseigne la macro af\_r dans les liens d'attribution. Saisissez l'URL où l'APK est hébergé, ou l'URL de sa page d'accueil.
     * Vous pouvez modifier ce paramètre pour chaque lien d'attribution lorsque vous les créez.
     * Si vous laissez ce champ vide, vous ne pourrez plus jamais définir de page par défaut.
4. Cliquez sur **Suivant**.
5. Suivez les instructions de l'interface pour finir d'ajouter l'application.

</Accordion>

<div id="testing-both-dashboard-options" />

<Accordion title="Tests — les deux options du tableau de bord">

<div id="non-organic-installs" />

#### **installations non organiques**

**Pour tester les installations non organiques :**

1. Utilisez un appareil Android sur lequel votre application n'est pas installée ou bien <Anchor target="_blank" href="/marketers/fr/docs/registering-test-devices">enregistrez l'appareil</Anchor>.
2. Générez un lien d'attribution de test à l'aide d'un lien <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">OneLink</Anchor>. Utilisez test comme nom de source média ("&pid=test").
3. Ajoutez un identifiant publicitaire à l'URL de clic, soit GAID, OAID ou Android ID.

   ```http
   http://app.appsflyer.com/com.greatapp?pid=test
   &af_r=http://www.destinationurl.com&advertising_id=b5a3-78d9b5-0f12345-xxxx
   ```

   Envoyez-vous le lien d'attribution via email et cliquez dessus. **Une fois redirigé, n'installez pas l'application depuis le store**. Au lieu de cela, installez la version bêta mise à jour de l'application avec le SDK d'attribution d'AppsFlyer intégré et lancez-la.

| Tableau de bord unique | Tableau de bord par store |
| --- | --- |
| <ol><li>Vérifiez le rapport des données brutes d'installation de votre app sur la page Données d'exportation.</li><li>Vous devriez voir s'afficher une conversion d'installation avec la source média test. Sous la colonne intitulée **Installer l'app store**, vous devriez voir le nom du store tel qu'il apparaît dans le fichier manifest.xml.</li><li>Vous pouvez également voir le paramètre "af\_installstore": "STORE\_NAME" dans les journaux de l'installation.</li></ol> | <ol><li>Rendez-vous sur le tableau de bord par app store concerné.</li><li>Vérifiez le rapport de données brutes des installations de l'app dans l'onglet Données d'exportation ou bien consultez la page de présentation de l'app.</li><li>Vous devriez voir une conversion d'installation avec la source média « test ».</li></ol> |

<div id="organic-installs" />

#### **Installations organiques**

**Pour tester les installations organiques :**

1. Utilisez un appareil Android sur lequel votre application n'est pas installée, ou bien un appareil <Anchor target="_blank" href="/marketers/fr/docs/registering-test-devices">enregistré</Anchor>.
2. Installez la dernière version bêta de l'app avec le SDK d'attribution d'AppsFlyer intégré, puis lancez-la.
3. Vérifiez les résultats :

<div id="expected-results" />

#### Résultats attendus

| Tableau de bord unique | Tableau de bord par store |
| --- | --- |
| Consultez la page de présentation pour vérifier la présence d'une nouvelle installation organique (sous la source média « organique »). Actuellement, avec la méthode d'app unique, il n'existe aucune indication sur l'origine des installations organiques. | <ol><li>Accédez au dashboard et à l'overview de l'application qui est spécifique au store testé</li><li>Vous devriez voir une conversion d'installation sous la source média « organique ».</li></ol> |

</Accordion>

<div id="3rd-party-raw-data" />

<div id="additional-features" />

## Fonctionnalités supplémentaires

<div id="migrating-from-dashboard-per-store-to-single-dashboard" />

<Accordion title="Migration du tableau de bord par store vers un tableau de bord unique">

**Pour passer d'un tableau de bord multiple à un tableau de bord unique** :

Préparez de nouveaux APK pour les stores en suivant les instructions pour tableau de bord unique détaillées dans cet article.

</Accordion>

<div id="driving-users-to-the-amazon-app-store-from-facebook" />

<Accordion title="Diriger les utilisateurs Facebook vers l'app store Amazon">

1. Configurez un lien URL vers l'app dans les paramètres Meta de votre app, au niveau de la section **Android**.
2. Connectez-vous à Meta en tant qu'admin de l'application, allez sur <Anchor target="_blank" href="https://developers.facebook.com/apps/">https://developers.facebook.com/apps/</Anchor>, et choisissez l'application.
3. Allez dans les Paramètres et trouvez vos paramètres Android ou, si vous n'avez pas encore configuré Android, ajoutez la plate-forme.
4. Remplissez les informations requises, y compris l'URL Amazon App Store spécifique de votre application.  

   <Image align="center" alt="outofstore_1.png" src="https://files.readme.io/1e8c365176ac9e0e55360a8a5db1dd549518e477f3fba43206491bcf9a3023da-115010742229.png" />
5. Dans le tableau de bord AppsFlyer, dans Intégrations actives, sélectionnez Meta ads puis entrez le même identifiant d'app Facebook que celui que vous utilisez pour enregistrer les Meta ads d'installations mobile in-store dans AppsFlyer.

</Accordion>

<div id="getting-the-data-appsflyer-reports" />

<Accordion title="Obtenir les données - Autres méthodes de reporting AppsFlyer">

En plus du tableau du bord général, vous pouvez utiliser les méthodes de reporting suivantes dans AppsFlyer.

* Cohorte :
  * Combinez plusieurs tableaux de bord (apps) en un seul rapport
  * Observez les performances de chaque tableau de bord en les regroupant par *install\_app\_store*
* Pull API (pour app unique) : l'<Anchor target="_blank" href="/marketers/fr/docs/pull-api-aggregate-data">API</Anchor> les données brutes d'installation ne contiennent pas **l'app store d'installation** par défaut. Pour inclure la colonne, ajoutez ce qui suit à l'appel d'API Pull : `&additional_fields=install_app_store`
* Tableau de bord personnalisé (pour apps multiples) : si vous utilisez la méthode des tableaux de bord multiple, servez-vous du <Anchor target="_blank" href="/marketers/fr/docs/custom-dashboards">tableau de bord personnalisé</Anchor> pour rassembler les données de performance de différentes apps au même endroit.

</Accordion>

<div id="referrer-implementation-thirdparty-android-app-stores" />

<Accordion title="Implémentation du référent—app stores Android tierces">

* L'attribution des référents est prise en charge en fonction de Google Play et des stores tierces répertoriées ici.
* Pour la plupart des app stores tiers, aucun autre paramètre ni configuration n'est nécessaire. Pour Xiaomi, une dépendance supplémentaire doit être configurée. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk#xiaomi-getapps-store-referrer">En savoir plus</Anchor>
* L'attribution par référent de store tierce est signalée dans les rapports de données brutes comme suit :
  * Type de correspondance : le nom de l'app store tierce attribuée. Exemple : huawei\_referrer.
  * Contributeur : si l'utilisateur s'est engagé auprès de plusieurs app stores avant d'installer l'app, AppsFlyer considère ces engagements comme des contributeurs. L'installation est accordée à l'engagement du dernier clic. Exemple :
    * Un utilisateur clique sur une annonce diffusée par Google et est redirigé vers le Play Store. L'utilisateur ne télécharge pas l'app.
    * L'utilisateur clique sur une autre publicité et est redirigé vers le Samsung Galaxy Store. L'utilisateur télécharge et installe l'app.
    * L'attribution est attribuée au réseau publicitaire qui a redirigé l'utilisateur vers la boutique Samsung Galaxy ; Google est reconnu comme contributeur.

Stores Android tiers ayant des intégrations d'attribution par référent avec AppsFlyer

| App store tierce | À compter de | Version du SDK |
| --- | --- | --- |
| <span id="huawei-app-store"></span>App store Huawei | Juillet 2020 | 5.4.6 et +, 6.1.1 et + |
| <span id="samsung-galaxy-store"></span>Store Samsung Galaxy | Décembre 2020 | 6.1.1 et + |
| <span id="xiaomi-getapps-store"></span>Xiaomi GetApps Store | Septembre 2022 | 6.9.0 + |

<div id="troubleshooting" />

<Accordion title="Dépannage">

<div id="installs-attributed-to-the-default-app" />

### Installations attribuées à l'app par défaut

Si vous créez un APK d'app avec un paramètre de canal mais que vous ne créez pas de tableau de bord pour celui-ci dans le compte AppsFlyer : les installations seront attribuées à l'app par défaut, généralement l'app Google Play Store de votre compte. S'il n'existe pas d'app par défaut, aucune donnée n'est enregistrée pour l'app.

</Accordion>

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Particularités et limites">

| Particularité | Remarques |
| --- | --- |
| Redirection OneLink vers plusieurs app stores | Plusieurs app stores peuvent être définis dans le <Anchor target="_blank" href="/marketers/fr/docs/create-a-onelink-template#procédures">template OneLink</Anchor> à la condition que le nom du package d'app soit le même pour tous les app stores. |
| App store d'installation | Ce paramètre n'est pas disponible pour les agences ou les réseaux publicitaires. |

</Accordion>

<div data-zendesk-anchors="multistore-android-attribution=attribution-mutli-stores-android single-dashboard-vs-dashboard-per-store=tableau-de-bord-unique-et-tableau-de-bord-par-store reporting-options-available-having%C2%A0install_app_store-field=reporting-options-available-having-install_app_store-field setup-tasks=op%C3%A9rations-de-mise-en-place procedures=proc%C3%A9dures single-dashboard%E2%80%94apk-preparation=single-dashboard-apk-preparation single-dashboard%E2%80%94attribution-links=single-dashboard-attribution-links dashboard-per-store%E2%80%94apk-preparation=dashboard-per-store-apk-preparation dashboard-per-store%E2%80%94adding-the-app=dashboard-per-store-adding-the-app testing%E2%80%94both-dashboard-options=testing-both-dashboard-options nonorganic-installs=installations-non-organiques organic-installs=installations-organiques expected-results=r%C3%A9sultats-attendus additional-features=fonctionnalit%C3%A9s-suppl%C3%A9mentaires referrer-implementation%E2%80%94thirdparty-android-app-stores=referrer-implementation-thirdparty-android-app-stores installs-attributed-to-the-default-app=installations-attribu%C3%A9es-%C3%A0-lapp-par-d%C3%A9faut" />
