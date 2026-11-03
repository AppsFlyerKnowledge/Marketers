---
title: Bien démarrer—Introduction pour les marketeurs
metadata:
  keywords:
    - SDK
    - Integration
    - Reports
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
  created_at: '2015-01-18T11:03:01Z'
  edited_at: '2024-01-16T11:41:06Z'
  id: 207033486
  locale: fr
  section: Marketer onboarding
  section_id: 6550866490129
  url: https://support.appsflyer.com/hc/fr/articles/207033486
---
> **En bref :** exploitez tout le potentiel de votre compte AppsFlyer. Comprenez les étapes, les délais et les dépendances pour commencer à travailler sur votre app avec votre équipe.

<Embed title="Bien démarrer—Introduction pour les marketeurs" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/gamcb25kgu" providerUrl="https://fast.wistia.com" />

## Introduction

Ce document aide le marketeur (propriétaire de l'app) à **planifier et exécuter son intégration avec AppsFlyer**. Le propriétaire et le temps approximatif de mise en œuvre sont indiqués pour chaque élément.

Remarque : Les temps de réalisation de cet article ne sont donnés qu'à titre indicatif. Ils reposent sur notre expérience avec différents nouveaux clients, mais nous sommes conscients que chaque propriétaire d'app, chaque app et chaque mise en œuvre ont leurs particularités.Votre temps effectif peut donc varier.

## Configuration du compte

L'**admin du compte** doit suivre les étapes ci-dessous :

| Étape | Heure | Commentaires |
| --- | --- | --- |
| <Anchor target="_blank" href="https://www.appsflyer.com/get-started/">S'identifier</Anchor> avec AppsFlyer | 5 min | Idéalement, un admin de compte est un véritable utilisateur AppsFlyer qui peut recevoir des messages importants au besoin. |
| <Anchor target="_blank" href="/marketers/fr/docs/user-management#creating-users">Ajoutez des utilisateurs de compte</Anchor> qui utiliseront le tableau de bord AppsFlyer et définissez leurs autorisations | 1 min par utilisateur de compte | <Anchor target="_blank" href="/marketers/fr/docs/user-management#creating-users">Dans certains cas</Anchor>, les utilisateurs peuvent être ajoutés à plusieurs comptes. |

**Résultat :** Bienvenue ! Vous avez maintenant un compte AppsFlyer actif et des utilisateurs de compte qui peuvent y accéder.

> 👍 **Astuce**
>
> Vous êtes nouveau sur AppsFlyer et vous vous demandez comment bien l'utiliser ? <Anchor target="_blank" href="/marketers/fr/docs/welcome-to-appsflyer#ce-que-vous-pouvez-faire-avec-appsflyer">Découvrez cette vidéo de 6 minutes</Anchor>.

## Intégration de l'app (onboarding)

Les **étapes 1 à 3** ci-dessous sont obligatoires pour chacune des applications ajoutée à AppsFlyer (sauf mention *facultative*).

Vous pouvez suivre les étapes à l'aide de ce guide ou via la page d'onboarding de l'app (pour les apps Android et iOS uniquement). La page d'onboarding de l'app vous accompagne étape par étape pour bien préparer votre app à l'attribution. Si vous passez par la page d'onboarding, nous vous conseillons de suivre en parallèle ce guide pour connaître les étapes propres aux besoins de votre entreprise.

**Pour ouvrir la page d'onboarding de l'app :**

1. Dans la barre de menu, cliquez sur le menu utilisateur (liste déroulante de l'adresse e-mail).
2. Sélectionnez Onboarding de l'app

## Étape 2 : configuration de l'app

L'**admin du compte** doit effectuer les étapes suivantes pour chacune de vos apps :

| Étape | Heure | Commentaires |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/fr/docs/adding-an-app-to-appsflyer">Ajout d'une app</Anchor> au compte AppsFlyer | 1 min | Si l'ajout d'une app échoue, c'est souvent parce qu'elle a été associée à un compte différent (généralement une agence de publicité avec laquelle vos responsables marketing travaillent). Contactez votre CSM ou écrivez à hello@appsflyer.com pour <Anchor target="_blank" href="/marketers/fr/docs/transferring-apps-between-accounts">transférer l'app vers votre compte</Anchor>.<br /><br />Voir les <Anchor target="_blank" href="/marketers/fr/docs/adding-an-app-to-appsflyer#dépannage">étapes de dépannage</Anchor> supplémentaires pour l'ajout d'une app. |
| Définit le <Anchor target="_blank" href="/marketers/fr/docs/adding-an-app-to-appsflyer#enter-additional-information-not-applicable-to-web-apps">fuseau horaire de l'app</Anchor> , la devise et si l'app est destinée aux enfants. | 1 min |  |
| Définir la   <br /><Anchor target="_blank" href="/marketers/fr/docs/set-up-re-attribution-window">fenêtre de réattribution</Anchor> de l'app (sur la page <Anchor target="_blank" href="/marketers/fr/docs/app-settings#reattribution-window">Paramètres de l'app</Anchor>) | 1 min | La fenêtre de réattribution est la période qui commence à la date de la première installation, et pendant laquelle **les réinstallations ne peuvent pas être attribuées en tant que nouvelles installations.** La valeur par défaut est de 90 jours mais vous pouvez la personnaliser. |
| [Facultatif] Migrer les appareils des utilisateurs existants vers AppsFlyer | 2 heures | Si votre app dispose déjà d'une base d'utilisateurs conséquente, envisagez de <Anchor target="_blank" href="/marketers/fr/docs/migration-to-appsflyer-from-other-vendors#migration-dappareil-facultatif">migrer cette dernière vers AppsFlyer</Anchor> pour éviter les doubles frais.<br /><br />**Remarque** :   <br />vous pouvez demander l'aide de votre CSM AppsFlyer ou de l'équipe d'assistance à l'adresse [hello@appsflyer.com](mailto:hello@appsflyer.com)) |

