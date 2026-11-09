---
title: 'Obtenir les données de postback SKAN depuis Google Ads '
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
  created_at: '2021-06-28T19:34:39Z'
  edited_at: '2023-12-21T10:06:02Z'
  id: 4403215779857
  locale: fr
  section: SKAN interoperation
  section_id: 6552115163153
  url: https://support.appsflyer.com/hc/fr/articles/4403215779857
---
> **En bref :** autorisez Google à transmettre le contenu des postbacks iOS de votre app SKAdNewtork (SKAN) à AppsFlyer.

<div id="get-skan-postback-data-from-google-ads" />

## Obtenir les données de postback SKAN depuis Google Ads

Si vous travaillez avec différents partenaires de réseau publicitaire, nous vous conseillons de le configurer dans AppsFlyer. Les résultats de performance SKAN pour l'ensemble de vos partenaires de réseaux publicitaires (accompagnés de différentes mesures, comme le coût) seront ainsi disponibles via la plateforme AppsFlyer.

**Champ d'application des rapports SKAN avec Google Ads**

* Google Ads transmet à AppsFlyer les postbacks SKAN iOS agrégés reçus dans le cadre des campagnes d'applications iOS. Ces postbacks représentent les installations sur plusieurs canaux (comme l'affichage et YouTube), mais ils excluent généralement la plupart des recherches car SKAN ne prend pas en charge le suivi web>app à ce stade.
* AppsFlyer décode le postback et met à jour le tableau de bord ainsi que les rapports SKAN (y compris le rapport sur les données brutes du postback).
* <Anchor target="_blank" href="/marketers/fr/docs/self-reporting-networks-srns#ios-145-srn-attribution">Implications relatives à iOS 14.5 pour le reporting SRN</Anchor>

**Attention** :

À la réception du postback iOS, Google détermine l'heure du dernier clic à l'aide des indicateurs de diffusion publicitaire. AppsFlyer de son côté prend l'heure du clic pour définir l'heure de l'installation. Ceci peut entraîner des différences entre les tableaux de bord AppsFlyer et Google.

En raison du système employé par Google pour rapporter les clics et de sa mise à jour quotidienne des données rétroactives, AppsFlyer extrait les données des 13 jours précédents, puis affiche l'installation avec le dernier clic qui précède le jour d'installation.  Par exemple, un clic effectué le 1er juillet peut être rapporté à AppsFlyer jusqu'au 15 août. AppsFlyer affiche cette installation au niveau de la date du clic rapporté par Google. Ce principe se répercute dans les <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide#reporting-options">rapports</Anchor> de la manière suivante :

* Les rapports agrégés et le tableau de bord sont mis à jour d'une manière rétroactive.
* Les <Anchor target="_blank" href="/marketers/fr/docs/skan-raw-data-reports">rapports de données brutes</Anchor> ne sont pas modifiés d'une manière rétroactive. Les données (fournies via Data Locker) sont classées dans des dossiers en fonction du jour où Google a transmis les données à AppsFlyer (date d'arrivée des données).

<div id="set-up-interoperation" />

## Configurer l'interopérabilité

Pour configurer l'interopérabilité avec Google Ads, suivez les étapes décrites dans les onglets suivants.

<div id="set-up-postbacks" />

<Accordion title="Configurer les postbacks">

**Pour configurer l'envoi des postbacks :**

