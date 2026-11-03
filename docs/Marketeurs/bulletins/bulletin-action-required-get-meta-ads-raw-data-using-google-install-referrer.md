---
title: >-
  Bulletin : Action requise - Obtenir les données brutes des Meta ads à l'aide
  de Google Install Referrer
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2021-10-21T07:02:51Z'
  edited_at: '2023-11-27T14:03:09Z'
  id: 4409322107537
  locale: fr
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/fr/articles/4409322107537
---

<Table>
  <tbody>
    <tr>
      <td>
        **Quoi de neuf ?**
      </td>
      <td>
        Obtenez les données brutes de campagne Meta ads des publicités qui répondent au Google Play Store à l'aide du référent d'installation.
      </td>
    </tr>
    <tr>
      <td>
        **Ce qui a changé**

        **![Information_icon.png](https://files.readme.io/cc1ff74668360a2be64ec90db8f771d751b0a95847ecaee582c2e31c60e310cf-20445036062993.png)**
      </td>
      <td>
        Depuis le 29 octobre 2021, les données d'attribution de niveau utilisateur (données brutes) des utilisateurs conduits par Meta ads **après** cette date sont restreintes. Meta ads met ces données à la disposition des MMP comme AppsFlyer, mais pas à celle des annonceurs.

        Toutefois, si la publicité dirige les utilisateurs vers Google Play Store, les annonceurs disposent de champs d'attribution dans le référent d'installation de Google, qui doit être <Anchor target="_blank" href="/marketers/fr/docs/basic-sdk-integration-guide#attribute-apps-published-on-google-play">intégré à votre application</Anchor>. Les champs fournis via le référent renseignent les rapports de données brutes AppsFlyer mis à votre disposition et permettent à AppsFlyer d'attribuer les utilisateurs qui n'ont pas d'identifiant publicitaire (LAT activée).

        L'utilisation du procédé de référent nécessite d'avoir le SDK AppsFlyer V5.4+.

        **Remarque** : les données du référent ont la priorité sur les données fournies par l'API, et elles ne sont pas limitées.

        Les données du référent sont cryptées par Meta ads, puis décryptées à l'aide d'une clé disponible dans votre compte de développeur Meta ads. Vous devez nous fournir la clé de décryptage en suivant les actions indiquées dans la ligne.

        **Champs d'attribution de campagne disponibles via le référent :**

        * Identifiant de publicité
        * Nom de la publicité
        * Identifiant de l'ensemble de publicités
        * Nom d'adset
        * Identifiant de la campagne
        * Nom de la campagne
        * ID de compte
        * Canal
        * Type de publicité (ce champ n'est pas encore disponible)

        **Remarque**:

        * Aucun autre champ n'est disponible via le référent.
        * Cette solution s'applique à l'attribution post clic et non à l'attribution post vue.
        * Les données du référent ne s'appliquent pas aux campagnes de réengagement, car les utilisateurs ne passent pas par le store.

        **Quand AppsFlyer a-t-il appliqué ce changement ?**

        * Depuis le 29 octobre 2021 :
          * Les restrictions de Meta ads pour les données post clic (c'est à dire les données brutes d'attribution) sont effectives.
          * Les annonceurs peuvent mettre à jour la clé de décryptage du référent dans AppsFlyer.
        * Depuis le 3 novembre 2021 :
          * AppsFlyer renseigne les données brutes et les attribut en utilisant les données fournies par le principe de référent.
      </td>
    </tr>
    <tr>
      <td>
        **Résumé de la disponibilité des données**
      </td>
      <td>
        <table><tbody><tr><th rowspan="2">Moyen d'attribution</th><th rowspan="2">Source des données d'attribution</th><th colspan="2">Données disponibles pour les annonceurs </th><th>Remarques</th></tr><tr><th>Données Brutes</th><th>Données agrégées</th><th> </th></tr><tr><td>Post-clic</td><td>Référent (s'applique aux apps Android téléchargées dans Google Play Store)</td><td>Disponible</td><td>Disponible</td><td><ul><li>Données d'attribution des utilisateurs LAT disponibles.</li><li>Le référent a la priorité sur les données MMP si les deux sont disponibles.</li><li>Ne s'applique pas aux campagnes de réengagement.</li></ul></td></tr><tr><td>Post-clic</td><td>API MMP</td><td>Restreint\*</td><td>Disponible</td><td> </td></tr><tr><td>Fraude de visibilité</td><td>API MMP</td><td>Restreint\*</td><td>Disponible</td><td>Le mécanisme de référent n'est pas pris en charge.</td></tr><tr><td colspan="5"><p><strong>Remarque :</strong> lorsque la disponibilité des données est limitée,</p><ul><li><ul><li>Les postbacks d'installation et d'événements in-app sont envoyés aux réseaux publicitaires restrictifs uniquement. Les partenaires tiers, tels que les partenaires analytiques, n'obtiennent pas de postback en cas d'attribution restreinte. </li><li>Les postbacks non attribués (ne contenant pas de champs d'attribution) sont envoyés aux réseaux publicitaires qui ont été configurés pour recevoir l'ensemble des événements (y compris les événements organiques et non attribués). Cela inclut les partenaires de gestion des campagnes Meta.</li></ul></li></ul></td></tr></tbody></table>
      </td>
    </tr>
    <tr>
      <td>
        **Action requise**
      </td>
      <td>
        **Pour obtenir votre clé de décryptage depuis Meta ads :**

        [Les informations suivantes sont basées sur les données fournies par Facebook.]

        1. Connectez-vous au portail des développeurs Meta.
        2. Allez dans **Mes Apps** (en haut à droite).
        3. Sélectionnez l'app pour laquelle vous souhaitez accéder à votre clé de décryptage.
        4. Accédez à **Paramètres** > **Basique** à gauche de la page.  

           [![FBUIforKey.png](https://files.readme.io/7581629ac17217154300bc796fd54416c1b04c08353b21ae7b93662fe182f694-4409669308049.png)](https://files.readme.io/7581629ac17217154300bc796fd54416c1b04c08353b21ae7b93662fe182f694-4409669308049.png)
        5. Faites défiler l'écran vers le bas jusqu'à la section **Android**. Vous pourrez accéder à votre clé de décryptage avec le message **Clé de décryptage du référent d'installation** , sous le champ **Nom du Package**. **Remarque** : Il s'agit de la même section que celle où vous avez configuré le nom de votre package et le Google Play Store.

        **Pour activer le mécanisme de référent dans AppsFlyer.**

        1. [Obligatoire] Vérifiez que votre app utilise AppsFlyer SDK V5.4 et +. Ne vous fiez pas aux versions antérieures.
        2. Effectuez l'une des opérations suivantes :
           1. [Prochainement] Définissez la clé de décryptage via l'API.
           2. Pour définir la clé de décryptage via l'interface utilisateur :
              1. Dans AppsFlyer, allez dans **Configuration** > **Intégrations actives**.
              2. Sélectionnez Meta ads.  

                 ![meta-ads-install-referrer-decryption-key.png](https://files.readme.io/adf6caa8d7cee493695eb8fb7db1b61c60e6a1cef0273e615c43a05ad8a9485d-13963525463825.png)
           3. Dans l'onglet **Integration**, collez la clé dans **Clé de décryptage du référent d'installation**.
           4. Cliquez sur **Enregistrer l'intégration**.
      </td>
    </tr>
    <tr>
      <td>
        **Mise à jour de la clé de décryptage via l'API**
      </td>
      <td>
        **[Prochainement]**

        Nous allons sortir une API qui mettra à jour la clé de décryptage.
      </td>
    </tr>
    <tr>
      <td>
        **Disponibilité des données brutes dans le temps**
      </td>
      <td>
        * Si les données d'attribution sont obtenues via le principe de référent, les données ne sont pas limitées et sont disponibles via les rapports de données brutes.
        * Si les données d'attribution sont obtenues via API, les données brutes des utilisateurs conduits par Meta ads sont attribuées à la source média *restreinte*.
        * Ce changement n'impacte pas les données brutes des utilisateurs conduits avant le changement. C'est à dire avant le 29 octobre 2021, 08:00 UTC.
      </td>
    </tr>
    <tr>
      <td>
        **Ce qui ne change pas**
      </td>
      <td>
        AppsFlyer continue à recevoir des données de niveau appareil depuis Meta ads. Cela signifie que nos capacités d'attribution et de rapports (y compris : attribution multi-touch, LTV, ROI, cohorte, rapports de rétention, protection contre la fraude, Audiences, et autres services) restent inchangées. Voir les <Anchor target="_blank" href="/marketers/fr/docs/aggregated-and-analytics-reporting-overview">outils de reporting agrégé et analytique</Anchor>.

        **Remarque** : Si vous nous fournissez la clé de décryptage, nous pouvons attribuer des utilisateurs qui n'ont pas d'identifiant publicitaire (LAT activé). Ceci permet de rendre l'attribution plus précise.
      </td>
    </tr>
    <tr>
      <td>
        **Modifications de l'attribution**
      </td>
      <td>
        Le deep linking différé via GCD sera disponible pour les applications Android qui utilisent le principe de référent Google Install. Il n'est pas disponible pour les applications iOS.
      </td>
    </tr>
    <tr>
      <td>
        **FAQ**
      </td>
      <td>
        * **La clé de décryptage du référent d'installation doit-elle être mise à jour ?**  
          Une fois transmise, la clé de décryptage n'a pas besoin d'être mise à jour.
        * **Quand puis-je voir les données de niveau utilisateur dans les rapports de données brutes ?**  
          Les données de niveau utilisateur sont affichées dans des rapports de données brutes une fois qu'une clé de décryptage de référent d'installation valide est soumise, et qu'une installation est attribuée à Meta ads.
        * **Les données d'attribution de niveau de utilisateur sont-elles disponibles pour les installations effectuées entre le 29 octobre 2021 et le 3 novembre 2021 ?**  
          Malheureusement non, ces données ne sont pas disponibles.
      </td>
    </tr>
  </tbody>
</Table>
