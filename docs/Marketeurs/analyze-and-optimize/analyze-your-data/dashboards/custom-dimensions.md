---
title: Dimensions personnalisées
metadata:
  keywords:
    - dashboard
    - Marketers
    - Marketing Analytics
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-nohar-avigal
    - Marketers
    - Marketing Analytics
  created_at: '2023-06-06T09:28:20Z'
  edited_at: '2023-12-11T11:40:37Z'
  id: 15920604187921
  locale: fr
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/fr/articles/15920604187921
---
> **En bref :** définissez vos propres dimensions et utilisez-les pour regrouper les données dans le tableau de bord général.

<Embed title="Dimensions personnalisées" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/tvcdofnwjo" providerUrl="https://fast.wistia.com" />

<div id="overview" />

## Présentation

Les dimensions personnalisées vous permettent d'utiliser les dimensions existantes pour créer vos propres dimensions afin d'analyser les données selon vos objectifs commerciaux.Ces dimensions peuvent être utilisées dans tous les widgets du tableau de bord général pour regrouper les données, vous permettre d'obtenir des informations plus précises et prendre des décisions qui servent vos objectifs commerciaux selon ces données.

Les dimensions personnalisées que vous créez se trouvent au niveau du compte, ce qui signifie que différentes apps issues d'un même compte AppsFlyer peuvent utiliser les mêmes dimensions personnalisées.

<div id="benefits" />

### Avantages

* Des informations sur mesure : permet de définir et collecter des données liées à votre entreprise. En accédant à des informations qui dépassent les dimensions standard, vous pouvez obtenir des analyses plus approfondies et une vue plus complète de vos données.
* Analyse segmentée : permet de regrouper et analyser vos données selon des attributs ou caractéristiques précis afin d'obtenir une meilleure vision du comportement des utilisateurs, des segments de clientèle ou des performances de produit.
* Rapports améliorés : permet de créer des tableaux de bord et des rapports personnalisés parfaitement adaptés à vos besoins.
* Prise de décision éclairée : en captant des dimensions personnalisées qui suivent les objectifs de votre entreprise, vous pouvez prendre des décisions encore plus éclairées.Les dimensions personnalisées permettent d'évaluer l'impact des différentes variables et différents facteurs sur vos indicateurs clés de performance (KPI), car elles vous aident à déchiffrer les tendances, les modèles et à anticiper ce qui peut être optimisé.

<div id="example-use-cases" />

### Exemple de cas d'utilisation

| Exemple de cas d'utilisation | Description |
| --- | --- |
| Intention de la campagne | <ul><li>Concerne les noms de vos campagnes.</li><li>Choisissez des noms de valeur pour différencier vos objectifs de campagne.Par exemple, une campagne de branding peut être étiquetée "brd" et une campagne d'acquisition d'utilisateurs peut être étiquetée "nouveau" ou "ua."</li><li>Incluez les noms des valeurs dans les noms de vos campagnes.Exemple : "US\_Facebook\_BRD" ou "UK\_Google\_nouveau".</li><li>AppsFlyer analyse le nom de la campagne et regroupe les données en fonction de vos étiquettes.</li></ul> |
| Régions | <ul><li>Concerne les géos.</li><li>Pour regrouper plusieurs géos/pays en régions. Exemple : regroupez les États-Unis, le Canada et le Mexique dans "Amérique du Nord," ou utilisez des géos différents pour créer des groupes pour l'Europe, l'APAC, etc.</li><li>AppsFlyer regroupe les données en fonction de vos valeurs de région (Amérique du Nord, Europe, APAC, etc.).</li></ul> |
| Médias propriétaires et médias payants | <ul><li>Concerne les sources média.</li><li>Pou regrouper les différentes sources média selon son statut "propriétaire" ou "payante". Exemple : regroupez les SMS et les posts Facebook sous la valeur "propriétaire," et Facebook et Google sous la valeur "payante".</li><li>AppsFlyer regroupe les données de ces sources média selon les valeurs "propriétaire" et "payante".</li></ul> |
| Villes | <ul><li>Concerne les noms de vos campagnes.</li><li>Les valeurs incluent les villes qui ont des campagnes précises définies dans les noms de campagne.Exemple : "US\_Facebook\_NY" pour New York et "US\_Google\_SF" pour San Francisco.</li><li>AppsFlyer analyse le nom de la campagne et regroupe les données en fonction des villes.</li></ul> |
| Gestionnaire UA | <ul><li>Concerne les sources média.</li><li>Pour regrouper les différentes sources médias par membres d'équipe. Exemple : regroupez les campagnes Google et Facebook sous la valeur "Kevin", et les campagnes TikTok et Instagram sous la valeur "Natasha."</li><li>AppsFlyer regroupe les données de ces sources média selon les valeurs "Kevin" et "Natasha".</li></ul> |