| Étape | Action | Détails |
| --- | --- | --- |
| <span id="1"></span>1 | Examen des paramètres SKAN | Vérifiez que la <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide">solution SKAN</Anchor> AppsFlyer est configurée et activée. Elle permet au SDK AppsFlyer d'appeler les API SKAN et de définir la valeur de conversion.<br /><br />**Pour visualiser les paramètres SKAN** :<ol><li>Dans AppsFlyer, ouvrez **Configuration** > **Studio de Conversion SKAN**.</li><li>Cliquez sur Options (⋮) et vérifiez que **la mesure SKAN** est activée.</li></ol>![skan-settings.png](https://files.readme.io/5602fded7e030177bb921ff83ff1e6dad7a230a87825e112314935a4c3dd83dd-4406452045457.png)<ol><li>Sélectionnez votre mode de mesure préféré.<br />En savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>.</li><li>Notez les noms exacts des événements définis. Vous en aurez besoin à l’étape suivante. **Attention** : les noms sont sensibles à la casse.</li></ol> |
| <span id="2"></span>2 | Mappage des événements in-app dans AppsFlyer | **Pour afficher et définir des mappages d’événements in-app** :<ol><li>Dans AppsFlyer, allez dans **Configuration** > **Intégrations actives**.</li><li>Sélectionnez **Google Ads**.</li><li>Dans l'onglet **Intégration**, vérifiez que l'option **Activer le partenaire** est activée. Si ce n'est pas le cas, vous devez d'abord procéder à l'<Anchor target="_blank" href="/marketers/fr/docs/google-ads-adwords-integration-setup-for-advertisers">intégration avec Google Ads</Anchor>.</li><li>Dans la **section Postback d'événements in-app :**<ol><li>Si ce n'est pas le cas, activez les **postbacks d'événements in-app**.</li><li>La meilleure méthode consiste à mapper les événements liés au type de mesure sélectionné. Attention ! Dans le cas de la mesure des revenus, vous devez mapper af\_skad\_revenue à l'événement de revenu Google approprié.</li></ol></li><li>Faites défiler jusqu'au bas de la page.</li><li>Cliquez sur **Enregistrer l'intégration**.</li></ol> |

</Accordion>

<div id="allow-google-ads-to-share-skan-data-with-appsflyer" />

<Accordion title="Autoriser Google Ads à partager les données SKAN avec AppsFlyer">

Pour voir les installations SKAN attribuées à Google Ads dans le tableau de bord SKAN AppsFlyer, vous devez autoriser Google Ads à partager les données SKAN avec AppsFlyer.

**Pour autoriser Google Ads à partager les données SKAN avec AppsFlyer :**

1. La procédure suivante doit être effectuée soit par l'annonceur, soit par l'agence, soit par les deux.
2. Dans AppsFlyer, allez dans **Configuration** > **Intégrations actives**.
3. Recherchez et sélectionnez **Google Ads**.
4. Ouvrez l'onglet **SKAN**.

   <Image align="center" alt="mceclip0.png" src="https://files.readme.io/ba8d881ca8430bfdcf67a37e862ad3e31a9af522f2f877d3fba30bc2e13006a6-4404428381457.png" width="309px" />
5. Si le **message *Temporairement indisponible* s'affiche**, cela indique souvent qu'un bloqueur de publicité est activé. Si c'est le cas, désactivez le bloqueur de publicité et rechargez la page. Si ce n'est pas le cas, contactez l'assistance AppsFlyer.

   <Image align="center" alt="mceclip1.png" src="https://files.readme.io/e86b868f71e11ad347ff7557a793090d9d6adb8fe4df4f9010c8d770b373ac6a-4404428420497.png" />
6. Cliquez sur **Connexion à Google Ads**.
   * Vous devez vous connecter à Google Ads en utilisant le rôle d'admin du compte .
   * Si le compte Google est associé à plusieurs applications, une seule connexion suffit pour que toutes les applications soient autorisées. En d'autres termes, vous n'avez pas à autoriser chaque application une par une.
   * AppsFlyer extrait des données pour toutes les apps iOS AppsFlyer associées à votre compte Google, quel que soit le paramètre d'activation du partenaire de l'application.
7. Suivez les instructions de l’interface utilisateur.
8. Dans certains cas, on pourra vous demander de donner à AppsFlyer l'autorisation de **gérer vos campagnes AdWords**. Vous devrez alors activer l'autorisation. Ne vous inquiétez pas : nous ne modifierons pas pour autant les paramètres de votre campagne.

   <Image align="center" alt="GoogleManageAdWords.png" src="https://files.readme.io/bf327f152f937cdbea0b71cca72cc989aa83de6cef83677fca1f687b71aa8606-4405185007121.png" width="182px" />
