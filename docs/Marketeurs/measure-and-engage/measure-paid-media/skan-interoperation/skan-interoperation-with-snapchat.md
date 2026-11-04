---
title: Interopérabilité entre SKAN et Snapchat
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
  created_at: '2021-02-10T20:20:51Z'
  edited_at: '2024-10-24T13:19:39Z'
  id: 360017604077
  locale: fr
  section: SKAN interoperation
  section_id: 6552115163153
  url: https://support.appsflyer.com/hc/fr/articles/360017604077
---
> **En bref :** L'interopérabilité de SKAN permet d’un côté à Snapchat de transmettre les postbacks SKAN à AppsFlyer, et permet de l’autre à AppsFlyer de fournir à Snapchat le mappage des mesures de la valeur de conversion.

<div id="skan-interoperability-appsflyer---snapchat" />

## Interopérabilité avec SKAN : AppsFlyer &lt;-> Snapchat

Si vous travaillez avec plusieurs partenaires de réseau publicitaire, le mieux est de configurer votre intégration SKAN dans AppsFlyer. Les résultats de performance SKAN, accompagnés de différents indicateurs comme le coût, seront alors disponibles sur la plateforme AppsFlyer. 

**Possibilités de l'interopérabilité entre SKAN et Snapchat**

L'interopérabilité permet à AppsFlyer et Snapchat de s’échanger le mappage des valeurs de conversion SKAN, les deux peuvent ainsi vous offrir les mesures de performance. Si vous activez l'intégration du partenaire Snapchat dans AppsFlyer, AppsFlyer fournit à Snapchat des événements pour dans un souci d’optimisation.

**Guide d'installation des publicités de l'app Snapchat**

Lorsque vous configurez vos campagnes d'installation de l’app Snapchat iOS 14, gardez à l’esprit les considérations Snapchat suivantes :

*Depuis le 18 février 2021, SKAdNetwork est disponible dans Snapchat Ads Manager pour tous les annonceurs. Nous recommandons de configurer et tester les applications, afin de garantir la continuité des mesures, et pour faire en sorte que l'échelle des campagnes d'acquisition d'applications iOS 14 sur Snapchat ne soit pas un problème. À l'avenir, SKAdNetwork sera obligatoire pour accéder aux App Goal-Based Bidding dans le cadre des campagnes iOS sur Snapchat.*

