---
title: Intégration de Steam à AppsFlyer
metadata:
  keywords:
    - CTV
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2022-12-08T10:02:09Z'
  edited_at: '2024-08-26T13:30:53Z'
  id: 11241130508433
  locale: fr
  section: Promoting Desktop apps
  section_id: 15329004312593
  url: https://support.appsflyer.com/hc/fr/articles/11241130508433
---
> **En bref :** intégrez votre Steam/app de gaming à AppsFlyer pour recevoir les données d'attribution et d'événements de vos campagnes Steam. L'intégration de Steam prend en charge l'attributionet l'enregistrement des événements in-app pour les apps Steam présentes dans l'appareil Steam de l'utilisateur.

<div id="about-steam-attribution" />

## À propos de l'attribution Steam

Steam fonctionne sur les appareils Windows et Mac, Steam Deck et autres appareils Steam OS.

Les applications exécutées sur Steam peuvent s’intégrer à AppsFlyer via l’API ou le SDK S2S pour recevoir les  données d’attribution et mesures des performances des sources et campagnes qui génèrent des ouvertures d’app et des événements in-app. Les marketeurs s'appuient sur ces informations pour mesurer et optimiser leurs activités marketing.

<div id="example-attribution-flow" />

### Exemple de processus d'attribution

Voici un exemple de flux qui illustre les étapes les plus importantes du parcours de l'utilisateur, de l'engagement publicitaire à l'attribution. Il utilise la page d'accueil multi-plateforme recommandée par AppsFlyer. **Remarque** : Même si nous vous conseillons d'utiliser la page d'accueil multi-plateforme, vous pouvez aussi utiliser des liens d'attribution directs.

