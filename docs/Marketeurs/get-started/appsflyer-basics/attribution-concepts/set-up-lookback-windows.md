---
title: Explication des fenêtres rétrospectives
metadata:
  keywords:
    - Advertisers
    - look back
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2016-03-07T09:27:55Z'
  edited_at: '2023-07-31T12:06:32Z'
  id: 208338403
  locale: fr
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/fr/articles/208338403
---
> **En bref :** personnalisez les fenêtres rétrospectives post-clic et post-vue, en fonction de vos accords avec les sources média.

<div id="lookback-windows" />

## Fenêtre d'attribution

La fenêtre d'attribution configurable vous permet de personnaliser la période d'attribution en fonction de votre accord avec les sources média.

En définissant des fenêtres d'attribution par source média, AppsFlyer attribue les informations conformément aux conditions prévues.

**Types de fenêtres d'attribution** :

* **Fenêtre d'attribution post-clic** : période maximale après un clic sur une publicité pendant laquelle une installation peut être attribuée à la publicité. Les installations qui ont lieu après la fenêtre d'attribution sont considérées comme organiques.
* **Fenêtre d'attribution post-vue**: période maximale après la visualisation d'une publicité pendant laquelle une installation peut être attribuée à la publicité. Les installations qui ont lieu après la fenêtre d'attribution sont considérées comme organiques.

<div id="configurable-lookback-windows-per-attribution-type" />

#### Fenêtres d'attribution configurables par type d'attribution

<table><thead><tr><th rowspan="2"><p><strong>Type d'attribution</strong></p></th><th rowspan="2"><p><strong>Méthode d'attribution</strong></p></th><th colspan="2"><p><strong>Fenêtre rétrospective des clics</strong> </p></th></tr><tr><th><p><strong>Plage</strong></p></th><th><p><strong><strong>Par défaut</strong></strong></p></th></tr></thead><tbody><tr><td rowspan="2"><p>Post-clic</p><p>(Toutes les sources média)</p></td><td><p>Référent, correspondance des identifiants</p></td><td><p>1-30 jours OU<br/>1-23 heures</p></td><td><p>7 jours</p></td></tr><tr><td><p>Modélisation probabiliste</p></td><td><p><a href="./appsflyer-attribution-model#probabilistic-modeling" target="_blank">Adaptive</a></p></td><td><p>Jusqu'à 24 heures</p></td></tr><tr><td rowspan="3"><p>Fraude de visibilité</p><p>(Sélectionnez les <a href="./measure-view-through-engagements#view-vta-partner-list" target="_blank">sources média</a>)</p></td><td><p>ID Matching</p></td><td><p>1-24 heures</p><p>[Jusqu'au 15 décembre 2021, la limite supérieure était de 7 jours].</p></td><td><p>24 heures</p></td></tr><tr><td><p>Modélisation probabiliste</p></td><td><p><a href="./appsflyer-attribution-model#probabilistic-modeling" target="_blank">Adaptive</a></p></td><td><p>Jusqu'à 24 heures</p></td></tr><tr><td><p>Modélisation probabiliste (multiplateforme)</p></td><td><p>1-72 heures</p></td><td><p>24 heures</p></td></tr></tbody></table>

<div id="probabilistic-modeling-lookback-window" />

### Fenêtre de recul de la modélisation probabiliste

La fenêtre d'attribution de la modélisation probabiliste, utilisée pour maintenir la précision de l'attribution, présente les caractéristiques suivantes :

* S'applique à la fois aux clics et aux impressions
* A une durée d'adaptation allant jusqu'à 24 heures
* Ne tient pas compte des paramètres de durée de la fenêtre envoyés sur le lien d'attribution
* A une durée plus courte que les fenêtres utilisées par les modèles déterministes

Pour en savoir plus, consultez le site <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-attribution-model#probabilistic-modeling">Méthode de modélisation probabiliste AppsFlyer</Anchor>.

<div id="lookback-window-setup" />

## Configuration de la fenêtre d'attribution

Nous présentons ci-après le processus de configuration de la fenêtre d'attribution pour les SRN et les liens d'attribution.

<Tabs>
<Tab title="Fenêtre d'attribution du SRN">

<div id="h_01JKWVQB6TTA24VAZ9WVJMGY4X" />

<div id="non-srn-attribution-lookback-window-for-engaged-click-through-and-engaged-view-through" />

