---
title: Interopérabilité de SKAdNetwork (SKAN) avec Meta ads
metadata:
  keywords:
    - Facebook
    - Advertisers
    - Marketers
    - SKAN
    - SKAdNetwork
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-01-17T10:08:28Z'
  edited_at: '2023-11-12T12:52:24Z'
  id: 360017095198
  locale: fr
  section: SKAN interoperation
  section_id: 6552115163153
  url: https://support.appsflyer.com/hc/fr/articles/360017095198
---
> **En bref :** l'interopérabilité permet aux Meta ads de transmettre à AppsFlyer les données SKAN décodées, et elle autorise AppsFlyer à partager les bits de mesure de votre CV (mapping) avec les Meta ads.

<Embed title="Interopérabilité de SKAdNetwork (SKAN) avec Meta ads" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/15jnbml3h7" providerUrl="https://fast.wistia.com" />

<div id="skan-interoperability-appsflyer---meta-ads" />

## Interopérabilité de SKAN : AppsFlyer &lt;-> Meta ads

Si vous travaillez avec plusieurs partenaires de réseau publicitaire, nous vous conseillons de le configurer dans AppsFlyer. Les résultats de performance SKAN, accompagnés d'autres indicateurs comme le coût, seront ainsi disponibles via la plateforme AppsFlyer.

<div id="scope-of-skan-interoperability-with-meta-ads" />

#### Possibilités d'interopérabilité SKAN / Meta ads

L'interopérabilité avec les Meta ads permet :

* AppsFlyer et Meta ads partagent le schéma de valeur de conversion (CV) SKAN, ce qui leur permet de vous fournir des métriques de performance.
* AppsFlyer prend en charge tous les objectifs de campagne Meta Ads qui viennent optimiser les campagnes :
  * Installation d’applications mobile (MAI, Mobile app install)
  * Engagement des applications mobile (MAE, Mobile app engagement)
  * Optimisation de valeur (VO, Value optimization)
* Après avoir activé l’intégration SKAN, les événements suivants se produisent :
  * Le SDK Facebook arrête la mise à jour de la VC SKAN*(kill switch).*
  * Le SDK AppsFlyer met la VC à jour.
  * Meta ads partage les données de postback SKAN à inclure dans le tableau de bord SKAN et les rapports agrégés.

Autres considérations :

* Si vous n’activez pas l’intégration des partenaires SKAN, dans le tableau de bord SKAN les installations en provenance de Meta ads sont comptées comme des installations organiques.
* Dans le contexte de l'attribution AppsFlyer (Tableau de bord général) :
  * Les installations des utilisateurs consentants effectuées par Meta ads sont attribuées correctement.
  * Les utilisateurs non consentants sont attribués comme organiques.
* <Anchor target="_blank" href="/marketers/fr/docs/self-reporting-networks-srns#ios-145-srn-attribution">Implications relatives à iOS 14.5 pour le reporting SRN</Anchor>
* Notre intégration MMP avec Meta ads implémente systématiquement le drapeau *Suivi d'annonceur activé*. (Ces informations sont conformes à la liste de vérification iOS 14 pour l'app Meta ads publiée en février 2021.)

<div id="considerations" />

#### Attention

