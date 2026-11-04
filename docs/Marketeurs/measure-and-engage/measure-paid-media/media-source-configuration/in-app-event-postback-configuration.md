---
title: Configuration des postbacks d'événements in-app
metadata:
  keywords:
    - In-App Events
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-04-11T08:47:14Z'
  edited_at: '2024-06-17T15:47:54Z'
  id: 208439256
  locale: fr
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/fr/articles/208439256
---
> **En bref :** mesurez l'engagement dans l'app et la qualité de vos utilisateurs, et optimisez vos campagnes à l'aide des données sur les événements in-app.

<div id="overview" />

## Présentation

Les événements in-app permettent aux marketeurs de mesurer l'engagement dans l'app et la qualité des utilisateurs à partir de différentes sources pour élaborer la bonne stratégie d'acquisition d'utilisateurs.Les réseaux publicitaires utilisent les informations des événements in-app pour optimiser les campagnes et mener des campagnes de coût par action/événement. Les réseaux publicitaires reçoivent des données sur les événements in-app par l'intermédiaire de postbacks, envoyés en temps réel. <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview">À propos des événements in-app riches</Anchor>.

<div id="postback-in-app-event-selection" />

## Sélection du postback d'événement in-app

Les marketeurs peuvent sélectionner les événements in-app qu'ils souhaitent renvoyer aux réseaux publicitaires, à l'aide des paramètres décrits dans cet article.

> 📘 **Note**
>
> * Les événements in-app incluent les événements **rejetés**, c'est-à-dire les événements in-app bloqués par Protect360 ou les événements jugés non conformes aux règles de validation cibles.
> * Si la section **Postbacks d'événements in-app** n'apparait pas dans l'onglet **Intégration**, cela signifie que le partenaire n'a pas encore pré-configuré l'enregistrement de ses événements in-app avec AppsFlyer. Le partenaire peut contacter AppsFlyer via le <Anchor target="_blank" href="https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif">widget assistant du partenaire</Anchor> pour compléter l'intégration.

<div id="in-app-event-postback-window" />

## Fenêtre des postbacks d'événements in-app

La fenêtre de postback d'événements in-app permet aux marketeurs qui travaillent avec des réseaux sur la base du CPA (coût par action) de configurer des fenêtres de post-conversion après lesquelles les postbacks d'événement ne sont plus envoyés.

Par exemple, si vous êtes facturé pour des événements se produisant dans les 15 jours suivant l'installation d'un utilisateur, définissez la fenêtre comme suit :

<Image alt="15-day_in_app_event_postback_setting.png" src="https://files.readme.io/6ffcd335b85334015f518895b317d3a5e273f4e00c31e3694c0f95a22ba6d4fb-33379700644497.png" width="529px" />

Les postbacks créés après cette période ne sont pas envoyés, le réseau n'est pas notifié, mais les événements sont toujours enregistrés dans AppsFlyer et ils sont attribués au réseau.

Les postbacks sont toujours envoyés d'après le paramètre de la fenêtre **en cours.** Cf exemple suivant :

| 1er janvier | La fenêtre est de 15 jours.<br /><br />L'utilisateur installe une application. |
| --- | --- |
| Le 2 janvier | La fenêtre est modifiée et passe à 10 jours. |
| 14 janvier | L'utilisateur effectue un achat.<br /><br />Le postback n'est pas envoyé au réseau publicitaire parce que l'événement ne tombe pas dans la fenêtre actuelle (10 jours). |
| 15 Janvier | La fenêtre est modifiée et passe à 20 jours. |
| 18 janvier | L'utilisateur effectue un autre achat.<br /><br />Cette fois, le postback est envoyé, puisque l'événement se situe dans la fenêtre actuelle (20 jours). |

<div id="default-postback-window" />

### Fenêtre de postback par défaut

Lorsque vous commencez à mettre en place des postbacks d'événements in-app, la fenêtre par défaut est automatiquement fixée à six mois.

> 📘 **Note**
>
> Si vous avez commencé à utiliser les postbacks d'événements in-app avec un partenaire donné avant le 30 juillet 2019, le paramètre par défaut de la fenêtre est Lifetime (Durée de vie). Ce qui signifie que les postbacks d'événements in-app sont systématiquement envoyés.