**Résultat :** vos apps sont maintenant définies dans le tableau de bord AppsFlyer.

## Étape 3 : intégration du SDK

Complétez les étapes suivantes pour chacune des apps que vous avez définies dans l'[étape 1 de la configuration de l'app.](/docs/getting-started-onboarding-for-marketers#étape-2-configuration-de-lapp)

| Étape | Propriétaire | Heure | Commentaires |
| --- | --- | --- | --- |
| Examen des options disponibles et sélection des <Anchor target="_blank" href="/marketers/fr/docs/sdk-integration-overview">fonctionnalités du SDK</Anchor> que vous souhaitez utiliser pour votre app. | Chef de produits | 1 heure | <ul><li>Quelques considérations qui vont au-delà de l'attribution de base :<ul><li>Vos campagnes vont-elles deep linker les utilisateurs dans l'app ?</li><li>L'app aura-t-elle besoin d'<Anchor target="_blank" href="/marketers/fr/docs/basic-sdk-integration-guide#accéder-aux-données-dattribution-et-de-deep-linking">accéder aux données d'attribution ou de deep linking</Anchor> ?</li><li>Les données AppsFlyer doivent-elles contenir votre <Anchor target="_blank" href="/marketers/fr/docs/basic-sdk-integration-guide#integrate-unique-identifiers-from-your-bi-system-with-appsflyer">ID utilisateur client</Anchor> pour référence ?</li><li>Comment allez-vous mettre en œuvre les <Anchor target="_blank" href="/marketers/fr/docs/basic-sdk-integration-guide#configure-app-tracking-transparency-att-support">paramètres de confidentialité de pour les appareils iOS 14 et +</Anchor> ? Voulez-vous mesurer les désinstallations, mener des campagnes de promotion croisée et bien plus encore ?</li></ul></li><li>Votre application est une CTV ? Découvrez notre <Anchor target="_blank" href="/marketers/fr/docs/ctv-pc-and-console-platform-attribution-concepts">Présentation de la CTV</Anchor>.</li></ul> |
| Sélection des <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview">événements d'app</Anchor> à enregistrer | Chef de produits | 1 heure | L'enregistrement des événements post-installation que vos utilisateurs effectuent dans l'app vous aide à mieux comprendre la **qualité** de vos utilisateurs.<br /><br />Visitez le [générateur d'événements in-app](https://evgen.appsflyer.com/) pour découvrir notre liste exhaustive des <Anchor target="_blank" href="/marketers/fr/docs/in-app-events-overview#recommended-events-by-business-vertical">événements et paramètres in-app recommandés</Anchor> en fonction de votre activité. Vous pouvez ajouter vos propres événements et paramètres.  <br />Cliquez sur le bouton **Code** pour afficher et copier le code qui sera généré automatiquement pour vos développeurs (et pour leur plus grand bonheur). |
| Sélection de méthodes de récupération des données d'attribution/de deep linking | Chef de produits | 30 min | En savoir plus sur les <Anchor target="_blank" href="/marketers/fr/docs/basic-sdk-integration-guide#accéder-aux-données-dattribution-et-de-deep-linking">méthodes</Anchor> disponibles :<ul><li><Anchor target="_blank" href="/marketers/fr/docs/pull-api-raw-data">API pull</Anchor></li><li><Anchor target="_blank" href="/marketers/fr/docs/push-api-streaming-raw-data">API push</Anchor></li><li><Anchor target="_blank" href="/marketers/fr/docs/create-a-onelink-template">API de deep linking unifié</Anchor></li><li><Anchor target="_blank" href="/marketers/fr/docs/conversion-data-payloads-and-scenarios">Obtenir les données de conversion</Anchor></li></ul> |
| Mise en œuvre par le développeur | Développeur d'apps | 3 heures | Ressources AppsFlyer pour vos développeurs :<ul><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk">Android</Anchor></li><li><Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-ios-sdk">iOS</Anchor></li><li>Unity</li><li><Anchor target="_blank" href="/marketers/fr/docs/windows-sdk-integration-for-developers">Windows phone</Anchor></li><li><Anchor target="_blank" href="/marketers/fr/docs/other-platforms">Autres plates-formes</Anchor></li></ul> |
| <Anchor target="_blank" href="/marketers/fr/docs/testing-the-sdk-integration-for-marketers">Test d'intégration</Anchor> | Chef de produit/  <br />Développeur d'apps | 1 heure | Vous pouvez tester l'intégration de votre SDK avant ou après la mise en ligne de votre app dans l'app store. Vous pouvez utiliser des applications de débogage pour garder vos données d'app ordonnées.<br /><br />Veillez à <Anchor target="_blank" href="/marketers/fr/docs/registering-test-devices">enregistrer vos appareils de test</Anchor>. |
| Lancement d'une nouvelle version de l'app | Chef de produits | 1 heure | <Anchor target="_blank" href="/marketers/fr/docs/preparing-for-the-app-store-review-nutrition-labels">Préparation à l'examen de l'App Store iOS</Anchor>. |

**Résultat :** vos apps sont prêtes pour l'attribution des installations, la mesure des événements d'app et d'autres fonctionnalités d'AppsFlyer qui ne nécessiteront pas de ressources de développement supplémentaires.

## Étape 4 : configuration de l'attribution

Complétez les étapes suivantes pour chacune des apps que vous avez définies dans l'[étape 1 de la configuration de l'app.](/docs/getting-started-onboarding-for-marketers#étape-2-configuration-de-lapp)

| Étape | Propriétaire | Heure | Commentaires |
| --- | --- | --- | --- |
| Configurer des sources média **payantes** pour l'attribution dans AppsFlyer | Chef de produit/  <br />marketer | 15 minutes par source média | En savoir plus sur l'attribution des <Anchor target="_blank" href="/marketers/fr/docs/self-reporting-networks-srns">réseaux auto-reporting (SRN)</Anchor>, en particulier :<ul><li><Anchor target="_blank" href="/marketers/fr/docs/google-ads-adwords-integration-setup-for-advertisers">Google Ads</Anchor></li><li><Anchor target="_blank" href="/marketers/fr/docs/meta-ads-integration-setup">Meta Ads</Anchor></li><li><Anchor target="_blank" href="/marketers/fr/docs/apple-ads-integration-setup">Apple Search Ads</Anchor></li><li>GMP (Doubleclick)</li></ul>En savoir plus sur l'attribution de réseaux publicitaires non SRN :<ul><li><Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner">Autres partenaires intégrés</Anchor></li><li>Structure et paramètres du <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters">lien d'attribution</Anchor> AppsFlyer</li></ul> |
| Utilisation de OneLink pour attribuer **des sources média propres** : sites web mobile, réseaux sociaux, invitations d'utilisateurs, etc. | Chef de produits | 1 heure | Découvrez les solutions <Anchor target="_blank" href="/marketers/fr/docs/onelink-guide#options-supplémentaires">basées sur OneLink</Anchor> pour les cas d'utilisation de vos médias propres. |
| Implémentation de médias propres par le développeur | Développeur d'apps | 0-6h30 (en fonction des solutions mises en œuvre) | Pour les développeurs : <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/getting-started-1">démarrer avec le deep linking</Anchor> |
| Mettre en place des fenêtres d'attribution | Chef de produits | 2 min par source média | En savoir plus : <Anchor target="_blank" href="/marketers/fr/docs/set-up-lookback-windows">explication des fenêtres rétrospectives post vue et post clic</Anchor> |
| [Facultatif] Activer les campagnes de retargeting | Chef de produits | 2 min | <Anchor target="_blank" href="/marketers/fr/docs/app-settings#reengagement-attribution">Activez le retargeting sur la page des paramètres d'app</Anchor>.<br /><br />En savoir plus : <Anchor target="_blank" href="/marketers/fr/docs/retargeting-attribution-guide">guide du retargeting</Anchor> |

**Résultat :** toutes les sources média qui acheminent du trafic vers vos apps sont attribuées chaque fois que des utilisateurs nouveaux ou récurrents interagissent avec elles.

## Étape 5 : configuration supplémentaire

Complétez les étapes suivantes pour chacune des applications définies dans l'[étape 1 de la configuration de l'app.](/docs/getting-started-onboarding-for-marketers#étape-2-configuration-de-lapp)

Certains éléments sont obligatoires pour vous permettre d'atteindre les objectifs de votre entreprise.

| Étape | Propriétaire | Ressources supplémentaires |
| --- | --- | --- |
| Optimisation des campagnes d'acquisition d'utilisateurs en enregistrant les revenus | Chef de produit/  <br />Développeurs | <ul><li><Anchor target="_blank" href="/marketers/fr/docs/legacy-receipt-validation-for-in-app-purchases">Validation des achats d'app</Anchor></li><li><Anchor target="_blank" href="/marketers/fr/docs/roi360-guide-ad-revenue-attribution">monétisation publicitaire</Anchor></li><li>Abonnements des utilisateurs</li></ul> |
| Méthodes permettant d'agréger et de visualiser les données sur les coûts de marketing | Chef de produits | <Anchor target="_blank" href="/marketers/fr/docs/roi360-cost-aggregation-overview">ROI360—Présentation de l'agrégation des coûts</Anchor> |
| Configuration des autres <Anchor target="_blank" href="/marketers/fr/docs/3rd-party-platforms">plateformes tierces</Anchor> avec lesquelles votre app fonctionne | Chef de produit/  <br />Développeurs | <ul><li><Anchor target="_blank" href="/marketers/fr/docs/mparticle-integration-with-appsflyer">mParticle</Anchor></li><li><Anchor target="_blank" href="/marketers/fr/docs/segment-integration">Segment</Anchor></li><li><Anchor target="_blank" href="/marketers/fr/docs/mixpanel-integration-with-appsflyer">Mixpanel</Anchor></li><li><Anchor target="_blank" href="/marketers/fr/docs/amplitude-integration-with-appsflyer">Amplitude</Anchor></li><li><Anchor target="_blank" href="/marketers/fr/docs/adobe-analytics-integration-with-appsflyer">Adobe Analytics</Anchor> (Omniture)</li><li><Anchor target="_blank" href="/marketers/fr/docs/braze-formerly-appboy-integration-with-appsflyer">Braze</Anchor></li></ul> |
| Fonctionnalités premium d'AppsFlyer qui vous permettront de gagner du temps et de l'argent. | Chef de produits | <ul><li><Anchor target="_blank" href="/marketers/fr/docs/audiences-guide">Audiences</Anchor></li><li><Anchor target="_blank" href="/marketers/fr/docs/pivot-table-user-metrics">Tableau Pivot</Anchor></li><li><Anchor target="_blank" href="/marketers/fr/docs/data-locker-for-marketers">Data Locker</Anchor></li></ul> |
| Protégez vos campagnes de la fraude et des mauvais ciblages | Chef de produits | <ul><li><Anchor target="_blank" href="/marketers/fr/docs/protect360-anti-fraud-guide">Protect360—Solution antifraude</Anchor></li><li>Utilisez les <Anchor target="_blank" href="/marketers/fr/docs/implement-validation-rules-to-prevent-fraud">règles de validation</Anchor> pour vous assurer que les campagnes ne sont pas mal ciblées</li><li>Définissez des alertes en direct pour surveiller un large éventail de KPI en temps réel</li></ul> |
| Utilisation d'une API de serveur à serveur pour les événements d'app signalés à l'extérieur de celle-ci | Chef de produit/  <br />Développeurs | <Anchor target="_blank" href="/marketers/fr/docs/server-to-server-events-api-for-mobile-s2s-mobile">API S2S REST</Anchor> |
| Mesure des taux de désinstallation de vos sources média | Chef de produit/  <br />Développeurs | Mesure des désinstallations |
| Vue unifiée de la navigation de vos clients sur tous les canaux, plates-formes et appareils | Chef de produit/  <br />Développeurs | <Anchor target="_blank" href="/marketers/fr/docs/people-based-attribution-pba-overview">Attribution basée sur les personnes (PBA)</Anchor> |
| Conformité aux réglementations en matière de confidentialité : RGPD, CCPA, etc. | Chef de produit/  <br />Développeurs | Permet aux utilisateurs de <Anchor target="_blank" href="/marketers/fr/docs/apply-privacy-preserving-sdk-methods">désactiver</Anchor> l'attribution. |

## Enrichir vos connaissances

Recommandé pour tous les utilisateurs d'AppsFlyer :

| Étape | Heure |
| --- | --- |
| Utiliser le tableau de bord général d'AppsFlyer | 15 min |
| Explorer les différences entre les données sur la durée de vie (LTV) <Anchor target="_blank" href="/marketers/fr/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">et les données sur l'activité</Anchor> dans AppsFlyer (pour comprendre pourquoi le résumé des événements d'app diffère entre les tableaux de bord Vue d'ensemble et Activité) | 15 min |
| Comprendre le <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-attribution-model">modèle d'attribution</Anchor> AppsFlyer | 30 min |
| En savoir plus sur les <Anchor target="_blank" href="/marketers/fr/docs/aggregated-and-analytics-reporting-overview">outils de rapport et d'analyse agrégés.</Anchor> | 30 min |
| En savoir plus sur les <Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview">rapports de données brutes</Anchor> | 30 min |

## Connexe

> 👍 **Astuce**
>
> Vous débutez avec l'AU ? Découvrez <Anchor target="_blank" href="https://www.appsflyer.com/resources/ecommerce/getting-started-user-acquisition-apps-complete-guide/">tout sur</Anchor> les plus grands défis et les facteurs de réussite essentiels à la planification, l'exécution et l'optimisation continue de vos efforts d'acquisition d'utilisateurs.

> 📘 **Remarque**
>
> Vous découvrez AppsFlyer mais vous n'êtes pas marketeur ? Ne vous inquiétez pas !
> Choisissez le guide qui vous convient ci-dessous, et commençons :
>
> * <Anchor target="_blank" href="/partners/fr/docs/getting-started-agency-onboarding">Comment démarrer pour les agences</Anchor>
> * <Anchor target="_blank" href="/partners/fr/docs/getting-started-onboarding-guide-for-ad-networks">Comment démarrer pour les réseaux publicitaires</Anchor>

<div data-zendesk-anchors="01H8BD2FJ6TQ5FP9625MNP2B3Z=introduction step-1-account-setup=configuration-du-compte 01H8BD2FJ6E8KZW41V04SBDQPQ=configuration-du-compte 01H8BD2FJ6A39JB8J0PQ3EY52N=astuce app-onboarding=int%C3%A9gration-de-lapp-onboarding 01H8V6FS97NTTF1VPQQDZQT973=int%C3%A9gration-de-lapp-onboarding step-2-app-setup=%C3%A9tape-2-configuration-de-lapp 01H8BD2FJ61S3Z22CD01H6F39E=%C3%A9tape-2-configuration-de-lapp step-3-sdk-integration=%C3%A9tape-3-int%C3%A9gration-du-sdk 01H8BD2FJ6CY53QXVB5QC98KTT=%C3%A9tape-3-int%C3%A9gration-du-sdk step-4-attribution-setup=%C3%A9tape-4-configuration-de-lattribution 01H8BD2FJ6Q8R83FV0XS5B93B3=%C3%A9tape-4-configuration-de-lattribution step-5-additional-setup=%C3%A9tape-5-configuration-suppl%C3%A9mentaire 01H8BD2FJ76WD0MRCJXZH8XABN=%C3%A9tape-5-configuration-suppl%C3%A9mentaire enrich-your-knowledge=enrichir-vos-connaissances 01H8BD2FJ7ZV0ZYHQZ8DBTTFFK=enrichir-vos-connaissances related=connexe 01H8BD2FJ748GFC4VJWWYGGN1K=connexe 01H8BD2FJ712NGA534TCSWQGR8=astuce-1 01H8BD2FJ7PRJAA1K8MESRK7VA=remarque" />