* Une fois que l'interopérabilité est activée, à chaque fois que vous modifiez les paramètres de mesure vous n'avez pas à répéter le processus d'intégration MMP décrit dans cet article. Vous n'avez donc pas besoin de copier à nouveau l'URL de connexion MMP.
* Dans AppsFlyer, si vous désactivez la mesure SKAN, Meta ads ne peut plus obtenir de mappage de la CV.
* SDK AppsFlyer ou SDK Facebook : le SDK Facebook convient si vous exécutez des campagnes uniquement avec Meta ads. Si vous exécutez des campagnes avec plusieurs partenaires, le SDK AppsFlyer vous permet d'afficher les données de tous les partenaires.
* Consultez la section [sur les différences](/docs/skadnetwork-skan-interoperation-with-meta-ads#troubleshooting-discrepancies-and-faq) dans cet article.

<div id="meta-ads-app-install-ads-guidance" />

#### Conseils pour l'installation d'une app Meta ads

Lors de la configuration de vos campagnes d'installation d'une app Meta ads avec iOS 14, suivez les <Anchor target="_blank" href="https://developers.facebook.com/blog/post/2020/10/29/preparing-our-partners-ios-14-latest-guidance-on-skadnetwork/">conseils Meta ads</Anchor> suivants : 

* Un maximum de 9 campagnes par app, avec 5 adsets autorisés chacune. Les annonceurs peuvent diffuser ces 9 campagnes d’app sur 9 comptes publicitaires par ID d’app.
* Vous n’avez pas besoin d’un compte séparé pour les campagnes iOS 14. Vous pouvez exécuter des campagnes iOS 14 à partir de comptes existants.
* Il existe une relation entre la méthode d’optimisation Meta ads et le type de mesure que vous sélectionnez dans AppsFlyer, comme suit :
  * **Mesure des revenus** : VO et AEO
  * **Mesure de conversion** : AEO — Inclut les événements Meta ads standard et les événements d'achat. Vous devez mapper l’événement d’app dans AppsFlyer à l’événement Meta ads concerné.

<div id="interoperation-procedures" />

## Procédures d’interopérabilité

Suivez les procédures qui suivent pour utiliser l’interopérabilité.

Pour l’attribution des installations de l’app :

<div id="allow-facebook-to-share-skadnetwork-data-with-appsflyer" />

<Accordion title="Autorisez Meta ads à partager des données SKAN avec AppsFlyer">

Autorisez Meta ads à partager des données SKAN avec AppsFlyer. Si vous ne le faites pas, vous ne verrez pas les installations SKAN attribuées à Meta ads dans le tableau de bord SKAN AppsFlyer.

Cette procédure doit être effectuée pour chaque app.

**Pour autoriser Meta ads à partager les données SKAN avec AppsFlyer :**

1. Dans AppsFlyer, allez dans **Configuration** > **Intégrations actives**.
2. Recherchez et sélectionnez Meta ads.
3. Ouvrez l'onglet **SKAN**.

   ![skan_repprtiing_-_connected_accounts.png](https://files.readme.io/41514c220de398871292c990e448e2bc8ce450a17512649842cdb2bc4fd78846-40032591356817.png)
4. Cliquez sur **f login**. Le compte que vous utilisez doit être un compte Admin ou Annonceur <Anchor target="_blank" href="https://www.facebook.com/business/help/155909647811305?id=829106167281625">disposant des autorisations suivantes</Anchor> :
   * L'autorisation Ads\_read Cf [Vérifier que vous disposez d’une autorisation de lecture des publicités](/docs/skadnetwork-skan-interoperation-with-meta-ads#verifying-the-ads_read-permission).
   * Accès à l'ID de l'app dont la promotion est faite dans les paramètres Meta Business Partner.
5. Suivez les instructions de l’interface utilisateur.  
   Meta génère un <Anchor target="_blank" href="https://developers.facebook.com/docs/facebook-login/guides/access-tokens/get-long-lived/">jeton d'accès</Anchor> qui permet le partage des données avec AppsFlyer. Une fois la procédure terminée, vous serez redirigé vers AppsFlyer.
6. Si vous configurez cette intégration pour la première fois, vérifiez que le statut de compte **En attente de synchronisation** s'affiche.  
   Ce message s'affichera jusqu'à ce que nous obtenions des données de Meta ads.
7. Attendez 02:00 UTC le lendemain, puis vérifiez que le statut est passé à **Les données ont bien été extraites.**  
   Les données du tableau de bord SKAN sont mises à jour quotidiennement à 08 h UTC.
8. Lisez la section sur [les différences de mesure](/docs/skadnetwork-skan-interoperation-with-meta-ads#measurement-and-timing-differences-between-appsflyer-and-facebook).

</Accordion>

Pour l'attribution d'événements in-app :

<div id="share-cv-schema-with-facebook" />

<Accordion title="Partager le schéma du CV avec Meta ads">

![SKAdNetwork-Facebook-AppsFlyer_integration__5_.png](https://files.readme.io/f5965dc535a47b3d665a3cf1ae1df564a176ff9be76d5fb4a9f01d80b0e58994-40032652599953.png)

<div id="enabling-appsflyer-skan-interoperation-with-meta-ads" />

#### Activation de l'interopérabilité AppsFlyer SKAN avec Meta ads

<Table>
  <thead>
    <tr>
      <th>
        Étape
      </th>
      <th>
        Action
      </th>
      <th>
        Détails
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="1"></span>
        1
      </td>
      <td>
        Configuration de l'app requise
      </td>
      <td>
        * Utilisez le <Anchor target="_blank" href="/marketers/fr/docs/sdk-integration-overview">SDK</Anchor> AppsFlyer le plus récent dans votre app.
      </td>
    </tr>
    <tr>
      <td><span id="2"></span>
        2
      </td>
      <td>
        Examen des paramètres SKAN
      </td>
      <td>
        Vérifiez que la <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide">solution SKAN</Anchor> AppsFlyer est configurée et activée. Cela permet au SDK AppsFlyer d’appeler les API SKAN et de définir la VC.

        **Pour visualiser les paramètres SKAN** :

        1. Dans AppsFlyer, ouvrez **Configuration** > **Studio de Conversion SKAN**.
        2. Cliquez sur l'icône des options ⋮, et vérifiez que la **mesure SKAN** est bien activée.  
            [![Measurement_mode_on_facebook_ads.png](https://files.readme.io/310ec3b7cb313dfbf00e073ab808231f48a995e7e6a5c482ccd6c997a3714483-40032652602257.png)](https://files.readme.io/310ec3b7cb313dfbf00e073ab808231f48a995e7e6a5c482ccd6c997a3714483-40032652602257.png)
        3. Sélectionnez votre mode de mesure préféré.  
           En savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>.
        4. Notez les noms exacts des événements définis. Vous en aurez besoin à l’étape suivante. **Remarque :** les noms sont sensibles à la casse.
      </td>
    </tr>
    <tr>
      <td><span id="in-app-event-mapping"></span>
        3
      </td>
      <td>
        Mappage d'événements in-app
      </td>
      <td>
        Vérifiez et, si nécessaire, modifiez vos mappages d'événements in-app.

        **Pour afficher et définir des mappages d’événements in-app** :

        1. Dans AppsFlyer, allez dans **Configuration** > **Intégrations actives**.
        2. Sélectionnez **Meta ads**.
        3. [Obligatoire] Dans l'onglet **Integration**, activez **Postbacks d'évènement in-app**.  
           * Vous devez mapper le type de mesure SKAN qui est sélectionné. Le type de mesure par défaut est le revenu.  
             ![in-app_events_fb_en-us.png](https://files.readme.io/98e2c8048444331c5d24343e683605e8388ee93bbfcb70aa5e8dad183c995859-40032591364241.png)
           * Vérifiez que les événements in-app définis dans la mesure SKAN (**événements AppsFlyer**) sont mappés aux identifiants d'événements Meta ads (**mappés à l'événement partenaire**). Si vous ne mappez pas les événements, Meta ads ne pourra rien optimiser et ne comptabilisera que les installations.  

             <div id="h_01H8XRMVR5GY77K7GJ4TXGWEHS" />

             > 📘 **Note**
             >
             > Lorsque vous ajoutez, modifiez ou supprimez une valeur de conversion (CV) dans SKAN Conversion Studio, vérifiez que l’événement est correctement mappé dans les **postbacks d’événements in-app**. Dans le cas contraire, la CV ne sera pas mise à jour sur Meta ads. 
             >
             > #### <span id="inapp-event-mapping-guide"></span>Guide de mappage d'événements in-app


        | Type de mesure | Exigence relative au mappage |
        | --- | --- |
        | <span id="custom"></span><Anchor target="_blank" href="/marketers/fr/docs/skan-conversion-studio#custom">Personnalisation</Anchor> | Mappez les événements in-app que vous avez configurés dans « Personnalisé » aux événements Meta ads correspondants.<br /><br />Pour transmettre les revenus par postback, vous devez définir **Envoyer les revenus** sur **Valeurs et revenus**.<br /><br />![SendValueandRevenue.png](https://files.readme.io/412c60db2b09d80a989b7546a6819aa1b030732e0ce004b323dc09db1015c238-11331054047377.png)<br /><br />*af\_skad\_revenue* est utilisé pour les revenus globaux et mappé à l’événement de revenus Meta ads, généralement *fb\_mobile\_purchase.*<br /><br />Remarque ! Il est possible de mapper plus d’un événement à *fb\_mobile\_purchase*. |
        | <span id="revenue"></span>Revenu | Si vous signalez les revenus aux réseaux publicitaires via postback, vérifiez que le mappage de vos postbacks d'événements in-app incluent les événements de revenus in-app que vous avez définis.<br /><br />*af\_skad\_revenue* est utilisé pour les revenus globaux et mappé à l’événement de revenus Meta ads, généralement *fb\_mobile\_purchase.*<br /><br />Remarque ! Il est possible de mapper plus d’un événement à *fb\_mobile\_purchase*. |
        | <span id="conversion"></span>Conversion | Mappez 1 à 6 événements de conversion aux événements Meta ads correspondants. |

        4. Cliquez sur **Enregistrer l'intégration**.
        5. Faites défiler jusqu’à la section **Configuration SKAN** et cliquez sur l'**URL de connexion MMP** pour la copier. Dans le paragraphe suivant, nous vous indiquerons où coller l’URL dans Meta.  

           ![meta_ads_skan_configuration_mmp_url.png](https://files.readme.io/341918a757014d51a240898d157a6576b50cb269ad3bd0a574e4e6aef9d504ef-40032652607377.png)
      </td>
    </tr>
    <tr>
      <td><span id="4"></span>
        4
      </td>
      <td>
        Connecter AppsFlyer aux Meta ads
      </td>
      <td>
        1. Dans Meta ads, ouvrez le gestionnaire d'événements.

           [<Image alt="FacebookSkadNetworkSetup.jpg" src="https://files.readme.io/8720d8f951915091df74bbe1b1154a1c5af80a547f81bb70bf66ac74f5ff6e54-40032652609297.jpg" width="503px" />](https://files.readme.io/8720d8f951915091df74bbe1b1154a1c5af80a547f81bb70bf66ac74f5ff6e54-40032652609297.jpg)
        2. Allez dans l'onglet **Paramètres**.  

           [![mceclip0.png](https://files.readme.io/0db272073a261c6e1b214110aa722dda53c73d5cf07a6590b2afd8f2b6f16126-360016584877.png)](https://files.readme.io/0db272073a261c6e1b214110aa722dda53c73d5cf07a6590b2afd8f2b6f16126-360016584877.png)
        3. Dans la section Configurer des événements d'app pour SKAN, cliquez sur Configurer les événements.

           [![mceclip1.png](https://files.readme.io/61d55b6fe05055fbc9b8db5a412c6da7d80807abec4b6b31a7b357fb76fcdf34-40032652611729.png)](https://files.readme.io/61d55b6fe05055fbc9b8db5a412c6da7d80807abec4b6b31a7b357fb76fcdf34-40032652611729.png)
        4. Sélectionnez **Importer à partir de l'app partenaire**.  
           Un champ permettant de coller **l’URL de connexion MMP** s’affiche.   
           Cela met à jour Meta avec le mappage de CV et **indique au SDK Facebook de votre app d’arrêter de définir la CV**. Si l’importation à partir de l’application partenaire est désactivée, procédez à un [dépannage.](/docs/skadnetwork-skan-interoperation-with-meta-ads#import-from-partner-app-is-disabled)
        5. Suivez les instructions de l’interface utilisateur Meta ads. L'un des événements suivants se produit :
           1. Collez **l’URL de connexion MMP** dans l’interface utilisateur de Meta ads. Voilà ! Vous avez terminé l’intégration. Veuillez lire les notes qui suivent.
           2. Le collage de **l’URL de connexion MMP** échoue et un message d’erreur s’affiche dans l’interface utilisateur de Meta ads. Le cas échéant :  
              - Attendez 24 heures, puis répétez la procédure.  
              - Si l’erreur persiste (plus de 24 heures), contactez le support AppsFlyer.

        Remarques

        * Vous ne devez effectuer cette procédure qu'une seule fois. Cela signifie qu'il n'est pas nécessaire de copier-coller l'URL de connexion après avoir modifié les paramètres de mesure dans AppsFlyer. Par exemple, si vous passez de la mesure des revenus à la mesure des conversions, Meta ads utilise l'URL existante pour obtenir la structure requise.
        * Terminer la procédure permet à Meta ads d'obtenir le schéma de CV d'AppsFlyer à l'aide d'une structure aléatoire propriétaire. Vous n'avez pas la possibilité de configurer ceci.
        * Il faut compter jusqu'à 24 heures pour que les paramètres de mesure mis à jour prennent effet sur Meta ads.
      </td>
    </tr>
    <tr>
      <td><span id="5"></span>
        5
      </td>
      <td>
        Paramètres de campagne iOS 14
      </td>
      <td>
        Dans Meta ads, vérifiez que le paramètre de campagne iOS 14 est activé.

        Ce paramètre se trouve sur la page des paramètres de la **campagne de nouvelles installations d'app**.

        [![FBiOS14.png](https://files.readme.io/3f45a8480affad430adaac46a603bf43b47e8254314226077e5d9f8255ca2e97-40032652616209.png)](https://files.readme.io/3f45a8480affad430adaac46a603bf43b47e8254314226077e5d9f8255ca2e97-40032652616209.png)
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="still-not-working" />

<div id="quick-fix-checklist" />

<div id="not-seeing-skan-inapp-events-from-meta" />

<div id="additional-information" />

## Informations supplémentaires

<div id="turning-off-the-skan-integration" />

<Accordion title="Désactivation de l’intégration SKAN">

Lorsque vous désactivez votre intégration Meta Ads, il ne suffit pas seulement de décocher **Activer le partenaire**, vous devez également supprimer chaque connexion SKAN pour que les données SKAN cessent d'être enregistrées.

**Pour désactiver l’intégration SKAN :**

1. Dans AppsFlyer, ouvrez **Configuration** > **Partenaires intégrés**.
2. Recherchez et sélectionnez Meta ads.
3. Ouvrez l'onglet **SKAN**.
4. Cliquez sur l’icône suppression dans le compte que vous souhaitez supprimer.

</Accordion>

<div id="measurement-and-timing-differences-between-appsflyer-and-facebook" />

<Accordion title="Différences de mesure et de synchronisation entre AppsFlyer et Meta ads">

| Article | Détails |
| --- | --- |
| Noms d'événements in-app | Avant le 15 août 2021, les noms d'événements du tableau de bord utilisaient les noms d'événements Meta ads. Ce n’est plus le cas. |
| Métriques des utilisateurs convertis en mode revenus | [Obsolète depuis le 16 août 2021]<br /><br />En mode revenus, la métrique des utilisateurs convertis (utilisateurs payants) ne tient pas compte du nombre d’utilisateurs déclarant des revenus via les campagnes Meta ads, conformément à la convention de dénomination des revenus mentionnée dans la section précédente (noms d’événements in-app) |
| Première disponibilité des données | Pour la première synchronisation des données après intégration, et pour les synchronisations suivantes, AppsFlyer reçoit les données de coût de Meta ads pour les 7 derniers jours. |
| Date d'installation | AppsFlyer et Meta ads ne déterminent pas la date d’installation de la même façon. N'oubliez pas :<ul><li>Les postbacks SKAN avec iOS ne contiennent pas l'horodatage de l'installation.</li><li>Meta ads considère l’heure d’arrivée du postback comme l’heure d’installation et prend en compte le fuseau horaire de l’app dans Facebook pour définir la date.</li><li>AppsFlyer calcule l'heure d’installation en fonction des <Anchor target="_blank" href="/marketers/fr/docs/skan-conversion-studio#activity-window">paramètres de la fenêtre d’activité</Anchor>. Ni le fuseau horaire de l’app ni le fuseau horaire du compte publicitaire Meta ads ne sont pris en compte dans le calcul.</li></ul> |
| Actualisation des données | <ul><li>Nous collectons les données SKAN de Meta ads à 01:00 UTC</li><li>Les tableaux de bord et les données agrégées sont mis à jour 7 heures plus tard.</li></ul> |

</Accordion>

<div id="verifying-the-ads_read-permission" />

<Accordion title="Vérifier l'autorisation ads_read">

L'autorisation ads\_read fournit aux clients Meta Ads un accès API aux données de performances publicitaires qu'ils peuvent utiliser dans des tableaux de bord personnalisés et les analyses de données.

**Pour vérifier que votre compte Meta Ads dispose de l'autorisation ads\_read :**

1. Accédez à votre <Anchor target="_blank" href="https://developers.facebook.com/apps">compte de développeur Meta ads.</Anchor>
2. Sélectionnez un ID d’app Facebook.
3. Accédez à **Examen de l'app** > **Autorisations et fonctionnalités**.

   [<Image alt="FBad_permission.png" src="https://support.appsflyer.com/hc/article_attachments/4409499084433" width="421px" />](https://support.appsflyer.com/hc/article_attachments/4409499084433)
4. Vérifiez que **ads\_read** a le statut **Prêt**. Si tel est le cas, aucune autre action n'est requise.
5. Si vous n'avez pas l'autorisation ads\_read, vous devez la demander comme suit :
   1. Accédez à **Examen de l'app** > **Demandes**.
   2. Demandez l'autorisation **ads\_admin**.
   3. Répétez les étapes de cette procédure pour vérifier que vous avez reçu l’autorisation nécessaire.

</Accordion>

<div id="troubleshooting-discrepancies-and-faq" />

<Accordion title="Dépannage, divergences et FAQ">

| Action | Détails |
| --- | --- |
| <span id="facebook-cant-connect"></span>Meta ads ne peut pas se connecter | **Symptôme**<br /><br />Dans Meta ads, si vous recevez le message *Nous ne pouvons pas nous connecter. Vérifiez que vous utilisez la bonne URL. Si le problème persiste, contactez votre application partenaire pour obtenir de l’aide.*<br /><br />**Mesure corrective**<br /><br />Dans AppsFlyer, vérifiez que vous avez activé le mappage d'événements in-app et mappé vos événements AppsFlyer à vos événements Meta ads. (Explication dans le mappage des événements in-app décrit dans la section précédente)<br /><br />[Lignes directrices mises à jour le 20 avril 2021] |
| <span id="event-priority"></span>Priorité de l'événement | Q : Comment définir la priorité des événements dans Meta ads ?<br /><br />R : il n’est pas nécessaire de définir la priorité dans Meta ads. Cette fonctionnalité prioritaire concerne les applications qui utilisent le SDK Facebook pour définir la VC. Dans votre cas, la VC est définie par le SDK AppsFlyer. Ne tenez pas compte de l'option de priorité dans Meta ads. AppsFlyer mesure 6 événements de conversion sans priorité.<br /><br />[Lignes directrices mises à jour le 20 avril 2021] |
| <span id="event-occurrences"></span>Nombre d'évènements | Q : Pourquoi y a-t-il plus d'occurrences d'événements dans AppsFlyer que dans Meta ads ?<br /><br />R : Meta ads ne compte que les occurrences d’événements 0-1. Par conséquent, même si vous définissez plusieurs occurrences dans le cadre d’une plage, les occurrences supplémentaires ne sont comptabilisées que par AppsFlyer. |
| <span id="import-from-partner-app-is-disabled"></span>L’importation à partir de l’application partenaire est désactivée | ![ImportFromPartnerApp.png](https://files.readme.io/c124696c4a8bca7c0d95d812f5390e9672adbfd6fc510a6fa573972f5441cd02-40032591386129.png)<br /><br />**Symptôme**<br /><br />Dans Meta ads, si **l’importation à partir d’une app partenaire** est désactivée, c'est que l’app n’a jamais envoyé d’événement à Meta ads à l’aide du SDK MMP.<br /><br />**Mesure corrective**<br /><br />Effectuez l'une des opérations suivantes :<ul><li>Commencez à transmettre des événements à Meta ads à l'aide du SDK MMP dès que possible.</li><li>Commencez à transmettre des événements à Meta ads à l'aide du SDK Facebook ou de l'API d'événements d'app et utilisez l'un des autres flux pour configurer le schéma de conversion.</li></ul>Après avoir enregistré les premiers événements sur Meta ads, configurez l'intégration avec AppsFlyer.<br /><br />[Lignes directrices mises à jour le 25 avril 2021] |
| <span id="ranges-cant-overlap-and-must-be-in-consecutive-order"></span>Les plages ne peuvent pas se chevaucher et doivent se suivre | **Symptôme**<br /><br />Vous utilisez le mode de mesure personnalisé AppsFlyer SKAN. Lors de l’importation du schéma de mesure sur Meta ads, le message suivant s’affiche : *Les plages ne peuvent pas se chevaucher et doivent se suivre.*<br /><br />**Mesure corrective**<br /><br />Les valeurs de revenus dans le schéma de conversion personnalisé doivent se suivre dans un ordre croissant.<br /><br />[Lignes directrices mises à jour le 26 avril 2021] |
| <span id="sending-events-to-facebook"></span>Envoi d'événements aux Meta ads | **Q** : Faut-il envoyer des postbacks d'événements supplémentaires à Meta ads pour les événements non sélectionnés dans l'option de mesure de la CV ?<br /><br />**R** : Pour les utilisateurs ayant donné leur consentement, envoyez la gamme complète d'événements afin de permettre l'optimisation par Meta ads. |
| <span id="map-multiple-events-to-the-same-facebook-event"></span>Mappez plusieurs événements vers le même événement Meta ads | **Q** : puis-je mapper plusieurs événements in-app à un événement Meta ads ?<br /><br />**R** : si plusieurs événements sont mappés à un événement standard Meta ads, Meta ads ne sera pas en mesure de différencier les événements. Meta ads optimisera donc en fonction de l'événement qu'il reconnaît. |
| <span id="no-data-to-pull"></span>Pas de données à extraire | **Q :** Pourquoi l'état de la connexion affiche-t-il « Pas de données à extraire : vérifiez vos autorisations de partage de données Meta » ?<br /><br />**R**: Soit il n'y a pas encore de données SKAN, soit vous devez vous connecter à Meta Ads en utilisant un rôle d'admin sur le compte.<br /><br />**Q :** J'ai reçu le message « Aucune donnée à extraire : vérifiez vos autorisations de partage des données Google ». Est-ce qu'il y a un problème, même si je vois s'afficher les infos Meta Ads ?<br /><br />**R** : Oui Même si ce message d'erreur apparaît, il n'y a pas d'erreur, vos données seront extraites. |
| <span id="facebook-data-is-not-in-the-dashboard"></span>Les données Meta ads ne figurent pas dans le tableau de bord | **Symptôme**<br /><br />Dans l'onglet d'intégration SKAN, le message *Échec de l'extraction des données* s'affiche.<br /><br />![FacebookSKAdIntegration.png](https://files.readme.io/42538a59d27815b95b71ec136ebc45b8d918eebf6a2235c90fef59c467128fb2-40032591388177.png)<br /><br />**Mesure corrective**<br /><br />Vérifiez que le compte connecté est soit un admin Facebook, soit un compte d'annonceur Meta ads disposant de l'autorisation ads\_read. |
| <span id="there-is-an-error-in-facebook-when-you-try-to-run-ios-14-campaigns"></span>Une erreur se produit dans Meta ads lorsque vous essayez d’exécuter des campagnes iOS 14 | **Symptôme**<br /><br />Les éléments suivants sont avérés :<ul><li>Vous obtenez un message d’erreur dans Meta ads lorsque vous essayez d’exécuter une campagne iOS 14</li><li>Vous avez récemment ajouté à l'App Store une nouvelle application, ou une app jeune public</li></ul>Cela se produit car Meta ads ne sait pas que vous utilisez un SDK qui inclut la prise en charge de SKAN. C'est-à-dire le SDK AppsFlyer.<br /><br />**Mesure corrective**<ol><li>Dans AppsFlyer, allez dans **Configuration** > **Intégrations actives**.</li><li>Recherchez et sélectionnez **Meta ads.**</li><li>Dans l'onglet **Integration** , cochez **Activer le partenaire**.</li><li>Cliquez sur **Enregistrer l'intégration**.</li><li>Attendez 15 secondes.</li><li>Cochez **Activer le partenaire**.</li><li>Cliquez sur **Enregistrer l'intégration**.</li><li>Attendez jusqu'à 24 heures, le temps que Meta ads reçoive le signal.</li></ol> |
| <span id="revenue-reported-by-facebook"></span>Rapports de revenus pour Meta ads | [Mise à jour le 12 juillet 2021]<br /><br />Meta ads génère des revenus à partir de la VC en utilisant vos paramètres SKAN. Cependant, ce n'est pas un calcul direct, et Meta ads utilise des algorithmes pour déterminer le revenu.<br /><br />L'une des conséquences est que les revenus ont des valeurs non arrondies, même si vous mesurez les revenus en dollars entiers. |
| <span id="retroactive-data-backfill"></span>Remplissage rétroactif des données | [Mise à jour le 30 novembre 2021]<br /><br />Parfois, nous ne sommes pas en mesure de nous connecter à Meta ads pour obtenir les données, par exemple, en raison d’échecs de login. Mais nous avons une solution. Nous comblons les lacunes dans les rapports des 7 derniers jours dès que nous parvenons à nous connecter. |
| <span id="appsflyer-is-showing-significantly-more-installseventsrevenue-than-facebook"></span>AppsFlyer affiche beaucoup plus d’installations / d’événements / de revenus que Meta ads | Dans de nombreux cas, cette divergence se produit parce que le tableau de bord Meta ads affiche uniquement les installations ou événements post clic par défaut, tandis que le tableau de bord AppsFlyer affiche les installations et les événements post clic ET post vue. |
| <span id="agency-integration"></span>Intégrations d'agence | Si l’agence a un rôle d’admin dans le compte Meta Ads de l’annonceur, elle peut lancer la procédure détaillée dans cet article pour activer l’interopérabilité SKAN au nom de l’annonceur. Les annonceurs non plus n’ont pas besoin de se connecter à leur compte Meta Ads. Le login de l'agence sera indiqué dans le compte de l'annonceur. |
| <span id="an-updated-cv-doesnt-appear-on-facebook"></span>Une VC mise à jour n'apparaît pas dans Meta ads | Lorsque vous ajoutez, modifiez ou supprimez une valeur de conversion (CV) dans SKAN Conversion Studio, vérifiez que l’événement est correctement mappé dans les **postbacks d’événements in-app**. Dans le cas contraire, la CV ne sera pas mise à jour sur Meta ads. |
| <span id="modeled-data-differences-in-appsflyer-and-facebook-ads-manager"></span>Différences entre les données modélisées dans AppsFlyer et dans Meta Ads Manager | Les modèles AppsFlyer agrègent des données qu'un rapport de base SKAN ne peut pas produire. <Anchor target="_blank" href="/marketers/fr/docs/skan-modeled-data">En savoir plus</Anchor><br /><br />Lorsque AppsFlyer modélise les données, les données modélisées par Meta ads ne sont pas prises en compte car AppsFlyer s'appuie uniquement sur les données neutres et vérifiées. Il peut donc y avoir des différences de données et de résultats entre les rapports du Meta Ads Manager et ceux d'AppsFlyer. |

</Accordion>

<div id="see-also" />

> 📄 **À consulter également**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide">Guide de AppsFlyer SKANetwork</Anchor>

<div data-zendesk-anchors="skan-interoperability-appsflyer-facebook=interop%C3%A9rabilit%C3%A9-de-skan--appsflyer---meta-ads h_01H8XRMVR4JK6ZCGPQJE4D3T26=interop%C3%A9rabilit%C3%A9-de-skan--appsflyer---meta-ads scope-of-skan-interoperability-with-meta-ads=possibilit%C3%A9s-dinterop%C3%A9rabilit%C3%A9-skan--meta-ads h_01H8XRMVR4Q7HAJV0B7QB5MDPH=possibilit%C3%A9s-dinterop%C3%A9rabilit%C3%A9-skan--meta-ads considerations=attention h_01H8XRMVR43KEGWARYMD45S0VY=attention facebook-app-install-ads-guidance=conseils-pour-linstallation-dune-app-meta-ads h_01H8XRMVR48NWM47043YWT63HK=conseils-pour-linstallation-dune-app-meta-ads interoperation-procedures=proc%C3%A9dures-dinterop%C3%A9rabilit%C3%A9 h_01H8XRMVR4NVDZ23572F6KJTA9=proc%C3%A9dures-dinterop%C3%A9rabilit%C3%A9 h_01H8XRMVR4D07SWXS1TWK42DS3=allow-facebook-to-share-skadnetwork-data-with-appsflyer h_01H8XRMVR5HKXWYB3XN11V48Y0=share-cv-schema-with-facebook enabling-appsflyer-skadnetwork-interoperation-with-facebook=activation-de-linterop%C3%A9rabilit%C3%A9-appsflyer-skan-avec-meta-ads h_01H8XRMVR56T3X9MJ6KVJF0Z8W=activation-de-linterop%C3%A9rabilit%C3%A9-appsflyer-skan-avec-meta-ads h_01H8XRMVR5GY77K7GJ4TXGWEHS=note inapp-event-mapping-guide=guide-de-mappage-d%C3%A9v%C3%A9nements-in-app h_01H8XRMVR5T28Q0E8KP6BZ6CGH=guide-de-mappage-d%C3%A9v%C3%A9nements-in-app additional-information=informations-suppl%C3%A9mentaires h_01H8XRMVR5WXZ88676PAW9BKC9=informations-suppl%C3%A9mentaires h_01H8XRMVR5AW2HZD6JFDYJRNFJ=turning-off-the-skan-integration h_01H8XRMVR5HZ2BBP4XXDEFYT34=measurement-and-timing-differences-between-appsflyer-and-facebook h_01H8XRMVR58DFA2SX20ZEKZRC3=verifying-the-ads_read-permission h_01H8XRMVR5Z9H83X0TAYS50CJ9=troubleshooting-discrepancies-and-faq h_01HE7SMBXBCEQM7KF2RG3V16KV=%C3%A0-consulter-%C3%A9galement" />
