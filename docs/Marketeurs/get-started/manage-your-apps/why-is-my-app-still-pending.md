---
title: "Pourquoi mon app est-elle toujours en attente\_?"
metadata:
  keywords:
    - Google Play
    - App Store
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2018-10-14T07:22:04Z'
  edited_at: '2021-12-12T17:03:51Z'
  id: 360001533885
  locale: fr
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/fr/articles/360001533885
---
> **En bref :** surveillez le statut des apps en attente de publication dans les app stores depuis le tableau de bord AppsFlyer.

Lorsque vous <Anchor target="_blank" href="/marketers/fr/docs/adding-an-app-to-appsflyer">ajoutez votre nouvelle app</Anchor> au tableau de bord AppsFlyer, vous devez indiquer si elle est en attente ou déjà publiée.

Les apps en attente dans AppsFlyer s'affichent de la même manière que les apps publiées. Elles ont des tableaux de bord accessibles et peuvent utiliser toutes les mesures d'attribution. La seule différence est le logo : le logo AppsFlyer s'affiche au lieu du logo de l'app elle-même.

![Pending_App.png](https://files.readme.io/fd280ea8dbcd280aae0a1328d1523f52c51d2f30dc163e7a62deb424ae5bc8ed-360001789338.png)

<div id="whats-happening" />

## Que se passe-t-il ?

AppsFlyer vérifie automatiquement le statut des apps plusieurs fois par jour.

Si votre app n'est toujours pas en ligne dans le store lorsque AppsFlyer vérifie son statut, celle-ci apparaît avec le statut « en attente » dans le tableau de bord. Une fois l'app soumise à iTunes ou Google, son statut est 1 active » et son logo devient le logo d'origine de l'app.

Le statut de l'app dans le tableau de bord n'affecte ni la collecte ni la mesure des données. Si l'app est disponible sur Google Play ou sur l'App Store et que des utilisateurs l'installent et interagissent avec elle, les données des événements d'installation et des événements in-app seront toujours affichées dans le tableau de bord.

<div id="refreshing-the-app-status" />

## Actualisation du statut de l'app

Pour que l'app devienne active, AppsFlyer vérifie son statut dans le store. Si vous êtes certain que l'app est publiée dans Google Play ou iTunes, mais qu'elle apparaît toujours en attente dans le tableau de bord, l'administrateur peut vérifier manuellement son statut.

**Prérequis** : disponible pour l'administrateur du compte.

**Pour mettre à jour manuellement le statut de l'app :**

1. Dans le coin supérieur droit du tableau de bord, cliquez sur **Mes apps**.  
   ![app-refersh-status.png](https://files.readme.io/d995ea3ee3523a8f0d4854f9ec116efc33c892694d56334c483b7d9fa6da8d64-360001704577.png)
2. À côté de l'app en attente, cliquez sur **Actualiser le statut.** Si le statut de l'app n'est pas modifié, celle-ci affiche toujours En attente. S'il a été mis à jour, l'app affiche En ligne et le logo est actualisé.

<div id="store-country" />

## Pays du store

Certaines apps sont uniquement disponibles dans Google Play ou iTunes pour certains pays. **Il est important de définir le pays correct pour une app,** afin qu'AppsFlyer puisse vérifier son statut et le mettre à jour.

### iOS

Lorsque vous <Anchor target="_blank" href="/marketers/fr/docs/adding-an-app-to-appsflyer">ajoutez une app iOS</Anchor> à votre tableau de bord AppsFlyer, vous choisissez le pays Apple Store dans lequel l'app est publiée. Si le pays choisi n'est pas correct, AppsFlyer ne peut pas mettre à jour le statut de l'app, même si elle est publiée.

Pour modifier le pays de l'Apple Store :

1. Dans le tableau de bord de votre app, cliquez sur **Réglages de l'app** dans le menu de gauche.
2. Sous **Pays de l'App Store**, choisissez le pays approprié.
3. Faites défiler vers le bas et cliquez sur **Enregistrer les paramètres**.
4. Si l'app apparaît toujours en attente, [cliquez sur **Actualiser le statut**](/docs/why-is-my-app-still-pending#refreshing-the-app-status).

### Android

<Anchor target="_blank" href="/marketers/fr/docs/adding-an-app-to-appsflyer">Lorsque vous ajoutez une app Android</Anchor> à votre tableau de bord AppsFlyer, il n'y a pas d'option pour choisir un pays Google Play. Les États-Unis sont choisis par défaut. Si votre app n'est pas publiée dans le Google Play Store américain, il est important de définir le pays correct afin qu'AppsFlyer puisse vérifier le statut de l'app et le mettre à jour.

Pour modifier le pays Google Play :

1. Dans le tableau de bord de votre app, cliquez sur **Réglages de l'app** dans le menu de gauche.
2. Sous **Pays de l'App Store**, choisissez le pays approprié.
3. Faites défiler vers le bas et cliquez sur **Enregistrer les paramètres**.
4. Si l'app apparaît toujours en attente, [cliquez sur **Actualiser le statut**](/docs/why-is-my-app-still-pending#refreshing-the-app-status).