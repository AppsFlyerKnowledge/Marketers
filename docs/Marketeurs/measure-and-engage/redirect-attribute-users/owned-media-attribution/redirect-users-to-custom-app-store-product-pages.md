---
title: Redirection vers les pages produit personnalisées de l'App Store
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Agencies
    - OneLink
  created_at: '2021-08-26T07:25:53Z'
  edited_at: '2022-01-02T23:17:36Z'
  id: 4406217556625
  locale: fr
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/fr/articles/4406217556625
---
> **En bref :** redirigez les utilisateurs iOS vers les pages produit personnalisées de votre app dans l'App Store. Optimisez vos campagnes avec les données AppsFlyer sur les pages produit personnalisées.

## Présentation

Avec la sortie d'iOS 15, Apple a introduit des pages produit personnalisées qui permettent aux propriétaires d'app de créer jusqu'à 35 versions supplémentaires de leur page produit App Store avec différentes fonctionnalités ou contenus dans leur app. Les pages produit personnalisées peuvent comporter du texte promotionnel, des captures d'écran et des aperçus différents de ceux de la page produit App Store par défaut.

Vous pouvez utiliser les URL OneLink d'AppsFlyer ou les liens d'attribution d'une seule plateforme pour rediriger les utilisateurs vers ces pages produit personnalisées et créer des parcours contextuels spécifiques pour différents publics cibles.

Les données concernant les pages produit personnalisées sont disponibles dans le tableau de bord AppsFlyer et les rapports de données brutes. Vous pouvez utiliser ces données pour effectuer des tests A/B et optimiser vos campagnes et vos pages produit.

## Disponibilité des données

<Accordion title="Tableau de bord">

Les données agrégées pour les pages produit personnalisées sont disponibles dans le tableau de bord V2.

**Pour afficher les données** :

* Dans le tableau de bord V2, ajoutez la dimension de groupe **Page produit sur le store**.  
  La page produit personnalisée s'affiche dans les graphiques et tableaux du tableau de bord.

</Accordion>

<Accordion title="Données Brutes">

Les données brutes sont disponibles via les <Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview#reporting-tools-characteristics-and-features">outils de rapports AppsFlyer</Anchor>.

Le champ `store_product_page` des rapports indique vers quelle page produit personnalisée un utilisateur donné a été redirigé.

</Accordion>

## Configuration

Pour configurer des redirections vers une page produit personnalisée dans l'App Store, vous pouvez :

* Utiliser l'interface utilisateur de OneLink.
* Ajouter le paramètre `af_ios_store_cpp` à vos URL OneLink ou à vos liens d'attribution à une seule plateforme, la valeur étant l'ID de la page produit personnalisée.

<Accordion title="Utilisation de l'interface utilisateur OneLink">

Conditions préalables :

* Page produit personnalisée créée dans App Store Connect
* <Anchor target="_blank" href="/marketers/fr/docs/create-a-onelink-template#1-creating-a-onelink-template">Template OneLink</Anchor>
* <Anchor target="_blank" href="/marketers/fr/docs/create-a-onelink-template#2-creating-a-custom-attribution-link-for-users">Lien personnalisé OneLink</Anchor>

**Pour ajouter une redirection vers une page produit personnalisée via un lien personnalisé OneLink** :

1. Dans votre lien personnalisé OneLink, allez dans la section **Deep linking et redirections** .
2. Faites défiler jusqu'aux paramètres **Lorsque l'app n'est pas installée**.  

   <Image align="center" alt="" src="https://files.readme.io/21348e79a1cf3eed59d18c8a29d1a48e72ab81ed6209a5112f5bfc9e6ff4d2f4-4413512078993.png" />
3. Pour iOS, assurez-vous que l'option **Rediriger vers** est définie sur App Store.
4. Dans la zone de texte **Page produit personnalisée**, saisissez l'identifiant de votre page produit personnalisée (ppid) tel que défini dans App Store Connect. Par exemple : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
5. Cliquez sur ***Mettre le lien à jour***.

</Accordion>