<div id="who-can-configure-postback-windows" />

### Qui peut configurer les fenêtres de postback ?

* Marketeurs
* Les agences, si elles ont l'<Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#autorisations-pour-lagence">autorisation</Anchor> **de configurer les postbacks d'événements in-app .**  
  **Remarque :** Un marketeur et une agence travaillant avec le même réseau publicitaire peuvent configurer les fenêtres de postback séparément l'un de l'autre, en fonction de leur contrat avec le réseau.
* Les partenaires, s'ils ont l'<Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#permissions-tab">autorisation</Anchor> **de configurer les postbacks d'événements in-app** .

<div id="event-mapping" />

## Le mappage d'événement

Chaque marketeur peut donner un nom différent à un événement du même type. Les noms de ces événements peuvent également différer des noms des partenaires.

Par exemple, lorsqu'un utilisateur achète quelque chose par l'intermédiaire d'une application, un marketeur peut l'appeler `achat`, ou un donner un identifiant moins parlant, comme `evenement5`, et un partenaire peut l'appeler `achat_evenement`.

Pour s'assurer que les événements du marketeur correspondent aux mêmes événements que ceux des partenaires, les noms des événements doivent être mappés.

> 📘 **Note**
>
> Les événements de l'onglet Intégration qui sont mappés pour un partenaire précis s'appliquent à la fois aux postbacks standard et aux <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">postbacks SKAN.</Anchor>

<div id="mapping-methods" />

### Les méthodes de mappage

Chaque partenaire décide de la méthode à utiliser pour mapper ses événements in-app :

