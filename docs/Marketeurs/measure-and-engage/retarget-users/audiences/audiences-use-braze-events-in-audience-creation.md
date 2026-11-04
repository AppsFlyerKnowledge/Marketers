---
title: Connexion partenaire entrante — Braze
metadata:
  keywords:
    - Advertisers
    - Premium Feature
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2021-11-17T09:55:26Z'
  edited_at: '2024-11-19T16:53:43Z'
  id: 4411130243217
  locale: fr
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/fr/articles/4411130243217
---
> **En bref :** Transmettez les événements d'engagement des messages Braze aux audiences AppsFlyer et affinez vos définitions d'audience avec eux.

En établissant une connexion entrante entre votre compte Braze et AppsFlyer Audiences, vous intégrez les données des événements d'engagement des messages Braze dans Audiences. Vous pouvez alors utiliser ces données dans les <Anchor target="_blank" href="/marketers/fr/docs/audiences-guide#all-about-rulesets">ensembles de règles</Anchor> pour définir vos audiences.

<div id="important" />

> 🚧 **Conditions préalables**
>
> * Les SDK de Braze et AppsFlyer doivent être intégrés dans votre application.
> * Vous devez être abonné à la fonctionnalité **Currents** dans Braze.

<div id="set-up-the-braze-incoming-connection" />

## Configurer la connexion entrante de Braze

Il y a trois principales étapes pour configurer la connexion entrante de Braze :

