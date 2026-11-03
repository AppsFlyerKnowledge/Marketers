---
title: Rapports de données brutes SKAN
metadata:
  keywords:
    - Advertisers
    - Premium Feature
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2020-10-08T20:54:55Z'
  edited_at: '2023-11-27T11:51:03Z'
  id: 360014261518
  locale: fr
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/fr/articles/360014261518
---
> **En bref :** les rapports de données brutes SKAN contiennent des données au niveau des lignes générées après la traduction et le décodage des postbacks envoyés par iOS à AppsFlyer, ainsi que des postbacks bruts SKAN. Les données sont disponibles via <Anchor target="_blank" href="/marketers/fr/docs/data-locker-for-marketers">Data Locker</Anchor> et <Anchor target="_blank" href="/marketers/fr/docs/push-api-streaming-raw-data">API Push</Anchor>. Si votre abonnement comprend des données brutes, il n'est pas nécessaire de souscrire à un abonnement Data Locker.

## Rapports de données brutes SKAN

Principes : 

* **Les données sont fournies par :**
  * **Data Locker**
    * **Attention**! Disponible pour les comptes avec un abonnement incluant les données brutes. Autrement dit, inutile de souscrire à un abonnement Data Locker. Si vous n'utilisez pas encore Data Locker, un utilisateur avec le rôle d'admin doit configurer Data Locker et activer les rapports SKAN. Pour ce faire, rendez-vous dans **Intégration** > **Data Locker**. Sélectionnez les rapports SKAN.
    * **Actualisation des données :** quotidienne  
      Les données sont contenues dans le dossier h=23 du jour où les données sont reçues par AppsFlyer.Exemple : un postback reçu le lundi est traité après la fin de la journée. Le traitement se termine le mardi à 12:00 UTC et les données sont mises à disposition dans le dossier du lundi h=23.
  * **API Push**
    * Actualisation des données : voir <Anchor target="_blank" href="/marketers/fr/docs/push-api-streaming-raw-data">API Push pour les données SKAN</Anchor>.
* **Date d'installation**: elle est estimée selon l'heure d'arrivée du postback chez AppsFlyer de la manière suivante :
  * S'il s'agit de postbacks SKAN V4, la formule de calcul de la date d'installation est la suivante : Date d'installation = heure d'arrivée du postback - [longueur de fenêtre accumulée] - [délai moyen de postback].
    * Postback 1 : date d'installation = heure d'arrivée du postback - 48h - 36h
    * Postback 2 : date d'installation = heure d'arrivée du postback - 168h - 84h
    * Postback 3 : date d'installation = heure d'arrivée du postback - 840h - 84h
  * S'il s'agit de postbacks SKAN V3, la formule de calcul de la date d'installation est la suivante : Date d'installation = heure d'arrivée du postback - 36 heures - [moyenne de la dernière plage active]. 
    * La valeur par défaut [moyenne de la dernière plage active] est de 12 heures.
    * Pour une valeur de conversion de 0, la moyenne de la dernière plage active est fixée à 0.
  * Google estime lui-même le temps d'installation et AppsFlyer utilise ce temps d'installation. **Remarque** : Google peut mettre jusqu'à 13 jours prendre en compte les installations. <Anchor target="_blank" href="/marketers/fr/docs/get-skan-postback-data-from-google-ads#obtenir-les-données-de-postback-skan-depuis-google-ads">En savoir plus</Anchor>

Les types de rapports disponibles sont les suivants :

* **Postback d'appareil** : 1 postback d'appareil par installation ou re-téléchargement reçu de l'appareil iOS.
* **Données brutes SKAN** :
  * AppsFlyer décode et traduit le postback de l'appareil en enregistrements de données brutes.
  * Chaque postback génère un enregistrement d'installation ou de re-téléchargement et des enregistrements d'événements in-app.
  * Le nombre d'enregistrements d'événements in-app dépend de la valeur de conversion (VC), comme suit :
    * VC = 0, vide ou null : aucun enregistrement in-app n'est généré.
    * Plage de VC :
      * 1-63 : pour SKAN 3, et SKAN 4 fenêtre 1 valeur fine, il s'agit du nombre d'enregistrements dans l'app, en fonction de vos paramètres de mesure.
      * Faible, moyen ou élevé : pour les valeurs grossières de SKAN 4, il s'agit du nombre d'enregistrements dans l'app, en fonction de vos paramètres de mesure.

**Pourquoi certains champs sont-ils vides ?** Cela se produit pour l'une des raisons suivantes :

* Champs d'enrichissement non obligatoires tels que campaign\_name, ad\_network\_campaign\_id, ip, que le réseau publicitaire n'a pas fournis.
* Apple n'a pas divulgué les données en raison de ses politiques de seuil. Champs tels que source\_app\_id, skad\_campaign\_id, skad\_conversion\_value.

## Format et contenu du rapport sur les données brutes SKAN

<div id="raw-data-report-types" />

<Accordion title="Types de rapports sur les données brutes">

