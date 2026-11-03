---
title: Studio de conversion SKAN
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-07-08T09:26:58Z'
  edited_at: '2023-10-26T14:42:38Z'
  id: 4403727223185
  locale: fr
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/fr/articles/4403727223185
---
> **En bref** : avec le Studio de Conversion SKAN, vous pouvez choisir quel type d'engagement utilisateur est mesuré au sein d'une app, et pour quelle durée. Mesurez le revenu, la conversion, l'engagement et la rétention pendant une période post-installation précise. En ajoutant la mesure SSOT (Single Source Of Truth), nous pouvons vous indiquer si un utilisateur a été attribué à la fois par AppsFlyer et par SKAN.

<Embed title="Studio de conversion SKAN 4 (verrouillage de fenêtre inclus)" typeOfEmbed="iframe" url="https://player.vimeo.com/video/810457121?h=a3acc3ee41&amp;badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479" providerUrl="https://player.vimeo.com" />

## Studio de conversion SKAN : présentation

Dans le cadre du flux d'attribution SKAdNetwork (SKAN), un appareil iOS envoie des postbacks SKAN contenant la VC la plus récente à la fin de chaque fenêtre de mesure.

Pour SKAN 3 et -, un postback arrive après la fin de la fenêtre d'activité initiale. La fenêtre d'activité peut aller de 12 heures à 63 jours. La CV est limitée à 6 bits, ce qui signifie 64 valeurs possibles (0-63).

Pour SKAN 4, 3 postbacks arrivent à la fin de chacune des trois fenêtres, soit après les jours 2, 7 et 35. Pour :