9. Vérifiez que le statut du compte **En attente de synchronisation** s'affiche.  
   Ce message restera affiché jusqu'à ce que nous recevions des données de Google Ads (maximum 24 heures).
10. Attendez 02:00 UTC le lendemain, puis vérifiez que le statut est passé à **actif.**  
    Les données du tableau de bord SKAN sont mises à jour quotidiennement à 08:00 UTC. **Attention** ! Comme indiqué dans la section des remarques, Google peut mettre à jour les données jusqu'à 13 jours rétroactivement.
11. En savoir plus sur les [différences dans les mesures](/docs/get-skan-postback-data-from-google-ads#measurement-and-timing-differences-between-appsflyer-and-google-ads).

</Accordion>

<div id="additional-information" />

## Informations supplémentaires

<div id="turning-off-the-skan-integration" />

<Accordion title="Désactivation de l’intégration SKAN">

Lorsque vous désactivez votre intégration Google Ads, il ne suffit pas seulement de décocher **Activer le partenaire**, vous devez également supprimer chaque connexion SKAN pour que les données SKAN cessent d'être enregistrées.

**Pour désactiver l’intégration SKAN :**

1. Dans AppsFlyer, allez dans **Configuration** > **Intégrations actives**.
2. Recherchez et sélectionnez Google Ads.
3. Ouvrez l'onglet **SKAN**.
4. Cliquez sur l’icône suppression dans le compte que vous souhaitez supprimer.

</Accordion>

<div id="measurement-and-timing-differences-between-appsflyer-and-google-ads" />

<Accordion title="Différences de mesures et de synchronisation entre AppsFlyer et Google ads">

| Élément | Détails |
| --- | --- |
| <span id="earliest-data-availability"></span>Première disponibilité des données | Les données sont disponibles à partir de la date où vous activez l'intégration, en heure UTC. Comme Google utilise l'heure du clic, les installations qui se produisent avant la date de début peuvent s'afficher d'une manière rétroactive. |
| <span id="install-date"></span>Date d'installation | Google définit l'heure d'installation selon l'heure estimée du tout dernier clic pré installation. C'est Google qui détermine l'heure du clic selon les indicateurs de diffusion publicitaire.<br /><br />Les éléments suivants doivent être pris en compte pour comparer les sources média et le tableau de bord AppsFlyer :<ul><li>AppsFlyer ne prend pas en compte le fuseau horaire de l'application, ni celui du compte publicitaire Google Ads.</li><li>Google peut rapporter rétroactivement les installations pendant 45 jours après l'installation.</li><li>Pour les autres sources média, nous calculons le temps d'installation d'après l'heure d'arrivée du postback.</li></ul> |
| <span id="installs"></span>Installations | Depuis l'API Google Ads V10+, AppsFlyer n'affiche que les installations issues des postbacks contenant did\_win=TRUE. En conséquence, le nombre d'installations dans AppsFlyer peut être plus bas que celui du tableau de bord Google Ads. |

</Accordion>

<div id="troubleshooting-and-faq" />

<Accordion title="Dépannage et FAQ">

| Élément | Détails |
| --- | --- |
| <span id="sending-events-to-google-ads"></span>Envoi d'événements à Google Ads | **Q** : Faut-il envoyer des postbacks d'événements supplémentaires à Google Ads pour les événements non sélectionnés dans l'option de mesure de la valeur de conversion ?<br /><br />**R** : Pour les utilisateurs ayant donné leur consentement, envoyez la gamme complète d'événements afin de permettre l'optimisation par Google Ads. |
| <span id="map-multiple-events-to-the-same-google-ads-event"></span>Mapper plusieurs événements à un même événement Google Ads | **Q** : Puis-je mapper plusieurs événements in-app à un événement Google Ads ?<br /><br />**R** : Si plusieurs événements sont mappés à un événement standard Google Ads, Google Ads ne peut pas différencier les événements. Google Ads optimise donc en fonction de l'événement qu'il reconnaît. |
| <span id="campaign-types-supported"></span>Types de campagnes pris en charge | **Q :** Quels types de campagnes Google Ads sont pris en charge ?<br /><br />**R** : Les campagnes iOS web-to-app et app-to-app, incluant les recherches, vidéos, etc. |
| <span id="no-data-to-pull"></span>Pas de données à extraire | **Q :**  Pourquoi l'état de la connexion affiche-t-il « Pas de données à extraire : vérifiez vos autorisations de partage de données Google » ?<br /><br />**R**: Soit il n'y a pas encore de données SKAN, soit vous devez vous connecter à Google Ads à l'aide d'un rôle d'admin du compte. |

</Accordion>

<div id="specifications-and-limitations" />

<Accordion title="Caractéristiques et limitations">

| Caractéristiques | Description |
| --- | --- |
| <span id="engaged-views"></span>Visionnages engagés | Les visionnages engagés sont comptabilisées comme des clics, les postbacks de visionnages engagés sont envoyés au même titre que pour n'importe quelle attribution de clic. |
| <span id="data-freshness"></span>Actualisation des données | <ul><li>Nous collectons les données SKAN de Google Ads quotidiennement à partir de 01:00 UTC.</li><li>Les tableaux de bord et les données agrégées sont mis à jour 7 heures plus tard.</li></ul> |
| <span id="reports-available"></span>Rapports disponibles | Les données Google Ads sont disponibles dans le tableau de bord SKAN, les rapports agrégés et les rapports de données brutes. Voir les <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide#reporting-options">options dans les rapports SKAN</Anchor>. |
| <span id="agencies"></span>Agences | Si l’agence a un rôle d’admin dans le compte Google Ads de l’annonceur, elle peut lancer la procédure détaillée dans cet article et activer l’interopérabilité Google SKAN au nom de l’annonceur. Les annonceurs n'ont pas besoin de se connecter à leur Google Ads. Le login de l'agence sera indiqué dans le compte de l'annonceur. |

</Accordion>

<div id="see-also" />

> 📄 **À consulter également**
>
> * <Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-solution-guide">Guide de la solution SKAN AppsFlyer</Anchor>

<div data-zendesk-anchors="get-skan-postback-data-from-google-ads=obtenir-les-donn%C3%A9es-de-postback-skan-depuis-google-ads h_01HCHYGCVJA3C8WJS8JH7BG0CD=obtenir-les-donn%C3%A9es-de-postback-skan-depuis-google-ads set-up-interoperation=configurer-linterop%C3%A9rabilit%C3%A9 h_01HCHYGCVJY5KT4J6RQS0BJ90G=configurer-linterop%C3%A9rabilit%C3%A9 h_01HCHYGCVJKHF0NFJSAZMMKZ7Z=set-up-postbacks h_01HCHYGCVJEA39W87MWXF7P018=allow-google-ads-to-share-skan-data-with-appsflyer additional-information=informations-suppl%C3%A9mentaires h_01HCHYGCVJTS53PCGK21BEZB2T=informations-suppl%C3%A9mentaires h_01HCHYGCVJCSGKYQD3EH0GKZVS=turning-off-the-skan-integration h_01HCHYGCVJE80JX9BKE8NFMA45=measurement-and-timing-differences-between-appsflyer-and-google-ads h_01HCHYGCVJX832CCX87JHGD50W=troubleshooting-and-faq h_01HCHYGCVJ1D32JW8G9YSR27PN=specifications-and-limitations h_01HE7RMSECNDW9VD9XY6H01H55=%C3%A0-consulter-%C3%A9galement" />