<Table>
  <thead>
    <tr>
      <th>
        Type de rapport
      </th>
      <th>
        Nom du rapport
      </th>
      <th>
        Description
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Postback
      </td>
      <td>
        Les postbacks
      </td>
      <td>
        Postbacks envoyés par iOS au réseau publicitaire. Le postback, après enrichissement par le réseau publicitaire est transmis à AppsFlyer. [Télécharger l'exemple de postback](https://docs.google.com/spreadsheets/d/e/2PACX-1vRfFFmj1YV1c73Wbar2VOiKWml6VmsyFvQuydXTPUOO4zXVKmwtw6nup9vKNtNwou2z8IqNpcF4yP6c/pub?gid=1225544365&single=true&output=csv) (CSV).

        Remarque : les postbacks ne sont pas inclus lorsque did\_win=false.

        **Nom du sujet dans Data Locker** : skad\_postbacks
      </td>
    </tr>
    <tr>
      <td>
        Postback
      </td>
      <td>
        Copie des postbacks (directement d'Apple)
      </td>
      <td>
        Postbacks envoyés directement par iOS à AppsFlyer.

        Disponible à partir d'iOS 15+ et nécessite que l'annonceur configure l'app pour <Anchor target="_blank" href="/marketers/fr/docs/send-skan-and-adattributionkit-postback-copies-directly-to-appsflyer-ios-15">envoyer le postback retenu</Anchor> à AppsFlyer. [Télécharger l'exemple de postback](https://docs.google.com/spreadsheets/d/e/2PACX-1vSu0c3gYoIHe2k6_M3cngSFzc-txQvEN38X7Ig7qhXYPg8uBUzyyPqlSwDMugvZS_tUrFjtY8AGYKrh/pub?gid=1225544365&single=true&output=csv) (CSV).

        Remarque : Cette rubrique ne contient que les postbacks retenus.

        **Nom du sujet dans Data Locker** : skad\_postbacks\_copy
      </td>
    </tr>
    <tr>
      <td>
        Événement décodé
      </td>
      <td>
        Installations
      </td>
      <td>
        **Première installation d'une app**

        SKAN a rapporté *redownload=false*. Cela signifie que c'est la première fois que l'utilisateur, représenté par l'identifiant Apple, a téléchargé l'app.  
        [Télécharger l'exemple de postback](https://docs.google.com/spreadsheets/d/e/2PACX-1vS4rNJAio8Ub2cffUEiYhzdavVfXaJAD6OpjhRBjVpGQsAlibOWCkZpfLl29n1OCDBZ2eToO4_gOvbl/pub?gid=1472391837&single=true&output=csv) (CSV).

        **Nom du sujet dans Data Locker**: skad\_installs
      </td>
    </tr>
    <tr>
      <td>
        Événement décodé
      </td>
      <td>
        Re-téléchargements
      </td>
      <td>
        **Installations de l'app qui ne sont pas des premières installations**

        SKAN a rapporté *redownload=true*. Cela signifie que ce n'est pas la première fois que l'utilisateur, représenté par l'identifiant Apple, a téléchargé l'app.  
         Ce rapport a la même structure que les installations.

        **Nom du sujet dans Data Locker**: skad\_redownloads
      </td>
    </tr>
    <tr>
      <td>
        Événement décodé
      </td>
      <td>
        Évènements in-app
      </td>
      <td>
        **Évènements in-app**

        Depuis le 21 juillet 2021, des changements ont été apportés à la manière dont nous fournissons les données brutes des événements in-app, comme indiqué dans les tableaux.

        Le nombre d'enregistrements d'événements in-app dépend de vos paramètres de mesure.

        [Télécharger l'exemple d'événements in-app](https://docs.google.com/spreadsheets/d/e/2PACX-1vRwhxOmZwTkOr9uNFN0d4Rk2jFpipONoB8KzIZI5Tw12IvoLirj07QUdI9RJoL9rZYFSN1PvT-W6vP0/pub?gid=1454741057&single=true&output=csv) (CSV).

        **Nom du sujet dans Data Locker**: skad\_inapps

        Valable pour les postbacks iOS reçus à partir du 21 juillet 2021 :

        | Type de mesure | Description |
        | --- | --- |
        | Revenus | * Revenu pour un utilisateur donné. Si revenu > 0, enregistrement contenant les champs skad\_revenue et event\_name.<br />* Les champs min\_revenue et max\_revenue sont remplis avec les valeurs de votre plage de conversion personnalisée. |
        | Conversion in-app et événements relatifs au tunnel | * Un enregistrement pour chaque événement de conversion unique réalisé. Le champ event\_name est rempli en conséquence. Si aucun événement n'a lieu, il n'y a pas d'enregistrement.<br />* Les événements de conversion ont un compteur min\_événement = 0 et un compteur max\_événement = 1. |
        | Engagement in-app | Pour déterminer le nombre de fois qu'un utilisateur effectue un événement in-app donné, utilisez la formule suivante : `[(min_event_counter + max_event_counter) arrondi / 2]` |

        Valable pour les postbacks iOS reçus à partir du 21 juillet 2021 :

        | Type de mesure | Nombre d'enregistrements | Description |
        | --- | --- | --- |
        | Revenus | 0-1 | Si revenu > 0, enregistrement contenant les champs skad\_revenue et event\_name. |
        | Conversion | 0-6 | Un enregistrement pour chaque événement de conversion unique réalisé. Le champ event\_name est rempli en conséquence. Si aucun événement n'a lieu, il n'y a pas d'enregistrement. |
        | Engagement | 0-63 | Le nombre d'enregistrements représente le nombre de fois où l'utilisateur a effectué l'événement d'engagement. Si l'utilisateur ne s'engage pas, il n'y a pas d'enregistrement d'engagement. |
        | Personnalisation | 0-unlimited | Selon votre schéma de conversion personnalisé. |
      </td>
    </tr>
    <tr>
      <td>
        Événement décodé
      </td>
      <td>
        Dimensions publicitaires SRN
      </td>
      <td>
        * Le rapport contient des événements Meta Ads avec une granularité de campagne, d'adset et de publicités. Chaque ligne du rapport peut correspondre à un événement d'installation ou à un événement in-app.
        * La granularité de l'adset et de la publicité n'est pas incluse dans les postbacks SKAN Meta Ads. Ces données sont propres à ce rapport et ne s'affichent pas dans le tableau de bord SKAN, l'API de performance et les autres rapports SKAN Data Locker.
        * Rapport dénué de schéma. Les options de choix des champs Data Locker ne s'appliquent pas.
        * Recommandation : ne combinez pas ou ne comparez pas les données de ce rapport avec d'autres rapports SKAN, car il peut y avoir des divergences entre ce rapport, qui utilise des données décodées par le SRN, et les autres rapports, qui utilisent des données décodées par AppsFlyer. Ces écarts peuvent être dues à des différences de fuseau horaire, de schéma SRN ou à des événements in-app incorrectement mappés à la CV dans l'intégration SRN.
        * <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTZjIpqZJxHY9WpIdf9OeDCVQYzM_fLmrpB1oAt3S-MbJTKueOJODwwl6Pz3M0SCAbCFIdMlshOayrw/pub?output=xlsx">Télécharger l'exemple de dimensions publicitaires SRN</Anchor> (CSV).

        **Nom du sujet dans Data Locker** : skad\_srn\_advertising\_dimensions
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="raw-data-field-format-types" />

<Accordion title="Types de formats de champs de données brutes">

#### Formats de champs

| Nom de format | Description |
| --- | --- |
| Chaîne [n] | La longueur maximale de la chaîne. En général, nous ne limitons pas la longueur des champs à réception des données, mais les données peuvent être tronquées par la suite. |
| Chaîne de temps | Chaîne au format `aaaa-mm-jj hh:mm:ss`. Par exemple ,`2019-09-17 00:09:25` |
| Enum [n] | Les champs Enum ne peuvent contenir que des valeurs spécifiques. Par exemple, la devise Coût a 3 caractères et ne peut contenir que les codes de devise spécifiés. |
| Horodatage | 10-digit UNIX timestamp. Exemple :<br /><br />Le 4 août 2020, 07h25 UTC, se traduit par `"timestamp": "1596525944"` |
| Booléen | La valeur du champ peut être`TRUE` ou `FALSE`. |
| Entier | Entier |
| Float | Nombre réel flottant qui peut avoir une virgule et des valeurs après celle-ci. |

</Accordion>

<div id="fields-available-in-postback-and-postback-copy-reports" />

<Accordion title="Champs disponibles dans les rapports de postback et de copie de postback">

<table><thead><tr><th>Nom du champ</th><th>Source ou version de départ iOS SKAN</th><th>Description</th><th>Format</th><th>Disponible en copie de postback </th></tr></thead><tbody><tr><td><p>ad_network_campaign_id</p></td><td>Réseau publicitaire</td><td>ID de campagne communiqué par le réseau publicitaire à AppsFlyer.</td><td>Chaîne</td><td>Non</td></tr><tr><td><p>ad_network_campaign</p><p>_name</p></td><td>Réseau publicitaire</td><td><p>Nom de la campagne communiqué par le réseau publicitaire à AppsFlyer.</p></td><td>Chaîne</td><td>Non</td></tr><tr><td><p>ad_network_timestamp</p></td><td>Réseau publicitaire</td><td><p>Heure à laquelle le réseau publicitaire a reçu le postback.</p><p>Dans le cas de Google Ads, l'heure est dérivée de l'heure du dernier clic enregistrée par Google.</p></td><td>Horodatage</td><td>Non</td></tr><tr><td><p>app_id</p></td><td>AppsFlyer</td><td>ID d'app (app de l'annonceur) avec le préfixe ID.</td><td>Chaîne</td><td>Oui</td></tr><tr><td><p>city</p></td><td>AppsFlyer</td><td>Depuis le 30 août 2021, toujours null </td><td>Chaîne</td><td>Non</td></tr><tr><td><p>country_code</p></td><td>Réseau publicitaire</td><td> </td><td>Chaîne</td><td>Non</td></tr><tr><td>dma</td><td> </td><td>Depuis le 30 août 2021, toujours null </td><td>Chaîne</td><td>Non</td></tr><tr><td><p>postal_code</p></td><td> </td><td>Depuis le 30 août 2021, toujours null  </td><td>Chaîne</td><td>Non</td></tr><tr><td><p>Région</p></td><td>AppsFlyer</td><td>Selon le country_code indiqué.</td><td>Chaîne</td><td>Non</td></tr><tr><td><p>skad_ad_network_id</p></td><td>1.0 </td><td><p>Certains SRN ne partagent pas leur identifiant et le champ est laissé vide. Par exemple, X. </p></td><td>Chaîne</td><td><p>Oui </p></td></tr><tr><td><p>skad_attribution_signature</p></td><td>1.0</td><td> </td><td>Chaîne</td><td>Oui</td></tr><tr><td>skad_campaign_id</td><td>1.0</td><td>ID de la campagne utilisé pour publier la publicité. Plage de valeurs : 0-100</td><td>Chaîne</td><td>Oui</td></tr><tr><td>skad_conversion_value</td><td>2.0 </td><td><p>Valeur de conversion rapportée par iOS. Plage de valeurs : 0-63</p><p>Si null, iOS n'a pas rempli le champ\*\* </p></td><td>Entier</td><td>Oui</td></tr><tr><td>skad_redownload</td><td>2.0</td><td>Si TRUE, l'app a été re-téléchargée.</td><td><p>Booléen</p></td><td><p>Oui</p></td></tr><tr><td>skad_source_app_id</td><td>2.0</td><td><p>ID du site. L'app qui publie l'annonce. Ce champ est identique à source_app_id.</p><p>Le champ est rempli en fonction des seuils de confidentialité\*\*</p></td><td>Chaîne</td><td>Oui</td></tr><tr><td>skad_transaction_id</td><td>1.0</td><td> </td><td>Chaîne</td><td>Oui</td></tr><tr><td>skad_version</td><td>2.0</td><td> </td><td>Chaîne</td><td>Oui</td></tr><tr><td>Horodatage</td><td>Réseau publicitaire</td><td><p>Heure à laquelle AppsFlyer a reçu le postback SKAN. </p></td><td>Chaîne de temps</td><td>Oui</td></tr><tr><td>ad_network_name</td><td>Réseau publicitaire</td><td><p>Nom du réseau publicitaire communiqué par le réseau publicitaire à AppsFlyer. </p><ul><li>Si ce champ est vide, c'est que le réseau publicitaire ne l'a pas rempli ou n'a pas pu le remplir.</li><li>Vous pouvez corriger le nom du réseau publicitaire en utilisant using skad_ad_network_id. Pour ce faire, utilisez ce <a href="./skan-integrated-partners-list#apple-skadnetwork-ids-of-ad-networks" target="_blank">tableau</a>. </li></ul></td><td>Chaîne</td><td>Non</td></tr><tr><td>ip</td><td> </td><td><p>Adresse IP dans le message HTTP de l'appareil iOS qui envoie le postback.</p><p>Ce champ est rempli si le réseau publicitaire fournit l'adresse à AppsFlyer.</p><p>Important ! Le SDK n'est pas impliqué dans l'obtention de l'adresse.</p></td><td>Chaîne</td><td>Non</td></tr><tr><td><p>skad_app_id</p></td><td>1.0</td><td> </td><td>Chaîne</td><td>Non</td></tr><tr><td><p>source_app_id</p></td><td>AppsFlyer</td><td>ID du site. L'app qui publie l'annonce. Ce champ est identique à skad_source_app_id.</td><td>Chaîne</td><td>Non</td></tr><tr><td><p>ad_network_adset_id</p></td><td>Réseau publicitaire</td><td> </td><td>Chaîne</td><td>Non</td></tr><tr><td><p>ad_network_adset_name</p></td><td>Réseau publicitaire</td><td> </td><td>Chaîne</td><td>Non</td></tr><tr><td><p>ad_network_ad_name</p></td><td>Réseau publicitaire</td><td> </td><td>Chaîne</td><td>Non</td></tr><tr><td><p>ad_network_ad_id</p></td><td>Réseau publicitaire</td><td> </td><td>Chaîne</td><td>Non</td></tr><tr><td><p>did_win</p></td><td>3.0 (iOS 14.6)</td><td><p>Utilisé pour distinguer les campagnes qui <a href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes">contribuent à l'installation ou auxquelles l'installation est attribuée.</a> </p><ul><li>Si true, la campagne est attribuée à l'installation.</li><li>Si false, la campagne est reconnue comme contribuant à l'installation, mais elle n'est incluse dans aucun tableau de bord ni rapport SKAN.</li><li>Si null, iOS n'a pas rempli le champ en raison d'une  <a href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes" target="_blank">version ancienne d'iOS ou de SKAdNetwork.</a> </li></ul></td><td>Booléen</td><td>Oui</td></tr><tr><td><p>fidelity_type</p></td><td>2.2 (iOS 14.5)</td><td><p><span>Différencie les options de <a href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_ad_attributions" target="_blank">présentation des publicités</a> qui affectent l'attribution. Indiqué avec les valeurs 0 et 1 comme suit : </span></p><ul><li><span>Publicités post vue (0)</span></li><li><span>Publicités rendues par StoreKit (1)</span></li></ul><p>Ne pas tenir compte de la valeur du champ si la version de SKAN est antérieure à 2.2.</p></td><td>Entier</td><td>Oui</td></tr><tr><td><p>ad_network_source_app_id</p></td><td>Réseau publicitaire</td><td><span>ID de l'application de l'éditeur communiqué par le réseau publicitaire. Utilisé pour réconcilier les coûts ; rapporté par le réseau publicitaire. L'application de l'éditeur fournit la base de ces données. </span></td><td>Chaîne</td><td>Non</td></tr><tr><td><p>ad_network_channel</p></td><td>Réseau publicitaire</td><td> </td><td>Chaîne</td><td>Non</td></tr><tr><td><p>af_prt</p></td><td>Réseau publicitaire</td><td> </td><td>Chaîne</td><td>Non</td></tr><tr><td><p><span>skad_postback_sequence_index</span></p></td><td><span>4.0 (iOS 16.2)</span></td><td><ul><li><span>La valeur représente la fenêtre SKAN, soit <code>0</code>, <code>1</code> ou <code>2</code>. </span></li><li><span>Pour SKAN 3, la valeur est <code>0</code></span></li></ul></td><td><span>Entier</span></td><td><span>Oui</span></td></tr><tr><td><span>skad_coarse_conversion_value</span></td><td><p><span>4.0 (iOS 16.2)</span></p></td><td><ul><li><span>La valeur peut être <code>low</code>, <code>medium</code> ou <code>high</code>. </span></li><li><span>Pour SKAN 3, la valeur est <code>nulle</code>.</span></li></ul></td><td><span>Chaîne</span></td><td><span>Oui</span></td></tr><tr><td><span>skad_source_identifier</span></td><td><span>4.0 (iOS 16.2)</span></td><td><ul><li><span>La valeur peut inclure jusqu'à 4 chiffres. </span></li><li><span>Pour SKAN 3, la valeur est<code>nulle</code>. </span></li></ul></td><td><span>Chaîne</span></td><td><span>Oui</span></td></tr><tr><td><span>skad_source_domain</span></td><td><span>4.0 (iOS 16.2)</span></td><td><ul><li><span>La valeur représente la source des publicités web attribuables. </span></li><li><span>Pour SKAN 3, la valeur est <code>nulle</code>.</span></li></ul></td><td><span>Chaîne</span></td><td><span>Oui</span></td></tr><tr><td><span>ad_network_creative</span></td><td><span>Réseau publicitaire</span></td><td><ul><li><span>La valeur est basée sur l'enrichissement des données reçues du réseau publicitaire. </span></li><li><span>Pour SKAN 3, la valeur est <code>nulle</code>.</span></li></ul></td><td><span>Chaîne</span></td><td><span>Non</span></td></tr></tbody><tfoot><tr><td colspan="4"><p>\*\* Apple détermine si le champ est rempli à l'aide d'un mécanisme de seuil de confidentialité </p></td><td></td></tr></tfoot></table>

</Accordion>

<div id="fields-available-in-decoded-event-reports" />

<Accordion title="Champs disponibles dans les rapports d'événements décodés">

<table><thead><tr><th>Nom du champ</th><th>Source</th><th>Description</th><th>Format</th><th>Inclus dans le rapport sur les dimensions publicitaires du SRN</th></tr></thead><tbody><tr><td>ad_network_campaign_id</td><td>Réseau publicitaire</td><td>ID de campagne communiqué par le réseau publicitaire à AppsFlyer.</td><td>Chaîne</td><td>Oui</td></tr><tr><td>ad_network_campaign<br/>_name</td><td>Réseau publicitaire</td><td>Nom de la campagne communiqué par le réseau publicitaire à AppsFlyer.</td><td>Chaîne</td><td>Oui</td></tr><tr><td>ad_network_timestamp</td><td>Réseau publicitaire</td><td><p>Heure à laquelle le postback a été reçu par le réseau publicitaire</p><p>Dans le cas de Google Ads, ce champ n'est pas renseigné. </p></td><td><p>Horodatage</p><p>(chaîne de temps pour le rapport sur les dimensions publicitaires du SRN)</p></td><td>Oui</td></tr><tr><td>app_id</td><td>iOS</td><td>L'ID d'app (app de l'annonceur)</td><td>Chaîne</td><td>Oui</td></tr><tr><td>city</td><td> </td><td>Depuis le 30 août 2021, toujours null </td><td>Chaîne</td><td>Non</td></tr><tr><td>country_code</td><td>Réseau publicitaire</td><td> </td><td>Chaîne</td><td>Non</td></tr><tr><td>dma</td><td> </td><td>Depuis le 30 août 2021, toujours null </td><td>Chaîne</td><td>Non</td></tr><tr><td>event_name</td><td>AppsFlyer</td><td><p>Nom de l'événement in-app tel que configuré dans AppsFlyer.</p><p>Pour le rapport ___ SRN, il s'agit du nom de l'événement in-app tel que configuré dans Meta ads.</p></td><td>Chaîne</td><td>Oui</td></tr><tr><td>event_uuid</td><td>AppsFlyer</td><td>Un identifiant aléatoire unique permettant aux partenaires d'identifier les postbaks en double.</td><td>Chaîne</td><td>Non</td></tr><tr><td>install_date</td><td>iOS</td><td>Estimé par AppsFlyer sur la base de l'heure d'arrivée du postback.</td><td>Chaîne de temps</td><td>Non</td></tr><tr><td>install_type</td><td>iOS</td><td>Nouvelles installations</td><td>Chaîne</td><td>Non</td></tr><tr><td>ip</td><td>iOS</td><td><p>Adresse IP dans le message HTTP de l'appareil iOS qui envoie le postback.</p><p>Ce champ est rempli si le réseau publicitaire fournit l'adresse à AppsFlyer.</p><p>Important ! Le SDK n'est pas impliqué dans l'obtention de l'adresse. </p></td><td>Chaîne</td><td>Non</td></tr><tr><td>media_source</td><td>iOS</td><td>Réseau publicitaire attribué à l'aide des noms de réseaux AppsFlyer.</td><td>Chaîne</td><td>Oui</td></tr><tr><td>postal_code</td><td> </td><td>Depuis le 30 août 2021, toujours null </td><td>Chaîne</td><td>Non</td></tr><tr><td>Région</td><td>AppsFlyer</td><td>Déterminé en fonction de country_code</td><td>Chaîne</td><td>Non</td></tr><tr><td>skad_ad_network_id</td><td>iOS</td><td>ID du réseau publicitaire auquel le postback a été envoyé</td><td>Chaîne</td><td>Non</td></tr><tr><td>skad_ambiguous_event</td><td>AppsFlyer</td><td>Si la réponse est true, le postback iOS a été reçu au cours des 72 premières heures après qu'un annonceur a modifié les paramètres SKAN dans le tableau de bord. En raison des différents chronomètres utilisés par SKAN, AppsFlyer ne peut pas cartographier l'événement avec précision.</td><td>Booléen</td><td>Non</td></tr><tr><td>skad_attribution_signature</td><td>iOS</td><td> </td><td>Chaîne</td><td>Non</td></tr><tr><td>skad_campaign_id</td><td>iOS</td><td>ID de la campagne utilisé pour publier la publicité. Plage de valeurs : 0-100</td><td>Entier</td><td>Non</td></tr><tr><td>skad_conversion_value</td><td>iOS</td><td><p>Valeur de conversion rapportée par iOS. Plage de valeurs : 0-63</p><p>Si null, iOS n'a pas rempli le champ\*\*</p></td><td>Entier</td><td>Non</td></tr><tr><td>skad_mode</td><td>AppsFlyer</td><td><p>Mode de mesure de la conversion utilisé pour décoder le postback iOS. Options :</p><ul><li>custom_decode</li><li>revenus</li><li>évènements</li><li>skan4</li><li>custom_encode</li><li>Engagement</li></ul></td><td>Chaîne</td><td>Non</td></tr><tr><td>skad_redownload</td><td>iOS</td><td>Si TRUE, l'application a été re-téléchargée.</td><td>Booléen</td><td>Non</td></tr><tr><td>skad_revenue</td><td>iOS</td><td>Montant des revenus de l'événement en USD.</td><td>Float</td><td>Non</td></tr><tr><td>skad_source_app_id</td><td>iOS</td><td><p>ID du site (l'application qui publie la publicité).</p><p>Le champ est rempli en fonction des seuils de confidentialité\*\*</p></td><td>Chaîne</td><td>Non</td></tr><tr><td>skad_transaction_id</td><td>iOS</td><td>-</td><td>Chaîne</td><td>Non</td></tr><tr><td>skad_version</td><td>iOS</td><td>-</td><td>Chaîne</td><td>Non</td></tr><tr><td>Horodatage</td><td>iOS</td><td><p><span>Heure à laquelle AppsFlyer a reçu le postback SKAN.</span></p><p>Pour Google Ads et Meta ads, il s'agit du moment où AppsFlyer obtient les données des API Google Ads et Meta ads.</p></td><td><p>Horodatage</p><p>(chaîne de temps pour le rapport sur les dimensions publicitaires du SRN)</p></td><td>Oui</td></tr><tr><td>event_value</td><td>S2S</td><td><p>Valeur par défaut : null</p><p>Contient une chaîne définie par les apps mettant en œuvre un décodage personnalisé.</p><p>Les annonceurs consomment ces données dans leurs systèmes. AppsFlyer n'utilise pas cette fonctionnalité. </p></td><td>String (JSON)</td><td>Non</td></tr><tr><td><p>ad_network_adset_id</p></td><td>Réseau publicitaire</td><td> </td><td>Chaîne</td><td>Oui</td></tr><tr><td><p>ad_network_adset_name</p></td><td>Réseau publicitaire</td><td> </td><td>Chaîne</td><td>Oui</td></tr><tr><td><p>ad_network_ad_name</p></td><td>Réseau publicitaire</td><td> </td><td>Chaîne</td><td>Oui</td></tr><tr><td><p>ad_network_ad_id</p></td><td>Réseau publicitaire</td><td></td><td>Chaîne</td><td>Oui</td></tr><tr><td><p>skad_did_win (1)</p></td><td>3.0 (iOS 14.6)</td><td><p>Utilisé pour distinguer les campagnes qui <a href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes">contribuent à l'installation ou auxquelles l'installation est attribuée.</a> </p><ul><li>Si true, la campagne est attribuée à l'installation.</li><li>Si false, la campagne est reconnue comme contribuant à l'installation, mais elle n'est incluse dans aucun tableau de bord ni rapport SKAN.</li><li>Si null, iOS n'a pas rempli le champ en raison d'une  <a href="https://developer.apple.com/documentation/storekit/skadnetwork/skadnetwork_release_notes/skadnetwork_version_3_0_release_notes" target="_blank">version ancienne d'iOS ou de SKAdNetwork.</a> </li></ul></td><td>Booléen</td><td>Non</td></tr><tr><td><p>skad_fidelity_type (1)</p></td><td>2.2 (iOS 14.5)</td><td><p><span>Différencie les options de <a href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_ad_attributions" target="_blank">présentation des publicités</a> qui affectent l'attribution. Indiqué avec les valeurs 0 et 1 comme suit : </span></p><ul><li><span>Publicités post vue (0)</span></li><li><span>Publicités rendues par StoreKit (1)</span></li></ul><p>Ne pas tenir compte de la valeur du champ si la version de SKAN est antérieure à 2.2.</p></td><td>Entier</td><td>Oui</td></tr><tr><td><p>ad_network_source_app_id (1)</p></td><td>Réseau publicitaire</td><td><span>ID de l'application de l'éditeur communiqué par le réseau publicitaire. Utilisé pour réconcilier les coûts ; rapporté par le réseau publicitaire. La base de ces données est fournie par l'application de l'éditeur.</span></td><td>Chaîne</td><td>Non</td></tr><tr><td><p>ad_network_channel (1)</p></td><td>Réseau publicitaire</td><td> </td><td>Chaîne</td><td>Non</td></tr><tr><td><p>af_prt (1)</p></td><td>Réseau publicitaire</td><td> </td><td>Chaîne</td><td>Non</td></tr><tr><td><p>min_revenue </p></td><td>AppsFlyer</td><td>Voir note (4)</td><td>Nombre réel</td><td>Non</td></tr><tr><td><p>max_revenue </p></td><td>AppsFlyer</td><td>Voir note (4)</td><td>Nombre réel</td><td>Non</td></tr><tr><td><p>event_revenue</p></td><td>AppsFlyer</td><td><p>Formule : [somme des valeurs de l'événement spécifique en USD]/[nombre d'événements survenus un jour donné].</p></td><td>Float</td><td>Oui</td></tr><tr><td><p>min_event_counter</p></td><td>AppsFlyer</td><td>Permet de calculer le nombre de fois qu'un utilisateur effectue un événement. Voir note (3)</td><td>Entier</td><td>Non</td></tr><tr><td><p>max_event_counter</p></td><td>AppsFlyer</td><td>Voir note (3)</td><td>Entier</td><td>Non</td></tr><tr><td><p>min_time_post_install</p></td><td>AppsFlyer</td><td>Voir note (5)</td><td>Entier</td><td>Non</td></tr><tr><td><p>max_time_post_install</p></td><td>AppsFlyer</td><td>Voir note (5)</td><td>Entier</td><td>Non</td></tr><tr><td><p>af_attribution_flag</p></td><td>AppsFlyer</td><td><p>Lorsque la fonctionnalité SSOT (Source Unique de Vérité) est activée : si TRUE, l'installation a été attribuée à la fois par AppsFlyer et SKAN. Si FALSE, l'installation n'a pas été attribuée par AppsFlyer. Si la valeur skad_conversion_value est nulle, l'indicateur est soit true, soit false (en fonction de la <a href="./skan-modeled-data#null-conversion-values" target="_blank">modélisation</a>).</p></td><td>Booléen</td><td>Non</td></tr><tr><td><p>measurement_window</p></td><td>AppsFlyer</td><td>Durée de la fenêtre d'activité. 24 heures par défaut. </td><td>Entier</td><td>Non</td></tr><tr><td><p>Durée</p></td><td>AppsFlyer</td><td>Intervalles de la fenêtre d'activité. </td><td>Entier</td><td>Non</td></tr><tr><td><p>user_agent</p></td><td>AppsFlyer</td><td>Agent utilisateur du dispositif</td><td>Chaîne</td><td>Non</td></tr><tr><td><p><span>skad_postback_sequence_index</span></p></td><td><span>4.0 (iOS 16.2)</span></td><td><ul><li><span>La valeur représente la fenêtre SKAN, soit <code>0</code>, <code>1</code> ou <code>2</code>. </span></li><li><span>Pour SKAN 3, la valeur est <code>0</code></span></li></ul></td><td><span>Entier</span></td><td><span>Oui</span></td></tr><tr><td><span>skad_coarse_conversion_value</span></td><td><p><span>4.0 (iOS 16.2)</span></p></td><td><ul><li><span>La valeur peut être <code>low</code>, <code>medium</code> ou <code>high</code>. </span></li><li><span>Pour SKAN 3, la valeur est <code>nulle</code>.</span></li></ul></td><td><span>Chaîne</span></td><td><span>Oui</span></td></tr><tr><td><span>skad_source_identifier</span></td><td><span>4.0 (iOS 16.2)</span></td><td><ul><li><span>La valeur peut inclure jusqu'à 4 chiffres. </span></li><li><span>Pour SKAN 3, la valeur est<code>nulle</code>. </span></li></ul></td><td><span>Chaîne</span></td><td><span>Oui</span></td></tr><tr><td><span>skad_source_domain</span></td><td><span>4.0 (iOS 16.2)</span></td><td><ul><li><span>La valeur représente la source des publicités web attribuables. </span></li><li><span>Pour SKAN 3, la valeur est <code>nulle</code>.</span></li></ul></td><td><span>Chaîne</span></td><td><span>Oui</span></td></tr><tr><td><span>ad_network_creative</span></td><td><span>Réseau publicitaire</span></td><td><ul><li><span>La valeur est basée sur l'enrichissement des données reçues du réseau publicitaire. </span></li><li><span>Pour SKAN 3, la valeur est <code>nulle</code>.</span></li></ul></td><td><span>Chaîne</span></td><td><span>Non</span></td></tr></tbody><tfoot><tr><td colspan="4"><p>\*\* Apple détermine si le champ est rempli à l'aide d'un mécanisme de seuil de confidentialité</p><p>(1) Depuis le 2 juin 2021, le champ est ajouté aux rapports mais n'est pas nécessairement rempli.</p><p>(3) Pour déterminer le nombre de fois qu'un utilisateur effectue un événement in-app donné, utilisez la formule suivante : <code>[arrondi (min_event_counter + max_event_counter) / 2].</code> Vous devez arrondir <mark>au nombre entier le plus proche.</mark><br/>Exemple :<br/>A. Si min = 0 et max = 1, la moyenne est de 0,5 ; l'arrondi supérieur donne un résultat de 1.<br/>B. Si min = 5 et max = 10, la moyenne est de 7,5 ; l'arrondi supérieur donne un résultat de 8.</p><p>(4) Les revenus sont toujours indiqués dans le champ <code>skad_revenue</code>. Si vous utilisez <span>SKAN 4</span> ou le <span><a href="./skan-conversion-studio" target="_blank">mode personnalisé</a></span>, l'intervalle de compartiments associé à l'événement et utilisé pour calculer skad_revenue est défini par min_revenue et max_revenue.</p><p>(5)</p><ul><li>Avec la conversion personnalisée : AppsFlyer calcule le temps d'installation comme le temps d'arrivée du postback - 36h - moyenne (min_time_post_install + max_time_post_install). Toutefois, si CV=0, la moyenne (min_time_post_install + max_time_post_install) est considérée comme 0. </li><li>Dans la conversion de décodage : min_time_post_install est inférieur d'une heure à la valeur définie dans le max_time_post_install qui est égal à <a href="./skan-cv-decode-map-your-cv-to-events#decode-csv-file-specification" target="_blank">hours_from_install</a> que vous avez défini dans votre conversion de décodage. </li></ul></td><td></td></tr></tfoot></table>

</Accordion>

## Informations supplémentaires

<div id="traits-and-limitations" />

<Accordion title="Caractéristiques et limitations">

| Caractéristique | Remarques |
| --- | --- |
| Accès du réseau publicitaire | Les ad networks sont fournis avec des postbacks |
| Autorisations de l'agence | Non disponible |
| Transparence de l'agence | S/O |
| Fuseau horaire | UTC |
| Devise | USD |
| Données organiques | En fonction des données d'événements du SDK. Par exemple, les métriques d'installation organique sont calculées comme suit : les données de toutes les installations rapportées par le SDK moins les installations non organiques rapportées par SKAN. |
| Données non organiques | Basé sur les postbacks SKAN |
| Actualisation des données | Quotidiennement. Le calendrier SKAN signifie qu'iOS signale une installation 24 à 48 heures après la fermeture de la fenêtre. |
| Données historiques | Limité à la fenêtre de disponibilité de Data Locker. |
| Accès utilisateur du compte | Disponible. Selon les permissions du compte |

</Accordion>

> 📄 **À consulter également**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide#reporting-options">Rapports SKAN disponibles (Guide de la solution SKAN)</Anchor>

<div data-zendesk-anchors="skan-raw-data-reports=rapports-de-donn%C3%A9es-brutes-skan 01H8XHATZB2G6YZ9AJNPRZS59Y=rapports-de-donn%C3%A9es-brutes-skan skan-raw-data-report-format-and-content=format-et-contenu-du-rapport-sur-les-donn%C3%A9es-brutes-skan 01H8XHATZCJQZTZF0Y5P18XMEA=format-et-contenu-du-rapport-sur-les-donn%C3%A9es-brutes-skan 01H8XHATZCR5BC2P5TSQTMDY5Q=raw-data-report-types 01H8XHATZC0MST5ASGWDGGK2R8=raw-data-field-format-types field-formats=formats-de-champs 01H8XHATZCZMNGK72DDE5HS6E9=formats-de-champs 01H8XHATZC24DH4AYB2C523JDH=fields-available-in-postback-and-postback-copy-reports 01H8XHATZCNXVG0E3MZ9H68AA1=fields-available-in-decoded-event-reports additional-information=informations-suppl%C3%A9mentaires 01H8XHATZD9D7JBHTFZ095EBD5=informations-suppl%C3%A9mentaires 01H8XHATZDMV0VN4BDTECGF91K=traits-and-limitations h_01HDNYQBVZP0A6SQASGDRFVFGP=%C3%A0-consulter-%C3%A9galement" />
