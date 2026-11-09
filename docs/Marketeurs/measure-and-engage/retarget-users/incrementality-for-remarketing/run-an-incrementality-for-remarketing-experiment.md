---
title: Lancez une expérience d'incrémentalité
metadata:
  keywords:
    - Advertisers
    - Premium
    - Marketers
    - Incrementality
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-niv-klein
    - Marketers
    - Incrementality
  created_at: '2020-10-12T19:26:09Z'
  edited_at: '2024-11-19T15:37:38Z'
  id: 360014225577
  locale: fr
  section: Incrementality for remarketing
  section_id: 6551378485649
  url: https://support.appsflyer.com/hc/fr/articles/360014225577
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En bref :** Réalisez une expérience d'incrémentalité pour comprendre l'impact réel de vos campagnes de remarketing.

<Image align="center" alt="KB_toggle_final.jpg" src="https://files.readme.io/4de8c3ff1edaaae77fc0571de6125b25c884bcc4e4ac67471fc90610298866e1-30780522054801.jpg" />

<div id="about-the-experiment" />

## À propos de l'expérience

Les tests d'<Anchor target="_blank" href="/marketers/fr/docs/incrementality-for-remarketing-overview">incrémentalité</Anchor> mesurent l'impact réel de vos campagnes grâce à des tests A/B qui évaluent précisément « l'augmentation incrémentielle » — la différence entre les conversions générées par vos campagnes de remarketing et celles qui se seraient produites malgré tout.

Les résultats sont essentiels pour comprendre la réelle valeur que vos investissements marketing génèrent. Avec les tests d'incrémentalité, vous pouvez objectivement observer l'impact de canaux et de campagnes spécifiques, et prendre de meilleures décisions concernant l'allocation budgétaire et l'optimisation des campagnes.

AppsFlyer simplifie les tests d'incrémentalité grâce à un processus automatisé initié lors de la création de l'audience. La nouvelle audience est automatiquement répartie entre les partenaires média connectés et un groupe de contrôle via l'activation de l'option « Mesurer l'impact incrémentiel ». Le groupe de contrôle est la partie de l'audience retenue des partenaires, constituant un élément indispensable des tests. Une fois l'audience enregistrée, une expérience d'incrémentalité est automatiquement créée. Après avoir lancé vos campagnes auprès des partenaires et vous être assuré que les campagnes adéquates sont affectées, vous pourrez visionner les résultats de l'expérience dans le tableau de bord d'incrémentalité.

<div id="get-started" />

## Commencez

