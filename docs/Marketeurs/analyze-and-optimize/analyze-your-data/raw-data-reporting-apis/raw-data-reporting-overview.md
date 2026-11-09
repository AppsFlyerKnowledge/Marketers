---
title: Vue d'ensemble du reporting des données brutes
metadata:
  keywords:
    - LTV
    - raw data
    - uninstalls
    - AFI
    - Advertisers
    - Agencies
    - Premium Feature
    - Gray
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Agencies
    - Raw Reports
  created_at: '2016-03-21T08:32:06Z'
  edited_at: '2023-11-12T12:52:09Z'
  id: 209680773
  locale: fr
  section: Raw data reporting/APIs
  section_id: 6550930711057
  url: https://support.appsflyer.com/hc/fr/articles/209680773
---
> **En bref :** les données au niveau des lignes (c'est à dire les données brutes) décrivent des événements déclenchés par les utilisateurs comme les installations, événements in-app, visites de sites web, installations bloquées par Protect360, revenus publicitaires et postbacks relatifs aux utilisateurs envoyés aux partenaires. Les rapports de données brutes sont disponibles via téléchargement, API et Data Locker.

<div id="raw-data-reportingtools-and-reports" />

## Le reporting des données brutes : outils et rapports

Les rapports de données brutes vous permettent d'analyser le comportement et le parcours des utilisateurs, de rapprocher les comptes de ad network et enfin d'enrichir vos systèmes CRM et BI. Grâce aux données brutes vous augmentez votre capacité d'analyse, d'optimisation et d'amélioration des performances.

Les rapports sont proposés via des outils de reporting. Les outils présentent chacun des caractéristiques adaptées à des cas d'utilisation précis. Par exemple, pour rapprocher un compte de ad network précis, vous téléchargez le rapport selon les besoins depuis la page Données d'exportation. Pour obtenir les données de performances utilisateur à charger dans vos systèmes BI, vous récupérez les données par programme en utilisant Data Locker ou Pull API.

<div id="tip" />

> 👍 **Astuce**
>
> Vous voulez en savoir plus sur vos données brutes ? Suivez cette <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7806/play/18629/viewing-and-understanding-your-raw-data">brève formation</Anchor> sur le portail d'apprentissage AppsFlyer.

<div id="reporting-tools-characteristics-and-features" />

<Accordion title="Outils de reporting : caractéristiques et fonctionnalités">

Les rapports sont proposés via différents outils de reporting détaillés dans cette section.

Attention :

* La plage de dates du rapport correspond à la date de l'activité (réelle) à laquelle l'événement a eu lieu. Ce qui est très différent des rapports agrégés dont la plage de dates est <Anchor target="_blank" href="/marketers/fr/docs/troubleshooting-discrepancies-in-appsflyer-dashboards-and-reports">basée sur la LTV</Anchor>.
* Descriptions des champs : cf <Anchor target="_blank" href="/marketers/fr/docs/raw-data-field-dictionary">dictionnaire des champs de données.</Anchor>

<div id="reporting-tools" />

#### Outil de reporting

<table><thead><tr><th>Outil</th><th>Description</th><th>App multiple/unique (1)</th><th>Capacité d'actualisation des données (2)</th><th>Intégré dans des scripts</th><th>Fuseau horaire</th><th>Devise</th></tr></thead><tbody><tr><td><a href="./raw-data-export-page" target="_blank">Page d'exportation des données brutes</a></td><td><ul><li>Télécharger le rapport depuis l'interface utilisateur</li><li>Format : fichier CSV</li></ul></td><td>Unique</td><td>Mise à jour en continu</td><td><strong><span>X</span></strong></td><td><p>Spécifique à l'app</p></td><td>Spécifique à l'app</td></tr><tr><td><a href="./pull-api-raw-data" target="_blank">API pull\*</a></td><td><ul><li>Télécharger le rapport à l'aide des appels d'API.</li><li>Format : fichiers CSV</li></ul></td><td>Unique</td><td>Mise à jour en continu</td><td><span>✓</span></td><td><ul><li>Sélectionnable</li><li>Par défaut : UTC</li></ul></td><td><ul><li>Sélectionnable</li><li>Par défaut : USD</li></ul></td></tr><tr><td> <a href="./data-locker-for-marketers" target="_blank">Data Locker</a> <strong><span>P</span></strong> </td><td><ul><li>Données envoyées vers un <a href="./data-locker-cloud-service-setup" target="_blank">compartiment dans le Cloud.</a> </li><li>Pas de volume maximum</li><li>Fenêtre de disponibilité des données : 14 jours.</li><li>Format : CSV ou Parquet</li></ul></td><td>Multiple</td><td>Mise à jour continue avec un décalage de plusieurs heures</td><td><span>✓</span></td><td>UTC</td><td>USD </td></tr><tr><td> <a href="./push-api-streaming-raw-data" target="_blank">API Push<span></span></a> <strong><span>P</span></strong> </td><td><ul><li>Données sur les parcours utilisateurs (installations, événements in-app, retargeting, SKAN) transmises à vos serveurs en temps réel.</li><li>Format : JSON ou params de requête</li></ul></td><td>Peut utiliser le même point de terminaison</td><td>Minutes après l'enregistrement de l'événement dans AppsFlyer</td><td><span>✓</span></td><td>UTC + spécifique à l'app</td><td>USD + spécifique à l'app</td></tr><tr><td> <a href="./conversion-data-payloads-and-scenarios" target="_blank">Données de conversion SDK</a> (3)</td><td><ul><li>Permet d'obtenir les données de conversion d'attribution dans l'app.</li><li>Format : JSON</li></ul></td><td>S/O</td><td> Temps réel &lt;5 secondes</td><td> <span>✓</span> </td><td>UTC</td><td>S/O</td></tr></tbody><tfoot><tr><td colspan="7"><p><strong>Remarques/abréviations :</strong><br/> (1) Prend en charge le multi apps<br/>(2) L'actualisation effective des données dépend du rapport, car certains rapports sont quotidiens.<br/>(3) Les données de conversion du SDK récupèrent les données d'attribution des utilisateurs en moins de 5 secondes à compter du premier lancement de l'application, ce qui en fait la méthode la moins précise.<br/><strong><span>(P) </span></strong><span>Fonctionnalité Premium</span><br/><a href="./report-generation-quotas-rate-limitations" target="_blank">(\*) Des limitations sur la génération des rapports s'appliquent</a></p></td></tr></tfoot></table>

<div id="tool-limitations" />

#### Limitations des outils

<table><thead><tr><th>Limitation </th><th>API Pull (\*)</th><th>API push</th><th>Data Locker</th><th>Données de conversion SDK</th></tr></thead><tbody><tr><td>Limitation des données</td><td>1 million de lignes par appel</td><td>S/O</td><td>S/O</td><td>S/O</td></tr><tr><td>Options de sélection des données</td><td>Sélectionner les types de données. Options de sélection de champs limitées</td><td>Sélectionnez les types de données, les champs et les données in-app</td><td>Sélectionnez les types de données, les champs et les données in-app</td><td>Non</td></tr><tr><td>Fenêtre de disponibilité des données</td><td>90 jours</td><td>S/O</td><td>14 jours </td><td>À vie (disponible dans le SDK)</td></tr><tr><td colspan="5"><p><a href="./report-generation-quotas-rate-limitations" target="_blank">(\*) Des limitations sur la génération des rapports s'appliquent</a></p></td></tr></tbody></table>

<div id="integration-considerations" />

#### Considérations d'intégration

| Contrepartie | API pull | API push | Data Locker | Données de conversion  <br />SDK |
| --- | --- | --- | --- | --- |
| Développement côté serveur | OPTIONNELLE | OBLIGATOIRE | OPTIONNELLE | OPTIONNELLE |
| Nécessite un traitement des données | OPTIONNELLE | OBLIGATOIRE | OPTIONNELLE | OPTIONNELLE |
| Risque de perte de données | Non | Oui, si les serveurs de réception sont en panne | Non | Faible, si la réponse du ad network est décalée |
| Coûts de traitement client-serveur | Aucun | Haut(e) | Faible | Aucun (à moins d'envoyer les données aux serveurs) |
| Maintenance client-serveur | Aucun | Haut(e) | Faible | Aucun (à moins d'envoyer les données aux serveurs) |
| Format des données | Fichier CSV | Params de requête ou JSON | CSV ou Parquet | JSON |

</Accordion>

Les enregistrements de données brutes propres à un contexte donné sont regroupés dans les rapports. Exemple : les installations non organiques, les événements organiques in-app. Pour faciliter la logique, les rapports sont regroupés de la manière suivante :

* **Parcours utilisateur  :** permet de suivre le parcours et l'engagement d'un utilisateur au sein de l'application.  
  Exemple  : clic > installation > événement in-app > désinstallation.
* **Fonctionnalité :** découle d'une fonctionnalité AppsFlyer donnée, mais ne fait pas partie du parcours principal de l'utilisateur. Exemple : les postbacks envoyés aux ad networks, les rapports sur la fraude et les règles de validation, les rapports sur les revenus publicitaires de niveau utilisateur.

<div id="report-fields" />

<Accordion title="Champs du rapport">

Le dictionnaire de champs des <Anchor target="_blank" href="/marketers/fr/docs/raw-data-field-dictionary">données brutes</Anchor> contient des champs qui concernent les rapports de parcours utilisateur, et certains champs liés aux rapports de fonctionnalités. Le principe est le suivant :

* **Parcours utilisateur :**
  * Doit avoir un ensemble de champs en commun.
  * Le champ est rempli en fonction du contexte du parcours. Exemple : les rapports non organiques contiennent la source média à qui l'on impute l'entrée de l'utilisateur.Les champs d'attribution des rapports organiques restent vides car il n'existe aucune source média.
* **Fonctionnalité** : contient un ensemble de champs propre, ou contient des champs de parcours utilisateur et des champs supplémentaires en lien avec la fonctionnalité. Exemple : les rapports SKAdNetwork ont une liste de champs unique, tandis que les rapports de postback contiennent des champs de parcours utilisateur ET des champs supplémentaires propres à l'envoi de postback aux partenaires.

**Conseil**! La meilleure façon de vous familiariser avec les rapports est de les parcourir. Vous pouvez télécharger vos rapports sur la <Anchor target="_blank" href="/marketers/fr/docs/raw-data-export-page">page Données d'exportation</Anchor>.

Pour rendre les choses plus claires, les champs du parcours utilisateur sont divisés en groupes liés au contexte.

<div id="user-journey-raw-data-field-groups" />

#### Groupes de champs de données brutes du parcours utilisateur

| Groupe du champ | Concerne les utilisateurs organiques | Exemples de champs |
| --- | --- | --- |
| Téléchargement | Oui | ID de l'app, nom de l'app, version de l'app, version du SDK, ATT |
| Attribution | Non, sauf pour l'heure d'installation | Heure d'installation, heure de touch attribué, source média, campagne, adset, publicité, partenaire, type de conversion de retargeting |
| Attribution des contributeurs | Non | Partenaire contributeur, type de correspondance |
| Infos appareil | Oui | ID publicitaire, GAID, OAID, type d'appareil, ID utilisateur du client |
| Localisation de l'appareil | Oui | Adresse IP, localité, pays |
| Événement | Oui | Champs remplis dans les rapports d'événements in-app :<br /><br />Nom de l'événement, valeur de l'événement, revenu de l'événement |

</Accordion>

<div id="user-journey-reports" />

## Rapports de parcours utilisateur

<Image align="center" alt="Raw_data_-_User_acquisition_.png" src="https://files.readme.io/319da2a6a5567d6cfe4a74337279e67e0bdcdb063e62ecacde5eb4293a98a1a2-36317497158033.png" />

<div id="user-journey-basics" />

<Accordion title="Principes de base du parcours utilisateur">

Les rapports de parcours utilisateur contiennent les données en lien avec les événements survenus pendant la durée vie d'un utilisateur. Les données sont divisées en rapports en fonction de :

* La source de l'utilisateur : organique ou non organique
* Contexte du parcours :
  * Engagement avec les publicités avant l'installation de l'app (impressions et clics)
  * Acquisition
  * Retargeting

**Les rapports d'acquisition d'utilisateurs (UA)** **contiennent :**

* Les impressions et les clics générés avant l'installation par tout *potentiel* utilisateur qui interagit avec une publicité.
* Événement d'installation.
* Les événements in-app produits par l'utilisateur qui en découlent.

**Les rapports de retargeting contiennent :**

* Les impressions et les clics qui se produisent lorsque l'utilisateur est reciblé.
* Événements de conversion : soit un réengagement soit une réattribution.
* Événements in-app réalisés dans le cadre du réengagement qui en découlent. N'oubliez pas :
  * Les données de retargeting sont toujours non organiques.
  * Les événements in-app de retargeting se trouvent à la fois dans les rapports UA et les rapports d'événements in-app de retargeting. Voir le principe de la <Anchor target="_blank" href="/marketers/fr/docs/resolve-retargeting-double-attribution">double-attribution de retargeting</Anchor>.

    <Image align="center" alt="Raw_data_-_Retargeting.png" src="https://files.readme.io/717f6e43ca3b224ead9e3e1c5f9b277d2f21dbc1fe3b4c217ebf4bdbc539bab7-36317470735249.png" />

Pour suivre un parcours utilisateur, vous devez cumuler les rapports en lien avec les parties du parcours qui vous intéressent, par exemple : les installations et les événements in-app. Une fois fait, vous n'avez qu'à trier le rapport en utilisant l'ID AppsFlyer, l'heure de l'événement et le type de rapport. Le résultat correspond à l'ensemble des événements pour un utilisateur donné au fil du temps, en d'autres termes le parcours utilisateur.

</Accordion>

<div id="user-journey-report-availability" />

<Accordion title="Disponibilité du rapport du parcours utilisateur">

* La disponibilité des rapports dépend de votre forfait d'abonnement.
* Les rapports peuvent inclure des utilisateurs organiques, des utilisateurs non organiques ou les deux, comme indiqué.
* Les politiques de rétention s'appliquent aux rapports données brutes historiques et dépendent de l'outil de reporting et de l'origine des données brutes. En général, les données sont disponibles pour les 90 derniers jours. **Important** ! Les politiques de rétention ne s'appliquent pas aux données agrégées.

<div id="user-journey-reports-1" />

#### Rapports de parcours utilisateur

<table><thead><tr><th>Catégorie</th><th>Propre à Data Locker</th><th>Sujet du rapport</th><th>Trafic</th><th>Non organique</th></tr></thead><tbody><tr><td>Acquisition des utilisateurs</td><td><span>✓</span></td><td>Clics</td><td colspan="2">S/O</td></tr><tr><td>Retargeting</td><td><span>✓</span></td><td>Clics en provenance des campagnes de retargeting </td><td colspan="2">Retargeting non organique uniquement</td></tr><tr><td>Acquisition des utilisateurs</td><td><span>✓</span></td><td>Impressions</td><td colspan="2">S/O</td></tr><tr><td>Retargeting</td><td><span>✓</span></td><td>Impressions des campagnes de retargeting</td><td colspan="2">Retargeting non organique uniquement</td></tr><tr><td>Acquisition des utilisateurs</td><td>-</td><td>Installations </td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Acquisition des utilisateurs</td><td>-</td><td>Évènements in-app </td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Acquisition des utilisateurs</td><td>-</td><td>Revenus publicitaires attribués</td><td>-</td><td><span>✓</span></td></tr><tr><td>Acquisition des utilisateurs</td><td>-</td><td>Revenus publicitaires organiques</td><td><span>✓</span></td><td>-</td></tr><tr><td>Retargeting</td><td>-</td><td>Revenus publicitaires de retargeting</td><td colspan="2">Retargeting non organique uniquement</td></tr><tr><td>Retargeting</td><td>-</td><td>Conversions de retargeting (réengagements et réattributions)</td><td colspan="2">Retargeting non organique uniquement</td></tr><tr><td>Retargeting</td><td>-</td><td>Événements in-app de retargeting (réengagements et réattributions)</td><td colspan="2">Retargeting non organique uniquement</td></tr><tr><td>Retargeting</td><td> <span>✓</span> </td><td>Sessions de retargeting (réengagements et réattributions)</td><td colspan="2">Retargeting non organique uniquement</td></tr><tr><td>Acquisition des utilisateurs</td><td> <span>✓</span> </td><td>Sessions</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Acquisition des utilisateurs</td><td>-</td><td>Désinstallations non organiques </td><td>-</td><td><span>✓</span></td></tr><tr><td>Acquisition des utilisateurs</td><td>-</td><td>Désinstallations organiques</td><td><span>✓</span></td><td>-</td></tr><tr><td>Acquisition des utilisateurs</td><td><span>✓</span></td><td>Engagements multiplateformes</td><td><span>✓</span></td><td><span>✓</span></td></tr></tbody></table>

</Accordion>

<div id="user-journey-report-descriptions" />

<Accordion title="Description des rapports du parcours utilisateur">

<div id="clicks-and-impressions" />

#### Clics et impressions

| Rapport | Caractéristiques |
| --- | --- |
| Contexte | Un utilisateur s'engage dans une campagne et clique sur une publicité, ou il la visionne. |
| Caractéristiques | Les rapports contiennent un enregistrement du lien d'attribution et des en-têtes HTTP présents au moment où un utilisateur clique ou <Anchor target="_blank" href="/marketers/fr/docs/measure-view-through-engagements#set-impression-links">visionne</Anchor> une publicité. |
| Cas d'utilisation | <ul><li>Optimisez les campagnes qui ne conduisent pas à l'ouverture d'une app (installation, réattribution, réengagement).</li><li>Reciblez ces utilisateurs avec différentes campagnes.</li></ul> |
| Exemple de rapport | <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRcNRnKgPP5ZRL51o3b9PDhbFv6VFG7xe9xHqCsIC7HwqO2ERLV5dh4bS7pr-WONxpUXvsCc64eTzzN/pub?gid=1036692270&single=true&output=csv">Clics</Anchor> |
| Remarques | Données SRN non disponibles. |
| Utilisateurs restreints | Dans certains cas, en raison des règles de confidentialité, les données d'impression et de clic sont soit restreintes (elles n'ont pas d'identifiant utilisateur), soit non disponibles. La disponibilité dépend de la source média et de la plate-forme. |

<div id="installs-and-retargeting-conversions" />

#### Installations et conversions de retargeting

<table><thead><tr><th rowspan="2">Nom de rapport </th><th rowspan="2"><p>Acquisition d'utilisateur : installations</p></th><th rowspan="2">Retargeting : conversions</th></tr></thead><tbody><tr><td> <br/>Contexte</td><td><p>Lorsqu'un utilisateur ouvre une app pour la première fois.</p></td><td><p>Lorsqu'un utilisateur s'engage avec une publicité de retargeting, puis finit par ouvrir l'app. Une conversion de retargeting est un réengagement ou une réattribution.</p> Voir notre <a href="./retargeting-attribution-guide#retargeting-reports-and-raw-data" target="_blank">guide d'attribution du retargeting</a>. </td></tr><tr><td>CAS D'UTILISATION</td><td><ul><li>Générez des rapports agrégés en utilisant des champs non disponibles via les outils d'analyse d'AppsFlyer.</li><li>Cumulez avec d'autres rapports pour une analyse transversale avancée.</li><li>Analysez les performances à travers différentes dimensions comme les localités, zones métropolitaines, etc.</li><li>Segmentez les utilisateurs en fonction des pays, localités et langues à des fins de retargeting.</li><li>Obtenez des ID d'appareil utilisateur à des fins de retargeting.</li></ul></td><td>Identique aux installations.</td></tr><tr><td>Organique ou non organique</td><td><ul><li> <strong>Non-organique :</strong> les groupes de champs d'attribution et d'attribution des contributeurs sont renseignés.</li><li> <strong>Organique :</strong> le champ source média est soit vide, soit null, soit organique. Gardez ces éléments à l'esprit lorsque vous chargez les données dans votre système.</li></ul></td><td>Ne s'applique pas</td></tr><tr><td>Exemple de rapport</td><td><a href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRcNRnKgPP5ZRL51o3b9PDhbFv6VFG7xe9xHqCsIC7HwqO2ERLV5dh4bS7pr-WONxpUXvsCc64eTzzN/pub?gid=0&amp;single=true&amp;output=csv" target="_blank">d'installations</a></td><td>Le rapport des conversions de retargeting possède la même structure que le rapport des installations. Certains champs sont renseignés dans le cadre du retargeting. Cf <a href="./retargeting-attribution-guide#retargeting-reports-and-raw-data" target="_blank">retargeting des données brutes</a>.</td></tr></tbody></table>

<div id="in-app-events" />

#### Évènement in-app

<Table>
  <thead>
    <tr>
      <th>
        Rapport
      </th>
      <th>
        Caractéristiques
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="report-context"></span>
        Contexte du rapport
      </td>
      <td>
        Liste chronologique des actions effectuées par les utilisateurs après l'attribution (installation, réattribution ou réengagement)
      </td>
    </tr>
    <tr>
      <td><span id="characteristics"></span>
        Caractéristiques
      </td>
      <td>
        * La structure et les champs du rapport sont identiques à ceux des rapports d'installation.
        * Les champs dédiés décrivent l'événement. Il s'agit notamment du nom de l'événement, de sa valeur, son revenu et son heure.
      </td>
    </tr>
    <tr>
      <td><span id="use-case"></span>
        Cas d'utilisation
      </td>
      <td>
        Le rapport vous permet de :

        * Obtenir des informations en observant le parcours utilisateur pendant la durée vie de l'utilisateur
        * Cumulez les données brutes d'installation et des événements in-app pour suivre l'ensemble du parcours utilisateur.
      </td>
    </tr>
    <tr>
      <td><span id="event-values"></span>
        Valeurs de l'événement
      </td>
      <td>
        **Champ valeur de l'événement**

        Le champ valeur de l'événement contient toutes les données relatives à l'événement dans un JSON. Vous pouvez les charger dans votre système BI pour obtenir une analyse plus précise.

        **Astuce**Vous pouvez utiliser <Anchor target="_blank" href="https://docs.microsoft.com/en-us/power-query/parse-json-xml">Power Query dans Microsoft Excel</Anchor> pour analyser les paramètres d'événement à partir des chaînes de texte JSON.

        ```json
        {"af_level":"10","af_user_journey":"3387","arena":"7","char_type":"paladin"}
        ```

        **Reporting des revenus**

        Dans AppsFlyer, les données des revenus et du ROI proviennent du af\_revenue envoyé dans les événements.

        Lorsque le paramètre af\_revenue est envoyé dans un événement in-app, AppsFlyer l'utilise pour renseigner le champ revenu de l'événement. C'est ce champ que AppsFlyer utilise pour mettre à jour le tableau de bord et les rapports agrégés.

        Attention ! N'utilisez le paramètre af\_revenue qu'avec les événements in-app qui décrivent **les revenus réellement générés.** Pour tout autre événement impliquant des revenus, mais qui n'est pas conclu (ex : add\_to\_cart), vous devez utiliser des paramètres différents (comme af\_price)
      </td>
    </tr>
    <tr>
      <td><span id="example-report"></span>
        Exemple de rapport
      </td>
      <td>
        [Évènement in-app](https://docs.google.com/spreadsheets/d/e/2PACX-1vRcNRnKgPP5ZRL51o3b9PDhbFv6VFG7xe9xHqCsIC7HwqO2ERLV5dh4bS7pr-WONxpUXvsCc64eTzzN/pub?gid=819556999&single=true&output=csv)
      </td>
    </tr>
    <tr>
      <td><span id="remarks"></span>
        Remarques
      </td>
      <td>
        * Les événements in-app de retargeting sont <Anchor target="_blank" href="/marketers/fr/docs/resolve-retargeting-double-attribution">enregistrés deux fois</Anchor>, à la fois dans les rapports UA et les rapports de données brutes d'événements in-app de retargeting.
        * Les événements in-app n'incluent pas l'événement de lancement (af\_app\_opened). Cette option est disponible dans le rapport de données brutes des <Anchor target="_blank" href="/marketers/fr/docs/measure-sessions">sessions</Anchor>.
        * Emplacement geo : provient de l'adresse IP utilisateur au moment où l'événement se produit.
      </td>
    </tr>
  </tbody>
</Table>

#### Sessions

| Rapport | Caractéristiques |
| --- | --- |
| Contexte | Lorsque l'utilisateur ouvre l'app, un événement de session est envoyé à AppsFlyer. L'événement est enregistré uniquement si la <Anchor target="_blank" href="/marketers/fr/docs/measure-sessions">durée entre les sessions</Anchor> dépasse le seuil minimum fixé. |
| Caractéristiques | La structure du rapport est identique à celle des rapports d'événements in-app. Les sessions (événements de session) s'affichent dans un rapport séparé à cause du nombre important de ces événements. |
| Cas d'utilisation | Comprendre l'engagement des utilisateurs dans l'application. |
| Exemple de rapport | Le rapport des sessions est identique au rapport des événements in-app. Remarque : dans les données brutes, les sessions portent le nom d'événement *launch*. |

<div id="uninstalls" />

#### Désinstallations

| Rapport | Caractéristiques |
| --- | --- |
| Contexte | Enregistrement des utilisateurs qui désinstallent l'app. |
| Caractéristiques | <ul><li>Ce rapport est mis à jour quotidiennement et non en continu, c'est également le cas pour les autres rapports de parcours utilisateur.</li><li>Dans le rapport, l'heure de l'événement correspond à l'heure à laquelle AppsFlyer détermine que l'app a été désinstallée, et non à l'heure de la désinstallation en elle-même. Cf Mesure des désinstallations.</li></ul> |
| Champs disponibles | <ul><li>Si l'utilisateur est issu d'une source média non organique, les champs source média sont renseignés.</li><li>Notez que l'événement de désinstallation est généré par les serveurs AppsFlyer seulement après avoir déterminé que l'utilisateur a effectué la désinstallation. Ce qui explique que de nombreux champs ne sont pas renseignés.</li><li>Les identifiants utilisateur disponibles sont ceux enregistrés au moment de l'installation. Le CUID n'est jamais disponible.</li><li>Les champs géo sont remplis d'après la localisation de l'utilisateur à l'heure de l'engagement avec la source média (par clic ou impression). Si la localisation de l'engagement n'est pas disponible, c'est celle associée à l'événement d'installation qui est utilisée.</li></ul> |
| Exemple de rapport | Remarque sur les <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vRcNRnKgPP5ZRL51o3b9PDhbFv6VFG7xe9xHqCsIC7HwqO2ERLV5dh4bS7pr-WONxpUXvsCc64eTzzN/pub?gid=1558773473&single=true&output=csv">désinstallations</Anchor> ! Dans notre exemple, par souci de clarté, la ligne 2 indique les champs qui sont renseignés si les données disponibles le permettent. |
| CAS D'UTILISATION | <ul><li>Analyser l'événement de désinstallation, les caractéristiques de l'appareil et de l'utilisateur</li><li>Créer une audience d'évènement de désinstallation pour le retargeting.</li></ul> |

</Accordion>

<div id="user-journey-report-availability-per-tool" />

<Accordion title="Disponibilité du rapport de parcours utilisateur selon les outils">

<div id="ad-engagement-report-by-tool" />

#### Rapport d'engagement publicitaire selon les outils

<table><tbody><tr><th>Rapport</th><th>Données d'exportation</th><th>API pull</th><th>Data Locker</th><th>API push</th><th>Données de conversion<br/>SDK</th></tr><tr><td>Impressions (1)</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>Clics (1)</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td colspan="6">(1) Les données sur les clics et les impressions sont fournies par les non-SRN. Les SRN ne rendent pas ces données disponibles.</td></tr></tbody></table>

<div id="user-acquisition-reports-by-tool" />

#### Rapports d'acquisition d'utilisateurs par outil

| Rapport | Données d'exportation | API pull | Data Locker | API push | Données de conversion du SDK |
| --- | --- | --- | --- | --- | --- |
| d'installations | ✓ | ✓ | ✓ | ✓ | ✓ |
| Sessions | - | - | ✓ | - | - |
| Évènement in-app | ✓ | ✓ | ✓ | ✓ | - |
| Désinstallations | ✓ | ✓ | ✓ | - | - |

<div id="retargeting-raw-data-reports-by-tool" />

#### Rapports de données brutes de retargeting par outil

<table><thead><tr><th>Rapport</th><th>Données d'exportation</th><th>API pull</th><th>Data Locker</th><th>API push</th><th>Données de conversion du SDK</th></tr></thead><tbody><tr><td>Clics (1)</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>Conversions (réattributions + réengagements)</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Impressions (1)</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>Sessions</td><td>-</td><td>-</td><td><span>✓</span></td><td>-</td><td>-</td></tr><tr><td>Évènement in-app</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td>-</td></tr></tbody><tbody><tr><td colspan="6"><p>(1) Les données sur les clics et les impressions sont fournies par les non-SRN. Les SRN ne rendent pas ces données disponibles.</p></td></tr></tbody></table>

</Accordion>

<div id="faq" />

<Accordion title="FAQ">

| Détails |
| --- |
| **Pourquoi les données brutes de Meta ads sont-elles manquantes ?**<br /><br />Par défaut, les données brutes de Meta ads sont attribuées à la <Anchor target="_blank" href="/marketers/fr/docs/about-raw-data-identifier-restrictions">source média qui est limitée.</Anchor> Voir <Anchor target="_blank" href="/marketers/fr/docs/meta-ads-integration-setup#userlevel-data">données Meta ads au niveau de l'utilisateur.</Anchor> |
| **Quelle différence existe-t-il entre les horodatages ?**<br /><br />Les horodatages sont communs à tous les rapports. Vous pouvez ainsi combiner différents rapports.<br /><br />Les horodatages suivants sont appliqués :<ul><li>**Heure du touch attribué**: l'heure à laquelle l'utilisateur s'est engagé avec une publicité.</li><li>**Heure** **d'installation** : heure à laquelle l'app est lancée pour la première fois.</li><li>**Heure de l'événement**: l'heure où l'événement se produit.</li></ul>Important :<ul><li>Dans les rapports d'installation, les heures d'installation et d'événement sont les mêmes.</li><li>Dans les rapports d'événements in-app, les heures d'installation et d'événement diffèrent. L'écart entre les deux peut indiquer le temps écoulé entre le lancement de l'app et l'engagement de l'utilisateur avec l'app.</li></ul> |
| **Quel est le rôle du champ contributeur ?**<br /><br />Le champ contributeur recense les sources média du contributeur. On l'appelle parfois <Anchor target="_blank" href="/marketers/fr/docs/measure-assisted-installs#le-reporting-des-installations-assistées">installations assistées</Anchor>. Dans Protect360, il est également utilisé pour corriger l'<Anchor target="_blank" href="/marketers/fr/docs/protect360-raw-data-reports#correction-de-lattribution-des-installations-détournées">attribution des installations détournées.</Anchor> |
| **Qu'est-ce que le champ mots-clés ? Pourquoi n'est-il pas disponible pour toutes les installations non organiques ?**<br /><br />Les installations attribuées à Google Ads ou Apple Search Ads, peuvent contenir les mots-clés (ou l'ID de mot-clé) associés à la publicité qui a généré l'installation. |

</Accordion>

<div id="install-report-tips" />

<Accordion title="Conseils sur les rapports d'installations">

**Comprendre le parcours utilisateur**

Le parcours utilisateur est constitué d'une série d'étapes que l'utilisateur traverse avant d'atteindre un objectif donné (l'achat d'un produit ou la réservation d'un vol par exemple). Analyser le parcours d'un utilisateur vous permet donc de voir les actions de l'utilisateur au sein de l'app, son niveau d'activité et la valeur qu'il produit sur une période donnée.

Vous pouvez identifier et mettre en évidence les parcours utilisateur à l'aide de l'ID AppsFlyer. L'ID est généré pour chaque installation d'app sur un appareil. L'ID reste le même tout au long du cycle vie de l'utilisateur (de l'installation à la désinstallation). L'ID ne disparait pas si l'utilisateur réinitialise l'ID de son appareil.

Les rapports d'installations et ceux des événements in-app ayant la même structure, ils peuvent être fusionnés en un seul rapport. Dans le rapport fusionné, vous pouvez agréger et filtrer en utilisant l'ID AppsFlyer et l'ID utilisateur du client (si disponible) dans le but d'analyser les parcours utilisateur.

<div id="engaged-userstrong" />

> 📄 **Un utilisateur engagé - fort**
>
> * Un utilisateur installe l'app le 20 août à 09h31.
> * Le rapport fusionné indique qu'il a effectué des achats le 20 août à 10h31, le 22 août à 15h22 et le 25 août à 16h47.
> * Nous en concluons que l'utilisateur est un utilisateur engagé. Il a effectué un achat une heure après avoir lancé l'application, et a continué ses achats les jours qui ont suivi.
>
> #### <span id="engaged-userweak"></span>Utilisateur engagé - faible
>
> * Un utilisateur installe l'app le 30 juillet. Le rapport fusionné indique qu'il a ajouté un article à son panier le 15 août, mais qu'aucun événement d'achat n'a suivi.
> * Vous pouvez partir du principe que l'utilisateur hésite à effectuer son achat, et ainsi le recibler avec les articles qu'il a ajoutés au panier.
>
> #### <span id="analyzing-the-user-journey-for-campaign-optimization"></span>Analyser le parcours utilisateur pour optimiser vos campagnes
>
> * Le manager de l'acquisition d'utilisateurs (UA) d'une app de voyage télécharge les rapports d'installation et d'événements in-app, puis il les fusionne.
> * Ensuite, pour consulter les parcours utilisateur dans l'app, il filtre ou agrège les données avec l'ID AppsFlyer.
> * Il remarque qu'un certain utilisateur, identifié par son ID AppsFlyer, a téléchargé l'app il y a 12 mois et a réservé un vol quelques jours plus tard.
> * Par la suite, l'utilisateur a consulté des offres de vols mais n'a effectué aucune réservation. En poursuivant sa recherche, le manager UA découvre d'autres d'utilisateurs qui ont suivi le même modèle, et continue son analyse.
> * Il constate que ces utilisateurs proviennent en majorité de la **publicité A** de la **campagne B** diffusée via la **source média C**. Le manager UA comprend que la publicité et la campagne ont ciblé des utilisateurs souhaitant voyager vers une destination spécifique.
> * En analysant le parcours utilisateur, il a pu découvrir que la campagne était trop ciblée, et que les utilisateurs n'étaient pas suffisamment investis dans l'application.

</Accordion>

<div id="feature-reports" />

## Rapports de fonctionnalités

Rapports relatifs aux fonctionnalités supplémentaires proposées sur la plateforme

* <Anchor target="_blank" href="/marketers/fr/docs/roi360-guide-ad-revenue-attribution#ad-revenue-raw-data">Revenus publicitaires</Anchor>
* <Anchor target="_blank" href="/marketers/fr/docs/incrementality-for-remarketing-overview#rapports-de-données-brutes">Incrementality</Anchor>
* <Anchor target="_blank" href="/marketers/fr/docs/skan-raw-data-reports">SKAdNetwork</Anchor>

<div id="postbacks" />

<Accordion title="Les postbacks">

Utilisez les rapports de postback pour examiner les copies des données envoyées à un ad network. Par exemple, pour analyser les écarts ou anomalies. Ces rapports sont établis à titre informatif et ne sont pas obligatoires pour l'intégration aux ad networks.

* Le rapport contient :
  * Copies des postbacks envoyées à la source média attribuée.
  * Des <Anchor target="_blank" href="/marketers/fr/docs/raw-data-field-dictionary">champs de données brutes</Anchor> et champs supplémentaires tels qu'indiqués dans cette section.
* Le rapport ne contient pas :
  * Les installations SRN.
  * Événements in-app relatifs à Meta ads, Twitter et Apple Search Ads.
  * Postbacks de partenaires non attribués. Cf <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#g">événements attribués à tout partenaire ou organique</Anchor>.
  * Utilisateurs organiques. Cf <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#f">à propos des installations organiques.</Anchor>
  * Campagnes d'installation CPA ayant désactivé les postbacks d'installation.
* Depuis mars 2021, les champs sont renseignés d'après les paramètres de confidentialité avancée du réseau. En d'autres termes, si la confidentialité avancée est activée, certains champs (comme les identifiants utilisateur) ne sont pas inclus. Cf <Anchor target="_blank" href="/partners/fr/docs/advanced-privacy-guide-postback-macros-for-ad-networks#advanced-privacy-postback-specification">Spécifications caractéristiques des postbacks de confidentialité avancée pour les réseaux publicitaires.</Anchor>
* <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTs4MUZTBKRQF24n-T8JM1L6EhU4TayYneX6MB5HjM9iwnrQtX8tlPLBA-J7zmqDcJqYTCpRxhStdGg/pub?output=xlsx">URI pour les rapports de postback via API Pull</Anchor>

<div id="postback-reports-available-via-the-export-data-page-and-pull-api" />

#### Rapports de postback (disponibles via la page Données d'exportation et API Pull)

| Sujet du rapport | Événements envoyés à la source média attribuée |
| --- | --- |
| d'installations | installations non organiques (UA) |
| Évènement in-app | Les événements in-app non organiques |
| Postbacks de conversion de retargeting | Retargeting (réengagement et réattribution) |
| événements in-app de retargeting | Les événements in-app de retargeting |

<div id="additional-fields-in-postback-reports" />

#### Champs supplémentaires dans les rapports de postback

| Champ | Remarques |
| --- | --- |
| URL de postback | Certaines valeurs, comme les revenus, peuvent ne pas apparaître dans le champ approprié, mais ces données seront toujours consultables dans l'**URL du postback.** |
| Méthode de postback |  |
| Code de réponse HTTP de postback | 200 : confirme que le postback a été reçu par l'ad network. |
| Message d'erreur de postback |  |

</Accordion>

<div id="protect360-fraud-and-validation-rules" />

<Accordion title="Fraude Protect360 et règles de validation">

* Cf <Anchor target="_blank" href="/marketers/fr/docs/protect360-raw-data-reports">Protect360</Anchor> et rapports de données brutes des <Anchor target="_blank" href="/marketers/fr/docs/implement-validation-rules-to-prevent-fraud#outcomes">règles de validation</Anchor>
* Les ad networks et les agences ont besoin d'une <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#access-protect360-dashboard-raw-data">autorisation</Anchor> d'annonceur pour accéder aux rapports Protect360 et aux règles de validation.

**Pour accorder à un partenaire intégré la permission d'accéder à Protect360 :**

1. Allez dans **Configuration** > **Intégrations actives**.
2. Sélectionnez le partenaire intégré.
3. Dans l'onglet **Autorisations**, activez l'option **Accès à votre tableau de bord Protect360 et aux données brutes via API**.
4. Pour donner accès au dashboard des événements in-app (CPA), activez **Accès aux données agrégées des événements in-app**.

</Accordion>

<div id="see-also" />

> 📄 **À consulter également**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/aggregated-and-analytics-reporting-overview">Rapports agrégés et analyses</Anchor>

<div data-zendesk-anchors="raw-data-reporting%E2%80%94tools-and-reports=le-reporting-des-donn%C3%A9es-brutes--outils-et-rapports h_01HE7SRDXQ9TR0CRB2JC9XCQE2=le-reporting-des-donn%C3%A9es-brutes--outils-et-rapports h_01HE7SRDXQQJFMV9EJKPY34D00=astuce reporting-tools%E2%80%94characteristics-and-features=reporting-tools-characteristics-and-features h_01HE7SRDXQFJGMY05K1SV4TF63=reporting-tools-characteristics-and-features reporting-tools=outil-de-reporting h_01HE7SRDXQ647XRQ8QVMPGH43B=outil-de-reporting tool-limitations=limitations-des-outils h_01HE7SRDXQWQAKR0G6CNKC5AMT=limitations-des-outils integration-considerations=consid%C3%A9rations-dint%C3%A9gration h_01HE7SRDXQN3HSMGAPBAX9S3MB=consid%C3%A9rations-dint%C3%A9gration h_01HE7SRDXQRPD8MHC8M5916HTQ=report-fields user-journey-raw-data-field-groups=groupes-de-champs-de-donn%C3%A9es-brutes-du-parcours-utilisateur h_01HE7SRDXQMGQEG1QWGWEESQER=groupes-de-champs-de-donn%C3%A9es-brutes-du-parcours-utilisateur user-journey-reports=rapports-de-parcours-utilisateur h_01HE7SRDXQZ50WMKCMYHZM7D92=rapports-de-parcours-utilisateur h_01HE7SRDXQFN0P9QK8SKAZKVKP=user-journey-basics h_01HE7SRDXRS2B12Z67MYMH0QN9=user-journey-report-availability user-journey-reports::d286e1f5=rapports-de-parcours-utilisateur-1 h_01HE7SRDXR7YQGWN4FNDXMNMX8=rapports-de-parcours-utilisateur-1 h_01HE7SRDXRK6G27SDFK3CGDCRC=user-journey-report-descriptions clicks-and-impressions=clics-et-impressions h_01HE7SRDXRC9YKZ0P9ED0218SJ=clics-et-impressions installs-and-retargeting-conversions=installations-et-conversions-de-retargeting h_01HE7SRDXRN60XE5BSDQY28N71=installations-et-conversions-de-retargeting inapp-events=%C3%A9v%C3%A8nement-in-app h_01HE7SRDXR3ZT39EDNW4MVZZTX=%C3%A9v%C3%A8nement-in-app h_01HE7SRDXRY05XQCMZE6YPXGWQ=sessions uninstalls=d%C3%A9sinstallations h_01HE7SRDXRA7ESDD4ME51WWBPR=d%C3%A9sinstallations h_01HE7SRDXRZYNFGK4CNP4VPAE0=user-journey-report-availability-per-tool ad-engagement-report-by-tool=rapport-dengagement-publicitaire-selon-les-outils h_01HE7SRDXR171M74HMQBZJ2E8R=rapport-dengagement-publicitaire-selon-les-outils user-acquisition-reports-by-tool=rapports-dacquisition-dutilisateurs-par-outil h_01HE7SRDXRMGEP5QB452ZKQ8X7=rapports-dacquisition-dutilisateurs-par-outil retargeting-raw-data-reports-by-tool=rapports-de-donn%C3%A9es-brutes-de-retargeting-par-outil h_01HE7SRDXRXR4J3HTMYW2P233Y=rapports-de-donn%C3%A9es-brutes-de-retargeting-par-outil h_01HE7SRDXRWW3JKNESSN2QA4DV=faq h_01HE7SRDXR61K28JGA8944D6HV=install-report-tips h_01HE7SRDXRKFR2WYGNF317CTRX=rapports-de-donn%C3%A9es-brutes-de-retargeting-par-outil engaged-user%E2%80%94strong=un-utilisateur-engag%C3%A9---fort h_01HE7SRDXRW0CWHGQV75VF66DC=un-utilisateur-engag%C3%A9---fort engaged-user%E2%80%94weak=utilisateur-engag%C3%A9---faible h_01HE7SRDXRNMDZEJQ32665T14F=utilisateur-engag%C3%A9---faible analyzing-the-user-journey-for-campaign-optimization=analyser-le-parcours-utilisateur-pour-optimiser-vos-campagnes h_01HE7SRDXRRET0YN4Q8WYMENSR=analyser-le-parcours-utilisateur-pour-optimiser-vos-campagnes feature-reports=rapports-de-fonctionnalit%C3%A9s h_01HE7SRDXSVAHKBYQK0C71K6AR=rapports-de-fonctionnalit%C3%A9s h_01HE7SRDXSFWMVY61NBYFQ4XSM=postbacks postback-reports-available-via-the-export-data-page-and-pull-api=rapports-de-postback-disponibles-via-la-page-donn%C3%A9es-dexportation-et-api-pull h_01HE7SRDXS6T4M4CRQN0ZTJETR=rapports-de-postback-disponibles-via-la-page-donn%C3%A9es-dexportation-et-api-pull additional-fields-in-postback-reports=champs-suppl%C3%A9mentaires-dans-les-rapports-de-postback h_01HE7SRDXSYBDG0H2QEYBFWSRH=champs-suppl%C3%A9mentaires-dans-les-rapports-de-postback h_01HE7SRDXS8K4MB76WVBCBHASQ=protect360-fraud-and-validation-rules h_01HE7ST20N8ZBFNY2QXW5G44A1=%C3%A0-consulter-%C3%A9galement" />
