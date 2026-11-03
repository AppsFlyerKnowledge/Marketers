---
title: Implémenter le code web des bannières intelligentes pour les marketeurs
metadata:
  keywords:
    - OneLink
    - Advertisers
    - Developer
    - Developers
    - Smart Banner
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2022-01-10T11:25:54Z'
  edited_at: '2024-08-19T13:08:55Z'
  id: 4416119954705
  locale: fr
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/fr/articles/4416119954705
---
> **En bref :** Ajoutez le code des bannières intelligentes à votre site web pour convertir les internautes en utilisateurs d'app mobile.

> 📘 **Remarque**
>
> Le SDK web V1 pour les bannières intelligentes AppsFlyer a été supprimé le 8 novembre 2023. Pour afficher les bannières intelligentes sur votre site web, vous devez passer à la version 2. <Anchor target="_blank" href="/marketers/fr/docs/bulletin-deprecation-of-appsflyer-smart-banner-web-sdk-v1">En savoir plus</Anchor>

## Mettre en place le code d’un site web

Cet article est destiné aux marketeurs qui souhaitent intégrer à leur site le code des bannières intelligentes via l'une des méthodes suivantes :

* Google Tag Manager (GTM)
* Adobe Launch Tag Manager
* Shopify
* Wix
* Squarespace
* WordPress

Pour ajouter le code à votre site en passant par une autre plateforme, ou pour apporter des modifications au code en cours (ce qui inclut l'ajout d’un paramètre, le deep linking, le masquage d’une bannière ou l'intégration de la PBA via les bannières intelligentes), veuillez consulter l’article <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2">Implémenter le code web des bannières intelligentes pour les développeurs.</Anchor>

**Pour implémenter le code des bannières intelligentes sur votre site** :

1. Suivez les <Anchor target="_blank" href="/marketers/fr/docs/smart-banners-mobile-web-to-app-for-marketers#1-website-workplace-setup">instructions du site web</Anchor> pour obtenir le code des bannières intelligentes.
2. Utilisez les instructions propres à chaque plateforme pour implémenter le code dans votre site web :

<div id="google-tag-manager" />

<Accordion title="Google Tag Manager">

**Pour implémenter le code via Google Tag Manager :**

1. Dans GTM, créez une nouvelle balise.
2. **Nommez la balise, cliquez sur** **Configuration des balises,** et sélectionnez HTML personnalisé.
3. Dans la boîte HTML, collez l'extrait de code des bannières intelligentes. Remplacez YOUR-BANNER-KEY par votre propre clé de bannière.
4. Cliquez sur **Déclenchement** et créez un déclencheur en cliquant sur l'icône situé en haut à droite de l'écran.
5. Nommez le déclencheur, cliquez sur **Configuration du déclencheur** et choisissez **Vue sur la page**.
6. Si vous souhaitez que la bannière s'affiche sur toutes les pages, sélectionnez **Vue sur toutes les pages**. Si vous souhaitez que la bannière s'affiche sur certaines pages seulement, sélectionnez **Vues sur certaines pages** et stipulez la condition qui viendra déclencher la balise. Pour en savoir plus sur les déclencheurs, lisez la **documentation de GTM**.
7. Cliquez sur **Enregistrer**, en haut à droite.
8. Revenez à l'écran de configuration des balises. Vérifiez que tout est correctement paramétré et cliquez sur **Enregistrer**, en haut à droite.
9. Publiez votre conteneur GTM.

</Accordion>

<div id="adobe-launch-tag-manager" />

<Accordion title="Adobe Launch Tag Manager">

**Pour implémenter le code via Adobe Launch Tag Manager :**

<div id="step-1-create-a-property-in-adobe-experience-cloud" />

<Accordion title="Étape 1 : créer une propriété dans Adobe Experience Cloud">

**Pour créer une propriété (balise) qui héberge le code des bannières intelligentes :**

1. Allez dans **Adobe Experience Cloud** > **Lancement**.
2. Dans **Adobe Experience Cloud Launch**, cliquez sur **Accéder au lancement.**
3. Cliquez sur **Nouvelle propriété**.
4. Nommez votre propriété.
5. Dans **Plateforme**, sélectionnez **web**.
6. Saisissez le domaine de votre site web.
7. Cliquez sur **Enregistrer**.

