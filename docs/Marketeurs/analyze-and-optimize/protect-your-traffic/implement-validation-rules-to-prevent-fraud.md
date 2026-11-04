---
title: Règles de validation pour les propriétaires d'apps
metadata:
  keywords:
    - Advertisers
    - validation rule
    - Marketers
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2017-09-14T14:43:46Z'
  edited_at: '2021-06-14T23:16:10Z'
  id: 115004703926
  locale: fr
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/fr/articles/115004703926
---
> **En bref :** les règles de validation sont une fonctionnalité premium d'AppsFlyer. Elles ajoutent une couche de protection personnalisée contre les campagnes mal ciblées et la fraude. Les règles permettent aux propriétaires d'apps de contrôler quelles installations et quels événements in-app sont bloqués, ou quelles installations sont attribuées à la source valide la plus récente.

![5906_animation-750x330__1_.gif](https://files.readme.io/2a5fbee83bdbc342c744f8079b743f06cb3205697bd9caa183593c411ae03d08-360014483338.gif)

## Présentation

* Les règles de validation sont définies dans le générateur de règles à l'aide de conditions et d'une logique personnalisées qui filtrent et sélectionnent les installations d'app ou les événements in-app à conserver ou à bloquer.
* Les règles sont basées sur une variété de paramètres pour de multiples cas d'utilisation, notamment :
  * Installations non ciblées pour votre campagne (mauvaise geo, version du système d'exploitation, etc.)
  * Installations qui ne répondent pas à l'ordre d'insertion signée avec l'ad network
  * Installations piratées par des réseaux frauduleux
  * Fausses installations ou événements in-app envoyés par des bots, des émulateurs ou des fermes d'appareils
* Les règles définies pour les événements in-app ne prennent effet que sur les EIA associés à des installations qui n'ont pas déjà été bloquées.
* Les règles qui incluent un ad network sont visibles par le personnel de cet ad network (mais elles ne peuvent pas voir les autres ad networks inclus dans la règle). Ceci est dans l'intérêt de la transparence et pour aider les ad networks à mieux comprendre les performances du trafic qu'ils fournissent.
* Les règles s'exécutent en temps réel et sont effectives immédiatement. Pour en savoir plus, consultez la section [Résultats](/docs/implement-validation-rules-to-prevent-fraud#outcomes).
* Des options supplémentaires de règles de validation sont disponibles pour les clients <Anchor target="_blank" href="/marketers/fr/docs/protect360-anti-fraud-guide">Protect360</Anchor>, en plus du blocage et de la détection automatiques de la fraude par Protect360. Ces conditions sont connues pour aider à la détection de diverses installations détournées, fausses installations et faux événements in-app.  
   **Note** : les règles de validation ne valident que les installations / évenements in-app qui n'ont pas été identifiés comme frauduleux par Protect360.

<Accordion title="Résultats">

* Pour les installations : les règles de validation, en fonction de l'action sélectionnée, bloquent soit l'attribution à des sources non valides, soit l'installation.
* Pour les événements in-app : les règles de validation bloquent l'événement in-app.
* Voir le tableau suivant pour les détails.  

| Type de blocage | Description | Où les données d'installation peuvent être visualisées | Les événements in-app qui suivent |
| --- | --- | --- | --- |
| Bloquer attribution | <ul><li>Sélectionnée lorsque vous considérez l'installation comme réelle, mais vos conditions déterminent quelles sources doivent être attribuées ou non.</li><li>L'attribution est corrigée, et l'installation est attribuée à la dernière source média valide.</li><li>Si aucune source média valide n'est identifiée, l'installation est marquée comme étant organique.</li></ul> | <ul><li>Tableaux de bord AppsFlyer et rapports de données brutes en tant qu'installation régulière (attribuée à la dernière source média valide)</li><li>Avec Protect360 Premium :<ul><li><Anchor target="_blank" href="/marketers/fr/docs/protect360-dashboard#tableau-de-bord-des-installations">Tableau de bord des installations Protect 360</Anchor></li><li>Protect360 installe un rapport de données brutes (avec la source média bloquée)</li></ul></li><li>Sans Protect360 Premium :<ul><li>Protect360 installe un rapport de données brutes (avec la source média bloquée)</li></ul></li></ul> | <ul><li>A la même attribution corrigée que l'installation</li><li>Données disponibles avec Protect360 Premium :<ul><li>Avec une attribution corrigée dans les tableaux de bord et les rapports AppsFlyer en tant qu'EIA régulier.</li><li>Avec source média bloquée dans le tableau de bord des EIA Protect360 et le rapport de données brutes d'EIA Protect360 bloqués</li></ul></li></ul> |
| Installation bloquée | <ul><li>Sélectionné lorsque les installations qui ne sont pas valides selon les conditions de la règle sont considérées comme fausses.</li><li>L'installation n'est pas du tout attribuée (elle n'apparaît donc pas dans les tableaux de bord ou les rapports Appsflyer).</li></ul> | <ul><li>Avec Protect360 Premium :<ul><li><Anchor target="_blank" href="/marketers/fr/docs/protect360-dashboard#tableau-de-bord-des-installations">Tableau de bord des installations Protect 360</Anchor></li><li>Protect360 installe un rapport de données brutes (avec la source média bloquée)</li></ul></li><li>Sans Protect360 Premium :<ul><li>Protect360 installe un rapport de données brutes (avec la source média bloquée)</li></ul></li></ul> | <ul><li>Bloqué</li><li>Données disponibles avec Protect360 Premium dans le tableau de bord des EIA Protect360 et le rapport de données brutes des EIA bloqués</li></ul> |
| Événements in-app bloqués | <ul><li>Appliqué automatiquement aux règles de validation pour les événements in-app.</li></ul> | <ul><li>Avec Protect360 Premium :<ul><li><Anchor target="_blank" href="/marketers/fr/docs/protect360-dashboard#tableau-de-bord-des-événements-in-app">Tableau de bord Protect360 des EIA</Anchor></li><li>Rapport sur les données brutes des événements in-app Protect360</li></ul></li><li>Sans Protect360 Premium : N/A</li></ul> | <ul><li>Données disponibles avec Protect360 Premium dans le <Anchor target="_blank" href="/marketers/fr/docs/protect360-dashboard#tableau-de-bord-des-événements-in-app">tableau de bord des EIA</Anchor> Protect360 et le rapport de données brutes d'événements in-app bloqués</li></ul> |

* Les ad networks et les agences ne peuvent afficher les données que si l'annonceur leur donne les <Anchor target="_blank" href="/marketers/fr/docs/raw-data-reporting-overview#protect360-fraud-and-validation-rules">autorisations</Anchor> requises.
* Lorsqu'une installation est bloquée ou attribuée à une source média valide en temps réel, un postback de rejet est instantanément envoyé à l'ad network bloqué, afin de rationaliser votre flux de réconciliation. Lorsque l'attribution est bloquée et corrigée à la dernière source média valide, un postback est également envoyé au dernier ad network valide.
* Lorsqu'un événement in-app est bloqué, un postback de rejet est instantanément envoyé à l'ad network bloqué.  
  **Remarque** :
  * Un postback n'est envoyé que si l'ad network configuré pour le recevoir est intégré à AppsFlyer pour recevoir des postbacks.
  * Les rapports de postbacks et de postbacks rejetés sont disponibles sur la page d'exportation.
  * En savoir plus sur les postbacks et les <Anchor target="_blank" href="/partners/fr/docs/rejected-attribution-postbacks-to-integrated-partners">postbacks rejetés</Anchor>.
* Le blocage de l'installation et de l'attribution, ainsi que le blocage des EIA, n'affectent que la manière et l'endroit où les données sont rapportées dans AppsFlyer. Ils n'empêchent pas l'utilisation des apps par vos utilisateurs finaux.
  * Si nécessaire, vous pouvez utiliser l'installation bloquée <Anchor target="_blank" href="/marketers/fr/docs/protect360-raw-data-reports">et les rapports de données brutes des EIA bloqués</Anchor> (disponibles via l'exportation, l'API pull et Data Locker), pour obtenir la liste des utilisateurs de l'app à désactiver.
* Les rapports sur les installations/EIA bloqués et les postbacks rejetés contiennent  le nom des règles qui ont bloqué les installations/EIA sous la raison du blocage. Consultez la section [règles multiples](/docs/implement-validation-rules-to-prevent-fraud#multiple-rules) s'il y a plus d'une règle.
  * Lorsque les installations/EIA sont bloqués par le moteur anti-fraude Protect360, même s'il existe également une règle de validation, les motifs Protect360 s'affichent.
* Les règles peuvent entraîner des divergences dans les rapports entre AppsFlyer et les SRN comme <Anchor target="_blank" href="/marketers/fr/docs/meta-ads-integration-setup#discrepancies">Facebook Ads</Anchor> et <Anchor target="_blank" href="/marketers/fr/docs/google-ads-adwords-integration-setup-for-advertisers#faq-discrepancies">Google Adwords</Anchor> car ils déploient leur propre logique pour valider les installations.

</Accordion>

<Accordion title="Règles multiples">

* Plusieurs règles de validation peuvent être exécutées sur la même installation / EIA. Cela se produit lorsque l'installation remplit les conditions de plusieurs règles.
* L'installation/EIA est classé comme non valide lorsqu'il ne respecte pas les conditions  de l'une ou l'autre des règles séparément.
* Dans les rapports de données brutes et les postbacks rejetés, le champ de la valeur **Motif du blocage** contient les noms de toutes les règles qui classent l'installation comme non valide. Le **sous-motif du bloc** contient le nom de la première règle à exécuter.
* Plusieurs règles pour la même installation sont séquencées pour s'exécuter dans l'ordre suivant, en fonction des types de blocage des règles :

| Types de règle/blocage | Commande |
| --- | --- |
| Bloquer les installations | Aléatoire |
| Bloquer attribution | Aléatoire |
| Événement in-app bloqué | Aléatoire |
| Installations et attribution bloquées | <ol><li>Règles relatives aux installations bloquées (dans un ordre aléatoire)</li><li>Règles relatives aux attributions bloquées (dans un ordre aléatoire)</li></ol> |
| Installations et attributions bloquées avec le moteur Protect360 et les règles de validation | <ol><li>Installations bloquées avec le moteur Protect360</li><li>Installation bloquée avec les règles de validation</li><li>Attribution bloquée avec le moteur Protect360</li><li>Attribution bloquée avec les règles de validation</li></ol> |
| Événements in-app bloqués avec le moteur Protect360 et les règles de validation | <ol><li>EIA bloqués avec le moteur Protect360</li><li>EIA bloqués avec les règles de validation</li></ol> |

</Accordion>

## Générateur de règles

L'interface utilisateur du générateur de règles est conçue pour la création interactive de règles. **Astuce !** Familiarisez-vous avec le générateur de règles et expérimentez avant de lire cet article en détail.

[![](https://files.readme.io/ed1bfe9c2d4a806bd1c00449f6245a965d2be4257a39076f1b33abd24ec8836a-360014789398.jpg)](https://files.readme.io/ed1bfe9c2d4a806bd1c00449f6245a965d2be4257a39076f1b33abd24ec8836a-360014789398.jpg)

Le générateur de règles contient les sections suivantes :

| Section | Remarques |
| --- | --- |
| Événements | <ul><li>**Type d'événement** pour lequel la règle est appliquée : installations ou événements in-app.</li><li>**Apps** pour lesquelles la règle est appliquée : une seule app, plusieurs apps, ou toutes les apps du compte.</li><li>La sélection affecte les options disponibles dans les sections suivantes (agence, source média, campagne, etc.)</li></ul> |
| Sources | Source de trafic pour laquelle la règle est appliquée. [Voir également Sources Protect360](/docs/implement-validation-rules-to-prevent-fraud#protect360-sources) |
| Important | Décidez si les conditions définies déterminent que les installations sont invalides ou valides.<ul><li>**Invalide** :<ul><li>Les installations/sources répondant aux conditions définies sont considérées comme **invalides**.</li><li>L'action sélectionnée est effectuée sur **tous**.</li></ul></li><li>**Valide** :<ul><li>Les installations sont considérées comme valides, mais toutes les installations qui ne remplissent PAS les conditions spécifiées sont considérées comme invalides.</li></ul></li></ul> |
| CONDITIONS | Les conditions qui déterminent la validité de l'installation en fonction de divers paramètres, ainsi que votre sélection dans la section « considérée comme ». [Voir également les conditions Protect360](/docs/implement-validation-rules-to-prevent-fraud#protect360-conditions) |
| Action | <ul><li>Pour les installations : sélectionnez les actions pour les installations répondant aux conditions spécifiées.<ul><li>Bloquer l'attribution et la modifier d'après la dernière source média valide.</li><li>Bloquer les installations et n'attribuer aucune source.</li></ul></li><li>Pour les événements in-app : aucune sélection : les règles de validation bloquent l'événement in-app.</li></ul>Reportez-vous à la rubrique [Résultats](/docs/implement-validation-rules-to-prevent-fraud#outcomes) pour plus d'informations. |

<Accordion title="Sources">

C'est dans la section **Sources** que vous définissez les sources de trafic des installations auxquelles la règle s'applique.

Il existe deux options principales :

* **Tout le trafic** : la règle s'applique à toute installation, quelle que soit sa source (agence, source média, campagne, organique, etc.).  
  **Remarque** : comme cette option inclut des installations organiques, aucune autre information source ne peut être sélectionnée et seule l'option d'installation bloquée est disponible. Cela est dû au fait qu'il n'est pas possible de bloquer/corriger l'attribution des installations organiques.
* **Non-organique uniquement** : la règle s'applique aux sources que vous sélectionnez, avec les champs, opérateurs et valeurs décrits dans le tableau qui suit.

Des options de source supplémentaires sont disponibles pour les clients Protect360, pour les [installations](/docs/implement-validation-rules-to-prevent-fraud#protect360-install-sources) et les [événements in-app](/docs/implement-validation-rules-to-prevent-fraud#protect360-inapp-event-conditions).

<table><thead><tr><th>Champ</th><th>operator</th><th>valeur</th><th>Remarques</th></tr></thead><tbody><tr><td>agences</td><td><ul><li>Dans</li></ul></td><td><ul><li>Trafic des agences et non-agences</li><li>Trafic de non-agences</li><li>Agences transparentes (menu)</li><li>Agences non transparentes (menu)</li></ul></td><td><ul><li> <span>Si vos apps sont intégrées à des agences, ce champ est obligatoire car il affecte les options du champ de la source média.</span><ul><li>Si aucune de vos apps n'est intégrée aux agences, le champ ne s'affiche pas.</li></ul></li><li> <span>Agences non transparentes</span><ul><li>Il s'agit d'agences qui ne partagent pas leurs sources de trafic.</li><li>Lorsque l'option « Agences non transparentes » ou « Trafic d'agence et de non agence » est sélectionnée, il n'est pas possible de sélectionner des sources média spécifiques.</li><li>Les publicités Facebook et Twitter restent disponibles même lorsque des agences non transparentes sont sélectionnées, car les publicités ont toujours besoin d'agences pour les partager en tant que sources.</li></ul></li><li> <span>Agences transparentes :</span><ul><li>Il s'agit d'agences qui précisent leurs sources média.</li><li>Les agences qui ne sont transparentes que pour certaines de vos apps s'affichent dans le menu des agences non transparentes.</li></ul></li></ul></td></tr><tr><td>Source média</td><td><ul><li><span>Dans la liste</span></li><li><span>Pas dans la liste</span></li><li><span>Equivaut à</span></li><li><span>N'équivaut pas à</span></li><li><span>contient</span></li><li><span>Ne contient pas</span></li><li><span>Commence par</span></li><li><span>Se termine par</span></li><li> <span>Correspond à l'expression régulière</span><span></span> </li></ul></td><td><ul><li><span>Recherchez la valeur souhaitée.</span></li><li><span>Sélectionnez dans le menu. </span></li><li><span>Texte libre (pour les valeurs qui n'existent pas dans vos résultats de recherche).</span></li></ul></td><td rowspan="5"><ul><li> <span>Le menu est basé sur :</span><ul><li>Apps et agences sélectionnées.</li><li>Trafic des 30 derniers jours, classé par volume de trafic.</li></ul></li><li><span>Le texte libre doit être saisi exactement tel qu'il apparaît dans les données brutes. </span></li></ul></td></tr><tr><td>Campagne</td><td rowspan="4"><ul><li><span>Dans la liste</span></li><li><span>Pas dans la liste</span></li><li><span>Equivaut à</span></li><li><span>N'équivaut pas à</span></li><li><span>contient</span></li><li><span>Ne contient pas</span></li><li><span>Commence par</span></li><li><span>Se termine par</span></li><li><span>Est vide</span></li><li><span>N'est pas vide</span></li><li><span>Correspond à l'expression régulière</span></li></ul></td><td><ul><li>Recherchez la valeur souhaitée.</li><li>Sélectionnez une valeur dans le menu.</li><li>Texte libre (pour les valeurs qui n'existent pas dans vos résultats de recherche).</li></ul></td></tr><tr><td>Identifiant de publicité</td><td rowspan="3"><ul><li><span>Texte libre uniquement.</span></li><li><span>Possibilité d'ajouter plusieurs valeurs séparées par des espaces.</span></li></ul></td></tr><tr><td>Identifiant de l'ensemble de publicités</td></tr><tr><td>Nom de l'ensemble de publicités</td></tr></tbody></table>

</Accordion>

<Accordion title="CONDITIONS">

La section **Conditions** est l'endroit où vous définissez les conditions qui déterminent quand les installations sont bloquées, ou attribuées à la dernière source valide.

Vous pouvez ajouter plusieurs conditions et des groupes de conditions à chaque règle.

Les conditions sont définies selon les conditions, opérateurs et valeurs définies dans le tableau qui suit.

Des options de source supplémentaires sont disponibles pour les clients Protect360, pour les [installations](/docs/implement-validation-rules-to-prevent-fraud#protect360-install-conditions) et les [événements in-app](/docs/implement-validation-rules-to-prevent-fraud#protect360-inapp-event-conditions).

<table><thead><tr><th><span>Condition</span></th><th><span>operator</span></th><th><span>valeur</span></th><th><span>Remarques</span></th></tr></thead><tbody><tr><td><span>Campagne</span></td><td rowspan="5"><ul><li><span>Equivaut à</span></li><li><span>N'équivaut pas à</span></li><li><span>Ne contient pas</span></li><li><span>contient</span></li><li><span>Commence par</span></li><li><span>Se termine par</span></li><li><span>Dans la liste</span></li><li><span>Pas dans la liste</span></li><li><span>Correspond à l'expression régulière</span></li><li><span>Est vide</span></li><li><span>N'est pas vide</span></li></ul></td><td><ul><li>Recherchez la valeur souhaitée.</li><li>Sélectionnez une valeur dans le menu.</li><li>Texte libre (pour les valeurs qui n'existent pas dans vos résultats de recherche).</li></ul></td><td rowspan="8"><ul><li> <span>Le menu est basé sur :</span><ul><li>Apps et agences sélectionnées.</li><li>Trafic des 30 derniers jours, classé par fréquence de trafic.</li></ul></li><li><span>Le texte libre doit être saisi exactement tel qu'il apparaît dans les données brutes.</span></li></ul></td></tr><tr><td><span>Identifiant de publicité</span></td><td rowspan="4"><ul><li><span>Texte libre uniquement.</span></li><li><span>Possibilité d'ajouter plusieurs valeurs séparées par des espaces.</span></li></ul></td></tr><tr><td><span>Identifiant de l'ensemble de publicités</span></td></tr><tr><td><span>Nom de l'ensemble de publicités</span></td></tr><tr><td><span>Type d'appareil</span></td></tr><tr><td><span>Géo</span></td><td rowspan="2"><ul><li><span>Dans la liste</span></li><li><span>Pas dans la liste</span></li><li><span>Equivaut à</span></li><li><span>N'équivaut pas à</span></li></ul></td><td><ul><li><span>Rechercher la valeur souhaitée (selon le nom du pays, l'indicatif du pays, l'État ou la ville).</span></li><li><span>Sélectionnez une valeur dans le menu.</span></li></ul></td></tr><tr><td><span>Plate-forme</span></td><td><p><span>Sélectionnez une valeur dans le menu.</span></p></td></tr><tr><td><span>Version OS</span></td><td><ul><li><span>Plus petit que</span></li><li><span>Inférieur ou égal à</span></li><li><span>Plus grand que</span></li><li><span>Supérieur ou égal à</span></li><li><span>Equivaut à</span></li><li><span>N'équivaut pas à</span></li><li><span>Est compris entre</span></li><li><span>Dans la liste</span></li><li><span>Pas dans la liste</span></li></ul></td><td><ul><li><span>Recherchez la valeur souhaitée.</span></li><li><span>Sélectionnez dans le menu. </span></li><li><span>Texte libre (pour les valeurs qui n'existent pas dans vos résultats de recherche).</span></li></ul></td></tr><tr><td><span>Jours rétrospectifs</span></td><td><ul><li><span>Plus petit que</span></li><li><span>Inférieur ou égal à</span></li><li><span>Plus grand que</span></li><li><span>Supérieur ou égal à</span></li><li><span>Est compris entre</span></li></ul></td><td><ul><li><span>Texte libre : valeur numérique unique.</span></li></ul></td><td><ul><li><span>Désigne la fenêtre d'attribution par clic en jours.</span></li><li><span>S'assure que vous ne payez pas les installations avec un lien d'attribution qui a été modifié pour permettre une période d'attribution plus longue.</span></li><li><span>Ne remplace pas la configuration de la fenêtre d'attribution dans votre lien d'attribution. </span></li></ul></td></tr><tr><td><span>Est préinstallé</span></td><td rowspan="2"><ul><li><span>Oui</span></li><li><span>Non</span></li></ul></td><td rowspan="2"><ul><li>Pas de valeur (l'opérateur est la valeur)</li></ul></td><td><ul><li> <span>Valide tous les types de préinstallations :</span><ul><li><span>Pré-installations en usine, c'est-à-dire une app installée dans l'appareil dans le cadre du système d'exploitation.</span></li><li><span>Pré-installations proposées, c'est-à-dire une app promue et proposée aux utilisateurs dès l'initialisation de l'appareil. Cette opération s'effectue par les sources média désignées pour les pré-installations.</span></li></ul></li><li>Pour les installations avec plusieurs clics/sources, cette condition valide si l'une des sources est une pré-installation.</li></ul></td></tr><tr><td><span>Is deeplink (est deeplink)</span></td><td><p><span>Un champ de deep link vide dans les données brutes est considéré comme </span><span> Is deeplink = No</span></p></td></tr></tbody></table>

</Accordion>

<Accordion title="Sources d'installation de Protect360">

En plus des [options de source habituelles](/docs/implement-validation-rules-to-prevent-fraud#sources), les clients Protect360 disposent d'une autre option de source pour définir les installations auxquelles leur règle s'applique. La source est définie selon le champ, les opérateurs et les valeurs indiqués dans le tableau qui suit.

| Champ | operator | valeur | Remarques |
| --- | --- | --- | --- |
| ID site | <ul><li>Dans la liste</li><li>Pas dans la liste</li><li>Equivaut à</li><li>N'équivaut pas à</li><li>contient</li><li>ne contient pas</li><li>Commence par</li><li>Se termine par</li><li>Est vide</li><li>N'est pas vide</li><li>Correspond à l'expression régulière</li></ul> | <ul><li>Texte libre uniquement.</li><li>Possibilité d'ajouter plusieurs valeurs séparées par des espaces.</li></ul> | <ul><li>Le texte libre doit être saisi exactement tel qu'il apparaît dans les données brutes.</li></ul> |

</Accordion>

<Accordion title="Conditions d'installation de Protect360">

Les clients Protect360 disposent d'un ensemble de conditions supplémentaires pour valider leurs installations. Ces conditions peuvent être mélangées et associées à l'une des conditions non-Protect360 [répertoriées précédemment](/docs/implement-validation-rules-to-prevent-fraud#conditions).

Les conditions Protect360 sont définies selon les conditions, opérateurs et valeurs définies dans le tableau qui suit.

<table><thead><tr><th><span>Condition</span></th><th><span>operator</span></th><th><span>valeur</span></th><th><span>Remarques</span></th></tr></thead><tbody><tr><td><span> CTIT (Click Time to Install Time)</span></td><td><ul><li><span>Plus petit que</span></li><li><span>Inférieur ou égal à</span></li><li><span>Plus grand que</span></li><li><span>Supérieur ou égal à</span></li><li><span>Est compris entre</span></li></ul></td><td><ul><li><span>Texte libre : valeur numérique unique.</span></li></ul></td><td><ul><li><span>Utilisez ce champ uniquement si vous êtes certain d'un CTIT spécifique (généralement dans une géo spécifique). Sinon, vous risquez de provoquer des installations bloquées falsifiées.<br/><strong>Note</strong> : le moteur anti-fraude de Protect360 a intégré des moyens sophistiqués pour identifier les anomalies CTIT complexes dues au détournement d'attribution, au click flooding, aux fausses installations par des bots, et plus encore.</span></li><li> <span>Pensez à utiliser ce champ avec les champs suivants :</span><ul><li>Est pré-installé</li><li>Is deeplink (est deeplink)</li><li>Géo</li></ul></li></ul></td></tr><tr><td><span>ID utilisateur du client (CUID)</span></td><td><ul><li><span>Equivaut à</span></li><li><span>N'équivaut pas à</span></li><li><span>Ne contient pas</span></li><li><span>contient</span></li><li><span>Commence par</span></li><li><span>Ne commence pas par</span></li><li><span>Se termine par</span></li><li><span>Ne se termine pas par</span></li><li><span>Dans la liste</span></li><li><span>Pas dans la liste</span></li><li><span>Correspond à l'expression régulière</span></li><li><span>Est vide</span></li><li><span>N'est pas vide</span></li></ul></td><td><ul><li><span>Texte libre uniquement.</span></li><li><span>Possibilité d'ajouter plusieurs valeurs séparées par des espaces.</span></li></ul></td><td rowspan="3"><ul><li> <span>Le menu est basé sur le trafic du site</span>des 30 derniers jours, classé par fréquence de trafic.</li><li><span>Le texte libre doit être saisi exactement tel qu'il apparaît dans les données brutes.</span></li></ul><br/><br/> </td></tr><tr><td><span>Version de l'app</span></td><td rowspan="2"><ul><li><span>Plus petit que</span></li><li><span>Inférieur ou égal à</span></li><li><span>Plus grand que</span></li><li><span>Supérieur ou égal à</span></li><li><span>Equivaut à</span></li><li><span>N'équivaut pas à</span></li><li><span>Est compris entre</span></li><li><span>Dans la liste</span></li><li><span>Pas dans la liste</span></li></ul></td><td rowspan="2"><ul><li>Recherchez la valeur souhaitée.</li><li>Sélectionnez une valeur dans le menu. </li><li>Texte libre (pour les valeurs qui n'existent pas dans vos résultats de recherche).</li></ul></td></tr><tr><td><span>Version du SDK</span></td></tr><tr><td><span>Installateur/Magasin</span></td><td><ul><li>Dans la liste</li><li>Pas dans la liste</li><li>Equivaut à</li><li>N'équivaut pas à</li></ul></td><td><p><span>Sélectionnez une valeur dans le menu :</span></p><ul><li>Google Play</li><li>Autres magasins</li><li>Hors magasin</li></ul></td><td><span>Dans le cas où l'appareil d'un utilisateur ne fournit pas le paramètre installateur/magasin à AppsFlyer, la règle ne prend pas effet.</span></td></tr></tbody></table>

</Accordion>

<Accordion title="Sources d'événements in-app Protect360">

Lorsque l'option **Evénements in-app** est sélectionnée dans la section **Événements**, les clients Protect360 disposent, en plus des options de source habituelles , d'une autre option de source pour définir les événements in-app auxquels leur règle s'applique.

La source est définie selon le champ, les opérateurs et les valeurs indiqués dans le tableau qui suit.

**Remarque** : toutes les autres sources d'événements in-app sont basées sur la source de l'installation à laquelle l'EIA est associé (par exemple, agence, source média, campagne, ID de site, etc.).

| Champ | operator | valeur | Remarques |
| --- | --- | --- | --- |
| Nom de l'événement | <ul><li>Dans la liste</li><li>Pas dans la liste</li><li>Equivaut à</li><li>N'équivaut pas à</li><li>contient</li><li>ne contient pas</li><li>Commence par</li><li>Se termine par</li><li>Est vide</li><li>N'est pas vide</li><li>Correspond à l'expression régulière</li></ul> | <ul><li>Recherchez la valeur souhaitée.</li><li>Sélectionnez une valeur dans le menu.</li><li>Texte libre (pour les valeurs qui n'existent pas dans vos résultats de recherche).</li></ul> | <ul><li>Le texte libre doit être saisi exactement tel qu'il apparaît dans les données brutes.</li></ul> |

</Accordion>

<Accordion title="Conditions des événements in-app Protect360">

Lorsque l'option **Événements in-app** est sélectionnée dans la section **Événements**, les clients Protect360 disposent d'options de conditions supplémentaires pour définir les événements in-app auxquels leur règle s'applique. Ces conditions peuvent être mélangées et associées à l'une des conditions non-Protect360 [répertoriées précédemment](/docs/implement-validation-rules-to-prevent-fraud#conditions).

Les conditions Protect360 sont définies selon les conditions, opérateurs et valeurs définies dans le tableau qui suit.

<table><thead><tr><th>Condition</th><th>operator</th><th>valeur</th><th>Remarques</th></tr></thead><tbody><tr><td><span>Nom de l'événement</span></td><td rowspan="3"><ul><li><span>Dans la liste</span></li><li><span>Pas dans la liste</span></li><li><span>Equivaut à</span></li><li><span>N'équivaut pas à</span></li><li><span>contient</span></li><li><span>ne contient pas</span></li><li><span>Commence par</span></li><li><span>Se termine par</span></li><li><span>Est vide</span></li><li><span>N'est pas vide</span></li><li><span>Correspond à l'expression régulière</span></li></ul></td><td rowspan="2"><ul><li>Recherchez la valeur souhaitée.</li><li>Sélectionnez une valeur dans le menu. </li><li>Texte libre (pour les valeurs qui n'existent pas dans vos résultats de recherche).</li></ul></td><td rowspan="3"><ul><li><span>Le texte libre doit être saisi exactement tel qu'il apparaît dans les données brutes. </span></li></ul><span><br/></span><span><br/></span> </td></tr><tr><td><span>Source de l'évènement</span></td></tr><tr><td><span>Valeur de l'événement</span></td><td><ul><li><span>Texte libre uniquement.</span></li><li><span>Possibilité d'ajouter plusieurs valeurs séparées par des espaces.</span></li></ul></td></tr><tr><td><span>Délai entre l'installation et l'événement (en secondes)</span></td><td><ul><li><span>Plus petit que</span></li><li><span>Supérieur ou égal à</span></li><li><span>Est compris entre</span></li></ul></td><td><span>Texte libre. Une valeur numérique unique.</span></td><td><ul><li> <span>En fonction du flux de votre app, vous décidez du temps valide entre l'installation de l'app et un EIA.</span><br/><ul><li>Exemple : temps pour atteindre le niveau 5, temps pour le premier achat (FTD), temps pour le passage en caisse, etc.</li></ul></li><li> <span>Le temps est en secondes, mais vous pouvez valider les minutes, les heures ou les jours en utilisant l'équivalent en secondes.</span><span></span> </li></ul></td></tr></tbody></table>

</Accordion>

<Accordion title="Logique entre les conditions et les groupes de conditions">

Si vous ajoutez plusieurs conditions ou groupes de conditions à une règle, sélectionnez la relation logique entre elles en utilisant l'une des options suivantes : 

* **Et**  : signifie que l'installation est conforme à toutes les conditions définies.
* **Ou**  : signifie que l'installation est conforme à au moins une des conditions définies.

Par exemple, si vous souhaitez valider les installations en fonction de la plateforme et du système d'exploitation, vous devez sélectionner **et**. De cette façon, la plate-forme définie doit toujours accompagner le système d'exploitation défini. Si vous souhaitez valider les installations en fonction de la plate-forme ou du système d'exploitation, vous devez sélectionner **ou**.

</Accordion>

## Procédures

<Accordion title="Afficher la liste des règles">

**Pour afficher toutes les règles créées dans votre compte** :

1. Dans AppsFlyer, accédez à **Configuration** > **Règles de validation.**  
   La fenêtre Règles de validation s'ouvre, avec la liste des règles de validation.
2. Sélectionnez votre vue tabulaire préférée à l'aide du bouton **Vue liste/Détails**.
3. Filtrez les règles de la liste à l'aide des options de recherche et de filtrage. 
   * Vous pouvez effectuer une recherche par nom de règle, source, nom de condition et valeur.
   * Par exemple, tapez **7** pour trouver toutes les règles définies pour une version de système d'exploitation qui contient 7 (par exemple : 2.7.4, 7.1, etc.). Ou tapez **Canada** pour trouver les règles définies avec le Canada dans la condition géo.

</Accordion>

<Accordion title="Ajouter une règle">

**Pour configurer une nouvelle règle** :

1. Dans AppsFlyer, allez dans  **Configuration** >  **Règles de validation.**  
    La fenêtre Règles de validation s'ouvre.
2. Cliquez sur  **Ajouter une règle.**  La fenêtre Ajouter une nouvelle règle s'ouvre.
3. Insérez un **nom de règle**.Utilisez un nom unique qui :
   * décrit avec précision la règle.
   * n'est pas offensant pour les ad networks, puisqu'il apparaît dans le rapport des installations bloquées, ainsi que dans celui des postbacks refusés aux ad networks.
4. Complétez les [sections du constructeur de règle.](/docs/implement-validation-rules-to-prevent-fraud#rule-builder-sections)
5. [Facultatif] Ajoutez des conditions et/ou groupes de conditions, selon les besoins. Veillez à sélectionner la logique pertinente [entre les conditions/groupes de conditions](/docs/implement-validation-rules-to-prevent-fraud#logic-between-conditions-and-condition-groups).
6. [Facultatif] Cliquez sur **Estimer l'impact du trafic** pour [voir comment votre règle affectera le trafic](/docs/implement-validation-rules-to-prevent-fraud#view-validation-rule-impact).
7. Cliquez sur ***Enregistrer***.

</Accordion>

<Accordion title="Afficher l'impact des règles de validation">

Visualisez l'impact estimé de vos règles de validation sur le trafic, c'est-à-dire le nombre d'installations et d'attributions bloquées qui pourraient survenir.

![vr_estimate.png](https://support.appsflyer.com/hc/article_attachments/360019928077/vr_estimate.png)

> 📘 **Remarque**
>
> * L'estimateur de règles de validation est uniquement accessible aux annonceurs. Les partenaires n'ont pas accès.
> * Les estimations sont disponibles pour les règles liées aux installations, pas pour les événements in-app.
> * L'estimation affiche également ce qui s'applique à la règle, mais qui est **déjà bloqué** par la protection antifraude Protect360, une autre règle de validation ou, si la règle estimée n'est pas nouvelle, le trafic bloqué par son paramètre précédent.

**Pour voir l'impact estimé de votre règle de validation** :

1. Dans AppsFlyer, allez dans **Règles de validation**.
2. Sélectionnez une règle existante ou cliquez sur **+ Ajouter une règle** et [créez une nouvelle règle](/docs/implement-validation-rules-to-prevent-fraud#add-rule) avec des sources de règles et des conditions.
3. Faites défiler jusqu'au bas de la règle et cliquez sur **Estimer l'impact sur le trafic**.  
    La fenêtre de l'impact estimé de la règle s'ouvre.
4. Choisissez si vous voulez baser l'impact estimé sur les données depuis le jour précédent ou sur les 7 derniers jours.
   * L'estimation des nouveaux blocages, ainsi que le pourcentage du trafic nouvellement bloqué en raison de la règle de validation, s'affichent.
   * Lorsque la règle est définie sur des sources non organiques uniquement, l'estimation affiche l'impact de la règle par rapport à l'ensemble de votre trafic. Pour voir l'impact par rapport aux sources uniquement (par exemple, une source média ou une campagne spécifique), dans la légende du graphique, désélectionnez **Autres sources**.  

     [![](https://support.appsflyer.com/hc/article_attachments/360020016218/vr_estimate_other_sources.png)](https://support.appsflyer.com/hc/article_attachments/360020016218/vr_estimate_other_sources.png)

</Accordion>

<Accordion title="Modifier ou supprimer une règle">

**Pour modifier, supprimer, activer ou désactiver une règle** :

* Dans la [liste de règles](/docs/implement-validation-rules-to-prevent-fraud), sélectionnez l'action que vous souhaitez effectuer pour une règle spécifique.
  * Sous **Actif** : activez ou désactivez la règle.
  * Sous **Action** : modifiez ou supprimez la règle.

</Accordion>

## API des règles de validation

Les développeurs peuvent utiliser l'API des règles de validation pour [obtenir](https://dash.readme.com/project/hc/v0.1/refs/get-rules), [créer](https://dash.readme.com/project/hc/v0.1/refs/create-rule), [mettre à jour les règles](https://dash.readme.com/project/hc/v0.1/refs/update-rule) et [mettre à jour leur statut](https://dash.readme.com/project/hc/v0.1/refs/update-rule-status).

* [Obtenir des règles :](https://dash.readme.com/project/hc/v0.1/refs/get-rules) fournit une liste de toutes vos règles de validation avec des détails concernant toutes les conditions de la règle.
* [Créer une règle](https://dash.readme.com/project/hc/v0.1/refs/create-rule) : crée une nouvelle règle avec des conditions spécifiques.
* [Mettre une règle à jour](https://dash.readme.com/project/hc/v0.1/refs/update-rule) : change/modifie les conditions d'une règle existante.
* [Mettre à jour le statut d'une règle](https://dash.readme.com/project/hc/v0.1/refs/update-rule-status) : active, désactive ou supprime une règle existante.

<div id="example-latest-version-calculation" />

<div id="how-appsflyer-determines-the-latest-version" />

<div id="understand-how-the-condition-works-with-multiple-apps" />

<div id="example-not-in-last-major" />

<div id="example-not-in-last" />

## FAQ

<Accordion title="Qu'est-ce qu'une « expression régulière » ?">

Un modèle d'expression régulière est composé de caractères pour lesquels vous souhaitez trouver une correspondance. Les modèles simples sont construits avec des caractères pour lesquels vous souhaitez trouver une correspondance directe. Lorsque la recherche d'une correspondance nécessite plus qu'une correspondance directe, vous pouvez inclure des caractères spéciaux dans le modèle.

**Exemples** :

| Expression **régulière** | **Description** |
| --- | --- |
| ^abc | Commence par abc |
| xyz$ | Se termine par xyz |
| ^abc.*xyz$ | Commence par abc et se termine par xyz |
| ^abc.*(?&lt;xyz)$ | Commence par abc et ne se termine pas par xyz. |
| ^([0-9]`{2}`) | Commence par 2 chiffres |
| \"example\_param\":\"[5\|6] | La valeur du paramètre spécifié commence par 5 ou 6. |
| ^.\{0\}$\|^\{\}$ | Est vide ou n'est que \{\} |

</Accordion>

<Accordion title="Pourquoi la source ou la condition ne s'affiche-t-elle pas comme valeur suggérée lorsque je la recherche ?">

Il y a deux raisons possibles :

* Assurez-vous que la ou les apps concernées sont sélectionnées. Si l'app n'est pas sélectionnée, les valeurs ne s'affichent pas dans les résultats de recherche.
* Les résultats s'affichent uniquement si la valeur que vous recherchez est apparue dans votre trafic au cours des 30 derniers jours.

Si la valeur n'apparaît pas comme résultat de recherche, vous pouvez saisir la valeur sous forme de texte libre et appuyer sur la touche Entrée de votre clavier.

</Accordion>

<Accordion title="Pourquoi mes options de source média incluent-elles uniquement les publicités Facebook et Twitter ?">

Les options du champ Sources de média sont affectées par votre sélection d'agence. Si l'agence « non transparente » est sélectionnée comme l'une des sources de trafic, aucune source de média ne s'affiche, à l'exception de Facebook Ads et Twitter, sur lesquels même les agences non transparentes doivent être transparentes.

**Remarque** : si votre règle s'applique à plusieurs apps, toute agence transparente dans certaines des apps sélectionnées, mais non transparente dans d'autres, est considérée comme non transparente. Cela signifie que vous ne pouvez pas sélectionner des sources média spécifiques autres que les publicités Facebook ou Twitter.

</Accordion>

<Accordion title="Est-il nécessaire d'avoir « et/ou » à la fois dans des conditions spécifiques et entre les groupes de conditions ?">

Cela dépend de votre cas d'utilisation. Parfois, les deux options permettent d'obtenir les mêmes résultats. D'autres fois, les deux options sont nécessaires.

Par exemple, si, aux États-Unis, vous prenez uniquement en charge les installations sous OS V10 ou version ultérieure, mais au Brésil, vous prenez en charge les versions V7 et ultérieures, vous aurez besoin d'une règle comme :

`{[Geo = US] and [OS version = 10]} OR {[Geo = Brazil] and [OS version = 7]}`

</Accordion>

<Accordion title="Les règles de validation bloquent-elles les clics ?">

Non. Les règles de validation peuvent bloquer les installations, bloquer l'attribution aux sources d'une installation (ce qui empêche la source média d'un clic/impression de recevoir l'attribution) ou bloquer les événements in-app. Cependant, aucune de ces options ne bloque le clic réel, et les indicateurs clés de performance du clic ne sont pas affectés par l'exécution des règles de validation.

</Accordion>

<Accordion title="En examinant les données brutes, je vois que les installations que je m'attendais à bloquer par des règles de validation ont une raison de blocage différente de mon nom de règle. Pourquoi ?">

Cela signifie que le blocage était dû au moteur <Anchor target="_blank" href="/marketers/fr/docs/protect360-raw-data-reports#protect360-blocked-reasons">Protect360</Anchor> et non à une règle de validation. Voir également [règles multiples](/docs/implement-validation-rules-to-prevent-fraud#multiple-rules).

</Accordion>

<Accordion title="Les règles existantes s'appliquent-elles automatiquement au trafic d'agence récemment intégré ?">

Cela dépend de vos paramètres **Source**, comme décrit dans le tableau ci-dessous.

Si la règle n'est pas appliquée automatiquement, vous devez la modifier :

* Modifiez le champ Agence de manière à ce qu'il contienne l'une des options suivantes : **trafic de l'agence et trafic hors agence**, ou sélectionnez l'agence en question.

<table><thead><tr><th><p>Réglage de la source</p></th><th><p>Sélection du champ de l'agence</p></th><th><p>La règle est-elle appliquée si elle a été créée avant toute intégration d'agence avec l'une de vos apps ?</p></th><th><p>La règle est-elle appliquée si elle a été créée après au moins une intégration d'agence avec l'une de vos apps ?</p></th></tr></thead><tbody><tr><td><p><span>Tout le trafic</span></p></td><td><p><span>N/R</span></p></td><td><p><span>Oui</span></p></td><td><p><span>Oui</span></p></td></tr><tr><td rowspan="3"> <br/><p><span>Non-organiques exclusivement</span></p></td><td><p><span>N/R</span></p></td><td><p><span>Non</span></p></td><td><p><span>N/R</span></p></td></tr><tr><td><p><span>Trafic des agences et non-agences</span></p></td><td><p><span>N/R</span></p></td><td><p><span>Oui</span></p></td></tr><tr><td><p><span>Trafic hors agences et/ou</span></p><p><span>d'agences spécifiques</span></p></td><td><p><span>N/R</span></p></td><td><p><span>Non</span></p></td></tr></tbody></table>

</Accordion>

<Accordion title="Particularités">

| Particularité | Description |
| --- | --- |
| Accès de l'équipe | L'admin du compte doit accorder aux membres d'équipe l'autorisation d'afficher, d'ajouter et de modifier les règles de validation. |
| Acquisition des utilisateurs | Les règles de validation s'appliquent aux installations, aux réinstallations et aux réattributions (lorsque l'app a été supprimée de l'appareil). Elles ne s'appliquent pas en cas de réengagement, c'est-à-dire lorsque l'app est toujours sur l'appareil. |
| Désactivation automatique des règles | Si vous créez des règles :<ul><li>en utilisant les sources ou les conditions Protect360, et que votre licence ou votre essai Protect360 expire, les règles sont automatiquement désactivées.</li><li>pour le trafic d'agences transparentes, et si l'une ou plusieurs des agences deviennent non transparentes, la règle est automatiquement désactivée.</li></ul> |

</Accordion>
