---
title: Intégration native des PC avec AppsFlyer
metadata:
  keywords:
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2023-06-20T05:52:13Z'
  edited_at: '2024-10-12T17:30:56Z'
  id: 16308237781649
  locale: fr
  section: Promoting Desktop apps
  section_id: 15329004312593
  url: https://support.appsflyer.com/hc/fr/articles/16308237781649
---
> **En bref :** Intégrez votre jeu ou application PC à AppsFlyer pour recevoir des données d'attribution et d'événements pour vos campagnes PC. L'intégration Native PC prend en charge l'attributionet l'enregistrement d'événements in-app pour les applications PC (en d'autres termes, l'attribution et l'enregistrement sur l'ordinateur de l'utilisateur).

<div id="about-native-pc-attribution" />

## À propos de l'attribution Native PC

Native PC fonctionne sur tous les appareils Windows, grâce à l'installation d'une extension de fichier .EXE ou .MSI.

Le fonctionnement est différent de celui du <Anchor target="_blank" href="/marketers/fr/docs/windows-sdk-integration-for-developers">SDK Windows AppsFlyer 2.4.1</Anchor> qui fonctionne avec les installations à partir du Microsoft App Store, des téléphones Windows et de l'UWP.

Les applications exécutées sur Steam peuvent s’intégrer à AppsFlyer via l’API ou le SDK S2S pour recevoir les données d’attribution et mesures des performances des sources et campagnes qui génèrent des ouvertures d’app et des événements in-app. Les marketeurs s'appuient sur ces informations pour mesurer et optimiser leurs activités marketing.

<div id="example-attribution-flow" />

### Exemple de processus d'attribution

Voici un exemple de flux qui illustre les étapes les plus importantes du parcours de l'utilisateur, de l'engagement publicitaire à l'attribution. Il utilise la page d'accueil multi-plateforme recommandée par AppsFlyer. **Remarque** : Même si nous vous conseillons d'utiliser la page d'accueil multi-plateforme, vous pouvez aussi utiliser des liens d'attribution directs.

<Image align="center" alt="User_windows.jpg" src="https://files.readme.io/33c9138ef2064832a0bd5d08d52c84bea3e70efb674af362a8ef0d3e5d505db1-small-16332549715217.jpg" />

1. <span id="marketing-touchpoint"></span>Point de contact marketing : Les clients interagissent avec votre marque par le biais de points de contact marketing, en ligne ou hors ligne. Il peut s'agir d’e-mails ou de lettres d'information, de posts sociaux, de sites web mobile, etc.
2. Page d'accueil de gaming : une page d'accueil de gaming qui dirige les clients vers votre page de téléchargement d'application. Cette étape est importante pour collecter les paramètres UTM et autres paramètres URL afin d'attribuer les clients du clic/de l'installation aux sources média d'origine, ou à vos sources média propriétaire.  
   La page d'accueil sert également à fournir des liens vers les différentes plateformes que votre jeu prend en charge. Par exemple, vous pouvez avoir des liens vers votre page Xbox, Microsoft Store et Steam sur votre page d'accueil.
3. Page d'application Voici l'URL de votre page d'application Native PC qui héberge votre application pour que les clients puissent la télécharger.
4. Installation du jeu : l'utilisateur installe le jeu, ce qui déclenche l'attribution et l'enregistrement d'événements et de sessions in-app.

<div id="integration-procedures" />

## Étapes de l’intégration

Le tableau suivant répertorie les tâches nécessaires pour intégrer votre application PC à AppsFlyer.

**Remarque :** L'ajout de membres d'équipe et la configuration de rapports dans Data Locker ne sont pas obligatoires.

| Tâche | Actions | Personne responsable |
| --- | --- | --- |
| Configuration de l'app | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Créer un compte AppsFlyer</Anchor></li><li><Anchor target="_blank" href="/marketers/fr/docs/user-management">Ajouter des utilisateurs de compte avec les autorisations nécessaires</Anchor></li><li><Anchor target="_blank" href="/marketers/fr/docs/adding-an-app-to-appsflyer">Ajoutez votre application PC dans AppsFlyer</Anchor></li></ul> | Marketeur |
| Intégration du SDK à votre application (via S2S ou SDK) | Il existe deux méthodes d’intégration que vous pouvez suivre : S2S et SDK.<br /><br />Pour la méthode S2S, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">intégrez l'API AppsFlyer dans votre app avec des commandes visant à rapporter les événements suivants à AppsFlyer.</Anchor><ul><li>Premières ouvertures</li><li>Événements in-app</li><li>Sessions</li></ul>**Remarque** :<ul><li>Les premières ouvertures de l'application doivent être signalées avant les événements et les sessions in-app.</li><li>Pour le `device_ids` paramètre, sélectionner le type `custom`.<ul><li>L’ID `custom` généré pour les <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_first-open-app-platform-app-id">premières ouvertures</Anchor> doit matcher vos <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_inapp-app-platform-app-id">événements in-app</Anchor> et votre ID de <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_session-app-platform-app-id">session</Anchor>.</li></ul></li><li>Envoyez les événements via l'API. Indiquez à votre développeur quels événements doivent être envoyés. Vérifiez que lorsque vous configurez l'API, vous configurez et mappez les événements à envoyer à AppsFlyer.</li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">Pour rapporter les engagements des médias propriétaire, intégrez l'API d'engagement par impression.</Anchor></li></ul>Pour la méthode SDK, il existe trois versions : native <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/nativepc-vanilla">C++</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unreal-nativepc">Unreal</Anchor> et <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/unity-nativepc">Unity</Anchor>.<br /><br />**Remarque** :<br /><br />Si vous disposez d’une base d’utilisateurs existante et que vous souhaitez que la première session soit considérée comme une session et non comme une installation, le développeur peut utiliser la méthode `skipFirst=true`. | Développeur de l’app |
| Configuration de la page d’accueil multi-plateforme | **Recommandations :** Une page d’accueil multi-plateforme exécutant le script intelligent AppsFlyer vous permet d’effectuer l’attribution Web-to-app. Ce procédé est recommandé si votre campagne fait la promotion d’une app également disponible sur d’autres plateformes, comme Epic ou Steam.<br /><br /><Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">En savoir plus sur les pages de d’accueil multi-plateformes</Anchor><br /><br /><Anchor target="_blank" href="/marketers/fr/docs/cross-platform-landing-pages-with-smart-script">Savoir comment configurer une page d’accueil multi-plateforme</Anchor><br /><br />Pour Native PC, les paramètres suivants sont demandés :<ul><li>**Nom de l'app**<br />Le nom de votre application</li><li>**app\_id**<br />L'identifiant de l'application.</li></ul>Un ID d'app est nécessaire pour AppsFlyer. Les applications Native PC n'ont pas de règles spécifiques concernant l'ID d'application, donc votre développeur peut choisir et créer l'ID d'application de son choix pour votre application. **Recommandations :** Choisissez un identifiant qui vous est familier, mais qui n'est pas susceptible d'être utilisé par des applications. Par exemple, `app-name-is-the-best`.<ul><li>**media\_source**</li></ul>Les paramètres suivants ne sont pas obligatoires, mais recommandés :<ul><li>**campaign**</li><li>**ad**</li><li>**ad\_set**</li></ul> | Marketeur (peut nécessiter l’aide du développeur) |
| Configuration du lien | Si vous n'utilisez pas de page d’accueil multi-plateforme, vous pouvez créer des liens d'attribution directs à placer après les publicités.<br /><br /><Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-direct-attribution-links">Savoir comment créer des liens d’attribution directs</Anchor> | Marketeur |
| Configuration du rapport/affichage des données | <Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-attribution-concepts#disponibilité-des-données">En savoir plus sur la disponibilité des données dans les tableaux de bord et les rapports</Anchor> | Marketeur/Ingénieur des données |

<div id="removing-appsflyer-data-when-uninstalling-the-app" />

### Supprimer les données AppsFlyer lors de la désinstallation de l'app

Pour supprimer toutes les données du SDK AppsFlyer lors de la désinstallation de l'application, demandez à votre développeur de suivre les étapes détaillées [ici.](https://dev.appsflyer.com/hc/docs/nativepc-vanilla#deleting-appsflyer-data-on-uninstall)

<div id="traits-and-limitations" />

## Caractéristiques et limitations

| Caractéristique | Remarques |
| --- | --- |
| Reciblage | Non pris en charge actuellement |
| Données de coûts | Les données des coûts doivent être envoyées via l’<Anchor target="_blank" href="/marketers/fr/docs/import-cost-data">Ingestion des dépenses publicitaires</Anchor> en utilisant la méthode d’envoi du fichier par e-mail. |

<div id="see-also" />

> 📄 **Articles connexes**
>
> * <span id="overview"></span><Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-attribution-concepts">Aperçu des plateformes CTV, PC et consoles</Anchor>

<div data-zendesk-anchors="about-steam-attribution=%C3%A0-propos-de-lattribution-native-pc 01H7Z19FJ5J1CB4ESE55Z32C1C=%C3%A0-propos-de-lattribution-native-pc flow=exemple-de-processus-dattribution 01H7Z19FJ5R869054GDRKHTBJ8=exemple-de-processus-dattribution 01H7Z19FJ54WZ7XV91Y36EKYQ6=marketing-touchpoint integration-procedures=%C3%A9tapes-de-lint%C3%A9gration 01H7Z19FJ5KKPJ88KAQM49FNVA=%C3%A9tapes-de-lint%C3%A9gration removing-appsflyer-data-when-uninstalling-the-app=supprimer-les-donn%C3%A9es-appsflyer-lors-de-la-d%C3%A9sinstallation-de-lapp h_01J3349MAA4J231B6FJ74V3PTB=supprimer-les-donn%C3%A9es-appsflyer-lors-de-la-d%C3%A9sinstallation-de-lapp traits-and-limitations=caract%C3%A9ristiques-et-limitations h_01HF9W8YG149TMQE1F57BG0ZS7=caract%C3%A9ristiques-et-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=articles-connexes" />