</Accordion>

<div id="step-2-add-smart-banners-code-to-the-adobe-launch-property" />

<Accordion title="Étape 2 : ajouter le code des bannières intelligentes à la propriété Adobe Launch">

**Pour ajouter le code des bannières intelligentes à la balise** :

1. Sur la page **Mes propriétés web**, ouvrez l'onglet **Règles**.
2. Nommez la règle. Recommandé : bannières intelligentes AppsFlyer
3. Dans **Evénements**, allez dans la section **If (si)**, puis cliquez sur **+Ajouter**.
   * Dans **Type d'événement**, sélectionnez **Core - DOM Ready**.
   * Cliquez sur **Garder les modifications**.
4. Dans **Actions**, allez dans la section **Then (Alors)**, puis cliquez sur **+Ajouter**.
   * Dans **Type d'action**, cliquez sur **Code personnalisé**.
   * Sélectionnez **JavaScript** > **Ouvrir l'éditeur** et collez l'extrait de code du SDK pour les bannières intelligentes,**sans les balises &lt;script>** .
   * Cliquez sur **Conserver les modifications** pour fermer l'éditeur de code.
5. Cliquez sur **Enregistrer**.

</Accordion>

<div id="step-3-add-the-adobe-launch-tag-to-your-website" />

<Accordion title="Étape 3 : ajouter la balise Adobe Launch à votre site web.">

**Pour ajouter la balise Adobe Launch à votre site web (qui chargera le code des bannières intelligentes) :**

1. Sur la page **Mes propriétés web**, sélectionnez l'onglet **Environnements**.
2. Trouvez la ligne contenant l'environnement que vous souhaitez publier (développement ou production).
   * Dans le header **Install**, cliquez sur l'icône en forme de boîte au bout de la ligne concernée. Il s'agit souvent d'un environnement de production.
   * Consultez la section qui traite de la publication de l'environnement **Adobe Launch**.
3. Dans la boîte de dialogue des **Instructions d'installation web** :
   * Copiez l'extrait de code de script.
   * Fermez la boîte de dialogue.
4. Collez l'extrait de code dans la balise &lt;head> de votre site web.

</Accordion>

<div id="step-4-publish-the-adobe-launch-environment" />

<Accordion title="Étape 4 : publier l’environnement Adobe Launch">

**Pour publier l'environnement qui activera la balise Adobe Launch :**

1. Sur la page **Mes propriétés web**, ouvrez l'onglet **Publication**.
2. Dans la section **Développement** , cliquez sur **Ajouter une nouvelle bibliothèque.**
   1. Nommez la bibliothèque puis choisissez un environnement.
   2. Dans **Changements de ressource**, cliquez sur **Ajouter une ressource.**
   3. Cliquez sur **Règles** > **Charger les bannières intelligentes** > **Les plus récentes** > **Sélectionner et créer une nouvelle révision**.
   4. Cliquez sur **Enregistrer**.
3. Dans la section **Développement** :
   1. À côté de la bibliothèque nouvellement créée, cliquez sur le menu Action (3 points) et sélectionnez **Créer pour le développement.**
   2. Cliquez à nouveau sur le menu Action et sélectionnez **Envoyer pour validation**.
4. Dans la section **Envoyé** :
   1. Cliquez sur le menu Action et sélectionnez **Créer pour le test**.
   2. Cliquez à nouveau sur le menu Action et sélectionnez **Approuver la publication.**
5. Dans la section **Approuvé**, cliquez sur le menu Action et sélectionnez **Créer le build et publier pour la production.**  
   La procédure est maintenant terminée.

</Accordion>

Désormais, lorsque votre site web se chargera sur un mobile, la bannière active s'affichera. Pour afficher la bannière sur certaines pages uniquement, ou en réponse à certaines actions de l'utilisateur, consultez les <Anchor target="_blank" href="https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/rules.html">Règles d’Adobe Launch</Anchor>.

</Accordion>

<div id="shopify" />

<Accordion title="Shopify">