<div id="procedures" />

## Procédures

<div id="create-a-custom-dimension" />

<Accordion title="Créer une dimension personnalisée">

**Pour créer une dimension personnalisée** :

1. Dans le tableau de bord général :
   * Cliquez sur l'**icône Menu** (⋮)  > **Dimension personnalisée**.  

     <Image align="center" alt="" src="https://files.readme.io/9c7a9e390b27972356f715a1379594fd4e6445274e478a6e469369d6c9fd2123-17109190496017.png" />
   * Dans un graphique ou un tableau, dans le menu déroulant **Afficher le haut**ou **Regrouper par**, cliquez sur **+ Créer une dimension personnalisée**.
2. Si vous créez une dimension personnalisée pour la première fois, cliquez sur **+ Nouvelle dimension**.  
   L'onglet **Créer** s'ouvre.
3. Saisissez un nom et une description pour votre dimension. Choisissez un nom et une description qui vous permettront d'identifier facilement cette dimension personnalisée dans les différents groupes du tableau de bord.
4. Définissez les valeurs possibles des dimensions. Il peut y avoir jusqu'à 10 valeurs par dimension. Pour chacune des valeurs :
   1. Saisissez un nom de valeur.
      * Exemple : pour une dimension personnalisée appelée «intention de campagne», les valeurs pourront être «branding» et «ua». Voir d'autres exemples de cas d'utilisation.
   2. Définissez les règles d'utilisation liées au nom de la valeur. Il peut y avoir jusqu'à 10 règles par valeur.
      * Chaque règle comprend la dimension existante sur laquelle la valeur se base, les opérateurs ainsi que les valeurs des opérateurs.
      * Exemple : si le nom de la campagne comprend "brd" ou "brnd,", le nom de la valeur sera "branding."Voir d'autres exemples de cas d'utilisation.
      * Le tableau suivant détaille les différents éléments qui permettent de définir une dimension. 

<table><thead><tr><th>Nom de la valeur</th><th>Dimension (sur laquelle se base la valeur)</th><th>operator</th><th>Valeur de l'opérateur</th></tr></thead><tbody><tr><td rowspan="3">Vous décidez des noms de valeurs possibles pour votre dimension personnalisée.</td><td><p>Source média</p></td><td rowspan="2"><p>Sélection : </p><ul><li>Est</li><li>contient</li><li>Commence par</li><li>Se termine par</li></ul></td><td><ul><li>Chaîne</li><li>Sélection déroulante (si l'opérateur est "is")</li></ul></td></tr><tr><td>Nom de la campagne</td><td><p>Chaîne</p></td></tr><tr><td>Géo</td><td>Est</td><td>Sélection déroulante</td></tr></tbody></table>

5. Cliquez sur ***Enregistrer***.

</Accordion>

<div id="delete-or-edit-a-custom-dimension" />

<Accordion title="Supprimer ou modifier une dimension personnalisée">

**Pour supprimer ou modifier une dimension personnalisée** :

1. Dans le tableau de bord général :
   * Cliquez sur l'**icône Menu** > **Dimension personnalisée**.  

     <Image align="center" alt="" src="https://files.readme.io/9c7a9e390b27972356f715a1379594fd4e6445274e478a6e469369d6c9fd2123-17109190496017.png" />
   * Dans un graphique ou un tableau, dans le menu déroulant **Afficher le haut**ou **Regrouper par**, cliquez sur **+ Créer une dimension personnalisée**.
2. Cliquez sur l'onglet **Modifier**.
3. Sélectionnez ou recherchez une dimension personnalisée.
4. Pour supprimer la dimension, cliquez sur l'icône **Supprimer** situé à côté de la dimension sélectionnée.
5. Pour modifier la dimension, apportez les modifications souhaitées à vos paramètres de dimension personnalisés, puis cliquez sur **Enregistrer**.

