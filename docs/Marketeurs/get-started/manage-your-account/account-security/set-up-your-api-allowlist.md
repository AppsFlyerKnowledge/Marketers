---
title: Configurez votre liste d'autorisation API
metadata:
  keywords:
    - OneLink
    - API Policy
    - fraud
    - Advertisers
    - Agencies
    - API access
    - attribution link
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
  created_at: '2021-08-22T13:50:14Z'
  edited_at: '2024-09-19T13:10:10Z'
  id: 4406016140817
  locale: fr
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/fr/articles/4406016140817
---
> **En bref :** Protégez votre compte AppsFlyer en définissant une liste d'autorisations API.

## [altListe d'autorisations APIalt](https://support.appsflyer.com/hc/article_attachments/4423224122385)

## Aperçu

Protégez vos données contre tout accès non autorisé en configurant une liste d'autorisations API spécifiant les adresses IP pouvant effectuer des appels API sur votre compte AppsFlyer. Une fois votre liste d'autorisations active, seuls les appels API provenant de ces adresses IP seront autorisés, tous les autres seront refusés.

> 📘 **Remarque**
>
> * Seuls les administrateurs peuvent accéder et gérer la liste d'autorisations.
> * L'utilisation de la liste est facultative et désactivée par défaut.
> * L'activation de la liste d'autorisations s'effectue au niveau du compte et s'applique à toutes les applications du compte.

## Configurer votre liste d'autorisations API

<div id="set-up-the-api-allowlist" />

<Accordion title="Configurer la liste">

altAppsFlyerAdmin\_us-fr.pngaltPour configurer et activer la liste d'autorisations API :

1. Depuis la barre supérieure, ouvrez le menu du compte (liste déroulante de l’adresse e-mail) > **Centre de sécurité**.
2. Dans la section Liste d'autorisations API, cliquez sur **Gérer la liste d'autorisations API**.
3. Entrez une adresse IP ou une plage d'adresses IP au format standard :
   * Exemples : `192.168.1.1`, `185.114.120.140`
   * Pour saisir une plage d'adresses IP, utilisez ce format : `185.114.120.1/32`(où `185.114.120.1` est la première adresse de la plage et `185.114.120.32` la dernière adresse de la plage).
4. Cliquez sur **Appliquer.**
5. [Facultatif] Cliquez sur **+ Ajouter** pour ajouter une adresse IP ou une plage supplémentaire.
6. Cliquez sur le bouton **Enregistrer la liste**.
7. Définissez la liste sur **Active.**

   **Remarque :** La liste doit contenir au moins une adresse IP ou une plage avant de pouvoir être enregistrée et activée.

</Accordion>

<div id="edit-the-api-allowlist" />

<Accordion title="Modifier la liste">

Vous pouvez ajouter ou supprimer des adresses IP de la liste à tout moment, qu'elle soit active ou non.

altAppsFlyerAdmin\_us-fr.pngaltPour ajouter une adresse IP ou une plage :

1. Depuis la barre supérieure, ouvrez le menu du compte (liste déroulante de l’adresse e-mail) > **Centre de sécurité**.
2. Dans la section Liste d'autorisations API, cliquez sur **Gérer la liste d'autorisations API**.
3. Cliquez sur **+ Ajouter** pour ajouter une adresse IP ou une plage à la liste.
4. Entrez une adresse IP ou une plage.
5. Cliquez sur **Appliquer.**
6. Assurez-vous d'enregistrer vos modifications en cliquant sur le bouton **Enregistrer la liste**.

   **Remarque :** Le statut de la liste (actif ou inactif) ne changera pas lorsque vous enregistrez la liste. Assurez-vous de vérifier l'état du bouton **Actif** et activez/désactivez-le si nécessaire.

altAppsFlyerAdmin\_us-en.pngaltPour supprimer une adresse IP ou une plage :

1. Depuis la barre supérieure, ouvrez le menu du compte (liste déroulante de l’adresse e-mail) > **Centre de sécurité**.
2. Dans la section Liste d'autorisations API, cliquez sur **Gérer la liste d'autorisations API**.
3. Cliquez sur l'icône de la corbeille à côté de l'adresse IP que vous souhaitez supprimer.
4. Dans la fenêtre contextuelle de confirmation, cliquez sur **Supprimer**.
5. Assurez-vous d'enregistrer vos modifications en cliquant sur le bouton **Enregistrer la liste**.

</Accordion>

<div id="api-allowlist-specifications" />

<Accordion title="Spécifications de la liste d'autorisation">

* Pour protéger votre compte contre les appels d'API non autorisés, la liste d'autorisation doit être définie sur **Actif** et inclure au moins une adresse IP ou une plage.
* La liste d'autorisation s'applique à toutes les <Anchor target="_blank" href="/marketers/fr/docs/managing-appsflyer-tokens#applications-of-the-api-v2-token">API AppsFlyer qui utilisent le jeton V2.0</Anchor><Anchor target="_blank" href="/marketers/fr/docs/managing-appsflyer-tokens#applications-of-the-api-v2-token">. Les appels d'API qui utilisent le jeton API V1.0 seront autorisés à partir de toutes les adresses API.</Anchor>
* Jusqu'à 20 adresses IP ou plages peuvent être ajoutées à la liste d'autorisation.

</Accordion>

<div data-zendesk-anchors="overview=altliste-dautorisations-apialt h_01HZCCCTT52ZQB9VAF6Q7RRKES=altliste-dautorisations-apialt overview::6f3684c7=aper%C3%A7u h_01HZCD0681XNKR2HSNCN4GWGA0=aper%C3%A7u h_01HJR00RGQX0CQEHDS9BHBGJD4=remarque set-up-your-api-allowlist=configurer-votre-liste-dautorisations-api h_01HZCCW4XYJ72Z6KKJPCXQB947=configurer-votre-liste-dautorisations-api h_01HJR00RGRQ54R71HY0ZBRM1PM=set-up-the-api-allowlist h_01HJR00RGRD7PK2HR5VS1JENWQ=edit-the-api-allowlist h_01HJR00RGRESGGEW3D6NHHF7VY=api-allowlist-specifications" />
