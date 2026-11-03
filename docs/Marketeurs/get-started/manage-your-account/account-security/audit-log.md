---
title: Journal d'audit
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
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
    - Ad Networks
  created_at: '2020-05-05T14:18:09Z'
  edited_at: '2024-10-08T10:43:37Z'
  id: 360007971697
  locale: fr
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/fr/articles/360007971697
---
> **En bref :** Identifiez et protégez-vous contre les accès non autorisés à votre compte AppsFlyer grâce au journal d'audit. Consultez et téléchargez un résumé des activités liées à la sécurité de votre compte.

## Aperçu

Le **journal d'audit** offre un point central pour examiner diverses activités de votre compte, telles que les connexions, l'accès aux données, les appels API, les modifications des configurations et autorisations des partenaires intégrés, les règles de validation, les audiences, et d'autres événements importants. Il joue un rôle essentiel pour garantir la transparence, la sécurité et le respect des normes de conformité. Pour protéger la sécurité de votre compte AppsFlyer, il est recommandé de vérifier régulièrement **qui** accède à votre compte et **comment** il est utilisé. Les données du journal d’audit sont disponibles pour les 90 derniers jours.

**Pour accéder au journal d'audit :**

1. Depuis la barre supérieure, ouvrez le menu du compte (liste déroulante de l'adresse e-mail) : **Centre de sécurité.**
2. Dans la section **Journal d'audit**, cliquez sur **Afficher le journal d'audit**.

## Utilisation du journal d'audit

Une description des données fournies par le journal d’audit et un résumé de ses fonctionnalités figurent dans le tableau ci-dessous.

[altjournal\_d'audit.pngalt](https://support.appsflyer.com/hc/article_attachments/6867050961809)

|  | Élément | Description |
| --- | --- | --- |
| ![A.png](https://files.readme.io/d515ad5eb908256574b52dee5d598a785020c3392b410b9fa4574eeb8c4ae594-6867187386897.png) | Zone de recherche et filtres | Filtrez les données affichées pour vous concentrer uniquement sur ce que vous souhaitez voir :<ul><li>Utilisez la barre de recherche pour filtrer les données par un terme spécifique (tel qu'un ID d'application pertinent, une adresse e-mail, etc.)</li><li>Utilisez le sélecteur de date pour choisir la période pour laquelle les données sont affichées</li><li>Utilisez le filtre de service pour trier les données en fonction des services spécifiques auxquels vous avez accès :<ul><li>Accès au système</li><li>Autorisations des partenaires intégrés</li><li>Gestion des utilisateurs</li><li>Règles de validation</li><li>Appels API</li></ul></li></ul>Notez que le service **Appels API** est désélectionné par défaut afin d'optimiser la lisibilité du rapport. Assurez-vous de sélectionner ce service si vous souhaitez l'inclure dans le rapport. |
| ![B.png](https://files.readme.io/ee0be2e394ad7bf76766a84c3bcad882a55dd0522e0aa41ed8ef11432c0df592-6867187537809.png) | Données du journal d'audit | Chaque entrée dans le journal d'audit comprend les informations suivantes :<ul><li>**Date et heure :** la date et l'heure auxquelles le service a été consulté (en UTC)</li><li>**Application/compte consulté :**<ul><li>Pour les connexions utilisateurs (accès au système) et la gestion des utilisateurs, cette colonne affiche **Compte** (indiquant un accès au niveau du compte).</li><li>Pour les appels API, cette colonne affiche soit l'accès au **Compte**, soit l'**ID Application** de l'application pour laquelle les données ont été consultées.</li></ul></li><li>**Identifiants**<ul><li>Pour l'accès au système ou la gestion des utilisateurs, cette colonne affiche l'adresse e-mail de l'utilisateur accédant au service.</li><li>Pour les appels API, cette colonne affiche le jeton API AppsFlyer utilisé (V2).</li></ul></li><li>**Service :** le service auquel on a accédé (accès au système, gestion des utilisateurs, ou appels API).</li><li>**Action :** l'action enregistrée (exemples : connexion, déconnexion, données consultées via une API).</li><li>**Détails :** Détails supplémentaires sur l'action enregistrée.</li></ul> |
| ![C.png](https://files.readme.io/078ad9663eed2141f7047e0869fe02f4d1a0f8545176bce4d1c6027bfaa439b3-6867187658385.png) | ![bouton_de_téléchargement_du_journal_d'audit.png](https://files.readme.io/50e6cfef2aceb4b199f79008090da39d021f94be8d88d329bb8c8a0723edfa75-6867407922577.png) | Cliquez sur le bouton de téléchargement pour obtenir le journal d'audit sous forme de fichier CSV.<ul><li>Toutes les sélections appliquées au rapport tel qu'affiché à l'écran (utilisant la barre de recherche et les filtres) sont également appliquées au fichier téléchargé.</li></ul> |

## Dépannage

<div id="why-does-an-advertiser-audit-log-show-partner-api-call-requests" />

<Accordion title="Pourquoi le journal d'audit d'un annonceur affiche-t-il les requêtes d'appel API des partenaires ?">

Lorsqu'un partenaire fait une demande API sur une application appartenant à un annonceur, le partenaire et l'annonceur voient tous deux la requête dans leur journal d'audit.

Lorsqu'un annonceur utilise son propre jeton pour effectuer une demande API, elle n'apparaîtra que dans le journal d'audit de l'annonceur.

</Accordion>

<div data-zendesk-anchors="overview=aper%C3%A7u h_01H9Q3XYYBKYSRP3T0R2MP712C=aper%C3%A7u using-the-audit-log=utilisation-du-journal-daudit h_01H9Q3XYYBBCB6PXBZBF97QE11=utilisation-du-journal-daudit troubleshooting=d%C3%A9pannage h_01H9Q3XYYB24R3EATM7R32V0G7=d%C3%A9pannage h_01H9Q3XYYCHWJ1NQS389MR311X=why-does-an-advertiser-audit-log-show-partner-api-call-requests" />
