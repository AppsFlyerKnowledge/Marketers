---
title: 'ROI360 : données sur les coûts et les revenus'
metadata:
  keywords:
    - cost
    - Advertisers
    - Premium
    - Marketers
    - revenue
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2022-11-10T13:52:03Z'
  edited_at: '2023-04-02T14:40:10Z'
  id: 10515748254609
  locale: fr
  section: Overview
  section_id: 15173289016593
  url: https://support.appsflyer.com/hc/fr/articles/10515748254609
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **En bref**  : accédez aux données sur les coûts et revenus pour mieux déchiffrer votre ROI total et votre ROAS.

<Image align="center" alt="M_emptyState.png" src="https://files.readme.io/5eec5be77bf0b72afdd95b1957642cc67ba509000bc756ac68d87da5e96ed08e-11832563913489.png" />

<div id="overview" />

## Présentation

ROI360 est une suite d'outils de reporting des coûts et revenus qui qui vous permet d'obtenir rapidement des données d'une grande précision.

En comparant les informations sur les coûts et les revenus, vous pouvez tout connaître de votre retour sur investissement publicitaire (ROAS), et votre retour sur investissement (ROI).

<div id="cost-tools" />

### Outils de coûts

Anciennement connus sous le nom de Xpend, les outils de coûts ROI360 permettent d'agréger et rapporter et les données de coûts. L'ensemble des outils de coûts et ses différentes fonctionnalités sont présentées dans le tableau suivant. Cliquez sur les liens pour en savoir plus sur chacune des fonctionnalités.

<table><thead><tr><th>Outil</th><th>Description</th></tr></thead><tbody><tr><td><a href="./roi360-cost-aggregation-overview" target="_blank">Coût attribué</a></td><td><p><span>Données sur les coûts liés à l'attribution, aux clics et aux impressions au niveau le plus précis possible.</span></p><p><span>Inclut l'accès à plus de 80 intégrations d'API qui facilite votre connexion aux réseaux publicitaires mondiaux et locaux.</span></p></td></tr><tr><td><a href="./import-cost-data" target="_blank">Ingestion des fichiers</a></td><td><p><span>Ingestion des dépenses publicitaires pour enregistrer les données de coûts qui n'ont pas été transmises par l'API.</span></p></td></tr><tr><td><a href="./incorporate-agency-fees-into-campaign-costs" target="_blank">Frais d'agence</a></td><td><p><span>Les frais d'agence sont inclus dans votre coût.</span></p></td></tr><tr><td><a href="./set-up-and-use-roi360-cost-etl-reports" target="_blank">ETL des coûts\*</a></td><td><span>Fournit des données sur les coûts des campagnes, celles-ci sont actualisées 4 fois par jour, transmises à votre compartiment AWS S3 ou GCS, et sont prêtes à être importées dans les systèmes BI des annonceurs.</span></td></tr><tr><td colspan="2"><span>\* Disponible avec le pack avancé ROI360</span></td></tr></tbody></table>

**Remarque** : vous pouvez également agréger les <Anchor target="_blank" href="/marketers/fr/docs/view-aggregated-cost-data-for-attribution-links">données de coûts par clic</Anchor> sans passer par ROI360. Toutefois, cette méthode s'applique au modèle de coût CPI, mais pas aux autres modèles de type CPA, CPC et CPM.

<div id="revenue-tools" />

### Outils de revenus

Les outils de revenus ROI360 permettent d'agréger et rapporter les données de revenus en incluant les achats in-app, les abonnements et les revenus publicitaires. Les Taxes et commissions des app stores sont également compris dans les chiffres de revenus. La suite complète d'outils de revenus et ses différentes fonctionnalités sont présentées dans le tableau suivant. Cliquez sur les liens pour en savoir plus sur chacune des fonctionnalités.

<table><thead><tr><th>Outil</th><th>Description</th></tr></thead><tbody><tr><td>Achats in-app</td><td><p><span>Reporting automatique des achats in-app validés, qui incluent les données sur les transactions après vente telles que les remboursements ou annulations.</span></p></td></tr><tr><td>Revenus d'abonnement</td><td><p><span>Rapports automatiques sur les abonnements, qui incluent les modifications, les annulations et le partage familial.</span></p></td></tr><tr><td><a href="./roi360-guide-ad-revenue-attribution" target="_blank">Revenus publicitaires</a></td><td><p>Accès à plus de 20 partenaires de revenus publicitaires connectés via API ou SDK, ce qui autorise une plus grande précision et une meilleure actualisation des données.</p></td></tr><tr><td>[Prochainement] Revenus ETL\*</td><td><span>Transmet des données sur les revenus à votre compartiment AWS S3 ou GCS, celles-ci sont prêtes à être importées dans les systèmes BI des annonceurs.</span></td></tr><tr><td colspan="2"><span>\* Disponible avec le pack avancé ROI360</span></td></tr></tbody></table>

**Remarque** : il existe également des outils basiques de mesure des revenus qui ne sont pas compris dans ROI360. Contrairement aux outils inclus dans ROI360, ces outils vont demander à vos développeurs une configuration importante :

* <Anchor target="_blank" href="/marketers/fr/docs/legacy-receipt-validation-for-in-app-purchases">Validation des reçus d'achats in-app</Anchor>
* Mesure des revenus d'abonnement
* <Anchor target="_blank" href="/marketers/fr/docs/roi360-revenue-attribution-overview">Enregistrement des revenus via les événements in-app personnalisés</Anchor>

<div data-zendesk-anchors="overview=pr%C3%A9sentation cost-tools=outils-de-co%C3%BBts revenue-tools=outils-de-revenus" />
