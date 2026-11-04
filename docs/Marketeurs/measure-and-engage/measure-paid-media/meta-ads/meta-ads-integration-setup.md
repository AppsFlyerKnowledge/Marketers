---
title: Configurer l’intégration de Meta ads
metadata:
  keywords:
    - iOS
    - Android
    - SDK
    - Facebook
    - App Install
    - View-Through
    - integrated partner
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2013-01-24T20:13:58Z'
  edited_at: '2024-10-12T18:01:42Z'
  id: 207033826
  locale: fr
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/fr/articles/207033826
---
> **En bref :** apprenez à intégrer Meta ads avec AppsFlyer.

<div id="meta-ads-setup-guide" />

## Guide de configuration Meta Ads

Combien de temps faut-il pour attribuer vos publicités Meta ads pour app mobile avec AppsFlyer ?

Si vous avez déjà <Anchor target="_blank" href="/marketers/fr/docs/integrate-the-appsflyer-sdk">intégré le SDK AppsFlyer à votre app</Anchor>, et que vous avez déjà paramétré votre app dans Meta ads, la réponse est : moins d'une minute.

Vous n'avez pas besoin d'implémenter Facebook Login ou d'intégrer votre app au SDK de Facebook pour l'attribution mobile. Il vous suffit de suivre les [instructions de configuration](/docs/meta-ads-integration-setup#configuration-de-base-de-lattribution-meta-ads) ci-dessous. Ensuite, vous pourrez consulter les [options de configuration avancées](/docs/meta-ads-integration-setup#configuration-de-base-de-lattribution-meta-ads-1) pour Meta ads.

### ID d'app Facebook

Pour intégrer des Meta Ads dans AppsFlyer, vous devez d'abord créer puis récupérer l'<Anchor target="_blank" href="https://developers.facebook.com/docs/apps/register">ID d'app Facebook.</Anchor>

**Pour créer l**'ID d'app Facebook :

1. Dans **Meta ads**, rendez-vous dans le <Anchor target="_blank" href="https://developers.facebook.com/apps">tableau de bord de votre app.</Anchor>
2. Dans **Apps**, cliquez sur **Créer une nouvelle app**.
3. Indiquez le nom de votre app, et saisissez un espace de noms unique. Veillez à ajouter la bonne plateforme pour votre application, ou les installations pourront ne pas être attribuées correctement.

Pour récupérer l'**ID d'app Facebook** :

1. Dans **Meta ads**, rendez-vous dans le <Anchor target="_blank" href="https://developers.facebook.com/apps">tableau de bord de votre app.</Anchor>
2. Cliquez sur l'application concernée.
3. Cliquez sur l’ID de l’app, qui apparaît en haut à gauche de l’écran, puis copiez-le.  
   ![meta-ads-for-developters.jpg](https://files.readme.io/86ef4cdfbb965a362c77527a532af2bb7e7eb2b39b477e4a93a2d2f22e19f377-30354101851793.jpg)

AppsFlyer attribue les données en fonction des ID d'app. Un même ID d'app Facebook peut être utilisé à la fois pour [vos apps Android et iOS](https://developers.facebook.com/docs/app-ads/app-setup/). Notez que pour iOS 14 et +, Meta Ads limite le nombre de comptes par application à 9.

<div id="enable-meta-ads-device-level-data" />

<div id="create-and-retreive-facebook-app-id" />

<div id="basic-meta-ads-attribution-setup" />

## Configuration de base de l'attribution Meta ads

Pour commencer l'attribution de campagnes Meta Ads avec AppsFlyer, procédez comme suit :

<Accordion title="Voir">

<Embed title="Configurer l’intégration de Meta ads" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/mrwnab4x7r" providerUrl="https://fast.wistia.com" />

</Accordion>

<Accordion title="Lire">

1. **Pour activer l'intégration avec Meta Ads :**
   1. Accédez à vos applications sur [Meta pour les développeurs](https://developers.facebook.com/apps).
   2. Sélectionnez l'app.  

      ![find-fb-app-id.jpg](https://support.appsflyer.com/hc/article_attachments/25899320112017)
   3. Pour copier l'identifiant de votre application, cliquez dessus en haut de écran.  

      ![meta-ads-copy-app-id.jpg](https://support.appsflyer.com/hc/article_attachments/25899342893585)
   4. Dans AppsFlyer, dans le menu latéral, sélectionnez Collaboration **> Marketplace partenaire**
   5. Recherchez Meta Ads et sélectionnez-le.
   6. Cliquez sur **Configurer l'intégration. Tu es dirigé vers la page de configuration de l'intégration.**
   7. Dans **l'onglet intégration**: Cochez Activer le partenaire.  
       **Remarque :** la case doit rester cochée (<Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">activée</Anchor>) tant que vous travaillez avec le partenaire<Anchor target="_blank" href="/marketers/fr/docs/partner-activation-deactivation">.</Anchor>
   8. Dans **Paramètres généraux** :  

      ![meta_ads_general_settings2.png](https://files.readme.io/f03cc930c7242970294546ffbddb9c648d6eaeecc23b93aa1fadc945a6d777f8-30354101883281.png)

      * Collez l'identifiant de votre application dans l'**identifiant de l'application Facebook** Champ
      * Collez le référent d'installation [clé de déchiffrement de Meta Ads](#données-cryptées-provenant-de-lapi-google-play-referrer-ou-du-référent-meta-install).
   9. Activez ou désactivez le **partage avancé des données**, voir [Partage de données avancé](#advanced_data_sharing) inférieur à (Progressivement disponible pour tous les comptes d'ici octobre) 14, 2024
   10. Cliquez sur **Enregistrer l'intégration**.
2. [facultatif] **Pour configurer les paramètres recommandés :**  

   ![meta_ads_install_attribution.png](https://files.readme.io/82b59d3460ea0487de932b7e49be7de10a8f4eaca151afaca281724f85d0c325-30354145601681.png)

   * Pour correspondre à la fenêtre de visualisation par clic de Meta ads, réglez-le sur 7 jours.  
      Notez que : [il existe des cas spécifiques où la valeur par défaut est différente](https://www.facebook.com/business/help/395050428485124?id=428636648170202)).
   * Pour correspondre à la fenêtre rétrospective de Meta Ads, réglez-le sur un jour.
   * Pour attribuer les noms des utilisateurs qui réinstallent l'application pendant la Fenêtre de réattribution Activez l'**attribution de réinstallation**.  
      Il n'est pas nécessaire d'activer l'attribution par visualisation ou configurez des fenêtres de retour pour la réinstallation de l'attribution, car sa configuration provient de l'attribution d'installation Réglages :

Vous ne voyez toujours pas les résultats dans AppsFlyer ? Reportez-vous à Dépannage de l'intégration Meta ads

</Accordion>

<div id="note-1" />

<div id="campaign-attribution-fields-available-via-the-referrer" />

<div id="note" />

<div id="meta-install-referrer" />

<div id="google-play-install-referrer-api" />

<div id="advanced-meta-ads-attribution-setup" />

## Configuration de base de l'attribution Meta ads

Avec l'attribution de base déjà configurée pour Meta ads, il est temps de mettre en place une configuration d'attribution avancée rapide.

<Accordion title="Voir">

<Embed title="Configurer l’intégration de Meta ads" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/slxtvp2pcs" providerUrl="https://fast.wistia.com" />

</Accordion>

<Accordion title="Lire">

<div id="userlevel-data" />

<Accordion title="Données de niveau utilisateur">

#### Données d'attribution Meta ads restreintes

À compter du 29 octobre 2021, seuls les rapports agrégés est disponible pour les annonceurs. Cela signifie que les deux les données d'attribution affichées et cliquables apparaissent comme « restreint » dans les rapports de données brutes. Autres domaines liés à la source multimédia ne sont pas renseignés. Voir : Restriction du contenu des données brutes

Cela s'applique à tous les annonceurs, systèmes d'exploitation et MMP. Cela concerne les données au niveau de l'appareil pour tous les utilisateurs d'iOS et d'Android, indépendamment du statut de consentement ATT ou de la personnalisation des publicités.

AppsFlyer continue à recevoir des données de niveau appareil depuis Meta ads. Cela signifie que nos capacités d'attribution et de rapports (y compris : attribution multi-touch, LTV, ROI, cohorte, rapports de rétention, protection anti fraude, Audiences, et autres services) restent inchangées. Voir les <Anchor target="_blank" href="/marketers/fr/docs/aggregated-and-analytics-reporting-overview">outils de reporting agrégé et analytiques</Anchor>.

<div id="getting-userlevel-data-for-android-installs" />

#### Obtenir des données de niveau utilisateur pour les installations Android et les événements in-app

**API référent d’installation Google Play**

Bien que les données de niveau utilisateur soient limitées, Meta ads partage les métadonnées des campagnes avec les annonceurs, pour les publicités d'apps Android redirigeant les utilisateurs vers le Google Play Store. Dans ce cas, les champs  d'attribution sont mis à la disposition des annonceurs dans l'API référent d’installation Google Play, qui doit être <Anchor target="_blank" href="/marketers/fr/docs/basic-sdk-integration-guide#attribute-apps-published-on-google-play">intégrée à votre app</Anchor>. Les champs fournis via l'API référent d’installation Google Play renseignent les rapports de données brutes d'AppsFlyer avec le type de matching. `gp_referrer` Ceci n'est   disponible qu'une fois que la clé de décryptage a été envoyée et qu'une installation a été attribuée à Meta ads. Cela permet à AppsFlyer d'attribuer les utilisateurs sans identifiant publicitaire (LAT activé).

**Référent d’installation Meta**

Outre l'API Google Play Install Referrer, Le référent de méta-installation permet à AppsFlyer de recevoir les métadonnées des campagnes publicitaires provenant de la mémoire locale d'un appareil. Ces données sont utilisées à des fins de mesure d'attribution. Le terme principales différences entre l'installation de Google Play L'API Referrer et le référent Meta install sont les suivants :

* Le référent Meta install peut inclure une impression et cliquez sur les données, tandis que Google Play Install L'API Referrer est limitée aux données de clic
* Le référent Meta install inclut potentiellement les données de plusieurs sessions, alors que Google L'API Play Install Referrer est limitée aux données à partir de la dernière session uniquement (l'appareil doit être installé l'application (dans la même session que celle où le clic s'est produit)

Par conséquent, vous pouvez constater une augmentation des méta-attributions installe des rapports de données brutes. Lorsqu'une installation est attribué via l'API Google Play Install Referrer ou le référent Meta install, les données sont disponibles dans des rapports de données brutes. Les champs qui peuvent être disponibles pour l'attribution via le référent Meta install, remplissez Rapports de données brutes AppsFlyer avec type de match `fb_referrer` pour attribution depuis l'application Facebook et `ig_referrer` pour attribution depuis l'application Instagram. Ceci n'est disponible qu'une seule fois la clé de déchiffrement est soumise et une installation est attribué à Meta Ads. Le référent Meta install la clé de déchiffrement est la même [utilisé pour le référent d'installation de Google Play](#données-cryptées-provenant-de-lapi-google-play-referrer-ou-du-référent-meta-install) et n'a pas besoin d'être fourni à AppsFlyer une seconde Heure.

**Champs d'attribution de campagne disponibles via le référent :**

* ID publicitaire
* Nom de la publicité
* ID d’adset
* Nom d'adset
* ID de campagne
* Nom de la campagne
* ID de compte
* Canal

> 📘 **Remarque**
>
> * **Pour l’API référent d’installation Google Play :**
>   * **Le SDK AppsFlyer doit être V5.4.0 ou version ultérieure** pour que les données du référent soient transmises correctement. Les données de référence sont prioritaires sur les données fournies par l'API et ne l'est pas limité Cette solution s'applique Attribution post clic Voir Attribution post-vue.
>   * Le champ Canal est déterminé par la valeur de canal reçue par l'API référent d’installation Google Play (envoyée à Google Play par Meta). Si un canal vide est reçu, le champ Canal affiche « Aucune ».
> * **Pour le référent d’installation Meta : REPORTER à la <Anchor target="_blank" href="/marketers/fr/docs/bulletin-get-meta-ads-attribution-in-raw-data-reports-with-the-meta-install-refe">prérequis et actions requises</Anchor> décrit dans le bulletin.**

<div id="meta-install-referrerfaq" />

#### Référent d’installation Meta—FAQ

**Dans quels cas le référent d’installation Meta s’applique à l'attribution ?**

* Pour l’attribution des installations :
  * Attribution post-clic, pour toutes les campagnes
  * L'attribution par visualisation est prise en charge pour toutes les campagnes d'applications Advantage+ et Campagnes de promotion d'applications manuelles avec de larges ciblage (par exemple, lorsque l'âge et le sexe est réglé sur Par défaut).
* Compatibilité : Google Play Store et sites autres que Google Jouez aux boutiques d'applications Android
* Exceptions : Cela n'inclut pas la redirection des campagnes vers les pages de destination

**À quoi sert le « ciblage étendu » dans Meta ads ?**

Un ciblage large est nécessaire pour obtenir une visibilité Données d'installation La configuration de campagne prise en charge Inclus

* L’âge : Le réglage par défaut (18-65 ans et plus) s’applique
* Le sexe : Le réglage par défaut (Tous) s’applique
* Emplacement : Les groupes de pays et pays sont pris en charge. **Remarque :** Pour des emplacements plus ciblés (villes ou codes postaux, par exemple) campagnes utilisant un ciblage d'inclusion avec ceux-ci doit être défini Réglez sur Relaxed.
* Ciblage détaillé : Segments d'intérêt, comportements, et les données démographiques avancées sont définies comme étant détendues.
* Audiences personnalisées : Réglez sur Relaxed.
* Pour un ciblage « détendu », le « ciblage détaillé Advantage » la case pour les campagnes publicitaires doit être sélectionnée :  

  <Image alt="" src="https://support.appsflyer.com/hc/article_attachments/22950622532497" width="569px" />

<div id="encrypted-data-from-google-play-referrer-api-or-meta-install-referrer" />

#### Données cryptées provenant de l'API Google Play Referrer ou du référent Meta install

Les données provenant de l'API Google Play Referrer ou du référent d'installation Meta sont cryptées par Meta. Ces données peuvent être déchiffrées à   l'aide d'une clé dont vous disposez dans votre compte développeur Meta. Vous devez nous fournir la clé de décryptage telle que décrite dans les actions requises. La clé de décryptage doit être soumise une seule fois par app.

Notez que si la clé n'est pas fournie ou a été supprimée, il y a des cas où les Meta Ads sont toujours attribués pour l'installation provenant d'un référent, et ce même en l'absence des champs d'attribution de la campagne (mentionnés dans la liste ci-dessus). Cela se produit lorsque :

* Meta ads n'a pas revendiqué l'installation
* Les données reçues de l'API référent d’installation Google Play n'ont pas été décodées.
* C'était le dernier clic.

**Pour obtenir votre clé de décryptage dans Meta :**

1. Connectez-vous au portail des développeurs Meta.
2. Accédez à **Mes Apps** dans le coin supérieur droit.
3. Sélectionnez l'app pour laquelle vous souhaitez accéder à votre clé de décryptage.
4. Accédez à **Paramètres** > **Basique** sur le côté gauche de la page.  

   [![](https://files.readme.io/253be6d4cd2a75cc2c038c5b14ed3df067612c46bea174475adba3d196f25789-30354101891985.png)](https://files.readme.io/253be6d4cd2a75cc2c038c5b14ed3df067612c46bea174475adba3d196f25789-30354101891985.png)
5. Faites défiler la page vers le bas jusqu'à la section Android et vous verrez voir votre clé de déchiffrement intitulée Install Referrer clé de déchiffrement sous le champ Package Names. Remarque : Il s'agit de la même section que celle dans laquelle vous avez configuré le nom de votre package et le Google Play Store.

**Pour définir la clé de décryptage dans AppsFlyer :**

1. [Obligatoire] Vérifiez que le SDK AppsFlyer V5.4+ est adopté dans votre application. Ne vous fiez pas aux versions antérieures.
2. Dans AppsFlyer, dans le menu latéral, sélectionnez **Collaborer** > **Intégrations actives**.
3. Sélectionnez **Meta ads**.  
    [![meta_ads_general_settings2.png](https://files.readme.io/f03cc930c7242970294546ffbddb9c648d6eaeecc23b93aa1fadc945a6d777f8-30354101883281.png)](https://files.readme.io/f03cc930c7242970294546ffbddb9c648d6eaeecc23b93aa1fadc945a6d777f8-30354101883281.png)
4. Dans l'onglet **Intégration**, collez Définir la clé de décryptage du référent d'installation Cette opération doit être effectuée une seule fois par app.
5. Cliquez sur **Enregistrer l'intégration**.

</Accordion>

<div id="cost-clicks-and-impressions" />

<Accordion title="Coûts, clics et impressions">

[![meta_cost_tab.png](https://files.readme.io/5c840dbce9c019a8655e8b7b54b8d8e29f3128a8e7115065d0f4083b703b80c0-30354101895185.png)](https://files.readme.io/5c840dbce9c019a8655e8b7b54b8d8e29f3128a8e7115065d0f4083b703b80c0-30354101895185.png)  

Cette intégration fournit des données agrégées sur les coûts, clics et impressions pour vos campagnes, vos annonces, annonces et géos/pays. Consultez les <Anchor target="_blank" href="/marketers/fr/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tableau d'intégration des coûts des réseaux publicitaires</Anchor> pour plus de détails sur les dimensions, les métriques prises en charge, et fonctionnalités.

**Remarque :** Données sur les clics et les impressions. est inclus dans l'intégration. Cependant : Les données de coût nécessitent un abonnement ROI360.

**Pour activer l'API de coûts :**

1. Assurez-vous d'être connecté à l'utilisateur de Meta Ads compte, qui est activé pour gérer le compte campagnes sur les Meta Ads. L'utilisateur qui se connecte doit avoir l'autorisation de lancer toutes les campagnes dans Meta Directeur commercial.
2. Rendez-vous dans l'onglet **Coût**.
3. Activez **Obtenir les données de coût, de clic et d'impression**.
4. Cliquez sur le bouton **f login**. You peut se connecter avec une entreprise ou un administrateur de Meta Ads Compte
5. Lorsque vous y êtes invité, autorisez AppsFlyer à accéder à votre Données des campagnes Meta Ads.  
    **Remarque** : Lors de la première synchronisation des données après l'intégration, ainsi que les synchronisations ultérieures, AppsFlyer reçoit des données sur les coûts des méta-publicités pour une hausse rétroactivement aux 7 derniers jours.

En savoir plus sur comment les Meta Ads définissent les clics et les vues.

**Pour supprimer un compte Meta Ads connecté : IN dans la colonne des actions, passez la souris sur un compte et cliquez sur Supprimer la connexion**

<div id="notes" />

> 📘 **Remarques**
>
> * Si vous êtes déjà connecté à Meta Ads, lorsque vous cliquez sur le bouton **f pour vous connecter** bouton, la fenêtre s'ouvre immédiatement et ferme. C'est tout à fait normal.
> * Si vous avez plusieurs utilisateurs autorisés pour les Meta Ads, la meilleure pratique consiste à effectuer le login pour chacun d'entre eux, pour <Anchor target="_blank" href="/marketers/fr/docs/meta-ads-faq#why-doesnt-cost-data-include-data-from-all-campaigns">évitez d'obtenir des données partielles</Anchor>.

<div id="cost-data-sync-status" />

#### État de synchronisation des données de coût

<Anchor target="_blank" href="/marketers/fr/docs/set-up-roi360-cost-api-to-measure-cost-data#view-cost-api-status">Permet d'afficher le statut de votre API de coûts</Anchor> et de savoir quand AppsFlyer a pu extraire pour la dernière fois les données de coûts correspondantes. Ces éléments se trouvent dans le tableau de bord du statut d'intégration des coûts (et des revenus publicitaires), ou dans le tableau de bord du réseau publicitaire personnel.

Vous pouvez synchroniser plusieurs comptes pour extraire des données de coûts. Pour chaque compte synchronisé, AppsFlyer affiche le statut de l'intégration des coûts et de la dernière gestion d'AppsFlyer pour extraire les données de coûts correspondantes.

En savoir plus sur l'enrichissement de vos données avec les <Anchor target="_blank" href="/marketers/fr/docs/meta-ads-faq#faq-sur-le-coût-des-meta-ads">données de coûts, de clics et d'impressions.</Anchor>

</Accordion>

<div id="inapp-event-mapping" />

<Accordion title="Mappage d'événements in-app">

[![meta_iae_postbacks.png](https://files.readme.io/8f2fd671a067684738964d245a9e80873bbb28f33a55c61ee0cb00a32ac9815e-30354145614865.png)](https://files.readme.io/8f2fd671a067684738964d245a9e80873bbb28f33a55c61ee0cb00a32ac9815e-30354145614865.png)

**Pour mapper des événements in-app :**

1. Activez les **postbacks d'événements in-app.**  
    Lors de l'activation du mappage des événements intégrés à l'application Meta Ads pour une application **pour la première fois**, **af\_app\_open est automatique** mappé à **fb\_mobile\_activate\_app**.
2. Remplissez les paramètres suivants : 

| Nom du paramètre | Description |
| --- | --- |
| **Événement AppsFlyer** | Le nom de l'événement, comme reçu par AppsFlyer soit à partir du SDK intégré à votre application ou de serveur à serveur Évènements :<br />**Astuce** : Ne le faites pas voir l'événement que vous recherchez Pour :<ul><li>Assurez-vous d'activer l'événement sur un appareil avec une installation non biologique et revérifiez.</li><li>Tapez-le Événement AppsFlyer puis cliquez sur **Créer une personnalisation**. En savoir plus sur <Anchor target="_blank" href="/marketers/fr/docs/in-app-event-postback-configuration#événements-personnalisés">mappage d'événements personnalisé.</Anchor></li></ul> |
| **mappé à l’événement partenaire** | Le nom ou l'identifiant unique de chaque événement, tel que défini sur Meta ads Cartographie possible les configurations sont les suivantes :<ul><li>**Champ de texte :** Obtenez le correspondant ID d'événement provenant de Meta ads</li><li>**Liste déroulante :** Sélectionnez le plus adapté AppsFlyer prédéfini event\_</li><li>**Tel quel** : Envoyez les événements tels quels sont, sans mappage de noms.</li></ul> |
| **pour les utilisateurs de** | Sélectionnez l'option d'envoi pour l'événement :<ul><li>**Ce partenaire uniquement** : envoie des postbacks exclusivement lorsque cet événement est attribué à Meta ads.</li><li>**Toutes les sources média, y compris organiques** : envoie un postback pour tout événement attribué à n'importe quel partenaire ou événement organique.</li></ul> |
| **y compris** | <ul><li>**Pas de données (par défaut)** : envoyer uniquement l'événement lui-même sans la valeur de l'événement.</li><li>**Valeurs et revenus** : envoyer tous les paramètres de l'événement, **Y compris** la valeur des recettes (si existe dans l'événement).</li><li>**Valeurs sans revenus** : envoyer tous les paramètres **hormis** Valeur des revenus publicitaires</li></ul> |

3. Pour ajouter un SDK ou événement de serveur à serveur dans la liste, cliquez sur **Ajouter un événement**.

**Limitations concernant les noms d'événements :**

* Limitation de la longueur des noms d'événements : 2 à 40 caractères
* Les caractères suivants ne sont pas autorisés :
  * Deux points (:)
  * Point (.)
  * Caractères non latins (anglais) : As du 12 janvier 2020, Meta Ads rejette Caractères chinois. AppsFlyer n'a pas testé d'autres jeux de caractères et vous devriez utilisez-les uniquement après vérification auprès de Meta annonces si elles prennent en charge ces jeux de caractères Les postbacks
* Les noms d'événements sont sensibles à la casse. Éviter les écarts assurez-vous d'utiliser le bon étui en cas d'événement noms pour toutes les sources multimédia et toutes les versions d'applications.

<div id="use-deep-links-in-meta-ads-campaigns" />

<div id="advanced_matching_data_sharing" />

<div id="see-also" />

<div id="note-3" />

<div id="whatsapp-retargeting-campaign-attribution" />

<div id="note-2" />

> 📘 **Remarque**
>
> * Vous pouvez envoyer Les Ad Revenue Postbacks aux Meta Ads afin qu'ils puissent optimiser leurs campagnes à l'aide des données relatives aux recettes publicitaires :
>   * **Nom de l'événement :** af\_ad\_revenue
>   * **Mappé à :** fb\_mobile\_purchase
> * En savoir plus sur : Mappage des événements in-app des Meta Ads

</Accordion>

<div id="retargeting-attribution" />

<Accordion title="Attribution de retargeting">

Attribution de retargeting AppsFlyer pour les méta-annonces les annonceurs attribuent l'engagement d'un utilisateur existant avec une publicité sur Facebook, et mesurez la qualité du utilisateur, publiez un engagement, à l'aide des rapports AppsFlyer. Il ne doit être utilisé que si vous courez activement des campagnes destinées à vos propres utilisateurs de Facebook.

1. <Anchor target="_blank" href="/marketers/fr/docs/app-settings#reengagement-attribution">Activez le retargeting sur la page Paramètres de l'app</Anchor>.
2. Sur la page partenaire de Meta Ads, activez Attribution du ré-engagement
3. Réglez le Fenêtre rétrospective de réengagement post clic  
    La fenêtre rétrospective de réengagement est la période durée, à compter du clic sur l'annonce, pendant laquelle l'application doit être lancée pour que le clic soit enregistré comme un réengagement.  
    Sélectionnez les unités de la fenêtre rétrospective (heures ou jours), et réglez le curseur sur la valeur souhaitée.  

   ![re-engagement_attribution_toggle.png](https://files.readme.io/86e0bb7d4dfa8e55720ed67d1ff8ea34f0e71df9df12382996bb7ea8817da4ba-30354101904785.png)
4. Activez **l'attribution de réengagement post-vue**.
5. Définissez le curseur de la **fenêtre rétrospective post-vue de réengagement** sur la valeur souhaitée (24 heures maximum). Il s’agit de la période qui commence au moment de de l'impression publicitaire, et durant laquelle l’application doit être lancée pour que l’impression soit enregistrée comme réengagement.

   ![re-engagement_view-through_toggle.png](https://support.appsflyer.com/hc/article_attachments/13880480985489)
6. Définissez la **fenêtre de réengagement**.  
    Il s'agit de la période au cours de laquelle les événements intégrés à l'application de l'utilisateur sont attribués à la source média de retargeting, comme source principale.  
    Vous pouvez définir la valeur en jours (1-90), en heures (jusqu'à à 23), voire à vie. La valeur par défaut est 30 jours.  

   ![re-engagement_window.png](https://files.readme.io/6f589562cd6248697ffa8d5ebb4a72e2fdad118df6abf517e43b4fa23c3332ec-30354101914385.png)

En savoir plus sur : Attribution de <Anchor target="_blank" href="/marketers/fr/docs/retargeting-attribution-guide">retargeting AppsFlyer</Anchor>.

En savoir plus sur : création de <Anchor target="_blank" href="/marketers/fr/docs/self-reporting-networks-srns#deep-linking-avec-des-srn">liens profonds entre les utilisateurs à partir de SRN tels que les Meta Ads</Anchor>.

</Accordion>

<div id="advanced_data_sharing" />

<Accordion title="Partage avancé des données">

Lorsque le **partage de données avancé** est activé activé, Meta reçoit les messages et les événements au niveau de l'appareil identifiants pour tous les appareils, y compris les appareils qui n'ont pas rendu leur identifiant publicitaire (IDFA) disponible. En outre, lorsque le **partage de données avancé** est activé, ces événements peuvent être attribués par AppsFlyer. Lorsque cette option est désactivée, uniquement les publications et les événements provenant des appareils avec un IDFA sont envoyés et attribués.

Cette méthode fonctionnera pour la désinscription simple et double Appareils : Les événements seront limités au dernier clic attribution, avec une fenêtre d'attribution maximale de 24 heures

Remarque : Disponible progressivement pour tous les comptes d'ici le 14 octobre 2024

</Accordion>

<div id="comply-with-california-consumer-privacy-act-ccpa" />

<Accordion title="Être conforme avec la California Consumer Privacy Act (CCPA)">

Le respect des réglementations de confidentialité du CCPA limite données provenant d'utilisateurs de Meta Ads basés en Californie, ÉTATS-UNIS

**Pour vous conformer aux règles de la CCPA :** Allumer **Limiter l'utilisation des informations personnelles des utilisateurs par Meta Ads (CCPA)** Dans l'onglet intégration:

En savoir plus sur : <Anchor target="_blank" href="/marketers/fr/docs/send-opendsr-api-requests">lois sur la protection des données</Anchor>.

</Accordion>

<div id="ad-revenue-recording" />

<Accordion title="Enregistrement des revenus publicitaires">

![meta_ads_ad_revenue.png](https://files.readme.io/5c27f2adf0e4515a7ad0efac4776eb296874273e2af71e14c9be8bd65a983757-30354101917201.png)

Si votre application utilise les revenus publicitaires du réseau Meta Audience pour la monétisation des publicités, vous pouvez enregistrer vos revenus à partir de Meta Ads sur AppsFlyer. Ceci, avec ou sans les données sur les revenus d'achat intégrées à l'application vous offrent un **une image complète des revenus de vos utilisateurs**.

<div id="record-meta-audience-network-ad-revenue" />

#### Enregistrer les revenus publicitaires du réseau Audience Meta

1. Dans l'onglet **Revenus publicitaires** et Activez l'option Obtenir les données des revenus publicitaires.
2. Sélectionnez le type de données agrégées sur les revenus publicitaires vous souhaitez recevoir : **Revenus attribués** : et/ou **Revenus de monétisation agrégés** :
   * **Revenus attribués** : Revenus basés sur l'acquisition d'utilisateurs Source  
      Définissez la **source de l'événement**, qui est l'événement qui représente votre modèle de revenus publicitaires le meilleur possible manière. Par exemple, si vos revenus sont sur la base des impressions, il est recommandé pour envoyer à AppsFlyer un événement ad\_viewed. Le meilleur événement peut être configuré pour chaque plateforme de monétisation séparément. Cependant, il est également possible d’utiliser l’événement. event\_ Dans dans ce cas, les recettes publicitaires sont attribuées à chaque ouverture d'application effectuée par l'utilisateur.
   * **Revenus de monétisation agrégés** : Revenus basés sur la source de la publicité.
3. L'événement **Revenus publicitaires** s'affiche. Il s'agit d'un champ en lecture seule présentant la nouvelle annonce événement de revenus appelé [événement source] \_monétisé (par exemple, Ad\_Watched\_Monetized tel qu'il est affiché au dessus de L'événement relatif aux recettes publicitaires est présenté dans le tableau de bord en tant qu'événement supplémentaire.
4. Cliquez sur **Se connecter à Meta Ads** pour activer la collecte de Meta Audience Network Revenus publicitaires générés par les Meta Ads. Connectez-vous avec votre Meta ajoute des informations d'identification pour autoriser Meta Audience Network Revenu publicitaire :
5. Entrez le Saisissez l'**ID d'app du réseau Audience ([ID d'app Facebook](/docs/meta-ads-integration-setup#id-dapp-facebook)).** Vous pouvez l'obtenir auprès du réseau Meta Audience.
   * Obtenez le ID d'app Facebook
   * Copiez l'ID dans l'ID de l'**application Audience Network** champ dans AppsFlyer.
6. Cliquez sur **Enregistrer les revenus publicitaires.**

</Accordion>

<div id="permissions" />

<Accordion title="Autorisations">

Activez les méta-annonces pour effectuer diverses actions et pour accéder à vos données en fonction des autorisations disponibles.

En savoir plus sur : <Anchor target="_blank" href="/marketers/fr/docs/set-up-an-integrated-partner#permissions-tab">accorder des autorisations aux partenaires intégrés</Anchor>.

</Accordion>

</Accordion>

<div id="aggregate-event-measurement-aem-for-ios" />

## Mesure agrégée des événements (AEM) pour iOS

<Anchor target="_blank" href="/marketers/fr/docs/meta-ads-aggregate-event-measurement-aem-for-ios">AppsFlyer prend en charge la Mesure agrégée des événements (AEM) de Meta ads.. Cette solution permet d'optimiser les conversions iOS et les événements in-app, tout en attribuant les réengagements iOS à Meta ads.</Anchor>

<div id="aem-attribution-is-not-working" />

<div id="meta-ads-integration-troubleshooting" />

## Dépannage de l'intégration Meta ads

Si vous avez complété l'intégration de base et que vous ne voyez toujours pas les résultats de Meta ads sur le tableau de bord AppsFlyer, vérifiez si vous avez eu des nouvelles installations de Meta ads depuis l'intégration.

Si c’est le cas, consultez les raisons principales ci-dessous pour résoudre le problème :

<div id="no-idfa-collection" />

<Accordion title="Aucune collecte IDFA">

Comme indiqué dans le Guide d'intégration SDK - iOS, vous devez ajouter AdSupport.framework à votre projet pour que la collection IDFA puisse avoir lieu. Vérifiez le rapport Données brutes d'installation pour voir si la colonne IDFA est vide ou pas. Nous vous recommandons d'autoriser votre app à collecter l'IDFA dans le cadre des apps iOS, et le GAID dans le cadre des apps Android.  
Depuis iOS 14.5, vous devez afficher la fenêtre Apple ATT et obtenir le consentement de l'utilisateur avant de pouvoir collecter l'IDFA.

**Remarque :** l'attribution SKAdNetwork n'est pas affectée par la disponibilité de l'IDFA. Pensez malgré tout à activer l'option « campagne iOS 14 » dans Meta ads lorsque vous configurez les campagnes iOS 14.

</Accordion>

<div id="wrong-facebook-app-id" />

<Accordion title="ID d'app Facebook incorrect">

L'ID d'app Facebook a été mal configuré dans AppsFlyer.  
Vérifiez que l’ID d’app est correct et qu'il correspond au tableau de bord Meta Ads.  

Remarque : vous pouvez également utiliser l'<Anchor target="_blank" href="https://developers.facebook.com/tools/explorer/?method=GET&path=&version=v6.0">API graphique de Facebook</Anchor> pour valider votre ID d'app Facebook.

</Accordion>

<div id="app-status-on-meta-ads" />

<Accordion title="Statut de l'application sur Meta ads">

Pour garantir le bon fonctionnement de l'attribution, l'app doit être définie sur Meta ads comme **En ligne** plutôt que **En développement**.

![fb-app-status.png](https://files.readme.io/b982355eb0d3d858988866673d3f9ee4f081c43042221d11ebfb93afe05c36a4-30354101922577.png)

</Accordion>

<div id="wrong-type-of-meta-ads-campaign" />

<Accordion title="Mauvais type de campagne Meta ads">

Vérifiez que la campagne Meta ads repose sur des **publicités d'installation d'app mobile** ou sur l'**engagement d'app mobile**. Si d'autres objectifs de campagne sont définis (ex :clic sur un lien pour les pages d'accueil), pour avoir accès à le mesure des installations mobile l'annonceur doit cocher l'option Enregistrement d'événements d'app lorsqu'il configure la campagne Meta ads.

</Accordion>

<div id="meta-ads-app-install" />

<Accordion title="Installation d'une app Meta ads">

Lors de la configuration de la campagne d'installation d'app Meta ads, vous pouvez sélectionner l'app dans une liste déroulante, ou bien coller l'URL complète du store directement dans l'app. Les deux méthodes fonctionnent avec Meta ads, mais la seconde ne permet pas l'attribution AppsFlyer.

Configuration correcte - réussite de l'attribution.

<Image alt="fb-app-install.png" src="https://files.readme.io/5cb735144128035d752281f7d94e2015478c62049a2e96fc5a42400513f7fad3-30354101926033.png" width="496px" />

Configuration incorrecte - échec de l'attribution.

![fb-app-incorrect_setup.png](https://files.readme.io/77d508b62d5445cac071262cb35e4a89a6dfa5be439325254c0b8f6c5f51606c-30354145644561.png)

</Accordion>

## Mise à jour de Meta Ads

<div id="optional--configure-recommended-settings" />

<div id="set-the-meta-ads-active-integration" />

> 🚧 **Important**
>
> Depuis le 29 octobre 2021, seuls les rapports agrégés des Meta ads sont disponibles pour les annonceurs. Cela inclut les installations et les événements in-app. Cela s'applique à tous les annonceurs, systèmes d'exploitation et MMP. Cela concerne les données au niveau de l'appareil pour tous les utilisateurs d'iOS et d'Android, indépendamment du statut de consentement ATT ou de la personnalisation des publicités.
> Les données brutes pour les installations et les événements in-app effectués avant le changement (29 octobre 2021) continuent d'être disponibles.
> Notez que les données relatives aux utilisateurs peuvent être reçues via le référent Google Install.
> Consultez notre <Anchor target="_blank" href="/marketers/fr/docs/bulletin-action-required-get-meta-ads-raw-data-using-google-install-referrer">bulletin d'informations</Anchor> pour plus de détails.

<div id="ios-14-updates-relating-to-meta-ads" />

### Mises à jour d'iOS 14 relative à Meta Ads

AppsFlyer confirme que notre intégration de la MMP avec Meta ads implémente systématiquement le drapeau *Suivi d'annonceur activé*. Ce qui signifie qu'aucune action n'est requise de votre part au niveau d'AppsFlyer. Ces informations sont fournies conformément à la liste de vérification iOS 14 pour l'app Meta ads publiée en février 2021.

<div id="see-also-1" />

> 📄 **À consulter également**
>
> * Pour iOS 14, voir l'<Anchor target="_blank" href="/marketers/fr/docs/skadnetwork-skan-interoperation-with-meta-ads">interopérabilité SKAN Meta Ads</Anchor>.
> * <Anchor target="_blank" href="/marketers/fr/docs/configuring-meta-campaign-management-partners">Configuration des partenaires pour la gestion des campagnes Meta</Anchor> (<Anchor target="_blank" href="/marketers/fr/docs/bidalgo-meta-campaign-management-partner-configuration">Bidalgo</Anchor> / <Anchor target="_blank" href="/marketers/fr/docs/kenshoo-meta-campaign-management-partner-configuration">Kenshoo</Anchor> / <Anchor target="_blank" href="/marketers/fr/docs/adquant-meta-campaign-management-partner-configuration">Adquant</Anchor> / <Anchor target="_blank" href="/marketers/fr/docs/webpals-mobile-meta-campaign-management-partner-configuration">Webpals</Anchor>)

<div data-zendesk-anchors="facebook-ads-setup-guide=guide-de-configuration-meta-ads 01H7YJVNMSZ4WG4HWBZF648HZN=guide-de-configuration-meta-ads facebook-app-id=id-dapp-facebook 01H7YJVNMTP8PP2S88Q70E082G=id-dapp-facebook basic-facebook-attribution-setup=configuration-de-base-de-lattribution-meta-ads 01H7YJVNMTFW076FAJZGJWT4R9=configuration-de-base-de-lattribution-meta-ads advanced-facebook-attribution-setup=configuration-de-base-de-lattribution-meta-ads-1 01H7YJVNMTHF800PD5CEWPFS49=configuration-de-base-de-lattribution-meta-ads-1 01H7YJVNMTP2CA09QPEQ4DV37C=userlevel-data meta-ads-restricted-attribution-data=donn%C3%A9es-dattribution-meta-ads-restreintes h_01HNW0B77CQ4HS6ERHBD8YV28E=donn%C3%A9es-dattribution-meta-ads-restreintes getting-userlevel-data-for-android-installs=obtenir-des-donn%C3%A9es-de-niveau-utilisateur-pour-les-installations-android-et-les-%C3%A9v%C3%A9nements-in-app 01H7YJVNMTYJV5H1FSM5HBD3N7=obtenir-des-donn%C3%A9es-de-niveau-utilisateur-pour-les-installations-android-et-les-%C3%A9v%C3%A9nements-in-app 01H7YJVNMTAQKG7YDS72125HFP=remarque meta-install-referrer%E2%80%94faq=r%C3%A9f%C3%A9rent-dinstallation-metafaq h_01HQR6QZKDEWXXMGFXXMG2VZ7F=r%C3%A9f%C3%A9rent-dinstallation-metafaq encrypted-data-from-the-referrer=donn%C3%A9es-crypt%C3%A9es-provenant-de-lapi-google-play-referrer-ou-du-r%C3%A9f%C3%A9rent-meta-install 01H7YJVNMTZGQFEGJD9QEEVZHR=donn%C3%A9es-crypt%C3%A9es-provenant-de-lapi-google-play-referrer-ou-du-r%C3%A9f%C3%A9rent-meta-install 01H7YJVNMTBN9RJ6Q7TJ1AJ0XX=cost-clicks-and-impressions 01H7YJVNMTGRBQG54DVMJDHDKS=remarques cost-data-sync-status=%C3%A9tat-de-synchronisation-des-donn%C3%A9es-de-co%C3%BBt 01H7YJVNMTRQAYG7TY29AX4MZS=%C3%A9tat-de-synchronisation-des-donn%C3%A9es-de-co%C3%BBt 01H7YJVNMTNRREKWY96CK9JJKV=inapp-event-mapping 01H7YJVNMT2DRVR26F8CDDTWHP=remarque-1 01H7YJVNMV5AZ9G2KCKEFF1CSV=retargeting-attribution 01H7YJVNMVSA4Y33MW6Q8Y777Y=advanced_data_sharing 01H7YJVNMVWRG10SZY1B33H5EA=ad-revenue-recording record-meta-audience-network-ad-revenue=enregistrer-les-revenus-publicitaires-du-r%C3%A9seau-audience-meta 01H7YJVNMV1TTHKMMX4TFB2BF3=enregistrer-les-revenus-publicitaires-du-r%C3%A9seau-audience-meta 01H7YJVNMVMW5BXWEP8BPX4D7E=permissions aggregate-event-measurement-aem-for-ios=mesure-agr%C3%A9g%C3%A9e-des-%C3%A9v%C3%A9nements-aem-pour-ios 01H7YJVNMVGFYMHE5FACTD9NS0=mesure-agr%C3%A9g%C3%A9e-des-%C3%A9v%C3%A9nements-aem-pour-ios meta-ads-integration-troubleshooting=d%C3%A9pannage-de-lint%C3%A9gration-meta-ads 01H7YJVNMVCAQ6ETKBGCAM31B9=d%C3%A9pannage-de-lint%C3%A9gration-meta-ads 01H7YJVNMV3YRF59RX87TJCT8D=no-idfa-collection 01H7YJVNMVHCYVWKDW5WWPX1A5=wrong-facebook-app-id 01H7YJVNMVE9QJAXQBD4P14C88=app-status-on-meta-ads 01H7YJVNMVBRVTT9HH7KM8P33B=wrong-type-of-meta-ads-campaign 01H7YJVNMV4G3VP40E6VFD7SJD=meta-ads-app-install facebook-ads-updates=mise-%C3%A0-jour-de-meta-ads 01H7YJVNMV5MQX81Z9NP3X5KJM=mise-%C3%A0-jour-de-meta-ads 01H7YJVNMVS2A95Z20R1ENQYPR=important ios-14-updates-relating-to-facebook=mises-%C3%A0-jour-dios-14-relative-%C3%A0-meta-ads 01H7YJVNMVQP5PR6XDHTCPXVDC=mises-%C3%A0-jour-dios-14-relative-%C3%A0-meta-ads h_01HDP0Y4CZBZEK5VZ6FG3T31JB=%C3%A0-consulter-%C3%A9galement" />
