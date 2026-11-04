---
title: 'Paramètres d''application  '
metadata:
  keywords:
    - App Settings
    - Advertisers
    - Agencies
    - Developers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - Marketers
    - Platform essentials
    - Agencies
    - pm-guy-riesenberg
  created_at: '2016-08-16T07:50:37Z'
  edited_at: '2023-10-27T11:12:45Z'
  id: 211719806
  locale: fr
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/fr/articles/211719806
---
> **En bref :** découvrez les paramètres qui agissent sur l'attribution et l'analyse de votre app sur l'ensemble des sources média.

<div id="app-settings" />

## Paramètres d'application

**Accès :**

* Un admin (ou n'importe quel utilisateur avec les autorisations nécessaires) peut **modifier** les paramètres de l'app.
* Tous les utilisateurs de compte qui ont accès à une app spécifique peuvent **consulter** ses paramètres.

**Pour apporter des modifications ou afficher les paramètres de l'app :**

1. Dans AppsFlyer, rendez-vous dans **Configuration** > **Paramètres de l'app.**
2. Affichez les paramètres et faites les modifications requises sur la page Paramètres de l'app.
3. Cliquez sur **Enregistrer les paramètres**.

<div id="general-app-settings" />

### Paramètres généraux de l'app

<Table>
  <thead>
    <tr>
      <th>
        Paramètre
      </th>
      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="sdk-authentication-dev-key"></span>
        Authentification SDK : clé dev
      </td>
      <td>
        * La clé dev authentifie les événements envoyés par l'app ou par S2S à AppsFlyer.
        * La clé est unique par compte et est utilisée par toutes les apps du compte.
        * La clé est disponible sur la page Paramètres d'app pour tous les utilisateurs de compte ayant accès à cette app.
        * [Facultatif] Une clé d'app individuelle peut être allouée dans certains cas. Contactez votre CSM pour en discuter.
      </td>
    </tr>
    <tr>
      <td><span id="aggregated-advanced-privacy-ios-apps"></span>
        Confidentialité avancée agrégée (apps iOS)
      </td>
      <td>
        Lorsque cette option est activée, les données d'attribution de niveau utilisateur ne sont pas accessibles aux annonceurs. Les postbacks et données d'événement partagées avec les partenaires sont agrégées et anonymes (en savoir plus sur l'infrastructure <Anchor target="_blank" href="/marketers/fr/docs/apply-aggregated-advanced-privacy-framework">Confidentialité avancée agrégée</Anchor>).

        Lorsque cette option est désactivée, les données d'attribution de niveau utilisateur sont accessibles à tous les partenaires en tant que données agrégées et peuvent être définies séparément pour chaque partenaire.
      </td>
    </tr>
    <tr>
      <td><span id="analytics-define-loyal-user-trigger"></span>
        Analyses : définir le déclencheur pour utilisateur fidèle
      </td>
      <td>
        * Ce déclencheur désigne un utilisateur comme un utilisateur fidèle. Par défaut l'option définie lorsque vous ajoutez l'app est : ouverture de 3 apps.
        * Après avoir attribué des événements in-app, vous pouvez utiliser un événement in-app comme événement déclencheur.
          * [Par défaut] 3 ouvertures d'app.
          * Le paramètre Utilisateurs fidèles indique la qualité des utilisateurs. Pensez à utiliser <Anchor target="_blank" href="/marketers/fr/docs/protect360-anti-fraud-guide#faq">Protect360</Anchor> pour lutter contre la fraude.
          * La modification de ce paramètre a un impact rétroactif sur les données. Cela signifie que les données historiques des utilisateurs fidèles sont recalculées.
      </td>
    </tr>
    <tr>
      <td><span id="app-store-country"></span>
        Pays de l'App Store
      </td>
      <td>
        Définit le pays de l'app store dans laquelle l'app est disponible. Ce paramètre affecte l'application comme détaillé ici.

        * **Passer le statut de l'app de En attente à En ligne :**
          * <Anchor target="_blank" href="/marketers/fr/docs/why-is-my-app-still-pending">Lorsque l'app est mise en ligne</Anchor>, AppsFlyer vérifie le store en utilisant le paramètre du pays afin de récupérer des détails sur l'app, comme son icône.
          * Si l'app ne se trouve pas dans le pays défini pour le store, AppsFlyer ne peut pas modifier l'état de l'app de En attente à En ligne.
        * Le comportement de redirection est affecté par le paramètre en fonction du scénario, comme détaillé dans le tableau qui suit.

        | Type d'utilisateur | Scénario de redirection |
        | --- | --- |
        | <span id="mobile"></span>Mobile | Les utilisateurs cliquent généralement sur les liens d'attribution à l'intérieur d'autres apps mobiles. En cliquant, le système d'exploitation détermine le pays de l'app store vers lequel rediriger les utilisateurs :  <br /><br />* **Android** redirige en fonction de l'adresse IP/de l'emplacement de l'utilisateur.<br />* **iOS** redirige vers l'app store associé au compte iTunes actif sur l'appareil. |
        | <span id="mobile-and-web"></span>Mobile et web | Dans un **site web** (mobile et ordinateur de bureau), lorsqu'un utilisateur web clique sur un lien d'attribution,, la redirection initiale se fait vers le store défini dans le pays de l'app store.<br /><br />Lors d'une tentative d'installation, le système d'exploitation les redirige vers le store du pays, tel que décrit précédemment pour les mobiles. |
        | <span id="ipad-ios-13"></span>iPad iOS 13 | À partir d'iOS 13, <Anchor target="_blank" href="https://www.apple.com/ipados/features/">les iPads exécutent la version de bureau des sites web</Anchor> . Cela signifie que le type d'utilisateur (mobile ou web) ne change rien. Un clic sur un lien d'attribution envoie sur un site d'ordinateur et à partir de là les règles de redirection sont celles des utilisateurs web. |
      </td>
    </tr>
    <tr>
      <td><span id="localization-time-zone"></span>
        Localisation : fuseau horaire
      </td>
      <td>
        Le paramètre d'app par défaut est l'UTC.  <Anchor target="_blank" href="/marketers/fr/docs/changing-app-time-zone-settings">À propos du fuseau horaire de l'app.</Anchor>
      </td>
    </tr>
    <tr>
      <td><span id="localization-currency"></span>
        Localisation :  
        devise
      </td>
      <td>
        La devise par défaut est USD.

        * Le changement de devise n'est disponible que pour les apps sans revenus ni coûts.
        * Pour les nouvelles apps, la devise est définie lorsque l'app est ajoutée.

        <div id="reporting-tools-impacted-by-app-currency" />

        #### Outils de reporting impactés par la devise de l'app

        | Outil de reporting | Options de devise disponibles |
        | --- | --- |
        | <span id="dashboards"></span>Tableaux de bord | Devise spécifique à l'app |
        | <span id="export-data-page"></span>Page Données d'exportation | Devise spécifique à l'app |
        | <span id="push-api"></span>API push | Devise spécifique à l'app et USD disponibles simultanément |
        | <span id="pull-api"></span>API pull | Données agrégées : devise spécifique à l'app<br /><br />Données brutes : USD sélectionnable ou devise spécifique à l'app |
        | <span id="master-api"></span>Master API | USD sélectionnable ou devise spécifique à l'app |
        | <span id="data-locker"></span>Data Locker | USD seulement |
      </td>
    </tr>
  </tbody>
</Table>

<div id="attribution-settings" />

### Paramètres d'attribution

| Paramètre | Description |
| --- | --- |
| <span id="reattribution-window"></span>Fenêtre de réattribution | La <Anchor target="_blank" href="/marketers/fr/docs/set-up-re-attribution-window">fenêtre de réattribution</Anchor> est la période qui commence aux données de la première installation, et pendant laquelle les réinstallations ne peuvent pas être attribuées en tant que nouvelles installations.<ul><li>[default] Trois mois</li><li>Plage de valeurs : 1-24 mois</li></ul> |
| <span id="viewthrough-attribution-via-probabilistic-modeling"></span>Attribution post vue par modélisation probabiliste | <ul><li>[Méthode conseillée] Activez la modélisation probabiliste post vue en complément de l'attribution post clic, qui est toujours activée.</li><li>Après avoir activé la modélisation probabiliste post vue, vous devez également activer l'attribution post vue dans l'onglet d'intégration au réseau publicitaire.</li></ul> |
| <span id="reengagement-attribution"></span>Attribution du ré-engagement | Lectures connexes : <Anchor target="_blank" href="/marketers/fr/docs/retargeting-attribution-guide">Le guide du retargeting</Anchor><br /><br />**Pour activer l'attribution de réengagement :**<ul><li>Rendez-vous dans **Paramètres** > **Paramètres de l'app** et activez l'**Attribution de réengagement**.</li></ul>En plus des paramétres de l'app, vous devez également <Anchor target="_blank" href="/marketers/fr/docs/retargeting-attribution-guide#retargeting-settings">définir les paramètres pour chaque partenaire</Anchor>.<br /><br />Le paramètre **<Anchor target="_blank" href="/marketers/fr/docs/retargeting-attribution-guide#fenêtres-dexclusion">Temps minimum entre les conversions de réengagement</Anchor>** est utilisé pour empêcher une fenêtre de réengagement existante de se refermer avant la durée fixée. |
| <span id="organic-search-seo-mobile-app-attribution"></span>Attribution d'app mobile en recherche organique (SEO) | Lecture connexe : <Anchor target="_blank" href="/marketers/fr/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">Attribution de la recherche organique</Anchor><br /><br />**Pour activer l'attribution de recherche organique :**<ul><li>Allez dans **Paramètres** > **Paramètres de l'app**, activez l'**attribution d'app mobile en recherche organique (SEO**).</li></ul> |
| <span id="uninstall-measurement"></span>Mesure des désinstallations | La mesure des désinstallations se rapporte aux installations qui ont lieu lorsque la mesure des désinstallations est activée.<br /><br />**Pour activer la mesure des désinstallations :**<ol><li>Effectuez les opérations suivantes selon le système d'exploitation :<ul><li>**iOS** : les apps qui implémentent la fonctionnalité d'attribution des désinstallations iOS doivent télécharger le certificat P12 ici.</li><li>**Android**: les apps nécessitent une clé de serveur Firebase/GCM (à définir ici) pour l'attribution des désinstallations Android.</li></ul></li><li>Activez la **mesure des désinstallations**.</li><li>Cliquez sur **Enregistrer les paramètres**.</li></ol>**Pour désactiver la mesure des désinstallations :**<ol><li>Désactivez la **mesure des désinstallations**.</li><li>Cliquez sur **Enregistrer les paramètres**.</li></ol> |

<div id="advanced-settings" />

### Paramètres avancés

| Paramètre | Description |
| --- | --- |
| <span id="mask-ip-address-in-raw-data-reports"></span>Masquer les adresses IP | Lorsque cette option est activée, les <Anchor target="_blank" href="/marketers/fr/docs/apply-ip-masking-to-user-data">adresses IP des appareils des utilisateurs finaux sont masquées</Anchor> dans les rapports de données brutes ainsi que dans les postbacks envoyés aux partenaires par l'application sélectionnée. |
| <span id="reinstall-detection-using-ondevice-storage-ios-only"></span>Détection des réinstallations à l'aide du stockage sur appareil (iOS uniquement) | Détectez les réinstallations sans dépendre des identifiants publicitaires. Pour ce faire, vous devez stocker la dernière date d'installation de l'app sur le stockage local sécurisé de l'appareil (dans iOS, Keychain). Déterminer si une installation était une réinstallation ou une nouvelle installation vous permet de dédupliquer les réinstallations de vos NOI, ce qui rend l’analyse d’attribution plus précise. |
| <span id="ios-103-redirect-fallback"></span>Redirection de secours iOS 10.3 | [Obsolète] Pour iOS 10.3 et +. Nous avons simplifié le flux pour les utilisateurs iOS et ce paramètre n'est désormais plus utilisé. <Anchor target="_blank" href="/marketers/fr/docs/uri-scheme-fallback-for-ios">Redirections IOS</Anchor>.<br /><br />Cette option est uniquement disponible pour les apps iOS. |
| <span id="change-app-name"></span>Modifier le nom de l'application | <ul><li>L'administrateur de votre compte peut changer le nom de votre app, qui se sera ainsi modifiée sur le tableau de bord et dans les rapports de données. Cette option est particulièrement utile si vous disposez de plusieurs versions de la même application, par exemple pour des raisons de distribution régionale.</li><li>Cette modification agit sur l'affichage de l'app. L'ID d'app, utilisé pour identifier l'app lorsque vous utilisez plusieurs API AppsFlyer, **reste identique**.</li><li>Les noms sont limités à 50 caractères.</li></ul> |
| <span id="outofstore-app-url"></span>URL d'app hors store | <ul><li>Définir l'URL de téléchargement de l'app utilisée pour remplir les liens d'attribution.</li><li>Ce paramètre ne modifie pas les liens d'attribution générés précédemment.</li></ul>**Limitation**: l'option ne s'affichera pas du tout si vous n'avez pas défini l'URL lors de l'ajout de l'app. Dans ce cas, voyez avec votre CSM ou contactez [hello@appsflyer.com](mailto:hello@Appsflyer.com) pour que nous le définissions pour vous. .<br /><br />Cette option est uniquement disponible pour les apps Android. |

<div id="see-also" />

> 📄 **À consulter également**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/retargeting-attribution-guide">Guide d'attribution de retargeting</Anchor>
> * <Anchor target="_blank" href="/marketers/fr/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">Attribution de recherche organique</Anchor>

<div data-zendesk-anchors="app-settings=param%C3%A8tres-dapplication 01ECHQME56X51MDW9TMA6DBNCK=param%C3%A8tres-dapplication general-app-settings=param%C3%A8tres-g%C3%A9n%C3%A9raux-de-lapp h_01HAVS8CVPQKSDKCEM3YHHJ99Y=param%C3%A8tres-g%C3%A9n%C3%A9raux-de-lapp reporting-tools-impacted-by-app-currency=outils-de-reporting-impact%C3%A9s-par-la-devise-de-lapp h_01HAVS8CVQESWAQXKDW5SNVHCJ=outils-de-reporting-impact%C3%A9s-par-la-devise-de-lapp attribution-settings=param%C3%A8tres-dattribution h_01HAVS8CVQN1YYTT7S49VGB3J0=param%C3%A8tres-dattribution advanced-settings=param%C3%A8tres-avanc%C3%A9s h_01HAVS8CVQTKXVXSMT5KNYZ3T4=param%C3%A8tres-avanc%C3%A9s h_01HDPCC9465DR4A3CCXYQC2M56=%C3%A0-consulter-%C3%A9galement" />
