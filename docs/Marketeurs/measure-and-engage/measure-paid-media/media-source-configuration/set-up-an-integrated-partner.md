---
title: Configurer un partenaire intégré
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2021-11-08T08:02:46Z'
  edited_at: '2023-11-24T14:22:13Z'
  id: 4410395957521
  locale: fr
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/fr/articles/4410395957521
---
> **En bref :** activez la mesure d'attribution, envoyez des postbacks aux partenaires et activez différentes fonctions d'intégration en configurant la connexion partenaire avec AppsFlyer.

## Présentation

AppsFlyer s’intègre avec des partenaires, des sources média et des plateformes tierces via API. Cet article contient les instructions pour activer et configurer l'intégration, y compris la génération de liens d'attribution pour les ad networks non-SRN.

* Ce guide ne concerne pas les SRN. Consultez l'article consacré aux <Anchor target="_blank" href="/marketers/fr/docs/self-reporting-networks-srns">SRN</Anchor>.
* Certains réseaux publicitaires ont des articles dédiés.
* Avant de procéder à la configuration, vous devez contacter le partenaire et ouvrir un compte chez lui.

<div id="partner-types-in-the-ecosystem" />

<Accordion title="Types de partenaires présents dans l'écosystème">

L'image qui suit présente les différents types de partenaires qui forment l'écosystème d'attribution.

