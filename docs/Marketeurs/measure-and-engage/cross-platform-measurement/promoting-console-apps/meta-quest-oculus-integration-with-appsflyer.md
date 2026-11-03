---
title: Intégration de Meta Quest (Oculus) avec AppsFlyer
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
  created_at: '2022-12-08T10:10:00Z'
  edited_at: '2024-05-26T08:51:09Z'
  id: 11241398279569
  locale: fr
  section: Promoting Console apps
  section_id: 15329052471057
  url: https://support.appsflyer.com/hc/fr/articles/11241398279569
---
> **En bref :** Intégrez votre application Meta Quest (Oculus) à AppsFlyer pour recevoir des données d’attribution et d’événement pour vos campagnes sur Meta Quest (Oculus).

## À propos de l’attribution de Meta Quest (Oculus)

Le système d’exploitation Meta Quest (Oculus) pour les jeux fonctionne sur tous les appareils Meta Quest (Oculus).

Les applications exécutées sur Meta Quest peuvent s’intégrer à AppsFlyer via l’API ou le SDK S2S pour recevoir des  données d’attribution et des mesures de performance sur les sources et les campagnes qui génèrent des événements ouverts et intégrés aux applications (in-app events). Les marketeurs s’appuient sur ces informations pour mesurer et optimiser les activités marketing.

## Procédures d'intégration

Le tableau suivant répertorie les tâches requises pour intégrer votre application Meta Quest (Oculus) à AppsFlyer. 

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
        Personnes concernées
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Configuration de l’application
      </td>
      <td>
        * <Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Créer un compte AppsFlyer</Anchor>
        * <Anchor target="_blank" href="/marketers/fr/docs/user-management">Ajouter des utilisateurs de compte avec les autorisations appropriées</Anchor>
        * <Anchor target="_blank" href="/marketers/fr/docs/adding-an-app-to-appsflyer">Ajouter votre application Meta Quest (Oculus) dans AppsFlyer</Anchor>
      </td>
      <td>
        Marketeur
      </td>
    </tr>
    <tr>
      <td>
        Intégration du SDK avec votre application (via S2S ou SDK)
      </td>
      <td>
        Il existe deux méthodes d’intégration que vous pouvez utiliser : S2S et SDK.

        Pour la méthode S2S, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-4">intégrez l’API AppsFlyer</Anchor> dans votre application avec des commandes pour signaler les événements suivants à AppsFlyer.

        * Premières ouvertures
        * Événements in-app
        * Sessions

        Remarque :

        * Les premières ouvertures d’applications doivent être signalées avant les événements et les sessions in-app.
        * Pour le `device_ids` paramètre, sélectionner le type `custom`.
          * L’ID `custom` généré pour les <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_first-open-app-platform-app-id">premières ouvertures</Anchor> doit correspondre à vos <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_inapp-app-platform-app-id">événements dans l’application (in-app events)</Anchor> et à votre <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_session-app-platform-app-id">ID de session</Anchor> .
          * Envoyer des événements à l’aide de l’API. Indiquer à votre développeur les événements à envoyer. Vérifier que lorsque vous configurez l’API, vous configurez et mappez les événements à envoyer à AppsFlyer.
          * Pour générer des rapports sur les engagements avec les médias propriétaires, intégrez l’API d’engagement par <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">impression.</Anchor>

        Pour la méthode SDK, il existe deux versions : <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/meta-quest2-unity">Unity</Anchor> et <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/meta-quest2-unreal">Unreal</Anchor>.

        **Remarque** :

        Si vous disposez d’une base d’utilisateurs existante et que vous souhaitez donc que la première session soit considérée comme une session et non comme une installation, le développeur peut utiliser la méthode `skipFirst=true`.
      </td>
      <td>
        Développeur d'apps
      </td>
    </tr>
    <tr>
      <td>
        Configuration de la page de destination multi-plateforme
      </td>
      <td>
        **Recommandé :** Une page de destination multi-plateforme exécutant le script intelligent AppsFlyer vous permet d’effectuer l’attribution Web-to-app. Ce process est notamment recommandé lorsque votre campagne fait la promotion d’une application également disponible sur d’autres plateformes, comme Epic et Native PC.

        <Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">En savoir plus sur les pages de destination multi-plateformes</Anchor>

        <Anchor target="_blank" href="/marketers/fr/docs/cross-platform-landing-pages-with-smart-script">Découvrir comment configurer une page de destination multi-plateforme</Anchor>

        **Remarque** :

        Pour Meta Quest, les paramètres suivants sont requis :

        * **Plateforme** : Quest
        * **QUEST\_APP\_ID** : L’ID de l’application Quest Store.  
          Pour Quest 2, il s’agit du numéro dans l’URL de la boutique, par exemple :

          ```http
          https://www.oculus.com/experiences/quest/XXXXXXXXXXXXXXXX/
          ```

          où **XXXXXXXXXXXXXXXX** est votre ID d’application unique.
        * **media\_source**

        Les paramètres suivants ne sont pas obligatoires mais recommandés :

        * **campagne**
        * **ad**
        * **ad\_set**
        * **storefront\_redirect\_url**: L’URL complète de la vitrine Oculus de votre application, y compris votre **QUEST\_APP\_ID**. Par exemple,
      </td>
      <td>
        Marketeur (peut nécessiter l’aide d’un développeur)
      </td>
    </tr>
    <tr>
      <td>
        Configuration du lien
      </td>
      <td>
        <Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-direct-attribution-links">Découvrir comment créer des liens d’attribution directe</Anchor>
      </td>
      <td>
        Marketeur
      </td>
    </tr>
    <tr>
      <td>
        Paramétrage/affichage des données du rapport
      </td>
      <td>
        <Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-attribution-concepts#disponibilité-des-données">En savoir plus sur la disponibilité des données dans les tableaux de bord et les rapports</Anchor>
      </td>
      <td>
        Marketeur/Ingénieur data
      </td>
    </tr>
  </tbody>
</Table>

<div id="traits-and-limitations" />

<Accordion title="Caractéristiques et limitations">

| Caractéristique | Remarques |
| --- | --- |
| Retargeting | Non pris en charge actuellement |
| Données de coûts | Les données de coût doivent être envoyées via  <Anchor target="_blank" href="/marketers/fr/docs/import-cost-data">Cost Import</Anchor> en utilisant la méthode de téléchargement de fichier par e-mail. |

</Accordion>

> 📄 **À consulter également**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-attribution-concepts">Aperçu des plateformes CTV, PC et consoles</Anchor>

<div data-zendesk-anchors="about-meta-quest-attribution=%C3%A0-propos-de-lattribution-de-meta-quest-oculus 01H7Z1MK9JHA4C5CB7YME4AJMA=%C3%A0-propos-de-lattribution-de-meta-quest-oculus integration-procedures=proc%C3%A9dures-dint%C3%A9gration 01H7Z1MK9JNRKAY9VNH5RTF03F=proc%C3%A9dures-dint%C3%A9gration 01H7Z1MK9KXFY4XVPCDSJPQ26N=traits-and-limitations h_01HE0T79YSNWGB3W4S7WEBW1B5=%C3%A0-consulter-%C3%A9galement" />