</Accordion>

<div id="view-custom-dimension-data" />

<Accordion title="Consulter les données des dimensions personnalisées">

Les dimensions personnalisées peuvent être utilisées pour regrouper et afficher les données dans tous les widgets du tableau de bord général.

**Pour afficher les données des dimensions personnalisées** :

1. Dans le tableau de bord général, accédez au graphique ou widget de tableau de bord de votre choix.
2. Dans le menu déroulant **Afficher le haut** ou **Regrouper par**, **Dimensions personnalisées**, recherchez la dimension personnalisée que vous souhaitez utiliser.  

   <Image align="center" alt="" src="https://files.readme.io/e34bcb2ca34546347b391f0ad921319f296a21c41c3783e59a7d808b44d0b6a9-17082706166929.png" />
3. Les données du graphique ou du tableau s'affichent dans un groupe qui utilise votre dimension personnalisée.

</Accordion>

<div id="specifications-and-limitations" />

<Accordion title="Caractéristiques et limitations">

| Caractéristiques | Remarques |
| --- | --- |
| Dimensions personnalisées | Vous pouvez créer jusqu'à 10 dimensions personnalisées. |
| Annonceur | Ne peut pas afficher ou modifier les dimensions personnalisées établies par les agences. |
| Agences | <ul><li>Peuvent créer et modifier leurs propres dimensions personnalisées et les afficher dans leur tableau de bord.</li><li>Ne peuvent pas modifier ou afficher les dimensions personnalisées établies par l'annonceur.</li></ul> |
| Réseaux publicitaires | Ne peuvent pas afficher, créer ou modifier les dimensions personnalisées. |
| Mesures SKAN | Lorsque la SSOT est désactivée et que les données sont regroupées par dimension personnalisée, les mesures SKAN ne s'affichent pas. |
| SSOT | Lorsque la SSOT est désactivée et que les données sont regroupées par dimension personnalisée basée sur géo, les données ne s'affichent pas. |
| Autorisations | Tout membre d'équipe peut créer de nouvelles dimensions et modifier les dimensions existantes, même si elles ont été créées par un autre membre de l'équipe. |
| Sensibilité à la casse | Les majuscules et minuscules sont traitées de la même manière. |
| Valeurs des dimensions | <ul><li>Il peut y avoir jusqu'à 10 valeurs de dimensions personnalisées.</li><li>Lors du matching des données avec les valeurs des dimensions personnalisées, la priorité est donnée aux dimensions les mieux classées.  Exemple :<ul><li>Pour la dimension correspondant aux médias payants ou propriétaires, vous définissez la valeur 1 comme étant un média payant si la source média est Facebook, et la valeur 2 comme étant un média propriétaire si la source média est Facebook.</li><li>Facebook peut être classé dans la catégorie médias payants ou propriétaires selon vos paramètres, mais AppsFlyer donnera la priorité au paramètre qui a la valeur 1 (payant).</li></ul></li></ul> |
| Opérateurs | L'opérateur « ne contient pas » n'est pas encore disponible. |
| Règles des dimensions | Vous pouvez avoir jusqu'à 10 règles par valeur de dimension. Elles sont reliées par « ou ».Le connecteur « et » n'est pas encore disponible. |

</Accordion>

<div data-zendesk-anchors="organic-search-attribution=pr%C3%A9sentation h_01H8XWQHPERAEDQVD275TFVC5B=pr%C3%A9sentation benefits=avantages h_01H8XWQHPE85376WV1Q9SPQ2NM=avantages example-use-cases=exemple-de-cas-dutilisation h_01H8XWQHPETE03XG9GGV9EBA2H=exemple-de-cas-dutilisation procedures=proc%C3%A9dures h_01H8XWQHPESY4DDDJSTR0JDHNB=proc%C3%A9dures h_01H8XWQHPEDYVDQQV3P8EDARAY=create-a-custom-dimension h_01H8XWQHPE22WZ46RTNCYKX96F=delete-or-edit-a-custom-dimension h_01H8XWQHPED4PFPJP2044FT1H8=view-custom-dimension-data h_01H8XWQHPF7WZ7B5Q7T9CHADRK=specifications-and-limitations" />