[![Ecosystem.jpg](https://files.readme.io/9377db3a6a6effd7ff8139994e2e8ed8dea04331588b5df2a31f1acd643afd9f-4411031173265.jpg)](https://files.readme.io/9377db3a6a6effd7ff8139994e2e8ed8dea04331588b5df2a31f1acd643afd9f-4411031173265.jpg)

**Lecture connexe** : <Anchor target="_blank" href="https://www.appsflyer.com/performance-index/">Indice de performance AppsFlyer</Anchor> qui classe les meilleures sources média mobiles par catégorie et région.

| Type de partenaire | Description |
| --- | --- |
| Réseaux publicitaires | Lancent des campagnes en votre nom. |
| Agences | Leur expertise vous permet d'obtenir des utilisateurs de haute qualité lorsque vous lancez des campagnes en votre nom. Vous pouvez choisir d'avoir une relation transparente ou non. |
| Partenaires marketing | Les partenaires marketing sont spécialisés dans la collaboration avec certains réseaux publicitaires. Exemples : partenaires marketing Facebook, partenaires marketing Apple Search Ads, partenaires publicitaires officiels Twitter |
| Réseaux de retargeting | Ad networks spécialisés dans l'exécution de campagnes de retargeting. |
| Plate-formes tierces | Fournissent des services BI comme les plateformes d'analyse et d'automatisation marketing. |
| Attribution TV | Partenaires permettant une attribution plus précise des nouvelles installations aux publicités TV diffusées. |
| Détection des fraudes | Les systèmes anti-fraude de tierces parties qui ne sont pas inclus dans la solution anti-fraude AppsFlyer Protect360. |

</Accordion>

<div id="partners-in-the-marketplace" />

<Accordion title="Partenaires du marketplace">

Tous les partenaires, sources média et autres plateformes intégrées à AppsFlyer apparaissent sur la page <Anchor target="_blank" href="/marketers/fr/docs/partner-integrations">marketplace</Anchor>. Vous pouvez y retrouver vos partenaires <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">actifs et inactifs</Anchor>, et rechercher de nouveaux partenaires à qui vous connecter.

**Pour rechercher et filtrer tous les partenaires, sources média ou autres plateformes sur le <Anchor target="_blank" href="/marketers/fr/docs/partner-integrations">marketplace</Anchor> :**

* Dans AppsFlyer, allez dans **Configuration** et ouvrez **Marketplace des partenaires**.  Vous pouvez utiliser les différents <Anchor target="_blank" href="/marketers/fr/docs/partner-integrations#filtrer-la-liste-des-partenaires">filtres</Anchor> de recherche.

#### Inviter de nouveaux partenaires dans AppsFlyer

Si le partenaire avec lequel vous travaillez n'est pas encore intégré à AppsFlyer, vous pouvez lui <Anchor target="_blank" href="/marketers/fr/docs/partner-integrations#inviter-de-nouveaux-partenaires-dans-appsflyer">envoyer un lien d'invitation</Anchor>.

</Accordion>

<div id="your-integrated-partners" />

<Accordion title="Vos partenaires intégrés actifs">

La page <Anchor target="_blank" href="/marketers/fr/docs/partner-integrations#intégrations-actives">Integrations actives</Anchor> du Marketplace partenaire affiche l'ensemble de vos partenaires intégrés <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">actifs</Anchor>. Sur cette page, vous pouvez obtenir des informations sur le partenaire et gérer l'intégration.

> 📘 **Note**
>
> La liste des partenaires actifs qui s'affiche sur la page **Intégrations actives** varie en fonction de l'app sélectionnée (c'est à dire la dernière app que vous avez sélectionnez avant d'ouvrir le Marketplace).Vous pouvez voir quels partenaires sont connectés aux différentes apps en cliquant sur l'app en haut à gauche, puis en en sélectionnant une autre.

**Pour voir tous vos partenaires actifs :**

* Dans AppsFlyer, allez dans **Configuration** et ouvrez **Intégrations actives**.

Découvrez <Anchor target="_blank" href="/marketers/fr/docs/partner-integrations#découvrez-ce-que-vous-pouvez-faire-depuis-la-page-intégrations-actives">ce que vous pouvez faire depuis la page Intégrations actives</Anchor>.

</Accordion>

<div id="about-the-integrated-partner-page" />

<Accordion title="À propos de la page de configuration du partenaire">

La page est structurée comme suit :

* **En-tête**, qui contient :
  * Nom du partenaire
  * Lien vers un article dédié à un partenaire. Si aucun article dédié n'existe, cet article s'affiche.
  * Statut de l'intégration
  * App sélectionnée
* **Onglets de paramétrage** : les onglets disponibles dépendent du type de partenaire et des fonctionnalités prises en charge.
* **Pied de page** :
  * **Retour à la liste**: permet de revenir à la liste des intégrations actives en utilisant les options de filtrage sélectionnées précédemment.
  * **Message de statut :** état actuel des données de l'onglet (ex : sauvegarde, sauvegardé, erreur, modifications non sauvegardées).
  * **Annuler les modifications :** annule les dernières modifications sans les enregistrer.
  * **Sauvegarder :** Sauvegarde les paramètres de l'onglet en cours uniquement.

#### Onglets paramètres applicables selon le type de partenaire

<table><thead><tr><th> </th><th colspan="2">Onglet paramètres</th><th> </th></tr><tr><th>Type de partenaire</th><th>Intégration </th><th>Autorisations</th><th>Remarques</th></tr></thead><tbody><tr><td>Source média</td><td>Y</td><td>Y</td><td><p><strong>Des onglets supplémentaires sont disponibles</strong>: coût, revenus publicitaires, lien d'attribution</p><p>Sont inclus : les réseaux publicitaires, les réseaux d'affiliation, les éditeurs directs, la publicité programmatique, les réseaux publicitaires nationaux chinois et les réseaux de retargeting.<br/>Pour les SRN, l'onglet du lien d'attribution est vide.</p></td></tr><tr><td>Agence</td><td>N</td><td>Y</td><td>Agences autonomes qui ne fonctionnent pas comme des réseaux publicitaires </td></tr><tr><td>Plateformes tierces</td><td>Y</td><td>N</td><td>Plateformes d'automatisation des solutions d'analyse ou du marketing</td></tr><tr><td>Partenaire marketing </td><td>Y</td><td>N</td><td> </td></tr></tbody></table>

</Accordion>

## Configurer un partenaire (non-SRN)

Pour accéder aux paramètres et configurer vos campagnes avec le partenaire :

1. Localisez votre partenaire et sélectionnez-le, soit <Anchor target="_blank" href="/marketers/fr/docs/partner-integrations#gérer-les-intégrations-existantes">depuis le marketplace</Anchor>, soit sur la page **Configuration** > **Intégrations actives.**
2. Complétez les paramètres par onglet, selon vos besoins. Consultez les sections suivantes.

> 📘 **Note**
>
> L'étape [Paramètres généraux](/docs/set-up-an-integrated-partner#d) de l'onglet Intégration est **obligatoire** pour tous les partenaires. Vous devez également compléter l'onglet **Lien d'attribution** pour les réseaux publicitaires non-SRN. Les autres filtres sont facultatifs.

<div id="integration-tab" />

<Accordion title="Onglet Intégration">

Les intégrations de partenaire varient d'un partenaire à l'autre et peuvent nécessiter une ou plusieurs des options détaillées dans cette section. Il existe certaines différences entre les paramètres iOS et Android.

![set_up_an_integrated_partner.png](https://files.readme.io/441ddfcd784a000099ae75acdb234d32bfe75ab598a34a88c7f9ed651fe8f7ec-15520850610449.png)

Veuillez renseigner les sections tel que demandé.

#### Sections concernant l'intégration

Le tableau suivant présente les différentes sections de la page d'intégration. Certaines sections sont accessibles à toutes les intégrations, d'autres sont spécifiques à chaque intégration.

<Table>
  <thead>
    <tr>
      <th>
        Section
      </th>
      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="a"></span>
        Activation du partenaire
      </td>
      <td>
        Avant de pouvoir partager les liens d'attribution avec un partenaire, vous devez sélectionner **Activer le partenaire** puis renseigner les sections de l'onglet Intégration.

        * N'utilisez jamais **Activer le partenaire** pour suspendre ou désactiver une attribution de campagne.
        * En désactivant l'intégration d'un partenaire vous **risquez d’endommager de manière irréversible vos campagnes en cours**.
        * <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">En savoir plus sur l'activation du partenaire</Anchor> et les effets en cas de désactivation de ce dernier.

        **Pour activer un partenaire intégré** :

        1. Dans AppsFlyer, rendez-vous dans **Configurations** > **Intégrations actives**.
        2. Localisez le partenaire et sélectionnez-le. Vous êtes envoyé sur la page de configuration du partenaire.
        3. Cochez **<Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">Activer le partenaire</Anchor>.**
        4. Cliquez sur **Enregistrer l'intégration**.
        5. [Facultatif] Pour permettre au partenaire de <Anchor target="_blank" href="/marketers/fr/docs/manage-data-access-permissions">consulter les données qui lui sont attribuées</Anchor>, vous devez [activer les autorisations de réseau publicitaire](/docs/set-up-an-integrated-partner#autorisations-pour-le-réseau-publicitaire) dans l'onglet [Autorisations](/docs/set-up-an-integrated-partner#permissions-tab).
      </td>
    </tr>
    <tr>
      <td><span id="b"></span>
        Protection de la vie privée avancée
      </td>
      <td>
        Pour les apps IOS uniquement :lorsque **la confidentialité avancée (pour iOS 14.5 et +)** est activée, vous pouvez <Anchor target="_blank" href="/marketers/fr/docs/apply-aggregated-advanced-privacy-framework">décider quelles données sont partagées</Anchor> avec le partenaire via les postbacks et les rapports, ce qui restreint le partage des identifiants utilisateur avec le partenaire. Notez que lorsque l'option <Anchor target="_blank" href="/marketers/fr/docs/apply-aggregated-advanced-privacy-framework">Confidentialité avancée agrégée</Anchor> est activée dans les paramètres de l'app, l'option **Confidentialité avancée (pour iOS 14.5 et +)** est activée et verrouillée.
      </td>
    </tr>
    <tr>
      <td><span id="c"></span>
        ID de transaction
      </td>
      <td>
        Pour les apps IOS uniquement : lorsque l'option **Partager l'ID de transaction SKAN** est activée, vous autorisez AppsFlyer à <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">partager l'ID de transaction des postbacks SKAdNetwork</Anchor> avec le partenaire. En conséquence, le partenaire aura la possibilité de décoder vos valeurs de conversion SKAdNetwork.
      </td>
    </tr>
    <tr>
      <td><span id="d"></span>
        Paramètres généraux
      </td>
      <td>
        **ID du partenaire—Identifiants** Certains partenaires nécessitent d'avoir des identifiants pour que AppsFlyer puisse les intégrer. Chez les partenaires, cet identifiant correspond à l'ID d'app, ID de compte, ID d'utilisateur ou ID de réseau. Si cet élément vous est demandé, récupérez l'identifiant dans le tableau de bord du partenaire puis saisissez-le dans le champ correspondant.
      </td>
    </tr>
    <tr>
      <td><span id="e-install-attribution"></span>
        Attribution d'installation
      </td>
      <td>
        Lorsque l'option **Attribution d'installation** est activée, les nouvelles installations des utilisateurs ayant vu la publicité sans avoir cliqué dessus sont attribuées.
      </td>
    </tr>
    <tr>
      <td><span id="e-re-engagement-attribution"></span>
        Attribution du ré-engagement
      </td>
      <td>
        Activer et configurer les fenêtres rétrospectives pour pouvoir attribuer les réengagements de vos utilisateurs existants. Pour les non-SRN, ce paramètre est disponible soit dans l'onglet Intégration, soit dans l'onglet Lien d'attribution.

        * **Attribution post-vue des réengagements :** lorsque cette option est activée, les réengagements des utilisateurs qui ont visualisé votre publicité mais sans cliquer dessus, sont attribués.
        * **Attribution post-clic des réengagements :** lorsque cette option est activée, les réengagements des utilisateurs qui ont cliqué sur votre publicité sont attribués.
      </td>
    </tr>
    <tr>
      <td><span id="ignore-active-users"></span>
        Ignorer les utilisateurs actifs pour le retargeting (SRN)
      </td>
      <td>
        Lorsque **l'attribution de réengagement** est activée, l'option **Ignorer les utilisateurs actifs pour le retargeting** (disponible pour les <Anchor target="_blank" href="/marketers/fr/docs/self-reporting-networks-srns">SRN</Anchor>) est activée. Lorsque cette option est activée et qu'une **fenêtre d'inactivité** est définie, les conversions de retargeting des utilisateurs qui étaient actifs durant la fenêtre d'inactivité sont ignorées, et elles ne sont pas enregistrées dans AppsFlyer.
      </td>
    </tr>
    <tr>
      <td><span id="e"></span>
        Attribution multiplateforme
      </td>
      <td>
        Si l'option **Priorité d'attribution multiplateforme égale** est activée, les impressions multiplateforme ayant lieu sur la période sélectionnée auront la même priorité d'attribution.
      </td>
    </tr>
    <tr>
      <td><span id="f-preload-attribution"></span>
        Attribution de préchargement
      </td>
      <td>
        Lorsque **l'Attribution de préchargement** est activée, les installations sont attribuées aux <Anchor target="_blank" href="/marketers/fr/docs/measure-preload-campaigns-with-google-play-install">campagnes de préchargement</Anchor>. Définissez la **fenêtre rétrospective de préchargement** pour déterminer combien de temps après l'activation de l'appareil une installation de pré-chargement peut être attribuée au partenaire.
      </td>
    </tr>
    <tr>
      <td><span id="f-preload-equal-attribution-priority"></span>
        Priorité d'attribution égale pour le préchargement
      </td>
      <td>
        Lorsque la fonction **Priorité d'attribution égale pour le préchargement** est activée, la <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-attribution-model#méthodes-dattribution">priorité d'attribution</Anchor> pour l'engagement de préchargement pendant la fenêtre rétrospective est la même que celle des clics déterministes.
      </td>
    </tr>
    <tr>
      <td><span id="advanced-data-sharing"></span>
        Partage avancé des données
      </td>
      <td>
        Lorsque le **partage avancé des données** est activé, des données supplémentaires sont partagées avec le partenaire via le lien d'attribution.  
        **Remarque :** Cette option de partage est différente du <Anchor target="_blank" href="/marketers/fr/docs/meta-ads-integration-setup#aem-data-sharing">partage des données AEM Meta ads avancé</Anchor>.
      </td>
    </tr>
    <tr>
      <td><span id="f"></span>
        Postbacks par défaut
      </td>
      <td>
        Lorsque l'intégration du partenaire est activée, AppsFlyer envoie au partenaires des postbacks par défaut pour les actions que l'utilisateur initie avant de lancer l'app, comme les installations, installations rejetées et réengagements.

        > 📘 **Note**
        >
        > * Les événements rejetés sont les événements d'app qui ont été bloqués par <Anchor target="_blank" href="/marketers/fr/docs/protect360-anti-fraud-guide">Protect360</Anchor>, ou bien qui ont été jugés non conformes à la validation de cible. Dans le cas d'événements rejetés, vérifiez auprès du partenaire qu'il a bien activé l'intégration de l'événement rejeté auprès d'AppsFlyer.
        > * Les partenaires qui n’effectuent pas d’attribution (tels que les plateformes tierces) reçoivent le postback par défaut uniquement pour les installations. Les postbacks d’attribution sont envoyés au partenaire attribué.

        **Pour configurer les postbacks par défaut du partenaire**, définissez la source utilisateur pour laquelle les postbacks sont envoyés :

        * **Ce partenaire uniquement** : envoi de postbacks uniquement lorsque l'événement est attribué à ce partenaire, c'est-à-dire lorsque l'utilisateur concerné provient de ce partenaire.  
          **Remarque :** dans les cas suivants, les postbacks par défaut sont toujours définis sur **Ce partenaire uniquement** :
          * Installations rejetées
          * Agences (avec [autorisations](/docs/set-up-an-integrated-partner#autorisations-pour-lagence))
        * **Toutes les sources média, y compris organiques** : envoi de postbacks pour les événements attribués à n'importe quel partenaire ainsi que pour les événements organiques (soit tout utilisateur qui réalise l'événement depuis n'importe quelle source média).
        * **Désactivé** :ne pas envoyer de postbacks par défaut à ce partenaire.
      </td>
    </tr>
    <tr>
      <td><span id="g"></span>
        <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration">Postbacks d'événements in-app</Anchor>
      </td>
      <td>
        <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#le-mappage-dévénement">Mappage</Anchor> des événements AppsFlyer avec le partenaire via les postbacks. Si l'envoi de postback est activé, il inclut les événements in-app rejetés (événements bloqués par Protect360 ou événements jugés non conformes par les règles de validation de cible).

        **Pour configurer les postbacks d'événement in-app :**

        1. Définissez **l'ID du partenaire** (si nécessaire).
        2. Activez **Postbacks d'événement in-app.**
        3. Si nécessaire, configurez la **fenêtre de postback d'évènement in-app**, (en savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#fenêtre-des-postbacks-dévénements-in-app">la configuration de la fenêtre de postback d'événement in-app</Anchor>).
        4. Cliquez sur **Ajouter un événement** pour ajouter à la liste un SDK ou un événement de serveur à serveur.
        5. Complétez les paramètres requis selon la <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#les-méthodes-de-mappage">méthode de mappage</Anchor>.
        6. [Facultatif] Cliquez sur <Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/e2543cb26e0cc02f4840040721376ae88a4015a24ac1fc271264e3965560c1f9-4413022777105.png" width="30px" /> pour <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#postbacks-conditionnels-dévénements-in-app">définir les conditions</Anchor> d'envoi de certains événements in-app au partenaire.

        | Nom du paramètre | Description |
        | --- | --- |
        | <span id="appsflyer-event"></span>**Événement AppsFlyer** | Le nom de l'événement tel que reçu par AppsFlyer, soit depuis le SDK intégré à votre app, soit depuis les événements de serveur à serveur.  <br />**Astuce** : l'événement que vous recherchez ne s'affiche pas ?<br /><br />* Assurez-vous d'activer l'évènement sur un appareil avec une installation non-organique avant de vérifier à nouveau.<br />* Saisissez-le dans **Événement AppsFlyer** puis cliquez sur **Créer événement personnalisé**. En savoir plus sur le <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#événements-personnalisés">mappage d'événements personnalisés.</Anchor> |
        | <span id="mapped-to-partner-event"></span>**mappé à l’événement partenaire** | Le nom ou l'identifiant unique de chaque événement, tel que défini du côté du partenaire. <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#les-méthodes-de-mappage">Les différentes configurations de mappage</Anchor> sont :<br /><br />* **Champ de texte :** obtenez l'ID d'événement correspondant auprès du partenaire.<br />* **Liste déroulante :** sélectionnez l’événement de partenaire prédéfini le mieux approprié.<br />* **Tel quel** : envoie les événements à l'état brut, sans mappage du nom. |
        | <span id="for-users-from"></span>**pour les utilisateurs de** | Sélectionnez l'option d'envoi pour l'événement :<br /><br />* **Ce partenaire uniquement** : envoi de postbacks uniquement lorsque l'événement est attribué à ce partenaire, c'est-à-dire lorsque l'utilisateur qui l'effectue provient de ce partenaire.<br />* **Toutes les sources média, y compris organiques** : envoi de postbacks pour les événements attribués à n'importe quel partenaire ainsi que pour les événements organiques (soit tout utilisateur qui réalise l'événement depuis n'importe quelle source média). |
        | <span id="including"></span>**Y compris** | Sélectionnez <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#données-à-inclure-dans-les-postbacks">les données d’événement</Anchor> à partager avec le partenaire dans le postback :<br /><br />* **Sans valeur et sans revenu** : envoyez uniquement l'événement, sans aucun paramètre (valeur ou revenu).<br />* **Avec valeurs et sans revenu** : envoyez tous les paramètres **à l'exception** de la valeur du revenu.<br />* **Avec valeurs et avec revenus** : envoyez tous les paramètres de l’événement, **y compris** la valeur du revenu (si incluse dans l’événement). |

        Remarques :

        * Les événements de l'onglet Intégration qui sont mappés pour un partenaire précis s'appliquent à la fois aux postbacks standard et aux <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">postbacks SKAN.</Anchor>
        * Les postbacks sont envoyés aux partenaires en temps réel.
        * Le nom de l'évènement SDK peut être sélectionné ou saisi.  
          Les valeurs saisies peuvent contenir des espaces (tirets du bas) avant ou après le nom de l'évènement. Utilisez les tirets du bas UNIQUEMENT si le nom de l'évènement envoyé par AppsFlyer contient les mêmes tirets du bas.
        * **Attention** : les noms d'évènements sont sensibles à la casse. Pour éviter les incohérences, assurez-vous d'utiliser le bon nom d'événement pour toutes les sources média et versions d'app.
        * Si la section **Postback d'événement in-app** n'apparait pas dans l'onglet **Intégration**, cela signifie que le partenaire n'a pas encore pré-configuré l'enregistrement de ses événements in-app avec AppsFlyer. Le partenaire peut contacter AppsFlyer via le <Anchor target="_blank" href="https://af-static-content.s3.eu-west-1.amazonaws.com/marketplace/static/logo/Help_GIF_Final-min.gif">widget assistant du partenaire</Anchor> pour compléter l'intégration.
        * Pour éviter que les annonceurs ne partagent involontairement un trop grand nombre d'informations avec les plateformes d'analyse tierces, nous avons supprimé l'option **Envoyer tous les évènements (à l’exclusion des désinstallations et des sessions)** pour les plateformes d'analyse, et ce depuis mars 2019. Les plateformes tierces qui ont configurées avant cette date maintiennent quant à elles cette option.

        Lectures connexes :

        * Configuration des <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration">postbacks d'événements in-app</Anchor>
        * Configuration des <Anchor target="_blank" href="/marketers/fr/docs/roi360-guide-ad-revenue-attribution#ad-revenue-event-postbacks-for-ad-networks">postbacks d'événements des revenus publicitaires</Anchor>
      </td>
    </tr>
    <tr>
      <td><span id="h"></span>
        Enregistrer l'intégration
      </td>
      <td>
        Cliquez sur **Enregistrer l'intégration** une fois les modifications apportées.
      </td>
    </tr>
    <tr>
      <td><span id="i"></span>
        Connecter plus d'apps (facultatif)
      </td>
      <td>
        Une fois l'intégration enregistrée, restez sur la page de configuration pour intégrer plus d'apps avec le partenaire.

        1. Dans le coin supérieur gauche, sous le nom du partenaire, cliquez sur le nom de l’app pour ouvrir la liste des apps.
        2. Sélectionnez une autre app dans la liste déroulante.
        3. Répétez les différentes étapes d’intégration pour l’app sélectionnée.
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Onglet Lien d'attribution">

Générez et enregistrez les liens d'attribution pour l'utilisation des réseaux publicitaires à clics (non SRN), et envoyez le lien d'attribution au partenaire pour attribuer des campagnes spécifiques, des ensembles de publicités ou des publicités individuelles.

**Remarque :** les SRN n'implémentent pas les liens d'attribution générés par les annonceurs, cet onglet ne concerne donc pas les campagnes SRN.

**Pour générer un lien d'attribution** :

1. Sélectionnez **Utiliser un lien vers une plateforme unique** ou **Utiliser OneLink**.

   Sélectionnez **Utiliser un lien vers une plateforme unique** si l'un des cas suivants s'applique :

   * Vous prévoyez d'utiliser uniquement des <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">schémas d'URI</Anchor> pour ouvrir l'app.
   * Vous n'avez pas besoin du deep link avec l'URL.

   Sélectionnez **Utiliser OneLink** si l'une des situations suivantes s'applique :

   * Vous voulez utiliser un lien unique pour les apps Android et iOS.
   * Vous voulez utiliser les liens d'app Android ou des liens universels iOS pour ouvrir l'app.
   * Vous voulez des options de deep linking.

   **Remarque** : la sélection de OneLink modifie le lien d'enregistrement des clics. Il ne s'agit plus d'un lien spécifique à l'app mais d'une <Anchor target="_blank" href="/marketers/fr/docs/onelink-guide">URL OneLink</Anchor>.
2. Si vous avez sélectionné **Utiliser OneLink** :

   1. Sélectionnez le template OneLink que vous souhaitez utiliser pour ouvrir l'app (et potentiellement le deep link).
   2. [Facultatif] Entrez la **valeur du deep link**.
   3. [Facultatif] Entrez la **valeur du deep link supplémentaire**.
3. Ajoutez des paramètres pour <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters#paramètres-android-spécifiques">Android</Anchor> et <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters#paramètres-spécifiques-à-ios">iOS</Anchor>, tel que nécessaire.
4. [Facultatif] Sélectionnez des paramètres d'attribution supplémentaires.

#### Paramètres du lien d'attribution

[![attribution-link-parameters-en_us.png](https://files.readme.io/5f010d760295d53b8ff1891b58aaa57ac8171af7d08d7bc0df07b0998f81f666-4414306787601.png)](https://files.readme.io/5f010d760295d53b8ff1891b58aaa57ac8171af7d08d7bc0df07b0998f81f666-4414306787601.png)

En ajoutant des paramètres au lien d'attribution vous pouvez effectuer des analyses beaucoup plus précises. Il est possible de modifier les paramètres déjà définis sur le lien d'attribution en les ajoutant, ainsi que leurs nouvelles valeurs, ici. Lors de l'enregistrement du lien d'attribution, tous les paramètres configurés dans cet onglet sont sauvegardés.

Sélectionnez les paramètres que vous souhaitez ajouter au lien d'attribution.

#### Paramètres du lien d'attribution

| Nom | Description | Paramètre du lien d'attribution |
| --- | --- | --- |
| Campagne | **Paramètre requis.**  <br />Permet de comparer les différentes campagnes qui tournent sur la source média. | C |
| Ensemble de publicités | Permet de comparer différents adsets au sein de certaines campagnes de la source média. | af\_adset |
| Nom de la publicité | Permet de comparer différentes créations pour des adsets donnés au sein de certaines campagnes de la source média. | af\_ad |
| ID de site et ID de sous-site | **Paramètre requis.**<br /><br />Définissez l'ID de site pour attribuer les installations à certains éditeurs.<br /><br />L'ID de site doit être transmis à AppsFlyer via le lien d'attribution pour les raisons suivantes :<ul><li>Il fournit clarté et transparence sur l'éditeur.</li><li>Il est utilisé par AppsFlyer pour identifier et éliminer les éditeurs frauduleux, ou tout autre cluster de trafic.</li></ul>Notez qu'un identifiant de site manquant n'affectera pas l'attribution. En savoir plus sur le <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters#site-id-parameter">Paramètre d'ID de site</Anchor>.<br /><br />Si vous avez beaucoup d'éditeurs, nous vous conseillons de limiter le nombre d'ID de site et d'utiliser plutôt le paramètre d'ID de sous-site pour ne pas risquer de <Anchor target="_blank" href="/marketers/fr/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">dépasser le nombre d'ID de site autorisé</Anchor>. | af\_siteid et af\_sub\_siteid |
| Paramètres abonné | Utilisez l'un des 5 paramètres abonné pour insérer des valeurs utiles. Notez que ces paramètres sont analysés et apparaissent dans le rapport de données brutes, ce qui les rend très utiles pour l'agrégation de données ou le filtrage. | af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5 |

Vous pouvez ajouter d'autres paramètres au lien d'attribution en le saisissant dans une nouvelle fenêtre de paramètres. Vous pouvez utiliser tous les <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters">paramètres URL AppsFlyer disponibles.</Anchor> Notez que seuls le schéma d'URI et les paramètres OneLink sont encodés sur le lien d'attribution.

#### Paramètres de retargeting

**Lorsque le retargeting est activé**: ajouter <Anchor target="_blank" href="/marketers/fr/docs/retargeting-attribution-guide">&is\_retargeting=true</Anchor> au lien d'attribution fait que AppsFlyer reconnaît le lien comme un lien d'attribution de `retargeting`, plutôt que comme un lien d'acquisition d'utilisateur. **Paramètre du lien d'attribution :** is\_retargeting

Pour utiliser votre lien pour le retargeting :

1. Activez les **paramètres de retargeting**.
2. [Facultatif] Entrez un schéma d'URI si vous souhaitez qu'un schéma d'URI ouvre l'app.  
   **Remarque** :
   * Les schémas d'URI permettent d'ouvrir l'app en solution de secours dans le cas où les liens universels ou les liens d'app échouent.
   * Lorsque vous ajoutez un schéma d'URI ici, il remplace tout autre schéma d'URI défini dans les paramètres de votre template OneLink.
   * Le schéma d'URI est ajouté au lien dans le paramètre af\_dp.
3. [Facultatif] Activez **Ignorer les utilisateurs actifs pour le retargeting**.
4. Définissez la fenêtre inactive pour déterminer quels utilisateurs sont considérés comme actifs et inactifs.
5. Définissez la fenêtre de réengagement pour déterminer la période suivant le réengagement, où les événements in-app de l'utilisateur sont attribués à la source média de retargeting.

   * Vous pouvez définir la valeur en jours (1-90), en heures (jusqu'à 23) ou même en valeur vie.
   * La fenêtre de réengagement est ajoutée au lien dans le paramètre af\_reengagement\_window.

#### Attribution post clic

Utilisez le paramètre pour définir la **durée maximale entre le clic et l'installation**. Seules les installations (premiers lancements) qui ont lieu dans la fenêtre rétrospective seront attribuées.

Période autorisée : de 1 à 23 heures ou de 1 à 30 jours.

**Paramètre du lien d'attribution :** af\_click\_lookback

En savoir plus sur la <Anchor target="_blank" href="/marketers/fr/docs/set-up-lookback-windows">fenêtre rétrospective de clic</Anchor>.

**Lien d'attribution de clic**

[![click-through-attribution-link_en-us.png](https://files.readme.io/aba15af3164c4f233625cd56f90aa4d1a18b834cfb151c4e7042fa099c8f9125-4411038599953.png)](https://files.readme.io/aba15af3164c4f233625cd56f90aa4d1a18b834cfb151c4e7042fa099c8f9125-4411038599953.png)

C'est le lien d'attribution qui contient toutes les informations de configuration que vous avez définies pour ce lien. Pour enregistrer le lien pour référence future, cliquez sur **Enregistrer le lien d'attribution**.

**Pour copier le lien d'attribution de clic :**

1. Cliquez sur **Enregistrer le lien d'attribution.**
2. Copiez le lien généré.

Envoyez le lien au partenaire, il sera activé lorsque vos clients potentiels cliqueront sur la publicité correspondante.

#### Fenêtre rétrospective d'attribution post vue

Définissez la **durée maximale entre l'impression et l'installation**. Seules les installations (premiers lancements) qui ont lieu dans cette fenêtre rétrospective suite à une impression de publicité, sont attribuées au partenaire (à condition qu'aucun autre clic sur la publicité ne soit pris en compte).

Vous pouvez personnaliser cette valeur et la définir entre 1 à 24 heures.

**Paramètre du lien d'attribution :** af\_viewthrough\_lookback

En savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/set-up-lookback-windows">l'attribution post vue</Anchor>.

**Lien d'attribution des impressions**

[![impressions-attribution-link_en-us.png](https://files.readme.io/76a2d084f66f3a279b281f60a465af5098e05de8de128cfd6f04a97fe52c4dc6-4411047429265.png)](https://files.readme.io/76a2d084f66f3a279b281f60a465af5098e05de8de128cfd6f04a97fe52c4dc6-4411047429265.png)

Le lien d'attribution des impressions contient des données d'attribution similaires au lien d'enregistrement des clics (en plus de la fenêtre rétrospective différente). Pour enregistrer le lien pour référence future, cliquez sur **Enregistrer le lien d'attribution**.

Cliquez sur Enregistrer le lien d'attribution, puis copiez le lien généré.

**Pour copier le lien d'attribution des impressions :**

1. Cliquez sur **Enregistrer le lien d'attribution.**
2. Copiez le lien généré.

Envoyez-le au partenaire afin de l'activer lorsqu'une publicité correspondante est regardée, généralement pendant 1 seconde ou plus.

</Accordion>

<div id="cost-tab" />

<Accordion title="Onglet Coût">

* Les données de coûts sont rapportées par vos partenaires intégrés au clic, ou par API de coût.
* Il est recommandé d'implémenter l'API de coût (abonnement ROI360 requis).
* L'API de coût inclut les rapports sur les clics et les impressions. Consultez le <Anchor target="_blank" href="/marketers/fr/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tableau d'intégration des coûts du réseau publicitaire</Anchor> pour en savoir plus sur les dimensions, les métriques et les fonctionnalités prises en charge.

> 📘 **Note**
>
> Si un annonceur fait appel à une agence pour gérer ses campagnes, c'est l'agence, et non l'annonceur, qui doit être intégrée aux partenaires concernés. Sinon, si l'annonceur et l'agence s'intègrent à un partenaire en utilisant les mêmes informations d'identification pour la même app, les données de coût sont dupliquées.

#### Activation des données de coût par API

**Pour activer l'API de coûts :**

* Suivez  <Anchor target="_blank" href="/marketers/fr/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">ces instructions d'intégration</Anchor>.

#### État de synchronisation des données de coût

<Anchor target="_blank" href="/marketers/fr/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">Affichez le statut de votre API de coûts</Anchor> et la dernière fois qu'AppsFlyer a réussi à extraire des données de coûts correspondantes, soit dans le tableau de bord du statut d'intégration des coûts (et des revenus publicitaires), soit dans le tableau de bord du réseau publicitaire individuel.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Onglet Revenus publicitaires">

Si vous avez le rôle d'éditeur en diffusant les publicités dans votre app, l'option revenu publicitaire vous permet d'attribuer les revenus publicitaires à la source média qui a drainé l'utilisateur. <Anchor target="_blank" href="/marketers/fr/docs/roi360-guide-ad-revenue-attribution">A propos de l'attribution des revenus publicitaires.</Anchor>

#### Activer l'attribution des revenus publicitaires

1. Vérifiez quelle type de méthode, <Anchor target="_blank" href="/marketers/fr/docs/roi360-guide-ad-revenue-attribution#list-of-ad-revenue-integrated-partners">attribution agrégée ou bien au niveau de l'utilisateur</Anchor>, le partenaire prend en charge.
2. Suivez la procédure proposée dans <Anchor target="_blank" href="/marketers/fr/docs/roi360-guide-ad-revenue-attribution#implémentation">le guide d'intégration des revenus publicitaires</Anchor>.

#### Messages de statut de l'API des revenus publicitaires

| Statut | Remarques/actions requises |
| --- | --- |
| Actif | La connexion est active et les données sont en cours d'extraction. |
| Aucune donnée à extraire n'a été trouvée. | La connexion a été établie. Le partenaire ne disposait d'aucune donnée relative à cette app. |
| L'API partenaire ne répond pas. Veuillez contacter l'assistance AppsFlyer. | Le serveur du partenaire ne répond pas à AppsFlyer. |
| Identifiants invalides. Veuillez saisir de nouveaux identifiants. |  |
| Un problème est survenu. Veuillez contacter l'assistance AppsFlyer. | Un problème technique vient de se produire. |
| Les données du partenaire ne sont pas encore prêtes. Si le problème persiste, contactez l'assistance AppsFlyer. |  |
| Les données sont en cours de traitement et seront bientôt disponibles. | Nous traitons actuellement les données reçues du partenaire. Les données seront mises à disposition dans les tableaux de bord et les rapports. |
| Aucune données n'a pu être extraite correctement | Si ce statut perdure une heure de plus, contactez l'assistance AppsFlyer. |

</Accordion>

<div id="permissions-tab" />

<Accordion title="Onglet Autorisations">

* Permet au partenaire d'effectuer différentes actions et d'accéder à vos données selon les autorisations accordées.
* Il n'est pas nécessaire d'activer l'intégration d'attribution avec un partenaire pour lui donner certaines autorisations.
* **Réseau publicitaire configuré par une agence :** lorsque un partenaire est configuré par une agence, l'annonceur ne peut ni afficher l'état d'activation du réseau publicitaire, ni les autorisations qui ont été accordées.
* Si vous collaborez avec le partenaire exclusivement en tant qu'agence, ignorez la section **Autorisations du réseau publicitaire** et paramétrez directement la section **Autorisations de l'agence**.

#### Autorisations pour le réseau publicitaire

**Pour octroyer des autorisations aux membres d'équipe du réseau publicitaire :**

1. Activez les **Autorisations du réseau publicitaire**.
   * Votre app apparaît dans le tableau de bord du réseau publicitaire.
   * L'admin du réseau publicitaire peut <Anchor target="_blank" href="/marketers/fr/docs/manage-data-access-permissions">consulter les données de base de l'app</Anchor>.
2. Octroyez des autorisations aux membres d'équipe du réseau publicitaire :  
   * Pour accorder des autorisations à certains membres d'équipe, vous devez les définir en utilisant leur adresse e-mail.  
     **Pour ajouter un membre d'équipe** :
     1. Cliquez sur **Ajouter un membre d'équipe**.
     2. Saisissez l'adresse email du membre d'équipe du réseau publicitaire
     3. Cliquez sur **Ajouter**.
3. Sélectionnez les autorisations supplémentaires à accorder à l'ad network : 

| **Autorisation** | **Permission accordée** |
| --- | --- |
| <span id="configure-integration"></span>Configurer l'intégration | Le réseau publicitaire peut modifier les paramètres dans l'onglet *Intégration*. |
| <span id="configure-inapp-event-postbacks"></span>Configurer les postbacks d'événement in-app | Le réseau publicitaire peut : créer, définir et modifier les paramètres des postbacks.<br /><br />**Attention**! Lorsque cette autorisation et l'option **Configurer l’intégration** sont activées en même temps : le réseau publicitaire a accès à la totalité des événements, ce qui inclut le trafic organique et le trafic non organique provenant de l'ensemble des sources média. |
| <span id="access-retention-report"></span>Accéder au rapport de rétention | Le réseau publicitaire peut accéder au rapport de rétention de l'application. Il ne verra que les données relatives à ses sessions. |
| <span id="access-aggregate-loyal-users-data"></span>Accéder aux données agrégées sur les utilisateurs fidèles | Le réseau publicitaire peut accéder aux mesures de ses propres <Anchor target="_blank" href="/marketers/fr/docs/about-a-loyal-user">utilisateurs fidèles</Anchor>. |
| <span id="access-aggregate-conversions-data"></span>Accéder aux données agrégées de conversion | Le réseau publicitaire peut accéder à  ses rapports de mesures agrégées des événements de conversion. Ils incluent les réengagements, les réinstallations et les réattributions. Exemple : <Anchor target="_blank" href="/partners/fr/docs/aggregated-campaign-performance-report-for-ad-networks">performances agrégées de campagne pour les rapports des réseaux publicitaires</Anchor>. |
| <span id="access-aggregate-inapp-events-data"></span>Accéder aux données agrégées sur les événements in-app | Le réseau publicitaire peut :<ul><li>Accéder aux rapports agrégés de données des événements in-app. Le partenaire a accès à l'ensemble des données d'événements in-app, y compris les données d'événements in-app Protect360, et pas seulement aux événements mappés dans la configuration de postback.</li><li>Accéder aux données de monétisation publicitaire, qui peuvent inclure les événements provenant d'autres sources média.</li></ul> |
| <span id="view-validation-rules"></span>Afficher les règles de validation | Le réseau publicitaire peut consulter les détails de la <Anchor target="_blank" href="/marketers/fr/docs/implement-validation-rules-to-prevent-fraud">règle de validation</Anchor>. |
| <span id="access-aggregate-revenue-data"></span>Accéder aux données agrégées sur les revenus | Le réseau publicitaire peut accéder aux rapports agrégés de données in-app et de données des revenus publicitaires attribuées aux utilisateurs drainés par le réseau publicitaire. **Remarque :** Cette autorisation n'identifie pas directement le partenaire des revenus publicitaires. mais sachez que si vous avez paramétré le nom de l'événement de monétisation pour que le nom du partenaire y apparaisse, vous risquez de divulguer l'identité du réseau de monétisation. |
| <span id="use-ad-spend-ingestion"></span>Utiliser l'ingestion des dépenses publicitaires | Le réseau publicitaire peut :<ul><li>Accéder à la fenêtre <Anchor target="_blank" href="/marketers/fr/docs/import-cost-data">d'ingestion des dépenses publicitaires</Anchor>. Cette fenêtre affiche uniquement les apps pour lesquelles le partenaire a une autorisation.</li><li>Envoyer les fichiers de dépenses publicitaires pour ingestion.</li></ul> |
| <span id="access-protect360-dashboard-raw-data"></span>Accéder au tableau de bord Protect360 et aux données brutes | Le réseau publicitaire peut :<ul><li>Accéder au tableau de bord Protect360 (inclut <Anchor target="_blank" href="/marketers/fr/docs/basic-fraud-detection-and-insights-with-protectlite-dashboard-and-reporting">ProtectLITE</Anchor>).</li><li>Accéder à Protect360, aux règles de validation et aux données brutes, si elles sont comprises dans la formule d'abonnement. ProtectLITE n'inclut pas l'accès aux données brutes.</li></ul>**Remarque :** si vous avez un abonnement <Anchor target="_blank" href="/marketers/fr/docs/protect360-anti-fraud-guide">Protect360</Anchor>, le réseau publicitaire peut voir le tableau de bord complet. Sans abonnement Protect360, il peut uniquement accéder au tableau de bord réduit. |
| <span id="access-ad-revenue-raw-data"></span>Accédez aux données brutes des revenus publicitaires | Le réseau publicitaire peut accéder à ses <Anchor target="_blank" href="/partners/fr/docs/ad-revenue-signals-for-ua-ad-networks">données de revenus publicitaires afin d'optimiser l'AU</Anchor>.   <br />**Remarque :** Cette permission n'est disponible que pour les apps disposant d'un abonnement <Anchor target="_blank" href="/marketers/fr/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor>. |

#### Autorisations pour l'agence

* Lorsque vous accordez des autorisations aux agences, elles peuvent accorder des autorisations aux réseaux publicitaires avec lesquels elles collaborent de manière à ce que ces derniers gèrent vos apps. Cela revient à accorder des autorisations aux réseaux publicitaires.
* Si vous travaillez avec un réseau publicitaire et que votre agence travaille également avec ce réseau publicitaire, vous pouvez tous les deux modifier les autorisations des membres de l'équipe du réseau publicitaire concernant la visibilité du tableau de bord de l'app. Si vous voyez des nouveaux membres d'équipe du réseau publicitaire que vous n'avez pas ajoutés, ou s'il manque des membres d'équipe que vous n'avez pas supprimés, il est donc possible que ce soit le marketeur qui l'ait fait.
* **Attention :** les installations de l'agence qui ont lieu alors que le contrôle est désactivé ne seront pas attribuées à l'agence, et elles n'apparaitront ni dans le tableau de bord ni dans les données de l'agence. En savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation#agency-permissions">l'activation des agences</Anchor>.
* Découvrez <Anchor target="_blank" href="/partners/fr/docs/getting-started-agency-onboarding#que-signifie-obtenir-lautorisation-dun-marketeur">ce que les agences peuvent faire</Anchor> lorsqu’elles obtiennent des autorisations.

**Pour accorder des autorisations à une agence :**

1. Activez **les autorisations de l'Agence**.
2. Sélectionnez les autorisations à donner à l'agence : 

| **Autorisation** | **Permission accordée** |
| --- | --- |
| <span id="change-advanced-privacy-configuration"></span>Modifier la configuration de confidentialité avancée | L'agence peut modifier les paramètres de <Anchor target="_blank" href="/marketers/fr/docs/apply-aggregated-advanced-privacy-framework">Confidentialité avancée du partage des données</Anchor> du réseau publicitaire. |
| <span id="access-retention-and-cohort-reports"></span>Accéder aux rapports de rétention et de cohorte | L'agence peut accéder aux données de rétention/cohorte créées par les utilisateurs qu'elle a amenés. |
| <span id="access-aggregate-organic-data"></span>Accéder aux données organiques agrégées | L'agence peut accéder aux données organiques agrégées. |
| <span id="view-validation-rules::6872643b"></span>Afficher les règles de validation | L'agence peut consulter les détails de la règle de validation sur le site. |
| <span id="add-validation-rules"></span>Ajouter des règles de validation | L'agence peut ajouter et modifier des règles de validation. Disponible lorsque l'option **Consulter les règles de validation** est activée. **Remarque** : les agences ne peuvent pas modifier les règles qui ont été créées par des annonceurs. |
| <span id="access-rawdata-reports"></span>Accéder aux rapports de données brutes | L'agence peut accéder aux rapports de données brutes pour le trafic qui lui est attribué. Les annonceurs ne peuvent pas limiter les événements qu'une agence peut visualiser dans les rapports. |
| <span id="access-protect360-dashboard-raw-data::dd9829fd"></span>Accéder au tableau de bord Protect360 et aux données brutes | L'agence peut :<ul><li>Accéder à votre tableau de bord agrégé Protect360</li><li>Accéder à Protect360, aux règles de validation et aux données brutes, si elles sont comprises dans la foemule d'abonnement.</li></ul>**Remarque** : Pour les annonceurs qui travaillent avec les réseaux publicitaires par le biais d'une agence, pour que ces derniers puissent accéder aux données, l'annonceur doit intégrer à la fois l'agence et le réseau publicitaire dans AppsFlyer, et leur accorder l'autorisation d'accéder aux données.Si seule l'agence est intégrée et autorisée, le réseau publicitaire n'aura pas accès aux données. |
| <span id="configure-inapp-event-postbacks::8743ba60"></span>Configurer les postbacks d'événement in-app | L'agence peut configurer les postbacks d'événements in-app pour les évènements spécifiques sélectionnés :<ul><li>**Ajouter un événement :** dans le menu déroulant, sélectionnez les événements pour lesquels vous approuvez l'autorisation accordée à l'agence.</li></ul>Les options suivantes s'appliquent aux événements sélectionnés :<ul><li>**Autoriser l'envoi des revenus d'événement :** lorsque cette option est activée, l'agence peut configurer l'envoi d'événements qui incluent leur valeur monétaire.</li><li>**Option d'envoi :**<ul><li>**Ce partenaire uniquement :** si cette option est sélectionnée, l'agence peut configurer l'envoi de postbacks uniquement pour les événements attribués au trafic qu'elle a généré.</li><li>**Toutes les sources média, y compris organiques :** si cette option est sélectionnée, l'agence peut configurer l'envoi de postbacks pour les événements attribués à toutes les autres sources média, aux agences et aux utilisateurs organiques.</li></ul></li></ul> |

En savoir plus sur <Anchor target="_blank" href="/partners/fr/docs/about-agency-accounts#accès-des-agences-aux-données-des-marketeurs">le travail avec les agences</Anchor>.

</Accordion>

## Tester l'intégration

Une fois l’intégration du partenaire terminée et avant de commencer à lancer des campagnes avec le partenaire nouvellement ajouté, il est important de tester l’intégration. Les erreurs sont plus susceptibles de survenir lors de la configuration. Veillez à effectuer des tests préalables, afin d'éviter des dépenses de ressources pour découvrir au final que vos données d'attributions sont manquantes ou erronées.

> 📘 **Note**
>
> Avant de tester l’intégration, assurez-vous de <Anchor target="_blank" href="/marketers/fr/docs/testing-the-sdk-integration-for-marketers">commencer par tester l’app pour l’intégration de base du SDK,</Anchor> y compris les installations organiques et non organiques.

<div id="test-the-attribution-link-for-nonsrns" />

<Accordion title="Tester le lien d'attribution pour les non SRN">

Les réseaux publicitaires non SRN les plus répandus (qui représentent 99,5 % de l'ensemble des réseaux publicitaires intégrés) utilisent des liens d'attribution AppsFlyer. Il en va de même pour l'attribution des médias propres, qui se fait à l'aide des liens d'attribution personnalisés AppsFlyer.

Comme une bonne attribution dépend des paramètres des liens d'attribution, pensez à tester ces liens avant de lancer une nouvelle campagne avec un réseau publicitaire non SRN, ou un lien d'attribution personnalisé.

**Pour tester les liens d'attribution :**

1. Créer un [lien d'attribution](/docs/set-up-an-integrated-partner#attribution-link-tab).
2. Envoyez le nouveau lien d'attribution à votre appareil de test <Anchor target="_blank" href="/marketers/fr/docs/registering-test-devices">enregistré</Anchor> (via email ou QR Code)
3. Cliquez sur le lien et vérifiez que vous êtes bien redirigé ver l'app store.
4. Installez l'app.
5. Lancez l'app.
6. Vérifiez que l'installation apparaît bien dans le tableau de bord AppsFlyer, en dessous du nom de la source média du partenaire. Il faut compter jusqu'à 30 minutes pour que l'installation apparaisse dans le tableau de bord.
7. Rendez-vous au niveau de la campagne (en sélectionnant le partenaire dans le **filtre Source média** en haut de la page de vue d'ensemble) pour vérifier que l'installation apparaît en dessous du nom de campagne approprié.
8. Si nécessaire, continuez d'explorer et vérifiez également les niveaux Définir les publicités et Publicité unique.

</Accordion>

<div id="test-the-srn-integration" />

<Accordion title="Tester l'intégration SRN">

Les SRN tels que Meta ads, Apple Search Ads et Google Ads ne se basent pas sur des liens d'attribution externes pour attribuer. Au lieu de cela, les SRN reçoivent des requêtes provenant d'AppsFlyer, les attribuent eux-mêmes puis renvoient la réponse. Par conséquent, il est impossible de tester l'intégration indépendamment du système du réseau, comme on le fait pour les réseaux publicitaires habituels. Vous devez systématiquement tester l'intégration avec chaque SRN avec qui vous collaborez.

**Pour tester l'intégration d'un SRN** :

1. Effectuez la configuration complète du SRN sur AppsFlyer conformément au <Anchor target="_blank" href="/marketers/fr/docs/self-reporting-networks-srns#srn-intégrés-à-appsflyer">Guide de configuration spécifique du SRN</Anchor>.
2. Lancez une nouvelle campagne à petit budget avec le partenaire SRN.
3. Lorsque le tableau de bord du partenaire affiche de nouvelles installations, vérifiez si elles apparaissent bien dans le tableau de bord AppsFlyer sous le nom de la source média du partenaire.
4. Dans la vue d'ensemble du tableau de bord, développez les catégories jusqu'au niveau campagne en sélectionnant le partenaire à l'aide du **filtre de source média**. Vous pourrez ainsi vérifier que l'installation apparaît sous le bon nom de campagne. Il faut compter jusqu'à 30 minutes pour que l'installation apparaisse dans le tableau de bord.
5. Si nécessaire, ouvrez d'autres sous-catégories pour accéder aux niveaux adset et publicité unique.

Si tout se passe bien, vous pouvez commencer de nouvelles campagnes à gros budget avec le partenaire. Ce test d'intégration ne doit s'effectuer qu'une seule fois par partenaire SRN. Ce qui veut dire qu'il est inutile de tester chaque campagne.

</Accordion>

<div id="test-the-raw-data" />

<Accordion title="Tester les données brutes">

Si votre forfait d'abonnement AppsFlyer comprend l'accès aux données brutes, vous devez tester ces données.

**Pour tester les données brutes**:

1. Une fois effectué le test mentionné précédemment, rendez-vous dans **Rapports** > **<Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview">Données d'exportation</Anchor>**.
2. Sélectionnez la source média testée.
3. Attendez jusqu'à 15 minutes après l'installation puis téléchargez le rapport des installations.
4. Vérifiez que les enregistrements d'installation du partenaire existent bien et qu'ils incluent les paramètres de type : source média, nom de la campagne, heure et type de touch, ID de l'appareil (si fourni), nom de l'agence (apparait sous l'appellation « Partenaire » dans le rapport), etc.

> 🚧 **Important !**
>
> Certains réseaux publicitaires exigent des actions spécifiques pour activer la collecte de données brutes au niveau utilisateur.
>
> Si vous voyez une nouvelle installation sur le tableau de bord mais que vous ne la voyez pas dans les données brutes, consultez le guide du centre d'aide dédié au réseau publicitaire, par exemple <Anchor target="_blank" href="/marketers/fr/docs/x-ads-formerly-twitter-ads-faq-and-discrepancies#do-you-make-twitters-raw-data-available-to-agencies">Twitter</Anchor>.

</Accordion>

<div data-zendesk-anchors="overview=pr%C3%A9sentation 01H80XGTBQ6MAK3VG0X6QMAYMP=pr%C3%A9sentation 01H80XGTBQPPZV7WR5JBHQFB0B=partner-types-in-the-ecosystem 01H80XGTBQ4CPMBRVSMM7TD4VD=partners-in-the-marketplace invite-new-partners-to-appsflyer=inviter-de-nouveaux-partenaires-dans-appsflyer 01H80XGTBQRJ78XCGNZBTJVYEQ=inviter-de-nouveaux-partenaires-dans-appsflyer 01H80XGTBQ8VF6V9WARZRECWVR=your-integrated-partners 01H80XGTBQJQYD3R46H95WVVM0=note 01H80XGTBQ5BE24X219BVZBMDG=about-the-integrated-partner-page applicable-settings-tabs-per-partner-type=onglets-param%C3%A8tres-applicables-selon-le-type-de-partenaire 01H80XGTBQPP74G38YNNYVXWP2=onglets-param%C3%A8tres-applicables-selon-le-type-de-partenaire set-up-a-partner-nonsrn=configurer-un-partenaire-non-srn 01H80XGTBQXNQ7SFXZ5PBQGS1V=configurer-un-partenaire-non-srn 01H80XGTBQZXZARZCM61CMG0K3=note-1 01H80XGTBQB9T22GQ7CSHS2S1X=integration-tab integration-tab-sections=sections-concernant-lint%C3%A9gration 01H80XGTBQ0531M2RS3DH7E4Z0=sections-concernant-lint%C3%A9gration 01H80XGTBQ4MPGGKSZW0D9GG9H=note-2 01H80XGTBRT41FGP5107G96TWC=attribution-link-tab attribution-link-parameters=param%C3%A8tres-du-lien-dattribution 01H80XGTBRPENCTCRK8PPYSCGX=param%C3%A8tres-du-lien-dattribution attribution-link-parameters::3874dfb8=param%C3%A8tres-du-lien-dattribution-1 01H80XGTBR8630SEV80K9RD6V9=param%C3%A8tres-du-lien-dattribution-1 retargeting-settings=param%C3%A8tres-de-retargeting 01H80XGTBRT57QMPRENYSS81Z3=param%C3%A8tres-de-retargeting clickthrough-attribution=attribution-post-clic 01H80XGTBREZTJ6B0Y08JCKN1E=attribution-post-clic viewthrough-attribution-lookback-window=fen%C3%AAtre-r%C3%A9trospective-dattribution-post-vue 01H80XGTBRXC1YYX4FW94NDR2Z=fen%C3%AAtre-r%C3%A9trospective-dattribution-post-vue 01H80XGTBRERTJ9XHGDV416T7V=cost-tab 01H80XGTBR54TQ0DNY1JR36GXN=note-3 enabling-cost-data-by-api=activation-des-donn%C3%A9es-de-co%C3%BBt-par-api 01H80XGTBRV6BHWS76HWHK933M=activation-des-donn%C3%A9es-de-co%C3%BBt-par-api cost-data-sync-status=%C3%A9tat-de-synchronisation-des-donn%C3%A9es-de-co%C3%BBt 01H80XGTBRPWREFYFXA0A6VD47=%C3%A9tat-de-synchronisation-des-donn%C3%A9es-de-co%C3%BBt 01H80XGTBRJ1AKX2Q7WPXFVA49=ad-revenue-tab enable-ad-revenue-attribution=activer-lattribution-des-revenus-publicitaires 01H80XGTBRHE9PPRA9X46M4TGZ=activer-lattribution-des-revenus-publicitaires ad-revenue-api-status-messages=messages-de-statut-de-lapi-des-revenus-publicitaires 01H80XGTBRNT4K4ZNPKVV25ESJ=messages-de-statut-de-lapi-des-revenus-publicitaires 01H80XGTBRGXS97JMG45QR4BEQ=permissions-tab ad-network-permissions=autorisations-pour-le-r%C3%A9seau-publicitaire 01H80XGTBRS9BTT2F8F95BCE9Z=autorisations-pour-le-r%C3%A9seau-publicitaire agency-permissions=autorisations-pour-lagence 01H80XGTBRTVP407AAA77N090E=autorisations-pour-lagence test-the-integration=tester-lint%C3%A9gration 01H80XGTBSEWPHCPQF29XD6Y4W=tester-lint%C3%A9gration 01H80XGTBSTHG2FC2M31F83RGK=note-4 01H80XGTBS4P06757QXHDKYAHT=test-the-attribution-link-for-nonsrns 01H80XGTBS2K9SPQ1MTAV7GP2H=test-the-srn-integration 01H80XGTBSTBV4RC3V279WNNB1=test-the-raw-data 01H80XGTBSN0VAX76XW9Y77T04=important-" />
