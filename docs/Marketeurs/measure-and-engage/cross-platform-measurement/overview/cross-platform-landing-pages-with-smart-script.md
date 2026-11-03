---
title: Pages de destination multiplateformes avec Smart Script
metadata:
  keywords:
    - CTV
    - Marketers
    - gaming
    - cross-platform
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Cross-Platform Measurement
  created_at: '2023-09-10T07:17:21Z'
  edited_at: '2024-11-01T08:52:11Z'
  id: 18440789126289
  locale: fr
  section: Overview
  section_id: 15323084579345
  url: https://support.appsflyer.com/hc/fr/articles/18440789126289
---
> **En bref :** Utilisez une page de destination multiplateforme exécutant le script intelligent AppsFlyer pour réaliser une attribution Web vers application. Cela permet de convertir les utilisateurs voyant une publicité web de n'importe quelle source média en utilisateurs d'applications sur CTV, PC, console ou plateformes mobiles.

## Aperçu

Avec une page de destination multiplateforme utilisant le script intelligent AppsFlyer, vous pouvez effectuer une attribution Web vers application. Cela signifie que vous pouvez attribuer des installations sur n'importe quelle plateforme aux publicités affichées sur le web.

Le script intelligent d'une page de destination multiplateforme utilise le lien entrant (provenant de l'annonce web) pour faire deux choses qui assurent que la source média d'origine et l'annonce web sont attribuées à l'installation :

* Créer un lien OneLink multiplateforme qui envoie une impression à AppsFlyer.
* Créer des liens d'attribution directe pour chaque application/plateforme.

## Configuration

#### PORTÉE DES TRAVAUX

| **Qui est impliqué ?**<ul><li>**Annonceur** :<ul><li>Détermine ce que doivent contenir l'[impression multiplateforme](#create-crossplatform-impression-link) et les [liens d'attribution directe](#create-direct-attribution-links) en fonction des <Anchor target="_blank" href="/marketers/fr/docs/set-up-smart-script-to-convert-web-visitors#arguments">arguments</Anchor> dans le script intelligent. Cela détermine les données d'attribution ajoutées à l'URL sortante, soit en manipulant l'URL entrante, soit en imposant certaines valeurs.</li><li>S'assure que toutes les campagnes menant au site web ont des URL entrantes avec des paramètres que le script peut traiter.</li><li><Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-onelink-smart-script/examples/test_page.html">Teste le script intelligent</Anchor>.</li></ul></li><li>**Développeur Web** :<ul><li>Ajoute les arguments au script et implémente le script intelligent sur la page de destination.</li><li>Teste le script intelligent.</li></ul></li></ul> |
| --- |
| **Prérequis**<ul><li>Un compte AppsFlyer avec au moins une application.</li><li>Pour l'URL d'impression : Un modèle <Anchor target="_blank" href="/marketers/fr/docs/create-a-onelink-template#procédures">OneLink</Anchor>  avec attribution multiplateforme activée.</li></ul> |

<div id="create-crossplatform-impression-link" />

<Accordion title="Créer un lien d'impression multiplateforme">

**Pour créer un lien OneLink multiplateforme qui envoie une impression à AppsFlyer** :

1. Mettez en correspondance les paramètres du lien entrant avec les paramètres que doit contenir le lien d'impression (pour source média, campagne, nom de l'annonce, etc.).
   * En savoir plus sur les <Anchor target="_blank" href="/marketers/fr/docs/set-up-smart-script-to-convert-web-visitors#arguments">arguments</Anchor> dans le script qui traitent l'URL entrante.
   * La valeur de l'argument <Anchor target="_blank" href="/marketers/fr/docs/set-up-smart-script-to-convert-web-visitors#arguments">OneLinkURL</Anchor> est le domaine + ID du modèle OneLink avec attribution multiplateforme activée.
2. Demandez à votre développeur d'initialiser les arguments du Smart Script et d'appeler la méthode Smart Script `generateOneLinkURL`. <Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/">Consultez la démo et les instructions destinées aux développeurs</Anchor>.  
   **Remarque :** Le paramètre `af_xplatform=true` est obligatoire pour activer l'attribution multiplateforme.

</Accordion>

<div id="create-direct-attribution-links" />

<Accordion title="Créer des liens d'attribution directe">

1. Associez les paramètres des liens entrants aux paramètres que les liens d'attribution directe sortants doivent contenir (source média, campagne, nom de l'annonce, etc.). En savoir plus sur les <Anchor target="_blank" href="/marketers/fr/docs/set-up-smart-script-to-convert-web-visitors#arguments">arguments</Anchor> dans le script qui traite l'URL entrante.
2. Demandez à votre développeur d'initialiser les arguments du Smart Script et d'utiliser la méthode Smart Script pour créer un lien pour chaque plateforme\/application. Consultez la <Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-sample-app-smartscript-demo-page/">démo</Anchor> et les <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/create-direct-click-url">instructions</Anchor> destinées aux développeurs.  
   Remarque : Le développeur doit ajouter les paramètres suivants :  

| Paramètre\/Argument | Remarques | Enregistrez vos réponses (à utiliser par vous ou votre développeur) |
| --- | --- | --- |
| plateforme | Une chaîne décrit la plateforme et doit être issue de cette liste :<ul><li>smartcast</li><li>tizen</li><li>roku</li><li>webos</li><li>vidaa</li><li>playstation</li><li>android</li><li>ios</li><li>steam</li><li>quest</li><li>battlenet</li><li>nativepc</li></ul> |  |
| app\_id | <ul><li>ID d'app</li><li>Exemple : 123456</li></ul> |  |
| URL de redirection | <ul><li>L'URL vers laquelle l'utilisateur de la plateforme\/application doit être redirigé.</li><li>Exemple :</li></ul> |  |


</Accordion>

<div data-zendesk-anchors="overview=aper%C3%A7u 01H8V0RV7X8JEVEJ36TJB1X43D=aper%C3%A7u setup=configuration 01H8V0RV7X0K157JTDQMJSQYKF=configuration scope-of-work=port%C3%A9e-des-travaux h_01H95PGMNWPBRHSZBPMKNJ2PS6=port%C3%A9e-des-travaux 01H8EQ4KS75Q62Z7WVNSTDXBZX=create-crossplatform-impression-link 01H8EQ4KS7C6HADNKQZYNTTFMF=create-direct-attribution-links" />
