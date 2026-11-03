---
title: Guide de l'attribution post vue
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2016-04-20T07:38:24Z'
  edited_at: '2023-11-14T11:19:32Z'
  id: 210084473
  locale: fr
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/fr/articles/210084473
---
> **En bref :** un utilisateur qui regarde une publicité (impression) et qui installe ensuite l'application est attribué via l'attribution post-vue.

## Présentation

L'attribution post-vue mesure les installations, réattributions et réengagements des utilisateurs qui ont visionné une publicité mais sans cliquer dessus.

### Processus d'attribution post-vue

![Retargeting_-_View-through__1_.png](https://files.readme.io/86d32778a8a0966499a0c5c91c1b2d8aed6d5bb24214b1a32fd484779c105a98-4412917609489.png)

### Terminologie

* **Impression :** l'affichage d'une publicité, indépendamment du clic ou autre engagement produit par l'utilisateur.
* **Installation** : dans cet article, il s'agit des installations, réattributions et réengagements.
* **Attribution post-vue :** attribution des installations à une source média après visionnage d'une impression par l'utilisateur.

### Principes de l'attribution post-vue

* La <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-attribution-model#device-id-matching">correspondance des ID d'appareil</Anchor> et la <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-attribution-model#probabilistic-modeling">modélisation probabiliste</Anchor><Anchor target="_blank" href="/marketers/fr/docs/app-settings#viewthrough-attribution-via-probabilistic-modeling">(que vous devez activer</Anchor>) sont toutes deux prises en charge.
* Pris en charge par les partenaires figurant dans la [liste des partenaires d'attribution post-vue](/docs/measure-view-through-engagements#view-vta-partner-list).

Les impressions sont considérées comme attribution post-vue selon les critères suivants :

* L'impression a eu lieu pendant la fenêtre rétrospective post-vue (par défaut 24 heures).
* Si plusieurs impressions sont trouvées, la plus récente est prise en compte.
* Les clics sont prioritaires sur les impressions. Cela signifie que s'il y a des clics dans la fenêtre rétrospective post-vue, c'est le clic le plus récent qui l'emporte. L'impression la plus récente est attribuée en tant que contributeur (assistance).

### Fenêtre rétrospective post vue

* Pour les SRN, la fenêtre rétrospective d'attribution post vue est comprise entre 1 et 24 heures.Pour les SRN, la fenêtre rétrospective peut être plus longue.
* Pour paramétrer la fenêtre :
  * **Non-SRN :** définissez la durée avec les liens d'attribution d'impression en réglant le paramètre  `af_viewthrough_lookback.` Si le paramètre n'est pas défini, une fenêtre de 24 heures est utilisée par défaut.
  * **SRN**: la fenêtre est déterminée par le SRN. Nous recommandons de définir la même valeur que celle des SRN dans AppsFlyer.

### Mesures et reporting de l'attribution post-vue

* **Données agrégées :** les réseaux publicitaires communiquent à AppsFlyer les données d'impression agrégées via API, ou par impression. Notez que le comptage et la déclaration des impressions sont définis par chaque partenaire individuellement. Cf la manière dont les principaux partenaires intégrés définissent les impressions.Les mesures sont disponibles dans le tableau de bord général et proposées par différents outils de reporting. Les métriques disponibles sont :
  * Impressions : nombre d'impressions affichées sur une période donnée.
  * Post-vue : le nombre d'installations attribuées à l'aide de l'attribution post-vue.
* **Données brutes** :
  * Les données de niveau utilisateur (données brutes) des utilisateurs attribués en post-vue sont similaires à celles des utilisateurs attribués par clic. Cependant, certains partenaires limitent la disponibilité de ces données.
  * Des données d'impression (similaires aux données de clic) sont disponibles.
  * Le champ attributed\_touch\_type contient la valeur *impression*.

## Opérations post-vue

<div id="set-impression-links" />

<Accordion title="Définir des liens d'impression">

Les réseaux publicitaires envoient à AppsFlyer des liens d'impression avec des informations sur la campagne et autres données propres aux <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters">liens d'attribution de</Anchor> post-clic.

Les liens sont envoyés en temps réel, de sorte que si une installation suit une impression, elle est correctement attribuée.

Tenez compte des éléments suivants lorsque vous préparez les liens :

* L'URL de base est `http://impression.appsflyer.com`. Les protocoles HTTP et HTTPS sont pris en charge.
* Utilisez une demande GET.
* Incluez les ID d'appareil lorsqu'ils sont disponibles : IDFA, GAID, IDFV, etc.
* Incluez les paramètres de <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-attribution-model#paramètres-de-modélisation-probabiliste-pour-les-réseaux-publicitaires">modélisation probabiliste</Anchor>.
* Pour plus de sécurité, les valeurs de l'ID d'appareil peuvent être hachées avec SHA1. Le nom du paramètre doit commencer par "sha1\_" et être suivi du nom du paramètre et de la valeur hachée, ex. sha1\_idfa, sha1\_advertising\_id, sha1\_android\_id et sha1\_imei.

> 📄
>
>  Exemple
>
> ```http
> http://impression.appsflyer.com/{app-id}?c={campaign name}&pid={media source}
> &af_viewthrough_lookback=1d&af_prt={agency_name}&af_siteid={site id value}
> &af_sub1={free value}&idfa={idfa value}
> ```

</Accordion>

<div id="set-custom-impression-links" />

<Accordion title="Définir des liens d'impression personnalisés">

Les annonceurs utilisent les liens d'impression d'attribution avec leurs propres sources média personnalisées, par exemple les bannières de sites web.

Lorsque les annonceurs <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#créer-un-lien-onelink">créent des liens d'attribution personnalisés</Anchor>, ils obtiennent des liens d'impression complets, pouvant être activés chaque fois qu'un utilisateur interagit avec les publicités qu'ils possèdent.

Les liens d'impression personnalisés (créés via OneLink) peuvent également être utilisés pour attribuer les visiteurs d'un site web mobile. En savoir plus sur la <Anchor target="_blank" href="/marketers/fr/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#create-a-custom-impression-url">création d'URL d'impression personnalisées</Anchor>.

</Accordion>

<div id="turn-off-viewthroughattribution" />

<Accordion title="Désactiver l'attribution post-vue">

Par défaut, l'attribution post-vue est activée.Si AppsFlyer reçoit un lien d'attribution d'impression valide, l'impression rejoint le flux d'attribution.

Étant donné que l'attribution post vue est activée par défaut, il est important pour les annonceurs de signer un contrat avec le réseau pour définir si l'attribution post vue doit être activée ou non.

L'attribution post vue peut être désactivée pour chaque source média. Mais si des impressions sont réceptionnées et que l'attribution post vue est désactivée :

* Les mesures des impressions sont disponibles dans le tableau de bord.
* Le processus d'attribution ignore ces impressions.

**Pour désactiver l'attribution post-vue :**

1. Dans AppsFlyer, allez dans **Configuration** > **Intégrations actives**.
2. Sélectionnez le partenaire intégré.
3. Dans l'onglet *Intégration*, désenclenchez **Activer l'attribution post-vue**.
4. Cliquez sur **Enregistrer l'intégration**.

Avec les SRN, la désactivation de l'attribution post-vue dans AppsFlyer n'a pas les mêmes conséquences pour les réseaux.Veillez à définir les mêmes paramètres post-vue dans AppsFlyer et dans les réseaux afin d'éviter les erreurs de résultat.

</Accordion>

<div id="view-vta-partner-list" />

<Accordion title="Voir la liste des partenaires VTA">

La liste des partenaires d'ad network qui prennent en charge l'attribution post-vue est disponible dans le tableau de bord.

**Pour afficher la liste** :

1. Dans AppsFlyer, allez dans **Configuration** > **Intégrations** **actives**.
2. Sélectionnez **Toutes les intégrations**.
3. Dans le filtre **Capacités du partenaire**, sélectionnez **post-vue**.  
   La liste des partenaires s'affiche.

</Accordion>

<div data-zendesk-anchors="overview=pr%C3%A9sentation h_01HEMT7T1TB9W7ZBRPQW29SRPF=pr%C3%A9sentation viewthrough-attribution-flow=processus-dattribution-post-vue h_01HEMT7T1T6ZK4ZH7DKV3162J1=processus-dattribution-post-vue terminology=terminologie h_01HEMT7T1TY46QXBDS6MBF1DZ5=terminologie viewthrough-attribution-principles=principes-de-lattribution-post-vue h_01HEMT7T1THD8TVKRRJ168HKY2=principes-de-lattribution-post-vue viewthrough-lookback-window=fen%C3%AAtre-r%C3%A9trospective-post-vue h_01HEMT7T1TWHN2AB3Q5X36TKKB=fen%C3%AAtre-r%C3%A9trospective-post-vue viewthrough-attribution-reporting-and-metrics=mesures-et-reporting-de-lattribution-post-vue h_01HEMT7T1TQNKM5GABA7VY6KR1=mesures-et-reporting-de-lattribution-post-vue viewthrough-operations=op%C3%A9rations-post-vue h_01HEMT7T1T13JC75ZYY01N8PS6=op%C3%A9rations-post-vue h_01HEMT7T1TQ3YNQ2Y0CCGPXWDX=set-impression-links h_01HEMT7T1T75MBS64JE837CJ0E=set-custom-impression-links h_01HEMT7T1T253G1CZNS9KVDFCP=turn-off-viewthroughattribution h_01HEMT7T1T5MQHC3F5EHSGMYQF=view-vta-partner-list" />
