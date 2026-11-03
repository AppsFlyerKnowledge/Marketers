---
title: Formulaire de la section sécurité de Google
metadata:
  keywords:
    - Google Play
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2022-01-19T15:00:21Z'
  edited_at: '2023-10-27T11:12:52Z'
  id: 4417197430289
  locale: fr
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/fr/articles/4417197430289
---
> **En bref** : à partir d'avril 2022, les développeurs d'apps sont tenus de remplir le formulaire de la section « Sécurité des données » de Google Play et de publier un lien vers une politique de confidentialité, même s'ils ne collectent aucun des types de données spécifiés par Google. Cette page est destinée à vous fournir des informations pour vous aider à répondre au questionnaire de la section de sécurité de Google, uniquement pour les éléments qu'AppsFlyer traite au nom des clients.

Les clients doivent travailler en étroite collaboration avec des conseillers juridiques et autres professionnels pour déterminer précisément comment les politiques Google s'appliquent à eux. Ils sont tenus d'adapter leurs mesures en fonction de leurs configurations et utilisations spécifiques.

#### **Clause de non-responsabilité**

Les informations contenues dans cet article sont destinées à vous aider à répondre au questionnaire de la section de sécurité de Google, **uniquement** pour les éléments qu'AppsFlyer traite au nom des clients.

Elles sont fournies à titre d'information uniquement. Les clients doivent travailler en étroite collaboration avec des conseillers juridiques et autres professionnels pour déterminer précisément comment les politiques Google s'appliquent à eux. Ils sont tenus d'adapter leurs mesures en fonction de leurs configurations et utilisations spécifiques.

## Introduction

À partir d'avril 2022, les développeurs d'apps seront tenus de fournir des informations relatives à leurs pratiques en matière de protection de la vie privée par le biais de la section de Google dédiée. Ils devront notamment fournir des détails sur les données qu'ils collectent, la manière dont elles sont traitées et partagées, y compris par l'utilisation de tout kit de développement logiciel tiers.

Les informations fournies par chaque app seront affichées dans la liste du Google Store, ce qui permettra aux utilisateurs finaux de mieux comprendre les règles de confidentialité d'une app.

## Audience

Tous les développeurs d'apps devront remplir le questionnaire de la section Sécurité et publier un lien vers une politique de confidentialité, même s'ils ne collectent aucun des types de données spécifiés par Google.

## Formulaire de sécurité Google (questionnaire)

Google a publié un formulaire (questionnaire) que les développeurs d'apps devront remplir. Le questionnaire comprend les sections suivantes :

* Collecte et sécurité des données
* Types de données
* Utilisation et traitement des données

Les développeurs d'apps devront d'abord évaluer leurs pratiques en matière de collecte et de traitement des données avant de répondre au questionnaire.

Concernant l'utilisation d'AppsFlyer, nous rappelons aux développeurs d'apps qu'ils contrôlent pleinement la façon dont ils implémentent et configurent AppsFlyer, y compris les données collectées et la façon dont elles sont utilisées. Par conséquent, chaque développeur d'app peut avoir des réponses différentes au questionnaire en fonction de ses pratiques de données et de l'utilisation d'AppsFlyer.

Les développeurs d'apps doivent répondre au questionnaire en fonction de leurs cas d'utilisation, configurations et intégrations de partenaires spécifiques.

### Collecte et sécurité des données

Dans cette section, nous vous poserons quelques questions générales auxquelles vous pouvez répondre par oui ou par non :

1. Votre app collecte-t-elle ou partage-t-elle l'un des types de données requis ?
2. Toutes les données utilisateur collectées par votre app sont-elles cryptées durant le transit ?
3. Permettez-vous aux utilisateurs de demander la suppression de leurs données ?