<div id="non-srn-attribution-lookback-window-for-click-through-and-view-through" />

<div id="important" />

<div id="attribution-lookback-window-for-srns" />

### Attribution de la fenêtre d'attribution pour les SRN

> 🚧 **Important !**
>
> Chaque SRN a sa propre fenêtre d'attribution. Afin de minimiser les divergences, nous vous recommandons de faire correspondre la valeur de la fenêtre d'attribution dans AppsFlyer avec la valeur du SRN. La modifier pourrait entraîner des divergences. Pour en savoir plus, consultez [l'exemple de divergence SRN](#scénarios-et-exemples).

1. Depuis votre tableau de bord AppsFlyer, allez sur **Intégrations actives.**
2. Recherchez et sélectionnez le SRN - voir la <Anchor target="_blank" href="/marketers/fr/docs/self-reporting-networks-srns#srn-intégrés-à-appsflyer">liste des SRN pris en charge</Anchor>.
3. L'attribution post-vue est activée par défaut.
4. Dans l'onglet **Integration**, descendez jusqu'à la configuration **Attribution post-clic** et **Attribution post-vue**.
5. Utilisez les curseurs pour définir la fenêtre d'attribution

Voir ci-dessous chaque fenêtre d'attribution SRN :

| SRN | Fenêtre d'attribution post-clic par défaut (jours) | Fenêtre d'observation post-vue par défaut (heures) |
| --- | --- | --- |
| Google | 30 | 24 |
| Meta Ads | 7 | 24 |
| Snapchat | 28 | 24 |
| Twitter | 14 | 24 |
| Apple Search Ads | 30 | S/O |
| Oath (YahooGemini) | 7 | 24 |

</Tab>

<Tab title="Fenêtre d'attribution des liens d'attribution">

<div id="attribution-lookback-window-with-attribution-links" />

<div id="tip" />

### Fenêtre d'attribution rétrospective avec liens d'attribution

1. Depuis votre tableau de bord AppsFlyer, allez sur **Intégrations actives.**
2. Rechercher et sélectionner un partenaire.
3. L'attribution post-vue est activée par défaut.
4. Cliquez sur l'onglet de **lien d'attribution**.
5. Configurez le temps en jours ou en heures.
6. Utilisez les curseurs dans **Attribution post-clic** (paramètre `af_click_lookback`) et **Attribution post-vue** (paramètre `af_viewthrough_lookback`) pour définir la fenêtre d'attribution.  
   La durée sélectionnée est automatiquement reportée dans le lien d'attribution.
7. Sélectionnez les paramètres correspondant à la campagne, c'est-à-dire le nom de la campagne, l'adset, etc.
8. Copiez et enregistrez le lien - il s'agit du lien que vous fournissez au réseau publicitaire.

> 👍
>
> * Vous voulez des conseils et des astuces pour configurer la fenêtre d'attribution ? Suivez cette <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7768/play/18612/attribution-102-tips-and-tricks">brève formation</Anchor> sur le portail d'apprentissage AppsFlyer.
> * [Cliquez ici](/docs/set-up-lookback-windows#lookback-in-hours-for-flash-campaigns) pour savoir quand vous devez utiliser les heures pour les fenêtres d'attribution.

<div id="lookback-window-in-onelink" />

### Fenêtre d'attribution dans OneLink™

Vous pouvez également définir la fenêtre d'attribution dans OneLink.

1. <Anchor target="_blank" href="/marketers/fr/docs/create-a-onelink-template">Configuration d'un OneLink</Anchor>
2. <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#créer-un-lien-onelink">Créer un lien d'attribution personnalisé</Anchor>
3. Sous **Avancé**, activez **Personnaliser la fenêtre d'attribution** et définissez la fenêtre.

</Tab>
</Tabs>

<div id="distribution-of-first-app-launches" />

## Distribution des premiers lancements d'applications

Le graphique ci-dessous montre la distribution des premiers lancements d'applications à partir du jour de l'engagement.

<Image align="center" alt="" src="https://files.readme.io/8fdc8b23ba9a1b78bdea7bacad99d6ed5e59d57de32f395cb2fd9e5451483962-360001666918.png" />

Le graphique peut vous donner une meilleure idée du nombre d'utilisateurs qui installent l'application en fonction de la fenêtre d'attribution.

La majorité des utilisateurs, un peu plus de 97 %, qui lancent l'application le font dans les sept jours suivant l'affichage de la publicité. Les 2 % restants le font entre le 7ème jour et la fin de la fenêtre d'attribution (30ème jour).

Près de 62 % des utilisateurs qui lancent l'application le font dans les 15 minutes qui suivent la diffusion de la publicité. 72 % des utilisateurs le font dans la première heure.

<div id="tip-1" />

<div id="scenarios-and-examples" />

## Scénarios et exemples

Vous trouverez ci-dessous une liste de scénarios possibles et d'exemples d'utilisation de la fenêtre d'attribution.

<div id="srn-discrepancy-srn-lookback-longer-than-appsflyer" />

<Accordion title="Divergence SRN : la période de veille SRN est plus longue que celle d'AppsFlyer">

Vous mettez en place une campagne sur Twitter et configurez la fenêtre d'attribution post-clic à 7 jours. Twitter, quant à lui, dispose d'une fenêtre d'attribution par défaut de 14 jours.

<Image align="center" alt="srn-discrepancy-srn-lookback-larger-than-appsflyer.png" src="https://files.readme.io/a0a60df2c1b142c9b2871c2083168ef5d88922001f1e5ab6a95c7ffbdcc178a5-360001586637.png" />

</Accordion>

<div id="srn-lookback-smaller-than-appsflyer" />

<Accordion title="Fenêtre d'attribution SRN inférieure à celle d'AppsFlyer">

Vous mettez en place une campagne sur Twitter et configurez la fenêtre d'attribution post-clic à 28 jours. Twitter, quant à lui, dispose d'une fenêtre d'attribution par défaut de 14 jours.

<Image align="center" alt="srn-lookback-smaller-than-appsflyer.png" src="https://files.readme.io/9111035d903bfb35be2ab4bff27c16e527b401b12225b71316a7e36ed68ffb0c-360001586697.png" />

</Accordion>

<div id="attribution-link-without-a-lookback-window-parameter" />

<Accordion title="Lien d'attribution sans paramètre de fenêtre d'attribution">

Il est possible d'avoir un lien d'attribution qui n'a pas de paramètre de fenêtre d'attribution. Dans ce cas, AppsFlyer propose par défaut une fenêtre d'attribution de 7 jours pour les clics et une fenêtre d'attribution de 1 jour pour les impressions.

</Accordion>

<div id="lookback-in-hours-for-flash-campaigns" />

<Accordion title="Attribution en heures pour les campagnes flash">

Les campagnes flash sont des campagnes dont l'objectif est d'inciter les utilisateurs à installer l'application le plus rapidement possible dans une courte fenêtre de promotion.

Une application de commerce électronique appelée SuperShopping lance une campagne flash. Dans le cadre de cette campagne, l'utilisateur qui installe l'application dans l'heure qui suit bénéficie d'offres spéciales.

Johnny, le responsable marketing de SuperShopping, crée un lien d'attribution et fixe la fenêtre d'attribution à 1 heure. Johnny sait ainsi combien d'utilisateurs réagissent à la campagne.

De plus, le développeur de l'application peut identifier les utilisateurs qui proviennent de cette campagne flash et proposer les promotions annoncées par la campagne.

</Accordion>

> 👍 **Astuce**
>
> Vous voulez des conseils et des astuces pour la fenêtre d'attribution ? Suivez cette <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7768/play/18612/attribution-102-tips-and-tricks">brève formation</Anchor> sur le portail d'apprentissage AppsFlyer.

<div data-zendesk-anchors="lookback-windows=fen%C3%AAtre-dattribution configurable-lookback-windows-per-attribution-type=fen%C3%AAtres-dattribution-configurables-par-type-dattribution probabilistic-modeling-lookback-window=fen%C3%AAtre-de-recul-de-la-mod%C3%A9lisation-probabiliste lookback-window-setup=configuration-de-la-fen%C3%AAtre-dattribution attribution-lookback-window-for-srns=attribution-de-la-fen%C3%AAtre-dattribution-pour-les-srn lookback-window-in-onelink%E2%84%A2=lookback-window-in-onelink distribution-of-first-app-launches=distribution-des-premiers-lancements-dapplications scenarios-and-examples=sc%C3%A9narios-et-exemples" />