Suivez ces étapes pour débuter les tests d'incrémentalité. Pour plus de détails sur chaque étape, consultez [Configurer l'expérience](/docs/run-an-incrementality-for-remarketing-experiment#configurer-lexpérience) ci-dessous.

|  | Étapes |
| --- | --- |
| 1 | [**Établissez vos objectifs de test**](/docs/run-an-incrementality-for-remarketing-experiment#know-your-test-objectives)<br /><br />Maximisez l'efficacité des résultats de votre expérience en définissant des objectifs de test clairs et une hypothèse pour les résultats attendus. |
| 2 | **[Créez le public cible et répartissez les groupes](/docs/run-an-incrementality-for-remarketing-experiment#create-the-target-audience-and-split-groups)**<br /><br />Dans <Anchor target="_blank" href="/marketers/fr/docs/audiences-guide">Audiences</Anchor> :<ul><li>Configurez l'audience.</li><li>Connectez-la aux réseaux publicitaires.</li><li>L'audience est automatiquement divisée en groupes de test et de contrôle, via une bascule activée (pour les abonnés Incrementality, dans les audiences créées après le 11 janvier 2023).</li></ul>AppsFlyer Audiences télécharge les membres du groupe de test sur les réseaux publicitaires et retient ceux du groupe de contrôle. |
| 3 | [**Lancez la campagne et l'expérience**](/docs/run-an-incrementality-for-remarketing-experiment#launch-the-campaign-and-experiment)<ul><li>Sur les réseaux publicitaires, créez et lancez une campagne qui cible les utilisateurs de l'audience.</li><li>L'expérience d'incrémentalité est générée automatiquement (pour les abonnés à l'incrémentalité).</li></ul>Les membres du groupe test sont exposés aux publicités. Le groupe de contrôle ne l’est pas. |
| 4 | **[Analyser les résultats](/docs/run-an-incrementality-for-remarketing-experiment#analyze-the-results)**<ul><li>L'analyse d'incrémentalité est visible sur le <Anchor target="_blank" href="/marketers/fr/docs/incrementality-for-remarketing-overview#tableau-de-bord-dincrémentalité">tableau de bord d'incrémentalité</Anchor>.</li><li>Les données utilisateur détaillées sont accessibles dans les <Anchor target="_blank" href="/marketers/fr/docs/incrementality-for-remarketing-overview#rapports-de-données-brutes">rapports de données brutes d'incrémentalité</Anchor> (via Data Locker).</li></ul>Les informations obtenues grâce à des expériences d'incrémentalité bien menées permettent d'optimiser vos campagnes marketing pour un impact positif maximal. Par exemple, elles peuvent vous orienter vers le meilleur message pour une audience cible, la meilleure création ou promotion, la source média la plus efficace, et bien plus encore. |

<div id="set-up-the-experiment" />

## Configurer l'expérience

<div id="know-your-test-objectives" />

<Accordion title="Définissez vos objectifs de test">

Comme dans toute expérience, il est essentiel de préciser exactement ce que vous testez (variables) et d'anticiper le résultat attendu (l'hypothèse). Le tableau ci-dessous fournit des lignes directrices et des bonnes pratiques pour concevoir votre expérience :

| Variables/Hypothèses | Lignes directrices et bonnes pratiques |
| --- | --- |
| Audience | Décrivez l'audience que vous testez. Choisissez une audience déjà configurée dans AppsFlyer Audiences ou créez-en une nouvelle qui répond à vos critères de test. |
| Taille de l'audience | Sélectionnez une audience avec une grande base d'utilisateurs et un événement avec des taux de conversion élevés. Un échantillon de grande taille est plus susceptible de produire des <Anchor target="_blank" href="/marketers/fr/docs/incrementality-for-remarketing-overview#statistical-significance">résultats significatifs sur le plan statistique</Anchor>.<br /><br />**Bonne pratique :** Une audience d'au moins 50 000 utilisateurs, répartis entre 1 à 3 réseaux publicitaires + le groupe de contrôle. |
| Campagne | Décrivez la campagne (message, incitations, etc.). |
| % du groupe de contrôle | Le groupe de contrôle est automatiquement défini à 15 % de la taille de l'audience (la bonne pratique est entre 15 % et 25 %). |
| Groupe test | Identifiez les réseaux publicitaires que vous souhaitez tester. Le pourcentage sera réparti de manière égale entre eux (vous pouvez ajuster le pourcentage de l'audience envoyé à chacun).<br /><br />**Bonne pratique :** 1 à 3 réseaux publicitaires |
| Hypothèse | Définir les résultats attendus de l'expérience.<br /><br />Bien qu'il puisse sembler un peu contre-intuitif de prévoir le résultat avant de commencer, formuler une hypothèse est un élément essentiel de la conception expérimentale ; c'est ce qui vous aide à interpréter vos résultats.<br /><br />**Bonne pratique :** Énoncez une hypothèse facilement testable en utilisant des pourcentages concrets au lieu d'estimations vagues. Par exemple :<ul><li>***15 % d'utilisateurs supplémentaires achèteront une mise à niveau*** est une hypothèse facilement testable.</li><li>***Beaucoup plus d'utilisateurs achèteront une mise à niveau*** est plus difficile à tester.</li></ul> |

<div id="example" />

> 📄 **Exemple**
>
> En suivant les directives ci-dessus, vous pouvez définir une expérience semblable à ce qui suit.
>
>
>
> | Variables/Hypothèses | Exemple |
> | --- | --- |
> | Audience | Utilisateurs ayant terminé l'inscription mais n'ayant pas effectué d'achat |
> | Taille de l'audience | 100 000 |
> | Campagne | Une campagne qui offre un bon de réduction aux utilisateurs effectuant un achat durant une période déterminée |
> | % du groupe de contrôle | 15 % de la taille de l'audience |
> | Groupe test | Envoyez le reste des membres de l'audience à :<br /><br />* Réseau A (42 % de l'audience)<br />* Réseau B (43 % de l'audience) |
> | Hypothèse | Le taux d'utilisateurs du groupe test interagissant avec la campagne de remarketing et réalisant un achat sera 10 % supérieur à celui des utilisateurs du groupe témoin. |

</Accordion>

<div id="create-the-target-audience-and-split-groups" />

<Accordion title="Créez l'audience cible et répartissez les groupes">

Après avoir défini vos objectifs, l'étape suivante consiste à configurer l'audience que vous testerez :

1. Dans AppsFlyer Audiences, <Anchor target="_blank" href="/marketers/fr/docs/audiences-guide#créer-et-gérer-les-audiences">créez une audience</Anchor> (ou divisez une audience existante qui répond aux exigences de votre conception expérimentale).
2. Dans l'onglet **Connecter** de l'audience sélectionnée :
   * Connectez l'audience à 1 à 3 partenaires de réseaux publicitaires.
   * Assurez-vous que l'option de division de l'audience est activée (elle est **automatiquement activée pour les abonnés à l'incrémentalité, sur les audiences créées après le 11 janvier 2023**). Sinon, cliquez sur l'interrupteur pour l'activer.  

     <Image align="center" alt="Mesure_inc_impact_bascule.jpg" src="https://files.readme.io/a04b3be68fcc00d62e6a92391fbbea685ca2bfcbf83bd5678660c6a1b8c58fc2-30780493858065.jpg" />
   * Le groupe témoin est automatiquement fixé à 15 % (recommandé).
   * Le reste de l'audience est automatiquement réparti équitablement entre les partenaires des réseaux publicitaires sélectionnés.
     * Le pourcentage total de répartition doit être égal à 100 % (y compris le groupe témoin).

Une fois que vous avez enregistré votre audience avec la division activée, une expérience d'incrémentalité est automatiquement lancée (réservé aux abonnés à l'incrémentalité). Ces expériences peuvent être visualisées sur le tableau de bord d'incrémentalité avec le préfixe «[Auto]» avant le titre.

<Image align="center" alt="Auto_avant_titre.jpg" src="https://files.readme.io/fdab39eee29240ae0d9b907f7c6504a9e08e470454d5f8e43933512c65db15d4-30780522066833.jpg" />

**Remarques importantes :**

* Pendant que l'expérience est en cours, n'apportez aucune modification à la configuration de l'audience. Les modifications des partenaires, du nom de l'audience ou d'autres paramètres entraîneront des analyses statistiques inexactes.  
  **Bonne pratique :** Même après la conclusion d'une expérience, si vous devez modifier la définition d'une audience précédemment testée, dupliquez d'abord l'audience, puis effectuez les modifications sur la nouvelle copie. Cela garantit l’intégrité continue des données historiques sur le tableau de bord d’incrémentalité.
* Modifier la répartition et la configuration des partenaires d'une audience existante mettra fin à l'expérience d'incrémentalité en cours et en créera une nouvelle.
* #### <span id="check-for-audience-expansion-features"></span>Vérifiez les fonctionnalités d’extension d’audience :

Les publicités Meta et Google Ads ont toutes deux une fonctionnalité optionnelle qui permet aux campagnes de cibler au-delà d'une liste d'audience configurée pour élargir la portée de la campagne. Cette fonctionnalité, si elle reste activée, influencera les expériences d'incrémentalité et faussera les résultats. **Veuillez vérifier que cette fonctionnalité est désactivée.**

Dans les publicités Meta, la fonctionnalité s'appelle « Audience personnalisée Advantage ». Elle apparaît au niveau de l'ensemble d'annonces et est activée par défaut.

<Image align="center" alt="image__4_.png" src="https://files.readme.io/a0bee1bbb2c6521007146a5ac70de52ce821f459fd2aece127a97a2e0b75c93d-30780493862033.png" width="458px" />
Dans Google Ads, cela s'appelle « élargissement de l'audience ».

<Image align="center" alt="Limitation_d'incrémentalité_de_Google_Ads_cropped.jpg" src="https://files.readme.io/042aac534d0a527753b643bb63a52f59889219ebda922cc04f8a61c5984afb80-30780493867409.jpg" width="436px" />

</Accordion>

<div id="launch-the-campaign-and-experiment" />

<Accordion title="Lancez la campagne et expérimentez">

**Prenez les mesures suivantes :**

<div id="1-configure-campaigns-on-ad-networks" />

#### 1. Configurez des campagnes sur les réseaux publicitaires

La première étape consiste à créer une campagne qui cible les utilisateurs de votre audience et à la lancer sur le réseau publicitaire (pour chaque réseau publicitaire vers lequel l'audience est téléchargée).

* **Important !** Pour obtenir des résultats de test précis, configurez la campagne pour qu'elle cible **uniquement** les utilisateurs de l'audience testée ; n'incluez pas les utilisateurs d'autres sources.
* Si l'audience testée est une audience nouvellement créée, il peut falloir jusqu'à 24 heures pour que celle-ci soit disponible sur la plateforme du réseau publicitaire.

<div id="2-ensure-the-correct-campaign-is-linked-to-the-experiment" />

#### 2. Assurez-vous que la bonne campagne est liée à l'expérience.

Une nouvelle expérience d'incrémentalité est automatiquement lancée lorsqu'une audience est créée avec l'option « Mesurer l'impact incrémentiel » activée (ou activée sur une audience existante). La campagne la plus pertinente est automatiquement associée à l'expérience, mais vous pouvez modifier cette campagne si vous le souhaitez.

**Pour lier/modifier une campagne :**

1. Depuis le **tableau de bord d'incrémentalité**, accédez à l'expérience spécifique, puis cliquez sur **Modifier l'expérience**.

<Image align="center" alt="Edit_experiment.jpg" src="https://files.readme.io/f478737e2a8db560a5ea33b287fe8f41587ec1f743c1bc01ba15ab6ce72478e9-30780493873425.jpg" width="642px" />

Ou

Dans **Audiences**, localisez l'audience spécifique, puis cliquez sur **+ Lier la campagne** dans la colonne Incrémentalité.

<Image align="center" alt="Link_campaign__audiences_status_.jpg" src="https://files.readme.io/5da762448fb731843fef0aec66ae826ed6922a5dd213a78ccd93f544b21fcfdc-small-30780522084625.jpg" width="768px" />

Une fenêtre s'affiche, vous permettant de lier des campagnes.

<Image align="center" alt="Link_campaign_to_experiment_window.jpg" src="https://files.readme.io/9492444847bfc6a26778624d72d5b468acc62b705530db66d0bd0fdff89f5e89-30780493883409.jpg" width="506px" />

2. Sélectionnez la ou les campagnes pertinentes pour chaque réseau publicitaire.

**Remarque :** Le menu déroulant sera rempli des campagnes provenant de vos partenaires média. Lorsque les données sont disponibles, les campagnes dans la liste déroulante seront classées selon leur probabilité d'être utilisées pour cibler l'audience spécifique. La suggestion principale sera pré-sélectionnée pour vous.

3. Cliquez sur **Enregistrer**.

La campagne est maintenant liée à l'expérience.

<div id="manually-create-an-experiment" />

#### Créer manuellement une expérience

Si vous êtes abonné à Incrementality et avez créé votre audience après le 11 janvier 2023, il n'est pas nécessaire de créer manuellement une expérience. Les expériences sont automatiquement créées pour vos audiences (et apparaissent sur le tableau de bord d'incrémentalité avec « [Auto] » avant le titre). Si vous souhaitez créer manuellement une expérience pour une audience antérieure ou pour une autre raison, suivez ces étapes.

**Pour créer manuellement une nouvelle expérience d'incrémentalité :**

* Dans AppsFlyer, dans le menu latéral, sélectionnez **Optimiser** > **Incrémentalité**.
* Sur la page **Expériences d'incrémentalité**, cliquez sur le bouton **Nouvelle expérience**.
* Suivez les étapes de l'assistant pour créer l'expérience. Des instructions détaillées vous sont fournies à chaque étape.

  <div id="notes" />

  > 📘 **Remarques**
  >
  > **Étape 2 de l'assistant – Configuration de l'audience**
  >
  > À l'étape 2 de l'assistant, il vous est demandé de sélectionner la **date à partir de laquelle les membres de l'audience doivent être inclus dans l'expérience.**
  >
  > Par défaut, c'est la date à laquelle l'audience a été initialement divisée avec un groupe témoin. Pour garantir des résultats précis de l'expérience, vous devez modifier cette date si l'une des situations suivantes s'applique :
  >
  > * Si vous avez apporté des modifications à la définition de l'audience sélectionnée (<Anchor target="_blank" href="/marketers/fr/docs/audiences-guide#tout-savoir-sur-les-ensembles-de-règles">ensembles de règles de segmentation de l'audience</Anchor>, <Anchor target="_blank" href="/marketers/fr/docs/audiences-guide#user-identifier-device-id-vs-customer-id">identifiant utilisateur</Anchor>, etc.), → modifiez cette date pour qu'elle corresponde à la dernière date de modification de ces définitions d'audience.
  > * Si vous testez une nouvelle campagne sur une audience préexistante → modifiez cette date à celle du lancement de la nouvelle campagne.
  >
  > **Étape 3 de l'assistant – Définir des objectifs**
  >
  > <Image align="center" alt="Étape_3_Définir_des_cibles.jpg" src="https://files.readme.io/9c58ad61463b1751f5ad8b2c5235d6d61b13baa156db56d5edeb156debbcfeaa-30780522104081.jpg" />
  >
  > C'est ici que vous devez sélectionner l'application cible et les indicateurs clés de performance (KPI).
  >
  > **Remarque :** Tous les autres KPI seront disponibles à la fin de l'expérience, même s'ils n'ont pas été sélectionnés.
  >
  > **Étape 4 de l'assistant – Révision**
  >
  > À l'étape 4 de l'assistant, il vous est demandé de définir la **période d'expérimentation.**
  >
  > * Par défaut, une expérience est programmée pour durer 30 jours à partir de sa création. C'est la période minimale recommandée pour qu'une expérience se déroule.
  > * Sélectionnez l'option **Poursuivre l'expérience indéfiniment** si vous souhaitez qu'elle continue jusqu'à ce que vous décidiez activement de l'arrêter.


</Accordion>

<div id="analyze-the-results" />

<Accordion title="Analysez les résultats">

Les premiers résultats de l'expérience sont disponibles sur le <Anchor target="_blank" href="/marketers/fr/docs/incrementality-for-remarketing-overview#tableau-de-bord-dincrémentalité">tableau de bord d'incrémentalité</Anchor> environ 48 heures après le lancement des campagnes connectées sur les réseaux publicitaires (mis à jour <Anchor target="_blank" href="/marketers/fr/docs/about-data-freshness-and-timezone-support#eod">quotidiennement</Anchor>). Vous pouvez voir des <Anchor target="_blank" href="/marketers/fr/docs/understand-incrementality-for-remarketing-experiment-alerts">alertes sur la page de l'expérience</Anchor> qui vous aident à identifier les problèmes pouvant compromettre la précision des résultats et suggèrent des actions à entreprendre pour les résoudre.

<Anchor target="_blank" href="/marketers/fr/docs/incrementality-for-remarketing-overview#rapports-de-données-brutes">Les rapports de données brutes d'incrémentalité</Anchor> sont disponibles via Data Locker.

</Accordion>

<div id="see-also" />

> 📄 **Voir aussi**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/audiences-guide">Guide des audiences</Anchor>

<div data-zendesk-anchors="overview=%C3%A0-propos-de-lexp%C3%A9rience h_01HARVCSMM80QXXXKJC8TX7CKC=%C3%A0-propos-de-lexp%C3%A9rience get-started=commencez h_01HARVCSMMYJVN6GJ3TB46P8AC=commencez set-up-the-experiment=configurer-lexp%C3%A9rience h_01HARVCSMMMAJ6VTYHZ2ZJ5HNS=configurer-lexp%C3%A9rience h_01HARVCSMM9P2HN5WA9C16PA5E=know-your-test-objectives h_01HARVCSMM2THH54JH58GM1K57=exemple h_01HARVCSMM77RV7NM9K7D5FJM5=create-the-target-audience-and-split-groups check-for-audience-expansion-features=v%C3%A9rifiez-les-fonctionnalit%C3%A9s-dextension-daudience- h_01HARVCSMMXNE4NCWSQZ9SHK1J=v%C3%A9rifiez-les-fonctionnalit%C3%A9s-dextension-daudience- h_01HARVCSMMH11D6RKDZQZ3WVZ6=launch-the-campaign-and-experiment 1-configure-campaigns-on-ad-networks=1-configurez-des-campagnes-sur-les-r%C3%A9seaux-publicitaires h_01HARVCSMMVXJWCT2BX3CVC3VT=1-configurez-des-campagnes-sur-les-r%C3%A9seaux-publicitaires 2-link-campaigns-to-experiment=2-assurez-vous-que-la-bonne-campagne-est-li%C3%A9e-%C3%A0-lexp%C3%A9rience h_01HARVCSMNAWNYEY83NC6Y5XV4=2-assurez-vous-que-la-bonne-campagne-est-li%C3%A9e-%C3%A0-lexp%C3%A9rience manually-create-an-experiment=cr%C3%A9er-manuellement-une-exp%C3%A9rience h_01HARVCSMNZVWK8Z36ER1HH10W=cr%C3%A9er-manuellement-une-exp%C3%A9rience h_01HARVCSMN5944HRD9N7YEKT3P=remarques h_01HARVCSMNS961WKFX280J3R2X=analyze-the-results h_01HE7RBMSE1RHVSJC7B7FZG8SJ=voir-aussi" />