* Fenêtre 1, la CV fin est limitée à 6 bits, ce qui signifie 64 valeurs possibles (0-63).
* Fenêtres 1-3, la CV approximative est limitée au résultat faible, moyen ou élevé. (Les fenêtres 2 et 3 n'ont pas de CV précises).

Ces restrictions au niveau des CV font que vous devrez probablement faire des choix sur comment utiliser ces 64 valeurs pour de CV précises, et ces 3 valeurs de CV approximatives.

Le Studio de Conversion offre une flexibilité maximale pour que chaque valeur de conversion soit pleinement mise à profit. Vous déterminez précisément les données de mesure qui doivent être encodées dans la CV, y compris l'activité et la durée de la mesure post-installation. Il existe plusieurs modes de mesure qui vous permettent de configurer les paramètres de votre CV.

| Type | Mode de mesure | Description | Fenêtre d'activité |
| --- | --- | --- | --- |
| Flexible | [SKAN 4.0](/docs/skan-conversion-studio#skan-4)<br /><br />[Bonnes pratiques] | Définir une combinaison de revenus, de conversions (événements in-app) et de mesures de l'engagement durant 3 fenêtres d'activité configurables.<br /><br />Les 3 fenêtres mesurent 3 périodes différentes, qui ne se chevauchent pas, et qui suivent l'installation. Autrement dit, la fenêtre 2 mesure les jours 3 à 7 après l'installation, et non les jours 0 à 7. | <ul><li>Fenêtre 1 : 1-2 jours</li><li>Fenêtre 2 : 3-7 jours</li><li>Fenêtre 3 : 8-35 jours</li></ul> |
| Flexible | Personnalisation | Définir une combinaison de revenus, de conversions (événements in-app) et de mesures d'engagement lors d'une fenêtre d'activité configurable. | 12-1512 h (la durée par défaut est de 72 heures, mais elle peut être prolongée) |
| Fixe | Revenu<br /><br />[Par défaut]<br /><br />[Ancienne version] | Mesurer les revenus à l'aide de l'une des plages suivantes :<ul><li>1 $-630 $ par tranches de 10 $</li><li>1 $ à 63 $ par tranches de 1 $</li><li>0,01 $ à 0,63 $ par tranches de 0,01 $.</li></ul> | 24 h |
| Fixe | Conversion<br /><br />[Ancienne version] | Sélectionnez 1 à 6 événements in-app. | 24 h |
| Fixe | Engagement<br /><br />[Ancienne version] | Nombre de fois qu'un utilisateur effectue un événement | 24 h |
| Flexible | <Anchor target="_blank" href="/marketers/fr/docs/skan-cv-decode-map-your-cv-to-events">Décryptage</Anchor> | <ul><li>Créez une valeur de conversion personnalisée pour le mappage d'événements et définissez-la dans l'app. Utiliser cette option s'il est impossible d'intégrer le SDK AppsFlyer dans votre app. Pour utiliser la fonction « Decode », accédez à **SKAN Conversion Studio**, cliquez sur Options (⋮) puis sélectionnez **Importer un fichier de mappage décryptage personnalisé**.</li></ul> | 12-1512 h (63 jours) |

**Conseil !** Faites des essais dans le Studio de Conversion. Dans AppsFlyer, ouvrez **Configuration** > **Studio de Conversion SKAN**.

<div id="measurement-principles-and-definitions" />

<Accordion title="Principes des mesures et définitions">

**Définitions**

* **Fenêtre de mesure SKAN**: valable pour SKAN 4 et +. Il y a 3 périodes (fenêtres) pendant lesquelles l'activité post-installation des utilisateurs est mesurée :
  * Fenêtre 1 : 1-2 jours
  * Fenêtre 2 : 3-7 jours
  * Fenêtre 3 : 8-35 jours
  * Les 3 fenêtres mesurent 3 périodes différentes, qui ne se chevauchent pas, et qui suivent l'installation. Autrement dit, la fenêtre 2 mesure les jours 3 à 7 après l'installation, et non les jours 0 à 7.
* **Fenêtre d'activité** : valable pour SKAN 3 et -. A une durée définie par défaut sur 24 heures, le début correspond à la première ouverture de l'app. Si vous utilisez SKAN 4+ mais que les appareils des utilisateurs ou les réseaux publicitaires ne prennent pas en charge SKAN 4, la fenêtre d'activité est alors de 48 heures.
* **Valeur de conversion (CV)** : mesure de la qualité de l'utilisateur transmise dans les postbacks envoyés par iOS à la fin des fenêtres de mesure pour SKAN 4 (ou pour SKAN 3 et -, à la fin de la fenêtre d'activité). Le SDK AppsFlyer définit les CV pour vous. Si vous souhaitez régler vous-même la CV, utilisez l'option <Anchor target="_blank" href="/marketers/fr/docs/skan-cv-decode-map-your-cv-to-events">*Decode*</Anchor> pour importer votre fichier de mappage CV.
  * Pour SKAN 4+, il existe des valeurs de conversion précises ou approximatives.
* **Capacité de la valeur de conversion :** le nombre VC nécessaire pour mapper votre paramètre. Plus vous sélectionnez de composants et d'éléments de mesure, plus la capacité de la valeur de conversion est importante. Chaque période ou paramètre sélectionné consomme une capacité de valeur de conversion (de plus chaque nouvelle unité de paramètre ajoutée dans un composant la consomme de manière exponentielle !) [Exemples d'utilisation optimale de VC.](/docs/skan-conversion-studio#maximized-custom-cv-examples)
* **Single Source of Truth (SSOT) :** <Anchor target="_blank" href="/marketers/fr/docs/single-source-of-truth-ssot-guide-for-ios-attribution">le procédé qui permet d'indiquer</Anchor> si l'utilisateur a été attribué à la fois par SKAN et par une autre méthode de matching. L'indicateur permet de retirer les données d'installation qui sont en double dans les données brutes SKAN, et donc d'obtenir des résultats de performance fidèles à la réalité.
* **Composants de la mesure**:  
  * **Revenus :** mesure les revenus générés
  * **Évènement in-app** : pour mesurer la conversion (le nombre d'utilisateurs uniques qui ont réalisé un événement), l'engagement (le nombre de fois où un événement a été réalisé), ou même les deux.
  * **Tunnel :** pour mesurer le nombre d'événements in-app après un enchainement d'événements au sein d'un entonnoir. On considère que l'utilisateur qui produit un événement dans l'entonnoir a forcément effectué tous les événements qui le précédent.
  * **Priorité** : un composant qui contient des revenus, un événement in-app, ou les deux.
  * **Predict (Prévisions) :**  utilise des algorithmes avancés de machine learning pour fournir des estimations précises, basées sur la LTV, des performances de la campagne. Les KPI estimés au niveau utilisateur (y compris l'estimation des revenus et de la rétention) sont codés et transmis à SKAN sous la forme d’une valeur de conversion unique, que SKAN signale ensuite sous forme de publication, avec l’ID de campagne et la source d’attribution.

**Fondamentaux**

* **![Admin.png](https://files.readme.io/74a71649d541921d2b61425323cc4cf5b669cd4d5665294d0813a3e9230bd11d-4405725144977.png) Admin exclusivement** : seul l'admin est habilité à enregistrer les paramètres du Studio de conversion. Les utilisateurs du compte peuvent quant à eux consulter les paramètres.
* À tout moment, un seul mode peut être actif.
* Pour un mode donné, AppsFlyer mappe les combinaisons définies par vos paramètres vis-à-vis des VC. Vous pouvez [consulter et télécharger le tableau de mappage](/docs/skan-conversion-studio#view-cv-mapping).
* Dans l'application, AppsFlyer définit la VC après chaque action mesurable de l'utilisateur, et ce à l'aide du mode de mesure qui s'applique lors du premier lancement de l'app par un utilisateur.
* iOS tient compte de  <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_postbacks_in_multiple_conversion_windows">l'anonymat des foules d'Apple</Anchor> avant de remplir la CV dans le postback.
* Les actions de l'utilisateur qui ont lieu après la fin d'une fenêtre ne sont pas prises en compte.
* Tableau de bord et rapports SKAN :
  * L'affichage et les mesures du tableau de bord SKAN varient en fonction du mode actif et de la configuration.
  * L'affichage est mis à jour quotidiennement en fonction du mode qui est actif à minuit UTC. La mise à jour est disponible à partir de 05:00 UTC.
  * Dans SKAN 4, en mode *Custom* et *Decode*, les données organiques des événements in-app ne sont pas disponibles.

#### **Principes de base du S2S**

Les actions mesurables peuvent être transmises via l'API [server-to-server (S2S)](/docs/skan-conversion-studio#report-events-by-servertoserver-api). En fonction des modes, veuillez noter ce qui suit :

* SKAN 4 et *Custom* : S2S est toujours activé.
* Décodage : le S2S n'est pas pris en charge et n'est donc pas disponible. AppsFlyer ne définit pas de VC pour ce mode.
* Revenus, conversion et modes d'engagement : vous devez forcément activer l'[enregistrement des événements S2S](/docs/skan-conversion-studio#report-events-by-servertoserver-api) avant d'envoyer les événements.

</Accordion>

## Configuration des valeurs de conversion dans SKAN Conversion Studio

Plusieurs modes sont disponibles dans SKAN Conversion Studio pour définir les valeurs de conversion :

* SKAN 4 : utilise différents composants de mesure (comme les revenus et événements in-app, la priorité, le SSOT) pour définir ce qui est mesuré durant chacune des trois fenêtres de mesure.
* Personnalisé : utilise différents composants de mesure (comme les revenus et événements in-app, la priorité, le SSOT) pour définir ce qui est mesuré durant la fenêtre d'activité.
* Modes fixes : mesure la valeur de l'utilisateur avec l'une des mesures suivantes :
  * Revenu
  * Conversion
  * Engagement

Pour en savoir plus sur les différents modes de mesure, consultez les sections suivantes.

> 🚧 **Important !**
>
> La définition des valeurs de conversion dans SKAN Conversion Studio doit être effectuée par un admin ou un utilisateur de compte disposant des autorisations **de gestion** dans **SKAN Conversion Studio**.
>
> **Pour afficher ou modifier les autorisations des utilisateurs** :
>
> 1. Dans AppsFlyer, en haut à droite de l'écran, cliquez sur votre adresse e-mail.
> 2. Sélectionnez **Gestion des utilisateurs** > Sélectionnez l'utilisateur.
> 3. Si ce n'est déjà le cas, accordez à l'utilisateur les autorisations de **gestion** dans **SKAN Conversion Studio**. Pour en savoir plus sur les autorisations, cf <Anchor target="_blank" href="/marketers/fr/docs/user-management">Gestion des utilisateurs</Anchor>.

<div id="skan-4" />

<Accordion title="SKAN 4">

Dans SKAN 4, vous utilisez différents composants de mesure tels que les revenus, les événements in-app, la priorité et la SSOT pour définir les éléments mesurés durant chacune des trois fenêtres de mesure. Ensemble, les composants créent votre mode de mesure SKAN 4.

Si vous effectuez une mise à niveau vers SKAN 4 à partir d'un mode SKAN précédent, votre mappage de schéma actuel est reporté pour la configuration fine de la fenêtre 1. AppsFlyer mappe automatiquement pour vous les valeurs élargies pour les fenêtres 1-3.

Pour définir manuellement SKAN 4, tentez différentes options. En fonction des modifications, la jauge de **capacité de la valeur de conversion** évolue. Affinez les paramètres jusqu'à obtenir les données qui vous intéressent le plus, mais sans dépasser la capacité. Cf [Calcul de la capacité de la valeur de conversion.](/docs/skan-conversion-studio#conversion-value-capacity-formula)

![CapacitCounter.png](https://files.readme.io/c976bbf52b8348ffa8de092f5f75eb66b137cc9fa63bc34d0b84e50fc7d112f7-4405725161233.png)

Remarque **: si vous passez à SKAN 4 à partir d'un mode SKAN précédent, votre mappage de schéma actuel est reporté pour les mesures précises et AppsFlyer mappe automatiquement les valeurs approximatives pour vous. Et si vous êtes nouveau sur SKAN, AppsFlyer fournit un mappage initial par défaut.**

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) Pour définir manuellement les valeurs de conversion dans Conversion Studio en utilisant le mode SKAN 4 :**

1. Dans le tableau de bord AppsFlyer, allez dans **Configurations** > **SKAN Conversion Studio.**
2. Cliquez sur les options (⋮) pour afficher le menu des options et assurez-vous que la mesure **SKAN** est activée. **Remarque** : si elle est désactivée, le SDK n'appellera pas les fonctions SKAdNetwork iOS de type *registerAppForAdNetworkAttribution* et *updateConversionValue.*
3. Sélectionnez le mode de mesure **SKAN 4.0**.
4. Cliquez sur **Continuer**.  
   Les paramètres de CV précise de la **fenêtre 1 (1-2 jours) précise** s'ouvrent.
5. [Optionnel] Activez **la SSOT (Single Source Of Truth)**.  
   Le mécanisme SSOT signale (et déduplique) les installations apportées par plus d'une méthode de correspondance d'attribution. <Anchor target="_blank" href="/marketers/fr/docs/single-source-of-truth-ssot-guide-for-ios-attribution">En savoir plus</Anchor>
6. Cliquez sur **+ Ajouter une mesure** pour ajouter différents [composants de mesure](/docs/skan-conversion-studio#composants-de-la-mesure).  
   Les sections suivantes décrivent les options et comosants de réglage. Utilisez-les comme référence pour tester les différents paramètres de mesure de SKAN :
   * Revenu
   * Évènement in-app
   * Tunnel
   * Priorité
   * Prévisions
7. Cliquez sur **Approximative** et reprenez les étapes 6 et 7 pour définir la CV approximative de la **fenêtre 1 (1-2 jours)**.   
   **Remarque** : 
   * Seuls les composants de mesure des revenus et des événements in-app sont disponibles.
   * La CV basse doit être une session utilisateur visant à garantir l'envoi du postback.
8. [Facultatif] Activez **Verrouiller la fenêtre** et définissez la condition (soit la durée soit la valeur de conversion approximative) pour que la fenêtre SKAN se verrouille avant la valeur par défaut. [En savoir plus](/docs/skan-conversion-studio#lock-window)
9. Cliquez sur **Fenêtre 2 (3-7 jours)** et reprenez les étapes 6 à 8 pour définir la CV de la fenêtre 2.   
   **Remarque** : 
   * Seuls les composants de mesure des revenus et des événements in-app sont disponibles.
   * [Recommandé] La CV faible devrait être une session utilisateur.
10. Cliquez sur **Fenêtre 3 (8-35 jours)** et répétez les étapes 6 à 8 pour définir la VC de la fenêtre 3.   
    **Remarque** :
    * Seuls les composants de mesure des revenus et des événements in-app sont disponibles.
    * [Recommandé] La CV faible devrait être une session utilisateur.
11. Cliquez sur ***Enregistrer***.
12. Vérifiez que les mappages de postback d'événements in-app de votre partenaire mappent bien les événements que vous avez configurés.

</Accordion>

<div id="custom" />

<Accordion title="Personnalisation">

En mode personnalisé, vous utilisez différents composants de mesure (comme les revenus et événements in-app, la priorité, le SSOT) pour définir d'une part ce qui doit être mesuré, et d'autre part la fenêtre d'activité visant à déterminer la durée et les intervalles de mesure. C'est l'ensemble de ces composants qui créent votre mode de mesure personnalisé.

Pour définir le mode Personnalisé, tentez différents réglages, en fonction des modifications la synthèse de la **capacité de la valeur de conversion** évolue. Affinez les paramètres jusqu'à obtenir les données qui vous intéressent le plus, mais sans dépasser la capacité. Cf [Calcul de la capacité de la valeur de conversion.](/docs/skan-conversion-studio#conversion-value-capacity-formula)

![CapacitCounter.png](https://files.readme.io/c976bbf52b8348ffa8de092f5f75eb66b137cc9fa63bc34d0b84e50fc7d112f7-4405725161233.png)

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) Pour définir manuellement les valeurs de conversion dans Conversion Studio en utilisant le mode personnalisé :**

1. Dans le tableau de bord AppsFlyer, allez dans **Configurations** > **SKAN Conversion Studio.**
2. Cliquez sur les options (⋮) pour afficher le menu des options et assurez-vous que la mesure **SKAN** est activée. **Attention !** Si elle est désactivée, le SDK n'appellera pas les fonctions SKAN iOS de type *registerAppForAdNetworkAttribution* et *updateConversionValue.*
3. Sélectionnez le mode de mesure **personnalisé** .
4. Cliquez sur **Continuer**.
5. [Optionnel] Activez **la SSOT (Single Source Of Truth)**.  
   Le mécanisme SSOT signale (et déduplique) les installations apportées par plus d'une méthode de correspondance d'attribution. <Anchor target="_blank" href="/marketers/fr/docs/single-source-of-truth-ssot-guide-for-ios-attribution">En savoir plus</Anchor>
6. Cliquez sur **+ Ajouter une mesure** pour ajouter différents composants de mesure.  
   Les sections suivantes détaillent les options de réglage et les composants. Utilisez-les comme guides lorsque vous expérimentez les différents paramètres de mesure de SKAN :
   * Revenu
   * Évènement in-app
   * Tunnel
   * Priorité
   * Prévisions
7. Définissez la durée de la fenêtre d'activité (entre 12 heures et 63 jours) pendant laquelle vous souhaitez mesurer l'activité des utilisateurs.La valeur par défaut de **Période d'activité** vous permet de définir une fenêtre allant de 24 à 72 heures. Le réglage par défaut de **Intervalle** vous permet de définir 12 ou 24 heures. Utilisez la **Fenêtre personnalisée** pour étendre la fenêtre d'activité jusqu'à 63 jours, et définir des intervalles plus longs.
8. Cliquez sur ***Enregistrer***.
9. Vérifiez que les mappages de postback d'événements in-app de votre partenaire mappent bien les événements que vous avez configurés.

</Accordion>

<div id="fixed-modes" />

<Accordion title="Modes fixes">

Les modes fixes vous permettent de mesurer la valeur utilisateur en utilisant l'une des mesures suivantes :

* * Revenu
  * Conversion
  * Engagement

Au fur et à mesure que vous modifiez les paramètres du mode, la synthèse **de la capacité des valeurs de conversion** se met à jour. Optimisez vos paramètres pour capturer les données les plus importantes, sans dépasser la capacité. Cf [Calcul de la capacité des valeurs de conversion.](/docs/skan-conversion-studio#conversion-value-capacity-formula)

![CapacitCounter.png](https://files.readme.io/c976bbf52b8348ffa8de092f5f75eb66b137cc9fa63bc34d0b84e50fc7d112f7-4405725161233.png)

**Important !**

* La mesure porte sur une fenêtre d'activité de 24 heures qui démarre dès la première ouverture de l'application.
* Si vous souhaitez envoyer des événements via le S2S, vous devez explicitement activer [SKAN S2S](/docs/skan-conversion-studio#report-events-by-servertoserver-api)

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) Pour définir manuellement les valeurs de conversion dans Conversion Studio en utilisant un mode fixe :**

1. Dans le tableau de bord AppsFlyer, allez dans **Configurations** > **SKAN Conversion Studio.**
2. Cliquez sur les options (⋮) pour afficher le menu des options puis :
   * Assurez-vous que la mesure **SKAN** est activée. **Attention !** En cas de désactivation, le SDK n'appellera pas les fonctions SKAdNetwork iOS de type *registerAppForAdNetworkAttribution* et *updateConversionValue.*
   * [Facultatif] [Activer l'envoi d'événements par S2S](/docs/skan-conversion-studio#report-events-by-servertoserver-api). Option disponible si le mode sélectionné est revenu, conversion ou engagement.
3. Sélectionnez un mode de mesure fixe.
4. Suivez les informations et les instructions du tableau suivant pour le mode de mesure fixe que vous avez choisi.
5. Cliquez sur **Enregistrer**.
6. Vérifiez que les mappages de postback d'événements in-app de votre partenaire mappent bien les événements que vous avez configurés.

#### Mesures en mode fixe

| Mode de mesure | Description |
| --- | --- |
| [Par défaut] Revenus | ![RevenueFixed.png](https://files.readme.io/ee0882a8b76e50c6fc0ce9bdb04934f3c22324bcaeb15181caf685b00c014a80-4406058625809.png)<br /><br />**Revenus générés durant la fenêtre d'activité de 24 heures**<br /><br />Sélectionnez un taux unité/USD parmi les suivants :<ul><li>0.01 $ pour mesurer jusqu'à 0.63$.</li><li>1$ pour mesurer jusqu'à 63$</li><li>10$ pour mesurer jusqu'à 630$</li></ul>AppsFlyer remplit automatiquement les 63 plages de mesure des revenus. `af_skad_revenue` devraient être mappé. Dans le tableau de bord, le revenu enregistré correspond au seuil maximum de la plage. Exemple, si la plage est comprise entre 60$ et 61$, le revenu enregistré est de 61$. Remarque ! Les revenus personnalisés utilisent une autre méthode de calcul pour définir le montant des revenus.<br /><br />**Métriques disponibles :**<ul><li>Revenu</li><li>ROI</li><li>ROAS</li><li>ARPU  : revenus/utilisateurs installant l'app</li><li>Taux de conversion des utilisateurs : utilisateurs effectuant un achat/installant l'app</li><li>eCPA</li></ul> |
| Conversion | ![mceclip0.png](https://files.readme.io/29535e45638cb2b1eecdf43e4fbee0fa52665c90aefe064caaaac9d0fc98472f-4406052008593.png)<br /><br />**Événements in-app effectués à une ou plusieurs reprises pendant la fenêtre d'activité de 24 heures**<br /><br />**Réglages** :<ul><li>Sélectionnez dans le menu déroulant 1 à 6 événements in-app à mesurer. Limitation : la liste est limitée aux 300 premiers événements sur les 30 derniers jours.</li><li>Dans le tableau de bord SKAdNetwork, sélectionnez un événement qui désignera l'événement de conversion.</li></ul>**Métriques par événement in-app :**<ul><li>Nombre d'utilisateurs effectuant un événement</li><li>Taux de conversion : utilisateurs effectuant l'événement de conversion/utilisateurs installant l'app</li><li>eCPA</li><li>Sessions (utilise l'événement *af\_app\_opened*)</li></ul>Exemple de comptage des utilisateurs :<ul><li>Inscription complète</li><li>A effectué un achat</li><li>A atteint un niveau de jeu</li></ul>**Clarification :** utilisez la mesure de conversion pour comptabiliser **si** un utilisateur a effectué un événement. Utilisez la mesure de l'engagement pour compter combien de fois un utilisateur effectue un événement. |
| Engagement | ![mceclip1.png](https://files.readme.io/51b38d6693e843f04fe7ce02706ae2959d88a047606b41cccad6ed09a46eea39-4406058637841.png)<br /><br />**Nombre de fois où l'utilisateur a réalisé un certain événement in-app au cours de la fenêtre d'activité SKAN**<br /><br />**Réglages :**<ul><li>Sélectionnez un événement in-app dans la liste déroulante.</li><li>La sélection in-app est également désignée comme l'événement de conversion.</li><li>Plage de valeurs : 0-63</li></ul>**Métriques de l'événement in-app** :<ul><li>Nombre d'utilisateurs effectuant l'événement</li><li>Nombre moyen d'événements par utilisateur</li><li>de l'installation à la première commande</li><li>eCPA</li><li>Sessions</li></ul>Exemples :<ul><li>Mesurez le nombre de fois :<ul><li>où un utilisateur a ouvert l'app</li><li>où un utilisateur a vu une publicité</li></ul></li></ul> |

</Accordion>

<div id="decode" />

<Accordion title="Décryptage">

Créez une valeur de conversion personnalisée pour le mappage d'événements et définissez-la dans l'app. Utiliser cette option s'il vous est impossible d'intégrer le SDK AppsFlyer dans votre app.

**Pour utiliser Decode** :

1. Dans le tableau de bord AppsFlyer, allez dans **Configurations** > **SKAN Conversion Studio.**
2. Cliquez sur les options (⋮) pour afficher le menu des options puis :
   * Assurez-vous que la mesure **SKAN** est activée. **Attention !** En cas de désactivation, le SDK n'appellera pas les fonctions SKAdNetwork iOS de type *registerAppForAdNetworkAttribution* et *updateConversionValue.*
   * Exportez votre fichier de mappage Décodage.
3. Cliquez sur **Enregistrer**.
4. Vérifiez que les mappages de postback d'événements in-app de votre partenaire mappent bien les événements que vous avez configurés.

</Accordion>

## Composants de la mesure

<div id="single-source-of-truth" />

<Accordion title="SSOT (Source Unique de Vérité)">

<table><tbody><tr><td colspan="2"><p><img alt="SSOTControl.png" src="https://files.readme.io/77570ca922d33a0ef3df4b5a42904452c07b9b472ea4c68c8390155ed2bc53ed-4458326657553.png"/></p><p>Le procédé <a href="./single-source-of-truth-ssot-guide-for-ios-attribution" target="_blank">Single Source of Truth (SSOT)</a> indique (et déduplique) les installations qui ont été rapportées par différents matchings d'attribution. C'est à dire SKAN plus une autre méthode d'attribution. L'indicateur est disponible dans les rapports de données brutes SKAN et sera probablement utilisé dans le calcul des mesures de la <a href="./single-source-of-truth-ssot-guide-for-ios-attribution#tableau-de-bord-général-fenêtre-ssot" target="_blank">fenêtre SSOT</a> du tableau de bord général.</p></td></tr><tr><td><p>Obligatoire</p></td><td>Non</td></tr><tr><td><p>Pluri-utilisation autorisée</p></td><td>Non</td></tr><tr><td><p>Options des paramètres</p></td><td><p>Lorsque SSOT est activé, la CV est reglée de manière à définir si un utilisateur est attribué à la fois par SKAN et par une autre méthode de correspondance. </p><p>Dans quel cadre l'indicateur SSOT est-il utilisé ?</p><ul><li>Vue d'ensemble du tableau de bord Vue SSOT AppsFlyer</li><li>Les rapports de données brutes SKAN contiennent le champ <em>af_attribution_flag</em>. Si la réponse est «true», l'utilisateur a été attribué à la fois par SKAN et par une autre méthode.</li><li>Rapports d'API d'attribution agrégée SKAN.</li></ul></td></tr></tbody></table>

</Accordion>

<div id="predict-component" />

<Accordion title="Composant de prévisions">

<table><tbody><tr><td colspan="2"><p><img alt="Predict-SKAN_Conversion_Studio__1_.png" src="https://support.appsflyer.com/hc/article_attachments/7742007538065"/></p></td></tr><tr><td><p>Obligatoire</p></td><td><p>Non</p></td></tr><tr><td><p>Pluri-utilisation autorisée</p></td><td><p>Non</p></td></tr><tr><td><p>Options des paramètres</p></td><td><ul><li><span>Lecture seule</span></li><li><span>La fenêtre d'activité est définie sur 24 heures</span></li><li><span>D'autres paramètres se basent sur les paramètres de Prévisions.</span></li></ul></td></tr><tr><td><p>Disponibilité</p></td><td><ul><li>Disponible pour les abonnés à Predict</li><li>Pour bénéficier de l’accès à Predict, contactez votre CSM</li></ul></td></tr></tbody></table>

</Accordion>

<div id="inapp-event-component" />

<Accordion title="Composant d'événement in-app">

<Table>
  <tbody>
    <tr>
      <td colSpan="2">
        ![ConversionStudioIn-app-event.png](https://files.readme.io/7b110093a72b13c0750ccb66da5efe737b8f83c0adcb95eb35185a4dc77bad6c-4406051824657.png)
      </td>
    </tr>
    <tr>
      <td>
        Obligatoire
      </td>
      <td>
        Non
      </td>
    </tr>
    <tr>
      <td>
        Pluri-utilisation autorisée
      </td>
      <td>
        Oui
      </td>
    </tr>
    <tr>
      <td>
        Options des paramètres
      </td>
      <td>
        Sélectionnez un événement in-app, puis configurez les périodes en fonction du type de mesure recherché :

        * **Conversion uniquement :** configurez une période comprise entre 0 et 1
        * **Engagement et conversion :** configurez plusieurs périodes avec les plages sélectionnées
      </td>
    </tr>
    <tr>
      <td>
        Périodes pour l'engagement
      </td>
      <td>
        Pour mesurer l'engagement, vous devez créer des périodes d'occurrence. Lorsque l'occurrence de l'événement d'engagement choisi est signalée se produit, SKAN l'associe à la période correspondant au nombre d'occurrences de l'événement.

        **Caractéristiques**

        * Chaque période contient une plage d'occurrences définie par les valeurs **from (de)**  et **to (à)**. La valeur la plus basse n'est pas comprise dans la plage, mais la valeur la plus haute oui. Exemple : 5–10 signifie strictement supérieur à 5, 10 compris.
        * La plage avec la valeur la plus basse commence toujours par 0 (mais 0 n'est pas compris).
        * Vous pouvez créer autant de plages que vous le souhaitez, mais n'oubliez pas que chaque plage influe sur la capacité de votre valeur de conversion.
        * Les plages doivent se suivre (sans espaces entre elles).

        **Mesurer l'engagement à l'aide des plages**

        * Lorsque l'occurrence d'un événement est rapportée, SKAN associe l'occurrence à la plage concernée. Les occurrences enregistrées sont calculées d'après la plage moyenne. La valeur est arrondie au nombre entier le plus proche. Exemple : 5.7 est arrondi à 6.
        * Si le nombre d'occurrences dépasse la plus haute valeur de la période la plus élevée, les occurrences sont comprises dans la période la plus élevée. Le nombre d'occurrences enregistré correspond à la valeur moyenne de la période la plus élevée. Le nombre réel d'occurrences est donc ignoré.
        * Dans les données brutes, le nombre réel d'occurrences et de plages est bien proposé.

        **Exemple :**

        Le schéma illustre les plages d'occurrence ci-dessous.

        Les plages d'occurrence définies sont le suivantes :

        * A : 0-5
        * B : 5-10
        * C : 10-20

        Le nombre d'occurrences est enregistré en fonction des plages suivantes :

        | Exemple | Nombre d'occurrences indiqué par le SDK | Plage associée | Nombre d'occurrences rapporté |
        | --- | --- | --- | --- |
        | 1 | 5 | A | 3 |
        | 2 | 6 | B | 8 |
        | 3 | 10 | B | 8 |
        | 4 | 125 | C | 15 |
      </td>
    </tr>
    <tr>
      <td>
        Limitation
      </td>
      <td>
        Un événement in-app ne peut être associé qu'une seule fois à ce composant.
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="revenue-component" />

<Accordion title="Composant du revenu">

<Table>
  <tbody>
    <tr>
      <td colSpan="2">
        ![ConversionStudioRevenue.png](https://files.readme.io/202c258f11cd93248f8aceff410126efc02ced11e9a9b159bac8ba81cbc8d9fe-4406075612305.png)
      </td>
    </tr>
    <tr>
      <td>
        Obligatoire
      </td>
      <td>
        Non
      </td>
    </tr>
    <tr>
      <td>
        Pluri-utilisation autorisée
      </td>
      <td>
        Oui, si vous utilisez la source de revenu des événements in-app.
      </td>
    </tr>
    <tr>
      <td>
        Options des paramètres
      </td>
      <td>
        Le revenu peut être enregistré pour un seul événement, ou vous pouvez associer chaque revenu à un flux précis selon les événements in-app sélectionnés.

        Parmi les différentes sources de revenu vous trouverez :

        * **Revenu total**
          * Tout revenu qui est enregistré par SKAN avec l'événement `af_skad_revenue`.  `af_skad_revenue` doit être mappé.
          * Le composant ne peut être inclus qu'une seule fois.
        * **Évènement in-app**
          * Le revenu rapporté selon le type est attribué à un événement in-app choisi et est enregistré via SKAN pour pour ce même événement in-app. L'événement doit être mappé ; `af_skad_revenue` ne doit pas être mappé.
          * Le composant peut être utilisé plusieurs fois.
          * Si vous signalez les revenus aux réseaux publicitaires via postback, vérifiez que le mappage de vos postbacks d'événements in-app incluent les événements de revenus in-app que vous avez définis.
      </td>
    </tr>
    <tr>
      <td>
        Périodes
      </td>
      <td>
        Pour mesurer les revenus, vous devez créer des plages de revenu. Lorsque les revenus sont rapportés, SKAN associe chaque revenu à la plage concernée.

        **Caractéristiques**

        * Chaque période contient une plage de revenus définie par les valeurs **from (de)** et **to (à)**. La valeur la plus basse n'est pas comprise dans la plage, mais la valeur la plus haute oui. Exemple : 5–10 signifie strictement supérieur à 5, 10 compris.
        * La plage avec la valeur la plus basse commence toujours par 0 (mais 0 n'est pas compris).
        * Vous pouvez créer autant de plages que vous le souhaitez, mais n'oubliez pas que chaque plage influe sur la capacité de votre valeur de conversion.
        * Les plages doivent se suivre (sans espaces entre elles).
        * Les montants sont en USD
        * Si vous lancez des campagnes sur Meta ads, vous devez avoir 4 plages au minimum.
        * Les valeurs de plage comportent 4 chiffres maximum après la virgule.

        **Enregistrer les revenus à l'aide des plages**

        * Lorsque les revenus sont rapportés, SKAN associe chaque revenu à la plage concernée. Le revenu enregistré correspond à la plus haute valeur de la plage.
        * Si le revenu rapporté dépassent la valeur moyenne de la plage la plus élevée, le revenu est compris dans la plage la plus élevée. **Important** ! Le revenu enregistré correspond à la valeur moyenne de cette plage. Le montant réel du revenu est donc ignoré.
        * Dans les données brutes, le montant réel du revenu et la plage correspondante sont bien proposés.

        **Exemple :**

        Le schéma illustre les plages de revenus ci-dessous.

        * A : 0-5
        * B : 5-10
        * C : 10-20

        Le revenu est enregistré en fonction des plages suivantes :

        | Exemple | Revenu rapporté par le SDK | Plage associée | Revenu enregistré |
        | --- | --- | --- | --- |
        | 1 | 5 | A | 2.5 $ |
        | 2 | 6 | B | 7,5 $ |
        | 3 | 10 | B | 7,5 $ |
        | 4 | 125 | C | 15 $ |
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="funnel-component" />

<Accordion title="Composant de l'entonnoir">

<Table>
  <tbody>
    <tr>
      <td colSpan="2">
        <Image alt="ConversionValueFunnel.png" src="https://files.readme.io/b43b5db0cee11c9addd50fb56af1ac6d3221e1956e2ee3c4c21a6940e9dfe61b-4406051997969.png" width="674px" />
      </td>
    </tr>
    <tr>
      <td>
        Obligatoire
      </td>
      <td>
        Non
      </td>
    </tr>
    <tr>
      <td>
        Pluri-utilisation autorisée
      </td>
      <td>
        Non
      </td>
    </tr>
    <tr>
      <td>
        Options des paramètres
      </td>
      <td>
        Liste un enchainement d'événements dans un entonnoir. Comme chaque événement est traité comme l'ensemble des événements qui le précédent, l'ordre dans lequel vous choisissez de lister les événements est très important. Cf exemple suivant.
      </td>
    </tr>
    <tr>
      <td>
        Exemple
      </td>
      <td>
        Un entonnoir contient les événements a, f, b, k et z (cf image précédente).

        | Exemple | Événement réalisé | Événements enregistrés |
        | --- | --- | --- |
        | 1 | A | A |
        | 2 | B | a, f, b |
        | 3 | z | a, f, b, k, z |
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="priority-measurement-component" />

<Accordion title="Composant de mesure des priorités">

Le composant de mesure des priorités (proposé dans le mode personnalisé) vous permet de classer par ordre le parcours d'activité d'un utilisateur en fonction de vos objectifs marketing. Les mesures classées en haute priorité l'emportent sur les mesures à faible priorité. Vous avez ainsi la possibilité de choisir quelles mesures doivent être effectuées à chaque étape de l'entonnoir de conversion. 

Chaque priorité (63 maxi) peut contenir un revenu, un événement in-app, ou les deux ensemble. Lorsqu'un utilisateur produit différents événements dans l'app, AppsFlyer détermine le degré de priorité correspondant à chaque action, puis définit la VC en fonction.

Pour faire simple : si l'on compare l'utilisation du mode Personnalisé avec composant et sans composant de priorité, on constate que **sans** le composant de priorité, AppsFlyer mappe l'ensemble des mesures possibles pour définir les VC. Mais **avec** le composant de priorité, seules les mesures prioritaires que vous avez explicitement définies sont utilisées pour mapper les VC.

Le principe de priorité est expliqué plus en détails dans cet [exemple](/docs/skan-conversion-studio#priority-measurement-detailed-example).

**Fonctionnement de la priorité**

* Vous pouvez définir 1 à 63 priorités. Le nombre disponible dépend de votre fenêtre d'activité et des paramètres de la SSOT.
* «Priority 1» possède toujours la priorité la plus haute. Plus «Priority» a un nombre élevé, et plus la priorité est basse.
* Une priorité se compose soit de [revenu](/docs/skan-conversion-studio#revenue-component) , soit d['un événement in-app,](/docs/skan-conversion-studio#inapp-event-component), soit des deux composants. Une priorité donnée peut contenir plusieurs événements in-app et flux de revenus.
* La priorité ne peut pas être définie pour un entonnoir. Cependant, vous pouvez choisir la priorité pour différents événements in-app afin de mesurer la conversion des utilisateurs dans un entonnoir.
* Pour utiliser le composant de mesure des priorités, vous ne pouvez pas avoir d'autres composants configurés, comme les événements in-app ou les revenus.

**Pour définir une mesure en fonction de la priorité :**

1. Dans AppsFlyer, rendez-vous dans **Studio de Conversion SKAN**
2. Sélectionnez **Personnalisé**, puis cliquez sur **Continuer**.
3. Si besoin est, cliquez sur **Supprimer** pour effacer les paramètres en cours.
4. Cliquez sur **+ Ajouter une mesure**.Sélectionnez **Priorité**.   
   Priority 1 s'affiche.  

   [![Priority1.png](https://files.readme.io/f0bc64c4fbb95462a17a1e6bb8d250d3396096b743b3d412cd0605d9b0a1079d-4756458366865.png)](https://files.readme.io/f0bc64c4fbb95462a17a1e6bb8d250d3396096b743b3d412cd0605d9b0a1079d-4756458366865.png)
5. Sélectionnez un composant de mesure dans :
   * Revenu
   * Évènement in-app
6. Remplissez les champs en suivant l'interface utilisateur.
   * N'oubliez pas qu'une priorité peut se composer d'un revenu, d'un événement in-app, ou bien des deux.
   * Les valeurs de plages des occurrences d'événements et des revenus doivent se suivre dans un ordre croissant. Exemple : les plages suivantes sont classées dans l'ordre croissant et elles se suivent : 1-5, 5-8, 8-10, etc. Une plage peut être utilisée plus d'une fois (elle est répétée) si la deuxième fois où elle est utilisée fait partie d'un ensemble, et a la même durée que la dernière priorité avec une plage. Par exemple, 1-5, 1-5 + ajouter au panier.
7. Cliquez sur **Valider.** Le message **Priorité validée** s'affiche. Si ce n'est pas le cas, corrigez la priorité avant de continuer.
8. Effectuez l'une des opérations suivantes :
   * Pour ajouter une priorité, cliquez sur **+ Ajouter une priorité.** La priorité 1 existante change de rang et devient la priorité 2. Complétez les paramètres de priorité comme précédemment.
   * Pour supprimer une priorité, cliquez sur ... > **Supprimer.**
   * Pour modifier le niveau de priorité, cliquez sur **Options** (⋮), puis sélectionnez **Changer l'ordre** ou bien **Baisser la priorité**.
   * Pour dupliquer une priorité, cliquez sur**Options** (⋮), puis sélectionnez **Dupliquer**.
   * Cliquez sur **Enregistrer** pour terminer le paramétrage des priorités.

</Accordion>

<div id="lock-window" />

<Accordion title="Verrouiller la fenêtre">

**Remarque**: Le verrouillage de fenêtre n'est disponible qu'avec SKAN 4 et +.

<table><tbody><tr><td colspan="2"><p><img alt="lock_window.png" src="https://files.readme.io/d9db51890a5d589b7343ed389d55af0c4181b249a2c5e970b9a5e1244c489abc-14240675527057.png"/></p></td></tr><tr><td><p>Utiliser</p></td><td><span>Par défaut, les fenêtres SKAN mesurent la valeur de l'utilisateur à certains moments suivant l'installation. Vous pouvez verrouiller les fenêtres plus tôt et envoyer des postbacks en même temps que les données disponibles. Pour ce faire, vous devez définir les conditions qui déclenchent le verrouillage des fenêtres.</span></td></tr><tr><td><p>Obligatoire</p></td><td>Non</td></tr><tr><td><p>Pluri-utilisation autorisée</p></td><td>Oui, une pour chaque fenêtre SKAN</td></tr><tr><td><p>Conditions</p></td><td><p>Le verrouillage de fenêtre offre deux possibilités pour verrouiller la fenêtre SKAN en avance :</p><ul><li>Durée : vous devez choisir une durée post installation (plus courte que la durée par défaut) pour verrouiller la fenêtre. <strong>Remarque</strong> : Un verrouillage basé sur la durée ne prend effet que si l'utilisateur ouvre l'application.</li><li>Valeur haute approximative : dès que la valeur haute approximative est atteinte, la fenêtre se referme.</li></ul></td></tr><tr><td><p>Effets de l'utilisation du verrouillage de fenêtre</p></td><td><p>Les postbacks SKAN ne contiennent aucune information indiquant l'heure de fermeture d'une fenêtre, le verrouillage d'une fenêtre n'est donc pas pris en compte lors du calcul de l'heure d'installation. Verrouiller la fenêtre en avance peut donc diminuer la précision avec laquelle l'heure d'installation est estimée.</p></td></tr></tbody></table>

</Accordion>

<div id="activity-window" />

<Accordion title="Fenêtre d'activité">

**Remarque** :

* La fenêtre d'activité est uniquement pertinente pour SKAN 3 et - (c'est-à-dire les modes personnalisé et fixe).
* Si vous utilisez SKAN 4 et + mais que les appareils des utilisateurs ou les réseaux publicitaires ne prennent pas en charge SKAN 4, la fenêtre d'activité est alors de 48 heures.

<table><tbody><tr><td colspan="2"><p><img alt="flex_activity_window.jpg" src="https://files.readme.io/ac51126eda5b9d319ccdd90adb936baaa512dcd844ad191cac6c20a45cd4aae8-6390396808081.jpg"/></p></td></tr><tr><td><p>Obligatoire</p></td><td>Oui </td></tr><tr><td><p>Pluri-utilisation autorisée</p></td><td>Non</td></tr><tr><td><p>Caractéristiques du décompte</p></td><td><ul><li>Le décompte possède une durée fixe, que vous définissez, et qui fonctionne à part du décompte IOS.</li><li>Le décompte iOS quant à lui possède une durée initiale de 24 heures. Chaque fois que la valeur de conversion augmente, le décompte repart à zéro.</li><li>Durée par défaut : 24 heures.</li><li>La mesure cesse lorsque l'un des deux décomptes atteint 0.</li></ul></td></tr><tr><td>Durée du décompte</td><td><ul><li>Durée : 12-72 heures. Pour obtenir plus d’options, cf <strong>Personnaliser la mesure</strong> dans ce tableau.</li><li>Lorsque le décompte arrive à zéro, AppsFlyer cesse d'effectuer les mesures.</li><li>Si le décompte possède une durée de plus de 24 heures, l'utilisateur doit interagir avec l'app au moins une fois dans l'intervalle. Dans le cas contraire, la mesure est interrompue car AppsFlyer ne pouvant pas empêcher le décompte iOS d'atteindre 0, iOS cesse alors de mesurer.</li></ul></td></tr><tr><td><p>Durée</p></td><td><p>12 ou 24 heures. Les intervalles impactent la précision de la dernière période d'activité et de l'heure d'installation. Pour obtenir plus d'options, consultez la rubrique <strong>Personnaliser la mesure</strong> du tableau. </p><p>La dernière période d'activité se trouve dans les rapports de données brutes, dans les colonnes <em>min_install_time</em> et <em>max_install_time</em>. Elle permet de déterminer l'heure d'installation, comme expliqué dans ce paragraphe.</p><p>Exemple :</p><ul><li>La durée du décompte est fixée à 48 heures</li><li>La dernière activité de l'utilisateur remonte à l'heure 40</li><li>En fonction de l'intervalle défini, la dernière période d'activité aura pour valeur : <br/><ul><li>Intervalle de 12 heures : 36–48h</li><li>Intervalle de 24 heures : 24–48h</li></ul></li></ul></td></tr><tr><td><p>Heure d'installation</p></td><td><p>L'heure d'installation est calculée comme suit :</p><p><code>Heure d'installation = heure d'arrivée du postback - [Dernière période d'activité moyenne] - [Délai du postback iOS]</code></p><ul><li> <code>Heure d'arrivée du postback</code> : l'heure à laquelle le postback iOS a été réceptionné par l'appareil (généralement par le réseau publicitaire).</li><li> <code>La dernière période d'activité moyenne</code> repose sur la VC et est calculée comme suit : <ul><li>Si CV = 0, la dernière période d'activité est supposée nulle (0).</li><li>Si CV &gt; 1 ou CV = null : en utilisant min_install_time et max_install time, elles sont calculées en fonction de l'intervalle et de la dernière fois où l'utilisateur a interagi avec l'application.  Exemple : si l'intervalle est 12, comme la dernière activité de l'utilisateur a eu lieu 25 heures après l'installation, le résultat est [24 + 36] / 2 = 30. </li></ul></li><li> <code>Délai du postback iOS</code>: [24 + 48 ] / 2 = 36. Notez que le décompte iOS se termine 24 heures après la dernière modification apportée à la VC, et que le postback est envoyé entre 0 et 24 heures après. <strong>36 heures est la valeur répandue.</strong> </li></ul></td></tr><tr><td><p>Options des paramètres</p></td><td><p>La fenêtre Activité comprend deux paramètres : la durée et les intervalles.</p><ul><li>Durée : 24–72 heures avec un intervalle de 24 heures. 3 intervalles maximum.</li><li>Durée : 12–72 heures avec un intervalle de 12 heures. 6 intervalles maximum.</li></ul></td></tr><tr><td><p>Effets des modifications de la durée de la fenêtre d'activité</p></td><td><ul><li>Le postback est envoyé entre 0 et 24 heures après la fin du décompte iOS. </li><li>Initialement, le décompte iOS est réglé sur 24 heures.</li><li>Si vous définissez la fenêtre d'activité sur plus de 24 heures, l'utilisateur devra être actif au moins une fois dans l'intervalle pour faire en sorte que le décompte iOS ne se termine pas.</li></ul></td></tr><tr><td><p>Remarques concernant les réseaux publicitaires</p></td><td><ul><li>La durée par défaut du décompte est fixée à 24 heures.</li><li>Vous pouvez choisir une durée différente, mais pensez au préalable à vérifier si vos partenaires de réseau publicitaire peuvent prendre en charge une autre période que celle définie par défaut. </li><li><span>Avec une fenêtre de 24 heures, vous pouvez améliorer vos mesures en divisant cette période de 24 heures en 2 intervalles de 12 heures chacun. Vous pourrez ainsi savoir si l'utilisateur a continué son activité dans l'application après les 12 premières heures. </span></li></ul></td></tr><tr><td><p>Exemple d'utilisation des capacités d'une période</p></td><td><p><span>Cette illustration donne l'exemple d'un décompte de 60 heures avec un intervalle de 12 heures.</span></p></td></tr><tr><td><p>Options de personnalisation de la fenêtre d'activité</p></td><td><p>Avec la personnalisation des mesures vous pouvez choisir une fenêtre d’activité plus longue et profiter d'une granularité de niveau horaire. Il en va de même pour le paramétrage des intervalles. Les paramètres ont les caractéristiques suivantes :</p><ul><li>Fenêtre d’activité : <ul><li>Période : 12 à 1512 heures (63 jours)  </li><li>Granularité : 1 heure</li></ul></li><li>Intervalles : <ul><li>Période : <span>1 heure au minimum, et tout autre multiplicateur de la fenêtre d'activité</span> </li><li>Granularité 1 heure</li></ul></li></ul><p>Remarque : le rapport entre la fenêtre d'activité et les intervalles doit être un nombre entier.</p><p>Recommandation : ne définissez pas l’intervalle sur plus de 24 heures car au-delà, l’estimation de l'heure d’installation perdra en précision.</p></td></tr></tbody></table>

</Accordion>

## Informations supplémentaires

<div id="view-cv-mapping" />

<Accordion title="Afficher le mappage des VC">

* Affichez les événements associés à une VC en la sélectionnant. Les événements mappés s'affichent sous le tableau.
* Téléchargez le tableau de mappage des CV au format .CSV. Cliquez sur **Télécharger le fichier de mappage.**
* Pour obtenir le mappage des CV utilisez l'<Anchor target="_blank" href="/marketers/fr/docs/skan-cv-schema-api-for-advertisers">API de schéma CV SKAN pour les annonceurs</Anchor>.

![CVmapping.png](https://files.readme.io/97ec2570636897a6274f7750c7f77c92d8457cab51660de496bec6cb7504c4a3-4407788932113.png)

#### Les colonnes du fichier de mappage CSV

| Colonne | Description |
| --- | --- |
| app\_id |  |
| conversion\_value | Valeur CV :<ul><li>0-63</li><li>Faible, moyenne ou élevée</li></ul> |
| event\_name |  |
| min\_event\_counter | Le seuil le plus bas de la plage du compteur d'événements |
| max\_event\_counter | <ul><li>Le seuil le plus haut de la plage du compteur d'événements.</li><li>Dans les rapports générés par AppsFlyer, le nombre d'événements est calculé d'après la formule suivante : Total ([min\_event\_counter + max\_event\_counter]) / 2</li></ul> |
| min\_event\_revenue | Le seuil le plus bas de la plage des revenus d'événement en USD |
| max\_event\_revenue | <ul><li>Le seuil le plus haut de la plage des revenus d'événement en USD</li><li>Dans les rapports générés par AppsFlyer, le revenu est calculé d'après la formule suivante : ([min\_event\_revenue + max\_event\_revenue]) / 2)</li></ul> |
| min\_time\_post\_install | Le seuil le plus bas (nombre d'heures après installation), indiquant quand l'utilisateur a été actif pour la dernière fois dans l'application. |
| max\_time\_post\_install | Le seuil le plus haut (nombre d'heures après installation), indiquant quand l'utilisateur a été actif pour la dernière fois dans l'application. |
| last\_config\_change | La date à laquelle vous avez enregistré la configuration du Studio de Conversion SKAN. |

</Accordion>

<div id="conversion-value-capacity-formula" />

<Accordion title="Formule de capacité de la valeur de conversion">

Comme nous l'avons vu précédemment, le nombre maximum de valeurs de conversion est de 64. La formule suivante permet de calculer combien de valeurs de conversion sont utilisées par le mode.

```http
(activity time duration in hours / interval size in hours) * 
(number of revenue ranges + 1 ) * 
(number of in-app event ranges + 1 ) * 
(number of steps in a funnel + 1)
```

Vous pouvez modifier la formule pour inclure tous les composants de mesure

</Accordion>

<div id="maximized-custom-cv-examples" />

<Accordion title="Exemples de VC personnalisées optimisées">

#### Exemple 1

| Composante | Description |
| --- | --- |
| Fenêtre d'activité | <ul><li>Durée : 24 heures</li><li>Intervalle : 24 heures (soit 1 intervalle)</li></ul> |
| Revenu | <ul><li>Le revenu est rapporté en fonction d'un seul événement in-app (global.</li><li>Plages de revenus : 15</li></ul> |
| Achat | Aucun |
| Tunnel | 3 événements in-app |

#### Exemple 2

| Composante | Description |
| --- | --- |
| Fenêtre d'activité | <ul><li>Durée : 24 heures</li><li>Intervalle : 12 heures (soit 2 intervalles)</li></ul> |
| Revenu | <ul><li>Les revenus sont rapportés et classés par type selon deux événements in-app différents</li><li>Plages de revenus : 3 (par événement in-app)</li></ul> |
| Paramétrage in-app pour la conversion | 1 événement in-app pour mesurer la conversion, chaque événement in-app requiert une plage |
| Tunnel | Aucun |

#### Exemple 3

| Composante | Description |
| --- | --- |
| Fenêtre d'activité | <ul><li>Durée : 24 heures</li><li>Intervalle : 24 heures (soit 1 intervalle)</li></ul> |
| Revenu | <ul><li>Le revenu est rapporté en fonction d'un seul événement in-app (global.</li><li>Plages de revenus : 3</li></ul> |
| In-app paramétré pour l'engagement | <ul><li>2 événements in-app pour mesurer le nombre d'événements d'engagement</li><li>Plages d'occurrences : 3 par événement in-app</li></ul> |
| Tunnel | Aucun |

#### Exemple 4

| Composante | Description |
| --- | --- |
| Fenêtre d'activité | <ul><li>Durée : 48 heures</li><li>Intervalle : 12 heures (soit 4 intervalles)</li></ul> |
| Revenu | <ul><li>Le revenu est rapporté en fonction d'un seul événement in-app (global.</li><li>Plages de revenus : 7</li></ul> |
| Paramétrage in-app pour la conversion | 1 événement in-app pour mesurer la conversion (requiert 1 plage) |
| Tunnel | Aucun |

</Accordion>

<div id="priority-measurement-detailed-example" />

<Accordion title="Exemple détaillé de mesure des priorités">

Dans une appl d'achat, l'annonceur souhaite que la mesure se concentre sur :

* Actions des **utilisateurs non payants**
* Revenus des utilisateurs **payants**

De fait, l'annonceur utilise les VC pour enregistrer les revenus d'une manière plus précise. Pour obtenir ces mesures détaillées, un ensemble de priorités est appliqué aux mesures tel qu'indiqué dans le tableau suivant.

N'oubliez pas :

* La priorité la plus élevée est toujours celle qui est en 1. **Remarque** ! Les numéros des priorités ne correspondent pas à ceux des VC. Les mappages des VC s'affichent dans l'interface utilisateur.
* Le nombre de priorités ne peut pas dépasser 63. Le nombre réel disponible dépend de la fenêtre d'activité et de l'activation ou non de la SSOT.
* Chaque priorité contient une plage de revenus, ou une plage d'événements in-app, ou les deux.
* Valeurs de la plage : la valeur la plus basse n'est pas comprise dans la plage, mais la valeur la plus haute l'est. Exemple, la plage $5-$10 n'inclut pas la valeur 5, mais elle comprend la valeur 10.

#### Exemple de paramétrage des priorités de mesure

<table><tbody><tr><th><p>Nº de priorité</p></th><th><p>Plages de revenus</p></th><th>Évènement in-app</th></tr><tr><td>1 [Priorité élevée]</td><td>$5-$10</td><td>send_recommendation</td></tr><tr><td>2</td><td>$5-$10</td><td>--</td></tr><tr><td>3</td><td>$0-$5</td><td>send_recommendation</td></tr><tr><td>4</td><td>$0-$5</td><td>--</td></tr><tr><td>5</td><td>--</td><td>send_recommendation<br/>add_to_cart</td></tr><tr><td>6</td><td>--</td><td><p>send_recommendation</p></td></tr><tr><td>7 [Priorité basse]</td><td>--</td><td>add_to_cart</td></tr><tr><td colspan="3">-- Aucune valeur définie</td></tr></tbody></table>

Le tableau qui suit présente des exemples de parcours utilisateur. Chaque exemple indique la liste des actions effectuées par l'utilisateur tout au long de son parcours, ainsi que la priorité définie par AppsFlyer.

Dans le tableau :

* Les actions multiples sont séparées par des >
* La valeur entre parenthèses () correspond à la priorité définie par AppsFlyer une fois que l'utilisateur a réalisé l'action. En fonction de la priorité AppsFlyer met à jour la CV dans l'app.

#### Exemples de parcours utilisateur

| Exemple de parcours utilisateur | Actions de l'utilisateur et priorité |
| --- | --- |
| A | add\_to cart (7) |
| B | add\_to\_cart (7) > send\_recommendation (5) |
| C | Achat de 3$ (4) |
| D | Achat de 6$ (2) |
| E | Achats de 6$ (2) > send\_recommendation (1) |

</Accordion>

<div id="fixed-mode-examples" />

<Accordion title="Exemples de mode fixe">

#### Exemple A : mesure du revenu

| Facteur | Remarques |
| --- | --- |
| Scénario | <ul><li>20 utilisateurs installent l'app et effectuent les achats suivants :<ul><li>9 utilisateurs, effectuant chacun un achat de 10 $</li><li>5 utilisateurs, effectuant chacun un achat de 5 $</li><li>1 utilisateur effectue un achat de 1 $, puis de 3 $, puis de 5 $, et enfin de 1 $. 10 $ au total.</li></ul></li><li>Données de coût fournies par l'API de l'ad network : 30 $</li></ul> |
| Configuration SKAN | <ul><li>Sélectionner le type de mesure : revenu</li><li>Définir le facteur de conversion  : 1 unité de conversion = 1 $</li><li>Événement de conversion désigné : dans le SDK, vous devez envoyer des revenus en utilisant le paramètre *af\_revenue*.</li></ul> |
| Métriques sélectionnées | Mesures liées au revenu disponibles<ul><li>Installations : 20</li><li>Revenus : 125 $</li><li>Conversions : 15</li><li>ARPU : 6,25 $</li><li>ROI : 316 %</li></ul> |
| Nombre de lignes de données brutes par rapport | <Anchor target="_blank" href="/marketers/fr/docs/skan-raw-data-reports">Les rapports de données brutes sont disponibles via Data Locker</Anchor><ul><li>Postbacks de l'appareil : 20 lignes</li><li>Installations : 20 lignes</li><li>Événements in-app : 15 lignes. Important ! L'utilisateur effectuant plusieurs achats est représenté par une seule ligne de 10 $.</li></ul> |
| Considérations pour les développeurs | Les événements générateurs de revenus sont reconnus |

#### Exemple B : mesure de conversion

<Table>
  <thead>
    <tr>
      <th>
        Facteur
      </th>
      <th>
        Remarques
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Exemple
      </td>
      <td>
        * 5 utilisateurs (A-E) installent l'app
        * Ils effectuent 0 à 3 événements in-app différents, comme le montre le tableau suivant
        * Données de coût fournies par l'API de l'ad network : 30 $

        #### Événements in-app effectués par des utilisateurs

        |  | in-app-1 | in-app-2 | in-app-3 |
        | --- | --- | --- | --- |
        | Utilisateur A | A effectué | A effectué | - |
        | Utilisateur B | A effectué | - | A effectué |
        | Utilisateur C | A effectué | A effectué | - |
        | Utilisateur D | A effectué | A effectué | - |
        | Utilisateur E | - | - | - |
      </td>
    </tr>
    <tr>
      <td>
        Configuration de l'attribution de SKAdNetwork
      </td>
      <td>
        Sélectionner le type de mesure : conversion

        * Sélectionner les événements in-app  : in-app-1, in-app-2, in-app-3
        * Dans le <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#dashboard-settings">tableau de bord</Anchor> SKAdNetwork, vous devez sélectionnez un des événements pour calculer la métrique des utilisateurs convertis. Vous pouvez modifier l'événement sélectionné selon vos besoins.
      </td>
    </tr>
    <tr>
      <td>
        Métriques sélectionnées
      </td>
      <td>
        #### Indicateurs liés à l'app disponibles

        | Métrique | App | in-app-1 | in-app-2 | in-app-3 |
        | --- | --- | --- | --- | --- |
        | d'installations | 5 |  |  |  |
        | Conversions | 4 |  |  |  |
        | Utilisateurs uniques |  | 4 | 3 | 1 |
        | eCPA | 7,5 $ |  |  |  |

        **Important !** Comme l'événement de conversion désigné est in-app 1, la valeur 4 est utilisée pour calculer les mesures au niveau de l'app et pour les mesures in-app-1.
      </td>
    </tr>
    <tr>
      <td>

      </td>
      <td>
        <Anchor target="_blank" href="/marketers/fr/docs/skan-raw-data-reports">Les rapports de données brutes sont disponibles via Data Locker</Anchor>

        * Postbacks de l'appareil : 5 lignes
        * Installations : 5 lignes
        * Événements in-app : 8 lignes
      </td>
    </tr>
    <tr>
      <td>
        Considérations pour les développeurs
      </td>
      <td>
        * Veillez à envoyer les événements que les utilisateurs effectuent dans l'app.
        * La solution SKAdNetwork ne tient pas compte des valeurs des événements (sauf en ce qui concerne la mesure des revenus).
      </td>
    </tr>
  </tbody>
</Table>

#### Exemple C  : mesure de l'engagement

<Table>
  <thead>
    <tr>
      <th>
        Facteur
      </th>
      <th>
        Remarques
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Exemple
      </td>
      <td>
        5 utilisateurs installent l'app et l'ouvrent le nombre de fois indiqué dans le tableau.

        #### Ouverture de l'app

        |  | Nombre de fois où l'événement a été effectué |
        | --- | --- |
        | Utilisateur A | 63 |
        | Utilisateur B | 10 |
        | Utilisateur C | 5 |
        | Utilisateur D | 1 |
        | Utilisateur E | - |
      </td>
    </tr>
    <tr>
      <td>
        Configuration de l'attribution de SKAdNetwork
      </td>
      <td>
        * Sélectionnez le type de mesure : engagement
        * Événement de conversion désigné : af\_app\_opened Important ! Vous pouvez utiliser n'importe quel événement disponible.
      </td>
    </tr>
    <tr>
      <td>
        Métriques sélectionnées
      </td>
      <td>
        Exemples de métriques disponibles

        * Installations : 5
        * Conversions : 4
        * Sessions : 79
      </td>
    </tr>
    <tr>
      <td>
        Nombre de lignes de données brutes par rapport
      </td>
      <td>
        <Anchor target="_blank" href="/marketers/fr/docs/skan-raw-data-reports">Les rapports de données brutes sont disponibles via Data Locker</Anchor>

        * Postbacks de l'appareil : 5 lignes
        * Installations : 5 lignes
        * Événements in-app : 79 lignes ; une ligne équivaut à une session
      </td>
    </tr>
    <tr>
      <td>
        Considérations pour les développeurs
      </td>
      <td>
        À chaque fois que l'utilisateur effectue l'événement d'engagement sélectionné : envoyez l'événement in-app. SKAdNetwork compte le nombre de fois que vous envoyez l'événement.
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="skan-conversion-studio-api" />

<Accordion title="API Studio de conversion SKAN">

Si vous souhaitez appliquer les mêmes configurations de valeurs de conversion SKAN à plusieurs applications, concevoir le schéma pour chaque application séparément dans l'interface utilisateur de Conversion Studio peut s'avérer long et complexe. Pour gagner du temps et de l'énergie, vous configurer votre schéma SKAN une fois dans l'interface utilisateur, puis utiliser l'API du Studio de conversion SKAN pour utiliser ce même schéma dans plusieurs applications. **Remarque** : L'API prend uniquement en charge les schémas configurés dans l'interface utilisateur à l'aide de SKAN 4 ou des modes de mesure personnalisés (mais dans ces modes, le composant de mesure Predict n'est pas pris en charge).

**Pour utiliser l'API Studio de conversion SKAN** :

1. Récupérez le <Anchor target="_blank" href="/marketers/fr/docs/managing-appsflyer-tokens">jeton d'API</Anchor>. Seul un admin peut obtenir le jeton.
2. Donnez à votre développeur le jeton d'API à utiliser dans l'en-tête d'authentification.
3. Transmettez les identifiants des apps suivantes à vos développeurs :
   * L'application pour laquelle le schéma SKAN est configuré dans l'interface utilisateur (c'est-à-dire l'application à partir de laquelle vous souhaitez copier le schéma SKAN).
   * Toutes les applications auxquelles vous souhaitez appliquer le même schéma.
4. Dites à votre développeur de suivre les instructions de <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/skan-studio-config-overview-1">l'API Studio de conversion SKAN</Anchor> dans le hub des développeurs.

**Remarque** :

* L'API peut être utilisée pour copier le schéma dans une application par appel d'API. Votre développeur peut alors créer un script pour copier le schéma requis dans plusieurs applications.
* L'API Studio de conversion SKAN n'est pas disponible pour les agences.

</Accordion>

## Procédures supplémentaires

<div id="change-skan-measurement-mode" />

<Accordion title="Modifier le mode de mesure SKAN">

Important :

* Lorsque vous commencez à utiliser le mode de mesure SKAN 4, vous ne pouvez plus revenir à un mode précédent.
* Lorsque vous modifiez les paramètres, ils prennent effet à 00:00 UTC et une période de transition démarre. Au cours de cette transition, nous décodons la valeur de conversion en utilisant les derniers paramètres sélectionnés. Cependant, un postback qui arrive à l'instant T concerne une installation qui a eu lieu dans le passé.
* Le nombre d'installations signalé n'est pas lié à la modification des paramètres et est exact.

</Accordion>

<div id="disable-skan-measurement" />

<Accordion title="Désactiver la mesure de SKAN">

Pour désactiver la mesure SKAdNetwork :

1. Dans AppsFlyer, ouvrez **Configuration** > **Studio de Conversion SKAN**.
2. Cliquez sur ⋮.
3. Désactivez la **mesure SKAdNetwork**.   
   Entre autres, le SDK cessera d'appeler les fonctions SKAN de type *registerAppForAdNetworkAttribution* ou *updateConversionValue.*
4. Cliquez sur **Enregistrer les modifications**.

</Accordion>

<div id="report-events-by-servertoserver-api" />

<Accordion title="Signaler les événements par API de serveur à serveur">

![SKAdNetwork_-_S2S__2_.png](https://files.readme.io/ed55e5c10184afcc27ce7e414a3213f69d2c20bd70d38f78be338f1b17254ee2-16281446657937.png)

Le SDK et <Anchor target="_blank" href="/marketers/fr/docs/server-to-server-events-api-for-mobile-s2s-mobile">l'API de serveur à serveur (S2S)</Anchor> peuvent tous deux envoyer des événements in-app aux serveurs AppsFlyer.

Le flux S2S est le suivant :

* Un événement en lien avec l'utilisateur se produit sur les serveurs de l'annonceur. L'app peut être ouverte ou fermée à ce moment.
* Les serveurs de l'annonceur signalent l'événement à AppsFlyer par S2S.
* AppsFlyer calcule la valeur de conversion mise à jour, puis : 
  * Si l'app est ouverte sur l'appareil de l'utilisateur : le SDK est informé de la valeur mise à jour. Le SDK met à jour la valeur de conversion iOS sur l'appareil.
  * Si l'app n'est pas ouverte sur l'appareil de l'utilisateur : le serveur attend que l'app soit ouverte pour informer le SDK de la valeur de conversion. L'action doit forcément se produire avant la fin de la fenêtre d'activité. Si la notification échoue, l'événement est ignoré.

**Version du SDK requise**

* Adoptez la dernière version du SDK dans l'app. **Important !** Aucune action supplémentaire n'est requise de la part du développeur.

**Pour implémenter l'envoi d'événements in-app via l'API de serveur à serveur :**

1. Effectuez l'une des opérations suivantes :
   * Si votre mode sélectionné est SKAN 4 ou personnalisé :
     * Aucune modification des paramètres n'est requise.
   * Si vous avez choisi le mode revenu, conversion ou engagement :
     1. Dans AppsFlyer, ouvrez **Configuration** > **Studio de Conversion SKAN**.
     2. Cliquez pour accéder aux options (⋮).
     3. Activez **Enregistrer les événements in-app envoyés par l'API S2S**.
2. Envoyer les événements par S2S.

**Limitation**

* Si vous implémentez *l'anonymisation de l'utilisateur* pour un utilisateur donné, vous ne pouvez pas envoyer d'événements par S2S pour cet utilisateur.

</Accordion>

<div id="add-ssot-to-fixed-mode-measurements" />

<Accordion title="Ajouter le SSOT aux mesures en mode fixe">

Si vous avez configuré le mode de mesure Revenus ou Engagement, la SSOT (Single Source of Truth, qui supprime les doublons et signale avec précision les données iOS) n'est pas prise en charge. <Anchor target="_blank" href="/marketers/fr/docs/single-source-of-truth-ssot-guide-for-ios-attribution">En savoir plus sur la SSOT</Anchor>

**Pour activer la SSOT lorsque le mode Revenu ou Engagement est configuré** :

1. Dans AppsFlyer, ouvrez **Configuration** > **Studio de Conversion SKAN**.
2. Faites défiler jusqu'à votre mode de mesure actif.
3. Cliquez sur **+ Ajouter SSOT**.
   * Le bouton SSOT est automatiquement activé.
   * Vos plages de mesure en mode fixe sont modifiées au minimum, pour donner à la SSOT un certain espace de valeur de conversion.
4. Cliquez sur ***Enregistrer***.

</Accordion>

<div id="specifications-and-limitations" />

<Accordion title="Caractéristiques et limitations">

| Caractéristiques | Remarques |
| --- | --- |
| Agences | Les agences ont <Anchor target="_blank" href="/partners/fr/docs/getting-started-agency-onboarding#accès-au-skan-conversion-studio">un accès limité au SKAN Conversion Studio des annonceurs</Anchor>. |
| Valeurs approximatives | Jusqu'à 10 composants de mesure. |
| Rapport In-App Events Organiques | Dans les modes *Custom* et *Decode* de SKAN 4, ni les mesures organiques des événements in-app, ni le revenu global ne sont disponibles. |

</Accordion>

<div data-zendesk-anchors="skan-conversion-studio-basics=studio-de-conversion-skan--pr%C3%A9sentation 01H7Z08MFDASBCBJD18QTXYSXK=studio-de-conversion-skan--pr%C3%A9sentation 01H7Z08MFDX3VYJTSWXQ5HQ7BZ=measurement-principles-and-definitions s2s-principles=principes-de-base-du-s2s 01H7Z08MFDWRGVNXB62Z6CT1G7=principes-de-base-du-s2s setting-up-conversion-values-in-skan-conversion-studio=configuration-des-valeurs-de-conversion-dans-skan-conversion-studio 01H7Z08MFDB76C6Z5SSXHFT71P=configuration-des-valeurs-de-conversion-dans-skan-conversion-studio 01H7Z08MFDEAYHJAG9XA2TGBWV=important- 01H7Z08MFD7VY1QP85W0YPK8RC=skan-4 01H7Z08MFD3SWVZK68K45NYDP8=custom 01H7Z08MFDZ1EKDQNZWGF7DHK9=fixed-modes fixed-mode-measurement=mesures-en-mode-fixe 01H7Z08MFDAYVJKJBT08R82N26=mesures-en-mode-fixe 01H7Z08MFDCJGZGQR2JR4WQVHR=decode measurement-components=composants-de-la-mesure 01H7Z08MFDFE345QWHF77RGTD7=composants-de-la-mesure 01H7Z08MFE5G01NGY5EFTAW93M=single-source-of-truth 01H7Z08MFEZRQ9NA2KTJW0PSST=predict-component 01H7Z08MFERDJHSD8NT5KN7DKN=inapp-event-component 01H7Z08MFETMGAE67X499V4092=revenue-component 01H7Z08MFEQG2HRJBWBYFTW3ZK=funnel-component 01H7Z08MFE22J8DDBDNJ18KBEJ=priority-measurement-component 01H7Z08MFES844SS08HS17Y29R=lock-window 01H7Z08MFE61QCC0MZW5RJ910B=activity-window additional-information=informations-suppl%C3%A9mentaires 01H7Z08MFET64PSAVMREQ4HP4S=informations-suppl%C3%A9mentaires 01H7Z08MFEKP9WNGJD2GBVKB0P=view-cv-mapping csv-mapping-file-columns=les-colonnes-du-fichier-de-mappage-csv 01H7Z08MFETCB428W1TXTH2HJ8=les-colonnes-du-fichier-de-mappage-csv 01H7Z08MFE5CBQK024CF8FARJ9=conversion-value-capacity-formula 01H7Z08MFETZVQSNWX639E56SK=maximized-custom-cv-examples example-1=exemple1 01H7Z08MFEXME7RV67XTZRDWJE=exemple1 example-2=exemple2 01H7Z08MFEHRF4656X5AR301D8=exemple2 example-3=exemple-3 01H7Z08MFEK0725CN35TP3MPYT=exemple-3 example-4=exemple-4 01H7Z08MFES7W3EF2JJ8B75K99=exemple-4 01H7Z08MFF2JXA0BFNKCW3ZCZ7=priority-measurement-detailed-example measurement-priorities-setting-example=exemple-de-param%C3%A9trage-des-priorit%C3%A9s-de-mesure 01H7Z08MFFXAAC37MBV0ES6ADQ=exemple-de-param%C3%A9trage-des-priorit%C3%A9s-de-mesure user-journey-scenarios=exemples-de-parcours-utilisateur 01H7Z08MFFJ9TQMH0Q93B7N1A8=exemples-de-parcours-utilisateur 01H7Z08MFFNBXECB8A5Y0KH9C8=fixed-mode-examples example-a-revenue-measurement=exemple-a-mesure-du-revenu 01H7Z08MFFVKZN3Y2R1ZEVEW4D=exemple-a-mesure-du-revenu example-b-conversion-measurement=exemple-b-mesure-de-conversion 01H7Z08MFFNBA5786R5XZDA5FG=exemple-b-mesure-de-conversion inapp-events-performed-by-users=%C3%A9v%C3%A9nements-in-app-effectu%C3%A9s-par-des-utilisateurs 01H7Z08MFFA7C6HWQPADZXQQNC=%C3%A9v%C3%A9nements-in-app-effectu%C3%A9s-par-des-utilisateurs inapp-related-metrics-available=indicateurs-li%C3%A9s-%C3%A0-lapp-disponibles 01H7Z08MFF1PEE91J5CJN1GC7V=indicateurs-li%C3%A9s-%C3%A0-lapp-disponibles example-c-engagement-measurement=exemple-c--mesure-de-lengagement 01H7Z08MFF8V718C23PQ2NG3C3=exemple-c--mesure-de-lengagement app-opens=ouverture-de-lapp 01H7Z08MFF4PRHSR8NCJ1Q78WM=ouverture-de-lapp 01H7Z08MFFVS6MYC9EB3KP0H2Y=skan-conversion-studio-api additional-procedures=proc%C3%A9dures-suppl%C3%A9mentaires 01H7Z08MFFPZ4GKM5GFMAE2HDJ=proc%C3%A9dures-suppl%C3%A9mentaires 01H7Z08MFFPKCX5TFQQTMYJEGW=change-skan-measurement-mode 01H7Z08MFF78F9NMWJATYE2YFE=disable-skan-measurement 01H7Z08MFFD4T3D71A6R9K83A3=report-events-by-servertoserver-api 01H7Z08MFFFAEW6NP0YAX773B3=add-ssot-to-fixed-mode-measurements 01H7Z08MFFG9EQFVEKN3AXE9DD=specifications-and-limitations" />
