---
title: Exclure certains utilisateurs des campagnes d'acquisition d'utilisateurs (AU)
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2020-05-03T10:11:31Z'
  edited_at: '2021-04-21T00:13:02Z'
  id: 360007949158
  locale: fr
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/fr/articles/360007949158
---
> **En bref** : ne pas inclure les utilisateurs existants dans les campagnes d'acquisition d'utilisateurs (AU) permet d'obtenir un plus grand nombre d'installations avec le même budget, tout en améliorant le ROAS.

## Difficultés et conséquences

Si votre app reçoit du trafic issu de différentes sources média, ces sources peuvent cibler vos utilisateurs existants dans leurs campagnes AU.

L'efficacité d'une campagne peut être diminuée pour les raisons suivantes :

| Doubles paiements | Payer pour les impressions / clics d'utilisateur que vous avez déjà payés par le passé. |
| --- | --- |
| Taux de conversion incorrects | Les campagnes AU semblent moins productives. Il y a moins d'installations car les impressions sont gaspillées par les utilisateurs existants. |
| Perte d'utilisateurs potentiels | Un non-utilisateur aurait pu lire les publicités et devenir l'un de vos utilisateurs mobiles. |

Typiquement, les performances sont également affectées par <Anchor target="_blank" href="/marketers/fr/docs/self-reporting-networks-srns#what-is-srn-mistargeting">un mauvais ciblage du SRN</Anchor>. Ce problème critique peut se produire si vos campagnes UA et vos campagnes de retargeting pointent vers le même SRN. <Anchor target="_blank" href="/marketers/fr/docs/self-reporting-networks-srns#le-mauvais-ciblage-pose-t-il-des-problèmes">En savoir plus</Anchor>

## Solutions

Ces solutions décrivent comment mettre à jour les ad networks afin d'exclure les utilisateurs existants des campagnes UA.

### Mise à jour manuelle

Depuis AppsFlyer, collectez vos données d'installation brutes de niveau utilisateur afin de créer des listes d'ID d'appareil. Envoyez ensuite ces listes aux ad networks pour faire appliquer l'exclusion d'utilisateurs.

L'ajout de ces données brutes à votre système BI peut se faire de différentes manières :

* Téléchargez les rapports de données brutes
* Utilisez périodiquement des requêtes API Pull de données brutes
* Utilisez l'API Push pour implémenter la collecte en temps réel
* Obtenez les données de conversion depuis le SDK

> 📘 **Remarque**
>
> Dans l'intervalle de temps situé entre deux envois manuels de liste aux ad networks, les campagnes UA peuvent cibler vos tous nouveaux utilisateurs d'app.

### Audiences

**<Anchor target="_blank" href="/marketers/fr/docs/audiences-guide">Audiences</Anchor>** est une fonctionnalité premium AppsFlyer. Chaque jour, des segments sélectionnés dans votre base d'utilisateurs sont envoyés automatiquement aux différents réseaux publicitaires de votre choix.

**Audiences** est très pratique pour gérer les listes d'exclusion :

| Effort minimum | Aucun travail de développement ou de maintenance n'est exigé de votre part ou de la part du réseau publicitaire. |
| --- | --- |
| Simple à utiliser | Après une brève configuration de base, vous pouvez commencer à télécharger les audiences. |
| Efficace | Les segments sont envoyés automatiquement aux réseaux publicitaires toutes les 24 heures. |