En ce qui concerne votre utilisation d'AppsFlyer, AppsFlyer chiffre toutes les données transmises via le SDK. AppsFlyer offre également à ses clients la possibilité de supprimer des données spécifiques de l'utilisateur final grâce à son infrastructure OpenGDPR. Pour connaître les types de données collectés, reportez-vous au tableau de la section [Types de données](/docs/fill-out-google-safety-section-form#types-de-données).

### Types de données

Dans cette section, il vous sera demandé de sélectionner les types de données collectés et de répondre aux questions suivantes :

1. Si les données sont partagées
2. Les données sont-elles traitées de manière éphémère ?
3. Les données sont-elles obligatoires ou les utilisateurs finaux peuvent-ils choisir de ne pas les fournir ?
4. L'objectif

Le tableau qui suit suppose que les configurations par défaut du logiciel AppsFlyer sont appliquées. Les développeurs sont tenus de s'assurer que leurs configurations et utilisations spécifiques sont conformes.

« Collecté » désigne les données transmises hors de l'appareil par quelque moyen que ce soit (par exemple, webview ou le SDK).  Une exception est faite si un cryptage de bout en bout est utilisé, rendant les données illisibles pour qui que ce soit.

| Type de données | Collecte des données par défaut d'AppsFlyer | Remarques |
| --- | --- | --- |
| Infos de localisation<ul><li>Localisation approximative</li><li>Localisation précise</li></ul> | Voir les notes | Localisation précise : non<br /><br />Localisation approximative : oui, l'adresse IP est reçue et cartographiée au niveau région/ville. |
| Informations personnelles<ul><li>Nom</li><li>Adresse e-mail</li><li>Identifiants personnels (identifiant de compte, numéro ou nom)</li><li>Adresse</li><li>Numéro de téléphone</li><li>Race et origine ethnique</li><li>Opinions politiques ou religieuses</li><li>Orientation sexuelle ou identité de genre</li><li>Autres informations personnelles</li></ul> | Voir les notes | Les informations personnelles ne doivent pas être collectées, et AppsFlyer limite la collecte de ces données personnelles telles que le nom et l'adresse. Toutefois, si les développeurs d'apps ont configuré la transmission d'e-mails ou de numéros de téléphone hachés, ou s'ils ont configuré un ID de compte utilisateur client (CUID), ils devront prendre des mesures en conséquence. |
| Informations financières<ul><li>Numéro de carte de crédit, de carte de débit ou de compte bancaire</li><li>Historique des achats</li><li>Infos sur la carte bancaire</li><li>Autres éléments bancaires</li></ul> | Non  <br />  <br /> Facultatif<br /><br />Non  <br />non | Les informations financières telles que les données de cartes de crédit ne doivent pas être collectées.<br /><br />Si vous mesurez les achats in-app (historique des achats), vous devez répondre **Oui** |
| Santé et forme physique<ul><li>Informations sur la santé</li><li>Informations sur la forme physique</li></ul> | Non | Ne doivent pas être collectées |
| Messages<ul><li>E-mails</li><li>Messages SMS ou MMS</li><li>Autres messages in-app</li></ul> | Non | Ne doivent pas être collectées |
| Photos ou vidéos<ul><li>Photos</li><li>Vidéos</li></ul> | Non | Ne doivent pas être collectées |
| Fichiers audio<ul><li>Enregistrements vocaux ou sonores</li><li>Fichiers de musique</li><li>Autres fichiers audio</li></ul> | Non | Ne doivent pas être collectées |
| Calendrier<ul><li>Évènements du calendrier</li></ul> | Non | Ne doivent pas être collectées |
| Activité de l'app<ul><li>Pages vues et presses in-app</li><li>Historique de recherche in-app</li><li>Apps installées</li><li>Autres contenus générés par les utilisateurs</li><li>Autres actions</li></ul> | Voir les notes | AppsFlyer mesure par défaut les lancements d'apps qui peuvent être considérés comme des pages vues ou d'autres actions.<br /><br />En outre, si vous configurez votre app pour mesurer des événements in-app spécifiques, vous devez répondre Oui, conformément à vos configurations. |
| Navigation sur Internet | Non | Ne doivent pas être collectées |
| Informations et performances de l'app<ul><li>Journaux d'erreurs</li><li>Diagnostics</li><li>Autres données de performance de l'app</li></ul> | Non<br /><br />Oui<br /><br />Oui | L'heure de lancement et/ou les niveaux de batterie peuvent être transmis pour détecter les fraudes |
| Dispositif ou autres identifiants<ul><li>Appareil ou autres identifiants (par exemple, IMEI, MAC et ID publicitaire)</li></ul> | OPTIONNELLE | L'ID publicitaire est collecté lorsque l'utilisateur est accessible |

## Partage des données

« Partagé » désigne le transfert des données à un tiers (hors appareil ou sur l'appareil).

Les exceptions sont les suivantes :

* Transferts à des prestataires de services qui traitent les données en votre nom et selon vos instructions.
* Transferts requis à des fins légales (par exemple dans le cadre d'une demande de l'État)
* Action de l'utilisateur final ou sur la base d'une divulgation majeure et d'un consentement dans l'app
* Données anonymes

Il est important de noter que même si AppsFlyer agit uniquement en tant que fournisseur de services en votre nom et selon vos instructions lorsque vous partagez des données avec des réseaux tiers (ex. via postbacks, SRN et audiences), cela reste considéré comme du partage.  Par conséquent, chaque développeur d'app devra évaluer ses configurations et les intégrations de ses partenaires et prendre les mesures qui s'imposent.

## Traitement éphémère

Le traitement éphémère fait référence aux données traitées en mémoire, uniquement pendant la période nécessaire au traitement d'une action spécifique en temps réel, et à aucune autre fin. Compte tenu de la nature des services AppsFlyer, les données traitées par AppsFlyer en votre nom ne sont pas traitées de manière éphémère.

## Choix de l'utilisateur

Les données collectées sont généralement nécessaires à l'exécution des services. Cela dit, les développeurs d'apps ont la possibilité de soumettre toute collecte de données à des options d'opt-in/opt-out.

## Objectif

Google a fourni une liste d'objectifs parmi lesquels les développeurs d'apps doivent choisir, comme le montre le tableau ci-dessous. Vous devez identifier l'objectif qui vous concerne.

| Objectif | Remarques |
| --- | --- |
| Fonctionnalité de l'app | Sélectionnez cette option si vous utilisez les données pour activer les fonctionnalités de l'app |
| Solutions d'analyse | Oui |
| Communications du développeur | Sélectionnez cette option si vous utilisez les données pour envoyer des notifications aux utilisateurs. |
| Publicité et marketing | Sélectionnez cette option si vous partagez le type de données avec une tierce partie dans le but d'afficher des publicités tierces, ou si elles sont utilisées pour promouvoir des produits ou envoyer des notifications push |
| Fraude, prévention, sécurité et conformité | Oui |
| Personnalisation | Sélectionnez cette option si vous utilisez les données pour toute personnalisation de produit |
| Gestion des comptes | Sélectionnez cette option si vous utilisez les données pour la configuration et la gestion des comptes utilisateurs |

> 📄 **À consulter également**
>
> Pour en savoir plus sur la préparation à la section « Sécurité » de Google Play et sur la manière de remplir le formulaire, lisez ces articles :
>
> * <Anchor target="_blank" href="https://android-developers.googleblog.com/2021/07/new-google-play-safety-section.html">Se préparer aux termes de la nouvelle section « Sécurité » de Google Play</Anchor>
> * <Anchor target="_blank" href="https://support.google.com/googleplay/android-developer/answer/10787469">Fournir des informations pour la section « Sécurité » de Google Play</Anchor>

<div data-zendesk-anchors="disclaimer=clause-de-non-responsabilit%C3%A9 h_01HDP3NTTKH3X3585J3DM6MCDC=clause-de-non-responsabilit%C3%A9 h_01HDP3NTTK1BDTZTHNWRM3411D=introduction h_01HDP3NTTKQE2N0HZDNGK2ZQPC=audience google-safety-form-questionnaire=formulaire-de-s%C3%A9curit%C3%A9-google-questionnaire h_01HDP3NTTKK6DJSF49326V3BEG=formulaire-de-s%C3%A9curit%C3%A9-google-questionnaire data-collection-and-security=collecte-et-s%C3%A9curit%C3%A9-des-donn%C3%A9es h_01HDP3NTTK89K8YPT6C7S9QM3W=collecte-et-s%C3%A9curit%C3%A9-des-donn%C3%A9es data-types=types-de-donn%C3%A9es h_01HDP3NTTK9DYZTQ2B64QMKGX8=types-de-donn%C3%A9es data-sharing=partage-des-donn%C3%A9es h_01HDP3NTTKF5PQ1N8VBTMB1W2Z=partage-des-donn%C3%A9es ephemeral-processing=traitement-%C3%A9ph%C3%A9m%C3%A8re h_01HDP3NTTKT7C0TGVCZJ4GR9BF=traitement-%C3%A9ph%C3%A9m%C3%A8re user-choice=choix-de-lutilisateur h_01HDP3NTTK4CT8MJ1S84MAG8VD=choix-de-lutilisateur purpose=objectif h_01HDP3NTTKD3MND388MWCC6PAT=objectif h_01HDP3RBENN69F150ESQMSVP3Q=%C3%A0-consulter-%C3%A9galement" />