1. [Configurer le SDK AppsFlyer](/docs/audiences-use-braze-events-in-audience-creation#set-up-the-appsflyer-sdk)
2. [Créer une connexion entrante dans AppsFlyer](/docs/audiences-use-braze-events-in-audience-creation#create-an-incoming-braze-connection-in-appsflyer)
3. [Créer un Current dans Braze](/docs/audiences-use-braze-events-in-audience-creation#create-a-current-in-braze)

<div id="set-up-the-appsflyer-sdk" />

<Accordion title="Configurer le SDK AppsFlyer">

Pour créer une connexion entrante depuis Braze, le SDK AppsFlyer de vos applications doit être configuré pour transmettre l'**ID externe Braze** de chaque utilisateur à AppsFlyer. Cela peut être fait en utilisant soit :

* Le paramètre ID externe de Braze
* Le champ CUID

<div id="using-a-braze-external-id-parameter" />

#### **Utilisation d’un paramètre ID externe Braze**

Vous pouvez configurer un paramètre dédié pour transmettre l'ID externe Braze à AppsFlyer en utilisant la fonction `setPartnerData` du SDK AppsFlyer. Voici quelques exemples d'utilisation :

<Tabs>
<Tab title="Android">

```java
Map<String, Object> brazeData = new HashMap<>();
partnerData.put("external_user_id", "some-braze-external-id-value");
AppsFlyerLib.getInstance().setPartnerData("braze_int", brazeData);
```

</Tab>

<Tab title="iOS">

```objectivec
NSDictionary *brazeInfo = @{
@"external_user_id":@"some-braze-external-id-value"
};
[[AppsFlyerLib shared] setPartnerDataWithPartnerId:@"braze_int"
partnerInfo:brazeInfo];
```

</Tab>
</Tabs>

<div id="using-the-cuid-field" />

#### **Utilisation du champ CUID**

Il n'est pas nécessaire de configurer un paramètre dédié pour l'ID externe Braze si :

* Vous avez configuré le SDK pour envoyer un <Anchor target="_blank" href="/marketers/fr/docs/customer-user-id-field-cuid">CUID</Anchor> à AppsFlyer pour chaque utilisateur
* Le CUID a la même valeur que l'ID externe Braze

Dans ce cas, vous pouvez simplement sélectionner l'option **CUID** comme paramètre du SDK lors de la [création de votre connexion entrante Braze](/docs/audiences-use-braze-events-in-audience-creation#create-an-incoming-braze-connection-in-appsflyer).

</Accordion>

<div id="create-an-incoming-braze-connection-in-appsflyer" />

<Accordion title="Créer une connexion entrante Braze dans AppsFlyer">

**Suivez ces étapes pour créer une connexion entrante dans AppsFlyer :**

1. Dans AppsFlyer, dans le menu latéral, sélectionnez **Engage** > **Audiences**
2. Sur la page Audiences, allez à l'onglet **Connexions > Entrant** .
3. Cliquez sur le bouton **Nouvelle connexion entrante**.
4. Sélectionnez Braze dans la liste des partenaires disponibles.
5. Cliquez sur le bouton **Enregistrer** pour créer la connexion.  
   La boîte de dialogue des **identifiants de connexion** s'ouvre.
6. Copiez ces identifiants pour configurer la connexion à AppsFlyer Audiences sur la plateforme Braze :
   * ID clé d'accès
   * Clé d'accès secrète
   * Nom du compartiment
   * Chemin du dossier
7. Sélectionnez le paramètre SDK que vous utilisez pour envoyer l'ID externe Braze :
   * ID externe Braze
   * CUID

</Accordion>

<div id="create-a-current-in-braze" />

<Accordion title="Créer un flux dans Braze">

**Suivez ces étapes pour créer un flux dans Braze :**

1. Accédez à la section **Intégration** de la barre de menu à gauche.
2. Cliquez sur **Flux.**
3. Cliquez sur le bouton **Créer un flux**.
4. Sélectionnez **Exportation de données Amazon S3.**
5. Dans la section **Créer une intégration de flux** :
   1. Saisissez un nom pour le flux (par exemple, AppsFlyer Audiences).
   2. Entrez l'email d'une personne de votre équipe que Braze avertira en cas de problème avec les identifiants pour le flux.
6. Dans la section **Identifiants** :
   1. Gardez l'option pour **Clé d'accès secrète AWS** sélectionnée (c'est la valeur par défaut).
   2. Entrez les identifiants que vous avez copiés depuis AppsFlyer dans les champs appropriés.
   3. Laissez l'option **Activer le chiffrement** décochée.
7. Sous **Paramètres généraux**, cochez **Inclure les événements des utilisateurs anonymes**.
8. Dans la section **Événements d'engagement des messages**, sélectionnez les événements que vous souhaitez que Braze envoie à AppsFlyer. Consultez la liste des événements pris en charge [ci-dessous](/docs/audiences-use-braze-events-in-audience-creation#événements-pris-en-charge).
9. Dans la section Comportement du client et événements de l'utilisateur, laissez l'option **Suivre le comportement du client et événements utilisateur** désactivée.
10. Cliquez sur le bouton **Lancer le flux** pour enregistrer la configuration et commencer à envoyer les événements d'engagement de messages Braze aux audiences.

<div id="supported-events" />

#### événements pris en charge

<div id="note" />

> 📘 **Événements Braze pris en charge**
>
> * Changement d'état du groupe d'abonnement
> * Clic sur l'email
> * Ouverture d'email
> * Envoi d'email
> * Livraison d'email
> * Email marqué comme spam
> * Désinscription par email
> * Rebond d'email
> * Rebond doux d'email
> * Ouverture de notification push
> * Envoi de notification push
> * Rebond de notification push
> * Notification push iOS au premier plan
> * Envoi de SMS\/MMS

</Accordion>

<div id="using-braze-data-in-audiences" />

## Utilisation des données Braze dans Audiences

Une fois la connexion entrante de Braze configurée, les événements d'engagement que vous avez définis apparaîtront comme options dans les [filtres de règles](/docs/audiences-use-braze-events-in-audience-creation/%20/docs/audiences-guide#all-about-rulesets) pour définir les audiences.

[altensemble\_règles\_braze\_audiences.pngalt](https://support.appsflyer.com/hc/article_attachments/4886242115089)

**Remarque :** Il faut environ 24 heures pour que les événements d'engagement de messages Braze soient disponibles dans AppsFlyer après le lancement du flux dans Braze.

<div data-zendesk-anchors="h_01HKW0BS5H5FS7MXZPHBARK3VR=conditions-pr%C3%A9alables set-up-the-braze-incoming-connection=configurer-la-connexion-entrante-de-braze h_01HKW0BS5H1ANWAJZTVBWDQHJH=configurer-la-connexion-entrante-de-braze h_01HKW0BS5HKREHBKPMQ25AYTMH=set-up-the-appsflyer-sdk using-a-braze-external-id-parameter=utilisation-dun-param%C3%A8tre-id-externe-braze h_01HKW0BS5HGB2RYGWNXT1M163C=utilisation-dun-param%C3%A8tre-id-externe-braze using-the-cuid-field=utilisation-du-champ-cuid h_01HKW0BS5HQJZRR60VKBCWGHQB=utilisation-du-champ-cuid h_01HKW0BS5H6P7WTT6XBYF7HP3X=create-an-incoming-braze-connection-in-appsflyer h_01HKW0BS5J83HMXPWB6VNKD6P1=create-a-current-in-braze supported-events=%C3%A9v%C3%A9nements-pris-en-charge h_01HKW0BS5JM8A9XFVX22KWFE3H=%C3%A9v%C3%A9nements-pris-en-charge h_01HKW0BS5J6V57BDHKRY9A5XZE=%C3%A9v%C3%A9nements-braze-pris-en-charge using-braze-data-in-audiences=utilisation-des-donn%C3%A9es-braze-dans-audiences h_01HKW0BS5JTZQ71HFE305ZT1CS=utilisation-des-donn%C3%A9es-braze-dans-audiences" />