**Pour implémenter le code dans votre site Shopify** :

1. Dans votre tableau de bord Shopify, allez dans **Canaux des ventes** > **Boutique en ligne** > **Thèmes**.  
   Votre thème en cours s'affiche.
2. Cliquez sur **Actions** > **Modifier le code**.  
   La page Modifier le code s'ouvre pour votre thème.
3. Dans le dossier Layout (mise en page), cliquez sur le fichier qui débute par **`{/}` theme.**  
   Le code de la page web s'affiche.
4. Dans le code, juste après **&lt;head>,** collez le code de vos bannières intelligentes.

</Accordion>

<div id="wix" />

<Accordion title="Wix">

**Pour implémenter le code dans votre site Wix** :

1. Dans votre tableau de bord Wix, cliquez sur **Paramètres.**
2. Dans la section Avancé de la page Paramètres, cliquez sur **Code personnalisé**.
3. Cliquez sur **+ Ajouter un code personnalisé**.
4. Dans la case **Coller l'extrait de code ici**, collez le code des bannières intelligentes.
5. Dans la case Nom, saisissez un nom pour votre code. **Recommandé** : Bannières intelligentes AppsFlyer.
6. Dans **Ajouter du code aux pages**, sélectionnez l'endroit où s’afficheront vos bannières. Soit :
   * Toutes les pages
   * Certaines pages
7. Cliquez sur **Appliquer**.  
   La page Code personnalisé doit alors afficher votre code. Veillez à ce qu'il soit placé dans la section **Head**.

</Accordion>

<div id="squarespace" />

<Accordion title="Squarespace">

**Pour implémenter le code dans votre site Squarespace** :

1. Dans votre tableau de bord Squarespace, cliquez sur **Site web**.
2. Cliquez sur Paramètres.
3. Cliquez sur **Avancé**.
4. Cliquez sur **Insérer du code**.
5. Dans la section **Header**, collez le code des bannières intelligentes.
6. Cliquez sur Enregistrer.

</Accordion>

<div id="wordpress" />

<Accordion title="WordPress">

**Pour implémenter le code dans votre site web WordPress** :

1. Dans votre tableau de bord WordPress, cliquez sur **Apparence** > **Editeur de thème.**  
   La page Modifier les thèmes s'ouvre, et le code CSS de votre site web s'affiche.
2. Dans **Fichiers du thème**, cliquez sur **Header du thème (header.php).**
3. Dans le code qui s'affiche, juste après **&lt;head>,** collez le code des bannières intelligentes.
4. Cliquez sur **Mettre à jour le lien**.

</Accordion>

> 📄 **Articles connexes**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/pba-web-sdk-integration-guide#installation-and-integration">Intégrer la PBA avec les Bannières intelligentes</Anchor>

<div data-zendesk-anchors="h_01HBT97B1ZGKKTD0TN2J2W56ZQ=remarque website-code-implementation=mettre-en-place-le-code-dun-site-web h_01HBT97B1Z0F4B8E9GQWJEE6BH=mettre-en-place-le-code-dun-site-web h_01HBT97B1ZKW36W9F0XQKM323P=google-tag-manager h_01HBT97B1ZX6VM1YER2HXTYQJ2=adobe-launch-tag-manager h_01HBT97B1ZPP0AKB5E31W36VC2=step-1-create-a-property-in-adobe-experience-cloud h_01HBT97B1ZK4T23MF4D6VGP4B8=step-2-add-smart-banners-code-to-the-adobe-launch-property h_01HBT97B1Z0W9VJ5FCW4605RDC=step-3-add-the-adobe-launch-tag-to-your-website h_01HBT97B1Z1W33DTT6NR4PQHQ0=step-4-publish-the-adobe-launch-environment h_01HBT97B1Z0NTYJKB2YFMX62P9=shopify h_01HBT97B1ZYVJ6PW7F811V5TAX=wix h_01HBT97B1ZS0FDM60M1GA04PRT=squarespace h_01HBT97B1ZKYB7XPGFG00PB2BT=wordpress h_01HE7SG3MJ4WTPMTXF0DA0M07D=articles-connexes" />