* [Saisir l'ID de l'événement partenaire](/docs/in-app-event-postback-configuration#h_c513e6d4-d46f-4070-a98d-1888a5ea939d)
* [Sélectionner l'ID de l'événement dans la liste](/docs/in-app-event-postback-configuration#select-an-event-id-from-the-list)
* [Envoyer les événements tels quels (non mappés)](/docs/in-app-event-postback-configuration#send-events-as-they-are-unmapped)

> 📘 **Note**
>
> * Toutes les méthodes de cartographie n'apparaissent pas pour tous les partenaires
> * Vous pouvez [autoriser le partenaire](/docs/in-app-event-postback-configuration#le-mappage-dévénements-par-les-réseaux-publicitaires) à effectuer lui-même le mappage

<div id="h_c513e6d4-d46f-4070-a98d-1888a5ea939d" />

<Accordion title="Saisir l'ID de l'événement partenaire">

* **AppsFlyer**: sélectionnez un événement dans la liste des événements de votre app.
* **mappé à l'événement du partenaire**: dans le champ de texte, saisissez l'identifiant de l'événement reçu du partenaire, qui correspond à l'événement de votre app (événement AppsFlyer).

> 📘 **Note**
>
> * Les noms d'événements sont sensibles à la casse. Pour éviter les incohérences, assurez-vous d'utiliser le bon nom d'événement pour toutes les sources média et versions d'app.
> * Lorsque vous tapez le nom d'un événement, vous pouvez utiliser des espaces soulignés (tirets bas) avant ou après le nom de l'événement. Utilisez les tirets du bas uniquement si le nom de l'évènement envoyé par AppsFlyer contient les mêmes tirets du bas.

[![enter_event_name.png](https://files.readme.io/b9d65d3a6b4c1ab4d3f7e83cc2226af5c5a83e1e83cfbfa3df36d295ae568a45-33379700646545.png)](https://files.readme.io/b9d65d3a6b4c1ab4d3f7e83cc2226af5c5a83e1e83cfbfa3df36d295ae568a45-33379700646545.png)

</Accordion>

<div id="select-an-event-id-from-the-list" />

<Accordion title="Sélectionner l'ID de l'événement dans la liste">

* **Évènement AppsFlyer**: sélectionnez un événement dans la liste des événements de votre app.
* **mappé à l'événement partenaire**: dans la liste des événements partenaires prédéfinis, sélectionnez l'événement qui correspond à l'événement de votre app (événement AppsFlyer).

[![In-app_event_postbacks_en-us.png](https://files.readme.io/71455978bc7511c2d98f7a396fd7c86e646ec358eb6e362f13ee418c7fdcd1da-33379700647825.png)](https://files.readme.io/71455978bc7511c2d98f7a396fd7c86e646ec358eb6e362f13ee418c7fdcd1da-33379700647825.png)

</Accordion>

<div id="send-events-as-they-are-unmapped" />

<Accordion title="Envoyer les événements tels quels (non mappés)">

Certains partenaires préfèrent recevoir des postbacks d'événements non mappés dans l'app, c'est-à-dire que les noms des événements sont envoyés tels qu'ils sont nommés dans votre app. Peu importe que l'événement soit appelé `achat`, `acquisition` ou `événement5`.

Vous pouvez choisir les événements non mappés à envoyer au partenaire :

* **Ajouter manuellement :** sélectionnez des événements spécifiques.
* **Envoyer tous les événements (à l'exclusion des désinstallations et des sessions)**: envoyez tous vos événements. Cela n'inclut pas les désinstallations, les sessions (lancements d'applications) et l'événement `af_app_opened`.

> 📘 **Note**
>
> Pour éviter que les annonceurs ne partagent involontairement un trop grand nombre d'informations avec les plateformes d'analyse tierces, nous avons supprimé l'option **Envoyer tous les événements (à l'exclusion des désinstallations et des sessions)** pour ces plateformes, depuis mars 2019.Les plateformes d'analyse configurées avant cette date conservent cette option de configuration.

**Pour ajouter manuellement des événements :**

1. Cliquez sur **Ajouter un événement**.
2. Sélectionnez les options de postback :
   * **Évènement AppsFlyer**: sélectionnez un événement dans la liste des événements de votre app.
   * **pour les utilisateurs de**: sélectionnez l'<Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#for-users-from">option d'envoi</Anchor> pour l'événement.
   * **incluant**: sélectionnez [les données à inclure](/docs/in-app-event-postback-configuration#données-à-inclure-dans-les-postbacks) dans le postback.
3. Répétez cette procédure pour d'autres événements.

![send_postbacks_as_is_en-us.png](https://files.readme.io/cc6b2bb1a381d88add035b9f369b0ba68dee8744aa3c2ee2f8f6f054b365a0dd-33379684962705.png)

**Pour envoyer tous les événements :**

1. Envoyez tous les événements **(à l’exclusion des désinstallations et des sessions)**.
2. Sélectionnez les options de postback :  
   * **pour les utilisateurs de**: sélectionnez [l'option d'envoi](/docs/in-app-event-postback-configuration#options-pour-lenvoi-de-postbacks) pour l'événement.
   * **incluant** : sélectionnez [les données à inclure](/docs/in-app-event-postback-configuration#données-à-inclure-dans-les-postbacks) pour tous les événements dans le postback.

![send_postbacsk_as_is_no_mapping.png](https://files.readme.io/458ca832d4176ccd306236cf10f211499e841dc9f550558987dff3ee683bd2d1-33379700651665.png)

</Accordion>

Pour plus d'informations sur le mappage des événements, voir les <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">postbacks d'événements in-app</Anchor>.

<div id="options-for-sending-postbacks" />

### Options pour l'envoi de postbacks

Pour chaque événement, vous pouvez choisir dans quel cas envoyer les postbacks (dans la fenêtre de postback) :

* **Ce partenaire uniquement** : envoi de postbacks uniquement lorsque l'événement est attribué à ce partenaire, c'est-à-dire lorsque l'utilisateur qui l'effectue provient de ce partenaire.
* **Toutes les sources média, y compris organiques** : envoi de postbacks pour les événements attribués à n'importe quel partenaire, ainsi que pour les événements organiques (soit tout utilisateur qui réalise l'événement depuis n'importe quelle source média).

<div id="data-to-include-in-the-postbacks" />

### Données à inclure dans les postbacks

Vous pouvez choisir le type de données d'événement qui sera partagé avec le réseau publicitaire dans le postback. Sélectionnez l'une des options suivantes :

* **Sans valeur et sans revenu** : envoyez uniquement l'événement, sans aucun paramètre (valeur ou revenu).
* **Avec valeurs et sans revenu** : envoyez tous les paramètres **à l'exception** de la valeur du revenu.
* **Avec valeurs et avec revenus** : envoyez tous les paramètres de l’événement, **y compris** la valeur du revenu (si incluse dans l’événement).

Nous vous conseillons de partager les revenus si vous souhaitez que les réseaux publicitaires optimisent vos campagnes et en améliorent les résultats. Le partage des revenus n'est pas obligatoire. Veillez à activer le partage des revenus uniquement pour les événements dont la valeur `af_revenue` est définie. Dans le cas contraire, les réseaux publicitaires reçoivent des événements sans valeur de revenus.

Dans les postbacks, `af_revenue` et `af_currency` sont inscrits en dehors du JSON event\_value en tant que **monetary** et **currency** et peuvent être envoyés séparément. Exemple de structure de postback `: https://appsflyer.com/push?event_value=(event-value)&monetary=(monetary)&content_id=(af_content_id)`

**Remarque** : Lorsque l'on choisit l'option **Pas de valeurs et pas de revenus** ou **Valeurs et pas de revenus**, les paramètres respectifs sont masqués par la mention N/A.

<div id="h_01HBZCRNKGBEDSBZEY87KYQ60G" />

> 📄 **Exemple**
>
> Un marketeur envoie un événement d'achat avec la valeur d'événement suivante :
> `{af_revenue: 50.87, af_currency: USD, af_level=2,af_receipt_id=57601333}`
>
> Le tableau ci-dessous montre comment les paramètres sont envoyés :
>
>
>
> | Nom du champ | event\_value | monétaire | devise |
> | --- | --- | --- | --- |
> | **Pas de valeurs et pas de revenus** | N/A | N/A | S/O |
> | **Valeurs et pas de revenus** | `{"af_currency":"N/A","af_content_id":"1234567",`<br /><br />`"af_revenue":"N/A","af_content_type":"category_a"}`<br /><br />`&monetary=N/A&content_id=1234567` | N/A | S/O |
> | **Valeurs et revenus** | `"af_currency":"USD","af_content_id":"1234567",`<br /><br />`"af_revenue":200,"af_content_type":"category_a"}`<br /><br />`&monetary=1.856918&content_id=1234567` | 50.87 | USD |

<div id="conditional-in-app-event-postbacks" />

### Postbacks conditionnels d'événements in-app

Filtrez les postbacks d'événements in-app à l'aide de plusieurs conditions qui peuvent être associées à différents événements. Seuls les événements répondant aux conditions de filtrage sont envoyés aux partenaires, y compris les SRN et les partenaires analytiques. Utilisez cette fonction pour :

* Optimiser la segmentation, la personnalisation et la fidélisation des utilisateurs
* Minimiser les données
* Protéger la vie privée des utilisateurs

<div id="h_01HBZCRNKHRTMHP3JPFVCS8D6N" />

> 📄 **Exemple**
>
> Le marketeur d'une application de jeu souhaite optimiser les campagnes diffusées par un réseau publicitaire, mais uniquement pour les utilisateurs qui passent le niveau 10 ou le niveau 50, ou pour les utilisateurs qui dépensent 3 dollars pour des achats dans l'application.
>
> [![in_app_event_condition__1_.png](https://files.readme.io/0f179d79fdb544f209f901370f7c0103e0fc5dbeda2554268b2a06a272a6b8b9-14979535388433.png)](https://files.readme.io/0f179d79fdb544f209f901370f7c0103e0fc5dbeda2554268b2a06a272a6b8b9-14979535388433.png)
>
> **Les conditions de cet événement sont définies de cette façon :**
>
> * Si le ***niveau*** est égal à ***10***, mapper à ***`fb_mobile_level_acheived`***
>   Sinon **(OU**),
> * Lorsque ***le niveau*** est égal à ***50***, mapper à ***`fb_mobile_level_acheived`***
>   Sinon **(OU**),
> * Lorsque ***le coût*** est égal à ***3***, mapper à ***`fb_mobile_purchase`***

**Pour définir les conditions d'un événement :**

1. Sur la page d'intégration du partenaire, <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">définissez et mappez</Anchor> les événements in-app à envoyer au partenaire.
2. Cliquez sur l'icône Ajouter une condition![image.png](https://files.readme.io/8e650caf6472b316bd49bc25c45cc4c9d63b67770dd1c920fb873118b82ff868-17023682954385.png) de l'événement requis.
3. Saisissez les champs de condition, tels qu'ils apparaissent dans la <Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview#event-values">valeur de l'événement</Anchor>:
   * Nom de la propriété
   * valeur
   * Événement partenaire à associer à la condition (à l'aide de l'une des [options de mappage](/docs/in-app-event-postback-configuration#les-méthodes-de-mappage) suivantes)
4. Vous pouvez ajouter d'autres conditions, mais veillez à saisir d'abord tous les champs de la condition existante.
5. Cliquez sur **Enregistrer l'intégration**.

<div id="considerations" />

#### Attention

Lors de la configuration des conditions, assurez-vous que les points suivants sont respectés pour que l'événement soit envoyé au partenaire :

<div id="condition-structure" />

<Accordion title="Structure d'état">

* La propriété et la valeur de la condition doivent toutes deux correspondre aux données de l'événement.
* Actuellement, les conditions ne peuvent être définies que comme égales.
* Les structures complexes comme les tableaux ne sont pas prises en charge.

</Accordion>

<div id="multiple-conditions-for-an-event" />

<Accordion title="Conditions multiples pour un événement">

* Le nombre maximum de conditions par événement est de 5.
* Au moins une condition doit être remplie pour que le postback soit envoyé, mais une seule condition est exécutée.
* Chaque condition est vérifiée par ordre d'apparition - la première condition remplie est exécutée.
* Chaque condition est mappée séparément. Le nom de l'événement partenaire devient **Basé sur les conditions**.
* Plusieurs conditions peuvent avoir la même propriété ou la même valeur, mais deux conditions ne peuvent avoir à la fois la même propriété et la même valeur.
* Plusieurs conditions peuvent être associées à un même événement.

</Accordion>

<div id="note-9" />

> 📘 **Note**
>
> * Nous vous recommandons de tester cette fonctionnalité avec une application de test, ou pour des événements mineurs afin de comprendre son impact sur l'optimisation de la campagne.
> * Pour voir le <Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview">contenu du postback</Anchor>, vous pouvez télécharger le rapport de postback des données brutes.

<div id="editing-multiple-events" />

### Modification de plusieurs événements

Lors du mappage des événements, les valeurs des champs **Utilisateurs de**  et **Utilisateursinclus** peuvent être modifiées pour plusieurs événements en une seule action.

**Pour modifier plusieurs évènements :**

1. Sélectionnez les événements à mettre à jour.
2. Cliquez sur **Actions groupées**.
3. Sélectionnez le nouveau paramètre à appliquer à tous les événements sélectionnés :
   * **pour les utilisateurs de** (choisir une seule option)
     * Ce partenaire uniquement
     * Toutes les sources média, y compris organiques
   * **incluant** (choisir une seule option)
     * Pas de données (par défaut)
     * Valeurs sans revenus
     * Valeurs et revenus

[![In-app_event_postbacks_en-us.png](https://files.readme.io/559265d0e12e9e2ef62e0a19c5833465ee758821654877cffa4e75f6ff3f99b9-33379700657169.png)](https://files.readme.io/559265d0e12e9e2ef62e0a19c5833465ee758821654877cffa4e75f6ff3f99b9-33379700657169.png)

<div id="custom-events" />

### Événements personnalisés

La liste des événements disponibles pour le mappage ne comprend que les événements qui ont déjà été transmis à AppsFlyer par le SDK ou les évènements de serveur à serveur.Si l'événement que vous souhaitez mapper n'apparaît pas dans la liste déroulante, il peut y avoir différentes explications :

* Aucun utilisateur n'a encore provoqué cet événement
* La dernière fois que l'événement s'est produit, c'était il y a plus de deux semaines
* Vous avez une longue liste d'événements actifs

**Dans l'un ou l'autre de ces cas, pour associer l'événement à l'ID du partenaire :**

1. Saisissez le nom de l'événement.
2. Cliquez sur **Créer personnalisé**

   [![In-app_event_postbacks_en-us.png](https://files.readme.io/73ad7c6a34a292056ddd750901ce1e0a2975d6ce6f235610f0bee28aecd05d53-7901768117905.png)](https://files.readme.io/73ad7c6a34a292056ddd750901ce1e0a2975d6ce6f235610f0bee28aecd05d53-7901768117905.png)
3. Mappez l'événement à l'identifiant du partenaire.
4. Cliquez sur **Enregistrer l'intégration** pour vous assurer que le mappage est sauvegardé.

<div id="note-10" />

<div id="tip" />

<div id="note-8" />

<div id="share-revenue" />

> 📘 **Note**
>
> * Lorsqu'un événement personnalisé est ajouté à un certain partenaire, l'événement est ajouté à la liste des événements pour tous les partenaires. Cela signifie que vous pouvez voir cet événement dans la liste déroulante des événements de n'importe quel partenaire.
> * Voir les <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview#tips">conseils</Anchor> et les <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview#limitations">limites</Anchor> pour définir les noms et les paramètres des événements.

**Agences et réseaux publicitaires :**

* Impossible d'ajouter des événements personnalisés
* Ne peut visualiser et/ou cartographier des événements qu'après que le marketeur a ajouté l'événement et accordé les <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#permissions-tab">autorisations</Anchor> nécessaires.

<div id="event-mapping-by-ad-networks" />

## Le mappage d'événements par les réseaux publicitaires

Les marketeurs peuvent également permettre aux réseaux publicitaires de mapper par eux-mêmes les événements et de désactiver les postbacks. Pour que ce soit possible, le marketeur doit accorder certaines autorisations au réseau publicitaire :

1. Sur la page **Intégrations actives**, recherchez le partenaire auquel vous souhaitez donner une autorisation.
2. Dans l'onglet Permissions, **activez** **Autoriser à configurer les postbacks d'événements in-app**.

![adnetwork-permissions-postbacks.png](https://files.readme.io/f8369f6a0a60d3c48ef66b51f61b3c81f00f6c88511f5f69b2c927788a64f018-33379700661265.png)

Une fois que le réseau publicitaire a reçu les autorisations, il peut mapper les événements en suivant les instructions qui apparaissent dans la section [Tapez l'ID d'évènement dans le champ de texte](/docs/in-app-event-postback-configuration#les-méthodes-de-mappage).

<div id="event-mapping-by-agencies" />

## Le mappage des événements par les agences

Les marketeurs peuvent autoriser les agences à configurer les postbacks d'événements in-app.

**Pour autoriser l'agence à configurer les postbacks in-app :**

1. Trouvez l'agence sur la page des **intégrations actives**.
2. Indiquez si l'agence peut partager la totalité des événements, ou seulement ceux attribués au réseau publicitaire spécifique.
3. Précisez si l'agence est autorisée à envoyer des revenus d'événement.
4. Sélectionnez les événements précis que l'agence est autorisée à partager.

![agency-events.png](https://files.readme.io/194b9a18f7721d4cc159f6385140cbb989108b70110e2e0d0f29f90d6115b10a-33379684973969.png)

<div id="h_01HDP3XHBPA5GZEVERMBN43JH0" />

<div id="note-11" />

> 📄 **À consulter également**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview">Les événements in-app riches : aperçu</Anchor>
> * <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-event-structure">Événements in-app riches—Structure des événements</Anchor>

<div data-zendesk-anchors="overview=pr%C3%A9sentation h_01HE0FQ1AB6NQCTKFTDW22SRYC=pr%C3%A9sentation postback-inapp-event-selection=s%C3%A9lection-du-postback-d%C3%A9v%C3%A9nement-in-app h_01HBZCRNKGH1PAK8RC846PPRTS=s%C3%A9lection-du-postback-d%C3%A9v%C3%A9nement-in-app h_01HBZCRNKGQTJ4VJ00TVTS14N2=note inapp-event-postback-window=fen%C3%AAtre-des-postbacks-d%C3%A9v%C3%A9nements-in-app h_01HBZCRNKGS71QGK5506N07K84=fen%C3%AAtre-des-postbacks-d%C3%A9v%C3%A9nements-in-app default-postback-window=fen%C3%AAtre-de-postback-par-d%C3%A9faut h_01HBZCRNKGV5CREN5K0RBDMBH6=fen%C3%AAtre-de-postback-par-d%C3%A9faut h_01HBZCRNKGVXN233AFFHG42NW9=note-1 who-can-configure-postback-windows=qui-peut-configurer-les-fen%C3%AAtres-de-postback- h_01HBZCRNKG7AECFSBXV2WDD9AR=qui-peut-configurer-les-fen%C3%AAtres-de-postback- event-mapping=le-mappage-d%C3%A9v%C3%A9nement h_01HBZCRNKG7SZ4T41BY60BAJZN=le-mappage-d%C3%A9v%C3%A9nement h_01HBZCRNKGT64TE2XYK9VS4ATD=note-2 mapping-methods=les-m%C3%A9thodes-de-mappage h_01HBZCRNKG4EF9MSY696SD5VQ9=les-m%C3%A9thodes-de-mappage h_01HBZCVAGPSNDJMWRWENEP45N7=note-3 enter-the-partner-event-id=h_c513e6d4-d46f-4070-a98d-1888a5ea939d h_01HBZCRNKG1E63DZRSDWTB8CJN=note-4 h_01HBZCRNKGWQBNY8RP4MTW3DXV=select-an-event-id-from-the-list h_01HBZCRNKG4981T00N70X2GP0J=send-events-as-they-are-unmapped h_01HBZCRNKGXJ683VHFTE277ER9=note-5 options-for-sending-postbacks=options-pour-lenvoi-de-postbacks h_01HBZCRNKG1VN7E6TVCPDW7M73=options-pour-lenvoi-de-postbacks data-to-include-in-the-postbacks=donn%C3%A9es-%C3%A0-inclure-dans-les-postbacks h_01HBZCRNKGESY50NSZGTVPT25M=donn%C3%A9es-%C3%A0-inclure-dans-les-postbacks h_01HBZCRNKGBEDSBZEY87KYQ60G=exemple conditional-inapp-event-postbacks=postbacks-conditionnels-d%C3%A9v%C3%A9nements-in-app h_01HBZCRNKG5X3B2NJZZP6ER2CX=postbacks-conditionnels-d%C3%A9v%C3%A9nements-in-app h_01HBZCRNKHRTMHP3JPFVCS8D6N=exemple-1 considerations=attention h_01HBZCRNKHBR57YVHZQP7NJBAP=attention h_01HBZCRNKHJGBYNP9JN24CQ3CC=condition-structure h_01HBZCRNKH1R0FR61C6TA0MCTN=multiple-conditions-for-an-event h_01HBZCRNKHF6TFP0N302D7DCMD=note-6 editing-multiple-events=modification-de-plusieurs-%C3%A9v%C3%A9nements h_01HBZCRNKHHD3WC4GTJT9NSJ4C=modification-de-plusieurs-%C3%A9v%C3%A9nements custom-events=%C3%A9v%C3%A9nements-personnalis%C3%A9s h_01HBZCRNKH754PANWSZ4FMXJVQ=%C3%A9v%C3%A9nements-personnalis%C3%A9s h_01HBZCRNKH4PVR3FEMTMERW3M1=note-7 event-mapping-by-ad-networks=le-mappage-d%C3%A9v%C3%A9nements-par-les-r%C3%A9seaux-publicitaires h_01HBZCRNKH1GCZY17R04WTZ0MQ=le-mappage-d%C3%A9v%C3%A9nements-par-les-r%C3%A9seaux-publicitaires event-mapping-by-agencies=le-mappage-des-%C3%A9v%C3%A9nements-par-les-agences h_01HBZCRNKHHF3E6CZNQQG0Q4VS=le-mappage-des-%C3%A9v%C3%A9nements-par-les-agences h_01HDP3XHBPA5GZEVERMBN43JH0=%C3%A0-consulter-%C3%A9galement" />