*Veuillez compléter votre intégration SKAdNetwork dans votre tableau de bord AppsFlyer MMP, et configurer le mappage des valeurs de conversion avant de lancer les adsets SKAdNetwork dans Snapchat Ads Manager. Le guide de configuration de Snapchat pour SKAdNetwork est consultable [ici](https://businesshelp.snapchat.com/s/article/skadnetwork).*

**Conditions pour la mise en œuvre**

Tenez compte des éléments suivants dans Snapchat :

* Configurez un [ID d'app Snap](https://businesshelp.snapchat.com/en-US/a/snap-app-id) pour chacune des applications que vous promouvez sur Snapchat.
* Activez les Ad Sets Snapchat pour la mesure SKAN.
* Pour chaque application, vous êtes limité à 10 adsets ayant opté pour l'attribution SKAN en même temps.

<div id="enabling-appsflyer-skan-interoperation-with-snapchat" />

### Activation de l'interopérabilité entre AppsFlyer SKAN et Snapchat

L'interopérabilité se définit dans les paramètres des tableaux de bord AppsFlyer et Snapchat. Aucune configuration n'est requise dans l'application elle-même. Vous devez cependant avoir le SDK AppsFlyer le plus récent.

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
      <td>
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
      <td>
        2
      </td>
      <td>
        Vérification des paramètres SKAN
      </td>
      <td>
        Configurez et activez <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide">la solution AppsFlyer SKAN.</Anchor>

        **Pour visualiser les paramètres SKAN** :

        1. Dans AppsFlyer, rendez-vous dans **Paramètres** > **Studio de Conversion SKAN.**
        2. Cliquez sur Options (⋮) et vérifiez que **la mesure SKAN** est activée.  

           ![skan-settings.png](https://files.readme.io/e4c36e8f5b10a7a4593a8dc776c4c8c43df88577dae8a812303b2d7b3ee37797-4406452401425.png)
        3. Sélectionnez le mode de mesure souhaitée.  
           En savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>.
        4. Notez les noms exacts des événements définis. Vous en aurez besoin à l’étape suivante.
      </td>
    </tr>
    <tr>
      <td>
        3
      </td>
      <td>
        Mappage d'événements in-app
      </td>
      <td>
        Vérifiez et, si nécessaire, apportez des modifications à vos mappages d’événements in-app Snapchat.

        **Pour afficher et définir les mappages d’événements in-app** :

        1. Dans AppsFlyer, rendez-vous dans **Paramètres** > **Intégrations actives**.
        2. Recherchez et sélectionnez **Snapchat**.
        3. Dans l’onglet **Intégration**, si l’option **Activer le partenaire** n’est pas activée, enclenchez-la.
        4. Vérifiez et, si nécessaire, mettez à jour l'ID d'app Snap qui s'affiche dans AppsFlyer avec l'ID d'app qui s'affiche dans le <Anchor target="_blank" href="https://businesshelp.snapchat.com/s/article/snap-app-id?language=en_US">tableau de bord Snapchat</Anchor>.
        5. S’ils sont désactivés, activez les **postbacks d'événements in-app**.  

           [<Image alt="mceclip0.png" src="https://files.readme.io/7dd29ac3be914e9c1b29761d9be525c8945e3ae298274f95f82ede1f548617f6-360017154137.png" width="432px" />](https://files.readme.io/7dd29ac3be914e9c1b29761d9be525c8945e3ae298274f95f82ede1f548617f6-360017154137.png)

           Vérifiez que les **noms d'événements SDK d'événements** in-app que vous définissez dans la mesure SKAN sont mappés aux **identifiants d'événements partenaires,** c'est-à-dire aux noms d'événements Snapchat. Vous devez mapper les événements du type de mesure SKAN sélectionné, ou les événements de votre <Anchor target="_blank" href="/marketers/fr/docs/skan-cv-decode-map-your-cv-to-events">map de conversion personnalisée</Anchor>. **Important !** Le type de mesure par défaut est le revenu.

           <div id="inapp-event-mapping-guide" />

           <div id="in-app-event-mapping-guide" />

           #### Guide du mappage des événements in-app

        | Type de mesure | Obligation pour le mappage |
        | --- | --- |
        | Personnalisé | Mappez les événements in-app que vous avez configurés dans « Personnalisé » aux événements Snap correspondants.<br /><br />Pour transmettre les revenus par postback, vous devez régler Envoyer les revenus sur **Valeurs et revenus**.<br /><br />![SendValueandRevenue.png](https://files.readme.io/412c60db2b09d80a989b7546a6819aa1b030732e0ce004b323dc09db1015c238-11331054047377.png)<br /><br />*af\_skad\_revenue* est utilisé pour les revenus globaux et est mappé à l’événement de revenus Snap.<br /><br />**Important !** Il est possible de mapper plusieurs événements à l'événement de revenus Snap. |
        | Revenu | Map af\_skad\_revenue sur PURCHASE |
        | Conversion | Mappez 1 à 6 événements de conversion aux événements Snapchat correspondants. |
        | Engagement | Mappez l’événement d’engagement que vous avez défini à l’événement Snapchat correspondant. |

        6. Cliquez sur **Enregistrer l'intégration**.
      </td>
    </tr>
    <tr>
      <td>
        4
      </td>
      <td>
        Autoriser Snapchat à partager des postbacks avec AppsFlyer
      </td>
      <td>
        1. Ouvrez votre tableau de bord Snapchat.
        2. Dans la section **Partager les postbacks avec ce MMP**, sélectionnez AppsFlyer.

           [<Image alt="SnapchatSelectAppsFlyer.png" src="https://files.readme.io/e142c4bf54019e8587722af4c5cf5aa95ca49a76948f66e3fb584b003aaacdd6-360017154717.png" width="268px" />](https://files.readme.io/e142c4bf54019e8587722af4c5cf5aa95ca49a76948f66e3fb584b003aaacdd6-360017154717.png)
        3. Cliquez sur **Mettre à jour**.
      </td>
    </tr>
  </tbody>
</Table>

<div id="additional-information" />

## Autres informations

<div id="discrepancies-guide" />

<Accordion title="Guide concernant les écarts de mesure">

| Écart | Détails |
| --- | --- |
| Filtres du tableau de bord | **Cause de la divergence**<ul><li>AppsFlyer : Le tableau de bord SKAN contient les installations relatives aux postbacks iOS reçus.</li><li>Snapchat : Par défaut, le tableau de bord et le rapport Snapchat incluent à la fois SKAN et les installations attribuées classiquement (IDFA). Filtrez le rapport Snapchat pour obtenir uniquement les installations SKAN.</li></ul>**Solution**<br /><br />Choisissez les filtres du tableau de bord Snapchat pour afficher uniquement les installations SKAN, comme indiqué dans cette capture d'écran.<br /><br />[![SnapchatFilter.png](https://files.readme.io/6e067557aabe899df48454aaf4b7be7f466da55e41b7cd3c68db802e48df7d07-360019782137.png)](https://files.readme.io/6e067557aabe899df48454aaf4b7be7f466da55e41b7cd3c68db802e48df7d07-360019782137.png) |
| Différences dans les dates d'installation | **Cause de la divergence**<br /><br />Les dates d'installation entre AppsFlyer et Snapchat peuvent différer comme suit :<ul><li>AppsFlyer - définit la date d'installation avec la formule suivante : Heure d'arrivée du postback - 24 heures - fenêtre de mesure (par défaut 24 heures). Le réglage par défaut est donc de 48 heures. Toutes les heures sont en UTC. <Anchor target="_blank" href="/marketers/fr/docs/about-data-freshness-and-timezone-support#skan">Actualisation des données SKAN.</Anchor></li><li>Snapchat - utilise généralement l’heure d’arrivée du postback iOS pour définir le moment de l’installation, sans rien modifier.</li></ul>**Solution**<br /><br />Tenez compte des éléments précédents lorsque vous comparez les résultats. |

</Accordion>

<div id="see-also" />

> 📄 **Articles connexes**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide">Guide de la solution AppsFlyer SKAN</Anchor>

<div data-zendesk-anchors="skan-interoperability-appsflyer-snapchat=interop%C3%A9rabilit%C3%A9-avec-skan--appsflyer---snapchat h_01HDNZ3SP97C331D45AP1F8CM7=interop%C3%A9rabilit%C3%A9-avec-skan--appsflyer---snapchat enabling-appsflyer-skan-interoperation-with-snapchat=activation-de-linterop%C3%A9rabilit%C3%A9-entre-appsflyer-skan-et-snapchat h_01HDNZ3SP9FZ3AXCNG185DJQY1=activation-de-linterop%C3%A9rabilit%C3%A9-entre-appsflyer-skan-et-snapchat inapp-event-mapping-guide=guide-du-mappage-des-%C3%A9v%C3%A9nements-in-app h_01HDNZ3SPA742313RAJPYSEHWV=guide-du-mappage-des-%C3%A9v%C3%A9nements-in-app additional-information=autres-informations h_01HDNZ3SPASN8P9G5YYQGRFC8F=autres-informations h_01HDNZ3SPA99XHVBPXVWB5MN86=discrepancies-guide h_01HDNZ1BW5EBP0JCX84MTYPQ6K=articles-connexes" />