![Steam_user_journey.jpg](https://files.readme.io/4979821043af1ed3e662b55c84df10a17a863e79084d050c478fa31767ed8eaa-51473918246929.jpg)

1. Point de contact marketing : Les clients interagissent avec votre marque par le biais de points de contact marketing, en ligne ou hors ligne. Il peut s'agir d’e-mails ou de lettres d'information, de posts sociaux, de sites web mobile, etc.
2. Page d'accueil de gaming : la page d'accueil de gaming dirige les clients vers votre page de jeu Steam. Cette étape est importante pour collecter les paramètres UTM et autres paramètres URL afin d'attribuer les clients du clic/de l'installation aux sources média d'origine, ou à vos sources média propriétaire.  
   La page d'accueil sert également à fournir des liens vers les différentes plateformes que votre jeu prend en charge. Par exemple, vous pouvez avoir des liens vers votre page Xbox, Microsoft Store et Steam sur votre page d'accueil.  
   ![awesome_game.png](https://files.readme.io/37cabff10a2e0a721b4d2901e7df47f53a7dedff25bdac80b97003b60eaef430-51473918248465.png)
3. <span id="marketing-touchpoint"></span>Page de l'application Steam : il s'agit de votre page d’accueil Steam, elle héberge votre app Steam que les clients peuvent télécharger.
4. Installation du jeu : l'utilisateur installe le jeu, ce qui déclenche l'attribution et l'enregistrement d'événements et de sessions in-app.

<div id="integration-procedures" />

## Étapes de l’intégration

Le tableau suivant indique la marche à suivre pour intégrer votre application Xbox à AppsFlyer.

<Table>
  <thead>
    <tr>
      <th>
        Tâche
      </th>
      <th>
        Actions
      </th>
      <th>
        Personne responsable
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Configuration de l'app
      </td>
      <td>
        * <Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Créer un compte AppsFlyer</Anchor>
        * <Anchor target="_blank" href="/marketers/fr/docs/user-management">Ajouter des utilisateurs de compte avec les autorisations nécessaires</Anchor>
        * <Anchor target="_blank" href="/marketers/fr/docs/adding-an-app-to-appsflyer">Ajouter votre application Steam à AppsFlyer</Anchor>
      </td>
      <td>
        Marketeur
      </td>
    </tr>
    <tr>
      <td>
        Intégration du SDK à votre application (via S2S ou SDK)
      </td>
      <td>
        Il existe deux méthodes d’intégration que vous pouvez suivre : S2S et SDK.

        Pour la méthode S2S, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/pc-console-ctv-api-overview">intégrez l'API AppsFlyer dans votre app avec des commandes visant à rapporter les événements suivants à AppsFlyer.</Anchor>

        * Premières ouvertures
        * Événements in-app
        * Sessions

        **Remarque** :

        * Les premières ouvertures de l'application doivent être rapportées avant les événements in-app et les sessions.
        * Pour le paramètre `platform`, sélectionnez `steam`.
        * Pour le paramètre `device_ids`, sélectionnez le type `custom`.
          * L’ID `custom` généré pour les <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_first-open-app-platform-app-id">premières ouvertures</Anchor> doit matcher vos <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_inapp-app-platform-app-id">événements in-app</Anchor> et votre ID de <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_session-app-platform-app-id">session</Anchor>.
        * Envoyez les événements via l'API. Indiquez à votre développeur quels événements doivent être envoyés. Vérifiez que lorsque vous configurez l'API, vous configurez et mappez les événements à envoyer à AppsFlyer.
        * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">Pour rapporter les engagements des médias propriétaire, intégrez l'API d'engagement par impression.</Anchor>

        Pour la méthode SDK, il existe trois versions : native <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/steam-vanilla">C++</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unreal-steam">Unreal</Anchor> et <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unity-steam">Unity</Anchor>.

        **Remarque** :

        Si vous disposez d’une base d’utilisateurs existante et que vous souhaitez que la première session soit considérée comme une session et non comme une installation, le développeur peut utiliser la méthode `skipFirst=true`.
      </td>
      <td>
        Développeur de l’app
      </td>
    </tr>
    <tr>
      <td>
        Configuration de la page d’accueil multi-plateforme
      </td>
      <td>
        **Recommandations :** Une page d’accueil multi-plateforme exécutant le script intelligent AppsFlyer vous permet d’effectuer l’attribution Web-to-app. Ce procédé est recommandé si votre campagne fait la promotion d’une app également disponible sur d’autres plateformes, comme Epic ou Native PC.

        <Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">En savoir plus sur les pages de d’accueil multi-plateformes</Anchor>

        <Anchor target="_blank" href="/marketers/fr/docs/cross-platform-landing-pages-with-smart-script">Savoir comment configurer une page d’accueil multi-plateforme</Anchor>

        **Remarque** :

        Pour Steam, les paramètres suivants sont demandés :

        * **platform** : steam
        * **steam\_app\_id** : ID de la page de l'application.  

          Vous pouvez trouver votre ID d’app unique en le copiant dans la barre d'URL, ou en allant sur <Anchor target="_blank" href="https://steamdb.info/">https://steamdb.info/</Anchor> et en recherchant votre jeu. ex :

          ```http
          https://store.steampowered.com/app/12345678/
          ```

          où **12345678** est l'ID unique de votre app.
        * **media\_source**

        Les paramètres suivants ne sont pas obligatoires, mais recommandés :

        * **campaign**
        * **ad**
        * **ad\_set**
        * **storefront\_redirect\_url**: L'URL complète de la vitrine Steam pour votre app, y compris votre **steam\_app\_id.** Par exemple, `https://store.steampowered.com/app/12345678/`
      </td>
      <td>
        Marketeur (peut nécessiter l’aide du développeur)
      </td>
    </tr>
    <tr>
      <td>
        Configuration du lien
      </td>
      <td>
        Si vous n'utilisez pas de page d’accueil multi-plateforme, vous pouvez créer des liens d'attribution directs à placer après les publicités.

        <Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-direct-attribution-links">Savoir comment créer des liens d’attribution directs</Anchor>
      </td>
      <td>
        Marketeur
      </td>
    </tr>
    <tr>
      <td>
        Configuration du rapport/affichage des données
      </td>
      <td>
        <Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-attribution-concepts#disponibilité-des-données">En savoir plus sur la disponibilité des données dans les tableaux de bord et les rapports</Anchor>
      </td>
      <td>
        Marketeur/Ingénieur des données
      </td>
    </tr>
  </tbody>
</Table>

<div id="removing-appsflyer-data-when-uninstalling-the-app" />

### Supprimer les données AppsFlyer lors de la désinstallation de l'app

Pour supprimer toutes les données du SDK AppsFlyer lors de la désinstallation de l'application, demandez à votre développeur de suivre les étapes détaillées [ici.](https://dev.appsflyer.com/hc/docs/steam-vanilla#deleting-appsflyer-data-on-uninstall)

<div id="traits-and-limitations" />

## Caractéristiques et limitations

| Caractéristique | Remarques |
| --- | --- |
| Retargeting | Non pris en charge actuellement |
| Données de coûts | Les données des coûts doivent être envoyées via l’<Anchor target="_blank" href="/marketers/fr/docs/import-cost-data">Ingestion des dépenses publicitaires</Anchor> en utilisant la méthode d’envoi du fichier par e-mail. |

<div id="see-also" />

> 📄 **Articles connexes**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-attribution-concepts">Attribution des plateformes CTV, PC et consoles</Anchor>

<div data-zendesk-anchors="about-steam-attribution=%C3%A0-propos-de-lattribution-steam 01H7Z1DJRW1KPJQ4CZ6T85ASRK=%C3%A0-propos-de-lattribution-steam flow=exemple-de-processus-dattribution 01H7Z1DJRWHB8TQC15WW4FVSHG=exemple-de-processus-dattribution integration-procedures=%C3%A9tapes-de-lint%C3%A9gration 01H7Z1DJRWX54DN2SNS21GPGXB=%C3%A9tapes-de-lint%C3%A9gration removing-appsflyer-data-when-uninstalling-the-app=supprimer-les-donn%C3%A9es-appsflyer-lors-de-la-d%C3%A9sinstallation-de-lapp h_01J3349MAA4J231B6FJ74V3PTB=supprimer-les-donn%C3%A9es-appsflyer-lors-de-la-d%C3%A9sinstallation-de-lapp traits-and-limitations=caract%C3%A9ristiques-et-limitations h_01HDEHMH0HF201TH4XDW691STH=caract%C3%A9ristiques-et-limitations h_01HDP1K6FDDEED5P2WNESST7GE=articles-connexes" />
