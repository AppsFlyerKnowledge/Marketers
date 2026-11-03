---
title: Générateur d'événements in-app
metadata:
  keywords:
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2022-11-08T12:47:30Z'
  edited_at: '2023-11-06T08:36:59Z'
  id: 10457123447953
  locale: fr
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/fr/articles/10457123447953
---
> **En bref :** créez automatiquement le code d'une app (native Android et iOS, Unity) pour envoyer des événements in-app en définissant les noms et le contenu des événements selon la spécificité de votre activité.

## Introduction

Les événements in-app sont indispensables aux propriétaires d'app, ils permettent **de mesurer la qualité des utilisateurs issus de différentes sources** en fonction des actions qu'ils réalisent après avoir installé l'application. Les événements sont également souvent utilisés pour réaliser des campagnes de marketing basées sur le CPA.

Différents rôles sont impliqués dans la création et l'intégration des événements in-app. D'abord le marketeur/gestionnaire de produits qui définit le contenu de l'ensemble d'événements en fonction de l'activité de l'entreprise, puis un ou plusieurs développeurs mobile  qui sont souvent requis pour implémenter l'API d'événements in-app dans les applications.

Le <Anchor target="_blank" href="https://evgen.appsflyer.com/">générateur d'événements in-app</Anchor> AppsFlyer **permet d'accompagner efficacement cette collaboration marketeur-développeur**.

En utilisant le générateur d'événements in-app, les marketeurs peuvent :

* Utiliser un **ensemble prédéfini d'événements recommandés** et de paramètres en lien avec leur verticale.
* Ajouter ou supprimer des événements/paramètres prédéfinis ou personnalisés, des descriptions, des déclencheurs et des exemples de référence.
* **Envoyer le code généré automatiquement** à leurs développeurs mobile Android et iOS, **ce qui permet à ces derneirs d'écoomiser beaucoup d'heures de travail,** de messages inutiles ou d'erreurs.
* **Réutiliser le fruit de leur travail** s'ils décident ensuite de mettre à jour les événements, d'en ajouter de nouveaux ou d'ajouter d'autres applications.

## Utiliser le générateur d'événements in-app

**Le générateur d'événements in-app permet de créer un ensemble d'événements pour une nouvelle application, ou de mettre à jour un ensemble d'événements existant.**

### Créer un nouvel ensemble d'événements

**Pour créer un nouvel ensemble d'événements :**

1. Rendez-vous dans <Anchor target="_blank" href="https://evgen.appsflyer.com/">Générateur d'événements in-app</Anchor> et saisissez le nom de votre application.
2. Sélectionnez une verticale ou importez l'ensemble d'événements depuis une application similaire via le fichier JSON que vous aurez téléchargé.
3. Ajoutez ou supprimez les événements et paramètres, selon les besoins de votre entreprise.
4. Cliquez sur le bouton **`< />` Code** pour afficher et copier le code généré à l'attention de vos développeurs : Java (Android natif), Obj-C/Swift (iOS natif), ou C# (Unity).
5. Cliquez sur **Télécharger le .zip** pour enregistrer l'ensemble d'événements si vous souhaitez l'utiliser plus tard, par exemple avec vos collègues ou développeurs.

### Mettre à jour d'un ensemble d'événements existant

**Pour mettre à jour un ensemble d'événements existant :**

1. Rendez-vous dans <Anchor target="_blank" href="https://evgen.appsflyer.com/">Générateur d'événements in-app</Anchor>.
2. Importez un ensemble d'événements  avec le fichier JSON que vous avez extrait de votre application.
3. Ajoutez ou supprimez les événements et paramètres, selon les besoins de votre entreprise.
4. Cliquez sur le bouton **`< />` Code** pour afficher et copier le code généré à l'attention de vos développeurs : Java (Android natif), Obj-C/Swift (iOS natif), ou C# (Unity).
5. Cliquez sur **Télécharger le .zip** pour enregistrer l'ensemble d'événements si vous souhaitez l'utiliser plus tard, par exemple avec vos collègues ou développeurs.

### Ajout d'événements

**Pour ajouter un nouvel événement à l'ensemble d'événements :**

1. Cliquez sur le bouton  **+ événement**. Le nouvel événement apparaît en bas de l'ensemble d'événements.
2. Sélectionnez un événement prédéfini  dans la liste des événements qui vous sont proposés (recommandé), ou cliquez sur **Personnaliser** pour définir votre propre nom d'événement. Vérifiez que le nom de l'événement n'apparait pas déjà dans l'ensemble d'événements.
3. Saisissez l'objectif de l'événement, en décrivant le scénario d'entreprise.
4. Saisissez l'action qui déclenche l'événement, en précisant à quel moment du parcours de l'utilisateur l'événement doit être envoyé. Cette précision sera ajoutée sous forme de commentaire dans le code généré pour que les développeurs sachent tout de suite de quoi il s'agit.
5. [Optionnel] Ajoutez un ou plusieurs paramètres à l'événement.

### Ajouter des paramètres

**Pour ajouter un nouveau paramètre à l'ensemble d'événements :**

1. Cliquez sur le bouton  **+ Ajouter un paramètre** dans l'événement concerné.
2. Sélectionnez un paramètre prédéfini  dans la liste des paramètres proposés (recommandé).
3. Vous pouvez aussi cliquer sur **Personnalisé** pour définir votre propre nom de paramètre (pressez **Entrée** pour valider).
4. Saisissez une ou plusieurs valeurs de paramètres communes à titre de référence.
5. Pour aider vos développeurs, donnez une description globale, le type de champ ou la source correspondante à la valeur du paramètre dans votre application. Cela apparaîtra sous forme de commentaire dans le code généré pour chacun des paramètres d'événement.

**Remarque** :  <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview#predefined-and-custom-events">utiliser un nom prédéfini</Anchor> permet de mapper automatiquement les événements et paramètres aux partenaires , c'est donc la méthode à privilégier.

> 📄 **À consulter également**
>
> * Tableau de bord des événements

<div data-zendesk-anchors="h_01HE7T0ZA12E7KHS7WBQ757KF1=introduction using-the-inapp-event-generator=utiliser-le-g%C3%A9n%C3%A9rateur-d%C3%A9v%C3%A9nements-in-app h_01HE7T0ZA2A1KS4NF43GRZB87X=utiliser-le-g%C3%A9n%C3%A9rateur-d%C3%A9v%C3%A9nements-in-app creating-a-new-event-set=cr%C3%A9er-un-nouvel-ensemble-d%C3%A9v%C3%A9nements h_01HE7T0ZA2KQ44P40Y028VVA4K=cr%C3%A9er-un-nouvel-ensemble-d%C3%A9v%C3%A9nements updating-an-existing-event-set=mettre-%C3%A0-jour-dun-ensemble-d%C3%A9v%C3%A9nements-existant h_01HE7T0ZA2P2WZ07CT880ZSK0Z=mettre-%C3%A0-jour-dun-ensemble-d%C3%A9v%C3%A9nements-existant adding-events=ajout-d%C3%A9v%C3%A9nements h_01HE7T0ZA2Z3D3J014E7E0T13X=ajout-d%C3%A9v%C3%A9nements adding-parameters=ajouter-des-param%C3%A8tres h_01HE7T0ZA2KAH7N44EQ9W5BH5G=ajouter-des-param%C3%A8tres h_01HE7T4ZR4AY2J71B3PJKJP490=%C3%A0-consulter-%C3%A9galement" />
