---
title: Guide des tests A/B pour AppsFlyer
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
  created_at: '2019-05-07T09:17:43Z'
  edited_at: '2024-10-23T13:11:58Z'
  id: 360001523657
  locale: fr
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/fr/articles/360001523657
---
> **En bref :** Utilisez AppsFlyer pour effectuer des tests A/B sur les sources média, les campagnes, les créations, le ciblage et l'emplacement des publicités.

![AB_TESTING.jpg](https://files.readme.io/259277a96d044e85cbac39de0f636bad531706e53e2ad5a21475277ea9dbd3a6-360002822018.jpg)

## Qu'est-ce que le test A/B ?

Le test A/B est une méthode utilisée par les marketers pour tester différents éléments de leurs publicités et de leurs campagnes. Chaque publicité contient des éléments (ciblage, visuels, textes) qui peuvent affecter les taux de conversion des utilisateurs potentiels. Trouver les variantes les plus performantes de vos éléments publicitaires peut avoir un impact significatif sur le résultat de vos efforts de marketing mobile.

Cet article explique **comment les annonceurs peuvent effectuer des tests A/B à l'aide d'AppsFlyer, afin de trouver les éléments publicitaires les plus performants**.

## Comment tester les campagnes mobiles A/B

Pour tester un élément par A/B, divisez votre trafic mobile à 50/50 entre deux sources présentant une offre identique. Ensuite, créez deux variantes de l'élément que vous souhaitez tester. Une fois que le trafic est suffisant, vous pouvez comparer les résultats de la version existante (contrôle) à ceux de la nouvelle version (variation).

Les étapes suivantes s'appliquent à un test A/B que vous réalisez avec AppsFlyer.

**Configuration** :

1. Sélectionnez l'élément à tester.  
   Dans cet article, nous expliquons ce qu'est le test A/B pour les [créations](/docs/create-a-b-tests#tests-ab-des-créations-et-du-ciblage), les emplacements publicitaires, les sources média et les campagnes.
2. Créez deux campagnes (ou publicités) identiques, puis faites varier un seul élément de la publicité. Par exemple, le texte du bouton d'appel à l'action.
   * Pour tester l'impact de la variation sur les **taux de conversion des installations**, répartissez le trafic de manière égale entre les deux campagnes.   
     Si des données complètes sur les impressions sont disponibles pour les deux sources, divisez les installations par les impressions pour calculer les taux de conversion des installations.
   * Pour tester l'impact de la variation sur la qualité des utilisateurs, **après l'installation**, vous pouvez envoyer différents volumes de trafic aux deux campagnes.
3. Attirez suffisamment de trafic vers chaque campagne pour obtenir une signification statistique, c'est-à-dire au moins 50 installations par campagne. Utilisez le <Anchor target="_blank" href="https://neilpatel.com/ab-testing-calculator/">calculateur de l'importance des tests A/B.</Anchor>

**Analyse :**

1. Utilisez le tableau de bord et les données d'AppsFlyer pour comparer les performances des principaux indicateurs clés de performance entre les deux campagnes.
2. Sélectionnez la variante gagnante et utilisez-la dans vos campagnes en direct.

## Tests A/B des créations et du ciblage

Les créations contiennent de nombreux éléments ayant un impact variable sur les taux de conversion des utilisateurs, notamment le texte, les images, les couleurs, les polices, les boutons, etc. Les paramètres de ciblage, tels que le pays, l'âge ou le sexe, peuvent également avoir un impact majeur sur les taux de conversion. Pour iOS 15+, vous pouvez également avoir jusqu'à 35 pages de produits personnalisées. **Des tests A/B sur ces éléments peuvent vous aider à déterminer les facteurs qui ont le plus d'impact sur l'amélioration des taux de conversion des utilisateurs**.

Nous expliquons ci-dessous deux méthodes de tests A/B :

* Une seule source média
* Sources média multiples

| Méthode | Avantages | Inconvénients |
| --- | --- | --- |
| Tests A/B avec une seule source média | <ul><li>Configuration rapide</li><li>Taux de conversion de l'installation facile à tester</li></ul> | <ul><li>Les résultats peuvent ne s'appliquer qu'aux utilisateurs de la source média en question.</li><li>Le test peut prendre plus de temps</li></ul> |
| Tests A/B sur plusieurs sources média | <ul><li>Des résultats rapides</li><li>Les résultats s'appliquent aux utilisateurs de toutes les sources média</li></ul> | <ul><li>Nécessité de mettre à jour les liens d'attribution à plusieurs endroits</li></ul> |

<div id="method-1-ab-testing-with-a-single-media-source" />

<Accordion title="Méthode 1 : Tests A/B avec une seule source média">

**Configuration** :

1. Sélectionnez une source média fiable ayant un trafic suffisant.
2. Créez deux campagnes ou <Anchor target="_blank" href="/marketers/fr/docs/smart-banners-mobile-web-to-app-for-marketers#3-banner-setup">Smart Banners</Anchor> dans AppsFlyer en utilisant l'une des méthodes suivantes :
   * Variez la campagne qui est le nom qui est le paramètre **c** dans le lien d'attribution.
   * Vous pouvez également créer deux ensembles de publicités ("**af\_adset=")** au sein d'une campagne ou des publicités individuelles ("**af\_ad=**") au sein d'un adset. **Remarque** : dans Smart Banners, vous pouvez également <Anchor target="_blank" href="/marketers/fr/docs/smart-banners-mobile-web-to-app-for-marketers#ab-testing-banner-performance">effectuer des tests A/B en définissant des paramètres différents pour chaque bannière</Anchor> au sein d'un même groupe de bannières.
   * Pour iOS 15+, vous pouvez également tester l'efficacité de différentes pages de produits personnalisées, en envoyant différentes URL OneLink à différentes pages de produits. <Anchor target="_blank" href="/marketers/fr/docs/redirect-users-to-custom-app-store-product-pages">En savoir plus</Anchor>
3. Utilisez la même création dans les deux campagnes, à l'exception de la variante testée.
4. Envoyez le même volume de trafic aux deux campagnes.

**Analyse :**

* Comparez les indicateurs clés de performance (par exemple, le taux de conversion des installations, le retour sur investissement, l'ARPU, le taux d'utilisateurs fidèles) des campagnes dans la page du tableau de bord "Vue d'ensemble".

</Accordion>

<div id="method-2-ab-testing-across-multiple-media-sources" />

<Accordion title="Méthode 2 : Tests A/B sur plusieurs sources média">

**Configuration** :

1. Sélectionnez un paramètre d'abonné pour conserver la valeur de variation.  
   Par exemple, pour tester 2 variantes de texte CTA, vous pouvez utiliser af\_sub1="install now" ou af\_sub1="please install". Pour en savoir plus sur les paramètres des abonnés et pour un exemple de test créatif <Anchor target="_blank" href="/marketers/fr/docs/about-link-structure-and-parameters#what-are-subscriber-parameters-good-for">, cliquez ici.</Anchor>
2. Ajoutez le paramètre d'abonné avec la valeur correspondante à chaque lien d'attribution en direct.
3. Il est recommandé d'utiliser les mêmes créations dans toutes les campagnes, à l'exception de la variante testée.

**Analyse :**

1. Téléchargez l'installation ou les rapports de données brutes des événements in-app. Utilisez la colonne des paramètres de l'abonné que vous avez sélectionnée pour filtrer et trier vos données.
2. Comparez les performances des créatifs avec l'une ou l'autre des deux valeurs stockées.

</Accordion>

## Tests A/B de l'emplacement des publicités pour le web mobile

![ad_placement.png](https://files.readme.io/6d64eed1a7a16c6daae9c93429d5bd46625dc4de12728e42b49a91ae69765f24-360002747977.png)

L'emplacement des bannières de vos applications sur les sites web mobiles peut avoir un impact significatif sur les taux de conversion des utilisateurs. Dans la plupart des cas, les annonceurs utilisent leurs propres sites web mobiles pour convertir les visiteurs en utilisateurs mobiles.

Avec la fonction AppsFlyer <Anchor target="_blank" href="/marketers/fr/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banners</Anchor>, vous pouvez mettre en place des bannières web mobiles rapidement et facilement. Cette fonctionnalité vous permet également d'effectuer facilement des tests A/B afin de **déterminer le meilleur emplacement pour convertir les visiteurs du site web en utilisateurs mobiles**.

**Configuration** :

1. Mettez en place des <Anchor target="_blank" href="/marketers/fr/docs/smart-banners-mobile-web-to-app-for-marketers">bannières intelligentes</Anchor> sur votre site web mobile.
2. Pour chaque nouveau visiteur, déterminez si la bannière doit être affichée en haut ou en bas de la page. Veillez à répartir le trafic 50/50 entre les deux.  
   Conseil du développeur - Une méthode simple pour diviser le trafic de votre site web consiste à utiliser un compteur de visiteurs, puis à vérifier si la valeur du compteur est impaire (option A) ou paire (option B) pour chaque nouveau visiteur.
3. Définissez l'emplacement de la bannière et le lien d'attribution en fonction de l'emplacement déterminé à l'aide de <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#showbanner">l'API ShowBanner</Anchor> du SDK Smart Banners.  
   Exemple :

   ```javascript
   showBanner({ bannerContainerQuery: "#document.body", additionalParams:{ af_sub5: "top"}})
   ```

**Analyse :**

1. Téléchargez les rapports de données brutes pour les installations ou les événements in-app. Utilisez la colonne du paramètre d'abonné sélectionné (par exemple af\_sub5) pour filtrer et trier vos données.
2. Comparez les performances des deux emplacements publicitaires, c'est-à-dire l'emplacement qui a obtenu le plus d'installations ou d'événements post-installation.

## Test A/B des sources média

AppsFlyer a été conçu pour aider les annonceurs à identifier les sources média les plus performantes (et les moins performantes) pour leurs applications. Toutefois, **si les annonceurs ne comparent pas correctement les sources média, ils risquent de tirer des conclusions erronées quant à la qualité du trafic.**

**Configuration :**

1. Créez une seule création publicitaire pour les DEUX sources média.
2. Définissez une publicité pour chaque source de média, avec les mêmes paramètres exacts de ciblage de l'audience.
3. Vous pouvez envoyer des volumes de trafic différents aux deux sources média.

**Analyse :**

1. Si les publicités testées sont les seules diffusées sur les deux sources média, utilisez le tableau de bord et les données d'AppsFlyer pour comparer facilement vos indicateurs clés de performance entre les deux sources.  
     
   Dans le cas contraire :
2. Accédez au rapport de rétention, au <Anchor target="_blank" href="/marketers/fr/docs/cohort-and-retention-dashboard">rapport de cohorte</Anchor>, à <Anchor target="_blank" href="/marketers/fr/docs/master-api-user-acquisition-metrics-via-api">l'API principale</Anchor> ou au <Anchor target="_blank" href="/marketers/fr/docs/pivot-table-user-metrics">tableau croisé dynamique</Anchor> d'AppsFlyer.
3. Groupe par source média -> Campagne -> Adset -> Publicité.
4. Comparez les indicateurs clés de performance pour identifier la source média la plus performante.

> 📄 **Exemple**
>
> [![](https://files.readme.io/bf907e0e67d24764a68579ba6fc42d0d49befbc7ffc7645b91ae1aa8f8b97c12-360002829938.png)](https://files.readme.io/bf907e0e67d24764a68579ba6fc42d0d49befbc7ffc7645b91ae1aa8f8b97c12-360002829938.png)
>
> * 1 et 2 sont des publicités différentes sur la même source média. Comparez un indicateur de performance unique, par exemple le taux de fidélisation au quatrième jour, pour tester les créations, le ciblage ou l'emplacement des publicités.
> * 2 et 3 sont des publicités diffusées sur des supports différents. Si les créations et le ciblage des publicités sont identiques, la comparaison d'un seul KPI permet d'effectuer des tests A/B sur la source média.

### Utilisation de la division des audiences pour faciliter les tests A/B des sources média

Si vous définissez les mêmes paramètres de ciblage pour chaque source média, le test inclut les capacités de ciblage des réseaux. Lors d'un test A/B, il est préférable de tester une seule variation à chaque fois. Par conséquent, il est conseillé d'éliminer les différences de capacités de ciblage lors des tests A/B portant sur d'autres facteurs de performance des réseaux.

Pour ce faire, nous recommandons de diviser une audience de manière aléatoire et de cibler les deux audiences avec la même création, sur chaque réseau testé. AppsFlyer offre une **méthode simple pour définir, diviser et distribuer automatiquement les audiences entre les différentes sources média.** Pour en savoir plus <Anchor target="_blank" href="/marketers/fr/docs/audiences-guide#partage-daudience-et-test-dincrémentalité">, cliquez ici</Anchor>.

<div data-zendesk-anchors="what-is-ab-testing=quest-ce-que-le-test-ab- h_01HN5CNKKBHV52ENXJXCBV2CES=quest-ce-que-le-test-ab- how-to-ab-test-mobile-campaigns=comment-tester-les-campagnes-mobiles-ab h_01HN5CNKKC02NKW4330QB6E01T=comment-tester-les-campagnes-mobiles-ab ab-testing-creatives-and-targeting=tests-ab-des-cr%C3%A9ations-et-du-ciblage h_01HN5CNKKCJPZSEEF1RAHC0HXD=tests-ab-des-cr%C3%A9ations-et-du-ciblage h_01HN5CNKKCMVE9YH379RP1S19W=method-1-ab-testing-with-a-single-media-source h_01HN5CNKKC53RTV61K08T9AVRA=method-2-ab-testing-across-multiple-media-sources ab-testing-ad-placement-on-mobile-web=tests-ab-de-lemplacement-des-publicit%C3%A9s-pour-le-web-mobile h_01HN5CNKKCVPSSZZTJ8QGJHY1B=tests-ab-de-lemplacement-des-publicit%C3%A9s-pour-le-web-mobile ab-testing-media-sources=test-ab-des-sources-m%C3%A9dia h_01HN5CNKKC03ZAFCQZ0KJ0RHCE=test-ab-des-sources-m%C3%A9dia h_01HN5CNKKC4M6YMPHTQCFHFDMD=exemple using-audiences-split-for-easy-ab-testing-of-media-sources=utilisation-de-la-division-des-audiences-pour-faciliter-les-tests-ab-des-sources-m%C3%A9dia h_01HN5CNKKC551X3HQFNKHW1JBY=utilisation-de-la-division-des-audiences-pour-faciliter-les-tests-ab-des-sources-m%C3%A9dia" />
