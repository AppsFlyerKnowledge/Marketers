---
title: Tableau de bord général SKAdNetwork (SKAN) par AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2020-07-25T21:27:38Z'
  edited_at: '2024-09-12T12:26:10Z'
  id: 360011307357
  locale: fr
  section: Dashboards
  section_id: 6550925337873
  url: https://support.appsflyer.com/hc/fr/articles/360011307357
---
> **En bref :** Le tableau de bord SKAdNetwork (SKAN) contient les résultats de campagne transmis par les postbacks SKAN iOS, ainsi que différents points de données des premières fenêtres de mesure de l’utilisateur. Les mesures modélisées qui prennent en compte les conversions nulles sont également présentées. Les données s’affichent en fonction de la date de l’installation ou de celle d’arrivée du postback.

![SKAdHeadling8_us-en.png](https://files.readme.io/72c2eb452741cbd77c5828197f827f238c71c5097b8703528fa180dcafe2364c-360011831017.png)

<div id="dashboard-principles" />

## Les bases du tableau de bord

Le tableau de bord contient les données de performance des campagnes SKAN, il se base sur les principes suivants :

* Sachez que Apple, en raison de l’application <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork">du seuil de confidentialité</Anchor>, n’est pas toujours renseigné dans la valeur de conversion (CV). On parle alors de CV nulles. Dans le cas d’une CV nulle, seule l’installation est enregistrée.
* Les mesures sont calculées comme suit :
  * Les résultats non organiques du tableau de bord sont calculés à l’aide des données de postback SKAN que reçoit AppsFlyer. Certaines mesures, comme les re-téléchargements, l’ID de l’app source et les métriques de type fidélité, nécessitent que vous configuriez votre app pour <Anchor target="_blank" href="/marketers/fr/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">que les copies de postback soient transmises directement à AppsFlyer</Anchor>.
  * Les métriques organiques sont calculées en soustrayant les données d’attribution non organiques SKAN aux données d’attribution AppsFlyer. **Remarque** : Les métriques organiques ne sont pas toujours disponibles. [En savoir plus.](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#traits-and-limitations)
    * Veillez à filtrer par **Nouvelles installations** dans le champ Type d’installation.
  * Certaines mesures, comme les revenus et le ROAS, portent à la fois la valeur d’origine issue des postbacks et la [valeur modélisée](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv) (qui prend en compte les CV nulles).
* Le trafic généré par l’agence est traité comme issu d’une agence transparente.
* Actualisation des données :
  * Quotidienne.
  * Les postbacks reçus un jour donné sont traités en fin de journée UTC. Les données sont disponibles à 08:00 UTC le jour suivant. Cela signifie que des postbacks reçus le lundi seront disponibles dans le tableau de bord le mardi matin.
  * Cf <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide#timing-from-app-install-until-dashboard-and-reports-update">Horaires des mises à jour du tableau de bord.</Anchor>

<div id="skan-dashboard-view-options" />

## Options d’affichage du tableau de bord SKAN

Affichez les données soir selon la [date d’installation soit la date d’arrivée du postback](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#filter-options).

**Pour sélectionner le type d’affichage de la date**, dans AppsFlyer, allez dans le menu latéral, sélectionnez **Analyser** > **SKAN général.** Dans la barre des filtres, sélectionnez l’une des options de date **Afficher par**.

Des filtres et des options d’affichage supplémentaires sont abordés dans les sections qui suivent.

<div id="dashboard-use" />

## Utilisation du tableau de bord

<div id="dashboard-settings" />

<Accordion title="Paramètres du tableau de bord">

Les paramètres du tableau de bord sont disponibles si votre application utilise la méthode héritée <Anchor target="_blank" href="/marketers/fr/docs/skan-conversion-studio#fixed-modes">Mesure de conversion en mode fixepour</Anchor> sélectionner l’événement de conversion.

**Pour sélectionner l’événement de conversion** :

1. Cliquez sur **Paramètres du tableau de bord**, en haut à droite du tableau de bord.
2. Sélectionnez un événement de conversion.
3. Cliquez sur Appliquer.  
   Les mesures de conversion seront calculées avec cet événement.  
   Attention ! Ce paramètre modifie l’affichage du tableau de bord, il ne change pas le paramètre CV dans l’application.

</Accordion>

<div id="filter-options" />

<Accordion title="Options de filtrage">

Les filtres vous permettent de choisir les données à afficher.

| **Filtre** | **Remarques** |
| --- | --- |
| Afficher par | <ul><li>**Date d'installation :** Découle de l’heure d'arrivée du postback, comme suit :<ul><li>Si les postbacks SKAN sont SKAN V4, la formule de la date d'installation est : Date d'installation = heure d'arrivée du postback - [durée cumulée de la fenêtre] - [délai moyen du postback].<ul><li>Postback 1 : date d'installation = heure d'arrivée du postback - 48h - 36h</li><li>Postback 2 : date d'installation = heure d'arrivée du postback - 168h - 84h</li><li>Postback 3 : date d'installation = heure d'arrivée du postback - 840h - 84h</li></ul></li><li>Si les postbacks SKAN sont SKAN V3 ou -, la formule de date d’installation est : Date d'installation = heure d'arrivée du postback - 36 heures - [moyenne de la dernière période active].<ul><li>La valeur par défaut [moyenne de la dernière période active] est de 12 heures.</li><li>Pour une valeur de conversion de 0, la moyenne de la dernière période active est fixée à 0.</li></ul></li></ul></li><li>**Date d'arrivée du postback :**<ul><li>Le moment où le postback a été reçu par AppsFlyer.</li><li>Lorsque vous comparez les mesures du tableau de bord SKAN AppsFlyer et celles fournies par les réseaux publicitaires, n’oubliez pas que les réseaux publicitaires fournissent généralement les données d’après la date d’arrivée du postback.</li><li>Les résultats organiques ne sont pas disponibles lorsque vous choisissez cette option.</li><li>Dans le cas de Google Ads, les dates d’arrivée et d’installation sont les mêmes.</li></ul></li></ul> |
| Période | <ul><li>La date d’installation attribuée. Cette date découle de l’heure d’arrivée du postback.</li><li>Avec un grand nombre d’installations, le manque de précision issu des problèmes de synchronisation est quasi inexistant.</li><li>Les installations incluent les re-téléchargements.</li><li>La période est limitée à 90 jours.</li></ul> |
| Source média | <ul><li>Le réseau publicitaire attribué à l'installation</li><li>Trafic généré par agence : La véritable source média s’affiche quel que soit le statut de transparence de l’agence. Il peut donc arriver que des sources média que vous ne connaissez pas s’affichent.</li></ul> |
| Campagne | <ul><li>Nom et ID de la campagne tels que définis par le réseau publicitaire.</li><li>AppsFlyer convertit l’ID de campagne du postback en celui du réseau publicitaire.</li><li>Si plusieurs noms de campagne sont associés à un même ID de campagne, tous les noms s’affichent dans le tableau de bord. Attention ! Le réseau publicitaire fournit l'ID et le nom de la campagne par postback. L’ID et le nom de campagne sont disponibles dans les données brutes et les rapports SKAN agrégés.</li></ul> |
| ID de site | <ul><li>L’application source qui diffuse votre publicité.</li><li>Permet de comprendre quelles applications vous sont les plus rentables.</li></ul> |
| Géo | <ul><li>Territoire ou pays</li><li>La géo découle des données fournies par le réseau publicitaire, ou de l’adresse IP de l’appareil.</li><li>À partir d’iOS 14.6, l’adresse IP de l’appareil est masquée par un serveur proxy Apple. Ce qui signifie que la géo du serveur Apple apparaît, mais pas l’appareil lui-même.</li></ul> |
| Type d'installation | <ul><li>Installations</li><li>Re-téléchargements rapportés par l’app store</li></ul> |
| Adset | Disponible si le réseau publicitaire fournit ce point de données |
| Ad | Disponible si le réseau publicitaire fournit ce point de données |
| Version | La version de SKAN |

</Accordion>

<div id="headline-metrics" />

<Accordion title="Métriques principales">

| Métrique | Remarques |
| --- | --- |
| Installations | SKAN ne rapporte pas les installations si l’utilisateur n’a pas interagi avec une publicité avant l’installation. AppsFlyer calcule les mesures organiques à l’aide des installations attribuées par AppsFlyer (tableau de bord LTV).<ul><li>Non organique : Installations attribuées à une source média dans le cadre d’une campagne payante app-to-app et qui ont été rapportées par SKAN.</li><li>Les résultats organiques calculés par AppsFlyer comprennent les données suivantes :<ul><li>Installations non attribuées par SKAN, ou pour lesquelles aucun postback n'a été transmis à un réseau publicitaire.</li><li>Clips d'app</li><li>Apple Search Ads</li></ul></li></ul> |
| Points de touch | Les réseaux publicitaires rapportent les impressions et les clics soit par clic, soit par API. |
| Revenu total | <ul><li>Disponible lorsque le mode revenu est actif.</li><li>S’affiche en USD, ou suit la devise spécifique à l'app qui a été définie sur la <Anchor target="_blank" href="/marketers/fr/docs/app-settings">page des paramètres de l'app.</Anchor></li><li>Divisé entre les revenus organiques et non organiques.</li><li>Les revenus organiques sont calculés comme les revenus de toutes les sources, déduction faite des revenus non organiques.</li><li>Pour permettre une véritable comparaison, la durée de la fenêtre post-installation des installations organiques et des installations non organiques est la même.</li><li>Inclut les <Anchor target="_blank" href="/marketers/fr/docs/skan-modeled-data#null-conversion-values">données modélisées</Anchor></li></ul>**Remarque** : Les métriques organiques ne sont pas toujours disponibles. [En savoir plus.](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#traits-and-limitations) |
| Coût | <ul><li>Coût rapporté par le réseau publicitaire. Les données de coût sont rapportées à AppsFlyer via ROI360/ l’API de coût. Le coût s’affiche en USD, ou suit la devise spécifique à l'app qui a été définie sur la <Anchor target="_blank" href="/marketers/fr/docs/app-settings">page des paramètres de l'app.</Anchor></li><li>Si le nom de la campagne change, le coût s’affiche avec le nom de campagne utilisé en dernier (s’il y a plusieurs noms de campagne)</li><li>Les mesures du coût ne sont disponibles que pour le filtre Install type=All qui inclut à la fois les installations et les re-téléchargements.</li></ul> |
| Taux de clic par installation | Taux de clic par installation |
| Tendance sur la période précédente | Les valeurs de tendance (en %) indiquent l’évolution de la mesure par rapport à la période équivalente précédente. Par exemple, si la période en cours va du 1er au 10 mai, la période précédente va du 21 au 30 avril. |

</Accordion>

<div id="charts" />

<Accordion title="Diagrammes">

Les diagrammes proposés dépendent du type de mesure sélectionné.

<Table>
  <thead>
    <tr>
      <th>
        Mesure du diagramme
      </th>
      <th>
        Remarques
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Tendance de l'acquisition utilisateur
      </td>
      <td>
        Dimensions disponibles :

        * Organique
        * Non organique

        [<Image alt="SKAdNetwork_Dashboard_AppsFlyer2_us-en.png" src="https://files.readme.io/5c46dc05b4df07f3f60ff6015f115b4bc89106a6eb594f43d777af2100fdf460-360010368477.png" width="201px" />](https://files.readme.io/e30781379f0acb50d73e18e6c59ff76f8c91fa4cda6b92064310050555f826a3-360010359738.png)
      </td>
    </tr>
    <tr>
      <td>
        Touch pour convertir
      </td>
      <td>
        Vues disponibles :

        * Dimensions du point de touch :
          * Impressions
          * Clics
        * Taux de clic par installation

        [<Image alt="SKAdNetwork_Dashboard_AppsFlyer3_us-en.png" src="https://files.readme.io/3e134f9411b356c8879dad8185b1762e6e039ed277da60fa9f67af351d8ab76d-360010368497.png" width="223px" />](https://files.readme.io/3e134f9411b356c8879dad8185b1762e6e039ed277da60fa9f67af351d8ab76d-360010368497.png)
      </td>
    </tr>
    <tr>
      <td>
        Installations par jour, regroupées par élément publicitaire
      </td>
      <td>
        Éléments disponibles : Source média, Campagne, ID du site, Adset, Publicité, Version

        [<Image alt="SKAdNetwork_Dashboard_AppsFlyer4_us-en.png" src="https://files.readme.io/a9b80aaeb0f34a3054bfb97bb72ff2ab549ff88ae4f6af43bf1c5e1ab604d3d3-360010368537.png" width="206px" />](https://files.readme.io/a9b80aaeb0f34a3054bfb97bb72ff2ab549ff88ae4f6af43bf1c5e1ab604d3d3-360010368537.png)
      </td>
    </tr>
    <tr>
      <td>
        Répartition des mesures par éléments publicitaires
      </td>
      <td>
        Éléments disponibles : Source média, Campagne, ID de site, Adset, Publicité, Version

        [<Image alt="SKAdNetwork_Dashboard_AppsFlyer5_us-en.png" src="https://files.readme.io/f201592b110b3137329f7ad3c48c53e20639fb664383d76ceba2a347e969f6e4-360010368657.png" width="198px" />](https://files.readme.io/f201592b110b3137329f7ad3c48c53e20639fb664383d76ceba2a347e969f6e4-360010368657.png)
      </td>
    </tr>
    <tr>
      <td>
        Principaux événements
      </td>
      <td>
        Les principaux événements contiennent à la fois les utilisateurs organiques et non organiques. Utilisez le filtre de source média (en haut de la page) pour séparer les utilisateurs organiques et non organiques, ou par voir la source média sélectionnée.

        [<Image alt="SKAdNetwork_Dashboard_AppsFlyer6_us-en.png" src="https://files.readme.io/1a569224cec155b54a96433d6b2e36918c9c6f7924629cb09dcfc859358199c3-360010454658.png" width="245px" />](https://files.readme.io/1a569224cec155b54a96433d6b2e36918c9c6f7924629cb09dcfc859358199c3-360010454658.png)
      </td>
    </tr>
    <tr>
      <td>
        Principaux pays
      </td>
      <td>
        [<Image alt="mceclip1.png" src="https://files.readme.io/aba8db1a2aa7a90d5fd5c07e184eebd6d09762c5564f87f87f584d91686a59c6-360011169298.png" width="181px" />](https://files.readme.io/aba8db1a2aa7a90d5fd5c07e184eebd6d09762c5564f87f87f584d91686a59c6-360011169298.png)

         Remarque : Ce tableau est disponible pour les agences mais pas pour les annonceurs
      </td>
    </tr>
    <tr>
      <td>
        Copie de postback
      </td>
      <td>
        Ce diagramme est disponible une fois que vous avez configuré l’application pour qu’elle envoie les <Anchor target="_blank" href="/marketers/fr/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">Copies de postback</Anchor> IOS 15+ à AppsFlyer. Si aucun diagramme ne s’affiche, il peut y avoir différentes raisons :

        * L’app ne nous envoie pas de postback, ou si elle le fait, nous ne les avons pas encore reçus. Vérifiez auprès du développeur de votre app que le point de terminaison AppsFlyer a été correctement défini dans l’application, et que la version de l’application dans l’app store est bien mise à jour.
        * Aucun postback n’a été reçu (ce qui signifie qu’il n’y a pas eu d’installation SKAN) pour la date choisie, ou bien vous avez sélectionné une date antérieure au 1er janvier 2022.

        Remarques :

        * Toutes les autres mesures du tableau de bord sont calculés d’après les postbacks iOS transmis par les réseaux publicitaires à AppsFlyer, ou d’après les données envoyées directement par les SRN. Il peut donc y avoir des différences de résultat entre les copies de postback et les autres métriques.
        * Le tableau des copies de postback n’est pas disponible pour les agences.

        [<Image alt="PostbackCopy.png" src="https://files.readme.io/0f2d290817650c87b3719ce2cdd107fdf66f62f575d3b4b75fcdd1f8330a04a9-4417816656657.png" width="207px" />](https://files.readme.io/0f2d290817650c87b3719ce2cdd107fdf66f62f575d3b4b75fcdd1f8330a04a9-4417816656657.png)

        | Dimension | Remarques |
        | --- | --- |
        | Source média | Source média attribuée à l’installation. <br /><br />* Métriques :<br />  * **Taux de re-téléchargement :** Les métriques reposent sur les postbacks utilisant SKAdNetwork V2.0+.<br />  * **Taux de type de touch attribué :** L’engagement, la vue ou le clic qui a donné l’installation. Les métriques reposent sur les postbacks utilisant SKAdNetwork V2.2+.<br />* Remarque : Si l’ID de la source média s’affiche, c’est qu’aucun nom ne peut être associé à cet ID. Demandez à la source média de mettre à jour son identifiant SKAdNetwork dans AppsFlyer. |
        | App source | Le nom de l’éditeur de la publicité, c’est-à-dire le nom de l’app où l’utilisateur a interagi avec votre publicité.<br /><br />* Métrique : <br />  * **Nombre d'installations** : le nombre d’installations produites par l’application de l’éditeur.<br />* Remarques :<br />  * Si Apple ne divulgue pas l’ID de l’app source en raison des seuils de confidentialité, l’app source s’affiche comme *inconnu*.<br />  * Si le nom de l’app est introuvable, c’est l’ID de l’application qui s’affiche |
        | ID de l'app source | L’ID de l’éditeur de la publicité, c’est-à-dire l’ID de l’app où l’utilisateur a interagi avec votre publicité.<br /><br />* Métrique : <br />  * **Nombre d'installations** : Nombre d’installations générées par l’ID d’app de l’éditeur. |
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="metrics" />

<Accordion title="Métriques">

* Sélectionnez l’une des mesures disponibles. [Métriques modélisées](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv) prennent en compte le taux de CV nulles.
* Définissez le groupe primaire et le groupe secondaire pour chaque dimension pour analyser en profondeur les mesures de performance.

[![SKAdNetwork_Dashboard_AppsFlyer7_us-en.png](https://files.readme.io/434a848c7a33c052c80101788b066f4bdb90ef36423ea140f85c1cc59ace2ebf-360010368617.png)](https://files.readme.io/434a848c7a33c052c80101788b066f4bdb90ef36423ea140f85c1cc59ace2ebf-360010368617.png)

À propos du tableau des mesures :

* Utilisez le tableau pour comparer les performances des campagnes et des sources média.
* D’emblée, les 20 principales sources média s’affichent, rangées par ordre décroissant du nombre d’installations.
* Pour trier le tableau, cliquez sur l'en-tête d'une colonne. Cliquez à nouveau pour inverser l'ordre du tri.
* Les mesures des coûts (coût, impressions et clics) sont disponibles si au moins 1 installation est associée à une campagne donnée. Remarque :
  * Les campagnes avec 0 installation ne s’affichent pas du tout.
  * Certains réseaux publicitaires rapportent les mesures des coûts au niveau de l’adset et de la publicité, mais rapportent l’installation au niveau de la campagne. Dans ce cas, les métriques relatives aux coûts et à l’adset affichent 0 comme résultat d’installation.
* Limitation de la dimension de type touch attribué : les métriques liées aux coûts ne peuvent pas être ventilées et s’affichent comme**Inconnu**.

Métriques du tableau :

<table><tbody><tr><th>Métrique</th><th>Formule/remarques</th></tr><tr><td><p><span>Installations</span></p></td><td><ul><li>Total des installations</li><li>Post-clic <ul><li><p>Utilisateurs produits via attribution post-clic</p></li><li><p>Disponible pour les installations enregistrées à partir du 22 décembre 2021</p></li></ul></li><li>Post-vue <ul><li>Disponible pour les installations enregistrées à partir du 22 décembre 2021</li><li>S’applique aux réseaux publicitaires qui ont implémenté SKAdNetwork V2.2+</li></ul></li></ul><p>Ces données sont dérivées du champ de postback fidelity_type</p></td></tr><tr><td><p><span>Taux de valeur de conversion nulle</span></p></td><td>Postbacks ayant une valeur de conversion nulle/Installations x 100 </td></tr><tr><td><p><span>Impressions</span></p></td><td></td></tr><tr><td><p><span>Clics</span></p></td><td> </td></tr><tr><td><p><span>Taux de clic par installation</span></p></td><td>Installations/Clics x 100</td></tr><tr><td><p><span>Utilisateurs convertis</span></p></td><td><p><span>Nombre d'utilisateurs uniques qui ont produit un certain événement de mesure :</span></p><ul><li><span>Mode personnalisé : Systématiquement af_skad_revenue (si autre chose est sélectionné, les utilisateurs convertis restent vides)</span></li><li><span>Mode SKAN 4 : Systématiquement af_skad_revenue (si autre chose est sélectionné, les utilisateurs convertis restent vides)</span></li><li><span>Mode de revenu : Systématiquement af_skad_revenue</span></li><li><span>Mode de conversion : Événement in-app sélectionné dans les paramètres du tableau de bord</span></li><li> <span>Mode d’engagement : Événement in-app tel que défini dans Conversion Studio</span><span> </span> </li></ul></td></tr><tr><td>Utilisateurs convertis / Installations</td><td> </td></tr><tr><td><p><span>Revenu total</span></p></td><td>Revenus, y compris les données modélisées avec une valeur nulle. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">En savoir plus</a> </td></tr><tr><td><p><span>Revenu total (non modélisé)</span></p></td><td>Revenus rapportés via les valeurs de conversion. Données modélisées non incluses</td></tr><tr><td><p><span>Revenus J1-J2</span></p></td><td>Revenus perçus pour la fenêtre SKAN 1 (jours 1 à 2 sauf modification), y compris les données modélisées de valeurs nulles. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">En savoir plus</a> </td></tr><tr><td><p><span>Revenu J1-J2 (non modélisé)</span></p></td><td>Revenus reçus dans la fenêtre SKAN 1 (jours 1 à 2 sauf modification) Données modélisées non incluses</td></tr><tr><td><p><span>Revenus J3-J7</span> </p></td><td><span>Revenus pour la fenêtre SKAN 2 (jours 3 à 7 sauf modification)</span></td></tr><tr><td><p><span>Revenus J8-J35</span></p></td><td><span>Revenus pour la fenêtre SKAN 3 (jours 8 à 35 sauf modification)</span></td></tr><tr><td><p><span>Coût</span></p></td><td><ul><li><span>Coût rapporté par le réseau publicitaire.<span></span></span></li><li>Si le nom de la campagne change, le coût s’affiche avec le nom de campagne utilisé en dernier (s’il y a plusieurs noms de campagne)</li></ul></td></tr><tr><td>ARPU</td><td><ul><li>Revenu moyen par utilisateur, y compris les données modélisées des valeurs nulles. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">En savoir plus</a> </li><li>Formule : Revenu ($) (modélisé) / Installations</li></ul></td></tr><tr><td>ARPU (non modélisé)</td><td><p>Revenu moyen par utilisateur, données modélisées non incluses</p></td></tr><tr><td>ROI</td><td><ul><li>Retour sur investissement, ce qui inclut les données modélisées de valeurs nulles. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">En savoir plus</a> </li><li>Formule : (Revenu ($) (modélisé) - Coût) / Coût x 100</li></ul></td></tr><tr><td>ROI (non modélisé)</td><td><p>Retour sur investissement, données modélisées non incluses</p></td></tr><tr><td>ROAS</td><td><ul><li>Retour sur les dépenses publicitaires, ce qui inclut les données modélisées de valeurs nulles. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">En savoir plus</a> </li><li>Formule : Revenu ($) (modélisé) / Coût x 100</li></ul></td></tr><tr><td>ROAS (non modélisé)</td><td><p>Retour sur les dépenses publicitaires, données modélisées non incluses</p></td></tr><tr><td>eCPI</td><td> </td></tr><tr><td colspan="2"><strong>Mesures des événements in-app</strong></td></tr><tr><td>Nom de l'événement in-app</td><td> </td></tr><tr><td>eCPA</td><td><ul><li>Coût par action effectif, données modélisées de valeurs nulles incluses. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">En savoir plus</a> </li><li>Formule : Coût / Utilisateurs uniques ayant produit les événements (modélisé)</li></ul></td></tr><tr><td>eCPA (non modélisé)</td><td><p>Coût par action effectif, données modélisées non incluses</p></td></tr><tr><td>Nombre total d’événements</td><td>Nombre total d’événements sur toutes les fenêtres, y compris les données modélisées de valeurs nulles. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">En savoir plus</a> </td></tr><tr><td>Nombre total d'événements (non modélisé)</td><td>Nombre total d’événements sur toutes les fenêtres, données modélisées non incluses</td></tr><tr><td>Nombre d'événements <span>J1-J2</span> </td><td>Nombre d’événements sur la fenêtre 1 (jours 1 et 2, sauf modification), données modélisées de valeurs nulles incluses. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">En savoir plus</a> </td></tr><tr><td>Nombre d'événements <span>J1-J2 (non modélisé)</span> </td><td>Nombre d’événements sur la fenêtre 1 (jours 1 et 2, sauf modification), données modélisées non incluses</td></tr><tr><td>Nombre d'événements <span>J3-J7</span> </td><td>Nombre d’événements sur la fenêtre 2 (jours 3 à 7, sauf modification), données modélisées de valeurs nulles incluses. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">En savoir plus</a> </td></tr><tr><td>Nombre d'événements <span>J8-J35</span> </td><td>Nombre d’événements sur la fenêtre 3 (jours 8 à 35, sauf modification), données modélisées de valeurs nulles incluses. <a href="./skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv">En savoir plus</a> </td></tr></tbody></table>

</Accordion>

<div id="modeled-metrics-and-null-cv" />

<Accordion title="Mesures modélisées et CV nulles">

Les rapports de SKAdNetwork (SKAN) peuvent être limités pour les raisons suivantes :

* SKAN s'appuie sur des valeurs de conversion (CV) limitées à 6 bits, ce qui donne 64 valeurs possibles (0-63).
* Apple dissimule parfois la CV réelle (et renvoie les données avec la mention « null ») afin de préserver la confidentialité de l'utilisateur.
* Les données ne sont disponibles que depuis une fenêtre de mesure, la valeur lifetime complète (LTV) n’est pas connue.

Les données modélisées par SKAN corrigent ces problèmes, en fournissant :

* Des valeurs de conversion modélisées à la place des valeurs nulles.
* Des revenus et le nombre d’événements modélisés.
* Une meilleure vision des performances des applications et campagnes en termes de LTV.

Les métriques modélisées disponibles sont les suivantes :

* Revenus
* Nombre d'événements
* eCPA
* ARPU
* ROI
* ROAS

<Anchor target="_blank" href="/marketers/fr/docs/skan-modeled-data">En savoir plus sur les données SKAN modélisées</Anchor>

</Accordion>

<div id="appsflyer-attribution-vs-skan-attribution" />

<Accordion title="L’attribution AppsFlyer et l’attribution SKAN">

Les mesures SKAN diffèrent de celles proposées par le modèle d’attribution AppsFlyer. Le tableau ci-dessous vous explique pourquoi.

Postulat :

* **Heures :** Supposons que la fenêtre d’activité par défaut soit de 24 heures (48 heures après la mise à niveau vers SKAN 4).
* **SDK :** SDK AppsFlyer intégré à l’application.
* **Règles**: <Anchor target="_blank" href="/marketers/fr/docs/appsflyer-attribution-model">Modèle d'attribution AppsFlyer</Anchor>

<div id="attribution-framework-differences" />

#### Différences dans le cadre d’attribution

| Concept | SKAN | AppsFlyer |
| --- | --- | --- |
| Méthode d’attribution prise en charge | Apple SKAN pour l’attribution post-clic et post-vue. Contient le trafic des campagnes app-to-app des réseaux publicitaires et des SRN prenant en charge SKAN. | **<Anchor target="_blank" href="/marketers/fr/docs/appsflyer-attribution-model">Le modèle d’attribution AppsFlyer</Anchor> prend en charge plusieurs méthodes et scénarios d’attribution :**<ul><li>Web mobile</li><li>Fraude de visibilité</li><li>Post-clic</li><li>Clips d'app</li><li>Attribution web</li><li>Apple Search Ads</li><li>Média propriétaire</li><li>Trafic SRN (utilisateurs consentants)</li><li>Autre</li></ul> |
| Source de données principale | <ul><li>Postbacks SKAN</li><li>SDK</li></ul> | SDK et solutions associées.  Ex. : Événements de serveur à serveur |
| Actualisation des données | <Anchor target="_blank" href="/marketers/fr/docs/about-data-freshness-and-timezone-support#skan">Actualisation des données SKAN.</Anchor> | En temps réel lorsque l’utilisateur lance et utilise l’application. |
| Fuseau horaire | UTC | Fuseau horaire propre à l'app. |
| Heure d'installation | Découle de l’heure d'arrivée du postback IOS. | Rapporté via SDK. |
| Fenêtre d'activité | Activité de l’utilisateur pendant une fenêtre de mesure fixe qui démarre au moment de l’ouverture de l’app. | Contient les données LTV de la date d’installation au jour présent.<br /><br />Pour afficher une période de mesure comparable, utilisez l’option Cohorte permettant d’afficher les données limitées soit au jour 0, soit au jour 1, soit aux 2 jours de cohorte.<br /><br />Gardez en tête que le jour 0 de la cohorte comprend moins de 24 heures d’activité. Exemple : un utilisateur qui installe à 18h00 aura 6 heures d’activité le jour 0 de la cohorte. |
| Installations rapportées par | <ul><li>**SKAN** : limité aux installations non organiques et aux re-téléchargements non organiques.</li><li>**SDK** : toutes les installations sont rapportées. Seules les premières installations sont prises en compte dans les mesures. C’est-à-dire que les réattributions ne sont pas prises en compte.</li></ul> | Le SDK rapporte toutes les installations classées dans les Règles *premières installations* et *réinstallations de retargeting* (réattributions). |
| Niveau de granularité publicitaire | Campagne, adset, ID d’adset, publicité et ID publicitaire. | Hiérarchie complète : Campagne, ID de campagne, adset, paramètres complémentaires de type canal ou partenaire. |
| Re-téléchargements et réinstallations | Les re-téléchargements concernent les actions d’un utilisateur donné de l’ID Apple. Ils ne sont pas liés aux réattributions. | Le retargeting (ré-engagements, ré-attributions) apparaît reflété dans le tableau de bord de retargeting. Il n’est pas lié aux re-téléchargements. |

<div id="metric-differences" />

#### Différences entre les métriques

| Métrique | SKAN | Attribution classique |
| --- | --- | --- |
| installations non organiques | Nombre de postbacks iOS valides reçus par AppsFlyer.<br /><br />Remarque : AppsFlyer n’obtient pas les postbacks des réseaux publicitaires qui n’ont pas complété l’intégration SKAN avec AppsFlyer.<br /><br />Cela peut réduire le nombre d’installations non organiques comptabilisées, et augmenter celui des installations organiques. | <ul><li>Rapporté via SDK.</li><li>Attribué a une source média.</li><li>Comptabilisé en suivant les Règles.</li></ul> |
| Installations organiques | Les installations du SDK moins les installations SKAN. | <ul><li>Rapporté via SDK.</li><li>Non attribuées à une source média.</li><li>Comptabilisé en suivant les Règles.</li></ul> |
| Revenus | **Non organique** : Revenu rapporté via postbacks SKAN.<br /><br />**Organique :** Revenu rapporté par les événements in-app du SDK moins les revenus non organiques. **Remarque** : Les métriques organiques ne sont pas toujours disponibles. [En savoir plus.](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#traits-and-limitations) | <ul><li>Rapporté par le SDK et l’API de serveur à serveur.</li></ul> |
| Revenus publicitaires | <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide#recording-ad-revenue">Disponible</Anchor> | Les revenus publicitaires de niveau utilisateur sont attribués selon l’IDFV |
| ROI / ROAS | Revenu au cours de la fenêtre de mesure. | <ul><li>LTV</li><li>Métriques des campagnes UA et de retargeting.</li></ul> |

</Accordion>

<div id="faq-skan-discrepancies" />

<Accordion title="FAQ : Les écarts dans SKAN">

| Raison | Écarts dans les mesures : Questions & Réponses |
| --- | --- |
| A | **Q : Pourquoi les chiffres de conversion du tableau de bord AppsFlyer sont-ils différents de ceux du tableau de bord du réseau publicitaire ?**<br /><br />**R** : Ce qui cause des résultats différents<ul><li>**Date d’installation / date d’arrivée du postback :**<ul><li>AppsFlyer : la date d’installation est issue d’une formule qui prend en compte l’heure d’arrivée du postback iOS, la longueur de la fenêtre et le délai du postback.</li><li>Réseau publicitaire : il utilise généralement l’heure d’arrivée du postback iOS pour dater l’installation, sans rien modifier.</li><li>Choisissez l’option **Affichage par date d’arrivée du postback**dans le tableau de bord pour supprimer le problème.</li></ul></li><li>**Validation du postback :** AppsFlyer valide les postbacks iOS reçus et s’assure que la signature Apple est valide. Le réseau publicitaire peut quant à lui envoyer des postbacks non valides refusés par AppsFlyer.</li><li>**Postbacks manquants** : les Postbacks iOS doivent être transmis à AppsFlyer par le réseau publicitaire. AppsFlyer n’obtient pas le postback directement depuis l’appareil. Si des postbacks sont manquants, AppsFlyer n’a aucun moyen de le savoir.</li></ul> |
| B | **Q :** Ecarts entre les <Anchor target="_blank" href="/marketers/fr/docs/skan-aggregated-performance-report-api">API de performance SKAN</Anchor> et le tableau de bord comparé à l’<Anchor target="_blank" href="/marketers/fr/docs/skan-aggregated-postback-arrival-date-api">API de postback agrégé SKAN ?</Anchor><br /><br />**R** : La période de l’API de postback correspond à la date à laquelle AppsFlyer a reçu la publication. La période de l’API de performance correspond à la date d’installation telle que calculée dans le scénario A. |
| C | **Q : Est-ce que tous les réseaux publicitaires rapportent la géo ?**<br /><br />**R** : Non. |
| D | **Q : Pourquoi y a-t-il des différences entre le tableau de bord général et le tableau de bord SKAN ?**<br /><br />**R** : Cf la section précédente pour obtenir des informations sur les écarts de résultat. |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Caractéristiques et limitations">

| Caractéristique | Remarques |
| --- | --- |
| Nombre d'événements modélisés | <ul><li>Les événements modélisés sont basés sur la formule décrite dans la section [Mesures modélisées et CV nulles](/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#modeled-metrics-and-null-cv).</li><li>La formule s’applique à chaque ligne de données. Cela peut entraîner des différences entre le nombre d’événements modélisés pour une source média précise, et le nombre total d’événements modélisés de ses campagnes.</li></ul> |
| Date d'arrivée du postback | La date finale d’une période est fixée au jour où la dernière installation a été enregistrée. |
| Données organiques | <ul><li>Pour <Anchor target="_blank" href="/marketers/fr/docs/skan-conversion-studio#skan-4">SKAN 4</Anchor> et <Anchor target="_blank" href="/marketers/fr/docs/skan-conversion-studio#custom">Modes personnalisés</Anchor>, les données organiques sont disponibles pour les installations, mais pas pour les événements in-app, ni le total des revenus.</li><li>Pour les <Anchor target="_blank" href="/marketers/fr/docs/skan-conversion-studio#fixed-modes">Modes fixes</Anchor>, les données organiques sont disponibles pour les installations et les événements in-app.</li><li>Pensez à utiliser la SSOT pour afficher les données organiques, car la SSOT supprime les doublons des événements attribués au modèle SKAN et au modèle AppsFlyer.</li><li>Si les données d’attribution AppsFlyer (nouvelles installations organiques et non organiques) moins les données d’attribution SKAN (installations non organiques) donnent un résultat négatif (-), le tableau de bord SKAN affiche 0 dans la section Installations organiques.</li></ul> |
| Données historiques | Données de conversion les plus anciennes pouvant être prises en charge : Novembre 1, 2020 |
| Devise | S’affiche en USD, ou suit la devise spécifique à l'app qui a été définie sur la <Anchor target="_blank" href="/marketers/fr/docs/app-settings">page des paramètres de l'app.</Anchor> |
| Fuseau horaire | Pour les données rapportées par SKAN, les installations et les événements s'affichent en utilisant UTC, à l'exception des données Meta et Google SKAN, pour lesquelles le fuseau horaire est celui que vous avez configuré dans chacun de vos comptes Meta et Google. |

</Accordion>

<div id="see-also" />

> 📄 **Articles connexes**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide">Guide de la solution SKAN AppsFlyer</Anchor>
> * <Anchor target="_blank" href="/marketers/fr/docs/about-att-and-skan">Ce qui change : mises à jour AppsFlyer pour iOS 14</Anchor>

<div data-zendesk-anchors="dashboard-principles=les-bases-du-tableau-de-bord 01H81P8JPZM24J0536GKBPNFMJ=les-bases-du-tableau-de-bord skan-dashboard-view-options=options-daffichage-du-tableau-de-bord-skan 01H81P8JPZC5K0KZR64P084N4W=options-daffichage-du-tableau-de-bord-skan dashboard-use=utilisation-du-tableau-de-bord 01H81P8JPZGSHQVMG27YEJPARH=utilisation-du-tableau-de-bord 01H81P8JPZ93G4EQY343SV2B1Q=dashboard-settings 01H81P8JPZV5F4VCZHR537HREH=filter-options 01H81P8JQ0KRGXWCVT82YW30CS=headline-metrics 01H81P8JQ0ETB0W3SGS56CBCX8=charts 01H81P8JQ0KK1NMRGFR0GBX4EK=metrics 01H81P8JQ0ZKGTRWNW95D015Z7=modeled-metrics-and-null-cv 01H81P8JQ18NGP8Z74D02DMQ7P=appsflyer-attribution-vs-skan-attribution attribution-framework-differences=diff%C3%A9rences-dans-le-cadre-dattribution 01H81P8JQ1VTYX3382WDXDMVT3=diff%C3%A9rences-dans-le-cadre-dattribution metric-differences=diff%C3%A9rences-entre-les-m%C3%A9triques 01H81P8JQ1M8M9TSHF0C12Z2QE=diff%C3%A9rences-entre-les-m%C3%A9triques faq%E2%80%94skan-discrepancies=faq-skan-discrepancies 01H81P8JQ157YYNX9C527ES4C8=faq-skan-discrepancies 01H81P8JQ1T3DE29Y14VARKASK=traits-and-limitations h_01HE7SWGPWNWG26CEN40VSTA9J=articles-connexes" />
