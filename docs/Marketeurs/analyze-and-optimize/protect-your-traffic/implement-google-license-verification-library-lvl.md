---
title: Configuration de la bibliothèque de vérification de licence Google (LVL)
metadata:
  keywords:
    - Premium
    - Premium Feature
    - Marketers
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2023-07-27T14:45:46Z'
  edited_at: '2024-07-08T13:52:30Z'
  id: 17329535522961
  locale: fr
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/fr/articles/17329535522961
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En bref :** Protégez vos applications contre toute utilisation non autorisée en ajoutant la bibliothèque de validation de licence Google (LVL) pour gérer toutes les communications liées aux licences avec Google Play.

<div id="overview" />

## Introduction

La bibliothèque de vérification de licence (LVL) est une bibliothèque que vous pouvez ajouter à vos applications (téléchargeable à partir du SDK Android) et qui gère toutes les communications liées aux licences avec le service de gestion des licences Google Play.

Cela ajoute une autre couche de protection, en plus des algorithmes de Protect360, en permettant de vérifier que les installations sont issues de vrais utilisateurs de Google Play. Cela permet de réduire les écarts entre le nombre d’installations visibles sur Google Play et sur le tableau de bord AppsFlyer.

Le service de gestion des licences Google Play détermine si l’utilisateur est autorisé à utiliser une application ou non. Google Play considère que les utilisateurs sont titulaires d’une licence s’ils sont des acheteurs enregistrés de l’application. La licence est unique par application et peut être utilisée pour une protection renforcée. <Anchor target="_blank" href="https://developer.android.com/google/play/licensing">En savoir plus</Anchor>

Le SDK d’AppsFlyer collecte les données côté client et Protect360 effectue la vérification de la licence côté serveur, bloquant les installations frauduleuses qui échouent à la vérification pour les installations organiques et non organiques. La « raison du blocage » dans le tableau de bord et les rapports de Protect360 sera « Bots ».

<div id="note" />

<div id="set-up-lvl" />

## Configurer LVL

<div id="add-lvl" />

<Accordion title="Ajouter LVL">

Actuellement, il s’agit d’un processus manuel nécessitant la transmission des informations ci-dessous à votre CSM AppsFlyer afin qu’il puisse les ajouter manuellement.

**Pour ajouter le LVL :**

1. Assurez-vous que vous disposez de la version 5.4.3 ou ultérieure du SDK pour ajouter le dernier SDK à l’implémentation build.gradle. **Note :** la version 6.12.3 ou supérieure est recommandée.   

   ```http
   com.appsflyer:af-android-sdk:6.12.3
   ```
2. Ajouter la bibliothèque LVL à l’implémentation build.gradle  

   ```http
   com.appsflyer:lvl:6.12.3
   ```
3. Obtenez les licences et la facturation dans l’application :  
   Dans la console développeur Google Play (sélectionnez l’application > Outils de développement > Services et API).  

   ```http
   Base64-encoded RSA public key
   ```
4. Transmettez les informations ci-dessus à votre CSM AppsFlyer.

</Accordion>

<div id="test-and-troubleshoot" />

<Accordion title="Test et dépannage">

Lors du débogage de l’application, vous devez pouvoir voir les informations LVL sur la charge utile envoyée à AppsFlyer, comme dans l’exemple ci-dessous :

```json
"lvl":{
      "ttr":,<ttr>,
      "signature":"<signature>",
      "signedData":"<signedData>"
   }
```

Contactez votre équipe de support/SDK au cas où il n’y aurait pas d’informations LVL dans le message d’installation.

Veuillez fournir à votre CSM les informations suivantes :

* clé publique
* app-id
* version minimale de l’application dans laquelle le LVL est intégré

</Accordion>

<div id="setup-process" />

<Accordion title="Processus de configuration">

Une fois que nous aurons reçu votre demande, l’équipe Protect360 configurera la vérification LVL en mode STAGING. À ce stade, le système ne communiquera que les résultats de la vérification LVL en interne pour AppsFlyer. Quelques jours plus tard, nous vérifierons nos données.

**Si tout semble correct :**

* Nous allons régler la vérification LVL en mode PRODUCTION et elle commencera à bloquer le trafic.
* L’équipe Protect360 en informera le CSM.

**En cas de problème** (par exemple si nous ne voyons pas d’informations LVL sur les événements d’installation) :

* Nous laisserons la vérification LVL en mode STAGING.
* Votre CSM vous avertira et vous aidera à résoudre les problèmes d’implémentation dans l’application.

</Accordion>

## FAQ

<div id="what-if-an-app-is-installed-from-a-store-other-than-google-play" />

<Accordion title="Que se passe-t-il si une application est installée à partir d’un magasin autre que Google Play ?">

La validation LVL ne vérifie pas et ne bloque pas les installations provenant de magasins autres que Google Play.

</Accordion>

<div id="how-much-time-does-it-take-to-get-lvl-set-up" />

<Accordion title="Combien de temps faut-il pour mettre en place LVL ?">

Une fois que nous avons obtenu les informations, il faut quelques jours ouvrables pour configurer LVL et vérifier les données. Voir les détails sur le [Processus de configuration](/docs/implement-google-license-verification-library-lvl#setup-process).

</Accordion>

<div id="does-lvl-affect-app-functionality" />

<Accordion title="LVL affecte-t-il les fonctionnalités de l’application ?">

Non, les fonctionnalités de l’application ne sont pas affectées.

</Accordion>

<div id="what-is-the-difference-between-lvl-and-gpreferrer" />

<Accordion title="Quelle est la différence entre LVL et GP-referrer ?">

La vérification de la licence à l’aide de LVL diffère des algorithmes de vérification GP-referrer car LVL gère la vérification de la licence pour l’application elle-même (licence par application), tandis que GP-referrer est utilisé pour obtenir la source de redirection de l’installation vers le Google Play Store avec l’URL du référent du package installé (les horodatages du moment où un clic sur le référent s’est produit, lorsque l’installation a commencé, la version de l’application, etc.). En bref, alors que LVL est utilisé pour vérifier que l’utilisateur est autorisé à utiliser l’application, le GP-referrer est utilisé pour vérifier que les détails de l’installation n’ont pas été falsifiés.

</Accordion>

<div data-zendesk-anchors="overview=introduction 01H7YJ35YKDHJ2MDZSSYKMDCJ4=introduction set-up-lvl=configurer-lvl 01H7YJ35YKDW0CB9TWRBKFBCDJ=configurer-lvl 01H7YJ35YK585NA5F4HZN8C74K=add-lvl 01H7YJ35YKX1CVYMRZ1W8NRH7Y=test-and-troubleshoot 01H7YJ35YKMCN2E2BDWA5DD5M3=setup-process 01H7YJ35YMR8PBTTSHD77WZ4AE=faq 01H7YJ35YMRZ8KRSVND1JT6JGH=what-if-an-app-is-installed-from-a-store-other-than-google-play 01H7YJ35YM11J0EG0B8PBMSPAC=how-much-time-does-it-take-to-get-lvl-set-up 01H7YJ35YMH0NM73Y1R90JDMEA=does-lvl-affect-app-functionality 01H7YJ35YM6RHCA6QP3MK0Y9J0=what-is-the-difference-between-lvl-and-gpreferrer" />
